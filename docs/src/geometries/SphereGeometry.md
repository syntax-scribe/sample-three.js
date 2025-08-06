[⬅️ Back to Table of Contents](../../index.md)

# 📄 `SphereGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 16 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/geometries/SphereGeometry.js`**

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
| `index` | `number` | let/var | `0` | ✗ |
| `grid` | `any[]` | let/var | `[]` | ✗ |
| `vertex` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `normal` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `uvs` | `any[]` | let/var | `[]` | ✗ |
| `verticesRow` | `any[]` | let/var | `[]` | ✗ |
| `v` | `number` | let/var | `iy / heightSegments` | ✗ |
| `uOffset` | `number` | let/var | `0` | ✗ |
| `u` | `number` | let/var | `ix / widthSegments` | ✗ |
| `a` | `number` | let/var | `grid[ iy ][ ix + 1 ]` | ✗ |
| `b` | `number` | let/var | `grid[ iy ][ ix ]` | ✗ |
| `c` | `number` | let/var | `grid[ iy + 1 ][ ix ]` | ✗ |
| `d` | `number` | let/var | `grid[ iy + 1 ][ ix + 1 ]` | ✗ |


---

## Functions

### `SphereGeometry.copy(source: any): this`

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

### `SphereGeometry.fromJSON(data: any): SphereGeometry`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @return {SphereGeometry} A new instance.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `SphereGeometry`

<details><summary>Code</summary>

```typescript
static fromJSON( data ) {

		return new SphereGeometry( data.radius, data.widthSegments, data.heightSegments, data.phiStart, data.phiLength, data.thetaStart, data.thetaLength );

	}
```
</details>


---

## Classes

### `SphereGeometry`

<details><summary>Class Code</summary>

```ts
class SphereGeometry extends BufferGeometry {

	/**
	 * Constructs a new sphere geometry.
	 *
	 * @param {number} [radius=1] - The sphere radius.
	 * @param {number} [widthSegments=32] - The number of horizontal segments. Minimum value is `3`.
	 * @param {number} [heightSegments=16] - The number of vertical segments. Minimum value is `2`.
	 * @param {number} [phiStart=0] - The horizontal starting angle in radians.
	 * @param {number} [phiLength=Math.PI*2] - The horizontal sweep angle size.
	 * @param {number} [thetaStart=0] - The vertical starting angle in radians.
	 * @param {number} [thetaLength=Math.PI] - The vertical sweep angle size.
	 */
	constructor( radius = 1, widthSegments = 32, heightSegments = 16, phiStart = 0, phiLength = Math.PI * 2, thetaStart = 0, thetaLength = Math.PI ) {

		super();

		this.type = 'SphereGeometry';

		/**
		 * Holds the constructor parameters that have been
		 * used to generate the geometry. Any modification
		 * after instantiation does not change the geometry.
		 *
		 * @type {Object}
		 */
		this.parameters = {
			radius: radius,
			widthSegments: widthSegments,
			heightSegments: heightSegments,
			phiStart: phiStart,
			phiLength: phiLength,
			thetaStart: thetaStart,
			thetaLength: thetaLength
		};

		widthSegments = Math.max( 3, Math.floor( widthSegments ) );
		heightSegments = Math.max( 2, Math.floor( heightSegments ) );

		const thetaEnd = Math.min( thetaStart + thetaLength, Math.PI );

		let index = 0;
		const grid = [];

		const vertex = new Vector3();
		const normal = new Vector3();

		// buffers

		const indices = [];
		const vertices = [];
		const normals = [];
		const uvs = [];

		// generate vertices, normals and uvs

		for ( let iy = 0; iy <= heightSegments; iy ++ ) {

			const verticesRow = [];

			const v = iy / heightSegments;

			// special case for the poles

			let uOffset = 0;

			if ( iy === 0 && thetaStart === 0 ) {

				uOffset = 0.5 / widthSegments;

			} else if ( iy === heightSegments && thetaEnd === Math.PI ) {

				uOffset = - 0.5 / widthSegments;

			}

			for ( let ix = 0; ix <= widthSegments; ix ++ ) {

				const u = ix / widthSegments;

				// vertex

				vertex.x = - radius * Math.cos( phiStart + u * phiLength ) * Math.sin( thetaStart + v * thetaLength );
				vertex.y = radius * Math.cos( thetaStart + v * thetaLength );
				vertex.z = radius * Math.sin( phiStart + u * phiLength ) * Math.sin( thetaStart + v * thetaLength );

				vertices.push( vertex.x, vertex.y, vertex.z );

				// normal

				normal.copy( vertex ).normalize();
				normals.push( normal.x, normal.y, normal.z );

				// uv

				uvs.push( u + uOffset, 1 - v );

				verticesRow.push( index ++ );

			}

			grid.push( verticesRow );

		}

		// indices

		for ( let iy = 0; iy < heightSegments; iy ++ ) {

			for ( let ix = 0; ix < widthSegments; ix ++ ) {

				const a = grid[ iy ][ ix + 1 ];
				const b = grid[ iy ][ ix ];
				const c = grid[ iy + 1 ][ ix ];
				const d = grid[ iy + 1 ][ ix + 1 ];

				if ( iy !== 0 || thetaStart > 0 ) indices.push( a, b, d );
				if ( iy !== heightSegments - 1 || thetaEnd < Math.PI ) indices.push( b, c, d );

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
	 * @return {SphereGeometry} A new instance.
	 */
	static fromJSON( data ) {

		return new SphereGeometry( data.radius, data.widthSegments, data.heightSegments, data.phiStart, data.phiLength, data.thetaStart, data.thetaLength );

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

##### `fromJSON(data: any): SphereGeometry`

<details><summary>Code</summary>

```ts
static fromJSON( data ) {

		return new SphereGeometry( data.radius, data.widthSegments, data.heightSegments, data.phiStart, data.phiLength, data.thetaStart, data.thetaLength );

	}
```
</details>


---