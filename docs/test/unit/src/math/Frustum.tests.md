[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Frustum.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 📦 Imports | 12 |
| 📊 Variables & Constants | 36 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)

## 🛠️ File Location:
📂 **`test/unit/src/math/Frustum.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Frustum` | `../../../../src/math/Frustum.js` |
| `Sphere` | `../../../../src/math/Sphere.js` |
| `Plane` | `../../../../src/math/Plane.js` |
| `Sprite` | `../../../../src/objects/Sprite.js` |
| `Vector3` | `../../../../src/math/Vector3.js` |
| `Matrix4` | `../../../../src/math/Matrix4.js` |
| `Box3` | `../../../../src/math/Box3.js` |
| `Mesh` | `../../../../src/objects/Mesh.js` |
| `BoxGeometry` | `../../../../src/geometries/BoxGeometry.js` |
| `zero3` | `../../utils/math-constants.js` |
| `one3` | `../../utils/math-constants.js` |
| `eps` | `../../utils/math-constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `unit3` | `Vector3` | let/var | `new Vector3( 1, 0, 0 )` | ✗ |
| `a` | `Frustum` | let/var | `new Frustum()` | ✗ |
| `pDefault` | `Plane` | let/var | `new Plane()` | ✗ |
| `p0` | `Plane` | let/var | `new Plane( unit3, - 1 )` | ✗ |
| `p1` | `Plane` | let/var | `new Plane( unit3, 1 )` | ✗ |
| `p2` | `Plane` | let/var | `new Plane( unit3, 2 )` | ✗ |
| `p3` | `Plane` | let/var | `new Plane( unit3, 3 )` | ✗ |
| `p4` | `Plane` | let/var | `new Plane( unit3, 4 )` | ✗ |
| `p5` | `Plane` | let/var | `new Plane( unit3, 5 )` | ✗ |
| `a` | `Frustum` | let/var | `new Frustum()` | ✗ |
| `p0` | `Plane` | let/var | `new Plane( unit3, - 1 )` | ✗ |
| `p1` | `Plane` | let/var | `new Plane( unit3, 1 )` | ✗ |
| `p2` | `Plane` | let/var | `new Plane( unit3, 2 )` | ✗ |
| `p3` | `Plane` | let/var | `new Plane( unit3, 3 )` | ✗ |
| `p4` | `Plane` | let/var | `new Plane( unit3, 4 )` | ✗ |
| `p5` | `Plane` | let/var | `new Plane( unit3, 5 )` | ✗ |
| `p0` | `Plane` | let/var | `new Plane( unit3, - 1 )` | ✗ |
| `p1` | `Plane` | let/var | `new Plane( unit3, 1 )` | ✗ |
| `p2` | `Plane` | let/var | `new Plane( unit3, 2 )` | ✗ |
| `p3` | `Plane` | let/var | `new Plane( unit3, 3 )` | ✗ |
| `p4` | `Plane` | let/var | `new Plane( unit3, 4 )` | ✗ |
| `p5` | `Plane` | let/var | `new Plane( unit3, 5 )` | ✗ |
| `b` | `Frustum` | let/var | `new Frustum( p0, p1, p2, p3, p4, p5 )` | ✗ |
| `p0` | `Plane` | let/var | `new Plane( unit3, - 1 )` | ✗ |
| `p1` | `Plane` | let/var | `new Plane( unit3, 1 )` | ✗ |
| `p2` | `Plane` | let/var | `new Plane( unit3, 2 )` | ✗ |
| `p3` | `Plane` | let/var | `new Plane( unit3, 3 )` | ✗ |
| `p4` | `Plane` | let/var | `new Plane( unit3, 4 )` | ✗ |
| `p5` | `Plane` | let/var | `new Plane( unit3, 5 )` | ✗ |
| `b` | `Frustum` | let/var | `new Frustum( p0, p1, p2, p3, p4, p5 )` | ✗ |
| `object` | `Mesh` | let/var | `new Mesh( new BoxGeometry( 1, 1, 1 ) )` | ✗ |
| `intersects` | `any` | let/var | `*not shown*` | ✗ |
| `sprite` | `Sprite` | let/var | `new Sprite()` | ✗ |
| `intersects` | `any` | let/var | `*not shown*` | ✗ |
| `box` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `intersects` | `any` | let/var | `*not shown*` | ✗ |


---