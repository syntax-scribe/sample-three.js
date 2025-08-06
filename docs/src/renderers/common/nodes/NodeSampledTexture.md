[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `NodeSampledTexture.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 3 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/nodes/NodeSampledTexture.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `SampledTexture` | `../SampledTexture.js` |


---

## Functions

### `NodeSampledTexture.update(): boolean`

**JSDoc:**
```typescript
/**
	 * Updates the binding.
	 *
	 * @return {boolean} Whether the texture has been updated and must be
	 * uploaded to the GPU.
	 */
```

**Returns:** `boolean`

**Calls:**

- `super.update`

<details><summary>Code</summary>

```typescript
update() {

		const { textureNode } = this;

		if ( this.texture !== textureNode.value ) {

			this.texture = textureNode.value;

			return true;

		}

		return super.update();

	}
```
</details>


---

## Classes

### `NodeSampledTexture`

<details><summary>Class Code</summary>

```ts
class NodeSampledTexture extends SampledTexture {

	/**
	 * Constructs a new node-based sampled texture.
	 *
	 * @param {string} name - The textures's name.
	 * @param {TextureNode} textureNode - The texture node.
	 * @param {UniformGroupNode} groupNode - The uniform group node.
	 * @param {?string} [access=null] - The access type.
	 */
	constructor( name, textureNode, groupNode, access = null ) {

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

		/**
		 * The access type.
		 *
		 * @type {?string}
		 * @default null
		 */
		this.access = access;

	}

	/**
	 * Updates the binding.
	 *
	 * @return {boolean} Whether the texture has been updated and must be
	 * uploaded to the GPU.
	 */
	update() {

		const { textureNode } = this;

		if ( this.texture !== textureNode.value ) {

			this.texture = textureNode.value;

			return true;

		}

		return super.update();

	}

}
```
</details>

#### Methods

##### `update(): boolean`

<details><summary>Code</summary>

```ts
update() {

		const { textureNode } = this;

		if ( this.texture !== textureNode.value ) {

			this.texture = textureNode.value;

			return true;

		}

		return super.update();

	}
```
</details>

### `NodeSampledCubeTexture`

<details><summary>Class Code</summary>

```ts
class NodeSampledCubeTexture extends NodeSampledTexture {

	/**
	 * Constructs a new node-based sampled cube texture.
	 *
	 * @param {string} name - The textures's name.
	 * @param {TextureNode} textureNode - The texture node.
	 * @param {UniformGroupNode} groupNode - The uniform group node.
	 * @param {?string} [access=null] - The access type.
	 */
	constructor( name, textureNode, groupNode, access = null ) {

		super( name, textureNode, groupNode, access );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSampledCubeTexture = true;

	}

}
```
</details>

### `NodeSampledTexture3D`

<details><summary>Class Code</summary>

```ts
class NodeSampledTexture3D extends NodeSampledTexture {

	/**
	 * Constructs a new node-based sampled 3D texture.
	 *
	 * @param {string} name - The textures's name.
	 * @param {TextureNode} textureNode - The texture node.
	 * @param {UniformGroupNode} groupNode - The uniform group node.
	 * @param {?string} [access=null] - The access type.
	 */
	constructor( name, textureNode, groupNode, access = null ) {

		super( name, textureNode, groupNode, access );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSampledTexture3D = true;

	}

}
```
</details>


---