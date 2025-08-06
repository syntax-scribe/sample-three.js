[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Resizer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Resizer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIElement` | `./libs/ui.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `offsetWidth` | `number` | let/var | `document.body.offsetWidth` | ✗ |
| `clientX` | `any` | let/var | `event.clientX` | ✗ |
| `cX` | `any` | let/var | `clientX < 0 ? 0 : clientX > offsetWidth ? offsetWidth : clientX` | ✗ |


---

## Functions

### `Resizer(editor: any): UIElement`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIElement`

**Calls:**

- `document.createElement`
- `dom.ownerDocument.addEventListener`
- `dom.ownerDocument.removeEventListener`
- `Math.max`
- `document.getElementById`
- `signals.windowResize.dispatch`
- `dom.addEventListener`

**Internal Comments:**
```
// PointerEvent's movementX/movementY are 0 in WebKit
```

<details><summary>Code</summary>

```typescript
function Resizer( editor ) {

	const signals = editor.signals;

	const dom = document.createElement( 'div' );
	dom.id = 'resizer';

	function onPointerDown( event ) {

		if ( event.isPrimary === false ) return;

		dom.ownerDocument.addEventListener( 'pointermove', onPointerMove );
		dom.ownerDocument.addEventListener( 'pointerup', onPointerUp );

	}

	function onPointerUp( event ) {

		if ( event.isPrimary === false ) return;

		dom.ownerDocument.removeEventListener( 'pointermove', onPointerMove );
		dom.ownerDocument.removeEventListener( 'pointerup', onPointerUp );

	}

	function onPointerMove( event ) {

		// PointerEvent's movementX/movementY are 0 in WebKit

		if ( event.isPrimary === false ) return;

		const offsetWidth = document.body.offsetWidth;
		const clientX = event.clientX;

		const cX = clientX < 0 ? 0 : clientX > offsetWidth ? offsetWidth : clientX;

		const x = Math.max( 335, offsetWidth - cX ); // .TabbedPanel min-width: 335px

		dom.style.right = x + 'px';

		document.getElementById( 'sidebar' ).style.width = x + 'px';
		document.getElementById( 'player' ).style.right = x + 'px';
		document.getElementById( 'script' ).style.right = x + 'px';
		document.getElementById( 'viewport' ).style.right = x + 'px';

		signals.windowResize.dispatch();

	}

	dom.addEventListener( 'pointerdown', onPointerDown );

	return new UIElement( dom );

}
```
</details>

### `onPointerDown(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `dom.ownerDocument.addEventListener`

<details><summary>Code</summary>

```typescript
function onPointerDown( event ) {

		if ( event.isPrimary === false ) return;

		dom.ownerDocument.addEventListener( 'pointermove', onPointerMove );
		dom.ownerDocument.addEventListener( 'pointerup', onPointerUp );

	}
```
</details>

### `onPointerUp(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `dom.ownerDocument.removeEventListener`

<details><summary>Code</summary>

```typescript
function onPointerUp( event ) {

		if ( event.isPrimary === false ) return;

		dom.ownerDocument.removeEventListener( 'pointermove', onPointerMove );
		dom.ownerDocument.removeEventListener( 'pointerup', onPointerUp );

	}
```
</details>

### `onPointerMove(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `Math.max`
- `document.getElementById`
- `signals.windowResize.dispatch`

**Internal Comments:**
```
// PointerEvent's movementX/movementY are 0 in WebKit
```

<details><summary>Code</summary>

```typescript
function onPointerMove( event ) {

		// PointerEvent's movementX/movementY are 0 in WebKit

		if ( event.isPrimary === false ) return;

		const offsetWidth = document.body.offsetWidth;
		const clientX = event.clientX;

		const cX = clientX < 0 ? 0 : clientX > offsetWidth ? offsetWidth : clientX;

		const x = Math.max( 335, offsetWidth - cX ); // .TabbedPanel min-width: 335px

		dom.style.right = x + 'px';

		document.getElementById( 'sidebar' ).style.width = x + 'px';
		document.getElementById( 'player' ).style.right = x + 'px';
		document.getElementById( 'script' ).style.right = x + 'px';
		document.getElementById( 'viewport' ).style.right = x + 'px';

		signals.windowResize.dispatch();

	}
```
</details>


---