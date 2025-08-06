[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Lensflare.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 2 |
| 📦 Imports | 14 |
| 📊 Variables & Constants | 31 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/objects/Lensflare.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AdditiveBlending` | `three` |
| `Box2` | `three` |
| `BufferGeometry` | `three` |
| `Color` | `three` |
| `FramebufferTexture` | `three` |
| `InterleavedBuffer` | `three` |
| `InterleavedBufferAttribute` | `three` |
| `Mesh` | `three` |
| `MeshBasicMaterial` | `three` |
| `RawShaderMaterial` | `three` |
| `UnsignedByteType` | `three` |
| `Vector2` | `three` |
| `Vector3` | `three` |
| `Vector4` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `positionScreen` | `any` | let/var | `new Vector3()` | ✗ |
| `positionView` | `any` | let/var | `new Vector3()` | ✗ |
| `tempMap` | `any` | let/var | `new FramebufferTexture( 16, 16 )` | ✗ |
| `occlusionMap` | `any` | let/var | `new FramebufferTexture( 16, 16 )` | ✗ |
| `currentType` | `any` | let/var | `UnsignedByteType` | ✗ |
| `geometry` | `any` | let/var | `Lensflare.Geometry` | ✗ |
| `material1a` | `any` | let/var | `new RawShaderMaterial( { uniforms: { 'scale': { value: null }, 'screenPositio...` | ✗ |
| `material1b` | `any` | let/var | `new RawShaderMaterial( { uniforms: { 'map': { value: tempMap }, 'scale': { va...` | ✗ |
| `mesh1` | `any` | let/var | `new Mesh( geometry, material1a )` | ✗ |
| `elements` | `any[]` | let/var | `[]` | ✗ |
| `shader` | `{ name: string; uniforms: { map: { va...` | let/var | `LensflareElement.Shader` | ✗ |
| `material2` | `any` | let/var | `new RawShaderMaterial( { name: shader.name, uniforms: { 'map': { value: null ...` | ✗ |
| `mesh2` | `any` | let/var | `new Mesh( geometry, material2 )` | ✗ |
| `scale` | `any` | let/var | `new Vector2()` | ✗ |
| `screenPositionPixels` | `any` | let/var | `new Vector2()` | ✗ |
| `validArea` | `any` | let/var | `new Box2()` | ✗ |
| `viewport` | `any` | let/var | `new Vector4()` | ✗ |
| `type` | `any` | let/var | `( renderTarget !== null ) ? renderTarget.texture.type : UnsignedByteType` | ✗ |
| `invAspect` | `number` | let/var | `viewport.w / viewport.z` | ✗ |
| `halfViewportWidth` | `number` | let/var | `viewport.z / 2.0` | ✗ |
| `halfViewportHeight` | `number` | let/var | `viewport.w / 2.0` | ✗ |
| `size` | `number` | let/var | `16 / viewport.w` | ✗ |
| `uniforms` | `any` | let/var | `material1a.uniforms` | ✗ |
| `vecX` | `number` | let/var | `- positionScreen.x * 2` | ✗ |
| `vecY` | `number` | let/var | `- positionScreen.y * 2` | ✗ |
| `element` | `any` | let/var | `elements[ i ]` | ✗ |
| `uniforms` | `any` | let/var | `material2.uniforms` | ✗ |
| `invAspect` | `number` | let/var | `viewport.w / viewport.z` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `float32Array` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ - 1, - 1, 0, 0, 0, 1, - 1, 0, 1, 0, 1, 1, 0, 1, 1, - 1, 1...` | ✗ |
| `interleavedBuffer` | `any` | let/var | `new InterleavedBuffer( float32Array, 5 )` | ✗ |


---

## Classes

### `Lensflare`

<details><summary>Class Code</summary>

```ts
class Lensflare extends Mesh {

	/**
	 * Constructs a new lensflare.
	 */
	constructor() {

		super( Lensflare.Geometry, new MeshBasicMaterial( { opacity: 0, transparent: true } ) );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isLensflare = true;

		this.type = 'Lensflare';

		/**
		 * Overwritten to disable view-frustum culling by default.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.frustumCulled = false;

		/**
		 * Overwritten to make sure lensflares a rendered last.
		 *
		 * @type {number}
		 * @default Infinity
		 */
		this.renderOrder = Infinity;

		//

		const positionScreen = new Vector3();
		const positionView = new Vector3();

		// textures

		const tempMap = new FramebufferTexture( 16, 16 );
		const occlusionMap = new FramebufferTexture( 16, 16 );

		let currentType = UnsignedByteType;

		// material

		const geometry = Lensflare.Geometry;

		const material1a = new RawShaderMaterial( {
			uniforms: {
				'scale': { value: null },
				'screenPosition': { value: null }
			},
			vertexShader: /* glsl */`

				precision highp float;

				uniform vec3 screenPosition;
				uniform vec2 scale;

				attribute vec3 position;

				void main() {

					gl_Position = vec4( position.xy * scale + screenPosition.xy, screenPosition.z, 1.0 );

				}`,

			fragmentShader: /* glsl */`

				precision highp float;

				void main() {

					gl_FragColor = vec4( 1.0, 0.0, 1.0, 1.0 );

				}`,
			depthTest: true,
			depthWrite: false,
			transparent: false
		} );

		const material1b = new RawShaderMaterial( {
			uniforms: {
				'map': { value: tempMap },
				'scale': { value: null },
				'screenPosition': { value: null }
			},
			vertexShader: /* glsl */`

				precision highp float;

				uniform vec3 screenPosition;
				uniform vec2 scale;

				attribute vec3 position;
				attribute vec2 uv;

				varying vec2 vUV;

				void main() {

					vUV = uv;

					gl_Position = vec4( position.xy * scale + screenPosition.xy, screenPosition.z, 1.0 );

				}`,

			fragmentShader: /* glsl */`

				precision highp float;

				uniform sampler2D map;

				varying vec2 vUV;

				void main() {

					gl_FragColor = texture2D( map, vUV );

				}`,
			depthTest: false,
			depthWrite: false,
			transparent: false
		} );

		// the following object is used for occlusionMap generation

		const mesh1 = new Mesh( geometry, material1a );

		//

		const elements = [];

		const shader = LensflareElement.Shader;

		const material2 = new RawShaderMaterial( {
			name: shader.name,
			uniforms: {
				'map': { value: null },
				'occlusionMap': { value: occlusionMap },
				'color': { value: new Color( 0xffffff ) },
				'scale': { value: new Vector2() },
				'screenPosition': { value: new Vector3() }
			},
			vertexShader: shader.vertexShader,
			fragmentShader: shader.fragmentShader,
			blending: AdditiveBlending,
			transparent: true,
			depthWrite: false
		} );

		const mesh2 = new Mesh( geometry, material2 );

		/**
		 * Adds the given lensflare element to this instance.
		 *
		 * @param {LensflareElement} element - The element to add.
		 */
		this.addElement = function ( element ) {

			elements.push( element );

		};

		//

		const scale = new Vector2();
		const screenPositionPixels = new Vector2();
		const validArea = new Box2();
		const viewport = new Vector4();

		this.onBeforeRender = function ( renderer, scene, camera ) {

			renderer.getCurrentViewport( viewport );

			const renderTarget = renderer.getRenderTarget();
			const type = ( renderTarget !== null ) ? renderTarget.texture.type : UnsignedByteType;

			if ( currentType !== type ) {

				tempMap.dispose();
				occlusionMap.dispose();

				tempMap.type = occlusionMap.type = type;

				currentType = type;

			}

			const invAspect = viewport.w / viewport.z;
			const halfViewportWidth = viewport.z / 2.0;
			const halfViewportHeight = viewport.w / 2.0;

			let size = 16 / viewport.w;
			scale.set( size * invAspect, size );

			validArea.min.set( viewport.x, viewport.y );
			validArea.max.set( viewport.x + ( viewport.z - 16 ), viewport.y + ( viewport.w - 16 ) );

			// calculate position in screen space

			positionView.setFromMatrixPosition( this.matrixWorld );
			positionView.applyMatrix4( camera.matrixWorldInverse );

			if ( positionView.z > 0 ) return; // lensflare is behind the camera

			positionScreen.copy( positionView ).applyMatrix4( camera.projectionMatrix );

			// horizontal and vertical coordinate of the lower left corner of the pixels to copy

			screenPositionPixels.x = viewport.x + ( positionScreen.x * halfViewportWidth ) + halfViewportWidth - 8;
			screenPositionPixels.y = viewport.y + ( positionScreen.y * halfViewportHeight ) + halfViewportHeight - 8;

			// screen cull

			if ( validArea.containsPoint( screenPositionPixels ) ) {

				// save current RGB to temp texture

				renderer.copyFramebufferToTexture( tempMap, screenPositionPixels );

				// render pink quad

				let uniforms = material1a.uniforms;
				uniforms[ 'scale' ].value = scale;
				uniforms[ 'screenPosition' ].value = positionScreen;

				renderer.renderBufferDirect( camera, null, geometry, material1a, mesh1, null );

				// copy result to occlusionMap

				renderer.copyFramebufferToTexture( occlusionMap, screenPositionPixels );

				// restore graphics

				uniforms = material1b.uniforms;
				uniforms[ 'scale' ].value = scale;
				uniforms[ 'screenPosition' ].value = positionScreen;

				renderer.renderBufferDirect( camera, null, geometry, material1b, mesh1, null );

				// render elements

				const vecX = - positionScreen.x * 2;
				const vecY = - positionScreen.y * 2;

				for ( let i = 0, l = elements.length; i < l; i ++ ) {

					const element = elements[ i ];

					const uniforms = material2.uniforms;

					uniforms[ 'color' ].value.copy( element.color );
					uniforms[ 'map' ].value = element.texture;
					uniforms[ 'screenPosition' ].value.x = positionScreen.x + vecX * element.distance;
					uniforms[ 'screenPosition' ].value.y = positionScreen.y + vecY * element.distance;

					size = element.size / viewport.w;
					const invAspect = viewport.w / viewport.z;

					uniforms[ 'scale' ].value.set( size * invAspect, size );

					material2.uniformsNeedUpdate = true;

					renderer.renderBufferDirect( camera, null, geometry, material2, mesh2, null );

				}

			}

		};

		/**
		 * Frees the GPU-related resources allocated by this instance. Call this
		 * method whenever this instance is no longer used in your app.
		 */
		this.dispose = function () {

			material1a.dispose();
			material1b.dispose();
			material2.dispose();

			tempMap.dispose();
			occlusionMap.dispose();

			for ( let i = 0, l = elements.length; i < l; i ++ ) {

				elements[ i ].texture.dispose();

			}

		};

	}

}
```
</details>

### `LensflareElement`

<details><summary>Class Code</summary>

```ts
class LensflareElement {

	/**
	 * Constructs a new lensflare element.
	 *
	 * @param {Texture} texture - The flare's texture.
	 * @param {number} [size=1] - The size in pixels.
	 * @param {number} [distance=0] - The normalized distance (`[0,1]`) from the light source.
	 * A value of `0` means the flare is located at light source.
	 * @param {Color} [color] - The flare's color
	 */
	constructor( texture, size = 1, distance = 0, color = new Color( 0xffffff ) ) {

		/**
		 * The flare's texture.
		 *
		 * @type {Texture}
		 */
		this.texture = texture;

		/**
		 * The size in pixels.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.size = size;

		/**
		 * The normalized distance (`[0,1]`) from the light source.
		 * A value of `0` means the flare is located at light source.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.distance = distance;

		/**
		 * The flare's color
		 *
		 * @type {Color}
		 * @default (1,1,1)
		 */
		this.color = color;

	}

}
```
</details>


---