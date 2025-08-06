[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SetColorCommand.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/commands/SetColorCommand.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Command` | `../Command.js` |


---

## Functions

### `SetColorCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.object[ this.attributeName ].setHex`
- `this.editor.signals.objectChanged.dispatch`

<details><summary>Code</summary>

```typescript
execute() {

		this.object[ this.attributeName ].setHex( this.newValue );
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

### `SetColorCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.object[ this.attributeName ].setHex`
- `this.editor.signals.objectChanged.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		this.object[ this.attributeName ].setHex( this.oldValue );
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

### `SetColorCommand.update(cmd: any): void`

**Parameters:**

- **`cmd`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
update( cmd ) {

		this.newValue = cmd.newValue;

	}
```
</details>

### `SetColorCommand.toJSON(): { type: string; id: number; name: string; }`

**Returns:** `{ type: string; id: number; name: string; }`

**Calls:**

- `super.toJSON`

<details><summary>Code</summary>

```typescript
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.attributeName = this.attributeName;
		output.oldValue = this.oldValue;
		output.newValue = this.newValue;

		return output;

	}
```
</details>

### `SetColorCommand.fromJSON(json: any): void`

**Parameters:**

- **`json`** `any`

**Returns:** `void`

**Calls:**

- `super.fromJSON`
- `this.editor.objectByUuid`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.objectUuid );
		this.attributeName = json.attributeName;
		this.oldValue = json.oldValue;
		this.newValue = json.newValue;

	}
```
</details>


---

## Classes

### `SetColorCommand`

<details><summary>Class Code</summary>

```ts
class SetColorCommand extends Command {

	/**
	 * @param {Editor} editor
	 * @param {THREE.Object3D|null} [object=null]
	 * @param {string} attributeName
	 * @param {?number} [newValue=null] Integer representing a hex color value
	 * @constructor
	 */
	constructor( editor, object = null, attributeName = '', newValue = null ) {

		super( editor );

		this.type = 'SetColorCommand';
		this.name = editor.strings.getKey( 'command/SetColor' ) + ': ' + attributeName;
		this.updatable = true;

		this.object = object;
		this.attributeName = attributeName;
		this.oldValue = ( object !== null ) ? this.object[ this.attributeName ].getHex() : null;
		this.newValue = newValue;

	}

	execute() {

		this.object[ this.attributeName ].setHex( this.newValue );
		this.editor.signals.objectChanged.dispatch( this.object );

	}

	undo() {

		this.object[ this.attributeName ].setHex( this.oldValue );
		this.editor.signals.objectChanged.dispatch( this.object );

	}

	update( cmd ) {

		this.newValue = cmd.newValue;

	}

	toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.attributeName = this.attributeName;
		output.oldValue = this.oldValue;
		output.newValue = this.newValue;

		return output;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.objectUuid );
		this.attributeName = json.attributeName;
		this.oldValue = json.oldValue;
		this.newValue = json.newValue;

	}

}
```
</details>

#### Methods

##### `execute(): void`

<details><summary>Code</summary>

```ts
execute() {

		this.object[ this.attributeName ].setHex( this.newValue );
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		this.object[ this.attributeName ].setHex( this.oldValue );
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

##### `update(cmd: any): void`

<details><summary>Code</summary>

```ts
update( cmd ) {

		this.newValue = cmd.newValue;

	}
```
</details>

##### `toJSON(): { type: string; id: number; name: string; }`

<details><summary>Code</summary>

```ts
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.attributeName = this.attributeName;
		output.oldValue = this.oldValue;
		output.newValue = this.newValue;

		return output;

	}
```
</details>

##### `fromJSON(json: any): void`

<details><summary>Code</summary>

```ts
fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.objectUuid );
		this.attributeName = json.attributeName;
		this.oldValue = json.oldValue;
		this.newValue = json.newValue;

	}
```
</details>


---