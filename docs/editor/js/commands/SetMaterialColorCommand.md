[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SetMaterialColorCommand.js`

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
📂 **`editor/js/commands/SetMaterialColorCommand.js`**

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

### `SetMaterialColorCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.editor.getObjectMaterial`
- `material[ this.attributeName ].setHex`
- `this.editor.signals.materialChanged.dispatch`

<details><summary>Code</summary>

```typescript
execute() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.attributeName ].setHex( this.newValue );

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

### `SetMaterialColorCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.editor.getObjectMaterial`
- `material[ this.attributeName ].setHex`
- `this.editor.signals.materialChanged.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.attributeName ].setHex( this.oldValue );

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

### `SetMaterialColorCommand.update(cmd: any): void`

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

### `SetMaterialColorCommand.toJSON(): { type: string; id: number; name: string; }`

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

### `SetMaterialColorCommand.fromJSON(json: any): void`

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

### `SetMaterialColorCommand`

<details><summary>Class Code</summary>

```ts
class SetMaterialColorCommand extends Command {

	/**
	 * @param {Editor} editor
	 * @param {THREE.Object3D|null} [object=null]
	 * @param {string} attributeName
	 * @param {?number} [newValue=null] Integer representing a hex color value
	 * @param {number} [materialSlot=-1]
	 * @constructor
	 */
	constructor( editor, object = null, attributeName = '', newValue = null, materialSlot = - 1 ) {

		super( editor );

		this.type = 'SetMaterialColorCommand';
		this.name = editor.strings.getKey( 'command/SetMaterialColor' ) + ': ' + attributeName;
		this.updatable = true;

		this.object = object;
		this.materialSlot = materialSlot;

		const material = ( object !== null ) ? editor.getObjectMaterial( object, materialSlot ) : null;

		this.oldValue = ( material !== null ) ? material[ attributeName ].getHex() : null;
		this.newValue = newValue;

		this.attributeName = attributeName;

	}

	execute() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.attributeName ].setHex( this.newValue );

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}

	undo() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.attributeName ].setHex( this.oldValue );

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

		material[ this.attributeName ].setHex( this.newValue );

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.attributeName ].setHex( this.oldValue );

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