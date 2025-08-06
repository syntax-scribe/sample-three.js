[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MaxMipLevelNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/utils/MaxMipLevelNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UniformNode` | `../core/UniformNode.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `texture` | `Texture` | let/var | `this.texture` | ✗ |
| `images` | `any` | let/var | `texture.images` | ✗ |
| `image` | `any` | let/var | `( images && images.length > 0 ) ? ( ( images[ 0 ] && images[ 0 ].image ) \|\|...` | ✗ |


---

## Functions

### `MaxMipLevelNode.update(): void`

**Returns:** `void`

**Calls:**

- `Math.log2`
- `Math.max`

<details><summary>Code</summary>

```typescript
update() {

		const texture = this.texture;
		const images = texture.images;
		const image = ( images && images.length > 0 ) ? ( ( images[ 0 ] && images[ 0 ].image ) || images[ 0 ] ) : texture.image;

		if ( image && image.width !== undefined ) {

			const { width, height } = image;

			this.value = Math.log2( Math.max( width, height ) );

		}

	}
```
</details>


---

## Classes

### `MaxMipLevelNode`

<details><summary>Class Code</summary>

```ts
class MaxMipLevelNode extends UniformNode {

	static get type() {

		return 'MaxMipLevelNode';

	}

	/**
	 * Constructs a new max mip level node.
	 *
	 * @param {TextureNode} textureNode - The texture node to compute the max mip level for.
	 */
	constructor( textureNode ) {

		super( 0 );

		/**
		 * The texture node to compute the max mip level for.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._textureNode = textureNode;

		/**
		 * The `updateType` is set to `NodeUpdateType.FRAME` since the node updates
		 * the texture once per frame in its {@link MaxMipLevelNode#update} method.
		 *
		 * @type {string}
		 * @default 'frame'
		 */
		this.updateType = NodeUpdateType.FRAME;

	}

	/**
	 * The texture node to compute the max mip level for.
	 *
	 * @readonly
	 * @type {TextureNode}
	 */
	get textureNode() {

		return this._textureNode;

	}

	/**
	 * The texture.
	 *
	 * @readonly
	 * @type {Texture}
	 */
	get texture() {

		return this._textureNode.value;

	}

	update() {

		const texture = this.texture;
		const images = texture.images;
		const image = ( images && images.length > 0 ) ? ( ( images[ 0 ] && images[ 0 ].image ) || images[ 0 ] ) : texture.image;

		if ( image && image.width !== undefined ) {

			const { width, height } = image;

			this.value = Math.log2( Math.max( width, height ) );

		}

	}

}
```
</details>

#### Methods

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		const texture = this.texture;
		const images = texture.images;
		const image = ( images && images.length > 0 ) ? ( ( images[ 0 ] && images[ 0 ].image ) || images[ 0 ] ) : texture.image;

		if ( image && image.width !== undefined ) {

			const { width, height } = image;

			this.value = Math.log2( Math.max( width, height ) );

		}

	}
```
</details>


---