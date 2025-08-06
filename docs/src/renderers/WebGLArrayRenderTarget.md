[⬅️ Back to Table of Contents](../../index.md)

# 📄 `WebGLArrayRenderTarget.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/WebGLArrayRenderTarget.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `WebGLRenderTarget` | `./WebGLRenderTarget.js` |
| `DataArrayTexture` | `../textures/DataArrayTexture.js` |


---

## Classes

### `WebGLArrayRenderTarget`

<details><summary>Class Code</summary>

```ts
class WebGLArrayRenderTarget extends WebGLRenderTarget {

	/**
	 * Constructs a new array render target.
	 *
	 * @param {number} [width=1] - The width of the render target.
	 * @param {number} [height=1] - The height of the render target.
	 * @param {number} [depth=1] - The height of the render target.
	 * @param {RenderTarget~Options} [options] - The configuration object.
	 */
	constructor( width = 1, height = 1, depth = 1, options = {} ) {

		super( width, height, options );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isWebGLArrayRenderTarget = true;

		this.depth = depth;

		/**
		 * Overwritten with a different texture type.
		 *
		 * @type {DataArrayTexture}
		 */
		this.texture = new DataArrayTexture( null, width, height, depth );
		this._setTextureOptions( options );

		this.texture.isRenderTargetTexture = true;

	}

}
```
</details>


---