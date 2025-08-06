[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SSAARenderPass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/SSAARenderPass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AdditiveBlending` | `three` |
| `Color` | `three` |
| `HalfFloatType` | `three` |
| `ShaderMaterial` | `three` |
| `UniformsUtils` | `three` |
| `WebGLRenderTarget` | `three` |
| `Pass` | `./Pass.js` |
| `FullScreenQuad` | `./Pass.js` |
| `CopyShader` | `../shaders/CopyShader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `jitterOffsets` | `number[][]` | let/var | `_JitterVectors[ Math.max( 0, Math.min( this.sampleLevel, 5 ) ) ]` | ✗ |
| `autoClear` | `any` | let/var | `renderer.autoClear` | ✗ |
| `baseSampleWeight` | `number` | let/var | `1.0 / jitterOffsets.length` | ✗ |
| `roundingRange` | `number` | let/var | `1 / 32` | ✗ |
| `viewOffset` | `{ fullWidth: any; fullHeight: any; of...` | let/var | `{ fullWidth: readBuffer.width, fullHeight: readBuffer.height, offsetX: 0, off...` | ✗ |
| `jitterOffset` | `number[]` | let/var | `jitterOffsets[ i ]` | ✗ |
| `sampleWeight` | `number` | let/var | `baseSampleWeight` | ✗ |
| `uniformCenteredDistribution` | `number` | let/var | `( - 0.5 + ( i + 0.5 ) / jitterOffsets.length )` | ✗ |
| `_JitterVectors` | `number[][][]` | let/var | `[ [ [ 0, 0 ] ], [ [ 4, 4 ], [ - 4, - 4 ] ], [ [ - 2, - 6 ], [ 6, - 2 ], [ - 6...` | ✗ |


---

## Functions

### `SSAARenderPass.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this._sampleRenderTarget.dispose`
- `this._copyMaterial.dispose`
- `this._fsQuad.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		if ( this._sampleRenderTarget ) {

			this._sampleRenderTarget.dispose();
			this._sampleRenderTarget = null;

		}

		this._copyMaterial.dispose();

		this._fsQuad.dispose();

	}
```
</details>

### `SSAARenderPass.setSize(width: number, height: number): void`

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

- `this._sampleRenderTarget.setSize`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		if ( this._sampleRenderTarget )	this._sampleRenderTarget.setSize( width, height );

	}
```
</details>

### `SSAARenderPass.render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget): void`

**JSDoc:**
```typescript
/**
	 * Performs the SSAA render pass.
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

- `Math.max`
- `Math.min`
- `renderer.getClearColor`
- `renderer.getClearAlpha`
- `Object.assign`
- `this.camera.setViewOffset`
- `renderer.setClearColor`
- `renderer.setRenderTarget`
- `renderer.clear`
- `renderer.render`
- `this._fsQuad.render`
- `this.camera.clearViewOffset`

**Internal Comments:**
```
// render the scene multiple times, each slightly jitter offset from the last and accumulate the results.
// the theory is that equal weights for each sample lead to an accumulation of rounding errors. (x2)
// The following equation varies the sampleWeight per sample so that it is uniformly distributed (x2)
// across a range of values whose rounding errors cancel each other out. (x2)
```

<details><summary>Code</summary>

```typescript
render( renderer, writeBuffer, readBuffer/*, deltaTime, maskActive */ ) {

		if ( ! this._sampleRenderTarget ) {

			this._sampleRenderTarget = new WebGLRenderTarget( readBuffer.width, readBuffer.height, { type: HalfFloatType, stencilBuffer: this.stencilBuffer } );
			this._sampleRenderTarget.texture.name = 'SSAARenderPass.sample';

		}

		const jitterOffsets = _JitterVectors[ Math.max( 0, Math.min( this.sampleLevel, 5 ) ) ];

		const autoClear = renderer.autoClear;
		renderer.autoClear = false;

		renderer.getClearColor( this._oldClearColor );
		const oldClearAlpha = renderer.getClearAlpha();

		const baseSampleWeight = 1.0 / jitterOffsets.length;
		const roundingRange = 1 / 32;
		this._copyUniforms[ 'tDiffuse' ].value = this._sampleRenderTarget.texture;

		const viewOffset = {

			fullWidth: readBuffer.width,
			fullHeight: readBuffer.height,
			offsetX: 0,
			offsetY: 0,
			width: readBuffer.width,
			height: readBuffer.height

		};

		const originalViewOffset = Object.assign( {}, this.camera.view );

		if ( originalViewOffset.enabled ) Object.assign( viewOffset, originalViewOffset );

		// render the scene multiple times, each slightly jitter offset from the last and accumulate the results.
		for ( let i = 0; i < jitterOffsets.length; i ++ ) {

			const jitterOffset = jitterOffsets[ i ];

			if ( this.camera.setViewOffset ) {

				this.camera.setViewOffset(

					viewOffset.fullWidth, viewOffset.fullHeight,

					viewOffset.offsetX + jitterOffset[ 0 ] * 0.0625, viewOffset.offsetY + jitterOffset[ 1 ] * 0.0625, // 0.0625 = 1 / 16

					viewOffset.width, viewOffset.height

				);

			}

			let sampleWeight = baseSampleWeight;

			if ( this.unbiased ) {

				// the theory is that equal weights for each sample lead to an accumulation of rounding errors.
				// The following equation varies the sampleWeight per sample so that it is uniformly distributed
				// across a range of values whose rounding errors cancel each other out.

				const uniformCenteredDistribution = ( - 0.5 + ( i + 0.5 ) / jitterOffsets.length );
				sampleWeight += roundingRange * uniformCenteredDistribution;

			}

			this._copyUniforms[ 'opacity' ].value = sampleWeight;
			renderer.setClearColor( this.clearColor, this.clearAlpha );
			renderer.setRenderTarget( this._sampleRenderTarget );
			renderer.clear();
			renderer.render( this.scene, this.camera );

			renderer.setRenderTarget( this.renderToScreen ? null : writeBuffer );

			if ( i === 0 ) {

				renderer.setClearColor( 0x000000, 0.0 );
				renderer.clear();

			}

			this._fsQuad.render( renderer );

		}

		if ( this.camera.setViewOffset && originalViewOffset.enabled ) {

			this.camera.setViewOffset(

				originalViewOffset.fullWidth, originalViewOffset.fullHeight,

				originalViewOffset.offsetX, originalViewOffset.offsetY,

				originalViewOffset.width, originalViewOffset.height

			);

		} else if ( this.camera.clearViewOffset ) {

			this.camera.clearViewOffset();

		}

		renderer.autoClear = autoClear;
		renderer.setClearColor( this._oldClearColor, oldClearAlpha );

	}
```
</details>


---

## Classes

### `SSAARenderPass`

<details><summary>Class Code</summary>

```ts
class SSAARenderPass extends Pass {

	/**
	 * Constructs a new SSAA render pass.
	 *
	 * @param {Scene} scene - The scene to render.
	 * @param {Camera} camera - The camera.
	 * @param {?(number|Color|string)} [clearColor=0x000000] - The clear color of the render pass.
	 * @param {?number} [clearAlpha=0] - The clear alpha of the render pass.
	 */
	constructor( scene, camera, clearColor = 0x000000, clearAlpha = 0 ) {

		super();

		/**
		 * The scene to render.
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

		/**
		 * The sample level. Specified as n, where the number of
		 * samples is 2^n, so sampleLevel = 4, is 2^4 samples, 16.
		 *
		 * @type {number}
		 * @default 4
		 */
		this.sampleLevel = 4;

		/**
		 * Whether the pass should be unbiased or not. This property has the most
		 * visible effect when rendering to a RGBA8 buffer because it mitigates
		 * rounding errors. By default RGBA16F is used.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.unbiased = true;

		/**
		 * Whether to use a stencil buffer or not. This property can't
		 * be changed after the first render.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.stencilBuffer = false;

		/**
		 * The clear color of the render pass.
		 *
		 * @type {?(number|Color|string)}
		 * @default 0x000000
		 */
		this.clearColor = clearColor;

		/**
		 * The clear alpha of the render pass.
		 *
		 * @type {?number}
		 * @default 0
		 */
		this.clearAlpha = clearAlpha;

		// internals

		this._sampleRenderTarget = null;

		this._oldClearColor = new Color();

		this._copyUniforms = UniformsUtils.clone( CopyShader.uniforms );

		this._copyMaterial = new ShaderMaterial(	{
			uniforms: this._copyUniforms,
			vertexShader: CopyShader.vertexShader,
			fragmentShader: CopyShader.fragmentShader,
			transparent: true,
			depthTest: false,
			depthWrite: false,
			premultipliedAlpha: true,
			blending: AdditiveBlending
		} );

		this._fsQuad = new FullScreenQuad( this._copyMaterial );

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
	dispose() {

		if ( this._sampleRenderTarget ) {

			this._sampleRenderTarget.dispose();
			this._sampleRenderTarget = null;

		}

		this._copyMaterial.dispose();

		this._fsQuad.dispose();

	}

	/**
	 * Sets the size of the pass.
	 *
	 * @param {number} width - The width to set.
	 * @param {number} height - The height to set.
	 */
	setSize( width, height ) {

		if ( this._sampleRenderTarget )	this._sampleRenderTarget.setSize( width, height );

	}

	/**
	 * Performs the SSAA render pass.
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

		if ( ! this._sampleRenderTarget ) {

			this._sampleRenderTarget = new WebGLRenderTarget( readBuffer.width, readBuffer.height, { type: HalfFloatType, stencilBuffer: this.stencilBuffer } );
			this._sampleRenderTarget.texture.name = 'SSAARenderPass.sample';

		}

		const jitterOffsets = _JitterVectors[ Math.max( 0, Math.min( this.sampleLevel, 5 ) ) ];

		const autoClear = renderer.autoClear;
		renderer.autoClear = false;

		renderer.getClearColor( this._oldClearColor );
		const oldClearAlpha = renderer.getClearAlpha();

		const baseSampleWeight = 1.0 / jitterOffsets.length;
		const roundingRange = 1 / 32;
		this._copyUniforms[ 'tDiffuse' ].value = this._sampleRenderTarget.texture;

		const viewOffset = {

			fullWidth: readBuffer.width,
			fullHeight: readBuffer.height,
			offsetX: 0,
			offsetY: 0,
			width: readBuffer.width,
			height: readBuffer.height

		};

		const originalViewOffset = Object.assign( {}, this.camera.view );

		if ( originalViewOffset.enabled ) Object.assign( viewOffset, originalViewOffset );

		// render the scene multiple times, each slightly jitter offset from the last and accumulate the results.
		for ( let i = 0; i < jitterOffsets.length; i ++ ) {

			const jitterOffset = jitterOffsets[ i ];

			if ( this.camera.setViewOffset ) {

				this.camera.setViewOffset(

					viewOffset.fullWidth, viewOffset.fullHeight,

					viewOffset.offsetX + jitterOffset[ 0 ] * 0.0625, viewOffset.offsetY + jitterOffset[ 1 ] * 0.0625, // 0.0625 = 1 / 16

					viewOffset.width, viewOffset.height

				);

			}

			let sampleWeight = baseSampleWeight;

			if ( this.unbiased ) {

				// the theory is that equal weights for each sample lead to an accumulation of rounding errors.
				// The following equation varies the sampleWeight per sample so that it is uniformly distributed
				// across a range of values whose rounding errors cancel each other out.

				const uniformCenteredDistribution = ( - 0.5 + ( i + 0.5 ) / jitterOffsets.length );
				sampleWeight += roundingRange * uniformCenteredDistribution;

			}

			this._copyUniforms[ 'opacity' ].value = sampleWeight;
			renderer.setClearColor( this.clearColor, this.clearAlpha );
			renderer.setRenderTarget( this._sampleRenderTarget );
			renderer.clear();
			renderer.render( this.scene, this.camera );

			renderer.setRenderTarget( this.renderToScreen ? null : writeBuffer );

			if ( i === 0 ) {

				renderer.setClearColor( 0x000000, 0.0 );
				renderer.clear();

			}

			this._fsQuad.render( renderer );

		}

		if ( this.camera.setViewOffset && originalViewOffset.enabled ) {

			this.camera.setViewOffset(

				originalViewOffset.fullWidth, originalViewOffset.fullHeight,

				originalViewOffset.offsetX, originalViewOffset.offsetY,

				originalViewOffset.width, originalViewOffset.height

			);

		} else if ( this.camera.clearViewOffset ) {

			this.camera.clearViewOffset();

		}

		renderer.autoClear = autoClear;
		renderer.setClearColor( this._oldClearColor, oldClearAlpha );

	}

}
```
</details>

#### Methods

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		if ( this._sampleRenderTarget ) {

			this._sampleRenderTarget.dispose();
			this._sampleRenderTarget = null;

		}

		this._copyMaterial.dispose();

		this._fsQuad.dispose();

	}
```
</details>

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		if ( this._sampleRenderTarget )	this._sampleRenderTarget.setSize( width, height );

	}
```
</details>

##### `render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget): void`

<details><summary>Code</summary>

```ts
render( renderer, writeBuffer, readBuffer/*, deltaTime, maskActive */ ) {

		if ( ! this._sampleRenderTarget ) {

			this._sampleRenderTarget = new WebGLRenderTarget( readBuffer.width, readBuffer.height, { type: HalfFloatType, stencilBuffer: this.stencilBuffer } );
			this._sampleRenderTarget.texture.name = 'SSAARenderPass.sample';

		}

		const jitterOffsets = _JitterVectors[ Math.max( 0, Math.min( this.sampleLevel, 5 ) ) ];

		const autoClear = renderer.autoClear;
		renderer.autoClear = false;

		renderer.getClearColor( this._oldClearColor );
		const oldClearAlpha = renderer.getClearAlpha();

		const baseSampleWeight = 1.0 / jitterOffsets.length;
		const roundingRange = 1 / 32;
		this._copyUniforms[ 'tDiffuse' ].value = this._sampleRenderTarget.texture;

		const viewOffset = {

			fullWidth: readBuffer.width,
			fullHeight: readBuffer.height,
			offsetX: 0,
			offsetY: 0,
			width: readBuffer.width,
			height: readBuffer.height

		};

		const originalViewOffset = Object.assign( {}, this.camera.view );

		if ( originalViewOffset.enabled ) Object.assign( viewOffset, originalViewOffset );

		// render the scene multiple times, each slightly jitter offset from the last and accumulate the results.
		for ( let i = 0; i < jitterOffsets.length; i ++ ) {

			const jitterOffset = jitterOffsets[ i ];

			if ( this.camera.setViewOffset ) {

				this.camera.setViewOffset(

					viewOffset.fullWidth, viewOffset.fullHeight,

					viewOffset.offsetX + jitterOffset[ 0 ] * 0.0625, viewOffset.offsetY + jitterOffset[ 1 ] * 0.0625, // 0.0625 = 1 / 16

					viewOffset.width, viewOffset.height

				);

			}

			let sampleWeight = baseSampleWeight;

			if ( this.unbiased ) {

				// the theory is that equal weights for each sample lead to an accumulation of rounding errors.
				// The following equation varies the sampleWeight per sample so that it is uniformly distributed
				// across a range of values whose rounding errors cancel each other out.

				const uniformCenteredDistribution = ( - 0.5 + ( i + 0.5 ) / jitterOffsets.length );
				sampleWeight += roundingRange * uniformCenteredDistribution;

			}

			this._copyUniforms[ 'opacity' ].value = sampleWeight;
			renderer.setClearColor( this.clearColor, this.clearAlpha );
			renderer.setRenderTarget( this._sampleRenderTarget );
			renderer.clear();
			renderer.render( this.scene, this.camera );

			renderer.setRenderTarget( this.renderToScreen ? null : writeBuffer );

			if ( i === 0 ) {

				renderer.setClearColor( 0x000000, 0.0 );
				renderer.clear();

			}

			this._fsQuad.render( renderer );

		}

		if ( this.camera.setViewOffset && originalViewOffset.enabled ) {

			this.camera.setViewOffset(

				originalViewOffset.fullWidth, originalViewOffset.fullHeight,

				originalViewOffset.offsetX, originalViewOffset.offsetY,

				originalViewOffset.width, originalViewOffset.height

			);

		} else if ( this.camera.clearViewOffset ) {

			this.camera.clearViewOffset();

		}

		renderer.autoClear = autoClear;
		renderer.setClearColor( this._oldClearColor, oldClearAlpha );

	}
```
</details>


---