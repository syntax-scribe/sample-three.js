[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SetMaterialRangeCommand.js`

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
📂 **`editor/js/commands/SetMaterialRangeCommand.js`**

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

### `SetMaterialRangeCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.editor.getObjectMaterial`
- `this.editor.signals.objectChanged.dispatch`
- `this.editor.signals.materialChanged.dispatch`

<details><summary>Code</summary>

```typescript
execute() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.attributeName ] = [ ...this.newRange ];
		material.needsUpdate = true;

		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

### `SetMaterialRangeCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.editor.getObjectMaterial`
- `this.editor.signals.objectChanged.dispatch`
- `this.editor.signals.materialChanged.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.attributeName ] = [ ...this.oldRange ];
		material.needsUpdate = true;

		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

### `SetMaterialRangeCommand.update(cmd: any): void`

**Parameters:**

- **`cmd`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
update( cmd ) {

		this.newRange = [ ...cmd.newRange ];

	}
```
</details>

### `SetMaterialRangeCommand.toJSON(): { type: string; id: number; name: string; }`

**Returns:** `{ type: string; id: number; name: string; }`

**Calls:**

- `super.toJSON`

<details><summary>Code</summary>

```typescript
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.attributeName = this.attributeName;
		output.oldRange = [ ...this.oldRange ];
		output.newRange = [ ...this.newRange ];
		output.materialSlot = this.materialSlot;

		return output;

	}
```
</details>

### `SetMaterialRangeCommand.fromJSON(json: any): void`

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

		this.attributeName = json.attributeName;
		this.oldRange = [ ...json.oldRange ];
		this.newRange = [ ...json.newRange ];
		this.object = this.editor.objectByUuid( json.objectUuid );
		this.materialSlot = json.materialSlot;

	}
```
</details>


---

## Classes

### `SetMaterialRangeCommand`

<details><summary>Class Code</summary>

```ts
class SetMaterialRangeCommand extends Command {

	/**
	 * @param {Editor} editor
	 * @param {THREE.Object3D|null} [object=null]
	 * @param {string} [attributeName='']
	 * @param {number} [newMinValue=-Infinity]
	 * @param {number} [newMaxValue=Infinity]
	 * @param {number} [materialSlot=-1]
	 * @constructor
	 */
	constructor( editor, object = null, attributeName = '', newMinValue = - Infinity, newMaxValue = Infinity, materialSlot = - 1 ) {

		super( editor );

		this.type = 'SetMaterialRangeCommand';
		this.name = editor.strings.getKey( 'command/SetMaterialRange' ) + ': ' + attributeName;
		this.updatable = true;

		this.object = object;
		this.materialSlot = materialSlot;

		const material = ( object !== null ) ? editor.getObjectMaterial( object, materialSlot ) : null;

		this.oldRange = ( material !== null && material[ attributeName ] !== undefined ) ? [ ...this.material[ attributeName ] ] : null;
		this.newRange = [ newMinValue, newMaxValue ];

		this.attributeName = attributeName;

	}

	execute() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.attributeName ] = [ ...this.newRange ];
		material.needsUpdate = true;

		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}

	undo() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.attributeName ] = [ ...this.oldRange ];
		material.needsUpdate = true;

		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}

	update( cmd ) {

		this.newRange = [ ...cmd.newRange ];

	}

	toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.attributeName = this.attributeName;
		output.oldRange = [ ...this.oldRange ];
		output.newRange = [ ...this.newRange ];
		output.materialSlot = this.materialSlot;

		return output;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.attributeName = json.attributeName;
		this.oldRange = [ ...json.oldRange ];
		this.newRange = [ ...json.newRange ];
		this.object = this.editor.objectByUuid( json.objectUuid );
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

		material[ this.attributeName ] = [ ...this.newRange ];
		material.needsUpdate = true;

		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		const material = this.editor.getObjectMaterial( this.object, this.materialSlot );

		material[ this.attributeName ] = [ ...this.oldRange ];
		material.needsUpdate = true;

		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

##### `update(cmd: any): void`

<details><summary>Code</summary>

```ts
update( cmd ) {

		this.newRange = [ ...cmd.newRange ];

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
		output.oldRange = [ ...this.oldRange ];
		output.newRange = [ ...this.newRange ];
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

		this.attributeName = json.attributeName;
		this.oldRange = [ ...json.oldRange ];
		this.newRange = [ ...json.newRange ];
		this.object = this.editor.objectByUuid( json.objectUuid );
		this.materialSlot = json.materialSlot;

	}
```
</details>


---