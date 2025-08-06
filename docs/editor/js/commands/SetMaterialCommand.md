[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SetMaterialCommand.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/commands/SetMaterialCommand.js`**

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

### `SetMaterialCommand.execute(): void`

**Returns:** `void`

**Calls:**

- `this.editor.setObjectMaterial`
- `this.editor.signals.materialChanged.dispatch`

<details><summary>Code</summary>

```typescript
execute() {

		this.editor.setObjectMaterial( this.object, this.materialSlot, this.newMaterial );

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

### `SetMaterialCommand.undo(): void`

**Returns:** `void`

**Calls:**

- `this.editor.setObjectMaterial`
- `this.editor.signals.materialChanged.dispatch`

<details><summary>Code</summary>

```typescript
undo() {

		this.editor.setObjectMaterial( this.object, this.materialSlot, this.oldMaterial );

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

### `SetMaterialCommand.toJSON(): { type: string; id: number; name: string; }`

**Returns:** `{ type: string; id: number; name: string; }`

**Calls:**

- `super.toJSON`
- `this.oldMaterial.toJSON`
- `this.newMaterial.toJSON`

<details><summary>Code</summary>

```typescript
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.oldMaterial = this.oldMaterial.toJSON();
		output.newMaterial = this.newMaterial.toJSON();
		output.materialSlot = this.materialSlot;

		return output;

	}
```
</details>

### `SetMaterialCommand.fromJSON(json: any): void`

**Parameters:**

- **`json`** `any`

**Returns:** `void`

**Calls:**

- `super.fromJSON`
- `this.editor.objectByUuid`
- `parseMaterial`
- `loader.parseImages`
- `loader.parseTextures`
- `loader.parseMaterials`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.objectUuid );
		this.oldMaterial = parseMaterial( json.oldMaterial );
		this.newMaterial = parseMaterial( json.newMaterial );
		this.materialSlot = json.materialSlot;

		function parseMaterial( json ) {

			const loader = new ObjectLoader();
			const images = loader.parseImages( json.images );
			const textures = loader.parseTextures( json.textures, images );
			const materials = loader.parseMaterials( [ json ], textures );
			return materials[ json.uuid ];

		}

	}
```
</details>

### `parseMaterial(json: any): any`

**Parameters:**

- **`json`** `any`

**Returns:** `any`

**Calls:**

- `loader.parseImages`
- `loader.parseTextures`
- `loader.parseMaterials`

<details><summary>Code</summary>

```typescript
function parseMaterial( json ) {

			const loader = new ObjectLoader();
			const images = loader.parseImages( json.images );
			const textures = loader.parseTextures( json.textures, images );
			const materials = loader.parseMaterials( [ json ], textures );
			return materials[ json.uuid ];

		}
```
</details>


---

## Classes

### `SetMaterialCommand`

<details><summary>Class Code</summary>

```ts
class SetMaterialCommand extends Command {

	/**
	 * @param {Editor} editor
	 * @param {THREE.Object3D|null} object
	 * @param {THREE.Material|null} newMaterial
	 * @param {number} [materialSlot=-1]
	 * @constructor
	 */
	constructor( editor, object = null, newMaterial = null, materialSlot = - 1 ) {

		super( editor );

		this.type = 'SetMaterialCommand';
		this.name = editor.strings.getKey( 'command/SetMaterial' );

		this.object = object;
		this.materialSlot = materialSlot;

		this.oldMaterial = ( object !== null ) ? editor.getObjectMaterial( object, materialSlot ) : null;
		this.newMaterial = newMaterial;

	}

	execute() {

		this.editor.setObjectMaterial( this.object, this.materialSlot, this.newMaterial );

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}

	undo() {

		this.editor.setObjectMaterial( this.object, this.materialSlot, this.oldMaterial );

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}

	toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.oldMaterial = this.oldMaterial.toJSON();
		output.newMaterial = this.newMaterial.toJSON();
		output.materialSlot = this.materialSlot;

		return output;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.object = this.editor.objectByUuid( json.objectUuid );
		this.oldMaterial = parseMaterial( json.oldMaterial );
		this.newMaterial = parseMaterial( json.newMaterial );
		this.materialSlot = json.materialSlot;

		function parseMaterial( json ) {

			const loader = new ObjectLoader();
			const images = loader.parseImages( json.images );
			const textures = loader.parseTextures( json.textures, images );
			const materials = loader.parseMaterials( [ json ], textures );
			return materials[ json.uuid ];

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

		this.editor.setObjectMaterial( this.object, this.materialSlot, this.newMaterial );

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

##### `undo(): void`

<details><summary>Code</summary>

```ts
undo() {

		this.editor.setObjectMaterial( this.object, this.materialSlot, this.oldMaterial );

		this.editor.signals.materialChanged.dispatch( this.object, this.materialSlot );

	}
```
</details>

##### `toJSON(): { type: string; id: number; name: string; }`

<details><summary>Code</summary>

```ts
toJSON() {

		const output = super.toJSON( this );

		output.objectUuid = this.object.uuid;
		output.oldMaterial = this.oldMaterial.toJSON();
		output.newMaterial = this.newMaterial.toJSON();
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
		this.oldMaterial = parseMaterial( json.oldMaterial );
		this.newMaterial = parseMaterial( json.newMaterial );
		this.materialSlot = json.materialSlot;

		function parseMaterial( json ) {

			const loader = new ObjectLoader();
			const images = loader.parseImages( json.images );
			const textures = loader.parseTextures( json.textures, images );
			const materials = loader.parseMaterials( [ json ], textures );
			return materials[ json.uuid ];

		}

	}
```
</details>


---