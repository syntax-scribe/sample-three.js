[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Geometry.CircleGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 10 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Geometry.CircleGeometry.js`**

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
| `segmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
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
- `new UIText( strings.getKey( 'sidebar/geometry/circle_geometry/radius' ) ).setClass`
- `strings.getKey`
- `container.add`
- `new UIInteger( parameters.segments ).setRange( 3, Infinity ).onChange`
- `segmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/circle_geometry/segments' ) ).setClass`
- `new UINumber( parameters.thetaStart * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange`
- `thetaStartRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/circle_geometry/thetastart' ) ).setClass`
- `new UINumber( parameters.thetaLength * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange`
- `thetaLengthRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/circle_geometry/thetalength' ) ).setClass`
- `radius.setValue`
- `segments.setValue`
- `thetaStart.setValue`
- `thetaLength.setValue`
- `signals.geometryChanged.add`
- `refreshUI`
- `editor.execute`
- `radius.getValue`
- `segments.getValue`
- `thetaStart.getValue`
- `thetaLength.getValue`

**Internal Comments:**
```
// radius (x2)
// segments (x2)
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

	radiusRow.add( new UIText( strings.getKey( 'sidebar/geometry/circle_geometry/radius' ) ).setClass( 'Label' ) );
	radiusRow.add( radius );

	container.add( radiusRow );

	// segments

	const segmentsRow = new UIRow();
	const segments = new UIInteger( parameters.segments ).setRange( 3, Infinity ).onChange( update );

	segmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/circle_geometry/segments' ) ).setClass( 'Label' ) );
	segmentsRow.add( segments );

	container.add( segmentsRow );

	// thetaStart

	const thetaStartRow = new UIRow();
	const thetaStart = new UINumber( parameters.thetaStart * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange( update );

	thetaStartRow.add( new UIText( strings.getKey( 'sidebar/geometry/circle_geometry/thetastart' ) ).setClass( 'Label' ) );
	thetaStartRow.add( thetaStart );

	container.add( thetaStartRow );

	// thetaLength

	const thetaLengthRow = new UIRow();
	const thetaLength = new UINumber( parameters.thetaLength * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange( update );

	thetaLengthRow.add( new UIText( strings.getKey( 'sidebar/geometry/circle_geometry/thetalength' ) ).setClass( 'Label' ) );
	thetaLengthRow.add( thetaLength );

	container.add( thetaLengthRow );

	//

	function refreshUI() {

		const parameters = object.geometry.parameters;

		radius.setValue( parameters.radius );
		segments.setValue( parameters.segments );
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

		editor.execute( new SetGeometryCommand( editor, object, new THREE.CircleGeometry(
			radius.getValue(),
			segments.getValue(),
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
- `segments.setValue`
- `thetaStart.setValue`
- `thetaLength.setValue`

<details><summary>Code</summary>

```typescript
function refreshUI() {

		const parameters = object.geometry.parameters;

		radius.setValue( parameters.radius );
		segments.setValue( parameters.segments );
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
- `segments.getValue`
- `thetaStart.getValue`
- `thetaLength.getValue`

<details><summary>Code</summary>

```typescript
function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.CircleGeometry(
			radius.getValue(),
			segments.getValue(),
			thetaStart.getValue() * THREE.MathUtils.DEG2RAD,
			thetaLength.getValue() * THREE.MathUtils.DEG2RAD
		) ) );

	}
```
</details>


---