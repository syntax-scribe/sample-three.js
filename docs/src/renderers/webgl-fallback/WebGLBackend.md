[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLBackend.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 65 |
| 🧱 Classes | 1 |
| 📦 Imports | 14 |
| 📊 Variables & Constants | 124 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgl-fallback/WebGLBackend.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `GLSLNodeBuilder` | `./nodes/GLSLNodeBuilder.js` |
| `Backend` | `../common/Backend.js` |
| `getCacheKey` | `../common/RenderContext.js` |
| `WebGLAttributeUtils` | `./utils/WebGLAttributeUtils.js` |
| `WebGLState` | `./utils/WebGLState.js` |
| `WebGLUtils` | `./utils/WebGLUtils.js` |
| `WebGLTextureUtils` | `./utils/WebGLTextureUtils.js` |
| `WebGLExtensions` | `./utils/WebGLExtensions.js` |
| `WebGLCapabilities` | `./utils/WebGLCapabilities.js` |
| `GLFeatureName` | `./utils/WebGLConstants.js` |
| `WebGLBufferRenderer` | `./WebGLBufferRenderer.js` |
| `warnOnce` | `../../utils.js` |
| `WebGLCoordinateSystem` | `../../constants.js` |
| `WebGLTimestampQueryPool` | `./utils/WebGLTimestampQueryPool.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `parameters` | `any` | let/var | `this.parameters` | ✗ |
| `contextAttributes` | `{ antialias: boolean; alpha: boolean;...` | let/var | `{ antialias: renderer.samples > 0, alpha: true, // always true for performanc...` | ✗ |
| `glContext` | `any` | let/var | `( parameters.context !== undefined ) ? parameters.context : renderer.domEleme...` | ✗ |
| `contextLossInfo` | `{ api: string; message: any; reason: ...` | let/var | `{ api: 'WebGL', message: event.statusMessage \|\| 'Unknown reason', reason: n...` | ✗ |
| `gl` | `WebGL2RenderingContext` | let/var | `this.gl` | ✗ |
| `glInternalFormat` | `35056 \| 33190` | let/var | `renderTarget.stencilBuffer ? gl.DEPTH24_STENCIL8 : gl.DEPTH_COMPONENT24` | ✗ |
| `type` | `"compute" \| "render"` | let/var | `renderContext.isComputeNode ? 'compute' : 'render'` | ✗ |
| `timestampQueryPool` | `any` | let/var | `this.timestampQueryPool[ type ]` | ✗ |
| `type` | `"compute" \| "render"` | let/var | `renderContext.isComputeNode ? 'compute' : 'render'` | ✗ |
| `timestampQueryPool` | `any` | let/var | `this.timestampQueryPool[ type ]` | ✗ |
| `occlusionQueryCount` | `any` | let/var | `renderContext.occlusionQueryCount` | ✗ |
| `previousContext` | `any` | let/var | `renderContextData.previousContext` | ✗ |
| `occlusionQueryCount` | `any` | let/var | `renderContext.occlusionQueryCount` | ✗ |
| `textures` | `any` | let/var | `renderContext.textures` | ✗ |
| `texture` | `any` | let/var | `textures[ i ]` | ✗ |
| `renderTarget` | `any` | let/var | `renderContext.renderTarget` | ✗ |
| `fb` | `any` | let/var | `renderTargetContextData.framebuffers[ renderContext.getCacheKey() ]` | ✗ |
| `mask` | `16384` | let/var | `gl.COLOR_BUFFER_BIT` | ✗ |
| `msaaFrameBuffer` | `any` | let/var | `renderTargetContextData.msaaFrameBuffer` | ✗ |
| `msaaRenderbuffers` | `any` | let/var | `renderTargetContextData.msaaRenderbuffers` | ✗ |
| `textures` | `any` | let/var | `renderContext.textures` | ✗ |
| `isMRT` | `boolean` | let/var | `textures.length > 1` | ✗ |
| `viewY` | `number` | let/var | `renderContext.height - height - y` | ✗ |
| `fb` | `any` | let/var | `renderTargetContextData.framebuffers[ renderContext.getCacheKey() ]` | ✗ |
| `occluded` | `WeakSet<WeakKey>` | let/var | `new WeakSet()` | ✗ |
| `completed` | `number` | let/var | `0` | ✗ |
| `query` | `any` | let/var | `currentOcclusionQueries[ i ]` | ✗ |
| `state` | `WebGLState` | let/var | `this.state` | ✗ |
| `clear` | `number` | let/var | `0` | ✗ |
| `clearColor` | `any` | let/var | `*not shown*` | ✗ |
| `vaoGPU` | `WebGLVertexArrayObject` | let/var | `this.vaoCache[ vaoKey ]` | ✗ |
| `dualAttributeData` | `any` | let/var | `transformBuffers[ i ]` | ✗ |
| `gl` | `WebGL2RenderingContext` | let/var | `this.gl` | ✗ |
| `frontFaceCW` | `boolean` | let/var | `( object.isMesh && object.matrixWorld.determinant() < 0 )` | ✗ |
| `vaoGPU` | `any` | let/var | `attributesData.vaoGPU` | ✗ |
| `indexGPU` | `any` | let/var | `( index !== null ) ? this.get( index ).bufferGPU : null` | ✗ |
| `lastObject` | `any` | let/var | `contextData.lastOcclusionObject` | ✗ |
| `renderer` | `WebGLBufferRenderer` | let/var | `this.bufferRenderer` | ✗ |
| `cameras` | `any` | let/var | `renderObject.camera.cameras` | ✗ |
| `cameraIndex` | `any` | let/var | `renderObject.getBindingGroup( 'cameraIndex' ).bindings[ 0 ]` | ✗ |
| `data` | `Uint32Array<ArrayBuffer>` | let/var | `new Uint32Array( [ 0, 0, 0, 0 ] )` | ✗ |
| `indexesGPU` | `any[]` | let/var | `[]` | ✗ |
| `renderTarget` | `any` | let/var | `this._currentContext.renderTarget` | ✗ |
| `prevActiveCubeFace` | `any` | let/var | `this._currentContext.activeCubeFace` | ✗ |
| `subCamera` | `any` | let/var | `cameras[ i ]` | ✗ |
| `vp` | `any` | let/var | `subCamera.viewport` | ✗ |
| `x` | `number` | let/var | `vp.x * pixelRatio` | ✗ |
| `y` | `number` | let/var | `vp.y * pixelRatio` | ✗ |
| `width` | `number` | let/var | `vp.width * pixelRatio` | ✗ |
| `height` | `number` | let/var | `vp.height * pixelRatio` | ✗ |
| `gl` | `WebGL2RenderingContext` | let/var | `this.gl` | ✗ |
| `shader` | `WebGLShader` | let/var | `stage === 'fragment' ? gl.createShader( gl.FRAGMENT_SHADER ) : gl.createShade...` | ✗ |
| `gl` | `WebGL2RenderingContext` | let/var | `this.gl` | ✗ |
| `pipeline` | `any` | let/var | `renderObject.pipeline` | ✗ |
| `fragmentShader` | `any` | let/var | `this.get( fragmentProgram ).shaderGPU` | ✗ |
| `vertexShader` | `any` | let/var | `this.get( vertexProgram ).shaderGPU` | ✗ |
| `parallel` | `KHRParallelShaderCompile` | let/var | `this.parallel` | ✗ |
| `p` | `Promise<any>` | let/var | `new Promise( ( resolve /*, reject*/ ) => { const parallel = this.parallel; co...` | ✗ |
| `lines2` | `any[]` | let/var | `[]` | ✗ |
| `line` | `number` | let/var | `i + 1` | ✗ |
| `shaderInfoLog` | `string` | let/var | `gl.getShaderInfoLog( shader ) \|\| ''` | ✗ |
| `gl` | `WebGL2RenderingContext` | let/var | `this.gl` | ✗ |
| `programInfoLog` | `string` | let/var | `gl.getProgramInfoLog( programGPU ) \|\| ''` | ✗ |
| `fragmentProgram` | `{ stage: string; code: string; }` | let/var | `{ stage: 'fragment', code: '#version 300 es\nprecision highp float;\nvoid mai...` | ✗ |
| `fragmentShader` | `any` | let/var | `this.get( fragmentProgram ).shaderGPU` | ✗ |
| `vertexShader` | `any` | let/var | `this.get( computeProgram ).shaderGPU` | ✗ |
| `transforms` | `any` | let/var | `computeProgram.transforms` | ✗ |
| `transformVaryingNames` | `any[]` | let/var | `[]` | ✗ |
| `transformAttributeNodes` | `any[]` | let/var | `[]` | ✗ |
| `transform` | `any` | let/var | `transforms[ i ]` | ✗ |
| `attributeNodes` | `any` | let/var | `computeProgram.attributes` | ✗ |
| `attributes` | `any[]` | let/var | `[]` | ✗ |
| `transformBuffers` | `any[]` | let/var | `[]` | ✗ |
| `attribute` | `any` | let/var | `attributeNodes[ i ].node.attribute` | ✗ |
| `attribute` | `any` | let/var | `transformAttributeNodes[ i ].attribute` | ✗ |
| `uniformBuffers` | `number` | let/var | `0` | ✗ |
| `textures` | `number` | let/var | `0` | ✗ |
| `i` | `any` | let/var | `bindGroupData.uniformBuffers` | ✗ |
| `t` | `any` | let/var | `bindGroupData.textures` | ✗ |
| `data` | `any` | let/var | `binding.buffer` | ✗ |
| `gl` | `WebGL2RenderingContext` | let/var | `this.gl` | ✗ |
| `bufferGPU` | `any` | let/var | `bindingData.bufferGPU` | ✗ |
| `data` | `ArrayBufferLike` | let/var | `binding.buffer` | ✗ |
| `gl` | `WebGL2RenderingContext` | let/var | `this.gl` | ✗ |
| `gl` | `WebGL2RenderingContext` | let/var | `this.gl` | ✗ |
| `gl` | `WebGL2RenderingContext` | let/var | `this.gl` | ✗ |
| `extensions` | `WebGLExtensions` | let/var | `this.extensions` | ✗ |
| `currentFrameBuffer` | `any` | let/var | `null` | ✗ |
| `renderTarget` | `any` | let/var | `descriptor.renderTarget` | ✗ |
| `isCube` | `boolean` | let/var | `renderTarget.isWebGLCubeRenderTarget === true` | ✗ |
| `isRenderTarget3D` | `boolean` | let/var | `renderTarget.isRenderTarget3D === true` | ✗ |
| `isRenderTargetArray` | `boolean` | let/var | `renderTarget.depth > 1` | ✗ |
| `isXRRenderTarget` | `boolean` | let/var | `renderTarget.isXRRenderTarget === true` | ✗ |
| `_hasExternalTextures` | `boolean` | let/var | `( isXRRenderTarget === true && renderTarget._hasExternalTextures === true )` | ✗ |
| `msaaFb` | `any` | let/var | `renderTargetContextData.msaaFrameBuffer` | ✗ |
| `depthRenderbuffer` | `any` | let/var | `renderTargetContextData.depthRenderbuffer` | ✗ |
| `fb` | `any` | let/var | `*not shown*` | ✗ |
| `textures` | `any` | let/var | `descriptor.textures` | ✗ |
| `depthInvalidationArray` | `any[]` | let/var | `[]` | ✗ |
| `cubeFace` | `any` | let/var | `this.renderer._activeCubeFace` | ✗ |
| `texture` | `any` | let/var | `textures[ i ]` | ✗ |
| `attachment` | `number` | let/var | `gl.COLOR_ATTACHMENT0 + i` | ✗ |
| `layer` | `any` | let/var | `this.renderer._activeCubeFace` | ✗ |
| `depthStyle` | `33306 \| 36096` | let/var | `stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT` | ✗ |
| `layer` | `any` | let/var | `this.renderer._activeCubeFace` | ✗ |
| `layer` | `any` | let/var | `this.renderer._activeCubeFace` | ✗ |
| `depthStyle` | `33306 \| 36096` | let/var | `stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT` | ✗ |
| `depthStyle` | `33306 \| 36096` | let/var | `stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT` | ✗ |
| `renderbuffer` | `any` | let/var | `renderTargetContextData.xrDepthRenderbuffer` | ✗ |
| `invalidationArray` | `any[]` | let/var | `[]` | ✗ |
| `msaaRenderbuffers` | `any[]` | let/var | `[]` | ✗ |
| `textures` | `any` | let/var | `descriptor.textures` | ✗ |
| `texture` | `any` | let/var | `descriptor.textures[ i ]` | ✗ |
| `depthStyle` | `33306 \| 36096` | let/var | `stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT` | ✗ |
| `key` | `string` | let/var | `''` | ✗ |
| `attribute` | `BufferAttribute` | let/var | `attributes[ i ]` | ✗ |
| `stride` | `any` | let/var | `*not shown*` | ✗ |
| `offset` | `any` | let/var | `*not shown*` | ✗ |
| `key` | `string` | let/var | `''` | ✗ |
| `transformFeedbackGPU` | `WebGLTransformFeedback` | let/var | `this.transformFeedbackCache[ key ]` | ✗ |
| `attributeData` | `DualAttributeData` | let/var | `transformBuffers[ i ]` | ✗ |
| `gl` | `WebGL2RenderingContext` | let/var | `this.gl` | ✗ |
| `index` | `any` | let/var | `bindingData.index` | ✗ |
| `index` | `any` | let/var | `bindingData.index` | ✗ |


---

## Functions

### `WebGLBackend.init(renderer: Renderer): void`

**JSDoc:**
```typescript
/**
	 * Initializes the backend so it is ready for usage.
	 *
	 * @param {Renderer} renderer - The renderer.
	 */
```

**Parameters:**

- **`renderer`** `Renderer`

**Returns:** `void`

**Calls:**

- `super.init`
- `renderer.domElement.getContext`
- `event.preventDefault`
- `renderer.onDeviceLost`
- `renderer.domElement.addEventListener`
- `this.extensions.get`

**Internal Comments:**
```
// (x2)
```

<details><summary>Code</summary>

```typescript
init( renderer ) {

		super.init( renderer );

		//

		const parameters = this.parameters;

		const contextAttributes = {
			antialias: renderer.samples > 0,
			alpha: true, // always true for performance reasons
			depth: renderer.depth,
			stencil: renderer.stencil
		};

		const glContext = ( parameters.context !== undefined ) ? parameters.context : renderer.domElement.getContext( 'webgl2', contextAttributes );

	 	function onContextLost( event ) {

			event.preventDefault();

			const contextLossInfo = {
				api: 'WebGL',
				message: event.statusMessage || 'Unknown reason',
				reason: null,
				originalEvent: event
			};

			renderer.onDeviceLost( contextLossInfo );

		}

		this._onContextLost = onContextLost;

		renderer.domElement.addEventListener( 'webglcontextlost', onContextLost, false );

		this.gl = glContext;

		this.extensions = new WebGLExtensions( this );
		this.capabilities = new WebGLCapabilities( this );
		this.attributeUtils = new WebGLAttributeUtils( this );
		this.textureUtils = new WebGLTextureUtils( this );
		this.bufferRenderer = new WebGLBufferRenderer( this );

		this.state = new WebGLState( this );
		this.utils = new WebGLUtils( this );

		this.extensions.get( 'EXT_color_buffer_float' );
		this.extensions.get( 'WEBGL_clip_cull_distance' );
		this.extensions.get( 'OES_texture_float_linear' );
		this.extensions.get( 'EXT_color_buffer_half_float' );
		this.extensions.get( 'WEBGL_multisampled_render_to_texture' );
		this.extensions.get( 'WEBGL_render_shared_exponent' );
		this.extensions.get( 'WEBGL_multi_draw' );
		this.extensions.get( 'OVR_multiview2' );

		this.disjoint = this.extensions.get( 'EXT_disjoint_timer_query_webgl2' );
		this.parallel = this.extensions.get( 'KHR_parallel_shader_compile' );

	}
```
</details>

### `WebGLBackend.getArrayBufferAsync(attribute: StorageBufferAttribute): Promise<ArrayBuffer>`

**JSDoc:**
```typescript
/**
	 * This method performs a readback operation by moving buffer data from
	 * a storage buffer attribute from the GPU to the CPU.
	 *
	 * @async
	 * @param {StorageBufferAttribute} attribute - The storage buffer attribute.
	 * @return {Promise<ArrayBuffer>} A promise that resolves with the buffer data when the data are ready.
	 */
```

**Parameters:**

- **`attribute`** `StorageBufferAttribute`

**Returns:** `Promise<ArrayBuffer>`

**Calls:**

- `this.attributeUtils.getArrayBufferAsync`

<details><summary>Code</summary>

```typescript
async getArrayBufferAsync( attribute ) {

		return await this.attributeUtils.getArrayBufferAsync( attribute );

	}
```
</details>

### `WebGLBackend.waitForGPU(): Promise<any>`

**JSDoc:**
```typescript
/**
	 * Can be used to synchronize CPU operations with GPU tasks. So when this method is called,
	 * the CPU waits for the GPU to complete its operation (e.g. a compute task).
	 *
	 * @async
	 * @return {Promise} A Promise that resolves when synchronization has been finished.
	 */
```

**Returns:** `Promise<any>`

**Calls:**

- `this.utils._clientWaitAsync`

<details><summary>Code</summary>

```typescript
async waitForGPU() {

		await this.utils._clientWaitAsync();

	}
```
</details>

### `WebGLBackend.makeXRCompatible(): Promise<any>`

**JSDoc:**
```typescript
/**
	 * Ensures the backend is XR compatible.
	 *
	 * @async
	 * @return {Promise} A Promise that resolve when the renderer is XR compatible.
	 */
```

**Returns:** `Promise<any>`

**Calls:**

- `this.gl.getContextAttributes`
- `this.gl.makeXRCompatible`

<details><summary>Code</summary>

```typescript
async makeXRCompatible() {

		const attributes = this.gl.getContextAttributes();

		if ( attributes.xrCompatible !== true ) {

			await this.gl.makeXRCompatible();

		}

	}
```
</details>

### `WebGLBackend.setXRTarget(xrFramebuffer: WebGLFramebuffer): void`

**JSDoc:**
```typescript
/**
	 * Sets the XR rendering destination.
	 *
	 * @param {WebGLFramebuffer} xrFramebuffer - The XR framebuffer.
	 */
```

**Parameters:**

- **`xrFramebuffer`** `WebGLFramebuffer`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setXRTarget( xrFramebuffer ) {

		this._xrFramebuffer = xrFramebuffer;

	}
```
</details>

### `WebGLBackend.setXRRenderTargetTextures(renderTarget: XRRenderTarget, colorTexture: WebGLTexture, depthTexture: WebGLTexture): void`

**JSDoc:**
```typescript
/**
	 * Configures the given XR render target with external textures.
	 *
	 * This method is only relevant when using the WebXR Layers API.
	 *
	 * @param {XRRenderTarget} renderTarget - The XR render target.
	 * @param {WebGLTexture} colorTexture - A native color texture.
	 * @param {?WebGLTexture} [depthTexture=null] - A native depth texture.
	 */
```

**Parameters:**

- **`renderTarget`** `XRRenderTarget`
- **`colorTexture`** `WebGLTexture`
- **`depthTexture`** `WebGLTexture`

**Returns:** `void`

**Calls:**

- `this.set`
- `this.extensions.has`
- `console.warn`

**Internal Comments:**
```
// The multisample_render_to_texture extension doesn't work properly if there
// are midframe flushes and an external depth texture.
```

<details><summary>Code</summary>

```typescript
setXRRenderTargetTextures( renderTarget, colorTexture, depthTexture = null ) {

		const gl = this.gl;

		this.set( renderTarget.texture, { textureGPU: colorTexture, glInternalFormat: gl.RGBA8 } ); // see #24698 why RGBA8 and not SRGB8_ALPHA8 is used

		if ( depthTexture !== null ) {

			const glInternalFormat = renderTarget.stencilBuffer ? gl.DEPTH24_STENCIL8 : gl.DEPTH_COMPONENT24;

			this.set( renderTarget.depthTexture, { textureGPU: depthTexture, glInternalFormat: glInternalFormat } );

			// The multisample_render_to_texture extension doesn't work properly if there
			// are midframe flushes and an external depth texture.
			if ( ( this.extensions.has( 'WEBGL_multisampled_render_to_texture' ) === true ) && renderTarget._autoAllocateDepthBuffer === true && renderTarget.multiview === false ) {

				console.warn( 'THREE.WebGLBackend: Render-to-texture extension was disabled because an external texture was provided' );

			}

			renderTarget._autoAllocateDepthBuffer = false;

		}

	}
```
</details>

### `WebGLBackend.initTimestampQuery(renderContext: RenderContext): void`

**JSDoc:**
```typescript
/**
	 * Inits a time stamp query for the given render context.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`

**Returns:** `void`

**Calls:**

- `timestampQueryPool.allocateQueriesForContext`
- `timestampQueryPool.beginQuery`

**Internal Comments:**
```
// TODO: Variable maxQueries? (x5)
```

<details><summary>Code</summary>

```typescript
initTimestampQuery( renderContext ) {

		if ( ! this.disjoint || ! this.trackTimestamp ) return;

		const type = renderContext.isComputeNode ? 'compute' : 'render';

		if ( ! this.timestampQueryPool[ type ] ) {

			// TODO: Variable maxQueries?
			this.timestampQueryPool[ type ] = new WebGLTimestampQueryPool( this.gl, type, 2048 );

		}

		const timestampQueryPool = this.timestampQueryPool[ type ];

		const baseOffset = timestampQueryPool.allocateQueriesForContext( renderContext );

		if ( baseOffset !== null ) {

			timestampQueryPool.beginQuery( renderContext );

		}

	}
```
</details>

### `WebGLBackend.prepareTimestampBuffer(renderContext: RenderContext): void`

**JSDoc:**
```typescript
/**
	 * Prepares the timestamp buffer.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`

**Returns:** `void`

**Calls:**

- `timestampQueryPool.endQuery`

<details><summary>Code</summary>

```typescript
prepareTimestampBuffer( renderContext ) {

		if ( ! this.disjoint || ! this.trackTimestamp ) return;

		const type = renderContext.isComputeNode ? 'compute' : 'render';
		const timestampQueryPool = this.timestampQueryPool[ type ];

		timestampQueryPool.endQuery( renderContext );

	}
```
</details>

### `WebGLBackend.getContext(): WebGL2RenderingContext`

**JSDoc:**
```typescript
/**
	 * Returns the backend's rendering context.
	 *
	 * @return {WebGL2RenderingContext} The rendering context.
	 */
```

**Returns:** `WebGL2RenderingContext`

<details><summary>Code</summary>

```typescript
getContext() {

		return this.gl;

	}
```
</details>

### `WebGLBackend.beginRender(renderContext: RenderContext): void`

**JSDoc:**
```typescript
/**
	 * This method is executed at the beginning of a render call and prepares
	 * the WebGL state for upcoming render calls
	 *
	 * @param {RenderContext} renderContext - The render context.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`

**Returns:** `void`

**Calls:**

- `this.get`
- `this.updateViewport`
- `this.getDrawingBufferSize`
- `state.viewport`
- `state.scissor`
- `this.initTimestampQuery`
- `this._setFramebuffer`
- `this.clear`

**Internal Comments:**
```
// (x5)
// Get a reference to the array of objects with queries. The renderContextData property (x4)
// can be changed by another render pass before the async reading of all previous queries complete (x4)
```

<details><summary>Code</summary>

```typescript
beginRender( renderContext ) {

		const { state } = this;
		const renderContextData = this.get( renderContext );

		//

		if ( renderContext.viewport ) {

			this.updateViewport( renderContext );

		} else {

			const { width, height } = this.getDrawingBufferSize();
			state.viewport( 0, 0, width, height );

		}

		if ( renderContext.scissor ) {

			const { x, y, width, height } = renderContext.scissorValue;

			state.scissor( x, renderContext.height - height - y, width, height );

		}

		//

		this.initTimestampQuery( renderContext );

		renderContextData.previousContext = this._currentContext;
		this._currentContext = renderContext;

		this._setFramebuffer( renderContext );
		this.clear( renderContext.clearColor, renderContext.clearDepth, renderContext.clearStencil, renderContext, false );

		const occlusionQueryCount = renderContext.occlusionQueryCount;

		if ( occlusionQueryCount > 0 ) {

			// Get a reference to the array of objects with queries. The renderContextData property
			// can be changed by another render pass before the async reading of all previous queries complete
			renderContextData.currentOcclusionQueries = renderContextData.occlusionQueries;
			renderContextData.currentOcclusionQueryObjects = renderContextData.occlusionQueryObjects;

			renderContextData.lastOcclusionObject = null;
			renderContextData.occlusionQueries = new Array( occlusionQueryCount );
			renderContextData.occlusionQueryObjects = new Array( occlusionQueryCount );
			renderContextData.occlusionQueryIndex = 0;

		}

	}
```
</details>

### `WebGLBackend.finishRender(renderContext: RenderContext): void`

**JSDoc:**
```typescript
/**
	 * This method is executed at the end of a render call and finalizes work
	 * after draw calls.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`

**Returns:** `void`

**Calls:**

- `this.get`
- `state.resetVertexState`
- `gl.endQuery`
- `this.resolveOccludedAsync`
- `this.generateMipmaps`
- `this._useMultisampledExtension`
- `renderContext.getCacheKey`
- `state.bindFramebuffer`
- `gl.framebufferRenderbuffer`
- `gl.framebufferTexture2D`
- `gl.blitFramebuffer`
- `gl.invalidateFramebuffer`
- `this._setFramebuffer`
- `this.updateViewport`
- `this.getDrawingBufferSize`
- `state.viewport`
- `this.prepareTimestampBuffer`

**Internal Comments:**
```
// blitFramebuffer() can only copy/resolve the first color attachment of a framebuffer. When using MRT,
// the engine temporarily removes all attachments and then configures each attachment for the resolve.
// configure attachment for resolve (x2)
// restore attachments
```

<details><summary>Code</summary>

```typescript
finishRender( renderContext ) {

		const { gl, state } = this;
		const renderContextData = this.get( renderContext );
		const previousContext = renderContextData.previousContext;

		state.resetVertexState();

		const occlusionQueryCount = renderContext.occlusionQueryCount;

		if ( occlusionQueryCount > 0 ) {

			if ( occlusionQueryCount > renderContextData.occlusionQueryIndex ) {

				gl.endQuery( gl.ANY_SAMPLES_PASSED );

			}

			this.resolveOccludedAsync( renderContext );

		}

		const textures = renderContext.textures;

		if ( textures !== null ) {

			for ( let i = 0; i < textures.length; i ++ ) {

				const texture = textures[ i ];

				if ( texture.generateMipmaps ) {

					this.generateMipmaps( texture );

				}

			}

		}

		this._currentContext = previousContext;
		const renderTarget = renderContext.renderTarget;

		if ( renderContext.textures !== null && renderTarget ) {

			const renderTargetContextData = this.get( renderTarget );

			if ( renderTarget.samples > 0 && this._useMultisampledExtension( renderTarget ) === false ) {

				const fb = renderTargetContextData.framebuffers[ renderContext.getCacheKey() ];

				let mask = gl.COLOR_BUFFER_BIT;

				if ( renderTarget.resolveDepthBuffer ) {

					if ( renderTarget.depthBuffer ) mask |= gl.DEPTH_BUFFER_BIT;
					if ( renderTarget.stencilBuffer && renderTarget.resolveStencilBuffer ) mask |= gl.STENCIL_BUFFER_BIT;

				}

				const msaaFrameBuffer = renderTargetContextData.msaaFrameBuffer;
				const msaaRenderbuffers = renderTargetContextData.msaaRenderbuffers;

				const textures = renderContext.textures;
				const isMRT = textures.length > 1;

				state.bindFramebuffer( gl.READ_FRAMEBUFFER, msaaFrameBuffer );
				state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, fb );

				if ( isMRT ) {

					// blitFramebuffer() can only copy/resolve the first color attachment of a framebuffer. When using MRT,
					// the engine temporarily removes all attachments and then configures each attachment for the resolve.

					for ( let i = 0; i < textures.length; i ++ ) {

						gl.framebufferRenderbuffer( gl.READ_FRAMEBUFFER, gl.COLOR_ATTACHMENT0 + i, gl.RENDERBUFFER, null );
						gl.framebufferTexture2D( gl.DRAW_FRAMEBUFFER, gl.COLOR_ATTACHMENT0 + i, gl.TEXTURE_2D, null, 0 );

					}

				}

				for ( let i = 0; i < textures.length; i ++ ) {

					if ( isMRT ) {

						// configure attachment for resolve

						const { textureGPU } = this.get( textures[ i ] );

						gl.framebufferRenderbuffer( gl.READ_FRAMEBUFFER, gl.COLOR_ATTACHMENT0, gl.RENDERBUFFER, msaaRenderbuffers[ i ] );
						gl.framebufferTexture2D( gl.DRAW_FRAMEBUFFER, gl.COLOR_ATTACHMENT0, gl.TEXTURE_2D, textureGPU, 0 );

					}

					if ( renderContext.scissor ) {

						const { x, y, width, height } = renderContext.scissorValue;

						const viewY = renderContext.height - height - y;

						gl.blitFramebuffer( x, viewY, x + width, viewY + height, x, viewY, x + width, viewY + height, mask, gl.NEAREST );

					} else {

						gl.blitFramebuffer( 0, 0, renderContext.width, renderContext.height, 0, 0, renderContext.width, renderContext.height, mask, gl.NEAREST );

					}

				}

				if ( isMRT ) {

					// restore attachments

					for ( let i = 0; i < textures.length; i ++ ) {

						const { textureGPU } = this.get( textures[ i ] );

						gl.framebufferRenderbuffer( gl.READ_FRAMEBUFFER, gl.COLOR_ATTACHMENT0 + i, gl.RENDERBUFFER, msaaRenderbuffers[ i ] );
						gl.framebufferTexture2D( gl.DRAW_FRAMEBUFFER, gl.COLOR_ATTACHMENT0 + i, gl.TEXTURE_2D, textureGPU, 0 );

					}

				}

				if ( this._supportsInvalidateFramebuffer === true ) {

					gl.invalidateFramebuffer( gl.READ_FRAMEBUFFER, renderTargetContextData.invalidationArray );

				}

			} else if ( renderTarget.resolveDepthBuffer === false && renderTargetContextData.framebuffers ) {

				const fb = renderTargetContextData.framebuffers[ renderContext.getCacheKey() ];
				state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, fb );
				gl.invalidateFramebuffer( gl.DRAW_FRAMEBUFFER, renderTargetContextData.depthInvalidationArray );

			}

		}

		if ( previousContext !== null ) {

			this._setFramebuffer( previousContext );

			if ( previousContext.viewport ) {

				this.updateViewport( previousContext );

			} else {

				const { width, height } = this.getDrawingBufferSize();
				state.viewport( 0, 0, width, height );

			}

		}

		this.prepareTimestampBuffer( renderContext );

	}
```
</details>

### `WebGLBackend.resolveOccludedAsync(renderContext: RenderContext): void`

**JSDoc:**
```typescript
/**
	 * This method processes the result of occlusion queries and writes it
	 * into render context data.
	 *
	 * @async
	 * @param {RenderContext} renderContext - The render context.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`

**Returns:** `void`

**Calls:**

- `this.get`
- `gl.getQueryParameter`
- `occluded.add`
- `gl.deleteQuery`
- `requestAnimationFrame`
- `check`

**Internal Comments:**
```
// handle occlusion query results (x2)
// check all queries and requeue as appropriate
```

<details><summary>Code</summary>

```typescript
resolveOccludedAsync( renderContext ) {

		const renderContextData = this.get( renderContext );

		// handle occlusion query results

		const { currentOcclusionQueries, currentOcclusionQueryObjects } = renderContextData;

		if ( currentOcclusionQueries && currentOcclusionQueryObjects ) {

			const occluded = new WeakSet();
			const { gl } = this;

			renderContextData.currentOcclusionQueryObjects = null;
			renderContextData.currentOcclusionQueries = null;

			const check = () => {

				let completed = 0;

				// check all queries and requeue as appropriate
				for ( let i = 0; i < currentOcclusionQueries.length; i ++ ) {

					const query = currentOcclusionQueries[ i ];

					if ( query === null ) continue;

					if ( gl.getQueryParameter( query, gl.QUERY_RESULT_AVAILABLE ) ) {

						if ( gl.getQueryParameter( query, gl.QUERY_RESULT ) === 0 ) occluded.add( currentOcclusionQueryObjects[ i ] );

						currentOcclusionQueries[ i ] = null;
						gl.deleteQuery( query );

						completed ++;

					}

				}

				if ( completed < currentOcclusionQueries.length ) {

					requestAnimationFrame( check );

				} else {

					renderContextData.occluded = occluded;

				}

			};

			check();

		}

	}
```
</details>

### `WebGLBackend.isOccluded(renderContext: RenderContext, object: Object3D): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given 3D object is fully occluded by other
	 * 3D objects in the scene.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @param {Object3D} object - The 3D object to test.
	 * @return {boolean} Whether the 3D object is fully occluded or not.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`
- **`object`** `Object3D`

**Returns:** `boolean`

**Calls:**

- `this.get`
- `renderContextData.occluded.has`

<details><summary>Code</summary>

```typescript
isOccluded( renderContext, object ) {

		const renderContextData = this.get( renderContext );

		return renderContextData.occluded && renderContextData.occluded.has( object );

	}
```
</details>

### `WebGLBackend.updateViewport(renderContext: RenderContext): void`

**JSDoc:**
```typescript
/**
	 * Updates the viewport with the values from the given render context.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`

**Returns:** `void`

**Calls:**

- `state.viewport`

<details><summary>Code</summary>

```typescript
updateViewport( renderContext ) {

		const { state } = this;
		const { x, y, width, height } = renderContext.viewportValue;

		state.viewport( x, renderContext.height - height - y, width, height );

	}
```
</details>

### `WebGLBackend.setScissorTest(boolean: boolean): void`

**JSDoc:**
```typescript
/**
	 * Defines the scissor test.
	 *
	 * @param {boolean} boolean - Whether the scissor test should be enabled or not.
	 */
```

**Parameters:**

- **`boolean`** `boolean`

**Returns:** `void`

**Calls:**

- `state.setScissorTest`

<details><summary>Code</summary>

```typescript
setScissorTest( boolean ) {

		const state = this.state;

		state.setScissorTest( boolean );

	}
```
</details>

### `WebGLBackend.getClearColor(): Color4`

**JSDoc:**
```typescript
/**
	 * Returns the clear color and alpha into a single
	 * color object.
	 *
	 * @return {Color4} The clear color.
	 */
```

**Returns:** `Color4`

**Calls:**

- `super.getClearColor`

**Internal Comments:**
```
// Since the canvas is always created with alpha: true, (x4)
// WebGL must always premultiply the clear color. (x4)
```

<details><summary>Code</summary>

```typescript
getClearColor() {

		const clearColor = super.getClearColor();

		// Since the canvas is always created with alpha: true,
		// WebGL must always premultiply the clear color.

		clearColor.r *= clearColor.a;
		clearColor.g *= clearColor.a;
		clearColor.b *= clearColor.a;

		return clearColor;

	}
```
</details>

### `WebGLBackend.clear(color: boolean, depth: boolean, stencil: boolean, descriptor: any, setFrameBuffer: boolean): void`

**JSDoc:**
```typescript
/**
	 * Performs a clear operation.
	 *
	 * @param {boolean} color - Whether the color buffer should be cleared or not.
	 * @param {boolean} depth - Whether the depth buffer should be cleared or not.
	 * @param {boolean} stencil - Whether the stencil buffer should be cleared or not.
	 * @param {?Object} [descriptor=null] - The render context of the current set render target.
	 * @param {boolean} [setFrameBuffer=true] - TODO.
	 */
```

**Parameters:**

- **`color`** `boolean`
- **`depth`** `boolean`
- **`stencil`** `boolean`
- **`descriptor`** `any`
- **`setFrameBuffer`** `boolean`

**Returns:** `void`

**Calls:**

- `this.getClearColor`
- `renderer.getClearDepth`
- `renderer.getClearStencil`
- `this.state.setDepthMask`
- `gl.clearColor`
- `gl.clear`
- `this._setFramebuffer`
- `gl.clearBufferfv`
- `gl.clearBufferfi`
- `gl.clearBufferiv`

**Internal Comments:**
```
// (x2)
```

<details><summary>Code</summary>

```typescript
clear( color, depth, stencil, descriptor = null, setFrameBuffer = true ) {

		const { gl, renderer } = this;

		if ( descriptor === null ) {

			const clearColor = this.getClearColor();

			descriptor = {
				textures: null,
				clearColorValue: clearColor
			};

		}

		//

		let clear = 0;

		if ( color ) clear |= gl.COLOR_BUFFER_BIT;
		if ( depth ) clear |= gl.DEPTH_BUFFER_BIT;
		if ( stencil ) clear |= gl.STENCIL_BUFFER_BIT;

		if ( clear !== 0 ) {

			let clearColor;

			if ( descriptor.clearColorValue ) {

				clearColor = descriptor.clearColorValue;

			} else {

				clearColor = this.getClearColor();

			}

			const clearDepth = renderer.getClearDepth();
			const clearStencil = renderer.getClearStencil();

			if ( depth ) this.state.setDepthMask( true );

			if ( descriptor.textures === null ) {

				gl.clearColor( clearColor.r, clearColor.g, clearColor.b, clearColor.a );
				gl.clear( clear );

			} else {

				if ( setFrameBuffer ) this._setFramebuffer( descriptor );

				if ( color ) {

					for ( let i = 0; i < descriptor.textures.length; i ++ ) {

						if ( i === 0 ) {

							gl.clearBufferfv( gl.COLOR, i, [ clearColor.r, clearColor.g, clearColor.b, clearColor.a ] );

						} else {

							gl.clearBufferfv( gl.COLOR, i, [ 0, 0, 0, 1 ] );

						}

					}

				}

				if ( depth && stencil ) {

					gl.clearBufferfi( gl.DEPTH_STENCIL, 0, clearDepth, clearStencil );

				} else if ( depth ) {

					gl.clearBufferfv( gl.DEPTH, 0, [ clearDepth ] );

				} else if ( stencil ) {

					gl.clearBufferiv( gl.STENCIL, 0, [ clearStencil ] );

				}

			}

		}

	}
```
</details>

### `WebGLBackend.beginCompute(computeGroup: Node | Node[]): void`

**JSDoc:**
```typescript
/**
	 * This method is executed at the beginning of a compute call and
	 * prepares the state for upcoming compute tasks.
	 *
	 * @param {Node|Array<Node>} computeGroup - The compute node(s).
	 */
```

**Parameters:**

- **`computeGroup`** `Node | Node[]`

**Returns:** `void`

**Calls:**

- `state.bindFramebuffer`
- `this.initTimestampQuery`

<details><summary>Code</summary>

```typescript
beginCompute( computeGroup ) {

		const { state, gl } = this;

		state.bindFramebuffer( gl.FRAMEBUFFER, null );
		this.initTimestampQuery( computeGroup );

	}
```
</details>

### `WebGLBackend.compute(computeGroup: Node | Node[], computeNode: Node, bindings: BindGroup[], pipeline: ComputePipeline, count: number): void`

**JSDoc:**
```typescript
/**
	 * Executes a compute command for the given compute node.
	 *
	 * @param {Node|Array<Node>} computeGroup - The group of compute nodes of a compute call. Can be a single compute node.
	 * @param {Node} computeNode - The compute node.
	 * @param {Array<BindGroup>} bindings - The bindings.
	 * @param {ComputePipeline} pipeline - The compute pipeline.
	 * @param {number|null} [count=null] - The count of compute invocations. If `null`, the count is determined by the compute node.
	 */
```

**Parameters:**

- **`computeGroup`** `Node | Node[]`
- **`computeNode`** `Node`
- **`bindings`** `BindGroup[]`
- **`pipeline`** `ComputePipeline`
- **`count`** `number`

**Returns:** `void`

**Calls:**

- `gl.enable`
- `this.get`
- `this._getVaoKey`
- `this._createVao`
- `state.setVertexState`
- `state.useProgram`
- `this._bindUniforms`
- `this._getTransformFeedback`
- `gl.bindTransformFeedback`
- `gl.beginTransformFeedback`
- `Array.isArray`
- `warnOnce (from ../../utils.js)`
- `gl.drawArraysInstanced`
- `gl.drawArrays`
- `gl.endTransformFeedback`
- `this.has`
- `this.textureUtils.copyBufferToTexture`
- `dualAttributeData.switchBuffers`

**Internal Comments:**
```
// required here to handle async behaviour of render.compute() (x4)
// switch active buffers
```

<details><summary>Code</summary>

```typescript
compute( computeGroup, computeNode, bindings, pipeline, count = null ) {

		const { state, gl } = this;

		if ( this.discard === false ) {

			// required here to handle async behaviour of render.compute()
			gl.enable( gl.RASTERIZER_DISCARD );
			this.discard = true;

		}

		const { programGPU, transformBuffers, attributes } = this.get( pipeline );

		const vaoKey = this._getVaoKey( attributes );

		const vaoGPU = this.vaoCache[ vaoKey ];

		if ( vaoGPU === undefined ) {

			this.vaoCache[ vaoKey ] = this._createVao( attributes );

		} else {

			state.setVertexState( vaoGPU );

		}

		state.useProgram( programGPU );

		this._bindUniforms( bindings );

		const transformFeedbackGPU = this._getTransformFeedback( transformBuffers );

		gl.bindTransformFeedback( gl.TRANSFORM_FEEDBACK, transformFeedbackGPU );
		gl.beginTransformFeedback( gl.POINTS );

		count = ( count !== null ) ? count : computeNode.count;

		if ( Array.isArray( count ) ) {

			warnOnce( 'WebGLBackend.compute(): The count parameter must be a single number, not an array.' );

			count = count[ 0 ];

		}

		if ( attributes[ 0 ].isStorageInstancedBufferAttribute ) {

			gl.drawArraysInstanced( gl.POINTS, 0, 1, count );

		} else {

			gl.drawArrays( gl.POINTS, 0, count );

		}

		gl.endTransformFeedback();
		gl.bindTransformFeedback( gl.TRANSFORM_FEEDBACK, null );

		// switch active buffers

		for ( let i = 0; i < transformBuffers.length; i ++ ) {

			const dualAttributeData = transformBuffers[ i ];

			if ( dualAttributeData.pbo && this.has( dualAttributeData.pbo ) ) {

				this.textureUtils.copyBufferToTexture( dualAttributeData.transformBuffer, dualAttributeData.pbo );

			}

			dualAttributeData.switchBuffers();


		}

	}
```
</details>

### `WebGLBackend.finishCompute(computeGroup: Node | Node[]): void`

**JSDoc:**
```typescript
/**
	 * This method is executed at the end of a compute call and
	 * finalizes work after compute tasks.
	 *
	 * @param {Node|Array<Node>} computeGroup - The compute node(s).
	 */
```

**Parameters:**

- **`computeGroup`** `Node | Node[]`

**Returns:** `void`

**Calls:**

- `gl.disable`
- `this.prepareTimestampBuffer`
- `this._setFramebuffer`

<details><summary>Code</summary>

```typescript
finishCompute( computeGroup ) {

		const gl = this.gl;

		this.discard = false;

		gl.disable( gl.RASTERIZER_DISCARD );

		this.prepareTimestampBuffer( computeGroup );

		if ( this._currentContext ) {

			this._setFramebuffer( this._currentContext );

		}

	}
```
</details>

### `WebGLBackend._isRenderCameraDepthArray(renderContext: RenderContext): boolean`

**JSDoc:**
```typescript
/**
	 * Internal to determine if the current render target is a render target array with depth 2D array texture.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @return {boolean} Whether the render target is a render target array with depth 2D array texture.
	 *
	 * @private
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
_isRenderCameraDepthArray( renderContext ) {

		return renderContext.depthTexture && renderContext.depthTexture.isArrayTexture && renderContext.camera.isArrayCamera;

	}
```
</details>

### `WebGLBackend.draw(renderObject: RenderObject): void`

**JSDoc:**
```typescript
/**
	 * Executes a draw command for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object to draw.
	 * @param {Info} info - Holds a series of statistical information about the GPU memory and the rendering process.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `void`

**Calls:**

- `this.get`
- `renderObject.getDrawParameters`
- `this._bindUniforms`
- `renderObject.getBindings`
- `object.matrixWorld.determinant`
- `state.setMaterial`
- `state.useProgram`
- `renderObject.getAttributes`
- `this._getVaoKey`
- `this._createVao`
- `renderObject.getIndex`
- `state.setVertexState`
- `gl.endQuery`
- `gl.createQuery`
- `gl.beginQuery`
- `state.setLineWidth`
- `this.renderer.getPixelRatio`
- `warnOnce (from ../../utils.js)`
- `renderer.renderMultiDrawInstances`
- `this.hasFeature`
- `renderer.renderMultiDraw`
- `renderer.renderInstances`
- `renderer.render`
- `renderObject.getBindingGroup`
- `gl.createBuffer`
- `gl.bindBuffer`
- `gl.bufferData`
- `indexesGPU.push`
- `this._isRenderCameraDepthArray`
- `this._setFramebuffer`
- `this.clear`
- `object.layers.test`
- `state.viewport`
- `Math.floor`
- `state.bindBufferBase`
- `draw`

**Internal Comments:**
```
// (x10)
// vertex state (x2)
// @deprecated, r174 (x3)
// Clear the depth texture (x2)
// Update the active layer (x5)
```

<details><summary>Code</summary>

```typescript
draw( renderObject/*, info*/ ) {

		const { object, pipeline, material, context, hardwareClippingPlanes } = renderObject;
		const { programGPU } = this.get( pipeline );

		const { gl, state } = this;

		const contextData = this.get( context );

		const drawParams = renderObject.getDrawParameters();

		if ( drawParams === null ) return;

		//

		this._bindUniforms( renderObject.getBindings() );

		const frontFaceCW = ( object.isMesh && object.matrixWorld.determinant() < 0 );

		state.setMaterial( material, frontFaceCW, hardwareClippingPlanes );

		state.useProgram( programGPU );

		// vertex state

		const attributes = renderObject.getAttributes();
		const attributesData = this.get( attributes );

		let vaoGPU = attributesData.vaoGPU;

		if ( vaoGPU === undefined ) {

			const vaoKey = this._getVaoKey( attributes );

			vaoGPU = this.vaoCache[ vaoKey ];

			if ( vaoGPU === undefined ) {

				vaoGPU = this._createVao( attributes );

				this.vaoCache[ vaoKey ] = vaoGPU;
				attributesData.vaoGPU = vaoGPU;

			}

		}

		const index = renderObject.getIndex();
		const indexGPU = ( index !== null ) ? this.get( index ).bufferGPU : null;

		state.setVertexState( vaoGPU, indexGPU );

		//

		const lastObject = contextData.lastOcclusionObject;

		if ( lastObject !== object && lastObject !== undefined ) {

			if ( lastObject !== null && lastObject.occlusionTest === true ) {

				gl.endQuery( gl.ANY_SAMPLES_PASSED );

				contextData.occlusionQueryIndex ++;

			}

			if ( object.occlusionTest === true ) {

				const query = gl.createQuery();

				gl.beginQuery( gl.ANY_SAMPLES_PASSED, query );

				contextData.occlusionQueries[ contextData.occlusionQueryIndex ] = query;
				contextData.occlusionQueryObjects[ contextData.occlusionQueryIndex ] = object;

			}

			contextData.lastOcclusionObject = object;

		}

		//
		const renderer = this.bufferRenderer;

		if ( object.isPoints ) renderer.mode = gl.POINTS;
		else if ( object.isLineSegments ) renderer.mode = gl.LINES;
		else if ( object.isLine ) renderer.mode = gl.LINE_STRIP;
		else if ( object.isLineLoop ) renderer.mode = gl.LINE_LOOP;
		else {

			if ( material.wireframe === true ) {

				state.setLineWidth( material.wireframeLinewidth * this.renderer.getPixelRatio() );
				renderer.mode = gl.LINES;

			} else {

				renderer.mode = gl.TRIANGLES;

			}

		}

		//

		const { vertexCount, instanceCount } = drawParams;
		let { firstVertex } = drawParams;

		renderer.object = object;

		if ( index !== null ) {

			firstVertex *= index.array.BYTES_PER_ELEMENT;

			const indexData = this.get( index );

			renderer.index = index.count;
			renderer.type = indexData.type;

		} else {

			renderer.index = 0;

		}

		const draw = () => {

			if ( object.isBatchedMesh ) {

				if ( object._multiDrawInstances !== null ) {

					// @deprecated, r174
					warnOnce( 'THREE.WebGLBackend: renderMultiDrawInstances has been deprecated and will be removed in r184. Append to renderMultiDraw arguments and use indirection.' );
					renderer.renderMultiDrawInstances( object._multiDrawStarts, object._multiDrawCounts, object._multiDrawCount, object._multiDrawInstances );

				} else if ( ! this.hasFeature( 'WEBGL_multi_draw' ) ) {

					warnOnce( 'THREE.WebGLRenderer: WEBGL_multi_draw not supported.' );

				} else {

					renderer.renderMultiDraw( object._multiDrawStarts, object._multiDrawCounts, object._multiDrawCount );

				}

			} else if ( instanceCount > 1 ) {

				renderer.renderInstances( firstVertex, vertexCount, instanceCount );

			} else {

				renderer.render( firstVertex, vertexCount );

			}

		};

		if ( renderObject.camera.isArrayCamera === true && renderObject.camera.cameras.length > 0 && renderObject.camera.isMultiViewCamera === false ) {

			const cameraData = this.get( renderObject.camera );
			const cameras = renderObject.camera.cameras;
			const cameraIndex = renderObject.getBindingGroup( 'cameraIndex' ).bindings[ 0 ];

			if ( cameraData.indexesGPU === undefined || cameraData.indexesGPU.length !== cameras.length ) {

				const data = new Uint32Array( [ 0, 0, 0, 0 ] );
				const indexesGPU = [];

				for ( let i = 0, len = cameras.length; i < len; i ++ ) {

					const bufferGPU = gl.createBuffer();

					data[ 0 ] = i;

					gl.bindBuffer( gl.UNIFORM_BUFFER, bufferGPU );
					gl.bufferData( gl.UNIFORM_BUFFER, data, gl.STATIC_DRAW );

					indexesGPU.push( bufferGPU );

				}

				cameraData.indexesGPU = indexesGPU; // TODO: Create a global library for this

			}

			const cameraIndexData = this.get( cameraIndex );
			const pixelRatio = this.renderer.getPixelRatio();

			const renderTarget = this._currentContext.renderTarget;
			const isRenderCameraDepthArray = this._isRenderCameraDepthArray( this._currentContext );
			const prevActiveCubeFace = this._currentContext.activeCubeFace;

			if ( isRenderCameraDepthArray ) {

				// Clear the depth texture
				const textureData = this.get( renderTarget.depthTexture );

				if ( textureData.clearedRenderId !== this.renderer._nodes.nodeFrame.renderId ) {

					textureData.clearedRenderId = this.renderer._nodes.nodeFrame.renderId;

					const { stencilBuffer } = renderTarget;

					for ( let i = 0, len = cameras.length; i < len; i ++ ) {

						this.renderer._activeCubeFace = i;
						this._currentContext.activeCubeFace = i;

						this._setFramebuffer( this._currentContext );
						this.clear( false, true, stencilBuffer, this._currentContext, false );

					}

					this.renderer._activeCubeFace = prevActiveCubeFace;
					this._currentContext.activeCubeFace = prevActiveCubeFace;

				}

			}

			for ( let i = 0, len = cameras.length; i < len; i ++ ) {

				const subCamera = cameras[ i ];

				if ( object.layers.test( subCamera.layers ) ) {

					if ( isRenderCameraDepthArray ) {

						// Update the active layer
						this.renderer._activeCubeFace = i;
						this._currentContext.activeCubeFace = i;

						this._setFramebuffer( this._currentContext );

					}

					const vp = subCamera.viewport;

					if ( vp !== undefined ) {

						const x = vp.x * pixelRatio;
						const y = vp.y * pixelRatio;
						const width = vp.width * pixelRatio;
						const height = vp.height * pixelRatio;

						state.viewport(
							Math.floor( x ),
							Math.floor( renderObject.context.height - height - y ),
							Math.floor( width ),
							Math.floor( height )
						);

					}

					state.bindBufferBase( gl.UNIFORM_BUFFER, cameraIndexData.index, cameraData.indexesGPU[ i ] );

					draw();

				}

				this._currentContext.activeCubeFace = prevActiveCubeFace;
				this.renderer._activeCubeFace = prevActiveCubeFace;

			}

		} else {

			draw();

		}

	}
```
</details>

### `WebGLBackend.needsRenderUpdate(): boolean`

**JSDoc:**
```typescript
/**
	 * Explain why always null is returned.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {boolean} Whether the render pipeline requires an update or not.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
needsRenderUpdate( /*renderObject*/ ) {

		return false;

	}
```
</details>

### `WebGLBackend.getRenderCacheKey(): string`

**JSDoc:**
```typescript
/**
	 * Explain why no cache key is computed.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {string} The cache key.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getRenderCacheKey( /*renderObject*/ ) {

		return '';

	}
```
</details>

### `WebGLBackend.createDefaultTexture(texture: Texture): void`

**JSDoc:**
```typescript
/**
	 * Creates a default texture for the given texture that can be used
	 * as a placeholder until the actual texture is ready for usage.
	 *
	 * @param {Texture} texture - The texture to create a default texture for.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `void`

**Calls:**

- `this.textureUtils.createDefaultTexture`

<details><summary>Code</summary>

```typescript
createDefaultTexture( texture ) {

		this.textureUtils.createDefaultTexture( texture );

	}
```
</details>

### `WebGLBackend.createTexture(texture: Texture, options: any): void`

**JSDoc:**
```typescript
/**
	 * Defines a texture on the GPU for the given texture object.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {Object} [options={}] - Optional configuration parameter.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `this.textureUtils.createTexture`

<details><summary>Code</summary>

```typescript
createTexture( texture, options ) {

		this.textureUtils.createTexture( texture, options );

	}
```
</details>

### `WebGLBackend.updateTexture(texture: Texture, options: any): void`

**JSDoc:**
```typescript
/**
	 * Uploads the updated texture data to the GPU.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {Object} [options={}] - Optional configuration parameter.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `this.textureUtils.updateTexture`

<details><summary>Code</summary>

```typescript
updateTexture( texture, options ) {

		this.textureUtils.updateTexture( texture, options );

	}
```
</details>

### `WebGLBackend.generateMipmaps(texture: Texture): void`

**JSDoc:**
```typescript
/**
	 * Generates mipmaps for the given texture.
	 *
	 * @param {Texture} texture - The texture.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `void`

**Calls:**

- `this.textureUtils.generateMipmaps`

<details><summary>Code</summary>

```typescript
generateMipmaps( texture ) {

		this.textureUtils.generateMipmaps( texture );

	}
```
</details>

### `WebGLBackend.destroyTexture(texture: Texture): void`

**JSDoc:**
```typescript
/**
	 * Destroys the GPU data for the given texture object.
	 *
	 * @param {Texture} texture - The texture.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `void`

**Calls:**

- `this.textureUtils.destroyTexture`

<details><summary>Code</summary>

```typescript
destroyTexture( texture ) {

		this.textureUtils.destroyTexture( texture );

	}
```
</details>

### `WebGLBackend.copyTextureToBuffer(texture: Texture, x: number, y: number, width: number, height: number, faceIndex: number): Promise<TypedArray>`

**JSDoc:**
```typescript
/**
	 * Returns texture data as a typed array.
	 *
	 * @async
	 * @param {Texture} texture - The texture to copy.
	 * @param {number} x - The x coordinate of the copy origin.
	 * @param {number} y - The y coordinate of the copy origin.
	 * @param {number} width - The width of the copy.
	 * @param {number} height - The height of the copy.
	 * @param {number} faceIndex - The face index.
	 * @return {Promise<TypedArray>} A Promise that resolves with a typed array when the copy operation has finished.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`x`** `number`
- **`y`** `number`
- **`width`** `number`
- **`height`** `number`
- **`faceIndex`** `number`

**Returns:** `Promise<TypedArray>`

**Calls:**

- `this.textureUtils.copyTextureToBuffer`

<details><summary>Code</summary>

```typescript
async copyTextureToBuffer( texture, x, y, width, height, faceIndex ) {

		return this.textureUtils.copyTextureToBuffer( texture, x, y, width, height, faceIndex );

	}
```
</details>

### `WebGLBackend.createSampler(): void`

**JSDoc:**
```typescript
/**
	 * This method does nothing since WebGL 2 has no concept of samplers.
	 *
	 * @param {Texture} texture - The texture to create the sampler for.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
createSampler( /*texture*/ ) {

		//console.warn( 'Abstract class.' );

	}
```
</details>

### `WebGLBackend.destroySampler(): void`

**JSDoc:**
```typescript
/**
	 * This method does nothing since WebGL 2 has no concept of samplers.
	 *
	 * @param {Texture} texture - The texture to destroy the sampler for.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
destroySampler( /*texture*/ ) {}
```
</details>

### `WebGLBackend.createNodeBuilder(object: RenderObject, renderer: Renderer): GLSLNodeBuilder`

**JSDoc:**
```typescript
/**
	 * Returns a node builder for the given render object.
	 *
	 * @param {RenderObject} object - The render object.
	 * @param {Renderer} renderer - The renderer.
	 * @return {GLSLNodeBuilder} The node builder.
	 */
```

**Parameters:**

- **`object`** `RenderObject`
- **`renderer`** `Renderer`

**Returns:** `GLSLNodeBuilder`

<details><summary>Code</summary>

```typescript
createNodeBuilder( object, renderer ) {

		return new GLSLNodeBuilder( object, renderer );

	}
```
</details>

### `WebGLBackend.createProgram(program: ProgrammableStage): void`

**JSDoc:**
```typescript
/**
	 * Creates a shader program from the given programmable stage.
	 *
	 * @param {ProgrammableStage} program - The programmable stage.
	 */
```

**Parameters:**

- **`program`** `ProgrammableStage`

**Returns:** `void`

**Calls:**

- `gl.createShader`
- `gl.shaderSource`
- `gl.compileShader`
- `this.set`

<details><summary>Code</summary>

```typescript
createProgram( program ) {

		const gl = this.gl;
		const { stage, code } = program;

		const shader = stage === 'fragment' ? gl.createShader( gl.FRAGMENT_SHADER ) : gl.createShader( gl.VERTEX_SHADER );

		gl.shaderSource( shader, code );
		gl.compileShader( shader );

		this.set( program, {
			shaderGPU: shader
		} );

	}
```
</details>

### `WebGLBackend.destroyProgram(program: ProgrammableStage): void`

**JSDoc:**
```typescript
/**
	 * Destroys the shader program of the given programmable stage.
	 *
	 * @param {ProgrammableStage} program - The programmable stage.
	 */
```

**Parameters:**

- **`program`** `ProgrammableStage`

**Returns:** `void`

**Calls:**

- `this.delete`

<details><summary>Code</summary>

```typescript
destroyProgram( program ) {

		this.delete( program );

	}
```
</details>

### `WebGLBackend.createRenderPipeline(renderObject: RenderObject, promises: Promise<any>[]): void`

**JSDoc:**
```typescript
/**
	 * Creates a render pipeline for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @param {Array<Promise>} promises - An array of compilation promises which are used in `compileAsync()`.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`
- **`promises`** `Promise<any>[]`

**Returns:** `void`

**Calls:**

- `gl.createProgram`
- `this.get`
- `gl.attachShader`
- `gl.linkProgram`
- `this.set`
- `gl.getProgramParameter`
- `this._completeCompile`
- `resolve`
- `requestAnimationFrame`
- `checkStatus`
- `promises.push`

**Internal Comments:**
```
// Program (x2)
```

<details><summary>Code</summary>

```typescript
createRenderPipeline( renderObject, promises ) {

		const gl = this.gl;
		const pipeline = renderObject.pipeline;

		// Program

		const { fragmentProgram, vertexProgram } = pipeline;

		const programGPU = gl.createProgram();

		const fragmentShader = this.get( fragmentProgram ).shaderGPU;
		const vertexShader = this.get( vertexProgram ).shaderGPU;

		gl.attachShader( programGPU, fragmentShader );
		gl.attachShader( programGPU, vertexShader );
		gl.linkProgram( programGPU );

		this.set( pipeline, {
			programGPU,
			fragmentShader,
			vertexShader
		} );

		if ( promises !== null && this.parallel ) {

			const p = new Promise( ( resolve /*, reject*/ ) => {

				const parallel = this.parallel;
				const checkStatus = () => {

					if ( gl.getProgramParameter( programGPU, parallel.COMPLETION_STATUS_KHR ) ) {

						this._completeCompile( renderObject, pipeline );
						resolve();

					} else {

						requestAnimationFrame( checkStatus );

					}

				};

				checkStatus();

			} );

			promises.push( p );

			return;

		}

		this._completeCompile( renderObject, pipeline );

	}
```
</details>

### `WebGLBackend._handleSource(string: string, errorLine: number): string`

**JSDoc:**
```typescript
/**
	 * Formats the source code of error messages.
	 *
	 * @private
	 * @param {string} string - The code.
	 * @param {number} errorLine - The error line.
	 * @return {string} The formatted code.
	 */
```

**Parameters:**

- **`string`** `string`
- **`errorLine`** `number`

**Returns:** `string`

**Calls:**

- `string.split`
- `Math.max`
- `Math.min`
- `lines2.push`
- `lines2.join`

<details><summary>Code</summary>

```typescript
_handleSource( string, errorLine ) {

		const lines = string.split( '\n' );
		const lines2 = [];

		const from = Math.max( errorLine - 6, 0 );
		const to = Math.min( errorLine + 6, lines.length );

		for ( let i = from; i < to; i ++ ) {

			const line = i + 1;
			lines2.push( `${line === errorLine ? '>' : ' '} ${line}: ${lines[ i ]}` );

		}

		return lines2.join( '\n' );

	}
```
</details>

### `WebGLBackend._getShaderErrors(gl: WebGL2RenderingContext, shader: WebGLShader, type: string): string`

**JSDoc:**
```typescript
/**
	 * Gets the shader compilation errors from the info log.
	 *
	 * @private
	 * @param {WebGL2RenderingContext} gl - The rendering context.
	 * @param {WebGLShader} shader - The WebGL shader object.
	 * @param {string} type - The shader type.
	 * @return {string} The shader errors.
	 */
```

**Parameters:**

- **`gl`** `WebGL2RenderingContext`
- **`shader`** `WebGLShader`
- **`type`** `string`

**Returns:** `string`

**Calls:**

- `gl.getShaderParameter`
- `gl.getShaderInfoLog`
- `shaderInfoLog.trim`
- `/ERROR: 0:(\d+)/.exec`
- `parseInt`
- `type.toUpperCase`
- `this._handleSource`
- `gl.getShaderSource`

<details><summary>Code</summary>

```typescript
_getShaderErrors( gl, shader, type ) {

		const status = gl.getShaderParameter( shader, gl.COMPILE_STATUS );

		const shaderInfoLog = gl.getShaderInfoLog( shader ) || '';
		const errors = shaderInfoLog.trim();

		if ( status && errors === '' ) return '';

		const errorMatches = /ERROR: 0:(\d+)/.exec( errors );
		if ( errorMatches ) {

			const errorLine = parseInt( errorMatches[ 1 ] );
			return type.toUpperCase() + '\n\n' + errors + '\n\n' + this._handleSource( gl.getShaderSource( shader ), errorLine );

		} else {

			return errors;

		}

	}
```
</details>

### `WebGLBackend._logProgramError(programGPU: WebGLProgram, glFragmentShader: WebGLShader, glVertexShader: WebGLShader): void`

**JSDoc:**
```typescript
/**
	 * Logs shader compilation errors.
	 *
	 * @private
	 * @param {WebGLProgram} programGPU - The WebGL program.
	 * @param {WebGLShader} glFragmentShader - The fragment shader as a native WebGL shader object.
	 * @param {WebGLShader} glVertexShader - The vertex shader as a native WebGL shader object.
	 */
```

**Parameters:**

- **`programGPU`** `WebGLProgram`
- **`glFragmentShader`** `WebGLShader`
- **`glVertexShader`** `WebGLShader`

**Returns:** `void`

**Calls:**

- `gl.getProgramInfoLog`
- `programInfoLog.trim`
- `gl.getProgramParameter`
- `this.renderer.debug.onShaderError`
- `this._getShaderErrors`
- `console.error`
- `gl.getError`
- `console.warn`

**Internal Comments:**
```
// default error reporting (x2)
```

<details><summary>Code</summary>

```typescript
_logProgramError( programGPU, glFragmentShader, glVertexShader ) {

		if ( this.renderer.debug.checkShaderErrors ) {

			const gl = this.gl;

			const programInfoLog = gl.getProgramInfoLog( programGPU ) || '';
			const programLog = programInfoLog.trim();

			if ( gl.getProgramParameter( programGPU, gl.LINK_STATUS ) === false ) {

				if ( typeof this.renderer.debug.onShaderError === 'function' ) {

					this.renderer.debug.onShaderError( gl, programGPU, glVertexShader, glFragmentShader );

				} else {

					// default error reporting

					const vertexErrors = this._getShaderErrors( gl, glVertexShader, 'vertex' );
					const fragmentErrors = this._getShaderErrors( gl, glFragmentShader, 'fragment' );

					console.error(
						'THREE.WebGLProgram: Shader Error ' + gl.getError() + ' - ' +
						'VALIDATE_STATUS ' + gl.getProgramParameter( programGPU, gl.VALIDATE_STATUS ) + '\n\n' +
						'Program Info Log: ' + programLog + '\n' +
						vertexErrors + '\n' +
						fragmentErrors
					);

				}

			} else if ( programLog !== '' ) {

				console.warn( 'THREE.WebGLProgram: Program Info Log:', programLog );

			}

		}

	}
```
</details>

### `WebGLBackend._completeCompile(renderObject: RenderObject, pipeline: RenderPipeline): void`

**JSDoc:**
```typescript
/**
	 * Completes the shader program setup for the given render object.
	 *
	 * @private
	 * @param {RenderObject} renderObject - The render object.
	 * @param {RenderPipeline} pipeline - The render pipeline.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`
- **`pipeline`** `RenderPipeline`

**Returns:** `void`

**Calls:**

- `this.get`
- `gl.getProgramParameter`
- `this._logProgramError`
- `state.useProgram`
- `renderObject.getBindings`
- `this._setupBindings`
- `this.set`

**Internal Comments:**
```
// Bindings (x2)
// (x4)
```

<details><summary>Code</summary>

```typescript
_completeCompile( renderObject, pipeline ) {

		const { state, gl } = this;
		const pipelineData = this.get( pipeline );
		const { programGPU, fragmentShader, vertexShader } = pipelineData;

		if ( gl.getProgramParameter( programGPU, gl.LINK_STATUS ) === false ) {

			this._logProgramError( programGPU, fragmentShader, vertexShader );

		}

		state.useProgram( programGPU );

		// Bindings

		const bindings = renderObject.getBindings();

		this._setupBindings( bindings, programGPU );

		//

		this.set( pipeline, {
			programGPU
		} );

	}
```
</details>

### `WebGLBackend.createComputePipeline(computePipeline: ComputePipeline, bindings: BindGroup[]): void`

**JSDoc:**
```typescript
/**
	 * Creates a compute pipeline for the given compute node.
	 *
	 * @param {ComputePipeline} computePipeline - The compute pipeline.
	 * @param {Array<BindGroup>} bindings - The bindings.
	 */
```

**Parameters:**

- **`computePipeline`** `ComputePipeline`
- **`bindings`** `BindGroup[]`

**Returns:** `void`

**Calls:**

- `this.createProgram`
- `gl.createProgram`
- `this.get`
- `transformVaryingNames.push`
- `transformAttributeNodes.push`
- `gl.attachShader`
- `gl.transformFeedbackVaryings`
- `gl.linkProgram`
- `gl.getProgramParameter`
- `this._logProgramError`
- `state.useProgram`
- `this._setupBindings`
- `attributes.push`
- `this.has`
- `this.attributeUtils.createAttribute`
- `transformBuffers.push`
- `this.set`

**Internal Comments:**
```
// Program (x2)
// Bindings (x4)
// (x4)
```

<details><summary>Code</summary>

```typescript
createComputePipeline( computePipeline, bindings ) {

		const { state, gl } = this;

		// Program

		const fragmentProgram = {
			stage: 'fragment',
			code: '#version 300 es\nprecision highp float;\nvoid main() {}'
		};

		this.createProgram( fragmentProgram );

		const { computeProgram } = computePipeline;

		const programGPU = gl.createProgram();

		const fragmentShader = this.get( fragmentProgram ).shaderGPU;
		const vertexShader = this.get( computeProgram ).shaderGPU;

		const transforms = computeProgram.transforms;

		const transformVaryingNames = [];
		const transformAttributeNodes = [];

		for ( let i = 0; i < transforms.length; i ++ ) {

			const transform = transforms[ i ];

			transformVaryingNames.push( transform.varyingName );
			transformAttributeNodes.push( transform.attributeNode );

		}

		gl.attachShader( programGPU, fragmentShader );
		gl.attachShader( programGPU, vertexShader );

		gl.transformFeedbackVaryings(
			programGPU,
			transformVaryingNames,
			gl.SEPARATE_ATTRIBS
		);

		gl.linkProgram( programGPU );

		if ( gl.getProgramParameter( programGPU, gl.LINK_STATUS ) === false ) {

			this._logProgramError( programGPU, fragmentShader, vertexShader );


		}

		state.useProgram( programGPU );

		// Bindings

		this._setupBindings( bindings, programGPU );

		const attributeNodes = computeProgram.attributes;
		const attributes = [];
		const transformBuffers = [];

		for ( let i = 0; i < attributeNodes.length; i ++ ) {

			const attribute = attributeNodes[ i ].node.attribute;

			attributes.push( attribute );

			if ( ! this.has( attribute ) ) this.attributeUtils.createAttribute( attribute, gl.ARRAY_BUFFER );

		}

		for ( let i = 0; i < transformAttributeNodes.length; i ++ ) {

			const attribute = transformAttributeNodes[ i ].attribute;

			if ( ! this.has( attribute ) ) this.attributeUtils.createAttribute( attribute, gl.ARRAY_BUFFER );

			const attributeData = this.get( attribute );

			transformBuffers.push( attributeData );

		}

		//

		this.set( computePipeline, {
			programGPU,
			transformBuffers,
			attributes
		} );

	}
```
</details>

### `WebGLBackend.createBindings(bindGroup: BindGroup, bindings: BindGroup[]): void`

**JSDoc:**
```typescript
/**
	 * Creates bindings from the given bind group definition.
	 *
	 * @param {BindGroup} bindGroup - The bind group.
	 * @param {Array<BindGroup>} bindings - Array of bind groups.
	 * @param {number} cacheIndex - The cache index.
	 * @param {number} version - The version.
	 */
```

**Parameters:**

- **`bindGroup`** `BindGroup`
- **`bindings`** `BindGroup[]`

**Returns:** `void`

**Calls:**

- `this._knownBindings.has`
- `this._knownBindings.add`
- `this.set`
- `this.updateBindings`

<details><summary>Code</summary>

```typescript
createBindings( bindGroup, bindings /*, cacheIndex, version*/ ) {

		if ( this._knownBindings.has( bindings ) === false ) {

			this._knownBindings.add( bindings );

			let uniformBuffers = 0;
			let textures = 0;

			for ( const bindGroup of bindings ) {

				this.set( bindGroup, {
					textures: textures,
					uniformBuffers: uniformBuffers
				} );

				for ( const binding of bindGroup.bindings ) {

					if ( binding.isUniformBuffer ) uniformBuffers ++;
					if ( binding.isSampledTexture ) textures ++;

				}

			}

		}

		this.updateBindings( bindGroup, bindings );

	}
```
</details>

### `WebGLBackend.updateBindings(bindGroup: BindGroup): void`

**JSDoc:**
```typescript
/**
	 * Updates the given bind group definition.
	 *
	 * @param {BindGroup} bindGroup - The bind group.
	 * @param {Array<BindGroup>} bindings - Array of bind groups.
	 * @param {number} cacheIndex - The cache index.
	 * @param {number} version - The version.
	 */
```

**Parameters:**

- **`bindGroup`** `BindGroup`

**Returns:** `void`

**Calls:**

- `this.get`
- `gl.createBuffer`
- `gl.bindBuffer`
- `gl.bufferData`
- `this.set`

<details><summary>Code</summary>

```typescript
updateBindings( bindGroup /*, bindings, cacheIndex, version*/ ) {

		const { gl } = this;

		const bindGroupData = this.get( bindGroup );

		let i = bindGroupData.uniformBuffers;
		let t = bindGroupData.textures;

		for ( const binding of bindGroup.bindings ) {

			if ( binding.isUniformsGroup || binding.isUniformBuffer ) {

				const data = binding.buffer;
				const bufferGPU = gl.createBuffer();

				gl.bindBuffer( gl.UNIFORM_BUFFER, bufferGPU );
				gl.bufferData( gl.UNIFORM_BUFFER, data, gl.DYNAMIC_DRAW );

				this.set( binding, {
					index: i ++,
					bufferGPU
				} );

			} else if ( binding.isSampledTexture ) {

				const { textureGPU, glTextureType } = this.get( binding.texture );

				this.set( binding, {
					index: t ++,
					textureGPU,
					glTextureType
				} );

			}

		}

	}
```
</details>

### `WebGLBackend.updateBinding(binding: Buffer<ArrayBufferLike>): void`

**JSDoc:**
```typescript
/**
	 * Updates a buffer binding.
	 *
	 *  @param {Buffer} binding - The buffer binding to update.
	 */
```

**Parameters:**

- **`binding`** `Buffer<ArrayBufferLike>`

**Returns:** `void`

**Calls:**

- `this.get`
- `gl.bindBuffer`
- `gl.bufferData`

<details><summary>Code</summary>

```typescript
updateBinding( binding ) {

		const gl = this.gl;

		if ( binding.isUniformsGroup || binding.isUniformBuffer ) {

			const bindingData = this.get( binding );
			const bufferGPU = bindingData.bufferGPU;
			const data = binding.buffer;

			gl.bindBuffer( gl.UNIFORM_BUFFER, bufferGPU );
			gl.bufferData( gl.UNIFORM_BUFFER, data, gl.DYNAMIC_DRAW );

		}

	}
```
</details>

### `WebGLBackend.createIndexAttribute(attribute: BufferAttribute): void`

**JSDoc:**
```typescript
/**
	 * Creates the GPU buffer of an indexed shader attribute.
	 *
	 * @param {BufferAttribute} attribute - The indexed buffer attribute.
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`

**Returns:** `void`

**Calls:**

- `this.attributeUtils.createAttribute`

<details><summary>Code</summary>

```typescript
createIndexAttribute( attribute ) {

		const gl = this.gl;

		this.attributeUtils.createAttribute( attribute, gl.ELEMENT_ARRAY_BUFFER );

	}
```
</details>

### `WebGLBackend.createAttribute(attribute: BufferAttribute): void`

**JSDoc:**
```typescript
/**
	 * Creates the GPU buffer of a shader attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`

**Returns:** `void`

**Calls:**

- `this.has`
- `this.attributeUtils.createAttribute`

<details><summary>Code</summary>

```typescript
createAttribute( attribute ) {

		if ( this.has( attribute ) ) return;

		const gl = this.gl;

		this.attributeUtils.createAttribute( attribute, gl.ARRAY_BUFFER );

	}
```
</details>

### `WebGLBackend.createStorageAttribute(attribute: BufferAttribute): void`

**JSDoc:**
```typescript
/**
	 * Creates the GPU buffer of a storage attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`

**Returns:** `void`

**Calls:**

- `this.has`
- `this.attributeUtils.createAttribute`

<details><summary>Code</summary>

```typescript
createStorageAttribute( attribute ) {

		if ( this.has( attribute ) ) return;

		const gl = this.gl;

		this.attributeUtils.createAttribute( attribute, gl.ARRAY_BUFFER );

	}
```
</details>

### `WebGLBackend.updateAttribute(attribute: BufferAttribute): void`

**JSDoc:**
```typescript
/**
	 * Updates the GPU buffer of a shader attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute to update.
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`

**Returns:** `void`

**Calls:**

- `this.attributeUtils.updateAttribute`

<details><summary>Code</summary>

```typescript
updateAttribute( attribute ) {

		this.attributeUtils.updateAttribute( attribute );

	}
```
</details>

### `WebGLBackend.destroyAttribute(attribute: BufferAttribute): void`

**JSDoc:**
```typescript
/**
	 * Destroys the GPU buffer of a shader attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute to destroy.
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`

**Returns:** `void`

**Calls:**

- `this.attributeUtils.destroyAttribute`

<details><summary>Code</summary>

```typescript
destroyAttribute( attribute ) {

		this.attributeUtils.destroyAttribute( attribute );

	}
```
</details>

### `WebGLBackend.hasFeature(name: string): boolean`

**JSDoc:**
```typescript
/**
	 * Checks if the given feature is supported  by the backend.
	 *
	 * @param {string} name - The feature's name.
	 * @return {boolean} Whether the feature is supported or not.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `boolean`

**Calls:**

- `Object.keys( GLFeatureName ).filter`
- `extensions.has`

<details><summary>Code</summary>

```typescript
hasFeature( name ) {

		const keysMatching = Object.keys( GLFeatureName ).filter( key => GLFeatureName[ key ] === name );

		const extensions = this.extensions;

		for ( let i = 0; i < keysMatching.length; i ++ ) {

			if ( extensions.has( keysMatching[ i ] ) ) return true;

		}

		return false;

	}
```
</details>

### `WebGLBackend.getMaxAnisotropy(): number`

**JSDoc:**
```typescript
/**
	 * Returns the maximum anisotropy texture filtering value.
	 *
	 * @return {number} The maximum anisotropy texture filtering value.
	 */
```

**Returns:** `number`

**Calls:**

- `this.capabilities.getMaxAnisotropy`

<details><summary>Code</summary>

```typescript
getMaxAnisotropy() {

		return this.capabilities.getMaxAnisotropy();

	}
```
</details>

### `WebGLBackend.copyTextureToTexture(srcTexture: Texture, dstTexture: Texture, srcRegion: any, dstPosition: any, srcLevel: number, dstLevel: number): void`

**JSDoc:**
```typescript
/**
	 * Copies data of the given source texture to the given destination texture.
	 *
	 * @param {Texture} srcTexture - The source texture.
	 * @param {Texture} dstTexture - The destination texture.
	 * @param {?(Box3|Box2)} [srcRegion=null] - The region of the source texture to copy.
	 * @param {?(Vector2|Vector3)} [dstPosition=null] - The destination position of the copy.
	 * @param {number} [srcLevel=0] - The source mip level to copy from.
	 * @param {number} [dstLevel=0] - The destination mip level to copy to.
	 */
```

**Parameters:**

- **`srcTexture`** `Texture`
- **`dstTexture`** `Texture`
- **`srcRegion`** `any`
- **`dstPosition`** `any`
- **`srcLevel`** `number`
- **`dstLevel`** `number`

**Returns:** `void`

**Calls:**

- `this.textureUtils.copyTextureToTexture`

<details><summary>Code</summary>

```typescript
copyTextureToTexture( srcTexture, dstTexture, srcRegion = null, dstPosition = null, srcLevel = 0, dstLevel = 0 ) {

		this.textureUtils.copyTextureToTexture( srcTexture, dstTexture, srcRegion, dstPosition, srcLevel, dstLevel );

	}
```
</details>

### `WebGLBackend.copyFramebufferToTexture(texture: Texture, renderContext: RenderContext, rectangle: Vector4): void`

**JSDoc:**
```typescript
/**
	 * Copies the current bound framebuffer to the given texture.
	 *
	 * @param {Texture} texture - The destination texture.
	 * @param {RenderContext} renderContext - The render context.
	 * @param {Vector4} rectangle - A four dimensional vector defining the origin and dimension of the copy.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`renderContext`** `RenderContext`
- **`rectangle`** `Vector4`

**Returns:** `void`

**Calls:**

- `this.textureUtils.copyFramebufferToTexture`

<details><summary>Code</summary>

```typescript
copyFramebufferToTexture( texture, renderContext, rectangle ) {

		this.textureUtils.copyFramebufferToTexture( texture, renderContext, rectangle );

	}
```
</details>

### `WebGLBackend._setFramebuffer(descriptor: RenderContext): void`

**JSDoc:**
```typescript
/**
	 * Configures the active framebuffer from the given render context.
	 *
	 * @private
	 * @param {RenderContext} descriptor - The render context.
	 */
```

**Parameters:**

- **`descriptor`** `RenderContext`

**Returns:** `void`

**Calls:**

- `this.get`
- `this.extensions.get`
- `this._useMultisampledExtension`
- `getCacheKey (from ../common/RenderContext.js)`
- `gl.createFramebuffer`
- `state.bindFramebuffer`
- `gl.framebufferTexture2D`
- `multiviewExt.framebufferTextureMultisampleMultiviewOVR`
- `gl.framebufferTextureLayer`
- `multisampledRTTExt.framebufferTexture2DMultisampleEXT`
- `gl.createRenderbuffer`
- `this.textureUtils.setupRenderBufferStorage`
- `depthInvalidationArray.push`
- `gl.bindRenderbuffer`
- `gl.framebufferRenderbuffer`
- `this._isRenderCameraDepthArray`
- `invalidationArray.push`
- `gl.renderbufferStorageMultisample`
- `state.drawBuffers`

**Internal Comments:**
```
// rebind external XR textures
// rebind color (x2)
// rebind depth (x2)
```

<details><summary>Code</summary>

```typescript
_setFramebuffer( descriptor ) {

		const { gl, state } = this;

		let currentFrameBuffer = null;

		if ( descriptor.textures !== null ) {

			const renderTarget = descriptor.renderTarget;
			const renderTargetContextData = this.get( renderTarget );
			const { samples, depthBuffer, stencilBuffer } = renderTarget;

			const isCube = renderTarget.isWebGLCubeRenderTarget === true;
			const isRenderTarget3D = renderTarget.isRenderTarget3D === true;
			const isRenderTargetArray = renderTarget.depth > 1;
			const isXRRenderTarget = renderTarget.isXRRenderTarget === true;
			const _hasExternalTextures = ( isXRRenderTarget === true && renderTarget._hasExternalTextures === true );

			let msaaFb = renderTargetContextData.msaaFrameBuffer;
			let depthRenderbuffer = renderTargetContextData.depthRenderbuffer;
			const multisampledRTTExt = this.extensions.get( 'WEBGL_multisampled_render_to_texture' );
			const multiviewExt = this.extensions.get( 'OVR_multiview2' );
			const useMultisampledRTT = this._useMultisampledExtension( renderTarget );
			const cacheKey = getCacheKey( descriptor );

			let fb;

			if ( isCube ) {

				renderTargetContextData.cubeFramebuffers || ( renderTargetContextData.cubeFramebuffers = {} );

				fb = renderTargetContextData.cubeFramebuffers[ cacheKey ];

			} else if ( isXRRenderTarget && _hasExternalTextures === false ) {

				fb = this._xrFramebuffer;

			} else {

				renderTargetContextData.framebuffers || ( renderTargetContextData.framebuffers = {} );

				fb = renderTargetContextData.framebuffers[ cacheKey ];

			}

			if ( fb === undefined ) {

				fb = gl.createFramebuffer();

				state.bindFramebuffer( gl.FRAMEBUFFER, fb );

				const textures = descriptor.textures;
				const depthInvalidationArray = [];

				if ( isCube ) {

					renderTargetContextData.cubeFramebuffers[ cacheKey ] = fb;

					const { textureGPU } = this.get( textures[ 0 ] );

					const cubeFace = this.renderer._activeCubeFace;

					gl.framebufferTexture2D( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0, gl.TEXTURE_CUBE_MAP_POSITIVE_X + cubeFace, textureGPU, 0 );

				} else {

					renderTargetContextData.framebuffers[ cacheKey ] = fb;

					for ( let i = 0; i < textures.length; i ++ ) {

						const texture = textures[ i ];
						const textureData = this.get( texture );
						textureData.renderTarget = descriptor.renderTarget;
						textureData.cacheKey = cacheKey; // required for copyTextureToTexture()

						const attachment = gl.COLOR_ATTACHMENT0 + i;

						if ( renderTarget.multiview ) {

							multiviewExt.framebufferTextureMultisampleMultiviewOVR( gl.FRAMEBUFFER, attachment, textureData.textureGPU, 0, samples, 0, 2 );

						} else if ( isRenderTarget3D || isRenderTargetArray ) {

							const layer = this.renderer._activeCubeFace;

							gl.framebufferTextureLayer( gl.FRAMEBUFFER, attachment, textureData.textureGPU, 0, layer );

						} else {

							if ( useMultisampledRTT ) {

								multisampledRTTExt.framebufferTexture2DMultisampleEXT( gl.FRAMEBUFFER, attachment, gl.TEXTURE_2D, textureData.textureGPU, 0, samples );

							} else {

								gl.framebufferTexture2D( gl.FRAMEBUFFER, attachment, gl.TEXTURE_2D, textureData.textureGPU, 0 );

							}

						}

					}

				}

				const depthStyle = stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT;

				if ( renderTarget._autoAllocateDepthBuffer === true ) {

					const renderbuffer = gl.createRenderbuffer();
					this.textureUtils.setupRenderBufferStorage( renderbuffer, descriptor, 0, useMultisampledRTT );
					renderTargetContextData.xrDepthRenderbuffer = renderbuffer;
					depthInvalidationArray.push( stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT );

					gl.bindRenderbuffer( gl.RENDERBUFFER, renderbuffer );
					gl.framebufferRenderbuffer( gl.FRAMEBUFFER, depthStyle, gl.RENDERBUFFER, renderbuffer );


				} else {

					if ( descriptor.depthTexture !== null ) {

						depthInvalidationArray.push( stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT );

						const textureData = this.get( descriptor.depthTexture );
						textureData.renderTarget = descriptor.renderTarget;
						textureData.cacheKey = cacheKey; // required for copyTextureToTexture()

						if ( renderTarget.multiview ) {

							multiviewExt.framebufferTextureMultisampleMultiviewOVR( gl.FRAMEBUFFER, depthStyle, textureData.textureGPU, 0, samples, 0, 2 );

						} else if ( _hasExternalTextures && useMultisampledRTT ) {

							multisampledRTTExt.framebufferTexture2DMultisampleEXT( gl.FRAMEBUFFER, depthStyle, gl.TEXTURE_2D, textureData.textureGPU, 0, samples );

						} else {

							if ( descriptor.depthTexture.isArrayTexture ) {

								const layer = this.renderer._activeCubeFace;

								gl.framebufferTextureLayer( gl.FRAMEBUFFER, depthStyle, textureData.textureGPU, 0, layer );

							} else {

								gl.framebufferTexture2D( gl.FRAMEBUFFER, depthStyle, gl.TEXTURE_2D, textureData.textureGPU, 0 );

							}

						}

					}

				}

				renderTargetContextData.depthInvalidationArray = depthInvalidationArray;


			} else {

				const isRenderCameraDepthArray = this._isRenderCameraDepthArray( descriptor );

				if ( isRenderCameraDepthArray ) {

					state.bindFramebuffer( gl.FRAMEBUFFER, fb );

					const layer = this.renderer._activeCubeFace;

					const depthData = this.get( descriptor.depthTexture );
					const depthStyle = stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT;
					gl.framebufferTextureLayer(
						gl.FRAMEBUFFER,
						depthStyle,
						depthData.textureGPU,
						0,
						layer
					);

				}

				// rebind external XR textures

				if ( ( isXRRenderTarget || useMultisampledRTT || renderTarget.multiview ) && ( renderTarget._isOpaqueFramebuffer !== true ) ) {

					state.bindFramebuffer( gl.FRAMEBUFFER, fb );

					// rebind color

					const textureData = this.get( descriptor.textures[ 0 ] );

					if ( renderTarget.multiview ) {

						multiviewExt.framebufferTextureMultisampleMultiviewOVR( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0, textureData.textureGPU, 0, samples, 0, 2 );

					} else if ( useMultisampledRTT ) {

						multisampledRTTExt.framebufferTexture2DMultisampleEXT( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0, gl.TEXTURE_2D, textureData.textureGPU, 0, samples );

					} else {

						gl.framebufferTexture2D( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0, gl.TEXTURE_2D, textureData.textureGPU, 0 );

					}

					// rebind depth

					const depthStyle = stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT;

					if ( renderTarget._autoAllocateDepthBuffer === true ) {

						const renderbuffer = renderTargetContextData.xrDepthRenderbuffer;
						gl.bindRenderbuffer( gl.RENDERBUFFER, renderbuffer );
						gl.framebufferRenderbuffer( gl.FRAMEBUFFER, depthStyle, gl.RENDERBUFFER, renderbuffer );

					} else {

						const textureData = this.get( descriptor.depthTexture );

						if ( renderTarget.multiview ) {

							multiviewExt.framebufferTextureMultisampleMultiviewOVR( gl.FRAMEBUFFER, depthStyle, textureData.textureGPU, 0, samples, 0, 2 );

						} else if ( useMultisampledRTT ) {

							multisampledRTTExt.framebufferTexture2DMultisampleEXT( gl.FRAMEBUFFER, depthStyle, gl.TEXTURE_2D, textureData.textureGPU, 0, samples );

						} else {

							gl.framebufferTexture2D( gl.FRAMEBUFFER, depthStyle, gl.TEXTURE_2D, textureData.textureGPU, 0 );

						}

					}

				}

			}

			if ( samples > 0 && useMultisampledRTT === false && ! renderTarget.multiview ) {

				if ( msaaFb === undefined ) {

					const invalidationArray = [];

					msaaFb = gl.createFramebuffer();

					state.bindFramebuffer( gl.FRAMEBUFFER, msaaFb );

					const msaaRenderbuffers = [];

					const textures = descriptor.textures;

					for ( let i = 0; i < textures.length; i ++ ) {

						msaaRenderbuffers[ i ] = gl.createRenderbuffer();

						gl.bindRenderbuffer( gl.RENDERBUFFER, msaaRenderbuffers[ i ] );

						invalidationArray.push( gl.COLOR_ATTACHMENT0 + i );

						const texture = descriptor.textures[ i ];
						const textureData = this.get( texture );

						gl.renderbufferStorageMultisample( gl.RENDERBUFFER, samples, textureData.glInternalFormat, descriptor.width, descriptor.height );
						gl.framebufferRenderbuffer( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0 + i, gl.RENDERBUFFER, msaaRenderbuffers[ i ] );


					}

					gl.bindRenderbuffer( gl.RENDERBUFFER, null );

					renderTargetContextData.msaaFrameBuffer = msaaFb;
					renderTargetContextData.msaaRenderbuffers = msaaRenderbuffers;

					if ( depthBuffer && depthRenderbuffer === undefined ) {

						depthRenderbuffer = gl.createRenderbuffer();
						this.textureUtils.setupRenderBufferStorage( depthRenderbuffer, descriptor, samples );

						renderTargetContextData.depthRenderbuffer = depthRenderbuffer;

						const depthStyle = stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT;
						invalidationArray.push( depthStyle );

					}

					renderTargetContextData.invalidationArray = invalidationArray;

				}

				currentFrameBuffer = renderTargetContextData.msaaFrameBuffer;

			} else {

				currentFrameBuffer = fb;

			}

			state.drawBuffers( descriptor, fb );

		}

		state.bindFramebuffer( gl.FRAMEBUFFER, currentFrameBuffer );

	}
```
</details>

### `WebGLBackend._getVaoKey(attributes: BufferAttribute[]): string`

**JSDoc:**
```typescript
/**
	 * Computes the VAO key for the given index and attributes.
	 *
	 * @private
	 * @param {Array<BufferAttribute>} attributes - An array of buffer attributes.
	 * @return {string} The VAO key.
	 */
```

**Parameters:**

- **`attributes`** `BufferAttribute[]`

**Returns:** `string`

**Calls:**

- `this.get`

<details><summary>Code</summary>

```typescript
_getVaoKey( attributes ) {

		let key = '';

		for ( let i = 0; i < attributes.length; i ++ ) {

			const attributeData = this.get( attributes[ i ] );

			key += ':' + attributeData.id;

		}

		return key;

	}
```
</details>

### `WebGLBackend._createVao(attributes: BufferAttribute[]): any`

**JSDoc:**
```typescript
/**
	 * Creates a VAO from the index and attributes.
	 *
	 * @private
	 * @param {Array<BufferAttribute>} attributes - An array of buffer attributes.
	 * @return {Object} The VAO data.
	 */
```

**Parameters:**

- **`attributes`** `BufferAttribute[]`

**Returns:** `any`

**Calls:**

- `gl.createVertexArray`
- `gl.bindVertexArray`
- `this.get`
- `gl.bindBuffer`
- `gl.enableVertexAttribArray`
- `gl.vertexAttribIPointer`
- `gl.vertexAttribPointer`
- `gl.vertexAttribDivisor`

<details><summary>Code</summary>

```typescript
_createVao( attributes ) {

		const { gl } = this;

		const vaoGPU = gl.createVertexArray();

		gl.bindVertexArray( vaoGPU );

		for ( let i = 0; i < attributes.length; i ++ ) {

			const attribute = attributes[ i ];
			const attributeData = this.get( attribute );

			gl.bindBuffer( gl.ARRAY_BUFFER, attributeData.bufferGPU );
			gl.enableVertexAttribArray( i );

			let stride, offset;

			if ( attribute.isInterleavedBufferAttribute === true ) {

				stride = attribute.data.stride * attributeData.bytesPerElement;
				offset = attribute.offset * attributeData.bytesPerElement;

			} else {

				stride = 0;
				offset = 0;

			}

			if ( attributeData.isInteger ) {

				gl.vertexAttribIPointer( i, attribute.itemSize, attributeData.type, stride, offset );

			} else {

				gl.vertexAttribPointer( i, attribute.itemSize, attributeData.type, attribute.normalized, stride, offset );

			}

			if ( attribute.isInstancedBufferAttribute && ! attribute.isInterleavedBufferAttribute ) {

				gl.vertexAttribDivisor( i, attribute.meshPerAttribute );

			} else if ( attribute.isInterleavedBufferAttribute && attribute.data.isInstancedInterleavedBuffer ) {

				gl.vertexAttribDivisor( i, attribute.data.meshPerAttribute );

			}

		}

		gl.bindBuffer( gl.ARRAY_BUFFER, null );

		return vaoGPU;

	}
```
</details>

### `WebGLBackend._getTransformFeedback(transformBuffers: DualAttributeData[]): WebGLTransformFeedback`

**JSDoc:**
```typescript
/**
	 * Creates a transform feedback from the given transform buffers.
	 *
	 * @private
	 * @param {Array<DualAttributeData>} transformBuffers - The transform buffers.
	 * @return {WebGLTransformFeedback} The transform feedback.
	 */
```

**Parameters:**

- **`transformBuffers`** `DualAttributeData[]`

**Returns:** `WebGLTransformFeedback`

**Calls:**

- `gl.createTransformFeedback`
- `gl.bindTransformFeedback`
- `gl.bindBufferBase`

<details><summary>Code</summary>

```typescript
_getTransformFeedback( transformBuffers ) {

		let key = '';

		for ( let i = 0; i < transformBuffers.length; i ++ ) {

			key += ':' + transformBuffers[ i ].id;

		}

		let transformFeedbackGPU = this.transformFeedbackCache[ key ];

		if ( transformFeedbackGPU !== undefined ) {

			return transformFeedbackGPU;

		}

		const { gl } = this;

		transformFeedbackGPU = gl.createTransformFeedback();

		gl.bindTransformFeedback( gl.TRANSFORM_FEEDBACK, transformFeedbackGPU );

		for ( let i = 0; i < transformBuffers.length; i ++ ) {

			const attributeData = transformBuffers[ i ];

			gl.bindBufferBase( gl.TRANSFORM_FEEDBACK_BUFFER, i, attributeData.transformBuffer );

		}

		gl.bindTransformFeedback( gl.TRANSFORM_FEEDBACK, null );

		this.transformFeedbackCache[ key ] = transformFeedbackGPU;

		return transformFeedbackGPU;

	}
```
</details>

### `WebGLBackend._setupBindings(bindings: BindGroup[], programGPU: WebGLProgram): void`

**JSDoc:**
```typescript
/**
	 * Setups the given bindings.
	 *
	 * @private
	 * @param {Array<BindGroup>} bindings - The bindings.
	 * @param {WebGLProgram} programGPU - The WebGL program.
	 */
```

**Parameters:**

- **`bindings`** `BindGroup[]`
- **`programGPU`** `WebGLProgram`

**Returns:** `void`

**Calls:**

- `this.get`
- `gl.getUniformBlockIndex`
- `gl.uniformBlockBinding`
- `gl.getUniformLocation`
- `gl.uniform1i`

<details><summary>Code</summary>

```typescript
_setupBindings( bindings, programGPU ) {

		const gl = this.gl;

		for ( const bindGroup of bindings ) {

			for ( const binding of bindGroup.bindings ) {

				const bindingData = this.get( binding );
				const index = bindingData.index;

				if ( binding.isUniformsGroup || binding.isUniformBuffer ) {

					const location = gl.getUniformBlockIndex( programGPU, binding.name );
					gl.uniformBlockBinding( programGPU, location, index );

				} else if ( binding.isSampledTexture ) {

					const location = gl.getUniformLocation( programGPU, binding.name );
					gl.uniform1i( location, index );

				}

			}

		}

	}
```
</details>

### `WebGLBackend._bindUniforms(bindings: BindGroup[]): void`

**JSDoc:**
```typescript
/**
	 * Binds the given uniforms.
	 *
	 * @private
	 * @param {Array<BindGroup>} bindings - The bindings.
	 */
```

**Parameters:**

- **`bindings`** `BindGroup[]`

**Returns:** `void`

**Calls:**

- `this.get`
- `state.bindBufferBase`
- `state.bindTexture`

**Internal Comments:**
```
// TODO USE bindBufferRange to group multiple uniform buffers (x4)
```

<details><summary>Code</summary>

```typescript
_bindUniforms( bindings ) {

		const { gl, state } = this;

		for ( const bindGroup of bindings ) {

			for ( const binding of bindGroup.bindings ) {

				const bindingData = this.get( binding );
				const index = bindingData.index;

				if ( binding.isUniformsGroup || binding.isUniformBuffer ) {

					// TODO USE bindBufferRange to group multiple uniform buffers
					state.bindBufferBase( gl.UNIFORM_BUFFER, index, bindingData.bufferGPU );

				} else if ( binding.isSampledTexture ) {

					state.bindTexture( bindingData.glTextureType, bindingData.textureGPU, gl.TEXTURE0 + index );

				}

			}

		}

	}
```
</details>

### `WebGLBackend._useMultisampledExtension(renderTarget: RenderTarget): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the `WEBGL_multisampled_render_to_texture` extension
	 * should be used when MSAA is enabled.
	 *
	 * @private
	 * @param {RenderTarget} renderTarget - The render target that should be multisampled.
	 * @return {boolean} Whether to use the `WEBGL_multisampled_render_to_texture` extension for MSAA or not.
	 */
```

**Parameters:**

- **`renderTarget`** `RenderTarget`

**Returns:** `boolean`

**Calls:**

- `this.extensions.has`

<details><summary>Code</summary>

```typescript
_useMultisampledExtension( renderTarget ) {

		if ( renderTarget.multiview === true ) {

			return true;

		}

		return renderTarget.samples > 0 && this.extensions.has( 'WEBGL_multisampled_render_to_texture' ) === true && renderTarget._autoAllocateDepthBuffer !== false;

	}
```
</details>

### `WebGLBackend.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources.
	 */
```

**Returns:** `void`

**Calls:**

- `this.extensions.get`
- `extension.loseContext`
- `this.renderer.domElement.removeEventListener`

<details><summary>Code</summary>

```typescript
dispose() {

		const extension = this.extensions.get( 'WEBGL_lose_context' );
		if ( extension ) extension.loseContext();

		this.renderer.domElement.removeEventListener( 'webglcontextlost', this._onContextLost );

	}
```
</details>

### `onContextLost(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `event.preventDefault`
- `renderer.onDeviceLost`

<details><summary>Code</summary>

```typescript
function onContextLost( event ) {

			event.preventDefault();

			const contextLossInfo = {
				api: 'WebGL',
				message: event.statusMessage || 'Unknown reason',
				reason: null,
				originalEvent: event
			};

			renderer.onDeviceLost( contextLossInfo );

		}
```
</details>

### `check(): void`

**Returns:** `void`

**Calls:**

- `gl.getQueryParameter`
- `occluded.add`
- `gl.deleteQuery`
- `requestAnimationFrame`

**Internal Comments:**
```
// check all queries and requeue as appropriate
```

<details><summary>Code</summary>

```typescript
() => {

				let completed = 0;

				// check all queries and requeue as appropriate
				for ( let i = 0; i < currentOcclusionQueries.length; i ++ ) {

					const query = currentOcclusionQueries[ i ];

					if ( query === null ) continue;

					if ( gl.getQueryParameter( query, gl.QUERY_RESULT_AVAILABLE ) ) {

						if ( gl.getQueryParameter( query, gl.QUERY_RESULT ) === 0 ) occluded.add( currentOcclusionQueryObjects[ i ] );

						currentOcclusionQueries[ i ] = null;
						gl.deleteQuery( query );

						completed ++;

					}

				}

				if ( completed < currentOcclusionQueries.length ) {

					requestAnimationFrame( check );

				} else {

					renderContextData.occluded = occluded;

				}

			}
```
</details>

### `draw(): void`

**Returns:** `void`

**Calls:**

- `warnOnce (from ../../utils.js)`
- `renderer.renderMultiDrawInstances`
- `this.hasFeature`
- `renderer.renderMultiDraw`
- `renderer.renderInstances`
- `renderer.render`

**Internal Comments:**
```
// @deprecated, r174 (x3)
```

<details><summary>Code</summary>

```typescript
() => {

			if ( object.isBatchedMesh ) {

				if ( object._multiDrawInstances !== null ) {

					// @deprecated, r174
					warnOnce( 'THREE.WebGLBackend: renderMultiDrawInstances has been deprecated and will be removed in r184. Append to renderMultiDraw arguments and use indirection.' );
					renderer.renderMultiDrawInstances( object._multiDrawStarts, object._multiDrawCounts, object._multiDrawCount, object._multiDrawInstances );

				} else if ( ! this.hasFeature( 'WEBGL_multi_draw' ) ) {

					warnOnce( 'THREE.WebGLRenderer: WEBGL_multi_draw not supported.' );

				} else {

					renderer.renderMultiDraw( object._multiDrawStarts, object._multiDrawCounts, object._multiDrawCount );

				}

			} else if ( instanceCount > 1 ) {

				renderer.renderInstances( firstVertex, vertexCount, instanceCount );

			} else {

				renderer.render( firstVertex, vertexCount );

			}

		}
```
</details>

### `checkStatus(): void`

**Returns:** `void`

**Calls:**

- `gl.getProgramParameter`
- `this._completeCompile`
- `resolve`
- `requestAnimationFrame`

<details><summary>Code</summary>

```typescript
() => {

					if ( gl.getProgramParameter( programGPU, parallel.COMPLETION_STATUS_KHR ) ) {

						this._completeCompile( renderObject, pipeline );
						resolve();

					} else {

						requestAnimationFrame( checkStatus );

					}

				}
```
</details>


---

## Classes

### `WebGLBackend`

<details><summary>Class Code</summary>

```ts
class WebGLBackend extends Backend {

	/**
	 * WebGLBackend options.
	 *
	 * @typedef {Object} WebGLBackend~Options
	 * @property {boolean} [logarithmicDepthBuffer=false] - Whether logarithmic depth buffer is enabled or not.
	 * @property {boolean} [alpha=true] - Whether the default framebuffer (which represents the final contents of the canvas) should be transparent or opaque.
	 * @property {boolean} [depth=true] - Whether the default framebuffer should have a depth buffer or not.
	 * @property {boolean} [stencil=false] - Whether the default framebuffer should have a stencil buffer or not.
	 * @property {boolean} [antialias=false] - Whether MSAA as the default anti-aliasing should be enabled or not.
	 * @property {number} [samples=0] - When `antialias` is `true`, `4` samples are used by default. Set this parameter to any other integer value than 0 to overwrite the default.
	 * @property {boolean} [forceWebGL=false] - If set to `true`, the renderer uses a WebGL 2 backend no matter if WebGPU is supported or not.
	 * @property {WebGL2RenderingContext} [context=undefined] - A WebGL 2 rendering context.
	 */

	/**
	 * Constructs a new WebGPU backend.
	 *
	 * @param {WebGLBackend~Options} [parameters] - The configuration parameter.
	 */
	constructor( parameters = {} ) {

		super( parameters );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isWebGLBackend = true;

		/**
		 * A reference to a backend module holding shader attribute-related
		 * utility functions.
		 *
		 * @type {?WebGLAttributeUtils}
		 * @default null
		 */
		this.attributeUtils = null;

		/**
		 * A reference to a backend module holding extension-related
		 * utility functions.
		 *
		 * @type {?WebGLExtensions}
		 * @default null
		 */
		this.extensions = null;

		/**
		 * A reference to a backend module holding capability-related
		 * utility functions.
		 *
		 * @type {?WebGLCapabilities}
		 * @default null
		 */
		this.capabilities = null;

		/**
		 * A reference to a backend module holding texture-related
		 * utility functions.
		 *
		 * @type {?WebGLTextureUtils}
		 * @default null
		 */
		this.textureUtils = null;

		/**
		 * A reference to a backend module holding renderer-related
		 * utility functions.
		 *
		 * @type {?WebGLBufferRenderer}
		 * @default null
		 */
		this.bufferRenderer = null;

		/**
		 * A reference to the rendering context.
		 *
		 * @type {?WebGL2RenderingContext}
		 * @default null
		 */
		this.gl = null;

		/**
		 * A reference to a backend module holding state-related
		 * utility functions.
		 *
		 * @type {?WebGLState}
		 * @default null
		 */
		this.state = null;

		/**
		 * A reference to a backend module holding common
		 * utility functions.
		 *
		 * @type {?WebGLUtils}
		 * @default null
		 */
		this.utils = null;

		/**
		 * Dictionary for caching VAOs.
		 *
		 * @type {Object<string,WebGLVertexArrayObject>}
		 */
		this.vaoCache = {};

		/**
		 * Dictionary for caching transform feedback objects.
		 *
		 * @type {Object<string,WebGLTransformFeedback>}
		 */
		this.transformFeedbackCache = {};

		/**
		 * Controls if `gl.RASTERIZER_DISCARD` should be enabled or not.
		 * Only relevant when using compute shaders.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.discard = false;

		/**
		 * A reference to the `EXT_disjoint_timer_query_webgl2` extension. `null` if the
		 * device does not support the extension.
		 *
		 * @type {?EXTDisjointTimerQueryWebGL2}
		 * @default null
		 */
		this.disjoint = null;

		/**
		* A reference to the `KHR_parallel_shader_compile` extension. `null` if the
		* device does not support the extension.
		*
		* @type {?KHRParallelShaderCompile}
		* @default null
		*/
		this.parallel = null;

		/**
		 * A reference to the current render context.
		 *
		 * @private
		 * @type {RenderContext}
		 * @default null
		 */
		this._currentContext = null;

		/**
		 * A unique collection of bindings.
		 *
		 * @private
		 * @type {WeakSet<Array<BindGroup>>}
		 */
		this._knownBindings = new WeakSet();


		/**
		 * Whether the device supports framebuffers invalidation or not.
		 *
		 * @private
		 * @type {boolean}
		 */
		this._supportsInvalidateFramebuffer = typeof navigator === 'undefined' ? false : /OculusBrowser/g.test( navigator.userAgent );

		/**
		 * The target framebuffer when rendering with
		 * the WebXR device API.
		 *
		 * @private
		 * @type {WebGLFramebuffer}
		 * @default null
		 */
		this._xrFramebuffer = null;

	}

	/**
	 * Initializes the backend so it is ready for usage.
	 *
	 * @param {Renderer} renderer - The renderer.
	 */
	init( renderer ) {

		super.init( renderer );

		//

		const parameters = this.parameters;

		const contextAttributes = {
			antialias: renderer.samples > 0,
			alpha: true, // always true for performance reasons
			depth: renderer.depth,
			stencil: renderer.stencil
		};

		const glContext = ( parameters.context !== undefined ) ? parameters.context : renderer.domElement.getContext( 'webgl2', contextAttributes );

	 	function onContextLost( event ) {

			event.preventDefault();

			const contextLossInfo = {
				api: 'WebGL',
				message: event.statusMessage || 'Unknown reason',
				reason: null,
				originalEvent: event
			};

			renderer.onDeviceLost( contextLossInfo );

		}

		this._onContextLost = onContextLost;

		renderer.domElement.addEventListener( 'webglcontextlost', onContextLost, false );

		this.gl = glContext;

		this.extensions = new WebGLExtensions( this );
		this.capabilities = new WebGLCapabilities( this );
		this.attributeUtils = new WebGLAttributeUtils( this );
		this.textureUtils = new WebGLTextureUtils( this );
		this.bufferRenderer = new WebGLBufferRenderer( this );

		this.state = new WebGLState( this );
		this.utils = new WebGLUtils( this );

		this.extensions.get( 'EXT_color_buffer_float' );
		this.extensions.get( 'WEBGL_clip_cull_distance' );
		this.extensions.get( 'OES_texture_float_linear' );
		this.extensions.get( 'EXT_color_buffer_half_float' );
		this.extensions.get( 'WEBGL_multisampled_render_to_texture' );
		this.extensions.get( 'WEBGL_render_shared_exponent' );
		this.extensions.get( 'WEBGL_multi_draw' );
		this.extensions.get( 'OVR_multiview2' );

		this.disjoint = this.extensions.get( 'EXT_disjoint_timer_query_webgl2' );
		this.parallel = this.extensions.get( 'KHR_parallel_shader_compile' );

	}

	/**
	 * The coordinate system of the backend.
	 *
	 * @type {number}
	 * @readonly
	 */
	get coordinateSystem() {

		return WebGLCoordinateSystem;

	}

	/**
	 * This method performs a readback operation by moving buffer data from
	 * a storage buffer attribute from the GPU to the CPU.
	 *
	 * @async
	 * @param {StorageBufferAttribute} attribute - The storage buffer attribute.
	 * @return {Promise<ArrayBuffer>} A promise that resolves with the buffer data when the data are ready.
	 */
	async getArrayBufferAsync( attribute ) {

		return await this.attributeUtils.getArrayBufferAsync( attribute );

	}

	/**
	 * Can be used to synchronize CPU operations with GPU tasks. So when this method is called,
	 * the CPU waits for the GPU to complete its operation (e.g. a compute task).
	 *
	 * @async
	 * @return {Promise} A Promise that resolves when synchronization has been finished.
	 */
	async waitForGPU() {

		await this.utils._clientWaitAsync();

	}

	/**
	 * Ensures the backend is XR compatible.
	 *
	 * @async
	 * @return {Promise} A Promise that resolve when the renderer is XR compatible.
	 */
	async makeXRCompatible() {

		const attributes = this.gl.getContextAttributes();

		if ( attributes.xrCompatible !== true ) {

			await this.gl.makeXRCompatible();

		}

	}
	/**
	 * Sets the XR rendering destination.
	 *
	 * @param {WebGLFramebuffer} xrFramebuffer - The XR framebuffer.
	 */
	setXRTarget( xrFramebuffer ) {

		this._xrFramebuffer = xrFramebuffer;

	}

	/**
	 * Configures the given XR render target with external textures.
	 *
	 * This method is only relevant when using the WebXR Layers API.
	 *
	 * @param {XRRenderTarget} renderTarget - The XR render target.
	 * @param {WebGLTexture} colorTexture - A native color texture.
	 * @param {?WebGLTexture} [depthTexture=null] - A native depth texture.
	 */
	setXRRenderTargetTextures( renderTarget, colorTexture, depthTexture = null ) {

		const gl = this.gl;

		this.set( renderTarget.texture, { textureGPU: colorTexture, glInternalFormat: gl.RGBA8 } ); // see #24698 why RGBA8 and not SRGB8_ALPHA8 is used

		if ( depthTexture !== null ) {

			const glInternalFormat = renderTarget.stencilBuffer ? gl.DEPTH24_STENCIL8 : gl.DEPTH_COMPONENT24;

			this.set( renderTarget.depthTexture, { textureGPU: depthTexture, glInternalFormat: glInternalFormat } );

			// The multisample_render_to_texture extension doesn't work properly if there
			// are midframe flushes and an external depth texture.
			if ( ( this.extensions.has( 'WEBGL_multisampled_render_to_texture' ) === true ) && renderTarget._autoAllocateDepthBuffer === true && renderTarget.multiview === false ) {

				console.warn( 'THREE.WebGLBackend: Render-to-texture extension was disabled because an external texture was provided' );

			}

			renderTarget._autoAllocateDepthBuffer = false;

		}

	}

	/**
	 * Inits a time stamp query for the given render context.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 */
	initTimestampQuery( renderContext ) {

		if ( ! this.disjoint || ! this.trackTimestamp ) return;

		const type = renderContext.isComputeNode ? 'compute' : 'render';

		if ( ! this.timestampQueryPool[ type ] ) {

			// TODO: Variable maxQueries?
			this.timestampQueryPool[ type ] = new WebGLTimestampQueryPool( this.gl, type, 2048 );

		}

		const timestampQueryPool = this.timestampQueryPool[ type ];

		const baseOffset = timestampQueryPool.allocateQueriesForContext( renderContext );

		if ( baseOffset !== null ) {

			timestampQueryPool.beginQuery( renderContext );

		}

	}

	// timestamp utils

	/**
	 * Prepares the timestamp buffer.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 */
	prepareTimestampBuffer( renderContext ) {

		if ( ! this.disjoint || ! this.trackTimestamp ) return;

		const type = renderContext.isComputeNode ? 'compute' : 'render';
		const timestampQueryPool = this.timestampQueryPool[ type ];

		timestampQueryPool.endQuery( renderContext );

	}


	/**
	 * Returns the backend's rendering context.
	 *
	 * @return {WebGL2RenderingContext} The rendering context.
	 */
	getContext() {

		return this.gl;

	}

	/**
	 * This method is executed at the beginning of a render call and prepares
	 * the WebGL state for upcoming render calls
	 *
	 * @param {RenderContext} renderContext - The render context.
	 */
	beginRender( renderContext ) {

		const { state } = this;
		const renderContextData = this.get( renderContext );

		//

		if ( renderContext.viewport ) {

			this.updateViewport( renderContext );

		} else {

			const { width, height } = this.getDrawingBufferSize();
			state.viewport( 0, 0, width, height );

		}

		if ( renderContext.scissor ) {

			const { x, y, width, height } = renderContext.scissorValue;

			state.scissor( x, renderContext.height - height - y, width, height );

		}

		//

		this.initTimestampQuery( renderContext );

		renderContextData.previousContext = this._currentContext;
		this._currentContext = renderContext;

		this._setFramebuffer( renderContext );
		this.clear( renderContext.clearColor, renderContext.clearDepth, renderContext.clearStencil, renderContext, false );

		const occlusionQueryCount = renderContext.occlusionQueryCount;

		if ( occlusionQueryCount > 0 ) {

			// Get a reference to the array of objects with queries. The renderContextData property
			// can be changed by another render pass before the async reading of all previous queries complete
			renderContextData.currentOcclusionQueries = renderContextData.occlusionQueries;
			renderContextData.currentOcclusionQueryObjects = renderContextData.occlusionQueryObjects;

			renderContextData.lastOcclusionObject = null;
			renderContextData.occlusionQueries = new Array( occlusionQueryCount );
			renderContextData.occlusionQueryObjects = new Array( occlusionQueryCount );
			renderContextData.occlusionQueryIndex = 0;

		}

	}

	/**
	 * This method is executed at the end of a render call and finalizes work
	 * after draw calls.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 */
	finishRender( renderContext ) {

		const { gl, state } = this;
		const renderContextData = this.get( renderContext );
		const previousContext = renderContextData.previousContext;

		state.resetVertexState();

		const occlusionQueryCount = renderContext.occlusionQueryCount;

		if ( occlusionQueryCount > 0 ) {

			if ( occlusionQueryCount > renderContextData.occlusionQueryIndex ) {

				gl.endQuery( gl.ANY_SAMPLES_PASSED );

			}

			this.resolveOccludedAsync( renderContext );

		}

		const textures = renderContext.textures;

		if ( textures !== null ) {

			for ( let i = 0; i < textures.length; i ++ ) {

				const texture = textures[ i ];

				if ( texture.generateMipmaps ) {

					this.generateMipmaps( texture );

				}

			}

		}

		this._currentContext = previousContext;
		const renderTarget = renderContext.renderTarget;

		if ( renderContext.textures !== null && renderTarget ) {

			const renderTargetContextData = this.get( renderTarget );

			if ( renderTarget.samples > 0 && this._useMultisampledExtension( renderTarget ) === false ) {

				const fb = renderTargetContextData.framebuffers[ renderContext.getCacheKey() ];

				let mask = gl.COLOR_BUFFER_BIT;

				if ( renderTarget.resolveDepthBuffer ) {

					if ( renderTarget.depthBuffer ) mask |= gl.DEPTH_BUFFER_BIT;
					if ( renderTarget.stencilBuffer && renderTarget.resolveStencilBuffer ) mask |= gl.STENCIL_BUFFER_BIT;

				}

				const msaaFrameBuffer = renderTargetContextData.msaaFrameBuffer;
				const msaaRenderbuffers = renderTargetContextData.msaaRenderbuffers;

				const textures = renderContext.textures;
				const isMRT = textures.length > 1;

				state.bindFramebuffer( gl.READ_FRAMEBUFFER, msaaFrameBuffer );
				state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, fb );

				if ( isMRT ) {

					// blitFramebuffer() can only copy/resolve the first color attachment of a framebuffer. When using MRT,
					// the engine temporarily removes all attachments and then configures each attachment for the resolve.

					for ( let i = 0; i < textures.length; i ++ ) {

						gl.framebufferRenderbuffer( gl.READ_FRAMEBUFFER, gl.COLOR_ATTACHMENT0 + i, gl.RENDERBUFFER, null );
						gl.framebufferTexture2D( gl.DRAW_FRAMEBUFFER, gl.COLOR_ATTACHMENT0 + i, gl.TEXTURE_2D, null, 0 );

					}

				}

				for ( let i = 0; i < textures.length; i ++ ) {

					if ( isMRT ) {

						// configure attachment for resolve

						const { textureGPU } = this.get( textures[ i ] );

						gl.framebufferRenderbuffer( gl.READ_FRAMEBUFFER, gl.COLOR_ATTACHMENT0, gl.RENDERBUFFER, msaaRenderbuffers[ i ] );
						gl.framebufferTexture2D( gl.DRAW_FRAMEBUFFER, gl.COLOR_ATTACHMENT0, gl.TEXTURE_2D, textureGPU, 0 );

					}

					if ( renderContext.scissor ) {

						const { x, y, width, height } = renderContext.scissorValue;

						const viewY = renderContext.height - height - y;

						gl.blitFramebuffer( x, viewY, x + width, viewY + height, x, viewY, x + width, viewY + height, mask, gl.NEAREST );

					} else {

						gl.blitFramebuffer( 0, 0, renderContext.width, renderContext.height, 0, 0, renderContext.width, renderContext.height, mask, gl.NEAREST );

					}

				}

				if ( isMRT ) {

					// restore attachments

					for ( let i = 0; i < textures.length; i ++ ) {

						const { textureGPU } = this.get( textures[ i ] );

						gl.framebufferRenderbuffer( gl.READ_FRAMEBUFFER, gl.COLOR_ATTACHMENT0 + i, gl.RENDERBUFFER, msaaRenderbuffers[ i ] );
						gl.framebufferTexture2D( gl.DRAW_FRAMEBUFFER, gl.COLOR_ATTACHMENT0 + i, gl.TEXTURE_2D, textureGPU, 0 );

					}

				}

				if ( this._supportsInvalidateFramebuffer === true ) {

					gl.invalidateFramebuffer( gl.READ_FRAMEBUFFER, renderTargetContextData.invalidationArray );

				}

			} else if ( renderTarget.resolveDepthBuffer === false && renderTargetContextData.framebuffers ) {

				const fb = renderTargetContextData.framebuffers[ renderContext.getCacheKey() ];
				state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, fb );
				gl.invalidateFramebuffer( gl.DRAW_FRAMEBUFFER, renderTargetContextData.depthInvalidationArray );

			}

		}

		if ( previousContext !== null ) {

			this._setFramebuffer( previousContext );

			if ( previousContext.viewport ) {

				this.updateViewport( previousContext );

			} else {

				const { width, height } = this.getDrawingBufferSize();
				state.viewport( 0, 0, width, height );

			}

		}

		this.prepareTimestampBuffer( renderContext );

	}

	/**
	 * This method processes the result of occlusion queries and writes it
	 * into render context data.
	 *
	 * @async
	 * @param {RenderContext} renderContext - The render context.
	 */
	resolveOccludedAsync( renderContext ) {

		const renderContextData = this.get( renderContext );

		// handle occlusion query results

		const { currentOcclusionQueries, currentOcclusionQueryObjects } = renderContextData;

		if ( currentOcclusionQueries && currentOcclusionQueryObjects ) {

			const occluded = new WeakSet();
			const { gl } = this;

			renderContextData.currentOcclusionQueryObjects = null;
			renderContextData.currentOcclusionQueries = null;

			const check = () => {

				let completed = 0;

				// check all queries and requeue as appropriate
				for ( let i = 0; i < currentOcclusionQueries.length; i ++ ) {

					const query = currentOcclusionQueries[ i ];

					if ( query === null ) continue;

					if ( gl.getQueryParameter( query, gl.QUERY_RESULT_AVAILABLE ) ) {

						if ( gl.getQueryParameter( query, gl.QUERY_RESULT ) === 0 ) occluded.add( currentOcclusionQueryObjects[ i ] );

						currentOcclusionQueries[ i ] = null;
						gl.deleteQuery( query );

						completed ++;

					}

				}

				if ( completed < currentOcclusionQueries.length ) {

					requestAnimationFrame( check );

				} else {

					renderContextData.occluded = occluded;

				}

			};

			check();

		}

	}

	/**
	 * Returns `true` if the given 3D object is fully occluded by other
	 * 3D objects in the scene.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @param {Object3D} object - The 3D object to test.
	 * @return {boolean} Whether the 3D object is fully occluded or not.
	 */
	isOccluded( renderContext, object ) {

		const renderContextData = this.get( renderContext );

		return renderContextData.occluded && renderContextData.occluded.has( object );

	}

	/**
	 * Updates the viewport with the values from the given render context.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 */
	updateViewport( renderContext ) {

		const { state } = this;
		const { x, y, width, height } = renderContext.viewportValue;

		state.viewport( x, renderContext.height - height - y, width, height );

	}

	/**
	 * Defines the scissor test.
	 *
	 * @param {boolean} boolean - Whether the scissor test should be enabled or not.
	 */
	setScissorTest( boolean ) {

		const state = this.state;

		state.setScissorTest( boolean );

	}

	/**
	 * Returns the clear color and alpha into a single
	 * color object.
	 *
	 * @return {Color4} The clear color.
	 */
	getClearColor() {

		const clearColor = super.getClearColor();

		// Since the canvas is always created with alpha: true,
		// WebGL must always premultiply the clear color.

		clearColor.r *= clearColor.a;
		clearColor.g *= clearColor.a;
		clearColor.b *= clearColor.a;

		return clearColor;

	}

	/**
	 * Performs a clear operation.
	 *
	 * @param {boolean} color - Whether the color buffer should be cleared or not.
	 * @param {boolean} depth - Whether the depth buffer should be cleared or not.
	 * @param {boolean} stencil - Whether the stencil buffer should be cleared or not.
	 * @param {?Object} [descriptor=null] - The render context of the current set render target.
	 * @param {boolean} [setFrameBuffer=true] - TODO.
	 */
	clear( color, depth, stencil, descriptor = null, setFrameBuffer = true ) {

		const { gl, renderer } = this;

		if ( descriptor === null ) {

			const clearColor = this.getClearColor();

			descriptor = {
				textures: null,
				clearColorValue: clearColor
			};

		}

		//

		let clear = 0;

		if ( color ) clear |= gl.COLOR_BUFFER_BIT;
		if ( depth ) clear |= gl.DEPTH_BUFFER_BIT;
		if ( stencil ) clear |= gl.STENCIL_BUFFER_BIT;

		if ( clear !== 0 ) {

			let clearColor;

			if ( descriptor.clearColorValue ) {

				clearColor = descriptor.clearColorValue;

			} else {

				clearColor = this.getClearColor();

			}

			const clearDepth = renderer.getClearDepth();
			const clearStencil = renderer.getClearStencil();

			if ( depth ) this.state.setDepthMask( true );

			if ( descriptor.textures === null ) {

				gl.clearColor( clearColor.r, clearColor.g, clearColor.b, clearColor.a );
				gl.clear( clear );

			} else {

				if ( setFrameBuffer ) this._setFramebuffer( descriptor );

				if ( color ) {

					for ( let i = 0; i < descriptor.textures.length; i ++ ) {

						if ( i === 0 ) {

							gl.clearBufferfv( gl.COLOR, i, [ clearColor.r, clearColor.g, clearColor.b, clearColor.a ] );

						} else {

							gl.clearBufferfv( gl.COLOR, i, [ 0, 0, 0, 1 ] );

						}

					}

				}

				if ( depth && stencil ) {

					gl.clearBufferfi( gl.DEPTH_STENCIL, 0, clearDepth, clearStencil );

				} else if ( depth ) {

					gl.clearBufferfv( gl.DEPTH, 0, [ clearDepth ] );

				} else if ( stencil ) {

					gl.clearBufferiv( gl.STENCIL, 0, [ clearStencil ] );

				}

			}

		}

	}

	/**
	 * This method is executed at the beginning of a compute call and
	 * prepares the state for upcoming compute tasks.
	 *
	 * @param {Node|Array<Node>} computeGroup - The compute node(s).
	 */
	beginCompute( computeGroup ) {

		const { state, gl } = this;

		state.bindFramebuffer( gl.FRAMEBUFFER, null );
		this.initTimestampQuery( computeGroup );

	}

	/**
	 * Executes a compute command for the given compute node.
	 *
	 * @param {Node|Array<Node>} computeGroup - The group of compute nodes of a compute call. Can be a single compute node.
	 * @param {Node} computeNode - The compute node.
	 * @param {Array<BindGroup>} bindings - The bindings.
	 * @param {ComputePipeline} pipeline - The compute pipeline.
	 * @param {number|null} [count=null] - The count of compute invocations. If `null`, the count is determined by the compute node.
	 */
	compute( computeGroup, computeNode, bindings, pipeline, count = null ) {

		const { state, gl } = this;

		if ( this.discard === false ) {

			// required here to handle async behaviour of render.compute()
			gl.enable( gl.RASTERIZER_DISCARD );
			this.discard = true;

		}

		const { programGPU, transformBuffers, attributes } = this.get( pipeline );

		const vaoKey = this._getVaoKey( attributes );

		const vaoGPU = this.vaoCache[ vaoKey ];

		if ( vaoGPU === undefined ) {

			this.vaoCache[ vaoKey ] = this._createVao( attributes );

		} else {

			state.setVertexState( vaoGPU );

		}

		state.useProgram( programGPU );

		this._bindUniforms( bindings );

		const transformFeedbackGPU = this._getTransformFeedback( transformBuffers );

		gl.bindTransformFeedback( gl.TRANSFORM_FEEDBACK, transformFeedbackGPU );
		gl.beginTransformFeedback( gl.POINTS );

		count = ( count !== null ) ? count : computeNode.count;

		if ( Array.isArray( count ) ) {

			warnOnce( 'WebGLBackend.compute(): The count parameter must be a single number, not an array.' );

			count = count[ 0 ];

		}

		if ( attributes[ 0 ].isStorageInstancedBufferAttribute ) {

			gl.drawArraysInstanced( gl.POINTS, 0, 1, count );

		} else {

			gl.drawArrays( gl.POINTS, 0, count );

		}

		gl.endTransformFeedback();
		gl.bindTransformFeedback( gl.TRANSFORM_FEEDBACK, null );

		// switch active buffers

		for ( let i = 0; i < transformBuffers.length; i ++ ) {

			const dualAttributeData = transformBuffers[ i ];

			if ( dualAttributeData.pbo && this.has( dualAttributeData.pbo ) ) {

				this.textureUtils.copyBufferToTexture( dualAttributeData.transformBuffer, dualAttributeData.pbo );

			}

			dualAttributeData.switchBuffers();


		}

	}

	/**
	 * This method is executed at the end of a compute call and
	 * finalizes work after compute tasks.
	 *
	 * @param {Node|Array<Node>} computeGroup - The compute node(s).
	 */
	finishCompute( computeGroup ) {

		const gl = this.gl;

		this.discard = false;

		gl.disable( gl.RASTERIZER_DISCARD );

		this.prepareTimestampBuffer( computeGroup );

		if ( this._currentContext ) {

			this._setFramebuffer( this._currentContext );

		}

	}

	/**
	 * Internal to determine if the current render target is a render target array with depth 2D array texture.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @return {boolean} Whether the render target is a render target array with depth 2D array texture.
	 *
	 * @private
	 */
	_isRenderCameraDepthArray( renderContext ) {

		return renderContext.depthTexture && renderContext.depthTexture.isArrayTexture && renderContext.camera.isArrayCamera;

	}

	/**
	 * Executes a draw command for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object to draw.
	 * @param {Info} info - Holds a series of statistical information about the GPU memory and the rendering process.
	 */
	draw( renderObject/*, info*/ ) {

		const { object, pipeline, material, context, hardwareClippingPlanes } = renderObject;
		const { programGPU } = this.get( pipeline );

		const { gl, state } = this;

		const contextData = this.get( context );

		const drawParams = renderObject.getDrawParameters();

		if ( drawParams === null ) return;

		//

		this._bindUniforms( renderObject.getBindings() );

		const frontFaceCW = ( object.isMesh && object.matrixWorld.determinant() < 0 );

		state.setMaterial( material, frontFaceCW, hardwareClippingPlanes );

		state.useProgram( programGPU );

		// vertex state

		const attributes = renderObject.getAttributes();
		const attributesData = this.get( attributes );

		let vaoGPU = attributesData.vaoGPU;

		if ( vaoGPU === undefined ) {

			const vaoKey = this._getVaoKey( attributes );

			vaoGPU = this.vaoCache[ vaoKey ];

			if ( vaoGPU === undefined ) {

				vaoGPU = this._createVao( attributes );

				this.vaoCache[ vaoKey ] = vaoGPU;
				attributesData.vaoGPU = vaoGPU;

			}

		}

		const index = renderObject.getIndex();
		const indexGPU = ( index !== null ) ? this.get( index ).bufferGPU : null;

		state.setVertexState( vaoGPU, indexGPU );

		//

		const lastObject = contextData.lastOcclusionObject;

		if ( lastObject !== object && lastObject !== undefined ) {

			if ( lastObject !== null && lastObject.occlusionTest === true ) {

				gl.endQuery( gl.ANY_SAMPLES_PASSED );

				contextData.occlusionQueryIndex ++;

			}

			if ( object.occlusionTest === true ) {

				const query = gl.createQuery();

				gl.beginQuery( gl.ANY_SAMPLES_PASSED, query );

				contextData.occlusionQueries[ contextData.occlusionQueryIndex ] = query;
				contextData.occlusionQueryObjects[ contextData.occlusionQueryIndex ] = object;

			}

			contextData.lastOcclusionObject = object;

		}

		//
		const renderer = this.bufferRenderer;

		if ( object.isPoints ) renderer.mode = gl.POINTS;
		else if ( object.isLineSegments ) renderer.mode = gl.LINES;
		else if ( object.isLine ) renderer.mode = gl.LINE_STRIP;
		else if ( object.isLineLoop ) renderer.mode = gl.LINE_LOOP;
		else {

			if ( material.wireframe === true ) {

				state.setLineWidth( material.wireframeLinewidth * this.renderer.getPixelRatio() );
				renderer.mode = gl.LINES;

			} else {

				renderer.mode = gl.TRIANGLES;

			}

		}

		//

		const { vertexCount, instanceCount } = drawParams;
		let { firstVertex } = drawParams;

		renderer.object = object;

		if ( index !== null ) {

			firstVertex *= index.array.BYTES_PER_ELEMENT;

			const indexData = this.get( index );

			renderer.index = index.count;
			renderer.type = indexData.type;

		} else {

			renderer.index = 0;

		}

		const draw = () => {

			if ( object.isBatchedMesh ) {

				if ( object._multiDrawInstances !== null ) {

					// @deprecated, r174
					warnOnce( 'THREE.WebGLBackend: renderMultiDrawInstances has been deprecated and will be removed in r184. Append to renderMultiDraw arguments and use indirection.' );
					renderer.renderMultiDrawInstances( object._multiDrawStarts, object._multiDrawCounts, object._multiDrawCount, object._multiDrawInstances );

				} else if ( ! this.hasFeature( 'WEBGL_multi_draw' ) ) {

					warnOnce( 'THREE.WebGLRenderer: WEBGL_multi_draw not supported.' );

				} else {

					renderer.renderMultiDraw( object._multiDrawStarts, object._multiDrawCounts, object._multiDrawCount );

				}

			} else if ( instanceCount > 1 ) {

				renderer.renderInstances( firstVertex, vertexCount, instanceCount );

			} else {

				renderer.render( firstVertex, vertexCount );

			}

		};

		if ( renderObject.camera.isArrayCamera === true && renderObject.camera.cameras.length > 0 && renderObject.camera.isMultiViewCamera === false ) {

			const cameraData = this.get( renderObject.camera );
			const cameras = renderObject.camera.cameras;
			const cameraIndex = renderObject.getBindingGroup( 'cameraIndex' ).bindings[ 0 ];

			if ( cameraData.indexesGPU === undefined || cameraData.indexesGPU.length !== cameras.length ) {

				const data = new Uint32Array( [ 0, 0, 0, 0 ] );
				const indexesGPU = [];

				for ( let i = 0, len = cameras.length; i < len; i ++ ) {

					const bufferGPU = gl.createBuffer();

					data[ 0 ] = i;

					gl.bindBuffer( gl.UNIFORM_BUFFER, bufferGPU );
					gl.bufferData( gl.UNIFORM_BUFFER, data, gl.STATIC_DRAW );

					indexesGPU.push( bufferGPU );

				}

				cameraData.indexesGPU = indexesGPU; // TODO: Create a global library for this

			}

			const cameraIndexData = this.get( cameraIndex );
			const pixelRatio = this.renderer.getPixelRatio();

			const renderTarget = this._currentContext.renderTarget;
			const isRenderCameraDepthArray = this._isRenderCameraDepthArray( this._currentContext );
			const prevActiveCubeFace = this._currentContext.activeCubeFace;

			if ( isRenderCameraDepthArray ) {

				// Clear the depth texture
				const textureData = this.get( renderTarget.depthTexture );

				if ( textureData.clearedRenderId !== this.renderer._nodes.nodeFrame.renderId ) {

					textureData.clearedRenderId = this.renderer._nodes.nodeFrame.renderId;

					const { stencilBuffer } = renderTarget;

					for ( let i = 0, len = cameras.length; i < len; i ++ ) {

						this.renderer._activeCubeFace = i;
						this._currentContext.activeCubeFace = i;

						this._setFramebuffer( this._currentContext );
						this.clear( false, true, stencilBuffer, this._currentContext, false );

					}

					this.renderer._activeCubeFace = prevActiveCubeFace;
					this._currentContext.activeCubeFace = prevActiveCubeFace;

				}

			}

			for ( let i = 0, len = cameras.length; i < len; i ++ ) {

				const subCamera = cameras[ i ];

				if ( object.layers.test( subCamera.layers ) ) {

					if ( isRenderCameraDepthArray ) {

						// Update the active layer
						this.renderer._activeCubeFace = i;
						this._currentContext.activeCubeFace = i;

						this._setFramebuffer( this._currentContext );

					}

					const vp = subCamera.viewport;

					if ( vp !== undefined ) {

						const x = vp.x * pixelRatio;
						const y = vp.y * pixelRatio;
						const width = vp.width * pixelRatio;
						const height = vp.height * pixelRatio;

						state.viewport(
							Math.floor( x ),
							Math.floor( renderObject.context.height - height - y ),
							Math.floor( width ),
							Math.floor( height )
						);

					}

					state.bindBufferBase( gl.UNIFORM_BUFFER, cameraIndexData.index, cameraData.indexesGPU[ i ] );

					draw();

				}

				this._currentContext.activeCubeFace = prevActiveCubeFace;
				this.renderer._activeCubeFace = prevActiveCubeFace;

			}

		} else {

			draw();

		}

	}

	/**
	 * Explain why always null is returned.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {boolean} Whether the render pipeline requires an update or not.
	 */
	needsRenderUpdate( /*renderObject*/ ) {

		return false;

	}

	/**
	 * Explain why no cache key is computed.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {string} The cache key.
	 */
	getRenderCacheKey( /*renderObject*/ ) {

		return '';

	}

	// textures

	/**
	 * Creates a default texture for the given texture that can be used
	 * as a placeholder until the actual texture is ready for usage.
	 *
	 * @param {Texture} texture - The texture to create a default texture for.
	 */
	createDefaultTexture( texture ) {

		this.textureUtils.createDefaultTexture( texture );

	}

	/**
	 * Defines a texture on the GPU for the given texture object.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {Object} [options={}] - Optional configuration parameter.
	 */
	createTexture( texture, options ) {

		this.textureUtils.createTexture( texture, options );

	}

	/**
	 * Uploads the updated texture data to the GPU.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {Object} [options={}] - Optional configuration parameter.
	 */
	updateTexture( texture, options ) {

		this.textureUtils.updateTexture( texture, options );

	}

	/**
	 * Generates mipmaps for the given texture.
	 *
	 * @param {Texture} texture - The texture.
	 */
	generateMipmaps( texture ) {

		this.textureUtils.generateMipmaps( texture );

	}

	/**
	 * Destroys the GPU data for the given texture object.
	 *
	 * @param {Texture} texture - The texture.
	 */
	destroyTexture( texture ) {

		this.textureUtils.destroyTexture( texture );

	}

	/**
	 * Returns texture data as a typed array.
	 *
	 * @async
	 * @param {Texture} texture - The texture to copy.
	 * @param {number} x - The x coordinate of the copy origin.
	 * @param {number} y - The y coordinate of the copy origin.
	 * @param {number} width - The width of the copy.
	 * @param {number} height - The height of the copy.
	 * @param {number} faceIndex - The face index.
	 * @return {Promise<TypedArray>} A Promise that resolves with a typed array when the copy operation has finished.
	 */
	async copyTextureToBuffer( texture, x, y, width, height, faceIndex ) {

		return this.textureUtils.copyTextureToBuffer( texture, x, y, width, height, faceIndex );

	}

	/**
	 * This method does nothing since WebGL 2 has no concept of samplers.
	 *
	 * @param {Texture} texture - The texture to create the sampler for.
	 */
	createSampler( /*texture*/ ) {

		//console.warn( 'Abstract class.' );

	}

	/**
	 * This method does nothing since WebGL 2 has no concept of samplers.
	 *
	 * @param {Texture} texture - The texture to destroy the sampler for.
	 */
	destroySampler( /*texture*/ ) {}

	// node builder

	/**
	 * Returns a node builder for the given render object.
	 *
	 * @param {RenderObject} object - The render object.
	 * @param {Renderer} renderer - The renderer.
	 * @return {GLSLNodeBuilder} The node builder.
	 */
	createNodeBuilder( object, renderer ) {

		return new GLSLNodeBuilder( object, renderer );

	}

	// program

	/**
	 * Creates a shader program from the given programmable stage.
	 *
	 * @param {ProgrammableStage} program - The programmable stage.
	 */
	createProgram( program ) {

		const gl = this.gl;
		const { stage, code } = program;

		const shader = stage === 'fragment' ? gl.createShader( gl.FRAGMENT_SHADER ) : gl.createShader( gl.VERTEX_SHADER );

		gl.shaderSource( shader, code );
		gl.compileShader( shader );

		this.set( program, {
			shaderGPU: shader
		} );

	}

	/**
	 * Destroys the shader program of the given programmable stage.
	 *
	 * @param {ProgrammableStage} program - The programmable stage.
	 */
	destroyProgram( program ) {

		this.delete( program );

	}

	/**
	 * Creates a render pipeline for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @param {Array<Promise>} promises - An array of compilation promises which are used in `compileAsync()`.
	 */
	createRenderPipeline( renderObject, promises ) {

		const gl = this.gl;
		const pipeline = renderObject.pipeline;

		// Program

		const { fragmentProgram, vertexProgram } = pipeline;

		const programGPU = gl.createProgram();

		const fragmentShader = this.get( fragmentProgram ).shaderGPU;
		const vertexShader = this.get( vertexProgram ).shaderGPU;

		gl.attachShader( programGPU, fragmentShader );
		gl.attachShader( programGPU, vertexShader );
		gl.linkProgram( programGPU );

		this.set( pipeline, {
			programGPU,
			fragmentShader,
			vertexShader
		} );

		if ( promises !== null && this.parallel ) {

			const p = new Promise( ( resolve /*, reject*/ ) => {

				const parallel = this.parallel;
				const checkStatus = () => {

					if ( gl.getProgramParameter( programGPU, parallel.COMPLETION_STATUS_KHR ) ) {

						this._completeCompile( renderObject, pipeline );
						resolve();

					} else {

						requestAnimationFrame( checkStatus );

					}

				};

				checkStatus();

			} );

			promises.push( p );

			return;

		}

		this._completeCompile( renderObject, pipeline );

	}

	/**
	 * Formats the source code of error messages.
	 *
	 * @private
	 * @param {string} string - The code.
	 * @param {number} errorLine - The error line.
	 * @return {string} The formatted code.
	 */
	_handleSource( string, errorLine ) {

		const lines = string.split( '\n' );
		const lines2 = [];

		const from = Math.max( errorLine - 6, 0 );
		const to = Math.min( errorLine + 6, lines.length );

		for ( let i = from; i < to; i ++ ) {

			const line = i + 1;
			lines2.push( `${line === errorLine ? '>' : ' '} ${line}: ${lines[ i ]}` );

		}

		return lines2.join( '\n' );

	}

	/**
	 * Gets the shader compilation errors from the info log.
	 *
	 * @private
	 * @param {WebGL2RenderingContext} gl - The rendering context.
	 * @param {WebGLShader} shader - The WebGL shader object.
	 * @param {string} type - The shader type.
	 * @return {string} The shader errors.
	 */
	_getShaderErrors( gl, shader, type ) {

		const status = gl.getShaderParameter( shader, gl.COMPILE_STATUS );

		const shaderInfoLog = gl.getShaderInfoLog( shader ) || '';
		const errors = shaderInfoLog.trim();

		if ( status && errors === '' ) return '';

		const errorMatches = /ERROR: 0:(\d+)/.exec( errors );
		if ( errorMatches ) {

			const errorLine = parseInt( errorMatches[ 1 ] );
			return type.toUpperCase() + '\n\n' + errors + '\n\n' + this._handleSource( gl.getShaderSource( shader ), errorLine );

		} else {

			return errors;

		}

	}

	/**
	 * Logs shader compilation errors.
	 *
	 * @private
	 * @param {WebGLProgram} programGPU - The WebGL program.
	 * @param {WebGLShader} glFragmentShader - The fragment shader as a native WebGL shader object.
	 * @param {WebGLShader} glVertexShader - The vertex shader as a native WebGL shader object.
	 */
	_logProgramError( programGPU, glFragmentShader, glVertexShader ) {

		if ( this.renderer.debug.checkShaderErrors ) {

			const gl = this.gl;

			const programInfoLog = gl.getProgramInfoLog( programGPU ) || '';
			const programLog = programInfoLog.trim();

			if ( gl.getProgramParameter( programGPU, gl.LINK_STATUS ) === false ) {

				if ( typeof this.renderer.debug.onShaderError === 'function' ) {

					this.renderer.debug.onShaderError( gl, programGPU, glVertexShader, glFragmentShader );

				} else {

					// default error reporting

					const vertexErrors = this._getShaderErrors( gl, glVertexShader, 'vertex' );
					const fragmentErrors = this._getShaderErrors( gl, glFragmentShader, 'fragment' );

					console.error(
						'THREE.WebGLProgram: Shader Error ' + gl.getError() + ' - ' +
						'VALIDATE_STATUS ' + gl.getProgramParameter( programGPU, gl.VALIDATE_STATUS ) + '\n\n' +
						'Program Info Log: ' + programLog + '\n' +
						vertexErrors + '\n' +
						fragmentErrors
					);

				}

			} else if ( programLog !== '' ) {

				console.warn( 'THREE.WebGLProgram: Program Info Log:', programLog );

			}

		}

	}

	/**
	 * Completes the shader program setup for the given render object.
	 *
	 * @private
	 * @param {RenderObject} renderObject - The render object.
	 * @param {RenderPipeline} pipeline - The render pipeline.
	 */
	_completeCompile( renderObject, pipeline ) {

		const { state, gl } = this;
		const pipelineData = this.get( pipeline );
		const { programGPU, fragmentShader, vertexShader } = pipelineData;

		if ( gl.getProgramParameter( programGPU, gl.LINK_STATUS ) === false ) {

			this._logProgramError( programGPU, fragmentShader, vertexShader );

		}

		state.useProgram( programGPU );

		// Bindings

		const bindings = renderObject.getBindings();

		this._setupBindings( bindings, programGPU );

		//

		this.set( pipeline, {
			programGPU
		} );

	}

	/**
	 * Creates a compute pipeline for the given compute node.
	 *
	 * @param {ComputePipeline} computePipeline - The compute pipeline.
	 * @param {Array<BindGroup>} bindings - The bindings.
	 */
	createComputePipeline( computePipeline, bindings ) {

		const { state, gl } = this;

		// Program

		const fragmentProgram = {
			stage: 'fragment',
			code: '#version 300 es\nprecision highp float;\nvoid main() {}'
		};

		this.createProgram( fragmentProgram );

		const { computeProgram } = computePipeline;

		const programGPU = gl.createProgram();

		const fragmentShader = this.get( fragmentProgram ).shaderGPU;
		const vertexShader = this.get( computeProgram ).shaderGPU;

		const transforms = computeProgram.transforms;

		const transformVaryingNames = [];
		const transformAttributeNodes = [];

		for ( let i = 0; i < transforms.length; i ++ ) {

			const transform = transforms[ i ];

			transformVaryingNames.push( transform.varyingName );
			transformAttributeNodes.push( transform.attributeNode );

		}

		gl.attachShader( programGPU, fragmentShader );
		gl.attachShader( programGPU, vertexShader );

		gl.transformFeedbackVaryings(
			programGPU,
			transformVaryingNames,
			gl.SEPARATE_ATTRIBS
		);

		gl.linkProgram( programGPU );

		if ( gl.getProgramParameter( programGPU, gl.LINK_STATUS ) === false ) {

			this._logProgramError( programGPU, fragmentShader, vertexShader );


		}

		state.useProgram( programGPU );

		// Bindings

		this._setupBindings( bindings, programGPU );

		const attributeNodes = computeProgram.attributes;
		const attributes = [];
		const transformBuffers = [];

		for ( let i = 0; i < attributeNodes.length; i ++ ) {

			const attribute = attributeNodes[ i ].node.attribute;

			attributes.push( attribute );

			if ( ! this.has( attribute ) ) this.attributeUtils.createAttribute( attribute, gl.ARRAY_BUFFER );

		}

		for ( let i = 0; i < transformAttributeNodes.length; i ++ ) {

			const attribute = transformAttributeNodes[ i ].attribute;

			if ( ! this.has( attribute ) ) this.attributeUtils.createAttribute( attribute, gl.ARRAY_BUFFER );

			const attributeData = this.get( attribute );

			transformBuffers.push( attributeData );

		}

		//

		this.set( computePipeline, {
			programGPU,
			transformBuffers,
			attributes
		} );

	}

	/**
	 * Creates bindings from the given bind group definition.
	 *
	 * @param {BindGroup} bindGroup - The bind group.
	 * @param {Array<BindGroup>} bindings - Array of bind groups.
	 * @param {number} cacheIndex - The cache index.
	 * @param {number} version - The version.
	 */
	createBindings( bindGroup, bindings /*, cacheIndex, version*/ ) {

		if ( this._knownBindings.has( bindings ) === false ) {

			this._knownBindings.add( bindings );

			let uniformBuffers = 0;
			let textures = 0;

			for ( const bindGroup of bindings ) {

				this.set( bindGroup, {
					textures: textures,
					uniformBuffers: uniformBuffers
				} );

				for ( const binding of bindGroup.bindings ) {

					if ( binding.isUniformBuffer ) uniformBuffers ++;
					if ( binding.isSampledTexture ) textures ++;

				}

			}

		}

		this.updateBindings( bindGroup, bindings );

	}

	/**
	 * Updates the given bind group definition.
	 *
	 * @param {BindGroup} bindGroup - The bind group.
	 * @param {Array<BindGroup>} bindings - Array of bind groups.
	 * @param {number} cacheIndex - The cache index.
	 * @param {number} version - The version.
	 */
	updateBindings( bindGroup /*, bindings, cacheIndex, version*/ ) {

		const { gl } = this;

		const bindGroupData = this.get( bindGroup );

		let i = bindGroupData.uniformBuffers;
		let t = bindGroupData.textures;

		for ( const binding of bindGroup.bindings ) {

			if ( binding.isUniformsGroup || binding.isUniformBuffer ) {

				const data = binding.buffer;
				const bufferGPU = gl.createBuffer();

				gl.bindBuffer( gl.UNIFORM_BUFFER, bufferGPU );
				gl.bufferData( gl.UNIFORM_BUFFER, data, gl.DYNAMIC_DRAW );

				this.set( binding, {
					index: i ++,
					bufferGPU
				} );

			} else if ( binding.isSampledTexture ) {

				const { textureGPU, glTextureType } = this.get( binding.texture );

				this.set( binding, {
					index: t ++,
					textureGPU,
					glTextureType
				} );

			}

		}

	}

	/**
	 * Updates a buffer binding.
	 *
	 *  @param {Buffer} binding - The buffer binding to update.
	 */
	updateBinding( binding ) {

		const gl = this.gl;

		if ( binding.isUniformsGroup || binding.isUniformBuffer ) {

			const bindingData = this.get( binding );
			const bufferGPU = bindingData.bufferGPU;
			const data = binding.buffer;

			gl.bindBuffer( gl.UNIFORM_BUFFER, bufferGPU );
			gl.bufferData( gl.UNIFORM_BUFFER, data, gl.DYNAMIC_DRAW );

		}

	}

	// attributes

	/**
	 * Creates the GPU buffer of an indexed shader attribute.
	 *
	 * @param {BufferAttribute} attribute - The indexed buffer attribute.
	 */
	createIndexAttribute( attribute ) {

		const gl = this.gl;

		this.attributeUtils.createAttribute( attribute, gl.ELEMENT_ARRAY_BUFFER );

	}

	/**
	 * Creates the GPU buffer of a shader attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
	createAttribute( attribute ) {

		if ( this.has( attribute ) ) return;

		const gl = this.gl;

		this.attributeUtils.createAttribute( attribute, gl.ARRAY_BUFFER );

	}

	/**
	 * Creates the GPU buffer of a storage attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
	createStorageAttribute( attribute ) {

		if ( this.has( attribute ) ) return;

		const gl = this.gl;

		this.attributeUtils.createAttribute( attribute, gl.ARRAY_BUFFER );

	}

	/**
	 * Updates the GPU buffer of a shader attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute to update.
	 */
	updateAttribute( attribute ) {

		this.attributeUtils.updateAttribute( attribute );

	}

	/**
	 * Destroys the GPU buffer of a shader attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute to destroy.
	 */
	destroyAttribute( attribute ) {

		this.attributeUtils.destroyAttribute( attribute );

	}

	/**
	 * Checks if the given feature is supported  by the backend.
	 *
	 * @param {string} name - The feature's name.
	 * @return {boolean} Whether the feature is supported or not.
	 */
	hasFeature( name ) {

		const keysMatching = Object.keys( GLFeatureName ).filter( key => GLFeatureName[ key ] === name );

		const extensions = this.extensions;

		for ( let i = 0; i < keysMatching.length; i ++ ) {

			if ( extensions.has( keysMatching[ i ] ) ) return true;

		}

		return false;

	}

	/**
	 * Returns the maximum anisotropy texture filtering value.
	 *
	 * @return {number} The maximum anisotropy texture filtering value.
	 */
	getMaxAnisotropy() {

		return this.capabilities.getMaxAnisotropy();

	}

	/**
	 * Copies data of the given source texture to the given destination texture.
	 *
	 * @param {Texture} srcTexture - The source texture.
	 * @param {Texture} dstTexture - The destination texture.
	 * @param {?(Box3|Box2)} [srcRegion=null] - The region of the source texture to copy.
	 * @param {?(Vector2|Vector3)} [dstPosition=null] - The destination position of the copy.
	 * @param {number} [srcLevel=0] - The source mip level to copy from.
	 * @param {number} [dstLevel=0] - The destination mip level to copy to.
	 */
	copyTextureToTexture( srcTexture, dstTexture, srcRegion = null, dstPosition = null, srcLevel = 0, dstLevel = 0 ) {

		this.textureUtils.copyTextureToTexture( srcTexture, dstTexture, srcRegion, dstPosition, srcLevel, dstLevel );

	}

	/**
	 * Copies the current bound framebuffer to the given texture.
	 *
	 * @param {Texture} texture - The destination texture.
	 * @param {RenderContext} renderContext - The render context.
	 * @param {Vector4} rectangle - A four dimensional vector defining the origin and dimension of the copy.
	 */
	copyFramebufferToTexture( texture, renderContext, rectangle ) {

		this.textureUtils.copyFramebufferToTexture( texture, renderContext, rectangle );

	}

	/**
	 * Configures the active framebuffer from the given render context.
	 *
	 * @private
	 * @param {RenderContext} descriptor - The render context.
	 */
	_setFramebuffer( descriptor ) {

		const { gl, state } = this;

		let currentFrameBuffer = null;

		if ( descriptor.textures !== null ) {

			const renderTarget = descriptor.renderTarget;
			const renderTargetContextData = this.get( renderTarget );
			const { samples, depthBuffer, stencilBuffer } = renderTarget;

			const isCube = renderTarget.isWebGLCubeRenderTarget === true;
			const isRenderTarget3D = renderTarget.isRenderTarget3D === true;
			const isRenderTargetArray = renderTarget.depth > 1;
			const isXRRenderTarget = renderTarget.isXRRenderTarget === true;
			const _hasExternalTextures = ( isXRRenderTarget === true && renderTarget._hasExternalTextures === true );

			let msaaFb = renderTargetContextData.msaaFrameBuffer;
			let depthRenderbuffer = renderTargetContextData.depthRenderbuffer;
			const multisampledRTTExt = this.extensions.get( 'WEBGL_multisampled_render_to_texture' );
			const multiviewExt = this.extensions.get( 'OVR_multiview2' );
			const useMultisampledRTT = this._useMultisampledExtension( renderTarget );
			const cacheKey = getCacheKey( descriptor );

			let fb;

			if ( isCube ) {

				renderTargetContextData.cubeFramebuffers || ( renderTargetContextData.cubeFramebuffers = {} );

				fb = renderTargetContextData.cubeFramebuffers[ cacheKey ];

			} else if ( isXRRenderTarget && _hasExternalTextures === false ) {

				fb = this._xrFramebuffer;

			} else {

				renderTargetContextData.framebuffers || ( renderTargetContextData.framebuffers = {} );

				fb = renderTargetContextData.framebuffers[ cacheKey ];

			}

			if ( fb === undefined ) {

				fb = gl.createFramebuffer();

				state.bindFramebuffer( gl.FRAMEBUFFER, fb );

				const textures = descriptor.textures;
				const depthInvalidationArray = [];

				if ( isCube ) {

					renderTargetContextData.cubeFramebuffers[ cacheKey ] = fb;

					const { textureGPU } = this.get( textures[ 0 ] );

					const cubeFace = this.renderer._activeCubeFace;

					gl.framebufferTexture2D( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0, gl.TEXTURE_CUBE_MAP_POSITIVE_X + cubeFace, textureGPU, 0 );

				} else {

					renderTargetContextData.framebuffers[ cacheKey ] = fb;

					for ( let i = 0; i < textures.length; i ++ ) {

						const texture = textures[ i ];
						const textureData = this.get( texture );
						textureData.renderTarget = descriptor.renderTarget;
						textureData.cacheKey = cacheKey; // required for copyTextureToTexture()

						const attachment = gl.COLOR_ATTACHMENT0 + i;

						if ( renderTarget.multiview ) {

							multiviewExt.framebufferTextureMultisampleMultiviewOVR( gl.FRAMEBUFFER, attachment, textureData.textureGPU, 0, samples, 0, 2 );

						} else if ( isRenderTarget3D || isRenderTargetArray ) {

							const layer = this.renderer._activeCubeFace;

							gl.framebufferTextureLayer( gl.FRAMEBUFFER, attachment, textureData.textureGPU, 0, layer );

						} else {

							if ( useMultisampledRTT ) {

								multisampledRTTExt.framebufferTexture2DMultisampleEXT( gl.FRAMEBUFFER, attachment, gl.TEXTURE_2D, textureData.textureGPU, 0, samples );

							} else {

								gl.framebufferTexture2D( gl.FRAMEBUFFER, attachment, gl.TEXTURE_2D, textureData.textureGPU, 0 );

							}

						}

					}

				}

				const depthStyle = stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT;

				if ( renderTarget._autoAllocateDepthBuffer === true ) {

					const renderbuffer = gl.createRenderbuffer();
					this.textureUtils.setupRenderBufferStorage( renderbuffer, descriptor, 0, useMultisampledRTT );
					renderTargetContextData.xrDepthRenderbuffer = renderbuffer;
					depthInvalidationArray.push( stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT );

					gl.bindRenderbuffer( gl.RENDERBUFFER, renderbuffer );
					gl.framebufferRenderbuffer( gl.FRAMEBUFFER, depthStyle, gl.RENDERBUFFER, renderbuffer );


				} else {

					if ( descriptor.depthTexture !== null ) {

						depthInvalidationArray.push( stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT );

						const textureData = this.get( descriptor.depthTexture );
						textureData.renderTarget = descriptor.renderTarget;
						textureData.cacheKey = cacheKey; // required for copyTextureToTexture()

						if ( renderTarget.multiview ) {

							multiviewExt.framebufferTextureMultisampleMultiviewOVR( gl.FRAMEBUFFER, depthStyle, textureData.textureGPU, 0, samples, 0, 2 );

						} else if ( _hasExternalTextures && useMultisampledRTT ) {

							multisampledRTTExt.framebufferTexture2DMultisampleEXT( gl.FRAMEBUFFER, depthStyle, gl.TEXTURE_2D, textureData.textureGPU, 0, samples );

						} else {

							if ( descriptor.depthTexture.isArrayTexture ) {

								const layer = this.renderer._activeCubeFace;

								gl.framebufferTextureLayer( gl.FRAMEBUFFER, depthStyle, textureData.textureGPU, 0, layer );

							} else {

								gl.framebufferTexture2D( gl.FRAMEBUFFER, depthStyle, gl.TEXTURE_2D, textureData.textureGPU, 0 );

							}

						}

					}

				}

				renderTargetContextData.depthInvalidationArray = depthInvalidationArray;


			} else {

				const isRenderCameraDepthArray = this._isRenderCameraDepthArray( descriptor );

				if ( isRenderCameraDepthArray ) {

					state.bindFramebuffer( gl.FRAMEBUFFER, fb );

					const layer = this.renderer._activeCubeFace;

					const depthData = this.get( descriptor.depthTexture );
					const depthStyle = stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT;
					gl.framebufferTextureLayer(
						gl.FRAMEBUFFER,
						depthStyle,
						depthData.textureGPU,
						0,
						layer
					);

				}

				// rebind external XR textures

				if ( ( isXRRenderTarget || useMultisampledRTT || renderTarget.multiview ) && ( renderTarget._isOpaqueFramebuffer !== true ) ) {

					state.bindFramebuffer( gl.FRAMEBUFFER, fb );

					// rebind color

					const textureData = this.get( descriptor.textures[ 0 ] );

					if ( renderTarget.multiview ) {

						multiviewExt.framebufferTextureMultisampleMultiviewOVR( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0, textureData.textureGPU, 0, samples, 0, 2 );

					} else if ( useMultisampledRTT ) {

						multisampledRTTExt.framebufferTexture2DMultisampleEXT( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0, gl.TEXTURE_2D, textureData.textureGPU, 0, samples );

					} else {

						gl.framebufferTexture2D( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0, gl.TEXTURE_2D, textureData.textureGPU, 0 );

					}

					// rebind depth

					const depthStyle = stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT;

					if ( renderTarget._autoAllocateDepthBuffer === true ) {

						const renderbuffer = renderTargetContextData.xrDepthRenderbuffer;
						gl.bindRenderbuffer( gl.RENDERBUFFER, renderbuffer );
						gl.framebufferRenderbuffer( gl.FRAMEBUFFER, depthStyle, gl.RENDERBUFFER, renderbuffer );

					} else {

						const textureData = this.get( descriptor.depthTexture );

						if ( renderTarget.multiview ) {

							multiviewExt.framebufferTextureMultisampleMultiviewOVR( gl.FRAMEBUFFER, depthStyle, textureData.textureGPU, 0, samples, 0, 2 );

						} else if ( useMultisampledRTT ) {

							multisampledRTTExt.framebufferTexture2DMultisampleEXT( gl.FRAMEBUFFER, depthStyle, gl.TEXTURE_2D, textureData.textureGPU, 0, samples );

						} else {

							gl.framebufferTexture2D( gl.FRAMEBUFFER, depthStyle, gl.TEXTURE_2D, textureData.textureGPU, 0 );

						}

					}

				}

			}

			if ( samples > 0 && useMultisampledRTT === false && ! renderTarget.multiview ) {

				if ( msaaFb === undefined ) {

					const invalidationArray = [];

					msaaFb = gl.createFramebuffer();

					state.bindFramebuffer( gl.FRAMEBUFFER, msaaFb );

					const msaaRenderbuffers = [];

					const textures = descriptor.textures;

					for ( let i = 0; i < textures.length; i ++ ) {

						msaaRenderbuffers[ i ] = gl.createRenderbuffer();

						gl.bindRenderbuffer( gl.RENDERBUFFER, msaaRenderbuffers[ i ] );

						invalidationArray.push( gl.COLOR_ATTACHMENT0 + i );

						const texture = descriptor.textures[ i ];
						const textureData = this.get( texture );

						gl.renderbufferStorageMultisample( gl.RENDERBUFFER, samples, textureData.glInternalFormat, descriptor.width, descriptor.height );
						gl.framebufferRenderbuffer( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0 + i, gl.RENDERBUFFER, msaaRenderbuffers[ i ] );


					}

					gl.bindRenderbuffer( gl.RENDERBUFFER, null );

					renderTargetContextData.msaaFrameBuffer = msaaFb;
					renderTargetContextData.msaaRenderbuffers = msaaRenderbuffers;

					if ( depthBuffer && depthRenderbuffer === undefined ) {

						depthRenderbuffer = gl.createRenderbuffer();
						this.textureUtils.setupRenderBufferStorage( depthRenderbuffer, descriptor, samples );

						renderTargetContextData.depthRenderbuffer = depthRenderbuffer;

						const depthStyle = stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT;
						invalidationArray.push( depthStyle );

					}

					renderTargetContextData.invalidationArray = invalidationArray;

				}

				currentFrameBuffer = renderTargetContextData.msaaFrameBuffer;

			} else {

				currentFrameBuffer = fb;

			}

			state.drawBuffers( descriptor, fb );

		}

		state.bindFramebuffer( gl.FRAMEBUFFER, currentFrameBuffer );

	}

	/**
	 * Computes the VAO key for the given index and attributes.
	 *
	 * @private
	 * @param {Array<BufferAttribute>} attributes - An array of buffer attributes.
	 * @return {string} The VAO key.
	 */
	_getVaoKey( attributes ) {

		let key = '';

		for ( let i = 0; i < attributes.length; i ++ ) {

			const attributeData = this.get( attributes[ i ] );

			key += ':' + attributeData.id;

		}

		return key;

	}

	/**
	 * Creates a VAO from the index and attributes.
	 *
	 * @private
	 * @param {Array<BufferAttribute>} attributes - An array of buffer attributes.
	 * @return {Object} The VAO data.
	 */
	_createVao( attributes ) {

		const { gl } = this;

		const vaoGPU = gl.createVertexArray();

		gl.bindVertexArray( vaoGPU );

		for ( let i = 0; i < attributes.length; i ++ ) {

			const attribute = attributes[ i ];
			const attributeData = this.get( attribute );

			gl.bindBuffer( gl.ARRAY_BUFFER, attributeData.bufferGPU );
			gl.enableVertexAttribArray( i );

			let stride, offset;

			if ( attribute.isInterleavedBufferAttribute === true ) {

				stride = attribute.data.stride * attributeData.bytesPerElement;
				offset = attribute.offset * attributeData.bytesPerElement;

			} else {

				stride = 0;
				offset = 0;

			}

			if ( attributeData.isInteger ) {

				gl.vertexAttribIPointer( i, attribute.itemSize, attributeData.type, stride, offset );

			} else {

				gl.vertexAttribPointer( i, attribute.itemSize, attributeData.type, attribute.normalized, stride, offset );

			}

			if ( attribute.isInstancedBufferAttribute && ! attribute.isInterleavedBufferAttribute ) {

				gl.vertexAttribDivisor( i, attribute.meshPerAttribute );

			} else if ( attribute.isInterleavedBufferAttribute && attribute.data.isInstancedInterleavedBuffer ) {

				gl.vertexAttribDivisor( i, attribute.data.meshPerAttribute );

			}

		}

		gl.bindBuffer( gl.ARRAY_BUFFER, null );

		return vaoGPU;

	}

	/**
	 * Creates a transform feedback from the given transform buffers.
	 *
	 * @private
	 * @param {Array<DualAttributeData>} transformBuffers - The transform buffers.
	 * @return {WebGLTransformFeedback} The transform feedback.
	 */
	_getTransformFeedback( transformBuffers ) {

		let key = '';

		for ( let i = 0; i < transformBuffers.length; i ++ ) {

			key += ':' + transformBuffers[ i ].id;

		}

		let transformFeedbackGPU = this.transformFeedbackCache[ key ];

		if ( transformFeedbackGPU !== undefined ) {

			return transformFeedbackGPU;

		}

		const { gl } = this;

		transformFeedbackGPU = gl.createTransformFeedback();

		gl.bindTransformFeedback( gl.TRANSFORM_FEEDBACK, transformFeedbackGPU );

		for ( let i = 0; i < transformBuffers.length; i ++ ) {

			const attributeData = transformBuffers[ i ];

			gl.bindBufferBase( gl.TRANSFORM_FEEDBACK_BUFFER, i, attributeData.transformBuffer );

		}

		gl.bindTransformFeedback( gl.TRANSFORM_FEEDBACK, null );

		this.transformFeedbackCache[ key ] = transformFeedbackGPU;

		return transformFeedbackGPU;

	}

	/**
	 * Setups the given bindings.
	 *
	 * @private
	 * @param {Array<BindGroup>} bindings - The bindings.
	 * @param {WebGLProgram} programGPU - The WebGL program.
	 */
	_setupBindings( bindings, programGPU ) {

		const gl = this.gl;

		for ( const bindGroup of bindings ) {

			for ( const binding of bindGroup.bindings ) {

				const bindingData = this.get( binding );
				const index = bindingData.index;

				if ( binding.isUniformsGroup || binding.isUniformBuffer ) {

					const location = gl.getUniformBlockIndex( programGPU, binding.name );
					gl.uniformBlockBinding( programGPU, location, index );

				} else if ( binding.isSampledTexture ) {

					const location = gl.getUniformLocation( programGPU, binding.name );
					gl.uniform1i( location, index );

				}

			}

		}

	}

	/**
	 * Binds the given uniforms.
	 *
	 * @private
	 * @param {Array<BindGroup>} bindings - The bindings.
	 */
	_bindUniforms( bindings ) {

		const { gl, state } = this;

		for ( const bindGroup of bindings ) {

			for ( const binding of bindGroup.bindings ) {

				const bindingData = this.get( binding );
				const index = bindingData.index;

				if ( binding.isUniformsGroup || binding.isUniformBuffer ) {

					// TODO USE bindBufferRange to group multiple uniform buffers
					state.bindBufferBase( gl.UNIFORM_BUFFER, index, bindingData.bufferGPU );

				} else if ( binding.isSampledTexture ) {

					state.bindTexture( bindingData.glTextureType, bindingData.textureGPU, gl.TEXTURE0 + index );

				}

			}

		}

	}

	/**
	 * Returns `true` if the `WEBGL_multisampled_render_to_texture` extension
	 * should be used when MSAA is enabled.
	 *
	 * @private
	 * @param {RenderTarget} renderTarget - The render target that should be multisampled.
	 * @return {boolean} Whether to use the `WEBGL_multisampled_render_to_texture` extension for MSAA or not.
	 */
	_useMultisampledExtension( renderTarget ) {

		if ( renderTarget.multiview === true ) {

			return true;

		}

		return renderTarget.samples > 0 && this.extensions.has( 'WEBGL_multisampled_render_to_texture' ) === true && renderTarget._autoAllocateDepthBuffer !== false;

	}

	/**
	 * Frees internal resources.
	 */
	dispose() {

		const extension = this.extensions.get( 'WEBGL_lose_context' );
		if ( extension ) extension.loseContext();

		this.renderer.domElement.removeEventListener( 'webglcontextlost', this._onContextLost );

	}

}
```
</details>

#### Methods

##### `init(renderer: Renderer): void`

<details><summary>Code</summary>

```ts
init( renderer ) {

		super.init( renderer );

		//

		const parameters = this.parameters;

		const contextAttributes = {
			antialias: renderer.samples > 0,
			alpha: true, // always true for performance reasons
			depth: renderer.depth,
			stencil: renderer.stencil
		};

		const glContext = ( parameters.context !== undefined ) ? parameters.context : renderer.domElement.getContext( 'webgl2', contextAttributes );

	 	function onContextLost( event ) {

			event.preventDefault();

			const contextLossInfo = {
				api: 'WebGL',
				message: event.statusMessage || 'Unknown reason',
				reason: null,
				originalEvent: event
			};

			renderer.onDeviceLost( contextLossInfo );

		}

		this._onContextLost = onContextLost;

		renderer.domElement.addEventListener( 'webglcontextlost', onContextLost, false );

		this.gl = glContext;

		this.extensions = new WebGLExtensions( this );
		this.capabilities = new WebGLCapabilities( this );
		this.attributeUtils = new WebGLAttributeUtils( this );
		this.textureUtils = new WebGLTextureUtils( this );
		this.bufferRenderer = new WebGLBufferRenderer( this );

		this.state = new WebGLState( this );
		this.utils = new WebGLUtils( this );

		this.extensions.get( 'EXT_color_buffer_float' );
		this.extensions.get( 'WEBGL_clip_cull_distance' );
		this.extensions.get( 'OES_texture_float_linear' );
		this.extensions.get( 'EXT_color_buffer_half_float' );
		this.extensions.get( 'WEBGL_multisampled_render_to_texture' );
		this.extensions.get( 'WEBGL_render_shared_exponent' );
		this.extensions.get( 'WEBGL_multi_draw' );
		this.extensions.get( 'OVR_multiview2' );

		this.disjoint = this.extensions.get( 'EXT_disjoint_timer_query_webgl2' );
		this.parallel = this.extensions.get( 'KHR_parallel_shader_compile' );

	}
```
</details>

##### `getArrayBufferAsync(attribute: StorageBufferAttribute): Promise<ArrayBuffer>`

<details><summary>Code</summary>

```ts
async getArrayBufferAsync( attribute ) {

		return await this.attributeUtils.getArrayBufferAsync( attribute );

	}
```
</details>

##### `waitForGPU(): Promise<any>`

<details><summary>Code</summary>

```ts
async waitForGPU() {

		await this.utils._clientWaitAsync();

	}
```
</details>

##### `makeXRCompatible(): Promise<any>`

<details><summary>Code</summary>

```ts
async makeXRCompatible() {

		const attributes = this.gl.getContextAttributes();

		if ( attributes.xrCompatible !== true ) {

			await this.gl.makeXRCompatible();

		}

	}
```
</details>

##### `setXRTarget(xrFramebuffer: WebGLFramebuffer): void`

<details><summary>Code</summary>

```ts
setXRTarget( xrFramebuffer ) {

		this._xrFramebuffer = xrFramebuffer;

	}
```
</details>

##### `setXRRenderTargetTextures(renderTarget: XRRenderTarget, colorTexture: WebGLTexture, depthTexture: WebGLTexture): void`

<details><summary>Code</summary>

```ts
setXRRenderTargetTextures( renderTarget, colorTexture, depthTexture = null ) {

		const gl = this.gl;

		this.set( renderTarget.texture, { textureGPU: colorTexture, glInternalFormat: gl.RGBA8 } ); // see #24698 why RGBA8 and not SRGB8_ALPHA8 is used

		if ( depthTexture !== null ) {

			const glInternalFormat = renderTarget.stencilBuffer ? gl.DEPTH24_STENCIL8 : gl.DEPTH_COMPONENT24;

			this.set( renderTarget.depthTexture, { textureGPU: depthTexture, glInternalFormat: glInternalFormat } );

			// The multisample_render_to_texture extension doesn't work properly if there
			// are midframe flushes and an external depth texture.
			if ( ( this.extensions.has( 'WEBGL_multisampled_render_to_texture' ) === true ) && renderTarget._autoAllocateDepthBuffer === true && renderTarget.multiview === false ) {

				console.warn( 'THREE.WebGLBackend: Render-to-texture extension was disabled because an external texture was provided' );

			}

			renderTarget._autoAllocateDepthBuffer = false;

		}

	}
```
</details>

##### `initTimestampQuery(renderContext: RenderContext): void`

<details><summary>Code</summary>

```ts
initTimestampQuery( renderContext ) {

		if ( ! this.disjoint || ! this.trackTimestamp ) return;

		const type = renderContext.isComputeNode ? 'compute' : 'render';

		if ( ! this.timestampQueryPool[ type ] ) {

			// TODO: Variable maxQueries?
			this.timestampQueryPool[ type ] = new WebGLTimestampQueryPool( this.gl, type, 2048 );

		}

		const timestampQueryPool = this.timestampQueryPool[ type ];

		const baseOffset = timestampQueryPool.allocateQueriesForContext( renderContext );

		if ( baseOffset !== null ) {

			timestampQueryPool.beginQuery( renderContext );

		}

	}
```
</details>

##### `prepareTimestampBuffer(renderContext: RenderContext): void`

<details><summary>Code</summary>

```ts
prepareTimestampBuffer( renderContext ) {

		if ( ! this.disjoint || ! this.trackTimestamp ) return;

		const type = renderContext.isComputeNode ? 'compute' : 'render';
		const timestampQueryPool = this.timestampQueryPool[ type ];

		timestampQueryPool.endQuery( renderContext );

	}
```
</details>

##### `getContext(): WebGL2RenderingContext`

<details><summary>Code</summary>

```ts
getContext() {

		return this.gl;

	}
```
</details>

##### `beginRender(renderContext: RenderContext): void`

<details><summary>Code</summary>

```ts
beginRender( renderContext ) {

		const { state } = this;
		const renderContextData = this.get( renderContext );

		//

		if ( renderContext.viewport ) {

			this.updateViewport( renderContext );

		} else {

			const { width, height } = this.getDrawingBufferSize();
			state.viewport( 0, 0, width, height );

		}

		if ( renderContext.scissor ) {

			const { x, y, width, height } = renderContext.scissorValue;

			state.scissor( x, renderContext.height - height - y, width, height );

		}

		//

		this.initTimestampQuery( renderContext );

		renderContextData.previousContext = this._currentContext;
		this._currentContext = renderContext;

		this._setFramebuffer( renderContext );
		this.clear( renderContext.clearColor, renderContext.clearDepth, renderContext.clearStencil, renderContext, false );

		const occlusionQueryCount = renderContext.occlusionQueryCount;

		if ( occlusionQueryCount > 0 ) {

			// Get a reference to the array of objects with queries. The renderContextData property
			// can be changed by another render pass before the async reading of all previous queries complete
			renderContextData.currentOcclusionQueries = renderContextData.occlusionQueries;
			renderContextData.currentOcclusionQueryObjects = renderContextData.occlusionQueryObjects;

			renderContextData.lastOcclusionObject = null;
			renderContextData.occlusionQueries = new Array( occlusionQueryCount );
			renderContextData.occlusionQueryObjects = new Array( occlusionQueryCount );
			renderContextData.occlusionQueryIndex = 0;

		}

	}
```
</details>

##### `finishRender(renderContext: RenderContext): void`

<details><summary>Code</summary>

```ts
finishRender( renderContext ) {

		const { gl, state } = this;
		const renderContextData = this.get( renderContext );
		const previousContext = renderContextData.previousContext;

		state.resetVertexState();

		const occlusionQueryCount = renderContext.occlusionQueryCount;

		if ( occlusionQueryCount > 0 ) {

			if ( occlusionQueryCount > renderContextData.occlusionQueryIndex ) {

				gl.endQuery( gl.ANY_SAMPLES_PASSED );

			}

			this.resolveOccludedAsync( renderContext );

		}

		const textures = renderContext.textures;

		if ( textures !== null ) {

			for ( let i = 0; i < textures.length; i ++ ) {

				const texture = textures[ i ];

				if ( texture.generateMipmaps ) {

					this.generateMipmaps( texture );

				}

			}

		}

		this._currentContext = previousContext;
		const renderTarget = renderContext.renderTarget;

		if ( renderContext.textures !== null && renderTarget ) {

			const renderTargetContextData = this.get( renderTarget );

			if ( renderTarget.samples > 0 && this._useMultisampledExtension( renderTarget ) === false ) {

				const fb = renderTargetContextData.framebuffers[ renderContext.getCacheKey() ];

				let mask = gl.COLOR_BUFFER_BIT;

				if ( renderTarget.resolveDepthBuffer ) {

					if ( renderTarget.depthBuffer ) mask |= gl.DEPTH_BUFFER_BIT;
					if ( renderTarget.stencilBuffer && renderTarget.resolveStencilBuffer ) mask |= gl.STENCIL_BUFFER_BIT;

				}

				const msaaFrameBuffer = renderTargetContextData.msaaFrameBuffer;
				const msaaRenderbuffers = renderTargetContextData.msaaRenderbuffers;

				const textures = renderContext.textures;
				const isMRT = textures.length > 1;

				state.bindFramebuffer( gl.READ_FRAMEBUFFER, msaaFrameBuffer );
				state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, fb );

				if ( isMRT ) {

					// blitFramebuffer() can only copy/resolve the first color attachment of a framebuffer. When using MRT,
					// the engine temporarily removes all attachments and then configures each attachment for the resolve.

					for ( let i = 0; i < textures.length; i ++ ) {

						gl.framebufferRenderbuffer( gl.READ_FRAMEBUFFER, gl.COLOR_ATTACHMENT0 + i, gl.RENDERBUFFER, null );
						gl.framebufferTexture2D( gl.DRAW_FRAMEBUFFER, gl.COLOR_ATTACHMENT0 + i, gl.TEXTURE_2D, null, 0 );

					}

				}

				for ( let i = 0; i < textures.length; i ++ ) {

					if ( isMRT ) {

						// configure attachment for resolve

						const { textureGPU } = this.get( textures[ i ] );

						gl.framebufferRenderbuffer( gl.READ_FRAMEBUFFER, gl.COLOR_ATTACHMENT0, gl.RENDERBUFFER, msaaRenderbuffers[ i ] );
						gl.framebufferTexture2D( gl.DRAW_FRAMEBUFFER, gl.COLOR_ATTACHMENT0, gl.TEXTURE_2D, textureGPU, 0 );

					}

					if ( renderContext.scissor ) {

						const { x, y, width, height } = renderContext.scissorValue;

						const viewY = renderContext.height - height - y;

						gl.blitFramebuffer( x, viewY, x + width, viewY + height, x, viewY, x + width, viewY + height, mask, gl.NEAREST );

					} else {

						gl.blitFramebuffer( 0, 0, renderContext.width, renderContext.height, 0, 0, renderContext.width, renderContext.height, mask, gl.NEAREST );

					}

				}

				if ( isMRT ) {

					// restore attachments

					for ( let i = 0; i < textures.length; i ++ ) {

						const { textureGPU } = this.get( textures[ i ] );

						gl.framebufferRenderbuffer( gl.READ_FRAMEBUFFER, gl.COLOR_ATTACHMENT0 + i, gl.RENDERBUFFER, msaaRenderbuffers[ i ] );
						gl.framebufferTexture2D( gl.DRAW_FRAMEBUFFER, gl.COLOR_ATTACHMENT0 + i, gl.TEXTURE_2D, textureGPU, 0 );

					}

				}

				if ( this._supportsInvalidateFramebuffer === true ) {

					gl.invalidateFramebuffer( gl.READ_FRAMEBUFFER, renderTargetContextData.invalidationArray );

				}

			} else if ( renderTarget.resolveDepthBuffer === false && renderTargetContextData.framebuffers ) {

				const fb = renderTargetContextData.framebuffers[ renderContext.getCacheKey() ];
				state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, fb );
				gl.invalidateFramebuffer( gl.DRAW_FRAMEBUFFER, renderTargetContextData.depthInvalidationArray );

			}

		}

		if ( previousContext !== null ) {

			this._setFramebuffer( previousContext );

			if ( previousContext.viewport ) {

				this.updateViewport( previousContext );

			} else {

				const { width, height } = this.getDrawingBufferSize();
				state.viewport( 0, 0, width, height );

			}

		}

		this.prepareTimestampBuffer( renderContext );

	}
```
</details>

##### `resolveOccludedAsync(renderContext: RenderContext): void`

<details><summary>Code</summary>

```ts
resolveOccludedAsync( renderContext ) {

		const renderContextData = this.get( renderContext );

		// handle occlusion query results

		const { currentOcclusionQueries, currentOcclusionQueryObjects } = renderContextData;

		if ( currentOcclusionQueries && currentOcclusionQueryObjects ) {

			const occluded = new WeakSet();
			const { gl } = this;

			renderContextData.currentOcclusionQueryObjects = null;
			renderContextData.currentOcclusionQueries = null;

			const check = () => {

				let completed = 0;

				// check all queries and requeue as appropriate
				for ( let i = 0; i < currentOcclusionQueries.length; i ++ ) {

					const query = currentOcclusionQueries[ i ];

					if ( query === null ) continue;

					if ( gl.getQueryParameter( query, gl.QUERY_RESULT_AVAILABLE ) ) {

						if ( gl.getQueryParameter( query, gl.QUERY_RESULT ) === 0 ) occluded.add( currentOcclusionQueryObjects[ i ] );

						currentOcclusionQueries[ i ] = null;
						gl.deleteQuery( query );

						completed ++;

					}

				}

				if ( completed < currentOcclusionQueries.length ) {

					requestAnimationFrame( check );

				} else {

					renderContextData.occluded = occluded;

				}

			};

			check();

		}

	}
```
</details>

##### `isOccluded(renderContext: RenderContext, object: Object3D): boolean`

<details><summary>Code</summary>

```ts
isOccluded( renderContext, object ) {

		const renderContextData = this.get( renderContext );

		return renderContextData.occluded && renderContextData.occluded.has( object );

	}
```
</details>

##### `updateViewport(renderContext: RenderContext): void`

<details><summary>Code</summary>

```ts
updateViewport( renderContext ) {

		const { state } = this;
		const { x, y, width, height } = renderContext.viewportValue;

		state.viewport( x, renderContext.height - height - y, width, height );

	}
```
</details>

##### `setScissorTest(boolean: boolean): void`

<details><summary>Code</summary>

```ts
setScissorTest( boolean ) {

		const state = this.state;

		state.setScissorTest( boolean );

	}
```
</details>

##### `getClearColor(): Color4`

<details><summary>Code</summary>

```ts
getClearColor() {

		const clearColor = super.getClearColor();

		// Since the canvas is always created with alpha: true,
		// WebGL must always premultiply the clear color.

		clearColor.r *= clearColor.a;
		clearColor.g *= clearColor.a;
		clearColor.b *= clearColor.a;

		return clearColor;

	}
```
</details>

##### `clear(color: boolean, depth: boolean, stencil: boolean, descriptor: any, setFrameBuffer: boolean): void`

<details><summary>Code</summary>

```ts
clear( color, depth, stencil, descriptor = null, setFrameBuffer = true ) {

		const { gl, renderer } = this;

		if ( descriptor === null ) {

			const clearColor = this.getClearColor();

			descriptor = {
				textures: null,
				clearColorValue: clearColor
			};

		}

		//

		let clear = 0;

		if ( color ) clear |= gl.COLOR_BUFFER_BIT;
		if ( depth ) clear |= gl.DEPTH_BUFFER_BIT;
		if ( stencil ) clear |= gl.STENCIL_BUFFER_BIT;

		if ( clear !== 0 ) {

			let clearColor;

			if ( descriptor.clearColorValue ) {

				clearColor = descriptor.clearColorValue;

			} else {

				clearColor = this.getClearColor();

			}

			const clearDepth = renderer.getClearDepth();
			const clearStencil = renderer.getClearStencil();

			if ( depth ) this.state.setDepthMask( true );

			if ( descriptor.textures === null ) {

				gl.clearColor( clearColor.r, clearColor.g, clearColor.b, clearColor.a );
				gl.clear( clear );

			} else {

				if ( setFrameBuffer ) this._setFramebuffer( descriptor );

				if ( color ) {

					for ( let i = 0; i < descriptor.textures.length; i ++ ) {

						if ( i === 0 ) {

							gl.clearBufferfv( gl.COLOR, i, [ clearColor.r, clearColor.g, clearColor.b, clearColor.a ] );

						} else {

							gl.clearBufferfv( gl.COLOR, i, [ 0, 0, 0, 1 ] );

						}

					}

				}

				if ( depth && stencil ) {

					gl.clearBufferfi( gl.DEPTH_STENCIL, 0, clearDepth, clearStencil );

				} else if ( depth ) {

					gl.clearBufferfv( gl.DEPTH, 0, [ clearDepth ] );

				} else if ( stencil ) {

					gl.clearBufferiv( gl.STENCIL, 0, [ clearStencil ] );

				}

			}

		}

	}
```
</details>

##### `beginCompute(computeGroup: Node | Node[]): void`

<details><summary>Code</summary>

```ts
beginCompute( computeGroup ) {

		const { state, gl } = this;

		state.bindFramebuffer( gl.FRAMEBUFFER, null );
		this.initTimestampQuery( computeGroup );

	}
```
</details>

##### `compute(computeGroup: Node | Node[], computeNode: Node, bindings: BindGroup[], pipeline: ComputePipeline, count: number): void`

<details><summary>Code</summary>

```ts
compute( computeGroup, computeNode, bindings, pipeline, count = null ) {

		const { state, gl } = this;

		if ( this.discard === false ) {

			// required here to handle async behaviour of render.compute()
			gl.enable( gl.RASTERIZER_DISCARD );
			this.discard = true;

		}

		const { programGPU, transformBuffers, attributes } = this.get( pipeline );

		const vaoKey = this._getVaoKey( attributes );

		const vaoGPU = this.vaoCache[ vaoKey ];

		if ( vaoGPU === undefined ) {

			this.vaoCache[ vaoKey ] = this._createVao( attributes );

		} else {

			state.setVertexState( vaoGPU );

		}

		state.useProgram( programGPU );

		this._bindUniforms( bindings );

		const transformFeedbackGPU = this._getTransformFeedback( transformBuffers );

		gl.bindTransformFeedback( gl.TRANSFORM_FEEDBACK, transformFeedbackGPU );
		gl.beginTransformFeedback( gl.POINTS );

		count = ( count !== null ) ? count : computeNode.count;

		if ( Array.isArray( count ) ) {

			warnOnce( 'WebGLBackend.compute(): The count parameter must be a single number, not an array.' );

			count = count[ 0 ];

		}

		if ( attributes[ 0 ].isStorageInstancedBufferAttribute ) {

			gl.drawArraysInstanced( gl.POINTS, 0, 1, count );

		} else {

			gl.drawArrays( gl.POINTS, 0, count );

		}

		gl.endTransformFeedback();
		gl.bindTransformFeedback( gl.TRANSFORM_FEEDBACK, null );

		// switch active buffers

		for ( let i = 0; i < transformBuffers.length; i ++ ) {

			const dualAttributeData = transformBuffers[ i ];

			if ( dualAttributeData.pbo && this.has( dualAttributeData.pbo ) ) {

				this.textureUtils.copyBufferToTexture( dualAttributeData.transformBuffer, dualAttributeData.pbo );

			}

			dualAttributeData.switchBuffers();


		}

	}
```
</details>

##### `finishCompute(computeGroup: Node | Node[]): void`

<details><summary>Code</summary>

```ts
finishCompute( computeGroup ) {

		const gl = this.gl;

		this.discard = false;

		gl.disable( gl.RASTERIZER_DISCARD );

		this.prepareTimestampBuffer( computeGroup );

		if ( this._currentContext ) {

			this._setFramebuffer( this._currentContext );

		}

	}
```
</details>

##### `_isRenderCameraDepthArray(renderContext: RenderContext): boolean`

<details><summary>Code</summary>

```ts
_isRenderCameraDepthArray( renderContext ) {

		return renderContext.depthTexture && renderContext.depthTexture.isArrayTexture && renderContext.camera.isArrayCamera;

	}
```
</details>

##### `draw(renderObject: RenderObject): void`

<details><summary>Code</summary>

```ts
draw( renderObject/*, info*/ ) {

		const { object, pipeline, material, context, hardwareClippingPlanes } = renderObject;
		const { programGPU } = this.get( pipeline );

		const { gl, state } = this;

		const contextData = this.get( context );

		const drawParams = renderObject.getDrawParameters();

		if ( drawParams === null ) return;

		//

		this._bindUniforms( renderObject.getBindings() );

		const frontFaceCW = ( object.isMesh && object.matrixWorld.determinant() < 0 );

		state.setMaterial( material, frontFaceCW, hardwareClippingPlanes );

		state.useProgram( programGPU );

		// vertex state

		const attributes = renderObject.getAttributes();
		const attributesData = this.get( attributes );

		let vaoGPU = attributesData.vaoGPU;

		if ( vaoGPU === undefined ) {

			const vaoKey = this._getVaoKey( attributes );

			vaoGPU = this.vaoCache[ vaoKey ];

			if ( vaoGPU === undefined ) {

				vaoGPU = this._createVao( attributes );

				this.vaoCache[ vaoKey ] = vaoGPU;
				attributesData.vaoGPU = vaoGPU;

			}

		}

		const index = renderObject.getIndex();
		const indexGPU = ( index !== null ) ? this.get( index ).bufferGPU : null;

		state.setVertexState( vaoGPU, indexGPU );

		//

		const lastObject = contextData.lastOcclusionObject;

		if ( lastObject !== object && lastObject !== undefined ) {

			if ( lastObject !== null && lastObject.occlusionTest === true ) {

				gl.endQuery( gl.ANY_SAMPLES_PASSED );

				contextData.occlusionQueryIndex ++;

			}

			if ( object.occlusionTest === true ) {

				const query = gl.createQuery();

				gl.beginQuery( gl.ANY_SAMPLES_PASSED, query );

				contextData.occlusionQueries[ contextData.occlusionQueryIndex ] = query;
				contextData.occlusionQueryObjects[ contextData.occlusionQueryIndex ] = object;

			}

			contextData.lastOcclusionObject = object;

		}

		//
		const renderer = this.bufferRenderer;

		if ( object.isPoints ) renderer.mode = gl.POINTS;
		else if ( object.isLineSegments ) renderer.mode = gl.LINES;
		else if ( object.isLine ) renderer.mode = gl.LINE_STRIP;
		else if ( object.isLineLoop ) renderer.mode = gl.LINE_LOOP;
		else {

			if ( material.wireframe === true ) {

				state.setLineWidth( material.wireframeLinewidth * this.renderer.getPixelRatio() );
				renderer.mode = gl.LINES;

			} else {

				renderer.mode = gl.TRIANGLES;

			}

		}

		//

		const { vertexCount, instanceCount } = drawParams;
		let { firstVertex } = drawParams;

		renderer.object = object;

		if ( index !== null ) {

			firstVertex *= index.array.BYTES_PER_ELEMENT;

			const indexData = this.get( index );

			renderer.index = index.count;
			renderer.type = indexData.type;

		} else {

			renderer.index = 0;

		}

		const draw = () => {

			if ( object.isBatchedMesh ) {

				if ( object._multiDrawInstances !== null ) {

					// @deprecated, r174
					warnOnce( 'THREE.WebGLBackend: renderMultiDrawInstances has been deprecated and will be removed in r184. Append to renderMultiDraw arguments and use indirection.' );
					renderer.renderMultiDrawInstances( object._multiDrawStarts, object._multiDrawCounts, object._multiDrawCount, object._multiDrawInstances );

				} else if ( ! this.hasFeature( 'WEBGL_multi_draw' ) ) {

					warnOnce( 'THREE.WebGLRenderer: WEBGL_multi_draw not supported.' );

				} else {

					renderer.renderMultiDraw( object._multiDrawStarts, object._multiDrawCounts, object._multiDrawCount );

				}

			} else if ( instanceCount > 1 ) {

				renderer.renderInstances( firstVertex, vertexCount, instanceCount );

			} else {

				renderer.render( firstVertex, vertexCount );

			}

		};

		if ( renderObject.camera.isArrayCamera === true && renderObject.camera.cameras.length > 0 && renderObject.camera.isMultiViewCamera === false ) {

			const cameraData = this.get( renderObject.camera );
			const cameras = renderObject.camera.cameras;
			const cameraIndex = renderObject.getBindingGroup( 'cameraIndex' ).bindings[ 0 ];

			if ( cameraData.indexesGPU === undefined || cameraData.indexesGPU.length !== cameras.length ) {

				const data = new Uint32Array( [ 0, 0, 0, 0 ] );
				const indexesGPU = [];

				for ( let i = 0, len = cameras.length; i < len; i ++ ) {

					const bufferGPU = gl.createBuffer();

					data[ 0 ] = i;

					gl.bindBuffer( gl.UNIFORM_BUFFER, bufferGPU );
					gl.bufferData( gl.UNIFORM_BUFFER, data, gl.STATIC_DRAW );

					indexesGPU.push( bufferGPU );

				}

				cameraData.indexesGPU = indexesGPU; // TODO: Create a global library for this

			}

			const cameraIndexData = this.get( cameraIndex );
			const pixelRatio = this.renderer.getPixelRatio();

			const renderTarget = this._currentContext.renderTarget;
			const isRenderCameraDepthArray = this._isRenderCameraDepthArray( this._currentContext );
			const prevActiveCubeFace = this._currentContext.activeCubeFace;

			if ( isRenderCameraDepthArray ) {

				// Clear the depth texture
				const textureData = this.get( renderTarget.depthTexture );

				if ( textureData.clearedRenderId !== this.renderer._nodes.nodeFrame.renderId ) {

					textureData.clearedRenderId = this.renderer._nodes.nodeFrame.renderId;

					const { stencilBuffer } = renderTarget;

					for ( let i = 0, len = cameras.length; i < len; i ++ ) {

						this.renderer._activeCubeFace = i;
						this._currentContext.activeCubeFace = i;

						this._setFramebuffer( this._currentContext );
						this.clear( false, true, stencilBuffer, this._currentContext, false );

					}

					this.renderer._activeCubeFace = prevActiveCubeFace;
					this._currentContext.activeCubeFace = prevActiveCubeFace;

				}

			}

			for ( let i = 0, len = cameras.length; i < len; i ++ ) {

				const subCamera = cameras[ i ];

				if ( object.layers.test( subCamera.layers ) ) {

					if ( isRenderCameraDepthArray ) {

						// Update the active layer
						this.renderer._activeCubeFace = i;
						this._currentContext.activeCubeFace = i;

						this._setFramebuffer( this._currentContext );

					}

					const vp = subCamera.viewport;

					if ( vp !== undefined ) {

						const x = vp.x * pixelRatio;
						const y = vp.y * pixelRatio;
						const width = vp.width * pixelRatio;
						const height = vp.height * pixelRatio;

						state.viewport(
							Math.floor( x ),
							Math.floor( renderObject.context.height - height - y ),
							Math.floor( width ),
							Math.floor( height )
						);

					}

					state.bindBufferBase( gl.UNIFORM_BUFFER, cameraIndexData.index, cameraData.indexesGPU[ i ] );

					draw();

				}

				this._currentContext.activeCubeFace = prevActiveCubeFace;
				this.renderer._activeCubeFace = prevActiveCubeFace;

			}

		} else {

			draw();

		}

	}
```
</details>

##### `needsRenderUpdate(): boolean`

<details><summary>Code</summary>

```ts
needsRenderUpdate( /*renderObject*/ ) {

		return false;

	}
```
</details>

##### `getRenderCacheKey(): string`

<details><summary>Code</summary>

```ts
getRenderCacheKey( /*renderObject*/ ) {

		return '';

	}
```
</details>

##### `createDefaultTexture(texture: Texture): void`

<details><summary>Code</summary>

```ts
createDefaultTexture( texture ) {

		this.textureUtils.createDefaultTexture( texture );

	}
```
</details>

##### `createTexture(texture: Texture, options: any): void`

<details><summary>Code</summary>

```ts
createTexture( texture, options ) {

		this.textureUtils.createTexture( texture, options );

	}
```
</details>

##### `updateTexture(texture: Texture, options: any): void`

<details><summary>Code</summary>

```ts
updateTexture( texture, options ) {

		this.textureUtils.updateTexture( texture, options );

	}
```
</details>

##### `generateMipmaps(texture: Texture): void`

<details><summary>Code</summary>

```ts
generateMipmaps( texture ) {

		this.textureUtils.generateMipmaps( texture );

	}
```
</details>

##### `destroyTexture(texture: Texture): void`

<details><summary>Code</summary>

```ts
destroyTexture( texture ) {

		this.textureUtils.destroyTexture( texture );

	}
```
</details>

##### `copyTextureToBuffer(texture: Texture, x: number, y: number, width: number, height: number, faceIndex: number): Promise<TypedArray>`

<details><summary>Code</summary>

```ts
async copyTextureToBuffer( texture, x, y, width, height, faceIndex ) {

		return this.textureUtils.copyTextureToBuffer( texture, x, y, width, height, faceIndex );

	}
```
</details>

##### `createSampler(): void`

<details><summary>Code</summary>

```ts
createSampler( /*texture*/ ) {

		//console.warn( 'Abstract class.' );

	}
```
</details>

##### `destroySampler(): void`

<details><summary>Code</summary>

```ts
destroySampler( /*texture*/ ) {}
```
</details>

##### `createNodeBuilder(object: RenderObject, renderer: Renderer): GLSLNodeBuilder`

<details><summary>Code</summary>

```ts
createNodeBuilder( object, renderer ) {

		return new GLSLNodeBuilder( object, renderer );

	}
```
</details>

##### `createProgram(program: ProgrammableStage): void`

<details><summary>Code</summary>

```ts
createProgram( program ) {

		const gl = this.gl;
		const { stage, code } = program;

		const shader = stage === 'fragment' ? gl.createShader( gl.FRAGMENT_SHADER ) : gl.createShader( gl.VERTEX_SHADER );

		gl.shaderSource( shader, code );
		gl.compileShader( shader );

		this.set( program, {
			shaderGPU: shader
		} );

	}
```
</details>

##### `destroyProgram(program: ProgrammableStage): void`

<details><summary>Code</summary>

```ts
destroyProgram( program ) {

		this.delete( program );

	}
```
</details>

##### `createRenderPipeline(renderObject: RenderObject, promises: Promise<any>[]): void`

<details><summary>Code</summary>

```ts
createRenderPipeline( renderObject, promises ) {

		const gl = this.gl;
		const pipeline = renderObject.pipeline;

		// Program

		const { fragmentProgram, vertexProgram } = pipeline;

		const programGPU = gl.createProgram();

		const fragmentShader = this.get( fragmentProgram ).shaderGPU;
		const vertexShader = this.get( vertexProgram ).shaderGPU;

		gl.attachShader( programGPU, fragmentShader );
		gl.attachShader( programGPU, vertexShader );
		gl.linkProgram( programGPU );

		this.set( pipeline, {
			programGPU,
			fragmentShader,
			vertexShader
		} );

		if ( promises !== null && this.parallel ) {

			const p = new Promise( ( resolve /*, reject*/ ) => {

				const parallel = this.parallel;
				const checkStatus = () => {

					if ( gl.getProgramParameter( programGPU, parallel.COMPLETION_STATUS_KHR ) ) {

						this._completeCompile( renderObject, pipeline );
						resolve();

					} else {

						requestAnimationFrame( checkStatus );

					}

				};

				checkStatus();

			} );

			promises.push( p );

			return;

		}

		this._completeCompile( renderObject, pipeline );

	}
```
</details>

##### `_handleSource(string: string, errorLine: number): string`

<details><summary>Code</summary>

```ts
_handleSource( string, errorLine ) {

		const lines = string.split( '\n' );
		const lines2 = [];

		const from = Math.max( errorLine - 6, 0 );
		const to = Math.min( errorLine + 6, lines.length );

		for ( let i = from; i < to; i ++ ) {

			const line = i + 1;
			lines2.push( `${line === errorLine ? '>' : ' '} ${line}: ${lines[ i ]}` );

		}

		return lines2.join( '\n' );

	}
```
</details>

##### `_getShaderErrors(gl: WebGL2RenderingContext, shader: WebGLShader, type: string): string`

<details><summary>Code</summary>

```ts
_getShaderErrors( gl, shader, type ) {

		const status = gl.getShaderParameter( shader, gl.COMPILE_STATUS );

		const shaderInfoLog = gl.getShaderInfoLog( shader ) || '';
		const errors = shaderInfoLog.trim();

		if ( status && errors === '' ) return '';

		const errorMatches = /ERROR: 0:(\d+)/.exec( errors );
		if ( errorMatches ) {

			const errorLine = parseInt( errorMatches[ 1 ] );
			return type.toUpperCase() + '\n\n' + errors + '\n\n' + this._handleSource( gl.getShaderSource( shader ), errorLine );

		} else {

			return errors;

		}

	}
```
</details>

##### `_logProgramError(programGPU: WebGLProgram, glFragmentShader: WebGLShader, glVertexShader: WebGLShader): void`

<details><summary>Code</summary>

```ts
_logProgramError( programGPU, glFragmentShader, glVertexShader ) {

		if ( this.renderer.debug.checkShaderErrors ) {

			const gl = this.gl;

			const programInfoLog = gl.getProgramInfoLog( programGPU ) || '';
			const programLog = programInfoLog.trim();

			if ( gl.getProgramParameter( programGPU, gl.LINK_STATUS ) === false ) {

				if ( typeof this.renderer.debug.onShaderError === 'function' ) {

					this.renderer.debug.onShaderError( gl, programGPU, glVertexShader, glFragmentShader );

				} else {

					// default error reporting

					const vertexErrors = this._getShaderErrors( gl, glVertexShader, 'vertex' );
					const fragmentErrors = this._getShaderErrors( gl, glFragmentShader, 'fragment' );

					console.error(
						'THREE.WebGLProgram: Shader Error ' + gl.getError() + ' - ' +
						'VALIDATE_STATUS ' + gl.getProgramParameter( programGPU, gl.VALIDATE_STATUS ) + '\n\n' +
						'Program Info Log: ' + programLog + '\n' +
						vertexErrors + '\n' +
						fragmentErrors
					);

				}

			} else if ( programLog !== '' ) {

				console.warn( 'THREE.WebGLProgram: Program Info Log:', programLog );

			}

		}

	}
```
</details>

##### `_completeCompile(renderObject: RenderObject, pipeline: RenderPipeline): void`

<details><summary>Code</summary>

```ts
_completeCompile( renderObject, pipeline ) {

		const { state, gl } = this;
		const pipelineData = this.get( pipeline );
		const { programGPU, fragmentShader, vertexShader } = pipelineData;

		if ( gl.getProgramParameter( programGPU, gl.LINK_STATUS ) === false ) {

			this._logProgramError( programGPU, fragmentShader, vertexShader );

		}

		state.useProgram( programGPU );

		// Bindings

		const bindings = renderObject.getBindings();

		this._setupBindings( bindings, programGPU );

		//

		this.set( pipeline, {
			programGPU
		} );

	}
```
</details>

##### `createComputePipeline(computePipeline: ComputePipeline, bindings: BindGroup[]): void`

<details><summary>Code</summary>

```ts
createComputePipeline( computePipeline, bindings ) {

		const { state, gl } = this;

		// Program

		const fragmentProgram = {
			stage: 'fragment',
			code: '#version 300 es\nprecision highp float;\nvoid main() {}'
		};

		this.createProgram( fragmentProgram );

		const { computeProgram } = computePipeline;

		const programGPU = gl.createProgram();

		const fragmentShader = this.get( fragmentProgram ).shaderGPU;
		const vertexShader = this.get( computeProgram ).shaderGPU;

		const transforms = computeProgram.transforms;

		const transformVaryingNames = [];
		const transformAttributeNodes = [];

		for ( let i = 0; i < transforms.length; i ++ ) {

			const transform = transforms[ i ];

			transformVaryingNames.push( transform.varyingName );
			transformAttributeNodes.push( transform.attributeNode );

		}

		gl.attachShader( programGPU, fragmentShader );
		gl.attachShader( programGPU, vertexShader );

		gl.transformFeedbackVaryings(
			programGPU,
			transformVaryingNames,
			gl.SEPARATE_ATTRIBS
		);

		gl.linkProgram( programGPU );

		if ( gl.getProgramParameter( programGPU, gl.LINK_STATUS ) === false ) {

			this._logProgramError( programGPU, fragmentShader, vertexShader );


		}

		state.useProgram( programGPU );

		// Bindings

		this._setupBindings( bindings, programGPU );

		const attributeNodes = computeProgram.attributes;
		const attributes = [];
		const transformBuffers = [];

		for ( let i = 0; i < attributeNodes.length; i ++ ) {

			const attribute = attributeNodes[ i ].node.attribute;

			attributes.push( attribute );

			if ( ! this.has( attribute ) ) this.attributeUtils.createAttribute( attribute, gl.ARRAY_BUFFER );

		}

		for ( let i = 0; i < transformAttributeNodes.length; i ++ ) {

			const attribute = transformAttributeNodes[ i ].attribute;

			if ( ! this.has( attribute ) ) this.attributeUtils.createAttribute( attribute, gl.ARRAY_BUFFER );

			const attributeData = this.get( attribute );

			transformBuffers.push( attributeData );

		}

		//

		this.set( computePipeline, {
			programGPU,
			transformBuffers,
			attributes
		} );

	}
```
</details>

##### `createBindings(bindGroup: BindGroup, bindings: BindGroup[]): void`

<details><summary>Code</summary>

```ts
createBindings( bindGroup, bindings /*, cacheIndex, version*/ ) {

		if ( this._knownBindings.has( bindings ) === false ) {

			this._knownBindings.add( bindings );

			let uniformBuffers = 0;
			let textures = 0;

			for ( const bindGroup of bindings ) {

				this.set( bindGroup, {
					textures: textures,
					uniformBuffers: uniformBuffers
				} );

				for ( const binding of bindGroup.bindings ) {

					if ( binding.isUniformBuffer ) uniformBuffers ++;
					if ( binding.isSampledTexture ) textures ++;

				}

			}

		}

		this.updateBindings( bindGroup, bindings );

	}
```
</details>

##### `updateBindings(bindGroup: BindGroup): void`

<details><summary>Code</summary>

```ts
updateBindings( bindGroup /*, bindings, cacheIndex, version*/ ) {

		const { gl } = this;

		const bindGroupData = this.get( bindGroup );

		let i = bindGroupData.uniformBuffers;
		let t = bindGroupData.textures;

		for ( const binding of bindGroup.bindings ) {

			if ( binding.isUniformsGroup || binding.isUniformBuffer ) {

				const data = binding.buffer;
				const bufferGPU = gl.createBuffer();

				gl.bindBuffer( gl.UNIFORM_BUFFER, bufferGPU );
				gl.bufferData( gl.UNIFORM_BUFFER, data, gl.DYNAMIC_DRAW );

				this.set( binding, {
					index: i ++,
					bufferGPU
				} );

			} else if ( binding.isSampledTexture ) {

				const { textureGPU, glTextureType } = this.get( binding.texture );

				this.set( binding, {
					index: t ++,
					textureGPU,
					glTextureType
				} );

			}

		}

	}
```
</details>

##### `updateBinding(binding: Buffer<ArrayBufferLike>): void`

<details><summary>Code</summary>

```ts
updateBinding( binding ) {

		const gl = this.gl;

		if ( binding.isUniformsGroup || binding.isUniformBuffer ) {

			const bindingData = this.get( binding );
			const bufferGPU = bindingData.bufferGPU;
			const data = binding.buffer;

			gl.bindBuffer( gl.UNIFORM_BUFFER, bufferGPU );
			gl.bufferData( gl.UNIFORM_BUFFER, data, gl.DYNAMIC_DRAW );

		}

	}
```
</details>

##### `createIndexAttribute(attribute: BufferAttribute): void`

<details><summary>Code</summary>

```ts
createIndexAttribute( attribute ) {

		const gl = this.gl;

		this.attributeUtils.createAttribute( attribute, gl.ELEMENT_ARRAY_BUFFER );

	}
```
</details>

##### `createAttribute(attribute: BufferAttribute): void`

<details><summary>Code</summary>

```ts
createAttribute( attribute ) {

		if ( this.has( attribute ) ) return;

		const gl = this.gl;

		this.attributeUtils.createAttribute( attribute, gl.ARRAY_BUFFER );

	}
```
</details>

##### `createStorageAttribute(attribute: BufferAttribute): void`

<details><summary>Code</summary>

```ts
createStorageAttribute( attribute ) {

		if ( this.has( attribute ) ) return;

		const gl = this.gl;

		this.attributeUtils.createAttribute( attribute, gl.ARRAY_BUFFER );

	}
```
</details>

##### `updateAttribute(attribute: BufferAttribute): void`

<details><summary>Code</summary>

```ts
updateAttribute( attribute ) {

		this.attributeUtils.updateAttribute( attribute );

	}
```
</details>

##### `destroyAttribute(attribute: BufferAttribute): void`

<details><summary>Code</summary>

```ts
destroyAttribute( attribute ) {

		this.attributeUtils.destroyAttribute( attribute );

	}
```
</details>

##### `hasFeature(name: string): boolean`

<details><summary>Code</summary>

```ts
hasFeature( name ) {

		const keysMatching = Object.keys( GLFeatureName ).filter( key => GLFeatureName[ key ] === name );

		const extensions = this.extensions;

		for ( let i = 0; i < keysMatching.length; i ++ ) {

			if ( extensions.has( keysMatching[ i ] ) ) return true;

		}

		return false;

	}
```
</details>

##### `getMaxAnisotropy(): number`

<details><summary>Code</summary>

```ts
getMaxAnisotropy() {

		return this.capabilities.getMaxAnisotropy();

	}
```
</details>

##### `copyTextureToTexture(srcTexture: Texture, dstTexture: Texture, srcRegion: any, dstPosition: any, srcLevel: number, dstLevel: number): void`

<details><summary>Code</summary>

```ts
copyTextureToTexture( srcTexture, dstTexture, srcRegion = null, dstPosition = null, srcLevel = 0, dstLevel = 0 ) {

		this.textureUtils.copyTextureToTexture( srcTexture, dstTexture, srcRegion, dstPosition, srcLevel, dstLevel );

	}
```
</details>

##### `copyFramebufferToTexture(texture: Texture, renderContext: RenderContext, rectangle: Vector4): void`

<details><summary>Code</summary>

```ts
copyFramebufferToTexture( texture, renderContext, rectangle ) {

		this.textureUtils.copyFramebufferToTexture( texture, renderContext, rectangle );

	}
```
</details>

##### `_setFramebuffer(descriptor: RenderContext): void`

<details><summary>Code</summary>

```ts
_setFramebuffer( descriptor ) {

		const { gl, state } = this;

		let currentFrameBuffer = null;

		if ( descriptor.textures !== null ) {

			const renderTarget = descriptor.renderTarget;
			const renderTargetContextData = this.get( renderTarget );
			const { samples, depthBuffer, stencilBuffer } = renderTarget;

			const isCube = renderTarget.isWebGLCubeRenderTarget === true;
			const isRenderTarget3D = renderTarget.isRenderTarget3D === true;
			const isRenderTargetArray = renderTarget.depth > 1;
			const isXRRenderTarget = renderTarget.isXRRenderTarget === true;
			const _hasExternalTextures = ( isXRRenderTarget === true && renderTarget._hasExternalTextures === true );

			let msaaFb = renderTargetContextData.msaaFrameBuffer;
			let depthRenderbuffer = renderTargetContextData.depthRenderbuffer;
			const multisampledRTTExt = this.extensions.get( 'WEBGL_multisampled_render_to_texture' );
			const multiviewExt = this.extensions.get( 'OVR_multiview2' );
			const useMultisampledRTT = this._useMultisampledExtension( renderTarget );
			const cacheKey = getCacheKey( descriptor );

			let fb;

			if ( isCube ) {

				renderTargetContextData.cubeFramebuffers || ( renderTargetContextData.cubeFramebuffers = {} );

				fb = renderTargetContextData.cubeFramebuffers[ cacheKey ];

			} else if ( isXRRenderTarget && _hasExternalTextures === false ) {

				fb = this._xrFramebuffer;

			} else {

				renderTargetContextData.framebuffers || ( renderTargetContextData.framebuffers = {} );

				fb = renderTargetContextData.framebuffers[ cacheKey ];

			}

			if ( fb === undefined ) {

				fb = gl.createFramebuffer();

				state.bindFramebuffer( gl.FRAMEBUFFER, fb );

				const textures = descriptor.textures;
				const depthInvalidationArray = [];

				if ( isCube ) {

					renderTargetContextData.cubeFramebuffers[ cacheKey ] = fb;

					const { textureGPU } = this.get( textures[ 0 ] );

					const cubeFace = this.renderer._activeCubeFace;

					gl.framebufferTexture2D( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0, gl.TEXTURE_CUBE_MAP_POSITIVE_X + cubeFace, textureGPU, 0 );

				} else {

					renderTargetContextData.framebuffers[ cacheKey ] = fb;

					for ( let i = 0; i < textures.length; i ++ ) {

						const texture = textures[ i ];
						const textureData = this.get( texture );
						textureData.renderTarget = descriptor.renderTarget;
						textureData.cacheKey = cacheKey; // required for copyTextureToTexture()

						const attachment = gl.COLOR_ATTACHMENT0 + i;

						if ( renderTarget.multiview ) {

							multiviewExt.framebufferTextureMultisampleMultiviewOVR( gl.FRAMEBUFFER, attachment, textureData.textureGPU, 0, samples, 0, 2 );

						} else if ( isRenderTarget3D || isRenderTargetArray ) {

							const layer = this.renderer._activeCubeFace;

							gl.framebufferTextureLayer( gl.FRAMEBUFFER, attachment, textureData.textureGPU, 0, layer );

						} else {

							if ( useMultisampledRTT ) {

								multisampledRTTExt.framebufferTexture2DMultisampleEXT( gl.FRAMEBUFFER, attachment, gl.TEXTURE_2D, textureData.textureGPU, 0, samples );

							} else {

								gl.framebufferTexture2D( gl.FRAMEBUFFER, attachment, gl.TEXTURE_2D, textureData.textureGPU, 0 );

							}

						}

					}

				}

				const depthStyle = stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT;

				if ( renderTarget._autoAllocateDepthBuffer === true ) {

					const renderbuffer = gl.createRenderbuffer();
					this.textureUtils.setupRenderBufferStorage( renderbuffer, descriptor, 0, useMultisampledRTT );
					renderTargetContextData.xrDepthRenderbuffer = renderbuffer;
					depthInvalidationArray.push( stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT );

					gl.bindRenderbuffer( gl.RENDERBUFFER, renderbuffer );
					gl.framebufferRenderbuffer( gl.FRAMEBUFFER, depthStyle, gl.RENDERBUFFER, renderbuffer );


				} else {

					if ( descriptor.depthTexture !== null ) {

						depthInvalidationArray.push( stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT );

						const textureData = this.get( descriptor.depthTexture );
						textureData.renderTarget = descriptor.renderTarget;
						textureData.cacheKey = cacheKey; // required for copyTextureToTexture()

						if ( renderTarget.multiview ) {

							multiviewExt.framebufferTextureMultisampleMultiviewOVR( gl.FRAMEBUFFER, depthStyle, textureData.textureGPU, 0, samples, 0, 2 );

						} else if ( _hasExternalTextures && useMultisampledRTT ) {

							multisampledRTTExt.framebufferTexture2DMultisampleEXT( gl.FRAMEBUFFER, depthStyle, gl.TEXTURE_2D, textureData.textureGPU, 0, samples );

						} else {

							if ( descriptor.depthTexture.isArrayTexture ) {

								const layer = this.renderer._activeCubeFace;

								gl.framebufferTextureLayer( gl.FRAMEBUFFER, depthStyle, textureData.textureGPU, 0, layer );

							} else {

								gl.framebufferTexture2D( gl.FRAMEBUFFER, depthStyle, gl.TEXTURE_2D, textureData.textureGPU, 0 );

							}

						}

					}

				}

				renderTargetContextData.depthInvalidationArray = depthInvalidationArray;


			} else {

				const isRenderCameraDepthArray = this._isRenderCameraDepthArray( descriptor );

				if ( isRenderCameraDepthArray ) {

					state.bindFramebuffer( gl.FRAMEBUFFER, fb );

					const layer = this.renderer._activeCubeFace;

					const depthData = this.get( descriptor.depthTexture );
					const depthStyle = stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT;
					gl.framebufferTextureLayer(
						gl.FRAMEBUFFER,
						depthStyle,
						depthData.textureGPU,
						0,
						layer
					);

				}

				// rebind external XR textures

				if ( ( isXRRenderTarget || useMultisampledRTT || renderTarget.multiview ) && ( renderTarget._isOpaqueFramebuffer !== true ) ) {

					state.bindFramebuffer( gl.FRAMEBUFFER, fb );

					// rebind color

					const textureData = this.get( descriptor.textures[ 0 ] );

					if ( renderTarget.multiview ) {

						multiviewExt.framebufferTextureMultisampleMultiviewOVR( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0, textureData.textureGPU, 0, samples, 0, 2 );

					} else if ( useMultisampledRTT ) {

						multisampledRTTExt.framebufferTexture2DMultisampleEXT( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0, gl.TEXTURE_2D, textureData.textureGPU, 0, samples );

					} else {

						gl.framebufferTexture2D( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0, gl.TEXTURE_2D, textureData.textureGPU, 0 );

					}

					// rebind depth

					const depthStyle = stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT;

					if ( renderTarget._autoAllocateDepthBuffer === true ) {

						const renderbuffer = renderTargetContextData.xrDepthRenderbuffer;
						gl.bindRenderbuffer( gl.RENDERBUFFER, renderbuffer );
						gl.framebufferRenderbuffer( gl.FRAMEBUFFER, depthStyle, gl.RENDERBUFFER, renderbuffer );

					} else {

						const textureData = this.get( descriptor.depthTexture );

						if ( renderTarget.multiview ) {

							multiviewExt.framebufferTextureMultisampleMultiviewOVR( gl.FRAMEBUFFER, depthStyle, textureData.textureGPU, 0, samples, 0, 2 );

						} else if ( useMultisampledRTT ) {

							multisampledRTTExt.framebufferTexture2DMultisampleEXT( gl.FRAMEBUFFER, depthStyle, gl.TEXTURE_2D, textureData.textureGPU, 0, samples );

						} else {

							gl.framebufferTexture2D( gl.FRAMEBUFFER, depthStyle, gl.TEXTURE_2D, textureData.textureGPU, 0 );

						}

					}

				}

			}

			if ( samples > 0 && useMultisampledRTT === false && ! renderTarget.multiview ) {

				if ( msaaFb === undefined ) {

					const invalidationArray = [];

					msaaFb = gl.createFramebuffer();

					state.bindFramebuffer( gl.FRAMEBUFFER, msaaFb );

					const msaaRenderbuffers = [];

					const textures = descriptor.textures;

					for ( let i = 0; i < textures.length; i ++ ) {

						msaaRenderbuffers[ i ] = gl.createRenderbuffer();

						gl.bindRenderbuffer( gl.RENDERBUFFER, msaaRenderbuffers[ i ] );

						invalidationArray.push( gl.COLOR_ATTACHMENT0 + i );

						const texture = descriptor.textures[ i ];
						const textureData = this.get( texture );

						gl.renderbufferStorageMultisample( gl.RENDERBUFFER, samples, textureData.glInternalFormat, descriptor.width, descriptor.height );
						gl.framebufferRenderbuffer( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0 + i, gl.RENDERBUFFER, msaaRenderbuffers[ i ] );


					}

					gl.bindRenderbuffer( gl.RENDERBUFFER, null );

					renderTargetContextData.msaaFrameBuffer = msaaFb;
					renderTargetContextData.msaaRenderbuffers = msaaRenderbuffers;

					if ( depthBuffer && depthRenderbuffer === undefined ) {

						depthRenderbuffer = gl.createRenderbuffer();
						this.textureUtils.setupRenderBufferStorage( depthRenderbuffer, descriptor, samples );

						renderTargetContextData.depthRenderbuffer = depthRenderbuffer;

						const depthStyle = stencilBuffer ? gl.DEPTH_STENCIL_ATTACHMENT : gl.DEPTH_ATTACHMENT;
						invalidationArray.push( depthStyle );

					}

					renderTargetContextData.invalidationArray = invalidationArray;

				}

				currentFrameBuffer = renderTargetContextData.msaaFrameBuffer;

			} else {

				currentFrameBuffer = fb;

			}

			state.drawBuffers( descriptor, fb );

		}

		state.bindFramebuffer( gl.FRAMEBUFFER, currentFrameBuffer );

	}
```
</details>

##### `_getVaoKey(attributes: BufferAttribute[]): string`

<details><summary>Code</summary>

```ts
_getVaoKey( attributes ) {

		let key = '';

		for ( let i = 0; i < attributes.length; i ++ ) {

			const attributeData = this.get( attributes[ i ] );

			key += ':' + attributeData.id;

		}

		return key;

	}
```
</details>

##### `_createVao(attributes: BufferAttribute[]): any`

<details><summary>Code</summary>

```ts
_createVao( attributes ) {

		const { gl } = this;

		const vaoGPU = gl.createVertexArray();

		gl.bindVertexArray( vaoGPU );

		for ( let i = 0; i < attributes.length; i ++ ) {

			const attribute = attributes[ i ];
			const attributeData = this.get( attribute );

			gl.bindBuffer( gl.ARRAY_BUFFER, attributeData.bufferGPU );
			gl.enableVertexAttribArray( i );

			let stride, offset;

			if ( attribute.isInterleavedBufferAttribute === true ) {

				stride = attribute.data.stride * attributeData.bytesPerElement;
				offset = attribute.offset * attributeData.bytesPerElement;

			} else {

				stride = 0;
				offset = 0;

			}

			if ( attributeData.isInteger ) {

				gl.vertexAttribIPointer( i, attribute.itemSize, attributeData.type, stride, offset );

			} else {

				gl.vertexAttribPointer( i, attribute.itemSize, attributeData.type, attribute.normalized, stride, offset );

			}

			if ( attribute.isInstancedBufferAttribute && ! attribute.isInterleavedBufferAttribute ) {

				gl.vertexAttribDivisor( i, attribute.meshPerAttribute );

			} else if ( attribute.isInterleavedBufferAttribute && attribute.data.isInstancedInterleavedBuffer ) {

				gl.vertexAttribDivisor( i, attribute.data.meshPerAttribute );

			}

		}

		gl.bindBuffer( gl.ARRAY_BUFFER, null );

		return vaoGPU;

	}
```
</details>

##### `_getTransformFeedback(transformBuffers: DualAttributeData[]): WebGLTransformFeedback`

<details><summary>Code</summary>

```ts
_getTransformFeedback( transformBuffers ) {

		let key = '';

		for ( let i = 0; i < transformBuffers.length; i ++ ) {

			key += ':' + transformBuffers[ i ].id;

		}

		let transformFeedbackGPU = this.transformFeedbackCache[ key ];

		if ( transformFeedbackGPU !== undefined ) {

			return transformFeedbackGPU;

		}

		const { gl } = this;

		transformFeedbackGPU = gl.createTransformFeedback();

		gl.bindTransformFeedback( gl.TRANSFORM_FEEDBACK, transformFeedbackGPU );

		for ( let i = 0; i < transformBuffers.length; i ++ ) {

			const attributeData = transformBuffers[ i ];

			gl.bindBufferBase( gl.TRANSFORM_FEEDBACK_BUFFER, i, attributeData.transformBuffer );

		}

		gl.bindTransformFeedback( gl.TRANSFORM_FEEDBACK, null );

		this.transformFeedbackCache[ key ] = transformFeedbackGPU;

		return transformFeedbackGPU;

	}
```
</details>

##### `_setupBindings(bindings: BindGroup[], programGPU: WebGLProgram): void`

<details><summary>Code</summary>

```ts
_setupBindings( bindings, programGPU ) {

		const gl = this.gl;

		for ( const bindGroup of bindings ) {

			for ( const binding of bindGroup.bindings ) {

				const bindingData = this.get( binding );
				const index = bindingData.index;

				if ( binding.isUniformsGroup || binding.isUniformBuffer ) {

					const location = gl.getUniformBlockIndex( programGPU, binding.name );
					gl.uniformBlockBinding( programGPU, location, index );

				} else if ( binding.isSampledTexture ) {

					const location = gl.getUniformLocation( programGPU, binding.name );
					gl.uniform1i( location, index );

				}

			}

		}

	}
```
</details>

##### `_bindUniforms(bindings: BindGroup[]): void`

<details><summary>Code</summary>

```ts
_bindUniforms( bindings ) {

		const { gl, state } = this;

		for ( const bindGroup of bindings ) {

			for ( const binding of bindGroup.bindings ) {

				const bindingData = this.get( binding );
				const index = bindingData.index;

				if ( binding.isUniformsGroup || binding.isUniformBuffer ) {

					// TODO USE bindBufferRange to group multiple uniform buffers
					state.bindBufferBase( gl.UNIFORM_BUFFER, index, bindingData.bufferGPU );

				} else if ( binding.isSampledTexture ) {

					state.bindTexture( bindingData.glTextureType, bindingData.textureGPU, gl.TEXTURE0 + index );

				}

			}

		}

	}
```
</details>

##### `_useMultisampledExtension(renderTarget: RenderTarget): boolean`

<details><summary>Code</summary>

```ts
_useMultisampledExtension( renderTarget ) {

		if ( renderTarget.multiview === true ) {

			return true;

		}

		return renderTarget.samples > 0 && this.extensions.has( 'WEBGL_multisampled_render_to_texture' ) === true && renderTarget._autoAllocateDepthBuffer !== false;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		const extension = this.extensions.get( 'WEBGL_lose_context' );
		if ( extension ) extension.loseContext();

		this.renderer.domElement.removeEventListener( 'webglcontextlost', this._onContextLost );

	}
```
</details>


---