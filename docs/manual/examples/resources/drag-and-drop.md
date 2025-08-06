[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `drag-and-drop.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/examples/resources/drag-and-drop.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `handlers` | `{ onDropFile: () => void; }` | let/var | `{ onDropFile: () => {}, }` | ✗ |
| `html` | `string` | let/var | `` <style> .dragInfo { position: fixed; left: 0; top: 0; width: 100%; height: ...` | ✗ |
| `dragElem` | `Element` | let/var | `dragInfo` | ✗ |
| `fileNdx` | `number` | let/var | `0` | ✗ |
| `item` | `any` | let/var | `e.dataTransfer.items[ i ]` | ✗ |


---

## Functions

### `onDropFile(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {}
```
</details>

### `onDropFile(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {}
```
</details>

### `onDropFile(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {}
```
</details>

### `onDropFile(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {}
```
</details>

### `onDropFile(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {}
```
</details>

### `onDropFile(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
() => {}
```
</details>

### `setup(options: any): void`

**Parameters:**

- **`options`** `any`

**Returns:** `void`

**Calls:**

- `document.createElement`
- `document.body.appendChild`
- `document.querySelector`
- `document.body.addEventListener`
- `showDragInfo`
- `dragElem.addEventListener`
- `e.preventDefault`
- `handlers.onDropFile`
- `item.getAsFile`

<details><summary>Code</summary>

```typescript
export function setup( options ) {

	const html = `
  <style>
    .dragInfo {
        position: fixed;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, .9);
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .dragInfo>div {
        padding: 1em;
        background: blue;
        color: white;
        pointer-events: none;
    }
    .dragerror div {
        background: red !important;
        font-weight: bold;
        color: white;
    }
  </style>
  <div class="dragInfo" style="display: none;">
    <div>
       ${options.msg}
    </div>
  </div>
  `;

	const elem = document.createElement( 'div' );
	elem.innerHTML = html;
	document.body.appendChild( elem );

	const dragInfo = document.querySelector( '.dragInfo' );
	function showDragInfo( show ) {

		dragInfo.style.display = show ? '' : 'none';

	}

	document.body.addEventListener( 'dragenter', () => {

		showDragInfo( true );

	} );

	const dragElem = dragInfo;

	dragElem.addEventListener( 'dragover', ( e ) => {

		e.preventDefault();
		return false;

	} );

	dragElem.addEventListener( 'dragleave', () => {

		showDragInfo( false );
		return false;

	} );

	dragElem.addEventListener( 'dragend', () => {

		showDragInfo( false );
		return false;

	} );

	dragElem.addEventListener( 'drop', ( e ) => {

		e.preventDefault();
		showDragInfo( false );
		if ( e.dataTransfer.items ) {

			let fileNdx = 0;
			for ( let i = 0; i < e.dataTransfer.items.length; ++ i ) {

				const item = e.dataTransfer.items[ i ];
				if ( item.kind === 'file' ) {

					handlers.onDropFile( item.getAsFile(), fileNdx ++ );

				}

			}

		}

		return false;

	} );

}
```
</details>

### `showDragInfo(show: any): void`

**Parameters:**

- **`show`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function showDragInfo( show ) {

		dragInfo.style.display = show ? '' : 'none';

	}
```
</details>

### `onDropFile(fn: any): void`

**Parameters:**

- **`fn`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
export function onDropFile( fn ) {

	handlers.onDropFile = fn;

}
```
</details>


---