[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Reflector.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 11 |
| 📊 Variables & Constants | 26 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/objects/Reflector.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `three` |
| `Matrix4` | `three` |
| `Mesh` | `three` |
| `PerspectiveCamera` | `three` |
| `Plane` | `three` |
| `ShaderMaterial` | `three` |
| `UniformsUtils` | `three` |
| `Vector3` | `three` |
| `Vector4` | `three` |
| `WebGLRenderTarget` | `three` |
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
| `shader` | `any` | let/var | `options.shader \|\| Reflector.ReflectorShader` | ✗ |
| `multisample` | `any` | let/var | `( options.multisample !== undefined ) ? options.multisample : 4` | ✗ |
| `reflectorPlane` | `any` | let/var | `new Plane()` | ✗ |
| `normal` | `any` | let/var | `new Vector3()` | ✗ |
| `reflectorWorldPosition` | `any` | let/var | `new Vector3()` | ✗ |
| `cameraWorldPosition` | `any` | let/var | `new Vector3()` | ✗ |
| `rotationMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `lookAtPosition` | `any` | let/var | `new Vector3( 0, 0, - 1 )` | ✗ |
| `clipPlane` | `any` | let/var | `new Vector4()` | ✗ |
| `view` | `any` | let/var | `new Vector3()` | ✗ |
| `target` | `any` | let/var | `new Vector3()` | ✗ |
| `q` | `any` | let/var | `new Vector4()` | ✗ |
| `textureMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `virtualCamera` | `PerspectiveCamera` | let/var | `this.camera` | ✗ |
| `renderTarget` | `any` | let/var | `new WebGLRenderTarget( textureWidth, textureHeight, { samples: multisample, t...` | ✗ |
| `material` | `any` | let/var | `new ShaderMaterial( { name: ( shader.name !== undefined ) ? shader.name : 'un...` | ✗ |
| `isFacingAway` | `boolean` | let/var | `view.dot( normal ) > 0` | ✗ |
| `projectionMatrix` | `any` | let/var | `virtualCamera.projectionMatrix` | ✗ |
| `currentXrEnabled` | `any` | let/var | `renderer.xr.enabled` | ✗ |
| `currentShadowAutoUpdate` | `any` | let/var | `renderer.shadowMap.autoUpdate` | ✗ |
| `viewport` | `any` | let/var | `camera.viewport` | ✗ |


---

## Classes

### `Reflector`

<details><summary>Class Code</summary>

```ts
class Reflector extends Mesh {

	/**
	 * Constructs a new reflector.
	 *
	 * @param {BufferGeometry} geometry - The reflector's geometry.
	 * @param {Reflector~Options} [options] - The configuration options.
	 */
	constructor( geometry, options = {} ) {

		super( geometry );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isReflector = true;

		this.type = 'Reflector';

		/**
		 * Whether to force an update, no matter if the reflector
		 * is in view or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.forceUpdate = false;

		/**
		 * The reflector's virtual camera. This is used to render
		 * the scene from the mirror's point of view.
		 *
		 * @type {PerspectiveCamera}
		 */
		this.camera = new PerspectiveCamera();

		const scope = this;

		const color = ( options.color !== undefined ) ? new Color( options.color ) : new Color( 0x7F7F7F );
		const textureWidth = options.textureWidth || 512;
		const textureHeight = options.textureHeight || 512;
		const clipBias = options.clipBias || 0;
		const shader = options.shader || Reflector.ReflectorShader;
		const multisample = ( options.multisample !== undefined ) ? options.multisample : 4;

		//

		const reflectorPlane = new Plane();
		const normal = new Vector3();
		const reflectorWorldPosition = new Vector3();
		const cameraWorldPosition = new Vector3();
		const rotationMatrix = new Matrix4();
		const lookAtPosition = new Vector3( 0, 0, - 1 );
		const clipPlane = new Vector4();

		const view = new Vector3();
		const target = new Vector3();
		const q = new Vector4();

		const textureMatrix = new Matrix4();
		const virtualCamera = this.camera;

		const renderTarget = new WebGLRenderTarget( textureWidth, textureHeight, { samples: multisample, type: HalfFloatType } );

		const material = new ShaderMaterial( {
			name: ( shader.name !== undefined ) ? shader.name : 'unspecified',
			uniforms: UniformsUtils.clone( shader.uniforms ),
			fragmentShader: shader.fragmentShader,
			vertexShader: shader.vertexShader
		} );

		material.uniforms[ 'tDiffuse' ].value = renderTarget.texture;
		material.uniforms[ 'color' ].value = color;
		material.uniforms[ 'textureMatrix' ].value = textureMatrix;

		this.material = material;

		this.onBeforeRender = function ( renderer, scene, camera ) {

			reflectorWorldPosition.setFromMatrixPosition( scope.matrixWorld );
			cameraWorldPosition.setFromMatrixPosition( camera.matrixWorld );

			rotationMatrix.extractRotation( scope.matrixWorld );

			normal.set( 0, 0, 1 );
			normal.applyMatrix4( rotationMatrix );

			view.subVectors( reflectorWorldPosition, cameraWorldPosition );

			// Avoid rendering when reflector is facing away unless forcing an update
			const isFacingAway = view.dot( normal ) > 0;

			if ( isFacingAway === true && this.forceUpdate === false ) return;

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

			// Now update projection matrix with new clip plane, implementing code from: http://www.terathon.com/code/oblique.html
			// Paper explaining this technique: http://www.terathon.com/lengyel/Lengyel-Oblique.pdf
			reflectorPlane.setFromNormalAndCoplanarPoint( normal, reflectorWorldPosition );
			reflectorPlane.applyMatrix4( virtualCamera.matrixWorldInverse );

			clipPlane.set( reflectorPlane.normal.x, reflectorPlane.normal.y, reflectorPlane.normal.z, reflectorPlane.constant );

			const projectionMatrix = virtualCamera.projectionMatrix;

			q.x = ( Math.sign( clipPlane.x ) + projectionMatrix.elements[ 8 ] ) / projectionMatrix.elements[ 0 ];
			q.y = ( Math.sign( clipPlane.y ) + projectionMatrix.elements[ 9 ] ) / projectionMatrix.elements[ 5 ];
			q.z = - 1.0;
			q.w = ( 1.0 + projectionMatrix.elements[ 10 ] ) / projectionMatrix.elements[ 14 ];

			// Calculate the scaled plane vector
			clipPlane.multiplyScalar( 2.0 / clipPlane.dot( q ) );

			// Replacing the third row of the projection matrix
			projectionMatrix.elements[ 2 ] = clipPlane.x;
			projectionMatrix.elements[ 6 ] = clipPlane.y;
			projectionMatrix.elements[ 10 ] = clipPlane.z + 1.0 - clipBias;
			projectionMatrix.elements[ 14 ] = clipPlane.w;

			// Render
			scope.visible = false;

			const currentRenderTarget = renderer.getRenderTarget();

			const currentXrEnabled = renderer.xr.enabled;
			const currentShadowAutoUpdate = renderer.shadowMap.autoUpdate;

			renderer.xr.enabled = false; // Avoid camera modification
			renderer.shadowMap.autoUpdate = false; // Avoid re-computing shadows

			renderer.setRenderTarget( renderTarget );

			renderer.state.buffers.depth.setMask( true ); // make sure the depth buffer is writable so it can be properly cleared, see #18897

			if ( renderer.autoClear === false ) renderer.clear();
			renderer.render( scene, virtualCamera );

			renderer.xr.enabled = currentXrEnabled;
			renderer.shadowMap.autoUpdate = currentShadowAutoUpdate;

			renderer.setRenderTarget( currentRenderTarget );

			// Restore viewport

			const viewport = camera.viewport;

			if ( viewport !== undefined ) {

				renderer.state.viewport( viewport );

			}

			scope.visible = true;
			this.forceUpdate = false;

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