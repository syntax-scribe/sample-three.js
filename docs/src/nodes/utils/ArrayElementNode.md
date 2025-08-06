[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ArrayElementNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/utils/ArrayElementNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |


---

## Functions

### `ArrayElementNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node type is inferred from the array-like node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.node.getElementType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return this.node.getElementType( builder );

	}
```
</details>

### `ArrayElementNode.generate(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `this.indexNode.getNodeType`
- `this.node.build`
- `this.indexNode.build`
- `builder.isVector`
- `builder.isInteger`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const indexType = this.indexNode.getNodeType( builder );

		const nodeSnippet = this.node.build( builder );
		const indexSnippet = this.indexNode.build( builder, ! builder.isVector( indexType ) && builder.isInteger( indexType ) ? indexType : 'uint' );

		return `${ nodeSnippet }[ ${ indexSnippet } ]`;

	}
```
</details>


---

## Classes

### `ArrayElementNode`

<details><summary>Class Code</summary>

```ts
class ArrayElementNode extends Node { // @TODO: If extending from TempNode it breaks webgpu_compute

	static get type() {

		return 'ArrayElementNode';

	}

	/**
	 * Constructs an array element node.
	 *
	 * @param {Node} node - The array-like node.
	 * @param {Node} indexNode - The index node that defines the element access.
	 */
	constructor( node, indexNode ) {

		super();

		/**
		 * The array-like node.
		 *
		 * @type {Node}
		 */
		this.node = node;

		/**
		 * The index node that defines the element access.
		 *
		 * @type {Node}
		 */
		this.indexNode = indexNode;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isArrayElementNode = true;

	}

	/**
	 * This method is overwritten since the node type is inferred from the array-like node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( builder ) {

		return this.node.getElementType( builder );

	}

	generate( builder ) {

		const indexType = this.indexNode.getNodeType( builder );

		const nodeSnippet = this.node.build( builder );
		const indexSnippet = this.indexNode.build( builder, ! builder.isVector( indexType ) && builder.isInteger( indexType ) ? indexType : 'uint' );

		return `${ nodeSnippet }[ ${ indexSnippet } ]`;

	}

}
```
</details>

#### Methods

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return this.node.getElementType( builder );

	}
```
</details>

##### `generate(builder: any): string`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const indexType = this.indexNode.getNodeType( builder );

		const nodeSnippet = this.node.build( builder );
		const indexSnippet = this.indexNode.build( builder, ! builder.isVector( indexType ) && builder.isInteger( indexType ) ? indexType : 'uint' );

		return `${ nodeSnippet }[ ${ indexSnippet } ]`;

	}
```
</details>


---