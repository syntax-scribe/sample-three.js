[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `STLExporter.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 21 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/exporters/STLExporter.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `binary` | `any` | let/var | `options.binary` | ✗ |
| `objects` | `any[]` | let/var | `[]` | ✗ |
| `triangles` | `number` | let/var | `0` | ✗ |
| `geometry` | `any` | let/var | `object.geometry` | ✗ |
| `index` | `any` | let/var | `geometry.index` | ✗ |
| `output` | `any` | let/var | `*not shown*` | ✗ |
| `offset` | `number` | let/var | `80` | ✗ |
| `bufferLength` | `number` | let/var | `triangles * 2 + triangles * 3 * 4 * 4 + 80 + 4` | ✗ |
| `arrayBuffer` | `ArrayBuffer` | let/var | `new ArrayBuffer( bufferLength )` | ✗ |
| `vA` | `any` | let/var | `new Vector3()` | ✗ |
| `vB` | `any` | let/var | `new Vector3()` | ✗ |
| `vC` | `any` | let/var | `new Vector3()` | ✗ |
| `cb` | `any` | let/var | `new Vector3()` | ✗ |
| `ab` | `any` | let/var | `new Vector3()` | ✗ |
| `normal` | `any` | let/var | `new Vector3()` | ✗ |
| `object` | `any` | let/var | `objects[ i ].object3d` | ✗ |
| `geometry` | `any` | let/var | `objects[ i ].geometry` | ✗ |
| `index` | `any` | let/var | `geometry.index` | ✗ |
| `a` | `number` | let/var | `j + 0` | ✗ |
| `b` | `number` | let/var | `j + 1` | ✗ |
| `c` | `number` | let/var | `j + 2` | ✗ |


---

## Functions

### `STLExporter.parse(scene: Object3D, options: {}): string | ArrayBuffer`

**JSDoc:**
```typescript
/**
	 * Parses the given 3D object and generates the STL output.
	 *
	 * If the 3D object is composed of multiple children and geometry, they are merged into a single mesh in the file.
	 *
	 * @param {Object3D} scene - A scene, mesh or any other 3D object containing meshes to encode.
	 * @param {STLExporter~Options} options - The export options.
	 * @return {string|ArrayBuffer} The exported STL.
	 */
```

**Parameters:**

- **`scene`** `Object3D`
- **`options`** `{}`

**Returns:** `string | ArrayBuffer`

**Calls:**

- `Object.assign`
- `scene.traverse`
- `geometry.getAttribute`
- `objects.push`
- `output.setUint32`
- `index.getX`
- `writeFace`
- `vA.fromBufferAttribute`
- `vB.fromBufferAttribute`
- `vC.fromBufferAttribute`
- `object.applyBoneTransform`
- `vA.applyMatrix4`
- `vB.applyMatrix4`
- `vC.applyMatrix4`
- `writeNormal`
- `writeVertex`
- `output.setUint16`
- `cb.subVectors`
- `ab.subVectors`
- `cb.cross( ab ).normalize`
- `normal.copy( cb ).normalize`
- `output.setFloat32`

**Internal Comments:**
```
// (x2)
// indexed geometry
// non-indexed geometry
```

<details><summary>Code</summary>

```typescript
parse( scene, options = {} ) {

		options = Object.assign( {
			binary: false
		}, options );

		const binary = options.binary;

		//

		const objects = [];
		let triangles = 0;

		scene.traverse( function ( object ) {

			if ( object.isMesh ) {

				const geometry = object.geometry;

				const index = geometry.index;
				const positionAttribute = geometry.getAttribute( 'position' );

				triangles += ( index !== null ) ? ( index.count / 3 ) : ( positionAttribute.count / 3 );

				objects.push( {
					object3d: object,
					geometry: geometry
				} );

			}

		} );

		let output;
		let offset = 80; // skip header

		if ( binary === true ) {

			const bufferLength = triangles * 2 + triangles * 3 * 4 * 4 + 80 + 4;
			const arrayBuffer = new ArrayBuffer( bufferLength );
			output = new DataView( arrayBuffer );
			output.setUint32( offset, triangles, true ); offset += 4;

		} else {

			output = '';
			output += 'solid exported\n';

		}

		const vA = new Vector3();
		const vB = new Vector3();
		const vC = new Vector3();
		const cb = new Vector3();
		const ab = new Vector3();
		const normal = new Vector3();

		for ( let i = 0, il = objects.length; i < il; i ++ ) {

			const object = objects[ i ].object3d;
			const geometry = objects[ i ].geometry;

			const index = geometry.index;
			const positionAttribute = geometry.getAttribute( 'position' );

			if ( index !== null ) {

				// indexed geometry

				for ( let j = 0; j < index.count; j += 3 ) {

					const a = index.getX( j + 0 );
					const b = index.getX( j + 1 );
					const c = index.getX( j + 2 );

					writeFace( a, b, c, positionAttribute, object );

				}

			} else {

				// non-indexed geometry

				for ( let j = 0; j < positionAttribute.count; j += 3 ) {

					const a = j + 0;
					const b = j + 1;
					const c = j + 2;

					writeFace( a, b, c, positionAttribute, object );

				}

			}

		}

		if ( binary === false ) {

			output += 'endsolid exported\n';

		}

		return output;

		function writeFace( a, b, c, positionAttribute, object ) {

			vA.fromBufferAttribute( positionAttribute, a );
			vB.fromBufferAttribute( positionAttribute, b );
			vC.fromBufferAttribute( positionAttribute, c );

			if ( object.isSkinnedMesh === true ) {

				object.applyBoneTransform( a, vA );
				object.applyBoneTransform( b, vB );
				object.applyBoneTransform( c, vC );

			}

			vA.applyMatrix4( object.matrixWorld );
			vB.applyMatrix4( object.matrixWorld );
			vC.applyMatrix4( object.matrixWorld );

			writeNormal( vA, vB, vC );

			writeVertex( vA );
			writeVertex( vB );
			writeVertex( vC );

			if ( binary === true ) {

				output.setUint16( offset, 0, true ); offset += 2;

			} else {

				output += '\t\tendloop\n';
				output += '\tendfacet\n';

			}

		}

		function writeNormal( vA, vB, vC ) {

			cb.subVectors( vC, vB );
			ab.subVectors( vA, vB );
			cb.cross( ab ).normalize();

			normal.copy( cb ).normalize();

			if ( binary === true ) {

				output.setFloat32( offset, normal.x, true ); offset += 4;
				output.setFloat32( offset, normal.y, true ); offset += 4;
				output.setFloat32( offset, normal.z, true ); offset += 4;

			} else {

				output += '\tfacet normal ' + normal.x + ' ' + normal.y + ' ' + normal.z + '\n';
				output += '\t\touter loop\n';

			}

		}

		function writeVertex( vertex ) {

			if ( binary === true ) {

				output.setFloat32( offset, vertex.x, true ); offset += 4;
				output.setFloat32( offset, vertex.y, true ); offset += 4;
				output.setFloat32( offset, vertex.z, true ); offset += 4;

			} else {

				output += '\t\t\tvertex ' + vertex.x + ' ' + vertex.y + ' ' + vertex.z + '\n';

			}

		}

	}
```
</details>

### `writeFace(a: any, b: any, c: any, positionAttribute: any, object: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`
- **`positionAttribute`** `any`
- **`object`** `any`

**Returns:** `void`

**Calls:**

- `vA.fromBufferAttribute`
- `vB.fromBufferAttribute`
- `vC.fromBufferAttribute`
- `object.applyBoneTransform`
- `vA.applyMatrix4`
- `vB.applyMatrix4`
- `vC.applyMatrix4`
- `writeNormal`
- `writeVertex`
- `output.setUint16`

<details><summary>Code</summary>

```typescript
function writeFace( a, b, c, positionAttribute, object ) {

			vA.fromBufferAttribute( positionAttribute, a );
			vB.fromBufferAttribute( positionAttribute, b );
			vC.fromBufferAttribute( positionAttribute, c );

			if ( object.isSkinnedMesh === true ) {

				object.applyBoneTransform( a, vA );
				object.applyBoneTransform( b, vB );
				object.applyBoneTransform( c, vC );

			}

			vA.applyMatrix4( object.matrixWorld );
			vB.applyMatrix4( object.matrixWorld );
			vC.applyMatrix4( object.matrixWorld );

			writeNormal( vA, vB, vC );

			writeVertex( vA );
			writeVertex( vB );
			writeVertex( vC );

			if ( binary === true ) {

				output.setUint16( offset, 0, true ); offset += 2;

			} else {

				output += '\t\tendloop\n';
				output += '\tendfacet\n';

			}

		}
```
</details>

### `writeNormal(vA: any, vB: any, vC: any): void`

**Parameters:**

- **`vA`** `any`
- **`vB`** `any`
- **`vC`** `any`

**Returns:** `void`

**Calls:**

- `cb.subVectors`
- `ab.subVectors`
- `cb.cross( ab ).normalize`
- `normal.copy( cb ).normalize`
- `output.setFloat32`

<details><summary>Code</summary>

```typescript
function writeNormal( vA, vB, vC ) {

			cb.subVectors( vC, vB );
			ab.subVectors( vA, vB );
			cb.cross( ab ).normalize();

			normal.copy( cb ).normalize();

			if ( binary === true ) {

				output.setFloat32( offset, normal.x, true ); offset += 4;
				output.setFloat32( offset, normal.y, true ); offset += 4;
				output.setFloat32( offset, normal.z, true ); offset += 4;

			} else {

				output += '\tfacet normal ' + normal.x + ' ' + normal.y + ' ' + normal.z + '\n';
				output += '\t\touter loop\n';

			}

		}
```
</details>

### `writeVertex(vertex: any): void`

**Parameters:**

- **`vertex`** `any`

**Returns:** `void`

**Calls:**

- `output.setFloat32`

<details><summary>Code</summary>

```typescript
function writeVertex( vertex ) {

			if ( binary === true ) {

				output.setFloat32( offset, vertex.x, true ); offset += 4;
				output.setFloat32( offset, vertex.y, true ); offset += 4;
				output.setFloat32( offset, vertex.z, true ); offset += 4;

			} else {

				output += '\t\t\tvertex ' + vertex.x + ' ' + vertex.y + ' ' + vertex.z + '\n';

			}

		}
```
</details>


---

## Classes

### `STLExporter`

<details><summary>Class Code</summary>

```ts
class STLExporter {

	/**
	 * Parses the given 3D object and generates the STL output.
	 *
	 * If the 3D object is composed of multiple children and geometry, they are merged into a single mesh in the file.
	 *
	 * @param {Object3D} scene - A scene, mesh or any other 3D object containing meshes to encode.
	 * @param {STLExporter~Options} options - The export options.
	 * @return {string|ArrayBuffer} The exported STL.
	 */
	parse( scene, options = {} ) {

		options = Object.assign( {
			binary: false
		}, options );

		const binary = options.binary;

		//

		const objects = [];
		let triangles = 0;

		scene.traverse( function ( object ) {

			if ( object.isMesh ) {

				const geometry = object.geometry;

				const index = geometry.index;
				const positionAttribute = geometry.getAttribute( 'position' );

				triangles += ( index !== null ) ? ( index.count / 3 ) : ( positionAttribute.count / 3 );

				objects.push( {
					object3d: object,
					geometry: geometry
				} );

			}

		} );

		let output;
		let offset = 80; // skip header

		if ( binary === true ) {

			const bufferLength = triangles * 2 + triangles * 3 * 4 * 4 + 80 + 4;
			const arrayBuffer = new ArrayBuffer( bufferLength );
			output = new DataView( arrayBuffer );
			output.setUint32( offset, triangles, true ); offset += 4;

		} else {

			output = '';
			output += 'solid exported\n';

		}

		const vA = new Vector3();
		const vB = new Vector3();
		const vC = new Vector3();
		const cb = new Vector3();
		const ab = new Vector3();
		const normal = new Vector3();

		for ( let i = 0, il = objects.length; i < il; i ++ ) {

			const object = objects[ i ].object3d;
			const geometry = objects[ i ].geometry;

			const index = geometry.index;
			const positionAttribute = geometry.getAttribute( 'position' );

			if ( index !== null ) {

				// indexed geometry

				for ( let j = 0; j < index.count; j += 3 ) {

					const a = index.getX( j + 0 );
					const b = index.getX( j + 1 );
					const c = index.getX( j + 2 );

					writeFace( a, b, c, positionAttribute, object );

				}

			} else {

				// non-indexed geometry

				for ( let j = 0; j < positionAttribute.count; j += 3 ) {

					const a = j + 0;
					const b = j + 1;
					const c = j + 2;

					writeFace( a, b, c, positionAttribute, object );

				}

			}

		}

		if ( binary === false ) {

			output += 'endsolid exported\n';

		}

		return output;

		function writeFace( a, b, c, positionAttribute, object ) {

			vA.fromBufferAttribute( positionAttribute, a );
			vB.fromBufferAttribute( positionAttribute, b );
			vC.fromBufferAttribute( positionAttribute, c );

			if ( object.isSkinnedMesh === true ) {

				object.applyBoneTransform( a, vA );
				object.applyBoneTransform( b, vB );
				object.applyBoneTransform( c, vC );

			}

			vA.applyMatrix4( object.matrixWorld );
			vB.applyMatrix4( object.matrixWorld );
			vC.applyMatrix4( object.matrixWorld );

			writeNormal( vA, vB, vC );

			writeVertex( vA );
			writeVertex( vB );
			writeVertex( vC );

			if ( binary === true ) {

				output.setUint16( offset, 0, true ); offset += 2;

			} else {

				output += '\t\tendloop\n';
				output += '\tendfacet\n';

			}

		}

		function writeNormal( vA, vB, vC ) {

			cb.subVectors( vC, vB );
			ab.subVectors( vA, vB );
			cb.cross( ab ).normalize();

			normal.copy( cb ).normalize();

			if ( binary === true ) {

				output.setFloat32( offset, normal.x, true ); offset += 4;
				output.setFloat32( offset, normal.y, true ); offset += 4;
				output.setFloat32( offset, normal.z, true ); offset += 4;

			} else {

				output += '\tfacet normal ' + normal.x + ' ' + normal.y + ' ' + normal.z + '\n';
				output += '\t\touter loop\n';

			}

		}

		function writeVertex( vertex ) {

			if ( binary === true ) {

				output.setFloat32( offset, vertex.x, true ); offset += 4;
				output.setFloat32( offset, vertex.y, true ); offset += 4;
				output.setFloat32( offset, vertex.z, true ); offset += 4;

			} else {

				output += '\t\t\tvertex ' + vertex.x + ' ' + vertex.y + ' ' + vertex.z + '\n';

			}

		}

	}

}
```
</details>

#### Methods

##### `parse(scene: Object3D, options: {}): string | ArrayBuffer`

<details><summary>Code</summary>

```ts
parse( scene, options = {} ) {

		options = Object.assign( {
			binary: false
		}, options );

		const binary = options.binary;

		//

		const objects = [];
		let triangles = 0;

		scene.traverse( function ( object ) {

			if ( object.isMesh ) {

				const geometry = object.geometry;

				const index = geometry.index;
				const positionAttribute = geometry.getAttribute( 'position' );

				triangles += ( index !== null ) ? ( index.count / 3 ) : ( positionAttribute.count / 3 );

				objects.push( {
					object3d: object,
					geometry: geometry
				} );

			}

		} );

		let output;
		let offset = 80; // skip header

		if ( binary === true ) {

			const bufferLength = triangles * 2 + triangles * 3 * 4 * 4 + 80 + 4;
			const arrayBuffer = new ArrayBuffer( bufferLength );
			output = new DataView( arrayBuffer );
			output.setUint32( offset, triangles, true ); offset += 4;

		} else {

			output = '';
			output += 'solid exported\n';

		}

		const vA = new Vector3();
		const vB = new Vector3();
		const vC = new Vector3();
		const cb = new Vector3();
		const ab = new Vector3();
		const normal = new Vector3();

		for ( let i = 0, il = objects.length; i < il; i ++ ) {

			const object = objects[ i ].object3d;
			const geometry = objects[ i ].geometry;

			const index = geometry.index;
			const positionAttribute = geometry.getAttribute( 'position' );

			if ( index !== null ) {

				// indexed geometry

				for ( let j = 0; j < index.count; j += 3 ) {

					const a = index.getX( j + 0 );
					const b = index.getX( j + 1 );
					const c = index.getX( j + 2 );

					writeFace( a, b, c, positionAttribute, object );

				}

			} else {

				// non-indexed geometry

				for ( let j = 0; j < positionAttribute.count; j += 3 ) {

					const a = j + 0;
					const b = j + 1;
					const c = j + 2;

					writeFace( a, b, c, positionAttribute, object );

				}

			}

		}

		if ( binary === false ) {

			output += 'endsolid exported\n';

		}

		return output;

		function writeFace( a, b, c, positionAttribute, object ) {

			vA.fromBufferAttribute( positionAttribute, a );
			vB.fromBufferAttribute( positionAttribute, b );
			vC.fromBufferAttribute( positionAttribute, c );

			if ( object.isSkinnedMesh === true ) {

				object.applyBoneTransform( a, vA );
				object.applyBoneTransform( b, vB );
				object.applyBoneTransform( c, vC );

			}

			vA.applyMatrix4( object.matrixWorld );
			vB.applyMatrix4( object.matrixWorld );
			vC.applyMatrix4( object.matrixWorld );

			writeNormal( vA, vB, vC );

			writeVertex( vA );
			writeVertex( vB );
			writeVertex( vC );

			if ( binary === true ) {

				output.setUint16( offset, 0, true ); offset += 2;

			} else {

				output += '\t\tendloop\n';
				output += '\tendfacet\n';

			}

		}

		function writeNormal( vA, vB, vC ) {

			cb.subVectors( vC, vB );
			ab.subVectors( vA, vB );
			cb.cross( ab ).normalize();

			normal.copy( cb ).normalize();

			if ( binary === true ) {

				output.setFloat32( offset, normal.x, true ); offset += 4;
				output.setFloat32( offset, normal.y, true ); offset += 4;
				output.setFloat32( offset, normal.z, true ); offset += 4;

			} else {

				output += '\tfacet normal ' + normal.x + ' ' + normal.y + ' ' + normal.z + '\n';
				output += '\t\touter loop\n';

			}

		}

		function writeVertex( vertex ) {

			if ( binary === true ) {

				output.setFloat32( offset, vertex.x, true ); offset += 4;
				output.setFloat32( offset, vertex.y, true ); offset += 4;
				output.setFloat32( offset, vertex.z, true ); offset += 4;

			} else {

				output += '\t\t\tvertex ' + vertex.x + ' ' + vertex.y + ' ' + vertex.z + '\n';

			}

		}

	}
```
</details>


---