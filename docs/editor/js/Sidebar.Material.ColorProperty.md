[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Material.ColorProperty.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Material.ColorProperty.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIColor` | `./libs/ui.js` |
| `UINumber` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `SetMaterialColorCommand` | `./commands/SetMaterialColorCommand.js` |
| `SetMaterialValueCommand` | `./commands/SetMaterialValueCommand.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `container` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `intensity` | `any` | let/var | `*not shown*` | ✗ |
| `object` | `any` | let/var | `null` | ✗ |
| `materialSlot` | `any` | let/var | `null` | ✗ |
| `material` | `any` | let/var | `null` | ✗ |


---

## Functions

### `SidebarMaterialColorProperty(editor: any, property: any, name: any): UIRow`

**Parameters:**

- **`editor`** `any`
- **`property`** `any`
- **`name`** `any`

**Returns:** `UIRow`

**Calls:**

- `container.add`
- `new UIText( name ).setClass`
- `new UIColor().onInput`
- `new UINumber( 1 ).setWidth( '30px' ).setRange( 0, Infinity ).onChange`
- `material[ property ].getHex`
- `color.getHexValue`
- `editor.execute`
- `intensity.getValue`
- `editor.getObjectMaterial`
- `color.setHexValue`
- `material[ property ].getHexString`
- `intensity.setValue`
- `container.setDisplay`
- `signals.objectSelected.add`
- `signals.materialChanged.add`

**Internal Comments:**
```
// (x5)
```

<details><summary>Code</summary>

```typescript
function SidebarMaterialColorProperty( editor, property, name ) {

	const signals = editor.signals;

	const container = new UIRow();
	container.add( new UIText( name ).setClass( 'Label' ) );

	const color = new UIColor().onInput( onChange );
	container.add( color );

	let intensity;

	if ( property === 'emissive' ) {

		intensity = new UINumber( 1 ).setWidth( '30px' ).setRange( 0, Infinity ).onChange( onChange );
		container.add( intensity );

	}

	let object = null;
	let materialSlot = null;
	let material = null;

	function onChange() {

		if ( material[ property ].getHex() !== color.getHexValue() ) {

			editor.execute( new SetMaterialColorCommand( editor, object, property, color.getHexValue(), materialSlot ) );

		}

		if ( intensity !== undefined ) {

			if ( material[ `${ property }Intensity` ] !== intensity.getValue() ) {

				editor.execute( new SetMaterialValueCommand( editor, object, `${ property }Intensity`, intensity.getValue(), materialSlot ) );

			}

		}

	}

	function update( currentObject, currentMaterialSlot = 0 ) {

		object = currentObject;
		materialSlot = currentMaterialSlot;

		if ( object === null ) return;
		if ( object.material === undefined ) return;

		material = editor.getObjectMaterial( object, materialSlot );

		if ( property in material ) {

			color.setHexValue( material[ property ].getHexString() );

			if ( intensity !== undefined ) {

				intensity.setValue( material[ `${ property }Intensity` ] );

			}

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

- `material[ property ].getHex`
- `color.getHexValue`
- `editor.execute`
- `intensity.getValue`

<details><summary>Code</summary>

```typescript
function onChange() {

		if ( material[ property ].getHex() !== color.getHexValue() ) {

			editor.execute( new SetMaterialColorCommand( editor, object, property, color.getHexValue(), materialSlot ) );

		}

		if ( intensity !== undefined ) {

			if ( material[ `${ property }Intensity` ] !== intensity.getValue() ) {

				editor.execute( new SetMaterialValueCommand( editor, object, `${ property }Intensity`, intensity.getValue(), materialSlot ) );

			}

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
- `color.setHexValue`
- `material[ property ].getHexString`
- `intensity.setValue`
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

			color.setHexValue( material[ property ].getHexString() );

			if ( intensity !== undefined ) {

				intensity.setValue( material[ `${ property }Intensity` ] );

			}

			container.setDisplay( '' );

		} else {

			container.setDisplay( 'none' );

		}

	}
```
</details>


---