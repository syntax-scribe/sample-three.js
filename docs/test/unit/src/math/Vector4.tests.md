[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Vector4.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 📦 Imports | 8 |
| 📊 Variables & Constants | 64 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)

## 🛠️ File Location:
📂 **`test/unit/src/math/Vector4.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector4` | `../../../../src/math/Vector4.js` |
| `Matrix4` | `../../../../src/math/Matrix4.js` |
| `BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `x` | `../../utils/math-constants.js` |
| `y` | `../../utils/math-constants.js` |
| `z` | `../../utils/math-constants.js` |
| `w` | `../../utils/math-constants.js` |
| `eps` | `../../utils/math-constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `a` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `object` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( x, y, z, w )` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( x, y, z, w )` | ✗ |
| `b` | `Vector4` | let/var | `new Vector4( - x, - y, - z, - w )` | ✗ |
| `b` | `Vector4` | let/var | `new Vector4( - x, - y, - z, - w )` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( x, y, z, w )` | ✗ |
| `b` | `Vector4` | let/var | `new Vector4( 6, 7, 8, 9 )` | ✗ |
| `s` | `3` | let/var | `3` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( x, y, z, w )` | ✗ |
| `b` | `Vector4` | let/var | `new Vector4( - x, - y, - z, - w )` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( x, y, z, w )` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( x, y, z, w )` | ✗ |
| `expected` | `Vector4` | let/var | `new Vector4( 2, - 3, - 4, 5 )` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( 7, 8, 9, 0 )` | ✗ |
| `b` | `Vector4` | let/var | `new Vector4( 2, 2, 3, 4 )` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( - 0.1, 0.01, 0.5, 1.5 )` | ✗ |
| `clamped` | `Vector4` | let/var | `new Vector4( 0.1, 0.1, 0.5, 1.0 )` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( x, y, z, w )` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( x, y, z, w )` | ✗ |
| `b` | `Vector4` | let/var | `new Vector4( - x, - y, - z, - w )` | ✗ |
| `c` | `Vector4` | let/var | `new Vector4( 0, 0, 0, 0 )` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( x, 0, 0, 0 )` | ✗ |
| `b` | `Vector4` | let/var | `new Vector4( 0, - y, 0, 0 )` | ✗ |
| `c` | `Vector4` | let/var | `new Vector4( 0, 0, z, 0 )` | ✗ |
| `d` | `Vector4` | let/var | `new Vector4( 0, 0, 0, w )` | ✗ |
| `e` | `Vector4` | let/var | `new Vector4( 0, 0, 0, 0 )` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( x, 0, 0, 0 )` | ✗ |
| `b` | `Vector4` | let/var | `new Vector4( 0, - y, 0, 0 )` | ✗ |
| `c` | `Vector4` | let/var | `new Vector4( 0, 0, z, 0 )` | ✗ |
| `d` | `Vector4` | let/var | `new Vector4( 0, 0, 0, - w )` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( x, 0, 0, 0 )` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( x, 0, z, 0 )` | ✗ |
| `b` | `Vector4` | let/var | `new Vector4( 0, - y, 0, - w )` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `array` | `number[]` | let/var | `[ 1, 2, 3, 4, 5, 6, 7, 8 ]` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( x, y, z, w )` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `attr` | `BufferAttribute` | let/var | `new BufferAttribute( new Float32Array( [ 1, 2, 3, 4, 5, 6, 7, 8 ] ), 4 )` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `s` | `3` | let/var | `3` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( x, y, z, w )` | ✗ |
| `b` | `Vector4` | let/var | `new Vector4( - x, - y, - z, - w )` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( x, y, z, w )` | ✗ |
| `b` | `Vector4` | let/var | `new Vector4( - x, - y, - z, - w )` | ✗ |
| `c` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( x, 0, 0, 0 )` | ✗ |
| `b` | `Vector4` | let/var | `new Vector4( 0, - y, 0, 0 )` | ✗ |
| `c` | `Vector4` | let/var | `new Vector4( 0, 0, z, 0 )` | ✗ |
| `d` | `Vector4` | let/var | `new Vector4( 0, 0, 0, w )` | ✗ |
| `e` | `Vector4` | let/var | `new Vector4( 0, 0, 0, 0 )` | ✗ |
| `a` | `Vector4` | let/var | `new Vector4( x, 0, z, 0 )` | ✗ |
| `b` | `Vector4` | let/var | `new Vector4( 0, - y, 0, - w )` | ✗ |
| `v` | `Vector4` | let/var | `new Vector4( 0, 0.3, 0.7, 1 )` | ✗ |
| `array` | `number[]` | let/var | `[ ...v ]` | ✗ |


---