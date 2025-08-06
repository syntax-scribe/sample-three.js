[⬅️ Back to Table of Contents](../../index.md)

# 📄 `WebGLCubeRenderTarget.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 11 |
| 📊 Variables & Constants | 8 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/WebGLCubeRenderTarget.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BackSide` | `../constants.js` |
| `LinearFilter` | `../constants.js` |
| `LinearMipmapLinearFilter` | `../constants.js` |
| `NoBlending` | `../constants.js` |
| `Mesh` | `../objects/Mesh.js` |
| `BoxGeometry` | `../geometries/BoxGeometry.js` |
| `ShaderMaterial` | `../materials/ShaderMaterial.js` |
| `cloneUniforms` | `./shaders/UniformsUtils.js` |
| `WebGLRenderTarget` | `./WebGLRenderTarget.js` |
| `CubeCamera` | `../cameras/CubeCamera.js` |
| `CubeTexture` | `../textures/CubeTexture.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `image` | `{ width: number; height: number; dept...` | let/var | `{ width: size, height: size, depth: 1 }` | ✗ |
| `images` | `{ width: number; height: number; dept...` | let/var | `[ image, image, image, image, image, image ]` | ✗ |
| `shader` | `{ uniforms: { tEquirect: { value: any...` | let/var | `{ uniforms: { tEquirect: { value: null }, }, vertexShader: /* glsl */` varyin...` | ✗ |
| `geometry` | `BoxGeometry` | let/var | `new BoxGeometry( 5, 5, 5 )` | ✗ |
| `material` | `ShaderMaterial` | let/var | `new ShaderMaterial( { name: 'CubemapFromEquirect', uniforms: cloneUniforms( s...` | ✗ |
| `mesh` | `Mesh` | let/var | `new Mesh( geometry, material )` | ✗ |
| `currentMinFilter` | `any` | let/var | `texture.minFilter` | ✗ |
| `camera` | `CubeCamera` | let/var | `new CubeCamera( 1, 10, this )` | ✗ |


---

## Functions

### `WebGLCubeRenderTarget.fromEquirectangularTexture(renderer: WebGLRenderer, texture: Texture): WebGLCubeRenderTarget`

**JSDoc:**
```typescript
/**
	 * Converts the given equirectangular texture to a cube map.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {Texture} texture - The equirectangular texture.
	 * @return {WebGLCubeRenderTarget} A reference to this cube render target.
	 */
```

**Parameters:**

- **`renderer`** `WebGLRenderer`
- **`texture`** `Texture`

**Returns:** `WebGLCubeRenderTarget`

**Calls:**

- `cloneUniforms (from ./shaders/UniformsUtils.js)`
- `camera.update`
- `mesh.geometry.dispose`
- `mesh.material.dispose`

**Internal Comments:**
```
// Avoid blurred poles
```

<details><summary>Code</summary>

```typescript
fromEquirectangularTexture( renderer, texture ) {

		this.texture.type = texture.type;
		this.texture.colorSpace = texture.colorSpace;

		this.texture.generateMipmaps = texture.generateMipmaps;
		this.texture.minFilter = texture.minFilter;
		this.texture.magFilter = texture.magFilter;

		const shader = {

			uniforms: {
				tEquirect: { value: null },
			},

			vertexShader: /* glsl */`

				varying vec3 vWorldDirection;

				vec3 transformDirection( in vec3 dir, in mat4 matrix ) {

					return normalize( ( matrix * vec4( dir, 0.0 ) ).xyz );

				}

				void main() {

					vWorldDirection = transformDirection( position, modelMatrix );

					#include <begin_vertex>
					#include <project_vertex>

				}
			`,

			fragmentShader: /* glsl */`

				uniform sampler2D tEquirect;

				varying vec3 vWorldDirection;

				#include <common>

				void main() {

					vec3 direction = normalize( vWorldDirection );

					vec2 sampleUV = equirectUv( direction );

					gl_FragColor = texture2D( tEquirect, sampleUV );

				}
			`
		};

		const geometry = new BoxGeometry( 5, 5, 5 );

		const material = new ShaderMaterial( {

			name: 'CubemapFromEquirect',

			uniforms: cloneUniforms( shader.uniforms ),
			vertexShader: shader.vertexShader,
			fragmentShader: shader.fragmentShader,
			side: BackSide,
			blending: NoBlending

		} );

		material.uniforms.tEquirect.value = texture;

		const mesh = new Mesh( geometry, material );

		const currentMinFilter = texture.minFilter;

		// Avoid blurred poles
		if ( texture.minFilter === LinearMipmapLinearFilter ) texture.minFilter = LinearFilter;

		const camera = new CubeCamera( 1, 10, this );
		camera.update( renderer, mesh );

		texture.minFilter = currentMinFilter;

		mesh.geometry.dispose();
		mesh.material.dispose();

		return this;

	}
```
</details>

### `WebGLCubeRenderTarget.clear(renderer: WebGLRenderer, color: boolean, depth: boolean, stencil: boolean): void`

**JSDoc:**
```typescript
/**
	 * Clears this cube render target.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {boolean} [color=true] - Whether the color buffer should be cleared or not.
	 * @param {boolean} [depth=true] - Whether the depth buffer should be cleared or not.
	 * @param {boolean} [stencil=true] - Whether the stencil buffer should be cleared or not.
	 */
```

**Parameters:**

- **`renderer`** `WebGLRenderer`
- **`color`** `boolean`
- **`depth`** `boolean`
- **`stencil`** `boolean`

**Returns:** `void`

**Calls:**

- `renderer.getRenderTarget`
- `renderer.setRenderTarget`
- `renderer.clear`

<details><summary>Code</summary>

```typescript
clear( renderer, color = true, depth = true, stencil = true ) {

		const currentRenderTarget = renderer.getRenderTarget();

		for ( let i = 0; i < 6; i ++ ) {

			renderer.setRenderTarget( this, i );

			renderer.clear( color, depth, stencil );

		}

		renderer.setRenderTarget( currentRenderTarget );

	}
```
</details>


---

## Classes

### `WebGLCubeRenderTarget`

<details><summary>Class Code</summary>

```ts
class WebGLCubeRenderTarget extends WebGLRenderTarget {

	/**
	 * Constructs a new cube render target.
	 *
	 * @param {number} [size=1] - The size of the render target.
	 * @param {RenderTarget~Options} [options] - The configuration object.
	 */
	constructor( size = 1, options = {} ) {

		super( size, size, options );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isWebGLCubeRenderTarget = true;

		const image = { width: size, height: size, depth: 1 };
		const images = [ image, image, image, image, image, image ];

		/**
		 * Overwritten with a different texture type.
		 *
		 * @type {DataArrayTexture}
		 */
		this.texture = new CubeTexture( images );
		this._setTextureOptions( options );

		// By convention -- likely based on the RenderMan spec from the 1990's -- cube maps are specified by WebGL (and three.js)
		// in a coordinate system in which positive-x is to the right when looking up the positive-z axis -- in other words,
		// in a left-handed coordinate system. By continuing this convention, preexisting cube maps continued to render correctly.

		// three.js uses a right-handed coordinate system. So environment maps used in three.js appear to have px and nx swapped
		// and the flag isRenderTargetTexture controls this conversion. The flip is not required when using WebGLCubeRenderTarget.texture
		// as a cube texture (this is detected when isRenderTargetTexture is set to true for cube textures).

		this.texture.isRenderTargetTexture = true;

	}

	/**
	 * Converts the given equirectangular texture to a cube map.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {Texture} texture - The equirectangular texture.
	 * @return {WebGLCubeRenderTarget} A reference to this cube render target.
	 */
	fromEquirectangularTexture( renderer, texture ) {

		this.texture.type = texture.type;
		this.texture.colorSpace = texture.colorSpace;

		this.texture.generateMipmaps = texture.generateMipmaps;
		this.texture.minFilter = texture.minFilter;
		this.texture.magFilter = texture.magFilter;

		const shader = {

			uniforms: {
				tEquirect: { value: null },
			},

			vertexShader: /* glsl */`

				varying vec3 vWorldDirection;

				vec3 transformDirection( in vec3 dir, in mat4 matrix ) {

					return normalize( ( matrix * vec4( dir, 0.0 ) ).xyz );

				}

				void main() {

					vWorldDirection = transformDirection( position, modelMatrix );

					#include <begin_vertex>
					#include <project_vertex>

				}
			`,

			fragmentShader: /* glsl */`

				uniform sampler2D tEquirect;

				varying vec3 vWorldDirection;

				#include <common>

				void main() {

					vec3 direction = normalize( vWorldDirection );

					vec2 sampleUV = equirectUv( direction );

					gl_FragColor = texture2D( tEquirect, sampleUV );

				}
			`
		};

		const geometry = new BoxGeometry( 5, 5, 5 );

		const material = new ShaderMaterial( {

			name: 'CubemapFromEquirect',

			uniforms: cloneUniforms( shader.uniforms ),
			vertexShader: shader.vertexShader,
			fragmentShader: shader.fragmentShader,
			side: BackSide,
			blending: NoBlending

		} );

		material.uniforms.tEquirect.value = texture;

		const mesh = new Mesh( geometry, material );

		const currentMinFilter = texture.minFilter;

		// Avoid blurred poles
		if ( texture.minFilter === LinearMipmapLinearFilter ) texture.minFilter = LinearFilter;

		const camera = new CubeCamera( 1, 10, this );
		camera.update( renderer, mesh );

		texture.minFilter = currentMinFilter;

		mesh.geometry.dispose();
		mesh.material.dispose();

		return this;

	}

	/**
	 * Clears this cube render target.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {boolean} [color=true] - Whether the color buffer should be cleared or not.
	 * @param {boolean} [depth=true] - Whether the depth buffer should be cleared or not.
	 * @param {boolean} [stencil=true] - Whether the stencil buffer should be cleared or not.
	 */
	clear( renderer, color = true, depth = true, stencil = true ) {

		const currentRenderTarget = renderer.getRenderTarget();

		for ( let i = 0; i < 6; i ++ ) {

			renderer.setRenderTarget( this, i );

			renderer.clear( color, depth, stencil );

		}

		renderer.setRenderTarget( currentRenderTarget );

	}

}
```
</details>

#### Methods

##### `fromEquirectangularTexture(renderer: WebGLRenderer, texture: Texture): WebGLCubeRenderTarget`

<details><summary>Code</summary>

```ts
fromEquirectangularTexture( renderer, texture ) {

		this.texture.type = texture.type;
		this.texture.colorSpace = texture.colorSpace;

		this.texture.generateMipmaps = texture.generateMipmaps;
		this.texture.minFilter = texture.minFilter;
		this.texture.magFilter = texture.magFilter;

		const shader = {

			uniforms: {
				tEquirect: { value: null },
			},

			vertexShader: /* glsl */`

				varying vec3 vWorldDirection;

				vec3 transformDirection( in vec3 dir, in mat4 matrix ) {

					return normalize( ( matrix * vec4( dir, 0.0 ) ).xyz );

				}

				void main() {

					vWorldDirection = transformDirection( position, modelMatrix );

					#include <begin_vertex>
					#include <project_vertex>

				}
			`,

			fragmentShader: /* glsl */`

				uniform sampler2D tEquirect;

				varying vec3 vWorldDirection;

				#include <common>

				void main() {

					vec3 direction = normalize( vWorldDirection );

					vec2 sampleUV = equirectUv( direction );

					gl_FragColor = texture2D( tEquirect, sampleUV );

				}
			`
		};

		const geometry = new BoxGeometry( 5, 5, 5 );

		const material = new ShaderMaterial( {

			name: 'CubemapFromEquirect',

			uniforms: cloneUniforms( shader.uniforms ),
			vertexShader: shader.vertexShader,
			fragmentShader: shader.fragmentShader,
			side: BackSide,
			blending: NoBlending

		} );

		material.uniforms.tEquirect.value = texture;

		const mesh = new Mesh( geometry, material );

		const currentMinFilter = texture.minFilter;

		// Avoid blurred poles
		if ( texture.minFilter === LinearMipmapLinearFilter ) texture.minFilter = LinearFilter;

		const camera = new CubeCamera( 1, 10, this );
		camera.update( renderer, mesh );

		texture.minFilter = currentMinFilter;

		mesh.geometry.dispose();
		mesh.material.dispose();

		return this;

	}
```
</details>

##### `clear(renderer: WebGLRenderer, color: boolean, depth: boolean, stencil: boolean): void`

<details><summary>Code</summary>

```ts
clear( renderer, color = true, depth = true, stencil = true ) {

		const currentRenderTarget = renderer.getRenderTarget();

		for ( let i = 0; i < 6; i ++ ) {

			renderer.setRenderTarget( this, i );

			renderer.clear( color, depth, stencil );

		}

		renderer.setRenderTarget( currentRenderTarget );

	}
```
</details>


---