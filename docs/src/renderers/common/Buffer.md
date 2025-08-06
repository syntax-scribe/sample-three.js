[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Buffer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/Buffer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Binding` | `./Binding.js` |
| `getFloatLength` | `./BufferUtils.js` |


---

## Functions

### `Buffer.update(): boolean`

**JSDoc:**
```typescript
/**
	 * Updates the binding.
	 *
	 * @return {boolean} Whether the buffer has been updated and must be
	 * uploaded to the GPU.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
update() {

		return true;

	}
```
</details>


---

## Classes

### `Buffer`

<details><summary>Class Code</summary>

```ts
class Buffer extends Binding {

	/**
	 * Constructs a new buffer.
	 *
	 * @param {string} name - The buffer's name.
	 * @param {TypedArray} [buffer=null] - The buffer.
	 */
	constructor( name, buffer = null ) {

		super( name );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isBuffer = true;

		/**
		 * The bytes per element.
		 *
		 * @type {number}
		 */
		this.bytesPerElement = Float32Array.BYTES_PER_ELEMENT;

		/**
		 * A reference to the internal buffer.
		 *
		 * @private
		 * @type {TypedArray}
		 */
		this._buffer = buffer;

	}

	/**
	 * The buffer's byte length.
	 *
	 * @type {number}
	 * @readonly
	 */
	get byteLength() {

		return getFloatLength( this._buffer.byteLength );

	}

	/**
	 * A reference to the internal buffer.
	 *
	 * @type {Float32Array}
	 * @readonly
	 */
	get buffer() {

		return this._buffer;

	}

	/**
	 * Updates the binding.
	 *
	 * @return {boolean} Whether the buffer has been updated and must be
	 * uploaded to the GPU.
	 */
	update() {

		return true;

	}

}
```
</details>

#### Methods

##### `update(): boolean`

<details><summary>Code</summary>

```ts
update() {

		return true;

	}
```
</details>


---