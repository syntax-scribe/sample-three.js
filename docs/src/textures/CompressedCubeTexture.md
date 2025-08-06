[⬅️ Back to Table of Contents](../../index.md)

# 📄 `CompressedCubeTexture.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/textures/CompressedCubeTexture.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `CubeReflectionMapping` | `../constants.js` |
| `CompressedTexture` | `./CompressedTexture.js` |


---

## Classes

### `CompressedCubeTexture`

<details><summary>Class Code</summary>

```ts
class CompressedCubeTexture extends CompressedTexture {

	/**
	 * Constructs a new compressed texture.
	 *
	 * @param {Array<CompressedTexture>} images - An array of compressed textures.
	 * @param {number} [format=RGBAFormat] - The texture format.
	 * @param {number} [type=UnsignedByteType] - The texture type.
	 */
	constructor( images, format, type ) {

		super( undefined, images[ 0 ].width, images[ 0 ].height, format, type, CubeReflectionMapping );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isCompressedCubeTexture = true;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isCubeTexture = true;

		this.image = images;

	}

}
```
</details>


---