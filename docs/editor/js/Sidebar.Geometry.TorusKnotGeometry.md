[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Geometry.TorusKnotGeometry.js`

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
📂 **`editor/js/Sidebar.Geometry.TorusKnotGeometry.js`**

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
| `tubularSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `radialSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `pRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `qRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
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
- `new UIText( strings.getKey( 'sidebar/geometry/torusKnot_geometry/radius' ) ).setClass`
- `strings.getKey`
- `container.add`
- `new UINumber( parameters.tube ).onChange`
- `tubeRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/torusKnot_geometry/tube' ) ).setClass`
- `new UIInteger( parameters.tubularSegments ).setRange( 1, Infinity ).onChange`
- `tubularSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/torusKnot_geometry/tubularsegments' ) ).setClass`
- `new UIInteger( parameters.radialSegments ).setRange( 1, Infinity ).onChange`
- `radialSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/torusKnot_geometry/radialsegments' ) ).setClass`
- `new UIInteger( parameters.p ).onChange`
- `pRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/torusKnot_geometry/p' ) ).setClass`
- `new UIInteger( parameters.q ).onChange`
- `qRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/torusKnot_geometry/q' ) ).setClass`
- `radius.setValue`
- `tube.setValue`
- `tubularSegments.setValue`
- `radialSegments.setValue`
- `p.setValue`
- `q.setValue`
- `signals.geometryChanged.add`
- `refreshUI`
- `editor.execute`
- `radius.getValue`
- `tube.getValue`
- `tubularSegments.getValue`
- `radialSegments.getValue`
- `p.getValue`
- `q.getValue`

**Internal Comments:**
```
// radius (x2)
// tube (x2)
// tubularSegments (x2)
// radialSegments (x2)
// p (x2)
// q (x2)
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

	radiusRow.add( new UIText( strings.getKey( 'sidebar/geometry/torusKnot_geometry/radius' ) ).setClass( 'Label' ) );
	radiusRow.add( radius );

	container.add( radiusRow );

	// tube

	const tubeRow = new UIRow();
	const tube = new UINumber( parameters.tube ).onChange( update );

	tubeRow.add( new UIText( strings.getKey( 'sidebar/geometry/torusKnot_geometry/tube' ) ).setClass( 'Label' ) );
	tubeRow.add( tube );

	container.add( tubeRow );

	// tubularSegments

	const tubularSegmentsRow = new UIRow();
	const tubularSegments = new UIInteger( parameters.tubularSegments ).setRange( 1, Infinity ).onChange( update );

	tubularSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/torusKnot_geometry/tubularsegments' ) ).setClass( 'Label' ) );
	tubularSegmentsRow.add( tubularSegments );

	container.add( tubularSegmentsRow );

	// radialSegments

	const radialSegmentsRow = new UIRow();
	const radialSegments = new UIInteger( parameters.radialSegments ).setRange( 1, Infinity ).onChange( update );

	radialSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/torusKnot_geometry/radialsegments' ) ).setClass( 'Label' ) );
	radialSegmentsRow.add( radialSegments );

	container.add( radialSegmentsRow );

	// p

	const pRow = new UIRow();
	const p = new UIInteger( parameters.p ).onChange( update );

	pRow.add( new UIText( strings.getKey( 'sidebar/geometry/torusKnot_geometry/p' ) ).setClass( 'Label' ) );
	pRow.add( p );

	container.add( pRow );

	// q

	const qRow = new UIRow();
	const q = new UIInteger( parameters.q ).onChange( update );

	qRow.add( new UIText( strings.getKey( 'sidebar/geometry/torusKnot_geometry/q' ) ).setClass( 'Label' ) );
	qRow.add( q );

	container.add( qRow );

	//

	function refreshUI() {

		const parameters = object.geometry.parameters;

		radius.setValue( parameters.radius );
		tube.setValue( parameters.tube );
		tubularSegments.setValue( parameters.tubularSegments );
		radialSegments.setValue( parameters.radialSegments );
		p.setValue( parameters.p );
		q.setValue( parameters.q );

	}

	signals.geometryChanged.add( function ( mesh ) {

		if ( mesh === object ) {

			refreshUI();

		}

	} );

	//

	function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.TorusKnotGeometry(
			radius.getValue(),
			tube.getValue(),
			tubularSegments.getValue(),
			radialSegments.getValue(),
			p.getValue(),
			q.getValue()
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
- `tubularSegments.setValue`
- `radialSegments.setValue`
- `p.setValue`
- `q.setValue`

<details><summary>Code</summary>

```typescript
function refreshUI() {

		const parameters = object.geometry.parameters;

		radius.setValue( parameters.radius );
		tube.setValue( parameters.tube );
		tubularSegments.setValue( parameters.tubularSegments );
		radialSegments.setValue( parameters.radialSegments );
		p.setValue( parameters.p );
		q.setValue( parameters.q );

	}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `editor.execute`
- `radius.getValue`
- `tube.getValue`
- `tubularSegments.getValue`
- `radialSegments.getValue`
- `p.getValue`
- `q.getValue`

<details><summary>Code</summary>

```typescript
function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.TorusKnotGeometry(
			radius.getValue(),
			tube.getValue(),
			tubularSegments.getValue(),
			radialSegments.getValue(),
			p.getValue(),
			q.getValue()
		) ) );

	}
```
</details>


---