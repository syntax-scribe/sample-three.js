[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TexturePass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/TexturePass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ShaderMaterial` | `three` |
| `UniformsUtils` | `three` |
| `Pass` | `./Pass.js` |
| `FullScreenQuad` | `./Pass.js` |
| `CopyShader` | `../shaders/CopyShader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `shader` | `ShaderMaterial` | let/var | `CopyShader` | ✗ |
| `oldAutoClear` | `any` | let/var | `renderer.autoClear` | ✗ |


---

## Functions

### `TexturePass.render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget): void`

**JSDoc:**
```typescript
/**
	 * Performs the texture pass.
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
render( renderer, writeBuffer, readBuffer /*, deltaTime, maskActive */ ) {

		const oldAutoClear = renderer.autoClear;
		renderer.autoClear = false;

		this._fsQuad.material = this.material;

		this.uniforms[ 'opacity' ].value = this.opacity;
		this.uniforms[ 'tDiffuse' ].value = this.map;
		this.material.transparent = ( this.opacity < 1.0 );

		renderer.setRenderTarget( this.renderToScreen ? null : readBuffer );
		if ( this.clear ) renderer.clear();
		this._fsQuad.render( renderer );

		renderer.autoClear = oldAutoClear;

	}
```
</details>

### `TexturePass.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.material.dispose`
- `this._fsQuad.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.material.dispose();
		this._fsQuad.dispose();

	}
```
</details>


---

## Classes

### `TexturePass`

<details><summary>Class Code</summary>

```ts
class TexturePass extends Pass {

	/**
	 * Constructs a new texture pass.
	 *
	 * @param {Texture} map - The texture to render.
	 * @param {number} [opacity=1] - The opacity.
	 */
	constructor( map, opacity = 1 ) {

		super();

		const shader = CopyShader;

		/**
		 * The texture to render.
		 *
		 * @type {Texture}
		 */
		this.map = map;

		/**
		 * The opacity.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.opacity = opacity;

		/**
		 * Overwritten to disable the swap.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.needsSwap = false;

		/**
		 * The pass uniforms.
		 *
		 * @type {Object}
		 */
		this.uniforms = UniformsUtils.clone( shader.uniforms );

		/**
		 * The pass material.
		 *
		 * @type {ShaderMaterial}
		 */
		this.material = new ShaderMaterial( {

			uniforms: this.uniforms,
			vertexShader: shader.vertexShader,
			fragmentShader: shader.fragmentShader,
			depthTest: false,
			depthWrite: false,
			premultipliedAlpha: true

		} );

		// internals

		this._fsQuad = new FullScreenQuad( null );

	}

	/**
	 * Performs the texture pass.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {WebGLRenderTarget} writeBuffer - The write buffer. This buffer is intended as the rendering
	 * destination for the pass.
	 * @param {WebGLRenderTarget} readBuffer - The read buffer. The pass can access the result from the
	 * previous pass from this buffer.
	 * @param {number} deltaTime - The delta time in seconds.
	 * @param {boolean} maskActive - Whether masking is active or not.
	 */
	render( renderer, writeBuffer, readBuffer /*, deltaTime, maskActive */ ) {

		const oldAutoClear = renderer.autoClear;
		renderer.autoClear = false;

		this._fsQuad.material = this.material;

		this.uniforms[ 'opacity' ].value = this.opacity;
		this.uniforms[ 'tDiffuse' ].value = this.map;
		this.material.transparent = ( this.opacity < 1.0 );

		renderer.setRenderTarget( this.renderToScreen ? null : readBuffer );
		if ( this.clear ) renderer.clear();
		this._fsQuad.render( renderer );

		renderer.autoClear = oldAutoClear;

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
	dispose() {

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
render( renderer, writeBuffer, readBuffer /*, deltaTime, maskActive */ ) {

		const oldAutoClear = renderer.autoClear;
		renderer.autoClear = false;

		this._fsQuad.material = this.material;

		this.uniforms[ 'opacity' ].value = this.opacity;
		this.uniforms[ 'tDiffuse' ].value = this.map;
		this.material.transparent = ( this.opacity < 1.0 );

		renderer.setRenderTarget( this.renderToScreen ? null : readBuffer );
		if ( this.clear ) renderer.clear();
		this._fsQuad.render( renderer );

		renderer.autoClear = oldAutoClear;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.material.dispose();
		this._fsQuad.dispose();

	}
```
</details>


---