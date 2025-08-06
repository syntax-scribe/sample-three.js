[⬅️ Back to Table of Contents](../../index.md)

# 📄 `VideoFrameTexture.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/textures/VideoFrameTexture.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `VideoTexture` | `./VideoTexture.js` |


---

## Functions

### `VideoFrameTexture.update(): void`

**JSDoc:**
```typescript
/**
	 * This method overwritten with an empty implementation since
	 * this type of texture is updated via `setFrame()`.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
update() {}
```
</details>

### `VideoFrameTexture.clone(): any`

**Returns:** `any`

**Calls:**

- `new this.constructor().copy`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor().copy( this ); // restoring Texture.clone()

	}
```
</details>

### `VideoFrameTexture.setFrame(frame: VideoFrame): void`

**JSDoc:**
```typescript
/**
	 * Sets the current frame of the video. This will automatically update the texture
	 * so the data can be used for rendering.
	 *
	 * @param {VideoFrame} frame - The video frame.
	 */
```

**Parameters:**

- **`frame`** `VideoFrame`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setFrame( frame ) {

		this.image = frame;
		this.needsUpdate = true;

	}
```
</details>


---

## Classes

### `VideoFrameTexture`

<details><summary>Class Code</summary>

```ts
class VideoFrameTexture extends VideoTexture {

	/**
	 * Constructs a new video frame texture.
	 *
	 * @param {number} [mapping=Texture.DEFAULT_MAPPING] - The texture mapping.
	 * @param {number} [wrapS=ClampToEdgeWrapping] - The wrapS value.
	 * @param {number} [wrapT=ClampToEdgeWrapping] - The wrapT value.
	 * @param {number} [magFilter=LinearFilter] - The mag filter value.
	 * @param {number} [minFilter=LinearFilter] - The min filter value.
	 * @param {number} [format=RGBAFormat] - The texture format.
	 * @param {number} [type=UnsignedByteType] - The texture type.
	 * @param {number} [anisotropy=Texture.DEFAULT_ANISOTROPY] - The anisotropy value.
	 */
	constructor( mapping, wrapS, wrapT, magFilter, minFilter, format, type, anisotropy ) {

		super( {}, mapping, wrapS, wrapT, magFilter, minFilter, format, type, anisotropy );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isVideoFrameTexture = true;

	}

	/**
	 * This method overwritten with an empty implementation since
	 * this type of texture is updated via `setFrame()`.
	 */
	update() {}

	clone() {

		return new this.constructor().copy( this ); // restoring Texture.clone()

	}

	/**
	 * Sets the current frame of the video. This will automatically update the texture
	 * so the data can be used for rendering.
	 *
	 * @param {VideoFrame} frame - The video frame.
	 */
	setFrame( frame ) {

		this.image = frame;
		this.needsUpdate = true;

	}

}
```
</details>

#### Methods

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {}
```
</details>

##### `clone(): any`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor().copy( this ); // restoring Texture.clone()

	}
```
</details>

##### `setFrame(frame: VideoFrame): void`

<details><summary>Code</summary>

```ts
setFrame( frame ) {

		this.image = frame;
		this.needsUpdate = true;

	}
```
</details>


---