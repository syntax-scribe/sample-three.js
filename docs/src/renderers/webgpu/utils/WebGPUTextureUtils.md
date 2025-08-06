[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `WebGPUTextureUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 26 |
| 🧱 Classes | 1 |
| 📦 Imports | 63 |
| 📊 Variables & Constants | 49 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgpu/utils/WebGPUTextureUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `GPUTextureFormat` | `./WebGPUConstants.js` |
| `GPUAddressMode` | `./WebGPUConstants.js` |
| `GPUFilterMode` | `./WebGPUConstants.js` |
| `GPUTextureDimension` | `./WebGPUConstants.js` |
| `GPUFeatureName` | `./WebGPUConstants.js` |
| `GPUTextureViewDimension` | `./WebGPUConstants.js` |
| `ColorManagement` | `../../../math/ColorManagement.js` |
| `WebGPUTexturePassUtils` | `./WebGPUTexturePassUtils.js` |
| `ByteType` | `../../../constants.js` |
| `ShortType` | `../../../constants.js` |
| `NearestFilter` | `../../../constants.js` |
| `NearestMipmapNearestFilter` | `../../../constants.js` |
| `NearestMipmapLinearFilter` | `../../../constants.js` |
| `RepeatWrapping` | `../../../constants.js` |
| `MirroredRepeatWrapping` | `../../../constants.js` |
| `RGB_ETC2_Format` | `../../../constants.js` |
| `RGBA_ETC2_EAC_Format` | `../../../constants.js` |
| `RGBAFormat` | `../../../constants.js` |
| `RGBFormat` | `../../../constants.js` |
| `RedFormat` | `../../../constants.js` |
| `RGFormat` | `../../../constants.js` |
| `RGBA_S3TC_DXT1_Format` | `../../../constants.js` |
| `RGBA_S3TC_DXT3_Format` | `../../../constants.js` |
| `RGBA_S3TC_DXT5_Format` | `../../../constants.js` |
| `UnsignedByteType` | `../../../constants.js` |
| `FloatType` | `../../../constants.js` |
| `HalfFloatType` | `../../../constants.js` |
| `SRGBTransfer` | `../../../constants.js` |
| `DepthFormat` | `../../../constants.js` |
| `DepthStencilFormat` | `../../../constants.js` |
| `RGBA_ASTC_4x4_Format` | `../../../constants.js` |
| `RGBA_ASTC_5x4_Format` | `../../../constants.js` |
| `RGBA_ASTC_5x5_Format` | `../../../constants.js` |
| `RGBA_ASTC_6x5_Format` | `../../../constants.js` |
| `RGBA_ASTC_6x6_Format` | `../../../constants.js` |
| `RGBA_ASTC_8x5_Format` | `../../../constants.js` |
| `RGBA_ASTC_8x6_Format` | `../../../constants.js` |
| `RGBA_ASTC_8x8_Format` | `../../../constants.js` |
| `RGBA_ASTC_10x5_Format` | `../../../constants.js` |
| `RGBA_ASTC_10x6_Format` | `../../../constants.js` |
| `RGBA_ASTC_10x8_Format` | `../../../constants.js` |
| `RGBA_ASTC_10x10_Format` | `../../../constants.js` |
| `RGBA_ASTC_12x10_Format` | `../../../constants.js` |
| `RGBA_ASTC_12x12_Format` | `../../../constants.js` |
| `UnsignedIntType` | `../../../constants.js` |
| `UnsignedShortType` | `../../../constants.js` |
| `UnsignedInt248Type` | `../../../constants.js` |
| `UnsignedInt5999Type` | `../../../constants.js` |
| `NeverCompare` | `../../../constants.js` |
| `AlwaysCompare` | `../../../constants.js` |
| `LessCompare` | `../../../constants.js` |
| `LessEqualCompare` | `../../../constants.js` |
| `EqualCompare` | `../../../constants.js` |
| `GreaterEqualCompare` | `../../../constants.js` |
| `GreaterCompare` | `../../../constants.js` |
| `NotEqualCompare` | `../../../constants.js` |
| `IntType` | `../../../constants.js` |
| `RedIntegerFormat` | `../../../constants.js` |
| `RGIntegerFormat` | `../../../constants.js` |
| `RGBAIntegerFormat` | `../../../constants.js` |
| `CubeTexture` | `../../../textures/CubeTexture.js` |
| `DepthTexture` | `../../../textures/DepthTexture.js` |
| `Texture` | `../../../textures/Texture.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_compareToWebGPU` | `{ [x: number]: string; }` | let/var | `{ [ NeverCompare ]: 'never', [ LessCompare ]: 'less', [ EqualCompare ]: 'equa...` | ✗ |
| `_flipMap` | `number[]` | let/var | `[ 0, 1, 3, 2, 4, 5 ]` | ✗ |
| `backend` | `WebGPUBackend` | let/var | `this.backend` | ✗ |
| `device` | `any` | let/var | `backend.device` | ✗ |
| `samplerDescriptorGPU` | `{ addressModeU: string; addressModeV:...` | let/var | `{ addressModeU: this._convertAddressMode( texture.wrapS ), addressModeV: this...` | ✗ |
| `textureGPU` | `any` | let/var | `*not shown*` | ✗ |
| `backend` | `WebGPUBackend` | let/var | `this.backend` | ✗ |
| `format` | `any` | let/var | `texture.internalFormat \|\| options.format \|\| getFormat( texture, backend.d...` | ✗ |
| `usage` | `number` | let/var | `GPUTextureUsage.TEXTURE_BINDING \| GPUTextureUsage.COPY_DST \| GPUTextureUsag...` | ✗ |
| `textureDescriptorGPU` | `{ label: string; size: { width: any; ...` | let/var | `{ label: texture.name, size: { width: width, height: height, depthOrArrayLaye...` | ✗ |
| `backend` | `WebGPUBackend` | let/var | `this.backend` | ✗ |
| `backend` | `WebGPUBackend` | let/var | `this.backend` | ✗ |
| `depth` | `any` | let/var | `texture.image.depth \|\| 1` | ✗ |
| `backend` | `WebGPUBackend` | let/var | `this.backend` | ✗ |
| `backend` | `WebGPUBackend` | let/var | `this.backend` | ✗ |
| `depthTexture` | `DepthTexture` | let/var | `this.depthTexture` | ✗ |
| `depthTextureGPU` | `any` | let/var | `backend.get( depthTexture ).texture` | ✗ |
| `format` | `any` | let/var | `*not shown*` | ✗ |
| `type` | `any` | let/var | `*not shown*` | ✗ |
| `device` | `any` | let/var | `this.backend.device` | ✗ |
| `textureGPU` | `any` | let/var | `textureData.texture` | ✗ |
| `format` | `any` | let/var | `textureData.textureDescriptorGPU.format` | ✗ |
| `bytesPerRow` | `number` | let/var | `width * bytesPerTexel` | ✗ |
| `defaultTexture` | `Texture` | let/var | `this.defaultTexture[ format ]` | ✗ |
| `texture` | `Texture` | let/var | `new Texture()` | ✗ |
| `defaultCubeTexture` | `Texture` | let/var | `this.defaultTexture[ format ]` | ✗ |
| `texture` | `CubeTexture` | let/var | `new CubeTexture()` | ✗ |
| `image` | `any` | let/var | `images[ i ]` | ✗ |
| `flipIndex` | `number` | let/var | `flipY === true ? _flipMap[ i ] : i` | ✗ |
| `device` | `any` | let/var | `this.backend.device` | ✗ |
| `passUtils` | `WebGPUTexturePassUtils` | let/var | `this._passUtils` | ✗ |
| `device` | `any` | let/var | `this.backend.device` | ✗ |
| `data` | `any` | let/var | `image.data` | ✗ |
| `bytesPerRow` | `number` | let/var | `image.width * bytesPerTexel` | ✗ |
| `device` | `any` | let/var | `this.backend.device` | ✗ |
| `isArrayTexture` | `boolean` | let/var | `textureDescriptorGPU.size.depthOrArrayLayers > 1` | ✗ |
| `mipmap` | `any` | let/var | `mipmaps[ i ]` | ✗ |
| `width` | `any` | let/var | `mipmap.width` | ✗ |
| `height` | `any` | let/var | `mipmap.height` | ✗ |
| `depth` | `any` | let/var | `isArrayTexture ? textureDescriptorGPU.size.depthOrArrayLayers : 1` | ✗ |
| `bytesPerRow` | `number` | let/var | `Math.ceil( width / blockData.width ) * blockData.byteLength` | ✗ |
| `bytesPerImage` | `number` | let/var | `bytesPerRow * Math.ceil( height / blockData.height )` | ✗ |
| `addressMode` | `string` | let/var | `GPUAddressMode.ClampToEdge` | ✗ |
| `filterMode` | `string` | let/var | `GPUFilterMode.Linear` | ✗ |
| `dimension` | `any` | let/var | `*not shown*` | ✗ |
| `format` | `number` | let/var | `texture.format` | ✗ |
| `type` | `number` | let/var | `texture.type` | ✗ |
| `colorSpace` | `string` | let/var | `texture.colorSpace` | ✗ |
| `formatGPU` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `WebGPUTextureUtils.createSampler(texture: Texture): void`

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

- `backend.get`
- `this._convertAddressMode`
- `this._convertFilterMode`
- `device.createSampler`

**Internal Comments:**
```
// anisotropy can only be used when all filter modes are set to linear.
```

<details><summary>Code</summary>

```typescript
createSampler( texture ) {

		const backend = this.backend;
		const device = backend.device;

		const textureGPU = backend.get( texture );

		const samplerDescriptorGPU = {
			addressModeU: this._convertAddressMode( texture.wrapS ),
			addressModeV: this._convertAddressMode( texture.wrapT ),
			addressModeW: this._convertAddressMode( texture.wrapR ),
			magFilter: this._convertFilterMode( texture.magFilter ),
			minFilter: this._convertFilterMode( texture.minFilter ),
			mipmapFilter: this._convertFilterMode( texture.minFilter ),
			maxAnisotropy: 1
		};

		// anisotropy can only be used when all filter modes are set to linear.

		if ( samplerDescriptorGPU.magFilter === GPUFilterMode.Linear && samplerDescriptorGPU.minFilter === GPUFilterMode.Linear && samplerDescriptorGPU.mipmapFilter === GPUFilterMode.Linear ) {

			samplerDescriptorGPU.maxAnisotropy = texture.anisotropy;

		}

		if ( texture.isDepthTexture && texture.compareFunction !== null ) {

			samplerDescriptorGPU.compare = _compareToWebGPU[ texture.compareFunction ];

		}

		textureGPU.sampler = device.createSampler( samplerDescriptorGPU );

	}
```
</details>

### `WebGPUTextureUtils.createDefaultTexture(texture: Texture): void`

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

- `getFormat`
- `this._getDefaultCubeTextureGPU`
- `this._getDefaultTextureGPU`
- `this.backend.get`

<details><summary>Code</summary>

```typescript
createDefaultTexture( texture ) {

		let textureGPU;

		const format = getFormat( texture );

		if ( texture.isCubeTexture ) {

			textureGPU = this._getDefaultCubeTextureGPU( format );

		} else {

			textureGPU = this._getDefaultTextureGPU( format );

		}

		this.backend.get( texture ).texture = textureGPU;

	}
```
</details>

### `WebGPUTextureUtils.createTexture(texture: Texture, options: any): void`

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

- `backend.get`
- `this.backend.utils.getCurrentColorFormat`
- `this.backend.utils.getPreferredCanvasFormat`
- `this._getDimension`
- `getFormat`
- `backend.utils.getTextureSampleData`
- `console.warn`
- `this.createDefaultTexture`
- `backend.device.createTexture`
- `Object.assign`

**Internal Comments:**
```
// texture creation
```

<details><summary>Code</summary>

```typescript
createTexture( texture, options = {} ) {

		const backend = this.backend;
		const textureData = backend.get( texture );

		if ( textureData.initialized ) {

			throw new Error( 'WebGPUTextureUtils: Texture already initialized.' );

		}

		if ( options.needsMipmaps === undefined ) options.needsMipmaps = false;
		if ( options.levels === undefined ) options.levels = 1;
		if ( options.depth === undefined ) options.depth = 1;

		const { width, height, depth, levels } = options;

		if ( texture.isFramebufferTexture ) {

			if ( options.renderTarget ) {

				options.format = this.backend.utils.getCurrentColorFormat( options.renderTarget );

			} else {

				options.format = this.backend.utils.getPreferredCanvasFormat();

			}

		}

		const dimension = this._getDimension( texture );
		const format = texture.internalFormat || options.format || getFormat( texture, backend.device );

		textureData.format = format;

		const { samples, primarySamples, isMSAA } = backend.utils.getTextureSampleData( texture );

		let usage = GPUTextureUsage.TEXTURE_BINDING | GPUTextureUsage.COPY_DST | GPUTextureUsage.COPY_SRC;

		if ( texture.isStorageTexture === true ) {

			usage |= GPUTextureUsage.STORAGE_BINDING;

		}

		if ( texture.isCompressedTexture !== true && texture.isCompressedArrayTexture !== true ) {

			usage |= GPUTextureUsage.RENDER_ATTACHMENT;

		}

		const textureDescriptorGPU = {
			label: texture.name,
			size: {
				width: width,
				height: height,
				depthOrArrayLayers: depth,
			},
			mipLevelCount: levels,
			sampleCount: primarySamples,
			dimension: dimension,
			format: format,
			usage: usage
		};

		// texture creation

		if ( format === undefined ) {

			console.warn( 'WebGPURenderer: Texture format not supported.' );

			this.createDefaultTexture( texture );
			return;

		}

		if ( texture.isCubeTexture ) {

			textureDescriptorGPU.textureBindingViewDimension = GPUTextureViewDimension.Cube;

		}

		textureData.texture = backend.device.createTexture( textureDescriptorGPU );

		if ( isMSAA ) {

			const msaaTextureDescriptorGPU = Object.assign( {}, textureDescriptorGPU );

			msaaTextureDescriptorGPU.label = msaaTextureDescriptorGPU.label + '-msaa';
			msaaTextureDescriptorGPU.sampleCount = samples;
			msaaTextureDescriptorGPU.mipLevelCount = 1; // See https://www.w3.org/TR/webgpu/#texture-creation

			textureData.msaaTexture = backend.device.createTexture( msaaTextureDescriptorGPU );

		}

		textureData.initialized = true;

		textureData.textureDescriptorGPU = textureDescriptorGPU;

	}
```
</details>

### `WebGPUTextureUtils.destroyTexture(texture: Texture): void`

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

- `backend.get`
- `textureData.texture.destroy`
- `textureData.msaaTexture.destroy`
- `backend.delete`

<details><summary>Code</summary>

```typescript
destroyTexture( texture ) {

		const backend = this.backend;
		const textureData = backend.get( texture );

		if ( textureData.texture !== undefined ) textureData.texture.destroy();

		if ( textureData.msaaTexture !== undefined ) textureData.msaaTexture.destroy();

		backend.delete( texture );

	}
```
</details>

### `WebGPUTextureUtils.destroySampler(texture: Texture): void`

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

- `backend.get`

<details><summary>Code</summary>

```typescript
destroySampler( texture ) {

		const backend = this.backend;
		const textureData = backend.get( texture );

		delete textureData.sampler;

	}
```
</details>

### `WebGPUTextureUtils.generateMipmaps(texture: Texture): void`

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

- `this.backend.get`
- `this._generateMipmaps`

<details><summary>Code</summary>

```typescript
generateMipmaps( texture ) {

		const textureData = this.backend.get( texture );

		if ( texture.isCubeTexture ) {

			for ( let i = 0; i < 6; i ++ ) {

				this._generateMipmaps( textureData.texture, textureData.textureDescriptorGPU, i );

			}

		} else {

			const depth = texture.image.depth || 1;

			for ( let i = 0; i < depth; i ++ ) {

				this._generateMipmaps( textureData.texture, textureData.textureDescriptorGPU, i );

			}

		}

	}
```
</details>

### `WebGPUTextureUtils.getColorBuffer(): GPUTexture`

**JSDoc:**
```typescript
/**
	 * Returns the color buffer representing the color
	 * attachment of the default framebuffer.
	 *
	 * @return {GPUTexture} The color buffer.
	 */
```

**Returns:** `GPUTexture`

**Calls:**

- `this.colorBuffer.destroy`
- `backend.getDrawingBufferSize`
- `backend.device.createTexture`
- `backend.utils.getSampleCount`
- `backend.utils.getPreferredCanvasFormat`

<details><summary>Code</summary>

```typescript
getColorBuffer() {

		if ( this.colorBuffer ) this.colorBuffer.destroy();

		const backend = this.backend;
		const { width, height } = backend.getDrawingBufferSize();

		this.colorBuffer = backend.device.createTexture( {
			label: 'colorBuffer',
			size: {
				width: width,
				height: height,
				depthOrArrayLayers: 1
			},
			sampleCount: backend.utils.getSampleCount( backend.renderer.samples ),
			format: backend.utils.getPreferredCanvasFormat(),
			usage: GPUTextureUsage.RENDER_ATTACHMENT | GPUTextureUsage.COPY_SRC
		} );

		return this.colorBuffer;

	}
```
</details>

### `WebGPUTextureUtils.getDepthBuffer(depth: boolean, stencil: boolean): GPUTexture`

**JSDoc:**
```typescript
/**
	 * Returns the depth buffer representing the depth
	 * attachment of the default framebuffer.
	 *
	 * @param {boolean} [depth=true] - Whether depth is enabled or not.
	 * @param {boolean} [stencil=false] -  Whether stencil is enabled or not.
	 * @return {GPUTexture} The depth buffer.
	 */
```

**Parameters:**

- **`depth`** `boolean`
- **`stencil`** `boolean`

**Returns:** `GPUTexture`

**Calls:**

- `backend.getDrawingBufferSize`
- `backend.get`
- `this.destroyTexture`
- `this.createTexture`

<details><summary>Code</summary>

```typescript
getDepthBuffer( depth = true, stencil = false ) {

		const backend = this.backend;
		const { width, height } = backend.getDrawingBufferSize();

		const depthTexture = this.depthTexture;
		const depthTextureGPU = backend.get( depthTexture ).texture;

		let format, type;

		if ( stencil ) {

			format = DepthStencilFormat;
			type = UnsignedInt248Type;

		} else if ( depth ) {

			format = DepthFormat;
			type = UnsignedIntType;

		}

		if ( depthTextureGPU !== undefined ) {

			if ( depthTexture.image.width === width && depthTexture.image.height === height && depthTexture.format === format && depthTexture.type === type ) {

				return depthTextureGPU;

			}

			this.destroyTexture( depthTexture );

		}

		depthTexture.name = 'depthBuffer';
		depthTexture.format = format;
		depthTexture.type = type;
		depthTexture.image.width = width;
		depthTexture.image.height = height;

		this.createTexture( depthTexture, { width, height } );

		return backend.get( depthTexture ).texture;

	}
```
</details>

### `WebGPUTextureUtils.updateTexture(texture: Texture, options: any): void`

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

- `this.backend.get`
- `this._copyBufferToTexture`
- `this._copyCompressedBufferToTexture`
- `this._copyCubeMapToTexture`
- `this._copyImageToTexture`
- `texture.onUpdate`

**Internal Comments:**
```
// transfer texture data
// (x4)
```

<details><summary>Code</summary>

```typescript
updateTexture( texture, options ) {

		const textureData = this.backend.get( texture );

		const { textureDescriptorGPU } = textureData;

		if ( texture.isRenderTargetTexture || ( textureDescriptorGPU === undefined /* unsupported texture format */ ) )
			return;

		// transfer texture data

		if ( texture.isDataTexture ) {

			this._copyBufferToTexture( options.image, textureData.texture, textureDescriptorGPU, 0, texture.flipY );

		} else if ( texture.isArrayTexture || texture.isDataArrayTexture || texture.isData3DTexture ) {

			for ( let i = 0; i < options.image.depth; i ++ ) {

				this._copyBufferToTexture( options.image, textureData.texture, textureDescriptorGPU, i, texture.flipY, i );

			}

		} else if ( texture.isCompressedTexture || texture.isCompressedArrayTexture ) {

			this._copyCompressedBufferToTexture( texture.mipmaps, textureData.texture, textureDescriptorGPU );

		} else if ( texture.isCubeTexture ) {

			this._copyCubeMapToTexture( options.images, textureData.texture, textureDescriptorGPU, texture.flipY, texture.premultiplyAlpha );

		} else {

			this._copyImageToTexture( options.image, textureData.texture, textureDescriptorGPU, 0, texture.flipY, texture.premultiplyAlpha );

		}

		//

		textureData.version = texture.version;

		if ( texture.onUpdate ) texture.onUpdate( texture );

	}
```
</details>

### `WebGPUTextureUtils.copyTextureToBuffer(texture: Texture, x: number, y: number, width: number, height: number, faceIndex: number): Promise<TypedArray>`

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

- `this.backend.get`
- `this._getBytesPerTexel`
- `Math.ceil`
- `device.createBuffer`
- `device.createCommandEncoder`
- `encoder.copyTextureToBuffer`
- `this._getTypedArrayType`
- `device.queue.submit`
- `encoder.finish`
- `readBuffer.mapAsync`
- `readBuffer.getMappedRange`

<details><summary>Code</summary>

```typescript
async copyTextureToBuffer( texture, x, y, width, height, faceIndex ) {

		const device = this.backend.device;

		const textureData = this.backend.get( texture );
		const textureGPU = textureData.texture;
		const format = textureData.textureDescriptorGPU.format;
		const bytesPerTexel = this._getBytesPerTexel( format );

		let bytesPerRow = width * bytesPerTexel;
		bytesPerRow = Math.ceil( bytesPerRow / 256 ) * 256; // Align to 256 bytes

		const readBuffer = device.createBuffer(
			{
				size: width * height * bytesPerTexel,
				usage: GPUBufferUsage.COPY_DST | GPUBufferUsage.MAP_READ
			}
		);

		const encoder = device.createCommandEncoder();

		encoder.copyTextureToBuffer(
			{
				texture: textureGPU,
				origin: { x, y, z: faceIndex },
			},
			{
				buffer: readBuffer,
				bytesPerRow: bytesPerRow
			},
			{
				width: width,
				height: height
			}

		);

		const typedArrayType = this._getTypedArrayType( format );

		device.queue.submit( [ encoder.finish() ] );

		await readBuffer.mapAsync( GPUMapMode.READ );

		const buffer = readBuffer.getMappedRange();

		return new typedArrayType( buffer );

	}
```
</details>

### `WebGPUTextureUtils._getDefaultTextureGPU(format: string): GPUTexture`

**JSDoc:**
```typescript
/**
	 * Returns the default GPU texture for the given format.
	 *
	 * @private
	 * @param {string} format - The GPU format.
	 * @return {GPUTexture} The GPU texture.
	 */
```

**Parameters:**

- **`format`** `string`

**Returns:** `GPUTexture`

**Calls:**

- `this.createTexture`
- `this.backend.get`

<details><summary>Code</summary>

```typescript
_getDefaultTextureGPU( format ) {

		let defaultTexture = this.defaultTexture[ format ];

		if ( defaultTexture === undefined ) {

			const texture = new Texture();
			texture.minFilter = NearestFilter;
			texture.magFilter = NearestFilter;

			this.createTexture( texture, { width: 1, height: 1, format } );

			this.defaultTexture[ format ] = defaultTexture = texture;

		}

		return this.backend.get( defaultTexture ).texture;

	}
```
</details>

### `WebGPUTextureUtils._getDefaultCubeTextureGPU(format: string): GPUTexture`

**JSDoc:**
```typescript
/**
	 * Returns the default GPU cube texture for the given format.
	 *
	 * @private
	 * @param {string} format - The GPU format.
	 * @return {GPUTexture} The GPU texture.
	 */
```

**Parameters:**

- **`format`** `string`

**Returns:** `GPUTexture`

**Calls:**

- `this.createTexture`
- `this.backend.get`

<details><summary>Code</summary>

```typescript
_getDefaultCubeTextureGPU( format ) {

		let defaultCubeTexture = this.defaultTexture[ format ];

		if ( defaultCubeTexture === undefined ) {

			const texture = new CubeTexture();
			texture.minFilter = NearestFilter;
			texture.magFilter = NearestFilter;

			this.createTexture( texture, { width: 1, height: 1, depth: 6 } );

			this.defaultCubeTexture[ format ] = defaultCubeTexture = texture;

		}

		return this.backend.get( defaultCubeTexture ).texture;

	}
```
</details>

### `WebGPUTextureUtils._copyCubeMapToTexture(images: any[], textureGPU: GPUTexture, textureDescriptorGPU: any, flipY: boolean, premultiplyAlpha: boolean): void`

**JSDoc:**
```typescript
/**
	 * Uploads cube texture image data to the GPU memory.
	 *
	 * @private
	 * @param {Array} images - The cube image data.
	 * @param {GPUTexture} textureGPU - The GPU texture.
	 * @param {Object} textureDescriptorGPU - The GPU texture descriptor.
	 * @param {boolean} flipY - Whether to flip texture data along their vertical axis or not.
	 * @param {boolean} premultiplyAlpha - Whether the texture should have its RGB channels premultiplied by the alpha channel or not.
	 */
```

**Parameters:**

- **`images`** `any[]`
- **`textureGPU`** `GPUTexture`
- **`textureDescriptorGPU`** `any`
- **`flipY`** `boolean`
- **`premultiplyAlpha`** `boolean`

**Returns:** `void`

**Calls:**

- `this._copyBufferToTexture`
- `this._copyImageToTexture`

<details><summary>Code</summary>

```typescript
_copyCubeMapToTexture( images, textureGPU, textureDescriptorGPU, flipY, premultiplyAlpha ) {

		for ( let i = 0; i < 6; i ++ ) {

			const image = images[ i ];

			const flipIndex = flipY === true ? _flipMap[ i ] : i;

			if ( image.isDataTexture ) {

				this._copyBufferToTexture( image.image, textureGPU, textureDescriptorGPU, flipIndex, flipY );

			} else {

				this._copyImageToTexture( image, textureGPU, textureDescriptorGPU, flipIndex, flipY, premultiplyAlpha );

			}

		}

	}
```
</details>

### `WebGPUTextureUtils._copyImageToTexture(image: HTMLCanvasElement | HTMLImageElement | ImageBitmap, textureGPU: GPUTexture, textureDescriptorGPU: any, originDepth: number, flipY: boolean, premultiplyAlpha: boolean): void`

**JSDoc:**
```typescript
/**
	 * Uploads texture image data to the GPU memory.
	 *
	 * @private
	 * @param {HTMLImageElement|ImageBitmap|HTMLCanvasElement} image - The image data.
	 * @param {GPUTexture} textureGPU - The GPU texture.
	 * @param {Object} textureDescriptorGPU - The GPU texture descriptor.
	 * @param {number} originDepth - The origin depth.
	 * @param {boolean} flipY - Whether to flip texture data along their vertical axis or not.
	 * @param {boolean} premultiplyAlpha - Whether the texture should have its RGB channels premultiplied by the alpha channel or not.
	 */
```

**Parameters:**

- **`image`** `HTMLCanvasElement | HTMLImageElement | ImageBitmap`
- **`textureGPU`** `GPUTexture`
- **`textureDescriptorGPU`** `any`
- **`originDepth`** `number`
- **`flipY`** `boolean`
- **`premultiplyAlpha`** `boolean`

**Returns:** `void`

**Calls:**

- `device.queue.copyExternalImageToTexture`

<details><summary>Code</summary>

```typescript
_copyImageToTexture( image, textureGPU, textureDescriptorGPU, originDepth, flipY, premultiplyAlpha ) {

		const device = this.backend.device;

		device.queue.copyExternalImageToTexture(
			{
				source: image,
				flipY: flipY
			}, {
				texture: textureGPU,
				mipLevel: 0,
				origin: { x: 0, y: 0, z: originDepth },
				premultipliedAlpha: premultiplyAlpha
			}, {
				width: textureDescriptorGPU.size.width,
				height: textureDescriptorGPU.size.height,
				depthOrArrayLayers: 1
			}
		);

	}
```
</details>

### `WebGPUTextureUtils._getPassUtils(): WebGPUTexturePassUtils`

**JSDoc:**
```typescript
/**
	 * Returns the pass utils singleton.
	 *
	 * @private
	 * @return {WebGPUTexturePassUtils} The utils instance.
	 */
```

**Returns:** `WebGPUTexturePassUtils`

<details><summary>Code</summary>

```typescript
_getPassUtils() {

		let passUtils = this._passUtils;

		if ( passUtils === null ) {

			this._passUtils = passUtils = new WebGPUTexturePassUtils( this.backend.device );

		}

		return passUtils;

	}
```
</details>

### `WebGPUTextureUtils._generateMipmaps(textureGPU: GPUTexture, textureDescriptorGPU: any, baseArrayLayer: number): void`

**JSDoc:**
```typescript
/**
	 * Generates mipmaps for the given GPU texture.
	 *
	 * @private
	 * @param {GPUTexture} textureGPU - The GPU texture object.
	 * @param {Object} textureDescriptorGPU - The texture descriptor.
	 * @param {number} [baseArrayLayer=0] - The index of the first array layer accessible to the texture view.
	 */
```

**Parameters:**

- **`textureGPU`** `GPUTexture`
- **`textureDescriptorGPU`** `any`
- **`baseArrayLayer`** `number`

**Returns:** `void`

**Calls:**

- `this._getPassUtils().generateMipmaps`

<details><summary>Code</summary>

```typescript
_generateMipmaps( textureGPU, textureDescriptorGPU, baseArrayLayer = 0 ) {

		this._getPassUtils().generateMipmaps( textureGPU, textureDescriptorGPU, baseArrayLayer );

	}
```
</details>

### `WebGPUTextureUtils._flipY(textureGPU: GPUTexture, textureDescriptorGPU: any, originDepth: number): void`

**JSDoc:**
```typescript
/**
	 * Flip the contents of the given GPU texture along its vertical axis.
	 *
	 * @private
	 * @param {GPUTexture} textureGPU - The GPU texture object.
	 * @param {Object} textureDescriptorGPU - The texture descriptor.
	 * @param {number} [originDepth=0] - The origin depth.
	 */
```

**Parameters:**

- **`textureGPU`** `GPUTexture`
- **`textureDescriptorGPU`** `any`
- **`originDepth`** `number`

**Returns:** `void`

**Calls:**

- `this._getPassUtils().flipY`

<details><summary>Code</summary>

```typescript
_flipY( textureGPU, textureDescriptorGPU, originDepth = 0 ) {

		this._getPassUtils().flipY( textureGPU, textureDescriptorGPU, originDepth );

	}
```
</details>

### `WebGPUTextureUtils._copyBufferToTexture(image: any, textureGPU: GPUTexture, textureDescriptorGPU: any, originDepth: number, flipY: boolean, depth: number): void`

**JSDoc:**
```typescript
/**
	 * Uploads texture buffer data to the GPU memory.
	 *
	 * @private
	 * @param {Object} image - An object defining the image buffer data.
	 * @param {GPUTexture} textureGPU - The GPU texture.
	 * @param {Object} textureDescriptorGPU - The GPU texture descriptor.
	 * @param {number} originDepth - The origin depth.
	 * @param {boolean} flipY - Whether to flip texture data along their vertical axis or not.
	 * @param {number} [depth=0] - TODO.
	 */
```

**Parameters:**

- **`image`** `any`
- **`textureGPU`** `GPUTexture`
- **`textureDescriptorGPU`** `any`
- **`originDepth`** `number`
- **`flipY`** `boolean`
- **`depth`** `number`

**Returns:** `void`

**Calls:**

- `this._getBytesPerTexel`
- `device.queue.writeTexture`
- `this._flipY`

**Internal Comments:**
```
// @TODO: Consider to use GPUCommandEncoder.copyBufferToTexture() (x2)
// @TODO: Consider to support valid buffer layouts with other formats like RGB (x2)
```

<details><summary>Code</summary>

```typescript
_copyBufferToTexture( image, textureGPU, textureDescriptorGPU, originDepth, flipY, depth = 0 ) {

		// @TODO: Consider to use GPUCommandEncoder.copyBufferToTexture()
		// @TODO: Consider to support valid buffer layouts with other formats like RGB

		const device = this.backend.device;

		const data = image.data;

		const bytesPerTexel = this._getBytesPerTexel( textureDescriptorGPU.format );
		const bytesPerRow = image.width * bytesPerTexel;

		device.queue.writeTexture(
			{
				texture: textureGPU,
				mipLevel: 0,
				origin: { x: 0, y: 0, z: originDepth }
			},
			data,
			{
				offset: image.width * image.height * bytesPerTexel * depth,
				bytesPerRow
			},
			{
				width: image.width,
				height: image.height,
				depthOrArrayLayers: 1
			} );

		if ( flipY === true ) {

			this._flipY( textureGPU, textureDescriptorGPU, originDepth );

		}

	}
```
</details>

### `WebGPUTextureUtils._copyCompressedBufferToTexture(mipmaps: any[], textureGPU: GPUTexture, textureDescriptorGPU: any): void`

**JSDoc:**
```typescript
/**
	 * Uploads compressed texture data to the GPU memory.
	 *
	 * @private
	 * @param {Array<Object>} mipmaps - An array with mipmap data.
	 * @param {GPUTexture} textureGPU - The GPU texture.
	 * @param {Object} textureDescriptorGPU - The GPU texture descriptor.
	 */
```

**Parameters:**

- **`mipmaps`** `any[]`
- **`textureGPU`** `GPUTexture`
- **`textureDescriptorGPU`** `any`

**Returns:** `void`

**Calls:**

- `this._getBlockData`
- `Math.ceil`
- `device.queue.writeTexture`

**Internal Comments:**
```
// @TODO: Consider to use GPUCommandEncoder.copyBufferToTexture() (x2)
```

<details><summary>Code</summary>

```typescript
_copyCompressedBufferToTexture( mipmaps, textureGPU, textureDescriptorGPU ) {

		// @TODO: Consider to use GPUCommandEncoder.copyBufferToTexture()

		const device = this.backend.device;

		const blockData = this._getBlockData( textureDescriptorGPU.format );
		const isArrayTexture = textureDescriptorGPU.size.depthOrArrayLayers > 1;

		for ( let i = 0; i < mipmaps.length; i ++ ) {

			const mipmap = mipmaps[ i ];

			const width = mipmap.width;
			const height = mipmap.height;
			const depth = isArrayTexture ? textureDescriptorGPU.size.depthOrArrayLayers : 1;

			const bytesPerRow = Math.ceil( width / blockData.width ) * blockData.byteLength;
			const bytesPerImage = bytesPerRow * Math.ceil( height / blockData.height );

			for ( let j = 0; j < depth; j ++ ) {

				device.queue.writeTexture(
					{
						texture: textureGPU,
						mipLevel: i,
						origin: { x: 0, y: 0, z: j }
					},
					mipmap.data,
					{
						offset: j * bytesPerImage,
						bytesPerRow,
						rowsPerImage: Math.ceil( height / blockData.height )
					},
					{
						width: Math.ceil( width / blockData.width ) * blockData.width,
						height: Math.ceil( height / blockData.height ) * blockData.height,
						depthOrArrayLayers: 1
					}
				);

			}

		}

	}
```
</details>

### `WebGPUTextureUtils._getBlockData(format: string): any`

**JSDoc:**
```typescript
/**
	 * This method is only relevant for compressed texture formats. It returns a block
	 * data descriptor for the given GPU compressed texture format.
	 *
	 * @private
	 * @param {string} format - The GPU compressed texture format.
	 * @return {Object} The block data descriptor.
	 */
```

**Parameters:**

- **`format`** `string`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
_getBlockData( format ) {

		if ( format === GPUTextureFormat.BC1RGBAUnorm || format === GPUTextureFormat.BC1RGBAUnormSRGB ) return { byteLength: 8, width: 4, height: 4 }; // DXT1
		if ( format === GPUTextureFormat.BC2RGBAUnorm || format === GPUTextureFormat.BC2RGBAUnormSRGB ) return { byteLength: 16, width: 4, height: 4 }; // DXT3
		if ( format === GPUTextureFormat.BC3RGBAUnorm || format === GPUTextureFormat.BC3RGBAUnormSRGB ) return { byteLength: 16, width: 4, height: 4 }; // DXT5
		if ( format === GPUTextureFormat.BC4RUnorm || format === GPUTextureFormat.BC4RSnorm ) return { byteLength: 8, width: 4, height: 4 }; // RGTC1
		if ( format === GPUTextureFormat.BC5RGUnorm || format === GPUTextureFormat.BC5RGSnorm ) return { byteLength: 16, width: 4, height: 4 }; // RGTC2
		if ( format === GPUTextureFormat.BC6HRGBUFloat || format === GPUTextureFormat.BC6HRGBFloat ) return { byteLength: 16, width: 4, height: 4 }; // BPTC (float)
		if ( format === GPUTextureFormat.BC7RGBAUnorm || format === GPUTextureFormat.BC7RGBAUnormSRGB ) return { byteLength: 16, width: 4, height: 4 }; // BPTC (unorm)

		if ( format === GPUTextureFormat.ETC2RGB8Unorm || format === GPUTextureFormat.ETC2RGB8UnormSRGB ) return { byteLength: 8, width: 4, height: 4 };
		if ( format === GPUTextureFormat.ETC2RGB8A1Unorm || format === GPUTextureFormat.ETC2RGB8A1UnormSRGB ) return { byteLength: 8, width: 4, height: 4 };
		if ( format === GPUTextureFormat.ETC2RGBA8Unorm || format === GPUTextureFormat.ETC2RGBA8UnormSRGB ) return { byteLength: 16, width: 4, height: 4 };
		if ( format === GPUTextureFormat.EACR11Unorm ) return { byteLength: 8, width: 4, height: 4 };
		if ( format === GPUTextureFormat.EACR11Snorm ) return { byteLength: 8, width: 4, height: 4 };
		if ( format === GPUTextureFormat.EACRG11Unorm ) return { byteLength: 16, width: 4, height: 4 };
		if ( format === GPUTextureFormat.EACRG11Snorm ) return { byteLength: 16, width: 4, height: 4 };

		if ( format === GPUTextureFormat.ASTC4x4Unorm || format === GPUTextureFormat.ASTC4x4UnormSRGB ) return { byteLength: 16, width: 4, height: 4 };
		if ( format === GPUTextureFormat.ASTC5x4Unorm || format === GPUTextureFormat.ASTC5x4UnormSRGB ) return { byteLength: 16, width: 5, height: 4 };
		if ( format === GPUTextureFormat.ASTC5x5Unorm || format === GPUTextureFormat.ASTC5x5UnormSRGB ) return { byteLength: 16, width: 5, height: 5 };
		if ( format === GPUTextureFormat.ASTC6x5Unorm || format === GPUTextureFormat.ASTC6x5UnormSRGB ) return { byteLength: 16, width: 6, height: 5 };
		if ( format === GPUTextureFormat.ASTC6x6Unorm || format === GPUTextureFormat.ASTC6x6UnormSRGB ) return { byteLength: 16, width: 6, height: 6 };
		if ( format === GPUTextureFormat.ASTC8x5Unorm || format === GPUTextureFormat.ASTC8x5UnormSRGB ) return { byteLength: 16, width: 8, height: 5 };
		if ( format === GPUTextureFormat.ASTC8x6Unorm || format === GPUTextureFormat.ASTC8x6UnormSRGB ) return { byteLength: 16, width: 8, height: 6 };
		if ( format === GPUTextureFormat.ASTC8x8Unorm || format === GPUTextureFormat.ASTC8x8UnormSRGB ) return { byteLength: 16, width: 8, height: 8 };
		if ( format === GPUTextureFormat.ASTC10x5Unorm || format === GPUTextureFormat.ASTC10x5UnormSRGB ) return { byteLength: 16, width: 10, height: 5 };
		if ( format === GPUTextureFormat.ASTC10x6Unorm || format === GPUTextureFormat.ASTC10x6UnormSRGB ) return { byteLength: 16, width: 10, height: 6 };
		if ( format === GPUTextureFormat.ASTC10x8Unorm || format === GPUTextureFormat.ASTC10x8UnormSRGB ) return { byteLength: 16, width: 10, height: 8 };
		if ( format === GPUTextureFormat.ASTC10x10Unorm || format === GPUTextureFormat.ASTC10x10UnormSRGB ) return { byteLength: 16, width: 10, height: 10 };
		if ( format === GPUTextureFormat.ASTC12x10Unorm || format === GPUTextureFormat.ASTC12x10UnormSRGB ) return { byteLength: 16, width: 12, height: 10 };
		if ( format === GPUTextureFormat.ASTC12x12Unorm || format === GPUTextureFormat.ASTC12x12UnormSRGB ) return { byteLength: 16, width: 12, height: 12 };

	}
```
</details>

### `WebGPUTextureUtils._convertAddressMode(value: number): string`

**JSDoc:**
```typescript
/**
	 * Converts the three.js uv wrapping constants to GPU address mode constants.
	 *
	 * @private
	 * @param {number} value - The three.js constant defining a uv wrapping mode.
	 * @return {string} The GPU address mode.
	 */
```

**Parameters:**

- **`value`** `number`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
_convertAddressMode( value ) {

		let addressMode = GPUAddressMode.ClampToEdge;

		if ( value === RepeatWrapping ) {

			addressMode = GPUAddressMode.Repeat;

		} else if ( value === MirroredRepeatWrapping ) {

			addressMode = GPUAddressMode.MirrorRepeat;

		}

		return addressMode;

	}
```
</details>

### `WebGPUTextureUtils._convertFilterMode(value: number): string`

**JSDoc:**
```typescript
/**
	 * Converts the three.js filter constants to GPU filter constants.
	 *
	 * @private
	 * @param {number} value - The three.js constant defining a filter mode.
	 * @return {string} The GPU filter mode.
	 */
```

**Parameters:**

- **`value`** `number`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
_convertFilterMode( value ) {

		let filterMode = GPUFilterMode.Linear;

		if ( value === NearestFilter || value === NearestMipmapNearestFilter || value === NearestMipmapLinearFilter ) {

			filterMode = GPUFilterMode.Nearest;

		}

		return filterMode;

	}
```
</details>

### `WebGPUTextureUtils._getBytesPerTexel(format: string): number`

**JSDoc:**
```typescript
/**
	 * Returns the bytes-per-texel value for the given GPU texture format.
	 *
	 * @private
	 * @param {string} format - The GPU texture format.
	 * @return {number} The bytes-per-texel.
	 */
```

**Parameters:**

- **`format`** `string`

**Returns:** `number`

**Internal Comments:**
```
// 8-bit formats
// 16-bit formats
// 32-bit formats
// Packed 32-bit formats (x2)
// 64-bit formats
// 128-bit formats
```

<details><summary>Code</summary>

```typescript
_getBytesPerTexel( format ) {

		// 8-bit formats
		if ( format === GPUTextureFormat.R8Unorm ||
			format === GPUTextureFormat.R8Snorm ||
			format === GPUTextureFormat.R8Uint ||
			format === GPUTextureFormat.R8Sint ) return 1;

		// 16-bit formats
		if ( format === GPUTextureFormat.R16Uint ||
			format === GPUTextureFormat.R16Sint ||
			format === GPUTextureFormat.R16Float ||
			format === GPUTextureFormat.RG8Unorm ||
			format === GPUTextureFormat.RG8Snorm ||
			format === GPUTextureFormat.RG8Uint ||
			format === GPUTextureFormat.RG8Sint ) return 2;

		// 32-bit formats
		if ( format === GPUTextureFormat.R32Uint ||
			format === GPUTextureFormat.R32Sint ||
			format === GPUTextureFormat.R32Float ||
			format === GPUTextureFormat.RG16Uint ||
			format === GPUTextureFormat.RG16Sint ||
			format === GPUTextureFormat.RG16Float ||
			format === GPUTextureFormat.RGBA8Unorm ||
			format === GPUTextureFormat.RGBA8UnormSRGB ||
			format === GPUTextureFormat.RGBA8Snorm ||
			format === GPUTextureFormat.RGBA8Uint ||
			format === GPUTextureFormat.RGBA8Sint ||
			format === GPUTextureFormat.BGRA8Unorm ||
			format === GPUTextureFormat.BGRA8UnormSRGB ||
			// Packed 32-bit formats
			format === GPUTextureFormat.RGB9E5UFloat ||
			format === GPUTextureFormat.RGB10A2Unorm ||
			format === GPUTextureFormat.RG11B10UFloat ||
			format === GPUTextureFormat.Depth32Float ||
			format === GPUTextureFormat.Depth24Plus ||
			format === GPUTextureFormat.Depth24PlusStencil8 ||
			format === GPUTextureFormat.Depth32FloatStencil8 ) return 4;

		// 64-bit formats
		if ( format === GPUTextureFormat.RG32Uint ||
			format === GPUTextureFormat.RG32Sint ||
			format === GPUTextureFormat.RG32Float ||
			format === GPUTextureFormat.RGBA16Uint ||
			format === GPUTextureFormat.RGBA16Sint ||
			format === GPUTextureFormat.RGBA16Float ) return 8;

		// 128-bit formats
		if ( format === GPUTextureFormat.RGBA32Uint ||
			format === GPUTextureFormat.RGBA32Sint ||
			format === GPUTextureFormat.RGBA32Float ) return 16;


	}
```
</details>

### `WebGPUTextureUtils._getTypedArrayType(format: string): TypedArray.constructor`

**JSDoc:**
```typescript
/**
	 * Returns the corresponding typed array type for the given GPU texture format.
	 *
	 * @private
	 * @param {string} format - The GPU texture format.
	 * @return {TypedArray.constructor} The typed array type.
	 */
```

**Parameters:**

- **`format`** `string`

**Returns:** `TypedArray.constructor`

<details><summary>Code</summary>

```typescript
_getTypedArrayType( format ) {

		if ( format === GPUTextureFormat.R8Uint ) return Uint8Array;
		if ( format === GPUTextureFormat.R8Sint ) return Int8Array;
		if ( format === GPUTextureFormat.R8Unorm ) return Uint8Array;
		if ( format === GPUTextureFormat.R8Snorm ) return Int8Array;
		if ( format === GPUTextureFormat.RG8Uint ) return Uint8Array;
		if ( format === GPUTextureFormat.RG8Sint ) return Int8Array;
		if ( format === GPUTextureFormat.RG8Unorm ) return Uint8Array;
		if ( format === GPUTextureFormat.RG8Snorm ) return Int8Array;
		if ( format === GPUTextureFormat.RGBA8Uint ) return Uint8Array;
		if ( format === GPUTextureFormat.RGBA8Sint ) return Int8Array;
		if ( format === GPUTextureFormat.RGBA8Unorm ) return Uint8Array;
		if ( format === GPUTextureFormat.RGBA8Snorm ) return Int8Array;


		if ( format === GPUTextureFormat.R16Uint ) return Uint16Array;
		if ( format === GPUTextureFormat.R16Sint ) return Int16Array;
		if ( format === GPUTextureFormat.RG16Uint ) return Uint16Array;
		if ( format === GPUTextureFormat.RG16Sint ) return Int16Array;
		if ( format === GPUTextureFormat.RGBA16Uint ) return Uint16Array;
		if ( format === GPUTextureFormat.RGBA16Sint ) return Int16Array;
		if ( format === GPUTextureFormat.R16Float ) return Uint16Array;
		if ( format === GPUTextureFormat.RG16Float ) return Uint16Array;
		if ( format === GPUTextureFormat.RGBA16Float ) return Uint16Array;


		if ( format === GPUTextureFormat.R32Uint ) return Uint32Array;
		if ( format === GPUTextureFormat.R32Sint ) return Int32Array;
		if ( format === GPUTextureFormat.R32Float ) return Float32Array;
		if ( format === GPUTextureFormat.RG32Uint ) return Uint32Array;
		if ( format === GPUTextureFormat.RG32Sint ) return Int32Array;
		if ( format === GPUTextureFormat.RG32Float ) return Float32Array;
		if ( format === GPUTextureFormat.RGBA32Uint ) return Uint32Array;
		if ( format === GPUTextureFormat.RGBA32Sint ) return Int32Array;
		if ( format === GPUTextureFormat.RGBA32Float ) return Float32Array;

		if ( format === GPUTextureFormat.BGRA8Unorm ) return Uint8Array;
		if ( format === GPUTextureFormat.BGRA8UnormSRGB ) return Uint8Array;
		if ( format === GPUTextureFormat.RGB10A2Unorm ) return Uint32Array;
		if ( format === GPUTextureFormat.RGB9E5UFloat ) return Uint32Array;
		if ( format === GPUTextureFormat.RG11B10UFloat ) return Uint32Array;

		if ( format === GPUTextureFormat.Depth32Float ) return Float32Array;
		if ( format === GPUTextureFormat.Depth24Plus ) return Uint32Array;
		if ( format === GPUTextureFormat.Depth24PlusStencil8 ) return Uint32Array;
		if ( format === GPUTextureFormat.Depth32FloatStencil8 ) return Float32Array;

	}
```
</details>

### `WebGPUTextureUtils._getDimension(texture: Texture): string`

**JSDoc:**
```typescript
/**
	 * Returns the GPU dimensions for the given texture.
	 *
	 * @private
	 * @param {Texture} texture - The texture.
	 * @return {string} The GPU dimension.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
_getDimension( texture ) {

		let dimension;

		if ( texture.is3DTexture || texture.isData3DTexture ) {

			dimension = GPUTextureDimension.ThreeD;

		} else {

			dimension = GPUTextureDimension.TwoD;

		}

		return dimension;

	}
```
</details>

### `getFormat(texture: Texture, device: GPUDevice): string`

**JSDoc:**
```typescript
/**
 * Returns the GPU format for the given texture.
 *
 * @param {Texture} texture - The texture.
 * @param {?GPUDevice} [device=null] - The GPU device which is used for feature detection.
 * It is not necessary to apply the device for most formats.
 * @return {string} The GPU format.
 */
```

**Parameters:**

- **`texture`** `Texture`
- **`device`** `GPUDevice`

**Returns:** `string`

**Calls:**

- `ColorManagement.getTransfer`
- `console.error`
- `device.features.has`

<details><summary>Code</summary>

```typescript
export function getFormat( texture, device = null ) {

	const format = texture.format;
	const type = texture.type;
	const colorSpace = texture.colorSpace;
	const transfer = ColorManagement.getTransfer( colorSpace );

	let formatGPU;

	if ( texture.isCompressedTexture === true || texture.isCompressedArrayTexture === true ) {

		switch ( format ) {

			case RGBA_S3TC_DXT1_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.BC1RGBAUnormSRGB : GPUTextureFormat.BC1RGBAUnorm;
				break;

			case RGBA_S3TC_DXT3_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.BC2RGBAUnormSRGB : GPUTextureFormat.BC2RGBAUnorm;
				break;

			case RGBA_S3TC_DXT5_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.BC3RGBAUnormSRGB : GPUTextureFormat.BC3RGBAUnorm;
				break;

			case RGB_ETC2_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.ETC2RGB8UnormSRGB : GPUTextureFormat.ETC2RGB8Unorm;
				break;

			case RGBA_ETC2_EAC_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.ETC2RGBA8UnormSRGB : GPUTextureFormat.ETC2RGBA8Unorm;
				break;

			case RGBA_ASTC_4x4_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.ASTC4x4UnormSRGB : GPUTextureFormat.ASTC4x4Unorm;
				break;

			case RGBA_ASTC_5x4_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.ASTC5x4UnormSRGB : GPUTextureFormat.ASTC5x4Unorm;
				break;

			case RGBA_ASTC_5x5_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.ASTC5x5UnormSRGB : GPUTextureFormat.ASTC5x5Unorm;
				break;

			case RGBA_ASTC_6x5_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.ASTC6x5UnormSRGB : GPUTextureFormat.ASTC6x5Unorm;
				break;

			case RGBA_ASTC_6x6_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.ASTC6x6UnormSRGB : GPUTextureFormat.ASTC6x6Unorm;
				break;

			case RGBA_ASTC_8x5_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.ASTC8x5UnormSRGB : GPUTextureFormat.ASTC8x5Unorm;
				break;

			case RGBA_ASTC_8x6_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.ASTC8x6UnormSRGB : GPUTextureFormat.ASTC8x6Unorm;
				break;

			case RGBA_ASTC_8x8_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.ASTC8x8UnormSRGB : GPUTextureFormat.ASTC8x8Unorm;
				break;

			case RGBA_ASTC_10x5_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.ASTC10x5UnormSRGB : GPUTextureFormat.ASTC10x5Unorm;
				break;

			case RGBA_ASTC_10x6_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.ASTC10x6UnormSRGB : GPUTextureFormat.ASTC10x6Unorm;
				break;

			case RGBA_ASTC_10x8_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.ASTC10x8UnormSRGB : GPUTextureFormat.ASTC10x8Unorm;
				break;

			case RGBA_ASTC_10x10_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.ASTC10x10UnormSRGB : GPUTextureFormat.ASTC10x10Unorm;
				break;

			case RGBA_ASTC_12x10_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.ASTC12x10UnormSRGB : GPUTextureFormat.ASTC12x10Unorm;
				break;

			case RGBA_ASTC_12x12_Format:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.ASTC12x12UnormSRGB : GPUTextureFormat.ASTC12x12Unorm;
				break;

			case RGBAFormat:
				formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.RGBA8UnormSRGB : GPUTextureFormat.RGBA8Unorm;
				break;

			default:
				console.error( 'WebGPURenderer: Unsupported texture format.', format );

		}

	} else {

		switch ( format ) {

			case RGBAFormat:

				switch ( type ) {

					case ByteType:
						formatGPU = GPUTextureFormat.RGBA8Snorm;
						break;

					case ShortType:
						formatGPU = GPUTextureFormat.RGBA16Sint;
						break;

					case UnsignedShortType:
						formatGPU = GPUTextureFormat.RGBA16Uint;
						break;
					case UnsignedIntType:
						formatGPU = GPUTextureFormat.RGBA32Uint;
						break;

					case IntType:
						formatGPU = GPUTextureFormat.RGBA32Sint;
						break;

					case UnsignedByteType:
						formatGPU = ( transfer === SRGBTransfer ) ? GPUTextureFormat.RGBA8UnormSRGB : GPUTextureFormat.RGBA8Unorm;
						break;

					case HalfFloatType:
						formatGPU = GPUTextureFormat.RGBA16Float;
						break;

					case FloatType:
						formatGPU = GPUTextureFormat.RGBA32Float;
						break;

					default:
						console.error( 'WebGPURenderer: Unsupported texture type with RGBAFormat.', type );

				}

				break;

			case RGBFormat:

				switch ( type ) {

					case UnsignedInt5999Type:
						formatGPU = GPUTextureFormat.RGB9E5UFloat;
						break;

					default:
						console.error( 'WebGPURenderer: Unsupported texture type with RGBFormat.', type );

				}

				break;

			case RedFormat:

				switch ( type ) {

					case ByteType:
						formatGPU = GPUTextureFormat.R8Snorm;
						break;

					case ShortType:
						formatGPU = GPUTextureFormat.R16Sint;
						break;

					case UnsignedShortType:
						formatGPU = GPUTextureFormat.R16Uint;
						break;

					case UnsignedIntType:
						formatGPU = GPUTextureFormat.R32Uint;
						break;

					case IntType:
						formatGPU = GPUTextureFormat.R32Sint;
						break;

					case UnsignedByteType:
						formatGPU = GPUTextureFormat.R8Unorm;
						break;

					case HalfFloatType:
						formatGPU = GPUTextureFormat.R16Float;
						break;

					case FloatType:
						formatGPU = GPUTextureFormat.R32Float;
						break;

					default:
						console.error( 'WebGPURenderer: Unsupported texture type with RedFormat.', type );

				}

				break;

			case RGFormat:

				switch ( type ) {

					case ByteType:
						formatGPU = GPUTextureFormat.RG8Snorm;
						break;

					case ShortType:
						formatGPU = GPUTextureFormat.RG16Sint;
						break;

					case UnsignedShortType:
						formatGPU = GPUTextureFormat.RG16Uint;
						break;

					case UnsignedIntType:
						formatGPU = GPUTextureFormat.RG32Uint;
						break;

					case IntType:
						formatGPU = GPUTextureFormat.RG32Sint;
						break;

					case UnsignedByteType:
						formatGPU = GPUTextureFormat.RG8Unorm;
						break;

					case HalfFloatType:
						formatGPU = GPUTextureFormat.RG16Float;
						break;

					case FloatType:
						formatGPU = GPUTextureFormat.RG32Float;
						break;

					default:
						console.error( 'WebGPURenderer: Unsupported texture type with RGFormat.', type );

				}

				break;

			case DepthFormat:

				switch ( type ) {

					case UnsignedShortType:
						formatGPU = GPUTextureFormat.Depth16Unorm;
						break;

					case UnsignedIntType:
						formatGPU = GPUTextureFormat.Depth24Plus;
						break;

					case FloatType:
						formatGPU = GPUTextureFormat.Depth32Float;
						break;

					default:
						console.error( 'WebGPURenderer: Unsupported texture type with DepthFormat.', type );

				}

				break;

			case DepthStencilFormat:

				switch ( type ) {

					case UnsignedInt248Type:
						formatGPU = GPUTextureFormat.Depth24PlusStencil8;
						break;

					case FloatType:

						if ( device && device.features.has( GPUFeatureName.Depth32FloatStencil8 ) === false ) {

							console.error( 'WebGPURenderer: Depth textures with DepthStencilFormat + FloatType can only be used with the "depth32float-stencil8" GPU feature.' );

						}

						formatGPU = GPUTextureFormat.Depth32FloatStencil8;

						break;

					default:
						console.error( 'WebGPURenderer: Unsupported texture type with DepthStencilFormat.', type );

				}

				break;

			case RedIntegerFormat:

				switch ( type ) {

					case IntType:
						formatGPU = GPUTextureFormat.R32Sint;
						break;

					case UnsignedIntType:
						formatGPU = GPUTextureFormat.R32Uint;
						break;

					default:
						console.error( 'WebGPURenderer: Unsupported texture type with RedIntegerFormat.', type );

				}

				break;

			case RGIntegerFormat:

				switch ( type ) {

					case IntType:
						formatGPU = GPUTextureFormat.RG32Sint;
						break;

					case UnsignedIntType:
						formatGPU = GPUTextureFormat.RG32Uint;
						break;

					default:
						console.error( 'WebGPURenderer: Unsupported texture type with RGIntegerFormat.', type );

				}

				break;

			case RGBAIntegerFormat:

				switch ( type ) {

					case IntType:
						formatGPU = GPUTextureFormat.RGBA32Sint;
						break;

					case UnsignedIntType:
						formatGPU = GPUTextureFormat.RGBA32Uint;
						break;

					default:
						console.error( 'WebGPURenderer: Unsupported texture type with RGBAIntegerFormat.', type );

				}

				break;

			default:
				console.error( 'WebGPURenderer: Unsupported texture format.', format );

		}

	}

	return formatGPU;

}
```
</details>


---

## Classes

### `WebGPUTextureUtils`

<details><summary>Class Code</summary>

```ts
class WebGPUTextureUtils {

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
		 * A reference to the pass utils.
		 *
		 * @type {?WebGPUTexturePassUtils}
		 * @default null
		 */
		this._passUtils = null;

		/**
		 * A dictionary for managing default textures. The key
		 * is the texture format, the value the texture object.
		 *
		 * @type {Object<string,Texture>}
		 */
		this.defaultTexture = {};

		/**
		 * A dictionary for managing default cube textures. The key
		 * is the texture format, the value the texture object.
		 *
		 * @type {Object<string,CubeTexture>}
		 */
		this.defaultCubeTexture = {};

		/**
		 * A default video frame.
		 *
		 * @type {?VideoFrame}
		 * @default null
		 */
		this.defaultVideoFrame = null;

		/**
		 * Represents the color attachment of the default framebuffer.
		 *
		 * @type {?GPUTexture}
		 * @default null
		 */
		this.colorBuffer = null;

		/**
		 * Represents the depth attachment of the default framebuffer.
		 *
		 * @type {DepthTexture}
		 */
		this.depthTexture = new DepthTexture();
		this.depthTexture.name = 'depthBuffer';

	}

	/**
	 * Creates a GPU sampler for the given texture.
	 *
	 * @param {Texture} texture - The texture to create the sampler for.
	 */
	createSampler( texture ) {

		const backend = this.backend;
		const device = backend.device;

		const textureGPU = backend.get( texture );

		const samplerDescriptorGPU = {
			addressModeU: this._convertAddressMode( texture.wrapS ),
			addressModeV: this._convertAddressMode( texture.wrapT ),
			addressModeW: this._convertAddressMode( texture.wrapR ),
			magFilter: this._convertFilterMode( texture.magFilter ),
			minFilter: this._convertFilterMode( texture.minFilter ),
			mipmapFilter: this._convertFilterMode( texture.minFilter ),
			maxAnisotropy: 1
		};

		// anisotropy can only be used when all filter modes are set to linear.

		if ( samplerDescriptorGPU.magFilter === GPUFilterMode.Linear && samplerDescriptorGPU.minFilter === GPUFilterMode.Linear && samplerDescriptorGPU.mipmapFilter === GPUFilterMode.Linear ) {

			samplerDescriptorGPU.maxAnisotropy = texture.anisotropy;

		}

		if ( texture.isDepthTexture && texture.compareFunction !== null ) {

			samplerDescriptorGPU.compare = _compareToWebGPU[ texture.compareFunction ];

		}

		textureGPU.sampler = device.createSampler( samplerDescriptorGPU );

	}

	/**
	 * Creates a default texture for the given texture that can be used
	 * as a placeholder until the actual texture is ready for usage.
	 *
	 * @param {Texture} texture - The texture to create a default texture for.
	 */
	createDefaultTexture( texture ) {

		let textureGPU;

		const format = getFormat( texture );

		if ( texture.isCubeTexture ) {

			textureGPU = this._getDefaultCubeTextureGPU( format );

		} else {

			textureGPU = this._getDefaultTextureGPU( format );

		}

		this.backend.get( texture ).texture = textureGPU;

	}

	/**
	 * Defines a texture on the GPU for the given texture object.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {Object} [options={}] - Optional configuration parameter.
	 */
	createTexture( texture, options = {} ) {

		const backend = this.backend;
		const textureData = backend.get( texture );

		if ( textureData.initialized ) {

			throw new Error( 'WebGPUTextureUtils: Texture already initialized.' );

		}

		if ( options.needsMipmaps === undefined ) options.needsMipmaps = false;
		if ( options.levels === undefined ) options.levels = 1;
		if ( options.depth === undefined ) options.depth = 1;

		const { width, height, depth, levels } = options;

		if ( texture.isFramebufferTexture ) {

			if ( options.renderTarget ) {

				options.format = this.backend.utils.getCurrentColorFormat( options.renderTarget );

			} else {

				options.format = this.backend.utils.getPreferredCanvasFormat();

			}

		}

		const dimension = this._getDimension( texture );
		const format = texture.internalFormat || options.format || getFormat( texture, backend.device );

		textureData.format = format;

		const { samples, primarySamples, isMSAA } = backend.utils.getTextureSampleData( texture );

		let usage = GPUTextureUsage.TEXTURE_BINDING | GPUTextureUsage.COPY_DST | GPUTextureUsage.COPY_SRC;

		if ( texture.isStorageTexture === true ) {

			usage |= GPUTextureUsage.STORAGE_BINDING;

		}

		if ( texture.isCompressedTexture !== true && texture.isCompressedArrayTexture !== true ) {

			usage |= GPUTextureUsage.RENDER_ATTACHMENT;

		}

		const textureDescriptorGPU = {
			label: texture.name,
			size: {
				width: width,
				height: height,
				depthOrArrayLayers: depth,
			},
			mipLevelCount: levels,
			sampleCount: primarySamples,
			dimension: dimension,
			format: format,
			usage: usage
		};

		// texture creation

		if ( format === undefined ) {

			console.warn( 'WebGPURenderer: Texture format not supported.' );

			this.createDefaultTexture( texture );
			return;

		}

		if ( texture.isCubeTexture ) {

			textureDescriptorGPU.textureBindingViewDimension = GPUTextureViewDimension.Cube;

		}

		textureData.texture = backend.device.createTexture( textureDescriptorGPU );

		if ( isMSAA ) {

			const msaaTextureDescriptorGPU = Object.assign( {}, textureDescriptorGPU );

			msaaTextureDescriptorGPU.label = msaaTextureDescriptorGPU.label + '-msaa';
			msaaTextureDescriptorGPU.sampleCount = samples;
			msaaTextureDescriptorGPU.mipLevelCount = 1; // See https://www.w3.org/TR/webgpu/#texture-creation

			textureData.msaaTexture = backend.device.createTexture( msaaTextureDescriptorGPU );

		}

		textureData.initialized = true;

		textureData.textureDescriptorGPU = textureDescriptorGPU;

	}

	/**
	 * Destroys the GPU data for the given texture object.
	 *
	 * @param {Texture} texture - The texture.
	 */
	destroyTexture( texture ) {

		const backend = this.backend;
		const textureData = backend.get( texture );

		if ( textureData.texture !== undefined ) textureData.texture.destroy();

		if ( textureData.msaaTexture !== undefined ) textureData.msaaTexture.destroy();

		backend.delete( texture );

	}

	/**
	 * Destroys the GPU sampler for the given texture.
	 *
	 * @param {Texture} texture - The texture to destroy the sampler for.
	 */
	destroySampler( texture ) {

		const backend = this.backend;
		const textureData = backend.get( texture );

		delete textureData.sampler;

	}

	/**
	 * Generates mipmaps for the given texture.
	 *
	 * @param {Texture} texture - The texture.
	 */
	generateMipmaps( texture ) {

		const textureData = this.backend.get( texture );

		if ( texture.isCubeTexture ) {

			for ( let i = 0; i < 6; i ++ ) {

				this._generateMipmaps( textureData.texture, textureData.textureDescriptorGPU, i );

			}

		} else {

			const depth = texture.image.depth || 1;

			for ( let i = 0; i < depth; i ++ ) {

				this._generateMipmaps( textureData.texture, textureData.textureDescriptorGPU, i );

			}

		}

	}

	/**
	 * Returns the color buffer representing the color
	 * attachment of the default framebuffer.
	 *
	 * @return {GPUTexture} The color buffer.
	 */
	getColorBuffer() {

		if ( this.colorBuffer ) this.colorBuffer.destroy();

		const backend = this.backend;
		const { width, height } = backend.getDrawingBufferSize();

		this.colorBuffer = backend.device.createTexture( {
			label: 'colorBuffer',
			size: {
				width: width,
				height: height,
				depthOrArrayLayers: 1
			},
			sampleCount: backend.utils.getSampleCount( backend.renderer.samples ),
			format: backend.utils.getPreferredCanvasFormat(),
			usage: GPUTextureUsage.RENDER_ATTACHMENT | GPUTextureUsage.COPY_SRC
		} );

		return this.colorBuffer;

	}

	/**
	 * Returns the depth buffer representing the depth
	 * attachment of the default framebuffer.
	 *
	 * @param {boolean} [depth=true] - Whether depth is enabled or not.
	 * @param {boolean} [stencil=false] -  Whether stencil is enabled or not.
	 * @return {GPUTexture} The depth buffer.
	 */
	getDepthBuffer( depth = true, stencil = false ) {

		const backend = this.backend;
		const { width, height } = backend.getDrawingBufferSize();

		const depthTexture = this.depthTexture;
		const depthTextureGPU = backend.get( depthTexture ).texture;

		let format, type;

		if ( stencil ) {

			format = DepthStencilFormat;
			type = UnsignedInt248Type;

		} else if ( depth ) {

			format = DepthFormat;
			type = UnsignedIntType;

		}

		if ( depthTextureGPU !== undefined ) {

			if ( depthTexture.image.width === width && depthTexture.image.height === height && depthTexture.format === format && depthTexture.type === type ) {

				return depthTextureGPU;

			}

			this.destroyTexture( depthTexture );

		}

		depthTexture.name = 'depthBuffer';
		depthTexture.format = format;
		depthTexture.type = type;
		depthTexture.image.width = width;
		depthTexture.image.height = height;

		this.createTexture( depthTexture, { width, height } );

		return backend.get( depthTexture ).texture;

	}

	/**
	 * Uploads the updated texture data to the GPU.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {Object} [options={}] - Optional configuration parameter.
	 */
	updateTexture( texture, options ) {

		const textureData = this.backend.get( texture );

		const { textureDescriptorGPU } = textureData;

		if ( texture.isRenderTargetTexture || ( textureDescriptorGPU === undefined /* unsupported texture format */ ) )
			return;

		// transfer texture data

		if ( texture.isDataTexture ) {

			this._copyBufferToTexture( options.image, textureData.texture, textureDescriptorGPU, 0, texture.flipY );

		} else if ( texture.isArrayTexture || texture.isDataArrayTexture || texture.isData3DTexture ) {

			for ( let i = 0; i < options.image.depth; i ++ ) {

				this._copyBufferToTexture( options.image, textureData.texture, textureDescriptorGPU, i, texture.flipY, i );

			}

		} else if ( texture.isCompressedTexture || texture.isCompressedArrayTexture ) {

			this._copyCompressedBufferToTexture( texture.mipmaps, textureData.texture, textureDescriptorGPU );

		} else if ( texture.isCubeTexture ) {

			this._copyCubeMapToTexture( options.images, textureData.texture, textureDescriptorGPU, texture.flipY, texture.premultiplyAlpha );

		} else {

			this._copyImageToTexture( options.image, textureData.texture, textureDescriptorGPU, 0, texture.flipY, texture.premultiplyAlpha );

		}

		//

		textureData.version = texture.version;

		if ( texture.onUpdate ) texture.onUpdate( texture );

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

		const device = this.backend.device;

		const textureData = this.backend.get( texture );
		const textureGPU = textureData.texture;
		const format = textureData.textureDescriptorGPU.format;
		const bytesPerTexel = this._getBytesPerTexel( format );

		let bytesPerRow = width * bytesPerTexel;
		bytesPerRow = Math.ceil( bytesPerRow / 256 ) * 256; // Align to 256 bytes

		const readBuffer = device.createBuffer(
			{
				size: width * height * bytesPerTexel,
				usage: GPUBufferUsage.COPY_DST | GPUBufferUsage.MAP_READ
			}
		);

		const encoder = device.createCommandEncoder();

		encoder.copyTextureToBuffer(
			{
				texture: textureGPU,
				origin: { x, y, z: faceIndex },
			},
			{
				buffer: readBuffer,
				bytesPerRow: bytesPerRow
			},
			{
				width: width,
				height: height
			}

		);

		const typedArrayType = this._getTypedArrayType( format );

		device.queue.submit( [ encoder.finish() ] );

		await readBuffer.mapAsync( GPUMapMode.READ );

		const buffer = readBuffer.getMappedRange();

		return new typedArrayType( buffer );

	}

	/**
	 * Returns the default GPU texture for the given format.
	 *
	 * @private
	 * @param {string} format - The GPU format.
	 * @return {GPUTexture} The GPU texture.
	 */
	_getDefaultTextureGPU( format ) {

		let defaultTexture = this.defaultTexture[ format ];

		if ( defaultTexture === undefined ) {

			const texture = new Texture();
			texture.minFilter = NearestFilter;
			texture.magFilter = NearestFilter;

			this.createTexture( texture, { width: 1, height: 1, format } );

			this.defaultTexture[ format ] = defaultTexture = texture;

		}

		return this.backend.get( defaultTexture ).texture;

	}

	/**
	 * Returns the default GPU cube texture for the given format.
	 *
	 * @private
	 * @param {string} format - The GPU format.
	 * @return {GPUTexture} The GPU texture.
	 */
	_getDefaultCubeTextureGPU( format ) {

		let defaultCubeTexture = this.defaultTexture[ format ];

		if ( defaultCubeTexture === undefined ) {

			const texture = new CubeTexture();
			texture.minFilter = NearestFilter;
			texture.magFilter = NearestFilter;

			this.createTexture( texture, { width: 1, height: 1, depth: 6 } );

			this.defaultCubeTexture[ format ] = defaultCubeTexture = texture;

		}

		return this.backend.get( defaultCubeTexture ).texture;

	}

	/**
	 * Uploads cube texture image data to the GPU memory.
	 *
	 * @private
	 * @param {Array} images - The cube image data.
	 * @param {GPUTexture} textureGPU - The GPU texture.
	 * @param {Object} textureDescriptorGPU - The GPU texture descriptor.
	 * @param {boolean} flipY - Whether to flip texture data along their vertical axis or not.
	 * @param {boolean} premultiplyAlpha - Whether the texture should have its RGB channels premultiplied by the alpha channel or not.
	 */
	_copyCubeMapToTexture( images, textureGPU, textureDescriptorGPU, flipY, premultiplyAlpha ) {

		for ( let i = 0; i < 6; i ++ ) {

			const image = images[ i ];

			const flipIndex = flipY === true ? _flipMap[ i ] : i;

			if ( image.isDataTexture ) {

				this._copyBufferToTexture( image.image, textureGPU, textureDescriptorGPU, flipIndex, flipY );

			} else {

				this._copyImageToTexture( image, textureGPU, textureDescriptorGPU, flipIndex, flipY, premultiplyAlpha );

			}

		}

	}

	/**
	 * Uploads texture image data to the GPU memory.
	 *
	 * @private
	 * @param {HTMLImageElement|ImageBitmap|HTMLCanvasElement} image - The image data.
	 * @param {GPUTexture} textureGPU - The GPU texture.
	 * @param {Object} textureDescriptorGPU - The GPU texture descriptor.
	 * @param {number} originDepth - The origin depth.
	 * @param {boolean} flipY - Whether to flip texture data along their vertical axis or not.
	 * @param {boolean} premultiplyAlpha - Whether the texture should have its RGB channels premultiplied by the alpha channel or not.
	 */
	_copyImageToTexture( image, textureGPU, textureDescriptorGPU, originDepth, flipY, premultiplyAlpha ) {

		const device = this.backend.device;

		device.queue.copyExternalImageToTexture(
			{
				source: image,
				flipY: flipY
			}, {
				texture: textureGPU,
				mipLevel: 0,
				origin: { x: 0, y: 0, z: originDepth },
				premultipliedAlpha: premultiplyAlpha
			}, {
				width: textureDescriptorGPU.size.width,
				height: textureDescriptorGPU.size.height,
				depthOrArrayLayers: 1
			}
		);

	}

	/**
	 * Returns the pass utils singleton.
	 *
	 * @private
	 * @return {WebGPUTexturePassUtils} The utils instance.
	 */
	_getPassUtils() {

		let passUtils = this._passUtils;

		if ( passUtils === null ) {

			this._passUtils = passUtils = new WebGPUTexturePassUtils( this.backend.device );

		}

		return passUtils;

	}

	/**
	 * Generates mipmaps for the given GPU texture.
	 *
	 * @private
	 * @param {GPUTexture} textureGPU - The GPU texture object.
	 * @param {Object} textureDescriptorGPU - The texture descriptor.
	 * @param {number} [baseArrayLayer=0] - The index of the first array layer accessible to the texture view.
	 */
	_generateMipmaps( textureGPU, textureDescriptorGPU, baseArrayLayer = 0 ) {

		this._getPassUtils().generateMipmaps( textureGPU, textureDescriptorGPU, baseArrayLayer );

	}

	/**
	 * Flip the contents of the given GPU texture along its vertical axis.
	 *
	 * @private
	 * @param {GPUTexture} textureGPU - The GPU texture object.
	 * @param {Object} textureDescriptorGPU - The texture descriptor.
	 * @param {number} [originDepth=0] - The origin depth.
	 */
	_flipY( textureGPU, textureDescriptorGPU, originDepth = 0 ) {

		this._getPassUtils().flipY( textureGPU, textureDescriptorGPU, originDepth );

	}

	/**
	 * Uploads texture buffer data to the GPU memory.
	 *
	 * @private
	 * @param {Object} image - An object defining the image buffer data.
	 * @param {GPUTexture} textureGPU - The GPU texture.
	 * @param {Object} textureDescriptorGPU - The GPU texture descriptor.
	 * @param {number} originDepth - The origin depth.
	 * @param {boolean} flipY - Whether to flip texture data along their vertical axis or not.
	 * @param {number} [depth=0] - TODO.
	 */
	_copyBufferToTexture( image, textureGPU, textureDescriptorGPU, originDepth, flipY, depth = 0 ) {

		// @TODO: Consider to use GPUCommandEncoder.copyBufferToTexture()
		// @TODO: Consider to support valid buffer layouts with other formats like RGB

		const device = this.backend.device;

		const data = image.data;

		const bytesPerTexel = this._getBytesPerTexel( textureDescriptorGPU.format );
		const bytesPerRow = image.width * bytesPerTexel;

		device.queue.writeTexture(
			{
				texture: textureGPU,
				mipLevel: 0,
				origin: { x: 0, y: 0, z: originDepth }
			},
			data,
			{
				offset: image.width * image.height * bytesPerTexel * depth,
				bytesPerRow
			},
			{
				width: image.width,
				height: image.height,
				depthOrArrayLayers: 1
			} );

		if ( flipY === true ) {

			this._flipY( textureGPU, textureDescriptorGPU, originDepth );

		}

	}

	/**
	 * Uploads compressed texture data to the GPU memory.
	 *
	 * @private
	 * @param {Array<Object>} mipmaps - An array with mipmap data.
	 * @param {GPUTexture} textureGPU - The GPU texture.
	 * @param {Object} textureDescriptorGPU - The GPU texture descriptor.
	 */
	_copyCompressedBufferToTexture( mipmaps, textureGPU, textureDescriptorGPU ) {

		// @TODO: Consider to use GPUCommandEncoder.copyBufferToTexture()

		const device = this.backend.device;

		const blockData = this._getBlockData( textureDescriptorGPU.format );
		const isArrayTexture = textureDescriptorGPU.size.depthOrArrayLayers > 1;

		for ( let i = 0; i < mipmaps.length; i ++ ) {

			const mipmap = mipmaps[ i ];

			const width = mipmap.width;
			const height = mipmap.height;
			const depth = isArrayTexture ? textureDescriptorGPU.size.depthOrArrayLayers : 1;

			const bytesPerRow = Math.ceil( width / blockData.width ) * blockData.byteLength;
			const bytesPerImage = bytesPerRow * Math.ceil( height / blockData.height );

			for ( let j = 0; j < depth; j ++ ) {

				device.queue.writeTexture(
					{
						texture: textureGPU,
						mipLevel: i,
						origin: { x: 0, y: 0, z: j }
					},
					mipmap.data,
					{
						offset: j * bytesPerImage,
						bytesPerRow,
						rowsPerImage: Math.ceil( height / blockData.height )
					},
					{
						width: Math.ceil( width / blockData.width ) * blockData.width,
						height: Math.ceil( height / blockData.height ) * blockData.height,
						depthOrArrayLayers: 1
					}
				);

			}

		}

	}

	/**
	 * This method is only relevant for compressed texture formats. It returns a block
	 * data descriptor for the given GPU compressed texture format.
	 *
	 * @private
	 * @param {string} format - The GPU compressed texture format.
	 * @return {Object} The block data descriptor.
	 */
	_getBlockData( format ) {

		if ( format === GPUTextureFormat.BC1RGBAUnorm || format === GPUTextureFormat.BC1RGBAUnormSRGB ) return { byteLength: 8, width: 4, height: 4 }; // DXT1
		if ( format === GPUTextureFormat.BC2RGBAUnorm || format === GPUTextureFormat.BC2RGBAUnormSRGB ) return { byteLength: 16, width: 4, height: 4 }; // DXT3
		if ( format === GPUTextureFormat.BC3RGBAUnorm || format === GPUTextureFormat.BC3RGBAUnormSRGB ) return { byteLength: 16, width: 4, height: 4 }; // DXT5
		if ( format === GPUTextureFormat.BC4RUnorm || format === GPUTextureFormat.BC4RSnorm ) return { byteLength: 8, width: 4, height: 4 }; // RGTC1
		if ( format === GPUTextureFormat.BC5RGUnorm || format === GPUTextureFormat.BC5RGSnorm ) return { byteLength: 16, width: 4, height: 4 }; // RGTC2
		if ( format === GPUTextureFormat.BC6HRGBUFloat || format === GPUTextureFormat.BC6HRGBFloat ) return { byteLength: 16, width: 4, height: 4 }; // BPTC (float)
		if ( format === GPUTextureFormat.BC7RGBAUnorm || format === GPUTextureFormat.BC7RGBAUnormSRGB ) return { byteLength: 16, width: 4, height: 4 }; // BPTC (unorm)

		if ( format === GPUTextureFormat.ETC2RGB8Unorm || format === GPUTextureFormat.ETC2RGB8UnormSRGB ) return { byteLength: 8, width: 4, height: 4 };
		if ( format === GPUTextureFormat.ETC2RGB8A1Unorm || format === GPUTextureFormat.ETC2RGB8A1UnormSRGB ) return { byteLength: 8, width: 4, height: 4 };
		if ( format === GPUTextureFormat.ETC2RGBA8Unorm || format === GPUTextureFormat.ETC2RGBA8UnormSRGB ) return { byteLength: 16, width: 4, height: 4 };
		if ( format === GPUTextureFormat.EACR11Unorm ) return { byteLength: 8, width: 4, height: 4 };
		if ( format === GPUTextureFormat.EACR11Snorm ) return { byteLength: 8, width: 4, height: 4 };
		if ( format === GPUTextureFormat.EACRG11Unorm ) return { byteLength: 16, width: 4, height: 4 };
		if ( format === GPUTextureFormat.EACRG11Snorm ) return { byteLength: 16, width: 4, height: 4 };

		if ( format === GPUTextureFormat.ASTC4x4Unorm || format === GPUTextureFormat.ASTC4x4UnormSRGB ) return { byteLength: 16, width: 4, height: 4 };
		if ( format === GPUTextureFormat.ASTC5x4Unorm || format === GPUTextureFormat.ASTC5x4UnormSRGB ) return { byteLength: 16, width: 5, height: 4 };
		if ( format === GPUTextureFormat.ASTC5x5Unorm || format === GPUTextureFormat.ASTC5x5UnormSRGB ) return { byteLength: 16, width: 5, height: 5 };
		if ( format === GPUTextureFormat.ASTC6x5Unorm || format === GPUTextureFormat.ASTC6x5UnormSRGB ) return { byteLength: 16, width: 6, height: 5 };
		if ( format === GPUTextureFormat.ASTC6x6Unorm || format === GPUTextureFormat.ASTC6x6UnormSRGB ) return { byteLength: 16, width: 6, height: 6 };
		if ( format === GPUTextureFormat.ASTC8x5Unorm || format === GPUTextureFormat.ASTC8x5UnormSRGB ) return { byteLength: 16, width: 8, height: 5 };
		if ( format === GPUTextureFormat.ASTC8x6Unorm || format === GPUTextureFormat.ASTC8x6UnormSRGB ) return { byteLength: 16, width: 8, height: 6 };
		if ( format === GPUTextureFormat.ASTC8x8Unorm || format === GPUTextureFormat.ASTC8x8UnormSRGB ) return { byteLength: 16, width: 8, height: 8 };
		if ( format === GPUTextureFormat.ASTC10x5Unorm || format === GPUTextureFormat.ASTC10x5UnormSRGB ) return { byteLength: 16, width: 10, height: 5 };
		if ( format === GPUTextureFormat.ASTC10x6Unorm || format === GPUTextureFormat.ASTC10x6UnormSRGB ) return { byteLength: 16, width: 10, height: 6 };
		if ( format === GPUTextureFormat.ASTC10x8Unorm || format === GPUTextureFormat.ASTC10x8UnormSRGB ) return { byteLength: 16, width: 10, height: 8 };
		if ( format === GPUTextureFormat.ASTC10x10Unorm || format === GPUTextureFormat.ASTC10x10UnormSRGB ) return { byteLength: 16, width: 10, height: 10 };
		if ( format === GPUTextureFormat.ASTC12x10Unorm || format === GPUTextureFormat.ASTC12x10UnormSRGB ) return { byteLength: 16, width: 12, height: 10 };
		if ( format === GPUTextureFormat.ASTC12x12Unorm || format === GPUTextureFormat.ASTC12x12UnormSRGB ) return { byteLength: 16, width: 12, height: 12 };

	}

	/**
	 * Converts the three.js uv wrapping constants to GPU address mode constants.
	 *
	 * @private
	 * @param {number} value - The three.js constant defining a uv wrapping mode.
	 * @return {string} The GPU address mode.
	 */
	_convertAddressMode( value ) {

		let addressMode = GPUAddressMode.ClampToEdge;

		if ( value === RepeatWrapping ) {

			addressMode = GPUAddressMode.Repeat;

		} else if ( value === MirroredRepeatWrapping ) {

			addressMode = GPUAddressMode.MirrorRepeat;

		}

		return addressMode;

	}

	/**
	 * Converts the three.js filter constants to GPU filter constants.
	 *
	 * @private
	 * @param {number} value - The three.js constant defining a filter mode.
	 * @return {string} The GPU filter mode.
	 */
	_convertFilterMode( value ) {

		let filterMode = GPUFilterMode.Linear;

		if ( value === NearestFilter || value === NearestMipmapNearestFilter || value === NearestMipmapLinearFilter ) {

			filterMode = GPUFilterMode.Nearest;

		}

		return filterMode;

	}

	/**
	 * Returns the bytes-per-texel value for the given GPU texture format.
	 *
	 * @private
	 * @param {string} format - The GPU texture format.
	 * @return {number} The bytes-per-texel.
	 */
	_getBytesPerTexel( format ) {

		// 8-bit formats
		if ( format === GPUTextureFormat.R8Unorm ||
			format === GPUTextureFormat.R8Snorm ||
			format === GPUTextureFormat.R8Uint ||
			format === GPUTextureFormat.R8Sint ) return 1;

		// 16-bit formats
		if ( format === GPUTextureFormat.R16Uint ||
			format === GPUTextureFormat.R16Sint ||
			format === GPUTextureFormat.R16Float ||
			format === GPUTextureFormat.RG8Unorm ||
			format === GPUTextureFormat.RG8Snorm ||
			format === GPUTextureFormat.RG8Uint ||
			format === GPUTextureFormat.RG8Sint ) return 2;

		// 32-bit formats
		if ( format === GPUTextureFormat.R32Uint ||
			format === GPUTextureFormat.R32Sint ||
			format === GPUTextureFormat.R32Float ||
			format === GPUTextureFormat.RG16Uint ||
			format === GPUTextureFormat.RG16Sint ||
			format === GPUTextureFormat.RG16Float ||
			format === GPUTextureFormat.RGBA8Unorm ||
			format === GPUTextureFormat.RGBA8UnormSRGB ||
			format === GPUTextureFormat.RGBA8Snorm ||
			format === GPUTextureFormat.RGBA8Uint ||
			format === GPUTextureFormat.RGBA8Sint ||
			format === GPUTextureFormat.BGRA8Unorm ||
			format === GPUTextureFormat.BGRA8UnormSRGB ||
			// Packed 32-bit formats
			format === GPUTextureFormat.RGB9E5UFloat ||
			format === GPUTextureFormat.RGB10A2Unorm ||
			format === GPUTextureFormat.RG11B10UFloat ||
			format === GPUTextureFormat.Depth32Float ||
			format === GPUTextureFormat.Depth24Plus ||
			format === GPUTextureFormat.Depth24PlusStencil8 ||
			format === GPUTextureFormat.Depth32FloatStencil8 ) return 4;

		// 64-bit formats
		if ( format === GPUTextureFormat.RG32Uint ||
			format === GPUTextureFormat.RG32Sint ||
			format === GPUTextureFormat.RG32Float ||
			format === GPUTextureFormat.RGBA16Uint ||
			format === GPUTextureFormat.RGBA16Sint ||
			format === GPUTextureFormat.RGBA16Float ) return 8;

		// 128-bit formats
		if ( format === GPUTextureFormat.RGBA32Uint ||
			format === GPUTextureFormat.RGBA32Sint ||
			format === GPUTextureFormat.RGBA32Float ) return 16;


	}

	/**
	 * Returns the corresponding typed array type for the given GPU texture format.
	 *
	 * @private
	 * @param {string} format - The GPU texture format.
	 * @return {TypedArray.constructor} The typed array type.
	 */
	_getTypedArrayType( format ) {

		if ( format === GPUTextureFormat.R8Uint ) return Uint8Array;
		if ( format === GPUTextureFormat.R8Sint ) return Int8Array;
		if ( format === GPUTextureFormat.R8Unorm ) return Uint8Array;
		if ( format === GPUTextureFormat.R8Snorm ) return Int8Array;
		if ( format === GPUTextureFormat.RG8Uint ) return Uint8Array;
		if ( format === GPUTextureFormat.RG8Sint ) return Int8Array;
		if ( format === GPUTextureFormat.RG8Unorm ) return Uint8Array;
		if ( format === GPUTextureFormat.RG8Snorm ) return Int8Array;
		if ( format === GPUTextureFormat.RGBA8Uint ) return Uint8Array;
		if ( format === GPUTextureFormat.RGBA8Sint ) return Int8Array;
		if ( format === GPUTextureFormat.RGBA8Unorm ) return Uint8Array;
		if ( format === GPUTextureFormat.RGBA8Snorm ) return Int8Array;


		if ( format === GPUTextureFormat.R16Uint ) return Uint16Array;
		if ( format === GPUTextureFormat.R16Sint ) return Int16Array;
		if ( format === GPUTextureFormat.RG16Uint ) return Uint16Array;
		if ( format === GPUTextureFormat.RG16Sint ) return Int16Array;
		if ( format === GPUTextureFormat.RGBA16Uint ) return Uint16Array;
		if ( format === GPUTextureFormat.RGBA16Sint ) return Int16Array;
		if ( format === GPUTextureFormat.R16Float ) return Uint16Array;
		if ( format === GPUTextureFormat.RG16Float ) return Uint16Array;
		if ( format === GPUTextureFormat.RGBA16Float ) return Uint16Array;


		if ( format === GPUTextureFormat.R32Uint ) return Uint32Array;
		if ( format === GPUTextureFormat.R32Sint ) return Int32Array;
		if ( format === GPUTextureFormat.R32Float ) return Float32Array;
		if ( format === GPUTextureFormat.RG32Uint ) return Uint32Array;
		if ( format === GPUTextureFormat.RG32Sint ) return Int32Array;
		if ( format === GPUTextureFormat.RG32Float ) return Float32Array;
		if ( format === GPUTextureFormat.RGBA32Uint ) return Uint32Array;
		if ( format === GPUTextureFormat.RGBA32Sint ) return Int32Array;
		if ( format === GPUTextureFormat.RGBA32Float ) return Float32Array;

		if ( format === GPUTextureFormat.BGRA8Unorm ) return Uint8Array;
		if ( format === GPUTextureFormat.BGRA8UnormSRGB ) return Uint8Array;
		if ( format === GPUTextureFormat.RGB10A2Unorm ) return Uint32Array;
		if ( format === GPUTextureFormat.RGB9E5UFloat ) return Uint32Array;
		if ( format === GPUTextureFormat.RG11B10UFloat ) return Uint32Array;

		if ( format === GPUTextureFormat.Depth32Float ) return Float32Array;
		if ( format === GPUTextureFormat.Depth24Plus ) return Uint32Array;
		if ( format === GPUTextureFormat.Depth24PlusStencil8 ) return Uint32Array;
		if ( format === GPUTextureFormat.Depth32FloatStencil8 ) return Float32Array;

	}

	/**
	 * Returns the GPU dimensions for the given texture.
	 *
	 * @private
	 * @param {Texture} texture - The texture.
	 * @return {string} The GPU dimension.
	 */
	_getDimension( texture ) {

		let dimension;

		if ( texture.is3DTexture || texture.isData3DTexture ) {

			dimension = GPUTextureDimension.ThreeD;

		} else {

			dimension = GPUTextureDimension.TwoD;

		}

		return dimension;

	}

}
```
</details>

#### Methods

##### `createSampler(texture: Texture): void`

<details><summary>Code</summary>

```ts
createSampler( texture ) {

		const backend = this.backend;
		const device = backend.device;

		const textureGPU = backend.get( texture );

		const samplerDescriptorGPU = {
			addressModeU: this._convertAddressMode( texture.wrapS ),
			addressModeV: this._convertAddressMode( texture.wrapT ),
			addressModeW: this._convertAddressMode( texture.wrapR ),
			magFilter: this._convertFilterMode( texture.magFilter ),
			minFilter: this._convertFilterMode( texture.minFilter ),
			mipmapFilter: this._convertFilterMode( texture.minFilter ),
			maxAnisotropy: 1
		};

		// anisotropy can only be used when all filter modes are set to linear.

		if ( samplerDescriptorGPU.magFilter === GPUFilterMode.Linear && samplerDescriptorGPU.minFilter === GPUFilterMode.Linear && samplerDescriptorGPU.mipmapFilter === GPUFilterMode.Linear ) {

			samplerDescriptorGPU.maxAnisotropy = texture.anisotropy;

		}

		if ( texture.isDepthTexture && texture.compareFunction !== null ) {

			samplerDescriptorGPU.compare = _compareToWebGPU[ texture.compareFunction ];

		}

		textureGPU.sampler = device.createSampler( samplerDescriptorGPU );

	}
```
</details>

##### `createDefaultTexture(texture: Texture): void`

<details><summary>Code</summary>

```ts
createDefaultTexture( texture ) {

		let textureGPU;

		const format = getFormat( texture );

		if ( texture.isCubeTexture ) {

			textureGPU = this._getDefaultCubeTextureGPU( format );

		} else {

			textureGPU = this._getDefaultTextureGPU( format );

		}

		this.backend.get( texture ).texture = textureGPU;

	}
```
</details>

##### `createTexture(texture: Texture, options: any): void`

<details><summary>Code</summary>

```ts
createTexture( texture, options = {} ) {

		const backend = this.backend;
		const textureData = backend.get( texture );

		if ( textureData.initialized ) {

			throw new Error( 'WebGPUTextureUtils: Texture already initialized.' );

		}

		if ( options.needsMipmaps === undefined ) options.needsMipmaps = false;
		if ( options.levels === undefined ) options.levels = 1;
		if ( options.depth === undefined ) options.depth = 1;

		const { width, height, depth, levels } = options;

		if ( texture.isFramebufferTexture ) {

			if ( options.renderTarget ) {

				options.format = this.backend.utils.getCurrentColorFormat( options.renderTarget );

			} else {

				options.format = this.backend.utils.getPreferredCanvasFormat();

			}

		}

		const dimension = this._getDimension( texture );
		const format = texture.internalFormat || options.format || getFormat( texture, backend.device );

		textureData.format = format;

		const { samples, primarySamples, isMSAA } = backend.utils.getTextureSampleData( texture );

		let usage = GPUTextureUsage.TEXTURE_BINDING | GPUTextureUsage.COPY_DST | GPUTextureUsage.COPY_SRC;

		if ( texture.isStorageTexture === true ) {

			usage |= GPUTextureUsage.STORAGE_BINDING;

		}

		if ( texture.isCompressedTexture !== true && texture.isCompressedArrayTexture !== true ) {

			usage |= GPUTextureUsage.RENDER_ATTACHMENT;

		}

		const textureDescriptorGPU = {
			label: texture.name,
			size: {
				width: width,
				height: height,
				depthOrArrayLayers: depth,
			},
			mipLevelCount: levels,
			sampleCount: primarySamples,
			dimension: dimension,
			format: format,
			usage: usage
		};

		// texture creation

		if ( format === undefined ) {

			console.warn( 'WebGPURenderer: Texture format not supported.' );

			this.createDefaultTexture( texture );
			return;

		}

		if ( texture.isCubeTexture ) {

			textureDescriptorGPU.textureBindingViewDimension = GPUTextureViewDimension.Cube;

		}

		textureData.texture = backend.device.createTexture( textureDescriptorGPU );

		if ( isMSAA ) {

			const msaaTextureDescriptorGPU = Object.assign( {}, textureDescriptorGPU );

			msaaTextureDescriptorGPU.label = msaaTextureDescriptorGPU.label + '-msaa';
			msaaTextureDescriptorGPU.sampleCount = samples;
			msaaTextureDescriptorGPU.mipLevelCount = 1; // See https://www.w3.org/TR/webgpu/#texture-creation

			textureData.msaaTexture = backend.device.createTexture( msaaTextureDescriptorGPU );

		}

		textureData.initialized = true;

		textureData.textureDescriptorGPU = textureDescriptorGPU;

	}
```
</details>

##### `destroyTexture(texture: Texture): void`

<details><summary>Code</summary>

```ts
destroyTexture( texture ) {

		const backend = this.backend;
		const textureData = backend.get( texture );

		if ( textureData.texture !== undefined ) textureData.texture.destroy();

		if ( textureData.msaaTexture !== undefined ) textureData.msaaTexture.destroy();

		backend.delete( texture );

	}
```
</details>

##### `destroySampler(texture: Texture): void`

<details><summary>Code</summary>

```ts
destroySampler( texture ) {

		const backend = this.backend;
		const textureData = backend.get( texture );

		delete textureData.sampler;

	}
```
</details>

##### `generateMipmaps(texture: Texture): void`

<details><summary>Code</summary>

```ts
generateMipmaps( texture ) {

		const textureData = this.backend.get( texture );

		if ( texture.isCubeTexture ) {

			for ( let i = 0; i < 6; i ++ ) {

				this._generateMipmaps( textureData.texture, textureData.textureDescriptorGPU, i );

			}

		} else {

			const depth = texture.image.depth || 1;

			for ( let i = 0; i < depth; i ++ ) {

				this._generateMipmaps( textureData.texture, textureData.textureDescriptorGPU, i );

			}

		}

	}
```
</details>

##### `getColorBuffer(): GPUTexture`

<details><summary>Code</summary>

```ts
getColorBuffer() {

		if ( this.colorBuffer ) this.colorBuffer.destroy();

		const backend = this.backend;
		const { width, height } = backend.getDrawingBufferSize();

		this.colorBuffer = backend.device.createTexture( {
			label: 'colorBuffer',
			size: {
				width: width,
				height: height,
				depthOrArrayLayers: 1
			},
			sampleCount: backend.utils.getSampleCount( backend.renderer.samples ),
			format: backend.utils.getPreferredCanvasFormat(),
			usage: GPUTextureUsage.RENDER_ATTACHMENT | GPUTextureUsage.COPY_SRC
		} );

		return this.colorBuffer;

	}
```
</details>

##### `getDepthBuffer(depth: boolean, stencil: boolean): GPUTexture`

<details><summary>Code</summary>

```ts
getDepthBuffer( depth = true, stencil = false ) {

		const backend = this.backend;
		const { width, height } = backend.getDrawingBufferSize();

		const depthTexture = this.depthTexture;
		const depthTextureGPU = backend.get( depthTexture ).texture;

		let format, type;

		if ( stencil ) {

			format = DepthStencilFormat;
			type = UnsignedInt248Type;

		} else if ( depth ) {

			format = DepthFormat;
			type = UnsignedIntType;

		}

		if ( depthTextureGPU !== undefined ) {

			if ( depthTexture.image.width === width && depthTexture.image.height === height && depthTexture.format === format && depthTexture.type === type ) {

				return depthTextureGPU;

			}

			this.destroyTexture( depthTexture );

		}

		depthTexture.name = 'depthBuffer';
		depthTexture.format = format;
		depthTexture.type = type;
		depthTexture.image.width = width;
		depthTexture.image.height = height;

		this.createTexture( depthTexture, { width, height } );

		return backend.get( depthTexture ).texture;

	}
```
</details>

##### `updateTexture(texture: Texture, options: any): void`

<details><summary>Code</summary>

```ts
updateTexture( texture, options ) {

		const textureData = this.backend.get( texture );

		const { textureDescriptorGPU } = textureData;

		if ( texture.isRenderTargetTexture || ( textureDescriptorGPU === undefined /* unsupported texture format */ ) )
			return;

		// transfer texture data

		if ( texture.isDataTexture ) {

			this._copyBufferToTexture( options.image, textureData.texture, textureDescriptorGPU, 0, texture.flipY );

		} else if ( texture.isArrayTexture || texture.isDataArrayTexture || texture.isData3DTexture ) {

			for ( let i = 0; i < options.image.depth; i ++ ) {

				this._copyBufferToTexture( options.image, textureData.texture, textureDescriptorGPU, i, texture.flipY, i );

			}

		} else if ( texture.isCompressedTexture || texture.isCompressedArrayTexture ) {

			this._copyCompressedBufferToTexture( texture.mipmaps, textureData.texture, textureDescriptorGPU );

		} else if ( texture.isCubeTexture ) {

			this._copyCubeMapToTexture( options.images, textureData.texture, textureDescriptorGPU, texture.flipY, texture.premultiplyAlpha );

		} else {

			this._copyImageToTexture( options.image, textureData.texture, textureDescriptorGPU, 0, texture.flipY, texture.premultiplyAlpha );

		}

		//

		textureData.version = texture.version;

		if ( texture.onUpdate ) texture.onUpdate( texture );

	}
```
</details>

##### `copyTextureToBuffer(texture: Texture, x: number, y: number, width: number, height: number, faceIndex: number): Promise<TypedArray>`

<details><summary>Code</summary>

```ts
async copyTextureToBuffer( texture, x, y, width, height, faceIndex ) {

		const device = this.backend.device;

		const textureData = this.backend.get( texture );
		const textureGPU = textureData.texture;
		const format = textureData.textureDescriptorGPU.format;
		const bytesPerTexel = this._getBytesPerTexel( format );

		let bytesPerRow = width * bytesPerTexel;
		bytesPerRow = Math.ceil( bytesPerRow / 256 ) * 256; // Align to 256 bytes

		const readBuffer = device.createBuffer(
			{
				size: width * height * bytesPerTexel,
				usage: GPUBufferUsage.COPY_DST | GPUBufferUsage.MAP_READ
			}
		);

		const encoder = device.createCommandEncoder();

		encoder.copyTextureToBuffer(
			{
				texture: textureGPU,
				origin: { x, y, z: faceIndex },
			},
			{
				buffer: readBuffer,
				bytesPerRow: bytesPerRow
			},
			{
				width: width,
				height: height
			}

		);

		const typedArrayType = this._getTypedArrayType( format );

		device.queue.submit( [ encoder.finish() ] );

		await readBuffer.mapAsync( GPUMapMode.READ );

		const buffer = readBuffer.getMappedRange();

		return new typedArrayType( buffer );

	}
```
</details>

##### `_getDefaultTextureGPU(format: string): GPUTexture`

<details><summary>Code</summary>

```ts
_getDefaultTextureGPU( format ) {

		let defaultTexture = this.defaultTexture[ format ];

		if ( defaultTexture === undefined ) {

			const texture = new Texture();
			texture.minFilter = NearestFilter;
			texture.magFilter = NearestFilter;

			this.createTexture( texture, { width: 1, height: 1, format } );

			this.defaultTexture[ format ] = defaultTexture = texture;

		}

		return this.backend.get( defaultTexture ).texture;

	}
```
</details>

##### `_getDefaultCubeTextureGPU(format: string): GPUTexture`

<details><summary>Code</summary>

```ts
_getDefaultCubeTextureGPU( format ) {

		let defaultCubeTexture = this.defaultTexture[ format ];

		if ( defaultCubeTexture === undefined ) {

			const texture = new CubeTexture();
			texture.minFilter = NearestFilter;
			texture.magFilter = NearestFilter;

			this.createTexture( texture, { width: 1, height: 1, depth: 6 } );

			this.defaultCubeTexture[ format ] = defaultCubeTexture = texture;

		}

		return this.backend.get( defaultCubeTexture ).texture;

	}
```
</details>

##### `_copyCubeMapToTexture(images: any[], textureGPU: GPUTexture, textureDescriptorGPU: any, flipY: boolean, premultiplyAlpha: boolean): void`

<details><summary>Code</summary>

```ts
_copyCubeMapToTexture( images, textureGPU, textureDescriptorGPU, flipY, premultiplyAlpha ) {

		for ( let i = 0; i < 6; i ++ ) {

			const image = images[ i ];

			const flipIndex = flipY === true ? _flipMap[ i ] : i;

			if ( image.isDataTexture ) {

				this._copyBufferToTexture( image.image, textureGPU, textureDescriptorGPU, flipIndex, flipY );

			} else {

				this._copyImageToTexture( image, textureGPU, textureDescriptorGPU, flipIndex, flipY, premultiplyAlpha );

			}

		}

	}
```
</details>

##### `_copyImageToTexture(image: HTMLCanvasElement | HTMLImageElement | ImageBitmap, textureGPU: GPUTexture, textureDescriptorGPU: any, originDepth: number, flipY: boolean, premultiplyAlpha: boolean): void`

<details><summary>Code</summary>

```ts
_copyImageToTexture( image, textureGPU, textureDescriptorGPU, originDepth, flipY, premultiplyAlpha ) {

		const device = this.backend.device;

		device.queue.copyExternalImageToTexture(
			{
				source: image,
				flipY: flipY
			}, {
				texture: textureGPU,
				mipLevel: 0,
				origin: { x: 0, y: 0, z: originDepth },
				premultipliedAlpha: premultiplyAlpha
			}, {
				width: textureDescriptorGPU.size.width,
				height: textureDescriptorGPU.size.height,
				depthOrArrayLayers: 1
			}
		);

	}
```
</details>

##### `_getPassUtils(): WebGPUTexturePassUtils`

<details><summary>Code</summary>

```ts
_getPassUtils() {

		let passUtils = this._passUtils;

		if ( passUtils === null ) {

			this._passUtils = passUtils = new WebGPUTexturePassUtils( this.backend.device );

		}

		return passUtils;

	}
```
</details>

##### `_generateMipmaps(textureGPU: GPUTexture, textureDescriptorGPU: any, baseArrayLayer: number): void`

<details><summary>Code</summary>

```ts
_generateMipmaps( textureGPU, textureDescriptorGPU, baseArrayLayer = 0 ) {

		this._getPassUtils().generateMipmaps( textureGPU, textureDescriptorGPU, baseArrayLayer );

	}
```
</details>

##### `_flipY(textureGPU: GPUTexture, textureDescriptorGPU: any, originDepth: number): void`

<details><summary>Code</summary>

```ts
_flipY( textureGPU, textureDescriptorGPU, originDepth = 0 ) {

		this._getPassUtils().flipY( textureGPU, textureDescriptorGPU, originDepth );

	}
```
</details>

##### `_copyBufferToTexture(image: any, textureGPU: GPUTexture, textureDescriptorGPU: any, originDepth: number, flipY: boolean, depth: number): void`

<details><summary>Code</summary>

```ts
_copyBufferToTexture( image, textureGPU, textureDescriptorGPU, originDepth, flipY, depth = 0 ) {

		// @TODO: Consider to use GPUCommandEncoder.copyBufferToTexture()
		// @TODO: Consider to support valid buffer layouts with other formats like RGB

		const device = this.backend.device;

		const data = image.data;

		const bytesPerTexel = this._getBytesPerTexel( textureDescriptorGPU.format );
		const bytesPerRow = image.width * bytesPerTexel;

		device.queue.writeTexture(
			{
				texture: textureGPU,
				mipLevel: 0,
				origin: { x: 0, y: 0, z: originDepth }
			},
			data,
			{
				offset: image.width * image.height * bytesPerTexel * depth,
				bytesPerRow
			},
			{
				width: image.width,
				height: image.height,
				depthOrArrayLayers: 1
			} );

		if ( flipY === true ) {

			this._flipY( textureGPU, textureDescriptorGPU, originDepth );

		}

	}
```
</details>

##### `_copyCompressedBufferToTexture(mipmaps: any[], textureGPU: GPUTexture, textureDescriptorGPU: any): void`

<details><summary>Code</summary>

```ts
_copyCompressedBufferToTexture( mipmaps, textureGPU, textureDescriptorGPU ) {

		// @TODO: Consider to use GPUCommandEncoder.copyBufferToTexture()

		const device = this.backend.device;

		const blockData = this._getBlockData( textureDescriptorGPU.format );
		const isArrayTexture = textureDescriptorGPU.size.depthOrArrayLayers > 1;

		for ( let i = 0; i < mipmaps.length; i ++ ) {

			const mipmap = mipmaps[ i ];

			const width = mipmap.width;
			const height = mipmap.height;
			const depth = isArrayTexture ? textureDescriptorGPU.size.depthOrArrayLayers : 1;

			const bytesPerRow = Math.ceil( width / blockData.width ) * blockData.byteLength;
			const bytesPerImage = bytesPerRow * Math.ceil( height / blockData.height );

			for ( let j = 0; j < depth; j ++ ) {

				device.queue.writeTexture(
					{
						texture: textureGPU,
						mipLevel: i,
						origin: { x: 0, y: 0, z: j }
					},
					mipmap.data,
					{
						offset: j * bytesPerImage,
						bytesPerRow,
						rowsPerImage: Math.ceil( height / blockData.height )
					},
					{
						width: Math.ceil( width / blockData.width ) * blockData.width,
						height: Math.ceil( height / blockData.height ) * blockData.height,
						depthOrArrayLayers: 1
					}
				);

			}

		}

	}
```
</details>

##### `_getBlockData(format: string): any`

<details><summary>Code</summary>

```ts
_getBlockData( format ) {

		if ( format === GPUTextureFormat.BC1RGBAUnorm || format === GPUTextureFormat.BC1RGBAUnormSRGB ) return { byteLength: 8, width: 4, height: 4 }; // DXT1
		if ( format === GPUTextureFormat.BC2RGBAUnorm || format === GPUTextureFormat.BC2RGBAUnormSRGB ) return { byteLength: 16, width: 4, height: 4 }; // DXT3
		if ( format === GPUTextureFormat.BC3RGBAUnorm || format === GPUTextureFormat.BC3RGBAUnormSRGB ) return { byteLength: 16, width: 4, height: 4 }; // DXT5
		if ( format === GPUTextureFormat.BC4RUnorm || format === GPUTextureFormat.BC4RSnorm ) return { byteLength: 8, width: 4, height: 4 }; // RGTC1
		if ( format === GPUTextureFormat.BC5RGUnorm || format === GPUTextureFormat.BC5RGSnorm ) return { byteLength: 16, width: 4, height: 4 }; // RGTC2
		if ( format === GPUTextureFormat.BC6HRGBUFloat || format === GPUTextureFormat.BC6HRGBFloat ) return { byteLength: 16, width: 4, height: 4 }; // BPTC (float)
		if ( format === GPUTextureFormat.BC7RGBAUnorm || format === GPUTextureFormat.BC7RGBAUnormSRGB ) return { byteLength: 16, width: 4, height: 4 }; // BPTC (unorm)

		if ( format === GPUTextureFormat.ETC2RGB8Unorm || format === GPUTextureFormat.ETC2RGB8UnormSRGB ) return { byteLength: 8, width: 4, height: 4 };
		if ( format === GPUTextureFormat.ETC2RGB8A1Unorm || format === GPUTextureFormat.ETC2RGB8A1UnormSRGB ) return { byteLength: 8, width: 4, height: 4 };
		if ( format === GPUTextureFormat.ETC2RGBA8Unorm || format === GPUTextureFormat.ETC2RGBA8UnormSRGB ) return { byteLength: 16, width: 4, height: 4 };
		if ( format === GPUTextureFormat.EACR11Unorm ) return { byteLength: 8, width: 4, height: 4 };
		if ( format === GPUTextureFormat.EACR11Snorm ) return { byteLength: 8, width: 4, height: 4 };
		if ( format === GPUTextureFormat.EACRG11Unorm ) return { byteLength: 16, width: 4, height: 4 };
		if ( format === GPUTextureFormat.EACRG11Snorm ) return { byteLength: 16, width: 4, height: 4 };

		if ( format === GPUTextureFormat.ASTC4x4Unorm || format === GPUTextureFormat.ASTC4x4UnormSRGB ) return { byteLength: 16, width: 4, height: 4 };
		if ( format === GPUTextureFormat.ASTC5x4Unorm || format === GPUTextureFormat.ASTC5x4UnormSRGB ) return { byteLength: 16, width: 5, height: 4 };
		if ( format === GPUTextureFormat.ASTC5x5Unorm || format === GPUTextureFormat.ASTC5x5UnormSRGB ) return { byteLength: 16, width: 5, height: 5 };
		if ( format === GPUTextureFormat.ASTC6x5Unorm || format === GPUTextureFormat.ASTC6x5UnormSRGB ) return { byteLength: 16, width: 6, height: 5 };
		if ( format === GPUTextureFormat.ASTC6x6Unorm || format === GPUTextureFormat.ASTC6x6UnormSRGB ) return { byteLength: 16, width: 6, height: 6 };
		if ( format === GPUTextureFormat.ASTC8x5Unorm || format === GPUTextureFormat.ASTC8x5UnormSRGB ) return { byteLength: 16, width: 8, height: 5 };
		if ( format === GPUTextureFormat.ASTC8x6Unorm || format === GPUTextureFormat.ASTC8x6UnormSRGB ) return { byteLength: 16, width: 8, height: 6 };
		if ( format === GPUTextureFormat.ASTC8x8Unorm || format === GPUTextureFormat.ASTC8x8UnormSRGB ) return { byteLength: 16, width: 8, height: 8 };
		if ( format === GPUTextureFormat.ASTC10x5Unorm || format === GPUTextureFormat.ASTC10x5UnormSRGB ) return { byteLength: 16, width: 10, height: 5 };
		if ( format === GPUTextureFormat.ASTC10x6Unorm || format === GPUTextureFormat.ASTC10x6UnormSRGB ) return { byteLength: 16, width: 10, height: 6 };
		if ( format === GPUTextureFormat.ASTC10x8Unorm || format === GPUTextureFormat.ASTC10x8UnormSRGB ) return { byteLength: 16, width: 10, height: 8 };
		if ( format === GPUTextureFormat.ASTC10x10Unorm || format === GPUTextureFormat.ASTC10x10UnormSRGB ) return { byteLength: 16, width: 10, height: 10 };
		if ( format === GPUTextureFormat.ASTC12x10Unorm || format === GPUTextureFormat.ASTC12x10UnormSRGB ) return { byteLength: 16, width: 12, height: 10 };
		if ( format === GPUTextureFormat.ASTC12x12Unorm || format === GPUTextureFormat.ASTC12x12UnormSRGB ) return { byteLength: 16, width: 12, height: 12 };

	}
```
</details>

##### `_convertAddressMode(value: number): string`

<details><summary>Code</summary>

```ts
_convertAddressMode( value ) {

		let addressMode = GPUAddressMode.ClampToEdge;

		if ( value === RepeatWrapping ) {

			addressMode = GPUAddressMode.Repeat;

		} else if ( value === MirroredRepeatWrapping ) {

			addressMode = GPUAddressMode.MirrorRepeat;

		}

		return addressMode;

	}
```
</details>

##### `_convertFilterMode(value: number): string`

<details><summary>Code</summary>

```ts
_convertFilterMode( value ) {

		let filterMode = GPUFilterMode.Linear;

		if ( value === NearestFilter || value === NearestMipmapNearestFilter || value === NearestMipmapLinearFilter ) {

			filterMode = GPUFilterMode.Nearest;

		}

		return filterMode;

	}
```
</details>

##### `_getBytesPerTexel(format: string): number`

<details><summary>Code</summary>

```ts
_getBytesPerTexel( format ) {

		// 8-bit formats
		if ( format === GPUTextureFormat.R8Unorm ||
			format === GPUTextureFormat.R8Snorm ||
			format === GPUTextureFormat.R8Uint ||
			format === GPUTextureFormat.R8Sint ) return 1;

		// 16-bit formats
		if ( format === GPUTextureFormat.R16Uint ||
			format === GPUTextureFormat.R16Sint ||
			format === GPUTextureFormat.R16Float ||
			format === GPUTextureFormat.RG8Unorm ||
			format === GPUTextureFormat.RG8Snorm ||
			format === GPUTextureFormat.RG8Uint ||
			format === GPUTextureFormat.RG8Sint ) return 2;

		// 32-bit formats
		if ( format === GPUTextureFormat.R32Uint ||
			format === GPUTextureFormat.R32Sint ||
			format === GPUTextureFormat.R32Float ||
			format === GPUTextureFormat.RG16Uint ||
			format === GPUTextureFormat.RG16Sint ||
			format === GPUTextureFormat.RG16Float ||
			format === GPUTextureFormat.RGBA8Unorm ||
			format === GPUTextureFormat.RGBA8UnormSRGB ||
			format === GPUTextureFormat.RGBA8Snorm ||
			format === GPUTextureFormat.RGBA8Uint ||
			format === GPUTextureFormat.RGBA8Sint ||
			format === GPUTextureFormat.BGRA8Unorm ||
			format === GPUTextureFormat.BGRA8UnormSRGB ||
			// Packed 32-bit formats
			format === GPUTextureFormat.RGB9E5UFloat ||
			format === GPUTextureFormat.RGB10A2Unorm ||
			format === GPUTextureFormat.RG11B10UFloat ||
			format === GPUTextureFormat.Depth32Float ||
			format === GPUTextureFormat.Depth24Plus ||
			format === GPUTextureFormat.Depth24PlusStencil8 ||
			format === GPUTextureFormat.Depth32FloatStencil8 ) return 4;

		// 64-bit formats
		if ( format === GPUTextureFormat.RG32Uint ||
			format === GPUTextureFormat.RG32Sint ||
			format === GPUTextureFormat.RG32Float ||
			format === GPUTextureFormat.RGBA16Uint ||
			format === GPUTextureFormat.RGBA16Sint ||
			format === GPUTextureFormat.RGBA16Float ) return 8;

		// 128-bit formats
		if ( format === GPUTextureFormat.RGBA32Uint ||
			format === GPUTextureFormat.RGBA32Sint ||
			format === GPUTextureFormat.RGBA32Float ) return 16;


	}
```
</details>

##### `_getTypedArrayType(format: string): TypedArray.constructor`

<details><summary>Code</summary>

```ts
_getTypedArrayType( format ) {

		if ( format === GPUTextureFormat.R8Uint ) return Uint8Array;
		if ( format === GPUTextureFormat.R8Sint ) return Int8Array;
		if ( format === GPUTextureFormat.R8Unorm ) return Uint8Array;
		if ( format === GPUTextureFormat.R8Snorm ) return Int8Array;
		if ( format === GPUTextureFormat.RG8Uint ) return Uint8Array;
		if ( format === GPUTextureFormat.RG8Sint ) return Int8Array;
		if ( format === GPUTextureFormat.RG8Unorm ) return Uint8Array;
		if ( format === GPUTextureFormat.RG8Snorm ) return Int8Array;
		if ( format === GPUTextureFormat.RGBA8Uint ) return Uint8Array;
		if ( format === GPUTextureFormat.RGBA8Sint ) return Int8Array;
		if ( format === GPUTextureFormat.RGBA8Unorm ) return Uint8Array;
		if ( format === GPUTextureFormat.RGBA8Snorm ) return Int8Array;


		if ( format === GPUTextureFormat.R16Uint ) return Uint16Array;
		if ( format === GPUTextureFormat.R16Sint ) return Int16Array;
		if ( format === GPUTextureFormat.RG16Uint ) return Uint16Array;
		if ( format === GPUTextureFormat.RG16Sint ) return Int16Array;
		if ( format === GPUTextureFormat.RGBA16Uint ) return Uint16Array;
		if ( format === GPUTextureFormat.RGBA16Sint ) return Int16Array;
		if ( format === GPUTextureFormat.R16Float ) return Uint16Array;
		if ( format === GPUTextureFormat.RG16Float ) return Uint16Array;
		if ( format === GPUTextureFormat.RGBA16Float ) return Uint16Array;


		if ( format === GPUTextureFormat.R32Uint ) return Uint32Array;
		if ( format === GPUTextureFormat.R32Sint ) return Int32Array;
		if ( format === GPUTextureFormat.R32Float ) return Float32Array;
		if ( format === GPUTextureFormat.RG32Uint ) return Uint32Array;
		if ( format === GPUTextureFormat.RG32Sint ) return Int32Array;
		if ( format === GPUTextureFormat.RG32Float ) return Float32Array;
		if ( format === GPUTextureFormat.RGBA32Uint ) return Uint32Array;
		if ( format === GPUTextureFormat.RGBA32Sint ) return Int32Array;
		if ( format === GPUTextureFormat.RGBA32Float ) return Float32Array;

		if ( format === GPUTextureFormat.BGRA8Unorm ) return Uint8Array;
		if ( format === GPUTextureFormat.BGRA8UnormSRGB ) return Uint8Array;
		if ( format === GPUTextureFormat.RGB10A2Unorm ) return Uint32Array;
		if ( format === GPUTextureFormat.RGB9E5UFloat ) return Uint32Array;
		if ( format === GPUTextureFormat.RG11B10UFloat ) return Uint32Array;

		if ( format === GPUTextureFormat.Depth32Float ) return Float32Array;
		if ( format === GPUTextureFormat.Depth24Plus ) return Uint32Array;
		if ( format === GPUTextureFormat.Depth24PlusStencil8 ) return Uint32Array;
		if ( format === GPUTextureFormat.Depth32FloatStencil8 ) return Float32Array;

	}
```
</details>

##### `_getDimension(texture: Texture): string`

<details><summary>Code</summary>

```ts
_getDimension( texture ) {

		let dimension;

		if ( texture.is3DTexture || texture.isData3DTexture ) {

			dimension = GPUTextureDimension.ThreeD;

		} else {

			dimension = GPUTextureDimension.TwoD;

		}

		return dimension;

	}
```
</details>


---