[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NodeAttribute.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |

## 📚 Table of Contents

- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/NodeAttribute.js`**

## Classes

### `NodeAttribute`

<details><summary>Class Code</summary>

```ts
class NodeAttribute {

	/**
	 * Constructs a new node attribute.
	 *
	 * @param {string} name - The name of the attribute.
	 * @param {string} type - The type of the attribute.
	 * @param {?Node} node - An optional reference to the node.
	 */
	constructor( name, type, node = null ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isNodeAttribute = true;

		/**
		 * The name of the attribute.
		 *
		 * @type {string}
		 */
		this.name = name;

		/**
		 * The type of the attribute.
		 *
		 * @type {string}
		 */
		this.type = type;

		/**
		 * An optional reference to the node.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.node = node;

	}

}
```
</details>


---