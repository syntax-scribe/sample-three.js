[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `PropertyBinding.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 📦 Imports | 4 |
| 📊 Variables & Constants | 15 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)

## 🛠️ File Location:
📂 **`test/unit/src/animation/PropertyBinding.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `PropertyBinding` | `../../../../src/animation/PropertyBinding.js` |
| `BoxGeometry` | `../../../../src/geometries/BoxGeometry.js` |
| `Mesh` | `../../../../src/objects/Mesh.js` |
| `MeshBasicMaterial` | `../../../../src/materials/MeshBasicMaterial.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `geometry` | `BoxGeometry` | let/var | `new BoxGeometry()` | ✗ |
| `material` | `MeshBasicMaterial` | let/var | `new MeshBasicMaterial()` | ✗ |
| `mesh` | `Mesh` | let/var | `new Mesh( geometry, material )` | ✗ |
| `path` | `".material.opacity"` | let/var | `'.material.opacity'` | ✗ |
| `parsedPath` | `{ nodeName: string; objectName: strin...` | let/var | `{ nodeName: '', objectName: 'material', objectIndex: undefined, propertyName:...` | ✗ |
| `object` | `PropertyBinding` | let/var | `new PropertyBinding( mesh, path )` | ✗ |
| `object_all` | `PropertyBinding` | let/var | `new PropertyBinding( mesh, path, parsedPath )` | ✗ |
| `paths` | `(string \| { nodeName: string; object...` | let/var | `[ [ '.property', { nodeName: undefined, objectName: undefined, objectIndex: u...` | ✗ |
| `paths` | `string[]` | let/var | `[ '.material.opacity', '.material[opacity]' ]` | ✗ |
| `originalValue` | `0` | let/var | `0` | ✗ |
| `expectedValue` | `1` | let/var | `1` | ✗ |
| `geometry` | `BoxGeometry` | let/var | `new BoxGeometry()` | ✗ |
| `material` | `MeshBasicMaterial` | let/var | `new MeshBasicMaterial()` | ✗ |
| `mesh` | `Mesh` | let/var | `new Mesh( geometry, material )` | ✗ |
| `binding` | `PropertyBinding` | let/var | `new PropertyBinding( mesh, path, null )` | ✗ |


---