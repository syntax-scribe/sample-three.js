[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLTextures.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 41 |
| 📦 Imports | 33 |
| 📊 Variables & Constants | 106 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLTextures.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LinearFilter` | `../../constants.js` |
| `LinearMipmapLinearFilter` | `../../constants.js` |
| `LinearMipmapNearestFilter` | `../../constants.js` |
| `NearestFilter` | `../../constants.js` |
| `NearestMipmapLinearFilter` | `../../constants.js` |
| `NearestMipmapNearestFilter` | `../../constants.js` |
| `RGBAFormat` | `../../constants.js` |
| `DepthFormat` | `../../constants.js` |
| `DepthStencilFormat` | `../../constants.js` |
| `UnsignedIntType` | `../../constants.js` |
| `FloatType` | `../../constants.js` |
| `MirroredRepeatWrapping` | `../../constants.js` |
| `ClampToEdgeWrapping` | `../../constants.js` |
| `RepeatWrapping` | `../../constants.js` |
| `UnsignedByteType` | `../../constants.js` |
| `NoColorSpace` | `../../constants.js` |
| `LinearSRGBColorSpace` | `../../constants.js` |
| `NeverCompare` | `../../constants.js` |
| `AlwaysCompare` | `../../constants.js` |
| `LessCompare` | `../../constants.js` |
| `LessEqualCompare` | `../../constants.js` |
| `EqualCompare` | `../../constants.js` |
| `GreaterEqualCompare` | `../../constants.js` |
| `GreaterCompare` | `../../constants.js` |
| `NotEqualCompare` | `../../constants.js` |
| `SRGBTransfer` | `../../constants.js` |
| `LinearTransfer` | `../../constants.js` |
| `UnsignedShortType` | `../../constants.js` |
| `UnsignedInt248Type` | `../../constants.js` |
| `createElementNS` | `../../utils.js` |
| `ColorManagement` | `../../math/ColorManagement.js` |
| `Vector2` | `../../math/Vector2.js` |
| `getByteLength` | `../../extras/TextureUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `multisampledRTTExt` | `any` | let/var | `extensions.has( 'WEBGL_multisampled_render_to_texture' ) ? extensions.get( 'W...` | ✗ |
| `supportsInvalidateFramebuffer` | `boolean` | let/var | `typeof navigator === 'undefined' ? false : /OculusBrowser/g.test( navigator.u...` | ✗ |
| `_imageDimensions` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `_videoTextures` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `_canvas` | `any` | let/var | `*not shown*` | ✗ |
| `_sources` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `useOffscreenCanvas` | `boolean` | let/var | `false` | ✗ |
| `scale` | `number` | let/var | `1` | ✗ |
| `canvas` | `any` | let/var | `needsNewCanvas ? createCanvas( width, height ) : _canvas` | ✗ |
| `internalFormat` | `any` | let/var | `glFormat` | ✗ |
| `transfer` | `any` | let/var | `forceLinearTransfer ? LinearTransfer : ColorManagement.getTransfer( colorSpace )` | ✗ |
| `glInternalFormat` | `any` | let/var | `*not shown*` | ✗ |
| `texture` | `any` | let/var | `event.target` | ✗ |
| `renderTarget` | `any` | let/var | `event.target` | ✗ |
| `source` | `any` | let/var | `texture.source` | ✗ |
| `webglTexture` | `any` | let/var | `webglTextures[ textureProperties.__cacheKey ]` | ✗ |
| `source` | `any` | let/var | `texture.source` | ✗ |
| `textures` | `any` | let/var | `renderTarget.textures` | ✗ |
| `textureUnits` | `number` | let/var | `0` | ✗ |
| `textureUnit` | `number` | let/var | `textureUnits` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `image` | `any` | let/var | `texture.image` | ✗ |
| `wrappingToGL` | `{ [x: number]: any; }` | let/var | `{ [ RepeatWrapping ]: _gl.REPEAT, [ ClampToEdgeWrapping ]: _gl.CLAMP_TO_EDGE,...` | ✗ |
| `filterToGL` | `{ [x: number]: any; }` | let/var | `{ [ NearestFilter ]: _gl.NEAREST, [ NearestMipmapNearestFilter ]: _gl.NEAREST...` | ✗ |
| `compareToGL` | `{ [x: number]: any; }` | let/var | `{ [ NeverCompare ]: _gl.NEVER, [ AlwaysCompare ]: _gl.ALWAYS, [ LessCompare ]...` | ✗ |
| `forceUpload` | `boolean` | let/var | `false` | ✗ |
| `source` | `any` | let/var | `texture.source` | ✗ |
| `webglTexture` | `any` | let/var | `webglTextures[ textureProperties.__cacheKey ]` | ✗ |
| `componentStride` | `4` | let/var | `4` | ✗ |
| `updateRanges` | `any` | let/var | `texture.updateRanges` | ✗ |
| `mergeIndex` | `number` | let/var | `0` | ✗ |
| `previousRange` | `any` | let/var | `updateRanges[ mergeIndex ]` | ✗ |
| `range` | `any` | let/var | `updateRanges[ i ]` | ✗ |
| `previousEnd` | `any` | let/var | `previousRange.start + previousRange.count` | ✗ |
| `range` | `any` | let/var | `updateRanges[ i ]` | ✗ |
| `x` | `number` | let/var | `pixelStart % image.width` | ✗ |
| `width` | `number` | let/var | `pixelCount` | ✗ |
| `height` | `1` | let/var | `1` | ✗ |
| `textureType` | `any` | let/var | `_gl.TEXTURE_2D` | ✗ |
| `source` | `any` | let/var | `texture.source` | ✗ |
| `texturePrimaries` | `any` | let/var | `texture.colorSpace === NoColorSpace ? null : ColorManagement.getPrimaries( te...` | ✗ |
| `unpackConversion` | `any` | let/var | `texture.colorSpace === NoColorSpace \|\| workingPrimaries === texturePrimarie...` | ✗ |
| `mipmap` | `any` | let/var | `*not shown*` | ✗ |
| `mipmaps` | `any` | let/var | `texture.mipmaps` | ✗ |
| `useTexStorage` | `boolean` | let/var | `( texture.isVideoTexture !== true )` | ✗ |
| `allocateMemory` | `boolean` | let/var | `( sourceProperties.__version === undefined ) \|\| ( forceUpload === true )` | ✗ |
| `dataReady` | `any` | let/var | `source.dataReady` | ✗ |
| `width` | `any` | let/var | `image.width` | ✗ |
| `height` | `any` | let/var | `image.height` | ✗ |
| `source` | `any` | let/var | `texture.source` | ✗ |
| `texturePrimaries` | `any` | let/var | `texture.colorSpace === NoColorSpace ? null : ColorManagement.getPrimaries( te...` | ✗ |
| `unpackConversion` | `any` | let/var | `texture.colorSpace === NoColorSpace \|\| workingPrimaries === texturePrimarie...` | ✗ |
| `isCompressed` | `any` | let/var | `( texture.isCompressedTexture \|\| texture.image[ 0 ].isCompressedTexture )` | ✗ |
| `isDataTexture` | `any` | let/var | `( texture.image[ 0 ] && texture.image[ 0 ].isDataTexture )` | ✗ |
| `cubeImage` | `any[]` | let/var | `[]` | ✗ |
| `image` | `any` | let/var | `cubeImage[ 0 ]` | ✗ |
| `useTexStorage` | `boolean` | let/var | `( texture.isVideoTexture !== true )` | ✗ |
| `allocateMemory` | `boolean` | let/var | `( sourceProperties.__version === undefined ) \|\| ( forceUpload === true )` | ✗ |
| `dataReady` | `any` | let/var | `source.dataReady` | ✗ |
| `mipmaps` | `any` | let/var | `*not shown*` | ✗ |
| `mipmap` | `any` | let/var | `mipmaps[ j ]` | ✗ |
| `mipmap` | `any` | let/var | `mipmaps[ j ]` | ✗ |
| `mipmapImage` | `any` | let/var | `mipmap.image[ i ].image` | ✗ |
| `mipmap` | `any` | let/var | `mipmaps[ j ]` | ✗ |
| `depthTexture` | `any` | let/var | `renderTarget.depthTexture` | ✗ |
| `depthType` | `any` | let/var | `depthTexture && depthTexture.isDepthTexture ? depthTexture.type : null` | ✗ |
| `glAttachmentType` | `any` | let/var | `renderTarget.stencilBuffer ? _gl.DEPTH_STENCIL_ATTACHMENT : _gl.DEPTH_ATTACHMENT` | ✗ |
| `textures` | `any` | let/var | `renderTarget.textures` | ✗ |
| `texture` | `any` | let/var | `textures[ i ]` | ✗ |
| `isCube` | `any` | let/var | `( renderTarget && renderTarget.isWebGLCubeRenderTarget )` | ✗ |
| `webglDepthTexture` | `any` | let/var | `textureProperties.__webglTexture` | ✗ |
| `isCube` | `boolean` | let/var | `( renderTarget.isWebGLCubeRenderTarget === true )` | ✗ |
| `depthTexture` | `any` | let/var | `renderTarget.depthTexture` | ✗ |
| `mipmaps` | `any` | let/var | `renderTarget.texture.mipmaps` | ✗ |
| `glAttachmentType` | `any` | let/var | `renderTarget.stencilBuffer ? _gl.DEPTH_STENCIL_ATTACHMENT : _gl.DEPTH_ATTACHMENT` | ✗ |
| `renderbuffer` | `any` | let/var | `renderTargetProperties.__webglDepthbuffer[ i ]` | ✗ |
| `mipmaps` | `any` | let/var | `renderTarget.texture.mipmaps` | ✗ |
| `glAttachmentType` | `any` | let/var | `renderTarget.stencilBuffer ? _gl.DEPTH_STENCIL_ATTACHMENT : _gl.DEPTH_ATTACHMENT` | ✗ |
| `renderbuffer` | `any` | let/var | `renderTargetProperties.__webglDepthbuffer` | ✗ |
| `texture` | `any` | let/var | `renderTarget.texture` | ✗ |
| `textures` | `any` | let/var | `renderTarget.textures` | ✗ |
| `isCube` | `boolean` | let/var | `( renderTarget.isWebGLCubeRenderTarget === true )` | ✗ |
| `isMultipleRenderTargets` | `boolean` | let/var | `( textures.length > 1 )` | ✗ |
| `texture` | `any` | let/var | `textures[ i ]` | ✗ |
| `attachment` | `any` | let/var | `textures[ i ]` | ✗ |
| `glTextureType` | `any` | let/var | `_gl.TEXTURE_2D` | ✗ |
| `glTextureType` | `any` | let/var | `_gl.TEXTURE_2D` | ✗ |
| `textures` | `any` | let/var | `renderTarget.textures` | ✗ |
| `texture` | `any` | let/var | `textures[ i ]` | ✗ |
| `webglTexture` | `any` | let/var | `properties.get( texture ).__webglTexture` | ✗ |
| `invalidationArrayRead` | `any[]` | let/var | `[]` | ✗ |
| `invalidationArrayDraw` | `any[]` | let/var | `[]` | ✗ |
| `textures` | `any` | let/var | `renderTarget.textures` | ✗ |
| `width` | `any` | let/var | `renderTarget.width` | ✗ |
| `height` | `any` | let/var | `renderTarget.height` | ✗ |
| `mask` | `any` | let/var | `_gl.COLOR_BUFFER_BIT` | ✗ |
| `depthStyle` | `any` | let/var | `renderTarget.stencilBuffer ? _gl.DEPTH_STENCIL_ATTACHMENT : _gl.DEPTH_ATTACHMENT` | ✗ |
| `isMultipleRenderTargets` | `boolean` | let/var | `( textures.length > 1 )` | ✗ |
| `mipmaps` | `any` | let/var | `renderTarget.texture.mipmaps` | ✗ |
| `webglTexture` | `any` | let/var | `properties.get( textures[ i ] ).__webglTexture` | ✗ |
| `webglTexture` | `any` | let/var | `properties.get( textures[ i ] ).__webglTexture` | ✗ |
| `depthStyle` | `any` | let/var | `renderTarget.stencilBuffer ? _gl.DEPTH_STENCIL_ATTACHMENT : _gl.DEPTH_ATTACHMENT` | ✗ |
| `frame` | `any` | let/var | `info.render.frame` | ✗ |
| `colorSpace` | `any` | let/var | `texture.colorSpace` | ✗ |
| `format` | `any` | let/var | `texture.format` | ✗ |
| `type` | `any` | let/var | `texture.type` | ✗ |


---

## Functions

### `WebGLTextures(_gl: any, extensions: any, state: any, properties: any, capabilities: any, utils: any, info: any): void`

**Parameters:**

- **`_gl`** `any`
- **`extensions`** `any`
- **`state`** `any`
- **`properties`** `any`
- **`capabilities`** `any`
- **`utils`** `any`
- **`info`** `any`

**Returns:** `void`

**Calls:**

- `extensions.has`
- `extensions.get`
- `/OculusBrowser/g.test`
- `new OffscreenCanvas( 1, 1 ).getContext`
- `createElementNS (from ../../utils.js)`
- `getDimensions`
- `Math.max`
- `Math.floor`
- `createCanvas`
- `canvas.getContext`
- `context.drawImage`
- `console.warn`
- `_gl.generateMipmap`
- `ColorManagement.getTransfer`
- `textureNeedsGenerateMipmaps`
- `Math.log2`
- `Array.isArray`
- `texture.removeEventListener`
- `deallocateTexture`
- `_videoTextures.delete`
- `renderTarget.removeEventListener`
- `deallocateRenderTarget`
- `properties.get`
- `_sources.get`
- `deleteTexture`
- `Object.keys`
- `_sources.delete`
- `properties.remove`
- `_gl.deleteTexture`
- `renderTarget.depthTexture.dispose`
- `_gl.deleteFramebuffer`
- `_gl.deleteRenderbuffer`
- `array.push`
- `array.join`
- `updateVideoTexture`
- `uploadTexture`
- `state.bindTexture`
- `uploadCubeTexture`
- `_gl.texParameteri`
- `_gl.texParameterf`
- `Math.min`
- `capabilities.getMaxAnisotropy`
- `texture.addEventListener`
- `_sources.set`
- `getTextureCacheKey`
- `_gl.createTexture`
- `state.texSubImage2D`
- `updateRanges.sort`
- `getRow`
- `_gl.getParameter`
- `_gl.pixelStorei`
- `Math.ceil`
- `texture.clearUpdateRanges`
- `initTexture`
- `state.activeTexture`
- `ColorManagement.getPrimaries`
- `resizeImage`
- `verifyColorSpace`
- `utils.convert`
- `getInternalFormat`
- `setTextureParameters`
- `getMipLevels`
- `getInternalDepthFormat`
- `state.texStorage2D`
- `state.texImage2D`
- `updateTexture`
- `state.texStorage3D`
- `getByteLength (from ../../extras/TextureUtils.js)`
- `mipmap.data.subarray`
- `state.compressedTexSubImage3D`
- `texture.clearLayerUpdates`
- `state.compressedTexImage3D`
- `state.texSubImage3D`
- `state.texImage3D`
- `state.compressedTexSubImage2D`
- `state.compressedTexImage2D`
- `image.data.subarray`
- `generateMipmap`
- `texture.onUpdate`
- `state.bindFramebuffer`
- `useMultisampledRTT`
- `multisampledRTTExt.framebufferTexture2DMultisampleEXT`
- `getRenderTargetSamples`
- `_gl.framebufferTexture2D`
- `_gl.bindRenderbuffer`
- `multisampledRTTExt.renderbufferStorageMultisampleEXT`
- `_gl.renderbufferStorageMultisample`
- `_gl.renderbufferStorage`
- `_gl.framebufferRenderbuffer`
- `setTexture2D`
- `renderTargetProperties.__depthDisposeCallback`
- `depthTexture.removeEventListener`
- `depthTexture.addEventListener`
- `setupDepthTexture`
- `_gl.createRenderbuffer`
- `setupRenderBufferStorage`
- `setupFrameBufferTexture`
- `setupDepthRenderbuffer`
- `renderTarget.addEventListener`
- `_gl.createFramebuffer`
- `state.unbindTexture`
- `getTargetType`
- `_gl.blitFramebuffer`
- `invalidationArrayRead.push`
- `invalidationArrayDraw.push`
- `_gl.invalidateFramebuffer`
- `_videoTextures.get`
- `_videoTextures.set`
- `texture.update`
- `console.error`

**Internal Comments:**
```
// cordova iOS (as of 5.0) still uses UIWebView, which provides OffscreenCanvas, (x2)
// also OffscreenCanvas.getContext("webgl"), but not OffscreenCanvas.getContext("2d")! (x2)
// Some implementations may only implement OffscreenCanvas partially (e.g. lacking 2d). (x2)
// eslint-disable-next-line compat/compat (x2)
// Use OffscreenCanvas when available. Specially needed in web workers
// handle case if texture exceeds max size
// only perform resize if necessary
// only perform resize for certain image types
// cube textures can't reuse the same canvas (x2)
// user-defined mipmaps
// texture without mipmaps (only base level)
// (x14)
// check if it's necessary to remove the WebGLTexture object (x2)
// the WebGLTexture object is not used anymore, remove it
// remove the weak map entry if no WebGLTexture uses the source anymore
// create Source <-> WebGLTextures mapping if necessary (x2)
// check if there is already a WebGLTexture object for the given texture parameters (x2)
// if not, create a new instance of WebGLTexture
// create new entry (x4)
// when a new instance of WebGLTexture was created, a texture upload is required (x3)
// even if the image contents are identical (x3)
// every time the texture cache key changes, it's necessary to check if an instance of (x2)
// WebGLTexture can be deleted in order to avoid a memory leak. (x2)
// store references to cache key and WebGLTexture object (x4)
// Before applying update ranges, we merge any adjacent / overlapping (x4)
// ranges to reduce load on `gl.texSubImage2D`. Empirically, this has led (x4)
// to performance improvements for applications which make heavy use of (x4)
// update ranges. Likely due to GPU command overhead. (x4)
// Note that to reduce garbage collection between frames, we merge the (x4)
// update ranges in-place. This is safe because this method will clear the (x4)
// update ranges once updated. (x4)
// To merge the update ranges in-place, we work from left to right in the (x2)
// existing updateRanges array, merging ranges. This may result in a final (x2)
// array which is smaller than the original. This index tracks the last (x2)
// index representing a merged range, any data after this index can be (x2)
// trimmed once the merge algorithm is completed. (x2)
// Only merge if in the same row and overlapping/adjacent (x2)
// We add one here to merge adjacent ranges. This is safe because ranges
// operate over positive integers.
// Trim the array to only contain the merged ranges. (x4)
// Assumes update ranges refer to contiguous memory (x2)
// use manually created mipmaps if available (x2)
// if there are no manual mipmaps (x2)
// set 0 level mipmap and then use GL to generate other mipmap levels (x2)
// regular Texture (image, video, canvas)
// TODO: Uniformly handle mipmap definitions
// Normal textures and compressed cube textures define base level + mips with their mipmap array
// Uncompressed cube textures use their mipmap array only for mips (no base level)
// We assume images for cube map have the same size. (x3)
// Render targets
// Setup storage for target texture and bind it to correct framebuffer
// Setup storage for internal depth/stencil buffers and bind to correct framebuffer
// retrieve the depth attachment types (x2)
// set up the attachment (x2)
// Setup resources for a Depth Texture for a FBO (needs an extension)
// upload an empty depth texture with framebuffer size
// Setup GL resources for a non-texture depth buffer
// if the bound depth texture has changed
// fire the dispose event to get rid of stored state associated with the previously bound depth buffer (x2)
// set up dispose listeners to track when the currently attached buffer is implicitly unbound
// attach buffer if it's been created already (x4)
// rebind framebuffer with external textures
// Set up GL resources for the render target
// Setup framebuffer
// Setup color buffer
// Setup depth and stencil buffers
// If MRT we need to remove FBO attachments
// resolving stencil is slow with a D3D backend. disable it for all transmission render targets (see #27799)
// If MRT since pre-blit we removed the FBO we need to reconstruct the attachments
// Check the last frame we updated the VideoTexture
// sRGB
// in WebGL 2 uncompressed textures can only be sRGB encoded if they have the RGBA8 format
// if intrinsic data are not available, fallback to width/height (x4)
```

<details><summary>Code</summary>

```typescript
function WebGLTextures( _gl, extensions, state, properties, capabilities, utils, info ) {

	const multisampledRTTExt = extensions.has( 'WEBGL_multisampled_render_to_texture' ) ? extensions.get( 'WEBGL_multisampled_render_to_texture' ) : null;
	const supportsInvalidateFramebuffer = typeof navigator === 'undefined' ? false : /OculusBrowser/g.test( navigator.userAgent );

	const _imageDimensions = new Vector2();
	const _videoTextures = new WeakMap();
	let _canvas;

	const _sources = new WeakMap(); // maps WebglTexture objects to instances of Source

	// cordova iOS (as of 5.0) still uses UIWebView, which provides OffscreenCanvas,
	// also OffscreenCanvas.getContext("webgl"), but not OffscreenCanvas.getContext("2d")!
	// Some implementations may only implement OffscreenCanvas partially (e.g. lacking 2d).

	let useOffscreenCanvas = false;

	try {

		useOffscreenCanvas = typeof OffscreenCanvas !== 'undefined'
			// eslint-disable-next-line compat/compat
			&& ( new OffscreenCanvas( 1, 1 ).getContext( '2d' ) ) !== null;

	} catch ( err ) {

		// Ignore any errors

	}

	function createCanvas( width, height ) {

		// Use OffscreenCanvas when available. Specially needed in web workers

		return useOffscreenCanvas ?
			// eslint-disable-next-line compat/compat
			new OffscreenCanvas( width, height ) : createElementNS( 'canvas' );

	}

	function resizeImage( image, needsNewCanvas, maxSize ) {

		let scale = 1;

		const dimensions = getDimensions( image );

		// handle case if texture exceeds max size

		if ( dimensions.width > maxSize || dimensions.height > maxSize ) {

			scale = maxSize / Math.max( dimensions.width, dimensions.height );

		}

		// only perform resize if necessary

		if ( scale < 1 ) {

			// only perform resize for certain image types

			if ( ( typeof HTMLImageElement !== 'undefined' && image instanceof HTMLImageElement ) ||
				( typeof HTMLCanvasElement !== 'undefined' && image instanceof HTMLCanvasElement ) ||
				( typeof ImageBitmap !== 'undefined' && image instanceof ImageBitmap ) ||
				( typeof VideoFrame !== 'undefined' && image instanceof VideoFrame ) ) {

				const width = Math.floor( scale * dimensions.width );
				const height = Math.floor( scale * dimensions.height );

				if ( _canvas === undefined ) _canvas = createCanvas( width, height );

				// cube textures can't reuse the same canvas

				const canvas = needsNewCanvas ? createCanvas( width, height ) : _canvas;

				canvas.width = width;
				canvas.height = height;

				const context = canvas.getContext( '2d' );
				context.drawImage( image, 0, 0, width, height );

				console.warn( 'THREE.WebGLRenderer: Texture has been resized from (' + dimensions.width + 'x' + dimensions.height + ') to (' + width + 'x' + height + ').' );

				return canvas;

			} else {

				if ( 'data' in image ) {

					console.warn( 'THREE.WebGLRenderer: Image in DataTexture is too big (' + dimensions.width + 'x' + dimensions.height + ').' );

				}

				return image;

			}

		}

		return image;

	}

	function textureNeedsGenerateMipmaps( texture ) {

		return texture.generateMipmaps;

	}

	function generateMipmap( target ) {

		_gl.generateMipmap( target );

	}

	function getTargetType( texture ) {

		if ( texture.isWebGLCubeRenderTarget ) return _gl.TEXTURE_CUBE_MAP;
		if ( texture.isWebGL3DRenderTarget ) return _gl.TEXTURE_3D;
		if ( texture.isWebGLArrayRenderTarget || texture.isCompressedArrayTexture ) return _gl.TEXTURE_2D_ARRAY;
		return _gl.TEXTURE_2D;

	}

	function getInternalFormat( internalFormatName, glFormat, glType, colorSpace, forceLinearTransfer = false ) {

		if ( internalFormatName !== null ) {

			if ( _gl[ internalFormatName ] !== undefined ) return _gl[ internalFormatName ];

			console.warn( 'THREE.WebGLRenderer: Attempt to use non-existing WebGL internal format \'' + internalFormatName + '\'' );

		}

		let internalFormat = glFormat;

		if ( glFormat === _gl.RED ) {

			if ( glType === _gl.FLOAT ) internalFormat = _gl.R32F;
			if ( glType === _gl.HALF_FLOAT ) internalFormat = _gl.R16F;
			if ( glType === _gl.UNSIGNED_BYTE ) internalFormat = _gl.R8;

		}

		if ( glFormat === _gl.RED_INTEGER ) {

			if ( glType === _gl.UNSIGNED_BYTE ) internalFormat = _gl.R8UI;
			if ( glType === _gl.UNSIGNED_SHORT ) internalFormat = _gl.R16UI;
			if ( glType === _gl.UNSIGNED_INT ) internalFormat = _gl.R32UI;
			if ( glType === _gl.BYTE ) internalFormat = _gl.R8I;
			if ( glType === _gl.SHORT ) internalFormat = _gl.R16I;
			if ( glType === _gl.INT ) internalFormat = _gl.R32I;

		}

		if ( glFormat === _gl.RG ) {

			if ( glType === _gl.FLOAT ) internalFormat = _gl.RG32F;
			if ( glType === _gl.HALF_FLOAT ) internalFormat = _gl.RG16F;
			if ( glType === _gl.UNSIGNED_BYTE ) internalFormat = _gl.RG8;

		}

		if ( glFormat === _gl.RG_INTEGER ) {

			if ( glType === _gl.UNSIGNED_BYTE ) internalFormat = _gl.RG8UI;
			if ( glType === _gl.UNSIGNED_SHORT ) internalFormat = _gl.RG16UI;
			if ( glType === _gl.UNSIGNED_INT ) internalFormat = _gl.RG32UI;
			if ( glType === _gl.BYTE ) internalFormat = _gl.RG8I;
			if ( glType === _gl.SHORT ) internalFormat = _gl.RG16I;
			if ( glType === _gl.INT ) internalFormat = _gl.RG32I;

		}

		if ( glFormat === _gl.RGB_INTEGER ) {

			if ( glType === _gl.UNSIGNED_BYTE ) internalFormat = _gl.RGB8UI;
			if ( glType === _gl.UNSIGNED_SHORT ) internalFormat = _gl.RGB16UI;
			if ( glType === _gl.UNSIGNED_INT ) internalFormat = _gl.RGB32UI;
			if ( glType === _gl.BYTE ) internalFormat = _gl.RGB8I;
			if ( glType === _gl.SHORT ) internalFormat = _gl.RGB16I;
			if ( glType === _gl.INT ) internalFormat = _gl.RGB32I;

		}

		if ( glFormat === _gl.RGBA_INTEGER ) {

			if ( glType === _gl.UNSIGNED_BYTE ) internalFormat = _gl.RGBA8UI;
			if ( glType === _gl.UNSIGNED_SHORT ) internalFormat = _gl.RGBA16UI;
			if ( glType === _gl.UNSIGNED_INT ) internalFormat = _gl.RGBA32UI;
			if ( glType === _gl.BYTE ) internalFormat = _gl.RGBA8I;
			if ( glType === _gl.SHORT ) internalFormat = _gl.RGBA16I;
			if ( glType === _gl.INT ) internalFormat = _gl.RGBA32I;

		}

		if ( glFormat === _gl.RGB ) {

			if ( glType === _gl.UNSIGNED_INT_5_9_9_9_REV ) internalFormat = _gl.RGB9_E5;

		}

		if ( glFormat === _gl.RGBA ) {

			const transfer = forceLinearTransfer ? LinearTransfer : ColorManagement.getTransfer( colorSpace );

			if ( glType === _gl.FLOAT ) internalFormat = _gl.RGBA32F;
			if ( glType === _gl.HALF_FLOAT ) internalFormat = _gl.RGBA16F;
			if ( glType === _gl.UNSIGNED_BYTE ) internalFormat = ( transfer === SRGBTransfer ) ? _gl.SRGB8_ALPHA8 : _gl.RGBA8;
			if ( glType === _gl.UNSIGNED_SHORT_4_4_4_4 ) internalFormat = _gl.RGBA4;
			if ( glType === _gl.UNSIGNED_SHORT_5_5_5_1 ) internalFormat = _gl.RGB5_A1;

		}

		if ( internalFormat === _gl.R16F || internalFormat === _gl.R32F ||
			internalFormat === _gl.RG16F || internalFormat === _gl.RG32F ||
			internalFormat === _gl.RGBA16F || internalFormat === _gl.RGBA32F ) {

			extensions.get( 'EXT_color_buffer_float' );

		}

		return internalFormat;

	}

	function getInternalDepthFormat( useStencil, depthType ) {

		let glInternalFormat;
		if ( useStencil ) {

			if ( depthType === null || depthType === UnsignedIntType || depthType === UnsignedInt248Type ) {

				glInternalFormat = _gl.DEPTH24_STENCIL8;

			} else if ( depthType === FloatType ) {

				glInternalFormat = _gl.DEPTH32F_STENCIL8;

			} else if ( depthType === UnsignedShortType ) {

				glInternalFormat = _gl.DEPTH24_STENCIL8;
				console.warn( 'DepthTexture: 16 bit depth attachment is not supported with stencil. Using 24-bit attachment.' );

			}

		} else {

			if ( depthType === null || depthType === UnsignedIntType || depthType === UnsignedInt248Type ) {

				glInternalFormat = _gl.DEPTH_COMPONENT24;

			} else if ( depthType === FloatType ) {

				glInternalFormat = _gl.DEPTH_COMPONENT32F;

			} else if ( depthType === UnsignedShortType ) {

				glInternalFormat = _gl.DEPTH_COMPONENT16;

			}

		}

		return glInternalFormat;

	}

	function getMipLevels( texture, image ) {

		if ( textureNeedsGenerateMipmaps( texture ) === true || ( texture.isFramebufferTexture && texture.minFilter !== NearestFilter && texture.minFilter !== LinearFilter ) ) {

			return Math.log2( Math.max( image.width, image.height ) ) + 1;

		} else if ( texture.mipmaps !== undefined && texture.mipmaps.length > 0 ) {

			// user-defined mipmaps

			return texture.mipmaps.length;

		} else if ( texture.isCompressedTexture && Array.isArray( texture.image ) ) {

			return image.mipmaps.length;

		} else {

			// texture without mipmaps (only base level)

			return 1;

		}

	}

	//

	function onTextureDispose( event ) {

		const texture = event.target;

		texture.removeEventListener( 'dispose', onTextureDispose );

		deallocateTexture( texture );

		if ( texture.isVideoTexture ) {

			_videoTextures.delete( texture );

		}

	}

	function onRenderTargetDispose( event ) {

		const renderTarget = event.target;

		renderTarget.removeEventListener( 'dispose', onRenderTargetDispose );

		deallocateRenderTarget( renderTarget );

	}

	//

	function deallocateTexture( texture ) {

		const textureProperties = properties.get( texture );

		if ( textureProperties.__webglInit === undefined ) return;

		// check if it's necessary to remove the WebGLTexture object

		const source = texture.source;
		const webglTextures = _sources.get( source );

		if ( webglTextures ) {

			const webglTexture = webglTextures[ textureProperties.__cacheKey ];
			webglTexture.usedTimes --;

			// the WebGLTexture object is not used anymore, remove it

			if ( webglTexture.usedTimes === 0 ) {

				deleteTexture( texture );

			}

			// remove the weak map entry if no WebGLTexture uses the source anymore

			if ( Object.keys( webglTextures ).length === 0 ) {

				_sources.delete( source );

			}

		}

		properties.remove( texture );

	}

	function deleteTexture( texture ) {

		const textureProperties = properties.get( texture );
		_gl.deleteTexture( textureProperties.__webglTexture );

		const source = texture.source;
		const webglTextures = _sources.get( source );
		delete webglTextures[ textureProperties.__cacheKey ];

		info.memory.textures --;

	}

	function deallocateRenderTarget( renderTarget ) {

		const renderTargetProperties = properties.get( renderTarget );

		if ( renderTarget.depthTexture ) {

			renderTarget.depthTexture.dispose();

			properties.remove( renderTarget.depthTexture );

		}

		if ( renderTarget.isWebGLCubeRenderTarget ) {

			for ( let i = 0; i < 6; i ++ ) {

				if ( Array.isArray( renderTargetProperties.__webglFramebuffer[ i ] ) ) {

					for ( let level = 0; level < renderTargetProperties.__webglFramebuffer[ i ].length; level ++ ) _gl.deleteFramebuffer( renderTargetProperties.__webglFramebuffer[ i ][ level ] );

				} else {

					_gl.deleteFramebuffer( renderTargetProperties.__webglFramebuffer[ i ] );

				}

				if ( renderTargetProperties.__webglDepthbuffer ) _gl.deleteRenderbuffer( renderTargetProperties.__webglDepthbuffer[ i ] );

			}

		} else {

			if ( Array.isArray( renderTargetProperties.__webglFramebuffer ) ) {

				for ( let level = 0; level < renderTargetProperties.__webglFramebuffer.length; level ++ ) _gl.deleteFramebuffer( renderTargetProperties.__webglFramebuffer[ level ] );

			} else {

				_gl.deleteFramebuffer( renderTargetProperties.__webglFramebuffer );

			}

			if ( renderTargetProperties.__webglDepthbuffer ) _gl.deleteRenderbuffer( renderTargetProperties.__webglDepthbuffer );
			if ( renderTargetProperties.__webglMultisampledFramebuffer ) _gl.deleteFramebuffer( renderTargetProperties.__webglMultisampledFramebuffer );

			if ( renderTargetProperties.__webglColorRenderbuffer ) {

				for ( let i = 0; i < renderTargetProperties.__webglColorRenderbuffer.length; i ++ ) {

					if ( renderTargetProperties.__webglColorRenderbuffer[ i ] ) _gl.deleteRenderbuffer( renderTargetProperties.__webglColorRenderbuffer[ i ] );

				}

			}

			if ( renderTargetProperties.__webglDepthRenderbuffer ) _gl.deleteRenderbuffer( renderTargetProperties.__webglDepthRenderbuffer );

		}

		const textures = renderTarget.textures;

		for ( let i = 0, il = textures.length; i < il; i ++ ) {

			const attachmentProperties = properties.get( textures[ i ] );

			if ( attachmentProperties.__webglTexture ) {

				_gl.deleteTexture( attachmentProperties.__webglTexture );

				info.memory.textures --;

			}

			properties.remove( textures[ i ] );

		}

		properties.remove( renderTarget );

	}

	//

	let textureUnits = 0;

	function resetTextureUnits() {

		textureUnits = 0;

	}

	function allocateTextureUnit() {

		const textureUnit = textureUnits;

		if ( textureUnit >= capabilities.maxTextures ) {

			console.warn( 'THREE.WebGLTextures: Trying to use ' + textureUnit + ' texture units while this GPU supports only ' + capabilities.maxTextures );

		}

		textureUnits += 1;

		return textureUnit;

	}

	function getTextureCacheKey( texture ) {

		const array = [];

		array.push( texture.wrapS );
		array.push( texture.wrapT );
		array.push( texture.wrapR || 0 );
		array.push( texture.magFilter );
		array.push( texture.minFilter );
		array.push( texture.anisotropy );
		array.push( texture.internalFormat );
		array.push( texture.format );
		array.push( texture.type );
		array.push( texture.generateMipmaps );
		array.push( texture.premultiplyAlpha );
		array.push( texture.flipY );
		array.push( texture.unpackAlignment );
		array.push( texture.colorSpace );

		return array.join();

	}

	//

	function setTexture2D( texture, slot ) {

		const textureProperties = properties.get( texture );

		if ( texture.isVideoTexture ) updateVideoTexture( texture );

		if ( texture.isRenderTargetTexture === false && texture.isExternalTexture !== true && texture.version > 0 && textureProperties.__version !== texture.version ) {

			const image = texture.image;

			if ( image === null ) {

				console.warn( 'THREE.WebGLRenderer: Texture marked for update but no image data found.' );

			} else if ( image.complete === false ) {

				console.warn( 'THREE.WebGLRenderer: Texture marked for update but image is incomplete' );

			} else {

				uploadTexture( textureProperties, texture, slot );
				return;

			}

		} else if ( texture.isExternalTexture ) {

			textureProperties.__webglTexture = texture.sourceTexture ? texture.sourceTexture : null;

		}

		state.bindTexture( _gl.TEXTURE_2D, textureProperties.__webglTexture, _gl.TEXTURE0 + slot );

	}

	function setTexture2DArray( texture, slot ) {

		const textureProperties = properties.get( texture );

		if ( texture.isRenderTargetTexture === false && texture.version > 0 && textureProperties.__version !== texture.version ) {

			uploadTexture( textureProperties, texture, slot );
			return;

		}

		state.bindTexture( _gl.TEXTURE_2D_ARRAY, textureProperties.__webglTexture, _gl.TEXTURE0 + slot );

	}

	function setTexture3D( texture, slot ) {

		const textureProperties = properties.get( texture );

		if ( texture.isRenderTargetTexture === false && texture.version > 0 && textureProperties.__version !== texture.version ) {

			uploadTexture( textureProperties, texture, slot );
			return;

		}

		state.bindTexture( _gl.TEXTURE_3D, textureProperties.__webglTexture, _gl.TEXTURE0 + slot );

	}

	function setTextureCube( texture, slot ) {

		const textureProperties = properties.get( texture );

		if ( texture.version > 0 && textureProperties.__version !== texture.version ) {

			uploadCubeTexture( textureProperties, texture, slot );
			return;

		}

		state.bindTexture( _gl.TEXTURE_CUBE_MAP, textureProperties.__webglTexture, _gl.TEXTURE0 + slot );

	}

	const wrappingToGL = {
		[ RepeatWrapping ]: _gl.REPEAT,
		[ ClampToEdgeWrapping ]: _gl.CLAMP_TO_EDGE,
		[ MirroredRepeatWrapping ]: _gl.MIRRORED_REPEAT
	};

	const filterToGL = {
		[ NearestFilter ]: _gl.NEAREST,
		[ NearestMipmapNearestFilter ]: _gl.NEAREST_MIPMAP_NEAREST,
		[ NearestMipmapLinearFilter ]: _gl.NEAREST_MIPMAP_LINEAR,

		[ LinearFilter ]: _gl.LINEAR,
		[ LinearMipmapNearestFilter ]: _gl.LINEAR_MIPMAP_NEAREST,
		[ LinearMipmapLinearFilter ]: _gl.LINEAR_MIPMAP_LINEAR
	};

	const compareToGL = {
		[ NeverCompare ]: _gl.NEVER,
		[ AlwaysCompare ]: _gl.ALWAYS,
		[ LessCompare ]: _gl.LESS,
		[ LessEqualCompare ]: _gl.LEQUAL,
		[ EqualCompare ]: _gl.EQUAL,
		[ GreaterEqualCompare ]: _gl.GEQUAL,
		[ GreaterCompare ]: _gl.GREATER,
		[ NotEqualCompare ]: _gl.NOTEQUAL
	};

	function setTextureParameters( textureType, texture ) {

		if ( texture.type === FloatType && extensions.has( 'OES_texture_float_linear' ) === false &&
			( texture.magFilter === LinearFilter || texture.magFilter === LinearMipmapNearestFilter || texture.magFilter === NearestMipmapLinearFilter || texture.magFilter === LinearMipmapLinearFilter ||
			texture.minFilter === LinearFilter || texture.minFilter === LinearMipmapNearestFilter || texture.minFilter === NearestMipmapLinearFilter || texture.minFilter === LinearMipmapLinearFilter ) ) {

			console.warn( 'THREE.WebGLRenderer: Unable to use linear filtering with floating point textures. OES_texture_float_linear not supported on this device.' );

		}

		_gl.texParameteri( textureType, _gl.TEXTURE_WRAP_S, wrappingToGL[ texture.wrapS ] );
		_gl.texParameteri( textureType, _gl.TEXTURE_WRAP_T, wrappingToGL[ texture.wrapT ] );

		if ( textureType === _gl.TEXTURE_3D || textureType === _gl.TEXTURE_2D_ARRAY ) {

			_gl.texParameteri( textureType, _gl.TEXTURE_WRAP_R, wrappingToGL[ texture.wrapR ] );

		}

		_gl.texParameteri( textureType, _gl.TEXTURE_MAG_FILTER, filterToGL[ texture.magFilter ] );
		_gl.texParameteri( textureType, _gl.TEXTURE_MIN_FILTER, filterToGL[ texture.minFilter ] );

		if ( texture.compareFunction ) {

			_gl.texParameteri( textureType, _gl.TEXTURE_COMPARE_MODE, _gl.COMPARE_REF_TO_TEXTURE );
			_gl.texParameteri( textureType, _gl.TEXTURE_COMPARE_FUNC, compareToGL[ texture.compareFunction ] );

		}

		if ( extensions.has( 'EXT_texture_filter_anisotropic' ) === true ) {

			if ( texture.magFilter === NearestFilter ) return;
			if ( texture.minFilter !== NearestMipmapLinearFilter && texture.minFilter !== LinearMipmapLinearFilter ) return;
			if ( texture.type === FloatType && extensions.has( 'OES_texture_float_linear' ) === false ) return; // verify extension

			if ( texture.anisotropy > 1 || properties.get( texture ).__currentAnisotropy ) {

				const extension = extensions.get( 'EXT_texture_filter_anisotropic' );
				_gl.texParameterf( textureType, extension.TEXTURE_MAX_ANISOTROPY_EXT, Math.min( texture.anisotropy, capabilities.getMaxAnisotropy() ) );
				properties.get( texture ).__currentAnisotropy = texture.anisotropy;

			}

		}

	}

	function initTexture( textureProperties, texture ) {

		let forceUpload = false;

		if ( textureProperties.__webglInit === undefined ) {

			textureProperties.__webglInit = true;

			texture.addEventListener( 'dispose', onTextureDispose );

		}

		// create Source <-> WebGLTextures mapping if necessary

		const source = texture.source;
		let webglTextures = _sources.get( source );

		if ( webglTextures === undefined ) {

			webglTextures = {};
			_sources.set( source, webglTextures );

		}

		// check if there is already a WebGLTexture object for the given texture parameters

		const textureCacheKey = getTextureCacheKey( texture );

		if ( textureCacheKey !== textureProperties.__cacheKey ) {

			// if not, create a new instance of WebGLTexture

			if ( webglTextures[ textureCacheKey ] === undefined ) {

				// create new entry

				webglTextures[ textureCacheKey ] = {
					texture: _gl.createTexture(),
					usedTimes: 0
				};

				info.memory.textures ++;

				// when a new instance of WebGLTexture was created, a texture upload is required
				// even if the image contents are identical

				forceUpload = true;

			}

			webglTextures[ textureCacheKey ].usedTimes ++;

			// every time the texture cache key changes, it's necessary to check if an instance of
			// WebGLTexture can be deleted in order to avoid a memory leak.

			const webglTexture = webglTextures[ textureProperties.__cacheKey ];

			if ( webglTexture !== undefined ) {

				webglTextures[ textureProperties.__cacheKey ].usedTimes --;

				if ( webglTexture.usedTimes === 0 ) {

					deleteTexture( texture );

				}

			}

			// store references to cache key and WebGLTexture object

			textureProperties.__cacheKey = textureCacheKey;
			textureProperties.__webglTexture = webglTextures[ textureCacheKey ].texture;

		}

		return forceUpload;

	}

	function getRow( index, rowLength, componentStride ) {

		return Math.floor( Math.floor( index / componentStride ) / rowLength );

	}

	function updateTexture( texture, image, glFormat, glType ) {

		const componentStride = 4; // only RGBA supported

		const updateRanges = texture.updateRanges;

		if ( updateRanges.length === 0 ) {

			state.texSubImage2D( _gl.TEXTURE_2D, 0, 0, 0, image.width, image.height, glFormat, glType, image.data );

		} else {

			// Before applying update ranges, we merge any adjacent / overlapping
			// ranges to reduce load on `gl.texSubImage2D`. Empirically, this has led
			// to performance improvements for applications which make heavy use of
			// update ranges. Likely due to GPU command overhead.
			//
			// Note that to reduce garbage collection between frames, we merge the
			// update ranges in-place. This is safe because this method will clear the
			// update ranges once updated.

			updateRanges.sort( ( a, b ) => a.start - b.start );

			// To merge the update ranges in-place, we work from left to right in the
			// existing updateRanges array, merging ranges. This may result in a final
			// array which is smaller than the original. This index tracks the last
			// index representing a merged range, any data after this index can be
			// trimmed once the merge algorithm is completed.
			let mergeIndex = 0;

			for ( let i = 1; i < updateRanges.length; i ++ ) {

				const previousRange = updateRanges[ mergeIndex ];
				const range = updateRanges[ i ];

				// Only merge if in the same row and overlapping/adjacent
				const previousEnd = previousRange.start + previousRange.count;
				const currentRow = getRow( range.start, image.width, componentStride );
				const previousRow = getRow( previousRange.start, image.width, componentStride );

				// We add one here to merge adjacent ranges. This is safe because ranges
				// operate over positive integers.
				if (
					range.start <= previousEnd + 1 &&
					currentRow === previousRow &&
					getRow( range.start + range.count - 1, image.width, componentStride ) === currentRow // ensure range doesn't spill
				) {

					previousRange.count = Math.max(
						previousRange.count,
						range.start + range.count - previousRange.start
					);

				} else {

					++ mergeIndex;
					updateRanges[ mergeIndex ] = range;

				}


			}

			// Trim the array to only contain the merged ranges.
			updateRanges.length = mergeIndex + 1;

			const currentUnpackRowLen = _gl.getParameter( _gl.UNPACK_ROW_LENGTH );
			const currentUnpackSkipPixels = _gl.getParameter( _gl.UNPACK_SKIP_PIXELS );
			const currentUnpackSkipRows = _gl.getParameter( _gl.UNPACK_SKIP_ROWS );

			_gl.pixelStorei( _gl.UNPACK_ROW_LENGTH, image.width );

			for ( let i = 0, l = updateRanges.length; i < l; i ++ ) {

				const range = updateRanges[ i ];

				const pixelStart = Math.floor( range.start / componentStride );
				const pixelCount = Math.ceil( range.count / componentStride );

				const x = pixelStart % image.width;
				const y = Math.floor( pixelStart / image.width );

				// Assumes update ranges refer to contiguous memory
				const width = pixelCount;
				const height = 1;

				_gl.pixelStorei( _gl.UNPACK_SKIP_PIXELS, x );
				_gl.pixelStorei( _gl.UNPACK_SKIP_ROWS, y );

				state.texSubImage2D( _gl.TEXTURE_2D, 0, x, y, width, height, glFormat, glType, image.data );

			}

			texture.clearUpdateRanges();

			_gl.pixelStorei( _gl.UNPACK_ROW_LENGTH, currentUnpackRowLen );
			_gl.pixelStorei( _gl.UNPACK_SKIP_PIXELS, currentUnpackSkipPixels );
			_gl.pixelStorei( _gl.UNPACK_SKIP_ROWS, currentUnpackSkipRows );

		}

	}

	function uploadTexture( textureProperties, texture, slot ) {

		let textureType = _gl.TEXTURE_2D;

		if ( texture.isDataArrayTexture || texture.isCompressedArrayTexture ) textureType = _gl.TEXTURE_2D_ARRAY;
		if ( texture.isData3DTexture ) textureType = _gl.TEXTURE_3D;

		const forceUpload = initTexture( textureProperties, texture );
		const source = texture.source;

		state.bindTexture( textureType, textureProperties.__webglTexture, _gl.TEXTURE0 + slot );

		const sourceProperties = properties.get( source );

		if ( source.version !== sourceProperties.__version || forceUpload === true ) {

			state.activeTexture( _gl.TEXTURE0 + slot );

			const workingPrimaries = ColorManagement.getPrimaries( ColorManagement.workingColorSpace );
			const texturePrimaries = texture.colorSpace === NoColorSpace ? null : ColorManagement.getPrimaries( texture.colorSpace );
			const unpackConversion = texture.colorSpace === NoColorSpace || workingPrimaries === texturePrimaries ? _gl.NONE : _gl.BROWSER_DEFAULT_WEBGL;

			_gl.pixelStorei( _gl.UNPACK_FLIP_Y_WEBGL, texture.flipY );
			_gl.pixelStorei( _gl.UNPACK_PREMULTIPLY_ALPHA_WEBGL, texture.premultiplyAlpha );
			_gl.pixelStorei( _gl.UNPACK_ALIGNMENT, texture.unpackAlignment );
			_gl.pixelStorei( _gl.UNPACK_COLORSPACE_CONVERSION_WEBGL, unpackConversion );

			let image = resizeImage( texture.image, false, capabilities.maxTextureSize );
			image = verifyColorSpace( texture, image );

			const glFormat = utils.convert( texture.format, texture.colorSpace );

			const glType = utils.convert( texture.type );
			let glInternalFormat = getInternalFormat( texture.internalFormat, glFormat, glType, texture.colorSpace, texture.isVideoTexture );

			setTextureParameters( textureType, texture );

			let mipmap;
			const mipmaps = texture.mipmaps;

			const useTexStorage = ( texture.isVideoTexture !== true );
			const allocateMemory = ( sourceProperties.__version === undefined ) || ( forceUpload === true );
			const dataReady = source.dataReady;
			const levels = getMipLevels( texture, image );

			if ( texture.isDepthTexture ) {

				glInternalFormat = getInternalDepthFormat( texture.format === DepthStencilFormat, texture.type );

				//

				if ( allocateMemory ) {

					if ( useTexStorage ) {

						state.texStorage2D( _gl.TEXTURE_2D, 1, glInternalFormat, image.width, image.height );

					} else {

						state.texImage2D( _gl.TEXTURE_2D, 0, glInternalFormat, image.width, image.height, 0, glFormat, glType, null );

					}

				}

			} else if ( texture.isDataTexture ) {

				// use manually created mipmaps if available
				// if there are no manual mipmaps
				// set 0 level mipmap and then use GL to generate other mipmap levels

				if ( mipmaps.length > 0 ) {

					if ( useTexStorage && allocateMemory ) {

						state.texStorage2D( _gl.TEXTURE_2D, levels, glInternalFormat, mipmaps[ 0 ].width, mipmaps[ 0 ].height );

					}

					for ( let i = 0, il = mipmaps.length; i < il; i ++ ) {

						mipmap = mipmaps[ i ];

						if ( useTexStorage ) {

							if ( dataReady ) {

								state.texSubImage2D( _gl.TEXTURE_2D, i, 0, 0, mipmap.width, mipmap.height, glFormat, glType, mipmap.data );

							}

						} else {

							state.texImage2D( _gl.TEXTURE_2D, i, glInternalFormat, mipmap.width, mipmap.height, 0, glFormat, glType, mipmap.data );

						}

					}

					texture.generateMipmaps = false;

				} else {

					if ( useTexStorage ) {

						if ( allocateMemory ) {

							state.texStorage2D( _gl.TEXTURE_2D, levels, glInternalFormat, image.width, image.height );

						}

						if ( dataReady ) {

							updateTexture( texture, image, glFormat, glType );

						}

					} else {

						state.texImage2D( _gl.TEXTURE_2D, 0, glInternalFormat, image.width, image.height, 0, glFormat, glType, image.data );

					}

				}

			} else if ( texture.isCompressedTexture ) {

				if ( texture.isCompressedArrayTexture ) {

					if ( useTexStorage && allocateMemory ) {

						state.texStorage3D( _gl.TEXTURE_2D_ARRAY, levels, glInternalFormat, mipmaps[ 0 ].width, mipmaps[ 0 ].height, image.depth );

					}

					for ( let i = 0, il = mipmaps.length; i < il; i ++ ) {

						mipmap = mipmaps[ i ];

						if ( texture.format !== RGBAFormat ) {

							if ( glFormat !== null ) {

								if ( useTexStorage ) {

									if ( dataReady ) {

										if ( texture.layerUpdates.size > 0 ) {

											const layerByteLength = getByteLength( mipmap.width, mipmap.height, texture.format, texture.type );

											for ( const layerIndex of texture.layerUpdates ) {

												const layerData = mipmap.data.subarray(
													layerIndex * layerByteLength / mipmap.data.BYTES_PER_ELEMENT,
													( layerIndex + 1 ) * layerByteLength / mipmap.data.BYTES_PER_ELEMENT
												);
												state.compressedTexSubImage3D( _gl.TEXTURE_2D_ARRAY, i, 0, 0, layerIndex, mipmap.width, mipmap.height, 1, glFormat, layerData );

											}

											texture.clearLayerUpdates();

										} else {

											state.compressedTexSubImage3D( _gl.TEXTURE_2D_ARRAY, i, 0, 0, 0, mipmap.width, mipmap.height, image.depth, glFormat, mipmap.data );

										}

									}

								} else {

									state.compressedTexImage3D( _gl.TEXTURE_2D_ARRAY, i, glInternalFormat, mipmap.width, mipmap.height, image.depth, 0, mipmap.data, 0, 0 );

								}

							} else {

								console.warn( 'THREE.WebGLRenderer: Attempt to load unsupported compressed texture format in .uploadTexture()' );

							}

						} else {

							if ( useTexStorage ) {

								if ( dataReady ) {

									state.texSubImage3D( _gl.TEXTURE_2D_ARRAY, i, 0, 0, 0, mipmap.width, mipmap.height, image.depth, glFormat, glType, mipmap.data );

								}

							} else {

								state.texImage3D( _gl.TEXTURE_2D_ARRAY, i, glInternalFormat, mipmap.width, mipmap.height, image.depth, 0, glFormat, glType, mipmap.data );

							}

						}

					}

				} else {

					if ( useTexStorage && allocateMemory ) {

						state.texStorage2D( _gl.TEXTURE_2D, levels, glInternalFormat, mipmaps[ 0 ].width, mipmaps[ 0 ].height );

					}

					for ( let i = 0, il = mipmaps.length; i < il; i ++ ) {

						mipmap = mipmaps[ i ];

						if ( texture.format !== RGBAFormat ) {

							if ( glFormat !== null ) {

								if ( useTexStorage ) {

									if ( dataReady ) {

										state.compressedTexSubImage2D( _gl.TEXTURE_2D, i, 0, 0, mipmap.width, mipmap.height, glFormat, mipmap.data );

									}

								} else {

									state.compressedTexImage2D( _gl.TEXTURE_2D, i, glInternalFormat, mipmap.width, mipmap.height, 0, mipmap.data );

								}

							} else {

								console.warn( 'THREE.WebGLRenderer: Attempt to load unsupported compressed texture format in .uploadTexture()' );

							}

						} else {

							if ( useTexStorage ) {

								if ( dataReady ) {

									state.texSubImage2D( _gl.TEXTURE_2D, i, 0, 0, mipmap.width, mipmap.height, glFormat, glType, mipmap.data );

								}

							} else {

								state.texImage2D( _gl.TEXTURE_2D, i, glInternalFormat, mipmap.width, mipmap.height, 0, glFormat, glType, mipmap.data );

							}

						}

					}

				}

			} else if ( texture.isDataArrayTexture ) {

				if ( useTexStorage ) {

					if ( allocateMemory ) {

						state.texStorage3D( _gl.TEXTURE_2D_ARRAY, levels, glInternalFormat, image.width, image.height, image.depth );

					}

					if ( dataReady ) {

						if ( texture.layerUpdates.size > 0 ) {

							const layerByteLength = getByteLength( image.width, image.height, texture.format, texture.type );

							for ( const layerIndex of texture.layerUpdates ) {

								const layerData = image.data.subarray(
									layerIndex * layerByteLength / image.data.BYTES_PER_ELEMENT,
									( layerIndex + 1 ) * layerByteLength / image.data.BYTES_PER_ELEMENT
								);
								state.texSubImage3D( _gl.TEXTURE_2D_ARRAY, 0, 0, 0, layerIndex, image.width, image.height, 1, glFormat, glType, layerData );

							}

							texture.clearLayerUpdates();

						} else {

							state.texSubImage3D( _gl.TEXTURE_2D_ARRAY, 0, 0, 0, 0, image.width, image.height, image.depth, glFormat, glType, image.data );

						}

					}

				} else {

					state.texImage3D( _gl.TEXTURE_2D_ARRAY, 0, glInternalFormat, image.width, image.height, image.depth, 0, glFormat, glType, image.data );

				}

			} else if ( texture.isData3DTexture ) {

				if ( useTexStorage ) {

					if ( allocateMemory ) {

						state.texStorage3D( _gl.TEXTURE_3D, levels, glInternalFormat, image.width, image.height, image.depth );

					}

					if ( dataReady ) {

						state.texSubImage3D( _gl.TEXTURE_3D, 0, 0, 0, 0, image.width, image.height, image.depth, glFormat, glType, image.data );

					}

				} else {

					state.texImage3D( _gl.TEXTURE_3D, 0, glInternalFormat, image.width, image.height, image.depth, 0, glFormat, glType, image.data );

				}

			} else if ( texture.isFramebufferTexture ) {

				if ( allocateMemory ) {

					if ( useTexStorage ) {

						state.texStorage2D( _gl.TEXTURE_2D, levels, glInternalFormat, image.width, image.height );

					} else {

						let width = image.width, height = image.height;

						for ( let i = 0; i < levels; i ++ ) {

							state.texImage2D( _gl.TEXTURE_2D, i, glInternalFormat, width, height, 0, glFormat, glType, null );

							width >>= 1;
							height >>= 1;

						}

					}

				}

			} else {

				// regular Texture (image, video, canvas)

				// use manually created mipmaps if available
				// if there are no manual mipmaps
				// set 0 level mipmap and then use GL to generate other mipmap levels

				if ( mipmaps.length > 0 ) {

					if ( useTexStorage && allocateMemory ) {

						const dimensions = getDimensions( mipmaps[ 0 ] );

						state.texStorage2D( _gl.TEXTURE_2D, levels, glInternalFormat, dimensions.width, dimensions.height );

					}

					for ( let i = 0, il = mipmaps.length; i < il; i ++ ) {

						mipmap = mipmaps[ i ];

						if ( useTexStorage ) {

							if ( dataReady ) {

								state.texSubImage2D( _gl.TEXTURE_2D, i, 0, 0, glFormat, glType, mipmap );

							}

						} else {

							state.texImage2D( _gl.TEXTURE_2D, i, glInternalFormat, glFormat, glType, mipmap );

						}

					}

					texture.generateMipmaps = false;

				} else {

					if ( useTexStorage ) {

						if ( allocateMemory ) {

							const dimensions = getDimensions( image );

							state.texStorage2D( _gl.TEXTURE_2D, levels, glInternalFormat, dimensions.width, dimensions.height );

						}

						if ( dataReady ) {

							state.texSubImage2D( _gl.TEXTURE_2D, 0, 0, 0, glFormat, glType, image );

						}

					} else {

						state.texImage2D( _gl.TEXTURE_2D, 0, glInternalFormat, glFormat, glType, image );

					}

				}

			}

			if ( textureNeedsGenerateMipmaps( texture ) ) {

				generateMipmap( textureType );

			}

			sourceProperties.__version = source.version;

			if ( texture.onUpdate ) texture.onUpdate( texture );

		}

		textureProperties.__version = texture.version;

	}

	function uploadCubeTexture( textureProperties, texture, slot ) {

		if ( texture.image.length !== 6 ) return;

		const forceUpload = initTexture( textureProperties, texture );
		const source = texture.source;

		state.bindTexture( _gl.TEXTURE_CUBE_MAP, textureProperties.__webglTexture, _gl.TEXTURE0 + slot );

		const sourceProperties = properties.get( source );

		if ( source.version !== sourceProperties.__version || forceUpload === true ) {

			state.activeTexture( _gl.TEXTURE0 + slot );

			const workingPrimaries = ColorManagement.getPrimaries( ColorManagement.workingColorSpace );
			const texturePrimaries = texture.colorSpace === NoColorSpace ? null : ColorManagement.getPrimaries( texture.colorSpace );
			const unpackConversion = texture.colorSpace === NoColorSpace || workingPrimaries === texturePrimaries ? _gl.NONE : _gl.BROWSER_DEFAULT_WEBGL;

			_gl.pixelStorei( _gl.UNPACK_FLIP_Y_WEBGL, texture.flipY );
			_gl.pixelStorei( _gl.UNPACK_PREMULTIPLY_ALPHA_WEBGL, texture.premultiplyAlpha );
			_gl.pixelStorei( _gl.UNPACK_ALIGNMENT, texture.unpackAlignment );
			_gl.pixelStorei( _gl.UNPACK_COLORSPACE_CONVERSION_WEBGL, unpackConversion );

			const isCompressed = ( texture.isCompressedTexture || texture.image[ 0 ].isCompressedTexture );
			const isDataTexture = ( texture.image[ 0 ] && texture.image[ 0 ].isDataTexture );

			const cubeImage = [];

			for ( let i = 0; i < 6; i ++ ) {

				if ( ! isCompressed && ! isDataTexture ) {

					cubeImage[ i ] = resizeImage( texture.image[ i ], true, capabilities.maxCubemapSize );

				} else {

					cubeImage[ i ] = isDataTexture ? texture.image[ i ].image : texture.image[ i ];

				}

				cubeImage[ i ] = verifyColorSpace( texture, cubeImage[ i ] );

			}

			const image = cubeImage[ 0 ],
				glFormat = utils.convert( texture.format, texture.colorSpace ),
				glType = utils.convert( texture.type ),
				glInternalFormat = getInternalFormat( texture.internalFormat, glFormat, glType, texture.colorSpace );

			const useTexStorage = ( texture.isVideoTexture !== true );
			const allocateMemory = ( sourceProperties.__version === undefined ) || ( forceUpload === true );
			const dataReady = source.dataReady;
			let levels = getMipLevels( texture, image );

			setTextureParameters( _gl.TEXTURE_CUBE_MAP, texture );

			let mipmaps;

			if ( isCompressed ) {

				if ( useTexStorage && allocateMemory ) {

					state.texStorage2D( _gl.TEXTURE_CUBE_MAP, levels, glInternalFormat, image.width, image.height );

				}

				for ( let i = 0; i < 6; i ++ ) {

					mipmaps = cubeImage[ i ].mipmaps;

					for ( let j = 0; j < mipmaps.length; j ++ ) {

						const mipmap = mipmaps[ j ];

						if ( texture.format !== RGBAFormat ) {

							if ( glFormat !== null ) {

								if ( useTexStorage ) {

									if ( dataReady ) {

										state.compressedTexSubImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, j, 0, 0, mipmap.width, mipmap.height, glFormat, mipmap.data );

									}

								} else {

									state.compressedTexImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, j, glInternalFormat, mipmap.width, mipmap.height, 0, mipmap.data );

								}

							} else {

								console.warn( 'THREE.WebGLRenderer: Attempt to load unsupported compressed texture format in .setTextureCube()' );

							}

						} else {

							if ( useTexStorage ) {

								if ( dataReady ) {

									state.texSubImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, j, 0, 0, mipmap.width, mipmap.height, glFormat, glType, mipmap.data );

								}

							} else {

								state.texImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, j, glInternalFormat, mipmap.width, mipmap.height, 0, glFormat, glType, mipmap.data );

							}

						}

					}

				}

			} else {

				mipmaps = texture.mipmaps;

				if ( useTexStorage && allocateMemory ) {

					// TODO: Uniformly handle mipmap definitions
					// Normal textures and compressed cube textures define base level + mips with their mipmap array
					// Uncompressed cube textures use their mipmap array only for mips (no base level)

					if ( mipmaps.length > 0 ) levels ++;

					const dimensions = getDimensions( cubeImage[ 0 ] );

					state.texStorage2D( _gl.TEXTURE_CUBE_MAP, levels, glInternalFormat, dimensions.width, dimensions.height );

				}

				for ( let i = 0; i < 6; i ++ ) {

					if ( isDataTexture ) {

						if ( useTexStorage ) {

							if ( dataReady ) {

								state.texSubImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, 0, 0, 0, cubeImage[ i ].width, cubeImage[ i ].height, glFormat, glType, cubeImage[ i ].data );

							}

						} else {

							state.texImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, 0, glInternalFormat, cubeImage[ i ].width, cubeImage[ i ].height, 0, glFormat, glType, cubeImage[ i ].data );

						}

						for ( let j = 0; j < mipmaps.length; j ++ ) {

							const mipmap = mipmaps[ j ];
							const mipmapImage = mipmap.image[ i ].image;

							if ( useTexStorage ) {

								if ( dataReady ) {

									state.texSubImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, j + 1, 0, 0, mipmapImage.width, mipmapImage.height, glFormat, glType, mipmapImage.data );

								}

							} else {

								state.texImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, j + 1, glInternalFormat, mipmapImage.width, mipmapImage.height, 0, glFormat, glType, mipmapImage.data );

							}

						}

					} else {

						if ( useTexStorage ) {

							if ( dataReady ) {

								state.texSubImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, 0, 0, 0, glFormat, glType, cubeImage[ i ] );

							}

						} else {

							state.texImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, 0, glInternalFormat, glFormat, glType, cubeImage[ i ] );

						}

						for ( let j = 0; j < mipmaps.length; j ++ ) {

							const mipmap = mipmaps[ j ];

							if ( useTexStorage ) {

								if ( dataReady ) {

									state.texSubImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, j + 1, 0, 0, glFormat, glType, mipmap.image[ i ] );

								}

							} else {

								state.texImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, j + 1, glInternalFormat, glFormat, glType, mipmap.image[ i ] );

							}

						}

					}

				}

			}

			if ( textureNeedsGenerateMipmaps( texture ) ) {

				// We assume images for cube map have the same size.
				generateMipmap( _gl.TEXTURE_CUBE_MAP );

			}

			sourceProperties.__version = source.version;

			if ( texture.onUpdate ) texture.onUpdate( texture );

		}

		textureProperties.__version = texture.version;

	}

	// Render targets

	// Setup storage for target texture and bind it to correct framebuffer
	function setupFrameBufferTexture( framebuffer, renderTarget, texture, attachment, textureTarget, level ) {

		const glFormat = utils.convert( texture.format, texture.colorSpace );
		const glType = utils.convert( texture.type );
		const glInternalFormat = getInternalFormat( texture.internalFormat, glFormat, glType, texture.colorSpace );
		const renderTargetProperties = properties.get( renderTarget );
		const textureProperties = properties.get( texture );

		textureProperties.__renderTarget = renderTarget;

		if ( ! renderTargetProperties.__hasExternalTextures ) {

			const width = Math.max( 1, renderTarget.width >> level );
			const height = Math.max( 1, renderTarget.height >> level );

			if ( textureTarget === _gl.TEXTURE_3D || textureTarget === _gl.TEXTURE_2D_ARRAY ) {

				state.texImage3D( textureTarget, level, glInternalFormat, width, height, renderTarget.depth, 0, glFormat, glType, null );

			} else {

				state.texImage2D( textureTarget, level, glInternalFormat, width, height, 0, glFormat, glType, null );

			}

		}

		state.bindFramebuffer( _gl.FRAMEBUFFER, framebuffer );

		if ( useMultisampledRTT( renderTarget ) ) {

			multisampledRTTExt.framebufferTexture2DMultisampleEXT( _gl.FRAMEBUFFER, attachment, textureTarget, textureProperties.__webglTexture, 0, getRenderTargetSamples( renderTarget ) );

		} else if ( textureTarget === _gl.TEXTURE_2D || ( textureTarget >= _gl.TEXTURE_CUBE_MAP_POSITIVE_X && textureTarget <= _gl.TEXTURE_CUBE_MAP_NEGATIVE_Z ) ) { // see #24753

			_gl.framebufferTexture2D( _gl.FRAMEBUFFER, attachment, textureTarget, textureProperties.__webglTexture, level );

		}

		state.bindFramebuffer( _gl.FRAMEBUFFER, null );

	}

	// Setup storage for internal depth/stencil buffers and bind to correct framebuffer
	function setupRenderBufferStorage( renderbuffer, renderTarget, isMultisample ) {

		_gl.bindRenderbuffer( _gl.RENDERBUFFER, renderbuffer );

		if ( renderTarget.depthBuffer ) {

			// retrieve the depth attachment types
			const depthTexture = renderTarget.depthTexture;
			const depthType = depthTexture && depthTexture.isDepthTexture ? depthTexture.type : null;
			const glInternalFormat = getInternalDepthFormat( renderTarget.stencilBuffer, depthType );
			const glAttachmentType = renderTarget.stencilBuffer ? _gl.DEPTH_STENCIL_ATTACHMENT : _gl.DEPTH_ATTACHMENT;

			// set up the attachment
			const samples = getRenderTargetSamples( renderTarget );
			const isUseMultisampledRTT = useMultisampledRTT( renderTarget );
			if ( isUseMultisampledRTT ) {

				multisampledRTTExt.renderbufferStorageMultisampleEXT( _gl.RENDERBUFFER, samples, glInternalFormat, renderTarget.width, renderTarget.height );

			} else if ( isMultisample ) {

				_gl.renderbufferStorageMultisample( _gl.RENDERBUFFER, samples, glInternalFormat, renderTarget.width, renderTarget.height );

			} else {

				_gl.renderbufferStorage( _gl.RENDERBUFFER, glInternalFormat, renderTarget.width, renderTarget.height );

			}

			_gl.framebufferRenderbuffer( _gl.FRAMEBUFFER, glAttachmentType, _gl.RENDERBUFFER, renderbuffer );

		} else {

			const textures = renderTarget.textures;

			for ( let i = 0; i < textures.length; i ++ ) {

				const texture = textures[ i ];

				const glFormat = utils.convert( texture.format, texture.colorSpace );
				const glType = utils.convert( texture.type );
				const glInternalFormat = getInternalFormat( texture.internalFormat, glFormat, glType, texture.colorSpace );
				const samples = getRenderTargetSamples( renderTarget );

				if ( isMultisample && useMultisampledRTT( renderTarget ) === false ) {

					_gl.renderbufferStorageMultisample( _gl.RENDERBUFFER, samples, glInternalFormat, renderTarget.width, renderTarget.height );

				} else if ( useMultisampledRTT( renderTarget ) ) {

					multisampledRTTExt.renderbufferStorageMultisampleEXT( _gl.RENDERBUFFER, samples, glInternalFormat, renderTarget.width, renderTarget.height );

				} else {

					_gl.renderbufferStorage( _gl.RENDERBUFFER, glInternalFormat, renderTarget.width, renderTarget.height );

				}

			}

		}

		_gl.bindRenderbuffer( _gl.RENDERBUFFER, null );

	}

	// Setup resources for a Depth Texture for a FBO (needs an extension)
	function setupDepthTexture( framebuffer, renderTarget ) {

		const isCube = ( renderTarget && renderTarget.isWebGLCubeRenderTarget );
		if ( isCube ) throw new Error( 'Depth Texture with cube render targets is not supported' );

		state.bindFramebuffer( _gl.FRAMEBUFFER, framebuffer );

		if ( ! ( renderTarget.depthTexture && renderTarget.depthTexture.isDepthTexture ) ) {

			throw new Error( 'renderTarget.depthTexture must be an instance of THREE.DepthTexture' );

		}

		const textureProperties = properties.get( renderTarget.depthTexture );
		textureProperties.__renderTarget = renderTarget;

		// upload an empty depth texture with framebuffer size
		if ( ! textureProperties.__webglTexture ||
				renderTarget.depthTexture.image.width !== renderTarget.width ||
				renderTarget.depthTexture.image.height !== renderTarget.height ) {

			renderTarget.depthTexture.image.width = renderTarget.width;
			renderTarget.depthTexture.image.height = renderTarget.height;
			renderTarget.depthTexture.needsUpdate = true;

		}

		setTexture2D( renderTarget.depthTexture, 0 );

		const webglDepthTexture = textureProperties.__webglTexture;
		const samples = getRenderTargetSamples( renderTarget );

		if ( renderTarget.depthTexture.format === DepthFormat ) {

			if ( useMultisampledRTT( renderTarget ) ) {

				multisampledRTTExt.framebufferTexture2DMultisampleEXT( _gl.FRAMEBUFFER, _gl.DEPTH_ATTACHMENT, _gl.TEXTURE_2D, webglDepthTexture, 0, samples );

			} else {

				_gl.framebufferTexture2D( _gl.FRAMEBUFFER, _gl.DEPTH_ATTACHMENT, _gl.TEXTURE_2D, webglDepthTexture, 0 );

			}

		} else if ( renderTarget.depthTexture.format === DepthStencilFormat ) {

			if ( useMultisampledRTT( renderTarget ) ) {

				multisampledRTTExt.framebufferTexture2DMultisampleEXT( _gl.FRAMEBUFFER, _gl.DEPTH_STENCIL_ATTACHMENT, _gl.TEXTURE_2D, webglDepthTexture, 0, samples );

			} else {

				_gl.framebufferTexture2D( _gl.FRAMEBUFFER, _gl.DEPTH_STENCIL_ATTACHMENT, _gl.TEXTURE_2D, webglDepthTexture, 0 );

			}

		} else {

			throw new Error( 'Unknown depthTexture format' );

		}

	}

	// Setup GL resources for a non-texture depth buffer
	function setupDepthRenderbuffer( renderTarget ) {

		const renderTargetProperties = properties.get( renderTarget );
		const isCube = ( renderTarget.isWebGLCubeRenderTarget === true );

		// if the bound depth texture has changed
		if ( renderTargetProperties.__boundDepthTexture !== renderTarget.depthTexture ) {

			// fire the dispose event to get rid of stored state associated with the previously bound depth buffer
			const depthTexture = renderTarget.depthTexture;
			if ( renderTargetProperties.__depthDisposeCallback ) {

				renderTargetProperties.__depthDisposeCallback();

			}

			// set up dispose listeners to track when the currently attached buffer is implicitly unbound
			if ( depthTexture ) {

				const disposeEvent = () => {

					delete renderTargetProperties.__boundDepthTexture;
					delete renderTargetProperties.__depthDisposeCallback;
					depthTexture.removeEventListener( 'dispose', disposeEvent );

				};

				depthTexture.addEventListener( 'dispose', disposeEvent );
				renderTargetProperties.__depthDisposeCallback = disposeEvent;

			}

			renderTargetProperties.__boundDepthTexture = depthTexture;

		}

		if ( renderTarget.depthTexture && ! renderTargetProperties.__autoAllocateDepthBuffer ) {

			if ( isCube ) throw new Error( 'target.depthTexture not supported in Cube render targets' );

			const mipmaps = renderTarget.texture.mipmaps;

			if ( mipmaps && mipmaps.length > 0 ) {

				setupDepthTexture( renderTargetProperties.__webglFramebuffer[ 0 ], renderTarget );

			} else {

				setupDepthTexture( renderTargetProperties.__webglFramebuffer, renderTarget );

			}

		} else {

			if ( isCube ) {

				renderTargetProperties.__webglDepthbuffer = [];

				for ( let i = 0; i < 6; i ++ ) {

					state.bindFramebuffer( _gl.FRAMEBUFFER, renderTargetProperties.__webglFramebuffer[ i ] );

					if ( renderTargetProperties.__webglDepthbuffer[ i ] === undefined ) {

						renderTargetProperties.__webglDepthbuffer[ i ] = _gl.createRenderbuffer();
						setupRenderBufferStorage( renderTargetProperties.__webglDepthbuffer[ i ], renderTarget, false );

					} else {

						// attach buffer if it's been created already
						const glAttachmentType = renderTarget.stencilBuffer ? _gl.DEPTH_STENCIL_ATTACHMENT : _gl.DEPTH_ATTACHMENT;
						const renderbuffer = renderTargetProperties.__webglDepthbuffer[ i ];
						_gl.bindRenderbuffer( _gl.RENDERBUFFER, renderbuffer );
						_gl.framebufferRenderbuffer( _gl.FRAMEBUFFER, glAttachmentType, _gl.RENDERBUFFER, renderbuffer );

					}

				}

			} else {

				const mipmaps = renderTarget.texture.mipmaps;

				if ( mipmaps && mipmaps.length > 0 ) {

					state.bindFramebuffer( _gl.FRAMEBUFFER, renderTargetProperties.__webglFramebuffer[ 0 ] );

				} else {

					state.bindFramebuffer( _gl.FRAMEBUFFER, renderTargetProperties.__webglFramebuffer );

				}

				if ( renderTargetProperties.__webglDepthbuffer === undefined ) {

					renderTargetProperties.__webglDepthbuffer = _gl.createRenderbuffer();
					setupRenderBufferStorage( renderTargetProperties.__webglDepthbuffer, renderTarget, false );

				} else {

					// attach buffer if it's been created already
					const glAttachmentType = renderTarget.stencilBuffer ? _gl.DEPTH_STENCIL_ATTACHMENT : _gl.DEPTH_ATTACHMENT;
					const renderbuffer = renderTargetProperties.__webglDepthbuffer;
					_gl.bindRenderbuffer( _gl.RENDERBUFFER, renderbuffer );
					_gl.framebufferRenderbuffer( _gl.FRAMEBUFFER, glAttachmentType, _gl.RENDERBUFFER, renderbuffer );

				}

			}

		}

		state.bindFramebuffer( _gl.FRAMEBUFFER, null );

	}

	// rebind framebuffer with external textures
	function rebindTextures( renderTarget, colorTexture, depthTexture ) {

		const renderTargetProperties = properties.get( renderTarget );

		if ( colorTexture !== undefined ) {

			setupFrameBufferTexture( renderTargetProperties.__webglFramebuffer, renderTarget, renderTarget.texture, _gl.COLOR_ATTACHMENT0, _gl.TEXTURE_2D, 0 );

		}

		if ( depthTexture !== undefined ) {

			setupDepthRenderbuffer( renderTarget );

		}

	}

	// Set up GL resources for the render target
	function setupRenderTarget( renderTarget ) {

		const texture = renderTarget.texture;

		const renderTargetProperties = properties.get( renderTarget );
		const textureProperties = properties.get( texture );

		renderTarget.addEventListener( 'dispose', onRenderTargetDispose );

		const textures = renderTarget.textures;

		const isCube = ( renderTarget.isWebGLCubeRenderTarget === true );
		const isMultipleRenderTargets = ( textures.length > 1 );

		if ( ! isMultipleRenderTargets ) {

			if ( textureProperties.__webglTexture === undefined ) {

				textureProperties.__webglTexture = _gl.createTexture();

			}

			textureProperties.__version = texture.version;
			info.memory.textures ++;

		}

		// Setup framebuffer

		if ( isCube ) {

			renderTargetProperties.__webglFramebuffer = [];

			for ( let i = 0; i < 6; i ++ ) {

				if ( texture.mipmaps && texture.mipmaps.length > 0 ) {

					renderTargetProperties.__webglFramebuffer[ i ] = [];

					for ( let level = 0; level < texture.mipmaps.length; level ++ ) {

						renderTargetProperties.__webglFramebuffer[ i ][ level ] = _gl.createFramebuffer();

					}

				} else {

					renderTargetProperties.__webglFramebuffer[ i ] = _gl.createFramebuffer();

				}

			}

		} else {

			if ( texture.mipmaps && texture.mipmaps.length > 0 ) {

				renderTargetProperties.__webglFramebuffer = [];

				for ( let level = 0; level < texture.mipmaps.length; level ++ ) {

					renderTargetProperties.__webglFramebuffer[ level ] = _gl.createFramebuffer();

				}

			} else {

				renderTargetProperties.__webglFramebuffer = _gl.createFramebuffer();

			}

			if ( isMultipleRenderTargets ) {

				for ( let i = 0, il = textures.length; i < il; i ++ ) {

					const attachmentProperties = properties.get( textures[ i ] );

					if ( attachmentProperties.__webglTexture === undefined ) {

						attachmentProperties.__webglTexture = _gl.createTexture();

						info.memory.textures ++;

					}

				}

			}

			if ( ( renderTarget.samples > 0 ) && useMultisampledRTT( renderTarget ) === false ) {

				renderTargetProperties.__webglMultisampledFramebuffer = _gl.createFramebuffer();
				renderTargetProperties.__webglColorRenderbuffer = [];

				state.bindFramebuffer( _gl.FRAMEBUFFER, renderTargetProperties.__webglMultisampledFramebuffer );

				for ( let i = 0; i < textures.length; i ++ ) {

					const texture = textures[ i ];
					renderTargetProperties.__webglColorRenderbuffer[ i ] = _gl.createRenderbuffer();

					_gl.bindRenderbuffer( _gl.RENDERBUFFER, renderTargetProperties.__webglColorRenderbuffer[ i ] );

					const glFormat = utils.convert( texture.format, texture.colorSpace );
					const glType = utils.convert( texture.type );
					const glInternalFormat = getInternalFormat( texture.internalFormat, glFormat, glType, texture.colorSpace, renderTarget.isXRRenderTarget === true );
					const samples = getRenderTargetSamples( renderTarget );
					_gl.renderbufferStorageMultisample( _gl.RENDERBUFFER, samples, glInternalFormat, renderTarget.width, renderTarget.height );

					_gl.framebufferRenderbuffer( _gl.FRAMEBUFFER, _gl.COLOR_ATTACHMENT0 + i, _gl.RENDERBUFFER, renderTargetProperties.__webglColorRenderbuffer[ i ] );

				}

				_gl.bindRenderbuffer( _gl.RENDERBUFFER, null );

				if ( renderTarget.depthBuffer ) {

					renderTargetProperties.__webglDepthRenderbuffer = _gl.createRenderbuffer();
					setupRenderBufferStorage( renderTargetProperties.__webglDepthRenderbuffer, renderTarget, true );

				}

				state.bindFramebuffer( _gl.FRAMEBUFFER, null );

			}

		}

		// Setup color buffer

		if ( isCube ) {

			state.bindTexture( _gl.TEXTURE_CUBE_MAP, textureProperties.__webglTexture );
			setTextureParameters( _gl.TEXTURE_CUBE_MAP, texture );

			for ( let i = 0; i < 6; i ++ ) {

				if ( texture.mipmaps && texture.mipmaps.length > 0 ) {

					for ( let level = 0; level < texture.mipmaps.length; level ++ ) {

						setupFrameBufferTexture( renderTargetProperties.__webglFramebuffer[ i ][ level ], renderTarget, texture, _gl.COLOR_ATTACHMENT0, _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, level );

					}

				} else {

					setupFrameBufferTexture( renderTargetProperties.__webglFramebuffer[ i ], renderTarget, texture, _gl.COLOR_ATTACHMENT0, _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, 0 );

				}

			}

			if ( textureNeedsGenerateMipmaps( texture ) ) {

				generateMipmap( _gl.TEXTURE_CUBE_MAP );

			}

			state.unbindTexture();

		} else if ( isMultipleRenderTargets ) {

			for ( let i = 0, il = textures.length; i < il; i ++ ) {

				const attachment = textures[ i ];
				const attachmentProperties = properties.get( attachment );

				let glTextureType = _gl.TEXTURE_2D;

				if ( renderTarget.isWebGL3DRenderTarget || renderTarget.isWebGLArrayRenderTarget ) {

					glTextureType = renderTarget.isWebGL3DRenderTarget ? _gl.TEXTURE_3D : _gl.TEXTURE_2D_ARRAY;

				}

				state.bindTexture( glTextureType, attachmentProperties.__webglTexture );
				setTextureParameters( glTextureType, attachment );
				setupFrameBufferTexture( renderTargetProperties.__webglFramebuffer, renderTarget, attachment, _gl.COLOR_ATTACHMENT0 + i, glTextureType, 0 );

				if ( textureNeedsGenerateMipmaps( attachment ) ) {

					generateMipmap( glTextureType );

				}

			}

			state.unbindTexture();

		} else {

			let glTextureType = _gl.TEXTURE_2D;

			if ( renderTarget.isWebGL3DRenderTarget || renderTarget.isWebGLArrayRenderTarget ) {

				glTextureType = renderTarget.isWebGL3DRenderTarget ? _gl.TEXTURE_3D : _gl.TEXTURE_2D_ARRAY;

			}

			state.bindTexture( glTextureType, textureProperties.__webglTexture );
			setTextureParameters( glTextureType, texture );

			if ( texture.mipmaps && texture.mipmaps.length > 0 ) {

				for ( let level = 0; level < texture.mipmaps.length; level ++ ) {

					setupFrameBufferTexture( renderTargetProperties.__webglFramebuffer[ level ], renderTarget, texture, _gl.COLOR_ATTACHMENT0, glTextureType, level );

				}

			} else {

				setupFrameBufferTexture( renderTargetProperties.__webglFramebuffer, renderTarget, texture, _gl.COLOR_ATTACHMENT0, glTextureType, 0 );

			}

			if ( textureNeedsGenerateMipmaps( texture ) ) {

				generateMipmap( glTextureType );

			}

			state.unbindTexture();

		}

		// Setup depth and stencil buffers

		if ( renderTarget.depthBuffer ) {

			setupDepthRenderbuffer( renderTarget );

		}

	}

	function updateRenderTargetMipmap( renderTarget ) {

		const textures = renderTarget.textures;

		for ( let i = 0, il = textures.length; i < il; i ++ ) {

			const texture = textures[ i ];

			if ( textureNeedsGenerateMipmaps( texture ) ) {

				const targetType = getTargetType( renderTarget );
				const webglTexture = properties.get( texture ).__webglTexture;

				state.bindTexture( targetType, webglTexture );
				generateMipmap( targetType );
				state.unbindTexture();

			}

		}

	}

	const invalidationArrayRead = [];
	const invalidationArrayDraw = [];

	function updateMultisampleRenderTarget( renderTarget ) {

		if ( renderTarget.samples > 0 ) {

			if ( useMultisampledRTT( renderTarget ) === false ) {

				const textures = renderTarget.textures;
				const width = renderTarget.width;
				const height = renderTarget.height;
				let mask = _gl.COLOR_BUFFER_BIT;
				const depthStyle = renderTarget.stencilBuffer ? _gl.DEPTH_STENCIL_ATTACHMENT : _gl.DEPTH_ATTACHMENT;
				const renderTargetProperties = properties.get( renderTarget );
				const isMultipleRenderTargets = ( textures.length > 1 );

				// If MRT we need to remove FBO attachments
				if ( isMultipleRenderTargets ) {

					for ( let i = 0; i < textures.length; i ++ ) {

						state.bindFramebuffer( _gl.FRAMEBUFFER, renderTargetProperties.__webglMultisampledFramebuffer );
						_gl.framebufferRenderbuffer( _gl.FRAMEBUFFER, _gl.COLOR_ATTACHMENT0 + i, _gl.RENDERBUFFER, null );

						state.bindFramebuffer( _gl.FRAMEBUFFER, renderTargetProperties.__webglFramebuffer );
						_gl.framebufferTexture2D( _gl.DRAW_FRAMEBUFFER, _gl.COLOR_ATTACHMENT0 + i, _gl.TEXTURE_2D, null, 0 );

					}

				}

				state.bindFramebuffer( _gl.READ_FRAMEBUFFER, renderTargetProperties.__webglMultisampledFramebuffer );

				const mipmaps = renderTarget.texture.mipmaps;

				if ( mipmaps && mipmaps.length > 0 ) {

					state.bindFramebuffer( _gl.DRAW_FRAMEBUFFER, renderTargetProperties.__webglFramebuffer[ 0 ] );

				} else {

					state.bindFramebuffer( _gl.DRAW_FRAMEBUFFER, renderTargetProperties.__webglFramebuffer );

				}

				for ( let i = 0; i < textures.length; i ++ ) {

					if ( renderTarget.resolveDepthBuffer ) {

						if ( renderTarget.depthBuffer ) mask |= _gl.DEPTH_BUFFER_BIT;

						// resolving stencil is slow with a D3D backend. disable it for all transmission render targets (see #27799)

						if ( renderTarget.stencilBuffer && renderTarget.resolveStencilBuffer ) mask |= _gl.STENCIL_BUFFER_BIT;

					}

					if ( isMultipleRenderTargets ) {

						_gl.framebufferRenderbuffer( _gl.READ_FRAMEBUFFER, _gl.COLOR_ATTACHMENT0, _gl.RENDERBUFFER, renderTargetProperties.__webglColorRenderbuffer[ i ] );

						const webglTexture = properties.get( textures[ i ] ).__webglTexture;
						_gl.framebufferTexture2D( _gl.DRAW_FRAMEBUFFER, _gl.COLOR_ATTACHMENT0, _gl.TEXTURE_2D, webglTexture, 0 );

					}

					_gl.blitFramebuffer( 0, 0, width, height, 0, 0, width, height, mask, _gl.NEAREST );

					if ( supportsInvalidateFramebuffer === true ) {

						invalidationArrayRead.length = 0;
						invalidationArrayDraw.length = 0;

						invalidationArrayRead.push( _gl.COLOR_ATTACHMENT0 + i );

						if ( renderTarget.depthBuffer && renderTarget.resolveDepthBuffer === false ) {

							invalidationArrayRead.push( depthStyle );
							invalidationArrayDraw.push( depthStyle );

							_gl.invalidateFramebuffer( _gl.DRAW_FRAMEBUFFER, invalidationArrayDraw );

						}

						_gl.invalidateFramebuffer( _gl.READ_FRAMEBUFFER, invalidationArrayRead );

					}

				}

				state.bindFramebuffer( _gl.READ_FRAMEBUFFER, null );
				state.bindFramebuffer( _gl.DRAW_FRAMEBUFFER, null );

				// If MRT since pre-blit we removed the FBO we need to reconstruct the attachments
				if ( isMultipleRenderTargets ) {

					for ( let i = 0; i < textures.length; i ++ ) {

						state.bindFramebuffer( _gl.FRAMEBUFFER, renderTargetProperties.__webglMultisampledFramebuffer );
						_gl.framebufferRenderbuffer( _gl.FRAMEBUFFER, _gl.COLOR_ATTACHMENT0 + i, _gl.RENDERBUFFER, renderTargetProperties.__webglColorRenderbuffer[ i ] );

						const webglTexture = properties.get( textures[ i ] ).__webglTexture;

						state.bindFramebuffer( _gl.FRAMEBUFFER, renderTargetProperties.__webglFramebuffer );
						_gl.framebufferTexture2D( _gl.DRAW_FRAMEBUFFER, _gl.COLOR_ATTACHMENT0 + i, _gl.TEXTURE_2D, webglTexture, 0 );

					}

				}

				state.bindFramebuffer( _gl.DRAW_FRAMEBUFFER, renderTargetProperties.__webglMultisampledFramebuffer );

			} else {

				if ( renderTarget.depthBuffer && renderTarget.resolveDepthBuffer === false && supportsInvalidateFramebuffer ) {

					const depthStyle = renderTarget.stencilBuffer ? _gl.DEPTH_STENCIL_ATTACHMENT : _gl.DEPTH_ATTACHMENT;

					_gl.invalidateFramebuffer( _gl.DRAW_FRAMEBUFFER, [ depthStyle ] );

				}

			}

		}

	}

	function getRenderTargetSamples( renderTarget ) {

		return Math.min( capabilities.maxSamples, renderTarget.samples );

	}

	function useMultisampledRTT( renderTarget ) {

		const renderTargetProperties = properties.get( renderTarget );

		return renderTarget.samples > 0 && extensions.has( 'WEBGL_multisampled_render_to_texture' ) === true && renderTargetProperties.__useRenderToTexture !== false;

	}

	function updateVideoTexture( texture ) {

		const frame = info.render.frame;

		// Check the last frame we updated the VideoTexture

		if ( _videoTextures.get( texture ) !== frame ) {

			_videoTextures.set( texture, frame );
			texture.update();

		}

	}

	function verifyColorSpace( texture, image ) {

		const colorSpace = texture.colorSpace;
		const format = texture.format;
		const type = texture.type;

		if ( texture.isCompressedTexture === true || texture.isVideoTexture === true ) return image;

		if ( colorSpace !== LinearSRGBColorSpace && colorSpace !== NoColorSpace ) {

			// sRGB

			if ( ColorManagement.getTransfer( colorSpace ) === SRGBTransfer ) {

				// in WebGL 2 uncompressed textures can only be sRGB encoded if they have the RGBA8 format

				if ( format !== RGBAFormat || type !== UnsignedByteType ) {

					console.warn( 'THREE.WebGLTextures: sRGB encoded textures have to use RGBAFormat and UnsignedByteType.' );

				}

			} else {

				console.error( 'THREE.WebGLTextures: Unsupported texture color space:', colorSpace );

			}

		}

		return image;

	}

	function getDimensions( image ) {

		if ( typeof HTMLImageElement !== 'undefined' && image instanceof HTMLImageElement ) {

			// if intrinsic data are not available, fallback to width/height

			_imageDimensions.width = image.naturalWidth || image.width;
			_imageDimensions.height = image.naturalHeight || image.height;

		} else if ( typeof VideoFrame !== 'undefined' && image instanceof VideoFrame ) {

			_imageDimensions.width = image.displayWidth;
			_imageDimensions.height = image.displayHeight;

		} else {

			_imageDimensions.width = image.width;
			_imageDimensions.height = image.height;

		}

		return _imageDimensions;

	}

	//

	this.allocateTextureUnit = allocateTextureUnit;
	this.resetTextureUnits = resetTextureUnits;

	this.setTexture2D = setTexture2D;
	this.setTexture2DArray = setTexture2DArray;
	this.setTexture3D = setTexture3D;
	this.setTextureCube = setTextureCube;
	this.rebindTextures = rebindTextures;
	this.setupRenderTarget = setupRenderTarget;
	this.updateRenderTargetMipmap = updateRenderTargetMipmap;
	this.updateMultisampleRenderTarget = updateMultisampleRenderTarget;
	this.setupDepthRenderbuffer = setupDepthRenderbuffer;
	this.setupFrameBufferTexture = setupFrameBufferTexture;
	this.useMultisampledRTT = useMultisampledRTT;

}
```
</details>

### `createCanvas(width: any, height: any): HTMLElement | OffscreenCanvas`

**Parameters:**

- **`width`** `any`
- **`height`** `any`

**Returns:** `HTMLElement | OffscreenCanvas`

**Calls:**

- `createElementNS (from ../../utils.js)`

**Internal Comments:**
```
// Use OffscreenCanvas when available. Specially needed in web workers
// eslint-disable-next-line compat/compat
```

<details><summary>Code</summary>

```typescript
function createCanvas( width, height ) {

		// Use OffscreenCanvas when available. Specially needed in web workers

		return useOffscreenCanvas ?
			// eslint-disable-next-line compat/compat
			new OffscreenCanvas( width, height ) : createElementNS( 'canvas' );

	}
```
</details>

### `resizeImage(image: any, needsNewCanvas: any, maxSize: any): any`

**Parameters:**

- **`image`** `any`
- **`needsNewCanvas`** `any`
- **`maxSize`** `any`

**Returns:** `any`

**Calls:**

- `getDimensions`
- `Math.max`
- `Math.floor`
- `createCanvas`
- `canvas.getContext`
- `context.drawImage`
- `console.warn`

**Internal Comments:**
```
// handle case if texture exceeds max size
// only perform resize if necessary
// only perform resize for certain image types
// cube textures can't reuse the same canvas (x2)
```

<details><summary>Code</summary>

```typescript
function resizeImage( image, needsNewCanvas, maxSize ) {

		let scale = 1;

		const dimensions = getDimensions( image );

		// handle case if texture exceeds max size

		if ( dimensions.width > maxSize || dimensions.height > maxSize ) {

			scale = maxSize / Math.max( dimensions.width, dimensions.height );

		}

		// only perform resize if necessary

		if ( scale < 1 ) {

			// only perform resize for certain image types

			if ( ( typeof HTMLImageElement !== 'undefined' && image instanceof HTMLImageElement ) ||
				( typeof HTMLCanvasElement !== 'undefined' && image instanceof HTMLCanvasElement ) ||
				( typeof ImageBitmap !== 'undefined' && image instanceof ImageBitmap ) ||
				( typeof VideoFrame !== 'undefined' && image instanceof VideoFrame ) ) {

				const width = Math.floor( scale * dimensions.width );
				const height = Math.floor( scale * dimensions.height );

				if ( _canvas === undefined ) _canvas = createCanvas( width, height );

				// cube textures can't reuse the same canvas

				const canvas = needsNewCanvas ? createCanvas( width, height ) : _canvas;

				canvas.width = width;
				canvas.height = height;

				const context = canvas.getContext( '2d' );
				context.drawImage( image, 0, 0, width, height );

				console.warn( 'THREE.WebGLRenderer: Texture has been resized from (' + dimensions.width + 'x' + dimensions.height + ') to (' + width + 'x' + height + ').' );

				return canvas;

			} else {

				if ( 'data' in image ) {

					console.warn( 'THREE.WebGLRenderer: Image in DataTexture is too big (' + dimensions.width + 'x' + dimensions.height + ').' );

				}

				return image;

			}

		}

		return image;

	}
```
</details>

### `textureNeedsGenerateMipmaps(texture: any): any`

**Parameters:**

- **`texture`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function textureNeedsGenerateMipmaps( texture ) {

		return texture.generateMipmaps;

	}
```
</details>

### `generateMipmap(target: any): void`

**Parameters:**

- **`target`** `any`

**Returns:** `void`

**Calls:**

- `_gl.generateMipmap`

<details><summary>Code</summary>

```typescript
function generateMipmap( target ) {

		_gl.generateMipmap( target );

	}
```
</details>

### `getTargetType(texture: any): any`

**Parameters:**

- **`texture`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getTargetType( texture ) {

		if ( texture.isWebGLCubeRenderTarget ) return _gl.TEXTURE_CUBE_MAP;
		if ( texture.isWebGL3DRenderTarget ) return _gl.TEXTURE_3D;
		if ( texture.isWebGLArrayRenderTarget || texture.isCompressedArrayTexture ) return _gl.TEXTURE_2D_ARRAY;
		return _gl.TEXTURE_2D;

	}
```
</details>

### `getInternalFormat(internalFormatName: any, glFormat: any, glType: any, colorSpace: any, forceLinearTransfer: boolean): any`

**Parameters:**

- **`internalFormatName`** `any`
- **`glFormat`** `any`
- **`glType`** `any`
- **`colorSpace`** `any`
- **`forceLinearTransfer`** `boolean`

**Returns:** `any`

**Calls:**

- `console.warn`
- `ColorManagement.getTransfer`
- `extensions.get`

<details><summary>Code</summary>

```typescript
function getInternalFormat( internalFormatName, glFormat, glType, colorSpace, forceLinearTransfer = false ) {

		if ( internalFormatName !== null ) {

			if ( _gl[ internalFormatName ] !== undefined ) return _gl[ internalFormatName ];

			console.warn( 'THREE.WebGLRenderer: Attempt to use non-existing WebGL internal format \'' + internalFormatName + '\'' );

		}

		let internalFormat = glFormat;

		if ( glFormat === _gl.RED ) {

			if ( glType === _gl.FLOAT ) internalFormat = _gl.R32F;
			if ( glType === _gl.HALF_FLOAT ) internalFormat = _gl.R16F;
			if ( glType === _gl.UNSIGNED_BYTE ) internalFormat = _gl.R8;

		}

		if ( glFormat === _gl.RED_INTEGER ) {

			if ( glType === _gl.UNSIGNED_BYTE ) internalFormat = _gl.R8UI;
			if ( glType === _gl.UNSIGNED_SHORT ) internalFormat = _gl.R16UI;
			if ( glType === _gl.UNSIGNED_INT ) internalFormat = _gl.R32UI;
			if ( glType === _gl.BYTE ) internalFormat = _gl.R8I;
			if ( glType === _gl.SHORT ) internalFormat = _gl.R16I;
			if ( glType === _gl.INT ) internalFormat = _gl.R32I;

		}

		if ( glFormat === _gl.RG ) {

			if ( glType === _gl.FLOAT ) internalFormat = _gl.RG32F;
			if ( glType === _gl.HALF_FLOAT ) internalFormat = _gl.RG16F;
			if ( glType === _gl.UNSIGNED_BYTE ) internalFormat = _gl.RG8;

		}

		if ( glFormat === _gl.RG_INTEGER ) {

			if ( glType === _gl.UNSIGNED_BYTE ) internalFormat = _gl.RG8UI;
			if ( glType === _gl.UNSIGNED_SHORT ) internalFormat = _gl.RG16UI;
			if ( glType === _gl.UNSIGNED_INT ) internalFormat = _gl.RG32UI;
			if ( glType === _gl.BYTE ) internalFormat = _gl.RG8I;
			if ( glType === _gl.SHORT ) internalFormat = _gl.RG16I;
			if ( glType === _gl.INT ) internalFormat = _gl.RG32I;

		}

		if ( glFormat === _gl.RGB_INTEGER ) {

			if ( glType === _gl.UNSIGNED_BYTE ) internalFormat = _gl.RGB8UI;
			if ( glType === _gl.UNSIGNED_SHORT ) internalFormat = _gl.RGB16UI;
			if ( glType === _gl.UNSIGNED_INT ) internalFormat = _gl.RGB32UI;
			if ( glType === _gl.BYTE ) internalFormat = _gl.RGB8I;
			if ( glType === _gl.SHORT ) internalFormat = _gl.RGB16I;
			if ( glType === _gl.INT ) internalFormat = _gl.RGB32I;

		}

		if ( glFormat === _gl.RGBA_INTEGER ) {

			if ( glType === _gl.UNSIGNED_BYTE ) internalFormat = _gl.RGBA8UI;
			if ( glType === _gl.UNSIGNED_SHORT ) internalFormat = _gl.RGBA16UI;
			if ( glType === _gl.UNSIGNED_INT ) internalFormat = _gl.RGBA32UI;
			if ( glType === _gl.BYTE ) internalFormat = _gl.RGBA8I;
			if ( glType === _gl.SHORT ) internalFormat = _gl.RGBA16I;
			if ( glType === _gl.INT ) internalFormat = _gl.RGBA32I;

		}

		if ( glFormat === _gl.RGB ) {

			if ( glType === _gl.UNSIGNED_INT_5_9_9_9_REV ) internalFormat = _gl.RGB9_E5;

		}

		if ( glFormat === _gl.RGBA ) {

			const transfer = forceLinearTransfer ? LinearTransfer : ColorManagement.getTransfer( colorSpace );

			if ( glType === _gl.FLOAT ) internalFormat = _gl.RGBA32F;
			if ( glType === _gl.HALF_FLOAT ) internalFormat = _gl.RGBA16F;
			if ( glType === _gl.UNSIGNED_BYTE ) internalFormat = ( transfer === SRGBTransfer ) ? _gl.SRGB8_ALPHA8 : _gl.RGBA8;
			if ( glType === _gl.UNSIGNED_SHORT_4_4_4_4 ) internalFormat = _gl.RGBA4;
			if ( glType === _gl.UNSIGNED_SHORT_5_5_5_1 ) internalFormat = _gl.RGB5_A1;

		}

		if ( internalFormat === _gl.R16F || internalFormat === _gl.R32F ||
			internalFormat === _gl.RG16F || internalFormat === _gl.RG32F ||
			internalFormat === _gl.RGBA16F || internalFormat === _gl.RGBA32F ) {

			extensions.get( 'EXT_color_buffer_float' );

		}

		return internalFormat;

	}
```
</details>

### `getInternalDepthFormat(useStencil: any, depthType: any): any`

**Parameters:**

- **`useStencil`** `any`
- **`depthType`** `any`

**Returns:** `any`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
function getInternalDepthFormat( useStencil, depthType ) {

		let glInternalFormat;
		if ( useStencil ) {

			if ( depthType === null || depthType === UnsignedIntType || depthType === UnsignedInt248Type ) {

				glInternalFormat = _gl.DEPTH24_STENCIL8;

			} else if ( depthType === FloatType ) {

				glInternalFormat = _gl.DEPTH32F_STENCIL8;

			} else if ( depthType === UnsignedShortType ) {

				glInternalFormat = _gl.DEPTH24_STENCIL8;
				console.warn( 'DepthTexture: 16 bit depth attachment is not supported with stencil. Using 24-bit attachment.' );

			}

		} else {

			if ( depthType === null || depthType === UnsignedIntType || depthType === UnsignedInt248Type ) {

				glInternalFormat = _gl.DEPTH_COMPONENT24;

			} else if ( depthType === FloatType ) {

				glInternalFormat = _gl.DEPTH_COMPONENT32F;

			} else if ( depthType === UnsignedShortType ) {

				glInternalFormat = _gl.DEPTH_COMPONENT16;

			}

		}

		return glInternalFormat;

	}
```
</details>

### `getMipLevels(texture: any, image: any): any`

**Parameters:**

- **`texture`** `any`
- **`image`** `any`

**Returns:** `any`

**Calls:**

- `textureNeedsGenerateMipmaps`
- `Math.log2`
- `Math.max`
- `Array.isArray`

**Internal Comments:**
```
// user-defined mipmaps
// texture without mipmaps (only base level)
```

<details><summary>Code</summary>

```typescript
function getMipLevels( texture, image ) {

		if ( textureNeedsGenerateMipmaps( texture ) === true || ( texture.isFramebufferTexture && texture.minFilter !== NearestFilter && texture.minFilter !== LinearFilter ) ) {

			return Math.log2( Math.max( image.width, image.height ) ) + 1;

		} else if ( texture.mipmaps !== undefined && texture.mipmaps.length > 0 ) {

			// user-defined mipmaps

			return texture.mipmaps.length;

		} else if ( texture.isCompressedTexture && Array.isArray( texture.image ) ) {

			return image.mipmaps.length;

		} else {

			// texture without mipmaps (only base level)

			return 1;

		}

	}
```
</details>

### `onTextureDispose(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `texture.removeEventListener`
- `deallocateTexture`
- `_videoTextures.delete`

<details><summary>Code</summary>

```typescript
function onTextureDispose( event ) {

		const texture = event.target;

		texture.removeEventListener( 'dispose', onTextureDispose );

		deallocateTexture( texture );

		if ( texture.isVideoTexture ) {

			_videoTextures.delete( texture );

		}

	}
```
</details>

### `onRenderTargetDispose(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `renderTarget.removeEventListener`
- `deallocateRenderTarget`

<details><summary>Code</summary>

```typescript
function onRenderTargetDispose( event ) {

		const renderTarget = event.target;

		renderTarget.removeEventListener( 'dispose', onRenderTargetDispose );

		deallocateRenderTarget( renderTarget );

	}
```
</details>

### `deallocateTexture(texture: any): void`

**Parameters:**

- **`texture`** `any`

**Returns:** `void`

**Calls:**

- `properties.get`
- `_sources.get`
- `deleteTexture`
- `Object.keys`
- `_sources.delete`
- `properties.remove`

**Internal Comments:**
```
// check if it's necessary to remove the WebGLTexture object (x2)
// the WebGLTexture object is not used anymore, remove it
// remove the weak map entry if no WebGLTexture uses the source anymore
```

<details><summary>Code</summary>

```typescript
function deallocateTexture( texture ) {

		const textureProperties = properties.get( texture );

		if ( textureProperties.__webglInit === undefined ) return;

		// check if it's necessary to remove the WebGLTexture object

		const source = texture.source;
		const webglTextures = _sources.get( source );

		if ( webglTextures ) {

			const webglTexture = webglTextures[ textureProperties.__cacheKey ];
			webglTexture.usedTimes --;

			// the WebGLTexture object is not used anymore, remove it

			if ( webglTexture.usedTimes === 0 ) {

				deleteTexture( texture );

			}

			// remove the weak map entry if no WebGLTexture uses the source anymore

			if ( Object.keys( webglTextures ).length === 0 ) {

				_sources.delete( source );

			}

		}

		properties.remove( texture );

	}
```
</details>

### `deleteTexture(texture: any): void`

**Parameters:**

- **`texture`** `any`

**Returns:** `void`

**Calls:**

- `properties.get`
- `_gl.deleteTexture`
- `_sources.get`

<details><summary>Code</summary>

```typescript
function deleteTexture( texture ) {

		const textureProperties = properties.get( texture );
		_gl.deleteTexture( textureProperties.__webglTexture );

		const source = texture.source;
		const webglTextures = _sources.get( source );
		delete webglTextures[ textureProperties.__cacheKey ];

		info.memory.textures --;

	}
```
</details>

### `deallocateRenderTarget(renderTarget: any): void`

**Parameters:**

- **`renderTarget`** `any`

**Returns:** `void`

**Calls:**

- `properties.get`
- `renderTarget.depthTexture.dispose`
- `properties.remove`
- `Array.isArray`
- `_gl.deleteFramebuffer`
- `_gl.deleteRenderbuffer`
- `_gl.deleteTexture`

<details><summary>Code</summary>

```typescript
function deallocateRenderTarget( renderTarget ) {

		const renderTargetProperties = properties.get( renderTarget );

		if ( renderTarget.depthTexture ) {

			renderTarget.depthTexture.dispose();

			properties.remove( renderTarget.depthTexture );

		}

		if ( renderTarget.isWebGLCubeRenderTarget ) {

			for ( let i = 0; i < 6; i ++ ) {

				if ( Array.isArray( renderTargetProperties.__webglFramebuffer[ i ] ) ) {

					for ( let level = 0; level < renderTargetProperties.__webglFramebuffer[ i ].length; level ++ ) _gl.deleteFramebuffer( renderTargetProperties.__webglFramebuffer[ i ][ level ] );

				} else {

					_gl.deleteFramebuffer( renderTargetProperties.__webglFramebuffer[ i ] );

				}

				if ( renderTargetProperties.__webglDepthbuffer ) _gl.deleteRenderbuffer( renderTargetProperties.__webglDepthbuffer[ i ] );

			}

		} else {

			if ( Array.isArray( renderTargetProperties.__webglFramebuffer ) ) {

				for ( let level = 0; level < renderTargetProperties.__webglFramebuffer.length; level ++ ) _gl.deleteFramebuffer( renderTargetProperties.__webglFramebuffer[ level ] );

			} else {

				_gl.deleteFramebuffer( renderTargetProperties.__webglFramebuffer );

			}

			if ( renderTargetProperties.__webglDepthbuffer ) _gl.deleteRenderbuffer( renderTargetProperties.__webglDepthbuffer );
			if ( renderTargetProperties.__webglMultisampledFramebuffer ) _gl.deleteFramebuffer( renderTargetProperties.__webglMultisampledFramebuffer );

			if ( renderTargetProperties.__webglColorRenderbuffer ) {

				for ( let i = 0; i < renderTargetProperties.__webglColorRenderbuffer.length; i ++ ) {

					if ( renderTargetProperties.__webglColorRenderbuffer[ i ] ) _gl.deleteRenderbuffer( renderTargetProperties.__webglColorRenderbuffer[ i ] );

				}

			}

			if ( renderTargetProperties.__webglDepthRenderbuffer ) _gl.deleteRenderbuffer( renderTargetProperties.__webglDepthRenderbuffer );

		}

		const textures = renderTarget.textures;

		for ( let i = 0, il = textures.length; i < il; i ++ ) {

			const attachmentProperties = properties.get( textures[ i ] );

			if ( attachmentProperties.__webglTexture ) {

				_gl.deleteTexture( attachmentProperties.__webglTexture );

				info.memory.textures --;

			}

			properties.remove( textures[ i ] );

		}

		properties.remove( renderTarget );

	}
```
</details>

### `resetTextureUnits(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function resetTextureUnits() {

		textureUnits = 0;

	}
```
</details>

### `allocateTextureUnit(): number`

**Returns:** `number`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
function allocateTextureUnit() {

		const textureUnit = textureUnits;

		if ( textureUnit >= capabilities.maxTextures ) {

			console.warn( 'THREE.WebGLTextures: Trying to use ' + textureUnit + ' texture units while this GPU supports only ' + capabilities.maxTextures );

		}

		textureUnits += 1;

		return textureUnit;

	}
```
</details>

### `getTextureCacheKey(texture: any): string`

**Parameters:**

- **`texture`** `any`

**Returns:** `string`

**Calls:**

- `array.push`
- `array.join`

<details><summary>Code</summary>

```typescript
function getTextureCacheKey( texture ) {

		const array = [];

		array.push( texture.wrapS );
		array.push( texture.wrapT );
		array.push( texture.wrapR || 0 );
		array.push( texture.magFilter );
		array.push( texture.minFilter );
		array.push( texture.anisotropy );
		array.push( texture.internalFormat );
		array.push( texture.format );
		array.push( texture.type );
		array.push( texture.generateMipmaps );
		array.push( texture.premultiplyAlpha );
		array.push( texture.flipY );
		array.push( texture.unpackAlignment );
		array.push( texture.colorSpace );

		return array.join();

	}
```
</details>

### `setTexture2D(texture: any, slot: any): void`

**Parameters:**

- **`texture`** `any`
- **`slot`** `any`

**Returns:** `void`

**Calls:**

- `properties.get`
- `updateVideoTexture`
- `console.warn`
- `uploadTexture`
- `state.bindTexture`

<details><summary>Code</summary>

```typescript
function setTexture2D( texture, slot ) {

		const textureProperties = properties.get( texture );

		if ( texture.isVideoTexture ) updateVideoTexture( texture );

		if ( texture.isRenderTargetTexture === false && texture.isExternalTexture !== true && texture.version > 0 && textureProperties.__version !== texture.version ) {

			const image = texture.image;

			if ( image === null ) {

				console.warn( 'THREE.WebGLRenderer: Texture marked for update but no image data found.' );

			} else if ( image.complete === false ) {

				console.warn( 'THREE.WebGLRenderer: Texture marked for update but image is incomplete' );

			} else {

				uploadTexture( textureProperties, texture, slot );
				return;

			}

		} else if ( texture.isExternalTexture ) {

			textureProperties.__webglTexture = texture.sourceTexture ? texture.sourceTexture : null;

		}

		state.bindTexture( _gl.TEXTURE_2D, textureProperties.__webglTexture, _gl.TEXTURE0 + slot );

	}
```
</details>

### `setTexture2DArray(texture: any, slot: any): void`

**Parameters:**

- **`texture`** `any`
- **`slot`** `any`

**Returns:** `void`

**Calls:**

- `properties.get`
- `uploadTexture`
- `state.bindTexture`

<details><summary>Code</summary>

```typescript
function setTexture2DArray( texture, slot ) {

		const textureProperties = properties.get( texture );

		if ( texture.isRenderTargetTexture === false && texture.version > 0 && textureProperties.__version !== texture.version ) {

			uploadTexture( textureProperties, texture, slot );
			return;

		}

		state.bindTexture( _gl.TEXTURE_2D_ARRAY, textureProperties.__webglTexture, _gl.TEXTURE0 + slot );

	}
```
</details>

### `setTexture3D(texture: any, slot: any): void`

**Parameters:**

- **`texture`** `any`
- **`slot`** `any`

**Returns:** `void`

**Calls:**

- `properties.get`
- `uploadTexture`
- `state.bindTexture`

<details><summary>Code</summary>

```typescript
function setTexture3D( texture, slot ) {

		const textureProperties = properties.get( texture );

		if ( texture.isRenderTargetTexture === false && texture.version > 0 && textureProperties.__version !== texture.version ) {

			uploadTexture( textureProperties, texture, slot );
			return;

		}

		state.bindTexture( _gl.TEXTURE_3D, textureProperties.__webglTexture, _gl.TEXTURE0 + slot );

	}
```
</details>

### `setTextureCube(texture: any, slot: any): void`

**Parameters:**

- **`texture`** `any`
- **`slot`** `any`

**Returns:** `void`

**Calls:**

- `properties.get`
- `uploadCubeTexture`
- `state.bindTexture`

<details><summary>Code</summary>

```typescript
function setTextureCube( texture, slot ) {

		const textureProperties = properties.get( texture );

		if ( texture.version > 0 && textureProperties.__version !== texture.version ) {

			uploadCubeTexture( textureProperties, texture, slot );
			return;

		}

		state.bindTexture( _gl.TEXTURE_CUBE_MAP, textureProperties.__webglTexture, _gl.TEXTURE0 + slot );

	}
```
</details>

### `setTextureParameters(textureType: any, texture: any): void`

**Parameters:**

- **`textureType`** `any`
- **`texture`** `any`

**Returns:** `void`

**Calls:**

- `extensions.has`
- `console.warn`
- `_gl.texParameteri`
- `properties.get`
- `extensions.get`
- `_gl.texParameterf`
- `Math.min`
- `capabilities.getMaxAnisotropy`

<details><summary>Code</summary>

```typescript
function setTextureParameters( textureType, texture ) {

		if ( texture.type === FloatType && extensions.has( 'OES_texture_float_linear' ) === false &&
			( texture.magFilter === LinearFilter || texture.magFilter === LinearMipmapNearestFilter || texture.magFilter === NearestMipmapLinearFilter || texture.magFilter === LinearMipmapLinearFilter ||
			texture.minFilter === LinearFilter || texture.minFilter === LinearMipmapNearestFilter || texture.minFilter === NearestMipmapLinearFilter || texture.minFilter === LinearMipmapLinearFilter ) ) {

			console.warn( 'THREE.WebGLRenderer: Unable to use linear filtering with floating point textures. OES_texture_float_linear not supported on this device.' );

		}

		_gl.texParameteri( textureType, _gl.TEXTURE_WRAP_S, wrappingToGL[ texture.wrapS ] );
		_gl.texParameteri( textureType, _gl.TEXTURE_WRAP_T, wrappingToGL[ texture.wrapT ] );

		if ( textureType === _gl.TEXTURE_3D || textureType === _gl.TEXTURE_2D_ARRAY ) {

			_gl.texParameteri( textureType, _gl.TEXTURE_WRAP_R, wrappingToGL[ texture.wrapR ] );

		}

		_gl.texParameteri( textureType, _gl.TEXTURE_MAG_FILTER, filterToGL[ texture.magFilter ] );
		_gl.texParameteri( textureType, _gl.TEXTURE_MIN_FILTER, filterToGL[ texture.minFilter ] );

		if ( texture.compareFunction ) {

			_gl.texParameteri( textureType, _gl.TEXTURE_COMPARE_MODE, _gl.COMPARE_REF_TO_TEXTURE );
			_gl.texParameteri( textureType, _gl.TEXTURE_COMPARE_FUNC, compareToGL[ texture.compareFunction ] );

		}

		if ( extensions.has( 'EXT_texture_filter_anisotropic' ) === true ) {

			if ( texture.magFilter === NearestFilter ) return;
			if ( texture.minFilter !== NearestMipmapLinearFilter && texture.minFilter !== LinearMipmapLinearFilter ) return;
			if ( texture.type === FloatType && extensions.has( 'OES_texture_float_linear' ) === false ) return; // verify extension

			if ( texture.anisotropy > 1 || properties.get( texture ).__currentAnisotropy ) {

				const extension = extensions.get( 'EXT_texture_filter_anisotropic' );
				_gl.texParameterf( textureType, extension.TEXTURE_MAX_ANISOTROPY_EXT, Math.min( texture.anisotropy, capabilities.getMaxAnisotropy() ) );
				properties.get( texture ).__currentAnisotropy = texture.anisotropy;

			}

		}

	}
```
</details>

### `initTexture(textureProperties: any, texture: any): boolean`

**Parameters:**

- **`textureProperties`** `any`
- **`texture`** `any`

**Returns:** `boolean`

**Calls:**

- `texture.addEventListener`
- `_sources.get`
- `_sources.set`
- `getTextureCacheKey`
- `_gl.createTexture`
- `deleteTexture`

**Internal Comments:**
```
// create Source <-> WebGLTextures mapping if necessary (x2)
// check if there is already a WebGLTexture object for the given texture parameters (x2)
// if not, create a new instance of WebGLTexture
// create new entry (x4)
// when a new instance of WebGLTexture was created, a texture upload is required (x3)
// even if the image contents are identical (x3)
// every time the texture cache key changes, it's necessary to check if an instance of (x2)
// WebGLTexture can be deleted in order to avoid a memory leak. (x2)
// store references to cache key and WebGLTexture object (x4)
```

<details><summary>Code</summary>

```typescript
function initTexture( textureProperties, texture ) {

		let forceUpload = false;

		if ( textureProperties.__webglInit === undefined ) {

			textureProperties.__webglInit = true;

			texture.addEventListener( 'dispose', onTextureDispose );

		}

		// create Source <-> WebGLTextures mapping if necessary

		const source = texture.source;
		let webglTextures = _sources.get( source );

		if ( webglTextures === undefined ) {

			webglTextures = {};
			_sources.set( source, webglTextures );

		}

		// check if there is already a WebGLTexture object for the given texture parameters

		const textureCacheKey = getTextureCacheKey( texture );

		if ( textureCacheKey !== textureProperties.__cacheKey ) {

			// if not, create a new instance of WebGLTexture

			if ( webglTextures[ textureCacheKey ] === undefined ) {

				// create new entry

				webglTextures[ textureCacheKey ] = {
					texture: _gl.createTexture(),
					usedTimes: 0
				};

				info.memory.textures ++;

				// when a new instance of WebGLTexture was created, a texture upload is required
				// even if the image contents are identical

				forceUpload = true;

			}

			webglTextures[ textureCacheKey ].usedTimes ++;

			// every time the texture cache key changes, it's necessary to check if an instance of
			// WebGLTexture can be deleted in order to avoid a memory leak.

			const webglTexture = webglTextures[ textureProperties.__cacheKey ];

			if ( webglTexture !== undefined ) {

				webglTextures[ textureProperties.__cacheKey ].usedTimes --;

				if ( webglTexture.usedTimes === 0 ) {

					deleteTexture( texture );

				}

			}

			// store references to cache key and WebGLTexture object

			textureProperties.__cacheKey = textureCacheKey;
			textureProperties.__webglTexture = webglTextures[ textureCacheKey ].texture;

		}

		return forceUpload;

	}
```
</details>

### `getRow(index: any, rowLength: any, componentStride: any): number`

**Parameters:**

- **`index`** `any`
- **`rowLength`** `any`
- **`componentStride`** `any`

**Returns:** `number`

**Calls:**

- `Math.floor`

<details><summary>Code</summary>

```typescript
function getRow( index, rowLength, componentStride ) {

		return Math.floor( Math.floor( index / componentStride ) / rowLength );

	}
```
</details>

### `updateTexture(texture: any, image: any, glFormat: any, glType: any): void`

**Parameters:**

- **`texture`** `any`
- **`image`** `any`
- **`glFormat`** `any`
- **`glType`** `any`

**Returns:** `void`

**Calls:**

- `state.texSubImage2D`
- `updateRanges.sort`
- `getRow`
- `Math.max`
- `_gl.getParameter`
- `_gl.pixelStorei`
- `Math.floor`
- `Math.ceil`
- `texture.clearUpdateRanges`

**Internal Comments:**
```
// Before applying update ranges, we merge any adjacent / overlapping (x4)
// ranges to reduce load on `gl.texSubImage2D`. Empirically, this has led (x4)
// to performance improvements for applications which make heavy use of (x4)
// update ranges. Likely due to GPU command overhead. (x4)
// (x4)
// Note that to reduce garbage collection between frames, we merge the (x4)
// update ranges in-place. This is safe because this method will clear the (x4)
// update ranges once updated. (x4)
// To merge the update ranges in-place, we work from left to right in the (x2)
// existing updateRanges array, merging ranges. This may result in a final (x2)
// array which is smaller than the original. This index tracks the last (x2)
// index representing a merged range, any data after this index can be (x2)
// trimmed once the merge algorithm is completed. (x2)
// Only merge if in the same row and overlapping/adjacent (x2)
// We add one here to merge adjacent ranges. This is safe because ranges
// operate over positive integers.
// Trim the array to only contain the merged ranges. (x4)
// Assumes update ranges refer to contiguous memory (x2)
```

<details><summary>Code</summary>

```typescript
function updateTexture( texture, image, glFormat, glType ) {

		const componentStride = 4; // only RGBA supported

		const updateRanges = texture.updateRanges;

		if ( updateRanges.length === 0 ) {

			state.texSubImage2D( _gl.TEXTURE_2D, 0, 0, 0, image.width, image.height, glFormat, glType, image.data );

		} else {

			// Before applying update ranges, we merge any adjacent / overlapping
			// ranges to reduce load on `gl.texSubImage2D`. Empirically, this has led
			// to performance improvements for applications which make heavy use of
			// update ranges. Likely due to GPU command overhead.
			//
			// Note that to reduce garbage collection between frames, we merge the
			// update ranges in-place. This is safe because this method will clear the
			// update ranges once updated.

			updateRanges.sort( ( a, b ) => a.start - b.start );

			// To merge the update ranges in-place, we work from left to right in the
			// existing updateRanges array, merging ranges. This may result in a final
			// array which is smaller than the original. This index tracks the last
			// index representing a merged range, any data after this index can be
			// trimmed once the merge algorithm is completed.
			let mergeIndex = 0;

			for ( let i = 1; i < updateRanges.length; i ++ ) {

				const previousRange = updateRanges[ mergeIndex ];
				const range = updateRanges[ i ];

				// Only merge if in the same row and overlapping/adjacent
				const previousEnd = previousRange.start + previousRange.count;
				const currentRow = getRow( range.start, image.width, componentStride );
				const previousRow = getRow( previousRange.start, image.width, componentStride );

				// We add one here to merge adjacent ranges. This is safe because ranges
				// operate over positive integers.
				if (
					range.start <= previousEnd + 1 &&
					currentRow === previousRow &&
					getRow( range.start + range.count - 1, image.width, componentStride ) === currentRow // ensure range doesn't spill
				) {

					previousRange.count = Math.max(
						previousRange.count,
						range.start + range.count - previousRange.start
					);

				} else {

					++ mergeIndex;
					updateRanges[ mergeIndex ] = range;

				}


			}

			// Trim the array to only contain the merged ranges.
			updateRanges.length = mergeIndex + 1;

			const currentUnpackRowLen = _gl.getParameter( _gl.UNPACK_ROW_LENGTH );
			const currentUnpackSkipPixels = _gl.getParameter( _gl.UNPACK_SKIP_PIXELS );
			const currentUnpackSkipRows = _gl.getParameter( _gl.UNPACK_SKIP_ROWS );

			_gl.pixelStorei( _gl.UNPACK_ROW_LENGTH, image.width );

			for ( let i = 0, l = updateRanges.length; i < l; i ++ ) {

				const range = updateRanges[ i ];

				const pixelStart = Math.floor( range.start / componentStride );
				const pixelCount = Math.ceil( range.count / componentStride );

				const x = pixelStart % image.width;
				const y = Math.floor( pixelStart / image.width );

				// Assumes update ranges refer to contiguous memory
				const width = pixelCount;
				const height = 1;

				_gl.pixelStorei( _gl.UNPACK_SKIP_PIXELS, x );
				_gl.pixelStorei( _gl.UNPACK_SKIP_ROWS, y );

				state.texSubImage2D( _gl.TEXTURE_2D, 0, x, y, width, height, glFormat, glType, image.data );

			}

			texture.clearUpdateRanges();

			_gl.pixelStorei( _gl.UNPACK_ROW_LENGTH, currentUnpackRowLen );
			_gl.pixelStorei( _gl.UNPACK_SKIP_PIXELS, currentUnpackSkipPixels );
			_gl.pixelStorei( _gl.UNPACK_SKIP_ROWS, currentUnpackSkipRows );

		}

	}
```
</details>

### `uploadTexture(textureProperties: any, texture: any, slot: any): void`

**Parameters:**

- **`textureProperties`** `any`
- **`texture`** `any`
- **`slot`** `any`

**Returns:** `void`

**Calls:**

- `initTexture`
- `state.bindTexture`
- `properties.get`
- `state.activeTexture`
- `ColorManagement.getPrimaries`
- `_gl.pixelStorei`
- `resizeImage`
- `verifyColorSpace`
- `utils.convert`
- `getInternalFormat`
- `setTextureParameters`
- `getMipLevels`
- `getInternalDepthFormat`
- `state.texStorage2D`
- `state.texImage2D`
- `state.texSubImage2D`
- `updateTexture`
- `state.texStorage3D`
- `getByteLength (from ../../extras/TextureUtils.js)`
- `mipmap.data.subarray`
- `state.compressedTexSubImage3D`
- `texture.clearLayerUpdates`
- `state.compressedTexImage3D`
- `console.warn`
- `state.texSubImage3D`
- `state.texImage3D`
- `state.compressedTexSubImage2D`
- `state.compressedTexImage2D`
- `image.data.subarray`
- `getDimensions`
- `textureNeedsGenerateMipmaps`
- `generateMipmap`
- `texture.onUpdate`

**Internal Comments:**
```
//
// use manually created mipmaps if available (x2)
// if there are no manual mipmaps (x2)
// set 0 level mipmap and then use GL to generate other mipmap levels (x2)
// regular Texture (image, video, canvas)
```

<details><summary>Code</summary>

```typescript
function uploadTexture( textureProperties, texture, slot ) {

		let textureType = _gl.TEXTURE_2D;

		if ( texture.isDataArrayTexture || texture.isCompressedArrayTexture ) textureType = _gl.TEXTURE_2D_ARRAY;
		if ( texture.isData3DTexture ) textureType = _gl.TEXTURE_3D;

		const forceUpload = initTexture( textureProperties, texture );
		const source = texture.source;

		state.bindTexture( textureType, textureProperties.__webglTexture, _gl.TEXTURE0 + slot );

		const sourceProperties = properties.get( source );

		if ( source.version !== sourceProperties.__version || forceUpload === true ) {

			state.activeTexture( _gl.TEXTURE0 + slot );

			const workingPrimaries = ColorManagement.getPrimaries( ColorManagement.workingColorSpace );
			const texturePrimaries = texture.colorSpace === NoColorSpace ? null : ColorManagement.getPrimaries( texture.colorSpace );
			const unpackConversion = texture.colorSpace === NoColorSpace || workingPrimaries === texturePrimaries ? _gl.NONE : _gl.BROWSER_DEFAULT_WEBGL;

			_gl.pixelStorei( _gl.UNPACK_FLIP_Y_WEBGL, texture.flipY );
			_gl.pixelStorei( _gl.UNPACK_PREMULTIPLY_ALPHA_WEBGL, texture.premultiplyAlpha );
			_gl.pixelStorei( _gl.UNPACK_ALIGNMENT, texture.unpackAlignment );
			_gl.pixelStorei( _gl.UNPACK_COLORSPACE_CONVERSION_WEBGL, unpackConversion );

			let image = resizeImage( texture.image, false, capabilities.maxTextureSize );
			image = verifyColorSpace( texture, image );

			const glFormat = utils.convert( texture.format, texture.colorSpace );

			const glType = utils.convert( texture.type );
			let glInternalFormat = getInternalFormat( texture.internalFormat, glFormat, glType, texture.colorSpace, texture.isVideoTexture );

			setTextureParameters( textureType, texture );

			let mipmap;
			const mipmaps = texture.mipmaps;

			const useTexStorage = ( texture.isVideoTexture !== true );
			const allocateMemory = ( sourceProperties.__version === undefined ) || ( forceUpload === true );
			const dataReady = source.dataReady;
			const levels = getMipLevels( texture, image );

			if ( texture.isDepthTexture ) {

				glInternalFormat = getInternalDepthFormat( texture.format === DepthStencilFormat, texture.type );

				//

				if ( allocateMemory ) {

					if ( useTexStorage ) {

						state.texStorage2D( _gl.TEXTURE_2D, 1, glInternalFormat, image.width, image.height );

					} else {

						state.texImage2D( _gl.TEXTURE_2D, 0, glInternalFormat, image.width, image.height, 0, glFormat, glType, null );

					}

				}

			} else if ( texture.isDataTexture ) {

				// use manually created mipmaps if available
				// if there are no manual mipmaps
				// set 0 level mipmap and then use GL to generate other mipmap levels

				if ( mipmaps.length > 0 ) {

					if ( useTexStorage && allocateMemory ) {

						state.texStorage2D( _gl.TEXTURE_2D, levels, glInternalFormat, mipmaps[ 0 ].width, mipmaps[ 0 ].height );

					}

					for ( let i = 0, il = mipmaps.length; i < il; i ++ ) {

						mipmap = mipmaps[ i ];

						if ( useTexStorage ) {

							if ( dataReady ) {

								state.texSubImage2D( _gl.TEXTURE_2D, i, 0, 0, mipmap.width, mipmap.height, glFormat, glType, mipmap.data );

							}

						} else {

							state.texImage2D( _gl.TEXTURE_2D, i, glInternalFormat, mipmap.width, mipmap.height, 0, glFormat, glType, mipmap.data );

						}

					}

					texture.generateMipmaps = false;

				} else {

					if ( useTexStorage ) {

						if ( allocateMemory ) {

							state.texStorage2D( _gl.TEXTURE_2D, levels, glInternalFormat, image.width, image.height );

						}

						if ( dataReady ) {

							updateTexture( texture, image, glFormat, glType );

						}

					} else {

						state.texImage2D( _gl.TEXTURE_2D, 0, glInternalFormat, image.width, image.height, 0, glFormat, glType, image.data );

					}

				}

			} else if ( texture.isCompressedTexture ) {

				if ( texture.isCompressedArrayTexture ) {

					if ( useTexStorage && allocateMemory ) {

						state.texStorage3D( _gl.TEXTURE_2D_ARRAY, levels, glInternalFormat, mipmaps[ 0 ].width, mipmaps[ 0 ].height, image.depth );

					}

					for ( let i = 0, il = mipmaps.length; i < il; i ++ ) {

						mipmap = mipmaps[ i ];

						if ( texture.format !== RGBAFormat ) {

							if ( glFormat !== null ) {

								if ( useTexStorage ) {

									if ( dataReady ) {

										if ( texture.layerUpdates.size > 0 ) {

											const layerByteLength = getByteLength( mipmap.width, mipmap.height, texture.format, texture.type );

											for ( const layerIndex of texture.layerUpdates ) {

												const layerData = mipmap.data.subarray(
													layerIndex * layerByteLength / mipmap.data.BYTES_PER_ELEMENT,
													( layerIndex + 1 ) * layerByteLength / mipmap.data.BYTES_PER_ELEMENT
												);
												state.compressedTexSubImage3D( _gl.TEXTURE_2D_ARRAY, i, 0, 0, layerIndex, mipmap.width, mipmap.height, 1, glFormat, layerData );

											}

											texture.clearLayerUpdates();

										} else {

											state.compressedTexSubImage3D( _gl.TEXTURE_2D_ARRAY, i, 0, 0, 0, mipmap.width, mipmap.height, image.depth, glFormat, mipmap.data );

										}

									}

								} else {

									state.compressedTexImage3D( _gl.TEXTURE_2D_ARRAY, i, glInternalFormat, mipmap.width, mipmap.height, image.depth, 0, mipmap.data, 0, 0 );

								}

							} else {

								console.warn( 'THREE.WebGLRenderer: Attempt to load unsupported compressed texture format in .uploadTexture()' );

							}

						} else {

							if ( useTexStorage ) {

								if ( dataReady ) {

									state.texSubImage3D( _gl.TEXTURE_2D_ARRAY, i, 0, 0, 0, mipmap.width, mipmap.height, image.depth, glFormat, glType, mipmap.data );

								}

							} else {

								state.texImage3D( _gl.TEXTURE_2D_ARRAY, i, glInternalFormat, mipmap.width, mipmap.height, image.depth, 0, glFormat, glType, mipmap.data );

							}

						}

					}

				} else {

					if ( useTexStorage && allocateMemory ) {

						state.texStorage2D( _gl.TEXTURE_2D, levels, glInternalFormat, mipmaps[ 0 ].width, mipmaps[ 0 ].height );

					}

					for ( let i = 0, il = mipmaps.length; i < il; i ++ ) {

						mipmap = mipmaps[ i ];

						if ( texture.format !== RGBAFormat ) {

							if ( glFormat !== null ) {

								if ( useTexStorage ) {

									if ( dataReady ) {

										state.compressedTexSubImage2D( _gl.TEXTURE_2D, i, 0, 0, mipmap.width, mipmap.height, glFormat, mipmap.data );

									}

								} else {

									state.compressedTexImage2D( _gl.TEXTURE_2D, i, glInternalFormat, mipmap.width, mipmap.height, 0, mipmap.data );

								}

							} else {

								console.warn( 'THREE.WebGLRenderer: Attempt to load unsupported compressed texture format in .uploadTexture()' );

							}

						} else {

							if ( useTexStorage ) {

								if ( dataReady ) {

									state.texSubImage2D( _gl.TEXTURE_2D, i, 0, 0, mipmap.width, mipmap.height, glFormat, glType, mipmap.data );

								}

							} else {

								state.texImage2D( _gl.TEXTURE_2D, i, glInternalFormat, mipmap.width, mipmap.height, 0, glFormat, glType, mipmap.data );

							}

						}

					}

				}

			} else if ( texture.isDataArrayTexture ) {

				if ( useTexStorage ) {

					if ( allocateMemory ) {

						state.texStorage3D( _gl.TEXTURE_2D_ARRAY, levels, glInternalFormat, image.width, image.height, image.depth );

					}

					if ( dataReady ) {

						if ( texture.layerUpdates.size > 0 ) {

							const layerByteLength = getByteLength( image.width, image.height, texture.format, texture.type );

							for ( const layerIndex of texture.layerUpdates ) {

								const layerData = image.data.subarray(
									layerIndex * layerByteLength / image.data.BYTES_PER_ELEMENT,
									( layerIndex + 1 ) * layerByteLength / image.data.BYTES_PER_ELEMENT
								);
								state.texSubImage3D( _gl.TEXTURE_2D_ARRAY, 0, 0, 0, layerIndex, image.width, image.height, 1, glFormat, glType, layerData );

							}

							texture.clearLayerUpdates();

						} else {

							state.texSubImage3D( _gl.TEXTURE_2D_ARRAY, 0, 0, 0, 0, image.width, image.height, image.depth, glFormat, glType, image.data );

						}

					}

				} else {

					state.texImage3D( _gl.TEXTURE_2D_ARRAY, 0, glInternalFormat, image.width, image.height, image.depth, 0, glFormat, glType, image.data );

				}

			} else if ( texture.isData3DTexture ) {

				if ( useTexStorage ) {

					if ( allocateMemory ) {

						state.texStorage3D( _gl.TEXTURE_3D, levels, glInternalFormat, image.width, image.height, image.depth );

					}

					if ( dataReady ) {

						state.texSubImage3D( _gl.TEXTURE_3D, 0, 0, 0, 0, image.width, image.height, image.depth, glFormat, glType, image.data );

					}

				} else {

					state.texImage3D( _gl.TEXTURE_3D, 0, glInternalFormat, image.width, image.height, image.depth, 0, glFormat, glType, image.data );

				}

			} else if ( texture.isFramebufferTexture ) {

				if ( allocateMemory ) {

					if ( useTexStorage ) {

						state.texStorage2D( _gl.TEXTURE_2D, levels, glInternalFormat, image.width, image.height );

					} else {

						let width = image.width, height = image.height;

						for ( let i = 0; i < levels; i ++ ) {

							state.texImage2D( _gl.TEXTURE_2D, i, glInternalFormat, width, height, 0, glFormat, glType, null );

							width >>= 1;
							height >>= 1;

						}

					}

				}

			} else {

				// regular Texture (image, video, canvas)

				// use manually created mipmaps if available
				// if there are no manual mipmaps
				// set 0 level mipmap and then use GL to generate other mipmap levels

				if ( mipmaps.length > 0 ) {

					if ( useTexStorage && allocateMemory ) {

						const dimensions = getDimensions( mipmaps[ 0 ] );

						state.texStorage2D( _gl.TEXTURE_2D, levels, glInternalFormat, dimensions.width, dimensions.height );

					}

					for ( let i = 0, il = mipmaps.length; i < il; i ++ ) {

						mipmap = mipmaps[ i ];

						if ( useTexStorage ) {

							if ( dataReady ) {

								state.texSubImage2D( _gl.TEXTURE_2D, i, 0, 0, glFormat, glType, mipmap );

							}

						} else {

							state.texImage2D( _gl.TEXTURE_2D, i, glInternalFormat, glFormat, glType, mipmap );

						}

					}

					texture.generateMipmaps = false;

				} else {

					if ( useTexStorage ) {

						if ( allocateMemory ) {

							const dimensions = getDimensions( image );

							state.texStorage2D( _gl.TEXTURE_2D, levels, glInternalFormat, dimensions.width, dimensions.height );

						}

						if ( dataReady ) {

							state.texSubImage2D( _gl.TEXTURE_2D, 0, 0, 0, glFormat, glType, image );

						}

					} else {

						state.texImage2D( _gl.TEXTURE_2D, 0, glInternalFormat, glFormat, glType, image );

					}

				}

			}

			if ( textureNeedsGenerateMipmaps( texture ) ) {

				generateMipmap( textureType );

			}

			sourceProperties.__version = source.version;

			if ( texture.onUpdate ) texture.onUpdate( texture );

		}

		textureProperties.__version = texture.version;

	}
```
</details>

### `uploadCubeTexture(textureProperties: any, texture: any, slot: any): void`

**Parameters:**

- **`textureProperties`** `any`
- **`texture`** `any`
- **`slot`** `any`

**Returns:** `void`

**Calls:**

- `initTexture`
- `state.bindTexture`
- `properties.get`
- `state.activeTexture`
- `ColorManagement.getPrimaries`
- `_gl.pixelStorei`
- `resizeImage`
- `verifyColorSpace`
- `utils.convert`
- `getInternalFormat`
- `getMipLevels`
- `setTextureParameters`
- `state.texStorage2D`
- `state.compressedTexSubImage2D`
- `state.compressedTexImage2D`
- `console.warn`
- `state.texSubImage2D`
- `state.texImage2D`
- `getDimensions`
- `textureNeedsGenerateMipmaps`
- `generateMipmap`
- `texture.onUpdate`

**Internal Comments:**
```
// TODO: Uniformly handle mipmap definitions
// Normal textures and compressed cube textures define base level + mips with their mipmap array
// Uncompressed cube textures use their mipmap array only for mips (no base level)
// We assume images for cube map have the same size. (x3)
```

<details><summary>Code</summary>

```typescript
function uploadCubeTexture( textureProperties, texture, slot ) {

		if ( texture.image.length !== 6 ) return;

		const forceUpload = initTexture( textureProperties, texture );
		const source = texture.source;

		state.bindTexture( _gl.TEXTURE_CUBE_MAP, textureProperties.__webglTexture, _gl.TEXTURE0 + slot );

		const sourceProperties = properties.get( source );

		if ( source.version !== sourceProperties.__version || forceUpload === true ) {

			state.activeTexture( _gl.TEXTURE0 + slot );

			const workingPrimaries = ColorManagement.getPrimaries( ColorManagement.workingColorSpace );
			const texturePrimaries = texture.colorSpace === NoColorSpace ? null : ColorManagement.getPrimaries( texture.colorSpace );
			const unpackConversion = texture.colorSpace === NoColorSpace || workingPrimaries === texturePrimaries ? _gl.NONE : _gl.BROWSER_DEFAULT_WEBGL;

			_gl.pixelStorei( _gl.UNPACK_FLIP_Y_WEBGL, texture.flipY );
			_gl.pixelStorei( _gl.UNPACK_PREMULTIPLY_ALPHA_WEBGL, texture.premultiplyAlpha );
			_gl.pixelStorei( _gl.UNPACK_ALIGNMENT, texture.unpackAlignment );
			_gl.pixelStorei( _gl.UNPACK_COLORSPACE_CONVERSION_WEBGL, unpackConversion );

			const isCompressed = ( texture.isCompressedTexture || texture.image[ 0 ].isCompressedTexture );
			const isDataTexture = ( texture.image[ 0 ] && texture.image[ 0 ].isDataTexture );

			const cubeImage = [];

			for ( let i = 0; i < 6; i ++ ) {

				if ( ! isCompressed && ! isDataTexture ) {

					cubeImage[ i ] = resizeImage( texture.image[ i ], true, capabilities.maxCubemapSize );

				} else {

					cubeImage[ i ] = isDataTexture ? texture.image[ i ].image : texture.image[ i ];

				}

				cubeImage[ i ] = verifyColorSpace( texture, cubeImage[ i ] );

			}

			const image = cubeImage[ 0 ],
				glFormat = utils.convert( texture.format, texture.colorSpace ),
				glType = utils.convert( texture.type ),
				glInternalFormat = getInternalFormat( texture.internalFormat, glFormat, glType, texture.colorSpace );

			const useTexStorage = ( texture.isVideoTexture !== true );
			const allocateMemory = ( sourceProperties.__version === undefined ) || ( forceUpload === true );
			const dataReady = source.dataReady;
			let levels = getMipLevels( texture, image );

			setTextureParameters( _gl.TEXTURE_CUBE_MAP, texture );

			let mipmaps;

			if ( isCompressed ) {

				if ( useTexStorage && allocateMemory ) {

					state.texStorage2D( _gl.TEXTURE_CUBE_MAP, levels, glInternalFormat, image.width, image.height );

				}

				for ( let i = 0; i < 6; i ++ ) {

					mipmaps = cubeImage[ i ].mipmaps;

					for ( let j = 0; j < mipmaps.length; j ++ ) {

						const mipmap = mipmaps[ j ];

						if ( texture.format !== RGBAFormat ) {

							if ( glFormat !== null ) {

								if ( useTexStorage ) {

									if ( dataReady ) {

										state.compressedTexSubImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, j, 0, 0, mipmap.width, mipmap.height, glFormat, mipmap.data );

									}

								} else {

									state.compressedTexImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, j, glInternalFormat, mipmap.width, mipmap.height, 0, mipmap.data );

								}

							} else {

								console.warn( 'THREE.WebGLRenderer: Attempt to load unsupported compressed texture format in .setTextureCube()' );

							}

						} else {

							if ( useTexStorage ) {

								if ( dataReady ) {

									state.texSubImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, j, 0, 0, mipmap.width, mipmap.height, glFormat, glType, mipmap.data );

								}

							} else {

								state.texImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, j, glInternalFormat, mipmap.width, mipmap.height, 0, glFormat, glType, mipmap.data );

							}

						}

					}

				}

			} else {

				mipmaps = texture.mipmaps;

				if ( useTexStorage && allocateMemory ) {

					// TODO: Uniformly handle mipmap definitions
					// Normal textures and compressed cube textures define base level + mips with their mipmap array
					// Uncompressed cube textures use their mipmap array only for mips (no base level)

					if ( mipmaps.length > 0 ) levels ++;

					const dimensions = getDimensions( cubeImage[ 0 ] );

					state.texStorage2D( _gl.TEXTURE_CUBE_MAP, levels, glInternalFormat, dimensions.width, dimensions.height );

				}

				for ( let i = 0; i < 6; i ++ ) {

					if ( isDataTexture ) {

						if ( useTexStorage ) {

							if ( dataReady ) {

								state.texSubImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, 0, 0, 0, cubeImage[ i ].width, cubeImage[ i ].height, glFormat, glType, cubeImage[ i ].data );

							}

						} else {

							state.texImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, 0, glInternalFormat, cubeImage[ i ].width, cubeImage[ i ].height, 0, glFormat, glType, cubeImage[ i ].data );

						}

						for ( let j = 0; j < mipmaps.length; j ++ ) {

							const mipmap = mipmaps[ j ];
							const mipmapImage = mipmap.image[ i ].image;

							if ( useTexStorage ) {

								if ( dataReady ) {

									state.texSubImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, j + 1, 0, 0, mipmapImage.width, mipmapImage.height, glFormat, glType, mipmapImage.data );

								}

							} else {

								state.texImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, j + 1, glInternalFormat, mipmapImage.width, mipmapImage.height, 0, glFormat, glType, mipmapImage.data );

							}

						}

					} else {

						if ( useTexStorage ) {

							if ( dataReady ) {

								state.texSubImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, 0, 0, 0, glFormat, glType, cubeImage[ i ] );

							}

						} else {

							state.texImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, 0, glInternalFormat, glFormat, glType, cubeImage[ i ] );

						}

						for ( let j = 0; j < mipmaps.length; j ++ ) {

							const mipmap = mipmaps[ j ];

							if ( useTexStorage ) {

								if ( dataReady ) {

									state.texSubImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, j + 1, 0, 0, glFormat, glType, mipmap.image[ i ] );

								}

							} else {

								state.texImage2D( _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, j + 1, glInternalFormat, glFormat, glType, mipmap.image[ i ] );

							}

						}

					}

				}

			}

			if ( textureNeedsGenerateMipmaps( texture ) ) {

				// We assume images for cube map have the same size.
				generateMipmap( _gl.TEXTURE_CUBE_MAP );

			}

			sourceProperties.__version = source.version;

			if ( texture.onUpdate ) texture.onUpdate( texture );

		}

		textureProperties.__version = texture.version;

	}
```
</details>

### `setupFrameBufferTexture(framebuffer: any, renderTarget: any, texture: any, attachment: any, textureTarget: any, level: any): void`

**Parameters:**

- **`framebuffer`** `any`
- **`renderTarget`** `any`
- **`texture`** `any`
- **`attachment`** `any`
- **`textureTarget`** `any`
- **`level`** `any`

**Returns:** `void`

**Calls:**

- `utils.convert`
- `getInternalFormat`
- `properties.get`
- `Math.max`
- `state.texImage3D`
- `state.texImage2D`
- `state.bindFramebuffer`
- `useMultisampledRTT`
- `multisampledRTTExt.framebufferTexture2DMultisampleEXT`
- `getRenderTargetSamples`
- `_gl.framebufferTexture2D`

<details><summary>Code</summary>

```typescript
function setupFrameBufferTexture( framebuffer, renderTarget, texture, attachment, textureTarget, level ) {

		const glFormat = utils.convert( texture.format, texture.colorSpace );
		const glType = utils.convert( texture.type );
		const glInternalFormat = getInternalFormat( texture.internalFormat, glFormat, glType, texture.colorSpace );
		const renderTargetProperties = properties.get( renderTarget );
		const textureProperties = properties.get( texture );

		textureProperties.__renderTarget = renderTarget;

		if ( ! renderTargetProperties.__hasExternalTextures ) {

			const width = Math.max( 1, renderTarget.width >> level );
			const height = Math.max( 1, renderTarget.height >> level );

			if ( textureTarget === _gl.TEXTURE_3D || textureTarget === _gl.TEXTURE_2D_ARRAY ) {

				state.texImage3D( textureTarget, level, glInternalFormat, width, height, renderTarget.depth, 0, glFormat, glType, null );

			} else {

				state.texImage2D( textureTarget, level, glInternalFormat, width, height, 0, glFormat, glType, null );

			}

		}

		state.bindFramebuffer( _gl.FRAMEBUFFER, framebuffer );

		if ( useMultisampledRTT( renderTarget ) ) {

			multisampledRTTExt.framebufferTexture2DMultisampleEXT( _gl.FRAMEBUFFER, attachment, textureTarget, textureProperties.__webglTexture, 0, getRenderTargetSamples( renderTarget ) );

		} else if ( textureTarget === _gl.TEXTURE_2D || ( textureTarget >= _gl.TEXTURE_CUBE_MAP_POSITIVE_X && textureTarget <= _gl.TEXTURE_CUBE_MAP_NEGATIVE_Z ) ) { // see #24753

			_gl.framebufferTexture2D( _gl.FRAMEBUFFER, attachment, textureTarget, textureProperties.__webglTexture, level );

		}

		state.bindFramebuffer( _gl.FRAMEBUFFER, null );

	}
```
</details>

### `setupRenderBufferStorage(renderbuffer: any, renderTarget: any, isMultisample: any): void`

**Parameters:**

- **`renderbuffer`** `any`
- **`renderTarget`** `any`
- **`isMultisample`** `any`

**Returns:** `void`

**Calls:**

- `_gl.bindRenderbuffer`
- `getInternalDepthFormat`
- `getRenderTargetSamples`
- `useMultisampledRTT`
- `multisampledRTTExt.renderbufferStorageMultisampleEXT`
- `_gl.renderbufferStorageMultisample`
- `_gl.renderbufferStorage`
- `_gl.framebufferRenderbuffer`
- `utils.convert`
- `getInternalFormat`

**Internal Comments:**
```
// retrieve the depth attachment types (x2)
// set up the attachment (x2)
```

<details><summary>Code</summary>

```typescript
function setupRenderBufferStorage( renderbuffer, renderTarget, isMultisample ) {

		_gl.bindRenderbuffer( _gl.RENDERBUFFER, renderbuffer );

		if ( renderTarget.depthBuffer ) {

			// retrieve the depth attachment types
			const depthTexture = renderTarget.depthTexture;
			const depthType = depthTexture && depthTexture.isDepthTexture ? depthTexture.type : null;
			const glInternalFormat = getInternalDepthFormat( renderTarget.stencilBuffer, depthType );
			const glAttachmentType = renderTarget.stencilBuffer ? _gl.DEPTH_STENCIL_ATTACHMENT : _gl.DEPTH_ATTACHMENT;

			// set up the attachment
			const samples = getRenderTargetSamples( renderTarget );
			const isUseMultisampledRTT = useMultisampledRTT( renderTarget );
			if ( isUseMultisampledRTT ) {

				multisampledRTTExt.renderbufferStorageMultisampleEXT( _gl.RENDERBUFFER, samples, glInternalFormat, renderTarget.width, renderTarget.height );

			} else if ( isMultisample ) {

				_gl.renderbufferStorageMultisample( _gl.RENDERBUFFER, samples, glInternalFormat, renderTarget.width, renderTarget.height );

			} else {

				_gl.renderbufferStorage( _gl.RENDERBUFFER, glInternalFormat, renderTarget.width, renderTarget.height );

			}

			_gl.framebufferRenderbuffer( _gl.FRAMEBUFFER, glAttachmentType, _gl.RENDERBUFFER, renderbuffer );

		} else {

			const textures = renderTarget.textures;

			for ( let i = 0; i < textures.length; i ++ ) {

				const texture = textures[ i ];

				const glFormat = utils.convert( texture.format, texture.colorSpace );
				const glType = utils.convert( texture.type );
				const glInternalFormat = getInternalFormat( texture.internalFormat, glFormat, glType, texture.colorSpace );
				const samples = getRenderTargetSamples( renderTarget );

				if ( isMultisample && useMultisampledRTT( renderTarget ) === false ) {

					_gl.renderbufferStorageMultisample( _gl.RENDERBUFFER, samples, glInternalFormat, renderTarget.width, renderTarget.height );

				} else if ( useMultisampledRTT( renderTarget ) ) {

					multisampledRTTExt.renderbufferStorageMultisampleEXT( _gl.RENDERBUFFER, samples, glInternalFormat, renderTarget.width, renderTarget.height );

				} else {

					_gl.renderbufferStorage( _gl.RENDERBUFFER, glInternalFormat, renderTarget.width, renderTarget.height );

				}

			}

		}

		_gl.bindRenderbuffer( _gl.RENDERBUFFER, null );

	}
```
</details>

### `setupDepthTexture(framebuffer: any, renderTarget: any): void`

**Parameters:**

- **`framebuffer`** `any`
- **`renderTarget`** `any`

**Returns:** `void`

**Calls:**

- `state.bindFramebuffer`
- `properties.get`
- `setTexture2D`
- `getRenderTargetSamples`
- `useMultisampledRTT`
- `multisampledRTTExt.framebufferTexture2DMultisampleEXT`
- `_gl.framebufferTexture2D`

**Internal Comments:**
```
// upload an empty depth texture with framebuffer size
```

<details><summary>Code</summary>

```typescript
function setupDepthTexture( framebuffer, renderTarget ) {

		const isCube = ( renderTarget && renderTarget.isWebGLCubeRenderTarget );
		if ( isCube ) throw new Error( 'Depth Texture with cube render targets is not supported' );

		state.bindFramebuffer( _gl.FRAMEBUFFER, framebuffer );

		if ( ! ( renderTarget.depthTexture && renderTarget.depthTexture.isDepthTexture ) ) {

			throw new Error( 'renderTarget.depthTexture must be an instance of THREE.DepthTexture' );

		}

		const textureProperties = properties.get( renderTarget.depthTexture );
		textureProperties.__renderTarget = renderTarget;

		// upload an empty depth texture with framebuffer size
		if ( ! textureProperties.__webglTexture ||
				renderTarget.depthTexture.image.width !== renderTarget.width ||
				renderTarget.depthTexture.image.height !== renderTarget.height ) {

			renderTarget.depthTexture.image.width = renderTarget.width;
			renderTarget.depthTexture.image.height = renderTarget.height;
			renderTarget.depthTexture.needsUpdate = true;

		}

		setTexture2D( renderTarget.depthTexture, 0 );

		const webglDepthTexture = textureProperties.__webglTexture;
		const samples = getRenderTargetSamples( renderTarget );

		if ( renderTarget.depthTexture.format === DepthFormat ) {

			if ( useMultisampledRTT( renderTarget ) ) {

				multisampledRTTExt.framebufferTexture2DMultisampleEXT( _gl.FRAMEBUFFER, _gl.DEPTH_ATTACHMENT, _gl.TEXTURE_2D, webglDepthTexture, 0, samples );

			} else {

				_gl.framebufferTexture2D( _gl.FRAMEBUFFER, _gl.DEPTH_ATTACHMENT, _gl.TEXTURE_2D, webglDepthTexture, 0 );

			}

		} else if ( renderTarget.depthTexture.format === DepthStencilFormat ) {

			if ( useMultisampledRTT( renderTarget ) ) {

				multisampledRTTExt.framebufferTexture2DMultisampleEXT( _gl.FRAMEBUFFER, _gl.DEPTH_STENCIL_ATTACHMENT, _gl.TEXTURE_2D, webglDepthTexture, 0, samples );

			} else {

				_gl.framebufferTexture2D( _gl.FRAMEBUFFER, _gl.DEPTH_STENCIL_ATTACHMENT, _gl.TEXTURE_2D, webglDepthTexture, 0 );

			}

		} else {

			throw new Error( 'Unknown depthTexture format' );

		}

	}
```
</details>

### `setupDepthRenderbuffer(renderTarget: any): void`

**Parameters:**

- **`renderTarget`** `any`

**Returns:** `void`

**Calls:**

- `properties.get`
- `renderTargetProperties.__depthDisposeCallback`
- `depthTexture.removeEventListener`
- `depthTexture.addEventListener`
- `setupDepthTexture`
- `state.bindFramebuffer`
- `_gl.createRenderbuffer`
- `setupRenderBufferStorage`
- `_gl.bindRenderbuffer`
- `_gl.framebufferRenderbuffer`

**Internal Comments:**
```
// if the bound depth texture has changed
// fire the dispose event to get rid of stored state associated with the previously bound depth buffer (x2)
// set up dispose listeners to track when the currently attached buffer is implicitly unbound
// attach buffer if it's been created already (x4)
```

<details><summary>Code</summary>

```typescript
function setupDepthRenderbuffer( renderTarget ) {

		const renderTargetProperties = properties.get( renderTarget );
		const isCube = ( renderTarget.isWebGLCubeRenderTarget === true );

		// if the bound depth texture has changed
		if ( renderTargetProperties.__boundDepthTexture !== renderTarget.depthTexture ) {

			// fire the dispose event to get rid of stored state associated with the previously bound depth buffer
			const depthTexture = renderTarget.depthTexture;
			if ( renderTargetProperties.__depthDisposeCallback ) {

				renderTargetProperties.__depthDisposeCallback();

			}

			// set up dispose listeners to track when the currently attached buffer is implicitly unbound
			if ( depthTexture ) {

				const disposeEvent = () => {

					delete renderTargetProperties.__boundDepthTexture;
					delete renderTargetProperties.__depthDisposeCallback;
					depthTexture.removeEventListener( 'dispose', disposeEvent );

				};

				depthTexture.addEventListener( 'dispose', disposeEvent );
				renderTargetProperties.__depthDisposeCallback = disposeEvent;

			}

			renderTargetProperties.__boundDepthTexture = depthTexture;

		}

		if ( renderTarget.depthTexture && ! renderTargetProperties.__autoAllocateDepthBuffer ) {

			if ( isCube ) throw new Error( 'target.depthTexture not supported in Cube render targets' );

			const mipmaps = renderTarget.texture.mipmaps;

			if ( mipmaps && mipmaps.length > 0 ) {

				setupDepthTexture( renderTargetProperties.__webglFramebuffer[ 0 ], renderTarget );

			} else {

				setupDepthTexture( renderTargetProperties.__webglFramebuffer, renderTarget );

			}

		} else {

			if ( isCube ) {

				renderTargetProperties.__webglDepthbuffer = [];

				for ( let i = 0; i < 6; i ++ ) {

					state.bindFramebuffer( _gl.FRAMEBUFFER, renderTargetProperties.__webglFramebuffer[ i ] );

					if ( renderTargetProperties.__webglDepthbuffer[ i ] === undefined ) {

						renderTargetProperties.__webglDepthbuffer[ i ] = _gl.createRenderbuffer();
						setupRenderBufferStorage( renderTargetProperties.__webglDepthbuffer[ i ], renderTarget, false );

					} else {

						// attach buffer if it's been created already
						const glAttachmentType = renderTarget.stencilBuffer ? _gl.DEPTH_STENCIL_ATTACHMENT : _gl.DEPTH_ATTACHMENT;
						const renderbuffer = renderTargetProperties.__webglDepthbuffer[ i ];
						_gl.bindRenderbuffer( _gl.RENDERBUFFER, renderbuffer );
						_gl.framebufferRenderbuffer( _gl.FRAMEBUFFER, glAttachmentType, _gl.RENDERBUFFER, renderbuffer );

					}

				}

			} else {

				const mipmaps = renderTarget.texture.mipmaps;

				if ( mipmaps && mipmaps.length > 0 ) {

					state.bindFramebuffer( _gl.FRAMEBUFFER, renderTargetProperties.__webglFramebuffer[ 0 ] );

				} else {

					state.bindFramebuffer( _gl.FRAMEBUFFER, renderTargetProperties.__webglFramebuffer );

				}

				if ( renderTargetProperties.__webglDepthbuffer === undefined ) {

					renderTargetProperties.__webglDepthbuffer = _gl.createRenderbuffer();
					setupRenderBufferStorage( renderTargetProperties.__webglDepthbuffer, renderTarget, false );

				} else {

					// attach buffer if it's been created already
					const glAttachmentType = renderTarget.stencilBuffer ? _gl.DEPTH_STENCIL_ATTACHMENT : _gl.DEPTH_ATTACHMENT;
					const renderbuffer = renderTargetProperties.__webglDepthbuffer;
					_gl.bindRenderbuffer( _gl.RENDERBUFFER, renderbuffer );
					_gl.framebufferRenderbuffer( _gl.FRAMEBUFFER, glAttachmentType, _gl.RENDERBUFFER, renderbuffer );

				}

			}

		}

		state.bindFramebuffer( _gl.FRAMEBUFFER, null );

	}
```
</details>

### `disposeEvent(): void`

**Returns:** `void`

**Calls:**

- `depthTexture.removeEventListener`

<details><summary>Code</summary>

```typescript
() => {

					delete renderTargetProperties.__boundDepthTexture;
					delete renderTargetProperties.__depthDisposeCallback;
					depthTexture.removeEventListener( 'dispose', disposeEvent );

				}
```
</details>

### `rebindTextures(renderTarget: any, colorTexture: any, depthTexture: any): void`

**Parameters:**

- **`renderTarget`** `any`
- **`colorTexture`** `any`
- **`depthTexture`** `any`

**Returns:** `void`

**Calls:**

- `properties.get`
- `setupFrameBufferTexture`
- `setupDepthRenderbuffer`

<details><summary>Code</summary>

```typescript
function rebindTextures( renderTarget, colorTexture, depthTexture ) {

		const renderTargetProperties = properties.get( renderTarget );

		if ( colorTexture !== undefined ) {

			setupFrameBufferTexture( renderTargetProperties.__webglFramebuffer, renderTarget, renderTarget.texture, _gl.COLOR_ATTACHMENT0, _gl.TEXTURE_2D, 0 );

		}

		if ( depthTexture !== undefined ) {

			setupDepthRenderbuffer( renderTarget );

		}

	}
```
</details>

### `setupRenderTarget(renderTarget: any): void`

**Parameters:**

- **`renderTarget`** `any`

**Returns:** `void`

**Calls:**

- `properties.get`
- `renderTarget.addEventListener`
- `_gl.createTexture`
- `_gl.createFramebuffer`
- `useMultisampledRTT`
- `state.bindFramebuffer`
- `_gl.createRenderbuffer`
- `_gl.bindRenderbuffer`
- `utils.convert`
- `getInternalFormat`
- `getRenderTargetSamples`
- `_gl.renderbufferStorageMultisample`
- `_gl.framebufferRenderbuffer`
- `setupRenderBufferStorage`
- `state.bindTexture`
- `setTextureParameters`
- `setupFrameBufferTexture`
- `textureNeedsGenerateMipmaps`
- `generateMipmap`
- `state.unbindTexture`
- `setupDepthRenderbuffer`

**Internal Comments:**
```
// Setup framebuffer
// Setup color buffer
// Setup depth and stencil buffers
```

<details><summary>Code</summary>

```typescript
function setupRenderTarget( renderTarget ) {

		const texture = renderTarget.texture;

		const renderTargetProperties = properties.get( renderTarget );
		const textureProperties = properties.get( texture );

		renderTarget.addEventListener( 'dispose', onRenderTargetDispose );

		const textures = renderTarget.textures;

		const isCube = ( renderTarget.isWebGLCubeRenderTarget === true );
		const isMultipleRenderTargets = ( textures.length > 1 );

		if ( ! isMultipleRenderTargets ) {

			if ( textureProperties.__webglTexture === undefined ) {

				textureProperties.__webglTexture = _gl.createTexture();

			}

			textureProperties.__version = texture.version;
			info.memory.textures ++;

		}

		// Setup framebuffer

		if ( isCube ) {

			renderTargetProperties.__webglFramebuffer = [];

			for ( let i = 0; i < 6; i ++ ) {

				if ( texture.mipmaps && texture.mipmaps.length > 0 ) {

					renderTargetProperties.__webglFramebuffer[ i ] = [];

					for ( let level = 0; level < texture.mipmaps.length; level ++ ) {

						renderTargetProperties.__webglFramebuffer[ i ][ level ] = _gl.createFramebuffer();

					}

				} else {

					renderTargetProperties.__webglFramebuffer[ i ] = _gl.createFramebuffer();

				}

			}

		} else {

			if ( texture.mipmaps && texture.mipmaps.length > 0 ) {

				renderTargetProperties.__webglFramebuffer = [];

				for ( let level = 0; level < texture.mipmaps.length; level ++ ) {

					renderTargetProperties.__webglFramebuffer[ level ] = _gl.createFramebuffer();

				}

			} else {

				renderTargetProperties.__webglFramebuffer = _gl.createFramebuffer();

			}

			if ( isMultipleRenderTargets ) {

				for ( let i = 0, il = textures.length; i < il; i ++ ) {

					const attachmentProperties = properties.get( textures[ i ] );

					if ( attachmentProperties.__webglTexture === undefined ) {

						attachmentProperties.__webglTexture = _gl.createTexture();

						info.memory.textures ++;

					}

				}

			}

			if ( ( renderTarget.samples > 0 ) && useMultisampledRTT( renderTarget ) === false ) {

				renderTargetProperties.__webglMultisampledFramebuffer = _gl.createFramebuffer();
				renderTargetProperties.__webglColorRenderbuffer = [];

				state.bindFramebuffer( _gl.FRAMEBUFFER, renderTargetProperties.__webglMultisampledFramebuffer );

				for ( let i = 0; i < textures.length; i ++ ) {

					const texture = textures[ i ];
					renderTargetProperties.__webglColorRenderbuffer[ i ] = _gl.createRenderbuffer();

					_gl.bindRenderbuffer( _gl.RENDERBUFFER, renderTargetProperties.__webglColorRenderbuffer[ i ] );

					const glFormat = utils.convert( texture.format, texture.colorSpace );
					const glType = utils.convert( texture.type );
					const glInternalFormat = getInternalFormat( texture.internalFormat, glFormat, glType, texture.colorSpace, renderTarget.isXRRenderTarget === true );
					const samples = getRenderTargetSamples( renderTarget );
					_gl.renderbufferStorageMultisample( _gl.RENDERBUFFER, samples, glInternalFormat, renderTarget.width, renderTarget.height );

					_gl.framebufferRenderbuffer( _gl.FRAMEBUFFER, _gl.COLOR_ATTACHMENT0 + i, _gl.RENDERBUFFER, renderTargetProperties.__webglColorRenderbuffer[ i ] );

				}

				_gl.bindRenderbuffer( _gl.RENDERBUFFER, null );

				if ( renderTarget.depthBuffer ) {

					renderTargetProperties.__webglDepthRenderbuffer = _gl.createRenderbuffer();
					setupRenderBufferStorage( renderTargetProperties.__webglDepthRenderbuffer, renderTarget, true );

				}

				state.bindFramebuffer( _gl.FRAMEBUFFER, null );

			}

		}

		// Setup color buffer

		if ( isCube ) {

			state.bindTexture( _gl.TEXTURE_CUBE_MAP, textureProperties.__webglTexture );
			setTextureParameters( _gl.TEXTURE_CUBE_MAP, texture );

			for ( let i = 0; i < 6; i ++ ) {

				if ( texture.mipmaps && texture.mipmaps.length > 0 ) {

					for ( let level = 0; level < texture.mipmaps.length; level ++ ) {

						setupFrameBufferTexture( renderTargetProperties.__webglFramebuffer[ i ][ level ], renderTarget, texture, _gl.COLOR_ATTACHMENT0, _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, level );

					}

				} else {

					setupFrameBufferTexture( renderTargetProperties.__webglFramebuffer[ i ], renderTarget, texture, _gl.COLOR_ATTACHMENT0, _gl.TEXTURE_CUBE_MAP_POSITIVE_X + i, 0 );

				}

			}

			if ( textureNeedsGenerateMipmaps( texture ) ) {

				generateMipmap( _gl.TEXTURE_CUBE_MAP );

			}

			state.unbindTexture();

		} else if ( isMultipleRenderTargets ) {

			for ( let i = 0, il = textures.length; i < il; i ++ ) {

				const attachment = textures[ i ];
				const attachmentProperties = properties.get( attachment );

				let glTextureType = _gl.TEXTURE_2D;

				if ( renderTarget.isWebGL3DRenderTarget || renderTarget.isWebGLArrayRenderTarget ) {

					glTextureType = renderTarget.isWebGL3DRenderTarget ? _gl.TEXTURE_3D : _gl.TEXTURE_2D_ARRAY;

				}

				state.bindTexture( glTextureType, attachmentProperties.__webglTexture );
				setTextureParameters( glTextureType, attachment );
				setupFrameBufferTexture( renderTargetProperties.__webglFramebuffer, renderTarget, attachment, _gl.COLOR_ATTACHMENT0 + i, glTextureType, 0 );

				if ( textureNeedsGenerateMipmaps( attachment ) ) {

					generateMipmap( glTextureType );

				}

			}

			state.unbindTexture();

		} else {

			let glTextureType = _gl.TEXTURE_2D;

			if ( renderTarget.isWebGL3DRenderTarget || renderTarget.isWebGLArrayRenderTarget ) {

				glTextureType = renderTarget.isWebGL3DRenderTarget ? _gl.TEXTURE_3D : _gl.TEXTURE_2D_ARRAY;

			}

			state.bindTexture( glTextureType, textureProperties.__webglTexture );
			setTextureParameters( glTextureType, texture );

			if ( texture.mipmaps && texture.mipmaps.length > 0 ) {

				for ( let level = 0; level < texture.mipmaps.length; level ++ ) {

					setupFrameBufferTexture( renderTargetProperties.__webglFramebuffer[ level ], renderTarget, texture, _gl.COLOR_ATTACHMENT0, glTextureType, level );

				}

			} else {

				setupFrameBufferTexture( renderTargetProperties.__webglFramebuffer, renderTarget, texture, _gl.COLOR_ATTACHMENT0, glTextureType, 0 );

			}

			if ( textureNeedsGenerateMipmaps( texture ) ) {

				generateMipmap( glTextureType );

			}

			state.unbindTexture();

		}

		// Setup depth and stencil buffers

		if ( renderTarget.depthBuffer ) {

			setupDepthRenderbuffer( renderTarget );

		}

	}
```
</details>

### `updateRenderTargetMipmap(renderTarget: any): void`

**Parameters:**

- **`renderTarget`** `any`

**Returns:** `void`

**Calls:**

- `textureNeedsGenerateMipmaps`
- `getTargetType`
- `properties.get`
- `state.bindTexture`
- `generateMipmap`
- `state.unbindTexture`

<details><summary>Code</summary>

```typescript
function updateRenderTargetMipmap( renderTarget ) {

		const textures = renderTarget.textures;

		for ( let i = 0, il = textures.length; i < il; i ++ ) {

			const texture = textures[ i ];

			if ( textureNeedsGenerateMipmaps( texture ) ) {

				const targetType = getTargetType( renderTarget );
				const webglTexture = properties.get( texture ).__webglTexture;

				state.bindTexture( targetType, webglTexture );
				generateMipmap( targetType );
				state.unbindTexture();

			}

		}

	}
```
</details>

### `updateMultisampleRenderTarget(renderTarget: any): void`

**Parameters:**

- **`renderTarget`** `any`

**Returns:** `void`

**Calls:**

- `useMultisampledRTT`
- `properties.get`
- `state.bindFramebuffer`
- `_gl.framebufferRenderbuffer`
- `_gl.framebufferTexture2D`
- `_gl.blitFramebuffer`
- `invalidationArrayRead.push`
- `invalidationArrayDraw.push`
- `_gl.invalidateFramebuffer`

**Internal Comments:**
```
// If MRT we need to remove FBO attachments
// resolving stencil is slow with a D3D backend. disable it for all transmission render targets (see #27799)
// If MRT since pre-blit we removed the FBO we need to reconstruct the attachments
```

<details><summary>Code</summary>

```typescript
function updateMultisampleRenderTarget( renderTarget ) {

		if ( renderTarget.samples > 0 ) {

			if ( useMultisampledRTT( renderTarget ) === false ) {

				const textures = renderTarget.textures;
				const width = renderTarget.width;
				const height = renderTarget.height;
				let mask = _gl.COLOR_BUFFER_BIT;
				const depthStyle = renderTarget.stencilBuffer ? _gl.DEPTH_STENCIL_ATTACHMENT : _gl.DEPTH_ATTACHMENT;
				const renderTargetProperties = properties.get( renderTarget );
				const isMultipleRenderTargets = ( textures.length > 1 );

				// If MRT we need to remove FBO attachments
				if ( isMultipleRenderTargets ) {

					for ( let i = 0; i < textures.length; i ++ ) {

						state.bindFramebuffer( _gl.FRAMEBUFFER, renderTargetProperties.__webglMultisampledFramebuffer );
						_gl.framebufferRenderbuffer( _gl.FRAMEBUFFER, _gl.COLOR_ATTACHMENT0 + i, _gl.RENDERBUFFER, null );

						state.bindFramebuffer( _gl.FRAMEBUFFER, renderTargetProperties.__webglFramebuffer );
						_gl.framebufferTexture2D( _gl.DRAW_FRAMEBUFFER, _gl.COLOR_ATTACHMENT0 + i, _gl.TEXTURE_2D, null, 0 );

					}

				}

				state.bindFramebuffer( _gl.READ_FRAMEBUFFER, renderTargetProperties.__webglMultisampledFramebuffer );

				const mipmaps = renderTarget.texture.mipmaps;

				if ( mipmaps && mipmaps.length > 0 ) {

					state.bindFramebuffer( _gl.DRAW_FRAMEBUFFER, renderTargetProperties.__webglFramebuffer[ 0 ] );

				} else {

					state.bindFramebuffer( _gl.DRAW_FRAMEBUFFER, renderTargetProperties.__webglFramebuffer );

				}

				for ( let i = 0; i < textures.length; i ++ ) {

					if ( renderTarget.resolveDepthBuffer ) {

						if ( renderTarget.depthBuffer ) mask |= _gl.DEPTH_BUFFER_BIT;

						// resolving stencil is slow with a D3D backend. disable it for all transmission render targets (see #27799)

						if ( renderTarget.stencilBuffer && renderTarget.resolveStencilBuffer ) mask |= _gl.STENCIL_BUFFER_BIT;

					}

					if ( isMultipleRenderTargets ) {

						_gl.framebufferRenderbuffer( _gl.READ_FRAMEBUFFER, _gl.COLOR_ATTACHMENT0, _gl.RENDERBUFFER, renderTargetProperties.__webglColorRenderbuffer[ i ] );

						const webglTexture = properties.get( textures[ i ] ).__webglTexture;
						_gl.framebufferTexture2D( _gl.DRAW_FRAMEBUFFER, _gl.COLOR_ATTACHMENT0, _gl.TEXTURE_2D, webglTexture, 0 );

					}

					_gl.blitFramebuffer( 0, 0, width, height, 0, 0, width, height, mask, _gl.NEAREST );

					if ( supportsInvalidateFramebuffer === true ) {

						invalidationArrayRead.length = 0;
						invalidationArrayDraw.length = 0;

						invalidationArrayRead.push( _gl.COLOR_ATTACHMENT0 + i );

						if ( renderTarget.depthBuffer && renderTarget.resolveDepthBuffer === false ) {

							invalidationArrayRead.push( depthStyle );
							invalidationArrayDraw.push( depthStyle );

							_gl.invalidateFramebuffer( _gl.DRAW_FRAMEBUFFER, invalidationArrayDraw );

						}

						_gl.invalidateFramebuffer( _gl.READ_FRAMEBUFFER, invalidationArrayRead );

					}

				}

				state.bindFramebuffer( _gl.READ_FRAMEBUFFER, null );
				state.bindFramebuffer( _gl.DRAW_FRAMEBUFFER, null );

				// If MRT since pre-blit we removed the FBO we need to reconstruct the attachments
				if ( isMultipleRenderTargets ) {

					for ( let i = 0; i < textures.length; i ++ ) {

						state.bindFramebuffer( _gl.FRAMEBUFFER, renderTargetProperties.__webglMultisampledFramebuffer );
						_gl.framebufferRenderbuffer( _gl.FRAMEBUFFER, _gl.COLOR_ATTACHMENT0 + i, _gl.RENDERBUFFER, renderTargetProperties.__webglColorRenderbuffer[ i ] );

						const webglTexture = properties.get( textures[ i ] ).__webglTexture;

						state.bindFramebuffer( _gl.FRAMEBUFFER, renderTargetProperties.__webglFramebuffer );
						_gl.framebufferTexture2D( _gl.DRAW_FRAMEBUFFER, _gl.COLOR_ATTACHMENT0 + i, _gl.TEXTURE_2D, webglTexture, 0 );

					}

				}

				state.bindFramebuffer( _gl.DRAW_FRAMEBUFFER, renderTargetProperties.__webglMultisampledFramebuffer );

			} else {

				if ( renderTarget.depthBuffer && renderTarget.resolveDepthBuffer === false && supportsInvalidateFramebuffer ) {

					const depthStyle = renderTarget.stencilBuffer ? _gl.DEPTH_STENCIL_ATTACHMENT : _gl.DEPTH_ATTACHMENT;

					_gl.invalidateFramebuffer( _gl.DRAW_FRAMEBUFFER, [ depthStyle ] );

				}

			}

		}

	}
```
</details>

### `getRenderTargetSamples(renderTarget: any): number`

**Parameters:**

- **`renderTarget`** `any`

**Returns:** `number`

**Calls:**

- `Math.min`

<details><summary>Code</summary>

```typescript
function getRenderTargetSamples( renderTarget ) {

		return Math.min( capabilities.maxSamples, renderTarget.samples );

	}
```
</details>

### `useMultisampledRTT(renderTarget: any): boolean`

**Parameters:**

- **`renderTarget`** `any`

**Returns:** `boolean`

**Calls:**

- `properties.get`
- `extensions.has`

<details><summary>Code</summary>

```typescript
function useMultisampledRTT( renderTarget ) {

		const renderTargetProperties = properties.get( renderTarget );

		return renderTarget.samples > 0 && extensions.has( 'WEBGL_multisampled_render_to_texture' ) === true && renderTargetProperties.__useRenderToTexture !== false;

	}
```
</details>

### `updateVideoTexture(texture: any): void`

**Parameters:**

- **`texture`** `any`

**Returns:** `void`

**Calls:**

- `_videoTextures.get`
- `_videoTextures.set`
- `texture.update`

**Internal Comments:**
```
// Check the last frame we updated the VideoTexture
```

<details><summary>Code</summary>

```typescript
function updateVideoTexture( texture ) {

		const frame = info.render.frame;

		// Check the last frame we updated the VideoTexture

		if ( _videoTextures.get( texture ) !== frame ) {

			_videoTextures.set( texture, frame );
			texture.update();

		}

	}
```
</details>

### `verifyColorSpace(texture: any, image: any): any`

**Parameters:**

- **`texture`** `any`
- **`image`** `any`

**Returns:** `any`

**Calls:**

- `ColorManagement.getTransfer`
- `console.warn`
- `console.error`

**Internal Comments:**
```
// sRGB
// in WebGL 2 uncompressed textures can only be sRGB encoded if they have the RGBA8 format
```

<details><summary>Code</summary>

```typescript
function verifyColorSpace( texture, image ) {

		const colorSpace = texture.colorSpace;
		const format = texture.format;
		const type = texture.type;

		if ( texture.isCompressedTexture === true || texture.isVideoTexture === true ) return image;

		if ( colorSpace !== LinearSRGBColorSpace && colorSpace !== NoColorSpace ) {

			// sRGB

			if ( ColorManagement.getTransfer( colorSpace ) === SRGBTransfer ) {

				// in WebGL 2 uncompressed textures can only be sRGB encoded if they have the RGBA8 format

				if ( format !== RGBAFormat || type !== UnsignedByteType ) {

					console.warn( 'THREE.WebGLTextures: sRGB encoded textures have to use RGBAFormat and UnsignedByteType.' );

				}

			} else {

				console.error( 'THREE.WebGLTextures: Unsupported texture color space:', colorSpace );

			}

		}

		return image;

	}
```
</details>

### `getDimensions(image: any): Vector2`

**Parameters:**

- **`image`** `any`

**Returns:** `Vector2`

**Internal Comments:**
```
// if intrinsic data are not available, fallback to width/height (x4)
```

<details><summary>Code</summary>

```typescript
function getDimensions( image ) {

		if ( typeof HTMLImageElement !== 'undefined' && image instanceof HTMLImageElement ) {

			// if intrinsic data are not available, fallback to width/height

			_imageDimensions.width = image.naturalWidth || image.width;
			_imageDimensions.height = image.naturalHeight || image.height;

		} else if ( typeof VideoFrame !== 'undefined' && image instanceof VideoFrame ) {

			_imageDimensions.width = image.displayWidth;
			_imageDimensions.height = image.displayHeight;

		} else {

			_imageDimensions.width = image.width;
			_imageDimensions.height = image.height;

		}

		return _imageDimensions;

	}
```
</details>


---