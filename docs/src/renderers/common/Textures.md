[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Textures.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 18 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/Textures.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DataMap` | `./DataMap.js` |
| `Vector3` | `../../math/Vector3.js` |
| `DepthTexture` | `../../textures/DepthTexture.js` |
| `DepthStencilFormat` | `../../constants.js` |
| `DepthFormat` | `../../constants.js` |
| `UnsignedIntType` | `../../constants.js` |
| `UnsignedInt248Type` | `../../constants.js` |
| `UnsignedByteType` | `../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_size` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `sampleCount` | `any` | let/var | `renderTarget.samples === 0 ? 1 : renderTarget.samples` | ✗ |
| `depthTextureMips` | `any` | let/var | `renderTargetData.depthTextureMips \|\| ( renderTargetData.depthTextureMips = ...` | ✗ |
| `textures` | `any` | let/var | `renderTarget.textures` | ✗ |
| `mipWidth` | `number` | let/var | `size.width >> activeMipmapLevel` | ✗ |
| `mipHeight` | `number` | let/var | `size.height >> activeMipmapLevel` | ✗ |
| `depthTexture` | `any` | let/var | `renderTarget.depthTexture \|\| depthTextureMips[ activeMipmapLevel ]` | ✗ |
| `useDepthTexture` | `boolean` | let/var | `renderTarget.depthBuffer === true \|\| renderTarget.stencilBuffer === true` | ✗ |
| `textureNeedsUpdate` | `boolean` | let/var | `false` | ✗ |
| `options` | `{ sampleCount: any; }` | let/var | `{ sampleCount }` | ✗ |
| `texture` | `any` | let/var | `textures[ i ]` | ✗ |
| `isRenderTarget` | `any` | let/var | `texture.isRenderTargetTexture \|\| texture.isDepthTexture \|\| texture.isFram...` | ✗ |
| `backend` | `Backend` | let/var | `this.backend` | ✗ |
| `needsCreate` | `boolean` | let/var | `textureData.initialized !== true` | ✗ |
| `image` | `any` | let/var | `texture.image` | ✗ |
| `images` | `any[]` | let/var | `[]` | ✗ |
| `image` | `any` | let/var | `texture.images ? texture.images[ 0 ] : texture.image` | ✗ |
| `mipLevelCount` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `Textures.updateRenderTarget(renderTarget: RenderTarget, activeMipmapLevel: number): void`

**JSDoc:**
```typescript
/**
	 * Updates the given render target. Based on the given render target configuration,
	 * it updates the texture states representing the attachments of the framebuffer.
	 *
	 * @param {RenderTarget} renderTarget - The render target to update.
	 * @param {number} [activeMipmapLevel=0] - The active mipmap level.
	 */
```

**Parameters:**

- **`renderTarget`** `RenderTarget`
- **`activeMipmapLevel`** `number`

**Returns:** `void`

**Calls:**

- `this.get`
- `this.getSize`
- `this.updateTexture`
- `renderTarget.removeEventListener`
- `this._destroyTexture`
- `this.delete`
- `renderTarget.addEventListener`

**Internal Comments:**
```
// (x2)
// XR render targets require no texture updates
// dispose handler
// dispose (x2)
```

<details><summary>Code</summary>

```typescript
updateRenderTarget( renderTarget, activeMipmapLevel = 0 ) {

		const renderTargetData = this.get( renderTarget );

		const sampleCount = renderTarget.samples === 0 ? 1 : renderTarget.samples;
		const depthTextureMips = renderTargetData.depthTextureMips || ( renderTargetData.depthTextureMips = {} );

		const textures = renderTarget.textures;

		const size = this.getSize( textures[ 0 ] );

		const mipWidth = size.width >> activeMipmapLevel;
		const mipHeight = size.height >> activeMipmapLevel;

		let depthTexture = renderTarget.depthTexture || depthTextureMips[ activeMipmapLevel ];
		const useDepthTexture = renderTarget.depthBuffer === true || renderTarget.stencilBuffer === true;

		let textureNeedsUpdate = false;

		if ( depthTexture === undefined && useDepthTexture ) {

			depthTexture = new DepthTexture();

			depthTexture.format = renderTarget.stencilBuffer ? DepthStencilFormat : DepthFormat;
			depthTexture.type = renderTarget.stencilBuffer ? UnsignedInt248Type : UnsignedIntType; // FloatType
			depthTexture.image.width = mipWidth;
			depthTexture.image.height = mipHeight;
			depthTexture.image.depth = size.depth;
			depthTexture.isArrayTexture = renderTarget.multiview === true && size.depth > 1;

			depthTextureMips[ activeMipmapLevel ] = depthTexture;

		}

		if ( renderTargetData.width !== size.width || size.height !== renderTargetData.height ) {

			textureNeedsUpdate = true;

			if ( depthTexture ) {

				depthTexture.needsUpdate = true;
				depthTexture.image.width = mipWidth;
				depthTexture.image.height = mipHeight;
				depthTexture.image.depth = depthTexture.isArrayTexture ? depthTexture.image.depth : 1;

			}

		}

		renderTargetData.width = size.width;
		renderTargetData.height = size.height;
		renderTargetData.textures = textures;
		renderTargetData.depthTexture = depthTexture || null;
		renderTargetData.depth = renderTarget.depthBuffer;
		renderTargetData.stencil = renderTarget.stencilBuffer;
		renderTargetData.renderTarget = renderTarget;

		if ( renderTargetData.sampleCount !== sampleCount ) {

			textureNeedsUpdate = true;

			if ( depthTexture ) {

				depthTexture.needsUpdate = true;

			}

			renderTargetData.sampleCount = sampleCount;

		}

		//


		const options = { sampleCount };

		// XR render targets require no texture updates

		if ( renderTarget.isXRRenderTarget !== true ) {

			for ( let i = 0; i < textures.length; i ++ ) {

				const texture = textures[ i ];

				if ( textureNeedsUpdate ) texture.needsUpdate = true;

				this.updateTexture( texture, options );

			}

			if ( depthTexture ) {

				this.updateTexture( depthTexture, options );

			}

		}

		// dispose handler

		if ( renderTargetData.initialized !== true ) {

			renderTargetData.initialized = true;

			// dispose

			const onDispose = () => {

				renderTarget.removeEventListener( 'dispose', onDispose );

				for ( let i = 0; i < textures.length; i ++ ) {

					this._destroyTexture( textures[ i ] );

				}

				if ( depthTexture ) {

					this._destroyTexture( depthTexture );

				}

				this.delete( renderTarget );

			};

			renderTarget.addEventListener( 'dispose', onDispose );

		}

	}
```
</details>

### `Textures.updateTexture(texture: Texture, options: any): void`

**JSDoc:**
```typescript
/**
	 * Updates the given texture. Depending on the texture state, this method
	 * triggers the upload of texture data to the GPU memory. If the texture data are
	 * not yet ready for the upload, it uses default texture data for as a placeholder.
	 *
	 * @param {Texture} texture - The texture to update.
	 * @param {Object} [options={}] - The options.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`options`** `any`

**Returns:** `void`

**Calls:**

- `this.get`
- `backend.destroySampler`
- `backend.destroyTexture`
- `this.renderer.getRenderTarget`
- `this.getSize`
- `this.needsMipmaps`
- `this.getMipLevels`
- `backend.createSampler`
- `backend.createTexture`
- `console.warn`
- `images.push`
- `backend.updateTexture`
- `backend.generateMipmaps`
- `backend.createDefaultTexture`
- `texture.removeEventListener`
- `this._destroyTexture`
- `texture.addEventListener`

**Internal Comments:**
```
// it's an update (x4)
// (x14)
// async update (x4)
// dispose handler
// dispose (x2)
```

<details><summary>Code</summary>

```typescript
updateTexture( texture, options = {} ) {

		const textureData = this.get( texture );
		if ( textureData.initialized === true && textureData.version === texture.version ) return;

		const isRenderTarget = texture.isRenderTargetTexture || texture.isDepthTexture || texture.isFramebufferTexture;
		const backend = this.backend;

		if ( isRenderTarget && textureData.initialized === true ) {

			// it's an update

			backend.destroySampler( texture );
			backend.destroyTexture( texture );

		}

		//

		if ( texture.isFramebufferTexture ) {

			const renderTarget = this.renderer.getRenderTarget();

			if ( renderTarget ) {

				texture.type = renderTarget.texture.type;

			} else {

				texture.type = UnsignedByteType;

			}

		}

		//

		const { width, height, depth } = this.getSize( texture );

		options.width = width;
		options.height = height;
		options.depth = depth;
		options.needsMipmaps = this.needsMipmaps( texture );
		options.levels = options.needsMipmaps ? this.getMipLevels( texture, width, height ) : 1;

		//

		if ( isRenderTarget || texture.isStorageTexture === true ) {

			backend.createSampler( texture );
			backend.createTexture( texture, options );

			textureData.generation = texture.version;

		} else {

			const needsCreate = textureData.initialized !== true;

			if ( needsCreate ) backend.createSampler( texture );

			if ( texture.version > 0 ) {

				const image = texture.image;

				if ( image === undefined ) {

					console.warn( 'THREE.Renderer: Texture marked for update but image is undefined.' );

				} else if ( image.complete === false ) {

					console.warn( 'THREE.Renderer: Texture marked for update but image is incomplete.' );

				} else {

					if ( texture.images ) {

						const images = [];

						for ( const image of texture.images ) {

							images.push( image );

						}

						options.images = images;

					} else {

						options.image = image;

					}

					if ( textureData.isDefaultTexture === undefined || textureData.isDefaultTexture === true ) {

						backend.createTexture( texture, options );

						textureData.isDefaultTexture = false;
						textureData.generation = texture.version;

					}

					if ( texture.source.dataReady === true ) backend.updateTexture( texture, options );

					if ( options.needsMipmaps && texture.mipmaps.length === 0 ) backend.generateMipmaps( texture );

				}

			} else {

				// async update

				backend.createDefaultTexture( texture );

				textureData.isDefaultTexture = true;
				textureData.generation = texture.version;

			}

		}

		// dispose handler

		if ( textureData.initialized !== true ) {

			textureData.initialized = true;
			textureData.generation = texture.version;

			//

			this.info.memory.textures ++;

			// dispose

			const onDispose = () => {

				texture.removeEventListener( 'dispose', onDispose );

				this._destroyTexture( texture );

			};

			texture.addEventListener( 'dispose', onDispose );

		}

		//

		textureData.version = texture.version;

	}
```
</details>

### `Textures.getSize(texture: Texture, target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Computes the size of the given texture and writes the result
	 * into the target vector. This vector is also returned by the
	 * method.
	 *
	 * If no texture data are available for the compute yet, the method
	 * returns default size values.
	 *
	 * @param {Texture} texture - The texture to compute the size for.
	 * @param {Vector3} target - The target vector.
	 * @return {Vector3} The target vector.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`target`** `Vector3`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
getSize( texture, target = _size ) {

		let image = texture.images ? texture.images[ 0 ] : texture.image;

		if ( image ) {

			if ( image.image !== undefined ) image = image.image;

			if ( image instanceof HTMLVideoElement ) {

				target.width = image.videoWidth || 1;
				target.height = image.videoHeight || 1;
				target.depth = 1;

			} else if ( image instanceof VideoFrame ) {

				target.width = image.displayWidth || 1;
				target.height = image.displayHeight || 1;
				target.depth = 1;

			} else {

				target.width = image.width || 1;
				target.height = image.height || 1;
				target.depth = texture.isCubeTexture ? 6 : ( image.depth || 1 );

			}

		} else {

			target.width = target.height = target.depth = 1;

		}

		return target;

	}
```
</details>

### `Textures.getMipLevels(texture: Texture, width: number, height: number): number`

**JSDoc:**
```typescript
/**
	 * Computes the number of mipmap levels for the given texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {number} width - The texture's width.
	 * @param {number} height - The texture's height.
	 * @return {number} The number of mipmap levels.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`width`** `number`
- **`height`** `number`

**Returns:** `number`

**Calls:**

- `Math.floor`
- `Math.log2`
- `Math.max`

<details><summary>Code</summary>

```typescript
getMipLevels( texture, width, height ) {

		let mipLevelCount;

		if ( texture.isCompressedTexture ) {

			if ( texture.mipmaps ) {

				mipLevelCount = texture.mipmaps.length;

			} else {

				mipLevelCount = 1;

			}

		} else {

			mipLevelCount = Math.floor( Math.log2( Math.max( width, height ) ) ) + 1;

		}

		return mipLevelCount;

	}
```
</details>

### `Textures.needsMipmaps(texture: Texture): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given texture requires mipmaps.
	 *
	 * @param {Texture} texture - The texture.
	 * @return {boolean} Whether mipmaps are required or not.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
needsMipmaps( texture ) {

		return texture.isCompressedTexture === true || texture.generateMipmaps;

	}
```
</details>

### `Textures._destroyTexture(texture: Texture): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resource when the given texture isn't
	 * required anymore.
	 *
	 * @param {Texture} texture - The texture to destroy.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `void`

**Calls:**

- `this.has`
- `this.backend.destroySampler`
- `this.backend.destroyTexture`
- `this.delete`

<details><summary>Code</summary>

```typescript
_destroyTexture( texture ) {

		if ( this.has( texture ) === true ) {

			this.backend.destroySampler( texture );
			this.backend.destroyTexture( texture );

			this.delete( texture );

			this.info.memory.textures --;

		}

	}
```
</details>

### `onDispose(): void`

**Returns:** `void`

**Calls:**

- `renderTarget.removeEventListener`
- `this._destroyTexture`
- `this.delete`

<details><summary>Code</summary>

```typescript
() => {

				renderTarget.removeEventListener( 'dispose', onDispose );

				for ( let i = 0; i < textures.length; i ++ ) {

					this._destroyTexture( textures[ i ] );

				}

				if ( depthTexture ) {

					this._destroyTexture( depthTexture );

				}

				this.delete( renderTarget );

			}
```
</details>

### `onDispose(): void`

**Returns:** `void`

**Calls:**

- `texture.removeEventListener`
- `this._destroyTexture`

<details><summary>Code</summary>

```typescript
() => {

				texture.removeEventListener( 'dispose', onDispose );

				this._destroyTexture( texture );

			}
```
</details>


---

## Classes

### `Textures`

<details><summary>Class Code</summary>

```ts
class Textures extends DataMap {

	/**
	 * Constructs a new texture management component.
	 *
	 * @param {Renderer} renderer - The renderer.
	 * @param {Backend} backend - The renderer's backend.
	 * @param {Info} info - Renderer component for managing metrics and monitoring data.
	 */
	constructor( renderer, backend, info ) {

		super();

		/**
		 * The renderer.
		 *
		 * @type {Renderer}
		 */
		this.renderer = renderer;

		/**
		 * The backend.
		 *
		 * @type {Backend}
		 */
		this.backend = backend;

		/**
		 * Renderer component for managing metrics and monitoring data.
		 *
		 * @type {Info}
		 */
		this.info = info;

	}

	/**
	 * Updates the given render target. Based on the given render target configuration,
	 * it updates the texture states representing the attachments of the framebuffer.
	 *
	 * @param {RenderTarget} renderTarget - The render target to update.
	 * @param {number} [activeMipmapLevel=0] - The active mipmap level.
	 */
	updateRenderTarget( renderTarget, activeMipmapLevel = 0 ) {

		const renderTargetData = this.get( renderTarget );

		const sampleCount = renderTarget.samples === 0 ? 1 : renderTarget.samples;
		const depthTextureMips = renderTargetData.depthTextureMips || ( renderTargetData.depthTextureMips = {} );

		const textures = renderTarget.textures;

		const size = this.getSize( textures[ 0 ] );

		const mipWidth = size.width >> activeMipmapLevel;
		const mipHeight = size.height >> activeMipmapLevel;

		let depthTexture = renderTarget.depthTexture || depthTextureMips[ activeMipmapLevel ];
		const useDepthTexture = renderTarget.depthBuffer === true || renderTarget.stencilBuffer === true;

		let textureNeedsUpdate = false;

		if ( depthTexture === undefined && useDepthTexture ) {

			depthTexture = new DepthTexture();

			depthTexture.format = renderTarget.stencilBuffer ? DepthStencilFormat : DepthFormat;
			depthTexture.type = renderTarget.stencilBuffer ? UnsignedInt248Type : UnsignedIntType; // FloatType
			depthTexture.image.width = mipWidth;
			depthTexture.image.height = mipHeight;
			depthTexture.image.depth = size.depth;
			depthTexture.isArrayTexture = renderTarget.multiview === true && size.depth > 1;

			depthTextureMips[ activeMipmapLevel ] = depthTexture;

		}

		if ( renderTargetData.width !== size.width || size.height !== renderTargetData.height ) {

			textureNeedsUpdate = true;

			if ( depthTexture ) {

				depthTexture.needsUpdate = true;
				depthTexture.image.width = mipWidth;
				depthTexture.image.height = mipHeight;
				depthTexture.image.depth = depthTexture.isArrayTexture ? depthTexture.image.depth : 1;

			}

		}

		renderTargetData.width = size.width;
		renderTargetData.height = size.height;
		renderTargetData.textures = textures;
		renderTargetData.depthTexture = depthTexture || null;
		renderTargetData.depth = renderTarget.depthBuffer;
		renderTargetData.stencil = renderTarget.stencilBuffer;
		renderTargetData.renderTarget = renderTarget;

		if ( renderTargetData.sampleCount !== sampleCount ) {

			textureNeedsUpdate = true;

			if ( depthTexture ) {

				depthTexture.needsUpdate = true;

			}

			renderTargetData.sampleCount = sampleCount;

		}

		//


		const options = { sampleCount };

		// XR render targets require no texture updates

		if ( renderTarget.isXRRenderTarget !== true ) {

			for ( let i = 0; i < textures.length; i ++ ) {

				const texture = textures[ i ];

				if ( textureNeedsUpdate ) texture.needsUpdate = true;

				this.updateTexture( texture, options );

			}

			if ( depthTexture ) {

				this.updateTexture( depthTexture, options );

			}

		}

		// dispose handler

		if ( renderTargetData.initialized !== true ) {

			renderTargetData.initialized = true;

			// dispose

			const onDispose = () => {

				renderTarget.removeEventListener( 'dispose', onDispose );

				for ( let i = 0; i < textures.length; i ++ ) {

					this._destroyTexture( textures[ i ] );

				}

				if ( depthTexture ) {

					this._destroyTexture( depthTexture );

				}

				this.delete( renderTarget );

			};

			renderTarget.addEventListener( 'dispose', onDispose );

		}

	}

	/**
	 * Updates the given texture. Depending on the texture state, this method
	 * triggers the upload of texture data to the GPU memory. If the texture data are
	 * not yet ready for the upload, it uses default texture data for as a placeholder.
	 *
	 * @param {Texture} texture - The texture to update.
	 * @param {Object} [options={}] - The options.
	 */
	updateTexture( texture, options = {} ) {

		const textureData = this.get( texture );
		if ( textureData.initialized === true && textureData.version === texture.version ) return;

		const isRenderTarget = texture.isRenderTargetTexture || texture.isDepthTexture || texture.isFramebufferTexture;
		const backend = this.backend;

		if ( isRenderTarget && textureData.initialized === true ) {

			// it's an update

			backend.destroySampler( texture );
			backend.destroyTexture( texture );

		}

		//

		if ( texture.isFramebufferTexture ) {

			const renderTarget = this.renderer.getRenderTarget();

			if ( renderTarget ) {

				texture.type = renderTarget.texture.type;

			} else {

				texture.type = UnsignedByteType;

			}

		}

		//

		const { width, height, depth } = this.getSize( texture );

		options.width = width;
		options.height = height;
		options.depth = depth;
		options.needsMipmaps = this.needsMipmaps( texture );
		options.levels = options.needsMipmaps ? this.getMipLevels( texture, width, height ) : 1;

		//

		if ( isRenderTarget || texture.isStorageTexture === true ) {

			backend.createSampler( texture );
			backend.createTexture( texture, options );

			textureData.generation = texture.version;

		} else {

			const needsCreate = textureData.initialized !== true;

			if ( needsCreate ) backend.createSampler( texture );

			if ( texture.version > 0 ) {

				const image = texture.image;

				if ( image === undefined ) {

					console.warn( 'THREE.Renderer: Texture marked for update but image is undefined.' );

				} else if ( image.complete === false ) {

					console.warn( 'THREE.Renderer: Texture marked for update but image is incomplete.' );

				} else {

					if ( texture.images ) {

						const images = [];

						for ( const image of texture.images ) {

							images.push( image );

						}

						options.images = images;

					} else {

						options.image = image;

					}

					if ( textureData.isDefaultTexture === undefined || textureData.isDefaultTexture === true ) {

						backend.createTexture( texture, options );

						textureData.isDefaultTexture = false;
						textureData.generation = texture.version;

					}

					if ( texture.source.dataReady === true ) backend.updateTexture( texture, options );

					if ( options.needsMipmaps && texture.mipmaps.length === 0 ) backend.generateMipmaps( texture );

				}

			} else {

				// async update

				backend.createDefaultTexture( texture );

				textureData.isDefaultTexture = true;
				textureData.generation = texture.version;

			}

		}

		// dispose handler

		if ( textureData.initialized !== true ) {

			textureData.initialized = true;
			textureData.generation = texture.version;

			//

			this.info.memory.textures ++;

			// dispose

			const onDispose = () => {

				texture.removeEventListener( 'dispose', onDispose );

				this._destroyTexture( texture );

			};

			texture.addEventListener( 'dispose', onDispose );

		}

		//

		textureData.version = texture.version;

	}

	/**
	 * Computes the size of the given texture and writes the result
	 * into the target vector. This vector is also returned by the
	 * method.
	 *
	 * If no texture data are available for the compute yet, the method
	 * returns default size values.
	 *
	 * @param {Texture} texture - The texture to compute the size for.
	 * @param {Vector3} target - The target vector.
	 * @return {Vector3} The target vector.
	 */
	getSize( texture, target = _size ) {

		let image = texture.images ? texture.images[ 0 ] : texture.image;

		if ( image ) {

			if ( image.image !== undefined ) image = image.image;

			if ( image instanceof HTMLVideoElement ) {

				target.width = image.videoWidth || 1;
				target.height = image.videoHeight || 1;
				target.depth = 1;

			} else if ( image instanceof VideoFrame ) {

				target.width = image.displayWidth || 1;
				target.height = image.displayHeight || 1;
				target.depth = 1;

			} else {

				target.width = image.width || 1;
				target.height = image.height || 1;
				target.depth = texture.isCubeTexture ? 6 : ( image.depth || 1 );

			}

		} else {

			target.width = target.height = target.depth = 1;

		}

		return target;

	}

	/**
	 * Computes the number of mipmap levels for the given texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {number} width - The texture's width.
	 * @param {number} height - The texture's height.
	 * @return {number} The number of mipmap levels.
	 */
	getMipLevels( texture, width, height ) {

		let mipLevelCount;

		if ( texture.isCompressedTexture ) {

			if ( texture.mipmaps ) {

				mipLevelCount = texture.mipmaps.length;

			} else {

				mipLevelCount = 1;

			}

		} else {

			mipLevelCount = Math.floor( Math.log2( Math.max( width, height ) ) ) + 1;

		}

		return mipLevelCount;

	}

	/**
	 * Returns `true` if the given texture requires mipmaps.
	 *
	 * @param {Texture} texture - The texture.
	 * @return {boolean} Whether mipmaps are required or not.
	 */
	needsMipmaps( texture ) {

		return texture.isCompressedTexture === true || texture.generateMipmaps;

	}

	/**
	 * Frees internal resource when the given texture isn't
	 * required anymore.
	 *
	 * @param {Texture} texture - The texture to destroy.
	 */
	_destroyTexture( texture ) {

		if ( this.has( texture ) === true ) {

			this.backend.destroySampler( texture );
			this.backend.destroyTexture( texture );

			this.delete( texture );

			this.info.memory.textures --;

		}

	}

}
```
</details>

#### Methods

##### `updateRenderTarget(renderTarget: RenderTarget, activeMipmapLevel: number): void`

<details><summary>Code</summary>

```ts
updateRenderTarget( renderTarget, activeMipmapLevel = 0 ) {

		const renderTargetData = this.get( renderTarget );

		const sampleCount = renderTarget.samples === 0 ? 1 : renderTarget.samples;
		const depthTextureMips = renderTargetData.depthTextureMips || ( renderTargetData.depthTextureMips = {} );

		const textures = renderTarget.textures;

		const size = this.getSize( textures[ 0 ] );

		const mipWidth = size.width >> activeMipmapLevel;
		const mipHeight = size.height >> activeMipmapLevel;

		let depthTexture = renderTarget.depthTexture || depthTextureMips[ activeMipmapLevel ];
		const useDepthTexture = renderTarget.depthBuffer === true || renderTarget.stencilBuffer === true;

		let textureNeedsUpdate = false;

		if ( depthTexture === undefined && useDepthTexture ) {

			depthTexture = new DepthTexture();

			depthTexture.format = renderTarget.stencilBuffer ? DepthStencilFormat : DepthFormat;
			depthTexture.type = renderTarget.stencilBuffer ? UnsignedInt248Type : UnsignedIntType; // FloatType
			depthTexture.image.width = mipWidth;
			depthTexture.image.height = mipHeight;
			depthTexture.image.depth = size.depth;
			depthTexture.isArrayTexture = renderTarget.multiview === true && size.depth > 1;

			depthTextureMips[ activeMipmapLevel ] = depthTexture;

		}

		if ( renderTargetData.width !== size.width || size.height !== renderTargetData.height ) {

			textureNeedsUpdate = true;

			if ( depthTexture ) {

				depthTexture.needsUpdate = true;
				depthTexture.image.width = mipWidth;
				depthTexture.image.height = mipHeight;
				depthTexture.image.depth = depthTexture.isArrayTexture ? depthTexture.image.depth : 1;

			}

		}

		renderTargetData.width = size.width;
		renderTargetData.height = size.height;
		renderTargetData.textures = textures;
		renderTargetData.depthTexture = depthTexture || null;
		renderTargetData.depth = renderTarget.depthBuffer;
		renderTargetData.stencil = renderTarget.stencilBuffer;
		renderTargetData.renderTarget = renderTarget;

		if ( renderTargetData.sampleCount !== sampleCount ) {

			textureNeedsUpdate = true;

			if ( depthTexture ) {

				depthTexture.needsUpdate = true;

			}

			renderTargetData.sampleCount = sampleCount;

		}

		//


		const options = { sampleCount };

		// XR render targets require no texture updates

		if ( renderTarget.isXRRenderTarget !== true ) {

			for ( let i = 0; i < textures.length; i ++ ) {

				const texture = textures[ i ];

				if ( textureNeedsUpdate ) texture.needsUpdate = true;

				this.updateTexture( texture, options );

			}

			if ( depthTexture ) {

				this.updateTexture( depthTexture, options );

			}

		}

		// dispose handler

		if ( renderTargetData.initialized !== true ) {

			renderTargetData.initialized = true;

			// dispose

			const onDispose = () => {

				renderTarget.removeEventListener( 'dispose', onDispose );

				for ( let i = 0; i < textures.length; i ++ ) {

					this._destroyTexture( textures[ i ] );

				}

				if ( depthTexture ) {

					this._destroyTexture( depthTexture );

				}

				this.delete( renderTarget );

			};

			renderTarget.addEventListener( 'dispose', onDispose );

		}

	}
```
</details>

##### `updateTexture(texture: Texture, options: any): void`

<details><summary>Code</summary>

```ts
updateTexture( texture, options = {} ) {

		const textureData = this.get( texture );
		if ( textureData.initialized === true && textureData.version === texture.version ) return;

		const isRenderTarget = texture.isRenderTargetTexture || texture.isDepthTexture || texture.isFramebufferTexture;
		const backend = this.backend;

		if ( isRenderTarget && textureData.initialized === true ) {

			// it's an update

			backend.destroySampler( texture );
			backend.destroyTexture( texture );

		}

		//

		if ( texture.isFramebufferTexture ) {

			const renderTarget = this.renderer.getRenderTarget();

			if ( renderTarget ) {

				texture.type = renderTarget.texture.type;

			} else {

				texture.type = UnsignedByteType;

			}

		}

		//

		const { width, height, depth } = this.getSize( texture );

		options.width = width;
		options.height = height;
		options.depth = depth;
		options.needsMipmaps = this.needsMipmaps( texture );
		options.levels = options.needsMipmaps ? this.getMipLevels( texture, width, height ) : 1;

		//

		if ( isRenderTarget || texture.isStorageTexture === true ) {

			backend.createSampler( texture );
			backend.createTexture( texture, options );

			textureData.generation = texture.version;

		} else {

			const needsCreate = textureData.initialized !== true;

			if ( needsCreate ) backend.createSampler( texture );

			if ( texture.version > 0 ) {

				const image = texture.image;

				if ( image === undefined ) {

					console.warn( 'THREE.Renderer: Texture marked for update but image is undefined.' );

				} else if ( image.complete === false ) {

					console.warn( 'THREE.Renderer: Texture marked for update but image is incomplete.' );

				} else {

					if ( texture.images ) {

						const images = [];

						for ( const image of texture.images ) {

							images.push( image );

						}

						options.images = images;

					} else {

						options.image = image;

					}

					if ( textureData.isDefaultTexture === undefined || textureData.isDefaultTexture === true ) {

						backend.createTexture( texture, options );

						textureData.isDefaultTexture = false;
						textureData.generation = texture.version;

					}

					if ( texture.source.dataReady === true ) backend.updateTexture( texture, options );

					if ( options.needsMipmaps && texture.mipmaps.length === 0 ) backend.generateMipmaps( texture );

				}

			} else {

				// async update

				backend.createDefaultTexture( texture );

				textureData.isDefaultTexture = true;
				textureData.generation = texture.version;

			}

		}

		// dispose handler

		if ( textureData.initialized !== true ) {

			textureData.initialized = true;
			textureData.generation = texture.version;

			//

			this.info.memory.textures ++;

			// dispose

			const onDispose = () => {

				texture.removeEventListener( 'dispose', onDispose );

				this._destroyTexture( texture );

			};

			texture.addEventListener( 'dispose', onDispose );

		}

		//

		textureData.version = texture.version;

	}
```
</details>

##### `getSize(texture: Texture, target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getSize( texture, target = _size ) {

		let image = texture.images ? texture.images[ 0 ] : texture.image;

		if ( image ) {

			if ( image.image !== undefined ) image = image.image;

			if ( image instanceof HTMLVideoElement ) {

				target.width = image.videoWidth || 1;
				target.height = image.videoHeight || 1;
				target.depth = 1;

			} else if ( image instanceof VideoFrame ) {

				target.width = image.displayWidth || 1;
				target.height = image.displayHeight || 1;
				target.depth = 1;

			} else {

				target.width = image.width || 1;
				target.height = image.height || 1;
				target.depth = texture.isCubeTexture ? 6 : ( image.depth || 1 );

			}

		} else {

			target.width = target.height = target.depth = 1;

		}

		return target;

	}
```
</details>

##### `getMipLevels(texture: Texture, width: number, height: number): number`

<details><summary>Code</summary>

```ts
getMipLevels( texture, width, height ) {

		let mipLevelCount;

		if ( texture.isCompressedTexture ) {

			if ( texture.mipmaps ) {

				mipLevelCount = texture.mipmaps.length;

			} else {

				mipLevelCount = 1;

			}

		} else {

			mipLevelCount = Math.floor( Math.log2( Math.max( width, height ) ) ) + 1;

		}

		return mipLevelCount;

	}
```
</details>

##### `needsMipmaps(texture: Texture): boolean`

<details><summary>Code</summary>

```ts
needsMipmaps( texture ) {

		return texture.isCompressedTexture === true || texture.generateMipmaps;

	}
```
</details>

##### `_destroyTexture(texture: Texture): void`

<details><summary>Code</summary>

```ts
_destroyTexture( texture ) {

		if ( this.has( texture ) === true ) {

			this.backend.destroySampler( texture );
			this.backend.destroyTexture( texture );

			this.delete( texture );

			this.info.memory.textures --;

		}

	}
```
</details>


---