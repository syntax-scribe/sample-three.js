[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `signal.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/libs/ternjs/signal.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `handlers` | `any` | let/var | `this._handlers \|\| (this._handlers = Object.create(null))` | ✗ |
| `arr` | `any` | let/var | `this._handlers && this._handlers[type]` | ✗ |
| `arr` | `any` | let/var | `this._handlers && this._handlers[type]` | ✗ |


---

## Functions

### `on(type: any, f: any): void`

**Parameters:**

- **`type`** `any`
- **`f`** `any`

**Returns:** `void`

**Calls:**

- `Object.create`
- `(handlers[type] || (handlers[type] = [])).push`

<details><summary>Code</summary>

```typescript
function on(type, f) {
    var handlers = this._handlers || (this._handlers = Object.create(null));
    (handlers[type] || (handlers[type] = [])).push(f);
  }
```
</details>

### `off(type: any, f: any): void`

**Parameters:**

- **`type`** `any`
- **`f`** `any`

**Returns:** `void`

**Calls:**

- `arr.splice`

<details><summary>Code</summary>

```typescript
function off(type, f) {
    var arr = this._handlers && this._handlers[type];
    if (arr) for (var i = 0; i < arr.length; ++i)
      if (arr[i] == f) { arr.splice(i, 1); break; }
  }
```
</details>

### `signal(type: any, a1: any, a2: any, a3: any, a4: any): void`

**Parameters:**

- **`type`** `any`
- **`a1`** `any`
- **`a2`** `any`
- **`a3`** `any`
- **`a4`** `any`

**Returns:** `void`

**Calls:**

- `arr[i].call`

<details><summary>Code</summary>

```typescript
function signal(type, a1, a2, a3, a4) {
    var arr = this._handlers && this._handlers[type];
    if (arr) for (var i = 0; i < arr.length; ++i) arr[i].call(this, a1, a2, a3, a4);
  }
```
</details>


---