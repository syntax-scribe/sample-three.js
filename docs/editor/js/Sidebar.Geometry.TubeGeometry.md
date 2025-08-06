[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Geometry.TubeGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 12 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Geometry.TubeGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIDiv` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `UIInteger` | `./libs/ui.js` |
| `UISelect` | `./libs/ui.js` |
| `UICheckbox` | `./libs/ui.js` |
| `UINumber` | `./libs/ui.js` |
| `UIPoints3` | `./libs/ui.three.js` |
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
| `pointsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `radiusRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `tubularSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `radialSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `closedRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `curveTypeRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `parameters` | `any` | let/var | `object.geometry.parameters` | ✗ |


---

## Functions

### `GeometryParametersPanel(editor: any, object: any): UIDiv`

**Parameters:**

- **`editor`** `any`
- **`object`** `any`

**Returns:** `UIDiv`

**Calls:**

- `pointsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/tube_geometry/path' ) ).setClass`
- `strings.getKey`
- `new UIPoints3().setValue( parameters.path.points ).onChange`
- `container.add`
- `new UINumber( parameters.radius ).onChange`
- `radiusRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/tube_geometry/radius' ) ).setClass`
- `new UIInteger( parameters.tubularSegments ).onChange`
- `tubularSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/tube_geometry/tubularsegments' ) ).setClass`
- `new UIInteger( parameters.radialSegments ).onChange`
- `radialSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/tube_geometry/radialsegments' ) ).setClass`
- `new UICheckbox( parameters.closed ).onChange`
- `closedRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/tube_geometry/closed' ) ).setClass`
- `new UISelect().setOptions( { centripetal: 'centripetal', chordal: 'chordal', catmullrom: 'catmullrom' } ).setValue( parameters.path.curveType ).onChange`
- `curveTypeRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/tube_geometry/curvetype' ) ).setClass`
- `new UIRow().setDisplay`
- `curveType.getValue`
- `new UINumber( parameters.path.tension ).setStep( 0.01 ).onChange`
- `tensionRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/tube_geometry/tension' ) ).setClass`
- `tubularSegments.setValue`
- `radius.setValue`
- `radialSegments.setValue`
- `closed.setValue`
- `points.setValue`
- `curveType.setValue`
- `tension.setValue`
- `tensionRow.setDisplay`
- `signals.geometryChanged.add`
- `refreshUI`
- `editor.execute`
- `points.getValue`
- `closed.getValue`
- `tension.getValue`
- `tubularSegments.getValue`
- `radius.getValue`
- `radialSegments.getValue`

**Internal Comments:**
```
// points (x2)
// radius (x2)
// tubularSegments (x2)
// radialSegments (x2)
// closed (x2)
// curveType (x2)
// tension (x2)
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

	// points

	const pointsRow = new UIRow();
	pointsRow.add( new UIText( strings.getKey( 'sidebar/geometry/tube_geometry/path' ) ).setClass( 'Label' ) );

	const points = new UIPoints3().setValue( parameters.path.points ).onChange( update );
	pointsRow.add( points );

	container.add( pointsRow );

	// radius

	const radiusRow = new UIRow();
	const radius = new UINumber( parameters.radius ).onChange( update );

	radiusRow.add( new UIText( strings.getKey( 'sidebar/geometry/tube_geometry/radius' ) ).setClass( 'Label' ) );
	radiusRow.add( radius );

	container.add( radiusRow );

	// tubularSegments

	const tubularSegmentsRow = new UIRow();
	const tubularSegments = new UIInteger( parameters.tubularSegments ).onChange( update );

	tubularSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/tube_geometry/tubularsegments' ) ).setClass( 'Label' ) );
	tubularSegmentsRow.add( tubularSegments );

	container.add( tubularSegmentsRow );

	// radialSegments

	const radialSegmentsRow = new UIRow();
	const radialSegments = new UIInteger( parameters.radialSegments ).onChange( update );

	radialSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/tube_geometry/radialsegments' ) ).setClass( 'Label' ) );
	radialSegmentsRow.add( radialSegments );

	container.add( radialSegmentsRow );

	// closed

	const closedRow = new UIRow();
	const closed = new UICheckbox( parameters.closed ).onChange( update );

	closedRow.add( new UIText( strings.getKey( 'sidebar/geometry/tube_geometry/closed' ) ).setClass( 'Label' ) );
	closedRow.add( closed );

	container.add( closedRow );

	// curveType

	const curveTypeRow = new UIRow();
	const curveType = new UISelect().setOptions( { centripetal: 'centripetal', chordal: 'chordal', catmullrom: 'catmullrom' } ).setValue( parameters.path.curveType ).onChange( update );

	curveTypeRow.add( new UIText( strings.getKey( 'sidebar/geometry/tube_geometry/curvetype' ) ).setClass( 'Label' ), curveType );

	container.add( curveTypeRow );

	// tension

	const tensionRow = new UIRow().setDisplay( curveType.getValue() == 'catmullrom' ? '' : 'none' );
	const tension = new UINumber( parameters.path.tension ).setStep( 0.01 ).onChange( update );

	tensionRow.add( new UIText( strings.getKey( 'sidebar/geometry/tube_geometry/tension' ) ).setClass( 'Label' ), tension );

	container.add( tensionRow );

	//

	function refreshUI() {

		const parameters = object.geometry.parameters;

		tubularSegments.setValue( parameters.tubularSegments );
		radius.setValue( parameters.radius );
		radialSegments.setValue( parameters.radialSegments );
		closed.setValue( parameters.closed );

		points.setValue( parameters.path.points, false );
		curveType.setValue( parameters.path.curveType );
		tension.setValue( parameters.path.tension );

		tensionRow.setDisplay( curveType.getValue() == 'catmullrom' ? '' : 'none' );

	}

	signals.geometryChanged.add( function ( mesh ) {

		if ( mesh === object ) {

			refreshUI();

		}

	} );

	//

	function update() {

		tensionRow.setDisplay( curveType.getValue() == 'catmullrom' ? '' : 'none' );

		editor.execute( new SetGeometryCommand( editor, object, new THREE.TubeGeometry(
			new THREE.CatmullRomCurve3( points.getValue(), closed.getValue(), curveType.getValue(), tension.getValue() ),
			tubularSegments.getValue(),
			radius.getValue(),
			radialSegments.getValue(),
			closed.getValue()
		) ) );

	}

	return container;

}
```
</details>

### `refreshUI(): void`

**Returns:** `void`

**Calls:**

- `tubularSegments.setValue`
- `radius.setValue`
- `radialSegments.setValue`
- `closed.setValue`
- `points.setValue`
- `curveType.setValue`
- `tension.setValue`
- `tensionRow.setDisplay`
- `curveType.getValue`

<details><summary>Code</summary>

```typescript
function refreshUI() {

		const parameters = object.geometry.parameters;

		tubularSegments.setValue( parameters.tubularSegments );
		radius.setValue( parameters.radius );
		radialSegments.setValue( parameters.radialSegments );
		closed.setValue( parameters.closed );

		points.setValue( parameters.path.points, false );
		curveType.setValue( parameters.path.curveType );
		tension.setValue( parameters.path.tension );

		tensionRow.setDisplay( curveType.getValue() == 'catmullrom' ? '' : 'none' );

	}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `tensionRow.setDisplay`
- `curveType.getValue`
- `editor.execute`
- `points.getValue`
- `closed.getValue`
- `tension.getValue`
- `tubularSegments.getValue`
- `radius.getValue`
- `radialSegments.getValue`

<details><summary>Code</summary>

```typescript
function update() {

		tensionRow.setDisplay( curveType.getValue() == 'catmullrom' ? '' : 'none' );

		editor.execute( new SetGeometryCommand( editor, object, new THREE.TubeGeometry(
			new THREE.CatmullRomCurve3( points.getValue(), closed.getValue(), curveType.getValue(), tension.getValue() ),
			tubularSegments.getValue(),
			radius.getValue(),
			radialSegments.getValue(),
			closed.getValue()
		) ) );

	}
```
</details>


---