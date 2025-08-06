[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NodeCode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |

## 📚 Table of Contents

- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/NodeCode.js`**

## Classes

### `NodeCode`

<details><summary>Class Code</summary>

```ts
class NodeCode {

	/**
	 * Constructs a new code node.
	 *
	 * @param {string} name - The name of the code.
	 * @param {string} type - The node type.
	 * @param {string} [code=''] - The native shader code.
	 */
	constructor( name, type, code = '' ) {

		/**
		 * The name of the code.
		 *
		 * @type {string}
		 */
		this.name = name;

		/**
		 * The node type.
		 *
		 * @type {string}
		 */
		this.type = type;

		/**
		 * The native shader code.
		 *
		 * @type {string}
		 * @default ''
		 */
		this.code = code;

		Object.defineProperty( this, 'isNodeCode', { value: true } );

	}

}
```
</details>


---