[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Geometry.Modifiers.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 9 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Geometry.Modifiers.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIDiv` | `./libs/ui.js` |
| `UIButton` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `computeMikkTSpaceTangents` | `three/addons/utils/BufferGeometryUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `geometry` | `any` | let/var | `object.geometry` | ✗ |
| `computeVertexNormalsButton` | `UIButton` | let/var | `new UIButton( strings.getKey( 'sidebar/geometry/compute_vertex_normals' ) )` | ✗ |
| `computeVertexNormalsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `computeVertexTangentsButton` | `UIButton` | let/var | `new UIButton( strings.getKey( 'sidebar/geometry/compute_vertex_tangents' ) )` | ✗ |
| `computeVertexTangentsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `centerButton` | `UIButton` | let/var | `new UIButton( strings.getKey( 'sidebar/geometry/center' ) )` | ✗ |
| `centerRow` | `UIRow` | let/var | `new UIRow()` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| await-expression | `SidebarGeometryModifiers` | MikkTSpace.ready | *none* |


---

## Functions

### `SidebarGeometryModifiers(editor: any, object: any): any`

**Parameters:**

- **`editor`** `any`
- **`object`** `any`

**Returns:** `any`

**Calls:**

- `new UIDiv().setMarginLeft`
- `strings.getKey`
- `computeVertexNormalsButton.onClick`
- `geometry.computeVertexNormals`
- `signals.geometryChanged.dispatch`
- `computeVertexNormalsRow.add`
- `container.add`
- `geometry.hasAttribute`
- `computeVertexTangentsButton.onClick`
- `computeMikkTSpaceTangents (from three/addons/utils/BufferGeometryUtils.js)`
- `computeVertexTangentsRow.add`
- `centerButton.onClick`
- `geometry.center`
- `centerRow.add`

**Internal Comments:**
```
// Compute Vertex Normals (x2)
// Compute Vertex Tangents
// Center Geometry (x2)
//
```

<details><summary>Code</summary>

```typescript
function SidebarGeometryModifiers( editor, object ) {

	const strings = editor.strings;

	const signals = editor.signals;

	const container = new UIDiv().setMarginLeft( '120px' );

	const geometry = object.geometry;

	// Compute Vertex Normals

	const computeVertexNormalsButton = new UIButton( strings.getKey( 'sidebar/geometry/compute_vertex_normals' ) );
	computeVertexNormalsButton.onClick( function () {

		geometry.computeVertexNormals();

		signals.geometryChanged.dispatch( object );

	} );

	const computeVertexNormalsRow = new UIRow();
	computeVertexNormalsRow.add( computeVertexNormalsButton );
	container.add( computeVertexNormalsRow );

	// Compute Vertex Tangents

	if ( geometry.hasAttribute( 'position' ) && geometry.hasAttribute( 'normal' ) && geometry.hasAttribute( 'uv' ) ) {

		const computeVertexTangentsButton = new UIButton( strings.getKey( 'sidebar/geometry/compute_vertex_tangents' ) );
		computeVertexTangentsButton.onClick( async function () {

			await MikkTSpace.ready;

			computeMikkTSpaceTangents( geometry, MikkTSpace );

			signals.geometryChanged.dispatch( object );

		} );

		const computeVertexTangentsRow = new UIRow();
		computeVertexTangentsRow.add( computeVertexTangentsButton );
		container.add( computeVertexTangentsRow );

	}

	// Center Geometry

	const centerButton = new UIButton( strings.getKey( 'sidebar/geometry/center' ) );
	centerButton.onClick( function () {

		geometry.center();

		signals.geometryChanged.dispatch( object );

	} );

	const centerRow = new UIRow();
	centerRow.add( centerButton );
	container.add( centerRow );

	//

	return container;

}
```
</details>


---