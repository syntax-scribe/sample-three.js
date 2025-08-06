[⬅️ Back to Table of Contents](../../index.md)

# 📄 `WebGL3DRenderTarget.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/WebGL3DRenderTarget.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `WebGLRenderTarget` | `./WebGLRenderTarget.js` |
| `Data3DTexture` | `../textures/Data3DTexture.js` |


---

## Classes

### `WebGL3DRenderTarget`

<details><summary>Class Code</summary>

```ts
class WebGL3DRenderTarget extends WebGLRenderTarget {

	/**
	 * Constructs a new 3D render target.
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
		this.isWebGL3DRenderTarget = true;

		this.depth = depth;

		/**
		 * Overwritten with a different texture type.
		 *
		 * @type {Data3DTexture}
		 */
		this.texture = new Data3DTexture( null, width, height, depth );
		this._setTextureOptions( options );

		this.texture.isRenderTargetTexture = true;

	}

}
```
</details>


---