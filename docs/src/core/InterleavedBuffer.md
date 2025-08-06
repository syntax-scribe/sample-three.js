[⬅️ Back to Table of Contents](../../index.md)

# 📄 `InterleavedBuffer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/core/InterleavedBuffer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `generateUUID` | `../math/MathUtils.js` |
| `StaticDrawUsage` | `../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `array` | `any` | let/var | `new this.array.constructor( data.arrayBuffers[ this.array.buffer._uuid ] )` | ✗ |
| `ib` | `any` | let/var | `new this.constructor( array, this.stride )` | ✗ |


---

## Functions

### `InterleavedBuffer.onUploadCallback(): void`

**JSDoc:**
```typescript
/**
	 * A callback function that is executed after the renderer has transferred the attribute array
	 * data to the GPU.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
onUploadCallback() {}
```
</details>

### `InterleavedBuffer.setUsage(value: any): InterleavedBuffer`

**JSDoc:**
```typescript
/**
	 * Sets the usage of this interleaved buffer.
	 *
	 * @param {(StaticDrawUsage|DynamicDrawUsage|StreamDrawUsage|StaticReadUsage|DynamicReadUsage|StreamReadUsage|StaticCopyUsage|DynamicCopyUsage|StreamCopyUsage)} value - The usage to set.
	 * @return {InterleavedBuffer} A reference to this interleaved buffer.
	 */
```

**Parameters:**

- **`value`** `any`

**Returns:** `InterleavedBuffer`

<details><summary>Code</summary>

```typescript
setUsage( value ) {

		this.usage = value;

		return this;

	}
```
</details>

### `InterleavedBuffer.addUpdateRange(start: number, count: number): void`

**JSDoc:**
```typescript
/**
	 * Adds a range of data in the data array to be updated on the GPU.
	 *
	 * @param {number} start - Position at which to start update.
	 * @param {number} count - The number of components to update.
	 */
```

**Parameters:**

- **`start`** `number`
- **`count`** `number`

**Returns:** `void`

**Calls:**

- `this.updateRanges.push`

<details><summary>Code</summary>

```typescript
addUpdateRange( start, count ) {

		this.updateRanges.push( { start, count } );

	}
```
</details>

### `InterleavedBuffer.clearUpdateRanges(): void`

**JSDoc:**
```typescript
/**
	 * Clears the update ranges.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
clearUpdateRanges() {

		this.updateRanges.length = 0;

	}
```
</details>

### `InterleavedBuffer.copy(source: InterleavedBuffer): InterleavedBuffer`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given interleaved buffer to this instance.
	 *
	 * @param {InterleavedBuffer} source - The interleaved buffer to copy.
	 * @return {InterleavedBuffer} A reference to this instance.
	 */
```

**Parameters:**

- **`source`** `InterleavedBuffer`

**Returns:** `InterleavedBuffer`

<details><summary>Code</summary>

```typescript
copy( source ) {

		this.array = new source.array.constructor( source.array );
		this.count = source.count;
		this.stride = source.stride;
		this.usage = source.usage;

		return this;

	}
```
</details>

### `InterleavedBuffer.copyAt(index1: number, interleavedBuffer: InterleavedBuffer, index2: number): InterleavedBuffer`

**JSDoc:**
```typescript
/**
	 * Copies a vector from the given interleaved buffer to this one. The start
	 * and destination position in the attribute buffers are represented by the
	 * given indices.
	 *
	 * @param {number} index1 - The destination index into this interleaved buffer.
	 * @param {InterleavedBuffer} interleavedBuffer - The interleaved buffer to copy from.
	 * @param {number} index2 - The source index into the given interleaved buffer.
	 * @return {InterleavedBuffer} A reference to this instance.
	 */
```

**Parameters:**

- **`index1`** `number`
- **`interleavedBuffer`** `InterleavedBuffer`
- **`index2`** `number`

**Returns:** `InterleavedBuffer`

<details><summary>Code</summary>

```typescript
copyAt( index1, interleavedBuffer, index2 ) {

		index1 *= this.stride;
		index2 *= interleavedBuffer.stride;

		for ( let i = 0, l = this.stride; i < l; i ++ ) {

			this.array[ index1 + i ] = interleavedBuffer.array[ index2 + i ];

		}

		return this;

	}
```
</details>

### `InterleavedBuffer.set(value: any, offset: number): InterleavedBuffer`

**JSDoc:**
```typescript
/**
	 * Sets the given array data in the interleaved buffer.
	 *
	 * @param {(TypedArray|Array)} value - The array data to set.
	 * @param {number} [offset=0] - The offset in this interleaved buffer's array.
	 * @return {InterleavedBuffer} A reference to this instance.
	 */
```

**Parameters:**

- **`value`** `any`
- **`offset`** `number`

**Returns:** `InterleavedBuffer`

**Calls:**

- `this.array.set`

<details><summary>Code</summary>

```typescript
set( value, offset = 0 ) {

		this.array.set( value, offset );

		return this;

	}
```
</details>

### `InterleavedBuffer.clone(data: any): InterleavedBuffer`

**JSDoc:**
```typescript
/**
	 * Returns a new interleaved buffer with copied values from this instance.
	 *
	 * @param {Object} [data] - An object with shared array buffers that allows to retain shared structures.
	 * @return {InterleavedBuffer} A clone of this instance.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `InterleavedBuffer`

**Calls:**

- `generateUUID (from ../math/MathUtils.js)`
- `this.array.slice`
- `ib.setUsage`

<details><summary>Code</summary>

```typescript
clone( data ) {

		if ( data.arrayBuffers === undefined ) {

			data.arrayBuffers = {};

		}

		if ( this.array.buffer._uuid === undefined ) {

			this.array.buffer._uuid = generateUUID();

		}

		if ( data.arrayBuffers[ this.array.buffer._uuid ] === undefined ) {

			data.arrayBuffers[ this.array.buffer._uuid ] = this.array.slice( 0 ).buffer;

		}

		const array = new this.array.constructor( data.arrayBuffers[ this.array.buffer._uuid ] );

		const ib = new this.constructor( array, this.stride );
		ib.setUsage( this.usage );

		return ib;

	}
```
</details>

### `InterleavedBuffer.onUpload(callback: Function): InterleavedBuffer`

**JSDoc:**
```typescript
/**
	 * Sets the given callback function that is executed after the Renderer has transferred
	 * the array data to the GPU. Can be used to perform clean-up operations after
	 * the upload when data are not needed anymore on the CPU side.
	 *
	 * @param {Function} callback - The `onUpload()` callback.
	 * @return {InterleavedBuffer} A reference to this instance.
	 */
```

**Parameters:**

- **`callback`** `Function`

**Returns:** `InterleavedBuffer`

<details><summary>Code</summary>

```typescript
onUpload( callback ) {

		this.onUploadCallback = callback;

		return this;

	}
```
</details>

### `InterleavedBuffer.toJSON(data: any): any`

**JSDoc:**
```typescript
/**
	 * Serializes the interleaved buffer into JSON.
	 *
	 * @param {Object} [data] - An optional value holding meta information about the serialization.
	 * @return {Object} A JSON object representing the serialized interleaved buffer.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `generateUUID (from ../math/MathUtils.js)`
- `Array.from`

**Internal Comments:**
```
// generate UUID for array buffer if necessary
//
```

<details><summary>Code</summary>

```typescript
toJSON( data ) {

		if ( data.arrayBuffers === undefined ) {

			data.arrayBuffers = {};

		}

		// generate UUID for array buffer if necessary

		if ( this.array.buffer._uuid === undefined ) {

			this.array.buffer._uuid = generateUUID();

		}

		if ( data.arrayBuffers[ this.array.buffer._uuid ] === undefined ) {

			data.arrayBuffers[ this.array.buffer._uuid ] = Array.from( new Uint32Array( this.array.buffer ) );

		}

		//

		return {
			uuid: this.uuid,
			buffer: this.array.buffer._uuid,
			type: this.array.constructor.name,
			stride: this.stride
		};

	}
```
</details>


---

## Classes

### `InterleavedBuffer`

<details><summary>Class Code</summary>

```ts
class InterleavedBuffer {

	/**
	 * Constructs a new interleaved buffer.
	 *
	 * @param {TypedArray} array - A typed array with a shared buffer storing attribute data.
	 * @param {number} stride - The number of typed-array elements per vertex.
	 */
	constructor( array, stride ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isInterleavedBuffer = true;

		/**
		 * A typed array with a shared buffer storing attribute data.
		 *
		 * @type {TypedArray}
		 */
		this.array = array;

		/**
		 * The number of typed-array elements per vertex.
		 *
		 * @type {number}
		 */
		this.stride = stride;

		/**
		 * The total number of elements in the array
		 *
		 * @type {number}
		 * @readonly
		 */
		this.count = array !== undefined ? array.length / stride : 0;

		/**
		 * Defines the intended usage pattern of the data store for optimization purposes.
		 *
		 * Note: After the initial use of a buffer, its usage cannot be changed. Instead,
		 * instantiate a new one and set the desired usage before the next render.
		 *
		 * @type {(StaticDrawUsage|DynamicDrawUsage|StreamDrawUsage|StaticReadUsage|DynamicReadUsage|StreamReadUsage|StaticCopyUsage|DynamicCopyUsage|StreamCopyUsage)}
		 * @default StaticDrawUsage
		 */
		this.usage = StaticDrawUsage;

		/**
		 * This can be used to only update some components of stored vectors (for example, just the
		 * component related to color). Use the `addUpdateRange()` function to add ranges to this array.
		 *
		 * @type {Array<Object>}
		 */
		this.updateRanges = [];

		/**
		 * A version number, incremented every time the `needsUpdate` is set to `true`.
		 *
		 * @type {number}
		 */
		this.version = 0;

		/**
		 * The UUID of the interleaved buffer.
		 *
		 * @type {string}
		 * @readonly
		 */
		this.uuid = generateUUID();

	}

	/**
	 * A callback function that is executed after the renderer has transferred the attribute array
	 * data to the GPU.
	 */
	onUploadCallback() {}

	/**
	 * Flag to indicate that this attribute has changed and should be re-sent to
	 * the GPU. Set this to `true` when you modify the value of the array.
	 *
	 * @type {number}
	 * @default false
	 * @param {boolean} value
	 */
	set needsUpdate( value ) {

		if ( value === true ) this.version ++;

	}

	/**
	 * Sets the usage of this interleaved buffer.
	 *
	 * @param {(StaticDrawUsage|DynamicDrawUsage|StreamDrawUsage|StaticReadUsage|DynamicReadUsage|StreamReadUsage|StaticCopyUsage|DynamicCopyUsage|StreamCopyUsage)} value - The usage to set.
	 * @return {InterleavedBuffer} A reference to this interleaved buffer.
	 */
	setUsage( value ) {

		this.usage = value;

		return this;

	}

	/**
	 * Adds a range of data in the data array to be updated on the GPU.
	 *
	 * @param {number} start - Position at which to start update.
	 * @param {number} count - The number of components to update.
	 */
	addUpdateRange( start, count ) {

		this.updateRanges.push( { start, count } );

	}

	/**
	 * Clears the update ranges.
	 */
	clearUpdateRanges() {

		this.updateRanges.length = 0;

	}

	/**
	 * Copies the values of the given interleaved buffer to this instance.
	 *
	 * @param {InterleavedBuffer} source - The interleaved buffer to copy.
	 * @return {InterleavedBuffer} A reference to this instance.
	 */
	copy( source ) {

		this.array = new source.array.constructor( source.array );
		this.count = source.count;
		this.stride = source.stride;
		this.usage = source.usage;

		return this;

	}

	/**
	 * Copies a vector from the given interleaved buffer to this one. The start
	 * and destination position in the attribute buffers are represented by the
	 * given indices.
	 *
	 * @param {number} index1 - The destination index into this interleaved buffer.
	 * @param {InterleavedBuffer} interleavedBuffer - The interleaved buffer to copy from.
	 * @param {number} index2 - The source index into the given interleaved buffer.
	 * @return {InterleavedBuffer} A reference to this instance.
	 */
	copyAt( index1, interleavedBuffer, index2 ) {

		index1 *= this.stride;
		index2 *= interleavedBuffer.stride;

		for ( let i = 0, l = this.stride; i < l; i ++ ) {

			this.array[ index1 + i ] = interleavedBuffer.array[ index2 + i ];

		}

		return this;

	}

	/**
	 * Sets the given array data in the interleaved buffer.
	 *
	 * @param {(TypedArray|Array)} value - The array data to set.
	 * @param {number} [offset=0] - The offset in this interleaved buffer's array.
	 * @return {InterleavedBuffer} A reference to this instance.
	 */
	set( value, offset = 0 ) {

		this.array.set( value, offset );

		return this;

	}

	/**
	 * Returns a new interleaved buffer with copied values from this instance.
	 *
	 * @param {Object} [data] - An object with shared array buffers that allows to retain shared structures.
	 * @return {InterleavedBuffer} A clone of this instance.
	 */
	clone( data ) {

		if ( data.arrayBuffers === undefined ) {

			data.arrayBuffers = {};

		}

		if ( this.array.buffer._uuid === undefined ) {

			this.array.buffer._uuid = generateUUID();

		}

		if ( data.arrayBuffers[ this.array.buffer._uuid ] === undefined ) {

			data.arrayBuffers[ this.array.buffer._uuid ] = this.array.slice( 0 ).buffer;

		}

		const array = new this.array.constructor( data.arrayBuffers[ this.array.buffer._uuid ] );

		const ib = new this.constructor( array, this.stride );
		ib.setUsage( this.usage );

		return ib;

	}

	/**
	 * Sets the given callback function that is executed after the Renderer has transferred
	 * the array data to the GPU. Can be used to perform clean-up operations after
	 * the upload when data are not needed anymore on the CPU side.
	 *
	 * @param {Function} callback - The `onUpload()` callback.
	 * @return {InterleavedBuffer} A reference to this instance.
	 */
	onUpload( callback ) {

		this.onUploadCallback = callback;

		return this;

	}

	/**
	 * Serializes the interleaved buffer into JSON.
	 *
	 * @param {Object} [data] - An optional value holding meta information about the serialization.
	 * @return {Object} A JSON object representing the serialized interleaved buffer.
	 */
	toJSON( data ) {

		if ( data.arrayBuffers === undefined ) {

			data.arrayBuffers = {};

		}

		// generate UUID for array buffer if necessary

		if ( this.array.buffer._uuid === undefined ) {

			this.array.buffer._uuid = generateUUID();

		}

		if ( data.arrayBuffers[ this.array.buffer._uuid ] === undefined ) {

			data.arrayBuffers[ this.array.buffer._uuid ] = Array.from( new Uint32Array( this.array.buffer ) );

		}

		//

		return {
			uuid: this.uuid,
			buffer: this.array.buffer._uuid,
			type: this.array.constructor.name,
			stride: this.stride
		};

	}

}
```
</details>

#### Methods

##### `onUploadCallback(): void`

<details><summary>Code</summary>

```ts
onUploadCallback() {}
```
</details>

##### `setUsage(value: any): InterleavedBuffer`

<details><summary>Code</summary>

```ts
setUsage( value ) {

		this.usage = value;

		return this;

	}
```
</details>

##### `addUpdateRange(start: number, count: number): void`

<details><summary>Code</summary>

```ts
addUpdateRange( start, count ) {

		this.updateRanges.push( { start, count } );

	}
```
</details>

##### `clearUpdateRanges(): void`

<details><summary>Code</summary>

```ts
clearUpdateRanges() {

		this.updateRanges.length = 0;

	}
```
</details>

##### `copy(source: InterleavedBuffer): InterleavedBuffer`

<details><summary>Code</summary>

```ts
copy( source ) {

		this.array = new source.array.constructor( source.array );
		this.count = source.count;
		this.stride = source.stride;
		this.usage = source.usage;

		return this;

	}
```
</details>

##### `copyAt(index1: number, interleavedBuffer: InterleavedBuffer, index2: number): InterleavedBuffer`

<details><summary>Code</summary>

```ts
copyAt( index1, interleavedBuffer, index2 ) {

		index1 *= this.stride;
		index2 *= interleavedBuffer.stride;

		for ( let i = 0, l = this.stride; i < l; i ++ ) {

			this.array[ index1 + i ] = interleavedBuffer.array[ index2 + i ];

		}

		return this;

	}
```
</details>

##### `set(value: any, offset: number): InterleavedBuffer`

<details><summary>Code</summary>

```ts
set( value, offset = 0 ) {

		this.array.set( value, offset );

		return this;

	}
```
</details>

##### `clone(data: any): InterleavedBuffer`

<details><summary>Code</summary>

```ts
clone( data ) {

		if ( data.arrayBuffers === undefined ) {

			data.arrayBuffers = {};

		}

		if ( this.array.buffer._uuid === undefined ) {

			this.array.buffer._uuid = generateUUID();

		}

		if ( data.arrayBuffers[ this.array.buffer._uuid ] === undefined ) {

			data.arrayBuffers[ this.array.buffer._uuid ] = this.array.slice( 0 ).buffer;

		}

		const array = new this.array.constructor( data.arrayBuffers[ this.array.buffer._uuid ] );

		const ib = new this.constructor( array, this.stride );
		ib.setUsage( this.usage );

		return ib;

	}
```
</details>

##### `onUpload(callback: Function): InterleavedBuffer`

<details><summary>Code</summary>

```ts
onUpload( callback ) {

		this.onUploadCallback = callback;

		return this;

	}
```
</details>

##### `toJSON(data: any): any`

<details><summary>Code</summary>

```ts
toJSON( data ) {

		if ( data.arrayBuffers === undefined ) {

			data.arrayBuffers = {};

		}

		// generate UUID for array buffer if necessary

		if ( this.array.buffer._uuid === undefined ) {

			this.array.buffer._uuid = generateUUID();

		}

		if ( data.arrayBuffers[ this.array.buffer._uuid ] === undefined ) {

			data.arrayBuffers[ this.array.buffer._uuid ] = Array.from( new Uint32Array( this.array.buffer ) );

		}

		//

		return {
			uuid: this.uuid,
			buffer: this.array.buffer._uuid,
			type: this.array.constructor.name,
			stride: this.stride
		};

	}
```
</details>


---