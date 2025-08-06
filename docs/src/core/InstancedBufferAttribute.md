[⬅️ Back to Table of Contents](../../index.md)

# 📄 `InstancedBufferAttribute.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/core/InstancedBufferAttribute.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferAttribute` | `./BufferAttribute.js` |


---

## Functions

### `InstancedBufferAttribute.copy(source: any): this`

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

### `InstancedBufferAttribute.toJSON(): any`

**Returns:** `any`

**Calls:**

- `super.toJSON`

<details><summary>Code</summary>

```typescript
toJSON() {

		const data = super.toJSON();

		data.meshPerAttribute = this.meshPerAttribute;

		data.isInstancedBufferAttribute = true;

		return data;

	}
```
</details>


---

## Classes

### `InstancedBufferAttribute`

<details><summary>Class Code</summary>

```ts
class InstancedBufferAttribute extends BufferAttribute {

	/**
	 * Constructs a new instanced buffer attribute.
	 *
	 * @param {TypedArray} array - The array holding the attribute data.
	 * @param {number} itemSize - The item size.
	 * @param {boolean} [normalized=false] - Whether the data are normalized or not.
	 * @param {number} [meshPerAttribute=1] - How often a value of this buffer attribute should be repeated.
	 */
	constructor( array, itemSize, normalized, meshPerAttribute = 1 ) {

		super( array, itemSize, normalized );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isInstancedBufferAttribute = true;

		/**
		 * Defines how often a value of this buffer attribute should be repeated. A
		 * value of one means that each value of the instanced attribute is used for
		 * a single instance. A value of two means that each value is used for two
		 * consecutive instances (and so on).
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

	toJSON() {

		const data = super.toJSON();

		data.meshPerAttribute = this.meshPerAttribute;

		data.isInstancedBufferAttribute = true;

		return data;

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

##### `toJSON(): any`

<details><summary>Code</summary>

```ts
toJSON() {

		const data = super.toJSON();

		data.meshPerAttribute = this.meshPerAttribute;

		data.isInstancedBufferAttribute = true;

		return data;

	}
```
</details>


---