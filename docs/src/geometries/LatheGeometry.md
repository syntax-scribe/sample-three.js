[⬅️ Back to Table of Contents](../../index.md)

# 📄 `LatheGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 22 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/geometries/LatheGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Float32BufferAttribute` | `../core/BufferAttribute.js` |
| `BufferGeometry` | `../core/BufferGeometry.js` |
| `Vector3` | `../math/Vector3.js` |
| `Vector2` | `../math/Vector2.js` |
| `clamp` | `../math/MathUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `uvs` | `any[]` | let/var | `[]` | ✗ |
| `initNormals` | `any[]` | let/var | `[]` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `inverseSegments` | `number` | let/var | `1.0 / segments` | ✗ |
| `vertex` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `uv` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `normal` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `curNormal` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `prevNormal` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `dx` | `number` | let/var | `0` | ✗ |
| `dy` | `number` | let/var | `0` | ✗ |
| `phi` | `number` | let/var | `phiStart + i * inverseSegments * phiLength` | ✗ |
| `x` | `number` | let/var | `initNormals[ 3 * j + 0 ] * sin` | ✗ |
| `y` | `number` | let/var | `initNormals[ 3 * j + 1 ]` | ✗ |
| `z` | `number` | let/var | `initNormals[ 3 * j + 0 ] * cos` | ✗ |
| `base` | `number` | let/var | `j + i * points.length` | ✗ |
| `a` | `number` | let/var | `base` | ✗ |
| `b` | `number` | let/var | `base + points.length` | ✗ |
| `c` | `number` | let/var | `base + points.length + 1` | ✗ |
| `d` | `number` | let/var | `base + 1` | ✗ |


---

## Functions

### `LatheGeometry.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `Object.assign`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.parameters = Object.assign( {}, source.parameters );

		return this;

	}
```
</details>

### `LatheGeometry.fromJSON(data: any): LatheGeometry`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @return {LatheGeometry} A new instance.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `LatheGeometry`

<details><summary>Code</summary>

```typescript
static fromJSON( data ) {

		return new LatheGeometry( data.points, data.segments, data.phiStart, data.phiLength );

	}
```
</details>


---

## Classes

### `LatheGeometry`

<details><summary>Class Code</summary>

```ts
class LatheGeometry extends BufferGeometry {

	/**
	 * Constructs a new lathe geometry.
	 *
	 * @param {Array<Vector2|Vector3>} [points] - An array of points in 2D space. The x-coordinate of each point
	 * must be greater than zero.
	 * @param {number} [segments=12] - The number of circumference segments to generate.
	 * @param {number} [phiStart=0] - The starting angle in radians.
	 * @param {number} [phiLength=Math.PI*2] - The radian (0 to 2PI) range of the lathed section 2PI is a
	 * closed lathe, less than 2PI is a portion.
	 */
	constructor( points = [ new Vector2( 0, - 0.5 ), new Vector2( 0.5, 0 ), new Vector2( 0, 0.5 ) ], segments = 12, phiStart = 0, phiLength = Math.PI * 2 ) {

		super();

		this.type = 'LatheGeometry';

		/**
		 * Holds the constructor parameters that have been
		 * used to generate the geometry. Any modification
		 * after instantiation does not change the geometry.
		 *
		 * @type {Object}
		 */
		this.parameters = {
			points: points,
			segments: segments,
			phiStart: phiStart,
			phiLength: phiLength
		};

		segments = Math.floor( segments );

		// clamp phiLength so it's in range of [ 0, 2PI ]

		phiLength = clamp( phiLength, 0, Math.PI * 2 );

		// buffers

		const indices = [];
		const vertices = [];
		const uvs = [];
		const initNormals = [];
		const normals = [];

		// helper variables

		const inverseSegments = 1.0 / segments;
		const vertex = new Vector3();
		const uv = new Vector2();
		const normal = new Vector3();
		const curNormal = new Vector3();
		const prevNormal = new Vector3();
		let dx = 0;
		let dy = 0;

		// pre-compute normals for initial "meridian"

		for ( let j = 0; j <= ( points.length - 1 ); j ++ ) {

			switch ( j ) {

				case 0:				// special handling for 1st vertex on path

					dx = points[ j + 1 ].x - points[ j ].x;
					dy = points[ j + 1 ].y - points[ j ].y;

					normal.x = dy * 1.0;
					normal.y = - dx;
					normal.z = dy * 0.0;

					prevNormal.copy( normal );

					normal.normalize();

					initNormals.push( normal.x, normal.y, normal.z );

					break;

				case ( points.length - 1 ):	// special handling for last Vertex on path

					initNormals.push( prevNormal.x, prevNormal.y, prevNormal.z );

					break;

				default:			// default handling for all vertices in between

					dx = points[ j + 1 ].x - points[ j ].x;
					dy = points[ j + 1 ].y - points[ j ].y;

					normal.x = dy * 1.0;
					normal.y = - dx;
					normal.z = dy * 0.0;

					curNormal.copy( normal );

					normal.x += prevNormal.x;
					normal.y += prevNormal.y;
					normal.z += prevNormal.z;

					normal.normalize();

					initNormals.push( normal.x, normal.y, normal.z );

					prevNormal.copy( curNormal );

			}

		}

		// generate vertices, uvs and normals

		for ( let i = 0; i <= segments; i ++ ) {

			const phi = phiStart + i * inverseSegments * phiLength;

			const sin = Math.sin( phi );
			const cos = Math.cos( phi );

			for ( let j = 0; j <= ( points.length - 1 ); j ++ ) {

				// vertex

				vertex.x = points[ j ].x * sin;
				vertex.y = points[ j ].y;
				vertex.z = points[ j ].x * cos;

				vertices.push( vertex.x, vertex.y, vertex.z );

				// uv

				uv.x = i / segments;
				uv.y = j / ( points.length - 1 );

				uvs.push( uv.x, uv.y );

				// normal

				const x = initNormals[ 3 * j + 0 ] * sin;
				const y = initNormals[ 3 * j + 1 ];
				const z = initNormals[ 3 * j + 0 ] * cos;

				normals.push( x, y, z );

			}

		}

		// indices

		for ( let i = 0; i < segments; i ++ ) {

			for ( let j = 0; j < ( points.length - 1 ); j ++ ) {

				const base = j + i * points.length;

				const a = base;
				const b = base + points.length;
				const c = base + points.length + 1;
				const d = base + 1;

				// faces

				indices.push( a, b, d );
				indices.push( c, d, b );

			}

		}

		// build geometry

		this.setIndex( indices );
		this.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
		this.setAttribute( 'uv', new Float32BufferAttribute( uvs, 2 ) );
		this.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );

	}

	copy( source ) {

		super.copy( source );

		this.parameters = Object.assign( {}, source.parameters );

		return this;

	}

	/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @return {LatheGeometry} A new instance.
	 */
	static fromJSON( data ) {

		return new LatheGeometry( data.points, data.segments, data.phiStart, data.phiLength );

	}

}
```
</details>

#### Methods

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source );

		this.parameters = Object.assign( {}, source.parameters );

		return this;

	}
```
</details>

##### `fromJSON(data: any): LatheGeometry`

<details><summary>Code</summary>

```ts
static fromJSON( data ) {

		return new LatheGeometry( data.points, data.segments, data.phiStart, data.phiLength );

	}
```
</details>


---