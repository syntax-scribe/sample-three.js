[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Material.NumberProperty.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Material.NumberProperty.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UINumber` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `SetMaterialValueCommand` | `./commands/SetMaterialValueCommand.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `container` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `object` | `any` | let/var | `null` | ✗ |
| `materialSlot` | `any` | let/var | `null` | ✗ |
| `material` | `any` | let/var | `null` | ✗ |


---

## Functions

### `SidebarMaterialNumberProperty(editor: any, property: any, name: any, range: number[], precision: number): UIRow`

**Parameters:**

- **`editor`** `any`
- **`property`** `any`
- **`name`** `any`
- **`range`** `number[]`
- **`precision`** `number`

**Returns:** `UIRow`

**Calls:**

- `container.add`
- `new UIText( name ).setClass`
- `new UINumber().setWidth( '60px' ).setRange( range[ 0 ], range[ 1 ] ).setPrecision( precision ).onChange`
- `number.getValue`
- `editor.execute`
- `editor.getObjectMaterial`
- `number.setValue`
- `container.setDisplay`
- `signals.objectSelected.add`
- `signals.materialChanged.add`

**Internal Comments:**
```
// (x5)
```

<details><summary>Code</summary>

```typescript
function SidebarMaterialNumberProperty( editor, property, name, range = [ - Infinity, Infinity ], precision = 2 ) {

	const signals = editor.signals;

	const container = new UIRow();
	container.add( new UIText( name ).setClass( 'Label' ) );

	const number = new UINumber().setWidth( '60px' ).setRange( range[ 0 ], range[ 1 ] ).setPrecision( precision ).onChange( onChange );
	container.add( number );

	let object = null;
	let materialSlot = null;
	let material = null;

	function onChange() {

		if ( material[ property ] !== number.getValue() ) {

			editor.execute( new SetMaterialValueCommand( editor, object, property, number.getValue(), materialSlot ) );

		}

	}

	function update( currentObject, currentMaterialSlot = 0 ) {

		object = currentObject;
		materialSlot = currentMaterialSlot;

		if ( object === null ) return;
		if ( object.material === undefined ) return;

		material = editor.getObjectMaterial( object, materialSlot );

		if ( property in material ) {

			number.setValue( material[ property ] );
			container.setDisplay( '' );

		} else {

			container.setDisplay( 'none' );

		}

	}

	//

	signals.objectSelected.add( update );
	signals.materialChanged.add( update );

	return container;

}
```
</details>

### `onChange(): void`

**Returns:** `void`

**Calls:**

- `number.getValue`
- `editor.execute`

<details><summary>Code</summary>

```typescript
function onChange() {

		if ( material[ property ] !== number.getValue() ) {

			editor.execute( new SetMaterialValueCommand( editor, object, property, number.getValue(), materialSlot ) );

		}

	}
```
</details>

### `update(currentObject: any, currentMaterialSlot: number): void`

**Parameters:**

- **`currentObject`** `any`
- **`currentMaterialSlot`** `number`

**Returns:** `void`

**Calls:**

- `editor.getObjectMaterial`
- `number.setValue`
- `container.setDisplay`

<details><summary>Code</summary>

```typescript
function update( currentObject, currentMaterialSlot = 0 ) {

		object = currentObject;
		materialSlot = currentMaterialSlot;

		if ( object === null ) return;
		if ( object.material === undefined ) return;

		material = editor.getObjectMaterial( object, materialSlot );

		if ( property in material ) {

			number.setValue( material[ property ] );
			container.setDisplay( '' );

		} else {

			container.setDisplay( 'none' );

		}

	}
```
</details>


---