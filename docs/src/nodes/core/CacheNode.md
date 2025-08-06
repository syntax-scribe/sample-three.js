[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CacheNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/CacheNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `./Node.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `nodeObject` | `../tsl/TSLCore.js` |


---

## Functions

### `CacheNode.getNodeType(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `builder.getCache`
- `builder.getCacheFromNode`
- `builder.setCache`
- `this.node.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		const previousCache = builder.getCache();
		const cache = builder.getCacheFromNode( this, this.parent );

		builder.setCache( cache );

		const nodeType = this.node.getNodeType( builder );

		builder.setCache( previousCache );

		return nodeType;

	}
```
</details>

### `CacheNode.build(builder: any, params: any[]): string | Node`

**Parameters:**

- **`builder`** `any`
- **`params`** `any[]`

**Returns:** `string | Node`

**Calls:**

- `builder.getCache`
- `builder.getCacheFromNode`
- `builder.setCache`
- `this.node.build`

<details><summary>Code</summary>

```typescript
build( builder, ...params ) {

		const previousCache = builder.getCache();
		const cache = builder.getCacheFromNode( this, this.parent );

		builder.setCache( cache );

		const data = this.node.build( builder, ...params );

		builder.setCache( previousCache );

		return data;

	}
```
</details>

### `cache(node: Node, parent: boolean): CacheNode`

**Parameters:**

- **`node`** `Node`
- **`parent`** `boolean`

**Returns:** `CacheNode`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( node, parent ) => nodeObject( new CacheNode( nodeObject( node ), parent ) )
```
</details>


---

## Classes

### `CacheNode`

<details><summary>Class Code</summary>

```ts
class CacheNode extends Node {

	static get type() {

		return 'CacheNode';

	}

	/**
	 * Constructs a new cache node.
	 *
	 * @param {Node} node - The node that should be cached.
	 * @param {boolean} [parent=true] - Whether this node refers to a shared parent cache or not.
	 */
	constructor( node, parent = true ) {

		super();

		/**
		 * The node that should be cached.
		 *
		 * @type {Node}
		 */
		this.node = node;

		/**
		 * Whether this node refers to a shared parent cache or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.parent = parent;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isCacheNode = true;

	}

	getNodeType( builder ) {

		const previousCache = builder.getCache();
		const cache = builder.getCacheFromNode( this, this.parent );

		builder.setCache( cache );

		const nodeType = this.node.getNodeType( builder );

		builder.setCache( previousCache );

		return nodeType;

	}

	build( builder, ...params ) {

		const previousCache = builder.getCache();
		const cache = builder.getCacheFromNode( this, this.parent );

		builder.setCache( cache );

		const data = this.node.build( builder, ...params );

		builder.setCache( previousCache );

		return data;

	}

}
```
</details>

#### Methods

##### `getNodeType(builder: any): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		const previousCache = builder.getCache();
		const cache = builder.getCacheFromNode( this, this.parent );

		builder.setCache( cache );

		const nodeType = this.node.getNodeType( builder );

		builder.setCache( previousCache );

		return nodeType;

	}
```
</details>

##### `build(builder: any, params: any[]): string | Node`

<details><summary>Code</summary>

```ts
build( builder, ...params ) {

		const previousCache = builder.getCache();
		const cache = builder.getCacheFromNode( this, this.parent );

		builder.setCache( cache );

		const data = this.node.build( builder, ...params );

		builder.setCache( previousCache );

		return data;

	}
```
</details>


---