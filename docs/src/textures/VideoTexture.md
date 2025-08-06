[⬅️ Back to Table of Contents](../../index.md)

# 📄 `VideoTexture.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/textures/VideoTexture.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LinearFilter` | `../constants.js` |
| `Texture` | `./Texture.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `video` | `any` | let/var | `this.image` | ✗ |
| `hasVideoFrameCallback` | `boolean` | let/var | `'requestVideoFrameCallback' in video` | ✗ |


---

## Functions

### `VideoTexture.clone(): any`

**Returns:** `any`

**Calls:**

- `new this.constructor( this.image ).copy`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor( this.image ).copy( this );

	}
```
</details>

### `VideoTexture.update(): void`

**JSDoc:**
```typescript
/**
	 * This method is called automatically by the renderer and sets {@link Texture#needsUpdate}
	 * to `true` every time a new frame is available.
	 *
	 * Only relevant if `requestVideoFrameCallback` is not supported in the browser.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
update() {

		const video = this.image;
		const hasVideoFrameCallback = 'requestVideoFrameCallback' in video;

		if ( hasVideoFrameCallback === false && video.readyState >= video.HAVE_CURRENT_DATA ) {

			this.needsUpdate = true;

		}

	}
```
</details>

### `VideoTexture.dispose(): void`

**JSDoc:**
```typescript
/**
	 * @override
	 */
```

**Returns:** `void`

**Calls:**

- `this.source.data.cancelVideoFrameCallback`
- `super.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		if ( this._requestVideoFrameCallbackId !== 0 ) {

			this.source.data.cancelVideoFrameCallback( this._requestVideoFrameCallbackId );

		}

		super.dispose();

	}
```
</details>

### `updateVideo(): void`

**Returns:** `void`

**Calls:**

- `video.requestVideoFrameCallback`

<details><summary>Code</summary>

```typescript
function updateVideo() {

			scope.needsUpdate = true;
			scope._requestVideoFrameCallbackId = video.requestVideoFrameCallback( updateVideo );

		}
```
</details>


---

## Classes

### `VideoTexture`

<details><summary>Class Code</summary>

```ts
class VideoTexture extends Texture {

	/**
	 * Constructs a new video texture.
	 *
	 * @param {HTMLVideoElement} video - The video element to use as a data source for the texture.
	 * @param {number} [mapping=Texture.DEFAULT_MAPPING] - The texture mapping.
	 * @param {number} [wrapS=ClampToEdgeWrapping] - The wrapS value.
	 * @param {number} [wrapT=ClampToEdgeWrapping] - The wrapT value.
	 * @param {number} [magFilter=LinearFilter] - The mag filter value.
	 * @param {number} [minFilter=LinearFilter] - The min filter value.
	 * @param {number} [format=RGBAFormat] - The texture format.
	 * @param {number} [type=UnsignedByteType] - The texture type.
	 * @param {number} [anisotropy=Texture.DEFAULT_ANISOTROPY] - The anisotropy value.
	 */
	constructor( video, mapping, wrapS, wrapT, magFilter = LinearFilter, minFilter = LinearFilter, format, type, anisotropy ) {

		super( video, mapping, wrapS, wrapT, magFilter, minFilter, format, type, anisotropy );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isVideoTexture = true;

		/**
		 * Whether to generate mipmaps (if possible) for a texture.
		 *
		 * Overwritten and set to `false` by default.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.generateMipmaps = false;

		/**
		 * The video frame request callback identifier, which is a positive integer.
		 *
		 * Value of 0 represents no scheduled rVFC.
		 *
		 * @private
		 * @type {number}
		 */
		this._requestVideoFrameCallbackId = 0;

		const scope = this;

		function updateVideo() {

			scope.needsUpdate = true;
			scope._requestVideoFrameCallbackId = video.requestVideoFrameCallback( updateVideo );

		}

		if ( 'requestVideoFrameCallback' in video ) {

			this._requestVideoFrameCallbackId = video.requestVideoFrameCallback( updateVideo );

		}

	}

	clone() {

		return new this.constructor( this.image ).copy( this );

	}

	/**
	 * This method is called automatically by the renderer and sets {@link Texture#needsUpdate}
	 * to `true` every time a new frame is available.
	 *
	 * Only relevant if `requestVideoFrameCallback` is not supported in the browser.
	 */
	update() {

		const video = this.image;
		const hasVideoFrameCallback = 'requestVideoFrameCallback' in video;

		if ( hasVideoFrameCallback === false && video.readyState >= video.HAVE_CURRENT_DATA ) {

			this.needsUpdate = true;

		}

	}

	/**
	 * @override
	 */
	dispose() {

		if ( this._requestVideoFrameCallbackId !== 0 ) {

			this.source.data.cancelVideoFrameCallback( this._requestVideoFrameCallbackId );

		}

		super.dispose();

	}

}
```
</details>

#### Methods

##### `clone(): any`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor( this.image ).copy( this );

	}
```
</details>

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		const video = this.image;
		const hasVideoFrameCallback = 'requestVideoFrameCallback' in video;

		if ( hasVideoFrameCallback === false && video.readyState >= video.HAVE_CURRENT_DATA ) {

			this.needsUpdate = true;

		}

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		if ( this._requestVideoFrameCallbackId !== 0 ) {

			this.source.data.cancelVideoFrameCallback( this._requestVideoFrameCallbackId );

		}

		super.dispose();

	}
```
</details>


---