[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MoveObjectCommand.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/commands/MoveObjectCommand.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Command` | `../Command.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `children` | `any` | let/var | `this.newParent.children` | ✗ |
| `children` | `any` | let/var | `this.oldParent.children` | ✗ |


---

## Functions

### `MoveObjectCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.oldParent.remove`
- `children.splice`
- `this.object.dispatchEvent`
- `this.editor.signals.objectChanged.dispatch`
- `this.editor.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
execute() {

		this.oldParent.remove( this.object );

		const children = this.newParent.children;
		children.splice( this.newIndex, 0, this.object );
		this.object.parent = this.newParent;

		this.object.dispatchEvent( { type: 'added' } );
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.objectChanged.dispatch( this.newParent );
		this.editor.signals.objectChanged.dispatch( this.oldParent );
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `MoveObjectCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.newParent.remove`
- `children.splice`
- `this.object.dispatchEvent`
- `this.editor.signals.objectChanged.dispatch`
- `this.editor.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		this.newParent.remove( this.object );

		const children = this.oldParent.children;
		children.splice( this.oldIndex, 0, this.object );
		this.object.parent = this.oldParent;

		this.object.dispatchEvent( { type: 'added' } );
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.objectChanged.dispatch( this.newParent );
		this.editor.signals.objectChanged.dispatch( this.oldParent );
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `MoveObjectCommand.toJSON(): { type: string; id: number; name: string; }`

**Returns:** `{ type: string; id: number; name: string; }`

**Calls:**

- `super.toJSON`

<details><summary>Code</summary>

```typescript
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.newParentUuid = this.newParent.uuid;
		output.oldParentUuid = this.oldParent.uuid;
		output.newIndex = this.newIndex;
		output.oldIndex = this.oldIndex;

		return output;

	}
```
</details>

### `MoveObjectCommand.fromJSON(json: any): void`

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
		this.oldParent = this.editor.objectByUuid( json.oldParentUuid );
		if ( this.oldParent === undefined ) {

			this.oldParent = this.editor.scene;

		}

		this.newParent = this.editor.objectByUuid( json.newParentUuid );

		if ( this.newParent === undefined ) {

			this.newParent = this.editor.scene;

		}

		this.newIndex = json.newIndex;
		this.oldIndex = json.oldIndex;

	}
```
</details>


---

## Classes

### `MoveObjectCommand`

<details><summary>Class Code</summary>

```ts
class MoveObjectCommand extends Command {

	/**
	 * @param {Editor} editor
	 * @param {THREE.Object3D|null} [object=null]
	 * @param {THREE.Object3D|null} [newParent=null]
	 * @param {THREE.Object3D|null} [newBefore=null]
	 * @constructor
	 */
	constructor( editor, object = null, newParent = null, newBefore = null ) {

		super( editor );

		this.type = 'MoveObjectCommand';
		this.name = editor.strings.getKey( 'command/MoveObject' );

		this.object = object;
		this.oldParent = ( object !== null ) ? object.parent : null;
		this.oldIndex = ( this.oldParent !== null ) ? this.oldParent.children.indexOf( this.object ) : null;
		this.newParent = newParent;

		if ( newBefore !== null ) {

			this.newIndex = ( newParent !== null ) ? newParent.children.indexOf( newBefore ) : null;

		} else {

			this.newIndex = ( newParent !== null ) ? newParent.children.length : null;

		}

		if ( this.oldParent === this.newParent && this.newIndex > this.oldIndex ) {

			this.newIndex --;

		}

		this.newBefore = newBefore;

	}

	execute() {

		this.oldParent.remove( this.object );

		const children = this.newParent.children;
		children.splice( this.newIndex, 0, this.object );
		this.object.parent = this.newParent;

		this.object.dispatchEvent( { type: 'added' } );
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.objectChanged.dispatch( this.newParent );
		this.editor.signals.objectChanged.dispatch( this.oldParent );
		this.editor.signals.sceneGraphChanged.dispatch();

	}

	undo() {

		this.newParent.remove( this.object );

		const children = this.oldParent.children;
		children.splice( this.oldIndex, 0, this.object );
		this.object.parent = this.oldParent;

		this.object.dispatchEvent( { type: 'added' } );
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.objectChanged.dispatch( this.newParent );
		this.editor.signals.objectChanged.dispatch( this.oldParent );
		this.editor.signals.sceneGraphChanged.dispatch();

	}

	toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.newParentUuid = this.newParent.uuid;
		output.oldParentUuid = this.oldParent.uuid;
		output.newIndex = this.newIndex;
		output.oldIndex = this.oldIndex;

		return output;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.objectUuid );
		this.oldParent = this.editor.objectByUuid( json.oldParentUuid );
		if ( this.oldParent === undefined ) {

			this.oldParent = this.editor.scene;

		}

		this.newParent = this.editor.objectByUuid( json.newParentUuid );

		if ( this.newParent === undefined ) {

			this.newParent = this.editor.scene;

		}

		this.newIndex = json.newIndex;
		this.oldIndex = json.oldIndex;

	}

}
```
</details>

#### Methods

##### `execute(): void`

<details><summary>Code</summary>

```ts
execute() {

		this.oldParent.remove( this.object );

		const children = this.newParent.children;
		children.splice( this.newIndex, 0, this.object );
		this.object.parent = this.newParent;

		this.object.dispatchEvent( { type: 'added' } );
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.objectChanged.dispatch( this.newParent );
		this.editor.signals.objectChanged.dispatch( this.oldParent );
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		this.newParent.remove( this.object );

		const children = this.oldParent.children;
		children.splice( this.oldIndex, 0, this.object );
		this.object.parent = this.oldParent;

		this.object.dispatchEvent( { type: 'added' } );
		this.editor.signals.objectChanged.dispatch( this.object );
		this.editor.signals.objectChanged.dispatch( this.newParent );
		this.editor.signals.objectChanged.dispatch( this.oldParent );
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
		output.newParentUuid = this.newParent.uuid;
		output.oldParentUuid = this.oldParent.uuid;
		output.newIndex = this.newIndex;
		output.oldIndex = this.oldIndex;

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
		this.oldParent = this.editor.objectByUuid( json.oldParentUuid );
		if ( this.oldParent === undefined ) {

			this.oldParent = this.editor.scene;

		}

		this.newParent = this.editor.objectByUuid( json.newParentUuid );

		if ( this.newParent === undefined ) {

			this.newParent = this.editor.scene;

		}

		this.newIndex = json.newIndex;
		this.oldIndex = json.oldIndex;

	}
```
</details>


---