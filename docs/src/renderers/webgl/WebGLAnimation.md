[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLAnimation.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLAnimation.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `context` | `any` | let/var | `null` | ✗ |
| `isAnimating` | `boolean` | let/var | `false` | ✗ |
| `animationLoop` | `any` | let/var | `null` | ✗ |
| `requestId` | `any` | let/var | `null` | ✗ |


---

## Functions

### `WebGLAnimation(): { start: () => void; stop: () => void; setAnimationLoop: (callback: any) => void; setContext: (value: any) => void; }`

**Returns:** `{ start: () => void; stop: () => void; setAnimationLoop: (callback: any) => void; setContext: (value: any) => void; }`

**Calls:**

- `animationLoop`
- `context.requestAnimationFrame`
- `context.cancelAnimationFrame`

<details><summary>Code</summary>

```typescript
function WebGLAnimation() {

	let context = null;
	let isAnimating = false;
	let animationLoop = null;
	let requestId = null;

	function onAnimationFrame( time, frame ) {

		animationLoop( time, frame );

		requestId = context.requestAnimationFrame( onAnimationFrame );

	}

	return {

		start: function () {

			if ( isAnimating === true ) return;
			if ( animationLoop === null ) return;

			requestId = context.requestAnimationFrame( onAnimationFrame );

			isAnimating = true;

		},

		stop: function () {

			context.cancelAnimationFrame( requestId );

			isAnimating = false;

		},

		setAnimationLoop: function ( callback ) {

			animationLoop = callback;

		},

		setContext: function ( value ) {

			context = value;

		}

	};

}
```
</details>

### `onAnimationFrame(time: any, frame: any): void`

**Parameters:**

- **`time`** `any`
- **`frame`** `any`

**Returns:** `void`

**Calls:**

- `animationLoop`
- `context.requestAnimationFrame`

<details><summary>Code</summary>

```typescript
function onAnimationFrame( time, frame ) {

		animationLoop( time, frame );

		requestId = context.requestAnimationFrame( onAnimationFrame );

	}
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `context.requestAnimationFrame`

<details><summary>Code</summary>

```typescript
function () {

			if ( isAnimating === true ) return;
			if ( animationLoop === null ) return;

			requestId = context.requestAnimationFrame( onAnimationFrame );

			isAnimating = true;

		}
```
</details>

### `stop(): void`

**Returns:** `void`

**Calls:**

- `context.cancelAnimationFrame`

<details><summary>Code</summary>

```typescript
function () {

			context.cancelAnimationFrame( requestId );

			isAnimating = false;

		}
```
</details>

### `setAnimationLoop(callback: any): void`

**Parameters:**

- **`callback`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( callback ) {

			animationLoop = callback;

		}
```
</details>

### `setContext(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( value ) {

			context = value;

		}
```
</details>

### `start(): void`

**Returns:** `void`

**Calls:**

- `context.requestAnimationFrame`

<details><summary>Code</summary>

```typescript
function () {

			if ( isAnimating === true ) return;
			if ( animationLoop === null ) return;

			requestId = context.requestAnimationFrame( onAnimationFrame );

			isAnimating = true;

		}
```
</details>

### `stop(): void`

**Returns:** `void`

**Calls:**

- `context.cancelAnimationFrame`

<details><summary>Code</summary>

```typescript
function () {

			context.cancelAnimationFrame( requestId );

			isAnimating = false;

		}
```
</details>

### `setAnimationLoop(callback: any): void`

**Parameters:**

- **`callback`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( callback ) {

			animationLoop = callback;

		}
```
</details>

### `setContext(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( value ) {

			context = value;

		}
```
</details>


---