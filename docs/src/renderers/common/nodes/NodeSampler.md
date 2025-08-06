[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `NodeSampler.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/nodes/NodeSampler.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Sampler` | `../Sampler.js` |


---

## Functions

### `NodeSampler.update(): void`

**JSDoc:**
```typescript
/**
	 * Updates the texture value of this sampler.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
update() {

		this.texture = this.textureNode.value;

	}
```
</details>


---

## Classes

### `NodeSampler`

<details><summary>Class Code</summary>

```ts
class NodeSampler extends Sampler {

	/**
	 * Constructs a new node-based sampler.
	 *
	 * @param {string} name - The samplers's name.
	 * @param {TextureNode} textureNode - The texture node.
	 * @param {UniformGroupNode} groupNode - The uniform group node.
	 */
	constructor( name, textureNode, groupNode ) {

		super( name, textureNode ? textureNode.value : null );

		/**
		 * The texture node.
		 *
		 * @type {TextureNode}
		 */
		this.textureNode = textureNode;

		/**
		 * The uniform group node.
		 *
		 * @type {UniformGroupNode}
		 */
		this.groupNode = groupNode;

	}

	/**
	 * Updates the texture value of this sampler.
	 */
	update() {

		this.texture = this.textureNode.value;

	}

}
```
</details>

#### Methods

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		this.texture = this.textureNode.value;

	}
```
</details>


---