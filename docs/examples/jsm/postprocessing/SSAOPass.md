[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SSAOPass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 🧱 Classes | 1 |
| 📦 Imports | 29 |
| 📊 Variables & Constants | 17 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/SSAOPass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AddEquation` | `three` |
| `Color` | `three` |
| `CustomBlending` | `three` |
| `DataTexture` | `three` |
| `DepthTexture` | `three` |
| `DstAlphaFactor` | `three` |
| `DstColorFactor` | `three` |
| `FloatType` | `three` |
| `HalfFloatType` | `three` |
| `MathUtils` | `three` |
| `MeshNormalMaterial` | `three` |
| `NearestFilter` | `three` |
| `NoBlending` | `three` |
| `RedFormat` | `three` |
| `DepthStencilFormat` | `three` |
| `UnsignedInt248Type` | `three` |
| `RepeatWrapping` | `three` |
| `ShaderMaterial` | `three` |
| `UniformsUtils` | `three` |
| `Vector3` | `three` |
| `WebGLRenderTarget` | `three` |
| `ZeroFactor` | `three` |
| `Pass` | `./Pass.js` |
| `FullScreenQuad` | `./Pass.js` |
| `SimplexNoise` | `../math/SimplexNoise.js` |
| `SSAOBlurShader` | `../shaders/SSAOShader.js` |
| `SSAODepthShader` | `../shaders/SSAOShader.js` |
| `SSAOShader` | `../shaders/SSAOShader.js` |
| `CopyShader` | `../shaders/CopyShader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `depthTexture` | `any` | let/var | `new DepthTexture()` | ✗ |
| `originalAutoClear` | `any` | let/var | `renderer.autoClear` | ✗ |
| `originalAutoClear` | `any` | let/var | `renderer.autoClear` | ✗ |
| `kernel` | `any[]` | let/var | `this.kernel` | ✗ |
| `sample` | `any` | let/var | `new Vector3()` | ✗ |
| `scale` | `number` | let/var | `i / kernelSize` | ✗ |
| `width` | `4` | let/var | `4` | ✗ |
| `height` | `4` | let/var | `4` | ✗ |
| `simplex` | `SimplexNoise` | let/var | `new SimplexNoise()` | ✗ |
| `size` | `number` | let/var | `width * height` | ✗ |
| `data` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( size )` | ✗ |
| `x` | `number` | let/var | `( Math.random() * 2 ) - 1` | ✗ |
| `y` | `number` | let/var | `( Math.random() * 2 ) - 1` | ✗ |
| `z` | `0` | let/var | `0` | ✗ |
| `scene` | `Scene` | let/var | `this.scene` | ✗ |
| `cache` | `any[]` | let/var | `this._visibilityCache` | ✗ |
| `cache` | `any[]` | let/var | `this._visibilityCache` | ✗ |


---

## Functions

### `SSAOPass.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.normalRenderTarget.dispose`
- `this.ssaoRenderTarget.dispose`
- `this.blurRenderTarget.dispose`
- `this.normalMaterial.dispose`
- `this.blurMaterial.dispose`
- `this.copyMaterial.dispose`
- `this.depthRenderMaterial.dispose`
- `this._fsQuad.dispose`

**Internal Comments:**
```
// dispose render targets (x5)
// dispose materials (x5)
// dispose full screen quad (x5)
```

<details><summary>Code</summary>

```typescript
dispose() {

		// dispose render targets

		this.normalRenderTarget.dispose();
		this.ssaoRenderTarget.dispose();
		this.blurRenderTarget.dispose();

		// dispose materials

		this.normalMaterial.dispose();
		this.blurMaterial.dispose();
		this.copyMaterial.dispose();
		this.depthRenderMaterial.dispose();

		// dispose full screen quad

		this._fsQuad.dispose();

	}
```
</details>

### `SSAOPass.render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget): void`

**JSDoc:**
```typescript
/**
	 * Performs the SSAO pass.
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

- `this._overrideVisibility`
- `this._renderOverride`
- `this._restoreVisibility`
- `this._renderPass`
- `console.warn`

**Internal Comments:**
```
// render normals and depth (honor only meshes, points and lines do not contribute to SSAO) (x4)
// render SSAO (x7)
// render blur (x4)
// output result to screen
```

<details><summary>Code</summary>

```typescript
render( renderer, writeBuffer, readBuffer /*, deltaTime, maskActive */ ) {

		// render normals and depth (honor only meshes, points and lines do not contribute to SSAO)

		this._overrideVisibility();
		this._renderOverride( renderer, this.normalMaterial, this.normalRenderTarget, 0x7777ff, 1.0 );
		this._restoreVisibility();

		// render SSAO

		this.ssaoMaterial.uniforms[ 'kernelRadius' ].value = this.kernelRadius;
		this.ssaoMaterial.uniforms[ 'minDistance' ].value = this.minDistance;
		this.ssaoMaterial.uniforms[ 'maxDistance' ].value = this.maxDistance;
		this._renderPass( renderer, this.ssaoMaterial, this.ssaoRenderTarget );

		// render blur

		this._renderPass( renderer, this.blurMaterial, this.blurRenderTarget );

		// output result to screen

		switch ( this.output ) {

			case SSAOPass.OUTPUT.SSAO:

				this.copyMaterial.uniforms[ 'tDiffuse' ].value = this.ssaoRenderTarget.texture;
				this.copyMaterial.blending = NoBlending;
				this._renderPass( renderer, this.copyMaterial, this.renderToScreen ? null : readBuffer );

				break;

			case SSAOPass.OUTPUT.Blur:

				this.copyMaterial.uniforms[ 'tDiffuse' ].value = this.blurRenderTarget.texture;
				this.copyMaterial.blending = NoBlending;
				this._renderPass( renderer, this.copyMaterial, this.renderToScreen ? null : readBuffer );

				break;

			case SSAOPass.OUTPUT.Depth:

				this._renderPass( renderer, this.depthRenderMaterial, this.renderToScreen ? null : readBuffer );

				break;

			case SSAOPass.OUTPUT.Normal:

				this.copyMaterial.uniforms[ 'tDiffuse' ].value = this.normalRenderTarget.texture;
				this.copyMaterial.blending = NoBlending;
				this._renderPass( renderer, this.copyMaterial, this.renderToScreen ? null : readBuffer );

				break;

			case SSAOPass.OUTPUT.Default:

				this.copyMaterial.uniforms[ 'tDiffuse' ].value = this.blurRenderTarget.texture;
				this.copyMaterial.blending = CustomBlending;
				this._renderPass( renderer, this.copyMaterial, this.renderToScreen ? null : readBuffer );

				break;

			default:
				console.warn( 'THREE.SSAOPass: Unknown output type.' );

		}

	}
```
</details>

### `SSAOPass.setSize(width: number, height: number): void`

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

- `this.ssaoRenderTarget.setSize`
- `this.normalRenderTarget.setSize`
- `this.blurRenderTarget.setSize`
- `this.ssaoMaterial.uniforms[ 'resolution' ].value.set`
- `this.ssaoMaterial.uniforms[ 'cameraProjectionMatrix' ].value.copy`
- `this.ssaoMaterial.uniforms[ 'cameraInverseProjectionMatrix' ].value.copy`
- `this.blurMaterial.uniforms[ 'resolution' ].value.set`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this.width = width;
		this.height = height;

		this.ssaoRenderTarget.setSize( width, height );
		this.normalRenderTarget.setSize( width, height );
		this.blurRenderTarget.setSize( width, height );

		this.ssaoMaterial.uniforms[ 'resolution' ].value.set( width, height );
		this.ssaoMaterial.uniforms[ 'cameraProjectionMatrix' ].value.copy( this.camera.projectionMatrix );
		this.ssaoMaterial.uniforms[ 'cameraInverseProjectionMatrix' ].value.copy( this.camera.projectionMatrixInverse );

		this.blurMaterial.uniforms[ 'resolution' ].value.set( width, height );

	}
```
</details>

### `SSAOPass._renderPass(renderer: any, passMaterial: any, renderTarget: any, clearColor: any, clearAlpha: any): void`

**Parameters:**

- **`renderer`** `any`
- **`passMaterial`** `any`
- **`renderTarget`** `any`
- **`clearColor`** `any`
- **`clearAlpha`** `any`

**Returns:** `void`

**Calls:**

- `renderer.getClearColor`
- `renderer.getClearAlpha`
- `renderer.setRenderTarget`
- `renderer.setClearColor`
- `renderer.setClearAlpha`
- `renderer.clear`
- `this._fsQuad.render`

**Internal Comments:**
```
// save original state (x4)
// setup pass state (x4)
// restore original state (x4)
```

<details><summary>Code</summary>

```typescript
_renderPass( renderer, passMaterial, renderTarget, clearColor, clearAlpha ) {

		// save original state
		renderer.getClearColor( this._originalClearColor );
		const originalClearAlpha = renderer.getClearAlpha();
		const originalAutoClear = renderer.autoClear;

		renderer.setRenderTarget( renderTarget );

		// setup pass state
		renderer.autoClear = false;
		if ( ( clearColor !== undefined ) && ( clearColor !== null ) ) {

			renderer.setClearColor( clearColor );
			renderer.setClearAlpha( clearAlpha || 0.0 );
			renderer.clear();

		}

		this._fsQuad.material = passMaterial;
		this._fsQuad.render( renderer );

		// restore original state
		renderer.autoClear = originalAutoClear;
		renderer.setClearColor( this._originalClearColor );
		renderer.setClearAlpha( originalClearAlpha );

	}
```
</details>

### `SSAOPass._renderOverride(renderer: any, overrideMaterial: any, renderTarget: any, clearColor: any, clearAlpha: any): void`

**Parameters:**

- **`renderer`** `any`
- **`overrideMaterial`** `any`
- **`renderTarget`** `any`
- **`clearColor`** `any`
- **`clearAlpha`** `any`

**Returns:** `void`

**Calls:**

- `renderer.getClearColor`
- `renderer.getClearAlpha`
- `renderer.setRenderTarget`
- `renderer.setClearColor`
- `renderer.setClearAlpha`
- `renderer.clear`
- `renderer.render`

**Internal Comments:**
```
// restore original state (x4)
```

<details><summary>Code</summary>

```typescript
_renderOverride( renderer, overrideMaterial, renderTarget, clearColor, clearAlpha ) {

		renderer.getClearColor( this._originalClearColor );
		const originalClearAlpha = renderer.getClearAlpha();
		const originalAutoClear = renderer.autoClear;

		renderer.setRenderTarget( renderTarget );
		renderer.autoClear = false;

		clearColor = overrideMaterial.clearColor || clearColor;
		clearAlpha = overrideMaterial.clearAlpha || clearAlpha;

		if ( ( clearColor !== undefined ) && ( clearColor !== null ) ) {

			renderer.setClearColor( clearColor );
			renderer.setClearAlpha( clearAlpha || 0.0 );
			renderer.clear();

		}

		this.scene.overrideMaterial = overrideMaterial;
		renderer.render( this.scene, this.camera );
		this.scene.overrideMaterial = null;

		// restore original state

		renderer.autoClear = originalAutoClear;
		renderer.setClearColor( this._originalClearColor );
		renderer.setClearAlpha( originalClearAlpha );

	}
```
</details>

### `SSAOPass._generateSampleKernel(kernelSize: any): void`

**Parameters:**

- **`kernelSize`** `any`

**Returns:** `void`

**Calls:**

- `Math.random`
- `sample.normalize`
- `MathUtils.lerp`
- `sample.multiplyScalar`
- `kernel.push`

<details><summary>Code</summary>

```typescript
_generateSampleKernel( kernelSize ) {

		const kernel = this.kernel;

		for ( let i = 0; i < kernelSize; i ++ ) {

			const sample = new Vector3();
			sample.x = ( Math.random() * 2 ) - 1;
			sample.y = ( Math.random() * 2 ) - 1;
			sample.z = Math.random();

			sample.normalize();

			let scale = i / kernelSize;
			scale = MathUtils.lerp( 0.1, 1, scale * scale );
			sample.multiplyScalar( scale );

			kernel.push( sample );

		}

	}
```
</details>

### `SSAOPass._generateRandomKernelRotations(): void`

**Returns:** `void`

**Calls:**

- `Math.random`
- `simplex.noise3d`

<details><summary>Code</summary>

```typescript
_generateRandomKernelRotations() {

		const width = 4, height = 4;

		const simplex = new SimplexNoise();

		const size = width * height;
		const data = new Float32Array( size );

		for ( let i = 0; i < size; i ++ ) {

			const x = ( Math.random() * 2 ) - 1;
			const y = ( Math.random() * 2 ) - 1;
			const z = 0;

			data[ i ] = simplex.noise3d( x, y, z );

		}

		this.noiseTexture = new DataTexture( data, width, height, RedFormat, FloatType );
		this.noiseTexture.wrapS = RepeatWrapping;
		this.noiseTexture.wrapT = RepeatWrapping;
		this.noiseTexture.needsUpdate = true;

	}
```
</details>

### `SSAOPass._overrideVisibility(): void`

**Returns:** `void`

**Calls:**

- `scene.traverse`
- `cache.push`

<details><summary>Code</summary>

```typescript
_overrideVisibility() {

		const scene = this.scene;
		const cache = this._visibilityCache;

		scene.traverse( function ( object ) {

			if ( ( object.isPoints || object.isLine || object.isLine2 ) && object.visible ) {

				object.visible = false;
				cache.push( object );

			}

		} );

	}
```
</details>

### `SSAOPass._restoreVisibility(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_restoreVisibility() {

		const cache = this._visibilityCache;

		for ( let i = 0; i < cache.length; i ++ ) {

			cache[ i ].visible = true;

		}

		cache.length = 0;

	}
```
</details>


---

## Classes

### `SSAOPass`

<details><summary>Class Code</summary>

```ts
class SSAOPass extends Pass {

	/**
	 * Constructs a new SSAO pass.
	 *
	 * @param {Scene} scene - The scene to compute the AO for.
	 * @param {Camera} camera - The camera.
	 * @param {number} [width=512] - The width of the effect.
	 * @param {number} [height=512] - The height of the effect.
	 * @param {number} [kernelSize=32] - The kernel size.
	 */
	constructor( scene, camera, width = 512, height = 512, kernelSize = 32 ) {

		super();

		/**
		 * The width of the effect.
		 *
		 * @type {number}
		 * @default 512
		 */
		this.width = width;

		/**
		 * The height of the effect.
		 *
		 * @type {number}
		 * @default 512
		 */
		this.height = height;

		/**
		 * Overwritten to perform a clear operation by default.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.clear = true;

		/**
		 * Overwritten to disable the swap.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.needsSwap = false;

		/**
		 * The camera.
		 *
		 * @type {Camera}
		 */
		this.camera = camera;

		/**
		 * The scene to render the AO for.
		 *
		 * @type {Scene}
		 */
		this.scene = scene;

		/**
		 * The kernel radius controls how wide the
		 * AO spreads.
		 *
		 * @type {number}
		 * @default 8
		 */
		this.kernelRadius = 8;
		this.kernel = [];
		this.noiseTexture = null;

		/**
		 * The output configuration.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.output = 0;

		/**
		 * Defines the minimum distance that should be
		 * affected by the AO.
		 *
		 * @type {number}
		 * @default 0.005
		 */
		this.minDistance = 0.005;

		/**
		 * Defines the maximum distance that should be
		 * affected by the AO.
		 *
		 * @type {number}
		 * @default 0.1
		 */
		this.maxDistance = 0.1;

		this._visibilityCache = [];

		//

		this._generateSampleKernel( kernelSize );
		this._generateRandomKernelRotations();

		// depth texture

		const depthTexture = new DepthTexture();
		depthTexture.format = DepthStencilFormat;
		depthTexture.type = UnsignedInt248Type;

		// normal render target with depth buffer

		this.normalRenderTarget = new WebGLRenderTarget( this.width, this.height, {
			minFilter: NearestFilter,
			magFilter: NearestFilter,
			type: HalfFloatType,
			depthTexture: depthTexture
		} );

		// ssao render target

		this.ssaoRenderTarget = new WebGLRenderTarget( this.width, this.height, { type: HalfFloatType } );

		this.blurRenderTarget = this.ssaoRenderTarget.clone();

		// ssao material

		this.ssaoMaterial = new ShaderMaterial( {
			defines: Object.assign( {}, SSAOShader.defines ),
			uniforms: UniformsUtils.clone( SSAOShader.uniforms ),
			vertexShader: SSAOShader.vertexShader,
			fragmentShader: SSAOShader.fragmentShader,
			blending: NoBlending
		} );

		this.ssaoMaterial.defines[ 'KERNEL_SIZE' ] = kernelSize;

		this.ssaoMaterial.uniforms[ 'tNormal' ].value = this.normalRenderTarget.texture;
		this.ssaoMaterial.uniforms[ 'tDepth' ].value = this.normalRenderTarget.depthTexture;
		this.ssaoMaterial.uniforms[ 'tNoise' ].value = this.noiseTexture;
		this.ssaoMaterial.uniforms[ 'kernel' ].value = this.kernel;
		this.ssaoMaterial.uniforms[ 'cameraNear' ].value = this.camera.near;
		this.ssaoMaterial.uniforms[ 'cameraFar' ].value = this.camera.far;
		this.ssaoMaterial.uniforms[ 'resolution' ].value.set( this.width, this.height );
		this.ssaoMaterial.uniforms[ 'cameraProjectionMatrix' ].value.copy( this.camera.projectionMatrix );
		this.ssaoMaterial.uniforms[ 'cameraInverseProjectionMatrix' ].value.copy( this.camera.projectionMatrixInverse );

		// normal material

		this.normalMaterial = new MeshNormalMaterial();
		this.normalMaterial.blending = NoBlending;

		// blur material

		this.blurMaterial = new ShaderMaterial( {
			defines: Object.assign( {}, SSAOBlurShader.defines ),
			uniforms: UniformsUtils.clone( SSAOBlurShader.uniforms ),
			vertexShader: SSAOBlurShader.vertexShader,
			fragmentShader: SSAOBlurShader.fragmentShader
		} );
		this.blurMaterial.uniforms[ 'tDiffuse' ].value = this.ssaoRenderTarget.texture;
		this.blurMaterial.uniforms[ 'resolution' ].value.set( this.width, this.height );

		// material for rendering the depth

		this.depthRenderMaterial = new ShaderMaterial( {
			defines: Object.assign( {}, SSAODepthShader.defines ),
			uniforms: UniformsUtils.clone( SSAODepthShader.uniforms ),
			vertexShader: SSAODepthShader.vertexShader,
			fragmentShader: SSAODepthShader.fragmentShader,
			blending: NoBlending
		} );
		this.depthRenderMaterial.uniforms[ 'tDepth' ].value = this.normalRenderTarget.depthTexture;
		this.depthRenderMaterial.uniforms[ 'cameraNear' ].value = this.camera.near;
		this.depthRenderMaterial.uniforms[ 'cameraFar' ].value = this.camera.far;

		// material for rendering the content of a render target

		this.copyMaterial = new ShaderMaterial( {
			uniforms: UniformsUtils.clone( CopyShader.uniforms ),
			vertexShader: CopyShader.vertexShader,
			fragmentShader: CopyShader.fragmentShader,
			transparent: true,
			depthTest: false,
			depthWrite: false,
			blendSrc: DstColorFactor,
			blendDst: ZeroFactor,
			blendEquation: AddEquation,
			blendSrcAlpha: DstAlphaFactor,
			blendDstAlpha: ZeroFactor,
			blendEquationAlpha: AddEquation
		} );

		// internals

		this._fsQuad = new FullScreenQuad( null );

		this._originalClearColor = new Color();

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
	dispose() {

		// dispose render targets

		this.normalRenderTarget.dispose();
		this.ssaoRenderTarget.dispose();
		this.blurRenderTarget.dispose();

		// dispose materials

		this.normalMaterial.dispose();
		this.blurMaterial.dispose();
		this.copyMaterial.dispose();
		this.depthRenderMaterial.dispose();

		// dispose full screen quad

		this._fsQuad.dispose();

	}

	/**
	 * Performs the SSAO pass.
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

		// render normals and depth (honor only meshes, points and lines do not contribute to SSAO)

		this._overrideVisibility();
		this._renderOverride( renderer, this.normalMaterial, this.normalRenderTarget, 0x7777ff, 1.0 );
		this._restoreVisibility();

		// render SSAO

		this.ssaoMaterial.uniforms[ 'kernelRadius' ].value = this.kernelRadius;
		this.ssaoMaterial.uniforms[ 'minDistance' ].value = this.minDistance;
		this.ssaoMaterial.uniforms[ 'maxDistance' ].value = this.maxDistance;
		this._renderPass( renderer, this.ssaoMaterial, this.ssaoRenderTarget );

		// render blur

		this._renderPass( renderer, this.blurMaterial, this.blurRenderTarget );

		// output result to screen

		switch ( this.output ) {

			case SSAOPass.OUTPUT.SSAO:

				this.copyMaterial.uniforms[ 'tDiffuse' ].value = this.ssaoRenderTarget.texture;
				this.copyMaterial.blending = NoBlending;
				this._renderPass( renderer, this.copyMaterial, this.renderToScreen ? null : readBuffer );

				break;

			case SSAOPass.OUTPUT.Blur:

				this.copyMaterial.uniforms[ 'tDiffuse' ].value = this.blurRenderTarget.texture;
				this.copyMaterial.blending = NoBlending;
				this._renderPass( renderer, this.copyMaterial, this.renderToScreen ? null : readBuffer );

				break;

			case SSAOPass.OUTPUT.Depth:

				this._renderPass( renderer, this.depthRenderMaterial, this.renderToScreen ? null : readBuffer );

				break;

			case SSAOPass.OUTPUT.Normal:

				this.copyMaterial.uniforms[ 'tDiffuse' ].value = this.normalRenderTarget.texture;
				this.copyMaterial.blending = NoBlending;
				this._renderPass( renderer, this.copyMaterial, this.renderToScreen ? null : readBuffer );

				break;

			case SSAOPass.OUTPUT.Default:

				this.copyMaterial.uniforms[ 'tDiffuse' ].value = this.blurRenderTarget.texture;
				this.copyMaterial.blending = CustomBlending;
				this._renderPass( renderer, this.copyMaterial, this.renderToScreen ? null : readBuffer );

				break;

			default:
				console.warn( 'THREE.SSAOPass: Unknown output type.' );

		}

	}

	/**
	 * Sets the size of the pass.
	 *
	 * @param {number} width - The width to set.
	 * @param {number} height - The height to set.
	 */
	setSize( width, height ) {

		this.width = width;
		this.height = height;

		this.ssaoRenderTarget.setSize( width, height );
		this.normalRenderTarget.setSize( width, height );
		this.blurRenderTarget.setSize( width, height );

		this.ssaoMaterial.uniforms[ 'resolution' ].value.set( width, height );
		this.ssaoMaterial.uniforms[ 'cameraProjectionMatrix' ].value.copy( this.camera.projectionMatrix );
		this.ssaoMaterial.uniforms[ 'cameraInverseProjectionMatrix' ].value.copy( this.camera.projectionMatrixInverse );

		this.blurMaterial.uniforms[ 'resolution' ].value.set( width, height );

	}

	// internals

	_renderPass( renderer, passMaterial, renderTarget, clearColor, clearAlpha ) {

		// save original state
		renderer.getClearColor( this._originalClearColor );
		const originalClearAlpha = renderer.getClearAlpha();
		const originalAutoClear = renderer.autoClear;

		renderer.setRenderTarget( renderTarget );

		// setup pass state
		renderer.autoClear = false;
		if ( ( clearColor !== undefined ) && ( clearColor !== null ) ) {

			renderer.setClearColor( clearColor );
			renderer.setClearAlpha( clearAlpha || 0.0 );
			renderer.clear();

		}

		this._fsQuad.material = passMaterial;
		this._fsQuad.render( renderer );

		// restore original state
		renderer.autoClear = originalAutoClear;
		renderer.setClearColor( this._originalClearColor );
		renderer.setClearAlpha( originalClearAlpha );

	}

	_renderOverride( renderer, overrideMaterial, renderTarget, clearColor, clearAlpha ) {

		renderer.getClearColor( this._originalClearColor );
		const originalClearAlpha = renderer.getClearAlpha();
		const originalAutoClear = renderer.autoClear;

		renderer.setRenderTarget( renderTarget );
		renderer.autoClear = false;

		clearColor = overrideMaterial.clearColor || clearColor;
		clearAlpha = overrideMaterial.clearAlpha || clearAlpha;

		if ( ( clearColor !== undefined ) && ( clearColor !== null ) ) {

			renderer.setClearColor( clearColor );
			renderer.setClearAlpha( clearAlpha || 0.0 );
			renderer.clear();

		}

		this.scene.overrideMaterial = overrideMaterial;
		renderer.render( this.scene, this.camera );
		this.scene.overrideMaterial = null;

		// restore original state

		renderer.autoClear = originalAutoClear;
		renderer.setClearColor( this._originalClearColor );
		renderer.setClearAlpha( originalClearAlpha );

	}

	_generateSampleKernel( kernelSize ) {

		const kernel = this.kernel;

		for ( let i = 0; i < kernelSize; i ++ ) {

			const sample = new Vector3();
			sample.x = ( Math.random() * 2 ) - 1;
			sample.y = ( Math.random() * 2 ) - 1;
			sample.z = Math.random();

			sample.normalize();

			let scale = i / kernelSize;
			scale = MathUtils.lerp( 0.1, 1, scale * scale );
			sample.multiplyScalar( scale );

			kernel.push( sample );

		}

	}

	_generateRandomKernelRotations() {

		const width = 4, height = 4;

		const simplex = new SimplexNoise();

		const size = width * height;
		const data = new Float32Array( size );

		for ( let i = 0; i < size; i ++ ) {

			const x = ( Math.random() * 2 ) - 1;
			const y = ( Math.random() * 2 ) - 1;
			const z = 0;

			data[ i ] = simplex.noise3d( x, y, z );

		}

		this.noiseTexture = new DataTexture( data, width, height, RedFormat, FloatType );
		this.noiseTexture.wrapS = RepeatWrapping;
		this.noiseTexture.wrapT = RepeatWrapping;
		this.noiseTexture.needsUpdate = true;

	}

	_overrideVisibility() {

		const scene = this.scene;
		const cache = this._visibilityCache;

		scene.traverse( function ( object ) {

			if ( ( object.isPoints || object.isLine || object.isLine2 ) && object.visible ) {

				object.visible = false;
				cache.push( object );

			}

		} );

	}

	_restoreVisibility() {

		const cache = this._visibilityCache;

		for ( let i = 0; i < cache.length; i ++ ) {

			cache[ i ].visible = true;

		}

		cache.length = 0;

	}

}
```
</details>

#### Methods

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		// dispose render targets

		this.normalRenderTarget.dispose();
		this.ssaoRenderTarget.dispose();
		this.blurRenderTarget.dispose();

		// dispose materials

		this.normalMaterial.dispose();
		this.blurMaterial.dispose();
		this.copyMaterial.dispose();
		this.depthRenderMaterial.dispose();

		// dispose full screen quad

		this._fsQuad.dispose();

	}
```
</details>

##### `render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget): void`

<details><summary>Code</summary>

```ts
render( renderer, writeBuffer, readBuffer /*, deltaTime, maskActive */ ) {

		// render normals and depth (honor only meshes, points and lines do not contribute to SSAO)

		this._overrideVisibility();
		this._renderOverride( renderer, this.normalMaterial, this.normalRenderTarget, 0x7777ff, 1.0 );
		this._restoreVisibility();

		// render SSAO

		this.ssaoMaterial.uniforms[ 'kernelRadius' ].value = this.kernelRadius;
		this.ssaoMaterial.uniforms[ 'minDistance' ].value = this.minDistance;
		this.ssaoMaterial.uniforms[ 'maxDistance' ].value = this.maxDistance;
		this._renderPass( renderer, this.ssaoMaterial, this.ssaoRenderTarget );

		// render blur

		this._renderPass( renderer, this.blurMaterial, this.blurRenderTarget );

		// output result to screen

		switch ( this.output ) {

			case SSAOPass.OUTPUT.SSAO:

				this.copyMaterial.uniforms[ 'tDiffuse' ].value = this.ssaoRenderTarget.texture;
				this.copyMaterial.blending = NoBlending;
				this._renderPass( renderer, this.copyMaterial, this.renderToScreen ? null : readBuffer );

				break;

			case SSAOPass.OUTPUT.Blur:

				this.copyMaterial.uniforms[ 'tDiffuse' ].value = this.blurRenderTarget.texture;
				this.copyMaterial.blending = NoBlending;
				this._renderPass( renderer, this.copyMaterial, this.renderToScreen ? null : readBuffer );

				break;

			case SSAOPass.OUTPUT.Depth:

				this._renderPass( renderer, this.depthRenderMaterial, this.renderToScreen ? null : readBuffer );

				break;

			case SSAOPass.OUTPUT.Normal:

				this.copyMaterial.uniforms[ 'tDiffuse' ].value = this.normalRenderTarget.texture;
				this.copyMaterial.blending = NoBlending;
				this._renderPass( renderer, this.copyMaterial, this.renderToScreen ? null : readBuffer );

				break;

			case SSAOPass.OUTPUT.Default:

				this.copyMaterial.uniforms[ 'tDiffuse' ].value = this.blurRenderTarget.texture;
				this.copyMaterial.blending = CustomBlending;
				this._renderPass( renderer, this.copyMaterial, this.renderToScreen ? null : readBuffer );

				break;

			default:
				console.warn( 'THREE.SSAOPass: Unknown output type.' );

		}

	}
```
</details>

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		this.width = width;
		this.height = height;

		this.ssaoRenderTarget.setSize( width, height );
		this.normalRenderTarget.setSize( width, height );
		this.blurRenderTarget.setSize( width, height );

		this.ssaoMaterial.uniforms[ 'resolution' ].value.set( width, height );
		this.ssaoMaterial.uniforms[ 'cameraProjectionMatrix' ].value.copy( this.camera.projectionMatrix );
		this.ssaoMaterial.uniforms[ 'cameraInverseProjectionMatrix' ].value.copy( this.camera.projectionMatrixInverse );

		this.blurMaterial.uniforms[ 'resolution' ].value.set( width, height );

	}
```
</details>

##### `_renderPass(renderer: any, passMaterial: any, renderTarget: any, clearColor: any, clearAlpha: any): void`

<details><summary>Code</summary>

```ts
_renderPass( renderer, passMaterial, renderTarget, clearColor, clearAlpha ) {

		// save original state
		renderer.getClearColor( this._originalClearColor );
		const originalClearAlpha = renderer.getClearAlpha();
		const originalAutoClear = renderer.autoClear;

		renderer.setRenderTarget( renderTarget );

		// setup pass state
		renderer.autoClear = false;
		if ( ( clearColor !== undefined ) && ( clearColor !== null ) ) {

			renderer.setClearColor( clearColor );
			renderer.setClearAlpha( clearAlpha || 0.0 );
			renderer.clear();

		}

		this._fsQuad.material = passMaterial;
		this._fsQuad.render( renderer );

		// restore original state
		renderer.autoClear = originalAutoClear;
		renderer.setClearColor( this._originalClearColor );
		renderer.setClearAlpha( originalClearAlpha );

	}
```
</details>

##### `_renderOverride(renderer: any, overrideMaterial: any, renderTarget: any, clearColor: any, clearAlpha: any): void`

<details><summary>Code</summary>

```ts
_renderOverride( renderer, overrideMaterial, renderTarget, clearColor, clearAlpha ) {

		renderer.getClearColor( this._originalClearColor );
		const originalClearAlpha = renderer.getClearAlpha();
		const originalAutoClear = renderer.autoClear;

		renderer.setRenderTarget( renderTarget );
		renderer.autoClear = false;

		clearColor = overrideMaterial.clearColor || clearColor;
		clearAlpha = overrideMaterial.clearAlpha || clearAlpha;

		if ( ( clearColor !== undefined ) && ( clearColor !== null ) ) {

			renderer.setClearColor( clearColor );
			renderer.setClearAlpha( clearAlpha || 0.0 );
			renderer.clear();

		}

		this.scene.overrideMaterial = overrideMaterial;
		renderer.render( this.scene, this.camera );
		this.scene.overrideMaterial = null;

		// restore original state

		renderer.autoClear = originalAutoClear;
		renderer.setClearColor( this._originalClearColor );
		renderer.setClearAlpha( originalClearAlpha );

	}
```
</details>

##### `_generateSampleKernel(kernelSize: any): void`

<details><summary>Code</summary>

```ts
_generateSampleKernel( kernelSize ) {

		const kernel = this.kernel;

		for ( let i = 0; i < kernelSize; i ++ ) {

			const sample = new Vector3();
			sample.x = ( Math.random() * 2 ) - 1;
			sample.y = ( Math.random() * 2 ) - 1;
			sample.z = Math.random();

			sample.normalize();

			let scale = i / kernelSize;
			scale = MathUtils.lerp( 0.1, 1, scale * scale );
			sample.multiplyScalar( scale );

			kernel.push( sample );

		}

	}
```
</details>

##### `_generateRandomKernelRotations(): void`

<details><summary>Code</summary>

```ts
_generateRandomKernelRotations() {

		const width = 4, height = 4;

		const simplex = new SimplexNoise();

		const size = width * height;
		const data = new Float32Array( size );

		for ( let i = 0; i < size; i ++ ) {

			const x = ( Math.random() * 2 ) - 1;
			const y = ( Math.random() * 2 ) - 1;
			const z = 0;

			data[ i ] = simplex.noise3d( x, y, z );

		}

		this.noiseTexture = new DataTexture( data, width, height, RedFormat, FloatType );
		this.noiseTexture.wrapS = RepeatWrapping;
		this.noiseTexture.wrapT = RepeatWrapping;
		this.noiseTexture.needsUpdate = true;

	}
```
</details>

##### `_overrideVisibility(): void`

<details><summary>Code</summary>

```ts
_overrideVisibility() {

		const scene = this.scene;
		const cache = this._visibilityCache;

		scene.traverse( function ( object ) {

			if ( ( object.isPoints || object.isLine || object.isLine2 ) && object.visible ) {

				object.visible = false;
				cache.push( object );

			}

		} );

	}
```
</details>

##### `_restoreVisibility(): void`

<details><summary>Code</summary>

```ts
_restoreVisibility() {

		const cache = this._visibilityCache;

		for ( let i = 0; i < cache.length; i ++ ) {

			cache[ i ].visible = true;

		}

		cache.length = 0;

	}
```
</details>


---