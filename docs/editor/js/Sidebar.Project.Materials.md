[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Project.Materials.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Project.Materials.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIBreak` | `./libs/ui.js` |
| `UIPanel` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `UIListbox` | `./libs/ui.js` |
| `UIButton` | `./libs/ui.js` |
| `SetMaterialCommand` | `./commands/SetMaterialCommand.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `headerRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `listbox` | `UIListbox` | let/var | `new UIListbox()` | ✗ |
| `buttonsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `assignMaterial` | `UIButton` | let/var | `new UIButton( strings.getKey( 'sidebar/project/Assign' ) )` | ✗ |
| `selectedObject` | `any` | let/var | `editor.selected` | ✗ |
| `oldMaterial` | `any` | let/var | `selectedObject.material` | ✗ |


---

## Functions

### `SidebarProjectMaterials(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `headerRow.add`
- `strings.getKey( 'sidebar/project/materials' ).toUpperCase`
- `container.add`
- `strings.getKey`
- `assignMaterial.onClick`
- `editor.getMaterialById`
- `parseInt`
- `listbox.getValue`
- `editor.removeMaterial`
- `editor.execute`
- `editor.addMaterial`
- `buttonsRow.add`
- `listbox.setItems`
- `Object.values`
- `signals.objectSelected.add`
- `Object.values( editor.materials ).indexOf`
- `listbox.selectIndex`
- `signals.materialAdded.add`
- `signals.materialChanged.add`
- `signals.materialRemoved.add`

**Internal Comments:**
```
// only passing materials to objects with a material property (e.g. avoid assigning material to THREE.Group)
// Signals
```

<details><summary>Code</summary>

```typescript
function SidebarProjectMaterials( editor ) {

	const signals = editor.signals;
	const strings = editor.strings;

	const container = new UIPanel();

	const headerRow = new UIRow();
	headerRow.add( new UIText( strings.getKey( 'sidebar/project/materials' ).toUpperCase() ) );

	container.add( headerRow );

	const listbox = new UIListbox();
	container.add( listbox );

	container.add( new UIBreak() );

	const buttonsRow = new UIRow();
	container.add( buttonsRow );

	const assignMaterial = new UIButton( strings.getKey( 'sidebar/project/Assign' ) );
	assignMaterial.onClick( function () {

		const selectedObject = editor.selected;

		if ( selectedObject !== null ) {

			const oldMaterial = selectedObject.material;

			// only passing materials to objects with a material property (e.g. avoid assigning material to THREE.Group)

			if ( oldMaterial !== undefined ) {

				const material = editor.getMaterialById( parseInt( listbox.getValue() ) );

				if ( material !== undefined ) {

					editor.removeMaterial( oldMaterial );
					editor.execute( new SetMaterialCommand( editor, selectedObject, material ) );
					editor.addMaterial( material );

				}

			}

		}

	} );
	buttonsRow.add( assignMaterial );

	// Signals

	function refreshMaterialBrowserUI() {

		listbox.setItems( Object.values( editor.materials ) );

	}

	signals.objectSelected.add( function ( object ) {

		if ( object !== null ) {

			const index = Object.values( editor.materials ).indexOf( object.material );
			listbox.selectIndex( index );

		}

	} );

	signals.materialAdded.add( refreshMaterialBrowserUI );
	signals.materialChanged.add( refreshMaterialBrowserUI );
	signals.materialRemoved.add( refreshMaterialBrowserUI );

	return container;

}
```
</details>

### `refreshMaterialBrowserUI(): void`

**Returns:** `void`

**Calls:**

- `listbox.setItems`
- `Object.values`

<details><summary>Code</summary>

```typescript
function refreshMaterialBrowserUI() {

		listbox.setItems( Object.values( editor.materials ) );

	}
```
</details>


---