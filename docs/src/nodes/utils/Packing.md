[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Packing.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/nodes/utils/Packing.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `nodeObject` | `../tsl/TSLBase.js` |


---

## Functions

### `directionToColor(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `nodeObject( node ).mul( 0.5 ).add`

<details><summary>Code</summary>

```typescript
( node ) => nodeObject( node ).mul( 0.5 ).add( 0.5 )
```
</details>

### `colorToDirection(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `nodeObject( node ).mul( 2.0 ).sub`

<details><summary>Code</summary>

```typescript
( node ) => nodeObject( node ).mul( 2.0 ).sub( 1 )
```
</details>


---