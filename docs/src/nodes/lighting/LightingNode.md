[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LightingNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/LightingNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |


---

## Classes

### `LightingNode`

<details><summary>Class Code</summary>

```ts
class LightingNode extends Node {

	static get type() {

		return 'LightingNode';

	}

	/**
	 * Constructs a new lighting node.
	 */
	constructor() {

		super( 'vec3' );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isLightingNode = true;

	}

}
```
</details>


---