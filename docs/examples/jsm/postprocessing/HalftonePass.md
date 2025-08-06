[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `HalftonePass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/HalftonePass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ShaderMaterial` | `three` |
| `UniformsUtils` | `three` |
| `Pass` | `./Pass.js` |
| `FullScreenQuad` | `./Pass.js` |
| `HalftoneShader` | `../shaders/HalftoneShader.js` |


---

## Functions

### `HalftonePass.render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget): void`

**JSDoc:**
```typescript
/**
	 * Performs the halftone pass.
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
- `this._fsQuad.render`
- `renderer.clear`

<details><summary>Code</summary>

```typescript
render( renderer, writeBuffer, readBuffer/*, deltaTime, maskActive*/ ) {

 		this.material.uniforms[ 'tDiffuse' ].value = readBuffer.texture;

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

### `HalftonePass.setSize(width: number, height: number): void`

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

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

 		this.uniforms.width.value = width;
 		this.uniforms.height.value = height;

 	}
```
</details>

### `HalftonePass.dispose(): void`

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

### `HalftonePass`

<details><summary>Class Code</summary>

```ts
class HalftonePass extends Pass {

	/**
	 * Constructs a new halftone pass.
	 *
	 * @param {Object} params - The halftone shader parameter.
	 */
	constructor( params ) {

		super();

		/**
		 * The pass uniforms.
		 *
		 * @type {Object}
		 */
	 	this.uniforms = UniformsUtils.clone( HalftoneShader.uniforms );

		/**
		 * The pass material.
		 *
		 * @type {ShaderMaterial}
		 */
	 	this.material = new ShaderMaterial( {
	 		uniforms: this.uniforms,
	 		fragmentShader: HalftoneShader.fragmentShader,
	 		vertexShader: HalftoneShader.vertexShader
	 	} );


		for ( const key in params ) {

			if ( params.hasOwnProperty( key ) && this.uniforms.hasOwnProperty( key ) ) {

				this.uniforms[ key ].value = params[ key ];

			}

		}

		// internals

		this._fsQuad = new FullScreenQuad( this.material );

	}

	/**
	 * Performs the halftone pass.
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

 		this.material.uniforms[ 'tDiffuse' ].value = readBuffer.texture;

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
	 * Sets the size of the pass.
	 *
	 * @param {number} width - The width to set.
	 * @param {number} height - The height to set.
	 */
 	setSize( width, height ) {

 		this.uniforms.width.value = width;
 		this.uniforms.height.value = height;

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
render( renderer, writeBuffer, readBuffer/*, deltaTime, maskActive*/ ) {

 		this.material.uniforms[ 'tDiffuse' ].value = readBuffer.texture;

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

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

 		this.uniforms.width.value = width;
 		this.uniforms.height.value = height;

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