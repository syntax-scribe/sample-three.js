[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BokehPass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 12 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/BokehPass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `three` |
| `HalfFloatType` | `three` |
| `MeshDepthMaterial` | `three` |
| `NearestFilter` | `three` |
| `NoBlending` | `three` |
| `RGBADepthPacking` | `three` |
| `ShaderMaterial` | `three` |
| `UniformsUtils` | `three` |
| `WebGLRenderTarget` | `three` |
| `Pass` | `./Pass.js` |
| `FullScreenQuad` | `./Pass.js` |
| `BokehShader` | `../shaders/BokehShader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `focus` | `any` | let/var | `( params.focus !== undefined ) ? params.focus : 1.0` | ✗ |
| `aperture` | `any` | let/var | `( params.aperture !== undefined ) ? params.aperture : 0.025` | ✗ |
| `maxblur` | `any` | let/var | `( params.maxblur !== undefined ) ? params.maxblur : 1.0` | ✗ |
| `oldAutoClear` | `any` | let/var | `renderer.autoClear` | ✗ |


---

## Functions

### `BokehPass.render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget): void`

**JSDoc:**
```typescript
/**
	 * Performs the Bokeh pass.
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

- `renderer.getClearColor`
- `renderer.getClearAlpha`
- `renderer.setClearColor`
- `renderer.setClearAlpha`
- `renderer.setRenderTarget`
- `renderer.clear`
- `renderer.render`
- `this._fsQuad.render`

**Internal Comments:**
```
// Render depth into texture (x5)
// Render bokeh composite (x6)
```

<details><summary>Code</summary>

```typescript
render( renderer, writeBuffer, readBuffer/*, deltaTime, maskActive*/ ) {

		// Render depth into texture

		this.scene.overrideMaterial = this._materialDepth;

		renderer.getClearColor( this._oldClearColor );
		const oldClearAlpha = renderer.getClearAlpha();
		const oldAutoClear = renderer.autoClear;
		renderer.autoClear = false;

		renderer.setClearColor( 0xffffff );
		renderer.setClearAlpha( 1.0 );
		renderer.setRenderTarget( this._renderTargetDepth );
		renderer.clear();
		renderer.render( this.scene, this.camera );

		// Render bokeh composite

		this.uniforms[ 'tColor' ].value = readBuffer.texture;
		this.uniforms[ 'nearClip' ].value = this.camera.near;
		this.uniforms[ 'farClip' ].value = this.camera.far;

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );
			this._fsQuad.render( renderer );

		} else {

			renderer.setRenderTarget( writeBuffer );
			renderer.clear();
			this._fsQuad.render( renderer );

		}

		this.scene.overrideMaterial = null;
		renderer.setClearColor( this._oldClearColor );
		renderer.setClearAlpha( oldClearAlpha );
		renderer.autoClear = oldAutoClear;

	}
```
</details>

### `BokehPass.setSize(width: number, height: number): void`

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

- `this._renderTargetDepth.setSize`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this.materialBokeh.uniforms[ 'aspect' ].value = width / height;

		this._renderTargetDepth.setSize( width, height );

	}
```
</details>

### `BokehPass.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this._renderTargetDepth.dispose`
- `this._materialDepth.dispose`
- `this.materialBokeh.dispose`
- `this._fsQuad.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this._renderTargetDepth.dispose();

		this._materialDepth.dispose();
		this.materialBokeh.dispose();

		this._fsQuad.dispose();

	}
```
</details>


---

## Classes

### `BokehPass`

<details><summary>Class Code</summary>

```ts
class BokehPass extends Pass {

	/**
	 * Constructs a new Bokeh pass.
	 *
	 * @param {Scene} scene - The scene to render the DOF for.
	 * @param {Camera} camera - The camera.
	 * @param {BokehPass~Options} params - The pass options.
	 */
	constructor( scene, camera, params ) {

		super();

		/**
		 * The scene to render the DOF for.
		 *
		 * @type {Scene}
		 */
		this.scene = scene;

		/**
		 * The camera.
		 *
		 * @type {Camera}
		 */
		this.camera = camera;

		const focus = ( params.focus !== undefined ) ? params.focus : 1.0;
		const aperture = ( params.aperture !== undefined ) ? params.aperture : 0.025;
		const maxblur = ( params.maxblur !== undefined ) ? params.maxblur : 1.0;

		// render targets

		this._renderTargetDepth = new WebGLRenderTarget( 1, 1, { // will be resized later
			minFilter: NearestFilter,
			magFilter: NearestFilter,
			type: HalfFloatType
		} );

		this._renderTargetDepth.texture.name = 'BokehPass.depth';

		// depth material

		this._materialDepth = new MeshDepthMaterial();
		this._materialDepth.depthPacking = RGBADepthPacking;
		this._materialDepth.blending = NoBlending;

		// bokeh material

		const bokehUniforms = UniformsUtils.clone( BokehShader.uniforms );

		bokehUniforms[ 'tDepth' ].value = this._renderTargetDepth.texture;

		bokehUniforms[ 'focus' ].value = focus;
		bokehUniforms[ 'aspect' ].value = camera.aspect;
		bokehUniforms[ 'aperture' ].value = aperture;
		bokehUniforms[ 'maxblur' ].value = maxblur;
		bokehUniforms[ 'nearClip' ].value = camera.near;
		bokehUniforms[ 'farClip' ].value = camera.far;

		/**
		 * The pass bokeh material.
		 *
		 * @type {ShaderMaterial}
		 */
		this.materialBokeh = new ShaderMaterial( {
			defines: Object.assign( {}, BokehShader.defines ),
			uniforms: bokehUniforms,
			vertexShader: BokehShader.vertexShader,
			fragmentShader: BokehShader.fragmentShader
		} );

		/**
		 * The pass uniforms.  Use this object if you want to update the
		 * `focus`, `aperture` or `maxblur` values at runtime.
		 *
		 * ```js
		 * pass.uniforms.focus.value = focus;
		 * pass.uniforms.aperture.value = aperture;
		 * pass.uniforms.maxblur.value = maxblur;
		 * ```
		 *
		 * @type {Object}
		 */
		this.uniforms = bokehUniforms;

		// internals

		this._fsQuad = new FullScreenQuad( this.materialBokeh );

		this._oldClearColor = new Color();

	}

	/**
	 * Performs the Bokeh pass.
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

		// Render depth into texture

		this.scene.overrideMaterial = this._materialDepth;

		renderer.getClearColor( this._oldClearColor );
		const oldClearAlpha = renderer.getClearAlpha();
		const oldAutoClear = renderer.autoClear;
		renderer.autoClear = false;

		renderer.setClearColor( 0xffffff );
		renderer.setClearAlpha( 1.0 );
		renderer.setRenderTarget( this._renderTargetDepth );
		renderer.clear();
		renderer.render( this.scene, this.camera );

		// Render bokeh composite

		this.uniforms[ 'tColor' ].value = readBuffer.texture;
		this.uniforms[ 'nearClip' ].value = this.camera.near;
		this.uniforms[ 'farClip' ].value = this.camera.far;

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );
			this._fsQuad.render( renderer );

		} else {

			renderer.setRenderTarget( writeBuffer );
			renderer.clear();
			this._fsQuad.render( renderer );

		}

		this.scene.overrideMaterial = null;
		renderer.setClearColor( this._oldClearColor );
		renderer.setClearAlpha( oldClearAlpha );
		renderer.autoClear = oldAutoClear;

	}

	/**
	 * Sets the size of the pass.
	 *
	 * @param {number} width - The width to set.
	 * @param {number} height - The height to set.
	 */
	setSize( width, height ) {

		this.materialBokeh.uniforms[ 'aspect' ].value = width / height;

		this._renderTargetDepth.setSize( width, height );

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
	dispose() {

		this._renderTargetDepth.dispose();

		this._materialDepth.dispose();
		this.materialBokeh.dispose();

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

		// Render depth into texture

		this.scene.overrideMaterial = this._materialDepth;

		renderer.getClearColor( this._oldClearColor );
		const oldClearAlpha = renderer.getClearAlpha();
		const oldAutoClear = renderer.autoClear;
		renderer.autoClear = false;

		renderer.setClearColor( 0xffffff );
		renderer.setClearAlpha( 1.0 );
		renderer.setRenderTarget( this._renderTargetDepth );
		renderer.clear();
		renderer.render( this.scene, this.camera );

		// Render bokeh composite

		this.uniforms[ 'tColor' ].value = readBuffer.texture;
		this.uniforms[ 'nearClip' ].value = this.camera.near;
		this.uniforms[ 'farClip' ].value = this.camera.far;

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );
			this._fsQuad.render( renderer );

		} else {

			renderer.setRenderTarget( writeBuffer );
			renderer.clear();
			this._fsQuad.render( renderer );

		}

		this.scene.overrideMaterial = null;
		renderer.setClearColor( this._oldClearColor );
		renderer.setClearAlpha( oldClearAlpha );
		renderer.autoClear = oldAutoClear;

	}
```
</details>

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		this.materialBokeh.uniforms[ 'aspect' ].value = width / height;

		this._renderTargetDepth.setSize( width, height );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this._renderTargetDepth.dispose();

		this._materialDepth.dispose();
		this.materialBokeh.dispose();

		this._fsQuad.dispose();

	}
```
</details>


---