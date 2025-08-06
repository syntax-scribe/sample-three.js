[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `AddScriptCommand.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/commands/AddScriptCommand.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Command` | `../Command.js` |


---

## Functions

### `AddScriptCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.editor.scripts[ this.object.uuid ].push`
- `this.editor.signals.scriptAdded.dispatch`

<details><summary>Code</summary>

```typescript
execute() {

		if ( this.editor.scripts[ this.object.uuid ] === undefined ) {

			this.editor.scripts[ this.object.uuid ] = [];

		}

		this.editor.scripts[ this.object.uuid ].push( this.script );

		this.editor.signals.scriptAdded.dispatch( this.script );

	}
```
</details>

### `AddScriptCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.editor.scripts[ this.object.uuid ].indexOf`
- `this.editor.scripts[ this.object.uuid ].splice`
- `this.editor.signals.scriptRemoved.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		if ( this.editor.scripts[ this.object.uuid ] === undefined ) return;

		const index = this.editor.scripts[ this.object.uuid ].indexOf( this.script );

		if ( index !== - 1 ) {

			this.editor.scripts[ this.object.uuid ].splice( index, 1 );

		}

		this.editor.signals.scriptRemoved.dispatch( this.script );

	}
```
</details>

### `AddScriptCommand.toJSON(): { type: string; id: number; name: string; }`

**Returns:** `{ type: string; id: number; name: string; }`

**Calls:**

- `super.toJSON`

<details><summary>Code</summary>

```typescript
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.script = this.script;

		return output;

	}
```
</details>

### `AddScriptCommand.fromJSON(json: any): void`

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

		this.script = json.script;
		this.object = this.editor.objectByUuid( json.objectUuid );

	}
```
</details>


---

## Classes

### `AddScriptCommand`

<details><summary>Class Code</summary>

```ts
class AddScriptCommand extends Command {

	/**
	 * @param {Editor} editor
	 * @param {THREE.Object3D|null} [object=null]
	 * @param {string} [script='']
	 * @constructor
	 */
	constructor( editor, object = null, script = '' ) {

		super( editor );

		this.type = 'AddScriptCommand';
		this.name = editor.strings.getKey( 'command/AddScript' );

		this.object = object;
		this.script = script;

	}

	execute() {

		if ( this.editor.scripts[ this.object.uuid ] === undefined ) {

			this.editor.scripts[ this.object.uuid ] = [];

		}

		this.editor.scripts[ this.object.uuid ].push( this.script );

		this.editor.signals.scriptAdded.dispatch( this.script );

	}

	undo() {

		if ( this.editor.scripts[ this.object.uuid ] === undefined ) return;

		const index = this.editor.scripts[ this.object.uuid ].indexOf( this.script );

		if ( index !== - 1 ) {

			this.editor.scripts[ this.object.uuid ].splice( index, 1 );

		}

		this.editor.signals.scriptRemoved.dispatch( this.script );

	}

	toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.script = this.script;

		return output;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.script = json.script;
		this.object = this.editor.objectByUuid( json.objectUuid );

	}

}
```
</details>

#### Methods

##### `execute(): void`

<details><summary>Code</summary>

```ts
execute() {

		if ( this.editor.scripts[ this.object.uuid ] === undefined ) {

			this.editor.scripts[ this.object.uuid ] = [];

		}

		this.editor.scripts[ this.object.uuid ].push( this.script );

		this.editor.signals.scriptAdded.dispatch( this.script );

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		if ( this.editor.scripts[ this.object.uuid ] === undefined ) return;

		const index = this.editor.scripts[ this.object.uuid ].indexOf( this.script );

		if ( index !== - 1 ) {

			this.editor.scripts[ this.object.uuid ].splice( index, 1 );

		}

		this.editor.signals.scriptRemoved.dispatch( this.script );

	}
```
</details>

##### `toJSON(): { type: string; id: number; name: string; }`

<details><summary>Code</summary>

```ts
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.script = this.script;

		return output;

	}
```
</details>

##### `fromJSON(json: any): void`

<details><summary>Code</summary>

```ts
fromJSON( json ) {

		super.fromJSON( json );

		this.script = json.script;
		this.object = this.editor.objectByUuid( json.objectUuid );

	}
```
</details>


---