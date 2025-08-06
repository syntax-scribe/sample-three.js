[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `PMREMGenerator.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 29 |
| 🧱 Classes | 1 |
| 📦 Imports | 31 |
| 📊 Variables & Constants | 87 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/extras/PMREMGenerator.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeMaterial` | `../../../materials/nodes/NodeMaterial.js` |
| `getDirection` | `../../../nodes/pmrem/PMREMUtils.js` |
| `blur` | `../../../nodes/pmrem/PMREMUtils.js` |
| `equirectUV` | `../../../nodes/utils/EquirectUV.js` |
| `uniform` | `../../../nodes/core/UniformNode.js` |
| `uniformArray` | `../../../nodes/accessors/UniformArrayNode.js` |
| `texture` | `../../../nodes/accessors/TextureNode.js` |
| `cubeTexture` | `../../../nodes/accessors/CubeTextureNode.js` |
| `float` | `../../../nodes/tsl/TSLBase.js` |
| `vec3` | `../../../nodes/tsl/TSLBase.js` |
| `uv` | `../../../nodes/accessors/UV.js` |
| `attribute` | `../../../nodes/core/AttributeNode.js` |
| `OrthographicCamera` | `../../../cameras/OrthographicCamera.js` |
| `Color` | `../../../math/Color.js` |
| `Vector3` | `../../../math/Vector3.js` |
| `BufferGeometry` | `../../../core/BufferGeometry.js` |
| `BufferAttribute` | `../../../core/BufferAttribute.js` |
| `RenderTarget` | `../../../core/RenderTarget.js` |
| `Mesh` | `../../../objects/Mesh.js` |
| `PerspectiveCamera` | `../../../cameras/PerspectiveCamera.js` |
| `MeshBasicMaterial` | `../../../materials/MeshBasicMaterial.js` |
| `BoxGeometry` | `../../../geometries/BoxGeometry.js` |
| `CubeReflectionMapping` | `../../../constants.js` |
| `CubeRefractionMapping` | `../../../constants.js` |
| `CubeUVReflectionMapping` | `../../../constants.js` |
| `LinearFilter` | `../../../constants.js` |
| `NoBlending` | `../../../constants.js` |
| `RGBAFormat` | `../../../constants.js` |
| `HalfFloatType` | `../../../constants.js` |
| `BackSide` | `../../../constants.js` |
| `LinearSRGBColorSpace` | `../../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `LOD_MIN` | `4` | let/var | `4` | ✗ |
| `EXTRA_LOD_SIGMA` | `number[]` | let/var | `[ 0.125, 0.215, 0.35, 0.446, 0.526, 0.582 ]` | ✗ |
| `MAX_SAMPLES` | `20` | let/var | `20` | ✗ |
| `_flatCamera` | `OrthographicCamera` | let/var | `new OrthographicCamera( - 1, 1, 1, - 1, 0, 1 )` | ✗ |
| `_cubeCamera` | `PerspectiveCamera` | let/var | `new PerspectiveCamera( 90, 1 )` | ✗ |
| `_clearColor` | `Color` | let/var | `new Color()` | ✗ |
| `_oldTarget` | `any` | let/var | `null` | ✗ |
| `_oldActiveCubeFace` | `number` | let/var | `0` | ✗ |
| `_oldActiveMipmapLevel` | `number` | let/var | `0` | ✗ |
| `PHI` | `number` | let/var | `( 1 + Math.sqrt( 5 ) ) / 2` | ✗ |
| `INV_PHI` | `number` | let/var | `1 / PHI` | ✗ |
| `_axisDirections` | `Vector3[]` | let/var | `[ /*@__PURE__*/ new Vector3( - PHI, INV_PHI, 0 ), /*@__PURE__*/ new Vector3( ...` | ✗ |
| `_origin` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_uniformsMap` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `_faceLib` | `number[]` | let/var | `[ 3, 1, 5, 0, 4, 2 ]` | ✗ |
| `cubeUVRenderTarget` | `Vector3 \| RenderTarget` | let/var | `renderTarget \|\| this._allocateTarget()` | ✗ |
| `cubeUVRenderTarget` | `Vector3 \| RenderTarget` | let/var | `renderTarget \|\| this._allocateTarget()` | ✗ |
| `cubeUVRenderTarget` | `RenderTarget` | let/var | `renderTarget \|\| this._allocateTarget()` | ✗ |
| `cubeUVRenderTarget` | `RenderTarget` | let/var | `renderTarget \|\| this._allocateTarget()` | ✗ |
| `cubeUVRenderTarget` | `any` | let/var | `renderTarget \|\| this._allocateTarget()` | ✗ |
| `width` | `number` | let/var | `3 * Math.max( this._cubeSize, 16 * 7 )` | ✗ |
| `height` | `number` | let/var | `4 * this._cubeSize` | ✗ |
| `tmpMesh` | `Mesh` | let/var | `new Mesh( this._lodPlanes[ 0 ], material )` | ✗ |
| `cubeCamera` | `PerspectiveCamera` | let/var | `_cubeCamera` | ✗ |
| `upSign` | `number[]` | let/var | `[ 1, 1, 1, 1, - 1, 1 ]` | ✗ |
| `forwardSign` | `number[]` | let/var | `[ 1, - 1, 1, - 1, 1, - 1 ]` | ✗ |
| `renderer` | `Renderer` | let/var | `this._renderer` | ✗ |
| `originalAutoClear` | `any` | let/var | `renderer.autoClear` | ✗ |
| `backgroundBox` | `any` | let/var | `this._backgroundBox` | ✗ |
| `backgroundMaterial` | `MeshBasicMaterial` | let/var | `new MeshBasicMaterial( { name: 'PMREM.Background', side: BackSide, depthWrite...` | ✗ |
| `useSolidColor` | `boolean` | let/var | `false` | ✗ |
| `background` | `any` | let/var | `scene.background` | ✗ |
| `col` | `number` | let/var | `i % 3` | ✗ |
| `size` | `number` | let/var | `this._cubeSize` | ✗ |
| `renderer` | `Renderer` | let/var | `this._renderer` | ✗ |
| `isCubeTexture` | `boolean` | let/var | `( texture.mapping === CubeReflectionMapping \|\| texture.mapping === CubeRefr...` | ✗ |
| `material` | `NodeMaterial` | let/var | `isCubeTexture ? this._cubemapMaterial : this._equirectMaterial` | ✗ |
| `mesh` | `any` | let/var | `this._lodMeshes[ 0 ]` | ✗ |
| `size` | `number` | let/var | `this._cubeSize` | ✗ |
| `renderer` | `Renderer` | let/var | `this._renderer` | ✗ |
| `autoClear` | `any` | let/var | `renderer.autoClear` | ✗ |
| `n` | `number` | let/var | `this._lodPlanes.length` | ✗ |
| `poleAxis` | `Vector3` | let/var | `_axisDirections[ ( n - i - 1 ) % _axisDirections.length ]` | ✗ |
| `pingPongRenderTarget` | `RenderTarget` | let/var | `this._pingPongRenderTarget` | ✗ |
| `renderer` | `Renderer` | let/var | `this._renderer` | ✗ |
| `blurMaterial` | `NodeMaterial` | let/var | `this._blurMaterial` | ✗ |
| `STANDARD_DEVIATIONS` | `3` | let/var | `3` | ✗ |
| `blurMesh` | `any` | let/var | `this._lodMeshes[ lodOut ]` | ✗ |
| `pixels` | `number` | let/var | `this._sizeLods[ lodIn ] - 1` | ✗ |
| `radiansPerPixel` | `number` | let/var | `isFinite( sigmaRadians ) ? Math.PI / ( 2 * pixels ) : 2 * Math.PI / ( 2 * MAX...` | ✗ |
| `sigmaPixels` | `number` | let/var | `sigmaRadians / radiansPerPixel` | ✗ |
| `samples` | `number` | let/var | `isFinite( sigmaRadians ) ? 1 + Math.floor( STANDARD_DEVIATIONS * sigmaPixels ...` | ✗ |
| `weights` | `any[]` | let/var | `[]` | ✗ |
| `sum` | `number` | let/var | `0` | ✗ |
| `x` | `number` | let/var | `i / sigmaPixels` | ✗ |
| `outputSize` | `any` | let/var | `this._sizeLods[ lodOut ]` | ✗ |
| `x` | `number` | let/var | `3 * outputSize * ( lodOut > _lodMax - LOD_MIN ? lodOut - _lodMax + LOD_MIN : 0 )` | ✗ |
| `y` | `number` | let/var | `4 * ( this._cubeSize - outputSize )` | ✗ |
| `lodPlanes` | `any[]` | let/var | `[]` | ✗ |
| `sizeLods` | `any[]` | let/var | `[]` | ✗ |
| `sigmas` | `any[]` | let/var | `[]` | ✗ |
| `lodMeshes` | `any[]` | let/var | `[]` | ✗ |
| `lod` | `any` | let/var | `lodMax` | ✗ |
| `totalLods` | `number` | let/var | `lodMax - LOD_MIN + 1 + EXTRA_LOD_SIGMA.length` | ✗ |
| `sigma` | `number` | let/var | `1.0 / sizeLod` | ✗ |
| `texelSize` | `number` | let/var | `1.0 / ( sizeLod - 2 )` | ✗ |
| `min` | `number` | let/var | `- texelSize` | ✗ |
| `max` | `number` | let/var | `1 + texelSize` | ✗ |
| `uv1` | `number[]` | let/var | `[ min, min, max, min, max, max, min, min, max, max, min, max ]` | ✗ |
| `cubeFaces` | `6` | let/var | `6` | ✗ |
| `vertices` | `6` | let/var | `6` | ✗ |
| `positionSize` | `3` | let/var | `3` | ✗ |
| `uvSize` | `2` | let/var | `2` | ✗ |
| `faceIndexSize` | `1` | let/var | `1` | ✗ |
| `position` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( positionSize * vertices * cubeFaces )` | ✗ |
| `uv` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( uvSize * vertices * cubeFaces )` | ✗ |
| `faceIndex` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( faceIndexSize * vertices * cubeFaces )` | ✗ |
| `x` | `number` | let/var | `( face % 3 ) * 2 / 3 - 1` | ✗ |
| `y` | `0 \| -1` | let/var | `face > 2 ? 0 : - 1` | ✗ |
| `coordinates` | `number[]` | let/var | `[ x, y, 0, x + 2 / 3, y, 0, x + 2 / 3, y + 1, 0, x, y, 0, x + 2 / 3, y + 1, 0...` | ✗ |
| `faceIdx` | `number` | let/var | `_faceLib[ face ]` | ✗ |
| `fill` | `number[]` | let/var | `[ faceIdx, faceIdx, faceIdx, faceIdx, faceIdx, faceIdx ]` | ✗ |
| `planes` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `params` | `{ magFilter: number; minFilter: numbe...` | let/var | `{ magFilter: LinearFilter, minFilter: LinearFilter, generateMipmaps: false, t...` | ✗ |
| `cubeUVRenderTarget` | `RenderTarget` | let/var | `new RenderTarget( width, height, params )` | ✗ |
| `material` | `NodeMaterial` | let/var | `new NodeMaterial()` | ✗ |
| `materialUniforms` | `{ n: any; latitudinal: UniformNode; w...` | let/var | `{ n, latitudinal, weights, poleAxis, outputDirection: _outputDirection, dThet...` | ✗ |


---

## Functions

### `PMREMGenerator.fromScene(scene: Scene, sigma: number, near: number, far: number, options: { size?: number; renderTarget?: Vector3; }): RenderTarget`

**JSDoc:**
```typescript
/**
	 * Generates a PMREM from a supplied Scene, which can be faster than using an
	 * image if networking bandwidth is low. Optional sigma specifies a blur radius
	 * in radians to be applied to the scene before PMREM generation. Optional near
	 * and far planes ensure the scene is rendered in its entirety.
	 *
	 * @param {Scene} scene - The scene to be captured.
	 * @param {number} [sigma=0] - The blur radius in radians.
	 * @param {number} [near=0.1] - The near plane distance.
	 * @param {number} [far=100] - The far plane distance.
	 * @param {Object} [options={}] - The configuration options.
	 * @param {number} [options.size=256] - The texture size of the PMREM.
	 * @param {Vector3} [options.renderTarget=origin] - The position of the internal cube camera that renders the scene.
	 * @param {?RenderTarget} [options.renderTarget=null] - The render target to use.
	 * @return {RenderTarget} The resulting PMREM.
	 * @see {@link PMREMGenerator#fromSceneAsync}
	 */
```

**Parameters:**

- **`scene`** `Scene`
- **`sigma`** `number`
- **`near`** `number`
- **`far`** `number`
- **`options`** `{ size?: number; renderTarget?: Vector3; }`

**Returns:** `RenderTarget`

**Calls:**

- `this._setSize`
- `console.warn`
- `this._allocateTarget`
- `this.fromSceneAsync`
- `this._renderer.getRenderTarget`
- `this._renderer.getActiveCubeFace`
- `this._renderer.getActiveMipmapLevel`
- `this._init`
- `this._sceneToCubeUV`
- `this._blur`
- `this._applyPMREM`
- `this._cleanup`

<details><summary>Code</summary>

```typescript
fromScene( scene, sigma = 0, near = 0.1, far = 100, options = {} ) {

		const {
			size = 256,
			position = _origin,
			renderTarget = null,
		} = options;

		this._setSize( size );

		if ( this._hasInitialized === false ) {

			console.warn( 'THREE.PMREMGenerator: .fromScene() called before the backend is initialized. Try using .fromSceneAsync() instead.' );

			const cubeUVRenderTarget = renderTarget || this._allocateTarget();

			options.renderTarget = cubeUVRenderTarget;

			this.fromSceneAsync( scene, sigma, near, far, options );

			return cubeUVRenderTarget;

		}

		_oldTarget = this._renderer.getRenderTarget();
		_oldActiveCubeFace = this._renderer.getActiveCubeFace();
		_oldActiveMipmapLevel = this._renderer.getActiveMipmapLevel();

		const cubeUVRenderTarget = renderTarget || this._allocateTarget();
		cubeUVRenderTarget.depthBuffer = true;

		this._init( cubeUVRenderTarget );

		this._sceneToCubeUV( scene, near, far, cubeUVRenderTarget, position );

		if ( sigma > 0 ) {

			this._blur( cubeUVRenderTarget, 0, 0, sigma );

		}

		this._applyPMREM( cubeUVRenderTarget );

		this._cleanup( cubeUVRenderTarget );

		return cubeUVRenderTarget;

	}
```
</details>

### `PMREMGenerator.fromSceneAsync(scene: Scene, sigma: number, near: number, far: number, options: { size?: number; position?: Vector3; renderTarget?: RenderTarget; }): Promise<RenderTarget>`

**JSDoc:**
```typescript
/**
	 * Generates a PMREM from a supplied Scene, which can be faster than using an
	 * image if networking bandwidth is low. Optional sigma specifies a blur radius
	 * in radians to be applied to the scene before PMREM generation. Optional near
	 * and far planes ensure the scene is rendered in its entirety (the cubeCamera
	 * is placed at the origin).
	 *
	 * @param {Scene} scene - The scene to be captured.
	 * @param {number} [sigma=0] - The blur radius in radians.
	 * @param {number} [near=0.1] - The near plane distance.
	 * @param {number} [far=100] - The far plane distance.
	 * @param {Object} [options={}] - The configuration options.
	 * @param {number} [options.size=256] - The texture size of the PMREM.
	 * @param {Vector3} [options.position=origin] - The position of the internal cube camera that renders the scene.
	 * @param {?RenderTarget} [options.renderTarget=null] - The render target to use.
	 * @return {Promise<RenderTarget>} A Promise that resolve with the PMREM when the generation has been finished.
	 * @see {@link PMREMGenerator#fromScene}
	 */
```

**Parameters:**

- **`scene`** `Scene`
- **`sigma`** `number`
- **`near`** `number`
- **`far`** `number`
- **`options`** `{ size?: number; position?: Vector3; renderTarget?: RenderTarget; }`

**Returns:** `Promise<RenderTarget>`

**Calls:**

- `this._renderer.init`
- `this.fromScene`

<details><summary>Code</summary>

```typescript
async fromSceneAsync( scene, sigma = 0, near = 0.1, far = 100, options = {} ) {

		if ( this._hasInitialized === false ) await this._renderer.init();

		return this.fromScene( scene, sigma, near, far, options );

	}
```
</details>

### `PMREMGenerator.fromEquirectangular(equirectangular: Texture, renderTarget: RenderTarget): RenderTarget`

**JSDoc:**
```typescript
/**
	 * Generates a PMREM from an equirectangular texture, which can be either LDR
	 * or HDR. The ideal input image size is 1k (1024 x 512),
	 * as this matches best with the 256 x 256 cubemap output.
	 *
	 * @param {Texture} equirectangular - The equirectangular texture to be converted.
	 * @param {?RenderTarget} [renderTarget=null] - The render target to use.
	 * @return {RenderTarget} The resulting PMREM.
	 * @see {@link PMREMGenerator#fromEquirectangularAsync}
	 */
```

**Parameters:**

- **`equirectangular`** `Texture`
- **`renderTarget`** `RenderTarget`

**Returns:** `RenderTarget`

**Calls:**

- `console.warn`
- `this._setSizeFromTexture`
- `this._allocateTarget`
- `this.fromEquirectangularAsync`
- `this._fromTexture`

<details><summary>Code</summary>

```typescript
fromEquirectangular( equirectangular, renderTarget = null ) {

		if ( this._hasInitialized === false ) {

			console.warn( 'THREE.PMREMGenerator: .fromEquirectangular() called before the backend is initialized. Try using .fromEquirectangularAsync() instead.' );

			this._setSizeFromTexture( equirectangular );

			const cubeUVRenderTarget = renderTarget || this._allocateTarget();

			this.fromEquirectangularAsync( equirectangular, cubeUVRenderTarget );

			return cubeUVRenderTarget;

		}

		return this._fromTexture( equirectangular, renderTarget );

	}
```
</details>

### `PMREMGenerator.fromEquirectangularAsync(equirectangular: Texture, renderTarget: RenderTarget): Promise<RenderTarget>`

**JSDoc:**
```typescript
/**
	 * Generates a PMREM from an equirectangular texture, which can be either LDR
	 * or HDR. The ideal input image size is 1k (1024 x 512),
	 * as this matches best with the 256 x 256 cubemap output.
	 *
	 * @param {Texture} equirectangular - The equirectangular texture to be converted.
	 * @param {?RenderTarget} [renderTarget=null] - The render target to use.
	 * @return {Promise<RenderTarget>} The resulting PMREM.
	 * @see {@link PMREMGenerator#fromEquirectangular}
	 */
```

**Parameters:**

- **`equirectangular`** `Texture`
- **`renderTarget`** `RenderTarget`

**Returns:** `Promise<RenderTarget>`

**Calls:**

- `this._renderer.init`
- `this._fromTexture`

<details><summary>Code</summary>

```typescript
async fromEquirectangularAsync( equirectangular, renderTarget = null ) {

		if ( this._hasInitialized === false ) await this._renderer.init();

		return this._fromTexture( equirectangular, renderTarget );

	}
```
</details>

### `PMREMGenerator.fromCubemap(cubemap: Texture, renderTarget: RenderTarget): RenderTarget`

**JSDoc:**
```typescript
/**
	 * Generates a PMREM from an cubemap texture, which can be either LDR
	 * or HDR. The ideal input cube size is 256 x 256,
	 * as this matches best with the 256 x 256 cubemap output.
	 *
	 * @param {Texture} cubemap - The cubemap texture to be converted.
	 * @param {?RenderTarget} [renderTarget=null] - The render target to use.
	 * @return {RenderTarget} The resulting PMREM.
	 * @see {@link PMREMGenerator#fromCubemapAsync}
	 */
```

**Parameters:**

- **`cubemap`** `Texture`
- **`renderTarget`** `RenderTarget`

**Returns:** `RenderTarget`

**Calls:**

- `console.warn`
- `this._setSizeFromTexture`
- `this._allocateTarget`
- `this.fromCubemapAsync`
- `this._fromTexture`

<details><summary>Code</summary>

```typescript
fromCubemap( cubemap, renderTarget = null ) {

		if ( this._hasInitialized === false ) {

			console.warn( 'THREE.PMREMGenerator: .fromCubemap() called before the backend is initialized. Try using .fromCubemapAsync() instead.' );

			this._setSizeFromTexture( cubemap );

			const cubeUVRenderTarget = renderTarget || this._allocateTarget();

			this.fromCubemapAsync( cubemap, renderTarget );

			return cubeUVRenderTarget;

		}

		return this._fromTexture( cubemap, renderTarget );

	}
```
</details>

### `PMREMGenerator.fromCubemapAsync(cubemap: Texture, renderTarget: RenderTarget): Promise<RenderTarget>`

**JSDoc:**
```typescript
/**
	 * Generates a PMREM from an cubemap texture, which can be either LDR
	 * or HDR. The ideal input cube size is 256 x 256,
	 * with the 256 x 256 cubemap output.
	 *
	 * @param {Texture} cubemap - The cubemap texture to be converted.
	 * @param {?RenderTarget} [renderTarget=null] - The render target to use.
	 * @return {Promise<RenderTarget>} The resulting PMREM.
	 * @see {@link PMREMGenerator#fromCubemap}
	 */
```

**Parameters:**

- **`cubemap`** `Texture`
- **`renderTarget`** `RenderTarget`

**Returns:** `Promise<RenderTarget>`

**Calls:**

- `this._renderer.init`
- `this._fromTexture`

<details><summary>Code</summary>

```typescript
async fromCubemapAsync( cubemap, renderTarget = null ) {

		if ( this._hasInitialized === false ) await this._renderer.init();

		return this._fromTexture( cubemap, renderTarget );

	}
```
</details>

### `PMREMGenerator.compileCubemapShader(): Promise<any>`

**JSDoc:**
```typescript
/**
	 * Pre-compiles the cubemap shader. You can get faster start-up by invoking this method during
	 * your texture's network fetch for increased concurrency.
	 *
	 * @returns {Promise}
	 */
```

**Returns:** `Promise<any>`

**Calls:**

- `_getCubemapMaterial`
- `this._compileMaterial`

<details><summary>Code</summary>

```typescript
async compileCubemapShader() {

		if ( this._cubemapMaterial === null ) {

			this._cubemapMaterial = _getCubemapMaterial();
			await this._compileMaterial( this._cubemapMaterial );

		}

	}
```
</details>

### `PMREMGenerator.compileEquirectangularShader(): Promise<any>`

**JSDoc:**
```typescript
/**
	 * Pre-compiles the equirectangular shader. You can get faster start-up by invoking this method during
	 * your texture's network fetch for increased concurrency.
	 *
	 * @returns {Promise}
	 */
```

**Returns:** `Promise<any>`

**Calls:**

- `_getEquirectMaterial`
- `this._compileMaterial`

<details><summary>Code</summary>

```typescript
async compileEquirectangularShader() {

		if ( this._equirectMaterial === null ) {

			this._equirectMaterial = _getEquirectMaterial();
			await this._compileMaterial( this._equirectMaterial );

		}

	}
```
</details>

### `PMREMGenerator.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Disposes of the PMREMGenerator's internal memory. Note that PMREMGenerator is a static class,
	 * so you should not need more than one PMREMGenerator object. If you do, calling dispose() on
	 * one of them will cause any others to also become unusable.
	 */
```

**Returns:** `void`

**Calls:**

- `this._dispose`
- `this._cubemapMaterial.dispose`
- `this._equirectMaterial.dispose`
- `this._backgroundBox.geometry.dispose`
- `this._backgroundBox.material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this._dispose();

		if ( this._cubemapMaterial !== null ) this._cubemapMaterial.dispose();
		if ( this._equirectMaterial !== null ) this._equirectMaterial.dispose();
		if ( this._backgroundBox !== null ) {

			this._backgroundBox.geometry.dispose();
			this._backgroundBox.material.dispose();

		}

	}
```
</details>

### `PMREMGenerator._setSizeFromTexture(texture: any): void`

**Parameters:**

- **`texture`** `any`

**Returns:** `void`

**Calls:**

- `this._setSize`

<details><summary>Code</summary>

```typescript
_setSizeFromTexture( texture ) {

		if ( texture.mapping === CubeReflectionMapping || texture.mapping === CubeRefractionMapping ) {

			this._setSize( texture.image.length === 0 ? 16 : ( texture.image[ 0 ].width || texture.image[ 0 ].image.width ) );

		} else { // Equirectangular

			this._setSize( texture.image.width / 4 );

		}

	}
```
</details>

### `PMREMGenerator._setSize(cubeSize: any): void`

**Parameters:**

- **`cubeSize`** `any`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `Math.log2`
- `Math.pow`

<details><summary>Code</summary>

```typescript
_setSize( cubeSize ) {

		this._lodMax = Math.floor( Math.log2( cubeSize ) );
		this._cubeSize = Math.pow( 2, this._lodMax );

	}
```
</details>

### `PMREMGenerator._dispose(): void`

**Returns:** `void`

**Calls:**

- `this._blurMaterial.dispose`
- `this._pingPongRenderTarget.dispose`
- `this._lodPlanes[ i ].dispose`

<details><summary>Code</summary>

```typescript
_dispose() {

		if ( this._blurMaterial !== null ) this._blurMaterial.dispose();

		if ( this._pingPongRenderTarget !== null ) this._pingPongRenderTarget.dispose();

		for ( let i = 0; i < this._lodPlanes.length; i ++ ) {

			this._lodPlanes[ i ].dispose();

		}

	}
```
</details>

### `PMREMGenerator._cleanup(outputTarget: any): void`

**Parameters:**

- **`outputTarget`** `any`

**Returns:** `void`

**Calls:**

- `this._renderer.setRenderTarget`
- `_setViewport`

<details><summary>Code</summary>

```typescript
_cleanup( outputTarget ) {

		this._renderer.setRenderTarget( _oldTarget, _oldActiveCubeFace, _oldActiveMipmapLevel );
		outputTarget.scissorTest = false;
		_setViewport( outputTarget, 0, 0, outputTarget.width, outputTarget.height );

	}
```
</details>

### `PMREMGenerator._fromTexture(texture: any, renderTarget: any): any`

**Parameters:**

- **`texture`** `any`
- **`renderTarget`** `any`

**Returns:** `any`

**Calls:**

- `this._setSizeFromTexture`
- `this._renderer.getRenderTarget`
- `this._renderer.getActiveCubeFace`
- `this._renderer.getActiveMipmapLevel`
- `this._allocateTarget`
- `this._init`
- `this._textureToCubeUV`
- `this._applyPMREM`
- `this._cleanup`

<details><summary>Code</summary>

```typescript
_fromTexture( texture, renderTarget ) {

		this._setSizeFromTexture( texture );

		_oldTarget = this._renderer.getRenderTarget();
		_oldActiveCubeFace = this._renderer.getActiveCubeFace();
		_oldActiveMipmapLevel = this._renderer.getActiveMipmapLevel();

		const cubeUVRenderTarget = renderTarget || this._allocateTarget();
		this._init( cubeUVRenderTarget );
		this._textureToCubeUV( texture, cubeUVRenderTarget );
		this._applyPMREM( cubeUVRenderTarget );
		this._cleanup( cubeUVRenderTarget );

		return cubeUVRenderTarget;

	}
```
</details>

### `PMREMGenerator._allocateTarget(): RenderTarget`

**Returns:** `RenderTarget`

**Calls:**

- `Math.max`
- `_createRenderTarget`

<details><summary>Code</summary>

```typescript
_allocateTarget() {

		const width = 3 * Math.max( this._cubeSize, 16 * 7 );
		const height = 4 * this._cubeSize;

		const cubeUVRenderTarget = _createRenderTarget( width, height );

		return cubeUVRenderTarget;

	}
```
</details>

### `PMREMGenerator._init(renderTarget: any): void`

**Parameters:**

- **`renderTarget`** `any`

**Returns:** `void`

**Calls:**

- `this._dispose`
- `_createRenderTarget`
- `_createPlanes`
- `_getBlurShader`

<details><summary>Code</summary>

```typescript
_init( renderTarget ) {

		if ( this._pingPongRenderTarget === null || this._pingPongRenderTarget.width !== renderTarget.width || this._pingPongRenderTarget.height !== renderTarget.height ) {

			if ( this._pingPongRenderTarget !== null ) {

				this._dispose();

			}

			this._pingPongRenderTarget = _createRenderTarget( renderTarget.width, renderTarget.height );

			const { _lodMax } = this;
			( { sizeLods: this._sizeLods, lodPlanes: this._lodPlanes, sigmas: this._sigmas, lodMeshes: this._lodMeshes } = _createPlanes( _lodMax ) );

			this._blurMaterial = _getBlurShader( _lodMax, renderTarget.width, renderTarget.height );

		}

	}
```
</details>

### `PMREMGenerator._compileMaterial(material: any): Promise<void>`

**Parameters:**

- **`material`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `this._renderer.compile`

<details><summary>Code</summary>

```typescript
async _compileMaterial( material ) {

		const tmpMesh = new Mesh( this._lodPlanes[ 0 ], material );
		await this._renderer.compile( tmpMesh, _flatCamera );

	}
```
</details>

### `PMREMGenerator._sceneToCubeUV(scene: any, near: any, far: any, cubeUVRenderTarget: any, position: any): void`

**Parameters:**

- **`scene`** `any`
- **`near`** `any`
- **`far`** `any`
- **`cubeUVRenderTarget`** `any`
- **`position`** `any`

**Returns:** `void`

**Calls:**

- `renderer.getClearColor`
- `backgroundBox.material.color.copy`
- `renderer.setRenderTarget`
- `renderer.clear`
- `renderer.render`
- `cubeCamera.up.set`
- `cubeCamera.position.set`
- `cubeCamera.lookAt`
- `_setViewport`

**Internal Comments:**
```
// px, py, pz, nx, ny, nz (x2)
```

<details><summary>Code</summary>

```typescript
_sceneToCubeUV( scene, near, far, cubeUVRenderTarget, position ) {

		const cubeCamera = _cubeCamera;
		cubeCamera.near = near;
		cubeCamera.far = far;

		// px, py, pz, nx, ny, nz
		const upSign = [ 1, 1, 1, 1, - 1, 1 ];
		const forwardSign = [ 1, - 1, 1, - 1, 1, - 1 ];

		const renderer = this._renderer;

		const originalAutoClear = renderer.autoClear;

		renderer.getClearColor( _clearColor );

		renderer.autoClear = false;

		let backgroundBox = this._backgroundBox;

		if ( backgroundBox === null ) {

			const backgroundMaterial = new MeshBasicMaterial( {
				name: 'PMREM.Background',
				side: BackSide,
				depthWrite: false,
				depthTest: false
			} );

			backgroundBox = new Mesh( new BoxGeometry(), backgroundMaterial );

		}

		let useSolidColor = false;
		const background = scene.background;

		if ( background ) {

			if ( background.isColor ) {

				backgroundBox.material.color.copy( background );
				scene.background = null;
				useSolidColor = true;

			}

		} else {

			backgroundBox.material.color.copy( _clearColor );
			useSolidColor = true;

		}

		renderer.setRenderTarget( cubeUVRenderTarget );

		renderer.clear();

		if ( useSolidColor ) {

			renderer.render( backgroundBox, cubeCamera );

		}

		for ( let i = 0; i < 6; i ++ ) {

			const col = i % 3;

			if ( col === 0 ) {

				cubeCamera.up.set( 0, upSign[ i ], 0 );
				cubeCamera.position.set( position.x, position.y, position.z );
				cubeCamera.lookAt( position.x + forwardSign[ i ], position.y, position.z );

			} else if ( col === 1 ) {

				cubeCamera.up.set( 0, 0, upSign[ i ] );
				cubeCamera.position.set( position.x, position.y, position.z );
				cubeCamera.lookAt( position.x, position.y + forwardSign[ i ], position.z );


			} else {

				cubeCamera.up.set( 0, upSign[ i ], 0 );
				cubeCamera.position.set( position.x, position.y, position.z );
				cubeCamera.lookAt( position.x, position.y, position.z + forwardSign[ i ] );


			}

			const size = this._cubeSize;

			_setViewport( cubeUVRenderTarget, col * size, i > 2 ? size : 0, size, size );

			renderer.render( scene, cubeCamera );

		}

		renderer.autoClear = originalAutoClear;
		scene.background = background;

	}
```
</details>

### `PMREMGenerator._textureToCubeUV(texture: any, cubeUVRenderTarget: any): void`

**Parameters:**

- **`texture`** `any`
- **`cubeUVRenderTarget`** `any`

**Returns:** `void`

**Calls:**

- `_getCubemapMaterial`
- `_getEquirectMaterial`
- `_setViewport`
- `renderer.setRenderTarget`
- `renderer.render`

<details><summary>Code</summary>

```typescript
_textureToCubeUV( texture, cubeUVRenderTarget ) {

		const renderer = this._renderer;

		const isCubeTexture = ( texture.mapping === CubeReflectionMapping || texture.mapping === CubeRefractionMapping );

		if ( isCubeTexture ) {

			if ( this._cubemapMaterial === null ) {

				this._cubemapMaterial = _getCubemapMaterial( texture );

			}

		} else {

			if ( this._equirectMaterial === null ) {

				this._equirectMaterial = _getEquirectMaterial( texture );

			}

		}

		const material = isCubeTexture ? this._cubemapMaterial : this._equirectMaterial;
		material.fragmentNode.value = texture;

		const mesh = this._lodMeshes[ 0 ];
		mesh.material = material;

		const size = this._cubeSize;

		_setViewport( cubeUVRenderTarget, 0, 0, 3 * size, 2 * size );

		renderer.setRenderTarget( cubeUVRenderTarget );
		renderer.render( mesh, _flatCamera );

	}
```
</details>

### `PMREMGenerator._applyPMREM(cubeUVRenderTarget: any): void`

**Parameters:**

- **`cubeUVRenderTarget`** `any`

**Returns:** `void`

**Calls:**

- `Math.sqrt`
- `this._blur`

<details><summary>Code</summary>

```typescript
_applyPMREM( cubeUVRenderTarget ) {

		const renderer = this._renderer;
		const autoClear = renderer.autoClear;
		renderer.autoClear = false;
		const n = this._lodPlanes.length;

		for ( let i = 1; i < n; i ++ ) {

			const sigma = Math.sqrt( this._sigmas[ i ] * this._sigmas[ i ] - this._sigmas[ i - 1 ] * this._sigmas[ i - 1 ] );

			const poleAxis = _axisDirections[ ( n - i - 1 ) % _axisDirections.length ];

			this._blur( cubeUVRenderTarget, i - 1, i, sigma, poleAxis );

		}

		renderer.autoClear = autoClear;

	}
```
</details>

### `PMREMGenerator._blur(cubeUVRenderTarget: RenderTarget, lodIn: number, lodOut: number, sigma: number, poleAxis: Vector3): void`

**JSDoc:**
```typescript
/**
	 * This is a two-pass Gaussian blur for a cubemap. Normally this is done
	 * vertically and horizontally, but this breaks down on a cube. Here we apply
	 * the blur latitudinally (around the poles), and then longitudinally (towards
	 * the poles) to approximate the orthogonally-separable blur. It is least
	 * accurate at the poles, but still does a decent job.
	 *
	 * @private
	 * @param {RenderTarget} cubeUVRenderTarget - The cubemap render target.
	 * @param {number} lodIn - The input level-of-detail.
	 * @param {number} lodOut - The output level-of-detail.
	 * @param {number} sigma - The blur radius in radians.
	 * @param {Vector3} [poleAxis] - The pole axis.
	 */
```

**Parameters:**

- **`cubeUVRenderTarget`** `RenderTarget`
- **`lodIn`** `number`
- **`lodOut`** `number`
- **`sigma`** `number`
- **`poleAxis`** `Vector3`

**Returns:** `void`

**Calls:**

- `this._halfBlur`

<details><summary>Code</summary>

```typescript
_blur( cubeUVRenderTarget, lodIn, lodOut, sigma, poleAxis ) {

		const pingPongRenderTarget = this._pingPongRenderTarget;

		this._halfBlur(
			cubeUVRenderTarget,
			pingPongRenderTarget,
			lodIn,
			lodOut,
			sigma,
			'latitudinal',
			poleAxis );

		this._halfBlur(
			pingPongRenderTarget,
			cubeUVRenderTarget,
			lodOut,
			lodOut,
			sigma,
			'longitudinal',
			poleAxis );

	}
```
</details>

### `PMREMGenerator._halfBlur(targetIn: any, targetOut: any, lodIn: any, lodOut: any, sigmaRadians: any, direction: any, poleAxis: any): void`

**Parameters:**

- **`targetIn`** `any`
- **`targetOut`** `any`
- **`lodIn`** `any`
- **`lodOut`** `any`
- **`sigmaRadians`** `any`
- **`direction`** `any`
- **`poleAxis`** `any`

**Returns:** `void`

**Calls:**

- `console.error`
- `_uniformsMap.get`
- `isFinite`
- `Math.floor`
- `console.warn`
- `Math.exp`
- `weights.push`
- `_setViewport`
- `renderer.setRenderTarget`
- `renderer.render`

**Internal Comments:**
```
// Number of standard deviations at which to cut off the discrete approximation. (x2)
```

<details><summary>Code</summary>

```typescript
_halfBlur( targetIn, targetOut, lodIn, lodOut, sigmaRadians, direction, poleAxis ) {

		const renderer = this._renderer;
		const blurMaterial = this._blurMaterial;

		if ( direction !== 'latitudinal' && direction !== 'longitudinal' ) {

			console.error( 'blur direction must be either latitudinal or longitudinal!' );

		}

		// Number of standard deviations at which to cut off the discrete approximation.
		const STANDARD_DEVIATIONS = 3;

		const blurMesh = this._lodMeshes[ lodOut ];
		blurMesh.material = blurMaterial;

		const blurUniforms = _uniformsMap.get( blurMaterial );

		const pixels = this._sizeLods[ lodIn ] - 1;
		const radiansPerPixel = isFinite( sigmaRadians ) ? Math.PI / ( 2 * pixels ) : 2 * Math.PI / ( 2 * MAX_SAMPLES - 1 );
		const sigmaPixels = sigmaRadians / radiansPerPixel;
		const samples = isFinite( sigmaRadians ) ? 1 + Math.floor( STANDARD_DEVIATIONS * sigmaPixels ) : MAX_SAMPLES;

		if ( samples > MAX_SAMPLES ) {

			console.warn( `sigmaRadians, ${
				sigmaRadians}, is too large and will clip, as it requested ${
				samples} samples when the maximum is set to ${MAX_SAMPLES}` );

		}

		const weights = [];
		let sum = 0;

		for ( let i = 0; i < MAX_SAMPLES; ++ i ) {

			const x = i / sigmaPixels;
			const weight = Math.exp( - x * x / 2 );
			weights.push( weight );

			if ( i === 0 ) {

				sum += weight;

			} else if ( i < samples ) {

				sum += 2 * weight;

			}

		}

		for ( let i = 0; i < weights.length; i ++ ) {

			weights[ i ] = weights[ i ] / sum;

		}

		targetIn.texture.frame = ( targetIn.texture.frame || 0 ) + 1;

		blurUniforms.envMap.value = targetIn.texture;
		blurUniforms.samples.value = samples;
		blurUniforms.weights.array = weights;
		blurUniforms.latitudinal.value = direction === 'latitudinal' ? 1 : 0;

		if ( poleAxis ) {

			blurUniforms.poleAxis.value = poleAxis;

		}

		const { _lodMax } = this;
		blurUniforms.dTheta.value = radiansPerPixel;
		blurUniforms.mipInt.value = _lodMax - lodIn;

		const outputSize = this._sizeLods[ lodOut ];
		const x = 3 * outputSize * ( lodOut > _lodMax - LOD_MIN ? lodOut - _lodMax + LOD_MIN : 0 );
		const y = 4 * ( this._cubeSize - outputSize );

		_setViewport( targetOut, x, y, 3 * outputSize, 2 * outputSize );
		renderer.setRenderTarget( targetOut );
		renderer.render( blurMesh, _flatCamera );

	}
```
</details>

### `_createPlanes(lodMax: any): { lodPlanes: BufferGeometry[]; sizeLods: number[]; sigmas: number[]; lodMeshes: Mesh[]; }`

**Parameters:**

- **`lodMax`** `any`

**Returns:** `{ lodPlanes: BufferGeometry[]; sizeLods: number[]; sigmas: number[]; lodMeshes: Mesh[]; }`

**Calls:**

- `Math.pow`
- `sizeLods.push`
- `sigmas.push`
- `position.set`
- `uv.set`
- `faceIndex.set`
- `planes.setAttribute`
- `lodPlanes.push`
- `lodMeshes.push`

<details><summary>Code</summary>

```typescript
function _createPlanes( lodMax ) {

	const lodPlanes = [];
	const sizeLods = [];
	const sigmas = [];
	const lodMeshes = [];

	let lod = lodMax;

	const totalLods = lodMax - LOD_MIN + 1 + EXTRA_LOD_SIGMA.length;

	for ( let i = 0; i < totalLods; i ++ ) {

		const sizeLod = Math.pow( 2, lod );
		sizeLods.push( sizeLod );
		let sigma = 1.0 / sizeLod;

		if ( i > lodMax - LOD_MIN ) {

			sigma = EXTRA_LOD_SIGMA[ i - lodMax + LOD_MIN - 1 ];

		} else if ( i === 0 ) {

			sigma = 0;

		}

		sigmas.push( sigma );

		const texelSize = 1.0 / ( sizeLod - 2 );
		const min = - texelSize;
		const max = 1 + texelSize;
		const uv1 = [ min, min, max, min, max, max, min, min, max, max, min, max ];

		const cubeFaces = 6;
		const vertices = 6;
		const positionSize = 3;
		const uvSize = 2;
		const faceIndexSize = 1;

		const position = new Float32Array( positionSize * vertices * cubeFaces );
		const uv = new Float32Array( uvSize * vertices * cubeFaces );
		const faceIndex = new Float32Array( faceIndexSize * vertices * cubeFaces );

		for ( let face = 0; face < cubeFaces; face ++ ) {

			const x = ( face % 3 ) * 2 / 3 - 1;
			const y = face > 2 ? 0 : - 1;
			const coordinates = [
				x, y, 0,
				x + 2 / 3, y, 0,
				x + 2 / 3, y + 1, 0,
				x, y, 0,
				x + 2 / 3, y + 1, 0,
				x, y + 1, 0
			];

			const faceIdx = _faceLib[ face ];
			position.set( coordinates, positionSize * vertices * faceIdx );
			uv.set( uv1, uvSize * vertices * faceIdx );
			const fill = [ faceIdx, faceIdx, faceIdx, faceIdx, faceIdx, faceIdx ];
			faceIndex.set( fill, faceIndexSize * vertices * faceIdx );

		}

		const planes = new BufferGeometry();
		planes.setAttribute( 'position', new BufferAttribute( position, positionSize ) );
		planes.setAttribute( 'uv', new BufferAttribute( uv, uvSize ) );
		planes.setAttribute( 'faceIndex', new BufferAttribute( faceIndex, faceIndexSize ) );
		lodPlanes.push( planes );
		lodMeshes.push( new Mesh( planes, null ) );

		if ( lod > LOD_MIN ) {

			lod --;

		}

	}

	return { lodPlanes, sizeLods, sigmas, lodMeshes };

}
```
</details>

### `_createRenderTarget(width: any, height: any): RenderTarget`

**Parameters:**

- **`width`** `any`
- **`height`** `any`

**Returns:** `RenderTarget`

<details><summary>Code</summary>

```typescript
function _createRenderTarget( width, height ) {

	const params = {
		magFilter: LinearFilter,
		minFilter: LinearFilter,
		generateMipmaps: false,
		type: HalfFloatType,
		format: RGBAFormat,
		colorSpace: LinearSRGBColorSpace,
		//depthBuffer: false
	};

	const cubeUVRenderTarget = new RenderTarget( width, height, params );
	cubeUVRenderTarget.texture.mapping = CubeUVReflectionMapping;
	cubeUVRenderTarget.texture.name = 'PMREM.cubeUv';
	cubeUVRenderTarget.texture.isPMREMTexture = true;
	cubeUVRenderTarget.scissorTest = true;
	return cubeUVRenderTarget;

}
```
</details>

### `_setViewport(target: any, x: any, y: any, width: any, height: any): void`

**Parameters:**

- **`target`** `any`
- **`x`** `any`
- **`y`** `any`
- **`width`** `any`
- **`height`** `any`

**Returns:** `void`

**Calls:**

- `target.viewport.set`
- `target.scissor.set`

<details><summary>Code</summary>

```typescript
function _setViewport( target, x, y, width, height ) {

	target.viewport.set( x, y, width, height );
	target.scissor.set( x, y, width, height );

}
```
</details>

### `_getMaterial(type: any): NodeMaterial`

**Parameters:**

- **`type`** `any`

**Returns:** `NodeMaterial`

<details><summary>Code</summary>

```typescript
function _getMaterial( type ) {

	const material = new NodeMaterial();
	material.depthTest = false;
	material.depthWrite = false;
	material.blending = NoBlending;
	material.name = `PMREM_${ type }`;

	return material;

}
```
</details>

### `_getBlurShader(lodMax: any, width: any, height: any): NodeMaterial`

**Parameters:**

- **`lodMax`** `any`
- **`width`** `any`
- **`height`** `any`

**Returns:** `NodeMaterial`

**Calls:**

- `uniformArray (from ../../../nodes/accessors/UniformArrayNode.js)`
- `new Array( MAX_SAMPLES ).fill`
- `uniform (from ../../../nodes/core/UniformNode.js)`
- `float (from ../../../nodes/tsl/TSLBase.js)`
- `texture (from ../../../nodes/accessors/TextureNode.js)`
- `_getMaterial`
- `blur (from ../../../nodes/pmrem/PMREMUtils.js)`
- `latitudinal.equal`
- `_uniformsMap.set`

<details><summary>Code</summary>

```typescript
function _getBlurShader( lodMax, width, height ) {

	const weights = uniformArray( new Array( MAX_SAMPLES ).fill( 0 ) );
	const poleAxis = uniform( new Vector3( 0, 1, 0 ) );
	const dTheta = uniform( 0 );
	const n = float( MAX_SAMPLES );
	const latitudinal = uniform( 0 ); // false, bool
	const samples = uniform( 1 ); // int
	const envMap = texture( null );
	const mipInt = uniform( 0 ); // int
	const CUBEUV_TEXEL_WIDTH = float( 1 / width );
	const CUBEUV_TEXEL_HEIGHT = float( 1 / height );
	const CUBEUV_MAX_MIP = float( lodMax );

	const materialUniforms = {
		n,
		latitudinal,
		weights,
		poleAxis,
		outputDirection: _outputDirection,
		dTheta,
		samples,
		envMap,
		mipInt,
		CUBEUV_TEXEL_WIDTH,
		CUBEUV_TEXEL_HEIGHT,
		CUBEUV_MAX_MIP
	};

	const material = _getMaterial( 'blur' );
	material.fragmentNode = blur( { ...materialUniforms, latitudinal: latitudinal.equal( 1 ) } );

	_uniformsMap.set( material, materialUniforms );

	return material;

}
```
</details>

### `_getCubemapMaterial(envTexture: any): NodeMaterial`

**Parameters:**

- **`envTexture`** `any`

**Returns:** `NodeMaterial`

**Calls:**

- `_getMaterial`
- `cubeTexture (from ../../../nodes/accessors/CubeTextureNode.js)`

<details><summary>Code</summary>

```typescript
function _getCubemapMaterial( envTexture ) {

	const material = _getMaterial( 'cubemap' );
	material.fragmentNode = cubeTexture( envTexture, _outputDirection );

	return material;

}
```
</details>

### `_getEquirectMaterial(envTexture: any): NodeMaterial`

**Parameters:**

- **`envTexture`** `any`

**Returns:** `NodeMaterial`

**Calls:**

- `_getMaterial`
- `texture (from ../../../nodes/accessors/TextureNode.js)`
- `equirectUV (from ../../../nodes/utils/EquirectUV.js)`

<details><summary>Code</summary>

```typescript
function _getEquirectMaterial( envTexture ) {

	const material = _getMaterial( 'equirect' );
	material.fragmentNode = texture( envTexture, equirectUV( _outputDirection ), 0 );

	return material;

}
```
</details>


---

## Classes

### `PMREMGenerator`

<details><summary>Class Code</summary>

```ts
class PMREMGenerator {

	/**
	 * Constructs a new PMREM generator.
	 *
	 * @param {Renderer} renderer - The renderer.
	 */
	constructor( renderer ) {

		this._renderer = renderer;
		this._pingPongRenderTarget = null;

		this._lodMax = 0;
		this._cubeSize = 0;
		this._lodPlanes = [];
		this._sizeLods = [];
		this._sigmas = [];
		this._lodMeshes = [];

		this._blurMaterial = null;
		this._cubemapMaterial = null;
		this._equirectMaterial = null;
		this._backgroundBox = null;

	}

	get _hasInitialized() {

		return this._renderer.hasInitialized();

	}

	/**
	 * Generates a PMREM from a supplied Scene, which can be faster than using an
	 * image if networking bandwidth is low. Optional sigma specifies a blur radius
	 * in radians to be applied to the scene before PMREM generation. Optional near
	 * and far planes ensure the scene is rendered in its entirety.
	 *
	 * @param {Scene} scene - The scene to be captured.
	 * @param {number} [sigma=0] - The blur radius in radians.
	 * @param {number} [near=0.1] - The near plane distance.
	 * @param {number} [far=100] - The far plane distance.
	 * @param {Object} [options={}] - The configuration options.
	 * @param {number} [options.size=256] - The texture size of the PMREM.
	 * @param {Vector3} [options.renderTarget=origin] - The position of the internal cube camera that renders the scene.
	 * @param {?RenderTarget} [options.renderTarget=null] - The render target to use.
	 * @return {RenderTarget} The resulting PMREM.
	 * @see {@link PMREMGenerator#fromSceneAsync}
	 */
	fromScene( scene, sigma = 0, near = 0.1, far = 100, options = {} ) {

		const {
			size = 256,
			position = _origin,
			renderTarget = null,
		} = options;

		this._setSize( size );

		if ( this._hasInitialized === false ) {

			console.warn( 'THREE.PMREMGenerator: .fromScene() called before the backend is initialized. Try using .fromSceneAsync() instead.' );

			const cubeUVRenderTarget = renderTarget || this._allocateTarget();

			options.renderTarget = cubeUVRenderTarget;

			this.fromSceneAsync( scene, sigma, near, far, options );

			return cubeUVRenderTarget;

		}

		_oldTarget = this._renderer.getRenderTarget();
		_oldActiveCubeFace = this._renderer.getActiveCubeFace();
		_oldActiveMipmapLevel = this._renderer.getActiveMipmapLevel();

		const cubeUVRenderTarget = renderTarget || this._allocateTarget();
		cubeUVRenderTarget.depthBuffer = true;

		this._init( cubeUVRenderTarget );

		this._sceneToCubeUV( scene, near, far, cubeUVRenderTarget, position );

		if ( sigma > 0 ) {

			this._blur( cubeUVRenderTarget, 0, 0, sigma );

		}

		this._applyPMREM( cubeUVRenderTarget );

		this._cleanup( cubeUVRenderTarget );

		return cubeUVRenderTarget;

	}

	/**
	 * Generates a PMREM from a supplied Scene, which can be faster than using an
	 * image if networking bandwidth is low. Optional sigma specifies a blur radius
	 * in radians to be applied to the scene before PMREM generation. Optional near
	 * and far planes ensure the scene is rendered in its entirety (the cubeCamera
	 * is placed at the origin).
	 *
	 * @param {Scene} scene - The scene to be captured.
	 * @param {number} [sigma=0] - The blur radius in radians.
	 * @param {number} [near=0.1] - The near plane distance.
	 * @param {number} [far=100] - The far plane distance.
	 * @param {Object} [options={}] - The configuration options.
	 * @param {number} [options.size=256] - The texture size of the PMREM.
	 * @param {Vector3} [options.position=origin] - The position of the internal cube camera that renders the scene.
	 * @param {?RenderTarget} [options.renderTarget=null] - The render target to use.
	 * @return {Promise<RenderTarget>} A Promise that resolve with the PMREM when the generation has been finished.
	 * @see {@link PMREMGenerator#fromScene}
	 */
	async fromSceneAsync( scene, sigma = 0, near = 0.1, far = 100, options = {} ) {

		if ( this._hasInitialized === false ) await this._renderer.init();

		return this.fromScene( scene, sigma, near, far, options );

	}

	/**
	 * Generates a PMREM from an equirectangular texture, which can be either LDR
	 * or HDR. The ideal input image size is 1k (1024 x 512),
	 * as this matches best with the 256 x 256 cubemap output.
	 *
	 * @param {Texture} equirectangular - The equirectangular texture to be converted.
	 * @param {?RenderTarget} [renderTarget=null] - The render target to use.
	 * @return {RenderTarget} The resulting PMREM.
	 * @see {@link PMREMGenerator#fromEquirectangularAsync}
	 */
	fromEquirectangular( equirectangular, renderTarget = null ) {

		if ( this._hasInitialized === false ) {

			console.warn( 'THREE.PMREMGenerator: .fromEquirectangular() called before the backend is initialized. Try using .fromEquirectangularAsync() instead.' );

			this._setSizeFromTexture( equirectangular );

			const cubeUVRenderTarget = renderTarget || this._allocateTarget();

			this.fromEquirectangularAsync( equirectangular, cubeUVRenderTarget );

			return cubeUVRenderTarget;

		}

		return this._fromTexture( equirectangular, renderTarget );

	}

	/**
	 * Generates a PMREM from an equirectangular texture, which can be either LDR
	 * or HDR. The ideal input image size is 1k (1024 x 512),
	 * as this matches best with the 256 x 256 cubemap output.
	 *
	 * @param {Texture} equirectangular - The equirectangular texture to be converted.
	 * @param {?RenderTarget} [renderTarget=null] - The render target to use.
	 * @return {Promise<RenderTarget>} The resulting PMREM.
	 * @see {@link PMREMGenerator#fromEquirectangular}
	 */
	async fromEquirectangularAsync( equirectangular, renderTarget = null ) {

		if ( this._hasInitialized === false ) await this._renderer.init();

		return this._fromTexture( equirectangular, renderTarget );

	}

	/**
	 * Generates a PMREM from an cubemap texture, which can be either LDR
	 * or HDR. The ideal input cube size is 256 x 256,
	 * as this matches best with the 256 x 256 cubemap output.
	 *
	 * @param {Texture} cubemap - The cubemap texture to be converted.
	 * @param {?RenderTarget} [renderTarget=null] - The render target to use.
	 * @return {RenderTarget} The resulting PMREM.
	 * @see {@link PMREMGenerator#fromCubemapAsync}
	 */
	fromCubemap( cubemap, renderTarget = null ) {

		if ( this._hasInitialized === false ) {

			console.warn( 'THREE.PMREMGenerator: .fromCubemap() called before the backend is initialized. Try using .fromCubemapAsync() instead.' );

			this._setSizeFromTexture( cubemap );

			const cubeUVRenderTarget = renderTarget || this._allocateTarget();

			this.fromCubemapAsync( cubemap, renderTarget );

			return cubeUVRenderTarget;

		}

		return this._fromTexture( cubemap, renderTarget );

	}

	/**
	 * Generates a PMREM from an cubemap texture, which can be either LDR
	 * or HDR. The ideal input cube size is 256 x 256,
	 * with the 256 x 256 cubemap output.
	 *
	 * @param {Texture} cubemap - The cubemap texture to be converted.
	 * @param {?RenderTarget} [renderTarget=null] - The render target to use.
	 * @return {Promise<RenderTarget>} The resulting PMREM.
	 * @see {@link PMREMGenerator#fromCubemap}
	 */
	async fromCubemapAsync( cubemap, renderTarget = null ) {

		if ( this._hasInitialized === false ) await this._renderer.init();

		return this._fromTexture( cubemap, renderTarget );

	}

	/**
	 * Pre-compiles the cubemap shader. You can get faster start-up by invoking this method during
	 * your texture's network fetch for increased concurrency.
	 *
	 * @returns {Promise}
	 */
	async compileCubemapShader() {

		if ( this._cubemapMaterial === null ) {

			this._cubemapMaterial = _getCubemapMaterial();
			await this._compileMaterial( this._cubemapMaterial );

		}

	}

	/**
	 * Pre-compiles the equirectangular shader. You can get faster start-up by invoking this method during
	 * your texture's network fetch for increased concurrency.
	 *
	 * @returns {Promise}
	 */
	async compileEquirectangularShader() {

		if ( this._equirectMaterial === null ) {

			this._equirectMaterial = _getEquirectMaterial();
			await this._compileMaterial( this._equirectMaterial );

		}

	}

	/**
	 * Disposes of the PMREMGenerator's internal memory. Note that PMREMGenerator is a static class,
	 * so you should not need more than one PMREMGenerator object. If you do, calling dispose() on
	 * one of them will cause any others to also become unusable.
	 */
	dispose() {

		this._dispose();

		if ( this._cubemapMaterial !== null ) this._cubemapMaterial.dispose();
		if ( this._equirectMaterial !== null ) this._equirectMaterial.dispose();
		if ( this._backgroundBox !== null ) {

			this._backgroundBox.geometry.dispose();
			this._backgroundBox.material.dispose();

		}

	}

	// private interface

	_setSizeFromTexture( texture ) {

		if ( texture.mapping === CubeReflectionMapping || texture.mapping === CubeRefractionMapping ) {

			this._setSize( texture.image.length === 0 ? 16 : ( texture.image[ 0 ].width || texture.image[ 0 ].image.width ) );

		} else { // Equirectangular

			this._setSize( texture.image.width / 4 );

		}

	}

	_setSize( cubeSize ) {

		this._lodMax = Math.floor( Math.log2( cubeSize ) );
		this._cubeSize = Math.pow( 2, this._lodMax );

	}

	_dispose() {

		if ( this._blurMaterial !== null ) this._blurMaterial.dispose();

		if ( this._pingPongRenderTarget !== null ) this._pingPongRenderTarget.dispose();

		for ( let i = 0; i < this._lodPlanes.length; i ++ ) {

			this._lodPlanes[ i ].dispose();

		}

	}

	_cleanup( outputTarget ) {

		this._renderer.setRenderTarget( _oldTarget, _oldActiveCubeFace, _oldActiveMipmapLevel );
		outputTarget.scissorTest = false;
		_setViewport( outputTarget, 0, 0, outputTarget.width, outputTarget.height );

	}

	_fromTexture( texture, renderTarget ) {

		this._setSizeFromTexture( texture );

		_oldTarget = this._renderer.getRenderTarget();
		_oldActiveCubeFace = this._renderer.getActiveCubeFace();
		_oldActiveMipmapLevel = this._renderer.getActiveMipmapLevel();

		const cubeUVRenderTarget = renderTarget || this._allocateTarget();
		this._init( cubeUVRenderTarget );
		this._textureToCubeUV( texture, cubeUVRenderTarget );
		this._applyPMREM( cubeUVRenderTarget );
		this._cleanup( cubeUVRenderTarget );

		return cubeUVRenderTarget;

	}

	_allocateTarget() {

		const width = 3 * Math.max( this._cubeSize, 16 * 7 );
		const height = 4 * this._cubeSize;

		const cubeUVRenderTarget = _createRenderTarget( width, height );

		return cubeUVRenderTarget;

	}

	_init( renderTarget ) {

		if ( this._pingPongRenderTarget === null || this._pingPongRenderTarget.width !== renderTarget.width || this._pingPongRenderTarget.height !== renderTarget.height ) {

			if ( this._pingPongRenderTarget !== null ) {

				this._dispose();

			}

			this._pingPongRenderTarget = _createRenderTarget( renderTarget.width, renderTarget.height );

			const { _lodMax } = this;
			( { sizeLods: this._sizeLods, lodPlanes: this._lodPlanes, sigmas: this._sigmas, lodMeshes: this._lodMeshes } = _createPlanes( _lodMax ) );

			this._blurMaterial = _getBlurShader( _lodMax, renderTarget.width, renderTarget.height );

		}

	}

	async _compileMaterial( material ) {

		const tmpMesh = new Mesh( this._lodPlanes[ 0 ], material );
		await this._renderer.compile( tmpMesh, _flatCamera );

	}

	_sceneToCubeUV( scene, near, far, cubeUVRenderTarget, position ) {

		const cubeCamera = _cubeCamera;
		cubeCamera.near = near;
		cubeCamera.far = far;

		// px, py, pz, nx, ny, nz
		const upSign = [ 1, 1, 1, 1, - 1, 1 ];
		const forwardSign = [ 1, - 1, 1, - 1, 1, - 1 ];

		const renderer = this._renderer;

		const originalAutoClear = renderer.autoClear;

		renderer.getClearColor( _clearColor );

		renderer.autoClear = false;

		let backgroundBox = this._backgroundBox;

		if ( backgroundBox === null ) {

			const backgroundMaterial = new MeshBasicMaterial( {
				name: 'PMREM.Background',
				side: BackSide,
				depthWrite: false,
				depthTest: false
			} );

			backgroundBox = new Mesh( new BoxGeometry(), backgroundMaterial );

		}

		let useSolidColor = false;
		const background = scene.background;

		if ( background ) {

			if ( background.isColor ) {

				backgroundBox.material.color.copy( background );
				scene.background = null;
				useSolidColor = true;

			}

		} else {

			backgroundBox.material.color.copy( _clearColor );
			useSolidColor = true;

		}

		renderer.setRenderTarget( cubeUVRenderTarget );

		renderer.clear();

		if ( useSolidColor ) {

			renderer.render( backgroundBox, cubeCamera );

		}

		for ( let i = 0; i < 6; i ++ ) {

			const col = i % 3;

			if ( col === 0 ) {

				cubeCamera.up.set( 0, upSign[ i ], 0 );
				cubeCamera.position.set( position.x, position.y, position.z );
				cubeCamera.lookAt( position.x + forwardSign[ i ], position.y, position.z );

			} else if ( col === 1 ) {

				cubeCamera.up.set( 0, 0, upSign[ i ] );
				cubeCamera.position.set( position.x, position.y, position.z );
				cubeCamera.lookAt( position.x, position.y + forwardSign[ i ], position.z );


			} else {

				cubeCamera.up.set( 0, upSign[ i ], 0 );
				cubeCamera.position.set( position.x, position.y, position.z );
				cubeCamera.lookAt( position.x, position.y, position.z + forwardSign[ i ] );


			}

			const size = this._cubeSize;

			_setViewport( cubeUVRenderTarget, col * size, i > 2 ? size : 0, size, size );

			renderer.render( scene, cubeCamera );

		}

		renderer.autoClear = originalAutoClear;
		scene.background = background;

	}

	_textureToCubeUV( texture, cubeUVRenderTarget ) {

		const renderer = this._renderer;

		const isCubeTexture = ( texture.mapping === CubeReflectionMapping || texture.mapping === CubeRefractionMapping );

		if ( isCubeTexture ) {

			if ( this._cubemapMaterial === null ) {

				this._cubemapMaterial = _getCubemapMaterial( texture );

			}

		} else {

			if ( this._equirectMaterial === null ) {

				this._equirectMaterial = _getEquirectMaterial( texture );

			}

		}

		const material = isCubeTexture ? this._cubemapMaterial : this._equirectMaterial;
		material.fragmentNode.value = texture;

		const mesh = this._lodMeshes[ 0 ];
		mesh.material = material;

		const size = this._cubeSize;

		_setViewport( cubeUVRenderTarget, 0, 0, 3 * size, 2 * size );

		renderer.setRenderTarget( cubeUVRenderTarget );
		renderer.render( mesh, _flatCamera );

	}

	_applyPMREM( cubeUVRenderTarget ) {

		const renderer = this._renderer;
		const autoClear = renderer.autoClear;
		renderer.autoClear = false;
		const n = this._lodPlanes.length;

		for ( let i = 1; i < n; i ++ ) {

			const sigma = Math.sqrt( this._sigmas[ i ] * this._sigmas[ i ] - this._sigmas[ i - 1 ] * this._sigmas[ i - 1 ] );

			const poleAxis = _axisDirections[ ( n - i - 1 ) % _axisDirections.length ];

			this._blur( cubeUVRenderTarget, i - 1, i, sigma, poleAxis );

		}

		renderer.autoClear = autoClear;

	}

	/**
	 * This is a two-pass Gaussian blur for a cubemap. Normally this is done
	 * vertically and horizontally, but this breaks down on a cube. Here we apply
	 * the blur latitudinally (around the poles), and then longitudinally (towards
	 * the poles) to approximate the orthogonally-separable blur. It is least
	 * accurate at the poles, but still does a decent job.
	 *
	 * @private
	 * @param {RenderTarget} cubeUVRenderTarget - The cubemap render target.
	 * @param {number} lodIn - The input level-of-detail.
	 * @param {number} lodOut - The output level-of-detail.
	 * @param {number} sigma - The blur radius in radians.
	 * @param {Vector3} [poleAxis] - The pole axis.
	 */
	_blur( cubeUVRenderTarget, lodIn, lodOut, sigma, poleAxis ) {

		const pingPongRenderTarget = this._pingPongRenderTarget;

		this._halfBlur(
			cubeUVRenderTarget,
			pingPongRenderTarget,
			lodIn,
			lodOut,
			sigma,
			'latitudinal',
			poleAxis );

		this._halfBlur(
			pingPongRenderTarget,
			cubeUVRenderTarget,
			lodOut,
			lodOut,
			sigma,
			'longitudinal',
			poleAxis );

	}

	_halfBlur( targetIn, targetOut, lodIn, lodOut, sigmaRadians, direction, poleAxis ) {

		const renderer = this._renderer;
		const blurMaterial = this._blurMaterial;

		if ( direction !== 'latitudinal' && direction !== 'longitudinal' ) {

			console.error( 'blur direction must be either latitudinal or longitudinal!' );

		}

		// Number of standard deviations at which to cut off the discrete approximation.
		const STANDARD_DEVIATIONS = 3;

		const blurMesh = this._lodMeshes[ lodOut ];
		blurMesh.material = blurMaterial;

		const blurUniforms = _uniformsMap.get( blurMaterial );

		const pixels = this._sizeLods[ lodIn ] - 1;
		const radiansPerPixel = isFinite( sigmaRadians ) ? Math.PI / ( 2 * pixels ) : 2 * Math.PI / ( 2 * MAX_SAMPLES - 1 );
		const sigmaPixels = sigmaRadians / radiansPerPixel;
		const samples = isFinite( sigmaRadians ) ? 1 + Math.floor( STANDARD_DEVIATIONS * sigmaPixels ) : MAX_SAMPLES;

		if ( samples > MAX_SAMPLES ) {

			console.warn( `sigmaRadians, ${
				sigmaRadians}, is too large and will clip, as it requested ${
				samples} samples when the maximum is set to ${MAX_SAMPLES}` );

		}

		const weights = [];
		let sum = 0;

		for ( let i = 0; i < MAX_SAMPLES; ++ i ) {

			const x = i / sigmaPixels;
			const weight = Math.exp( - x * x / 2 );
			weights.push( weight );

			if ( i === 0 ) {

				sum += weight;

			} else if ( i < samples ) {

				sum += 2 * weight;

			}

		}

		for ( let i = 0; i < weights.length; i ++ ) {

			weights[ i ] = weights[ i ] / sum;

		}

		targetIn.texture.frame = ( targetIn.texture.frame || 0 ) + 1;

		blurUniforms.envMap.value = targetIn.texture;
		blurUniforms.samples.value = samples;
		blurUniforms.weights.array = weights;
		blurUniforms.latitudinal.value = direction === 'latitudinal' ? 1 : 0;

		if ( poleAxis ) {

			blurUniforms.poleAxis.value = poleAxis;

		}

		const { _lodMax } = this;
		blurUniforms.dTheta.value = radiansPerPixel;
		blurUniforms.mipInt.value = _lodMax - lodIn;

		const outputSize = this._sizeLods[ lodOut ];
		const x = 3 * outputSize * ( lodOut > _lodMax - LOD_MIN ? lodOut - _lodMax + LOD_MIN : 0 );
		const y = 4 * ( this._cubeSize - outputSize );

		_setViewport( targetOut, x, y, 3 * outputSize, 2 * outputSize );
		renderer.setRenderTarget( targetOut );
		renderer.render( blurMesh, _flatCamera );

	}

}
```
</details>

#### Methods

##### `fromScene(scene: Scene, sigma: number, near: number, far: number, options: { size?: number; renderTarget?: Vector3; }): RenderTarget`

<details><summary>Code</summary>

```ts
fromScene( scene, sigma = 0, near = 0.1, far = 100, options = {} ) {

		const {
			size = 256,
			position = _origin,
			renderTarget = null,
		} = options;

		this._setSize( size );

		if ( this._hasInitialized === false ) {

			console.warn( 'THREE.PMREMGenerator: .fromScene() called before the backend is initialized. Try using .fromSceneAsync() instead.' );

			const cubeUVRenderTarget = renderTarget || this._allocateTarget();

			options.renderTarget = cubeUVRenderTarget;

			this.fromSceneAsync( scene, sigma, near, far, options );

			return cubeUVRenderTarget;

		}

		_oldTarget = this._renderer.getRenderTarget();
		_oldActiveCubeFace = this._renderer.getActiveCubeFace();
		_oldActiveMipmapLevel = this._renderer.getActiveMipmapLevel();

		const cubeUVRenderTarget = renderTarget || this._allocateTarget();
		cubeUVRenderTarget.depthBuffer = true;

		this._init( cubeUVRenderTarget );

		this._sceneToCubeUV( scene, near, far, cubeUVRenderTarget, position );

		if ( sigma > 0 ) {

			this._blur( cubeUVRenderTarget, 0, 0, sigma );

		}

		this._applyPMREM( cubeUVRenderTarget );

		this._cleanup( cubeUVRenderTarget );

		return cubeUVRenderTarget;

	}
```
</details>

##### `fromSceneAsync(scene: Scene, sigma: number, near: number, far: number, options: { size?: number; position?: Vector3; renderTarget?: RenderTarget; }): Promise<RenderTarget>`

<details><summary>Code</summary>

```ts
async fromSceneAsync( scene, sigma = 0, near = 0.1, far = 100, options = {} ) {

		if ( this._hasInitialized === false ) await this._renderer.init();

		return this.fromScene( scene, sigma, near, far, options );

	}
```
</details>

##### `fromEquirectangular(equirectangular: Texture, renderTarget: RenderTarget): RenderTarget`

<details><summary>Code</summary>

```ts
fromEquirectangular( equirectangular, renderTarget = null ) {

		if ( this._hasInitialized === false ) {

			console.warn( 'THREE.PMREMGenerator: .fromEquirectangular() called before the backend is initialized. Try using .fromEquirectangularAsync() instead.' );

			this._setSizeFromTexture( equirectangular );

			const cubeUVRenderTarget = renderTarget || this._allocateTarget();

			this.fromEquirectangularAsync( equirectangular, cubeUVRenderTarget );

			return cubeUVRenderTarget;

		}

		return this._fromTexture( equirectangular, renderTarget );

	}
```
</details>

##### `fromEquirectangularAsync(equirectangular: Texture, renderTarget: RenderTarget): Promise<RenderTarget>`

<details><summary>Code</summary>

```ts
async fromEquirectangularAsync( equirectangular, renderTarget = null ) {

		if ( this._hasInitialized === false ) await this._renderer.init();

		return this._fromTexture( equirectangular, renderTarget );

	}
```
</details>

##### `fromCubemap(cubemap: Texture, renderTarget: RenderTarget): RenderTarget`

<details><summary>Code</summary>

```ts
fromCubemap( cubemap, renderTarget = null ) {

		if ( this._hasInitialized === false ) {

			console.warn( 'THREE.PMREMGenerator: .fromCubemap() called before the backend is initialized. Try using .fromCubemapAsync() instead.' );

			this._setSizeFromTexture( cubemap );

			const cubeUVRenderTarget = renderTarget || this._allocateTarget();

			this.fromCubemapAsync( cubemap, renderTarget );

			return cubeUVRenderTarget;

		}

		return this._fromTexture( cubemap, renderTarget );

	}
```
</details>

##### `fromCubemapAsync(cubemap: Texture, renderTarget: RenderTarget): Promise<RenderTarget>`

<details><summary>Code</summary>

```ts
async fromCubemapAsync( cubemap, renderTarget = null ) {

		if ( this._hasInitialized === false ) await this._renderer.init();

		return this._fromTexture( cubemap, renderTarget );

	}
```
</details>

##### `compileCubemapShader(): Promise<any>`

<details><summary>Code</summary>

```ts
async compileCubemapShader() {

		if ( this._cubemapMaterial === null ) {

			this._cubemapMaterial = _getCubemapMaterial();
			await this._compileMaterial( this._cubemapMaterial );

		}

	}
```
</details>

##### `compileEquirectangularShader(): Promise<any>`

<details><summary>Code</summary>

```ts
async compileEquirectangularShader() {

		if ( this._equirectMaterial === null ) {

			this._equirectMaterial = _getEquirectMaterial();
			await this._compileMaterial( this._equirectMaterial );

		}

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this._dispose();

		if ( this._cubemapMaterial !== null ) this._cubemapMaterial.dispose();
		if ( this._equirectMaterial !== null ) this._equirectMaterial.dispose();
		if ( this._backgroundBox !== null ) {

			this._backgroundBox.geometry.dispose();
			this._backgroundBox.material.dispose();

		}

	}
```
</details>

##### `_setSizeFromTexture(texture: any): void`

<details><summary>Code</summary>

```ts
_setSizeFromTexture( texture ) {

		if ( texture.mapping === CubeReflectionMapping || texture.mapping === CubeRefractionMapping ) {

			this._setSize( texture.image.length === 0 ? 16 : ( texture.image[ 0 ].width || texture.image[ 0 ].image.width ) );

		} else { // Equirectangular

			this._setSize( texture.image.width / 4 );

		}

	}
```
</details>

##### `_setSize(cubeSize: any): void`

<details><summary>Code</summary>

```ts
_setSize( cubeSize ) {

		this._lodMax = Math.floor( Math.log2( cubeSize ) );
		this._cubeSize = Math.pow( 2, this._lodMax );

	}
```
</details>

##### `_dispose(): void`

<details><summary>Code</summary>

```ts
_dispose() {

		if ( this._blurMaterial !== null ) this._blurMaterial.dispose();

		if ( this._pingPongRenderTarget !== null ) this._pingPongRenderTarget.dispose();

		for ( let i = 0; i < this._lodPlanes.length; i ++ ) {

			this._lodPlanes[ i ].dispose();

		}

	}
```
</details>

##### `_cleanup(outputTarget: any): void`

<details><summary>Code</summary>

```ts
_cleanup( outputTarget ) {

		this._renderer.setRenderTarget( _oldTarget, _oldActiveCubeFace, _oldActiveMipmapLevel );
		outputTarget.scissorTest = false;
		_setViewport( outputTarget, 0, 0, outputTarget.width, outputTarget.height );

	}
```
</details>

##### `_fromTexture(texture: any, renderTarget: any): any`

<details><summary>Code</summary>

```ts
_fromTexture( texture, renderTarget ) {

		this._setSizeFromTexture( texture );

		_oldTarget = this._renderer.getRenderTarget();
		_oldActiveCubeFace = this._renderer.getActiveCubeFace();
		_oldActiveMipmapLevel = this._renderer.getActiveMipmapLevel();

		const cubeUVRenderTarget = renderTarget || this._allocateTarget();
		this._init( cubeUVRenderTarget );
		this._textureToCubeUV( texture, cubeUVRenderTarget );
		this._applyPMREM( cubeUVRenderTarget );
		this._cleanup( cubeUVRenderTarget );

		return cubeUVRenderTarget;

	}
```
</details>

##### `_allocateTarget(): RenderTarget`

<details><summary>Code</summary>

```ts
_allocateTarget() {

		const width = 3 * Math.max( this._cubeSize, 16 * 7 );
		const height = 4 * this._cubeSize;

		const cubeUVRenderTarget = _createRenderTarget( width, height );

		return cubeUVRenderTarget;

	}
```
</details>

##### `_init(renderTarget: any): void`

<details><summary>Code</summary>

```ts
_init( renderTarget ) {

		if ( this._pingPongRenderTarget === null || this._pingPongRenderTarget.width !== renderTarget.width || this._pingPongRenderTarget.height !== renderTarget.height ) {

			if ( this._pingPongRenderTarget !== null ) {

				this._dispose();

			}

			this._pingPongRenderTarget = _createRenderTarget( renderTarget.width, renderTarget.height );

			const { _lodMax } = this;
			( { sizeLods: this._sizeLods, lodPlanes: this._lodPlanes, sigmas: this._sigmas, lodMeshes: this._lodMeshes } = _createPlanes( _lodMax ) );

			this._blurMaterial = _getBlurShader( _lodMax, renderTarget.width, renderTarget.height );

		}

	}
```
</details>

##### `_compileMaterial(material: any): Promise<void>`

<details><summary>Code</summary>

```ts
async _compileMaterial( material ) {

		const tmpMesh = new Mesh( this._lodPlanes[ 0 ], material );
		await this._renderer.compile( tmpMesh, _flatCamera );

	}
```
</details>

##### `_sceneToCubeUV(scene: any, near: any, far: any, cubeUVRenderTarget: any, position: any): void`

<details><summary>Code</summary>

```ts
_sceneToCubeUV( scene, near, far, cubeUVRenderTarget, position ) {

		const cubeCamera = _cubeCamera;
		cubeCamera.near = near;
		cubeCamera.far = far;

		// px, py, pz, nx, ny, nz
		const upSign = [ 1, 1, 1, 1, - 1, 1 ];
		const forwardSign = [ 1, - 1, 1, - 1, 1, - 1 ];

		const renderer = this._renderer;

		const originalAutoClear = renderer.autoClear;

		renderer.getClearColor( _clearColor );

		renderer.autoClear = false;

		let backgroundBox = this._backgroundBox;

		if ( backgroundBox === null ) {

			const backgroundMaterial = new MeshBasicMaterial( {
				name: 'PMREM.Background',
				side: BackSide,
				depthWrite: false,
				depthTest: false
			} );

			backgroundBox = new Mesh( new BoxGeometry(), backgroundMaterial );

		}

		let useSolidColor = false;
		const background = scene.background;

		if ( background ) {

			if ( background.isColor ) {

				backgroundBox.material.color.copy( background );
				scene.background = null;
				useSolidColor = true;

			}

		} else {

			backgroundBox.material.color.copy( _clearColor );
			useSolidColor = true;

		}

		renderer.setRenderTarget( cubeUVRenderTarget );

		renderer.clear();

		if ( useSolidColor ) {

			renderer.render( backgroundBox, cubeCamera );

		}

		for ( let i = 0; i < 6; i ++ ) {

			const col = i % 3;

			if ( col === 0 ) {

				cubeCamera.up.set( 0, upSign[ i ], 0 );
				cubeCamera.position.set( position.x, position.y, position.z );
				cubeCamera.lookAt( position.x + forwardSign[ i ], position.y, position.z );

			} else if ( col === 1 ) {

				cubeCamera.up.set( 0, 0, upSign[ i ] );
				cubeCamera.position.set( position.x, position.y, position.z );
				cubeCamera.lookAt( position.x, position.y + forwardSign[ i ], position.z );


			} else {

				cubeCamera.up.set( 0, upSign[ i ], 0 );
				cubeCamera.position.set( position.x, position.y, position.z );
				cubeCamera.lookAt( position.x, position.y, position.z + forwardSign[ i ] );


			}

			const size = this._cubeSize;

			_setViewport( cubeUVRenderTarget, col * size, i > 2 ? size : 0, size, size );

			renderer.render( scene, cubeCamera );

		}

		renderer.autoClear = originalAutoClear;
		scene.background = background;

	}
```
</details>

##### `_textureToCubeUV(texture: any, cubeUVRenderTarget: any): void`

<details><summary>Code</summary>

```ts
_textureToCubeUV( texture, cubeUVRenderTarget ) {

		const renderer = this._renderer;

		const isCubeTexture = ( texture.mapping === CubeReflectionMapping || texture.mapping === CubeRefractionMapping );

		if ( isCubeTexture ) {

			if ( this._cubemapMaterial === null ) {

				this._cubemapMaterial = _getCubemapMaterial( texture );

			}

		} else {

			if ( this._equirectMaterial === null ) {

				this._equirectMaterial = _getEquirectMaterial( texture );

			}

		}

		const material = isCubeTexture ? this._cubemapMaterial : this._equirectMaterial;
		material.fragmentNode.value = texture;

		const mesh = this._lodMeshes[ 0 ];
		mesh.material = material;

		const size = this._cubeSize;

		_setViewport( cubeUVRenderTarget, 0, 0, 3 * size, 2 * size );

		renderer.setRenderTarget( cubeUVRenderTarget );
		renderer.render( mesh, _flatCamera );

	}
```
</details>

##### `_applyPMREM(cubeUVRenderTarget: any): void`

<details><summary>Code</summary>

```ts
_applyPMREM( cubeUVRenderTarget ) {

		const renderer = this._renderer;
		const autoClear = renderer.autoClear;
		renderer.autoClear = false;
		const n = this._lodPlanes.length;

		for ( let i = 1; i < n; i ++ ) {

			const sigma = Math.sqrt( this._sigmas[ i ] * this._sigmas[ i ] - this._sigmas[ i - 1 ] * this._sigmas[ i - 1 ] );

			const poleAxis = _axisDirections[ ( n - i - 1 ) % _axisDirections.length ];

			this._blur( cubeUVRenderTarget, i - 1, i, sigma, poleAxis );

		}

		renderer.autoClear = autoClear;

	}
```
</details>

##### `_blur(cubeUVRenderTarget: RenderTarget, lodIn: number, lodOut: number, sigma: number, poleAxis: Vector3): void`

<details><summary>Code</summary>

```ts
_blur( cubeUVRenderTarget, lodIn, lodOut, sigma, poleAxis ) {

		const pingPongRenderTarget = this._pingPongRenderTarget;

		this._halfBlur(
			cubeUVRenderTarget,
			pingPongRenderTarget,
			lodIn,
			lodOut,
			sigma,
			'latitudinal',
			poleAxis );

		this._halfBlur(
			pingPongRenderTarget,
			cubeUVRenderTarget,
			lodOut,
			lodOut,
			sigma,
			'longitudinal',
			poleAxis );

	}
```
</details>

##### `_halfBlur(targetIn: any, targetOut: any, lodIn: any, lodOut: any, sigmaRadians: any, direction: any, poleAxis: any): void`

<details><summary>Code</summary>

```ts
_halfBlur( targetIn, targetOut, lodIn, lodOut, sigmaRadians, direction, poleAxis ) {

		const renderer = this._renderer;
		const blurMaterial = this._blurMaterial;

		if ( direction !== 'latitudinal' && direction !== 'longitudinal' ) {

			console.error( 'blur direction must be either latitudinal or longitudinal!' );

		}

		// Number of standard deviations at which to cut off the discrete approximation.
		const STANDARD_DEVIATIONS = 3;

		const blurMesh = this._lodMeshes[ lodOut ];
		blurMesh.material = blurMaterial;

		const blurUniforms = _uniformsMap.get( blurMaterial );

		const pixels = this._sizeLods[ lodIn ] - 1;
		const radiansPerPixel = isFinite( sigmaRadians ) ? Math.PI / ( 2 * pixels ) : 2 * Math.PI / ( 2 * MAX_SAMPLES - 1 );
		const sigmaPixels = sigmaRadians / radiansPerPixel;
		const samples = isFinite( sigmaRadians ) ? 1 + Math.floor( STANDARD_DEVIATIONS * sigmaPixels ) : MAX_SAMPLES;

		if ( samples > MAX_SAMPLES ) {

			console.warn( `sigmaRadians, ${
				sigmaRadians}, is too large and will clip, as it requested ${
				samples} samples when the maximum is set to ${MAX_SAMPLES}` );

		}

		const weights = [];
		let sum = 0;

		for ( let i = 0; i < MAX_SAMPLES; ++ i ) {

			const x = i / sigmaPixels;
			const weight = Math.exp( - x * x / 2 );
			weights.push( weight );

			if ( i === 0 ) {

				sum += weight;

			} else if ( i < samples ) {

				sum += 2 * weight;

			}

		}

		for ( let i = 0; i < weights.length; i ++ ) {

			weights[ i ] = weights[ i ] / sum;

		}

		targetIn.texture.frame = ( targetIn.texture.frame || 0 ) + 1;

		blurUniforms.envMap.value = targetIn.texture;
		blurUniforms.samples.value = samples;
		blurUniforms.weights.array = weights;
		blurUniforms.latitudinal.value = direction === 'latitudinal' ? 1 : 0;

		if ( poleAxis ) {

			blurUniforms.poleAxis.value = poleAxis;

		}

		const { _lodMax } = this;
		blurUniforms.dTheta.value = radiansPerPixel;
		blurUniforms.mipInt.value = _lodMax - lodIn;

		const outputSize = this._sizeLods[ lodOut ];
		const x = 3 * outputSize * ( lodOut > _lodMax - LOD_MIN ? lodOut - _lodMax + LOD_MIN : 0 );
		const y = 4 * ( this._cubeSize - outputSize );

		_setViewport( targetOut, x, y, 3 * outputSize, 2 * outputSize );
		renderer.setRenderTarget( targetOut );
		renderer.render( blurMesh, _flatCamera );

	}
```
</details>


---