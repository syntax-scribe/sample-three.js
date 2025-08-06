[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `OutlineNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 30 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/OutlineNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DepthTexture` | `three/webgpu` |
| `FloatType` | `three/webgpu` |
| `RenderTarget` | `three/webgpu` |
| `Vector2` | `three/webgpu` |
| `TempNode` | `three/webgpu` |
| `QuadMesh` | `three/webgpu` |
| `NodeMaterial` | `three/webgpu` |
| `RendererUtils` | `three/webgpu` |
| `NodeUpdateType` | `three/webgpu` |
| `Loop` | `three/tsl` |
| `int` | `three/tsl` |
| `exp` | `three/tsl` |
| `min` | `three/tsl` |
| `float` | `three/tsl` |
| `mul` | `three/tsl` |
| `uv` | `three/tsl` |
| `vec2` | `three/tsl` |
| `vec3` | `three/tsl` |
| `Fn` | `three/tsl` |
| `textureSize` | `three/tsl` |
| `orthographicDepthToViewZ` | `three/tsl` |
| `screenUV` | `three/tsl` |
| `nodeObject` | `three/tsl` |
| `uniform` | `three/tsl` |
| `vec4` | `three/tsl` |
| `passTexture` | `three/tsl` |
| `texture` | `three/tsl` |
| `perspectiveDepthToViewZ` | `three/tsl` |
| `positionView` | `three/tsl` |
| `reference` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_quadMesh` | `any` | let/var | `new QuadMesh()` | ✗ |
| `_size` | `any` | let/var | `new Vector2()` | ✗ |
| `_BLUR_DIRECTION_X` | `any` | let/var | `new Vector2( 1.0, 0.0 )` | ✗ |
| `_BLUR_DIRECTION_Y` | `any` | let/var | `new Vector2( 0.0, 1.0 )` | ✗ |
| `_rendererState` | `any` | let/var | `*not shown*` | ✗ |
| `viewZNode` | `any` | let/var | `*not shown*` | ✗ |
| `MAX_RADIUS` | `4` | let/var | `4` | ✗ |
| `edgeValue1` | `TextureNode` | let/var | `this._edge1TextureUniform` | ✗ |
| `edgeValue2` | `TextureNode` | let/var | `this._edge2TextureUniform` | ✗ |
| `maskColor` | `TextureNode` | let/var | `this._maskTextureUniform` | ✗ |
| `selectedObject` | `Object3D` | let/var | `this.selectedObjects[ i ]` | ✗ |


---

## Functions

### `OutlineNode.getTextureNode(): PassTextureNode`

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

### `OutlineNode.setSize(width: number, height: number): void`

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

- `this._renderTargetDepthBuffer.setSize`
- `this._renderTargetMaskBuffer.setSize`
- `this._renderTargetComposite.setSize`
- `Math.round`
- `this._renderTargetMaskDownSampleBuffer.setSize`
- `this._renderTargetEdgeBuffer1.setSize`
- `this._renderTargetBlurBuffer1.setSize`
- `this._renderTargetEdgeBuffer2.setSize`
- `this._renderTargetBlurBuffer2.setSize`

**Internal Comments:**
```
// downsample 1 (x2)
// downsample 2 (x3)
```

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this._renderTargetDepthBuffer.setSize( width, height );
		this._renderTargetMaskBuffer.setSize( width, height );
		this._renderTargetComposite.setSize( width, height );

		// downsample 1

		let resx = Math.round( width / this.downSampleRatio );
		let resy = Math.round( height / this.downSampleRatio );

		this._renderTargetMaskDownSampleBuffer.setSize( resx, resy );
		this._renderTargetEdgeBuffer1.setSize( resx, resy );
		this._renderTargetBlurBuffer1.setSize( resx, resy );

		// downsample 2

		resx = Math.round( resx / 2 );
		resy = Math.round( resy / 2 );

		this._renderTargetEdgeBuffer2.setSize( resx, resy );
		this._renderTargetBlurBuffer2.setSize( resx, resy );

	}
```
</details>

### `OutlineNode.updateBefore(frame: NodeFrame): void`

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

- `RendererUtils.resetRendererAndSceneState`
- `renderer.getDrawingBufferSize`
- `this.setSize`
- `renderer.setClearColor`
- `this._updateSelectionCache`
- `renderer.setRenderTarget`
- `renderer.setRenderObjectFunction`
- `this._selectionCache.has`
- `renderer.renderObject`
- `renderer.render`
- `this._selectionCache.clear`
- `_quadMesh.render`
- `this._blurDirection.value.copy`
- `RendererUtils.restoreRendererAndSceneState`

**Internal Comments:**
```
// (x10)
// 1. Draw non-selected objects in the depth buffer (x4)
// 2. Draw only the selected objects by comparing the depth buffer of non-selected objects (x4)
// 3. Downsample to (at least) half resolution (x4)
// 4. Perform edge detection (half resolution) (x4)
// 5. Apply blur (half resolution) (x5)
// 6. Apply blur (quarter resolution) (x5)
// 7. Composite (x4)
// restore (x4)
```

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		const { renderer } = frame;
		const { camera, scene } = this;

		_rendererState = RendererUtils.resetRendererAndSceneState( renderer, scene, _rendererState );

		//

		const size = renderer.getDrawingBufferSize( _size );
		this.setSize( size.width, size.height );

		//

		renderer.setClearColor( 0xffffff, 1 );

		this._updateSelectionCache();

		// 1. Draw non-selected objects in the depth buffer

		scene.overrideMaterial = this._depthMaterial;

		renderer.setRenderTarget( this._renderTargetDepthBuffer );
		renderer.setRenderObjectFunction( ( object, ...params ) => {

			if ( this._selectionCache.has( object ) === false ) {

				renderer.renderObject( object, ...params );

			}

		} );

		renderer.render( scene, camera );

		// 2. Draw only the selected objects by comparing the depth buffer of non-selected objects

		scene.overrideMaterial = this._prepareMaskMaterial;

		renderer.setRenderTarget( this._renderTargetMaskBuffer );
		renderer.setRenderObjectFunction( ( object, ...params ) => {

			if ( this._selectionCache.has( object ) === true ) {

				renderer.renderObject( object, ...params );

			}

		} );

		renderer.render( scene, camera );

		//

		renderer.setRenderObjectFunction( _rendererState.renderObjectFunction );

		this._selectionCache.clear();

		// 3. Downsample to (at least) half resolution

		_quadMesh.material = this._materialCopy;
		renderer.setRenderTarget( this._renderTargetMaskDownSampleBuffer );
		_quadMesh.render( renderer );

		// 4. Perform edge detection (half resolution)

		_quadMesh.material = this._edgeDetectionMaterial;
		renderer.setRenderTarget( this._renderTargetEdgeBuffer1 );
		_quadMesh.render( renderer );

		// 5. Apply blur (half resolution)

		this._blurColorTextureUniform.value = this._renderTargetEdgeBuffer1.texture;
		this._blurDirection.value.copy( _BLUR_DIRECTION_X );

		_quadMesh.material = this._separableBlurMaterial;
		renderer.setRenderTarget( this._renderTargetBlurBuffer1 );
		_quadMesh.render( renderer );

		this._blurColorTextureUniform.value = this._renderTargetBlurBuffer1.texture;
		this._blurDirection.value.copy( _BLUR_DIRECTION_Y );

		renderer.setRenderTarget( this._renderTargetEdgeBuffer1 );
		_quadMesh.render( renderer );

		// 6. Apply blur (quarter resolution)

		this._blurColorTextureUniform.value = this._renderTargetEdgeBuffer1.texture;
		this._blurDirection.value.copy( _BLUR_DIRECTION_X );

		_quadMesh.material = this._separableBlurMaterial2;
		renderer.setRenderTarget( this._renderTargetBlurBuffer2 );
		_quadMesh.render( renderer );

		this._blurColorTextureUniform.value = this._renderTargetBlurBuffer2.texture;
		this._blurDirection.value.copy( _BLUR_DIRECTION_Y );

		renderer.setRenderTarget( this._renderTargetEdgeBuffer2 );
		_quadMesh.render( renderer );

		// 7. Composite

		_quadMesh.material = this._compositeMaterial;
		renderer.setRenderTarget( this._renderTargetComposite );
		_quadMesh.render( renderer );

		// restore

		RendererUtils.restoreRendererAndSceneState( renderer, scene, _rendererState );

	}
```
</details>

### `OutlineNode.setup(): PassTextureNode`

**JSDoc:**
```typescript
/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {PassTextureNode}
	 */
```

**Returns:** `PassTextureNode`

**Calls:**

- `this._depthTextureUniform.sample`
- `perspectiveDepthToViewZ (from three/tsl)`
- `orthographicDepthToViewZ (from three/tsl)`
- `positionView.z.lessThanEqual( viewZNode ).select`
- `vec4 (from three/tsl)`
- `prepareMask`
- `Fn (from three/tsl)`
- `textureSize (from three/tsl)`
- `vec2( 1 ).div( resolution ).toVar`
- `vec4( 1.0, 0.0, 0.0, 1.0 ).mul`
- `uv (from three/tsl)`
- `this._maskTextureDownsSampleUniform.sample( uvNode.add( uvOffset.xy ) ).toVar`
- `this._maskTextureDownsSampleUniform.sample( uvNode.sub( uvOffset.xy ) ).toVar`
- `this._maskTextureDownsSampleUniform.sample( uvNode.add( uvOffset.yw ) ).toVar`
- `this._maskTextureDownsSampleUniform.sample( uvNode.sub( uvOffset.yw ) ).toVar`
- `mul (from three/tsl)`
- `c1.r.sub`
- `c3.r.sub`
- `vec2( diff1, diff2 ).length`
- `min (from three/tsl)`
- `visibilityFactor.oneMinus().greaterThan( 0.001 ).select`
- `vec4( edgeColor, 1 ).mul`
- `edgeDetection`
- `float( 0.39894 ).mul`
- `exp( float( - 0.5 ).mul( x ).mul( x ).div( sigma.mul( sigma ) ) ).div`
- `kernelRadius.div( 2 ).toVar`
- `gaussianPdf( 0, sigma ).toVar`
- `this._blurColorTextureUniform.sample( uvNode ).mul( weightSum ).toVar`
- `this._blurDirection.mul( invSize ).mul( kernelRadius ).div( MAX_RADIUS ).toVar`
- `delta.toVar`
- `Loop (from three/tsl)`
- `int (from three/tsl)`
- `kernelRadius.mul( float( i ) ).div`
- `gaussianPdf`
- `this._blurColorTextureUniform.sample`
- `uvNode.add`
- `uvNode.sub`
- `diffuseSum.addAssign`
- `sample1.add( sample2 ).mul`
- `weightSum.addAssign`
- `w.mul`
- `uvOffset.addAssign`
- `diffuseSum.div`
- `separableBlur`
- `edgeValue1.add`
- `edgeValue2.mul`
- `maskColor.r.mul`
- `composite`

**Internal Comments:**
```
// prepare mask material (x2)
// copy material (x5)
// edge detection material (x2)
// separable blur material (x2)
// composite material (x2)
```

<details><summary>Code</summary>

```typescript
setup() {

		// prepare mask material

		const prepareMask = () => {

			const depth = this._depthTextureUniform.sample( screenUV );

			let viewZNode;

			if ( this.camera.isPerspectiveCamera ) {

				viewZNode = perspectiveDepthToViewZ( depth, this._cameraNear, this._cameraFar );

			} else {

				viewZNode = orthographicDepthToViewZ( depth, this._cameraNear, this._cameraFar );

			}

			const depthTest = positionView.z.lessThanEqual( viewZNode ).select( 1, 0 );
			return vec4( 0.0, depthTest, 1.0, 1.0 );

		};

		this._prepareMaskMaterial.fragmentNode = prepareMask();
		this._prepareMaskMaterial.needsUpdate = true;

		// copy material

		this._materialCopy.fragmentNode = this._maskTextureUniform;
		this._materialCopy.needsUpdate = true;

		// edge detection material

		const edgeDetection = Fn( () => {

			const resolution = textureSize( this._maskTextureDownsSampleUniform );
			const invSize = vec2( 1 ).div( resolution ).toVar();
			const uvOffset = vec4( 1.0, 0.0, 0.0, 1.0 ).mul( vec4( invSize, invSize ) );

			const uvNode = uv();
			const c1 = this._maskTextureDownsSampleUniform.sample( uvNode.add( uvOffset.xy ) ).toVar();
			const c2 = this._maskTextureDownsSampleUniform.sample( uvNode.sub( uvOffset.xy ) ).toVar();
			const c3 = this._maskTextureDownsSampleUniform.sample( uvNode.add( uvOffset.yw ) ).toVar();
			const c4 = this._maskTextureDownsSampleUniform.sample( uvNode.sub( uvOffset.yw ) ).toVar();

			const diff1 = mul( c1.r.sub( c2.r ), 0.5 );
			const diff2 = mul( c3.r.sub( c4.r ), 0.5 );
			const d = vec2( diff1, diff2 ).length();
			const a1 = min( c1.g, c2.g );
			const a2 = min( c3.g, c4.g );
			const visibilityFactor = min( a1, a2 );
			const edgeColor = visibilityFactor.oneMinus().greaterThan( 0.001 ).select( this._visibleEdgeColor, this._hiddenEdgeColor );
			return vec4( edgeColor, 1 ).mul( d );

		} );

		this._edgeDetectionMaterial.fragmentNode = edgeDetection();
		this._edgeDetectionMaterial.needsUpdate = true;

		// separable blur material

		const MAX_RADIUS = 4;

		const gaussianPdf = Fn( ( [ x, sigma ] ) => {

			return float( 0.39894 ).mul( exp( float( - 0.5 ).mul( x ).mul( x ).div( sigma.mul( sigma ) ) ).div( sigma ) );

		} );

		const separableBlur = Fn( ( [ kernelRadius ] ) => {

			const resolution = textureSize( this._maskTextureDownsSampleUniform );
			const invSize = vec2( 1 ).div( resolution ).toVar();
			const uvNode = uv();

			const sigma = kernelRadius.div( 2 ).toVar();
			const weightSum = gaussianPdf( 0, sigma ).toVar();
			const diffuseSum = this._blurColorTextureUniform.sample( uvNode ).mul( weightSum ).toVar();
			const delta = this._blurDirection.mul( invSize ).mul( kernelRadius ).div( MAX_RADIUS ).toVar();

			const uvOffset = delta.toVar();

			Loop( { start: int( 1 ), end: int( MAX_RADIUS ), type: 'int', condition: '<=' }, ( { i } ) => {

				const x = kernelRadius.mul( float( i ) ).div( MAX_RADIUS );
				const w = gaussianPdf( x, sigma );
				const sample1 = this._blurColorTextureUniform.sample( uvNode.add( uvOffset ) );
				const sample2 = this._blurColorTextureUniform.sample( uvNode.sub( uvOffset ) );

				diffuseSum.addAssign( sample1.add( sample2 ).mul( w ) );
				weightSum.addAssign( w.mul( 2 ) );
				uvOffset.addAssign( delta );

			} );

			return diffuseSum.div( weightSum );

		} );

		this._separableBlurMaterial.fragmentNode = separableBlur( this.edgeThicknessNode );
		this._separableBlurMaterial.needsUpdate = true;

		this._separableBlurMaterial2.fragmentNode = separableBlur( MAX_RADIUS );
		this._separableBlurMaterial2.needsUpdate = true;

		// composite material

		const composite = Fn( () => {

			const edgeValue1 = this._edge1TextureUniform;
			const edgeValue2 = this._edge2TextureUniform;
			const maskColor = this._maskTextureUniform;

			const edgeValue = edgeValue1.add( edgeValue2.mul( this.edgeGlowNode ) );

			return maskColor.r.mul( edgeValue );

		} );

		this._compositeMaterial.fragmentNode = composite();
		this._compositeMaterial.needsUpdate = true;

		return this._textureNode;

	}
```
</details>

### `OutlineNode.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources. This method should be called
	 * when the effect is no longer required.
	 */
```

**Returns:** `void`

**Calls:**

- `this._renderTargetDepthBuffer.dispose`
- `this._renderTargetMaskBuffer.dispose`
- `this._renderTargetMaskDownSampleBuffer.dispose`
- `this._renderTargetEdgeBuffer1.dispose`
- `this._renderTargetEdgeBuffer2.dispose`
- `this._renderTargetBlurBuffer1.dispose`
- `this._renderTargetBlurBuffer2.dispose`
- `this._renderTargetComposite.dispose`
- `this._depthMaterial.dispose`
- `this._prepareMaskMaterial.dispose`
- `this._materialCopy.dispose`
- `this._edgeDetectionMaterial.dispose`
- `this._separableBlurMaterial.dispose`
- `this._separableBlurMaterial2.dispose`
- `this._compositeMaterial.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.selectedObjects.length = 0;

		this._renderTargetDepthBuffer.dispose();
		this._renderTargetMaskBuffer.dispose();
		this._renderTargetMaskDownSampleBuffer.dispose();
		this._renderTargetEdgeBuffer1.dispose();
		this._renderTargetEdgeBuffer2.dispose();
		this._renderTargetBlurBuffer1.dispose();
		this._renderTargetBlurBuffer2.dispose();
		this._renderTargetComposite.dispose();

		this._depthMaterial.dispose();
		this._prepareMaskMaterial.dispose();
		this._materialCopy.dispose();
		this._edgeDetectionMaterial.dispose();
		this._separableBlurMaterial.dispose();
		this._separableBlurMaterial2.dispose();
		this._compositeMaterial.dispose();

	}
```
</details>

### `OutlineNode._updateSelectionCache(): void`

**JSDoc:**
```typescript
/**
	 * Updates the selection cache based on the selected objects.
	 *
	 * @private
	 */
```

**Returns:** `void`

**Calls:**

- `selectedObject.traverse`
- `this._selectionCache.add`

<details><summary>Code</summary>

```typescript
_updateSelectionCache() {

		for ( let i = 0; i < this.selectedObjects.length; i ++ ) {

			const selectedObject = this.selectedObjects[ i ];
			selectedObject.traverse( ( object ) => {

				if ( object.isMesh ) this._selectionCache.add( object );

			} );

		}

	}
```
</details>

### `prepareMask(): any`

**Returns:** `any`

**Calls:**

- `this._depthTextureUniform.sample`
- `perspectiveDepthToViewZ (from three/tsl)`
- `orthographicDepthToViewZ (from three/tsl)`
- `positionView.z.lessThanEqual( viewZNode ).select`
- `vec4 (from three/tsl)`

<details><summary>Code</summary>

```typescript
() => {

			const depth = this._depthTextureUniform.sample( screenUV );

			let viewZNode;

			if ( this.camera.isPerspectiveCamera ) {

				viewZNode = perspectiveDepthToViewZ( depth, this._cameraNear, this._cameraFar );

			} else {

				viewZNode = orthographicDepthToViewZ( depth, this._cameraNear, this._cameraFar );

			}

			const depthTest = positionView.z.lessThanEqual( viewZNode ).select( 1, 0 );
			return vec4( 0.0, depthTest, 1.0, 1.0 );

		}
```
</details>

### `outline(scene: Scene, camera: Camera, params: { selectedObjects: Object3D[]; edgeThickness?: any; edgeGlow?: any; downSampleRatio?: number; }): OutlineNode`

**Parameters:**

- **`scene`** `Scene`
- **`camera`** `Camera`
- **`params`** `{ selectedObjects: Object3D[]; edgeThickness?: any; edgeGlow?: any; downSampleRatio?: number; }`

**Returns:** `OutlineNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( scene, camera, params ) => nodeObject( new OutlineNode( scene, camera, params ) )
```
</details>


---

## Classes

### `OutlineNode`

<details><summary>Class Code</summary>

```ts
class OutlineNode extends TempNode {

	static get type() {

		return 'OutlineNode';

	}

	/**
	 * Constructs a new outline node.
	 *
	 * @param {Scene} scene - A reference to the scene.
	 * @param {Camera} camera - The camera the scene is rendered with.
	 * @param {Object} params - The configuration parameters.
	 * @param {Array<Object3D>} params.selectedObjects - An array of selected objects.
	 * @param {Node<float>} [params.edgeThickness=float(1)] - The thickness of the edges.
	 * @param {Node<float>} [params.edgeGlow=float(0)] - Can be used for an animated glow/pulse effects.
	 * @param {number} [params.downSampleRatio=2] - The downsample ratio.
	 */
	constructor( scene, camera, params = {} ) {

		super( 'vec4' );

		const {
			selectedObjects = [],
			edgeThickness = float( 1 ),
			edgeGlow = float( 0 ),
			downSampleRatio = 2
		} = params;

		/**
		 * A reference to the scene.
		 *
		 * @type {Scene}
		 */
		this.scene = scene;

		/**
		 * The camera the scene is rendered with.
		 *
		 * @type {Camera}
		 */
		this.camera = camera;

		/**
		 * An array of selected objects.
		 *
		 * @type {Array<Object3D>}
		 */
		this.selectedObjects = selectedObjects;

		/**
		 * The thickness of the edges.
		 *
		 * @type {Node<float>}
		 */
		this.edgeThicknessNode = nodeObject( edgeThickness );

		/**
		 * Can be used for an animated glow/pulse effect.
		 *
		 * @type {Node<float>}
		 */
		this.edgeGlowNode = nodeObject( edgeGlow );

		/**
		 * The downsample ratio.
		 *
		 * @type {number}
		 * @default 2
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

		// render targets

		/**
		 * The render target for the depth pre-pass.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._renderTargetDepthBuffer = new RenderTarget();
		this._renderTargetDepthBuffer.depthTexture = new DepthTexture();
		this._renderTargetDepthBuffer.depthTexture.type = FloatType;

		/**
		 * The render target for the mask pass.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._renderTargetMaskBuffer = new RenderTarget();

		/**
		 * The render target for the mask downsample.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._renderTargetMaskDownSampleBuffer = new RenderTarget( 1, 1, { depthBuffer: false } );

		/**
		 * The first render target for the edge detection.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._renderTargetEdgeBuffer1 = new RenderTarget( 1, 1, { depthBuffer: false } );

		/**
		 * The second render target for the edge detection.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._renderTargetEdgeBuffer2 = new RenderTarget( 1, 1, { depthBuffer: false } );

		/**
		 * The first render target for the blur pass.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._renderTargetBlurBuffer1 = new RenderTarget( 1, 1, { depthBuffer: false } );

		/**
		 * The second render target for the blur pass.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._renderTargetBlurBuffer2 = new RenderTarget( 1, 1, { depthBuffer: false } );

		/**
		 * The render target for the final composite.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._renderTargetComposite = new RenderTarget( 1, 1, { depthBuffer: false } );

		// uniforms

		/**
		 * Represents the near value of the scene's camera.
		 *
		 * @private
		 * @type {ReferenceNode<float>}
		 */
		this._cameraNear = reference( 'near', 'float', camera );

		/**
		 * Represents the far value of the scene's camera.
		 *
		 * @private
		 * @type {ReferenceNode<float>}
		 */
		this._cameraFar = reference( 'far', 'float', camera );

		/**
		 * Uniform that represents the blur direction of the pass.
		 *
		 * @private
		 * @type {UniformNode<vec2>}
		 */
		this._blurDirection = uniform( new Vector2() );

		/**
		 * Texture node that holds the data from the depth pre-pass.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._depthTextureUniform = texture( this._renderTargetDepthBuffer.depthTexture );

		/**
		 * Texture node that holds the data from the mask pass.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._maskTextureUniform = texture( this._renderTargetMaskBuffer.texture );

		/**
		 * Texture node that holds the data from the mask downsample pass.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._maskTextureDownsSampleUniform = texture( this._renderTargetMaskDownSampleBuffer.texture );

		/**
		 * Texture node that holds the data from the first edge detection pass.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._edge1TextureUniform = texture( this._renderTargetEdgeBuffer1.texture );

		/**
		 * Texture node that holds the data from the second edge detection pass.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._edge2TextureUniform = texture( this._renderTargetEdgeBuffer2.texture );

		/**
		 * Texture node that holds the current blurred color data.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._blurColorTextureUniform = texture( this._renderTargetEdgeBuffer1.texture );

		// constants

		/**
		 * Visible edge color.
		 *
		 * @private
		 * @type {Node<vec3>}
		 */
		this._visibleEdgeColor = vec3( 1, 0, 0 );

		/**
		 * Hidden edge color.
		 *
		 * @private
		 * @type {Node<vec3>}
		 */
		this._hiddenEdgeColor = vec3( 0, 1, 0 );

		// materials

		/**
		 * The material for the depth pre-pass.
		 *
		 * @private
		 * @type {NodeMaterial}
		 */
		this._depthMaterial = new NodeMaterial();
		this._depthMaterial.fragmentNode = vec4( 0, 0, 0, 1 );
		this._depthMaterial.name = 'OutlineNode.depth';

		/**
		 * The material for preparing the mask.
		 *
		 * @private
		 * @type {NodeMaterial}
		 */
		this._prepareMaskMaterial = new NodeMaterial();
		this._prepareMaskMaterial.name = 'OutlineNode.prepareMask';

		/**
		 * The copy material
		 *
		 * @private
		 * @type {NodeMaterial}
		 */
		this._materialCopy = new NodeMaterial();
		this._materialCopy.name = 'OutlineNode.copy';

		/**
		 * The edge detection material.
		 *
		 * @private
		 * @type {NodeMaterial}
		 */
		this._edgeDetectionMaterial = new NodeMaterial();
		this._edgeDetectionMaterial.name = 'OutlineNode.edgeDetection';

		/**
		 * The material that is used to render in the blur pass.
		 *
		 * @private
		 * @type {NodeMaterial}
		 */
		this._separableBlurMaterial = new NodeMaterial();
		this._separableBlurMaterial.name = 'OutlineNode.separableBlur';

		/**
		 * The material that is used to render in the blur pass.
		 *
		 * @private
		 * @type {NodeMaterial}
		 */
		this._separableBlurMaterial2 = new NodeMaterial();
		this._separableBlurMaterial2.name = 'OutlineNode.separableBlur2';

		/**
		 * The final composite material.
		 *
		 * @private
		 * @type {NodeMaterial}
		 */
		this._compositeMaterial = new NodeMaterial();
		this._compositeMaterial.name = 'OutlineNode.composite';

		/**
		 * A set to cache selected objects in the scene.
		 *
		 * @private
		 * @type {Set<Object3D>}
		 */
		this._selectionCache = new Set();

		/**
		 * The result of the effect is represented as a separate texture node.
		 *
		 * @private
		 * @type {PassTextureNode}
		 */
		this._textureNode = passTexture( this, this._renderTargetComposite.texture );

	}

	/**
	 * A mask value that represents the visible edge.
	 *
	 * @return {Node<float>} The visible edge.
	 */
	get visibleEdge() {

		return this.r;

	}

	/**
	 * A mask value that represents the hidden edge.
	 *
	 * @return {Node<float>} The hidden edge.
	 */
	get hiddenEdge() {

		return this.g;

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

		this._renderTargetDepthBuffer.setSize( width, height );
		this._renderTargetMaskBuffer.setSize( width, height );
		this._renderTargetComposite.setSize( width, height );

		// downsample 1

		let resx = Math.round( width / this.downSampleRatio );
		let resy = Math.round( height / this.downSampleRatio );

		this._renderTargetMaskDownSampleBuffer.setSize( resx, resy );
		this._renderTargetEdgeBuffer1.setSize( resx, resy );
		this._renderTargetBlurBuffer1.setSize( resx, resy );

		// downsample 2

		resx = Math.round( resx / 2 );
		resy = Math.round( resy / 2 );

		this._renderTargetEdgeBuffer2.setSize( resx, resy );
		this._renderTargetBlurBuffer2.setSize( resx, resy );

	}

	/**
	 * This method is used to render the effect once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
	updateBefore( frame ) {

		const { renderer } = frame;
		const { camera, scene } = this;

		_rendererState = RendererUtils.resetRendererAndSceneState( renderer, scene, _rendererState );

		//

		const size = renderer.getDrawingBufferSize( _size );
		this.setSize( size.width, size.height );

		//

		renderer.setClearColor( 0xffffff, 1 );

		this._updateSelectionCache();

		// 1. Draw non-selected objects in the depth buffer

		scene.overrideMaterial = this._depthMaterial;

		renderer.setRenderTarget( this._renderTargetDepthBuffer );
		renderer.setRenderObjectFunction( ( object, ...params ) => {

			if ( this._selectionCache.has( object ) === false ) {

				renderer.renderObject( object, ...params );

			}

		} );

		renderer.render( scene, camera );

		// 2. Draw only the selected objects by comparing the depth buffer of non-selected objects

		scene.overrideMaterial = this._prepareMaskMaterial;

		renderer.setRenderTarget( this._renderTargetMaskBuffer );
		renderer.setRenderObjectFunction( ( object, ...params ) => {

			if ( this._selectionCache.has( object ) === true ) {

				renderer.renderObject( object, ...params );

			}

		} );

		renderer.render( scene, camera );

		//

		renderer.setRenderObjectFunction( _rendererState.renderObjectFunction );

		this._selectionCache.clear();

		// 3. Downsample to (at least) half resolution

		_quadMesh.material = this._materialCopy;
		renderer.setRenderTarget( this._renderTargetMaskDownSampleBuffer );
		_quadMesh.render( renderer );

		// 4. Perform edge detection (half resolution)

		_quadMesh.material = this._edgeDetectionMaterial;
		renderer.setRenderTarget( this._renderTargetEdgeBuffer1 );
		_quadMesh.render( renderer );

		// 5. Apply blur (half resolution)

		this._blurColorTextureUniform.value = this._renderTargetEdgeBuffer1.texture;
		this._blurDirection.value.copy( _BLUR_DIRECTION_X );

		_quadMesh.material = this._separableBlurMaterial;
		renderer.setRenderTarget( this._renderTargetBlurBuffer1 );
		_quadMesh.render( renderer );

		this._blurColorTextureUniform.value = this._renderTargetBlurBuffer1.texture;
		this._blurDirection.value.copy( _BLUR_DIRECTION_Y );

		renderer.setRenderTarget( this._renderTargetEdgeBuffer1 );
		_quadMesh.render( renderer );

		// 6. Apply blur (quarter resolution)

		this._blurColorTextureUniform.value = this._renderTargetEdgeBuffer1.texture;
		this._blurDirection.value.copy( _BLUR_DIRECTION_X );

		_quadMesh.material = this._separableBlurMaterial2;
		renderer.setRenderTarget( this._renderTargetBlurBuffer2 );
		_quadMesh.render( renderer );

		this._blurColorTextureUniform.value = this._renderTargetBlurBuffer2.texture;
		this._blurDirection.value.copy( _BLUR_DIRECTION_Y );

		renderer.setRenderTarget( this._renderTargetEdgeBuffer2 );
		_quadMesh.render( renderer );

		// 7. Composite

		_quadMesh.material = this._compositeMaterial;
		renderer.setRenderTarget( this._renderTargetComposite );
		_quadMesh.render( renderer );

		// restore

		RendererUtils.restoreRendererAndSceneState( renderer, scene, _rendererState );

	}

	/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {PassTextureNode}
	 */
	setup() {

		// prepare mask material

		const prepareMask = () => {

			const depth = this._depthTextureUniform.sample( screenUV );

			let viewZNode;

			if ( this.camera.isPerspectiveCamera ) {

				viewZNode = perspectiveDepthToViewZ( depth, this._cameraNear, this._cameraFar );

			} else {

				viewZNode = orthographicDepthToViewZ( depth, this._cameraNear, this._cameraFar );

			}

			const depthTest = positionView.z.lessThanEqual( viewZNode ).select( 1, 0 );
			return vec4( 0.0, depthTest, 1.0, 1.0 );

		};

		this._prepareMaskMaterial.fragmentNode = prepareMask();
		this._prepareMaskMaterial.needsUpdate = true;

		// copy material

		this._materialCopy.fragmentNode = this._maskTextureUniform;
		this._materialCopy.needsUpdate = true;

		// edge detection material

		const edgeDetection = Fn( () => {

			const resolution = textureSize( this._maskTextureDownsSampleUniform );
			const invSize = vec2( 1 ).div( resolution ).toVar();
			const uvOffset = vec4( 1.0, 0.0, 0.0, 1.0 ).mul( vec4( invSize, invSize ) );

			const uvNode = uv();
			const c1 = this._maskTextureDownsSampleUniform.sample( uvNode.add( uvOffset.xy ) ).toVar();
			const c2 = this._maskTextureDownsSampleUniform.sample( uvNode.sub( uvOffset.xy ) ).toVar();
			const c3 = this._maskTextureDownsSampleUniform.sample( uvNode.add( uvOffset.yw ) ).toVar();
			const c4 = this._maskTextureDownsSampleUniform.sample( uvNode.sub( uvOffset.yw ) ).toVar();

			const diff1 = mul( c1.r.sub( c2.r ), 0.5 );
			const diff2 = mul( c3.r.sub( c4.r ), 0.5 );
			const d = vec2( diff1, diff2 ).length();
			const a1 = min( c1.g, c2.g );
			const a2 = min( c3.g, c4.g );
			const visibilityFactor = min( a1, a2 );
			const edgeColor = visibilityFactor.oneMinus().greaterThan( 0.001 ).select( this._visibleEdgeColor, this._hiddenEdgeColor );
			return vec4( edgeColor, 1 ).mul( d );

		} );

		this._edgeDetectionMaterial.fragmentNode = edgeDetection();
		this._edgeDetectionMaterial.needsUpdate = true;

		// separable blur material

		const MAX_RADIUS = 4;

		const gaussianPdf = Fn( ( [ x, sigma ] ) => {

			return float( 0.39894 ).mul( exp( float( - 0.5 ).mul( x ).mul( x ).div( sigma.mul( sigma ) ) ).div( sigma ) );

		} );

		const separableBlur = Fn( ( [ kernelRadius ] ) => {

			const resolution = textureSize( this._maskTextureDownsSampleUniform );
			const invSize = vec2( 1 ).div( resolution ).toVar();
			const uvNode = uv();

			const sigma = kernelRadius.div( 2 ).toVar();
			const weightSum = gaussianPdf( 0, sigma ).toVar();
			const diffuseSum = this._blurColorTextureUniform.sample( uvNode ).mul( weightSum ).toVar();
			const delta = this._blurDirection.mul( invSize ).mul( kernelRadius ).div( MAX_RADIUS ).toVar();

			const uvOffset = delta.toVar();

			Loop( { start: int( 1 ), end: int( MAX_RADIUS ), type: 'int', condition: '<=' }, ( { i } ) => {

				const x = kernelRadius.mul( float( i ) ).div( MAX_RADIUS );
				const w = gaussianPdf( x, sigma );
				const sample1 = this._blurColorTextureUniform.sample( uvNode.add( uvOffset ) );
				const sample2 = this._blurColorTextureUniform.sample( uvNode.sub( uvOffset ) );

				diffuseSum.addAssign( sample1.add( sample2 ).mul( w ) );
				weightSum.addAssign( w.mul( 2 ) );
				uvOffset.addAssign( delta );

			} );

			return diffuseSum.div( weightSum );

		} );

		this._separableBlurMaterial.fragmentNode = separableBlur( this.edgeThicknessNode );
		this._separableBlurMaterial.needsUpdate = true;

		this._separableBlurMaterial2.fragmentNode = separableBlur( MAX_RADIUS );
		this._separableBlurMaterial2.needsUpdate = true;

		// composite material

		const composite = Fn( () => {

			const edgeValue1 = this._edge1TextureUniform;
			const edgeValue2 = this._edge2TextureUniform;
			const maskColor = this._maskTextureUniform;

			const edgeValue = edgeValue1.add( edgeValue2.mul( this.edgeGlowNode ) );

			return maskColor.r.mul( edgeValue );

		} );

		this._compositeMaterial.fragmentNode = composite();
		this._compositeMaterial.needsUpdate = true;

		return this._textureNode;

	}

	/**
	 * Frees internal resources. This method should be called
	 * when the effect is no longer required.
	 */
	dispose() {

		this.selectedObjects.length = 0;

		this._renderTargetDepthBuffer.dispose();
		this._renderTargetMaskBuffer.dispose();
		this._renderTargetMaskDownSampleBuffer.dispose();
		this._renderTargetEdgeBuffer1.dispose();
		this._renderTargetEdgeBuffer2.dispose();
		this._renderTargetBlurBuffer1.dispose();
		this._renderTargetBlurBuffer2.dispose();
		this._renderTargetComposite.dispose();

		this._depthMaterial.dispose();
		this._prepareMaskMaterial.dispose();
		this._materialCopy.dispose();
		this._edgeDetectionMaterial.dispose();
		this._separableBlurMaterial.dispose();
		this._separableBlurMaterial2.dispose();
		this._compositeMaterial.dispose();

	}

	/**
	 * Updates the selection cache based on the selected objects.
	 *
	 * @private
	 */
	_updateSelectionCache() {

		for ( let i = 0; i < this.selectedObjects.length; i ++ ) {

			const selectedObject = this.selectedObjects[ i ];
			selectedObject.traverse( ( object ) => {

				if ( object.isMesh ) this._selectionCache.add( object );

			} );

		}

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

		this._renderTargetDepthBuffer.setSize( width, height );
		this._renderTargetMaskBuffer.setSize( width, height );
		this._renderTargetComposite.setSize( width, height );

		// downsample 1

		let resx = Math.round( width / this.downSampleRatio );
		let resy = Math.round( height / this.downSampleRatio );

		this._renderTargetMaskDownSampleBuffer.setSize( resx, resy );
		this._renderTargetEdgeBuffer1.setSize( resx, resy );
		this._renderTargetBlurBuffer1.setSize( resx, resy );

		// downsample 2

		resx = Math.round( resx / 2 );
		resy = Math.round( resy / 2 );

		this._renderTargetEdgeBuffer2.setSize( resx, resy );
		this._renderTargetBlurBuffer2.setSize( resx, resy );

	}
```
</details>

##### `updateBefore(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		const { renderer } = frame;
		const { camera, scene } = this;

		_rendererState = RendererUtils.resetRendererAndSceneState( renderer, scene, _rendererState );

		//

		const size = renderer.getDrawingBufferSize( _size );
		this.setSize( size.width, size.height );

		//

		renderer.setClearColor( 0xffffff, 1 );

		this._updateSelectionCache();

		// 1. Draw non-selected objects in the depth buffer

		scene.overrideMaterial = this._depthMaterial;

		renderer.setRenderTarget( this._renderTargetDepthBuffer );
		renderer.setRenderObjectFunction( ( object, ...params ) => {

			if ( this._selectionCache.has( object ) === false ) {

				renderer.renderObject( object, ...params );

			}

		} );

		renderer.render( scene, camera );

		// 2. Draw only the selected objects by comparing the depth buffer of non-selected objects

		scene.overrideMaterial = this._prepareMaskMaterial;

		renderer.setRenderTarget( this._renderTargetMaskBuffer );
		renderer.setRenderObjectFunction( ( object, ...params ) => {

			if ( this._selectionCache.has( object ) === true ) {

				renderer.renderObject( object, ...params );

			}

		} );

		renderer.render( scene, camera );

		//

		renderer.setRenderObjectFunction( _rendererState.renderObjectFunction );

		this._selectionCache.clear();

		// 3. Downsample to (at least) half resolution

		_quadMesh.material = this._materialCopy;
		renderer.setRenderTarget( this._renderTargetMaskDownSampleBuffer );
		_quadMesh.render( renderer );

		// 4. Perform edge detection (half resolution)

		_quadMesh.material = this._edgeDetectionMaterial;
		renderer.setRenderTarget( this._renderTargetEdgeBuffer1 );
		_quadMesh.render( renderer );

		// 5. Apply blur (half resolution)

		this._blurColorTextureUniform.value = this._renderTargetEdgeBuffer1.texture;
		this._blurDirection.value.copy( _BLUR_DIRECTION_X );

		_quadMesh.material = this._separableBlurMaterial;
		renderer.setRenderTarget( this._renderTargetBlurBuffer1 );
		_quadMesh.render( renderer );

		this._blurColorTextureUniform.value = this._renderTargetBlurBuffer1.texture;
		this._blurDirection.value.copy( _BLUR_DIRECTION_Y );

		renderer.setRenderTarget( this._renderTargetEdgeBuffer1 );
		_quadMesh.render( renderer );

		// 6. Apply blur (quarter resolution)

		this._blurColorTextureUniform.value = this._renderTargetEdgeBuffer1.texture;
		this._blurDirection.value.copy( _BLUR_DIRECTION_X );

		_quadMesh.material = this._separableBlurMaterial2;
		renderer.setRenderTarget( this._renderTargetBlurBuffer2 );
		_quadMesh.render( renderer );

		this._blurColorTextureUniform.value = this._renderTargetBlurBuffer2.texture;
		this._blurDirection.value.copy( _BLUR_DIRECTION_Y );

		renderer.setRenderTarget( this._renderTargetEdgeBuffer2 );
		_quadMesh.render( renderer );

		// 7. Composite

		_quadMesh.material = this._compositeMaterial;
		renderer.setRenderTarget( this._renderTargetComposite );
		_quadMesh.render( renderer );

		// restore

		RendererUtils.restoreRendererAndSceneState( renderer, scene, _rendererState );

	}
```
</details>

##### `setup(): PassTextureNode`

<details><summary>Code</summary>

```ts
setup() {

		// prepare mask material

		const prepareMask = () => {

			const depth = this._depthTextureUniform.sample( screenUV );

			let viewZNode;

			if ( this.camera.isPerspectiveCamera ) {

				viewZNode = perspectiveDepthToViewZ( depth, this._cameraNear, this._cameraFar );

			} else {

				viewZNode = orthographicDepthToViewZ( depth, this._cameraNear, this._cameraFar );

			}

			const depthTest = positionView.z.lessThanEqual( viewZNode ).select( 1, 0 );
			return vec4( 0.0, depthTest, 1.0, 1.0 );

		};

		this._prepareMaskMaterial.fragmentNode = prepareMask();
		this._prepareMaskMaterial.needsUpdate = true;

		// copy material

		this._materialCopy.fragmentNode = this._maskTextureUniform;
		this._materialCopy.needsUpdate = true;

		// edge detection material

		const edgeDetection = Fn( () => {

			const resolution = textureSize( this._maskTextureDownsSampleUniform );
			const invSize = vec2( 1 ).div( resolution ).toVar();
			const uvOffset = vec4( 1.0, 0.0, 0.0, 1.0 ).mul( vec4( invSize, invSize ) );

			const uvNode = uv();
			const c1 = this._maskTextureDownsSampleUniform.sample( uvNode.add( uvOffset.xy ) ).toVar();
			const c2 = this._maskTextureDownsSampleUniform.sample( uvNode.sub( uvOffset.xy ) ).toVar();
			const c3 = this._maskTextureDownsSampleUniform.sample( uvNode.add( uvOffset.yw ) ).toVar();
			const c4 = this._maskTextureDownsSampleUniform.sample( uvNode.sub( uvOffset.yw ) ).toVar();

			const diff1 = mul( c1.r.sub( c2.r ), 0.5 );
			const diff2 = mul( c3.r.sub( c4.r ), 0.5 );
			const d = vec2( diff1, diff2 ).length();
			const a1 = min( c1.g, c2.g );
			const a2 = min( c3.g, c4.g );
			const visibilityFactor = min( a1, a2 );
			const edgeColor = visibilityFactor.oneMinus().greaterThan( 0.001 ).select( this._visibleEdgeColor, this._hiddenEdgeColor );
			return vec4( edgeColor, 1 ).mul( d );

		} );

		this._edgeDetectionMaterial.fragmentNode = edgeDetection();
		this._edgeDetectionMaterial.needsUpdate = true;

		// separable blur material

		const MAX_RADIUS = 4;

		const gaussianPdf = Fn( ( [ x, sigma ] ) => {

			return float( 0.39894 ).mul( exp( float( - 0.5 ).mul( x ).mul( x ).div( sigma.mul( sigma ) ) ).div( sigma ) );

		} );

		const separableBlur = Fn( ( [ kernelRadius ] ) => {

			const resolution = textureSize( this._maskTextureDownsSampleUniform );
			const invSize = vec2( 1 ).div( resolution ).toVar();
			const uvNode = uv();

			const sigma = kernelRadius.div( 2 ).toVar();
			const weightSum = gaussianPdf( 0, sigma ).toVar();
			const diffuseSum = this._blurColorTextureUniform.sample( uvNode ).mul( weightSum ).toVar();
			const delta = this._blurDirection.mul( invSize ).mul( kernelRadius ).div( MAX_RADIUS ).toVar();

			const uvOffset = delta.toVar();

			Loop( { start: int( 1 ), end: int( MAX_RADIUS ), type: 'int', condition: '<=' }, ( { i } ) => {

				const x = kernelRadius.mul( float( i ) ).div( MAX_RADIUS );
				const w = gaussianPdf( x, sigma );
				const sample1 = this._blurColorTextureUniform.sample( uvNode.add( uvOffset ) );
				const sample2 = this._blurColorTextureUniform.sample( uvNode.sub( uvOffset ) );

				diffuseSum.addAssign( sample1.add( sample2 ).mul( w ) );
				weightSum.addAssign( w.mul( 2 ) );
				uvOffset.addAssign( delta );

			} );

			return diffuseSum.div( weightSum );

		} );

		this._separableBlurMaterial.fragmentNode = separableBlur( this.edgeThicknessNode );
		this._separableBlurMaterial.needsUpdate = true;

		this._separableBlurMaterial2.fragmentNode = separableBlur( MAX_RADIUS );
		this._separableBlurMaterial2.needsUpdate = true;

		// composite material

		const composite = Fn( () => {

			const edgeValue1 = this._edge1TextureUniform;
			const edgeValue2 = this._edge2TextureUniform;
			const maskColor = this._maskTextureUniform;

			const edgeValue = edgeValue1.add( edgeValue2.mul( this.edgeGlowNode ) );

			return maskColor.r.mul( edgeValue );

		} );

		this._compositeMaterial.fragmentNode = composite();
		this._compositeMaterial.needsUpdate = true;

		return this._textureNode;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.selectedObjects.length = 0;

		this._renderTargetDepthBuffer.dispose();
		this._renderTargetMaskBuffer.dispose();
		this._renderTargetMaskDownSampleBuffer.dispose();
		this._renderTargetEdgeBuffer1.dispose();
		this._renderTargetEdgeBuffer2.dispose();
		this._renderTargetBlurBuffer1.dispose();
		this._renderTargetBlurBuffer2.dispose();
		this._renderTargetComposite.dispose();

		this._depthMaterial.dispose();
		this._prepareMaskMaterial.dispose();
		this._materialCopy.dispose();
		this._edgeDetectionMaterial.dispose();
		this._separableBlurMaterial.dispose();
		this._separableBlurMaterial2.dispose();
		this._compositeMaterial.dispose();

	}
```
</details>

##### `_updateSelectionCache(): void`

<details><summary>Code</summary>

```ts
_updateSelectionCache() {

		for ( let i = 0; i < this.selectedObjects.length; i ++ ) {

			const selectedObject = this.selectedObjects[ i ];
			selectedObject.traverse( ( object ) => {

				if ( object.isMesh ) this._selectionCache.add( object );

			} );

		}

	}
```
</details>


---