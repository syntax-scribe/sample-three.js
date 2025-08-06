[⬅️ Back to Table of Contents](../../index.md)

# 📄 `WebGLRenderTarget.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/WebGLRenderTarget.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `RenderTarget` | `../core/RenderTarget.js` |


---

## Classes

### `WebGLRenderTarget`

<details><summary>Class Code</summary>

```ts
class WebGLRenderTarget extends RenderTarget {

	/**
	 * Constructs a new 3D render target.
	 *
	 * @param {number} [width=1] - The width of the render target.
	 * @param {number} [height=1] - The height of the render target.
	 * @param {RenderTarget~Options} [options] - The configuration object.
	 */
	constructor( width = 1, height = 1, options = {} ) {

		super( width, height, options );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isWebGLRenderTarget = true;

	}

}
```
</details>


---