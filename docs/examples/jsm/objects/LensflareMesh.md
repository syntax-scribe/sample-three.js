[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LensflareMesh.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 2 |
| 📦 Imports | 26 |
| 📊 Variables & Constants | 31 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/objects/LensflareMesh.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AdditiveBlending` | `three/webgpu` |
| `Box2` | `three/webgpu` |
| `BufferGeometry` | `three/webgpu` |
| `Color` | `three/webgpu` |
| `FramebufferTexture` | `three/webgpu` |
| `InterleavedBuffer` | `three/webgpu` |
| `InterleavedBufferAttribute` | `three/webgpu` |
| `Mesh` | `three/webgpu` |
| `MeshBasicNodeMaterial` | `three/webgpu` |
| `NodeMaterial` | `three/webgpu` |
| `UnsignedByteType` | `three/webgpu` |
| `Vector2` | `three/webgpu` |
| `Vector3` | `three/webgpu` |
| `Vector4` | `three/webgpu` |
| `Node` | `three/webgpu` |
| `texture` | `three/tsl` |
| `textureLoad` | `three/tsl` |
| `uv` | `three/tsl` |
| `ivec2` | `three/tsl` |
| `vec2` | `three/tsl` |
| `vec4` | `three/tsl` |
| `positionGeometry` | `three/tsl` |
| `reference` | `three/tsl` |
| `varyingProperty` | `three/tsl` |
| `materialReference` | `three/tsl` |
| `Fn` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `positionView` | `any` | let/var | `new Vector3()` | ✗ |
| `tempMap` | `any` | let/var | `new FramebufferTexture( 16, 16 )` | ✗ |
| `occlusionMap` | `any` | let/var | `new FramebufferTexture( 16, 16 )` | ✗ |
| `currentType` | `any` | let/var | `UnsignedByteType` | ✗ |
| `geometry` | `any` | let/var | `LensflareMesh.Geometry` | ✗ |
| `sharedValues` | `{ scale: any; positionScreen: any; }` | let/var | `{ scale: new Vector2(), positionScreen: new Vector3() }` | ✗ |
| `material1a` | `any` | let/var | `new NodeMaterial()` | ✗ |
| `material1b` | `any` | let/var | `new NodeMaterial()` | ✗ |
| `mesh1` | `any` | let/var | `new Mesh( geometry, material1a )` | ✗ |
| `elements` | `any[]` | let/var | `[]` | ✗ |
| `elementMeshes` | `any[]` | let/var | `[]` | ✗ |
| `material2` | `any` | let/var | `new NodeMaterial()` | ✗ |
| `occlusionMap` | `any` | let/var | `material.occlusionMap` | ✗ |
| `positionScreen` | `any` | let/var | `sharedValues.positionScreen` | ✗ |
| `screenPositionPixels` | `any` | let/var | `new Vector4( 0, 0, 16, 16 )` | ✗ |
| `validArea` | `any` | let/var | `new Box2()` | ✗ |
| `viewport` | `any` | let/var | `new Vector4()` | ✗ |
| `lightsNode` | `any` | let/var | `new Node()` | ✗ |
| `type` | `any` | let/var | `( renderTarget !== null ) ? renderTarget.texture.type : UnsignedByteType` | ✗ |
| `invAspect` | `number` | let/var | `viewport.w / viewport.z` | ✗ |
| `halfViewportWidth` | `number` | let/var | `viewport.z / 2.0` | ✗ |
| `halfViewportHeight` | `number` | let/var | `viewport.w / 2.0` | ✗ |
| `size` | `number` | let/var | `16 / viewport.w` | ✗ |
| `vecX` | `number` | let/var | `- positionScreen.x * 2` | ✗ |
| `vecY` | `number` | let/var | `- positionScreen.y * 2` | ✗ |
| `element` | `any` | let/var | `elements[ i ]` | ✗ |
| `mesh2` | `any` | let/var | `elementMeshes[ i ]` | ✗ |
| `size` | `number` | let/var | `element.size / viewport.w` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `float32Array` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ - 1, - 1, 0, 0, 0, 1, - 1, 0, 1, 0, 1, 1, 0, 1, 1, - 1, 1...` | ✗ |
| `interleavedBuffer` | `any` | let/var | `new InterleavedBuffer( float32Array, 5 )` | ✗ |


---

## Classes

### `LensflareMesh`

<details><summary>Class Code</summary>

```ts
class LensflareMesh extends Mesh {

	/**
	 * Constructs a new lensflare mesh.
	 */
	constructor() {

		super( LensflareMesh.Geometry, new MeshBasicNodeMaterial( { opacity: 0, transparent: true } ) );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isLensflareMesh = true;

		this.type = 'LensflareMesh';

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

		const positionView = new Vector3();

		// textures

		const tempMap = new FramebufferTexture( 16, 16 );
		const occlusionMap = new FramebufferTexture( 16, 16 );

		let currentType = UnsignedByteType;

		const geometry = LensflareMesh.Geometry;

		// values for shared material uniforms

		const sharedValues = {
			scale: new Vector2(),
			positionScreen: new Vector3()
		};

		// materials

		const scale = reference( 'scale', 'vec2', sharedValues );
		const screenPosition = reference( 'positionScreen', 'vec3', sharedValues );

		const vertexNode = vec4( positionGeometry.xy.mul( scale ).add( screenPosition.xy ), screenPosition.z, 1.0 );

		const material1a = new NodeMaterial();

		material1a.depthTest = true;
		material1a.depthWrite = false;
		material1a.transparent = false;
		material1a.fog = false;
		material1a.type = 'Lensflare-1a';

		material1a.vertexNode = vertexNode;
		material1a.colorNode = vec4( 1.0, 0.0, 1.0, 1.0 );

		const material1b = new NodeMaterial();

		material1b.depthTest = false;
		material1b.depthWrite = false;
		material1b.transparent = false;
		material1b.fog = false;
		material1b.type = 'Lensflare-1b';

		material1b.vertexNode = vertexNode;
		material1b.colorNode = texture( tempMap, vec2( uv().flipY() ) );

		// the following object is used for occlusionMap generation

		const mesh1 = new Mesh( geometry, material1a );

		//

		const elements = [];
		const elementMeshes = [];

		const material2 = new NodeMaterial();

		material2.transparent = true;
		material2.blending = AdditiveBlending;
		material2.depthWrite = false;
		material2.depthTest = false;
		material2.fog = false;
		material2.type = 'Lensflare-2';

		material2.screenPosition = new Vector3();
		material2.scale = new Vector2();
		material2.occlusionMap = occlusionMap;

		material2.vertexNode = Fn( ( { material } ) => {

			const scale = materialReference( 'scale', 'vec2' );
			const screenPosition = materialReference( 'screenPosition', 'vec3' );

			const occlusionMap = material.occlusionMap;

			const pos = positionGeometry.xy.toVar();

			const visibility = textureLoad( occlusionMap, ivec2( 2, 2 ) ).toVar();
			visibility.addAssign( textureLoad( occlusionMap, ivec2( 8, 2 ) ) );
			visibility.addAssign( textureLoad( occlusionMap, ivec2( 14, 2 ) ) );
			visibility.addAssign( textureLoad( occlusionMap, ivec2( 14, 8 ) ) );
			visibility.addAssign( textureLoad( occlusionMap, ivec2( 14, 14 ) ) );
			visibility.addAssign( textureLoad( occlusionMap, ivec2( 8, 14 ) ) );
			visibility.addAssign( textureLoad( occlusionMap, ivec2( 2, 14 ) ) );
			visibility.addAssign( textureLoad( occlusionMap, ivec2( 2, 8 ) ) );
			visibility.addAssign( textureLoad( occlusionMap, ivec2( 8, 8 ) ) );

			const vVisibility = varyingProperty( 'float', 'vVisibility' );

			vVisibility.assign( visibility.r.div( 9.0 ) );
			vVisibility.mulAssign( visibility.g.div( 9.0 ).oneMinus() );
			vVisibility.mulAssign( visibility.b.div( 9.0 ) );

			return vec4( ( pos.mul( scale ).add( screenPosition.xy ).xy ), screenPosition.z, 1.0 );

		} )();

		material2.colorNode = Fn( () => {

			const color = reference( 'color', 'color' );
			const map = reference( 'map', 'texture' );

			const vVisibility = varyingProperty( 'float', 'vVisibility' );

			const output = map.toVar();

			output.a.mulAssign( vVisibility );
			output.rgb.mulAssign( color );

			return output;

		} )();

		/**
		 * Adds the given lensflare element to this instance.
		 *
		 * @param {LensflareElement} element - The element to add.
		 */
		this.addElement = function ( element ) {

			elements.push( element );

		};

		//

		const positionScreen = sharedValues.positionScreen;
		const screenPositionPixels = new Vector4( 0, 0, 16, 16 );
		const validArea = new Box2();
		const viewport = new Vector4();

		// dummy node for renderer.renderObject()
		const lightsNode = new Node();

		this.onBeforeRender = ( renderer, scene, camera ) => {

			renderer.getViewport( viewport );

			viewport.multiplyScalar( window.devicePixelRatio );

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

			const size = 16 / viewport.w;

			sharedValues.scale.set( size * invAspect, size );

			validArea.min.set( viewport.x, viewport.y );
			validArea.max.set( viewport.x + ( viewport.z - 16 ), viewport.y + ( viewport.w - 16 ) );

			// calculate position in screen space

			positionView.setFromMatrixPosition( this.matrixWorld );
			positionView.applyMatrix4( camera.matrixWorldInverse );

			if ( positionView.z > 0 ) return; // lensflare is behind the camera

			positionScreen.copy( positionView ).applyMatrix4( camera.projectionMatrix );

			// horizontal and vertical coordinate of the lower left corner of the pixels to copy

			screenPositionPixels.x = viewport.x + ( positionScreen.x * halfViewportWidth ) + halfViewportWidth - 8;
			screenPositionPixels.y = viewport.y - ( positionScreen.y * halfViewportHeight ) + halfViewportHeight - 8;

			// screen cull

			if ( validArea.containsPoint( screenPositionPixels ) ) {

				// save current RGB to temp texture

				renderer.copyFramebufferToTexture( tempMap, screenPositionPixels );

				// render pink quad

				renderer.renderObject( mesh1, scene, camera, geometry, material1a, null, lightsNode );

				// copy result to occlusionMap

				renderer.copyFramebufferToTexture( occlusionMap, screenPositionPixels );

				// restore graphics

				renderer.renderObject( mesh1, scene, camera, geometry, material1b, null, lightsNode );

				// render elements

				const vecX = - positionScreen.x * 2;
				const vecY = - positionScreen.y * 2;

				for ( let i = 0, l = elements.length; i < l; i ++ ) {

					const element = elements[ i ];

					let mesh2 = elementMeshes[ i ];

					if ( mesh2 === undefined ) {

						mesh2 = elementMeshes[ i ] = new Mesh( geometry, material2 );

						mesh2.color = element.color.convertSRGBToLinear();
						mesh2.map = element.texture;

					}

					material2.screenPosition.x = positionScreen.x + vecX * element.distance;
					material2.screenPosition.y = positionScreen.y - vecY * element.distance;
					material2.screenPosition.z = positionScreen.z;

					const size = element.size / viewport.w;

					material2.scale.set( size * invAspect, size );

					renderer.renderObject( mesh2, scene, camera, geometry, material2, null, lightsNode );

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

	constructor( texture, size = 1, distance = 0, color = new Color( 0xffffff ) ) {

		this.texture = texture;
		this.size = size;
		this.distance = distance;
		this.color = color;

	}

}
```
</details>


---