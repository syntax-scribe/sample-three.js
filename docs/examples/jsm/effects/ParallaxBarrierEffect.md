[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ParallaxBarrierEffect.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/effects/ParallaxBarrierEffect.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LinearFilter` | `three` |
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
| `_renderTargetL` | `any` | let/var | `new WebGLRenderTarget( 512, 512, _params )` | ✗ |
| `_renderTargetR` | `any` | let/var | `new WebGLRenderTarget( 512, 512, _params )` | ✗ |
| `_material` | `any` | let/var | `new ShaderMaterial( { uniforms: { 'mapLeft': { value: _renderTargetL.texture ...` | ✗ |
| `_quad` | `FullScreenQuad` | let/var | `new FullScreenQuad( _material )` | ✗ |


---

## Classes

### `ParallaxBarrierEffect`

<details><summary>Class Code</summary>

```ts
class ParallaxBarrierEffect {

	/**
	 * Constructs a new parallax barrier effect.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 */
	constructor( renderer ) {

		const _stereo = new StereoCamera();

		const _params = { minFilter: LinearFilter, magFilter: NearestFilter, format: RGBAFormat };

		const _renderTargetL = new WebGLRenderTarget( 512, 512, _params );
		const _renderTargetR = new WebGLRenderTarget( 512, 512, _params );

		const _material = new ShaderMaterial( {

			uniforms: {

				'mapLeft': { value: _renderTargetL.texture },
				'mapRight': { value: _renderTargetR.texture }

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

				'void main() {',

				'	vec2 uv = vUv;',

				'	if ( ( mod( gl_FragCoord.y, 2.0 ) ) > 1.00 ) {',

				'		gl_FragColor = texture2D( mapLeft, uv );',

				'	} else {',

				'		gl_FragColor = texture2D( mapRight, uv );',

				'	}',

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