[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGPUBackend.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 56 |
| 🧱 Classes | 1 |
| 📦 Imports | 15 |
| 📊 Variables & Constants | 118 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgpu/WebGPUBackend.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `GPUFeatureName` | `./utils/WebGPUConstants.js` |
| `GPULoadOp` | `./utils/WebGPUConstants.js` |
| `GPUStoreOp` | `./utils/WebGPUConstants.js` |
| `GPUIndexFormat` | `./utils/WebGPUConstants.js` |
| `GPUTextureViewDimension` | `./utils/WebGPUConstants.js` |
| `WGSLNodeBuilder` | `./nodes/WGSLNodeBuilder.js` |
| `Backend` | `../common/Backend.js` |
| `WebGPUUtils` | `./utils/WebGPUUtils.js` |
| `WebGPUAttributeUtils` | `./utils/WebGPUAttributeUtils.js` |
| `WebGPUBindingUtils` | `./utils/WebGPUBindingUtils.js` |
| `WebGPUPipelineUtils` | `./utils/WebGPUPipelineUtils.js` |
| `WebGPUTextureUtils` | `./utils/WebGPUTextureUtils.js` |
| `WebGPUCoordinateSystem` | `../../constants.js` |
| `WebGPUTimestampQueryPool` | `./utils/WebGPUTimestampQueryPool.js` |
| `warnOnce` | `../../utils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `parameters` | `any` | let/var | `this.parameters` | ✗ |
| `device` | `any` | let/var | `*not shown*` | ✗ |
| `adapterOptions` | `{ powerPreference: any; featureLevel:...` | let/var | `{ powerPreference: parameters.powerPreference, featureLevel: parameters.compa...` | ✗ |
| `adapter` | `any` | let/var | `( typeof navigator !== 'undefined' ) ? await navigator.gpu.requestAdapter( ad...` | ✗ |
| `supportedFeatures` | `any[]` | let/var | `[]` | ✗ |
| `deviceDescriptor` | `{ requiredFeatures: string[]; require...` | let/var | `{ requiredFeatures: supportedFeatures, requiredLimits: parameters.requiredLim...` | ✗ |
| `deviceLossInfo` | `{ api: string; message: any; reason: ...` | let/var | `{ api: 'WebGPU', message: info.message \|\| 'Unknown reason', reason: info.re...` | ✗ |
| `context` | `any` | let/var | `( parameters.context !== undefined ) ? parameters.context : renderer.domEleme...` | ✗ |
| `alphaMode` | `"opaque" \| "premultiplied"` | let/var | `parameters.alpha ? 'premultiplied' : 'opaque'` | ✗ |
| `descriptor` | `any` | let/var | `this.defaultRenderPassdescriptor` | ✗ |
| `renderer` | `Renderer` | let/var | `this.renderer` | ✗ |
| `colorAttachment` | `any` | let/var | `descriptor.colorAttachments[ 0 ]` | ✗ |
| `colorAttachment` | `any` | let/var | `descriptor.colorAttachments[ 0 ]` | ✗ |
| `renderTarget` | `any` | let/var | `renderContext.renderTarget` | ✗ |
| `descriptors` | `any` | let/var | `renderTargetData.descriptors` | ✗ |
| `descriptorBase` | `any` | let/var | `descriptors[ cacheKey ]` | ✗ |
| `textures` | `any` | let/var | `renderContext.textures` | ✗ |
| `textureViews` | `any[]` | let/var | `[]` | ✗ |
| `sliceIndex` | `any` | let/var | `*not shown*` | ✗ |
| `viewDescriptor` | `{ label: string; baseMipLevel: any; m...` | let/var | `{ label: `colorAttachment_${ i }`, baseMipLevel: renderContext.activeMipmapLe...` | ✗ |
| `cameras` | `any` | let/var | `renderContext.camera.cameras` | ✗ |
| `layerViewDescriptor` | `{ baseArrayLayer: number; arrayLayerC...` | let/var | `{ ...viewDescriptor, baseArrayLayer: layer, arrayLayerCount: 1, dimension: GP...` | ✗ |
| `view` | `any` | let/var | `*not shown*` | ✗ |
| `resolveTarget` | `any` | let/var | `*not shown*` | ✗ |
| `options` | `{}` | let/var | `{}` | ✗ |
| `descriptor` | `{ colorAttachments: any[]; }` | let/var | `{ colorAttachments: [] }` | ✗ |
| `viewInfo` | `any` | let/var | `descriptorBase.textureViews[ i ]` | ✗ |
| `clearValue` | `{ r: number; g: number; b: number; a:...` | let/var | `{ r: 0, g: 0, b: 0, a: 1 }` | ✗ |
| `device` | `GPUDevice` | let/var | `this.device` | ✗ |
| `occlusionQueryCount` | `any` | let/var | `renderContext.occlusionQueryCount` | ✗ |
| `occlusionQuerySet` | `any` | let/var | `*not shown*` | ✗ |
| `descriptor` | `any` | let/var | `*not shown*` | ✗ |
| `depthStencilAttachment` | `any` | let/var | `descriptor.depthStencilAttachment` | ✗ |
| `colorAttachments` | `any` | let/var | `descriptor.colorAttachments` | ✗ |
| `colorAttachment` | `any` | let/var | `colorAttachments[ i ]` | ✗ |
| `colorAttachment` | `any` | let/var | `descriptor.colorAttachments[ 0 ]` | ✗ |
| `cameras` | `any` | let/var | `renderContext.camera.cameras` | ✗ |
| `bundleSets` | `{ attributes: {}; bindingGroups: any[...` | let/var | `{ attributes: {}, bindingGroups: [], pipeline: null, index: null }` | ✗ |
| `depthStencilAttachment` | `any` | let/var | `descriptor.depthStencilAttachment` | ✗ |
| `layerDescriptor` | `any` | let/var | `{ ...descriptor, colorAttachments: [ { ...descriptor.colorAttachments[ 0 ], v...` | ✗ |
| `layerIndex` | `number` | let/var | `i` | ✗ |
| `layerDescriptor` | `any` | let/var | `renderContextData.layerDescriptors[ i ]` | ✗ |
| `depthAttachment` | `any` | let/var | `layerDescriptor.depthStencilAttachment` | ✗ |
| `occlusionQueryCount` | `any` | let/var | `renderContext.occlusionQueryCount` | ✗ |
| `encoder` | `any` | let/var | `renderContextData.encoder` | ✗ |
| `bundles` | `any[]` | let/var | `[]` | ✗ |
| `bundleEncoder` | `any` | let/var | `renderContextData.bundleEncoders[ i ]` | ✗ |
| `layerDescriptor` | `any` | let/var | `renderContextData.layerDescriptors[ i ]` | ✗ |
| `bufferSize` | `number` | let/var | `occlusionQueryCount * 8` | ✗ |
| `textures` | `any` | let/var | `renderContext.textures` | ✗ |
| `texture` | `any` | let/var | `textures[ i ]` | ✗ |
| `occluded` | `WeakSet<WeakKey>` | let/var | `new WeakSet()` | ✗ |
| `results` | `BigUint64Array<any>` | let/var | `new BigUint64Array( buffer )` | ✗ |
| `device` | `GPUDevice` | let/var | `this.device` | ✗ |
| `renderer` | `Renderer` | let/var | `this.renderer` | ✗ |
| `colorAttachments` | `any[]` | let/var | `[]` | ✗ |
| `depthStencilAttachment` | `any` | let/var | `*not shown*` | ✗ |
| `clearValue` | `any` | let/var | `*not shown*` | ✗ |
| `supportsDepth` | `any` | let/var | `*not shown*` | ✗ |
| `supportsStencil` | `any` | let/var | `*not shown*` | ✗ |
| `colorAttachment` | `any` | let/var | `colorAttachments[ 0 ]` | ✗ |
| `clearConfig` | `{ loadOp: string; clearValue: { r: an...` | let/var | `{ loadOp: color ? GPULoadOp.Clear : GPULoadOp.Load, clearValue: color ? clear...` | ✗ |
| `descriptor` | `{ label: string; }` | let/var | `{ label: 'computeGroup_' + computeGroup.id }` | ✗ |
| `pipelineGPU` | `any` | let/var | `this.get( pipeline ).pipeline` | ✗ |
| `bindGroup` | `BindGroup` | let/var | `bindings[ i ]` | ✗ |
| `dispatchSize` | `any` | let/var | `*not shown*` | ✗ |
| `count` | `number` | let/var | `dispatchSizeOrCount` | ✗ |
| `workgroupSize` | `any` | let/var | `computeNode.workgroupSize` | ✗ |
| `size` | `any` | let/var | `workgroupSize[ 0 ]` | ✗ |
| `maxComputeWorkgroupsPerDime...` | `any` | let/var | `this.device.limits.maxComputeWorkgroupsPerDimension` | ✗ |
| `pipelineGPU` | `any` | let/var | `this.get( pipeline ).pipeline` | ✗ |
| `hasIndex` | `boolean` | let/var | `( index !== null )` | ✗ |
| `currentBindingGroups` | `any` | let/var | `currentSets.bindingGroups` | ✗ |
| `bindGroup` | `any` | let/var | `bindings[ i ]` | ✗ |
| `buffer` | `any` | let/var | `this.get( index ).buffer` | ✗ |
| `indexFormat` | `string` | let/var | `( index.array instanceof Uint16Array ) ? GPUIndexFormat.Uint16 : GPUIndexForm...` | ✗ |
| `vertexBuffer` | `any` | let/var | `vertexBuffers[ i ]` | ✗ |
| `buffer` | `any` | let/var | `this.get( vertexBuffer ).buffer` | ✗ |
| `starts` | `any` | let/var | `object._multiDrawStarts` | ✗ |
| `counts` | `any` | let/var | `object._multiDrawCounts` | ✗ |
| `drawCount` | `any` | let/var | `object._multiDrawCount` | ✗ |
| `drawInstances` | `any` | let/var | `object._multiDrawInstances` | ✗ |
| `count` | `any` | let/var | `drawInstances ? drawInstances[ i ] : 1` | ✗ |
| `firstInstance` | `number` | let/var | `count > 1 ? 0 : i` | ✗ |
| `buffer` | `any` | let/var | `this.get( indirect ).buffer` | ✗ |
| `buffer` | `any` | let/var | `this.get( indirect ).buffer` | ✗ |
| `cameras` | `any` | let/var | `renderObject.camera.cameras` | ✗ |
| `indexesGPU` | `any[]` | let/var | `[]` | ✗ |
| `data` | `Uint32Array<ArrayBuffer>` | let/var | `new Uint32Array( [ 0, 0, 0, 0 ] )` | ✗ |
| `subCamera` | `any` | let/var | `cameras[ i ]` | ✗ |
| `vp` | `any` | let/var | `subCamera.viewport` | ✗ |
| `pass` | `any` | let/var | `renderContextData.currentPass` | ✗ |
| `sets` | `any` | let/var | `renderContextData.currentSets` | ✗ |
| `bundleEncoder` | `any` | let/var | `renderContextData.bundleEncoders[ i ]` | ✗ |
| `bundleSets` | `any` | let/var | `renderContextData.bundleSets[ i ]` | ✗ |
| `lastObject` | `any` | let/var | `renderContextData.lastOcclusionObject` | ✗ |
| `utils` | `WebGPUUtils` | let/var | `this.utils` | ✗ |
| `needsUpdate` | `boolean` | let/var | `false` | ✗ |
| `utils` | `WebGPUUtils` | let/var | `this.utils` | ✗ |
| `renderContext` | `any` | let/var | `renderObject.context` | ✗ |
| `type` | `"compute" \| "render"` | let/var | `renderContext.isComputeNode ? 'compute' : 'render'` | ✗ |
| `timestampQueryPool` | `any` | let/var | `this.timestampQueryPool[ type ]` | ✗ |
| `bundleEncoder` | `any` | let/var | `renderContextData.currentPass` | ✗ |
| `usage` | `number` | let/var | `GPUBufferUsage.INDEX \| GPUBufferUsage.COPY_SRC \| GPUBufferUsage.COPY_DST` | ✗ |
| `dstX` | `number` | let/var | `0` | ✗ |
| `dstY` | `number` | let/var | `0` | ✗ |
| `dstZ` | `number` | let/var | `0` | ✗ |
| `srcX` | `number` | let/var | `0` | ✗ |
| `srcY` | `number` | let/var | `0` | ✗ |
| `srcZ` | `number` | let/var | `0` | ✗ |
| `srcWidth` | `any` | let/var | `srcTexture.image.width` | ✗ |
| `srcHeight` | `any` | let/var | `srcTexture.image.height` | ✗ |
| `srcDepth` | `number` | let/var | `1` | ✗ |
| `sourceGPU` | `any` | let/var | `this.get( srcTexture ).texture` | ✗ |
| `destinationGPU` | `any` | let/var | `this.get( dstTexture ).texture` | ✗ |
| `sourceGPU` | `any` | let/var | `null` | ✗ |
| `destinationGPU` | `any` | let/var | `this.get( texture ).texture` | ✗ |
| `encoder` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `WebGPUBackend.init(renderer: Renderer): Promise<any>`

**JSDoc:**
```typescript
/**
	 * Initializes the backend so it is ready for usage.
	 *
	 * @async
	 * @param {Renderer} renderer - The renderer.
	 * @return {Promise} A Promise that resolves when the backend has been initialized.
	 */
```

**Parameters:**

- **`renderer`** `Renderer`

**Returns:** `Promise<any>`

**Calls:**

- `super.init`
- `navigator.gpu.requestAdapter`
- `Object.values`
- `adapter.features.has`
- `supportedFeatures.push`
- `adapter.requestDevice`
- `device.lost.then`
- `renderer.onDeviceLost`
- `renderer.domElement.getContext`
- `this.hasFeature`
- `this.context.configure`
- `this.utils.getPreferredCanvasFormat`
- `this.updateSize`

**Internal Comments:**
```
// (x2)
// create the device if it is not passed with parameters (x2)
// feature support (x2)
```

<details><summary>Code</summary>

```typescript
async init( renderer ) {

		await super.init( renderer );

		//

		const parameters = this.parameters;

		// create the device if it is not passed with parameters

		let device;

		if ( parameters.device === undefined ) {

			const adapterOptions = {
				powerPreference: parameters.powerPreference,
				featureLevel: parameters.compatibilityMode ? 'compatibility' : undefined
			};

			const adapter = ( typeof navigator !== 'undefined' ) ? await navigator.gpu.requestAdapter( adapterOptions ) : null;

			if ( adapter === null ) {

				throw new Error( 'WebGPUBackend: Unable to create WebGPU adapter.' );

			}

			// feature support

			const features = Object.values( GPUFeatureName );

			const supportedFeatures = [];

			for ( const name of features ) {

				if ( adapter.features.has( name ) ) {

					supportedFeatures.push( name );

				}

			}

			const deviceDescriptor = {
				requiredFeatures: supportedFeatures,
				requiredLimits: parameters.requiredLimits
			};

			device = await adapter.requestDevice( deviceDescriptor );

		} else {

			device = parameters.device;

		}

		device.lost.then( ( info ) => {

			const deviceLossInfo = {
				api: 'WebGPU',
				message: info.message || 'Unknown reason',
				reason: info.reason || null,
				originalEvent: info
			};

			renderer.onDeviceLost( deviceLossInfo );

		} );

		const context = ( parameters.context !== undefined ) ? parameters.context : renderer.domElement.getContext( 'webgpu' );

		this.device = device;
		this.context = context;

		const alphaMode = parameters.alpha ? 'premultiplied' : 'opaque';

		this.trackTimestamp = this.trackTimestamp && this.hasFeature( GPUFeatureName.TimestampQuery );

		this.context.configure( {
			device: this.device,
			format: this.utils.getPreferredCanvasFormat(),
			usage: GPUTextureUsage.RENDER_ATTACHMENT | GPUTextureUsage.COPY_SRC,
			alphaMode: alphaMode
		} );

		this.updateSize();

	}
```
</details>

### `WebGPUBackend.getArrayBufferAsync(attribute: StorageBufferAttribute): Promise<ArrayBuffer>`

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

### `WebGPUBackend.getContext(): GPUCanvasContext`

**JSDoc:**
```typescript
/**
	 * Returns the backend's rendering context.
	 *
	 * @return {GPUCanvasContext} The rendering context.
	 */
```

**Returns:** `GPUCanvasContext`

<details><summary>Code</summary>

```typescript
getContext() {

		return this.context;

	}
```
</details>

### `WebGPUBackend._getDefaultRenderPassDescriptor(): any`

**JSDoc:**
```typescript
/**
	 * Returns the default render pass descriptor.
	 *
	 * In WebGPU, the default framebuffer must be configured
	 * like custom framebuffers so the backend needs a render
	 * pass descriptor even when rendering directly to screen.
	 *
	 * @private
	 * @return {Object} The render pass descriptor.
	 */
```

**Returns:** `any`

**Calls:**

- `this.textureUtils.getDepthBuffer( renderer.depth, renderer.stencil ).createView`
- `this.colorBuffer.createView`
- `this.context.getCurrentTexture().createView`

<details><summary>Code</summary>

```typescript
_getDefaultRenderPassDescriptor() {

		let descriptor = this.defaultRenderPassdescriptor;

		if ( descriptor === null ) {

			const renderer = this.renderer;

			descriptor = {
				colorAttachments: [ {
					view: null
				} ],
			};

			if ( this.renderer.depth === true || this.renderer.stencil === true ) {

				descriptor.depthStencilAttachment = {
					view: this.textureUtils.getDepthBuffer( renderer.depth, renderer.stencil ).createView()
				};

			}

			const colorAttachment = descriptor.colorAttachments[ 0 ];

			if ( this.renderer.samples > 0 ) {

				colorAttachment.view = this.colorBuffer.createView();

			} else {

				colorAttachment.resolveTarget = undefined;

			}

			this.defaultRenderPassdescriptor = descriptor;

		}

		const colorAttachment = descriptor.colorAttachments[ 0 ];

		if ( this.renderer.samples > 0 ) {

			colorAttachment.resolveTarget = this.context.getCurrentTexture().createView();

		} else {

			colorAttachment.view = this.context.getCurrentTexture().createView();

		}

		return descriptor;

	}
```
</details>

### `WebGPUBackend._isRenderCameraDepthArray(renderContext: RenderContext): boolean`

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

		return renderContext.depthTexture && renderContext.depthTexture.image.depth > 1 && renderContext.camera.isArrayCamera;

	}
```
</details>

### `WebGPUBackend._getRenderPassDescriptor(renderContext: RenderContext, colorAttachmentsConfig: any): any`

**JSDoc:**
```typescript
/**
	 * Returns the render pass descriptor for the given render context.
	 *
	 * @private
	 * @param {RenderContext} renderContext - The render context.
	 * @param {Object} colorAttachmentsConfig - Configuration object for the color attachments.
	 * @return {Object} The render pass descriptor.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`
- **`colorAttachmentsConfig`** `any`

**Returns:** `any`

**Calls:**

- `this.get`
- `renderTarget.removeEventListener`
- `this.delete`
- `renderTarget.hasEventListener`
- `renderTarget.addEventListener`
- `renderContext.getCacheKey`
- `this._isRenderCameraDepthArray`
- `textureData.texture.createView`
- `textureViews.push`
- `textureData.msaaTexture.createView`
- `depthTextureData.texture.createView`
- `descriptor.colorAttachments.push`

**Internal Comments:**
```
// dispose (x2)
// Apply dynamic properties to cached views
```

<details><summary>Code</summary>

```typescript
_getRenderPassDescriptor( renderContext, colorAttachmentsConfig = {} ) {

		const renderTarget = renderContext.renderTarget;
		const renderTargetData = this.get( renderTarget );

		let descriptors = renderTargetData.descriptors;

		if ( descriptors === undefined ||
			renderTargetData.width !== renderTarget.width ||
			renderTargetData.height !== renderTarget.height ||
			renderTargetData.dimensions !== renderTarget.dimensions ||
			renderTargetData.activeMipmapLevel !== renderContext.activeMipmapLevel ||
			renderTargetData.activeCubeFace !== renderContext.activeCubeFace ||
			renderTargetData.samples !== renderTarget.samples
		) {

			descriptors = {};

			renderTargetData.descriptors = descriptors;

			// dispose

			const onDispose = () => {

				renderTarget.removeEventListener( 'dispose', onDispose );
				this.delete( renderTarget );

			};

			if ( renderTarget.hasEventListener( 'dispose', onDispose ) === false ) {

				renderTarget.addEventListener( 'dispose', onDispose );

			}

		}

		const cacheKey = renderContext.getCacheKey();
		let descriptorBase = descriptors[ cacheKey ];

		if ( descriptorBase === undefined ) {

			const textures = renderContext.textures;
			const textureViews = [];

			let sliceIndex;

			const isRenderCameraDepthArray = this._isRenderCameraDepthArray( renderContext );

			for ( let i = 0; i < textures.length; i ++ ) {

				const textureData = this.get( textures[ i ] );

				const viewDescriptor = {
					label: `colorAttachment_${ i }`,
					baseMipLevel: renderContext.activeMipmapLevel,
					mipLevelCount: 1,
					baseArrayLayer: renderContext.activeCubeFace,
					arrayLayerCount: 1,
					dimension: GPUTextureViewDimension.TwoD
				};

				if ( renderTarget.isRenderTarget3D ) {

					sliceIndex = renderContext.activeCubeFace;

					viewDescriptor.baseArrayLayer = 0;
					viewDescriptor.dimension = GPUTextureViewDimension.ThreeD;
					viewDescriptor.depthOrArrayLayers = textures[ i ].image.depth;

				} else if ( renderTarget.isRenderTarget && textures[ i ].image.depth > 1 ) {

					if ( isRenderCameraDepthArray === true ) {

						const cameras = renderContext.camera.cameras;
						for ( let layer = 0; layer < cameras.length; layer ++ ) {

							const layerViewDescriptor = {
								...viewDescriptor,
								baseArrayLayer: layer,
								arrayLayerCount: 1,
								dimension: GPUTextureViewDimension.TwoD
							};
							const textureView = textureData.texture.createView( layerViewDescriptor );
							textureViews.push( {
								view: textureView,
								resolveTarget: undefined,
								depthSlice: undefined
							} );

						}

					} else {

						viewDescriptor.dimension = GPUTextureViewDimension.TwoDArray;
						viewDescriptor.depthOrArrayLayers = textures[ i ].image.depth;

					}

				}

				if ( isRenderCameraDepthArray !== true ) {

					const textureView = textureData.texture.createView( viewDescriptor );

					let view, resolveTarget;

					if ( textureData.msaaTexture !== undefined ) {

						view = textureData.msaaTexture.createView();
						resolveTarget = textureView;

					} else {

						view = textureView;
						resolveTarget = undefined;

					}

					textureViews.push( {
						view,
						resolveTarget,
						depthSlice: sliceIndex
					} );

				}

			}

			descriptorBase = { textureViews };

			if ( renderContext.depth ) {

				const depthTextureData = this.get( renderContext.depthTexture );
				const options = {};
				if ( renderContext.depthTexture.isArrayTexture ) {

					options.dimension = GPUTextureViewDimension.TwoD;
					options.arrayLayerCount = 1;
					options.baseArrayLayer = renderContext.activeCubeFace;

				}

				descriptorBase.depthStencilView = depthTextureData.texture.createView( options );

			}

			descriptors[ cacheKey ] = descriptorBase;

			renderTargetData.width = renderTarget.width;
			renderTargetData.height = renderTarget.height;
			renderTargetData.samples = renderTarget.samples;
			renderTargetData.activeMipmapLevel = renderContext.activeMipmapLevel;
			renderTargetData.activeCubeFace = renderContext.activeCubeFace;
			renderTargetData.dimensions = renderTarget.dimensions;

		}

		const descriptor = {
			colorAttachments: []
		};

		// Apply dynamic properties to cached views
		for ( let i = 0; i < descriptorBase.textureViews.length; i ++ ) {

			const viewInfo = descriptorBase.textureViews[ i ];

			let clearValue = { r: 0, g: 0, b: 0, a: 1 };
			if ( i === 0 && colorAttachmentsConfig.clearValue ) {

				clearValue = colorAttachmentsConfig.clearValue;

			}

			descriptor.colorAttachments.push( {
				view: viewInfo.view,
				depthSlice: viewInfo.depthSlice,
				resolveTarget: viewInfo.resolveTarget,
				loadOp: colorAttachmentsConfig.loadOp || GPULoadOp.Load,
				storeOp: colorAttachmentsConfig.storeOp || GPUStoreOp.Store,
				clearValue: clearValue
			} );

		}

		if ( descriptorBase.depthStencilView ) {

			descriptor.depthStencilAttachment = {
				view: descriptorBase.depthStencilView
			};

		}

		return descriptor;

	}
```
</details>

### `WebGPUBackend.beginRender(renderContext: RenderContext): void`

**JSDoc:**
```typescript
/**
	 * This method is executed at the beginning of a render call and prepares
	 * the WebGPU state for upcoming render calls
	 *
	 * @param {RenderContext} renderContext - The render context.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`

**Returns:** `void`

**Calls:**

- `this.get`
- `renderContextData.currentOcclusionQuerySet.destroy`
- `renderContextData.currentOcclusionQueryBuffer.destroy`
- `device.createQuerySet`
- `this._getDefaultRenderPassDescriptor`
- `this._getRenderPassDescriptor`
- `this.initTimestampQuery`
- `device.createCommandEncoder`
- `this._isRenderCameraDepthArray`
- `this._createDepthLayerDescriptors`
- `this._updateDepthLayerDescriptors`
- `this.pipelineUtils.createBundleEncoder`
- `renderContextData.bundleEncoders.push`
- `renderContextData.bundleSets.push`
- `encoder.beginRenderPass`
- `this.updateViewport`
- `currentPass.setScissorRect`

**Internal Comments:**
```
// Get a reference to the array of objects with queries. The renderContextData property (x4)
// can be changed by another render pass before the buffer.mapAsyc() completes. (x4)
// (x10)
// shadow arrays - prepare bundle encoders for each camera in an array camera
// Create bundle encoders for each layer (x4)
// Create separate bundle encoders for each camera in the array
// Initialize state tracking for this bundle (x2)
// We'll complete the bundles in finishRender (x4)
```

<details><summary>Code</summary>

```typescript
beginRender( renderContext ) {

		const renderContextData = this.get( renderContext );

		const device = this.device;
		const occlusionQueryCount = renderContext.occlusionQueryCount;

		let occlusionQuerySet;

		if ( occlusionQueryCount > 0 ) {

			if ( renderContextData.currentOcclusionQuerySet ) renderContextData.currentOcclusionQuerySet.destroy();
			if ( renderContextData.currentOcclusionQueryBuffer ) renderContextData.currentOcclusionQueryBuffer.destroy();

			// Get a reference to the array of objects with queries. The renderContextData property
			// can be changed by another render pass before the buffer.mapAsyc() completes.
			renderContextData.currentOcclusionQuerySet = renderContextData.occlusionQuerySet;
			renderContextData.currentOcclusionQueryBuffer = renderContextData.occlusionQueryBuffer;
			renderContextData.currentOcclusionQueryObjects = renderContextData.occlusionQueryObjects;

			//

			occlusionQuerySet = device.createQuerySet( { type: 'occlusion', count: occlusionQueryCount, label: `occlusionQuerySet_${ renderContext.id }` } );

			renderContextData.occlusionQuerySet = occlusionQuerySet;
			renderContextData.occlusionQueryIndex = 0;
			renderContextData.occlusionQueryObjects = new Array( occlusionQueryCount );

			renderContextData.lastOcclusionObject = null;

		}

		let descriptor;

		if ( renderContext.textures === null ) {

			descriptor = this._getDefaultRenderPassDescriptor();

		} else {

			descriptor = this._getRenderPassDescriptor( renderContext, { loadOp: GPULoadOp.Load } );

		}

		this.initTimestampQuery( renderContext, descriptor );

		descriptor.occlusionQuerySet = occlusionQuerySet;

		const depthStencilAttachment = descriptor.depthStencilAttachment;

		if ( renderContext.textures !== null ) {

			const colorAttachments = descriptor.colorAttachments;

			for ( let i = 0; i < colorAttachments.length; i ++ ) {

				const colorAttachment = colorAttachments[ i ];

				if ( renderContext.clearColor ) {

					colorAttachment.clearValue = i === 0 ? renderContext.clearColorValue : { r: 0, g: 0, b: 0, a: 1 };
					colorAttachment.loadOp = GPULoadOp.Clear;

				} else {

					colorAttachment.loadOp = GPULoadOp.Load;

				}

				colorAttachment.storeOp = GPUStoreOp.Store;

			}

		} else {

			const colorAttachment = descriptor.colorAttachments[ 0 ];

			if ( renderContext.clearColor ) {

				colorAttachment.clearValue = renderContext.clearColorValue;
				colorAttachment.loadOp = GPULoadOp.Clear;

			} else {

				colorAttachment.loadOp = GPULoadOp.Load;

			}

		  	colorAttachment.storeOp = GPUStoreOp.Store;

		}

		//

		if ( renderContext.depth ) {

			if ( renderContext.clearDepth ) {

				depthStencilAttachment.depthClearValue = renderContext.clearDepthValue;
				depthStencilAttachment.depthLoadOp = GPULoadOp.Clear;

			} else {

				depthStencilAttachment.depthLoadOp = GPULoadOp.Load;

			}

		  depthStencilAttachment.depthStoreOp = GPUStoreOp.Store;

		}

		if ( renderContext.stencil ) {

		  if ( renderContext.clearStencil ) {

				depthStencilAttachment.stencilClearValue = renderContext.clearStencilValue;
				depthStencilAttachment.stencilLoadOp = GPULoadOp.Clear;

			} else {

				depthStencilAttachment.stencilLoadOp = GPULoadOp.Load;

			}

		  depthStencilAttachment.stencilStoreOp = GPUStoreOp.Store;

		}

		//

		const encoder = device.createCommandEncoder( { label: 'renderContext_' + renderContext.id } );

		// shadow arrays - prepare bundle encoders for each camera in an array camera

		if ( this._isRenderCameraDepthArray( renderContext ) === true ) {

			const cameras = renderContext.camera.cameras;

			if ( ! renderContextData.layerDescriptors || renderContextData.layerDescriptors.length !== cameras.length ) {

				this._createDepthLayerDescriptors( renderContext, renderContextData, descriptor, cameras );

			} else {

				this._updateDepthLayerDescriptors( renderContext, renderContextData, cameras );

			}

			// Create bundle encoders for each layer
			renderContextData.bundleEncoders = [];
			renderContextData.bundleSets = [];

			// Create separate bundle encoders for each camera in the array
			for ( let i = 0; i < cameras.length; i ++ ) {

				const bundleEncoder = this.pipelineUtils.createBundleEncoder(
					renderContext,
					'renderBundleArrayCamera_' + i
				);

				// Initialize state tracking for this bundle
				const bundleSets = {
					attributes: {},
					bindingGroups: [],
					pipeline: null,
					index: null
				};

				renderContextData.bundleEncoders.push( bundleEncoder );
				renderContextData.bundleSets.push( bundleSets );

			}

			// We'll complete the bundles in finishRender
			renderContextData.currentPass = null;

		} else {

			const currentPass = encoder.beginRenderPass( descriptor );
			renderContextData.currentPass = currentPass;

			if ( renderContext.viewport ) {

				this.updateViewport( renderContext );

			}

			if ( renderContext.scissor ) {

				const { x, y, width, height } = renderContext.scissorValue;
				currentPass.setScissorRect( x, y, width, height );

			}

		}

		//

		renderContextData.descriptor = descriptor;
		renderContextData.encoder = encoder;
		renderContextData.currentSets = { attributes: {}, bindingGroups: [], pipeline: null, index: null };
		renderContextData.renderBundles = [];

	}
```
</details>

### `WebGPUBackend._createDepthLayerDescriptors(renderContext: RenderContext, renderContextData: any, descriptor: any, cameras: ArrayCamera): void`

**JSDoc:**
```typescript
/**
	 * This method creates layer descriptors for each camera in an array camera
	 * to prepare for rendering to a depth array texture.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @param {Object} renderContextData - The render context data.
	 * @param {Object} descriptor  - The render pass descriptor.
	 * @param {ArrayCamera} cameras - The array camera.
	 *
	 * @private
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`
- **`renderContextData`** `any`
- **`descriptor`** `any`
- **`cameras`** `ArrayCamera`

**Returns:** `void`

**Calls:**

- `this.get`
- `depthTextureData.texture.createView`
- `renderContextData.layerDescriptors.push`

<details><summary>Code</summary>

```typescript
_createDepthLayerDescriptors( renderContext, renderContextData, descriptor, cameras ) {

		const depthStencilAttachment = descriptor.depthStencilAttachment;
		renderContextData.layerDescriptors = [];

		const depthTextureData = this.get( renderContext.depthTexture );
		if ( ! depthTextureData.viewCache ) {

			depthTextureData.viewCache = [];

		}

		for ( let i = 0; i < cameras.length; i ++ ) {

			const layerDescriptor = {
				...descriptor,
				colorAttachments: [ {
					...descriptor.colorAttachments[ 0 ],
					view: descriptor.colorAttachments[ i ].view
				} ]
			};

			if ( descriptor.depthStencilAttachment ) {

				const layerIndex = i;

				if ( ! depthTextureData.viewCache[ layerIndex ] ) {

					depthTextureData.viewCache[ layerIndex ] = depthTextureData.texture.createView( {
						dimension: GPUTextureViewDimension.TwoD,
						baseArrayLayer: i,
						arrayLayerCount: 1
					} );

				}

				layerDescriptor.depthStencilAttachment = {
					view: depthTextureData.viewCache[ layerIndex ],
					depthLoadOp: depthStencilAttachment.depthLoadOp || GPULoadOp.Clear,
					depthStoreOp: depthStencilAttachment.depthStoreOp || GPUStoreOp.Store,
					depthClearValue: depthStencilAttachment.depthClearValue || 1.0
				};

				if ( renderContext.stencil ) {

					layerDescriptor.depthStencilAttachment.stencilLoadOp = depthStencilAttachment.stencilLoadOp;
					layerDescriptor.depthStencilAttachment.stencilStoreOp = depthStencilAttachment.stencilStoreOp;
					layerDescriptor.depthStencilAttachment.stencilClearValue = depthStencilAttachment.stencilClearValue;

				}

			} else {

				layerDescriptor.depthStencilAttachment = { ...depthStencilAttachment };

			}

			renderContextData.layerDescriptors.push( layerDescriptor );

		}

	}
```
</details>

### `WebGPUBackend._updateDepthLayerDescriptors(renderContext: RenderContext, renderContextData: any, cameras: ArrayCamera): void`

**JSDoc:**
```typescript
/**
	 * This method updates the layer descriptors for each camera in an array camera
	 * to prepare for rendering to a depth array texture.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @param {Object} renderContextData - The render context data.
	 * @param {ArrayCamera} cameras - The array camera.
	 *
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`
- **`renderContextData`** `any`
- **`cameras`** `ArrayCamera`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_updateDepthLayerDescriptors( renderContext, renderContextData, cameras ) {

		for ( let i = 0; i < cameras.length; i ++ ) {

			const layerDescriptor = renderContextData.layerDescriptors[ i ];

			if ( layerDescriptor.depthStencilAttachment ) {

				const depthAttachment = layerDescriptor.depthStencilAttachment;

				if ( renderContext.depth ) {

					if ( renderContext.clearDepth ) {

						depthAttachment.depthClearValue = renderContext.clearDepthValue;
						depthAttachment.depthLoadOp = GPULoadOp.Clear;

					} else {

						depthAttachment.depthLoadOp = GPULoadOp.Load;

					}

				}

				if ( renderContext.stencil ) {

					if ( renderContext.clearStencil ) {

						depthAttachment.stencilClearValue = renderContext.clearStencilValue;
						depthAttachment.stencilLoadOp = GPULoadOp.Clear;

					} else {

						depthAttachment.stencilLoadOp = GPULoadOp.Load;

					}

				}

			}

		}

	}
```
</details>

### `WebGPUBackend.finishRender(renderContext: RenderContext): void`

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
- `renderContextData.currentPass.executeBundles`
- `renderContextData.currentPass.endOcclusionQuery`
- `this._isRenderCameraDepthArray`
- `bundles.push`
- `bundleEncoder.finish`
- `encoder.beginRenderPass`
- `renderPass.setViewport`
- `renderPass.setScissorRect`
- `renderPass.executeBundles`
- `renderPass.end`
- `renderContextData.currentPass.end`
- `this.occludedResolveCache.get`
- `this.device.createBuffer`
- `this.occludedResolveCache.set`
- `renderContextData.encoder.resolveQuerySet`
- `renderContextData.encoder.copyBufferToBuffer`
- `this.resolveOccludedAsync`
- `this.device.queue.submit`
- `renderContextData.encoder.finish`
- `this.textureUtils.generateMipmaps`

**Internal Comments:**
```
// shadow arrays - Execute bundles for each layer (x2)
// (x9)
// two buffers required here - WebGPU doesn't allow usage of QUERY_RESOLVE & MAP_READ to be combined (x5)
```

<details><summary>Code</summary>

```typescript
finishRender( renderContext ) {

		const renderContextData = this.get( renderContext );
		const occlusionQueryCount = renderContext.occlusionQueryCount;

		if ( renderContextData.renderBundles.length > 0 ) {

			renderContextData.currentPass.executeBundles( renderContextData.renderBundles );

		}

		if ( occlusionQueryCount > renderContextData.occlusionQueryIndex ) {

			renderContextData.currentPass.endOcclusionQuery();

		}

		// shadow arrays - Execute bundles for each layer

		const encoder = renderContextData.encoder;

		if ( this._isRenderCameraDepthArray( renderContext ) === true ) {

		  const bundles = [];

		  for ( let i = 0; i < renderContextData.bundleEncoders.length; i ++ ) {

				const bundleEncoder = renderContextData.bundleEncoders[ i ];
				bundles.push( bundleEncoder.finish() );

			}

		  for ( let i = 0; i < renderContextData.layerDescriptors.length; i ++ ) {

				if ( i < bundles.length ) {

					const layerDescriptor = renderContextData.layerDescriptors[ i ];
					const renderPass = encoder.beginRenderPass( layerDescriptor );

					if ( renderContext.viewport ) {

						const { x, y, width, height, minDepth, maxDepth } = renderContext.viewportValue;
						renderPass.setViewport( x, y, width, height, minDepth, maxDepth );

					}

					if ( renderContext.scissor ) {

						const { x, y, width, height } = renderContext.scissorValue;
						renderPass.setScissorRect( x, y, width, height );

					}

					renderPass.executeBundles( [ bundles[ i ] ] );

					renderPass.end();

				}

			}

		} else if ( renderContextData.currentPass ) {

		  renderContextData.currentPass.end();

		}

		if ( occlusionQueryCount > 0 ) {

			const bufferSize = occlusionQueryCount * 8; // 8 byte entries for query results

			//

			let queryResolveBuffer = this.occludedResolveCache.get( bufferSize );

			if ( queryResolveBuffer === undefined ) {

				queryResolveBuffer = this.device.createBuffer(
					{
						size: bufferSize,
						usage: GPUBufferUsage.QUERY_RESOLVE | GPUBufferUsage.COPY_SRC
					}
				);

				this.occludedResolveCache.set( bufferSize, queryResolveBuffer );

			}

			//

			const readBuffer = this.device.createBuffer(
				{
					size: bufferSize,
					usage: GPUBufferUsage.COPY_DST | GPUBufferUsage.MAP_READ
				}
			);

			// two buffers required here - WebGPU doesn't allow usage of QUERY_RESOLVE & MAP_READ to be combined
			renderContextData.encoder.resolveQuerySet( renderContextData.occlusionQuerySet, 0, occlusionQueryCount, queryResolveBuffer, 0 );
			renderContextData.encoder.copyBufferToBuffer( queryResolveBuffer, 0, readBuffer, 0, bufferSize );

			renderContextData.occlusionQueryBuffer = readBuffer;

			//

			this.resolveOccludedAsync( renderContext );

		}

		this.device.queue.submit( [ renderContextData.encoder.finish() ] );


		//

		if ( renderContext.textures !== null ) {

			const textures = renderContext.textures;

			for ( let i = 0; i < textures.length; i ++ ) {

				const texture = textures[ i ];

				if ( texture.generateMipmaps === true ) {

					this.textureUtils.generateMipmaps( texture );

				}

			}

		}

	}
```
</details>

### `WebGPUBackend.isOccluded(renderContext: RenderContext, object: Object3D): boolean`

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

### `WebGPUBackend.resolveOccludedAsync(renderContext: RenderContext): Promise<any>`

**JSDoc:**
```typescript
/**
	 * This method processes the result of occlusion queries and writes it
	 * into render context data.
	 *
	 * @async
	 * @param {RenderContext} renderContext - The render context.
	 * @return {Promise} A Promise that resolves when the occlusion query results have been processed.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`

**Returns:** `Promise<any>`

**Calls:**

- `this.get`
- `currentOcclusionQueryBuffer.mapAsync`
- `currentOcclusionQueryBuffer.getMappedRange`
- `BigInt`
- `occluded.add`
- `currentOcclusionQueryBuffer.destroy`

**Internal Comments:**
```
// handle occlusion query results (x2)
```

<details><summary>Code</summary>

```typescript
async resolveOccludedAsync( renderContext ) {

		const renderContextData = this.get( renderContext );

		// handle occlusion query results

		const { currentOcclusionQueryBuffer, currentOcclusionQueryObjects } = renderContextData;

		if ( currentOcclusionQueryBuffer && currentOcclusionQueryObjects ) {

			const occluded = new WeakSet();

			renderContextData.currentOcclusionQueryObjects = null;
			renderContextData.currentOcclusionQueryBuffer = null;

			await currentOcclusionQueryBuffer.mapAsync( GPUMapMode.READ );

			const buffer = currentOcclusionQueryBuffer.getMappedRange();
			const results = new BigUint64Array( buffer );

			for ( let i = 0; i < currentOcclusionQueryObjects.length; i ++ ) {

				if ( results[ i ] === BigInt( 0 ) ) {

					occluded.add( currentOcclusionQueryObjects[ i ] );

				}

			}

			currentOcclusionQueryBuffer.destroy();

			renderContextData.occluded = occluded;

		}

	}
```
</details>

### `WebGPUBackend.updateViewport(renderContext: RenderContext): void`

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

- `this.get`
- `currentPass.setViewport`

<details><summary>Code</summary>

```typescript
updateViewport( renderContext ) {

		const { currentPass } = this.get( renderContext );
		const { x, y, width, height, minDepth, maxDepth } = renderContext.viewportValue;

		currentPass.setViewport( x, y, width, height, minDepth, maxDepth );

	}
```
</details>

### `WebGPUBackend.getClearColor(): Color4`

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
// only premultiply alpha when alphaMode is "premultiplied"
```

<details><summary>Code</summary>

```typescript
getClearColor() {

		const clearColor = super.getClearColor();

		// only premultiply alpha when alphaMode is "premultiplied"

		if ( this.renderer.alpha === true ) {

			clearColor.r *= clearColor.a;
			clearColor.g *= clearColor.a;
			clearColor.b *= clearColor.a;

		}

		return clearColor;

	}
```
</details>

### `WebGPUBackend.clear(color: boolean, depth: boolean, stencil: boolean, renderTargetContext: RenderContext): void`

**JSDoc:**
```typescript
/**
	 * Performs a clear operation.
	 *
	 * @param {boolean} color - Whether the color buffer should be cleared or not.
	 * @param {boolean} depth - Whether the depth buffer should be cleared or not.
	 * @param {boolean} stencil - Whether the stencil buffer should be cleared or not.
	 * @param {?RenderContext} [renderTargetContext=null] - The render context of the current set render target.
	 */
```

**Parameters:**

- **`color`** `boolean`
- **`depth`** `boolean`
- **`stencil`** `boolean`
- **`renderTargetContext`** `RenderContext`

**Returns:** `void`

**Calls:**

- `this.getClearColor`
- `this._getDefaultRenderPassDescriptor`
- `renderer.getClearDepth`
- `renderer.getClearStencil`
- `this._getRenderPassDescriptor`
- `device.createCommandEncoder`
- `encoder.beginRenderPass`
- `currentPass.end`
- `device.queue.submit`
- `encoder.finish`

**Internal Comments:**
```
// (x3)
```

<details><summary>Code</summary>

```typescript
clear( color, depth, stencil, renderTargetContext = null ) {

		const device = this.device;
		const renderer = this.renderer;

		let colorAttachments = [];
		let depthStencilAttachment;
		let clearValue;

		let supportsDepth;
		let supportsStencil;

		if ( color ) {

			const clearColor = this.getClearColor();
			clearValue = { r: clearColor.r, g: clearColor.g, b: clearColor.b, a: clearColor.a };

		}

		if ( renderTargetContext === null ) {

			supportsDepth = renderer.depth;
			supportsStencil = renderer.stencil;

			const descriptor = this._getDefaultRenderPassDescriptor();

			if ( color ) {

				colorAttachments = descriptor.colorAttachments;

				const colorAttachment = colorAttachments[ 0 ];

				colorAttachment.clearValue = clearValue;
				colorAttachment.loadOp = GPULoadOp.Clear;
				colorAttachment.storeOp = GPUStoreOp.Store;

			}

			if ( supportsDepth || supportsStencil ) {

				depthStencilAttachment = descriptor.depthStencilAttachment;

			}

		} else {

			supportsDepth = renderTargetContext.depth;
			supportsStencil = renderTargetContext.stencil;

			const clearConfig = {
				loadOp: color ? GPULoadOp.Clear : GPULoadOp.Load,
				clearValue: color ? clearValue : undefined
			};

			if ( supportsDepth ) {

				clearConfig.depthLoadOp = depth ? GPULoadOp.Clear : GPULoadOp.Load;
				clearConfig.depthClearValue = depth ? renderer.getClearDepth() : undefined;
				clearConfig.depthStoreOp = GPUStoreOp.Store;

			}

			if ( supportsStencil ) {

				clearConfig.stencilLoadOp = stencil ? GPULoadOp.Clear : GPULoadOp.Load;
				clearConfig.stencilClearValue = stencil ? renderer.getClearStencil() : undefined;
				clearConfig.stencilStoreOp = GPUStoreOp.Store;

			}

			const descriptor = this._getRenderPassDescriptor( renderTargetContext, clearConfig );

			colorAttachments = descriptor.colorAttachments;
			depthStencilAttachment = descriptor.depthStencilAttachment;

		}

		if ( supportsDepth && depthStencilAttachment ) {

			if ( depth ) {

				depthStencilAttachment.depthLoadOp = GPULoadOp.Clear;
				depthStencilAttachment.depthClearValue = renderer.getClearDepth();
				depthStencilAttachment.depthStoreOp = GPUStoreOp.Store;

			} else {

				depthStencilAttachment.depthLoadOp = GPULoadOp.Load;
				depthStencilAttachment.depthStoreOp = GPUStoreOp.Store;

			}

		}

		//

		if ( supportsStencil && depthStencilAttachment ) {

			if ( stencil ) {

				depthStencilAttachment.stencilLoadOp = GPULoadOp.Clear;
				depthStencilAttachment.stencilClearValue = renderer.getClearStencil();
				depthStencilAttachment.stencilStoreOp = GPUStoreOp.Store;

			} else {

				depthStencilAttachment.stencilLoadOp = GPULoadOp.Load;
				depthStencilAttachment.stencilStoreOp = GPUStoreOp.Store;

			}

		}

		//

		const encoder = device.createCommandEncoder( { label: 'clear' } );
		const currentPass = encoder.beginRenderPass( {
			colorAttachments,
			depthStencilAttachment
		} );

		currentPass.end();

		device.queue.submit( [ encoder.finish() ] );

	}
```
</details>

### `WebGPUBackend.beginCompute(computeGroup: Node | Node[]): void`

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

- `this.get`
- `this.initTimestampQuery`
- `this.device.createCommandEncoder`
- `groupGPU.cmdEncoderGPU.beginComputePass`

<details><summary>Code</summary>

```typescript
beginCompute( computeGroup ) {

		const groupGPU = this.get( computeGroup );

		const descriptor = {
			label: 'computeGroup_' + computeGroup.id
		};

		this.initTimestampQuery( computeGroup, descriptor );

		groupGPU.cmdEncoderGPU = this.device.createCommandEncoder( { label: 'computeGroup_' + computeGroup.id } );

		groupGPU.passEncoderGPU = groupGPU.cmdEncoderGPU.beginComputePass( descriptor );

	}
```
</details>

### `WebGPUBackend.compute(computeGroup: Node | Node[], computeNode: Node, bindings: BindGroup[], pipeline: ComputePipeline, dispatchSizeOrCount: number | number[]): void`

**JSDoc:**
```typescript
/**
	 * Executes a compute command for the given compute node.
	 *
	 * @param {Node|Array<Node>} computeGroup - The group of compute nodes of a compute call. Can be a single compute node.
	 * @param {Node} computeNode - The compute node.
	 * @param {Array<BindGroup>} bindings - The bindings.
	 * @param {ComputePipeline} pipeline - The compute pipeline.
	 * @param {Array<number>|number} [dispatchSizeOrCount=null] - Array with [ x, y, z ] values for dispatch or a single number for the count.
	 */
```

**Parameters:**

- **`computeGroup`** `Node | Node[]`
- **`computeNode`** `Node`
- **`bindings`** `BindGroup[]`
- **`pipeline`** `ComputePipeline`
- **`dispatchSizeOrCount`** `number | number[]`

**Returns:** `void`

**Calls:**

- `this.get`
- `this.pipelineUtils.setPipeline`
- `passEncoderGPU.setBindGroup`
- `Math.ceil`
- `Math.min`
- `passEncoderGPU.dispatchWorkgroups`

**Internal Comments:**
```
// pipeline (x2)
// bind groups
// If a single number is given, we calculate the dispatch size based on the workgroup size (x2)
// cache dispatch size to avoid recalculating it every time (x4)
// (x6)
```

<details><summary>Code</summary>

```typescript
compute( computeGroup, computeNode, bindings, pipeline, dispatchSizeOrCount = null ) {

		const computeNodeData = this.get( computeNode );
		const { passEncoderGPU } = this.get( computeGroup );

		// pipeline

		const pipelineGPU = this.get( pipeline ).pipeline;

		this.pipelineUtils.setPipeline( passEncoderGPU, pipelineGPU );

		// bind groups

		for ( let i = 0, l = bindings.length; i < l; i ++ ) {

			const bindGroup = bindings[ i ];
			const bindingsData = this.get( bindGroup );

			passEncoderGPU.setBindGroup( i, bindingsData.group );

		}

		let dispatchSize;

		if ( dispatchSizeOrCount === null ) {

			dispatchSizeOrCount = computeNode.count;

		}

		if ( typeof dispatchSizeOrCount === 'number' ) {

			// If a single number is given, we calculate the dispatch size based on the workgroup size

			const count = dispatchSizeOrCount;

			if ( computeNodeData.dispatchSize === undefined || computeNodeData.count !== count ) {

				// cache dispatch size to avoid recalculating it every time

				computeNodeData.dispatchSize = [ 0, 1, 1 ];
				computeNodeData.count = count;

				const workgroupSize = computeNode.workgroupSize;

				let size = workgroupSize[ 0 ];

				for ( let i = 1; i < workgroupSize.length; i ++ )
					size *= workgroupSize[ i ];

				const dispatchCount = Math.ceil( count / size );

				//

				const maxComputeWorkgroupsPerDimension = this.device.limits.maxComputeWorkgroupsPerDimension;

				dispatchSize = [ dispatchCount, 1, 1 ];

				if ( dispatchCount > maxComputeWorkgroupsPerDimension ) {

					dispatchSize[ 0 ] = Math.min( dispatchCount, maxComputeWorkgroupsPerDimension );
					dispatchSize[ 1 ] = Math.ceil( dispatchCount / maxComputeWorkgroupsPerDimension );

				}

				computeNodeData.dispatchSize = dispatchSize;

			}

			dispatchSize = computeNodeData.dispatchSize;

		} else {

			dispatchSize = dispatchSizeOrCount;

		}

		//

		passEncoderGPU.dispatchWorkgroups(
			dispatchSize[ 0 ],
			dispatchSize[ 1 ] || 1,
			dispatchSize[ 2 ] || 1
		);

	}
```
</details>

### `WebGPUBackend.finishCompute(computeGroup: Node | Node[]): void`

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

- `this.get`
- `groupData.passEncoderGPU.end`
- `this.device.queue.submit`
- `groupData.cmdEncoderGPU.finish`

<details><summary>Code</summary>

```typescript
finishCompute( computeGroup ) {

		const groupData = this.get( computeGroup );

		groupData.passEncoderGPU.end();

		this.device.queue.submit( [ groupData.cmdEncoderGPU.finish() ] );

	}
```
</details>

### `WebGPUBackend.waitForGPU(): Promise<any>`

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

- `this.device.queue.onSubmittedWorkDone`

<details><summary>Code</summary>

```typescript
async waitForGPU() {

		await this.device.queue.onSubmittedWorkDone();

	}
```
</details>

### `WebGPUBackend.draw(renderObject: RenderObject, info: Info): void`

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
- **`info`** `Info`

**Returns:** `void`

**Calls:**

- `renderObject.getBindings`
- `this.get`
- `renderObject.getIndex`
- `renderObject.getDrawParameters`
- `this.pipelineUtils.setPipeline`
- `passEncoderGPU.setBindGroup`
- `passEncoderGPU.setIndexBuffer`
- `renderObject.getVertexBuffers`
- `passEncoderGPU.setVertexBuffer`
- `passEncoderGPU.setStencilReference`
- `setPipelineAndBindings`
- `warnOnce (from ../../utils.js)`
- `passEncoderGPU.drawIndexed`
- `passEncoderGPU.draw`
- `info.update`
- `renderObject.getIndirect`
- `passEncoderGPU.drawIndexedIndirect`
- `passEncoderGPU.drawIndirect`
- `renderObject.getBindingGroup`
- `this.bindingUtils.createBindGroupIndex`
- `indexesGPU.push`
- `this.renderer.getPixelRatio`
- `object.layers.test`
- `pass.setViewport`
- `Math.floor`
- `pass.setBindGroup`
- `draw`
- `renderContextData.currentPass.endOcclusionQuery`
- `renderContextData.currentPass.beginOcclusionQuery`

**Internal Comments:**
```
// pipeline (x7)
// bind groups (x2)
// attributes
// index
// vertex buffers (x2)
// stencil
// Define draw function (x2)
// @deprecated, r174 (x3)
// Set camera index binding for this layer
// Regular single camera rendering
// Handle occlusion queries
```

<details><summary>Code</summary>

```typescript
draw( renderObject, info ) {

		const { object, material, context, pipeline } = renderObject;
		const bindings = renderObject.getBindings();
		const renderContextData = this.get( context );
		const pipelineGPU = this.get( pipeline ).pipeline;

		const index = renderObject.getIndex();
		const hasIndex = ( index !== null );


		const drawParams = renderObject.getDrawParameters();
		if ( drawParams === null ) return;

		// pipeline

		const setPipelineAndBindings = ( passEncoderGPU, currentSets ) => {

			// pipeline
			this.pipelineUtils.setPipeline( passEncoderGPU, pipelineGPU );
			currentSets.pipeline = pipelineGPU;

			// bind groups
			const currentBindingGroups = currentSets.bindingGroups;
			for ( let i = 0, l = bindings.length; i < l; i ++ ) {

				const bindGroup = bindings[ i ];
				const bindingsData = this.get( bindGroup );
				if ( currentBindingGroups[ bindGroup.index ] !== bindGroup.id ) {

					passEncoderGPU.setBindGroup( bindGroup.index, bindingsData.group );
					currentBindingGroups[ bindGroup.index ] = bindGroup.id;

				}

			}

			// attributes

			// index

			if ( hasIndex === true ) {

				if ( currentSets.index !== index ) {

					const buffer = this.get( index ).buffer;
					const indexFormat = ( index.array instanceof Uint16Array ) ? GPUIndexFormat.Uint16 : GPUIndexFormat.Uint32;

					passEncoderGPU.setIndexBuffer( buffer, indexFormat );

					currentSets.index = index;

				}

			}
			// vertex buffers

			const vertexBuffers = renderObject.getVertexBuffers();

			for ( let i = 0, l = vertexBuffers.length; i < l; i ++ ) {

				const vertexBuffer = vertexBuffers[ i ];

				if ( currentSets.attributes[ i ] !== vertexBuffer ) {

					const buffer = this.get( vertexBuffer ).buffer;
					passEncoderGPU.setVertexBuffer( i, buffer );

					currentSets.attributes[ i ] = vertexBuffer;

				}

			}
			// stencil

			if ( context.stencil === true && material.stencilWrite === true && renderContextData.currentStencilRef !== material.stencilRef ) {

				passEncoderGPU.setStencilReference( material.stencilRef );
				renderContextData.currentStencilRef = material.stencilRef;

			}


		};

		// Define draw function
		const draw = ( passEncoderGPU, currentSets ) => {

			setPipelineAndBindings( passEncoderGPU, currentSets );

			if ( object.isBatchedMesh === true ) {

				const starts = object._multiDrawStarts;
				const counts = object._multiDrawCounts;
				const drawCount = object._multiDrawCount;
				const drawInstances = object._multiDrawInstances;

				if ( drawInstances !== null ) {

					// @deprecated, r174
					warnOnce( 'THREE.WebGPUBackend: renderMultiDrawInstances has been deprecated and will be removed in r184. Append to renderMultiDraw arguments and use indirection.' );

				}

				for ( let i = 0; i < drawCount; i ++ ) {

					const count = drawInstances ? drawInstances[ i ] : 1;
					const firstInstance = count > 1 ? 0 : i;

					if ( hasIndex === true ) {

						passEncoderGPU.drawIndexed( counts[ i ], count, starts[ i ] / index.array.BYTES_PER_ELEMENT, 0, firstInstance );

					} else {

						passEncoderGPU.draw( counts[ i ], count, starts[ i ], firstInstance );

					}

					info.update( object, counts[ i ], count );

				}

			} else if ( hasIndex === true ) {

				const { vertexCount: indexCount, instanceCount, firstVertex: firstIndex } = drawParams;

				const indirect = renderObject.getIndirect();

				if ( indirect !== null ) {

					const buffer = this.get( indirect ).buffer;

					passEncoderGPU.drawIndexedIndirect( buffer, 0 );

				} else {

					passEncoderGPU.drawIndexed( indexCount, instanceCount, firstIndex, 0, 0 );

				}

				info.update( object, indexCount, instanceCount );

			} else {

				const { vertexCount, instanceCount, firstVertex } = drawParams;

				const indirect = renderObject.getIndirect();

				if ( indirect !== null ) {

					const buffer = this.get( indirect ).buffer;

					passEncoderGPU.drawIndirect( buffer, 0 );

				} else {

					passEncoderGPU.draw( vertexCount, instanceCount, firstVertex, 0 );

				}

				info.update( object, vertexCount, instanceCount );

			}

		};

		if ( renderObject.camera.isArrayCamera && renderObject.camera.cameras.length > 0 ) {

			const cameraData = this.get( renderObject.camera );
			const cameras = renderObject.camera.cameras;
			const cameraIndex = renderObject.getBindingGroup( 'cameraIndex' );

			if ( cameraData.indexesGPU === undefined || cameraData.indexesGPU.length !== cameras.length ) {

				const bindingsData = this.get( cameraIndex );
				const indexesGPU = [];

				const data = new Uint32Array( [ 0, 0, 0, 0 ] );

				for ( let i = 0, len = cameras.length; i < len; i ++ ) {

					data[ 0 ] = i;

					const bindGroupIndex = this.bindingUtils.createBindGroupIndex( data, bindingsData.layout );

					indexesGPU.push( bindGroupIndex );

				}

				cameraData.indexesGPU = indexesGPU; // TODO: Create a global library for this

			}

			const pixelRatio = this.renderer.getPixelRatio();

			for ( let i = 0, len = cameras.length; i < len; i ++ ) {

				const subCamera = cameras[ i ];

				if ( object.layers.test( subCamera.layers ) ) {

					const vp = subCamera.viewport;



					let pass = renderContextData.currentPass;
					let sets = renderContextData.currentSets;
					if ( renderContextData.bundleEncoders ) {

						const bundleEncoder = renderContextData.bundleEncoders[ i ];
						const bundleSets = renderContextData.bundleSets[ i ];
						pass = bundleEncoder;
						sets = bundleSets;

					}



					if ( vp ) {

						pass.setViewport(
							Math.floor( vp.x * pixelRatio ),
							Math.floor( vp.y * pixelRatio ),
							Math.floor( vp.width * pixelRatio ),
							Math.floor( vp.height * pixelRatio ),
							context.viewportValue.minDepth,
							context.viewportValue.maxDepth
						);

					}


					// Set camera index binding for this layer
					if ( cameraIndex && cameraData.indexesGPU ) {

						pass.setBindGroup( cameraIndex.index, cameraData.indexesGPU[ i ] );
						sets.bindingGroups[ cameraIndex.index ] = cameraIndex.id;

					}

					draw( pass, sets );


				}

			}

		} else {

			// Regular single camera rendering
			if ( renderContextData.currentPass ) {

				// Handle occlusion queries
				if ( renderContextData.occlusionQuerySet !== undefined ) {

					const lastObject = renderContextData.lastOcclusionObject;
					if ( lastObject !== object ) {

						if ( lastObject !== null && lastObject.occlusionTest === true ) {

							renderContextData.currentPass.endOcclusionQuery();
							renderContextData.occlusionQueryIndex ++;

						}

						if ( object.occlusionTest === true ) {

							renderContextData.currentPass.beginOcclusionQuery( renderContextData.occlusionQueryIndex );
							renderContextData.occlusionQueryObjects[ renderContextData.occlusionQueryIndex ] = object;

						}

						renderContextData.lastOcclusionObject = object;

					}

				}

				draw( renderContextData.currentPass, renderContextData.currentSets );

			}

		}

	}
```
</details>

### `WebGPUBackend.needsRenderUpdate(renderObject: RenderObject): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the render pipeline requires an update.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {boolean} Whether the render pipeline requires an update or not.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `boolean`

**Calls:**

- `this.get`
- `utils.getSampleCountRenderContext`
- `utils.getCurrentColorSpace`
- `utils.getCurrentColorFormat`
- `utils.getCurrentDepthStencilFormat`
- `utils.getPrimitiveTopology`

<details><summary>Code</summary>

```typescript
needsRenderUpdate( renderObject ) {

		const data = this.get( renderObject );

		const { object, material } = renderObject;

		const utils = this.utils;

		const sampleCount = utils.getSampleCountRenderContext( renderObject.context );
		const colorSpace = utils.getCurrentColorSpace( renderObject.context );
		const colorFormat = utils.getCurrentColorFormat( renderObject.context );
		const depthStencilFormat = utils.getCurrentDepthStencilFormat( renderObject.context );
		const primitiveTopology = utils.getPrimitiveTopology( object, material );

		let needsUpdate = false;

		if ( data.material !== material || data.materialVersion !== material.version ||
			data.transparent !== material.transparent || data.blending !== material.blending || data.premultipliedAlpha !== material.premultipliedAlpha ||
			data.blendSrc !== material.blendSrc || data.blendDst !== material.blendDst || data.blendEquation !== material.blendEquation ||
			data.blendSrcAlpha !== material.blendSrcAlpha || data.blendDstAlpha !== material.blendDstAlpha || data.blendEquationAlpha !== material.blendEquationAlpha ||
			data.colorWrite !== material.colorWrite || data.depthWrite !== material.depthWrite || data.depthTest !== material.depthTest || data.depthFunc !== material.depthFunc ||
			data.stencilWrite !== material.stencilWrite || data.stencilFunc !== material.stencilFunc ||
			data.stencilFail !== material.stencilFail || data.stencilZFail !== material.stencilZFail || data.stencilZPass !== material.stencilZPass ||
			data.stencilFuncMask !== material.stencilFuncMask || data.stencilWriteMask !== material.stencilWriteMask ||
			data.side !== material.side || data.alphaToCoverage !== material.alphaToCoverage ||
			data.sampleCount !== sampleCount || data.colorSpace !== colorSpace ||
			data.colorFormat !== colorFormat || data.depthStencilFormat !== depthStencilFormat ||
			data.primitiveTopology !== primitiveTopology ||
			data.clippingContextCacheKey !== renderObject.clippingContextCacheKey
		) {

			data.material = material; data.materialVersion = material.version;
			data.transparent = material.transparent; data.blending = material.blending; data.premultipliedAlpha = material.premultipliedAlpha;
			data.blendSrc = material.blendSrc; data.blendDst = material.blendDst; data.blendEquation = material.blendEquation;
			data.blendSrcAlpha = material.blendSrcAlpha; data.blendDstAlpha = material.blendDstAlpha; data.blendEquationAlpha = material.blendEquationAlpha;
			data.colorWrite = material.colorWrite;
			data.depthWrite = material.depthWrite; data.depthTest = material.depthTest; data.depthFunc = material.depthFunc;
			data.stencilWrite = material.stencilWrite; data.stencilFunc = material.stencilFunc;
			data.stencilFail = material.stencilFail; data.stencilZFail = material.stencilZFail; data.stencilZPass = material.stencilZPass;
			data.stencilFuncMask = material.stencilFuncMask; data.stencilWriteMask = material.stencilWriteMask;
			data.side = material.side; data.alphaToCoverage = material.alphaToCoverage;
			data.sampleCount = sampleCount;
			data.colorSpace = colorSpace;
			data.colorFormat = colorFormat;
			data.depthStencilFormat = depthStencilFormat;
			data.primitiveTopology = primitiveTopology;
			data.clippingContextCacheKey = renderObject.clippingContextCacheKey;

			needsUpdate = true;

		}

		return needsUpdate;

	}
```
</details>

### `WebGPUBackend.getRenderCacheKey(renderObject: RenderObject): string`

**JSDoc:**
```typescript
/**
	 * Returns a cache key that is used to identify render pipelines.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {string} The cache key.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `string`

**Calls:**

- `[
			material.transparent, material.blending, material.premultipliedAlpha,
			material.blendSrc, material.blendDst, material.blendEquation,
			material.blendSrcAlpha, material.blendDstAlpha, material.blendEquationAlpha,
			material.colorWrite,
			material.depthWrite, material.depthTest, material.depthFunc,
			material.stencilWrite, material.stencilFunc,
			material.stencilFail, material.stencilZFail, material.stencilZPass,
			material.stencilFuncMask, material.stencilWriteMask,
			material.side,
			utils.getSampleCountRenderContext( renderContext ),
			utils.getCurrentColorSpace( renderContext ), utils.getCurrentColorFormat( renderContext ), utils.getCurrentDepthStencilFormat( renderContext ),
			utils.getPrimitiveTopology( object, material ),
			renderObject.getGeometryCacheKey(),
			renderObject.clippingContextCacheKey
		].join`
- `utils.getSampleCountRenderContext`
- `utils.getCurrentColorSpace`
- `utils.getCurrentColorFormat`
- `utils.getCurrentDepthStencilFormat`
- `utils.getPrimitiveTopology`
- `renderObject.getGeometryCacheKey`

<details><summary>Code</summary>

```typescript
getRenderCacheKey( renderObject ) {

		const { object, material } = renderObject;

		const utils = this.utils;
		const renderContext = renderObject.context;

		return [
			material.transparent, material.blending, material.premultipliedAlpha,
			material.blendSrc, material.blendDst, material.blendEquation,
			material.blendSrcAlpha, material.blendDstAlpha, material.blendEquationAlpha,
			material.colorWrite,
			material.depthWrite, material.depthTest, material.depthFunc,
			material.stencilWrite, material.stencilFunc,
			material.stencilFail, material.stencilZFail, material.stencilZPass,
			material.stencilFuncMask, material.stencilWriteMask,
			material.side,
			utils.getSampleCountRenderContext( renderContext ),
			utils.getCurrentColorSpace( renderContext ), utils.getCurrentColorFormat( renderContext ), utils.getCurrentDepthStencilFormat( renderContext ),
			utils.getPrimitiveTopology( object, material ),
			renderObject.getGeometryCacheKey(),
			renderObject.clippingContextCacheKey
		].join();

	}
```
</details>

### `WebGPUBackend.createSampler(texture: Texture): void`

**JSDoc:**
```typescript
/**
	 * Creates a GPU sampler for the given texture.
	 *
	 * @param {Texture} texture - The texture to create the sampler for.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `void`

**Calls:**

- `this.textureUtils.createSampler`

<details><summary>Code</summary>

```typescript
createSampler( texture ) {

		this.textureUtils.createSampler( texture );

	}
```
</details>

### `WebGPUBackend.destroySampler(texture: Texture): void`

**JSDoc:**
```typescript
/**
	 * Destroys the GPU sampler for the given texture.
	 *
	 * @param {Texture} texture - The texture to destroy the sampler for.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `void`

**Calls:**

- `this.textureUtils.destroySampler`

<details><summary>Code</summary>

```typescript
destroySampler( texture ) {

		this.textureUtils.destroySampler( texture );

	}
```
</details>

### `WebGPUBackend.createDefaultTexture(texture: Texture): void`

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

### `WebGPUBackend.createTexture(texture: Texture, options: any): void`

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

### `WebGPUBackend.updateTexture(texture: Texture, options: any): void`

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

### `WebGPUBackend.generateMipmaps(texture: Texture): void`

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

### `WebGPUBackend.destroyTexture(texture: Texture): void`

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

### `WebGPUBackend.copyTextureToBuffer(texture: Texture, x: number, y: number, width: number, height: number, faceIndex: number): Promise<TypedArray>`

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

### `WebGPUBackend.initTimestampQuery(renderContext: RenderContext, descriptor: any): void`

**JSDoc:**
```typescript
/**
	 * Inits a time stamp query for the given render context.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @param {Object} descriptor - The query descriptor.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`
- **`descriptor`** `any`

**Returns:** `void`

**Calls:**

- `timestampQueryPool.allocateQueriesForContext`

**Internal Comments:**
```
// TODO: Variable maxQueries? (x5)
```

<details><summary>Code</summary>

```typescript
initTimestampQuery( renderContext, descriptor ) {

		if ( ! this.trackTimestamp ) return;

		const type = renderContext.isComputeNode ? 'compute' : 'render';

		if ( ! this.timestampQueryPool[ type ] ) {

			// TODO: Variable maxQueries?
			this.timestampQueryPool[ type ] = new WebGPUTimestampQueryPool( this.device, type, 2048 );

		}

		const timestampQueryPool = this.timestampQueryPool[ type ];

		const baseOffset = timestampQueryPool.allocateQueriesForContext( renderContext );

		descriptor.timestampWrites = {
			querySet: timestampQueryPool.querySet,
			beginningOfPassWriteIndex: baseOffset,
			endOfPassWriteIndex: baseOffset + 1,
		  };

	}
```
</details>

### `WebGPUBackend.createNodeBuilder(object: RenderObject, renderer: Renderer): WGSLNodeBuilder`

**JSDoc:**
```typescript
/**
	 * Returns a node builder for the given render object.
	 *
	 * @param {RenderObject} object - The render object.
	 * @param {Renderer} renderer - The renderer.
	 * @return {WGSLNodeBuilder} The node builder.
	 */
```

**Parameters:**

- **`object`** `RenderObject`
- **`renderer`** `Renderer`

**Returns:** `WGSLNodeBuilder`

<details><summary>Code</summary>

```typescript
createNodeBuilder( object, renderer ) {

		return new WGSLNodeBuilder( object, renderer );

	}
```
</details>

### `WebGPUBackend.createProgram(program: ProgrammableStage): void`

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

- `this.get`
- `this.device.createShaderModule`

<details><summary>Code</summary>

```typescript
createProgram( program ) {

		const programGPU = this.get( program );

		programGPU.module = {
			module: this.device.createShaderModule( { code: program.code, label: program.stage + ( program.name !== '' ? `_${ program.name }` : '' ) } ),
			entryPoint: 'main'
		};

	}
```
</details>

### `WebGPUBackend.destroyProgram(program: ProgrammableStage): void`

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

### `WebGPUBackend.createRenderPipeline(renderObject: RenderObject, promises: Promise<any>[]): void`

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

- `this.pipelineUtils.createRenderPipeline`

<details><summary>Code</summary>

```typescript
createRenderPipeline( renderObject, promises ) {

		this.pipelineUtils.createRenderPipeline( renderObject, promises );

	}
```
</details>

### `WebGPUBackend.createComputePipeline(computePipeline: ComputePipeline, bindings: BindGroup[]): void`

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

- `this.pipelineUtils.createComputePipeline`

<details><summary>Code</summary>

```typescript
createComputePipeline( computePipeline, bindings ) {

		this.pipelineUtils.createComputePipeline( computePipeline, bindings );

	}
```
</details>

### `WebGPUBackend.beginBundle(renderContext: RenderContext): void`

**JSDoc:**
```typescript
/**
	 * Prepares the state for encoding render bundles.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`

**Returns:** `void`

**Calls:**

- `this.get`
- `this.pipelineUtils.createBundleEncoder`

<details><summary>Code</summary>

```typescript
beginBundle( renderContext ) {

		const renderContextData = this.get( renderContext );

		renderContextData._currentPass = renderContextData.currentPass;
		renderContextData._currentSets = renderContextData.currentSets;

		renderContextData.currentSets = { attributes: {}, bindingGroups: [], pipeline: null, index: null };
		renderContextData.currentPass = this.pipelineUtils.createBundleEncoder( renderContext );

	}
```
</details>

### `WebGPUBackend.finishBundle(renderContext: RenderContext, bundle: RenderBundle): void`

**JSDoc:**
```typescript
/**
	 * After processing render bundles this method finalizes related work.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @param {RenderBundle} bundle - The render bundle.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`
- **`bundle`** `RenderBundle`

**Returns:** `void`

**Calls:**

- `this.get`
- `bundleEncoder.finish`

**Internal Comments:**
```
// restore render pass state (x4)
```

<details><summary>Code</summary>

```typescript
finishBundle( renderContext, bundle ) {

		const renderContextData = this.get( renderContext );

		const bundleEncoder = renderContextData.currentPass;
		const bundleGPU = bundleEncoder.finish();

		this.get( bundle ).bundleGPU = bundleGPU;

		// restore render pass state

		renderContextData.currentSets = renderContextData._currentSets;
		renderContextData.currentPass = renderContextData._currentPass;

	}
```
</details>

### `WebGPUBackend.addBundle(renderContext: RenderContext, bundle: RenderBundle): void`

**JSDoc:**
```typescript
/**
	 * Adds a render bundle to the render context data.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @param {RenderBundle} bundle - The render bundle to add.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`
- **`bundle`** `RenderBundle`

**Returns:** `void`

**Calls:**

- `this.get`
- `renderContextData.renderBundles.push`

<details><summary>Code</summary>

```typescript
addBundle( renderContext, bundle ) {

		const renderContextData = this.get( renderContext );

		renderContextData.renderBundles.push( this.get( bundle ).bundleGPU );

	}
```
</details>

### `WebGPUBackend.createBindings(bindGroup: BindGroup, bindings: BindGroup[], cacheIndex: number, version: number): void`

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
- **`cacheIndex`** `number`
- **`version`** `number`

**Returns:** `void`

**Calls:**

- `this.bindingUtils.createBindings`

<details><summary>Code</summary>

```typescript
createBindings( bindGroup, bindings, cacheIndex, version ) {

		this.bindingUtils.createBindings( bindGroup, bindings, cacheIndex, version );

	}
```
</details>

### `WebGPUBackend.updateBindings(bindGroup: BindGroup, bindings: BindGroup[], cacheIndex: number, version: number): void`

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
- **`bindings`** `BindGroup[]`
- **`cacheIndex`** `number`
- **`version`** `number`

**Returns:** `void`

**Calls:**

- `this.bindingUtils.createBindings`

<details><summary>Code</summary>

```typescript
updateBindings( bindGroup, bindings, cacheIndex, version ) {

		this.bindingUtils.createBindings( bindGroup, bindings, cacheIndex, version );

	}
```
</details>

### `WebGPUBackend.updateBinding(binding: Buffer<ArrayBufferLike>): void`

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

- `this.bindingUtils.updateBinding`

<details><summary>Code</summary>

```typescript
updateBinding( binding ) {

		this.bindingUtils.updateBinding( binding );

	}
```
</details>

### `WebGPUBackend.createIndexAttribute(attribute: BufferAttribute): void`

**JSDoc:**
```typescript
/**
	 * Creates the buffer of an indexed shader attribute.
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

		let usage = GPUBufferUsage.INDEX | GPUBufferUsage.COPY_SRC | GPUBufferUsage.COPY_DST;

		if ( attribute.isStorageBufferAttribute || attribute.isStorageInstancedBufferAttribute ) {

			usage |= GPUBufferUsage.STORAGE;

		}

		this.attributeUtils.createAttribute( attribute, usage );

	}
```
</details>

### `WebGPUBackend.createAttribute(attribute: BufferAttribute): void`

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

- `this.attributeUtils.createAttribute`

<details><summary>Code</summary>

```typescript
createAttribute( attribute ) {

		this.attributeUtils.createAttribute( attribute, GPUBufferUsage.VERTEX | GPUBufferUsage.COPY_SRC | GPUBufferUsage.COPY_DST );

	}
```
</details>

### `WebGPUBackend.createStorageAttribute(attribute: BufferAttribute): void`

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

- `this.attributeUtils.createAttribute`

<details><summary>Code</summary>

```typescript
createStorageAttribute( attribute ) {

		this.attributeUtils.createAttribute( attribute, GPUBufferUsage.STORAGE | GPUBufferUsage.VERTEX | GPUBufferUsage.COPY_SRC | GPUBufferUsage.COPY_DST );

	}
```
</details>

### `WebGPUBackend.createIndirectStorageAttribute(attribute: BufferAttribute): void`

**JSDoc:**
```typescript
/**
	 * Creates the GPU buffer of an indirect storage attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`

**Returns:** `void`

**Calls:**

- `this.attributeUtils.createAttribute`

<details><summary>Code</summary>

```typescript
createIndirectStorageAttribute( attribute ) {

		this.attributeUtils.createAttribute( attribute, GPUBufferUsage.STORAGE | GPUBufferUsage.INDIRECT | GPUBufferUsage.COPY_SRC | GPUBufferUsage.COPY_DST );

	}
```
</details>

### `WebGPUBackend.updateAttribute(attribute: BufferAttribute): void`

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

### `WebGPUBackend.destroyAttribute(attribute: BufferAttribute): void`

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

### `WebGPUBackend.updateSize(): void`

**JSDoc:**
```typescript
/**
	 * Triggers an update of the default render pass descriptor.
	 */
```

**Returns:** `void`

**Calls:**

- `this.textureUtils.getColorBuffer`

<details><summary>Code</summary>

```typescript
updateSize() {

		this.colorBuffer = this.textureUtils.getColorBuffer();
		this.defaultRenderPassdescriptor = null;

	}
```
</details>

### `WebGPUBackend.getMaxAnisotropy(): number`

**JSDoc:**
```typescript
/**
	 * Returns the maximum anisotropy texture filtering value.
	 *
	 * @return {number} The maximum anisotropy texture filtering value.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getMaxAnisotropy() {

		return 16;

	}
```
</details>

### `WebGPUBackend.hasFeature(name: string): boolean`

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

- `this.device.features.has`

<details><summary>Code</summary>

```typescript
hasFeature( name ) {

		return this.device.features.has( name );

	}
```
</details>

### `WebGPUBackend.copyTextureToTexture(srcTexture: Texture, dstTexture: Texture, srcRegion: any, dstPosition: any, srcLevel: number, dstLevel: number): void`

**JSDoc:**
```typescript
/**
	 * Copies data of the given source texture to the given destination texture.
	 *
	 * @param {Texture} srcTexture - The source texture.
	 * @param {Texture} dstTexture - The destination texture.
	 * @param {?(Box3|Box2)} [srcRegion=null] - The region of the source texture to copy.
	 * @param {?(Vector2|Vector3)} [dstPosition=null] - The destination position of the copy.
	 * @param {number} [srcLevel=0] - The mipmap level to copy.
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

- `this.device.createCommandEncoder`
- `this.get`
- `encoder.copyTextureToTexture`
- `this.device.queue.submit`
- `encoder.finish`
- `this.textureUtils.generateMipmaps`

**Internal Comments:**
```
// Assume it's a Box2 (x3)
```

<details><summary>Code</summary>

```typescript
copyTextureToTexture( srcTexture, dstTexture, srcRegion = null, dstPosition = null, srcLevel = 0, dstLevel = 0 ) {

		let dstX = 0;
		let dstY = 0;
		let dstZ = 0;

		let srcX = 0;
		let srcY = 0;
		let srcZ = 0;

		let srcWidth = srcTexture.image.width;
		let srcHeight = srcTexture.image.height;
		let srcDepth = 1;


		if ( srcRegion !== null ) {

			if ( srcRegion.isBox3 === true ) {

				srcX = srcRegion.min.x;
				srcY = srcRegion.min.y;
				srcZ = srcRegion.min.z;
				srcWidth = srcRegion.max.x - srcRegion.min.x;
				srcHeight = srcRegion.max.y - srcRegion.min.y;
				srcDepth = srcRegion.max.z - srcRegion.min.z;

			} else {

				// Assume it's a Box2
				srcX = srcRegion.min.x;
				srcY = srcRegion.min.y;
				srcWidth = srcRegion.max.x - srcRegion.min.x;
				srcHeight = srcRegion.max.y - srcRegion.min.y;
				srcDepth = 1;

			}

		}


		if ( dstPosition !== null ) {

			dstX = dstPosition.x;
			dstY = dstPosition.y;
			dstZ = dstPosition.z || 0;

		}

		const encoder = this.device.createCommandEncoder( { label: 'copyTextureToTexture_' + srcTexture.id + '_' + dstTexture.id } );

		const sourceGPU = this.get( srcTexture ).texture;
		const destinationGPU = this.get( dstTexture ).texture;

		encoder.copyTextureToTexture(
			{
				texture: sourceGPU,
				mipLevel: srcLevel,
				origin: { x: srcX, y: srcY, z: srcZ }
			},
			{
				texture: destinationGPU,
				mipLevel: dstLevel,
				origin: { x: dstX, y: dstY, z: dstZ }
			},
			[
				srcWidth,
				srcHeight,
				srcDepth
			]
		);

		this.device.queue.submit( [ encoder.finish() ] );

		if ( dstLevel === 0 && dstTexture.generateMipmaps ) {

			this.textureUtils.generateMipmaps( dstTexture );

		}

	}
```
</details>

### `WebGPUBackend.copyFramebufferToTexture(texture: Texture, renderContext: RenderContext, rectangle: Vector4): void`

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

- `this.get`
- `this.textureUtils.getDepthBuffer`
- `this.context.getCurrentTexture`
- `console.error`
- `renderContextData.currentPass.end`
- `this.device.createCommandEncoder`
- `encoder.copyTextureToTexture`
- `encoder.beginRenderPass`
- `this.updateViewport`
- `renderContextData.currentPass.setScissorRect`
- `this.device.queue.submit`
- `encoder.finish`
- `this.textureUtils.generateMipmaps`

<details><summary>Code</summary>

```typescript
copyFramebufferToTexture( texture, renderContext, rectangle ) {

		const renderContextData = this.get( renderContext );

		let sourceGPU = null;

		if ( renderContext.renderTarget ) {

			if ( texture.isDepthTexture ) {

				sourceGPU = this.get( renderContext.depthTexture ).texture;

			} else {

				sourceGPU = this.get( renderContext.textures[ 0 ] ).texture;

			}

		} else {

			if ( texture.isDepthTexture ) {

				sourceGPU = this.textureUtils.getDepthBuffer( renderContext.depth, renderContext.stencil );

			} else {

				sourceGPU = this.context.getCurrentTexture();

			}

		}

		const destinationGPU = this.get( texture ).texture;

		if ( sourceGPU.format !== destinationGPU.format ) {

			console.error( 'WebGPUBackend: copyFramebufferToTexture: Source and destination formats do not match.', sourceGPU.format, destinationGPU.format );

			return;

		}

		let encoder;

		if ( renderContextData.currentPass ) {

			renderContextData.currentPass.end();

			encoder = renderContextData.encoder;

		} else {

			encoder = this.device.createCommandEncoder( { label: 'copyFramebufferToTexture_' + texture.id } );

		}

		encoder.copyTextureToTexture(
			{
				texture: sourceGPU,
				origin: [ rectangle.x, rectangle.y, 0 ],
			},
			{
				texture: destinationGPU
			},
			[
				rectangle.z,
				rectangle.w
			]
		);

		if ( renderContextData.currentPass ) {

			const { descriptor } = renderContextData;

			for ( let i = 0; i < descriptor.colorAttachments.length; i ++ ) {

				descriptor.colorAttachments[ i ].loadOp = GPULoadOp.Load;

			}

			if ( renderContext.depth ) descriptor.depthStencilAttachment.depthLoadOp = GPULoadOp.Load;
			if ( renderContext.stencil ) descriptor.depthStencilAttachment.stencilLoadOp = GPULoadOp.Load;

			renderContextData.currentPass = encoder.beginRenderPass( descriptor );
			renderContextData.currentSets = { attributes: {}, bindingGroups: [], pipeline: null, index: null };

			if ( renderContext.viewport ) {

				this.updateViewport( renderContext );

			}

			if ( renderContext.scissor ) {

				const { x, y, width, height } = renderContext.scissorValue;

				renderContextData.currentPass.setScissorRect( x, y, width, height );

			}

		} else {

			this.device.queue.submit( [ encoder.finish() ] );

		}

		if ( texture.generateMipmaps ) {

			this.textureUtils.generateMipmaps( texture );

		}

	}
```
</details>

### `onDispose(): void`

**Returns:** `void`

**Calls:**

- `renderTarget.removeEventListener`
- `this.delete`

<details><summary>Code</summary>

```typescript
() => {

				renderTarget.removeEventListener( 'dispose', onDispose );
				this.delete( renderTarget );

			}
```
</details>

### `setPipelineAndBindings(passEncoderGPU: any, currentSets: any): void`

**Parameters:**

- **`passEncoderGPU`** `any`
- **`currentSets`** `any`

**Returns:** `void`

**Calls:**

- `this.pipelineUtils.setPipeline`
- `this.get`
- `passEncoderGPU.setBindGroup`
- `passEncoderGPU.setIndexBuffer`
- `renderObject.getVertexBuffers`
- `passEncoderGPU.setVertexBuffer`
- `passEncoderGPU.setStencilReference`

**Internal Comments:**
```
// pipeline (x5)
// bind groups (x2)
// attributes
// index
// vertex buffers (x2)
// stencil
```

<details><summary>Code</summary>

```typescript
( passEncoderGPU, currentSets ) => {

			// pipeline
			this.pipelineUtils.setPipeline( passEncoderGPU, pipelineGPU );
			currentSets.pipeline = pipelineGPU;

			// bind groups
			const currentBindingGroups = currentSets.bindingGroups;
			for ( let i = 0, l = bindings.length; i < l; i ++ ) {

				const bindGroup = bindings[ i ];
				const bindingsData = this.get( bindGroup );
				if ( currentBindingGroups[ bindGroup.index ] !== bindGroup.id ) {

					passEncoderGPU.setBindGroup( bindGroup.index, bindingsData.group );
					currentBindingGroups[ bindGroup.index ] = bindGroup.id;

				}

			}

			// attributes

			// index

			if ( hasIndex === true ) {

				if ( currentSets.index !== index ) {

					const buffer = this.get( index ).buffer;
					const indexFormat = ( index.array instanceof Uint16Array ) ? GPUIndexFormat.Uint16 : GPUIndexFormat.Uint32;

					passEncoderGPU.setIndexBuffer( buffer, indexFormat );

					currentSets.index = index;

				}

			}
			// vertex buffers

			const vertexBuffers = renderObject.getVertexBuffers();

			for ( let i = 0, l = vertexBuffers.length; i < l; i ++ ) {

				const vertexBuffer = vertexBuffers[ i ];

				if ( currentSets.attributes[ i ] !== vertexBuffer ) {

					const buffer = this.get( vertexBuffer ).buffer;
					passEncoderGPU.setVertexBuffer( i, buffer );

					currentSets.attributes[ i ] = vertexBuffer;

				}

			}
			// stencil

			if ( context.stencil === true && material.stencilWrite === true && renderContextData.currentStencilRef !== material.stencilRef ) {

				passEncoderGPU.setStencilReference( material.stencilRef );
				renderContextData.currentStencilRef = material.stencilRef;

			}


		}
```
</details>

### `draw(passEncoderGPU: any, currentSets: any): void`

**Parameters:**

- **`passEncoderGPU`** `any`
- **`currentSets`** `any`

**Returns:** `void`

**Calls:**

- `setPipelineAndBindings`
- `warnOnce (from ../../utils.js)`
- `passEncoderGPU.drawIndexed`
- `passEncoderGPU.draw`
- `info.update`
- `renderObject.getIndirect`
- `this.get`
- `passEncoderGPU.drawIndexedIndirect`
- `passEncoderGPU.drawIndirect`

**Internal Comments:**
```
// @deprecated, r174 (x3)
```

<details><summary>Code</summary>

```typescript
( passEncoderGPU, currentSets ) => {

			setPipelineAndBindings( passEncoderGPU, currentSets );

			if ( object.isBatchedMesh === true ) {

				const starts = object._multiDrawStarts;
				const counts = object._multiDrawCounts;
				const drawCount = object._multiDrawCount;
				const drawInstances = object._multiDrawInstances;

				if ( drawInstances !== null ) {

					// @deprecated, r174
					warnOnce( 'THREE.WebGPUBackend: renderMultiDrawInstances has been deprecated and will be removed in r184. Append to renderMultiDraw arguments and use indirection.' );

				}

				for ( let i = 0; i < drawCount; i ++ ) {

					const count = drawInstances ? drawInstances[ i ] : 1;
					const firstInstance = count > 1 ? 0 : i;

					if ( hasIndex === true ) {

						passEncoderGPU.drawIndexed( counts[ i ], count, starts[ i ] / index.array.BYTES_PER_ELEMENT, 0, firstInstance );

					} else {

						passEncoderGPU.draw( counts[ i ], count, starts[ i ], firstInstance );

					}

					info.update( object, counts[ i ], count );

				}

			} else if ( hasIndex === true ) {

				const { vertexCount: indexCount, instanceCount, firstVertex: firstIndex } = drawParams;

				const indirect = renderObject.getIndirect();

				if ( indirect !== null ) {

					const buffer = this.get( indirect ).buffer;

					passEncoderGPU.drawIndexedIndirect( buffer, 0 );

				} else {

					passEncoderGPU.drawIndexed( indexCount, instanceCount, firstIndex, 0, 0 );

				}

				info.update( object, indexCount, instanceCount );

			} else {

				const { vertexCount, instanceCount, firstVertex } = drawParams;

				const indirect = renderObject.getIndirect();

				if ( indirect !== null ) {

					const buffer = this.get( indirect ).buffer;

					passEncoderGPU.drawIndirect( buffer, 0 );

				} else {

					passEncoderGPU.draw( vertexCount, instanceCount, firstVertex, 0 );

				}

				info.update( object, vertexCount, instanceCount );

			}

		}
```
</details>


---

## Classes

### `WebGPUBackend`

<details><summary>Class Code</summary>

```ts
class WebGPUBackend extends Backend {

	/**
	 * WebGPUBackend options.
	 *
	 * @typedef {Object} WebGPUBackend~Options
	 * @property {boolean} [logarithmicDepthBuffer=false] - Whether logarithmic depth buffer is enabled or not.
	 * @property {boolean} [alpha=true] - Whether the default framebuffer (which represents the final contents of the canvas) should be transparent or opaque.
	 * @property {boolean} [compatibilityMode=false] - Whether the backend should be in compatibility mode or not.
	 * @property {boolean} [depth=true] - Whether the default framebuffer should have a depth buffer or not.
	 * @property {boolean} [stencil=false] - Whether the default framebuffer should have a stencil buffer or not.
	 * @property {boolean} [antialias=false] - Whether MSAA as the default anti-aliasing should be enabled or not.
	 * @property {number} [samples=0] - When `antialias` is `true`, `4` samples are used by default. Set this parameter to any other integer value than 0 to overwrite the default.
	 * @property {boolean} [forceWebGL=false] - If set to `true`, the renderer uses a WebGL 2 backend no matter if WebGPU is supported or not.
	 * @property {boolean} [trackTimestamp=false] - Whether to track timestamps with a Timestamp Query API or not.
	 * @property {string} [powerPreference=undefined] - The power preference.
	 * @property {Object} [requiredLimits=undefined] - Specifies the limits that are required by the device request. The request will fail if the adapter cannot provide these limits.
	 * @property {GPUDevice} [device=undefined] - If there is an existing GPU device on app level, it can be passed to the renderer as a parameter.
	 * @property {number} [outputType=undefined] - Texture type for output to canvas. By default, device's preferred format is used; other formats may incur overhead.
	 */

	/**
	 * Constructs a new WebGPU backend.
	 *
	 * @param {WebGPUBackend~Options} [parameters] - The configuration parameter.
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
		this.isWebGPUBackend = true;

		// some parameters require default values other than "undefined"
		this.parameters.alpha = ( parameters.alpha === undefined ) ? true : parameters.alpha;
		this.parameters.compatibilityMode = ( parameters.compatibilityMode === undefined ) ? false : parameters.compatibilityMode;

		this.parameters.requiredLimits = ( parameters.requiredLimits === undefined ) ? {} : parameters.requiredLimits;

		/**
		 * Indicates whether the backend is in compatibility mode or not.
		 * @type {boolean}
		 * @default false
		 */
		this.compatibilityMode = this.parameters.compatibilityMode;

		/**
		 * A reference to the device.
		 *
		 * @type {?GPUDevice}
		 * @default null
		 */
		this.device = null;

		/**
		 * A reference to the context.
		 *
		 * @type {?GPUCanvasContext}
		 * @default null
		 */
		this.context = null;

		/**
		 * A reference to the color attachment of the default framebuffer.
		 *
		 * @type {?GPUTexture}
		 * @default null
		 */
		this.colorBuffer = null;

		/**
		 * A reference to the default render pass descriptor.
		 *
		 * @type {?Object}
		 * @default null
		 */
		this.defaultRenderPassdescriptor = null;

		/**
		 * A reference to a backend module holding common utility functions.
		 *
		 * @type {WebGPUUtils}
		 */
		this.utils = new WebGPUUtils( this );

		/**
		 * A reference to a backend module holding shader attribute-related
		 * utility functions.
		 *
		 * @type {WebGPUAttributeUtils}
		 */
		this.attributeUtils = new WebGPUAttributeUtils( this );

		/**
		 * A reference to a backend module holding shader binding-related
		 * utility functions.
		 *
		 * @type {WebGPUBindingUtils}
		 */
		this.bindingUtils = new WebGPUBindingUtils( this );

		/**
		 * A reference to a backend module holding shader pipeline-related
		 * utility functions.
		 *
		 * @type {WebGPUPipelineUtils}
		 */
		this.pipelineUtils = new WebGPUPipelineUtils( this );

		/**
		 * A reference to a backend module holding shader texture-related
		 * utility functions.
		 *
		 * @type {WebGPUTextureUtils}
		 */
		this.textureUtils = new WebGPUTextureUtils( this );

		/**
		 * A map that manages the resolve buffers for occlusion queries.
		 *
		 * @type {Map<number,GPUBuffer>}
		 */
		this.occludedResolveCache = new Map();

	}

	/**
	 * Initializes the backend so it is ready for usage.
	 *
	 * @async
	 * @param {Renderer} renderer - The renderer.
	 * @return {Promise} A Promise that resolves when the backend has been initialized.
	 */
	async init( renderer ) {

		await super.init( renderer );

		//

		const parameters = this.parameters;

		// create the device if it is not passed with parameters

		let device;

		if ( parameters.device === undefined ) {

			const adapterOptions = {
				powerPreference: parameters.powerPreference,
				featureLevel: parameters.compatibilityMode ? 'compatibility' : undefined
			};

			const adapter = ( typeof navigator !== 'undefined' ) ? await navigator.gpu.requestAdapter( adapterOptions ) : null;

			if ( adapter === null ) {

				throw new Error( 'WebGPUBackend: Unable to create WebGPU adapter.' );

			}

			// feature support

			const features = Object.values( GPUFeatureName );

			const supportedFeatures = [];

			for ( const name of features ) {

				if ( adapter.features.has( name ) ) {

					supportedFeatures.push( name );

				}

			}

			const deviceDescriptor = {
				requiredFeatures: supportedFeatures,
				requiredLimits: parameters.requiredLimits
			};

			device = await adapter.requestDevice( deviceDescriptor );

		} else {

			device = parameters.device;

		}

		device.lost.then( ( info ) => {

			const deviceLossInfo = {
				api: 'WebGPU',
				message: info.message || 'Unknown reason',
				reason: info.reason || null,
				originalEvent: info
			};

			renderer.onDeviceLost( deviceLossInfo );

		} );

		const context = ( parameters.context !== undefined ) ? parameters.context : renderer.domElement.getContext( 'webgpu' );

		this.device = device;
		this.context = context;

		const alphaMode = parameters.alpha ? 'premultiplied' : 'opaque';

		this.trackTimestamp = this.trackTimestamp && this.hasFeature( GPUFeatureName.TimestampQuery );

		this.context.configure( {
			device: this.device,
			format: this.utils.getPreferredCanvasFormat(),
			usage: GPUTextureUsage.RENDER_ATTACHMENT | GPUTextureUsage.COPY_SRC,
			alphaMode: alphaMode
		} );

		this.updateSize();

	}

	/**
	 * The coordinate system of the backend.
	 *
	 * @type {number}
	 * @readonly
	 */
	get coordinateSystem() {

		return WebGPUCoordinateSystem;

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
	 * Returns the backend's rendering context.
	 *
	 * @return {GPUCanvasContext} The rendering context.
	 */
	getContext() {

		return this.context;

	}

	/**
	 * Returns the default render pass descriptor.
	 *
	 * In WebGPU, the default framebuffer must be configured
	 * like custom framebuffers so the backend needs a render
	 * pass descriptor even when rendering directly to screen.
	 *
	 * @private
	 * @return {Object} The render pass descriptor.
	 */
	_getDefaultRenderPassDescriptor() {

		let descriptor = this.defaultRenderPassdescriptor;

		if ( descriptor === null ) {

			const renderer = this.renderer;

			descriptor = {
				colorAttachments: [ {
					view: null
				} ],
			};

			if ( this.renderer.depth === true || this.renderer.stencil === true ) {

				descriptor.depthStencilAttachment = {
					view: this.textureUtils.getDepthBuffer( renderer.depth, renderer.stencil ).createView()
				};

			}

			const colorAttachment = descriptor.colorAttachments[ 0 ];

			if ( this.renderer.samples > 0 ) {

				colorAttachment.view = this.colorBuffer.createView();

			} else {

				colorAttachment.resolveTarget = undefined;

			}

			this.defaultRenderPassdescriptor = descriptor;

		}

		const colorAttachment = descriptor.colorAttachments[ 0 ];

		if ( this.renderer.samples > 0 ) {

			colorAttachment.resolveTarget = this.context.getCurrentTexture().createView();

		} else {

			colorAttachment.view = this.context.getCurrentTexture().createView();

		}

		return descriptor;

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

		return renderContext.depthTexture && renderContext.depthTexture.image.depth > 1 && renderContext.camera.isArrayCamera;

	}

	/**
	 * Returns the render pass descriptor for the given render context.
	 *
	 * @private
	 * @param {RenderContext} renderContext - The render context.
	 * @param {Object} colorAttachmentsConfig - Configuration object for the color attachments.
	 * @return {Object} The render pass descriptor.
	 */
	_getRenderPassDescriptor( renderContext, colorAttachmentsConfig = {} ) {

		const renderTarget = renderContext.renderTarget;
		const renderTargetData = this.get( renderTarget );

		let descriptors = renderTargetData.descriptors;

		if ( descriptors === undefined ||
			renderTargetData.width !== renderTarget.width ||
			renderTargetData.height !== renderTarget.height ||
			renderTargetData.dimensions !== renderTarget.dimensions ||
			renderTargetData.activeMipmapLevel !== renderContext.activeMipmapLevel ||
			renderTargetData.activeCubeFace !== renderContext.activeCubeFace ||
			renderTargetData.samples !== renderTarget.samples
		) {

			descriptors = {};

			renderTargetData.descriptors = descriptors;

			// dispose

			const onDispose = () => {

				renderTarget.removeEventListener( 'dispose', onDispose );
				this.delete( renderTarget );

			};

			if ( renderTarget.hasEventListener( 'dispose', onDispose ) === false ) {

				renderTarget.addEventListener( 'dispose', onDispose );

			}

		}

		const cacheKey = renderContext.getCacheKey();
		let descriptorBase = descriptors[ cacheKey ];

		if ( descriptorBase === undefined ) {

			const textures = renderContext.textures;
			const textureViews = [];

			let sliceIndex;

			const isRenderCameraDepthArray = this._isRenderCameraDepthArray( renderContext );

			for ( let i = 0; i < textures.length; i ++ ) {

				const textureData = this.get( textures[ i ] );

				const viewDescriptor = {
					label: `colorAttachment_${ i }`,
					baseMipLevel: renderContext.activeMipmapLevel,
					mipLevelCount: 1,
					baseArrayLayer: renderContext.activeCubeFace,
					arrayLayerCount: 1,
					dimension: GPUTextureViewDimension.TwoD
				};

				if ( renderTarget.isRenderTarget3D ) {

					sliceIndex = renderContext.activeCubeFace;

					viewDescriptor.baseArrayLayer = 0;
					viewDescriptor.dimension = GPUTextureViewDimension.ThreeD;
					viewDescriptor.depthOrArrayLayers = textures[ i ].image.depth;

				} else if ( renderTarget.isRenderTarget && textures[ i ].image.depth > 1 ) {

					if ( isRenderCameraDepthArray === true ) {

						const cameras = renderContext.camera.cameras;
						for ( let layer = 0; layer < cameras.length; layer ++ ) {

							const layerViewDescriptor = {
								...viewDescriptor,
								baseArrayLayer: layer,
								arrayLayerCount: 1,
								dimension: GPUTextureViewDimension.TwoD
							};
							const textureView = textureData.texture.createView( layerViewDescriptor );
							textureViews.push( {
								view: textureView,
								resolveTarget: undefined,
								depthSlice: undefined
							} );

						}

					} else {

						viewDescriptor.dimension = GPUTextureViewDimension.TwoDArray;
						viewDescriptor.depthOrArrayLayers = textures[ i ].image.depth;

					}

				}

				if ( isRenderCameraDepthArray !== true ) {

					const textureView = textureData.texture.createView( viewDescriptor );

					let view, resolveTarget;

					if ( textureData.msaaTexture !== undefined ) {

						view = textureData.msaaTexture.createView();
						resolveTarget = textureView;

					} else {

						view = textureView;
						resolveTarget = undefined;

					}

					textureViews.push( {
						view,
						resolveTarget,
						depthSlice: sliceIndex
					} );

				}

			}

			descriptorBase = { textureViews };

			if ( renderContext.depth ) {

				const depthTextureData = this.get( renderContext.depthTexture );
				const options = {};
				if ( renderContext.depthTexture.isArrayTexture ) {

					options.dimension = GPUTextureViewDimension.TwoD;
					options.arrayLayerCount = 1;
					options.baseArrayLayer = renderContext.activeCubeFace;

				}

				descriptorBase.depthStencilView = depthTextureData.texture.createView( options );

			}

			descriptors[ cacheKey ] = descriptorBase;

			renderTargetData.width = renderTarget.width;
			renderTargetData.height = renderTarget.height;
			renderTargetData.samples = renderTarget.samples;
			renderTargetData.activeMipmapLevel = renderContext.activeMipmapLevel;
			renderTargetData.activeCubeFace = renderContext.activeCubeFace;
			renderTargetData.dimensions = renderTarget.dimensions;

		}

		const descriptor = {
			colorAttachments: []
		};

		// Apply dynamic properties to cached views
		for ( let i = 0; i < descriptorBase.textureViews.length; i ++ ) {

			const viewInfo = descriptorBase.textureViews[ i ];

			let clearValue = { r: 0, g: 0, b: 0, a: 1 };
			if ( i === 0 && colorAttachmentsConfig.clearValue ) {

				clearValue = colorAttachmentsConfig.clearValue;

			}

			descriptor.colorAttachments.push( {
				view: viewInfo.view,
				depthSlice: viewInfo.depthSlice,
				resolveTarget: viewInfo.resolveTarget,
				loadOp: colorAttachmentsConfig.loadOp || GPULoadOp.Load,
				storeOp: colorAttachmentsConfig.storeOp || GPUStoreOp.Store,
				clearValue: clearValue
			} );

		}

		if ( descriptorBase.depthStencilView ) {

			descriptor.depthStencilAttachment = {
				view: descriptorBase.depthStencilView
			};

		}

		return descriptor;

	}

	/**
	 * This method is executed at the beginning of a render call and prepares
	 * the WebGPU state for upcoming render calls
	 *
	 * @param {RenderContext} renderContext - The render context.
	 */
	beginRender( renderContext ) {

		const renderContextData = this.get( renderContext );

		const device = this.device;
		const occlusionQueryCount = renderContext.occlusionQueryCount;

		let occlusionQuerySet;

		if ( occlusionQueryCount > 0 ) {

			if ( renderContextData.currentOcclusionQuerySet ) renderContextData.currentOcclusionQuerySet.destroy();
			if ( renderContextData.currentOcclusionQueryBuffer ) renderContextData.currentOcclusionQueryBuffer.destroy();

			// Get a reference to the array of objects with queries. The renderContextData property
			// can be changed by another render pass before the buffer.mapAsyc() completes.
			renderContextData.currentOcclusionQuerySet = renderContextData.occlusionQuerySet;
			renderContextData.currentOcclusionQueryBuffer = renderContextData.occlusionQueryBuffer;
			renderContextData.currentOcclusionQueryObjects = renderContextData.occlusionQueryObjects;

			//

			occlusionQuerySet = device.createQuerySet( { type: 'occlusion', count: occlusionQueryCount, label: `occlusionQuerySet_${ renderContext.id }` } );

			renderContextData.occlusionQuerySet = occlusionQuerySet;
			renderContextData.occlusionQueryIndex = 0;
			renderContextData.occlusionQueryObjects = new Array( occlusionQueryCount );

			renderContextData.lastOcclusionObject = null;

		}

		let descriptor;

		if ( renderContext.textures === null ) {

			descriptor = this._getDefaultRenderPassDescriptor();

		} else {

			descriptor = this._getRenderPassDescriptor( renderContext, { loadOp: GPULoadOp.Load } );

		}

		this.initTimestampQuery( renderContext, descriptor );

		descriptor.occlusionQuerySet = occlusionQuerySet;

		const depthStencilAttachment = descriptor.depthStencilAttachment;

		if ( renderContext.textures !== null ) {

			const colorAttachments = descriptor.colorAttachments;

			for ( let i = 0; i < colorAttachments.length; i ++ ) {

				const colorAttachment = colorAttachments[ i ];

				if ( renderContext.clearColor ) {

					colorAttachment.clearValue = i === 0 ? renderContext.clearColorValue : { r: 0, g: 0, b: 0, a: 1 };
					colorAttachment.loadOp = GPULoadOp.Clear;

				} else {

					colorAttachment.loadOp = GPULoadOp.Load;

				}

				colorAttachment.storeOp = GPUStoreOp.Store;

			}

		} else {

			const colorAttachment = descriptor.colorAttachments[ 0 ];

			if ( renderContext.clearColor ) {

				colorAttachment.clearValue = renderContext.clearColorValue;
				colorAttachment.loadOp = GPULoadOp.Clear;

			} else {

				colorAttachment.loadOp = GPULoadOp.Load;

			}

		  	colorAttachment.storeOp = GPUStoreOp.Store;

		}

		//

		if ( renderContext.depth ) {

			if ( renderContext.clearDepth ) {

				depthStencilAttachment.depthClearValue = renderContext.clearDepthValue;
				depthStencilAttachment.depthLoadOp = GPULoadOp.Clear;

			} else {

				depthStencilAttachment.depthLoadOp = GPULoadOp.Load;

			}

		  depthStencilAttachment.depthStoreOp = GPUStoreOp.Store;

		}

		if ( renderContext.stencil ) {

		  if ( renderContext.clearStencil ) {

				depthStencilAttachment.stencilClearValue = renderContext.clearStencilValue;
				depthStencilAttachment.stencilLoadOp = GPULoadOp.Clear;

			} else {

				depthStencilAttachment.stencilLoadOp = GPULoadOp.Load;

			}

		  depthStencilAttachment.stencilStoreOp = GPUStoreOp.Store;

		}

		//

		const encoder = device.createCommandEncoder( { label: 'renderContext_' + renderContext.id } );

		// shadow arrays - prepare bundle encoders for each camera in an array camera

		if ( this._isRenderCameraDepthArray( renderContext ) === true ) {

			const cameras = renderContext.camera.cameras;

			if ( ! renderContextData.layerDescriptors || renderContextData.layerDescriptors.length !== cameras.length ) {

				this._createDepthLayerDescriptors( renderContext, renderContextData, descriptor, cameras );

			} else {

				this._updateDepthLayerDescriptors( renderContext, renderContextData, cameras );

			}

			// Create bundle encoders for each layer
			renderContextData.bundleEncoders = [];
			renderContextData.bundleSets = [];

			// Create separate bundle encoders for each camera in the array
			for ( let i = 0; i < cameras.length; i ++ ) {

				const bundleEncoder = this.pipelineUtils.createBundleEncoder(
					renderContext,
					'renderBundleArrayCamera_' + i
				);

				// Initialize state tracking for this bundle
				const bundleSets = {
					attributes: {},
					bindingGroups: [],
					pipeline: null,
					index: null
				};

				renderContextData.bundleEncoders.push( bundleEncoder );
				renderContextData.bundleSets.push( bundleSets );

			}

			// We'll complete the bundles in finishRender
			renderContextData.currentPass = null;

		} else {

			const currentPass = encoder.beginRenderPass( descriptor );
			renderContextData.currentPass = currentPass;

			if ( renderContext.viewport ) {

				this.updateViewport( renderContext );

			}

			if ( renderContext.scissor ) {

				const { x, y, width, height } = renderContext.scissorValue;
				currentPass.setScissorRect( x, y, width, height );

			}

		}

		//

		renderContextData.descriptor = descriptor;
		renderContextData.encoder = encoder;
		renderContextData.currentSets = { attributes: {}, bindingGroups: [], pipeline: null, index: null };
		renderContextData.renderBundles = [];

	}

	/**
	 * This method creates layer descriptors for each camera in an array camera
	 * to prepare for rendering to a depth array texture.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @param {Object} renderContextData - The render context data.
	 * @param {Object} descriptor  - The render pass descriptor.
	 * @param {ArrayCamera} cameras - The array camera.
	 *
	 * @private
	 */
	_createDepthLayerDescriptors( renderContext, renderContextData, descriptor, cameras ) {

		const depthStencilAttachment = descriptor.depthStencilAttachment;
		renderContextData.layerDescriptors = [];

		const depthTextureData = this.get( renderContext.depthTexture );
		if ( ! depthTextureData.viewCache ) {

			depthTextureData.viewCache = [];

		}

		for ( let i = 0; i < cameras.length; i ++ ) {

			const layerDescriptor = {
				...descriptor,
				colorAttachments: [ {
					...descriptor.colorAttachments[ 0 ],
					view: descriptor.colorAttachments[ i ].view
				} ]
			};

			if ( descriptor.depthStencilAttachment ) {

				const layerIndex = i;

				if ( ! depthTextureData.viewCache[ layerIndex ] ) {

					depthTextureData.viewCache[ layerIndex ] = depthTextureData.texture.createView( {
						dimension: GPUTextureViewDimension.TwoD,
						baseArrayLayer: i,
						arrayLayerCount: 1
					} );

				}

				layerDescriptor.depthStencilAttachment = {
					view: depthTextureData.viewCache[ layerIndex ],
					depthLoadOp: depthStencilAttachment.depthLoadOp || GPULoadOp.Clear,
					depthStoreOp: depthStencilAttachment.depthStoreOp || GPUStoreOp.Store,
					depthClearValue: depthStencilAttachment.depthClearValue || 1.0
				};

				if ( renderContext.stencil ) {

					layerDescriptor.depthStencilAttachment.stencilLoadOp = depthStencilAttachment.stencilLoadOp;
					layerDescriptor.depthStencilAttachment.stencilStoreOp = depthStencilAttachment.stencilStoreOp;
					layerDescriptor.depthStencilAttachment.stencilClearValue = depthStencilAttachment.stencilClearValue;

				}

			} else {

				layerDescriptor.depthStencilAttachment = { ...depthStencilAttachment };

			}

			renderContextData.layerDescriptors.push( layerDescriptor );

		}

	}

	/**
	 * This method updates the layer descriptors for each camera in an array camera
	 * to prepare for rendering to a depth array texture.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @param {Object} renderContextData - The render context data.
	 * @param {ArrayCamera} cameras - The array camera.
	 *
	 */
	_updateDepthLayerDescriptors( renderContext, renderContextData, cameras ) {

		for ( let i = 0; i < cameras.length; i ++ ) {

			const layerDescriptor = renderContextData.layerDescriptors[ i ];

			if ( layerDescriptor.depthStencilAttachment ) {

				const depthAttachment = layerDescriptor.depthStencilAttachment;

				if ( renderContext.depth ) {

					if ( renderContext.clearDepth ) {

						depthAttachment.depthClearValue = renderContext.clearDepthValue;
						depthAttachment.depthLoadOp = GPULoadOp.Clear;

					} else {

						depthAttachment.depthLoadOp = GPULoadOp.Load;

					}

				}

				if ( renderContext.stencil ) {

					if ( renderContext.clearStencil ) {

						depthAttachment.stencilClearValue = renderContext.clearStencilValue;
						depthAttachment.stencilLoadOp = GPULoadOp.Clear;

					} else {

						depthAttachment.stencilLoadOp = GPULoadOp.Load;

					}

				}

			}

		}

	}

	/**
	 * This method is executed at the end of a render call and finalizes work
	 * after draw calls.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 */
	finishRender( renderContext ) {

		const renderContextData = this.get( renderContext );
		const occlusionQueryCount = renderContext.occlusionQueryCount;

		if ( renderContextData.renderBundles.length > 0 ) {

			renderContextData.currentPass.executeBundles( renderContextData.renderBundles );

		}

		if ( occlusionQueryCount > renderContextData.occlusionQueryIndex ) {

			renderContextData.currentPass.endOcclusionQuery();

		}

		// shadow arrays - Execute bundles for each layer

		const encoder = renderContextData.encoder;

		if ( this._isRenderCameraDepthArray( renderContext ) === true ) {

		  const bundles = [];

		  for ( let i = 0; i < renderContextData.bundleEncoders.length; i ++ ) {

				const bundleEncoder = renderContextData.bundleEncoders[ i ];
				bundles.push( bundleEncoder.finish() );

			}

		  for ( let i = 0; i < renderContextData.layerDescriptors.length; i ++ ) {

				if ( i < bundles.length ) {

					const layerDescriptor = renderContextData.layerDescriptors[ i ];
					const renderPass = encoder.beginRenderPass( layerDescriptor );

					if ( renderContext.viewport ) {

						const { x, y, width, height, minDepth, maxDepth } = renderContext.viewportValue;
						renderPass.setViewport( x, y, width, height, minDepth, maxDepth );

					}

					if ( renderContext.scissor ) {

						const { x, y, width, height } = renderContext.scissorValue;
						renderPass.setScissorRect( x, y, width, height );

					}

					renderPass.executeBundles( [ bundles[ i ] ] );

					renderPass.end();

				}

			}

		} else if ( renderContextData.currentPass ) {

		  renderContextData.currentPass.end();

		}

		if ( occlusionQueryCount > 0 ) {

			const bufferSize = occlusionQueryCount * 8; // 8 byte entries for query results

			//

			let queryResolveBuffer = this.occludedResolveCache.get( bufferSize );

			if ( queryResolveBuffer === undefined ) {

				queryResolveBuffer = this.device.createBuffer(
					{
						size: bufferSize,
						usage: GPUBufferUsage.QUERY_RESOLVE | GPUBufferUsage.COPY_SRC
					}
				);

				this.occludedResolveCache.set( bufferSize, queryResolveBuffer );

			}

			//

			const readBuffer = this.device.createBuffer(
				{
					size: bufferSize,
					usage: GPUBufferUsage.COPY_DST | GPUBufferUsage.MAP_READ
				}
			);

			// two buffers required here - WebGPU doesn't allow usage of QUERY_RESOLVE & MAP_READ to be combined
			renderContextData.encoder.resolveQuerySet( renderContextData.occlusionQuerySet, 0, occlusionQueryCount, queryResolveBuffer, 0 );
			renderContextData.encoder.copyBufferToBuffer( queryResolveBuffer, 0, readBuffer, 0, bufferSize );

			renderContextData.occlusionQueryBuffer = readBuffer;

			//

			this.resolveOccludedAsync( renderContext );

		}

		this.device.queue.submit( [ renderContextData.encoder.finish() ] );


		//

		if ( renderContext.textures !== null ) {

			const textures = renderContext.textures;

			for ( let i = 0; i < textures.length; i ++ ) {

				const texture = textures[ i ];

				if ( texture.generateMipmaps === true ) {

					this.textureUtils.generateMipmaps( texture );

				}

			}

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
	 * This method processes the result of occlusion queries and writes it
	 * into render context data.
	 *
	 * @async
	 * @param {RenderContext} renderContext - The render context.
	 * @return {Promise} A Promise that resolves when the occlusion query results have been processed.
	 */
	async resolveOccludedAsync( renderContext ) {

		const renderContextData = this.get( renderContext );

		// handle occlusion query results

		const { currentOcclusionQueryBuffer, currentOcclusionQueryObjects } = renderContextData;

		if ( currentOcclusionQueryBuffer && currentOcclusionQueryObjects ) {

			const occluded = new WeakSet();

			renderContextData.currentOcclusionQueryObjects = null;
			renderContextData.currentOcclusionQueryBuffer = null;

			await currentOcclusionQueryBuffer.mapAsync( GPUMapMode.READ );

			const buffer = currentOcclusionQueryBuffer.getMappedRange();
			const results = new BigUint64Array( buffer );

			for ( let i = 0; i < currentOcclusionQueryObjects.length; i ++ ) {

				if ( results[ i ] === BigInt( 0 ) ) {

					occluded.add( currentOcclusionQueryObjects[ i ] );

				}

			}

			currentOcclusionQueryBuffer.destroy();

			renderContextData.occluded = occluded;

		}

	}

	/**
	 * Updates the viewport with the values from the given render context.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 */
	updateViewport( renderContext ) {

		const { currentPass } = this.get( renderContext );
		const { x, y, width, height, minDepth, maxDepth } = renderContext.viewportValue;

		currentPass.setViewport( x, y, width, height, minDepth, maxDepth );

	}

	/**
	 * Returns the clear color and alpha into a single
	 * color object.
	 *
	 * @return {Color4} The clear color.
	 */
	getClearColor() {

		const clearColor = super.getClearColor();

		// only premultiply alpha when alphaMode is "premultiplied"

		if ( this.renderer.alpha === true ) {

			clearColor.r *= clearColor.a;
			clearColor.g *= clearColor.a;
			clearColor.b *= clearColor.a;

		}

		return clearColor;

	}

	/**
	 * Performs a clear operation.
	 *
	 * @param {boolean} color - Whether the color buffer should be cleared or not.
	 * @param {boolean} depth - Whether the depth buffer should be cleared or not.
	 * @param {boolean} stencil - Whether the stencil buffer should be cleared or not.
	 * @param {?RenderContext} [renderTargetContext=null] - The render context of the current set render target.
	 */
	clear( color, depth, stencil, renderTargetContext = null ) {

		const device = this.device;
		const renderer = this.renderer;

		let colorAttachments = [];
		let depthStencilAttachment;
		let clearValue;

		let supportsDepth;
		let supportsStencil;

		if ( color ) {

			const clearColor = this.getClearColor();
			clearValue = { r: clearColor.r, g: clearColor.g, b: clearColor.b, a: clearColor.a };

		}

		if ( renderTargetContext === null ) {

			supportsDepth = renderer.depth;
			supportsStencil = renderer.stencil;

			const descriptor = this._getDefaultRenderPassDescriptor();

			if ( color ) {

				colorAttachments = descriptor.colorAttachments;

				const colorAttachment = colorAttachments[ 0 ];

				colorAttachment.clearValue = clearValue;
				colorAttachment.loadOp = GPULoadOp.Clear;
				colorAttachment.storeOp = GPUStoreOp.Store;

			}

			if ( supportsDepth || supportsStencil ) {

				depthStencilAttachment = descriptor.depthStencilAttachment;

			}

		} else {

			supportsDepth = renderTargetContext.depth;
			supportsStencil = renderTargetContext.stencil;

			const clearConfig = {
				loadOp: color ? GPULoadOp.Clear : GPULoadOp.Load,
				clearValue: color ? clearValue : undefined
			};

			if ( supportsDepth ) {

				clearConfig.depthLoadOp = depth ? GPULoadOp.Clear : GPULoadOp.Load;
				clearConfig.depthClearValue = depth ? renderer.getClearDepth() : undefined;
				clearConfig.depthStoreOp = GPUStoreOp.Store;

			}

			if ( supportsStencil ) {

				clearConfig.stencilLoadOp = stencil ? GPULoadOp.Clear : GPULoadOp.Load;
				clearConfig.stencilClearValue = stencil ? renderer.getClearStencil() : undefined;
				clearConfig.stencilStoreOp = GPUStoreOp.Store;

			}

			const descriptor = this._getRenderPassDescriptor( renderTargetContext, clearConfig );

			colorAttachments = descriptor.colorAttachments;
			depthStencilAttachment = descriptor.depthStencilAttachment;

		}

		if ( supportsDepth && depthStencilAttachment ) {

			if ( depth ) {

				depthStencilAttachment.depthLoadOp = GPULoadOp.Clear;
				depthStencilAttachment.depthClearValue = renderer.getClearDepth();
				depthStencilAttachment.depthStoreOp = GPUStoreOp.Store;

			} else {

				depthStencilAttachment.depthLoadOp = GPULoadOp.Load;
				depthStencilAttachment.depthStoreOp = GPUStoreOp.Store;

			}

		}

		//

		if ( supportsStencil && depthStencilAttachment ) {

			if ( stencil ) {

				depthStencilAttachment.stencilLoadOp = GPULoadOp.Clear;
				depthStencilAttachment.stencilClearValue = renderer.getClearStencil();
				depthStencilAttachment.stencilStoreOp = GPUStoreOp.Store;

			} else {

				depthStencilAttachment.stencilLoadOp = GPULoadOp.Load;
				depthStencilAttachment.stencilStoreOp = GPUStoreOp.Store;

			}

		}

		//

		const encoder = device.createCommandEncoder( { label: 'clear' } );
		const currentPass = encoder.beginRenderPass( {
			colorAttachments,
			depthStencilAttachment
		} );

		currentPass.end();

		device.queue.submit( [ encoder.finish() ] );

	}

	// compute

	/**
	 * This method is executed at the beginning of a compute call and
	 * prepares the state for upcoming compute tasks.
	 *
	 * @param {Node|Array<Node>} computeGroup - The compute node(s).
	 */
	beginCompute( computeGroup ) {

		const groupGPU = this.get( computeGroup );

		const descriptor = {
			label: 'computeGroup_' + computeGroup.id
		};

		this.initTimestampQuery( computeGroup, descriptor );

		groupGPU.cmdEncoderGPU = this.device.createCommandEncoder( { label: 'computeGroup_' + computeGroup.id } );

		groupGPU.passEncoderGPU = groupGPU.cmdEncoderGPU.beginComputePass( descriptor );

	}

	/**
	 * Executes a compute command for the given compute node.
	 *
	 * @param {Node|Array<Node>} computeGroup - The group of compute nodes of a compute call. Can be a single compute node.
	 * @param {Node} computeNode - The compute node.
	 * @param {Array<BindGroup>} bindings - The bindings.
	 * @param {ComputePipeline} pipeline - The compute pipeline.
	 * @param {Array<number>|number} [dispatchSizeOrCount=null] - Array with [ x, y, z ] values for dispatch or a single number for the count.
	 */
	compute( computeGroup, computeNode, bindings, pipeline, dispatchSizeOrCount = null ) {

		const computeNodeData = this.get( computeNode );
		const { passEncoderGPU } = this.get( computeGroup );

		// pipeline

		const pipelineGPU = this.get( pipeline ).pipeline;

		this.pipelineUtils.setPipeline( passEncoderGPU, pipelineGPU );

		// bind groups

		for ( let i = 0, l = bindings.length; i < l; i ++ ) {

			const bindGroup = bindings[ i ];
			const bindingsData = this.get( bindGroup );

			passEncoderGPU.setBindGroup( i, bindingsData.group );

		}

		let dispatchSize;

		if ( dispatchSizeOrCount === null ) {

			dispatchSizeOrCount = computeNode.count;

		}

		if ( typeof dispatchSizeOrCount === 'number' ) {

			// If a single number is given, we calculate the dispatch size based on the workgroup size

			const count = dispatchSizeOrCount;

			if ( computeNodeData.dispatchSize === undefined || computeNodeData.count !== count ) {

				// cache dispatch size to avoid recalculating it every time

				computeNodeData.dispatchSize = [ 0, 1, 1 ];
				computeNodeData.count = count;

				const workgroupSize = computeNode.workgroupSize;

				let size = workgroupSize[ 0 ];

				for ( let i = 1; i < workgroupSize.length; i ++ )
					size *= workgroupSize[ i ];

				const dispatchCount = Math.ceil( count / size );

				//

				const maxComputeWorkgroupsPerDimension = this.device.limits.maxComputeWorkgroupsPerDimension;

				dispatchSize = [ dispatchCount, 1, 1 ];

				if ( dispatchCount > maxComputeWorkgroupsPerDimension ) {

					dispatchSize[ 0 ] = Math.min( dispatchCount, maxComputeWorkgroupsPerDimension );
					dispatchSize[ 1 ] = Math.ceil( dispatchCount / maxComputeWorkgroupsPerDimension );

				}

				computeNodeData.dispatchSize = dispatchSize;

			}

			dispatchSize = computeNodeData.dispatchSize;

		} else {

			dispatchSize = dispatchSizeOrCount;

		}

		//

		passEncoderGPU.dispatchWorkgroups(
			dispatchSize[ 0 ],
			dispatchSize[ 1 ] || 1,
			dispatchSize[ 2 ] || 1
		);

	}

	/**
	 * This method is executed at the end of a compute call and
	 * finalizes work after compute tasks.
	 *
	 * @param {Node|Array<Node>} computeGroup - The compute node(s).
	 */
	finishCompute( computeGroup ) {

		const groupData = this.get( computeGroup );

		groupData.passEncoderGPU.end();

		this.device.queue.submit( [ groupData.cmdEncoderGPU.finish() ] );

	}

	/**
	 * Can be used to synchronize CPU operations with GPU tasks. So when this method is called,
	 * the CPU waits for the GPU to complete its operation (e.g. a compute task).
	 *
	 * @async
	 * @return {Promise} A Promise that resolves when synchronization has been finished.
	 */
	async waitForGPU() {

		await this.device.queue.onSubmittedWorkDone();

	}

	// render object

	/**
	 * Executes a draw command for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object to draw.
	 * @param {Info} info - Holds a series of statistical information about the GPU memory and the rendering process.
	 */
	draw( renderObject, info ) {

		const { object, material, context, pipeline } = renderObject;
		const bindings = renderObject.getBindings();
		const renderContextData = this.get( context );
		const pipelineGPU = this.get( pipeline ).pipeline;

		const index = renderObject.getIndex();
		const hasIndex = ( index !== null );


		const drawParams = renderObject.getDrawParameters();
		if ( drawParams === null ) return;

		// pipeline

		const setPipelineAndBindings = ( passEncoderGPU, currentSets ) => {

			// pipeline
			this.pipelineUtils.setPipeline( passEncoderGPU, pipelineGPU );
			currentSets.pipeline = pipelineGPU;

			// bind groups
			const currentBindingGroups = currentSets.bindingGroups;
			for ( let i = 0, l = bindings.length; i < l; i ++ ) {

				const bindGroup = bindings[ i ];
				const bindingsData = this.get( bindGroup );
				if ( currentBindingGroups[ bindGroup.index ] !== bindGroup.id ) {

					passEncoderGPU.setBindGroup( bindGroup.index, bindingsData.group );
					currentBindingGroups[ bindGroup.index ] = bindGroup.id;

				}

			}

			// attributes

			// index

			if ( hasIndex === true ) {

				if ( currentSets.index !== index ) {

					const buffer = this.get( index ).buffer;
					const indexFormat = ( index.array instanceof Uint16Array ) ? GPUIndexFormat.Uint16 : GPUIndexFormat.Uint32;

					passEncoderGPU.setIndexBuffer( buffer, indexFormat );

					currentSets.index = index;

				}

			}
			// vertex buffers

			const vertexBuffers = renderObject.getVertexBuffers();

			for ( let i = 0, l = vertexBuffers.length; i < l; i ++ ) {

				const vertexBuffer = vertexBuffers[ i ];

				if ( currentSets.attributes[ i ] !== vertexBuffer ) {

					const buffer = this.get( vertexBuffer ).buffer;
					passEncoderGPU.setVertexBuffer( i, buffer );

					currentSets.attributes[ i ] = vertexBuffer;

				}

			}
			// stencil

			if ( context.stencil === true && material.stencilWrite === true && renderContextData.currentStencilRef !== material.stencilRef ) {

				passEncoderGPU.setStencilReference( material.stencilRef );
				renderContextData.currentStencilRef = material.stencilRef;

			}


		};

		// Define draw function
		const draw = ( passEncoderGPU, currentSets ) => {

			setPipelineAndBindings( passEncoderGPU, currentSets );

			if ( object.isBatchedMesh === true ) {

				const starts = object._multiDrawStarts;
				const counts = object._multiDrawCounts;
				const drawCount = object._multiDrawCount;
				const drawInstances = object._multiDrawInstances;

				if ( drawInstances !== null ) {

					// @deprecated, r174
					warnOnce( 'THREE.WebGPUBackend: renderMultiDrawInstances has been deprecated and will be removed in r184. Append to renderMultiDraw arguments and use indirection.' );

				}

				for ( let i = 0; i < drawCount; i ++ ) {

					const count = drawInstances ? drawInstances[ i ] : 1;
					const firstInstance = count > 1 ? 0 : i;

					if ( hasIndex === true ) {

						passEncoderGPU.drawIndexed( counts[ i ], count, starts[ i ] / index.array.BYTES_PER_ELEMENT, 0, firstInstance );

					} else {

						passEncoderGPU.draw( counts[ i ], count, starts[ i ], firstInstance );

					}

					info.update( object, counts[ i ], count );

				}

			} else if ( hasIndex === true ) {

				const { vertexCount: indexCount, instanceCount, firstVertex: firstIndex } = drawParams;

				const indirect = renderObject.getIndirect();

				if ( indirect !== null ) {

					const buffer = this.get( indirect ).buffer;

					passEncoderGPU.drawIndexedIndirect( buffer, 0 );

				} else {

					passEncoderGPU.drawIndexed( indexCount, instanceCount, firstIndex, 0, 0 );

				}

				info.update( object, indexCount, instanceCount );

			} else {

				const { vertexCount, instanceCount, firstVertex } = drawParams;

				const indirect = renderObject.getIndirect();

				if ( indirect !== null ) {

					const buffer = this.get( indirect ).buffer;

					passEncoderGPU.drawIndirect( buffer, 0 );

				} else {

					passEncoderGPU.draw( vertexCount, instanceCount, firstVertex, 0 );

				}

				info.update( object, vertexCount, instanceCount );

			}

		};

		if ( renderObject.camera.isArrayCamera && renderObject.camera.cameras.length > 0 ) {

			const cameraData = this.get( renderObject.camera );
			const cameras = renderObject.camera.cameras;
			const cameraIndex = renderObject.getBindingGroup( 'cameraIndex' );

			if ( cameraData.indexesGPU === undefined || cameraData.indexesGPU.length !== cameras.length ) {

				const bindingsData = this.get( cameraIndex );
				const indexesGPU = [];

				const data = new Uint32Array( [ 0, 0, 0, 0 ] );

				for ( let i = 0, len = cameras.length; i < len; i ++ ) {

					data[ 0 ] = i;

					const bindGroupIndex = this.bindingUtils.createBindGroupIndex( data, bindingsData.layout );

					indexesGPU.push( bindGroupIndex );

				}

				cameraData.indexesGPU = indexesGPU; // TODO: Create a global library for this

			}

			const pixelRatio = this.renderer.getPixelRatio();

			for ( let i = 0, len = cameras.length; i < len; i ++ ) {

				const subCamera = cameras[ i ];

				if ( object.layers.test( subCamera.layers ) ) {

					const vp = subCamera.viewport;



					let pass = renderContextData.currentPass;
					let sets = renderContextData.currentSets;
					if ( renderContextData.bundleEncoders ) {

						const bundleEncoder = renderContextData.bundleEncoders[ i ];
						const bundleSets = renderContextData.bundleSets[ i ];
						pass = bundleEncoder;
						sets = bundleSets;

					}



					if ( vp ) {

						pass.setViewport(
							Math.floor( vp.x * pixelRatio ),
							Math.floor( vp.y * pixelRatio ),
							Math.floor( vp.width * pixelRatio ),
							Math.floor( vp.height * pixelRatio ),
							context.viewportValue.minDepth,
							context.viewportValue.maxDepth
						);

					}


					// Set camera index binding for this layer
					if ( cameraIndex && cameraData.indexesGPU ) {

						pass.setBindGroup( cameraIndex.index, cameraData.indexesGPU[ i ] );
						sets.bindingGroups[ cameraIndex.index ] = cameraIndex.id;

					}

					draw( pass, sets );


				}

			}

		} else {

			// Regular single camera rendering
			if ( renderContextData.currentPass ) {

				// Handle occlusion queries
				if ( renderContextData.occlusionQuerySet !== undefined ) {

					const lastObject = renderContextData.lastOcclusionObject;
					if ( lastObject !== object ) {

						if ( lastObject !== null && lastObject.occlusionTest === true ) {

							renderContextData.currentPass.endOcclusionQuery();
							renderContextData.occlusionQueryIndex ++;

						}

						if ( object.occlusionTest === true ) {

							renderContextData.currentPass.beginOcclusionQuery( renderContextData.occlusionQueryIndex );
							renderContextData.occlusionQueryObjects[ renderContextData.occlusionQueryIndex ] = object;

						}

						renderContextData.lastOcclusionObject = object;

					}

				}

				draw( renderContextData.currentPass, renderContextData.currentSets );

			}

		}

	}

	// cache key

	/**
	 * Returns `true` if the render pipeline requires an update.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {boolean} Whether the render pipeline requires an update or not.
	 */
	needsRenderUpdate( renderObject ) {

		const data = this.get( renderObject );

		const { object, material } = renderObject;

		const utils = this.utils;

		const sampleCount = utils.getSampleCountRenderContext( renderObject.context );
		const colorSpace = utils.getCurrentColorSpace( renderObject.context );
		const colorFormat = utils.getCurrentColorFormat( renderObject.context );
		const depthStencilFormat = utils.getCurrentDepthStencilFormat( renderObject.context );
		const primitiveTopology = utils.getPrimitiveTopology( object, material );

		let needsUpdate = false;

		if ( data.material !== material || data.materialVersion !== material.version ||
			data.transparent !== material.transparent || data.blending !== material.blending || data.premultipliedAlpha !== material.premultipliedAlpha ||
			data.blendSrc !== material.blendSrc || data.blendDst !== material.blendDst || data.blendEquation !== material.blendEquation ||
			data.blendSrcAlpha !== material.blendSrcAlpha || data.blendDstAlpha !== material.blendDstAlpha || data.blendEquationAlpha !== material.blendEquationAlpha ||
			data.colorWrite !== material.colorWrite || data.depthWrite !== material.depthWrite || data.depthTest !== material.depthTest || data.depthFunc !== material.depthFunc ||
			data.stencilWrite !== material.stencilWrite || data.stencilFunc !== material.stencilFunc ||
			data.stencilFail !== material.stencilFail || data.stencilZFail !== material.stencilZFail || data.stencilZPass !== material.stencilZPass ||
			data.stencilFuncMask !== material.stencilFuncMask || data.stencilWriteMask !== material.stencilWriteMask ||
			data.side !== material.side || data.alphaToCoverage !== material.alphaToCoverage ||
			data.sampleCount !== sampleCount || data.colorSpace !== colorSpace ||
			data.colorFormat !== colorFormat || data.depthStencilFormat !== depthStencilFormat ||
			data.primitiveTopology !== primitiveTopology ||
			data.clippingContextCacheKey !== renderObject.clippingContextCacheKey
		) {

			data.material = material; data.materialVersion = material.version;
			data.transparent = material.transparent; data.blending = material.blending; data.premultipliedAlpha = material.premultipliedAlpha;
			data.blendSrc = material.blendSrc; data.blendDst = material.blendDst; data.blendEquation = material.blendEquation;
			data.blendSrcAlpha = material.blendSrcAlpha; data.blendDstAlpha = material.blendDstAlpha; data.blendEquationAlpha = material.blendEquationAlpha;
			data.colorWrite = material.colorWrite;
			data.depthWrite = material.depthWrite; data.depthTest = material.depthTest; data.depthFunc = material.depthFunc;
			data.stencilWrite = material.stencilWrite; data.stencilFunc = material.stencilFunc;
			data.stencilFail = material.stencilFail; data.stencilZFail = material.stencilZFail; data.stencilZPass = material.stencilZPass;
			data.stencilFuncMask = material.stencilFuncMask; data.stencilWriteMask = material.stencilWriteMask;
			data.side = material.side; data.alphaToCoverage = material.alphaToCoverage;
			data.sampleCount = sampleCount;
			data.colorSpace = colorSpace;
			data.colorFormat = colorFormat;
			data.depthStencilFormat = depthStencilFormat;
			data.primitiveTopology = primitiveTopology;
			data.clippingContextCacheKey = renderObject.clippingContextCacheKey;

			needsUpdate = true;

		}

		return needsUpdate;

	}

	/**
	 * Returns a cache key that is used to identify render pipelines.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {string} The cache key.
	 */
	getRenderCacheKey( renderObject ) {

		const { object, material } = renderObject;

		const utils = this.utils;
		const renderContext = renderObject.context;

		return [
			material.transparent, material.blending, material.premultipliedAlpha,
			material.blendSrc, material.blendDst, material.blendEquation,
			material.blendSrcAlpha, material.blendDstAlpha, material.blendEquationAlpha,
			material.colorWrite,
			material.depthWrite, material.depthTest, material.depthFunc,
			material.stencilWrite, material.stencilFunc,
			material.stencilFail, material.stencilZFail, material.stencilZPass,
			material.stencilFuncMask, material.stencilWriteMask,
			material.side,
			utils.getSampleCountRenderContext( renderContext ),
			utils.getCurrentColorSpace( renderContext ), utils.getCurrentColorFormat( renderContext ), utils.getCurrentDepthStencilFormat( renderContext ),
			utils.getPrimitiveTopology( object, material ),
			renderObject.getGeometryCacheKey(),
			renderObject.clippingContextCacheKey
		].join();

	}

	// textures

	/**
	 * Creates a GPU sampler for the given texture.
	 *
	 * @param {Texture} texture - The texture to create the sampler for.
	 */
	createSampler( texture ) {

		this.textureUtils.createSampler( texture );

	}

	/**
	 * Destroys the GPU sampler for the given texture.
	 *
	 * @param {Texture} texture - The texture to destroy the sampler for.
	 */
	destroySampler( texture ) {

		this.textureUtils.destroySampler( texture );

	}

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
	 * Inits a time stamp query for the given render context.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @param {Object} descriptor - The query descriptor.
	 */
	initTimestampQuery( renderContext, descriptor ) {

		if ( ! this.trackTimestamp ) return;

		const type = renderContext.isComputeNode ? 'compute' : 'render';

		if ( ! this.timestampQueryPool[ type ] ) {

			// TODO: Variable maxQueries?
			this.timestampQueryPool[ type ] = new WebGPUTimestampQueryPool( this.device, type, 2048 );

		}

		const timestampQueryPool = this.timestampQueryPool[ type ];

		const baseOffset = timestampQueryPool.allocateQueriesForContext( renderContext );

		descriptor.timestampWrites = {
			querySet: timestampQueryPool.querySet,
			beginningOfPassWriteIndex: baseOffset,
			endOfPassWriteIndex: baseOffset + 1,
		  };

	}


	// node builder

	/**
	 * Returns a node builder for the given render object.
	 *
	 * @param {RenderObject} object - The render object.
	 * @param {Renderer} renderer - The renderer.
	 * @return {WGSLNodeBuilder} The node builder.
	 */
	createNodeBuilder( object, renderer ) {

		return new WGSLNodeBuilder( object, renderer );

	}

	// program

	/**
	 * Creates a shader program from the given programmable stage.
	 *
	 * @param {ProgrammableStage} program - The programmable stage.
	 */
	createProgram( program ) {

		const programGPU = this.get( program );

		programGPU.module = {
			module: this.device.createShaderModule( { code: program.code, label: program.stage + ( program.name !== '' ? `_${ program.name }` : '' ) } ),
			entryPoint: 'main'
		};

	}

	/**
	 * Destroys the shader program of the given programmable stage.
	 *
	 * @param {ProgrammableStage} program - The programmable stage.
	 */
	destroyProgram( program ) {

		this.delete( program );

	}

	// pipelines

	/**
	 * Creates a render pipeline for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @param {Array<Promise>} promises - An array of compilation promises which are used in `compileAsync()`.
	 */
	createRenderPipeline( renderObject, promises ) {

		this.pipelineUtils.createRenderPipeline( renderObject, promises );

	}

	/**
	 * Creates a compute pipeline for the given compute node.
	 *
	 * @param {ComputePipeline} computePipeline - The compute pipeline.
	 * @param {Array<BindGroup>} bindings - The bindings.
	 */
	createComputePipeline( computePipeline, bindings ) {

		this.pipelineUtils.createComputePipeline( computePipeline, bindings );

	}

	/**
	 * Prepares the state for encoding render bundles.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 */
	beginBundle( renderContext ) {

		const renderContextData = this.get( renderContext );

		renderContextData._currentPass = renderContextData.currentPass;
		renderContextData._currentSets = renderContextData.currentSets;

		renderContextData.currentSets = { attributes: {}, bindingGroups: [], pipeline: null, index: null };
		renderContextData.currentPass = this.pipelineUtils.createBundleEncoder( renderContext );

	}

	/**
	 * After processing render bundles this method finalizes related work.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @param {RenderBundle} bundle - The render bundle.
	 */
	finishBundle( renderContext, bundle ) {

		const renderContextData = this.get( renderContext );

		const bundleEncoder = renderContextData.currentPass;
		const bundleGPU = bundleEncoder.finish();

		this.get( bundle ).bundleGPU = bundleGPU;

		// restore render pass state

		renderContextData.currentSets = renderContextData._currentSets;
		renderContextData.currentPass = renderContextData._currentPass;

	}

	/**
	 * Adds a render bundle to the render context data.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @param {RenderBundle} bundle - The render bundle to add.
	 */
	addBundle( renderContext, bundle ) {

		const renderContextData = this.get( renderContext );

		renderContextData.renderBundles.push( this.get( bundle ).bundleGPU );

	}

	// bindings

	/**
	 * Creates bindings from the given bind group definition.
	 *
	 * @param {BindGroup} bindGroup - The bind group.
	 * @param {Array<BindGroup>} bindings - Array of bind groups.
	 * @param {number} cacheIndex - The cache index.
	 * @param {number} version - The version.
	 */
	createBindings( bindGroup, bindings, cacheIndex, version ) {

		this.bindingUtils.createBindings( bindGroup, bindings, cacheIndex, version );

	}

	/**
	 * Updates the given bind group definition.
	 *
	 * @param {BindGroup} bindGroup - The bind group.
	 * @param {Array<BindGroup>} bindings - Array of bind groups.
	 * @param {number} cacheIndex - The cache index.
	 * @param {number} version - The version.
	 */
	updateBindings( bindGroup, bindings, cacheIndex, version ) {

		this.bindingUtils.createBindings( bindGroup, bindings, cacheIndex, version );

	}

	/**
	 * Updates a buffer binding.
	 *
	 *  @param {Buffer} binding - The buffer binding to update.
	 */
	updateBinding( binding ) {

		this.bindingUtils.updateBinding( binding );

	}

	// attributes

	/**
	 * Creates the buffer of an indexed shader attribute.
	 *
	 * @param {BufferAttribute} attribute - The indexed buffer attribute.
	 */
	createIndexAttribute( attribute ) {

		let usage = GPUBufferUsage.INDEX | GPUBufferUsage.COPY_SRC | GPUBufferUsage.COPY_DST;

		if ( attribute.isStorageBufferAttribute || attribute.isStorageInstancedBufferAttribute ) {

			usage |= GPUBufferUsage.STORAGE;

		}

		this.attributeUtils.createAttribute( attribute, usage );

	}

	/**
	 * Creates the GPU buffer of a shader attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
	createAttribute( attribute ) {

		this.attributeUtils.createAttribute( attribute, GPUBufferUsage.VERTEX | GPUBufferUsage.COPY_SRC | GPUBufferUsage.COPY_DST );

	}

	/**
	 * Creates the GPU buffer of a storage attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
	createStorageAttribute( attribute ) {

		this.attributeUtils.createAttribute( attribute, GPUBufferUsage.STORAGE | GPUBufferUsage.VERTEX | GPUBufferUsage.COPY_SRC | GPUBufferUsage.COPY_DST );

	}

	/**
	 * Creates the GPU buffer of an indirect storage attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
	createIndirectStorageAttribute( attribute ) {

		this.attributeUtils.createAttribute( attribute, GPUBufferUsage.STORAGE | GPUBufferUsage.INDIRECT | GPUBufferUsage.COPY_SRC | GPUBufferUsage.COPY_DST );

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

	// canvas

	/**
	 * Triggers an update of the default render pass descriptor.
	 */
	updateSize() {

		this.colorBuffer = this.textureUtils.getColorBuffer();
		this.defaultRenderPassdescriptor = null;

	}

	// utils public

	/**
	 * Returns the maximum anisotropy texture filtering value.
	 *
	 * @return {number} The maximum anisotropy texture filtering value.
	 */
	getMaxAnisotropy() {

		return 16;

	}

	/**
	 * Checks if the given feature is supported  by the backend.
	 *
	 * @param {string} name - The feature's name.
	 * @return {boolean} Whether the feature is supported or not.
	 */
	hasFeature( name ) {

		return this.device.features.has( name );

	}

	/**
	 * Copies data of the given source texture to the given destination texture.
	 *
	 * @param {Texture} srcTexture - The source texture.
	 * @param {Texture} dstTexture - The destination texture.
	 * @param {?(Box3|Box2)} [srcRegion=null] - The region of the source texture to copy.
	 * @param {?(Vector2|Vector3)} [dstPosition=null] - The destination position of the copy.
	 * @param {number} [srcLevel=0] - The mipmap level to copy.
	 * @param {number} [dstLevel=0] - The destination mip level to copy to.
	 */
	copyTextureToTexture( srcTexture, dstTexture, srcRegion = null, dstPosition = null, srcLevel = 0, dstLevel = 0 ) {

		let dstX = 0;
		let dstY = 0;
		let dstZ = 0;

		let srcX = 0;
		let srcY = 0;
		let srcZ = 0;

		let srcWidth = srcTexture.image.width;
		let srcHeight = srcTexture.image.height;
		let srcDepth = 1;


		if ( srcRegion !== null ) {

			if ( srcRegion.isBox3 === true ) {

				srcX = srcRegion.min.x;
				srcY = srcRegion.min.y;
				srcZ = srcRegion.min.z;
				srcWidth = srcRegion.max.x - srcRegion.min.x;
				srcHeight = srcRegion.max.y - srcRegion.min.y;
				srcDepth = srcRegion.max.z - srcRegion.min.z;

			} else {

				// Assume it's a Box2
				srcX = srcRegion.min.x;
				srcY = srcRegion.min.y;
				srcWidth = srcRegion.max.x - srcRegion.min.x;
				srcHeight = srcRegion.max.y - srcRegion.min.y;
				srcDepth = 1;

			}

		}


		if ( dstPosition !== null ) {

			dstX = dstPosition.x;
			dstY = dstPosition.y;
			dstZ = dstPosition.z || 0;

		}

		const encoder = this.device.createCommandEncoder( { label: 'copyTextureToTexture_' + srcTexture.id + '_' + dstTexture.id } );

		const sourceGPU = this.get( srcTexture ).texture;
		const destinationGPU = this.get( dstTexture ).texture;

		encoder.copyTextureToTexture(
			{
				texture: sourceGPU,
				mipLevel: srcLevel,
				origin: { x: srcX, y: srcY, z: srcZ }
			},
			{
				texture: destinationGPU,
				mipLevel: dstLevel,
				origin: { x: dstX, y: dstY, z: dstZ }
			},
			[
				srcWidth,
				srcHeight,
				srcDepth
			]
		);

		this.device.queue.submit( [ encoder.finish() ] );

		if ( dstLevel === 0 && dstTexture.generateMipmaps ) {

			this.textureUtils.generateMipmaps( dstTexture );

		}

	}

	/**
	 * Copies the current bound framebuffer to the given texture.
	 *
	 * @param {Texture} texture - The destination texture.
	 * @param {RenderContext} renderContext - The render context.
	 * @param {Vector4} rectangle - A four dimensional vector defining the origin and dimension of the copy.
	 */
	copyFramebufferToTexture( texture, renderContext, rectangle ) {

		const renderContextData = this.get( renderContext );

		let sourceGPU = null;

		if ( renderContext.renderTarget ) {

			if ( texture.isDepthTexture ) {

				sourceGPU = this.get( renderContext.depthTexture ).texture;

			} else {

				sourceGPU = this.get( renderContext.textures[ 0 ] ).texture;

			}

		} else {

			if ( texture.isDepthTexture ) {

				sourceGPU = this.textureUtils.getDepthBuffer( renderContext.depth, renderContext.stencil );

			} else {

				sourceGPU = this.context.getCurrentTexture();

			}

		}

		const destinationGPU = this.get( texture ).texture;

		if ( sourceGPU.format !== destinationGPU.format ) {

			console.error( 'WebGPUBackend: copyFramebufferToTexture: Source and destination formats do not match.', sourceGPU.format, destinationGPU.format );

			return;

		}

		let encoder;

		if ( renderContextData.currentPass ) {

			renderContextData.currentPass.end();

			encoder = renderContextData.encoder;

		} else {

			encoder = this.device.createCommandEncoder( { label: 'copyFramebufferToTexture_' + texture.id } );

		}

		encoder.copyTextureToTexture(
			{
				texture: sourceGPU,
				origin: [ rectangle.x, rectangle.y, 0 ],
			},
			{
				texture: destinationGPU
			},
			[
				rectangle.z,
				rectangle.w
			]
		);

		if ( renderContextData.currentPass ) {

			const { descriptor } = renderContextData;

			for ( let i = 0; i < descriptor.colorAttachments.length; i ++ ) {

				descriptor.colorAttachments[ i ].loadOp = GPULoadOp.Load;

			}

			if ( renderContext.depth ) descriptor.depthStencilAttachment.depthLoadOp = GPULoadOp.Load;
			if ( renderContext.stencil ) descriptor.depthStencilAttachment.stencilLoadOp = GPULoadOp.Load;

			renderContextData.currentPass = encoder.beginRenderPass( descriptor );
			renderContextData.currentSets = { attributes: {}, bindingGroups: [], pipeline: null, index: null };

			if ( renderContext.viewport ) {

				this.updateViewport( renderContext );

			}

			if ( renderContext.scissor ) {

				const { x, y, width, height } = renderContext.scissorValue;

				renderContextData.currentPass.setScissorRect( x, y, width, height );

			}

		} else {

			this.device.queue.submit( [ encoder.finish() ] );

		}

		if ( texture.generateMipmaps ) {

			this.textureUtils.generateMipmaps( texture );

		}

	}

}
```
</details>

#### Methods

##### `init(renderer: Renderer): Promise<any>`

<details><summary>Code</summary>

```ts
async init( renderer ) {

		await super.init( renderer );

		//

		const parameters = this.parameters;

		// create the device if it is not passed with parameters

		let device;

		if ( parameters.device === undefined ) {

			const adapterOptions = {
				powerPreference: parameters.powerPreference,
				featureLevel: parameters.compatibilityMode ? 'compatibility' : undefined
			};

			const adapter = ( typeof navigator !== 'undefined' ) ? await navigator.gpu.requestAdapter( adapterOptions ) : null;

			if ( adapter === null ) {

				throw new Error( 'WebGPUBackend: Unable to create WebGPU adapter.' );

			}

			// feature support

			const features = Object.values( GPUFeatureName );

			const supportedFeatures = [];

			for ( const name of features ) {

				if ( adapter.features.has( name ) ) {

					supportedFeatures.push( name );

				}

			}

			const deviceDescriptor = {
				requiredFeatures: supportedFeatures,
				requiredLimits: parameters.requiredLimits
			};

			device = await adapter.requestDevice( deviceDescriptor );

		} else {

			device = parameters.device;

		}

		device.lost.then( ( info ) => {

			const deviceLossInfo = {
				api: 'WebGPU',
				message: info.message || 'Unknown reason',
				reason: info.reason || null,
				originalEvent: info
			};

			renderer.onDeviceLost( deviceLossInfo );

		} );

		const context = ( parameters.context !== undefined ) ? parameters.context : renderer.domElement.getContext( 'webgpu' );

		this.device = device;
		this.context = context;

		const alphaMode = parameters.alpha ? 'premultiplied' : 'opaque';

		this.trackTimestamp = this.trackTimestamp && this.hasFeature( GPUFeatureName.TimestampQuery );

		this.context.configure( {
			device: this.device,
			format: this.utils.getPreferredCanvasFormat(),
			usage: GPUTextureUsage.RENDER_ATTACHMENT | GPUTextureUsage.COPY_SRC,
			alphaMode: alphaMode
		} );

		this.updateSize();

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

##### `getContext(): GPUCanvasContext`

<details><summary>Code</summary>

```ts
getContext() {

		return this.context;

	}
```
</details>

##### `_getDefaultRenderPassDescriptor(): any`

<details><summary>Code</summary>

```ts
_getDefaultRenderPassDescriptor() {

		let descriptor = this.defaultRenderPassdescriptor;

		if ( descriptor === null ) {

			const renderer = this.renderer;

			descriptor = {
				colorAttachments: [ {
					view: null
				} ],
			};

			if ( this.renderer.depth === true || this.renderer.stencil === true ) {

				descriptor.depthStencilAttachment = {
					view: this.textureUtils.getDepthBuffer( renderer.depth, renderer.stencil ).createView()
				};

			}

			const colorAttachment = descriptor.colorAttachments[ 0 ];

			if ( this.renderer.samples > 0 ) {

				colorAttachment.view = this.colorBuffer.createView();

			} else {

				colorAttachment.resolveTarget = undefined;

			}

			this.defaultRenderPassdescriptor = descriptor;

		}

		const colorAttachment = descriptor.colorAttachments[ 0 ];

		if ( this.renderer.samples > 0 ) {

			colorAttachment.resolveTarget = this.context.getCurrentTexture().createView();

		} else {

			colorAttachment.view = this.context.getCurrentTexture().createView();

		}

		return descriptor;

	}
```
</details>

##### `_isRenderCameraDepthArray(renderContext: RenderContext): boolean`

<details><summary>Code</summary>

```ts
_isRenderCameraDepthArray( renderContext ) {

		return renderContext.depthTexture && renderContext.depthTexture.image.depth > 1 && renderContext.camera.isArrayCamera;

	}
```
</details>

##### `_getRenderPassDescriptor(renderContext: RenderContext, colorAttachmentsConfig: any): any`

<details><summary>Code</summary>

```ts
_getRenderPassDescriptor( renderContext, colorAttachmentsConfig = {} ) {

		const renderTarget = renderContext.renderTarget;
		const renderTargetData = this.get( renderTarget );

		let descriptors = renderTargetData.descriptors;

		if ( descriptors === undefined ||
			renderTargetData.width !== renderTarget.width ||
			renderTargetData.height !== renderTarget.height ||
			renderTargetData.dimensions !== renderTarget.dimensions ||
			renderTargetData.activeMipmapLevel !== renderContext.activeMipmapLevel ||
			renderTargetData.activeCubeFace !== renderContext.activeCubeFace ||
			renderTargetData.samples !== renderTarget.samples
		) {

			descriptors = {};

			renderTargetData.descriptors = descriptors;

			// dispose

			const onDispose = () => {

				renderTarget.removeEventListener( 'dispose', onDispose );
				this.delete( renderTarget );

			};

			if ( renderTarget.hasEventListener( 'dispose', onDispose ) === false ) {

				renderTarget.addEventListener( 'dispose', onDispose );

			}

		}

		const cacheKey = renderContext.getCacheKey();
		let descriptorBase = descriptors[ cacheKey ];

		if ( descriptorBase === undefined ) {

			const textures = renderContext.textures;
			const textureViews = [];

			let sliceIndex;

			const isRenderCameraDepthArray = this._isRenderCameraDepthArray( renderContext );

			for ( let i = 0; i < textures.length; i ++ ) {

				const textureData = this.get( textures[ i ] );

				const viewDescriptor = {
					label: `colorAttachment_${ i }`,
					baseMipLevel: renderContext.activeMipmapLevel,
					mipLevelCount: 1,
					baseArrayLayer: renderContext.activeCubeFace,
					arrayLayerCount: 1,
					dimension: GPUTextureViewDimension.TwoD
				};

				if ( renderTarget.isRenderTarget3D ) {

					sliceIndex = renderContext.activeCubeFace;

					viewDescriptor.baseArrayLayer = 0;
					viewDescriptor.dimension = GPUTextureViewDimension.ThreeD;
					viewDescriptor.depthOrArrayLayers = textures[ i ].image.depth;

				} else if ( renderTarget.isRenderTarget && textures[ i ].image.depth > 1 ) {

					if ( isRenderCameraDepthArray === true ) {

						const cameras = renderContext.camera.cameras;
						for ( let layer = 0; layer < cameras.length; layer ++ ) {

							const layerViewDescriptor = {
								...viewDescriptor,
								baseArrayLayer: layer,
								arrayLayerCount: 1,
								dimension: GPUTextureViewDimension.TwoD
							};
							const textureView = textureData.texture.createView( layerViewDescriptor );
							textureViews.push( {
								view: textureView,
								resolveTarget: undefined,
								depthSlice: undefined
							} );

						}

					} else {

						viewDescriptor.dimension = GPUTextureViewDimension.TwoDArray;
						viewDescriptor.depthOrArrayLayers = textures[ i ].image.depth;

					}

				}

				if ( isRenderCameraDepthArray !== true ) {

					const textureView = textureData.texture.createView( viewDescriptor );

					let view, resolveTarget;

					if ( textureData.msaaTexture !== undefined ) {

						view = textureData.msaaTexture.createView();
						resolveTarget = textureView;

					} else {

						view = textureView;
						resolveTarget = undefined;

					}

					textureViews.push( {
						view,
						resolveTarget,
						depthSlice: sliceIndex
					} );

				}

			}

			descriptorBase = { textureViews };

			if ( renderContext.depth ) {

				const depthTextureData = this.get( renderContext.depthTexture );
				const options = {};
				if ( renderContext.depthTexture.isArrayTexture ) {

					options.dimension = GPUTextureViewDimension.TwoD;
					options.arrayLayerCount = 1;
					options.baseArrayLayer = renderContext.activeCubeFace;

				}

				descriptorBase.depthStencilView = depthTextureData.texture.createView( options );

			}

			descriptors[ cacheKey ] = descriptorBase;

			renderTargetData.width = renderTarget.width;
			renderTargetData.height = renderTarget.height;
			renderTargetData.samples = renderTarget.samples;
			renderTargetData.activeMipmapLevel = renderContext.activeMipmapLevel;
			renderTargetData.activeCubeFace = renderContext.activeCubeFace;
			renderTargetData.dimensions = renderTarget.dimensions;

		}

		const descriptor = {
			colorAttachments: []
		};

		// Apply dynamic properties to cached views
		for ( let i = 0; i < descriptorBase.textureViews.length; i ++ ) {

			const viewInfo = descriptorBase.textureViews[ i ];

			let clearValue = { r: 0, g: 0, b: 0, a: 1 };
			if ( i === 0 && colorAttachmentsConfig.clearValue ) {

				clearValue = colorAttachmentsConfig.clearValue;

			}

			descriptor.colorAttachments.push( {
				view: viewInfo.view,
				depthSlice: viewInfo.depthSlice,
				resolveTarget: viewInfo.resolveTarget,
				loadOp: colorAttachmentsConfig.loadOp || GPULoadOp.Load,
				storeOp: colorAttachmentsConfig.storeOp || GPUStoreOp.Store,
				clearValue: clearValue
			} );

		}

		if ( descriptorBase.depthStencilView ) {

			descriptor.depthStencilAttachment = {
				view: descriptorBase.depthStencilView
			};

		}

		return descriptor;

	}
```
</details>

##### `beginRender(renderContext: RenderContext): void`

<details><summary>Code</summary>

```ts
beginRender( renderContext ) {

		const renderContextData = this.get( renderContext );

		const device = this.device;
		const occlusionQueryCount = renderContext.occlusionQueryCount;

		let occlusionQuerySet;

		if ( occlusionQueryCount > 0 ) {

			if ( renderContextData.currentOcclusionQuerySet ) renderContextData.currentOcclusionQuerySet.destroy();
			if ( renderContextData.currentOcclusionQueryBuffer ) renderContextData.currentOcclusionQueryBuffer.destroy();

			// Get a reference to the array of objects with queries. The renderContextData property
			// can be changed by another render pass before the buffer.mapAsyc() completes.
			renderContextData.currentOcclusionQuerySet = renderContextData.occlusionQuerySet;
			renderContextData.currentOcclusionQueryBuffer = renderContextData.occlusionQueryBuffer;
			renderContextData.currentOcclusionQueryObjects = renderContextData.occlusionQueryObjects;

			//

			occlusionQuerySet = device.createQuerySet( { type: 'occlusion', count: occlusionQueryCount, label: `occlusionQuerySet_${ renderContext.id }` } );

			renderContextData.occlusionQuerySet = occlusionQuerySet;
			renderContextData.occlusionQueryIndex = 0;
			renderContextData.occlusionQueryObjects = new Array( occlusionQueryCount );

			renderContextData.lastOcclusionObject = null;

		}

		let descriptor;

		if ( renderContext.textures === null ) {

			descriptor = this._getDefaultRenderPassDescriptor();

		} else {

			descriptor = this._getRenderPassDescriptor( renderContext, { loadOp: GPULoadOp.Load } );

		}

		this.initTimestampQuery( renderContext, descriptor );

		descriptor.occlusionQuerySet = occlusionQuerySet;

		const depthStencilAttachment = descriptor.depthStencilAttachment;

		if ( renderContext.textures !== null ) {

			const colorAttachments = descriptor.colorAttachments;

			for ( let i = 0; i < colorAttachments.length; i ++ ) {

				const colorAttachment = colorAttachments[ i ];

				if ( renderContext.clearColor ) {

					colorAttachment.clearValue = i === 0 ? renderContext.clearColorValue : { r: 0, g: 0, b: 0, a: 1 };
					colorAttachment.loadOp = GPULoadOp.Clear;

				} else {

					colorAttachment.loadOp = GPULoadOp.Load;

				}

				colorAttachment.storeOp = GPUStoreOp.Store;

			}

		} else {

			const colorAttachment = descriptor.colorAttachments[ 0 ];

			if ( renderContext.clearColor ) {

				colorAttachment.clearValue = renderContext.clearColorValue;
				colorAttachment.loadOp = GPULoadOp.Clear;

			} else {

				colorAttachment.loadOp = GPULoadOp.Load;

			}

		  	colorAttachment.storeOp = GPUStoreOp.Store;

		}

		//

		if ( renderContext.depth ) {

			if ( renderContext.clearDepth ) {

				depthStencilAttachment.depthClearValue = renderContext.clearDepthValue;
				depthStencilAttachment.depthLoadOp = GPULoadOp.Clear;

			} else {

				depthStencilAttachment.depthLoadOp = GPULoadOp.Load;

			}

		  depthStencilAttachment.depthStoreOp = GPUStoreOp.Store;

		}

		if ( renderContext.stencil ) {

		  if ( renderContext.clearStencil ) {

				depthStencilAttachment.stencilClearValue = renderContext.clearStencilValue;
				depthStencilAttachment.stencilLoadOp = GPULoadOp.Clear;

			} else {

				depthStencilAttachment.stencilLoadOp = GPULoadOp.Load;

			}

		  depthStencilAttachment.stencilStoreOp = GPUStoreOp.Store;

		}

		//

		const encoder = device.createCommandEncoder( { label: 'renderContext_' + renderContext.id } );

		// shadow arrays - prepare bundle encoders for each camera in an array camera

		if ( this._isRenderCameraDepthArray( renderContext ) === true ) {

			const cameras = renderContext.camera.cameras;

			if ( ! renderContextData.layerDescriptors || renderContextData.layerDescriptors.length !== cameras.length ) {

				this._createDepthLayerDescriptors( renderContext, renderContextData, descriptor, cameras );

			} else {

				this._updateDepthLayerDescriptors( renderContext, renderContextData, cameras );

			}

			// Create bundle encoders for each layer
			renderContextData.bundleEncoders = [];
			renderContextData.bundleSets = [];

			// Create separate bundle encoders for each camera in the array
			for ( let i = 0; i < cameras.length; i ++ ) {

				const bundleEncoder = this.pipelineUtils.createBundleEncoder(
					renderContext,
					'renderBundleArrayCamera_' + i
				);

				// Initialize state tracking for this bundle
				const bundleSets = {
					attributes: {},
					bindingGroups: [],
					pipeline: null,
					index: null
				};

				renderContextData.bundleEncoders.push( bundleEncoder );
				renderContextData.bundleSets.push( bundleSets );

			}

			// We'll complete the bundles in finishRender
			renderContextData.currentPass = null;

		} else {

			const currentPass = encoder.beginRenderPass( descriptor );
			renderContextData.currentPass = currentPass;

			if ( renderContext.viewport ) {

				this.updateViewport( renderContext );

			}

			if ( renderContext.scissor ) {

				const { x, y, width, height } = renderContext.scissorValue;
				currentPass.setScissorRect( x, y, width, height );

			}

		}

		//

		renderContextData.descriptor = descriptor;
		renderContextData.encoder = encoder;
		renderContextData.currentSets = { attributes: {}, bindingGroups: [], pipeline: null, index: null };
		renderContextData.renderBundles = [];

	}
```
</details>

##### `_createDepthLayerDescriptors(renderContext: RenderContext, renderContextData: any, descriptor: any, cameras: ArrayCamera): void`

<details><summary>Code</summary>

```ts
_createDepthLayerDescriptors( renderContext, renderContextData, descriptor, cameras ) {

		const depthStencilAttachment = descriptor.depthStencilAttachment;
		renderContextData.layerDescriptors = [];

		const depthTextureData = this.get( renderContext.depthTexture );
		if ( ! depthTextureData.viewCache ) {

			depthTextureData.viewCache = [];

		}

		for ( let i = 0; i < cameras.length; i ++ ) {

			const layerDescriptor = {
				...descriptor,
				colorAttachments: [ {
					...descriptor.colorAttachments[ 0 ],
					view: descriptor.colorAttachments[ i ].view
				} ]
			};

			if ( descriptor.depthStencilAttachment ) {

				const layerIndex = i;

				if ( ! depthTextureData.viewCache[ layerIndex ] ) {

					depthTextureData.viewCache[ layerIndex ] = depthTextureData.texture.createView( {
						dimension: GPUTextureViewDimension.TwoD,
						baseArrayLayer: i,
						arrayLayerCount: 1
					} );

				}

				layerDescriptor.depthStencilAttachment = {
					view: depthTextureData.viewCache[ layerIndex ],
					depthLoadOp: depthStencilAttachment.depthLoadOp || GPULoadOp.Clear,
					depthStoreOp: depthStencilAttachment.depthStoreOp || GPUStoreOp.Store,
					depthClearValue: depthStencilAttachment.depthClearValue || 1.0
				};

				if ( renderContext.stencil ) {

					layerDescriptor.depthStencilAttachment.stencilLoadOp = depthStencilAttachment.stencilLoadOp;
					layerDescriptor.depthStencilAttachment.stencilStoreOp = depthStencilAttachment.stencilStoreOp;
					layerDescriptor.depthStencilAttachment.stencilClearValue = depthStencilAttachment.stencilClearValue;

				}

			} else {

				layerDescriptor.depthStencilAttachment = { ...depthStencilAttachment };

			}

			renderContextData.layerDescriptors.push( layerDescriptor );

		}

	}
```
</details>

##### `_updateDepthLayerDescriptors(renderContext: RenderContext, renderContextData: any, cameras: ArrayCamera): void`

<details><summary>Code</summary>

```ts
_updateDepthLayerDescriptors( renderContext, renderContextData, cameras ) {

		for ( let i = 0; i < cameras.length; i ++ ) {

			const layerDescriptor = renderContextData.layerDescriptors[ i ];

			if ( layerDescriptor.depthStencilAttachment ) {

				const depthAttachment = layerDescriptor.depthStencilAttachment;

				if ( renderContext.depth ) {

					if ( renderContext.clearDepth ) {

						depthAttachment.depthClearValue = renderContext.clearDepthValue;
						depthAttachment.depthLoadOp = GPULoadOp.Clear;

					} else {

						depthAttachment.depthLoadOp = GPULoadOp.Load;

					}

				}

				if ( renderContext.stencil ) {

					if ( renderContext.clearStencil ) {

						depthAttachment.stencilClearValue = renderContext.clearStencilValue;
						depthAttachment.stencilLoadOp = GPULoadOp.Clear;

					} else {

						depthAttachment.stencilLoadOp = GPULoadOp.Load;

					}

				}

			}

		}

	}
```
</details>

##### `finishRender(renderContext: RenderContext): void`

<details><summary>Code</summary>

```ts
finishRender( renderContext ) {

		const renderContextData = this.get( renderContext );
		const occlusionQueryCount = renderContext.occlusionQueryCount;

		if ( renderContextData.renderBundles.length > 0 ) {

			renderContextData.currentPass.executeBundles( renderContextData.renderBundles );

		}

		if ( occlusionQueryCount > renderContextData.occlusionQueryIndex ) {

			renderContextData.currentPass.endOcclusionQuery();

		}

		// shadow arrays - Execute bundles for each layer

		const encoder = renderContextData.encoder;

		if ( this._isRenderCameraDepthArray( renderContext ) === true ) {

		  const bundles = [];

		  for ( let i = 0; i < renderContextData.bundleEncoders.length; i ++ ) {

				const bundleEncoder = renderContextData.bundleEncoders[ i ];
				bundles.push( bundleEncoder.finish() );

			}

		  for ( let i = 0; i < renderContextData.layerDescriptors.length; i ++ ) {

				if ( i < bundles.length ) {

					const layerDescriptor = renderContextData.layerDescriptors[ i ];
					const renderPass = encoder.beginRenderPass( layerDescriptor );

					if ( renderContext.viewport ) {

						const { x, y, width, height, minDepth, maxDepth } = renderContext.viewportValue;
						renderPass.setViewport( x, y, width, height, minDepth, maxDepth );

					}

					if ( renderContext.scissor ) {

						const { x, y, width, height } = renderContext.scissorValue;
						renderPass.setScissorRect( x, y, width, height );

					}

					renderPass.executeBundles( [ bundles[ i ] ] );

					renderPass.end();

				}

			}

		} else if ( renderContextData.currentPass ) {

		  renderContextData.currentPass.end();

		}

		if ( occlusionQueryCount > 0 ) {

			const bufferSize = occlusionQueryCount * 8; // 8 byte entries for query results

			//

			let queryResolveBuffer = this.occludedResolveCache.get( bufferSize );

			if ( queryResolveBuffer === undefined ) {

				queryResolveBuffer = this.device.createBuffer(
					{
						size: bufferSize,
						usage: GPUBufferUsage.QUERY_RESOLVE | GPUBufferUsage.COPY_SRC
					}
				);

				this.occludedResolveCache.set( bufferSize, queryResolveBuffer );

			}

			//

			const readBuffer = this.device.createBuffer(
				{
					size: bufferSize,
					usage: GPUBufferUsage.COPY_DST | GPUBufferUsage.MAP_READ
				}
			);

			// two buffers required here - WebGPU doesn't allow usage of QUERY_RESOLVE & MAP_READ to be combined
			renderContextData.encoder.resolveQuerySet( renderContextData.occlusionQuerySet, 0, occlusionQueryCount, queryResolveBuffer, 0 );
			renderContextData.encoder.copyBufferToBuffer( queryResolveBuffer, 0, readBuffer, 0, bufferSize );

			renderContextData.occlusionQueryBuffer = readBuffer;

			//

			this.resolveOccludedAsync( renderContext );

		}

		this.device.queue.submit( [ renderContextData.encoder.finish() ] );


		//

		if ( renderContext.textures !== null ) {

			const textures = renderContext.textures;

			for ( let i = 0; i < textures.length; i ++ ) {

				const texture = textures[ i ];

				if ( texture.generateMipmaps === true ) {

					this.textureUtils.generateMipmaps( texture );

				}

			}

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

##### `resolveOccludedAsync(renderContext: RenderContext): Promise<any>`

<details><summary>Code</summary>

```ts
async resolveOccludedAsync( renderContext ) {

		const renderContextData = this.get( renderContext );

		// handle occlusion query results

		const { currentOcclusionQueryBuffer, currentOcclusionQueryObjects } = renderContextData;

		if ( currentOcclusionQueryBuffer && currentOcclusionQueryObjects ) {

			const occluded = new WeakSet();

			renderContextData.currentOcclusionQueryObjects = null;
			renderContextData.currentOcclusionQueryBuffer = null;

			await currentOcclusionQueryBuffer.mapAsync( GPUMapMode.READ );

			const buffer = currentOcclusionQueryBuffer.getMappedRange();
			const results = new BigUint64Array( buffer );

			for ( let i = 0; i < currentOcclusionQueryObjects.length; i ++ ) {

				if ( results[ i ] === BigInt( 0 ) ) {

					occluded.add( currentOcclusionQueryObjects[ i ] );

				}

			}

			currentOcclusionQueryBuffer.destroy();

			renderContextData.occluded = occluded;

		}

	}
```
</details>

##### `updateViewport(renderContext: RenderContext): void`

<details><summary>Code</summary>

```ts
updateViewport( renderContext ) {

		const { currentPass } = this.get( renderContext );
		const { x, y, width, height, minDepth, maxDepth } = renderContext.viewportValue;

		currentPass.setViewport( x, y, width, height, minDepth, maxDepth );

	}
```
</details>

##### `getClearColor(): Color4`

<details><summary>Code</summary>

```ts
getClearColor() {

		const clearColor = super.getClearColor();

		// only premultiply alpha when alphaMode is "premultiplied"

		if ( this.renderer.alpha === true ) {

			clearColor.r *= clearColor.a;
			clearColor.g *= clearColor.a;
			clearColor.b *= clearColor.a;

		}

		return clearColor;

	}
```
</details>

##### `clear(color: boolean, depth: boolean, stencil: boolean, renderTargetContext: RenderContext): void`

<details><summary>Code</summary>

```ts
clear( color, depth, stencil, renderTargetContext = null ) {

		const device = this.device;
		const renderer = this.renderer;

		let colorAttachments = [];
		let depthStencilAttachment;
		let clearValue;

		let supportsDepth;
		let supportsStencil;

		if ( color ) {

			const clearColor = this.getClearColor();
			clearValue = { r: clearColor.r, g: clearColor.g, b: clearColor.b, a: clearColor.a };

		}

		if ( renderTargetContext === null ) {

			supportsDepth = renderer.depth;
			supportsStencil = renderer.stencil;

			const descriptor = this._getDefaultRenderPassDescriptor();

			if ( color ) {

				colorAttachments = descriptor.colorAttachments;

				const colorAttachment = colorAttachments[ 0 ];

				colorAttachment.clearValue = clearValue;
				colorAttachment.loadOp = GPULoadOp.Clear;
				colorAttachment.storeOp = GPUStoreOp.Store;

			}

			if ( supportsDepth || supportsStencil ) {

				depthStencilAttachment = descriptor.depthStencilAttachment;

			}

		} else {

			supportsDepth = renderTargetContext.depth;
			supportsStencil = renderTargetContext.stencil;

			const clearConfig = {
				loadOp: color ? GPULoadOp.Clear : GPULoadOp.Load,
				clearValue: color ? clearValue : undefined
			};

			if ( supportsDepth ) {

				clearConfig.depthLoadOp = depth ? GPULoadOp.Clear : GPULoadOp.Load;
				clearConfig.depthClearValue = depth ? renderer.getClearDepth() : undefined;
				clearConfig.depthStoreOp = GPUStoreOp.Store;

			}

			if ( supportsStencil ) {

				clearConfig.stencilLoadOp = stencil ? GPULoadOp.Clear : GPULoadOp.Load;
				clearConfig.stencilClearValue = stencil ? renderer.getClearStencil() : undefined;
				clearConfig.stencilStoreOp = GPUStoreOp.Store;

			}

			const descriptor = this._getRenderPassDescriptor( renderTargetContext, clearConfig );

			colorAttachments = descriptor.colorAttachments;
			depthStencilAttachment = descriptor.depthStencilAttachment;

		}

		if ( supportsDepth && depthStencilAttachment ) {

			if ( depth ) {

				depthStencilAttachment.depthLoadOp = GPULoadOp.Clear;
				depthStencilAttachment.depthClearValue = renderer.getClearDepth();
				depthStencilAttachment.depthStoreOp = GPUStoreOp.Store;

			} else {

				depthStencilAttachment.depthLoadOp = GPULoadOp.Load;
				depthStencilAttachment.depthStoreOp = GPUStoreOp.Store;

			}

		}

		//

		if ( supportsStencil && depthStencilAttachment ) {

			if ( stencil ) {

				depthStencilAttachment.stencilLoadOp = GPULoadOp.Clear;
				depthStencilAttachment.stencilClearValue = renderer.getClearStencil();
				depthStencilAttachment.stencilStoreOp = GPUStoreOp.Store;

			} else {

				depthStencilAttachment.stencilLoadOp = GPULoadOp.Load;
				depthStencilAttachment.stencilStoreOp = GPUStoreOp.Store;

			}

		}

		//

		const encoder = device.createCommandEncoder( { label: 'clear' } );
		const currentPass = encoder.beginRenderPass( {
			colorAttachments,
			depthStencilAttachment
		} );

		currentPass.end();

		device.queue.submit( [ encoder.finish() ] );

	}
```
</details>

##### `beginCompute(computeGroup: Node | Node[]): void`

<details><summary>Code</summary>

```ts
beginCompute( computeGroup ) {

		const groupGPU = this.get( computeGroup );

		const descriptor = {
			label: 'computeGroup_' + computeGroup.id
		};

		this.initTimestampQuery( computeGroup, descriptor );

		groupGPU.cmdEncoderGPU = this.device.createCommandEncoder( { label: 'computeGroup_' + computeGroup.id } );

		groupGPU.passEncoderGPU = groupGPU.cmdEncoderGPU.beginComputePass( descriptor );

	}
```
</details>

##### `compute(computeGroup: Node | Node[], computeNode: Node, bindings: BindGroup[], pipeline: ComputePipeline, dispatchSizeOrCount: number | number[]): void`

<details><summary>Code</summary>

```ts
compute( computeGroup, computeNode, bindings, pipeline, dispatchSizeOrCount = null ) {

		const computeNodeData = this.get( computeNode );
		const { passEncoderGPU } = this.get( computeGroup );

		// pipeline

		const pipelineGPU = this.get( pipeline ).pipeline;

		this.pipelineUtils.setPipeline( passEncoderGPU, pipelineGPU );

		// bind groups

		for ( let i = 0, l = bindings.length; i < l; i ++ ) {

			const bindGroup = bindings[ i ];
			const bindingsData = this.get( bindGroup );

			passEncoderGPU.setBindGroup( i, bindingsData.group );

		}

		let dispatchSize;

		if ( dispatchSizeOrCount === null ) {

			dispatchSizeOrCount = computeNode.count;

		}

		if ( typeof dispatchSizeOrCount === 'number' ) {

			// If a single number is given, we calculate the dispatch size based on the workgroup size

			const count = dispatchSizeOrCount;

			if ( computeNodeData.dispatchSize === undefined || computeNodeData.count !== count ) {

				// cache dispatch size to avoid recalculating it every time

				computeNodeData.dispatchSize = [ 0, 1, 1 ];
				computeNodeData.count = count;

				const workgroupSize = computeNode.workgroupSize;

				let size = workgroupSize[ 0 ];

				for ( let i = 1; i < workgroupSize.length; i ++ )
					size *= workgroupSize[ i ];

				const dispatchCount = Math.ceil( count / size );

				//

				const maxComputeWorkgroupsPerDimension = this.device.limits.maxComputeWorkgroupsPerDimension;

				dispatchSize = [ dispatchCount, 1, 1 ];

				if ( dispatchCount > maxComputeWorkgroupsPerDimension ) {

					dispatchSize[ 0 ] = Math.min( dispatchCount, maxComputeWorkgroupsPerDimension );
					dispatchSize[ 1 ] = Math.ceil( dispatchCount / maxComputeWorkgroupsPerDimension );

				}

				computeNodeData.dispatchSize = dispatchSize;

			}

			dispatchSize = computeNodeData.dispatchSize;

		} else {

			dispatchSize = dispatchSizeOrCount;

		}

		//

		passEncoderGPU.dispatchWorkgroups(
			dispatchSize[ 0 ],
			dispatchSize[ 1 ] || 1,
			dispatchSize[ 2 ] || 1
		);

	}
```
</details>

##### `finishCompute(computeGroup: Node | Node[]): void`

<details><summary>Code</summary>

```ts
finishCompute( computeGroup ) {

		const groupData = this.get( computeGroup );

		groupData.passEncoderGPU.end();

		this.device.queue.submit( [ groupData.cmdEncoderGPU.finish() ] );

	}
```
</details>

##### `waitForGPU(): Promise<any>`

<details><summary>Code</summary>

```ts
async waitForGPU() {

		await this.device.queue.onSubmittedWorkDone();

	}
```
</details>

##### `draw(renderObject: RenderObject, info: Info): void`

<details><summary>Code</summary>

```ts
draw( renderObject, info ) {

		const { object, material, context, pipeline } = renderObject;
		const bindings = renderObject.getBindings();
		const renderContextData = this.get( context );
		const pipelineGPU = this.get( pipeline ).pipeline;

		const index = renderObject.getIndex();
		const hasIndex = ( index !== null );


		const drawParams = renderObject.getDrawParameters();
		if ( drawParams === null ) return;

		// pipeline

		const setPipelineAndBindings = ( passEncoderGPU, currentSets ) => {

			// pipeline
			this.pipelineUtils.setPipeline( passEncoderGPU, pipelineGPU );
			currentSets.pipeline = pipelineGPU;

			// bind groups
			const currentBindingGroups = currentSets.bindingGroups;
			for ( let i = 0, l = bindings.length; i < l; i ++ ) {

				const bindGroup = bindings[ i ];
				const bindingsData = this.get( bindGroup );
				if ( currentBindingGroups[ bindGroup.index ] !== bindGroup.id ) {

					passEncoderGPU.setBindGroup( bindGroup.index, bindingsData.group );
					currentBindingGroups[ bindGroup.index ] = bindGroup.id;

				}

			}

			// attributes

			// index

			if ( hasIndex === true ) {

				if ( currentSets.index !== index ) {

					const buffer = this.get( index ).buffer;
					const indexFormat = ( index.array instanceof Uint16Array ) ? GPUIndexFormat.Uint16 : GPUIndexFormat.Uint32;

					passEncoderGPU.setIndexBuffer( buffer, indexFormat );

					currentSets.index = index;

				}

			}
			// vertex buffers

			const vertexBuffers = renderObject.getVertexBuffers();

			for ( let i = 0, l = vertexBuffers.length; i < l; i ++ ) {

				const vertexBuffer = vertexBuffers[ i ];

				if ( currentSets.attributes[ i ] !== vertexBuffer ) {

					const buffer = this.get( vertexBuffer ).buffer;
					passEncoderGPU.setVertexBuffer( i, buffer );

					currentSets.attributes[ i ] = vertexBuffer;

				}

			}
			// stencil

			if ( context.stencil === true && material.stencilWrite === true && renderContextData.currentStencilRef !== material.stencilRef ) {

				passEncoderGPU.setStencilReference( material.stencilRef );
				renderContextData.currentStencilRef = material.stencilRef;

			}


		};

		// Define draw function
		const draw = ( passEncoderGPU, currentSets ) => {

			setPipelineAndBindings( passEncoderGPU, currentSets );

			if ( object.isBatchedMesh === true ) {

				const starts = object._multiDrawStarts;
				const counts = object._multiDrawCounts;
				const drawCount = object._multiDrawCount;
				const drawInstances = object._multiDrawInstances;

				if ( drawInstances !== null ) {

					// @deprecated, r174
					warnOnce( 'THREE.WebGPUBackend: renderMultiDrawInstances has been deprecated and will be removed in r184. Append to renderMultiDraw arguments and use indirection.' );

				}

				for ( let i = 0; i < drawCount; i ++ ) {

					const count = drawInstances ? drawInstances[ i ] : 1;
					const firstInstance = count > 1 ? 0 : i;

					if ( hasIndex === true ) {

						passEncoderGPU.drawIndexed( counts[ i ], count, starts[ i ] / index.array.BYTES_PER_ELEMENT, 0, firstInstance );

					} else {

						passEncoderGPU.draw( counts[ i ], count, starts[ i ], firstInstance );

					}

					info.update( object, counts[ i ], count );

				}

			} else if ( hasIndex === true ) {

				const { vertexCount: indexCount, instanceCount, firstVertex: firstIndex } = drawParams;

				const indirect = renderObject.getIndirect();

				if ( indirect !== null ) {

					const buffer = this.get( indirect ).buffer;

					passEncoderGPU.drawIndexedIndirect( buffer, 0 );

				} else {

					passEncoderGPU.drawIndexed( indexCount, instanceCount, firstIndex, 0, 0 );

				}

				info.update( object, indexCount, instanceCount );

			} else {

				const { vertexCount, instanceCount, firstVertex } = drawParams;

				const indirect = renderObject.getIndirect();

				if ( indirect !== null ) {

					const buffer = this.get( indirect ).buffer;

					passEncoderGPU.drawIndirect( buffer, 0 );

				} else {

					passEncoderGPU.draw( vertexCount, instanceCount, firstVertex, 0 );

				}

				info.update( object, vertexCount, instanceCount );

			}

		};

		if ( renderObject.camera.isArrayCamera && renderObject.camera.cameras.length > 0 ) {

			const cameraData = this.get( renderObject.camera );
			const cameras = renderObject.camera.cameras;
			const cameraIndex = renderObject.getBindingGroup( 'cameraIndex' );

			if ( cameraData.indexesGPU === undefined || cameraData.indexesGPU.length !== cameras.length ) {

				const bindingsData = this.get( cameraIndex );
				const indexesGPU = [];

				const data = new Uint32Array( [ 0, 0, 0, 0 ] );

				for ( let i = 0, len = cameras.length; i < len; i ++ ) {

					data[ 0 ] = i;

					const bindGroupIndex = this.bindingUtils.createBindGroupIndex( data, bindingsData.layout );

					indexesGPU.push( bindGroupIndex );

				}

				cameraData.indexesGPU = indexesGPU; // TODO: Create a global library for this

			}

			const pixelRatio = this.renderer.getPixelRatio();

			for ( let i = 0, len = cameras.length; i < len; i ++ ) {

				const subCamera = cameras[ i ];

				if ( object.layers.test( subCamera.layers ) ) {

					const vp = subCamera.viewport;



					let pass = renderContextData.currentPass;
					let sets = renderContextData.currentSets;
					if ( renderContextData.bundleEncoders ) {

						const bundleEncoder = renderContextData.bundleEncoders[ i ];
						const bundleSets = renderContextData.bundleSets[ i ];
						pass = bundleEncoder;
						sets = bundleSets;

					}



					if ( vp ) {

						pass.setViewport(
							Math.floor( vp.x * pixelRatio ),
							Math.floor( vp.y * pixelRatio ),
							Math.floor( vp.width * pixelRatio ),
							Math.floor( vp.height * pixelRatio ),
							context.viewportValue.minDepth,
							context.viewportValue.maxDepth
						);

					}


					// Set camera index binding for this layer
					if ( cameraIndex && cameraData.indexesGPU ) {

						pass.setBindGroup( cameraIndex.index, cameraData.indexesGPU[ i ] );
						sets.bindingGroups[ cameraIndex.index ] = cameraIndex.id;

					}

					draw( pass, sets );


				}

			}

		} else {

			// Regular single camera rendering
			if ( renderContextData.currentPass ) {

				// Handle occlusion queries
				if ( renderContextData.occlusionQuerySet !== undefined ) {

					const lastObject = renderContextData.lastOcclusionObject;
					if ( lastObject !== object ) {

						if ( lastObject !== null && lastObject.occlusionTest === true ) {

							renderContextData.currentPass.endOcclusionQuery();
							renderContextData.occlusionQueryIndex ++;

						}

						if ( object.occlusionTest === true ) {

							renderContextData.currentPass.beginOcclusionQuery( renderContextData.occlusionQueryIndex );
							renderContextData.occlusionQueryObjects[ renderContextData.occlusionQueryIndex ] = object;

						}

						renderContextData.lastOcclusionObject = object;

					}

				}

				draw( renderContextData.currentPass, renderContextData.currentSets );

			}

		}

	}
```
</details>

##### `needsRenderUpdate(renderObject: RenderObject): boolean`

<details><summary>Code</summary>

```ts
needsRenderUpdate( renderObject ) {

		const data = this.get( renderObject );

		const { object, material } = renderObject;

		const utils = this.utils;

		const sampleCount = utils.getSampleCountRenderContext( renderObject.context );
		const colorSpace = utils.getCurrentColorSpace( renderObject.context );
		const colorFormat = utils.getCurrentColorFormat( renderObject.context );
		const depthStencilFormat = utils.getCurrentDepthStencilFormat( renderObject.context );
		const primitiveTopology = utils.getPrimitiveTopology( object, material );

		let needsUpdate = false;

		if ( data.material !== material || data.materialVersion !== material.version ||
			data.transparent !== material.transparent || data.blending !== material.blending || data.premultipliedAlpha !== material.premultipliedAlpha ||
			data.blendSrc !== material.blendSrc || data.blendDst !== material.blendDst || data.blendEquation !== material.blendEquation ||
			data.blendSrcAlpha !== material.blendSrcAlpha || data.blendDstAlpha !== material.blendDstAlpha || data.blendEquationAlpha !== material.blendEquationAlpha ||
			data.colorWrite !== material.colorWrite || data.depthWrite !== material.depthWrite || data.depthTest !== material.depthTest || data.depthFunc !== material.depthFunc ||
			data.stencilWrite !== material.stencilWrite || data.stencilFunc !== material.stencilFunc ||
			data.stencilFail !== material.stencilFail || data.stencilZFail !== material.stencilZFail || data.stencilZPass !== material.stencilZPass ||
			data.stencilFuncMask !== material.stencilFuncMask || data.stencilWriteMask !== material.stencilWriteMask ||
			data.side !== material.side || data.alphaToCoverage !== material.alphaToCoverage ||
			data.sampleCount !== sampleCount || data.colorSpace !== colorSpace ||
			data.colorFormat !== colorFormat || data.depthStencilFormat !== depthStencilFormat ||
			data.primitiveTopology !== primitiveTopology ||
			data.clippingContextCacheKey !== renderObject.clippingContextCacheKey
		) {

			data.material = material; data.materialVersion = material.version;
			data.transparent = material.transparent; data.blending = material.blending; data.premultipliedAlpha = material.premultipliedAlpha;
			data.blendSrc = material.blendSrc; data.blendDst = material.blendDst; data.blendEquation = material.blendEquation;
			data.blendSrcAlpha = material.blendSrcAlpha; data.blendDstAlpha = material.blendDstAlpha; data.blendEquationAlpha = material.blendEquationAlpha;
			data.colorWrite = material.colorWrite;
			data.depthWrite = material.depthWrite; data.depthTest = material.depthTest; data.depthFunc = material.depthFunc;
			data.stencilWrite = material.stencilWrite; data.stencilFunc = material.stencilFunc;
			data.stencilFail = material.stencilFail; data.stencilZFail = material.stencilZFail; data.stencilZPass = material.stencilZPass;
			data.stencilFuncMask = material.stencilFuncMask; data.stencilWriteMask = material.stencilWriteMask;
			data.side = material.side; data.alphaToCoverage = material.alphaToCoverage;
			data.sampleCount = sampleCount;
			data.colorSpace = colorSpace;
			data.colorFormat = colorFormat;
			data.depthStencilFormat = depthStencilFormat;
			data.primitiveTopology = primitiveTopology;
			data.clippingContextCacheKey = renderObject.clippingContextCacheKey;

			needsUpdate = true;

		}

		return needsUpdate;

	}
```
</details>

##### `getRenderCacheKey(renderObject: RenderObject): string`

<details><summary>Code</summary>

```ts
getRenderCacheKey( renderObject ) {

		const { object, material } = renderObject;

		const utils = this.utils;
		const renderContext = renderObject.context;

		return [
			material.transparent, material.blending, material.premultipliedAlpha,
			material.blendSrc, material.blendDst, material.blendEquation,
			material.blendSrcAlpha, material.blendDstAlpha, material.blendEquationAlpha,
			material.colorWrite,
			material.depthWrite, material.depthTest, material.depthFunc,
			material.stencilWrite, material.stencilFunc,
			material.stencilFail, material.stencilZFail, material.stencilZPass,
			material.stencilFuncMask, material.stencilWriteMask,
			material.side,
			utils.getSampleCountRenderContext( renderContext ),
			utils.getCurrentColorSpace( renderContext ), utils.getCurrentColorFormat( renderContext ), utils.getCurrentDepthStencilFormat( renderContext ),
			utils.getPrimitiveTopology( object, material ),
			renderObject.getGeometryCacheKey(),
			renderObject.clippingContextCacheKey
		].join();

	}
```
</details>

##### `createSampler(texture: Texture): void`

<details><summary>Code</summary>

```ts
createSampler( texture ) {

		this.textureUtils.createSampler( texture );

	}
```
</details>

##### `destroySampler(texture: Texture): void`

<details><summary>Code</summary>

```ts
destroySampler( texture ) {

		this.textureUtils.destroySampler( texture );

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

##### `initTimestampQuery(renderContext: RenderContext, descriptor: any): void`

<details><summary>Code</summary>

```ts
initTimestampQuery( renderContext, descriptor ) {

		if ( ! this.trackTimestamp ) return;

		const type = renderContext.isComputeNode ? 'compute' : 'render';

		if ( ! this.timestampQueryPool[ type ] ) {

			// TODO: Variable maxQueries?
			this.timestampQueryPool[ type ] = new WebGPUTimestampQueryPool( this.device, type, 2048 );

		}

		const timestampQueryPool = this.timestampQueryPool[ type ];

		const baseOffset = timestampQueryPool.allocateQueriesForContext( renderContext );

		descriptor.timestampWrites = {
			querySet: timestampQueryPool.querySet,
			beginningOfPassWriteIndex: baseOffset,
			endOfPassWriteIndex: baseOffset + 1,
		  };

	}
```
</details>

##### `createNodeBuilder(object: RenderObject, renderer: Renderer): WGSLNodeBuilder`

<details><summary>Code</summary>

```ts
createNodeBuilder( object, renderer ) {

		return new WGSLNodeBuilder( object, renderer );

	}
```
</details>

##### `createProgram(program: ProgrammableStage): void`

<details><summary>Code</summary>

```ts
createProgram( program ) {

		const programGPU = this.get( program );

		programGPU.module = {
			module: this.device.createShaderModule( { code: program.code, label: program.stage + ( program.name !== '' ? `_${ program.name }` : '' ) } ),
			entryPoint: 'main'
		};

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

		this.pipelineUtils.createRenderPipeline( renderObject, promises );

	}
```
</details>

##### `createComputePipeline(computePipeline: ComputePipeline, bindings: BindGroup[]): void`

<details><summary>Code</summary>

```ts
createComputePipeline( computePipeline, bindings ) {

		this.pipelineUtils.createComputePipeline( computePipeline, bindings );

	}
```
</details>

##### `beginBundle(renderContext: RenderContext): void`

<details><summary>Code</summary>

```ts
beginBundle( renderContext ) {

		const renderContextData = this.get( renderContext );

		renderContextData._currentPass = renderContextData.currentPass;
		renderContextData._currentSets = renderContextData.currentSets;

		renderContextData.currentSets = { attributes: {}, bindingGroups: [], pipeline: null, index: null };
		renderContextData.currentPass = this.pipelineUtils.createBundleEncoder( renderContext );

	}
```
</details>

##### `finishBundle(renderContext: RenderContext, bundle: RenderBundle): void`

<details><summary>Code</summary>

```ts
finishBundle( renderContext, bundle ) {

		const renderContextData = this.get( renderContext );

		const bundleEncoder = renderContextData.currentPass;
		const bundleGPU = bundleEncoder.finish();

		this.get( bundle ).bundleGPU = bundleGPU;

		// restore render pass state

		renderContextData.currentSets = renderContextData._currentSets;
		renderContextData.currentPass = renderContextData._currentPass;

	}
```
</details>

##### `addBundle(renderContext: RenderContext, bundle: RenderBundle): void`

<details><summary>Code</summary>

```ts
addBundle( renderContext, bundle ) {

		const renderContextData = this.get( renderContext );

		renderContextData.renderBundles.push( this.get( bundle ).bundleGPU );

	}
```
</details>

##### `createBindings(bindGroup: BindGroup, bindings: BindGroup[], cacheIndex: number, version: number): void`

<details><summary>Code</summary>

```ts
createBindings( bindGroup, bindings, cacheIndex, version ) {

		this.bindingUtils.createBindings( bindGroup, bindings, cacheIndex, version );

	}
```
</details>

##### `updateBindings(bindGroup: BindGroup, bindings: BindGroup[], cacheIndex: number, version: number): void`

<details><summary>Code</summary>

```ts
updateBindings( bindGroup, bindings, cacheIndex, version ) {

		this.bindingUtils.createBindings( bindGroup, bindings, cacheIndex, version );

	}
```
</details>

##### `updateBinding(binding: Buffer<ArrayBufferLike>): void`

<details><summary>Code</summary>

```ts
updateBinding( binding ) {

		this.bindingUtils.updateBinding( binding );

	}
```
</details>

##### `createIndexAttribute(attribute: BufferAttribute): void`

<details><summary>Code</summary>

```ts
createIndexAttribute( attribute ) {

		let usage = GPUBufferUsage.INDEX | GPUBufferUsage.COPY_SRC | GPUBufferUsage.COPY_DST;

		if ( attribute.isStorageBufferAttribute || attribute.isStorageInstancedBufferAttribute ) {

			usage |= GPUBufferUsage.STORAGE;

		}

		this.attributeUtils.createAttribute( attribute, usage );

	}
```
</details>

##### `createAttribute(attribute: BufferAttribute): void`

<details><summary>Code</summary>

```ts
createAttribute( attribute ) {

		this.attributeUtils.createAttribute( attribute, GPUBufferUsage.VERTEX | GPUBufferUsage.COPY_SRC | GPUBufferUsage.COPY_DST );

	}
```
</details>

##### `createStorageAttribute(attribute: BufferAttribute): void`

<details><summary>Code</summary>

```ts
createStorageAttribute( attribute ) {

		this.attributeUtils.createAttribute( attribute, GPUBufferUsage.STORAGE | GPUBufferUsage.VERTEX | GPUBufferUsage.COPY_SRC | GPUBufferUsage.COPY_DST );

	}
```
</details>

##### `createIndirectStorageAttribute(attribute: BufferAttribute): void`

<details><summary>Code</summary>

```ts
createIndirectStorageAttribute( attribute ) {

		this.attributeUtils.createAttribute( attribute, GPUBufferUsage.STORAGE | GPUBufferUsage.INDIRECT | GPUBufferUsage.COPY_SRC | GPUBufferUsage.COPY_DST );

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

##### `updateSize(): void`

<details><summary>Code</summary>

```ts
updateSize() {

		this.colorBuffer = this.textureUtils.getColorBuffer();
		this.defaultRenderPassdescriptor = null;

	}
```
</details>

##### `getMaxAnisotropy(): number`

<details><summary>Code</summary>

```ts
getMaxAnisotropy() {

		return 16;

	}
```
</details>

##### `hasFeature(name: string): boolean`

<details><summary>Code</summary>

```ts
hasFeature( name ) {

		return this.device.features.has( name );

	}
```
</details>

##### `copyTextureToTexture(srcTexture: Texture, dstTexture: Texture, srcRegion: any, dstPosition: any, srcLevel: number, dstLevel: number): void`

<details><summary>Code</summary>

```ts
copyTextureToTexture( srcTexture, dstTexture, srcRegion = null, dstPosition = null, srcLevel = 0, dstLevel = 0 ) {

		let dstX = 0;
		let dstY = 0;
		let dstZ = 0;

		let srcX = 0;
		let srcY = 0;
		let srcZ = 0;

		let srcWidth = srcTexture.image.width;
		let srcHeight = srcTexture.image.height;
		let srcDepth = 1;


		if ( srcRegion !== null ) {

			if ( srcRegion.isBox3 === true ) {

				srcX = srcRegion.min.x;
				srcY = srcRegion.min.y;
				srcZ = srcRegion.min.z;
				srcWidth = srcRegion.max.x - srcRegion.min.x;
				srcHeight = srcRegion.max.y - srcRegion.min.y;
				srcDepth = srcRegion.max.z - srcRegion.min.z;

			} else {

				// Assume it's a Box2
				srcX = srcRegion.min.x;
				srcY = srcRegion.min.y;
				srcWidth = srcRegion.max.x - srcRegion.min.x;
				srcHeight = srcRegion.max.y - srcRegion.min.y;
				srcDepth = 1;

			}

		}


		if ( dstPosition !== null ) {

			dstX = dstPosition.x;
			dstY = dstPosition.y;
			dstZ = dstPosition.z || 0;

		}

		const encoder = this.device.createCommandEncoder( { label: 'copyTextureToTexture_' + srcTexture.id + '_' + dstTexture.id } );

		const sourceGPU = this.get( srcTexture ).texture;
		const destinationGPU = this.get( dstTexture ).texture;

		encoder.copyTextureToTexture(
			{
				texture: sourceGPU,
				mipLevel: srcLevel,
				origin: { x: srcX, y: srcY, z: srcZ }
			},
			{
				texture: destinationGPU,
				mipLevel: dstLevel,
				origin: { x: dstX, y: dstY, z: dstZ }
			},
			[
				srcWidth,
				srcHeight,
				srcDepth
			]
		);

		this.device.queue.submit( [ encoder.finish() ] );

		if ( dstLevel === 0 && dstTexture.generateMipmaps ) {

			this.textureUtils.generateMipmaps( dstTexture );

		}

	}
```
</details>

##### `copyFramebufferToTexture(texture: Texture, renderContext: RenderContext, rectangle: Vector4): void`

<details><summary>Code</summary>

```ts
copyFramebufferToTexture( texture, renderContext, rectangle ) {

		const renderContextData = this.get( renderContext );

		let sourceGPU = null;

		if ( renderContext.renderTarget ) {

			if ( texture.isDepthTexture ) {

				sourceGPU = this.get( renderContext.depthTexture ).texture;

			} else {

				sourceGPU = this.get( renderContext.textures[ 0 ] ).texture;

			}

		} else {

			if ( texture.isDepthTexture ) {

				sourceGPU = this.textureUtils.getDepthBuffer( renderContext.depth, renderContext.stencil );

			} else {

				sourceGPU = this.context.getCurrentTexture();

			}

		}

		const destinationGPU = this.get( texture ).texture;

		if ( sourceGPU.format !== destinationGPU.format ) {

			console.error( 'WebGPUBackend: copyFramebufferToTexture: Source and destination formats do not match.', sourceGPU.format, destinationGPU.format );

			return;

		}

		let encoder;

		if ( renderContextData.currentPass ) {

			renderContextData.currentPass.end();

			encoder = renderContextData.encoder;

		} else {

			encoder = this.device.createCommandEncoder( { label: 'copyFramebufferToTexture_' + texture.id } );

		}

		encoder.copyTextureToTexture(
			{
				texture: sourceGPU,
				origin: [ rectangle.x, rectangle.y, 0 ],
			},
			{
				texture: destinationGPU
			},
			[
				rectangle.z,
				rectangle.w
			]
		);

		if ( renderContextData.currentPass ) {

			const { descriptor } = renderContextData;

			for ( let i = 0; i < descriptor.colorAttachments.length; i ++ ) {

				descriptor.colorAttachments[ i ].loadOp = GPULoadOp.Load;

			}

			if ( renderContext.depth ) descriptor.depthStencilAttachment.depthLoadOp = GPULoadOp.Load;
			if ( renderContext.stencil ) descriptor.depthStencilAttachment.stencilLoadOp = GPULoadOp.Load;

			renderContextData.currentPass = encoder.beginRenderPass( descriptor );
			renderContextData.currentSets = { attributes: {}, bindingGroups: [], pipeline: null, index: null };

			if ( renderContext.viewport ) {

				this.updateViewport( renderContext );

			}

			if ( renderContext.scissor ) {

				const { x, y, width, height } = renderContext.scissorValue;

				renderContextData.currentPass.setScissorRect( x, y, width, height );

			}

		} else {

			this.device.queue.submit( [ encoder.finish() ] );

		}

		if ( texture.generateMipmaps ) {

			this.textureUtils.generateMipmaps( texture );

		}

	}
```
</details>


---