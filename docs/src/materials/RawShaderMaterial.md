[⬅️ Back to Table of Contents](../../index.md)

# 📄 `RawShaderMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/RawShaderMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ShaderMaterial` | `./ShaderMaterial.js` |


---

## Classes

### `RawShaderMaterial`

<details><summary>Class Code</summary>

```ts
class RawShaderMaterial extends ShaderMaterial {

	/**
	 * Constructs a new raw shader material.
	 *
	 * @param {Object} [parameters] - An object with one or more properties
	 * defining the material's appearance. Any property of the material
	 * (including any property from inherited materials) can be passed
	 * in here. Color values can be passed any type of value accepted
	 * by {@link Color#set}.
	 */
	constructor( parameters ) {

		super( parameters );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isRawShaderMaterial = true;

		this.type = 'RawShaderMaterial';

	}

}
```
</details>


---