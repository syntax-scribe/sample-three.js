[⬅️ Back to Table of Contents](../../index.md)

# 📄 `GLBufferAttribute.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |

## 📚 Table of Contents

- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/core/GLBufferAttribute.js`**

## Functions

### `GLBufferAttribute.setBuffer(buffer: WebGLBuffer): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the given native WebGL buffer.
	 *
	 * @param {WebGLBuffer} buffer - The buffer to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`buffer`** `WebGLBuffer`

**Returns:** `BufferAttribute`

<details><summary>Code</summary>

```typescript
setBuffer( buffer ) {

		this.buffer = buffer;

		return this;

	}
```
</details>

### `GLBufferAttribute.setType(type: number, elementSize: number): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the given native data type and element size.
	 *
	 * @param {number} type - The native data type (e.g. `gl.FLOAT`).
	 * @param {number} elementSize - The corresponding size (in bytes) for the given `type` parameter.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`type`** `number`
- **`elementSize`** `number`

**Returns:** `BufferAttribute`

<details><summary>Code</summary>

```typescript
setType( type, elementSize ) {

		this.type = type;
		this.elementSize = elementSize;

		return this;

	}
```
</details>

### `GLBufferAttribute.setItemSize(itemSize: number): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the item size.
	 *
	 * @param {number} itemSize - The item size.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`itemSize`** `number`

**Returns:** `BufferAttribute`

<details><summary>Code</summary>

```typescript
setItemSize( itemSize ) {

		this.itemSize = itemSize;

		return this;

	}
```
</details>

### `GLBufferAttribute.setCount(count: number): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the count (the expected number of vertices in VBO).
	 *
	 * @param {number} count - The count.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`count`** `number`

**Returns:** `BufferAttribute`

<details><summary>Code</summary>

```typescript
setCount( count ) {

		this.count = count;

		return this;

	}
```
</details>


---

## Classes

### `GLBufferAttribute`

<details><summary>Class Code</summary>

```ts
class GLBufferAttribute {

	/**
	 * Constructs a new GL buffer attribute.
	 *
	 * @param {WebGLBuffer} buffer - The native WebGL buffer.
	 * @param {number} type - The native data type (e.g. `gl.FLOAT`).
	 * @param {number} itemSize - The item size.
	 * @param {number} elementSize - The corresponding size (in bytes) for the given `type` parameter.
	 * @param {number} count - The expected number of vertices in VBO.
	 * @param {boolean} [normalized=false] - Whether the data are normalized or not.
	 */
	constructor( buffer, type, itemSize, elementSize, count, normalized = false ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isGLBufferAttribute = true;

		/**
		 * The name of the buffer attribute.
		 *
		 * @type {string}
		 */
		this.name = '';

		/**
		 * The native WebGL buffer.
		 *
		 * @type {WebGLBuffer}
		 */
		this.buffer = buffer;

		/**
		 * The native data type.
		 *
		 * @type {number}
		 */
		this.type = type;

		/**
		 * The item size, see {@link BufferAttribute#itemSize}.
		 *
		 * @type {number}
		 */
		this.itemSize = itemSize;

		/**
		 * The corresponding size (in bytes) for the given `type` parameter.
		 *
		 * @type {number}
		 */
		this.elementSize = elementSize;

		/**
		 * The expected number of vertices in VBO.
		 *
		 * @type {number}
		 */
		this.count = count;

		/**
		 * Applies to integer data only. Indicates how the underlying data in the buffer maps to
		 * the values in the GLSL code. For instance, if `buffer` contains data of `gl.UNSIGNED_SHORT`,
		 * and `normalized` is `true`, the values `0 - +65535` in the buffer data will be mapped to
		 * `0.0f - +1.0f` in the GLSL attribute. If `normalized` is `false`, the values will be converted
		 * to floats unmodified, i.e. `65535` becomes `65535.0f`.
		 *
		 * @type {boolean}
		 */
		this.normalized = normalized;

		/**
		 * A version number, incremented every time the `needsUpdate` is set to `true`.
		 *
		 * @type {number}
		 */
		this.version = 0;

	}

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
	 * Sets the given native WebGL buffer.
	 *
	 * @param {WebGLBuffer} buffer - The buffer to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	setBuffer( buffer ) {

		this.buffer = buffer;

		return this;

	}

	/**
	 * Sets the given native data type and element size.
	 *
	 * @param {number} type - The native data type (e.g. `gl.FLOAT`).
	 * @param {number} elementSize - The corresponding size (in bytes) for the given `type` parameter.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	setType( type, elementSize ) {

		this.type = type;
		this.elementSize = elementSize;

		return this;

	}

	/**
	 * Sets the item size.
	 *
	 * @param {number} itemSize - The item size.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	setItemSize( itemSize ) {

		this.itemSize = itemSize;

		return this;

	}

	/**
	 * Sets the count (the expected number of vertices in VBO).
	 *
	 * @param {number} count - The count.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	setCount( count ) {

		this.count = count;

		return this;

	}

}
```
</details>

#### Methods

##### `setBuffer(buffer: WebGLBuffer): BufferAttribute`

<details><summary>Code</summary>

```ts
setBuffer( buffer ) {

		this.buffer = buffer;

		return this;

	}
```
</details>

##### `setType(type: number, elementSize: number): BufferAttribute`

<details><summary>Code</summary>

```ts
setType( type, elementSize ) {

		this.type = type;
		this.elementSize = elementSize;

		return this;

	}
```
</details>

##### `setItemSize(itemSize: number): BufferAttribute`

<details><summary>Code</summary>

```ts
setItemSize( itemSize ) {

		this.itemSize = itemSize;

		return this;

	}
```
</details>

##### `setCount(count: number): BufferAttribute`

<details><summary>Code</summary>

```ts
setCount( count ) {

		this.count = count;

		return this;

	}
```
</details>


---