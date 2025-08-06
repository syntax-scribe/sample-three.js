[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BufferNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/BufferNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UniformNode` | `../core/UniformNode.js` |
| `nodeObject` | `../tsl/TSLBase.js` |


---

## Functions

### `BufferNode.getElementType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * The data type of the buffer elements.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The element type.
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

### `BufferNode.getInputType(): string`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation to return a fixed value `'buffer'`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getInputType( /*builder*/ ) {

		return 'buffer';

	}
```
</details>

### `buffer(value: any[], type: string, count: number): BufferNode`

**Parameters:**

- **`value`** `any[]`
- **`type`** `string`
- **`count`** `number`

**Returns:** `BufferNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( value, type, count ) => nodeObject( new BufferNode( value, type, count ) )
```
</details>


---

## Classes

### `BufferNode`

<details><summary>Class Code</summary>

```ts
class BufferNode extends UniformNode {

	static get type() {

		return 'BufferNode';

	}

	/**
	 * Constructs a new buffer node.
	 *
	 * @param {Array<number>} value - Array-like buffer data.
	 * @param {string} bufferType - The data type of the buffer.
	 * @param {number} [bufferCount=0] - The count of buffer elements.
	 */
	constructor( value, bufferType, bufferCount = 0 ) {

		super( value, bufferType );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isBufferNode = true;

		/**
		 * The data type of the buffer.
		 *
		 * @type {string}
		 */
		this.bufferType = bufferType;

		/**
		 * The uniform node that holds the value of the reference node.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.bufferCount = bufferCount;

	}

	/**
	 * The data type of the buffer elements.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The element type.
	 */
	getElementType( builder ) {

		return this.getNodeType( builder );

	}

	/**
	 * Overwrites the default implementation to return a fixed value `'buffer'`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
	getInputType( /*builder*/ ) {

		return 'buffer';

	}

}
```
</details>

#### Methods

##### `getElementType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getElementType( builder ) {

		return this.getNodeType( builder );

	}
```
</details>

##### `getInputType(): string`

<details><summary>Code</summary>

```ts
getInputType( /*builder*/ ) {

		return 'buffer';

	}
```
</details>


---