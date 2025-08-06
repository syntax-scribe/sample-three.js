[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `WebGLCapabilities.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgl-fallback/utils/WebGLCapabilities.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `gl` | `any` | let/var | `this.backend.gl` | ✗ |
| `extensions` | `any` | let/var | `this.backend.extensions` | ✗ |


---

## Functions

### `WebGLCapabilities.getMaxAnisotropy(): number`

**JSDoc:**
```typescript
/**
	 * Returns the maximum anisotropy texture filtering value. This value
	 * depends on the device and is reported by the `EXT_texture_filter_anisotropic`
	 * WebGL extension.
	 *
	 * @return {number} The maximum anisotropy texture filtering value.
	 */
```

**Returns:** `number`

**Calls:**

- `extensions.has`
- `extensions.get`
- `gl.getParameter`

<details><summary>Code</summary>

```typescript
getMaxAnisotropy() {

		if ( this.maxAnisotropy !== null ) return this.maxAnisotropy;

		const gl = this.backend.gl;
		const extensions = this.backend.extensions;

		if ( extensions.has( 'EXT_texture_filter_anisotropic' ) === true ) {

			const extension = extensions.get( 'EXT_texture_filter_anisotropic' );

			this.maxAnisotropy = gl.getParameter( extension.MAX_TEXTURE_MAX_ANISOTROPY_EXT );

		} else {

			this.maxAnisotropy = 0;

		}

		return this.maxAnisotropy;

	}
```
</details>


---

## Classes

### `WebGLCapabilities`

<details><summary>Class Code</summary>

```ts
class WebGLCapabilities {

	/**
	 * Constructs a new utility object.
	 *
	 * @param {WebGLBackend} backend - The WebGL 2 backend.
	 */
	constructor( backend ) {

		/**
		 * A reference to the WebGL 2 backend.
		 *
		 * @type {WebGLBackend}
		 */
		this.backend = backend;

		/**
		 * This value holds the cached max anisotropy value.
		 *
		 * @type {?number}
		 * @default null
		 */
		this.maxAnisotropy = null;

	}

	/**
	 * Returns the maximum anisotropy texture filtering value. This value
	 * depends on the device and is reported by the `EXT_texture_filter_anisotropic`
	 * WebGL extension.
	 *
	 * @return {number} The maximum anisotropy texture filtering value.
	 */
	getMaxAnisotropy() {

		if ( this.maxAnisotropy !== null ) return this.maxAnisotropy;

		const gl = this.backend.gl;
		const extensions = this.backend.extensions;

		if ( extensions.has( 'EXT_texture_filter_anisotropic' ) === true ) {

			const extension = extensions.get( 'EXT_texture_filter_anisotropic' );

			this.maxAnisotropy = gl.getParameter( extension.MAX_TEXTURE_MAX_ANISOTROPY_EXT );

		} else {

			this.maxAnisotropy = 0;

		}

		return this.maxAnisotropy;

	}

}
```
</details>

#### Methods

##### `getMaxAnisotropy(): number`

<details><summary>Code</summary>

```ts
getMaxAnisotropy() {

		if ( this.maxAnisotropy !== null ) return this.maxAnisotropy;

		const gl = this.backend.gl;
		const extensions = this.backend.extensions;

		if ( extensions.has( 'EXT_texture_filter_anisotropic' ) === true ) {

			const extension = extensions.get( 'EXT_texture_filter_anisotropic' );

			this.maxAnisotropy = gl.getParameter( extension.MAX_TEXTURE_MAX_ANISOTROPY_EXT );

		} else {

			this.maxAnisotropy = 0;

		}

		return this.maxAnisotropy;

	}
```
</details>


---