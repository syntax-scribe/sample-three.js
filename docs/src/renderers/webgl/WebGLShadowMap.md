[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLShadowMap.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 📦 Imports | 18 |
| 📊 Variables & Constants | 35 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLShadowMap.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `FrontSide` | `../../constants.js` |
| `BackSide` | `../../constants.js` |
| `DoubleSide` | `../../constants.js` |
| `NearestFilter` | `../../constants.js` |
| `PCFShadowMap` | `../../constants.js` |
| `VSMShadowMap` | `../../constants.js` |
| `RGBADepthPacking` | `../../constants.js` |
| `NoBlending` | `../../constants.js` |
| `WebGLRenderTarget` | `../WebGLRenderTarget.js` |
| `MeshDepthMaterial` | `../../materials/MeshDepthMaterial.js` |
| `MeshDistanceMaterial` | `../../materials/MeshDistanceMaterial.js` |
| `ShaderMaterial` | `../../materials/ShaderMaterial.js` |
| `BufferAttribute` | `../../core/BufferAttribute.js` |
| `BufferGeometry` | `../../core/BufferGeometry.js` |
| `Mesh` | `../../objects/Mesh.js` |
| `Vector4` | `../../math/Vector4.js` |
| `Vector2` | `../../math/Vector2.js` |
| `Frustum` | `../../math/Frustum.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_frustum` | `Frustum` | let/var | `new Frustum()` | ✗ |
| `_shadowMapSize` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `_viewportSize` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `_viewport` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `_depthMaterial` | `MeshDepthMaterial` | let/var | `new MeshDepthMaterial( { depthPacking: RGBADepthPacking } )` | ✗ |
| `_distanceMaterial` | `MeshDistanceMaterial` | let/var | `new MeshDistanceMaterial()` | ✗ |
| `_materialCache` | `{}` | let/var | `{}` | ✗ |
| `_maxTextureSize` | `any` | let/var | `capabilities.maxTextureSize` | ✗ |
| `shadowSide` | `{ [x: number]: number; }` | let/var | `{ [ FrontSide ]: BackSide, [ BackSide ]: FrontSide, [ DoubleSide ]: DoubleSide }` | ✗ |
| `shadowMaterialVertical` | `ShaderMaterial` | let/var | `new ShaderMaterial( { defines: { VSM_SAMPLES: 8 }, uniforms: { shadow_pass: {...` | ✗ |
| `fullScreenTri` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `fullScreenMesh` | `Mesh` | let/var | `new Mesh( fullScreenTri, shadowMaterialVertical )` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `_previousType` | `number` | let/var | `this.type` | ✗ |
| `_state` | `any` | let/var | `renderer.state` | ✗ |
| `toVSM` | `boolean` | let/var | `( _previousType !== VSMShadowMap && this.type === VSMShadowMap )` | ✗ |
| `fromVSM` | `boolean` | let/var | `( _previousType === VSMShadowMap && this.type !== VSMShadowMap )` | ✗ |
| `light` | `any` | let/var | `lights[ i ]` | ✗ |
| `shadow` | `any` | let/var | `light.shadow` | ✗ |
| `pars` | `{ minFilter: number; magFilter: numbe...` | let/var | `( this.type !== VSMShadowMap ) ? { minFilter: NearestFilter, magFilter: Neare...` | ✗ |
| `result` | `any` | let/var | `null` | ✗ |
| `customMaterial` | `any` | let/var | `( light.isPointLight === true ) ? object.customDistanceMaterial : object.cust...` | ✗ |
| `keyA` | `string` | let/var | `result.uuid` | ✗ |
| `keyB` | `any` | let/var | `material.uuid` | ✗ |
| `materialsForVariant` | `any` | let/var | `_materialCache[ keyA ]` | ✗ |
| `cachedMaterial` | `any` | let/var | `materialsForVariant[ keyB ]` | ✗ |
| `material` | `any` | let/var | `object.material` | ✗ |
| `groups` | `any` | let/var | `geometry.groups` | ✗ |
| `group` | `any` | let/var | `groups[ k ]` | ✗ |
| `groupMaterial` | `any` | let/var | `material[ group.materialIndex ]` | ✗ |
| `children` | `any` | let/var | `object.children` | ✗ |
| `material` | `any` | let/var | `event.target` | ✗ |
| `cache` | `any` | let/var | `_materialCache[ id ]` | ✗ |
| `uuid` | `any` | let/var | `event.target.uuid` | ✗ |
| `shadowMaterial` | `any` | let/var | `cache[ uuid ]` | ✗ |


---

## Functions

### `WebGLShadowMap(renderer: any, objects: any, capabilities: any): void`

**Parameters:**

- **`renderer`** `any`
- **`objects`** `any`
- **`capabilities`** `any`

**Returns:** `void`

**Calls:**

- `shadowMaterialVertical.clone`
- `fullScreenTri.setAttribute`
- `renderer.getRenderTarget`
- `renderer.getActiveCubeFace`
- `renderer.getActiveMipmapLevel`
- `_state.setBlending`
- `_state.buffers.depth.getReversed`
- `_state.buffers.color.setClear`
- `_state.buffers.depth.setTest`
- `_state.setScissorTest`
- `console.warn`
- `_shadowMapSize.copy`
- `shadow.getFrameExtents`
- `_shadowMapSize.multiply`
- `_viewportSize.copy`
- `Math.floor`
- `shadow.map.dispose`
- `shadow.camera.updateProjectionMatrix`
- `renderer.setRenderTarget`
- `renderer.clear`
- `shadow.getViewportCount`
- `shadow.getViewport`
- `_viewport.set`
- `_state.viewport`
- `shadow.updateMatrices`
- `shadow.getFrustum`
- `renderObject`
- `VSMPass`
- `objects.update`
- `renderer.renderBufferDirect`
- `Array.isArray`
- `result.clone`
- `material.addEventListener`
- `renderer.properties.get`
- `object.layers.test`
- `_frustum.intersectsObject`
- `object.modelViewMatrix.multiplyMatrices`
- `getDepthMaterial`
- `object.onBeforeShadow`
- `object.onAfterShadow`
- `material.removeEventListener`
- `shadowMaterial.dispose`

**Internal Comments:**
```
// Set GL state for depth map. (x4)
// check for shadow map type changes (x2)
// render depth map
// do blur pass for VSM
// vertical pass (x6)
// horizontal pass (x6)
// in this case we need a unique material instance reflecting the (x2)
// appropriate state (x2)
// make sure to remove the unique distance/depth materials used for shadow map rendering
```

<details><summary>Code</summary>

```typescript
function WebGLShadowMap( renderer, objects, capabilities ) {

	let _frustum = new Frustum();

	const _shadowMapSize = new Vector2(),
		_viewportSize = new Vector2(),

		_viewport = new Vector4(),

		_depthMaterial = new MeshDepthMaterial( { depthPacking: RGBADepthPacking } ),
		_distanceMaterial = new MeshDistanceMaterial(),

		_materialCache = {},

		_maxTextureSize = capabilities.maxTextureSize;

	const shadowSide = { [ FrontSide ]: BackSide, [ BackSide ]: FrontSide, [ DoubleSide ]: DoubleSide };

	const shadowMaterialVertical = new ShaderMaterial( {
		defines: {
			VSM_SAMPLES: 8
		},
		uniforms: {
			shadow_pass: { value: null },
			resolution: { value: new Vector2() },
			radius: { value: 4.0 }
		},

		vertexShader: vsm.vertex,
		fragmentShader: vsm.fragment

	} );

	const shadowMaterialHorizontal = shadowMaterialVertical.clone();
	shadowMaterialHorizontal.defines.HORIZONTAL_PASS = 1;

	const fullScreenTri = new BufferGeometry();
	fullScreenTri.setAttribute(
		'position',
		new BufferAttribute(
			new Float32Array( [ - 1, - 1, 0.5, 3, - 1, 0.5, - 1, 3, 0.5 ] ),
			3
		)
	);

	const fullScreenMesh = new Mesh( fullScreenTri, shadowMaterialVertical );

	const scope = this;

	this.enabled = false;

	this.autoUpdate = true;
	this.needsUpdate = false;

	this.type = PCFShadowMap;
	let _previousType = this.type;

	this.render = function ( lights, scene, camera ) {

		if ( scope.enabled === false ) return;
		if ( scope.autoUpdate === false && scope.needsUpdate === false ) return;

		if ( lights.length === 0 ) return;

		const currentRenderTarget = renderer.getRenderTarget();
		const activeCubeFace = renderer.getActiveCubeFace();
		const activeMipmapLevel = renderer.getActiveMipmapLevel();

		const _state = renderer.state;

		// Set GL state for depth map.
		_state.setBlending( NoBlending );

		if ( _state.buffers.depth.getReversed() === true ) {

			_state.buffers.color.setClear( 0, 0, 0, 0 );

		} else {

			_state.buffers.color.setClear( 1, 1, 1, 1 );

		}

		_state.buffers.depth.setTest( true );
		_state.setScissorTest( false );

		// check for shadow map type changes

		const toVSM = ( _previousType !== VSMShadowMap && this.type === VSMShadowMap );
		const fromVSM = ( _previousType === VSMShadowMap && this.type !== VSMShadowMap );

		// render depth map

		for ( let i = 0, il = lights.length; i < il; i ++ ) {

			const light = lights[ i ];
			const shadow = light.shadow;

			if ( shadow === undefined ) {

				console.warn( 'THREE.WebGLShadowMap:', light, 'has no shadow.' );
				continue;

			}

			if ( shadow.autoUpdate === false && shadow.needsUpdate === false ) continue;

			_shadowMapSize.copy( shadow.mapSize );

			const shadowFrameExtents = shadow.getFrameExtents();

			_shadowMapSize.multiply( shadowFrameExtents );

			_viewportSize.copy( shadow.mapSize );

			if ( _shadowMapSize.x > _maxTextureSize || _shadowMapSize.y > _maxTextureSize ) {

				if ( _shadowMapSize.x > _maxTextureSize ) {

					_viewportSize.x = Math.floor( _maxTextureSize / shadowFrameExtents.x );
					_shadowMapSize.x = _viewportSize.x * shadowFrameExtents.x;
					shadow.mapSize.x = _viewportSize.x;

				}

				if ( _shadowMapSize.y > _maxTextureSize ) {

					_viewportSize.y = Math.floor( _maxTextureSize / shadowFrameExtents.y );
					_shadowMapSize.y = _viewportSize.y * shadowFrameExtents.y;
					shadow.mapSize.y = _viewportSize.y;

				}

			}

			if ( shadow.map === null || toVSM === true || fromVSM === true ) {

				const pars = ( this.type !== VSMShadowMap ) ? { minFilter: NearestFilter, magFilter: NearestFilter } : {};

				if ( shadow.map !== null ) {

					shadow.map.dispose();

				}

				shadow.map = new WebGLRenderTarget( _shadowMapSize.x, _shadowMapSize.y, pars );
				shadow.map.texture.name = light.name + '.shadowMap';

				shadow.camera.updateProjectionMatrix();

			}

			renderer.setRenderTarget( shadow.map );
			renderer.clear();

			const viewportCount = shadow.getViewportCount();

			for ( let vp = 0; vp < viewportCount; vp ++ ) {

				const viewport = shadow.getViewport( vp );

				_viewport.set(
					_viewportSize.x * viewport.x,
					_viewportSize.y * viewport.y,
					_viewportSize.x * viewport.z,
					_viewportSize.y * viewport.w
				);

				_state.viewport( _viewport );

				shadow.updateMatrices( light, vp );

				_frustum = shadow.getFrustum();

				renderObject( scene, camera, shadow.camera, light, this.type );

			}

			// do blur pass for VSM

			if ( shadow.isPointLightShadow !== true && this.type === VSMShadowMap ) {

				VSMPass( shadow, camera );

			}

			shadow.needsUpdate = false;

		}

		_previousType = this.type;

		scope.needsUpdate = false;

		renderer.setRenderTarget( currentRenderTarget, activeCubeFace, activeMipmapLevel );

	};

	function VSMPass( shadow, camera ) {

		const geometry = objects.update( fullScreenMesh );

		if ( shadowMaterialVertical.defines.VSM_SAMPLES !== shadow.blurSamples ) {

			shadowMaterialVertical.defines.VSM_SAMPLES = shadow.blurSamples;
			shadowMaterialHorizontal.defines.VSM_SAMPLES = shadow.blurSamples;

			shadowMaterialVertical.needsUpdate = true;
			shadowMaterialHorizontal.needsUpdate = true;

		}

		if ( shadow.mapPass === null ) {

			shadow.mapPass = new WebGLRenderTarget( _shadowMapSize.x, _shadowMapSize.y );

		}

		// vertical pass

		shadowMaterialVertical.uniforms.shadow_pass.value = shadow.map.texture;
		shadowMaterialVertical.uniforms.resolution.value = shadow.mapSize;
		shadowMaterialVertical.uniforms.radius.value = shadow.radius;
		renderer.setRenderTarget( shadow.mapPass );
		renderer.clear();
		renderer.renderBufferDirect( camera, null, geometry, shadowMaterialVertical, fullScreenMesh, null );

		// horizontal pass

		shadowMaterialHorizontal.uniforms.shadow_pass.value = shadow.mapPass.texture;
		shadowMaterialHorizontal.uniforms.resolution.value = shadow.mapSize;
		shadowMaterialHorizontal.uniforms.radius.value = shadow.radius;
		renderer.setRenderTarget( shadow.map );
		renderer.clear();
		renderer.renderBufferDirect( camera, null, geometry, shadowMaterialHorizontal, fullScreenMesh, null );

	}

	function getDepthMaterial( object, material, light, type ) {

		let result = null;

		const customMaterial = ( light.isPointLight === true ) ? object.customDistanceMaterial : object.customDepthMaterial;

		if ( customMaterial !== undefined ) {

			result = customMaterial;

		} else {

			result = ( light.isPointLight === true ) ? _distanceMaterial : _depthMaterial;

			if ( ( renderer.localClippingEnabled && material.clipShadows === true && Array.isArray( material.clippingPlanes ) && material.clippingPlanes.length !== 0 ) ||
				( material.displacementMap && material.displacementScale !== 0 ) ||
				( material.alphaMap && material.alphaTest > 0 ) ||
				( material.map && material.alphaTest > 0 ) ||
				( material.alphaToCoverage === true ) ) {

				// in this case we need a unique material instance reflecting the
				// appropriate state

				const keyA = result.uuid, keyB = material.uuid;

				let materialsForVariant = _materialCache[ keyA ];

				if ( materialsForVariant === undefined ) {

					materialsForVariant = {};
					_materialCache[ keyA ] = materialsForVariant;

				}

				let cachedMaterial = materialsForVariant[ keyB ];

				if ( cachedMaterial === undefined ) {

					cachedMaterial = result.clone();
					materialsForVariant[ keyB ] = cachedMaterial;
					material.addEventListener( 'dispose', onMaterialDispose );

				}

				result = cachedMaterial;

			}

		}

		result.visible = material.visible;
		result.wireframe = material.wireframe;

		if ( type === VSMShadowMap ) {

			result.side = ( material.shadowSide !== null ) ? material.shadowSide : material.side;

		} else {

			result.side = ( material.shadowSide !== null ) ? material.shadowSide : shadowSide[ material.side ];

		}

		result.alphaMap = material.alphaMap;
		result.alphaTest = ( material.alphaToCoverage === true ) ? 0.5 : material.alphaTest; // approximate alphaToCoverage by using a fixed alphaTest value
		result.map = material.map;

		result.clipShadows = material.clipShadows;
		result.clippingPlanes = material.clippingPlanes;
		result.clipIntersection = material.clipIntersection;

		result.displacementMap = material.displacementMap;
		result.displacementScale = material.displacementScale;
		result.displacementBias = material.displacementBias;

		result.wireframeLinewidth = material.wireframeLinewidth;
		result.linewidth = material.linewidth;

		if ( light.isPointLight === true && result.isMeshDistanceMaterial === true ) {

			const materialProperties = renderer.properties.get( result );
			materialProperties.light = light;

		}

		return result;

	}

	function renderObject( object, camera, shadowCamera, light, type ) {

		if ( object.visible === false ) return;

		const visible = object.layers.test( camera.layers );

		if ( visible && ( object.isMesh || object.isLine || object.isPoints ) ) {

			if ( ( object.castShadow || ( object.receiveShadow && type === VSMShadowMap ) ) && ( ! object.frustumCulled || _frustum.intersectsObject( object ) ) ) {

				object.modelViewMatrix.multiplyMatrices( shadowCamera.matrixWorldInverse, object.matrixWorld );

				const geometry = objects.update( object );
				const material = object.material;

				if ( Array.isArray( material ) ) {

					const groups = geometry.groups;

					for ( let k = 0, kl = groups.length; k < kl; k ++ ) {

						const group = groups[ k ];
						const groupMaterial = material[ group.materialIndex ];

						if ( groupMaterial && groupMaterial.visible ) {

							const depthMaterial = getDepthMaterial( object, groupMaterial, light, type );

							object.onBeforeShadow( renderer, object, camera, shadowCamera, geometry, depthMaterial, group );

							renderer.renderBufferDirect( shadowCamera, null, geometry, depthMaterial, object, group );

							object.onAfterShadow( renderer, object, camera, shadowCamera, geometry, depthMaterial, group );

						}

					}

				} else if ( material.visible ) {

					const depthMaterial = getDepthMaterial( object, material, light, type );

					object.onBeforeShadow( renderer, object, camera, shadowCamera, geometry, depthMaterial, null );

					renderer.renderBufferDirect( shadowCamera, null, geometry, depthMaterial, object, null );

					object.onAfterShadow( renderer, object, camera, shadowCamera, geometry, depthMaterial, null );

				}

			}

		}

		const children = object.children;

		for ( let i = 0, l = children.length; i < l; i ++ ) {

			renderObject( children[ i ], camera, shadowCamera, light, type );

		}

	}

	function onMaterialDispose( event ) {

		const material = event.target;

		material.removeEventListener( 'dispose', onMaterialDispose );

		// make sure to remove the unique distance/depth materials used for shadow map rendering

		for ( const id in _materialCache ) {

			const cache = _materialCache[ id ];

			const uuid = event.target.uuid;

			if ( uuid in cache ) {

				const shadowMaterial = cache[ uuid ];
				shadowMaterial.dispose();
				delete cache[ uuid ];

			}

		}

	}

}
```
</details>

### `VSMPass(shadow: any, camera: any): void`

**Parameters:**

- **`shadow`** `any`
- **`camera`** `any`

**Returns:** `void`

**Calls:**

- `objects.update`
- `renderer.setRenderTarget`
- `renderer.clear`
- `renderer.renderBufferDirect`

**Internal Comments:**
```
// vertical pass (x6)
// horizontal pass (x6)
```

<details><summary>Code</summary>

```typescript
function VSMPass( shadow, camera ) {

		const geometry = objects.update( fullScreenMesh );

		if ( shadowMaterialVertical.defines.VSM_SAMPLES !== shadow.blurSamples ) {

			shadowMaterialVertical.defines.VSM_SAMPLES = shadow.blurSamples;
			shadowMaterialHorizontal.defines.VSM_SAMPLES = shadow.blurSamples;

			shadowMaterialVertical.needsUpdate = true;
			shadowMaterialHorizontal.needsUpdate = true;

		}

		if ( shadow.mapPass === null ) {

			shadow.mapPass = new WebGLRenderTarget( _shadowMapSize.x, _shadowMapSize.y );

		}

		// vertical pass

		shadowMaterialVertical.uniforms.shadow_pass.value = shadow.map.texture;
		shadowMaterialVertical.uniforms.resolution.value = shadow.mapSize;
		shadowMaterialVertical.uniforms.radius.value = shadow.radius;
		renderer.setRenderTarget( shadow.mapPass );
		renderer.clear();
		renderer.renderBufferDirect( camera, null, geometry, shadowMaterialVertical, fullScreenMesh, null );

		// horizontal pass

		shadowMaterialHorizontal.uniforms.shadow_pass.value = shadow.mapPass.texture;
		shadowMaterialHorizontal.uniforms.resolution.value = shadow.mapSize;
		shadowMaterialHorizontal.uniforms.radius.value = shadow.radius;
		renderer.setRenderTarget( shadow.map );
		renderer.clear();
		renderer.renderBufferDirect( camera, null, geometry, shadowMaterialHorizontal, fullScreenMesh, null );

	}
```
</details>

### `getDepthMaterial(object: any, material: any, light: any, type: any): any`

**Parameters:**

- **`object`** `any`
- **`material`** `any`
- **`light`** `any`
- **`type`** `any`

**Returns:** `any`

**Calls:**

- `Array.isArray`
- `result.clone`
- `material.addEventListener`
- `renderer.properties.get`

**Internal Comments:**
```
// in this case we need a unique material instance reflecting the (x2)
// appropriate state (x2)
```

<details><summary>Code</summary>

```typescript
function getDepthMaterial( object, material, light, type ) {

		let result = null;

		const customMaterial = ( light.isPointLight === true ) ? object.customDistanceMaterial : object.customDepthMaterial;

		if ( customMaterial !== undefined ) {

			result = customMaterial;

		} else {

			result = ( light.isPointLight === true ) ? _distanceMaterial : _depthMaterial;

			if ( ( renderer.localClippingEnabled && material.clipShadows === true && Array.isArray( material.clippingPlanes ) && material.clippingPlanes.length !== 0 ) ||
				( material.displacementMap && material.displacementScale !== 0 ) ||
				( material.alphaMap && material.alphaTest > 0 ) ||
				( material.map && material.alphaTest > 0 ) ||
				( material.alphaToCoverage === true ) ) {

				// in this case we need a unique material instance reflecting the
				// appropriate state

				const keyA = result.uuid, keyB = material.uuid;

				let materialsForVariant = _materialCache[ keyA ];

				if ( materialsForVariant === undefined ) {

					materialsForVariant = {};
					_materialCache[ keyA ] = materialsForVariant;

				}

				let cachedMaterial = materialsForVariant[ keyB ];

				if ( cachedMaterial === undefined ) {

					cachedMaterial = result.clone();
					materialsForVariant[ keyB ] = cachedMaterial;
					material.addEventListener( 'dispose', onMaterialDispose );

				}

				result = cachedMaterial;

			}

		}

		result.visible = material.visible;
		result.wireframe = material.wireframe;

		if ( type === VSMShadowMap ) {

			result.side = ( material.shadowSide !== null ) ? material.shadowSide : material.side;

		} else {

			result.side = ( material.shadowSide !== null ) ? material.shadowSide : shadowSide[ material.side ];

		}

		result.alphaMap = material.alphaMap;
		result.alphaTest = ( material.alphaToCoverage === true ) ? 0.5 : material.alphaTest; // approximate alphaToCoverage by using a fixed alphaTest value
		result.map = material.map;

		result.clipShadows = material.clipShadows;
		result.clippingPlanes = material.clippingPlanes;
		result.clipIntersection = material.clipIntersection;

		result.displacementMap = material.displacementMap;
		result.displacementScale = material.displacementScale;
		result.displacementBias = material.displacementBias;

		result.wireframeLinewidth = material.wireframeLinewidth;
		result.linewidth = material.linewidth;

		if ( light.isPointLight === true && result.isMeshDistanceMaterial === true ) {

			const materialProperties = renderer.properties.get( result );
			materialProperties.light = light;

		}

		return result;

	}
```
</details>

### `renderObject(object: any, camera: any, shadowCamera: any, light: any, type: any): void`

**Parameters:**

- **`object`** `any`
- **`camera`** `any`
- **`shadowCamera`** `any`
- **`light`** `any`
- **`type`** `any`

**Returns:** `void`

**Calls:**

- `object.layers.test`
- `_frustum.intersectsObject`
- `object.modelViewMatrix.multiplyMatrices`
- `objects.update`
- `Array.isArray`
- `getDepthMaterial`
- `object.onBeforeShadow`
- `renderer.renderBufferDirect`
- `object.onAfterShadow`
- `renderObject`

<details><summary>Code</summary>

```typescript
function renderObject( object, camera, shadowCamera, light, type ) {

		if ( object.visible === false ) return;

		const visible = object.layers.test( camera.layers );

		if ( visible && ( object.isMesh || object.isLine || object.isPoints ) ) {

			if ( ( object.castShadow || ( object.receiveShadow && type === VSMShadowMap ) ) && ( ! object.frustumCulled || _frustum.intersectsObject( object ) ) ) {

				object.modelViewMatrix.multiplyMatrices( shadowCamera.matrixWorldInverse, object.matrixWorld );

				const geometry = objects.update( object );
				const material = object.material;

				if ( Array.isArray( material ) ) {

					const groups = geometry.groups;

					for ( let k = 0, kl = groups.length; k < kl; k ++ ) {

						const group = groups[ k ];
						const groupMaterial = material[ group.materialIndex ];

						if ( groupMaterial && groupMaterial.visible ) {

							const depthMaterial = getDepthMaterial( object, groupMaterial, light, type );

							object.onBeforeShadow( renderer, object, camera, shadowCamera, geometry, depthMaterial, group );

							renderer.renderBufferDirect( shadowCamera, null, geometry, depthMaterial, object, group );

							object.onAfterShadow( renderer, object, camera, shadowCamera, geometry, depthMaterial, group );

						}

					}

				} else if ( material.visible ) {

					const depthMaterial = getDepthMaterial( object, material, light, type );

					object.onBeforeShadow( renderer, object, camera, shadowCamera, geometry, depthMaterial, null );

					renderer.renderBufferDirect( shadowCamera, null, geometry, depthMaterial, object, null );

					object.onAfterShadow( renderer, object, camera, shadowCamera, geometry, depthMaterial, null );

				}

			}

		}

		const children = object.children;

		for ( let i = 0, l = children.length; i < l; i ++ ) {

			renderObject( children[ i ], camera, shadowCamera, light, type );

		}

	}
```
</details>

### `onMaterialDispose(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `material.removeEventListener`
- `shadowMaterial.dispose`

**Internal Comments:**
```
// make sure to remove the unique distance/depth materials used for shadow map rendering
```

<details><summary>Code</summary>

```typescript
function onMaterialDispose( event ) {

		const material = event.target;

		material.removeEventListener( 'dispose', onMaterialDispose );

		// make sure to remove the unique distance/depth materials used for shadow map rendering

		for ( const id in _materialCache ) {

			const cache = _materialCache[ id ];

			const uuid = event.target.uuid;

			if ( uuid in cache ) {

				const shadowMaterial = cache[ uuid ];
				shadowMaterial.dispose();
				delete cache[ uuid ];

			}

		}

	}
```
</details>


---