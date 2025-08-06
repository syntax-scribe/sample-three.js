[⬅️ Back to Table of Contents](../../index.md)

# 📄 `InstancedBufferGeometry.js`

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
📂 **`src/core/InstancedBufferGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `./BufferGeometry.js` |


---

## Functions

### `InstancedBufferGeometry.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.instanceCount = source.instanceCount;

		return this;

	}
```
</details>

### `InstancedBufferGeometry.toJSON(): any`

**Returns:** `any`

**Calls:**

- `super.toJSON`

<details><summary>Code</summary>

```typescript
toJSON() {

		const data = super.toJSON();

		data.instanceCount = this.instanceCount;

		data.isInstancedBufferGeometry = true;

		return data;

	}
```
</details>


---

## Classes

### `InstancedBufferGeometry`

<details><summary>Class Code</summary>

```ts
class InstancedBufferGeometry extends BufferGeometry {

	/**
	 * Constructs a new instanced buffer geometry.
	 */
	constructor() {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isInstancedBufferGeometry = true;

		this.type = 'InstancedBufferGeometry';

		/**
		 * The instance count.
		 *
		 * @type {number}
		 * @default Infinity
		 */
		this.instanceCount = Infinity;

	}

	copy( source ) {

		super.copy( source );

		this.instanceCount = source.instanceCount;

		return this;

	}

	toJSON() {

		const data = super.toJSON();

		data.instanceCount = this.instanceCount;

		data.isInstancedBufferGeometry = true;

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

		this.instanceCount = source.instanceCount;

		return this;

	}
```
</details>

##### `toJSON(): any`

<details><summary>Code</summary>

```ts
toJSON() {

		const data = super.toJSON();

		data.instanceCount = this.instanceCount;

		data.isInstancedBufferGeometry = true;

		return data;

	}
```
</details>


---