[⬅️ Back to Table of Contents](../../index.md)

# 📄 `StringEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/StringEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `createElementFromJSON` | `../NodeEditorUtils.js` |


---

## Functions

### `StringEditor.getURL(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getURL() {

		return this.stringNode.value;

	}
```
</details>


---

## Classes

### `StringEditor`

<details><summary>Class Code</summary>

```ts
export class StringEditor extends BaseNodeEditor {

	constructor() {

		const { element, inputNode } = createElementFromJSON( {
			inputType: 'string',
			inputConnection: false
		} );

		super( 'String', inputNode, 350 );

		element.addEventListener( 'changeInput', () => this.invalidate() );

		this.add( element );

	}

	get stringNode() {

		return this.value;

	}

	getURL() {

		return this.stringNode.value;

	}

}
```
</details>

#### Methods

##### `getURL(): any`

<details><summary>Code</summary>

```ts
getURL() {

		return this.stringNode.value;

	}
```
</details>


---