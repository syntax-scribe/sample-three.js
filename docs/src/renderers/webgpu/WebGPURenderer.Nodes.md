[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGPURenderer.Nodes.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgpu/WebGPURenderer.Nodes.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Renderer` | `../common/Renderer.js` |
| `WebGLBackend` | `../webgl-fallback/WebGLBackend.js` |
| `WebGPUBackend` | `./WebGPUBackend.js` |
| `BasicNodeLibrary` | `./nodes/BasicNodeLibrary.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `BackendClass` | `any` | let/var | `*not shown*` | ✗ |
| `backend` | `WebGLBackend \| WebGPUBackend` | let/var | `new BackendClass( parameters )` | ✗ |


---

## Classes

### `WebGPURenderer`

<details><summary>Class Code</summary>

```ts
class WebGPURenderer extends Renderer {

	/**
	 * Constructs a new WebGPU renderer.
	 *
	 * @param {WebGPURenderer~Options} [parameters] - The configuration parameter.
	 */
	constructor( parameters = {} ) {

		let BackendClass;

		if ( parameters.forceWebGL ) {

			BackendClass = WebGLBackend;

		} else {

			BackendClass = WebGPUBackend;

			parameters.getFallback = () => {

				console.warn( 'THREE.WebGPURenderer: WebGPU is not available, running under WebGL2 backend.' );

				return new WebGLBackend( parameters );

			};

		}

		const backend = new BackendClass( parameters );

		super( backend, parameters );

		/**
		 * The generic default value is overwritten with the
		 * standard node library for type mapping. Material
		 * mapping is not supported with this version.
		 *
		 * @type {BasicNodeLibrary}
		 */
		this.library = new BasicNodeLibrary();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isWebGPURenderer = true;

	}

}
```
</details>


---