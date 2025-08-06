[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Geometry.LatheGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 10 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Geometry.LatheGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIDiv` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `UIInteger` | `./libs/ui.js` |
| `UINumber` | `./libs/ui.js` |
| `UIPoints2` | `./libs/ui.three.js` |
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
| `segmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `phiStartRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `phiLengthRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `pointsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `parameters` | `any` | let/var | `object.geometry.parameters` | ✗ |


---

## Functions

### `GeometryParametersPanel(editor: any, object: any): UIDiv`

**Parameters:**

- **`editor`** `any`
- **`object`** `any`

**Returns:** `UIDiv`

**Calls:**

- `new UIInteger( parameters.segments ).onChange`
- `segmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/lathe_geometry/segments' ) ).setClass`
- `strings.getKey`
- `container.add`
- `new UINumber( parameters.phiStart * THREE.MathUtils.RAD2DEG ).onChange`
- `phiStartRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/lathe_geometry/phistart' ) ).setClass`
- `new UINumber( parameters.phiLength * THREE.MathUtils.RAD2DEG ).onChange`
- `phiLengthRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/lathe_geometry/philength' ) ).setClass`
- `pointsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/lathe_geometry/points' ) ).setClass`
- `new UIPoints2().setValue( parameters.points ).onChange`
- `points.setValue`
- `segments.setValue`
- `phiStart.setValue`
- `phiLength.setValue`
- `signals.geometryChanged.add`
- `refreshUI`
- `editor.execute`
- `points.getValue`
- `segments.getValue`
- `phiStart.getValue`
- `phiLength.getValue`

**Internal Comments:**
```
// segments (x2)
// phiStart (x2)
// phiLength (x2)
// points (x2)
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

	// segments

	const segmentsRow = new UIRow();
	const segments = new UIInteger( parameters.segments ).onChange( update );

	segmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/lathe_geometry/segments' ) ).setClass( 'Label' ) );
	segmentsRow.add( segments );

	container.add( segmentsRow );

	// phiStart

	const phiStartRow = new UIRow();
	const phiStart = new UINumber( parameters.phiStart * THREE.MathUtils.RAD2DEG ).onChange( update );

	phiStartRow.add( new UIText( strings.getKey( 'sidebar/geometry/lathe_geometry/phistart' ) ).setClass( 'Label' ) );
	phiStartRow.add( phiStart );

	container.add( phiStartRow );

	// phiLength

	const phiLengthRow = new UIRow();
	const phiLength = new UINumber( parameters.phiLength * THREE.MathUtils.RAD2DEG ).onChange( update );

	phiLengthRow.add( new UIText( strings.getKey( 'sidebar/geometry/lathe_geometry/philength' ) ).setClass( 'Label' ) );
	phiLengthRow.add( phiLength );

	container.add( phiLengthRow );

	// points

	const pointsRow = new UIRow();
	pointsRow.add( new UIText( strings.getKey( 'sidebar/geometry/lathe_geometry/points' ) ).setClass( 'Label' ) );

	const points = new UIPoints2().setValue( parameters.points ).onChange( update );
	pointsRow.add( points );

	container.add( pointsRow );

	//

	function refreshUI() {

		const parameters = object.geometry.parameters;

		points.setValue( parameters.points, false );
		segments.setValue( parameters.segments );
		phiStart.setValue( parameters.phiStart * THREE.MathUtils.RAD2DEG );
		phiLength.setValue( parameters.phiLength * THREE.MathUtils.RAD2DEG );

	}

	signals.geometryChanged.add( function ( mesh ) {

		if ( mesh === object ) {

			refreshUI();

		}

	} );

	//

	function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.LatheGeometry(
			points.getValue(),
			segments.getValue(),
			phiStart.getValue() * THREE.MathUtils.DEG2RAD,
			phiLength.getValue() * THREE.MathUtils.DEG2RAD
		) ) );

	}

	return container;

}
```
</details>

### `refreshUI(): void`

**Returns:** `void`

**Calls:**

- `points.setValue`
- `segments.setValue`
- `phiStart.setValue`
- `phiLength.setValue`

<details><summary>Code</summary>

```typescript
function refreshUI() {

		const parameters = object.geometry.parameters;

		points.setValue( parameters.points, false );
		segments.setValue( parameters.segments );
		phiStart.setValue( parameters.phiStart * THREE.MathUtils.RAD2DEG );
		phiLength.setValue( parameters.phiLength * THREE.MathUtils.RAD2DEG );

	}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `editor.execute`
- `points.getValue`
- `segments.getValue`
- `phiStart.getValue`
- `phiLength.getValue`

<details><summary>Code</summary>

```typescript
function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.LatheGeometry(
			points.getValue(),
			segments.getValue(),
			phiStart.getValue() * THREE.MathUtils.DEG2RAD,
			phiLength.getValue() * THREE.MathUtils.DEG2RAD
		) ) );

	}
```
</details>


---