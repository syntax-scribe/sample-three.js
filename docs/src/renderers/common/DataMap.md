[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `DataMap.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/DataMap.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `map` | `any` | let/var | `null` | ✗ |


---

## Functions

### `DataMap.get(object: any): any`

**JSDoc:**
```typescript
/**
	 * Returns the dictionary for the given object.
	 *
	 * @param {Object} object - The object.
	 * @return {Object} The dictionary.
	 */
```

**Parameters:**

- **`object`** `any`

**Returns:** `any`

**Calls:**

- `this.data.get`
- `this.data.set`

<details><summary>Code</summary>

```typescript
get( object ) {

		let map = this.data.get( object );

		if ( map === undefined ) {

			map = {};
			this.data.set( object, map );

		}

		return map;

	}
```
</details>

### `DataMap.delete(object: any): any`

**JSDoc:**
```typescript
/**
	 * Deletes the dictionary for the given object.
	 *
	 * @param {Object} object - The object.
	 * @return {?Object} The deleted dictionary.
	 */
```

**Parameters:**

- **`object`** `any`

**Returns:** `any`

**Calls:**

- `this.data.has`
- `this.data.get`
- `this.data.delete`

<details><summary>Code</summary>

```typescript
delete( object ) {

		let map = null;

		if ( this.data.has( object ) ) {

			map = this.data.get( object );

			this.data.delete( object );

		}

		return map;

	}
```
</details>

### `DataMap.has(object: any): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given object has a dictionary defined.
	 *
	 * @param {Object} object - The object to test.
	 * @return {boolean} Whether a dictionary is defined or not.
	 */
```

**Parameters:**

- **`object`** `any`

**Returns:** `boolean`

**Calls:**

- `this.data.has`

<details><summary>Code</summary>

```typescript
has( object ) {

		return this.data.has( object );

	}
```
</details>

### `DataMap.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
dispose() {

		this.data = new WeakMap();

	}
```
</details>


---

## Classes

### `DataMap`

<details><summary>Class Code</summary>

```ts
class DataMap {

	/**
	 * Constructs a new data map.
	 */
	constructor() {

		/**
		 * `DataMap` internally uses a weak map
		 * to manage its data.
		 *
		 * @type {WeakMap}
		 */
		this.data = new WeakMap();

	}

	/**
	 * Returns the dictionary for the given object.
	 *
	 * @param {Object} object - The object.
	 * @return {Object} The dictionary.
	 */
	get( object ) {

		let map = this.data.get( object );

		if ( map === undefined ) {

			map = {};
			this.data.set( object, map );

		}

		return map;

	}

	/**
	 * Deletes the dictionary for the given object.
	 *
	 * @param {Object} object - The object.
	 * @return {?Object} The deleted dictionary.
	 */
	delete( object ) {

		let map = null;

		if ( this.data.has( object ) ) {

			map = this.data.get( object );

			this.data.delete( object );

		}

		return map;

	}

	/**
	 * Returns `true` if the given object has a dictionary defined.
	 *
	 * @param {Object} object - The object to test.
	 * @return {boolean} Whether a dictionary is defined or not.
	 */
	has( object ) {

		return this.data.has( object );

	}

	/**
	 * Frees internal resources.
	 */
	dispose() {

		this.data = new WeakMap();

	}

}
```
</details>

#### Methods

##### `get(object: any): any`

<details><summary>Code</summary>

```ts
get( object ) {

		let map = this.data.get( object );

		if ( map === undefined ) {

			map = {};
			this.data.set( object, map );

		}

		return map;

	}
```
</details>

##### `delete(object: any): any`

<details><summary>Code</summary>

```ts
delete( object ) {

		let map = null;

		if ( this.data.has( object ) ) {

			map = this.data.get( object );

			this.data.delete( object );

		}

		return map;

	}
```
</details>

##### `has(object: any): boolean`

<details><summary>Code</summary>

```ts
has( object ) {

		return this.data.has( object );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.data = new WeakMap();

	}
```
</details>


---