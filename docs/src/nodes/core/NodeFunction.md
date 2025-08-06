[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NodeFunction.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |

## 📚 Table of Contents

- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/NodeFunction.js`**

## Functions

### `NodeFunction.getCode(): string`

**JSDoc:**
```typescript
/**
	 * This method returns the native code of the node function.
	 *
	 * @abstract
	 * @param {string} name - The function's name.
	 * @return {string} A shader code.
	 */
```

**Returns:** `string`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
getCode( /*name = this.name*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>


---

## Classes

### `NodeFunction`

<details><summary>Class Code</summary>

```ts
class NodeFunction {

	/**
	 * Constructs a new node function.
	 *
	 * @param {string} type - The node type. This type is the return type of the node function.
	 * @param {Array<NodeFunctionInput>} inputs - The function's inputs.
	 * @param {string} [name=''] - The function's name.
	 * @param {string} [precision=''] - The precision qualifier.
	 */
	constructor( type, inputs, name = '', precision = '' ) {

		/**
		 * The node type. This type is the return type of the node function.
		 *
		 * @type {string}
		 */
		this.type = type;

		/**
		 * The function's inputs.
		 *
		 * @type {Array<NodeFunctionInput>}
		 */
		this.inputs = inputs;

		/**
		 * The name of the uniform.
		 *
		 * @type {string}
		 * @default ''
		 */
		this.name = name;

		/**
		 * The precision qualifier.
		 *
		 * @type {string}
		 * @default ''
		 */
		this.precision = precision;

	}

	/**
	 * This method returns the native code of the node function.
	 *
	 * @abstract
	 * @param {string} name - The function's name.
	 * @return {string} A shader code.
	 */
	getCode( /*name = this.name*/ ) {

		console.warn( 'Abstract function.' );

	}

}
```
</details>

#### Methods

##### `getCode(): string`

<details><summary>Code</summary>

```ts
getCode( /*name = this.name*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>


---