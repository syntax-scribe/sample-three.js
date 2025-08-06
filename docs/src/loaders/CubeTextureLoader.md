[⬅️ Back to Table of Contents](../../index.md)

# 📄 `CubeTextureLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/loaders/CubeTextureLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ImageLoader` | `./ImageLoader.js` |
| `CubeTexture` | `../textures/CubeTexture.js` |
| `Loader` | `./Loader.js` |
| `SRGBColorSpace` | `../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `texture` | `CubeTexture` | let/var | `new CubeTexture()` | ✗ |
| `loader` | `ImageLoader` | let/var | `new ImageLoader( this.manager )` | ✗ |
| `loaded` | `number` | let/var | `0` | ✗ |


---

## Functions

### `CubeTextureLoader.load(urls: string[], onLoad: (arg0: CubeTexture) => any, onProgress: onProgressCallback, onError: onErrorCallback): CubeTexture`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and pass the fully loaded cube texture
	 * to the `onLoad()` callback. The method also returns a new cube texture object which can
	 * directly be used for material creation. If you do it this way, the cube texture
	 * may pop up in your scene once the respective loading process is finished.
	 *
	 * @param {Array<string>} urls - Array of 6 URLs to images, one for each side of the
	 * cube texture. The urls should be specified in the following order: pos-x,
	 * neg-x, pos-y, neg-y, pos-z, neg-z. An array of data URIs are allowed as well.
	 * @param {function(CubeTexture)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Unsupported in this loader.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 * @return {CubeTexture} The cube texture.
	 */
```

**Parameters:**

- **`urls`** `string[]`
- **`onLoad`** `(arg0: CubeTexture) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `CubeTexture`

**Calls:**

- `loader.setCrossOrigin`
- `loader.setPath`
- `loader.load`
- `onLoad`
- `loadTexture`

<details><summary>Code</summary>

```typescript
load( urls, onLoad, onProgress, onError ) {

		const texture = new CubeTexture();
		texture.colorSpace = SRGBColorSpace;

		const loader = new ImageLoader( this.manager );
		loader.setCrossOrigin( this.crossOrigin );
		loader.setPath( this.path );

		let loaded = 0;

		function loadTexture( i ) {

			loader.load( urls[ i ], function ( image ) {

				texture.images[ i ] = image;

				loaded ++;

				if ( loaded === 6 ) {

					texture.needsUpdate = true;

					if ( onLoad ) onLoad( texture );

				}

			}, undefined, onError );

		}

		for ( let i = 0; i < urls.length; ++ i ) {

			loadTexture( i );

		}

		return texture;

	}
```
</details>

### `loadTexture(i: any): void`

**Parameters:**

- **`i`** `any`

**Returns:** `void`

**Calls:**

- `loader.load`
- `onLoad`

<details><summary>Code</summary>

```typescript
function loadTexture( i ) {

			loader.load( urls[ i ], function ( image ) {

				texture.images[ i ] = image;

				loaded ++;

				if ( loaded === 6 ) {

					texture.needsUpdate = true;

					if ( onLoad ) onLoad( texture );

				}

			}, undefined, onError );

		}
```
</details>


---

## Classes

### `CubeTextureLoader`

<details><summary>Class Code</summary>

```ts
class CubeTextureLoader extends Loader {

	/**
	 * Constructs a new cube texture loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Starts loading from the given URL and pass the fully loaded cube texture
	 * to the `onLoad()` callback. The method also returns a new cube texture object which can
	 * directly be used for material creation. If you do it this way, the cube texture
	 * may pop up in your scene once the respective loading process is finished.
	 *
	 * @param {Array<string>} urls - Array of 6 URLs to images, one for each side of the
	 * cube texture. The urls should be specified in the following order: pos-x,
	 * neg-x, pos-y, neg-y, pos-z, neg-z. An array of data URIs are allowed as well.
	 * @param {function(CubeTexture)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Unsupported in this loader.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 * @return {CubeTexture} The cube texture.
	 */
	load( urls, onLoad, onProgress, onError ) {

		const texture = new CubeTexture();
		texture.colorSpace = SRGBColorSpace;

		const loader = new ImageLoader( this.manager );
		loader.setCrossOrigin( this.crossOrigin );
		loader.setPath( this.path );

		let loaded = 0;

		function loadTexture( i ) {

			loader.load( urls[ i ], function ( image ) {

				texture.images[ i ] = image;

				loaded ++;

				if ( loaded === 6 ) {

					texture.needsUpdate = true;

					if ( onLoad ) onLoad( texture );

				}

			}, undefined, onError );

		}

		for ( let i = 0; i < urls.length; ++ i ) {

			loadTexture( i );

		}

		return texture;

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
		texture.colorSpace = SRGBColorSpace;

		const loader = new ImageLoader( this.manager );
		loader.setCrossOrigin( this.crossOrigin );
		loader.setPath( this.path );

		let loaded = 0;

		function loadTexture( i ) {

			loader.load( urls[ i ], function ( image ) {

				texture.images[ i ] = image;

				loaded ++;

				if ( loaded === 6 ) {

					texture.needsUpdate = true;

					if ( onLoad ) onLoad( texture );

				}

			}, undefined, onError );

		}

		for ( let i = 0; i < urls.length; ++ i ) {

			loadTexture( i );

		}

		return texture;

	}
```
</details>


---