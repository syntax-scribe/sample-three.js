[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `AnaglyphEffect.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/effects/AnaglyphEffect.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LinearFilter` | `three` |
| `Matrix3` | `three` |
| `NearestFilter` | `three` |
| `RGBAFormat` | `three` |
| `ShaderMaterial` | `three` |
| `StereoCamera` | `three` |
| `WebGLRenderTarget` | `three` |
| `FullScreenQuad` | `../postprocessing/Pass.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_stereo` | `any` | let/var | `new StereoCamera()` | ✗ |
| `_params` | `{ minFilter: any; magFilter: any; for...` | let/var | `{ minFilter: LinearFilter, magFilter: NearestFilter, format: RGBAFormat }` | ✗ |
| `_renderTargetL` | `any` | let/var | `new WebGLRenderTarget( width, height, _params )` | ✗ |
| `_renderTargetR` | `any` | let/var | `new WebGLRenderTarget( width, height, _params )` | ✗ |
| `_material` | `any` | let/var | `new ShaderMaterial( { uniforms: { 'mapLeft': { value: _renderTargetL.texture ...` | ✗ |
| `_quad` | `FullScreenQuad` | let/var | `new FullScreenQuad( _material )` | ✗ |


---

## Classes

### `AnaglyphEffect`

<details><summary>Class Code</summary>

```ts
class AnaglyphEffect {

	/**
	 * Constructs a new anaglyph effect.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {number} width - The width of the effect in physical pixels.
	 * @param {number} height - The height of the effect in physical pixels.
	 */
	constructor( renderer, width = 512, height = 512 ) {

		// Dubois matrices from https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.7.6968&rep=rep1&type=pdf#page=4

		this.colorMatrixLeft = new Matrix3().fromArray( [
			0.456100, - 0.0400822, - 0.0152161,
			0.500484, - 0.0378246, - 0.0205971,
			0.176381, - 0.0157589, - 0.00546856
		] );

		this.colorMatrixRight = new Matrix3().fromArray( [
			- 0.0434706, 0.378476, - 0.0721527,
			- 0.0879388, 0.73364, - 0.112961,
			- 0.00155529, - 0.0184503, 1.2264
		] );

		const _stereo = new StereoCamera();

		const _params = { minFilter: LinearFilter, magFilter: NearestFilter, format: RGBAFormat };

		const _renderTargetL = new WebGLRenderTarget( width, height, _params );
		const _renderTargetR = new WebGLRenderTarget( width, height, _params );

		const _material = new ShaderMaterial( {

			uniforms: {

				'mapLeft': { value: _renderTargetL.texture },
				'mapRight': { value: _renderTargetR.texture },

				'colorMatrixLeft': { value: this.colorMatrixLeft },
				'colorMatrixRight': { value: this.colorMatrixRight }

			},

			vertexShader: [

				'varying vec2 vUv;',

				'void main() {',

				'	vUv = vec2( uv.x, uv.y );',
				'	gl_Position = projectionMatrix * modelViewMatrix * vec4( position, 1.0 );',

				'}'

			].join( '\n' ),

			fragmentShader: [

				'uniform sampler2D mapLeft;',
				'uniform sampler2D mapRight;',
				'varying vec2 vUv;',

				'uniform mat3 colorMatrixLeft;',
				'uniform mat3 colorMatrixRight;',

				'void main() {',

				'	vec2 uv = vUv;',

				'	vec4 colorL = texture2D( mapLeft, uv );',
				'	vec4 colorR = texture2D( mapRight, uv );',

				'	vec3 color = clamp(',
				'			colorMatrixLeft * colorL.rgb +',
				'			colorMatrixRight * colorR.rgb, 0., 1. );',

				'	gl_FragColor = vec4(',
				'			color.r, color.g, color.b,',
				'			max( colorL.a, colorR.a ) );',

				'	#include <tonemapping_fragment>',
				'	#include <colorspace_fragment>',

				'}'

			].join( '\n' )

		} );

		const _quad = new FullScreenQuad( _material );

		/**
		 * Resizes the effect.
		 *
		 * @param {number} width - The width of the effect in logical pixels.
		 * @param {number} height - The height of the effect in logical pixels.
		 */
		this.setSize = function ( width, height ) {

			renderer.setSize( width, height );

			const pixelRatio = renderer.getPixelRatio();

			_renderTargetL.setSize( width * pixelRatio, height * pixelRatio );
			_renderTargetR.setSize( width * pixelRatio, height * pixelRatio );

		};

		/**
		 * When using this effect, this method should be called instead of the
		 * default {@link WebGLRenderer#render}.
		 *
		 * @param {Object3D} scene - The scene to render.
		 * @param {Camera} camera - The camera.
		 */
		this.render = function ( scene, camera ) {

			const currentRenderTarget = renderer.getRenderTarget();

			if ( scene.matrixWorldAutoUpdate === true ) scene.updateMatrixWorld();

			if ( camera.parent === null && camera.matrixWorldAutoUpdate === true ) camera.updateMatrixWorld();

			_stereo.update( camera );

			renderer.setRenderTarget( _renderTargetL );
			renderer.clear();
			renderer.render( scene, _stereo.cameraL );

			renderer.setRenderTarget( _renderTargetR );
			renderer.clear();
			renderer.render( scene, _stereo.cameraR );

			renderer.setRenderTarget( null );
			_quad.render( renderer );

			renderer.setRenderTarget( currentRenderTarget );

		};

		/**
		 * Frees internal resources. This method should be called
		 * when the effect is no longer required.
		 */
		this.dispose = function () {

			_renderTargetL.dispose();
			_renderTargetR.dispose();

			_material.dispose();
			_quad.dispose();

		};

	}

}
```
</details>


---