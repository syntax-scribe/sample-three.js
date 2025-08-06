[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Geometry.ShapeGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Geometry.ShapeGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIDiv` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `UIInteger` | `./libs/ui.js` |
| `UIButton` | `./libs/ui.js` |
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
| `curveSegmentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `parameters` | `any` | let/var | `object.geometry.parameters` | ✗ |


---

## Functions

### `GeometryParametersPanel(editor: any, object: any): UIDiv`

**Parameters:**

- **`editor`** `any`
- **`object`** `any`

**Returns:** `UIDiv`

**Calls:**

- `new UIInteger( parameters.curveSegments || 12 ).onChange( changeShape ).setRange`
- `curveSegmentsRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/shape_geometry/curveSegments' ) ).setClass`
- `strings.getKey`
- `container.add`
- `new UIButton( strings.getKey( 'sidebar/geometry/shape_geometry/extrude' ) ).onClick( toExtrude ).setClass( 'Label' ).setMarginLeft`
- `curveSegments.setValue`
- `signals.geometryChanged.add`
- `refreshUI`
- `editor.execute`
- `curveSegments.getValue`

**Internal Comments:**
```
// curveSegments (x2)
// to extrude (x2)
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

	// curveSegments

	const curveSegmentsRow = new UIRow();
	const curveSegments = new UIInteger( parameters.curveSegments || 12 ).onChange( changeShape ).setRange( 1, Infinity );

	curveSegmentsRow.add( new UIText( strings.getKey( 'sidebar/geometry/shape_geometry/curveSegments' ) ).setClass( 'Label' ) );
	curveSegmentsRow.add( curveSegments );

	container.add( curveSegmentsRow );

	// to extrude
	const button = new UIButton( strings.getKey( 'sidebar/geometry/shape_geometry/extrude' ) ).onClick( toExtrude ).setClass( 'Label' ).setMarginLeft( '120px' );
	container.add( button );

	//

	function refreshUI() {

		const parameters = object.geometry.parameters;

		curveSegments.setValue( parameters.curveSegments );

	}

	signals.geometryChanged.add( function ( mesh ) {

		if ( mesh === object ) {

			refreshUI();

		}

	} );

	//

	function changeShape() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.ShapeGeometry(
			parameters.shapes,
			curveSegments.getValue()
		) ) );

	}

	function toExtrude() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.ExtrudeGeometry(
			parameters.shapes, {
				curveSegments: curveSegments.getValue()
			}
		) ) );

	}

	return container;

}
```
</details>

### `refreshUI(): void`

**Returns:** `void`

**Calls:**

- `curveSegments.setValue`

<details><summary>Code</summary>

```typescript
function refreshUI() {

		const parameters = object.geometry.parameters;

		curveSegments.setValue( parameters.curveSegments );

	}
```
</details>

### `changeShape(): void`

**Returns:** `void`

**Calls:**

- `editor.execute`
- `curveSegments.getValue`

<details><summary>Code</summary>

```typescript
function changeShape() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.ShapeGeometry(
			parameters.shapes,
			curveSegments.getValue()
		) ) );

	}
```
</details>

### `toExtrude(): void`

**Returns:** `void`

**Calls:**

- `editor.execute`
- `curveSegments.getValue`

<details><summary>Code</summary>

```typescript
function toExtrude() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.ExtrudeGeometry(
			parameters.shapes, {
				curveSegments: curveSegments.getValue()
			}
		) ) );

	}
```
</details>


---