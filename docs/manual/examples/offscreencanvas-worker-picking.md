[⬅️ Back to Table of Contents](../../index.md)

# 📄 `offscreencanvas-worker-picking.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/examples/offscreencanvas-worker-picking.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `state` | `./shared-picking.js` |
| `init` | `./shared-picking.js` |
| `pickPosition` | `./shared-picking.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `handlers` | `{ init: (data: any) => void; mouse: (...` | let/var | `{ init, mouse, size, }` | ✗ |
| `fn` | `any` | let/var | `handlers[ e.data.type ]` | ✗ |


---

## Functions

### `size(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function size( data ) {

	state.width = data.width;
	state.height = data.height;

}
```
</details>

### `mouse(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function mouse( data ) {

	pickPosition.x = data.x;
	pickPosition.y = data.y;

}
```
</details>


---