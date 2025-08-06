[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TAARenderPass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/TAARenderPass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `HalfFloatType` | `three` |
| `WebGLRenderTarget` | `three` |
| `SSAARenderPass` | `./SSAARenderPass.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `jitterOffsets` | `number[][]` | let/var | `_JitterVectors[ 5 ]` | ✗ |
| `autoClear` | `any` | let/var | `renderer.autoClear` | ✗ |
| `sampleWeight` | `number` | let/var | `1.0 / ( jitterOffsets.length )` | ✗ |
| `j` | `number` | let/var | `this.accumulateIndex` | ✗ |
| `jitterOffset` | `number[]` | let/var | `jitterOffsets[ j ]` | ✗ |
| `accumulationWeight` | `number` | let/var | `this.accumulateIndex * sampleWeight` | ✗ |
| `_JitterVectors` | `number[][][]` | let/var | `[ [ [ 0, 0 ] ], [ [ 4, 4 ], [ - 4, - 4 ] ], [ [ - 2, - 6 ], [ 6, - 2 ], [ - 6...` | ✗ |


---

## Functions

### `TAARenderPass.render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget, deltaTime: number): void`

**JSDoc:**
```typescript
/**
	 * Performs the TAA render pass.
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

**Returns:** `void`

**Calls:**

- `super.render`
- `renderer.getClearColor`
- `renderer.getClearAlpha`
- `Math.pow`
- `this.camera.setViewOffset`
- `renderer.setRenderTarget`
- `renderer.setClearColor`
- `renderer.clear`
- `renderer.render`
- `this._fsQuad.render`
- `this.camera.clearViewOffset`

**Internal Comments:**
```
// render the scene multiple times, each slightly jitter offset from the last and accumulate the results. (x2)
```

<details><summary>Code</summary>

```typescript
render( renderer, writeBuffer, readBuffer, deltaTime/*, maskActive*/ ) {

		if ( this.accumulate === false ) {

			super.render( renderer, writeBuffer, readBuffer, deltaTime );

			this.accumulateIndex = - 1;
			return;

		}

		const jitterOffsets = _JitterVectors[ 5 ];

		if ( this._sampleRenderTarget === null ) {

			this._sampleRenderTarget = new WebGLRenderTarget( readBuffer.width, readBuffer.height, { type: HalfFloatType } );
			this._sampleRenderTarget.texture.name = 'TAARenderPass.sample';

		}

		if ( this._holdRenderTarget === null ) {

			this._holdRenderTarget = new WebGLRenderTarget( readBuffer.width, readBuffer.height, { type: HalfFloatType } );
			this._holdRenderTarget.texture.name = 'TAARenderPass.hold';

		}

		if ( this.accumulateIndex === - 1 ) {

			super.render( renderer, this._holdRenderTarget, readBuffer, deltaTime );

			this.accumulateIndex = 0;

		}

		const autoClear = renderer.autoClear;
		renderer.autoClear = false;

		renderer.getClearColor( this._oldClearColor );
		const oldClearAlpha = renderer.getClearAlpha();

		const sampleWeight = 1.0 / ( jitterOffsets.length );

		if ( this.accumulateIndex >= 0 && this.accumulateIndex < jitterOffsets.length ) {

			this._copyUniforms[ 'opacity' ].value = sampleWeight;
			this._copyUniforms[ 'tDiffuse' ].value = writeBuffer.texture;

			// render the scene multiple times, each slightly jitter offset from the last and accumulate the results.
			const numSamplesPerFrame = Math.pow( 2, this.sampleLevel );
			for ( let i = 0; i < numSamplesPerFrame; i ++ ) {

				const j = this.accumulateIndex;
				const jitterOffset = jitterOffsets[ j ];

				if ( this.camera.setViewOffset ) {

					this.camera.setViewOffset( readBuffer.width, readBuffer.height,
						jitterOffset[ 0 ] * 0.0625, jitterOffset[ 1 ] * 0.0625, // 0.0625 = 1 / 16
						readBuffer.width, readBuffer.height );

				}

				renderer.setRenderTarget( writeBuffer );
				renderer.setClearColor( this.clearColor, this.clearAlpha );
				renderer.clear();
				renderer.render( this.scene, this.camera );

				renderer.setRenderTarget( this._sampleRenderTarget );
				if ( this.accumulateIndex === 0 ) {

					renderer.setClearColor( 0x000000, 0.0 );
					renderer.clear();

				}

				this._fsQuad.render( renderer );

				this.accumulateIndex ++;

				if ( this.accumulateIndex >= jitterOffsets.length ) break;

			}

			if ( this.camera.clearViewOffset ) this.camera.clearViewOffset();

		}

		renderer.setClearColor( this.clearColor, this.clearAlpha );
		const accumulationWeight = this.accumulateIndex * sampleWeight;

		if ( accumulationWeight > 0 ) {

			this._copyUniforms[ 'opacity' ].value = 1.0;
			this._copyUniforms[ 'tDiffuse' ].value = this._sampleRenderTarget.texture;
			renderer.setRenderTarget( writeBuffer );
			renderer.clear();
			this._fsQuad.render( renderer );

		}

		if ( accumulationWeight < 1.0 ) {

			this._copyUniforms[ 'opacity' ].value = 1.0 - accumulationWeight;
			this._copyUniforms[ 'tDiffuse' ].value = this._holdRenderTarget.texture;
			renderer.setRenderTarget( writeBuffer );
			this._fsQuad.render( renderer );

		}

		renderer.autoClear = autoClear;
		renderer.setClearColor( this._oldClearColor, oldClearAlpha );

	}
```
</details>

### `TAARenderPass.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `super.dispose`
- `this._holdRenderTarget.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		super.dispose();

		if ( this._holdRenderTarget ) this._holdRenderTarget.dispose();

	}
```
</details>


---

## Classes

### `TAARenderPass`

<details><summary>Class Code</summary>

```ts
class TAARenderPass extends SSAARenderPass {

	/**
	 * Constructs a new TAA render pass.
	 *
	 * @param {Scene} scene - The scene to render.
	 * @param {Camera} camera - The camera.
	 * @param {?(number|Color|string)} [clearColor=0x000000] - The clear color of the render pass.
	 * @param {?number} [clearAlpha=0] - The clear alpha of the render pass.
	 */
	constructor( scene, camera, clearColor, clearAlpha ) {

		super( scene, camera, clearColor, clearAlpha );

		/**
		 * Overwritten and set to 0 by default.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.sampleLevel = 0;

		/**
		 * Whether to accumulate frames or not. This enables
		 * the TAA.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.accumulate = false;

		/**
		 * The accumulation index.
		 *
		 * @type {number}
		 * @default -1
		 */
		this.accumulateIndex = - 1;

		// internals

		this._sampleRenderTarget = null;
		this._holdRenderTarget = null;

	}

	/**
	 * Performs the TAA render pass.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {WebGLRenderTarget} writeBuffer - The write buffer. This buffer is intended as the rendering
	 * destination for the pass.
	 * @param {WebGLRenderTarget} readBuffer - The read buffer. The pass can access the result from the
	 * previous pass from this buffer.
	 * @param {number} deltaTime - The delta time in seconds.
	 * @param {boolean} maskActive - Whether masking is active or not.
	 */
	render( renderer, writeBuffer, readBuffer, deltaTime/*, maskActive*/ ) {

		if ( this.accumulate === false ) {

			super.render( renderer, writeBuffer, readBuffer, deltaTime );

			this.accumulateIndex = - 1;
			return;

		}

		const jitterOffsets = _JitterVectors[ 5 ];

		if ( this._sampleRenderTarget === null ) {

			this._sampleRenderTarget = new WebGLRenderTarget( readBuffer.width, readBuffer.height, { type: HalfFloatType } );
			this._sampleRenderTarget.texture.name = 'TAARenderPass.sample';

		}

		if ( this._holdRenderTarget === null ) {

			this._holdRenderTarget = new WebGLRenderTarget( readBuffer.width, readBuffer.height, { type: HalfFloatType } );
			this._holdRenderTarget.texture.name = 'TAARenderPass.hold';

		}

		if ( this.accumulateIndex === - 1 ) {

			super.render( renderer, this._holdRenderTarget, readBuffer, deltaTime );

			this.accumulateIndex = 0;

		}

		const autoClear = renderer.autoClear;
		renderer.autoClear = false;

		renderer.getClearColor( this._oldClearColor );
		const oldClearAlpha = renderer.getClearAlpha();

		const sampleWeight = 1.0 / ( jitterOffsets.length );

		if ( this.accumulateIndex >= 0 && this.accumulateIndex < jitterOffsets.length ) {

			this._copyUniforms[ 'opacity' ].value = sampleWeight;
			this._copyUniforms[ 'tDiffuse' ].value = writeBuffer.texture;

			// render the scene multiple times, each slightly jitter offset from the last and accumulate the results.
			const numSamplesPerFrame = Math.pow( 2, this.sampleLevel );
			for ( let i = 0; i < numSamplesPerFrame; i ++ ) {

				const j = this.accumulateIndex;
				const jitterOffset = jitterOffsets[ j ];

				if ( this.camera.setViewOffset ) {

					this.camera.setViewOffset( readBuffer.width, readBuffer.height,
						jitterOffset[ 0 ] * 0.0625, jitterOffset[ 1 ] * 0.0625, // 0.0625 = 1 / 16
						readBuffer.width, readBuffer.height );

				}

				renderer.setRenderTarget( writeBuffer );
				renderer.setClearColor( this.clearColor, this.clearAlpha );
				renderer.clear();
				renderer.render( this.scene, this.camera );

				renderer.setRenderTarget( this._sampleRenderTarget );
				if ( this.accumulateIndex === 0 ) {

					renderer.setClearColor( 0x000000, 0.0 );
					renderer.clear();

				}

				this._fsQuad.render( renderer );

				this.accumulateIndex ++;

				if ( this.accumulateIndex >= jitterOffsets.length ) break;

			}

			if ( this.camera.clearViewOffset ) this.camera.clearViewOffset();

		}

		renderer.setClearColor( this.clearColor, this.clearAlpha );
		const accumulationWeight = this.accumulateIndex * sampleWeight;

		if ( accumulationWeight > 0 ) {

			this._copyUniforms[ 'opacity' ].value = 1.0;
			this._copyUniforms[ 'tDiffuse' ].value = this._sampleRenderTarget.texture;
			renderer.setRenderTarget( writeBuffer );
			renderer.clear();
			this._fsQuad.render( renderer );

		}

		if ( accumulationWeight < 1.0 ) {

			this._copyUniforms[ 'opacity' ].value = 1.0 - accumulationWeight;
			this._copyUniforms[ 'tDiffuse' ].value = this._holdRenderTarget.texture;
			renderer.setRenderTarget( writeBuffer );
			this._fsQuad.render( renderer );

		}

		renderer.autoClear = autoClear;
		renderer.setClearColor( this._oldClearColor, oldClearAlpha );

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
	dispose() {

		super.dispose();

		if ( this._holdRenderTarget ) this._holdRenderTarget.dispose();

	}

}
```
</details>

#### Methods

##### `render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget, deltaTime: number): void`

<details><summary>Code</summary>

```ts
render( renderer, writeBuffer, readBuffer, deltaTime/*, maskActive*/ ) {

		if ( this.accumulate === false ) {

			super.render( renderer, writeBuffer, readBuffer, deltaTime );

			this.accumulateIndex = - 1;
			return;

		}

		const jitterOffsets = _JitterVectors[ 5 ];

		if ( this._sampleRenderTarget === null ) {

			this._sampleRenderTarget = new WebGLRenderTarget( readBuffer.width, readBuffer.height, { type: HalfFloatType } );
			this._sampleRenderTarget.texture.name = 'TAARenderPass.sample';

		}

		if ( this._holdRenderTarget === null ) {

			this._holdRenderTarget = new WebGLRenderTarget( readBuffer.width, readBuffer.height, { type: HalfFloatType } );
			this._holdRenderTarget.texture.name = 'TAARenderPass.hold';

		}

		if ( this.accumulateIndex === - 1 ) {

			super.render( renderer, this._holdRenderTarget, readBuffer, deltaTime );

			this.accumulateIndex = 0;

		}

		const autoClear = renderer.autoClear;
		renderer.autoClear = false;

		renderer.getClearColor( this._oldClearColor );
		const oldClearAlpha = renderer.getClearAlpha();

		const sampleWeight = 1.0 / ( jitterOffsets.length );

		if ( this.accumulateIndex >= 0 && this.accumulateIndex < jitterOffsets.length ) {

			this._copyUniforms[ 'opacity' ].value = sampleWeight;
			this._copyUniforms[ 'tDiffuse' ].value = writeBuffer.texture;

			// render the scene multiple times, each slightly jitter offset from the last and accumulate the results.
			const numSamplesPerFrame = Math.pow( 2, this.sampleLevel );
			for ( let i = 0; i < numSamplesPerFrame; i ++ ) {

				const j = this.accumulateIndex;
				const jitterOffset = jitterOffsets[ j ];

				if ( this.camera.setViewOffset ) {

					this.camera.setViewOffset( readBuffer.width, readBuffer.height,
						jitterOffset[ 0 ] * 0.0625, jitterOffset[ 1 ] * 0.0625, // 0.0625 = 1 / 16
						readBuffer.width, readBuffer.height );

				}

				renderer.setRenderTarget( writeBuffer );
				renderer.setClearColor( this.clearColor, this.clearAlpha );
				renderer.clear();
				renderer.render( this.scene, this.camera );

				renderer.setRenderTarget( this._sampleRenderTarget );
				if ( this.accumulateIndex === 0 ) {

					renderer.setClearColor( 0x000000, 0.0 );
					renderer.clear();

				}

				this._fsQuad.render( renderer );

				this.accumulateIndex ++;

				if ( this.accumulateIndex >= jitterOffsets.length ) break;

			}

			if ( this.camera.clearViewOffset ) this.camera.clearViewOffset();

		}

		renderer.setClearColor( this.clearColor, this.clearAlpha );
		const accumulationWeight = this.accumulateIndex * sampleWeight;

		if ( accumulationWeight > 0 ) {

			this._copyUniforms[ 'opacity' ].value = 1.0;
			this._copyUniforms[ 'tDiffuse' ].value = this._sampleRenderTarget.texture;
			renderer.setRenderTarget( writeBuffer );
			renderer.clear();
			this._fsQuad.render( renderer );

		}

		if ( accumulationWeight < 1.0 ) {

			this._copyUniforms[ 'opacity' ].value = 1.0 - accumulationWeight;
			this._copyUniforms[ 'tDiffuse' ].value = this._holdRenderTarget.texture;
			renderer.setRenderTarget( writeBuffer );
			this._fsQuad.render( renderer );

		}

		renderer.autoClear = autoClear;
		renderer.setClearColor( this._oldClearColor, oldClearAlpha );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		super.dispose();

		if ( this._holdRenderTarget ) this._holdRenderTarget.dispose();

	}
```
</details>


---