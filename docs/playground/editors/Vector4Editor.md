[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Vector4Editor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/Vector4Editor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `createElementFromJSON` | `../NodeEditorUtils.js` |


---

## Classes

### `Vector4Editor`

<details><summary>Class Code</summary>

```ts
export class Vector4Editor extends BaseNodeEditor {

	constructor() {

		const { element, inputNode } = createElementFromJSON( {
			inputType: 'vec4',
			inputConnection: false
		} );

		super( 'Vector 4', inputNode, 350 );

		element.addEventListener( 'changeInput', () => this.invalidate() );

		this.add( element );

	}

}
```
</details>


---