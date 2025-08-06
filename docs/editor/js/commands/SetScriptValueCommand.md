[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SetScriptValueCommand.js`

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
📂 **`editor/js/commands/SetScriptValueCommand.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Command` | `../Command.js` |


---

## Functions

### `SetScriptValueCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.editor.signals.scriptChanged.dispatch`

<details><summary>Code</summary>

```typescript
execute() {

		this.script[ this.attributeName ] = this.newValue;

		this.editor.signals.scriptChanged.dispatch( this.script );

	}
```
</details>

### `SetScriptValueCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.editor.signals.scriptChanged.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		this.script[ this.attributeName ] = this.oldValue;

		this.editor.signals.scriptChanged.dispatch( this.script );

	}
```
</details>

### `SetScriptValueCommand.update(cmd: any): void`

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

### `SetScriptValueCommand.toJSON(): { type: string; id: number; name: string; }`

**Returns:** `{ type: string; id: number; name: string; }`

**Calls:**

- `super.toJSON`
- `this.editor.scripts[ this.object.uuid ].indexOf`

<details><summary>Code</summary>

```typescript
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.index = this.editor.scripts[ this.object.uuid ].indexOf( this.script );
		output.attributeName = this.attributeName;
		output.oldValue = this.oldValue;
		output.newValue = this.newValue;

		return output;

	}
```
</details>

### `SetScriptValueCommand.fromJSON(json: any): void`

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

		this.oldValue = json.oldValue;
		this.newValue = json.newValue;
		this.attributeName = json.attributeName;
		this.object = this.editor.objectByUuid( json.objectUuid );
		this.script = this.editor.scripts[ json.objectUuid ][ json.index ];

	}
```
</details>


---

## Classes

### `SetScriptValueCommand`

<details><summary>Class Code</summary>

```ts
class SetScriptValueCommand extends Command {

	/**
	 * @param {Editor} editor
	 * @param {THREE.Object3D|null} object
	 * @param {string} script
	 * @param {string} attributeName
	 * @param {string} newValue
	 * @constructor
	 */
	constructor( editor, object = null, script = '', attributeName = '', newValue = null ) {

		super( editor );

		this.type = 'SetScriptValueCommand';
		this.name = editor.strings.getKey( 'command/SetScriptValue' ) + ': ' + attributeName;
		this.updatable = true;

		this.object = object;
		this.script = script;

		this.attributeName = attributeName;
		this.oldValue = ( script !== '' ) ? script[ this.attributeName ] : null;
		this.newValue = newValue;

	}

	execute() {

		this.script[ this.attributeName ] = this.newValue;

		this.editor.signals.scriptChanged.dispatch( this.script );

	}

	undo() {

		this.script[ this.attributeName ] = this.oldValue;

		this.editor.signals.scriptChanged.dispatch( this.script );

	}

	update( cmd ) {

		this.newValue = cmd.newValue;

	}

	toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.index = this.editor.scripts[ this.object.uuid ].indexOf( this.script );
		output.attributeName = this.attributeName;
		output.oldValue = this.oldValue;
		output.newValue = this.newValue;

		return output;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.oldValue = json.oldValue;
		this.newValue = json.newValue;
		this.attributeName = json.attributeName;
		this.object = this.editor.objectByUuid( json.objectUuid );
		this.script = this.editor.scripts[ json.objectUuid ][ json.index ];

	}

}
```
</details>

#### Methods

##### `execute(): void`

<details><summary>Code</summary>

```ts
execute() {

		this.script[ this.attributeName ] = this.newValue;

		this.editor.signals.scriptChanged.dispatch( this.script );

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		this.script[ this.attributeName ] = this.oldValue;

		this.editor.signals.scriptChanged.dispatch( this.script );

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
		output.index = this.editor.scripts[ this.object.uuid ].indexOf( this.script );
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

		this.oldValue = json.oldValue;
		this.newValue = json.newValue;
		this.attributeName = json.attributeName;
		this.object = this.editor.objectByUuid( json.objectUuid );
		this.script = this.editor.scripts[ json.objectUuid ][ json.index ];

	}
```
</details>


---