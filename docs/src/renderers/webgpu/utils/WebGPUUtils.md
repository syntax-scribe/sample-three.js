[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `WebGPUUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgpu/utils/WebGPUUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `HalfFloatType` | `../../../constants.js` |
| `UnsignedByteType` | `../../../constants.js` |
| `GPUPrimitiveTopology` | `./WebGPUConstants.js` |
| `GPUTextureFormat` | `./WebGPUConstants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `format` | `any` | let/var | `*not shown*` | ✗ |
| `samples` | `any` | let/var | `*not shown*` | ✗ |
| `renderer` | `any` | let/var | `this.backend.renderer` | ✗ |
| `isMSAA` | `boolean` | let/var | `samples > 1 && texture.renderTarget !== null && ( texture.isDepthTexture !== ...` | ✗ |
| `primarySamples` | `any` | let/var | `isMSAA ? 1 : samples` | ✗ |
| `format` | `any` | let/var | `*not shown*` | ✗ |
| `outputType` | `any` | let/var | `this.backend.parameters.outputType` | ✗ |


---

## Functions

### `WebGPUUtils.getCurrentDepthStencilFormat(renderContext: RenderContext): string`

**JSDoc:**
```typescript
/**
	 * Returns the depth/stencil GPU format for the given render context.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @return {string} The depth/stencil GPU texture format.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`

**Returns:** `string`

**Calls:**

- `this.getTextureFormatGPU`

<details><summary>Code</summary>

```typescript
getCurrentDepthStencilFormat( renderContext ) {

		let format;

		if ( renderContext.depthTexture !== null ) {

			format = this.getTextureFormatGPU( renderContext.depthTexture );

		} else if ( renderContext.depth && renderContext.stencil ) {

			format = GPUTextureFormat.Depth24PlusStencil8;

		} else if ( renderContext.depth ) {

			format = GPUTextureFormat.Depth24Plus;

		}

		return format;

	}
```
</details>

### `WebGPUUtils.getTextureFormatGPU(texture: Texture): string`

**JSDoc:**
```typescript
/**
	 * Returns the GPU format for the given texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @return {string} The GPU texture format.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `string`

**Calls:**

- `this.backend.get`

<details><summary>Code</summary>

```typescript
getTextureFormatGPU( texture ) {

		return this.backend.get( texture ).format;

	}
```
</details>

### `WebGPUUtils.getTextureSampleData(texture: Texture): any`

**JSDoc:**
```typescript
/**
	 * Returns an object that defines the multi-sampling state of the given texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @return {Object} The multi-sampling state.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `any`

**Calls:**

- `renderer.getRenderTarget`

<details><summary>Code</summary>

```typescript
getTextureSampleData( texture ) {

		let samples;

		if ( texture.isFramebufferTexture ) {

			samples = 1;

		} else if ( texture.isDepthTexture && ! texture.renderTarget ) {

			const renderer = this.backend.renderer;
			const renderTarget = renderer.getRenderTarget();

			samples = renderTarget ? renderTarget.samples : renderer.samples;

		} else if ( texture.renderTarget ) {

			samples = texture.renderTarget.samples;

		}

		samples = samples || 1;

		const isMSAA = samples > 1 && texture.renderTarget !== null && ( texture.isDepthTexture !== true && texture.isFramebufferTexture !== true );
		const primarySamples = isMSAA ? 1 : samples;

		return { samples, primarySamples, isMSAA };

	}
```
</details>

### `WebGPUUtils.getCurrentColorFormat(renderContext: RenderContext): string`

**JSDoc:**
```typescript
/**
	 * Returns the default color attachment's GPU format of the current render context.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @return {string} The GPU texture format of the default color attachment.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`

**Returns:** `string`

**Calls:**

- `this.getTextureFormatGPU`
- `this.getPreferredCanvasFormat`

<details><summary>Code</summary>

```typescript
getCurrentColorFormat( renderContext ) {

		let format;

		if ( renderContext.textures !== null ) {

			format = this.getTextureFormatGPU( renderContext.textures[ 0 ] );

		} else {

			format = this.getPreferredCanvasFormat(); // default context format

		}

		return format;

	}
```
</details>

### `WebGPUUtils.getCurrentColorSpace(renderContext: RenderContext): string`

**JSDoc:**
```typescript
/**
	 * Returns the output color space of the current render context.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @return {string} The output color space.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getCurrentColorSpace( renderContext ) {

		if ( renderContext.textures !== null ) {

			return renderContext.textures[ 0 ].colorSpace;

		}

		return this.backend.renderer.outputColorSpace;

	}
```
</details>

### `WebGPUUtils.getPrimitiveTopology(object: Object3D, material: Material): string`

**JSDoc:**
```typescript
/**
	 * Returns GPU primitive topology for the given object and material.
	 *
	 * @param {Object3D} object - The 3D object.
	 * @param {Material} material - The material.
	 * @return {string} The GPU primitive topology.
	 */
```

**Parameters:**

- **`object`** `Object3D`
- **`material`** `Material`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getPrimitiveTopology( object, material ) {

		if ( object.isPoints ) return GPUPrimitiveTopology.PointList;
		else if ( object.isLineSegments || ( object.isMesh && material.wireframe === true ) ) return GPUPrimitiveTopology.LineList;
		else if ( object.isLine ) return GPUPrimitiveTopology.LineStrip;
		else if ( object.isMesh ) return GPUPrimitiveTopology.TriangleList;

	}
```
</details>

### `WebGPUUtils.getSampleCount(sampleCount: number): number`

**JSDoc:**
```typescript
/**
	 * Returns a modified sample count from the given sample count value.
	 *
	 * That is required since WebGPU only supports either 1 or 4.
	 *
	 * @param {number} sampleCount - The input sample count.
	 * @return {number} The (potentially updated) output sample count.
	 */
```

**Parameters:**

- **`sampleCount`** `number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getSampleCount( sampleCount ) {

		return sampleCount >= 4 ? 4 : 1;

	}
```
</details>

### `WebGPUUtils.getSampleCountRenderContext(renderContext: RenderContext): number`

**JSDoc:**
```typescript
/**
	 * Returns the sample count of the given render context.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @return {number} The sample count.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`

**Returns:** `number`

**Calls:**

- `this.getSampleCount`

<details><summary>Code</summary>

```typescript
getSampleCountRenderContext( renderContext ) {

		if ( renderContext.textures !== null ) {

			return this.getSampleCount( renderContext.sampleCount );

		}

		return this.getSampleCount( this.backend.renderer.samples );

	}
```
</details>

### `WebGPUUtils.getPreferredCanvasFormat(): string`

**JSDoc:**
```typescript
/**
	 * Returns the preferred canvas format.
	 *
	 * There is a separate method for this so it's possible to
	 * honor edge cases for specific devices.
	 *
	 * @return {string} The GPU texture format of the canvas.
	 */
```

**Returns:** `string`

**Calls:**

- `navigator.gpu.getPreferredCanvasFormat`

<details><summary>Code</summary>

```typescript
getPreferredCanvasFormat() {

		const outputType = this.backend.parameters.outputType;

		if ( outputType === undefined ) {

			return navigator.gpu.getPreferredCanvasFormat();

		} else if ( outputType === UnsignedByteType ) {

			return GPUTextureFormat.BGRA8Unorm;

		} else if ( outputType === HalfFloatType ) {

			return GPUTextureFormat.RGBA16Float;

		} else {

			throw new Error( 'Unsupported outputType' );

		}

	}
```
</details>


---

## Classes

### `WebGPUUtils`

<details><summary>Class Code</summary>

```ts
class WebGPUUtils {

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

	}

	/**
	 * Returns the depth/stencil GPU format for the given render context.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @return {string} The depth/stencil GPU texture format.
	 */
	getCurrentDepthStencilFormat( renderContext ) {

		let format;

		if ( renderContext.depthTexture !== null ) {

			format = this.getTextureFormatGPU( renderContext.depthTexture );

		} else if ( renderContext.depth && renderContext.stencil ) {

			format = GPUTextureFormat.Depth24PlusStencil8;

		} else if ( renderContext.depth ) {

			format = GPUTextureFormat.Depth24Plus;

		}

		return format;

	}

	/**
	 * Returns the GPU format for the given texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @return {string} The GPU texture format.
	 */
	getTextureFormatGPU( texture ) {

		return this.backend.get( texture ).format;

	}

	/**
	 * Returns an object that defines the multi-sampling state of the given texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @return {Object} The multi-sampling state.
	 */
	getTextureSampleData( texture ) {

		let samples;

		if ( texture.isFramebufferTexture ) {

			samples = 1;

		} else if ( texture.isDepthTexture && ! texture.renderTarget ) {

			const renderer = this.backend.renderer;
			const renderTarget = renderer.getRenderTarget();

			samples = renderTarget ? renderTarget.samples : renderer.samples;

		} else if ( texture.renderTarget ) {

			samples = texture.renderTarget.samples;

		}

		samples = samples || 1;

		const isMSAA = samples > 1 && texture.renderTarget !== null && ( texture.isDepthTexture !== true && texture.isFramebufferTexture !== true );
		const primarySamples = isMSAA ? 1 : samples;

		return { samples, primarySamples, isMSAA };

	}

	/**
	 * Returns the default color attachment's GPU format of the current render context.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @return {string} The GPU texture format of the default color attachment.
	 */
	getCurrentColorFormat( renderContext ) {

		let format;

		if ( renderContext.textures !== null ) {

			format = this.getTextureFormatGPU( renderContext.textures[ 0 ] );

		} else {

			format = this.getPreferredCanvasFormat(); // default context format

		}

		return format;

	}

	/**
	 * Returns the output color space of the current render context.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @return {string} The output color space.
	 */
	getCurrentColorSpace( renderContext ) {

		if ( renderContext.textures !== null ) {

			return renderContext.textures[ 0 ].colorSpace;

		}

		return this.backend.renderer.outputColorSpace;

	}

	/**
	 * Returns GPU primitive topology for the given object and material.
	 *
	 * @param {Object3D} object - The 3D object.
	 * @param {Material} material - The material.
	 * @return {string} The GPU primitive topology.
	 */
	getPrimitiveTopology( object, material ) {

		if ( object.isPoints ) return GPUPrimitiveTopology.PointList;
		else if ( object.isLineSegments || ( object.isMesh && material.wireframe === true ) ) return GPUPrimitiveTopology.LineList;
		else if ( object.isLine ) return GPUPrimitiveTopology.LineStrip;
		else if ( object.isMesh ) return GPUPrimitiveTopology.TriangleList;

	}

	/**
	 * Returns a modified sample count from the given sample count value.
	 *
	 * That is required since WebGPU only supports either 1 or 4.
	 *
	 * @param {number} sampleCount - The input sample count.
	 * @return {number} The (potentially updated) output sample count.
	 */
	getSampleCount( sampleCount ) {

		return sampleCount >= 4 ? 4 : 1;

	}

	/**
	 * Returns the sample count of the given render context.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @return {number} The sample count.
	 */
	getSampleCountRenderContext( renderContext ) {

		if ( renderContext.textures !== null ) {

			return this.getSampleCount( renderContext.sampleCount );

		}

		return this.getSampleCount( this.backend.renderer.samples );

	}

	/**
	 * Returns the preferred canvas format.
	 *
	 * There is a separate method for this so it's possible to
	 * honor edge cases for specific devices.
	 *
	 * @return {string} The GPU texture format of the canvas.
	 */
	getPreferredCanvasFormat() {

		const outputType = this.backend.parameters.outputType;

		if ( outputType === undefined ) {

			return navigator.gpu.getPreferredCanvasFormat();

		} else if ( outputType === UnsignedByteType ) {

			return GPUTextureFormat.BGRA8Unorm;

		} else if ( outputType === HalfFloatType ) {

			return GPUTextureFormat.RGBA16Float;

		} else {

			throw new Error( 'Unsupported outputType' );

		}

	}

}
```
</details>

#### Methods

##### `getCurrentDepthStencilFormat(renderContext: RenderContext): string`

<details><summary>Code</summary>

```ts
getCurrentDepthStencilFormat( renderContext ) {

		let format;

		if ( renderContext.depthTexture !== null ) {

			format = this.getTextureFormatGPU( renderContext.depthTexture );

		} else if ( renderContext.depth && renderContext.stencil ) {

			format = GPUTextureFormat.Depth24PlusStencil8;

		} else if ( renderContext.depth ) {

			format = GPUTextureFormat.Depth24Plus;

		}

		return format;

	}
```
</details>

##### `getTextureFormatGPU(texture: Texture): string`

<details><summary>Code</summary>

```ts
getTextureFormatGPU( texture ) {

		return this.backend.get( texture ).format;

	}
```
</details>

##### `getTextureSampleData(texture: Texture): any`

<details><summary>Code</summary>

```ts
getTextureSampleData( texture ) {

		let samples;

		if ( texture.isFramebufferTexture ) {

			samples = 1;

		} else if ( texture.isDepthTexture && ! texture.renderTarget ) {

			const renderer = this.backend.renderer;
			const renderTarget = renderer.getRenderTarget();

			samples = renderTarget ? renderTarget.samples : renderer.samples;

		} else if ( texture.renderTarget ) {

			samples = texture.renderTarget.samples;

		}

		samples = samples || 1;

		const isMSAA = samples > 1 && texture.renderTarget !== null && ( texture.isDepthTexture !== true && texture.isFramebufferTexture !== true );
		const primarySamples = isMSAA ? 1 : samples;

		return { samples, primarySamples, isMSAA };

	}
```
</details>

##### `getCurrentColorFormat(renderContext: RenderContext): string`

<details><summary>Code</summary>

```ts
getCurrentColorFormat( renderContext ) {

		let format;

		if ( renderContext.textures !== null ) {

			format = this.getTextureFormatGPU( renderContext.textures[ 0 ] );

		} else {

			format = this.getPreferredCanvasFormat(); // default context format

		}

		return format;

	}
```
</details>

##### `getCurrentColorSpace(renderContext: RenderContext): string`

<details><summary>Code</summary>

```ts
getCurrentColorSpace( renderContext ) {

		if ( renderContext.textures !== null ) {

			return renderContext.textures[ 0 ].colorSpace;

		}

		return this.backend.renderer.outputColorSpace;

	}
```
</details>

##### `getPrimitiveTopology(object: Object3D, material: Material): string`

<details><summary>Code</summary>

```ts
getPrimitiveTopology( object, material ) {

		if ( object.isPoints ) return GPUPrimitiveTopology.PointList;
		else if ( object.isLineSegments || ( object.isMesh && material.wireframe === true ) ) return GPUPrimitiveTopology.LineList;
		else if ( object.isLine ) return GPUPrimitiveTopology.LineStrip;
		else if ( object.isMesh ) return GPUPrimitiveTopology.TriangleList;

	}
```
</details>

##### `getSampleCount(sampleCount: number): number`

<details><summary>Code</summary>

```ts
getSampleCount( sampleCount ) {

		return sampleCount >= 4 ? 4 : 1;

	}
```
</details>

##### `getSampleCountRenderContext(renderContext: RenderContext): number`

<details><summary>Code</summary>

```ts
getSampleCountRenderContext( renderContext ) {

		if ( renderContext.textures !== null ) {

			return this.getSampleCount( renderContext.sampleCount );

		}

		return this.getSampleCount( this.backend.renderer.samples );

	}
```
</details>

##### `getPreferredCanvasFormat(): string`

<details><summary>Code</summary>

```ts
getPreferredCanvasFormat() {

		const outputType = this.backend.parameters.outputType;

		if ( outputType === undefined ) {

			return navigator.gpu.getPreferredCanvasFormat();

		} else if ( outputType === UnsignedByteType ) {

			return GPUTextureFormat.BGRA8Unorm;

		} else if ( outputType === HalfFloatType ) {

			return GPUTextureFormat.RGBA16Float;

		} else {

			throw new Error( 'Unsupported outputType' );

		}

	}
```
</details>


---