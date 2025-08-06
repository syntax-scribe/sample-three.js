[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LUTPass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/LUTPass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ShaderPass` | `./ShaderPass.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `LUTShader` | `{ name: string; uniforms: { lut: { va...` | let/var | `{ name: 'LUTShader', uniforms: { lut: { value: null }, lutSize: { value: 0 },...` | ✗ |
| `material` | `ShaderMaterial` | let/var | `this.material` | ✗ |


---

## Classes

### `LUTPass`

<details><summary>Class Code</summary>

```ts
class LUTPass extends ShaderPass {

	/**
	 * Constructs a LUT pass.
	 *
	 * @param {{lut:Data3DTexture,intensity:number}} [options={}] - The pass options.
	 */
	constructor( options = {} ) {

		super( LUTShader );

		/**
		 * The LUT as a 3D texture.
		 *
		 * @type {?Data3DTexture}
		 * @default null
		 */
		this.lut = options.lut || null;

		/**
		 * The intensity.
		 *
		 * @type {?number}
		 * @default 1
		 */
		this.intensity = 'intensity' in options ? options.intensity : 1;

	}

	set lut( v ) {

		const material = this.material;

		if ( v !== this.lut ) {

			material.uniforms.lut.value = null;

			if ( v ) {

				material.uniforms.lutSize.value = v.image.width;
				material.uniforms.lut.value = v;

			}

		}

	}

	get lut() {

		return this.material.uniforms.lut.value;

	}

	set intensity( v ) {

		this.material.uniforms.intensity.value = v;

	}

	get intensity() {

		return this.material.uniforms.intensity.value;

	}

}
```
</details>


---