[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Discard.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📦 Imports | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/nodes/utils/Discard.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `select` | `../math/ConditionalNode.js` |
| `expression` | `../code/ExpressionNode.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |


---

## Functions

### `Discard(conditional: ConditionalNode): Node`

**Parameters:**

- **`conditional`** `ConditionalNode`

**Returns:** `Node`

**Calls:**

- `( conditional ? select( conditional, expression( 'discard' ) ) : expression( 'discard' ) ).toStack`

<details><summary>Code</summary>

```typescript
( conditional ) => ( conditional ? select( conditional, expression( 'discard' ) ) : expression( 'discard' ) ).toStack()
```
</details>

### `Return(): ExpressionNode`

**Returns:** `ExpressionNode`

**Calls:**

- `expression( 'return' ).toStack`

<details><summary>Code</summary>

```typescript
() => expression( 'return' ).toStack()
```
</details>


---