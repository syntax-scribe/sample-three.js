[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TextureSizeNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/TextureSizeNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `level` | `any` | let/var | `this.levelNode === null ? '0' : this.levelNode.build( builder, 'int' )` | ✗ |


---

## Functions

### `TextureSizeNode.generate(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `this.textureNode.build`
- `this.levelNode.build`
- `builder.format`
- `builder.getMethod`
- `this.getNodeType`

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		const textureProperty = this.textureNode.build( builder, 'property' );
		const level = this.levelNode === null ? '0' : this.levelNode.build( builder, 'int' );

		return builder.format( `${ builder.getMethod( 'textureDimensions' ) }( ${ textureProperty }, ${ level } )`, this.getNodeType( builder ), output );

	}
```
</details>


---

## Classes

### `TextureSizeNode`

<details><summary>Class Code</summary>

```ts
class TextureSizeNode extends Node {

	static get type() {

		return 'TextureSizeNode';

	}

	/**
	 * Constructs a new texture size node.
	 *
	 * @param {TextureNode} textureNode - A texture node which size should be retrieved.
	 * @param {?Node<int>} [levelNode=null] - A level node which defines the requested mip.
	 */
	constructor( textureNode, levelNode = null ) {

		super( 'uvec2' );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isTextureSizeNode = true;

		/**
		 * A texture node which size should be retrieved.
		 *
		 * @type {TextureNode}
		 */
		this.textureNode = textureNode;

		/**
		 * A level node which defines the requested mip.
		 *
		 * @type {Node<int>}
		 * @default null
		 */
		this.levelNode = levelNode;

	}

	generate( builder, output ) {

		const textureProperty = this.textureNode.build( builder, 'property' );
		const level = this.levelNode === null ? '0' : this.levelNode.build( builder, 'int' );

		return builder.format( `${ builder.getMethod( 'textureDimensions' ) }( ${ textureProperty }, ${ level } )`, this.getNodeType( builder ), output );

	}

}
```
</details>

#### Methods

##### `generate(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		const textureProperty = this.textureNode.build( builder, 'property' );
		const level = this.levelNode === null ? '0' : this.levelNode.build( builder, 'int' );

		return builder.format( `${ builder.getMethod( 'textureDimensions' ) }( ${ textureProperty }, ${ level } )`, this.getNodeType( builder ), output );

	}
```
</details>


---