[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MD2Loader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 51 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/MD2Loader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnimationClip` | `three` |
| `BufferGeometry` | `three` |
| `FileLoader` | `three` |
| `Float32BufferAttribute` | `three` |
| `Loader` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_normalData` | `number[][]` | let/var | `[ [ - 0.525731, 0.000000, 0.850651 ], [ - 0.442863, 0.238856, 0.864188 ], [ -...` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( scope.manager )` | ✗ |
| `data` | `DataView<ArrayBuffer>` | let/var | `new DataView( buffer )` | ✗ |
| `header` | `{}` | let/var | `{}` | ✗ |
| `headerNames` | `string[]` | let/var | `[ 'ident', 'version', 'skinwidth', 'skinheight', 'framesize', 'num_skins', 'n...` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `uvsTemp` | `any[]` | let/var | `[]` | ✗ |
| `offset` | `any` | let/var | `header.offset_st` | ✗ |
| `vertexIndices` | `any[]` | let/var | `[]` | ✗ |
| `uvIndices` | `any[]` | let/var | `[]` | ✗ |
| `translation` | `any` | let/var | `new Vector3()` | ✗ |
| `scale` | `any` | let/var | `new Vector3()` | ✗ |
| `frames` | `any[]` | let/var | `[]` | ✗ |
| `string` | `any[]` | let/var | `[]` | ✗ |
| `frame` | `{ name: any; vertices: any[]; normals...` | let/var | `{ name: String.fromCharCode.apply( null, string ), vertices: [], normals: [] }` | ✗ |
| `n` | `number[]` | let/var | `_normalData[ data.getUint8( offset ++ ) ]` | ✗ |
| `positions` | `any[]` | let/var | `[]` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `uvs` | `any[]` | let/var | `[]` | ✗ |
| `verticesTemp` | `any[]` | let/var | `frames[ 0 ].vertices` | ✗ |
| `normalsTemp` | `any[]` | let/var | `frames[ 0 ].normals` | ✗ |
| `vertexIndex` | `number` | let/var | `vertexIndices[ i ]` | ✗ |
| `stride` | `number` | let/var | `vertexIndex * 3` | ✗ |
| `x` | `any` | let/var | `verticesTemp[ stride ]` | ✗ |
| `y` | `any` | let/var | `verticesTemp[ stride + 1 ]` | ✗ |
| `z` | `any` | let/var | `verticesTemp[ stride + 2 ]` | ✗ |
| `nx` | `any` | let/var | `normalsTemp[ stride ]` | ✗ |
| `ny` | `any` | let/var | `normalsTemp[ stride + 1 ]` | ✗ |
| `nz` | `any` | let/var | `normalsTemp[ stride + 2 ]` | ✗ |
| `uvIndex` | `number` | let/var | `uvIndices[ i ]` | ✗ |
| `u` | `number` | let/var | `uvsTemp[ stride ]` | ✗ |
| `v` | `number` | let/var | `uvsTemp[ stride + 1 ]` | ✗ |
| `morphPositions` | `any[]` | let/var | `[]` | ✗ |
| `morphNormals` | `any[]` | let/var | `[]` | ✗ |
| `frame` | `{ name: any; vertices: any[]; normals...` | let/var | `frames[ i ]` | ✗ |
| `attributeName` | `any` | let/var | `frame.name` | ✗ |
| `positions` | `any[]` | let/var | `[]` | ✗ |
| `vertexIndex` | `number` | let/var | `vertexIndices[ j ]` | ✗ |
| `stride` | `number` | let/var | `vertexIndex * 3` | ✗ |
| `x` | `any` | let/var | `frame.vertices[ stride ]` | ✗ |
| `y` | `any` | let/var | `frame.vertices[ stride + 1 ]` | ✗ |
| `z` | `any` | let/var | `frame.vertices[ stride + 2 ]` | ✗ |
| `positionAttribute` | `any` | let/var | `new Float32BufferAttribute( positions, 3 )` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `vertexIndex` | `number` | let/var | `vertexIndices[ j ]` | ✗ |
| `stride` | `number` | let/var | `vertexIndex * 3` | ✗ |
| `nx` | `any` | let/var | `frame.normals[ stride ]` | ✗ |
| `ny` | `any` | let/var | `frame.normals[ stride + 1 ]` | ✗ |
| `nz` | `any` | let/var | `frame.normals[ stride + 2 ]` | ✗ |
| `normalAttribute` | `any` | let/var | `new Float32BufferAttribute( normals, 3 )` | ✗ |


---

## Functions

### `MD2Loader.load(url: string, onLoad: (arg0: BufferGeometry) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded MD2 asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(BufferGeometry)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} [onProgress] - Executed while the loading is in progress.
	 * @param {onErrorCallback} [onError] - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: BufferGeometry) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `loader.setPath`
- `loader.setResponseType`
- `loader.setRequestHeader`
- `loader.setWithCredentials`
- `loader.load`
- `onLoad`
- `scope.parse`
- `onError`
- `console.error`
- `scope.manager.itemError`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( buffer ) {

			try {

				onLoad( scope.parse( buffer ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

### `MD2Loader.parse(buffer: ArrayBuffer): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Parses the given MD2 data and returns a geometry.
	 *
	 * @param {ArrayBuffer} buffer - The raw MD2 data as an array buffer.
	 * @return {BufferGeometry} The parsed geometry data.
	 */
```

**Parameters:**

- **`buffer`** `ArrayBuffer`

**Returns:** `BufferGeometry`

**Calls:**

- `data.getInt32`
- `console.error`
- `data.getInt16`
- `uvsTemp.push`
- `vertexIndices.push`
- `data.getUint16`
- `uvIndices.push`
- `scale.set`
- `data.getFloat32`
- `translation.set`
- `data.getUint8`
- `String.fromCharCode.apply`
- `frame.vertices.push`
- `frame.normals.push`
- `frames.push`
- `positions.push`
- `normals.push`
- `uvs.push`
- `geometry.setAttribute`
- `morphPositions.push`
- `morphNormals.push`
- `AnimationClip.CreateClipsFromMorphTargetSequences`

**Internal Comments:**
```
// http://tfc.duke.free.fr/coding/md2-specs-en.html (x2)
// (x8)
// uvs (x2)
// triangles (x3)
// frames (x2)
// static (x2)
// animation (x2)
```

<details><summary>Code</summary>

```typescript
parse( buffer ) {

		const data = new DataView( buffer );

		// http://tfc.duke.free.fr/coding/md2-specs-en.html

		const header = {};
		const headerNames = [
			'ident', 'version',
			'skinwidth', 'skinheight',
			'framesize',
			'num_skins', 'num_vertices', 'num_st', 'num_tris', 'num_glcmds', 'num_frames',
			'offset_skins', 'offset_st', 'offset_tris', 'offset_frames', 'offset_glcmds', 'offset_end'
		];

		for ( let i = 0; i < headerNames.length; i ++ ) {

			header[ headerNames[ i ] ] = data.getInt32( i * 4, true );

		}

		if ( header.ident !== 844121161 || header.version !== 8 ) {

			console.error( 'Not a valid MD2 file' );
			return;

		}

		if ( header.offset_end !== data.byteLength ) {

			console.error( 'Corrupted MD2 file' );
			return;

		}

		//

		const geometry = new BufferGeometry();

		// uvs

		const uvsTemp = [];
		let offset = header.offset_st;

		for ( let i = 0, l = header.num_st; i < l; i ++ ) {

			const u = data.getInt16( offset + 0, true );
			const v = data.getInt16( offset + 2, true );

			uvsTemp.push( u / header.skinwidth, 1 - ( v / header.skinheight ) );

			offset += 4;

		}

		// triangles

		offset = header.offset_tris;

		const vertexIndices = [];
		const uvIndices = [];

		for ( let i = 0, l = header.num_tris; i < l; i ++ ) {

			vertexIndices.push(
				data.getUint16( offset + 0, true ),
				data.getUint16( offset + 2, true ),
				data.getUint16( offset + 4, true )
			);

			uvIndices.push(
				data.getUint16( offset + 6, true ),
				data.getUint16( offset + 8, true ),
				data.getUint16( offset + 10, true )
			);

			offset += 12;

		}

		// frames

		const translation = new Vector3();
		const scale = new Vector3();

		const frames = [];

		offset = header.offset_frames;

		for ( let i = 0, l = header.num_frames; i < l; i ++ ) {

			scale.set(
				data.getFloat32( offset + 0, true ),
				data.getFloat32( offset + 4, true ),
				data.getFloat32( offset + 8, true )
			);

			translation.set(
				data.getFloat32( offset + 12, true ),
				data.getFloat32( offset + 16, true ),
				data.getFloat32( offset + 20, true )
			);

			offset += 24;

			const string = [];

			for ( let j = 0; j < 16; j ++ ) {

				const character = data.getUint8( offset + j );
				if ( character === 0 ) break;

				string[ j ] = character;

			}

			const frame = {
				name: String.fromCharCode.apply( null, string ),
				vertices: [],
				normals: []
			};

			offset += 16;

			for ( let j = 0; j < header.num_vertices; j ++ ) {

				let x = data.getUint8( offset ++ );
				let y = data.getUint8( offset ++ );
				let z = data.getUint8( offset ++ );
				const n = _normalData[ data.getUint8( offset ++ ) ];

				x = x * scale.x + translation.x;
				y = y * scale.y + translation.y;
				z = z * scale.z + translation.z;

				frame.vertices.push( x, z, y ); // convert to Y-up
				frame.normals.push( n[ 0 ], n[ 2 ], n[ 1 ] ); // convert to Y-up

			}

			frames.push( frame );

		}

		// static

		const positions = [];
		const normals = [];
		const uvs = [];

		const verticesTemp = frames[ 0 ].vertices;
		const normalsTemp = frames[ 0 ].normals;

		for ( let i = 0, l = vertexIndices.length; i < l; i ++ ) {

			const vertexIndex = vertexIndices[ i ];
			let stride = vertexIndex * 3;

			//

			const x = verticesTemp[ stride ];
			const y = verticesTemp[ stride + 1 ];
			const z = verticesTemp[ stride + 2 ];

			positions.push( x, y, z );

			//

			const nx = normalsTemp[ stride ];
			const ny = normalsTemp[ stride + 1 ];
			const nz = normalsTemp[ stride + 2 ];

			normals.push( nx, ny, nz );

			//

			const uvIndex = uvIndices[ i ];
			stride = uvIndex * 2;

			const u = uvsTemp[ stride ];
			const v = uvsTemp[ stride + 1 ];

			uvs.push( u, v );

		}

		geometry.setAttribute( 'position', new Float32BufferAttribute( positions, 3 ) );
		geometry.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );
		geometry.setAttribute( 'uv', new Float32BufferAttribute( uvs, 2 ) );

		// animation

		const morphPositions = [];
		const morphNormals = [];

		for ( let i = 0, l = frames.length; i < l; i ++ ) {

			const frame = frames[ i ];
			const attributeName = frame.name;

			if ( frame.vertices.length > 0 ) {

				const positions = [];

				for ( let j = 0, jl = vertexIndices.length; j < jl; j ++ ) {

					const vertexIndex = vertexIndices[ j ];
					const stride = vertexIndex * 3;

					const x = frame.vertices[ stride ];
					const y = frame.vertices[ stride + 1 ];
					const z = frame.vertices[ stride + 2 ];

					positions.push( x, y, z );

				}

				const positionAttribute = new Float32BufferAttribute( positions, 3 );
				positionAttribute.name = attributeName;

				morphPositions.push( positionAttribute );

			}

			if ( frame.normals.length > 0 ) {

				const normals = [];

				for ( let j = 0, jl = vertexIndices.length; j < jl; j ++ ) {

					const vertexIndex = vertexIndices[ j ];
					const stride = vertexIndex * 3;

					const nx = frame.normals[ stride ];
					const ny = frame.normals[ stride + 1 ];
					const nz = frame.normals[ stride + 2 ];

					normals.push( nx, ny, nz );

				}

				const normalAttribute = new Float32BufferAttribute( normals, 3 );
				normalAttribute.name = attributeName;

				morphNormals.push( normalAttribute );

			}

		}

		geometry.morphAttributes.position = morphPositions;
		geometry.morphAttributes.normal = morphNormals;
		geometry.morphTargetsRelative = false;

		geometry.animations = AnimationClip.CreateClipsFromMorphTargetSequences( frames, 10, false );

		return geometry;

	}
```
</details>


---

## Classes

### `MD2Loader`

<details><summary>Class Code</summary>

```ts
class MD2Loader extends Loader {

	/**
	 * Constructs a new MD2 loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Starts loading from the given URL and passes the loaded MD2 asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(BufferGeometry)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} [onProgress] - Executed while the loading is in progress.
	 * @param {onErrorCallback} [onError] - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( buffer ) {

			try {

				onLoad( scope.parse( buffer ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}

	/**
	 * Parses the given MD2 data and returns a geometry.
	 *
	 * @param {ArrayBuffer} buffer - The raw MD2 data as an array buffer.
	 * @return {BufferGeometry} The parsed geometry data.
	 */
	parse( buffer ) {

		const data = new DataView( buffer );

		// http://tfc.duke.free.fr/coding/md2-specs-en.html

		const header = {};
		const headerNames = [
			'ident', 'version',
			'skinwidth', 'skinheight',
			'framesize',
			'num_skins', 'num_vertices', 'num_st', 'num_tris', 'num_glcmds', 'num_frames',
			'offset_skins', 'offset_st', 'offset_tris', 'offset_frames', 'offset_glcmds', 'offset_end'
		];

		for ( let i = 0; i < headerNames.length; i ++ ) {

			header[ headerNames[ i ] ] = data.getInt32( i * 4, true );

		}

		if ( header.ident !== 844121161 || header.version !== 8 ) {

			console.error( 'Not a valid MD2 file' );
			return;

		}

		if ( header.offset_end !== data.byteLength ) {

			console.error( 'Corrupted MD2 file' );
			return;

		}

		//

		const geometry = new BufferGeometry();

		// uvs

		const uvsTemp = [];
		let offset = header.offset_st;

		for ( let i = 0, l = header.num_st; i < l; i ++ ) {

			const u = data.getInt16( offset + 0, true );
			const v = data.getInt16( offset + 2, true );

			uvsTemp.push( u / header.skinwidth, 1 - ( v / header.skinheight ) );

			offset += 4;

		}

		// triangles

		offset = header.offset_tris;

		const vertexIndices = [];
		const uvIndices = [];

		for ( let i = 0, l = header.num_tris; i < l; i ++ ) {

			vertexIndices.push(
				data.getUint16( offset + 0, true ),
				data.getUint16( offset + 2, true ),
				data.getUint16( offset + 4, true )
			);

			uvIndices.push(
				data.getUint16( offset + 6, true ),
				data.getUint16( offset + 8, true ),
				data.getUint16( offset + 10, true )
			);

			offset += 12;

		}

		// frames

		const translation = new Vector3();
		const scale = new Vector3();

		const frames = [];

		offset = header.offset_frames;

		for ( let i = 0, l = header.num_frames; i < l; i ++ ) {

			scale.set(
				data.getFloat32( offset + 0, true ),
				data.getFloat32( offset + 4, true ),
				data.getFloat32( offset + 8, true )
			);

			translation.set(
				data.getFloat32( offset + 12, true ),
				data.getFloat32( offset + 16, true ),
				data.getFloat32( offset + 20, true )
			);

			offset += 24;

			const string = [];

			for ( let j = 0; j < 16; j ++ ) {

				const character = data.getUint8( offset + j );
				if ( character === 0 ) break;

				string[ j ] = character;

			}

			const frame = {
				name: String.fromCharCode.apply( null, string ),
				vertices: [],
				normals: []
			};

			offset += 16;

			for ( let j = 0; j < header.num_vertices; j ++ ) {

				let x = data.getUint8( offset ++ );
				let y = data.getUint8( offset ++ );
				let z = data.getUint8( offset ++ );
				const n = _normalData[ data.getUint8( offset ++ ) ];

				x = x * scale.x + translation.x;
				y = y * scale.y + translation.y;
				z = z * scale.z + translation.z;

				frame.vertices.push( x, z, y ); // convert to Y-up
				frame.normals.push( n[ 0 ], n[ 2 ], n[ 1 ] ); // convert to Y-up

			}

			frames.push( frame );

		}

		// static

		const positions = [];
		const normals = [];
		const uvs = [];

		const verticesTemp = frames[ 0 ].vertices;
		const normalsTemp = frames[ 0 ].normals;

		for ( let i = 0, l = vertexIndices.length; i < l; i ++ ) {

			const vertexIndex = vertexIndices[ i ];
			let stride = vertexIndex * 3;

			//

			const x = verticesTemp[ stride ];
			const y = verticesTemp[ stride + 1 ];
			const z = verticesTemp[ stride + 2 ];

			positions.push( x, y, z );

			//

			const nx = normalsTemp[ stride ];
			const ny = normalsTemp[ stride + 1 ];
			const nz = normalsTemp[ stride + 2 ];

			normals.push( nx, ny, nz );

			//

			const uvIndex = uvIndices[ i ];
			stride = uvIndex * 2;

			const u = uvsTemp[ stride ];
			const v = uvsTemp[ stride + 1 ];

			uvs.push( u, v );

		}

		geometry.setAttribute( 'position', new Float32BufferAttribute( positions, 3 ) );
		geometry.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );
		geometry.setAttribute( 'uv', new Float32BufferAttribute( uvs, 2 ) );

		// animation

		const morphPositions = [];
		const morphNormals = [];

		for ( let i = 0, l = frames.length; i < l; i ++ ) {

			const frame = frames[ i ];
			const attributeName = frame.name;

			if ( frame.vertices.length > 0 ) {

				const positions = [];

				for ( let j = 0, jl = vertexIndices.length; j < jl; j ++ ) {

					const vertexIndex = vertexIndices[ j ];
					const stride = vertexIndex * 3;

					const x = frame.vertices[ stride ];
					const y = frame.vertices[ stride + 1 ];
					const z = frame.vertices[ stride + 2 ];

					positions.push( x, y, z );

				}

				const positionAttribute = new Float32BufferAttribute( positions, 3 );
				positionAttribute.name = attributeName;

				morphPositions.push( positionAttribute );

			}

			if ( frame.normals.length > 0 ) {

				const normals = [];

				for ( let j = 0, jl = vertexIndices.length; j < jl; j ++ ) {

					const vertexIndex = vertexIndices[ j ];
					const stride = vertexIndex * 3;

					const nx = frame.normals[ stride ];
					const ny = frame.normals[ stride + 1 ];
					const nz = frame.normals[ stride + 2 ];

					normals.push( nx, ny, nz );

				}

				const normalAttribute = new Float32BufferAttribute( normals, 3 );
				normalAttribute.name = attributeName;

				morphNormals.push( normalAttribute );

			}

		}

		geometry.morphAttributes.position = morphPositions;
		geometry.morphAttributes.normal = morphNormals;
		geometry.morphTargetsRelative = false;

		geometry.animations = AnimationClip.CreateClipsFromMorphTargetSequences( frames, 10, false );

		return geometry;

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: BufferGeometry) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( buffer ) {

			try {

				onLoad( scope.parse( buffer ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

##### `parse(buffer: ArrayBuffer): BufferGeometry`

<details><summary>Code</summary>

```ts
parse( buffer ) {

		const data = new DataView( buffer );

		// http://tfc.duke.free.fr/coding/md2-specs-en.html

		const header = {};
		const headerNames = [
			'ident', 'version',
			'skinwidth', 'skinheight',
			'framesize',
			'num_skins', 'num_vertices', 'num_st', 'num_tris', 'num_glcmds', 'num_frames',
			'offset_skins', 'offset_st', 'offset_tris', 'offset_frames', 'offset_glcmds', 'offset_end'
		];

		for ( let i = 0; i < headerNames.length; i ++ ) {

			header[ headerNames[ i ] ] = data.getInt32( i * 4, true );

		}

		if ( header.ident !== 844121161 || header.version !== 8 ) {

			console.error( 'Not a valid MD2 file' );
			return;

		}

		if ( header.offset_end !== data.byteLength ) {

			console.error( 'Corrupted MD2 file' );
			return;

		}

		//

		const geometry = new BufferGeometry();

		// uvs

		const uvsTemp = [];
		let offset = header.offset_st;

		for ( let i = 0, l = header.num_st; i < l; i ++ ) {

			const u = data.getInt16( offset + 0, true );
			const v = data.getInt16( offset + 2, true );

			uvsTemp.push( u / header.skinwidth, 1 - ( v / header.skinheight ) );

			offset += 4;

		}

		// triangles

		offset = header.offset_tris;

		const vertexIndices = [];
		const uvIndices = [];

		for ( let i = 0, l = header.num_tris; i < l; i ++ ) {

			vertexIndices.push(
				data.getUint16( offset + 0, true ),
				data.getUint16( offset + 2, true ),
				data.getUint16( offset + 4, true )
			);

			uvIndices.push(
				data.getUint16( offset + 6, true ),
				data.getUint16( offset + 8, true ),
				data.getUint16( offset + 10, true )
			);

			offset += 12;

		}

		// frames

		const translation = new Vector3();
		const scale = new Vector3();

		const frames = [];

		offset = header.offset_frames;

		for ( let i = 0, l = header.num_frames; i < l; i ++ ) {

			scale.set(
				data.getFloat32( offset + 0, true ),
				data.getFloat32( offset + 4, true ),
				data.getFloat32( offset + 8, true )
			);

			translation.set(
				data.getFloat32( offset + 12, true ),
				data.getFloat32( offset + 16, true ),
				data.getFloat32( offset + 20, true )
			);

			offset += 24;

			const string = [];

			for ( let j = 0; j < 16; j ++ ) {

				const character = data.getUint8( offset + j );
				if ( character === 0 ) break;

				string[ j ] = character;

			}

			const frame = {
				name: String.fromCharCode.apply( null, string ),
				vertices: [],
				normals: []
			};

			offset += 16;

			for ( let j = 0; j < header.num_vertices; j ++ ) {

				let x = data.getUint8( offset ++ );
				let y = data.getUint8( offset ++ );
				let z = data.getUint8( offset ++ );
				const n = _normalData[ data.getUint8( offset ++ ) ];

				x = x * scale.x + translation.x;
				y = y * scale.y + translation.y;
				z = z * scale.z + translation.z;

				frame.vertices.push( x, z, y ); // convert to Y-up
				frame.normals.push( n[ 0 ], n[ 2 ], n[ 1 ] ); // convert to Y-up

			}

			frames.push( frame );

		}

		// static

		const positions = [];
		const normals = [];
		const uvs = [];

		const verticesTemp = frames[ 0 ].vertices;
		const normalsTemp = frames[ 0 ].normals;

		for ( let i = 0, l = vertexIndices.length; i < l; i ++ ) {

			const vertexIndex = vertexIndices[ i ];
			let stride = vertexIndex * 3;

			//

			const x = verticesTemp[ stride ];
			const y = verticesTemp[ stride + 1 ];
			const z = verticesTemp[ stride + 2 ];

			positions.push( x, y, z );

			//

			const nx = normalsTemp[ stride ];
			const ny = normalsTemp[ stride + 1 ];
			const nz = normalsTemp[ stride + 2 ];

			normals.push( nx, ny, nz );

			//

			const uvIndex = uvIndices[ i ];
			stride = uvIndex * 2;

			const u = uvsTemp[ stride ];
			const v = uvsTemp[ stride + 1 ];

			uvs.push( u, v );

		}

		geometry.setAttribute( 'position', new Float32BufferAttribute( positions, 3 ) );
		geometry.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );
		geometry.setAttribute( 'uv', new Float32BufferAttribute( uvs, 2 ) );

		// animation

		const morphPositions = [];
		const morphNormals = [];

		for ( let i = 0, l = frames.length; i < l; i ++ ) {

			const frame = frames[ i ];
			const attributeName = frame.name;

			if ( frame.vertices.length > 0 ) {

				const positions = [];

				for ( let j = 0, jl = vertexIndices.length; j < jl; j ++ ) {

					const vertexIndex = vertexIndices[ j ];
					const stride = vertexIndex * 3;

					const x = frame.vertices[ stride ];
					const y = frame.vertices[ stride + 1 ];
					const z = frame.vertices[ stride + 2 ];

					positions.push( x, y, z );

				}

				const positionAttribute = new Float32BufferAttribute( positions, 3 );
				positionAttribute.name = attributeName;

				morphPositions.push( positionAttribute );

			}

			if ( frame.normals.length > 0 ) {

				const normals = [];

				for ( let j = 0, jl = vertexIndices.length; j < jl; j ++ ) {

					const vertexIndex = vertexIndices[ j ];
					const stride = vertexIndex * 3;

					const nx = frame.normals[ stride ];
					const ny = frame.normals[ stride + 1 ];
					const nz = frame.normals[ stride + 2 ];

					normals.push( nx, ny, nz );

				}

				const normalAttribute = new Float32BufferAttribute( normals, 3 );
				normalAttribute.name = attributeName;

				morphNormals.push( normalAttribute );

			}

		}

		geometry.morphAttributes.position = morphPositions;
		geometry.morphAttributes.normal = morphNormals;
		geometry.morphTargetsRelative = false;

		geometry.animations = AnimationClip.CreateClipsFromMorphTargetSequences( frames, 10, false );

		return geometry;

	}
```
</details>


---