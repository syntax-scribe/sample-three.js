[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `WebGPUBindingUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 33 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgpu/utils/WebGPUBindingUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `GPUTextureAspect` | `./WebGPUConstants.js` |
| `GPUTextureViewDimension` | `./WebGPUConstants.js` |
| `GPUTextureSampleType` | `./WebGPUConstants.js` |
| `GPUBufferBindingType` | `./WebGPUConstants.js` |
| `GPUStorageTextureAccess` | `./WebGPUConstants.js` |
| `GPUSamplerBindingType` | `./WebGPUConstants.js` |
| `FloatType` | `../../../constants.js` |
| `IntType` | `../../../constants.js` |
| `UnsignedIntType` | `../../../constants.js` |
| `NodeAccess` | `../../../nodes/core/constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `backend` | `WebGPUBackend` | let/var | `this.backend` | ✗ |
| `device` | `any` | let/var | `backend.device` | ✗ |
| `entries` | `any[]` | let/var | `[]` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `bindingGPU` | `{ binding: number; visibility: any; }` | let/var | `{ binding: index ++, visibility: binding.visibility }` | ✗ |
| `buffer` | `{}` | let/var | `{}` | ✗ |
| `storageTexture` | `{ format: any; }` | let/var | `{}` | ✗ |
| `access` | `any` | let/var | `binding.access` | ✗ |
| `texture` | `{}` | let/var | `{}` | ✗ |
| `type` | `any` | let/var | `binding.texture.type` | ✗ |
| `sampler` | `{}` | let/var | `{}` | ✗ |
| `bindGroupGPU` | `any` | let/var | `*not shown*` | ✗ |
| `backend` | `WebGPUBackend` | let/var | `this.backend` | ✗ |
| `device` | `any` | let/var | `backend.device` | ✗ |
| `buffer` | `ArrayBufferLike` | let/var | `binding.buffer` | ✗ |
| `bufferGPU` | `any` | let/var | `backend.get( binding ).buffer` | ✗ |
| `backend` | `WebGPUBackend` | let/var | `this.backend` | ✗ |
| `device` | `any` | let/var | `backend.device` | ✗ |
| `usage` | `number` | let/var | `GPUBufferUsage.UNIFORM \| GPUBufferUsage.COPY_DST` | ✗ |
| `index` | `number` | let/var | `data[ 0 ]` | ✗ |
| `entries` | `{ binding: number; resource: { buffer...` | let/var | `[ { binding: 0, resource: { buffer } } ]` | ✗ |
| `backend` | `WebGPUBackend` | let/var | `this.backend` | ✗ |
| `device` | `any` | let/var | `backend.device` | ✗ |
| `bindingPoint` | `number` | let/var | `0` | ✗ |
| `entriesGPU` | `any[]` | let/var | `[]` | ✗ |
| `byteLength` | `any` | let/var | `binding.byteLength` | ✗ |
| `usage` | `number` | let/var | `GPUBufferUsage.UNIFORM \| GPUBufferUsage.COPY_DST` | ✗ |
| `attribute` | `any` | let/var | `binding.attribute` | ✗ |
| `resourceGPU` | `any` | let/var | `*not shown*` | ✗ |
| `mipLevelCount` | `any` | let/var | `binding.store ? 1 : textureData.texture.mipLevelCount` | ✗ |
| `propertyName` | `string` | let/var | ``view-${ textureData.texture.width }-${ textureData.texture.height }`` | ✗ |
| `aspectGPU` | `string` | let/var | `GPUTextureAspect.All` | ✗ |
| `dimensionViewGPU` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `WebGPUBindingUtils.createBindingsLayout(bindGroup: BindGroup): GPUBindGroupLayout`

**JSDoc:**
```typescript
/**
	 * Creates a GPU bind group layout for the given bind group.
	 *
	 * @param {BindGroup} bindGroup - The bind group.
	 * @return {GPUBindGroupLayout} The GPU bind group layout.
	 */
```

**Parameters:**

- **`bindGroup`** `BindGroup`

**Returns:** `GPUBindGroupLayout`

**Calls:**

- `this.backend.get`
- `backend.utils.getTextureSampleData`
- `this.backend.hasFeature`
- `console.error`
- `entries.push`
- `device.createBindGroupLayout`

**Internal Comments:**
```
// compute
```

<details><summary>Code</summary>

```typescript
createBindingsLayout( bindGroup ) {

		const backend = this.backend;
		const device = backend.device;

		const entries = [];

		let index = 0;

		for ( const binding of bindGroup.bindings ) {

			const bindingGPU = {
				binding: index ++,
				visibility: binding.visibility
			};

			if ( binding.isUniformBuffer || binding.isStorageBuffer ) {

				const buffer = {}; // GPUBufferBindingLayout

				if ( binding.isStorageBuffer ) {

					if ( binding.visibility & 4 ) {

						// compute

						if ( binding.access === NodeAccess.READ_WRITE || binding.access === NodeAccess.WRITE_ONLY ) {

							buffer.type = GPUBufferBindingType.Storage;

						} else {

							buffer.type = GPUBufferBindingType.ReadOnlyStorage;

						}

					} else {

						buffer.type = GPUBufferBindingType.ReadOnlyStorage;

					}

				}

				bindingGPU.buffer = buffer;

			} else if ( binding.isSampledTexture && binding.store ) {

				const storageTexture = {}; // GPUStorageTextureBindingLayout
				storageTexture.format = this.backend.get( binding.texture ).texture.format;

				const access = binding.access;

				if ( access === NodeAccess.READ_WRITE ) {

					storageTexture.access = GPUStorageTextureAccess.ReadWrite;

				} else if ( access === NodeAccess.WRITE_ONLY ) {

					storageTexture.access = GPUStorageTextureAccess.WriteOnly;

				} else {

					storageTexture.access = GPUStorageTextureAccess.ReadOnly;

				}

				if ( binding.texture.isArrayTexture ) {

					storageTexture.viewDimension = GPUTextureViewDimension.TwoDArray;

				} else if ( binding.texture.is3DTexture ) {

					storageTexture.viewDimension = GPUTextureViewDimension.ThreeD;

				}

				bindingGPU.storageTexture = storageTexture;

			} else if ( binding.isSampledTexture ) {

				const texture = {}; // GPUTextureBindingLayout

				const { primarySamples } = backend.utils.getTextureSampleData( binding.texture );

				if ( primarySamples > 1 ) {

					texture.multisampled = true;

					if ( ! binding.texture.isDepthTexture ) {

						texture.sampleType = GPUTextureSampleType.UnfilterableFloat;

					}

				}

				if ( binding.texture.isDepthTexture ) {

					if ( backend.compatibilityMode && binding.texture.compareFunction === null ) {

						texture.sampleType = GPUTextureSampleType.UnfilterableFloat;

					} else {

						texture.sampleType = GPUTextureSampleType.Depth;

					}

				} else if ( binding.texture.isDataTexture || binding.texture.isDataArrayTexture || binding.texture.isData3DTexture ) {

					const type = binding.texture.type;

					if ( type === IntType ) {

						texture.sampleType = GPUTextureSampleType.SInt;

					} else if ( type === UnsignedIntType ) {

						texture.sampleType = GPUTextureSampleType.UInt;

					} else if ( type === FloatType ) {

						if ( this.backend.hasFeature( 'float32-filterable' ) ) {

							texture.sampleType = GPUTextureSampleType.Float;

						} else {

							texture.sampleType = GPUTextureSampleType.UnfilterableFloat;

						}

					}

				}

				if ( binding.isSampledCubeTexture ) {

					texture.viewDimension = GPUTextureViewDimension.Cube;

				} else if ( binding.texture.isArrayTexture || binding.texture.isDataArrayTexture || binding.texture.isCompressedArrayTexture ) {

					texture.viewDimension = GPUTextureViewDimension.TwoDArray;

				} else if ( binding.isSampledTexture3D ) {

					texture.viewDimension = GPUTextureViewDimension.ThreeD;

				}

				bindingGPU.texture = texture;

			} else if ( binding.isSampler ) {

				const sampler = {}; // GPUSamplerBindingLayout

				if ( binding.texture.isDepthTexture ) {

					if ( binding.texture.compareFunction !== null ) {

						sampler.type = GPUSamplerBindingType.Comparison;

					} else if ( backend.compatibilityMode ) {

						sampler.type = GPUSamplerBindingType.NonFiltering;

					}

				}

				bindingGPU.sampler = sampler;

			} else {

				console.error( `WebGPUBindingUtils: Unsupported binding "${ binding }".` );

			}

			entries.push( bindingGPU );

		}

		return device.createBindGroupLayout( { entries } );

	}
```
</details>

### `WebGPUBindingUtils.createBindings(bindGroup: BindGroup, bindings: BindGroup[], cacheIndex: number, version: number): void`

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

- `backend.get`
- `bindGroupLayoutCache.get`
- `this.createBindingsLayout`
- `bindGroupLayoutCache.set`
- `this.createBindGroup`

**Internal Comments:**
```
// setup (static) binding layout and (dynamic) binding group (x2)
```

<details><summary>Code</summary>

```typescript
createBindings( bindGroup, bindings, cacheIndex, version = 0 ) {

		const { backend, bindGroupLayoutCache } = this;
		const bindingsData = backend.get( bindGroup );

		// setup (static) binding layout and (dynamic) binding group

		let bindLayoutGPU = bindGroupLayoutCache.get( bindGroup.bindingsReference );

		if ( bindLayoutGPU === undefined ) {

			bindLayoutGPU = this.createBindingsLayout( bindGroup );
			bindGroupLayoutCache.set( bindGroup.bindingsReference, bindLayoutGPU );

		}

		let bindGroupGPU;

		if ( cacheIndex > 0 ) {

			if ( bindingsData.groups === undefined ) {

				bindingsData.groups = [];
				bindingsData.versions = [];

			}

			if ( bindingsData.versions[ cacheIndex ] === version ) {

				bindGroupGPU = bindingsData.groups[ cacheIndex ];

			}

		}

		if ( bindGroupGPU === undefined ) {

			bindGroupGPU = this.createBindGroup( bindGroup, bindLayoutGPU );

			if ( cacheIndex > 0 ) {

				bindingsData.groups[ cacheIndex ] = bindGroupGPU;
				bindingsData.versions[ cacheIndex ] = version;

			}

		}

		bindingsData.group = bindGroupGPU;
		bindingsData.layout = bindLayoutGPU;

	}
```
</details>

### `WebGPUBindingUtils.updateBinding(binding: Buffer<ArrayBufferLike>): void`

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

- `backend.get`
- `device.queue.writeBuffer`

<details><summary>Code</summary>

```typescript
updateBinding( binding ) {

		const backend = this.backend;
		const device = backend.device;

		const buffer = binding.buffer;
		const bufferGPU = backend.get( binding ).buffer;

		device.queue.writeBuffer( bufferGPU, 0, buffer, 0 );

	}
```
</details>

### `WebGPUBindingUtils.createBindGroupIndex(data: Uint32Array<ArrayBufferLike>, layout: GPUBindGroupLayout): GPUBindGroup`

**JSDoc:**
```typescript
/**
	 * Creates a GPU bind group for the camera index.
	 *
	 * @param {Uint32Array} data - The index data.
	 * @param {GPUBindGroupLayout} layout - The GPU bind group layout.
	 * @return {GPUBindGroup} The GPU bind group.
	 */
```

**Parameters:**

- **`data`** `Uint32Array<ArrayBufferLike>`
- **`layout`** `GPUBindGroupLayout`

**Returns:** `GPUBindGroup`

**Calls:**

- `device.createBuffer`
- `device.queue.writeBuffer`
- `device.createBindGroup`

<details><summary>Code</summary>

```typescript
createBindGroupIndex( data, layout ) {

		const backend = this.backend;
		const device = backend.device;

		const usage = GPUBufferUsage.UNIFORM | GPUBufferUsage.COPY_DST;
		const index = data[ 0 ];

		const buffer = device.createBuffer( {
			label: 'bindingCameraIndex_' + index,
			size: 16, // uint(4) * 4
			usage: usage
		} );

		device.queue.writeBuffer( buffer, 0, data, 0 );

		const entries = [ { binding: 0, resource: { buffer } } ];

		return device.createBindGroup( {
			label: 'bindGroupCameraIndex_' + index,
			layout,
			entries
		} );

	}
```
</details>

### `WebGPUBindingUtils.createBindGroup(bindGroup: BindGroup, layoutGPU: GPUBindGroupLayout): GPUBindGroup`

**JSDoc:**
```typescript
/**
	 * Creates a GPU bind group for the given bind group and GPU layout.
	 *
	 * @param {BindGroup} bindGroup - The bind group.
	 * @param {GPUBindGroupLayout} layoutGPU - The GPU bind group layout.
	 * @return {GPUBindGroup} The GPU bind group.
	 */
```

**Parameters:**

- **`bindGroup`** `BindGroup`
- **`layoutGPU`** `GPUBindGroupLayout`

**Returns:** `GPUBindGroup`

**Calls:**

- `backend.get`
- `device.createBuffer`
- `entriesGPU.push`
- `device.importExternalTexture`
- `textureData.texture.createView`
- `device.createBindGroup`

**Internal Comments:**
```
//const usage = GPUBufferUsage.STORAGE | GPUBufferUsage.VERTEX | /*GPUBufferUsage.COPY_SRC |*/ GPUBufferUsage.COPY_DST; (x4)
//backend.attributeUtils.createAttribute( attribute, usage ); // @TODO: Move it to universal renderer (x4)
```

<details><summary>Code</summary>

```typescript
createBindGroup( bindGroup, layoutGPU ) {

		const backend = this.backend;
		const device = backend.device;

		let bindingPoint = 0;
		const entriesGPU = [];

		for ( const binding of bindGroup.bindings ) {

			if ( binding.isUniformBuffer ) {

				const bindingData = backend.get( binding );

				if ( bindingData.buffer === undefined ) {

					const byteLength = binding.byteLength;

					const usage = GPUBufferUsage.UNIFORM | GPUBufferUsage.COPY_DST;

					const bufferGPU = device.createBuffer( {
						label: 'bindingBuffer_' + binding.name,
						size: byteLength,
						usage: usage
					} );

					bindingData.buffer = bufferGPU;

				}

				entriesGPU.push( { binding: bindingPoint, resource: { buffer: bindingData.buffer } } );

			} else if ( binding.isStorageBuffer ) {

				const bindingData = backend.get( binding );

				if ( bindingData.buffer === undefined ) {

					const attribute = binding.attribute;
					//const usage = GPUBufferUsage.STORAGE | GPUBufferUsage.VERTEX | /*GPUBufferUsage.COPY_SRC |*/ GPUBufferUsage.COPY_DST;

					//backend.attributeUtils.createAttribute( attribute, usage ); // @TODO: Move it to universal renderer

					bindingData.buffer = backend.get( attribute ).buffer;

				}

				entriesGPU.push( { binding: bindingPoint, resource: { buffer: bindingData.buffer } } );

			} else if ( binding.isSampledTexture ) {

				const textureData = backend.get( binding.texture );

				let resourceGPU;

				if ( textureData.externalTexture !== undefined ) {

					resourceGPU = device.importExternalTexture( { source: textureData.externalTexture } );

				} else {

					const mipLevelCount = binding.store ? 1 : textureData.texture.mipLevelCount;
					let propertyName = `view-${ textureData.texture.width }-${ textureData.texture.height }`;

					if ( textureData.texture.depthOrArrayLayers > 1 ) {

						propertyName += `-${ textureData.texture.depthOrArrayLayers }`;

					}

					propertyName += `-${ mipLevelCount }`;

					resourceGPU = textureData[ propertyName ];

					if ( resourceGPU === undefined ) {

						const aspectGPU = GPUTextureAspect.All;

						let dimensionViewGPU;

						if ( binding.isSampledCubeTexture ) {

							dimensionViewGPU = GPUTextureViewDimension.Cube;

						} else if ( binding.isSampledTexture3D ) {

							dimensionViewGPU = GPUTextureViewDimension.ThreeD;

						} else if ( binding.texture.isArrayTexture || binding.texture.isDataArrayTexture || binding.texture.isCompressedArrayTexture ) {

							dimensionViewGPU = GPUTextureViewDimension.TwoDArray;

						} else {

							dimensionViewGPU = GPUTextureViewDimension.TwoD;

						}

						resourceGPU = textureData[ propertyName ] = textureData.texture.createView( { aspect: aspectGPU, dimension: dimensionViewGPU, mipLevelCount } );

					}

				}

				entriesGPU.push( { binding: bindingPoint, resource: resourceGPU } );

			} else if ( binding.isSampler ) {

				const textureGPU = backend.get( binding.texture );

				entriesGPU.push( { binding: bindingPoint, resource: textureGPU.sampler } );

			}

			bindingPoint ++;

		}

		return device.createBindGroup( {
			label: 'bindGroup_' + bindGroup.name,
			layout: layoutGPU,
			entries: entriesGPU
		} );

	}
```
</details>


---

## Classes

### `WebGPUBindingUtils`

<details><summary>Class Code</summary>

```ts
class WebGPUBindingUtils {

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
		 * A cache for managing bind group layouts.
		 *
		 * @type {WeakMap<Array<Binding>,GPUBindGroupLayout>}
		 */
		this.bindGroupLayoutCache = new WeakMap();

	}

	/**
	 * Creates a GPU bind group layout for the given bind group.
	 *
	 * @param {BindGroup} bindGroup - The bind group.
	 * @return {GPUBindGroupLayout} The GPU bind group layout.
	 */
	createBindingsLayout( bindGroup ) {

		const backend = this.backend;
		const device = backend.device;

		const entries = [];

		let index = 0;

		for ( const binding of bindGroup.bindings ) {

			const bindingGPU = {
				binding: index ++,
				visibility: binding.visibility
			};

			if ( binding.isUniformBuffer || binding.isStorageBuffer ) {

				const buffer = {}; // GPUBufferBindingLayout

				if ( binding.isStorageBuffer ) {

					if ( binding.visibility & 4 ) {

						// compute

						if ( binding.access === NodeAccess.READ_WRITE || binding.access === NodeAccess.WRITE_ONLY ) {

							buffer.type = GPUBufferBindingType.Storage;

						} else {

							buffer.type = GPUBufferBindingType.ReadOnlyStorage;

						}

					} else {

						buffer.type = GPUBufferBindingType.ReadOnlyStorage;

					}

				}

				bindingGPU.buffer = buffer;

			} else if ( binding.isSampledTexture && binding.store ) {

				const storageTexture = {}; // GPUStorageTextureBindingLayout
				storageTexture.format = this.backend.get( binding.texture ).texture.format;

				const access = binding.access;

				if ( access === NodeAccess.READ_WRITE ) {

					storageTexture.access = GPUStorageTextureAccess.ReadWrite;

				} else if ( access === NodeAccess.WRITE_ONLY ) {

					storageTexture.access = GPUStorageTextureAccess.WriteOnly;

				} else {

					storageTexture.access = GPUStorageTextureAccess.ReadOnly;

				}

				if ( binding.texture.isArrayTexture ) {

					storageTexture.viewDimension = GPUTextureViewDimension.TwoDArray;

				} else if ( binding.texture.is3DTexture ) {

					storageTexture.viewDimension = GPUTextureViewDimension.ThreeD;

				}

				bindingGPU.storageTexture = storageTexture;

			} else if ( binding.isSampledTexture ) {

				const texture = {}; // GPUTextureBindingLayout

				const { primarySamples } = backend.utils.getTextureSampleData( binding.texture );

				if ( primarySamples > 1 ) {

					texture.multisampled = true;

					if ( ! binding.texture.isDepthTexture ) {

						texture.sampleType = GPUTextureSampleType.UnfilterableFloat;

					}

				}

				if ( binding.texture.isDepthTexture ) {

					if ( backend.compatibilityMode && binding.texture.compareFunction === null ) {

						texture.sampleType = GPUTextureSampleType.UnfilterableFloat;

					} else {

						texture.sampleType = GPUTextureSampleType.Depth;

					}

				} else if ( binding.texture.isDataTexture || binding.texture.isDataArrayTexture || binding.texture.isData3DTexture ) {

					const type = binding.texture.type;

					if ( type === IntType ) {

						texture.sampleType = GPUTextureSampleType.SInt;

					} else if ( type === UnsignedIntType ) {

						texture.sampleType = GPUTextureSampleType.UInt;

					} else if ( type === FloatType ) {

						if ( this.backend.hasFeature( 'float32-filterable' ) ) {

							texture.sampleType = GPUTextureSampleType.Float;

						} else {

							texture.sampleType = GPUTextureSampleType.UnfilterableFloat;

						}

					}

				}

				if ( binding.isSampledCubeTexture ) {

					texture.viewDimension = GPUTextureViewDimension.Cube;

				} else if ( binding.texture.isArrayTexture || binding.texture.isDataArrayTexture || binding.texture.isCompressedArrayTexture ) {

					texture.viewDimension = GPUTextureViewDimension.TwoDArray;

				} else if ( binding.isSampledTexture3D ) {

					texture.viewDimension = GPUTextureViewDimension.ThreeD;

				}

				bindingGPU.texture = texture;

			} else if ( binding.isSampler ) {

				const sampler = {}; // GPUSamplerBindingLayout

				if ( binding.texture.isDepthTexture ) {

					if ( binding.texture.compareFunction !== null ) {

						sampler.type = GPUSamplerBindingType.Comparison;

					} else if ( backend.compatibilityMode ) {

						sampler.type = GPUSamplerBindingType.NonFiltering;

					}

				}

				bindingGPU.sampler = sampler;

			} else {

				console.error( `WebGPUBindingUtils: Unsupported binding "${ binding }".` );

			}

			entries.push( bindingGPU );

		}

		return device.createBindGroupLayout( { entries } );

	}

	/**
	 * Creates bindings from the given bind group definition.
	 *
	 * @param {BindGroup} bindGroup - The bind group.
	 * @param {Array<BindGroup>} bindings - Array of bind groups.
	 * @param {number} cacheIndex - The cache index.
	 * @param {number} version - The version.
	 */
	createBindings( bindGroup, bindings, cacheIndex, version = 0 ) {

		const { backend, bindGroupLayoutCache } = this;
		const bindingsData = backend.get( bindGroup );

		// setup (static) binding layout and (dynamic) binding group

		let bindLayoutGPU = bindGroupLayoutCache.get( bindGroup.bindingsReference );

		if ( bindLayoutGPU === undefined ) {

			bindLayoutGPU = this.createBindingsLayout( bindGroup );
			bindGroupLayoutCache.set( bindGroup.bindingsReference, bindLayoutGPU );

		}

		let bindGroupGPU;

		if ( cacheIndex > 0 ) {

			if ( bindingsData.groups === undefined ) {

				bindingsData.groups = [];
				bindingsData.versions = [];

			}

			if ( bindingsData.versions[ cacheIndex ] === version ) {

				bindGroupGPU = bindingsData.groups[ cacheIndex ];

			}

		}

		if ( bindGroupGPU === undefined ) {

			bindGroupGPU = this.createBindGroup( bindGroup, bindLayoutGPU );

			if ( cacheIndex > 0 ) {

				bindingsData.groups[ cacheIndex ] = bindGroupGPU;
				bindingsData.versions[ cacheIndex ] = version;

			}

		}

		bindingsData.group = bindGroupGPU;
		bindingsData.layout = bindLayoutGPU;

	}

	/**
	 * Updates a buffer binding.
	 *
	 *  @param {Buffer} binding - The buffer binding to update.
	 */
	updateBinding( binding ) {

		const backend = this.backend;
		const device = backend.device;

		const buffer = binding.buffer;
		const bufferGPU = backend.get( binding ).buffer;

		device.queue.writeBuffer( bufferGPU, 0, buffer, 0 );

	}

	/**
	 * Creates a GPU bind group for the camera index.
	 *
	 * @param {Uint32Array} data - The index data.
	 * @param {GPUBindGroupLayout} layout - The GPU bind group layout.
	 * @return {GPUBindGroup} The GPU bind group.
	 */
	createBindGroupIndex( data, layout ) {

		const backend = this.backend;
		const device = backend.device;

		const usage = GPUBufferUsage.UNIFORM | GPUBufferUsage.COPY_DST;
		const index = data[ 0 ];

		const buffer = device.createBuffer( {
			label: 'bindingCameraIndex_' + index,
			size: 16, // uint(4) * 4
			usage: usage
		} );

		device.queue.writeBuffer( buffer, 0, data, 0 );

		const entries = [ { binding: 0, resource: { buffer } } ];

		return device.createBindGroup( {
			label: 'bindGroupCameraIndex_' + index,
			layout,
			entries
		} );

	}

	/**
	 * Creates a GPU bind group for the given bind group and GPU layout.
	 *
	 * @param {BindGroup} bindGroup - The bind group.
	 * @param {GPUBindGroupLayout} layoutGPU - The GPU bind group layout.
	 * @return {GPUBindGroup} The GPU bind group.
	 */
	createBindGroup( bindGroup, layoutGPU ) {

		const backend = this.backend;
		const device = backend.device;

		let bindingPoint = 0;
		const entriesGPU = [];

		for ( const binding of bindGroup.bindings ) {

			if ( binding.isUniformBuffer ) {

				const bindingData = backend.get( binding );

				if ( bindingData.buffer === undefined ) {

					const byteLength = binding.byteLength;

					const usage = GPUBufferUsage.UNIFORM | GPUBufferUsage.COPY_DST;

					const bufferGPU = device.createBuffer( {
						label: 'bindingBuffer_' + binding.name,
						size: byteLength,
						usage: usage
					} );

					bindingData.buffer = bufferGPU;

				}

				entriesGPU.push( { binding: bindingPoint, resource: { buffer: bindingData.buffer } } );

			} else if ( binding.isStorageBuffer ) {

				const bindingData = backend.get( binding );

				if ( bindingData.buffer === undefined ) {

					const attribute = binding.attribute;
					//const usage = GPUBufferUsage.STORAGE | GPUBufferUsage.VERTEX | /*GPUBufferUsage.COPY_SRC |*/ GPUBufferUsage.COPY_DST;

					//backend.attributeUtils.createAttribute( attribute, usage ); // @TODO: Move it to universal renderer

					bindingData.buffer = backend.get( attribute ).buffer;

				}

				entriesGPU.push( { binding: bindingPoint, resource: { buffer: bindingData.buffer } } );

			} else if ( binding.isSampledTexture ) {

				const textureData = backend.get( binding.texture );

				let resourceGPU;

				if ( textureData.externalTexture !== undefined ) {

					resourceGPU = device.importExternalTexture( { source: textureData.externalTexture } );

				} else {

					const mipLevelCount = binding.store ? 1 : textureData.texture.mipLevelCount;
					let propertyName = `view-${ textureData.texture.width }-${ textureData.texture.height }`;

					if ( textureData.texture.depthOrArrayLayers > 1 ) {

						propertyName += `-${ textureData.texture.depthOrArrayLayers }`;

					}

					propertyName += `-${ mipLevelCount }`;

					resourceGPU = textureData[ propertyName ];

					if ( resourceGPU === undefined ) {

						const aspectGPU = GPUTextureAspect.All;

						let dimensionViewGPU;

						if ( binding.isSampledCubeTexture ) {

							dimensionViewGPU = GPUTextureViewDimension.Cube;

						} else if ( binding.isSampledTexture3D ) {

							dimensionViewGPU = GPUTextureViewDimension.ThreeD;

						} else if ( binding.texture.isArrayTexture || binding.texture.isDataArrayTexture || binding.texture.isCompressedArrayTexture ) {

							dimensionViewGPU = GPUTextureViewDimension.TwoDArray;

						} else {

							dimensionViewGPU = GPUTextureViewDimension.TwoD;

						}

						resourceGPU = textureData[ propertyName ] = textureData.texture.createView( { aspect: aspectGPU, dimension: dimensionViewGPU, mipLevelCount } );

					}

				}

				entriesGPU.push( { binding: bindingPoint, resource: resourceGPU } );

			} else if ( binding.isSampler ) {

				const textureGPU = backend.get( binding.texture );

				entriesGPU.push( { binding: bindingPoint, resource: textureGPU.sampler } );

			}

			bindingPoint ++;

		}

		return device.createBindGroup( {
			label: 'bindGroup_' + bindGroup.name,
			layout: layoutGPU,
			entries: entriesGPU
		} );

	}

}
```
</details>

#### Methods

##### `createBindingsLayout(bindGroup: BindGroup): GPUBindGroupLayout`

<details><summary>Code</summary>

```ts
createBindingsLayout( bindGroup ) {

		const backend = this.backend;
		const device = backend.device;

		const entries = [];

		let index = 0;

		for ( const binding of bindGroup.bindings ) {

			const bindingGPU = {
				binding: index ++,
				visibility: binding.visibility
			};

			if ( binding.isUniformBuffer || binding.isStorageBuffer ) {

				const buffer = {}; // GPUBufferBindingLayout

				if ( binding.isStorageBuffer ) {

					if ( binding.visibility & 4 ) {

						// compute

						if ( binding.access === NodeAccess.READ_WRITE || binding.access === NodeAccess.WRITE_ONLY ) {

							buffer.type = GPUBufferBindingType.Storage;

						} else {

							buffer.type = GPUBufferBindingType.ReadOnlyStorage;

						}

					} else {

						buffer.type = GPUBufferBindingType.ReadOnlyStorage;

					}

				}

				bindingGPU.buffer = buffer;

			} else if ( binding.isSampledTexture && binding.store ) {

				const storageTexture = {}; // GPUStorageTextureBindingLayout
				storageTexture.format = this.backend.get( binding.texture ).texture.format;

				const access = binding.access;

				if ( access === NodeAccess.READ_WRITE ) {

					storageTexture.access = GPUStorageTextureAccess.ReadWrite;

				} else if ( access === NodeAccess.WRITE_ONLY ) {

					storageTexture.access = GPUStorageTextureAccess.WriteOnly;

				} else {

					storageTexture.access = GPUStorageTextureAccess.ReadOnly;

				}

				if ( binding.texture.isArrayTexture ) {

					storageTexture.viewDimension = GPUTextureViewDimension.TwoDArray;

				} else if ( binding.texture.is3DTexture ) {

					storageTexture.viewDimension = GPUTextureViewDimension.ThreeD;

				}

				bindingGPU.storageTexture = storageTexture;

			} else if ( binding.isSampledTexture ) {

				const texture = {}; // GPUTextureBindingLayout

				const { primarySamples } = backend.utils.getTextureSampleData( binding.texture );

				if ( primarySamples > 1 ) {

					texture.multisampled = true;

					if ( ! binding.texture.isDepthTexture ) {

						texture.sampleType = GPUTextureSampleType.UnfilterableFloat;

					}

				}

				if ( binding.texture.isDepthTexture ) {

					if ( backend.compatibilityMode && binding.texture.compareFunction === null ) {

						texture.sampleType = GPUTextureSampleType.UnfilterableFloat;

					} else {

						texture.sampleType = GPUTextureSampleType.Depth;

					}

				} else if ( binding.texture.isDataTexture || binding.texture.isDataArrayTexture || binding.texture.isData3DTexture ) {

					const type = binding.texture.type;

					if ( type === IntType ) {

						texture.sampleType = GPUTextureSampleType.SInt;

					} else if ( type === UnsignedIntType ) {

						texture.sampleType = GPUTextureSampleType.UInt;

					} else if ( type === FloatType ) {

						if ( this.backend.hasFeature( 'float32-filterable' ) ) {

							texture.sampleType = GPUTextureSampleType.Float;

						} else {

							texture.sampleType = GPUTextureSampleType.UnfilterableFloat;

						}

					}

				}

				if ( binding.isSampledCubeTexture ) {

					texture.viewDimension = GPUTextureViewDimension.Cube;

				} else if ( binding.texture.isArrayTexture || binding.texture.isDataArrayTexture || binding.texture.isCompressedArrayTexture ) {

					texture.viewDimension = GPUTextureViewDimension.TwoDArray;

				} else if ( binding.isSampledTexture3D ) {

					texture.viewDimension = GPUTextureViewDimension.ThreeD;

				}

				bindingGPU.texture = texture;

			} else if ( binding.isSampler ) {

				const sampler = {}; // GPUSamplerBindingLayout

				if ( binding.texture.isDepthTexture ) {

					if ( binding.texture.compareFunction !== null ) {

						sampler.type = GPUSamplerBindingType.Comparison;

					} else if ( backend.compatibilityMode ) {

						sampler.type = GPUSamplerBindingType.NonFiltering;

					}

				}

				bindingGPU.sampler = sampler;

			} else {

				console.error( `WebGPUBindingUtils: Unsupported binding "${ binding }".` );

			}

			entries.push( bindingGPU );

		}

		return device.createBindGroupLayout( { entries } );

	}
```
</details>

##### `createBindings(bindGroup: BindGroup, bindings: BindGroup[], cacheIndex: number, version: number): void`

<details><summary>Code</summary>

```ts
createBindings( bindGroup, bindings, cacheIndex, version = 0 ) {

		const { backend, bindGroupLayoutCache } = this;
		const bindingsData = backend.get( bindGroup );

		// setup (static) binding layout and (dynamic) binding group

		let bindLayoutGPU = bindGroupLayoutCache.get( bindGroup.bindingsReference );

		if ( bindLayoutGPU === undefined ) {

			bindLayoutGPU = this.createBindingsLayout( bindGroup );
			bindGroupLayoutCache.set( bindGroup.bindingsReference, bindLayoutGPU );

		}

		let bindGroupGPU;

		if ( cacheIndex > 0 ) {

			if ( bindingsData.groups === undefined ) {

				bindingsData.groups = [];
				bindingsData.versions = [];

			}

			if ( bindingsData.versions[ cacheIndex ] === version ) {

				bindGroupGPU = bindingsData.groups[ cacheIndex ];

			}

		}

		if ( bindGroupGPU === undefined ) {

			bindGroupGPU = this.createBindGroup( bindGroup, bindLayoutGPU );

			if ( cacheIndex > 0 ) {

				bindingsData.groups[ cacheIndex ] = bindGroupGPU;
				bindingsData.versions[ cacheIndex ] = version;

			}

		}

		bindingsData.group = bindGroupGPU;
		bindingsData.layout = bindLayoutGPU;

	}
```
</details>

##### `updateBinding(binding: Buffer<ArrayBufferLike>): void`

<details><summary>Code</summary>

```ts
updateBinding( binding ) {

		const backend = this.backend;
		const device = backend.device;

		const buffer = binding.buffer;
		const bufferGPU = backend.get( binding ).buffer;

		device.queue.writeBuffer( bufferGPU, 0, buffer, 0 );

	}
```
</details>

##### `createBindGroupIndex(data: Uint32Array<ArrayBufferLike>, layout: GPUBindGroupLayout): GPUBindGroup`

<details><summary>Code</summary>

```ts
createBindGroupIndex( data, layout ) {

		const backend = this.backend;
		const device = backend.device;

		const usage = GPUBufferUsage.UNIFORM | GPUBufferUsage.COPY_DST;
		const index = data[ 0 ];

		const buffer = device.createBuffer( {
			label: 'bindingCameraIndex_' + index,
			size: 16, // uint(4) * 4
			usage: usage
		} );

		device.queue.writeBuffer( buffer, 0, data, 0 );

		const entries = [ { binding: 0, resource: { buffer } } ];

		return device.createBindGroup( {
			label: 'bindGroupCameraIndex_' + index,
			layout,
			entries
		} );

	}
```
</details>

##### `createBindGroup(bindGroup: BindGroup, layoutGPU: GPUBindGroupLayout): GPUBindGroup`

<details><summary>Code</summary>

```ts
createBindGroup( bindGroup, layoutGPU ) {

		const backend = this.backend;
		const device = backend.device;

		let bindingPoint = 0;
		const entriesGPU = [];

		for ( const binding of bindGroup.bindings ) {

			if ( binding.isUniformBuffer ) {

				const bindingData = backend.get( binding );

				if ( bindingData.buffer === undefined ) {

					const byteLength = binding.byteLength;

					const usage = GPUBufferUsage.UNIFORM | GPUBufferUsage.COPY_DST;

					const bufferGPU = device.createBuffer( {
						label: 'bindingBuffer_' + binding.name,
						size: byteLength,
						usage: usage
					} );

					bindingData.buffer = bufferGPU;

				}

				entriesGPU.push( { binding: bindingPoint, resource: { buffer: bindingData.buffer } } );

			} else if ( binding.isStorageBuffer ) {

				const bindingData = backend.get( binding );

				if ( bindingData.buffer === undefined ) {

					const attribute = binding.attribute;
					//const usage = GPUBufferUsage.STORAGE | GPUBufferUsage.VERTEX | /*GPUBufferUsage.COPY_SRC |*/ GPUBufferUsage.COPY_DST;

					//backend.attributeUtils.createAttribute( attribute, usage ); // @TODO: Move it to universal renderer

					bindingData.buffer = backend.get( attribute ).buffer;

				}

				entriesGPU.push( { binding: bindingPoint, resource: { buffer: bindingData.buffer } } );

			} else if ( binding.isSampledTexture ) {

				const textureData = backend.get( binding.texture );

				let resourceGPU;

				if ( textureData.externalTexture !== undefined ) {

					resourceGPU = device.importExternalTexture( { source: textureData.externalTexture } );

				} else {

					const mipLevelCount = binding.store ? 1 : textureData.texture.mipLevelCount;
					let propertyName = `view-${ textureData.texture.width }-${ textureData.texture.height }`;

					if ( textureData.texture.depthOrArrayLayers > 1 ) {

						propertyName += `-${ textureData.texture.depthOrArrayLayers }`;

					}

					propertyName += `-${ mipLevelCount }`;

					resourceGPU = textureData[ propertyName ];

					if ( resourceGPU === undefined ) {

						const aspectGPU = GPUTextureAspect.All;

						let dimensionViewGPU;

						if ( binding.isSampledCubeTexture ) {

							dimensionViewGPU = GPUTextureViewDimension.Cube;

						} else if ( binding.isSampledTexture3D ) {

							dimensionViewGPU = GPUTextureViewDimension.ThreeD;

						} else if ( binding.texture.isArrayTexture || binding.texture.isDataArrayTexture || binding.texture.isCompressedArrayTexture ) {

							dimensionViewGPU = GPUTextureViewDimension.TwoDArray;

						} else {

							dimensionViewGPU = GPUTextureViewDimension.TwoD;

						}

						resourceGPU = textureData[ propertyName ] = textureData.texture.createView( { aspect: aspectGPU, dimension: dimensionViewGPU, mipLevelCount } );

					}

				}

				entriesGPU.push( { binding: bindingPoint, resource: resourceGPU } );

			} else if ( binding.isSampler ) {

				const textureGPU = backend.get( binding.texture );

				entriesGPU.push( { binding: bindingPoint, resource: textureGPU.sampler } );

			}

			bindingPoint ++;

		}

		return device.createBindGroup( {
			label: 'bindGroup_' + bindGroup.name,
			layout: layoutGPU,
			entries: entriesGPU
		} );

	}
```
</details>


---