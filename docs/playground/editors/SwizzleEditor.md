[⬅️ Back to Table of Contents](../../index.md)

# 📄 `SwizzleEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/SwizzleEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LabelElement` | `flow` |
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `createElementFromJSON` | `../NodeEditorUtils.js` |
| `split` | `three/tsl` |
| `float` | `three/tsl` |
| `setInputAestheticsFromType` | `../DataTypeLib.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `string` | `any` | let/var | `componentsElement.value.value` | ✗ |


---

## Classes

### `SwizzleEditor`

<details><summary>Class Code</summary>

```ts
export class SwizzleEditor extends BaseNodeEditor {

	constructor() {

		const node = split( float(), 'x' );

		super( 'Swizzle', node, 175 );

		const inputElement = setInputAestheticsFromType( new LabelElement( 'Input' ), 'node' ).onConnect( () => {

			node.node = inputElement.getLinkedObject() || float();

		} );

		this.add( inputElement );

		//

		const { element: componentsElement } = createElementFromJSON( {
			inputType: 'String',
			allows: 'xyzwrgba',
			transform: 'lowercase',
			options: [ 'x', 'y', 'z', 'w', 'r', 'g', 'b', 'a' ],
			maxLength: 4
		} );

		componentsElement.addEventListener( 'changeInput', () => {

			const string = componentsElement.value.value;

			node.components = string || 'x';

			this.invalidate();

		} );

		this.add( componentsElement );

	}

}
```
</details>


---