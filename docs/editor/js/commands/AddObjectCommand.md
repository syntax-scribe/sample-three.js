[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `AddObjectCommand.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/commands/AddObjectCommand.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Command` | `../Command.js` |
| `ObjectLoader` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `loader` | `any` | let/var | `new ObjectLoader()` | ✗ |


---

## Functions

### `AddObjectCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.editor.addObject`
- `this.editor.select`

<details><summary>Code</summary>

```typescript
execute() {

		this.editor.addObject( this.object );
		this.editor.select( this.object );

	}
```
</details>

### `AddObjectCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.editor.removeObject`
- `this.editor.deselect`

<details><summary>Code</summary>

```typescript
undo() {

		this.editor.removeObject( this.object );
		this.editor.deselect();

	}
```
</details>

### `AddObjectCommand.toJSON(): { type: string; id: number; name: string; }`

**Returns:** `{ type: string; id: number; name: string; }`

**Calls:**

- `super.toJSON`
- `this.object.toJSON`

<details><summary>Code</summary>

```typescript
toJSON() {

		const output = super.toJSON( this );

		output.object = this.object.toJSON();

		return output;

	}
```
</details>

### `AddObjectCommand.fromJSON(json: any): void`

**Parameters:**

- **`json`** `any`

**Returns:** `void`

**Calls:**

- `super.fromJSON`
- `this.editor.objectByUuid`
- `loader.parse`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.object.object.uuid );

		if ( this.object === undefined ) {

			const loader = new ObjectLoader();
			this.object = loader.parse( json.object );

		}

	}
```
</details>


---

## Classes

### `AddObjectCommand`

<details><summary>Class Code</summary>

```ts
class AddObjectCommand extends Command {

	/**
	 * @param {Editor} editor
	 * @param {THREE.Object3D|null} [object=null]
	 * @constructor
	 */
	constructor( editor, object = null ) {

		super( editor );

		this.type = 'AddObjectCommand';

		this.object = object;

		if ( object !== null ) {

			this.name = editor.strings.getKey( 'command/AddObject' ) + ': ' + object.name;

		}

	}

	execute() {

		this.editor.addObject( this.object );
		this.editor.select( this.object );

	}

	undo() {

		this.editor.removeObject( this.object );
		this.editor.deselect();

	}

	toJSON() {

		const output = super.toJSON( this );

		output.object = this.object.toJSON();

		return output;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.object.object.uuid );

		if ( this.object === undefined ) {

			const loader = new ObjectLoader();
			this.object = loader.parse( json.object );

		}

	}

}
```
</details>

#### Methods

##### `execute(): void`

<details><summary>Code</summary>

```ts
execute() {

		this.editor.addObject( this.object );
		this.editor.select( this.object );

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		this.editor.removeObject( this.object );
		this.editor.deselect();

	}
```
</details>

##### `toJSON(): { type: string; id: number; name: string; }`

<details><summary>Code</summary>

```ts
toJSON() {

		const output = super.toJSON( this );

		output.object = this.object.toJSON();

		return output;

	}
```
</details>

##### `fromJSON(json: any): void`

<details><summary>Code</summary>

```ts
fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.object.object.uuid );

		if ( this.object === undefined ) {

			const loader = new ObjectLoader();
			this.object = loader.parse( json.object );

		}

	}
```
</details>


---