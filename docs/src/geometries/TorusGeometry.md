[⬅️ Back to Table of Contents](../../index.md)

# 📄 `TorusGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 13 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/geometries/TorusGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `../core/BufferGeometry.js` |
| `Float32BufferAttribute` | `../core/BufferAttribute.js` |
| `Vector3` | `../math/Vector3.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `uvs` | `any[]` | let/var | `[]` | ✗ |
| `center` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `vertex` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `normal` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `u` | `number` | let/var | `i / tubularSegments * arc` | ✗ |
| `v` | `number` | let/var | `j / radialSegments * Math.PI * 2` | ✗ |
| `a` | `number` | let/var | `( tubularSegments + 1 ) * j + i - 1` | ✗ |
| `b` | `number` | let/var | `( tubularSegments + 1 ) * ( j - 1 ) + i - 1` | ✗ |
| `c` | `number` | let/var | `( tubularSegments + 1 ) * ( j - 1 ) + i` | ✗ |
| `d` | `number` | let/var | `( tubularSegments + 1 ) * j + i` | ✗ |


---

## Functions

### `TorusGeometry.copy(source: any): this`

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

### `TorusGeometry.fromJSON(data: any): TorusGeometry`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @return {TorusGeometry} A new instance.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `TorusGeometry`

<details><summary>Code</summary>

```typescript
static fromJSON( data ) {

		return new TorusGeometry( data.radius, data.tube, data.radialSegments, data.tubularSegments, data.arc );

	}
```
</details>


---

## Classes

### `TorusGeometry`

<details><summary>Class Code</summary>

```ts
class TorusGeometry extends BufferGeometry {

	/**
	 * Constructs a new torus geometry.
	 *
	 * @param {number} [radius=1] - Radius of the torus, from the center of the torus to the center of the tube.
	 * @param {number} [tube=0.4] - Radius of the tube. Must be smaller than `radius`.
	 * @param {number} [radialSegments=12] - The number of radial segments.
	 * @param {number} [tubularSegments=48] - The number of tubular segments.
	 * @param {number} [arc=Math.PI*2] - Central angle in radians.
	 */
	constructor( radius = 1, tube = 0.4, radialSegments = 12, tubularSegments = 48, arc = Math.PI * 2 ) {

		super();

		this.type = 'TorusGeometry';

		/**
		 * Holds the constructor parameters that have been
		 * used to generate the geometry. Any modification
		 * after instantiation does not change the geometry.
		 *
		 * @type {Object}
		 */
		this.parameters = {
			radius: radius,
			tube: tube,
			radialSegments: radialSegments,
			tubularSegments: tubularSegments,
			arc: arc
		};

		radialSegments = Math.floor( radialSegments );
		tubularSegments = Math.floor( tubularSegments );

		// buffers

		const indices = [];
		const vertices = [];
		const normals = [];
		const uvs = [];

		// helper variables

		const center = new Vector3();
		const vertex = new Vector3();
		const normal = new Vector3();

		// generate vertices, normals and uvs

		for ( let j = 0; j <= radialSegments; j ++ ) {

			for ( let i = 0; i <= tubularSegments; i ++ ) {

				const u = i / tubularSegments * arc;
				const v = j / radialSegments * Math.PI * 2;

				// vertex

				vertex.x = ( radius + tube * Math.cos( v ) ) * Math.cos( u );
				vertex.y = ( radius + tube * Math.cos( v ) ) * Math.sin( u );
				vertex.z = tube * Math.sin( v );

				vertices.push( vertex.x, vertex.y, vertex.z );

				// normal

				center.x = radius * Math.cos( u );
				center.y = radius * Math.sin( u );
				normal.subVectors( vertex, center ).normalize();

				normals.push( normal.x, normal.y, normal.z );

				// uv

				uvs.push( i / tubularSegments );
				uvs.push( j / radialSegments );

			}

		}

		// generate indices

		for ( let j = 1; j <= radialSegments; j ++ ) {

			for ( let i = 1; i <= tubularSegments; i ++ ) {

				// indices

				const a = ( tubularSegments + 1 ) * j + i - 1;
				const b = ( tubularSegments + 1 ) * ( j - 1 ) + i - 1;
				const c = ( tubularSegments + 1 ) * ( j - 1 ) + i;
				const d = ( tubularSegments + 1 ) * j + i;

				// faces

				indices.push( a, b, d );
				indices.push( b, c, d );

			}

		}

		// build geometry

		this.setIndex( indices );
		this.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
		this.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );
		this.setAttribute( 'uv', new Float32BufferAttribute( uvs, 2 ) );

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
	 * @return {TorusGeometry} A new instance.
	 */
	static fromJSON( data ) {

		return new TorusGeometry( data.radius, data.tube, data.radialSegments, data.tubularSegments, data.arc );

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

##### `fromJSON(data: any): TorusGeometry`

<details><summary>Code</summary>

```ts
static fromJSON( data ) {

		return new TorusGeometry( data.radius, data.tube, data.radialSegments, data.tubularSegments, data.arc );

	}
```
</details>


---