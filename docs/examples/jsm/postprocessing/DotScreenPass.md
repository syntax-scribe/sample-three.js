[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `DotScreenPass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/DotScreenPass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ShaderMaterial` | `three` |
| `UniformsUtils` | `three` |
| `Pass` | `./Pass.js` |
| `FullScreenQuad` | `./Pass.js` |
| `DotScreenShader` | `../shaders/DotScreenShader.js` |


---

## Functions

### `DotScreenPass.render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget): void`

**JSDoc:**
```typescript
/**
	 * Performs the dot screen pass.
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

- `this.uniforms[ 'tSize' ].value.set`
- `renderer.setRenderTarget`
- `this._fsQuad.render`
- `renderer.clear`

<details><summary>Code</summary>

```typescript
render( renderer, writeBuffer, readBuffer /*, deltaTime, maskActive */ ) {

		this.uniforms[ 'tDiffuse' ].value = readBuffer.texture;
		this.uniforms[ 'tSize' ].value.set( readBuffer.width, readBuffer.height );

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );
			this._fsQuad.render( renderer );

		} else {

			renderer.setRenderTarget( writeBuffer );
			if ( this.clear ) renderer.clear();
			this._fsQuad.render( renderer );

		}

	}
```
</details>

### `DotScreenPass.dispose(): void`

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

### `DotScreenPass`

<details><summary>Class Code</summary>

```ts
class DotScreenPass extends Pass {

	/**
	 * Constructs a new dot screen pass.
	 *
	 * @param {Vector2} center - The center point.
	 * @param {number} angle - The rotation of the effect in radians.
	 * @param {number} scale - The scale of the effect. A higher value means smaller dots.
	 */
	constructor( center, angle, scale ) {

		super();

		/**
		 * The pass uniforms. Use this object if you want to update the
		 * `center`, `angle` or `scale` values at runtime.
		 * ```js
		 * pass.uniforms.center.value.copy( center );
		 * pass.uniforms.angle.value = 0;
		 * pass.uniforms.scale.value = 0.5;
		 * ```
		 *
		 * @type {Object}
		 */
		this.uniforms = UniformsUtils.clone( DotScreenShader.uniforms );

		if ( center !== undefined ) this.uniforms[ 'center' ].value.copy( center );
		if ( angle !== undefined ) this.uniforms[ 'angle' ].value = angle;
		if ( scale !== undefined ) this.uniforms[ 'scale' ].value = scale;

		/**
		 * The pass material.
		 *
		 * @type {ShaderMaterial}
		 */
		this.material = new ShaderMaterial( {

			name: DotScreenShader.name,
			uniforms: this.uniforms,
			vertexShader: DotScreenShader.vertexShader,
			fragmentShader: DotScreenShader.fragmentShader

		} );

		// internals

		this._fsQuad = new FullScreenQuad( this.material );

	}

	/**
	 * Performs the dot screen pass.
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

		this.uniforms[ 'tDiffuse' ].value = readBuffer.texture;
		this.uniforms[ 'tSize' ].value.set( readBuffer.width, readBuffer.height );

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );
			this._fsQuad.render( renderer );

		} else {

			renderer.setRenderTarget( writeBuffer );
			if ( this.clear ) renderer.clear();
			this._fsQuad.render( renderer );

		}

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

		this.uniforms[ 'tDiffuse' ].value = readBuffer.texture;
		this.uniforms[ 'tSize' ].value.set( readBuffer.width, readBuffer.height );

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );
			this._fsQuad.render( renderer );

		} else {

			renderer.setRenderTarget( writeBuffer );
			if ( this.clear ) renderer.clear();
			this._fsQuad.render( renderer );

		}

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