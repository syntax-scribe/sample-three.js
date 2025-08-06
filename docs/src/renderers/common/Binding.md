[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Binding.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |

## 📚 Table of Contents

- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/Binding.js`**

## Functions

### `Binding.setVisibility(visibility: number): void`

**JSDoc:**
```typescript
/**
	 * Makes sure binding's resource is visible for the given shader stage.
	 *
	 * @param {number} visibility - The shader stage.
	 */
```

**Parameters:**

- **`visibility`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setVisibility( visibility ) {

		this.visibility |= visibility;

	}
```
</details>

### `Binding.clone(): Binding`

**JSDoc:**
```typescript
/**
	 * Clones the binding.
	 *
	 * @return {Binding} The cloned binding.
	 */
```

**Returns:** `Binding`

**Calls:**

- `Object.assign`

<details><summary>Code</summary>

```typescript
clone() {

		return Object.assign( new this.constructor(), this );

	}
```
</details>


---

## Classes

### `Binding`

<details><summary>Class Code</summary>

```ts
class Binding {

	/**
	 * Constructs a new binding.
	 *
	 * @param {string} [name=''] - The binding's name.
	 */
	constructor( name = '' ) {

		/**
		 * The binding's name.
		 *
		 * @type {string}
		 */
		this.name = name;

		/**
		 * A bitmask that defines in what shader stages the
		 * binding's resource is accessible.
		 *
		 * @type {number}
		 */
		this.visibility = 0;

	}

	/**
	 * Makes sure binding's resource is visible for the given shader stage.
	 *
	 * @param {number} visibility - The shader stage.
	 */
	setVisibility( visibility ) {

		this.visibility |= visibility;

	}

	/**
	 * Clones the binding.
	 *
	 * @return {Binding} The cloned binding.
	 */
	clone() {

		return Object.assign( new this.constructor(), this );

	}

}
```
</details>

#### Methods

##### `setVisibility(visibility: number): void`

<details><summary>Code</summary>

```ts
setVisibility( visibility ) {

		this.visibility |= visibility;

	}
```
</details>

##### `clone(): Binding`

<details><summary>Code</summary>

```ts
clone() {

		return Object.assign( new this.constructor(), this );

	}
```
</details>


---