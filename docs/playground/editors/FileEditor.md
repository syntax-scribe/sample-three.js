[⬅️ Back to Table of Contents](../../index.md)

# 📄 `FileEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/FileEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `StringInput` | `flow` |
| `Element` | `flow` |
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `NodeUtils` | `three/webgpu` |
| `arrayBuffer` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `blob` | `Blob` | let/var | `new Blob( [ this.buffer ], { type: 'application/octet-stream' } )` | ✗ |


---

## Functions

### `FileEditor.getURL(): string`

**Returns:** `string`

**Calls:**

- `URL.createObjectURL`

<details><summary>Code</summary>

```typescript
getURL() {

		if ( this.url === null ) {

			const blob = new Blob( [ this.buffer ], { type: 'application/octet-stream' } );

			this.url = URL.createObjectURL( blob );

		}

		return this.url;

	}
```
</details>

### `FileEditor.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`
- `NodeUtils.arrayBufferToBase64`
- `this.nameInput.getValue`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		data.buffer = NodeUtils.arrayBufferToBase64( this.buffer );
		data.name = this.nameInput.getValue();

	}
```
</details>

### `FileEditor.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`
- `NodeUtils.base64ToArrayBuffer`
- `this.nameInput.setValue`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		this.buffer = NodeUtils.base64ToArrayBuffer( data.buffer );
		this.nameInput.setValue( data.name );

	}
```
</details>


---

## Classes

### `FileEditor`

<details><summary>Class Code</summary>

```ts
export class FileEditor extends BaseNodeEditor {

	constructor( buffer = null, name = 'File' ) {

		super( 'File', arrayBuffer( buffer ), 250 );

		this.nameInput = new StringInput( name ).setReadOnly( true );

		this.add( new Element().add( this.nameInput ) );

		this.url = null;

	}

	set buffer( arrayBuffer ) {

		if ( this.url !== null ) {

			URL.revokeObjectUR( this.url );

		}

		this.value.value = arrayBuffer;
		this.url = null;

	}

	get buffer() {

		return this.value.value;

	}

	getURL() {

		if ( this.url === null ) {

			const blob = new Blob( [ this.buffer ], { type: 'application/octet-stream' } );

			this.url = URL.createObjectURL( blob );

		}

		return this.url;

	}

	serialize( data ) {

		super.serialize( data );

		data.buffer = NodeUtils.arrayBufferToBase64( this.buffer );
		data.name = this.nameInput.getValue();

	}

	deserialize( data ) {

		super.deserialize( data );

		this.buffer = NodeUtils.base64ToArrayBuffer( data.buffer );
		this.nameInput.setValue( data.name );

	}

}
```
</details>

#### Methods

##### `getURL(): string`

<details><summary>Code</summary>

```ts
getURL() {

		if ( this.url === null ) {

			const blob = new Blob( [ this.buffer ], { type: 'application/octet-stream' } );

			this.url = URL.createObjectURL( blob );

		}

		return this.url;

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		data.buffer = NodeUtils.arrayBufferToBase64( this.buffer );
		data.name = this.nameInput.getValue();

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		this.buffer = NodeUtils.base64ToArrayBuffer( data.buffer );
		this.nameInput.setValue( data.name );

	}
```
</details>


---