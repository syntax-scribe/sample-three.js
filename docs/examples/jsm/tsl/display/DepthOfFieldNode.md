[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `DepthOfFieldNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 27 |
| 📊 Variables & Constants | 15 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/DepthOfFieldNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `three/webgpu` |
| `NodeMaterial` | `three/webgpu` |
| `NodeUpdateType` | `three/webgpu` |
| `RenderTarget` | `three/webgpu` |
| `Vector2` | `three/webgpu` |
| `HalfFloatType` | `three/webgpu` |
| `RedFormat` | `three/webgpu` |
| `QuadMesh` | `three/webgpu` |
| `RendererUtils` | `three/webgpu` |
| `convertToTexture` | `three/tsl` |
| `nodeObject` | `three/tsl` |
| `Fn` | `three/tsl` |
| `uniform` | `three/tsl` |
| `smoothstep` | `three/tsl` |
| `step` | `three/tsl` |
| `texture` | `three/tsl` |
| `max` | `three/tsl` |
| `uniformArray` | `three/tsl` |
| `outputStruct` | `three/tsl` |
| `property` | `three/tsl` |
| `vec4` | `three/tsl` |
| `vec3` | `three/tsl` |
| `uv` | `three/tsl` |
| `Loop` | `three/tsl` |
| `min` | `three/tsl` |
| `mix` | `three/tsl` |
| `gaussianBlur` | `./GaussianBlurNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_quadMesh` | `any` | let/var | `new QuadMesh()` | ✗ |
| `_rendererState` | `any` | let/var | `*not shown*` | ✗ |
| `map` | `any` | let/var | `this.textureNode.value` | ✗ |
| `CoC` | `any` | let/var | `this._CoCTextureNode.sample( uvNode ).r` | ✗ |
| `maxVal` | `any` | let/var | `col.rgb` | ✗ |
| `CoC` | `any` | let/var | `col.a` | ✗ |
| `GOLDEN_ANGLE` | `2.39996323` | let/var | `2.39996323` | ✗ |
| `SAMPLES` | `80` | let/var | `80` | ✗ |
| `points64` | `any[]` | let/var | `[]` | ✗ |
| `points16` | `any[]` | let/var | `[]` | ✗ |
| `idx64` | `number` | let/var | `0` | ✗ |
| `idx16` | `number` | let/var | `0` | ✗ |
| `theta` | `number` | let/var | `i * GOLDEN_ANGLE` | ✗ |
| `r` | `number` | let/var | `Math.sqrt( i ) / Math.sqrt( SAMPLES )` | ✗ |
| `p` | `any` | let/var | `new Vector2( r * Math.cos( theta ), r * Math.sin( theta ) )` | ✗ |


---

## Functions

### `DepthOfFieldNode.setSize(width: number, height: number): void`

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
- `this._CoCRT.setSize`
- `this._compositeRT.setSize`
- `Math.round`
- `this._CoCBlurredRT.setSize`
- `this._blur64RT.setSize`
- `this._blur16NearRT.setSize`
- `this._blur16FarRT.setSize`

**Internal Comments:**
```
// blur runs in half resolution (x2)
```

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this._invSize.value.set( 1 / width, 1 / height );

		this._CoCRT.setSize( width, height );
		this._compositeRT.setSize( width, height );

		// blur runs in half resolution

		const halfResX = Math.round( width / 2 );
		const halfResY = Math.round( height / 2 );

		this._CoCBlurredRT.setSize( halfResX, halfResY );
		this._blur64RT.setSize( halfResX, halfResY );
		this._blur16NearRT.setSize( halfResX, halfResY );
		this._blur16FarRT.setSize( halfResX, halfResY );

	}
```
</details>

### `DepthOfFieldNode.getTextureNode(): PassTextureNode`

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

### `DepthOfFieldNode.updateBefore(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
	 * This method is used to update the effect's uniforms once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
```

**Parameters:**

- **`frame`** `NodeFrame`

**Returns:** `void`

**Calls:**

- `this.setSize`
- `RendererUtils.resetRendererState`
- `renderer.setClearColor`
- `renderer.setRenderTarget`
- `_quadMesh.render`
- `RendererUtils.restoreRendererState`

**Internal Comments:**
```
// resize (x2)
// save state (x3)
// coc (x4)
// blur near field to avoid visible aliased edges when the near field (x5)
// is blended with the background (x5)
// blur64 near (x5)
// blur16 near (x4)
// blur64 far (x5)
// blur16 far (x4)
// composite (x4)
// restore (x4)
```

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		const { renderer } = frame;

		// resize

		const map = this.textureNode.value;
		this.setSize( map.image.width, map.image.height );

		// save state

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		renderer.setClearColor( 0x000000, 0 );

		// coc

		_quadMesh.material = this._CoCMaterial;
		renderer.setRenderTarget( this._CoCRT );
		_quadMesh.render( renderer );

		// blur near field to avoid visible aliased edges when the near field
		// is blended with the background

		this._CoCTextureNode.value = this._CoCRT.textures[ 0 ];

		_quadMesh.material = this._CoCBlurredMaterial;
		renderer.setRenderTarget( this._CoCBlurredRT );
		_quadMesh.render( renderer );

		// blur64 near

		this._CoCTextureNode.value = this._CoCBlurredRT.texture;

		_quadMesh.material = this._blur64Material;
		renderer.setRenderTarget( this._blur64RT );
		_quadMesh.render( renderer );

		// blur16 near

		_quadMesh.material = this._blur16Material;
		renderer.setRenderTarget( this._blur16NearRT );
		_quadMesh.render( renderer );

		// blur64 far

		this._CoCTextureNode.value = this._CoCRT.textures[ 1 ];

		_quadMesh.material = this._blur64Material;
		renderer.setRenderTarget( this._blur64RT );
		_quadMesh.render( renderer );

		// blur16 far

		_quadMesh.material = this._blur16Material;
		renderer.setRenderTarget( this._blur16FarRT );
		_quadMesh.render( renderer );

		// composite

		_quadMesh.material = this._compositeMaterial;
		renderer.setRenderTarget( this._compositeRT );
		_quadMesh.render( renderer );

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

### `DepthOfFieldNode.setup(builder: NodeBuilder): ShaderCallNodeInternal`

**JSDoc:**
```typescript
/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {ShaderCallNodeInternal}
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `ShaderCallNodeInternal`

**Calls:**

- `this._generateKernels`
- `property (from three/tsl)`
- `outputStruct (from three/tsl)`
- `Fn (from three/tsl)`
- `this.viewZNode.negate().sub`
- `smoothstep (from three/tsl)`
- `signedDist.abs`
- `nearField.assign`
- `step( signedDist, 0 ).mul`
- `farField.assign`
- `step( 0, signedDist ).mul`
- `vec4 (from three/tsl)`
- `CoC().context`
- `builder.getSharedContext`
- `gaussianBlur (from ./GaussianBlurNode.js)`
- `uniformArray (from three/tsl)`
- `vec3 (from three/tsl)`
- `uv (from three/tsl)`
- `this._CoCTextureNode.sample`
- `this._invSize.mul( this.bokehScaleNode ).mul`
- `Loop (from three/tsl)`
- `uvNode.add`
- `sampleStep.mul`
- `bokeh64.element`
- `this.textureNode.sample`
- `acc.addAssign`
- `acc.divAssign`
- `blur64().context`
- `this._blur64TextureNode.sample( uvNode ).toVar`
- `bokeh16.element`
- `this._blur64TextureNode.sample`
- `maxVal.assign`
- `max (from three/tsl)`
- `blur16().context`
- `this._blur16NearTextureNode.sample`
- `this._blur16FarTextureNode.sample`
- `min( near.a, 0.5 ).mul`
- `min( far.a, 0.5 ).mul`
- `vec4( 0, 0, 0, 1 ).toVar`
- `mix (from three/tsl)`
- `composite().context`

**Internal Comments:**
```
// CoC, near and far fields (x2)
// blurred CoC for near field (x5)
// bokeh 64 blur pass (x2)
// bokeh 16 blur pass (x2)
// composite (x2)
// TODO: applying the bokeh scale to the near field CoC value introduces blending (x2)
// issues around edges of blurred foreground objects when their are rendered above (x2)
// the background. for now, don't apply the bokeh scale to the blend factors. that (x2)
// will cause less blur for objects which are partly out-of-focus (CoC between 0 and 1). (x2)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const kernels = this._generateKernels();

		// CoC, near and far fields

		const nearField = property( 'float' );
		const farField = property( 'float' );

		const outputNode = outputStruct( nearField, farField );

		const CoC = Fn( () => {

			const signedDist = this.viewZNode.negate().sub( this.focusDistanceNode );
			const CoC = smoothstep( 0, this.focalLengthNode, signedDist.abs() );

			nearField.assign( step( signedDist, 0 ).mul( CoC ) );
			farField.assign( step( 0, signedDist ).mul( CoC ) );

			return vec4( 0 );

		} );

		this._CoCMaterial.colorNode = CoC().context( builder.getSharedContext() );
		this._CoCMaterial.outputNode = outputNode;
		this._CoCMaterial.needsUpdate = true;

		// blurred CoC for near field

		this._CoCBlurredMaterial.colorNode = gaussianBlur( this._CoCTextureNode, 1, 2 );
		this._CoCBlurredMaterial.needsUpdate = true;

		// bokeh 64 blur pass

		const bokeh64 = uniformArray( kernels.points64 );

		const blur64 = Fn( () => {

			const acc = vec3();
			const uvNode = uv();

			const CoC = this._CoCTextureNode.sample( uvNode ).r;
			const sampleStep = this._invSize.mul( this.bokehScaleNode ).mul( CoC );

			Loop( 64, ( { i } ) => {

				const sUV = uvNode.add( sampleStep.mul( bokeh64.element( i ) ) );
				const tap = this.textureNode.sample( sUV );

				acc.addAssign( tap.rgb );

			} );

			acc.divAssign( 64 );

			return vec4( acc, CoC );

		} );

		this._blur64Material.fragmentNode = blur64().context( builder.getSharedContext() );
		this._blur64Material.needsUpdate = true;

		// bokeh 16 blur pass

		const bokeh16 = uniformArray( kernels.points16 );

		const blur16 = Fn( () => {

			const uvNode = uv();

			const col = this._blur64TextureNode.sample( uvNode ).toVar();
			const maxVal = col.rgb;
			const CoC = col.a;
			const sampleStep = this._invSize.mul( this.bokehScaleNode ).mul( CoC );

			Loop( 16, ( { i } ) => {

				const sUV = uvNode.add( sampleStep.mul( bokeh16.element( i ) ) );
				const tap = this._blur64TextureNode.sample( sUV );

				maxVal.assign( max( tap.rgb, maxVal ) );

			} );

			return vec4( maxVal, CoC );

		} );

		this._blur16Material.fragmentNode = blur16().context( builder.getSharedContext() );
		this._blur16Material.needsUpdate = true;

		// composite

		const composite = Fn( () => {

			const uvNode = uv();

			const near = this._blur16NearTextureNode.sample( uvNode );
			const far = this._blur16FarTextureNode.sample( uvNode );
			const beauty = this.textureNode.sample( uvNode );

			// TODO: applying the bokeh scale to the near field CoC value introduces blending
			// issues around edges of blurred foreground objects when their are rendered above
			// the background. for now, don't apply the bokeh scale to the blend factors. that
			// will cause less blur for objects which are partly out-of-focus (CoC between 0 and 1).

			const blendNear = min( near.a, 0.5 ).mul( 2 );
			const blendFar = min( far.a, 0.5 ).mul( 2 );

			const result = vec4( 0, 0, 0, 1 ).toVar();
			result.rgb = mix( beauty.rgb, far.rgb, blendFar );
			result.rgb = mix( result.rgb, near.rgb, blendNear );

			return result;

		} );

		this._compositeMaterial.fragmentNode = composite().context( builder.getSharedContext() );
		this._compositeMaterial.needsUpdate = true;

		return this._textureNode;

	}
```
</details>

### `DepthOfFieldNode._generateKernels(): { points16: any[]; points64: any[]; }`

**Returns:** `{ points16: any[]; points64: any[]; }`

**Calls:**

- `Math.sqrt`
- `Math.cos`
- `Math.sin`

**Internal Comments:**
```
// Vogel's method, see https://www.shadertoy.com/view/4fBXRG (x2)
// this approach allows to generate uniformly distributed sample (x2)
// points in a disc-shaped pattern. Blurring with these samples (x2)
// produces a typical optical lens blur (x2)
```

<details><summary>Code</summary>

```typescript
_generateKernels() {

		// Vogel's method, see https://www.shadertoy.com/view/4fBXRG
		// this approach allows to generate uniformly distributed sample
		// points in a disc-shaped pattern. Blurring with these samples
		// produces a typical optical lens blur

		const GOLDEN_ANGLE = 2.39996323;
		const SAMPLES = 80;

		const points64 = [];
		const points16 = [];

		let idx64 = 0;
		let idx16 = 0;

		for ( let i = 0; i < SAMPLES; i ++ ) {

			const theta = i * GOLDEN_ANGLE;
			const r = Math.sqrt( i ) / Math.sqrt( SAMPLES );

			const p = new Vector2( r * Math.cos( theta ), r * Math.sin( theta ) );

			if ( i % 5 === 0 ) {

				points16[ idx16 ] = p;
				idx16 ++;

			} else {

				points64[ idx64 ] = p;
				idx64 ++;

			}

		}

		return { points16, points64 };

	}
```
</details>

### `DepthOfFieldNode.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources. This method should be called
	 * when the effect is no longer required.
	 */
```

**Returns:** `void`

**Calls:**

- `this._CoCRT.dispose`
- `this._CoCBlurredRT.dispose`
- `this._blur64RT.dispose`
- `this._blur16NearRT.dispose`
- `this._blur16FarRT.dispose`
- `this._compositeRT.dispose`
- `this._CoCMaterial.dispose`
- `this._CoCBlurredMaterial.dispose`
- `this._blur64Material.dispose`
- `this._blur16Material.dispose`
- `this._compositeMaterial.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this._CoCRT.dispose();
		this._CoCBlurredRT.dispose();
		this._blur64RT.dispose();
		this._blur16NearRT.dispose();
		this._blur16FarRT.dispose();
		this._compositeRT.dispose();

		this._CoCMaterial.dispose();
		this._CoCBlurredMaterial.dispose();
		this._blur64Material.dispose();
		this._blur16Material.dispose();
		this._compositeMaterial.dispose();

	}
```
</details>

### `dof(node: any, viewZNode: any, focusDistance: any, focalLength: any, bokehScale: any): DepthOfFieldNode`

**Parameters:**

- **`node`** `any`
- **`viewZNode`** `any`
- **`focusDistance`** `any`
- **`focalLength`** `any`
- **`bokehScale`** `any`

**Returns:** `DepthOfFieldNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( node, viewZNode, focusDistance = 1, focalLength = 1, bokehScale = 1 ) => nodeObject( new DepthOfFieldNode( convertToTexture( node ), nodeObject( viewZNode ), nodeObject( focusDistance ), nodeObject( focalLength ), nodeObject( bokehScale ) ) )
```
</details>


---

## Classes

### `DepthOfFieldNode`

<details><summary>Class Code</summary>

```ts
class DepthOfFieldNode extends TempNode {

	static get type() {

		return 'DepthOfFieldNode';

	}

	/**
	 * Constructs a new DOF node.
	 *
	 * @param {TextureNode} textureNode - The texture node that represents the input of the effect.
	 * @param {Node<float>} viewZNode - Represents the viewZ depth values of the scene.
	 * @param {Node<float>} focusDistanceNode - Defines the effect's focus which is the distance along the camera's look direction in world units.
	 * @param {Node<float>} focalLengthNode - How far an object can be from the focal plane before it goes completely out-of-focus in world units.
	 * @param {Node<float>} bokehScaleNode - A unitless value for artistic purposes to adjust the size of the bokeh.
	 */
	constructor( textureNode, viewZNode, focusDistanceNode, focalLengthNode, bokehScaleNode ) {

		super( 'vec4' );

		/**
		 * The texture node that represents the input of the effect.
		 *
		 * @type {TextureNode}
		 */
		this.textureNode = textureNode;

		/**
		 * Represents the viewZ depth values of the scene.
		 *
		 * @type {Node<float>}
		 */
		this.viewZNode = viewZNode;

		/**
		 * Defines the effect's focus which is the distance along the camera's look direction in world units.
		 *
		 * @type {Node<float>}
		 */
		this.focusDistanceNode = focusDistanceNode;

		/**
		 * How far an object can be from the focal plane before it goes completely out-of-focus in world units.
		 *
		 * @type {Node<float>}
		 */
		this.focalLengthNode = focalLengthNode;

		/**
		 * A unitless value for artistic purposes to adjust the size of the bokeh.
		 *
		 * @type {Node<float>}
		 */
		this.bokehScaleNode = bokehScaleNode;

		/**
		 * The inverse size of the resolution.
		 *
		 * @private
		 * @type {UniformNode<vec2>}
		 */
		this._invSize = uniform( new Vector2() );

		/**
		 * The render target used for the near and far field.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._CoCRT = new RenderTarget( 1, 1, { depthBuffer: false, type: HalfFloatType, format: RedFormat, count: 2 } );
		this._CoCRT.textures[ 0 ].name = 'DepthOfField.NearField';
		this._CoCRT.textures[ 1 ].name = 'DepthOfField.FarField';

		/**
		 * The render target used for blurring the near field.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._CoCBlurredRT = new RenderTarget( 1, 1, { depthBuffer: false, type: HalfFloatType, format: RedFormat } );
		this._CoCBlurredRT.texture.name = 'DepthOfField.NearFieldBlurred';

		/**
		 * The render target used for the first blur pass.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._blur64RT = new RenderTarget( 1, 1, { depthBuffer: false, type: HalfFloatType } );
		this._blur64RT.texture.name = 'DepthOfField.Blur64';

		/**
		 * The render target used for the near field's second blur pass.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._blur16NearRT = new RenderTarget( 1, 1, { depthBuffer: false, type: HalfFloatType } );
		this._blur16NearRT.texture.name = 'DepthOfField.Blur16Near';

		/**
		 * The render target used for the far field's second blur pass.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._blur16FarRT = new RenderTarget( 1, 1, { depthBuffer: false, type: HalfFloatType } );
		this._blur16FarRT.texture.name = 'DepthOfField.Blur16Far';

		/**
		 * The render target used for the composite
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._compositeRT = new RenderTarget( 1, 1, { depthBuffer: false, type: HalfFloatType } );
		this._compositeRT.texture.name = 'DepthOfField.Composite';

		/**
		 * The material used for the CoC/near and far fields.
		 *
		 * @private
		 * @type {NodeMaterial}
		 */
		this._CoCMaterial = new NodeMaterial();

		/**
		 * The material used for blurring the near field.
		 *
		 * @private
		 * @type {NodeMaterial}
		 */
		this._CoCBlurredMaterial = new NodeMaterial();

		/**
		 * The material used for the 64 tap blur.
		 *
		 * @private
		 * @type {NodeMaterial}
		 */
		this._blur64Material = new NodeMaterial();

		/**
		 * The material used for the 16 tap blur.
		 *
		 * @private
		 * @type {NodeMaterial}
		 */
		this._blur16Material = new NodeMaterial();

		/**
		 * The material used for the final composite.
		 *
		 * @private
		 * @type {NodeMaterial}
		 */
		this._compositeMaterial = new NodeMaterial();

		/**
		 * The result of the effect is represented as a separate texture node.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._textureNode = texture( this._compositeRT.texture );

		/**
		 * The result of the CoC pass as a texture node.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._CoCTextureNode = texture( this._CoCRT.texture );

		/**
		 * The result of the blur64 pass as a texture node.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._blur64TextureNode = texture( this._blur64RT.texture );

		/**
		 * The result of the near field's blur16 pass as a texture node.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._blur16NearTextureNode = texture( this._blur16NearRT.texture );

		/**
		 * The result of the far field's blur16 pass as a texture node.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._blur16FarTextureNode = texture( this._blur16FarRT.texture );

		/**
		 * The `updateBeforeType` is set to `NodeUpdateType.FRAME` since the node updates
		 * its internal uniforms once per frame in `updateBefore()`.
		 *
		 * @type {string}
		 * @default 'frame'
		 */
		this.updateBeforeType = NodeUpdateType.FRAME;

	}

	/**
	 * Sets the size of the effect.
	 *
	 * @param {number} width - The width of the effect.
	 * @param {number} height - The height of the effect.
	 */
	setSize( width, height ) {

		this._invSize.value.set( 1 / width, 1 / height );

		this._CoCRT.setSize( width, height );
		this._compositeRT.setSize( width, height );

		// blur runs in half resolution

		const halfResX = Math.round( width / 2 );
		const halfResY = Math.round( height / 2 );

		this._CoCBlurredRT.setSize( halfResX, halfResY );
		this._blur64RT.setSize( halfResX, halfResY );
		this._blur16NearRT.setSize( halfResX, halfResY );
		this._blur16FarRT.setSize( halfResX, halfResY );

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
	 * This method is used to update the effect's uniforms once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
	updateBefore( frame ) {

		const { renderer } = frame;

		// resize

		const map = this.textureNode.value;
		this.setSize( map.image.width, map.image.height );

		// save state

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		renderer.setClearColor( 0x000000, 0 );

		// coc

		_quadMesh.material = this._CoCMaterial;
		renderer.setRenderTarget( this._CoCRT );
		_quadMesh.render( renderer );

		// blur near field to avoid visible aliased edges when the near field
		// is blended with the background

		this._CoCTextureNode.value = this._CoCRT.textures[ 0 ];

		_quadMesh.material = this._CoCBlurredMaterial;
		renderer.setRenderTarget( this._CoCBlurredRT );
		_quadMesh.render( renderer );

		// blur64 near

		this._CoCTextureNode.value = this._CoCBlurredRT.texture;

		_quadMesh.material = this._blur64Material;
		renderer.setRenderTarget( this._blur64RT );
		_quadMesh.render( renderer );

		// blur16 near

		_quadMesh.material = this._blur16Material;
		renderer.setRenderTarget( this._blur16NearRT );
		_quadMesh.render( renderer );

		// blur64 far

		this._CoCTextureNode.value = this._CoCRT.textures[ 1 ];

		_quadMesh.material = this._blur64Material;
		renderer.setRenderTarget( this._blur64RT );
		_quadMesh.render( renderer );

		// blur16 far

		_quadMesh.material = this._blur16Material;
		renderer.setRenderTarget( this._blur16FarRT );
		_quadMesh.render( renderer );

		// composite

		_quadMesh.material = this._compositeMaterial;
		renderer.setRenderTarget( this._compositeRT );
		_quadMesh.render( renderer );

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}

	/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {ShaderCallNodeInternal}
	 */
	setup( builder ) {

		const kernels = this._generateKernels();

		// CoC, near and far fields

		const nearField = property( 'float' );
		const farField = property( 'float' );

		const outputNode = outputStruct( nearField, farField );

		const CoC = Fn( () => {

			const signedDist = this.viewZNode.negate().sub( this.focusDistanceNode );
			const CoC = smoothstep( 0, this.focalLengthNode, signedDist.abs() );

			nearField.assign( step( signedDist, 0 ).mul( CoC ) );
			farField.assign( step( 0, signedDist ).mul( CoC ) );

			return vec4( 0 );

		} );

		this._CoCMaterial.colorNode = CoC().context( builder.getSharedContext() );
		this._CoCMaterial.outputNode = outputNode;
		this._CoCMaterial.needsUpdate = true;

		// blurred CoC for near field

		this._CoCBlurredMaterial.colorNode = gaussianBlur( this._CoCTextureNode, 1, 2 );
		this._CoCBlurredMaterial.needsUpdate = true;

		// bokeh 64 blur pass

		const bokeh64 = uniformArray( kernels.points64 );

		const blur64 = Fn( () => {

			const acc = vec3();
			const uvNode = uv();

			const CoC = this._CoCTextureNode.sample( uvNode ).r;
			const sampleStep = this._invSize.mul( this.bokehScaleNode ).mul( CoC );

			Loop( 64, ( { i } ) => {

				const sUV = uvNode.add( sampleStep.mul( bokeh64.element( i ) ) );
				const tap = this.textureNode.sample( sUV );

				acc.addAssign( tap.rgb );

			} );

			acc.divAssign( 64 );

			return vec4( acc, CoC );

		} );

		this._blur64Material.fragmentNode = blur64().context( builder.getSharedContext() );
		this._blur64Material.needsUpdate = true;

		// bokeh 16 blur pass

		const bokeh16 = uniformArray( kernels.points16 );

		const blur16 = Fn( () => {

			const uvNode = uv();

			const col = this._blur64TextureNode.sample( uvNode ).toVar();
			const maxVal = col.rgb;
			const CoC = col.a;
			const sampleStep = this._invSize.mul( this.bokehScaleNode ).mul( CoC );

			Loop( 16, ( { i } ) => {

				const sUV = uvNode.add( sampleStep.mul( bokeh16.element( i ) ) );
				const tap = this._blur64TextureNode.sample( sUV );

				maxVal.assign( max( tap.rgb, maxVal ) );

			} );

			return vec4( maxVal, CoC );

		} );

		this._blur16Material.fragmentNode = blur16().context( builder.getSharedContext() );
		this._blur16Material.needsUpdate = true;

		// composite

		const composite = Fn( () => {

			const uvNode = uv();

			const near = this._blur16NearTextureNode.sample( uvNode );
			const far = this._blur16FarTextureNode.sample( uvNode );
			const beauty = this.textureNode.sample( uvNode );

			// TODO: applying the bokeh scale to the near field CoC value introduces blending
			// issues around edges of blurred foreground objects when their are rendered above
			// the background. for now, don't apply the bokeh scale to the blend factors. that
			// will cause less blur for objects which are partly out-of-focus (CoC between 0 and 1).

			const blendNear = min( near.a, 0.5 ).mul( 2 );
			const blendFar = min( far.a, 0.5 ).mul( 2 );

			const result = vec4( 0, 0, 0, 1 ).toVar();
			result.rgb = mix( beauty.rgb, far.rgb, blendFar );
			result.rgb = mix( result.rgb, near.rgb, blendNear );

			return result;

		} );

		this._compositeMaterial.fragmentNode = composite().context( builder.getSharedContext() );
		this._compositeMaterial.needsUpdate = true;

		return this._textureNode;

	}

	_generateKernels() {

		// Vogel's method, see https://www.shadertoy.com/view/4fBXRG
		// this approach allows to generate uniformly distributed sample
		// points in a disc-shaped pattern. Blurring with these samples
		// produces a typical optical lens blur

		const GOLDEN_ANGLE = 2.39996323;
		const SAMPLES = 80;

		const points64 = [];
		const points16 = [];

		let idx64 = 0;
		let idx16 = 0;

		for ( let i = 0; i < SAMPLES; i ++ ) {

			const theta = i * GOLDEN_ANGLE;
			const r = Math.sqrt( i ) / Math.sqrt( SAMPLES );

			const p = new Vector2( r * Math.cos( theta ), r * Math.sin( theta ) );

			if ( i % 5 === 0 ) {

				points16[ idx16 ] = p;
				idx16 ++;

			} else {

				points64[ idx64 ] = p;
				idx64 ++;

			}

		}

		return { points16, points64 };

	}

	/**
	 * Frees internal resources. This method should be called
	 * when the effect is no longer required.
	 */
	dispose() {

		this._CoCRT.dispose();
		this._CoCBlurredRT.dispose();
		this._blur64RT.dispose();
		this._blur16NearRT.dispose();
		this._blur16FarRT.dispose();
		this._compositeRT.dispose();

		this._CoCMaterial.dispose();
		this._CoCBlurredMaterial.dispose();
		this._blur64Material.dispose();
		this._blur16Material.dispose();
		this._compositeMaterial.dispose();

	}

}
```
</details>

#### Methods

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		this._invSize.value.set( 1 / width, 1 / height );

		this._CoCRT.setSize( width, height );
		this._compositeRT.setSize( width, height );

		// blur runs in half resolution

		const halfResX = Math.round( width / 2 );
		const halfResY = Math.round( height / 2 );

		this._CoCBlurredRT.setSize( halfResX, halfResY );
		this._blur64RT.setSize( halfResX, halfResY );
		this._blur16NearRT.setSize( halfResX, halfResY );
		this._blur16FarRT.setSize( halfResX, halfResY );

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

##### `updateBefore(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		const { renderer } = frame;

		// resize

		const map = this.textureNode.value;
		this.setSize( map.image.width, map.image.height );

		// save state

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		renderer.setClearColor( 0x000000, 0 );

		// coc

		_quadMesh.material = this._CoCMaterial;
		renderer.setRenderTarget( this._CoCRT );
		_quadMesh.render( renderer );

		// blur near field to avoid visible aliased edges when the near field
		// is blended with the background

		this._CoCTextureNode.value = this._CoCRT.textures[ 0 ];

		_quadMesh.material = this._CoCBlurredMaterial;
		renderer.setRenderTarget( this._CoCBlurredRT );
		_quadMesh.render( renderer );

		// blur64 near

		this._CoCTextureNode.value = this._CoCBlurredRT.texture;

		_quadMesh.material = this._blur64Material;
		renderer.setRenderTarget( this._blur64RT );
		_quadMesh.render( renderer );

		// blur16 near

		_quadMesh.material = this._blur16Material;
		renderer.setRenderTarget( this._blur16NearRT );
		_quadMesh.render( renderer );

		// blur64 far

		this._CoCTextureNode.value = this._CoCRT.textures[ 1 ];

		_quadMesh.material = this._blur64Material;
		renderer.setRenderTarget( this._blur64RT );
		_quadMesh.render( renderer );

		// blur16 far

		_quadMesh.material = this._blur16Material;
		renderer.setRenderTarget( this._blur16FarRT );
		_quadMesh.render( renderer );

		// composite

		_quadMesh.material = this._compositeMaterial;
		renderer.setRenderTarget( this._compositeRT );
		_quadMesh.render( renderer );

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

##### `setup(builder: NodeBuilder): ShaderCallNodeInternal`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const kernels = this._generateKernels();

		// CoC, near and far fields

		const nearField = property( 'float' );
		const farField = property( 'float' );

		const outputNode = outputStruct( nearField, farField );

		const CoC = Fn( () => {

			const signedDist = this.viewZNode.negate().sub( this.focusDistanceNode );
			const CoC = smoothstep( 0, this.focalLengthNode, signedDist.abs() );

			nearField.assign( step( signedDist, 0 ).mul( CoC ) );
			farField.assign( step( 0, signedDist ).mul( CoC ) );

			return vec4( 0 );

		} );

		this._CoCMaterial.colorNode = CoC().context( builder.getSharedContext() );
		this._CoCMaterial.outputNode = outputNode;
		this._CoCMaterial.needsUpdate = true;

		// blurred CoC for near field

		this._CoCBlurredMaterial.colorNode = gaussianBlur( this._CoCTextureNode, 1, 2 );
		this._CoCBlurredMaterial.needsUpdate = true;

		// bokeh 64 blur pass

		const bokeh64 = uniformArray( kernels.points64 );

		const blur64 = Fn( () => {

			const acc = vec3();
			const uvNode = uv();

			const CoC = this._CoCTextureNode.sample( uvNode ).r;
			const sampleStep = this._invSize.mul( this.bokehScaleNode ).mul( CoC );

			Loop( 64, ( { i } ) => {

				const sUV = uvNode.add( sampleStep.mul( bokeh64.element( i ) ) );
				const tap = this.textureNode.sample( sUV );

				acc.addAssign( tap.rgb );

			} );

			acc.divAssign( 64 );

			return vec4( acc, CoC );

		} );

		this._blur64Material.fragmentNode = blur64().context( builder.getSharedContext() );
		this._blur64Material.needsUpdate = true;

		// bokeh 16 blur pass

		const bokeh16 = uniformArray( kernels.points16 );

		const blur16 = Fn( () => {

			const uvNode = uv();

			const col = this._blur64TextureNode.sample( uvNode ).toVar();
			const maxVal = col.rgb;
			const CoC = col.a;
			const sampleStep = this._invSize.mul( this.bokehScaleNode ).mul( CoC );

			Loop( 16, ( { i } ) => {

				const sUV = uvNode.add( sampleStep.mul( bokeh16.element( i ) ) );
				const tap = this._blur64TextureNode.sample( sUV );

				maxVal.assign( max( tap.rgb, maxVal ) );

			} );

			return vec4( maxVal, CoC );

		} );

		this._blur16Material.fragmentNode = blur16().context( builder.getSharedContext() );
		this._blur16Material.needsUpdate = true;

		// composite

		const composite = Fn( () => {

			const uvNode = uv();

			const near = this._blur16NearTextureNode.sample( uvNode );
			const far = this._blur16FarTextureNode.sample( uvNode );
			const beauty = this.textureNode.sample( uvNode );

			// TODO: applying the bokeh scale to the near field CoC value introduces blending
			// issues around edges of blurred foreground objects when their are rendered above
			// the background. for now, don't apply the bokeh scale to the blend factors. that
			// will cause less blur for objects which are partly out-of-focus (CoC between 0 and 1).

			const blendNear = min( near.a, 0.5 ).mul( 2 );
			const blendFar = min( far.a, 0.5 ).mul( 2 );

			const result = vec4( 0, 0, 0, 1 ).toVar();
			result.rgb = mix( beauty.rgb, far.rgb, blendFar );
			result.rgb = mix( result.rgb, near.rgb, blendNear );

			return result;

		} );

		this._compositeMaterial.fragmentNode = composite().context( builder.getSharedContext() );
		this._compositeMaterial.needsUpdate = true;

		return this._textureNode;

	}
```
</details>

##### `_generateKernels(): { points16: any[]; points64: any[]; }`

<details><summary>Code</summary>

```ts
_generateKernels() {

		// Vogel's method, see https://www.shadertoy.com/view/4fBXRG
		// this approach allows to generate uniformly distributed sample
		// points in a disc-shaped pattern. Blurring with these samples
		// produces a typical optical lens blur

		const GOLDEN_ANGLE = 2.39996323;
		const SAMPLES = 80;

		const points64 = [];
		const points16 = [];

		let idx64 = 0;
		let idx16 = 0;

		for ( let i = 0; i < SAMPLES; i ++ ) {

			const theta = i * GOLDEN_ANGLE;
			const r = Math.sqrt( i ) / Math.sqrt( SAMPLES );

			const p = new Vector2( r * Math.cos( theta ), r * Math.sin( theta ) );

			if ( i % 5 === 0 ) {

				points16[ idx16 ] = p;
				idx16 ++;

			} else {

				points64[ idx64 ] = p;
				idx64 ++;

			}

		}

		return { points16, points64 };

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this._CoCRT.dispose();
		this._CoCBlurredRT.dispose();
		this._blur64RT.dispose();
		this._blur16NearRT.dispose();
		this._blur16FarRT.dispose();
		this._compositeRT.dispose();

		this._CoCMaterial.dispose();
		this._CoCBlurredMaterial.dispose();
		this._blur64Material.dispose();
		this._blur16Material.dispose();
		this._compositeMaterial.dispose();

	}
```
</details>


---