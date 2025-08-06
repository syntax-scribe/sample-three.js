[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BindGroup.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/BindGroup.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_id` | `number` | let/var | `0` | ✗ |


---

## Classes

### `BindGroup`

<details><summary>Class Code</summary>

```ts
class BindGroup {

	/**
	 * Constructs a new bind group.
	 *
	 * @param {string} name - The bind group's name.
	 * @param {Array<Binding>} bindings - An array of bindings.
	 * @param {number} index - The group index.
	 * @param {Array<Binding>} bindingsReference - An array of reference bindings.
	 */
	constructor( name = '', bindings = [], index = 0, bindingsReference = [] ) {

		/**
		 * The bind group's name.
		 *
		 * @type {string}
		 */
		this.name = name;

		/**
		 * An array of bindings.
		 *
		 * @type {Array<Binding>}
		 */
		this.bindings = bindings;

		/**
		 * The group index.
		 *
		 * @type {number}
		 */
		this.index = index;

		/**
		 * An array of reference bindings.
		 *
		 * @type {Array<Binding>}
		 */
		this.bindingsReference = bindingsReference;

		/**
		 * The group's ID.
		 *
		 * @type {number}
		 */
		this.id = _id ++;

	}

}
```
</details>


---