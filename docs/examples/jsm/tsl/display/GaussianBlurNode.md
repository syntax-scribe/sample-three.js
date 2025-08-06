[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `GaussianBlurNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 🧱 Classes | 1 |
| 📦 Imports | 18 |
| 📊 Variables & Constants | 14 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/GaussianBlurNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `RenderTarget` | `three/webgpu` |
| `Vector2` | `three/webgpu` |
| `NodeMaterial` | `three/webgpu` |
| `RendererUtils` | `three/webgpu` |
| `QuadMesh` | `three/webgpu` |
| `TempNode` | `three/webgpu` |
| `NodeUpdateType` | `three/webgpu` |
| `nodeObject` | `three/tsl` |
| `Fn` | `three/tsl` |
| `float` | `three/tsl` |
| `uv` | `three/tsl` |
| `uniform` | `three/tsl` |
| `convertToTexture` | `three/tsl` |
| `vec2` | `three/tsl` |
| `vec4` | `three/tsl` |
| `passTexture` | `three/tsl` |
| `premultiplyAlpha` | `three/tsl` |
| `unpremultiplyAlpha` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_quadMesh` | `any` | let/var | `new QuadMesh()` | ✗ |
| `_rendererState` | `any` | let/var | `*not shown*` | ✗ |
| `textureNode` | `TextureNode` | let/var | `this.textureNode` | ✗ |
| `map` | `any` | let/var | `textureNode.value` | ✗ |
| `currentTexture` | `any` | let/var | `textureNode.value` | ✗ |
| `textureType` | `any` | let/var | `map.type` | ✗ |
| `textureNode` | `TextureNode` | let/var | `this.textureNode` | ✗ |
| `sampleTexture` | `any` | let/var | `*not shown*` | ✗ |
| `output` | `any` | let/var | `*not shown*` | ✗ |
| `kernelSize` | `number` | let/var | `3 + ( 2 * this.sigma )` | ✗ |
| `invSize` | `UniformNode<vec2>` | let/var | `this._invSize` | ✗ |
| `material` | `any` | let/var | `this._material \|\| ( this._material = new NodeMaterial() )` | ✗ |
| `coefficients` | `any[]` | let/var | `[]` | ✗ |
| `sigma` | `number` | let/var | `kernelRadius / 3` | ✗ |


---

## Functions

### `GaussianBlurNode.setPremultipliedAlpha(value: boolean): GaussianBlurNode`

**JSDoc:**
```typescript
/**
	 * Sets the given premultiplied alpha value.
	 *
	 * @param {boolean} value - Whether the effect should use premultiplied alpha or not.
	 * @return {GaussianBlurNode} height - A reference to this node.
	 */
```

**Parameters:**

- **`value`** `boolean`

**Returns:** `GaussianBlurNode`

<details><summary>Code</summary>

```typescript
setPremultipliedAlpha( value ) {

		this.premultipliedAlpha = value;

		return this;

	}
```
</details>

### `GaussianBlurNode.getPremultipliedAlpha(): boolean`

**JSDoc:**
```typescript
/**
	 * Returns the premultiplied alpha value.
	 *
	 * @return {boolean} Whether the effect should use premultiplied alpha or not.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
getPremultipliedAlpha() {

		return this.premultipliedAlpha;

	}
```
</details>

### `GaussianBlurNode.setSize(width: number, height: number): void`

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

- `Math.max`
- `Math.round`
- `this._invSize.value.set`
- `this._horizontalRT.setSize`
- `this._verticalRT.setSize`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		width = Math.max( Math.round( width * this.resolution.x ), 1 );
		height = Math.max( Math.round( height * this.resolution.y ), 1 );

		this._invSize.value.set( 1 / width, 1 / height );
		this._horizontalRT.setSize( width, height );
		this._verticalRT.setSize( width, height );

	}
```
</details>

### `GaussianBlurNode.updateBefore(frame: NodeFrame): void`

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
- `this._passDirection.value.set`
- `_quadMesh.render`
- `RendererUtils.restoreRendererState`

**Internal Comments:**
```
// (x2)
// horizontal (x4)
// vertical (x4)
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

		const currentTexture = textureNode.value;

		_quadMesh.material = this._material;

		this.setSize( map.image.width, map.image.height );

		const textureType = map.type;

		this._horizontalRT.texture.type = textureType;
		this._verticalRT.texture.type = textureType;

		// horizontal

		renderer.setRenderTarget( this._horizontalRT );

		this._passDirection.value.set( 1, 0 );

		_quadMesh.render( renderer );

		// vertical

		textureNode.value = this._horizontalRT.texture;
		renderer.setRenderTarget( this._verticalRT );

		this._passDirection.value.set( 0, 1 );

		_quadMesh.render( renderer );

		// restore

		textureNode.value = currentTexture;

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

### `GaussianBlurNode.getTextureNode(): PassTextureNode`

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

### `GaussianBlurNode.setup(builder: NodeBuilder): PassTextureNode`

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
- `vec2 (from three/tsl)`
- `premultiplyAlpha (from three/tsl)`
- `textureNode.sample`
- `unpremultiplyAlpha (from three/tsl)`
- `Fn (from three/tsl)`
- `this._getCoefficients`
- `directionNode.mul`
- `vec4( sampleTexture( uvNode ).mul( gaussianCoefficients[ 0 ] ) ).toVar`
- `float (from three/tsl)`
- `vec2( direction.mul( invSize.mul( x ) ) ).toVar`
- `sampleTexture`
- `uvNode.add`
- `uvNode.sub`
- `diffuseSum.addAssign`
- `sample1.add( sample2 ).mul`
- `output`
- `blur().context`
- `builder.getSharedContext`
- `builder.getNodeProperties`

**Internal Comments:**
```
// (x7)
// https://lisyarus.github.io/blog/posts/blur-coefficients-generator.html (x3)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const textureNode = this.textureNode;

		//

		const uvNode = uv();
		const directionNode = vec2( this.directionNode || 1 );

		let sampleTexture, output;

		if ( this.premultipliedAlpha ) {

			// https://lisyarus.github.io/blog/posts/blur-coefficients-generator.html

			sampleTexture = ( uv ) => premultiplyAlpha( textureNode.sample( uv ) );
			output = ( color ) => unpremultiplyAlpha( color );

		} else {

			sampleTexture = ( uv ) => textureNode.sample( uv );
			output = ( color ) => color;

		}

		const blur = Fn( () => {

			const kernelSize = 3 + ( 2 * this.sigma );
			const gaussianCoefficients = this._getCoefficients( kernelSize );

			const invSize = this._invSize;
			const direction = directionNode.mul( this._passDirection );

			const diffuseSum = vec4( sampleTexture( uvNode ).mul( gaussianCoefficients[ 0 ] ) ).toVar();

			for ( let i = 1; i < kernelSize; i ++ ) {

				const x = float( i );
				const w = float( gaussianCoefficients[ i ] );

				const uvOffset = vec2( direction.mul( invSize.mul( x ) ) ).toVar();

				const sample1 = sampleTexture( uvNode.add( uvOffset ) );
				const sample2 = sampleTexture( uvNode.sub( uvOffset ) );

				diffuseSum.addAssign( sample1.add( sample2 ).mul( w ) );
			}

			return output( diffuseSum );

		} );

		//

		const material = this._material || ( this._material = new NodeMaterial() );
		material.fragmentNode = blur().context( builder.getSharedContext() );
		material.name = 'Gaussian_blur';
		material.needsUpdate = true;

		//

		const properties = builder.getNodeProperties( this );
		properties.textureNode = textureNode;

		//

		return this._textureNode;

	}
```
</details>

### `GaussianBlurNode.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources. This method should be called
	 * when the effect is no longer required.
	 */
```

**Returns:** `void`

**Calls:**

- `this._horizontalRT.dispose`
- `this._verticalRT.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this._horizontalRT.dispose();
		this._verticalRT.dispose();

	}
```
</details>

### `GaussianBlurNode._getCoefficients(kernelRadius: number): number[]`

**JSDoc:**
```typescript
/**
	 * Computes gaussian coefficients depending on the given kernel radius.
	 *
	 * @private
	 * @param {number} kernelRadius - The kernel radius.
	 * @return {Array<number>}
	 */
```

**Parameters:**

- **`kernelRadius`** `number`

**Returns:** `number[]`

**Calls:**

- `coefficients.push`
- `Math.exp`

<details><summary>Code</summary>

```typescript
_getCoefficients( kernelRadius ) {

		const coefficients = [];
		const sigma = kernelRadius / 3;

		for ( let i = 0; i < kernelRadius; i ++ ) {

			coefficients.push( 0.39894 * Math.exp( - 0.5 * i * i / ( sigma * sigma ) ) / sigma );

		}

		return coefficients;

	}
```
</details>

### `gaussianBlur(node: any, directionNode: any, sigma: number): GaussianBlurNode`

**Parameters:**

- **`node`** `any`
- **`directionNode`** `any`
- **`sigma`** `number`

**Returns:** `GaussianBlurNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( node, directionNode, sigma ) => nodeObject( new GaussianBlurNode( convertToTexture( node ), directionNode, sigma ) )
```
</details>

### `premultipliedGaussianBlur(node: any, directionNode: any, sigma: number): GaussianBlurNode`

**Parameters:**

- **`node`** `any`
- **`directionNode`** `any`
- **`sigma`** `number`

**Returns:** `GaussianBlurNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( node, directionNode, sigma ) => nodeObject( new GaussianBlurNode( convertToTexture( node ), directionNode, sigma ).setPremultipliedAlpha( true ) )
```
</details>


---

## Classes

### `GaussianBlurNode`

<details><summary>Class Code</summary>

```ts
class GaussianBlurNode extends TempNode {

	static get type() {

		return 'GaussianBlurNode';

	}

	/**
	 * Constructs a new gaussian blur node.
	 *
	 * @param {TextureNode} textureNode - The texture node that represents the input of the effect.
	 * @param {Node<vec2|float>} directionNode - Defines the direction and radius of the blur.
	 * @param {number} sigma - Controls the kernel of the blur filter. Higher values mean a wider blur radius.
	 */
	constructor( textureNode, directionNode = null, sigma = 4 ) {

		super( 'vec4' );

		/**
		 * The texture node that represents the input of the effect.
		 *
		 * @type {TextureNode}
		 */
		this.textureNode = textureNode;

		/**
		 * Defines the direction and radius of the blur.
		 *
		 * @type {Node<vec2|float>}
		 */
		this.directionNode = directionNode;

		/**
		 * Controls the kernel of the blur filter. Higher values mean a wider blur radius.
		 *
		 * @type {number}
		 */
		this.sigma = sigma;

		/**
		 * A uniform node holding the inverse resolution value.
		 *
		 * @private
		 * @type {UniformNode<vec2>}
		 */
		this._invSize = uniform( new Vector2() );

		/**
		 * Gaussian blur is applied in two passes (horizontal, vertical).
		 * This node controls the direction of each pass.
		 *
		 * @private
		 * @type {UniformNode<vec2>}
		 */
		this._passDirection = uniform( new Vector2() );

		/**
		 * The render target used for the horizontal pass.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._horizontalRT = new RenderTarget( 1, 1, { depthBuffer: false } );
		this._horizontalRT.texture.name = 'GaussianBlurNode.horizontal';

		/**
		 * The render target used for the vertical pass.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._verticalRT = new RenderTarget( 1, 1, { depthBuffer: false } );
		this._verticalRT.texture.name = 'GaussianBlurNode.vertical';

		/**
		 * The result of the effect is represented as a separate texture node.
		 *
		 * @private
		 * @type {PassTextureNode}
		 */
		this._textureNode = passTexture( this, this._verticalRT.texture );
		this._textureNode.uvNode = textureNode.uvNode;

		/**
		 * The `updateBeforeType` is set to `NodeUpdateType.FRAME` since the node renders
		 * its effect once per frame in `updateBefore()`.
		 *
		 * @type {string}
		 * @default 'frame'
		 */
		this.updateBeforeType = NodeUpdateType.FRAME;

		/**
		 * Controls the resolution of the effect.
		 *
		 * @type {Vector2}
		 * @default (1,1)
		 */
		this.resolution = new Vector2( 1, 1 );

		/**
		 * Whether the effect should use premultiplied alpha or not. Set this to `true`
		 * if you are going to blur texture input with transparency.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.premultipliedAlpha = false;

	}

	/**
	 * Sets the given premultiplied alpha value.
	 *
	 * @param {boolean} value - Whether the effect should use premultiplied alpha or not.
	 * @return {GaussianBlurNode} height - A reference to this node.
	 */
	setPremultipliedAlpha( value ) {

		this.premultipliedAlpha = value;

		return this;

	}

	/**
	 * Returns the premultiplied alpha value.
	 *
	 * @return {boolean} Whether the effect should use premultiplied alpha or not.
	 */
	getPremultipliedAlpha() {

		return this.premultipliedAlpha;

	}

	/**
	 * Sets the size of the effect.
	 *
	 * @param {number} width - The width of the effect.
	 * @param {number} height - The height of the effect.
	 */
	setSize( width, height ) {

		width = Math.max( Math.round( width * this.resolution.x ), 1 );
		height = Math.max( Math.round( height * this.resolution.y ), 1 );

		this._invSize.value.set( 1 / width, 1 / height );
		this._horizontalRT.setSize( width, height );
		this._verticalRT.setSize( width, height );

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

		const currentTexture = textureNode.value;

		_quadMesh.material = this._material;

		this.setSize( map.image.width, map.image.height );

		const textureType = map.type;

		this._horizontalRT.texture.type = textureType;
		this._verticalRT.texture.type = textureType;

		// horizontal

		renderer.setRenderTarget( this._horizontalRT );

		this._passDirection.value.set( 1, 0 );

		_quadMesh.render( renderer );

		// vertical

		textureNode.value = this._horizontalRT.texture;
		renderer.setRenderTarget( this._verticalRT );

		this._passDirection.value.set( 0, 1 );

		_quadMesh.render( renderer );

		// restore

		textureNode.value = currentTexture;

		RendererUtils.restoreRendererState( renderer, _rendererState );

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
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {PassTextureNode}
	 */
	setup( builder ) {

		const textureNode = this.textureNode;

		//

		const uvNode = uv();
		const directionNode = vec2( this.directionNode || 1 );

		let sampleTexture, output;

		if ( this.premultipliedAlpha ) {

			// https://lisyarus.github.io/blog/posts/blur-coefficients-generator.html

			sampleTexture = ( uv ) => premultiplyAlpha( textureNode.sample( uv ) );
			output = ( color ) => unpremultiplyAlpha( color );

		} else {

			sampleTexture = ( uv ) => textureNode.sample( uv );
			output = ( color ) => color;

		}

		const blur = Fn( () => {

			const kernelSize = 3 + ( 2 * this.sigma );
			const gaussianCoefficients = this._getCoefficients( kernelSize );

			const invSize = this._invSize;
			const direction = directionNode.mul( this._passDirection );

			const diffuseSum = vec4( sampleTexture( uvNode ).mul( gaussianCoefficients[ 0 ] ) ).toVar();

			for ( let i = 1; i < kernelSize; i ++ ) {

				const x = float( i );
				const w = float( gaussianCoefficients[ i ] );

				const uvOffset = vec2( direction.mul( invSize.mul( x ) ) ).toVar();

				const sample1 = sampleTexture( uvNode.add( uvOffset ) );
				const sample2 = sampleTexture( uvNode.sub( uvOffset ) );

				diffuseSum.addAssign( sample1.add( sample2 ).mul( w ) );
			}

			return output( diffuseSum );

		} );

		//

		const material = this._material || ( this._material = new NodeMaterial() );
		material.fragmentNode = blur().context( builder.getSharedContext() );
		material.name = 'Gaussian_blur';
		material.needsUpdate = true;

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

		this._horizontalRT.dispose();
		this._verticalRT.dispose();

	}

	/**
	 * Computes gaussian coefficients depending on the given kernel radius.
	 *
	 * @private
	 * @param {number} kernelRadius - The kernel radius.
	 * @return {Array<number>}
	 */
	_getCoefficients( kernelRadius ) {

		const coefficients = [];
		const sigma = kernelRadius / 3;

		for ( let i = 0; i < kernelRadius; i ++ ) {

			coefficients.push( 0.39894 * Math.exp( - 0.5 * i * i / ( sigma * sigma ) ) / sigma );

		}

		return coefficients;

	}

}
```
</details>

#### Methods

##### `setPremultipliedAlpha(value: boolean): GaussianBlurNode`

<details><summary>Code</summary>

```ts
setPremultipliedAlpha( value ) {

		this.premultipliedAlpha = value;

		return this;

	}
```
</details>

##### `getPremultipliedAlpha(): boolean`

<details><summary>Code</summary>

```ts
getPremultipliedAlpha() {

		return this.premultipliedAlpha;

	}
```
</details>

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		width = Math.max( Math.round( width * this.resolution.x ), 1 );
		height = Math.max( Math.round( height * this.resolution.y ), 1 );

		this._invSize.value.set( 1 / width, 1 / height );
		this._horizontalRT.setSize( width, height );
		this._verticalRT.setSize( width, height );

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

		const currentTexture = textureNode.value;

		_quadMesh.material = this._material;

		this.setSize( map.image.width, map.image.height );

		const textureType = map.type;

		this._horizontalRT.texture.type = textureType;
		this._verticalRT.texture.type = textureType;

		// horizontal

		renderer.setRenderTarget( this._horizontalRT );

		this._passDirection.value.set( 1, 0 );

		_quadMesh.render( renderer );

		// vertical

		textureNode.value = this._horizontalRT.texture;
		renderer.setRenderTarget( this._verticalRT );

		this._passDirection.value.set( 0, 1 );

		_quadMesh.render( renderer );

		// restore

		textureNode.value = currentTexture;

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

##### `getTextureNode(): PassTextureNode`

<details><summary>Code</summary>

```ts
getTextureNode() {

		return this._textureNode;

	}
```
</details>

##### `setup(builder: NodeBuilder): PassTextureNode`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const textureNode = this.textureNode;

		//

		const uvNode = uv();
		const directionNode = vec2( this.directionNode || 1 );

		let sampleTexture, output;

		if ( this.premultipliedAlpha ) {

			// https://lisyarus.github.io/blog/posts/blur-coefficients-generator.html

			sampleTexture = ( uv ) => premultiplyAlpha( textureNode.sample( uv ) );
			output = ( color ) => unpremultiplyAlpha( color );

		} else {

			sampleTexture = ( uv ) => textureNode.sample( uv );
			output = ( color ) => color;

		}

		const blur = Fn( () => {

			const kernelSize = 3 + ( 2 * this.sigma );
			const gaussianCoefficients = this._getCoefficients( kernelSize );

			const invSize = this._invSize;
			const direction = directionNode.mul( this._passDirection );

			const diffuseSum = vec4( sampleTexture( uvNode ).mul( gaussianCoefficients[ 0 ] ) ).toVar();

			for ( let i = 1; i < kernelSize; i ++ ) {

				const x = float( i );
				const w = float( gaussianCoefficients[ i ] );

				const uvOffset = vec2( direction.mul( invSize.mul( x ) ) ).toVar();

				const sample1 = sampleTexture( uvNode.add( uvOffset ) );
				const sample2 = sampleTexture( uvNode.sub( uvOffset ) );

				diffuseSum.addAssign( sample1.add( sample2 ).mul( w ) );
			}

			return output( diffuseSum );

		} );

		//

		const material = this._material || ( this._material = new NodeMaterial() );
		material.fragmentNode = blur().context( builder.getSharedContext() );
		material.name = 'Gaussian_blur';
		material.needsUpdate = true;

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

		this._horizontalRT.dispose();
		this._verticalRT.dispose();

	}
```
</details>

##### `_getCoefficients(kernelRadius: number): number[]`

<details><summary>Code</summary>

```ts
_getCoefficients( kernelRadius ) {

		const coefficients = [];
		const sigma = kernelRadius / 3;

		for ( let i = 0; i < kernelRadius; i ++ ) {

			coefficients.push( 0.39894 * Math.exp( - 0.5 * i * i / ( sigma * sigma ) ) / sigma );

		}

		return coefficients;

	}
```
</details>


---