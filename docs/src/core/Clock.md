[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Clock.js`

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
📂 **`src/core/Clock.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `diff` | `number` | let/var | `0` | ✗ |


---

## Functions

### `Clock.start(): void`

**JSDoc:**
```typescript
/**
	 * Starts the clock. When `autoStart` is set to `true`, the method is automatically
	 * called by the class.
	 */
```

**Returns:** `void`

**Calls:**

- `performance.now`

<details><summary>Code</summary>

```typescript
start() {

		this.startTime = performance.now();

		this.oldTime = this.startTime;
		this.elapsedTime = 0;
		this.running = true;

	}
```
</details>

### `Clock.stop(): void`

**JSDoc:**
```typescript
/**
	 * Stops the clock.
	 */
```

**Returns:** `void`

**Calls:**

- `this.getElapsedTime`

<details><summary>Code</summary>

```typescript
stop() {

		this.getElapsedTime();
		this.running = false;
		this.autoStart = false;

	}
```
</details>

### `Clock.getElapsedTime(): number`

**JSDoc:**
```typescript
/**
	 * Returns the elapsed time in seconds.
	 *
	 * @return {number} The elapsed time.
	 */
```

**Returns:** `number`

**Calls:**

- `this.getDelta`

<details><summary>Code</summary>

```typescript
getElapsedTime() {

		this.getDelta();
		return this.elapsedTime;

	}
```
</details>

### `Clock.getDelta(): number`

**JSDoc:**
```typescript
/**
	 * Returns the delta time in seconds.
	 *
	 * @return {number} The delta time.
	 */
```

**Returns:** `number`

**Calls:**

- `this.start`
- `performance.now`

<details><summary>Code</summary>

```typescript
getDelta() {

		let diff = 0;

		if ( this.autoStart && ! this.running ) {

			this.start();
			return 0;

		}

		if ( this.running ) {

			const newTime = performance.now();

			diff = ( newTime - this.oldTime ) / 1000;
			this.oldTime = newTime;

			this.elapsedTime += diff;

		}

		return diff;

	}
```
</details>


---

## Classes

### `Clock`

<details><summary>Class Code</summary>

```ts
class Clock {

	/**
	 * Constructs a new clock.
	 *
	 * @param {boolean} [autoStart=true] - Whether to automatically start the clock when
	 * `getDelta()` is called for the first time.
	 */
	constructor( autoStart = true ) {

		/**
		 * If set to `true`, the clock starts automatically when `getDelta()` is called
		 * for the first time.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.autoStart = autoStart;

		/**
		 * Holds the time at which the clock's `start()` method was last called.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.startTime = 0;

		/**
		 * Holds the time at which the clock's `start()`, `getElapsedTime()` or
		 * `getDelta()` methods were last called.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.oldTime = 0;

		/**
		 * Keeps track of the total time that the clock has been running.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.elapsedTime = 0;

		/**
		 * Whether the clock is running or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.running = false;

	}

	/**
	 * Starts the clock. When `autoStart` is set to `true`, the method is automatically
	 * called by the class.
	 */
	start() {

		this.startTime = performance.now();

		this.oldTime = this.startTime;
		this.elapsedTime = 0;
		this.running = true;

	}

	/**
	 * Stops the clock.
	 */
	stop() {

		this.getElapsedTime();
		this.running = false;
		this.autoStart = false;

	}

	/**
	 * Returns the elapsed time in seconds.
	 *
	 * @return {number} The elapsed time.
	 */
	getElapsedTime() {

		this.getDelta();
		return this.elapsedTime;

	}

	/**
	 * Returns the delta time in seconds.
	 *
	 * @return {number} The delta time.
	 */
	getDelta() {

		let diff = 0;

		if ( this.autoStart && ! this.running ) {

			this.start();
			return 0;

		}

		if ( this.running ) {

			const newTime = performance.now();

			diff = ( newTime - this.oldTime ) / 1000;
			this.oldTime = newTime;

			this.elapsedTime += diff;

		}

		return diff;

	}

}
```
</details>

#### Methods

##### `start(): void`

<details><summary>Code</summary>

```ts
start() {

		this.startTime = performance.now();

		this.oldTime = this.startTime;
		this.elapsedTime = 0;
		this.running = true;

	}
```
</details>

##### `stop(): void`

<details><summary>Code</summary>

```ts
stop() {

		this.getElapsedTime();
		this.running = false;
		this.autoStart = false;

	}
```
</details>

##### `getElapsedTime(): number`

<details><summary>Code</summary>

```ts
getElapsedTime() {

		this.getDelta();
		return this.elapsedTime;

	}
```
</details>

##### `getDelta(): number`

<details><summary>Code</summary>

```ts
getDelta() {

		let diff = 0;

		if ( this.autoStart && ! this.running ) {

			this.start();
			return 0;

		}

		if ( this.running ) {

			const newTime = performance.now();

			diff = ( newTime - this.oldTime ) / 1000;
			this.oldTime = newTime;

			this.elapsedTime += diff;

		}

		return diff;

	}
```
</details>


---