[⬅️ Back to Table of Contents](../../index.md)

# 📄 `ImageBitmapLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/loaders/ImageBitmapLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Cache` | `./Cache.js` |
| `Loader` | `./Loader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_errorMap` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `fetchOptions` | `{ credentials: string; headers: { [x:...` | let/var | `{}` | ✗ |


---

## Functions

### `ImageBitmapLoader.setOptions(options: any): ImageBitmapLoader`

**JSDoc:**
```typescript
/**
	 * Sets the given loader options. The structure of the object must match the `options` parameter of
	 * [createImageBitmap]{@link https://developer.mozilla.org/en-US/docs/Web/API/Window/createImageBitmap}.
	 *
	 * @param {Object} options - The loader options to set.
	 * @return {ImageBitmapLoader} A reference to this image bitmap loader.
	 */
```

**Parameters:**

- **`options`** `any`

**Returns:** `ImageBitmapLoader`

<details><summary>Code</summary>

```typescript
setOptions( options ) {

		this.options = options;

		return this;

	}
```
</details>

### `ImageBitmapLoader.load(url: string, onLoad: (arg0: ImageBitmap) => any, onProgress: onProgressCallback, onError: onErrorCallback): ImageBitmap`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and pass the loaded image bitmap to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(ImageBitmap)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Unsupported in this loader.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 * @return {ImageBitmap|undefined} The image bitmap.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: ImageBitmap) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `ImageBitmap`

**Calls:**

- `this.manager.resolveURL`
- `Cache.get`
- `scope.manager.itemStart`
- `cached.then`
- `_errorMap.has`
- `onError`
- `_errorMap.get`
- `scope.manager.itemError`
- `scope.manager.itemEnd`
- `onLoad`
- `setTimeout`
- `AbortSignal.any`
- `fetch( url, fetchOptions ).then( function ( res ) {

			return res.blob();

		} ).then( function ( blob ) {

			return createImageBitmap( blob, Object.assign( scope.options, { colorSpaceConversion: 'none' } ) );

		} ).then( function ( imageBitmap ) {

			Cache.add( `image-bitmap:${url}`, imageBitmap );

			if ( onLoad ) onLoad( imageBitmap );

			scope.manager.itemEnd( url );

			return imageBitmap;

		} ).catch`
- `_errorMap.set`
- `Cache.remove`
- `Cache.add`

**Internal Comments:**
```
// If cached is a promise, wait for it to resolve
// check if there is an error for the cached promise
// If cached is not a promise (i.e., it's already an imageBitmap) (x3)
```

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		if ( url === undefined ) url = '';

		if ( this.path !== undefined ) url = this.path + url;

		url = this.manager.resolveURL( url );

		const scope = this;

		const cached = Cache.get( `image-bitmap:${url}` );

		if ( cached !== undefined ) {

			scope.manager.itemStart( url );

			// If cached is a promise, wait for it to resolve
			if ( cached.then ) {

				cached.then( imageBitmap => {

					// check if there is an error for the cached promise

					if ( _errorMap.has( cached ) === true ) {

						if ( onError ) onError( _errorMap.get( cached ) );

						scope.manager.itemError( url );
						scope.manager.itemEnd( url );

					} else {

						if ( onLoad ) onLoad( imageBitmap );

						scope.manager.itemEnd( url );

						return imageBitmap;

					}

				} );

				return;

			}

			// If cached is not a promise (i.e., it's already an imageBitmap)
			setTimeout( function () {

				if ( onLoad ) onLoad( cached );

				scope.manager.itemEnd( url );

			}, 0 );

			return cached;

		}

		const fetchOptions = {};
		fetchOptions.credentials = ( this.crossOrigin === 'anonymous' ) ? 'same-origin' : 'include';
		fetchOptions.headers = this.requestHeader;
		fetchOptions.signal = ( typeof AbortSignal.any === 'function' ) ? AbortSignal.any( [ this._abortController.signal, this.manager.abortController.signal ] ) : this._abortController.signal;

		const promise = fetch( url, fetchOptions ).then( function ( res ) {

			return res.blob();

		} ).then( function ( blob ) {

			return createImageBitmap( blob, Object.assign( scope.options, { colorSpaceConversion: 'none' } ) );

		} ).then( function ( imageBitmap ) {

			Cache.add( `image-bitmap:${url}`, imageBitmap );

			if ( onLoad ) onLoad( imageBitmap );

			scope.manager.itemEnd( url );

			return imageBitmap;

		} ).catch( function ( e ) {

			if ( onError ) onError( e );

			_errorMap.set( promise, e );

			Cache.remove( `image-bitmap:${url}` );

			scope.manager.itemError( url );
			scope.manager.itemEnd( url );

		} );

		Cache.add( `image-bitmap:${url}`, promise );
		scope.manager.itemStart( url );

	}
```
</details>

### `ImageBitmapLoader.abort(): ImageBitmapLoader`

**JSDoc:**
```typescript
/**
	 * Aborts ongoing fetch requests.
	 *
	 * @return {ImageBitmapLoader} A reference to this instance.
	 */
```

**Returns:** `ImageBitmapLoader`

**Calls:**

- `this._abortController.abort`

<details><summary>Code</summary>

```typescript
abort() {

		this._abortController.abort();
		this._abortController = new AbortController();

		return this;

	}
```
</details>


---

## Classes

### `ImageBitmapLoader`

<details><summary>Class Code</summary>

```ts
class ImageBitmapLoader extends Loader {

	/**
	 * Constructs a new image bitmap loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isImageBitmapLoader = true;

		if ( typeof createImageBitmap === 'undefined' ) {

			console.warn( 'THREE.ImageBitmapLoader: createImageBitmap() not supported.' );

		}

		if ( typeof fetch === 'undefined' ) {

			console.warn( 'THREE.ImageBitmapLoader: fetch() not supported.' );

		}

		/**
		 * Represents the loader options.
		 *
		 * @type {Object}
		 * @default {premultiplyAlpha:'none'}
		 */
		this.options = { premultiplyAlpha: 'none' };

		/**
		 * Used for aborting requests.
		 *
		 * @private
		 * @type {AbortController}
		 */
		this._abortController = new AbortController();

	}

	/**
	 * Sets the given loader options. The structure of the object must match the `options` parameter of
	 * [createImageBitmap]{@link https://developer.mozilla.org/en-US/docs/Web/API/Window/createImageBitmap}.
	 *
	 * @param {Object} options - The loader options to set.
	 * @return {ImageBitmapLoader} A reference to this image bitmap loader.
	 */
	setOptions( options ) {

		this.options = options;

		return this;

	}

	/**
	 * Starts loading from the given URL and pass the loaded image bitmap to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(ImageBitmap)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Unsupported in this loader.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 * @return {ImageBitmap|undefined} The image bitmap.
	 */
	load( url, onLoad, onProgress, onError ) {

		if ( url === undefined ) url = '';

		if ( this.path !== undefined ) url = this.path + url;

		url = this.manager.resolveURL( url );

		const scope = this;

		const cached = Cache.get( `image-bitmap:${url}` );

		if ( cached !== undefined ) {

			scope.manager.itemStart( url );

			// If cached is a promise, wait for it to resolve
			if ( cached.then ) {

				cached.then( imageBitmap => {

					// check if there is an error for the cached promise

					if ( _errorMap.has( cached ) === true ) {

						if ( onError ) onError( _errorMap.get( cached ) );

						scope.manager.itemError( url );
						scope.manager.itemEnd( url );

					} else {

						if ( onLoad ) onLoad( imageBitmap );

						scope.manager.itemEnd( url );

						return imageBitmap;

					}

				} );

				return;

			}

			// If cached is not a promise (i.e., it's already an imageBitmap)
			setTimeout( function () {

				if ( onLoad ) onLoad( cached );

				scope.manager.itemEnd( url );

			}, 0 );

			return cached;

		}

		const fetchOptions = {};
		fetchOptions.credentials = ( this.crossOrigin === 'anonymous' ) ? 'same-origin' : 'include';
		fetchOptions.headers = this.requestHeader;
		fetchOptions.signal = ( typeof AbortSignal.any === 'function' ) ? AbortSignal.any( [ this._abortController.signal, this.manager.abortController.signal ] ) : this._abortController.signal;

		const promise = fetch( url, fetchOptions ).then( function ( res ) {

			return res.blob();

		} ).then( function ( blob ) {

			return createImageBitmap( blob, Object.assign( scope.options, { colorSpaceConversion: 'none' } ) );

		} ).then( function ( imageBitmap ) {

			Cache.add( `image-bitmap:${url}`, imageBitmap );

			if ( onLoad ) onLoad( imageBitmap );

			scope.manager.itemEnd( url );

			return imageBitmap;

		} ).catch( function ( e ) {

			if ( onError ) onError( e );

			_errorMap.set( promise, e );

			Cache.remove( `image-bitmap:${url}` );

			scope.manager.itemError( url );
			scope.manager.itemEnd( url );

		} );

		Cache.add( `image-bitmap:${url}`, promise );
		scope.manager.itemStart( url );

	}

	/**
	 * Aborts ongoing fetch requests.
	 *
	 * @return {ImageBitmapLoader} A reference to this instance.
	 */
	abort() {

		this._abortController.abort();
		this._abortController = new AbortController();

		return this;

	}

}
```
</details>

#### Methods

##### `setOptions(options: any): ImageBitmapLoader`

<details><summary>Code</summary>

```ts
setOptions( options ) {

		this.options = options;

		return this;

	}
```
</details>

##### `load(url: string, onLoad: (arg0: ImageBitmap) => any, onProgress: onProgressCallback, onError: onErrorCallback): ImageBitmap`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		if ( url === undefined ) url = '';

		if ( this.path !== undefined ) url = this.path + url;

		url = this.manager.resolveURL( url );

		const scope = this;

		const cached = Cache.get( `image-bitmap:${url}` );

		if ( cached !== undefined ) {

			scope.manager.itemStart( url );

			// If cached is a promise, wait for it to resolve
			if ( cached.then ) {

				cached.then( imageBitmap => {

					// check if there is an error for the cached promise

					if ( _errorMap.has( cached ) === true ) {

						if ( onError ) onError( _errorMap.get( cached ) );

						scope.manager.itemError( url );
						scope.manager.itemEnd( url );

					} else {

						if ( onLoad ) onLoad( imageBitmap );

						scope.manager.itemEnd( url );

						return imageBitmap;

					}

				} );

				return;

			}

			// If cached is not a promise (i.e., it's already an imageBitmap)
			setTimeout( function () {

				if ( onLoad ) onLoad( cached );

				scope.manager.itemEnd( url );

			}, 0 );

			return cached;

		}

		const fetchOptions = {};
		fetchOptions.credentials = ( this.crossOrigin === 'anonymous' ) ? 'same-origin' : 'include';
		fetchOptions.headers = this.requestHeader;
		fetchOptions.signal = ( typeof AbortSignal.any === 'function' ) ? AbortSignal.any( [ this._abortController.signal, this.manager.abortController.signal ] ) : this._abortController.signal;

		const promise = fetch( url, fetchOptions ).then( function ( res ) {

			return res.blob();

		} ).then( function ( blob ) {

			return createImageBitmap( blob, Object.assign( scope.options, { colorSpaceConversion: 'none' } ) );

		} ).then( function ( imageBitmap ) {

			Cache.add( `image-bitmap:${url}`, imageBitmap );

			if ( onLoad ) onLoad( imageBitmap );

			scope.manager.itemEnd( url );

			return imageBitmap;

		} ).catch( function ( e ) {

			if ( onError ) onError( e );

			_errorMap.set( promise, e );

			Cache.remove( `image-bitmap:${url}` );

			scope.manager.itemError( url );
			scope.manager.itemEnd( url );

		} );

		Cache.add( `image-bitmap:${url}`, promise );
		scope.manager.itemStart( url );

	}
```
</details>

##### `abort(): ImageBitmapLoader`

<details><summary>Code</summary>

```ts
abort() {

		this._abortController.abort();
		this._abortController = new AbortController();

		return this;

	}
```
</details>


---