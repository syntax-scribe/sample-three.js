[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `LensflareNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 23 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/LensflareNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `RenderTarget` | `three/webgpu` |
| `Vector2` | `three/webgpu` |
| `TempNode` | `three/webgpu` |
| `NodeUpdateType` | `three/webgpu` |
| `QuadMesh` | `three/webgpu` |
| `RendererUtils` | `three/webgpu` |
| `NodeMaterial` | `three/webgpu` |
| `convertToTexture` | `three/tsl` |
| `nodeObject` | `three/tsl` |
| `Fn` | `three/tsl` |
| `passTexture` | `three/tsl` |
| `uv` | `three/tsl` |
| `vec2` | `three/tsl` |
| `vec3` | `three/tsl` |
| `vec4` | `three/tsl` |
| `max` | `three/tsl` |
| `float` | `three/tsl` |
| `sub` | `three/tsl` |
| `int` | `three/tsl` |
| `Loop` | `three/tsl` |
| `fract` | `three/tsl` |
| `pow` | `three/tsl` |
| `distance` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_quadMesh` | `any` | let/var | `new QuadMesh()` | ✗ |
| `_size` | `any` | let/var | `new Vector2()` | ✗ |
| `_rendererState` | `any` | let/var | `*not shown*` | ✗ |
| `sample` | `any` | let/var | `this.textureNode.sample( sampleUv ).rgb` | ✗ |


---

## Functions

### `LensflareNode.getTextureNode(): PassTextureNode`

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

### `LensflareNode.setSize(width: number, height: number): void`

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

- `Math.round`
- `this._renderTarget.setSize`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		const resx = Math.round( width / this.downSampleRatio );
		const resy = Math.round( height / this.downSampleRatio );

		this._renderTarget.setSize( resx, resy );

	}
```
</details>

### `LensflareNode.updateBefore(frame: NodeFrame): void`

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

- `renderer.getDrawingBufferSize`
- `this.setSize`
- `RendererUtils.resetRendererState`
- `renderer.setMRT`
- `renderer.setRenderTarget`
- `_quadMesh.render`
- `RendererUtils.restoreRendererState`

**Internal Comments:**
```
// clear (x4)
// lensflare (x4)
// restore (x4)
```

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		const { renderer } = frame;

		const size = renderer.getDrawingBufferSize( _size );
		this.setSize( size.width, size.height );

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		_quadMesh.material = this._material;

		// clear

		renderer.setMRT( null );

		// lensflare

		renderer.setRenderTarget( this._renderTarget );
		_quadMesh.render( renderer );

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

### `LensflareNode.setup(builder: NodeBuilder): PassTextureNode`

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

- `Fn (from three/tsl)`
- `uv().oneMinus().toVar`
- `sub( vec2( 0.5 ), texCoord ).mul( this.ghostSpacingNode ).toVar`
- `vec4().toVar`
- `Loop (from three/tsl)`
- `int (from three/tsl)`
- `fract( texCoord.add( ghostVec.mul( float( i ) ) ) ).toVar`
- `distance (from three/tsl)`
- `vec2 (from three/tsl)`
- `pow (from three/tsl)`
- `d.oneMinus`
- `this.textureNode.sample`
- `max( sample.sub( this.thresholdNode ), vec3( 0 ) ).mul`
- `result.addAssign`
- `sample.mul`
- `lensflare().context`
- `builder.getSharedContext`

**Internal Comments:**
```
// flip uvs so lens flare pivot around the image center (x2)
// ghosts are positioned along this vector (x2)
// sample ghosts (x2)
// use fract() to ensure that the texture coordinates wrap around (x2)
// reduce contributions from samples at the screen edge (x2)
// accumulate (x2)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const lensflare = Fn( () => {

			// flip uvs so lens flare pivot around the image center

			const texCoord = uv().oneMinus().toVar();

			// ghosts are positioned along this vector

			const ghostVec = sub( vec2( 0.5 ), texCoord ).mul( this.ghostSpacingNode ).toVar();

			// sample ghosts

			const result = vec4().toVar();

			Loop( { start: int( 0 ), end: int( this.ghostSamplesNode ), type: 'int', condition: '<' }, ( { i } ) => {

				// use fract() to ensure that the texture coordinates wrap around

				const sampleUv = fract( texCoord.add( ghostVec.mul( float( i ) ) ) ).toVar();

				// reduce contributions from samples at the screen edge

				const d = distance( sampleUv, vec2( 0.5 ) );
				const weight = pow( d.oneMinus(), this.ghostAttenuationFactorNode );

				// accumulate

				let sample = this.textureNode.sample( sampleUv ).rgb;

				sample = max( sample.sub( this.thresholdNode ), vec3( 0 ) ).mul( this.ghostTintNode );

				result.addAssign( sample.mul( weight ) );

			} );

			return result;

		} );

		this._material.fragmentNode = lensflare().context( builder.getSharedContext() );
		this._material.needsUpdate = true;

		return this._textureNode;

	}
```
</details>

### `LensflareNode.dispose(): void`

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
- `this._material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this._renderTarget.dispose();
		this._material.dispose();

	}
```
</details>

### `lensflare(node: TextureNode, params: { ghostTint?: any; threshold?: any; ghostSamples?: any; ghostSpacing?: any; ghostAttenuationFactor?: any; downSampleRatio?: number; }): LensflareNode`

**Parameters:**

- **`node`** `TextureNode`
- **`params`** `{ ghostTint?: any; threshold?: any; ghostSamples?: any; ghostSpacing?: any; ghostAttenuationFactor?: any; downSampleRatio?: number; }`

**Returns:** `LensflareNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( node, params ) => nodeObject( new LensflareNode( convertToTexture( node ), params ) )
```
</details>


---

## Classes

### `LensflareNode`

<details><summary>Class Code</summary>

```ts
class LensflareNode extends TempNode {

	static get type() {

		return 'LensflareNode';

	}

	/**
	 * Constructs a new lens flare node.
	 *
	 * @param {TextureNode} textureNode - The texture node that represents the scene's bloom.
	 * @param {Object} params - The parameter object for configuring the effect.
	 * @param {Node<vec3> | Color} [params.ghostTint=vec3(1, 1, 1)] - Defines the tint of the flare/ghosts.
	 * @param {Node<float> | number} [params.threshold=float(0.5)] - Controls the size and strength of the effect. A higher threshold results in smaller flares.
	 * @param {Node<float> | number} [params.ghostSamples=float(4)] - Represents the number of flares/ghosts per bright spot which pivot around the center.
	 * @param {Node<float> | number} [params.ghostSpacing=float(0.25)] - Defines the spacing of the flares/ghosts.
	 * @param {Node<float> | number} [params.ghostAttenuationFactor=float(25)] - Defines the attenuation factor of flares/ghosts.
	 * @param {number} [params.downSampleRatio=4] - Defines how downsampling since the effect is usually not rendered at full resolution.
	 */
	constructor( textureNode, params = {} ) {

		super( 'vec4' );

		/**
		 * The texture node that represents the scene's bloom.
		 *
		 * @type {TextureNode}
		 */
		this.textureNode = textureNode;

		const {
			ghostTint = vec3( 1, 1, 1 ),
			threshold = float( 0.5 ),
			ghostSamples = float( 4 ),
			ghostSpacing = float( 0.25 ),
			ghostAttenuationFactor = float( 25 ),
			downSampleRatio = 4
		} = params;

		/**
		 * Defines the tint of the flare/ghosts.
		 *
		 * @type {Node<vec3>}
		 */
		this.ghostTintNode = nodeObject( ghostTint );

		/**
		 * Controls the size and strength of the effect. A higher threshold results in smaller flares.
		 *
		 * @type {Node<float>}
		 */
		this.thresholdNode = nodeObject( threshold );

		/**
		 * Represents the number of flares/ghosts per bright spot which pivot around the center.
		 *
		 * @type {Node<float>}
		 */
		this.ghostSamplesNode = nodeObject( ghostSamples );

		/**
		 * Defines the spacing of the flares/ghosts.
		 *
		 * @type {Node<float>}
		 */
		this.ghostSpacingNode = nodeObject( ghostSpacing );

		/**
		 * Defines the attenuation factor of flares/ghosts.
		 *
		 * @type {Node<float>}
		 */
		this.ghostAttenuationFactorNode = nodeObject( ghostAttenuationFactor );

		/**
		 * Defines how downsampling since the effect is usually not rendered at full resolution.
		 *
		 * @type {number}
		 */
		this.downSampleRatio = downSampleRatio;

		/**
		 * The `updateBeforeType` is set to `NodeUpdateType.FRAME` since the node renders
		 * its effect once per frame in `updateBefore()`.
		 *
		 * @type {string}
		 * @default 'frame'
		 */
		this.updateBeforeType = NodeUpdateType.FRAME;

		/**
		 * The internal render target of the effect.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._renderTarget = new RenderTarget( 1, 1, { depthBuffer: false } );
		this._renderTarget.texture.name = 'LensflareNode';

		/**
		 * The node material that holds the effect's TSL code.
		 *
		 * @private
		 * @type {NodeMaterial}
		 */
		this._material = new NodeMaterial();
		this._material.name = 'LensflareNode';

		/**
		 * The result of the effect is represented as a separate texture node.
		 *
		 * @private
		 * @type {PassTextureNode}
		 */
		this._textureNode = passTexture( this, this._renderTarget.texture );

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

		const resx = Math.round( width / this.downSampleRatio );
		const resy = Math.round( height / this.downSampleRatio );

		this._renderTarget.setSize( resx, resy );

	}

	/**
	 * This method is used to render the effect once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
	updateBefore( frame ) {

		const { renderer } = frame;

		const size = renderer.getDrawingBufferSize( _size );
		this.setSize( size.width, size.height );

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		_quadMesh.material = this._material;

		// clear

		renderer.setMRT( null );

		// lensflare

		renderer.setRenderTarget( this._renderTarget );
		_quadMesh.render( renderer );

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}

	/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {PassTextureNode}
	 */
	setup( builder ) {

		const lensflare = Fn( () => {

			// flip uvs so lens flare pivot around the image center

			const texCoord = uv().oneMinus().toVar();

			// ghosts are positioned along this vector

			const ghostVec = sub( vec2( 0.5 ), texCoord ).mul( this.ghostSpacingNode ).toVar();

			// sample ghosts

			const result = vec4().toVar();

			Loop( { start: int( 0 ), end: int( this.ghostSamplesNode ), type: 'int', condition: '<' }, ( { i } ) => {

				// use fract() to ensure that the texture coordinates wrap around

				const sampleUv = fract( texCoord.add( ghostVec.mul( float( i ) ) ) ).toVar();

				// reduce contributions from samples at the screen edge

				const d = distance( sampleUv, vec2( 0.5 ) );
				const weight = pow( d.oneMinus(), this.ghostAttenuationFactorNode );

				// accumulate

				let sample = this.textureNode.sample( sampleUv ).rgb;

				sample = max( sample.sub( this.thresholdNode ), vec3( 0 ) ).mul( this.ghostTintNode );

				result.addAssign( sample.mul( weight ) );

			} );

			return result;

		} );

		this._material.fragmentNode = lensflare().context( builder.getSharedContext() );
		this._material.needsUpdate = true;

		return this._textureNode;

	}

	/**
	 * Frees internal resources. This method should be called
	 * when the effect is no longer required.
	 */
	dispose() {

		this._renderTarget.dispose();
		this._material.dispose();

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

		const resx = Math.round( width / this.downSampleRatio );
		const resy = Math.round( height / this.downSampleRatio );

		this._renderTarget.setSize( resx, resy );

	}
```
</details>

##### `updateBefore(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		const { renderer } = frame;

		const size = renderer.getDrawingBufferSize( _size );
		this.setSize( size.width, size.height );

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		_quadMesh.material = this._material;

		// clear

		renderer.setMRT( null );

		// lensflare

		renderer.setRenderTarget( this._renderTarget );
		_quadMesh.render( renderer );

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

##### `setup(builder: NodeBuilder): PassTextureNode`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const lensflare = Fn( () => {

			// flip uvs so lens flare pivot around the image center

			const texCoord = uv().oneMinus().toVar();

			// ghosts are positioned along this vector

			const ghostVec = sub( vec2( 0.5 ), texCoord ).mul( this.ghostSpacingNode ).toVar();

			// sample ghosts

			const result = vec4().toVar();

			Loop( { start: int( 0 ), end: int( this.ghostSamplesNode ), type: 'int', condition: '<' }, ( { i } ) => {

				// use fract() to ensure that the texture coordinates wrap around

				const sampleUv = fract( texCoord.add( ghostVec.mul( float( i ) ) ) ).toVar();

				// reduce contributions from samples at the screen edge

				const d = distance( sampleUv, vec2( 0.5 ) );
				const weight = pow( d.oneMinus(), this.ghostAttenuationFactorNode );

				// accumulate

				let sample = this.textureNode.sample( sampleUv ).rgb;

				sample = max( sample.sub( this.thresholdNode ), vec3( 0 ) ).mul( this.ghostTintNode );

				result.addAssign( sample.mul( weight ) );

			} );

			return result;

		} );

		this._material.fragmentNode = lensflare().context( builder.getSharedContext() );
		this._material.needsUpdate = true;

		return this._textureNode;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this._renderTarget.dispose();
		this._material.dispose();

	}
```
</details>


---