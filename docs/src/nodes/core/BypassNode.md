[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BypassNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/BypassNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `./Node.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `nodeProxy` | `../tsl/TSLCore.js` |


---

## Functions

### `BypassNode.getNodeType(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `this.outputNode.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return this.outputNode.getNodeType( builder );

	}
```
</details>

### `BypassNode.generate(builder: any): string | Node`

**Parameters:**

- **`builder`** `any`

**Returns:** `string | Node`

**Calls:**

- `this.callNode.build`
- `builder.addLineFlowCode`
- `this.outputNode.build`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const snippet = this.callNode.build( builder, 'void' );

		if ( snippet !== '' ) {

			builder.addLineFlowCode( snippet, this );

		}

		return this.outputNode.build( builder );

	}
```
</details>


---

## Classes

### `BypassNode`

<details><summary>Class Code</summary>

```ts
class BypassNode extends Node {

	static get type() {

		return 'BypassNode';

	}

	/**
	 * Constructs a new bypass node.
	 *
	 * @param {Node} outputNode - The output node.
	 * @param {Node} callNode - The call node.
	 */
	constructor( outputNode, callNode ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isBypassNode = true;

		/**
		 * The output node.
		 *
		 * @type {Node}
		 */
		this.outputNode = outputNode;

		/**
		 * The call node.
		 *
		 * @type {Node}
		 */
		this.callNode = callNode;

	}

	getNodeType( builder ) {

		return this.outputNode.getNodeType( builder );

	}

	generate( builder ) {

		const snippet = this.callNode.build( builder, 'void' );

		if ( snippet !== '' ) {

			builder.addLineFlowCode( snippet, this );

		}

		return this.outputNode.build( builder );

	}

}
```
</details>

#### Methods

##### `getNodeType(builder: any): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return this.outputNode.getNodeType( builder );

	}
```
</details>

##### `generate(builder: any): string | Node`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const snippet = this.callNode.build( builder, 'void' );

		if ( snippet !== '' ) {

			builder.addLineFlowCode( snippet, this );

		}

		return this.outputNode.build( builder );

	}
```
</details>


---