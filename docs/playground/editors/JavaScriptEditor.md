[⬅️ Back to Table of Contents](../../index.md)

# 📄 `JavaScriptEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/JavaScriptEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `CodeEditorElement` | `../elements/CodeEditorElement.js` |
| `js` | `three/tsl` |


---

## Classes

### `JavaScriptEditor`

<details><summary>Class Code</summary>

```ts
export class JavaScriptEditor extends BaseNodeEditor {

	constructor( source = '' ) {

		const codeNode = js( source );

		super( 'JavaScript', codeNode, 500 );

		this.setResizable( true );

		//

		this.editorElement = new CodeEditorElement( source );
		this.editorElement.addEventListener( 'change', () => {

			codeNode.code = this.editorElement.source;

			this.invalidate();

			this.editorElement.focus();

		} );

		this.add( this.editorElement );

	}

	set source( value ) {

		this.codeNode.code = value;

	}

	get source() {

		return this.codeNode.code;

	}

	get codeNode() {

		return this.value;

	}

}
```
</details>


---