[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Material.ConstantProperty.js`

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
📂 **`editor/js/Sidebar.Material.ConstantProperty.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIRow` | `./libs/ui.js` |
| `UISelect` | `./libs/ui.js` |
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

### `SidebarMaterialConstantProperty(editor: any, property: any, name: any, options: any): UIRow`

**Parameters:**

- **`editor`** `any`
- **`property`** `any`
- **`name`** `any`
- **`options`** `any`

**Returns:** `UIRow`

**Calls:**

- `container.add`
- `new UIText( name ).setClass`
- `new UISelect().setOptions( options ).onChange`
- `parseInt`
- `constant.getValue`
- `editor.execute`
- `editor.getObjectMaterial`
- `constant.setValue`
- `container.setDisplay`
- `signals.objectSelected.add`
- `signals.materialChanged.add`

**Internal Comments:**
```
// (x5)
```

<details><summary>Code</summary>

```typescript
function SidebarMaterialConstantProperty( editor, property, name, options ) {

	const signals = editor.signals;

	const container = new UIRow();
	container.add( new UIText( name ).setClass( 'Label' ) );

	const constant = new UISelect().setOptions( options ).onChange( onChange );
	container.add( constant );

	let object = null;
	let materialSlot = null;
	let material = null;

	function onChange() {

		const value = parseInt( constant.getValue() );

		if ( material[ property ] !== value ) {

			editor.execute( new SetMaterialValueCommand( editor, object, property, value, materialSlot ) );

		}

	}

	function update( currentObject, currentMaterialSlot = 0 ) {

		object = currentObject;
		materialSlot = currentMaterialSlot;

		if ( object === null ) return;
		if ( object.material === undefined ) return;

		material = editor.getObjectMaterial( object, materialSlot );

		if ( property in material ) {

			constant.setValue( material[ property ] );
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

- `parseInt`
- `constant.getValue`
- `editor.execute`

<details><summary>Code</summary>

```typescript
function onChange() {

		const value = parseInt( constant.getValue() );

		if ( material[ property ] !== value ) {

			editor.execute( new SetMaterialValueCommand( editor, object, property, value, materialSlot ) );

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
- `constant.setValue`
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

			constant.setValue( material[ property ] );
			container.setDisplay( '' );

		} else {

			container.setDisplay( 'none' );

		}

	}
```
</details>


---