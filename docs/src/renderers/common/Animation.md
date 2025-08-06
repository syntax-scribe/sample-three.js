[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Animation.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |

## 📚 Table of Contents

- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/Animation.js`**

## Functions

### `Animation.start(): void`

**JSDoc:**
```typescript
/**
	 * Starts the internal animation loop.
	 */
```

**Returns:** `void`

**Calls:**

- `this._context.requestAnimationFrame`
- `this.info.reset`
- `this.nodes.nodeFrame.update`
- `this._animationLoop`
- `update`

<details><summary>Code</summary>

```typescript
start() {

		const update = ( time, xrFrame ) => {

			this._requestId = this._context.requestAnimationFrame( update );

			if ( this.info.autoReset === true ) this.info.reset();

			this.nodes.nodeFrame.update();

			this.info.frame = this.nodes.nodeFrame.frameId;

			if ( this._animationLoop !== null ) this._animationLoop( time, xrFrame );

		};

		update();

	}
```
</details>

### `Animation.stop(): void`

**JSDoc:**
```typescript
/**
	 * Stops the internal animation loop.
	 */
```

**Returns:** `void`

**Calls:**

- `this._context.cancelAnimationFrame`

<details><summary>Code</summary>

```typescript
stop() {

		this._context.cancelAnimationFrame( this._requestId );

		this._requestId = null;

	}
```
</details>

### `Animation.getAnimationLoop(): Function`

**JSDoc:**
```typescript
/**
	 * Returns the user-level animation loop.
	 *
	 * @return {?Function} The animation loop.
	 */
```

**Returns:** `Function`

<details><summary>Code</summary>

```typescript
getAnimationLoop() {

		return this._animationLoop;

	}
```
</details>

### `Animation.setAnimationLoop(callback: Function): void`

**JSDoc:**
```typescript
/**
	 * Defines the user-level animation loop.
	 *
	 * @param {?Function} callback - The animation loop.
	 */
```

**Parameters:**

- **`callback`** `Function`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setAnimationLoop( callback ) {

		this._animationLoop = callback;

	}
```
</details>

### `Animation.getContext(): any`

**JSDoc:**
```typescript
/**
	 * Returns the animation context.
	 *
	 * @return {Window|XRSession} The animation context.
	 */
```

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getContext() {

		return this._context;

	}
```
</details>

### `Animation.setContext(context: any): void`

**JSDoc:**
```typescript
/**
	 * Defines the context in which `requestAnimationFrame()` is executed.
	 *
	 * @param {Window|XRSession} context - The context to set.
	 */
```

**Parameters:**

- **`context`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setContext( context ) {

		this._context = context;

	}
```
</details>

### `Animation.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees all internal resources and stops the animation loop.
	 */
```

**Returns:** `void`

**Calls:**

- `this.stop`

<details><summary>Code</summary>

```typescript
dispose() {

		this.stop();

	}
```
</details>

### `update(time: any, xrFrame: any): void`

**Parameters:**

- **`time`** `any`
- **`xrFrame`** `any`

**Returns:** `void`

**Calls:**

- `this._context.requestAnimationFrame`
- `this.info.reset`
- `this.nodes.nodeFrame.update`
- `this._animationLoop`

<details><summary>Code</summary>

```typescript
( time, xrFrame ) => {

			this._requestId = this._context.requestAnimationFrame( update );

			if ( this.info.autoReset === true ) this.info.reset();

			this.nodes.nodeFrame.update();

			this.info.frame = this.nodes.nodeFrame.frameId;

			if ( this._animationLoop !== null ) this._animationLoop( time, xrFrame );

		}
```
</details>


---

## Classes

### `Animation`

<details><summary>Class Code</summary>

```ts
class Animation {

	/**
	 * Constructs a new animation loop management component.
	 *
	 * @param {Nodes} nodes - Renderer component for managing nodes related logic.
	 * @param {Info} info - Renderer component for managing metrics and monitoring data.
	 */
	constructor( nodes, info ) {

		/**
		 * Renderer component for managing nodes related logic.
		 *
		 * @type {Nodes}
		 */
		this.nodes = nodes;

		/**
		 * Renderer component for managing metrics and monitoring data.
		 *
		 * @type {Info}
		 */
		this.info = info;

		/**
		 * A reference to the context from `requestAnimationFrame()` can
		 * be called (usually `window`).
		 *
		 * @type {?(Window|XRSession)}
		 */
		this._context = typeof self !== 'undefined' ? self : null;

		/**
		 * The user-defined animation loop.
		 *
		 * @type {?Function}
		 * @default null
		 */
		this._animationLoop = null;

		/**
		 * The requestId which is returned from the `requestAnimationFrame()` call.
		 * Can be used to cancel the stop the animation loop.
		 *
		 * @type {?number}
		 * @default null
		 */
		this._requestId = null;

	}

	/**
	 * Starts the internal animation loop.
	 */
	start() {

		const update = ( time, xrFrame ) => {

			this._requestId = this._context.requestAnimationFrame( update );

			if ( this.info.autoReset === true ) this.info.reset();

			this.nodes.nodeFrame.update();

			this.info.frame = this.nodes.nodeFrame.frameId;

			if ( this._animationLoop !== null ) this._animationLoop( time, xrFrame );

		};

		update();

	}

	/**
	 * Stops the internal animation loop.
	 */
	stop() {

		this._context.cancelAnimationFrame( this._requestId );

		this._requestId = null;

	}

	/**
	 * Returns the user-level animation loop.
	 *
	 * @return {?Function} The animation loop.
	 */
	getAnimationLoop() {

		return this._animationLoop;

	}

	/**
	 * Defines the user-level animation loop.
	 *
	 * @param {?Function} callback - The animation loop.
	 */
	setAnimationLoop( callback ) {

		this._animationLoop = callback;

	}

	/**
	 * Returns the animation context.
	 *
	 * @return {Window|XRSession} The animation context.
	 */
	getContext() {

		return this._context;

	}

	/**
	 * Defines the context in which `requestAnimationFrame()` is executed.
	 *
	 * @param {Window|XRSession} context - The context to set.
	 */
	setContext( context ) {

		this._context = context;

	}

	/**
	 * Frees all internal resources and stops the animation loop.
	 */
	dispose() {

		this.stop();

	}

}
```
</details>

#### Methods

##### `start(): void`

<details><summary>Code</summary>

```ts
start() {

		const update = ( time, xrFrame ) => {

			this._requestId = this._context.requestAnimationFrame( update );

			if ( this.info.autoReset === true ) this.info.reset();

			this.nodes.nodeFrame.update();

			this.info.frame = this.nodes.nodeFrame.frameId;

			if ( this._animationLoop !== null ) this._animationLoop( time, xrFrame );

		};

		update();

	}
```
</details>

##### `stop(): void`

<details><summary>Code</summary>

```ts
stop() {

		this._context.cancelAnimationFrame( this._requestId );

		this._requestId = null;

	}
```
</details>

##### `getAnimationLoop(): Function`

<details><summary>Code</summary>

```ts
getAnimationLoop() {

		return this._animationLoop;

	}
```
</details>

##### `setAnimationLoop(callback: Function): void`

<details><summary>Code</summary>

```ts
setAnimationLoop( callback ) {

		this._animationLoop = callback;

	}
```
</details>

##### `getContext(): any`

<details><summary>Code</summary>

```ts
getContext() {

		return this._context;

	}
```
</details>

##### `setContext(context: any): void`

<details><summary>Code</summary>

```ts
setContext( context ) {

		this._context = context;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.stop();

	}
```
</details>


---