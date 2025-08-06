[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TDSLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 21 |
| 🧱 Classes | 2 |
| 📦 Imports | 13 |
| 📊 Variables & Constants | 66 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/TDSLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AdditiveBlending` | `three` |
| `BufferGeometry` | `three` |
| `Color` | `three` |
| `DoubleSide` | `three` |
| `FileLoader` | `three` |
| `Float32BufferAttribute` | `three` |
| `Group` | `three` |
| `Loader` | `three` |
| `LoaderUtils` | `three` |
| `Matrix4` | `three` |
| `Mesh` | `three` |
| `MeshPhongMaterial` | `three` |
| `TextureLoader` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `path` | `any` | let/var | `( this.path === '' ) ? LoaderUtils.extractUrlBase( url ) : this.path` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `data` | `DataView<ArrayBuffer>` | let/var | `new DataView( arraybuffer )` | ✗ |
| `chunk` | `any` | let/var | `new Chunk( data, 0, this.debugMessage )` | ✗ |
| `version` | `number` | let/var | `+ next.readDWord()` | ✗ |
| `material` | `any` | let/var | `new MeshPhongMaterial()` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `material` | `any` | let/var | `new MeshPhongMaterial()` | ✗ |
| `mesh` | `any` | let/var | `new Mesh( geometry, material )` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `uvs` | `any[]` | let/var | `[]` | ✗ |
| `values` | `any[]` | let/var | `[]` | ✗ |
| `matrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `inverse` | `any` | let/var | `new Matrix4()` | ✗ |
| `index` | `any[]` | let/var | `[]` | ✗ |
| `materialIndex` | `number` | let/var | `0` | ✗ |
| `start` | `number` | let/var | `0` | ✗ |
| `count` | `number` | let/var | `group.index.length * 3` | ✗ |
| `material` | `any` | let/var | `this.materials[ group.name ]` | ✗ |
| `texture` | `{}` | let/var | `{}` | ✗ |
| `loader` | `any` | let/var | `new TextureLoader( this.manager )` | ✗ |
| `index` | `any[]` | let/var | `[]` | ✗ |
| `color` | `any` | let/var | `new Color()` | ✗ |
| `next` | `Chunk` | let/var | `new Chunk( this.data, this.position, this.debugMessage )` | ✗ |
| `s` | `string` | let/var | `''` | ✗ |
| `M3DMAGIC` | `19789` | let/var | `0x4D4D` | ✗ |
| `MLIBMAGIC` | `15786` | let/var | `0x3DAA` | ✗ |
| `CMAGIC` | `49725` | let/var | `0xC23D` | ✗ |
| `M3D_VERSION` | `2` | let/var | `0x0002` | ✗ |
| `COLOR_F` | `16` | let/var | `0x0010` | ✗ |
| `COLOR_24` | `17` | let/var | `0x0011` | ✗ |
| `LIN_COLOR_24` | `18` | let/var | `0x0012` | ✗ |
| `LIN_COLOR_F` | `19` | let/var | `0x0013` | ✗ |
| `INT_PERCENTAGE` | `48` | let/var | `0x0030` | ✗ |
| `FLOAT_PERCENTAGE` | `49` | let/var | `0x0031` | ✗ |
| `MDATA` | `15677` | let/var | `0x3D3D` | ✗ |
| `MESH_VERSION` | `15678` | let/var | `0x3D3E` | ✗ |
| `MASTER_SCALE` | `256` | let/var | `0x0100` | ✗ |
| `MAT_ENTRY` | `45055` | let/var | `0xAFFF` | ✗ |
| `MAT_NAME` | `40960` | let/var | `0xA000` | ✗ |
| `MAT_AMBIENT` | `40976` | let/var | `0xA010` | ✗ |
| `MAT_DIFFUSE` | `40992` | let/var | `0xA020` | ✗ |
| `MAT_SPECULAR` | `41008` | let/var | `0xA030` | ✗ |
| `MAT_SHININESS` | `41024` | let/var | `0xA040` | ✗ |
| `MAT_TRANSPARENCY` | `41040` | let/var | `0xA050` | ✗ |
| `MAT_TWO_SIDE` | `41089` | let/var | `0xA081` | ✗ |
| `MAT_ADDITIVE` | `41091` | let/var | `0xA083` | ✗ |
| `MAT_WIRE` | `41093` | let/var | `0xA085` | ✗ |
| `MAT_WIRE_SIZE` | `41095` | let/var | `0xA087` | ✗ |
| `MAT_TEXMAP` | `41472` | let/var | `0xA200` | ✗ |
| `MAT_OPACMAP` | `41488` | let/var | `0xA210` | ✗ |
| `MAT_BUMPMAP` | `41520` | let/var | `0xA230` | ✗ |
| `MAT_SPECMAP` | `41476` | let/var | `0xA204` | ✗ |
| `MAT_MAPNAME` | `41728` | let/var | `0xA300` | ✗ |
| `MAT_MAP_USCALE` | `41812` | let/var | `0xA354` | ✗ |
| `MAT_MAP_VSCALE` | `41814` | let/var | `0xA356` | ✗ |
| `MAT_MAP_UOFFSET` | `41816` | let/var | `0xA358` | ✗ |
| `MAT_MAP_VOFFSET` | `41818` | let/var | `0xA35A` | ✗ |
| `NAMED_OBJECT` | `16384` | let/var | `0x4000` | ✗ |
| `N_TRI_OBJECT` | `16640` | let/var | `0x4100` | ✗ |
| `POINT_ARRAY` | `16656` | let/var | `0x4110` | ✗ |
| `FACE_ARRAY` | `16672` | let/var | `0x4120` | ✗ |
| `MSH_MAT_GROUP` | `16688` | let/var | `0x4130` | ✗ |
| `TEX_VERTS` | `16704` | let/var | `0x4140` | ✗ |
| `MESH_MATRIX` | `16736` | let/var | `0x4160` | ✗ |


---

## Functions

### `TDSLoader.load(url: string, onLoad: (arg0: Group) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded 3DS asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Group)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: Group) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `LoaderUtils.extractUrlBase`
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

		const path = ( this.path === '' ) ? LoaderUtils.extractUrlBase( url ) : this.path;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );

		loader.load( url, function ( data ) {

			try {

				onLoad( scope.parse( data, path ) );

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

### `TDSLoader.parse(arraybuffer: ArrayBuffer, path: string): Group`

**JSDoc:**
```typescript
/**
	 * Parses the given 3DS data and returns the resulting data.
	 *
	 * @param {ArrayBuffer} arraybuffer - The raw 3DS data as an array buffer.
	 * @param {string} path - The asset path.
	 * @return {Group} The parsed asset represented as a group.
	 */
```

**Parameters:**

- **`arraybuffer`** `ArrayBuffer`
- **`path`** `string`

**Returns:** `Group`

**Calls:**

- `this.readFile`
- `this.group.add`

<details><summary>Code</summary>

```typescript
parse( arraybuffer, path ) {

		this.group = new Group();
		this.materials = [];
		this.meshes = [];

		this.readFile( arraybuffer, path );

		for ( let i = 0; i < this.meshes.length; i ++ ) {

			this.group.add( this.meshes[ i ] );

		}

		return this.group;

	}
```
</details>

### `TDSLoader.readFile(arraybuffer: ArrayBuffer, path: string): void`

**JSDoc:**
```typescript
/**
	 * Decode file content to read 3ds data.
	 *
	 * @private
	 * @param {ArrayBuffer} arraybuffer - Arraybuffer data to be loaded.
	 * @param {string} path - Path for external resources.
	 */
```

**Parameters:**

- **`arraybuffer`** `ArrayBuffer`
- **`path`** `string`

**Returns:** `void`

**Calls:**

- `chunk.readChunk`
- `next.readDWord`
- `this.debugMessage`
- `this.readMeshData`

<details><summary>Code</summary>

```typescript
readFile( arraybuffer, path ) {

		const data = new DataView( arraybuffer );
		const chunk = new Chunk( data, 0, this.debugMessage );

		if ( chunk.id === MLIBMAGIC || chunk.id === CMAGIC || chunk.id === M3DMAGIC ) {

			let next = chunk.readChunk();

			while ( next ) {

				if ( next.id === M3D_VERSION ) {

					const version = next.readDWord();
					this.debugMessage( '3DS file version: ' + version );

				} else if ( next.id === MDATA ) {

					this.readMeshData( next, path );

				} else {

					this.debugMessage( 'Unknown main chunk: ' + next.hexId );

				}

				next = chunk.readChunk();

			}

		}

		this.debugMessage( 'Parsed ' + this.meshes.length + ' meshes' );

	}
```
</details>

### `TDSLoader.readMeshData(chunk: Chunk, path: string): void`

**JSDoc:**
```typescript
/**
	 * Read mesh data chunk.
	 *
	 * @private
	 * @param {Chunk} chunk - to read mesh from
	 * @param {string} path - Path for external resources.
	 */
```

**Parameters:**

- **`chunk`** `Chunk`
- **`path`** `string`

**Returns:** `void`

**Calls:**

- `chunk.readChunk`
- `next.readDWord`
- `this.debugMessage`
- `next.readFloat`
- `this.group.scale.set`
- `this.readNamedObject`
- `this.readMaterialEntry`

<details><summary>Code</summary>

```typescript
readMeshData( chunk, path ) {

		let next = chunk.readChunk();

		while ( next ) {

			if ( next.id === MESH_VERSION ) {

				const version = + next.readDWord();
				this.debugMessage( 'Mesh Version: ' + version );

			} else if ( next.id === MASTER_SCALE ) {

				const scale = next.readFloat();
				this.debugMessage( 'Master scale: ' + scale );
				this.group.scale.set( scale, scale, scale );

			} else if ( next.id === NAMED_OBJECT ) {

				this.debugMessage( 'Named Object' );
				this.readNamedObject( next );

			} else if ( next.id === MAT_ENTRY ) {

				this.debugMessage( 'Material' );
				this.readMaterialEntry( next, path );

			} else {

				this.debugMessage( 'Unknown MDATA chunk: ' + next.hexId );

			}

			next = chunk.readChunk();

		}

	}
```
</details>

### `TDSLoader.readNamedObject(chunk: Chunk): void`

**JSDoc:**
```typescript
/**
	 * Read named object chunk.
	 *
	 * @private
	 * @param {Chunk} chunk - Chunk in use.
	 */
```

**Parameters:**

- **`chunk`** `Chunk`

**Returns:** `void`

**Calls:**

- `chunk.readString`
- `chunk.readChunk`
- `this.readMesh`
- `this.meshes.push`
- `this.debugMessage`

<details><summary>Code</summary>

```typescript
readNamedObject( chunk ) {

		const name = chunk.readString();

		let next = chunk.readChunk();
		while ( next ) {

			if ( next.id === N_TRI_OBJECT ) {

				const mesh = this.readMesh( next );
				mesh.name = name;
				this.meshes.push( mesh );

			} else {

				this.debugMessage( 'Unknown named object chunk: ' + next.hexId );

			}

			next = chunk.readChunk( );

		}

	}
```
</details>

### `TDSLoader.readMaterialEntry(chunk: Chunk, path: string): void`

**JSDoc:**
```typescript
/**
	 * Read material data chunk and add it to the material list.
	 *
	 * @private
	 * @param {Chunk} chunk - Chunk in use.
	 * @param {string} path - Path for external resources.
	 */
```

**Parameters:**

- **`chunk`** `Chunk`
- **`path`** `string`

**Returns:** `void`

**Calls:**

- `chunk.readChunk`
- `next.readString`
- `this.debugMessage`
- `next.readByte`
- `this.readColor`
- `this.readPercentage`
- `this.readMap`

<details><summary>Code</summary>

```typescript
readMaterialEntry( chunk, path ) {

		let next = chunk.readChunk();
		const material = new MeshPhongMaterial();

		while ( next ) {

			if ( next.id === MAT_NAME ) {

				material.name = next.readString();
				this.debugMessage( '   Name: ' + material.name );

			} else if ( next.id === MAT_WIRE ) {

				this.debugMessage( '   Wireframe' );
				material.wireframe = true;

			} else if ( next.id === MAT_WIRE_SIZE ) {

				const value = next.readByte();
				material.wireframeLinewidth = value;
				this.debugMessage( '   Wireframe Thickness: ' + value );

			} else if ( next.id === MAT_TWO_SIDE ) {

				material.side = DoubleSide;
				this.debugMessage( '   DoubleSided' );

			} else if ( next.id === MAT_ADDITIVE ) {

				this.debugMessage( '   Additive Blending' );
				material.blending = AdditiveBlending;

			} else if ( next.id === MAT_DIFFUSE ) {

				this.debugMessage( '   Diffuse Color' );
				material.color = this.readColor( next );

			} else if ( next.id === MAT_SPECULAR ) {

				this.debugMessage( '   Specular Color' );
				material.specular = this.readColor( next );

			} else if ( next.id === MAT_AMBIENT ) {

				this.debugMessage( '   Ambient color' );
				material.color = this.readColor( next );

			} else if ( next.id === MAT_SHININESS ) {

				const shininess = this.readPercentage( next );
				material.shininess = shininess * 100;
				this.debugMessage( '   Shininess : ' + shininess );

			} else if ( next.id === MAT_TRANSPARENCY ) {

				const transparency = this.readPercentage( next );
				material.opacity = 1 - transparency;
				this.debugMessage( '  Transparency : ' + transparency );
				material.transparent = material.opacity < 1 ? true : false;

			} else if ( next.id === MAT_TEXMAP ) {

				this.debugMessage( '   ColorMap' );
				material.map = this.readMap( next, path );

			} else if ( next.id === MAT_BUMPMAP ) {

				this.debugMessage( '   BumpMap' );
				material.bumpMap = this.readMap( next, path );

			} else if ( next.id === MAT_OPACMAP ) {

				this.debugMessage( '   OpacityMap' );
				material.alphaMap = this.readMap( next, path );

			} else if ( next.id === MAT_SPECMAP ) {

				this.debugMessage( '   SpecularMap' );
				material.specularMap = this.readMap( next, path );

			} else {

				this.debugMessage( '   Unknown material chunk: ' + next.hexId );

			}

			next = chunk.readChunk();

		}

		this.materials[ material.name ] = material;

	}
```
</details>

### `TDSLoader.readMesh(chunk: Chunk): Mesh`

**JSDoc:**
```typescript
/**
	 * Read mesh data chunk.
	 *
	 * @private
	 * @param {Chunk} chunk - Chunk in use.
	 * @return {Mesh} - The parsed mesh.
	 */
```

**Parameters:**

- **`chunk`** `Chunk`

**Returns:** `Mesh`

**Calls:**

- `chunk.readChunk`
- `next.readWord`
- `this.debugMessage`
- `vertices.push`
- `next.readFloat`
- `geometry.setAttribute`
- `this.readFaceArray`
- `uvs.push`
- `matrix.transpose`
- `inverse.copy( matrix ).invert`
- `geometry.applyMatrix4`
- `matrix.decompose`
- `geometry.computeVertexNormals`

**Internal Comments:**
```
//BufferGeometry (x4)
//X Line (x5)
//Y Line (x5)
//Z Line (x5)
//W Line (x5)
```

<details><summary>Code</summary>

```typescript
readMesh( chunk ) {

		let next = chunk.readChunk( );

		const geometry = new BufferGeometry();

		const material = new MeshPhongMaterial();
		const mesh = new Mesh( geometry, material );
		mesh.name = 'mesh';

		while ( next ) {

			if ( next.id === POINT_ARRAY ) {

				const points = next.readWord( );

				this.debugMessage( '   Vertex: ' + points );

				//BufferGeometry

				const vertices = [];

				for ( let i = 0; i < points; i ++ )		{

					vertices.push( next.readFloat( ) );
					vertices.push( next.readFloat( ) );
					vertices.push( next.readFloat( ) );

				}

				geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );

			} else if ( next.id === FACE_ARRAY ) {

				this.readFaceArray( next, mesh );

			} else if ( next.id === TEX_VERTS ) {

				const texels = next.readWord( );

				this.debugMessage( '   UV: ' + texels );

				//BufferGeometry

				const uvs = [];

				for ( let i = 0; i < texels; i ++ ) {

					uvs.push( next.readFloat( ) );
					uvs.push( next.readFloat( ) );

				}

				geometry.setAttribute( 'uv', new Float32BufferAttribute( uvs, 2 ) );


			} else if ( next.id === MESH_MATRIX ) {

				this.debugMessage( '   Transformation Matrix (TODO)' );

				const values = [];
				for ( let i = 0; i < 12; i ++ ) {

					values[ i ] = next.readFloat( );

				}

				const matrix = new Matrix4();

				//X Line
				matrix.elements[ 0 ] = values[ 0 ];
				matrix.elements[ 1 ] = values[ 6 ];
				matrix.elements[ 2 ] = values[ 3 ];
				matrix.elements[ 3 ] = values[ 9 ];

				//Y Line
				matrix.elements[ 4 ] = values[ 2 ];
				matrix.elements[ 5 ] = values[ 8 ];
				matrix.elements[ 6 ] = values[ 5 ];
				matrix.elements[ 7 ] = values[ 11 ];

				//Z Line
				matrix.elements[ 8 ] = values[ 1 ];
				matrix.elements[ 9 ] = values[ 7 ];
				matrix.elements[ 10 ] = values[ 4 ];
				matrix.elements[ 11 ] = values[ 10 ];

				//W Line
				matrix.elements[ 12 ] = 0;
				matrix.elements[ 13 ] = 0;
				matrix.elements[ 14 ] = 0;
				matrix.elements[ 15 ] = 1;

				matrix.transpose();

				const inverse = new Matrix4();
				inverse.copy( matrix ).invert();
				geometry.applyMatrix4( inverse );

				matrix.decompose( mesh.position, mesh.quaternion, mesh.scale );

			} else {

				this.debugMessage( '   Unknown mesh chunk: ' + next.hexId );

			}

			next = chunk.readChunk( );

		}

		geometry.computeVertexNormals();

		return mesh;

	}
```
</details>

### `TDSLoader.readFaceArray(chunk: Chunk, mesh: Mesh): void`

**JSDoc:**
```typescript
/**
	 * Read face array data chunk.
	 *
	 * @private
	 * @param {Chunk} chunk - Chunk in use.
	 * @param {Mesh} mesh - Mesh to be filled with the data read.
	 */
```

**Parameters:**

- **`chunk`** `Chunk`
- **`mesh`** `Mesh`

**Returns:** `void`

**Calls:**

- `chunk.readWord`
- `this.debugMessage`
- `index.push`
- `mesh.geometry.setIndex`
- `chunk.readChunk`
- `this.readMaterialGroup`
- `mesh.geometry.addGroup`
- `Array.isArray`
- `mesh.material.push`

**Internal Comments:**
```
//The rest of the FACE_ARRAY chunk is subchunks (x2)
```

<details><summary>Code</summary>

```typescript
readFaceArray( chunk, mesh ) {

		const faces = chunk.readWord( );

		this.debugMessage( '   Faces: ' + faces );

		const index = [];

		for ( let i = 0; i < faces; ++ i ) {

			index.push( chunk.readWord( ), chunk.readWord( ), chunk.readWord( ) );

			chunk.readWord( ); // visibility

		}

		mesh.geometry.setIndex( index );

		//The rest of the FACE_ARRAY chunk is subchunks

		let materialIndex = 0;
		let start = 0;

		while ( ! chunk.endOfChunk ) {

			const subchunk = chunk.readChunk( );

			if ( subchunk.id === MSH_MAT_GROUP ) {

				this.debugMessage( '      Material Group' );

				const group = this.readMaterialGroup( subchunk );
				const count = group.index.length * 3; // assuming successive indices

				mesh.geometry.addGroup( start, count, materialIndex );

				start += count;
				materialIndex ++;

				const material = this.materials[ group.name ];

				if ( Array.isArray( mesh.material ) === false ) mesh.material = [];

				if ( material !== undefined )	{

					mesh.material.push( material );

				}

			} else {

				this.debugMessage( '      Unknown face array chunk: ' + subchunk.hexId );

			}

		}

		if ( mesh.material.length === 1 ) mesh.material = mesh.material[ 0 ]; // for backwards compatibility

	}
```
</details>

### `TDSLoader.readMap(chunk: Chunk, path: string): Texture`

**JSDoc:**
```typescript
/**
	 * Read texture map data chunk.
	 *
	 * @private
	 * @param {Chunk} chunk - Chunk in use.
	 * @param {string} path - Path for external resources.
	 * @return {Texture} Texture read from this data chunk.
	 */
```

**Parameters:**

- **`chunk`** `Chunk`
- **`path`** `string`

**Returns:** `Texture`

**Calls:**

- `chunk.readChunk`
- `loader.setPath( this.resourcePath || path ).setCrossOrigin`
- `next.readString`
- `loader.load`
- `this.debugMessage`
- `next.readFloat`

<details><summary>Code</summary>

```typescript
readMap( chunk, path ) {

		let next = chunk.readChunk( );
		let texture = {};

		const loader = new TextureLoader( this.manager );
		loader.setPath( this.resourcePath || path ).setCrossOrigin( this.crossOrigin );

		while ( next ) {

			if ( next.id === MAT_MAPNAME ) {

				const name = next.readString();
				texture = loader.load( name );

				this.debugMessage( '      File: ' + path + name );

			} else if ( next.id === MAT_MAP_UOFFSET ) {

				texture.offset.x = next.readFloat( );
				this.debugMessage( '      OffsetX: ' + texture.offset.x );

			} else if ( next.id === MAT_MAP_VOFFSET ) {

				texture.offset.y = next.readFloat( );
				this.debugMessage( '      OffsetY: ' + texture.offset.y );

			} else if ( next.id === MAT_MAP_USCALE ) {

				texture.repeat.x = next.readFloat( );
				this.debugMessage( '      RepeatX: ' + texture.repeat.x );

			} else if ( next.id === MAT_MAP_VSCALE ) {

				texture.repeat.y = next.readFloat( );
				this.debugMessage( '      RepeatY: ' + texture.repeat.y );

			} else {

				this.debugMessage( '      Unknown map chunk: ' + next.hexId );

			}

			next = chunk.readChunk( );

		}

		return texture;

	}
```
</details>

### `TDSLoader.readMaterialGroup(chunk: Chunk): any`

**JSDoc:**
```typescript
/**
	 * Read material group data chunk.
	 *
	 * @private
	 * @param {Chunk} chunk - Chunk in use.
	 * @return {Object} Object with name and index of the object.
	 */
```

**Parameters:**

- **`chunk`** `Chunk`

**Returns:** `any`

**Calls:**

- `chunk.readString`
- `chunk.readWord`
- `this.debugMessage`
- `index.push`

<details><summary>Code</summary>

```typescript
readMaterialGroup( chunk ) {

		const name = chunk.readString();
		const numFaces = chunk.readWord();

		this.debugMessage( '         Name: ' + name );
		this.debugMessage( '         Faces: ' + numFaces );

		const index = [];
		for ( let i = 0; i < numFaces; ++ i ) {

			index.push( chunk.readWord( ) );

		}

		return { name: name, index: index };

	}
```
</details>

### `TDSLoader.readColor(chunk: Chunk): Color`

**JSDoc:**
```typescript
/**
	 * Read a color value.
	 *
	 * @private
	 * @param {Chunk} chunk - Chunk.
	 * @return {Color} Color value read.
	 */
```

**Parameters:**

- **`chunk`** `Chunk`

**Returns:** `Color`

**Calls:**

- `chunk.readChunk`
- `subChunk.readByte`
- `color.setRGB`
- `this.debugMessage`
- `subChunk.readFloat`

<details><summary>Code</summary>

```typescript
readColor( chunk ) {

		const subChunk = chunk.readChunk( );
		const color = new Color();

		if ( subChunk.id === COLOR_24 || subChunk.id === LIN_COLOR_24 ) {

			const r = subChunk.readByte( );
			const g = subChunk.readByte( );
			const b = subChunk.readByte( );

			color.setRGB( r / 255, g / 255, b / 255 );

			this.debugMessage( '      Color: ' + color.r + ', ' + color.g + ', ' + color.b );

		}	else if ( subChunk.id === COLOR_F || subChunk.id === LIN_COLOR_F ) {

			const r = subChunk.readFloat( );
			const g = subChunk.readFloat( );
			const b = subChunk.readFloat( );

			color.setRGB( r, g, b );

			this.debugMessage( '      Color: ' + color.r + ', ' + color.g + ', ' + color.b );

		}	else {

			this.debugMessage( '      Unknown color chunk: ' + subChunk.hexId );

		}

		return color;

	}
```
</details>

### `TDSLoader.readPercentage(chunk: Chunk): number`

**JSDoc:**
```typescript
/**
	 * Read percentage value.
	 *
	 * @private
	 * @param {Chunk} chunk - Chunk to read data from.
	 * @return {number} Data read from the dataview.
	 */
```

**Parameters:**

- **`chunk`** `Chunk`

**Returns:** `number`

**Calls:**

- `chunk.readChunk`
- `subChunk.readShort`
- `subChunk.readFloat`
- `this.debugMessage`

<details><summary>Code</summary>

```typescript
readPercentage( chunk ) {

		const subChunk = chunk.readChunk( );

		switch ( subChunk.id ) {

			case INT_PERCENTAGE:
				return ( subChunk.readShort( ) / 100 );
				break;

			case FLOAT_PERCENTAGE:
				return subChunk.readFloat( );
				break;

			default:
				this.debugMessage( '      Unknown percentage chunk: ' + subChunk.hexId );
				return 0;

		}

	}
```
</details>

### `TDSLoader.debugMessage(message: any): void`

**JSDoc:**
```typescript
/**
	 * Print debug message to the console.
	 *
	 * Is controlled by a flag to show or hide debug messages.
	 *
	 * @private
	 * @param {Object} message - Debug message to print to the console.
	 */
```

**Parameters:**

- **`message`** `any`

**Returns:** `void`

**Calls:**

- `console.log`

<details><summary>Code</summary>

```typescript
debugMessage( message ) {

		if ( this.debug ) {

			console.log( message );

		}

	}
```
</details>

### `Chunk.readChunk(): Chunk`

**JSDoc:**
```typescript
/**
	 * Reads a sub cchunk.
	 *
	 * @private
	 * @return {Chunk | null} next sub chunk.
	 */
```

**Returns:** `Chunk`

**Calls:**

- `this.debugMessage`

<details><summary>Code</summary>

```typescript
readChunk() {

		if ( this.endOfChunk ) {

			return null;

		}

		try {

			const next = new Chunk( this.data, this.position, this.debugMessage );
			this.position += next.size;
			return next;

		}	catch ( e ) {

			this.debugMessage( 'Unable to read chunk at ' + this.position );
			return null;

		}

	}
```
</details>

### `Chunk.readByte(): number`

**JSDoc:**
```typescript
/**
	 * Read byte value.
	 *
	 * @private
	 * @return {number} Data read from the dataview.
	 */
```

**Returns:** `number`

**Calls:**

- `this.data.getUint8`

<details><summary>Code</summary>

```typescript
readByte() {

		const v = this.data.getUint8( this.position, true );
		this.position += 1;
		return v;

	}
```
</details>

### `Chunk.readFloat(): number`

**JSDoc:**
```typescript
/**
	 * Read 32 bit float value.
	 *
	 * @private
	 * @return {number} Data read from the dataview.
	 */
```

**Returns:** `number`

**Calls:**

- `this.data.getFloat32`
- `this.debugMessage`

<details><summary>Code</summary>

```typescript
readFloat() {

		try {

			const v = this.data.getFloat32( this.position, true );
			this.position += 4;
			return v;

		}	catch ( e ) {

			this.debugMessage( e + ' ' + this.position + ' ' + this.data.byteLength );
			return 0;

		}

	}
```
</details>

### `Chunk.readInt(): number`

**JSDoc:**
```typescript
/**
	 * Read 32 bit signed integer value.
	 *
	 * @private
	 * @return {number} Data read from the dataview.
	 */
```

**Returns:** `number`

**Calls:**

- `this.data.getInt32`

<details><summary>Code</summary>

```typescript
readInt() {

		const v = this.data.getInt32( this.position, true );
		this.position += 4;
		return v;

	}
```
</details>

### `Chunk.readShort(): number`

**JSDoc:**
```typescript
/**
	 * Read 16 bit signed integer value.
	 *
	 * @private
	 * @return {number} Data read from the dataview.
	 */
```

**Returns:** `number`

**Calls:**

- `this.data.getInt16`

<details><summary>Code</summary>

```typescript
readShort() {

		const v = this.data.getInt16( this.position, true );
		this.position += 2;
		return v;

	}
```
</details>

### `Chunk.readDWord(): number`

**JSDoc:**
```typescript
/**
	 * Read 64 bit unsigned integer value.
	 *
	 * @private
	 * @return {number} Data read from the dataview.
	 */
```

**Returns:** `number`

**Calls:**

- `this.data.getUint32`

<details><summary>Code</summary>

```typescript
readDWord() {

		const v = this.data.getUint32( this.position, true );
		this.position += 4;
		return v;

	}
```
</details>

### `Chunk.readWord(): number`

**JSDoc:**
```typescript
/**
	 * Read 32 bit unsigned integer value.
	 *
	 * @private
	 * @return {number} Data read from the dataview.
	 */
```

**Returns:** `number`

**Calls:**

- `this.data.getUint16`

<details><summary>Code</summary>

```typescript
readWord() {

		const v = this.data.getUint16( this.position, true );
		this.position += 2;
		return v;

	}
```
</details>

### `Chunk.readString(): string`

**JSDoc:**
```typescript
/**
	 * Read NULL terminated ASCII string value from chunk-pos.
	 *
	 * @private
	 * @return {string} Data read from the dataview.
	 */
```

**Returns:** `string`

**Calls:**

- `this.readByte`
- `String.fromCharCode`

<details><summary>Code</summary>

```typescript
readString() {

		let s = '';
		let c = this.readByte();
		while ( c ) {

			s += String.fromCharCode( c );
			c = this.readByte();

		}

		return s;

	}
```
</details>


---

## Classes

### `TDSLoader`

<details><summary>Class Code</summary>

```ts
class TDSLoader extends Loader {

	/**
	 * Constructs a new 3DS loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		/**
		 * Whether debug mode should be enabled or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.debug = false;

		// internals

		this.group = null;

		this.materials = [];
		this.meshes = [];

	}

	/**
	 * Starts loading from the given URL and passes the loaded 3DS asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Group)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const path = ( this.path === '' ) ? LoaderUtils.extractUrlBase( url ) : this.path;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );

		loader.load( url, function ( data ) {

			try {

				onLoad( scope.parse( data, path ) );

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
	 * Parses the given 3DS data and returns the resulting data.
	 *
	 * @param {ArrayBuffer} arraybuffer - The raw 3DS data as an array buffer.
	 * @param {string} path - The asset path.
	 * @return {Group} The parsed asset represented as a group.
	 */
	parse( arraybuffer, path ) {

		this.group = new Group();
		this.materials = [];
		this.meshes = [];

		this.readFile( arraybuffer, path );

		for ( let i = 0; i < this.meshes.length; i ++ ) {

			this.group.add( this.meshes[ i ] );

		}

		return this.group;

	}

	/**
	 * Decode file content to read 3ds data.
	 *
	 * @private
	 * @param {ArrayBuffer} arraybuffer - Arraybuffer data to be loaded.
	 * @param {string} path - Path for external resources.
	 */
	readFile( arraybuffer, path ) {

		const data = new DataView( arraybuffer );
		const chunk = new Chunk( data, 0, this.debugMessage );

		if ( chunk.id === MLIBMAGIC || chunk.id === CMAGIC || chunk.id === M3DMAGIC ) {

			let next = chunk.readChunk();

			while ( next ) {

				if ( next.id === M3D_VERSION ) {

					const version = next.readDWord();
					this.debugMessage( '3DS file version: ' + version );

				} else if ( next.id === MDATA ) {

					this.readMeshData( next, path );

				} else {

					this.debugMessage( 'Unknown main chunk: ' + next.hexId );

				}

				next = chunk.readChunk();

			}

		}

		this.debugMessage( 'Parsed ' + this.meshes.length + ' meshes' );

	}

	/**
	 * Read mesh data chunk.
	 *
	 * @private
	 * @param {Chunk} chunk - to read mesh from
	 * @param {string} path - Path for external resources.
	 */
	readMeshData( chunk, path ) {

		let next = chunk.readChunk();

		while ( next ) {

			if ( next.id === MESH_VERSION ) {

				const version = + next.readDWord();
				this.debugMessage( 'Mesh Version: ' + version );

			} else if ( next.id === MASTER_SCALE ) {

				const scale = next.readFloat();
				this.debugMessage( 'Master scale: ' + scale );
				this.group.scale.set( scale, scale, scale );

			} else if ( next.id === NAMED_OBJECT ) {

				this.debugMessage( 'Named Object' );
				this.readNamedObject( next );

			} else if ( next.id === MAT_ENTRY ) {

				this.debugMessage( 'Material' );
				this.readMaterialEntry( next, path );

			} else {

				this.debugMessage( 'Unknown MDATA chunk: ' + next.hexId );

			}

			next = chunk.readChunk();

		}

	}

	/**
	 * Read named object chunk.
	 *
	 * @private
	 * @param {Chunk} chunk - Chunk in use.
	 */
	readNamedObject( chunk ) {

		const name = chunk.readString();

		let next = chunk.readChunk();
		while ( next ) {

			if ( next.id === N_TRI_OBJECT ) {

				const mesh = this.readMesh( next );
				mesh.name = name;
				this.meshes.push( mesh );

			} else {

				this.debugMessage( 'Unknown named object chunk: ' + next.hexId );

			}

			next = chunk.readChunk( );

		}

	}

	/**
	 * Read material data chunk and add it to the material list.
	 *
	 * @private
	 * @param {Chunk} chunk - Chunk in use.
	 * @param {string} path - Path for external resources.
	 */
	readMaterialEntry( chunk, path ) {

		let next = chunk.readChunk();
		const material = new MeshPhongMaterial();

		while ( next ) {

			if ( next.id === MAT_NAME ) {

				material.name = next.readString();
				this.debugMessage( '   Name: ' + material.name );

			} else if ( next.id === MAT_WIRE ) {

				this.debugMessage( '   Wireframe' );
				material.wireframe = true;

			} else if ( next.id === MAT_WIRE_SIZE ) {

				const value = next.readByte();
				material.wireframeLinewidth = value;
				this.debugMessage( '   Wireframe Thickness: ' + value );

			} else if ( next.id === MAT_TWO_SIDE ) {

				material.side = DoubleSide;
				this.debugMessage( '   DoubleSided' );

			} else if ( next.id === MAT_ADDITIVE ) {

				this.debugMessage( '   Additive Blending' );
				material.blending = AdditiveBlending;

			} else if ( next.id === MAT_DIFFUSE ) {

				this.debugMessage( '   Diffuse Color' );
				material.color = this.readColor( next );

			} else if ( next.id === MAT_SPECULAR ) {

				this.debugMessage( '   Specular Color' );
				material.specular = this.readColor( next );

			} else if ( next.id === MAT_AMBIENT ) {

				this.debugMessage( '   Ambient color' );
				material.color = this.readColor( next );

			} else if ( next.id === MAT_SHININESS ) {

				const shininess = this.readPercentage( next );
				material.shininess = shininess * 100;
				this.debugMessage( '   Shininess : ' + shininess );

			} else if ( next.id === MAT_TRANSPARENCY ) {

				const transparency = this.readPercentage( next );
				material.opacity = 1 - transparency;
				this.debugMessage( '  Transparency : ' + transparency );
				material.transparent = material.opacity < 1 ? true : false;

			} else if ( next.id === MAT_TEXMAP ) {

				this.debugMessage( '   ColorMap' );
				material.map = this.readMap( next, path );

			} else if ( next.id === MAT_BUMPMAP ) {

				this.debugMessage( '   BumpMap' );
				material.bumpMap = this.readMap( next, path );

			} else if ( next.id === MAT_OPACMAP ) {

				this.debugMessage( '   OpacityMap' );
				material.alphaMap = this.readMap( next, path );

			} else if ( next.id === MAT_SPECMAP ) {

				this.debugMessage( '   SpecularMap' );
				material.specularMap = this.readMap( next, path );

			} else {

				this.debugMessage( '   Unknown material chunk: ' + next.hexId );

			}

			next = chunk.readChunk();

		}

		this.materials[ material.name ] = material;

	}

	/**
	 * Read mesh data chunk.
	 *
	 * @private
	 * @param {Chunk} chunk - Chunk in use.
	 * @return {Mesh} - The parsed mesh.
	 */
	readMesh( chunk ) {

		let next = chunk.readChunk( );

		const geometry = new BufferGeometry();

		const material = new MeshPhongMaterial();
		const mesh = new Mesh( geometry, material );
		mesh.name = 'mesh';

		while ( next ) {

			if ( next.id === POINT_ARRAY ) {

				const points = next.readWord( );

				this.debugMessage( '   Vertex: ' + points );

				//BufferGeometry

				const vertices = [];

				for ( let i = 0; i < points; i ++ )		{

					vertices.push( next.readFloat( ) );
					vertices.push( next.readFloat( ) );
					vertices.push( next.readFloat( ) );

				}

				geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );

			} else if ( next.id === FACE_ARRAY ) {

				this.readFaceArray( next, mesh );

			} else if ( next.id === TEX_VERTS ) {

				const texels = next.readWord( );

				this.debugMessage( '   UV: ' + texels );

				//BufferGeometry

				const uvs = [];

				for ( let i = 0; i < texels; i ++ ) {

					uvs.push( next.readFloat( ) );
					uvs.push( next.readFloat( ) );

				}

				geometry.setAttribute( 'uv', new Float32BufferAttribute( uvs, 2 ) );


			} else if ( next.id === MESH_MATRIX ) {

				this.debugMessage( '   Transformation Matrix (TODO)' );

				const values = [];
				for ( let i = 0; i < 12; i ++ ) {

					values[ i ] = next.readFloat( );

				}

				const matrix = new Matrix4();

				//X Line
				matrix.elements[ 0 ] = values[ 0 ];
				matrix.elements[ 1 ] = values[ 6 ];
				matrix.elements[ 2 ] = values[ 3 ];
				matrix.elements[ 3 ] = values[ 9 ];

				//Y Line
				matrix.elements[ 4 ] = values[ 2 ];
				matrix.elements[ 5 ] = values[ 8 ];
				matrix.elements[ 6 ] = values[ 5 ];
				matrix.elements[ 7 ] = values[ 11 ];

				//Z Line
				matrix.elements[ 8 ] = values[ 1 ];
				matrix.elements[ 9 ] = values[ 7 ];
				matrix.elements[ 10 ] = values[ 4 ];
				matrix.elements[ 11 ] = values[ 10 ];

				//W Line
				matrix.elements[ 12 ] = 0;
				matrix.elements[ 13 ] = 0;
				matrix.elements[ 14 ] = 0;
				matrix.elements[ 15 ] = 1;

				matrix.transpose();

				const inverse = new Matrix4();
				inverse.copy( matrix ).invert();
				geometry.applyMatrix4( inverse );

				matrix.decompose( mesh.position, mesh.quaternion, mesh.scale );

			} else {

				this.debugMessage( '   Unknown mesh chunk: ' + next.hexId );

			}

			next = chunk.readChunk( );

		}

		geometry.computeVertexNormals();

		return mesh;

	}

	/**
	 * Read face array data chunk.
	 *
	 * @private
	 * @param {Chunk} chunk - Chunk in use.
	 * @param {Mesh} mesh - Mesh to be filled with the data read.
	 */
	readFaceArray( chunk, mesh ) {

		const faces = chunk.readWord( );

		this.debugMessage( '   Faces: ' + faces );

		const index = [];

		for ( let i = 0; i < faces; ++ i ) {

			index.push( chunk.readWord( ), chunk.readWord( ), chunk.readWord( ) );

			chunk.readWord( ); // visibility

		}

		mesh.geometry.setIndex( index );

		//The rest of the FACE_ARRAY chunk is subchunks

		let materialIndex = 0;
		let start = 0;

		while ( ! chunk.endOfChunk ) {

			const subchunk = chunk.readChunk( );

			if ( subchunk.id === MSH_MAT_GROUP ) {

				this.debugMessage( '      Material Group' );

				const group = this.readMaterialGroup( subchunk );
				const count = group.index.length * 3; // assuming successive indices

				mesh.geometry.addGroup( start, count, materialIndex );

				start += count;
				materialIndex ++;

				const material = this.materials[ group.name ];

				if ( Array.isArray( mesh.material ) === false ) mesh.material = [];

				if ( material !== undefined )	{

					mesh.material.push( material );

				}

			} else {

				this.debugMessage( '      Unknown face array chunk: ' + subchunk.hexId );

			}

		}

		if ( mesh.material.length === 1 ) mesh.material = mesh.material[ 0 ]; // for backwards compatibility

	}

	/**
	 * Read texture map data chunk.
	 *
	 * @private
	 * @param {Chunk} chunk - Chunk in use.
	 * @param {string} path - Path for external resources.
	 * @return {Texture} Texture read from this data chunk.
	 */
	readMap( chunk, path ) {

		let next = chunk.readChunk( );
		let texture = {};

		const loader = new TextureLoader( this.manager );
		loader.setPath( this.resourcePath || path ).setCrossOrigin( this.crossOrigin );

		while ( next ) {

			if ( next.id === MAT_MAPNAME ) {

				const name = next.readString();
				texture = loader.load( name );

				this.debugMessage( '      File: ' + path + name );

			} else if ( next.id === MAT_MAP_UOFFSET ) {

				texture.offset.x = next.readFloat( );
				this.debugMessage( '      OffsetX: ' + texture.offset.x );

			} else if ( next.id === MAT_MAP_VOFFSET ) {

				texture.offset.y = next.readFloat( );
				this.debugMessage( '      OffsetY: ' + texture.offset.y );

			} else if ( next.id === MAT_MAP_USCALE ) {

				texture.repeat.x = next.readFloat( );
				this.debugMessage( '      RepeatX: ' + texture.repeat.x );

			} else if ( next.id === MAT_MAP_VSCALE ) {

				texture.repeat.y = next.readFloat( );
				this.debugMessage( '      RepeatY: ' + texture.repeat.y );

			} else {

				this.debugMessage( '      Unknown map chunk: ' + next.hexId );

			}

			next = chunk.readChunk( );

		}

		return texture;

	}

	/**
	 * Read material group data chunk.
	 *
	 * @private
	 * @param {Chunk} chunk - Chunk in use.
	 * @return {Object} Object with name and index of the object.
	 */
	readMaterialGroup( chunk ) {

		const name = chunk.readString();
		const numFaces = chunk.readWord();

		this.debugMessage( '         Name: ' + name );
		this.debugMessage( '         Faces: ' + numFaces );

		const index = [];
		for ( let i = 0; i < numFaces; ++ i ) {

			index.push( chunk.readWord( ) );

		}

		return { name: name, index: index };

	}

	/**
	 * Read a color value.
	 *
	 * @private
	 * @param {Chunk} chunk - Chunk.
	 * @return {Color} Color value read.
	 */
	readColor( chunk ) {

		const subChunk = chunk.readChunk( );
		const color = new Color();

		if ( subChunk.id === COLOR_24 || subChunk.id === LIN_COLOR_24 ) {

			const r = subChunk.readByte( );
			const g = subChunk.readByte( );
			const b = subChunk.readByte( );

			color.setRGB( r / 255, g / 255, b / 255 );

			this.debugMessage( '      Color: ' + color.r + ', ' + color.g + ', ' + color.b );

		}	else if ( subChunk.id === COLOR_F || subChunk.id === LIN_COLOR_F ) {

			const r = subChunk.readFloat( );
			const g = subChunk.readFloat( );
			const b = subChunk.readFloat( );

			color.setRGB( r, g, b );

			this.debugMessage( '      Color: ' + color.r + ', ' + color.g + ', ' + color.b );

		}	else {

			this.debugMessage( '      Unknown color chunk: ' + subChunk.hexId );

		}

		return color;

	}

	/**
	 * Read percentage value.
	 *
	 * @private
	 * @param {Chunk} chunk - Chunk to read data from.
	 * @return {number} Data read from the dataview.
	 */
	readPercentage( chunk ) {

		const subChunk = chunk.readChunk( );

		switch ( subChunk.id ) {

			case INT_PERCENTAGE:
				return ( subChunk.readShort( ) / 100 );
				break;

			case FLOAT_PERCENTAGE:
				return subChunk.readFloat( );
				break;

			default:
				this.debugMessage( '      Unknown percentage chunk: ' + subChunk.hexId );
				return 0;

		}

	}

	/**
	 * Print debug message to the console.
	 *
	 * Is controlled by a flag to show or hide debug messages.
	 *
	 * @private
	 * @param {Object} message - Debug message to print to the console.
	 */
	debugMessage( message ) {

		if ( this.debug ) {

			console.log( message );

		}

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: Group) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const path = ( this.path === '' ) ? LoaderUtils.extractUrlBase( url ) : this.path;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );

		loader.load( url, function ( data ) {

			try {

				onLoad( scope.parse( data, path ) );

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

##### `parse(arraybuffer: ArrayBuffer, path: string): Group`

<details><summary>Code</summary>

```ts
parse( arraybuffer, path ) {

		this.group = new Group();
		this.materials = [];
		this.meshes = [];

		this.readFile( arraybuffer, path );

		for ( let i = 0; i < this.meshes.length; i ++ ) {

			this.group.add( this.meshes[ i ] );

		}

		return this.group;

	}
```
</details>

##### `readFile(arraybuffer: ArrayBuffer, path: string): void`

<details><summary>Code</summary>

```ts
readFile( arraybuffer, path ) {

		const data = new DataView( arraybuffer );
		const chunk = new Chunk( data, 0, this.debugMessage );

		if ( chunk.id === MLIBMAGIC || chunk.id === CMAGIC || chunk.id === M3DMAGIC ) {

			let next = chunk.readChunk();

			while ( next ) {

				if ( next.id === M3D_VERSION ) {

					const version = next.readDWord();
					this.debugMessage( '3DS file version: ' + version );

				} else if ( next.id === MDATA ) {

					this.readMeshData( next, path );

				} else {

					this.debugMessage( 'Unknown main chunk: ' + next.hexId );

				}

				next = chunk.readChunk();

			}

		}

		this.debugMessage( 'Parsed ' + this.meshes.length + ' meshes' );

	}
```
</details>

##### `readMeshData(chunk: Chunk, path: string): void`

<details><summary>Code</summary>

```ts
readMeshData( chunk, path ) {

		let next = chunk.readChunk();

		while ( next ) {

			if ( next.id === MESH_VERSION ) {

				const version = + next.readDWord();
				this.debugMessage( 'Mesh Version: ' + version );

			} else if ( next.id === MASTER_SCALE ) {

				const scale = next.readFloat();
				this.debugMessage( 'Master scale: ' + scale );
				this.group.scale.set( scale, scale, scale );

			} else if ( next.id === NAMED_OBJECT ) {

				this.debugMessage( 'Named Object' );
				this.readNamedObject( next );

			} else if ( next.id === MAT_ENTRY ) {

				this.debugMessage( 'Material' );
				this.readMaterialEntry( next, path );

			} else {

				this.debugMessage( 'Unknown MDATA chunk: ' + next.hexId );

			}

			next = chunk.readChunk();

		}

	}
```
</details>

##### `readNamedObject(chunk: Chunk): void`

<details><summary>Code</summary>

```ts
readNamedObject( chunk ) {

		const name = chunk.readString();

		let next = chunk.readChunk();
		while ( next ) {

			if ( next.id === N_TRI_OBJECT ) {

				const mesh = this.readMesh( next );
				mesh.name = name;
				this.meshes.push( mesh );

			} else {

				this.debugMessage( 'Unknown named object chunk: ' + next.hexId );

			}

			next = chunk.readChunk( );

		}

	}
```
</details>

##### `readMaterialEntry(chunk: Chunk, path: string): void`

<details><summary>Code</summary>

```ts
readMaterialEntry( chunk, path ) {

		let next = chunk.readChunk();
		const material = new MeshPhongMaterial();

		while ( next ) {

			if ( next.id === MAT_NAME ) {

				material.name = next.readString();
				this.debugMessage( '   Name: ' + material.name );

			} else if ( next.id === MAT_WIRE ) {

				this.debugMessage( '   Wireframe' );
				material.wireframe = true;

			} else if ( next.id === MAT_WIRE_SIZE ) {

				const value = next.readByte();
				material.wireframeLinewidth = value;
				this.debugMessage( '   Wireframe Thickness: ' + value );

			} else if ( next.id === MAT_TWO_SIDE ) {

				material.side = DoubleSide;
				this.debugMessage( '   DoubleSided' );

			} else if ( next.id === MAT_ADDITIVE ) {

				this.debugMessage( '   Additive Blending' );
				material.blending = AdditiveBlending;

			} else if ( next.id === MAT_DIFFUSE ) {

				this.debugMessage( '   Diffuse Color' );
				material.color = this.readColor( next );

			} else if ( next.id === MAT_SPECULAR ) {

				this.debugMessage( '   Specular Color' );
				material.specular = this.readColor( next );

			} else if ( next.id === MAT_AMBIENT ) {

				this.debugMessage( '   Ambient color' );
				material.color = this.readColor( next );

			} else if ( next.id === MAT_SHININESS ) {

				const shininess = this.readPercentage( next );
				material.shininess = shininess * 100;
				this.debugMessage( '   Shininess : ' + shininess );

			} else if ( next.id === MAT_TRANSPARENCY ) {

				const transparency = this.readPercentage( next );
				material.opacity = 1 - transparency;
				this.debugMessage( '  Transparency : ' + transparency );
				material.transparent = material.opacity < 1 ? true : false;

			} else if ( next.id === MAT_TEXMAP ) {

				this.debugMessage( '   ColorMap' );
				material.map = this.readMap( next, path );

			} else if ( next.id === MAT_BUMPMAP ) {

				this.debugMessage( '   BumpMap' );
				material.bumpMap = this.readMap( next, path );

			} else if ( next.id === MAT_OPACMAP ) {

				this.debugMessage( '   OpacityMap' );
				material.alphaMap = this.readMap( next, path );

			} else if ( next.id === MAT_SPECMAP ) {

				this.debugMessage( '   SpecularMap' );
				material.specularMap = this.readMap( next, path );

			} else {

				this.debugMessage( '   Unknown material chunk: ' + next.hexId );

			}

			next = chunk.readChunk();

		}

		this.materials[ material.name ] = material;

	}
```
</details>

##### `readMesh(chunk: Chunk): Mesh`

<details><summary>Code</summary>

```ts
readMesh( chunk ) {

		let next = chunk.readChunk( );

		const geometry = new BufferGeometry();

		const material = new MeshPhongMaterial();
		const mesh = new Mesh( geometry, material );
		mesh.name = 'mesh';

		while ( next ) {

			if ( next.id === POINT_ARRAY ) {

				const points = next.readWord( );

				this.debugMessage( '   Vertex: ' + points );

				//BufferGeometry

				const vertices = [];

				for ( let i = 0; i < points; i ++ )		{

					vertices.push( next.readFloat( ) );
					vertices.push( next.readFloat( ) );
					vertices.push( next.readFloat( ) );

				}

				geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );

			} else if ( next.id === FACE_ARRAY ) {

				this.readFaceArray( next, mesh );

			} else if ( next.id === TEX_VERTS ) {

				const texels = next.readWord( );

				this.debugMessage( '   UV: ' + texels );

				//BufferGeometry

				const uvs = [];

				for ( let i = 0; i < texels; i ++ ) {

					uvs.push( next.readFloat( ) );
					uvs.push( next.readFloat( ) );

				}

				geometry.setAttribute( 'uv', new Float32BufferAttribute( uvs, 2 ) );


			} else if ( next.id === MESH_MATRIX ) {

				this.debugMessage( '   Transformation Matrix (TODO)' );

				const values = [];
				for ( let i = 0; i < 12; i ++ ) {

					values[ i ] = next.readFloat( );

				}

				const matrix = new Matrix4();

				//X Line
				matrix.elements[ 0 ] = values[ 0 ];
				matrix.elements[ 1 ] = values[ 6 ];
				matrix.elements[ 2 ] = values[ 3 ];
				matrix.elements[ 3 ] = values[ 9 ];

				//Y Line
				matrix.elements[ 4 ] = values[ 2 ];
				matrix.elements[ 5 ] = values[ 8 ];
				matrix.elements[ 6 ] = values[ 5 ];
				matrix.elements[ 7 ] = values[ 11 ];

				//Z Line
				matrix.elements[ 8 ] = values[ 1 ];
				matrix.elements[ 9 ] = values[ 7 ];
				matrix.elements[ 10 ] = values[ 4 ];
				matrix.elements[ 11 ] = values[ 10 ];

				//W Line
				matrix.elements[ 12 ] = 0;
				matrix.elements[ 13 ] = 0;
				matrix.elements[ 14 ] = 0;
				matrix.elements[ 15 ] = 1;

				matrix.transpose();

				const inverse = new Matrix4();
				inverse.copy( matrix ).invert();
				geometry.applyMatrix4( inverse );

				matrix.decompose( mesh.position, mesh.quaternion, mesh.scale );

			} else {

				this.debugMessage( '   Unknown mesh chunk: ' + next.hexId );

			}

			next = chunk.readChunk( );

		}

		geometry.computeVertexNormals();

		return mesh;

	}
```
</details>

##### `readFaceArray(chunk: Chunk, mesh: Mesh): void`

<details><summary>Code</summary>

```ts
readFaceArray( chunk, mesh ) {

		const faces = chunk.readWord( );

		this.debugMessage( '   Faces: ' + faces );

		const index = [];

		for ( let i = 0; i < faces; ++ i ) {

			index.push( chunk.readWord( ), chunk.readWord( ), chunk.readWord( ) );

			chunk.readWord( ); // visibility

		}

		mesh.geometry.setIndex( index );

		//The rest of the FACE_ARRAY chunk is subchunks

		let materialIndex = 0;
		let start = 0;

		while ( ! chunk.endOfChunk ) {

			const subchunk = chunk.readChunk( );

			if ( subchunk.id === MSH_MAT_GROUP ) {

				this.debugMessage( '      Material Group' );

				const group = this.readMaterialGroup( subchunk );
				const count = group.index.length * 3; // assuming successive indices

				mesh.geometry.addGroup( start, count, materialIndex );

				start += count;
				materialIndex ++;

				const material = this.materials[ group.name ];

				if ( Array.isArray( mesh.material ) === false ) mesh.material = [];

				if ( material !== undefined )	{

					mesh.material.push( material );

				}

			} else {

				this.debugMessage( '      Unknown face array chunk: ' + subchunk.hexId );

			}

		}

		if ( mesh.material.length === 1 ) mesh.material = mesh.material[ 0 ]; // for backwards compatibility

	}
```
</details>

##### `readMap(chunk: Chunk, path: string): Texture`

<details><summary>Code</summary>

```ts
readMap( chunk, path ) {

		let next = chunk.readChunk( );
		let texture = {};

		const loader = new TextureLoader( this.manager );
		loader.setPath( this.resourcePath || path ).setCrossOrigin( this.crossOrigin );

		while ( next ) {

			if ( next.id === MAT_MAPNAME ) {

				const name = next.readString();
				texture = loader.load( name );

				this.debugMessage( '      File: ' + path + name );

			} else if ( next.id === MAT_MAP_UOFFSET ) {

				texture.offset.x = next.readFloat( );
				this.debugMessage( '      OffsetX: ' + texture.offset.x );

			} else if ( next.id === MAT_MAP_VOFFSET ) {

				texture.offset.y = next.readFloat( );
				this.debugMessage( '      OffsetY: ' + texture.offset.y );

			} else if ( next.id === MAT_MAP_USCALE ) {

				texture.repeat.x = next.readFloat( );
				this.debugMessage( '      RepeatX: ' + texture.repeat.x );

			} else if ( next.id === MAT_MAP_VSCALE ) {

				texture.repeat.y = next.readFloat( );
				this.debugMessage( '      RepeatY: ' + texture.repeat.y );

			} else {

				this.debugMessage( '      Unknown map chunk: ' + next.hexId );

			}

			next = chunk.readChunk( );

		}

		return texture;

	}
```
</details>

##### `readMaterialGroup(chunk: Chunk): any`

<details><summary>Code</summary>

```ts
readMaterialGroup( chunk ) {

		const name = chunk.readString();
		const numFaces = chunk.readWord();

		this.debugMessage( '         Name: ' + name );
		this.debugMessage( '         Faces: ' + numFaces );

		const index = [];
		for ( let i = 0; i < numFaces; ++ i ) {

			index.push( chunk.readWord( ) );

		}

		return { name: name, index: index };

	}
```
</details>

##### `readColor(chunk: Chunk): Color`

<details><summary>Code</summary>

```ts
readColor( chunk ) {

		const subChunk = chunk.readChunk( );
		const color = new Color();

		if ( subChunk.id === COLOR_24 || subChunk.id === LIN_COLOR_24 ) {

			const r = subChunk.readByte( );
			const g = subChunk.readByte( );
			const b = subChunk.readByte( );

			color.setRGB( r / 255, g / 255, b / 255 );

			this.debugMessage( '      Color: ' + color.r + ', ' + color.g + ', ' + color.b );

		}	else if ( subChunk.id === COLOR_F || subChunk.id === LIN_COLOR_F ) {

			const r = subChunk.readFloat( );
			const g = subChunk.readFloat( );
			const b = subChunk.readFloat( );

			color.setRGB( r, g, b );

			this.debugMessage( '      Color: ' + color.r + ', ' + color.g + ', ' + color.b );

		}	else {

			this.debugMessage( '      Unknown color chunk: ' + subChunk.hexId );

		}

		return color;

	}
```
</details>

##### `readPercentage(chunk: Chunk): number`

<details><summary>Code</summary>

```ts
readPercentage( chunk ) {

		const subChunk = chunk.readChunk( );

		switch ( subChunk.id ) {

			case INT_PERCENTAGE:
				return ( subChunk.readShort( ) / 100 );
				break;

			case FLOAT_PERCENTAGE:
				return subChunk.readFloat( );
				break;

			default:
				this.debugMessage( '      Unknown percentage chunk: ' + subChunk.hexId );
				return 0;

		}

	}
```
</details>

##### `debugMessage(message: any): void`

<details><summary>Code</summary>

```ts
debugMessage( message ) {

		if ( this.debug ) {

			console.log( message );

		}

	}
```
</details>

### `Chunk`

<details><summary>Class Code</summary>

```ts
class Chunk {

	/**
	 * Create a new chunk
	 *
	 * @private
	 * @param {DataView} data - DataView to read from.
	 * @param {number} position - In data.
	 * @param {Function} debugMessage - Logging callback.
	 */
	constructor( data, position, debugMessage ) {

		this.data = data;
		// the offset to the begin of this chunk
		this.offset = position;
		// the current reading position
		this.position = position;
		this.debugMessage = debugMessage;

		if ( this.debugMessage instanceof Function ) {

			this.debugMessage = function () {};

		}

		this.id = this.readWord();
		this.size = this.readDWord();
		this.end = this.offset + this.size;

		if ( this.end > data.byteLength ) {

			this.debugMessage( 'Bad chunk size for chunk at ' + position );

		}

	}

	/**
	 * Reads a sub cchunk.
	 *
	 * @private
	 * @return {Chunk | null} next sub chunk.
	 */
	readChunk() {

		if ( this.endOfChunk ) {

			return null;

		}

		try {

			const next = new Chunk( this.data, this.position, this.debugMessage );
			this.position += next.size;
			return next;

		}	catch ( e ) {

			this.debugMessage( 'Unable to read chunk at ' + this.position );
			return null;

		}

	}

	/**
	 * Returns the ID of this chunk as Hex
	 *
	 * @private
	 * @return {string} hex-string of id
	 */
	get hexId() {

		return this.id.toString( 16 );

	}

	get endOfChunk() {

		return this.position >= this.end;

	}

	/**
	 * Read byte value.
	 *
	 * @private
	 * @return {number} Data read from the dataview.
	 */
	readByte() {

		const v = this.data.getUint8( this.position, true );
		this.position += 1;
		return v;

	}

	/**
	 * Read 32 bit float value.
	 *
	 * @private
	 * @return {number} Data read from the dataview.
	 */
	readFloat() {

		try {

			const v = this.data.getFloat32( this.position, true );
			this.position += 4;
			return v;

		}	catch ( e ) {

			this.debugMessage( e + ' ' + this.position + ' ' + this.data.byteLength );
			return 0;

		}

	}

	/**
	 * Read 32 bit signed integer value.
	 *
	 * @private
	 * @return {number} Data read from the dataview.
	 */
	readInt() {

		const v = this.data.getInt32( this.position, true );
		this.position += 4;
		return v;

	}

	/**
	 * Read 16 bit signed integer value.
	 *
	 * @private
	 * @return {number} Data read from the dataview.
	 */
	readShort() {

		const v = this.data.getInt16( this.position, true );
		this.position += 2;
		return v;

	}

	/**
	 * Read 64 bit unsigned integer value.
	 *
	 * @private
	 * @return {number} Data read from the dataview.
	 */
	readDWord() {

		const v = this.data.getUint32( this.position, true );
		this.position += 4;
		return v;

	}

	/**
	 * Read 32 bit unsigned integer value.
	 *
	 * @private
	 * @return {number} Data read from the dataview.
	 */
	readWord() {

		const v = this.data.getUint16( this.position, true );
		this.position += 2;
		return v;

	}

	/**
	 * Read NULL terminated ASCII string value from chunk-pos.
	 *
	 * @private
	 * @return {string} Data read from the dataview.
	 */
	readString() {

		let s = '';
		let c = this.readByte();
		while ( c ) {

			s += String.fromCharCode( c );
			c = this.readByte();

		}

		return s;

	}

}
```
</details>

#### Methods

##### `readChunk(): Chunk`

<details><summary>Code</summary>

```ts
readChunk() {

		if ( this.endOfChunk ) {

			return null;

		}

		try {

			const next = new Chunk( this.data, this.position, this.debugMessage );
			this.position += next.size;
			return next;

		}	catch ( e ) {

			this.debugMessage( 'Unable to read chunk at ' + this.position );
			return null;

		}

	}
```
</details>

##### `readByte(): number`

<details><summary>Code</summary>

```ts
readByte() {

		const v = this.data.getUint8( this.position, true );
		this.position += 1;
		return v;

	}
```
</details>

##### `readFloat(): number`

<details><summary>Code</summary>

```ts
readFloat() {

		try {

			const v = this.data.getFloat32( this.position, true );
			this.position += 4;
			return v;

		}	catch ( e ) {

			this.debugMessage( e + ' ' + this.position + ' ' + this.data.byteLength );
			return 0;

		}

	}
```
</details>

##### `readInt(): number`

<details><summary>Code</summary>

```ts
readInt() {

		const v = this.data.getInt32( this.position, true );
		this.position += 4;
		return v;

	}
```
</details>

##### `readShort(): number`

<details><summary>Code</summary>

```ts
readShort() {

		const v = this.data.getInt16( this.position, true );
		this.position += 2;
		return v;

	}
```
</details>

##### `readDWord(): number`

<details><summary>Code</summary>

```ts
readDWord() {

		const v = this.data.getUint32( this.position, true );
		this.position += 4;
		return v;

	}
```
</details>

##### `readWord(): number`

<details><summary>Code</summary>

```ts
readWord() {

		const v = this.data.getUint16( this.position, true );
		this.position += 2;
		return v;

	}
```
</details>

##### `readString(): string`

<details><summary>Code</summary>

```ts
readString() {

		let s = '';
		let c = this.readByte();
		while ( c ) {

			s += String.fromCharCode( c );
			c = this.readByte();

		}

		return s;

	}
```
</details>


---