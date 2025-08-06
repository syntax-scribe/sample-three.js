[⬅️ Back to Table of Contents](../../index.md)

# 📄 `PMREMGenerator.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 24 |
| 🧱 Classes | 1 |
| 📦 Imports | 21 |
| 📊 Variables & Constants | 85 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/extras/PMREMGenerator.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `CubeReflectionMapping` | `../constants.js` |
| `CubeRefractionMapping` | `../constants.js` |
| `CubeUVReflectionMapping` | `../constants.js` |
| `LinearFilter` | `../constants.js` |
| `NoToneMapping` | `../constants.js` |
| `NoBlending` | `../constants.js` |
| `RGBAFormat` | `../constants.js` |
| `HalfFloatType` | `../constants.js` |
| `BackSide` | `../constants.js` |
| `LinearSRGBColorSpace` | `../constants.js` |
| `BufferAttribute` | `../core/BufferAttribute.js` |
| `BufferGeometry` | `../core/BufferGeometry.js` |
| `Mesh` | `../objects/Mesh.js` |
| `OrthographicCamera` | `../cameras/OrthographicCamera.js` |
| `PerspectiveCamera` | `../cameras/PerspectiveCamera.js` |
| `ShaderMaterial` | `../materials/ShaderMaterial.js` |
| `Vector3` | `../math/Vector3.js` |
| `Color` | `../math/Color.js` |
| `WebGLRenderTarget` | `../renderers/WebGLRenderTarget.js` |
| `MeshBasicMaterial` | `../materials/MeshBasicMaterial.js` |
| `BoxGeometry` | `../geometries/BoxGeometry.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `LOD_MIN` | `4` | let/var | `4` | ✗ |
| `EXTRA_LOD_SIGMA` | `number[]` | let/var | `[ 0.125, 0.215, 0.35, 0.446, 0.526, 0.582 ]` | ✗ |
| `MAX_SAMPLES` | `20` | let/var | `20` | ✗ |
| `_flatCamera` | `OrthographicCamera` | let/var | `new OrthographicCamera()` | ✗ |
| `_clearColor` | `Color` | let/var | `new Color()` | ✗ |
| `_oldTarget` | `any` | let/var | `null` | ✗ |
| `_oldActiveCubeFace` | `number` | let/var | `0` | ✗ |
| `_oldActiveMipmapLevel` | `number` | let/var | `0` | ✗ |
| `_oldXrEnabled` | `boolean` | let/var | `false` | ✗ |
| `PHI` | `number` | let/var | `( 1 + Math.sqrt( 5 ) ) / 2` | ✗ |
| `INV_PHI` | `number` | let/var | `1 / PHI` | ✗ |
| `_axisDirections` | `Vector3[]` | let/var | `[ /*@__PURE__*/ new Vector3( - PHI, INV_PHI, 0 ), /*@__PURE__*/ new Vector3( ...` | ✗ |
| `_origin` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `cubeUVRenderTarget` | `any` | let/var | `renderTarget \|\| this._allocateTargets()` | ✗ |
| `width` | `number` | let/var | `3 * Math.max( this._cubeSize, 16 * 7 )` | ✗ |
| `height` | `number` | let/var | `4 * this._cubeSize` | ✗ |
| `params` | `{ magFilter: number; minFilter: numbe...` | let/var | `{ magFilter: LinearFilter, minFilter: LinearFilter, generateMipmaps: false, t...` | ✗ |
| `tmpMesh` | `Mesh` | let/var | `new Mesh( this._lodPlanes[ 0 ], material )` | ✗ |
| `fov` | `90` | let/var | `90` | ✗ |
| `aspect` | `1` | let/var | `1` | ✗ |
| `cubeCamera` | `PerspectiveCamera` | let/var | `new PerspectiveCamera( fov, aspect, near, far )` | ✗ |
| `upSign` | `number[]` | let/var | `[ 1, - 1, 1, 1, 1, 1 ]` | ✗ |
| `forwardSign` | `number[]` | let/var | `[ 1, 1, 1, - 1, - 1, - 1 ]` | ✗ |
| `renderer` | `WebGLRenderer` | let/var | `this._renderer` | ✗ |
| `originalAutoClear` | `any` | let/var | `renderer.autoClear` | ✗ |
| `toneMapping` | `any` | let/var | `renderer.toneMapping` | ✗ |
| `backgroundMaterial` | `MeshBasicMaterial` | let/var | `new MeshBasicMaterial( { name: 'PMREM.Background', side: BackSide, depthWrite...` | ✗ |
| `backgroundBox` | `Mesh` | let/var | `new Mesh( new BoxGeometry(), backgroundMaterial )` | ✗ |
| `useSolidColor` | `boolean` | let/var | `false` | ✗ |
| `background` | `any` | let/var | `scene.background` | ✗ |
| `col` | `number` | let/var | `i % 3` | ✗ |
| `size` | `number` | let/var | `this._cubeSize` | ✗ |
| `renderer` | `WebGLRenderer` | let/var | `this._renderer` | ✗ |
| `isCubeTexture` | `boolean` | let/var | `( texture.mapping === CubeReflectionMapping \|\| texture.mapping === CubeRefr...` | ✗ |
| `material` | `ShaderMaterial` | let/var | `isCubeTexture ? this._cubemapMaterial : this._equirectMaterial` | ✗ |
| `mesh` | `Mesh` | let/var | `new Mesh( this._lodPlanes[ 0 ], material )` | ✗ |
| `uniforms` | `any` | let/var | `material.uniforms` | ✗ |
| `size` | `number` | let/var | `this._cubeSize` | ✗ |
| `renderer` | `WebGLRenderer` | let/var | `this._renderer` | ✗ |
| `autoClear` | `any` | let/var | `renderer.autoClear` | ✗ |
| `n` | `number` | let/var | `this._lodPlanes.length` | ✗ |
| `poleAxis` | `Vector3` | let/var | `_axisDirections[ ( n - i - 1 ) % _axisDirections.length ]` | ✗ |
| `pingPongRenderTarget` | `WebGLRenderTarget` | let/var | `this._pingPongRenderTarget` | ✗ |
| `renderer` | `WebGLRenderer` | let/var | `this._renderer` | ✗ |
| `blurMaterial` | `ShaderMaterial` | let/var | `this._blurMaterial` | ✗ |
| `STANDARD_DEVIATIONS` | `3` | let/var | `3` | ✗ |
| `blurMesh` | `Mesh` | let/var | `new Mesh( this._lodPlanes[ lodOut ], blurMaterial )` | ✗ |
| `blurUniforms` | `any` | let/var | `blurMaterial.uniforms` | ✗ |
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
| `fill` | `number[]` | let/var | `[ face, face, face, face, face, face ]` | ✗ |
| `planes` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `cubeUVRenderTarget` | `WebGLRenderTarget` | let/var | `new WebGLRenderTarget( width, height, params )` | ✗ |
| `weights` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( MAX_SAMPLES )` | ✗ |
| `poleAxis` | `Vector3` | let/var | `new Vector3( 0, 1, 0 )` | ✗ |
| `shaderMaterial` | `ShaderMaterial` | let/var | `new ShaderMaterial( { name: 'SphericalGaussianBlur', defines: { 'n': MAX_SAMP...` | ✗ |


---

## Functions

### `PMREMGenerator.fromScene(scene: Scene, sigma: number, near: number, far: number, options: { size?: number; renderTarget?: Vector3; }): WebGLRenderTarget`

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
	 * @return {WebGLRenderTarget} The resulting PMREM.
	 */
```

**Parameters:**

- **`scene`** `Scene`
- **`sigma`** `number`
- **`near`** `number`
- **`far`** `number`
- **`options`** `{ size?: number; renderTarget?: Vector3; }`

**Returns:** `WebGLRenderTarget`

**Calls:**

- `this._renderer.getRenderTarget`
- `this._renderer.getActiveCubeFace`
- `this._renderer.getActiveMipmapLevel`
- `this._setSize`
- `this._allocateTargets`
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
		} = options;

		_oldTarget = this._renderer.getRenderTarget();
		_oldActiveCubeFace = this._renderer.getActiveCubeFace();
		_oldActiveMipmapLevel = this._renderer.getActiveMipmapLevel();
		_oldXrEnabled = this._renderer.xr.enabled;

		this._renderer.xr.enabled = false;

		this._setSize( size );

		const cubeUVRenderTarget = this._allocateTargets();
		cubeUVRenderTarget.depthBuffer = true;

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

### `PMREMGenerator.fromEquirectangular(equirectangular: Texture, renderTarget: WebGLRenderTarget): WebGLRenderTarget`

**JSDoc:**
```typescript
/**
	 * Generates a PMREM from an equirectangular texture, which can be either LDR
	 * or HDR. The ideal input image size is 1k (1024 x 512),
	 * as this matches best with the 256 x 256 cubemap output.
	 *
	 * @param {Texture} equirectangular - The equirectangular texture to be converted.
	 * @param {?WebGLRenderTarget} [renderTarget=null] - The render target to use.
	 * @return {WebGLRenderTarget} The resulting PMREM.
	 */
```

**Parameters:**

- **`equirectangular`** `Texture`
- **`renderTarget`** `WebGLRenderTarget`

**Returns:** `WebGLRenderTarget`

**Calls:**

- `this._fromTexture`

<details><summary>Code</summary>

```typescript
fromEquirectangular( equirectangular, renderTarget = null ) {

		return this._fromTexture( equirectangular, renderTarget );

	}
```
</details>

### `PMREMGenerator.fromCubemap(cubemap: Texture, renderTarget: WebGLRenderTarget): WebGLRenderTarget`

**JSDoc:**
```typescript
/**
	 * Generates a PMREM from an cubemap texture, which can be either LDR
	 * or HDR. The ideal input cube size is 256 x 256,
	 * as this matches best with the 256 x 256 cubemap output.
	 *
	 * @param {Texture} cubemap - The cubemap texture to be converted.
	 * @param {?WebGLRenderTarget} [renderTarget=null] - The render target to use.
	 * @return {WebGLRenderTarget} The resulting PMREM.
	 */
```

**Parameters:**

- **`cubemap`** `Texture`
- **`renderTarget`** `WebGLRenderTarget`

**Returns:** `WebGLRenderTarget`

**Calls:**

- `this._fromTexture`

<details><summary>Code</summary>

```typescript
fromCubemap( cubemap, renderTarget = null ) {

		return this._fromTexture( cubemap, renderTarget );

	}
```
</details>

### `PMREMGenerator.compileCubemapShader(): void`

**JSDoc:**
```typescript
/**
	 * Pre-compiles the cubemap shader. You can get faster start-up by invoking this method during
	 * your texture's network fetch for increased concurrency.
	 */
```

**Returns:** `void`

**Calls:**

- `_getCubemapMaterial`
- `this._compileMaterial`

<details><summary>Code</summary>

```typescript
compileCubemapShader() {

		if ( this._cubemapMaterial === null ) {

			this._cubemapMaterial = _getCubemapMaterial();
			this._compileMaterial( this._cubemapMaterial );

		}

	}
```
</details>

### `PMREMGenerator.compileEquirectangularShader(): void`

**JSDoc:**
```typescript
/**
	 * Pre-compiles the equirectangular shader. You can get faster start-up by invoking this method during
	 * your texture's network fetch for increased concurrency.
	 */
```

**Returns:** `void`

**Calls:**

- `_getEquirectMaterial`
- `this._compileMaterial`

<details><summary>Code</summary>

```typescript
compileEquirectangularShader() {

		if ( this._equirectMaterial === null ) {

			this._equirectMaterial = _getEquirectMaterial();
			this._compileMaterial( this._equirectMaterial );

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

<details><summary>Code</summary>

```typescript
dispose() {

		this._dispose();

		if ( this._cubemapMaterial !== null ) this._cubemapMaterial.dispose();
		if ( this._equirectMaterial !== null ) this._equirectMaterial.dispose();

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
		this._renderer.xr.enabled = _oldXrEnabled;

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

- `this._setSize`
- `this._renderer.getRenderTarget`
- `this._renderer.getActiveCubeFace`
- `this._renderer.getActiveMipmapLevel`
- `this._allocateTargets`
- `this._textureToCubeUV`
- `this._applyPMREM`
- `this._cleanup`

<details><summary>Code</summary>

```typescript
_fromTexture( texture, renderTarget ) {

		if ( texture.mapping === CubeReflectionMapping || texture.mapping === CubeRefractionMapping ) {

			this._setSize( texture.image.length === 0 ? 16 : ( texture.image[ 0 ].width || texture.image[ 0 ].image.width ) );

		} else { // Equirectangular

			this._setSize( texture.image.width / 4 );

		}

		_oldTarget = this._renderer.getRenderTarget();
		_oldActiveCubeFace = this._renderer.getActiveCubeFace();
		_oldActiveMipmapLevel = this._renderer.getActiveMipmapLevel();
		_oldXrEnabled = this._renderer.xr.enabled;

		this._renderer.xr.enabled = false;

		const cubeUVRenderTarget = renderTarget || this._allocateTargets();
		this._textureToCubeUV( texture, cubeUVRenderTarget );
		this._applyPMREM( cubeUVRenderTarget );
		this._cleanup( cubeUVRenderTarget );

		return cubeUVRenderTarget;

	}
```
</details>

### `PMREMGenerator._allocateTargets(): WebGLRenderTarget`

**Returns:** `WebGLRenderTarget`

**Calls:**

- `Math.max`
- `_createRenderTarget`
- `this._dispose`
- `_createPlanes`
- `_getBlurShader`

<details><summary>Code</summary>

```typescript
_allocateTargets() {

		const width = 3 * Math.max( this._cubeSize, 16 * 7 );
		const height = 4 * this._cubeSize;

		const params = {
			magFilter: LinearFilter,
			minFilter: LinearFilter,
			generateMipmaps: false,
			type: HalfFloatType,
			format: RGBAFormat,
			colorSpace: LinearSRGBColorSpace,
			depthBuffer: false
		};

		const cubeUVRenderTarget = _createRenderTarget( width, height, params );

		if ( this._pingPongRenderTarget === null || this._pingPongRenderTarget.width !== width || this._pingPongRenderTarget.height !== height ) {

			if ( this._pingPongRenderTarget !== null ) {

				this._dispose();

			}

			this._pingPongRenderTarget = _createRenderTarget( width, height, params );

			const { _lodMax } = this;
			( { sizeLods: this._sizeLods, lodPlanes: this._lodPlanes, sigmas: this._sigmas } = _createPlanes( _lodMax ) );

			this._blurMaterial = _getBlurShader( _lodMax, width, height );

		}

		return cubeUVRenderTarget;

	}
```
</details>

### `PMREMGenerator._compileMaterial(material: any): void`

**Parameters:**

- **`material`** `any`

**Returns:** `void`

**Calls:**

- `this._renderer.compile`

<details><summary>Code</summary>

```typescript
_compileMaterial( material ) {

		const tmpMesh = new Mesh( this._lodPlanes[ 0 ], material );
		this._renderer.compile( tmpMesh, _flatCamera );

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
- `renderer.state.buffers.depth.getReversed`
- `renderer.setRenderTarget`
- `renderer.clearDepth`
- `backgroundMaterial.color.copy`
- `cubeCamera.up.set`
- `cubeCamera.position.set`
- `cubeCamera.lookAt`
- `_setViewport`
- `renderer.render`
- `backgroundBox.geometry.dispose`
- `backgroundBox.material.dispose`

**Internal Comments:**
```
// https://github.com/mrdoob/three.js/issues/31413#issuecomment-3095966812 (x2)
```

<details><summary>Code</summary>

```typescript
_sceneToCubeUV( scene, near, far, cubeUVRenderTarget, position ) {

		const fov = 90;
		const aspect = 1;
		const cubeCamera = new PerspectiveCamera( fov, aspect, near, far );
		const upSign = [ 1, - 1, 1, 1, 1, 1 ];
		const forwardSign = [ 1, 1, 1, - 1, - 1, - 1 ];
		const renderer = this._renderer;

		const originalAutoClear = renderer.autoClear;
		const toneMapping = renderer.toneMapping;
		renderer.getClearColor( _clearColor );

		renderer.toneMapping = NoToneMapping;
		renderer.autoClear = false;

		// https://github.com/mrdoob/three.js/issues/31413#issuecomment-3095966812
		const reversedDepthBuffer = renderer.state.buffers.depth.getReversed();

		if ( reversedDepthBuffer ) {

			renderer.setRenderTarget( cubeUVRenderTarget );
			renderer.clearDepth();
			renderer.setRenderTarget( null );

		}

		const backgroundMaterial = new MeshBasicMaterial( {
			name: 'PMREM.Background',
			side: BackSide,
			depthWrite: false,
			depthTest: false,
		} );

		const backgroundBox = new Mesh( new BoxGeometry(), backgroundMaterial );

		let useSolidColor = false;
		const background = scene.background;

		if ( background ) {

			if ( background.isColor ) {

				backgroundMaterial.color.copy( background );
				scene.background = null;
				useSolidColor = true;

			}

		} else {

			backgroundMaterial.color.copy( _clearColor );
			useSolidColor = true;

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

			renderer.setRenderTarget( cubeUVRenderTarget );

			if ( useSolidColor ) {

				renderer.render( backgroundBox, cubeCamera );

			}

			renderer.render( scene, cubeCamera );

		}

		backgroundBox.geometry.dispose();
		backgroundBox.material.dispose();

		renderer.toneMapping = toneMapping;
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

				this._cubemapMaterial = _getCubemapMaterial();

			}

			this._cubemapMaterial.uniforms.flipEnvMap.value = ( texture.isRenderTargetTexture === false ) ? - 1 : 1;

		} else {

			if ( this._equirectMaterial === null ) {

				this._equirectMaterial = _getEquirectMaterial();

			}

		}

		const material = isCubeTexture ? this._cubemapMaterial : this._equirectMaterial;
		const mesh = new Mesh( this._lodPlanes[ 0 ], material );

		const uniforms = material.uniforms;

		uniforms[ 'envMap' ].value = texture;

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

### `PMREMGenerator._blur(cubeUVRenderTarget: WebGLRenderTarget, lodIn: number, lodOut: number, sigma: number, poleAxis: Vector3): void`

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
	 * @param {WebGLRenderTarget} cubeUVRenderTarget
	 * @param {number} lodIn
	 * @param {number} lodOut
	 * @param {number} sigma
	 * @param {Vector3} [poleAxis]
	 */
```

**Parameters:**

- **`cubeUVRenderTarget`** `WebGLRenderTarget`
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

			console.error(
				'blur direction must be either latitudinal or longitudinal!' );

		}

		// Number of standard deviations at which to cut off the discrete approximation.
		const STANDARD_DEVIATIONS = 3;

		const blurMesh = new Mesh( this._lodPlanes[ lodOut ], blurMaterial );
		const blurUniforms = blurMaterial.uniforms;

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

		blurUniforms[ 'envMap' ].value = targetIn.texture;
		blurUniforms[ 'samples' ].value = samples;
		blurUniforms[ 'weights' ].value = weights;
		blurUniforms[ 'latitudinal' ].value = direction === 'latitudinal';

		if ( poleAxis ) {

			blurUniforms[ 'poleAxis' ].value = poleAxis;

		}

		const { _lodMax } = this;
		blurUniforms[ 'dTheta' ].value = radiansPerPixel;
		blurUniforms[ 'mipInt' ].value = _lodMax - lodIn;

		const outputSize = this._sizeLods[ lodOut ];
		const x = 3 * outputSize * ( lodOut > _lodMax - LOD_MIN ? lodOut - _lodMax + LOD_MIN : 0 );
		const y = 4 * ( this._cubeSize - outputSize );

		_setViewport( targetOut, x, y, 3 * outputSize, 2 * outputSize );
		renderer.setRenderTarget( targetOut );
		renderer.render( blurMesh, _flatCamera );

	}
```
</details>

### `_createPlanes(lodMax: any): { lodPlanes: BufferGeometry[]; sizeLods: number[]; sigmas: number[]; }`

**Parameters:**

- **`lodMax`** `any`

**Returns:** `{ lodPlanes: BufferGeometry[]; sizeLods: number[]; sigmas: number[]; }`

**Calls:**

- `Math.pow`
- `sizeLods.push`
- `sigmas.push`
- `position.set`
- `uv.set`
- `faceIndex.set`
- `planes.setAttribute`
- `lodPlanes.push`

<details><summary>Code</summary>

```typescript
function _createPlanes( lodMax ) {

	const lodPlanes = [];
	const sizeLods = [];
	const sigmas = [];

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
			position.set( coordinates, positionSize * vertices * face );
			uv.set( uv1, uvSize * vertices * face );
			const fill = [ face, face, face, face, face, face ];
			faceIndex.set( fill, faceIndexSize * vertices * face );

		}

		const planes = new BufferGeometry();
		planes.setAttribute( 'position', new BufferAttribute( position, positionSize ) );
		planes.setAttribute( 'uv', new BufferAttribute( uv, uvSize ) );
		planes.setAttribute( 'faceIndex', new BufferAttribute( faceIndex, faceIndexSize ) );
		lodPlanes.push( planes );

		if ( lod > LOD_MIN ) {

			lod --;

		}

	}

	return { lodPlanes, sizeLods, sigmas };

}
```
</details>

### `_createRenderTarget(width: any, height: any, params: any): WebGLRenderTarget`

**Parameters:**

- **`width`** `any`
- **`height`** `any`
- **`params`** `any`

**Returns:** `WebGLRenderTarget`

<details><summary>Code</summary>

```typescript
function _createRenderTarget( width, height, params ) {

	const cubeUVRenderTarget = new WebGLRenderTarget( width, height, params );
	cubeUVRenderTarget.texture.mapping = CubeUVReflectionMapping;
	cubeUVRenderTarget.texture.name = 'PMREM.cubeUv';
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

### `_getBlurShader(lodMax: any, width: any, height: any): ShaderMaterial`

**Parameters:**

- **`lodMax`** `any`
- **`width`** `any`
- **`height`** `any`

**Returns:** `ShaderMaterial`

**Calls:**

- `_getCommonVertexShader`

<details><summary>Code</summary>

```typescript
function _getBlurShader( lodMax, width, height ) {

	const weights = new Float32Array( MAX_SAMPLES );
	const poleAxis = new Vector3( 0, 1, 0 );
	const shaderMaterial = new ShaderMaterial( {

		name: 'SphericalGaussianBlur',

		defines: {
			'n': MAX_SAMPLES,
			'CUBEUV_TEXEL_WIDTH': 1.0 / width,
			'CUBEUV_TEXEL_HEIGHT': 1.0 / height,
			'CUBEUV_MAX_MIP': `${lodMax}.0`,
		},

		uniforms: {
			'envMap': { value: null },
			'samples': { value: 1 },
			'weights': { value: weights },
			'latitudinal': { value: false },
			'dTheta': { value: 0 },
			'mipInt': { value: 0 },
			'poleAxis': { value: poleAxis }
		},

		vertexShader: _getCommonVertexShader(),

		fragmentShader: /* glsl */`

			precision mediump float;
			precision mediump int;

			varying vec3 vOutputDirection;

			uniform sampler2D envMap;
			uniform int samples;
			uniform float weights[ n ];
			uniform bool latitudinal;
			uniform float dTheta;
			uniform float mipInt;
			uniform vec3 poleAxis;

			#define ENVMAP_TYPE_CUBE_UV
			#include <cube_uv_reflection_fragment>

			vec3 getSample( float theta, vec3 axis ) {

				float cosTheta = cos( theta );
				// Rodrigues' axis-angle rotation
				vec3 sampleDirection = vOutputDirection * cosTheta
					+ cross( axis, vOutputDirection ) * sin( theta )
					+ axis * dot( axis, vOutputDirection ) * ( 1.0 - cosTheta );

				return bilinearCubeUV( envMap, sampleDirection, mipInt );

			}

			void main() {

				vec3 axis = latitudinal ? poleAxis : cross( poleAxis, vOutputDirection );

				if ( all( equal( axis, vec3( 0.0 ) ) ) ) {

					axis = vec3( vOutputDirection.z, 0.0, - vOutputDirection.x );

				}

				axis = normalize( axis );

				gl_FragColor = vec4( 0.0, 0.0, 0.0, 1.0 );
				gl_FragColor.rgb += weights[ 0 ] * getSample( 0.0, axis );

				for ( int i = 1; i < n; i++ ) {

					if ( i >= samples ) {

						break;

					}

					float theta = dTheta * float( i );
					gl_FragColor.rgb += weights[ i ] * getSample( -1.0 * theta, axis );
					gl_FragColor.rgb += weights[ i ] * getSample( theta, axis );

				}

			}
		`,

		blending: NoBlending,
		depthTest: false,
		depthWrite: false

	} );

	return shaderMaterial;

}
```
</details>

### `_getEquirectMaterial(): ShaderMaterial`

**Returns:** `ShaderMaterial`

**Calls:**

- `_getCommonVertexShader`

<details><summary>Code</summary>

```typescript
function _getEquirectMaterial() {

	return new ShaderMaterial( {

		name: 'EquirectangularToCubeUV',

		uniforms: {
			'envMap': { value: null }
		},

		vertexShader: _getCommonVertexShader(),

		fragmentShader: /* glsl */`

			precision mediump float;
			precision mediump int;

			varying vec3 vOutputDirection;

			uniform sampler2D envMap;

			#include <common>

			void main() {

				vec3 outputDirection = normalize( vOutputDirection );
				vec2 uv = equirectUv( outputDirection );

				gl_FragColor = vec4( texture2D ( envMap, uv ).rgb, 1.0 );

			}
		`,

		blending: NoBlending,
		depthTest: false,
		depthWrite: false

	} );

}
```
</details>

### `_getCubemapMaterial(): ShaderMaterial`

**Returns:** `ShaderMaterial`

**Calls:**

- `_getCommonVertexShader`

<details><summary>Code</summary>

```typescript
function _getCubemapMaterial() {

	return new ShaderMaterial( {

		name: 'CubemapToCubeUV',

		uniforms: {
			'envMap': { value: null },
			'flipEnvMap': { value: - 1 }
		},

		vertexShader: _getCommonVertexShader(),

		fragmentShader: /* glsl */`

			precision mediump float;
			precision mediump int;

			uniform float flipEnvMap;

			varying vec3 vOutputDirection;

			uniform samplerCube envMap;

			void main() {

				gl_FragColor = textureCube( envMap, vec3( flipEnvMap * vOutputDirection.x, vOutputDirection.yz ) );

			}
		`,

		blending: NoBlending,
		depthTest: false,
		depthWrite: false

	} );

}
```
</details>

### `_getCommonVertexShader(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function _getCommonVertexShader() {

	return /* glsl */`

		precision mediump float;
		precision mediump int;

		attribute float faceIndex;

		varying vec3 vOutputDirection;

		// RH coordinate system; PMREM face-indexing convention
		vec3 getDirection( vec2 uv, float face ) {

			uv = 2.0 * uv - 1.0;

			vec3 direction = vec3( uv, 1.0 );

			if ( face == 0.0 ) {

				direction = direction.zyx; // ( 1, v, u ) pos x

			} else if ( face == 1.0 ) {

				direction = direction.xzy;
				direction.xz *= -1.0; // ( -u, 1, -v ) pos y

			} else if ( face == 2.0 ) {

				direction.x *= -1.0; // ( -u, v, 1 ) pos z

			} else if ( face == 3.0 ) {

				direction = direction.zyx;
				direction.xz *= -1.0; // ( -1, v, -u ) neg x

			} else if ( face == 4.0 ) {

				direction = direction.xzy;
				direction.xy *= -1.0; // ( -u, -1, v ) neg y

			} else if ( face == 5.0 ) {

				direction.z *= -1.0; // ( u, v, -1 ) neg z

			}

			return direction;

		}

		void main() {

			vOutputDirection = getDirection( uv, faceIndex );
			gl_Position = vec4( position, 1.0 );

		}
	`;

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
	 * @param {WebGLRenderer} renderer - The renderer.
	 */
	constructor( renderer ) {

		this._renderer = renderer;
		this._pingPongRenderTarget = null;

		this._lodMax = 0;
		this._cubeSize = 0;
		this._lodPlanes = [];
		this._sizeLods = [];
		this._sigmas = [];

		this._blurMaterial = null;
		this._cubemapMaterial = null;
		this._equirectMaterial = null;

		this._compileMaterial( this._blurMaterial );

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
	 * @return {WebGLRenderTarget} The resulting PMREM.
	 */
	fromScene( scene, sigma = 0, near = 0.1, far = 100, options = {} ) {

		const {
			size = 256,
			position = _origin,
		} = options;

		_oldTarget = this._renderer.getRenderTarget();
		_oldActiveCubeFace = this._renderer.getActiveCubeFace();
		_oldActiveMipmapLevel = this._renderer.getActiveMipmapLevel();
		_oldXrEnabled = this._renderer.xr.enabled;

		this._renderer.xr.enabled = false;

		this._setSize( size );

		const cubeUVRenderTarget = this._allocateTargets();
		cubeUVRenderTarget.depthBuffer = true;

		this._sceneToCubeUV( scene, near, far, cubeUVRenderTarget, position );

		if ( sigma > 0 ) {

			this._blur( cubeUVRenderTarget, 0, 0, sigma );

		}

		this._applyPMREM( cubeUVRenderTarget );
		this._cleanup( cubeUVRenderTarget );

		return cubeUVRenderTarget;

	}

	/**
	 * Generates a PMREM from an equirectangular texture, which can be either LDR
	 * or HDR. The ideal input image size is 1k (1024 x 512),
	 * as this matches best with the 256 x 256 cubemap output.
	 *
	 * @param {Texture} equirectangular - The equirectangular texture to be converted.
	 * @param {?WebGLRenderTarget} [renderTarget=null] - The render target to use.
	 * @return {WebGLRenderTarget} The resulting PMREM.
	 */
	fromEquirectangular( equirectangular, renderTarget = null ) {

		return this._fromTexture( equirectangular, renderTarget );

	}

	/**
	 * Generates a PMREM from an cubemap texture, which can be either LDR
	 * or HDR. The ideal input cube size is 256 x 256,
	 * as this matches best with the 256 x 256 cubemap output.
	 *
	 * @param {Texture} cubemap - The cubemap texture to be converted.
	 * @param {?WebGLRenderTarget} [renderTarget=null] - The render target to use.
	 * @return {WebGLRenderTarget} The resulting PMREM.
	 */
	fromCubemap( cubemap, renderTarget = null ) {

		return this._fromTexture( cubemap, renderTarget );

	}

	/**
	 * Pre-compiles the cubemap shader. You can get faster start-up by invoking this method during
	 * your texture's network fetch for increased concurrency.
	 */
	compileCubemapShader() {

		if ( this._cubemapMaterial === null ) {

			this._cubemapMaterial = _getCubemapMaterial();
			this._compileMaterial( this._cubemapMaterial );

		}

	}

	/**
	 * Pre-compiles the equirectangular shader. You can get faster start-up by invoking this method during
	 * your texture's network fetch for increased concurrency.
	 */
	compileEquirectangularShader() {

		if ( this._equirectMaterial === null ) {

			this._equirectMaterial = _getEquirectMaterial();
			this._compileMaterial( this._equirectMaterial );

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

	}

	// private interface

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
		this._renderer.xr.enabled = _oldXrEnabled;

		outputTarget.scissorTest = false;
		_setViewport( outputTarget, 0, 0, outputTarget.width, outputTarget.height );

	}

	_fromTexture( texture, renderTarget ) {

		if ( texture.mapping === CubeReflectionMapping || texture.mapping === CubeRefractionMapping ) {

			this._setSize( texture.image.length === 0 ? 16 : ( texture.image[ 0 ].width || texture.image[ 0 ].image.width ) );

		} else { // Equirectangular

			this._setSize( texture.image.width / 4 );

		}

		_oldTarget = this._renderer.getRenderTarget();
		_oldActiveCubeFace = this._renderer.getActiveCubeFace();
		_oldActiveMipmapLevel = this._renderer.getActiveMipmapLevel();
		_oldXrEnabled = this._renderer.xr.enabled;

		this._renderer.xr.enabled = false;

		const cubeUVRenderTarget = renderTarget || this._allocateTargets();
		this._textureToCubeUV( texture, cubeUVRenderTarget );
		this._applyPMREM( cubeUVRenderTarget );
		this._cleanup( cubeUVRenderTarget );

		return cubeUVRenderTarget;

	}

	_allocateTargets() {

		const width = 3 * Math.max( this._cubeSize, 16 * 7 );
		const height = 4 * this._cubeSize;

		const params = {
			magFilter: LinearFilter,
			minFilter: LinearFilter,
			generateMipmaps: false,
			type: HalfFloatType,
			format: RGBAFormat,
			colorSpace: LinearSRGBColorSpace,
			depthBuffer: false
		};

		const cubeUVRenderTarget = _createRenderTarget( width, height, params );

		if ( this._pingPongRenderTarget === null || this._pingPongRenderTarget.width !== width || this._pingPongRenderTarget.height !== height ) {

			if ( this._pingPongRenderTarget !== null ) {

				this._dispose();

			}

			this._pingPongRenderTarget = _createRenderTarget( width, height, params );

			const { _lodMax } = this;
			( { sizeLods: this._sizeLods, lodPlanes: this._lodPlanes, sigmas: this._sigmas } = _createPlanes( _lodMax ) );

			this._blurMaterial = _getBlurShader( _lodMax, width, height );

		}

		return cubeUVRenderTarget;

	}

	_compileMaterial( material ) {

		const tmpMesh = new Mesh( this._lodPlanes[ 0 ], material );
		this._renderer.compile( tmpMesh, _flatCamera );

	}

	_sceneToCubeUV( scene, near, far, cubeUVRenderTarget, position ) {

		const fov = 90;
		const aspect = 1;
		const cubeCamera = new PerspectiveCamera( fov, aspect, near, far );
		const upSign = [ 1, - 1, 1, 1, 1, 1 ];
		const forwardSign = [ 1, 1, 1, - 1, - 1, - 1 ];
		const renderer = this._renderer;

		const originalAutoClear = renderer.autoClear;
		const toneMapping = renderer.toneMapping;
		renderer.getClearColor( _clearColor );

		renderer.toneMapping = NoToneMapping;
		renderer.autoClear = false;

		// https://github.com/mrdoob/three.js/issues/31413#issuecomment-3095966812
		const reversedDepthBuffer = renderer.state.buffers.depth.getReversed();

		if ( reversedDepthBuffer ) {

			renderer.setRenderTarget( cubeUVRenderTarget );
			renderer.clearDepth();
			renderer.setRenderTarget( null );

		}

		const backgroundMaterial = new MeshBasicMaterial( {
			name: 'PMREM.Background',
			side: BackSide,
			depthWrite: false,
			depthTest: false,
		} );

		const backgroundBox = new Mesh( new BoxGeometry(), backgroundMaterial );

		let useSolidColor = false;
		const background = scene.background;

		if ( background ) {

			if ( background.isColor ) {

				backgroundMaterial.color.copy( background );
				scene.background = null;
				useSolidColor = true;

			}

		} else {

			backgroundMaterial.color.copy( _clearColor );
			useSolidColor = true;

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

			renderer.setRenderTarget( cubeUVRenderTarget );

			if ( useSolidColor ) {

				renderer.render( backgroundBox, cubeCamera );

			}

			renderer.render( scene, cubeCamera );

		}

		backgroundBox.geometry.dispose();
		backgroundBox.material.dispose();

		renderer.toneMapping = toneMapping;
		renderer.autoClear = originalAutoClear;
		scene.background = background;

	}

	_textureToCubeUV( texture, cubeUVRenderTarget ) {

		const renderer = this._renderer;

		const isCubeTexture = ( texture.mapping === CubeReflectionMapping || texture.mapping === CubeRefractionMapping );

		if ( isCubeTexture ) {

			if ( this._cubemapMaterial === null ) {

				this._cubemapMaterial = _getCubemapMaterial();

			}

			this._cubemapMaterial.uniforms.flipEnvMap.value = ( texture.isRenderTargetTexture === false ) ? - 1 : 1;

		} else {

			if ( this._equirectMaterial === null ) {

				this._equirectMaterial = _getEquirectMaterial();

			}

		}

		const material = isCubeTexture ? this._cubemapMaterial : this._equirectMaterial;
		const mesh = new Mesh( this._lodPlanes[ 0 ], material );

		const uniforms = material.uniforms;

		uniforms[ 'envMap' ].value = texture;

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
	 * @param {WebGLRenderTarget} cubeUVRenderTarget
	 * @param {number} lodIn
	 * @param {number} lodOut
	 * @param {number} sigma
	 * @param {Vector3} [poleAxis]
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

			console.error(
				'blur direction must be either latitudinal or longitudinal!' );

		}

		// Number of standard deviations at which to cut off the discrete approximation.
		const STANDARD_DEVIATIONS = 3;

		const blurMesh = new Mesh( this._lodPlanes[ lodOut ], blurMaterial );
		const blurUniforms = blurMaterial.uniforms;

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

		blurUniforms[ 'envMap' ].value = targetIn.texture;
		blurUniforms[ 'samples' ].value = samples;
		blurUniforms[ 'weights' ].value = weights;
		blurUniforms[ 'latitudinal' ].value = direction === 'latitudinal';

		if ( poleAxis ) {

			blurUniforms[ 'poleAxis' ].value = poleAxis;

		}

		const { _lodMax } = this;
		blurUniforms[ 'dTheta' ].value = radiansPerPixel;
		blurUniforms[ 'mipInt' ].value = _lodMax - lodIn;

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

##### `fromScene(scene: Scene, sigma: number, near: number, far: number, options: { size?: number; renderTarget?: Vector3; }): WebGLRenderTarget`

<details><summary>Code</summary>

```ts
fromScene( scene, sigma = 0, near = 0.1, far = 100, options = {} ) {

		const {
			size = 256,
			position = _origin,
		} = options;

		_oldTarget = this._renderer.getRenderTarget();
		_oldActiveCubeFace = this._renderer.getActiveCubeFace();
		_oldActiveMipmapLevel = this._renderer.getActiveMipmapLevel();
		_oldXrEnabled = this._renderer.xr.enabled;

		this._renderer.xr.enabled = false;

		this._setSize( size );

		const cubeUVRenderTarget = this._allocateTargets();
		cubeUVRenderTarget.depthBuffer = true;

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

##### `fromEquirectangular(equirectangular: Texture, renderTarget: WebGLRenderTarget): WebGLRenderTarget`

<details><summary>Code</summary>

```ts
fromEquirectangular( equirectangular, renderTarget = null ) {

		return this._fromTexture( equirectangular, renderTarget );

	}
```
</details>

##### `fromCubemap(cubemap: Texture, renderTarget: WebGLRenderTarget): WebGLRenderTarget`

<details><summary>Code</summary>

```ts
fromCubemap( cubemap, renderTarget = null ) {

		return this._fromTexture( cubemap, renderTarget );

	}
```
</details>

##### `compileCubemapShader(): void`

<details><summary>Code</summary>

```ts
compileCubemapShader() {

		if ( this._cubemapMaterial === null ) {

			this._cubemapMaterial = _getCubemapMaterial();
			this._compileMaterial( this._cubemapMaterial );

		}

	}
```
</details>

##### `compileEquirectangularShader(): void`

<details><summary>Code</summary>

```ts
compileEquirectangularShader() {

		if ( this._equirectMaterial === null ) {

			this._equirectMaterial = _getEquirectMaterial();
			this._compileMaterial( this._equirectMaterial );

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
		this._renderer.xr.enabled = _oldXrEnabled;

		outputTarget.scissorTest = false;
		_setViewport( outputTarget, 0, 0, outputTarget.width, outputTarget.height );

	}
```
</details>

##### `_fromTexture(texture: any, renderTarget: any): any`

<details><summary>Code</summary>

```ts
_fromTexture( texture, renderTarget ) {

		if ( texture.mapping === CubeReflectionMapping || texture.mapping === CubeRefractionMapping ) {

			this._setSize( texture.image.length === 0 ? 16 : ( texture.image[ 0 ].width || texture.image[ 0 ].image.width ) );

		} else { // Equirectangular

			this._setSize( texture.image.width / 4 );

		}

		_oldTarget = this._renderer.getRenderTarget();
		_oldActiveCubeFace = this._renderer.getActiveCubeFace();
		_oldActiveMipmapLevel = this._renderer.getActiveMipmapLevel();
		_oldXrEnabled = this._renderer.xr.enabled;

		this._renderer.xr.enabled = false;

		const cubeUVRenderTarget = renderTarget || this._allocateTargets();
		this._textureToCubeUV( texture, cubeUVRenderTarget );
		this._applyPMREM( cubeUVRenderTarget );
		this._cleanup( cubeUVRenderTarget );

		return cubeUVRenderTarget;

	}
```
</details>

##### `_allocateTargets(): WebGLRenderTarget`

<details><summary>Code</summary>

```ts
_allocateTargets() {

		const width = 3 * Math.max( this._cubeSize, 16 * 7 );
		const height = 4 * this._cubeSize;

		const params = {
			magFilter: LinearFilter,
			minFilter: LinearFilter,
			generateMipmaps: false,
			type: HalfFloatType,
			format: RGBAFormat,
			colorSpace: LinearSRGBColorSpace,
			depthBuffer: false
		};

		const cubeUVRenderTarget = _createRenderTarget( width, height, params );

		if ( this._pingPongRenderTarget === null || this._pingPongRenderTarget.width !== width || this._pingPongRenderTarget.height !== height ) {

			if ( this._pingPongRenderTarget !== null ) {

				this._dispose();

			}

			this._pingPongRenderTarget = _createRenderTarget( width, height, params );

			const { _lodMax } = this;
			( { sizeLods: this._sizeLods, lodPlanes: this._lodPlanes, sigmas: this._sigmas } = _createPlanes( _lodMax ) );

			this._blurMaterial = _getBlurShader( _lodMax, width, height );

		}

		return cubeUVRenderTarget;

	}
```
</details>

##### `_compileMaterial(material: any): void`

<details><summary>Code</summary>

```ts
_compileMaterial( material ) {

		const tmpMesh = new Mesh( this._lodPlanes[ 0 ], material );
		this._renderer.compile( tmpMesh, _flatCamera );

	}
```
</details>

##### `_sceneToCubeUV(scene: any, near: any, far: any, cubeUVRenderTarget: any, position: any): void`

<details><summary>Code</summary>

```ts
_sceneToCubeUV( scene, near, far, cubeUVRenderTarget, position ) {

		const fov = 90;
		const aspect = 1;
		const cubeCamera = new PerspectiveCamera( fov, aspect, near, far );
		const upSign = [ 1, - 1, 1, 1, 1, 1 ];
		const forwardSign = [ 1, 1, 1, - 1, - 1, - 1 ];
		const renderer = this._renderer;

		const originalAutoClear = renderer.autoClear;
		const toneMapping = renderer.toneMapping;
		renderer.getClearColor( _clearColor );

		renderer.toneMapping = NoToneMapping;
		renderer.autoClear = false;

		// https://github.com/mrdoob/three.js/issues/31413#issuecomment-3095966812
		const reversedDepthBuffer = renderer.state.buffers.depth.getReversed();

		if ( reversedDepthBuffer ) {

			renderer.setRenderTarget( cubeUVRenderTarget );
			renderer.clearDepth();
			renderer.setRenderTarget( null );

		}

		const backgroundMaterial = new MeshBasicMaterial( {
			name: 'PMREM.Background',
			side: BackSide,
			depthWrite: false,
			depthTest: false,
		} );

		const backgroundBox = new Mesh( new BoxGeometry(), backgroundMaterial );

		let useSolidColor = false;
		const background = scene.background;

		if ( background ) {

			if ( background.isColor ) {

				backgroundMaterial.color.copy( background );
				scene.background = null;
				useSolidColor = true;

			}

		} else {

			backgroundMaterial.color.copy( _clearColor );
			useSolidColor = true;

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

			renderer.setRenderTarget( cubeUVRenderTarget );

			if ( useSolidColor ) {

				renderer.render( backgroundBox, cubeCamera );

			}

			renderer.render( scene, cubeCamera );

		}

		backgroundBox.geometry.dispose();
		backgroundBox.material.dispose();

		renderer.toneMapping = toneMapping;
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

				this._cubemapMaterial = _getCubemapMaterial();

			}

			this._cubemapMaterial.uniforms.flipEnvMap.value = ( texture.isRenderTargetTexture === false ) ? - 1 : 1;

		} else {

			if ( this._equirectMaterial === null ) {

				this._equirectMaterial = _getEquirectMaterial();

			}

		}

		const material = isCubeTexture ? this._cubemapMaterial : this._equirectMaterial;
		const mesh = new Mesh( this._lodPlanes[ 0 ], material );

		const uniforms = material.uniforms;

		uniforms[ 'envMap' ].value = texture;

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

##### `_blur(cubeUVRenderTarget: WebGLRenderTarget, lodIn: number, lodOut: number, sigma: number, poleAxis: Vector3): void`

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

			console.error(
				'blur direction must be either latitudinal or longitudinal!' );

		}

		// Number of standard deviations at which to cut off the discrete approximation.
		const STANDARD_DEVIATIONS = 3;

		const blurMesh = new Mesh( this._lodPlanes[ lodOut ], blurMaterial );
		const blurUniforms = blurMaterial.uniforms;

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

		blurUniforms[ 'envMap' ].value = targetIn.texture;
		blurUniforms[ 'samples' ].value = samples;
		blurUniforms[ 'weights' ].value = weights;
		blurUniforms[ 'latitudinal' ].value = direction === 'latitudinal';

		if ( poleAxis ) {

			blurUniforms[ 'poleAxis' ].value = poleAxis;

		}

		const { _lodMax } = this;
		blurUniforms[ 'dTheta' ].value = radiansPerPixel;
		blurUniforms[ 'mipInt' ].value = _lodMax - lodIn;

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