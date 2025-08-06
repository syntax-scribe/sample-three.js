[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Backend.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 51 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/Backend.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color4` | `./Color4.js` |
| `Vector2` | `../../math/Vector2.js` |
| `createCanvasElement` | `../../utils.js` |
| `warnOnce` | `../../utils.js` |
| `REVISION` | `../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_vector2` | `any` | let/var | `null` | ✗ |
| `_color4` | `any` | let/var | `null` | ✗ |
| `queryPool` | `any` | let/var | `this.timestampQueryPool[ type ]` | ✗ |
| `duration` | `any` | let/var | `await queryPool.resolveQueriesAsync()` | ✗ |
| `renderer` | `Renderer` | let/var | `this.renderer` | ✗ |
| `domElement` | `HTMLCanvasElement \| OffscreenCanvas` | let/var | `this.domElement` | ✗ |


---

## Functions

### `Backend.init(renderer: Renderer): Promise<any>`

**JSDoc:**
```typescript
/**
	 * Initializes the backend so it is ready for usage. Concrete backends
	 * are supposed to implement their rendering context creation and related
	 * operations in this method.
	 *
	 * @async
	 * @param {Renderer} renderer - The renderer.
	 * @return {Promise} A Promise that resolves when the backend has been initialized.
	 */
```

**Parameters:**

- **`renderer`** `Renderer`

**Returns:** `Promise<any>`

<details><summary>Code</summary>

```typescript
async init( renderer ) {

		this.renderer = renderer;

	}
```
</details>

### `Backend.beginRender(): void`

**JSDoc:**
```typescript
/**
	 * This method is executed at the beginning of a render call and
	 * can be used by the backend to prepare the state for upcoming
	 * draw calls.
	 *
	 * @abstract
	 * @param {RenderContext} renderContext - The render context.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
beginRender( /*renderContext*/ ) {}
```
</details>

### `Backend.finishRender(): void`

**JSDoc:**
```typescript
/**
	 * This method is executed at the end of a render call and
	 * can be used by the backend to finalize work after draw
	 * calls.
	 *
	 * @abstract
	 * @param {RenderContext} renderContext - The render context.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
finishRender( /*renderContext*/ ) {}
```
</details>

### `Backend.beginCompute(): void`

**JSDoc:**
```typescript
/**
	 * This method is executed at the beginning of a compute call and
	 * can be used by the backend to prepare the state for upcoming
	 * compute tasks.
	 *
	 * @abstract
	 * @param {Node|Array<Node>} computeGroup - The compute node(s).
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
beginCompute( /*computeGroup*/ ) {}
```
</details>

### `Backend.finishCompute(): void`

**JSDoc:**
```typescript
/**
	 * This method is executed at the end of a compute call and
	 * can be used by the backend to finalize work after compute
	 * tasks.
	 *
	 * @abstract
	 * @param {Node|Array<Node>} computeGroup - The compute node(s).
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
finishCompute( /*computeGroup*/ ) {}
```
</details>

### `Backend.draw(): void`

**JSDoc:**
```typescript
/**
	 * Executes a draw command for the given render object.
	 *
	 * @abstract
	 * @param {RenderObject} renderObject - The render object to draw.
	 * @param {Info} info - Holds a series of statistical information about the GPU memory and the rendering process.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
draw( /*renderObject, info*/ ) { }
```
</details>

### `Backend.compute(): void`

**JSDoc:**
```typescript
/**
	 * Executes a compute command for the given compute node.
	 *
	 * @abstract
	 * @param {Node|Array<Node>} computeGroup - The group of compute nodes of a compute call. Can be a single compute node.
	 * @param {Node} computeNode - The compute node.
	 * @param {Array<BindGroup>} bindings - The bindings.
	 * @param {ComputePipeline} computePipeline - The compute pipeline.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
compute( /*computeGroup, computeNode, computeBindings, computePipeline*/ ) { }
```
</details>

### `Backend.createProgram(): void`

**JSDoc:**
```typescript
/**
	 * Creates a shader program from the given programmable stage.
	 *
	 * @abstract
	 * @param {ProgrammableStage} program - The programmable stage.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
createProgram( /*program*/ ) { }
```
</details>

### `Backend.destroyProgram(): void`

**JSDoc:**
```typescript
/**
	 * Destroys the shader program of the given programmable stage.
	 *
	 * @abstract
	 * @param {ProgrammableStage} program - The programmable stage.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
destroyProgram( /*program*/ ) { }
```
</details>

### `Backend.createBindings(): void`

**JSDoc:**
```typescript
/**
	 * Creates bindings from the given bind group definition.
	 *
	 * @abstract
	 * @param {BindGroup} bindGroup - The bind group.
	 * @param {Array<BindGroup>} bindings - Array of bind groups.
	 * @param {number} cacheIndex - The cache index.
	 * @param {number} version - The version.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
createBindings( /*bindGroup, bindings, cacheIndex, version*/ ) { }
```
</details>

### `Backend.updateBindings(): void`

**JSDoc:**
```typescript
/**
	 * Updates the given bind group definition.
	 *
	 * @abstract
	 * @param {BindGroup} bindGroup - The bind group.
	 * @param {Array<BindGroup>} bindings - Array of bind groups.
	 * @param {number} cacheIndex - The cache index.
	 * @param {number} version - The version.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
updateBindings( /*bindGroup, bindings, cacheIndex, version*/ ) { }
```
</details>

### `Backend.updateBinding(): void`

**JSDoc:**
```typescript
/**
	 * Updates a buffer binding.
	 *
	 * @abstract
	 * @param {Buffer} binding - The buffer binding to update.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
updateBinding( /*binding*/ ) { }
```
</details>

### `Backend.createRenderPipeline(): void`

**JSDoc:**
```typescript
/**
	 * Creates a render pipeline for the given render object.
	 *
	 * @abstract
	 * @param {RenderObject} renderObject - The render object.
	 * @param {Array<Promise>} promises - An array of compilation promises which are used in `compileAsync()`.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
createRenderPipeline( /*renderObject, promises*/ ) { }
```
</details>

### `Backend.createComputePipeline(): void`

**JSDoc:**
```typescript
/**
	 * Creates a compute pipeline for the given compute node.
	 *
	 * @abstract
	 * @param {ComputePipeline} computePipeline - The compute pipeline.
	 * @param {Array<BindGroup>} bindings - The bindings.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
createComputePipeline( /*computePipeline, bindings*/ ) { }
```
</details>

### `Backend.needsRenderUpdate(): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the render pipeline requires an update.
	 *
	 * @abstract
	 * @param {RenderObject} renderObject - The render object.
	 * @return {boolean} Whether the render pipeline requires an update or not.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
needsRenderUpdate( /*renderObject*/ ) { }
```
</details>

### `Backend.getRenderCacheKey(): string`

**JSDoc:**
```typescript
/**
	 * Returns a cache key that is used to identify render pipelines.
	 *
	 * @abstract
	 * @param {RenderObject} renderObject - The render object.
	 * @return {string} The cache key.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getRenderCacheKey( /*renderObject*/ ) { }
```
</details>

### `Backend.createNodeBuilder(): NodeBuilder`

**JSDoc:**
```typescript
/**
	 * Returns a node builder for the given render object.
	 *
	 * @abstract
	 * @param {RenderObject} renderObject - The render object.
	 * @param {Renderer} renderer - The renderer.
	 * @return {NodeBuilder} The node builder.
	 */
```

**Returns:** `NodeBuilder`

<details><summary>Code</summary>

```typescript
createNodeBuilder( /*renderObject, renderer*/ ) { }
```
</details>

### `Backend.createSampler(): void`

**JSDoc:**
```typescript
/**
	 * Creates a GPU sampler for the given texture.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture to create the sampler for.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
createSampler( /*texture*/ ) { }
```
</details>

### `Backend.destroySampler(): void`

**JSDoc:**
```typescript
/**
	 * Destroys the GPU sampler for the given texture.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture to destroy the sampler for.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
destroySampler( /*texture*/ ) {}
```
</details>

### `Backend.createDefaultTexture(): void`

**JSDoc:**
```typescript
/**
	 * Creates a default texture for the given texture that can be used
	 * as a placeholder until the actual texture is ready for usage.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture to create a default texture for.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
createDefaultTexture( /*texture*/ ) { }
```
</details>

### `Backend.createTexture(): void`

**JSDoc:**
```typescript
/**
	 * Defines a texture on the GPU for the given texture object.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture.
	 * @param {Object} [options={}] - Optional configuration parameter.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
createTexture( /*texture, options={}*/ ) { }
```
</details>

### `Backend.updateTexture(): void`

**JSDoc:**
```typescript
/**
	 * Uploads the updated texture data to the GPU.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture.
	 * @param {Object} [options={}] - Optional configuration parameter.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
updateTexture( /*texture, options = {}*/ ) { }
```
</details>

### `Backend.generateMipmaps(): void`

**JSDoc:**
```typescript
/**
	 * Generates mipmaps for the given texture.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
generateMipmaps( /*texture*/ ) { }
```
</details>

### `Backend.destroyTexture(): void`

**JSDoc:**
```typescript
/**
	 * Destroys the GPU data for the given texture object.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
destroyTexture( /*texture*/ ) { }
```
</details>

### `Backend.copyTextureToBuffer(): Promise<TypedArray>`

**JSDoc:**
```typescript
/**
	 * Returns texture data as a typed array.
	 *
	 * @abstract
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

**Returns:** `Promise<TypedArray>`

<details><summary>Code</summary>

```typescript
async copyTextureToBuffer( /*texture, x, y, width, height, faceIndex*/ ) {}
```
</details>

### `Backend.copyTextureToTexture(): void`

**JSDoc:**
```typescript
/**
	 * Copies data of the given source texture to the given destination texture.
	 *
	 * @abstract
	 * @param {Texture} srcTexture - The source texture.
	 * @param {Texture} dstTexture - The destination texture.
	 * @param {?(Box3|Box2)} [srcRegion=null] - The region of the source texture to copy.
	 * @param {?(Vector2|Vector3)} [dstPosition=null] - The destination position of the copy.
	 * @param {number} [srcLevel=0] - The source mip level to copy from.
	 * @param {number} [dstLevel=0] - The destination mip level to copy to.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
copyTextureToTexture( /*srcTexture, dstTexture, srcRegion = null, dstPosition = null, srcLevel = 0, dstLevel = 0*/ ) {}
```
</details>

### `Backend.copyFramebufferToTexture(): void`

**JSDoc:**
```typescript
/**
	* Copies the current bound framebuffer to the given texture.
	*
	* @abstract
	* @param {Texture} texture - The destination texture.
	* @param {RenderContext} renderContext - The render context.
	* @param {Vector4} rectangle - A four dimensional vector defining the origin and dimension of the copy.
	*/
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
copyFramebufferToTexture( /*texture, renderContext, rectangle*/ ) {}
```
</details>

### `Backend.createAttribute(): void`

**JSDoc:**
```typescript
/**
	 * Creates the GPU buffer of a shader attribute.
	 *
	 * @abstract
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
createAttribute( /*attribute*/ ) { }
```
</details>

### `Backend.createIndexAttribute(): void`

**JSDoc:**
```typescript
/**
	 * Creates the GPU buffer of an indexed shader attribute.
	 *
	 * @abstract
	 * @param {BufferAttribute} attribute - The indexed buffer attribute.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
createIndexAttribute( /*attribute*/ ) { }
```
</details>

### `Backend.createStorageAttribute(): void`

**JSDoc:**
```typescript
/**
	 * Creates the GPU buffer of a storage attribute.
	 *
	 * @abstract
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
createStorageAttribute( /*attribute*/ ) { }
```
</details>

### `Backend.updateAttribute(): void`

**JSDoc:**
```typescript
/**
	 * Updates the GPU buffer of a shader attribute.
	 *
	 * @abstract
	 * @param {BufferAttribute} attribute - The buffer attribute to update.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
updateAttribute( /*attribute*/ ) { }
```
</details>

### `Backend.destroyAttribute(): void`

**JSDoc:**
```typescript
/**
	 * Destroys the GPU buffer of a shader attribute.
	 *
	 * @abstract
	 * @param {BufferAttribute} attribute - The buffer attribute to destroy.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
destroyAttribute( /*attribute*/ ) { }
```
</details>

### `Backend.getContext(): any`

**JSDoc:**
```typescript
/**
	 * Returns the backend's rendering context.
	 *
	 * @abstract
	 * @return {Object} The rendering context.
	 */
```

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getContext() { }
```
</details>

### `Backend.updateSize(): void`

**JSDoc:**
```typescript
/**
	 * Backends can use this method if they have to run
	 * logic when the renderer gets resized.
	 *
	 * @abstract
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
updateSize() { }
```
</details>

### `Backend.updateViewport(): void`

**JSDoc:**
```typescript
/**
	 * Updates the viewport with the values from the given render context.
	 *
	 * @abstract
	 * @param {RenderContext} renderContext - The render context.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
updateViewport( /*renderContext*/ ) {}
```
</details>

### `Backend.isOccluded(): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given 3D object is fully occluded by other
	 * 3D objects in the scene. Backends must implement this method by using
	 * a Occlusion Query API.
	 *
	 * @abstract
	 * @param {RenderContext} renderContext - The render context.
	 * @param {Object3D} object - The 3D object to test.
	 * @return {boolean} Whether the 3D object is fully occluded or not.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
isOccluded( /*renderContext, object*/ ) {}
```
</details>

### `Backend.resolveTimestampsAsync(type: string): Promise<number>`

**JSDoc:**
```typescript
/**
	 * Resolves the time stamp for the given render context and type.
	 *
	 * @async
	 * @abstract
	 * @param {string} [type='render'] - The type of the time stamp.
	 * @return {Promise<number>} A Promise that resolves with the time stamp.
	 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `Promise<number>`

**Calls:**

- `warnOnce (from ../../utils.js)`
- `queryPool.resolveQueriesAsync`

<details><summary>Code</summary>

```typescript
async resolveTimestampsAsync( type = 'render' ) {

		if ( ! this.trackTimestamp ) {

			warnOnce( 'WebGPURenderer: Timestamp tracking is disabled.' );
			return;

		}

		const queryPool = this.timestampQueryPool[ type ];
		if ( ! queryPool ) {

			warnOnce( `WebGPURenderer: No timestamp query pool for type '${type}' found.` );
			return;

		}

		const duration = await queryPool.resolveQueriesAsync();

		this.renderer.info[ type ].timestamp = duration;

		return duration;

	}
```
</details>

### `Backend.waitForGPU(): Promise<any>`

**JSDoc:**
```typescript
/**
	 * Can be used to synchronize CPU operations with GPU tasks. So when this method is called,
	 * the CPU waits for the GPU to complete its operation (e.g. a compute task).
	 *
	 * @async
	 * @abstract
	 * @return {Promise} A Promise that resolves when synchronization has been finished.
	 */
```

**Returns:** `Promise<any>`

<details><summary>Code</summary>

```typescript
async waitForGPU() {}
```
</details>

### `Backend.getArrayBufferAsync(): Promise<ArrayBuffer>`

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

**Returns:** `Promise<ArrayBuffer>`

<details><summary>Code</summary>

```typescript
async getArrayBufferAsync( /* attribute */ ) {}
```
</details>

### `Backend.hasFeatureAsync(): Promise<boolean>`

**JSDoc:**
```typescript
/**
	 * Checks if the given feature is supported by the backend.
	 *
	 * @async
	 * @abstract
	 * @param {string} name - The feature's name.
	 * @return {Promise<boolean>} A Promise that resolves with a bool that indicates whether the feature is supported or not.
	 */
```

**Returns:** `Promise<boolean>`

<details><summary>Code</summary>

```typescript
async hasFeatureAsync( /*name*/ ) { }
```
</details>

### `Backend.hasFeature(): boolean`

**JSDoc:**
```typescript
/**
	 * Checks if the given feature is supported  by the backend.
	 *
	 * @abstract
	 * @param {string} name - The feature's name.
	 * @return {boolean} Whether the feature is supported or not.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
hasFeature( /*name*/ ) {}
```
</details>

### `Backend.getMaxAnisotropy(): number`

**JSDoc:**
```typescript
/**
	 * Returns the maximum anisotropy texture filtering value.
	 *
	 * @abstract
	 * @return {number} The maximum anisotropy texture filtering value.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getMaxAnisotropy() {}
```
</details>

### `Backend.getDrawingBufferSize(): Vector2`

**JSDoc:**
```typescript
/**
	 * Returns the drawing buffer size.
	 *
	 * @return {Vector2} The drawing buffer size.
	 */
```

**Returns:** `Vector2`

**Calls:**

- `this.renderer.getDrawingBufferSize`

<details><summary>Code</summary>

```typescript
getDrawingBufferSize() {

		_vector2 = _vector2 || new Vector2();

		return this.renderer.getDrawingBufferSize( _vector2 );

	}
```
</details>

### `Backend.setScissorTest(): void`

**JSDoc:**
```typescript
/**
	 * Defines the scissor test.
	 *
	 * @abstract
	 * @param {boolean} boolean - Whether the scissor test should be enabled or not.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setScissorTest( /*boolean*/ ) { }
```
</details>

### `Backend.getClearColor(): Color4`

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

- `renderer.getClearColor`
- `_color4.getRGB`

<details><summary>Code</summary>

```typescript
getClearColor() {

		const renderer = this.renderer;

		_color4 = _color4 || new Color4();

		renderer.getClearColor( _color4 );

		_color4.getRGB( _color4 );

		return _color4;

	}
```
</details>

### `Backend.getDomElement(): HTMLCanvasElement`

**JSDoc:**
```typescript
/**
	 * Returns the DOM element. If no DOM element exists, the backend
	 * creates a new one.
	 *
	 * @return {HTMLCanvasElement} The DOM element.
	 */
```

**Returns:** `HTMLCanvasElement`

**Calls:**

- `createCanvasElement (from ../../utils.js)`
- `domElement.setAttribute`

**Internal Comments:**
```
// OffscreenCanvas does not have setAttribute, see #22811
```

<details><summary>Code</summary>

```typescript
getDomElement() {

		let domElement = this.domElement;

		if ( domElement === null ) {

			domElement = ( this.parameters.canvas !== undefined ) ? this.parameters.canvas : createCanvasElement();

			// OffscreenCanvas does not have setAttribute, see #22811
			if ( 'setAttribute' in domElement ) domElement.setAttribute( 'data-engine', `three.js r${REVISION} webgpu` );

			this.domElement = domElement;

		}

		return domElement;

	}
```
</details>

### `Backend.set(object: any, value: any): void`

**JSDoc:**
```typescript
/**
	 * Sets a dictionary for the given object into the
	 * internal data structure.
	 *
	 * @param {Object} object - The object.
	 * @param {Object} value - The dictionary to set.
	 */
```

**Parameters:**

- **`object`** `any`
- **`value`** `any`

**Returns:** `void`

**Calls:**

- `this.data.set`

<details><summary>Code</summary>

```typescript
set( object, value ) {

		this.data.set( object, value );

	}
```
</details>

### `Backend.get(object: any): any`

**JSDoc:**
```typescript
/**
	 * Returns the dictionary for the given object.
	 *
	 * @param {Object} object - The object.
	 * @return {Object} The object's dictionary.
	 */
```

**Parameters:**

- **`object`** `any`

**Returns:** `any`

**Calls:**

- `this.data.get`
- `this.data.set`

<details><summary>Code</summary>

```typescript
get( object ) {

		let map = this.data.get( object );

		if ( map === undefined ) {

			map = {};
			this.data.set( object, map );

		}

		return map;

	}
```
</details>

### `Backend.has(object: any): boolean`

**JSDoc:**
```typescript
/**
	 * Checks if the given object has a dictionary
	 * with data defined.
	 *
	 * @param {Object} object - The object.
	 * @return {boolean} Whether a dictionary for the given object as been defined or not.
	 */
```

**Parameters:**

- **`object`** `any`

**Returns:** `boolean`

**Calls:**

- `this.data.has`

<details><summary>Code</summary>

```typescript
has( object ) {

		return this.data.has( object );

	}
```
</details>

### `Backend.delete(object: any): void`

**JSDoc:**
```typescript
/**
	 * Deletes an object from the internal data structure.
	 *
	 * @param {Object} object - The object to delete.
	 */
```

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `this.data.delete`

<details><summary>Code</summary>

```typescript
delete( object ) {

		this.data.delete( object );

	}
```
</details>

### `Backend.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources.
	 *
	 * @abstract
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
dispose() { }
```
</details>


---

## Classes

### `Backend`

<details><summary>Class Code</summary>

```ts
class Backend {

	/**
	 * Constructs a new backend.
	 *
	 * @param {Object} parameters - An object holding parameters for the backend.
	 */
	constructor( parameters = {} ) {

		/**
		 * The parameters of the backend.
		 *
		 * @type {Object}
		 */
		this.parameters = Object.assign( {}, parameters );

		/**
		 * This weak map holds backend-specific data of objects
		 * like textures, attributes or render targets.
		 *
		 * @type {WeakMap}
		 */
		this.data = new WeakMap();

		/**
		 * A reference to the renderer.
		 *
		 * @type {?Renderer}
		 * @default null
		 */
		this.renderer = null;

		/**
		 * A reference to the canvas element the renderer is drawing to.
		 *
		 * @type {?(HTMLCanvasElement|OffscreenCanvas)}
		 * @default null
		 */
		this.domElement = null;

		/**
		 * A reference to the timestamp query pool.
   		 *
   		 * @type {{render: ?TimestampQueryPool, compute: ?TimestampQueryPool}}
		 */
		this.timestampQueryPool = {
			'render': null,
			'compute': null
		};

		/**
		 * Whether to track timestamps with a Timestamp Query API or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.trackTimestamp = ( parameters.trackTimestamp === true );

	}

	/**
	 * Initializes the backend so it is ready for usage. Concrete backends
	 * are supposed to implement their rendering context creation and related
	 * operations in this method.
	 *
	 * @async
	 * @param {Renderer} renderer - The renderer.
	 * @return {Promise} A Promise that resolves when the backend has been initialized.
	 */
	async init( renderer ) {

		this.renderer = renderer;

	}

	/**
	 * The coordinate system of the backend.
	 *
	 * @abstract
	 * @type {number}
	 * @readonly
	 */
	get coordinateSystem() {}

	// render context

	/**
	 * This method is executed at the beginning of a render call and
	 * can be used by the backend to prepare the state for upcoming
	 * draw calls.
	 *
	 * @abstract
	 * @param {RenderContext} renderContext - The render context.
	 */
	beginRender( /*renderContext*/ ) {}

	/**
	 * This method is executed at the end of a render call and
	 * can be used by the backend to finalize work after draw
	 * calls.
	 *
	 * @abstract
	 * @param {RenderContext} renderContext - The render context.
	 */
	finishRender( /*renderContext*/ ) {}

	/**
	 * This method is executed at the beginning of a compute call and
	 * can be used by the backend to prepare the state for upcoming
	 * compute tasks.
	 *
	 * @abstract
	 * @param {Node|Array<Node>} computeGroup - The compute node(s).
	 */
	beginCompute( /*computeGroup*/ ) {}

	/**
	 * This method is executed at the end of a compute call and
	 * can be used by the backend to finalize work after compute
	 * tasks.
	 *
	 * @abstract
	 * @param {Node|Array<Node>} computeGroup - The compute node(s).
	 */
	finishCompute( /*computeGroup*/ ) {}

	// render object

	/**
	 * Executes a draw command for the given render object.
	 *
	 * @abstract
	 * @param {RenderObject} renderObject - The render object to draw.
	 * @param {Info} info - Holds a series of statistical information about the GPU memory and the rendering process.
	 */
	draw( /*renderObject, info*/ ) { }

	// compute node

	/**
	 * Executes a compute command for the given compute node.
	 *
	 * @abstract
	 * @param {Node|Array<Node>} computeGroup - The group of compute nodes of a compute call. Can be a single compute node.
	 * @param {Node} computeNode - The compute node.
	 * @param {Array<BindGroup>} bindings - The bindings.
	 * @param {ComputePipeline} computePipeline - The compute pipeline.
	 */
	compute( /*computeGroup, computeNode, computeBindings, computePipeline*/ ) { }

	// program

	/**
	 * Creates a shader program from the given programmable stage.
	 *
	 * @abstract
	 * @param {ProgrammableStage} program - The programmable stage.
	 */
	createProgram( /*program*/ ) { }

	/**
	 * Destroys the shader program of the given programmable stage.
	 *
	 * @abstract
	 * @param {ProgrammableStage} program - The programmable stage.
	 */
	destroyProgram( /*program*/ ) { }

	// bindings

	/**
	 * Creates bindings from the given bind group definition.
	 *
	 * @abstract
	 * @param {BindGroup} bindGroup - The bind group.
	 * @param {Array<BindGroup>} bindings - Array of bind groups.
	 * @param {number} cacheIndex - The cache index.
	 * @param {number} version - The version.
	 */
	createBindings( /*bindGroup, bindings, cacheIndex, version*/ ) { }

	/**
	 * Updates the given bind group definition.
	 *
	 * @abstract
	 * @param {BindGroup} bindGroup - The bind group.
	 * @param {Array<BindGroup>} bindings - Array of bind groups.
	 * @param {number} cacheIndex - The cache index.
	 * @param {number} version - The version.
	 */
	updateBindings( /*bindGroup, bindings, cacheIndex, version*/ ) { }

	/**
	 * Updates a buffer binding.
	 *
	 * @abstract
	 * @param {Buffer} binding - The buffer binding to update.
	 */
	updateBinding( /*binding*/ ) { }

	// pipeline

	/**
	 * Creates a render pipeline for the given render object.
	 *
	 * @abstract
	 * @param {RenderObject} renderObject - The render object.
	 * @param {Array<Promise>} promises - An array of compilation promises which are used in `compileAsync()`.
	 */
	createRenderPipeline( /*renderObject, promises*/ ) { }

	/**
	 * Creates a compute pipeline for the given compute node.
	 *
	 * @abstract
	 * @param {ComputePipeline} computePipeline - The compute pipeline.
	 * @param {Array<BindGroup>} bindings - The bindings.
	 */
	createComputePipeline( /*computePipeline, bindings*/ ) { }

	// cache key

	/**
	 * Returns `true` if the render pipeline requires an update.
	 *
	 * @abstract
	 * @param {RenderObject} renderObject - The render object.
	 * @return {boolean} Whether the render pipeline requires an update or not.
	 */
	needsRenderUpdate( /*renderObject*/ ) { }

	/**
	 * Returns a cache key that is used to identify render pipelines.
	 *
	 * @abstract
	 * @param {RenderObject} renderObject - The render object.
	 * @return {string} The cache key.
	 */
	getRenderCacheKey( /*renderObject*/ ) { }

	// node builder

	/**
	 * Returns a node builder for the given render object.
	 *
	 * @abstract
	 * @param {RenderObject} renderObject - The render object.
	 * @param {Renderer} renderer - The renderer.
	 * @return {NodeBuilder} The node builder.
	 */
	createNodeBuilder( /*renderObject, renderer*/ ) { }

	// textures

	/**
	 * Creates a GPU sampler for the given texture.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture to create the sampler for.
	 */
	createSampler( /*texture*/ ) { }

	/**
	 * Destroys the GPU sampler for the given texture.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture to destroy the sampler for.
	 */
	destroySampler( /*texture*/ ) {}

	/**
	 * Creates a default texture for the given texture that can be used
	 * as a placeholder until the actual texture is ready for usage.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture to create a default texture for.
	 */
	createDefaultTexture( /*texture*/ ) { }

	/**
	 * Defines a texture on the GPU for the given texture object.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture.
	 * @param {Object} [options={}] - Optional configuration parameter.
	 */
	createTexture( /*texture, options={}*/ ) { }

	/**
	 * Uploads the updated texture data to the GPU.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture.
	 * @param {Object} [options={}] - Optional configuration parameter.
	 */
	updateTexture( /*texture, options = {}*/ ) { }

	/**
	 * Generates mipmaps for the given texture.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture.
	 */
	generateMipmaps( /*texture*/ ) { }

	/**
	 * Destroys the GPU data for the given texture object.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture.
	 */
	destroyTexture( /*texture*/ ) { }

	/**
	 * Returns texture data as a typed array.
	 *
	 * @abstract
	 * @async
	 * @param {Texture} texture - The texture to copy.
	 * @param {number} x - The x coordinate of the copy origin.
	 * @param {number} y - The y coordinate of the copy origin.
	 * @param {number} width - The width of the copy.
	 * @param {number} height - The height of the copy.
	 * @param {number} faceIndex - The face index.
	 * @return {Promise<TypedArray>} A Promise that resolves with a typed array when the copy operation has finished.
	 */
	async copyTextureToBuffer( /*texture, x, y, width, height, faceIndex*/ ) {}

	/**
	 * Copies data of the given source texture to the given destination texture.
	 *
	 * @abstract
	 * @param {Texture} srcTexture - The source texture.
	 * @param {Texture} dstTexture - The destination texture.
	 * @param {?(Box3|Box2)} [srcRegion=null] - The region of the source texture to copy.
	 * @param {?(Vector2|Vector3)} [dstPosition=null] - The destination position of the copy.
	 * @param {number} [srcLevel=0] - The source mip level to copy from.
	 * @param {number} [dstLevel=0] - The destination mip level to copy to.
	 */
	copyTextureToTexture( /*srcTexture, dstTexture, srcRegion = null, dstPosition = null, srcLevel = 0, dstLevel = 0*/ ) {}

	/**
	* Copies the current bound framebuffer to the given texture.
	*
	* @abstract
	* @param {Texture} texture - The destination texture.
	* @param {RenderContext} renderContext - The render context.
	* @param {Vector4} rectangle - A four dimensional vector defining the origin and dimension of the copy.
	*/
	copyFramebufferToTexture( /*texture, renderContext, rectangle*/ ) {}

	// attributes

	/**
	 * Creates the GPU buffer of a shader attribute.
	 *
	 * @abstract
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
	createAttribute( /*attribute*/ ) { }

	/**
	 * Creates the GPU buffer of an indexed shader attribute.
	 *
	 * @abstract
	 * @param {BufferAttribute} attribute - The indexed buffer attribute.
	 */
	createIndexAttribute( /*attribute*/ ) { }

	/**
	 * Creates the GPU buffer of a storage attribute.
	 *
	 * @abstract
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
	createStorageAttribute( /*attribute*/ ) { }

	/**
	 * Updates the GPU buffer of a shader attribute.
	 *
	 * @abstract
	 * @param {BufferAttribute} attribute - The buffer attribute to update.
	 */
	updateAttribute( /*attribute*/ ) { }

	/**
	 * Destroys the GPU buffer of a shader attribute.
	 *
	 * @abstract
	 * @param {BufferAttribute} attribute - The buffer attribute to destroy.
	 */
	destroyAttribute( /*attribute*/ ) { }

	// canvas

	/**
	 * Returns the backend's rendering context.
	 *
	 * @abstract
	 * @return {Object} The rendering context.
	 */
	getContext() { }

	/**
	 * Backends can use this method if they have to run
	 * logic when the renderer gets resized.
	 *
	 * @abstract
	 */
	updateSize() { }

	/**
	 * Updates the viewport with the values from the given render context.
	 *
	 * @abstract
	 * @param {RenderContext} renderContext - The render context.
	 */
	updateViewport( /*renderContext*/ ) {}

	// utils

	/**
	 * Returns `true` if the given 3D object is fully occluded by other
	 * 3D objects in the scene. Backends must implement this method by using
	 * a Occlusion Query API.
	 *
	 * @abstract
	 * @param {RenderContext} renderContext - The render context.
	 * @param {Object3D} object - The 3D object to test.
	 * @return {boolean} Whether the 3D object is fully occluded or not.
	 */
	isOccluded( /*renderContext, object*/ ) {}

	/**
	 * Resolves the time stamp for the given render context and type.
	 *
	 * @async
	 * @abstract
	 * @param {string} [type='render'] - The type of the time stamp.
	 * @return {Promise<number>} A Promise that resolves with the time stamp.
	 */
	async resolveTimestampsAsync( type = 'render' ) {

		if ( ! this.trackTimestamp ) {

			warnOnce( 'WebGPURenderer: Timestamp tracking is disabled.' );
			return;

		}

		const queryPool = this.timestampQueryPool[ type ];
		if ( ! queryPool ) {

			warnOnce( `WebGPURenderer: No timestamp query pool for type '${type}' found.` );
			return;

		}

		const duration = await queryPool.resolveQueriesAsync();

		this.renderer.info[ type ].timestamp = duration;

		return duration;

	}

	/**
	 * Can be used to synchronize CPU operations with GPU tasks. So when this method is called,
	 * the CPU waits for the GPU to complete its operation (e.g. a compute task).
	 *
	 * @async
	 * @abstract
	 * @return {Promise} A Promise that resolves when synchronization has been finished.
	 */
	async waitForGPU() {}

	/**
	 * This method performs a readback operation by moving buffer data from
	 * a storage buffer attribute from the GPU to the CPU.
	 *
	 * @async
	 * @param {StorageBufferAttribute} attribute - The storage buffer attribute.
	 * @return {Promise<ArrayBuffer>} A promise that resolves with the buffer data when the data are ready.
	 */
	async getArrayBufferAsync( /* attribute */ ) {}

	/**
	 * Checks if the given feature is supported by the backend.
	 *
	 * @async
	 * @abstract
	 * @param {string} name - The feature's name.
	 * @return {Promise<boolean>} A Promise that resolves with a bool that indicates whether the feature is supported or not.
	 */
	async hasFeatureAsync( /*name*/ ) { }

	/**
	 * Checks if the given feature is supported  by the backend.
	 *
	 * @abstract
	 * @param {string} name - The feature's name.
	 * @return {boolean} Whether the feature is supported or not.
	 */
	hasFeature( /*name*/ ) {}

	/**
	 * Returns the maximum anisotropy texture filtering value.
	 *
	 * @abstract
	 * @return {number} The maximum anisotropy texture filtering value.
	 */
	getMaxAnisotropy() {}

	/**
	 * Returns the drawing buffer size.
	 *
	 * @return {Vector2} The drawing buffer size.
	 */
	getDrawingBufferSize() {

		_vector2 = _vector2 || new Vector2();

		return this.renderer.getDrawingBufferSize( _vector2 );

	}

	/**
	 * Defines the scissor test.
	 *
	 * @abstract
	 * @param {boolean} boolean - Whether the scissor test should be enabled or not.
	 */
	setScissorTest( /*boolean*/ ) { }

	/**
	 * Returns the clear color and alpha into a single
	 * color object.
	 *
	 * @return {Color4} The clear color.
	 */
	getClearColor() {

		const renderer = this.renderer;

		_color4 = _color4 || new Color4();

		renderer.getClearColor( _color4 );

		_color4.getRGB( _color4 );

		return _color4;

	}

	/**
	 * Returns the DOM element. If no DOM element exists, the backend
	 * creates a new one.
	 *
	 * @return {HTMLCanvasElement} The DOM element.
	 */
	getDomElement() {

		let domElement = this.domElement;

		if ( domElement === null ) {

			domElement = ( this.parameters.canvas !== undefined ) ? this.parameters.canvas : createCanvasElement();

			// OffscreenCanvas does not have setAttribute, see #22811
			if ( 'setAttribute' in domElement ) domElement.setAttribute( 'data-engine', `three.js r${REVISION} webgpu` );

			this.domElement = domElement;

		}

		return domElement;

	}

	/**
	 * Sets a dictionary for the given object into the
	 * internal data structure.
	 *
	 * @param {Object} object - The object.
	 * @param {Object} value - The dictionary to set.
	 */
	set( object, value ) {

		this.data.set( object, value );

	}

	/**
	 * Returns the dictionary for the given object.
	 *
	 * @param {Object} object - The object.
	 * @return {Object} The object's dictionary.
	 */
	get( object ) {

		let map = this.data.get( object );

		if ( map === undefined ) {

			map = {};
			this.data.set( object, map );

		}

		return map;

	}

	/**
	 * Checks if the given object has a dictionary
	 * with data defined.
	 *
	 * @param {Object} object - The object.
	 * @return {boolean} Whether a dictionary for the given object as been defined or not.
	 */
	has( object ) {

		return this.data.has( object );

	}

	/**
	 * Deletes an object from the internal data structure.
	 *
	 * @param {Object} object - The object to delete.
	 */
	delete( object ) {

		this.data.delete( object );

	}

	/**
	 * Frees internal resources.
	 *
	 * @abstract
	 */
	dispose() { }

}
```
</details>

#### Methods

##### `init(renderer: Renderer): Promise<any>`

<details><summary>Code</summary>

```ts
async init( renderer ) {

		this.renderer = renderer;

	}
```
</details>

##### `beginRender(): void`

<details><summary>Code</summary>

```ts
beginRender( /*renderContext*/ ) {}
```
</details>

##### `finishRender(): void`

<details><summary>Code</summary>

```ts
finishRender( /*renderContext*/ ) {}
```
</details>

##### `beginCompute(): void`

<details><summary>Code</summary>

```ts
beginCompute( /*computeGroup*/ ) {}
```
</details>

##### `finishCompute(): void`

<details><summary>Code</summary>

```ts
finishCompute( /*computeGroup*/ ) {}
```
</details>

##### `draw(): void`

<details><summary>Code</summary>

```ts
draw( /*renderObject, info*/ ) { }
```
</details>

##### `compute(): void`

<details><summary>Code</summary>

```ts
compute( /*computeGroup, computeNode, computeBindings, computePipeline*/ ) { }
```
</details>

##### `createProgram(): void`

<details><summary>Code</summary>

```ts
createProgram( /*program*/ ) { }
```
</details>

##### `destroyProgram(): void`

<details><summary>Code</summary>

```ts
destroyProgram( /*program*/ ) { }
```
</details>

##### `createBindings(): void`

<details><summary>Code</summary>

```ts
createBindings( /*bindGroup, bindings, cacheIndex, version*/ ) { }
```
</details>

##### `updateBindings(): void`

<details><summary>Code</summary>

```ts
updateBindings( /*bindGroup, bindings, cacheIndex, version*/ ) { }
```
</details>

##### `updateBinding(): void`

<details><summary>Code</summary>

```ts
updateBinding( /*binding*/ ) { }
```
</details>

##### `createRenderPipeline(): void`

<details><summary>Code</summary>

```ts
createRenderPipeline( /*renderObject, promises*/ ) { }
```
</details>

##### `createComputePipeline(): void`

<details><summary>Code</summary>

```ts
createComputePipeline( /*computePipeline, bindings*/ ) { }
```
</details>

##### `needsRenderUpdate(): boolean`

<details><summary>Code</summary>

```ts
needsRenderUpdate( /*renderObject*/ ) { }
```
</details>

##### `getRenderCacheKey(): string`

<details><summary>Code</summary>

```ts
getRenderCacheKey( /*renderObject*/ ) { }
```
</details>

##### `createNodeBuilder(): NodeBuilder`

<details><summary>Code</summary>

```ts
createNodeBuilder( /*renderObject, renderer*/ ) { }
```
</details>

##### `createSampler(): void`

<details><summary>Code</summary>

```ts
createSampler( /*texture*/ ) { }
```
</details>

##### `destroySampler(): void`

<details><summary>Code</summary>

```ts
destroySampler( /*texture*/ ) {}
```
</details>

##### `createDefaultTexture(): void`

<details><summary>Code</summary>

```ts
createDefaultTexture( /*texture*/ ) { }
```
</details>

##### `createTexture(): void`

<details><summary>Code</summary>

```ts
createTexture( /*texture, options={}*/ ) { }
```
</details>

##### `updateTexture(): void`

<details><summary>Code</summary>

```ts
updateTexture( /*texture, options = {}*/ ) { }
```
</details>

##### `generateMipmaps(): void`

<details><summary>Code</summary>

```ts
generateMipmaps( /*texture*/ ) { }
```
</details>

##### `destroyTexture(): void`

<details><summary>Code</summary>

```ts
destroyTexture( /*texture*/ ) { }
```
</details>

##### `copyTextureToBuffer(): Promise<TypedArray>`

<details><summary>Code</summary>

```ts
async copyTextureToBuffer( /*texture, x, y, width, height, faceIndex*/ ) {}
```
</details>

##### `copyTextureToTexture(): void`

<details><summary>Code</summary>

```ts
copyTextureToTexture( /*srcTexture, dstTexture, srcRegion = null, dstPosition = null, srcLevel = 0, dstLevel = 0*/ ) {}
```
</details>

##### `copyFramebufferToTexture(): void`

<details><summary>Code</summary>

```ts
copyFramebufferToTexture( /*texture, renderContext, rectangle*/ ) {}
```
</details>

##### `createAttribute(): void`

<details><summary>Code</summary>

```ts
createAttribute( /*attribute*/ ) { }
```
</details>

##### `createIndexAttribute(): void`

<details><summary>Code</summary>

```ts
createIndexAttribute( /*attribute*/ ) { }
```
</details>

##### `createStorageAttribute(): void`

<details><summary>Code</summary>

```ts
createStorageAttribute( /*attribute*/ ) { }
```
</details>

##### `updateAttribute(): void`

<details><summary>Code</summary>

```ts
updateAttribute( /*attribute*/ ) { }
```
</details>

##### `destroyAttribute(): void`

<details><summary>Code</summary>

```ts
destroyAttribute( /*attribute*/ ) { }
```
</details>

##### `getContext(): any`

<details><summary>Code</summary>

```ts
getContext() { }
```
</details>

##### `updateSize(): void`

<details><summary>Code</summary>

```ts
updateSize() { }
```
</details>

##### `updateViewport(): void`

<details><summary>Code</summary>

```ts
updateViewport( /*renderContext*/ ) {}
```
</details>

##### `isOccluded(): boolean`

<details><summary>Code</summary>

```ts
isOccluded( /*renderContext, object*/ ) {}
```
</details>

##### `resolveTimestampsAsync(type: string): Promise<number>`

<details><summary>Code</summary>

```ts
async resolveTimestampsAsync( type = 'render' ) {

		if ( ! this.trackTimestamp ) {

			warnOnce( 'WebGPURenderer: Timestamp tracking is disabled.' );
			return;

		}

		const queryPool = this.timestampQueryPool[ type ];
		if ( ! queryPool ) {

			warnOnce( `WebGPURenderer: No timestamp query pool for type '${type}' found.` );
			return;

		}

		const duration = await queryPool.resolveQueriesAsync();

		this.renderer.info[ type ].timestamp = duration;

		return duration;

	}
```
</details>

##### `waitForGPU(): Promise<any>`

<details><summary>Code</summary>

```ts
async waitForGPU() {}
```
</details>

##### `getArrayBufferAsync(): Promise<ArrayBuffer>`

<details><summary>Code</summary>

```ts
async getArrayBufferAsync( /* attribute */ ) {}
```
</details>

##### `hasFeatureAsync(): Promise<boolean>`

<details><summary>Code</summary>

```ts
async hasFeatureAsync( /*name*/ ) { }
```
</details>

##### `hasFeature(): boolean`

<details><summary>Code</summary>

```ts
hasFeature( /*name*/ ) {}
```
</details>

##### `getMaxAnisotropy(): number`

<details><summary>Code</summary>

```ts
getMaxAnisotropy() {}
```
</details>

##### `getDrawingBufferSize(): Vector2`

<details><summary>Code</summary>

```ts
getDrawingBufferSize() {

		_vector2 = _vector2 || new Vector2();

		return this.renderer.getDrawingBufferSize( _vector2 );

	}
```
</details>

##### `setScissorTest(): void`

<details><summary>Code</summary>

```ts
setScissorTest( /*boolean*/ ) { }
```
</details>

##### `getClearColor(): Color4`

<details><summary>Code</summary>

```ts
getClearColor() {

		const renderer = this.renderer;

		_color4 = _color4 || new Color4();

		renderer.getClearColor( _color4 );

		_color4.getRGB( _color4 );

		return _color4;

	}
```
</details>

##### `getDomElement(): HTMLCanvasElement`

<details><summary>Code</summary>

```ts
getDomElement() {

		let domElement = this.domElement;

		if ( domElement === null ) {

			domElement = ( this.parameters.canvas !== undefined ) ? this.parameters.canvas : createCanvasElement();

			// OffscreenCanvas does not have setAttribute, see #22811
			if ( 'setAttribute' in domElement ) domElement.setAttribute( 'data-engine', `three.js r${REVISION} webgpu` );

			this.domElement = domElement;

		}

		return domElement;

	}
```
</details>

##### `set(object: any, value: any): void`

<details><summary>Code</summary>

```ts
set( object, value ) {

		this.data.set( object, value );

	}
```
</details>

##### `get(object: any): any`

<details><summary>Code</summary>

```ts
get( object ) {

		let map = this.data.get( object );

		if ( map === undefined ) {

			map = {};
			this.data.set( object, map );

		}

		return map;

	}
```
</details>

##### `has(object: any): boolean`

<details><summary>Code</summary>

```ts
has( object ) {

		return this.data.has( object );

	}
```
</details>

##### `delete(object: any): void`

<details><summary>Code</summary>

```ts
delete( object ) {

		this.data.delete( object );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() { }
```
</details>


---