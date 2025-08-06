[⬅️ Back to Table of Contents](../../../../../index.md)

# 📄 `page.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📊 Variables & Constants | 4 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`utils/docs/template/static/scripts/page.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `element` | `HTMLPreElement` | let/var | `elements[ i ]` | ✗ |
| `codeContent` | `any` | let/var | `element.textContent` | ✗ |
| `pagename` | `string` | let/var | `filename.split( '.' )[ 0 ]` | ✗ |
| `aElement` | `ChildNode` | let/var | `liElement.firstChild` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| promise-chain | `addCopyButton` | *none* | navigator.clipboard.writeText( codeContent ).then |


---

## Functions

### `addCopyButton(element: any): void`

**Parameters:**

- **`element`** `any`

**Returns:** `void`

**Calls:**

- `document.createElement`
- `element.appendChild`
- `copyButton.addEventListener`
- `navigator.clipboard.writeText( codeContent ).then`
- `copyButton.classList.add`
- `setTimeout`
- `copyButton.classList.remove`

<details><summary>Code</summary>

```typescript
function addCopyButton( element ) {

	const copyButton = document.createElement( 'button' );
	copyButton.className = 'copy-btn';

	element.appendChild( copyButton );

	copyButton.addEventListener( 'click', function () {

		const codeContent = element.textContent;
		navigator.clipboard.writeText( codeContent ).then( () => {

			copyButton.classList.add( 'copied' );

			setTimeout( () => {

				copyButton.classList.remove( 'copied' );

			}, 1000 );

		} );

	} );

}
```
</details>

### `updateNavigation(): void`

**Returns:** `void`

**Calls:**

- `document.querySelectorAll`
- `selected.forEach`
- `link.classList.remove`
- `window.location.pathname.split( '/' ).pop`
- `filename.split`
- `pagename.replace`
- `window.location.hash.split( '#' ).pop`
- `document.querySelector`
- `aElement.scrollIntoView`
- `aElement.classList.add`

**Internal Comments:**
```
// unselected elements (x2)
// determine target (x2)
// select target and move into view (x2)
```

<details><summary>Code</summary>

```typescript
function updateNavigation() {

	// unselected elements

	const selected = document.querySelectorAll( 'nav a.selected' );
	selected.forEach( link => link.classList.remove( 'selected' ) );

	// determine target

	const filename = window.location.pathname.split( '/' ).pop();
	const pagename = filename.split( '.' )[ 0 ];

	let target = pagename.replace( 'module-', '' );

	if ( pagename === 'global' ) {

		target = window.location.hash.split( '#' ).pop();

	}

	if ( target === '' ) return;

	// select target and move into view

	const liElement = document.querySelector( `li[data-name="${target}"]` );

	if ( liElement !== null ) {

		const aElement = liElement.firstChild;

		aElement.scrollIntoView( { block: 'center' } );
		aElement.classList.add( 'selected' );

	}

}
```
</details>


---