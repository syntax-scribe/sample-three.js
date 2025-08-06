[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `WebGLTextureUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 18 |
| 🧱 Classes | 1 |
| 📦 Imports | 22 |
| 📊 Variables & Constants | 49 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgl-fallback/utils/WebGLTextureUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LinearFilter` | `../../../constants.js` |
| `LinearMipmapLinearFilter` | `../../../constants.js` |
| `LinearMipmapNearestFilter` | `../../../constants.js` |
| `NearestFilter` | `../../../constants.js` |
| `NearestMipmapLinearFilter` | `../../../constants.js` |
| `NearestMipmapNearestFilter` | `../../../constants.js` |
| `FloatType` | `../../../constants.js` |
| `MirroredRepeatWrapping` | `../../../constants.js` |
| `ClampToEdgeWrapping` | `../../../constants.js` |
| `RepeatWrapping` | `../../../constants.js` |
| `NeverCompare` | `../../../constants.js` |
| `AlwaysCompare` | `../../../constants.js` |
| `LessCompare` | `../../../constants.js` |
| `LessEqualCompare` | `../../../constants.js` |
| `EqualCompare` | `../../../constants.js` |
| `GreaterEqualCompare` | `../../../constants.js` |
| `GreaterCompare` | `../../../constants.js` |
| `NotEqualCompare` | `../../../constants.js` |
| `NoColorSpace` | `../../../constants.js` |
| `LinearTransfer` | `../../../constants.js` |
| `SRGBTransfer` | `../../../constants.js` |
| `ColorManagement` | `../../../math/ColorManagement.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `initialized` | `boolean` | let/var | `false` | ✗ |
| `wrappingToGL` | `any` | let/var | `*not shown*` | ✗ |
| `filterToGL` | `any` | let/var | `*not shown*` | ✗ |
| `compareToGL` | `any` | let/var | `*not shown*` | ✗ |
| `gl` | `WebGL2RenderingContext` | let/var | `this.gl` | ✗ |
| `glTextureType` | `any` | let/var | `*not shown*` | ✗ |
| `internalFormat` | `number` | let/var | `glFormat` | ✗ |
| `transfer` | `any` | let/var | `forceLinearTransfer ? LinearTransfer : ColorManagement.getTransfer( colorSpace )` | ✗ |
| `transfer` | `any` | let/var | `forceLinearTransfer ? LinearTransfer : ColorManagement.getTransfer( colorSpace )` | ✗ |
| `texturePrimaries` | `any` | let/var | `texture.colorSpace === NoColorSpace ? null : ColorManagement.getPrimaries( te...` | ✗ |
| `unpackConversion` | `0 \| 37444` | let/var | `texture.colorSpace === NoColorSpace \|\| workingPrimaries === texturePrimarie...` | ✗ |
| `hasMipmaps` | `boolean` | let/var | `texture.mipmaps !== undefined && texture.mipmaps.length > 0` | ✗ |
| `minFilter` | `any` | let/var | `texture.minFilter === LinearFilter && hasMipmaps ? LinearMipmapLinearFilter :...` | ✗ |
| `textureGPU` | `any` | let/var | `defaultTextures[ glTextureType ]` | ✗ |
| `mipmaps` | `any` | let/var | `texture.mipmaps` | ✗ |
| `image` | `any` | let/var | `options.image` | ✗ |
| `mipmap` | `any` | let/var | `mipmaps[ i ]` | ✗ |
| `images` | `any` | let/var | `options.images` | ✗ |
| `image` | `any` | let/var | `options.image` | ✗ |
| `image` | `any` | let/var | `options.image` | ✗ |
| `width` | `any` | let/var | `*not shown*` | ✗ |
| `height` | `any` | let/var | `*not shown*` | ✗ |
| `depth` | `any` | let/var | `*not shown*` | ✗ |
| `minX` | `any` | let/var | `*not shown*` | ✗ |
| `minY` | `any` | let/var | `*not shown*` | ✗ |
| `minZ` | `any` | let/var | `*not shown*` | ✗ |
| `dstX` | `any` | let/var | `*not shown*` | ✗ |
| `dstY` | `any` | let/var | `*not shown*` | ✗ |
| `dstZ` | `any` | let/var | `*not shown*` | ✗ |
| `image` | `any` | let/var | `srcTexture.isCompressedTexture ? srcTexture.mipmaps[ dstLevel ] : srcTexture....` | ✗ |
| `isDst3D` | `any` | let/var | `dstTexture.isDataArrayTexture \|\| dstTexture.isData3DTexture \|\| dstTexture...` | ✗ |
| `srcFramebuffer` | `any` | let/var | `srcRenderContextData.framebuffers[ srcTextureData.cacheKey ]` | ✗ |
| `dstFramebuffer` | `any` | let/var | `dstRenderContextData.framebuffers[ dstTextureData.cacheKey ]` | ✗ |
| `mask` | `16384` | let/var | `gl.COLOR_BUFFER_BIT` | ✗ |
| `requireDrawFrameBuffer` | `boolean` | let/var | `texture.isDepthTexture === true \|\| ( renderContext.renderTarget && renderCo...` | ✗ |
| `srcHeight` | `any` | let/var | `renderContext.renderTarget ? renderContext.renderTarget.height : this.backend...` | ✗ |
| `partial` | `boolean` | let/var | `( x !== 0 \|\| y !== 0 )` | ✗ |
| `mask` | `any` | let/var | `*not shown*` | ✗ |
| `attachment` | `any` | let/var | `*not shown*` | ✗ |
| `fb` | `any` | let/var | `renderTargetContextData.framebuffers[ renderContext.getCacheKey() ]` | ✗ |
| `msaaFrameBuffer` | `any` | let/var | `renderTargetContextData.msaaFrameBuffer` | ✗ |
| `flippedY` | `number` | let/var | `srcHeight - y - height` | ✗ |
| `renderTarget` | `any` | let/var | `renderContext.renderTarget` | ✗ |
| `glInternalFormat` | `33190` | let/var | `gl.DEPTH_COMPONENT24` | ✗ |
| `target` | `number` | let/var | `texture.isCubeTexture ? gl.TEXTURE_CUBE_MAP_POSITIVE_X + faceIndex : gl.TEXTU...` | ✗ |
| `elementCount` | `number` | let/var | `width * height` | ✗ |
| `byteLength` | `number` | let/var | `elementCount * bytesPerTexel` | ✗ |
| `dstBuffer` | `any` | let/var | `new typedArrayType( byteLength / typedArrayType.BYTES_PER_ELEMENT )` | ✗ |
| `bytesPerComponent` | `number` | let/var | `0` | ✗ |


---

## Functions

### `WebGLTextureUtils._init(): void`

**JSDoc:**
```typescript
/**
	 * Inits the state of the utility.
	 *
	 * @private
	 */
```

**Returns:** `void`

**Internal Comments:**
```
// Store only WebGL constants here. (x3)
```

<details><summary>Code</summary>

```typescript
_init() {

		const gl = this.gl;

		// Store only WebGL constants here.

		wrappingToGL = {
			[ RepeatWrapping ]: gl.REPEAT,
			[ ClampToEdgeWrapping ]: gl.CLAMP_TO_EDGE,
			[ MirroredRepeatWrapping ]: gl.MIRRORED_REPEAT
		};

		filterToGL = {
			[ NearestFilter ]: gl.NEAREST,
			[ NearestMipmapNearestFilter ]: gl.NEAREST_MIPMAP_NEAREST,
			[ NearestMipmapLinearFilter ]: gl.NEAREST_MIPMAP_LINEAR,

			[ LinearFilter ]: gl.LINEAR,
			[ LinearMipmapNearestFilter ]: gl.LINEAR_MIPMAP_NEAREST,
			[ LinearMipmapLinearFilter ]: gl.LINEAR_MIPMAP_LINEAR
		};

		compareToGL = {
			[ NeverCompare ]: gl.NEVER,
			[ AlwaysCompare ]: gl.ALWAYS,
			[ LessCompare ]: gl.LESS,
			[ LessEqualCompare ]: gl.LEQUAL,
			[ EqualCompare ]: gl.EQUAL,
			[ GreaterEqualCompare ]: gl.GEQUAL,
			[ GreaterCompare ]: gl.GREATER,
			[ NotEqualCompare ]: gl.NOTEQUAL
		};

	}
```
</details>

### `WebGLTextureUtils.getGLTextureType(texture: Texture): number`

**JSDoc:**
```typescript
/**
	 * Returns the native texture type for the given texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @return {GLenum} The native texture type.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getGLTextureType( texture ) {

		const { gl } = this;

		let glTextureType;

		if ( texture.isCubeTexture === true ) {

			glTextureType = gl.TEXTURE_CUBE_MAP;

		} else if ( texture.isArrayTexture === true || texture.isDataArrayTexture === true || texture.isCompressedArrayTexture === true ) {

			glTextureType = gl.TEXTURE_2D_ARRAY;

		} else if ( texture.isData3DTexture === true ) { // TODO: isCompressed3DTexture, wait for #26642

			glTextureType = gl.TEXTURE_3D;

		} else {

			glTextureType = gl.TEXTURE_2D;


		}

		return glTextureType;

	}
```
</details>

### `WebGLTextureUtils.getInternalFormat(internalFormatName: string, glFormat: number, glType: number, colorSpace: string, forceLinearTransfer: boolean): number`

**JSDoc:**
```typescript
/**
	 * Returns the native texture type for the given texture.
	 *
	 * @param {?string} internalFormatName - The internal format name. When `null`, the internal format is derived from the subsequent parameters.
	 * @param {GLenum} glFormat - The WebGL format.
	 * @param {GLenum} glType - The WebGL type.
	 * @param {string} colorSpace - The texture's color space.
	 * @param {boolean} [forceLinearTransfer=false] - Whether to force a linear transfer or not.
	 * @return {GLenum} The internal format.
	 */
```

**Parameters:**

- **`internalFormatName`** `string`
- **`glFormat`** `number`
- **`glType`** `number`
- **`colorSpace`** `string`
- **`forceLinearTransfer`** `boolean`

**Returns:** `number`

**Calls:**

- `console.warn`
- `ColorManagement.getTransfer`
- `extensions.get`

<details><summary>Code</summary>

```typescript
getInternalFormat( internalFormatName, glFormat, glType, colorSpace, forceLinearTransfer = false ) {

		const { gl, extensions } = this;

		if ( internalFormatName !== null ) {

			if ( gl[ internalFormatName ] !== undefined ) return gl[ internalFormatName ];

			console.warn( 'THREE.WebGLRenderer: Attempt to use non-existing WebGL internal format \'' + internalFormatName + '\'' );

		}

		let internalFormat = glFormat;

		if ( glFormat === gl.RED ) {

			if ( glType === gl.FLOAT ) internalFormat = gl.R32F;
			if ( glType === gl.HALF_FLOAT ) internalFormat = gl.R16F;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.R8;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.R16;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.R32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.R8I;
			if ( glType === gl.SHORT ) internalFormat = gl.R16I;
			if ( glType === gl.INT ) internalFormat = gl.R32I;

		}

		if ( glFormat === gl.RED_INTEGER ) {

			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.R8UI;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.R16UI;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.R32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.R8I;
			if ( glType === gl.SHORT ) internalFormat = gl.R16I;
			if ( glType === gl.INT ) internalFormat = gl.R32I;

		}

		if ( glFormat === gl.RG ) {

			if ( glType === gl.FLOAT ) internalFormat = gl.RG32F;
			if ( glType === gl.HALF_FLOAT ) internalFormat = gl.RG16F;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RG8;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RG16;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RG32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RG8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RG16I;
			if ( glType === gl.INT ) internalFormat = gl.RG32I;

		}

		if ( glFormat === gl.RG_INTEGER ) {

			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RG8UI;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RG16UI;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RG32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RG8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RG16I;
			if ( glType === gl.INT ) internalFormat = gl.RG32I;

		}

		if ( glFormat === gl.RGB ) {

			const transfer = forceLinearTransfer ? LinearTransfer : ColorManagement.getTransfer( colorSpace );

			if ( glType === gl.FLOAT ) internalFormat = gl.RGB32F;
			if ( glType === gl.HALF_FLOAT ) internalFormat = gl.RGB16F;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RGB8;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RGB16;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RGB32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RGB8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RGB16I;
			if ( glType === gl.INT ) internalFormat = gl.RGB32I;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = ( transfer === SRGBTransfer ) ? gl.SRGB8 : gl.RGB8;
			if ( glType === gl.UNSIGNED_SHORT_5_6_5 ) internalFormat = gl.RGB565;
			if ( glType === gl.UNSIGNED_SHORT_5_5_5_1 ) internalFormat = gl.RGB5_A1;
			if ( glType === gl.UNSIGNED_SHORT_4_4_4_4 ) internalFormat = gl.RGB4;
			if ( glType === gl.UNSIGNED_INT_5_9_9_9_REV ) internalFormat = gl.RGB9_E5;

		}

		if ( glFormat === gl.RGB_INTEGER ) {

			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RGB8UI;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RGB16UI;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RGB32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RGB8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RGB16I;
			if ( glType === gl.INT ) internalFormat = gl.RGB32I;

		}

		if ( glFormat === gl.RGBA ) {

			const transfer = forceLinearTransfer ? LinearTransfer : ColorManagement.getTransfer( colorSpace );

			if ( glType === gl.FLOAT ) internalFormat = gl.RGBA32F;
			if ( glType === gl.HALF_FLOAT ) internalFormat = gl.RGBA16F;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RGBA8;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RGBA16;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RGBA32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RGBA8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RGBA16I;
			if ( glType === gl.INT ) internalFormat = gl.RGBA32I;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = ( transfer === SRGBTransfer ) ? gl.SRGB8_ALPHA8 : gl.RGBA8;
			if ( glType === gl.UNSIGNED_SHORT_4_4_4_4 ) internalFormat = gl.RGBA4;
			if ( glType === gl.UNSIGNED_SHORT_5_5_5_1 ) internalFormat = gl.RGB5_A1;

		}

		if ( glFormat === gl.RGBA_INTEGER ) {

			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RGBA8UI;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RGBA16UI;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RGBA32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RGBA8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RGBA16I;
			if ( glType === gl.INT ) internalFormat = gl.RGBA32I;

		}

		if ( glFormat === gl.DEPTH_COMPONENT ) {

			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.DEPTH_COMPONENT16;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.DEPTH_COMPONENT24;
			if ( glType === gl.FLOAT ) internalFormat = gl.DEPTH_COMPONENT32F;

		}

		if ( glFormat === gl.DEPTH_STENCIL ) {

			if ( glType === gl.UNSIGNED_INT_24_8 ) internalFormat = gl.DEPTH24_STENCIL8;

		}

		if ( internalFormat === gl.R16F || internalFormat === gl.R32F ||
			internalFormat === gl.RG16F || internalFormat === gl.RG32F ||
			internalFormat === gl.RGBA16F || internalFormat === gl.RGBA32F ) {

			extensions.get( 'EXT_color_buffer_float' );

		}

		return internalFormat;

	}
```
</details>

### `WebGLTextureUtils.setTextureParameters(textureType: number, texture: Texture): void`

**JSDoc:**
```typescript
/**
	 * Sets the texture parameters for the given texture.
	 *
	 * @param {GLenum} textureType - The texture type.
	 * @param {Texture} texture - The texture.
	 */
```

**Parameters:**

- **`textureType`** `number`
- **`texture`** `Texture`

**Returns:** `void`

**Calls:**

- `ColorManagement.getPrimaries`
- `gl.pixelStorei`
- `gl.texParameteri`
- `extensions.has`
- `extensions.get`
- `gl.texParameterf`
- `Math.min`
- `backend.getMaxAnisotropy`

**Internal Comments:**
```
// WebGL 2 does not support wrapping for depth 2D array textures
// follow WebGPU backend mapping for texture filtering (x2)
```

<details><summary>Code</summary>

```typescript
setTextureParameters( textureType, texture ) {

		const { gl, extensions, backend } = this;

		const workingPrimaries = ColorManagement.getPrimaries( ColorManagement.workingColorSpace );
		const texturePrimaries = texture.colorSpace === NoColorSpace ? null : ColorManagement.getPrimaries( texture.colorSpace );
		const unpackConversion = texture.colorSpace === NoColorSpace || workingPrimaries === texturePrimaries ? gl.NONE : gl.BROWSER_DEFAULT_WEBGL;

		gl.pixelStorei( gl.UNPACK_FLIP_Y_WEBGL, texture.flipY );
		gl.pixelStorei( gl.UNPACK_PREMULTIPLY_ALPHA_WEBGL, texture.premultiplyAlpha );
		gl.pixelStorei( gl.UNPACK_ALIGNMENT, texture.unpackAlignment );
		gl.pixelStorei( gl.UNPACK_COLORSPACE_CONVERSION_WEBGL, unpackConversion );

		gl.texParameteri( textureType, gl.TEXTURE_WRAP_S, wrappingToGL[ texture.wrapS ] );
		gl.texParameteri( textureType, gl.TEXTURE_WRAP_T, wrappingToGL[ texture.wrapT ] );

		if ( textureType === gl.TEXTURE_3D || textureType === gl.TEXTURE_2D_ARRAY ) {

			// WebGL 2 does not support wrapping for depth 2D array textures
			if ( ! texture.isArrayTexture ) {

				gl.texParameteri( textureType, gl.TEXTURE_WRAP_R, wrappingToGL[ texture.wrapR ] );

			}

		}

		gl.texParameteri( textureType, gl.TEXTURE_MAG_FILTER, filterToGL[ texture.magFilter ] );


		const hasMipmaps = texture.mipmaps !== undefined && texture.mipmaps.length > 0;

		// follow WebGPU backend mapping for texture filtering
		const minFilter = texture.minFilter === LinearFilter && hasMipmaps ? LinearMipmapLinearFilter : texture.minFilter;

		gl.texParameteri( textureType, gl.TEXTURE_MIN_FILTER, filterToGL[ minFilter ] );

		if ( texture.compareFunction ) {

			gl.texParameteri( textureType, gl.TEXTURE_COMPARE_MODE, gl.COMPARE_REF_TO_TEXTURE );
			gl.texParameteri( textureType, gl.TEXTURE_COMPARE_FUNC, compareToGL[ texture.compareFunction ] );

		}

		if ( extensions.has( 'EXT_texture_filter_anisotropic' ) === true ) {

			if ( texture.magFilter === NearestFilter ) return;
			if ( texture.minFilter !== NearestMipmapLinearFilter && texture.minFilter !== LinearMipmapLinearFilter ) return;
			if ( texture.type === FloatType && extensions.has( 'OES_texture_float_linear' ) === false ) return; // verify extension for WebGL 1 and WebGL 2

			if ( texture.anisotropy > 1 ) {

				const extension = extensions.get( 'EXT_texture_filter_anisotropic' );
				gl.texParameterf( textureType, extension.TEXTURE_MAX_ANISOTROPY_EXT, Math.min( texture.anisotropy, backend.getMaxAnisotropy() ) );

			}

		}

	}
```
</details>

### `WebGLTextureUtils.createDefaultTexture(texture: Texture): void`

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

- `this.getGLTextureType`
- `gl.createTexture`
- `backend.state.bindTexture`
- `gl.texParameteri`
- `backend.set`

**Internal Comments:**
```
// gl.texImage2D( glTextureType, 0, gl.RGBA, 1, 1, 0, gl.RGBA, gl.UNSIGNED_BYTE, data ); (x4)
```

<details><summary>Code</summary>

```typescript
createDefaultTexture( texture ) {

		const { gl, backend, defaultTextures } = this;


		const glTextureType = this.getGLTextureType( texture );

		let textureGPU = defaultTextures[ glTextureType ];

		if ( textureGPU === undefined ) {

			textureGPU = gl.createTexture();

			backend.state.bindTexture( glTextureType, textureGPU );
			gl.texParameteri( glTextureType, gl.TEXTURE_MIN_FILTER, gl.NEAREST );
			gl.texParameteri( glTextureType, gl.TEXTURE_MAG_FILTER, gl.NEAREST );

			// gl.texImage2D( glTextureType, 0, gl.RGBA, 1, 1, 0, gl.RGBA, gl.UNSIGNED_BYTE, data );

			defaultTextures[ glTextureType ] = textureGPU;

		}

		backend.set( texture, {
			textureGPU,
			glTextureType,
			isDefault: true
		} );

	}
```
</details>

### `WebGLTextureUtils.createTexture(texture: Texture, options: any): undefined`

**JSDoc:**
```typescript
/**
	 * Defines a texture on the GPU for the given texture object.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {Object} [options={}] - Optional configuration parameter.
	 * @return {undefined}
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`options`** `any`

**Returns:** `undefined`

**Calls:**

- `backend.utils.convert`
- `this.getInternalFormat`
- `gl.createTexture`
- `this.getGLTextureType`
- `backend.state.bindTexture`
- `this.setTextureParameters`
- `gl.texStorage3D`
- `gl.texStorage2D`
- `backend.set`

<details><summary>Code</summary>

```typescript
createTexture( texture, options ) {

		const { gl, backend } = this;
		const { levels, width, height, depth } = options;

		const glFormat = backend.utils.convert( texture.format, texture.colorSpace );
		const glType = backend.utils.convert( texture.type );
		const glInternalFormat = this.getInternalFormat( texture.internalFormat, glFormat, glType, texture.colorSpace, texture.isVideoTexture );

		const textureGPU = gl.createTexture();
		const glTextureType = this.getGLTextureType( texture );

		backend.state.bindTexture( glTextureType, textureGPU );

		this.setTextureParameters( glTextureType, texture );

		if ( texture.isArrayTexture || texture.isDataArrayTexture || texture.isCompressedArrayTexture ) {

			gl.texStorage3D( gl.TEXTURE_2D_ARRAY, levels, glInternalFormat, width, height, depth );

		} else if ( texture.isData3DTexture ) {

			gl.texStorage3D( gl.TEXTURE_3D, levels, glInternalFormat, width, height, depth );

		} else if ( ! texture.isVideoTexture ) {

			gl.texStorage2D( glTextureType, levels, glInternalFormat, width, height );

		}

		backend.set( texture, {
			textureGPU,
			glTextureType,
			glFormat,
			glType,
			glInternalFormat
		} );

	}
```
</details>

### `WebGLTextureUtils.copyBufferToTexture(buffer: WebGLBuffer, texture: Texture): void`

**JSDoc:**
```typescript
/**
	 * Uploads texture buffer data to the GPU memory.
	 *
	 * @param {WebGLBuffer} buffer - The buffer data.
	 * @param {Texture} texture - The texture,
	 */
```

**Parameters:**

- **`buffer`** `WebGLBuffer`
- **`texture`** `Texture`

**Returns:** `void`

**Calls:**

- `backend.get`
- `gl.bindBuffer`
- `backend.state.bindTexture`
- `gl.pixelStorei`
- `gl.texSubImage2D`
- `backend.state.unbindTexture`

<details><summary>Code</summary>

```typescript
copyBufferToTexture( buffer, texture ) {

		const { gl, backend } = this;

		const { textureGPU, glTextureType, glFormat, glType } = backend.get( texture );

		const { width, height } = texture.source.data;

		gl.bindBuffer( gl.PIXEL_UNPACK_BUFFER, buffer );

		backend.state.bindTexture( glTextureType, textureGPU );

		gl.pixelStorei( gl.UNPACK_FLIP_Y_WEBGL, false );
		gl.pixelStorei( gl.UNPACK_PREMULTIPLY_ALPHA_WEBGL, false );
		gl.texSubImage2D( glTextureType, 0, 0, 0, width, height, glFormat, glType, 0 );

		gl.bindBuffer( gl.PIXEL_UNPACK_BUFFER, null );

		backend.state.unbindTexture();
		// debug
		// const framebuffer = gl.createFramebuffer();
		// gl.bindFramebuffer( gl.FRAMEBUFFER, framebuffer );
		// gl.framebufferTexture2D( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0, glTextureType, textureGPU, 0 );

		// const readout = new Float32Array( width * height * 4 );

		// const altFormat = gl.getParameter( gl.IMPLEMENTATION_COLOR_READ_FORMAT );
		// const altType = gl.getParameter( gl.IMPLEMENTATION_COLOR_READ_TYPE );

		// gl.readPixels( 0, 0, width, height, altFormat, altType, readout );
		// gl.bindFramebuffer( gl.FRAMEBUFFER, null );
		// console.log( readout );

	}
```
</details>

### `WebGLTextureUtils.updateTexture(texture: Texture, options: any): void`

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
- `this.backend.state.bindTexture`
- `this.setTextureParameters`
- `gl.compressedTexSubImage3D`
- `console.warn`
- `gl.texSubImage3D`
- `gl.compressedTexSubImage2D`
- `getImage`
- `gl.texSubImage2D`
- `texture.update`
- `gl.texImage2D`

<details><summary>Code</summary>

```typescript
updateTexture( texture, options ) {

		const { gl } = this;
		const { width, height } = options;
		const { textureGPU, glTextureType, glFormat, glType, glInternalFormat } = this.backend.get( texture );

		if ( texture.isRenderTargetTexture || ( textureGPU === undefined /* unsupported texture format */ ) )
			return;

		this.backend.state.bindTexture( glTextureType, textureGPU );

		this.setTextureParameters( glTextureType, texture );

		if ( texture.isCompressedTexture ) {

			const mipmaps = texture.mipmaps;
			const image = options.image;

			for ( let i = 0; i < mipmaps.length; i ++ ) {

				const mipmap = mipmaps[ i ];

				if ( texture.isCompressedArrayTexture ) {


					if ( texture.format !== gl.RGBA ) {

						if ( glFormat !== null ) {

							gl.compressedTexSubImage3D( gl.TEXTURE_2D_ARRAY, i, 0, 0, 0, mipmap.width, mipmap.height, image.depth, glFormat, mipmap.data );

						} else {

							console.warn( 'THREE.WebGLRenderer: Attempt to load unsupported compressed texture format in .uploadTexture()' );

						}

					} else {

						gl.texSubImage3D( gl.TEXTURE_2D_ARRAY, i, 0, 0, 0, mipmap.width, mipmap.height, image.depth, glFormat, glType, mipmap.data );

					}

				} else {

					if ( glFormat !== null ) {

						gl.compressedTexSubImage2D( gl.TEXTURE_2D, i, 0, 0, mipmap.width, mipmap.height, glFormat, mipmap.data );

					} else {

						console.warn( 'Unsupported compressed texture format' );

					}

				}

			}


		} else if ( texture.isCubeTexture ) {

			const images = options.images;

			for ( let i = 0; i < 6; i ++ ) {

				const image = getImage( images[ i ] );

				gl.texSubImage2D( gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, 0, 0, 0, width, height, glFormat, glType, image );

			}

		} else if ( texture.isDataArrayTexture || texture.isArrayTexture ) {

			const image = options.image;

			gl.texSubImage3D( gl.TEXTURE_2D_ARRAY, 0, 0, 0, 0, image.width, image.height, image.depth, glFormat, glType, image.data );

		} else if ( texture.isData3DTexture ) {

			const image = options.image;

			gl.texSubImage3D( gl.TEXTURE_3D, 0, 0, 0, 0, image.width, image.height, image.depth, glFormat, glType, image.data );

		} else if ( texture.isVideoTexture ) {

			texture.update();

			gl.texImage2D( glTextureType, 0, glInternalFormat, glFormat, glType, options.image );


		} else {

			const image = getImage( options.image );

			gl.texSubImage2D( glTextureType, 0, 0, 0, width, height, glFormat, glType, image );

		}

	}
```
</details>

### `WebGLTextureUtils.generateMipmaps(texture: Texture): void`

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

- `backend.get`
- `backend.state.bindTexture`
- `gl.generateMipmap`

<details><summary>Code</summary>

```typescript
generateMipmaps( texture ) {

		const { gl, backend } = this;
		const { textureGPU, glTextureType } = backend.get( texture );

		backend.state.bindTexture( glTextureType, textureGPU );
		gl.generateMipmap( glTextureType );

	}
```
</details>

### `WebGLTextureUtils.deallocateRenderBuffers(renderTarget: RenderTarget): void`

**JSDoc:**
```typescript
/**
	 * Deallocates the render buffers of the given render target.
	 *
	 * @param {RenderTarget} renderTarget - The render target.
	 */
```

**Parameters:**

- **`renderTarget`** `RenderTarget`

**Returns:** `void`

**Calls:**

- `backend.get`
- `gl.deleteFramebuffer`
- `gl.deleteRenderbuffer`

**Internal Comments:**
```
// remove framebuffer reference
```

<details><summary>Code</summary>

```typescript
deallocateRenderBuffers( renderTarget ) {

		const { gl, backend } = this;

		// remove framebuffer reference
		if ( renderTarget ) {

			const renderContextData = backend.get( renderTarget );

			renderContextData.renderBufferStorageSetup = undefined;

			if ( renderContextData.framebuffers ) {

				for ( const cacheKey in renderContextData.framebuffers ) {

					gl.deleteFramebuffer( renderContextData.framebuffers[ cacheKey ] );

				}

				delete renderContextData.framebuffers;

			}

			if ( renderContextData.depthRenderbuffer ) {

				gl.deleteRenderbuffer( renderContextData.depthRenderbuffer );
				delete renderContextData.depthRenderbuffer;

			}

			if ( renderContextData.stencilRenderbuffer ) {

				gl.deleteRenderbuffer( renderContextData.stencilRenderbuffer );
				delete renderContextData.stencilRenderbuffer;

			}

			if ( renderContextData.msaaFrameBuffer ) {

				gl.deleteFramebuffer( renderContextData.msaaFrameBuffer );
				delete renderContextData.msaaFrameBuffer;

			}

			if ( renderContextData.msaaRenderbuffers ) {

				for ( let i = 0; i < renderContextData.msaaRenderbuffers.length; i ++ ) {

					gl.deleteRenderbuffer( renderContextData.msaaRenderbuffers[ i ] );

				}

				delete renderContextData.msaaRenderbuffers;

			}

		}

	}
```
</details>

### `WebGLTextureUtils.destroyTexture(texture: Texture): void`

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
- `this.deallocateRenderBuffers`
- `gl.deleteTexture`
- `backend.delete`

<details><summary>Code</summary>

```typescript
destroyTexture( texture ) {

		const { gl, backend } = this;
		const { textureGPU, renderTarget } = backend.get( texture );

		this.deallocateRenderBuffers( renderTarget );
		gl.deleteTexture( textureGPU );

		backend.delete( texture );

	}
```
</details>

### `WebGLTextureUtils.copyTextureToTexture(srcTexture: Texture, dstTexture: Texture, srcRegion: any, dstPosition: any, srcLevel: number, dstLevel: number): void`

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

- `backend.get`
- `state.bindTexture`
- `Math.pow`
- `Math.floor`
- `gl.pixelStorei`
- `gl.getParameter`
- `state.bindFramebuffer`
- `gl.blitFramebuffer`
- `gl.texSubImage3D`
- `gl.compressedTexSubImage3D`
- `gl.texSubImage2D`
- `gl.compressedTexSubImage2D`
- `gl.generateMipmap`
- `state.unbindTexture`

**Internal Comments:**
```
// gather the necessary dimensions to copy (x2)
// used for copying data from cpu (x2)
// set up the src texture (x2)
// copy data into the 3d texture
// copy data into the 2d texture
// reset values (x4)
// Generate mipmaps only when copying level 0
```

<details><summary>Code</summary>

```typescript
copyTextureToTexture( srcTexture, dstTexture, srcRegion = null, dstPosition = null, srcLevel = 0, dstLevel = 0 ) {

		const { gl, backend } = this;
		const { state } = this.backend;

		const { textureGPU: dstTextureGPU, glTextureType, glType, glFormat } = backend.get( dstTexture );

		state.bindTexture( glTextureType, dstTextureGPU );

		// gather the necessary dimensions to copy
		let width, height, depth, minX, minY, minZ;
		let dstX, dstY, dstZ;
		const image = srcTexture.isCompressedTexture ? srcTexture.mipmaps[ dstLevel ] : srcTexture.image;

		if ( srcRegion !== null ) {

			width = srcRegion.max.x - srcRegion.min.x;
			height = srcRegion.max.y - srcRegion.min.y;
			depth = srcRegion.isBox3 ? srcRegion.max.z - srcRegion.min.z : 1;
			minX = srcRegion.min.x;
			minY = srcRegion.min.y;
			minZ = srcRegion.isBox3 ? srcRegion.min.z : 0;

		} else {

			const levelScale = Math.pow( 2, - srcLevel );
			width = Math.floor( image.width * levelScale );
			height = Math.floor( image.height * levelScale );

			if ( srcTexture.isDataArrayTexture || srcTexture.isArrayTexture ) {

				depth = image.depth;

			} else if ( srcTexture.isData3DTexture ) {

				depth = Math.floor( image.depth * levelScale );

			} else {

				depth = 1;

			}

			minX = 0;
			minY = 0;
			minZ = 0;

		}

		if ( dstPosition !== null ) {

			dstX = dstPosition.x;
			dstY = dstPosition.y;
			dstZ = dstPosition.z;

		} else {

			dstX = 0;
			dstY = 0;
			dstZ = 0;

		}


		gl.pixelStorei( gl.UNPACK_FLIP_Y_WEBGL, dstTexture.flipY );
		gl.pixelStorei( gl.UNPACK_PREMULTIPLY_ALPHA_WEBGL, dstTexture.premultiplyAlpha );
		gl.pixelStorei( gl.UNPACK_ALIGNMENT, dstTexture.unpackAlignment );

		// used for copying data from cpu
		const currentUnpackRowLen = gl.getParameter( gl.UNPACK_ROW_LENGTH );
		const currentUnpackImageHeight = gl.getParameter( gl.UNPACK_IMAGE_HEIGHT );
		const currentUnpackSkipPixels = gl.getParameter( gl.UNPACK_SKIP_PIXELS );
		const currentUnpackSkipRows = gl.getParameter( gl.UNPACK_SKIP_ROWS );
		const currentUnpackSkipImages = gl.getParameter( gl.UNPACK_SKIP_IMAGES );

		gl.pixelStorei( gl.UNPACK_ROW_LENGTH, image.width );
		gl.pixelStorei( gl.UNPACK_IMAGE_HEIGHT, image.height );
		gl.pixelStorei( gl.UNPACK_SKIP_PIXELS, minX );
		gl.pixelStorei( gl.UNPACK_SKIP_ROWS, minY );
		gl.pixelStorei( gl.UNPACK_SKIP_IMAGES, minZ );

		// set up the src texture
		const isDst3D = dstTexture.isDataArrayTexture || dstTexture.isData3DTexture || dstTexture.isArrayTexture;
		if ( srcTexture.isRenderTargetTexture || srcTexture.isDepthTexture ) {

			const srcTextureData = backend.get( srcTexture );
			const dstTextureData = backend.get( dstTexture );

			const srcRenderContextData = backend.get( srcTextureData.renderTarget );
			const dstRenderContextData = backend.get( dstTextureData.renderTarget );

			const srcFramebuffer = srcRenderContextData.framebuffers[ srcTextureData.cacheKey ];
			const dstFramebuffer = dstRenderContextData.framebuffers[ dstTextureData.cacheKey ];

			state.bindFramebuffer( gl.READ_FRAMEBUFFER, srcFramebuffer );
			state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, dstFramebuffer );

			let mask = gl.COLOR_BUFFER_BIT;

			if ( srcTexture.isDepthTexture ) mask = gl.DEPTH_BUFFER_BIT;

			gl.blitFramebuffer( minX, minY, width, height, dstX, dstY, width, height, mask, gl.NEAREST );

			state.bindFramebuffer( gl.READ_FRAMEBUFFER, null );
			state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, null );

		} else {

			if ( isDst3D ) {

				// copy data into the 3d texture
				if ( srcTexture.isDataTexture || srcTexture.isData3DTexture ) {

					gl.texSubImage3D( glTextureType, dstLevel, dstX, dstY, dstZ, width, height, depth, glFormat, glType, image.data );

				} else if ( dstTexture.isCompressedArrayTexture ) {

					gl.compressedTexSubImage3D( glTextureType, dstLevel, dstX, dstY, dstZ, width, height, depth, glFormat, image.data );

				} else {

					gl.texSubImage3D( glTextureType, dstLevel, dstX, dstY, dstZ, width, height, depth, glFormat, glType, image );

				}

			} else {

				// copy data into the 2d texture
				if ( srcTexture.isDataTexture ) {

					gl.texSubImage2D( glTextureType, dstLevel, dstX, dstY, width, height, glFormat, glType, image.data );

				} else if ( srcTexture.isCompressedTexture ) {

					gl.compressedTexSubImage2D( glTextureType, dstLevel, dstX, dstY, image.width, image.height, glFormat, image.data );

				} else {

					gl.texSubImage2D( glTextureType, dstLevel, dstX, dstY, width, height, glFormat, glType, image );

				}

			}

		}

		// reset values
		gl.pixelStorei( gl.UNPACK_ROW_LENGTH, currentUnpackRowLen );
		gl.pixelStorei( gl.UNPACK_IMAGE_HEIGHT, currentUnpackImageHeight );
		gl.pixelStorei( gl.UNPACK_SKIP_PIXELS, currentUnpackSkipPixels );
		gl.pixelStorei( gl.UNPACK_SKIP_ROWS, currentUnpackSkipRows );
		gl.pixelStorei( gl.UNPACK_SKIP_IMAGES, currentUnpackSkipImages );

		// Generate mipmaps only when copying level 0
		if ( dstLevel === 0 && dstTexture.generateMipmaps ) {

			gl.generateMipmap( glTextureType );

		}

		state.unbindTexture();

	}
```
</details>

### `WebGLTextureUtils.copyFramebufferToTexture(texture: Texture, renderContext: RenderContext, rectangle: Vector4): void`

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

- `this.backend.get`
- `this.backend.getDrawingBufferSize`
- `renderContext.getCacheKey`
- `state.bindFramebuffer`
- `gl.blitFramebuffer`
- `state.bindTexture`
- `gl.copyTexSubImage2D`
- `state.unbindTexture`
- `gl.createFramebuffer`
- `gl.framebufferTexture2D`
- `gl.deleteFramebuffer`
- `this.generateMipmaps`
- `this.backend._setFramebuffer`

<details><summary>Code</summary>

```typescript
copyFramebufferToTexture( texture, renderContext, rectangle ) {

		const { gl } = this;
		const { state } = this.backend;

		const { textureGPU } = this.backend.get( texture );

		const { x, y, z: width, w: height } = rectangle;

		const requireDrawFrameBuffer = texture.isDepthTexture === true || ( renderContext.renderTarget && renderContext.renderTarget.samples > 0 );

		const srcHeight = renderContext.renderTarget ? renderContext.renderTarget.height : this.backend.getDrawingBufferSize().y;

		if ( requireDrawFrameBuffer ) {

			const partial = ( x !== 0 || y !== 0 );
			let mask;
			let attachment;

			if ( texture.isDepthTexture === true ) {

				mask = gl.DEPTH_BUFFER_BIT;
				attachment = gl.DEPTH_ATTACHMENT;

				if ( renderContext.stencil ) {

					mask |= gl.STENCIL_BUFFER_BIT;

				}

			} else {

				mask = gl.COLOR_BUFFER_BIT;
				attachment = gl.COLOR_ATTACHMENT0;

			}

			if ( partial ) {

				const renderTargetContextData = this.backend.get( renderContext.renderTarget );

				const fb = renderTargetContextData.framebuffers[ renderContext.getCacheKey() ];
				const msaaFrameBuffer = renderTargetContextData.msaaFrameBuffer;

				state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, fb );
				state.bindFramebuffer( gl.READ_FRAMEBUFFER, msaaFrameBuffer );

				const flippedY = srcHeight - y - height;

				gl.blitFramebuffer( x, flippedY, x + width, flippedY + height, x, flippedY, x + width, flippedY + height, mask, gl.NEAREST );

				state.bindFramebuffer( gl.READ_FRAMEBUFFER, fb );

				state.bindTexture( gl.TEXTURE_2D, textureGPU );

				gl.copyTexSubImage2D( gl.TEXTURE_2D, 0, 0, 0, x, flippedY, width, height );

				state.unbindTexture();

			} else {

				const fb = gl.createFramebuffer();

				state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, fb );

				gl.framebufferTexture2D( gl.DRAW_FRAMEBUFFER, attachment, gl.TEXTURE_2D, textureGPU, 0 );
				gl.blitFramebuffer( 0, 0, width, height, 0, 0, width, height, mask, gl.NEAREST );

				gl.deleteFramebuffer( fb );

			}

		} else {

			state.bindTexture( gl.TEXTURE_2D, textureGPU );
			gl.copyTexSubImage2D( gl.TEXTURE_2D, 0, 0, 0, x, srcHeight - height - y, width, height );

			state.unbindTexture();

		}

		if ( texture.generateMipmaps ) this.generateMipmaps( texture );

		this.backend._setFramebuffer( renderContext );

	}
```
</details>

### `WebGLTextureUtils.setupRenderBufferStorage(renderbuffer: WebGLRenderbuffer, renderContext: RenderContext, samples: number, useMultisampledRTT: boolean): void`

**JSDoc:**
```typescript
/**
	 * SetupS storage for internal depth/stencil buffers and bind to correct framebuffer.
	 *
	 * @param {WebGLRenderbuffer} renderbuffer - The render buffer.
	 * @param {RenderContext} renderContext - The render context.
	 * @param {number} samples - The MSAA sample count.
	 * @param {boolean} [useMultisampledRTT=false] - Whether to use WEBGL_multisampled_render_to_texture or not.
	 */
```

**Parameters:**

- **`renderbuffer`** `WebGLRenderbuffer`
- **`renderContext`** `RenderContext`
- **`samples`** `number`
- **`useMultisampledRTT`** `boolean`

**Returns:** `void`

**Calls:**

- `gl.bindRenderbuffer`
- `this.extensions.get`
- `multisampledRTTExt.renderbufferStorageMultisampleEXT`
- `gl.renderbufferStorageMultisample`
- `gl.renderbufferStorage`
- `gl.framebufferRenderbuffer`

<details><summary>Code</summary>

```typescript
setupRenderBufferStorage( renderbuffer, renderContext, samples, useMultisampledRTT = false ) {

		const { gl } = this;
		const renderTarget = renderContext.renderTarget;

		const { depthTexture, depthBuffer, stencilBuffer, width, height } = renderTarget;

		gl.bindRenderbuffer( gl.RENDERBUFFER, renderbuffer );

		if ( depthBuffer && ! stencilBuffer ) {

			let glInternalFormat = gl.DEPTH_COMPONENT24;

			if ( useMultisampledRTT === true ) {

				const multisampledRTTExt = this.extensions.get( 'WEBGL_multisampled_render_to_texture' );

				multisampledRTTExt.renderbufferStorageMultisampleEXT( gl.RENDERBUFFER, renderTarget.samples, glInternalFormat, width, height );

			} else if ( samples > 0 ) {

				if ( depthTexture && depthTexture.isDepthTexture ) {

					if ( depthTexture.type === gl.FLOAT ) {

						glInternalFormat = gl.DEPTH_COMPONENT32F;

					}

				}

				gl.renderbufferStorageMultisample( gl.RENDERBUFFER, samples, glInternalFormat, width, height );

			} else {

				gl.renderbufferStorage( gl.RENDERBUFFER, glInternalFormat, width, height );

			}

			gl.framebufferRenderbuffer( gl.FRAMEBUFFER, gl.DEPTH_ATTACHMENT, gl.RENDERBUFFER, renderbuffer );

		} else if ( depthBuffer && stencilBuffer ) {

			if ( samples > 0 ) {

				gl.renderbufferStorageMultisample( gl.RENDERBUFFER, samples, gl.DEPTH24_STENCIL8, width, height );

			} else {

				gl.renderbufferStorage( gl.RENDERBUFFER, gl.DEPTH_STENCIL, width, height );

			}


			gl.framebufferRenderbuffer( gl.FRAMEBUFFER, gl.DEPTH_STENCIL_ATTACHMENT, gl.RENDERBUFFER, renderbuffer );

		}

		gl.bindRenderbuffer( gl.RENDERBUFFER, null );

	}
```
</details>

### `WebGLTextureUtils.copyTextureToBuffer(texture: Texture, x: number, y: number, width: number, height: number, faceIndex: number): Promise<TypedArray>`

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
- `gl.createFramebuffer`
- `gl.bindFramebuffer`
- `gl.framebufferTexture2D`
- `this._getTypedArrayType`
- `this._getBytesPerTexel`
- `gl.createBuffer`
- `gl.bindBuffer`
- `gl.bufferData`
- `gl.readPixels`
- `backend.utils._clientWaitAsync`
- `gl.getBufferSubData`
- `gl.deleteFramebuffer`

<details><summary>Code</summary>

```typescript
async copyTextureToBuffer( texture, x, y, width, height, faceIndex ) {

		const { backend, gl } = this;

		const { textureGPU, glFormat, glType } = this.backend.get( texture );

		const fb = gl.createFramebuffer();

		gl.bindFramebuffer( gl.READ_FRAMEBUFFER, fb );

		const target = texture.isCubeTexture ? gl.TEXTURE_CUBE_MAP_POSITIVE_X + faceIndex : gl.TEXTURE_2D;

		gl.framebufferTexture2D( gl.READ_FRAMEBUFFER, gl.COLOR_ATTACHMENT0, target, textureGPU, 0 );

		const typedArrayType = this._getTypedArrayType( glType );
		const bytesPerTexel = this._getBytesPerTexel( glType, glFormat );

		const elementCount = width * height;
		const byteLength = elementCount * bytesPerTexel;

		const buffer = gl.createBuffer();

		gl.bindBuffer( gl.PIXEL_PACK_BUFFER, buffer );
		gl.bufferData( gl.PIXEL_PACK_BUFFER, byteLength, gl.STREAM_READ );
		gl.readPixels( x, y, width, height, glFormat, glType, 0 );
		gl.bindBuffer( gl.PIXEL_PACK_BUFFER, null );

		await backend.utils._clientWaitAsync();

		const dstBuffer = new typedArrayType( byteLength / typedArrayType.BYTES_PER_ELEMENT );

		gl.bindBuffer( gl.PIXEL_PACK_BUFFER, buffer );
		gl.getBufferSubData( gl.PIXEL_PACK_BUFFER, 0, dstBuffer );
		gl.bindBuffer( gl.PIXEL_PACK_BUFFER, null );

		gl.deleteFramebuffer( fb );

		return dstBuffer;

	}
```
</details>

### `WebGLTextureUtils._getTypedArrayType(glType: number): TypedArray.constructor`

**JSDoc:**
```typescript
/**
	 * Returns the corresponding typed array type for the given WebGL data type.
	 *
	 * @private
	 * @param {GLenum} glType - The WebGL data type.
	 * @return {TypedArray.constructor} The typed array type.
	 */
```

**Parameters:**

- **`glType`** `number`

**Returns:** `TypedArray.constructor`

<details><summary>Code</summary>

```typescript
_getTypedArrayType( glType ) {

		const { gl } = this;

		if ( glType === gl.UNSIGNED_BYTE ) return Uint8Array;

		if ( glType === gl.UNSIGNED_SHORT_4_4_4_4 ) return Uint16Array;
		if ( glType === gl.UNSIGNED_SHORT_5_5_5_1 ) return Uint16Array;
		if ( glType === gl.UNSIGNED_SHORT_5_6_5 ) return Uint16Array;
		if ( glType === gl.UNSIGNED_SHORT ) return Uint16Array;
		if ( glType === gl.UNSIGNED_INT ) return Uint32Array;

		if ( glType === gl.HALF_FLOAT ) return Uint16Array;
		if ( glType === gl.FLOAT ) return Float32Array;

		throw new Error( `Unsupported WebGL type: ${glType}` );

	}
```
</details>

### `WebGLTextureUtils._getBytesPerTexel(glType: number, glFormat: number): number`

**JSDoc:**
```typescript
/**
	 * Returns the bytes-per-texel value for the given WebGL data type and texture format.
	 *
	 * @private
	 * @param {GLenum} glType - The WebGL data type.
	 * @param {GLenum} glFormat - The WebGL texture format.
	 * @return {number} The bytes-per-texel.
	 */
```

**Parameters:**

- **`glType`** `number`
- **`glFormat`** `number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
_getBytesPerTexel( glType, glFormat ) {

		const { gl } = this;

		let bytesPerComponent = 0;

		if ( glType === gl.UNSIGNED_BYTE ) bytesPerComponent = 1;

		if ( glType === gl.UNSIGNED_SHORT_4_4_4_4 ||
			glType === gl.UNSIGNED_SHORT_5_5_5_1 ||
			glType === gl.UNSIGNED_SHORT_5_6_5 ||
			glType === gl.UNSIGNED_SHORT ||
			glType === gl.HALF_FLOAT ) bytesPerComponent = 2;

		if ( glType === gl.UNSIGNED_INT ||
			glType === gl.FLOAT ) bytesPerComponent = 4;

		if ( glFormat === gl.RGBA ) return bytesPerComponent * 4;
		if ( glFormat === gl.RGB ) return bytesPerComponent * 3;
		if ( glFormat === gl.ALPHA ) return bytesPerComponent;

	}
```
</details>

### `getImage(source: any): any`

**Parameters:**

- **`source`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getImage( source ) {

	if ( source.isDataTexture ) {

		return source.image.data;

	} else if ( ( typeof HTMLImageElement !== 'undefined' && source instanceof HTMLImageElement ) ||
		( typeof HTMLCanvasElement !== 'undefined' && source instanceof HTMLCanvasElement ) ||
		( typeof ImageBitmap !== 'undefined' && source instanceof ImageBitmap ) ||
		( typeof OffscreenCanvas !== 'undefined' && source instanceof OffscreenCanvas ) ) {

		return source;

	}

	return source.data;

}
```
</details>


---

## Classes

### `WebGLTextureUtils`

<details><summary>Class Code</summary>

```ts
class WebGLTextureUtils {

	/**
	 * Constructs a new utility object.
	 *
	 * @param {WebGLBackend} backend - The WebGL 2 backend.
	 */
	constructor( backend ) {

		/**
		 * A reference to the WebGL 2 backend.
		 *
		 * @type {WebGLBackend}
		 */
		this.backend = backend;

		/**
		 * A reference to the rendering context.
		 *
		 * @type {WebGL2RenderingContext}
		 */
		this.gl = backend.gl;

		/**
		 * A reference to a backend module holding extension-related
		 * utility functions.
		 *
		 * @type {WebGLExtensions}
		 */
		this.extensions = backend.extensions;

		/**
		 * A dictionary for managing default textures. The key
		 * is the binding point (target), the value the WEbGL texture object.
		 *
		 * @type {Object<GLenum,WebGLTexture>}
		 */
		this.defaultTextures = {};

		if ( initialized === false ) {

			this._init();

			initialized = true;

		}

	}

	/**
	 * Inits the state of the utility.
	 *
	 * @private
	 */
	_init() {

		const gl = this.gl;

		// Store only WebGL constants here.

		wrappingToGL = {
			[ RepeatWrapping ]: gl.REPEAT,
			[ ClampToEdgeWrapping ]: gl.CLAMP_TO_EDGE,
			[ MirroredRepeatWrapping ]: gl.MIRRORED_REPEAT
		};

		filterToGL = {
			[ NearestFilter ]: gl.NEAREST,
			[ NearestMipmapNearestFilter ]: gl.NEAREST_MIPMAP_NEAREST,
			[ NearestMipmapLinearFilter ]: gl.NEAREST_MIPMAP_LINEAR,

			[ LinearFilter ]: gl.LINEAR,
			[ LinearMipmapNearestFilter ]: gl.LINEAR_MIPMAP_NEAREST,
			[ LinearMipmapLinearFilter ]: gl.LINEAR_MIPMAP_LINEAR
		};

		compareToGL = {
			[ NeverCompare ]: gl.NEVER,
			[ AlwaysCompare ]: gl.ALWAYS,
			[ LessCompare ]: gl.LESS,
			[ LessEqualCompare ]: gl.LEQUAL,
			[ EqualCompare ]: gl.EQUAL,
			[ GreaterEqualCompare ]: gl.GEQUAL,
			[ GreaterCompare ]: gl.GREATER,
			[ NotEqualCompare ]: gl.NOTEQUAL
		};

	}

	/**
	 * Returns the native texture type for the given texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @return {GLenum} The native texture type.
	 */
	getGLTextureType( texture ) {

		const { gl } = this;

		let glTextureType;

		if ( texture.isCubeTexture === true ) {

			glTextureType = gl.TEXTURE_CUBE_MAP;

		} else if ( texture.isArrayTexture === true || texture.isDataArrayTexture === true || texture.isCompressedArrayTexture === true ) {

			glTextureType = gl.TEXTURE_2D_ARRAY;

		} else if ( texture.isData3DTexture === true ) { // TODO: isCompressed3DTexture, wait for #26642

			glTextureType = gl.TEXTURE_3D;

		} else {

			glTextureType = gl.TEXTURE_2D;


		}

		return glTextureType;

	}

	/**
	 * Returns the native texture type for the given texture.
	 *
	 * @param {?string} internalFormatName - The internal format name. When `null`, the internal format is derived from the subsequent parameters.
	 * @param {GLenum} glFormat - The WebGL format.
	 * @param {GLenum} glType - The WebGL type.
	 * @param {string} colorSpace - The texture's color space.
	 * @param {boolean} [forceLinearTransfer=false] - Whether to force a linear transfer or not.
	 * @return {GLenum} The internal format.
	 */
	getInternalFormat( internalFormatName, glFormat, glType, colorSpace, forceLinearTransfer = false ) {

		const { gl, extensions } = this;

		if ( internalFormatName !== null ) {

			if ( gl[ internalFormatName ] !== undefined ) return gl[ internalFormatName ];

			console.warn( 'THREE.WebGLRenderer: Attempt to use non-existing WebGL internal format \'' + internalFormatName + '\'' );

		}

		let internalFormat = glFormat;

		if ( glFormat === gl.RED ) {

			if ( glType === gl.FLOAT ) internalFormat = gl.R32F;
			if ( glType === gl.HALF_FLOAT ) internalFormat = gl.R16F;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.R8;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.R16;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.R32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.R8I;
			if ( glType === gl.SHORT ) internalFormat = gl.R16I;
			if ( glType === gl.INT ) internalFormat = gl.R32I;

		}

		if ( glFormat === gl.RED_INTEGER ) {

			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.R8UI;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.R16UI;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.R32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.R8I;
			if ( glType === gl.SHORT ) internalFormat = gl.R16I;
			if ( glType === gl.INT ) internalFormat = gl.R32I;

		}

		if ( glFormat === gl.RG ) {

			if ( glType === gl.FLOAT ) internalFormat = gl.RG32F;
			if ( glType === gl.HALF_FLOAT ) internalFormat = gl.RG16F;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RG8;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RG16;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RG32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RG8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RG16I;
			if ( glType === gl.INT ) internalFormat = gl.RG32I;

		}

		if ( glFormat === gl.RG_INTEGER ) {

			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RG8UI;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RG16UI;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RG32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RG8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RG16I;
			if ( glType === gl.INT ) internalFormat = gl.RG32I;

		}

		if ( glFormat === gl.RGB ) {

			const transfer = forceLinearTransfer ? LinearTransfer : ColorManagement.getTransfer( colorSpace );

			if ( glType === gl.FLOAT ) internalFormat = gl.RGB32F;
			if ( glType === gl.HALF_FLOAT ) internalFormat = gl.RGB16F;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RGB8;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RGB16;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RGB32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RGB8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RGB16I;
			if ( glType === gl.INT ) internalFormat = gl.RGB32I;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = ( transfer === SRGBTransfer ) ? gl.SRGB8 : gl.RGB8;
			if ( glType === gl.UNSIGNED_SHORT_5_6_5 ) internalFormat = gl.RGB565;
			if ( glType === gl.UNSIGNED_SHORT_5_5_5_1 ) internalFormat = gl.RGB5_A1;
			if ( glType === gl.UNSIGNED_SHORT_4_4_4_4 ) internalFormat = gl.RGB4;
			if ( glType === gl.UNSIGNED_INT_5_9_9_9_REV ) internalFormat = gl.RGB9_E5;

		}

		if ( glFormat === gl.RGB_INTEGER ) {

			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RGB8UI;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RGB16UI;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RGB32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RGB8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RGB16I;
			if ( glType === gl.INT ) internalFormat = gl.RGB32I;

		}

		if ( glFormat === gl.RGBA ) {

			const transfer = forceLinearTransfer ? LinearTransfer : ColorManagement.getTransfer( colorSpace );

			if ( glType === gl.FLOAT ) internalFormat = gl.RGBA32F;
			if ( glType === gl.HALF_FLOAT ) internalFormat = gl.RGBA16F;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RGBA8;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RGBA16;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RGBA32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RGBA8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RGBA16I;
			if ( glType === gl.INT ) internalFormat = gl.RGBA32I;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = ( transfer === SRGBTransfer ) ? gl.SRGB8_ALPHA8 : gl.RGBA8;
			if ( glType === gl.UNSIGNED_SHORT_4_4_4_4 ) internalFormat = gl.RGBA4;
			if ( glType === gl.UNSIGNED_SHORT_5_5_5_1 ) internalFormat = gl.RGB5_A1;

		}

		if ( glFormat === gl.RGBA_INTEGER ) {

			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RGBA8UI;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RGBA16UI;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RGBA32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RGBA8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RGBA16I;
			if ( glType === gl.INT ) internalFormat = gl.RGBA32I;

		}

		if ( glFormat === gl.DEPTH_COMPONENT ) {

			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.DEPTH_COMPONENT16;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.DEPTH_COMPONENT24;
			if ( glType === gl.FLOAT ) internalFormat = gl.DEPTH_COMPONENT32F;

		}

		if ( glFormat === gl.DEPTH_STENCIL ) {

			if ( glType === gl.UNSIGNED_INT_24_8 ) internalFormat = gl.DEPTH24_STENCIL8;

		}

		if ( internalFormat === gl.R16F || internalFormat === gl.R32F ||
			internalFormat === gl.RG16F || internalFormat === gl.RG32F ||
			internalFormat === gl.RGBA16F || internalFormat === gl.RGBA32F ) {

			extensions.get( 'EXT_color_buffer_float' );

		}

		return internalFormat;

	}

	/**
	 * Sets the texture parameters for the given texture.
	 *
	 * @param {GLenum} textureType - The texture type.
	 * @param {Texture} texture - The texture.
	 */
	setTextureParameters( textureType, texture ) {

		const { gl, extensions, backend } = this;

		const workingPrimaries = ColorManagement.getPrimaries( ColorManagement.workingColorSpace );
		const texturePrimaries = texture.colorSpace === NoColorSpace ? null : ColorManagement.getPrimaries( texture.colorSpace );
		const unpackConversion = texture.colorSpace === NoColorSpace || workingPrimaries === texturePrimaries ? gl.NONE : gl.BROWSER_DEFAULT_WEBGL;

		gl.pixelStorei( gl.UNPACK_FLIP_Y_WEBGL, texture.flipY );
		gl.pixelStorei( gl.UNPACK_PREMULTIPLY_ALPHA_WEBGL, texture.premultiplyAlpha );
		gl.pixelStorei( gl.UNPACK_ALIGNMENT, texture.unpackAlignment );
		gl.pixelStorei( gl.UNPACK_COLORSPACE_CONVERSION_WEBGL, unpackConversion );

		gl.texParameteri( textureType, gl.TEXTURE_WRAP_S, wrappingToGL[ texture.wrapS ] );
		gl.texParameteri( textureType, gl.TEXTURE_WRAP_T, wrappingToGL[ texture.wrapT ] );

		if ( textureType === gl.TEXTURE_3D || textureType === gl.TEXTURE_2D_ARRAY ) {

			// WebGL 2 does not support wrapping for depth 2D array textures
			if ( ! texture.isArrayTexture ) {

				gl.texParameteri( textureType, gl.TEXTURE_WRAP_R, wrappingToGL[ texture.wrapR ] );

			}

		}

		gl.texParameteri( textureType, gl.TEXTURE_MAG_FILTER, filterToGL[ texture.magFilter ] );


		const hasMipmaps = texture.mipmaps !== undefined && texture.mipmaps.length > 0;

		// follow WebGPU backend mapping for texture filtering
		const minFilter = texture.minFilter === LinearFilter && hasMipmaps ? LinearMipmapLinearFilter : texture.minFilter;

		gl.texParameteri( textureType, gl.TEXTURE_MIN_FILTER, filterToGL[ minFilter ] );

		if ( texture.compareFunction ) {

			gl.texParameteri( textureType, gl.TEXTURE_COMPARE_MODE, gl.COMPARE_REF_TO_TEXTURE );
			gl.texParameteri( textureType, gl.TEXTURE_COMPARE_FUNC, compareToGL[ texture.compareFunction ] );

		}

		if ( extensions.has( 'EXT_texture_filter_anisotropic' ) === true ) {

			if ( texture.magFilter === NearestFilter ) return;
			if ( texture.minFilter !== NearestMipmapLinearFilter && texture.minFilter !== LinearMipmapLinearFilter ) return;
			if ( texture.type === FloatType && extensions.has( 'OES_texture_float_linear' ) === false ) return; // verify extension for WebGL 1 and WebGL 2

			if ( texture.anisotropy > 1 ) {

				const extension = extensions.get( 'EXT_texture_filter_anisotropic' );
				gl.texParameterf( textureType, extension.TEXTURE_MAX_ANISOTROPY_EXT, Math.min( texture.anisotropy, backend.getMaxAnisotropy() ) );

			}

		}

	}

	/**
	 * Creates a default texture for the given texture that can be used
	 * as a placeholder until the actual texture is ready for usage.
	 *
	 * @param {Texture} texture - The texture to create a default texture for.
	 */
	createDefaultTexture( texture ) {

		const { gl, backend, defaultTextures } = this;


		const glTextureType = this.getGLTextureType( texture );

		let textureGPU = defaultTextures[ glTextureType ];

		if ( textureGPU === undefined ) {

			textureGPU = gl.createTexture();

			backend.state.bindTexture( glTextureType, textureGPU );
			gl.texParameteri( glTextureType, gl.TEXTURE_MIN_FILTER, gl.NEAREST );
			gl.texParameteri( glTextureType, gl.TEXTURE_MAG_FILTER, gl.NEAREST );

			// gl.texImage2D( glTextureType, 0, gl.RGBA, 1, 1, 0, gl.RGBA, gl.UNSIGNED_BYTE, data );

			defaultTextures[ glTextureType ] = textureGPU;

		}

		backend.set( texture, {
			textureGPU,
			glTextureType,
			isDefault: true
		} );

	}

	/**
	 * Defines a texture on the GPU for the given texture object.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {Object} [options={}] - Optional configuration parameter.
	 * @return {undefined}
	 */
	createTexture( texture, options ) {

		const { gl, backend } = this;
		const { levels, width, height, depth } = options;

		const glFormat = backend.utils.convert( texture.format, texture.colorSpace );
		const glType = backend.utils.convert( texture.type );
		const glInternalFormat = this.getInternalFormat( texture.internalFormat, glFormat, glType, texture.colorSpace, texture.isVideoTexture );

		const textureGPU = gl.createTexture();
		const glTextureType = this.getGLTextureType( texture );

		backend.state.bindTexture( glTextureType, textureGPU );

		this.setTextureParameters( glTextureType, texture );

		if ( texture.isArrayTexture || texture.isDataArrayTexture || texture.isCompressedArrayTexture ) {

			gl.texStorage3D( gl.TEXTURE_2D_ARRAY, levels, glInternalFormat, width, height, depth );

		} else if ( texture.isData3DTexture ) {

			gl.texStorage3D( gl.TEXTURE_3D, levels, glInternalFormat, width, height, depth );

		} else if ( ! texture.isVideoTexture ) {

			gl.texStorage2D( glTextureType, levels, glInternalFormat, width, height );

		}

		backend.set( texture, {
			textureGPU,
			glTextureType,
			glFormat,
			glType,
			glInternalFormat
		} );

	}

	/**
	 * Uploads texture buffer data to the GPU memory.
	 *
	 * @param {WebGLBuffer} buffer - The buffer data.
	 * @param {Texture} texture - The texture,
	 */
	copyBufferToTexture( buffer, texture ) {

		const { gl, backend } = this;

		const { textureGPU, glTextureType, glFormat, glType } = backend.get( texture );

		const { width, height } = texture.source.data;

		gl.bindBuffer( gl.PIXEL_UNPACK_BUFFER, buffer );

		backend.state.bindTexture( glTextureType, textureGPU );

		gl.pixelStorei( gl.UNPACK_FLIP_Y_WEBGL, false );
		gl.pixelStorei( gl.UNPACK_PREMULTIPLY_ALPHA_WEBGL, false );
		gl.texSubImage2D( glTextureType, 0, 0, 0, width, height, glFormat, glType, 0 );

		gl.bindBuffer( gl.PIXEL_UNPACK_BUFFER, null );

		backend.state.unbindTexture();
		// debug
		// const framebuffer = gl.createFramebuffer();
		// gl.bindFramebuffer( gl.FRAMEBUFFER, framebuffer );
		// gl.framebufferTexture2D( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0, glTextureType, textureGPU, 0 );

		// const readout = new Float32Array( width * height * 4 );

		// const altFormat = gl.getParameter( gl.IMPLEMENTATION_COLOR_READ_FORMAT );
		// const altType = gl.getParameter( gl.IMPLEMENTATION_COLOR_READ_TYPE );

		// gl.readPixels( 0, 0, width, height, altFormat, altType, readout );
		// gl.bindFramebuffer( gl.FRAMEBUFFER, null );
		// console.log( readout );

	}

	/**
	 * Uploads the updated texture data to the GPU.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {Object} [options={}] - Optional configuration parameter.
	 */
	updateTexture( texture, options ) {

		const { gl } = this;
		const { width, height } = options;
		const { textureGPU, glTextureType, glFormat, glType, glInternalFormat } = this.backend.get( texture );

		if ( texture.isRenderTargetTexture || ( textureGPU === undefined /* unsupported texture format */ ) )
			return;

		this.backend.state.bindTexture( glTextureType, textureGPU );

		this.setTextureParameters( glTextureType, texture );

		if ( texture.isCompressedTexture ) {

			const mipmaps = texture.mipmaps;
			const image = options.image;

			for ( let i = 0; i < mipmaps.length; i ++ ) {

				const mipmap = mipmaps[ i ];

				if ( texture.isCompressedArrayTexture ) {


					if ( texture.format !== gl.RGBA ) {

						if ( glFormat !== null ) {

							gl.compressedTexSubImage3D( gl.TEXTURE_2D_ARRAY, i, 0, 0, 0, mipmap.width, mipmap.height, image.depth, glFormat, mipmap.data );

						} else {

							console.warn( 'THREE.WebGLRenderer: Attempt to load unsupported compressed texture format in .uploadTexture()' );

						}

					} else {

						gl.texSubImage3D( gl.TEXTURE_2D_ARRAY, i, 0, 0, 0, mipmap.width, mipmap.height, image.depth, glFormat, glType, mipmap.data );

					}

				} else {

					if ( glFormat !== null ) {

						gl.compressedTexSubImage2D( gl.TEXTURE_2D, i, 0, 0, mipmap.width, mipmap.height, glFormat, mipmap.data );

					} else {

						console.warn( 'Unsupported compressed texture format' );

					}

				}

			}


		} else if ( texture.isCubeTexture ) {

			const images = options.images;

			for ( let i = 0; i < 6; i ++ ) {

				const image = getImage( images[ i ] );

				gl.texSubImage2D( gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, 0, 0, 0, width, height, glFormat, glType, image );

			}

		} else if ( texture.isDataArrayTexture || texture.isArrayTexture ) {

			const image = options.image;

			gl.texSubImage3D( gl.TEXTURE_2D_ARRAY, 0, 0, 0, 0, image.width, image.height, image.depth, glFormat, glType, image.data );

		} else if ( texture.isData3DTexture ) {

			const image = options.image;

			gl.texSubImage3D( gl.TEXTURE_3D, 0, 0, 0, 0, image.width, image.height, image.depth, glFormat, glType, image.data );

		} else if ( texture.isVideoTexture ) {

			texture.update();

			gl.texImage2D( glTextureType, 0, glInternalFormat, glFormat, glType, options.image );


		} else {

			const image = getImage( options.image );

			gl.texSubImage2D( glTextureType, 0, 0, 0, width, height, glFormat, glType, image );

		}

	}

	/**
	 * Generates mipmaps for the given texture.
	 *
	 * @param {Texture} texture - The texture.
	 */
	generateMipmaps( texture ) {

		const { gl, backend } = this;
		const { textureGPU, glTextureType } = backend.get( texture );

		backend.state.bindTexture( glTextureType, textureGPU );
		gl.generateMipmap( glTextureType );

	}

	/**
	 * Deallocates the render buffers of the given render target.
	 *
	 * @param {RenderTarget} renderTarget - The render target.
	 */
	deallocateRenderBuffers( renderTarget ) {

		const { gl, backend } = this;

		// remove framebuffer reference
		if ( renderTarget ) {

			const renderContextData = backend.get( renderTarget );

			renderContextData.renderBufferStorageSetup = undefined;

			if ( renderContextData.framebuffers ) {

				for ( const cacheKey in renderContextData.framebuffers ) {

					gl.deleteFramebuffer( renderContextData.framebuffers[ cacheKey ] );

				}

				delete renderContextData.framebuffers;

			}

			if ( renderContextData.depthRenderbuffer ) {

				gl.deleteRenderbuffer( renderContextData.depthRenderbuffer );
				delete renderContextData.depthRenderbuffer;

			}

			if ( renderContextData.stencilRenderbuffer ) {

				gl.deleteRenderbuffer( renderContextData.stencilRenderbuffer );
				delete renderContextData.stencilRenderbuffer;

			}

			if ( renderContextData.msaaFrameBuffer ) {

				gl.deleteFramebuffer( renderContextData.msaaFrameBuffer );
				delete renderContextData.msaaFrameBuffer;

			}

			if ( renderContextData.msaaRenderbuffers ) {

				for ( let i = 0; i < renderContextData.msaaRenderbuffers.length; i ++ ) {

					gl.deleteRenderbuffer( renderContextData.msaaRenderbuffers[ i ] );

				}

				delete renderContextData.msaaRenderbuffers;

			}

		}

	}

	/**
	 * Destroys the GPU data for the given texture object.
	 *
	 * @param {Texture} texture - The texture.
	 */
	destroyTexture( texture ) {

		const { gl, backend } = this;
		const { textureGPU, renderTarget } = backend.get( texture );

		this.deallocateRenderBuffers( renderTarget );
		gl.deleteTexture( textureGPU );

		backend.delete( texture );

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

		const { gl, backend } = this;
		const { state } = this.backend;

		const { textureGPU: dstTextureGPU, glTextureType, glType, glFormat } = backend.get( dstTexture );

		state.bindTexture( glTextureType, dstTextureGPU );

		// gather the necessary dimensions to copy
		let width, height, depth, minX, minY, minZ;
		let dstX, dstY, dstZ;
		const image = srcTexture.isCompressedTexture ? srcTexture.mipmaps[ dstLevel ] : srcTexture.image;

		if ( srcRegion !== null ) {

			width = srcRegion.max.x - srcRegion.min.x;
			height = srcRegion.max.y - srcRegion.min.y;
			depth = srcRegion.isBox3 ? srcRegion.max.z - srcRegion.min.z : 1;
			minX = srcRegion.min.x;
			minY = srcRegion.min.y;
			minZ = srcRegion.isBox3 ? srcRegion.min.z : 0;

		} else {

			const levelScale = Math.pow( 2, - srcLevel );
			width = Math.floor( image.width * levelScale );
			height = Math.floor( image.height * levelScale );

			if ( srcTexture.isDataArrayTexture || srcTexture.isArrayTexture ) {

				depth = image.depth;

			} else if ( srcTexture.isData3DTexture ) {

				depth = Math.floor( image.depth * levelScale );

			} else {

				depth = 1;

			}

			minX = 0;
			minY = 0;
			minZ = 0;

		}

		if ( dstPosition !== null ) {

			dstX = dstPosition.x;
			dstY = dstPosition.y;
			dstZ = dstPosition.z;

		} else {

			dstX = 0;
			dstY = 0;
			dstZ = 0;

		}


		gl.pixelStorei( gl.UNPACK_FLIP_Y_WEBGL, dstTexture.flipY );
		gl.pixelStorei( gl.UNPACK_PREMULTIPLY_ALPHA_WEBGL, dstTexture.premultiplyAlpha );
		gl.pixelStorei( gl.UNPACK_ALIGNMENT, dstTexture.unpackAlignment );

		// used for copying data from cpu
		const currentUnpackRowLen = gl.getParameter( gl.UNPACK_ROW_LENGTH );
		const currentUnpackImageHeight = gl.getParameter( gl.UNPACK_IMAGE_HEIGHT );
		const currentUnpackSkipPixels = gl.getParameter( gl.UNPACK_SKIP_PIXELS );
		const currentUnpackSkipRows = gl.getParameter( gl.UNPACK_SKIP_ROWS );
		const currentUnpackSkipImages = gl.getParameter( gl.UNPACK_SKIP_IMAGES );

		gl.pixelStorei( gl.UNPACK_ROW_LENGTH, image.width );
		gl.pixelStorei( gl.UNPACK_IMAGE_HEIGHT, image.height );
		gl.pixelStorei( gl.UNPACK_SKIP_PIXELS, minX );
		gl.pixelStorei( gl.UNPACK_SKIP_ROWS, minY );
		gl.pixelStorei( gl.UNPACK_SKIP_IMAGES, minZ );

		// set up the src texture
		const isDst3D = dstTexture.isDataArrayTexture || dstTexture.isData3DTexture || dstTexture.isArrayTexture;
		if ( srcTexture.isRenderTargetTexture || srcTexture.isDepthTexture ) {

			const srcTextureData = backend.get( srcTexture );
			const dstTextureData = backend.get( dstTexture );

			const srcRenderContextData = backend.get( srcTextureData.renderTarget );
			const dstRenderContextData = backend.get( dstTextureData.renderTarget );

			const srcFramebuffer = srcRenderContextData.framebuffers[ srcTextureData.cacheKey ];
			const dstFramebuffer = dstRenderContextData.framebuffers[ dstTextureData.cacheKey ];

			state.bindFramebuffer( gl.READ_FRAMEBUFFER, srcFramebuffer );
			state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, dstFramebuffer );

			let mask = gl.COLOR_BUFFER_BIT;

			if ( srcTexture.isDepthTexture ) mask = gl.DEPTH_BUFFER_BIT;

			gl.blitFramebuffer( minX, minY, width, height, dstX, dstY, width, height, mask, gl.NEAREST );

			state.bindFramebuffer( gl.READ_FRAMEBUFFER, null );
			state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, null );

		} else {

			if ( isDst3D ) {

				// copy data into the 3d texture
				if ( srcTexture.isDataTexture || srcTexture.isData3DTexture ) {

					gl.texSubImage3D( glTextureType, dstLevel, dstX, dstY, dstZ, width, height, depth, glFormat, glType, image.data );

				} else if ( dstTexture.isCompressedArrayTexture ) {

					gl.compressedTexSubImage3D( glTextureType, dstLevel, dstX, dstY, dstZ, width, height, depth, glFormat, image.data );

				} else {

					gl.texSubImage3D( glTextureType, dstLevel, dstX, dstY, dstZ, width, height, depth, glFormat, glType, image );

				}

			} else {

				// copy data into the 2d texture
				if ( srcTexture.isDataTexture ) {

					gl.texSubImage2D( glTextureType, dstLevel, dstX, dstY, width, height, glFormat, glType, image.data );

				} else if ( srcTexture.isCompressedTexture ) {

					gl.compressedTexSubImage2D( glTextureType, dstLevel, dstX, dstY, image.width, image.height, glFormat, image.data );

				} else {

					gl.texSubImage2D( glTextureType, dstLevel, dstX, dstY, width, height, glFormat, glType, image );

				}

			}

		}

		// reset values
		gl.pixelStorei( gl.UNPACK_ROW_LENGTH, currentUnpackRowLen );
		gl.pixelStorei( gl.UNPACK_IMAGE_HEIGHT, currentUnpackImageHeight );
		gl.pixelStorei( gl.UNPACK_SKIP_PIXELS, currentUnpackSkipPixels );
		gl.pixelStorei( gl.UNPACK_SKIP_ROWS, currentUnpackSkipRows );
		gl.pixelStorei( gl.UNPACK_SKIP_IMAGES, currentUnpackSkipImages );

		// Generate mipmaps only when copying level 0
		if ( dstLevel === 0 && dstTexture.generateMipmaps ) {

			gl.generateMipmap( glTextureType );

		}

		state.unbindTexture();

	}


	/**
	 * Copies the current bound framebuffer to the given texture.
	 *
	 * @param {Texture} texture - The destination texture.
	 * @param {RenderContext} renderContext - The render context.
	 * @param {Vector4} rectangle - A four dimensional vector defining the origin and dimension of the copy.
	 */
	copyFramebufferToTexture( texture, renderContext, rectangle ) {

		const { gl } = this;
		const { state } = this.backend;

		const { textureGPU } = this.backend.get( texture );

		const { x, y, z: width, w: height } = rectangle;

		const requireDrawFrameBuffer = texture.isDepthTexture === true || ( renderContext.renderTarget && renderContext.renderTarget.samples > 0 );

		const srcHeight = renderContext.renderTarget ? renderContext.renderTarget.height : this.backend.getDrawingBufferSize().y;

		if ( requireDrawFrameBuffer ) {

			const partial = ( x !== 0 || y !== 0 );
			let mask;
			let attachment;

			if ( texture.isDepthTexture === true ) {

				mask = gl.DEPTH_BUFFER_BIT;
				attachment = gl.DEPTH_ATTACHMENT;

				if ( renderContext.stencil ) {

					mask |= gl.STENCIL_BUFFER_BIT;

				}

			} else {

				mask = gl.COLOR_BUFFER_BIT;
				attachment = gl.COLOR_ATTACHMENT0;

			}

			if ( partial ) {

				const renderTargetContextData = this.backend.get( renderContext.renderTarget );

				const fb = renderTargetContextData.framebuffers[ renderContext.getCacheKey() ];
				const msaaFrameBuffer = renderTargetContextData.msaaFrameBuffer;

				state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, fb );
				state.bindFramebuffer( gl.READ_FRAMEBUFFER, msaaFrameBuffer );

				const flippedY = srcHeight - y - height;

				gl.blitFramebuffer( x, flippedY, x + width, flippedY + height, x, flippedY, x + width, flippedY + height, mask, gl.NEAREST );

				state.bindFramebuffer( gl.READ_FRAMEBUFFER, fb );

				state.bindTexture( gl.TEXTURE_2D, textureGPU );

				gl.copyTexSubImage2D( gl.TEXTURE_2D, 0, 0, 0, x, flippedY, width, height );

				state.unbindTexture();

			} else {

				const fb = gl.createFramebuffer();

				state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, fb );

				gl.framebufferTexture2D( gl.DRAW_FRAMEBUFFER, attachment, gl.TEXTURE_2D, textureGPU, 0 );
				gl.blitFramebuffer( 0, 0, width, height, 0, 0, width, height, mask, gl.NEAREST );

				gl.deleteFramebuffer( fb );

			}

		} else {

			state.bindTexture( gl.TEXTURE_2D, textureGPU );
			gl.copyTexSubImage2D( gl.TEXTURE_2D, 0, 0, 0, x, srcHeight - height - y, width, height );

			state.unbindTexture();

		}

		if ( texture.generateMipmaps ) this.generateMipmaps( texture );

		this.backend._setFramebuffer( renderContext );

	}

	/**
	 * SetupS storage for internal depth/stencil buffers and bind to correct framebuffer.
	 *
	 * @param {WebGLRenderbuffer} renderbuffer - The render buffer.
	 * @param {RenderContext} renderContext - The render context.
	 * @param {number} samples - The MSAA sample count.
	 * @param {boolean} [useMultisampledRTT=false] - Whether to use WEBGL_multisampled_render_to_texture or not.
	 */
	setupRenderBufferStorage( renderbuffer, renderContext, samples, useMultisampledRTT = false ) {

		const { gl } = this;
		const renderTarget = renderContext.renderTarget;

		const { depthTexture, depthBuffer, stencilBuffer, width, height } = renderTarget;

		gl.bindRenderbuffer( gl.RENDERBUFFER, renderbuffer );

		if ( depthBuffer && ! stencilBuffer ) {

			let glInternalFormat = gl.DEPTH_COMPONENT24;

			if ( useMultisampledRTT === true ) {

				const multisampledRTTExt = this.extensions.get( 'WEBGL_multisampled_render_to_texture' );

				multisampledRTTExt.renderbufferStorageMultisampleEXT( gl.RENDERBUFFER, renderTarget.samples, glInternalFormat, width, height );

			} else if ( samples > 0 ) {

				if ( depthTexture && depthTexture.isDepthTexture ) {

					if ( depthTexture.type === gl.FLOAT ) {

						glInternalFormat = gl.DEPTH_COMPONENT32F;

					}

				}

				gl.renderbufferStorageMultisample( gl.RENDERBUFFER, samples, glInternalFormat, width, height );

			} else {

				gl.renderbufferStorage( gl.RENDERBUFFER, glInternalFormat, width, height );

			}

			gl.framebufferRenderbuffer( gl.FRAMEBUFFER, gl.DEPTH_ATTACHMENT, gl.RENDERBUFFER, renderbuffer );

		} else if ( depthBuffer && stencilBuffer ) {

			if ( samples > 0 ) {

				gl.renderbufferStorageMultisample( gl.RENDERBUFFER, samples, gl.DEPTH24_STENCIL8, width, height );

			} else {

				gl.renderbufferStorage( gl.RENDERBUFFER, gl.DEPTH_STENCIL, width, height );

			}


			gl.framebufferRenderbuffer( gl.FRAMEBUFFER, gl.DEPTH_STENCIL_ATTACHMENT, gl.RENDERBUFFER, renderbuffer );

		}

		gl.bindRenderbuffer( gl.RENDERBUFFER, null );

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

		const { backend, gl } = this;

		const { textureGPU, glFormat, glType } = this.backend.get( texture );

		const fb = gl.createFramebuffer();

		gl.bindFramebuffer( gl.READ_FRAMEBUFFER, fb );

		const target = texture.isCubeTexture ? gl.TEXTURE_CUBE_MAP_POSITIVE_X + faceIndex : gl.TEXTURE_2D;

		gl.framebufferTexture2D( gl.READ_FRAMEBUFFER, gl.COLOR_ATTACHMENT0, target, textureGPU, 0 );

		const typedArrayType = this._getTypedArrayType( glType );
		const bytesPerTexel = this._getBytesPerTexel( glType, glFormat );

		const elementCount = width * height;
		const byteLength = elementCount * bytesPerTexel;

		const buffer = gl.createBuffer();

		gl.bindBuffer( gl.PIXEL_PACK_BUFFER, buffer );
		gl.bufferData( gl.PIXEL_PACK_BUFFER, byteLength, gl.STREAM_READ );
		gl.readPixels( x, y, width, height, glFormat, glType, 0 );
		gl.bindBuffer( gl.PIXEL_PACK_BUFFER, null );

		await backend.utils._clientWaitAsync();

		const dstBuffer = new typedArrayType( byteLength / typedArrayType.BYTES_PER_ELEMENT );

		gl.bindBuffer( gl.PIXEL_PACK_BUFFER, buffer );
		gl.getBufferSubData( gl.PIXEL_PACK_BUFFER, 0, dstBuffer );
		gl.bindBuffer( gl.PIXEL_PACK_BUFFER, null );

		gl.deleteFramebuffer( fb );

		return dstBuffer;

	}

	/**
	 * Returns the corresponding typed array type for the given WebGL data type.
	 *
	 * @private
	 * @param {GLenum} glType - The WebGL data type.
	 * @return {TypedArray.constructor} The typed array type.
	 */
	_getTypedArrayType( glType ) {

		const { gl } = this;

		if ( glType === gl.UNSIGNED_BYTE ) return Uint8Array;

		if ( glType === gl.UNSIGNED_SHORT_4_4_4_4 ) return Uint16Array;
		if ( glType === gl.UNSIGNED_SHORT_5_5_5_1 ) return Uint16Array;
		if ( glType === gl.UNSIGNED_SHORT_5_6_5 ) return Uint16Array;
		if ( glType === gl.UNSIGNED_SHORT ) return Uint16Array;
		if ( glType === gl.UNSIGNED_INT ) return Uint32Array;

		if ( glType === gl.HALF_FLOAT ) return Uint16Array;
		if ( glType === gl.FLOAT ) return Float32Array;

		throw new Error( `Unsupported WebGL type: ${glType}` );

	}

	/**
	 * Returns the bytes-per-texel value for the given WebGL data type and texture format.
	 *
	 * @private
	 * @param {GLenum} glType - The WebGL data type.
	 * @param {GLenum} glFormat - The WebGL texture format.
	 * @return {number} The bytes-per-texel.
	 */
	_getBytesPerTexel( glType, glFormat ) {

		const { gl } = this;

		let bytesPerComponent = 0;

		if ( glType === gl.UNSIGNED_BYTE ) bytesPerComponent = 1;

		if ( glType === gl.UNSIGNED_SHORT_4_4_4_4 ||
			glType === gl.UNSIGNED_SHORT_5_5_5_1 ||
			glType === gl.UNSIGNED_SHORT_5_6_5 ||
			glType === gl.UNSIGNED_SHORT ||
			glType === gl.HALF_FLOAT ) bytesPerComponent = 2;

		if ( glType === gl.UNSIGNED_INT ||
			glType === gl.FLOAT ) bytesPerComponent = 4;

		if ( glFormat === gl.RGBA ) return bytesPerComponent * 4;
		if ( glFormat === gl.RGB ) return bytesPerComponent * 3;
		if ( glFormat === gl.ALPHA ) return bytesPerComponent;

	}

}
```
</details>

#### Methods

##### `_init(): void`

<details><summary>Code</summary>

```ts
_init() {

		const gl = this.gl;

		// Store only WebGL constants here.

		wrappingToGL = {
			[ RepeatWrapping ]: gl.REPEAT,
			[ ClampToEdgeWrapping ]: gl.CLAMP_TO_EDGE,
			[ MirroredRepeatWrapping ]: gl.MIRRORED_REPEAT
		};

		filterToGL = {
			[ NearestFilter ]: gl.NEAREST,
			[ NearestMipmapNearestFilter ]: gl.NEAREST_MIPMAP_NEAREST,
			[ NearestMipmapLinearFilter ]: gl.NEAREST_MIPMAP_LINEAR,

			[ LinearFilter ]: gl.LINEAR,
			[ LinearMipmapNearestFilter ]: gl.LINEAR_MIPMAP_NEAREST,
			[ LinearMipmapLinearFilter ]: gl.LINEAR_MIPMAP_LINEAR
		};

		compareToGL = {
			[ NeverCompare ]: gl.NEVER,
			[ AlwaysCompare ]: gl.ALWAYS,
			[ LessCompare ]: gl.LESS,
			[ LessEqualCompare ]: gl.LEQUAL,
			[ EqualCompare ]: gl.EQUAL,
			[ GreaterEqualCompare ]: gl.GEQUAL,
			[ GreaterCompare ]: gl.GREATER,
			[ NotEqualCompare ]: gl.NOTEQUAL
		};

	}
```
</details>

##### `getGLTextureType(texture: Texture): number`

<details><summary>Code</summary>

```ts
getGLTextureType( texture ) {

		const { gl } = this;

		let glTextureType;

		if ( texture.isCubeTexture === true ) {

			glTextureType = gl.TEXTURE_CUBE_MAP;

		} else if ( texture.isArrayTexture === true || texture.isDataArrayTexture === true || texture.isCompressedArrayTexture === true ) {

			glTextureType = gl.TEXTURE_2D_ARRAY;

		} else if ( texture.isData3DTexture === true ) { // TODO: isCompressed3DTexture, wait for #26642

			glTextureType = gl.TEXTURE_3D;

		} else {

			glTextureType = gl.TEXTURE_2D;


		}

		return glTextureType;

	}
```
</details>

##### `getInternalFormat(internalFormatName: string, glFormat: number, glType: number, colorSpace: string, forceLinearTransfer: boolean): number`

<details><summary>Code</summary>

```ts
getInternalFormat( internalFormatName, glFormat, glType, colorSpace, forceLinearTransfer = false ) {

		const { gl, extensions } = this;

		if ( internalFormatName !== null ) {

			if ( gl[ internalFormatName ] !== undefined ) return gl[ internalFormatName ];

			console.warn( 'THREE.WebGLRenderer: Attempt to use non-existing WebGL internal format \'' + internalFormatName + '\'' );

		}

		let internalFormat = glFormat;

		if ( glFormat === gl.RED ) {

			if ( glType === gl.FLOAT ) internalFormat = gl.R32F;
			if ( glType === gl.HALF_FLOAT ) internalFormat = gl.R16F;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.R8;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.R16;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.R32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.R8I;
			if ( glType === gl.SHORT ) internalFormat = gl.R16I;
			if ( glType === gl.INT ) internalFormat = gl.R32I;

		}

		if ( glFormat === gl.RED_INTEGER ) {

			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.R8UI;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.R16UI;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.R32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.R8I;
			if ( glType === gl.SHORT ) internalFormat = gl.R16I;
			if ( glType === gl.INT ) internalFormat = gl.R32I;

		}

		if ( glFormat === gl.RG ) {

			if ( glType === gl.FLOAT ) internalFormat = gl.RG32F;
			if ( glType === gl.HALF_FLOAT ) internalFormat = gl.RG16F;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RG8;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RG16;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RG32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RG8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RG16I;
			if ( glType === gl.INT ) internalFormat = gl.RG32I;

		}

		if ( glFormat === gl.RG_INTEGER ) {

			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RG8UI;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RG16UI;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RG32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RG8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RG16I;
			if ( glType === gl.INT ) internalFormat = gl.RG32I;

		}

		if ( glFormat === gl.RGB ) {

			const transfer = forceLinearTransfer ? LinearTransfer : ColorManagement.getTransfer( colorSpace );

			if ( glType === gl.FLOAT ) internalFormat = gl.RGB32F;
			if ( glType === gl.HALF_FLOAT ) internalFormat = gl.RGB16F;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RGB8;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RGB16;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RGB32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RGB8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RGB16I;
			if ( glType === gl.INT ) internalFormat = gl.RGB32I;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = ( transfer === SRGBTransfer ) ? gl.SRGB8 : gl.RGB8;
			if ( glType === gl.UNSIGNED_SHORT_5_6_5 ) internalFormat = gl.RGB565;
			if ( glType === gl.UNSIGNED_SHORT_5_5_5_1 ) internalFormat = gl.RGB5_A1;
			if ( glType === gl.UNSIGNED_SHORT_4_4_4_4 ) internalFormat = gl.RGB4;
			if ( glType === gl.UNSIGNED_INT_5_9_9_9_REV ) internalFormat = gl.RGB9_E5;

		}

		if ( glFormat === gl.RGB_INTEGER ) {

			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RGB8UI;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RGB16UI;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RGB32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RGB8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RGB16I;
			if ( glType === gl.INT ) internalFormat = gl.RGB32I;

		}

		if ( glFormat === gl.RGBA ) {

			const transfer = forceLinearTransfer ? LinearTransfer : ColorManagement.getTransfer( colorSpace );

			if ( glType === gl.FLOAT ) internalFormat = gl.RGBA32F;
			if ( glType === gl.HALF_FLOAT ) internalFormat = gl.RGBA16F;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RGBA8;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RGBA16;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RGBA32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RGBA8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RGBA16I;
			if ( glType === gl.INT ) internalFormat = gl.RGBA32I;
			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = ( transfer === SRGBTransfer ) ? gl.SRGB8_ALPHA8 : gl.RGBA8;
			if ( glType === gl.UNSIGNED_SHORT_4_4_4_4 ) internalFormat = gl.RGBA4;
			if ( glType === gl.UNSIGNED_SHORT_5_5_5_1 ) internalFormat = gl.RGB5_A1;

		}

		if ( glFormat === gl.RGBA_INTEGER ) {

			if ( glType === gl.UNSIGNED_BYTE ) internalFormat = gl.RGBA8UI;
			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.RGBA16UI;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.RGBA32UI;
			if ( glType === gl.BYTE ) internalFormat = gl.RGBA8I;
			if ( glType === gl.SHORT ) internalFormat = gl.RGBA16I;
			if ( glType === gl.INT ) internalFormat = gl.RGBA32I;

		}

		if ( glFormat === gl.DEPTH_COMPONENT ) {

			if ( glType === gl.UNSIGNED_SHORT ) internalFormat = gl.DEPTH_COMPONENT16;
			if ( glType === gl.UNSIGNED_INT ) internalFormat = gl.DEPTH_COMPONENT24;
			if ( glType === gl.FLOAT ) internalFormat = gl.DEPTH_COMPONENT32F;

		}

		if ( glFormat === gl.DEPTH_STENCIL ) {

			if ( glType === gl.UNSIGNED_INT_24_8 ) internalFormat = gl.DEPTH24_STENCIL8;

		}

		if ( internalFormat === gl.R16F || internalFormat === gl.R32F ||
			internalFormat === gl.RG16F || internalFormat === gl.RG32F ||
			internalFormat === gl.RGBA16F || internalFormat === gl.RGBA32F ) {

			extensions.get( 'EXT_color_buffer_float' );

		}

		return internalFormat;

	}
```
</details>

##### `setTextureParameters(textureType: number, texture: Texture): void`

<details><summary>Code</summary>

```ts
setTextureParameters( textureType, texture ) {

		const { gl, extensions, backend } = this;

		const workingPrimaries = ColorManagement.getPrimaries( ColorManagement.workingColorSpace );
		const texturePrimaries = texture.colorSpace === NoColorSpace ? null : ColorManagement.getPrimaries( texture.colorSpace );
		const unpackConversion = texture.colorSpace === NoColorSpace || workingPrimaries === texturePrimaries ? gl.NONE : gl.BROWSER_DEFAULT_WEBGL;

		gl.pixelStorei( gl.UNPACK_FLIP_Y_WEBGL, texture.flipY );
		gl.pixelStorei( gl.UNPACK_PREMULTIPLY_ALPHA_WEBGL, texture.premultiplyAlpha );
		gl.pixelStorei( gl.UNPACK_ALIGNMENT, texture.unpackAlignment );
		gl.pixelStorei( gl.UNPACK_COLORSPACE_CONVERSION_WEBGL, unpackConversion );

		gl.texParameteri( textureType, gl.TEXTURE_WRAP_S, wrappingToGL[ texture.wrapS ] );
		gl.texParameteri( textureType, gl.TEXTURE_WRAP_T, wrappingToGL[ texture.wrapT ] );

		if ( textureType === gl.TEXTURE_3D || textureType === gl.TEXTURE_2D_ARRAY ) {

			// WebGL 2 does not support wrapping for depth 2D array textures
			if ( ! texture.isArrayTexture ) {

				gl.texParameteri( textureType, gl.TEXTURE_WRAP_R, wrappingToGL[ texture.wrapR ] );

			}

		}

		gl.texParameteri( textureType, gl.TEXTURE_MAG_FILTER, filterToGL[ texture.magFilter ] );


		const hasMipmaps = texture.mipmaps !== undefined && texture.mipmaps.length > 0;

		// follow WebGPU backend mapping for texture filtering
		const minFilter = texture.minFilter === LinearFilter && hasMipmaps ? LinearMipmapLinearFilter : texture.minFilter;

		gl.texParameteri( textureType, gl.TEXTURE_MIN_FILTER, filterToGL[ minFilter ] );

		if ( texture.compareFunction ) {

			gl.texParameteri( textureType, gl.TEXTURE_COMPARE_MODE, gl.COMPARE_REF_TO_TEXTURE );
			gl.texParameteri( textureType, gl.TEXTURE_COMPARE_FUNC, compareToGL[ texture.compareFunction ] );

		}

		if ( extensions.has( 'EXT_texture_filter_anisotropic' ) === true ) {

			if ( texture.magFilter === NearestFilter ) return;
			if ( texture.minFilter !== NearestMipmapLinearFilter && texture.minFilter !== LinearMipmapLinearFilter ) return;
			if ( texture.type === FloatType && extensions.has( 'OES_texture_float_linear' ) === false ) return; // verify extension for WebGL 1 and WebGL 2

			if ( texture.anisotropy > 1 ) {

				const extension = extensions.get( 'EXT_texture_filter_anisotropic' );
				gl.texParameterf( textureType, extension.TEXTURE_MAX_ANISOTROPY_EXT, Math.min( texture.anisotropy, backend.getMaxAnisotropy() ) );

			}

		}

	}
```
</details>

##### `createDefaultTexture(texture: Texture): void`

<details><summary>Code</summary>

```ts
createDefaultTexture( texture ) {

		const { gl, backend, defaultTextures } = this;


		const glTextureType = this.getGLTextureType( texture );

		let textureGPU = defaultTextures[ glTextureType ];

		if ( textureGPU === undefined ) {

			textureGPU = gl.createTexture();

			backend.state.bindTexture( glTextureType, textureGPU );
			gl.texParameteri( glTextureType, gl.TEXTURE_MIN_FILTER, gl.NEAREST );
			gl.texParameteri( glTextureType, gl.TEXTURE_MAG_FILTER, gl.NEAREST );

			// gl.texImage2D( glTextureType, 0, gl.RGBA, 1, 1, 0, gl.RGBA, gl.UNSIGNED_BYTE, data );

			defaultTextures[ glTextureType ] = textureGPU;

		}

		backend.set( texture, {
			textureGPU,
			glTextureType,
			isDefault: true
		} );

	}
```
</details>

##### `createTexture(texture: Texture, options: any): undefined`

<details><summary>Code</summary>

```ts
createTexture( texture, options ) {

		const { gl, backend } = this;
		const { levels, width, height, depth } = options;

		const glFormat = backend.utils.convert( texture.format, texture.colorSpace );
		const glType = backend.utils.convert( texture.type );
		const glInternalFormat = this.getInternalFormat( texture.internalFormat, glFormat, glType, texture.colorSpace, texture.isVideoTexture );

		const textureGPU = gl.createTexture();
		const glTextureType = this.getGLTextureType( texture );

		backend.state.bindTexture( glTextureType, textureGPU );

		this.setTextureParameters( glTextureType, texture );

		if ( texture.isArrayTexture || texture.isDataArrayTexture || texture.isCompressedArrayTexture ) {

			gl.texStorage3D( gl.TEXTURE_2D_ARRAY, levels, glInternalFormat, width, height, depth );

		} else if ( texture.isData3DTexture ) {

			gl.texStorage3D( gl.TEXTURE_3D, levels, glInternalFormat, width, height, depth );

		} else if ( ! texture.isVideoTexture ) {

			gl.texStorage2D( glTextureType, levels, glInternalFormat, width, height );

		}

		backend.set( texture, {
			textureGPU,
			glTextureType,
			glFormat,
			glType,
			glInternalFormat
		} );

	}
```
</details>

##### `copyBufferToTexture(buffer: WebGLBuffer, texture: Texture): void`

<details><summary>Code</summary>

```ts
copyBufferToTexture( buffer, texture ) {

		const { gl, backend } = this;

		const { textureGPU, glTextureType, glFormat, glType } = backend.get( texture );

		const { width, height } = texture.source.data;

		gl.bindBuffer( gl.PIXEL_UNPACK_BUFFER, buffer );

		backend.state.bindTexture( glTextureType, textureGPU );

		gl.pixelStorei( gl.UNPACK_FLIP_Y_WEBGL, false );
		gl.pixelStorei( gl.UNPACK_PREMULTIPLY_ALPHA_WEBGL, false );
		gl.texSubImage2D( glTextureType, 0, 0, 0, width, height, glFormat, glType, 0 );

		gl.bindBuffer( gl.PIXEL_UNPACK_BUFFER, null );

		backend.state.unbindTexture();
		// debug
		// const framebuffer = gl.createFramebuffer();
		// gl.bindFramebuffer( gl.FRAMEBUFFER, framebuffer );
		// gl.framebufferTexture2D( gl.FRAMEBUFFER, gl.COLOR_ATTACHMENT0, glTextureType, textureGPU, 0 );

		// const readout = new Float32Array( width * height * 4 );

		// const altFormat = gl.getParameter( gl.IMPLEMENTATION_COLOR_READ_FORMAT );
		// const altType = gl.getParameter( gl.IMPLEMENTATION_COLOR_READ_TYPE );

		// gl.readPixels( 0, 0, width, height, altFormat, altType, readout );
		// gl.bindFramebuffer( gl.FRAMEBUFFER, null );
		// console.log( readout );

	}
```
</details>

##### `updateTexture(texture: Texture, options: any): void`

<details><summary>Code</summary>

```ts
updateTexture( texture, options ) {

		const { gl } = this;
		const { width, height } = options;
		const { textureGPU, glTextureType, glFormat, glType, glInternalFormat } = this.backend.get( texture );

		if ( texture.isRenderTargetTexture || ( textureGPU === undefined /* unsupported texture format */ ) )
			return;

		this.backend.state.bindTexture( glTextureType, textureGPU );

		this.setTextureParameters( glTextureType, texture );

		if ( texture.isCompressedTexture ) {

			const mipmaps = texture.mipmaps;
			const image = options.image;

			for ( let i = 0; i < mipmaps.length; i ++ ) {

				const mipmap = mipmaps[ i ];

				if ( texture.isCompressedArrayTexture ) {


					if ( texture.format !== gl.RGBA ) {

						if ( glFormat !== null ) {

							gl.compressedTexSubImage3D( gl.TEXTURE_2D_ARRAY, i, 0, 0, 0, mipmap.width, mipmap.height, image.depth, glFormat, mipmap.data );

						} else {

							console.warn( 'THREE.WebGLRenderer: Attempt to load unsupported compressed texture format in .uploadTexture()' );

						}

					} else {

						gl.texSubImage3D( gl.TEXTURE_2D_ARRAY, i, 0, 0, 0, mipmap.width, mipmap.height, image.depth, glFormat, glType, mipmap.data );

					}

				} else {

					if ( glFormat !== null ) {

						gl.compressedTexSubImage2D( gl.TEXTURE_2D, i, 0, 0, mipmap.width, mipmap.height, glFormat, mipmap.data );

					} else {

						console.warn( 'Unsupported compressed texture format' );

					}

				}

			}


		} else if ( texture.isCubeTexture ) {

			const images = options.images;

			for ( let i = 0; i < 6; i ++ ) {

				const image = getImage( images[ i ] );

				gl.texSubImage2D( gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, 0, 0, 0, width, height, glFormat, glType, image );

			}

		} else if ( texture.isDataArrayTexture || texture.isArrayTexture ) {

			const image = options.image;

			gl.texSubImage3D( gl.TEXTURE_2D_ARRAY, 0, 0, 0, 0, image.width, image.height, image.depth, glFormat, glType, image.data );

		} else if ( texture.isData3DTexture ) {

			const image = options.image;

			gl.texSubImage3D( gl.TEXTURE_3D, 0, 0, 0, 0, image.width, image.height, image.depth, glFormat, glType, image.data );

		} else if ( texture.isVideoTexture ) {

			texture.update();

			gl.texImage2D( glTextureType, 0, glInternalFormat, glFormat, glType, options.image );


		} else {

			const image = getImage( options.image );

			gl.texSubImage2D( glTextureType, 0, 0, 0, width, height, glFormat, glType, image );

		}

	}
```
</details>

##### `generateMipmaps(texture: Texture): void`

<details><summary>Code</summary>

```ts
generateMipmaps( texture ) {

		const { gl, backend } = this;
		const { textureGPU, glTextureType } = backend.get( texture );

		backend.state.bindTexture( glTextureType, textureGPU );
		gl.generateMipmap( glTextureType );

	}
```
</details>

##### `deallocateRenderBuffers(renderTarget: RenderTarget): void`

<details><summary>Code</summary>

```ts
deallocateRenderBuffers( renderTarget ) {

		const { gl, backend } = this;

		// remove framebuffer reference
		if ( renderTarget ) {

			const renderContextData = backend.get( renderTarget );

			renderContextData.renderBufferStorageSetup = undefined;

			if ( renderContextData.framebuffers ) {

				for ( const cacheKey in renderContextData.framebuffers ) {

					gl.deleteFramebuffer( renderContextData.framebuffers[ cacheKey ] );

				}

				delete renderContextData.framebuffers;

			}

			if ( renderContextData.depthRenderbuffer ) {

				gl.deleteRenderbuffer( renderContextData.depthRenderbuffer );
				delete renderContextData.depthRenderbuffer;

			}

			if ( renderContextData.stencilRenderbuffer ) {

				gl.deleteRenderbuffer( renderContextData.stencilRenderbuffer );
				delete renderContextData.stencilRenderbuffer;

			}

			if ( renderContextData.msaaFrameBuffer ) {

				gl.deleteFramebuffer( renderContextData.msaaFrameBuffer );
				delete renderContextData.msaaFrameBuffer;

			}

			if ( renderContextData.msaaRenderbuffers ) {

				for ( let i = 0; i < renderContextData.msaaRenderbuffers.length; i ++ ) {

					gl.deleteRenderbuffer( renderContextData.msaaRenderbuffers[ i ] );

				}

				delete renderContextData.msaaRenderbuffers;

			}

		}

	}
```
</details>

##### `destroyTexture(texture: Texture): void`

<details><summary>Code</summary>

```ts
destroyTexture( texture ) {

		const { gl, backend } = this;
		const { textureGPU, renderTarget } = backend.get( texture );

		this.deallocateRenderBuffers( renderTarget );
		gl.deleteTexture( textureGPU );

		backend.delete( texture );

	}
```
</details>

##### `copyTextureToTexture(srcTexture: Texture, dstTexture: Texture, srcRegion: any, dstPosition: any, srcLevel: number, dstLevel: number): void`

<details><summary>Code</summary>

```ts
copyTextureToTexture( srcTexture, dstTexture, srcRegion = null, dstPosition = null, srcLevel = 0, dstLevel = 0 ) {

		const { gl, backend } = this;
		const { state } = this.backend;

		const { textureGPU: dstTextureGPU, glTextureType, glType, glFormat } = backend.get( dstTexture );

		state.bindTexture( glTextureType, dstTextureGPU );

		// gather the necessary dimensions to copy
		let width, height, depth, minX, minY, minZ;
		let dstX, dstY, dstZ;
		const image = srcTexture.isCompressedTexture ? srcTexture.mipmaps[ dstLevel ] : srcTexture.image;

		if ( srcRegion !== null ) {

			width = srcRegion.max.x - srcRegion.min.x;
			height = srcRegion.max.y - srcRegion.min.y;
			depth = srcRegion.isBox3 ? srcRegion.max.z - srcRegion.min.z : 1;
			minX = srcRegion.min.x;
			minY = srcRegion.min.y;
			minZ = srcRegion.isBox3 ? srcRegion.min.z : 0;

		} else {

			const levelScale = Math.pow( 2, - srcLevel );
			width = Math.floor( image.width * levelScale );
			height = Math.floor( image.height * levelScale );

			if ( srcTexture.isDataArrayTexture || srcTexture.isArrayTexture ) {

				depth = image.depth;

			} else if ( srcTexture.isData3DTexture ) {

				depth = Math.floor( image.depth * levelScale );

			} else {

				depth = 1;

			}

			minX = 0;
			minY = 0;
			minZ = 0;

		}

		if ( dstPosition !== null ) {

			dstX = dstPosition.x;
			dstY = dstPosition.y;
			dstZ = dstPosition.z;

		} else {

			dstX = 0;
			dstY = 0;
			dstZ = 0;

		}


		gl.pixelStorei( gl.UNPACK_FLIP_Y_WEBGL, dstTexture.flipY );
		gl.pixelStorei( gl.UNPACK_PREMULTIPLY_ALPHA_WEBGL, dstTexture.premultiplyAlpha );
		gl.pixelStorei( gl.UNPACK_ALIGNMENT, dstTexture.unpackAlignment );

		// used for copying data from cpu
		const currentUnpackRowLen = gl.getParameter( gl.UNPACK_ROW_LENGTH );
		const currentUnpackImageHeight = gl.getParameter( gl.UNPACK_IMAGE_HEIGHT );
		const currentUnpackSkipPixels = gl.getParameter( gl.UNPACK_SKIP_PIXELS );
		const currentUnpackSkipRows = gl.getParameter( gl.UNPACK_SKIP_ROWS );
		const currentUnpackSkipImages = gl.getParameter( gl.UNPACK_SKIP_IMAGES );

		gl.pixelStorei( gl.UNPACK_ROW_LENGTH, image.width );
		gl.pixelStorei( gl.UNPACK_IMAGE_HEIGHT, image.height );
		gl.pixelStorei( gl.UNPACK_SKIP_PIXELS, minX );
		gl.pixelStorei( gl.UNPACK_SKIP_ROWS, minY );
		gl.pixelStorei( gl.UNPACK_SKIP_IMAGES, minZ );

		// set up the src texture
		const isDst3D = dstTexture.isDataArrayTexture || dstTexture.isData3DTexture || dstTexture.isArrayTexture;
		if ( srcTexture.isRenderTargetTexture || srcTexture.isDepthTexture ) {

			const srcTextureData = backend.get( srcTexture );
			const dstTextureData = backend.get( dstTexture );

			const srcRenderContextData = backend.get( srcTextureData.renderTarget );
			const dstRenderContextData = backend.get( dstTextureData.renderTarget );

			const srcFramebuffer = srcRenderContextData.framebuffers[ srcTextureData.cacheKey ];
			const dstFramebuffer = dstRenderContextData.framebuffers[ dstTextureData.cacheKey ];

			state.bindFramebuffer( gl.READ_FRAMEBUFFER, srcFramebuffer );
			state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, dstFramebuffer );

			let mask = gl.COLOR_BUFFER_BIT;

			if ( srcTexture.isDepthTexture ) mask = gl.DEPTH_BUFFER_BIT;

			gl.blitFramebuffer( minX, minY, width, height, dstX, dstY, width, height, mask, gl.NEAREST );

			state.bindFramebuffer( gl.READ_FRAMEBUFFER, null );
			state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, null );

		} else {

			if ( isDst3D ) {

				// copy data into the 3d texture
				if ( srcTexture.isDataTexture || srcTexture.isData3DTexture ) {

					gl.texSubImage3D( glTextureType, dstLevel, dstX, dstY, dstZ, width, height, depth, glFormat, glType, image.data );

				} else if ( dstTexture.isCompressedArrayTexture ) {

					gl.compressedTexSubImage3D( glTextureType, dstLevel, dstX, dstY, dstZ, width, height, depth, glFormat, image.data );

				} else {

					gl.texSubImage3D( glTextureType, dstLevel, dstX, dstY, dstZ, width, height, depth, glFormat, glType, image );

				}

			} else {

				// copy data into the 2d texture
				if ( srcTexture.isDataTexture ) {

					gl.texSubImage2D( glTextureType, dstLevel, dstX, dstY, width, height, glFormat, glType, image.data );

				} else if ( srcTexture.isCompressedTexture ) {

					gl.compressedTexSubImage2D( glTextureType, dstLevel, dstX, dstY, image.width, image.height, glFormat, image.data );

				} else {

					gl.texSubImage2D( glTextureType, dstLevel, dstX, dstY, width, height, glFormat, glType, image );

				}

			}

		}

		// reset values
		gl.pixelStorei( gl.UNPACK_ROW_LENGTH, currentUnpackRowLen );
		gl.pixelStorei( gl.UNPACK_IMAGE_HEIGHT, currentUnpackImageHeight );
		gl.pixelStorei( gl.UNPACK_SKIP_PIXELS, currentUnpackSkipPixels );
		gl.pixelStorei( gl.UNPACK_SKIP_ROWS, currentUnpackSkipRows );
		gl.pixelStorei( gl.UNPACK_SKIP_IMAGES, currentUnpackSkipImages );

		// Generate mipmaps only when copying level 0
		if ( dstLevel === 0 && dstTexture.generateMipmaps ) {

			gl.generateMipmap( glTextureType );

		}

		state.unbindTexture();

	}
```
</details>

##### `copyFramebufferToTexture(texture: Texture, renderContext: RenderContext, rectangle: Vector4): void`

<details><summary>Code</summary>

```ts
copyFramebufferToTexture( texture, renderContext, rectangle ) {

		const { gl } = this;
		const { state } = this.backend;

		const { textureGPU } = this.backend.get( texture );

		const { x, y, z: width, w: height } = rectangle;

		const requireDrawFrameBuffer = texture.isDepthTexture === true || ( renderContext.renderTarget && renderContext.renderTarget.samples > 0 );

		const srcHeight = renderContext.renderTarget ? renderContext.renderTarget.height : this.backend.getDrawingBufferSize().y;

		if ( requireDrawFrameBuffer ) {

			const partial = ( x !== 0 || y !== 0 );
			let mask;
			let attachment;

			if ( texture.isDepthTexture === true ) {

				mask = gl.DEPTH_BUFFER_BIT;
				attachment = gl.DEPTH_ATTACHMENT;

				if ( renderContext.stencil ) {

					mask |= gl.STENCIL_BUFFER_BIT;

				}

			} else {

				mask = gl.COLOR_BUFFER_BIT;
				attachment = gl.COLOR_ATTACHMENT0;

			}

			if ( partial ) {

				const renderTargetContextData = this.backend.get( renderContext.renderTarget );

				const fb = renderTargetContextData.framebuffers[ renderContext.getCacheKey() ];
				const msaaFrameBuffer = renderTargetContextData.msaaFrameBuffer;

				state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, fb );
				state.bindFramebuffer( gl.READ_FRAMEBUFFER, msaaFrameBuffer );

				const flippedY = srcHeight - y - height;

				gl.blitFramebuffer( x, flippedY, x + width, flippedY + height, x, flippedY, x + width, flippedY + height, mask, gl.NEAREST );

				state.bindFramebuffer( gl.READ_FRAMEBUFFER, fb );

				state.bindTexture( gl.TEXTURE_2D, textureGPU );

				gl.copyTexSubImage2D( gl.TEXTURE_2D, 0, 0, 0, x, flippedY, width, height );

				state.unbindTexture();

			} else {

				const fb = gl.createFramebuffer();

				state.bindFramebuffer( gl.DRAW_FRAMEBUFFER, fb );

				gl.framebufferTexture2D( gl.DRAW_FRAMEBUFFER, attachment, gl.TEXTURE_2D, textureGPU, 0 );
				gl.blitFramebuffer( 0, 0, width, height, 0, 0, width, height, mask, gl.NEAREST );

				gl.deleteFramebuffer( fb );

			}

		} else {

			state.bindTexture( gl.TEXTURE_2D, textureGPU );
			gl.copyTexSubImage2D( gl.TEXTURE_2D, 0, 0, 0, x, srcHeight - height - y, width, height );

			state.unbindTexture();

		}

		if ( texture.generateMipmaps ) this.generateMipmaps( texture );

		this.backend._setFramebuffer( renderContext );

	}
```
</details>

##### `setupRenderBufferStorage(renderbuffer: WebGLRenderbuffer, renderContext: RenderContext, samples: number, useMultisampledRTT: boolean): void`

<details><summary>Code</summary>

```ts
setupRenderBufferStorage( renderbuffer, renderContext, samples, useMultisampledRTT = false ) {

		const { gl } = this;
		const renderTarget = renderContext.renderTarget;

		const { depthTexture, depthBuffer, stencilBuffer, width, height } = renderTarget;

		gl.bindRenderbuffer( gl.RENDERBUFFER, renderbuffer );

		if ( depthBuffer && ! stencilBuffer ) {

			let glInternalFormat = gl.DEPTH_COMPONENT24;

			if ( useMultisampledRTT === true ) {

				const multisampledRTTExt = this.extensions.get( 'WEBGL_multisampled_render_to_texture' );

				multisampledRTTExt.renderbufferStorageMultisampleEXT( gl.RENDERBUFFER, renderTarget.samples, glInternalFormat, width, height );

			} else if ( samples > 0 ) {

				if ( depthTexture && depthTexture.isDepthTexture ) {

					if ( depthTexture.type === gl.FLOAT ) {

						glInternalFormat = gl.DEPTH_COMPONENT32F;

					}

				}

				gl.renderbufferStorageMultisample( gl.RENDERBUFFER, samples, glInternalFormat, width, height );

			} else {

				gl.renderbufferStorage( gl.RENDERBUFFER, glInternalFormat, width, height );

			}

			gl.framebufferRenderbuffer( gl.FRAMEBUFFER, gl.DEPTH_ATTACHMENT, gl.RENDERBUFFER, renderbuffer );

		} else if ( depthBuffer && stencilBuffer ) {

			if ( samples > 0 ) {

				gl.renderbufferStorageMultisample( gl.RENDERBUFFER, samples, gl.DEPTH24_STENCIL8, width, height );

			} else {

				gl.renderbufferStorage( gl.RENDERBUFFER, gl.DEPTH_STENCIL, width, height );

			}


			gl.framebufferRenderbuffer( gl.FRAMEBUFFER, gl.DEPTH_STENCIL_ATTACHMENT, gl.RENDERBUFFER, renderbuffer );

		}

		gl.bindRenderbuffer( gl.RENDERBUFFER, null );

	}
```
</details>

##### `copyTextureToBuffer(texture: Texture, x: number, y: number, width: number, height: number, faceIndex: number): Promise<TypedArray>`

<details><summary>Code</summary>

```ts
async copyTextureToBuffer( texture, x, y, width, height, faceIndex ) {

		const { backend, gl } = this;

		const { textureGPU, glFormat, glType } = this.backend.get( texture );

		const fb = gl.createFramebuffer();

		gl.bindFramebuffer( gl.READ_FRAMEBUFFER, fb );

		const target = texture.isCubeTexture ? gl.TEXTURE_CUBE_MAP_POSITIVE_X + faceIndex : gl.TEXTURE_2D;

		gl.framebufferTexture2D( gl.READ_FRAMEBUFFER, gl.COLOR_ATTACHMENT0, target, textureGPU, 0 );

		const typedArrayType = this._getTypedArrayType( glType );
		const bytesPerTexel = this._getBytesPerTexel( glType, glFormat );

		const elementCount = width * height;
		const byteLength = elementCount * bytesPerTexel;

		const buffer = gl.createBuffer();

		gl.bindBuffer( gl.PIXEL_PACK_BUFFER, buffer );
		gl.bufferData( gl.PIXEL_PACK_BUFFER, byteLength, gl.STREAM_READ );
		gl.readPixels( x, y, width, height, glFormat, glType, 0 );
		gl.bindBuffer( gl.PIXEL_PACK_BUFFER, null );

		await backend.utils._clientWaitAsync();

		const dstBuffer = new typedArrayType( byteLength / typedArrayType.BYTES_PER_ELEMENT );

		gl.bindBuffer( gl.PIXEL_PACK_BUFFER, buffer );
		gl.getBufferSubData( gl.PIXEL_PACK_BUFFER, 0, dstBuffer );
		gl.bindBuffer( gl.PIXEL_PACK_BUFFER, null );

		gl.deleteFramebuffer( fb );

		return dstBuffer;

	}
```
</details>

##### `_getTypedArrayType(glType: number): TypedArray.constructor`

<details><summary>Code</summary>

```ts
_getTypedArrayType( glType ) {

		const { gl } = this;

		if ( glType === gl.UNSIGNED_BYTE ) return Uint8Array;

		if ( glType === gl.UNSIGNED_SHORT_4_4_4_4 ) return Uint16Array;
		if ( glType === gl.UNSIGNED_SHORT_5_5_5_1 ) return Uint16Array;
		if ( glType === gl.UNSIGNED_SHORT_5_6_5 ) return Uint16Array;
		if ( glType === gl.UNSIGNED_SHORT ) return Uint16Array;
		if ( glType === gl.UNSIGNED_INT ) return Uint32Array;

		if ( glType === gl.HALF_FLOAT ) return Uint16Array;
		if ( glType === gl.FLOAT ) return Float32Array;

		throw new Error( `Unsupported WebGL type: ${glType}` );

	}
```
</details>

##### `_getBytesPerTexel(glType: number, glFormat: number): number`

<details><summary>Code</summary>

```ts
_getBytesPerTexel( glType, glFormat ) {

		const { gl } = this;

		let bytesPerComponent = 0;

		if ( glType === gl.UNSIGNED_BYTE ) bytesPerComponent = 1;

		if ( glType === gl.UNSIGNED_SHORT_4_4_4_4 ||
			glType === gl.UNSIGNED_SHORT_5_5_5_1 ||
			glType === gl.UNSIGNED_SHORT_5_6_5 ||
			glType === gl.UNSIGNED_SHORT ||
			glType === gl.HALF_FLOAT ) bytesPerComponent = 2;

		if ( glType === gl.UNSIGNED_INT ||
			glType === gl.FLOAT ) bytesPerComponent = 4;

		if ( glFormat === gl.RGBA ) return bytesPerComponent * 4;
		if ( glFormat === gl.RGB ) return bytesPerComponent * 3;
		if ( glFormat === gl.ALPHA ) return bytesPerComponent;

	}
```
</details>


---