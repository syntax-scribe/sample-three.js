[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `HDRCubeTextureLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/HDRCubeTextureLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `CubeTexture` | `three` |
| `DataTexture` | `three` |
| `FileLoader` | `three` |
| `FloatType` | `three` |
| `HalfFloatType` | `three` |
| `LinearFilter` | `three` |
| `LinearSRGBColorSpace` | `three` |
| `Loader` | `three` |
| `RGBELoader` | `../loaders/RGBELoader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `texture` | `any` | let/var | `new CubeTexture()` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `loaded` | `number` | let/var | `0` | ✗ |
| `dataTexture` | `any` | let/var | `new DataTexture( texData.data, texData.width, texData.height )` | ✗ |


---

## Functions

### `HDRCubeTextureLoader.load(urls: string[], onLoad: (arg0: CubeTexture) => any, onProgress: onProgressCallback, onError: onErrorCallback): CubeTexture`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URLs and passes the loaded HDR cube texture
	 * to the `onLoad()` callback.
	 *
	 * @param {Array<string>} urls - The paths/URLs of the files to be loaded. This can also be a data URIs.
	 * @param {function(CubeTexture)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 * @return {CubeTexture} The HDR cube texture.
	 */
```

**Parameters:**

- **`urls`** `string[]`
- **`onLoad`** `(arg0: CubeTexture) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `CubeTexture`

**Calls:**

- `new FileLoader( scope.manager )
				.setPath( scope.path )
				.setResponseType( 'arraybuffer' )
				.setWithCredentials( scope.withCredentials )
				.load`
- `scope.hdrLoader.parse`
- `onLoad`
- `loadHDRData`

<details><summary>Code</summary>

```typescript
load( urls, onLoad, onProgress, onError ) {

		const texture = new CubeTexture();

		texture.type = this.type;

		switch ( texture.type ) {

			case FloatType:

				texture.colorSpace = LinearSRGBColorSpace;
				texture.minFilter = LinearFilter;
				texture.magFilter = LinearFilter;
				texture.generateMipmaps = false;
				break;

			case HalfFloatType:

				texture.colorSpace = LinearSRGBColorSpace;
				texture.minFilter = LinearFilter;
				texture.magFilter = LinearFilter;
				texture.generateMipmaps = false;
				break;

		}

		const scope = this;

		let loaded = 0;

		function loadHDRData( i, onLoad, onProgress, onError ) {

			new FileLoader( scope.manager )
				.setPath( scope.path )
				.setResponseType( 'arraybuffer' )
				.setWithCredentials( scope.withCredentials )
				.load( urls[ i ], function ( buffer ) {

					loaded ++;

					const texData = scope.hdrLoader.parse( buffer );

					if ( ! texData ) return;

					if ( texData.data !== undefined ) {

						const dataTexture = new DataTexture( texData.data, texData.width, texData.height );

						dataTexture.type = texture.type;
						dataTexture.colorSpace = texture.colorSpace;
						dataTexture.format = texture.format;
						dataTexture.minFilter = texture.minFilter;
						dataTexture.magFilter = texture.magFilter;
						dataTexture.generateMipmaps = texture.generateMipmaps;

						texture.images[ i ] = dataTexture;

					}

					if ( loaded === 6 ) {

						texture.needsUpdate = true;
						if ( onLoad ) onLoad( texture );

					}

				}, onProgress, onError );

		}

		for ( let i = 0; i < urls.length; i ++ ) {

			loadHDRData( i, onLoad, onProgress, onError );

		}

		return texture;

	}
```
</details>

### `HDRCubeTextureLoader.setDataType(value: any): RGBELoader`

**JSDoc:**
```typescript
/**
	 * Sets the texture type.
	 *
	 * @param {(HalfFloatType|FloatType)} value - The texture type to set.
	 * @return {RGBELoader} A reference to this loader.
	 */
```

**Parameters:**

- **`value`** `any`

**Returns:** `RGBELoader`

**Calls:**

- `this.hdrLoader.setDataType`

<details><summary>Code</summary>

```typescript
setDataType( value ) {

		this.type = value;
		this.hdrLoader.setDataType( value );

		return this;

	}
```
</details>

### `loadHDRData(i: any, onLoad: any, onProgress: any, onError: any): void`

**Parameters:**

- **`i`** `any`
- **`onLoad`** `any`
- **`onProgress`** `any`
- **`onError`** `any`

**Returns:** `void`

**Calls:**

- `new FileLoader( scope.manager )
				.setPath( scope.path )
				.setResponseType( 'arraybuffer' )
				.setWithCredentials( scope.withCredentials )
				.load`
- `scope.hdrLoader.parse`
- `onLoad`

<details><summary>Code</summary>

```typescript
function loadHDRData( i, onLoad, onProgress, onError ) {

			new FileLoader( scope.manager )
				.setPath( scope.path )
				.setResponseType( 'arraybuffer' )
				.setWithCredentials( scope.withCredentials )
				.load( urls[ i ], function ( buffer ) {

					loaded ++;

					const texData = scope.hdrLoader.parse( buffer );

					if ( ! texData ) return;

					if ( texData.data !== undefined ) {

						const dataTexture = new DataTexture( texData.data, texData.width, texData.height );

						dataTexture.type = texture.type;
						dataTexture.colorSpace = texture.colorSpace;
						dataTexture.format = texture.format;
						dataTexture.minFilter = texture.minFilter;
						dataTexture.magFilter = texture.magFilter;
						dataTexture.generateMipmaps = texture.generateMipmaps;

						texture.images[ i ] = dataTexture;

					}

					if ( loaded === 6 ) {

						texture.needsUpdate = true;
						if ( onLoad ) onLoad( texture );

					}

				}, onProgress, onError );

		}
```
</details>


---

## Classes

### `HDRCubeTextureLoader`

<details><summary>Class Code</summary>

```ts
class HDRCubeTextureLoader extends Loader {

	/**
	 * Constructs a new HDR cube texture loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		/**
		 * The internal HDR loader that loads the
		 * individual textures for each cube face.
		 *
		 * @type {RGBELoader}
		 */
		this.hdrLoader = new RGBELoader();

		/**
		 * The texture type.
		 *
		 * @type {(HalfFloatType|FloatType)}
		 * @default HalfFloatType
		 */
		this.type = HalfFloatType;

	}

	/**
	 * Starts loading from the given URLs and passes the loaded HDR cube texture
	 * to the `onLoad()` callback.
	 *
	 * @param {Array<string>} urls - The paths/URLs of the files to be loaded. This can also be a data URIs.
	 * @param {function(CubeTexture)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 * @return {CubeTexture} The HDR cube texture.
	 */
	load( urls, onLoad, onProgress, onError ) {

		const texture = new CubeTexture();

		texture.type = this.type;

		switch ( texture.type ) {

			case FloatType:

				texture.colorSpace = LinearSRGBColorSpace;
				texture.minFilter = LinearFilter;
				texture.magFilter = LinearFilter;
				texture.generateMipmaps = false;
				break;

			case HalfFloatType:

				texture.colorSpace = LinearSRGBColorSpace;
				texture.minFilter = LinearFilter;
				texture.magFilter = LinearFilter;
				texture.generateMipmaps = false;
				break;

		}

		const scope = this;

		let loaded = 0;

		function loadHDRData( i, onLoad, onProgress, onError ) {

			new FileLoader( scope.manager )
				.setPath( scope.path )
				.setResponseType( 'arraybuffer' )
				.setWithCredentials( scope.withCredentials )
				.load( urls[ i ], function ( buffer ) {

					loaded ++;

					const texData = scope.hdrLoader.parse( buffer );

					if ( ! texData ) return;

					if ( texData.data !== undefined ) {

						const dataTexture = new DataTexture( texData.data, texData.width, texData.height );

						dataTexture.type = texture.type;
						dataTexture.colorSpace = texture.colorSpace;
						dataTexture.format = texture.format;
						dataTexture.minFilter = texture.minFilter;
						dataTexture.magFilter = texture.magFilter;
						dataTexture.generateMipmaps = texture.generateMipmaps;

						texture.images[ i ] = dataTexture;

					}

					if ( loaded === 6 ) {

						texture.needsUpdate = true;
						if ( onLoad ) onLoad( texture );

					}

				}, onProgress, onError );

		}

		for ( let i = 0; i < urls.length; i ++ ) {

			loadHDRData( i, onLoad, onProgress, onError );

		}

		return texture;

	}

	/**
	 * Sets the texture type.
	 *
	 * @param {(HalfFloatType|FloatType)} value - The texture type to set.
	 * @return {RGBELoader} A reference to this loader.
	 */
	setDataType( value ) {

		this.type = value;
		this.hdrLoader.setDataType( value );

		return this;

	}

}
```
</details>

#### Methods

##### `load(urls: string[], onLoad: (arg0: CubeTexture) => any, onProgress: onProgressCallback, onError: onErrorCallback): CubeTexture`

<details><summary>Code</summary>

```ts
load( urls, onLoad, onProgress, onError ) {

		const texture = new CubeTexture();

		texture.type = this.type;

		switch ( texture.type ) {

			case FloatType:

				texture.colorSpace = LinearSRGBColorSpace;
				texture.minFilter = LinearFilter;
				texture.magFilter = LinearFilter;
				texture.generateMipmaps = false;
				break;

			case HalfFloatType:

				texture.colorSpace = LinearSRGBColorSpace;
				texture.minFilter = LinearFilter;
				texture.magFilter = LinearFilter;
				texture.generateMipmaps = false;
				break;

		}

		const scope = this;

		let loaded = 0;

		function loadHDRData( i, onLoad, onProgress, onError ) {

			new FileLoader( scope.manager )
				.setPath( scope.path )
				.setResponseType( 'arraybuffer' )
				.setWithCredentials( scope.withCredentials )
				.load( urls[ i ], function ( buffer ) {

					loaded ++;

					const texData = scope.hdrLoader.parse( buffer );

					if ( ! texData ) return;

					if ( texData.data !== undefined ) {

						const dataTexture = new DataTexture( texData.data, texData.width, texData.height );

						dataTexture.type = texture.type;
						dataTexture.colorSpace = texture.colorSpace;
						dataTexture.format = texture.format;
						dataTexture.minFilter = texture.minFilter;
						dataTexture.magFilter = texture.magFilter;
						dataTexture.generateMipmaps = texture.generateMipmaps;

						texture.images[ i ] = dataTexture;

					}

					if ( loaded === 6 ) {

						texture.needsUpdate = true;
						if ( onLoad ) onLoad( texture );

					}

				}, onProgress, onError );

		}

		for ( let i = 0; i < urls.length; i ++ ) {

			loadHDRData( i, onLoad, onProgress, onError );

		}

		return texture;

	}
```
</details>

##### `setDataType(value: any): RGBELoader`

<details><summary>Code</summary>

```ts
setDataType( value ) {

		this.type = value;
		this.hdrLoader.setDataType( value );

		return this;

	}
```
</details>


---