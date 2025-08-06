[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `UV.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/nodes/accessors/UV.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `attribute` | `../core/AttributeNode.js` |


---

## Functions

### `uv(index: number): AttributeNode<vec2>`

**Parameters:**

- **`index`** `number`

**Returns:** `AttributeNode<vec2>`

**Calls:**

- `attribute (from ../core/AttributeNode.js)`

<details><summary>Code</summary>

```typescript
( index = 0 ) => attribute( 'uv' + ( index > 0 ? index : '' ), 'vec2' )
```
</details>


---