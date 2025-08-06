[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Geometry.BoxGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 12 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Geometry.BoxGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIDiv` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `UINumber` | `./libs/ui.js` |
| `UIInteger` | `./libs/ui.js` |
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
| `widthRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `heightRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `depthRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `widthSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `heightSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `depthSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `parameters` | `any` | let/var | `object.geometry.parameters` | ✗ |


---

## Functions

### `GeometryParametersPanel(editor: any, object: any): UIDiv`

**Parameters:**

- **`editor`** `any`
- **`object`** `any`

**Returns:** `UIDiv`

**Calls:**

- `new UINumber().setPrecision( 3 ).setValue( parameters.width ).onChange`
- `widthRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/box_geometry/width' ) ).setClass`
- `strings.getKey`
- `container.add`
- `new UINumber().setPrecision( 3 ).setValue( parameters.height ).onChange`
- `heightRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/box_geometry/height' ) ).setClass`
- `new UINumber().setPrecision( 3 ).setValue( parameters.depth ).onChange`
- `depthRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/box_geometry/depth' ) ).setClass`
- `new UIInteger( parameters.widthSegments ).setRange( 1, Infinity ).onChange`
- `widthSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/box_geometry/widthseg' ) ).setClass`
- `new UIInteger( parameters.heightSegments ).setRange( 1, Infinity ).onChange`
- `heightSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/box_geometry/heightseg' ) ).setClass`
- `new UIInteger( parameters.depthSegments ).setRange( 1, Infinity ).onChange`
- `depthSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/box_geometry/depthseg' ) ).setClass`
- `width.setValue`
- `height.setValue`
- `depth.setValue`
- `widthSegments.setValue`
- `heightSegments.setValue`
- `depthSegments.setValue`
- `signals.geometryChanged.add`
- `refreshUI`
- `editor.execute`
- `width.getValue`
- `height.getValue`
- `depth.getValue`
- `widthSegments.getValue`
- `heightSegments.getValue`
- `depthSegments.getValue`

**Internal Comments:**
```
// width (x2)
// height (x2)
// depth (x2)
// widthSegments (x2)
// heightSegments (x2)
// depthSegments (x2)
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

	// width

	const widthRow = new UIRow();
	const width = new UINumber().setPrecision( 3 ).setValue( parameters.width ).onChange( update );

	widthRow.add( new UIText( strings.getKey( 'sidebar/geometry/box_geometry/width' ) ).setClass( 'Label' ) );
	widthRow.add( width );

	container.add( widthRow );

	// height

	const heightRow = new UIRow();
	const height = new UINumber().setPrecision( 3 ).setValue( parameters.height ).onChange( update );

	heightRow.add( new UIText( strings.getKey( 'sidebar/geometry/box_geometry/height' ) ).setClass( 'Label' ) );
	heightRow.add( height );

	container.add( heightRow );

	// depth

	const depthRow = new UIRow();
	const depth = new UINumber().setPrecision( 3 ).setValue( parameters.depth ).onChange( update );

	depthRow.add( new UIText( strings.getKey( 'sidebar/geometry/box_geometry/depth' ) ).setClass( 'Label' ) );
	depthRow.add( depth );

	container.add( depthRow );

	// widthSegments

	const widthSegmentsRow = new UIRow();
	const widthSegments = new UIInteger( parameters.widthSegments ).setRange( 1, Infinity ).onChange( update );

	widthSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/box_geometry/widthseg' ) ).setClass( 'Label' ) );
	widthSegmentsRow.add( widthSegments );

	container.add( widthSegmentsRow );

	// heightSegments

	const heightSegmentsRow = new UIRow();
	const heightSegments = new UIInteger( parameters.heightSegments ).setRange( 1, Infinity ).onChange( update );

	heightSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/box_geometry/heightseg' ) ).setClass( 'Label' ) );
	heightSegmentsRow.add( heightSegments );

	container.add( heightSegmentsRow );

	// depthSegments

	const depthSegmentsRow = new UIRow();
	const depthSegments = new UIInteger( parameters.depthSegments ).setRange( 1, Infinity ).onChange( update );

	depthSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/box_geometry/depthseg' ) ).setClass( 'Label' ) );
	depthSegmentsRow.add( depthSegments );

	container.add( depthSegmentsRow );

	//

	function refreshUI() {

		const parameters = object.geometry.parameters;

		width.setValue( parameters.width );
		height.setValue( parameters.height );
		depth.setValue( parameters.depth );
		widthSegments.setValue( parameters.widthSegments );
		heightSegments.setValue( parameters.heightSegments );
		depthSegments.setValue( parameters.depthSegments );

	}

	signals.geometryChanged.add( function ( mesh ) {

		if ( mesh === object ) {

			refreshUI();

		}

	} );

	//

	function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.BoxGeometry(
			width.getValue(),
			height.getValue(),
			depth.getValue(),
			widthSegments.getValue(),
			heightSegments.getValue(),
			depthSegments.getValue()
		) ) );

	}

	return container;

}
```
</details>

### `refreshUI(): void`

**Returns:** `void`

**Calls:**

- `width.setValue`
- `height.setValue`
- `depth.setValue`
- `widthSegments.setValue`
- `heightSegments.setValue`
- `depthSegments.setValue`

<details><summary>Code</summary>

```typescript
function refreshUI() {

		const parameters = object.geometry.parameters;

		width.setValue( parameters.width );
		height.setValue( parameters.height );
		depth.setValue( parameters.depth );
		widthSegments.setValue( parameters.widthSegments );
		heightSegments.setValue( parameters.heightSegments );
		depthSegments.setValue( parameters.depthSegments );

	}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `editor.execute`
- `width.getValue`
- `height.getValue`
- `depth.getValue`
- `widthSegments.getValue`
- `heightSegments.getValue`
- `depthSegments.getValue`

<details><summary>Code</summary>

```typescript
function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.BoxGeometry(
			width.getValue(),
			height.getValue(),
			depth.getValue(),
			widthSegments.getValue(),
			heightSegments.getValue(),
			depthSegments.getValue()
		) ) );

	}
```
</details>


---