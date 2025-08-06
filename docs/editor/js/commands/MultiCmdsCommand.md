[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MultiCmdsCommand.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/commands/MultiCmdsCommand.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Command` | `../Command.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `cmds` | `any[]` | let/var | `[]` | ✗ |
| `cmds` | `any` | let/var | `json.cmds` | ✗ |
| `cmd` | `any` | let/var | `new window[ cmds[ i ].type ]()` | ✗ |


---

## Functions

### `MultiCmdsCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.cmdArray[ i ].execute`
- `this.editor.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
execute() {

		this.editor.signals.sceneGraphChanged.active = false;

		for ( let i = 0; i < this.cmdArray.length; i ++ ) {

			this.cmdArray[ i ].execute();

		}

		this.editor.signals.sceneGraphChanged.active = true;
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `MultiCmdsCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.cmdArray[ i ].undo`
- `this.editor.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		this.editor.signals.sceneGraphChanged.active = false;

		for ( let i = this.cmdArray.length - 1; i >= 0; i -- ) {

			this.cmdArray[ i ].undo();

		}

		this.editor.signals.sceneGraphChanged.active = true;
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `MultiCmdsCommand.toJSON(): { type: string; id: number; name: string; }`

**Returns:** `{ type: string; id: number; name: string; }`

**Calls:**

- `super.toJSON`
- `cmds.push`
- `this.cmdArray[ i ].toJSON`

<details><summary>Code</summary>

```typescript
toJSON() {

		const output = super.toJSON( this );

		const cmds = [];
		for ( let i = 0; i < this.cmdArray.length; i ++ ) {

			cmds.push( this.cmdArray[ i ].toJSON() );

		}

		output.cmds = cmds;

		return output;

	}
```
</details>

### `MultiCmdsCommand.fromJSON(json: any): void`

**Parameters:**

- **`json`** `any`

**Returns:** `void`

**Calls:**

- `super.fromJSON`
- `cmd.fromJSON`
- `this.cmdArray.push`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		super.fromJSON( json );

		const cmds = json.cmds;
		for ( let i = 0; i < cmds.length; i ++ ) {

			const cmd = new window[ cmds[ i ].type ]();	// creates a new object of type "json.type"
			cmd.fromJSON( cmds[ i ] );
			this.cmdArray.push( cmd );

		}

	}
```
</details>


---

## Classes

### `MultiCmdsCommand`

<details><summary>Class Code</summary>

```ts
class MultiCmdsCommand extends Command {

	/**
	 * @param {Editor} editor
	 * @param {Array<Command>} [cmdArray=[]]
	 * @constructor
	 */
	constructor( editor, cmdArray = [] ) {

		super( editor );

		this.type = 'MultiCmdsCommand';
		this.name = editor.strings.getKey( 'command/MultiCmds' );

		this.cmdArray = cmdArray;

	}

	execute() {

		this.editor.signals.sceneGraphChanged.active = false;

		for ( let i = 0; i < this.cmdArray.length; i ++ ) {

			this.cmdArray[ i ].execute();

		}

		this.editor.signals.sceneGraphChanged.active = true;
		this.editor.signals.sceneGraphChanged.dispatch();

	}

	undo() {

		this.editor.signals.sceneGraphChanged.active = false;

		for ( let i = this.cmdArray.length - 1; i >= 0; i -- ) {

			this.cmdArray[ i ].undo();

		}

		this.editor.signals.sceneGraphChanged.active = true;
		this.editor.signals.sceneGraphChanged.dispatch();

	}

	toJSON() {

		const output = super.toJSON( this );

		const cmds = [];
		for ( let i = 0; i < this.cmdArray.length; i ++ ) {

			cmds.push( this.cmdArray[ i ].toJSON() );

		}

		output.cmds = cmds;

		return output;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		const cmds = json.cmds;
		for ( let i = 0; i < cmds.length; i ++ ) {

			const cmd = new window[ cmds[ i ].type ]();	// creates a new object of type "json.type"
			cmd.fromJSON( cmds[ i ] );
			this.cmdArray.push( cmd );

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

		this.editor.signals.sceneGraphChanged.active = false;

		for ( let i = 0; i < this.cmdArray.length; i ++ ) {

			this.cmdArray[ i ].execute();

		}

		this.editor.signals.sceneGraphChanged.active = true;
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		this.editor.signals.sceneGraphChanged.active = false;

		for ( let i = this.cmdArray.length - 1; i >= 0; i -- ) {

			this.cmdArray[ i ].undo();

		}

		this.editor.signals.sceneGraphChanged.active = true;
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

##### `toJSON(): { type: string; id: number; name: string; }`

<details><summary>Code</summary>

```ts
toJSON() {

		const output = super.toJSON( this );

		const cmds = [];
		for ( let i = 0; i < this.cmdArray.length; i ++ ) {

			cmds.push( this.cmdArray[ i ].toJSON() );

		}

		output.cmds = cmds;

		return output;

	}
```
</details>

##### `fromJSON(json: any): void`

<details><summary>Code</summary>

```ts
fromJSON( json ) {

		super.fromJSON( json );

		const cmds = json.cmds;
		for ( let i = 0; i < cmds.length; i ++ ) {

			const cmd = new window[ cmds[ i ].type ]();	// creates a new object of type "json.type"
			cmd.fromJSON( cmds[ i ] );
			this.cmdArray.push( cmd );

		}

	}
```
</details>


---