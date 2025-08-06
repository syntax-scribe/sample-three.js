[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `NodeUniformsGroup.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/nodes/NodeUniformsGroup.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UniformsGroup` | `../UniformsGroup.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_id` | `number` | let/var | `0` | ✗ |


---

## Classes

### `NodeUniformsGroup`

<details><summary>Class Code</summary>

```ts
class NodeUniformsGroup extends UniformsGroup {

	/**
	 * Constructs a new node-based uniforms group.
	 *
	 * @param {string} name - The group's name.
	 * @param {UniformGroupNode} groupNode - The uniform group node.
	 */
	constructor( name, groupNode ) {

		super( name );

		/**
		 * The group's ID.
		 *
		 * @type {number}
		 */
		this.id = _id ++;

		/**
		 * The uniform group node.
		 *
		 * @type {UniformGroupNode}
		 */
		this.groupNode = groupNode;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isNodeUniformsGroup = true;

	}

}
```
</details>


---