[⬅️ Back to Table of Contents](../../index.md)

# 📄 `FloatEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/FloatEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `createElementFromJSON` | `../NodeEditorUtils.js` |


---

## Classes

### `FloatEditor`

<details><summary>Class Code</summary>

```ts
export class FloatEditor extends BaseNodeEditor {

	constructor() {

		const { element, inputNode } = createElementFromJSON( {
			inputType: 'float',
			inputConnection: false
		} );

		super( 'Float', inputNode, 150 );

		element.addEventListener( 'changeInput', () => this.invalidate() );

		this.add( element );

	}

}
```
</details>


---