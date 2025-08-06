[⬅️ Back to Table of Contents](../../index.md)

# 📄 `FramebufferTexture.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/textures/FramebufferTexture.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Texture` | `./Texture.js` |
| `NearestFilter` | `../constants.js` |


---

## Classes

### `FramebufferTexture`

<details><summary>Class Code</summary>

```ts
class FramebufferTexture extends Texture {

	/**
	 * Constructs a new framebuffer texture.
	 *
	 * @param {number} [width] - The width of the texture.
	 * @param {number} [height] - The height of the texture.
	 */
	constructor( width, height ) {

		super( { width, height } );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isFramebufferTexture = true;

		/**
		 * How the texture is sampled when a texel covers more than one pixel.
		 *
		 * Overwritten and set to `NearestFilter` by default to disable filtering.
		 *
		 * @type {(NearestFilter|NearestMipmapNearestFilter|NearestMipmapLinearFilter|LinearFilter|LinearMipmapNearestFilter|LinearMipmapLinearFilter)}
		 * @default NearestFilter
		 */
		this.magFilter = NearestFilter;

		/**
		 * How the texture is sampled when a texel covers less than one pixel.
		 *
		 * Overwritten and set to `NearestFilter` by default to disable filtering.
		 *
		 * @type {(NearestFilter|NearestMipmapNearestFilter|NearestMipmapLinearFilter|LinearFilter|LinearMipmapNearestFilter|LinearMipmapLinearFilter)}
		 * @default NearestFilter
		 */
		this.minFilter = NearestFilter;

		/**
		 * Whether to generate mipmaps (if possible) for a texture.
		 *
		 * Overwritten and set to `false` by default.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.generateMipmaps = false;

		this.needsUpdate = true;

	}

}
```
</details>


---