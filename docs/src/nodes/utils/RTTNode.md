[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RTTNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/utils/RTTNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `nodeObject` | `../tsl/TSLCore.js` |
| `TextureNode` | `../accessors/TextureNode.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `uv` | `../accessors/UV.js` |
| `NodeMaterial` | `../../materials/nodes/NodeMaterial.js` |
| `QuadMesh` | `../../renderers/common/QuadMesh.js` |
| `RenderTarget` | `../../core/RenderTarget.js` |
| `Vector2` | `../../math/Vector2.js` |
| `HalfFloatType` | `../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_size` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `renderTarget` | `RenderTarget` | let/var | `new RenderTarget( width, height, options )` | ✗ |
| `effectiveWidth` | `number` | let/var | `width * this.pixelRatio` | ✗ |
| `effectiveHeight` | `number` | let/var | `height * this.pixelRatio` | ✗ |
| `effectiveWidth` | `number` | let/var | `size.width * pixelRatio` | ✗ |
| `effectiveHeight` | `number` | let/var | `size.height * pixelRatio` | ✗ |
| `newNode` | `TextureNode` | let/var | `new TextureNode( this.value, this.uvNode, this.levelNode )` | ✗ |


---

## Functions

### `RTTNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `this.node.context`
- `builder.getSharedContext`
- `super.setup`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		this._rttNode = this.node.context( builder.getSharedContext() );
		this._quadMesh.material.name = 'RTT';
		this._quadMesh.material.needsUpdate = true;

		return super.setup( builder );

	}
```
</details>

### `RTTNode.setSize(width: number, height: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the size of the internal render target
	 *
	 * @param {number} width - The width to set.
	 * @param {number} height - The width to set.
	 */
```

**Parameters:**

- **`width`** `number`
- **`height`** `number`

**Returns:** `void`

**Calls:**

- `this.renderTarget.setSize`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this.width = width;
		this.height = height;

		const effectiveWidth = width * this.pixelRatio;
		const effectiveHeight = height * this.pixelRatio;

		this.renderTarget.setSize( effectiveWidth, effectiveHeight );

		this.textureNeedsUpdate = true;

	}
```
</details>

### `RTTNode.setPixelRatio(pixelRatio: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the pixel ratio. This will also resize the render target.
	 *
	 * @param {number} pixelRatio - The pixel ratio to set.
	 */
```

**Parameters:**

- **`pixelRatio`** `number`

**Returns:** `void`

**Calls:**

- `this.setSize`

<details><summary>Code</summary>

```typescript
setPixelRatio( pixelRatio ) {

		this.pixelRatio = pixelRatio;

		this.setSize( this.width, this.height );

	}
```
</details>

### `RTTNode.updateBefore({ renderer }: any): void`

**Parameters:**

- **`{ renderer }`** `any`

**Returns:** `void`

**Calls:**

- `renderer.getPixelRatio`
- `renderer.getSize`
- `this.renderTarget.setSize`
- `renderer.getRenderTarget`
- `renderer.setRenderTarget`
- `this._quadMesh.render`

**Internal Comments:**
```
// (x9)
```

<details><summary>Code</summary>

```typescript
updateBefore( { renderer } ) {

		if ( this.textureNeedsUpdate === false && this.autoUpdate === false ) return;

		this.textureNeedsUpdate = false;

		//

		if ( this.autoResize === true ) {

			const pixelRatio = renderer.getPixelRatio();
			const size = renderer.getSize( _size );

			const effectiveWidth = size.width * pixelRatio;
			const effectiveHeight = size.height * pixelRatio;

			if ( effectiveWidth !== this.renderTarget.width || effectiveHeight !== this.renderTarget.height ) {

				this.renderTarget.setSize( effectiveWidth, effectiveHeight );

				this.textureNeedsUpdate = true;

			}

		}

		//

		this._quadMesh.material.fragmentNode = this._rttNode;

		//

		const currentRenderTarget = renderer.getRenderTarget();

		renderer.setRenderTarget( this.renderTarget );

		this._quadMesh.render( renderer );

		renderer.setRenderTarget( currentRenderTarget );

	}
```
</details>

### `RTTNode.clone(): TextureNode`

**Returns:** `TextureNode`

<details><summary>Code</summary>

```typescript
clone() {

		const newNode = new TextureNode( this.value, this.uvNode, this.levelNode );
		newNode.sampler = this.sampler;
		newNode.referenceNode = this;

		return newNode;

	}
```
</details>

### `rtt(node: Node, params: any[]): RTTNode`

**Parameters:**

- **`node`** `Node`
- **`params`** `any[]`

**Returns:** `RTTNode`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( node, ...params ) => nodeObject( new RTTNode( nodeObject( node ), ...params ) )
```
</details>

### `convertToTexture(node: Node, params: any[]): RTTNode`

**Parameters:**

- **`node`** `Node`
- **`params`** `any[]`

**Returns:** `RTTNode`

**Calls:**

- `node.getTextureNode`
- `rtt`

<details><summary>Code</summary>

```typescript
( node, ...params ) => {

	if ( node.isTextureNode ) return node;
	if ( node.isPassNode ) return node.getTextureNode();

	return rtt( node, ...params );

}
```
</details>


---

## Classes

### `RTTNode`

<details><summary>Class Code</summary>

```ts
class RTTNode extends TextureNode {

	static get type() {

		return 'RTTNode';

	}

	/**
	 * Constructs a new RTT node.
	 *
	 * @param {Node} node - The node to render a texture with.
	 * @param {?number} [width=null] - The width of the internal render target. If not width is applied, the render target is automatically resized.
	 * @param {?number} [height=null] - The height of the internal render target.
	 * @param {Object} [options={type:HalfFloatType}] - The options for the internal render target.
	 */
	constructor( node, width = null, height = null, options = { type: HalfFloatType } ) {

		const renderTarget = new RenderTarget( width, height, options );

		super( renderTarget.texture, uv() );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isRTTNode = true;

		/**
		 * The node to render a texture with.
		 *
		 * @type {Node}
		 */
		this.node = node;

		/**
		 * The width of the internal render target.
		 * If not width is applied, the render target is automatically resized.
		 *
		 * @type {?number}
		 * @default null
		 */
		this.width = width;

		/**
		 * The height of the internal render target.
		 *
		 * @type {?number}
		 * @default null
		 */
		this.height = height;

		/**
		 * The pixel ratio
		 *
		 * @type {number}
		 * @default 1
		 */
		this.pixelRatio = 1;

		/**
		 * The render target
		 *
		 * @type {RenderTarget}
		 */
		this.renderTarget = renderTarget;

		/**
		 * Whether the texture requires an update or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.textureNeedsUpdate = true;

		/**
		 * Whether the texture should automatically be updated or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.autoUpdate = true;

		/**
		 * The node which is used with the quad mesh for RTT.
		 *
		 * @private
		 * @type {Node}
		 * @default null
		 */
		this._rttNode = null;

		/**
		 * The internal quad mesh for RTT.
		 *
		 * @private
		 * @type {QuadMesh}
		 */
		this._quadMesh = new QuadMesh( new NodeMaterial() );

		/**
		 * The `updateBeforeType` is set to `NodeUpdateType.RENDER` since the node updates
		 * the texture once per render in its {@link RTTNode#updateBefore} method.
		 *
		 * @type {string}
		 * @default 'render'
		 */
		this.updateBeforeType = NodeUpdateType.RENDER;

	}

	/**
	 * Whether the internal render target should automatically be resized or not.
	 *
	 * @type {boolean}
	 * @readonly
	 * @default true
	 */
	get autoResize() {

		return this.width === null;

	}

	setup( builder ) {

		this._rttNode = this.node.context( builder.getSharedContext() );
		this._quadMesh.material.name = 'RTT';
		this._quadMesh.material.needsUpdate = true;

		return super.setup( builder );

	}

	/**
	 * Sets the size of the internal render target
	 *
	 * @param {number} width - The width to set.
	 * @param {number} height - The width to set.
	 */
	setSize( width, height ) {

		this.width = width;
		this.height = height;

		const effectiveWidth = width * this.pixelRatio;
		const effectiveHeight = height * this.pixelRatio;

		this.renderTarget.setSize( effectiveWidth, effectiveHeight );

		this.textureNeedsUpdate = true;

	}

	/**
	 * Sets the pixel ratio. This will also resize the render target.
	 *
	 * @param {number} pixelRatio - The pixel ratio to set.
	 */
	setPixelRatio( pixelRatio ) {

		this.pixelRatio = pixelRatio;

		this.setSize( this.width, this.height );

	}

	updateBefore( { renderer } ) {

		if ( this.textureNeedsUpdate === false && this.autoUpdate === false ) return;

		this.textureNeedsUpdate = false;

		//

		if ( this.autoResize === true ) {

			const pixelRatio = renderer.getPixelRatio();
			const size = renderer.getSize( _size );

			const effectiveWidth = size.width * pixelRatio;
			const effectiveHeight = size.height * pixelRatio;

			if ( effectiveWidth !== this.renderTarget.width || effectiveHeight !== this.renderTarget.height ) {

				this.renderTarget.setSize( effectiveWidth, effectiveHeight );

				this.textureNeedsUpdate = true;

			}

		}

		//

		this._quadMesh.material.fragmentNode = this._rttNode;

		//

		const currentRenderTarget = renderer.getRenderTarget();

		renderer.setRenderTarget( this.renderTarget );

		this._quadMesh.render( renderer );

		renderer.setRenderTarget( currentRenderTarget );

	}

	clone() {

		const newNode = new TextureNode( this.value, this.uvNode, this.levelNode );
		newNode.sampler = this.sampler;
		newNode.referenceNode = this;

		return newNode;

	}

}
```
</details>

#### Methods

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		this._rttNode = this.node.context( builder.getSharedContext() );
		this._quadMesh.material.name = 'RTT';
		this._quadMesh.material.needsUpdate = true;

		return super.setup( builder );

	}
```
</details>

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		this.width = width;
		this.height = height;

		const effectiveWidth = width * this.pixelRatio;
		const effectiveHeight = height * this.pixelRatio;

		this.renderTarget.setSize( effectiveWidth, effectiveHeight );

		this.textureNeedsUpdate = true;

	}
```
</details>

##### `setPixelRatio(pixelRatio: number): void`

<details><summary>Code</summary>

```ts
setPixelRatio( pixelRatio ) {

		this.pixelRatio = pixelRatio;

		this.setSize( this.width, this.height );

	}
```
</details>

##### `updateBefore({ renderer }: any): void`

<details><summary>Code</summary>

```ts
updateBefore( { renderer } ) {

		if ( this.textureNeedsUpdate === false && this.autoUpdate === false ) return;

		this.textureNeedsUpdate = false;

		//

		if ( this.autoResize === true ) {

			const pixelRatio = renderer.getPixelRatio();
			const size = renderer.getSize( _size );

			const effectiveWidth = size.width * pixelRatio;
			const effectiveHeight = size.height * pixelRatio;

			if ( effectiveWidth !== this.renderTarget.width || effectiveHeight !== this.renderTarget.height ) {

				this.renderTarget.setSize( effectiveWidth, effectiveHeight );

				this.textureNeedsUpdate = true;

			}

		}

		//

		this._quadMesh.material.fragmentNode = this._rttNode;

		//

		const currentRenderTarget = renderer.getRenderTarget();

		renderer.setRenderTarget( this.renderTarget );

		this._quadMesh.render( renderer );

		renderer.setRenderTarget( currentRenderTarget );

	}
```
</details>

##### `clone(): TextureNode`

<details><summary>Code</summary>

```ts
clone() {

		const newNode = new TextureNode( this.value, this.uvNode, this.levelNode );
		newNode.sampler = this.sampler;
		newNode.referenceNode = this;

		return newNode;

	}
```
</details>


---