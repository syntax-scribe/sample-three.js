[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `StorageBufferAttribute.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/StorageBufferAttribute.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferAttribute` | `../../core/BufferAttribute.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `array` | `any` | let/var | `ArrayBuffer.isView( count ) ? count : new typeClass( count * itemSize )` | ✗ |


---

## Classes

### `StorageBufferAttribute`

<details><summary>Class Code</summary>

```ts
class StorageBufferAttribute extends BufferAttribute {

	/**
	 * Constructs a new storage buffer attribute.
	 *
	 * @param {number|TypedArray} count - The item count. It is also valid to pass a typed array as an argument.
	 * The subsequent parameters are then obsolete.
	 * @param {number} itemSize - The item size.
	 * @param {TypedArray.constructor} [typeClass=Float32Array] - A typed array constructor.
	 */
	constructor( count, itemSize, typeClass = Float32Array ) {

		const array = ArrayBuffer.isView( count ) ? count : new typeClass( count * itemSize );

		super( array, itemSize );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isStorageBufferAttribute = true;

	}

}
```
</details>


---