[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LWOLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 33 |
| 🧱 Classes | 4 |
| 📦 Imports | 26 |
| 📊 Variables & Constants | 51 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/LWOLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AddOperation` | `three` |
| `BackSide` | `three` |
| `BufferGeometry` | `three` |
| `ClampToEdgeWrapping` | `three` |
| `Color` | `three` |
| `DoubleSide` | `three` |
| `EquirectangularReflectionMapping` | `three` |
| `EquirectangularRefractionMapping` | `three` |
| `FileLoader` | `three` |
| `Float32BufferAttribute` | `three` |
| `FrontSide` | `three` |
| `LineBasicMaterial` | `three` |
| `LineSegments` | `three` |
| `Loader` | `three` |
| `Mesh` | `three` |
| `MeshPhongMaterial` | `three` |
| `MeshPhysicalMaterial` | `three` |
| `MeshStandardMaterial` | `three` |
| `MirroredRepeatWrapping` | `three` |
| `Points` | `three` |
| `PointsMaterial` | `three` |
| `RepeatWrapping` | `three` |
| `SRGBColorSpace` | `three` |
| `TextureLoader` | `three` |
| `Vector2` | `three` |
| `IFFParser` | `./lwo/IFFParser.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_lwoTree` | `any` | let/var | `*not shown*` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `path` | `any` | let/var | `( scope.path === '' ) ? extractParentUrl( url, 'Objects' ) : scope.path` | ✗ |
| `modelName` | `string` | let/var | `url.split( path ).pop().split( '.' )[ 0 ]` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `meshes` | `any[]` | let/var | `[]` | ✗ |
| `finalMeshes` | `any[]` | let/var | `[]` | ✗ |
| `geometryParser` | `GeometryParser` | let/var | `new GeometryParser()` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `mesh` | `any` | let/var | `*not shown*` | ✗ |
| `pivot` | `any` | let/var | `child.userData.pivot` | ✗ |
| `parentPivot` | `any` | let/var | `child.parent.userData.pivot` | ✗ |
| `materials` | `any[]` | let/var | `[]` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `spec` | `{ color: any; }` | let/var | `{ color: mat.color, }` | ✗ |
| `materials` | `any[]` | let/var | `[]` | ✗ |
| `params` | `{ name: any; side: any; flatShading: ...` | let/var | `{ name: name, side: this.getSide( materialData.attributes ), flatShading: thi...` | ✗ |
| `params` | `{ name: any; side: any; flatShading: ...` | let/var | `{ name: name, side: this.getSide( materialData.attributes ), flatShading: thi...` | ✗ |
| `materialConnections` | `{ maps: {}; }` | let/var | `{ maps: {} }` | ✗ |
| `inputName` | `any` | let/var | `connections.inputName` | ✗ |
| `inputNodeName` | `any` | let/var | `connections.inputNodeName` | ✗ |
| `nodeName` | `any` | let/var | `connections.nodeName` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `maps` | `{ map: any; roughnessMap: any; roughn...` | let/var | `{}` | ✗ |
| `node` | `any` | let/var | `textureNodes[ name ]` | ✗ |
| `path` | `any` | let/var | `node.fileName` | ✗ |
| `attribute` | `any` | let/var | `attributes[ name ]` | ✗ |
| `mapData` | `any` | let/var | `attribute.maps[ 0 ]` | ✗ |
| `params` | `{ color: any; opacity: number; transp...` | let/var | `{}` | ✗ |
| `fileName` | `string` | let/var | `''` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `remappedIndices` | `any[]` | let/var | `[]` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `tags` | `any` | let/var | `_lwoTree.tags` | ✗ |
| `matNames` | `any[]` | let/var | `[]` | ✗ |
| `elemSize` | `number` | let/var | `3` | ✗ |
| `indexNum` | `number` | let/var | `0` | ✗ |
| `indexPairs` | `{}` | let/var | `{}` | ✗ |
| `prevMaterialIndex` | `any` | let/var | `*not shown*` | ✗ |
| `materialIndex` | `any` | let/var | `*not shown*` | ✗ |
| `prevStart` | `number` | let/var | `0` | ✗ |
| `currentCount` | `number` | let/var | `0` | ✗ |
| `currentIndex` | `any` | let/var | `*not shown*` | ✗ |
| `currentIndex` | `any` | let/var | `*not shown*` | ✗ |
| `remappedIndices` | `any[]` | let/var | `[]` | ✗ |
| `uvs` | `any` | let/var | `layer.uvs[ name ].uvs` | ✗ |
| `uvIndices` | `any` | let/var | `layer.uvs[ name ].uvIndices` | ✗ |
| `num` | `number` | let/var | `0` | ✗ |
| `morphPoints` | `any` | let/var | `layer.morphTargets[ name ].points` | ✗ |
| `morphIndices` | `any` | let/var | `layer.morphTargets[ name ].indices` | ✗ |
| `type` | `any` | let/var | `layer.morphTargets[ name ].type` | ✗ |


---

## Functions

### `LWOLoader.load(url: string, onLoad: (arg0: { meshes: Mesh[]; materials: Material[]; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded LWO asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({meshes:Array<Mesh>,materials:Array<Material>})} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: { meshes: Mesh[]; materials: Material[]; }) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `extractParentUrl`
- `url.split( path ).pop().split`
- `loader.setPath`
- `loader.setResponseType`
- `loader.load`
- `onLoad`
- `scope.parse`
- `onError`
- `console.error`
- `scope.manager.itemError`

**Internal Comments:**
```
// give the mesh a default name based on the filename (x2)
// console.time( 'Total parsing: ' );
```

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const path = ( scope.path === '' ) ? extractParentUrl( url, 'Objects' ) : scope.path;

		// give the mesh a default name based on the filename
		const modelName = url.split( path ).pop().split( '.' )[ 0 ];

		const loader = new FileLoader( this.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );

		loader.load( url, function ( buffer ) {

			// console.time( 'Total parsing: ' );

			try {

				onLoad( scope.parse( buffer, path, modelName ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

			// console.timeEnd( 'Total parsing: ' );

		}, onProgress, onError );

	}
```
</details>

### `LWOLoader.parse(iffBuffer: ArrayBuffer, path: string, modelName: string): { meshes: Mesh[]; materials: Material[]; }`

**JSDoc:**
```typescript
/**
	 * Parses the given LWO data and returns the resulting meshes and materials.
	 *
	 * @param {ArrayBuffer} iffBuffer - The raw LWO data as an array buffer.
	 * @param {string} path - The URL base path.
	 * @param {string} modelName - The model name.
	 * @return {{meshes:Array<Mesh>,materials:Array<Material>}} An object holding the parse meshes and materials.
	 */
```

**Parameters:**

- **`iffBuffer`** `ArrayBuffer`
- **`path`** `string`
- **`modelName`** `string`

**Returns:** `{ meshes: Mesh[]; materials: Material[]; }`

**Calls:**

- `new IFFParser().parse`
- `new TextureLoader( this.manager ).setPath( this.resourcePath || path ).setCrossOrigin`
- `new LWOTreeParser( textureLoader ).parse`

**Internal Comments:**
```
// console.log( 'lwoTree', lwoTree ); (x2)
```

<details><summary>Code</summary>

```typescript
parse( iffBuffer, path, modelName ) {

		_lwoTree = new IFFParser().parse( iffBuffer );

		// console.log( 'lwoTree', lwoTree );

		const textureLoader = new TextureLoader( this.manager ).setPath( this.resourcePath || path ).setCrossOrigin( this.crossOrigin );

		return new LWOTreeParser( textureLoader ).parse( modelName );

	}
```
</details>

### `LWOTreeParser.parse(modelName: any): { materials: any[]; meshes: any[]; }`

**Parameters:**

- **`modelName`** `any`

**Returns:** `{ materials: any[]; meshes: any[]; }`

**Calls:**

- `new MaterialParser( this.textureLoader ).parse`
- `this.parseLayers`

<details><summary>Code</summary>

```typescript
parse( modelName ) {

		this.materials = new MaterialParser( this.textureLoader ).parse();
		this.defaultLayerName = modelName;

		this.meshes = this.parseLayers();

		return {
			materials: this.materials,
			meshes: this.meshes,
		};

	}
```
</details>

### `LWOTreeParser.parseLayers(): any[]`

**Returns:** `any[]`

**Calls:**

- `_lwoTree.layers.forEach`
- `geometryParser.parse`
- `scope.parseMesh`
- `finalMeshes.push`
- `meshes[ layer.parent ].add`
- `this.applyPivots`

**Internal Comments:**
```
// array of all meshes for building hierarchy (x2)
// final array containing meshes with scene graph hierarchy set up (x2)
```

<details><summary>Code</summary>

```typescript
parseLayers() {

		// array of all meshes for building hierarchy
		const meshes = [];

		// final array containing meshes with scene graph hierarchy set up
		const finalMeshes = [];

		const geometryParser = new GeometryParser();

		const scope = this;
		_lwoTree.layers.forEach( function ( layer ) {

			const geometry = geometryParser.parse( layer.geometry, layer );

			const mesh = scope.parseMesh( geometry, layer );

			meshes[ layer.number ] = mesh;

			if ( layer.parent === - 1 ) finalMeshes.push( mesh );
			else meshes[ layer.parent ].add( mesh );


		} );

		this.applyPivots( finalMeshes );

		return finalMeshes;

	}
```
</details>

### `LWOTreeParser.parseMesh(geometry: any, layer: any): any`

**Parameters:**

- **`geometry`** `any`
- **`layer`** `any`

**Returns:** `any`

**Calls:**

- `this.getMaterials`

<details><summary>Code</summary>

```typescript
parseMesh( geometry, layer ) {

		let mesh;

		const materials = this.getMaterials( geometry.userData.matNames, layer.geometry.type );

		if ( layer.geometry.type === 'points' ) mesh = new Points( geometry, materials );
		else if ( layer.geometry.type === 'lines' ) mesh = new LineSegments( geometry, materials );
		else mesh = new Mesh( geometry, materials );

		if ( layer.name ) mesh.name = layer.name;
		else mesh.name = this.defaultLayerName + '_layer_' + layer.number;

		mesh.userData.pivot = layer.pivot;

		return mesh;

	}
```
</details>

### `LWOTreeParser.applyPivots(meshes: any): void`

**Parameters:**

- **`meshes`** `any`

**Returns:** `void`

**Calls:**

- `meshes.forEach`
- `mesh.traverse`

<details><summary>Code</summary>

```typescript
applyPivots( meshes ) {

		meshes.forEach( function ( mesh ) {

			mesh.traverse( function ( child ) {

				const pivot = child.userData.pivot;

				child.position.x += pivot[ 0 ];
				child.position.y += pivot[ 1 ];
				child.position.z += pivot[ 2 ];

				if ( child.parent ) {

					const parentPivot = child.parent.userData.pivot;

					child.position.x -= parentPivot[ 0 ];
					child.position.y -= parentPivot[ 1 ];
					child.position.z -= parentPivot[ 2 ];

				}

			} );

		} );

	}
```
</details>

### `LWOTreeParser.getMaterials(namesArray: any, type: any): any`

**Parameters:**

- **`namesArray`** `any`
- **`type`** `any`

**Returns:** `any`

**Calls:**

- `namesArray.forEach`
- `scope.getMaterialByName`
- `materials.forEach`
- `materials.filter`

**Internal Comments:**
```
// convert materials to line or point mats if required
// if there is only one material, return that directly instead of array (x2)
```

<details><summary>Code</summary>

```typescript
getMaterials( namesArray, type ) {

		const materials = [];

		const scope = this;

		namesArray.forEach( function ( name, i ) {

			materials[ i ] = scope.getMaterialByName( name );

		} );

		// convert materials to line or point mats if required
		if ( type === 'points' || type === 'lines' ) {

			materials.forEach( function ( mat, i ) {

				const spec = {
					color: mat.color,
				};

				if ( type === 'points' ) {

					spec.size = 0.1;
					spec.map = mat.map;
					materials[ i ] = new PointsMaterial( spec );

				} else if ( type === 'lines' ) {

					materials[ i ] = new LineBasicMaterial( spec );

				}

			} );

		}

		// if there is only one material, return that directly instead of array
		const filtered = materials.filter( Boolean );
		if ( filtered.length === 1 ) return filtered[ 0 ];

		return materials;

	}
```
</details>

### `LWOTreeParser.getMaterialByName(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `this.materials.filter`

<details><summary>Code</summary>

```typescript
getMaterialByName( name ) {

		return this.materials.filter( function ( m ) {

			return m.name === name;

		} )[ 0 ];

	}
```
</details>

### `MaterialParser.parse(): any[]`

**Returns:** `any[]`

**Calls:**

- `materials.push`
- `this.parseMaterial`
- `this.parseMaterialLwo2`

<details><summary>Code</summary>

```typescript
parse() {

		const materials = [];
		this.textures = {};

		for ( const name in _lwoTree.materials ) {

			if ( _lwoTree.format === 'LWO3' ) {

				materials.push( this.parseMaterial( _lwoTree.materials[ name ], name, _lwoTree.textures ) );

			} else if ( _lwoTree.format === 'LWO2' ) {

				materials.push( this.parseMaterialLwo2( _lwoTree.materials[ name ], name, _lwoTree.textures ) );

			}

		}

		return materials;

	}
```
</details>

### `MaterialParser.parseMaterial(materialData: any, name: any, textures: any): any`

**Parameters:**

- **`materialData`** `any`
- **`name`** `any`
- **`textures`** `any`

**Returns:** `any`

**Calls:**

- `this.getSide`
- `this.getSmooth`
- `this.parseConnections`
- `this.parseTextureNodes`
- `this.parseAttributeImageMaps`
- `this.parseAttributes`
- `this.parseEnvMap`
- `Object.assign`
- `this.getMaterialType`

<details><summary>Code</summary>

```typescript
parseMaterial( materialData, name, textures ) {

		let params = {
			name: name,
			side: this.getSide( materialData.attributes ),
			flatShading: this.getSmooth( materialData.attributes ),
		};

		const connections = this.parseConnections( materialData.connections, materialData.nodes );

		const maps = this.parseTextureNodes( connections.maps );

		this.parseAttributeImageMaps( connections.attributes, textures, maps );

		const attributes = this.parseAttributes( connections.attributes, maps );

		this.parseEnvMap( connections, maps, attributes );

		params = Object.assign( maps, params );
		params = Object.assign( params, attributes );

		const materialType = this.getMaterialType( connections.attributes );

		if ( materialType !== MeshPhongMaterial ) delete params.refractionRatio; // PBR materials do not support "refractionRatio"

		return new materialType( params );

	}
```
</details>

### `MaterialParser.parseMaterialLwo2(materialData: any, name: any): any`

**Parameters:**

- **`materialData`** `any`
- **`name`** `any`

**Returns:** `any`

**Calls:**

- `this.getSide`
- `this.getSmooth`
- `this.parseAttributes`
- `Object.assign`

<details><summary>Code</summary>

```typescript
parseMaterialLwo2( materialData, name/*, textures*/ ) {

		let params = {
			name: name,
			side: this.getSide( materialData.attributes ),
			flatShading: this.getSmooth( materialData.attributes ),
		};

		const attributes = this.parseAttributes( materialData.attributes, {} );
		params = Object.assign( params, attributes );
		return new MeshPhongMaterial( params );

	}
```
</details>

### `MaterialParser.getSide(attributes: any): any`

**Parameters:**

- **`attributes`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getSide( attributes ) {

		if ( ! attributes.side ) return BackSide;

		switch ( attributes.side ) {

			case 0:
			case 1:
				return BackSide;
			case 2: return FrontSide;
			case 3: return DoubleSide;

		}

	}
```
</details>

### `MaterialParser.getSmooth(attributes: any): boolean`

**Parameters:**

- **`attributes`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
getSmooth( attributes ) {

		if ( ! attributes.smooth ) return true;
		return ! attributes.smooth;

	}
```
</details>

### `MaterialParser.parseConnections(connections: any, nodes: any): { maps: {}; }`

**Parameters:**

- **`connections`** `any`
- **`nodes`** `any`

**Returns:** `{ maps: {}; }`

**Calls:**

- `inputName.forEach`
- `scope.getNodeByRefName`
- `nodeName.forEach`

<details><summary>Code</summary>

```typescript
parseConnections( connections, nodes ) {

		const materialConnections = {
			maps: {}
		};

		const inputName = connections.inputName;
		const inputNodeName = connections.inputNodeName;
		const nodeName = connections.nodeName;

		const scope = this;
		inputName.forEach( function ( name, index ) {

			if ( name === 'Material' ) {

				const matNode = scope.getNodeByRefName( inputNodeName[ index ], nodes );
				materialConnections.attributes = matNode.attributes;
				materialConnections.envMap = matNode.fileName;
				materialConnections.name = inputNodeName[ index ];

			}

		} );

		nodeName.forEach( function ( name, index ) {

			if ( name === materialConnections.name ) {

				materialConnections.maps[ inputName[ index ] ] = scope.getNodeByRefName( inputNodeName[ index ], nodes );

			}

		} );

		return materialConnections;

	}
```
</details>

### `MaterialParser.getNodeByRefName(refName: any, nodes: any): any`

**Parameters:**

- **`refName`** `any`
- **`nodes`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getNodeByRefName( refName, nodes ) {

		for ( const name in nodes ) {

			if ( nodes[ name ].refName === refName ) return nodes[ name ];

		}

	}
```
</details>

### `MaterialParser.parseTextureNodes(textureNodes: any): { map: any; roughnessMap: any; roughness: number; specularMap: any; specular: number; emissiveMap: any; emissive: number; metalnessMap: any; metalness: number; alphaMap: any; transparent: boolean; normalMap: any; normalScale: any; bumpMap: any; }`

**Parameters:**

- **`textureNodes`** `any`

**Returns:** `{ map: any; roughnessMap: any; roughness: number; specularMap: any; specular: number; emissiveMap: any; emissive: number; metalnessMap: any; metalness: number; alphaMap: any; transparent: boolean; normalMap: any; normalScale: any; bumpMap: any; }`

**Calls:**

- `this.loadTexture`
- `this.getWrappingType`

**Internal Comments:**
```
// LWO BSDF materials can have both spec and rough, but this is not valid in three
```

<details><summary>Code</summary>

```typescript
parseTextureNodes( textureNodes ) {

		const maps = {};

		for ( const name in textureNodes ) {

			const node = textureNodes[ name ];
			const path = node.fileName;

			if ( ! path ) return;

			const texture = this.loadTexture( path );

			if ( node.widthWrappingMode !== undefined ) texture.wrapS = this.getWrappingType( node.widthWrappingMode );
			if ( node.heightWrappingMode !== undefined ) texture.wrapT = this.getWrappingType( node.heightWrappingMode );

			switch ( name ) {

				case 'Color':
					maps.map = texture;
					maps.map.colorSpace = SRGBColorSpace;
					break;
				case 'Roughness':
					maps.roughnessMap = texture;
					maps.roughness = 1;
					break;
				case 'Specular':
					maps.specularMap = texture;
					maps.specularMap.colorSpace = SRGBColorSpace;
					maps.specular = 0xffffff;
					break;
				case 'Luminous':
					maps.emissiveMap = texture;
					maps.emissiveMap.colorSpace = SRGBColorSpace;
					maps.emissive = 0x808080;
					break;
				case 'Luminous Color':
					maps.emissive = 0x808080;
					break;
				case 'Metallic':
					maps.metalnessMap = texture;
					maps.metalness = 1;
					break;
				case 'Transparency':
				case 'Alpha':
					maps.alphaMap = texture;
					maps.transparent = true;
					break;
				case 'Normal':
					maps.normalMap = texture;
					if ( node.amplitude !== undefined ) maps.normalScale = new Vector2( node.amplitude, node.amplitude );
					break;
				case 'Bump':
					maps.bumpMap = texture;
					break;

			}

		}

		// LWO BSDF materials can have both spec and rough, but this is not valid in three
		if ( maps.roughnessMap && maps.specularMap ) delete maps.specularMap;

		return maps;

	}
```
</details>

### `MaterialParser.parseAttributeImageMaps(attributes: any, textures: any, maps: any): void`

**Parameters:**

- **`attributes`** `any`
- **`textures`** `any`
- **`maps`** `any`

**Returns:** `void`

**Calls:**

- `this.getTexturePathByIndex`
- `this.loadTexture`
- `this.getWrappingType`

<details><summary>Code</summary>

```typescript
parseAttributeImageMaps( attributes, textures, maps ) {

		for ( const name in attributes ) {

			const attribute = attributes[ name ];

			if ( attribute.maps ) {

				const mapData = attribute.maps[ 0 ];

				const path = this.getTexturePathByIndex( mapData.imageIndex );
				if ( ! path ) return;

				const texture = this.loadTexture( path );

				if ( mapData.wrap !== undefined ) texture.wrapS = this.getWrappingType( mapData.wrap.w );
				if ( mapData.wrap !== undefined ) texture.wrapT = this.getWrappingType( mapData.wrap.h );

				switch ( name ) {

					case 'Color':
						maps.map = texture;
						maps.map.colorSpace = SRGBColorSpace;
						break;
					case 'Diffuse':
						maps.aoMap = texture;
						break;
					case 'Roughness':
						maps.roughnessMap = texture;
						maps.roughness = 1;
						break;
					case 'Specular':
						maps.specularMap = texture;
						maps.specularMap.colorSpace = SRGBColorSpace;
						maps.specular = 0xffffff;
						break;
					case 'Luminosity':
						maps.emissiveMap = texture;
						maps.emissiveMap.colorSpace = SRGBColorSpace;
						maps.emissive = 0x808080;
						break;
					case 'Metallic':
						maps.metalnessMap = texture;
						maps.metalness = 1;
						break;
					case 'Transparency':
					case 'Alpha':
						maps.alphaMap = texture;
						maps.transparent = true;
						break;
					case 'Normal':
						maps.normalMap = texture;
						break;
					case 'Bump':
						maps.bumpMap = texture;
						break;

				}

			}

		}

	}
```
</details>

### `MaterialParser.parseAttributes(attributes: any, maps: any): { color: any; opacity: number; transparent: boolean; bumpScale: number; }`

**Parameters:**

- **`attributes`** `any`
- **`maps`** `any`

**Returns:** `{ color: any; opacity: number; transparent: boolean; bumpScale: number; }`

**Calls:**

- `new Color().fromArray`
- `this.parsePhysicalAttributes`
- `this.parseStandardAttributes`
- `this.parsePhongAttributes`

**Internal Comments:**
```
// don't use color data if color map is present
```

<details><summary>Code</summary>

```typescript
parseAttributes( attributes, maps ) {

		const params = {};

		// don't use color data if color map is present
		if ( attributes.Color && ! maps.map ) {

			params.color = new Color().fromArray( attributes.Color.value );

		} else {

			params.color = new Color();

		}


		if ( attributes.Transparency && attributes.Transparency.value !== 0 ) {

			params.opacity = 1 - attributes.Transparency.value;
			params.transparent = true;

		}

		if ( attributes[ 'Bump Height' ] ) params.bumpScale = attributes[ 'Bump Height' ].value * 0.1;

		this.parsePhysicalAttributes( params, attributes, maps );
		this.parseStandardAttributes( params, attributes, maps );
		this.parsePhongAttributes( params, attributes, maps );

		return params;

	}
```
</details>

### `MaterialParser.parsePhysicalAttributes(params: any, attributes: any): void`

**Parameters:**

- **`params`** `any`
- **`attributes`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
parsePhysicalAttributes( params, attributes/*, maps*/ ) {

		if ( attributes.Clearcoat && attributes.Clearcoat.value > 0 ) {

			params.clearcoat = attributes.Clearcoat.value;

			if ( attributes[ 'Clearcoat Gloss' ] ) {

				params.clearcoatRoughness = 0.5 * ( 1 - attributes[ 'Clearcoat Gloss' ].value );

			}

		}

	}
```
</details>

### `MaterialParser.parseStandardAttributes(params: any, attributes: any, maps: any): void`

**Parameters:**

- **`params`** `any`
- **`attributes`** `any`
- **`maps`** `any`

**Returns:** `void`

**Calls:**

- `new Color().fromArray`

<details><summary>Code</summary>

```typescript
parseStandardAttributes( params, attributes, maps ) {


		if ( attributes.Luminous ) {

			params.emissiveIntensity = attributes.Luminous.value;

			if ( attributes[ 'Luminous Color' ] && ! maps.emissive ) {

				params.emissive = new Color().fromArray( attributes[ 'Luminous Color' ].value );

			} else {

				params.emissive = new Color( 0x808080 );

			}

		}

		if ( attributes.Roughness && ! maps.roughnessMap ) params.roughness = attributes.Roughness.value;
		if ( attributes.Metallic && ! maps.metalnessMap ) params.metalness = attributes.Metallic.value;

	}
```
</details>

### `MaterialParser.parsePhongAttributes(params: any, attributes: any, maps: any): void`

**Parameters:**

- **`params`** `any`
- **`attributes`** `any`
- **`maps`** `any`

**Returns:** `void`

**Calls:**

- `params.color.multiplyScalar`
- `new Color().setScalar( attributes.Specular.value ).lerp`
- `params.color.clone().multiplyScalar`
- `new Color().setScalar`
- `Math.pow`

**Internal Comments:**
```
// parse specular if there is no roughness - we will interpret the material as 'Phong' in this case
```

<details><summary>Code</summary>

```typescript
parsePhongAttributes( params, attributes, maps ) {

		if ( attributes[ 'Refraction Index' ] ) params.refractionRatio = 0.98 / attributes[ 'Refraction Index' ].value;

		if ( attributes.Diffuse ) params.color.multiplyScalar( attributes.Diffuse.value );

		if ( attributes.Reflection ) {

			params.reflectivity = attributes.Reflection.value;
			params.combine = AddOperation;

		}

		if ( attributes.Luminosity ) {

			params.emissiveIntensity = attributes.Luminosity.value;

			if ( ! maps.emissiveMap && ! maps.map ) {

				params.emissive = params.color;

			} else {

				params.emissive = new Color( 0x808080 );

			}

		}

		// parse specular if there is no roughness - we will interpret the material as 'Phong' in this case
		if ( ! attributes.Roughness && attributes.Specular && ! maps.specularMap ) {

			if ( attributes[ 'Color Highlight' ] ) {

				params.specular = new Color().setScalar( attributes.Specular.value ).lerp( params.color.clone().multiplyScalar( attributes.Specular.value ), attributes[ 'Color Highlight' ].value );

			} else {

				params.specular = new Color().setScalar( attributes.Specular.value );

			}

		}

		if ( params.specular && attributes.Glossiness ) params.shininess = 7 + Math.pow( 2, attributes.Glossiness.value * 12 + 2 );

	}
```
</details>

### `MaterialParser.parseEnvMap(connections: any, maps: any, attributes: any): void`

**Parameters:**

- **`connections`** `any`
- **`maps`** `any`
- **`attributes`** `any`

**Returns:** `void`

**Calls:**

- `this.loadTexture`

**Internal Comments:**
```
// Reflectivity and refraction mapping don't work well together in Phong materials
```

<details><summary>Code</summary>

```typescript
parseEnvMap( connections, maps, attributes ) {

		if ( connections.envMap ) {

			const envMap = this.loadTexture( connections.envMap );

			if ( attributes.transparent && attributes.opacity < 0.999 ) {

				envMap.mapping = EquirectangularRefractionMapping;

				// Reflectivity and refraction mapping don't work well together in Phong materials
				if ( attributes.reflectivity !== undefined ) {

					delete attributes.reflectivity;
					delete attributes.combine;

				}

				if ( attributes.metalness !== undefined ) {

					attributes.metalness = 1; // For most transparent materials metalness should be set to 1 if not otherwise defined. If set to 0 no refraction will be visible

				}

				attributes.opacity = 1; // transparency fades out refraction, forcing opacity to 1 ensures a closer visual match to the material in Lightwave.

			} else envMap.mapping = EquirectangularReflectionMapping;

			maps.envMap = envMap;

		}

	}
```
</details>

### `MaterialParser.getTexturePathByIndex(index: any): string`

**Parameters:**

- **`index`** `any`

**Returns:** `string`

**Calls:**

- `_lwoTree.textures.forEach`

<details><summary>Code</summary>

```typescript
getTexturePathByIndex( index ) {

		let fileName = '';

		if ( ! _lwoTree.textures ) return fileName;

		_lwoTree.textures.forEach( function ( texture ) {

			if ( texture.index === index ) fileName = texture.fileName;

		} );

		return fileName;

	}
```
</details>

### `MaterialParser.loadTexture(path: any): any`

**Parameters:**

- **`path`** `any`

**Returns:** `any`

**Calls:**

- `this.textureLoader.load`
- `console.warn`

<details><summary>Code</summary>

```typescript
loadTexture( path ) {

		if ( ! path ) return null;

		const texture = this.textureLoader.load(
			path,
			undefined,
			undefined,
			function () {

				console.warn( 'LWOLoader: non-standard resource hierarchy. Use \`resourcePath\` parameter to specify root content directory.' );

			}
		);

		return texture;

	}
```
</details>

### `MaterialParser.getWrappingType(num: any): any`

**Parameters:**

- **`num`** `any`

**Returns:** `any`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
getWrappingType( num ) {

		switch ( num ) {

			case 0:
				console.warn( 'LWOLoader: "Reset" texture wrapping type is not supported in three.js' );
				return ClampToEdgeWrapping;
			case 1: return RepeatWrapping;
			case 2: return MirroredRepeatWrapping;
			case 3: return ClampToEdgeWrapping;

		}

	}
```
</details>

### `MaterialParser.getMaterialType(nodeData: any): any`

**Parameters:**

- **`nodeData`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getMaterialType( nodeData ) {

		if ( nodeData.Clearcoat && nodeData.Clearcoat.value > 0 ) return MeshPhysicalMaterial;
		if ( nodeData.Roughness ) return MeshStandardMaterial;
		return MeshPhongMaterial;

	}
```
</details>

### `GeometryParser.parse(geoData: any, layer: any): any`

**Parameters:**

- **`geoData`** `any`
- **`layer`** `any`

**Returns:** `any`

**Calls:**

- `geometry.setAttribute`
- `this.splitIndices`
- `geometry.setIndex`
- `this.parseGroups`
- `geometry.computeVertexNormals`
- `this.parseUVs`
- `this.parseMorphTargets`
- `geometry.translate`

**Internal Comments:**
```
// TODO: z may need to be reversed to account for coordinate system change (x4)
// let userData = geometry.userData;
// geometry = geometry.toNonIndexed()
// geometry.userData = userData;
```

<details><summary>Code</summary>

```typescript
parse( geoData, layer ) {

		const geometry = new BufferGeometry();

		geometry.setAttribute( 'position', new Float32BufferAttribute( geoData.points, 3 ) );

		const indices = this.splitIndices( geoData.vertexIndices, geoData.polygonDimensions );
		geometry.setIndex( indices );

		this.parseGroups( geometry, geoData );

		geometry.computeVertexNormals();

		this.parseUVs( geometry, layer );
		this.parseMorphTargets( geometry, layer );

		// TODO: z may need to be reversed to account for coordinate system change
		geometry.translate( - layer.pivot[ 0 ], - layer.pivot[ 1 ], - layer.pivot[ 2 ] );

		// let userData = geometry.userData;
		// geometry = geometry.toNonIndexed()
		// geometry.userData = userData;

		return geometry;

	}
```
</details>

### `GeometryParser.splitIndices(indices: any, polygonDimensions: any): any[]`

**Parameters:**

- **`indices`** `any`
- **`polygonDimensions`** `any`

**Returns:** `any[]`

**Calls:**

- `polygonDimensions.forEach`
- `remappedIndices.push`
- `console.warn`

<details><summary>Code</summary>

```typescript
splitIndices( indices, polygonDimensions ) {

		const remappedIndices = [];

		let i = 0;
		polygonDimensions.forEach( function ( dim ) {

			if ( dim < 4 ) {

				for ( let k = 0; k < dim; k ++ ) remappedIndices.push( indices[ i + k ] );

			} else if ( dim === 4 ) {

				remappedIndices.push(
					indices[ i ],
					indices[ i + 1 ],
					indices[ i + 2 ],

					indices[ i ],
					indices[ i + 2 ],
					indices[ i + 3 ]

				);

			} else if ( dim > 4 ) {

				for ( let k = 1; k < dim - 1; k ++ ) {

					remappedIndices.push( indices[ i ], indices[ i + k ], indices[ i + k + 1 ] );

				}

				console.warn( 'LWOLoader: polygons with greater than 4 sides are not supported' );

			}

			i += dim;

		} );

		return remappedIndices;

	}
```
</details>

### `GeometryParser.parseGroups(geometry: any, geoData: any): void`

**Parameters:**

- **`geometry`** `any`
- **`geoData`** `any`

**Returns:** `void`

**Calls:**

- `this.splitMaterialIndices`
- `geometry.addGroup`

**Internal Comments:**
```
// the loop above doesn't add the last group, do that here.
// Mat names from TAGS chunk, used to build up an array of materials for this geometry (x5)
```

<details><summary>Code</summary>

```typescript
parseGroups( geometry, geoData ) {

		const tags = _lwoTree.tags;
		const matNames = [];

		let elemSize = 3;
		if ( geoData.type === 'lines' ) elemSize = 2;
		if ( geoData.type === 'points' ) elemSize = 1;

		const remappedIndices = this.splitMaterialIndices( geoData.polygonDimensions, geoData.materialIndices );

		let indexNum = 0; // create new indices in numerical order
		const indexPairs = {}; // original indices mapped to numerical indices

		let prevMaterialIndex;
		let materialIndex;

		let prevStart = 0;
		let currentCount = 0;

		for ( let i = 0; i < remappedIndices.length; i += 2 ) {

			materialIndex = remappedIndices[ i + 1 ];

			if ( i === 0 ) matNames[ indexNum ] = tags[ materialIndex ];

			if ( prevMaterialIndex === undefined ) prevMaterialIndex = materialIndex;

			if ( materialIndex !== prevMaterialIndex ) {

				let currentIndex;
				if ( indexPairs[ tags[ prevMaterialIndex ] ] ) {

					currentIndex = indexPairs[ tags[ prevMaterialIndex ] ];

				} else {

					currentIndex = indexNum;
					indexPairs[ tags[ prevMaterialIndex ] ] = indexNum;
					matNames[ indexNum ] = tags[ prevMaterialIndex ];
					indexNum ++;

				}

				geometry.addGroup( prevStart, currentCount, currentIndex );

				prevStart += currentCount;

				prevMaterialIndex = materialIndex;
				currentCount = 0;

			}

			currentCount += elemSize;

		}

		// the loop above doesn't add the last group, do that here.
		if ( geometry.groups.length > 0 ) {

			let currentIndex;
			if ( indexPairs[ tags[ materialIndex ] ] ) {

				currentIndex = indexPairs[ tags[ materialIndex ] ];

			} else {

				currentIndex = indexNum;
				indexPairs[ tags[ materialIndex ] ] = indexNum;
				matNames[ indexNum ] = tags[ materialIndex ];

			}

			geometry.addGroup( prevStart, currentCount, currentIndex );

		}

		// Mat names from TAGS chunk, used to build up an array of materials for this geometry
		geometry.userData.matNames = matNames;

	}
```
</details>

### `GeometryParser.splitMaterialIndices(polygonDimensions: any, indices: any): any[]`

**Parameters:**

- **`polygonDimensions`** `any`
- **`indices`** `any`

**Returns:** `any[]`

**Calls:**

- `polygonDimensions.forEach`
- `remappedIndices.push`

**Internal Comments:**
```
// ignore > 4 for now
```

<details><summary>Code</summary>

```typescript
splitMaterialIndices( polygonDimensions, indices ) {

		const remappedIndices = [];

		polygonDimensions.forEach( function ( dim, i ) {

			if ( dim <= 3 ) {

				remappedIndices.push( indices[ i * 2 ], indices[ i * 2 + 1 ] );

			} else if ( dim === 4 ) {

				remappedIndices.push( indices[ i * 2 ], indices[ i * 2 + 1 ], indices[ i * 2 ], indices[ i * 2 + 1 ] );

			} else {

				 // ignore > 4 for now
				for ( let k = 0; k < dim - 2; k ++ ) {

					remappedIndices.push( indices[ i * 2 ], indices[ i * 2 + 1 ] );

				}

			}

		} );

		return remappedIndices;

	}
```
</details>

### `GeometryParser.parseUVs(geometry: any, layer: any): void`

**Parameters:**

- **`geometry`** `any`
- **`layer`** `any`

**Returns:** `void`

**Calls:**

- `Array.from`
- `Array`
- `uvIndices.forEach`
- `geometry.setAttribute`

**Internal Comments:**
```
// start by creating a UV map set to zero for the whole geometry (x2)
```

<details><summary>Code</summary>

```typescript
parseUVs( geometry, layer ) {

		// start by creating a UV map set to zero for the whole geometry
		const remappedUVs = Array.from( Array( geometry.attributes.position.count * 2 ), function () {

			return 0;

		} );

		for ( const name in layer.uvs ) {

			const uvs = layer.uvs[ name ].uvs;
			const uvIndices = layer.uvs[ name ].uvIndices;

			uvIndices.forEach( function ( i, j ) {

				remappedUVs[ i * 2 ] = uvs[ j * 2 ];
				remappedUVs[ i * 2 + 1 ] = uvs[ j * 2 + 1 ];

			} );

		}

		geometry.setAttribute( 'uv', new Float32BufferAttribute( remappedUVs, 2 ) );

	}
```
</details>

### `GeometryParser.parseMorphTargets(geometry: any, layer: any): void`

**Parameters:**

- **`geometry`** `any`
- **`layer`** `any`

**Returns:** `void`

**Calls:**

- `geometry.attributes.position.array.slice`
- `morphIndices.forEach`

<details><summary>Code</summary>

```typescript
parseMorphTargets( geometry, layer ) {

		let num = 0;
		for ( const name in layer.morphTargets ) {

			const remappedPoints = geometry.attributes.position.array.slice();

			if ( ! geometry.morphAttributes.position ) geometry.morphAttributes.position = [];

			const morphPoints = layer.morphTargets[ name ].points;
			const morphIndices = layer.morphTargets[ name ].indices;
			const type = layer.morphTargets[ name ].type;

			morphIndices.forEach( function ( i, j ) {

				if ( type === 'relative' ) {

					remappedPoints[ i * 3 ] += morphPoints[ j * 3 ];
					remappedPoints[ i * 3 + 1 ] += morphPoints[ j * 3 + 1 ];
					remappedPoints[ i * 3 + 2 ] += morphPoints[ j * 3 + 2 ];

				} else {

					remappedPoints[ i * 3 ] = morphPoints[ j * 3 ];
					remappedPoints[ i * 3 + 1 ] = morphPoints[ j * 3 + 1 ];
					remappedPoints[ i * 3 + 2 ] = morphPoints[ j * 3 + 2 ];

				}

			} );

			geometry.morphAttributes.position[ num ] = new Float32BufferAttribute( remappedPoints, 3 );
			geometry.morphAttributes.position[ num ].name = name;

			num ++;

		}

		geometry.morphTargetsRelative = false;

	}
```
</details>

### `extractParentUrl(url: any, dir: any): any`

**Parameters:**

- **`url`** `any`
- **`dir`** `any`

**Returns:** `any`

**Calls:**

- `url.indexOf`
- `url.slice`

<details><summary>Code</summary>

```typescript
function extractParentUrl( url, dir ) {

	const index = url.indexOf( dir );

	if ( index === - 1 ) return './';

	return url.slice( 0, index );

}
```
</details>


---

## Classes

### `LWOLoader`

<details><summary>Class Code</summary>

```ts
class LWOLoader extends Loader {

	/**
	 * Constructs a new LWO loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Starts loading from the given URL and passes the loaded LWO asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({meshes:Array<Mesh>,materials:Array<Material>})} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const path = ( scope.path === '' ) ? extractParentUrl( url, 'Objects' ) : scope.path;

		// give the mesh a default name based on the filename
		const modelName = url.split( path ).pop().split( '.' )[ 0 ];

		const loader = new FileLoader( this.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );

		loader.load( url, function ( buffer ) {

			// console.time( 'Total parsing: ' );

			try {

				onLoad( scope.parse( buffer, path, modelName ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

			// console.timeEnd( 'Total parsing: ' );

		}, onProgress, onError );

	}

	/**
	 * Parses the given LWO data and returns the resulting meshes and materials.
	 *
	 * @param {ArrayBuffer} iffBuffer - The raw LWO data as an array buffer.
	 * @param {string} path - The URL base path.
	 * @param {string} modelName - The model name.
	 * @return {{meshes:Array<Mesh>,materials:Array<Material>}} An object holding the parse meshes and materials.
	 */
	parse( iffBuffer, path, modelName ) {

		_lwoTree = new IFFParser().parse( iffBuffer );

		// console.log( 'lwoTree', lwoTree );

		const textureLoader = new TextureLoader( this.manager ).setPath( this.resourcePath || path ).setCrossOrigin( this.crossOrigin );

		return new LWOTreeParser( textureLoader ).parse( modelName );

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: { meshes: Mesh[]; materials: Material[]; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const path = ( scope.path === '' ) ? extractParentUrl( url, 'Objects' ) : scope.path;

		// give the mesh a default name based on the filename
		const modelName = url.split( path ).pop().split( '.' )[ 0 ];

		const loader = new FileLoader( this.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );

		loader.load( url, function ( buffer ) {

			// console.time( 'Total parsing: ' );

			try {

				onLoad( scope.parse( buffer, path, modelName ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

			// console.timeEnd( 'Total parsing: ' );

		}, onProgress, onError );

	}
```
</details>

##### `parse(iffBuffer: ArrayBuffer, path: string, modelName: string): { meshes: Mesh[]; materials: Material[]; }`

<details><summary>Code</summary>

```ts
parse( iffBuffer, path, modelName ) {

		_lwoTree = new IFFParser().parse( iffBuffer );

		// console.log( 'lwoTree', lwoTree );

		const textureLoader = new TextureLoader( this.manager ).setPath( this.resourcePath || path ).setCrossOrigin( this.crossOrigin );

		return new LWOTreeParser( textureLoader ).parse( modelName );

	}
```
</details>

### `LWOTreeParser`

<details><summary>Class Code</summary>

```ts
class LWOTreeParser {

	constructor( textureLoader ) {

		this.textureLoader = textureLoader;

	}

	parse( modelName ) {

		this.materials = new MaterialParser( this.textureLoader ).parse();
		this.defaultLayerName = modelName;

		this.meshes = this.parseLayers();

		return {
			materials: this.materials,
			meshes: this.meshes,
		};

	}

	parseLayers() {

		// array of all meshes for building hierarchy
		const meshes = [];

		// final array containing meshes with scene graph hierarchy set up
		const finalMeshes = [];

		const geometryParser = new GeometryParser();

		const scope = this;
		_lwoTree.layers.forEach( function ( layer ) {

			const geometry = geometryParser.parse( layer.geometry, layer );

			const mesh = scope.parseMesh( geometry, layer );

			meshes[ layer.number ] = mesh;

			if ( layer.parent === - 1 ) finalMeshes.push( mesh );
			else meshes[ layer.parent ].add( mesh );


		} );

		this.applyPivots( finalMeshes );

		return finalMeshes;

	}

	parseMesh( geometry, layer ) {

		let mesh;

		const materials = this.getMaterials( geometry.userData.matNames, layer.geometry.type );

		if ( layer.geometry.type === 'points' ) mesh = new Points( geometry, materials );
		else if ( layer.geometry.type === 'lines' ) mesh = new LineSegments( geometry, materials );
		else mesh = new Mesh( geometry, materials );

		if ( layer.name ) mesh.name = layer.name;
		else mesh.name = this.defaultLayerName + '_layer_' + layer.number;

		mesh.userData.pivot = layer.pivot;

		return mesh;

	}

	// TODO: may need to be reversed in z to convert LWO to three.js coordinates
	applyPivots( meshes ) {

		meshes.forEach( function ( mesh ) {

			mesh.traverse( function ( child ) {

				const pivot = child.userData.pivot;

				child.position.x += pivot[ 0 ];
				child.position.y += pivot[ 1 ];
				child.position.z += pivot[ 2 ];

				if ( child.parent ) {

					const parentPivot = child.parent.userData.pivot;

					child.position.x -= parentPivot[ 0 ];
					child.position.y -= parentPivot[ 1 ];
					child.position.z -= parentPivot[ 2 ];

				}

			} );

		} );

	}

	getMaterials( namesArray, type ) {

		const materials = [];

		const scope = this;

		namesArray.forEach( function ( name, i ) {

			materials[ i ] = scope.getMaterialByName( name );

		} );

		// convert materials to line or point mats if required
		if ( type === 'points' || type === 'lines' ) {

			materials.forEach( function ( mat, i ) {

				const spec = {
					color: mat.color,
				};

				if ( type === 'points' ) {

					spec.size = 0.1;
					spec.map = mat.map;
					materials[ i ] = new PointsMaterial( spec );

				} else if ( type === 'lines' ) {

					materials[ i ] = new LineBasicMaterial( spec );

				}

			} );

		}

		// if there is only one material, return that directly instead of array
		const filtered = materials.filter( Boolean );
		if ( filtered.length === 1 ) return filtered[ 0 ];

		return materials;

	}

	getMaterialByName( name ) {

		return this.materials.filter( function ( m ) {

			return m.name === name;

		} )[ 0 ];

	}

}
```
</details>

#### Methods

##### `parse(modelName: any): { materials: any[]; meshes: any[]; }`

<details><summary>Code</summary>

```ts
parse( modelName ) {

		this.materials = new MaterialParser( this.textureLoader ).parse();
		this.defaultLayerName = modelName;

		this.meshes = this.parseLayers();

		return {
			materials: this.materials,
			meshes: this.meshes,
		};

	}
```
</details>

##### `parseLayers(): any[]`

<details><summary>Code</summary>

```ts
parseLayers() {

		// array of all meshes for building hierarchy
		const meshes = [];

		// final array containing meshes with scene graph hierarchy set up
		const finalMeshes = [];

		const geometryParser = new GeometryParser();

		const scope = this;
		_lwoTree.layers.forEach( function ( layer ) {

			const geometry = geometryParser.parse( layer.geometry, layer );

			const mesh = scope.parseMesh( geometry, layer );

			meshes[ layer.number ] = mesh;

			if ( layer.parent === - 1 ) finalMeshes.push( mesh );
			else meshes[ layer.parent ].add( mesh );


		} );

		this.applyPivots( finalMeshes );

		return finalMeshes;

	}
```
</details>

##### `parseMesh(geometry: any, layer: any): any`

<details><summary>Code</summary>

```ts
parseMesh( geometry, layer ) {

		let mesh;

		const materials = this.getMaterials( geometry.userData.matNames, layer.geometry.type );

		if ( layer.geometry.type === 'points' ) mesh = new Points( geometry, materials );
		else if ( layer.geometry.type === 'lines' ) mesh = new LineSegments( geometry, materials );
		else mesh = new Mesh( geometry, materials );

		if ( layer.name ) mesh.name = layer.name;
		else mesh.name = this.defaultLayerName + '_layer_' + layer.number;

		mesh.userData.pivot = layer.pivot;

		return mesh;

	}
```
</details>

##### `applyPivots(meshes: any): void`

<details><summary>Code</summary>

```ts
applyPivots( meshes ) {

		meshes.forEach( function ( mesh ) {

			mesh.traverse( function ( child ) {

				const pivot = child.userData.pivot;

				child.position.x += pivot[ 0 ];
				child.position.y += pivot[ 1 ];
				child.position.z += pivot[ 2 ];

				if ( child.parent ) {

					const parentPivot = child.parent.userData.pivot;

					child.position.x -= parentPivot[ 0 ];
					child.position.y -= parentPivot[ 1 ];
					child.position.z -= parentPivot[ 2 ];

				}

			} );

		} );

	}
```
</details>

##### `getMaterials(namesArray: any, type: any): any`

<details><summary>Code</summary>

```ts
getMaterials( namesArray, type ) {

		const materials = [];

		const scope = this;

		namesArray.forEach( function ( name, i ) {

			materials[ i ] = scope.getMaterialByName( name );

		} );

		// convert materials to line or point mats if required
		if ( type === 'points' || type === 'lines' ) {

			materials.forEach( function ( mat, i ) {

				const spec = {
					color: mat.color,
				};

				if ( type === 'points' ) {

					spec.size = 0.1;
					spec.map = mat.map;
					materials[ i ] = new PointsMaterial( spec );

				} else if ( type === 'lines' ) {

					materials[ i ] = new LineBasicMaterial( spec );

				}

			} );

		}

		// if there is only one material, return that directly instead of array
		const filtered = materials.filter( Boolean );
		if ( filtered.length === 1 ) return filtered[ 0 ];

		return materials;

	}
```
</details>

##### `getMaterialByName(name: any): any`

<details><summary>Code</summary>

```ts
getMaterialByName( name ) {

		return this.materials.filter( function ( m ) {

			return m.name === name;

		} )[ 0 ];

	}
```
</details>

### `MaterialParser`

<details><summary>Class Code</summary>

```ts
class MaterialParser {

	constructor( textureLoader ) {

		this.textureLoader = textureLoader;

	}

	parse() {

		const materials = [];
		this.textures = {};

		for ( const name in _lwoTree.materials ) {

			if ( _lwoTree.format === 'LWO3' ) {

				materials.push( this.parseMaterial( _lwoTree.materials[ name ], name, _lwoTree.textures ) );

			} else if ( _lwoTree.format === 'LWO2' ) {

				materials.push( this.parseMaterialLwo2( _lwoTree.materials[ name ], name, _lwoTree.textures ) );

			}

		}

		return materials;

	}

	parseMaterial( materialData, name, textures ) {

		let params = {
			name: name,
			side: this.getSide( materialData.attributes ),
			flatShading: this.getSmooth( materialData.attributes ),
		};

		const connections = this.parseConnections( materialData.connections, materialData.nodes );

		const maps = this.parseTextureNodes( connections.maps );

		this.parseAttributeImageMaps( connections.attributes, textures, maps );

		const attributes = this.parseAttributes( connections.attributes, maps );

		this.parseEnvMap( connections, maps, attributes );

		params = Object.assign( maps, params );
		params = Object.assign( params, attributes );

		const materialType = this.getMaterialType( connections.attributes );

		if ( materialType !== MeshPhongMaterial ) delete params.refractionRatio; // PBR materials do not support "refractionRatio"

		return new materialType( params );

	}

	parseMaterialLwo2( materialData, name/*, textures*/ ) {

		let params = {
			name: name,
			side: this.getSide( materialData.attributes ),
			flatShading: this.getSmooth( materialData.attributes ),
		};

		const attributes = this.parseAttributes( materialData.attributes, {} );
		params = Object.assign( params, attributes );
		return new MeshPhongMaterial( params );

	}

	// Note: converting from left to right handed coords by switching x -> -x in vertices, and
	// then switching mat FrontSide -> BackSide
	// NB: this means that FrontSide and BackSide have been switched!
	getSide( attributes ) {

		if ( ! attributes.side ) return BackSide;

		switch ( attributes.side ) {

			case 0:
			case 1:
				return BackSide;
			case 2: return FrontSide;
			case 3: return DoubleSide;

		}

	}

	getSmooth( attributes ) {

		if ( ! attributes.smooth ) return true;
		return ! attributes.smooth;

	}

	parseConnections( connections, nodes ) {

		const materialConnections = {
			maps: {}
		};

		const inputName = connections.inputName;
		const inputNodeName = connections.inputNodeName;
		const nodeName = connections.nodeName;

		const scope = this;
		inputName.forEach( function ( name, index ) {

			if ( name === 'Material' ) {

				const matNode = scope.getNodeByRefName( inputNodeName[ index ], nodes );
				materialConnections.attributes = matNode.attributes;
				materialConnections.envMap = matNode.fileName;
				materialConnections.name = inputNodeName[ index ];

			}

		} );

		nodeName.forEach( function ( name, index ) {

			if ( name === materialConnections.name ) {

				materialConnections.maps[ inputName[ index ] ] = scope.getNodeByRefName( inputNodeName[ index ], nodes );

			}

		} );

		return materialConnections;

	}

	getNodeByRefName( refName, nodes ) {

		for ( const name in nodes ) {

			if ( nodes[ name ].refName === refName ) return nodes[ name ];

		}

	}

	parseTextureNodes( textureNodes ) {

		const maps = {};

		for ( const name in textureNodes ) {

			const node = textureNodes[ name ];
			const path = node.fileName;

			if ( ! path ) return;

			const texture = this.loadTexture( path );

			if ( node.widthWrappingMode !== undefined ) texture.wrapS = this.getWrappingType( node.widthWrappingMode );
			if ( node.heightWrappingMode !== undefined ) texture.wrapT = this.getWrappingType( node.heightWrappingMode );

			switch ( name ) {

				case 'Color':
					maps.map = texture;
					maps.map.colorSpace = SRGBColorSpace;
					break;
				case 'Roughness':
					maps.roughnessMap = texture;
					maps.roughness = 1;
					break;
				case 'Specular':
					maps.specularMap = texture;
					maps.specularMap.colorSpace = SRGBColorSpace;
					maps.specular = 0xffffff;
					break;
				case 'Luminous':
					maps.emissiveMap = texture;
					maps.emissiveMap.colorSpace = SRGBColorSpace;
					maps.emissive = 0x808080;
					break;
				case 'Luminous Color':
					maps.emissive = 0x808080;
					break;
				case 'Metallic':
					maps.metalnessMap = texture;
					maps.metalness = 1;
					break;
				case 'Transparency':
				case 'Alpha':
					maps.alphaMap = texture;
					maps.transparent = true;
					break;
				case 'Normal':
					maps.normalMap = texture;
					if ( node.amplitude !== undefined ) maps.normalScale = new Vector2( node.amplitude, node.amplitude );
					break;
				case 'Bump':
					maps.bumpMap = texture;
					break;

			}

		}

		// LWO BSDF materials can have both spec and rough, but this is not valid in three
		if ( maps.roughnessMap && maps.specularMap ) delete maps.specularMap;

		return maps;

	}

	// maps can also be defined on individual material attributes, parse those here
	// This occurs on Standard (Phong) surfaces
	parseAttributeImageMaps( attributes, textures, maps ) {

		for ( const name in attributes ) {

			const attribute = attributes[ name ];

			if ( attribute.maps ) {

				const mapData = attribute.maps[ 0 ];

				const path = this.getTexturePathByIndex( mapData.imageIndex );
				if ( ! path ) return;

				const texture = this.loadTexture( path );

				if ( mapData.wrap !== undefined ) texture.wrapS = this.getWrappingType( mapData.wrap.w );
				if ( mapData.wrap !== undefined ) texture.wrapT = this.getWrappingType( mapData.wrap.h );

				switch ( name ) {

					case 'Color':
						maps.map = texture;
						maps.map.colorSpace = SRGBColorSpace;
						break;
					case 'Diffuse':
						maps.aoMap = texture;
						break;
					case 'Roughness':
						maps.roughnessMap = texture;
						maps.roughness = 1;
						break;
					case 'Specular':
						maps.specularMap = texture;
						maps.specularMap.colorSpace = SRGBColorSpace;
						maps.specular = 0xffffff;
						break;
					case 'Luminosity':
						maps.emissiveMap = texture;
						maps.emissiveMap.colorSpace = SRGBColorSpace;
						maps.emissive = 0x808080;
						break;
					case 'Metallic':
						maps.metalnessMap = texture;
						maps.metalness = 1;
						break;
					case 'Transparency':
					case 'Alpha':
						maps.alphaMap = texture;
						maps.transparent = true;
						break;
					case 'Normal':
						maps.normalMap = texture;
						break;
					case 'Bump':
						maps.bumpMap = texture;
						break;

				}

			}

		}

	}

	parseAttributes( attributes, maps ) {

		const params = {};

		// don't use color data if color map is present
		if ( attributes.Color && ! maps.map ) {

			params.color = new Color().fromArray( attributes.Color.value );

		} else {

			params.color = new Color();

		}


		if ( attributes.Transparency && attributes.Transparency.value !== 0 ) {

			params.opacity = 1 - attributes.Transparency.value;
			params.transparent = true;

		}

		if ( attributes[ 'Bump Height' ] ) params.bumpScale = attributes[ 'Bump Height' ].value * 0.1;

		this.parsePhysicalAttributes( params, attributes, maps );
		this.parseStandardAttributes( params, attributes, maps );
		this.parsePhongAttributes( params, attributes, maps );

		return params;

	}

	parsePhysicalAttributes( params, attributes/*, maps*/ ) {

		if ( attributes.Clearcoat && attributes.Clearcoat.value > 0 ) {

			params.clearcoat = attributes.Clearcoat.value;

			if ( attributes[ 'Clearcoat Gloss' ] ) {

				params.clearcoatRoughness = 0.5 * ( 1 - attributes[ 'Clearcoat Gloss' ].value );

			}

		}

	}

	parseStandardAttributes( params, attributes, maps ) {


		if ( attributes.Luminous ) {

			params.emissiveIntensity = attributes.Luminous.value;

			if ( attributes[ 'Luminous Color' ] && ! maps.emissive ) {

				params.emissive = new Color().fromArray( attributes[ 'Luminous Color' ].value );

			} else {

				params.emissive = new Color( 0x808080 );

			}

		}

		if ( attributes.Roughness && ! maps.roughnessMap ) params.roughness = attributes.Roughness.value;
		if ( attributes.Metallic && ! maps.metalnessMap ) params.metalness = attributes.Metallic.value;

	}

	parsePhongAttributes( params, attributes, maps ) {

		if ( attributes[ 'Refraction Index' ] ) params.refractionRatio = 0.98 / attributes[ 'Refraction Index' ].value;

		if ( attributes.Diffuse ) params.color.multiplyScalar( attributes.Diffuse.value );

		if ( attributes.Reflection ) {

			params.reflectivity = attributes.Reflection.value;
			params.combine = AddOperation;

		}

		if ( attributes.Luminosity ) {

			params.emissiveIntensity = attributes.Luminosity.value;

			if ( ! maps.emissiveMap && ! maps.map ) {

				params.emissive = params.color;

			} else {

				params.emissive = new Color( 0x808080 );

			}

		}

		// parse specular if there is no roughness - we will interpret the material as 'Phong' in this case
		if ( ! attributes.Roughness && attributes.Specular && ! maps.specularMap ) {

			if ( attributes[ 'Color Highlight' ] ) {

				params.specular = new Color().setScalar( attributes.Specular.value ).lerp( params.color.clone().multiplyScalar( attributes.Specular.value ), attributes[ 'Color Highlight' ].value );

			} else {

				params.specular = new Color().setScalar( attributes.Specular.value );

			}

		}

		if ( params.specular && attributes.Glossiness ) params.shininess = 7 + Math.pow( 2, attributes.Glossiness.value * 12 + 2 );

	}

	parseEnvMap( connections, maps, attributes ) {

		if ( connections.envMap ) {

			const envMap = this.loadTexture( connections.envMap );

			if ( attributes.transparent && attributes.opacity < 0.999 ) {

				envMap.mapping = EquirectangularRefractionMapping;

				// Reflectivity and refraction mapping don't work well together in Phong materials
				if ( attributes.reflectivity !== undefined ) {

					delete attributes.reflectivity;
					delete attributes.combine;

				}

				if ( attributes.metalness !== undefined ) {

					attributes.metalness = 1; // For most transparent materials metalness should be set to 1 if not otherwise defined. If set to 0 no refraction will be visible

				}

				attributes.opacity = 1; // transparency fades out refraction, forcing opacity to 1 ensures a closer visual match to the material in Lightwave.

			} else envMap.mapping = EquirectangularReflectionMapping;

			maps.envMap = envMap;

		}

	}

	// get texture defined at top level by its index
	getTexturePathByIndex( index ) {

		let fileName = '';

		if ( ! _lwoTree.textures ) return fileName;

		_lwoTree.textures.forEach( function ( texture ) {

			if ( texture.index === index ) fileName = texture.fileName;

		} );

		return fileName;

	}

	loadTexture( path ) {

		if ( ! path ) return null;

		const texture = this.textureLoader.load(
			path,
			undefined,
			undefined,
			function () {

				console.warn( 'LWOLoader: non-standard resource hierarchy. Use \`resourcePath\` parameter to specify root content directory.' );

			}
		);

		return texture;

	}

	// 0 = Reset, 1 = Repeat, 2 = Mirror, 3 = Edge
	getWrappingType( num ) {

		switch ( num ) {

			case 0:
				console.warn( 'LWOLoader: "Reset" texture wrapping type is not supported in three.js' );
				return ClampToEdgeWrapping;
			case 1: return RepeatWrapping;
			case 2: return MirroredRepeatWrapping;
			case 3: return ClampToEdgeWrapping;

		}

	}

	getMaterialType( nodeData ) {

		if ( nodeData.Clearcoat && nodeData.Clearcoat.value > 0 ) return MeshPhysicalMaterial;
		if ( nodeData.Roughness ) return MeshStandardMaterial;
		return MeshPhongMaterial;

	}

}
```
</details>

#### Methods

##### `parse(): any[]`

<details><summary>Code</summary>

```ts
parse() {

		const materials = [];
		this.textures = {};

		for ( const name in _lwoTree.materials ) {

			if ( _lwoTree.format === 'LWO3' ) {

				materials.push( this.parseMaterial( _lwoTree.materials[ name ], name, _lwoTree.textures ) );

			} else if ( _lwoTree.format === 'LWO2' ) {

				materials.push( this.parseMaterialLwo2( _lwoTree.materials[ name ], name, _lwoTree.textures ) );

			}

		}

		return materials;

	}
```
</details>

##### `parseMaterial(materialData: any, name: any, textures: any): any`

<details><summary>Code</summary>

```ts
parseMaterial( materialData, name, textures ) {

		let params = {
			name: name,
			side: this.getSide( materialData.attributes ),
			flatShading: this.getSmooth( materialData.attributes ),
		};

		const connections = this.parseConnections( materialData.connections, materialData.nodes );

		const maps = this.parseTextureNodes( connections.maps );

		this.parseAttributeImageMaps( connections.attributes, textures, maps );

		const attributes = this.parseAttributes( connections.attributes, maps );

		this.parseEnvMap( connections, maps, attributes );

		params = Object.assign( maps, params );
		params = Object.assign( params, attributes );

		const materialType = this.getMaterialType( connections.attributes );

		if ( materialType !== MeshPhongMaterial ) delete params.refractionRatio; // PBR materials do not support "refractionRatio"

		return new materialType( params );

	}
```
</details>

##### `parseMaterialLwo2(materialData: any, name: any): any`

<details><summary>Code</summary>

```ts
parseMaterialLwo2( materialData, name/*, textures*/ ) {

		let params = {
			name: name,
			side: this.getSide( materialData.attributes ),
			flatShading: this.getSmooth( materialData.attributes ),
		};

		const attributes = this.parseAttributes( materialData.attributes, {} );
		params = Object.assign( params, attributes );
		return new MeshPhongMaterial( params );

	}
```
</details>

##### `getSide(attributes: any): any`

<details><summary>Code</summary>

```ts
getSide( attributes ) {

		if ( ! attributes.side ) return BackSide;

		switch ( attributes.side ) {

			case 0:
			case 1:
				return BackSide;
			case 2: return FrontSide;
			case 3: return DoubleSide;

		}

	}
```
</details>

##### `getSmooth(attributes: any): boolean`

<details><summary>Code</summary>

```ts
getSmooth( attributes ) {

		if ( ! attributes.smooth ) return true;
		return ! attributes.smooth;

	}
```
</details>

##### `parseConnections(connections: any, nodes: any): { maps: {}; }`

<details><summary>Code</summary>

```ts
parseConnections( connections, nodes ) {

		const materialConnections = {
			maps: {}
		};

		const inputName = connections.inputName;
		const inputNodeName = connections.inputNodeName;
		const nodeName = connections.nodeName;

		const scope = this;
		inputName.forEach( function ( name, index ) {

			if ( name === 'Material' ) {

				const matNode = scope.getNodeByRefName( inputNodeName[ index ], nodes );
				materialConnections.attributes = matNode.attributes;
				materialConnections.envMap = matNode.fileName;
				materialConnections.name = inputNodeName[ index ];

			}

		} );

		nodeName.forEach( function ( name, index ) {

			if ( name === materialConnections.name ) {

				materialConnections.maps[ inputName[ index ] ] = scope.getNodeByRefName( inputNodeName[ index ], nodes );

			}

		} );

		return materialConnections;

	}
```
</details>

##### `getNodeByRefName(refName: any, nodes: any): any`

<details><summary>Code</summary>

```ts
getNodeByRefName( refName, nodes ) {

		for ( const name in nodes ) {

			if ( nodes[ name ].refName === refName ) return nodes[ name ];

		}

	}
```
</details>

##### `parseTextureNodes(textureNodes: any): { map: any; roughnessMap: any; roughness: number; specularMap: any; specular: number; emissiveMap: any; emissive: number; metalnessMap: any; metalness: number; alphaMap: any; transparent: boolean; normalMap: any; normalScale: any; bumpMap: any; }`

<details><summary>Code</summary>

```ts
parseTextureNodes( textureNodes ) {

		const maps = {};

		for ( const name in textureNodes ) {

			const node = textureNodes[ name ];
			const path = node.fileName;

			if ( ! path ) return;

			const texture = this.loadTexture( path );

			if ( node.widthWrappingMode !== undefined ) texture.wrapS = this.getWrappingType( node.widthWrappingMode );
			if ( node.heightWrappingMode !== undefined ) texture.wrapT = this.getWrappingType( node.heightWrappingMode );

			switch ( name ) {

				case 'Color':
					maps.map = texture;
					maps.map.colorSpace = SRGBColorSpace;
					break;
				case 'Roughness':
					maps.roughnessMap = texture;
					maps.roughness = 1;
					break;
				case 'Specular':
					maps.specularMap = texture;
					maps.specularMap.colorSpace = SRGBColorSpace;
					maps.specular = 0xffffff;
					break;
				case 'Luminous':
					maps.emissiveMap = texture;
					maps.emissiveMap.colorSpace = SRGBColorSpace;
					maps.emissive = 0x808080;
					break;
				case 'Luminous Color':
					maps.emissive = 0x808080;
					break;
				case 'Metallic':
					maps.metalnessMap = texture;
					maps.metalness = 1;
					break;
				case 'Transparency':
				case 'Alpha':
					maps.alphaMap = texture;
					maps.transparent = true;
					break;
				case 'Normal':
					maps.normalMap = texture;
					if ( node.amplitude !== undefined ) maps.normalScale = new Vector2( node.amplitude, node.amplitude );
					break;
				case 'Bump':
					maps.bumpMap = texture;
					break;

			}

		}

		// LWO BSDF materials can have both spec and rough, but this is not valid in three
		if ( maps.roughnessMap && maps.specularMap ) delete maps.specularMap;

		return maps;

	}
```
</details>

##### `parseAttributeImageMaps(attributes: any, textures: any, maps: any): void`

<details><summary>Code</summary>

```ts
parseAttributeImageMaps( attributes, textures, maps ) {

		for ( const name in attributes ) {

			const attribute = attributes[ name ];

			if ( attribute.maps ) {

				const mapData = attribute.maps[ 0 ];

				const path = this.getTexturePathByIndex( mapData.imageIndex );
				if ( ! path ) return;

				const texture = this.loadTexture( path );

				if ( mapData.wrap !== undefined ) texture.wrapS = this.getWrappingType( mapData.wrap.w );
				if ( mapData.wrap !== undefined ) texture.wrapT = this.getWrappingType( mapData.wrap.h );

				switch ( name ) {

					case 'Color':
						maps.map = texture;
						maps.map.colorSpace = SRGBColorSpace;
						break;
					case 'Diffuse':
						maps.aoMap = texture;
						break;
					case 'Roughness':
						maps.roughnessMap = texture;
						maps.roughness = 1;
						break;
					case 'Specular':
						maps.specularMap = texture;
						maps.specularMap.colorSpace = SRGBColorSpace;
						maps.specular = 0xffffff;
						break;
					case 'Luminosity':
						maps.emissiveMap = texture;
						maps.emissiveMap.colorSpace = SRGBColorSpace;
						maps.emissive = 0x808080;
						break;
					case 'Metallic':
						maps.metalnessMap = texture;
						maps.metalness = 1;
						break;
					case 'Transparency':
					case 'Alpha':
						maps.alphaMap = texture;
						maps.transparent = true;
						break;
					case 'Normal':
						maps.normalMap = texture;
						break;
					case 'Bump':
						maps.bumpMap = texture;
						break;

				}

			}

		}

	}
```
</details>

##### `parseAttributes(attributes: any, maps: any): { color: any; opacity: number; transparent: boolean; bumpScale: number; }`

<details><summary>Code</summary>

```ts
parseAttributes( attributes, maps ) {

		const params = {};

		// don't use color data if color map is present
		if ( attributes.Color && ! maps.map ) {

			params.color = new Color().fromArray( attributes.Color.value );

		} else {

			params.color = new Color();

		}


		if ( attributes.Transparency && attributes.Transparency.value !== 0 ) {

			params.opacity = 1 - attributes.Transparency.value;
			params.transparent = true;

		}

		if ( attributes[ 'Bump Height' ] ) params.bumpScale = attributes[ 'Bump Height' ].value * 0.1;

		this.parsePhysicalAttributes( params, attributes, maps );
		this.parseStandardAttributes( params, attributes, maps );
		this.parsePhongAttributes( params, attributes, maps );

		return params;

	}
```
</details>

##### `parsePhysicalAttributes(params: any, attributes: any): void`

<details><summary>Code</summary>

```ts
parsePhysicalAttributes( params, attributes/*, maps*/ ) {

		if ( attributes.Clearcoat && attributes.Clearcoat.value > 0 ) {

			params.clearcoat = attributes.Clearcoat.value;

			if ( attributes[ 'Clearcoat Gloss' ] ) {

				params.clearcoatRoughness = 0.5 * ( 1 - attributes[ 'Clearcoat Gloss' ].value );

			}

		}

	}
```
</details>

##### `parseStandardAttributes(params: any, attributes: any, maps: any): void`

<details><summary>Code</summary>

```ts
parseStandardAttributes( params, attributes, maps ) {


		if ( attributes.Luminous ) {

			params.emissiveIntensity = attributes.Luminous.value;

			if ( attributes[ 'Luminous Color' ] && ! maps.emissive ) {

				params.emissive = new Color().fromArray( attributes[ 'Luminous Color' ].value );

			} else {

				params.emissive = new Color( 0x808080 );

			}

		}

		if ( attributes.Roughness && ! maps.roughnessMap ) params.roughness = attributes.Roughness.value;
		if ( attributes.Metallic && ! maps.metalnessMap ) params.metalness = attributes.Metallic.value;

	}
```
</details>

##### `parsePhongAttributes(params: any, attributes: any, maps: any): void`

<details><summary>Code</summary>

```ts
parsePhongAttributes( params, attributes, maps ) {

		if ( attributes[ 'Refraction Index' ] ) params.refractionRatio = 0.98 / attributes[ 'Refraction Index' ].value;

		if ( attributes.Diffuse ) params.color.multiplyScalar( attributes.Diffuse.value );

		if ( attributes.Reflection ) {

			params.reflectivity = attributes.Reflection.value;
			params.combine = AddOperation;

		}

		if ( attributes.Luminosity ) {

			params.emissiveIntensity = attributes.Luminosity.value;

			if ( ! maps.emissiveMap && ! maps.map ) {

				params.emissive = params.color;

			} else {

				params.emissive = new Color( 0x808080 );

			}

		}

		// parse specular if there is no roughness - we will interpret the material as 'Phong' in this case
		if ( ! attributes.Roughness && attributes.Specular && ! maps.specularMap ) {

			if ( attributes[ 'Color Highlight' ] ) {

				params.specular = new Color().setScalar( attributes.Specular.value ).lerp( params.color.clone().multiplyScalar( attributes.Specular.value ), attributes[ 'Color Highlight' ].value );

			} else {

				params.specular = new Color().setScalar( attributes.Specular.value );

			}

		}

		if ( params.specular && attributes.Glossiness ) params.shininess = 7 + Math.pow( 2, attributes.Glossiness.value * 12 + 2 );

	}
```
</details>

##### `parseEnvMap(connections: any, maps: any, attributes: any): void`

<details><summary>Code</summary>

```ts
parseEnvMap( connections, maps, attributes ) {

		if ( connections.envMap ) {

			const envMap = this.loadTexture( connections.envMap );

			if ( attributes.transparent && attributes.opacity < 0.999 ) {

				envMap.mapping = EquirectangularRefractionMapping;

				// Reflectivity and refraction mapping don't work well together in Phong materials
				if ( attributes.reflectivity !== undefined ) {

					delete attributes.reflectivity;
					delete attributes.combine;

				}

				if ( attributes.metalness !== undefined ) {

					attributes.metalness = 1; // For most transparent materials metalness should be set to 1 if not otherwise defined. If set to 0 no refraction will be visible

				}

				attributes.opacity = 1; // transparency fades out refraction, forcing opacity to 1 ensures a closer visual match to the material in Lightwave.

			} else envMap.mapping = EquirectangularReflectionMapping;

			maps.envMap = envMap;

		}

	}
```
</details>

##### `getTexturePathByIndex(index: any): string`

<details><summary>Code</summary>

```ts
getTexturePathByIndex( index ) {

		let fileName = '';

		if ( ! _lwoTree.textures ) return fileName;

		_lwoTree.textures.forEach( function ( texture ) {

			if ( texture.index === index ) fileName = texture.fileName;

		} );

		return fileName;

	}
```
</details>

##### `loadTexture(path: any): any`

<details><summary>Code</summary>

```ts
loadTexture( path ) {

		if ( ! path ) return null;

		const texture = this.textureLoader.load(
			path,
			undefined,
			undefined,
			function () {

				console.warn( 'LWOLoader: non-standard resource hierarchy. Use \`resourcePath\` parameter to specify root content directory.' );

			}
		);

		return texture;

	}
```
</details>

##### `getWrappingType(num: any): any`

<details><summary>Code</summary>

```ts
getWrappingType( num ) {

		switch ( num ) {

			case 0:
				console.warn( 'LWOLoader: "Reset" texture wrapping type is not supported in three.js' );
				return ClampToEdgeWrapping;
			case 1: return RepeatWrapping;
			case 2: return MirroredRepeatWrapping;
			case 3: return ClampToEdgeWrapping;

		}

	}
```
</details>

##### `getMaterialType(nodeData: any): any`

<details><summary>Code</summary>

```ts
getMaterialType( nodeData ) {

		if ( nodeData.Clearcoat && nodeData.Clearcoat.value > 0 ) return MeshPhysicalMaterial;
		if ( nodeData.Roughness ) return MeshStandardMaterial;
		return MeshPhongMaterial;

	}
```
</details>

### `GeometryParser`

<details><summary>Class Code</summary>

```ts
class GeometryParser {

	parse( geoData, layer ) {

		const geometry = new BufferGeometry();

		geometry.setAttribute( 'position', new Float32BufferAttribute( geoData.points, 3 ) );

		const indices = this.splitIndices( geoData.vertexIndices, geoData.polygonDimensions );
		geometry.setIndex( indices );

		this.parseGroups( geometry, geoData );

		geometry.computeVertexNormals();

		this.parseUVs( geometry, layer );
		this.parseMorphTargets( geometry, layer );

		// TODO: z may need to be reversed to account for coordinate system change
		geometry.translate( - layer.pivot[ 0 ], - layer.pivot[ 1 ], - layer.pivot[ 2 ] );

		// let userData = geometry.userData;
		// geometry = geometry.toNonIndexed()
		// geometry.userData = userData;

		return geometry;

	}

	// split quads into tris
	splitIndices( indices, polygonDimensions ) {

		const remappedIndices = [];

		let i = 0;
		polygonDimensions.forEach( function ( dim ) {

			if ( dim < 4 ) {

				for ( let k = 0; k < dim; k ++ ) remappedIndices.push( indices[ i + k ] );

			} else if ( dim === 4 ) {

				remappedIndices.push(
					indices[ i ],
					indices[ i + 1 ],
					indices[ i + 2 ],

					indices[ i ],
					indices[ i + 2 ],
					indices[ i + 3 ]

				);

			} else if ( dim > 4 ) {

				for ( let k = 1; k < dim - 1; k ++ ) {

					remappedIndices.push( indices[ i ], indices[ i + k ], indices[ i + k + 1 ] );

				}

				console.warn( 'LWOLoader: polygons with greater than 4 sides are not supported' );

			}

			i += dim;

		} );

		return remappedIndices;

	}

	// NOTE: currently ignoring poly indices and assuming that they are intelligently ordered
	parseGroups( geometry, geoData ) {

		const tags = _lwoTree.tags;
		const matNames = [];

		let elemSize = 3;
		if ( geoData.type === 'lines' ) elemSize = 2;
		if ( geoData.type === 'points' ) elemSize = 1;

		const remappedIndices = this.splitMaterialIndices( geoData.polygonDimensions, geoData.materialIndices );

		let indexNum = 0; // create new indices in numerical order
		const indexPairs = {}; // original indices mapped to numerical indices

		let prevMaterialIndex;
		let materialIndex;

		let prevStart = 0;
		let currentCount = 0;

		for ( let i = 0; i < remappedIndices.length; i += 2 ) {

			materialIndex = remappedIndices[ i + 1 ];

			if ( i === 0 ) matNames[ indexNum ] = tags[ materialIndex ];

			if ( prevMaterialIndex === undefined ) prevMaterialIndex = materialIndex;

			if ( materialIndex !== prevMaterialIndex ) {

				let currentIndex;
				if ( indexPairs[ tags[ prevMaterialIndex ] ] ) {

					currentIndex = indexPairs[ tags[ prevMaterialIndex ] ];

				} else {

					currentIndex = indexNum;
					indexPairs[ tags[ prevMaterialIndex ] ] = indexNum;
					matNames[ indexNum ] = tags[ prevMaterialIndex ];
					indexNum ++;

				}

				geometry.addGroup( prevStart, currentCount, currentIndex );

				prevStart += currentCount;

				prevMaterialIndex = materialIndex;
				currentCount = 0;

			}

			currentCount += elemSize;

		}

		// the loop above doesn't add the last group, do that here.
		if ( geometry.groups.length > 0 ) {

			let currentIndex;
			if ( indexPairs[ tags[ materialIndex ] ] ) {

				currentIndex = indexPairs[ tags[ materialIndex ] ];

			} else {

				currentIndex = indexNum;
				indexPairs[ tags[ materialIndex ] ] = indexNum;
				matNames[ indexNum ] = tags[ materialIndex ];

			}

			geometry.addGroup( prevStart, currentCount, currentIndex );

		}

		// Mat names from TAGS chunk, used to build up an array of materials for this geometry
		geometry.userData.matNames = matNames;

	}

	splitMaterialIndices( polygonDimensions, indices ) {

		const remappedIndices = [];

		polygonDimensions.forEach( function ( dim, i ) {

			if ( dim <= 3 ) {

				remappedIndices.push( indices[ i * 2 ], indices[ i * 2 + 1 ] );

			} else if ( dim === 4 ) {

				remappedIndices.push( indices[ i * 2 ], indices[ i * 2 + 1 ], indices[ i * 2 ], indices[ i * 2 + 1 ] );

			} else {

				 // ignore > 4 for now
				for ( let k = 0; k < dim - 2; k ++ ) {

					remappedIndices.push( indices[ i * 2 ], indices[ i * 2 + 1 ] );

				}

			}

		} );

		return remappedIndices;

	}

	// UV maps:
	// 1: are defined via index into an array of points, not into a geometry
	// - the geometry is also defined by an index into this array, but the indexes may not match
	// 2: there can be any number of UV maps for a single geometry. Here these are combined,
	// 	with preference given to the first map encountered
	// 3: UV maps can be partial - that is, defined for only a part of the geometry
	// 4: UV maps can be VMAP or VMAD (discontinuous, to allow for seams). In practice, most
	// UV maps are defined as partially VMAP and partially VMAD
	// VMADs are currently not supported
	parseUVs( geometry, layer ) {

		// start by creating a UV map set to zero for the whole geometry
		const remappedUVs = Array.from( Array( geometry.attributes.position.count * 2 ), function () {

			return 0;

		} );

		for ( const name in layer.uvs ) {

			const uvs = layer.uvs[ name ].uvs;
			const uvIndices = layer.uvs[ name ].uvIndices;

			uvIndices.forEach( function ( i, j ) {

				remappedUVs[ i * 2 ] = uvs[ j * 2 ];
				remappedUVs[ i * 2 + 1 ] = uvs[ j * 2 + 1 ];

			} );

		}

		geometry.setAttribute( 'uv', new Float32BufferAttribute( remappedUVs, 2 ) );

	}

	parseMorphTargets( geometry, layer ) {

		let num = 0;
		for ( const name in layer.morphTargets ) {

			const remappedPoints = geometry.attributes.position.array.slice();

			if ( ! geometry.morphAttributes.position ) geometry.morphAttributes.position = [];

			const morphPoints = layer.morphTargets[ name ].points;
			const morphIndices = layer.morphTargets[ name ].indices;
			const type = layer.morphTargets[ name ].type;

			morphIndices.forEach( function ( i, j ) {

				if ( type === 'relative' ) {

					remappedPoints[ i * 3 ] += morphPoints[ j * 3 ];
					remappedPoints[ i * 3 + 1 ] += morphPoints[ j * 3 + 1 ];
					remappedPoints[ i * 3 + 2 ] += morphPoints[ j * 3 + 2 ];

				} else {

					remappedPoints[ i * 3 ] = morphPoints[ j * 3 ];
					remappedPoints[ i * 3 + 1 ] = morphPoints[ j * 3 + 1 ];
					remappedPoints[ i * 3 + 2 ] = morphPoints[ j * 3 + 2 ];

				}

			} );

			geometry.morphAttributes.position[ num ] = new Float32BufferAttribute( remappedPoints, 3 );
			geometry.morphAttributes.position[ num ].name = name;

			num ++;

		}

		geometry.morphTargetsRelative = false;

	}

}
```
</details>

#### Methods

##### `parse(geoData: any, layer: any): any`

<details><summary>Code</summary>

```ts
parse( geoData, layer ) {

		const geometry = new BufferGeometry();

		geometry.setAttribute( 'position', new Float32BufferAttribute( geoData.points, 3 ) );

		const indices = this.splitIndices( geoData.vertexIndices, geoData.polygonDimensions );
		geometry.setIndex( indices );

		this.parseGroups( geometry, geoData );

		geometry.computeVertexNormals();

		this.parseUVs( geometry, layer );
		this.parseMorphTargets( geometry, layer );

		// TODO: z may need to be reversed to account for coordinate system change
		geometry.translate( - layer.pivot[ 0 ], - layer.pivot[ 1 ], - layer.pivot[ 2 ] );

		// let userData = geometry.userData;
		// geometry = geometry.toNonIndexed()
		// geometry.userData = userData;

		return geometry;

	}
```
</details>

##### `splitIndices(indices: any, polygonDimensions: any): any[]`

<details><summary>Code</summary>

```ts
splitIndices( indices, polygonDimensions ) {

		const remappedIndices = [];

		let i = 0;
		polygonDimensions.forEach( function ( dim ) {

			if ( dim < 4 ) {

				for ( let k = 0; k < dim; k ++ ) remappedIndices.push( indices[ i + k ] );

			} else if ( dim === 4 ) {

				remappedIndices.push(
					indices[ i ],
					indices[ i + 1 ],
					indices[ i + 2 ],

					indices[ i ],
					indices[ i + 2 ],
					indices[ i + 3 ]

				);

			} else if ( dim > 4 ) {

				for ( let k = 1; k < dim - 1; k ++ ) {

					remappedIndices.push( indices[ i ], indices[ i + k ], indices[ i + k + 1 ] );

				}

				console.warn( 'LWOLoader: polygons with greater than 4 sides are not supported' );

			}

			i += dim;

		} );

		return remappedIndices;

	}
```
</details>

##### `parseGroups(geometry: any, geoData: any): void`

<details><summary>Code</summary>

```ts
parseGroups( geometry, geoData ) {

		const tags = _lwoTree.tags;
		const matNames = [];

		let elemSize = 3;
		if ( geoData.type === 'lines' ) elemSize = 2;
		if ( geoData.type === 'points' ) elemSize = 1;

		const remappedIndices = this.splitMaterialIndices( geoData.polygonDimensions, geoData.materialIndices );

		let indexNum = 0; // create new indices in numerical order
		const indexPairs = {}; // original indices mapped to numerical indices

		let prevMaterialIndex;
		let materialIndex;

		let prevStart = 0;
		let currentCount = 0;

		for ( let i = 0; i < remappedIndices.length; i += 2 ) {

			materialIndex = remappedIndices[ i + 1 ];

			if ( i === 0 ) matNames[ indexNum ] = tags[ materialIndex ];

			if ( prevMaterialIndex === undefined ) prevMaterialIndex = materialIndex;

			if ( materialIndex !== prevMaterialIndex ) {

				let currentIndex;
				if ( indexPairs[ tags[ prevMaterialIndex ] ] ) {

					currentIndex = indexPairs[ tags[ prevMaterialIndex ] ];

				} else {

					currentIndex = indexNum;
					indexPairs[ tags[ prevMaterialIndex ] ] = indexNum;
					matNames[ indexNum ] = tags[ prevMaterialIndex ];
					indexNum ++;

				}

				geometry.addGroup( prevStart, currentCount, currentIndex );

				prevStart += currentCount;

				prevMaterialIndex = materialIndex;
				currentCount = 0;

			}

			currentCount += elemSize;

		}

		// the loop above doesn't add the last group, do that here.
		if ( geometry.groups.length > 0 ) {

			let currentIndex;
			if ( indexPairs[ tags[ materialIndex ] ] ) {

				currentIndex = indexPairs[ tags[ materialIndex ] ];

			} else {

				currentIndex = indexNum;
				indexPairs[ tags[ materialIndex ] ] = indexNum;
				matNames[ indexNum ] = tags[ materialIndex ];

			}

			geometry.addGroup( prevStart, currentCount, currentIndex );

		}

		// Mat names from TAGS chunk, used to build up an array of materials for this geometry
		geometry.userData.matNames = matNames;

	}
```
</details>

##### `splitMaterialIndices(polygonDimensions: any, indices: any): any[]`

<details><summary>Code</summary>

```ts
splitMaterialIndices( polygonDimensions, indices ) {

		const remappedIndices = [];

		polygonDimensions.forEach( function ( dim, i ) {

			if ( dim <= 3 ) {

				remappedIndices.push( indices[ i * 2 ], indices[ i * 2 + 1 ] );

			} else if ( dim === 4 ) {

				remappedIndices.push( indices[ i * 2 ], indices[ i * 2 + 1 ], indices[ i * 2 ], indices[ i * 2 + 1 ] );

			} else {

				 // ignore > 4 for now
				for ( let k = 0; k < dim - 2; k ++ ) {

					remappedIndices.push( indices[ i * 2 ], indices[ i * 2 + 1 ] );

				}

			}

		} );

		return remappedIndices;

	}
```
</details>

##### `parseUVs(geometry: any, layer: any): void`

<details><summary>Code</summary>

```ts
parseUVs( geometry, layer ) {

		// start by creating a UV map set to zero for the whole geometry
		const remappedUVs = Array.from( Array( geometry.attributes.position.count * 2 ), function () {

			return 0;

		} );

		for ( const name in layer.uvs ) {

			const uvs = layer.uvs[ name ].uvs;
			const uvIndices = layer.uvs[ name ].uvIndices;

			uvIndices.forEach( function ( i, j ) {

				remappedUVs[ i * 2 ] = uvs[ j * 2 ];
				remappedUVs[ i * 2 + 1 ] = uvs[ j * 2 + 1 ];

			} );

		}

		geometry.setAttribute( 'uv', new Float32BufferAttribute( remappedUVs, 2 ) );

	}
```
</details>

##### `parseMorphTargets(geometry: any, layer: any): void`

<details><summary>Code</summary>

```ts
parseMorphTargets( geometry, layer ) {

		let num = 0;
		for ( const name in layer.morphTargets ) {

			const remappedPoints = geometry.attributes.position.array.slice();

			if ( ! geometry.morphAttributes.position ) geometry.morphAttributes.position = [];

			const morphPoints = layer.morphTargets[ name ].points;
			const morphIndices = layer.morphTargets[ name ].indices;
			const type = layer.morphTargets[ name ].type;

			morphIndices.forEach( function ( i, j ) {

				if ( type === 'relative' ) {

					remappedPoints[ i * 3 ] += morphPoints[ j * 3 ];
					remappedPoints[ i * 3 + 1 ] += morphPoints[ j * 3 + 1 ];
					remappedPoints[ i * 3 + 2 ] += morphPoints[ j * 3 + 2 ];

				} else {

					remappedPoints[ i * 3 ] = morphPoints[ j * 3 ];
					remappedPoints[ i * 3 + 1 ] = morphPoints[ j * 3 + 1 ];
					remappedPoints[ i * 3 + 2 ] = morphPoints[ j * 3 + 2 ];

				}

			} );

			geometry.morphAttributes.position[ num ] = new Float32BufferAttribute( remappedPoints, 3 );
			geometry.morphAttributes.position[ num ].name = name;

			num ++;

		}

		geometry.morphTargetsRelative = false;

	}
```
</details>


---