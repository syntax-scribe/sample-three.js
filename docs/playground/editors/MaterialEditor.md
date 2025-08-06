[⬅️ Back to Table of Contents](../../index.md)

# 📄 `MaterialEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/MaterialEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BaseNodeEditor` | `../BaseNodeEditor.js` |


---

## Classes

### `MaterialEditor`

<details><summary>Class Code</summary>

```ts
export class MaterialEditor extends BaseNodeEditor {

	constructor( name, material, width = 300 ) {

		super( name, material, width );

	}

	get material() {

		return this.value;

	}

}
```
</details>


---