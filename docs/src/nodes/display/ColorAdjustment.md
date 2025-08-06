[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ColorAdjustment.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 12 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/nodes/display/ColorAdjustment.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `dot` | `../math/MathNode.js` |
| `max` | `../math/MathNode.js` |
| `mix` | `../math/MathNode.js` |
| `add` | `../math/OperatorNode.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `If` | `../tsl/TSLBase.js` |
| `float` | `../tsl/TSLBase.js` |
| `vec3` | `../tsl/TSLBase.js` |
| `vec4` | `../tsl/TSLBase.js` |
| `ColorManagement` | `../../math/ColorManagement.js` |
| `Vector3` | `../../math/Vector3.js` |
| `LinearSRGBColorSpace` | `../../constants.js` |


---

## Functions

### `luminance(color: any, luminanceCoefficients: any): any`

**Parameters:**

- **`color`** `any`
- **`luminanceCoefficients`** `any`

**Returns:** `any`

**Calls:**

- `dot (from ../math/MathNode.js)`

<details><summary>Code</summary>

```typescript
(
	color,
	luminanceCoefficients = vec3( ColorManagement.getLuminanceCoefficients( new Vector3() ) )
) => dot( color, luminanceCoefficients )
```
</details>


---