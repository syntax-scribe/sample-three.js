[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Geometry.SphereGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 13 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Geometry.SphereGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIDiv` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `UIInteger` | `./libs/ui.js` |
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
| `radiusRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `widthSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `heightSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `phiStartRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `phiLengthRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `thetaStartRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `thetaLengthRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `parameters` | `any` | let/var | `object.geometry.parameters` | ✗ |


---

## Functions

### `GeometryParametersPanel(editor: any, object: any): UIDiv`

**Parameters:**

- **`editor`** `any`
- **`object`** `any`

**Returns:** `UIDiv`

**Calls:**

- `new UINumber( parameters.radius ).onChange`
- `radiusRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/sphere_geometry/radius' ) ).setClass`
- `strings.getKey`
- `container.add`
- `new UIInteger( parameters.widthSegments ).setRange( 1, Infinity ).onChange`
- `widthSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/sphere_geometry/widthsegments' ) ).setClass`
- `new UIInteger( parameters.heightSegments ).setRange( 1, Infinity ).onChange`
- `heightSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/sphere_geometry/heightsegments' ) ).setClass`
- `new UINumber( parameters.phiStart * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange`
- `phiStartRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/sphere_geometry/phistart' ) ).setClass`
- `new UINumber( parameters.phiLength * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange`
- `phiLengthRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/sphere_geometry/philength' ) ).setClass`
- `new UINumber( parameters.thetaStart * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange`
- `thetaStartRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/sphere_geometry/thetastart' ) ).setClass`
- `new UINumber( parameters.thetaLength * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange`
- `thetaLengthRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/sphere_geometry/thetalength' ) ).setClass`
- `radius.setValue`
- `widthSegments.setValue`
- `heightSegments.setValue`
- `phiStart.setValue`
- `phiLength.setValue`
- `thetaStart.setValue`
- `thetaLength.setValue`
- `signals.geometryChanged.add`
- `refreshUI`
- `editor.execute`
- `radius.getValue`
- `widthSegments.getValue`
- `heightSegments.getValue`
- `phiStart.getValue`
- `phiLength.getValue`
- `thetaStart.getValue`
- `thetaLength.getValue`

**Internal Comments:**
```
// radius (x2)
// widthSegments (x2)
// heightSegments (x2)
// phiStart (x2)
// phiLength (x2)
// thetaStart (x2)
// thetaLength (x2)
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

	// radius

	const radiusRow = new UIRow();
	const radius = new UINumber( parameters.radius ).onChange( update );

	radiusRow.add( new UIText( strings.getKey( 'sidebar/geometry/sphere_geometry/radius' ) ).setClass( 'Label' ) );
	radiusRow.add( radius );

	container.add( radiusRow );

	// widthSegments

	const widthSegmentsRow = new UIRow();
	const widthSegments = new UIInteger( parameters.widthSegments ).setRange( 1, Infinity ).onChange( update );

	widthSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/sphere_geometry/widthsegments' ) ).setClass( 'Label' ) );
	widthSegmentsRow.add( widthSegments );

	container.add( widthSegmentsRow );

	// heightSegments

	const heightSegmentsRow = new UIRow();
	const heightSegments = new UIInteger( parameters.heightSegments ).setRange( 1, Infinity ).onChange( update );

	heightSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/sphere_geometry/heightsegments' ) ).setClass( 'Label' ) );
	heightSegmentsRow.add( heightSegments );

	container.add( heightSegmentsRow );

	// phiStart

	const phiStartRow = new UIRow();
	const phiStart = new UINumber( parameters.phiStart * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange( update );

	phiStartRow.add( new UIText( strings.getKey( 'sidebar/geometry/sphere_geometry/phistart' ) ).setClass( 'Label' ) );
	phiStartRow.add( phiStart );

	container.add( phiStartRow );

	// phiLength

	const phiLengthRow = new UIRow();
	const phiLength = new UINumber( parameters.phiLength * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange( update );

	phiLengthRow.add( new UIText( strings.getKey( 'sidebar/geometry/sphere_geometry/philength' ) ).setClass( 'Label' ) );
	phiLengthRow.add( phiLength );

	container.add( phiLengthRow );

	// thetaStart

	const thetaStartRow = new UIRow();
	const thetaStart = new UINumber( parameters.thetaStart * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange( update );

	thetaStartRow.add( new UIText( strings.getKey( 'sidebar/geometry/sphere_geometry/thetastart' ) ).setClass( 'Label' ) );
	thetaStartRow.add( thetaStart );

	container.add( thetaStartRow );

	// thetaLength

	const thetaLengthRow = new UIRow();
	const thetaLength = new UINumber( parameters.thetaLength * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange( update );

	thetaLengthRow.add( new UIText( strings.getKey( 'sidebar/geometry/sphere_geometry/thetalength' ) ).setClass( 'Label' ) );
	thetaLengthRow.add( thetaLength );

	container.add( thetaLengthRow );

	//

	function refreshUI() {

		const parameters = object.geometry.parameters;

		radius.setValue( parameters.radius );
		widthSegments.setValue( parameters.widthSegments );
		heightSegments.setValue( parameters.heightSegments );
		phiStart.setValue( parameters.phiStart * THREE.MathUtils.RAD2DEG );
		phiLength.setValue( parameters.phiLength * THREE.MathUtils.RAD2DEG );
		thetaStart.setValue( parameters.thetaStart * THREE.MathUtils.RAD2DEG );
		thetaLength.setValue( parameters.thetaLength * THREE.MathUtils.RAD2DEG );

	}

	signals.geometryChanged.add( function ( mesh ) {

		if ( mesh === object ) {

			refreshUI();

		}

	} );

	//

	function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.SphereGeometry(
			radius.getValue(),
			widthSegments.getValue(),
			heightSegments.getValue(),
			phiStart.getValue() * THREE.MathUtils.DEG2RAD,
			phiLength.getValue() * THREE.MathUtils.DEG2RAD,
			thetaStart.getValue() * THREE.MathUtils.DEG2RAD,
			thetaLength.getValue() * THREE.MathUtils.DEG2RAD
		) ) );

	}

	return container;

}
```
</details>

### `refreshUI(): void`

**Returns:** `void`

**Calls:**

- `radius.setValue`
- `widthSegments.setValue`
- `heightSegments.setValue`
- `phiStart.setValue`
- `phiLength.setValue`
- `thetaStart.setValue`
- `thetaLength.setValue`

<details><summary>Code</summary>

```typescript
function refreshUI() {

		const parameters = object.geometry.parameters;

		radius.setValue( parameters.radius );
		widthSegments.setValue( parameters.widthSegments );
		heightSegments.setValue( parameters.heightSegments );
		phiStart.setValue( parameters.phiStart * THREE.MathUtils.RAD2DEG );
		phiLength.setValue( parameters.phiLength * THREE.MathUtils.RAD2DEG );
		thetaStart.setValue( parameters.thetaStart * THREE.MathUtils.RAD2DEG );
		thetaLength.setValue( parameters.thetaLength * THREE.MathUtils.RAD2DEG );

	}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `editor.execute`
- `radius.getValue`
- `widthSegments.getValue`
- `heightSegments.getValue`
- `phiStart.getValue`
- `phiLength.getValue`
- `thetaStart.getValue`
- `thetaLength.getValue`

<details><summary>Code</summary>

```typescript
function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.SphereGeometry(
			radius.getValue(),
			widthSegments.getValue(),
			heightSegments.getValue(),
			phiStart.getValue() * THREE.MathUtils.DEG2RAD,
			phiLength.getValue() * THREE.MathUtils.DEG2RAD,
			thetaStart.getValue() * THREE.MathUtils.DEG2RAD,
			thetaLength.getValue() * THREE.MathUtils.DEG2RAD
		) ) );

	}
```
</details>


---