[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Material.Program.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Material.Program.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIButton` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `object` | `any` | let/var | `null` | ✗ |
| `materialSlot` | `any` | let/var | `null` | ✗ |
| `material` | `any` | let/var | `null` | ✗ |
| `container` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `programInfo` | `UIButton` | let/var | `new UIButton( strings.getKey( 'sidebar/material/info' ) )` | ✗ |
| `programVertex` | `UIButton` | let/var | `new UIButton( strings.getKey( 'sidebar/material/vertex' ) )` | ✗ |
| `programFragment` | `UIButton` | let/var | `new UIButton( strings.getKey( 'sidebar/material/fragment' ) )` | ✗ |


---

## Functions

### `SidebarMaterialProgram(editor: any, property: any): UIRow`

**Parameters:**

- **`editor`** `any`
- **`property`** `any`

**Returns:** `UIRow`

**Calls:**

- `container.add`
- `new UIText( strings.getKey( 'sidebar/material/program' ) ).setClass`
- `strings.getKey`
- `programInfo.setMarginRight`
- `programInfo.onClick`
- `signals.editScript.dispatch`
- `programVertex.setMarginRight`
- `programVertex.onClick`
- `programFragment.setMarginRight`
- `programFragment.onClick`
- `editor.getObjectMaterial`
- `container.setDisplay`
- `signals.objectSelected.add`
- `signals.materialChanged.add`

**Internal Comments:**
```
// (x5)
```

<details><summary>Code</summary>

```typescript
function SidebarMaterialProgram( editor, property ) {

	const signals = editor.signals;
	const strings = editor.strings;

	let object = null;
	let materialSlot = null;
	let material = null;

	const container = new UIRow();
	container.add( new UIText( strings.getKey( 'sidebar/material/program' ) ).setClass( 'Label' ) );

	const programInfo = new UIButton( strings.getKey( 'sidebar/material/info' ) );
	programInfo.setMarginRight( '4px' );
	programInfo.onClick( function () {

		signals.editScript.dispatch( object, 'programInfo' );

	} );
	container.add( programInfo );

	const programVertex = new UIButton( strings.getKey( 'sidebar/material/vertex' ) );
	programVertex.setMarginRight( '4px' );
	programVertex.onClick( function () {

		signals.editScript.dispatch( object, 'vertexShader' );

	} );
	container.add( programVertex );

	const programFragment = new UIButton( strings.getKey( 'sidebar/material/fragment' ) );
	programFragment.setMarginRight( '4px' );
	programFragment.onClick( function () {

		signals.editScript.dispatch( object, 'fragmentShader' );

	} );
	container.add( programFragment );

	function update( currentObject, currentMaterialSlot = 0 ) {

		object = currentObject;
		materialSlot = currentMaterialSlot;

		if ( object === null ) return;
		if ( object.material === undefined ) return;

		material = editor.getObjectMaterial( object, materialSlot );

		if ( property in material ) {

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

### `update(currentObject: any, currentMaterialSlot: number): void`

**Parameters:**

- **`currentObject`** `any`
- **`currentMaterialSlot`** `number`

**Returns:** `void`

**Calls:**

- `editor.getObjectMaterial`
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

			container.setDisplay( '' );

		} else {

			container.setDisplay( 'none' );

		}

	}
```
</details>


---