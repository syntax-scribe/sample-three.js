[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SetPositionCommand.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/commands/SetPositionCommand.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Command` | `../Command.js` |
| `Vector3` | `three` |


---

## Functions

### `SetPositionCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.object.position.copy`
- `this.object.updateMatrixWorld`
- `this.editor.signals.objectChanged.dispatch`

<details><summary>Code</summary>

```typescript
execute() {

		this.object.position.copy( this.newPosition );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

### `SetPositionCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.object.position.copy`
- `this.object.updateMatrixWorld`
- `this.editor.signals.objectChanged.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		this.object.position.copy( this.oldPosition );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

### `SetPositionCommand.update(command: any): void`

**Parameters:**

- **`command`** `any`

**Returns:** `void`

**Calls:**

- `this.newPosition.copy`

<details><summary>Code</summary>

```typescript
update( command ) {

		this.newPosition.copy( command.newPosition );

	}
```
</details>

### `SetPositionCommand.toJSON(): { type: string; id: number; name: string; }`

**Returns:** `{ type: string; id: number; name: string; }`

**Calls:**

- `super.toJSON`
- `this.oldPosition.toArray`
- `this.newPosition.toArray`

<details><summary>Code</summary>

```typescript
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.oldPosition = this.oldPosition.toArray();
		output.newPosition = this.newPosition.toArray();

		return output;

	}
```
</details>

### `SetPositionCommand.fromJSON(json: any): void`

**Parameters:**

- **`json`** `any`

**Returns:** `void`

**Calls:**

- `super.fromJSON`
- `this.editor.objectByUuid`
- `new Vector3().fromArray`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.objectUuid );
		this.oldPosition = new Vector3().fromArray( json.oldPosition );
		this.newPosition = new Vector3().fromArray( json.newPosition );

	}
```
</details>


---

## Classes

### `SetPositionCommand`

<details><summary>Class Code</summary>

```ts
class SetPositionCommand extends Command {

	/**
	 * @param {Editor} editor
	 * @param {THREE.Object3D|null} object
	 * @param {THREE.Vector3|null} newPosition
	 * @param {THREE.Vector3|null} optionalOldPosition
	 * @constructor
	 */
	constructor( editor, object = null, newPosition = null, optionalOldPosition = null ) {

		super( editor );

		this.type = 'SetPositionCommand';
		this.name = editor.strings.getKey( 'command/SetPosition' );
		this.updatable = true;

		this.object = object;

		if ( object !== null && newPosition !== null ) {

			this.oldPosition = object.position.clone();
			this.newPosition = newPosition.clone();

		}

		if ( optionalOldPosition !== null ) {

			this.oldPosition = optionalOldPosition.clone();

		}

	}

	execute() {

		this.object.position.copy( this.newPosition );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}

	undo() {

		this.object.position.copy( this.oldPosition );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}

	update( command ) {

		this.newPosition.copy( command.newPosition );

	}

	toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.oldPosition = this.oldPosition.toArray();
		output.newPosition = this.newPosition.toArray();

		return output;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.objectUuid );
		this.oldPosition = new Vector3().fromArray( json.oldPosition );
		this.newPosition = new Vector3().fromArray( json.newPosition );

	}

}
```
</details>

#### Methods

##### `execute(): void`

<details><summary>Code</summary>

```ts
execute() {

		this.object.position.copy( this.newPosition );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		this.object.position.copy( this.oldPosition );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

##### `update(command: any): void`

<details><summary>Code</summary>

```ts
update( command ) {

		this.newPosition.copy( command.newPosition );

	}
```
</details>

##### `toJSON(): { type: string; id: number; name: string; }`

<details><summary>Code</summary>

```ts
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.oldPosition = this.oldPosition.toArray();
		output.newPosition = this.newPosition.toArray();

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
		this.oldPosition = new Vector3().fromArray( json.oldPosition );
		this.newPosition = new Vector3().fromArray( json.newPosition );

	}
```
</details>


---