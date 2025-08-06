[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SetScaleCommand.js`

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
📂 **`editor/js/commands/SetScaleCommand.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Command` | `../Command.js` |
| `Vector3` | `three` |


---

## Functions

### `SetScaleCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.object.scale.copy`
- `this.object.updateMatrixWorld`
- `this.editor.signals.objectChanged.dispatch`

<details><summary>Code</summary>

```typescript
execute() {

		this.object.scale.copy( this.newScale );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

### `SetScaleCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.object.scale.copy`
- `this.object.updateMatrixWorld`
- `this.editor.signals.objectChanged.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		this.object.scale.copy( this.oldScale );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

### `SetScaleCommand.update(command: any): void`

**Parameters:**

- **`command`** `any`

**Returns:** `void`

**Calls:**

- `this.newScale.copy`

<details><summary>Code</summary>

```typescript
update( command ) {

		this.newScale.copy( command.newScale );

	}
```
</details>

### `SetScaleCommand.toJSON(): { type: string; id: number; name: string; }`

**Returns:** `{ type: string; id: number; name: string; }`

**Calls:**

- `super.toJSON`
- `this.oldScale.toArray`
- `this.newScale.toArray`

<details><summary>Code</summary>

```typescript
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.oldScale = this.oldScale.toArray();
		output.newScale = this.newScale.toArray();

		return output;

	}
```
</details>

### `SetScaleCommand.fromJSON(json: any): void`

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
		this.oldScale = new Vector3().fromArray( json.oldScale );
		this.newScale = new Vector3().fromArray( json.newScale );

	}
```
</details>


---

## Classes

### `SetScaleCommand`

<details><summary>Class Code</summary>

```ts
class SetScaleCommand extends Command {

	/**
	 * @param {Editor} editor
	 * @param {THREE.Object3D|null} object
	 * @param {THREE.Vector3|null} newScale
	 * @param {THREE.Vector3|null} optionalOldScale
	 * @constructor
	 */
	constructor( editor, object = null, newScale = null, optionalOldScale = null ) {

		super( editor );

		this.type = 'SetScaleCommand';
		this.name = editor.strings.getKey( 'command/SetScale' );
		this.updatable = true;

		this.object = object;

		if ( object !== null && newScale !== null ) {

			this.oldScale = object.scale.clone();
			this.newScale = newScale.clone();

		}

		if ( optionalOldScale !== null ) {

			this.oldScale = optionalOldScale.clone();

		}

	}

	execute() {

		this.object.scale.copy( this.newScale );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}

	undo() {

		this.object.scale.copy( this.oldScale );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}

	update( command ) {

		this.newScale.copy( command.newScale );

	}

	toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.oldScale = this.oldScale.toArray();
		output.newScale = this.newScale.toArray();

		return output;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.objectUuid );
		this.oldScale = new Vector3().fromArray( json.oldScale );
		this.newScale = new Vector3().fromArray( json.newScale );

	}

}
```
</details>

#### Methods

##### `execute(): void`

<details><summary>Code</summary>

```ts
execute() {

		this.object.scale.copy( this.newScale );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		this.object.scale.copy( this.oldScale );
		this.object.updateMatrixWorld( true );
		this.editor.signals.objectChanged.dispatch( this.object );

	}
```
</details>

##### `update(command: any): void`

<details><summary>Code</summary>

```ts
update( command ) {

		this.newScale.copy( command.newScale );

	}
```
</details>

##### `toJSON(): { type: string; id: number; name: string; }`

<details><summary>Code</summary>

```ts
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.oldScale = this.oldScale.toArray();
		output.newScale = this.newScale.toArray();

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
		this.oldScale = new Vector3().fromArray( json.oldScale );
		this.newScale = new Vector3().fromArray( json.newScale );

	}
```
</details>


---