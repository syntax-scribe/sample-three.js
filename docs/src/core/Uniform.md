[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Uniform.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |

## 📚 Table of Contents

- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/core/Uniform.js`**

## Functions

### `Uniform.clone(): Uniform`

**JSDoc:**
```typescript
/**
	 * Returns a new uniform with copied values from this instance.
	 * If the value has a `clone()` method, the value is cloned as well.
	 *
	 * @return {Uniform} A clone of this instance.
	 */
```

**Returns:** `Uniform`

**Calls:**

- `this.value.clone`

<details><summary>Code</summary>

```typescript
clone() {

		return new Uniform( this.value.clone === undefined ? this.value : this.value.clone() );

	}
```
</details>


---

## Classes

### `Uniform`

<details><summary>Class Code</summary>

```ts
class Uniform {

	/**
	 * Constructs a new uniform.
	 *
	 * @param {any} value - The uniform value.
	 */
	constructor( value ) {

		/**
		 * The uniform value.
		 *
		 * @type {any}
		 */
		this.value = value;

	}

	/**
	 * Returns a new uniform with copied values from this instance.
	 * If the value has a `clone()` method, the value is cloned as well.
	 *
	 * @return {Uniform} A clone of this instance.
	 */
	clone() {

		return new Uniform( this.value.clone === undefined ? this.value : this.value.clone() );

	}

}
```
</details>

#### Methods

##### `clone(): Uniform`

<details><summary>Code</summary>

```ts
clone() {

		return new Uniform( this.value.clone === undefined ? this.value : this.value.clone() );

	}
```
</details>


---