[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `jank.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/offscreen/jank.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `interval` | `any` | let/var | `null` | ✗ |
| `result` | `any` | let/var | `null` | ✗ |
| `number` | `number` | let/var | `0` | ✗ |


---

## Functions

### `initJank(): void`

**Returns:** `void`

**Calls:**

- `document.getElementById`
- `button.addEventListener`
- `setInterval`
- `clearInterval`

<details><summary>Code</summary>

```typescript
function initJank() {

	const button = document.getElementById( 'button' );
	button.addEventListener( 'click', function () {

		if ( interval === null ) {

			interval = setInterval( jank, 1000 / 60 );

			button.textContent = 'STOP JANK';

		} else {

			clearInterval( interval );
			interval = null;

			button.textContent = 'START JANK';
			result.textContent = '';

		}

	} );

	result = document.getElementById( 'result' );

}
```
</details>

### `jank(): void`

**Returns:** `void`

**Calls:**

- `Math.random`

<details><summary>Code</summary>

```typescript
function jank() {

	let number = 0;

	for ( let i = 0; i < 10000000; i ++ ) {

		number += Math.random();

	}

	result.textContent = number;

}
```
</details>


---