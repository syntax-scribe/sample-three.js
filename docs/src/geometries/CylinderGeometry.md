[⬅️ Back to Table of Contents](../../index.md)

# 📄 `CylinderGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 33 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/geometries/CylinderGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `../core/BufferGeometry.js` |
| `Float32BufferAttribute` | `../core/BufferAttribute.js` |
| `Vector3` | `../math/Vector3.js` |
| `Vector2` | `../math/Vector2.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `uvs` | `any[]` | let/var | `[]` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `indexArray` | `any[]` | let/var | `[]` | ✗ |
| `halfHeight` | `number` | let/var | `height / 2` | ✗ |
| `groupStart` | `number` | let/var | `0` | ✗ |
| `normal` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `vertex` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `groupCount` | `number` | let/var | `0` | ✗ |
| `slope` | `number` | let/var | `( radiusBottom - radiusTop ) / height` | ✗ |
| `indexRow` | `any[]` | let/var | `[]` | ✗ |
| `v` | `number` | let/var | `y / heightSegments` | ✗ |
| `radius` | `number` | let/var | `v * ( radiusBottom - radiusTop ) + radiusTop` | ✗ |
| `u` | `number` | let/var | `x / radialSegments` | ✗ |
| `theta` | `number` | let/var | `u * thetaLength + thetaStart` | ✗ |
| `a` | `any` | let/var | `indexArray[ y ][ x ]` | ✗ |
| `b` | `any` | let/var | `indexArray[ y + 1 ][ x ]` | ✗ |
| `c` | `any` | let/var | `indexArray[ y + 1 ][ x + 1 ]` | ✗ |
| `d` | `any` | let/var | `indexArray[ y ][ x + 1 ]` | ✗ |
| `centerIndexStart` | `number` | let/var | `index` | ✗ |
| `uv` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `vertex` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `groupCount` | `number` | let/var | `0` | ✗ |
| `radius` | `number` | let/var | `( top === true ) ? radiusTop : radiusBottom` | ✗ |
| `sign` | `1 \| -1` | let/var | `( top === true ) ? 1 : - 1` | ✗ |
| `centerIndexEnd` | `number` | let/var | `index` | ✗ |
| `u` | `number` | let/var | `x / radialSegments` | ✗ |
| `theta` | `number` | let/var | `u * thetaLength + thetaStart` | ✗ |
| `c` | `number` | let/var | `centerIndexStart + x` | ✗ |
| `i` | `number` | let/var | `centerIndexEnd + x` | ✗ |


---

## Functions

### `CylinderGeometry.copy(source: any): this`

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

### `CylinderGeometry.fromJSON(data: any): CylinderGeometry`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @return {CylinderGeometry} A new instance.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `CylinderGeometry`

<details><summary>Code</summary>

```typescript
static fromJSON( data ) {

		return new CylinderGeometry( data.radiusTop, data.radiusBottom, data.height, data.radialSegments, data.heightSegments, data.openEnded, data.thetaStart, data.thetaLength );

	}
```
</details>

### `generateTorso(): void`

**Returns:** `void`

**Calls:**

- `Math.sin`
- `Math.cos`
- `vertices.push`
- `normal.set( sinTheta, slope, cosTheta ).normalize`
- `normals.push`
- `uvs.push`
- `indexRow.push`
- `indexArray.push`
- `indices.push`
- `scope.addGroup`

**Internal Comments:**
```
// this will be used to calculate the normal (x2)
// generate vertices, normals and uvs
// calculate the radius of the current row (x2)
// vertex (x4)
// normal (x6)
// uv (x4)
// save index of vertex in respective row (x4)
// now save vertices of the row in our index array (x4)
// generate indices
// we use the index array to access the correct indices (x2)
// faces
// add a group to the geometry. this will ensure multi material support (x4)
// calculate new start value for groups (x3)
```

<details><summary>Code</summary>

```typescript
function generateTorso() {

			const normal = new Vector3();
			const vertex = new Vector3();

			let groupCount = 0;

			// this will be used to calculate the normal
			const slope = ( radiusBottom - radiusTop ) / height;

			// generate vertices, normals and uvs

			for ( let y = 0; y <= heightSegments; y ++ ) {

				const indexRow = [];

				const v = y / heightSegments;

				// calculate the radius of the current row

				const radius = v * ( radiusBottom - radiusTop ) + radiusTop;

				for ( let x = 0; x <= radialSegments; x ++ ) {

					const u = x / radialSegments;

					const theta = u * thetaLength + thetaStart;

					const sinTheta = Math.sin( theta );
					const cosTheta = Math.cos( theta );

					// vertex

					vertex.x = radius * sinTheta;
					vertex.y = - v * height + halfHeight;
					vertex.z = radius * cosTheta;
					vertices.push( vertex.x, vertex.y, vertex.z );

					// normal

					normal.set( sinTheta, slope, cosTheta ).normalize();
					normals.push( normal.x, normal.y, normal.z );

					// uv

					uvs.push( u, 1 - v );

					// save index of vertex in respective row

					indexRow.push( index ++ );

				}

				// now save vertices of the row in our index array

				indexArray.push( indexRow );

			}

			// generate indices

			for ( let x = 0; x < radialSegments; x ++ ) {

				for ( let y = 0; y < heightSegments; y ++ ) {

					// we use the index array to access the correct indices

					const a = indexArray[ y ][ x ];
					const b = indexArray[ y + 1 ][ x ];
					const c = indexArray[ y + 1 ][ x + 1 ];
					const d = indexArray[ y ][ x + 1 ];

					// faces

					if ( radiusTop > 0 || y !== 0 ) {

						indices.push( a, b, d );
						groupCount += 3;

					}

					if ( radiusBottom > 0 || y !== heightSegments - 1 ) {

						indices.push( b, c, d );
						groupCount += 3;

					}

				}

			}

			// add a group to the geometry. this will ensure multi material support

			scope.addGroup( groupStart, groupCount, 0 );

			// calculate new start value for groups

			groupStart += groupCount;

		}
```
</details>

### `generateCap(top: any): void`

**Parameters:**

- **`top`** `any`

**Returns:** `void`

**Calls:**

- `vertices.push`
- `normals.push`
- `uvs.push`
- `Math.cos`
- `Math.sin`
- `indices.push`
- `scope.addGroup`

**Internal Comments:**
```
// save the index of the first center vertex (x2)
// first we generate the center vertex data of the cap.
// because the geometry needs one set of uvs per face,
// we must generate a center vertex per face/segment
// vertex (x8)
// normal (x8)
// uv (x8)
// increase index (x6)
// save the index of the last center vertex (x2)
// now we generate the surrounding vertices, normals and uvs
// generate indices
// face top (x4)
// face bottom (x4)
// add a group to the geometry. this will ensure multi material support (x4)
// calculate new start value for groups (x3)
```

<details><summary>Code</summary>

```typescript
function generateCap( top ) {

			// save the index of the first center vertex
			const centerIndexStart = index;

			const uv = new Vector2();
			const vertex = new Vector3();

			let groupCount = 0;

			const radius = ( top === true ) ? radiusTop : radiusBottom;
			const sign = ( top === true ) ? 1 : - 1;

			// first we generate the center vertex data of the cap.
			// because the geometry needs one set of uvs per face,
			// we must generate a center vertex per face/segment

			for ( let x = 1; x <= radialSegments; x ++ ) {

				// vertex

				vertices.push( 0, halfHeight * sign, 0 );

				// normal

				normals.push( 0, sign, 0 );

				// uv

				uvs.push( 0.5, 0.5 );

				// increase index

				index ++;

			}

			// save the index of the last center vertex
			const centerIndexEnd = index;

			// now we generate the surrounding vertices, normals and uvs

			for ( let x = 0; x <= radialSegments; x ++ ) {

				const u = x / radialSegments;
				const theta = u * thetaLength + thetaStart;

				const cosTheta = Math.cos( theta );
				const sinTheta = Math.sin( theta );

				// vertex

				vertex.x = radius * sinTheta;
				vertex.y = halfHeight * sign;
				vertex.z = radius * cosTheta;
				vertices.push( vertex.x, vertex.y, vertex.z );

				// normal

				normals.push( 0, sign, 0 );

				// uv

				uv.x = ( cosTheta * 0.5 ) + 0.5;
				uv.y = ( sinTheta * 0.5 * sign ) + 0.5;
				uvs.push( uv.x, uv.y );

				// increase index

				index ++;

			}

			// generate indices

			for ( let x = 0; x < radialSegments; x ++ ) {

				const c = centerIndexStart + x;
				const i = centerIndexEnd + x;

				if ( top === true ) {

					// face top

					indices.push( i, i + 1, c );

				} else {

					// face bottom

					indices.push( i + 1, i, c );

				}

				groupCount += 3;

			}

			// add a group to the geometry. this will ensure multi material support

			scope.addGroup( groupStart, groupCount, top === true ? 1 : 2 );

			// calculate new start value for groups

			groupStart += groupCount;

		}
```
</details>


---

## Classes

### `CylinderGeometry`

<details><summary>Class Code</summary>

```ts
class CylinderGeometry extends BufferGeometry {

	/**
	 * Constructs a new cylinder geometry.
	 *
	 * @param {number} [radiusTop=1] - Radius of the cylinder at the top.
	 * @param {number} [radiusBottom=1] - Radius of the cylinder at the bottom.
	 * @param {number} [height=1] - Height of the cylinder.
	 * @param {number} [radialSegments=32] - Number of segmented faces around the circumference of the cylinder.
	 * @param {number} [heightSegments=1] - Number of rows of faces along the height of the cylinder.
	 * @param {boolean} [openEnded=false] - Whether the base of the cylinder is open or capped.
	 * @param {number} [thetaStart=0] - Start angle for first segment, in radians.
	 * @param {number} [thetaLength=Math.PI*2] - The central angle, often called theta, of the circular sector, in radians.
	 * The default value results in a complete cylinder.
	 */
	constructor( radiusTop = 1, radiusBottom = 1, height = 1, radialSegments = 32, heightSegments = 1, openEnded = false, thetaStart = 0, thetaLength = Math.PI * 2 ) {

		super();

		this.type = 'CylinderGeometry';

		/**
		 * Holds the constructor parameters that have been
		 * used to generate the geometry. Any modification
		 * after instantiation does not change the geometry.
		 *
		 * @type {Object}
		 */
		this.parameters = {
			radiusTop: radiusTop,
			radiusBottom: radiusBottom,
			height: height,
			radialSegments: radialSegments,
			heightSegments: heightSegments,
			openEnded: openEnded,
			thetaStart: thetaStart,
			thetaLength: thetaLength
		};

		const scope = this;

		radialSegments = Math.floor( radialSegments );
		heightSegments = Math.floor( heightSegments );

		// buffers

		const indices = [];
		const vertices = [];
		const normals = [];
		const uvs = [];

		// helper variables

		let index = 0;
		const indexArray = [];
		const halfHeight = height / 2;
		let groupStart = 0;

		// generate geometry

		generateTorso();

		if ( openEnded === false ) {

			if ( radiusTop > 0 ) generateCap( true );
			if ( radiusBottom > 0 ) generateCap( false );

		}

		// build geometry

		this.setIndex( indices );
		this.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
		this.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );
		this.setAttribute( 'uv', new Float32BufferAttribute( uvs, 2 ) );

		function generateTorso() {

			const normal = new Vector3();
			const vertex = new Vector3();

			let groupCount = 0;

			// this will be used to calculate the normal
			const slope = ( radiusBottom - radiusTop ) / height;

			// generate vertices, normals and uvs

			for ( let y = 0; y <= heightSegments; y ++ ) {

				const indexRow = [];

				const v = y / heightSegments;

				// calculate the radius of the current row

				const radius = v * ( radiusBottom - radiusTop ) + radiusTop;

				for ( let x = 0; x <= radialSegments; x ++ ) {

					const u = x / radialSegments;

					const theta = u * thetaLength + thetaStart;

					const sinTheta = Math.sin( theta );
					const cosTheta = Math.cos( theta );

					// vertex

					vertex.x = radius * sinTheta;
					vertex.y = - v * height + halfHeight;
					vertex.z = radius * cosTheta;
					vertices.push( vertex.x, vertex.y, vertex.z );

					// normal

					normal.set( sinTheta, slope, cosTheta ).normalize();
					normals.push( normal.x, normal.y, normal.z );

					// uv

					uvs.push( u, 1 - v );

					// save index of vertex in respective row

					indexRow.push( index ++ );

				}

				// now save vertices of the row in our index array

				indexArray.push( indexRow );

			}

			// generate indices

			for ( let x = 0; x < radialSegments; x ++ ) {

				for ( let y = 0; y < heightSegments; y ++ ) {

					// we use the index array to access the correct indices

					const a = indexArray[ y ][ x ];
					const b = indexArray[ y + 1 ][ x ];
					const c = indexArray[ y + 1 ][ x + 1 ];
					const d = indexArray[ y ][ x + 1 ];

					// faces

					if ( radiusTop > 0 || y !== 0 ) {

						indices.push( a, b, d );
						groupCount += 3;

					}

					if ( radiusBottom > 0 || y !== heightSegments - 1 ) {

						indices.push( b, c, d );
						groupCount += 3;

					}

				}

			}

			// add a group to the geometry. this will ensure multi material support

			scope.addGroup( groupStart, groupCount, 0 );

			// calculate new start value for groups

			groupStart += groupCount;

		}

		function generateCap( top ) {

			// save the index of the first center vertex
			const centerIndexStart = index;

			const uv = new Vector2();
			const vertex = new Vector3();

			let groupCount = 0;

			const radius = ( top === true ) ? radiusTop : radiusBottom;
			const sign = ( top === true ) ? 1 : - 1;

			// first we generate the center vertex data of the cap.
			// because the geometry needs one set of uvs per face,
			// we must generate a center vertex per face/segment

			for ( let x = 1; x <= radialSegments; x ++ ) {

				// vertex

				vertices.push( 0, halfHeight * sign, 0 );

				// normal

				normals.push( 0, sign, 0 );

				// uv

				uvs.push( 0.5, 0.5 );

				// increase index

				index ++;

			}

			// save the index of the last center vertex
			const centerIndexEnd = index;

			// now we generate the surrounding vertices, normals and uvs

			for ( let x = 0; x <= radialSegments; x ++ ) {

				const u = x / radialSegments;
				const theta = u * thetaLength + thetaStart;

				const cosTheta = Math.cos( theta );
				const sinTheta = Math.sin( theta );

				// vertex

				vertex.x = radius * sinTheta;
				vertex.y = halfHeight * sign;
				vertex.z = radius * cosTheta;
				vertices.push( vertex.x, vertex.y, vertex.z );

				// normal

				normals.push( 0, sign, 0 );

				// uv

				uv.x = ( cosTheta * 0.5 ) + 0.5;
				uv.y = ( sinTheta * 0.5 * sign ) + 0.5;
				uvs.push( uv.x, uv.y );

				// increase index

				index ++;

			}

			// generate indices

			for ( let x = 0; x < radialSegments; x ++ ) {

				const c = centerIndexStart + x;
				const i = centerIndexEnd + x;

				if ( top === true ) {

					// face top

					indices.push( i, i + 1, c );

				} else {

					// face bottom

					indices.push( i + 1, i, c );

				}

				groupCount += 3;

			}

			// add a group to the geometry. this will ensure multi material support

			scope.addGroup( groupStart, groupCount, top === true ? 1 : 2 );

			// calculate new start value for groups

			groupStart += groupCount;

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
	 * @return {CylinderGeometry} A new instance.
	 */
	static fromJSON( data ) {

		return new CylinderGeometry( data.radiusTop, data.radiusBottom, data.height, data.radialSegments, data.heightSegments, data.openEnded, data.thetaStart, data.thetaLength );

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

##### `fromJSON(data: any): CylinderGeometry`

<details><summary>Code</summary>

```ts
static fromJSON( data ) {

		return new CylinderGeometry( data.radiusTop, data.radiusBottom, data.height, data.radialSegments, data.heightSegments, data.openEnded, data.thetaStart, data.thetaLength );

	}
```
</details>


---