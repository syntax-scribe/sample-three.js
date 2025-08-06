[⬅️ Back to Table of Contents](../../index.md)

# 📄 `InstancedInterleavedBuffer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/core/InstancedInterleavedBuffer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `InterleavedBuffer` | `./InterleavedBuffer.js` |


---

## Functions

### `InstancedInterleavedBuffer.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.meshPerAttribute = source.meshPerAttribute;

		return this;

	}
```
</details>

### `InstancedInterleavedBuffer.clone(data: any): InterleavedBuffer`

**Parameters:**

- **`data`** `any`

**Returns:** `InterleavedBuffer`

**Calls:**

- `super.clone`

<details><summary>Code</summary>

```typescript
clone( data ) {

		const ib = super.clone( data );

		ib.meshPerAttribute = this.meshPerAttribute;

		return ib;

	}
```
</details>

### `InstancedInterleavedBuffer.toJSON(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `super.toJSON`

<details><summary>Code</summary>

```typescript
toJSON( data ) {

		const json = super.toJSON( data );

		json.isInstancedInterleavedBuffer = true;
		json.meshPerAttribute = this.meshPerAttribute;

		return json;

	}
```
</details>


---

## Classes

### `InstancedInterleavedBuffer`

<details><summary>Class Code</summary>

```ts
class InstancedInterleavedBuffer extends InterleavedBuffer {

	/**
	 * Constructs a new instanced interleaved buffer.
	 *
	 * @param {TypedArray} array - A typed array with a shared buffer storing attribute data.
	 * @param {number} stride - The number of typed-array elements per vertex.
	 * @param {number} [meshPerAttribute=1] - Defines how often a value of this interleaved buffer should be repeated.
	 */
	constructor( array, stride, meshPerAttribute = 1 ) {

		super( array, stride );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isInstancedInterleavedBuffer = true;

		/**
		 * Defines how often a value of this buffer attribute should be repeated,
		 * see {@link InstancedBufferAttribute#meshPerAttribute}.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.meshPerAttribute = meshPerAttribute;

	}

	copy( source ) {

		super.copy( source );

		this.meshPerAttribute = source.meshPerAttribute;

		return this;

	}

	clone( data ) {

		const ib = super.clone( data );

		ib.meshPerAttribute = this.meshPerAttribute;

		return ib;

	}

	toJSON( data ) {

		const json = super.toJSON( data );

		json.isInstancedInterleavedBuffer = true;
		json.meshPerAttribute = this.meshPerAttribute;

		return json;

	}

}
```
</details>

#### Methods

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source );

		this.meshPerAttribute = source.meshPerAttribute;

		return this;

	}
```
</details>

##### `clone(data: any): InterleavedBuffer`

<details><summary>Code</summary>

```ts
clone( data ) {

		const ib = super.clone( data );

		ib.meshPerAttribute = this.meshPerAttribute;

		return ib;

	}
```
</details>

##### `toJSON(data: any): any`

<details><summary>Code</summary>

```ts
toJSON( data ) {

		const json = super.toJSON( data );

		json.isInstancedInterleavedBuffer = true;
		json.meshPerAttribute = this.meshPerAttribute;

		return json;

	}
```
</details>


---