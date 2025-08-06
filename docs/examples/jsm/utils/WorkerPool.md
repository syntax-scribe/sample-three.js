[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WorkerPool.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/utils/WorkerPool.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `resolve` | `Function` | let/var | `this.workersResolve[ workerId ]` | ✗ |


---

## Functions

### `WorkerPool._initWorker(workerId: any): void`

**Parameters:**

- **`workerId`** `any`

**Returns:** `void`

**Calls:**

- `this.workerCreator`
- `worker.addEventListener`
- `this._onMessage.bind`

<details><summary>Code</summary>

```typescript
_initWorker( workerId ) {

		if ( ! this.workers[ workerId ] ) {

			const worker = this.workerCreator();
			worker.addEventListener( 'message', this._onMessage.bind( this, workerId ) );
			this.workers[ workerId ] = worker;

		}

	}
```
</details>

### `WorkerPool._getIdleWorker(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
_getIdleWorker() {

		for ( let i = 0; i < this.pool; i ++ )
			if ( ! ( this.workerStatus & ( 1 << i ) ) ) return i;

		return - 1;

	}
```
</details>

### `WorkerPool._onMessage(workerId: any, msg: any): void`

**Parameters:**

- **`workerId`** `any`
- **`msg`** `any`

**Returns:** `void`

**Calls:**

- `resolve`
- `this.queue.shift`
- `this.workers[ workerId ].postMessage`

<details><summary>Code</summary>

```typescript
_onMessage( workerId, msg ) {

		const resolve = this.workersResolve[ workerId ];
		resolve && resolve( msg );

		if ( this.queue.length ) {

			const { resolve, msg, transfer } = this.queue.shift();
			this.workersResolve[ workerId ] = resolve;
			this.workers[ workerId ].postMessage( msg, transfer );

		} else {

			this.workerStatus ^= 1 << workerId;

		}

	}
```
</details>

### `WorkerPool.setWorkerCreator(workerCreator: Function): void`

**JSDoc:**
```typescript
/**
	 * Sets a function that is responsible for creating Workers.
	 *
	 * @param {Function} workerCreator - The worker creator function.
	 */
```

**Parameters:**

- **`workerCreator`** `Function`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setWorkerCreator( workerCreator ) {

		this.workerCreator = workerCreator;

	}
```
</details>

### `WorkerPool.setWorkerLimit(pool: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the Worker limit
	 *
	 * @param {number} pool - The size of the pool.
	 */
```

**Parameters:**

- **`pool`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setWorkerLimit( pool ) {

		this.pool = pool;

	}
```
</details>

### `WorkerPool.postMessage(msg: any, transfer: ArrayBuffer[]): Promise<any>`

**JSDoc:**
```typescript
/**
	 * Post a message to an idle Worker. If no Worker is available,
	 * the message is pushed into a message queue for later processing.
	 *
	 * @param {Object} msg - The message.
	 * @param {Array<ArrayBuffer>} transfer - An array with array buffers for data transfer.
	 * @return {Promise} A Promise that resolves when the message has been processed.
	 */
```

**Parameters:**

- **`msg`** `any`
- **`transfer`** `ArrayBuffer[]`

**Returns:** `Promise<any>`

**Calls:**

- `this._getIdleWorker`
- `this._initWorker`
- `this.workers[ workerId ].postMessage`
- `this.queue.push`

<details><summary>Code</summary>

```typescript
postMessage( msg, transfer ) {

		return new Promise( ( resolve ) => {

			const workerId = this._getIdleWorker();

			if ( workerId !== - 1 ) {

				this._initWorker( workerId );
				this.workerStatus |= 1 << workerId;
				this.workersResolve[ workerId ] = resolve;
				this.workers[ workerId ].postMessage( msg, transfer );

			} else {

				this.queue.push( { resolve, msg, transfer } );

			}

		} );

	}
```
</details>

### `WorkerPool.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Terminates all Workers of this pool. Call this  method whenever this
	 * Worker pool is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.workers.forEach`
- `worker.terminate`

<details><summary>Code</summary>

```typescript
dispose() {

		this.workers.forEach( ( worker ) => worker.terminate() );
		this.workersResolve.length = 0;
		this.workers.length = 0;
		this.queue.length = 0;
		this.workerStatus = 0;

	}
```
</details>


---

## Classes

### `WorkerPool`

<details><summary>Class Code</summary>

```ts
export class WorkerPool {

	/**
	 * Constructs a new Worker pool.
	 *
	 * @param {number} [pool=4] - The size of the pool.
	 */
	constructor( pool = 4 ) {

		/**
		 * The size of the pool.
		 *
		 * @type {number}
		 * @default 4
		 */
		this.pool = pool;

		/**
		 * A message queue.
		 *
		 * @type {Array<Object>}
		 */
		this.queue = [];

		/**
		 * An array of Workers.
		 *
		 * @type {Array<Worker>}
		 */
		this.workers = [];

		/**
		 * An array with resolve functions for messages.
		 *
		 * @type {Array<Function>}
		 */
		this.workersResolve = [];

		/**
		 * The current worker status.
		 *
		 * @type {number}
		 */
		this.workerStatus = 0;

		/**
		 * A factory function for creating workers.
		 *
		 * @type {?Function}
		 */
		this.workerCreator = null;

	}

	_initWorker( workerId ) {

		if ( ! this.workers[ workerId ] ) {

			const worker = this.workerCreator();
			worker.addEventListener( 'message', this._onMessage.bind( this, workerId ) );
			this.workers[ workerId ] = worker;

		}

	}

	_getIdleWorker() {

		for ( let i = 0; i < this.pool; i ++ )
			if ( ! ( this.workerStatus & ( 1 << i ) ) ) return i;

		return - 1;

	}

	_onMessage( workerId, msg ) {

		const resolve = this.workersResolve[ workerId ];
		resolve && resolve( msg );

		if ( this.queue.length ) {

			const { resolve, msg, transfer } = this.queue.shift();
			this.workersResolve[ workerId ] = resolve;
			this.workers[ workerId ].postMessage( msg, transfer );

		} else {

			this.workerStatus ^= 1 << workerId;

		}

	}

	/**
	 * Sets a function that is responsible for creating Workers.
	 *
	 * @param {Function} workerCreator - The worker creator function.
	 */
	setWorkerCreator( workerCreator ) {

		this.workerCreator = workerCreator;

	}

	/**
	 * Sets the Worker limit
	 *
	 * @param {number} pool - The size of the pool.
	 */
	setWorkerLimit( pool ) {

		this.pool = pool;

	}

	/**
	 * Post a message to an idle Worker. If no Worker is available,
	 * the message is pushed into a message queue for later processing.
	 *
	 * @param {Object} msg - The message.
	 * @param {Array<ArrayBuffer>} transfer - An array with array buffers for data transfer.
	 * @return {Promise} A Promise that resolves when the message has been processed.
	 */
	postMessage( msg, transfer ) {

		return new Promise( ( resolve ) => {

			const workerId = this._getIdleWorker();

			if ( workerId !== - 1 ) {

				this._initWorker( workerId );
				this.workerStatus |= 1 << workerId;
				this.workersResolve[ workerId ] = resolve;
				this.workers[ workerId ].postMessage( msg, transfer );

			} else {

				this.queue.push( { resolve, msg, transfer } );

			}

		} );

	}

	/**
	 * Terminates all Workers of this pool. Call this  method whenever this
	 * Worker pool is no longer used in your app.
	 */
	dispose() {

		this.workers.forEach( ( worker ) => worker.terminate() );
		this.workersResolve.length = 0;
		this.workers.length = 0;
		this.queue.length = 0;
		this.workerStatus = 0;

	}

}
```
</details>

#### Methods

##### `_initWorker(workerId: any): void`

<details><summary>Code</summary>

```ts
_initWorker( workerId ) {

		if ( ! this.workers[ workerId ] ) {

			const worker = this.workerCreator();
			worker.addEventListener( 'message', this._onMessage.bind( this, workerId ) );
			this.workers[ workerId ] = worker;

		}

	}
```
</details>

##### `_getIdleWorker(): number`

<details><summary>Code</summary>

```ts
_getIdleWorker() {

		for ( let i = 0; i < this.pool; i ++ )
			if ( ! ( this.workerStatus & ( 1 << i ) ) ) return i;

		return - 1;

	}
```
</details>

##### `_onMessage(workerId: any, msg: any): void`

<details><summary>Code</summary>

```ts
_onMessage( workerId, msg ) {

		const resolve = this.workersResolve[ workerId ];
		resolve && resolve( msg );

		if ( this.queue.length ) {

			const { resolve, msg, transfer } = this.queue.shift();
			this.workersResolve[ workerId ] = resolve;
			this.workers[ workerId ].postMessage( msg, transfer );

		} else {

			this.workerStatus ^= 1 << workerId;

		}

	}
```
</details>

##### `setWorkerCreator(workerCreator: Function): void`

<details><summary>Code</summary>

```ts
setWorkerCreator( workerCreator ) {

		this.workerCreator = workerCreator;

	}
```
</details>

##### `setWorkerLimit(pool: number): void`

<details><summary>Code</summary>

```ts
setWorkerLimit( pool ) {

		this.pool = pool;

	}
```
</details>

##### `postMessage(msg: any, transfer: ArrayBuffer[]): Promise<any>`

<details><summary>Code</summary>

```ts
postMessage( msg, transfer ) {

		return new Promise( ( resolve ) => {

			const workerId = this._getIdleWorker();

			if ( workerId !== - 1 ) {

				this._initWorker( workerId );
				this.workerStatus |= 1 << workerId;
				this.workersResolve[ workerId ] = resolve;
				this.workers[ workerId ].postMessage( msg, transfer );

			} else {

				this.queue.push( { resolve, msg, transfer } );

			}

		} );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.workers.forEach( ( worker ) => worker.terminate() );
		this.workersResolve.length = 0;
		this.workers.length = 0;
		this.queue.length = 0;
		this.workerStatus = 0;

	}
```
</details>


---