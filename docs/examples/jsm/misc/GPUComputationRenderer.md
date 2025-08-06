[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `GPUComputationRenderer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 24 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/misc/GPUComputationRenderer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ClampToEdgeWrapping` | `three` |
| `DataTexture` | `three` |
| `FloatType` | `three` |
| `NearestFilter` | `three` |
| `RGBAFormat` | `three` |
| `ShaderMaterial` | `three` |
| `WebGLRenderTarget` | `three` |
| `FullScreenQuad` | `../postprocessing/Pass.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `dataType` | `any` | let/var | `FloatType` | ✗ |
| `passThruUniforms` | `{ passThruTexture: { value: any; }; }` | let/var | `{ passThruTexture: { value: null } }` | ✗ |
| `quad` | `FullScreenQuad` | let/var | `new FullScreenQuad( passThruShader )` | ✗ |
| `variable` | `{ name: string; initialValueTexture: ...` | let/var | `{ name: variableName, initialValueTexture: initialValueTexture, material: mat...` | ✗ |
| `variable` | `any` | let/var | `this.variables[ i ]` | ✗ |
| `material` | `any` | let/var | `variable.material` | ✗ |
| `uniforms` | `any` | let/var | `material.uniforms` | ✗ |
| `depVar` | `any` | let/var | `variable.dependencies[ d ]` | ✗ |
| `found` | `boolean` | let/var | `false` | ✗ |
| `currentTextureIndex` | `undefined` | let/var | `this.currentTextureIndex` | ✗ |
| `nextTextureIndex` | `1 \| 0` | let/var | `this.currentTextureIndex === 0 ? 1 : 0` | ✗ |
| `variable` | `any` | let/var | `this.variables[ i ]` | ✗ |
| `uniforms` | `any` | let/var | `variable.material.uniforms` | ✗ |
| `depVar` | `any` | let/var | `variable.dependencies[ d ]` | ✗ |
| `variables` | `any[]` | let/var | `this.variables` | ✗ |
| `variable` | `any` | let/var | `variables[ i ]` | ✗ |
| `renderTargets` | `any` | let/var | `variable.renderTargets` | ✗ |
| `renderTarget` | `any` | let/var | `renderTargets[ j ]` | ✗ |
| `material` | `any` | let/var | `new ShaderMaterial( { name: 'GPUComputationShader', uniforms: uniforms, verte...` | ✗ |
| `renderTarget` | `any` | let/var | `new WebGLRenderTarget( sizeXTexture, sizeYTexture, { wrapS: wrapS, wrapT: wra...` | ✗ |
| `data` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( sizeX * sizeY * 4 )` | ✗ |
| `texture` | `any` | let/var | `new DataTexture( data, sizeX, sizeY, RGBAFormat, FloatType )` | ✗ |
| `currentXrEnabled` | `any` | let/var | `renderer.xr.enabled` | ✗ |
| `currentShadowAutoUpdate` | `any` | let/var | `renderer.shadowMap.autoUpdate` | ✗ |


---

## Functions

### `addResolutionDefine(materialShader: any): void`

**Parameters:**

- **`materialShader`** `any`

**Returns:** `void`

**Calls:**

- `sizeX.toFixed`
- `sizeY.toFixed`

<details><summary>Code</summary>

```typescript
function addResolutionDefine( materialShader ) {

			materialShader.defines.resolution = 'vec2( ' + sizeX.toFixed( 1 ) + ', ' + sizeY.toFixed( 1 ) + ' )';

		}
```
</details>

### `createShaderMaterial(computeFragmentShader: any, uniforms: any): any`

**Parameters:**

- **`computeFragmentShader`** `any`
- **`uniforms`** `any`

**Returns:** `any`

**Calls:**

- `getPassThroughVertexShader`
- `addResolutionDefine`

<details><summary>Code</summary>

```typescript
function createShaderMaterial( computeFragmentShader, uniforms ) {

			uniforms = uniforms || {};

			const material = new ShaderMaterial( {
				name: 'GPUComputationShader',
				uniforms: uniforms,
				vertexShader: getPassThroughVertexShader(),
				fragmentShader: computeFragmentShader
			} );

			addResolutionDefine( material );

			return material;

		}
```
</details>

### `getPassThroughVertexShader(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function getPassThroughVertexShader() {

			return	'void main()	{\n' +
					'\n' +
					'	gl_Position = vec4( position, 1.0 );\n' +
					'\n' +
					'}\n';

		}
```
</details>

### `getPassThroughFragmentShader(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function getPassThroughFragmentShader() {

			return	'uniform sampler2D passThruTexture;\n' +
					'\n' +
					'void main() {\n' +
					'\n' +
					'	vec2 uv = gl_FragCoord.xy / resolution.xy;\n' +
					'\n' +
					'	gl_FragColor = texture2D( passThruTexture, uv );\n' +
					'\n' +
					'}\n';

		}
```
</details>


---

## Classes

### `GPUComputationRenderer`

<details><summary>Class Code</summary>

```ts
class GPUComputationRenderer {

	/**
	 * Constructs a new GPU computation renderer.
	 *
	 * @param {number} sizeX - Computation problem size is always 2d: sizeX * sizeY elements.
 	 * @param {number} sizeY - Computation problem size is always 2d: sizeX * sizeY elements.
 	 * @param {WebGLRenderer} renderer - The renderer.
	 */
	constructor( sizeX, sizeY, renderer ) {

		this.variables = [];

		this.currentTextureIndex = 0;

		let dataType = FloatType;

		const passThruUniforms = {
			passThruTexture: { value: null }
		};

		const passThruShader = createShaderMaterial( getPassThroughFragmentShader(), passThruUniforms );

		const quad = new FullScreenQuad( passThruShader );

		/**
		 * Sets the data type of the internal textures.
		 *
		 * @param {(FloatType|HalfFloatType)} type - The type to set.
		 * @return {GPUComputationRenderer} A reference to this renderer.
		 */
		this.setDataType = function ( type ) {

			dataType = type;
			return this;

		};

		/**
		 * Adds a compute variable to the renderer.
		 *
		 * @param {string} variableName - The variable name.
		 * @param {string} computeFragmentShader - The compute (fragment) shader source.
		 * @param {Texture} initialValueTexture - The initial value texture.
		 * @return {Object} The compute variable.
		 */
		this.addVariable = function ( variableName, computeFragmentShader, initialValueTexture ) {

			const material = this.createShaderMaterial( computeFragmentShader );

			const variable = {
				name: variableName,
				initialValueTexture: initialValueTexture,
				material: material,
				dependencies: null,
				renderTargets: [],
				wrapS: null,
				wrapT: null,
				minFilter: NearestFilter,
				magFilter: NearestFilter
			};

			this.variables.push( variable );

			return variable;

		};

		/**
		 * Sets variable dependencies.
		 *
		 * @param {Object} variable - The compute variable.
		 * @param {Array<Object>} dependencies - Other compute variables that represents the dependencies.
		 */
		this.setVariableDependencies = function ( variable, dependencies ) {

			variable.dependencies = dependencies;

		};

		/**
		 * Initializes the renderer.
		 *
		 * @return {?string} Returns `null` if no errors are detected. Otherwise returns the error message.
		 */
		this.init = function () {

			if ( renderer.capabilities.maxVertexTextures === 0 ) {

				return 'No support for vertex shader textures.';

			}

			for ( let i = 0; i < this.variables.length; i ++ ) {

				const variable = this.variables[ i ];

				// Creates rendertargets and initialize them with input texture
				variable.renderTargets[ 0 ] = this.createRenderTarget( sizeX, sizeY, variable.wrapS, variable.wrapT, variable.minFilter, variable.magFilter );
				variable.renderTargets[ 1 ] = this.createRenderTarget( sizeX, sizeY, variable.wrapS, variable.wrapT, variable.minFilter, variable.magFilter );
				this.renderTexture( variable.initialValueTexture, variable.renderTargets[ 0 ] );
				this.renderTexture( variable.initialValueTexture, variable.renderTargets[ 1 ] );

				// Adds dependencies uniforms to the ShaderMaterial
				const material = variable.material;
				const uniforms = material.uniforms;

				if ( variable.dependencies !== null ) {

					for ( let d = 0; d < variable.dependencies.length; d ++ ) {

						const depVar = variable.dependencies[ d ];

						if ( depVar.name !== variable.name ) {

							// Checks if variable exists
							let found = false;

							for ( let j = 0; j < this.variables.length; j ++ ) {

								if ( depVar.name === this.variables[ j ].name ) {

									found = true;
									break;

								}

							}

							if ( ! found ) {

								return 'Variable dependency not found. Variable=' + variable.name + ', dependency=' + depVar.name;

							}

						}

						uniforms[ depVar.name ] = { value: null };

						material.fragmentShader = '\nuniform sampler2D ' + depVar.name + ';\n' + material.fragmentShader;

					}

				}

			}

			this.currentTextureIndex = 0;

			return null;

		};

		/**
		 * Executes the compute. This method is usually called in the animation loop.
		 */
		this.compute = function () {

			const currentTextureIndex = this.currentTextureIndex;
			const nextTextureIndex = this.currentTextureIndex === 0 ? 1 : 0;

			for ( let i = 0, il = this.variables.length; i < il; i ++ ) {

				const variable = this.variables[ i ];

				// Sets texture dependencies uniforms
				if ( variable.dependencies !== null ) {

					const uniforms = variable.material.uniforms;

					for ( let d = 0, dl = variable.dependencies.length; d < dl; d ++ ) {

						const depVar = variable.dependencies[ d ];

						uniforms[ depVar.name ].value = depVar.renderTargets[ currentTextureIndex ].texture;

					}

				}

				// Performs the computation for this variable
				this.doRenderTarget( variable.material, variable.renderTargets[ nextTextureIndex ] );

			}

			this.currentTextureIndex = nextTextureIndex;

		};

		/**
		 * Returns the current render target for the given compute variable.
		 *
		 * @param {Object} variable - The compute variable.
		 * @return {WebGLRenderTarget} The current render target.
		 */
		this.getCurrentRenderTarget = function ( variable ) {

			return variable.renderTargets[ this.currentTextureIndex ];

		};

		/**
		 * Returns the alternate render target for the given compute variable.
		 *
		 * @param {Object} variable - The compute variable.
		 * @return {WebGLRenderTarget} The alternate render target.
		 */
		this.getAlternateRenderTarget = function ( variable ) {

			return variable.renderTargets[ this.currentTextureIndex === 0 ? 1 : 0 ];

		};

		/**
		 * Frees all internal resources. Call this method if you don't need the
		 * renderer anymore.
		 */
		this.dispose = function () {

			quad.dispose();

			const variables = this.variables;

			for ( let i = 0; i < variables.length; i ++ ) {

				const variable = variables[ i ];

				if ( variable.initialValueTexture ) variable.initialValueTexture.dispose();

				const renderTargets = variable.renderTargets;

				for ( let j = 0; j < renderTargets.length; j ++ ) {

					const renderTarget = renderTargets[ j ];
					renderTarget.dispose();

				}

			}

		};

		function addResolutionDefine( materialShader ) {

			materialShader.defines.resolution = 'vec2( ' + sizeX.toFixed( 1 ) + ', ' + sizeY.toFixed( 1 ) + ' )';

		}

		/**
		 * Adds a resolution defined for the given material shader.
		 *
		 * @param {Object} materialShader - The material shader.
		 */
		this.addResolutionDefine = addResolutionDefine;


		// The following functions can be used to compute things manually

		function createShaderMaterial( computeFragmentShader, uniforms ) {

			uniforms = uniforms || {};

			const material = new ShaderMaterial( {
				name: 'GPUComputationShader',
				uniforms: uniforms,
				vertexShader: getPassThroughVertexShader(),
				fragmentShader: computeFragmentShader
			} );

			addResolutionDefine( material );

			return material;

		}

		this.createShaderMaterial = createShaderMaterial;

		/**
		 * Creates a new render target from the given parameters.
		 *
		 * @param {number} sizeXTexture - The width of the render target.
		 * @param {number} sizeYTexture - The height of the render target.
		 * @param {number} wrapS - The wrapS value.
		 * @param {number} wrapT - The wrapS value.
		 * @param {number} minFilter - The minFilter value.
		 * @param {number} magFilter - The magFilter value.
		 * @return {WebGLRenderTarget} The new render target.
		 */
		this.createRenderTarget = function ( sizeXTexture, sizeYTexture, wrapS, wrapT, minFilter, magFilter ) {

			sizeXTexture = sizeXTexture || sizeX;
			sizeYTexture = sizeYTexture || sizeY;

			wrapS = wrapS || ClampToEdgeWrapping;
			wrapT = wrapT || ClampToEdgeWrapping;

			minFilter = minFilter || NearestFilter;
			magFilter = magFilter || NearestFilter;

			const renderTarget = new WebGLRenderTarget( sizeXTexture, sizeYTexture, {
				wrapS: wrapS,
				wrapT: wrapT,
				minFilter: minFilter,
				magFilter: magFilter,
				format: RGBAFormat,
				type: dataType,
				depthBuffer: false
			} );

			return renderTarget;

		};

		/**
		 * Creates a new data texture.
		 *
		 * @return {DataTexture} The new data texture.
		 */
		this.createTexture = function () {

			const data = new Float32Array( sizeX * sizeY * 4 );
			const texture = new DataTexture( data, sizeX, sizeY, RGBAFormat, FloatType );
			texture.needsUpdate = true;
			return texture;

		};

		/**
		 * Renders the given texture into the given render target.
		 *
		 * @param {Texture} input - The input.
		 * @param {WebGLRenderTarget} output - The output.
		 */
		this.renderTexture = function ( input, output ) {

			passThruUniforms.passThruTexture.value = input;

			this.doRenderTarget( passThruShader, output );

			passThruUniforms.passThruTexture.value = null;

		};


		/**
		 * Renders the given material into the given render target
		 * with a full-screen pass.
		 *
		 * @param {Material} material - The material.
		 * @param {WebGLRenderTarget} output - The output.
		 */
		this.doRenderTarget = function ( material, output ) {

			const currentRenderTarget = renderer.getRenderTarget();

			const currentXrEnabled = renderer.xr.enabled;
			const currentShadowAutoUpdate = renderer.shadowMap.autoUpdate;

			renderer.xr.enabled = false; // Avoid camera modification
			renderer.shadowMap.autoUpdate = false; // Avoid re-computing shadows
			quad.material = material;
			renderer.setRenderTarget( output );
			quad.render( renderer );
			quad.material = passThruShader;

			renderer.xr.enabled = currentXrEnabled;
			renderer.shadowMap.autoUpdate = currentShadowAutoUpdate;

			renderer.setRenderTarget( currentRenderTarget );

		};

		// Shaders

		function getPassThroughVertexShader() {

			return	'void main()	{\n' +
					'\n' +
					'	gl_Position = vec4( position, 1.0 );\n' +
					'\n' +
					'}\n';

		}

		function getPassThroughFragmentShader() {

			return	'uniform sampler2D passThruTexture;\n' +
					'\n' +
					'void main() {\n' +
					'\n' +
					'	vec2 uv = gl_FragCoord.xy / resolution.xy;\n' +
					'\n' +
					'	gl_FragColor = texture2D( passThruTexture, uv );\n' +
					'\n' +
					'}\n';

		}

	}

}
```
</details>


---