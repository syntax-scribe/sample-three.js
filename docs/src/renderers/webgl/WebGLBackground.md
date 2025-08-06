[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLBackground.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 18 |
| 📦 Imports | 15 |
| 📊 Variables & Constants | 13 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLBackground.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BackSide` | `../../constants.js` |
| `FrontSide` | `../../constants.js` |
| `CubeUVReflectionMapping` | `../../constants.js` |
| `SRGBTransfer` | `../../constants.js` |
| `BoxGeometry` | `../../geometries/BoxGeometry.js` |
| `PlaneGeometry` | `../../geometries/PlaneGeometry.js` |
| `ShaderMaterial` | `../../materials/ShaderMaterial.js` |
| `Color` | `../../math/Color.js` |
| `ColorManagement` | `../../math/ColorManagement.js` |
| `Euler` | `../../math/Euler.js` |
| `Matrix4` | `../../math/Matrix4.js` |
| `Mesh` | `../../objects/Mesh.js` |
| `ShaderLib` | `../shaders/ShaderLib.js` |
| `cloneUniforms` | `../shaders/UniformsUtils.js` |
| `getUnlitUniformColorSpace` | `../shaders/UniformsUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_rgb` | `{ r: number; b: number; g: number; }` | let/var | `{ r: 0, b: 0, g: 0 }` | ✗ |
| `_e1` | `Euler` | let/var | `new Euler()` | ✗ |
| `_m1` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `clearColor` | `Color` | let/var | `new Color( 0x000000 )` | ✗ |
| `clearAlpha` | `number` | let/var | `alpha === true ? 0 : 1` | ✗ |
| `planeMesh` | `any` | let/var | `*not shown*` | ✗ |
| `boxMesh` | `any` | let/var | `*not shown*` | ✗ |
| `currentBackground` | `any` | let/var | `null` | ✗ |
| `currentBackgroundVersion` | `number` | let/var | `0` | ✗ |
| `currentTonemapping` | `any` | let/var | `null` | ✗ |
| `background` | `any` | let/var | `scene.isScene === true ? scene.background : null` | ✗ |
| `usePMREM` | `boolean` | let/var | `scene.backgroundBlurriness > 0` | ✗ |
| `forceClear` | `boolean` | let/var | `false` | ✗ |


---

## Functions

### `WebGLBackground(renderer: any, cubemaps: any, cubeuvmaps: any, state: any, objects: any, alpha: any, premultipliedAlpha: any): { getClearColor: () => Color; setClearColor: (color: any, alpha?: number) => void; getClearAlpha: () => number; setClearAlpha: (alpha: any) => void; render: (scene: any) => void; addToRenderList: (renderList: any, scene: any) => void; dispose: () => void; }`

**Parameters:**

- **`renderer`** `any`
- **`cubemaps`** `any`
- **`cubeuvmaps`** `any`
- **`state`** `any`
- **`objects`** `any`
- **`alpha`** `any`
- **`premultipliedAlpha`** `any`

**Returns:** `{ getClearColor: () => Color; setClearColor: (color: any, alpha?: number) => void; getClearAlpha: () => number; setClearAlpha: (alpha: any) => void; render: (scene: any) => void; addToRenderList: (renderList: any, scene: any) => void; dispose: () => void; }`

**Calls:**

- `( usePMREM ? cubeuvmaps : cubemaps ).get`
- `getBackground`
- `setClear`
- `renderer.xr.getEnvironmentBlendMode`
- `state.buffers.color.setClear`
- `state.buffers.depth.setTest`
- `state.buffers.depth.setMask`
- `state.buffers.color.setMask`
- `renderer.clear`
- `cloneUniforms (from ../shaders/UniformsUtils.js)`
- `boxMesh.geometry.deleteAttribute`
- `this.matrixWorld.copyPosition`
- `Object.defineProperty`
- `objects.update`
- `_e1.copy`
- `boxMesh.material.uniforms.backgroundRotation.value.setFromMatrix4`
- `_m1.makeRotationFromEuler`
- `ColorManagement.getTransfer`
- `boxMesh.layers.enableAll`
- `renderList.unshift`
- `planeMesh.geometry.deleteAttribute`
- `background.updateMatrix`
- `planeMesh.material.uniforms.uvTransform.value.copy`
- `planeMesh.layers.enableAll`
- `color.getRGB`
- `getUnlitUniformColorSpace (from ../shaders/UniformsUtils.js)`
- `boxMesh.geometry.dispose`
- `boxMesh.material.dispose`
- `planeMesh.geometry.dispose`
- `planeMesh.material.dispose`
- `clearColor.set`

**Internal Comments:**
```
// buffers might not be writable which is required to ensure a correct clear (x6)
// add "envMap" material property so the renderer can evaluate it like for built-in materials (x4)
// accommodate left-handed frame (x4)
// environment maps which are not cube render targets or PMREMs follow a different convention (x4)
// push to the pre-sorted opaque render list (x8)
// add "map" material property so the renderer can evaluate it like for built-in materials (x4)
```

<details><summary>Code</summary>

```typescript
function WebGLBackground( renderer, cubemaps, cubeuvmaps, state, objects, alpha, premultipliedAlpha ) {

	const clearColor = new Color( 0x000000 );
	let clearAlpha = alpha === true ? 0 : 1;

	let planeMesh;
	let boxMesh;

	let currentBackground = null;
	let currentBackgroundVersion = 0;
	let currentTonemapping = null;

	function getBackground( scene ) {

		let background = scene.isScene === true ? scene.background : null;

		if ( background && background.isTexture ) {

			const usePMREM = scene.backgroundBlurriness > 0; // use PMREM if the user wants to blur the background
			background = ( usePMREM ? cubeuvmaps : cubemaps ).get( background );

		}

		return background;

	}

	function render( scene ) {

		let forceClear = false;
		const background = getBackground( scene );

		if ( background === null ) {

			setClear( clearColor, clearAlpha );

		} else if ( background && background.isColor ) {

			setClear( background, 1 );
			forceClear = true;

		}

		const environmentBlendMode = renderer.xr.getEnvironmentBlendMode();

		if ( environmentBlendMode === 'additive' ) {

			state.buffers.color.setClear( 0, 0, 0, 1, premultipliedAlpha );

		} else if ( environmentBlendMode === 'alpha-blend' ) {

			state.buffers.color.setClear( 0, 0, 0, 0, premultipliedAlpha );

		}

		if ( renderer.autoClear || forceClear ) {

			// buffers might not be writable which is required to ensure a correct clear

			state.buffers.depth.setTest( true );
			state.buffers.depth.setMask( true );
			state.buffers.color.setMask( true );

			renderer.clear( renderer.autoClearColor, renderer.autoClearDepth, renderer.autoClearStencil );

		}

	}

	function addToRenderList( renderList, scene ) {

		const background = getBackground( scene );

		if ( background && ( background.isCubeTexture || background.mapping === CubeUVReflectionMapping ) ) {

			if ( boxMesh === undefined ) {

				boxMesh = new Mesh(
					new BoxGeometry( 1, 1, 1 ),
					new ShaderMaterial( {
						name: 'BackgroundCubeMaterial',
						uniforms: cloneUniforms( ShaderLib.backgroundCube.uniforms ),
						vertexShader: ShaderLib.backgroundCube.vertexShader,
						fragmentShader: ShaderLib.backgroundCube.fragmentShader,
						side: BackSide,
						depthTest: false,
						depthWrite: false,
						fog: false,
						allowOverride: false
					} )
				);

				boxMesh.geometry.deleteAttribute( 'normal' );
				boxMesh.geometry.deleteAttribute( 'uv' );

				boxMesh.onBeforeRender = function ( renderer, scene, camera ) {

					this.matrixWorld.copyPosition( camera.matrixWorld );

				};

				// add "envMap" material property so the renderer can evaluate it like for built-in materials
				Object.defineProperty( boxMesh.material, 'envMap', {

					get: function () {

						return this.uniforms.envMap.value;

					}

				} );

				objects.update( boxMesh );

			}

			_e1.copy( scene.backgroundRotation );

			// accommodate left-handed frame
			_e1.x *= - 1; _e1.y *= - 1; _e1.z *= - 1;

			if ( background.isCubeTexture && background.isRenderTargetTexture === false ) {

				// environment maps which are not cube render targets or PMREMs follow a different convention
				_e1.y *= - 1;
				_e1.z *= - 1;

			}

			boxMesh.material.uniforms.envMap.value = background;
			boxMesh.material.uniforms.flipEnvMap.value = ( background.isCubeTexture && background.isRenderTargetTexture === false ) ? - 1 : 1;
			boxMesh.material.uniforms.backgroundBlurriness.value = scene.backgroundBlurriness;
			boxMesh.material.uniforms.backgroundIntensity.value = scene.backgroundIntensity;
			boxMesh.material.uniforms.backgroundRotation.value.setFromMatrix4( _m1.makeRotationFromEuler( _e1 ) );
			boxMesh.material.toneMapped = ColorManagement.getTransfer( background.colorSpace ) !== SRGBTransfer;

			if ( currentBackground !== background ||
				currentBackgroundVersion !== background.version ||
				currentTonemapping !== renderer.toneMapping ) {

				boxMesh.material.needsUpdate = true;

				currentBackground = background;
				currentBackgroundVersion = background.version;
				currentTonemapping = renderer.toneMapping;

			}

			boxMesh.layers.enableAll();

			// push to the pre-sorted opaque render list
			renderList.unshift( boxMesh, boxMesh.geometry, boxMesh.material, 0, 0, null );

		} else if ( background && background.isTexture ) {

			if ( planeMesh === undefined ) {

				planeMesh = new Mesh(
					new PlaneGeometry( 2, 2 ),
					new ShaderMaterial( {
						name: 'BackgroundMaterial',
						uniforms: cloneUniforms( ShaderLib.background.uniforms ),
						vertexShader: ShaderLib.background.vertexShader,
						fragmentShader: ShaderLib.background.fragmentShader,
						side: FrontSide,
						depthTest: false,
						depthWrite: false,
						fog: false,
						allowOverride: false
					} )
				);

				planeMesh.geometry.deleteAttribute( 'normal' );

				// add "map" material property so the renderer can evaluate it like for built-in materials
				Object.defineProperty( planeMesh.material, 'map', {

					get: function () {

						return this.uniforms.t2D.value;

					}

				} );

				objects.update( planeMesh );

			}

			planeMesh.material.uniforms.t2D.value = background;
			planeMesh.material.uniforms.backgroundIntensity.value = scene.backgroundIntensity;
			planeMesh.material.toneMapped = ColorManagement.getTransfer( background.colorSpace ) !== SRGBTransfer;

			if ( background.matrixAutoUpdate === true ) {

				background.updateMatrix();

			}

			planeMesh.material.uniforms.uvTransform.value.copy( background.matrix );

			if ( currentBackground !== background ||
				currentBackgroundVersion !== background.version ||
				currentTonemapping !== renderer.toneMapping ) {

				planeMesh.material.needsUpdate = true;

				currentBackground = background;
				currentBackgroundVersion = background.version;
				currentTonemapping = renderer.toneMapping;

			}

			planeMesh.layers.enableAll();

			// push to the pre-sorted opaque render list
			renderList.unshift( planeMesh, planeMesh.geometry, planeMesh.material, 0, 0, null );

		}

	}

	function setClear( color, alpha ) {

		color.getRGB( _rgb, getUnlitUniformColorSpace( renderer ) );

		state.buffers.color.setClear( _rgb.r, _rgb.g, _rgb.b, alpha, premultipliedAlpha );

	}

	function dispose() {

		if ( boxMesh !== undefined ) {

			boxMesh.geometry.dispose();
			boxMesh.material.dispose();

			boxMesh = undefined;

		}

		if ( planeMesh !== undefined ) {

			planeMesh.geometry.dispose();
			planeMesh.material.dispose();

			planeMesh = undefined;

		}

	}

	return {

		getClearColor: function () {

			return clearColor;

		},
		setClearColor: function ( color, alpha = 1 ) {

			clearColor.set( color );
			clearAlpha = alpha;
			setClear( clearColor, clearAlpha );

		},
		getClearAlpha: function () {

			return clearAlpha;

		},
		setClearAlpha: function ( alpha ) {

			clearAlpha = alpha;
			setClear( clearColor, clearAlpha );

		},
		render: render,
		addToRenderList: addToRenderList,
		dispose: dispose

	};

}
```
</details>

### `getBackground(scene: any): any`

**Parameters:**

- **`scene`** `any`

**Returns:** `any`

**Calls:**

- `( usePMREM ? cubeuvmaps : cubemaps ).get`

<details><summary>Code</summary>

```typescript
function getBackground( scene ) {

		let background = scene.isScene === true ? scene.background : null;

		if ( background && background.isTexture ) {

			const usePMREM = scene.backgroundBlurriness > 0; // use PMREM if the user wants to blur the background
			background = ( usePMREM ? cubeuvmaps : cubemaps ).get( background );

		}

		return background;

	}
```
</details>

### `render(scene: any): void`

**Parameters:**

- **`scene`** `any`

**Returns:** `void`

**Calls:**

- `getBackground`
- `setClear`
- `renderer.xr.getEnvironmentBlendMode`
- `state.buffers.color.setClear`
- `state.buffers.depth.setTest`
- `state.buffers.depth.setMask`
- `state.buffers.color.setMask`
- `renderer.clear`

**Internal Comments:**
```
// buffers might not be writable which is required to ensure a correct clear (x6)
```

<details><summary>Code</summary>

```typescript
function render( scene ) {

		let forceClear = false;
		const background = getBackground( scene );

		if ( background === null ) {

			setClear( clearColor, clearAlpha );

		} else if ( background && background.isColor ) {

			setClear( background, 1 );
			forceClear = true;

		}

		const environmentBlendMode = renderer.xr.getEnvironmentBlendMode();

		if ( environmentBlendMode === 'additive' ) {

			state.buffers.color.setClear( 0, 0, 0, 1, premultipliedAlpha );

		} else if ( environmentBlendMode === 'alpha-blend' ) {

			state.buffers.color.setClear( 0, 0, 0, 0, premultipliedAlpha );

		}

		if ( renderer.autoClear || forceClear ) {

			// buffers might not be writable which is required to ensure a correct clear

			state.buffers.depth.setTest( true );
			state.buffers.depth.setMask( true );
			state.buffers.color.setMask( true );

			renderer.clear( renderer.autoClearColor, renderer.autoClearDepth, renderer.autoClearStencil );

		}

	}
```
</details>

### `addToRenderList(renderList: any, scene: any): void`

**Parameters:**

- **`renderList`** `any`
- **`scene`** `any`

**Returns:** `void`

**Calls:**

- `getBackground`
- `cloneUniforms (from ../shaders/UniformsUtils.js)`
- `boxMesh.geometry.deleteAttribute`
- `this.matrixWorld.copyPosition`
- `Object.defineProperty`
- `objects.update`
- `_e1.copy`
- `boxMesh.material.uniforms.backgroundRotation.value.setFromMatrix4`
- `_m1.makeRotationFromEuler`
- `ColorManagement.getTransfer`
- `boxMesh.layers.enableAll`
- `renderList.unshift`
- `planeMesh.geometry.deleteAttribute`
- `background.updateMatrix`
- `planeMesh.material.uniforms.uvTransform.value.copy`
- `planeMesh.layers.enableAll`

**Internal Comments:**
```
// add "envMap" material property so the renderer can evaluate it like for built-in materials (x4)
// accommodate left-handed frame (x4)
// environment maps which are not cube render targets or PMREMs follow a different convention (x4)
// push to the pre-sorted opaque render list (x8)
// add "map" material property so the renderer can evaluate it like for built-in materials (x4)
```

<details><summary>Code</summary>

```typescript
function addToRenderList( renderList, scene ) {

		const background = getBackground( scene );

		if ( background && ( background.isCubeTexture || background.mapping === CubeUVReflectionMapping ) ) {

			if ( boxMesh === undefined ) {

				boxMesh = new Mesh(
					new BoxGeometry( 1, 1, 1 ),
					new ShaderMaterial( {
						name: 'BackgroundCubeMaterial',
						uniforms: cloneUniforms( ShaderLib.backgroundCube.uniforms ),
						vertexShader: ShaderLib.backgroundCube.vertexShader,
						fragmentShader: ShaderLib.backgroundCube.fragmentShader,
						side: BackSide,
						depthTest: false,
						depthWrite: false,
						fog: false,
						allowOverride: false
					} )
				);

				boxMesh.geometry.deleteAttribute( 'normal' );
				boxMesh.geometry.deleteAttribute( 'uv' );

				boxMesh.onBeforeRender = function ( renderer, scene, camera ) {

					this.matrixWorld.copyPosition( camera.matrixWorld );

				};

				// add "envMap" material property so the renderer can evaluate it like for built-in materials
				Object.defineProperty( boxMesh.material, 'envMap', {

					get: function () {

						return this.uniforms.envMap.value;

					}

				} );

				objects.update( boxMesh );

			}

			_e1.copy( scene.backgroundRotation );

			// accommodate left-handed frame
			_e1.x *= - 1; _e1.y *= - 1; _e1.z *= - 1;

			if ( background.isCubeTexture && background.isRenderTargetTexture === false ) {

				// environment maps which are not cube render targets or PMREMs follow a different convention
				_e1.y *= - 1;
				_e1.z *= - 1;

			}

			boxMesh.material.uniforms.envMap.value = background;
			boxMesh.material.uniforms.flipEnvMap.value = ( background.isCubeTexture && background.isRenderTargetTexture === false ) ? - 1 : 1;
			boxMesh.material.uniforms.backgroundBlurriness.value = scene.backgroundBlurriness;
			boxMesh.material.uniforms.backgroundIntensity.value = scene.backgroundIntensity;
			boxMesh.material.uniforms.backgroundRotation.value.setFromMatrix4( _m1.makeRotationFromEuler( _e1 ) );
			boxMesh.material.toneMapped = ColorManagement.getTransfer( background.colorSpace ) !== SRGBTransfer;

			if ( currentBackground !== background ||
				currentBackgroundVersion !== background.version ||
				currentTonemapping !== renderer.toneMapping ) {

				boxMesh.material.needsUpdate = true;

				currentBackground = background;
				currentBackgroundVersion = background.version;
				currentTonemapping = renderer.toneMapping;

			}

			boxMesh.layers.enableAll();

			// push to the pre-sorted opaque render list
			renderList.unshift( boxMesh, boxMesh.geometry, boxMesh.material, 0, 0, null );

		} else if ( background && background.isTexture ) {

			if ( planeMesh === undefined ) {

				planeMesh = new Mesh(
					new PlaneGeometry( 2, 2 ),
					new ShaderMaterial( {
						name: 'BackgroundMaterial',
						uniforms: cloneUniforms( ShaderLib.background.uniforms ),
						vertexShader: ShaderLib.background.vertexShader,
						fragmentShader: ShaderLib.background.fragmentShader,
						side: FrontSide,
						depthTest: false,
						depthWrite: false,
						fog: false,
						allowOverride: false
					} )
				);

				planeMesh.geometry.deleteAttribute( 'normal' );

				// add "map" material property so the renderer can evaluate it like for built-in materials
				Object.defineProperty( planeMesh.material, 'map', {

					get: function () {

						return this.uniforms.t2D.value;

					}

				} );

				objects.update( planeMesh );

			}

			planeMesh.material.uniforms.t2D.value = background;
			planeMesh.material.uniforms.backgroundIntensity.value = scene.backgroundIntensity;
			planeMesh.material.toneMapped = ColorManagement.getTransfer( background.colorSpace ) !== SRGBTransfer;

			if ( background.matrixAutoUpdate === true ) {

				background.updateMatrix();

			}

			planeMesh.material.uniforms.uvTransform.value.copy( background.matrix );

			if ( currentBackground !== background ||
				currentBackgroundVersion !== background.version ||
				currentTonemapping !== renderer.toneMapping ) {

				planeMesh.material.needsUpdate = true;

				currentBackground = background;
				currentBackgroundVersion = background.version;
				currentTonemapping = renderer.toneMapping;

			}

			planeMesh.layers.enableAll();

			// push to the pre-sorted opaque render list
			renderList.unshift( planeMesh, planeMesh.geometry, planeMesh.material, 0, 0, null );

		}

	}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

						return this.uniforms.envMap.value;

					}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

						return this.uniforms.envMap.value;

					}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

						return this.uniforms.t2D.value;

					}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

						return this.uniforms.t2D.value;

					}
```
</details>

### `setClear(color: any, alpha: any): void`

**Parameters:**

- **`color`** `any`
- **`alpha`** `any`

**Returns:** `void`

**Calls:**

- `color.getRGB`
- `getUnlitUniformColorSpace (from ../shaders/UniformsUtils.js)`
- `state.buffers.color.setClear`

<details><summary>Code</summary>

```typescript
function setClear( color, alpha ) {

		color.getRGB( _rgb, getUnlitUniformColorSpace( renderer ) );

		state.buffers.color.setClear( _rgb.r, _rgb.g, _rgb.b, alpha, premultipliedAlpha );

	}
```
</details>

### `dispose(): void`

**Returns:** `void`

**Calls:**

- `boxMesh.geometry.dispose`
- `boxMesh.material.dispose`
- `planeMesh.geometry.dispose`
- `planeMesh.material.dispose`

<details><summary>Code</summary>

```typescript
function dispose() {

		if ( boxMesh !== undefined ) {

			boxMesh.geometry.dispose();
			boxMesh.material.dispose();

			boxMesh = undefined;

		}

		if ( planeMesh !== undefined ) {

			planeMesh.geometry.dispose();
			planeMesh.material.dispose();

			planeMesh = undefined;

		}

	}
```
</details>

### `getClearColor(): Color`

**Returns:** `Color`

<details><summary>Code</summary>

```typescript
function () {

			return clearColor;

		}
```
</details>

### `setClearColor(color: any, alpha: number): void`

**Parameters:**

- **`color`** `any`
- **`alpha`** `number`

**Returns:** `void`

**Calls:**

- `clearColor.set`
- `setClear`

<details><summary>Code</summary>

```typescript
function ( color, alpha = 1 ) {

			clearColor.set( color );
			clearAlpha = alpha;
			setClear( clearColor, clearAlpha );

		}
```
</details>

### `getClearAlpha(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () {

			return clearAlpha;

		}
```
</details>

### `setClearAlpha(alpha: any): void`

**Parameters:**

- **`alpha`** `any`

**Returns:** `void`

**Calls:**

- `setClear`

<details><summary>Code</summary>

```typescript
function ( alpha ) {

			clearAlpha = alpha;
			setClear( clearColor, clearAlpha );

		}
```
</details>

### `getClearColor(): Color`

**Returns:** `Color`

<details><summary>Code</summary>

```typescript
function () {

			return clearColor;

		}
```
</details>

### `setClearColor(color: any, alpha: number): void`

**Parameters:**

- **`color`** `any`
- **`alpha`** `number`

**Returns:** `void`

**Calls:**

- `clearColor.set`
- `setClear`

<details><summary>Code</summary>

```typescript
function ( color, alpha = 1 ) {

			clearColor.set( color );
			clearAlpha = alpha;
			setClear( clearColor, clearAlpha );

		}
```
</details>

### `getClearAlpha(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function () {

			return clearAlpha;

		}
```
</details>

### `setClearAlpha(alpha: any): void`

**Parameters:**

- **`alpha`** `any`

**Returns:** `void`

**Calls:**

- `setClear`

<details><summary>Code</summary>

```typescript
function ( alpha ) {

			clearAlpha = alpha;
			setClear( clearColor, clearAlpha );

		}
```
</details>


---