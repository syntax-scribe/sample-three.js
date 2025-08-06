[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BloomPass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/BloomPass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AdditiveBlending` | `three` |
| `HalfFloatType` | `three` |
| `ShaderMaterial` | `three` |
| `UniformsUtils` | `three` |
| `Vector2` | `three` |
| `WebGLRenderTarget` | `three` |
| `Pass` | `./Pass.js` |
| `FullScreenQuad` | `./Pass.js` |
| `ConvolutionShader` | `../shaders/ConvolutionShader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `convolutionShader` | `ShaderMaterial` | let/var | `ConvolutionShader` | ✗ |
| `CombineShader` | `{ name: string; uniforms: { tDiffuse:...` | let/var | `{ name: 'CombineShader', uniforms: { 'tDiffuse': { value: null }, 'strength':...` | ✗ |
| `kMaxKernelSize` | `25` | let/var | `25` | ✗ |
| `kernelSize` | `number` | let/var | `2 * Math.ceil( sigma * 3.0 ) + 1` | ✗ |
| `halfWidth` | `number` | let/var | `( kernelSize - 1 ) * 0.5` | ✗ |
| `values` | `any[]` | let/var | `new Array( kernelSize )` | ✗ |
| `sum` | `number` | let/var | `0.0` | ✗ |


---

## Functions

### `BloomPass.render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget, deltaTime: number, maskActive: boolean): void`

**JSDoc:**
```typescript
/**
	 * Performs the Bloom pass.
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
- **`deltaTime`** `number`
- **`maskActive`** `boolean`

**Returns:** `void`

**Calls:**

- `renderer.state.buffers.stencil.setTest`
- `renderer.setRenderTarget`
- `renderer.clear`
- `this._fsQuad.render`

**Internal Comments:**
```
// Render quad with blurred scene into texture (convolution pass 1) (x5)
// Render quad with blurred scene into texture (convolution pass 2) (x6)
// Render original scene with superimposed blur to texture (x5)
```

<details><summary>Code</summary>

```typescript
render( renderer, writeBuffer, readBuffer, deltaTime, maskActive ) {

		if ( maskActive ) renderer.state.buffers.stencil.setTest( false );

		// Render quad with blurred scene into texture (convolution pass 1)

		this._fsQuad.material = this.materialConvolution;

		this.convolutionUniforms[ 'tDiffuse' ].value = readBuffer.texture;
		this.convolutionUniforms[ 'uImageIncrement' ].value = BloomPass.blurX;

		renderer.setRenderTarget( this._renderTargetX );
		renderer.clear();
		this._fsQuad.render( renderer );


		// Render quad with blurred scene into texture (convolution pass 2)

		this.convolutionUniforms[ 'tDiffuse' ].value = this._renderTargetX.texture;
		this.convolutionUniforms[ 'uImageIncrement' ].value = BloomPass.blurY;

		renderer.setRenderTarget( this._renderTargetY );
		renderer.clear();
		this._fsQuad.render( renderer );

		// Render original scene with superimposed blur to texture

		this._fsQuad.material = this.materialCombine;

		this.combineUniforms[ 'tDiffuse' ].value = this._renderTargetY.texture;

		if ( maskActive ) renderer.state.buffers.stencil.setTest( true );

		renderer.setRenderTarget( readBuffer );
		if ( this.clear ) renderer.clear();
		this._fsQuad.render( renderer );

	}
```
</details>

### `BloomPass.setSize(width: number, height: number): void`

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

- `this._renderTargetX.setSize`
- `this._renderTargetY.setSize`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this._renderTargetX.setSize( width, height );
		this._renderTargetY.setSize( width, height );

	}
```
</details>

### `BloomPass.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this._renderTargetX.dispose`
- `this._renderTargetY.dispose`
- `this.materialCombine.dispose`
- `this.materialConvolution.dispose`
- `this._fsQuad.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this._renderTargetX.dispose();
		this._renderTargetY.dispose();

		this.materialCombine.dispose();
		this.materialConvolution.dispose();

		this._fsQuad.dispose();

	}
```
</details>

### `gauss(x: any, sigma: any): number`

**Parameters:**

- **`x`** `any`
- **`sigma`** `any`

**Returns:** `number`

**Calls:**

- `Math.exp`

<details><summary>Code</summary>

```typescript
function gauss( x, sigma ) {

	return Math.exp( - ( x * x ) / ( 2.0 * sigma * sigma ) );

}
```
</details>

### `buildKernel(sigma: any): any[]`

**Parameters:**

- **`sigma`** `any`

**Returns:** `any[]`

**Calls:**

- `Math.ceil`
- `gauss`

**Internal Comments:**
```
// We loop off the sqrt(2 * pi) * sigma term, since we're going to normalize anyway. (x2)
// normalize the kernel
```

<details><summary>Code</summary>

```typescript
function buildKernel( sigma ) {

	// We loop off the sqrt(2 * pi) * sigma term, since we're going to normalize anyway.

	const kMaxKernelSize = 25;
	let kernelSize = 2 * Math.ceil( sigma * 3.0 ) + 1;

	if ( kernelSize > kMaxKernelSize ) kernelSize = kMaxKernelSize;

	const halfWidth = ( kernelSize - 1 ) * 0.5;

	const values = new Array( kernelSize );
	let sum = 0.0;
	for ( let i = 0; i < kernelSize; ++ i ) {

		values[ i ] = gauss( i - halfWidth, sigma );
		sum += values[ i ];

	}

	// normalize the kernel

	for ( let i = 0; i < kernelSize; ++ i ) values[ i ] /= sum;

	return values;

}
```
</details>


---

## Classes

### `BloomPass`

<details><summary>Class Code</summary>

```ts
class BloomPass extends Pass {

	/**
	 * Constructs a new Bloom pass.
	 *
	 * @param {number} [strength=1] - The Bloom strength.
	 * @param {number} [kernelSize=25] - The kernel size.
	 * @param {number} [sigma=4] - The sigma.
	 */
	constructor( strength = 1, kernelSize = 25, sigma = 4 ) {

		super();

		// combine material

		/**
		 * The combine pass uniforms.
		 *
		 * @type {Object}
		 */
		this.combineUniforms = UniformsUtils.clone( CombineShader.uniforms );
		this.combineUniforms[ 'strength' ].value = strength;

		/**
		 * The combine pass material.
		 *
		 * @type {ShaderMaterial}
		 */
		this.materialCombine = new ShaderMaterial( {

			name: CombineShader.name,
			uniforms: this.combineUniforms,
			vertexShader: CombineShader.vertexShader,
			fragmentShader: CombineShader.fragmentShader,
			blending: AdditiveBlending,
			transparent: true

		} );

		// convolution material

		const convolutionShader = ConvolutionShader;

		/**
		 * The convolution pass uniforms.
		 *
		 * @type {Object}
		 */
		this.convolutionUniforms = UniformsUtils.clone( convolutionShader.uniforms );

		this.convolutionUniforms[ 'uImageIncrement' ].value = BloomPass.blurX;
		this.convolutionUniforms[ 'cKernel' ].value = buildKernel( sigma );

		/**
		 * The convolution pass material.
		 *
		 * @type {ShaderMaterial}
		 */
		this.materialConvolution = new ShaderMaterial( {

			name: convolutionShader.name,
			uniforms: this.convolutionUniforms,
			vertexShader: convolutionShader.vertexShader,
			fragmentShader: convolutionShader.fragmentShader,
			defines: {
				'KERNEL_SIZE_FLOAT': kernelSize.toFixed( 1 ),
				'KERNEL_SIZE_INT': kernelSize.toFixed( 0 )
			}

		} );

		/**
		 * Overwritten to disable the swap.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.needsSwap = false;

		// internals

		this._renderTargetX = new WebGLRenderTarget( 1, 1, { type: HalfFloatType } ); // will be resized later
		this._renderTargetX.texture.name = 'BloomPass.x';
		this._renderTargetY = new WebGLRenderTarget( 1, 1, { type: HalfFloatType } ); // will be resized later
		this._renderTargetY.texture.name = 'BloomPass.y';

		this._fsQuad = new FullScreenQuad( null );

	}

	/**
	 * Performs the Bloom pass.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {WebGLRenderTarget} writeBuffer - The write buffer. This buffer is intended as the rendering
	 * destination for the pass.
	 * @param {WebGLRenderTarget} readBuffer - The read buffer. The pass can access the result from the
	 * previous pass from this buffer.
	 * @param {number} deltaTime - The delta time in seconds.
	 * @param {boolean} maskActive - Whether masking is active or not.
	 */
	render( renderer, writeBuffer, readBuffer, deltaTime, maskActive ) {

		if ( maskActive ) renderer.state.buffers.stencil.setTest( false );

		// Render quad with blurred scene into texture (convolution pass 1)

		this._fsQuad.material = this.materialConvolution;

		this.convolutionUniforms[ 'tDiffuse' ].value = readBuffer.texture;
		this.convolutionUniforms[ 'uImageIncrement' ].value = BloomPass.blurX;

		renderer.setRenderTarget( this._renderTargetX );
		renderer.clear();
		this._fsQuad.render( renderer );


		// Render quad with blurred scene into texture (convolution pass 2)

		this.convolutionUniforms[ 'tDiffuse' ].value = this._renderTargetX.texture;
		this.convolutionUniforms[ 'uImageIncrement' ].value = BloomPass.blurY;

		renderer.setRenderTarget( this._renderTargetY );
		renderer.clear();
		this._fsQuad.render( renderer );

		// Render original scene with superimposed blur to texture

		this._fsQuad.material = this.materialCombine;

		this.combineUniforms[ 'tDiffuse' ].value = this._renderTargetY.texture;

		if ( maskActive ) renderer.state.buffers.stencil.setTest( true );

		renderer.setRenderTarget( readBuffer );
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

		this._renderTargetX.setSize( width, height );
		this._renderTargetY.setSize( width, height );

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
	dispose() {

		this._renderTargetX.dispose();
		this._renderTargetY.dispose();

		this.materialCombine.dispose();
		this.materialConvolution.dispose();

		this._fsQuad.dispose();

	}

}
```
</details>

#### Methods

##### `render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget, deltaTime: number, maskActive: boolean): void`

<details><summary>Code</summary>

```ts
render( renderer, writeBuffer, readBuffer, deltaTime, maskActive ) {

		if ( maskActive ) renderer.state.buffers.stencil.setTest( false );

		// Render quad with blurred scene into texture (convolution pass 1)

		this._fsQuad.material = this.materialConvolution;

		this.convolutionUniforms[ 'tDiffuse' ].value = readBuffer.texture;
		this.convolutionUniforms[ 'uImageIncrement' ].value = BloomPass.blurX;

		renderer.setRenderTarget( this._renderTargetX );
		renderer.clear();
		this._fsQuad.render( renderer );


		// Render quad with blurred scene into texture (convolution pass 2)

		this.convolutionUniforms[ 'tDiffuse' ].value = this._renderTargetX.texture;
		this.convolutionUniforms[ 'uImageIncrement' ].value = BloomPass.blurY;

		renderer.setRenderTarget( this._renderTargetY );
		renderer.clear();
		this._fsQuad.render( renderer );

		// Render original scene with superimposed blur to texture

		this._fsQuad.material = this.materialCombine;

		this.combineUniforms[ 'tDiffuse' ].value = this._renderTargetY.texture;

		if ( maskActive ) renderer.state.buffers.stencil.setTest( true );

		renderer.setRenderTarget( readBuffer );
		if ( this.clear ) renderer.clear();
		this._fsQuad.render( renderer );

	}
```
</details>

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		this._renderTargetX.setSize( width, height );
		this._renderTargetY.setSize( width, height );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this._renderTargetX.dispose();
		this._renderTargetY.dispose();

		this.materialCombine.dispose();
		this.materialConvolution.dispose();

		this._fsQuad.dispose();

	}
```
</details>


---