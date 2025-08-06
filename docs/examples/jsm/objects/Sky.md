[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Sky.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/objects/Sky.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BackSide` | `three` |
| `BoxGeometry` | `three` |
| `Mesh` | `three` |
| `ShaderMaterial` | `three` |
| `UniformsUtils` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `shader` | `{ name: string; uniforms: { turbidity...` | let/var | `Sky.SkyShader` | ✗ |
| `material` | `any` | let/var | `new ShaderMaterial( { name: shader.name, uniforms: UniformsUtils.clone( shade...` | ✗ |


---

## Classes

### `Sky`

<details><summary>Class Code</summary>

```ts
class Sky extends Mesh {

	/**
	 * Constructs a new skydome.
	 */
	constructor() {

		const shader = Sky.SkyShader;

		const material = new ShaderMaterial( {
			name: shader.name,
			uniforms: UniformsUtils.clone( shader.uniforms ),
			vertexShader: shader.vertexShader,
			fragmentShader: shader.fragmentShader,
			side: BackSide,
			depthWrite: false
		} );

		super( new BoxGeometry( 1, 1, 1 ), material );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSky = true;

	}

}
```
</details>


---