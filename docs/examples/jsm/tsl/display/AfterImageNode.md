[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `AfterImageNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 17 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/AfterImageNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `RenderTarget` | `three/webgpu` |
| `Vector2` | `three/webgpu` |
| `QuadMesh` | `three/webgpu` |
| `NodeMaterial` | `three/webgpu` |
| `RendererUtils` | `three/webgpu` |
| `TempNode` | `three/webgpu` |
| `NodeUpdateType` | `three/webgpu` |
| `nodeObject` | `three/tsl` |
| `Fn` | `three/tsl` |
| `float` | `three/tsl` |
| `uv` | `three/tsl` |
| `texture` | `three/tsl` |
| `passTexture` | `three/tsl` |
| `uniform` | `three/tsl` |
| `sign` | `three/tsl` |
| `max` | `three/tsl` |
| `convertToTexture` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_size` | `any` | let/var | `new Vector2()` | ✗ |
| `_quadMeshComp` | `any` | let/var | `new QuadMesh()` | ✗ |
| `_rendererState` | `any` | let/var | `*not shown*` | ✗ |
| `textureNode` | `TextureNode` | let/var | `this.textureNode` | ✗ |
| `map` | `any` | let/var | `textureNode.value` | ✗ |
| `textureType` | `any` | let/var | `map.type` | ✗ |
| `currentTexture` | `any` | let/var | `textureNode.value` | ✗ |
| `temp` | `RenderTarget` | let/var | `this._oldRT` | ✗ |
| `textureNode` | `TextureNode` | let/var | `this.textureNode` | ✗ |
| `textureNodeOld` | `TextureNode` | let/var | `this.textureNodeOld` | ✗ |
| `materialComposed` | `any` | let/var | `this._materialComposed \|\| ( this._materialComposed = new NodeMaterial() )` | ✗ |


---

## Functions

### `AfterImageNode.getTextureNode(): PassTextureNode`

**JSDoc:**
```typescript
/**
	 * Returns the result of the effect as a texture node.
	 *
	 * @return {PassTextureNode} A texture node that represents the result of the effect.
	 */
```

**Returns:** `PassTextureNode`

<details><summary>Code</summary>

```typescript
getTextureNode() {

		return this._textureNode;

	}
```
</details>

### `AfterImageNode.setSize(width: number, height: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the size of the effect.
	 *
	 * @param {number} width - The width of the effect.
	 * @param {number} height - The height of the effect.
	 */
```

**Parameters:**

- **`width`** `number`
- **`height`** `number`

**Returns:** `void`

**Calls:**

- `this._compRT.setSize`
- `this._oldRT.setSize`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this._compRT.setSize( width, height );
		this._oldRT.setSize( width, height );

	}
```
</details>

### `AfterImageNode.updateBefore(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
	 * This method is used to render the effect once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
```

**Parameters:**

- **`frame`** `NodeFrame`

**Returns:** `void`

**Calls:**

- `RendererUtils.resetRendererState`
- `renderer.getDrawingBufferSize`
- `this.setSize`
- `renderer.setRenderTarget`
- `_quadMeshComp.render`
- `RendererUtils.restoreRendererState`

**Internal Comments:**
```
// (x6)
// comp (x4)
// Swap the textures (x2)
```

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		const { renderer } = frame;

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		const textureNode = this.textureNode;
		const map = textureNode.value;

		const textureType = map.type;

		this._compRT.texture.type = textureType;
		this._oldRT.texture.type = textureType;

		renderer.getDrawingBufferSize( _size );

		this.setSize( _size.x, _size.y );

		const currentTexture = textureNode.value;

		this.textureNodeOld.value = this._oldRT.texture;

		// comp
		_quadMeshComp.material = this._materialComposed;

		renderer.setRenderTarget( this._compRT );
		_quadMeshComp.render( renderer );

		// Swap the textures

		const temp = this._oldRT;
		this._oldRT = this._compRT;
		this._compRT = temp;

		//

		textureNode.value = currentTexture;

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

### `AfterImageNode.setup(builder: NodeBuilder): PassTextureNode`

**JSDoc:**
```typescript
/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {PassTextureNode}
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `PassTextureNode`

**Calls:**

- `uv (from three/tsl)`
- `Fn (from three/tsl)`
- `textureNodeOld.sample().toVar`
- `textureNode.sample().toVar`
- `float( 0.1 ).toConst`
- `max (from three/tsl)`
- `sign (from three/tsl)`
- `texelOld.sub`
- `texelOld.mulAssign`
- `this.damp.mul`
- `afterImg`
- `builder.getNodeProperties`

**Internal Comments:**
```
// (x13)
// m acts as a mask. It's 1 if the previous pixel was "bright enough" (above the threshold) and 0 if it wasn't. (x2)
// This is where the after-image fades: (x4)
// - If m is 0, texelOld is multiplied by 0, effectively clearing the after-image for that pixel. (x4)
// - If m is 1, texelOld is multiplied by "damp". Since "damp" is between 0 and 1, this reduces the color value of (x4)
// texelOld, making it darker and causing it to fade. (x4)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const textureNode = this.textureNode;
		const textureNodeOld = this.textureNodeOld;

		//

		textureNodeOld.uvNode = textureNode.uvNode || uv();

		const afterImg = Fn( () => {

			const texelOld = textureNodeOld.sample().toVar();
			const texelNew = textureNode.sample().toVar();

			const threshold = float( 0.1 ).toConst();

			// m acts as a mask. It's 1 if the previous pixel was "bright enough" (above the threshold) and 0 if it wasn't.
			const m = max( sign( texelOld.sub( threshold ) ), 0.0 );

			// This is where the after-image fades:
			//
			// - If m is 0, texelOld is multiplied by 0, effectively clearing the after-image for that pixel.
			// - If m is 1, texelOld is multiplied by "damp". Since "damp" is between 0 and 1, this reduces the color value of
			// texelOld, making it darker and causing it to fade.
			texelOld.mulAssign( this.damp.mul( m ) );

			return max( texelNew, texelOld );

		} );

		//

		const materialComposed = this._materialComposed || ( this._materialComposed = new NodeMaterial() );
		materialComposed.name = 'AfterImage';
		materialComposed.fragmentNode = afterImg();
		//

		const properties = builder.getNodeProperties( this );
		properties.textureNode = textureNode;

		//

		return this._textureNode;

	}
```
</details>

### `AfterImageNode.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources. This method should be called
	 * when the effect is no longer required.
	 */
```

**Returns:** `void`

**Calls:**

- `this._compRT.dispose`
- `this._oldRT.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this._compRT.dispose();
		this._oldRT.dispose();

	}
```
</details>

### `afterImage(node: any, damp: number): AfterImageNode`

**Parameters:**

- **`node`** `any`
- **`damp`** `number`

**Returns:** `AfterImageNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( node, damp ) => nodeObject( new AfterImageNode( convertToTexture( node ), damp ) )
```
</details>


---

## Classes

### `AfterImageNode`

<details><summary>Class Code</summary>

```ts
class AfterImageNode extends TempNode {

	static get type() {

		return 'AfterImageNode';

	}

	/**
	 * Constructs a new after image node.
	 *
	 * @param {TextureNode} textureNode - The texture node that represents the input of the effect.
	 * @param {number} [damp=0.96] - The damping intensity. A higher value means a stronger after image effect.
	 */
	constructor( textureNode, damp = 0.96 ) {

		super( 'vec4' );

		/**
		 * The texture node that represents the input of the effect.
		 *
		 * @type {TextureNode}
		 */
		this.textureNode = textureNode;

		/**
		 * The texture represents the pervious frame.
		 *
		 * @type {TextureNode}
		 */
		this.textureNodeOld = texture( null );

		/**
		 * How quickly the after-image fades. A higher value means the after-image
		 * persists longer, while a lower value means it fades faster. Should be in
		 * the range `[0, 1]`.
		 *
		 * @type {UniformNode<float>}
		 */
		this.damp = uniform( damp );

		/**
		 * The render target used for compositing the effect.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._compRT = new RenderTarget( 1, 1, { depthBuffer: false } );
		this._compRT.texture.name = 'AfterImageNode.comp';

		/**
		 * The render target that represents the previous frame.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._oldRT = new RenderTarget( 1, 1, { depthBuffer: false } );
		this._oldRT.texture.name = 'AfterImageNode.old';

		/**
		 * The result of the effect is represented as a separate texture node.
		 *
		 * @private
		 * @type {PassTextureNode}
		 */
		this._textureNode = passTexture( this, this._compRT.texture );

		/**
		 * The `updateBeforeType` is set to `NodeUpdateType.FRAME` since the node renders
		 * its effect once per frame in `updateBefore()`.
		 *
		 * @type {string}
		 * @default 'frame'
		 */
		this.updateBeforeType = NodeUpdateType.FRAME;

	}

	/**
	 * Returns the result of the effect as a texture node.
	 *
	 * @return {PassTextureNode} A texture node that represents the result of the effect.
	 */
	getTextureNode() {

		return this._textureNode;

	}

	/**
	 * Sets the size of the effect.
	 *
	 * @param {number} width - The width of the effect.
	 * @param {number} height - The height of the effect.
	 */
	setSize( width, height ) {

		this._compRT.setSize( width, height );
		this._oldRT.setSize( width, height );

	}

	/**
	 * This method is used to render the effect once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
	updateBefore( frame ) {

		const { renderer } = frame;

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		const textureNode = this.textureNode;
		const map = textureNode.value;

		const textureType = map.type;

		this._compRT.texture.type = textureType;
		this._oldRT.texture.type = textureType;

		renderer.getDrawingBufferSize( _size );

		this.setSize( _size.x, _size.y );

		const currentTexture = textureNode.value;

		this.textureNodeOld.value = this._oldRT.texture;

		// comp
		_quadMeshComp.material = this._materialComposed;

		renderer.setRenderTarget( this._compRT );
		_quadMeshComp.render( renderer );

		// Swap the textures

		const temp = this._oldRT;
		this._oldRT = this._compRT;
		this._compRT = temp;

		//

		textureNode.value = currentTexture;

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}

	/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {PassTextureNode}
	 */
	setup( builder ) {

		const textureNode = this.textureNode;
		const textureNodeOld = this.textureNodeOld;

		//

		textureNodeOld.uvNode = textureNode.uvNode || uv();

		const afterImg = Fn( () => {

			const texelOld = textureNodeOld.sample().toVar();
			const texelNew = textureNode.sample().toVar();

			const threshold = float( 0.1 ).toConst();

			// m acts as a mask. It's 1 if the previous pixel was "bright enough" (above the threshold) and 0 if it wasn't.
			const m = max( sign( texelOld.sub( threshold ) ), 0.0 );

			// This is where the after-image fades:
			//
			// - If m is 0, texelOld is multiplied by 0, effectively clearing the after-image for that pixel.
			// - If m is 1, texelOld is multiplied by "damp". Since "damp" is between 0 and 1, this reduces the color value of
			// texelOld, making it darker and causing it to fade.
			texelOld.mulAssign( this.damp.mul( m ) );

			return max( texelNew, texelOld );

		} );

		//

		const materialComposed = this._materialComposed || ( this._materialComposed = new NodeMaterial() );
		materialComposed.name = 'AfterImage';
		materialComposed.fragmentNode = afterImg();
		//

		const properties = builder.getNodeProperties( this );
		properties.textureNode = textureNode;

		//

		return this._textureNode;

	}

	/**
	 * Frees internal resources. This method should be called
	 * when the effect is no longer required.
	 */
	dispose() {

		this._compRT.dispose();
		this._oldRT.dispose();

	}

}
```
</details>

#### Methods

##### `getTextureNode(): PassTextureNode`

<details><summary>Code</summary>

```ts
getTextureNode() {

		return this._textureNode;

	}
```
</details>

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		this._compRT.setSize( width, height );
		this._oldRT.setSize( width, height );

	}
```
</details>

##### `updateBefore(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		const { renderer } = frame;

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		const textureNode = this.textureNode;
		const map = textureNode.value;

		const textureType = map.type;

		this._compRT.texture.type = textureType;
		this._oldRT.texture.type = textureType;

		renderer.getDrawingBufferSize( _size );

		this.setSize( _size.x, _size.y );

		const currentTexture = textureNode.value;

		this.textureNodeOld.value = this._oldRT.texture;

		// comp
		_quadMeshComp.material = this._materialComposed;

		renderer.setRenderTarget( this._compRT );
		_quadMeshComp.render( renderer );

		// Swap the textures

		const temp = this._oldRT;
		this._oldRT = this._compRT;
		this._compRT = temp;

		//

		textureNode.value = currentTexture;

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

##### `setup(builder: NodeBuilder): PassTextureNode`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const textureNode = this.textureNode;
		const textureNodeOld = this.textureNodeOld;

		//

		textureNodeOld.uvNode = textureNode.uvNode || uv();

		const afterImg = Fn( () => {

			const texelOld = textureNodeOld.sample().toVar();
			const texelNew = textureNode.sample().toVar();

			const threshold = float( 0.1 ).toConst();

			// m acts as a mask. It's 1 if the previous pixel was "bright enough" (above the threshold) and 0 if it wasn't.
			const m = max( sign( texelOld.sub( threshold ) ), 0.0 );

			// This is where the after-image fades:
			//
			// - If m is 0, texelOld is multiplied by 0, effectively clearing the after-image for that pixel.
			// - If m is 1, texelOld is multiplied by "damp". Since "damp" is between 0 and 1, this reduces the color value of
			// texelOld, making it darker and causing it to fade.
			texelOld.mulAssign( this.damp.mul( m ) );

			return max( texelNew, texelOld );

		} );

		//

		const materialComposed = this._materialComposed || ( this._materialComposed = new NodeMaterial() );
		materialComposed.name = 'AfterImage';
		materialComposed.fragmentNode = afterImg();
		//

		const properties = builder.getNodeProperties( this );
		properties.textureNode = textureNode;

		//

		return this._textureNode;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this._compRT.dispose();
		this._oldRT.dispose();

	}
```
</details>


---