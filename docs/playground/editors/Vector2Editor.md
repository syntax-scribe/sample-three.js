[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Vector2Editor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/Vector2Editor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `createElementFromJSON` | `../NodeEditorUtils.js` |


---

## Classes

### `Vector2Editor`

<details><summary>Class Code</summary>

```ts
export class Vector2Editor extends BaseNodeEditor {

	constructor() {

		const { element, inputNode } = createElementFromJSON( {
			inputType: 'vec2',
			inputConnection: false
		} );

		super( 'Vector 2', inputNode );

		element.addEventListener( 'changeInput', () => this.invalidate() );

		this.add( element );


	}

}
```
</details>


---