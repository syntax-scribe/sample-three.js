[⬅️ Back to Table of Contents](../../index.md)

# 📄 `CodeEditorElement.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/elements/CodeEditorElement.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Element` | `flow` |
| `LoaderLib` | `flow` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `timeout` | `any` | let/var | `null` | ✗ |


---

## Functions

### `CodeEditorElement.focus(): void`

**Returns:** `void`

**Calls:**

- `this.editor.focus`

<details><summary>Code</summary>

```typescript
focus() {

		if ( this.editor ) this.editor.focus();

	}
```
</details>

### `CodeEditorElement.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		data.source = this.source;

	}
```
</details>

### `CodeEditorElement.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		this.source = data.source || '';

	}
```
</details>


---

## Classes

### `CodeEditorElement`

<details><summary>Class Code</summary>

```ts
export class CodeEditorElement extends Element {

	constructor( source = '' ) {

		super();

		this.updateInterval = 500;

		this._source = source;

		this.dom.style[ 'z-index' ] = - 1;
		this.dom.classList.add( 'no-zoom' );

		this.setHeight( 500 );

		const editorDOM = document.createElement( 'div' );
		editorDOM.style.width = '100%';
		editorDOM.style.height = '100%';
		this.dom.appendChild( editorDOM );

		this.editor = null; // async

		window.require.config( { paths: { 'vs': 'https://cdn.jsdelivr.net/npm/monaco-editor@0.52.2/min/vs' } } );

		require( [ 'vs/editor/editor.main' ], () => {

			this.editor = window.monaco.editor.create( editorDOM, {
				value: this.source,
				language: 'javascript',
				theme: 'vs-dark',
				automaticLayout: true,
				minimap: { enabled: false }
			} );

			let timeout = null;

			this.editor.getModel().onDidChangeContent( () => {

				this._source = this.editor.getValue();

				if ( timeout ) clearTimeout( timeout );

				timeout = setTimeout( () => {

					this.dispatchEvent( new Event( 'change' ) );

				}, this.updateInterval );

			} );

		} );

	}

	set source( value ) {

		if ( this._source === value ) return;

		this._source = value;

		if ( this.editor ) this.editor.setValue( value );

		this.dispatchEvent( new Event( 'change' ) );

	}

	get source() {

		return this._source;

	}

	focus() {

		if ( this.editor ) this.editor.focus();

	}

	serialize( data ) {

		super.serialize( data );

		data.source = this.source;

	}

	deserialize( data ) {

		super.deserialize( data );

		this.source = data.source || '';

	}

}
```
</details>

#### Methods

##### `focus(): void`

<details><summary>Code</summary>

```ts
focus() {

		if ( this.editor ) this.editor.focus();

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		data.source = this.source;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		this.source = data.source || '';

	}
```
</details>


---