[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LUTImageLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 10 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/LUTImageLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Loader` | `three` |
| `TextureLoader` | `three` |
| `Data3DTexture` | `three` |
| `RGBAFormat` | `three` |
| `UnsignedByteType` | `three` |
| `ClampToEdgeWrapping` | `three` |
| `LinearFilter` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `loader` | `any` | let/var | `new TextureLoader( this.manager )` | ✗ |
| `imageData` | `any` | let/var | `*not shown*` | ✗ |
| `data` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( dataArray )` | ✗ |
| `texture3D` | `any` | let/var | `new Data3DTexture()` | ✗ |
| `width` | `any` | let/var | `texture.image.width` | ✗ |
| `height` | `any` | let/var | `texture.image.height` | ✗ |
| `width` | `any` | let/var | `texture.image.height` | ✗ |
| `height` | `any` | let/var | `texture.image.width` | ✗ |
| `sy` | `number` | let/var | `i * width` | ✗ |
| `dy` | `number` | let/var | `( this.flip ) ? height - i * width : i * width` | ✗ |


---

## Functions

### `LUTImageLoader.load(url: string, onLoad: (arg0: { size: number; texture3D: Data3DTexture; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded LUT
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({size:number,texture3D:Data3DTexture})} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: { size: number; texture3D: Data3DTexture; }) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `loader.setCrossOrigin`
- `loader.setPath`
- `loader.load`
- `this._getImageData`
- `this._horz2Vert`
- `onLoad`
- `this.parse`
- `Math.min`
- `onError`
- `console.error`
- `this.manager.itemError`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const loader = new TextureLoader( this.manager );

		loader.setCrossOrigin( this.crossOrigin );

		loader.setPath( this.path );
		loader.load( url, texture => {

			try {

				let imageData;

				if ( texture.image.width < texture.image.height ) {

					imageData = this._getImageData( texture );

				} else {

					imageData = this._horz2Vert( texture );

				}

				onLoad( this.parse( imageData.data, Math.min( texture.image.width, texture.image.height ) ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				this.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

### `LUTImageLoader.parse(dataArray: Uint8ClampedArray<ArrayBufferLike>, size: number): { size: number; texture3D: Data3DTexture; }`

**JSDoc:**
```typescript
/**
	 * Parses the given LUT data and returns the resulting 3D data texture.
	 *
	 * @param {Uint8ClampedArray} dataArray - The raw LUT data.
	 * @param {number} size - The LUT size.
	 * @return {{size:number,texture3D:Data3DTexture}} An object representing the parsed LUT.
	 */
```

**Parameters:**

- **`dataArray`** `Uint8ClampedArray<ArrayBufferLike>`
- **`size`** `number`

**Returns:** `{ size: number; texture3D: Data3DTexture; }`

<details><summary>Code</summary>

```typescript
parse( dataArray, size ) {

		const data = new Uint8Array( dataArray );

		const texture3D = new Data3DTexture();
		texture3D.image.data = data;
		texture3D.image.width = size;
		texture3D.image.height = size;
		texture3D.image.depth = size;
		texture3D.format = RGBAFormat;
		texture3D.type = UnsignedByteType;
		texture3D.magFilter = LinearFilter;
		texture3D.minFilter = LinearFilter;
		texture3D.wrapS = ClampToEdgeWrapping;
		texture3D.wrapT = ClampToEdgeWrapping;
		texture3D.wrapR = ClampToEdgeWrapping;
		texture3D.generateMipmaps = false;
		texture3D.needsUpdate = true;

		return {
			size,
			texture3D,
		};

	}
```
</details>

### `LUTImageLoader._getImageData(texture: any): ImageData`

**Parameters:**

- **`texture`** `any`

**Returns:** `ImageData`

**Calls:**

- `document.createElement`
- `canvas.getContext`
- `context.scale`
- `context.translate`
- `context.drawImage`
- `context.getImageData`

<details><summary>Code</summary>

```typescript
_getImageData( texture ) {

		const width = texture.image.width;
		const height = texture.image.height;

		const canvas = document.createElement( 'canvas' );
		canvas.width = width;
		canvas.height = height;

		const context = canvas.getContext( '2d' );

		if ( this.flip === true ) {

			context.scale( 1, - 1 );
			context.translate( 0, - height );

		}

		context.drawImage( texture.image, 0, 0 );

		return context.getImageData( 0, 0, width, height );

	}
```
</details>

### `LUTImageLoader._horz2Vert(texture: any): ImageData`

**Parameters:**

- **`texture`** `any`

**Returns:** `ImageData`

**Calls:**

- `document.createElement`
- `canvas.getContext`
- `context.scale`
- `context.translate`
- `context.drawImage`
- `context.getImageData`

<details><summary>Code</summary>

```typescript
_horz2Vert( texture ) {

		const width = texture.image.height;
		const height = texture.image.width;

		const canvas = document.createElement( 'canvas' );
		canvas.width = width;
		canvas.height = height;

		const context = canvas.getContext( '2d' );

		if ( this.flip === true ) {

			context.scale( 1, - 1 );
			context.translate( 0, - height );

		}

		for ( let i = 0; i < width; i ++ ) {

			const sy = i * width;
			const dy = ( this.flip ) ? height - i * width : i * width;
			context.drawImage( texture.image, sy, 0, width, width, 0, dy, width, width );

		}

		return context.getImageData( 0, 0, width, height );

	}
```
</details>


---

## Classes

### `LUTImageLoader`

<details><summary>Class Code</summary>

```ts
export class LUTImageLoader extends Loader {

	/**
	 * Constructs a new LUT loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		/**
		 * Whether to vertically flip the LUT or not.
		 *
		 * Depending on the LUT's origin, the texture has green at the bottom (e.g. for Unreal)
		 * or green at the top (e.g. for Unity URP Color Lookup). If you're using lut image strips
		 * from a Unity pipeline, then set this property to `true`.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.flip = false;

	}

	/**
	 * Starts loading from the given URL and passes the loaded LUT
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({size:number,texture3D:Data3DTexture})} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const loader = new TextureLoader( this.manager );

		loader.setCrossOrigin( this.crossOrigin );

		loader.setPath( this.path );
		loader.load( url, texture => {

			try {

				let imageData;

				if ( texture.image.width < texture.image.height ) {

					imageData = this._getImageData( texture );

				} else {

					imageData = this._horz2Vert( texture );

				}

				onLoad( this.parse( imageData.data, Math.min( texture.image.width, texture.image.height ) ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				this.manager.itemError( url );

			}

		}, onProgress, onError );

	}

	/**
	 * Parses the given LUT data and returns the resulting 3D data texture.
	 *
	 * @param {Uint8ClampedArray} dataArray - The raw LUT data.
	 * @param {number} size - The LUT size.
	 * @return {{size:number,texture3D:Data3DTexture}} An object representing the parsed LUT.
	 */
	parse( dataArray, size ) {

		const data = new Uint8Array( dataArray );

		const texture3D = new Data3DTexture();
		texture3D.image.data = data;
		texture3D.image.width = size;
		texture3D.image.height = size;
		texture3D.image.depth = size;
		texture3D.format = RGBAFormat;
		texture3D.type = UnsignedByteType;
		texture3D.magFilter = LinearFilter;
		texture3D.minFilter = LinearFilter;
		texture3D.wrapS = ClampToEdgeWrapping;
		texture3D.wrapT = ClampToEdgeWrapping;
		texture3D.wrapR = ClampToEdgeWrapping;
		texture3D.generateMipmaps = false;
		texture3D.needsUpdate = true;

		return {
			size,
			texture3D,
		};

	}

	// internal

	_getImageData( texture ) {

		const width = texture.image.width;
		const height = texture.image.height;

		const canvas = document.createElement( 'canvas' );
		canvas.width = width;
		canvas.height = height;

		const context = canvas.getContext( '2d' );

		if ( this.flip === true ) {

			context.scale( 1, - 1 );
			context.translate( 0, - height );

		}

		context.drawImage( texture.image, 0, 0 );

		return context.getImageData( 0, 0, width, height );

	}

	_horz2Vert( texture ) {

		const width = texture.image.height;
		const height = texture.image.width;

		const canvas = document.createElement( 'canvas' );
		canvas.width = width;
		canvas.height = height;

		const context = canvas.getContext( '2d' );

		if ( this.flip === true ) {

			context.scale( 1, - 1 );
			context.translate( 0, - height );

		}

		for ( let i = 0; i < width; i ++ ) {

			const sy = i * width;
			const dy = ( this.flip ) ? height - i * width : i * width;
			context.drawImage( texture.image, sy, 0, width, width, 0, dy, width, width );

		}

		return context.getImageData( 0, 0, width, height );

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: { size: number; texture3D: Data3DTexture; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const loader = new TextureLoader( this.manager );

		loader.setCrossOrigin( this.crossOrigin );

		loader.setPath( this.path );
		loader.load( url, texture => {

			try {

				let imageData;

				if ( texture.image.width < texture.image.height ) {

					imageData = this._getImageData( texture );

				} else {

					imageData = this._horz2Vert( texture );

				}

				onLoad( this.parse( imageData.data, Math.min( texture.image.width, texture.image.height ) ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				this.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

##### `parse(dataArray: Uint8ClampedArray<ArrayBufferLike>, size: number): { size: number; texture3D: Data3DTexture; }`

<details><summary>Code</summary>

```ts
parse( dataArray, size ) {

		const data = new Uint8Array( dataArray );

		const texture3D = new Data3DTexture();
		texture3D.image.data = data;
		texture3D.image.width = size;
		texture3D.image.height = size;
		texture3D.image.depth = size;
		texture3D.format = RGBAFormat;
		texture3D.type = UnsignedByteType;
		texture3D.magFilter = LinearFilter;
		texture3D.minFilter = LinearFilter;
		texture3D.wrapS = ClampToEdgeWrapping;
		texture3D.wrapT = ClampToEdgeWrapping;
		texture3D.wrapR = ClampToEdgeWrapping;
		texture3D.generateMipmaps = false;
		texture3D.needsUpdate = true;

		return {
			size,
			texture3D,
		};

	}
```
</details>

##### `_getImageData(texture: any): ImageData`

<details><summary>Code</summary>

```ts
_getImageData( texture ) {

		const width = texture.image.width;
		const height = texture.image.height;

		const canvas = document.createElement( 'canvas' );
		canvas.width = width;
		canvas.height = height;

		const context = canvas.getContext( '2d' );

		if ( this.flip === true ) {

			context.scale( 1, - 1 );
			context.translate( 0, - height );

		}

		context.drawImage( texture.image, 0, 0 );

		return context.getImageData( 0, 0, width, height );

	}
```
</details>

##### `_horz2Vert(texture: any): ImageData`

<details><summary>Code</summary>

```ts
_horz2Vert( texture ) {

		const width = texture.image.height;
		const height = texture.image.width;

		const canvas = document.createElement( 'canvas' );
		canvas.width = width;
		canvas.height = height;

		const context = canvas.getContext( '2d' );

		if ( this.flip === true ) {

			context.scale( 1, - 1 );
			context.translate( 0, - height );

		}

		for ( let i = 0; i < width; i ++ ) {

			const sy = i * width;
			const dy = ( this.flip ) ? height - i * width : i * width;
			context.drawImage( texture.image, sy, 0, width, width, 0, dy, width, width );

		}

		return context.getImageData( 0, 0, width, height );

	}
```
</details>


---