[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Geometry.CapsuleGeometry.js`

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
📂 **`editor/js/Sidebar.Geometry.CapsuleGeometry.js`**

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
| `radiusRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `heightRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `capSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `radialSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `heightSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
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
- `new UIText( strings.getKey( 'sidebar/geometry/capsule_geometry/radius' ) ).setClass`
- `strings.getKey`
- `container.add`
- `new UINumber( parameters.height ).onChange`
- `heightRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/capsule_geometry/height' ) ).setClass`
- `new UIInteger( parameters.capSegments ).setRange( 1, Infinity ).onChange`
- `capSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/capsule_geometry/capseg' ) ).setClass`
- `new UIInteger( parameters.radialSegments ).setRange( 1, Infinity ).onChange`
- `radialSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/capsule_geometry/radialseg' ) ).setClass`
- `new UIInteger( parameters.heightSegments ).setRange( 1, Infinity ).onChange`
- `heightSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/capsule_geometry/heightseg' ) ).setClass`
- `radius.setValue`
- `height.setValue`
- `capSegments.setValue`
- `radialSegments.setValue`
- `heightSegments.setValue`
- `signals.geometryChanged.add`
- `refreshUI`
- `editor.execute`
- `radius.getValue`
- `height.getValue`
- `capSegments.getValue`
- `radialSegments.getValue`
- `heightSegments.getValue`

**Internal Comments:**
```
// radius (x2)
// height (x2)
// capSegments (x2)
// radialSegments (x2)
// heightSegments (x2)
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

	radiusRow.add( new UIText( strings.getKey( 'sidebar/geometry/capsule_geometry/radius' ) ).setClass( 'Label' ) );
	radiusRow.add( radius );

	container.add( radiusRow );

	// height

	const heightRow = new UIRow();
	const height = new UINumber( parameters.height ).onChange( update );

	heightRow.add( new UIText( strings.getKey( 'sidebar/geometry/capsule_geometry/height' ) ).setClass( 'Label' ) );
	heightRow.add( height );

	container.add( heightRow );

	// capSegments

	const capSegmentsRow = new UIRow();
	const capSegments = new UIInteger( parameters.capSegments ).setRange( 1, Infinity ).onChange( update );

	capSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/capsule_geometry/capseg' ) ).setClass( 'Label' ) );
	capSegmentsRow.add( capSegments );

	container.add( capSegmentsRow );

	// radialSegments

	const radialSegmentsRow = new UIRow();
	const radialSegments = new UIInteger( parameters.radialSegments ).setRange( 1, Infinity ).onChange( update );

	radialSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/capsule_geometry/radialseg' ) ).setClass( 'Label' ) );
	radialSegmentsRow.add( radialSegments );

	container.add( radialSegmentsRow );

	// heightSegments

	const heightSegmentsRow = new UIRow();
	const heightSegments = new UIInteger( parameters.heightSegments ).setRange( 1, Infinity ).onChange( update );

	heightSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/capsule_geometry/heightseg' ) ).setClass( 'Label' ) );
	heightSegmentsRow.add( heightSegments );

	container.add( heightSegmentsRow );

	//

	function refreshUI() {

		const parameters = object.geometry.parameters;

		radius.setValue( parameters.radius );
		height.setValue( parameters.height );
		capSegments.setValue( parameters.capSegments );
		radialSegments.setValue( parameters.radialSegments );
		heightSegments.setValue( parameters.heightSegments );

	}

	signals.geometryChanged.add( function ( mesh ) {

		if ( mesh === object ) {

			refreshUI();

		}

	} );

	//

	function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.CapsuleGeometry(
			radius.getValue(),
			height.getValue(),
			capSegments.getValue(),
			radialSegments.getValue(),
			heightSegments.getValue()
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
- `height.setValue`
- `capSegments.setValue`
- `radialSegments.setValue`
- `heightSegments.setValue`

<details><summary>Code</summary>

```typescript
function refreshUI() {

		const parameters = object.geometry.parameters;

		radius.setValue( parameters.radius );
		height.setValue( parameters.height );
		capSegments.setValue( parameters.capSegments );
		radialSegments.setValue( parameters.radialSegments );
		heightSegments.setValue( parameters.heightSegments );

	}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `editor.execute`
- `radius.getValue`
- `height.getValue`
- `capSegments.getValue`
- `radialSegments.getValue`
- `heightSegments.getValue`

<details><summary>Code</summary>

```typescript
function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.CapsuleGeometry(
			radius.getValue(),
			height.getValue(),
			capSegments.getValue(),
			radialSegments.getValue(),
			heightSegments.getValue()
		) ) );

	}
```
</details>


---