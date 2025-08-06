[⬅️ Back to Table of Contents](../../index.md)

# 📄 `ExternalTexture.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/textures/ExternalTexture.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Texture` | `./Texture.js` |


---

## Classes

### `ExternalTexture`

<details><summary>Class Code</summary>

```ts
class ExternalTexture extends Texture {

	/**
	 * Creates a new raw texture.
	 *
	 * @param {?WebGLTexture} [sourceTexture=null] - The external texture.
	 */
	constructor( sourceTexture = null ) {

		super();

		/**
		 * The external source texture.
		 *
		 * @type {?WebGLTexture}
		 * @default null
		 */
		this.sourceTexture = sourceTexture;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isExternalTexture = true;

	}

}
```
</details>


---