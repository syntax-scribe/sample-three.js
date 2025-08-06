[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Info.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |

## 📚 Table of Contents

- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/Info.js`**

## Functions

### `Info.update(object: Object3D, count: number, instanceCount: number): void`

**JSDoc:**
```typescript
/**
	 * This method should be executed per draw call and updates the corresponding metrics.
	 *
	 * @param {Object3D} object - The 3D object that is going to be rendered.
	 * @param {number} count - The vertex or index count.
	 * @param {number} instanceCount - The instance count.
	 */
```

**Parameters:**

- **`object`** `Object3D`
- **`count`** `number`
- **`instanceCount`** `number`

**Returns:** `void`

**Calls:**

- `console.error`

<details><summary>Code</summary>

```typescript
update( object, count, instanceCount ) {

		this.render.drawCalls ++;

		if ( object.isMesh || object.isSprite ) {

			this.render.triangles += instanceCount * ( count / 3 );

		} else if ( object.isPoints ) {

			this.render.points += instanceCount * count;

		} else if ( object.isLineSegments ) {

			this.render.lines += instanceCount * ( count / 2 );

		} else if ( object.isLine ) {

			this.render.lines += instanceCount * ( count - 1 );

		} else {

			console.error( 'THREE.WebGPUInfo: Unknown object type.' );

		}

	}
```
</details>

### `Info.reset(): void`

**JSDoc:**
```typescript
/**
	 * Resets frame related metrics.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
reset() {

		this.render.drawCalls = 0;
		this.render.frameCalls = 0;
		this.compute.frameCalls = 0;

		this.render.triangles = 0;
		this.render.points = 0;
		this.render.lines = 0;


	}
```
</details>

### `Info.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Performs a complete reset of the object.
	 */
```

**Returns:** `void`

**Calls:**

- `this.reset`

<details><summary>Code</summary>

```typescript
dispose() {

		this.reset();

		this.calls = 0;

		this.render.calls = 0;
		this.compute.calls = 0;

		this.render.timestamp = 0;
		this.compute.timestamp = 0;
		this.memory.geometries = 0;
		this.memory.textures = 0;

	}
```
</details>


---

## Classes

### `Info`

<details><summary>Class Code</summary>

```ts
class Info {

	/**
	 * Constructs a new info component.
	 */
	constructor() {

		/**
		 * Whether frame related metrics should automatically
		 * be resetted or not. This property should be set to `false`
		 * by apps which manage their own animation loop. They must
		 * then call `renderer.info.reset()` once per frame manually.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.autoReset = true;

		/**
		 * The current frame ID. This ID is managed
		 * by `NodeFrame`.
		 *
		 * @type {number}
		 * @readonly
		 * @default 0
		 */
		this.frame = 0;

		/**
		 * The number of render calls since the
		 * app has been started.
		 *
		 * @type {number}
		 * @readonly
		 * @default 0
		 */
		this.calls = 0;

		/**
		 * Render related metrics.
		 *
		 * @type {Object}
		 * @readonly
		 * @property {number} calls - The number of render calls since the app has been started.
		 * @property {number} frameCalls - The number of render calls of the current frame.
		 * @property {number} drawCalls - The number of draw calls of the current frame.
		 * @property {number} triangles - The number of rendered triangle primitives of the current frame.
		 * @property {number} points - The number of rendered point primitives of the current frame.
		 * @property {number} lines - The number of rendered line primitives of the current frame.
		 * @property {number} timestamp - The timestamp of the frame when using `renderer.renderAsync()`.
		 */
		this.render = {
			calls: 0,
			frameCalls: 0,
			drawCalls: 0,
			triangles: 0,
			points: 0,
			lines: 0,
			timestamp: 0,
		};

		/**
		 * Compute related metrics.
		 *
		 * @type {Object}
		 * @readonly
		 * @property {number} calls - The number of compute calls since the app has been started.
		 * @property {number} frameCalls - The number of compute calls of the current frame.
		 * @property {number} timestamp - The timestamp of the frame when using `renderer.computeAsync()`.
		 */
		this.compute = {
			calls: 0,
			frameCalls: 0,
			timestamp: 0
		};

		/**
		 * Memory related metrics.
		 *
		 * @type {Object}
		 * @readonly
		 * @property {number} geometries - The number of active geometries.
		 * @property {number} frameCalls - The number of active textures.
		 */
		this.memory = {
			geometries: 0,
			textures: 0
		};

	}

	/**
	 * This method should be executed per draw call and updates the corresponding metrics.
	 *
	 * @param {Object3D} object - The 3D object that is going to be rendered.
	 * @param {number} count - The vertex or index count.
	 * @param {number} instanceCount - The instance count.
	 */
	update( object, count, instanceCount ) {

		this.render.drawCalls ++;

		if ( object.isMesh || object.isSprite ) {

			this.render.triangles += instanceCount * ( count / 3 );

		} else if ( object.isPoints ) {

			this.render.points += instanceCount * count;

		} else if ( object.isLineSegments ) {

			this.render.lines += instanceCount * ( count / 2 );

		} else if ( object.isLine ) {

			this.render.lines += instanceCount * ( count - 1 );

		} else {

			console.error( 'THREE.WebGPUInfo: Unknown object type.' );

		}

	}

	/**
	 * Resets frame related metrics.
	 */
	reset() {

		this.render.drawCalls = 0;
		this.render.frameCalls = 0;
		this.compute.frameCalls = 0;

		this.render.triangles = 0;
		this.render.points = 0;
		this.render.lines = 0;


	}

	/**
	 * Performs a complete reset of the object.
	 */
	dispose() {

		this.reset();

		this.calls = 0;

		this.render.calls = 0;
		this.compute.calls = 0;

		this.render.timestamp = 0;
		this.compute.timestamp = 0;
		this.memory.geometries = 0;
		this.memory.textures = 0;

	}

}
```
</details>

#### Methods

##### `update(object: Object3D, count: number, instanceCount: number): void`

<details><summary>Code</summary>

```ts
update( object, count, instanceCount ) {

		this.render.drawCalls ++;

		if ( object.isMesh || object.isSprite ) {

			this.render.triangles += instanceCount * ( count / 3 );

		} else if ( object.isPoints ) {

			this.render.points += instanceCount * count;

		} else if ( object.isLineSegments ) {

			this.render.lines += instanceCount * ( count / 2 );

		} else if ( object.isLine ) {

			this.render.lines += instanceCount * ( count - 1 );

		} else {

			console.error( 'THREE.WebGPUInfo: Unknown object type.' );

		}

	}
```
</details>

##### `reset(): void`

<details><summary>Code</summary>

```ts
reset() {

		this.render.drawCalls = 0;
		this.render.frameCalls = 0;
		this.compute.frameCalls = 0;

		this.render.triangles = 0;
		this.render.points = 0;
		this.render.lines = 0;


	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.reset();

		this.calls = 0;

		this.render.calls = 0;
		this.compute.calls = 0;

		this.render.timestamp = 0;
		this.compute.timestamp = 0;
		this.memory.geometries = 0;
		this.memory.textures = 0;

	}
```
</details>


---