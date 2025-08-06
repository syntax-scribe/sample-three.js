[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SetGeometryValueCommand.js`

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
📂 **`editor/js/commands/SetGeometryValueCommand.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Command` | `../Command.js` |


---

## Functions

### `SetGeometryValueCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.editor.signals.objectChanged.dispatch`
- `this.editor.signals.geometryChanged.dispatch`
- `this.editor.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
execute() {

		this.object.geometry[ this.attributeName ] = this.newValue;
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.geometryChanged.dispatch();
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `SetGeometryValueCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.editor.signals.objectChanged.dispatch`
- `this.editor.signals.geometryChanged.dispatch`
- `this.editor.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		this.object.geometry[ this.attributeName ] = this.oldValue;
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.geometryChanged.dispatch();
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `SetGeometryValueCommand.toJSON(): { type: string; id: number; name: string; }`

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

### `SetGeometryValueCommand.fromJSON(json: any): void`

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

### `SetGeometryValueCommand`

<details><summary>Class Code</summary>

```ts
class SetGeometryValueCommand extends Command {

	/**
	 * @param {Editor} editor
	 * @param {THREE.Object3D|null} [object=null]
	 * @param {string} [attributeName='']
	 * @param {number|string|boolean|Object|null} [newValue=null]
	 * @constructor
	 */
	constructor( editor, object = null, attributeName = '', newValue = null ) {

		super( editor );

		this.type = 'SetGeometryValueCommand';
		this.name = editor.strings.getKey( 'command/SetGeometryValue' ) + ': ' + attributeName;

		this.object = object;
		this.attributeName = attributeName;
		this.oldValue = ( object !== null ) ? object.geometry[ attributeName ] : null;
		this.newValue = newValue;

	}

	execute() {

		this.object.geometry[ this.attributeName ] = this.newValue;
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.geometryChanged.dispatch();
		this.editor.signals.sceneGraphChanged.dispatch();

	}

	undo() {

		this.object.geometry[ this.attributeName ] = this.oldValue;
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.geometryChanged.dispatch();
		this.editor.signals.sceneGraphChanged.dispatch();

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

		this.object.geometry[ this.attributeName ] = this.newValue;
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.geometryChanged.dispatch();
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		this.object.geometry[ this.attributeName ] = this.oldValue;
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.geometryChanged.dispatch();
		this.editor.signals.sceneGraphChanged.dispatch();

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