[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `InstancedMeshNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/InstancedMeshNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `InstanceNode` | `./InstanceNode.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |


---

## Classes

### `InstancedMeshNode`

<details><summary>Class Code</summary>

```ts
class InstancedMeshNode extends InstanceNode {

	static get type() {

		return 'InstancedMeshNode';

	}

	/**
	 * Constructs a new instanced mesh node.
	 *
	 * @param {InstancedMesh} instancedMesh - The instanced mesh.
	 */
	constructor( instancedMesh ) {

		const { count, instanceMatrix, instanceColor } = instancedMesh;

		super( count, instanceMatrix, instanceColor );

		/**
		 * A reference to the instanced mesh.
		 *
		 * @type {InstancedMesh}
		 */
		this.instancedMesh = instancedMesh;

	}

}
```
</details>


---