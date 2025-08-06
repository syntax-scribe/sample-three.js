[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `UniformBuffer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/UniformBuffer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Buffer` | `./Buffer.js` |


---

## Classes

### `UniformBuffer`

<details><summary>Class Code</summary>

```ts
class UniformBuffer extends Buffer {

	/**
	 * Constructs a new uniform buffer.
	 *
	 * @param {string} name - The buffer's name.
	 * @param {TypedArray} [buffer=null] - The buffer.
	 */
	constructor( name, buffer = null ) {

		super( name, buffer );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isUniformBuffer = true;

	}

}
```
</details>


---