[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Ray.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 📦 Imports | 11 |
| 📊 Variables & Constants | 46 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)

## 🛠️ File Location:
📂 **`test/unit/src/math/Ray.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Ray` | `../../../../src/math/Ray.js` |
| `Box3` | `../../../../src/math/Box3.js` |
| `Vector3` | `../../../../src/math/Vector3.js` |
| `Sphere` | `../../../../src/math/Sphere.js` |
| `Plane` | `../../../../src/math/Plane.js` |
| `Matrix4` | `../../../../src/math/Matrix4.js` |
| `zero3` | `../../utils/math-constants.js` |
| `one3` | `../../utils/math-constants.js` |
| `two3` | `../../utils/math-constants.js` |
| `eps` | `../../utils/math-constants.js` |
| `posInf3` | `../../utils/math-constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `a` | `Ray` | let/var | `new Ray()` | ✗ |
| `a` | `Ray` | let/var | `new Ray()` | ✗ |
| `a` | `Ray` | let/var | `new Ray( one3.clone(), new Vector3( 0, 0, 1 ) )` | ✗ |
| `a` | `Ray` | let/var | `new Ray( zero3.clone(), one3.clone() )` | ✗ |
| `a` | `Ray` | let/var | `new Ray( one3.clone(), new Vector3( 0, 0, 1 ) )` | ✗ |
| `point` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Ray` | let/var | `new Ray( two3.clone(), one3.clone() )` | ✗ |
| `a` | `Ray` | let/var | `new Ray( one3.clone(), new Vector3( 0, 0, 1 ) )` | ✗ |
| `point` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Ray` | let/var | `new Ray( one3.clone(), new Vector3( 0, 0, 1 ) )` | ✗ |
| `a` | `Ray` | let/var | `new Ray( one3.clone(), new Vector3( 0, 0, 1 ) )` | ✗ |
| `a` | `Ray` | let/var | `new Ray( one3.clone(), new Vector3( 0, 0, 1 ) )` | ✗ |
| `ptOnLine` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `ptOnSegment` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `v0` | `Vector3` | let/var | `new Vector3( 3, 5, 50 )` | ✗ |
| `v1` | `Vector3` | let/var | `new Vector3( 50, 50, 50 )` | ✗ |
| `TOL` | `0.0001` | let/var | `0.0001` | ✗ |
| `point` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a0` | `Ray` | let/var | `new Ray( zero3.clone(), new Vector3( 0, 0, - 1 ) )` | ✗ |
| `a1` | `Ray` | let/var | `new Ray( one3.clone(), new Vector3( - 1, 0, 0 ) )` | ✗ |
| `b` | `Sphere` | let/var | `new Sphere( new Vector3( 0, 0, 3 ), 2 )` | ✗ |
| `a` | `Ray` | let/var | `new Ray( one3.clone(), new Vector3( 0, 0, 1 ) )` | ✗ |
| `b` | `Sphere` | let/var | `new Sphere( zero3, 0.5 )` | ✗ |
| `c` | `Sphere` | let/var | `new Sphere( zero3, 1.5 )` | ✗ |
| `d` | `Sphere` | let/var | `new Sphere( one3, 0.1 )` | ✗ |
| `e` | `Sphere` | let/var | `new Sphere( two3, 0.1 )` | ✗ |
| `f` | `Sphere` | let/var | `new Sphere( two3, 1 )` | ✗ |
| `a` | `Ray` | let/var | `new Ray( one3.clone(), new Vector3( 0, 0, 1 ) )` | ✗ |
| `point` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Ray` | let/var | `new Ray( one3.clone(), new Vector3( 0, 0, 1 ) )` | ✗ |
| `TOL` | `0.0001` | let/var | `0.0001` | ✗ |
| `box` | `Box3` | let/var | `new Box3( new Vector3( - 1, - 1, - 1 ), new Vector3( 1, 1, 1 ) )` | ✗ |
| `point` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Ray` | let/var | `new Ray( new Vector3( - 2, 0, 0 ), new Vector3( 1, 0, 0 ) )` | ✗ |
| `b` | `Ray` | let/var | `new Ray( new Vector3( - 2, 0, 0 ), new Vector3( - 1, 0, 0 ) )` | ✗ |
| `c` | `Ray` | let/var | `new Ray( new Vector3( 0, 0, 0 ), new Vector3( 1, 0, 0 ) )` | ✗ |
| `d` | `Ray` | let/var | `new Ray( new Vector3( 0, 2, 1 ), new Vector3( 0, - 1, - 1 ).normalize() )` | ✗ |
| `e` | `Ray` | let/var | `new Ray( new Vector3( 1, - 2, 1 ), new Vector3( 0, 1, 0 ).normalize() )` | ✗ |
| `f` | `Ray` | let/var | `new Ray( new Vector3( 1, - 2, 0 ), new Vector3( 0, - 1, 0 ).normalize() )` | ✗ |
| `ray` | `Ray` | let/var | `new Ray()` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( 1, 1, 0 )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( 0, 1, 1 )` | ✗ |
| `c` | `Vector3` | let/var | `new Vector3( 1, 0, 1 )` | ✗ |
| `point` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Ray` | let/var | `new Ray( one3.clone(), new Vector3( 0, 0, 1 ) )` | ✗ |
| `m` | `Matrix4` | let/var | `new Matrix4()` | ✗ |


---