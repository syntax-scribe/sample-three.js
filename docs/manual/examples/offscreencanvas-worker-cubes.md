[⬅️ Back to Table of Contents](../../index.md)

# 📄 `offscreencanvas-worker-cubes.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/examples/offscreencanvas-worker-cubes.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `init` | `./shared-cubes.js` |
| `state` | `./shared-cubes.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `handlers` | `{ init: (data: any) => void; size: (d...` | let/var | `{ init, size, }` | ✗ |
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


---