[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Geometry.CylinderGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 12 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Geometry.CylinderGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIDiv` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `UIInteger` | `./libs/ui.js` |
| `UICheckbox` | `./libs/ui.js` |
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
| `radiusTopRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `radiusBottomRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `heightRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `radialSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `heightSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `openEndedRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `parameters` | `any` | let/var | `object.geometry.parameters` | ✗ |


---

## Functions

### `GeometryParametersPanel(editor: any, object: any): UIDiv`

**Parameters:**

- **`editor`** `any`
- **`object`** `any`

**Returns:** `UIDiv`

**Calls:**

- `new UINumber( parameters.radiusTop ).onChange`
- `radiusTopRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/cylinder_geometry/radiustop' ) ).setClass`
- `strings.getKey`
- `container.add`
- `new UINumber( parameters.radiusBottom ).onChange`
- `radiusBottomRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/cylinder_geometry/radiusbottom' ) ).setClass`
- `new UINumber( parameters.height ).onChange`
- `heightRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/cylinder_geometry/height' ) ).setClass`
- `new UIInteger( parameters.radialSegments ).setRange( 1, Infinity ).onChange`
- `radialSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/cylinder_geometry/radialsegments' ) ).setClass`
- `new UIInteger( parameters.heightSegments ).setRange( 1, Infinity ).onChange`
- `heightSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/cylinder_geometry/heightsegments' ) ).setClass`
- `new UICheckbox( parameters.openEnded ).onChange`
- `openEndedRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/cylinder_geometry/openended' ) ).setClass`
- `radiusTop.setValue`
- `radiusBottom.setValue`
- `height.setValue`
- `radialSegments.setValue`
- `heightSegments.setValue`
- `openEnded.setValue`
- `signals.geometryChanged.add`
- `refreshUI`
- `editor.execute`
- `radiusTop.getValue`
- `radiusBottom.getValue`
- `height.getValue`
- `radialSegments.getValue`
- `heightSegments.getValue`
- `openEnded.getValue`

**Internal Comments:**
```
// radiusTop (x2)
// radiusBottom (x2)
// height (x2)
// radialSegments (x2)
// heightSegments (x2)
// openEnded (x2)
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

	// radiusTop

	const radiusTopRow = new UIRow();
	const radiusTop = new UINumber( parameters.radiusTop ).onChange( update );

	radiusTopRow.add( new UIText( strings.getKey( 'sidebar/geometry/cylinder_geometry/radiustop' ) ).setClass( 'Label' ) );
	radiusTopRow.add( radiusTop );

	container.add( radiusTopRow );

	// radiusBottom

	const radiusBottomRow = new UIRow();
	const radiusBottom = new UINumber( parameters.radiusBottom ).onChange( update );

	radiusBottomRow.add( new UIText( strings.getKey( 'sidebar/geometry/cylinder_geometry/radiusbottom' ) ).setClass( 'Label' ) );
	radiusBottomRow.add( radiusBottom );

	container.add( radiusBottomRow );

	// height

	const heightRow = new UIRow();
	const height = new UINumber( parameters.height ).onChange( update );

	heightRow.add( new UIText( strings.getKey( 'sidebar/geometry/cylinder_geometry/height' ) ).setClass( 'Label' ) );
	heightRow.add( height );

	container.add( heightRow );

	// radialSegments

	const radialSegmentsRow = new UIRow();
	const radialSegments = new UIInteger( parameters.radialSegments ).setRange( 1, Infinity ).onChange( update );

	radialSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/cylinder_geometry/radialsegments' ) ).setClass( 'Label' ) );
	radialSegmentsRow.add( radialSegments );

	container.add( radialSegmentsRow );

	// heightSegments

	const heightSegmentsRow = new UIRow();
	const heightSegments = new UIInteger( parameters.heightSegments ).setRange( 1, Infinity ).onChange( update );

	heightSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/cylinder_geometry/heightsegments' ) ).setClass( 'Label' ) );
	heightSegmentsRow.add( heightSegments );

	container.add( heightSegmentsRow );

	// openEnded

	const openEndedRow = new UIRow();
	const openEnded = new UICheckbox( parameters.openEnded ).onChange( update );

	openEndedRow.add( new UIText( strings.getKey( 'sidebar/geometry/cylinder_geometry/openended' ) ).setClass( 'Label' ) );
	openEndedRow.add( openEnded );

	container.add( openEndedRow );

	//

	function refreshUI() {

		const parameters = object.geometry.parameters;

		radiusTop.setValue( parameters.radiusTop );
		radiusBottom.setValue( parameters.radiusBottom );
		height.setValue( parameters.height );
		radialSegments.setValue( parameters.radialSegments );
		heightSegments.setValue( parameters.heightSegments );
		openEnded.setValue( parameters.openEnded );

	}

	signals.geometryChanged.add( function ( mesh ) {

		if ( mesh === object ) {

			refreshUI();

		}

	} );

	//

	function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.CylinderGeometry(
			radiusTop.getValue(),
			radiusBottom.getValue(),
			height.getValue(),
			radialSegments.getValue(),
			heightSegments.getValue(),
			openEnded.getValue()
		) ) );

	}

	return container;

}
```
</details>

### `refreshUI(): void`

**Returns:** `void`

**Calls:**

- `radiusTop.setValue`
- `radiusBottom.setValue`
- `height.setValue`
- `radialSegments.setValue`
- `heightSegments.setValue`
- `openEnded.setValue`

<details><summary>Code</summary>

```typescript
function refreshUI() {

		const parameters = object.geometry.parameters;

		radiusTop.setValue( parameters.radiusTop );
		radiusBottom.setValue( parameters.radiusBottom );
		height.setValue( parameters.height );
		radialSegments.setValue( parameters.radialSegments );
		heightSegments.setValue( parameters.heightSegments );
		openEnded.setValue( parameters.openEnded );

	}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `editor.execute`
- `radiusTop.getValue`
- `radiusBottom.getValue`
- `height.getValue`
- `radialSegments.getValue`
- `heightSegments.getValue`
- `openEnded.getValue`

<details><summary>Code</summary>

```typescript
function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.CylinderGeometry(
			radiusTop.getValue(),
			radiusBottom.getValue(),
			height.getValue(),
			radialSegments.getValue(),
			heightSegments.getValue(),
			openEnded.getValue()
		) ) );

	}
```
</details>


---