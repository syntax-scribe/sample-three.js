[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RenderPixelatedPass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/RenderPixelatedPass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `WebGLRenderTarget` | `three` |
| `MeshNormalMaterial` | `three` |
| `ShaderMaterial` | `three` |
| `Vector2` | `three` |
| `Vector4` | `three` |
| `DepthTexture` | `three` |
| `NearestFilter` | `three` |
| `HalfFloatType` | `three` |
| `Pass` | `./Pass.js` |
| `FullScreenQuad` | `./Pass.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `uniforms` | `any` | let/var | `this._fsQuad.material.uniforms` | ✗ |
| `overrideMaterial_old` | `any` | let/var | `this.scene.overrideMaterial` | ✗ |


---

## Functions

### `RenderPixelatedPass.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this._beautyRenderTarget.dispose`
- `this._normalRenderTarget.dispose`
- `this.pixelatedMaterial.dispose`
- `this._normalMaterial.dispose`
- `this._fsQuad.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this._beautyRenderTarget.dispose();
		this._normalRenderTarget.dispose();

		this.pixelatedMaterial.dispose();
		this._normalMaterial.dispose();

		this._fsQuad.dispose();

	}
```
</details>

### `RenderPixelatedPass.setSize(width: number, height: number): void`

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

- `this._resolution.set`
- `this._renderResolution.set`
- `this._beautyRenderTarget.setSize`
- `this._normalRenderTarget.setSize`
- `this._fsQuad.material.uniforms.resolution.value.set`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this._resolution.set( width, height );
		this._renderResolution.set( ( width / this.pixelSize ) | 0, ( height / this.pixelSize ) | 0 );
		const { x, y } = this._renderResolution;
		this._beautyRenderTarget.setSize( x, y );
		this._normalRenderTarget.setSize( x, y );
		this._fsQuad.material.uniforms.resolution.value.set( x, y, 1 / x, 1 / y );

	}
```
</details>

### `RenderPixelatedPass.setPixelSize(pixelSize: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the effect's pixel size.
	 *
	 * @param {number} pixelSize - The pixel size to set.
	 */
```

**Parameters:**

- **`pixelSize`** `number`

**Returns:** `void`

**Calls:**

- `this.setSize`

<details><summary>Code</summary>

```typescript
setPixelSize( pixelSize ) {

		this.pixelSize = pixelSize;
		this.setSize( this._resolution.x, this._resolution.y );

	}
```
</details>

### `RenderPixelatedPass.render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget): void`

**JSDoc:**
```typescript
/**
	 * Performs the pixelation pass.
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

		const uniforms = this._fsQuad.material.uniforms;
		uniforms.normalEdgeStrength.value = this.normalEdgeStrength;
		uniforms.depthEdgeStrength.value = this.depthEdgeStrength;

		renderer.setRenderTarget( this._beautyRenderTarget );
		renderer.render( this.scene, this.camera );

		const overrideMaterial_old = this.scene.overrideMaterial;
		renderer.setRenderTarget( this._normalRenderTarget );
		this.scene.overrideMaterial = this._normalMaterial;
		renderer.render( this.scene, this.camera );
		this.scene.overrideMaterial = overrideMaterial_old;

		uniforms.tDiffuse.value = this._beautyRenderTarget.texture;
		uniforms.tDepth.value = this._beautyRenderTarget.depthTexture;
		uniforms.tNormal.value = this._normalRenderTarget.texture;

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );

		} else {

			renderer.setRenderTarget( writeBuffer );

			if ( this.clear ) renderer.clear();

		}

		this._fsQuad.render( renderer );

	}
```
</details>

### `RenderPixelatedPass._createPixelatedMaterial(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
_createPixelatedMaterial() {

		return new ShaderMaterial( {
			uniforms: {
				tDiffuse: { value: null },
				tDepth: { value: null },
				tNormal: { value: null },
				resolution: { value: new Vector4() },
				normalEdgeStrength: { value: 0 },
				depthEdgeStrength: { value: 0 }
			},
			vertexShader: /* glsl */`
				varying vec2 vUv;

				void main() {

					vUv = uv;
					gl_Position = projectionMatrix * modelViewMatrix * vec4( position, 1.0 );

				}
			`,
			fragmentShader: /* glsl */`
				uniform sampler2D tDiffuse;
				uniform sampler2D tDepth;
				uniform sampler2D tNormal;
				uniform vec4 resolution;
				uniform float normalEdgeStrength;
				uniform float depthEdgeStrength;
				varying vec2 vUv;

				float getDepth(int x, int y) {

					return texture2D( tDepth, vUv + vec2(x, y) * resolution.zw ).r;

				}

				vec3 getNormal(int x, int y) {

					return texture2D( tNormal, vUv + vec2(x, y) * resolution.zw ).rgb * 2.0 - 1.0;

				}

				float depthEdgeIndicator(float depth, vec3 normal) {

					float diff = 0.0;
					diff += clamp(getDepth(1, 0) - depth, 0.0, 1.0);
					diff += clamp(getDepth(-1, 0) - depth, 0.0, 1.0);
					diff += clamp(getDepth(0, 1) - depth, 0.0, 1.0);
					diff += clamp(getDepth(0, -1) - depth, 0.0, 1.0);
					return floor(smoothstep(0.01, 0.02, diff) * 2.) / 2.;

				}

				float neighborNormalEdgeIndicator(int x, int y, float depth, vec3 normal) {

					float depthDiff = getDepth(x, y) - depth;
					vec3 neighborNormal = getNormal(x, y);

					// Edge pixels should yield to faces who's normals are closer to the bias normal.
					vec3 normalEdgeBias = vec3(1., 1., 1.); // This should probably be a parameter.
					float normalDiff = dot(normal - neighborNormal, normalEdgeBias);
					float normalIndicator = clamp(smoothstep(-.01, .01, normalDiff), 0.0, 1.0);

					// Only the shallower pixel should detect the normal edge.
					float depthIndicator = clamp(sign(depthDiff * .25 + .0025), 0.0, 1.0);

					return (1.0 - dot(normal, neighborNormal)) * depthIndicator * normalIndicator;

				}

				float normalEdgeIndicator(float depth, vec3 normal) {

					float indicator = 0.0;

					indicator += neighborNormalEdgeIndicator(0, -1, depth, normal);
					indicator += neighborNormalEdgeIndicator(0, 1, depth, normal);
					indicator += neighborNormalEdgeIndicator(-1, 0, depth, normal);
					indicator += neighborNormalEdgeIndicator(1, 0, depth, normal);

					return step(0.1, indicator);

				}

				void main() {

					vec4 texel = texture2D( tDiffuse, vUv );

					float depth = 0.0;
					vec3 normal = vec3(0.0);

					if (depthEdgeStrength > 0.0 || normalEdgeStrength > 0.0) {

						depth = getDepth(0, 0);
						normal = getNormal(0, 0);

					}

					float dei = 0.0;
					if (depthEdgeStrength > 0.0)
						dei = depthEdgeIndicator(depth, normal);

					float nei = 0.0;
					if (normalEdgeStrength > 0.0)
						nei = normalEdgeIndicator(depth, normal);

					float Strength = dei > 0.0 ? (1.0 - depthEdgeStrength * dei) : (1.0 + normalEdgeStrength * nei);

					gl_FragColor = texel * Strength;

				}
			`
		} );

	}
```
</details>


---

## Classes

### `RenderPixelatedPass`

<details><summary>Class Code</summary>

```ts
class RenderPixelatedPass extends Pass {

	/**
	 * Constructs a new render pixelated pass.
	 *
	 * @param {number} pixelSize - The effect's pixel size.
	 * @param {Scene} scene - The scene to render.
	 * @param {Camera} camera - The camera.
	 * @param {{normalEdgeStrength:number,depthEdgeStrength:number}} options - The pass options.
	 */
	constructor( pixelSize, scene, camera, options = {} ) {

		super();

		/**
		 * The effect's pixel size.
		 *
		 * @type {number}
		 */
		this.pixelSize = pixelSize;

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
		 * The normal edge strength.
		 *
		 * @type {number}
		 * @default 0.3
		 */
		this.normalEdgeStrength = options.normalEdgeStrength || 0.3;

		/**
		 * The normal edge strength.
		 *
		 * @type {number}
		 * @default 0.4
		 */
		this.depthEdgeStrength = options.depthEdgeStrength || 0.4;

		/**
		 * The pixelated material.
		 *
		 * @type {ShaderMaterial}
		 */
		this.pixelatedMaterial = this._createPixelatedMaterial();

		// internals

		this._resolution = new Vector2();
		this._renderResolution = new Vector2();

		this._normalMaterial = new MeshNormalMaterial();

		this._beautyRenderTarget = new WebGLRenderTarget();
		this._beautyRenderTarget.texture.minFilter = NearestFilter;
		this._beautyRenderTarget.texture.magFilter = NearestFilter;
		this._beautyRenderTarget.texture.type = HalfFloatType;
		this._beautyRenderTarget.depthTexture = new DepthTexture();

		this._normalRenderTarget = new WebGLRenderTarget();
		this._normalRenderTarget.texture.minFilter = NearestFilter;
		this._normalRenderTarget.texture.magFilter = NearestFilter;
		this._normalRenderTarget.texture.type = HalfFloatType;

		this._fsQuad = new FullScreenQuad( this.pixelatedMaterial );

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
	dispose() {

		this._beautyRenderTarget.dispose();
		this._normalRenderTarget.dispose();

		this.pixelatedMaterial.dispose();
		this._normalMaterial.dispose();

		this._fsQuad.dispose();

	}

	/**
	 * Sets the size of the pass.
	 *
	 * @param {number} width - The width to set.
	 * @param {number} height - The height to set.
	 */
	setSize( width, height ) {

		this._resolution.set( width, height );
		this._renderResolution.set( ( width / this.pixelSize ) | 0, ( height / this.pixelSize ) | 0 );
		const { x, y } = this._renderResolution;
		this._beautyRenderTarget.setSize( x, y );
		this._normalRenderTarget.setSize( x, y );
		this._fsQuad.material.uniforms.resolution.value.set( x, y, 1 / x, 1 / y );

	}

	/**
	 * Sets the effect's pixel size.
	 *
	 * @param {number} pixelSize - The pixel size to set.
	 */
	setPixelSize( pixelSize ) {

		this.pixelSize = pixelSize;
		this.setSize( this._resolution.x, this._resolution.y );

	}

	/**
	 * Performs the pixelation pass.
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

		const uniforms = this._fsQuad.material.uniforms;
		uniforms.normalEdgeStrength.value = this.normalEdgeStrength;
		uniforms.depthEdgeStrength.value = this.depthEdgeStrength;

		renderer.setRenderTarget( this._beautyRenderTarget );
		renderer.render( this.scene, this.camera );

		const overrideMaterial_old = this.scene.overrideMaterial;
		renderer.setRenderTarget( this._normalRenderTarget );
		this.scene.overrideMaterial = this._normalMaterial;
		renderer.render( this.scene, this.camera );
		this.scene.overrideMaterial = overrideMaterial_old;

		uniforms.tDiffuse.value = this._beautyRenderTarget.texture;
		uniforms.tDepth.value = this._beautyRenderTarget.depthTexture;
		uniforms.tNormal.value = this._normalRenderTarget.texture;

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );

		} else {

			renderer.setRenderTarget( writeBuffer );

			if ( this.clear ) renderer.clear();

		}

		this._fsQuad.render( renderer );

	}

	// internals

	_createPixelatedMaterial() {

		return new ShaderMaterial( {
			uniforms: {
				tDiffuse: { value: null },
				tDepth: { value: null },
				tNormal: { value: null },
				resolution: { value: new Vector4() },
				normalEdgeStrength: { value: 0 },
				depthEdgeStrength: { value: 0 }
			},
			vertexShader: /* glsl */`
				varying vec2 vUv;

				void main() {

					vUv = uv;
					gl_Position = projectionMatrix * modelViewMatrix * vec4( position, 1.0 );

				}
			`,
			fragmentShader: /* glsl */`
				uniform sampler2D tDiffuse;
				uniform sampler2D tDepth;
				uniform sampler2D tNormal;
				uniform vec4 resolution;
				uniform float normalEdgeStrength;
				uniform float depthEdgeStrength;
				varying vec2 vUv;

				float getDepth(int x, int y) {

					return texture2D( tDepth, vUv + vec2(x, y) * resolution.zw ).r;

				}

				vec3 getNormal(int x, int y) {

					return texture2D( tNormal, vUv + vec2(x, y) * resolution.zw ).rgb * 2.0 - 1.0;

				}

				float depthEdgeIndicator(float depth, vec3 normal) {

					float diff = 0.0;
					diff += clamp(getDepth(1, 0) - depth, 0.0, 1.0);
					diff += clamp(getDepth(-1, 0) - depth, 0.0, 1.0);
					diff += clamp(getDepth(0, 1) - depth, 0.0, 1.0);
					diff += clamp(getDepth(0, -1) - depth, 0.0, 1.0);
					return floor(smoothstep(0.01, 0.02, diff) * 2.) / 2.;

				}

				float neighborNormalEdgeIndicator(int x, int y, float depth, vec3 normal) {

					float depthDiff = getDepth(x, y) - depth;
					vec3 neighborNormal = getNormal(x, y);

					// Edge pixels should yield to faces who's normals are closer to the bias normal.
					vec3 normalEdgeBias = vec3(1., 1., 1.); // This should probably be a parameter.
					float normalDiff = dot(normal - neighborNormal, normalEdgeBias);
					float normalIndicator = clamp(smoothstep(-.01, .01, normalDiff), 0.0, 1.0);

					// Only the shallower pixel should detect the normal edge.
					float depthIndicator = clamp(sign(depthDiff * .25 + .0025), 0.0, 1.0);

					return (1.0 - dot(normal, neighborNormal)) * depthIndicator * normalIndicator;

				}

				float normalEdgeIndicator(float depth, vec3 normal) {

					float indicator = 0.0;

					indicator += neighborNormalEdgeIndicator(0, -1, depth, normal);
					indicator += neighborNormalEdgeIndicator(0, 1, depth, normal);
					indicator += neighborNormalEdgeIndicator(-1, 0, depth, normal);
					indicator += neighborNormalEdgeIndicator(1, 0, depth, normal);

					return step(0.1, indicator);

				}

				void main() {

					vec4 texel = texture2D( tDiffuse, vUv );

					float depth = 0.0;
					vec3 normal = vec3(0.0);

					if (depthEdgeStrength > 0.0 || normalEdgeStrength > 0.0) {

						depth = getDepth(0, 0);
						normal = getNormal(0, 0);

					}

					float dei = 0.0;
					if (depthEdgeStrength > 0.0)
						dei = depthEdgeIndicator(depth, normal);

					float nei = 0.0;
					if (normalEdgeStrength > 0.0)
						nei = normalEdgeIndicator(depth, normal);

					float Strength = dei > 0.0 ? (1.0 - depthEdgeStrength * dei) : (1.0 + normalEdgeStrength * nei);

					gl_FragColor = texel * Strength;

				}
			`
		} );

	}

}
```
</details>

#### Methods

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this._beautyRenderTarget.dispose();
		this._normalRenderTarget.dispose();

		this.pixelatedMaterial.dispose();
		this._normalMaterial.dispose();

		this._fsQuad.dispose();

	}
```
</details>

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		this._resolution.set( width, height );
		this._renderResolution.set( ( width / this.pixelSize ) | 0, ( height / this.pixelSize ) | 0 );
		const { x, y } = this._renderResolution;
		this._beautyRenderTarget.setSize( x, y );
		this._normalRenderTarget.setSize( x, y );
		this._fsQuad.material.uniforms.resolution.value.set( x, y, 1 / x, 1 / y );

	}
```
</details>

##### `setPixelSize(pixelSize: number): void`

<details><summary>Code</summary>

```ts
setPixelSize( pixelSize ) {

		this.pixelSize = pixelSize;
		this.setSize( this._resolution.x, this._resolution.y );

	}
```
</details>

##### `render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget): void`

<details><summary>Code</summary>

```ts
render( renderer, writeBuffer/*, readBuffer , deltaTime, maskActive */ ) {

		const uniforms = this._fsQuad.material.uniforms;
		uniforms.normalEdgeStrength.value = this.normalEdgeStrength;
		uniforms.depthEdgeStrength.value = this.depthEdgeStrength;

		renderer.setRenderTarget( this._beautyRenderTarget );
		renderer.render( this.scene, this.camera );

		const overrideMaterial_old = this.scene.overrideMaterial;
		renderer.setRenderTarget( this._normalRenderTarget );
		this.scene.overrideMaterial = this._normalMaterial;
		renderer.render( this.scene, this.camera );
		this.scene.overrideMaterial = overrideMaterial_old;

		uniforms.tDiffuse.value = this._beautyRenderTarget.texture;
		uniforms.tDepth.value = this._beautyRenderTarget.depthTexture;
		uniforms.tNormal.value = this._normalRenderTarget.texture;

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );

		} else {

			renderer.setRenderTarget( writeBuffer );

			if ( this.clear ) renderer.clear();

		}

		this._fsQuad.render( renderer );

	}
```
</details>

##### `_createPixelatedMaterial(): any`

<details><summary>Code</summary>

```ts
_createPixelatedMaterial() {

		return new ShaderMaterial( {
			uniforms: {
				tDiffuse: { value: null },
				tDepth: { value: null },
				tNormal: { value: null },
				resolution: { value: new Vector4() },
				normalEdgeStrength: { value: 0 },
				depthEdgeStrength: { value: 0 }
			},
			vertexShader: /* glsl */`
				varying vec2 vUv;

				void main() {

					vUv = uv;
					gl_Position = projectionMatrix * modelViewMatrix * vec4( position, 1.0 );

				}
			`,
			fragmentShader: /* glsl */`
				uniform sampler2D tDiffuse;
				uniform sampler2D tDepth;
				uniform sampler2D tNormal;
				uniform vec4 resolution;
				uniform float normalEdgeStrength;
				uniform float depthEdgeStrength;
				varying vec2 vUv;

				float getDepth(int x, int y) {

					return texture2D( tDepth, vUv + vec2(x, y) * resolution.zw ).r;

				}

				vec3 getNormal(int x, int y) {

					return texture2D( tNormal, vUv + vec2(x, y) * resolution.zw ).rgb * 2.0 - 1.0;

				}

				float depthEdgeIndicator(float depth, vec3 normal) {

					float diff = 0.0;
					diff += clamp(getDepth(1, 0) - depth, 0.0, 1.0);
					diff += clamp(getDepth(-1, 0) - depth, 0.0, 1.0);
					diff += clamp(getDepth(0, 1) - depth, 0.0, 1.0);
					diff += clamp(getDepth(0, -1) - depth, 0.0, 1.0);
					return floor(smoothstep(0.01, 0.02, diff) * 2.) / 2.;

				}

				float neighborNormalEdgeIndicator(int x, int y, float depth, vec3 normal) {

					float depthDiff = getDepth(x, y) - depth;
					vec3 neighborNormal = getNormal(x, y);

					// Edge pixels should yield to faces who's normals are closer to the bias normal.
					vec3 normalEdgeBias = vec3(1., 1., 1.); // This should probably be a parameter.
					float normalDiff = dot(normal - neighborNormal, normalEdgeBias);
					float normalIndicator = clamp(smoothstep(-.01, .01, normalDiff), 0.0, 1.0);

					// Only the shallower pixel should detect the normal edge.
					float depthIndicator = clamp(sign(depthDiff * .25 + .0025), 0.0, 1.0);

					return (1.0 - dot(normal, neighborNormal)) * depthIndicator * normalIndicator;

				}

				float normalEdgeIndicator(float depth, vec3 normal) {

					float indicator = 0.0;

					indicator += neighborNormalEdgeIndicator(0, -1, depth, normal);
					indicator += neighborNormalEdgeIndicator(0, 1, depth, normal);
					indicator += neighborNormalEdgeIndicator(-1, 0, depth, normal);
					indicator += neighborNormalEdgeIndicator(1, 0, depth, normal);

					return step(0.1, indicator);

				}

				void main() {

					vec4 texel = texture2D( tDiffuse, vUv );

					float depth = 0.0;
					vec3 normal = vec3(0.0);

					if (depthEdgeStrength > 0.0 || normalEdgeStrength > 0.0) {

						depth = getDepth(0, 0);
						normal = getNormal(0, 0);

					}

					float dei = 0.0;
					if (depthEdgeStrength > 0.0)
						dei = depthEdgeIndicator(depth, normal);

					float nei = 0.0;
					if (normalEdgeStrength > 0.0)
						nei = normalEdgeIndicator(depth, normal);

					float Strength = dei > 0.0 ? (1.0 - depthEdgeStrength * dei) : (1.0 + normalEdgeStrength * nei);

					gl_FragColor = texel * Strength;

				}
			`
		} );

	}
```
</details>


---