[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RenderTransitionPass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/RenderTransitionPass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `HalfFloatType` | `three` |
| `ShaderMaterial` | `three` |
| `WebGLRenderTarget` | `three` |
| `FullScreenQuad` | `./Pass.js` |
| `Pass` | `./Pass.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `uniforms` | `any` | let/var | `this._fsQuad.material.uniforms` | ✗ |


---

## Functions

### `RenderTransitionPass.setTransition(value: number | boolean): void`

**JSDoc:**
```typescript
/**
	 * Sets the transition factor. Must be in the range `[0,1]`.
	 * This value determines to what degree both scenes are mixed.
	 *
	 * @param {boolean|number} value - The transition factor.
	 */
```

**Parameters:**

- **`value`** `number | boolean`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setTransition( value ) {

		this.material.uniforms.mixRatio.value = value;

	}
```
</details>

### `RenderTransitionPass.useTexture(value: boolean): void`

**JSDoc:**
```typescript
/**
	 * Toggles the usage of a texture for the effect.
	 *
	 * @param {boolean} value - Whether to use a texture for the transition effect or not.
	 */
```

**Parameters:**

- **`value`** `boolean`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
useTexture( value ) {

		this.material.uniforms.useTexture.value = value ? 1 : 0;

	}
```
</details>

### `RenderTransitionPass.setTexture(value: Texture): void`

**JSDoc:**
```typescript
/**
	 * Sets the effect texture.
	 *
	 * @param {Texture} value - The effect texture.
	 */
```

**Parameters:**

- **`value`** `Texture`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setTexture( value ) {

		this.material.uniforms.tMixTexture.value = value;

	}
```
</details>

### `RenderTransitionPass.setTextureThreshold(value: number | boolean): void`

**JSDoc:**
```typescript
/**
	 * Sets the texture threshold. This value defined how strong the texture effects
	 * the transition. Must be in the range `[0,1]` (0 means full effect, 1 means no effect).
	 *
	 * @param {boolean|number} value - The threshold value.
	 */
```

**Parameters:**

- **`value`** `number | boolean`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setTextureThreshold( value ) {

		this.material.uniforms.threshold.value = value;

	}
```
</details>

### `RenderTransitionPass.setSize(width: number, height: number): void`

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

- `this._renderTargetA.setSize`
- `this._renderTargetB.setSize`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this._renderTargetA.setSize( width, height );
		this._renderTargetB.setSize( width, height );

	}
```
</details>

### `RenderTransitionPass.render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget): void`

**JSDoc:**
```typescript
/**
	 * Performs the transition pass.
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

**Returns:** `void`

**Calls:**

- `renderer.setRenderTarget`
- `renderer.render`
- `renderer.clear`
- `this._fsQuad.render`

<details><summary>Code</summary>

```typescript
render( renderer, writeBuffer/*, readBuffer , deltaTime, maskActive */ ) {

		renderer.setRenderTarget( this._renderTargetA );
		renderer.render( this.sceneA, this.cameraA );
		renderer.setRenderTarget( this._renderTargetB );
		renderer.render( this.sceneB, this.cameraB );

		const uniforms = this._fsQuad.material.uniforms;
		uniforms.tDiffuse1.value = this._renderTargetA.texture;
		uniforms.tDiffuse2.value = this._renderTargetB.texture;

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );
			renderer.clear();

		} else {

			renderer.setRenderTarget( writeBuffer );
			if ( this.clear ) renderer.clear();

		}

		this._fsQuad.render( renderer );

	}
```
</details>

### `RenderTransitionPass.dispose(): void`

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
- `this._renderTargetA.dispose`
- `this._renderTargetB.dispose`
- `this._fsQuad.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.material.dispose();

		this._renderTargetA.dispose();
		this._renderTargetB.dispose();
		this._fsQuad.dispose();

	}
```
</details>

### `RenderTransitionPass._createMaterial(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
_createMaterial() {

		return new ShaderMaterial( {
			uniforms: {
				tDiffuse1: {
					value: null
				},
				tDiffuse2: {
					value: null
				},
				mixRatio: {
					value: 0.0
				},
				threshold: {
					value: 0.1
				},
				useTexture: {
					value: 1
				},
				tMixTexture: {
					value: null
				}
			},
			vertexShader: /* glsl */`
				varying vec2 vUv;

				void main() {

					vUv = vec2( uv.x, uv.y );
					gl_Position = projectionMatrix * modelViewMatrix * vec4( position, 1.0 );

				}
			`,
			fragmentShader: /* glsl */`
				uniform float mixRatio;

				uniform sampler2D tDiffuse1;
				uniform sampler2D tDiffuse2;
				uniform sampler2D tMixTexture;

				uniform int useTexture;
				uniform float threshold;

				varying vec2 vUv;

				void main() {

					vec4 texel1 = texture2D( tDiffuse1, vUv );
					vec4 texel2 = texture2D( tDiffuse2, vUv );

					if (useTexture == 1) {

						vec4 transitionTexel = texture2D( tMixTexture, vUv );
						float r = mixRatio * ( 1.0 + threshold * 2.0 ) - threshold;
						float mixf = clamp( ( transitionTexel.r - r ) * ( 1.0 / threshold ), 0.0, 1.0 );

						gl_FragColor = mix( texel1, texel2, mixf );

					} else {

						gl_FragColor = mix( texel2, texel1, mixRatio );

					}

				}
			`
		} );

	}
```
</details>


---

## Classes

### `RenderTransitionPass`

<details><summary>Class Code</summary>

```ts
class RenderTransitionPass extends Pass {

	/**
	 * Constructs a render transition pass.
	 *
	 * @param {Scene} sceneA - The first scene.
	 * @param {Camera} cameraA - The camera of the first scene.
	 * @param {Scene} sceneB - The second scene.
	 * @param {Camera} cameraB - The camera of the second scene.
	 */
	constructor( sceneA, cameraA, sceneB, cameraB ) {

		super();

		/**
		 * The first scene.
		 *
		 * @type {Scene}
		 */
		this.sceneA = sceneA;


		/**
		 * The camera of the first scene.
		 *
		 * @type {Camera}
		 */
		this.cameraA = cameraA;

		/**
		 * The second scene.
		 *
		 * @type {Scene}
		 */
		this.sceneB = sceneB;

		/**
		 * The camera of the second scene.
		 *
		 * @type {Camera}
		 */
		this.cameraB = cameraB;

		/**
		 * The pass material.
		 *
		 * @type {ShaderMaterial}
		 */
		this.material = this._createMaterial();

		// internals

		this._renderTargetA = new WebGLRenderTarget();
		this._renderTargetA.texture.type = HalfFloatType;
		this._renderTargetB = new WebGLRenderTarget();
		this._renderTargetB.texture.type = HalfFloatType;

		this._fsQuad = new FullScreenQuad( this.material );

	}

	/**
	 * Sets the transition factor. Must be in the range `[0,1]`.
	 * This value determines to what degree both scenes are mixed.
	 *
	 * @param {boolean|number} value - The transition factor.
	 */
	setTransition( value ) {

		this.material.uniforms.mixRatio.value = value;

	}

	/**
	 * Toggles the usage of a texture for the effect.
	 *
	 * @param {boolean} value - Whether to use a texture for the transition effect or not.
	 */
	useTexture( value ) {

		this.material.uniforms.useTexture.value = value ? 1 : 0;

	}

	/**
	 * Sets the effect texture.
	 *
	 * @param {Texture} value - The effect texture.
	 */
	setTexture( value ) {

		this.material.uniforms.tMixTexture.value = value;

	}

	/**
	 * Sets the texture threshold. This value defined how strong the texture effects
	 * the transition. Must be in the range `[0,1]` (0 means full effect, 1 means no effect).
	 *
	 * @param {boolean|number} value - The threshold value.
	 */
	setTextureThreshold( value ) {

		this.material.uniforms.threshold.value = value;

	}

	/**
	 * Sets the size of the pass.
	 *
	 * @param {number} width - The width to set.
	 * @param {number} height - The height to set.
	 */
	setSize( width, height ) {

		this._renderTargetA.setSize( width, height );
		this._renderTargetB.setSize( width, height );

	}

	/**
	 * Performs the transition pass.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {WebGLRenderTarget} writeBuffer - The write buffer. This buffer is intended as the rendering
	 * destination for the pass.
	 * @param {WebGLRenderTarget} readBuffer - The read buffer. The pass can access the result from the
	 * previous pass from this buffer.
	 * @param {number} deltaTime - The delta time in seconds.
	 * @param {boolean} maskActive - Whether masking is active or not.
	 */
	render( renderer, writeBuffer/*, readBuffer , deltaTime, maskActive */ ) {

		renderer.setRenderTarget( this._renderTargetA );
		renderer.render( this.sceneA, this.cameraA );
		renderer.setRenderTarget( this._renderTargetB );
		renderer.render( this.sceneB, this.cameraB );

		const uniforms = this._fsQuad.material.uniforms;
		uniforms.tDiffuse1.value = this._renderTargetA.texture;
		uniforms.tDiffuse2.value = this._renderTargetB.texture;

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );
			renderer.clear();

		} else {

			renderer.setRenderTarget( writeBuffer );
			if ( this.clear ) renderer.clear();

		}

		this._fsQuad.render( renderer );

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
	dispose() {

		this.material.dispose();

		this._renderTargetA.dispose();
		this._renderTargetB.dispose();
		this._fsQuad.dispose();

	}

	// internals

	_createMaterial() {

		return new ShaderMaterial( {
			uniforms: {
				tDiffuse1: {
					value: null
				},
				tDiffuse2: {
					value: null
				},
				mixRatio: {
					value: 0.0
				},
				threshold: {
					value: 0.1
				},
				useTexture: {
					value: 1
				},
				tMixTexture: {
					value: null
				}
			},
			vertexShader: /* glsl */`
				varying vec2 vUv;

				void main() {

					vUv = vec2( uv.x, uv.y );
					gl_Position = projectionMatrix * modelViewMatrix * vec4( position, 1.0 );

				}
			`,
			fragmentShader: /* glsl */`
				uniform float mixRatio;

				uniform sampler2D tDiffuse1;
				uniform sampler2D tDiffuse2;
				uniform sampler2D tMixTexture;

				uniform int useTexture;
				uniform float threshold;

				varying vec2 vUv;

				void main() {

					vec4 texel1 = texture2D( tDiffuse1, vUv );
					vec4 texel2 = texture2D( tDiffuse2, vUv );

					if (useTexture == 1) {

						vec4 transitionTexel = texture2D( tMixTexture, vUv );
						float r = mixRatio * ( 1.0 + threshold * 2.0 ) - threshold;
						float mixf = clamp( ( transitionTexel.r - r ) * ( 1.0 / threshold ), 0.0, 1.0 );

						gl_FragColor = mix( texel1, texel2, mixf );

					} else {

						gl_FragColor = mix( texel2, texel1, mixRatio );

					}

				}
			`
		} );

	}

}
```
</details>

#### Methods

##### `setTransition(value: number | boolean): void`

<details><summary>Code</summary>

```ts
setTransition( value ) {

		this.material.uniforms.mixRatio.value = value;

	}
```
</details>

##### `useTexture(value: boolean): void`

<details><summary>Code</summary>

```ts
useTexture( value ) {

		this.material.uniforms.useTexture.value = value ? 1 : 0;

	}
```
</details>

##### `setTexture(value: Texture): void`

<details><summary>Code</summary>

```ts
setTexture( value ) {

		this.material.uniforms.tMixTexture.value = value;

	}
```
</details>

##### `setTextureThreshold(value: number | boolean): void`

<details><summary>Code</summary>

```ts
setTextureThreshold( value ) {

		this.material.uniforms.threshold.value = value;

	}
```
</details>

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		this._renderTargetA.setSize( width, height );
		this._renderTargetB.setSize( width, height );

	}
```
</details>

##### `render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget): void`

<details><summary>Code</summary>

```ts
render( renderer, writeBuffer/*, readBuffer , deltaTime, maskActive */ ) {

		renderer.setRenderTarget( this._renderTargetA );
		renderer.render( this.sceneA, this.cameraA );
		renderer.setRenderTarget( this._renderTargetB );
		renderer.render( this.sceneB, this.cameraB );

		const uniforms = this._fsQuad.material.uniforms;
		uniforms.tDiffuse1.value = this._renderTargetA.texture;
		uniforms.tDiffuse2.value = this._renderTargetB.texture;

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );
			renderer.clear();

		} else {

			renderer.setRenderTarget( writeBuffer );
			if ( this.clear ) renderer.clear();

		}

		this._fsQuad.render( renderer );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.material.dispose();

		this._renderTargetA.dispose();
		this._renderTargetB.dispose();
		this._fsQuad.dispose();

	}
```
</details>

##### `_createMaterial(): any`

<details><summary>Code</summary>

```ts
_createMaterial() {

		return new ShaderMaterial( {
			uniforms: {
				tDiffuse1: {
					value: null
				},
				tDiffuse2: {
					value: null
				},
				mixRatio: {
					value: 0.0
				},
				threshold: {
					value: 0.1
				},
				useTexture: {
					value: 1
				},
				tMixTexture: {
					value: null
				}
			},
			vertexShader: /* glsl */`
				varying vec2 vUv;

				void main() {

					vUv = vec2( uv.x, uv.y );
					gl_Position = projectionMatrix * modelViewMatrix * vec4( position, 1.0 );

				}
			`,
			fragmentShader: /* glsl */`
				uniform float mixRatio;

				uniform sampler2D tDiffuse1;
				uniform sampler2D tDiffuse2;
				uniform sampler2D tMixTexture;

				uniform int useTexture;
				uniform float threshold;

				varying vec2 vUv;

				void main() {

					vec4 texel1 = texture2D( tDiffuse1, vUv );
					vec4 texel2 = texture2D( tDiffuse2, vUv );

					if (useTexture == 1) {

						vec4 transitionTexel = texture2D( tMixTexture, vUv );
						float r = mixRatio * ( 1.0 + threshold * 2.0 ) - threshold;
						float mixf = clamp( ( transitionTexel.r - r ) * ( 1.0 / threshold ), 0.0, 1.0 );

						gl_FragColor = mix( texel1, texel2, mixf );

					} else {

						gl_FragColor = mix( texel2, texel1, mixRatio );

					}

				}
			`
		} );

	}
```
</details>


---