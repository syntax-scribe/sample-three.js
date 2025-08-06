[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ContextNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/ContextNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `./Node.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `nodeProxy` | `../tsl/TSLCore.js` |


---

## Functions

### `ContextNode.getScope(): Node`

**JSDoc:**
```typescript
/**
	 * This method is overwritten to ensure it returns the reference to {@link ContextNode#node}.
	 *
	 * @return {Node} A reference to {@link ContextNode#node}.
	 */
```

**Returns:** `Node`

**Calls:**

- `this.node.getScope`

<details><summary>Code</summary>

```typescript
getScope() {

		return this.node.getScope();

	}
```
</details>

### `ContextNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten to ensure it returns the type of {@link ContextNode#node}.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.node.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return this.node.getNodeType( builder );

	}
```
</details>

### `ContextNode.analyze(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `builder.getContext`
- `builder.setContext`
- `this.node.build`

<details><summary>Code</summary>

```typescript
analyze( builder ) {

		const previousContext = builder.getContext();

		builder.setContext( { ...builder.context, ...this.value } );

		this.node.build( builder );

		builder.setContext( previousContext );

	}
```
</details>

### `ContextNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `builder.getContext`
- `builder.setContext`
- `this.node.build`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const previousContext = builder.getContext();

		builder.setContext( { ...builder.context, ...this.value } );

		this.node.build( builder );

		builder.setContext( previousContext );

	}
```
</details>

### `ContextNode.generate(builder: any, output: any): string | Node`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `string | Node`

**Calls:**

- `builder.getContext`
- `builder.setContext`
- `this.node.build`

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		const previousContext = builder.getContext();

		builder.setContext( { ...builder.context, ...this.value } );

		const snippet = this.node.build( builder, output );

		builder.setContext( previousContext );

		return snippet;

	}
```
</details>

### `uniformFlow(node: Node): ContextNode`

**Parameters:**

- **`node`** `Node`

**Returns:** `ContextNode`

**Calls:**

- `context`

<details><summary>Code</summary>

```typescript
( node ) => context( node, { uniformFlow: true } )
```
</details>

### `setName(node: Node, name: string): ContextNode`

**Parameters:**

- **`node`** `Node`
- **`name`** `string`

**Returns:** `ContextNode`

**Calls:**

- `context`

<details><summary>Code</summary>

```typescript
( node, name ) => context( node, { nodeName: name } )
```
</details>

### `label(node: Node, name: string): ContextNode`

**JSDoc:**
```typescript
/**
 * TSL function for defining a label context value for a given node.
 *
 * @tsl
 * @function
 * @deprecated
 * @param {Node} node - The node whose context should be modified.
 * @param {string} name - The name/label to set.
 * @returns {ContextNode}
 */
```

**Parameters:**

- **`node`** `Node`
- **`name`** `string`

**Returns:** `ContextNode`

**Calls:**

- `console.warn`
- `setName`

<details><summary>Code</summary>

```typescript
export function label( node, name ) {

	console.warn( 'THREE.TSL: "label()" has been deprecated. Use "setName()" instead.' ); // @deprecated r179

	return setName( node, name );

}
```
</details>


---

## Classes

### `ContextNode`

<details><summary>Class Code</summary>

```ts
class ContextNode extends Node {

	static get type() {

		return 'ContextNode';

	}

	/**
	 * Constructs a new context node.
	 *
	 * @param {Node} node - The node whose context should be modified.
	 * @param {Object} [value={}] - The modified context data.
	 */
	constructor( node, value = {} ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isContextNode = true;

		/**
		 * The node whose context should be modified.
		 *
		 * @type {Node}
		 */
		this.node = node;

		/**
		 * The modified context data.
		 *
		 * @type {Object}
		 * @default {}
		 */
		this.value = value;

	}

	/**
	 * This method is overwritten to ensure it returns the reference to {@link ContextNode#node}.
	 *
	 * @return {Node} A reference to {@link ContextNode#node}.
	 */
	getScope() {

		return this.node.getScope();

	}

	/**
	 * This method is overwritten to ensure it returns the type of {@link ContextNode#node}.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( builder ) {

		return this.node.getNodeType( builder );

	}

	analyze( builder ) {

		const previousContext = builder.getContext();

		builder.setContext( { ...builder.context, ...this.value } );

		this.node.build( builder );

		builder.setContext( previousContext );

	}

	setup( builder ) {

		const previousContext = builder.getContext();

		builder.setContext( { ...builder.context, ...this.value } );

		this.node.build( builder );

		builder.setContext( previousContext );

	}

	generate( builder, output ) {

		const previousContext = builder.getContext();

		builder.setContext( { ...builder.context, ...this.value } );

		const snippet = this.node.build( builder, output );

		builder.setContext( previousContext );

		return snippet;

	}

}
```
</details>

#### Methods

##### `getScope(): Node`

<details><summary>Code</summary>

```ts
getScope() {

		return this.node.getScope();

	}
```
</details>

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return this.node.getNodeType( builder );

	}
```
</details>

##### `analyze(builder: any): void`

<details><summary>Code</summary>

```ts
analyze( builder ) {

		const previousContext = builder.getContext();

		builder.setContext( { ...builder.context, ...this.value } );

		this.node.build( builder );

		builder.setContext( previousContext );

	}
```
</details>

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const previousContext = builder.getContext();

		builder.setContext( { ...builder.context, ...this.value } );

		this.node.build( builder );

		builder.setContext( previousContext );

	}
```
</details>

##### `generate(builder: any, output: any): string | Node`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		const previousContext = builder.getContext();

		builder.setContext( { ...builder.context, ...this.value } );

		const snippet = this.node.build( builder, output );

		builder.setContext( previousContext );

		return snippet;

	}
```
</details>


---