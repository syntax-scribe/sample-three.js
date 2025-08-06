[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Geometry.RingGeometry.js`

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
📂 **`editor/js/Sidebar.Geometry.RingGeometry.js`**

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
| `innerRadiusRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `outerRadiusRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `thetaSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `phiSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
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

- `new UINumber( parameters.innerRadius ).onChange`
- `innerRadiusRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/ring_geometry/innerRadius' ) ).setClass`
- `strings.getKey`
- `container.add`
- `new UINumber( parameters.outerRadius ).onChange`
- `outerRadiusRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/ring_geometry/outerRadius' ) ).setClass`
- `new UIInteger( parameters.thetaSegments ).setRange( 3, Infinity ).onChange`
- `thetaSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/ring_geometry/thetaSegments' ) ).setClass`
- `new UIInteger( parameters.phiSegments ).setRange( 3, Infinity ).onChange`
- `phiSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/ring_geometry/phiSegments' ) ).setClass`
- `new UINumber( parameters.thetaStart * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange`
- `thetaStartRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/ring_geometry/thetastart' ) ).setClass`
- `new UINumber( parameters.thetaLength * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange`
- `thetaLengthRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/ring_geometry/thetalength' ) ).setClass`
- `innerRadius.setValue`
- `outerRadius.setValue`
- `thetaSegments.setValue`
- `phiSegments.setValue`
- `thetaStart.setValue`
- `thetaLength.setValue`
- `signals.geometryChanged.add`
- `refreshUI`
- `editor.execute`
- `innerRadius.getValue`
- `outerRadius.getValue`
- `thetaSegments.getValue`
- `phiSegments.getValue`
- `thetaStart.getValue`
- `thetaLength.getValue`

**Internal Comments:**
```
// innerRadius (x2)
// outerRadius (x2)
// thetaSegments (x2)
// phiSegments (x2)
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

	// innerRadius

	const innerRadiusRow = new UIRow();
	const innerRadius = new UINumber( parameters.innerRadius ).onChange( update );

	innerRadiusRow.add( new UIText( strings.getKey( 'sidebar/geometry/ring_geometry/innerRadius' ) ).setClass( 'Label' ) );
	innerRadiusRow.add( innerRadius );

	container.add( innerRadiusRow );

	// outerRadius

	const outerRadiusRow = new UIRow();
	const outerRadius = new UINumber( parameters.outerRadius ).onChange( update );

	outerRadiusRow.add( new UIText( strings.getKey( 'sidebar/geometry/ring_geometry/outerRadius' ) ).setClass( 'Label' ) );
	outerRadiusRow.add( outerRadius );

	container.add( outerRadiusRow );

	// thetaSegments

	const thetaSegmentsRow = new UIRow();
	const thetaSegments = new UIInteger( parameters.thetaSegments ).setRange( 3, Infinity ).onChange( update );

	thetaSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/ring_geometry/thetaSegments' ) ).setClass( 'Label' ) );
	thetaSegmentsRow.add( thetaSegments );

	container.add( thetaSegmentsRow );

	// phiSegments

	const phiSegmentsRow = new UIRow();
	const phiSegments = new UIInteger( parameters.phiSegments ).setRange( 3, Infinity ).onChange( update );

	phiSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/ring_geometry/phiSegments' ) ).setClass( 'Label' ) );
	phiSegmentsRow.add( phiSegments );

	container.add( phiSegmentsRow );

	// thetaStart

	const thetaStartRow = new UIRow();
	const thetaStart = new UINumber( parameters.thetaStart * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange( update );

	thetaStartRow.add( new UIText( strings.getKey( 'sidebar/geometry/ring_geometry/thetastart' ) ).setClass( 'Label' ) );
	thetaStartRow.add( thetaStart );

	container.add( thetaStartRow );

	// thetaLength

	const thetaLengthRow = new UIRow();
	const thetaLength = new UINumber( parameters.thetaLength * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange( update );

	thetaLengthRow.add( new UIText( strings.getKey( 'sidebar/geometry/ring_geometry/thetalength' ) ).setClass( 'Label' ) );
	thetaLengthRow.add( thetaLength );

	container.add( thetaLengthRow );

	//

	function refreshUI() {

		const parameters = object.geometry.parameters;

		innerRadius.setValue( parameters.innerRadius );
		outerRadius.setValue( parameters.outerRadius );
		thetaSegments.setValue( parameters.thetaSegments );
		phiSegments.setValue( parameters.phiSegments );
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

		editor.execute( new SetGeometryCommand( editor, object, new THREE.RingGeometry(
			innerRadius.getValue(),
			outerRadius.getValue(),
			thetaSegments.getValue(),
			phiSegments.getValue(),
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

- `innerRadius.setValue`
- `outerRadius.setValue`
- `thetaSegments.setValue`
- `phiSegments.setValue`
- `thetaStart.setValue`
- `thetaLength.setValue`

<details><summary>Code</summary>

```typescript
function refreshUI() {

		const parameters = object.geometry.parameters;

		innerRadius.setValue( parameters.innerRadius );
		outerRadius.setValue( parameters.outerRadius );
		thetaSegments.setValue( parameters.thetaSegments );
		phiSegments.setValue( parameters.phiSegments );
		thetaStart.setValue( parameters.thetaStart * THREE.MathUtils.RAD2DEG );
		thetaLength.setValue( parameters.thetaLength * THREE.MathUtils.RAD2DEG );

	}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `editor.execute`
- `innerRadius.getValue`
- `outerRadius.getValue`
- `thetaSegments.getValue`
- `phiSegments.getValue`
- `thetaStart.getValue`
- `thetaLength.getValue`

<details><summary>Code</summary>

```typescript
function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.RingGeometry(
			innerRadius.getValue(),
			outerRadius.getValue(),
			thetaSegments.getValue(),
			phiSegments.getValue(),
			thetaStart.getValue() * THREE.MathUtils.DEG2RAD,
			thetaLength.getValue() * THREE.MathUtils.DEG2RAD
		) ) );

	}
```
</details>


---