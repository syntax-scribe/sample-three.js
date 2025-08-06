[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `OutlineEffect.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 21 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/effects/OutlineEffect.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BackSide` | `three` |
| `Color` | `three` |
| `ShaderMaterial` | `three` |
| `UniformsLib` | `three` |
| `UniformsUtils` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `defaultThickness` | `any` | let/var | `parameters.defaultThickness !== undefined ? parameters.defaultThickness : 0.003` | ✗ |
| `defaultAlpha` | `any` | let/var | `parameters.defaultAlpha !== undefined ? parameters.defaultAlpha : 1.0` | ✗ |
| `defaultKeepAlive` | `any` | let/var | `parameters.defaultKeepAlive !== undefined ? parameters.defaultKeepAlive : false` | ✗ |
| `cache` | `{}` | let/var | `{}` | ✗ |
| `removeThresholdCount` | `60` | let/var | `60` | ✗ |
| `originalMaterials` | `{}` | let/var | `{}` | ✗ |
| `originalOnBeforeRenders` | `{}` | let/var | `{}` | ✗ |
| `uniformsOutline` | `{ outlineThickness: { value: any; }; ...` | let/var | `{ outlineThickness: { value: defaultThickness }, outlineColor: { value: defau...` | ✗ |
| `data` | `any` | let/var | `cache[ originalMaterial.uuid ]` | ✗ |
| `geometry` | `any` | let/var | `object.geometry` | ✗ |
| `hasNormals` | `boolean` | let/var | `( geometry !== undefined ) && ( geometry.attributes.normal !== undefined )` | ✗ |
| `originalMaterial` | `any` | let/var | `originalMaterials[ material.uuid ]` | ✗ |
| `outlineParameters` | `any` | let/var | `originalMaterial.userData.outlineParameters` | ✗ |
| `outlineParameters` | `any` | let/var | `originalMaterial.userData.outlineParameters` | ✗ |
| `keys` | `any` | let/var | `*not shown*` | ✗ |
| `key` | `string` | let/var | `keys[ i ]` | ✗ |
| `currentAutoClear` | `any` | let/var | `renderer.autoClear` | ✗ |
| `currentAutoClear` | `any` | let/var | `renderer.autoClear` | ✗ |
| `currentSceneAutoUpdate` | `any` | let/var | `scene.matrixWorldAutoUpdate` | ✗ |
| `currentSceneBackground` | `any` | let/var | `scene.background` | ✗ |
| `currentShadowMapEnabled` | `any` | let/var | `renderer.shadowMap.enabled` | ✗ |


---

## Functions

### `createMaterial(): any`

**Returns:** `any`

**Calls:**

- `UniformsUtils.merge`

<details><summary>Code</summary>

```typescript
function createMaterial() {

			return new ShaderMaterial( {
				type: 'OutlineEffect',
				uniforms: UniformsUtils.merge( [
					UniformsLib[ 'fog' ],
					UniformsLib[ 'displacementmap' ],
					uniformsOutline
				] ),
				vertexShader: vertexShader,
				fragmentShader: fragmentShader,
				side: BackSide
			} );

		}
```
</details>

### `getOutlineMaterialFromCache(originalMaterial: any): any`

**Parameters:**

- **`originalMaterial`** `any`

**Returns:** `any`

**Calls:**

- `createMaterial`

<details><summary>Code</summary>

```typescript
function getOutlineMaterialFromCache( originalMaterial ) {

			let data = cache[ originalMaterial.uuid ];

			if ( data === undefined ) {

				data = {
					material: createMaterial(),
					used: true,
					keepAlive: defaultKeepAlive,
					count: 0
				};

				cache[ originalMaterial.uuid ] = data;

			}

			data.used = true;

			return data.material;

		}
```
</details>

### `getOutlineMaterial(originalMaterial: any): any`

**Parameters:**

- **`originalMaterial`** `any`

**Returns:** `any`

**Calls:**

- `getOutlineMaterialFromCache`
- `updateOutlineMaterial`

<details><summary>Code</summary>

```typescript
function getOutlineMaterial( originalMaterial ) {

			const outlineMaterial = getOutlineMaterialFromCache( originalMaterial );

			originalMaterials[ outlineMaterial.uuid ] = originalMaterial;

			updateOutlineMaterial( outlineMaterial, originalMaterial );

			return outlineMaterial;

		}
```
</details>

### `isCompatible(object: any): boolean`

**Parameters:**

- **`object`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isCompatible( object ) {

			const geometry = object.geometry;
			const hasNormals = ( geometry !== undefined ) && ( geometry.attributes.normal !== undefined );

			return ( object.isMesh === true && object.material !== undefined && hasNormals === true );

		}
```
</details>

### `setOutlineMaterial(object: any): void`

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `isCompatible`
- `Array.isArray`
- `getOutlineMaterial`

<details><summary>Code</summary>

```typescript
function setOutlineMaterial( object ) {

			if ( isCompatible( object ) === false ) return;

			if ( Array.isArray( object.material ) ) {

				for ( let i = 0, il = object.material.length; i < il; i ++ ) {

					object.material[ i ] = getOutlineMaterial( object.material[ i ] );

				}

			} else {

				object.material = getOutlineMaterial( object.material );

			}

			originalOnBeforeRenders[ object.uuid ] = object.onBeforeRender;
			object.onBeforeRender = onBeforeRender;

		}
```
</details>

### `restoreOriginalMaterial(object: any): void`

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `isCompatible`
- `Array.isArray`

<details><summary>Code</summary>

```typescript
function restoreOriginalMaterial( object ) {

			if ( isCompatible( object ) === false ) return;

			if ( Array.isArray( object.material ) ) {

				for ( let i = 0, il = object.material.length; i < il; i ++ ) {

					object.material[ i ] = originalMaterials[ object.material[ i ].uuid ];

				}

			} else {

				object.material = originalMaterials[ object.material.uuid ];

			}

			object.onBeforeRender = originalOnBeforeRenders[ object.uuid ];

		}
```
</details>

### `onBeforeRender(renderer: any, scene: any, camera: any, geometry: any, material: any): void`

**Parameters:**

- **`renderer`** `any`
- **`scene`** `any`
- **`camera`** `any`
- **`geometry`** `any`
- **`material`** `any`

**Returns:** `void`

**Calls:**

- `updateUniforms`

**Internal Comments:**
```
// just in case
```

<details><summary>Code</summary>

```typescript
function onBeforeRender( renderer, scene, camera, geometry, material ) {

			const originalMaterial = originalMaterials[ material.uuid ];

			// just in case
			if ( originalMaterial === undefined ) return;

			updateUniforms( material, originalMaterial );

		}
```
</details>

### `updateUniforms(material: any, originalMaterial: any): void`

**Parameters:**

- **`material`** `any`
- **`originalMaterial`** `any`

**Returns:** `void`

**Calls:**

- `material.uniforms.outlineColor.value.fromArray`

<details><summary>Code</summary>

```typescript
function updateUniforms( material, originalMaterial ) {

			const outlineParameters = originalMaterial.userData.outlineParameters;

			material.uniforms.outlineAlpha.value = originalMaterial.opacity;

			if ( outlineParameters !== undefined ) {

				if ( outlineParameters.thickness !== undefined ) material.uniforms.outlineThickness.value = outlineParameters.thickness;
				if ( outlineParameters.color !== undefined ) material.uniforms.outlineColor.value.fromArray( outlineParameters.color );
				if ( outlineParameters.alpha !== undefined ) material.uniforms.outlineAlpha.value = outlineParameters.alpha;

			}

			if ( originalMaterial.displacementMap ) {

				material.uniforms.displacementMap.value = originalMaterial.displacementMap;
				material.uniforms.displacementScale.value = originalMaterial.displacementScale;
				material.uniforms.displacementBias.value = originalMaterial.displacementBias;

			}

		}
```
</details>

### `updateOutlineMaterial(material: any, originalMaterial: any): void`

**Parameters:**

- **`material`** `any`
- **`originalMaterial`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function updateOutlineMaterial( material, originalMaterial ) {

			if ( material.name === 'invisible' ) return;

			const outlineParameters = originalMaterial.userData.outlineParameters;

			material.fog = originalMaterial.fog;
			material.toneMapped = originalMaterial.toneMapped;
			material.premultipliedAlpha = originalMaterial.premultipliedAlpha;
			material.displacementMap = originalMaterial.displacementMap;

			if ( outlineParameters !== undefined ) {

				if ( originalMaterial.visible === false ) {

					material.visible = false;

				} else {

					material.visible = ( outlineParameters.visible !== undefined ) ? outlineParameters.visible : true;

				}

				material.transparent = ( outlineParameters.alpha !== undefined && outlineParameters.alpha < 1.0 ) ? true : originalMaterial.transparent;

				if ( outlineParameters.keepAlive !== undefined ) cache[ originalMaterial.uuid ].keepAlive = outlineParameters.keepAlive;

			} else {

				material.transparent = originalMaterial.transparent;
				material.visible = originalMaterial.visible;

			}

			if ( originalMaterial.wireframe === true || originalMaterial.depthTest === false ) material.visible = false;

			if ( originalMaterial.clippingPlanes ) {

				material.clipping = true;

				material.clippingPlanes = originalMaterial.clippingPlanes;
				material.clipIntersection = originalMaterial.clipIntersection;
				material.clipShadows = originalMaterial.clipShadows;

			}

			material.version = originalMaterial.version; // update outline material if necessary

		}
```
</details>

### `cleanupCache(): void`

**Returns:** `void`

**Calls:**

- `Object.keys`

**Internal Comments:**
```
// clear originalMaterials (x3)
// clear originalOnBeforeRenders (x3)
// remove unused outlineMaterial from cache (x3)
```

<details><summary>Code</summary>

```typescript
function cleanupCache() {

			let keys;

			// clear originalMaterials
			keys = Object.keys( originalMaterials );

			for ( let i = 0, il = keys.length; i < il; i ++ ) {

				originalMaterials[ keys[ i ] ] = undefined;

			}

			// clear originalOnBeforeRenders
			keys = Object.keys( originalOnBeforeRenders );

			for ( let i = 0, il = keys.length; i < il; i ++ ) {

				originalOnBeforeRenders[ keys[ i ] ] = undefined;

			}

			// remove unused outlineMaterial from cache
			keys = Object.keys( cache );

			for ( let i = 0, il = keys.length; i < il; i ++ ) {

				const key = keys[ i ];

				if ( cache[ key ].used === false ) {

					cache[ key ].count ++;

					if ( cache[ key ].keepAlive === false && cache[ key ].count > removeThresholdCount ) {

						delete cache[ key ];

					}

				} else {

					cache[ key ].used = false;
					cache[ key ].count = 0;

				}

			}

		}
```
</details>


---

## Classes

### `OutlineEffect`

<details><summary>Class Code</summary>

```ts
class OutlineEffect {

	/**
	 * Constructs a new outline effect.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {OutlineEffect~Options} [parameters] - The configuration parameter.
	 */
	constructor( renderer, parameters = {} ) {

		this.enabled = true;

		const defaultThickness = parameters.defaultThickness !== undefined ? parameters.defaultThickness : 0.003;
		const defaultColor = new Color().fromArray( parameters.defaultColor !== undefined ? parameters.defaultColor : [ 0, 0, 0 ] );
		const defaultAlpha = parameters.defaultAlpha !== undefined ? parameters.defaultAlpha : 1.0;
		const defaultKeepAlive = parameters.defaultKeepAlive !== undefined ? parameters.defaultKeepAlive : false;

		// object.material.uuid -> outlineMaterial or
		// object.material[ n ].uuid -> outlineMaterial
		// save at the outline material creation and release
		// if it's unused removeThresholdCount frames
		// unless keepAlive is true.
		const cache = {};

		const removeThresholdCount = 60;

		// outlineMaterial.uuid -> object.material or
		// outlineMaterial.uuid -> object.material[ n ]
		// save before render and release after render.
		const originalMaterials = {};

		// object.uuid -> originalOnBeforeRender
		// save before render and release after render.
		const originalOnBeforeRenders = {};

		//this.cache = cache;  // for debug

		const uniformsOutline = {
			outlineThickness: { value: defaultThickness },
			outlineColor: { value: defaultColor },
			outlineAlpha: { value: defaultAlpha }
		};

		const vertexShader = [
			'#include <common>',
			'#include <uv_pars_vertex>',
			'#include <displacementmap_pars_vertex>',
			'#include <fog_pars_vertex>',
			'#include <morphtarget_pars_vertex>',
			'#include <skinning_pars_vertex>',
			'#include <logdepthbuf_pars_vertex>',
			'#include <clipping_planes_pars_vertex>',

			'uniform float outlineThickness;',

			'vec4 calculateOutline( vec4 pos, vec3 normal, vec4 skinned ) {',
			'	float thickness = outlineThickness;',
			'	const float ratio = 1.0;', // TODO: support outline thickness ratio for each vertex
			'	vec4 pos2 = projectionMatrix * modelViewMatrix * vec4( skinned.xyz + normal, 1.0 );',
			// NOTE: subtract pos2 from pos because BackSide objectNormal is negative
			'	vec4 norm = normalize( pos - pos2 );',
			'	return pos + norm * thickness * pos.w * ratio;',
			'}',

			'void main() {',

			'	#include <uv_vertex>',

			'	#include <beginnormal_vertex>',
			'	#include <morphnormal_vertex>',
			'	#include <skinbase_vertex>',
			'	#include <skinnormal_vertex>',

			'	#include <begin_vertex>',
			'	#include <morphtarget_vertex>',
			'	#include <skinning_vertex>',
			'	#include <displacementmap_vertex>',
			'	#include <project_vertex>',

			'	vec3 outlineNormal = - objectNormal;', // the outline material is always rendered with BackSide

			'	gl_Position = calculateOutline( gl_Position, outlineNormal, vec4( transformed, 1.0 ) );',

			'	#include <logdepthbuf_vertex>',
			'	#include <clipping_planes_vertex>',
			'	#include <fog_vertex>',

			'}',

		].join( '\n' );

		const fragmentShader = [

			'#include <common>',
			'#include <fog_pars_fragment>',
			'#include <logdepthbuf_pars_fragment>',
			'#include <clipping_planes_pars_fragment>',

			'uniform vec3 outlineColor;',
			'uniform float outlineAlpha;',

			'void main() {',

			'	#include <clipping_planes_fragment>',
			'	#include <logdepthbuf_fragment>',

			'	gl_FragColor = vec4( outlineColor, outlineAlpha );',

			'	#include <tonemapping_fragment>',
			'	#include <colorspace_fragment>',
			'	#include <fog_fragment>',
			'	#include <premultiplied_alpha_fragment>',

			'}'

		].join( '\n' );

		function createMaterial() {

			return new ShaderMaterial( {
				type: 'OutlineEffect',
				uniforms: UniformsUtils.merge( [
					UniformsLib[ 'fog' ],
					UniformsLib[ 'displacementmap' ],
					uniformsOutline
				] ),
				vertexShader: vertexShader,
				fragmentShader: fragmentShader,
				side: BackSide
			} );

		}

		function getOutlineMaterialFromCache( originalMaterial ) {

			let data = cache[ originalMaterial.uuid ];

			if ( data === undefined ) {

				data = {
					material: createMaterial(),
					used: true,
					keepAlive: defaultKeepAlive,
					count: 0
				};

				cache[ originalMaterial.uuid ] = data;

			}

			data.used = true;

			return data.material;

		}

		function getOutlineMaterial( originalMaterial ) {

			const outlineMaterial = getOutlineMaterialFromCache( originalMaterial );

			originalMaterials[ outlineMaterial.uuid ] = originalMaterial;

			updateOutlineMaterial( outlineMaterial, originalMaterial );

			return outlineMaterial;

		}

		function isCompatible( object ) {

			const geometry = object.geometry;
			const hasNormals = ( geometry !== undefined ) && ( geometry.attributes.normal !== undefined );

			return ( object.isMesh === true && object.material !== undefined && hasNormals === true );

		}

		function setOutlineMaterial( object ) {

			if ( isCompatible( object ) === false ) return;

			if ( Array.isArray( object.material ) ) {

				for ( let i = 0, il = object.material.length; i < il; i ++ ) {

					object.material[ i ] = getOutlineMaterial( object.material[ i ] );

				}

			} else {

				object.material = getOutlineMaterial( object.material );

			}

			originalOnBeforeRenders[ object.uuid ] = object.onBeforeRender;
			object.onBeforeRender = onBeforeRender;

		}

		function restoreOriginalMaterial( object ) {

			if ( isCompatible( object ) === false ) return;

			if ( Array.isArray( object.material ) ) {

				for ( let i = 0, il = object.material.length; i < il; i ++ ) {

					object.material[ i ] = originalMaterials[ object.material[ i ].uuid ];

				}

			} else {

				object.material = originalMaterials[ object.material.uuid ];

			}

			object.onBeforeRender = originalOnBeforeRenders[ object.uuid ];

		}

		function onBeforeRender( renderer, scene, camera, geometry, material ) {

			const originalMaterial = originalMaterials[ material.uuid ];

			// just in case
			if ( originalMaterial === undefined ) return;

			updateUniforms( material, originalMaterial );

		}

		function updateUniforms( material, originalMaterial ) {

			const outlineParameters = originalMaterial.userData.outlineParameters;

			material.uniforms.outlineAlpha.value = originalMaterial.opacity;

			if ( outlineParameters !== undefined ) {

				if ( outlineParameters.thickness !== undefined ) material.uniforms.outlineThickness.value = outlineParameters.thickness;
				if ( outlineParameters.color !== undefined ) material.uniforms.outlineColor.value.fromArray( outlineParameters.color );
				if ( outlineParameters.alpha !== undefined ) material.uniforms.outlineAlpha.value = outlineParameters.alpha;

			}

			if ( originalMaterial.displacementMap ) {

				material.uniforms.displacementMap.value = originalMaterial.displacementMap;
				material.uniforms.displacementScale.value = originalMaterial.displacementScale;
				material.uniforms.displacementBias.value = originalMaterial.displacementBias;

			}

		}

		function updateOutlineMaterial( material, originalMaterial ) {

			if ( material.name === 'invisible' ) return;

			const outlineParameters = originalMaterial.userData.outlineParameters;

			material.fog = originalMaterial.fog;
			material.toneMapped = originalMaterial.toneMapped;
			material.premultipliedAlpha = originalMaterial.premultipliedAlpha;
			material.displacementMap = originalMaterial.displacementMap;

			if ( outlineParameters !== undefined ) {

				if ( originalMaterial.visible === false ) {

					material.visible = false;

				} else {

					material.visible = ( outlineParameters.visible !== undefined ) ? outlineParameters.visible : true;

				}

				material.transparent = ( outlineParameters.alpha !== undefined && outlineParameters.alpha < 1.0 ) ? true : originalMaterial.transparent;

				if ( outlineParameters.keepAlive !== undefined ) cache[ originalMaterial.uuid ].keepAlive = outlineParameters.keepAlive;

			} else {

				material.transparent = originalMaterial.transparent;
				material.visible = originalMaterial.visible;

			}

			if ( originalMaterial.wireframe === true || originalMaterial.depthTest === false ) material.visible = false;

			if ( originalMaterial.clippingPlanes ) {

				material.clipping = true;

				material.clippingPlanes = originalMaterial.clippingPlanes;
				material.clipIntersection = originalMaterial.clipIntersection;
				material.clipShadows = originalMaterial.clipShadows;

			}

			material.version = originalMaterial.version; // update outline material if necessary

		}

		function cleanupCache() {

			let keys;

			// clear originalMaterials
			keys = Object.keys( originalMaterials );

			for ( let i = 0, il = keys.length; i < il; i ++ ) {

				originalMaterials[ keys[ i ] ] = undefined;

			}

			// clear originalOnBeforeRenders
			keys = Object.keys( originalOnBeforeRenders );

			for ( let i = 0, il = keys.length; i < il; i ++ ) {

				originalOnBeforeRenders[ keys[ i ] ] = undefined;

			}

			// remove unused outlineMaterial from cache
			keys = Object.keys( cache );

			for ( let i = 0, il = keys.length; i < il; i ++ ) {

				const key = keys[ i ];

				if ( cache[ key ].used === false ) {

					cache[ key ].count ++;

					if ( cache[ key ].keepAlive === false && cache[ key ].count > removeThresholdCount ) {

						delete cache[ key ];

					}

				} else {

					cache[ key ].used = false;
					cache[ key ].count = 0;

				}

			}

		}

		/**
		 * When using this effect, this method should be called instead of the
		 * default {@link WebGLRenderer#render}.
		 *
		 * @param {Object3D} scene - The scene to render.
		 * @param {Camera} camera - The camera.
		 */
		this.render = function ( scene, camera ) {

			if ( this.enabled === false ) {

				renderer.render( scene, camera );
				return;

			}

			const currentAutoClear = renderer.autoClear;
			renderer.autoClear = this.autoClear;

			renderer.render( scene, camera );

			renderer.autoClear = currentAutoClear;

			this.renderOutline( scene, camera );

		};

		/**
		 * This method can be used to render outlines in VR.
		 *
		 * ```js
		 * const effect = new OutlineEffect( renderer );
		 * let renderingOutline = false;
		 *
		 * scene.onAfterRender = function () {
		 *
		 * 	if ( renderingOutline ) return;
		 *
		 * 	renderingOutline = true;
		 * 	effect.renderOutline( scene, camera );
		 * 	renderingOutline = false;
		 * };
		 *
		 * function render() {
		 * 	renderer.render( scene, camera );
		 * }
		 * ```
		 *
		 * @param {Object3D} scene - The scene to render.
		 * @param {Camera} camera - The camera.
		 */
		this.renderOutline = function ( scene, camera ) {

			const currentAutoClear = renderer.autoClear;
			const currentSceneAutoUpdate = scene.matrixWorldAutoUpdate;
			const currentSceneBackground = scene.background;
			const currentShadowMapEnabled = renderer.shadowMap.enabled;

			scene.matrixWorldAutoUpdate = false;
			scene.background = null;
			renderer.autoClear = false;
			renderer.shadowMap.enabled = false;

			scene.traverse( setOutlineMaterial );

			renderer.render( scene, camera );

			scene.traverse( restoreOriginalMaterial );

			cleanupCache();

			scene.matrixWorldAutoUpdate = currentSceneAutoUpdate;
			scene.background = currentSceneBackground;
			renderer.autoClear = currentAutoClear;
			renderer.shadowMap.enabled = currentShadowMapEnabled;

		};

		/**
		 * Resizes the effect.
		 *
		 * @param {number} width - The width of the effect in logical pixels.
		 * @param {number} height - The height of the effect in logical pixels.
		 */
		this.setSize = function ( width, height ) {

			renderer.setSize( width, height );

		};

	}

}
```
</details>


---