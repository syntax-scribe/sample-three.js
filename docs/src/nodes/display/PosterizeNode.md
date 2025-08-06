[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PosterizeNode.js`

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
📂 **`src/nodes/display/PosterizeNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `../core/TempNode.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |


---

## Functions

### `PosterizeNode.setup(): any`

**Returns:** `any`

**Calls:**

- `sourceNode.mul( stepsNode ).floor().div`

<details><summary>Code</summary>

```typescript
setup() {

		const { sourceNode, stepsNode } = this;

		return sourceNode.mul( stepsNode ).floor().div( stepsNode );

	}
```
</details>


---

## Classes

### `PosterizeNode`

<details><summary>Class Code</summary>

```ts
class PosterizeNode extends TempNode {

	static get type() {

		return 'PosterizeNode';

	}

	/**
	 * Constructs a new posterize node.
	 *
	 * @param {Node} sourceNode - The input color.
	 * @param {Node} stepsNode - Controls the intensity of the posterization effect. A lower number results in a more blocky appearance.
	 */
	constructor( sourceNode, stepsNode ) {

		super();

		/**
		 * The input color.
		 *
		 * @type {Node}
		 */
		this.sourceNode = sourceNode;

		/**
		 * Controls the intensity of the posterization effect. A lower number results in a more blocky appearance.
		 *
		 * @type {Node}
		 */
		this.stepsNode = stepsNode;

	}

	setup() {

		const { sourceNode, stepsNode } = this;

		return sourceNode.mul( stepsNode ).floor().div( stepsNode );

	}

}
```
</details>

#### Methods

##### `setup(): any`

<details><summary>Code</summary>

```ts
setup() {

		const { sourceNode, stepsNode } = this;

		return sourceNode.mul( stepsNode ).floor().div( stepsNode );

	}
```
</details>


---