[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `WebGLAttributeUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 2 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 20 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgl-fallback/utils/WebGLAttributeUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `IntType` | `../../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_id` | `number` | let/var | `0` | ✗ |
| `backend` | `WebGLBackend` | let/var | `this.backend` | ✗ |
| `array` | `any` | let/var | `attribute.array` | ✗ |
| `usage` | `any` | let/var | `attribute.usage \|\| gl.STATIC_DRAW` | ✗ |
| `bufferAttribute` | `any` | let/var | `attribute.isInterleavedBufferAttribute ? attribute.data : attribute` | ✗ |
| `bufferGPU` | `any` | let/var | `bufferData.bufferGPU` | ✗ |
| `type` | `any` | let/var | `*not shown*` | ✗ |
| `attributeData` | `{ bufferGPU: any; bufferType: number;...` | let/var | `{ bufferGPU, bufferType, type, byteLength: array.byteLength, bytesPerElement:...` | ✗ |
| `backend` | `WebGLBackend` | let/var | `this.backend` | ✗ |
| `array` | `any` | let/var | `attribute.array` | ✗ |
| `bufferAttribute` | `any` | let/var | `attribute.isInterleavedBufferAttribute ? attribute.data : attribute` | ✗ |
| `bufferType` | `any` | let/var | `bufferData.bufferType` | ✗ |
| `updateRanges` | `any` | let/var | `attribute.isInterleavedBufferAttribute ? attribute.data.updateRanges : attrib...` | ✗ |
| `range` | `any` | let/var | `updateRanges[ i ]` | ✗ |
| `backend` | `WebGLBackend` | let/var | `this.backend` | ✗ |
| `backend` | `WebGLBackend` | let/var | `this.backend` | ✗ |
| `bufferAttribute` | `any` | let/var | `attribute.isInterleavedBufferAttribute ? attribute.data : attribute` | ✗ |
| `array` | `any` | let/var | `attribute.array` | ✗ |
| `byteLength` | `any` | let/var | `array.byteLength` | ✗ |
| `dstBuffer` | `any` | let/var | `new attribute.array.constructor( array.length )` | ✗ |


---

## Functions

### `DualAttributeData.switchBuffers(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
switchBuffers() {

		this.activeBufferIndex ^= 1;

	}
```
</details>

### `WebGLAttributeUtils.createAttribute(attribute: BufferAttribute, bufferType: number): void`

**JSDoc:**
```typescript
/**
	 * Creates the GPU buffer for the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 * @param {GLenum } bufferType - A flag that indicates the buffer type and thus binding point target.
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`
- **`bufferType`** `number`

**Returns:** `void`

**Calls:**

- `backend.get`
- `this._createBuffer`
- `backend.set`

**Internal Comments:**
```
//attribute.onUploadCallback(); (x2)
// create buffer for transform feedback use (x2)
```

<details><summary>Code</summary>

```typescript
createAttribute( attribute, bufferType ) {

		const backend = this.backend;
		const { gl } = backend;

		const array = attribute.array;
		const usage = attribute.usage || gl.STATIC_DRAW;

		const bufferAttribute = attribute.isInterleavedBufferAttribute ? attribute.data : attribute;
		const bufferData = backend.get( bufferAttribute );

		let bufferGPU = bufferData.bufferGPU;

		if ( bufferGPU === undefined ) {

			bufferGPU = this._createBuffer( gl, bufferType, array, usage );

			bufferData.bufferGPU = bufferGPU;
			bufferData.bufferType = bufferType;
			bufferData.version = bufferAttribute.version;

		}

		//attribute.onUploadCallback();

		let type;

		if ( array instanceof Float32Array ) {

			type = gl.FLOAT;

		} else if ( typeof Float16Array !== 'undefined' && array instanceof Float16Array ) {

			type = gl.HALF_FLOAT;

		} else if ( array instanceof Uint16Array ) {

			if ( attribute.isFloat16BufferAttribute ) {

				type = gl.HALF_FLOAT;

			} else {

				type = gl.UNSIGNED_SHORT;

			}

		} else if ( array instanceof Int16Array ) {

			type = gl.SHORT;

		} else if ( array instanceof Uint32Array ) {

			type = gl.UNSIGNED_INT;

		} else if ( array instanceof Int32Array ) {

			type = gl.INT;

		} else if ( array instanceof Int8Array ) {

			type = gl.BYTE;

		} else if ( array instanceof Uint8Array ) {

			type = gl.UNSIGNED_BYTE;

		} else if ( array instanceof Uint8ClampedArray ) {

			type = gl.UNSIGNED_BYTE;

		} else {

			throw new Error( 'THREE.WebGLBackend: Unsupported buffer data format: ' + array );

		}

		let attributeData = {
			bufferGPU,
			bufferType,
			type,
			byteLength: array.byteLength,
			bytesPerElement: array.BYTES_PER_ELEMENT,
			version: attribute.version,
			pbo: attribute.pbo,
			isInteger: type === gl.INT || type === gl.UNSIGNED_INT || attribute.gpuType === IntType,
			id: _id ++
		};

		if ( attribute.isStorageBufferAttribute || attribute.isStorageInstancedBufferAttribute ) {

			// create buffer for transform feedback use
			const bufferGPUDual = this._createBuffer( gl, bufferType, array, usage );
			attributeData = new DualAttributeData( attributeData, bufferGPUDual );

		}

		backend.set( attribute, attributeData );

	}
```
</details>

### `WebGLAttributeUtils.updateAttribute(attribute: BufferAttribute): void`

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

- `backend.get`
- `gl.bindBuffer`
- `gl.bufferSubData`
- `bufferAttribute.clearUpdateRanges`

**Internal Comments:**
```
// Not using update ranges (x4)
```

<details><summary>Code</summary>

```typescript
updateAttribute( attribute ) {

		const backend = this.backend;
		const { gl } = backend;

		const array = attribute.array;
		const bufferAttribute = attribute.isInterleavedBufferAttribute ? attribute.data : attribute;
		const bufferData = backend.get( bufferAttribute );
		const bufferType = bufferData.bufferType;
		const updateRanges = attribute.isInterleavedBufferAttribute ? attribute.data.updateRanges : attribute.updateRanges;

		gl.bindBuffer( bufferType, bufferData.bufferGPU );

		if ( updateRanges.length === 0 ) {

			// Not using update ranges

			gl.bufferSubData( bufferType, 0, array );

		} else {

			for ( let i = 0, l = updateRanges.length; i < l; i ++ ) {

				const range = updateRanges[ i ];
				gl.bufferSubData( bufferType, range.start * array.BYTES_PER_ELEMENT,
					array, range.start, range.count );

			}

			bufferAttribute.clearUpdateRanges();

		}

		gl.bindBuffer( bufferType, null );

		bufferData.version = bufferAttribute.version;

	}
```
</details>

### `WebGLAttributeUtils.destroyAttribute(attribute: BufferAttribute): void`

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

- `backend.delete`
- `backend.get`
- `gl.deleteBuffer`

<details><summary>Code</summary>

```typescript
destroyAttribute( attribute ) {

		const backend = this.backend;
		const { gl } = backend;

		if ( attribute.isInterleavedBufferAttribute ) {

			backend.delete( attribute.data );

		}

		const attributeData = backend.get( attribute );

		gl.deleteBuffer( attributeData.bufferGPU );

		backend.delete( attribute );

	}
```
</details>

### `WebGLAttributeUtils.getArrayBufferAsync(attribute: StorageBufferAttribute): Promise<ArrayBuffer>`

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
- `gl.bindBuffer`
- `gl.createBuffer`
- `gl.bufferData`
- `gl.copyBufferSubData`
- `backend.utils._clientWaitAsync`
- `gl.getBufferSubData`
- `gl.deleteBuffer`

**Internal Comments:**
```
// Ensure the buffer is bound before reading (x4)
```

<details><summary>Code</summary>

```typescript
async getArrayBufferAsync( attribute ) {

		const backend = this.backend;
		const { gl } = backend;

		const bufferAttribute = attribute.isInterleavedBufferAttribute ? attribute.data : attribute;
		const { bufferGPU } = backend.get( bufferAttribute );

		const array = attribute.array;
		const byteLength = array.byteLength;

		gl.bindBuffer( gl.COPY_READ_BUFFER, bufferGPU );

		const writeBuffer = gl.createBuffer();

		gl.bindBuffer( gl.COPY_WRITE_BUFFER, writeBuffer );
		gl.bufferData( gl.COPY_WRITE_BUFFER, byteLength, gl.STREAM_READ );

		gl.copyBufferSubData( gl.COPY_READ_BUFFER, gl.COPY_WRITE_BUFFER, 0, 0, byteLength );

		await backend.utils._clientWaitAsync();

		const dstBuffer = new attribute.array.constructor( array.length );

		// Ensure the buffer is bound before reading
		gl.bindBuffer( gl.COPY_WRITE_BUFFER, writeBuffer );

		gl.getBufferSubData( gl.COPY_WRITE_BUFFER, 0, dstBuffer );

		gl.deleteBuffer( writeBuffer );

		gl.bindBuffer( gl.COPY_READ_BUFFER, null );
		gl.bindBuffer( gl.COPY_WRITE_BUFFER, null );

		return dstBuffer.buffer;

	}
```
</details>

### `WebGLAttributeUtils._createBuffer(gl: WebGL2RenderingContext, bufferType: number, array: TypedArray, usage: number): WebGLBuffer`

**JSDoc:**
```typescript
/**
	 * Creates a WebGL buffer with the given data.
	 *
	 * @private
	 * @param {WebGL2RenderingContext} gl - The rendering context.
	 * @param {GLenum } bufferType - A flag that indicates the buffer type and thus binding point target.
	 * @param {TypedArray} array - The array of the buffer attribute.
	 * @param {GLenum} usage - The usage.
	 * @return {WebGLBuffer} The WebGL buffer.
	 */
```

**Parameters:**

- **`gl`** `WebGL2RenderingContext`
- **`bufferType`** `number`
- **`array`** `TypedArray`
- **`usage`** `number`

**Returns:** `WebGLBuffer`

**Calls:**

- `gl.createBuffer`
- `gl.bindBuffer`
- `gl.bufferData`

<details><summary>Code</summary>

```typescript
_createBuffer( gl, bufferType, array, usage ) {

		const bufferGPU = gl.createBuffer();

		gl.bindBuffer( bufferType, bufferGPU );
		gl.bufferData( bufferType, array, usage );
		gl.bindBuffer( bufferType, null );

		return bufferGPU;

	}
```
</details>


---

## Classes

### `DualAttributeData`

<details><summary>Class Code</summary>

```ts
class DualAttributeData {

	constructor( attributeData, dualBuffer ) {

		this.buffers = [ attributeData.bufferGPU, dualBuffer ];
		this.type = attributeData.type;
		this.bufferType = attributeData.bufferType;
		this.pbo = attributeData.pbo;
		this.byteLength = attributeData.byteLength;
		this.bytesPerElement = attributeData.BYTES_PER_ELEMENT;
		this.version = attributeData.version;
		this.isInteger = attributeData.isInteger;
		this.activeBufferIndex = 0;
		this.baseId = attributeData.id;

	}


	get id() {

		return `${ this.baseId }|${ this.activeBufferIndex }`;

	}

	get bufferGPU() {

		return this.buffers[ this.activeBufferIndex ];

	}

	get transformBuffer() {

		return this.buffers[ this.activeBufferIndex ^ 1 ];

	}

	switchBuffers() {

		this.activeBufferIndex ^= 1;

	}

}
```
</details>

#### Methods

##### `switchBuffers(): void`

<details><summary>Code</summary>

```ts
switchBuffers() {

		this.activeBufferIndex ^= 1;

	}
```
</details>

### `WebGLAttributeUtils`

<details><summary>Class Code</summary>

```ts
class WebGLAttributeUtils {

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

	}

	/**
	 * Creates the GPU buffer for the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 * @param {GLenum } bufferType - A flag that indicates the buffer type and thus binding point target.
	 */
	createAttribute( attribute, bufferType ) {

		const backend = this.backend;
		const { gl } = backend;

		const array = attribute.array;
		const usage = attribute.usage || gl.STATIC_DRAW;

		const bufferAttribute = attribute.isInterleavedBufferAttribute ? attribute.data : attribute;
		const bufferData = backend.get( bufferAttribute );

		let bufferGPU = bufferData.bufferGPU;

		if ( bufferGPU === undefined ) {

			bufferGPU = this._createBuffer( gl, bufferType, array, usage );

			bufferData.bufferGPU = bufferGPU;
			bufferData.bufferType = bufferType;
			bufferData.version = bufferAttribute.version;

		}

		//attribute.onUploadCallback();

		let type;

		if ( array instanceof Float32Array ) {

			type = gl.FLOAT;

		} else if ( typeof Float16Array !== 'undefined' && array instanceof Float16Array ) {

			type = gl.HALF_FLOAT;

		} else if ( array instanceof Uint16Array ) {

			if ( attribute.isFloat16BufferAttribute ) {

				type = gl.HALF_FLOAT;

			} else {

				type = gl.UNSIGNED_SHORT;

			}

		} else if ( array instanceof Int16Array ) {

			type = gl.SHORT;

		} else if ( array instanceof Uint32Array ) {

			type = gl.UNSIGNED_INT;

		} else if ( array instanceof Int32Array ) {

			type = gl.INT;

		} else if ( array instanceof Int8Array ) {

			type = gl.BYTE;

		} else if ( array instanceof Uint8Array ) {

			type = gl.UNSIGNED_BYTE;

		} else if ( array instanceof Uint8ClampedArray ) {

			type = gl.UNSIGNED_BYTE;

		} else {

			throw new Error( 'THREE.WebGLBackend: Unsupported buffer data format: ' + array );

		}

		let attributeData = {
			bufferGPU,
			bufferType,
			type,
			byteLength: array.byteLength,
			bytesPerElement: array.BYTES_PER_ELEMENT,
			version: attribute.version,
			pbo: attribute.pbo,
			isInteger: type === gl.INT || type === gl.UNSIGNED_INT || attribute.gpuType === IntType,
			id: _id ++
		};

		if ( attribute.isStorageBufferAttribute || attribute.isStorageInstancedBufferAttribute ) {

			// create buffer for transform feedback use
			const bufferGPUDual = this._createBuffer( gl, bufferType, array, usage );
			attributeData = new DualAttributeData( attributeData, bufferGPUDual );

		}

		backend.set( attribute, attributeData );

	}

	/**
	 * Updates the GPU buffer of the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
	updateAttribute( attribute ) {

		const backend = this.backend;
		const { gl } = backend;

		const array = attribute.array;
		const bufferAttribute = attribute.isInterleavedBufferAttribute ? attribute.data : attribute;
		const bufferData = backend.get( bufferAttribute );
		const bufferType = bufferData.bufferType;
		const updateRanges = attribute.isInterleavedBufferAttribute ? attribute.data.updateRanges : attribute.updateRanges;

		gl.bindBuffer( bufferType, bufferData.bufferGPU );

		if ( updateRanges.length === 0 ) {

			// Not using update ranges

			gl.bufferSubData( bufferType, 0, array );

		} else {

			for ( let i = 0, l = updateRanges.length; i < l; i ++ ) {

				const range = updateRanges[ i ];
				gl.bufferSubData( bufferType, range.start * array.BYTES_PER_ELEMENT,
					array, range.start, range.count );

			}

			bufferAttribute.clearUpdateRanges();

		}

		gl.bindBuffer( bufferType, null );

		bufferData.version = bufferAttribute.version;

	}

	/**
	 * Destroys the GPU buffer of the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 */
	destroyAttribute( attribute ) {

		const backend = this.backend;
		const { gl } = backend;

		if ( attribute.isInterleavedBufferAttribute ) {

			backend.delete( attribute.data );

		}

		const attributeData = backend.get( attribute );

		gl.deleteBuffer( attributeData.bufferGPU );

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
		const { gl } = backend;

		const bufferAttribute = attribute.isInterleavedBufferAttribute ? attribute.data : attribute;
		const { bufferGPU } = backend.get( bufferAttribute );

		const array = attribute.array;
		const byteLength = array.byteLength;

		gl.bindBuffer( gl.COPY_READ_BUFFER, bufferGPU );

		const writeBuffer = gl.createBuffer();

		gl.bindBuffer( gl.COPY_WRITE_BUFFER, writeBuffer );
		gl.bufferData( gl.COPY_WRITE_BUFFER, byteLength, gl.STREAM_READ );

		gl.copyBufferSubData( gl.COPY_READ_BUFFER, gl.COPY_WRITE_BUFFER, 0, 0, byteLength );

		await backend.utils._clientWaitAsync();

		const dstBuffer = new attribute.array.constructor( array.length );

		// Ensure the buffer is bound before reading
		gl.bindBuffer( gl.COPY_WRITE_BUFFER, writeBuffer );

		gl.getBufferSubData( gl.COPY_WRITE_BUFFER, 0, dstBuffer );

		gl.deleteBuffer( writeBuffer );

		gl.bindBuffer( gl.COPY_READ_BUFFER, null );
		gl.bindBuffer( gl.COPY_WRITE_BUFFER, null );

		return dstBuffer.buffer;

	}

	/**
	 * Creates a WebGL buffer with the given data.
	 *
	 * @private
	 * @param {WebGL2RenderingContext} gl - The rendering context.
	 * @param {GLenum } bufferType - A flag that indicates the buffer type and thus binding point target.
	 * @param {TypedArray} array - The array of the buffer attribute.
	 * @param {GLenum} usage - The usage.
	 * @return {WebGLBuffer} The WebGL buffer.
	 */
	_createBuffer( gl, bufferType, array, usage ) {

		const bufferGPU = gl.createBuffer();

		gl.bindBuffer( bufferType, bufferGPU );
		gl.bufferData( bufferType, array, usage );
		gl.bindBuffer( bufferType, null );

		return bufferGPU;

	}

}
```
</details>

#### Methods

##### `createAttribute(attribute: BufferAttribute, bufferType: number): void`

<details><summary>Code</summary>

```ts
createAttribute( attribute, bufferType ) {

		const backend = this.backend;
		const { gl } = backend;

		const array = attribute.array;
		const usage = attribute.usage || gl.STATIC_DRAW;

		const bufferAttribute = attribute.isInterleavedBufferAttribute ? attribute.data : attribute;
		const bufferData = backend.get( bufferAttribute );

		let bufferGPU = bufferData.bufferGPU;

		if ( bufferGPU === undefined ) {

			bufferGPU = this._createBuffer( gl, bufferType, array, usage );

			bufferData.bufferGPU = bufferGPU;
			bufferData.bufferType = bufferType;
			bufferData.version = bufferAttribute.version;

		}

		//attribute.onUploadCallback();

		let type;

		if ( array instanceof Float32Array ) {

			type = gl.FLOAT;

		} else if ( typeof Float16Array !== 'undefined' && array instanceof Float16Array ) {

			type = gl.HALF_FLOAT;

		} else if ( array instanceof Uint16Array ) {

			if ( attribute.isFloat16BufferAttribute ) {

				type = gl.HALF_FLOAT;

			} else {

				type = gl.UNSIGNED_SHORT;

			}

		} else if ( array instanceof Int16Array ) {

			type = gl.SHORT;

		} else if ( array instanceof Uint32Array ) {

			type = gl.UNSIGNED_INT;

		} else if ( array instanceof Int32Array ) {

			type = gl.INT;

		} else if ( array instanceof Int8Array ) {

			type = gl.BYTE;

		} else if ( array instanceof Uint8Array ) {

			type = gl.UNSIGNED_BYTE;

		} else if ( array instanceof Uint8ClampedArray ) {

			type = gl.UNSIGNED_BYTE;

		} else {

			throw new Error( 'THREE.WebGLBackend: Unsupported buffer data format: ' + array );

		}

		let attributeData = {
			bufferGPU,
			bufferType,
			type,
			byteLength: array.byteLength,
			bytesPerElement: array.BYTES_PER_ELEMENT,
			version: attribute.version,
			pbo: attribute.pbo,
			isInteger: type === gl.INT || type === gl.UNSIGNED_INT || attribute.gpuType === IntType,
			id: _id ++
		};

		if ( attribute.isStorageBufferAttribute || attribute.isStorageInstancedBufferAttribute ) {

			// create buffer for transform feedback use
			const bufferGPUDual = this._createBuffer( gl, bufferType, array, usage );
			attributeData = new DualAttributeData( attributeData, bufferGPUDual );

		}

		backend.set( attribute, attributeData );

	}
```
</details>

##### `updateAttribute(attribute: BufferAttribute): void`

<details><summary>Code</summary>

```ts
updateAttribute( attribute ) {

		const backend = this.backend;
		const { gl } = backend;

		const array = attribute.array;
		const bufferAttribute = attribute.isInterleavedBufferAttribute ? attribute.data : attribute;
		const bufferData = backend.get( bufferAttribute );
		const bufferType = bufferData.bufferType;
		const updateRanges = attribute.isInterleavedBufferAttribute ? attribute.data.updateRanges : attribute.updateRanges;

		gl.bindBuffer( bufferType, bufferData.bufferGPU );

		if ( updateRanges.length === 0 ) {

			// Not using update ranges

			gl.bufferSubData( bufferType, 0, array );

		} else {

			for ( let i = 0, l = updateRanges.length; i < l; i ++ ) {

				const range = updateRanges[ i ];
				gl.bufferSubData( bufferType, range.start * array.BYTES_PER_ELEMENT,
					array, range.start, range.count );

			}

			bufferAttribute.clearUpdateRanges();

		}

		gl.bindBuffer( bufferType, null );

		bufferData.version = bufferAttribute.version;

	}
```
</details>

##### `destroyAttribute(attribute: BufferAttribute): void`

<details><summary>Code</summary>

```ts
destroyAttribute( attribute ) {

		const backend = this.backend;
		const { gl } = backend;

		if ( attribute.isInterleavedBufferAttribute ) {

			backend.delete( attribute.data );

		}

		const attributeData = backend.get( attribute );

		gl.deleteBuffer( attributeData.bufferGPU );

		backend.delete( attribute );

	}
```
</details>

##### `getArrayBufferAsync(attribute: StorageBufferAttribute): Promise<ArrayBuffer>`

<details><summary>Code</summary>

```ts
async getArrayBufferAsync( attribute ) {

		const backend = this.backend;
		const { gl } = backend;

		const bufferAttribute = attribute.isInterleavedBufferAttribute ? attribute.data : attribute;
		const { bufferGPU } = backend.get( bufferAttribute );

		const array = attribute.array;
		const byteLength = array.byteLength;

		gl.bindBuffer( gl.COPY_READ_BUFFER, bufferGPU );

		const writeBuffer = gl.createBuffer();

		gl.bindBuffer( gl.COPY_WRITE_BUFFER, writeBuffer );
		gl.bufferData( gl.COPY_WRITE_BUFFER, byteLength, gl.STREAM_READ );

		gl.copyBufferSubData( gl.COPY_READ_BUFFER, gl.COPY_WRITE_BUFFER, 0, 0, byteLength );

		await backend.utils._clientWaitAsync();

		const dstBuffer = new attribute.array.constructor( array.length );

		// Ensure the buffer is bound before reading
		gl.bindBuffer( gl.COPY_WRITE_BUFFER, writeBuffer );

		gl.getBufferSubData( gl.COPY_WRITE_BUFFER, 0, dstBuffer );

		gl.deleteBuffer( writeBuffer );

		gl.bindBuffer( gl.COPY_READ_BUFFER, null );
		gl.bindBuffer( gl.COPY_WRITE_BUFFER, null );

		return dstBuffer.buffer;

	}
```
</details>

##### `_createBuffer(gl: WebGL2RenderingContext, bufferType: number, array: TypedArray, usage: number): WebGLBuffer`

<details><summary>Code</summary>

```ts
_createBuffer( gl, bufferType, array, usage ) {

		const bufferGPU = gl.createBuffer();

		gl.bindBuffer( bufferType, bufferGPU );
		gl.bufferData( bufferType, array, usage );
		gl.bindBuffer( bufferType, null );

		return bufferGPU;

	}
```
</details>


---