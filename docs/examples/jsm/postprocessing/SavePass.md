[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SavePass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/SavePass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `HalfFloatType` | `three` |
| `NoBlending` | `three` |
| `ShaderMaterial` | `three` |
| `UniformsUtils` | `three` |
| `WebGLRenderTarget` | `three` |
| `Pass` | `./Pass.js` |
| `FullScreenQuad` | `./Pass.js` |
| `CopyShader` | `../shaders/CopyShader.js` |


---

## Functions

### `SavePass.render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget): void`

**JSDoc:**
```typescript
/**
	 * Performs the save pass.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {WebGLRenderTarget} writeBuffer - The write buffer. This buffer is intended as the rendering
	 * destination for the pass.
	 * @param {WebGLRenderTarget} readBuffer - The read buffer. The pass can access the result from the
	 * previous pass from this buffer.
	 * @param {number} deltaTime - The delta time in seconds.
	 * @param {boolean} maskActive - Whether masking is active or not.
	 */
```

**Parameters:**

- **`renderer`** `WebGLRenderer`
- **`writeBuffer`** `WebGLRenderTarget`
- **`readBuffer`** `WebGLRenderTarget`

**Returns:** `void`

**Calls:**

- `renderer.setRenderTarget`
- `renderer.clear`
- `this._fsQuad.render`

<details><summary>Code</summary>

```typescript
render( renderer, writeBuffer, readBuffer/*, deltaTime, maskActive */ ) {

		this.uniforms[ 'tDiffuse' ].value = readBuffer.texture;

		renderer.setRenderTarget( this.renderTarget );
		if ( this.clear ) renderer.clear();
		this._fsQuad.render( renderer );

	}
```
</details>

### `SavePass.setSize(width: number, height: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the size of the pass.
	 *
	 * @param {number} width - The width to set.
	 * @param {number} height - The height to set.
	 */
```

**Parameters:**

- **`width`** `number`
- **`height`** `number`

**Returns:** `void`

**Calls:**

- `this.renderTarget.setSize`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this.renderTarget.setSize( width, height );

	}
```
</details>

### `SavePass.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.renderTarget.dispose`
- `this.material.dispose`
- `this._fsQuad.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.renderTarget.dispose();

		this.material.dispose();

		this._fsQuad.dispose();

	}
```
</details>


---

## Classes

### `SavePass`

<details><summary>Class Code</summary>

```ts
class SavePass extends Pass {

	/**
	 * Constructs a new save pass.
	 *
	 * @param {WebGLRenderTarget} [renderTarget] - The render target for saving the read buffer.
	 * If not provided, the pass automatically creates a render target.
	 */
	constructor( renderTarget ) {

		super();

		/**
		 * The pass uniforms.
		 *
		 * @type {Object}
		 */
		this.uniforms = UniformsUtils.clone( CopyShader.uniforms );

		/**
		 * The pass material.
		 *
		 * @type {ShaderMaterial}
		 */
		this.material = new ShaderMaterial( {

			uniforms: this.uniforms,
			vertexShader: CopyShader.vertexShader,
			fragmentShader: CopyShader.fragmentShader,
			blending: NoBlending

		} );

		/**
		 * The render target which is used to save the read buffer.
		 *
		 * @type {WebGLRenderTarget}
		 */
		this.renderTarget = renderTarget;

		if ( this.renderTarget === undefined ) {

			this.renderTarget = new WebGLRenderTarget( 1, 1, { type: HalfFloatType } ); // will be resized later
			this.renderTarget.texture.name = 'SavePass.rt';

		}

		/**
		 * Overwritten to disable the swap.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.needsSwap = false;

		// internals

		this._fsQuad = new FullScreenQuad( this.material );

	}

	/**
	 * Performs the save pass.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {WebGLRenderTarget} writeBuffer - The write buffer. This buffer is intended as the rendering
	 * destination for the pass.
	 * @param {WebGLRenderTarget} readBuffer - The read buffer. The pass can access the result from the
	 * previous pass from this buffer.
	 * @param {number} deltaTime - The delta time in seconds.
	 * @param {boolean} maskActive - Whether masking is active or not.
	 */
	render( renderer, writeBuffer, readBuffer/*, deltaTime, maskActive */ ) {

		this.uniforms[ 'tDiffuse' ].value = readBuffer.texture;

		renderer.setRenderTarget( this.renderTarget );
		if ( this.clear ) renderer.clear();
		this._fsQuad.render( renderer );

	}

	/**
	 * Sets the size of the pass.
	 *
	 * @param {number} width - The width to set.
	 * @param {number} height - The height to set.
	 */
	setSize( width, height ) {

		this.renderTarget.setSize( width, height );

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
	dispose() {

		this.renderTarget.dispose();

		this.material.dispose();

		this._fsQuad.dispose();

	}

}
```
</details>

#### Methods

##### `render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget): void`

<details><summary>Code</summary>

```ts
render( renderer, writeBuffer, readBuffer/*, deltaTime, maskActive */ ) {

		this.uniforms[ 'tDiffuse' ].value = readBuffer.texture;

		renderer.setRenderTarget( this.renderTarget );
		if ( this.clear ) renderer.clear();
		this._fsQuad.render( renderer );

	}
```
</details>

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		this.renderTarget.setSize( width, height );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.renderTarget.dispose();

		this.material.dispose();

		this._fsQuad.dispose();

	}
```
</details>


---