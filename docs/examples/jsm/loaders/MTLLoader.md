[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MTLLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 16 |
| 🧱 Classes | 2 |
| 📦 Imports | 12 |
| 📊 Variables & Constants | 24 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/MTLLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `three` |
| `ColorManagement` | `three` |
| `DefaultLoadingManager` | `three` |
| `FileLoader` | `three` |
| `FrontSide` | `three` |
| `Loader` | `three` |
| `LoaderUtils` | `three` |
| `MeshPhongMaterial` | `three` |
| `RepeatWrapping` | `three` |
| `TextureLoader` | `three` |
| `Vector2` | `three` |
| `SRGBColorSpace` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `path` | `any` | let/var | `( this.path === '' ) ? LoaderUtils.extractUrlBase( url ) : this.path` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `info` | `{}` | let/var | `{}` | ✗ |
| `delimiter_pattern` | `RegExp` | let/var | `/\s+/` | ✗ |
| `materialsInfo` | `{}` | let/var | `{}` | ✗ |
| `line` | `string` | let/var | `lines[ i ]` | ✗ |
| `key` | `string` | let/var | `( pos >= 0 ) ? line.substring( 0, pos ) : line` | ✗ |
| `value` | `string` | let/var | `( pos >= 0 ) ? line.substring( pos + 1 ) : ''` | ✗ |
| `materialCreator` | `MaterialCreator` | let/var | `new MaterialCreator( this.resourcePath \|\| path, this.materialOptions )` | ✗ |
| `converted` | `{}` | let/var | `{}` | ✗ |
| `mat` | `any` | let/var | `materialsInfo[ mn ]` | ✗ |
| `covmat` | `{}` | let/var | `{}` | ✗ |
| `save` | `boolean` | let/var | `true` | ✗ |
| `value` | `any` | let/var | `mat[ prop ]` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `mat` | `any` | let/var | `this.materialsInfo[ materialName ]` | ✗ |
| `params` | `{ name: any; side: any; }` | let/var | `{ name: materialName, side: this.side }` | ✗ |
| `value` | `any` | let/var | `mat[ prop ]` | ✗ |
| `n` | `any` | let/var | `*not shown*` | ✗ |
| `texParams` | `{ scale: any; offset: any; }` | let/var | `{ scale: new Vector2( 1, 1 ), offset: new Vector2( 0, 0 ) }` | ✗ |
| `pos` | `any` | let/var | `*not shown*` | ✗ |
| `manager` | `any` | let/var | `( this.manager !== undefined ) ? this.manager : DefaultLoadingManager` | ✗ |


---

## Functions

### `MTLLoader.load(url: string, onLoad: (arg0: MaterialCreator) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded MTL asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(MaterialCreator)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: MaterialCreator) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `LoaderUtils.extractUrlBase`
- `loader.setPath`
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
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text, path ) );

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

### `MTLLoader.setMaterialOptions(value: any): MTLLoader`

**JSDoc:**
```typescript
/**
	 * Sets the material options.
	 *
	 * @param {MTLLoader~MaterialOptions} value - The material options.
	 * @return {MTLLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`value`** `any`

**Returns:** `MTLLoader`

<details><summary>Code</summary>

```typescript
setMaterialOptions( value ) {

		this.materialOptions = value;
		return this;

	}
```
</details>

### `MTLLoader.parse(text: string, path: string): MaterialCreator`

**JSDoc:**
```typescript
/**
	 * Parses the given MTL data and returns the resulting material creator.
	 *
	 * @param {string} text - The raw MTL data as a string.
	 * @param {string} path - The URL base path.
	 * @return {MaterialCreator} The material creator.
	 */
```

**Parameters:**

- **`text`** `string`
- **`path`** `string`

**Returns:** `MaterialCreator`

**Calls:**

- `text.split`
- `line.trim`
- `line.charAt`
- `line.indexOf`
- `line.substring`
- `key.toLowerCase`
- `value.trim`
- `value.split`
- `parseFloat`
- `materialCreator.setCrossOrigin`
- `materialCreator.setManager`
- `materialCreator.setMaterials`

**Internal Comments:**
```
// Blank line or comment ignore
// New material (x3)
```

<details><summary>Code</summary>

```typescript
parse( text, path ) {

		const lines = text.split( '\n' );
		let info = {};
		const delimiter_pattern = /\s+/;
		const materialsInfo = {};

		for ( let i = 0; i < lines.length; i ++ ) {

			let line = lines[ i ];
			line = line.trim();

			if ( line.length === 0 || line.charAt( 0 ) === '#' ) {

				// Blank line or comment ignore
				continue;

			}

			const pos = line.indexOf( ' ' );

			let key = ( pos >= 0 ) ? line.substring( 0, pos ) : line;
			key = key.toLowerCase();

			let value = ( pos >= 0 ) ? line.substring( pos + 1 ) : '';
			value = value.trim();

			if ( key === 'newmtl' ) {

				// New material

				info = { name: value };
				materialsInfo[ value ] = info;

			} else {

				if ( key === 'ka' || key === 'kd' || key === 'ks' || key === 'ke' ) {

					const ss = value.split( delimiter_pattern, 3 );
					info[ key ] = [ parseFloat( ss[ 0 ] ), parseFloat( ss[ 1 ] ), parseFloat( ss[ 2 ] ) ];

				} else {

					info[ key ] = value;

				}

			}

		}

		const materialCreator = new MaterialCreator( this.resourcePath || path, this.materialOptions );
		materialCreator.setCrossOrigin( this.crossOrigin );
		materialCreator.setManager( this.manager );
		materialCreator.setMaterials( materialsInfo );
		return materialCreator;

	}
```
</details>

### `MaterialCreator.setCrossOrigin(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setCrossOrigin( value ) {

		this.crossOrigin = value;
		return this;

	}
```
</details>

### `MaterialCreator.setManager(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setManager( value ) {

		this.manager = value;

	}
```
</details>

### `MaterialCreator.setMaterials(materialsInfo: any): void`

**Parameters:**

- **`materialsInfo`** `any`

**Returns:** `void`

**Calls:**

- `this.convert`

<details><summary>Code</summary>

```typescript
setMaterials( materialsInfo ) {

		this.materialsInfo = this.convert( materialsInfo );
		this.materials = {};
		this.materialsArray = [];
		this.nameLookup = {};

	}
```
</details>

### `MaterialCreator.convert(materialsInfo: any): any`

**Parameters:**

- **`materialsInfo`** `any`

**Returns:** `any`

**Calls:**

- `prop.toLowerCase`

**Internal Comments:**
```
// Convert materials info into normalized form based on options (x2)
// Diffuse color (color under white light) using RGB values
// ignore (x3)
```

<details><summary>Code</summary>

```typescript
convert( materialsInfo ) {

		if ( ! this.options ) return materialsInfo;

		const converted = {};

		for ( const mn in materialsInfo ) {

			// Convert materials info into normalized form based on options

			const mat = materialsInfo[ mn ];

			const covmat = {};

			converted[ mn ] = covmat;

			for ( const prop in mat ) {

				let save = true;
				let value = mat[ prop ];
				const lprop = prop.toLowerCase();

				switch ( lprop ) {

					case 'kd':
					case 'ka':
					case 'ks':

						// Diffuse color (color under white light) using RGB values

						if ( this.options && this.options.normalizeRGB ) {

							value = [ value[ 0 ] / 255, value[ 1 ] / 255, value[ 2 ] / 255 ];

						}

						if ( this.options && this.options.ignoreZeroRGBs ) {

							if ( value[ 0 ] === 0 && value[ 1 ] === 0 && value[ 2 ] === 0 ) {

								// ignore

								save = false;

							}

						}

						break;

					default:

						break;

				}

				if ( save ) {

					covmat[ lprop ] = value;

				}

			}

		}

		return converted;

	}
```
</details>

### `MaterialCreator.preload(): void`

**Returns:** `void`

**Calls:**

- `this.create`

<details><summary>Code</summary>

```typescript
preload() {

		for ( const mn in this.materialsInfo ) {

			this.create( mn );

		}

	}
```
</details>

### `MaterialCreator.getIndex(materialName: any): any`

**Parameters:**

- **`materialName`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getIndex( materialName ) {

		return this.nameLookup[ materialName ];

	}
```
</details>

### `MaterialCreator.getAsArray(): any[]`

**Returns:** `any[]`

**Calls:**

- `this.create`

<details><summary>Code</summary>

```typescript
getAsArray() {

		let index = 0;

		for ( const mn in this.materialsInfo ) {

			this.materialsArray[ index ] = this.create( mn );
			this.nameLookup[ mn ] = index;
			index ++;

		}

		return this.materialsArray;

	}
```
</details>

### `MaterialCreator.create(materialName: any): any`

**Parameters:**

- **`materialName`** `any`

**Returns:** `any`

**Calls:**

- `this.createMaterial_`

<details><summary>Code</summary>

```typescript
create( materialName ) {

		if ( this.materials[ materialName ] === undefined ) {

			this.createMaterial_( materialName );

		}

		return this.materials[ materialName ];

	}
```
</details>

### `MaterialCreator.createMaterial_(materialName: any): any`

**Parameters:**

- **`materialName`** `any`

**Returns:** `any`

**Calls:**

- `/^https?:\/\//i.test`
- `scope.getTextureParams`
- `scope.loadTexture`
- `resolveURL`
- `map.repeat.copy`
- `map.offset.copy`
- `prop.toLowerCase`
- `ColorManagement.colorSpaceToWorking`
- `new Color().fromArray`
- `setMapForType`
- `parseFloat`

**Internal Comments:**
```
// Create material (x2)
// Absolute URL
// Ns is material specular exponent
// Diffuse color (color under white light) using RGB values (x4)
// Specular color (color when light is reflected from shiny surface) using RGB values (x4)
// Emissive using RGB values (x4)
// Diffuse texture map (x3)
// Specular map (x3)
// Emissive map (x3)
// Bump texture map (x3)
// Displacement texture map (x3)
// Alpha map (x3)
// The specular exponent (defines the focus of the specular highlight) (x4)
// A high exponent results in a tight, concentrated highlight. Ns values normally range from 0 to 1000. (x4)
```

<details><summary>Code</summary>

```typescript
createMaterial_( materialName ) {

		// Create material

		const scope = this;
		const mat = this.materialsInfo[ materialName ];
		const params = {

			name: materialName,
			side: this.side

		};

		function resolveURL( baseUrl, url ) {

			if ( typeof url !== 'string' || url === '' )
				return '';

			// Absolute URL
			if ( /^https?:\/\//i.test( url ) ) return url;

			return baseUrl + url;

		}

		function setMapForType( mapType, value ) {

			if ( params[ mapType ] ) return; // Keep the first encountered texture

			const texParams = scope.getTextureParams( value, params );
			const map = scope.loadTexture( resolveURL( scope.baseUrl, texParams.url ) );

			map.repeat.copy( texParams.scale );
			map.offset.copy( texParams.offset );

			map.wrapS = scope.wrap;
			map.wrapT = scope.wrap;

			if ( mapType === 'map' || mapType === 'emissiveMap' ) {

				map.colorSpace = SRGBColorSpace;

			}

			params[ mapType ] = map;

		}

		for ( const prop in mat ) {

			const value = mat[ prop ];
			let n;

			if ( value === '' ) continue;

			switch ( prop.toLowerCase() ) {

				// Ns is material specular exponent

				case 'kd':

					// Diffuse color (color under white light) using RGB values

					params.color = ColorManagement.colorSpaceToWorking( new Color().fromArray( value ), SRGBColorSpace );

					break;

				case 'ks':

					// Specular color (color when light is reflected from shiny surface) using RGB values
					params.specular = ColorManagement.colorSpaceToWorking( new Color().fromArray( value ), SRGBColorSpace );

					break;

				case 'ke':

					// Emissive using RGB values
					params.emissive = ColorManagement.colorSpaceToWorking( new Color().fromArray( value ), SRGBColorSpace );

					break;

				case 'map_kd':

					// Diffuse texture map

					setMapForType( 'map', value );

					break;

				case 'map_ks':

					// Specular map

					setMapForType( 'specularMap', value );

					break;

				case 'map_ke':

					// Emissive map

					setMapForType( 'emissiveMap', value );

					break;

				case 'norm':

					setMapForType( 'normalMap', value );

					break;

				case 'map_bump':
				case 'bump':

					// Bump texture map

					setMapForType( 'bumpMap', value );

					break;

				case 'disp':

					// Displacement texture map

					setMapForType( 'displacementMap', value );

					break;

				case 'map_d':

					// Alpha map

					setMapForType( 'alphaMap', value );
					params.transparent = true;

					break;

				case 'ns':

					// The specular exponent (defines the focus of the specular highlight)
					// A high exponent results in a tight, concentrated highlight. Ns values normally range from 0 to 1000.

					params.shininess = parseFloat( value );

					break;

				case 'd':
					n = parseFloat( value );

					if ( n < 1 ) {

						params.opacity = n;
						params.transparent = true;

					}

					break;

				case 'tr':
					n = parseFloat( value );

					if ( this.options && this.options.invertTrProperty ) n = 1 - n;

					if ( n > 0 ) {

						params.opacity = 1 - n;
						params.transparent = true;

					}

					break;

				default:
					break;

			}

		}

		this.materials[ materialName ] = new MeshPhongMaterial( params );
		return this.materials[ materialName ];

	}
```
</details>

### `MaterialCreator.getTextureParams(value: any, matParams: any): { scale: any; offset: any; }`

**Parameters:**

- **`value`** `any`
- **`matParams`** `any`

**Returns:** `{ scale: any; offset: any; }`

**Calls:**

- `value.split`
- `items.indexOf`
- `parseFloat`
- `items.splice`
- `texParams.scale.set`
- `texParams.offset.set`
- `items.join( ' ' ).trim`

<details><summary>Code</summary>

```typescript
getTextureParams( value, matParams ) {

		const texParams = {

			scale: new Vector2( 1, 1 ),
			offset: new Vector2( 0, 0 )

		 };

		const items = value.split( /\s+/ );
		let pos;

		pos = items.indexOf( '-bm' );

		if ( pos >= 0 ) {

			matParams.bumpScale = parseFloat( items[ pos + 1 ] );
			items.splice( pos, 2 );

		}

		pos = items.indexOf( '-mm' );

		if ( pos >= 0 ) {

			matParams.displacementBias = parseFloat( items[ pos + 1 ] );
			matParams.displacementScale = parseFloat( items[ pos + 2 ] );
			items.splice( pos, 3 );

		}

		pos = items.indexOf( '-s' );

		if ( pos >= 0 ) {

			texParams.scale.set( parseFloat( items[ pos + 1 ] ), parseFloat( items[ pos + 2 ] ) );
			items.splice( pos, 4 ); // we expect 3 parameters here!

		}

		pos = items.indexOf( '-o' );

		if ( pos >= 0 ) {

			texParams.offset.set( parseFloat( items[ pos + 1 ] ), parseFloat( items[ pos + 2 ] ) );
			items.splice( pos, 4 ); // we expect 3 parameters here!

		}

		texParams.url = items.join( ' ' ).trim();
		return texParams;

	}
```
</details>

### `MaterialCreator.loadTexture(url: any, mapping: any, onLoad: any, onProgress: any, onError: any): any`

**Parameters:**

- **`url`** `any`
- **`mapping`** `any`
- **`onLoad`** `any`
- **`onProgress`** `any`
- **`onError`** `any`

**Returns:** `any`

**Calls:**

- `manager.getHandler`
- `loader.setCrossOrigin`
- `loader.load`

<details><summary>Code</summary>

```typescript
loadTexture( url, mapping, onLoad, onProgress, onError ) {

		const manager = ( this.manager !== undefined ) ? this.manager : DefaultLoadingManager;
		let loader = manager.getHandler( url );

		if ( loader === null ) {

			loader = new TextureLoader( manager );

		}

		if ( loader.setCrossOrigin ) loader.setCrossOrigin( this.crossOrigin );

		const texture = loader.load( url, onLoad, onProgress, onError );

		if ( mapping !== undefined ) texture.mapping = mapping;

		return texture;

	}
```
</details>

### `resolveURL(baseUrl: any, url: any): string`

**Parameters:**

- **`baseUrl`** `any`
- **`url`** `any`

**Returns:** `string`

**Calls:**

- `/^https?:\/\//i.test`

**Internal Comments:**
```
// Absolute URL
```

<details><summary>Code</summary>

```typescript
function resolveURL( baseUrl, url ) {

			if ( typeof url !== 'string' || url === '' )
				return '';

			// Absolute URL
			if ( /^https?:\/\//i.test( url ) ) return url;

			return baseUrl + url;

		}
```
</details>

### `setMapForType(mapType: any, value: any): void`

**Parameters:**

- **`mapType`** `any`
- **`value`** `any`

**Returns:** `void`

**Calls:**

- `scope.getTextureParams`
- `scope.loadTexture`
- `resolveURL`
- `map.repeat.copy`
- `map.offset.copy`

<details><summary>Code</summary>

```typescript
function setMapForType( mapType, value ) {

			if ( params[ mapType ] ) return; // Keep the first encountered texture

			const texParams = scope.getTextureParams( value, params );
			const map = scope.loadTexture( resolveURL( scope.baseUrl, texParams.url ) );

			map.repeat.copy( texParams.scale );
			map.offset.copy( texParams.offset );

			map.wrapS = scope.wrap;
			map.wrapT = scope.wrap;

			if ( mapType === 'map' || mapType === 'emissiveMap' ) {

				map.colorSpace = SRGBColorSpace;

			}

			params[ mapType ] = map;

		}
```
</details>


---

## Classes

### `MTLLoader`

<details><summary>Class Code</summary>

```ts
class MTLLoader extends Loader {

	constructor( manager ) {

		super( manager );

	}

	/**
	 * Starts loading from the given URL and passes the loaded MTL asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(MaterialCreator)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const path = ( this.path === '' ) ? LoaderUtils.extractUrlBase( url ) : this.path;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text, path ) );

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
	 * Sets the material options.
	 *
	 * @param {MTLLoader~MaterialOptions} value - The material options.
	 * @return {MTLLoader} A reference to this loader.
	 */
	setMaterialOptions( value ) {

		this.materialOptions = value;
		return this;

	}

	/**
	 * Parses the given MTL data and returns the resulting material creator.
	 *
	 * @param {string} text - The raw MTL data as a string.
	 * @param {string} path - The URL base path.
	 * @return {MaterialCreator} The material creator.
	 */
	parse( text, path ) {

		const lines = text.split( '\n' );
		let info = {};
		const delimiter_pattern = /\s+/;
		const materialsInfo = {};

		for ( let i = 0; i < lines.length; i ++ ) {

			let line = lines[ i ];
			line = line.trim();

			if ( line.length === 0 || line.charAt( 0 ) === '#' ) {

				// Blank line or comment ignore
				continue;

			}

			const pos = line.indexOf( ' ' );

			let key = ( pos >= 0 ) ? line.substring( 0, pos ) : line;
			key = key.toLowerCase();

			let value = ( pos >= 0 ) ? line.substring( pos + 1 ) : '';
			value = value.trim();

			if ( key === 'newmtl' ) {

				// New material

				info = { name: value };
				materialsInfo[ value ] = info;

			} else {

				if ( key === 'ka' || key === 'kd' || key === 'ks' || key === 'ke' ) {

					const ss = value.split( delimiter_pattern, 3 );
					info[ key ] = [ parseFloat( ss[ 0 ] ), parseFloat( ss[ 1 ] ), parseFloat( ss[ 2 ] ) ];

				} else {

					info[ key ] = value;

				}

			}

		}

		const materialCreator = new MaterialCreator( this.resourcePath || path, this.materialOptions );
		materialCreator.setCrossOrigin( this.crossOrigin );
		materialCreator.setManager( this.manager );
		materialCreator.setMaterials( materialsInfo );
		return materialCreator;

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: MaterialCreator) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const path = ( this.path === '' ) ? LoaderUtils.extractUrlBase( url ) : this.path;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text, path ) );

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

##### `setMaterialOptions(value: any): MTLLoader`

<details><summary>Code</summary>

```ts
setMaterialOptions( value ) {

		this.materialOptions = value;
		return this;

	}
```
</details>

##### `parse(text: string, path: string): MaterialCreator`

<details><summary>Code</summary>

```ts
parse( text, path ) {

		const lines = text.split( '\n' );
		let info = {};
		const delimiter_pattern = /\s+/;
		const materialsInfo = {};

		for ( let i = 0; i < lines.length; i ++ ) {

			let line = lines[ i ];
			line = line.trim();

			if ( line.length === 0 || line.charAt( 0 ) === '#' ) {

				// Blank line or comment ignore
				continue;

			}

			const pos = line.indexOf( ' ' );

			let key = ( pos >= 0 ) ? line.substring( 0, pos ) : line;
			key = key.toLowerCase();

			let value = ( pos >= 0 ) ? line.substring( pos + 1 ) : '';
			value = value.trim();

			if ( key === 'newmtl' ) {

				// New material

				info = { name: value };
				materialsInfo[ value ] = info;

			} else {

				if ( key === 'ka' || key === 'kd' || key === 'ks' || key === 'ke' ) {

					const ss = value.split( delimiter_pattern, 3 );
					info[ key ] = [ parseFloat( ss[ 0 ] ), parseFloat( ss[ 1 ] ), parseFloat( ss[ 2 ] ) ];

				} else {

					info[ key ] = value;

				}

			}

		}

		const materialCreator = new MaterialCreator( this.resourcePath || path, this.materialOptions );
		materialCreator.setCrossOrigin( this.crossOrigin );
		materialCreator.setManager( this.manager );
		materialCreator.setMaterials( materialsInfo );
		return materialCreator;

	}
```
</details>

### `MaterialCreator`

<details><summary>Class Code</summary>

```ts
class MaterialCreator {

	constructor( baseUrl = '', options = {} ) {

		this.baseUrl = baseUrl;
		this.options = options;
		this.materialsInfo = {};
		this.materials = {};
		this.materialsArray = [];
		this.nameLookup = {};

		this.crossOrigin = 'anonymous';

		this.side = ( this.options.side !== undefined ) ? this.options.side : FrontSide;
		this.wrap = ( this.options.wrap !== undefined ) ? this.options.wrap : RepeatWrapping;

	}

	setCrossOrigin( value ) {

		this.crossOrigin = value;
		return this;

	}

	setManager( value ) {

		this.manager = value;

	}

	setMaterials( materialsInfo ) {

		this.materialsInfo = this.convert( materialsInfo );
		this.materials = {};
		this.materialsArray = [];
		this.nameLookup = {};

	}

	convert( materialsInfo ) {

		if ( ! this.options ) return materialsInfo;

		const converted = {};

		for ( const mn in materialsInfo ) {

			// Convert materials info into normalized form based on options

			const mat = materialsInfo[ mn ];

			const covmat = {};

			converted[ mn ] = covmat;

			for ( const prop in mat ) {

				let save = true;
				let value = mat[ prop ];
				const lprop = prop.toLowerCase();

				switch ( lprop ) {

					case 'kd':
					case 'ka':
					case 'ks':

						// Diffuse color (color under white light) using RGB values

						if ( this.options && this.options.normalizeRGB ) {

							value = [ value[ 0 ] / 255, value[ 1 ] / 255, value[ 2 ] / 255 ];

						}

						if ( this.options && this.options.ignoreZeroRGBs ) {

							if ( value[ 0 ] === 0 && value[ 1 ] === 0 && value[ 2 ] === 0 ) {

								// ignore

								save = false;

							}

						}

						break;

					default:

						break;

				}

				if ( save ) {

					covmat[ lprop ] = value;

				}

			}

		}

		return converted;

	}

	preload() {

		for ( const mn in this.materialsInfo ) {

			this.create( mn );

		}

	}

	getIndex( materialName ) {

		return this.nameLookup[ materialName ];

	}

	getAsArray() {

		let index = 0;

		for ( const mn in this.materialsInfo ) {

			this.materialsArray[ index ] = this.create( mn );
			this.nameLookup[ mn ] = index;
			index ++;

		}

		return this.materialsArray;

	}

	create( materialName ) {

		if ( this.materials[ materialName ] === undefined ) {

			this.createMaterial_( materialName );

		}

		return this.materials[ materialName ];

	}

	createMaterial_( materialName ) {

		// Create material

		const scope = this;
		const mat = this.materialsInfo[ materialName ];
		const params = {

			name: materialName,
			side: this.side

		};

		function resolveURL( baseUrl, url ) {

			if ( typeof url !== 'string' || url === '' )
				return '';

			// Absolute URL
			if ( /^https?:\/\//i.test( url ) ) return url;

			return baseUrl + url;

		}

		function setMapForType( mapType, value ) {

			if ( params[ mapType ] ) return; // Keep the first encountered texture

			const texParams = scope.getTextureParams( value, params );
			const map = scope.loadTexture( resolveURL( scope.baseUrl, texParams.url ) );

			map.repeat.copy( texParams.scale );
			map.offset.copy( texParams.offset );

			map.wrapS = scope.wrap;
			map.wrapT = scope.wrap;

			if ( mapType === 'map' || mapType === 'emissiveMap' ) {

				map.colorSpace = SRGBColorSpace;

			}

			params[ mapType ] = map;

		}

		for ( const prop in mat ) {

			const value = mat[ prop ];
			let n;

			if ( value === '' ) continue;

			switch ( prop.toLowerCase() ) {

				// Ns is material specular exponent

				case 'kd':

					// Diffuse color (color under white light) using RGB values

					params.color = ColorManagement.colorSpaceToWorking( new Color().fromArray( value ), SRGBColorSpace );

					break;

				case 'ks':

					// Specular color (color when light is reflected from shiny surface) using RGB values
					params.specular = ColorManagement.colorSpaceToWorking( new Color().fromArray( value ), SRGBColorSpace );

					break;

				case 'ke':

					// Emissive using RGB values
					params.emissive = ColorManagement.colorSpaceToWorking( new Color().fromArray( value ), SRGBColorSpace );

					break;

				case 'map_kd':

					// Diffuse texture map

					setMapForType( 'map', value );

					break;

				case 'map_ks':

					// Specular map

					setMapForType( 'specularMap', value );

					break;

				case 'map_ke':

					// Emissive map

					setMapForType( 'emissiveMap', value );

					break;

				case 'norm':

					setMapForType( 'normalMap', value );

					break;

				case 'map_bump':
				case 'bump':

					// Bump texture map

					setMapForType( 'bumpMap', value );

					break;

				case 'disp':

					// Displacement texture map

					setMapForType( 'displacementMap', value );

					break;

				case 'map_d':

					// Alpha map

					setMapForType( 'alphaMap', value );
					params.transparent = true;

					break;

				case 'ns':

					// The specular exponent (defines the focus of the specular highlight)
					// A high exponent results in a tight, concentrated highlight. Ns values normally range from 0 to 1000.

					params.shininess = parseFloat( value );

					break;

				case 'd':
					n = parseFloat( value );

					if ( n < 1 ) {

						params.opacity = n;
						params.transparent = true;

					}

					break;

				case 'tr':
					n = parseFloat( value );

					if ( this.options && this.options.invertTrProperty ) n = 1 - n;

					if ( n > 0 ) {

						params.opacity = 1 - n;
						params.transparent = true;

					}

					break;

				default:
					break;

			}

		}

		this.materials[ materialName ] = new MeshPhongMaterial( params );
		return this.materials[ materialName ];

	}

	getTextureParams( value, matParams ) {

		const texParams = {

			scale: new Vector2( 1, 1 ),
			offset: new Vector2( 0, 0 )

		 };

		const items = value.split( /\s+/ );
		let pos;

		pos = items.indexOf( '-bm' );

		if ( pos >= 0 ) {

			matParams.bumpScale = parseFloat( items[ pos + 1 ] );
			items.splice( pos, 2 );

		}

		pos = items.indexOf( '-mm' );

		if ( pos >= 0 ) {

			matParams.displacementBias = parseFloat( items[ pos + 1 ] );
			matParams.displacementScale = parseFloat( items[ pos + 2 ] );
			items.splice( pos, 3 );

		}

		pos = items.indexOf( '-s' );

		if ( pos >= 0 ) {

			texParams.scale.set( parseFloat( items[ pos + 1 ] ), parseFloat( items[ pos + 2 ] ) );
			items.splice( pos, 4 ); // we expect 3 parameters here!

		}

		pos = items.indexOf( '-o' );

		if ( pos >= 0 ) {

			texParams.offset.set( parseFloat( items[ pos + 1 ] ), parseFloat( items[ pos + 2 ] ) );
			items.splice( pos, 4 ); // we expect 3 parameters here!

		}

		texParams.url = items.join( ' ' ).trim();
		return texParams;

	}

	loadTexture( url, mapping, onLoad, onProgress, onError ) {

		const manager = ( this.manager !== undefined ) ? this.manager : DefaultLoadingManager;
		let loader = manager.getHandler( url );

		if ( loader === null ) {

			loader = new TextureLoader( manager );

		}

		if ( loader.setCrossOrigin ) loader.setCrossOrigin( this.crossOrigin );

		const texture = loader.load( url, onLoad, onProgress, onError );

		if ( mapping !== undefined ) texture.mapping = mapping;

		return texture;

	}

}
```
</details>

#### Methods

##### `setCrossOrigin(value: any): this`

<details><summary>Code</summary>

```ts
setCrossOrigin( value ) {

		this.crossOrigin = value;
		return this;

	}
```
</details>

##### `setManager(value: any): void`

<details><summary>Code</summary>

```ts
setManager( value ) {

		this.manager = value;

	}
```
</details>

##### `setMaterials(materialsInfo: any): void`

<details><summary>Code</summary>

```ts
setMaterials( materialsInfo ) {

		this.materialsInfo = this.convert( materialsInfo );
		this.materials = {};
		this.materialsArray = [];
		this.nameLookup = {};

	}
```
</details>

##### `convert(materialsInfo: any): any`

<details><summary>Code</summary>

```ts
convert( materialsInfo ) {

		if ( ! this.options ) return materialsInfo;

		const converted = {};

		for ( const mn in materialsInfo ) {

			// Convert materials info into normalized form based on options

			const mat = materialsInfo[ mn ];

			const covmat = {};

			converted[ mn ] = covmat;

			for ( const prop in mat ) {

				let save = true;
				let value = mat[ prop ];
				const lprop = prop.toLowerCase();

				switch ( lprop ) {

					case 'kd':
					case 'ka':
					case 'ks':

						// Diffuse color (color under white light) using RGB values

						if ( this.options && this.options.normalizeRGB ) {

							value = [ value[ 0 ] / 255, value[ 1 ] / 255, value[ 2 ] / 255 ];

						}

						if ( this.options && this.options.ignoreZeroRGBs ) {

							if ( value[ 0 ] === 0 && value[ 1 ] === 0 && value[ 2 ] === 0 ) {

								// ignore

								save = false;

							}

						}

						break;

					default:

						break;

				}

				if ( save ) {

					covmat[ lprop ] = value;

				}

			}

		}

		return converted;

	}
```
</details>

##### `preload(): void`

<details><summary>Code</summary>

```ts
preload() {

		for ( const mn in this.materialsInfo ) {

			this.create( mn );

		}

	}
```
</details>

##### `getIndex(materialName: any): any`

<details><summary>Code</summary>

```ts
getIndex( materialName ) {

		return this.nameLookup[ materialName ];

	}
```
</details>

##### `getAsArray(): any[]`

<details><summary>Code</summary>

```ts
getAsArray() {

		let index = 0;

		for ( const mn in this.materialsInfo ) {

			this.materialsArray[ index ] = this.create( mn );
			this.nameLookup[ mn ] = index;
			index ++;

		}

		return this.materialsArray;

	}
```
</details>

##### `create(materialName: any): any`

<details><summary>Code</summary>

```ts
create( materialName ) {

		if ( this.materials[ materialName ] === undefined ) {

			this.createMaterial_( materialName );

		}

		return this.materials[ materialName ];

	}
```
</details>

##### `createMaterial_(materialName: any): any`

<details><summary>Code</summary>

```ts
createMaterial_( materialName ) {

		// Create material

		const scope = this;
		const mat = this.materialsInfo[ materialName ];
		const params = {

			name: materialName,
			side: this.side

		};

		function resolveURL( baseUrl, url ) {

			if ( typeof url !== 'string' || url === '' )
				return '';

			// Absolute URL
			if ( /^https?:\/\//i.test( url ) ) return url;

			return baseUrl + url;

		}

		function setMapForType( mapType, value ) {

			if ( params[ mapType ] ) return; // Keep the first encountered texture

			const texParams = scope.getTextureParams( value, params );
			const map = scope.loadTexture( resolveURL( scope.baseUrl, texParams.url ) );

			map.repeat.copy( texParams.scale );
			map.offset.copy( texParams.offset );

			map.wrapS = scope.wrap;
			map.wrapT = scope.wrap;

			if ( mapType === 'map' || mapType === 'emissiveMap' ) {

				map.colorSpace = SRGBColorSpace;

			}

			params[ mapType ] = map;

		}

		for ( const prop in mat ) {

			const value = mat[ prop ];
			let n;

			if ( value === '' ) continue;

			switch ( prop.toLowerCase() ) {

				// Ns is material specular exponent

				case 'kd':

					// Diffuse color (color under white light) using RGB values

					params.color = ColorManagement.colorSpaceToWorking( new Color().fromArray( value ), SRGBColorSpace );

					break;

				case 'ks':

					// Specular color (color when light is reflected from shiny surface) using RGB values
					params.specular = ColorManagement.colorSpaceToWorking( new Color().fromArray( value ), SRGBColorSpace );

					break;

				case 'ke':

					// Emissive using RGB values
					params.emissive = ColorManagement.colorSpaceToWorking( new Color().fromArray( value ), SRGBColorSpace );

					break;

				case 'map_kd':

					// Diffuse texture map

					setMapForType( 'map', value );

					break;

				case 'map_ks':

					// Specular map

					setMapForType( 'specularMap', value );

					break;

				case 'map_ke':

					// Emissive map

					setMapForType( 'emissiveMap', value );

					break;

				case 'norm':

					setMapForType( 'normalMap', value );

					break;

				case 'map_bump':
				case 'bump':

					// Bump texture map

					setMapForType( 'bumpMap', value );

					break;

				case 'disp':

					// Displacement texture map

					setMapForType( 'displacementMap', value );

					break;

				case 'map_d':

					// Alpha map

					setMapForType( 'alphaMap', value );
					params.transparent = true;

					break;

				case 'ns':

					// The specular exponent (defines the focus of the specular highlight)
					// A high exponent results in a tight, concentrated highlight. Ns values normally range from 0 to 1000.

					params.shininess = parseFloat( value );

					break;

				case 'd':
					n = parseFloat( value );

					if ( n < 1 ) {

						params.opacity = n;
						params.transparent = true;

					}

					break;

				case 'tr':
					n = parseFloat( value );

					if ( this.options && this.options.invertTrProperty ) n = 1 - n;

					if ( n > 0 ) {

						params.opacity = 1 - n;
						params.transparent = true;

					}

					break;

				default:
					break;

			}

		}

		this.materials[ materialName ] = new MeshPhongMaterial( params );
		return this.materials[ materialName ];

	}
```
</details>

##### `getTextureParams(value: any, matParams: any): { scale: any; offset: any; }`

<details><summary>Code</summary>

```ts
getTextureParams( value, matParams ) {

		const texParams = {

			scale: new Vector2( 1, 1 ),
			offset: new Vector2( 0, 0 )

		 };

		const items = value.split( /\s+/ );
		let pos;

		pos = items.indexOf( '-bm' );

		if ( pos >= 0 ) {

			matParams.bumpScale = parseFloat( items[ pos + 1 ] );
			items.splice( pos, 2 );

		}

		pos = items.indexOf( '-mm' );

		if ( pos >= 0 ) {

			matParams.displacementBias = parseFloat( items[ pos + 1 ] );
			matParams.displacementScale = parseFloat( items[ pos + 2 ] );
			items.splice( pos, 3 );

		}

		pos = items.indexOf( '-s' );

		if ( pos >= 0 ) {

			texParams.scale.set( parseFloat( items[ pos + 1 ] ), parseFloat( items[ pos + 2 ] ) );
			items.splice( pos, 4 ); // we expect 3 parameters here!

		}

		pos = items.indexOf( '-o' );

		if ( pos >= 0 ) {

			texParams.offset.set( parseFloat( items[ pos + 1 ] ), parseFloat( items[ pos + 2 ] ) );
			items.splice( pos, 4 ); // we expect 3 parameters here!

		}

		texParams.url = items.join( ' ' ).trim();
		return texParams;

	}
```
</details>

##### `loadTexture(url: any, mapping: any, onLoad: any, onProgress: any, onError: any): any`

<details><summary>Code</summary>

```ts
loadTexture( url, mapping, onLoad, onProgress, onError ) {

		const manager = ( this.manager !== undefined ) ? this.manager : DefaultLoadingManager;
		let loader = manager.getHandler( url );

		if ( loader === null ) {

			loader = new TextureLoader( manager );

		}

		if ( loader.setCrossOrigin ) loader.setCrossOrigin( this.crossOrigin );

		const texture = loader.load( url, onLoad, onProgress, onError );

		if ( mapping !== undefined ) texture.mapping = mapping;

		return texture;

	}
```
</details>


---