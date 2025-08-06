[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `IndirectStorageBufferAttribute.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/IndirectStorageBufferAttribute.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `StorageBufferAttribute` | `./StorageBufferAttribute.js` |


---

## Classes

### `IndirectStorageBufferAttribute`

<details><summary>Class Code</summary>

```ts
class IndirectStorageBufferAttribute extends StorageBufferAttribute {

	/**
	 * Constructs a new storage buffer attribute.
	 *
	 * @param {number|Uint32Array} count - The item count. It is also valid to pass a `Uint32Array` as an argument.
	 * The subsequent parameter is then obsolete.
	 * @param {number} itemSize - The item size.
	 */
	constructor( count, itemSize ) {

		super( count, itemSize, Uint32Array );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isIndirectStorageBufferAttribute = true;

	}

}
```
</details>


---