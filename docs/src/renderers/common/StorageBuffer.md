[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `StorageBuffer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/StorageBuffer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Buffer` | `./Buffer.js` |


---

## Classes

### `StorageBuffer`

<details><summary>Class Code</summary>

```ts
class StorageBuffer extends Buffer {

	/**
	 * Constructs a new uniform buffer.
	 *
	 * @param {string} name - The buffer's name.
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
	constructor( name, attribute ) {

		super( name, attribute ? attribute.array : null );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {BufferAttribute}
		 */
		this.attribute = attribute;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isStorageBuffer = true;

	}

}
```
</details>


---