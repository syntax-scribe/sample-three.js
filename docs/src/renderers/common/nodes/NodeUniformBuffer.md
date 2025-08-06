[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `NodeUniformBuffer.js`

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
📂 **`src/renderers/common/nodes/NodeUniformBuffer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UniformBuffer` | `../UniformBuffer.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_id` | `number` | let/var | `0` | ✗ |


---

## Classes

### `NodeUniformBuffer`

<details><summary>Class Code</summary>

```ts
class NodeUniformBuffer extends UniformBuffer {

	/**
	 * Constructs a new node-based uniform buffer.
	 *
	 * @param {BufferNode} nodeUniform - The uniform buffer node.
	 * @param {UniformGroupNode} groupNode - The uniform group node.
	 */
	constructor( nodeUniform, groupNode ) {

		super( 'UniformBuffer_' + _id ++, nodeUniform ? nodeUniform.value : null );

		/**
		 * The uniform buffer node.
		 *
		 * @type {BufferNode}
		 */
		this.nodeUniform = nodeUniform;

		/**
		 * The uniform group node.
		 *
		 * @type {UniformGroupNode}
		 */
		this.groupNode = groupNode;

	}

	/**
	 * The uniform buffer.
	 *
	 * @type {Float32Array}
	 */
	get buffer() {

		return this.nodeUniform.value;

	}

}
```
</details>


---