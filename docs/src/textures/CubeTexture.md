[⬅️ Back to Table of Contents](../../index.md)

# 📄 `CubeTexture.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/textures/CubeTexture.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Texture` | `./Texture.js` |
| `CubeReflectionMapping` | `../constants.js` |


---

## Classes

### `CubeTexture`

<details><summary>Class Code</summary>

```ts
class CubeTexture extends Texture {

	/**
	 * Constructs a new cube texture.
	 *
	 * @param {Array<Image>} [images=[]] - An array holding a image for each side of a cube.
	 * @param {number} [mapping=CubeReflectionMapping] - The texture mapping.
	 * @param {number} [wrapS=ClampToEdgeWrapping] - The wrapS value.
	 * @param {number} [wrapT=ClampToEdgeWrapping] - The wrapT value.
	 * @param {number} [magFilter=LinearFilter] - The mag filter value.
	 * @param {number} [minFilter=LinearMipmapLinearFilter] - The min filter value.
	 * @param {number} [format=RGBAFormat] - The texture format.
	 * @param {number} [type=UnsignedByteType] - The texture type.
	 * @param {number} [anisotropy=Texture.DEFAULT_ANISOTROPY] - The anisotropy value.
	 * @param {string} [colorSpace=NoColorSpace] - The color space value.
	 */
	constructor( images = [], mapping = CubeReflectionMapping, wrapS, wrapT, magFilter, minFilter, format, type, anisotropy, colorSpace ) {

		super( images, mapping, wrapS, wrapT, magFilter, minFilter, format, type, anisotropy, colorSpace );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isCubeTexture = true;

		/**
		 * If set to `true`, the texture is flipped along the vertical axis when
		 * uploaded to the GPU.
		 *
		 * Overwritten and set to `false` by default.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.flipY = false;

	}

	/**
	 * Alias for {@link CubeTexture#image}.
	 *
	 * @type {Array<Image>}
	 */
	get images() {

		return this.image;

	}

	set images( value ) {

		this.image = value;

	}

}
```
</details>


---