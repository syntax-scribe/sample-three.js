[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TimestampQueryPool.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |

## 📚 Table of Contents

- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/TimestampQueryPool.js`**

## Functions

### `TimestampQueryPool.allocateQueriesForContext(): number`

**JSDoc:**
```typescript
/**
	 * Allocate queries for a specific renderContext.
	 *
	 * @abstract
	 * @param {Object} renderContext - The render context to allocate queries for.
	 * @returns {?number}
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
allocateQueriesForContext( /* renderContext */ ) {}
```
</details>

### `TimestampQueryPool.resolveQueriesAsync(): number | Promise<number>`

**JSDoc:**
```typescript
/**
	 * Resolve all timestamps and return data (or process them).
	 *
	 * @abstract
	 * @async
	 * @returns {Promise<number>|number} The resolved timestamp value.
	 */
```

**Returns:** `number | Promise<number>`

<details><summary>Code</summary>

```typescript
async resolveQueriesAsync() {}
```
</details>

### `TimestampQueryPool.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Dispose of the query pool.
	 *
	 * @abstract
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
dispose() {}
```
</details>


---

## Classes

### `TimestampQueryPool`

<details><summary>Class Code</summary>

```ts
class TimestampQueryPool {

	/**
	 * Creates a new timestamp query pool.
	 *
	 * @param {number} [maxQueries=256] - Maximum number of queries this pool can hold.
	 */
	constructor( maxQueries = 256 ) {

		/**
		 * Whether to track timestamps or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.trackTimestamp = true;

		/**
		 * Maximum number of queries this pool can hold.
		 *
		 * @type {number}
		 * @default 256
		 */
		this.maxQueries = maxQueries;

		/**
		 * How many queries allocated so far.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.currentQueryIndex = 0;

		/**
		 * Tracks offsets for different contexts.
		 *
		 * @type {Map<string, number>}
		 */
		this.queryOffsets = new Map();

		/**
		 * Whether the pool has been disposed or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.isDisposed = false;

		/**
		 * TODO
		 *
		 * @type {number}
		 * @default 0
		 */
		this.lastValue = 0;

		/**
		 * TODO
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.pendingResolve = false;

	}

	/**
	 * Allocate queries for a specific renderContext.
	 *
	 * @abstract
	 * @param {Object} renderContext - The render context to allocate queries for.
	 * @returns {?number}
	 */
	allocateQueriesForContext( /* renderContext */ ) {}

	/**
	 * Resolve all timestamps and return data (or process them).
	 *
	 * @abstract
	 * @async
	 * @returns {Promise<number>|number} The resolved timestamp value.
	 */
	async resolveQueriesAsync() {}

	/**
	 * Dispose of the query pool.
	 *
	 * @abstract
	 */
	dispose() {}

}
```
</details>

#### Methods

##### `allocateQueriesForContext(): number`

<details><summary>Code</summary>

```ts
allocateQueriesForContext( /* renderContext */ ) {}
```
</details>

##### `resolveQueriesAsync(): number | Promise<number>`

<details><summary>Code</summary>

```ts
async resolveQueriesAsync() {}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {}
```
</details>


---