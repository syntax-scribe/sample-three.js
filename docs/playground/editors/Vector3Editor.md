[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Vector3Editor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/Vector3Editor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `createElementFromJSON` | `../NodeEditorUtils.js` |


---

## Classes

### `Vector3Editor`

<details><summary>Class Code</summary>

```ts
export class Vector3Editor extends BaseNodeEditor {

	constructor() {

		const { element, inputNode } = createElementFromJSON( {
			inputType: 'vec3',
			inputConnection: false
		} );

		super( 'Vector 3', inputNode, 325 );

		element.addEventListener( 'changeInput', () => this.invalidate() );

		this.add( element );

	}

}
```
</details>


---