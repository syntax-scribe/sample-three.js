[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLAttributes.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLAttributes.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `buffers` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `array` | `any` | let/var | `attribute.array` | ✗ |
| `usage` | `any` | let/var | `attribute.usage` | ✗ |
| `size` | `any` | let/var | `array.byteLength` | ✗ |
| `type` | `any` | let/var | `*not shown*` | ✗ |
| `array` | `any` | let/var | `attribute.array` | ✗ |
| `updateRanges` | `any` | let/var | `attribute.updateRanges` | ✗ |
| `mergeIndex` | `number` | let/var | `0` | ✗ |
| `previousRange` | `any` | let/var | `updateRanges[ mergeIndex ]` | ✗ |
| `range` | `any` | let/var | `updateRanges[ i ]` | ✗ |
| `range` | `any` | let/var | `updateRanges[ i ]` | ✗ |


---

## Functions

### `WebGLAttributes(gl: any): { get: (attribute: any) => any; remove: (attribute: any) => void; update: (attribute: any, bufferType: any) => void; }`

**Parameters:**

- **`gl`** `any`

**Returns:** `{ get: (attribute: any) => any; remove: (attribute: any) => void; update: (attribute: any, bufferType: any) => void; }`

**Calls:**

- `gl.createBuffer`
- `gl.bindBuffer`
- `gl.bufferData`
- `attribute.onUploadCallback`
- `gl.bufferSubData`
- `updateRanges.sort`
- `Math.max`
- `attribute.clearUpdateRanges`
- `buffers.get`
- `gl.deleteBuffer`
- `buffers.delete`
- `buffers.set`
- `createBuffer`
- `updateBuffer`

**Internal Comments:**
```
// Not using update ranges (x4)
// Before applying update ranges, we merge any adjacent / overlapping (x4)
// ranges to reduce load on `gl.bufferSubData`. Empirically, this has led (x4)
// to performance improvements for applications which make heavy use of (x4)
// update ranges. Likely due to GPU command overhead. (x4)
// (x5)
// Note that to reduce garbage collection between frames, we merge the (x4)
// update ranges in-place. This is safe because this method will clear the (x4)
// update ranges once updated. (x4)
// To merge the update ranges in-place, we work from left to right in the (x2)
// existing updateRanges array, merging ranges. This may result in a final (x2)
// array which is smaller than the original. This index tracks the last (x2)
// index representing a merged range, any data after this index can be (x2)
// trimmed once the merge algorithm is completed. (x2)
// We add one here to merge adjacent ranges. This is safe because ranges
// operate over positive integers.
// Trim the array to only contain the merged ranges. (x4)
```

<details><summary>Code</summary>

```typescript
function WebGLAttributes( gl ) {

	const buffers = new WeakMap();

	function createBuffer( attribute, bufferType ) {

		const array = attribute.array;
		const usage = attribute.usage;
		const size = array.byteLength;

		const buffer = gl.createBuffer();

		gl.bindBuffer( bufferType, buffer );
		gl.bufferData( bufferType, array, usage );

		attribute.onUploadCallback();

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

			throw new Error( 'THREE.WebGLAttributes: Unsupported buffer data format: ' + array );

		}

		return {
			buffer: buffer,
			type: type,
			bytesPerElement: array.BYTES_PER_ELEMENT,
			version: attribute.version,
			size: size
		};

	}

	function updateBuffer( buffer, attribute, bufferType ) {

		const array = attribute.array;
		const updateRanges = attribute.updateRanges;

		gl.bindBuffer( bufferType, buffer );

		if ( updateRanges.length === 0 ) {

			// Not using update ranges
			gl.bufferSubData( bufferType, 0, array );

		} else {

			// Before applying update ranges, we merge any adjacent / overlapping
			// ranges to reduce load on `gl.bufferSubData`. Empirically, this has led
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

				// We add one here to merge adjacent ranges. This is safe because ranges
				// operate over positive integers.
				if ( range.start <= previousRange.start + previousRange.count + 1 ) {

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

			for ( let i = 0, l = updateRanges.length; i < l; i ++ ) {

				const range = updateRanges[ i ];

				gl.bufferSubData( bufferType, range.start * array.BYTES_PER_ELEMENT,
					array, range.start, range.count );

			}

			attribute.clearUpdateRanges();

		}

		attribute.onUploadCallback();

	}

	//

	function get( attribute ) {

		if ( attribute.isInterleavedBufferAttribute ) attribute = attribute.data;

		return buffers.get( attribute );

	}

	function remove( attribute ) {

		if ( attribute.isInterleavedBufferAttribute ) attribute = attribute.data;

		const data = buffers.get( attribute );

		if ( data ) {

			gl.deleteBuffer( data.buffer );

			buffers.delete( attribute );

		}

	}

	function update( attribute, bufferType ) {

		if ( attribute.isInterleavedBufferAttribute ) attribute = attribute.data;

		if ( attribute.isGLBufferAttribute ) {

			const cached = buffers.get( attribute );

			if ( ! cached || cached.version < attribute.version ) {

				buffers.set( attribute, {
					buffer: attribute.buffer,
					type: attribute.type,
					bytesPerElement: attribute.elementSize,
					version: attribute.version
				} );

			}

			return;

		}

		const data = buffers.get( attribute );

		if ( data === undefined ) {

			buffers.set( attribute, createBuffer( attribute, bufferType ) );

		} else if ( data.version < attribute.version ) {

			if ( data.size !== attribute.array.byteLength ) {

				throw new Error( 'THREE.WebGLAttributes: The size of the buffer attribute\'s array buffer does not match the original size. Resizing buffer attributes is not supported.' );

			}

			updateBuffer( data.buffer, attribute, bufferType );

			data.version = attribute.version;

		}

	}

	return {

		get: get,
		remove: remove,
		update: update

	};

}
```
</details>

### `createBuffer(attribute: any, bufferType: any): { buffer: any; type: any; bytesPerElement: number; version: any; size: any; }`

**Parameters:**

- **`attribute`** `any`
- **`bufferType`** `any`

**Returns:** `{ buffer: any; type: any; bytesPerElement: number; version: any; size: any; }`

**Calls:**

- `gl.createBuffer`
- `gl.bindBuffer`
- `gl.bufferData`
- `attribute.onUploadCallback`

<details><summary>Code</summary>

```typescript
function createBuffer( attribute, bufferType ) {

		const array = attribute.array;
		const usage = attribute.usage;
		const size = array.byteLength;

		const buffer = gl.createBuffer();

		gl.bindBuffer( bufferType, buffer );
		gl.bufferData( bufferType, array, usage );

		attribute.onUploadCallback();

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

			throw new Error( 'THREE.WebGLAttributes: Unsupported buffer data format: ' + array );

		}

		return {
			buffer: buffer,
			type: type,
			bytesPerElement: array.BYTES_PER_ELEMENT,
			version: attribute.version,
			size: size
		};

	}
```
</details>

### `updateBuffer(buffer: any, attribute: any, bufferType: any): void`

**Parameters:**

- **`buffer`** `any`
- **`attribute`** `any`
- **`bufferType`** `any`

**Returns:** `void`

**Calls:**

- `gl.bindBuffer`
- `gl.bufferSubData`
- `updateRanges.sort`
- `Math.max`
- `attribute.clearUpdateRanges`
- `attribute.onUploadCallback`

**Internal Comments:**
```
// Not using update ranges (x4)
// Before applying update ranges, we merge any adjacent / overlapping (x4)
// ranges to reduce load on `gl.bufferSubData`. Empirically, this has led (x4)
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
// We add one here to merge adjacent ranges. This is safe because ranges
// operate over positive integers.
// Trim the array to only contain the merged ranges. (x4)
```

<details><summary>Code</summary>

```typescript
function updateBuffer( buffer, attribute, bufferType ) {

		const array = attribute.array;
		const updateRanges = attribute.updateRanges;

		gl.bindBuffer( bufferType, buffer );

		if ( updateRanges.length === 0 ) {

			// Not using update ranges
			gl.bufferSubData( bufferType, 0, array );

		} else {

			// Before applying update ranges, we merge any adjacent / overlapping
			// ranges to reduce load on `gl.bufferSubData`. Empirically, this has led
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

				// We add one here to merge adjacent ranges. This is safe because ranges
				// operate over positive integers.
				if ( range.start <= previousRange.start + previousRange.count + 1 ) {

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

			for ( let i = 0, l = updateRanges.length; i < l; i ++ ) {

				const range = updateRanges[ i ];

				gl.bufferSubData( bufferType, range.start * array.BYTES_PER_ELEMENT,
					array, range.start, range.count );

			}

			attribute.clearUpdateRanges();

		}

		attribute.onUploadCallback();

	}
```
</details>

### `get(attribute: any): any`

**Parameters:**

- **`attribute`** `any`

**Returns:** `any`

**Calls:**

- `buffers.get`

<details><summary>Code</summary>

```typescript
function get( attribute ) {

		if ( attribute.isInterleavedBufferAttribute ) attribute = attribute.data;

		return buffers.get( attribute );

	}
```
</details>

### `remove(attribute: any): void`

**Parameters:**

- **`attribute`** `any`

**Returns:** `void`

**Calls:**

- `buffers.get`
- `gl.deleteBuffer`
- `buffers.delete`

<details><summary>Code</summary>

```typescript
function remove( attribute ) {

		if ( attribute.isInterleavedBufferAttribute ) attribute = attribute.data;

		const data = buffers.get( attribute );

		if ( data ) {

			gl.deleteBuffer( data.buffer );

			buffers.delete( attribute );

		}

	}
```
</details>

### `update(attribute: any, bufferType: any): void`

**Parameters:**

- **`attribute`** `any`
- **`bufferType`** `any`

**Returns:** `void`

**Calls:**

- `buffers.get`
- `buffers.set`
- `createBuffer`
- `updateBuffer`

<details><summary>Code</summary>

```typescript
function update( attribute, bufferType ) {

		if ( attribute.isInterleavedBufferAttribute ) attribute = attribute.data;

		if ( attribute.isGLBufferAttribute ) {

			const cached = buffers.get( attribute );

			if ( ! cached || cached.version < attribute.version ) {

				buffers.set( attribute, {
					buffer: attribute.buffer,
					type: attribute.type,
					bytesPerElement: attribute.elementSize,
					version: attribute.version
				} );

			}

			return;

		}

		const data = buffers.get( attribute );

		if ( data === undefined ) {

			buffers.set( attribute, createBuffer( attribute, bufferType ) );

		} else if ( data.version < attribute.version ) {

			if ( data.size !== attribute.array.byteLength ) {

				throw new Error( 'THREE.WebGLAttributes: The size of the buffer attribute\'s array buffer does not match the original size. Resizing buffer attributes is not supported.' );

			}

			updateBuffer( data.buffer, attribute, bufferType );

			data.version = attribute.version;

		}

	}
```
</details>


---