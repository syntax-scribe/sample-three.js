[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SetMaterialVectorCommand.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/commands/SetMaterialVectorCommand.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Command` | `../Command.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `material` | `any` | let/var | `( object !== null ) ? editor.getObjectMaterial( object, materialSlot ) : null` | ✗ |


---

## Functions

### `SetMaterialVectorCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.editor.getObjectMaterial`
- `material[ this.attributeName ].fromArray`
- `this.editor.signals.materialChanged.dispatch`

<details><summary>Code</summary>

```typescript
execute() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.attributeName ].fromArray( this.newValue );

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

### `SetMaterialVectorCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.editor.getObjectMaterial`
- `material[ this.attributeName ].fromArray`
- `this.editor.signals.materialChanged.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.attributeName ].fromArray( this.oldValue );

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

### `SetMaterialVectorCommand.update(cmd: any): void`

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

### `SetMaterialVectorCommand.toJSON(): { type: string; id: number; name: string; }`

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
		output.materialSlot = this.materialSlot;

		return output;

	}
```
</details>

### `SetMaterialVectorCommand.fromJSON(json: any): void`

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
		this.materialSlot = json.materialSlot;

	}
```
</details>


---

## Classes

### `SetMaterialVectorCommand`

<details><summary>Class Code</summary>

```ts
class SetMaterialVectorCommand extends Command {

	/**
	 *
	 * @param {Editor} editor
	 * @param {THREE.Object3D|null} [object=null]
	 * @param {string} [attributeName='']
	 * @param {THREE.Vector2|THREE.Vector3|THREE.Vector4|null} [newValue=null]
	 * @param {number} [materialSlot=-1]
	 * @constructor
	 */
	constructor( editor, object = null, attributeName = '', newValue = null, materialSlot = - 1 ) {

		super( editor );

		this.type = 'SetMaterialVectorCommand';
		this.name = editor.strings.getKey( 'command/SetMaterialVector' ) + ': ' + attributeName;
		this.updatable = true;

		this.object = object;
		this.materialSlot = materialSlot;

		const material = ( object !== null ) ? editor.getObjectMaterial( object, materialSlot ) : null;

		this.oldValue = ( material !== null ) ? material[ attributeName ].toArray() : null;
		this.newValue = newValue;

		this.attributeName = attributeName;

	}

	execute() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.attributeName ].fromArray( this.newValue );

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}

	undo() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.attributeName ].fromArray( this.oldValue );

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

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
		output.materialSlot = this.materialSlot;

		return output;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.objectUuid );
		this.attributeName = json.attributeName;
		this.oldValue = json.oldValue;
		this.newValue = json.newValue;
		this.materialSlot = json.materialSlot;

	}

}
```
</details>

#### Methods

##### `execute(): void`

<details><summary>Code</summary>

```ts
execute() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.attributeName ].fromArray( this.newValue );

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.attributeName ].fromArray( this.oldValue );

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

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
		output.materialSlot = this.materialSlot;

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
		this.materialSlot = json.materialSlot;

	}
```
</details>


---