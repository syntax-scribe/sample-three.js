[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Vector3.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 📦 Imports | 14 |
| 📊 Variables & Constants | 110 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)

## 🛠️ File Location:
📂 **`test/unit/src/math/Vector3.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `../../../../src/math/Vector3.js` |
| `Vector4` | `../../../../src/math/Vector4.js` |
| `Matrix3` | `../../../../src/math/Matrix3.js` |
| `Matrix4` | `../../../../src/math/Matrix4.js` |
| `Spherical` | `../../../../src/math/Spherical.js` |
| `Quaternion` | `../../../../src/math/Quaternion.js` |
| `Euler` | `../../../../src/math/Euler.js` |
| `Cylindrical` | `../../../../src/math/Cylindrical.js` |
| `BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `PerspectiveCamera` | `../../../../src/cameras/PerspectiveCamera.js` |
| `x` | `../../utils/math-constants.js` |
| `y` | `../../utils/math-constants.js` |
| `z` | `../../utils/math-constants.js` |
| `eps` | `../../utils/math-constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `a` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `object` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( - x, - y, - z )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( 2, 3, 4 )` | ✗ |
| `s` | `3` | let/var | `3` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( - x, - y, - z )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( 2, 3, - 5 )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `euler` | `Euler` | let/var | `new Euler( 90, - 45, 0 )` | ✗ |
| `expected` | `Vector3` | let/var | `new Vector3( - 2.352970120501014, - 4.7441750936226645, 0.9779234597246458 )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `axis` | `Vector3` | let/var | `new Vector3( 0, 1, 0 )` | ✗ |
| `angle` | `number` | let/var | `Math.PI / 4.0` | ✗ |
| `expected` | `Vector3` | let/var | `new Vector3( 3 * Math.sqrt( 2 ), 3, Math.sqrt( 2 ) )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `b` | `Vector4` | let/var | `new Vector4( x, y, z, 1 )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `m` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `transformed` | `Vector3` | let/var | `new Vector3( 0.3713906763541037, 0.5570860145311556, 0.7427813527082074 )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( - 0.01, 0.5, 1.5 )` | ✗ |
| `clamped` | `Vector3` | let/var | `new Vector3( 0.1, 0.5, 1.0 )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( - x, - y, - z )` | ✗ |
| `c` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, 0, 0 )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( 0, - y, 0 )` | ✗ |
| `c` | `Vector3` | let/var | `new Vector3( 0, 0, z )` | ✗ |
| `d` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, 0, 0 )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( 0, - y, 0 )` | ✗ |
| `c` | `Vector3` | let/var | `new Vector3( 0, 0, z )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, 0, 0 )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( 2 * x, - y, 0.5 * z )` | ✗ |
| `crossed` | `Vector3` | let/var | `new Vector3( 18, 12, - 18 )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( x, - y, z )` | ✗ |
| `c` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `crossed` | `Vector3` | let/var | `new Vector3( 24, 0, - 12 )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( 1, 0, 0 )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `normal` | `Vector3` | let/var | `new Vector3( 10, 0, 0 )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( 1, 0, 0 )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `normal` | `Vector3` | let/var | `new Vector3( 1, 0, 0 )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `normal` | `Vector3` | let/var | `new Vector3( 0, 1, 0 )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( 0, - 0.18851655680720186, 0.9820700116639124 )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( 0, 0.18851655680720186, - 0.9820700116639124 )` | ✗ |
| `x` | `Vector3` | let/var | `new Vector3( 1, 0, 0 )` | ✗ |
| `y` | `Vector3` | let/var | `new Vector3( 0, 1, 0 )` | ✗ |
| `z` | `Vector3` | let/var | `new Vector3( 0, 0, 1 )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `theta` | `number` | let/var | `Math.sqrt( Math.PI ) * phi` | ✗ |
| `sph` | `Spherical` | let/var | `new Spherical( 10, phi, theta )` | ✗ |
| `expected` | `Vector3` | let/var | `new Vector3( - 4.677914006701843, - 5, - 7.288149322420796 )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `cyl` | `Cylindrical` | let/var | `new Cylindrical( 10, Math.PI * 0.125, 20 )` | ✗ |
| `expected` | `Vector3` | let/var | `new Vector3( 3.826834323650898, 20, 9.238795325112868 )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `expected` | `Vector3` | let/var | `new Vector3( 25.573423705088842, 31.921779399024736, 35.70714214271425 )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, 0, z )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( 0, - y, 0 )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `array` | `number[]` | let/var | `[ 1, 2, 3, 4, 5, 6 ]` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `attr` | `BufferAttribute` | let/var | `new BufferAttribute( new Float32Array( [ 1, 2, 3, 4, 5, 6 ] ), 3 )` | ✗ |
| `vec` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `zero` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( - x, - y, - z )` | ✗ |
| `c` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, 0, 0 )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( 0, - y, 0 )` | ✗ |
| `c` | `Vector3` | let/var | `new Vector3( 0, 0, z )` | ✗ |
| `d` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `s` | `3` | let/var | `3` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( 2 * x, 2 * y, 2 * z )` | ✗ |
| `c` | `Vector3` | let/var | `new Vector3( 4 * x, 4 * y, 4 * z )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( - x, - y, - z )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `camera` | `PerspectiveCamera` | let/var | `new PerspectiveCamera( 75, 16 / 9, 0.1, 300.0 )` | ✗ |
| `projected` | `Vector3` | let/var | `new Vector3( - 0.36653213611158914, - 0.9774190296309043, 1.0506835611870624 )` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, 0, 0 )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( 0, - y, 0 )` | ✗ |
| `c` | `Vector3` | let/var | `new Vector3( 0, 0, z )` | ✗ |
| `d` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Vector3` | let/var | `new Vector3( x, 0, z )` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( 0, - y, 0 )` | ✗ |
| `v` | `Vector3` | let/var | `new Vector3( 0, 0.5, 1 )` | ✗ |
| `array` | `number[]` | let/var | `[ ...v ]` | ✗ |


---