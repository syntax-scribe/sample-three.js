[⬅️ Back to Table of Contents](../../index.md)

# 📄 `ImageLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/loaders/ImageLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Cache` | `./Cache.js` |
| `Loader` | `./Loader.js` |
| `createElementNS` | `../utils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_loading` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `callbacks` | `any` | let/var | `_loading.get( this ) \|\| []` | ✗ |
| `callback` | `any` | let/var | `callbacks[ i ]` | ✗ |
| `callbacks` | `any` | let/var | `_loading.get( this ) \|\| []` | ✗ |
| `callback` | `any` | let/var | `callbacks[ i ]` | ✗ |


---

## Functions

### `ImageLoader.load(url: string, onLoad: (arg0: new (width?: number, height?: number) => HTMLImageElement) => any, onProgress: onProgressCallback, onError: onErrorCallback): new (width?: number, height?: number) => HTMLImageElement`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded image
	 * to the `onLoad()` callback. The method also returns a new `Image` object which can
	 * directly be used for texture creation. If you do it this way, the texture
	 * may pop up in your scene once the respective loading process is finished.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Image)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Unsupported in this loader.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 * @return {Image} The image.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: new (width?: number, height?: number) => HTMLImageElement) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `new (width?: number, height?: number) => HTMLImageElement`

**Calls:**

- `this.manager.resolveURL`
- `Cache.get`
- `scope.manager.itemStart`
- `setTimeout`
- `onLoad`
- `scope.manager.itemEnd`
- `_loading.get`
- `_loading.set`
- `arr.push`
- `createElementNS (from ../utils.js)`
- `removeEventListeners`
- `callback.onLoad`
- `_loading.delete`
- `onError`
- `Cache.remove`
- `callback.onError`
- `scope.manager.itemError`
- `image.removeEventListener`
- `image.addEventListener`
- `url.slice`
- `Cache.add`

**Internal Comments:**
```
// (x4)
```

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		if ( this.path !== undefined ) url = this.path + url;

		url = this.manager.resolveURL( url );

		const scope = this;

		const cached = Cache.get( `image:${url}` );

		if ( cached !== undefined ) {

			if ( cached.complete === true ) {

				scope.manager.itemStart( url );

				setTimeout( function () {

					if ( onLoad ) onLoad( cached );

					scope.manager.itemEnd( url );

				}, 0 );

			} else {

				let arr = _loading.get( cached );

				if ( arr === undefined ) {

					arr = [];
					_loading.set( cached, arr );

				}

				arr.push( { onLoad, onError } );

			}

			return cached;

		}

		const image = createElementNS( 'img' );

		function onImageLoad() {

			removeEventListeners();

			if ( onLoad ) onLoad( this );

			//

			const callbacks = _loading.get( this ) || [];

			for ( let i = 0; i < callbacks.length; i ++ ) {

				const callback = callbacks[ i ];
				if ( callback.onLoad ) callback.onLoad( this );

			}

			_loading.delete( this );

			scope.manager.itemEnd( url );

		}

		function onImageError( event ) {

			removeEventListeners();

			if ( onError ) onError( event );

			Cache.remove( `image:${url}` );

			//

			const callbacks = _loading.get( this ) || [];

			for ( let i = 0; i < callbacks.length; i ++ ) {

				const callback = callbacks[ i ];
				if ( callback.onError ) callback.onError( event );

			}

			_loading.delete( this );


			scope.manager.itemError( url );
			scope.manager.itemEnd( url );

		}

		function removeEventListeners() {

			image.removeEventListener( 'load', onImageLoad, false );
			image.removeEventListener( 'error', onImageError, false );

		}

		image.addEventListener( 'load', onImageLoad, false );
		image.addEventListener( 'error', onImageError, false );

		if ( url.slice( 0, 5 ) !== 'data:' ) {

			if ( this.crossOrigin !== undefined ) image.crossOrigin = this.crossOrigin;

		}

		Cache.add( `image:${url}`, image );
		scope.manager.itemStart( url );

		image.src = url;

		return image;

	}
```
</details>

### `onImageLoad(): void`

**Returns:** `void`

**Calls:**

- `removeEventListeners`
- `onLoad`
- `_loading.get`
- `callback.onLoad`
- `_loading.delete`
- `scope.manager.itemEnd`

**Internal Comments:**
```
// (x2)
```

<details><summary>Code</summary>

```typescript
function onImageLoad() {

			removeEventListeners();

			if ( onLoad ) onLoad( this );

			//

			const callbacks = _loading.get( this ) || [];

			for ( let i = 0; i < callbacks.length; i ++ ) {

				const callback = callbacks[ i ];
				if ( callback.onLoad ) callback.onLoad( this );

			}

			_loading.delete( this );

			scope.manager.itemEnd( url );

		}
```
</details>

### `onImageError(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `removeEventListeners`
- `onError`
- `Cache.remove`
- `_loading.get`
- `callback.onError`
- `_loading.delete`
- `scope.manager.itemError`
- `scope.manager.itemEnd`

**Internal Comments:**
```
// (x2)
```

<details><summary>Code</summary>

```typescript
function onImageError( event ) {

			removeEventListeners();

			if ( onError ) onError( event );

			Cache.remove( `image:${url}` );

			//

			const callbacks = _loading.get( this ) || [];

			for ( let i = 0; i < callbacks.length; i ++ ) {

				const callback = callbacks[ i ];
				if ( callback.onError ) callback.onError( event );

			}

			_loading.delete( this );


			scope.manager.itemError( url );
			scope.manager.itemEnd( url );

		}
```
</details>

### `removeEventListeners(): void`

**Returns:** `void`

**Calls:**

- `image.removeEventListener`

<details><summary>Code</summary>

```typescript
function removeEventListeners() {

			image.removeEventListener( 'load', onImageLoad, false );
			image.removeEventListener( 'error', onImageError, false );

		}
```
</details>


---

## Classes

### `ImageLoader`

<details><summary>Class Code</summary>

```ts
class ImageLoader extends Loader {

	/**
	 * Constructs a new image loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Starts loading from the given URL and passes the loaded image
	 * to the `onLoad()` callback. The method also returns a new `Image` object which can
	 * directly be used for texture creation. If you do it this way, the texture
	 * may pop up in your scene once the respective loading process is finished.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Image)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Unsupported in this loader.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 * @return {Image} The image.
	 */
	load( url, onLoad, onProgress, onError ) {

		if ( this.path !== undefined ) url = this.path + url;

		url = this.manager.resolveURL( url );

		const scope = this;

		const cached = Cache.get( `image:${url}` );

		if ( cached !== undefined ) {

			if ( cached.complete === true ) {

				scope.manager.itemStart( url );

				setTimeout( function () {

					if ( onLoad ) onLoad( cached );

					scope.manager.itemEnd( url );

				}, 0 );

			} else {

				let arr = _loading.get( cached );

				if ( arr === undefined ) {

					arr = [];
					_loading.set( cached, arr );

				}

				arr.push( { onLoad, onError } );

			}

			return cached;

		}

		const image = createElementNS( 'img' );

		function onImageLoad() {

			removeEventListeners();

			if ( onLoad ) onLoad( this );

			//

			const callbacks = _loading.get( this ) || [];

			for ( let i = 0; i < callbacks.length; i ++ ) {

				const callback = callbacks[ i ];
				if ( callback.onLoad ) callback.onLoad( this );

			}

			_loading.delete( this );

			scope.manager.itemEnd( url );

		}

		function onImageError( event ) {

			removeEventListeners();

			if ( onError ) onError( event );

			Cache.remove( `image:${url}` );

			//

			const callbacks = _loading.get( this ) || [];

			for ( let i = 0; i < callbacks.length; i ++ ) {

				const callback = callbacks[ i ];
				if ( callback.onError ) callback.onError( event );

			}

			_loading.delete( this );


			scope.manager.itemError( url );
			scope.manager.itemEnd( url );

		}

		function removeEventListeners() {

			image.removeEventListener( 'load', onImageLoad, false );
			image.removeEventListener( 'error', onImageError, false );

		}

		image.addEventListener( 'load', onImageLoad, false );
		image.addEventListener( 'error', onImageError, false );

		if ( url.slice( 0, 5 ) !== 'data:' ) {

			if ( this.crossOrigin !== undefined ) image.crossOrigin = this.crossOrigin;

		}

		Cache.add( `image:${url}`, image );
		scope.manager.itemStart( url );

		image.src = url;

		return image;

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: new (width?: number, height?: number) => HTMLImageElement) => any, onProgress: onProgressCallback, onError: onErrorCallback): new (width?: number, height?: number) => HTMLImageElement`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		if ( this.path !== undefined ) url = this.path + url;

		url = this.manager.resolveURL( url );

		const scope = this;

		const cached = Cache.get( `image:${url}` );

		if ( cached !== undefined ) {

			if ( cached.complete === true ) {

				scope.manager.itemStart( url );

				setTimeout( function () {

					if ( onLoad ) onLoad( cached );

					scope.manager.itemEnd( url );

				}, 0 );

			} else {

				let arr = _loading.get( cached );

				if ( arr === undefined ) {

					arr = [];
					_loading.set( cached, arr );

				}

				arr.push( { onLoad, onError } );

			}

			return cached;

		}

		const image = createElementNS( 'img' );

		function onImageLoad() {

			removeEventListeners();

			if ( onLoad ) onLoad( this );

			//

			const callbacks = _loading.get( this ) || [];

			for ( let i = 0; i < callbacks.length; i ++ ) {

				const callback = callbacks[ i ];
				if ( callback.onLoad ) callback.onLoad( this );

			}

			_loading.delete( this );

			scope.manager.itemEnd( url );

		}

		function onImageError( event ) {

			removeEventListeners();

			if ( onError ) onError( event );

			Cache.remove( `image:${url}` );

			//

			const callbacks = _loading.get( this ) || [];

			for ( let i = 0; i < callbacks.length; i ++ ) {

				const callback = callbacks[ i ];
				if ( callback.onError ) callback.onError( event );

			}

			_loading.delete( this );


			scope.manager.itemError( url );
			scope.manager.itemEnd( url );

		}

		function removeEventListeners() {

			image.removeEventListener( 'load', onImageLoad, false );
			image.removeEventListener( 'error', onImageError, false );

		}

		image.addEventListener( 'load', onImageLoad, false );
		image.addEventListener( 'error', onImageError, false );

		if ( url.slice( 0, 5 ) !== 'data:' ) {

			if ( this.crossOrigin !== undefined ) image.crossOrigin = this.crossOrigin;

		}

		Cache.add( `image:${url}`, image );
		scope.manager.itemStart( url );

		image.src = url;

		return image;

	}
```
</details>


---