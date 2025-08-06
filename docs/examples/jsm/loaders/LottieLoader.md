[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LottieLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/LottieLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `FileLoader` | `three` |
| `Loader` | `three` |
| `CanvasTexture` | `three` |
| `NearestFilter` | `three` |
| `SRGBColorSpace` | `three` |
| `lottie` | `../libs/lottie_canvas.module.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `quality` | `number` | let/var | `this._quality \|\| 1` | ✗ |
| `texture` | `any` | let/var | `new CanvasTexture()` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |


---

## Functions

### `LottieLoader.setQuality(value: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the texture quality.
	 *
	 * @param {number} value - The texture quality.
	 */
```

**Parameters:**

- **`value`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setQuality( value ) {

		this._quality = value;

	}
```
</details>

### `LottieLoader.load(url: string, onLoad: (arg0: CanvasTexture) => any, onProgress: onProgressCallback, onError: onErrorCallback): CanvasTexture`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded Lottie asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(CanvasTexture)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 * @returns {CanvasTexture} The Lottie texture.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: CanvasTexture) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `CanvasTexture`

**Calls:**

- `loader.setPath`
- `loader.setWithCredentials`
- `loader.load`
- `JSON.parse`
- `document.createElement`
- `document.body.appendChild`
- `lottie.loadAnimation`
- `animation.addEventListener`
- `onLoad`

**Internal Comments:**
```
// lottie uses container.offsetWidth and offsetHeight (x2)
// to define width/height (x2)
```

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const quality = this._quality || 1;

		const texture = new CanvasTexture();
		texture.minFilter = NearestFilter;
		texture.generateMipmaps = false;
		texture.colorSpace = SRGBColorSpace;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setWithCredentials( this.withCredentials );

		loader.load( url, function ( text ) {

			const data = JSON.parse( text );

			// lottie uses container.offsetWidth and offsetHeight
			// to define width/height

			const container = document.createElement( 'div' );
			container.style.width = data.w + 'px';
			container.style.height = data.h + 'px';
			document.body.appendChild( container );

			const animation = lottie.loadAnimation( {
				container: container,
				animType: 'canvas',
				loop: true,
				autoplay: true,
				animationData: data,
				rendererSettings: { dpr: quality }
			} );

			texture.animation = animation;
			texture.image = animation.container;

			animation.addEventListener( 'enterFrame', function () {

				texture.needsUpdate = true;

			} );

			container.style.display = 'none';

			if ( onLoad !== undefined ) {

				onLoad( texture );

			}

		}, onProgress, onError );

		return texture;

	}
```
</details>


---

## Classes

### `LottieLoader`

<details><summary>Class Code</summary>

```ts
class LottieLoader extends Loader {

	/**
	 * Constructs a new Lottie loader.
	 *
	 * @deprecated The loader has been deprecated and will be removed with r186. Use lottie-web instead and create your animated texture manually.
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		console.warn( 'THREE.LottieLoader: The loader has been deprecated and will be removed with r186. Use lottie-web instead and create your animated texture manually.' );

	}

	/**
	 * Sets the texture quality.
	 *
	 * @param {number} value - The texture quality.
	 */
	setQuality( value ) {

		this._quality = value;

	}

	/**
	 * Starts loading from the given URL and passes the loaded Lottie asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(CanvasTexture)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 * @returns {CanvasTexture} The Lottie texture.
	 */
	load( url, onLoad, onProgress, onError ) {

		const quality = this._quality || 1;

		const texture = new CanvasTexture();
		texture.minFilter = NearestFilter;
		texture.generateMipmaps = false;
		texture.colorSpace = SRGBColorSpace;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setWithCredentials( this.withCredentials );

		loader.load( url, function ( text ) {

			const data = JSON.parse( text );

			// lottie uses container.offsetWidth and offsetHeight
			// to define width/height

			const container = document.createElement( 'div' );
			container.style.width = data.w + 'px';
			container.style.height = data.h + 'px';
			document.body.appendChild( container );

			const animation = lottie.loadAnimation( {
				container: container,
				animType: 'canvas',
				loop: true,
				autoplay: true,
				animationData: data,
				rendererSettings: { dpr: quality }
			} );

			texture.animation = animation;
			texture.image = animation.container;

			animation.addEventListener( 'enterFrame', function () {

				texture.needsUpdate = true;

			} );

			container.style.display = 'none';

			if ( onLoad !== undefined ) {

				onLoad( texture );

			}

		}, onProgress, onError );

		return texture;

	}

}
```
</details>

#### Methods

##### `setQuality(value: number): void`

<details><summary>Code</summary>

```ts
setQuality( value ) {

		this._quality = value;

	}
```
</details>

##### `load(url: string, onLoad: (arg0: CanvasTexture) => any, onProgress: onProgressCallback, onError: onErrorCallback): CanvasTexture`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const quality = this._quality || 1;

		const texture = new CanvasTexture();
		texture.minFilter = NearestFilter;
		texture.generateMipmaps = false;
		texture.colorSpace = SRGBColorSpace;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setWithCredentials( this.withCredentials );

		loader.load( url, function ( text ) {

			const data = JSON.parse( text );

			// lottie uses container.offsetWidth and offsetHeight
			// to define width/height

			const container = document.createElement( 'div' );
			container.style.width = data.w + 'px';
			container.style.height = data.h + 'px';
			document.body.appendChild( container );

			const animation = lottie.loadAnimation( {
				container: container,
				animType: 'canvas',
				loop: true,
				autoplay: true,
				animationData: data,
				rendererSettings: { dpr: quality }
			} );

			texture.animation = animation;
			texture.image = animation.container;

			animation.addEventListener( 'enterFrame', function () {

				texture.needsUpdate = true;

			} );

			container.style.display = 'none';

			if ( onLoad !== undefined ) {

				onLoad( texture );

			}

		}, onProgress, onError );

		return texture;

	}
```
</details>


---