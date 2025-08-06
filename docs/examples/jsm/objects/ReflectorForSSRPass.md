[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ReflectorForSSRPass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 14 |
| 📊 Variables & Constants | 29 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/objects/ReflectorForSSRPass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `three` |
| `Matrix4` | `three` |
| `Mesh` | `three` |
| `PerspectiveCamera` | `three` |
| `ShaderMaterial` | `three` |
| `UniformsUtils` | `three` |
| `Vector2` | `three` |
| `Vector3` | `three` |
| `WebGLRenderTarget` | `three` |
| `DepthTexture` | `three` |
| `UnsignedShortType` | `three` |
| `NearestFilter` | `three` |
| `Plane` | `three` |
| `HalfFloatType` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `color` | `any` | let/var | `( options.color !== undefined ) ? new Color( options.color ) : new Color( 0x7...` | ✗ |
| `textureWidth` | `any` | let/var | `options.textureWidth \|\| 512` | ✗ |
| `textureHeight` | `any` | let/var | `options.textureHeight \|\| 512` | ✗ |
| `clipBias` | `any` | let/var | `options.clipBias \|\| 0` | ✗ |
| `shader` | `any` | let/var | `options.shader \|\| ReflectorForSSRPass.ReflectorShader` | ✗ |
| `useDepthTexture` | `boolean` | let/var | `options.useDepthTexture === true` | ✗ |
| `yAxis` | `any` | let/var | `new Vector3( 0, 1, 0 )` | ✗ |
| `vecTemp0` | `any` | let/var | `new Vector3()` | ✗ |
| `vecTemp1` | `any` | let/var | `new Vector3()` | ✗ |
| `normal` | `any` | let/var | `new Vector3()` | ✗ |
| `reflectorWorldPosition` | `any` | let/var | `new Vector3()` | ✗ |
| `cameraWorldPosition` | `any` | let/var | `new Vector3()` | ✗ |
| `rotationMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `lookAtPosition` | `any` | let/var | `new Vector3( 0, 0, - 1 )` | ✗ |
| `view` | `any` | let/var | `new Vector3()` | ✗ |
| `target` | `any` | let/var | `new Vector3()` | ✗ |
| `textureMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `virtualCamera` | `any` | let/var | `new PerspectiveCamera()` | ✗ |
| `depthTexture` | `any` | let/var | `*not shown*` | ✗ |
| `parameters` | `{ depthTexture: any; type: any; }` | let/var | `{ depthTexture: useDepthTexture ? depthTexture : null, type: HalfFloatType }` | ✗ |
| `renderTarget` | `any` | let/var | `new WebGLRenderTarget( textureWidth, textureHeight, parameters )` | ✗ |
| `material` | `any` | let/var | `new ShaderMaterial( { name: ( shader.name !== undefined ) ? shader.name : 'un...` | ✗ |
| `globalPlane` | `any` | let/var | `new Plane( new Vector3( 0, 1, 0 ), clipBias )` | ✗ |
| `globalPlanes` | `any[]` | let/var | `[ globalPlane ]` | ✗ |
| `currentXrEnabled` | `any` | let/var | `renderer.xr.enabled` | ✗ |
| `currentShadowAutoUpdate` | `any` | let/var | `renderer.shadowMap.autoUpdate` | ✗ |
| `currentClippingPlanes` | `any` | let/var | `renderer.clippingPlanes` | ✗ |
| `viewport` | `any` | let/var | `camera.viewport` | ✗ |


---

## Classes

### `ReflectorForSSRPass`

<details><summary>Class Code</summary>

```ts
class ReflectorForSSRPass extends Mesh {

	/**
	 * Constructs a new reflector.
	 *
	 * @param {BufferGeometry} geometry - The reflector's geometry.
	 * @param {ReflectorForSSRPass~Options} [options] - The configuration options.
	 */
	constructor( geometry, options = {} ) {

		super( geometry );

		this.isReflectorForSSRPass = true;

		this.type = 'ReflectorForSSRPass';

		const scope = this;

		const color = ( options.color !== undefined ) ? new Color( options.color ) : new Color( 0x7F7F7F );
		const textureWidth = options.textureWidth || 512;
		const textureHeight = options.textureHeight || 512;
		const clipBias = options.clipBias || 0;
		const shader = options.shader || ReflectorForSSRPass.ReflectorShader;
		const useDepthTexture = options.useDepthTexture === true;
		const yAxis = new Vector3( 0, 1, 0 );
		const vecTemp0 = new Vector3();
		const vecTemp1 = new Vector3();

		//

		scope.needsUpdate = false;
		scope.maxDistance = ReflectorForSSRPass.ReflectorShader.uniforms.maxDistance.value;
		scope.opacity = ReflectorForSSRPass.ReflectorShader.uniforms.opacity.value;
		scope.color = color;
		scope.resolution = options.resolution || new Vector2( window.innerWidth, window.innerHeight );


		scope._distanceAttenuation = ReflectorForSSRPass.ReflectorShader.defines.DISTANCE_ATTENUATION;
		Object.defineProperty( scope, 'distanceAttenuation', {
			get() {

				return scope._distanceAttenuation;

			},
			set( val ) {

				if ( scope._distanceAttenuation === val ) return;
				scope._distanceAttenuation = val;
				scope.material.defines.DISTANCE_ATTENUATION = val;
				scope.material.needsUpdate = true;

			}
		} );

		scope._fresnel = ReflectorForSSRPass.ReflectorShader.defines.FRESNEL;
		Object.defineProperty( scope, 'fresnel', {
			get() {

				return scope._fresnel;

			},
			set( val ) {

				if ( scope._fresnel === val ) return;
				scope._fresnel = val;
				scope.material.defines.FRESNEL = val;
				scope.material.needsUpdate = true;

			}
		} );

		const normal = new Vector3();
		const reflectorWorldPosition = new Vector3();
		const cameraWorldPosition = new Vector3();
		const rotationMatrix = new Matrix4();
		const lookAtPosition = new Vector3( 0, 0, - 1 );

		const view = new Vector3();
		const target = new Vector3();

		const textureMatrix = new Matrix4();
		const virtualCamera = new PerspectiveCamera();

		let depthTexture;

		if ( useDepthTexture ) {

			depthTexture = new DepthTexture();
			depthTexture.type = UnsignedShortType;
			depthTexture.minFilter = NearestFilter;
			depthTexture.magFilter = NearestFilter;

		}

		const parameters = {
			depthTexture: useDepthTexture ? depthTexture : null,
			type: HalfFloatType
		};

		const renderTarget = new WebGLRenderTarget( textureWidth, textureHeight, parameters );

		const material = new ShaderMaterial( {
			name: ( shader.name !== undefined ) ? shader.name : 'unspecified',
			transparent: useDepthTexture,
			defines: Object.assign( {}, ReflectorForSSRPass.ReflectorShader.defines, {
				useDepthTexture
			} ),
			uniforms: UniformsUtils.clone( shader.uniforms ),
			fragmentShader: shader.fragmentShader,
			vertexShader: shader.vertexShader
		} );

		material.uniforms[ 'tDiffuse' ].value = renderTarget.texture;
		material.uniforms[ 'color' ].value = scope.color;
		material.uniforms[ 'textureMatrix' ].value = textureMatrix;
		if ( useDepthTexture ) {

			material.uniforms[ 'tDepth' ].value = renderTarget.depthTexture;

		}

		this.material = material;

		const globalPlane = new Plane( new Vector3( 0, 1, 0 ), clipBias );
		const globalPlanes = [ globalPlane ];

		this.doRender = function ( renderer, scene, camera ) {

			material.uniforms[ 'maxDistance' ].value = scope.maxDistance;
			material.uniforms[ 'color' ].value = scope.color;
			material.uniforms[ 'opacity' ].value = scope.opacity;

			vecTemp0.copy( camera.position ).normalize();
			vecTemp1.copy( vecTemp0 ).reflect( yAxis );
			material.uniforms[ 'fresnelCoe' ].value = ( vecTemp0.dot( vecTemp1 ) + 1. ) / 2.; // TODO: Also need to use glsl viewPosition and viewNormal per pixel.

			reflectorWorldPosition.setFromMatrixPosition( scope.matrixWorld );
			cameraWorldPosition.setFromMatrixPosition( camera.matrixWorld );

			rotationMatrix.extractRotation( scope.matrixWorld );

			normal.set( 0, 0, 1 );
			normal.applyMatrix4( rotationMatrix );

			view.subVectors( reflectorWorldPosition, cameraWorldPosition );

			// Avoid rendering when reflector is facing away

			if ( view.dot( normal ) > 0 ) return;

			view.reflect( normal ).negate();
			view.add( reflectorWorldPosition );

			rotationMatrix.extractRotation( camera.matrixWorld );

			lookAtPosition.set( 0, 0, - 1 );
			lookAtPosition.applyMatrix4( rotationMatrix );
			lookAtPosition.add( cameraWorldPosition );

			target.subVectors( reflectorWorldPosition, lookAtPosition );
			target.reflect( normal ).negate();
			target.add( reflectorWorldPosition );

			virtualCamera.position.copy( view );
			virtualCamera.up.set( 0, 1, 0 );
			virtualCamera.up.applyMatrix4( rotationMatrix );
			virtualCamera.up.reflect( normal );
			virtualCamera.lookAt( target );

			virtualCamera.far = camera.far; // Used in WebGLBackground

			virtualCamera.updateMatrixWorld();
			virtualCamera.projectionMatrix.copy( camera.projectionMatrix );

			material.uniforms[ 'virtualCameraNear' ].value = camera.near;
			material.uniforms[ 'virtualCameraFar' ].value = camera.far;
			material.uniforms[ 'virtualCameraMatrixWorld' ].value = virtualCamera.matrixWorld;
			material.uniforms[ 'virtualCameraProjectionMatrix' ].value = camera.projectionMatrix;
			material.uniforms[ 'virtualCameraProjectionMatrixInverse' ].value = camera.projectionMatrixInverse;
			material.uniforms[ 'resolution' ].value = scope.resolution;

			// Update the texture matrix
			textureMatrix.set(
				0.5, 0.0, 0.0, 0.5,
				0.0, 0.5, 0.0, 0.5,
				0.0, 0.0, 0.5, 0.5,
				0.0, 0.0, 0.0, 1.0
			);
			textureMatrix.multiply( virtualCamera.projectionMatrix );
			textureMatrix.multiply( virtualCamera.matrixWorldInverse );
			textureMatrix.multiply( scope.matrixWorld );

			// scope.visible = false;

			const currentRenderTarget = renderer.getRenderTarget();

			const currentXrEnabled = renderer.xr.enabled;
			const currentShadowAutoUpdate = renderer.shadowMap.autoUpdate;
			const currentClippingPlanes = renderer.clippingPlanes;

			renderer.xr.enabled = false; // Avoid camera modification
			renderer.shadowMap.autoUpdate = false; // Avoid re-computing shadows
			renderer.clippingPlanes = globalPlanes;

			renderer.setRenderTarget( renderTarget );

			renderer.state.buffers.depth.setMask( true ); // make sure the depth buffer is writable so it can be properly cleared, see #18897

			if ( renderer.autoClear === false ) renderer.clear();
			renderer.render( scene, virtualCamera );

			renderer.xr.enabled = currentXrEnabled;
			renderer.shadowMap.autoUpdate = currentShadowAutoUpdate;
			renderer.clippingPlanes = currentClippingPlanes;

			renderer.setRenderTarget( currentRenderTarget );

			// Restore viewport

			const viewport = camera.viewport;

			if ( viewport !== undefined ) {

				renderer.state.viewport( viewport );

			}

			// scope.visible = true;

		};

		/**
		 * Returns the reflector's internal render target.
		 *
		 * @return {WebGLRenderTarget} The internal render target
		 */
		this.getRenderTarget = function () {

			return renderTarget;

		};

		/**
		 * Frees the GPU-related resources allocated by this instance. Call this
		 * method whenever this instance is no longer used in your app.
		 */
		this.dispose = function () {

			renderTarget.dispose();
			scope.material.dispose();

		};

	}

}
```
</details>


---