[⬅️ Back to Table of Contents](../../index.md)

# 📄 `CapsuleGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 29 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/geometries/CapsuleGeometry.js`**

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
| `halfHeight` | `number` | let/var | `height / 2` | ✗ |
| `capArcLength` | `number` | let/var | `( Math.PI / 2 ) * radius` | ✗ |
| `cylinderPartLength` | `number` | let/var | `height` | ✗ |
| `totalArcLength` | `number` | let/var | `2 * capArcLength + cylinderPartLength` | ✗ |
| `numVerticalSegments` | `number` | let/var | `capSegments * 2 + heightSegments` | ✗ |
| `verticesPerRow` | `number` | let/var | `radialSegments + 1` | ✗ |
| `normal` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `vertex` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `currentArcLength` | `number` | let/var | `0` | ✗ |
| `profileY` | `number` | let/var | `0` | ✗ |
| `profileRadius` | `number` | let/var | `0` | ✗ |
| `normalYComponent` | `number` | let/var | `0` | ✗ |
| `segmentProgress` | `number` | let/var | `iy / capSegments` | ✗ |
| `angle` | `number` | let/var | `( segmentProgress * Math.PI ) / 2` | ✗ |
| `segmentProgress` | `number` | let/var | `( iy - capSegments ) / heightSegments` | ✗ |
| `segmentProgress` | `number` | let/var | `( iy - capSegments - heightSegments ) / capSegments` | ✗ |
| `angle` | `number` | let/var | `( segmentProgress * Math.PI ) / 2` | ✗ |
| `uOffset` | `number` | let/var | `0` | ✗ |
| `u` | `number` | let/var | `ix / radialSegments` | ✗ |
| `theta` | `number` | let/var | `u * Math.PI * 2` | ✗ |
| `prevIndexRow` | `number` | let/var | `( iy - 1 ) * verticesPerRow` | ✗ |
| `i1` | `number` | let/var | `prevIndexRow + ix` | ✗ |
| `i2` | `number` | let/var | `prevIndexRow + ix + 1` | ✗ |
| `i3` | `number` | let/var | `iy * verticesPerRow + ix` | ✗ |
| `i4` | `number` | let/var | `iy * verticesPerRow + ix + 1` | ✗ |


---

## Functions

### `CapsuleGeometry.copy(source: any): this`

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

### `CapsuleGeometry.fromJSON(data: any): CapsuleGeometry`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @return {CapsuleGeometry} A new instance.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `CapsuleGeometry`

<details><summary>Code</summary>

```typescript
static fromJSON( data ) {

		return new CapsuleGeometry( data.radius, data.height, data.capSegments, data.radialSegments, data.heightSegments );

	}
```
</details>


---

## Classes

### `CapsuleGeometry`

<details><summary>Class Code</summary>

```ts
class CapsuleGeometry extends BufferGeometry {

	/**
	 * Constructs a new capsule geometry.
	 *
	 * @param {number} [radius=1] - Radius of the capsule.
	 * @param {number} [height=1] - Height of the middle section.
	 * @param {number} [capSegments=4] - Number of curve segments used to build each cap.
	 * @param {number} [radialSegments=8] - Number of segmented faces around the circumference of the capsule. Must be an integer >= 3.
	 * @param {number} [heightSegments=1] - Number of rows of faces along the height of the middle section. Must be an integer >= 1.
	 */
	constructor( radius = 1, height = 1, capSegments = 4, radialSegments = 8, heightSegments = 1 ) {

		super();

		this.type = 'CapsuleGeometry';

		/**
		 * Holds the constructor parameters that have been
		 * used to generate the geometry. Any modification
		 * after instantiation does not change the geometry.
		 *
		 * @type {Object}
		 */
		this.parameters = {
			radius: radius,
			height: height,
			capSegments: capSegments,
			radialSegments: radialSegments,
			heightSegments: heightSegments,
		};

		height = Math.max( 0, height );
		capSegments = Math.max( 1, Math.floor( capSegments ) );
		radialSegments = Math.max( 3, Math.floor( radialSegments ) );
		heightSegments = Math.max( 1, Math.floor( heightSegments ) );

		// buffers

		const indices = [];
		const vertices = [];
		const normals = [];
		const uvs = [];

		// helper variables

		const halfHeight = height / 2;
		const capArcLength = ( Math.PI / 2 ) * radius;
		const cylinderPartLength = height;
		const totalArcLength = 2 * capArcLength + cylinderPartLength;

		const numVerticalSegments = capSegments * 2 + heightSegments;
		const verticesPerRow = radialSegments + 1;

		const normal = new Vector3();
		const vertex = new Vector3();

		// generate vertices, normals, and uvs

		for ( let iy = 0; iy <= numVerticalSegments; iy ++ ) {

			let currentArcLength = 0;
			let profileY = 0;
			let profileRadius = 0;
			let normalYComponent = 0;

			if ( iy <= capSegments ) {

				// bottom cap
				const segmentProgress = iy / capSegments;
				const angle = ( segmentProgress * Math.PI ) / 2;
				profileY = - halfHeight - radius * Math.cos( angle );
				profileRadius = radius * Math.sin( angle );
				normalYComponent = - radius * Math.cos( angle );
				currentArcLength = segmentProgress * capArcLength;

			} else if ( iy <= capSegments + heightSegments ) {

				// middle section
				const segmentProgress = ( iy - capSegments ) / heightSegments;
				profileY = - halfHeight + segmentProgress * height;
				profileRadius = radius;
				normalYComponent = 0;
				currentArcLength = capArcLength + segmentProgress * cylinderPartLength;

			} else {

				// top cap
				const segmentProgress =
					( iy - capSegments - heightSegments ) / capSegments;
				const angle = ( segmentProgress * Math.PI ) / 2;
				profileY = halfHeight + radius * Math.sin( angle );
				profileRadius = radius * Math.cos( angle );
				normalYComponent = radius * Math.sin( angle );
				currentArcLength =
					capArcLength + cylinderPartLength + segmentProgress * capArcLength;

			}

			const v = Math.max( 0, Math.min( 1, currentArcLength / totalArcLength ) );


			// special case for the poles

			let uOffset = 0;

			if ( iy === 0 ) {

				uOffset = 0.5 / radialSegments;

			} else if ( iy === numVerticalSegments ) {

				uOffset = - 0.5 / radialSegments;

			}

			for ( let ix = 0; ix <= radialSegments; ix ++ ) {

				const u = ix / radialSegments;
				const theta = u * Math.PI * 2;

				const sinTheta = Math.sin( theta );
				const cosTheta = Math.cos( theta );

				// vertex

				vertex.x = - profileRadius * cosTheta;
				vertex.y = profileY;
				vertex.z = profileRadius * sinTheta;
				vertices.push( vertex.x, vertex.y, vertex.z );

				// normal

				normal.set(
					- profileRadius * cosTheta,
					normalYComponent,
					profileRadius * sinTheta
				);
				normal.normalize();
				normals.push( normal.x, normal.y, normal.z );

				// uv

				uvs.push( u + uOffset, v );

			}

			if ( iy > 0 ) {

				const prevIndexRow = ( iy - 1 ) * verticesPerRow;
				for ( let ix = 0; ix < radialSegments; ix ++ ) {

					const i1 = prevIndexRow + ix;
					const i2 = prevIndexRow + ix + 1;
					const i3 = iy * verticesPerRow + ix;
					const i4 = iy * verticesPerRow + ix + 1;

					indices.push( i1, i2, i3 );
					indices.push( i2, i4, i3 );

				}

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
	 * @return {CapsuleGeometry} A new instance.
	 */
	static fromJSON( data ) {

		return new CapsuleGeometry( data.radius, data.height, data.capSegments, data.radialSegments, data.heightSegments );

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

##### `fromJSON(data: any): CapsuleGeometry`

<details><summary>Code</summary>

```ts
static fromJSON( data ) {

		return new CapsuleGeometry( data.radius, data.height, data.capSegments, data.radialSegments, data.heightSegments );

	}
```
</details>


---