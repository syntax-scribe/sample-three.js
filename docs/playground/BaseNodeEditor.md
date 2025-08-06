[⬅️ Back to Table of Contents](../index.md)

# 📄 `BaseNodeEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 17 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/BaseNodeEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `flow` |
| `ButtonInput` | `flow` |
| `TitleElement` | `flow` |
| `ContextMenu` | `flow` |
| `exportJSON` | `./NodeEditorUtils.js` |
| `onValidNode` | `./NodeEditorUtils.js` |
| `setOutputAestheticsFromNode` | `./DataTypeLib.js` |
| `getColorFromNode` | `./DataTypeLib.js` |
| `getLengthFromNode` | `./DataTypeLib.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `context` | `any` | let/var | `new ContextMenu( this.dom )` | ✗ |


---

## Functions

### `BaseNodeEditor.getColor(): string`

**Returns:** `string`

**Calls:**

- `getColorFromNode (from ./DataTypeLib.js)`

<details><summary>Code</summary>

```typescript
getColor() {

		const color = getColorFromNode( this.value );

		return color ? color + 'BB' : null;

	}
```
</details>

### `BaseNodeEditor.hasJSON(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
hasJSON() {

		return this.value && typeof this.value.toJSON === 'function';

	}
```
</details>

### `BaseNodeEditor.exportJSON(): any`

**Returns:** `any`

**Calls:**

- `this.value.toJSON`

<details><summary>Code</summary>

```typescript
exportJSON() {

		return this.value.toJSON();

	}
```
</details>

### `BaseNodeEditor.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		delete data.width;

	}
```
</details>

### `BaseNodeEditor.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		delete data.width;

		super.deserialize( data );

	}
```
</details>

### `BaseNodeEditor.setEditor(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

**Calls:**

- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
setEditor( value ) {

		this.editor = value;

		this.dispatchEvent( new Event( 'editor' ) );

		return this;

	}
```
</details>

### `BaseNodeEditor.add(element: any): any`

**Parameters:**

- **`element`** `any`

**Returns:** `any`

**Calls:**

- `element.onValid`
- `this.onValidElement`
- `super.add`

<details><summary>Code</summary>

```typescript
add( element ) {

		element.onValid( ( source, target ) => this.onValidElement( source, target ) );

		return super.add( element );

	}
```
</details>

### `BaseNodeEditor.setName(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

**Calls:**

- `this.title.setTitle`

<details><summary>Code</summary>

```typescript
setName( value ) {

		this.title.setTitle( value );

		return this;

	}
```
</details>

### `BaseNodeEditor.setIcon(value: any): this`

**Parameters:**

- **`value`** `any`

**Returns:** `this`

**Calls:**

- `this.title.setIcon`

<details><summary>Code</summary>

```typescript
setIcon( value ) {

		this.title.setIcon( 'ti ti-' + value );

		return this;

	}
```
</details>

### `BaseNodeEditor.getName(): any`

**Returns:** `any`

**Calls:**

- `this.title.getTitle`

<details><summary>Code</summary>

```typescript
getName() {

		return this.title.getTitle();

	}
```
</details>

### `BaseNodeEditor.setObjectCallback(callback: any): this`

**Parameters:**

- **`callback`** `any`

**Returns:** `this`

**Calls:**

- `this.title.setObjectCallback`

<details><summary>Code</summary>

```typescript
setObjectCallback( callback ) {

		this.title.setObjectCallback( callback );

		return this;

	}
```
</details>

### `BaseNodeEditor.getObject(callback: any): any`

**Parameters:**

- **`callback`** `any`

**Returns:** `any`

**Calls:**

- `this.title.getObject`

<details><summary>Code</summary>

```typescript
getObject( callback ) {

		return this.title.getObject( callback );

	}
```
</details>

### `BaseNodeEditor.setColor(color: any): this`

**Parameters:**

- **`color`** `any`

**Returns:** `this`

**Calls:**

- `this.title.setColor`

<details><summary>Code</summary>

```typescript
setColor( color ) {

		this.title.setColor( color );

		return this;

	}
```
</details>

### `BaseNodeEditor.invalidate(): void`

**Returns:** `void`

**Calls:**

- `this.title.dispatchEvent`

<details><summary>Code</summary>

```typescript
invalidate() {

		this.title.dispatchEvent( new Event( 'connect' ) );

	}
```
</details>

### `BaseNodeEditor.dispose(): void`

**Returns:** `void`

**Calls:**

- `this.setEditor`
- `this.context.hide`
- `super.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.setEditor( null );

		this.context.hide();

		super.dispose();

	}
```
</details>

### `getObjectCallback(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
( /*output = null*/ ) => {

			return this.value;

		}
```
</details>

### `onAddButtons(): void`

**Returns:** `void`

**Calls:**

- `context.removeEventListener`
- `context.add`
- `new ButtonInput( 'Remove' ).setIcon( 'ti ti-trash' ).onClick`
- `this.dispose`
- `this.hasJSON`
- `this.context.add`
- `new ButtonInput( 'Export' ).setIcon( 'ti ti-download' ).onClick`
- `exportJSON (from ./NodeEditorUtils.js)`
- `this.exportJSON`
- `new ButtonInput( 'Isolate' ).setIcon( 'ti ti-3d-cube-sphere' ).onClick`
- `this.context.hide`
- `this.title.dom.dispatchEvent`

<details><summary>Code</summary>

```typescript
() => {

			context.removeEventListener( 'show', onAddButtons );

			context.add( new ButtonInput( 'Remove' ).setIcon( 'ti ti-trash' ).onClick( () => {

				this.dispose();

			} ) );

			if ( this.hasJSON() ) {

				this.context.add( new ButtonInput( 'Export' ).setIcon( 'ti ti-download' ).onClick( () => {

					exportJSON( this.exportJSON(), this.constructor.name );

				} ) );

			}

			context.add( new ButtonInput( 'Isolate' ).setIcon( 'ti ti-3d-cube-sphere' ).onClick( () => {

				this.context.hide();

				this.title.dom.dispatchEvent( new MouseEvent( 'dblclick' ) );

			} ) );

		}
```
</details>


---

## Classes

### `BaseNodeEditor`

<details><summary>Class Code</summary>

```ts
export class BaseNodeEditor extends Node {

	constructor( name, value = null, width = 300 ) {

		super();

		const getObjectCallback = ( /*output = null*/ ) => {

			return this.value;

		};

		this.setWidth( width );

		const title = new TitleElement( name )
			.setObjectCallback( getObjectCallback )
			.setSerializable( false );

		setOutputAestheticsFromNode( title, value );

		const contextButton = new ButtonInput().onClick( () => {

			context.open();

		} ).setIcon( 'ti ti-dots' );

		const onAddButtons = () => {

			context.removeEventListener( 'show', onAddButtons );

			context.add( new ButtonInput( 'Remove' ).setIcon( 'ti ti-trash' ).onClick( () => {

				this.dispose();

			} ) );

			if ( this.hasJSON() ) {

				this.context.add( new ButtonInput( 'Export' ).setIcon( 'ti ti-download' ).onClick( () => {

					exportJSON( this.exportJSON(), this.constructor.name );

				} ) );

			}

			context.add( new ButtonInput( 'Isolate' ).setIcon( 'ti ti-3d-cube-sphere' ).onClick( () => {

				this.context.hide();

				this.title.dom.dispatchEvent( new MouseEvent( 'dblclick' ) );

			} ) );

		};

		const context = new ContextMenu( this.dom );
		context.addEventListener( 'show', onAddButtons );

		this.title = title;

		if ( this.icon ) this.setIcon( 'ti ti-' + this.icon );

		this.contextButton = contextButton;
		this.context = context;

		title.addButton( contextButton );

		this.add( title );

		this.editor = null;

		this.value = value;

		this.onValidElement = onValidNode;

		this.outputLength = getLengthFromNode( value );

	}

	getColor() {

		const color = getColorFromNode( this.value );

		return color ? color + 'BB' : null;

	}

	hasJSON() {

		return this.value && typeof this.value.toJSON === 'function';

	}

	exportJSON() {

		return this.value.toJSON();

	}

	serialize( data ) {

		super.serialize( data );

		delete data.width;

	}

	deserialize( data ) {

		delete data.width;

		super.deserialize( data );

	}

	setEditor( value ) {

		this.editor = value;

		this.dispatchEvent( new Event( 'editor' ) );

		return this;

	}

	add( element ) {

		element.onValid( ( source, target ) => this.onValidElement( source, target ) );

		return super.add( element );

	}

	setName( value ) {

		this.title.setTitle( value );

		return this;

	}

	setIcon( value ) {

		this.title.setIcon( 'ti ti-' + value );

		return this;

	}

	getName() {

		return this.title.getTitle();

	}

	setObjectCallback( callback ) {

		this.title.setObjectCallback( callback );

		return this;

	}

	getObject( callback ) {

		return this.title.getObject( callback );

	}

	setColor( color ) {

		this.title.setColor( color );

		return this;

	}

	invalidate() {

		this.title.dispatchEvent( new Event( 'connect' ) );

	}

	dispose() {

		this.setEditor( null );

		this.context.hide();

		super.dispose();

	}

}
```
</details>

#### Methods

##### `getColor(): string`

<details><summary>Code</summary>

```ts
getColor() {

		const color = getColorFromNode( this.value );

		return color ? color + 'BB' : null;

	}
```
</details>

##### `hasJSON(): boolean`

<details><summary>Code</summary>

```ts
hasJSON() {

		return this.value && typeof this.value.toJSON === 'function';

	}
```
</details>

##### `exportJSON(): any`

<details><summary>Code</summary>

```ts
exportJSON() {

		return this.value.toJSON();

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		delete data.width;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		delete data.width;

		super.deserialize( data );

	}
```
</details>

##### `setEditor(value: any): this`

<details><summary>Code</summary>

```ts
setEditor( value ) {

		this.editor = value;

		this.dispatchEvent( new Event( 'editor' ) );

		return this;

	}
```
</details>

##### `add(element: any): any`

<details><summary>Code</summary>

```ts
add( element ) {

		element.onValid( ( source, target ) => this.onValidElement( source, target ) );

		return super.add( element );

	}
```
</details>

##### `setName(value: any): this`

<details><summary>Code</summary>

```ts
setName( value ) {

		this.title.setTitle( value );

		return this;

	}
```
</details>

##### `setIcon(value: any): this`

<details><summary>Code</summary>

```ts
setIcon( value ) {

		this.title.setIcon( 'ti ti-' + value );

		return this;

	}
```
</details>

##### `getName(): any`

<details><summary>Code</summary>

```ts
getName() {

		return this.title.getTitle();

	}
```
</details>

##### `setObjectCallback(callback: any): this`

<details><summary>Code</summary>

```ts
setObjectCallback( callback ) {

		this.title.setObjectCallback( callback );

		return this;

	}
```
</details>

##### `getObject(callback: any): any`

<details><summary>Code</summary>

```ts
getObject( callback ) {

		return this.title.getObject( callback );

	}
```
</details>

##### `setColor(color: any): this`

<details><summary>Code</summary>

```ts
setColor( color ) {

		this.title.setColor( color );

		return this;

	}
```
</details>

##### `invalidate(): void`

<details><summary>Code</summary>

```ts
invalidate() {

		this.title.dispatchEvent( new Event( 'connect' ) );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.setEditor( null );

		this.context.hide();

		super.dispose();

	}
```
</details>


---