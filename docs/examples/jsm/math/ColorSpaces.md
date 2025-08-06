[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ColorSpaces.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 📦 Imports | 3 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)

## 🛠️ File Location:
📂 **`examples/jsm/math/ColorSpaces.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LinearTransfer` | `three` |
| `Matrix3` | `three` |
| `SRGBTransfer` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `P3_PRIMARIES` | `number[]` | let/var | `[ 0.680, 0.320, 0.265, 0.690, 0.150, 0.060 ]` | ✗ |
| `P3_LUMINANCE_COEFFICIENTS` | `number[]` | let/var | `[ 0.2289, 0.6917, 0.0793 ]` | ✗ |
| `REC2020_PRIMARIES` | `number[]` | let/var | `[ 0.708, 0.292, 0.170, 0.797, 0.131, 0.046 ]` | ✗ |
| `REC2020_LUMINANCE_COEFFICIENTS` | `number[]` | let/var | `[ 0.2627, 0.6780, 0.0593 ]` | ✗ |
| `D65` | `number[]` | let/var | `[ 0.3127, 0.3290 ]` | ✗ |
| `DisplayP3ColorSpace` | `string` | let/var | `'display-p3'` | ✓ |
| `LinearDisplayP3ColorSpace` | `string` | let/var | `'display-p3-linear'` | ✓ |
| `DisplayP3ColorSpaceImpl` | `any` | let/var | `{ primaries: P3_PRIMARIES, whitePoint: D65, transfer: SRGBTransfer, toXYZ: LI...` | ✓ |
| `LinearDisplayP3ColorSpaceImpl` | `any` | let/var | `{ primaries: P3_PRIMARIES, whitePoint: D65, transfer: LinearTransfer, toXYZ: ...` | ✓ |
| `LinearRec2020ColorSpace` | `string` | let/var | `'rec2020-linear'` | ✓ |
| `LinearRec2020ColorSpaceImpl` | `any` | let/var | `{ primaries: REC2020_PRIMARIES, whitePoint: D65, transfer: LinearTransfer, to...` | ✓ |


---