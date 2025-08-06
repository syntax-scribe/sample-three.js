[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TriplanarTextures.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/nodes/utils/TriplanarTextures.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `add` | `../math/OperatorNode.js` |
| `normalLocal` | `../accessors/Normal.js` |
| `positionLocal` | `../accessors/Position.js` |
| `texture` | `../accessors/TextureNode.js` |
| `float` | `../tsl/TSLBase.js` |
| `vec3` | `../tsl/TSLBase.js` |
| `Fn` | `../tsl/TSLBase.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `textureX` | `any` | let/var | `textureXNode.value` | ✗ |
| `textureY` | `any` | let/var | `textureYNode !== null ? textureYNode.value : textureX` | ✗ |
| `textureZ` | `any` | let/var | `textureZNode !== null ? textureZNode.value : textureX` | ✗ |


---

## Functions

### `triplanarTexture(params: any[]): any`

**Parameters:**

- **`params`** `any[]`

**Returns:** `any`

**Calls:**

- `triplanarTextures`

<details><summary>Code</summary>

```typescript
( ...params ) => triplanarTextures( ...params )
```
</details>


---