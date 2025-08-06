[⬅️ Back to Table of Contents](../../index.md)

# 📄 `CompressedArrayTexture.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/textures/CompressedArrayTexture.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ClampToEdgeWrapping` | `../constants.js` |
| `CompressedTexture` | `./CompressedTexture.js` |


---

## Functions

### `CompressedArrayTexture.addLayerUpdate(layerIndex: number): void`

**JSDoc:**
```typescript
/**
	 * Describes that a specific layer of the texture needs to be updated.
	 * Normally when {@link Texture#needsUpdate} is set to `true`, the
	 * entire compressed texture array is sent to the GPU. Marking specific
	 * layers will only transmit subsets of all mipmaps associated with a
	 * specific depth in the array which is often much more performant.
	 *
	 * @param {number} layerIndex - The layer index that should be updated.
	 */
```

**Parameters:**

- **`layerIndex`** `number`

**Returns:** `void`

**Calls:**

- `this.layerUpdates.add`

<details><summary>Code</summary>

```typescript
addLayerUpdate( layerIndex ) {

		this.layerUpdates.add( layerIndex );

	}
```
</details>

### `CompressedArrayTexture.clearLayerUpdates(): void`

**JSDoc:**
```typescript
/**
	 * Resets the layer updates registry.
	 */
```

**Returns:** `void`

**Calls:**

- `this.layerUpdates.clear`

<details><summary>Code</summary>

```typescript
clearLayerUpdates() {

		this.layerUpdates.clear();

	}
```
</details>


---

## Classes

### `CompressedArrayTexture`

<details><summary>Class Code</summary>

```ts
class CompressedArrayTexture extends CompressedTexture {

	/**
	 * Constructs a new compressed array texture.
	 *
	 * @param {Array<Object>} mipmaps - This array holds for all mipmaps (including the bases mip)
	 * the data and dimensions.
	 * @param {number} width - The width of the texture.
	 * @param {number} height - The height of the texture.
	 * @param {number} depth - The depth of the texture.
	 * @param {number} [format=RGBAFormat] - The min filter value.
	 * @param {number} [type=UnsignedByteType] - The min filter value.
	 */
	constructor( mipmaps, width, height, depth, format, type ) {

		super( mipmaps, width, height, format, type );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isCompressedArrayTexture = true;

		/**
		 * The image property of a compressed texture just defines its dimensions.
		 *
		 * @name CompressedArrayTexture#image
		 * @type {{width:number,height:number,depth:number}}
		 */
		this.image.depth = depth;

		/**
		 * This defines how the texture is wrapped in the depth and corresponds to
		 * *W* in UVW mapping.
		 *
		 * @type {(RepeatWrapping|ClampToEdgeWrapping|MirroredRepeatWrapping)}
		 * @default ClampToEdgeWrapping
		 */
		this.wrapR = ClampToEdgeWrapping;

		/**
		 * A set of all layers which need to be updated in the texture.
		 *
		 * @type {Set<number>}
		 */
		this.layerUpdates = new Set();

	}

	/**
	 * Describes that a specific layer of the texture needs to be updated.
	 * Normally when {@link Texture#needsUpdate} is set to `true`, the
	 * entire compressed texture array is sent to the GPU. Marking specific
	 * layers will only transmit subsets of all mipmaps associated with a
	 * specific depth in the array which is often much more performant.
	 *
	 * @param {number} layerIndex - The layer index that should be updated.
	 */
	addLayerUpdate( layerIndex ) {

		this.layerUpdates.add( layerIndex );

	}

	/**
	 * Resets the layer updates registry.
	 */
	clearLayerUpdates() {

		this.layerUpdates.clear();

	}

}
```
</details>

#### Methods

##### `addLayerUpdate(layerIndex: number): void`

<details><summary>Code</summary>

```ts
addLayerUpdate( layerIndex ) {

		this.layerUpdates.add( layerIndex );

	}
```
</details>

##### `clearLayerUpdates(): void`

<details><summary>Code</summary>

```ts
clearLayerUpdates() {

		this.layerUpdates.clear();

	}
```
</details>


---