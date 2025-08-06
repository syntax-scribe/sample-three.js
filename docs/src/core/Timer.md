[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Timer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 🧱 Classes | 1 |

## 📚 Table of Contents

- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/core/Timer.js`**

## Functions

### `Timer.connect(document: Document): void`

**JSDoc:**
```typescript
/**
	 * Connect the timer to the given document.Calling this method is not mandatory to
	 * use the timer but enables the usage of the Page Visibility API to avoid large time
	 * delta values.
	 *
	 * @param {Document} document - The document.
	 */
```

**Parameters:**

- **`document`** `Document`

**Returns:** `void`

**Calls:**

- `handleVisibilityChange.bind`
- `document.addEventListener`

**Internal Comments:**
```
// use Page Visibility API to avoid large time delta values
```

<details><summary>Code</summary>

```typescript
connect( document ) {

		this._document = document;

		// use Page Visibility API to avoid large time delta values

		if ( document.hidden !== undefined ) {

			this._pageVisibilityHandler = handleVisibilityChange.bind( this );

			document.addEventListener( 'visibilitychange', this._pageVisibilityHandler, false );

		}

	}
```
</details>

### `Timer.disconnect(): void`

**JSDoc:**
```typescript
/**
	 * Disconnects the timer from the DOM and also disables the usage of the Page Visibility API.
	 */
```

**Returns:** `void`

**Calls:**

- `this._document.removeEventListener`

<details><summary>Code</summary>

```typescript
disconnect() {

		if ( this._pageVisibilityHandler !== null ) {

			this._document.removeEventListener( 'visibilitychange', this._pageVisibilityHandler );
			this._pageVisibilityHandler = null;

		}

		this._document = null;

	}
```
</details>

### `Timer.getDelta(): number`

**JSDoc:**
```typescript
/**
	 * Returns the time delta in seconds.
	 *
	 * @return {number} The time delta in second.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getDelta() {

		return this._delta / 1000;

	}
```
</details>

### `Timer.getElapsed(): number`

**JSDoc:**
```typescript
/**
	 * Returns the elapsed time in seconds.
	 *
	 * @return {number} The elapsed time in second.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getElapsed() {

		return this._elapsed / 1000;

	}
```
</details>

### `Timer.getTimescale(): number`

**JSDoc:**
```typescript
/**
	 * Returns the timescale.
	 *
	 * @return {number} The timescale.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getTimescale() {

		return this._timescale;

	}
```
</details>

### `Timer.setTimescale(timescale: number): Timer`

**JSDoc:**
```typescript
/**
	 * Sets the given timescale which scale the time delta computation
	 * in `update()`.
	 *
	 * @param {number} timescale - The timescale to set.
	 * @return {Timer} A reference to this timer.
	 */
```

**Parameters:**

- **`timescale`** `number`

**Returns:** `Timer`

<details><summary>Code</summary>

```typescript
setTimescale( timescale ) {

		this._timescale = timescale;

		return this;

	}
```
</details>

### `Timer.reset(): Timer`

**JSDoc:**
```typescript
/**
	 * Resets the time computation for the current simulation step.
	 *
	 * @return {Timer} A reference to this timer.
	 */
```

**Returns:** `Timer`

**Calls:**

- `performance.now`

<details><summary>Code</summary>

```typescript
reset() {

		this._currentTime = performance.now() - this._startTime;

		return this;

	}
```
</details>

### `Timer.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Can be used to free all internal resources. Usually called when
	 * the timer instance isn't required anymore.
	 */
```

**Returns:** `void`

**Calls:**

- `this.disconnect`

<details><summary>Code</summary>

```typescript
dispose() {

		this.disconnect();

	}
```
</details>

### `Timer.update(timestamp: number): Timer`

**JSDoc:**
```typescript
/**
	 * Updates the internal state of the timer. This method should be called
	 * once per simulation step and before you perform queries against the timer
	 * (e.g. via `getDelta()`).
	 *
	 * @param {number} timestamp - The current time in milliseconds. Can be obtained
	 * from the `requestAnimationFrame` callback argument. If not provided, the current
	 * time will be determined with `performance.now`.
	 * @return {Timer} A reference to this timer.
	 */
```

**Parameters:**

- **`timestamp`** `number`

**Returns:** `Timer`

**Calls:**

- `performance.now`

<details><summary>Code</summary>

```typescript
update( timestamp ) {

		if ( this._pageVisibilityHandler !== null && this._document.hidden === true ) {

			this._delta = 0;

		} else {

			this._previousTime = this._currentTime;
			this._currentTime = ( timestamp !== undefined ? timestamp : performance.now() ) - this._startTime;

			this._delta = ( this._currentTime - this._previousTime ) * this._timescale;
			this._elapsed += this._delta; // _elapsed is the accumulation of all previous deltas

		}

		return this;

	}
```
</details>

### `handleVisibilityChange(): void`

**Returns:** `void`

**Calls:**

- `this.reset`

<details><summary>Code</summary>

```typescript
function handleVisibilityChange() {

	if ( this._document.hidden === false ) this.reset();

}
```
</details>


---

## Classes

### `Timer`

<details><summary>Class Code</summary>

```ts
class Timer {

	/**
	 * Constructs a new timer.
	 */
	constructor() {

		this._previousTime = 0;
		this._currentTime = 0;
		this._startTime = performance.now();

		this._delta = 0;
		this._elapsed = 0;

		this._timescale = 1;

		this._document = null;
		this._pageVisibilityHandler = null;

	}

	/**
	 * Connect the timer to the given document.Calling this method is not mandatory to
	 * use the timer but enables the usage of the Page Visibility API to avoid large time
	 * delta values.
	 *
	 * @param {Document} document - The document.
	 */
	connect( document ) {

		this._document = document;

		// use Page Visibility API to avoid large time delta values

		if ( document.hidden !== undefined ) {

			this._pageVisibilityHandler = handleVisibilityChange.bind( this );

			document.addEventListener( 'visibilitychange', this._pageVisibilityHandler, false );

		}

	}

	/**
	 * Disconnects the timer from the DOM and also disables the usage of the Page Visibility API.
	 */
	disconnect() {

		if ( this._pageVisibilityHandler !== null ) {

			this._document.removeEventListener( 'visibilitychange', this._pageVisibilityHandler );
			this._pageVisibilityHandler = null;

		}

		this._document = null;

	}

	/**
	 * Returns the time delta in seconds.
	 *
	 * @return {number} The time delta in second.
	 */
	getDelta() {

		return this._delta / 1000;

	}

	/**
	 * Returns the elapsed time in seconds.
	 *
	 * @return {number} The elapsed time in second.
	 */
	getElapsed() {

		return this._elapsed / 1000;

	}

	/**
	 * Returns the timescale.
	 *
	 * @return {number} The timescale.
	 */
	getTimescale() {

		return this._timescale;

	}

	/**
	 * Sets the given timescale which scale the time delta computation
	 * in `update()`.
	 *
	 * @param {number} timescale - The timescale to set.
	 * @return {Timer} A reference to this timer.
	 */
	setTimescale( timescale ) {

		this._timescale = timescale;

		return this;

	}

	/**
	 * Resets the time computation for the current simulation step.
	 *
	 * @return {Timer} A reference to this timer.
	 */
	reset() {

		this._currentTime = performance.now() - this._startTime;

		return this;

	}

	/**
	 * Can be used to free all internal resources. Usually called when
	 * the timer instance isn't required anymore.
	 */
	dispose() {

		this.disconnect();

	}

	/**
	 * Updates the internal state of the timer. This method should be called
	 * once per simulation step and before you perform queries against the timer
	 * (e.g. via `getDelta()`).
	 *
	 * @param {number} timestamp - The current time in milliseconds. Can be obtained
	 * from the `requestAnimationFrame` callback argument. If not provided, the current
	 * time will be determined with `performance.now`.
	 * @return {Timer} A reference to this timer.
	 */
	update( timestamp ) {

		if ( this._pageVisibilityHandler !== null && this._document.hidden === true ) {

			this._delta = 0;

		} else {

			this._previousTime = this._currentTime;
			this._currentTime = ( timestamp !== undefined ? timestamp : performance.now() ) - this._startTime;

			this._delta = ( this._currentTime - this._previousTime ) * this._timescale;
			this._elapsed += this._delta; // _elapsed is the accumulation of all previous deltas

		}

		return this;

	}

}
```
</details>

#### Methods

##### `connect(document: Document): void`

<details><summary>Code</summary>

```ts
connect( document ) {

		this._document = document;

		// use Page Visibility API to avoid large time delta values

		if ( document.hidden !== undefined ) {

			this._pageVisibilityHandler = handleVisibilityChange.bind( this );

			document.addEventListener( 'visibilitychange', this._pageVisibilityHandler, false );

		}

	}
```
</details>

##### `disconnect(): void`

<details><summary>Code</summary>

```ts
disconnect() {

		if ( this._pageVisibilityHandler !== null ) {

			this._document.removeEventListener( 'visibilitychange', this._pageVisibilityHandler );
			this._pageVisibilityHandler = null;

		}

		this._document = null;

	}
```
</details>

##### `getDelta(): number`

<details><summary>Code</summary>

```ts
getDelta() {

		return this._delta / 1000;

	}
```
</details>

##### `getElapsed(): number`

<details><summary>Code</summary>

```ts
getElapsed() {

		return this._elapsed / 1000;

	}
```
</details>

##### `getTimescale(): number`

<details><summary>Code</summary>

```ts
getTimescale() {

		return this._timescale;

	}
```
</details>

##### `setTimescale(timescale: number): Timer`

<details><summary>Code</summary>

```ts
setTimescale( timescale ) {

		this._timescale = timescale;

		return this;

	}
```
</details>

##### `reset(): Timer`

<details><summary>Code</summary>

```ts
reset() {

		this._currentTime = performance.now() - this._startTime;

		return this;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.disconnect();

	}
```
</details>

##### `update(timestamp: number): Timer`

<details><summary>Code</summary>

```ts
update( timestamp ) {

		if ( this._pageVisibilityHandler !== null && this._document.hidden === true ) {

			this._delta = 0;

		} else {

			this._previousTime = this._currentTime;
			this._currentTime = ( timestamp !== undefined ? timestamp : performance.now() ) - this._startTime;

			this._delta = ( this._currentTime - this._previousTime ) * this._timescale;
			this._elapsed += this._delta; // _elapsed is the accumulation of all previous deltas

		}

		return this;

	}
```
</details>


---