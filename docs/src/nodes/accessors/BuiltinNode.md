[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BuiltinNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/BuiltinNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |


---

## Functions

### `BuiltinNode.generate(): string`

**JSDoc:**
```typescript
/**
	 * Generates the code snippet of the builtin node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The generated code snippet.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
generate( /* builder */ ) {

		return this.name;

	}
```
</details>


---

## Classes

### `BuiltinNode`

<details><summary>Class Code</summary>

```ts
class BuiltinNode extends Node {

	/**
	 * Constructs a new builtin node.
	 *
	 * @param {string} name - The name of the built-in shader variable.
	 */
	constructor( name ) {

		super( 'float' );

		/**
		 * The name of the built-in shader variable.
		 *
		 * @type {string}
		 */
		this.name = name;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isBuiltinNode = true;

	}

	/**
	 * Generates the code snippet of the builtin node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The generated code snippet.
	 */
	generate( /* builder */ ) {

		return this.name;

	}

}
```
</details>

#### Methods

##### `generate(): string`

<details><summary>Code</summary>

```ts
generate( /* builder */ ) {

		return this.name;

	}
```
</details>


---