[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `WebGPUPipelineUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 14 |
| 🧱 Classes | 1 |
| 📦 Imports | 59 |
| 📊 Variables & Constants | 40 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgpu/utils/WebGPUPipelineUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BlendColorFactor` | `../../common/Constants.js` |
| `OneMinusBlendColorFactor` | `../../common/Constants.js` |
| `GPUFrontFace` | `./WebGPUConstants.js` |
| `GPUCullMode` | `./WebGPUConstants.js` |
| `GPUColorWriteFlags` | `./WebGPUConstants.js` |
| `GPUCompareFunction` | `./WebGPUConstants.js` |
| `GPUBlendFactor` | `./WebGPUConstants.js` |
| `GPUBlendOperation` | `./WebGPUConstants.js` |
| `GPUIndexFormat` | `./WebGPUConstants.js` |
| `GPUStencilOperation` | `./WebGPUConstants.js` |
| `FrontSide` | `../../../constants.js` |
| `BackSide` | `../../../constants.js` |
| `DoubleSide` | `../../../constants.js` |
| `NeverDepth` | `../../../constants.js` |
| `AlwaysDepth` | `../../../constants.js` |
| `LessDepth` | `../../../constants.js` |
| `LessEqualDepth` | `../../../constants.js` |
| `EqualDepth` | `../../../constants.js` |
| `GreaterEqualDepth` | `../../../constants.js` |
| `GreaterDepth` | `../../../constants.js` |
| `NotEqualDepth` | `../../../constants.js` |
| `NoBlending` | `../../../constants.js` |
| `NormalBlending` | `../../../constants.js` |
| `AdditiveBlending` | `../../../constants.js` |
| `SubtractiveBlending` | `../../../constants.js` |
| `MultiplyBlending` | `../../../constants.js` |
| `CustomBlending` | `../../../constants.js` |
| `ZeroFactor` | `../../../constants.js` |
| `OneFactor` | `../../../constants.js` |
| `SrcColorFactor` | `../../../constants.js` |
| `OneMinusSrcColorFactor` | `../../../constants.js` |
| `SrcAlphaFactor` | `../../../constants.js` |
| `OneMinusSrcAlphaFactor` | `../../../constants.js` |
| `DstColorFactor` | `../../../constants.js` |
| `OneMinusDstColorFactor` | `../../../constants.js` |
| `DstAlphaFactor` | `../../../constants.js` |
| `OneMinusDstAlphaFactor` | `../../../constants.js` |
| `SrcAlphaSaturateFactor` | `../../../constants.js` |
| `AddEquation` | `../../../constants.js` |
| `SubtractEquation` | `../../../constants.js` |
| `ReverseSubtractEquation` | `../../../constants.js` |
| `MinEquation` | `../../../constants.js` |
| `MaxEquation` | `../../../constants.js` |
| `KeepStencilOp` | `../../../constants.js` |
| `ZeroStencilOp` | `../../../constants.js` |
| `ReplaceStencilOp` | `../../../constants.js` |
| `InvertStencilOp` | `../../../constants.js` |
| `IncrementStencilOp` | `../../../constants.js` |
| `DecrementStencilOp` | `../../../constants.js` |
| `IncrementWrapStencilOp` | `../../../constants.js` |
| `DecrementWrapStencilOp` | `../../../constants.js` |
| `NeverStencilFunc` | `../../../constants.js` |
| `AlwaysStencilFunc` | `../../../constants.js` |
| `LessStencilFunc` | `../../../constants.js` |
| `LessEqualStencilFunc` | `../../../constants.js` |
| `EqualStencilFunc` | `../../../constants.js` |
| `GreaterEqualStencilFunc` | `../../../constants.js` |
| `GreaterStencilFunc` | `../../../constants.js` |
| `NotEqualStencilFunc` | `../../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `backend` | `WebGPUBackend` | let/var | `this.backend` | ✗ |
| `device` | `any` | let/var | `backend.device` | ✗ |
| `utils` | `any` | let/var | `backend.utils` | ✗ |
| `bindGroupLayouts` | `any[]` | let/var | `[]` | ✗ |
| `blending` | `any` | let/var | `*not shown*` | ✗ |
| `stencilFront` | `{}` | let/var | `{}` | ✗ |
| `targets` | `any[]` | let/var | `[]` | ✗ |
| `textures` | `any` | let/var | `renderObject.context.textures` | ✗ |
| `vertexModule` | `any` | let/var | `backend.get( vertexProgram ).module` | ✗ |
| `fragmentModule` | `any` | let/var | `backend.get( fragmentProgram ).module` | ✗ |
| `pipelineDescriptor` | `{ label: string; vertex: any; fragmen...` | let/var | `{ label: `renderPipeline_${ material.name \|\| material.type }_${ material.id...` | ✗ |
| `depthStencil` | `{ format: any; depthWriteEnabled: any...` | let/var | `{}` | ✗ |
| `renderDepth` | `any` | let/var | `renderObject.context.depth` | ✗ |
| `renderStencil` | `any` | let/var | `renderObject.context.stencil` | ✗ |
| `p` | `Promise<any>` | let/var | `new Promise( ( resolve /*, reject*/ ) => { device.createRenderPipelineAsync( ...` | ✗ |
| `backend` | `WebGPUBackend` | let/var | `this.backend` | ✗ |
| `descriptor` | `{ label: string; colorFormats: any[];...` | let/var | `{ label: label, colorFormats: [ colorFormat ], depthStencilFormat, sampleCount }` | ✗ |
| `backend` | `WebGPUBackend` | let/var | `this.backend` | ✗ |
| `device` | `any` | let/var | `backend.device` | ✗ |
| `computeProgram` | `any` | let/var | `backend.get( pipeline.computeProgram ).module` | ✗ |
| `bindGroupLayouts` | `any[]` | let/var | `[]` | ✗ |
| `color` | `any` | let/var | `*not shown*` | ✗ |
| `alpha` | `any` | let/var | `*not shown*` | ✗ |
| `blending` | `any` | let/var | `material.blending` | ✗ |
| `blendSrc` | `any` | let/var | `material.blendSrc` | ✗ |
| `blendDst` | `any` | let/var | `material.blendDst` | ✗ |
| `blendEquation` | `any` | let/var | `material.blendEquation` | ✗ |
| `blendSrcAlpha` | `any` | let/var | `material.blendSrcAlpha !== null ? material.blendSrcAlpha : blendSrc` | ✗ |
| `blendDstAlpha` | `any` | let/var | `material.blendDstAlpha !== null ? material.blendDstAlpha : blendDst` | ✗ |
| `blendEquationAlpha` | `any` | let/var | `material.blendEquationAlpha !== null ? material.blendEquationAlpha : blendEqu...` | ✗ |
| `premultipliedAlpha` | `any` | let/var | `material.premultipliedAlpha` | ✗ |
| `blendFactor` | `any` | let/var | `*not shown*` | ✗ |
| `stencilCompare` | `any` | let/var | `*not shown*` | ✗ |
| `stencilFunc` | `any` | let/var | `material.stencilFunc` | ✗ |
| `stencilOperation` | `any` | let/var | `*not shown*` | ✗ |
| `blendOperation` | `any` | let/var | `*not shown*` | ✗ |
| `descriptor` | `{ topology: any; stripIndexFormat: st...` | let/var | `{}` | ✗ |
| `utils` | `any` | let/var | `this.backend.utils` | ✗ |
| `depthCompare` | `any` | let/var | `*not shown*` | ✗ |
| `depthFunc` | `any` | let/var | `material.depthFunc` | ✗ |


---

## Functions

### `WebGPUPipelineUtils.setPipeline(pass: any, pipeline: any): void`

**JSDoc:**
```typescript
/**
	 * Sets the given pipeline for the given pass. The method makes sure to only set the
	 * pipeline when necessary.
	 *
	 * @param {(GPURenderPassEncoder|GPUComputePassEncoder)} pass - The pass encoder.
	 * @param {(GPURenderPipeline|GPUComputePipeline)} pipeline - The pipeline.
	 */
```

**Parameters:**

- **`pass`** `any`
- **`pipeline`** `any`

**Returns:** `void`

**Calls:**

- `this._activePipelines.get`
- `pass.setPipeline`
- `this._activePipelines.set`

<details><summary>Code</summary>

```typescript
setPipeline( pass, pipeline ) {

		const currentPipeline = this._activePipelines.get( pass );

		if ( currentPipeline !== pipeline ) {

			pass.setPipeline( pipeline );

			this._activePipelines.set( pass, pipeline );

		}

	}
```
</details>

### `WebGPUPipelineUtils._getSampleCount(renderContext: RenderContext): number`

**JSDoc:**
```typescript
/**
	 * Returns the sample count derived from the given render context.
	 *
	 * @private
	 * @param {RenderContext} renderContext - The render context.
	 * @return {number} The sample count.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`

**Returns:** `number`

**Calls:**

- `this.backend.utils.getSampleCountRenderContext`

<details><summary>Code</summary>

```typescript
_getSampleCount( renderContext ) {

		return this.backend.utils.getSampleCountRenderContext( renderContext );

	}
```
</details>

### `WebGPUPipelineUtils.createRenderPipeline(renderObject: RenderObject, promises: Promise<any>[]): void`

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

- `backend.get`
- `renderObject.getBindings`
- `bindGroupLayouts.push`
- `backend.attributeUtils.createShaderVertexBuffers`
- `this._getBlending`
- `this._getStencilCompare`
- `this._getStencilOperation`
- `this._getColorWriteMask`
- `utils.getTextureFormatGPU`
- `targets.push`
- `utils.getCurrentColorFormat`
- `this._getPrimitiveState`
- `this._getDepthCompare`
- `utils.getCurrentDepthStencilFormat`
- `this._getSampleCount`
- `Object.assign`
- `device.createPipelineLayout`
- `device.createRenderPipeline`
- `device.createRenderPipelineAsync( pipelineDescriptor ).then`
- `resolve`
- `promises.push`

**Internal Comments:**
```
// bind group layouts (x2)
// vertex buffers (x2)
// blending (x2)
// stencil (x2)
```

<details><summary>Code</summary>

```typescript
createRenderPipeline( renderObject, promises ) {

		const { object, material, geometry, pipeline } = renderObject;
		const { vertexProgram, fragmentProgram } = pipeline;

		const backend = this.backend;
		const device = backend.device;
		const utils = backend.utils;

		const pipelineData = backend.get( pipeline );

		// bind group layouts

		const bindGroupLayouts = [];

		for ( const bindGroup of renderObject.getBindings() ) {

			const bindingsData = backend.get( bindGroup );

			bindGroupLayouts.push( bindingsData.layout );

		}

		// vertex buffers

		const vertexBuffers = backend.attributeUtils.createShaderVertexBuffers( renderObject );

		// blending

		let blending;

		if ( material.blending !== NoBlending && ( material.blending !== NormalBlending || material.transparent !== false ) ) {

			blending = this._getBlending( material );

		}

		// stencil

		let stencilFront = {};

		if ( material.stencilWrite === true ) {

			stencilFront = {
				compare: this._getStencilCompare( material ),
				failOp: this._getStencilOperation( material.stencilFail ),
				depthFailOp: this._getStencilOperation( material.stencilZFail ),
				passOp: this._getStencilOperation( material.stencilZPass )
			};

		}

		const colorWriteMask = this._getColorWriteMask( material );

		const targets = [];

		if ( renderObject.context.textures !== null ) {

			const textures = renderObject.context.textures;

			for ( let i = 0; i < textures.length; i ++ ) {

				const colorFormat = utils.getTextureFormatGPU( textures[ i ] );

				targets.push( {
					format: colorFormat,
					blend: blending,
					writeMask: colorWriteMask
				} );

			}

		} else {

			const colorFormat = utils.getCurrentColorFormat( renderObject.context );

			targets.push( {
				format: colorFormat,
				blend: blending,
				writeMask: colorWriteMask
			} );

		}

		const vertexModule = backend.get( vertexProgram ).module;
		const fragmentModule = backend.get( fragmentProgram ).module;

		const primitiveState = this._getPrimitiveState( object, geometry, material );
		const depthCompare = this._getDepthCompare( material );
		const depthStencilFormat = utils.getCurrentDepthStencilFormat( renderObject.context );

		const sampleCount = this._getSampleCount( renderObject.context );

		const pipelineDescriptor = {
			label: `renderPipeline_${ material.name || material.type }_${ material.id }`,
			vertex: Object.assign( {}, vertexModule, { buffers: vertexBuffers } ),
			fragment: Object.assign( {}, fragmentModule, { targets } ),
			primitive: primitiveState,
			multisample: {
				count: sampleCount,
				alphaToCoverageEnabled: material.alphaToCoverage && sampleCount > 1
			},
			layout: device.createPipelineLayout( {
				bindGroupLayouts
			} )
		};


		const depthStencil = {};
		const renderDepth = renderObject.context.depth;
		const renderStencil = renderObject.context.stencil;

		if ( renderDepth === true || renderStencil === true ) {

			if ( renderDepth === true ) {

				depthStencil.format = depthStencilFormat;
				depthStencil.depthWriteEnabled = material.depthWrite;
				depthStencil.depthCompare = depthCompare;

			}

			if ( renderStencil === true ) {

				depthStencil.stencilFront = stencilFront;
				depthStencil.stencilBack = {}; // three.js does not provide an API to configure the back function (gl.stencilFuncSeparate() was never used)
				depthStencil.stencilReadMask = material.stencilFuncMask;
				depthStencil.stencilWriteMask = material.stencilWriteMask;

			}

			if ( material.polygonOffset === true ) {

				depthStencil.depthBias = material.polygonOffsetUnits;
				depthStencil.depthBiasSlopeScale = material.polygonOffsetFactor;
				depthStencil.depthBiasClamp = 0; // three.js does not provide an API to configure this value

			}

			pipelineDescriptor.depthStencil = depthStencil;

		}


		if ( promises === null ) {

			pipelineData.pipeline = device.createRenderPipeline( pipelineDescriptor );

		} else {

			const p = new Promise( ( resolve /*, reject*/ ) => {

				device.createRenderPipelineAsync( pipelineDescriptor ).then( pipeline => {

					pipelineData.pipeline = pipeline;
					resolve();

				} );

			} );

			promises.push( p );

		}

	}
```
</details>

### `WebGPUPipelineUtils.createBundleEncoder(renderContext: RenderContext, label: string): GPURenderBundleEncoder`

**JSDoc:**
```typescript
/**
	 * Creates GPU render bundle encoder for the given render context.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @param {?string} [label='renderBundleEncoder'] - The label.
	 * @return {GPURenderBundleEncoder} The GPU render bundle encoder.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`
- **`label`** `string`

**Returns:** `GPURenderBundleEncoder`

**Calls:**

- `utils.getCurrentDepthStencilFormat`
- `utils.getCurrentColorFormat`
- `this._getSampleCount`
- `device.createRenderBundleEncoder`

<details><summary>Code</summary>

```typescript
createBundleEncoder( renderContext, label = 'renderBundleEncoder' ) {

		const backend = this.backend;
		const { utils, device } = backend;

		const depthStencilFormat = utils.getCurrentDepthStencilFormat( renderContext );
		const colorFormat = utils.getCurrentColorFormat( renderContext );
		const sampleCount = this._getSampleCount( renderContext );

		const descriptor = {
			label: label,
			colorFormats: [ colorFormat ],
			depthStencilFormat,
			sampleCount
		};

		return device.createRenderBundleEncoder( descriptor );

	}
```
</details>

### `WebGPUPipelineUtils.createComputePipeline(pipeline: ComputePipeline, bindings: BindGroup[]): void`

**JSDoc:**
```typescript
/**
	 * Creates a compute pipeline for the given compute node.
	 *
	 * @param {ComputePipeline} pipeline - The compute pipeline.
	 * @param {Array<BindGroup>} bindings - The bindings.
	 */
```

**Parameters:**

- **`pipeline`** `ComputePipeline`
- **`bindings`** `BindGroup[]`

**Returns:** `void`

**Calls:**

- `backend.get`
- `bindGroupLayouts.push`
- `device.createComputePipeline`
- `device.createPipelineLayout`

**Internal Comments:**
```
// bind group layouts (x2)
```

<details><summary>Code</summary>

```typescript
createComputePipeline( pipeline, bindings ) {

		const backend = this.backend;
		const device = backend.device;

		const computeProgram = backend.get( pipeline.computeProgram ).module;

		const pipelineGPU = backend.get( pipeline );

		// bind group layouts

		const bindGroupLayouts = [];

		for ( const bindingsGroup of bindings ) {

			const bindingsData = backend.get( bindingsGroup );

			bindGroupLayouts.push( bindingsData.layout );

		}

		pipelineGPU.pipeline = device.createComputePipeline( {
			compute: computeProgram,
			layout: device.createPipelineLayout( {
				bindGroupLayouts
			} )
		} );

	}
```
</details>

### `WebGPUPipelineUtils._getBlending(material: Material): any`

**JSDoc:**
```typescript
/**
	 * Returns the blending state as a descriptor object required
	 * for the pipeline creation.
	 *
	 * @private
	 * @param {Material} material - The material.
	 * @return {Object} The blending state.
	 */
```

**Parameters:**

- **`material`** `Material`

**Returns:** `any`

**Calls:**

- `this._getBlendFactor`
- `this._getBlendOperation`
- `setBlend`
- `console.error`

<details><summary>Code</summary>

```typescript
_getBlending( material ) {

		let color, alpha;

		const blending = material.blending;
		const blendSrc = material.blendSrc;
		const blendDst = material.blendDst;
		const blendEquation = material.blendEquation;


		if ( blending === CustomBlending ) {

			const blendSrcAlpha = material.blendSrcAlpha !== null ? material.blendSrcAlpha : blendSrc;
			const blendDstAlpha = material.blendDstAlpha !== null ? material.blendDstAlpha : blendDst;
			const blendEquationAlpha = material.blendEquationAlpha !== null ? material.blendEquationAlpha : blendEquation;

			color = {
				srcFactor: this._getBlendFactor( blendSrc ),
				dstFactor: this._getBlendFactor( blendDst ),
				operation: this._getBlendOperation( blendEquation )
			};

			alpha = {
				srcFactor: this._getBlendFactor( blendSrcAlpha ),
				dstFactor: this._getBlendFactor( blendDstAlpha ),
				operation: this._getBlendOperation( blendEquationAlpha )
			};

		} else {

			const premultipliedAlpha = material.premultipliedAlpha;

			const setBlend = ( srcRGB, dstRGB, srcAlpha, dstAlpha ) => {

				color = {
					srcFactor: srcRGB,
					dstFactor: dstRGB,
					operation: GPUBlendOperation.Add
				};

				alpha = {
					srcFactor: srcAlpha,
					dstFactor: dstAlpha,
					operation: GPUBlendOperation.Add
				};

			};

			if ( premultipliedAlpha ) {

				switch ( blending ) {

					case NormalBlending:
						setBlend( GPUBlendFactor.One, GPUBlendFactor.OneMinusSrcAlpha, GPUBlendFactor.One, GPUBlendFactor.OneMinusSrcAlpha );
						break;

					case AdditiveBlending:
						setBlend( GPUBlendFactor.One, GPUBlendFactor.One, GPUBlendFactor.One, GPUBlendFactor.One );
						break;

					case SubtractiveBlending:
						setBlend( GPUBlendFactor.Zero, GPUBlendFactor.OneMinusSrc, GPUBlendFactor.Zero, GPUBlendFactor.One );
						break;

					case MultiplyBlending:
						setBlend( GPUBlendFactor.Dst, GPUBlendFactor.OneMinusSrcAlpha, GPUBlendFactor.Zero, GPUBlendFactor.One );
						break;

				}

			} else {

				switch ( blending ) {

					case NormalBlending:
						setBlend( GPUBlendFactor.SrcAlpha, GPUBlendFactor.OneMinusSrcAlpha, GPUBlendFactor.One, GPUBlendFactor.OneMinusSrcAlpha );
						break;

					case AdditiveBlending:
						setBlend( GPUBlendFactor.SrcAlpha, GPUBlendFactor.One, GPUBlendFactor.One, GPUBlendFactor.One );
						break;

					case SubtractiveBlending:
						console.error( 'THREE.WebGPURenderer: SubtractiveBlending requires material.premultipliedAlpha = true' );
						break;

					case MultiplyBlending:
						console.error( 'THREE.WebGPURenderer: MultiplyBlending requires material.premultipliedAlpha = true' );
						break;

				}

			}

		}

		if ( color !== undefined && alpha !== undefined ) {

			return { color, alpha };

		} else {

			console.error( 'THREE.WebGPURenderer: Invalid blending: ', blending );

		}

	}
```
</details>

### `WebGPUPipelineUtils._getBlendFactor(blend: number): string`

**JSDoc:**
```typescript
/**
	 * Returns the GPU blend factor which is required for the pipeline creation.
	 *
	 * @private
	 * @param {number} blend - The blend factor as a three.js constant.
	 * @return {string} The GPU blend factor.
	 */
```

**Parameters:**

- **`blend`** `number`

**Returns:** `string`

**Calls:**

- `console.error`

<details><summary>Code</summary>

```typescript
_getBlendFactor( blend ) {

		let blendFactor;

		switch ( blend ) {

			case ZeroFactor:
				blendFactor = GPUBlendFactor.Zero;
				break;

			case OneFactor:
				blendFactor = GPUBlendFactor.One;
				break;

			case SrcColorFactor:
				blendFactor = GPUBlendFactor.Src;
				break;

			case OneMinusSrcColorFactor:
				blendFactor = GPUBlendFactor.OneMinusSrc;
				break;

			case SrcAlphaFactor:
				blendFactor = GPUBlendFactor.SrcAlpha;
				break;

			case OneMinusSrcAlphaFactor:
				blendFactor = GPUBlendFactor.OneMinusSrcAlpha;
				break;

			case DstColorFactor:
				blendFactor = GPUBlendFactor.Dst;
				break;

			case OneMinusDstColorFactor:
				blendFactor = GPUBlendFactor.OneMinusDst;
				break;

			case DstAlphaFactor:
				blendFactor = GPUBlendFactor.DstAlpha;
				break;

			case OneMinusDstAlphaFactor:
				blendFactor = GPUBlendFactor.OneMinusDstAlpha;
				break;

			case SrcAlphaSaturateFactor:
				blendFactor = GPUBlendFactor.SrcAlphaSaturated;
				break;

			case BlendColorFactor:
				blendFactor = GPUBlendFactor.Constant;
				break;

			case OneMinusBlendColorFactor:
				blendFactor = GPUBlendFactor.OneMinusConstant;
				break;

			default:
				console.error( 'THREE.WebGPURenderer: Blend factor not supported.', blend );

		}

		return blendFactor;

	}
```
</details>

### `WebGPUPipelineUtils._getStencilCompare(material: Material): string`

**JSDoc:**
```typescript
/**
	 * Returns the GPU stencil compare function which is required for the pipeline creation.
	 *
	 * @private
	 * @param {Material} material - The material.
	 * @return {string} The GPU stencil compare function.
	 */
```

**Parameters:**

- **`material`** `Material`

**Returns:** `string`

**Calls:**

- `console.error`

<details><summary>Code</summary>

```typescript
_getStencilCompare( material ) {

		let stencilCompare;

		const stencilFunc = material.stencilFunc;

		switch ( stencilFunc ) {

			case NeverStencilFunc:
				stencilCompare = GPUCompareFunction.Never;
				break;

			case AlwaysStencilFunc:
				stencilCompare = GPUCompareFunction.Always;
				break;

			case LessStencilFunc:
				stencilCompare = GPUCompareFunction.Less;
				break;

			case LessEqualStencilFunc:
				stencilCompare = GPUCompareFunction.LessEqual;
				break;

			case EqualStencilFunc:
				stencilCompare = GPUCompareFunction.Equal;
				break;

			case GreaterEqualStencilFunc:
				stencilCompare = GPUCompareFunction.GreaterEqual;
				break;

			case GreaterStencilFunc:
				stencilCompare = GPUCompareFunction.Greater;
				break;

			case NotEqualStencilFunc:
				stencilCompare = GPUCompareFunction.NotEqual;
				break;

			default:
				console.error( 'THREE.WebGPURenderer: Invalid stencil function.', stencilFunc );

		}

		return stencilCompare;

	}
```
</details>

### `WebGPUPipelineUtils._getStencilOperation(op: number): string`

**JSDoc:**
```typescript
/**
	 * Returns the GPU stencil operation which is required for the pipeline creation.
	 *
	 * @private
	 * @param {number} op - A three.js constant defining the stencil operation.
	 * @return {string} The GPU stencil operation.
	 */
```

**Parameters:**

- **`op`** `number`

**Returns:** `string`

**Calls:**

- `console.error`

<details><summary>Code</summary>

```typescript
_getStencilOperation( op ) {

		let stencilOperation;

		switch ( op ) {

			case KeepStencilOp:
				stencilOperation = GPUStencilOperation.Keep;
				break;

			case ZeroStencilOp:
				stencilOperation = GPUStencilOperation.Zero;
				break;

			case ReplaceStencilOp:
				stencilOperation = GPUStencilOperation.Replace;
				break;

			case InvertStencilOp:
				stencilOperation = GPUStencilOperation.Invert;
				break;

			case IncrementStencilOp:
				stencilOperation = GPUStencilOperation.IncrementClamp;
				break;

			case DecrementStencilOp:
				stencilOperation = GPUStencilOperation.DecrementClamp;
				break;

			case IncrementWrapStencilOp:
				stencilOperation = GPUStencilOperation.IncrementWrap;
				break;

			case DecrementWrapStencilOp:
				stencilOperation = GPUStencilOperation.DecrementWrap;
				break;

			default:
				console.error( 'THREE.WebGPURenderer: Invalid stencil operation.', stencilOperation );

		}

		return stencilOperation;

	}
```
</details>

### `WebGPUPipelineUtils._getBlendOperation(blendEquation: number): string`

**JSDoc:**
```typescript
/**
	 * Returns the GPU blend operation which is required for the pipeline creation.
	 *
	 * @private
	 * @param {number} blendEquation - A three.js constant defining the blend equation.
	 * @return {string} The GPU blend operation.
	 */
```

**Parameters:**

- **`blendEquation`** `number`

**Returns:** `string`

**Calls:**

- `console.error`

<details><summary>Code</summary>

```typescript
_getBlendOperation( blendEquation ) {

		let blendOperation;

		switch ( blendEquation ) {

			case AddEquation:
				blendOperation = GPUBlendOperation.Add;
				break;

			case SubtractEquation:
				blendOperation = GPUBlendOperation.Subtract;
				break;

			case ReverseSubtractEquation:
				blendOperation = GPUBlendOperation.ReverseSubtract;
				break;

			case MinEquation:
				blendOperation = GPUBlendOperation.Min;
				break;

			case MaxEquation:
				blendOperation = GPUBlendOperation.Max;
				break;

			default:
				console.error( 'THREE.WebGPUPipelineUtils: Blend equation not supported.', blendEquation );

		}

		return blendOperation;

	}
```
</details>

### `WebGPUPipelineUtils._getPrimitiveState(object: Object3D, geometry: BufferGeometry, material: Material): any`

**JSDoc:**
```typescript
/**
	 * Returns the primitive state as a descriptor object required
	 * for the pipeline creation.
	 *
	 * @private
	 * @param {Object3D} object - The 3D object.
	 * @param {BufferGeometry} geometry - The geometry.
	 * @param {Material} material - The material.
	 * @return {Object} The primitive state.
	 */
```

**Parameters:**

- **`object`** `Object3D`
- **`geometry`** `BufferGeometry`
- **`material`** `Material`

**Returns:** `any`

**Calls:**

- `utils.getPrimitiveTopology`
- `console.error`

<details><summary>Code</summary>

```typescript
_getPrimitiveState( object, geometry, material ) {

		const descriptor = {};
		const utils = this.backend.utils;

		descriptor.topology = utils.getPrimitiveTopology( object, material );

		if ( geometry.index !== null && object.isLine === true && object.isLineSegments !== true ) {

			descriptor.stripIndexFormat = ( geometry.index.array instanceof Uint16Array ) ? GPUIndexFormat.Uint16 : GPUIndexFormat.Uint32;

		}

		switch ( material.side ) {

			case FrontSide:
				descriptor.frontFace = GPUFrontFace.CCW;
				descriptor.cullMode = GPUCullMode.Back;
				break;

			case BackSide:
				descriptor.frontFace = GPUFrontFace.CCW;
				descriptor.cullMode = GPUCullMode.Front;
				break;

			case DoubleSide:
				descriptor.frontFace = GPUFrontFace.CCW;
				descriptor.cullMode = GPUCullMode.None;
				break;

			default:
				console.error( 'THREE.WebGPUPipelineUtils: Unknown material.side value.', material.side );
				break;

		}

		return descriptor;

	}
```
</details>

### `WebGPUPipelineUtils._getColorWriteMask(material: Material): number`

**JSDoc:**
```typescript
/**
	 * Returns the GPU color write mask which is required for the pipeline creation.
	 *
	 * @private
	 * @param {Material} material - The material.
	 * @return {number} The GPU color write mask.
	 */
```

**Parameters:**

- **`material`** `Material`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
_getColorWriteMask( material ) {

		return ( material.colorWrite === true ) ? GPUColorWriteFlags.All : GPUColorWriteFlags.None;

	}
```
</details>

### `WebGPUPipelineUtils._getDepthCompare(material: Material): string`

**JSDoc:**
```typescript
/**
	 * Returns the GPU depth compare function which is required for the pipeline creation.
	 *
	 * @private
	 * @param {Material} material - The material.
	 * @return {string} The GPU depth compare function.
	 */
```

**Parameters:**

- **`material`** `Material`

**Returns:** `string`

**Calls:**

- `console.error`

<details><summary>Code</summary>

```typescript
_getDepthCompare( material ) {

		let depthCompare;

		if ( material.depthTest === false ) {

			depthCompare = GPUCompareFunction.Always;

		} else {

			const depthFunc = material.depthFunc;

			switch ( depthFunc ) {

				case NeverDepth:
					depthCompare = GPUCompareFunction.Never;
					break;

				case AlwaysDepth:
					depthCompare = GPUCompareFunction.Always;
					break;

				case LessDepth:
					depthCompare = GPUCompareFunction.Less;
					break;

				case LessEqualDepth:
					depthCompare = GPUCompareFunction.LessEqual;
					break;

				case EqualDepth:
					depthCompare = GPUCompareFunction.Equal;
					break;

				case GreaterEqualDepth:
					depthCompare = GPUCompareFunction.GreaterEqual;
					break;

				case GreaterDepth:
					depthCompare = GPUCompareFunction.Greater;
					break;

				case NotEqualDepth:
					depthCompare = GPUCompareFunction.NotEqual;
					break;

				default:
					console.error( 'THREE.WebGPUPipelineUtils: Invalid depth function.', depthFunc );

			}

		}

		return depthCompare;

	}
```
</details>

### `setBlend(srcRGB: any, dstRGB: any, srcAlpha: any, dstAlpha: any): void`

**Parameters:**

- **`srcRGB`** `any`
- **`dstRGB`** `any`
- **`srcAlpha`** `any`
- **`dstAlpha`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
( srcRGB, dstRGB, srcAlpha, dstAlpha ) => {

				color = {
					srcFactor: srcRGB,
					dstFactor: dstRGB,
					operation: GPUBlendOperation.Add
				};

				alpha = {
					srcFactor: srcAlpha,
					dstFactor: dstAlpha,
					operation: GPUBlendOperation.Add
				};

			}
```
</details>


---

## Classes

### `WebGPUPipelineUtils`

<details><summary>Class Code</summary>

```ts
class WebGPUPipelineUtils {

	/**
	 * Constructs a new utility object.
	 *
	 * @param {WebGPUBackend} backend - The WebGPU backend.
	 */
	constructor( backend ) {

		/**
		 * A reference to the WebGPU backend.
		 *
		 * @type {WebGPUBackend}
		 */
		this.backend = backend;

		/**
		 * A Weak Map that tracks the active pipeline for render or compute passes.
		 *
		 * @private
		 * @type {WeakMap<(GPURenderPassEncoder|GPUComputePassEncoder),(GPURenderPipeline|GPUComputePipeline)>}
		 */
		this._activePipelines = new WeakMap();

	}

	/**
	 * Sets the given pipeline for the given pass. The method makes sure to only set the
	 * pipeline when necessary.
	 *
	 * @param {(GPURenderPassEncoder|GPUComputePassEncoder)} pass - The pass encoder.
	 * @param {(GPURenderPipeline|GPUComputePipeline)} pipeline - The pipeline.
	 */
	setPipeline( pass, pipeline ) {

		const currentPipeline = this._activePipelines.get( pass );

		if ( currentPipeline !== pipeline ) {

			pass.setPipeline( pipeline );

			this._activePipelines.set( pass, pipeline );

		}

	}

	/**
	 * Returns the sample count derived from the given render context.
	 *
	 * @private
	 * @param {RenderContext} renderContext - The render context.
	 * @return {number} The sample count.
	 */
	_getSampleCount( renderContext ) {

		return this.backend.utils.getSampleCountRenderContext( renderContext );

	}

	/**
	 * Creates a render pipeline for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @param {Array<Promise>} promises - An array of compilation promises which are used in `compileAsync()`.
	 */
	createRenderPipeline( renderObject, promises ) {

		const { object, material, geometry, pipeline } = renderObject;
		const { vertexProgram, fragmentProgram } = pipeline;

		const backend = this.backend;
		const device = backend.device;
		const utils = backend.utils;

		const pipelineData = backend.get( pipeline );

		// bind group layouts

		const bindGroupLayouts = [];

		for ( const bindGroup of renderObject.getBindings() ) {

			const bindingsData = backend.get( bindGroup );

			bindGroupLayouts.push( bindingsData.layout );

		}

		// vertex buffers

		const vertexBuffers = backend.attributeUtils.createShaderVertexBuffers( renderObject );

		// blending

		let blending;

		if ( material.blending !== NoBlending && ( material.blending !== NormalBlending || material.transparent !== false ) ) {

			blending = this._getBlending( material );

		}

		// stencil

		let stencilFront = {};

		if ( material.stencilWrite === true ) {

			stencilFront = {
				compare: this._getStencilCompare( material ),
				failOp: this._getStencilOperation( material.stencilFail ),
				depthFailOp: this._getStencilOperation( material.stencilZFail ),
				passOp: this._getStencilOperation( material.stencilZPass )
			};

		}

		const colorWriteMask = this._getColorWriteMask( material );

		const targets = [];

		if ( renderObject.context.textures !== null ) {

			const textures = renderObject.context.textures;

			for ( let i = 0; i < textures.length; i ++ ) {

				const colorFormat = utils.getTextureFormatGPU( textures[ i ] );

				targets.push( {
					format: colorFormat,
					blend: blending,
					writeMask: colorWriteMask
				} );

			}

		} else {

			const colorFormat = utils.getCurrentColorFormat( renderObject.context );

			targets.push( {
				format: colorFormat,
				blend: blending,
				writeMask: colorWriteMask
			} );

		}

		const vertexModule = backend.get( vertexProgram ).module;
		const fragmentModule = backend.get( fragmentProgram ).module;

		const primitiveState = this._getPrimitiveState( object, geometry, material );
		const depthCompare = this._getDepthCompare( material );
		const depthStencilFormat = utils.getCurrentDepthStencilFormat( renderObject.context );

		const sampleCount = this._getSampleCount( renderObject.context );

		const pipelineDescriptor = {
			label: `renderPipeline_${ material.name || material.type }_${ material.id }`,
			vertex: Object.assign( {}, vertexModule, { buffers: vertexBuffers } ),
			fragment: Object.assign( {}, fragmentModule, { targets } ),
			primitive: primitiveState,
			multisample: {
				count: sampleCount,
				alphaToCoverageEnabled: material.alphaToCoverage && sampleCount > 1
			},
			layout: device.createPipelineLayout( {
				bindGroupLayouts
			} )
		};


		const depthStencil = {};
		const renderDepth = renderObject.context.depth;
		const renderStencil = renderObject.context.stencil;

		if ( renderDepth === true || renderStencil === true ) {

			if ( renderDepth === true ) {

				depthStencil.format = depthStencilFormat;
				depthStencil.depthWriteEnabled = material.depthWrite;
				depthStencil.depthCompare = depthCompare;

			}

			if ( renderStencil === true ) {

				depthStencil.stencilFront = stencilFront;
				depthStencil.stencilBack = {}; // three.js does not provide an API to configure the back function (gl.stencilFuncSeparate() was never used)
				depthStencil.stencilReadMask = material.stencilFuncMask;
				depthStencil.stencilWriteMask = material.stencilWriteMask;

			}

			if ( material.polygonOffset === true ) {

				depthStencil.depthBias = material.polygonOffsetUnits;
				depthStencil.depthBiasSlopeScale = material.polygonOffsetFactor;
				depthStencil.depthBiasClamp = 0; // three.js does not provide an API to configure this value

			}

			pipelineDescriptor.depthStencil = depthStencil;

		}


		if ( promises === null ) {

			pipelineData.pipeline = device.createRenderPipeline( pipelineDescriptor );

		} else {

			const p = new Promise( ( resolve /*, reject*/ ) => {

				device.createRenderPipelineAsync( pipelineDescriptor ).then( pipeline => {

					pipelineData.pipeline = pipeline;
					resolve();

				} );

			} );

			promises.push( p );

		}

	}

	/**
	 * Creates GPU render bundle encoder for the given render context.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @param {?string} [label='renderBundleEncoder'] - The label.
	 * @return {GPURenderBundleEncoder} The GPU render bundle encoder.
	 */
	createBundleEncoder( renderContext, label = 'renderBundleEncoder' ) {

		const backend = this.backend;
		const { utils, device } = backend;

		const depthStencilFormat = utils.getCurrentDepthStencilFormat( renderContext );
		const colorFormat = utils.getCurrentColorFormat( renderContext );
		const sampleCount = this._getSampleCount( renderContext );

		const descriptor = {
			label: label,
			colorFormats: [ colorFormat ],
			depthStencilFormat,
			sampleCount
		};

		return device.createRenderBundleEncoder( descriptor );

	}

	/**
	 * Creates a compute pipeline for the given compute node.
	 *
	 * @param {ComputePipeline} pipeline - The compute pipeline.
	 * @param {Array<BindGroup>} bindings - The bindings.
	 */
	createComputePipeline( pipeline, bindings ) {

		const backend = this.backend;
		const device = backend.device;

		const computeProgram = backend.get( pipeline.computeProgram ).module;

		const pipelineGPU = backend.get( pipeline );

		// bind group layouts

		const bindGroupLayouts = [];

		for ( const bindingsGroup of bindings ) {

			const bindingsData = backend.get( bindingsGroup );

			bindGroupLayouts.push( bindingsData.layout );

		}

		pipelineGPU.pipeline = device.createComputePipeline( {
			compute: computeProgram,
			layout: device.createPipelineLayout( {
				bindGroupLayouts
			} )
		} );

	}

	/**
	 * Returns the blending state as a descriptor object required
	 * for the pipeline creation.
	 *
	 * @private
	 * @param {Material} material - The material.
	 * @return {Object} The blending state.
	 */
	_getBlending( material ) {

		let color, alpha;

		const blending = material.blending;
		const blendSrc = material.blendSrc;
		const blendDst = material.blendDst;
		const blendEquation = material.blendEquation;


		if ( blending === CustomBlending ) {

			const blendSrcAlpha = material.blendSrcAlpha !== null ? material.blendSrcAlpha : blendSrc;
			const blendDstAlpha = material.blendDstAlpha !== null ? material.blendDstAlpha : blendDst;
			const blendEquationAlpha = material.blendEquationAlpha !== null ? material.blendEquationAlpha : blendEquation;

			color = {
				srcFactor: this._getBlendFactor( blendSrc ),
				dstFactor: this._getBlendFactor( blendDst ),
				operation: this._getBlendOperation( blendEquation )
			};

			alpha = {
				srcFactor: this._getBlendFactor( blendSrcAlpha ),
				dstFactor: this._getBlendFactor( blendDstAlpha ),
				operation: this._getBlendOperation( blendEquationAlpha )
			};

		} else {

			const premultipliedAlpha = material.premultipliedAlpha;

			const setBlend = ( srcRGB, dstRGB, srcAlpha, dstAlpha ) => {

				color = {
					srcFactor: srcRGB,
					dstFactor: dstRGB,
					operation: GPUBlendOperation.Add
				};

				alpha = {
					srcFactor: srcAlpha,
					dstFactor: dstAlpha,
					operation: GPUBlendOperation.Add
				};

			};

			if ( premultipliedAlpha ) {

				switch ( blending ) {

					case NormalBlending:
						setBlend( GPUBlendFactor.One, GPUBlendFactor.OneMinusSrcAlpha, GPUBlendFactor.One, GPUBlendFactor.OneMinusSrcAlpha );
						break;

					case AdditiveBlending:
						setBlend( GPUBlendFactor.One, GPUBlendFactor.One, GPUBlendFactor.One, GPUBlendFactor.One );
						break;

					case SubtractiveBlending:
						setBlend( GPUBlendFactor.Zero, GPUBlendFactor.OneMinusSrc, GPUBlendFactor.Zero, GPUBlendFactor.One );
						break;

					case MultiplyBlending:
						setBlend( GPUBlendFactor.Dst, GPUBlendFactor.OneMinusSrcAlpha, GPUBlendFactor.Zero, GPUBlendFactor.One );
						break;

				}

			} else {

				switch ( blending ) {

					case NormalBlending:
						setBlend( GPUBlendFactor.SrcAlpha, GPUBlendFactor.OneMinusSrcAlpha, GPUBlendFactor.One, GPUBlendFactor.OneMinusSrcAlpha );
						break;

					case AdditiveBlending:
						setBlend( GPUBlendFactor.SrcAlpha, GPUBlendFactor.One, GPUBlendFactor.One, GPUBlendFactor.One );
						break;

					case SubtractiveBlending:
						console.error( 'THREE.WebGPURenderer: SubtractiveBlending requires material.premultipliedAlpha = true' );
						break;

					case MultiplyBlending:
						console.error( 'THREE.WebGPURenderer: MultiplyBlending requires material.premultipliedAlpha = true' );
						break;

				}

			}

		}

		if ( color !== undefined && alpha !== undefined ) {

			return { color, alpha };

		} else {

			console.error( 'THREE.WebGPURenderer: Invalid blending: ', blending );

		}

	}
	/**
	 * Returns the GPU blend factor which is required for the pipeline creation.
	 *
	 * @private
	 * @param {number} blend - The blend factor as a three.js constant.
	 * @return {string} The GPU blend factor.
	 */
	_getBlendFactor( blend ) {

		let blendFactor;

		switch ( blend ) {

			case ZeroFactor:
				blendFactor = GPUBlendFactor.Zero;
				break;

			case OneFactor:
				blendFactor = GPUBlendFactor.One;
				break;

			case SrcColorFactor:
				blendFactor = GPUBlendFactor.Src;
				break;

			case OneMinusSrcColorFactor:
				blendFactor = GPUBlendFactor.OneMinusSrc;
				break;

			case SrcAlphaFactor:
				blendFactor = GPUBlendFactor.SrcAlpha;
				break;

			case OneMinusSrcAlphaFactor:
				blendFactor = GPUBlendFactor.OneMinusSrcAlpha;
				break;

			case DstColorFactor:
				blendFactor = GPUBlendFactor.Dst;
				break;

			case OneMinusDstColorFactor:
				blendFactor = GPUBlendFactor.OneMinusDst;
				break;

			case DstAlphaFactor:
				blendFactor = GPUBlendFactor.DstAlpha;
				break;

			case OneMinusDstAlphaFactor:
				blendFactor = GPUBlendFactor.OneMinusDstAlpha;
				break;

			case SrcAlphaSaturateFactor:
				blendFactor = GPUBlendFactor.SrcAlphaSaturated;
				break;

			case BlendColorFactor:
				blendFactor = GPUBlendFactor.Constant;
				break;

			case OneMinusBlendColorFactor:
				blendFactor = GPUBlendFactor.OneMinusConstant;
				break;

			default:
				console.error( 'THREE.WebGPURenderer: Blend factor not supported.', blend );

		}

		return blendFactor;

	}

	/**
	 * Returns the GPU stencil compare function which is required for the pipeline creation.
	 *
	 * @private
	 * @param {Material} material - The material.
	 * @return {string} The GPU stencil compare function.
	 */
	_getStencilCompare( material ) {

		let stencilCompare;

		const stencilFunc = material.stencilFunc;

		switch ( stencilFunc ) {

			case NeverStencilFunc:
				stencilCompare = GPUCompareFunction.Never;
				break;

			case AlwaysStencilFunc:
				stencilCompare = GPUCompareFunction.Always;
				break;

			case LessStencilFunc:
				stencilCompare = GPUCompareFunction.Less;
				break;

			case LessEqualStencilFunc:
				stencilCompare = GPUCompareFunction.LessEqual;
				break;

			case EqualStencilFunc:
				stencilCompare = GPUCompareFunction.Equal;
				break;

			case GreaterEqualStencilFunc:
				stencilCompare = GPUCompareFunction.GreaterEqual;
				break;

			case GreaterStencilFunc:
				stencilCompare = GPUCompareFunction.Greater;
				break;

			case NotEqualStencilFunc:
				stencilCompare = GPUCompareFunction.NotEqual;
				break;

			default:
				console.error( 'THREE.WebGPURenderer: Invalid stencil function.', stencilFunc );

		}

		return stencilCompare;

	}

	/**
	 * Returns the GPU stencil operation which is required for the pipeline creation.
	 *
	 * @private
	 * @param {number} op - A three.js constant defining the stencil operation.
	 * @return {string} The GPU stencil operation.
	 */
	_getStencilOperation( op ) {

		let stencilOperation;

		switch ( op ) {

			case KeepStencilOp:
				stencilOperation = GPUStencilOperation.Keep;
				break;

			case ZeroStencilOp:
				stencilOperation = GPUStencilOperation.Zero;
				break;

			case ReplaceStencilOp:
				stencilOperation = GPUStencilOperation.Replace;
				break;

			case InvertStencilOp:
				stencilOperation = GPUStencilOperation.Invert;
				break;

			case IncrementStencilOp:
				stencilOperation = GPUStencilOperation.IncrementClamp;
				break;

			case DecrementStencilOp:
				stencilOperation = GPUStencilOperation.DecrementClamp;
				break;

			case IncrementWrapStencilOp:
				stencilOperation = GPUStencilOperation.IncrementWrap;
				break;

			case DecrementWrapStencilOp:
				stencilOperation = GPUStencilOperation.DecrementWrap;
				break;

			default:
				console.error( 'THREE.WebGPURenderer: Invalid stencil operation.', stencilOperation );

		}

		return stencilOperation;

	}

	/**
	 * Returns the GPU blend operation which is required for the pipeline creation.
	 *
	 * @private
	 * @param {number} blendEquation - A three.js constant defining the blend equation.
	 * @return {string} The GPU blend operation.
	 */
	_getBlendOperation( blendEquation ) {

		let blendOperation;

		switch ( blendEquation ) {

			case AddEquation:
				blendOperation = GPUBlendOperation.Add;
				break;

			case SubtractEquation:
				blendOperation = GPUBlendOperation.Subtract;
				break;

			case ReverseSubtractEquation:
				blendOperation = GPUBlendOperation.ReverseSubtract;
				break;

			case MinEquation:
				blendOperation = GPUBlendOperation.Min;
				break;

			case MaxEquation:
				blendOperation = GPUBlendOperation.Max;
				break;

			default:
				console.error( 'THREE.WebGPUPipelineUtils: Blend equation not supported.', blendEquation );

		}

		return blendOperation;

	}

	/**
	 * Returns the primitive state as a descriptor object required
	 * for the pipeline creation.
	 *
	 * @private
	 * @param {Object3D} object - The 3D object.
	 * @param {BufferGeometry} geometry - The geometry.
	 * @param {Material} material - The material.
	 * @return {Object} The primitive state.
	 */
	_getPrimitiveState( object, geometry, material ) {

		const descriptor = {};
		const utils = this.backend.utils;

		descriptor.topology = utils.getPrimitiveTopology( object, material );

		if ( geometry.index !== null && object.isLine === true && object.isLineSegments !== true ) {

			descriptor.stripIndexFormat = ( geometry.index.array instanceof Uint16Array ) ? GPUIndexFormat.Uint16 : GPUIndexFormat.Uint32;

		}

		switch ( material.side ) {

			case FrontSide:
				descriptor.frontFace = GPUFrontFace.CCW;
				descriptor.cullMode = GPUCullMode.Back;
				break;

			case BackSide:
				descriptor.frontFace = GPUFrontFace.CCW;
				descriptor.cullMode = GPUCullMode.Front;
				break;

			case DoubleSide:
				descriptor.frontFace = GPUFrontFace.CCW;
				descriptor.cullMode = GPUCullMode.None;
				break;

			default:
				console.error( 'THREE.WebGPUPipelineUtils: Unknown material.side value.', material.side );
				break;

		}

		return descriptor;

	}

	/**
	 * Returns the GPU color write mask which is required for the pipeline creation.
	 *
	 * @private
	 * @param {Material} material - The material.
	 * @return {number} The GPU color write mask.
	 */
	_getColorWriteMask( material ) {

		return ( material.colorWrite === true ) ? GPUColorWriteFlags.All : GPUColorWriteFlags.None;

	}

	/**
	 * Returns the GPU depth compare function which is required for the pipeline creation.
	 *
	 * @private
	 * @param {Material} material - The material.
	 * @return {string} The GPU depth compare function.
	 */
	_getDepthCompare( material ) {

		let depthCompare;

		if ( material.depthTest === false ) {

			depthCompare = GPUCompareFunction.Always;

		} else {

			const depthFunc = material.depthFunc;

			switch ( depthFunc ) {

				case NeverDepth:
					depthCompare = GPUCompareFunction.Never;
					break;

				case AlwaysDepth:
					depthCompare = GPUCompareFunction.Always;
					break;

				case LessDepth:
					depthCompare = GPUCompareFunction.Less;
					break;

				case LessEqualDepth:
					depthCompare = GPUCompareFunction.LessEqual;
					break;

				case EqualDepth:
					depthCompare = GPUCompareFunction.Equal;
					break;

				case GreaterEqualDepth:
					depthCompare = GPUCompareFunction.GreaterEqual;
					break;

				case GreaterDepth:
					depthCompare = GPUCompareFunction.Greater;
					break;

				case NotEqualDepth:
					depthCompare = GPUCompareFunction.NotEqual;
					break;

				default:
					console.error( 'THREE.WebGPUPipelineUtils: Invalid depth function.', depthFunc );

			}

		}

		return depthCompare;

	}

}
```
</details>

#### Methods

##### `setPipeline(pass: any, pipeline: any): void`

<details><summary>Code</summary>

```ts
setPipeline( pass, pipeline ) {

		const currentPipeline = this._activePipelines.get( pass );

		if ( currentPipeline !== pipeline ) {

			pass.setPipeline( pipeline );

			this._activePipelines.set( pass, pipeline );

		}

	}
```
</details>

##### `_getSampleCount(renderContext: RenderContext): number`

<details><summary>Code</summary>

```ts
_getSampleCount( renderContext ) {

		return this.backend.utils.getSampleCountRenderContext( renderContext );

	}
```
</details>

##### `createRenderPipeline(renderObject: RenderObject, promises: Promise<any>[]): void`

<details><summary>Code</summary>

```ts
createRenderPipeline( renderObject, promises ) {

		const { object, material, geometry, pipeline } = renderObject;
		const { vertexProgram, fragmentProgram } = pipeline;

		const backend = this.backend;
		const device = backend.device;
		const utils = backend.utils;

		const pipelineData = backend.get( pipeline );

		// bind group layouts

		const bindGroupLayouts = [];

		for ( const bindGroup of renderObject.getBindings() ) {

			const bindingsData = backend.get( bindGroup );

			bindGroupLayouts.push( bindingsData.layout );

		}

		// vertex buffers

		const vertexBuffers = backend.attributeUtils.createShaderVertexBuffers( renderObject );

		// blending

		let blending;

		if ( material.blending !== NoBlending && ( material.blending !== NormalBlending || material.transparent !== false ) ) {

			blending = this._getBlending( material );

		}

		// stencil

		let stencilFront = {};

		if ( material.stencilWrite === true ) {

			stencilFront = {
				compare: this._getStencilCompare( material ),
				failOp: this._getStencilOperation( material.stencilFail ),
				depthFailOp: this._getStencilOperation( material.stencilZFail ),
				passOp: this._getStencilOperation( material.stencilZPass )
			};

		}

		const colorWriteMask = this._getColorWriteMask( material );

		const targets = [];

		if ( renderObject.context.textures !== null ) {

			const textures = renderObject.context.textures;

			for ( let i = 0; i < textures.length; i ++ ) {

				const colorFormat = utils.getTextureFormatGPU( textures[ i ] );

				targets.push( {
					format: colorFormat,
					blend: blending,
					writeMask: colorWriteMask
				} );

			}

		} else {

			const colorFormat = utils.getCurrentColorFormat( renderObject.context );

			targets.push( {
				format: colorFormat,
				blend: blending,
				writeMask: colorWriteMask
			} );

		}

		const vertexModule = backend.get( vertexProgram ).module;
		const fragmentModule = backend.get( fragmentProgram ).module;

		const primitiveState = this._getPrimitiveState( object, geometry, material );
		const depthCompare = this._getDepthCompare( material );
		const depthStencilFormat = utils.getCurrentDepthStencilFormat( renderObject.context );

		const sampleCount = this._getSampleCount( renderObject.context );

		const pipelineDescriptor = {
			label: `renderPipeline_${ material.name || material.type }_${ material.id }`,
			vertex: Object.assign( {}, vertexModule, { buffers: vertexBuffers } ),
			fragment: Object.assign( {}, fragmentModule, { targets } ),
			primitive: primitiveState,
			multisample: {
				count: sampleCount,
				alphaToCoverageEnabled: material.alphaToCoverage && sampleCount > 1
			},
			layout: device.createPipelineLayout( {
				bindGroupLayouts
			} )
		};


		const depthStencil = {};
		const renderDepth = renderObject.context.depth;
		const renderStencil = renderObject.context.stencil;

		if ( renderDepth === true || renderStencil === true ) {

			if ( renderDepth === true ) {

				depthStencil.format = depthStencilFormat;
				depthStencil.depthWriteEnabled = material.depthWrite;
				depthStencil.depthCompare = depthCompare;

			}

			if ( renderStencil === true ) {

				depthStencil.stencilFront = stencilFront;
				depthStencil.stencilBack = {}; // three.js does not provide an API to configure the back function (gl.stencilFuncSeparate() was never used)
				depthStencil.stencilReadMask = material.stencilFuncMask;
				depthStencil.stencilWriteMask = material.stencilWriteMask;

			}

			if ( material.polygonOffset === true ) {

				depthStencil.depthBias = material.polygonOffsetUnits;
				depthStencil.depthBiasSlopeScale = material.polygonOffsetFactor;
				depthStencil.depthBiasClamp = 0; // three.js does not provide an API to configure this value

			}

			pipelineDescriptor.depthStencil = depthStencil;

		}


		if ( promises === null ) {

			pipelineData.pipeline = device.createRenderPipeline( pipelineDescriptor );

		} else {

			const p = new Promise( ( resolve /*, reject*/ ) => {

				device.createRenderPipelineAsync( pipelineDescriptor ).then( pipeline => {

					pipelineData.pipeline = pipeline;
					resolve();

				} );

			} );

			promises.push( p );

		}

	}
```
</details>

##### `createBundleEncoder(renderContext: RenderContext, label: string): GPURenderBundleEncoder`

<details><summary>Code</summary>

```ts
createBundleEncoder( renderContext, label = 'renderBundleEncoder' ) {

		const backend = this.backend;
		const { utils, device } = backend;

		const depthStencilFormat = utils.getCurrentDepthStencilFormat( renderContext );
		const colorFormat = utils.getCurrentColorFormat( renderContext );
		const sampleCount = this._getSampleCount( renderContext );

		const descriptor = {
			label: label,
			colorFormats: [ colorFormat ],
			depthStencilFormat,
			sampleCount
		};

		return device.createRenderBundleEncoder( descriptor );

	}
```
</details>

##### `createComputePipeline(pipeline: ComputePipeline, bindings: BindGroup[]): void`

<details><summary>Code</summary>

```ts
createComputePipeline( pipeline, bindings ) {

		const backend = this.backend;
		const device = backend.device;

		const computeProgram = backend.get( pipeline.computeProgram ).module;

		const pipelineGPU = backend.get( pipeline );

		// bind group layouts

		const bindGroupLayouts = [];

		for ( const bindingsGroup of bindings ) {

			const bindingsData = backend.get( bindingsGroup );

			bindGroupLayouts.push( bindingsData.layout );

		}

		pipelineGPU.pipeline = device.createComputePipeline( {
			compute: computeProgram,
			layout: device.createPipelineLayout( {
				bindGroupLayouts
			} )
		} );

	}
```
</details>

##### `_getBlending(material: Material): any`

<details><summary>Code</summary>

```ts
_getBlending( material ) {

		let color, alpha;

		const blending = material.blending;
		const blendSrc = material.blendSrc;
		const blendDst = material.blendDst;
		const blendEquation = material.blendEquation;


		if ( blending === CustomBlending ) {

			const blendSrcAlpha = material.blendSrcAlpha !== null ? material.blendSrcAlpha : blendSrc;
			const blendDstAlpha = material.blendDstAlpha !== null ? material.blendDstAlpha : blendDst;
			const blendEquationAlpha = material.blendEquationAlpha !== null ? material.blendEquationAlpha : blendEquation;

			color = {
				srcFactor: this._getBlendFactor( blendSrc ),
				dstFactor: this._getBlendFactor( blendDst ),
				operation: this._getBlendOperation( blendEquation )
			};

			alpha = {
				srcFactor: this._getBlendFactor( blendSrcAlpha ),
				dstFactor: this._getBlendFactor( blendDstAlpha ),
				operation: this._getBlendOperation( blendEquationAlpha )
			};

		} else {

			const premultipliedAlpha = material.premultipliedAlpha;

			const setBlend = ( srcRGB, dstRGB, srcAlpha, dstAlpha ) => {

				color = {
					srcFactor: srcRGB,
					dstFactor: dstRGB,
					operation: GPUBlendOperation.Add
				};

				alpha = {
					srcFactor: srcAlpha,
					dstFactor: dstAlpha,
					operation: GPUBlendOperation.Add
				};

			};

			if ( premultipliedAlpha ) {

				switch ( blending ) {

					case NormalBlending:
						setBlend( GPUBlendFactor.One, GPUBlendFactor.OneMinusSrcAlpha, GPUBlendFactor.One, GPUBlendFactor.OneMinusSrcAlpha );
						break;

					case AdditiveBlending:
						setBlend( GPUBlendFactor.One, GPUBlendFactor.One, GPUBlendFactor.One, GPUBlendFactor.One );
						break;

					case SubtractiveBlending:
						setBlend( GPUBlendFactor.Zero, GPUBlendFactor.OneMinusSrc, GPUBlendFactor.Zero, GPUBlendFactor.One );
						break;

					case MultiplyBlending:
						setBlend( GPUBlendFactor.Dst, GPUBlendFactor.OneMinusSrcAlpha, GPUBlendFactor.Zero, GPUBlendFactor.One );
						break;

				}

			} else {

				switch ( blending ) {

					case NormalBlending:
						setBlend( GPUBlendFactor.SrcAlpha, GPUBlendFactor.OneMinusSrcAlpha, GPUBlendFactor.One, GPUBlendFactor.OneMinusSrcAlpha );
						break;

					case AdditiveBlending:
						setBlend( GPUBlendFactor.SrcAlpha, GPUBlendFactor.One, GPUBlendFactor.One, GPUBlendFactor.One );
						break;

					case SubtractiveBlending:
						console.error( 'THREE.WebGPURenderer: SubtractiveBlending requires material.premultipliedAlpha = true' );
						break;

					case MultiplyBlending:
						console.error( 'THREE.WebGPURenderer: MultiplyBlending requires material.premultipliedAlpha = true' );
						break;

				}

			}

		}

		if ( color !== undefined && alpha !== undefined ) {

			return { color, alpha };

		} else {

			console.error( 'THREE.WebGPURenderer: Invalid blending: ', blending );

		}

	}
```
</details>

##### `_getBlendFactor(blend: number): string`

<details><summary>Code</summary>

```ts
_getBlendFactor( blend ) {

		let blendFactor;

		switch ( blend ) {

			case ZeroFactor:
				blendFactor = GPUBlendFactor.Zero;
				break;

			case OneFactor:
				blendFactor = GPUBlendFactor.One;
				break;

			case SrcColorFactor:
				blendFactor = GPUBlendFactor.Src;
				break;

			case OneMinusSrcColorFactor:
				blendFactor = GPUBlendFactor.OneMinusSrc;
				break;

			case SrcAlphaFactor:
				blendFactor = GPUBlendFactor.SrcAlpha;
				break;

			case OneMinusSrcAlphaFactor:
				blendFactor = GPUBlendFactor.OneMinusSrcAlpha;
				break;

			case DstColorFactor:
				blendFactor = GPUBlendFactor.Dst;
				break;

			case OneMinusDstColorFactor:
				blendFactor = GPUBlendFactor.OneMinusDst;
				break;

			case DstAlphaFactor:
				blendFactor = GPUBlendFactor.DstAlpha;
				break;

			case OneMinusDstAlphaFactor:
				blendFactor = GPUBlendFactor.OneMinusDstAlpha;
				break;

			case SrcAlphaSaturateFactor:
				blendFactor = GPUBlendFactor.SrcAlphaSaturated;
				break;

			case BlendColorFactor:
				blendFactor = GPUBlendFactor.Constant;
				break;

			case OneMinusBlendColorFactor:
				blendFactor = GPUBlendFactor.OneMinusConstant;
				break;

			default:
				console.error( 'THREE.WebGPURenderer: Blend factor not supported.', blend );

		}

		return blendFactor;

	}
```
</details>

##### `_getStencilCompare(material: Material): string`

<details><summary>Code</summary>

```ts
_getStencilCompare( material ) {

		let stencilCompare;

		const stencilFunc = material.stencilFunc;

		switch ( stencilFunc ) {

			case NeverStencilFunc:
				stencilCompare = GPUCompareFunction.Never;
				break;

			case AlwaysStencilFunc:
				stencilCompare = GPUCompareFunction.Always;
				break;

			case LessStencilFunc:
				stencilCompare = GPUCompareFunction.Less;
				break;

			case LessEqualStencilFunc:
				stencilCompare = GPUCompareFunction.LessEqual;
				break;

			case EqualStencilFunc:
				stencilCompare = GPUCompareFunction.Equal;
				break;

			case GreaterEqualStencilFunc:
				stencilCompare = GPUCompareFunction.GreaterEqual;
				break;

			case GreaterStencilFunc:
				stencilCompare = GPUCompareFunction.Greater;
				break;

			case NotEqualStencilFunc:
				stencilCompare = GPUCompareFunction.NotEqual;
				break;

			default:
				console.error( 'THREE.WebGPURenderer: Invalid stencil function.', stencilFunc );

		}

		return stencilCompare;

	}
```
</details>

##### `_getStencilOperation(op: number): string`

<details><summary>Code</summary>

```ts
_getStencilOperation( op ) {

		let stencilOperation;

		switch ( op ) {

			case KeepStencilOp:
				stencilOperation = GPUStencilOperation.Keep;
				break;

			case ZeroStencilOp:
				stencilOperation = GPUStencilOperation.Zero;
				break;

			case ReplaceStencilOp:
				stencilOperation = GPUStencilOperation.Replace;
				break;

			case InvertStencilOp:
				stencilOperation = GPUStencilOperation.Invert;
				break;

			case IncrementStencilOp:
				stencilOperation = GPUStencilOperation.IncrementClamp;
				break;

			case DecrementStencilOp:
				stencilOperation = GPUStencilOperation.DecrementClamp;
				break;

			case IncrementWrapStencilOp:
				stencilOperation = GPUStencilOperation.IncrementWrap;
				break;

			case DecrementWrapStencilOp:
				stencilOperation = GPUStencilOperation.DecrementWrap;
				break;

			default:
				console.error( 'THREE.WebGPURenderer: Invalid stencil operation.', stencilOperation );

		}

		return stencilOperation;

	}
```
</details>

##### `_getBlendOperation(blendEquation: number): string`

<details><summary>Code</summary>

```ts
_getBlendOperation( blendEquation ) {

		let blendOperation;

		switch ( blendEquation ) {

			case AddEquation:
				blendOperation = GPUBlendOperation.Add;
				break;

			case SubtractEquation:
				blendOperation = GPUBlendOperation.Subtract;
				break;

			case ReverseSubtractEquation:
				blendOperation = GPUBlendOperation.ReverseSubtract;
				break;

			case MinEquation:
				blendOperation = GPUBlendOperation.Min;
				break;

			case MaxEquation:
				blendOperation = GPUBlendOperation.Max;
				break;

			default:
				console.error( 'THREE.WebGPUPipelineUtils: Blend equation not supported.', blendEquation );

		}

		return blendOperation;

	}
```
</details>

##### `_getPrimitiveState(object: Object3D, geometry: BufferGeometry, material: Material): any`

<details><summary>Code</summary>

```ts
_getPrimitiveState( object, geometry, material ) {

		const descriptor = {};
		const utils = this.backend.utils;

		descriptor.topology = utils.getPrimitiveTopology( object, material );

		if ( geometry.index !== null && object.isLine === true && object.isLineSegments !== true ) {

			descriptor.stripIndexFormat = ( geometry.index.array instanceof Uint16Array ) ? GPUIndexFormat.Uint16 : GPUIndexFormat.Uint32;

		}

		switch ( material.side ) {

			case FrontSide:
				descriptor.frontFace = GPUFrontFace.CCW;
				descriptor.cullMode = GPUCullMode.Back;
				break;

			case BackSide:
				descriptor.frontFace = GPUFrontFace.CCW;
				descriptor.cullMode = GPUCullMode.Front;
				break;

			case DoubleSide:
				descriptor.frontFace = GPUFrontFace.CCW;
				descriptor.cullMode = GPUCullMode.None;
				break;

			default:
				console.error( 'THREE.WebGPUPipelineUtils: Unknown material.side value.', material.side );
				break;

		}

		return descriptor;

	}
```
</details>

##### `_getColorWriteMask(material: Material): number`

<details><summary>Code</summary>

```ts
_getColorWriteMask( material ) {

		return ( material.colorWrite === true ) ? GPUColorWriteFlags.All : GPUColorWriteFlags.None;

	}
```
</details>

##### `_getDepthCompare(material: Material): string`

<details><summary>Code</summary>

```ts
_getDepthCompare( material ) {

		let depthCompare;

		if ( material.depthTest === false ) {

			depthCompare = GPUCompareFunction.Always;

		} else {

			const depthFunc = material.depthFunc;

			switch ( depthFunc ) {

				case NeverDepth:
					depthCompare = GPUCompareFunction.Never;
					break;

				case AlwaysDepth:
					depthCompare = GPUCompareFunction.Always;
					break;

				case LessDepth:
					depthCompare = GPUCompareFunction.Less;
					break;

				case LessEqualDepth:
					depthCompare = GPUCompareFunction.LessEqual;
					break;

				case EqualDepth:
					depthCompare = GPUCompareFunction.Equal;
					break;

				case GreaterEqualDepth:
					depthCompare = GPUCompareFunction.GreaterEqual;
					break;

				case GreaterDepth:
					depthCompare = GPUCompareFunction.Greater;
					break;

				case NotEqualDepth:
					depthCompare = GPUCompareFunction.NotEqual;
					break;

				default:
					console.error( 'THREE.WebGPUPipelineUtils: Invalid depth function.', depthFunc );

			}

		}

		return depthCompare;

	}
```
</details>


---