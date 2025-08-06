[⬅️ Back to Table of Contents](../../index.md)

# 📄 `AudioContext.js`

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
📂 **`src/audio/AudioContext.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_context` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `AudioContext.getContext(): AudioContext`

**JSDoc:**
```typescript
/**
	 * Returns the global native audio context.
	 *
	 * @return {AudioContext} The native audio context.
	 */
```

**Returns:** `AudioContext`

<details><summary>Code</summary>

```typescript
static getContext() {

		if ( _context === undefined ) {

			_context = new ( window.AudioContext || window.webkitAudioContext )();

		}

		return _context;

	}
```
</details>

### `AudioContext.setContext(value: AudioContext): void`

**JSDoc:**
```typescript
/**
	 * Allows to set the global native audio context from outside.
	 *
	 * @param {AudioContext} value - The native context to set.
	 */
```

**Parameters:**

- **`value`** `AudioContext`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
static setContext( value ) {

		_context = value;

	}
```
</details>


---

## Classes

### `AudioContext`

<details><summary>Class Code</summary>

```ts
class AudioContext {

	/**
	 * Returns the global native audio context.
	 *
	 * @return {AudioContext} The native audio context.
	 */
	static getContext() {

		if ( _context === undefined ) {

			_context = new ( window.AudioContext || window.webkitAudioContext )();

		}

		return _context;

	}

	/**
	 * Allows to set the global native audio context from outside.
	 *
	 * @param {AudioContext} value - The native context to set.
	 */
	static setContext( value ) {

		_context = value;

	}

}
```
</details>

#### Methods

##### `getContext(): AudioContext`

<details><summary>Code</summary>

```ts
static getContext() {

		if ( _context === undefined ) {

			_context = new ( window.AudioContext || window.webkitAudioContext )();

		}

		return _context;

	}
```
</details>

##### `setContext(value: AudioContext): void`

<details><summary>Code</summary>

```ts
static setContext( value ) {

		_context = value;

	}
```
</details>


---