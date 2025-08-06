[⬅️ Back to Table of Contents](../../index.md)

# 📄 `TorusKnotGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 20 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/geometries/TorusKnotGeometry.js`**

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
| `vertex` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `normal` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `P1` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `P2` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `B` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `T` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `N` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `u` | `number` | let/var | `i / tubularSegments * p * Math.PI * 2` | ✗ |
| `v` | `number` | let/var | `j / radialSegments * Math.PI * 2` | ✗ |
| `cx` | `number` | let/var | `- tube * Math.cos( v )` | ✗ |
| `cy` | `number` | let/var | `tube * Math.sin( v )` | ✗ |
| `a` | `number` | let/var | `( radialSegments + 1 ) * ( j - 1 ) + ( i - 1 )` | ✗ |
| `b` | `number` | let/var | `( radialSegments + 1 ) * j + ( i - 1 )` | ✗ |
| `c` | `number` | let/var | `( radialSegments + 1 ) * j + i` | ✗ |
| `d` | `number` | let/var | `( radialSegments + 1 ) * ( j - 1 ) + i` | ✗ |
| `quOverP` | `number` | let/var | `q / p * u` | ✗ |


---

## Functions

### `TorusKnotGeometry.copy(source: any): this`

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

### `TorusKnotGeometry.fromJSON(data: any): TorusKnotGeometry`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @return {TorusKnotGeometry} A new instance.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `TorusKnotGeometry`

<details><summary>Code</summary>

```typescript
static fromJSON( data ) {

		return new TorusKnotGeometry( data.radius, data.tube, data.tubularSegments, data.radialSegments, data.p, data.q );

	}
```
</details>

### `calculatePositionOnCurve(u: any, p: any, q: any, radius: any, position: any): void`

**Parameters:**

- **`u`** `any`
- **`p`** `any`
- **`q`** `any`
- **`radius`** `any`
- **`position`** `any`

**Returns:** `void`

**Calls:**

- `Math.cos`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function calculatePositionOnCurve( u, p, q, radius, position ) {

			const cu = Math.cos( u );
			const su = Math.sin( u );
			const quOverP = q / p * u;
			const cs = Math.cos( quOverP );

			position.x = radius * ( 2 + cs ) * 0.5 * cu;
			position.y = radius * ( 2 + cs ) * su * 0.5;
			position.z = radius * Math.sin( quOverP ) * 0.5;

		}
```
</details>


---

## Classes

### `TorusKnotGeometry`

<details><summary>Class Code</summary>

```ts
class TorusKnotGeometry extends BufferGeometry {

	/**
	 * Constructs a new torus knot geometry.
	 *
	 * @param {number} [radius=1] - Radius of the torus knot.
	 * @param {number} [tube=0.4] - Radius of the tube.
	 * @param {number} [tubularSegments=64] - The number of tubular segments.
	 * @param {number} [radialSegments=8] - The number of radial segments.
	 * @param {number} [p=2] - This value determines, how many times the geometry winds around its axis of rotational symmetry.
	 * @param {number} [q=3] - This value determines, how many times the geometry winds around a circle in the interior of the torus.
	 */
	constructor( radius = 1, tube = 0.4, tubularSegments = 64, radialSegments = 8, p = 2, q = 3 ) {

		super();

		this.type = 'TorusKnotGeometry';

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
			tubularSegments: tubularSegments,
			radialSegments: radialSegments,
			p: p,
			q: q
		};

		tubularSegments = Math.floor( tubularSegments );
		radialSegments = Math.floor( radialSegments );

		// buffers

		const indices = [];
		const vertices = [];
		const normals = [];
		const uvs = [];

		// helper variables

		const vertex = new Vector3();
		const normal = new Vector3();

		const P1 = new Vector3();
		const P2 = new Vector3();

		const B = new Vector3();
		const T = new Vector3();
		const N = new Vector3();

		// generate vertices, normals and uvs

		for ( let i = 0; i <= tubularSegments; ++ i ) {

			// the radian "u" is used to calculate the position on the torus curve of the current tubular segment

			const u = i / tubularSegments * p * Math.PI * 2;

			// now we calculate two points. P1 is our current position on the curve, P2 is a little farther ahead.
			// these points are used to create a special "coordinate space", which is necessary to calculate the correct vertex positions

			calculatePositionOnCurve( u, p, q, radius, P1 );
			calculatePositionOnCurve( u + 0.01, p, q, radius, P2 );

			// calculate orthonormal basis

			T.subVectors( P2, P1 );
			N.addVectors( P2, P1 );
			B.crossVectors( T, N );
			N.crossVectors( B, T );

			// normalize B, N. T can be ignored, we don't use it

			B.normalize();
			N.normalize();

			for ( let j = 0; j <= radialSegments; ++ j ) {

				// now calculate the vertices. they are nothing more than an extrusion of the torus curve.
				// because we extrude a shape in the xy-plane, there is no need to calculate a z-value.

				const v = j / radialSegments * Math.PI * 2;
				const cx = - tube * Math.cos( v );
				const cy = tube * Math.sin( v );

				// now calculate the final vertex position.
				// first we orient the extrusion with our basis vectors, then we add it to the current position on the curve

				vertex.x = P1.x + ( cx * N.x + cy * B.x );
				vertex.y = P1.y + ( cx * N.y + cy * B.y );
				vertex.z = P1.z + ( cx * N.z + cy * B.z );

				vertices.push( vertex.x, vertex.y, vertex.z );

				// normal (P1 is always the center/origin of the extrusion, thus we can use it to calculate the normal)

				normal.subVectors( vertex, P1 ).normalize();

				normals.push( normal.x, normal.y, normal.z );

				// uv

				uvs.push( i / tubularSegments );
				uvs.push( j / radialSegments );

			}

		}

		// generate indices

		for ( let j = 1; j <= tubularSegments; j ++ ) {

			for ( let i = 1; i <= radialSegments; i ++ ) {

				// indices

				const a = ( radialSegments + 1 ) * ( j - 1 ) + ( i - 1 );
				const b = ( radialSegments + 1 ) * j + ( i - 1 );
				const c = ( radialSegments + 1 ) * j + i;
				const d = ( radialSegments + 1 ) * ( j - 1 ) + i;

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

		// this function calculates the current position on the torus curve

		function calculatePositionOnCurve( u, p, q, radius, position ) {

			const cu = Math.cos( u );
			const su = Math.sin( u );
			const quOverP = q / p * u;
			const cs = Math.cos( quOverP );

			position.x = radius * ( 2 + cs ) * 0.5 * cu;
			position.y = radius * ( 2 + cs ) * su * 0.5;
			position.z = radius * Math.sin( quOverP ) * 0.5;

		}

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
	 * @return {TorusKnotGeometry} A new instance.
	 */
	static fromJSON( data ) {

		return new TorusKnotGeometry( data.radius, data.tube, data.tubularSegments, data.radialSegments, data.p, data.q );

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

##### `fromJSON(data: any): TorusKnotGeometry`

<details><summary>Code</summary>

```ts
static fromJSON( data ) {

		return new TorusKnotGeometry( data.radius, data.tube, data.tubularSegments, data.radialSegments, data.p, data.q );

	}
```
</details>


---