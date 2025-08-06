[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `AccessorsUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 10 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/nodes/accessors/AccessorsUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `normalView` | `./Normal.js` |
| `tangentView` | `./Tangent.js` |
| `bitangentView` | `./Bitangent.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `mat3` | `../tsl/TSLBase.js` |
| `mix` | `../math/MathNode.js` |
| `anisotropy` | `../core/PropertyNode.js` |
| `anisotropyB` | `../core/PropertyNode.js` |
| `roughness` | `../core/PropertyNode.js` |
| `positionViewDirection` | `./Position.js` |


---

## Functions

### `parallaxUV(uv: any, scale: any): any`

**Parameters:**

- **`uv`** `any`
- **`scale`** `any`

**Returns:** `any`

**Calls:**

- `uv.sub`

<details><summary>Code</summary>

```typescript
( uv, scale ) => uv.sub( parallaxDirection.mul( scale ) )
```
</details>


---