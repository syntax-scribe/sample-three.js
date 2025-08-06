[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `TRAANode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 28 |
| 📊 Variables & Constants | 14 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/TRAANode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `HalfFloatType` | `three/webgpu` |
| `Vector2` | `three/webgpu` |
| `RenderTarget` | `three/webgpu` |
| `RendererUtils` | `three/webgpu` |
| `QuadMesh` | `three/webgpu` |
| `NodeMaterial` | `three/webgpu` |
| `TempNode` | `three/webgpu` |
| `NodeUpdateType` | `three/webgpu` |
| `Matrix4` | `three/webgpu` |
| `add` | `three/tsl` |
| `float` | `three/tsl` |
| `If` | `three/tsl` |
| `Loop` | `three/tsl` |
| `int` | `three/tsl` |
| `Fn` | `three/tsl` |
| `min` | `three/tsl` |
| `max` | `three/tsl` |
| `clamp` | `three/tsl` |
| `nodeObject` | `three/tsl` |
| `texture` | `three/tsl` |
| `uniform` | `three/tsl` |
| `uv` | `three/tsl` |
| `vec2` | `three/tsl` |
| `vec4` | `three/tsl` |
| `luminance` | `three/tsl` |
| `convertToTexture` | `three/tsl` |
| `passTexture` | `three/tsl` |
| `velocity` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_quadMesh` | `any` | let/var | `new QuadMesh()` | ✗ |
| `_size` | `any` | let/var | `new Vector2()` | ✗ |
| `_rendererState` | `any` | let/var | `*not shown*` | ✗ |
| `viewOffset` | `{ fullWidth: number; fullHeight: numb...` | let/var | `{ fullWidth: width, fullHeight: height, offsetX: 0, offsetY: 0, width: width,...` | ✗ |
| `jitterOffset` | `number[]` | let/var | `_JitterVectors[ this._jitterIndex ]` | ✗ |
| `beautyRenderTarget` | `any` | let/var | `( this.beautyNode.isRTTNode ) ? this.beautyNode.renderTarget : this.beautyNod...` | ✗ |
| `width` | `any` | let/var | `beautyRenderTarget.texture.width` | ✗ |
| `height` | `any` | let/var | `beautyRenderTarget.texture.height` | ✗ |
| `needsRestart` | `boolean` | let/var | `this._historyRenderTarget.width !== width \|\| this._historyRenderTarget.heig...` | ✗ |
| `postProcessing` | `any` | let/var | `builder.context.postProcessing` | ✗ |
| `sampleTexture` | `TextureNode` | let/var | `this.beautyNode` | ✗ |
| `depthTexture` | `TextureNode` | let/var | `this.depthNode` | ✗ |
| `velocityTexture` | `TextureNode` | let/var | `this.velocityNode` | ✗ |
| `_JitterVectors` | `number[][]` | let/var | `[ [ - 4, - 7 ], [ - 7, - 5 ], [ - 3, - 5 ], [ - 5, - 4 ], [ - 1, - 4 ], [ - 2...` | ✗ |


---

## Functions

### `TRAANode.getTextureNode(): PassTextureNode`

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

### `TRAANode.setSize(width: number, height: number): void`

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

- `this._historyRenderTarget.setSize`
- `this._resolveRenderTarget.setSize`
- `this._invSize.value.set`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this._historyRenderTarget.setSize( width, height );
		this._resolveRenderTarget.setSize( width, height );

		this._invSize.value.set( 1 / width, 1 / height );

	}
```
</details>

### `TRAANode.setViewOffset(width: number, height: number): void`

**JSDoc:**
```typescript
/**
	 * Defines the TRAA's current jitter as a view offset
	 * to the scene's camera.
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

- `this.camera.updateProjectionMatrix`
- `this._originalProjectionMatrix.copy`
- `velocity.setProjectionMatrix`
- `this.camera.setViewOffset`

**Internal Comments:**
```
// save original/unjittered projection matrix for velocity pass (x5)
// (x2)
```

<details><summary>Code</summary>

```typescript
setViewOffset( width, height ) {

		// save original/unjittered projection matrix for velocity pass

		this.camera.updateProjectionMatrix();
		this._originalProjectionMatrix.copy( this.camera.projectionMatrix );

		velocity.setProjectionMatrix( this._originalProjectionMatrix );

		//

		const viewOffset = {

			fullWidth: width,
			fullHeight: height,
			offsetX: 0,
			offsetY: 0,
			width: width,
			height: height

		};

		const jitterOffset = _JitterVectors[ this._jitterIndex ];

		this.camera.setViewOffset(

			viewOffset.fullWidth, viewOffset.fullHeight,

			viewOffset.offsetX + jitterOffset[ 0 ] * 0.0625, viewOffset.offsetY + jitterOffset[ 1 ] * 0.0625, // 0.0625 = 1 / 16

			viewOffset.width, viewOffset.height

		);

	}
```
</details>

### `TRAANode.clearViewOffset(): void`

**JSDoc:**
```typescript
/**
	 * Clears the view offset from the scene's camera.
	 */
```

**Returns:** `void`

**Calls:**

- `this.camera.clearViewOffset`
- `velocity.setProjectionMatrix`

**Internal Comments:**
```
// update jitter index (x4)
```

<details><summary>Code</summary>

```typescript
clearViewOffset() {

		this.camera.clearViewOffset();

		velocity.setProjectionMatrix( null );

		// update jitter index

		this._jitterIndex ++;
		this._jitterIndex = this._jitterIndex % ( _JitterVectors.length - 1 );

	}
```
</details>

### `TRAANode.updateBefore(frame: NodeFrame): void`

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

- `this.setViewOffset`
- `RendererUtils.resetRendererState`
- `this.setSize`
- `renderer.setRenderTarget`
- `renderer.clear`
- `renderer.copyTextureToTexture`
- `_quadMesh.render`
- `RendererUtils.restoreRendererState`

**Internal Comments:**
```
// keep the TRAA in sync with the dimensions of the beauty node (x2)
// (x3)
// every time when the dimensions change we need fresh history data
// bind and clear render target to make sure they are initialized after the resize which triggers a dispose() (x4)
// make sure to reset the history with the contents of the beauty buffer otherwise subsequent frames after the (x4)
// resize will fade from a darker color to the correct one because the history was cleared with black. (x4)
// resolve (x4)
// update history (x4)
// restore (x4)
```

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		const { renderer } = frame;

		// keep the TRAA in sync with the dimensions of the beauty node

		const beautyRenderTarget = ( this.beautyNode.isRTTNode ) ? this.beautyNode.renderTarget : this.beautyNode.passNode.renderTarget;

		const width = beautyRenderTarget.texture.width;
		const height = beautyRenderTarget.texture.height;

		//

		if ( this._needsPostProcessingSync === true ) {

			this.setViewOffset( width, height );

			this._needsPostProcessingSync = false;

		}

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		const needsRestart = this._historyRenderTarget.width !== width || this._historyRenderTarget.height !== height;
		this.setSize( width, height );

		// every time when the dimensions change we need fresh history data

		if ( needsRestart === true ) {

			// bind and clear render target to make sure they are initialized after the resize which triggers a dispose()

			renderer.setRenderTarget( this._historyRenderTarget );
			renderer.clear();

			renderer.setRenderTarget( this._resolveRenderTarget );
			renderer.clear();

			// make sure to reset the history with the contents of the beauty buffer otherwise subsequent frames after the
			// resize will fade from a darker color to the correct one because the history was cleared with black.

			renderer.copyTextureToTexture( beautyRenderTarget.texture, this._historyRenderTarget.texture );

		}

		// resolve

		renderer.setRenderTarget( this._resolveRenderTarget );
		_quadMesh.material = this._resolveMaterial;
		_quadMesh.render( renderer );
		renderer.setRenderTarget( null );

		// update history

		renderer.copyTextureToTexture( this._resolveRenderTarget.texture, this._historyRenderTarget.texture );

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

### `TRAANode.setup(builder: NodeBuilder): PassTextureNode`

**JSDoc:**
```typescript
/**
	 * This method is used to setup the effect's render targets and TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {PassTextureNode}
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `PassTextureNode`

**Calls:**

- `builder.renderer.getDrawingBufferSize`
- `this.setViewOffset`
- `this.clearViewOffset`
- `texture (from three/tsl)`
- `Fn (from three/tsl)`
- `uv (from three/tsl)`
- `vec4( 10000 ).toVar`
- `vec4( - 10000 ).toVar`
- `float( 1 ).toVar`
- `vec2( 0 ).toVar`
- `Loop (from three/tsl)`
- `int (from three/tsl)`
- `uvNode.add( vec2( float( x ), float( y ) ).mul( this._invSize ) ).toVar`
- `max( vec4( 0 ), sampleTexture.sample( uvNeighbor ) ).toVar`
- `minColor.assign`
- `min (from three/tsl)`
- `maxColor.assign`
- `max (from three/tsl)`
- `depthTexture.sample( uvNeighbor ).r.toVar`
- `If (from three/tsl)`
- `currentDepth.lessThan`
- `closestDepth.assign`
- `closestDepthPixelPosition.assign`
- `velocityTexture.sample( closestDepthPixelPosition ).xy.mul`
- `vec2 (from three/tsl)`
- `sampleTexture.sample`
- `historyTexture.sample`
- `uvNode.sub`
- `clamp (from three/tsl)`
- `float( 0.05 ).toVar`
- `currentWeight.oneMinus().toVar`
- `currentColor.mul`
- `float( 1 ).div`
- `max( currentColor.r, currentColor.g, currentColor.b ).add`
- `clampedHistoryColor.mul`
- `max( clampedHistoryColor.r, clampedHistoryColor.g, clampedHistoryColor.b ).add`
- `luminance (from three/tsl)`
- `currentWeight.mulAssign`
- `float( 1.0 ).div`
- `luminanceCurrent.add`
- `historyWeight.mulAssign`
- `luminanceHistory.add`
- `add( currentColor.mul( currentWeight ), clampedHistoryColor.mul( historyWeight ) ).div`
- `currentWeight.add`
- `resolve`

**Internal Comments:**
```
// sample a 3x3 neighborhood to create a box in color space (x3)
// clamping the history color with the resulting min/max colors mitigates ghosting (x3)
// find the sample position of the closest depth in the neighborhood (used for velocity) (x3)
// sampling/reprojection (x2)
// clamping (x2)
// flicker reduction based on luminance weighing (x2)
// materials (x5)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const postProcessing = builder.context.postProcessing;

		if ( postProcessing ) {

			this._needsPostProcessingSync = true;

			postProcessing.context.onBeforePostProcessing = () => {

				const size = builder.renderer.getDrawingBufferSize( _size );
				this.setViewOffset( size.width, size.height );

			};

			postProcessing.context.onAfterPostProcessing = () => {

				this.clearViewOffset();

			};

		}

		const historyTexture = texture( this._historyRenderTarget.texture );
		const sampleTexture = this.beautyNode;
		const depthTexture = this.depthNode;
		const velocityTexture = this.velocityNode;

		const resolve = Fn( () => {

			const uvNode = uv();

			const minColor = vec4( 10000 ).toVar();
			const maxColor = vec4( - 10000 ).toVar();
			const closestDepth = float( 1 ).toVar();
			const closestDepthPixelPosition = vec2( 0 ).toVar();

			// sample a 3x3 neighborhood to create a box in color space
			// clamping the history color with the resulting min/max colors mitigates ghosting

			Loop( { start: int( - 1 ), end: int( 1 ), type: 'int', condition: '<=', name: 'x' }, ( { x } ) => {

				Loop( { start: int( - 1 ), end: int( 1 ), type: 'int', condition: '<=', name: 'y' }, ( { y } ) => {

					const uvNeighbor = uvNode.add( vec2( float( x ), float( y ) ).mul( this._invSize ) ).toVar();
					const colorNeighbor = max( vec4( 0 ), sampleTexture.sample( uvNeighbor ) ).toVar(); // use max() to avoid propagate garbage values

					minColor.assign( min( minColor, colorNeighbor ) );
					maxColor.assign( max( maxColor, colorNeighbor ) );

					const currentDepth = depthTexture.sample( uvNeighbor ).r.toVar();

					// find the sample position of the closest depth in the neighborhood (used for velocity)

					If( currentDepth.lessThan( closestDepth ), () => {

						closestDepth.assign( currentDepth );
						closestDepthPixelPosition.assign( uvNeighbor );

					} );

				} );

			} );

			// sampling/reprojection

			const offset = velocityTexture.sample( closestDepthPixelPosition ).xy.mul( vec2( 0.5, - 0.5 ) ); // NDC to uv offset

			const currentColor = sampleTexture.sample( uvNode );
			const historyColor = historyTexture.sample( uvNode.sub( offset ) );

			// clamping

			const clampedHistoryColor = clamp( historyColor, minColor, maxColor );

			// flicker reduction based on luminance weighing

			const currentWeight = float( 0.05 ).toVar();
			const historyWeight = currentWeight.oneMinus().toVar();

			const compressedCurrent = currentColor.mul( float( 1 ).div( ( max( currentColor.r, currentColor.g, currentColor.b ).add( 1.0 ) ) ) );
			const compressedHistory = clampedHistoryColor.mul( float( 1 ).div( ( max( clampedHistoryColor.r, clampedHistoryColor.g, clampedHistoryColor.b ).add( 1.0 ) ) ) );

			const luminanceCurrent = luminance( compressedCurrent.rgb );
			const luminanceHistory = luminance( compressedHistory.rgb );

			currentWeight.mulAssign( float( 1.0 ).div( luminanceCurrent.add( 1 ) ) );
			historyWeight.mulAssign( float( 1.0 ).div( luminanceHistory.add( 1 ) ) );

			return add( currentColor.mul( currentWeight ), clampedHistoryColor.mul( historyWeight ) ).div( max( currentWeight.add( historyWeight ), 0.00001 ) );

		} );

		// materials

		this._resolveMaterial.colorNode = resolve();

		return this._textureNode;

	}
```
</details>

### `TRAANode.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources. This method should be called
	 * when the effect is no longer required.
	 */
```

**Returns:** `void`

**Calls:**

- `this._historyRenderTarget.dispose`
- `this._resolveRenderTarget.dispose`
- `this._resolveMaterial.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this._historyRenderTarget.dispose();
		this._resolveRenderTarget.dispose();

		this._resolveMaterial.dispose();

	}
```
</details>

### `traa(beautyNode: TextureNode, depthNode: TextureNode, velocityNode: TextureNode, camera: Camera): TRAANode`

**Parameters:**

- **`beautyNode`** `TextureNode`
- **`depthNode`** `TextureNode`
- **`velocityNode`** `TextureNode`
- **`camera`** `Camera`

**Returns:** `TRAANode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( beautyNode, depthNode, velocityNode, camera ) => nodeObject( new TRAANode( convertToTexture( beautyNode ), depthNode, velocityNode, camera ) )
```
</details>


---

## Classes

### `TRAANode`

<details><summary>Class Code</summary>

```ts
class TRAANode extends TempNode {

	static get type() {

		return 'TRAANode';

	}

	/**
	 * Constructs a new TRAA node.
	 *
	 * @param {TextureNode} beautyNode - The texture node that represents the input of the effect.
	 * @param {TextureNode} depthNode - A node that represents the scene's depth.
	 * @param {TextureNode} velocityNode - A node that represents the scene's velocity.
	 * @param {Camera} camera - The camera the scene is rendered with.
	 */
	constructor( beautyNode, depthNode, velocityNode, camera ) {

		super( 'vec4' );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isTRAANode = true;

		/**
		 * The `updateBeforeType` is set to `NodeUpdateType.FRAME` since the node renders
		 * its effect once per frame in `updateBefore()`.
		 *
		 * @type {string}
		 * @default 'frame'
		 */
		this.updateBeforeType = NodeUpdateType.FRAME;

		/**
		 * The texture node that represents the input of the effect.
		 *
		 * @type {TextureNode}
		 */
		this.beautyNode = beautyNode;

		/**
		 * A node that represents the scene's velocity.
		 *
		 * @type {TextureNode}
		 */
		this.depthNode = depthNode;

		/**
		 * A node that represents the scene's velocity.
		 *
		 * @type {TextureNode}
		 */
		this.velocityNode = velocityNode;

		/**
		 *  The camera the scene is rendered with.
		 *
		 * @type {TextureNode}
		 */
		this.camera = camera;

		/**
		 * The jitter index selects the current camera offset value.
		 *
		 * @private
		 * @type {number}
		 * @default 0
		 */
		this._jitterIndex = 0;

		/**
		 * A uniform node holding the inverse resolution value.
		 *
		 * @private
		 * @type {UniformNode<vec2>}
		 */
		this._invSize = uniform( new Vector2() );

		/**
		 * The render target that represents the history of frame data.
		 *
		 * @private
		 * @type {?RenderTarget}
		 */
		this._historyRenderTarget = new RenderTarget( 1, 1, { depthBuffer: false, type: HalfFloatType } );
		this._historyRenderTarget.texture.name = 'TRAANode.history';

		/**
		 * The render target for the resolve.
		 *
		 * @private
		 * @type {?RenderTarget}
		 */
		this._resolveRenderTarget = new RenderTarget( 1, 1, { depthBuffer: false, type: HalfFloatType } );
		this._resolveRenderTarget.texture.name = 'TRAANode.resolve';

		/**
		 * Material used for the resolve step.
		 *
		 * @private
		 * @type {NodeMaterial}
		 */
		this._resolveMaterial = new NodeMaterial();
		this._resolveMaterial.name = 'TRAA.resolve';

		/**
		 * The result of the effect is represented as a separate texture node.
		 *
		 * @private
		 * @type {PassTextureNode}
		 */
		this._textureNode = passTexture( this, this._resolveRenderTarget.texture );

		/**
		 * Used to save the original/unjittered projection matrix.
		 *
		 * @private
		 * @type {Matrix4}
		 */
		this._originalProjectionMatrix = new Matrix4();

		/**
		 * Sync the post processing stack with the TRAA node.
		 * @private
		 * @type {boolean}
		 */
		this._needsPostProcessingSync = false;

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

		this._historyRenderTarget.setSize( width, height );
		this._resolveRenderTarget.setSize( width, height );

		this._invSize.value.set( 1 / width, 1 / height );

	}

	/**
	 * Defines the TRAA's current jitter as a view offset
	 * to the scene's camera.
	 *
	 * @param {number} width - The width of the effect.
	 * @param {number} height - The height of the effect.
	 */
	setViewOffset( width, height ) {

		// save original/unjittered projection matrix for velocity pass

		this.camera.updateProjectionMatrix();
		this._originalProjectionMatrix.copy( this.camera.projectionMatrix );

		velocity.setProjectionMatrix( this._originalProjectionMatrix );

		//

		const viewOffset = {

			fullWidth: width,
			fullHeight: height,
			offsetX: 0,
			offsetY: 0,
			width: width,
			height: height

		};

		const jitterOffset = _JitterVectors[ this._jitterIndex ];

		this.camera.setViewOffset(

			viewOffset.fullWidth, viewOffset.fullHeight,

			viewOffset.offsetX + jitterOffset[ 0 ] * 0.0625, viewOffset.offsetY + jitterOffset[ 1 ] * 0.0625, // 0.0625 = 1 / 16

			viewOffset.width, viewOffset.height

		);

	}

	/**
	 * Clears the view offset from the scene's camera.
	 */
	clearViewOffset() {

		this.camera.clearViewOffset();

		velocity.setProjectionMatrix( null );

		// update jitter index

		this._jitterIndex ++;
		this._jitterIndex = this._jitterIndex % ( _JitterVectors.length - 1 );

	}

	/**
	 * This method is used to render the effect once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
	updateBefore( frame ) {

		const { renderer } = frame;

		// keep the TRAA in sync with the dimensions of the beauty node

		const beautyRenderTarget = ( this.beautyNode.isRTTNode ) ? this.beautyNode.renderTarget : this.beautyNode.passNode.renderTarget;

		const width = beautyRenderTarget.texture.width;
		const height = beautyRenderTarget.texture.height;

		//

		if ( this._needsPostProcessingSync === true ) {

			this.setViewOffset( width, height );

			this._needsPostProcessingSync = false;

		}

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		const needsRestart = this._historyRenderTarget.width !== width || this._historyRenderTarget.height !== height;
		this.setSize( width, height );

		// every time when the dimensions change we need fresh history data

		if ( needsRestart === true ) {

			// bind and clear render target to make sure they are initialized after the resize which triggers a dispose()

			renderer.setRenderTarget( this._historyRenderTarget );
			renderer.clear();

			renderer.setRenderTarget( this._resolveRenderTarget );
			renderer.clear();

			// make sure to reset the history with the contents of the beauty buffer otherwise subsequent frames after the
			// resize will fade from a darker color to the correct one because the history was cleared with black.

			renderer.copyTextureToTexture( beautyRenderTarget.texture, this._historyRenderTarget.texture );

		}

		// resolve

		renderer.setRenderTarget( this._resolveRenderTarget );
		_quadMesh.material = this._resolveMaterial;
		_quadMesh.render( renderer );
		renderer.setRenderTarget( null );

		// update history

		renderer.copyTextureToTexture( this._resolveRenderTarget.texture, this._historyRenderTarget.texture );

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}

	/**
	 * This method is used to setup the effect's render targets and TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {PassTextureNode}
	 */
	setup( builder ) {

		const postProcessing = builder.context.postProcessing;

		if ( postProcessing ) {

			this._needsPostProcessingSync = true;

			postProcessing.context.onBeforePostProcessing = () => {

				const size = builder.renderer.getDrawingBufferSize( _size );
				this.setViewOffset( size.width, size.height );

			};

			postProcessing.context.onAfterPostProcessing = () => {

				this.clearViewOffset();

			};

		}

		const historyTexture = texture( this._historyRenderTarget.texture );
		const sampleTexture = this.beautyNode;
		const depthTexture = this.depthNode;
		const velocityTexture = this.velocityNode;

		const resolve = Fn( () => {

			const uvNode = uv();

			const minColor = vec4( 10000 ).toVar();
			const maxColor = vec4( - 10000 ).toVar();
			const closestDepth = float( 1 ).toVar();
			const closestDepthPixelPosition = vec2( 0 ).toVar();

			// sample a 3x3 neighborhood to create a box in color space
			// clamping the history color with the resulting min/max colors mitigates ghosting

			Loop( { start: int( - 1 ), end: int( 1 ), type: 'int', condition: '<=', name: 'x' }, ( { x } ) => {

				Loop( { start: int( - 1 ), end: int( 1 ), type: 'int', condition: '<=', name: 'y' }, ( { y } ) => {

					const uvNeighbor = uvNode.add( vec2( float( x ), float( y ) ).mul( this._invSize ) ).toVar();
					const colorNeighbor = max( vec4( 0 ), sampleTexture.sample( uvNeighbor ) ).toVar(); // use max() to avoid propagate garbage values

					minColor.assign( min( minColor, colorNeighbor ) );
					maxColor.assign( max( maxColor, colorNeighbor ) );

					const currentDepth = depthTexture.sample( uvNeighbor ).r.toVar();

					// find the sample position of the closest depth in the neighborhood (used for velocity)

					If( currentDepth.lessThan( closestDepth ), () => {

						closestDepth.assign( currentDepth );
						closestDepthPixelPosition.assign( uvNeighbor );

					} );

				} );

			} );

			// sampling/reprojection

			const offset = velocityTexture.sample( closestDepthPixelPosition ).xy.mul( vec2( 0.5, - 0.5 ) ); // NDC to uv offset

			const currentColor = sampleTexture.sample( uvNode );
			const historyColor = historyTexture.sample( uvNode.sub( offset ) );

			// clamping

			const clampedHistoryColor = clamp( historyColor, minColor, maxColor );

			// flicker reduction based on luminance weighing

			const currentWeight = float( 0.05 ).toVar();
			const historyWeight = currentWeight.oneMinus().toVar();

			const compressedCurrent = currentColor.mul( float( 1 ).div( ( max( currentColor.r, currentColor.g, currentColor.b ).add( 1.0 ) ) ) );
			const compressedHistory = clampedHistoryColor.mul( float( 1 ).div( ( max( clampedHistoryColor.r, clampedHistoryColor.g, clampedHistoryColor.b ).add( 1.0 ) ) ) );

			const luminanceCurrent = luminance( compressedCurrent.rgb );
			const luminanceHistory = luminance( compressedHistory.rgb );

			currentWeight.mulAssign( float( 1.0 ).div( luminanceCurrent.add( 1 ) ) );
			historyWeight.mulAssign( float( 1.0 ).div( luminanceHistory.add( 1 ) ) );

			return add( currentColor.mul( currentWeight ), clampedHistoryColor.mul( historyWeight ) ).div( max( currentWeight.add( historyWeight ), 0.00001 ) );

		} );

		// materials

		this._resolveMaterial.colorNode = resolve();

		return this._textureNode;

	}

	/**
	 * Frees internal resources. This method should be called
	 * when the effect is no longer required.
	 */
	dispose() {

		this._historyRenderTarget.dispose();
		this._resolveRenderTarget.dispose();

		this._resolveMaterial.dispose();

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

		this._historyRenderTarget.setSize( width, height );
		this._resolveRenderTarget.setSize( width, height );

		this._invSize.value.set( 1 / width, 1 / height );

	}
```
</details>

##### `setViewOffset(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setViewOffset( width, height ) {

		// save original/unjittered projection matrix for velocity pass

		this.camera.updateProjectionMatrix();
		this._originalProjectionMatrix.copy( this.camera.projectionMatrix );

		velocity.setProjectionMatrix( this._originalProjectionMatrix );

		//

		const viewOffset = {

			fullWidth: width,
			fullHeight: height,
			offsetX: 0,
			offsetY: 0,
			width: width,
			height: height

		};

		const jitterOffset = _JitterVectors[ this._jitterIndex ];

		this.camera.setViewOffset(

			viewOffset.fullWidth, viewOffset.fullHeight,

			viewOffset.offsetX + jitterOffset[ 0 ] * 0.0625, viewOffset.offsetY + jitterOffset[ 1 ] * 0.0625, // 0.0625 = 1 / 16

			viewOffset.width, viewOffset.height

		);

	}
```
</details>

##### `clearViewOffset(): void`

<details><summary>Code</summary>

```ts
clearViewOffset() {

		this.camera.clearViewOffset();

		velocity.setProjectionMatrix( null );

		// update jitter index

		this._jitterIndex ++;
		this._jitterIndex = this._jitterIndex % ( _JitterVectors.length - 1 );

	}
```
</details>

##### `updateBefore(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		const { renderer } = frame;

		// keep the TRAA in sync with the dimensions of the beauty node

		const beautyRenderTarget = ( this.beautyNode.isRTTNode ) ? this.beautyNode.renderTarget : this.beautyNode.passNode.renderTarget;

		const width = beautyRenderTarget.texture.width;
		const height = beautyRenderTarget.texture.height;

		//

		if ( this._needsPostProcessingSync === true ) {

			this.setViewOffset( width, height );

			this._needsPostProcessingSync = false;

		}

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		const needsRestart = this._historyRenderTarget.width !== width || this._historyRenderTarget.height !== height;
		this.setSize( width, height );

		// every time when the dimensions change we need fresh history data

		if ( needsRestart === true ) {

			// bind and clear render target to make sure they are initialized after the resize which triggers a dispose()

			renderer.setRenderTarget( this._historyRenderTarget );
			renderer.clear();

			renderer.setRenderTarget( this._resolveRenderTarget );
			renderer.clear();

			// make sure to reset the history with the contents of the beauty buffer otherwise subsequent frames after the
			// resize will fade from a darker color to the correct one because the history was cleared with black.

			renderer.copyTextureToTexture( beautyRenderTarget.texture, this._historyRenderTarget.texture );

		}

		// resolve

		renderer.setRenderTarget( this._resolveRenderTarget );
		_quadMesh.material = this._resolveMaterial;
		_quadMesh.render( renderer );
		renderer.setRenderTarget( null );

		// update history

		renderer.copyTextureToTexture( this._resolveRenderTarget.texture, this._historyRenderTarget.texture );

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

##### `setup(builder: NodeBuilder): PassTextureNode`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const postProcessing = builder.context.postProcessing;

		if ( postProcessing ) {

			this._needsPostProcessingSync = true;

			postProcessing.context.onBeforePostProcessing = () => {

				const size = builder.renderer.getDrawingBufferSize( _size );
				this.setViewOffset( size.width, size.height );

			};

			postProcessing.context.onAfterPostProcessing = () => {

				this.clearViewOffset();

			};

		}

		const historyTexture = texture( this._historyRenderTarget.texture );
		const sampleTexture = this.beautyNode;
		const depthTexture = this.depthNode;
		const velocityTexture = this.velocityNode;

		const resolve = Fn( () => {

			const uvNode = uv();

			const minColor = vec4( 10000 ).toVar();
			const maxColor = vec4( - 10000 ).toVar();
			const closestDepth = float( 1 ).toVar();
			const closestDepthPixelPosition = vec2( 0 ).toVar();

			// sample a 3x3 neighborhood to create a box in color space
			// clamping the history color with the resulting min/max colors mitigates ghosting

			Loop( { start: int( - 1 ), end: int( 1 ), type: 'int', condition: '<=', name: 'x' }, ( { x } ) => {

				Loop( { start: int( - 1 ), end: int( 1 ), type: 'int', condition: '<=', name: 'y' }, ( { y } ) => {

					const uvNeighbor = uvNode.add( vec2( float( x ), float( y ) ).mul( this._invSize ) ).toVar();
					const colorNeighbor = max( vec4( 0 ), sampleTexture.sample( uvNeighbor ) ).toVar(); // use max() to avoid propagate garbage values

					minColor.assign( min( minColor, colorNeighbor ) );
					maxColor.assign( max( maxColor, colorNeighbor ) );

					const currentDepth = depthTexture.sample( uvNeighbor ).r.toVar();

					// find the sample position of the closest depth in the neighborhood (used for velocity)

					If( currentDepth.lessThan( closestDepth ), () => {

						closestDepth.assign( currentDepth );
						closestDepthPixelPosition.assign( uvNeighbor );

					} );

				} );

			} );

			// sampling/reprojection

			const offset = velocityTexture.sample( closestDepthPixelPosition ).xy.mul( vec2( 0.5, - 0.5 ) ); // NDC to uv offset

			const currentColor = sampleTexture.sample( uvNode );
			const historyColor = historyTexture.sample( uvNode.sub( offset ) );

			// clamping

			const clampedHistoryColor = clamp( historyColor, minColor, maxColor );

			// flicker reduction based on luminance weighing

			const currentWeight = float( 0.05 ).toVar();
			const historyWeight = currentWeight.oneMinus().toVar();

			const compressedCurrent = currentColor.mul( float( 1 ).div( ( max( currentColor.r, currentColor.g, currentColor.b ).add( 1.0 ) ) ) );
			const compressedHistory = clampedHistoryColor.mul( float( 1 ).div( ( max( clampedHistoryColor.r, clampedHistoryColor.g, clampedHistoryColor.b ).add( 1.0 ) ) ) );

			const luminanceCurrent = luminance( compressedCurrent.rgb );
			const luminanceHistory = luminance( compressedHistory.rgb );

			currentWeight.mulAssign( float( 1.0 ).div( luminanceCurrent.add( 1 ) ) );
			historyWeight.mulAssign( float( 1.0 ).div( luminanceHistory.add( 1 ) ) );

			return add( currentColor.mul( currentWeight ), clampedHistoryColor.mul( historyWeight ) ).div( max( currentWeight.add( historyWeight ), 0.00001 ) );

		} );

		// materials

		this._resolveMaterial.colorNode = resolve();

		return this._textureNode;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this._historyRenderTarget.dispose();
		this._resolveRenderTarget.dispose();

		this._resolveMaterial.dispose();

	}
```
</details>


---