[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Geometry.OctahedronGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 8 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Geometry.OctahedronGeometry.js`**

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
| `detailRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
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
- `new UIText( strings.getKey( 'sidebar/geometry/octahedron_geometry/radius' ) ).setClass`
- `strings.getKey`
- `container.add`
- `new UIInteger( parameters.detail ).setRange( 0, Infinity ).onChange`
- `detailRow.add`
- `new UIText( strings.getKey( 'sidebar/geometry/octahedron_geometry/detail' ) ).setClass`
- `radius.setValue`
- `detail.setValue`
- `signals.geometryChanged.add`
- `refreshUI`
- `editor.execute`
- `radius.getValue`
- `detail.getValue`

**Internal Comments:**
```
// radius (x2)
// detail (x2)
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

	radiusRow.add( new UIText( strings.getKey( 'sidebar/geometry/octahedron_geometry/radius' ) ).setClass( 'Label' ) );
	radiusRow.add( radius );

	container.add( radiusRow );

	// detail

	const detailRow = new UIRow();
	const detail = new UIInteger( parameters.detail ).setRange( 0, Infinity ).onChange( update );

	detailRow.add( new UIText( strings.getKey( 'sidebar/geometry/octahedron_geometry/detail' ) ).setClass( 'Label' ) );
	detailRow.add( detail );

	container.add( detailRow );

	//

	function refreshUI() {

		const parameters = object.geometry.parameters;

		radius.setValue( parameters.radius );
		detail.setValue( parameters.detail );

	}

	signals.geometryChanged.add( function ( mesh ) {

		if ( mesh === object ) {

			refreshUI();

		}

	} );

	//

	function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.OctahedronGeometry(
			radius.getValue(),
			detail.getValue()
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
- `detail.setValue`

<details><summary>Code</summary>

```typescript
function refreshUI() {

		const parameters = object.geometry.parameters;

		radius.setValue( parameters.radius );
		detail.setValue( parameters.detail );

	}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `editor.execute`
- `radius.getValue`
- `detail.getValue`

<details><summary>Code</summary>

```typescript
function update() {

		editor.execute( new SetGeometryCommand( editor, object, new THREE.OctahedronGeometry(
			radius.getValue(),
			detail.getValue()
		) ) );

	}
```
</details>


---