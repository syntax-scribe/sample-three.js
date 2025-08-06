[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ChainMap.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/ChainMap.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `map` | `WeakMap<any, any>` | let/var | `this.weakMap` | ✗ |
| `map` | `WeakMap<any, any>` | let/var | `this.weakMap` | ✗ |
| `key` | `any` | let/var | `keys[ i ]` | ✗ |
| `map` | `WeakMap<any, any>` | let/var | `this.weakMap` | ✗ |


---

## Functions

### `ChainMap.get(keys: any[]): any`

**JSDoc:**
```typescript
/**
	 * Returns the value for the given array of keys.
	 *
	 * @param {Array<Object>} keys - List of keys.
	 * @return {any} The value. Returns `undefined` if no value was found.
	 */
```

**Parameters:**

- **`keys`** `any[]`

**Returns:** `any`

**Calls:**

- `map.get`

<details><summary>Code</summary>

```typescript
get( keys ) {

		let map = this.weakMap;

		for ( let i = 0; i < keys.length - 1; i ++ ) {

			map = map.get( keys[ i ] );

			if ( map === undefined ) return undefined;

		}

		return map.get( keys[ keys.length - 1 ] );

	}
```
</details>

### `ChainMap.set(keys: any[], value: any): ChainMap`

**JSDoc:**
```typescript
/**
	 * Sets the value for the given keys.
	 *
	 * @param {Array<Object>} keys - List of keys.
	 * @param {any} value - The value to set.
	 * @return {ChainMap} A reference to this Chain Map.
	 */
```

**Parameters:**

- **`keys`** `any[]`
- **`value`** `any`

**Returns:** `ChainMap`

**Calls:**

- `map.has`
- `map.set`
- `map.get`

<details><summary>Code</summary>

```typescript
set( keys, value ) {

		let map = this.weakMap;

		for ( let i = 0; i < keys.length - 1; i ++ ) {

			const key = keys[ i ];

			if ( map.has( key ) === false ) map.set( key, new WeakMap() );

			map = map.get( key );

		}

		map.set( keys[ keys.length - 1 ], value );

		return this;

	}
```
</details>

### `ChainMap.delete(keys: any[]): boolean`

**JSDoc:**
```typescript
/**
	 * Deletes a value for the given keys.
	 *
	 * @param {Array<Object>} keys - The keys.
	 * @return {boolean} Returns `true` if the value has been removed successfully and `false` if the value has not be found.
	 */
```

**Parameters:**

- **`keys`** `any[]`

**Returns:** `boolean`

**Calls:**

- `map.get`
- `map.delete`

<details><summary>Code</summary>

```typescript
delete( keys ) {

		let map = this.weakMap;

		for ( let i = 0; i < keys.length - 1; i ++ ) {

			map = map.get( keys[ i ] );

			if ( map === undefined ) return false;

		}

		return map.delete( keys[ keys.length - 1 ] );

	}
```
</details>


---

## Classes

### `ChainMap`

<details><summary>Class Code</summary>

```ts
class ChainMap {

	/**
	 * Constructs a new Chain Map.
	 */
	constructor() {

		/**
		 * The root Weak Map.
		 *
		 * @type {WeakMap}
		 */
		this.weakMap = new WeakMap();

	}

	/**
	 * Returns the value for the given array of keys.
	 *
	 * @param {Array<Object>} keys - List of keys.
	 * @return {any} The value. Returns `undefined` if no value was found.
	 */
	get( keys ) {

		let map = this.weakMap;

		for ( let i = 0; i < keys.length - 1; i ++ ) {

			map = map.get( keys[ i ] );

			if ( map === undefined ) return undefined;

		}

		return map.get( keys[ keys.length - 1 ] );

	}

	/**
	 * Sets the value for the given keys.
	 *
	 * @param {Array<Object>} keys - List of keys.
	 * @param {any} value - The value to set.
	 * @return {ChainMap} A reference to this Chain Map.
	 */
	set( keys, value ) {

		let map = this.weakMap;

		for ( let i = 0; i < keys.length - 1; i ++ ) {

			const key = keys[ i ];

			if ( map.has( key ) === false ) map.set( key, new WeakMap() );

			map = map.get( key );

		}

		map.set( keys[ keys.length - 1 ], value );

		return this;

	}

	/**
	 * Deletes a value for the given keys.
	 *
	 * @param {Array<Object>} keys - The keys.
	 * @return {boolean} Returns `true` if the value has been removed successfully and `false` if the value has not be found.
	 */
	delete( keys ) {

		let map = this.weakMap;

		for ( let i = 0; i < keys.length - 1; i ++ ) {

			map = map.get( keys[ i ] );

			if ( map === undefined ) return false;

		}

		return map.delete( keys[ keys.length - 1 ] );

	}

}
```
</details>

#### Methods

##### `get(keys: any[]): any`

<details><summary>Code</summary>

```ts
get( keys ) {

		let map = this.weakMap;

		for ( let i = 0; i < keys.length - 1; i ++ ) {

			map = map.get( keys[ i ] );

			if ( map === undefined ) return undefined;

		}

		return map.get( keys[ keys.length - 1 ] );

	}
```
</details>

##### `set(keys: any[], value: any): ChainMap`

<details><summary>Code</summary>

```ts
set( keys, value ) {

		let map = this.weakMap;

		for ( let i = 0; i < keys.length - 1; i ++ ) {

			const key = keys[ i ];

			if ( map.has( key ) === false ) map.set( key, new WeakMap() );

			map = map.get( key );

		}

		map.set( keys[ keys.length - 1 ], value );

		return this;

	}
```
</details>

##### `delete(keys: any[]): boolean`

<details><summary>Code</summary>

```ts
delete( keys ) {

		let map = this.weakMap;

		for ( let i = 0; i < keys.length - 1; i ++ ) {

			map = map.get( keys[ i ] );

			if ( map === undefined ) return false;

		}

		return map.delete( keys[ keys.length - 1 ] );

	}
```
</details>


---