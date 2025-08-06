[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SetUuidCommand.js`

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
📂 **`editor/js/commands/SetUuidCommand.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Command` | `../Command.js` |


---

## Functions

### `SetUuidCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.editor.signals.objectChanged.dispatch`
- `this.editor.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
execute() {

		this.object.uuid = this.newUuid;
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `SetUuidCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.editor.signals.objectChanged.dispatch`
- `this.editor.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		this.object.uuid = this.oldUuid;
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `SetUuidCommand.toJSON(): { type: string; id: number; name: string; }`

**Returns:** `{ type: string; id: number; name: string; }`

**Calls:**

- `super.toJSON`

<details><summary>Code</summary>

```typescript
toJSON() {

		const output = super.toJSON( this );

		output.oldUuid = this.oldUuid;
		output.newUuid = this.newUuid;

		return output;

	}
```
</details>

### `SetUuidCommand.fromJSON(json: any): void`

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

		this.oldUuid = json.oldUuid;
		this.newUuid = json.newUuid;
		this.object = this.editor.objectByUuid( json.oldUuid );

		if ( this.object === undefined ) {

			this.object = this.editor.objectByUuid( json.newUuid );

		}

	}
```
</details>


---

## Classes

### `SetUuidCommand`

<details><summary>Class Code</summary>

```ts
class SetUuidCommand extends Command {

	/**
	 * @param {Editor} editor
	 * @param {THREE.Object3D|null} object
	 * @param {string|null} newUuid
	 * @constructor
	 */
	constructor( editor, object = null, newUuid = null ) {

		super( editor );

		this.type = 'SetUuidCommand';
		this.name = editor.strings.getKey( 'command/SetUuid' );

		this.object = object;

		this.oldUuid = ( object !== null ) ? object.uuid : null;
		this.newUuid = newUuid;

	}

	execute() {

		this.object.uuid = this.newUuid;
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.sceneGraphChanged.dispatch();

	}

	undo() {

		this.object.uuid = this.oldUuid;
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.sceneGraphChanged.dispatch();

	}

	toJSON() {

		const output = super.toJSON( this );

		output.oldUuid = this.oldUuid;
		output.newUuid = this.newUuid;

		return output;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.oldUuid = json.oldUuid;
		this.newUuid = json.newUuid;
		this.object = this.editor.objectByUuid( json.oldUuid );

		if ( this.object === undefined ) {

			this.object = this.editor.objectByUuid( json.newUuid );

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

		this.object.uuid = this.newUuid;
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		this.object.uuid = this.oldUuid;
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

##### `toJSON(): { type: string; id: number; name: string; }`

<details><summary>Code</summary>

```ts
toJSON() {

		const output = super.toJSON( this );

		output.oldUuid = this.oldUuid;
		output.newUuid = this.newUuid;

		return output;

	}
```
</details>

##### `fromJSON(json: any): void`

<details><summary>Code</summary>

```ts
fromJSON( json ) {

		super.fromJSON( json );

		this.oldUuid = json.oldUuid;
		this.newUuid = json.newUuid;
		this.object = this.editor.objectByUuid( json.oldUuid );

		if ( this.object === undefined ) {

			this.object = this.editor.objectByUuid( json.newUuid );

		}

	}
```
</details>


---