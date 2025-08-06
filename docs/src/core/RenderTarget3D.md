[⬅️ Back to Table of Contents](../../index.md)

# 📄 `RenderTarget3D.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/core/RenderTarget3D.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `RenderTarget` | `./RenderTarget.js` |
| `Data3DTexture` | `../textures/Data3DTexture.js` |


---

## Classes

### `RenderTarget3D`

<details><summary>Class Code</summary>

```ts
class RenderTarget3D extends RenderTarget {

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
		this.isRenderTarget3D = true;

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