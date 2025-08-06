[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SampledTexture.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 4 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/SampledTexture.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Sampler` | `./Sampler.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_id` | `number` | let/var | `0` | ✗ |


---

## Classes

### `SampledTexture`

<details><summary>Class Code</summary>

```ts
class SampledTexture extends Sampler {

	/**
	 * Constructs a new sampled texture.
	 *
	 * @param {string} name - The sampled texture's name.
	 * @param {?Texture} texture - The texture this binding is referring to.
	 */
	constructor( name, texture ) {

		super( name, texture );

		/**
		 * This identifier.
		 *
		 * @type {number}
		 */
		this.id = _id ++;

		/**
		 * Whether the texture is a storage texture or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.store = false;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSampledTexture = true;

	}

}
```
</details>

### `SampledArrayTexture`

<details><summary>Class Code</summary>

```ts
class SampledArrayTexture extends SampledTexture {

	/**
	 * Constructs a new sampled array texture.
	 *
	 * @param {string} name - The sampled array texture's name.
	 * @param {?(DataArrayTexture|CompressedArrayTexture)} texture - The texture this binding is referring to.
	 */
	constructor( name, texture ) {

		super( name, texture );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSampledArrayTexture = true;

	}

}
```
</details>

### `Sampled3DTexture`

<details><summary>Class Code</summary>

```ts
class Sampled3DTexture extends SampledTexture {

	/**
	 * Constructs a new sampled 3D texture.
	 *
	 * @param {string} name - The sampled 3D texture's name.
	 * @param {?Data3DTexture} texture - The texture this binding is referring to.
	 */
	constructor( name, texture ) {

		super( name, texture );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSampled3DTexture = true;

	}

}
```
</details>

### `SampledCubeTexture`

<details><summary>Class Code</summary>

```ts
class SampledCubeTexture extends SampledTexture {

	/**
	 * Constructs a new sampled cube texture.
	 *
	 * @param {string} name - The sampled cube texture's name.
	 * @param {?(CubeTexture|CompressedCubeTexture)} texture - The texture this binding is referring to.
	 */
	constructor( name, texture ) {

		super( name, texture );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSampledCubeTexture = true;

	}

}
```
</details>


---