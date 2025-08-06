[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `AnamorphicNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 19 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/AnamorphicNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `RenderTarget` | `three/webgpu` |
| `Vector2` | `three/webgpu` |
| `TempNode` | `three/webgpu` |
| `QuadMesh` | `three/webgpu` |
| `NodeMaterial` | `three/webgpu` |
| `RendererUtils` | `three/webgpu` |
| `nodeObject` | `three/tsl` |
| `Fn` | `three/tsl` |
| `float` | `three/tsl` |
| `NodeUpdateType` | `three/tsl` |
| `uv` | `three/tsl` |
| `passTexture` | `three/tsl` |
| `uniform` | `three/tsl` |
| `convertToTexture` | `three/tsl` |
| `vec2` | `three/tsl` |
| `vec3` | `three/tsl` |
| `Loop` | `three/tsl` |
| `mix` | `three/tsl` |
| `luminance` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_quadMesh` | `any` | let/var | `new QuadMesh()` | ✗ |
| `_rendererState` | `any` | let/var | `*not shown*` | ✗ |
| `textureNode` | `TextureNode` | let/var | `this.textureNode` | ✗ |
| `map` | `any` | let/var | `textureNode.value` | ✗ |
| `currentTexture` | `any` | let/var | `textureNode.value` | ✗ |
| `textureNode` | `TextureNode` | let/var | `this.textureNode` | ✗ |
| `uvNode` | `any` | let/var | `textureNode.uvNode \|\| uv()` | ✗ |
| `samples` | `any` | let/var | `this.samples` | ✗ |
| `material` | `any` | let/var | `this._material \|\| ( this._material = new NodeMaterial() )` | ✗ |


---

## Functions

### `AnamorphicNode.getTextureNode(): PassTextureNode`

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

### `AnamorphicNode.setSize(width: number, height: number): void`

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

- `this._invSize.value.set`
- `Math.max`
- `Math.round`
- `this._renderTarget.setSize`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this._invSize.value.set( 1 / width, 1 / height );

		width = Math.max( Math.round( width * this.resolution.x ), 1 );
		height = Math.max( Math.round( height * this.resolution.y ), 1 );

		this._renderTarget.setSize( width, height );

	}
```
</details>

### `AnamorphicNode.updateBefore(frame: NodeFrame): void`

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
- `this.setSize`
- `renderer.setRenderTarget`
- `_quadMesh.render`
- `RendererUtils.restoreRendererState`

**Internal Comments:**
```
// (x2)
// render (x4)
// restore (x4)
```

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		const { renderer } = frame;

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		const textureNode = this.textureNode;
		const map = textureNode.value;

		this._renderTarget.texture.type = map.type;

		const currentTexture = textureNode.value;

		_quadMesh.material = this._material;

		this.setSize( map.image.width, map.image.height );

		// render

		renderer.setRenderTarget( this._renderTarget );

		_quadMesh.render( renderer );

		// restore

		textureNode.value = currentTexture;

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

### `AnamorphicNode.setup(builder: NodeBuilder): PassTextureNode`

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
- `textureNode.sample`
- `mix (from three/tsl)`
- `vec3 (from three/tsl)`
- `luminance( color ).sub( threshold ).max`
- `Fn (from three/tsl)`
- `Math.floor`
- `vec3( 0 ).toVar`
- `Loop (from three/tsl)`
- `float( i ).abs().div( halfSamples ).oneMinus`
- `vec2 (from three/tsl)`
- `uvNode.x.add`
- `this._invSize.x.mul( i ).mul`
- `sampleTexture`
- `threshold( color, this.thresholdNode ).mul`
- `total.addAssign`
- `total.mul`
- `anamorph`
- `builder.getNodeProperties`

**Internal Comments:**
```
// (x5)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const textureNode = this.textureNode;
		const uvNode = textureNode.uvNode || uv();

		const sampleTexture = ( uv ) => textureNode.sample( uv );

		const threshold = ( color, threshold ) => mix( vec3( 0.0 ), color, luminance( color ).sub( threshold ).max( 0 ) );

		const anamorph = Fn( () => {

			const samples = this.samples;
			const halfSamples = Math.floor( samples / 2 );

			const total = vec3( 0 ).toVar();

			Loop( { start: - halfSamples, end: halfSamples }, ( { i } ) => {

				const softness = float( i ).abs().div( halfSamples ).oneMinus();

				const uv = vec2( uvNode.x.add( this._invSize.x.mul( i ).mul( this.scaleNode ) ), uvNode.y );
				const color = sampleTexture( uv );
				const pass = threshold( color, this.thresholdNode ).mul( softness );

				total.addAssign( pass );

			} );

			return total.mul( this.colorNode );

		} );

		//

		const material = this._material || ( this._material = new NodeMaterial() );
		material.name = 'Anamorphic';
		material.fragmentNode = anamorph();

		//

		const properties = builder.getNodeProperties( this );
		properties.textureNode = textureNode;

		//

		return this._textureNode;

	}
```
</details>

### `AnamorphicNode.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources. This method should be called
	 * when the effect is no longer required.
	 */
```

**Returns:** `void`

**Calls:**

- `this._renderTarget.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this._renderTarget.dispose();

	}
```
</details>

### `sampleTexture(uv: any): any`

**Parameters:**

- **`uv`** `any`

**Returns:** `any`

**Calls:**

- `textureNode.sample`

<details><summary>Code</summary>

```typescript
( uv ) => textureNode.sample( uv )
```
</details>

### `threshold(color: any, threshold: any): any`

**Parameters:**

- **`color`** `any`
- **`threshold`** `any`

**Returns:** `any`

**Calls:**

- `mix (from three/tsl)`

<details><summary>Code</summary>

```typescript
( color, threshold ) => mix( vec3( 0.0 ), color, luminance( color ).sub( threshold ).max( 0 ) )
```
</details>

### `anamorphic(node: TextureNode, threshold: any, scale: any, samples: number): AnamorphicNode`

**Parameters:**

- **`node`** `TextureNode`
- **`threshold`** `any`
- **`scale`** `any`
- **`samples`** `number`

**Returns:** `AnamorphicNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( node, threshold = .9, scale = 3, samples = 32 ) => nodeObject( new AnamorphicNode( convertToTexture( node ), nodeObject( threshold ), nodeObject( scale ), samples ) )
```
</details>


---

## Classes

### `AnamorphicNode`

<details><summary>Class Code</summary>

```ts
class AnamorphicNode extends TempNode {

	static get type() {

		return 'AnamorphicNode';

	}

	/**
	 * Constructs a new anamorphic node.
	 *
	 * @param {TextureNode} textureNode - The texture node that represents the input of the effect.
	 * @param {Node<float>} thresholdNode - The threshold is one option to control the intensity and size of the effect.
	 * @param {Node<float>} scaleNode - Defines the vertical scale of the flares.
	 * @param {number} samples - More samples result in larger flares and a more expensive runtime behavior.
	 */
	constructor( textureNode, thresholdNode, scaleNode, samples ) {

		super( 'vec4' );

		/**
		 * The texture node that represents the input of the effect.
		 *
		 * @type {TextureNode}
		 */
		this.textureNode = textureNode;

		/**
		 * The threshold is one option to control the intensity and size of the effect.
		 *
		 * @type {Node<float>}
		 */
		this.thresholdNode = thresholdNode;

		/**
		 * Defines the vertical scale of the flares.
		 *
		 * @type {Node<float>}
		 */
		this.scaleNode = scaleNode;

		/**
		 * The color of the flares.
		 *
		 * @type {Node<vec3>}
		 */
		this.colorNode = vec3( 0.1, 0.0, 1.0 );

		/**
		 * More samples result in larger flares and a more expensive runtime behavior.
		 *
		 * @type {Node<float>}
		 */
		this.samples = samples;

		/**
		 * The resolution scale.
		 *
		 * @type {Vector2}
		 */
		this.resolution = new Vector2( 1, 1 );

		/**
		 * The internal render target of the effect.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._renderTarget = new RenderTarget( 1, 1, { depthBuffer: false } );
		this._renderTarget.texture.name = 'anamorphic';

		/**
		 * A uniform node holding the inverse resolution value.
		 *
		 * @private
		 * @type {UniformNode<vec2>}
		 */
		this._invSize = uniform( new Vector2() );

		/**
		 * The result of the effect is represented as a separate texture node.
		 *
		 * @private
		 * @type {PassTextureNode}
		 */
		this._textureNode = passTexture( this, this._renderTarget.texture );

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

		this._invSize.value.set( 1 / width, 1 / height );

		width = Math.max( Math.round( width * this.resolution.x ), 1 );
		height = Math.max( Math.round( height * this.resolution.y ), 1 );

		this._renderTarget.setSize( width, height );

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

		this._renderTarget.texture.type = map.type;

		const currentTexture = textureNode.value;

		_quadMesh.material = this._material;

		this.setSize( map.image.width, map.image.height );

		// render

		renderer.setRenderTarget( this._renderTarget );

		_quadMesh.render( renderer );

		// restore

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
		const uvNode = textureNode.uvNode || uv();

		const sampleTexture = ( uv ) => textureNode.sample( uv );

		const threshold = ( color, threshold ) => mix( vec3( 0.0 ), color, luminance( color ).sub( threshold ).max( 0 ) );

		const anamorph = Fn( () => {

			const samples = this.samples;
			const halfSamples = Math.floor( samples / 2 );

			const total = vec3( 0 ).toVar();

			Loop( { start: - halfSamples, end: halfSamples }, ( { i } ) => {

				const softness = float( i ).abs().div( halfSamples ).oneMinus();

				const uv = vec2( uvNode.x.add( this._invSize.x.mul( i ).mul( this.scaleNode ) ), uvNode.y );
				const color = sampleTexture( uv );
				const pass = threshold( color, this.thresholdNode ).mul( softness );

				total.addAssign( pass );

			} );

			return total.mul( this.colorNode );

		} );

		//

		const material = this._material || ( this._material = new NodeMaterial() );
		material.name = 'Anamorphic';
		material.fragmentNode = anamorph();

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

		this._renderTarget.dispose();

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

		this._invSize.value.set( 1 / width, 1 / height );

		width = Math.max( Math.round( width * this.resolution.x ), 1 );
		height = Math.max( Math.round( height * this.resolution.y ), 1 );

		this._renderTarget.setSize( width, height );

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

		this._renderTarget.texture.type = map.type;

		const currentTexture = textureNode.value;

		_quadMesh.material = this._material;

		this.setSize( map.image.width, map.image.height );

		// render

		renderer.setRenderTarget( this._renderTarget );

		_quadMesh.render( renderer );

		// restore

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
		const uvNode = textureNode.uvNode || uv();

		const sampleTexture = ( uv ) => textureNode.sample( uv );

		const threshold = ( color, threshold ) => mix( vec3( 0.0 ), color, luminance( color ).sub( threshold ).max( 0 ) );

		const anamorph = Fn( () => {

			const samples = this.samples;
			const halfSamples = Math.floor( samples / 2 );

			const total = vec3( 0 ).toVar();

			Loop( { start: - halfSamples, end: halfSamples }, ( { i } ) => {

				const softness = float( i ).abs().div( halfSamples ).oneMinus();

				const uv = vec2( uvNode.x.add( this._invSize.x.mul( i ).mul( this.scaleNode ) ), uvNode.y );
				const color = sampleTexture( uv );
				const pass = threshold( color, this.thresholdNode ).mul( softness );

				total.addAssign( pass );

			} );

			return total.mul( this.colorNode );

		} );

		//

		const material = this._material || ( this._material = new NodeMaterial() );
		material.name = 'Anamorphic';
		material.fragmentNode = anamorph();

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

		this._renderTarget.dispose();

	}
```
</details>


---