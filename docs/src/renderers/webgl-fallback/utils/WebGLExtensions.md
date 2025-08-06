[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `WebGLExtensions.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgl-fallback/utils/WebGLExtensions.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `extension` | `any` | let/var | `this.extensions[ name ]` | ✗ |


---

## Functions

### `WebGLExtensions.get(name: string): any`

**JSDoc:**
```typescript
/**
	 * Returns the extension object for the given extension name.
	 *
	 * @param {string} name - The extension name.
	 * @return {Object} The extension object.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `any`

**Calls:**

- `this.gl.getExtension`

<details><summary>Code</summary>

```typescript
get( name ) {

		let extension = this.extensions[ name ];

		if ( extension === undefined ) {

			extension = this.gl.getExtension( name );

			this.extensions[ name ] = extension;

		}

		return extension;

	}
```
</details>

### `WebGLExtensions.has(name: string): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the requested extension is available.
	 *
	 * @param {string} name - The extension name.
	 * @return {boolean} Whether the given extension is available or not.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `boolean`

**Calls:**

- `this.availableExtensions.includes`

<details><summary>Code</summary>

```typescript
has( name ) {

		return this.availableExtensions.includes( name );

	}
```
</details>


---

## Classes

### `WebGLExtensions`

<details><summary>Class Code</summary>

```ts
class WebGLExtensions {

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
		 * A reference to the rendering context.
		 *
		 * @type {WebGL2RenderingContext}
		 */
		this.gl = this.backend.gl;

		/**
		 * A list with all the supported WebGL extensions.
		 *
		 * @type {Array<string>}
		 */
		this.availableExtensions = this.gl.getSupportedExtensions();

		/**
		 * A dictionary with requested WebGL extensions.
		 * The key is the name of the extension, the value
		 * the requested extension object.
		 *
		 * @type {Object<string,Object>}
		 */
		this.extensions = {};

	}

	/**
	 * Returns the extension object for the given extension name.
	 *
	 * @param {string} name - The extension name.
	 * @return {Object} The extension object.
	 */
	get( name ) {

		let extension = this.extensions[ name ];

		if ( extension === undefined ) {

			extension = this.gl.getExtension( name );

			this.extensions[ name ] = extension;

		}

		return extension;

	}

	/**
	 * Returns `true` if the requested extension is available.
	 *
	 * @param {string} name - The extension name.
	 * @return {boolean} Whether the given extension is available or not.
	 */
	has( name ) {

		return this.availableExtensions.includes( name );

	}

}
```
</details>

#### Methods

##### `get(name: string): any`

<details><summary>Code</summary>

```ts
get( name ) {

		let extension = this.extensions[ name ];

		if ( extension === undefined ) {

			extension = this.gl.getExtension( name );

			this.extensions[ name ] = extension;

		}

		return extension;

	}
```
</details>

##### `has(name: string): boolean`

<details><summary>Code</summary>

```ts
has( name ) {

		return this.availableExtensions.includes( name );

	}
```
</details>


---