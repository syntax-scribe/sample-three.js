[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `WebGPUAttributeUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 39 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgpu/utils/WebGPUAttributeUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `GPUInputStepMode` | `./WebGPUConstants.js` |
| `Float16BufferAttribute` | `../../../core/BufferAttribute.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `typedArraysToVertexFormatPr...` | `Map<Int8ArrayConstructor, string[]>` | let/var | `new Map( [ [ Int8Array, [ 'sint8', 'snorm8' ]], [ Uint8Array, [ 'uint8', 'uno...` | ✗ |
| `typedAttributeToVertexForma...` | `Map<typeof Float16BufferAttribute, st...` | let/var | `new Map( [ [ Float16BufferAttribute, [ 'float16', ]], ] )` | ✗ |
| `typeArraysToVertexFormatPre...` | `Map<Int16ArrayConstructor, string>` | let/var | `new Map( [ [ Int32Array, 'sint32' ], [ Int16Array, 'sint32' ], // patch for I...` | ✗ |
| `backend` | `WebGPUBackend` | let/var | `this.backend` | ✗ |
| `buffer` | `any` | let/var | `bufferData.buffer` | ✗ |
| `device` | `any` | let/var | `backend.device` | ✗ |
| `array` | `any` | let/var | `bufferAttribute.array` | ✗ |
| `byteLength` | `any` | let/var | `array.byteLength` | ✗ |
| `size` | `any` | let/var | `byteLength + ( ( 4 - ( byteLength % 4 ) ) % 4 )` | ✗ |
| `backend` | `WebGPUBackend` | let/var | `this.backend` | ✗ |
| `device` | `any` | let/var | `backend.device` | ✗ |
| `buffer` | `any` | let/var | `backend.get( bufferAttribute ).buffer` | ✗ |
| `array` | `any` | let/var | `bufferAttribute.array` | ✗ |
| `updateRanges` | `any` | let/var | `bufferAttribute.updateRanges` | ✗ |
| `byteOffsetFactor` | `any` | let/var | `isTypedArray ? 1 : array.BYTES_PER_ELEMENT` | ✗ |
| `range` | `any` | let/var | `updateRanges[ i ]` | ✗ |
| `dataOffset` | `any` | let/var | `*not shown*` | ✗ |
| `size` | `any` | let/var | `*not shown*` | ✗ |
| `bufferOffset` | `number` | let/var | `dataOffset * ( isTypedArray ? array.BYTES_PER_ELEMENT : 1 )` | ✗ |
| `vertexBuffers` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `geometryAttribute` | `any` | let/var | `attributes[ slot ]` | ✗ |
| `bytesPerElement` | `any` | let/var | `geometryAttribute.array.BYTES_PER_ELEMENT` | ✗ |
| `arrayStride` | `any` | let/var | `*not shown*` | ✗ |
| `stepMode` | `any` | let/var | `*not shown*` | ✗ |
| `offset` | `number` | let/var | `( geometryAttribute.isInterleavedBufferAttribute === true ) ? geometryAttribu...` | ✗ |
| `backend` | `WebGPUBackend` | let/var | `this.backend` | ✗ |
| `backend` | `WebGPUBackend` | let/var | `this.backend` | ✗ |
| `device` | `any` | let/var | `backend.device` | ✗ |
| `bufferGPU` | `any` | let/var | `data.buffer` | ✗ |
| `size` | `any` | let/var | `bufferGPU.size` | ✗ |
| `dstBuffer` | `any` | let/var | `new attribute.array.constructor( arrayBuffer.slice( 0 ) )` | ✗ |
| `ArrayType` | `any` | let/var | `geometryAttribute.array.constructor` | ✗ |
| `AttributeType` | `any` | let/var | `geometryAttribute.constructor` | ✗ |
| `format` | `any` | let/var | `*not shown*` | ✗ |
| `prefixOptions` | `string[]` | let/var | `typedAttributeToVertexFormatPrefix.get( AttributeType ) \|\| typedArraysToVer...` | ✗ |
| `prefix` | `string` | let/var | `prefixOptions[ normalized ? 1 : 0 ]` | ✗ |
| `bytesPerUnit` | `number` | let/var | `ArrayType.BYTES_PER_ELEMENT * itemSize` | ✗ |
| `paddedBytesPerUnit` | `number` | let/var | `Math.floor( ( bytesPerUnit + 3 ) / 4 ) * 4` | ✗ |
| `paddedItemSize` | `number` | let/var | `paddedBytesPerUnit / ArrayType.BYTES_PER_ELEMENT` | ✗ |


---

## Functions

### `WebGPUAttributeUtils.createAttribute(attribute: BufferAttribute, usage: GPUBufferUsage): void`

**JSDoc:**
```typescript
/**
	 * Creates the GPU buffer for the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 * @param {GPUBufferUsage} usage - A flag that indicates how the buffer may be used after its creation.
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`
- **`usage`** `GPUBufferUsage`

**Returns:** `void`

**Calls:**

- `this._getBufferAttribute`
- `backend.get`
- `array.set`
- `bufferAttribute.array.subarray`
- `device.createBuffer`
- `new array.constructor( buffer.getMappedRange() ).set`
- `buffer.getMappedRange`
- `buffer.unmap`

**Internal Comments:**
```
// patch for INT16 and UINT16
// Update BufferAttribute (x4)
// ensure 4 byte alignment (x2)
```

<details><summary>Code</summary>

```typescript
createAttribute( attribute, usage ) {

		const bufferAttribute = this._getBufferAttribute( attribute );

		const backend = this.backend;
		const bufferData = backend.get( bufferAttribute );

		let buffer = bufferData.buffer;

		if ( buffer === undefined ) {

			const device = backend.device;

			let array = bufferAttribute.array;

			// patch for INT16 and UINT16
			if ( attribute.normalized === false ) {

				if ( array.constructor === Int16Array || array.constructor === Int8Array ) {

					array = new Int32Array( array );

				} else if ( array.constructor === Uint16Array || array.constructor === Uint8Array ) {

					array = new Uint32Array( array );

					if ( usage & GPUBufferUsage.INDEX ) {

						for ( let i = 0; i < array.length; i ++ ) {

							if ( array[ i ] === 0xffff ) array[ i ] = 0xffffffff; // use correct primitive restart index

						}

					}

				}

			}

			bufferAttribute.array = array;

			if ( ( bufferAttribute.isStorageBufferAttribute || bufferAttribute.isStorageInstancedBufferAttribute ) && bufferAttribute.itemSize === 3 ) {

				array = new array.constructor( bufferAttribute.count * 4 );

				for ( let i = 0; i < bufferAttribute.count; i ++ ) {

					array.set( bufferAttribute.array.subarray( i * 3, i * 3 + 3 ), i * 4 );

				}

				// Update BufferAttribute
				bufferAttribute.itemSize = 4;
				bufferAttribute.array = array;

				bufferData._force3to4BytesAlignment = true;

			}

			// ensure 4 byte alignment
			const byteLength = array.byteLength;
			const size = byteLength + ( ( 4 - ( byteLength % 4 ) ) % 4 );

			buffer = device.createBuffer( {
				label: bufferAttribute.name,
				size: size,
				usage: usage,
				mappedAtCreation: true
			} );

			new array.constructor( buffer.getMappedRange() ).set( array );

			buffer.unmap();

			bufferData.buffer = buffer;

		}

	}
```
</details>

### `WebGPUAttributeUtils.updateAttribute(attribute: BufferAttribute): void`

**JSDoc:**
```typescript
/**
	 * Updates the GPU buffer of the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`

**Returns:** `void`

**Calls:**

- `this._getBufferAttribute`
- `backend.get`
- `array.set`
- `bufferAttribute.array.subarray`
- `this._isTypedArray`
- `device.queue.writeBuffer`
- `Math.floor`
- `Math.ceil`
- `bufferAttribute.clearUpdateRanges`

**Internal Comments:**
```
//  if storage buffer ensure 4 byte alignment
// Not using update ranges (x5)
```

<details><summary>Code</summary>

```typescript
updateAttribute( attribute ) {

		const bufferAttribute = this._getBufferAttribute( attribute );

		const backend = this.backend;
		const device = backend.device;

		const bufferData = backend.get( bufferAttribute );
		const buffer = backend.get( bufferAttribute ).buffer;

		let array = bufferAttribute.array;

		//  if storage buffer ensure 4 byte alignment
		if ( bufferData._force3to4BytesAlignment === true ) {

			array = new array.constructor( bufferAttribute.count * 4 );

			for ( let i = 0; i < bufferAttribute.count; i ++ ) {

				array.set( bufferAttribute.array.subarray( i * 3, i * 3 + 3 ), i * 4 );

			}

			bufferAttribute.array = array;

		}


		const isTypedArray = this._isTypedArray( array );
		const updateRanges = bufferAttribute.updateRanges;

		if ( updateRanges.length === 0 ) {

			// Not using update ranges

			device.queue.writeBuffer(
				buffer,
				0,
				array,
				0
			);

		} else {

			const byteOffsetFactor = isTypedArray ? 1 : array.BYTES_PER_ELEMENT;

			for ( let i = 0, l = updateRanges.length; i < l; i ++ ) {

				const range = updateRanges[ i ];
				let dataOffset, size;

				if ( bufferData._force3to4BytesAlignment === true ) {

					const vertexStart = Math.floor( range.start / 3 );
					const vertexCount = Math.ceil( range.count / 3 );
					dataOffset = vertexStart * 4 * byteOffsetFactor;
					size = vertexCount * 4 * byteOffsetFactor;

				} else {

					dataOffset = range.start * byteOffsetFactor;
					size = range.count * byteOffsetFactor;

				}

				const bufferOffset = dataOffset * ( isTypedArray ? array.BYTES_PER_ELEMENT : 1 ); // bufferOffset is always in bytes

				device.queue.writeBuffer(
					buffer,
					bufferOffset,
					array,
					dataOffset,
					size
				);

			}

			bufferAttribute.clearUpdateRanges();

		}

	}
```
</details>

### `WebGPUAttributeUtils.createShaderVertexBuffers(renderObject: RenderObject): any[]`

**JSDoc:**
```typescript
/**
	 * This method creates the vertex buffer layout data which are
	 * require when creating a render pipeline for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {Array<Object>} An array holding objects which describe the vertex buffer layout.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `any[]`

**Calls:**

- `renderObject.getAttributes`
- `this._getBufferAttribute`
- `vertexBuffers.get`
- `vertexBuffers.set`
- `this._getVertexFormat`
- `vertexBufferLayout.attributes.push`
- `Array.from`
- `vertexBuffers.values`

**Internal Comments:**
```
// patch for INT16 and UINT16
```

<details><summary>Code</summary>

```typescript
createShaderVertexBuffers( renderObject ) {

		const attributes = renderObject.getAttributes();
		const vertexBuffers = new Map();

		for ( let slot = 0; slot < attributes.length; slot ++ ) {

			const geometryAttribute = attributes[ slot ];
			const bytesPerElement = geometryAttribute.array.BYTES_PER_ELEMENT;
			const bufferAttribute = this._getBufferAttribute( geometryAttribute );

			let vertexBufferLayout = vertexBuffers.get( bufferAttribute );

			if ( vertexBufferLayout === undefined ) {

				let arrayStride, stepMode;

				if ( geometryAttribute.isInterleavedBufferAttribute === true ) {

					arrayStride = geometryAttribute.data.stride * bytesPerElement;
					stepMode = geometryAttribute.data.isInstancedInterleavedBuffer ? GPUInputStepMode.Instance : GPUInputStepMode.Vertex;

				} else {

					arrayStride = geometryAttribute.itemSize * bytesPerElement;
					stepMode = geometryAttribute.isInstancedBufferAttribute ? GPUInputStepMode.Instance : GPUInputStepMode.Vertex;

				}

				// patch for INT16 and UINT16
				if ( geometryAttribute.normalized === false && ( geometryAttribute.array.constructor === Int16Array || geometryAttribute.array.constructor === Uint16Array ) ) {

					arrayStride = 4;

				}

				vertexBufferLayout = {
					arrayStride,
					attributes: [],
					stepMode
				};

				vertexBuffers.set( bufferAttribute, vertexBufferLayout );

			}

			const format = this._getVertexFormat( geometryAttribute );
			const offset = ( geometryAttribute.isInterleavedBufferAttribute === true ) ? geometryAttribute.offset * bytesPerElement : 0;

			vertexBufferLayout.attributes.push( {
				shaderLocation: slot,
				offset,
				format
			} );

		}

		return Array.from( vertexBuffers.values() );

	}
```
</details>

### `WebGPUAttributeUtils.destroyAttribute(attribute: BufferAttribute): void`

**JSDoc:**
```typescript
/**
	 * Destroys the GPU buffer of the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`

**Returns:** `void`

**Calls:**

- `backend.get`
- `this._getBufferAttribute`
- `data.buffer.destroy`
- `backend.delete`

<details><summary>Code</summary>

```typescript
destroyAttribute( attribute ) {

		const backend = this.backend;
		const data = backend.get( this._getBufferAttribute( attribute ) );

		data.buffer.destroy();

		backend.delete( attribute );

	}
```
</details>

### `WebGPUAttributeUtils.getArrayBufferAsync(attribute: StorageBufferAttribute): Promise<ArrayBuffer>`

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

- `backend.get`
- `this._getBufferAttribute`
- `device.createBuffer`
- `device.createCommandEncoder`
- `cmdEncoder.copyBufferToBuffer`
- `cmdEncoder.finish`
- `device.queue.submit`
- `readBufferGPU.mapAsync`
- `readBufferGPU.getMappedRange`
- `arrayBuffer.slice`
- `readBufferGPU.unmap`

<details><summary>Code</summary>

```typescript
async getArrayBufferAsync( attribute ) {

		const backend = this.backend;
		const device = backend.device;

		const data = backend.get( this._getBufferAttribute( attribute ) );
		const bufferGPU = data.buffer;
		const size = bufferGPU.size;

		const readBufferGPU = device.createBuffer( {
			label: `${ attribute.name }_readback`,
			size,
			usage: GPUBufferUsage.COPY_DST | GPUBufferUsage.MAP_READ
		} );

		const cmdEncoder = device.createCommandEncoder( {
			label: `readback_encoder_${ attribute.name }`
		} );

		cmdEncoder.copyBufferToBuffer(
			bufferGPU,
			0,
			readBufferGPU,
			0,
			size
		);

		const gpuCommands = cmdEncoder.finish();
		device.queue.submit( [ gpuCommands ] );

		await readBufferGPU.mapAsync( GPUMapMode.READ );

		const arrayBuffer = readBufferGPU.getMappedRange();

		const dstBuffer = new attribute.array.constructor( arrayBuffer.slice( 0 ) );

		readBufferGPU.unmap();

		return dstBuffer.buffer;

	}
```
</details>

### `WebGPUAttributeUtils._getVertexFormat(geometryAttribute: BufferAttribute): string`

**JSDoc:**
```typescript
/**
	 * Returns the vertex format of the given buffer attribute.
	 *
	 * @private
	 * @param {BufferAttribute} geometryAttribute - The buffer attribute.
	 * @return {string|undefined} The vertex format (e.g. 'float32x3').
	 */
```

**Parameters:**

- **`geometryAttribute`** `BufferAttribute`

**Returns:** `string`

**Calls:**

- `typeArraysToVertexFormatPrefixForItemSize1.get`
- `typedAttributeToVertexFormatPrefix.get`
- `typedArraysToVertexFormatPrefix.get`
- `Math.floor`
- `console.error`

<details><summary>Code</summary>

```typescript
_getVertexFormat( geometryAttribute ) {

		const { itemSize, normalized } = geometryAttribute;
		const ArrayType = geometryAttribute.array.constructor;
		const AttributeType = geometryAttribute.constructor;

		let format;

		if ( itemSize === 1 ) {

			format = typeArraysToVertexFormatPrefixForItemSize1.get( ArrayType );

		} else {

			const prefixOptions = typedAttributeToVertexFormatPrefix.get( AttributeType ) || typedArraysToVertexFormatPrefix.get( ArrayType );
			const prefix = prefixOptions[ normalized ? 1 : 0 ];

			if ( prefix ) {

				const bytesPerUnit = ArrayType.BYTES_PER_ELEMENT * itemSize;
				const paddedBytesPerUnit = Math.floor( ( bytesPerUnit + 3 ) / 4 ) * 4;
				const paddedItemSize = paddedBytesPerUnit / ArrayType.BYTES_PER_ELEMENT;

				if ( paddedItemSize % 1 ) {

					throw new Error( 'THREE.WebGPUAttributeUtils: Bad vertex format item size.' );

				}

				format = `${prefix}x${paddedItemSize}`;

			}

		}

		if ( ! format ) {

			console.error( 'THREE.WebGPUAttributeUtils: Vertex format not supported yet.' );

		}

		return format;

	}
```
</details>

### `WebGPUAttributeUtils._isTypedArray(array: any): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given array is a typed array.
	 *
	 * @private
	 * @param {any} array - The array.
	 * @return {boolean} Whether the given array is a typed array or not.
	 */
```

**Parameters:**

- **`array`** `any`

**Returns:** `boolean`

**Calls:**

- `ArrayBuffer.isView`

<details><summary>Code</summary>

```typescript
_isTypedArray( array ) {

		return ArrayBuffer.isView( array ) && ! ( array instanceof DataView );

	}
```
</details>

### `WebGPUAttributeUtils._getBufferAttribute(attribute: BufferAttribute): any`

**JSDoc:**
```typescript
/**
	 * Utility method for handling interleaved buffer attributes correctly.
	 * To process them, their `InterleavedBuffer` is returned.
	 *
	 * @private
	 * @param {BufferAttribute} attribute - The attribute.
	 * @return {BufferAttribute|InterleavedBuffer}
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
_getBufferAttribute( attribute ) {

		if ( attribute.isInterleavedBufferAttribute ) attribute = attribute.data;

		return attribute;

	}
```
</details>


---

## Classes

### `WebGPUAttributeUtils`

<details><summary>Class Code</summary>

```ts
class WebGPUAttributeUtils {

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
	 * Creates the GPU buffer for the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 * @param {GPUBufferUsage} usage - A flag that indicates how the buffer may be used after its creation.
	 */
	createAttribute( attribute, usage ) {

		const bufferAttribute = this._getBufferAttribute( attribute );

		const backend = this.backend;
		const bufferData = backend.get( bufferAttribute );

		let buffer = bufferData.buffer;

		if ( buffer === undefined ) {

			const device = backend.device;

			let array = bufferAttribute.array;

			// patch for INT16 and UINT16
			if ( attribute.normalized === false ) {

				if ( array.constructor === Int16Array || array.constructor === Int8Array ) {

					array = new Int32Array( array );

				} else if ( array.constructor === Uint16Array || array.constructor === Uint8Array ) {

					array = new Uint32Array( array );

					if ( usage & GPUBufferUsage.INDEX ) {

						for ( let i = 0; i < array.length; i ++ ) {

							if ( array[ i ] === 0xffff ) array[ i ] = 0xffffffff; // use correct primitive restart index

						}

					}

				}

			}

			bufferAttribute.array = array;

			if ( ( bufferAttribute.isStorageBufferAttribute || bufferAttribute.isStorageInstancedBufferAttribute ) && bufferAttribute.itemSize === 3 ) {

				array = new array.constructor( bufferAttribute.count * 4 );

				for ( let i = 0; i < bufferAttribute.count; i ++ ) {

					array.set( bufferAttribute.array.subarray( i * 3, i * 3 + 3 ), i * 4 );

				}

				// Update BufferAttribute
				bufferAttribute.itemSize = 4;
				bufferAttribute.array = array;

				bufferData._force3to4BytesAlignment = true;

			}

			// ensure 4 byte alignment
			const byteLength = array.byteLength;
			const size = byteLength + ( ( 4 - ( byteLength % 4 ) ) % 4 );

			buffer = device.createBuffer( {
				label: bufferAttribute.name,
				size: size,
				usage: usage,
				mappedAtCreation: true
			} );

			new array.constructor( buffer.getMappedRange() ).set( array );

			buffer.unmap();

			bufferData.buffer = buffer;

		}

	}

	/**
	 * Updates the GPU buffer of the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
	updateAttribute( attribute ) {

		const bufferAttribute = this._getBufferAttribute( attribute );

		const backend = this.backend;
		const device = backend.device;

		const bufferData = backend.get( bufferAttribute );
		const buffer = backend.get( bufferAttribute ).buffer;

		let array = bufferAttribute.array;

		//  if storage buffer ensure 4 byte alignment
		if ( bufferData._force3to4BytesAlignment === true ) {

			array = new array.constructor( bufferAttribute.count * 4 );

			for ( let i = 0; i < bufferAttribute.count; i ++ ) {

				array.set( bufferAttribute.array.subarray( i * 3, i * 3 + 3 ), i * 4 );

			}

			bufferAttribute.array = array;

		}


		const isTypedArray = this._isTypedArray( array );
		const updateRanges = bufferAttribute.updateRanges;

		if ( updateRanges.length === 0 ) {

			// Not using update ranges

			device.queue.writeBuffer(
				buffer,
				0,
				array,
				0
			);

		} else {

			const byteOffsetFactor = isTypedArray ? 1 : array.BYTES_PER_ELEMENT;

			for ( let i = 0, l = updateRanges.length; i < l; i ++ ) {

				const range = updateRanges[ i ];
				let dataOffset, size;

				if ( bufferData._force3to4BytesAlignment === true ) {

					const vertexStart = Math.floor( range.start / 3 );
					const vertexCount = Math.ceil( range.count / 3 );
					dataOffset = vertexStart * 4 * byteOffsetFactor;
					size = vertexCount * 4 * byteOffsetFactor;

				} else {

					dataOffset = range.start * byteOffsetFactor;
					size = range.count * byteOffsetFactor;

				}

				const bufferOffset = dataOffset * ( isTypedArray ? array.BYTES_PER_ELEMENT : 1 ); // bufferOffset is always in bytes

				device.queue.writeBuffer(
					buffer,
					bufferOffset,
					array,
					dataOffset,
					size
				);

			}

			bufferAttribute.clearUpdateRanges();

		}

	}

	/**
	 * This method creates the vertex buffer layout data which are
	 * require when creating a render pipeline for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {Array<Object>} An array holding objects which describe the vertex buffer layout.
	 */
	createShaderVertexBuffers( renderObject ) {

		const attributes = renderObject.getAttributes();
		const vertexBuffers = new Map();

		for ( let slot = 0; slot < attributes.length; slot ++ ) {

			const geometryAttribute = attributes[ slot ];
			const bytesPerElement = geometryAttribute.array.BYTES_PER_ELEMENT;
			const bufferAttribute = this._getBufferAttribute( geometryAttribute );

			let vertexBufferLayout = vertexBuffers.get( bufferAttribute );

			if ( vertexBufferLayout === undefined ) {

				let arrayStride, stepMode;

				if ( geometryAttribute.isInterleavedBufferAttribute === true ) {

					arrayStride = geometryAttribute.data.stride * bytesPerElement;
					stepMode = geometryAttribute.data.isInstancedInterleavedBuffer ? GPUInputStepMode.Instance : GPUInputStepMode.Vertex;

				} else {

					arrayStride = geometryAttribute.itemSize * bytesPerElement;
					stepMode = geometryAttribute.isInstancedBufferAttribute ? GPUInputStepMode.Instance : GPUInputStepMode.Vertex;

				}

				// patch for INT16 and UINT16
				if ( geometryAttribute.normalized === false && ( geometryAttribute.array.constructor === Int16Array || geometryAttribute.array.constructor === Uint16Array ) ) {

					arrayStride = 4;

				}

				vertexBufferLayout = {
					arrayStride,
					attributes: [],
					stepMode
				};

				vertexBuffers.set( bufferAttribute, vertexBufferLayout );

			}

			const format = this._getVertexFormat( geometryAttribute );
			const offset = ( geometryAttribute.isInterleavedBufferAttribute === true ) ? geometryAttribute.offset * bytesPerElement : 0;

			vertexBufferLayout.attributes.push( {
				shaderLocation: slot,
				offset,
				format
			} );

		}

		return Array.from( vertexBuffers.values() );

	}

	/**
	 * Destroys the GPU buffer of the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
	destroyAttribute( attribute ) {

		const backend = this.backend;
		const data = backend.get( this._getBufferAttribute( attribute ) );

		data.buffer.destroy();

		backend.delete( attribute );

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

		const backend = this.backend;
		const device = backend.device;

		const data = backend.get( this._getBufferAttribute( attribute ) );
		const bufferGPU = data.buffer;
		const size = bufferGPU.size;

		const readBufferGPU = device.createBuffer( {
			label: `${ attribute.name }_readback`,
			size,
			usage: GPUBufferUsage.COPY_DST | GPUBufferUsage.MAP_READ
		} );

		const cmdEncoder = device.createCommandEncoder( {
			label: `readback_encoder_${ attribute.name }`
		} );

		cmdEncoder.copyBufferToBuffer(
			bufferGPU,
			0,
			readBufferGPU,
			0,
			size
		);

		const gpuCommands = cmdEncoder.finish();
		device.queue.submit( [ gpuCommands ] );

		await readBufferGPU.mapAsync( GPUMapMode.READ );

		const arrayBuffer = readBufferGPU.getMappedRange();

		const dstBuffer = new attribute.array.constructor( arrayBuffer.slice( 0 ) );

		readBufferGPU.unmap();

		return dstBuffer.buffer;

	}

	/**
	 * Returns the vertex format of the given buffer attribute.
	 *
	 * @private
	 * @param {BufferAttribute} geometryAttribute - The buffer attribute.
	 * @return {string|undefined} The vertex format (e.g. 'float32x3').
	 */
	_getVertexFormat( geometryAttribute ) {

		const { itemSize, normalized } = geometryAttribute;
		const ArrayType = geometryAttribute.array.constructor;
		const AttributeType = geometryAttribute.constructor;

		let format;

		if ( itemSize === 1 ) {

			format = typeArraysToVertexFormatPrefixForItemSize1.get( ArrayType );

		} else {

			const prefixOptions = typedAttributeToVertexFormatPrefix.get( AttributeType ) || typedArraysToVertexFormatPrefix.get( ArrayType );
			const prefix = prefixOptions[ normalized ? 1 : 0 ];

			if ( prefix ) {

				const bytesPerUnit = ArrayType.BYTES_PER_ELEMENT * itemSize;
				const paddedBytesPerUnit = Math.floor( ( bytesPerUnit + 3 ) / 4 ) * 4;
				const paddedItemSize = paddedBytesPerUnit / ArrayType.BYTES_PER_ELEMENT;

				if ( paddedItemSize % 1 ) {

					throw new Error( 'THREE.WebGPUAttributeUtils: Bad vertex format item size.' );

				}

				format = `${prefix}x${paddedItemSize}`;

			}

		}

		if ( ! format ) {

			console.error( 'THREE.WebGPUAttributeUtils: Vertex format not supported yet.' );

		}

		return format;

	}

	/**
	 * Returns `true` if the given array is a typed array.
	 *
	 * @private
	 * @param {any} array - The array.
	 * @return {boolean} Whether the given array is a typed array or not.
	 */
	_isTypedArray( array ) {

		return ArrayBuffer.isView( array ) && ! ( array instanceof DataView );

	}

	/**
	 * Utility method for handling interleaved buffer attributes correctly.
	 * To process them, their `InterleavedBuffer` is returned.
	 *
	 * @private
	 * @param {BufferAttribute} attribute - The attribute.
	 * @return {BufferAttribute|InterleavedBuffer}
	 */
	_getBufferAttribute( attribute ) {

		if ( attribute.isInterleavedBufferAttribute ) attribute = attribute.data;

		return attribute;

	}

}
```
</details>

#### Methods

##### `createAttribute(attribute: BufferAttribute, usage: GPUBufferUsage): void`

<details><summary>Code</summary>

```ts
createAttribute( attribute, usage ) {

		const bufferAttribute = this._getBufferAttribute( attribute );

		const backend = this.backend;
		const bufferData = backend.get( bufferAttribute );

		let buffer = bufferData.buffer;

		if ( buffer === undefined ) {

			const device = backend.device;

			let array = bufferAttribute.array;

			// patch for INT16 and UINT16
			if ( attribute.normalized === false ) {

				if ( array.constructor === Int16Array || array.constructor === Int8Array ) {

					array = new Int32Array( array );

				} else if ( array.constructor === Uint16Array || array.constructor === Uint8Array ) {

					array = new Uint32Array( array );

					if ( usage & GPUBufferUsage.INDEX ) {

						for ( let i = 0; i < array.length; i ++ ) {

							if ( array[ i ] === 0xffff ) array[ i ] = 0xffffffff; // use correct primitive restart index

						}

					}

				}

			}

			bufferAttribute.array = array;

			if ( ( bufferAttribute.isStorageBufferAttribute || bufferAttribute.isStorageInstancedBufferAttribute ) && bufferAttribute.itemSize === 3 ) {

				array = new array.constructor( bufferAttribute.count * 4 );

				for ( let i = 0; i < bufferAttribute.count; i ++ ) {

					array.set( bufferAttribute.array.subarray( i * 3, i * 3 + 3 ), i * 4 );

				}

				// Update BufferAttribute
				bufferAttribute.itemSize = 4;
				bufferAttribute.array = array;

				bufferData._force3to4BytesAlignment = true;

			}

			// ensure 4 byte alignment
			const byteLength = array.byteLength;
			const size = byteLength + ( ( 4 - ( byteLength % 4 ) ) % 4 );

			buffer = device.createBuffer( {
				label: bufferAttribute.name,
				size: size,
				usage: usage,
				mappedAtCreation: true
			} );

			new array.constructor( buffer.getMappedRange() ).set( array );

			buffer.unmap();

			bufferData.buffer = buffer;

		}

	}
```
</details>

##### `updateAttribute(attribute: BufferAttribute): void`

<details><summary>Code</summary>

```ts
updateAttribute( attribute ) {

		const bufferAttribute = this._getBufferAttribute( attribute );

		const backend = this.backend;
		const device = backend.device;

		const bufferData = backend.get( bufferAttribute );
		const buffer = backend.get( bufferAttribute ).buffer;

		let array = bufferAttribute.array;

		//  if storage buffer ensure 4 byte alignment
		if ( bufferData._force3to4BytesAlignment === true ) {

			array = new array.constructor( bufferAttribute.count * 4 );

			for ( let i = 0; i < bufferAttribute.count; i ++ ) {

				array.set( bufferAttribute.array.subarray( i * 3, i * 3 + 3 ), i * 4 );

			}

			bufferAttribute.array = array;

		}


		const isTypedArray = this._isTypedArray( array );
		const updateRanges = bufferAttribute.updateRanges;

		if ( updateRanges.length === 0 ) {

			// Not using update ranges

			device.queue.writeBuffer(
				buffer,
				0,
				array,
				0
			);

		} else {

			const byteOffsetFactor = isTypedArray ? 1 : array.BYTES_PER_ELEMENT;

			for ( let i = 0, l = updateRanges.length; i < l; i ++ ) {

				const range = updateRanges[ i ];
				let dataOffset, size;

				if ( bufferData._force3to4BytesAlignment === true ) {

					const vertexStart = Math.floor( range.start / 3 );
					const vertexCount = Math.ceil( range.count / 3 );
					dataOffset = vertexStart * 4 * byteOffsetFactor;
					size = vertexCount * 4 * byteOffsetFactor;

				} else {

					dataOffset = range.start * byteOffsetFactor;
					size = range.count * byteOffsetFactor;

				}

				const bufferOffset = dataOffset * ( isTypedArray ? array.BYTES_PER_ELEMENT : 1 ); // bufferOffset is always in bytes

				device.queue.writeBuffer(
					buffer,
					bufferOffset,
					array,
					dataOffset,
					size
				);

			}

			bufferAttribute.clearUpdateRanges();

		}

	}
```
</details>

##### `createShaderVertexBuffers(renderObject: RenderObject): any[]`

<details><summary>Code</summary>

```ts
createShaderVertexBuffers( renderObject ) {

		const attributes = renderObject.getAttributes();
		const vertexBuffers = new Map();

		for ( let slot = 0; slot < attributes.length; slot ++ ) {

			const geometryAttribute = attributes[ slot ];
			const bytesPerElement = geometryAttribute.array.BYTES_PER_ELEMENT;
			const bufferAttribute = this._getBufferAttribute( geometryAttribute );

			let vertexBufferLayout = vertexBuffers.get( bufferAttribute );

			if ( vertexBufferLayout === undefined ) {

				let arrayStride, stepMode;

				if ( geometryAttribute.isInterleavedBufferAttribute === true ) {

					arrayStride = geometryAttribute.data.stride * bytesPerElement;
					stepMode = geometryAttribute.data.isInstancedInterleavedBuffer ? GPUInputStepMode.Instance : GPUInputStepMode.Vertex;

				} else {

					arrayStride = geometryAttribute.itemSize * bytesPerElement;
					stepMode = geometryAttribute.isInstancedBufferAttribute ? GPUInputStepMode.Instance : GPUInputStepMode.Vertex;

				}

				// patch for INT16 and UINT16
				if ( geometryAttribute.normalized === false && ( geometryAttribute.array.constructor === Int16Array || geometryAttribute.array.constructor === Uint16Array ) ) {

					arrayStride = 4;

				}

				vertexBufferLayout = {
					arrayStride,
					attributes: [],
					stepMode
				};

				vertexBuffers.set( bufferAttribute, vertexBufferLayout );

			}

			const format = this._getVertexFormat( geometryAttribute );
			const offset = ( geometryAttribute.isInterleavedBufferAttribute === true ) ? geometryAttribute.offset * bytesPerElement : 0;

			vertexBufferLayout.attributes.push( {
				shaderLocation: slot,
				offset,
				format
			} );

		}

		return Array.from( vertexBuffers.values() );

	}
```
</details>

##### `destroyAttribute(attribute: BufferAttribute): void`

<details><summary>Code</summary>

```ts
destroyAttribute( attribute ) {

		const backend = this.backend;
		const data = backend.get( this._getBufferAttribute( attribute ) );

		data.buffer.destroy();

		backend.delete( attribute );

	}
```
</details>

##### `getArrayBufferAsync(attribute: StorageBufferAttribute): Promise<ArrayBuffer>`

<details><summary>Code</summary>

```ts
async getArrayBufferAsync( attribute ) {

		const backend = this.backend;
		const device = backend.device;

		const data = backend.get( this._getBufferAttribute( attribute ) );
		const bufferGPU = data.buffer;
		const size = bufferGPU.size;

		const readBufferGPU = device.createBuffer( {
			label: `${ attribute.name }_readback`,
			size,
			usage: GPUBufferUsage.COPY_DST | GPUBufferUsage.MAP_READ
		} );

		const cmdEncoder = device.createCommandEncoder( {
			label: `readback_encoder_${ attribute.name }`
		} );

		cmdEncoder.copyBufferToBuffer(
			bufferGPU,
			0,
			readBufferGPU,
			0,
			size
		);

		const gpuCommands = cmdEncoder.finish();
		device.queue.submit( [ gpuCommands ] );

		await readBufferGPU.mapAsync( GPUMapMode.READ );

		const arrayBuffer = readBufferGPU.getMappedRange();

		const dstBuffer = new attribute.array.constructor( arrayBuffer.slice( 0 ) );

		readBufferGPU.unmap();

		return dstBuffer.buffer;

	}
```
</details>

##### `_getVertexFormat(geometryAttribute: BufferAttribute): string`

<details><summary>Code</summary>

```ts
_getVertexFormat( geometryAttribute ) {

		const { itemSize, normalized } = geometryAttribute;
		const ArrayType = geometryAttribute.array.constructor;
		const AttributeType = geometryAttribute.constructor;

		let format;

		if ( itemSize === 1 ) {

			format = typeArraysToVertexFormatPrefixForItemSize1.get( ArrayType );

		} else {

			const prefixOptions = typedAttributeToVertexFormatPrefix.get( AttributeType ) || typedArraysToVertexFormatPrefix.get( ArrayType );
			const prefix = prefixOptions[ normalized ? 1 : 0 ];

			if ( prefix ) {

				const bytesPerUnit = ArrayType.BYTES_PER_ELEMENT * itemSize;
				const paddedBytesPerUnit = Math.floor( ( bytesPerUnit + 3 ) / 4 ) * 4;
				const paddedItemSize = paddedBytesPerUnit / ArrayType.BYTES_PER_ELEMENT;

				if ( paddedItemSize % 1 ) {

					throw new Error( 'THREE.WebGPUAttributeUtils: Bad vertex format item size.' );

				}

				format = `${prefix}x${paddedItemSize}`;

			}

		}

		if ( ! format ) {

			console.error( 'THREE.WebGPUAttributeUtils: Vertex format not supported yet.' );

		}

		return format;

	}
```
</details>

##### `_isTypedArray(array: any): boolean`

<details><summary>Code</summary>

```ts
_isTypedArray( array ) {

		return ArrayBuffer.isView( array ) && ! ( array instanceof DataView );

	}
```
</details>

##### `_getBufferAttribute(attribute: BufferAttribute): any`

<details><summary>Code</summary>

```ts
_getBufferAttribute( attribute ) {

		if ( attribute.isInterleavedBufferAttribute ) attribute = attribute.data;

		return attribute;

	}
```
</details>


---