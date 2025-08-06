[⬅️ Back to Table of Contents](../index.md)

# 📄 `utils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 11 |
| 📊 Variables & Constants | 7 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/utils.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `min` | `any` | let/var | `array[ 0 ]` | ✗ |
| `max` | `any` | let/var | `array[ 0 ]` | ✗ |
| `TYPED_ARRAYS` | `{ Int8Array: Int8ArrayConstructor; Ui...` | let/var | `{ Int8Array: Int8Array, Uint8Array: Uint8Array, Uint8ClampedArray: Uint8Clamp...` | ✗ |
| `_cache` | `{}` | let/var | `{}` | ✗ |
| `m` | `any` | let/var | `projectionMatrix.elements` | ✗ |
| `m` | `any` | let/var | `projectionMatrix.elements` | ✗ |
| `isPerspectiveMatrix` | `boolean` | let/var | `m[ 11 ] === - 1` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| promise-chain | `probeAsync` | *none* | new Promise(...) |


---

## Functions

### `arrayMin(array: any): any`

**Parameters:**

- **`array`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function arrayMin( array ) {

	if ( array.length === 0 ) return Infinity;

	let min = array[ 0 ];

	for ( let i = 1, l = array.length; i < l; ++ i ) {

		if ( array[ i ] < min ) min = array[ i ];

	}

	return min;

}
```
</details>

### `arrayMax(array: any): any`

**Parameters:**

- **`array`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function arrayMax( array ) {

	if ( array.length === 0 ) return - Infinity;

	let max = array[ 0 ];

	for ( let i = 1, l = array.length; i < l; ++ i ) {

		if ( array[ i ] > max ) max = array[ i ];

	}

	return max;

}
```
</details>

### `arrayNeedsUint32(array: any): boolean`

**Parameters:**

- **`array`** `any`

**Returns:** `boolean`

**Internal Comments:**
```
// assumes larger values usually on last
```

<details><summary>Code</summary>

```typescript
function arrayNeedsUint32( array ) {

	// assumes larger values usually on last

	for ( let i = array.length - 1; i >= 0; -- i ) {

		if ( array[ i ] >= 65535 ) return true; // account for PRIMITIVE_RESTART_FIXED_INDEX, #24565

	}

	return false;

}
```
</details>

### `getTypedArray(type: any, buffer: any): any`

**Parameters:**

- **`type`** `any`
- **`buffer`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getTypedArray( type, buffer ) {

	return new TYPED_ARRAYS[ type ]( buffer );

}
```
</details>

### `createElementNS(name: any): HTMLElement`

**Parameters:**

- **`name`** `any`

**Returns:** `HTMLElement`

**Calls:**

- `document.createElementNS`

<details><summary>Code</summary>

```typescript
function createElementNS( name ) {

	return document.createElementNS( 'http://www.w3.org/1999/xhtml', name );

}
```
</details>

### `createCanvasElement(): HTMLElement`

**Returns:** `HTMLElement`

**Calls:**

- `createElementNS`

<details><summary>Code</summary>

```typescript
function createCanvasElement() {

	const canvas = createElementNS( 'canvas' );
	canvas.style.display = 'block';
	return canvas;

}
```
</details>

### `warnOnce(message: any): void`

**Parameters:**

- **`message`** `any`

**Returns:** `void`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
function warnOnce( message ) {

	if ( message in _cache ) return;

	_cache[ message ] = true;

	console.warn( message );

}
```
</details>

### `probeAsync(gl: any, sync: any, interval: any): Promise<any>`

**Parameters:**

- **`gl`** `any`
- **`sync`** `any`
- **`interval`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `gl.clientWaitSync`
- `reject`
- `setTimeout`
- `resolve`

<details><summary>Code</summary>

```typescript
function probeAsync( gl, sync, interval ) {

	return new Promise( function ( resolve, reject ) {

		function probe() {

			switch ( gl.clientWaitSync( sync, gl.SYNC_FLUSH_COMMANDS_BIT, 0 ) ) {

				case gl.WAIT_FAILED:
					reject();
					break;

				case gl.TIMEOUT_EXPIRED:
					setTimeout( probe, interval );
					break;

				default:
					resolve();

			}

		}

		setTimeout( probe, interval );

	} );

}
```
</details>

### `probe(): void`

**Returns:** `void`

**Calls:**

- `gl.clientWaitSync`
- `reject`
- `setTimeout`
- `resolve`

<details><summary>Code</summary>

```typescript
function probe() {

			switch ( gl.clientWaitSync( sync, gl.SYNC_FLUSH_COMMANDS_BIT, 0 ) ) {

				case gl.WAIT_FAILED:
					reject();
					break;

				case gl.TIMEOUT_EXPIRED:
					setTimeout( probe, interval );
					break;

				default:
					resolve();

			}

		}
```
</details>

### `toNormalizedProjectionMatrix(projectionMatrix: any): void`

**Parameters:**

- **`projectionMatrix`** `any`

**Returns:** `void`

**Internal Comments:**
```
// Convert [-1, 1] to [0, 1] projection matrix (x4)
```

<details><summary>Code</summary>

```typescript
function toNormalizedProjectionMatrix( projectionMatrix ) {

	const m = projectionMatrix.elements;

	// Convert [-1, 1] to [0, 1] projection matrix
	m[ 2 ] = 0.5 * m[ 2 ] + 0.5 * m[ 3 ];
	m[ 6 ] = 0.5 * m[ 6 ] + 0.5 * m[ 7 ];
	m[ 10 ] = 0.5 * m[ 10 ] + 0.5 * m[ 11 ];
	m[ 14 ] = 0.5 * m[ 14 ] + 0.5 * m[ 15 ];

}
```
</details>

### `toReversedProjectionMatrix(projectionMatrix: any): void`

**Parameters:**

- **`projectionMatrix`** `any`

**Returns:** `void`

**Internal Comments:**
```
// Reverse [0, 1] projection matrix
```

<details><summary>Code</summary>

```typescript
function toReversedProjectionMatrix( projectionMatrix ) {

	const m = projectionMatrix.elements;
	const isPerspectiveMatrix = m[ 11 ] === - 1;

	// Reverse [0, 1] projection matrix
	if ( isPerspectiveMatrix ) {

		m[ 10 ] = - m[ 10 ] - 1;
		m[ 14 ] = - m[ 14 ];

	} else {

		m[ 10 ] = - m[ 10 ];
		m[ 14 ] = - m[ 14 ] + 1;

	}

}
```
</details>


---