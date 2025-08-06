[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CubeTexturePass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/CubeTexturePass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BackSide` | `three` |
| `BoxGeometry` | `three` |
| `Mesh` | `three` |
| `PerspectiveCamera` | `three` |
| `Scene` | `three` |
| `ShaderLib` | `three` |
| `ShaderMaterial` | `three` |
| `UniformsUtils` | `three` |
| `Pass` | `./Pass.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `cubeShader` | `any` | let/var | `ShaderLib[ 'cube' ]` | ✗ |
| `oldAutoClear` | `any` | let/var | `renderer.autoClear` | ✗ |


---

## Functions

### `CubeTexturePass.render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget): void`

**JSDoc:**
```typescript
/**
	 * Performs the cube texture pass.
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

- `this._cubeCamera.projectionMatrix.copy`
- `this._cubeCamera.quaternion.setFromRotationMatrix`
- `renderer.setRenderTarget`
- `renderer.clear`
- `renderer.render`

<details><summary>Code</summary>

```typescript
render( renderer, writeBuffer, readBuffer/*, deltaTime, maskActive*/ ) {

		const oldAutoClear = renderer.autoClear;
		renderer.autoClear = false;

		this._cubeCamera.projectionMatrix.copy( this.camera.projectionMatrix );
		this._cubeCamera.quaternion.setFromRotationMatrix( this.camera.matrixWorld );

		this._cubeMesh.material.uniforms.tCube.value = this.tCube;
		this._cubeMesh.material.uniforms.tFlip.value = ( this.tCube.isCubeTexture && this.tCube.isRenderTargetTexture === false ) ? - 1 : 1;
		this._cubeMesh.material.uniforms.opacity.value = this.opacity;
		this._cubeMesh.material.transparent = ( this.opacity < 1.0 );

		renderer.setRenderTarget( this.renderToScreen ? null : readBuffer );
		if ( this.clear ) renderer.clear();
		renderer.render( this._cubeScene, this._cubeCamera );

		renderer.autoClear = oldAutoClear;

	}
```
</details>

### `CubeTexturePass.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this._cubeMesh.geometry.dispose`
- `this._cubeMesh.material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this._cubeMesh.geometry.dispose();
		this._cubeMesh.material.dispose();

	}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

				return this.uniforms.tCube.value;

			}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

				return this.uniforms.tCube.value;

			}
```
</details>


---

## Classes

### `CubeTexturePass`

<details><summary>Class Code</summary>

```ts
class CubeTexturePass extends Pass {

	/**
	 * Constructs a new cube texture pass.
	 *
	 * @param {PerspectiveCamera} camera - The camera.
	 * @param {CubeTexture} tCube - The cube texture to render.
	 * @param {number} [opacity=1] - The opacity.
	 */
	constructor( camera, tCube, opacity = 1 ) {

		super();

		/**
		 * The camera.
		 *
		 * @type {PerspectiveCamera}
		 */
		this.camera = camera;

		/**
		 * The cube texture to render.
		 *
		 * @type {CubeTexture}
		 */
		this.tCube = tCube;

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

		// internals

		const cubeShader = ShaderLib[ 'cube' ];

		this._cubeMesh = new Mesh(
			new BoxGeometry( 10, 10, 10 ),
			new ShaderMaterial( {
				uniforms: UniformsUtils.clone( cubeShader.uniforms ),
				vertexShader: cubeShader.vertexShader,
				fragmentShader: cubeShader.fragmentShader,
				depthTest: false,
				depthWrite: false,
				side: BackSide
			} )
		);

		Object.defineProperty( this._cubeMesh.material, 'envMap', {

			get: function () {

				return this.uniforms.tCube.value;

			}

		} );

		this._cubeScene = new Scene();
		this._cubeCamera = new PerspectiveCamera();
		this._cubeScene.add( this._cubeMesh );

	}

	/**
	 * Performs the cube texture pass.
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

		const oldAutoClear = renderer.autoClear;
		renderer.autoClear = false;

		this._cubeCamera.projectionMatrix.copy( this.camera.projectionMatrix );
		this._cubeCamera.quaternion.setFromRotationMatrix( this.camera.matrixWorld );

		this._cubeMesh.material.uniforms.tCube.value = this.tCube;
		this._cubeMesh.material.uniforms.tFlip.value = ( this.tCube.isCubeTexture && this.tCube.isRenderTargetTexture === false ) ? - 1 : 1;
		this._cubeMesh.material.uniforms.opacity.value = this.opacity;
		this._cubeMesh.material.transparent = ( this.opacity < 1.0 );

		renderer.setRenderTarget( this.renderToScreen ? null : readBuffer );
		if ( this.clear ) renderer.clear();
		renderer.render( this._cubeScene, this._cubeCamera );

		renderer.autoClear = oldAutoClear;

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
	dispose() {

		this._cubeMesh.geometry.dispose();
		this._cubeMesh.material.dispose();

	}

}
```
</details>

#### Methods

##### `render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget): void`

<details><summary>Code</summary>

```ts
render( renderer, writeBuffer, readBuffer/*, deltaTime, maskActive*/ ) {

		const oldAutoClear = renderer.autoClear;
		renderer.autoClear = false;

		this._cubeCamera.projectionMatrix.copy( this.camera.projectionMatrix );
		this._cubeCamera.quaternion.setFromRotationMatrix( this.camera.matrixWorld );

		this._cubeMesh.material.uniforms.tCube.value = this.tCube;
		this._cubeMesh.material.uniforms.tFlip.value = ( this.tCube.isCubeTexture && this.tCube.isRenderTargetTexture === false ) ? - 1 : 1;
		this._cubeMesh.material.uniforms.opacity.value = this.opacity;
		this._cubeMesh.material.transparent = ( this.opacity < 1.0 );

		renderer.setRenderTarget( this.renderToScreen ? null : readBuffer );
		if ( this.clear ) renderer.clear();
		renderer.render( this._cubeScene, this._cubeCamera );

		renderer.autoClear = oldAutoClear;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this._cubeMesh.geometry.dispose();
		this._cubeMesh.material.dispose();

	}
```
</details>


---