[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SetShadowValueCommand.js`

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
📂 **`editor/js/commands/SetShadowValueCommand.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Command` | `../Command.js` |


---

## Functions

### `SetShadowValueCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.editor.signals.objectChanged.dispatch`

<details><summary>Code</summary>

```typescript
execute() {

		this.object.shadow[ this.attributeName ] = this.newValue;
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

### `SetShadowValueCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.editor.signals.objectChanged.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		this.object.shadow[ this.attributeName ] = this.oldValue;
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

### `SetShadowValueCommand.update(cmd: any): void`

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

### `SetShadowValueCommand.toJSON(): { type: string; id: number; name: string; }`

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

### `SetShadowValueCommand.fromJSON(json: any): void`

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

### `SetShadowValueCommand`

<details><summary>Class Code</summary>

```ts
class SetShadowValueCommand extends Command {

	/**
	 * @param {Editor} editor
	 * @param {THREE.Object3D|null} object
	 * @param {string} attributeName
	 * @param {number|string|boolean|Object|null} newValue
	 * @constructor
	 */
	constructor( editor, object = null, attributeName = '', newValue = null ) {

		super( editor );

		this.type = 'SetShadowValueCommand';
		this.name = editor.strings.getKey( 'command/SetShadowValue' ) + ': ' + attributeName;
		this.updatable = true;

		this.object = object;
		this.attributeName = attributeName;
		this.oldValue = ( object !== null ) ? object.shadow[ attributeName ] : null;
		this.newValue = newValue;

	}

	execute() {

		this.object.shadow[ this.attributeName ] = this.newValue;
		this.editor.signals.objectChanged.dispatch( this.object );

	}

	undo() {

		this.object.shadow[ this.attributeName ] = this.oldValue;
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

		this.object.shadow[ this.attributeName ] = this.newValue;
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		this.object.shadow[ this.attributeName ] = this.oldValue;
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