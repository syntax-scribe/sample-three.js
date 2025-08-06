[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `comment.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/ternjs/comment.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `found` | `any` | let/var | `null` | ✗ |
| `emptyLines` | `number` | let/var | `0` | ✗ |
| `topIsLineComment` | `any` | let/var | `*not shown*` | ✗ |
| `end` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `isSpace(ch: any): boolean`

**Parameters:**

- **`ch`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isSpace(ch) {
    return (ch < 14 && ch > 8) || ch === 32 || ch === 160;
  }
```
</details>

### `onOwnLine(text: any, pos: any): boolean`

**Parameters:**

- **`text`** `any`
- **`pos`** `any`

**Returns:** `boolean`

**Calls:**

- `text.charCodeAt`
- `isSpace`

<details><summary>Code</summary>

```typescript
function onOwnLine(text, pos) {
    for (; pos > 0; --pos) {
      var ch = text.charCodeAt(pos - 1);
      if (ch == 10) break;
      if (!isSpace(ch)) return false;
    }
    return true;
  }
```
</details>


---