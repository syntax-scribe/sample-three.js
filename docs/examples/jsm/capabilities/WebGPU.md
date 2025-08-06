[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGPU.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/capabilities/WebGPU.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `isAvailable` | `boolean` | let/var | `( typeof navigator !== 'undefined' && navigator.gpu !== undefined )` | ✗ |
| `message` | `"Your browser does not support <a hre...` | let/var | `'Your browser does not support <a href="https://gpuweb.github.io/gpuweb/" sty...` | ✗ |


---

## Functions

### `WebGPU.isAvailable(): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if WebGPU is available.
	 *
	 * @return {boolean} Whether WebGPU is available or not.
	 */
```

**Returns:** `boolean`

**Calls:**

- `Boolean`

<details><summary>Code</summary>

```typescript
static isAvailable() {

		return Boolean( isAvailable );

	}
```
</details>

### `WebGPU.getErrorMessage(): HTMLDivElement`

**JSDoc:**
```typescript
/**
	 * Returns a `div` element representing a formatted error message that can be appended in
	 * web sites if WebGPU isn't supported.
	 *
	 * @return {HTMLDivElement} A `div` element representing a formatted error message that WebGPU isn't supported.
	 */
```

**Returns:** `HTMLDivElement`

**Calls:**

- `document.createElement`

<details><summary>Code</summary>

```typescript
static getErrorMessage() {

		const message = 'Your browser does not support <a href="https://gpuweb.github.io/gpuweb/" style="color:blue">WebGPU</a> yet';

		const element = document.createElement( 'div' );
		element.id = 'webgpumessage';
		element.style.fontFamily = 'monospace';
		element.style.fontSize = '13px';
		element.style.fontWeight = 'normal';
		element.style.textAlign = 'center';
		element.style.background = '#fff';
		element.style.color = '#000';
		element.style.padding = '1.5em';
		element.style.maxWidth = '400px';
		element.style.margin = '5em auto 0';

		element.innerHTML = message;

		return element;

	}
```
</details>


---

## Classes

### `WebGPU`

<details><summary>Class Code</summary>

```ts
class WebGPU {

	/**
	 * Returns `true` if WebGPU is available.
	 *
	 * @return {boolean} Whether WebGPU is available or not.
	 */
	static isAvailable() {

		return Boolean( isAvailable );

	}

	/**
	 * Returns a `div` element representing a formatted error message that can be appended in
	 * web sites if WebGPU isn't supported.
	 *
	 * @return {HTMLDivElement} A `div` element representing a formatted error message that WebGPU isn't supported.
	 */
	static getErrorMessage() {

		const message = 'Your browser does not support <a href="https://gpuweb.github.io/gpuweb/" style="color:blue">WebGPU</a> yet';

		const element = document.createElement( 'div' );
		element.id = 'webgpumessage';
		element.style.fontFamily = 'monospace';
		element.style.fontSize = '13px';
		element.style.fontWeight = 'normal';
		element.style.textAlign = 'center';
		element.style.background = '#fff';
		element.style.color = '#000';
		element.style.padding = '1.5em';
		element.style.maxWidth = '400px';
		element.style.margin = '5em auto 0';

		element.innerHTML = message;

		return element;

	}

}
```
</details>

#### Methods

##### `isAvailable(): boolean`

<details><summary>Code</summary>

```ts
static isAvailable() {

		return Boolean( isAvailable );

	}
```
</details>

##### `getErrorMessage(): HTMLDivElement`

<details><summary>Code</summary>

```ts
static getErrorMessage() {

		const message = 'Your browser does not support <a href="https://gpuweb.github.io/gpuweb/" style="color:blue">WebGPU</a> yet';

		const element = document.createElement( 'div' );
		element.id = 'webgpumessage';
		element.style.fontFamily = 'monospace';
		element.style.fontSize = '13px';
		element.style.fontWeight = 'normal';
		element.style.textAlign = 'center';
		element.style.background = '#fff';
		element.style.color = '#000';
		element.style.padding = '1.5em';
		element.style.maxWidth = '400px';
		element.style.margin = '5em auto 0';

		element.innerHTML = message;

		return element;

	}
```
</details>


---