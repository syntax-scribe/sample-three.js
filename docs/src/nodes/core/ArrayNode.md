[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ArrayNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/ArrayNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `./TempNode.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `nodeObject` | `../tsl/TSLCore.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `node` | `any` | let/var | `*not shown*` | ✗ |
| `values` | `any` | let/var | `params[ 0 ]` | ✗ |
| `nodeType` | `any` | let/var | `params[ 0 ]` | ✗ |
| `count` | `any` | let/var | `params[ 1 ]` | ✗ |


---

## Functions

### `ArrayNode.getArrayCount(): number`

**JSDoc:**
```typescript
/**
	 * Returns the number of elements in the node array.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {number} The number of elements in the node array.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getArrayCount( /*builder*/ ) {

		return this.count;

	}
```
</details>

### `ArrayNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * Returns the node's type.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The type of the node.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.values[ 0 ].getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		if ( this.nodeType === null ) {

			this.nodeType = this.values[ 0 ].getNodeType( builder );

		}

		return this.nodeType;

	}
```
</details>

### `ArrayNode.getElementType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * Returns the node's type.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The type of the node.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.getNodeType`

<details><summary>Code</summary>

```typescript
getElementType( builder ) {

		return this.getNodeType( builder );

	}
```
</details>

### `ArrayNode.generate(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * This method builds the output node and returns the resulting array as a shader string.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The generated shader string.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.getNodeType`
- `builder.generateArray`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const type = this.getNodeType( builder );

		return builder.generateArray( type, this.count, this.values );

	}
```
</details>

### `array(params: any[]): ArrayNode`

**Parameters:**

- **`params`** `any[]`

**Returns:** `ArrayNode`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( ...params ) => {

	let node;

	if ( params.length === 1 ) {

		const values = params[ 0 ];

		node = new ArrayNode( null, values.length, values );

	} else {

		const nodeType = params[ 0 ];
		const count = params[ 1 ];

		node = new ArrayNode( nodeType, count );

	}

	return nodeObject( node );

}
```
</details>


---

## Classes

### `ArrayNode`

<details><summary>Class Code</summary>

```ts
class ArrayNode extends TempNode {

	static get type() {

		return 'ArrayNode';

	}

	/**
	 * Constructs a new array node.
	 *
	 * @param {?string} nodeType - The data type of the elements.
	 * @param {number} count - Size of the array.
	 * @param {?Array<Node>} [values=null] - Array default values.
	 */
	constructor( nodeType, count, values = null ) {

		super( nodeType );

		/**
		 * Array size.
		 *
		 * @type {number}
		 */
		this.count = count;

		/**
		 * Array default values.
		 *
		 * @type {?Array<Node>}
		 */
		this.values = values;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isArrayNode = true;

	}

	/**
	 * Returns the number of elements in the node array.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {number} The number of elements in the node array.
	 */
	getArrayCount( /*builder*/ ) {

		return this.count;

	}

	/**
	 * Returns the node's type.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The type of the node.
	 */
	getNodeType( builder ) {

		if ( this.nodeType === null ) {

			this.nodeType = this.values[ 0 ].getNodeType( builder );

		}

		return this.nodeType;

	}

	/**
	 * Returns the node's type.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The type of the node.
	 */
	getElementType( builder ) {

		return this.getNodeType( builder );

	}

	/**
	 * This method builds the output node and returns the resulting array as a shader string.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The generated shader string.
	 */
	generate( builder ) {

		const type = this.getNodeType( builder );

		return builder.generateArray( type, this.count, this.values );

	}

}
```
</details>

#### Methods

##### `getArrayCount(): number`

<details><summary>Code</summary>

```ts
getArrayCount( /*builder*/ ) {

		return this.count;

	}
```
</details>

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		if ( this.nodeType === null ) {

			this.nodeType = this.values[ 0 ].getNodeType( builder );

		}

		return this.nodeType;

	}
```
</details>

##### `getElementType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getElementType( builder ) {

		return this.getNodeType( builder );

	}
```
</details>

##### `generate(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const type = this.getNodeType( builder );

		return builder.generateArray( type, this.count, this.values );

	}
```
</details>


---