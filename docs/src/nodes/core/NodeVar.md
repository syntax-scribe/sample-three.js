[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NodeVar.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |

## 📚 Table of Contents

- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/NodeVar.js`**

## Classes

### `NodeVar`

<details><summary>Class Code</summary>

```ts
class NodeVar {

	/**
	 * Constructs a new node variable.
	 *
	 * @param {string} name - The name of the variable.
	 * @param {string} type - The type of the variable.
	 * @param {boolean} [readOnly=false] - The read-only flag.
	 * @param {?number} [count=null] - The size.
	 */
	constructor( name, type, readOnly = false, count = null ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isNodeVar = true;

		/**
		 * The name of the variable.
		 *
		 * @type {string}
		 */
		this.name = name;

		/**
		 * The type of the variable.
		 *
		 * @type {string}
		 */
		this.type = type;

		/**
		 *  The read-only flag.
		 *
		 * @type {boolean}
		 */
		this.readOnly = readOnly;

		/**
		 * The size.
		 *
		 * @type {?number}
		 */
		this.count = count;

	}

}
```
</details>


---