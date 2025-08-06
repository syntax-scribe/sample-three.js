[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `USDZExporter.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 20 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/addons/exporters/USDZExporter.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `USDZExporter` | `../../../../examples/jsm/exporters/USDZExporter.js` |
| `unzipSync` | `../../../../examples/jsm/libs/fflate.module.js` |
| `strFromU8` | `../../../../examples/jsm/libs/fflate.module.js` |
| `Scene` | `../../../../src/Three.js` |
| `Mesh` | `../../../../src/Three.js` |
| `MeshStandardMaterial` | `../../../../src/Three.js` |
| `BoxGeometry` | `../../../../src/Three.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `header` | `any` | let/var | `usda.split( '\n' )[ 0 ]` | ✗ |
| `exporter` | `USDZExporter` | let/var | `new USDZExporter()` | ✗ |
| `exporter` | `USDZExporter` | let/var | `new USDZExporter()` | ✗ |
| `scene` | `Scene` | let/var | `new Scene()` | ✗ |
| `geometry` | `BoxGeometry` | let/var | `new BoxGeometry( 1, 1, 1 )` | ✗ |
| `material` | `MeshStandardMaterial` | let/var | `new MeshStandardMaterial( { color: 0x00ff00, roughness: 0.5, metalness: 0.8, } )` | ✗ |
| `mesh` | `Mesh` | let/var | `new Mesh( geometry, material )` | ✗ |
| `result` | `ArrayBuffer` | let/var | `await exporter.parseAsync( scene )` | ✗ |
| `modelFileName` | `"model.usda"` | let/var | `'model.usda'` | ✗ |
| `exporter` | `USDZExporter` | let/var | `new USDZExporter( )` | ✗ |
| `scene` | `Scene` | let/var | `new Scene()` | ✗ |
| `geometry` | `BoxGeometry` | let/var | `new BoxGeometry( 1, 1, 1 )` | ✗ |
| `material1` | `MeshStandardMaterial` | let/var | `new MeshStandardMaterial( { color: 0xff0000 } )` | ✗ |
| `material2` | `MeshStandardMaterial` | let/var | `new MeshStandardMaterial( { color: 0x00ff00 } )` | ✗ |
| `box1` | `Mesh` | let/var | `new Mesh( geometry, material1 )` | ✗ |
| `box2` | `Mesh` | let/var | `new Mesh( geometry, material2 )` | ✗ |
| `options` | `{ onlyVisible: boolean; }` | let/var | `{ onlyVisible: true, }` | ✗ |
| `exportResult` | `ArrayBuffer` | let/var | `await exporter.parseAsync( scene, options )` | ✗ |
| `modelFileName` | `"model.usda"` | let/var | `'model.usda'` | ✗ |
| `exportResult2` | `ArrayBuffer` | let/var | `await exporter.parseAsync( scene, options )` | ✗ |


---

## Functions

### `isValidUSDA(usda: any): boolean`

**Parameters:**

- **`usda`** `any`

**Returns:** `boolean`

**Calls:**

- `usda.split`

<details><summary>Code</summary>

```typescript
function isValidUSDA( usda ) {

	const header = usda.split( '\n' )[ 0 ];
	if ( header !== '#usda 1.0' ) return false;

	return true;

}
```
</details>


---