[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Geometry.ExtrudeGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 16 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Geometry.ExtrudeGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIDiv` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `UIInteger` | `./libs/ui.js` |
| `UICheckbox` | `./libs/ui.js` |
| `UIButton` | `./libs/ui.js` |
| `UINumber` | `./libs/ui.js` |
| `SetGeometryCommand` | `./commands/SetGeometryCommand.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `container` | `UIDiv` | let/var | `new UIDiv()` | ✗ |
| `geometry` | `any` | let/var | `object.geometry` | ✗ |
| `parameters` | `any` | let/var | `geometry.parameters` | ✗ |
| `options` | `any` | let/var | `parameters.options` | ✗ |
| `bevelThickness` | `any` | let/var | `options.bevelThickness !== undefined ? options.bevelThickness : 0.2` | ✗ |
| `curveSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `stepsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `depthRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `enabledRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `thicknessRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `sizeRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `offsetRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `segmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `options` | `any` | let/var | `object.geometry.parameters.options` | ✗ |


---

## Functions

### `GeometryParametersPanel(editor: any, object: any): UIDiv`

**Parameters:**

- **`editor`** `any`
- **`object`** `any`

**Returns:** `UIDiv`

**Calls:**

- `new UIInteger( options.curveSegments ).onChange( update ).setRange`
- `curveSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/extrude_geometry/curveSegments' ) ).setClass`
- `strings.getKey`
- `container.add`
- `new UIInteger( options.steps ).onChange( update ).setRange`
- `stepsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/extrude_geometry/steps' ) ).setClass`
- `new UINumber( options.depth ).onChange( update ).setRange`
- `depthRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/extrude_geometry/depth' ) ).setClass`
- `new UICheckbox( options.bevelEnabled ).onChange`
- `enabledRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/extrude_geometry/bevelEnabled' ) ).setClass`
- `new UINumber( options.bevelThickness ).onChange`
- `thicknessRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/extrude_geometry/bevelThickness' ) ).setClass`
- `new UINumber( options.bevelSize ).onChange`
- `sizeRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/extrude_geometry/bevelSize' ) ).setClass`
- `new UINumber( options.bevelOffset ).onChange`
- `offsetRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/extrude_geometry/bevelOffset' ) ).setClass`
- `new UIInteger( options.bevelSegments ).onChange( update ).setRange`
- `segmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/extrude_geometry/bevelSegments' ) ).setClass`
- `updateBevelRow`
- `new UIButton( strings.getKey( 'sidebar/geometry/extrude_geometry/shape' ) ).onClick( toShape ).setClass( 'Label' ).setMarginLeft`
- `thicknessRow.setDisplay`
- `sizeRow.setDisplay`
- `offsetRow.setDisplay`
- `segmentsRow.setDisplay`
- `curveSegments.setValue`
- `steps.setValue`
- `depth.setValue`
- `enabled.setValue`
- `thickness.setValue`
- `size.setValue`
- `offset.setValue`
- `segments.setValue`
- `signals.geometryChanged.add`
- `refreshUI`
- `enabled.getValue`
- `editor.execute`
- `curveSegments.getValue`
- `steps.getValue`
- `depth.getValue`
- `thickness.getValue`
- `size.getValue`
- `offset.getValue`
- `segments.getValue`

**Internal Comments:**
```
// curveSegments (x2)
// steps (x2)
// depth (x2)
// enabled (x2)
// thickness (x2)
// size (x2)
// offset (x2)
// segments (x2)
// (x2)
```

<details><summary>Code</summary>

```typescript
function GeometryParametersPanel( editor, object ) {

	const strings = editor.strings;
	const signals = editor.signals;

	const container = new UIDiv();

	const geometry = object.geometry;
	const parameters = geometry.parameters;
	const options = parameters.options;
	options.curveSegments = options.curveSegments != undefined ? options.curveSegments : 12;
	options.steps = options.steps != undefined ? options.steps : 1;
	options.depth = options.depth != undefined ? options.depth : 1;
	const bevelThickness = options.bevelThickness !== undefined ? options.bevelThickness : 0.2;
	options.bevelThickness = bevelThickness;
	options.bevelSize = options.bevelSize !== undefined ? options.bevelSize : bevelThickness - 0.1;
	options.bevelOffset = options.bevelOffset !== undefined ? options.bevelOffset : 0;
	options.bevelSegments = options.bevelSegments !== undefined ? options.bevelSegments : 3;


	// curveSegments

	const curveSegmentsRow = new UIRow();
	const curveSegments = new UIInteger( options.curveSegments ).onChange( update ).setRange( 1, Infinity );

	curveSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/extrude_geometry/curveSegments' ) ).setClass( 'Label' ) );
	curveSegmentsRow.add( curveSegments );

	container.add( curveSegmentsRow );

	// steps

	const stepsRow = new UIRow();
	const steps = new UIInteger( options.steps ).onChange( update ).setRange( 1, Infinity );

	stepsRow.add( new UIText( strings.getKey( 'sidebar/geometry/extrude_geometry/steps' ) ).setClass( 'Label' ) );
	stepsRow.add( steps );

	container.add( stepsRow );

	// depth

	const depthRow = new UIRow();
	const depth = new UINumber( options.depth ).onChange( update ).setRange( 1, Infinity );

	depthRow.add( new UIText( strings.getKey( 'sidebar/geometry/extrude_geometry/depth' ) ).setClass( 'Label' ) );
	depthRow.add( depth );

	container.add( depthRow );

	// enabled

	const enabledRow = new UIRow();
	const enabled = new UICheckbox( options.bevelEnabled ).onChange( update );

	enabledRow.add( new UIText( strings.getKey( 'sidebar/geometry/extrude_geometry/bevelEnabled' ) ).setClass( 'Label' ) );
	enabledRow.add( enabled );

	container.add( enabledRow );

	// thickness

	const thicknessRow = new UIRow();
	const thickness = new UINumber( options.bevelThickness ).onChange( update );

	thicknessRow.add( new UIText( strings.getKey( 'sidebar/geometry/extrude_geometry/bevelThickness' ) ).setClass( 'Label' ) );
	thicknessRow.add( thickness );

	container.add( thicknessRow );

	// size

	const sizeRow = new UIRow();
	const size = new UINumber( options.bevelSize ).onChange( update );

	sizeRow.add( new UIText( strings.getKey( 'sidebar/geometry/extrude_geometry/bevelSize' ) ).setClass( 'Label' ) );
	sizeRow.add( size );

	container.add( sizeRow );

	// offset

	const offsetRow = new UIRow();
	const offset = new UINumber( options.bevelOffset ).onChange( update );

	offsetRow.add( new UIText( strings.getKey( 'sidebar/geometry/extrude_geometry/bevelOffset' ) ).setClass( 'Label' ) );
	offsetRow.add( offset );

	container.add( offsetRow );

	// segments

	const segmentsRow = new UIRow();
	const segments = new UIInteger( options.bevelSegments ).onChange( update ).setRange( 0, Infinity );

	segmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/extrude_geometry/bevelSegments' ) ).setClass( 'Label' ) );
	segmentsRow.add( segments );

	container.add( segmentsRow );

	updateBevelRow( options.bevelEnabled );

	const button = new UIButton( strings.getKey( 'sidebar/geometry/extrude_geometry/shape' ) ).onClick( toShape ).setClass( 'Label' ).setMarginLeft( '120px' );
	container.add( button );

	//

	function updateBevelRow( enabled ) {

		if ( enabled === true ) {

			thicknessRow.setDisplay( '' );
			sizeRow.setDisplay( '' );
			offsetRow.setDisplay( '' );
			segmentsRow.setDisplay( '' );

		} else {

			thicknessRow.setDisplay( 'none' );
			sizeRow.setDisplay( 'none' );
			offsetRow.setDisplay( 'none' );
			segmentsRow.setDisplay( 'none' );

		}

	}

	function refreshUI() {

		const options = object.geometry.parameters.options;

		curveSegments.setValue( options.curveSegments );
		steps.setValue( options.steps );
		depth.setValue( options.depth );
		enabled.setValue( options.bevelEnabled );
		thickness.setValue( options.bevelThickness );
		size.setValue( options.bevelSize );
		offset.setValue( options.bevelOffset );
		segments.setValue( options.bevelSegments );

		updateBevelRow( options.bevelEnabled );

	}

	signals.geometryChanged.add( function ( mesh ) {

		if ( mesh === object ) {

			refreshUI();

		}

	} );

	//

	function update() {

		updateBevelRow( enabled.getValue() );

		editor.execute( new SetGeometryCommand( editor, object, new THREE.ExtrudeGeometry(
			parameters.shapes,
			{
				curveSegments: curveSegments.getValue(),
				steps: steps.getValue(),
				depth: depth.getValue(),
				bevelEnabled: enabled.getValue(),
				bevelThickness: thickness !== undefined ? thickness.getValue() : options.bevelThickness,
				bevelSize: size !== undefined ? size.getValue() : options.bevelSize,
				bevelOffset: offset !== undefined ? offset.getValue() : options.bevelOffset,
				bevelSegments: segments !== undefined ? segments.getValue() : options.bevelSegments
			}
		) ) );

	}

	function toShape() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.ShapeGeometry(
			parameters.shapes,
			options.curveSegments
		) ) );

	}

	return container;

}
```
</details>

### `updateBevelRow(enabled: any): void`

**Parameters:**

- **`enabled`** `any`

**Returns:** `void`

**Calls:**

- `thicknessRow.setDisplay`
- `sizeRow.setDisplay`
- `offsetRow.setDisplay`
- `segmentsRow.setDisplay`

<details><summary>Code</summary>

```typescript
function updateBevelRow( enabled ) {

		if ( enabled === true ) {

			thicknessRow.setDisplay( '' );
			sizeRow.setDisplay( '' );
			offsetRow.setDisplay( '' );
			segmentsRow.setDisplay( '' );

		} else {

			thicknessRow.setDisplay( 'none' );
			sizeRow.setDisplay( 'none' );
			offsetRow.setDisplay( 'none' );
			segmentsRow.setDisplay( 'none' );

		}

	}
```
</details>

### `refreshUI(): void`

**Returns:** `void`

**Calls:**

- `curveSegments.setValue`
- `steps.setValue`
- `depth.setValue`
- `enabled.setValue`
- `thickness.setValue`
- `size.setValue`
- `offset.setValue`
- `segments.setValue`
- `updateBevelRow`

<details><summary>Code</summary>

```typescript
function refreshUI() {

		const options = object.geometry.parameters.options;

		curveSegments.setValue( options.curveSegments );
		steps.setValue( options.steps );
		depth.setValue( options.depth );
		enabled.setValue( options.bevelEnabled );
		thickness.setValue( options.bevelThickness );
		size.setValue( options.bevelSize );
		offset.setValue( options.bevelOffset );
		segments.setValue( options.bevelSegments );

		updateBevelRow( options.bevelEnabled );

	}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `updateBevelRow`
- `enabled.getValue`
- `editor.execute`
- `curveSegments.getValue`
- `steps.getValue`
- `depth.getValue`
- `thickness.getValue`
- `size.getValue`
- `offset.getValue`
- `segments.getValue`

<details><summary>Code</summary>

```typescript
function update() {

		updateBevelRow( enabled.getValue() );

		editor.execute( new SetGeometryCommand( editor, object, new THREE.ExtrudeGeometry(
			parameters.shapes,
			{
				curveSegments: curveSegments.getValue(),
				steps: steps.getValue(),
				depth: depth.getValue(),
				bevelEnabled: enabled.getValue(),
				bevelThickness: thickness !== undefined ? thickness.getValue() : options.bevelThickness,
				bevelSize: size !== undefined ? size.getValue() : options.bevelSize,
				bevelOffset: offset !== undefined ? offset.getValue() : options.bevelOffset,
				bevelSegments: segments !== undefined ? segments.getValue() : options.bevelSegments
			}
		) ) );

	}
```
</details>

### `toShape(): void`

**Returns:** `void`

**Calls:**

- `editor.execute`

<details><summary>Code</summary>

```typescript
function toShape() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.ShapeGeometry(
			parameters.shapes,
			options.curveSegments
		) ) );

	}
```
</details>


---