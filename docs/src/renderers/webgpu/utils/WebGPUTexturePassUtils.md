[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `WebGPUTexturePassUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgpu/utils/WebGPUTexturePassUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DataMap` | `../../common/DataMap.js` |
| `GPUTextureViewDimension` | `./WebGPUConstants.js` |
| `GPUIndexFormat` | `./WebGPUConstants.js` |
| `GPUFilterMode` | `./WebGPUConstants.js` |
| `GPUPrimitiveTopology` | `./WebGPUConstants.js` |
| `GPULoadOp` | `./WebGPUConstants.js` |
| `GPUStoreOp` | `./WebGPUConstants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `mipmapVertexSource` | `"\nstruct VarysStruct {\n\t@builtin( ...` | let/var | `` struct VarysStruct { @builtin( position ) Position: vec4<f32>, @location( 0...` | ✗ |
| `mipmapFragmentSource` | `"\n@group( 0 ) @binding( 0 )\nvar img...` | let/var | `` @group( 0 ) @binding( 0 ) var imgSampler : sampler; @group( 0 ) @binding( 1...` | ✗ |
| `flipYFragmentSource` | `"\n@group( 0 ) @binding( 0 )\nvar img...` | let/var | `` @group( 0 ) @binding( 0 ) var imgSampler : sampler; @group( 0 ) @binding( 1...` | ✗ |
| `pipeline` | `GPURenderPipeline` | let/var | `this.transferPipelines[ format ]` | ✗ |
| `pipeline` | `GPURenderPipeline` | let/var | `this.flipYPipelines[ format ]` | ✗ |
| `format` | `any` | let/var | `textureGPUDescriptor.format` | ✗ |
| `passes` | `any` | let/var | `textureData.layers[ baseArrayLayer ] \|\| this._mipmapCreateBundles( textureG...` | ✗ |
| `passes` | `any[]` | let/var | `[]` | ✗ |
| `passDescriptor` | `{ colorAttachments: { view: any; load...` | let/var | `{ colorAttachments: [ { view: dstView, loadOp: GPULoadOp.Clear, storeOp: GPUS...` | ✗ |
| `levels` | `number` | let/var | `passes.length` | ✗ |
| `pass` | `any` | let/var | `passes[ i ]` | ✗ |


---

## Functions

### `WebGPUTexturePassUtils.getTransferPipeline(format: string): GPURenderPipeline`

**JSDoc:**
```typescript
/**
	 * Returns a render pipeline for the internal copy render pass. The pass
	 * requires a unique render pipeline for each texture format.
	 *
	 * @param {string} format - The GPU texture format
	 * @return {GPURenderPipeline} The GPU render pipeline.
	 */
```

**Parameters:**

- **`format`** `string`

**Returns:** `GPURenderPipeline`

**Calls:**

- `this.device.createRenderPipeline`

<details><summary>Code</summary>

```typescript
getTransferPipeline( format ) {

		let pipeline = this.transferPipelines[ format ];

		if ( pipeline === undefined ) {

			pipeline = this.device.createRenderPipeline( {
				label: `mipmap-${ format }`,
				vertex: {
					module: this.mipmapVertexShaderModule,
					entryPoint: 'main'
				},
				fragment: {
					module: this.mipmapFragmentShaderModule,
					entryPoint: 'main',
					targets: [ { format } ]
				},
				primitive: {
					topology: GPUPrimitiveTopology.TriangleStrip,
					stripIndexFormat: GPUIndexFormat.Uint32
				},
				layout: 'auto'
			} );

			this.transferPipelines[ format ] = pipeline;

		}

		return pipeline;

	}
```
</details>

### `WebGPUTexturePassUtils.getFlipYPipeline(format: string): GPURenderPipeline`

**JSDoc:**
```typescript
/**
	 * Returns a render pipeline for the flipY render pass. The pass
	 * requires a unique render pipeline for each texture format.
	 *
	 * @param {string} format - The GPU texture format
	 * @return {GPURenderPipeline} The GPU render pipeline.
	 */
```

**Parameters:**

- **`format`** `string`

**Returns:** `GPURenderPipeline`

**Calls:**

- `this.device.createRenderPipeline`

<details><summary>Code</summary>

```typescript
getFlipYPipeline( format ) {

		let pipeline = this.flipYPipelines[ format ];

		if ( pipeline === undefined ) {

			pipeline = this.device.createRenderPipeline( {
				label: `flipY-${ format }`,
				vertex: {
					module: this.mipmapVertexShaderModule,
					entryPoint: 'main'
				},
				fragment: {
					module: this.flipYFragmentShaderModule,
					entryPoint: 'main',
					targets: [ { format } ]
				},
				primitive: {
					topology: GPUPrimitiveTopology.TriangleStrip,
					stripIndexFormat: GPUIndexFormat.Uint32
				},
				layout: 'auto'
			} );

			this.flipYPipelines[ format ] = pipeline;

		}

		return pipeline;

	}
```
</details>

### `WebGPUTexturePassUtils.flipY(textureGPU: GPUTexture, textureGPUDescriptor: any, baseArrayLayer: number): void`

**JSDoc:**
```typescript
/**
	 * Flip the contents of the given GPU texture along its vertical axis.
	 *
	 * @param {GPUTexture} textureGPU - The GPU texture object.
	 * @param {Object} textureGPUDescriptor - The texture descriptor.
	 * @param {number} [baseArrayLayer=0] - The index of the first array layer accessible to the texture view.
	 */
```

**Parameters:**

- **`textureGPU`** `GPUTexture`
- **`textureGPUDescriptor`** `any`
- **`baseArrayLayer`** `number`

**Returns:** `void`

**Calls:**

- `this.getTransferPipeline`
- `this.getFlipYPipeline`
- `this.device.createTexture`
- `textureGPU.createView`
- `tempTexture.createView`
- `this.device.createCommandEncoder`
- `pipeline.getBindGroupLayout`
- `this.device.createBindGroup`
- `commandEncoder.beginRenderPass`
- `passEncoder.setPipeline`
- `passEncoder.setBindGroup`
- `passEncoder.draw`
- `passEncoder.end`
- `pass`
- `this.device.queue.submit`
- `commandEncoder.finish`
- `tempTexture.destroy`

<details><summary>Code</summary>

```typescript
flipY( textureGPU, textureGPUDescriptor, baseArrayLayer = 0 ) {

		const format = textureGPUDescriptor.format;
		const { width, height } = textureGPUDescriptor.size;

		const transferPipeline = this.getTransferPipeline( format );
		const flipYPipeline = this.getFlipYPipeline( format );

		const tempTexture = this.device.createTexture( {
			size: { width, height, depthOrArrayLayers: 1 },
			format,
			usage: GPUTextureUsage.RENDER_ATTACHMENT | GPUTextureUsage.TEXTURE_BINDING
		} );

		const srcView = textureGPU.createView( {
			baseMipLevel: 0,
			mipLevelCount: 1,
			dimension: GPUTextureViewDimension.TwoD,
			baseArrayLayer
		} );

		const dstView = tempTexture.createView( {
			baseMipLevel: 0,
			mipLevelCount: 1,
			dimension: GPUTextureViewDimension.TwoD,
			baseArrayLayer: 0
		} );

		const commandEncoder = this.device.createCommandEncoder( {} );

		const pass = ( pipeline, sourceView, destinationView ) => {

			const bindGroupLayout = pipeline.getBindGroupLayout( 0 ); // @TODO: Consider making this static.

			const bindGroup = this.device.createBindGroup( {
				layout: bindGroupLayout,
				entries: [ {
					binding: 0,
					resource: this.flipYSampler
				}, {
					binding: 1,
					resource: sourceView
				} ]
			} );

			const passEncoder = commandEncoder.beginRenderPass( {
				colorAttachments: [ {
					view: destinationView,
					loadOp: GPULoadOp.Clear,
					storeOp: GPUStoreOp.Store,
					clearValue: [ 0, 0, 0, 0 ]
				} ]
			} );

			passEncoder.setPipeline( pipeline );
			passEncoder.setBindGroup( 0, bindGroup );
			passEncoder.draw( 4, 1, 0, 0 );
			passEncoder.end();

		};

		pass( transferPipeline, srcView, dstView );
		pass( flipYPipeline, dstView, srcView );

		this.device.queue.submit( [ commandEncoder.finish() ] );

		tempTexture.destroy();

	}
```
</details>

### `WebGPUTexturePassUtils.generateMipmaps(textureGPU: GPUTexture, textureGPUDescriptor: any, baseArrayLayer: number): void`

**JSDoc:**
```typescript
/**
	 * Generates mipmaps for the given GPU texture.
	 *
	 * @param {GPUTexture} textureGPU - The GPU texture object.
	 * @param {Object} textureGPUDescriptor - The texture descriptor.
	 * @param {number} [baseArrayLayer=0] - The index of the first array layer accessible to the texture view.
	 */
```

**Parameters:**

- **`textureGPU`** `GPUTexture`
- **`textureGPUDescriptor`** `any`
- **`baseArrayLayer`** `number`

**Returns:** `void`

**Calls:**

- `this.get`
- `this._mipmapCreateBundles`
- `this.device.createCommandEncoder`
- `this._mipmapRunBundles`
- `this.device.queue.submit`
- `commandEncoder.finish`

<details><summary>Code</summary>

```typescript
generateMipmaps( textureGPU, textureGPUDescriptor, baseArrayLayer = 0 ) {

		const textureData = this.get( textureGPU );

		if ( textureData.useCount === undefined ) {

			textureData.useCount = 0;
			textureData.layers = [];

		}

		const passes = textureData.layers[ baseArrayLayer ] || this._mipmapCreateBundles( textureGPU, textureGPUDescriptor, baseArrayLayer );

		const commandEncoder = this.device.createCommandEncoder( {} );

		this._mipmapRunBundles( commandEncoder, passes );

		this.device.queue.submit( [ commandEncoder.finish() ] );

		if ( textureData.useCount !== 0 ) textureData.layers[ baseArrayLayer ] = passes;

		textureData.useCount ++;

	}
```
</details>

### `WebGPUTexturePassUtils._mipmapCreateBundles(textureGPU: GPUTexture, textureGPUDescriptor: any, baseArrayLayer: number): any[]`

**JSDoc:**
```typescript
/**
	 * Since multiple copy render passes are required to generate mipmaps, the passes
	 * are managed as render bundles to improve performance.
	 *
	 * @param {GPUTexture} textureGPU - The GPU texture object.
	 * @param {Object} textureGPUDescriptor - The texture descriptor.
	 * @param {number} baseArrayLayer - The index of the first array layer accessible to the texture view.
	 * @return {Array<Object>} An array of render bundles.
	 */
```

**Parameters:**

- **`textureGPU`** `GPUTexture`
- **`textureGPUDescriptor`** `any`
- **`baseArrayLayer`** `number`

**Returns:** `any[]`

**Calls:**

- `this.getTransferPipeline`
- `pipeline.getBindGroupLayout`
- `textureGPU.createView`
- `this.device.createBindGroup`
- `this.device.createRenderBundleEncoder`
- `passEncoder.setPipeline`
- `passEncoder.setBindGroup`
- `passEncoder.draw`
- `passes.push`
- `passEncoder.finish`

<details><summary>Code</summary>

```typescript
_mipmapCreateBundles( textureGPU, textureGPUDescriptor, baseArrayLayer ) {

		const pipeline = this.getTransferPipeline( textureGPUDescriptor.format );

		const bindGroupLayout = pipeline.getBindGroupLayout( 0 ); // @TODO: Consider making this static.

		let srcView = textureGPU.createView( {
			baseMipLevel: 0,
			mipLevelCount: 1,
			dimension: GPUTextureViewDimension.TwoD,
			baseArrayLayer
		} );

		const passes = [];

		for ( let i = 1; i < textureGPUDescriptor.mipLevelCount; i ++ ) {

			const bindGroup = this.device.createBindGroup( {
				layout: bindGroupLayout,
				entries: [ {
					binding: 0,
					resource: this.mipmapSampler
				}, {
					binding: 1,
					resource: srcView
				} ]
			} );

			const dstView = textureGPU.createView( {
				baseMipLevel: i,
				mipLevelCount: 1,
				dimension: GPUTextureViewDimension.TwoD,
				baseArrayLayer
			} );

			const passDescriptor = {
				colorAttachments: [ {
					view: dstView,
					loadOp: GPULoadOp.Clear,
					storeOp: GPUStoreOp.Store,
					clearValue: [ 0, 0, 0, 0 ]
				} ]
			};

			const passEncoder = this.device.createRenderBundleEncoder( {
				colorFormats: [ textureGPUDescriptor.format ]
			} );

			passEncoder.setPipeline( pipeline );
			passEncoder.setBindGroup( 0, bindGroup );
			passEncoder.draw( 4, 1, 0, 0 );

			passes.push( {
				renderBundles: [ passEncoder.finish() ],
				passDescriptor
			} );

			srcView = dstView;

		}

		return passes;

	}
```
</details>

### `WebGPUTexturePassUtils._mipmapRunBundles(commandEncoder: GPUCommandEncoder, passes: any[]): void`

**JSDoc:**
```typescript
/**
	 * Executes the render bundles.
	 *
	 * @param {GPUCommandEncoder} commandEncoder - The GPU command encoder.
	 * @param {Array<Object>} passes - An array of render bundles.
	 */
```

**Parameters:**

- **`commandEncoder`** `GPUCommandEncoder`
- **`passes`** `any[]`

**Returns:** `void`

**Calls:**

- `commandEncoder.beginRenderPass`
- `passEncoder.executeBundles`
- `passEncoder.end`

<details><summary>Code</summary>

```typescript
_mipmapRunBundles( commandEncoder, passes ) {

		const levels = passes.length;

		for ( let i = 0; i < levels; i ++ ) {

			const pass = passes[ i ];

			const passEncoder = commandEncoder.beginRenderPass( pass.passDescriptor );

			passEncoder.executeBundles( pass.renderBundles );

			passEncoder.end();

		}

	}
```
</details>

### `pass(pipeline: any, sourceView: any, destinationView: any): void`

**Parameters:**

- **`pipeline`** `any`
- **`sourceView`** `any`
- **`destinationView`** `any`

**Returns:** `void`

**Calls:**

- `pipeline.getBindGroupLayout`
- `this.device.createBindGroup`
- `commandEncoder.beginRenderPass`
- `passEncoder.setPipeline`
- `passEncoder.setBindGroup`
- `passEncoder.draw`
- `passEncoder.end`

<details><summary>Code</summary>

```typescript
( pipeline, sourceView, destinationView ) => {

			const bindGroupLayout = pipeline.getBindGroupLayout( 0 ); // @TODO: Consider making this static.

			const bindGroup = this.device.createBindGroup( {
				layout: bindGroupLayout,
				entries: [ {
					binding: 0,
					resource: this.flipYSampler
				}, {
					binding: 1,
					resource: sourceView
				} ]
			} );

			const passEncoder = commandEncoder.beginRenderPass( {
				colorAttachments: [ {
					view: destinationView,
					loadOp: GPULoadOp.Clear,
					storeOp: GPUStoreOp.Store,
					clearValue: [ 0, 0, 0, 0 ]
				} ]
			} );

			passEncoder.setPipeline( pipeline );
			passEncoder.setBindGroup( 0, bindGroup );
			passEncoder.draw( 4, 1, 0, 0 );
			passEncoder.end();

		}
```
</details>


---

## Classes

### `WebGPUTexturePassUtils`

<details><summary>Class Code</summary>

```ts
class WebGPUTexturePassUtils extends DataMap {

	/**
	 * Constructs a new utility object.
	 *
	 * @param {GPUDevice} device - The WebGPU device.
	 */
	constructor( device ) {

		super();

		/**
		 * The WebGPU device.
		 *
		 * @type {GPUDevice}
		 */
		this.device = device;

		const mipmapVertexSource = `
struct VarysStruct {
	@builtin( position ) Position: vec4<f32>,
	@location( 0 ) vTex : vec2<f32>
};

@vertex
fn main( @builtin( vertex_index ) vertexIndex : u32 ) -> VarysStruct {

	var Varys : VarysStruct;

	var pos = array< vec2<f32>, 4 >(
		vec2<f32>( -1.0,  1.0 ),
		vec2<f32>(  1.0,  1.0 ),
		vec2<f32>( -1.0, -1.0 ),
		vec2<f32>(  1.0, -1.0 )
	);

	var tex = array< vec2<f32>, 4 >(
		vec2<f32>( 0.0, 0.0 ),
		vec2<f32>( 1.0, 0.0 ),
		vec2<f32>( 0.0, 1.0 ),
		vec2<f32>( 1.0, 1.0 )
	);

	Varys.vTex = tex[ vertexIndex ];
	Varys.Position = vec4<f32>( pos[ vertexIndex ], 0.0, 1.0 );

	return Varys;

}
`;

		const mipmapFragmentSource = `
@group( 0 ) @binding( 0 )
var imgSampler : sampler;

@group( 0 ) @binding( 1 )
var img : texture_2d<f32>;

@fragment
fn main( @location( 0 ) vTex : vec2<f32> ) -> @location( 0 ) vec4<f32> {

	return textureSample( img, imgSampler, vTex );

}
`;

		const flipYFragmentSource = `
@group( 0 ) @binding( 0 )
var imgSampler : sampler;

@group( 0 ) @binding( 1 )
var img : texture_2d<f32>;

@fragment
fn main( @location( 0 ) vTex : vec2<f32> ) -> @location( 0 ) vec4<f32> {

	return textureSample( img, imgSampler, vec2( vTex.x, 1.0 - vTex.y ) );

}
`;

		/**
		 * The mipmap GPU sampler.
		 *
		 * @type {GPUSampler}
		 */
		this.mipmapSampler = device.createSampler( { minFilter: GPUFilterMode.Linear } );

		/**
		 * The flipY GPU sampler.
		 *
		 * @type {GPUSampler}
		 */
		this.flipYSampler = device.createSampler( { minFilter: GPUFilterMode.Nearest } ); //@TODO?: Consider using textureLoad()

		/**
		 * A cache for GPU render pipelines used for copy/transfer passes.
		 * Every texture format requires a unique pipeline.
		 *
		 * @type {Object<string,GPURenderPipeline>}
		 */
		this.transferPipelines = {};

		/**
		 * A cache for GPU render pipelines used for flipY passes.
		 * Every texture format requires a unique pipeline.
		 *
		 * @type {Object<string,GPURenderPipeline>}
		 */
		this.flipYPipelines = {};

		/**
		 * The mipmap vertex shader module.
		 *
		 * @type {GPUShaderModule}
		 */
		this.mipmapVertexShaderModule = device.createShaderModule( {
			label: 'mipmapVertex',
			code: mipmapVertexSource
		} );

		/**
		 * The mipmap fragment shader module.
		 *
		 * @type {GPUShaderModule}
		 */
		this.mipmapFragmentShaderModule = device.createShaderModule( {
			label: 'mipmapFragment',
			code: mipmapFragmentSource
		} );

		/**
		 * The flipY fragment shader module.
		 *
		 * @type {GPUShaderModule}
		 */
		this.flipYFragmentShaderModule = device.createShaderModule( {
			label: 'flipYFragment',
			code: flipYFragmentSource
		} );

	}

	/**
	 * Returns a render pipeline for the internal copy render pass. The pass
	 * requires a unique render pipeline for each texture format.
	 *
	 * @param {string} format - The GPU texture format
	 * @return {GPURenderPipeline} The GPU render pipeline.
	 */
	getTransferPipeline( format ) {

		let pipeline = this.transferPipelines[ format ];

		if ( pipeline === undefined ) {

			pipeline = this.device.createRenderPipeline( {
				label: `mipmap-${ format }`,
				vertex: {
					module: this.mipmapVertexShaderModule,
					entryPoint: 'main'
				},
				fragment: {
					module: this.mipmapFragmentShaderModule,
					entryPoint: 'main',
					targets: [ { format } ]
				},
				primitive: {
					topology: GPUPrimitiveTopology.TriangleStrip,
					stripIndexFormat: GPUIndexFormat.Uint32
				},
				layout: 'auto'
			} );

			this.transferPipelines[ format ] = pipeline;

		}

		return pipeline;

	}

	/**
	 * Returns a render pipeline for the flipY render pass. The pass
	 * requires a unique render pipeline for each texture format.
	 *
	 * @param {string} format - The GPU texture format
	 * @return {GPURenderPipeline} The GPU render pipeline.
	 */
	getFlipYPipeline( format ) {

		let pipeline = this.flipYPipelines[ format ];

		if ( pipeline === undefined ) {

			pipeline = this.device.createRenderPipeline( {
				label: `flipY-${ format }`,
				vertex: {
					module: this.mipmapVertexShaderModule,
					entryPoint: 'main'
				},
				fragment: {
					module: this.flipYFragmentShaderModule,
					entryPoint: 'main',
					targets: [ { format } ]
				},
				primitive: {
					topology: GPUPrimitiveTopology.TriangleStrip,
					stripIndexFormat: GPUIndexFormat.Uint32
				},
				layout: 'auto'
			} );

			this.flipYPipelines[ format ] = pipeline;

		}

		return pipeline;

	}

	/**
	 * Flip the contents of the given GPU texture along its vertical axis.
	 *
	 * @param {GPUTexture} textureGPU - The GPU texture object.
	 * @param {Object} textureGPUDescriptor - The texture descriptor.
	 * @param {number} [baseArrayLayer=0] - The index of the first array layer accessible to the texture view.
	 */
	flipY( textureGPU, textureGPUDescriptor, baseArrayLayer = 0 ) {

		const format = textureGPUDescriptor.format;
		const { width, height } = textureGPUDescriptor.size;

		const transferPipeline = this.getTransferPipeline( format );
		const flipYPipeline = this.getFlipYPipeline( format );

		const tempTexture = this.device.createTexture( {
			size: { width, height, depthOrArrayLayers: 1 },
			format,
			usage: GPUTextureUsage.RENDER_ATTACHMENT | GPUTextureUsage.TEXTURE_BINDING
		} );

		const srcView = textureGPU.createView( {
			baseMipLevel: 0,
			mipLevelCount: 1,
			dimension: GPUTextureViewDimension.TwoD,
			baseArrayLayer
		} );

		const dstView = tempTexture.createView( {
			baseMipLevel: 0,
			mipLevelCount: 1,
			dimension: GPUTextureViewDimension.TwoD,
			baseArrayLayer: 0
		} );

		const commandEncoder = this.device.createCommandEncoder( {} );

		const pass = ( pipeline, sourceView, destinationView ) => {

			const bindGroupLayout = pipeline.getBindGroupLayout( 0 ); // @TODO: Consider making this static.

			const bindGroup = this.device.createBindGroup( {
				layout: bindGroupLayout,
				entries: [ {
					binding: 0,
					resource: this.flipYSampler
				}, {
					binding: 1,
					resource: sourceView
				} ]
			} );

			const passEncoder = commandEncoder.beginRenderPass( {
				colorAttachments: [ {
					view: destinationView,
					loadOp: GPULoadOp.Clear,
					storeOp: GPUStoreOp.Store,
					clearValue: [ 0, 0, 0, 0 ]
				} ]
			} );

			passEncoder.setPipeline( pipeline );
			passEncoder.setBindGroup( 0, bindGroup );
			passEncoder.draw( 4, 1, 0, 0 );
			passEncoder.end();

		};

		pass( transferPipeline, srcView, dstView );
		pass( flipYPipeline, dstView, srcView );

		this.device.queue.submit( [ commandEncoder.finish() ] );

		tempTexture.destroy();

	}

	/**
	 * Generates mipmaps for the given GPU texture.
	 *
	 * @param {GPUTexture} textureGPU - The GPU texture object.
	 * @param {Object} textureGPUDescriptor - The texture descriptor.
	 * @param {number} [baseArrayLayer=0] - The index of the first array layer accessible to the texture view.
	 */
	generateMipmaps( textureGPU, textureGPUDescriptor, baseArrayLayer = 0 ) {

		const textureData = this.get( textureGPU );

		if ( textureData.useCount === undefined ) {

			textureData.useCount = 0;
			textureData.layers = [];

		}

		const passes = textureData.layers[ baseArrayLayer ] || this._mipmapCreateBundles( textureGPU, textureGPUDescriptor, baseArrayLayer );

		const commandEncoder = this.device.createCommandEncoder( {} );

		this._mipmapRunBundles( commandEncoder, passes );

		this.device.queue.submit( [ commandEncoder.finish() ] );

		if ( textureData.useCount !== 0 ) textureData.layers[ baseArrayLayer ] = passes;

		textureData.useCount ++;

	}

	/**
	 * Since multiple copy render passes are required to generate mipmaps, the passes
	 * are managed as render bundles to improve performance.
	 *
	 * @param {GPUTexture} textureGPU - The GPU texture object.
	 * @param {Object} textureGPUDescriptor - The texture descriptor.
	 * @param {number} baseArrayLayer - The index of the first array layer accessible to the texture view.
	 * @return {Array<Object>} An array of render bundles.
	 */
	_mipmapCreateBundles( textureGPU, textureGPUDescriptor, baseArrayLayer ) {

		const pipeline = this.getTransferPipeline( textureGPUDescriptor.format );

		const bindGroupLayout = pipeline.getBindGroupLayout( 0 ); // @TODO: Consider making this static.

		let srcView = textureGPU.createView( {
			baseMipLevel: 0,
			mipLevelCount: 1,
			dimension: GPUTextureViewDimension.TwoD,
			baseArrayLayer
		} );

		const passes = [];

		for ( let i = 1; i < textureGPUDescriptor.mipLevelCount; i ++ ) {

			const bindGroup = this.device.createBindGroup( {
				layout: bindGroupLayout,
				entries: [ {
					binding: 0,
					resource: this.mipmapSampler
				}, {
					binding: 1,
					resource: srcView
				} ]
			} );

			const dstView = textureGPU.createView( {
				baseMipLevel: i,
				mipLevelCount: 1,
				dimension: GPUTextureViewDimension.TwoD,
				baseArrayLayer
			} );

			const passDescriptor = {
				colorAttachments: [ {
					view: dstView,
					loadOp: GPULoadOp.Clear,
					storeOp: GPUStoreOp.Store,
					clearValue: [ 0, 0, 0, 0 ]
				} ]
			};

			const passEncoder = this.device.createRenderBundleEncoder( {
				colorFormats: [ textureGPUDescriptor.format ]
			} );

			passEncoder.setPipeline( pipeline );
			passEncoder.setBindGroup( 0, bindGroup );
			passEncoder.draw( 4, 1, 0, 0 );

			passes.push( {
				renderBundles: [ passEncoder.finish() ],
				passDescriptor
			} );

			srcView = dstView;

		}

		return passes;

	}

	/**
	 * Executes the render bundles.
	 *
	 * @param {GPUCommandEncoder} commandEncoder - The GPU command encoder.
	 * @param {Array<Object>} passes - An array of render bundles.
	 */
	_mipmapRunBundles( commandEncoder, passes ) {

		const levels = passes.length;

		for ( let i = 0; i < levels; i ++ ) {

			const pass = passes[ i ];

			const passEncoder = commandEncoder.beginRenderPass( pass.passDescriptor );

			passEncoder.executeBundles( pass.renderBundles );

			passEncoder.end();

		}

	}

}
```
</details>

#### Methods

##### `getTransferPipeline(format: string): GPURenderPipeline`

<details><summary>Code</summary>

```ts
getTransferPipeline( format ) {

		let pipeline = this.transferPipelines[ format ];

		if ( pipeline === undefined ) {

			pipeline = this.device.createRenderPipeline( {
				label: `mipmap-${ format }`,
				vertex: {
					module: this.mipmapVertexShaderModule,
					entryPoint: 'main'
				},
				fragment: {
					module: this.mipmapFragmentShaderModule,
					entryPoint: 'main',
					targets: [ { format } ]
				},
				primitive: {
					topology: GPUPrimitiveTopology.TriangleStrip,
					stripIndexFormat: GPUIndexFormat.Uint32
				},
				layout: 'auto'
			} );

			this.transferPipelines[ format ] = pipeline;

		}

		return pipeline;

	}
```
</details>

##### `getFlipYPipeline(format: string): GPURenderPipeline`

<details><summary>Code</summary>

```ts
getFlipYPipeline( format ) {

		let pipeline = this.flipYPipelines[ format ];

		if ( pipeline === undefined ) {

			pipeline = this.device.createRenderPipeline( {
				label: `flipY-${ format }`,
				vertex: {
					module: this.mipmapVertexShaderModule,
					entryPoint: 'main'
				},
				fragment: {
					module: this.flipYFragmentShaderModule,
					entryPoint: 'main',
					targets: [ { format } ]
				},
				primitive: {
					topology: GPUPrimitiveTopology.TriangleStrip,
					stripIndexFormat: GPUIndexFormat.Uint32
				},
				layout: 'auto'
			} );

			this.flipYPipelines[ format ] = pipeline;

		}

		return pipeline;

	}
```
</details>

##### `flipY(textureGPU: GPUTexture, textureGPUDescriptor: any, baseArrayLayer: number): void`

<details><summary>Code</summary>

```ts
flipY( textureGPU, textureGPUDescriptor, baseArrayLayer = 0 ) {

		const format = textureGPUDescriptor.format;
		const { width, height } = textureGPUDescriptor.size;

		const transferPipeline = this.getTransferPipeline( format );
		const flipYPipeline = this.getFlipYPipeline( format );

		const tempTexture = this.device.createTexture( {
			size: { width, height, depthOrArrayLayers: 1 },
			format,
			usage: GPUTextureUsage.RENDER_ATTACHMENT | GPUTextureUsage.TEXTURE_BINDING
		} );

		const srcView = textureGPU.createView( {
			baseMipLevel: 0,
			mipLevelCount: 1,
			dimension: GPUTextureViewDimension.TwoD,
			baseArrayLayer
		} );

		const dstView = tempTexture.createView( {
			baseMipLevel: 0,
			mipLevelCount: 1,
			dimension: GPUTextureViewDimension.TwoD,
			baseArrayLayer: 0
		} );

		const commandEncoder = this.device.createCommandEncoder( {} );

		const pass = ( pipeline, sourceView, destinationView ) => {

			const bindGroupLayout = pipeline.getBindGroupLayout( 0 ); // @TODO: Consider making this static.

			const bindGroup = this.device.createBindGroup( {
				layout: bindGroupLayout,
				entries: [ {
					binding: 0,
					resource: this.flipYSampler
				}, {
					binding: 1,
					resource: sourceView
				} ]
			} );

			const passEncoder = commandEncoder.beginRenderPass( {
				colorAttachments: [ {
					view: destinationView,
					loadOp: GPULoadOp.Clear,
					storeOp: GPUStoreOp.Store,
					clearValue: [ 0, 0, 0, 0 ]
				} ]
			} );

			passEncoder.setPipeline( pipeline );
			passEncoder.setBindGroup( 0, bindGroup );
			passEncoder.draw( 4, 1, 0, 0 );
			passEncoder.end();

		};

		pass( transferPipeline, srcView, dstView );
		pass( flipYPipeline, dstView, srcView );

		this.device.queue.submit( [ commandEncoder.finish() ] );

		tempTexture.destroy();

	}
```
</details>

##### `generateMipmaps(textureGPU: GPUTexture, textureGPUDescriptor: any, baseArrayLayer: number): void`

<details><summary>Code</summary>

```ts
generateMipmaps( textureGPU, textureGPUDescriptor, baseArrayLayer = 0 ) {

		const textureData = this.get( textureGPU );

		if ( textureData.useCount === undefined ) {

			textureData.useCount = 0;
			textureData.layers = [];

		}

		const passes = textureData.layers[ baseArrayLayer ] || this._mipmapCreateBundles( textureGPU, textureGPUDescriptor, baseArrayLayer );

		const commandEncoder = this.device.createCommandEncoder( {} );

		this._mipmapRunBundles( commandEncoder, passes );

		this.device.queue.submit( [ commandEncoder.finish() ] );

		if ( textureData.useCount !== 0 ) textureData.layers[ baseArrayLayer ] = passes;

		textureData.useCount ++;

	}
```
</details>

##### `_mipmapCreateBundles(textureGPU: GPUTexture, textureGPUDescriptor: any, baseArrayLayer: number): any[]`

<details><summary>Code</summary>

```ts
_mipmapCreateBundles( textureGPU, textureGPUDescriptor, baseArrayLayer ) {

		const pipeline = this.getTransferPipeline( textureGPUDescriptor.format );

		const bindGroupLayout = pipeline.getBindGroupLayout( 0 ); // @TODO: Consider making this static.

		let srcView = textureGPU.createView( {
			baseMipLevel: 0,
			mipLevelCount: 1,
			dimension: GPUTextureViewDimension.TwoD,
			baseArrayLayer
		} );

		const passes = [];

		for ( let i = 1; i < textureGPUDescriptor.mipLevelCount; i ++ ) {

			const bindGroup = this.device.createBindGroup( {
				layout: bindGroupLayout,
				entries: [ {
					binding: 0,
					resource: this.mipmapSampler
				}, {
					binding: 1,
					resource: srcView
				} ]
			} );

			const dstView = textureGPU.createView( {
				baseMipLevel: i,
				mipLevelCount: 1,
				dimension: GPUTextureViewDimension.TwoD,
				baseArrayLayer
			} );

			const passDescriptor = {
				colorAttachments: [ {
					view: dstView,
					loadOp: GPULoadOp.Clear,
					storeOp: GPUStoreOp.Store,
					clearValue: [ 0, 0, 0, 0 ]
				} ]
			};

			const passEncoder = this.device.createRenderBundleEncoder( {
				colorFormats: [ textureGPUDescriptor.format ]
			} );

			passEncoder.setPipeline( pipeline );
			passEncoder.setBindGroup( 0, bindGroup );
			passEncoder.draw( 4, 1, 0, 0 );

			passes.push( {
				renderBundles: [ passEncoder.finish() ],
				passDescriptor
			} );

			srcView = dstView;

		}

		return passes;

	}
```
</details>

##### `_mipmapRunBundles(commandEncoder: GPUCommandEncoder, passes: any[]): void`

<details><summary>Code</summary>

```ts
_mipmapRunBundles( commandEncoder, passes ) {

		const levels = passes.length;

		for ( let i = 0; i < levels; i ++ ) {

			const pass = passes[ i ];

			const passEncoder = commandEncoder.beginRenderPass( pass.passDescriptor );

			passEncoder.executeBundles( pass.renderBundles );

			passEncoder.end();

		}

	}
```
</details>


---