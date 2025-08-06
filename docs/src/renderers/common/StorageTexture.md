[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `StorageTexture.js`

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
📂 **`src/renderers/common/StorageTexture.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Texture` | `../../textures/Texture.js` |
| `LinearFilter` | `../../constants.js` |


---

## Functions

### `StorageTexture.setSize(width: number, height: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the size of the storage texture.
	 *
	 * @param {number} width - The new width of the storage texture.
	 * @param {number} height - The new height of the storage texture.
	 */
```

**Parameters:**

- **`width`** `number`
- **`height`** `number`

**Returns:** `void`

**Calls:**

- `this.dispose`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		if ( this.image.width !== width || this.image.height !== height ) {

			this.image.width = width;
			this.image.height = height;

			this.dispose();

		}

	}
```
</details>


---

## Classes

### `StorageTexture`

<details><summary>Class Code</summary>

```ts
class StorageTexture extends Texture {

	/**
	 * Constructs a new storage texture.
	 *
	 * @param {number} [width=1] - The storage texture's width.
	 * @param {number} [height=1] - The storage texture's height.
	 */
	constructor( width = 1, height = 1 ) {

		super();

		/**
		 * The image object which just represents the texture's dimension.
		 *
		 * @type {{width: number, height: number}}
		 */
		this.image = { width, height };

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
	 * Sets the size of the storage texture.
	 *
	 * @param {number} width - The new width of the storage texture.
	 * @param {number} height - The new height of the storage texture.
	 */
	setSize( width, height ) {

		if ( this.image.width !== width || this.image.height !== height ) {

			this.image.width = width;
			this.image.height = height;

			this.dispose();

		}

	}

}
```
</details>

#### Methods

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		if ( this.image.width !== width || this.image.height !== height ) {

			this.image.width = width;
			this.image.height = height;

			this.dispose();

		}

	}
```
</details>


---