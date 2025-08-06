[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NodeCache.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/NodeCache.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_id` | `number` | let/var | `0` | ✗ |


---

## Functions

### `NodeCache.getData(node: Node): any`

**JSDoc:**
```typescript
/**
	 * Returns the data for the given node.
	 *
	 * @param {Node} node - The node.
	 * @return {?Object} The data for the node.
	 */
```

**Parameters:**

- **`node`** `Node`

**Returns:** `any`

**Calls:**

- `this.nodesData.get`
- `this.parent.getData`

<details><summary>Code</summary>

```typescript
getData( node ) {

		let data = this.nodesData.get( node );

		if ( data === undefined && this.parent !== null ) {

			data = this.parent.getData( node );

		}

		return data;

	}
```
</details>

### `NodeCache.setData(node: Node, data: any): void`

**JSDoc:**
```typescript
/**
	 * Sets the data for a given node.
	 *
	 * @param {Node} node - The node.
	 * @param {Object} data - The data that should be cached.
	 */
```

**Parameters:**

- **`node`** `Node`
- **`data`** `any`

**Returns:** `void`

**Calls:**

- `this.nodesData.set`

<details><summary>Code</summary>

```typescript
setData( node, data ) {

		this.nodesData.set( node, data );

	}
```
</details>


---

## Classes

### `NodeCache`

<details><summary>Class Code</summary>

```ts
class NodeCache {

	/**
	 * Constructs a new node cache.
	 *
	 * @param {?NodeCache} parent - A reference to a parent cache.
	 */
	constructor( parent = null ) {

		/**
		 * The id of the cache.
		 *
		 * @type {number}
		 * @readonly
		 */
		this.id = _id ++;

		/**
		 * A weak map for managing node data.
		 *
		 * @type {WeakMap<Node, Object>}
		 */
		this.nodesData = new WeakMap();

		/**
		 * Reference to a parent node cache.
		 *
		 * @type {?NodeCache}
		 * @default null
		 */
		this.parent = parent;

	}

	/**
	 * Returns the data for the given node.
	 *
	 * @param {Node} node - The node.
	 * @return {?Object} The data for the node.
	 */
	getData( node ) {

		let data = this.nodesData.get( node );

		if ( data === undefined && this.parent !== null ) {

			data = this.parent.getData( node );

		}

		return data;

	}

	/**
	 * Sets the data for a given node.
	 *
	 * @param {Node} node - The node.
	 * @param {Object} data - The data that should be cached.
	 */
	setData( node, data ) {

		this.nodesData.set( node, data );

	}

}
```
</details>

#### Methods

##### `getData(node: Node): any`

<details><summary>Code</summary>

```ts
getData( node ) {

		let data = this.nodesData.get( node );

		if ( data === undefined && this.parent !== null ) {

			data = this.parent.getData( node );

		}

		return data;

	}
```
</details>

##### `setData(node: Node, data: any): void`

<details><summary>Code</summary>

```ts
setData( node, data ) {

		this.nodesData.set( node, data );

	}
```
</details>


---