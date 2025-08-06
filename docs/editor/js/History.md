[⬅️ Back to Table of Contents](../../index.md)

# 📄 `History.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 12 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/History.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `lastCmd` | `any` | let/var | `this.undos[ this.undos.length - 1 ]` | ✗ |
| `timeDifference` | `number` | let/var | `Date.now() - this.lastCmdTime` | ✗ |
| `isUpdatableCmd` | `boolean` | let/var | `lastCmd && lastCmd.updatable && cmd.updatable && lastCmd.object === cmd.objec...` | ✗ |
| `cmd` | `any` | let/var | `undefined` | ✗ |
| `cmd` | `any` | let/var | `undefined` | ✗ |
| `history` | `{ undos: any[]; redos: any[]; }` | let/var | `{}` | ✗ |
| `cmdJSON` | `any` | let/var | `json.undos[ i ]` | ✗ |
| `cmd` | `any` | let/var | `new Commands[ cmdJSON.type ]( this.editor )` | ✗ |
| `cmdJSON` | `any` | let/var | `json.redos[ i ]` | ✗ |
| `cmd` | `any` | let/var | `new Commands[ cmdJSON.type ]( this.editor )` | ✗ |
| `cmd` | `any` | let/var | `this.undos.length > 0 ? this.undos[ this.undos.length - 1 ] : undefined` | ✗ |


---

## Functions

### `History.execute(cmd: any, optionalName: any): void`

**Parameters:**

- **`cmd`** `any`
- **`optionalName`** `any`

**Returns:** `void`

**Calls:**

- `Date.now`
- `lastCmd.update`
- `this.undos.push`
- `cmd.execute`
- `this.config.getKey`
- `cmd.toJSON`
- `this.editor.signals.historyChanged.dispatch`

**Internal Comments:**
```
// When the cmd.type is "SetScriptValueCommand" the timeDifference is ignored (x4)
// the command is not updatable and is added as a new part of the history (x5)
// clearing all the redo-commands (x4)
```

<details><summary>Code</summary>

```typescript
execute( cmd, optionalName ) {

		const lastCmd = this.undos[ this.undos.length - 1 ];
		const timeDifference = Date.now() - this.lastCmdTime;

		const isUpdatableCmd = lastCmd &&
			lastCmd.updatable &&
			cmd.updatable &&
			lastCmd.object === cmd.object &&
			lastCmd.type === cmd.type &&
			lastCmd.script === cmd.script &&
			lastCmd.attributeName === cmd.attributeName;

		if ( isUpdatableCmd && cmd.type === 'SetScriptValueCommand' ) {

			// When the cmd.type is "SetScriptValueCommand" the timeDifference is ignored

			lastCmd.update( cmd );
			cmd = lastCmd;

		} else if ( isUpdatableCmd && timeDifference < 500 ) {

			lastCmd.update( cmd );
			cmd = lastCmd;

		} else {

			// the command is not updatable and is added as a new part of the history

			this.undos.push( cmd );
			cmd.id = ++ this.idCounter;

		}

		cmd.name = ( optionalName !== undefined ) ? optionalName : cmd.name;
		cmd.execute();
		cmd.inMemory = true;

		if ( this.config.getKey( 'settings/history' ) ) {

			cmd.json = cmd.toJSON();	// serialize the cmd immediately after execution and append the json to the cmd

		}

		this.lastCmdTime = Date.now();

		// clearing all the redo-commands

		this.redos = [];
		this.editor.signals.historyChanged.dispatch( cmd );

	}
```
</details>

### `History.undo(): any`

**Returns:** `any`

**Calls:**

- `alert`
- `this.editor.strings.getKey`
- `this.undos.pop`
- `cmd.fromJSON`
- `cmd.undo`
- `this.redos.push`
- `this.editor.signals.historyChanged.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		if ( this.historyDisabled ) {

			alert( this.editor.strings.getKey( 'prompt/history/forbid' ) );
			return;

		}

		let cmd = undefined;

		if ( this.undos.length > 0 ) {

			cmd = this.undos.pop();

			if ( cmd.inMemory === false ) {

				cmd.fromJSON( cmd.json );

			}

		}

		if ( cmd !== undefined ) {

			cmd.undo();
			this.redos.push( cmd );
			this.editor.signals.historyChanged.dispatch( cmd );

		}

		return cmd;

	}
```
</details>

### `History.redo(): any`

**Returns:** `any`

**Calls:**

- `alert`
- `this.editor.strings.getKey`
- `this.redos.pop`
- `cmd.fromJSON`
- `cmd.execute`
- `this.undos.push`
- `this.editor.signals.historyChanged.dispatch`

<details><summary>Code</summary>

```typescript
redo() {

		if ( this.historyDisabled ) {

			alert( this.editor.strings.getKey( 'prompt/history/forbid' ) );
			return;

		}

		let cmd = undefined;

		if ( this.redos.length > 0 ) {

			cmd = this.redos.pop();

			if ( cmd.inMemory === false ) {

				cmd.fromJSON( cmd.json );

			}

		}

		if ( cmd !== undefined ) {

			cmd.execute();
			this.undos.push( cmd );
			this.editor.signals.historyChanged.dispatch( cmd );

		}

		return cmd;

	}
```
</details>

### `History.toJSON(): { undos: any[]; redos: any[]; }`

**Returns:** `{ undos: any[]; redos: any[]; }`

**Calls:**

- `this.config.getKey`
- `this.undos[ i ].hasOwnProperty`
- `history.undos.push`
- `this.redos[ i ].hasOwnProperty`
- `history.redos.push`

**Internal Comments:**
```
// Append Undos to History
// Append Redos to History
```

<details><summary>Code</summary>

```typescript
toJSON() {

		const history = {};
		history.undos = [];
		history.redos = [];

		if ( ! this.config.getKey( 'settings/history' ) ) {

			return history;

		}

		// Append Undos to History

		for ( let i = 0; i < this.undos.length; i ++ ) {

			if ( this.undos[ i ].hasOwnProperty( 'json' ) ) {

				history.undos.push( this.undos[ i ].json );

			}

		}

		// Append Redos to History

		for ( let i = 0; i < this.redos.length; i ++ ) {

			if ( this.redos[ i ].hasOwnProperty( 'json' ) ) {

				history.redos.push( this.redos[ i ].json );

			}

		}

		return history;

	}
```
</details>

### `History.fromJSON(json: any): void`

**Parameters:**

- **`json`** `any`

**Returns:** `void`

**Calls:**

- `this.undos.push`
- `this.redos.push`
- `this.editor.signals.historyChanged.dispatch`

**Internal Comments:**
```
// Select the last executed undo-command (x7)
```

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		if ( json === undefined ) return;

		for ( let i = 0; i < json.undos.length; i ++ ) {

			const cmdJSON = json.undos[ i ];
			const cmd = new Commands[ cmdJSON.type ]( this.editor ); // creates a new object of type "json.type"
			cmd.json = cmdJSON;
			cmd.id = cmdJSON.id;
			cmd.name = cmdJSON.name;
			this.undos.push( cmd );
			this.idCounter = ( cmdJSON.id > this.idCounter ) ? cmdJSON.id : this.idCounter; // set last used idCounter

		}

		for ( let i = 0; i < json.redos.length; i ++ ) {

			const cmdJSON = json.redos[ i ];
			const cmd = new Commands[ cmdJSON.type ]( this.editor ); // creates a new object of type "json.type"
			cmd.json = cmdJSON;
			cmd.id = cmdJSON.id;
			cmd.name = cmdJSON.name;
			this.redos.push( cmd );
			this.idCounter = ( cmdJSON.id > this.idCounter ) ? cmdJSON.id : this.idCounter; // set last used idCounter

		}

		// Select the last executed undo-command
		this.editor.signals.historyChanged.dispatch( this.undos[ this.undos.length - 1 ] );

	}
```
</details>

### `History.clear(): void`

**Returns:** `void`

**Calls:**

- `this.editor.signals.historyChanged.dispatch`

<details><summary>Code</summary>

```typescript
clear() {

		this.undos = [];
		this.redos = [];
		this.idCounter = 0;

		this.editor.signals.historyChanged.dispatch();

	}
```
</details>

### `History.goToState(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

**Calls:**

- `alert`
- `this.editor.strings.getKey`
- `this.redo`
- `this.undo`
- `this.editor.signals.sceneGraphChanged.dispatch`
- `this.editor.signals.historyChanged.dispatch`

<details><summary>Code</summary>

```typescript
goToState( id ) {

		if ( this.historyDisabled ) {

			alert( this.editor.strings.getKey( 'prompt/history/forbid' ) );
			return;

		}

		this.editor.signals.sceneGraphChanged.active = false;
		this.editor.signals.historyChanged.active = false;

		let cmd = this.undos.length > 0 ? this.undos[ this.undos.length - 1 ] : undefined;	// next cmd to pop

		if ( cmd === undefined || id > cmd.id ) {

			cmd = this.redo();
			while ( cmd !== undefined && id > cmd.id ) {

				cmd = this.redo();

			}

		} else {

			while ( true ) {

				cmd = this.undos[ this.undos.length - 1 ];	// next cmd to pop

				if ( cmd === undefined || id === cmd.id ) break;

				this.undo();

			}

		}

		this.editor.signals.sceneGraphChanged.active = true;
		this.editor.signals.historyChanged.active = true;

		this.editor.signals.sceneGraphChanged.dispatch();
		this.editor.signals.historyChanged.dispatch( cmd );

	}
```
</details>

### `History.enableSerialization(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

**Calls:**

- `this.goToState`
- `this.redo`
- `cmd.hasOwnProperty`
- `cmd.toJSON`

**Internal Comments:**
```
/**
		 * because there might be commands in this.undos and this.redos
		 * which have not been serialized with .toJSON() we go back
		 * to the oldest command and redo one command after the other
		 * while also calling .toJSON() on them.
		 */ (x4)
```

<details><summary>Code</summary>

```typescript
enableSerialization( id ) {

		/**
		 * because there might be commands in this.undos and this.redos
		 * which have not been serialized with .toJSON() we go back
		 * to the oldest command and redo one command after the other
		 * while also calling .toJSON() on them.
		 */

		this.goToState( - 1 );

		this.editor.signals.sceneGraphChanged.active = false;
		this.editor.signals.historyChanged.active = false;

		let cmd = this.redo();
		while ( cmd !== undefined ) {

			if ( ! cmd.hasOwnProperty( 'json' ) ) {

				cmd.json = cmd.toJSON();

			}

			cmd = this.redo();

		}

		this.editor.signals.sceneGraphChanged.active = true;
		this.editor.signals.historyChanged.active = true;

		this.goToState( id );

	}
```
</details>


---

## Classes

### `History`

<details><summary>Class Code</summary>

```ts
class History {

	constructor( editor ) {

		this.editor = editor;
		this.undos = [];
		this.redos = [];
		this.lastCmdTime = Date.now();
		this.idCounter = 0;

		this.historyDisabled = false;
		this.config = editor.config;

		// signals

		const scope = this;

		this.editor.signals.startPlayer.add( function () {

			scope.historyDisabled = true;

		} );

		this.editor.signals.stopPlayer.add( function () {

			scope.historyDisabled = false;

		} );

	}

	execute( cmd, optionalName ) {

		const lastCmd = this.undos[ this.undos.length - 1 ];
		const timeDifference = Date.now() - this.lastCmdTime;

		const isUpdatableCmd = lastCmd &&
			lastCmd.updatable &&
			cmd.updatable &&
			lastCmd.object === cmd.object &&
			lastCmd.type === cmd.type &&
			lastCmd.script === cmd.script &&
			lastCmd.attributeName === cmd.attributeName;

		if ( isUpdatableCmd && cmd.type === 'SetScriptValueCommand' ) {

			// When the cmd.type is "SetScriptValueCommand" the timeDifference is ignored

			lastCmd.update( cmd );
			cmd = lastCmd;

		} else if ( isUpdatableCmd && timeDifference < 500 ) {

			lastCmd.update( cmd );
			cmd = lastCmd;

		} else {

			// the command is not updatable and is added as a new part of the history

			this.undos.push( cmd );
			cmd.id = ++ this.idCounter;

		}

		cmd.name = ( optionalName !== undefined ) ? optionalName : cmd.name;
		cmd.execute();
		cmd.inMemory = true;

		if ( this.config.getKey( 'settings/history' ) ) {

			cmd.json = cmd.toJSON();	// serialize the cmd immediately after execution and append the json to the cmd

		}

		this.lastCmdTime = Date.now();

		// clearing all the redo-commands

		this.redos = [];
		this.editor.signals.historyChanged.dispatch( cmd );

	}

	undo() {

		if ( this.historyDisabled ) {

			alert( this.editor.strings.getKey( 'prompt/history/forbid' ) );
			return;

		}

		let cmd = undefined;

		if ( this.undos.length > 0 ) {

			cmd = this.undos.pop();

			if ( cmd.inMemory === false ) {

				cmd.fromJSON( cmd.json );

			}

		}

		if ( cmd !== undefined ) {

			cmd.undo();
			this.redos.push( cmd );
			this.editor.signals.historyChanged.dispatch( cmd );

		}

		return cmd;

	}

	redo() {

		if ( this.historyDisabled ) {

			alert( this.editor.strings.getKey( 'prompt/history/forbid' ) );
			return;

		}

		let cmd = undefined;

		if ( this.redos.length > 0 ) {

			cmd = this.redos.pop();

			if ( cmd.inMemory === false ) {

				cmd.fromJSON( cmd.json );

			}

		}

		if ( cmd !== undefined ) {

			cmd.execute();
			this.undos.push( cmd );
			this.editor.signals.historyChanged.dispatch( cmd );

		}

		return cmd;

	}

	toJSON() {

		const history = {};
		history.undos = [];
		history.redos = [];

		if ( ! this.config.getKey( 'settings/history' ) ) {

			return history;

		}

		// Append Undos to History

		for ( let i = 0; i < this.undos.length; i ++ ) {

			if ( this.undos[ i ].hasOwnProperty( 'json' ) ) {

				history.undos.push( this.undos[ i ].json );

			}

		}

		// Append Redos to History

		for ( let i = 0; i < this.redos.length; i ++ ) {

			if ( this.redos[ i ].hasOwnProperty( 'json' ) ) {

				history.redos.push( this.redos[ i ].json );

			}

		}

		return history;

	}

	fromJSON( json ) {

		if ( json === undefined ) return;

		for ( let i = 0; i < json.undos.length; i ++ ) {

			const cmdJSON = json.undos[ i ];
			const cmd = new Commands[ cmdJSON.type ]( this.editor ); // creates a new object of type "json.type"
			cmd.json = cmdJSON;
			cmd.id = cmdJSON.id;
			cmd.name = cmdJSON.name;
			this.undos.push( cmd );
			this.idCounter = ( cmdJSON.id > this.idCounter ) ? cmdJSON.id : this.idCounter; // set last used idCounter

		}

		for ( let i = 0; i < json.redos.length; i ++ ) {

			const cmdJSON = json.redos[ i ];
			const cmd = new Commands[ cmdJSON.type ]( this.editor ); // creates a new object of type "json.type"
			cmd.json = cmdJSON;
			cmd.id = cmdJSON.id;
			cmd.name = cmdJSON.name;
			this.redos.push( cmd );
			this.idCounter = ( cmdJSON.id > this.idCounter ) ? cmdJSON.id : this.idCounter; // set last used idCounter

		}

		// Select the last executed undo-command
		this.editor.signals.historyChanged.dispatch( this.undos[ this.undos.length - 1 ] );

	}

	clear() {

		this.undos = [];
		this.redos = [];
		this.idCounter = 0;

		this.editor.signals.historyChanged.dispatch();

	}

	goToState( id ) {

		if ( this.historyDisabled ) {

			alert( this.editor.strings.getKey( 'prompt/history/forbid' ) );
			return;

		}

		this.editor.signals.sceneGraphChanged.active = false;
		this.editor.signals.historyChanged.active = false;

		let cmd = this.undos.length > 0 ? this.undos[ this.undos.length - 1 ] : undefined;	// next cmd to pop

		if ( cmd === undefined || id > cmd.id ) {

			cmd = this.redo();
			while ( cmd !== undefined && id > cmd.id ) {

				cmd = this.redo();

			}

		} else {

			while ( true ) {

				cmd = this.undos[ this.undos.length - 1 ];	// next cmd to pop

				if ( cmd === undefined || id === cmd.id ) break;

				this.undo();

			}

		}

		this.editor.signals.sceneGraphChanged.active = true;
		this.editor.signals.historyChanged.active = true;

		this.editor.signals.sceneGraphChanged.dispatch();
		this.editor.signals.historyChanged.dispatch( cmd );

	}

	enableSerialization( id ) {

		/**
		 * because there might be commands in this.undos and this.redos
		 * which have not been serialized with .toJSON() we go back
		 * to the oldest command and redo one command after the other
		 * while also calling .toJSON() on them.
		 */

		this.goToState( - 1 );

		this.editor.signals.sceneGraphChanged.active = false;
		this.editor.signals.historyChanged.active = false;

		let cmd = this.redo();
		while ( cmd !== undefined ) {

			if ( ! cmd.hasOwnProperty( 'json' ) ) {

				cmd.json = cmd.toJSON();

			}

			cmd = this.redo();

		}

		this.editor.signals.sceneGraphChanged.active = true;
		this.editor.signals.historyChanged.active = true;

		this.goToState( id );

	}

}
```
</details>

#### Methods

##### `execute(cmd: any, optionalName: any): void`

<details><summary>Code</summary>

```ts
execute( cmd, optionalName ) {

		const lastCmd = this.undos[ this.undos.length - 1 ];
		const timeDifference = Date.now() - this.lastCmdTime;

		const isUpdatableCmd = lastCmd &&
			lastCmd.updatable &&
			cmd.updatable &&
			lastCmd.object === cmd.object &&
			lastCmd.type === cmd.type &&
			lastCmd.script === cmd.script &&
			lastCmd.attributeName === cmd.attributeName;

		if ( isUpdatableCmd && cmd.type === 'SetScriptValueCommand' ) {

			// When the cmd.type is "SetScriptValueCommand" the timeDifference is ignored

			lastCmd.update( cmd );
			cmd = lastCmd;

		} else if ( isUpdatableCmd && timeDifference < 500 ) {

			lastCmd.update( cmd );
			cmd = lastCmd;

		} else {

			// the command is not updatable and is added as a new part of the history

			this.undos.push( cmd );
			cmd.id = ++ this.idCounter;

		}

		cmd.name = ( optionalName !== undefined ) ? optionalName : cmd.name;
		cmd.execute();
		cmd.inMemory = true;

		if ( this.config.getKey( 'settings/history' ) ) {

			cmd.json = cmd.toJSON();	// serialize the cmd immediately after execution and append the json to the cmd

		}

		this.lastCmdTime = Date.now();

		// clearing all the redo-commands

		this.redos = [];
		this.editor.signals.historyChanged.dispatch( cmd );

	}
```
</details>

##### `undo(): any`

<details><summary>Code</summary>

```ts
undo() {

		if ( this.historyDisabled ) {

			alert( this.editor.strings.getKey( 'prompt/history/forbid' ) );
			return;

		}

		let cmd = undefined;

		if ( this.undos.length > 0 ) {

			cmd = this.undos.pop();

			if ( cmd.inMemory === false ) {

				cmd.fromJSON( cmd.json );

			}

		}

		if ( cmd !== undefined ) {

			cmd.undo();
			this.redos.push( cmd );
			this.editor.signals.historyChanged.dispatch( cmd );

		}

		return cmd;

	}
```
</details>

##### `redo(): any`

<details><summary>Code</summary>

```ts
redo() {

		if ( this.historyDisabled ) {

			alert( this.editor.strings.getKey( 'prompt/history/forbid' ) );
			return;

		}

		let cmd = undefined;

		if ( this.redos.length > 0 ) {

			cmd = this.redos.pop();

			if ( cmd.inMemory === false ) {

				cmd.fromJSON( cmd.json );

			}

		}

		if ( cmd !== undefined ) {

			cmd.execute();
			this.undos.push( cmd );
			this.editor.signals.historyChanged.dispatch( cmd );

		}

		return cmd;

	}
```
</details>

##### `toJSON(): { undos: any[]; redos: any[]; }`

<details><summary>Code</summary>

```ts
toJSON() {

		const history = {};
		history.undos = [];
		history.redos = [];

		if ( ! this.config.getKey( 'settings/history' ) ) {

			return history;

		}

		// Append Undos to History

		for ( let i = 0; i < this.undos.length; i ++ ) {

			if ( this.undos[ i ].hasOwnProperty( 'json' ) ) {

				history.undos.push( this.undos[ i ].json );

			}

		}

		// Append Redos to History

		for ( let i = 0; i < this.redos.length; i ++ ) {

			if ( this.redos[ i ].hasOwnProperty( 'json' ) ) {

				history.redos.push( this.redos[ i ].json );

			}

		}

		return history;

	}
```
</details>

##### `fromJSON(json: any): void`

<details><summary>Code</summary>

```ts
fromJSON( json ) {

		if ( json === undefined ) return;

		for ( let i = 0; i < json.undos.length; i ++ ) {

			const cmdJSON = json.undos[ i ];
			const cmd = new Commands[ cmdJSON.type ]( this.editor ); // creates a new object of type "json.type"
			cmd.json = cmdJSON;
			cmd.id = cmdJSON.id;
			cmd.name = cmdJSON.name;
			this.undos.push( cmd );
			this.idCounter = ( cmdJSON.id > this.idCounter ) ? cmdJSON.id : this.idCounter; // set last used idCounter

		}

		for ( let i = 0; i < json.redos.length; i ++ ) {

			const cmdJSON = json.redos[ i ];
			const cmd = new Commands[ cmdJSON.type ]( this.editor ); // creates a new object of type "json.type"
			cmd.json = cmdJSON;
			cmd.id = cmdJSON.id;
			cmd.name = cmdJSON.name;
			this.redos.push( cmd );
			this.idCounter = ( cmdJSON.id > this.idCounter ) ? cmdJSON.id : this.idCounter; // set last used idCounter

		}

		// Select the last executed undo-command
		this.editor.signals.historyChanged.dispatch( this.undos[ this.undos.length - 1 ] );

	}
```
</details>

##### `clear(): void`

<details><summary>Code</summary>

```ts
clear() {

		this.undos = [];
		this.redos = [];
		this.idCounter = 0;

		this.editor.signals.historyChanged.dispatch();

	}
```
</details>

##### `goToState(id: any): void`

<details><summary>Code</summary>

```ts
goToState( id ) {

		if ( this.historyDisabled ) {

			alert( this.editor.strings.getKey( 'prompt/history/forbid' ) );
			return;

		}

		this.editor.signals.sceneGraphChanged.active = false;
		this.editor.signals.historyChanged.active = false;

		let cmd = this.undos.length > 0 ? this.undos[ this.undos.length - 1 ] : undefined;	// next cmd to pop

		if ( cmd === undefined || id > cmd.id ) {

			cmd = this.redo();
			while ( cmd !== undefined && id > cmd.id ) {

				cmd = this.redo();

			}

		} else {

			while ( true ) {

				cmd = this.undos[ this.undos.length - 1 ];	// next cmd to pop

				if ( cmd === undefined || id === cmd.id ) break;

				this.undo();

			}

		}

		this.editor.signals.sceneGraphChanged.active = true;
		this.editor.signals.historyChanged.active = true;

		this.editor.signals.sceneGraphChanged.dispatch();
		this.editor.signals.historyChanged.dispatch( cmd );

	}
```
</details>

##### `enableSerialization(id: any): void`

<details><summary>Code</summary>

```ts
enableSerialization( id ) {

		/**
		 * because there might be commands in this.undos and this.redos
		 * which have not been serialized with .toJSON() we go back
		 * to the oldest command and redo one command after the other
		 * while also calling .toJSON() on them.
		 */

		this.goToState( - 1 );

		this.editor.signals.sceneGraphChanged.active = false;
		this.editor.signals.historyChanged.active = false;

		let cmd = this.redo();
		while ( cmd !== undefined ) {

			if ( ! cmd.hasOwnProperty( 'json' ) ) {

				cmd.json = cmd.toJSON();

			}

			cmd = this.redo();

		}

		this.editor.signals.sceneGraphChanged.active = true;
		this.editor.signals.historyChanged.active = true;

		this.goToState( id );

	}
```
</details>


---