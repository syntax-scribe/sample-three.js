[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Geometry.TorusGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Geometry.TorusGeometry.js`**

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
| `tubeRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `radialSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `tubularSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `arcRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
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
- `new UIText( strings.getKey( 'sidebar/geometry/torus_geometry/radius' ) ).setClass`
- `strings.getKey`
- `container.add`
- `new UINumber( parameters.tube ).onChange`
- `tubeRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/torus_geometry/tube' ) ).setClass`
- `new UIInteger( parameters.radialSegments ).setRange( 1, Infinity ).onChange`
- `radialSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/torus_geometry/radialsegments' ) ).setClass`
- `new UIInteger( parameters.tubularSegments ).setRange( 1, Infinity ).onChange`
- `tubularSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/torus_geometry/tubularsegments' ) ).setClass`
- `new UINumber( parameters.arc * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange`
- `arcRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/torus_geometry/arc' ) ).setClass`
- `radius.setValue`
- `tube.setValue`
- `radialSegments.setValue`
- `tubularSegments.setValue`
- `arc.setValue`
- `signals.geometryChanged.add`
- `refreshUI`
- `editor.execute`
- `radius.getValue`
- `tube.getValue`
- `radialSegments.getValue`
- `tubularSegments.getValue`
- `arc.getValue`

**Internal Comments:**
```
// radius (x2)
// tube (x2)
// radialSegments (x2)
// tubularSegments (x2)
// arc (x2)
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

	radiusRow.add( new UIText( strings.getKey( 'sidebar/geometry/torus_geometry/radius' ) ).setClass( 'Label' ) );
	radiusRow.add( radius );

	container.add( radiusRow );

	// tube

	const tubeRow = new UIRow();
	const tube = new UINumber( parameters.tube ).onChange( update );

	tubeRow.add( new UIText( strings.getKey( 'sidebar/geometry/torus_geometry/tube' ) ).setClass( 'Label' ) );
	tubeRow.add( tube );

	container.add( tubeRow );

	// radialSegments

	const radialSegmentsRow = new UIRow();
	const radialSegments = new UIInteger( parameters.radialSegments ).setRange( 1, Infinity ).onChange( update );

	radialSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/torus_geometry/radialsegments' ) ).setClass( 'Label' ) );
	radialSegmentsRow.add( radialSegments );

	container.add( radialSegmentsRow );

	// tubularSegments

	const tubularSegmentsRow = new UIRow();
	const tubularSegments = new UIInteger( parameters.tubularSegments ).setRange( 1, Infinity ).onChange( update );

	tubularSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/torus_geometry/tubularsegments' ) ).setClass( 'Label' ) );
	tubularSegmentsRow.add( tubularSegments );

	container.add( tubularSegmentsRow );

	// arc

	const arcRow = new UIRow();
	const arc = new UINumber( parameters.arc * THREE.MathUtils.RAD2DEG ).setUnit( '°' ).setStep( 10 ).onChange( update );

	arcRow.add( new UIText( strings.getKey( 'sidebar/geometry/torus_geometry/arc' ) ).setClass( 'Label' ) );
	arcRow.add( arc );

	container.add( arcRow );

	//

	function refreshUI() {

		const parameters = object.geometry.parameters;

		radius.setValue( parameters.radius );
		tube.setValue( parameters.tube );
		radialSegments.setValue( parameters.radialSegments );
		tubularSegments.setValue( parameters.tubularSegments );
		arc.setValue( parameters.arc * THREE.MathUtils.RAD2DEG );

	}

	signals.geometryChanged.add( function ( mesh ) {

		if ( mesh === object ) {

			refreshUI();

		}

	} );

	//

	function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.TorusGeometry(
			radius.getValue(),
			tube.getValue(),
			radialSegments.getValue(),
			tubularSegments.getValue(),
			arc.getValue() * THREE.MathUtils.DEG2RAD
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
- `tube.setValue`
- `radialSegments.setValue`
- `tubularSegments.setValue`
- `arc.setValue`

<details><summary>Code</summary>

```typescript
function refreshUI() {

		const parameters = object.geometry.parameters;

		radius.setValue( parameters.radius );
		tube.setValue( parameters.tube );
		radialSegments.setValue( parameters.radialSegments );
		tubularSegments.setValue( parameters.tubularSegments );
		arc.setValue( parameters.arc * THREE.MathUtils.RAD2DEG );

	}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `editor.execute`
- `radius.getValue`
- `tube.getValue`
- `radialSegments.getValue`
- `tubularSegments.getValue`
- `arc.getValue`

<details><summary>Code</summary>

```typescript
function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.TorusGeometry(
			radius.getValue(),
			tube.getValue(),
			radialSegments.getValue(),
			tubularSegments.getValue(),
			arc.getValue() * THREE.MathUtils.DEG2RAD
		) ) );

	}
```
</details>


---