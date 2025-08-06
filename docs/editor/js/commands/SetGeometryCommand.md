[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SetGeometryCommand.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/commands/SetGeometryCommand.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Command` | `../Command.js` |
| `ObjectLoader` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `loader` | `any` | let/var | `new ObjectLoader()` | ✗ |


---

## Functions

### `SetGeometryCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.object.geometry.dispose`
- `this.object.geometry.computeBoundingSphere`
- `this.editor.signals.geometryChanged.dispatch`
- `this.editor.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
execute() {

		this.object.geometry.dispose();
		this.object.geometry = this.newGeometry;
		this.object.geometry.computeBoundingSphere();

		this.editor.signals.geometryChanged.dispatch( this.object );
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `SetGeometryCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.object.geometry.dispose`
- `this.object.geometry.computeBoundingSphere`
- `this.editor.signals.geometryChanged.dispatch`
- `this.editor.signals.sceneGraphChanged.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		this.object.geometry.dispose();
		this.object.geometry = this.oldGeometry;
		this.object.geometry.computeBoundingSphere();

		this.editor.signals.geometryChanged.dispatch( this.object );
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

### `SetGeometryCommand.update(cmd: any): void`

**Parameters:**

- **`cmd`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
update( cmd ) {

		this.newGeometry = cmd.newGeometry;

	}
```
</details>

### `SetGeometryCommand.toJSON(): { type: string; id: number; name: string; }`

**Returns:** `{ type: string; id: number; name: string; }`

**Calls:**

- `super.toJSON`
- `this.oldGeometry.toJSON`
- `this.newGeometry.toJSON`

<details><summary>Code</summary>

```typescript
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.oldGeometry = this.oldGeometry.toJSON();
		output.newGeometry = this.newGeometry.toJSON();

		return output;

	}
```
</details>

### `SetGeometryCommand.fromJSON(json: any): void`

**Parameters:**

- **`json`** `any`

**Returns:** `void`

**Calls:**

- `super.fromJSON`
- `this.editor.objectByUuid`
- `parseGeometry`
- `loader.parseGeometries`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.objectUuid );

		this.oldGeometry = parseGeometry( json.oldGeometry );
		this.newGeometry = parseGeometry( json.newGeometry );

		function parseGeometry( data ) {

			const loader = new ObjectLoader();
			return loader.parseGeometries( [ data ] )[ data.uuid ];

		}

	}
```
</details>

### `parseGeometry(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `loader.parseGeometries`

<details><summary>Code</summary>

```typescript
function parseGeometry( data ) {

			const loader = new ObjectLoader();
			return loader.parseGeometries( [ data ] )[ data.uuid ];

		}
```
</details>


---

## Classes

### `SetGeometryCommand`

<details><summary>Class Code</summary>

```ts
class SetGeometryCommand extends Command {

	/**
	 * @param {Editor} editor
	 * @param {THREE.Object3D|null} [object=null]
	 * @param {THREE.Geometry|null} [newGeometry=null]
	 * @constructor
	 */
	constructor( editor, object = null, newGeometry = null ) {

		super( editor );

		this.type = 'SetGeometryCommand';
		this.name = editor.strings.getKey( 'command/SetGeometry' );
		this.updatable = true;

		this.object = object;
		this.oldGeometry = ( object !== null ) ? object.geometry : null;
		this.newGeometry = newGeometry;

	}

	execute() {

		this.object.geometry.dispose();
		this.object.geometry = this.newGeometry;
		this.object.geometry.computeBoundingSphere();

		this.editor.signals.geometryChanged.dispatch( this.object );
		this.editor.signals.sceneGraphChanged.dispatch();

	}

	undo() {

		this.object.geometry.dispose();
		this.object.geometry = this.oldGeometry;
		this.object.geometry.computeBoundingSphere();

		this.editor.signals.geometryChanged.dispatch( this.object );
		this.editor.signals.sceneGraphChanged.dispatch();

	}

	update( cmd ) {

		this.newGeometry = cmd.newGeometry;

	}

	toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.oldGeometry = this.oldGeometry.toJSON();
		output.newGeometry = this.newGeometry.toJSON();

		return output;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.objectUuid );

		this.oldGeometry = parseGeometry( json.oldGeometry );
		this.newGeometry = parseGeometry( json.newGeometry );

		function parseGeometry( data ) {

			const loader = new ObjectLoader();
			return loader.parseGeometries( [ data ] )[ data.uuid ];

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

		this.object.geometry.dispose();
		this.object.geometry = this.newGeometry;
		this.object.geometry.computeBoundingSphere();

		this.editor.signals.geometryChanged.dispatch( this.object );
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		this.object.geometry.dispose();
		this.object.geometry = this.oldGeometry;
		this.object.geometry.computeBoundingSphere();

		this.editor.signals.geometryChanged.dispatch( this.object );
		this.editor.signals.sceneGraphChanged.dispatch();

	}
```
</details>

##### `update(cmd: any): void`

<details><summary>Code</summary>

```ts
update( cmd ) {

		this.newGeometry = cmd.newGeometry;

	}
```
</details>

##### `toJSON(): { type: string; id: number; name: string; }`

<details><summary>Code</summary>

```ts
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.oldGeometry = this.oldGeometry.toJSON();
		output.newGeometry = this.newGeometry.toJSON();

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

		this.oldGeometry = parseGeometry( json.oldGeometry );
		this.newGeometry = parseGeometry( json.newGeometry );

		function parseGeometry( data ) {

			const loader = new ObjectLoader();
			return loader.parseGeometries( [ data ] )[ data.uuid ];

		}

	}
```
</details>


---