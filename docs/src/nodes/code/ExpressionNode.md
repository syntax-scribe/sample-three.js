[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ExpressionNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/code/ExpressionNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `nodeProxy` | `../tsl/TSLCore.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `snippet` | `string` | let/var | `this.snippet` | ✗ |


---

## Functions

### `ExpressionNode.generate(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `this.getNodeType`
- `builder.addLineFlowCode`
- `builder.format`

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		const type = this.getNodeType( builder );
		const snippet = this.snippet;

		if ( type === 'void' ) {

			builder.addLineFlowCode( snippet, this );

		} else {

			return builder.format( snippet, type, output );

		}

	}
```
</details>


---

## Classes

### `ExpressionNode`

<details><summary>Class Code</summary>

```ts
class ExpressionNode extends Node {

	static get type() {

		return 'ExpressionNode';

	}

	/**
	 * Constructs a new expression node.
	 *
	 * @param {string} [snippet=''] - The native code snippet.
	 * @param {string} [nodeType='void'] - The node type.
	 */
	constructor( snippet = '', nodeType = 'void' ) {

		super( nodeType );

		/**
		 * The native code snippet.
		 *
		 * @type {string}
		 * @default ''
		 */
		this.snippet = snippet;

	}

	generate( builder, output ) {

		const type = this.getNodeType( builder );
		const snippet = this.snippet;

		if ( type === 'void' ) {

			builder.addLineFlowCode( snippet, this );

		} else {

			return builder.format( snippet, type, output );

		}

	}

}
```
</details>

#### Methods

##### `generate(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		const type = this.getNodeType( builder );
		const snippet = this.snippet;

		if ( type === 'void' ) {

			builder.addLineFlowCode( snippet, this );

		} else {

			return builder.format( snippet, type, output );

		}

	}
```
</details>


---