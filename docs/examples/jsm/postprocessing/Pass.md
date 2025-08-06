[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Pass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 3 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/Pass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `three` |
| `Float32BufferAttribute` | `three` |
| `OrthographicCamera` | `three` |
| `Mesh` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_camera` | `any` | let/var | `new OrthographicCamera( - 1, 1, 1, - 1, 0, 1 )` | ✗ |
| `_geometry` | `FullscreenTriangleGeometry` | let/var | `new FullscreenTriangleGeometry()` | ✗ |


---

## Functions

### `Pass.setSize(): void`

**JSDoc:**
```typescript
/**
	 * Sets the size of the pass.
	 *
	 * @abstract
	 * @param {number} width - The width to set.
	 * @param {number} height - The height to set.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setSize( /* width, height */ ) {}
```
</details>

### `Pass.render(): void`

**JSDoc:**
```typescript
/**
	 * This method holds the render logic of a pass. It must be implemented in all derived classes.
	 *
	 * @abstract
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {WebGLRenderTarget} writeBuffer - The write buffer. This buffer is intended as the rendering
	 * destination for the pass.
	 * @param {WebGLRenderTarget} readBuffer - The read buffer. The pass can access the result from the
	 * previous pass from this buffer.
	 * @param {number} deltaTime - The delta time in seconds.
	 * @param {boolean} maskActive - Whether masking is active or not.
	 */
```

**Returns:** `void`

**Calls:**

- `console.error`

<details><summary>Code</summary>

```typescript
render( /* renderer, writeBuffer, readBuffer, deltaTime, maskActive */ ) {

		console.error( 'THREE.Pass: .render() must be implemented in derived pass.' );

	}
```
</details>

### `Pass.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
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

### `FullScreenQuad.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this._mesh.geometry.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this._mesh.geometry.dispose();

	}
```
</details>

### `FullScreenQuad.render(renderer: WebGLRenderer): void`

**JSDoc:**
```typescript
/**
	 * Renders the full screen quad.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 */
```

**Parameters:**

- **`renderer`** `WebGLRenderer`

**Returns:** `void`

**Calls:**

- `renderer.render`

<details><summary>Code</summary>

```typescript
render( renderer ) {

		renderer.render( this._mesh, _camera );

	}
```
</details>


---

## Classes

### `Pass`

<details><summary>Class Code</summary>

```ts
class Pass {

	/**
	 * Constructs a new pass.
	 */
	constructor() {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isPass = true;

		/**
		 * If set to `true`, the pass is processed by the composer.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.enabled = true;

		/**
		 * If set to `true`, the pass indicates to swap read and write buffer after rendering.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.needsSwap = true;

		/**
		 * If set to `true`, the pass clears its buffer before rendering
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.clear = false;

		/**
		 * If set to `true`, the result of the pass is rendered to screen. The last pass in the composers
		 * pass chain gets automatically rendered to screen, no matter how this property is configured.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.renderToScreen = false;

	}

	/**
	 * Sets the size of the pass.
	 *
	 * @abstract
	 * @param {number} width - The width to set.
	 * @param {number} height - The height to set.
	 */
	setSize( /* width, height */ ) {}

	/**
	 * This method holds the render logic of a pass. It must be implemented in all derived classes.
	 *
	 * @abstract
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {WebGLRenderTarget} writeBuffer - The write buffer. This buffer is intended as the rendering
	 * destination for the pass.
	 * @param {WebGLRenderTarget} readBuffer - The read buffer. The pass can access the result from the
	 * previous pass from this buffer.
	 * @param {number} deltaTime - The delta time in seconds.
	 * @param {boolean} maskActive - Whether masking is active or not.
	 */
	render( /* renderer, writeBuffer, readBuffer, deltaTime, maskActive */ ) {

		console.error( 'THREE.Pass: .render() must be implemented in derived pass.' );

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 *
	 * @abstract
	 */
	dispose() {}

}
```
</details>

#### Methods

##### `setSize(): void`

<details><summary>Code</summary>

```ts
setSize( /* width, height */ ) {}
```
</details>

##### `render(): void`

<details><summary>Code</summary>

```ts
render( /* renderer, writeBuffer, readBuffer, deltaTime, maskActive */ ) {

		console.error( 'THREE.Pass: .render() must be implemented in derived pass.' );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {}
```
</details>

### `FullscreenTriangleGeometry`

<details><summary>Class Code</summary>

```ts
class FullscreenTriangleGeometry extends BufferGeometry {

	constructor() {

		super();

		this.setAttribute( 'position', new Float32BufferAttribute( [ - 1, 3, 0, - 1, - 1, 0, 3, - 1, 0 ], 3 ) );
		this.setAttribute( 'uv', new Float32BufferAttribute( [ 0, 2, 0, 0, 2, 0 ], 2 ) );

	}

}
```
</details>

### `FullScreenQuad`

<details><summary>Class Code</summary>

```ts
class FullScreenQuad {

	/**
	 * Constructs a new full screen quad.
	 *
	 * @param {?Material} material - The material to render te full screen quad with.
	 */
	constructor( material ) {

		this._mesh = new Mesh( _geometry, material );

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the instance is no longer used in your app.
	 */
	dispose() {

		this._mesh.geometry.dispose();

	}

	/**
	 * Renders the full screen quad.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 */
	render( renderer ) {

		renderer.render( this._mesh, _camera );

	}

	/**
	 * The quad's material.
	 *
	 * @type {?Material}
	 */
	get material() {

		return this._mesh.material;

	}

	set material( value ) {

		this._mesh.material = value;

	}

}
```
</details>

#### Methods

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this._mesh.geometry.dispose();

	}
```
</details>

##### `render(renderer: WebGLRenderer): void`

<details><summary>Code</summary>

```ts
render( renderer ) {

		renderer.render( this._mesh, _camera );

	}
```
</details>


---