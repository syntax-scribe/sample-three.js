[⬅️ Back to Table of Contents](../../index.md)

# 📄 `threejs-voxel-geometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 📦 Imports | 1 |
| 📊 Variables & Constants | 15 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)

## 🛠️ File Location:
📂 **`manual/resources/threejs-voxel-geometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `threejsLessonUtils` | `./threejs-lesson-utils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `isDarkMode` | `boolean` | let/var | `darkMatcher.matches` | ✗ |
| `darkColors` | `{ wire: string; }` | let/var | `{ wire: '#DDD', }` | ✗ |
| `lightColors` | `{ wire: string; }` | let/var | `{ wire: '#000', }` | ✗ |
| `colors` | `{ wire: string; }` | let/var | `isDarkMode ? darkColors : lightColors` | ✗ |
| `geometries` | `any[]` | let/var | `[]` | ✗ |
| `width` | `3` | let/var | `3` | ✗ |
| `height` | `2` | let/var | `2` | ✗ |
| `depth` | `2` | let/var | `2` | ✗ |
| `geometry` | `any` | let/var | `new THREE.BoxGeometry( 1, 1, 1 )` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshBasicMaterial( { color: colors.wire, wireframe: true, } )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( mergedGeometry, material )` | ✗ |
| `base` | `any` | let/var | `new THREE.Object3D()` | ✗ |
| `geometry` | `any` | let/var | `new THREE.BoxGeometry( 3, 2, 2, 3, 2, 2 )` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshBasicMaterial( { color: colors.wire, wireframe: true, } )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, material )` | ✗ |


---