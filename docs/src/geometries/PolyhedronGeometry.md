[⬅️ Back to Table of Contents](../../index.md)

# 📄 `PolyhedronGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 13 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 23 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/geometries/PolyhedronGeometry.js`**

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
| `vertexBuffer` | `any[]` | let/var | `[]` | ✗ |
| `uvBuffer` | `any[]` | let/var | `[]` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `c` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `cols` | `any` | let/var | `detail + 1` | ✗ |
| `v` | `any[]` | let/var | `[]` | ✗ |
| `rows` | `number` | let/var | `cols - i` | ✗ |
| `vertex` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `vertex` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `u` | `number` | let/var | `azimuth( vertex ) / 2 / Math.PI + 0.5` | ✗ |
| `v` | `number` | let/var | `inclination( vertex ) / Math.PI + 0.5` | ✗ |
| `x0` | `any` | let/var | `uvBuffer[ i + 0 ]` | ✗ |
| `x1` | `any` | let/var | `uvBuffer[ i + 2 ]` | ✗ |
| `x2` | `any` | let/var | `uvBuffer[ i + 4 ]` | ✗ |
| `stride` | `number` | let/var | `index * 3` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `c` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `centroid` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `uvA` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `uvB` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `uvC` | `Vector2` | let/var | `new Vector2()` | ✗ |


---

## Functions

### `PolyhedronGeometry.copy(source: any): this`

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

### `PolyhedronGeometry.fromJSON(data: any): PolyhedronGeometry`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @return {PolyhedronGeometry} A new instance.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `PolyhedronGeometry`

<details><summary>Code</summary>

```typescript
static fromJSON( data ) {

		return new PolyhedronGeometry( data.vertices, data.indices, data.radius, data.details );

	}
```
</details>

### `subdivide(detail: any): void`

**Parameters:**

- **`detail`** `any`

**Returns:** `void`

**Calls:**

- `getVertexByIndex`
- `subdivideFace`

**Internal Comments:**
```
// iterate over all faces and apply a subdivision with the given detail value
// get the vertices of the face (x3)
// perform subdivision (x3)
```

<details><summary>Code</summary>

```typescript
function subdivide( detail ) {

			const a = new Vector3();
			const b = new Vector3();
			const c = new Vector3();

			// iterate over all faces and apply a subdivision with the given detail value

			for ( let i = 0; i < indices.length; i += 3 ) {

				// get the vertices of the face

				getVertexByIndex( indices[ i + 0 ], a );
				getVertexByIndex( indices[ i + 1 ], b );
				getVertexByIndex( indices[ i + 2 ], c );

				// perform subdivision

				subdivideFace( a, b, c, detail );

			}

		}
```
</details>

### `subdivideFace(a: any, b: any, c: any, detail: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`
- **`detail`** `any`

**Returns:** `void`

**Calls:**

- `a.clone().lerp`
- `b.clone().lerp`
- `aj.clone().lerp`
- `Math.floor`
- `pushVertex`

**Internal Comments:**
```
// we use this multidimensional array as a data structure for creating the subdivision (x2)
// construct all of the vertices for this subdivision
// construct all of the faces
```

<details><summary>Code</summary>

```typescript
function subdivideFace( a, b, c, detail ) {

			const cols = detail + 1;

			// we use this multidimensional array as a data structure for creating the subdivision

			const v = [];

			// construct all of the vertices for this subdivision

			for ( let i = 0; i <= cols; i ++ ) {

				v[ i ] = [];

				const aj = a.clone().lerp( c, i / cols );
				const bj = b.clone().lerp( c, i / cols );

				const rows = cols - i;

				for ( let j = 0; j <= rows; j ++ ) {

					if ( j === 0 && i === cols ) {

						v[ i ][ j ] = aj;

					} else {

						v[ i ][ j ] = aj.clone().lerp( bj, j / rows );

					}

				}

			}

			// construct all of the faces

			for ( let i = 0; i < cols; i ++ ) {

				for ( let j = 0; j < 2 * ( cols - i ) - 1; j ++ ) {

					const k = Math.floor( j / 2 );

					if ( j % 2 === 0 ) {

						pushVertex( v[ i ][ k + 1 ] );
						pushVertex( v[ i + 1 ][ k ] );
						pushVertex( v[ i ][ k ] );

					} else {

						pushVertex( v[ i ][ k + 1 ] );
						pushVertex( v[ i + 1 ][ k + 1 ] );
						pushVertex( v[ i + 1 ][ k ] );

					}

				}

			}

		}
```
</details>

### `applyRadius(radius: any): void`

**Parameters:**

- **`radius`** `any`

**Returns:** `void`

**Calls:**

- `vertex.normalize().multiplyScalar`

**Internal Comments:**
```
// iterate over the entire buffer and apply the radius to each vertex
```

<details><summary>Code</summary>

```typescript
function applyRadius( radius ) {

			const vertex = new Vector3();

			// iterate over the entire buffer and apply the radius to each vertex

			for ( let i = 0; i < vertexBuffer.length; i += 3 ) {

				vertex.x = vertexBuffer[ i + 0 ];
				vertex.y = vertexBuffer[ i + 1 ];
				vertex.z = vertexBuffer[ i + 2 ];

				vertex.normalize().multiplyScalar( radius );

				vertexBuffer[ i + 0 ] = vertex.x;
				vertexBuffer[ i + 1 ] = vertex.y;
				vertexBuffer[ i + 2 ] = vertex.z;

			}

		}
```
</details>

### `generateUVs(): void`

**Returns:** `void`

**Calls:**

- `azimuth`
- `inclination`
- `uvBuffer.push`
- `correctUVs`
- `correctSeam`

<details><summary>Code</summary>

```typescript
function generateUVs() {

			const vertex = new Vector3();

			for ( let i = 0; i < vertexBuffer.length; i += 3 ) {

				vertex.x = vertexBuffer[ i + 0 ];
				vertex.y = vertexBuffer[ i + 1 ];
				vertex.z = vertexBuffer[ i + 2 ];

				const u = azimuth( vertex ) / 2 / Math.PI + 0.5;
				const v = inclination( vertex ) / Math.PI + 0.5;
				uvBuffer.push( u, 1 - v );

			}

			correctUVs();

			correctSeam();

		}
```
</details>

### `correctSeam(): void`

**Returns:** `void`

**Calls:**

- `Math.max`
- `Math.min`

**Internal Comments:**
```
// handle case when face straddles the seam, see #3269
// uv data of a single face (x2)
// 0.9 is somewhat arbitrary
```

<details><summary>Code</summary>

```typescript
function correctSeam() {

			// handle case when face straddles the seam, see #3269

			for ( let i = 0; i < uvBuffer.length; i += 6 ) {

				// uv data of a single face

				const x0 = uvBuffer[ i + 0 ];
				const x1 = uvBuffer[ i + 2 ];
				const x2 = uvBuffer[ i + 4 ];

				const max = Math.max( x0, x1, x2 );
				const min = Math.min( x0, x1, x2 );

				// 0.9 is somewhat arbitrary

				if ( max > 0.9 && min < 0.1 ) {

					if ( x0 < 0.2 ) uvBuffer[ i + 0 ] += 1;
					if ( x1 < 0.2 ) uvBuffer[ i + 2 ] += 1;
					if ( x2 < 0.2 ) uvBuffer[ i + 4 ] += 1;

				}

			}

		}
```
</details>

### `pushVertex(vertex: any): void`

**Parameters:**

- **`vertex`** `any`

**Returns:** `void`

**Calls:**

- `vertexBuffer.push`

<details><summary>Code</summary>

```typescript
function pushVertex( vertex ) {

			vertexBuffer.push( vertex.x, vertex.y, vertex.z );

		}
```
</details>

### `getVertexByIndex(index: any, vertex: any): void`

**Parameters:**

- **`index`** `any`
- **`vertex`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function getVertexByIndex( index, vertex ) {

			const stride = index * 3;

			vertex.x = vertices[ stride + 0 ];
			vertex.y = vertices[ stride + 1 ];
			vertex.z = vertices[ stride + 2 ];

		}
```
</details>

### `correctUVs(): void`

**Returns:** `void`

**Calls:**

- `a.set`
- `b.set`
- `c.set`
- `uvA.set`
- `uvB.set`
- `uvC.set`
- `centroid.copy( a ).add( b ).add( c ).divideScalar`
- `azimuth`
- `correctUV`

<details><summary>Code</summary>

```typescript
function correctUVs() {

			const a = new Vector3();
			const b = new Vector3();
			const c = new Vector3();

			const centroid = new Vector3();

			const uvA = new Vector2();
			const uvB = new Vector2();
			const uvC = new Vector2();

			for ( let i = 0, j = 0; i < vertexBuffer.length; i += 9, j += 6 ) {

				a.set( vertexBuffer[ i + 0 ], vertexBuffer[ i + 1 ], vertexBuffer[ i + 2 ] );
				b.set( vertexBuffer[ i + 3 ], vertexBuffer[ i + 4 ], vertexBuffer[ i + 5 ] );
				c.set( vertexBuffer[ i + 6 ], vertexBuffer[ i + 7 ], vertexBuffer[ i + 8 ] );

				uvA.set( uvBuffer[ j + 0 ], uvBuffer[ j + 1 ] );
				uvB.set( uvBuffer[ j + 2 ], uvBuffer[ j + 3 ] );
				uvC.set( uvBuffer[ j + 4 ], uvBuffer[ j + 5 ] );

				centroid.copy( a ).add( b ).add( c ).divideScalar( 3 );

				const azi = azimuth( centroid );

				correctUV( uvA, j + 0, a, azi );
				correctUV( uvB, j + 2, b, azi );
				correctUV( uvC, j + 4, c, azi );

			}

		}
```
</details>

### `correctUV(uv: any, stride: any, vector: any, azimuth: any): void`

**Parameters:**

- **`uv`** `any`
- **`stride`** `any`
- **`vector`** `any`
- **`azimuth`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function correctUV( uv, stride, vector, azimuth ) {

			if ( ( azimuth < 0 ) && ( uv.x === 1 ) ) {

				uvBuffer[ stride ] = uv.x - 1;

			}

			if ( ( vector.x === 0 ) && ( vector.z === 0 ) ) {

				uvBuffer[ stride ] = azimuth / 2 / Math.PI + 0.5;

			}

		}
```
</details>

### `azimuth(vector: any): number`

**Parameters:**

- **`vector`** `any`

**Returns:** `number`

**Calls:**

- `Math.atan2`

<details><summary>Code</summary>

```typescript
function azimuth( vector ) {

			return Math.atan2( vector.z, - vector.x );

		}
```
</details>

### `inclination(vector: any): number`

**Parameters:**

- **`vector`** `any`

**Returns:** `number`

**Calls:**

- `Math.atan2`
- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function inclination( vector ) {

			return Math.atan2( - vector.y, Math.sqrt( ( vector.x * vector.x ) + ( vector.z * vector.z ) ) );

		}
```
</details>


---

## Classes

### `PolyhedronGeometry`

<details><summary>Class Code</summary>

```ts
class PolyhedronGeometry extends BufferGeometry {

	/**
	 * Constructs a new polyhedron geometry.
	 *
	 * @param {Array<number>} [vertices] - A flat array of vertices describing the base shape.
	 * @param {Array<number>} [indices] - A flat array of indices describing the base shape.
	 * @param {number} [radius=1] - The radius of the shape.
	 * @param {number} [detail=0] - How many levels to subdivide the geometry. The more detail, the smoother the shape.
	 */
	constructor( vertices = [], indices = [], radius = 1, detail = 0 ) {

		super();

		this.type = 'PolyhedronGeometry';

		/**
		 * Holds the constructor parameters that have been
		 * used to generate the geometry. Any modification
		 * after instantiation does not change the geometry.
		 *
		 * @type {Object}
		 */
		this.parameters = {
			vertices: vertices,
			indices: indices,
			radius: radius,
			detail: detail
		};

		// default buffer data

		const vertexBuffer = [];
		const uvBuffer = [];

		// the subdivision creates the vertex buffer data

		subdivide( detail );

		// all vertices should lie on a conceptual sphere with a given radius

		applyRadius( radius );

		// finally, create the uv data

		generateUVs();

		// build non-indexed geometry

		this.setAttribute( 'position', new Float32BufferAttribute( vertexBuffer, 3 ) );
		this.setAttribute( 'normal', new Float32BufferAttribute( vertexBuffer.slice(), 3 ) );
		this.setAttribute( 'uv', new Float32BufferAttribute( uvBuffer, 2 ) );

		if ( detail === 0 ) {

			this.computeVertexNormals(); // flat normals

		} else {

			this.normalizeNormals(); // smooth normals

		}

		// helper functions

		function subdivide( detail ) {

			const a = new Vector3();
			const b = new Vector3();
			const c = new Vector3();

			// iterate over all faces and apply a subdivision with the given detail value

			for ( let i = 0; i < indices.length; i += 3 ) {

				// get the vertices of the face

				getVertexByIndex( indices[ i + 0 ], a );
				getVertexByIndex( indices[ i + 1 ], b );
				getVertexByIndex( indices[ i + 2 ], c );

				// perform subdivision

				subdivideFace( a, b, c, detail );

			}

		}

		function subdivideFace( a, b, c, detail ) {

			const cols = detail + 1;

			// we use this multidimensional array as a data structure for creating the subdivision

			const v = [];

			// construct all of the vertices for this subdivision

			for ( let i = 0; i <= cols; i ++ ) {

				v[ i ] = [];

				const aj = a.clone().lerp( c, i / cols );
				const bj = b.clone().lerp( c, i / cols );

				const rows = cols - i;

				for ( let j = 0; j <= rows; j ++ ) {

					if ( j === 0 && i === cols ) {

						v[ i ][ j ] = aj;

					} else {

						v[ i ][ j ] = aj.clone().lerp( bj, j / rows );

					}

				}

			}

			// construct all of the faces

			for ( let i = 0; i < cols; i ++ ) {

				for ( let j = 0; j < 2 * ( cols - i ) - 1; j ++ ) {

					const k = Math.floor( j / 2 );

					if ( j % 2 === 0 ) {

						pushVertex( v[ i ][ k + 1 ] );
						pushVertex( v[ i + 1 ][ k ] );
						pushVertex( v[ i ][ k ] );

					} else {

						pushVertex( v[ i ][ k + 1 ] );
						pushVertex( v[ i + 1 ][ k + 1 ] );
						pushVertex( v[ i + 1 ][ k ] );

					}

				}

			}

		}

		function applyRadius( radius ) {

			const vertex = new Vector3();

			// iterate over the entire buffer and apply the radius to each vertex

			for ( let i = 0; i < vertexBuffer.length; i += 3 ) {

				vertex.x = vertexBuffer[ i + 0 ];
				vertex.y = vertexBuffer[ i + 1 ];
				vertex.z = vertexBuffer[ i + 2 ];

				vertex.normalize().multiplyScalar( radius );

				vertexBuffer[ i + 0 ] = vertex.x;
				vertexBuffer[ i + 1 ] = vertex.y;
				vertexBuffer[ i + 2 ] = vertex.z;

			}

		}

		function generateUVs() {

			const vertex = new Vector3();

			for ( let i = 0; i < vertexBuffer.length; i += 3 ) {

				vertex.x = vertexBuffer[ i + 0 ];
				vertex.y = vertexBuffer[ i + 1 ];
				vertex.z = vertexBuffer[ i + 2 ];

				const u = azimuth( vertex ) / 2 / Math.PI + 0.5;
				const v = inclination( vertex ) / Math.PI + 0.5;
				uvBuffer.push( u, 1 - v );

			}

			correctUVs();

			correctSeam();

		}

		function correctSeam() {

			// handle case when face straddles the seam, see #3269

			for ( let i = 0; i < uvBuffer.length; i += 6 ) {

				// uv data of a single face

				const x0 = uvBuffer[ i + 0 ];
				const x1 = uvBuffer[ i + 2 ];
				const x2 = uvBuffer[ i + 4 ];

				const max = Math.max( x0, x1, x2 );
				const min = Math.min( x0, x1, x2 );

				// 0.9 is somewhat arbitrary

				if ( max > 0.9 && min < 0.1 ) {

					if ( x0 < 0.2 ) uvBuffer[ i + 0 ] += 1;
					if ( x1 < 0.2 ) uvBuffer[ i + 2 ] += 1;
					if ( x2 < 0.2 ) uvBuffer[ i + 4 ] += 1;

				}

			}

		}

		function pushVertex( vertex ) {

			vertexBuffer.push( vertex.x, vertex.y, vertex.z );

		}

		function getVertexByIndex( index, vertex ) {

			const stride = index * 3;

			vertex.x = vertices[ stride + 0 ];
			vertex.y = vertices[ stride + 1 ];
			vertex.z = vertices[ stride + 2 ];

		}

		function correctUVs() {

			const a = new Vector3();
			const b = new Vector3();
			const c = new Vector3();

			const centroid = new Vector3();

			const uvA = new Vector2();
			const uvB = new Vector2();
			const uvC = new Vector2();

			for ( let i = 0, j = 0; i < vertexBuffer.length; i += 9, j += 6 ) {

				a.set( vertexBuffer[ i + 0 ], vertexBuffer[ i + 1 ], vertexBuffer[ i + 2 ] );
				b.set( vertexBuffer[ i + 3 ], vertexBuffer[ i + 4 ], vertexBuffer[ i + 5 ] );
				c.set( vertexBuffer[ i + 6 ], vertexBuffer[ i + 7 ], vertexBuffer[ i + 8 ] );

				uvA.set( uvBuffer[ j + 0 ], uvBuffer[ j + 1 ] );
				uvB.set( uvBuffer[ j + 2 ], uvBuffer[ j + 3 ] );
				uvC.set( uvBuffer[ j + 4 ], uvBuffer[ j + 5 ] );

				centroid.copy( a ).add( b ).add( c ).divideScalar( 3 );

				const azi = azimuth( centroid );

				correctUV( uvA, j + 0, a, azi );
				correctUV( uvB, j + 2, b, azi );
				correctUV( uvC, j + 4, c, azi );

			}

		}

		function correctUV( uv, stride, vector, azimuth ) {

			if ( ( azimuth < 0 ) && ( uv.x === 1 ) ) {

				uvBuffer[ stride ] = uv.x - 1;

			}

			if ( ( vector.x === 0 ) && ( vector.z === 0 ) ) {

				uvBuffer[ stride ] = azimuth / 2 / Math.PI + 0.5;

			}

		}

		// Angle around the Y axis, counter-clockwise when looking from above.

		function azimuth( vector ) {

			return Math.atan2( vector.z, - vector.x );

		}


		// Angle above the XZ plane.

		function inclination( vector ) {

			return Math.atan2( - vector.y, Math.sqrt( ( vector.x * vector.x ) + ( vector.z * vector.z ) ) );

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
	 * @return {PolyhedronGeometry} A new instance.
	 */
	static fromJSON( data ) {

		return new PolyhedronGeometry( data.vertices, data.indices, data.radius, data.details );

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

##### `fromJSON(data: any): PolyhedronGeometry`

<details><summary>Code</summary>

```ts
static fromJSON( data ) {

		return new PolyhedronGeometry( data.vertices, data.indices, data.radius, data.details );

	}
```
</details>


---