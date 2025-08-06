[⬅️ Back to Table of Contents](../../index.md)

# 📄 `UVEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/UVEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `SelectInput` | `flow` |
| `LabelElement` | `flow` |
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `uv` | `three/tsl` |


---

## Classes

### `UVEditor`

<details><summary>Class Code</summary>

```ts
export class UVEditor extends BaseNodeEditor {

	constructor() {

		const node = uv();

		super( 'UV', node, 200 );

		const optionsField = new SelectInput( [ '0', '1', '2', '3' ], 0 ).onChange( () => {

			node.index = Number( optionsField.getValue() );

			this.invalidate();

		} );

		this.add( new LabelElement( 'Channel' ).add( optionsField ) );

	}

}
```
</details>


---