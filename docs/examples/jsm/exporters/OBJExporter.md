[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `OBJExporter.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 21 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/exporters/OBJExporter.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `three` |
| `ColorManagement` | `three` |
| `Matrix3` | `three` |
| `SRGBColorSpace` | `three` |
| `Vector2` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `output` | `string` | let/var | `''` | ✗ |
| `indexVertex` | `number` | let/var | `0` | ✗ |
| `indexVertexUvs` | `number` | let/var | `0` | ✗ |
| `indexNormals` | `number` | let/var | `0` | ✗ |
| `vertex` | `any` | let/var | `new Vector3()` | ✗ |
| `color` | `any` | let/var | `new Color()` | ✗ |
| `normal` | `any` | let/var | `new Vector3()` | ✗ |
| `uv` | `any` | let/var | `new Vector2()` | ✗ |
| `face` | `any[]` | let/var | `[]` | ✗ |
| `nbVertex` | `number` | let/var | `0` | ✗ |
| `nbNormals` | `number` | let/var | `0` | ✗ |
| `nbVertexUvs` | `number` | let/var | `0` | ✗ |
| `geometry` | `any` | let/var | `mesh.geometry` | ✗ |
| `normalMatrixWorld` | `any` | let/var | `new Matrix3()` | ✗ |
| `j` | `any` | let/var | `indices.getX( i + m ) + 1` | ✗ |
| `j` | `number` | let/var | `i + m + 1` | ✗ |
| `nbVertex` | `number` | let/var | `0` | ✗ |
| `geometry` | `any` | let/var | `line.geometry` | ✗ |
| `type` | `any` | let/var | `line.type` | ✗ |
| `nbVertex` | `number` | let/var | `0` | ✗ |
| `geometry` | `any` | let/var | `points.geometry` | ✗ |


---

## Functions

### `OBJExporter.parse(object: Object3D): string`

**JSDoc:**
```typescript
/**
	 * Parses the given 3D object and generates the OBJ output.
	 *
	 * If the 3D object is composed of multiple children and geometry, they are merged into a single mesh in the file.
	 *
	 * @param {Object3D} object - The 3D object to export.
	 * @return {string} The exported OBJ.
	 */
```

**Parameters:**

- **`object`** `Object3D`

**Returns:** `string`

**Calls:**

- `geometry.getAttribute`
- `geometry.getIndex`
- `vertex.fromBufferAttribute`
- `vertex.applyMatrix4`
- `uv.fromBufferAttribute`
- `normalMatrixWorld.getNormalMatrix`
- `normal.fromBufferAttribute`
- `normal.applyMatrix3( normalMatrixWorld ).normalize`
- `indices.getX`
- `face.join`
- `color.fromBufferAttribute`
- `ColorManagement.workingToColorSpace`
- `object.traverse`
- `parseMesh`
- `parseLine`
- `parsePoints`

**Internal Comments:**
```
// shortcuts (x4)
// name of the mesh object (x3)
// name of the mesh material
// vertices
// transform the vertex to world space (x8)
// transform the vertex to export format (x6)
// uvs
// transform the uv to export format (x3)
// normals
// transform the normal to world space (x6)
// transform the normal to export format (x3)
// faces
// transform the face to export format (x6)
// update index (x9)
// name of the line object (x3)
```

<details><summary>Code</summary>

```typescript
parse( object ) {

		let output = '';

		let indexVertex = 0;
		let indexVertexUvs = 0;
		let indexNormals = 0;

		const vertex = new Vector3();
		const color = new Color();
		const normal = new Vector3();
		const uv = new Vector2();

		const face = [];

		function parseMesh( mesh ) {

			let nbVertex = 0;
			let nbNormals = 0;
			let nbVertexUvs = 0;

			const geometry = mesh.geometry;

			const normalMatrixWorld = new Matrix3();

			// shortcuts
			const vertices = geometry.getAttribute( 'position' );
			const normals = geometry.getAttribute( 'normal' );
			const uvs = geometry.getAttribute( 'uv' );
			const indices = geometry.getIndex();

			// name of the mesh object
			output += 'o ' + mesh.name + '\n';

			// name of the mesh material
			if ( mesh.material && mesh.material.name ) {

				output += 'usemtl ' + mesh.material.name + '\n';

			}

			// vertices

			if ( vertices !== undefined ) {

				for ( let i = 0, l = vertices.count; i < l; i ++, nbVertex ++ ) {

					vertex.fromBufferAttribute( vertices, i );

					// transform the vertex to world space
					vertex.applyMatrix4( mesh.matrixWorld );

					// transform the vertex to export format
					output += 'v ' + vertex.x + ' ' + vertex.y + ' ' + vertex.z + '\n';

				}

			}

			// uvs

			if ( uvs !== undefined ) {

				for ( let i = 0, l = uvs.count; i < l; i ++, nbVertexUvs ++ ) {

					uv.fromBufferAttribute( uvs, i );

					// transform the uv to export format
					output += 'vt ' + uv.x + ' ' + uv.y + '\n';

				}

			}

			// normals

			if ( normals !== undefined ) {

				normalMatrixWorld.getNormalMatrix( mesh.matrixWorld );

				for ( let i = 0, l = normals.count; i < l; i ++, nbNormals ++ ) {

					normal.fromBufferAttribute( normals, i );

					// transform the normal to world space
					normal.applyMatrix3( normalMatrixWorld ).normalize();

					// transform the normal to export format
					output += 'vn ' + normal.x + ' ' + normal.y + ' ' + normal.z + '\n';

				}

			}

			// faces

			if ( indices !== null ) {

				for ( let i = 0, l = indices.count; i < l; i += 3 ) {

					for ( let m = 0; m < 3; m ++ ) {

						const j = indices.getX( i + m ) + 1;

						face[ m ] = ( indexVertex + j ) + ( normals || uvs ? '/' + ( uvs ? ( indexVertexUvs + j ) : '' ) + ( normals ? '/' + ( indexNormals + j ) : '' ) : '' );

					}

					// transform the face to export format
					output += 'f ' + face.join( ' ' ) + '\n';

				}

			} else {

				for ( let i = 0, l = vertices.count; i < l; i += 3 ) {

					for ( let m = 0; m < 3; m ++ ) {

						const j = i + m + 1;

						face[ m ] = ( indexVertex + j ) + ( normals || uvs ? '/' + ( uvs ? ( indexVertexUvs + j ) : '' ) + ( normals ? '/' + ( indexNormals + j ) : '' ) : '' );

					}

					// transform the face to export format
					output += 'f ' + face.join( ' ' ) + '\n';

				}

			}

			// update index
			indexVertex += nbVertex;
			indexVertexUvs += nbVertexUvs;
			indexNormals += nbNormals;

		}

		function parseLine( line ) {

			let nbVertex = 0;

			const geometry = line.geometry;
			const type = line.type;

			// shortcuts
			const vertices = geometry.getAttribute( 'position' );

			// name of the line object
			output += 'o ' + line.name + '\n';

			if ( vertices !== undefined ) {

				for ( let i = 0, l = vertices.count; i < l; i ++, nbVertex ++ ) {

					vertex.fromBufferAttribute( vertices, i );

					// transform the vertex to world space
					vertex.applyMatrix4( line.matrixWorld );

					// transform the vertex to export format
					output += 'v ' + vertex.x + ' ' + vertex.y + ' ' + vertex.z + '\n';

				}

			}

			if ( type === 'Line' ) {

				output += 'l ';

				for ( let j = 1, l = vertices.count; j <= l; j ++ ) {

					output += ( indexVertex + j ) + ' ';

				}

				output += '\n';

			}

			if ( type === 'LineSegments' ) {

				for ( let j = 1, k = j + 1, l = vertices.count; j < l; j += 2, k = j + 1 ) {

					output += 'l ' + ( indexVertex + j ) + ' ' + ( indexVertex + k ) + '\n';

				}

			}

			// update index
			indexVertex += nbVertex;

		}

		function parsePoints( points ) {

			let nbVertex = 0;

			const geometry = points.geometry;

			const vertices = geometry.getAttribute( 'position' );
			const colors = geometry.getAttribute( 'color' );

			output += 'o ' + points.name + '\n';

			if ( vertices !== undefined ) {

				for ( let i = 0, l = vertices.count; i < l; i ++, nbVertex ++ ) {

					vertex.fromBufferAttribute( vertices, i );
					vertex.applyMatrix4( points.matrixWorld );

					output += 'v ' + vertex.x + ' ' + vertex.y + ' ' + vertex.z;

					if ( colors !== undefined ) {

						color.fromBufferAttribute( colors, i );

						ColorManagement.workingToColorSpace( color, SRGBColorSpace );

						output += ' ' + color.r + ' ' + color.g + ' ' + color.b;

					}

					output += '\n';

				}

				output += 'p ';

				for ( let j = 1, l = vertices.count; j <= l; j ++ ) {

					output += ( indexVertex + j ) + ' ';

				}

				output += '\n';

			}

			// update index
			indexVertex += nbVertex;

		}

		object.traverse( function ( child ) {

			if ( child.isMesh === true ) {

				parseMesh( child );

			}

			if ( child.isLine === true ) {

				parseLine( child );

			}

			if ( child.isPoints === true ) {

				parsePoints( child );

			}

		} );

		return output;

	}
```
</details>

### `parseMesh(mesh: any): void`

**Parameters:**

- **`mesh`** `any`

**Returns:** `void`

**Calls:**

- `geometry.getAttribute`
- `geometry.getIndex`
- `vertex.fromBufferAttribute`
- `vertex.applyMatrix4`
- `uv.fromBufferAttribute`
- `normalMatrixWorld.getNormalMatrix`
- `normal.fromBufferAttribute`
- `normal.applyMatrix3( normalMatrixWorld ).normalize`
- `indices.getX`
- `face.join`

**Internal Comments:**
```
// shortcuts (x2)
// name of the mesh object (x3)
// name of the mesh material
// vertices
// transform the vertex to world space (x4)
// transform the vertex to export format (x3)
// uvs
// transform the uv to export format (x3)
// normals
// transform the normal to world space (x6)
// transform the normal to export format (x3)
// faces
// transform the face to export format (x6)
// update index (x3)
```

<details><summary>Code</summary>

```typescript
function parseMesh( mesh ) {

			let nbVertex = 0;
			let nbNormals = 0;
			let nbVertexUvs = 0;

			const geometry = mesh.geometry;

			const normalMatrixWorld = new Matrix3();

			// shortcuts
			const vertices = geometry.getAttribute( 'position' );
			const normals = geometry.getAttribute( 'normal' );
			const uvs = geometry.getAttribute( 'uv' );
			const indices = geometry.getIndex();

			// name of the mesh object
			output += 'o ' + mesh.name + '\n';

			// name of the mesh material
			if ( mesh.material && mesh.material.name ) {

				output += 'usemtl ' + mesh.material.name + '\n';

			}

			// vertices

			if ( vertices !== undefined ) {

				for ( let i = 0, l = vertices.count; i < l; i ++, nbVertex ++ ) {

					vertex.fromBufferAttribute( vertices, i );

					// transform the vertex to world space
					vertex.applyMatrix4( mesh.matrixWorld );

					// transform the vertex to export format
					output += 'v ' + vertex.x + ' ' + vertex.y + ' ' + vertex.z + '\n';

				}

			}

			// uvs

			if ( uvs !== undefined ) {

				for ( let i = 0, l = uvs.count; i < l; i ++, nbVertexUvs ++ ) {

					uv.fromBufferAttribute( uvs, i );

					// transform the uv to export format
					output += 'vt ' + uv.x + ' ' + uv.y + '\n';

				}

			}

			// normals

			if ( normals !== undefined ) {

				normalMatrixWorld.getNormalMatrix( mesh.matrixWorld );

				for ( let i = 0, l = normals.count; i < l; i ++, nbNormals ++ ) {

					normal.fromBufferAttribute( normals, i );

					// transform the normal to world space
					normal.applyMatrix3( normalMatrixWorld ).normalize();

					// transform the normal to export format
					output += 'vn ' + normal.x + ' ' + normal.y + ' ' + normal.z + '\n';

				}

			}

			// faces

			if ( indices !== null ) {

				for ( let i = 0, l = indices.count; i < l; i += 3 ) {

					for ( let m = 0; m < 3; m ++ ) {

						const j = indices.getX( i + m ) + 1;

						face[ m ] = ( indexVertex + j ) + ( normals || uvs ? '/' + ( uvs ? ( indexVertexUvs + j ) : '' ) + ( normals ? '/' + ( indexNormals + j ) : '' ) : '' );

					}

					// transform the face to export format
					output += 'f ' + face.join( ' ' ) + '\n';

				}

			} else {

				for ( let i = 0, l = vertices.count; i < l; i += 3 ) {

					for ( let m = 0; m < 3; m ++ ) {

						const j = i + m + 1;

						face[ m ] = ( indexVertex + j ) + ( normals || uvs ? '/' + ( uvs ? ( indexVertexUvs + j ) : '' ) + ( normals ? '/' + ( indexNormals + j ) : '' ) : '' );

					}

					// transform the face to export format
					output += 'f ' + face.join( ' ' ) + '\n';

				}

			}

			// update index
			indexVertex += nbVertex;
			indexVertexUvs += nbVertexUvs;
			indexNormals += nbNormals;

		}
```
</details>

### `parseLine(line: any): void`

**Parameters:**

- **`line`** `any`

**Returns:** `void`

**Calls:**

- `geometry.getAttribute`
- `vertex.fromBufferAttribute`
- `vertex.applyMatrix4`

**Internal Comments:**
```
// shortcuts (x2)
// name of the line object (x3)
// transform the vertex to world space (x4)
// transform the vertex to export format (x3)
// update index (x3)
```

<details><summary>Code</summary>

```typescript
function parseLine( line ) {

			let nbVertex = 0;

			const geometry = line.geometry;
			const type = line.type;

			// shortcuts
			const vertices = geometry.getAttribute( 'position' );

			// name of the line object
			output += 'o ' + line.name + '\n';

			if ( vertices !== undefined ) {

				for ( let i = 0, l = vertices.count; i < l; i ++, nbVertex ++ ) {

					vertex.fromBufferAttribute( vertices, i );

					// transform the vertex to world space
					vertex.applyMatrix4( line.matrixWorld );

					// transform the vertex to export format
					output += 'v ' + vertex.x + ' ' + vertex.y + ' ' + vertex.z + '\n';

				}

			}

			if ( type === 'Line' ) {

				output += 'l ';

				for ( let j = 1, l = vertices.count; j <= l; j ++ ) {

					output += ( indexVertex + j ) + ' ';

				}

				output += '\n';

			}

			if ( type === 'LineSegments' ) {

				for ( let j = 1, k = j + 1, l = vertices.count; j < l; j += 2, k = j + 1 ) {

					output += 'l ' + ( indexVertex + j ) + ' ' + ( indexVertex + k ) + '\n';

				}

			}

			// update index
			indexVertex += nbVertex;

		}
```
</details>

### `parsePoints(points: any): void`

**Parameters:**

- **`points`** `any`

**Returns:** `void`

**Calls:**

- `geometry.getAttribute`
- `vertex.fromBufferAttribute`
- `vertex.applyMatrix4`
- `color.fromBufferAttribute`
- `ColorManagement.workingToColorSpace`

**Internal Comments:**
```
// update index (x3)
```

<details><summary>Code</summary>

```typescript
function parsePoints( points ) {

			let nbVertex = 0;

			const geometry = points.geometry;

			const vertices = geometry.getAttribute( 'position' );
			const colors = geometry.getAttribute( 'color' );

			output += 'o ' + points.name + '\n';

			if ( vertices !== undefined ) {

				for ( let i = 0, l = vertices.count; i < l; i ++, nbVertex ++ ) {

					vertex.fromBufferAttribute( vertices, i );
					vertex.applyMatrix4( points.matrixWorld );

					output += 'v ' + vertex.x + ' ' + vertex.y + ' ' + vertex.z;

					if ( colors !== undefined ) {

						color.fromBufferAttribute( colors, i );

						ColorManagement.workingToColorSpace( color, SRGBColorSpace );

						output += ' ' + color.r + ' ' + color.g + ' ' + color.b;

					}

					output += '\n';

				}

				output += 'p ';

				for ( let j = 1, l = vertices.count; j <= l; j ++ ) {

					output += ( indexVertex + j ) + ' ';

				}

				output += '\n';

			}

			// update index
			indexVertex += nbVertex;

		}
```
</details>


---

## Classes

### `OBJExporter`

<details><summary>Class Code</summary>

```ts
class OBJExporter {

	/**
	 * Parses the given 3D object and generates the OBJ output.
	 *
	 * If the 3D object is composed of multiple children and geometry, they are merged into a single mesh in the file.
	 *
	 * @param {Object3D} object - The 3D object to export.
	 * @return {string} The exported OBJ.
	 */
	parse( object ) {

		let output = '';

		let indexVertex = 0;
		let indexVertexUvs = 0;
		let indexNormals = 0;

		const vertex = new Vector3();
		const color = new Color();
		const normal = new Vector3();
		const uv = new Vector2();

		const face = [];

		function parseMesh( mesh ) {

			let nbVertex = 0;
			let nbNormals = 0;
			let nbVertexUvs = 0;

			const geometry = mesh.geometry;

			const normalMatrixWorld = new Matrix3();

			// shortcuts
			const vertices = geometry.getAttribute( 'position' );
			const normals = geometry.getAttribute( 'normal' );
			const uvs = geometry.getAttribute( 'uv' );
			const indices = geometry.getIndex();

			// name of the mesh object
			output += 'o ' + mesh.name + '\n';

			// name of the mesh material
			if ( mesh.material && mesh.material.name ) {

				output += 'usemtl ' + mesh.material.name + '\n';

			}

			// vertices

			if ( vertices !== undefined ) {

				for ( let i = 0, l = vertices.count; i < l; i ++, nbVertex ++ ) {

					vertex.fromBufferAttribute( vertices, i );

					// transform the vertex to world space
					vertex.applyMatrix4( mesh.matrixWorld );

					// transform the vertex to export format
					output += 'v ' + vertex.x + ' ' + vertex.y + ' ' + vertex.z + '\n';

				}

			}

			// uvs

			if ( uvs !== undefined ) {

				for ( let i = 0, l = uvs.count; i < l; i ++, nbVertexUvs ++ ) {

					uv.fromBufferAttribute( uvs, i );

					// transform the uv to export format
					output += 'vt ' + uv.x + ' ' + uv.y + '\n';

				}

			}

			// normals

			if ( normals !== undefined ) {

				normalMatrixWorld.getNormalMatrix( mesh.matrixWorld );

				for ( let i = 0, l = normals.count; i < l; i ++, nbNormals ++ ) {

					normal.fromBufferAttribute( normals, i );

					// transform the normal to world space
					normal.applyMatrix3( normalMatrixWorld ).normalize();

					// transform the normal to export format
					output += 'vn ' + normal.x + ' ' + normal.y + ' ' + normal.z + '\n';

				}

			}

			// faces

			if ( indices !== null ) {

				for ( let i = 0, l = indices.count; i < l; i += 3 ) {

					for ( let m = 0; m < 3; m ++ ) {

						const j = indices.getX( i + m ) + 1;

						face[ m ] = ( indexVertex + j ) + ( normals || uvs ? '/' + ( uvs ? ( indexVertexUvs + j ) : '' ) + ( normals ? '/' + ( indexNormals + j ) : '' ) : '' );

					}

					// transform the face to export format
					output += 'f ' + face.join( ' ' ) + '\n';

				}

			} else {

				for ( let i = 0, l = vertices.count; i < l; i += 3 ) {

					for ( let m = 0; m < 3; m ++ ) {

						const j = i + m + 1;

						face[ m ] = ( indexVertex + j ) + ( normals || uvs ? '/' + ( uvs ? ( indexVertexUvs + j ) : '' ) + ( normals ? '/' + ( indexNormals + j ) : '' ) : '' );

					}

					// transform the face to export format
					output += 'f ' + face.join( ' ' ) + '\n';

				}

			}

			// update index
			indexVertex += nbVertex;
			indexVertexUvs += nbVertexUvs;
			indexNormals += nbNormals;

		}

		function parseLine( line ) {

			let nbVertex = 0;

			const geometry = line.geometry;
			const type = line.type;

			// shortcuts
			const vertices = geometry.getAttribute( 'position' );

			// name of the line object
			output += 'o ' + line.name + '\n';

			if ( vertices !== undefined ) {

				for ( let i = 0, l = vertices.count; i < l; i ++, nbVertex ++ ) {

					vertex.fromBufferAttribute( vertices, i );

					// transform the vertex to world space
					vertex.applyMatrix4( line.matrixWorld );

					// transform the vertex to export format
					output += 'v ' + vertex.x + ' ' + vertex.y + ' ' + vertex.z + '\n';

				}

			}

			if ( type === 'Line' ) {

				output += 'l ';

				for ( let j = 1, l = vertices.count; j <= l; j ++ ) {

					output += ( indexVertex + j ) + ' ';

				}

				output += '\n';

			}

			if ( type === 'LineSegments' ) {

				for ( let j = 1, k = j + 1, l = vertices.count; j < l; j += 2, k = j + 1 ) {

					output += 'l ' + ( indexVertex + j ) + ' ' + ( indexVertex + k ) + '\n';

				}

			}

			// update index
			indexVertex += nbVertex;

		}

		function parsePoints( points ) {

			let nbVertex = 0;

			const geometry = points.geometry;

			const vertices = geometry.getAttribute( 'position' );
			const colors = geometry.getAttribute( 'color' );

			output += 'o ' + points.name + '\n';

			if ( vertices !== undefined ) {

				for ( let i = 0, l = vertices.count; i < l; i ++, nbVertex ++ ) {

					vertex.fromBufferAttribute( vertices, i );
					vertex.applyMatrix4( points.matrixWorld );

					output += 'v ' + vertex.x + ' ' + vertex.y + ' ' + vertex.z;

					if ( colors !== undefined ) {

						color.fromBufferAttribute( colors, i );

						ColorManagement.workingToColorSpace( color, SRGBColorSpace );

						output += ' ' + color.r + ' ' + color.g + ' ' + color.b;

					}

					output += '\n';

				}

				output += 'p ';

				for ( let j = 1, l = vertices.count; j <= l; j ++ ) {

					output += ( indexVertex + j ) + ' ';

				}

				output += '\n';

			}

			// update index
			indexVertex += nbVertex;

		}

		object.traverse( function ( child ) {

			if ( child.isMesh === true ) {

				parseMesh( child );

			}

			if ( child.isLine === true ) {

				parseLine( child );

			}

			if ( child.isPoints === true ) {

				parsePoints( child );

			}

		} );

		return output;

	}

}
```
</details>

#### Methods

##### `parse(object: Object3D): string`

<details><summary>Code</summary>

```ts
parse( object ) {

		let output = '';

		let indexVertex = 0;
		let indexVertexUvs = 0;
		let indexNormals = 0;

		const vertex = new Vector3();
		const color = new Color();
		const normal = new Vector3();
		const uv = new Vector2();

		const face = [];

		function parseMesh( mesh ) {

			let nbVertex = 0;
			let nbNormals = 0;
			let nbVertexUvs = 0;

			const geometry = mesh.geometry;

			const normalMatrixWorld = new Matrix3();

			// shortcuts
			const vertices = geometry.getAttribute( 'position' );
			const normals = geometry.getAttribute( 'normal' );
			const uvs = geometry.getAttribute( 'uv' );
			const indices = geometry.getIndex();

			// name of the mesh object
			output += 'o ' + mesh.name + '\n';

			// name of the mesh material
			if ( mesh.material && mesh.material.name ) {

				output += 'usemtl ' + mesh.material.name + '\n';

			}

			// vertices

			if ( vertices !== undefined ) {

				for ( let i = 0, l = vertices.count; i < l; i ++, nbVertex ++ ) {

					vertex.fromBufferAttribute( vertices, i );

					// transform the vertex to world space
					vertex.applyMatrix4( mesh.matrixWorld );

					// transform the vertex to export format
					output += 'v ' + vertex.x + ' ' + vertex.y + ' ' + vertex.z + '\n';

				}

			}

			// uvs

			if ( uvs !== undefined ) {

				for ( let i = 0, l = uvs.count; i < l; i ++, nbVertexUvs ++ ) {

					uv.fromBufferAttribute( uvs, i );

					// transform the uv to export format
					output += 'vt ' + uv.x + ' ' + uv.y + '\n';

				}

			}

			// normals

			if ( normals !== undefined ) {

				normalMatrixWorld.getNormalMatrix( mesh.matrixWorld );

				for ( let i = 0, l = normals.count; i < l; i ++, nbNormals ++ ) {

					normal.fromBufferAttribute( normals, i );

					// transform the normal to world space
					normal.applyMatrix3( normalMatrixWorld ).normalize();

					// transform the normal to export format
					output += 'vn ' + normal.x + ' ' + normal.y + ' ' + normal.z + '\n';

				}

			}

			// faces

			if ( indices !== null ) {

				for ( let i = 0, l = indices.count; i < l; i += 3 ) {

					for ( let m = 0; m < 3; m ++ ) {

						const j = indices.getX( i + m ) + 1;

						face[ m ] = ( indexVertex + j ) + ( normals || uvs ? '/' + ( uvs ? ( indexVertexUvs + j ) : '' ) + ( normals ? '/' + ( indexNormals + j ) : '' ) : '' );

					}

					// transform the face to export format
					output += 'f ' + face.join( ' ' ) + '\n';

				}

			} else {

				for ( let i = 0, l = vertices.count; i < l; i += 3 ) {

					for ( let m = 0; m < 3; m ++ ) {

						const j = i + m + 1;

						face[ m ] = ( indexVertex + j ) + ( normals || uvs ? '/' + ( uvs ? ( indexVertexUvs + j ) : '' ) + ( normals ? '/' + ( indexNormals + j ) : '' ) : '' );

					}

					// transform the face to export format
					output += 'f ' + face.join( ' ' ) + '\n';

				}

			}

			// update index
			indexVertex += nbVertex;
			indexVertexUvs += nbVertexUvs;
			indexNormals += nbNormals;

		}

		function parseLine( line ) {

			let nbVertex = 0;

			const geometry = line.geometry;
			const type = line.type;

			// shortcuts
			const vertices = geometry.getAttribute( 'position' );

			// name of the line object
			output += 'o ' + line.name + '\n';

			if ( vertices !== undefined ) {

				for ( let i = 0, l = vertices.count; i < l; i ++, nbVertex ++ ) {

					vertex.fromBufferAttribute( vertices, i );

					// transform the vertex to world space
					vertex.applyMatrix4( line.matrixWorld );

					// transform the vertex to export format
					output += 'v ' + vertex.x + ' ' + vertex.y + ' ' + vertex.z + '\n';

				}

			}

			if ( type === 'Line' ) {

				output += 'l ';

				for ( let j = 1, l = vertices.count; j <= l; j ++ ) {

					output += ( indexVertex + j ) + ' ';

				}

				output += '\n';

			}

			if ( type === 'LineSegments' ) {

				for ( let j = 1, k = j + 1, l = vertices.count; j < l; j += 2, k = j + 1 ) {

					output += 'l ' + ( indexVertex + j ) + ' ' + ( indexVertex + k ) + '\n';

				}

			}

			// update index
			indexVertex += nbVertex;

		}

		function parsePoints( points ) {

			let nbVertex = 0;

			const geometry = points.geometry;

			const vertices = geometry.getAttribute( 'position' );
			const colors = geometry.getAttribute( 'color' );

			output += 'o ' + points.name + '\n';

			if ( vertices !== undefined ) {

				for ( let i = 0, l = vertices.count; i < l; i ++, nbVertex ++ ) {

					vertex.fromBufferAttribute( vertices, i );
					vertex.applyMatrix4( points.matrixWorld );

					output += 'v ' + vertex.x + ' ' + vertex.y + ' ' + vertex.z;

					if ( colors !== undefined ) {

						color.fromBufferAttribute( colors, i );

						ColorManagement.workingToColorSpace( color, SRGBColorSpace );

						output += ' ' + color.r + ' ' + color.g + ' ' + color.b;

					}

					output += '\n';

				}

				output += 'p ';

				for ( let j = 1, l = vertices.count; j <= l; j ++ ) {

					output += ( indexVertex + j ) + ' ';

				}

				output += '\n';

			}

			// update index
			indexVertex += nbVertex;

		}

		object.traverse( function ( child ) {

			if ( child.isMesh === true ) {

				parseMesh( child );

			}

			if ( child.isLine === true ) {

				parseLine( child );

			}

			if ( child.isPoints === true ) {

				parsePoints( child );

			}

		} );

		return output;

	}
```
</details>


---