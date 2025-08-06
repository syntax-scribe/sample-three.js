[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGL.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/capabilities/WebGL.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `ctx` | `WebGL2RenderingContext` | let/var | `window.WebGL2RenderingContext && canvas.getContext( 'webgl2' )` | ✗ |
| `names` | `{ 1: string; 2: string; }` | let/var | `{ 1: 'WebGL', 2: 'WebGL 2' }` | ✗ |
| `contexts` | `{ 1: { new (): WebGLRenderingContext;...` | let/var | `{ 1: window.WebGLRenderingContext, 2: window.WebGL2RenderingContext }` | ✗ |
| `message` | `string` | let/var | `'Your $0 does not seem to support <a href="http://khronos.org/webgl/wiki/Gett...` | ✗ |


---

## Functions

### `WebGL.isWebGL2Available(): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if WebGL 2 is available.
	 *
	 * @return {boolean} Whether WebGL 2 is available or not.
	 */
```

**Returns:** `boolean`

**Calls:**

- `document.createElement`
- `canvas.getContext`

<details><summary>Code</summary>

```typescript
static isWebGL2Available() {

		try {

			const canvas = document.createElement( 'canvas' );
			return !! ( window.WebGL2RenderingContext && canvas.getContext( 'webgl2' ) );

		} catch ( e ) {

			return false;

		}

	}
```
</details>

### `WebGL.isColorSpaceAvailable(colorSpace: string): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given color space is available. This method can only be used
	 * if WebGL 2 is supported.
	 *
	 * @param {string} colorSpace - The color space to test.
	 * @return {boolean} Whether the given color space is available or not.
	 */
```

**Parameters:**

- **`colorSpace`** `string`

**Returns:** `boolean`

**Calls:**

- `document.createElement`
- `canvas.getContext`

<details><summary>Code</summary>

```typescript
static isColorSpaceAvailable( colorSpace ) {

		try {

			const canvas = document.createElement( 'canvas' );
			const ctx = window.WebGL2RenderingContext && canvas.getContext( 'webgl2' );
			ctx.drawingBufferColorSpace = colorSpace;
			return ctx.drawingBufferColorSpace === colorSpace; // deepscan-disable-line SAME_OPERAND_VALUE

		} catch ( e ) {

			return false;

		}

	}
```
</details>

### `WebGL.getWebGL2ErrorMessage(): HTMLDivElement`

**JSDoc:**
```typescript
/**
	 * Returns a `div` element representing a formatted error message that can be appended in
	 * web sites if WebGL 2 isn't supported.
	 *
	 * @return {HTMLDivElement} A `div` element representing a formatted error message that WebGL 2 isn't supported.
	 */
```

**Returns:** `HTMLDivElement`

**Calls:**

- `this._getErrorMessage`

<details><summary>Code</summary>

```typescript
static getWebGL2ErrorMessage() {

		return this._getErrorMessage( 2 );

	}
```
</details>

### `WebGL._getErrorMessage(version: any): HTMLDivElement`

**Parameters:**

- **`version`** `any`

**Returns:** `HTMLDivElement`

**Calls:**

- `document.createElement`
- `message.replace`

<details><summary>Code</summary>

```typescript
static _getErrorMessage( version ) {

		const names = {
			1: 'WebGL',
			2: 'WebGL 2'
		};

		const contexts = {
			1: window.WebGLRenderingContext,
			2: window.WebGL2RenderingContext
		};

		let message = 'Your $0 does not seem to support <a href="http://khronos.org/webgl/wiki/Getting_a_WebGL_Implementation" style="color:#000">$1</a>';

		const element = document.createElement( 'div' );
		element.id = 'webglmessage';
		element.style.fontFamily = 'monospace';
		element.style.fontSize = '13px';
		element.style.fontWeight = 'normal';
		element.style.textAlign = 'center';
		element.style.background = '#fff';
		element.style.color = '#000';
		element.style.padding = '1.5em';
		element.style.width = '400px';
		element.style.margin = '5em auto 0';

		if ( contexts[ version ] ) {

			message = message.replace( '$0', 'graphics card' );

		} else {

			message = message.replace( '$0', 'browser' );

		}

		message = message.replace( '$1', names[ version ] );

		element.innerHTML = message;

		return element;

	}
```
</details>


---

## Classes

### `WebGL`

<details><summary>Class Code</summary>

```ts
class WebGL {

	/**
	 * Returns `true` if WebGL 2 is available.
	 *
	 * @return {boolean} Whether WebGL 2 is available or not.
	 */
	static isWebGL2Available() {

		try {

			const canvas = document.createElement( 'canvas' );
			return !! ( window.WebGL2RenderingContext && canvas.getContext( 'webgl2' ) );

		} catch ( e ) {

			return false;

		}

	}

	/**
	 * Returns `true` if the given color space is available. This method can only be used
	 * if WebGL 2 is supported.
	 *
	 * @param {string} colorSpace - The color space to test.
	 * @return {boolean} Whether the given color space is available or not.
	 */
	static isColorSpaceAvailable( colorSpace ) {

		try {

			const canvas = document.createElement( 'canvas' );
			const ctx = window.WebGL2RenderingContext && canvas.getContext( 'webgl2' );
			ctx.drawingBufferColorSpace = colorSpace;
			return ctx.drawingBufferColorSpace === colorSpace; // deepscan-disable-line SAME_OPERAND_VALUE

		} catch ( e ) {

			return false;

		}

	}

	/**
	 * Returns a `div` element representing a formatted error message that can be appended in
	 * web sites if WebGL 2 isn't supported.
	 *
	 * @return {HTMLDivElement} A `div` element representing a formatted error message that WebGL 2 isn't supported.
	 */
	static getWebGL2ErrorMessage() {

		return this._getErrorMessage( 2 );

	}

	// private

	static _getErrorMessage( version ) {

		const names = {
			1: 'WebGL',
			2: 'WebGL 2'
		};

		const contexts = {
			1: window.WebGLRenderingContext,
			2: window.WebGL2RenderingContext
		};

		let message = 'Your $0 does not seem to support <a href="http://khronos.org/webgl/wiki/Getting_a_WebGL_Implementation" style="color:#000">$1</a>';

		const element = document.createElement( 'div' );
		element.id = 'webglmessage';
		element.style.fontFamily = 'monospace';
		element.style.fontSize = '13px';
		element.style.fontWeight = 'normal';
		element.style.textAlign = 'center';
		element.style.background = '#fff';
		element.style.color = '#000';
		element.style.padding = '1.5em';
		element.style.width = '400px';
		element.style.margin = '5em auto 0';

		if ( contexts[ version ] ) {

			message = message.replace( '$0', 'graphics card' );

		} else {

			message = message.replace( '$0', 'browser' );

		}

		message = message.replace( '$1', names[ version ] );

		element.innerHTML = message;

		return element;

	}

}
```
</details>

#### Methods

##### `isWebGL2Available(): boolean`

<details><summary>Code</summary>

```ts
static isWebGL2Available() {

		try {

			const canvas = document.createElement( 'canvas' );
			return !! ( window.WebGL2RenderingContext && canvas.getContext( 'webgl2' ) );

		} catch ( e ) {

			return false;

		}

	}
```
</details>

##### `isColorSpaceAvailable(colorSpace: string): boolean`

<details><summary>Code</summary>

```ts
static isColorSpaceAvailable( colorSpace ) {

		try {

			const canvas = document.createElement( 'canvas' );
			const ctx = window.WebGL2RenderingContext && canvas.getContext( 'webgl2' );
			ctx.drawingBufferColorSpace = colorSpace;
			return ctx.drawingBufferColorSpace === colorSpace; // deepscan-disable-line SAME_OPERAND_VALUE

		} catch ( e ) {

			return false;

		}

	}
```
</details>

##### `getWebGL2ErrorMessage(): HTMLDivElement`

<details><summary>Code</summary>

```ts
static getWebGL2ErrorMessage() {

		return this._getErrorMessage( 2 );

	}
```
</details>

##### `_getErrorMessage(version: any): HTMLDivElement`

<details><summary>Code</summary>

```ts
static _getErrorMessage( version ) {

		const names = {
			1: 'WebGL',
			2: 'WebGL 2'
		};

		const contexts = {
			1: window.WebGLRenderingContext,
			2: window.WebGL2RenderingContext
		};

		let message = 'Your $0 does not seem to support <a href="http://khronos.org/webgl/wiki/Getting_a_WebGL_Implementation" style="color:#000">$1</a>';

		const element = document.createElement( 'div' );
		element.id = 'webglmessage';
		element.style.fontFamily = 'monospace';
		element.style.fontSize = '13px';
		element.style.fontWeight = 'normal';
		element.style.textAlign = 'center';
		element.style.background = '#fff';
		element.style.color = '#000';
		element.style.padding = '1.5em';
		element.style.width = '400px';
		element.style.margin = '5em auto 0';

		if ( contexts[ version ] ) {

			message = message.replace( '$0', 'graphics card' );

		} else {

			message = message.replace( '$0', 'browser' );

		}

		message = message.replace( '$1', names[ version ] );

		element.innerHTML = message;

		return element;

	}
```
</details>


---