[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `StorageArrayTexture.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/StorageArrayTexture.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Texture` | `../../textures/Texture.js` |
| `LinearFilter` | `../../constants.js` |


---

## Functions

### `StorageArrayTexture.setSize(width: number, height: number, depth: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the size of the storage array texture.
	 *
	 * @param {number} width - The new width of the storage texture.
	 * @param {number} height - The new height of the storage texture.
	 * @param {number} depth - The new depth of the storage texture.
	 */
```

**Parameters:**

- **`width`** `number`
- **`height`** `number`
- **`depth`** `number`

**Returns:** `void`

**Calls:**

- `this.dispose`

<details><summary>Code</summary>

```typescript
setSize( width, height, depth ) {

		if ( this.image.width !== width || this.image.height !== height || this.image.depth !== depth ) {

			this.image.width = width;
			this.image.height = height;
			this.image.depth = depth;

			this.dispose();

		}

	}
```
</details>


---

## Classes

### `StorageArrayTexture`

<details><summary>Class Code</summary>

```ts
class StorageArrayTexture extends Texture {

	/**
	 * Constructs a new storage texture.
	 *
	 * @param {number} [width=1] - The storage texture's width.
	 * @param {number} [height=1] - The storage texture's height.
	 * @param {number} [depth=1] - The storage texture's depth.
	 */
	constructor( width = 1, height = 1, depth = 1 ) {

		super();

		//inherited from texture
		this.isArrayTexture = true;

		/**
		 * The image object which just represents the texture's dimension.
		 *
		 * @type {{width: number, height: number, depth: number}}
		 */
		this.image = { width, height, depth };

		/**
		 * The default `magFilter` for storage textures is `THREE.LinearFilter`.
		 *
		 * @type {number}
		 */
		this.magFilter = LinearFilter;

		/**
		 * The default `minFilter` for storage textures is `THREE.LinearFilter`.
		 *
		 * @type {number}
		 */
		this.minFilter = LinearFilter;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isStorageTexture = true;

	}

	/**
	 * Sets the size of the storage array texture.
	 *
	 * @param {number} width - The new width of the storage texture.
	 * @param {number} height - The new height of the storage texture.
	 * @param {number} depth - The new depth of the storage texture.
	 */
	setSize( width, height, depth ) {

		if ( this.image.width !== width || this.image.height !== height || this.image.depth !== depth ) {

			this.image.width = width;
			this.image.height = height;
			this.image.depth = depth;

			this.dispose();

		}

	}

}
```
</details>

#### Methods

##### `setSize(width: number, height: number, depth: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height, depth ) {

		if ( this.image.width !== width || this.image.height !== height || this.image.depth !== depth ) {

			this.image.width = width;
			this.image.height = height;
			this.image.depth = depth;

			this.dispose();

		}

	}
```
</details>


---