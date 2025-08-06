[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SetRotationCommand.js`

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
📂 **`editor/js/commands/SetRotationCommand.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Command` | `../Command.js` |
| `Euler` | `three` |


---

## Functions

### `SetRotationCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.object.rotation.copy`
- `this.object.updateMatrixWorld`
- `this.editor.signals.objectChanged.dispatch`

<details><summary>Code</summary>

```typescript
execute() {

		this.object.rotation.copy( this.newRotation );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

### `SetRotationCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.object.rotation.copy`
- `this.object.updateMatrixWorld`
- `this.editor.signals.objectChanged.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		this.object.rotation.copy( this.oldRotation );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

### `SetRotationCommand.update(command: any): void`

**Parameters:**

- **`command`** `any`

**Returns:** `void`

**Calls:**

- `this.newRotation.copy`

<details><summary>Code</summary>

```typescript
update( command ) {

		this.newRotation.copy( command.newRotation );

	}
```
</details>

### `SetRotationCommand.toJSON(): { type: string; id: number; name: string; }`

**Returns:** `{ type: string; id: number; name: string; }`

**Calls:**

- `super.toJSON`
- `this.oldRotation.toArray`
- `this.newRotation.toArray`

<details><summary>Code</summary>

```typescript
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.oldRotation = this.oldRotation.toArray();
		output.newRotation = this.newRotation.toArray();

		return output;

	}
```
</details>

### `SetRotationCommand.fromJSON(json: any): void`

**Parameters:**

- **`json`** `any`

**Returns:** `void`

**Calls:**

- `super.fromJSON`
- `this.editor.objectByUuid`
- `new Euler().fromArray`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.objectUuid );
		this.oldRotation = new Euler().fromArray( json.oldRotation );
		this.newRotation = new Euler().fromArray( json.newRotation );

	}
```
</details>


---

## Classes

### `SetRotationCommand`

<details><summary>Class Code</summary>

```ts
class SetRotationCommand extends Command {

	/**
	 * @param {Editor} editor
	 * @param {THREE.Object3D|null} object
	 * @param {THREE.Euler|null} newRotation
	 * @param {THREE.Euler|null} optionalOldRotation
	 * @constructor
	 */
	constructor( editor, object = null, newRotation = null, optionalOldRotation = null ) {

		super( editor );

		this.type = 'SetRotationCommand';
		this.name = editor.strings.getKey( 'command/SetRotation' );
		this.updatable = true;

		this.object = object;

		if ( object !== null && newRotation !== null ) {

			this.oldRotation = object.rotation.clone();
			this.newRotation = newRotation.clone();

		}

		if ( optionalOldRotation !== null ) {

			this.oldRotation = optionalOldRotation.clone();

		}

	}

	execute() {

		this.object.rotation.copy( this.newRotation );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}

	undo() {

		this.object.rotation.copy( this.oldRotation );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}

	update( command ) {

		this.newRotation.copy( command.newRotation );

	}

	toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.oldRotation = this.oldRotation.toArray();
		output.newRotation = this.newRotation.toArray();

		return output;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.objectUuid );
		this.oldRotation = new Euler().fromArray( json.oldRotation );
		this.newRotation = new Euler().fromArray( json.newRotation );

	}

}
```
</details>

#### Methods

##### `execute(): void`

<details><summary>Code</summary>

```ts
execute() {

		this.object.rotation.copy( this.newRotation );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		this.object.rotation.copy( this.oldRotation );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

##### `update(command: any): void`

<details><summary>Code</summary>

```ts
update( command ) {

		this.newRotation.copy( command.newRotation );

	}
```
</details>

##### `toJSON(): { type: string; id: number; name: string; }`

<details><summary>Code</summary>

```ts
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.oldRotation = this.oldRotation.toArray();
		output.newRotation = this.newRotation.toArray();

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
		this.oldRotation = new Euler().fromArray( json.oldRotation );
		this.newRotation = new Euler().fromArray( json.newRotation );

	}
```
</details>


---