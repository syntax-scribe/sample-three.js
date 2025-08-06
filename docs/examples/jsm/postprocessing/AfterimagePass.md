[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `AfterimagePass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/AfterimagePass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `HalfFloatType` | `three` |
| `NearestFilter` | `three` |
| `NoBlending` | `three` |
| `ShaderMaterial` | `three` |
| `UniformsUtils` | `three` |
| `WebGLRenderTarget` | `three` |
| `Pass` | `./Pass.js` |
| `FullScreenQuad` | `./Pass.js` |
| `CopyShader` | `../shaders/CopyShader.js` |
| `AfterimageShader` | `../shaders/AfterimageShader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `temp` | `any` | let/var | `this._textureOld` | ✗ |


---

## Functions

### `AfterimagePass.render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget): void`

**JSDoc:**
```typescript
/**
	 * Performs the after image pass.
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
- `this._compFsQuad.render`
- `this._copyFsQuad.render`
- `renderer.clear`

**Internal Comments:**
```
// Swap buffers. (x2)
```

<details><summary>Code</summary>

```typescript
render( renderer, writeBuffer, readBuffer/*, deltaTime, maskActive*/ ) {

		this.uniforms[ 'tOld' ].value = this._textureOld.texture;
		this.uniforms[ 'tNew' ].value = readBuffer.texture;

		renderer.setRenderTarget( this._textureComp );
		this._compFsQuad.render( renderer );

		this._copyFsQuad.material.uniforms.tDiffuse.value = this._textureComp.texture;

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );
			this._copyFsQuad.render( renderer );

		} else {

			renderer.setRenderTarget( writeBuffer );

			if ( this.clear ) renderer.clear();

			this._copyFsQuad.render( renderer );

		}

		// Swap buffers.
		const temp = this._textureOld;
		this._textureOld = this._textureComp;
		this._textureComp = temp;
		// Now textureOld contains the latest image, ready for the next frame.

	}
```
</details>

### `AfterimagePass.setSize(width: number, height: number): void`

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

- `this._textureComp.setSize`
- `this._textureOld.setSize`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this._textureComp.setSize( width, height );
		this._textureOld.setSize( width, height );

	}
```
</details>

### `AfterimagePass.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this._textureComp.dispose`
- `this._textureOld.dispose`
- `this.compFsMaterial.dispose`
- `this.copyFsMaterial.dispose`
- `this._compFsQuad.dispose`
- `this._copyFsQuad.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this._textureComp.dispose();
		this._textureOld.dispose();

		this.compFsMaterial.dispose();
		this.copyFsMaterial.dispose();

		this._compFsQuad.dispose();
		this._copyFsQuad.dispose();

	}
```
</details>


---

## Classes

### `AfterimagePass`

<details><summary>Class Code</summary>

```ts
class AfterimagePass extends Pass {

	/**
	 * Constructs a new after image pass.
	 *
	 * @param {number} [damp=0.96] - The damping intensity. A higher value means a stronger after image effect.
	 */
	constructor( damp = 0.96 ) {

		super();

		/**
		 * The pass uniforms. Use this object if you want to update the
		 * `damp` value at runtime.
		 * ```js
		 * pass.uniforms.damp.value = 0.9;
		 * ```
		 *
		 * @type {Object}
		 */
		this.uniforms = UniformsUtils.clone( AfterimageShader.uniforms );

		this.damp = damp;

		/**
		 * The composition material.
		 *
		 * @type {ShaderMaterial}
		 */
		this.compFsMaterial = new ShaderMaterial( {

			uniforms: this.uniforms,
			vertexShader: AfterimageShader.vertexShader,
			fragmentShader: AfterimageShader.fragmentShader

		} );

		/**
		 * The copy material.
		 *
		 * @type {ShaderMaterial}
		 */
		this.copyFsMaterial = new ShaderMaterial( {
			uniforms: UniformsUtils.clone( CopyShader.uniforms ),
			vertexShader: CopyShader.vertexShader,
			fragmentShader: CopyShader.fragmentShader,
			blending: NoBlending,
			depthTest: false,
			depthWrite: false
		} );

		// internals

		this._textureComp = new WebGLRenderTarget( window.innerWidth, window.innerHeight, {
			magFilter: NearestFilter,
			type: HalfFloatType
		} );

		this._textureOld = new WebGLRenderTarget( window.innerWidth, window.innerHeight, {
			magFilter: NearestFilter,
			type: HalfFloatType
		} );

		this._compFsQuad = new FullScreenQuad( this.compFsMaterial );
		this._copyFsQuad = new FullScreenQuad( this.copyFsMaterial );

	}

	/**
	 * The damping intensity, from 0.0 to 1.0. A higher value means a stronger after image effect.
	 *
	 * @type {number}
	 */
	get damp() {

		return this.uniforms[ 'damp' ].value;

	}

	set damp( value ) {

		this.uniforms[ 'damp' ].value = value;

	}

	/**
	 * Performs the after image pass.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {WebGLRenderTarget} writeBuffer - The write buffer. This buffer is intended as the rendering
	 * destination for the pass.
	 * @param {WebGLRenderTarget} readBuffer - The read buffer. The pass can access the result from the
	 * previous pass from this buffer.
	 * @param {number} deltaTime - The delta time in seconds.
	 * @param {boolean} maskActive - Whether masking is active or not.
	 */
	render( renderer, writeBuffer, readBuffer/*, deltaTime, maskActive*/ ) {

		this.uniforms[ 'tOld' ].value = this._textureOld.texture;
		this.uniforms[ 'tNew' ].value = readBuffer.texture;

		renderer.setRenderTarget( this._textureComp );
		this._compFsQuad.render( renderer );

		this._copyFsQuad.material.uniforms.tDiffuse.value = this._textureComp.texture;

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );
			this._copyFsQuad.render( renderer );

		} else {

			renderer.setRenderTarget( writeBuffer );

			if ( this.clear ) renderer.clear();

			this._copyFsQuad.render( renderer );

		}

		// Swap buffers.
		const temp = this._textureOld;
		this._textureOld = this._textureComp;
		this._textureComp = temp;
		// Now textureOld contains the latest image, ready for the next frame.

	}

	/**
	 * Sets the size of the pass.
	 *
	 * @param {number} width - The width to set.
	 * @param {number} height - The height to set.
	 */
	setSize( width, height ) {

		this._textureComp.setSize( width, height );
		this._textureOld.setSize( width, height );

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
	dispose() {

		this._textureComp.dispose();
		this._textureOld.dispose();

		this.compFsMaterial.dispose();
		this.copyFsMaterial.dispose();

		this._compFsQuad.dispose();
		this._copyFsQuad.dispose();

	}

}
```
</details>

#### Methods

##### `render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget): void`

<details><summary>Code</summary>

```ts
render( renderer, writeBuffer, readBuffer/*, deltaTime, maskActive*/ ) {

		this.uniforms[ 'tOld' ].value = this._textureOld.texture;
		this.uniforms[ 'tNew' ].value = readBuffer.texture;

		renderer.setRenderTarget( this._textureComp );
		this._compFsQuad.render( renderer );

		this._copyFsQuad.material.uniforms.tDiffuse.value = this._textureComp.texture;

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );
			this._copyFsQuad.render( renderer );

		} else {

			renderer.setRenderTarget( writeBuffer );

			if ( this.clear ) renderer.clear();

			this._copyFsQuad.render( renderer );

		}

		// Swap buffers.
		const temp = this._textureOld;
		this._textureOld = this._textureComp;
		this._textureComp = temp;
		// Now textureOld contains the latest image, ready for the next frame.

	}
```
</details>

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		this._textureComp.setSize( width, height );
		this._textureOld.setSize( width, height );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this._textureComp.dispose();
		this._textureOld.dispose();

		this.compFsMaterial.dispose();
		this.copyFsMaterial.dispose();

		this._compFsQuad.dispose();
		this._copyFsQuad.dispose();

	}
```
</details>


---