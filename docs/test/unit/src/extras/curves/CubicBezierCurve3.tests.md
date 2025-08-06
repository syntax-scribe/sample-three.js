[⬅️ Back to Table of Contents](../../../../../index.md)

# 📄 `CubicBezierCurve3.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 📦 Imports | 3 |
| 📊 Variables & Constants | 18 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)

## 🛠️ File Location:
📂 **`test/unit/src/extras/curves/CubicBezierCurve3.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `CubicBezierCurve3` | `../../../../../src/extras/curves/CubicBezierCurve3.js` |
| `Curve` | `../../../../../src/extras/core/Curve.js` |
| `Vector3` | `../../../../../src/math/Vector3.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `curve` | `any` | let/var | `undefined` | ✗ |
| `object` | `CubicBezierCurve3` | let/var | `new CubicBezierCurve3()` | ✗ |
| `object` | `CubicBezierCurve3` | let/var | `new CubicBezierCurve3()` | ✗ |
| `object` | `CubicBezierCurve3` | let/var | `new CubicBezierCurve3()` | ✗ |
| `object` | `CubicBezierCurve3` | let/var | `new CubicBezierCurve3()` | ✗ |
| `expectedPoints` | `Vector3[]` | let/var | `[ new Vector3( - 10, 0, 2 ), new Vector3( - 3.359375, 8.4375, 1.984375 ), new...` | ✗ |
| `curveRev` | `CubicBezierCurve3` | let/var | `new CubicBezierCurve3( curve.v3, curve.v2, curve.v1, curve.v0 )` | ✗ |
| `expectedLength` | `39.58103024989427` | let/var | `39.58103024989427` | ✗ |
| `expectedLengths` | `number[]` | let/var | `[ 0, 10.73729718231036, 20.19074500737662, 27.154413277853756, 38.45328715011...` | ✗ |
| `expectedPoints` | `Vector3[]` | let/var | `[ new Vector3( - 10, 0, 2 ), new Vector3( - 2.591880240484318, 8.908333501170...` | ✗ |
| `points` | `any[]` | let/var | `[ curve.getPointAt( 0, new Vector3() ), curve.getPointAt( 0.3, new Vector3() ...` | ✗ |
| `expectedTangents` | `Vector3[]` | let/var | `[ new Vector3( 0.3138715439944244, 0.9411440474105875, 0.12542940601858074 ),...` | ✗ |
| `tangents` | `any[]` | let/var | `[ curve.getTangent( 0, new Vector3() ), curve.getTangent( 0.25, new Vector3()...` | ✗ |
| `tangent` | `any` | let/var | `tangents[ i ]` | ✗ |
| `tangent` | `any` | let/var | `tangents[ i ]` | ✗ |
| `expectedSomewhere` | `0.021163245321323316` | let/var | `0.021163245321323316` | ✗ |
| `expectedPoints` | `Vector3[]` | let/var | `[ new Vector3( - 10, 0, 2 ), new Vector3( - 5.756524515061918, 6.568020242700...` | ✗ |
| `expected` | `{ binormals: Vector3[]; normals: Vect...` | let/var | `{ binormals: [ new Vector3( - 0.9486358543207215, 0.316370061632252, - 6.9388...` | ✗ |


---