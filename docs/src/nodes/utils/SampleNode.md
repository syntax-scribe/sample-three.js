[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SampleNode.js`

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
📂 **`src/nodes/utils/SampleNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `uv` | `../accessors/UV.js` |
| `nodeObject` | `../tsl/TSLCore.js` |


---

## Functions

### `SampleNode.setup(): Node`

**JSDoc:**
```typescript
/**
	 * Sets up the node by sampling with the default UV accessor.
	 *
	 * @returns {Node} The result of the callback function when called with the UV node.
	 */
```

**Returns:** `Node`

**Calls:**

- `this.sample`
- `uv (from ../accessors/UV.js)`

<details><summary>Code</summary>

```typescript
setup() {

		return this.sample( uv() );

	}
```
</details>

### `SampleNode.sample(uv: any): Node`

**JSDoc:**
```typescript
/**
	 * Calls the callback function with the provided UV node.
	 *
	 * @param {Node<vec2>} uv - The UV node or value to be passed to the callback.
	 * @returns {Node} The result of the callback function.
	 */
```

**Parameters:**

- **`uv`** `any`

**Returns:** `Node`

**Calls:**

- `this.callback`

<details><summary>Code</summary>

```typescript
sample( uv ) {

		return this.callback( uv );

	}
```
</details>

### `sample(callback: Function): SampleNode`

**Parameters:**

- **`callback`** `Function`

**Returns:** `SampleNode`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( callback ) => nodeObject( new SampleNode( callback ) )
```
</details>


---

## Classes

### `SampleNode`

<details><summary>Class Code</summary>

```ts
class SampleNode extends Node {

	/**
	 * Returns the type of the node.
	 *
	 * @type {string}
	 * @readonly
	 * @static
	 */
	static get type() {

		return 'SampleNode';

	}

	/**
	 * Creates an instance of SampleNode.
	 *
	 * @param {Function} callback - The function to be called when sampling. Should accept a UV node and return a value.
	 */
	constructor( callback ) {

		super();

		this.callback = callback;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSampleNode = true;

	}

	/**
	 * Sets up the node by sampling with the default UV accessor.
	 *
	 * @returns {Node} The result of the callback function when called with the UV node.
	 */
	setup() {

		return this.sample( uv() );

	}

	/**
	 * Calls the callback function with the provided UV node.
	 *
	 * @param {Node<vec2>} uv - The UV node or value to be passed to the callback.
	 * @returns {Node} The result of the callback function.
	 */
	sample( uv ) {

		return this.callback( uv );

	}

}
```
</details>

#### Methods

##### `setup(): Node`

<details><summary>Code</summary>

```ts
setup() {

		return this.sample( uv() );

	}
```
</details>

##### `sample(uv: any): Node`

<details><summary>Code</summary>

```ts
sample( uv ) {

		return this.callback( uv );

	}
```
</details>


---