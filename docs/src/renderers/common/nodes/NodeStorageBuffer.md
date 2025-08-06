[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `NodeStorageBuffer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/nodes/NodeStorageBuffer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `StorageBuffer` | `../StorageBuffer.js` |
| `NodeAccess` | `../../../nodes/core/constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_id` | `number` | let/var | `0` | ✗ |


---

## Classes

### `NodeStorageBuffer`

<details><summary>Class Code</summary>

```ts
class NodeStorageBuffer extends StorageBuffer {

	/**
	 * Constructs a new node-based storage buffer.
	 *
	 * @param {StorageBufferNode} nodeUniform - The storage buffer node.
	 * @param {UniformGroupNode} groupNode - The uniform group node.
	 */
	constructor( nodeUniform, groupNode ) {

		super( 'StorageBuffer_' + _id ++, nodeUniform ? nodeUniform.value : null );

		/**
		 * The node uniform.
		 *
		 * @type {StorageBufferNode}
		 */
		this.nodeUniform = nodeUniform;

		/**
		 * The access type.
		 *
		 * @type {string}
		 */
		this.access = nodeUniform ? nodeUniform.access : NodeAccess.READ_WRITE;

		/**
		 * The uniform group node.
		 *
		 * @type {UniformGroupNode}
		 */
		this.groupNode = groupNode;

	}

	/**
	 * The storage buffer.
	 *
	 * @type {BufferAttribute}
	 */
	get buffer() {

		return this.nodeUniform.value;

	}

}
```
</details>


---