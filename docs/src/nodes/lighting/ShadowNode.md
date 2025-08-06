[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ShadowNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 13 |
| 🧱 Classes | 1 |
| 📦 Imports | 36 |
| 📊 Variables & Constants | 20 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/ShadowNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `shadowPositionWorld` | `./ShadowBaseNode.js` |
| `ShadowBaseNode` | `./ShadowBaseNode.js` |
| `float` | `../tsl/TSLBase.js` |
| `vec2` | `../tsl/TSLBase.js` |
| `vec3` | `../tsl/TSLBase.js` |
| `int` | `../tsl/TSLBase.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `nodeObject` | `../tsl/TSLBase.js` |
| `reference` | `../accessors/ReferenceNode.js` |
| `texture` | `../accessors/TextureNode.js` |
| `normalWorld` | `../accessors/Normal.js` |
| `mix` | `../math/MathNode.js` |
| `sqrt` | `../math/MathNode.js` |
| `add` | `../math/OperatorNode.js` |
| `DepthTexture` | `../../textures/DepthTexture.js` |
| `NodeMaterial` | `../../materials/nodes/NodeMaterial.js` |
| `QuadMesh` | `../../renderers/common/QuadMesh.js` |
| `Loop` | `../utils/LoopNode.js` |
| `screenCoordinate` | `../display/ScreenNode.js` |
| `HalfFloatType` | `../../constants.js` |
| `LessCompare` | `../../constants.js` |
| `RGFormat` | `../../constants.js` |
| `VSMShadowMap` | `../../constants.js` |
| `WebGPUCoordinateSystem` | `../../constants.js` |
| `renderGroup` | `../core/UniformGroupNode.js` |
| `viewZToLogarithmicDepth` | `../display/ViewportDepthNode.js` |
| `lightShadowMatrix` | `../accessors/Lights.js` |
| `resetRendererAndSceneState` | `../../renderers/common/RendererUtils.js` |
| `restoreRendererAndSceneState` | `../../renderers/common/RendererUtils.js` |
| `getDataFromObject` | `../core/NodeUtils.js` |
| `getShadowMaterial` | `./ShadowFilterNode.js` |
| `BasicShadowFilter` | `./ShadowFilterNode.js` |
| `PCFShadowFilter` | `./ShadowFilterNode.js` |
| `PCFSoftShadowFilter` | `./ShadowFilterNode.js` |
| `VSMShadowFilter` | `./ShadowFilterNode.js` |
| `ChainMap` | `../../renderers/common/ChainMap.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_shadowRenderObjectLibrary` | `ChainMap` | let/var | `new ChainMap()` | ✗ |
| `_shadowRenderObjectKeys` | `any[]` | let/var | `[]` | ✗ |
| `_shadowFilterLib` | `(() => void)[]` | let/var | `[ BasicShadowFilter, PCFShadowFilter, PCFSoftShadowFilter, VSMShadowFilter ]` | ✗ |
| `_rendererState` | `any` | let/var | `*not shown*` | ✗ |
| `_quadMesh` | `QuadMesh` | let/var | `new QuadMesh()` | ✗ |
| `shadowCoord` | `any` | let/var | `shadowPosition` | ✗ |
| `coordZ` | `any` | let/var | `*not shown*` | ✗ |
| `w` | `any` | let/var | `shadowCoord.w` | ✗ |
| `depthTexture` | `DepthTexture` | let/var | `new DepthTexture( shadow.mapSize.width, shadow.mapSize.height )` | ✗ |
| `shadowMapType` | `any` | let/var | `renderer.shadowMap.type` | ✗ |
| `material` | `NodeMaterial` | let/var | `this.vsmMaterialVertical \|\| ( this.vsmMaterialVertical = new NodeMaterial() )` | ✗ |
| `filterFn` | `any` | let/var | `shadow.filterNode \|\| this.getShadowFilterFn( renderer.shadowMap.type ) \|\|...` | ✗ |
| `shadowDepthTexture` | `any` | let/var | `( shadowMapType === VSMShadowMap && shadow.isPointLightShadow !== true ) ? th...` | ✗ |
| `node` | `Node` | let/var | `this._node` | ✗ |
| `shadowType` | `any` | let/var | `renderer.shadowMap.type` | ✗ |
| `depthVersion` | `any` | let/var | `shadowMap.depthTexture.version` | ✗ |
| `_shadowCameraLayer` | `any` | let/var | `shadow.camera.layers.mask` | ✗ |
| `useVelocity` | `any` | let/var | `currentMRT ? currentMRT.has( 'velocity' ) : false` | ✗ |
| `depth` | `any` | let/var | `this.shadowMap.depth` | ✗ |
| `needsUpdate` | `any` | let/var | `shadow.needsUpdate \|\| shadow.autoUpdate` | ✗ |


---

## Functions

### `getShadowRenderObjectFunction(renderer: Renderer, shadow: LightShadow, shadowType: number, useVelocity: boolean): Function`

**Parameters:**

- **`renderer`** `Renderer`
- **`shadow`** `LightShadow`
- **`shadowType`** `number`
- **`useVelocity`** `boolean`

**Returns:** `Function`

**Calls:**

- `_shadowRenderObjectLibrary.get`
- `getDataFromObject (from ../core/NodeUtils.js)`
- `object.onBeforeShadow`
- `renderer.renderObject`
- `object.onAfterShadow`
- `_shadowRenderObjectLibrary.set`

<details><summary>Code</summary>

```typescript
( renderer, shadow, shadowType, useVelocity ) => {

	_shadowRenderObjectKeys[ 0 ] = renderer;
	_shadowRenderObjectKeys[ 1 ] = shadow;

	let renderObjectFunction = _shadowRenderObjectLibrary.get( _shadowRenderObjectKeys );

	if ( renderObjectFunction === undefined || ( renderObjectFunction.shadowType !== shadowType || renderObjectFunction.useVelocity !== useVelocity ) ) {

		renderObjectFunction = ( object, scene, _camera, geometry, material, group, ...params ) => {

			if ( object.castShadow === true || ( object.receiveShadow && shadowType === VSMShadowMap ) ) {

				if ( useVelocity ) {

					getDataFromObject( object ).useVelocity = true;

				}

				object.onBeforeShadow( renderer, object, _camera, shadow.camera, geometry, scene.overrideMaterial, group );

				renderer.renderObject( object, scene, _camera, geometry, material, group, ...params );

				object.onAfterShadow( renderer, object, _camera, shadow.camera, geometry, scene.overrideMaterial, group );

			}

		};

		renderObjectFunction.shadowType = shadowType;
		renderObjectFunction.useVelocity = useVelocity;

		_shadowRenderObjectLibrary.set( _shadowRenderObjectKeys, renderObjectFunction );

	}

	_shadowRenderObjectKeys[ 0 ] = null;
	_shadowRenderObjectKeys[ 1 ] = null;

	return renderObjectFunction;

}
```
</details>

### `ShadowNode.setupShadowFilter(builder: NodeBuilder, { filterFn, depthTexture, shadowCoord, shadow, depthLayer }: any): any`

**JSDoc:**
```typescript
/**
	 * Setups the shadow filtering.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @param {Object} inputs - A configuration object that defines the shadow filtering.
	 * @param {Function} inputs.filterFn - This function defines the filtering type of the shadow map e.g. PCF.
	 * @param {DepthTexture} inputs.depthTexture - A reference to the shadow map's texture data.
	 * @param {Node<vec3>} inputs.shadowCoord - Shadow coordinates which are used to sample from the shadow map.
	 * @param {LightShadow} inputs.shadow - The light shadow.
	 * @return {Node<float>} The result node of the shadow filtering.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`{ filterFn, depthTexture, shadowCoord, shadow, depthLayer }`** `any`

**Returns:** `any`

**Calls:**

- `shadowCoord.x.greaterThanEqual( 0 )
			.and( shadowCoord.x.lessThanEqual( 1 ) )
			.and( shadowCoord.y.greaterThanEqual( 0 ) )
			.and( shadowCoord.y.lessThanEqual( 1 ) )
			.and`
- `shadowCoord.z.lessThanEqual`
- `filterFn`
- `frustumTest.select`
- `float (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
setupShadowFilter( builder, { filterFn, depthTexture, shadowCoord, shadow, depthLayer } ) {

		const frustumTest = shadowCoord.x.greaterThanEqual( 0 )
			.and( shadowCoord.x.lessThanEqual( 1 ) )
			.and( shadowCoord.y.greaterThanEqual( 0 ) )
			.and( shadowCoord.y.lessThanEqual( 1 ) )
			.and( shadowCoord.z.lessThanEqual( 1 ) );

		const shadowNode = filterFn( { depthTexture, shadowCoord, shadow, depthLayer } );

		return frustumTest.select( shadowNode, float( 1 ) );

	}
```
</details>

### `ShadowNode.setupShadowCoord(builder: NodeBuilder, shadowPosition: any): any`

**JSDoc:**
```typescript
/**
	 * Setups the shadow coordinates.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @param {Node<vec3>} shadowPosition - A node representing the shadow position.
	 * @return {Node<vec3>} The shadow coordinates.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`shadowPosition`** `any`

**Returns:** `any`

**Calls:**

- `reference( 'bias', 'float', shadow ).setGroup`
- `shadowCoord.xyz.div`
- `coordZ.mul( 2 ).sub`
- `shadowCoord.xy.div`
- `reference( 'near', 'float', shadow.camera ).setGroup`
- `reference( 'far', 'float', shadow.camera ).setGroup`
- `viewZToLogarithmicDepth (from ../display/ViewportDepthNode.js)`
- `w.negate`
- `vec3 (from ../tsl/TSLBase.js)`
- `shadowCoord.y.oneMinus`
- `coordZ.add`

**Internal Comments:**
```
// The normally available "cameraNear" and "cameraFar" nodes cannot be used here because they do not get (x2)
// updated to use the shadow camera. So, we have to declare our own "local" ones here. (x2)
// TODO: How do we get the cameraNear/cameraFar nodes to use the shadow camera so we don't have to declare local ones here? (x2)
```

<details><summary>Code</summary>

```typescript
setupShadowCoord( builder, shadowPosition ) {

		const { shadow } = this;
		const { renderer } = builder;

		const bias = reference( 'bias', 'float', shadow ).setGroup( renderGroup );

		let shadowCoord = shadowPosition;
		let coordZ;

		if ( shadow.camera.isOrthographicCamera || renderer.logarithmicDepthBuffer !== true ) {

			shadowCoord = shadowCoord.xyz.div( shadowCoord.w );

			coordZ = shadowCoord.z;

			if ( renderer.coordinateSystem === WebGPUCoordinateSystem ) {

				coordZ = coordZ.mul( 2 ).sub( 1 ); // WebGPU: Conversion [ 0, 1 ] to [ - 1, 1 ]

			}

		} else {

			const w = shadowCoord.w;
			shadowCoord = shadowCoord.xy.div( w ); // <-- Only divide X/Y coords since we don't need Z

			// The normally available "cameraNear" and "cameraFar" nodes cannot be used here because they do not get
			// updated to use the shadow camera. So, we have to declare our own "local" ones here.
			// TODO: How do we get the cameraNear/cameraFar nodes to use the shadow camera so we don't have to declare local ones here?
			const cameraNearLocal = reference( 'near', 'float', shadow.camera ).setGroup( renderGroup );
			const cameraFarLocal = reference( 'far', 'float', shadow.camera ).setGroup( renderGroup );

			coordZ = viewZToLogarithmicDepth( w.negate(), cameraNearLocal, cameraFarLocal );

		}

		shadowCoord = vec3(
			shadowCoord.x,
			shadowCoord.y.oneMinus(), // follow webgpu standards
			coordZ.add( bias )
		);

		return shadowCoord;

	}
```
</details>

### `ShadowNode.getShadowFilterFn(type: number): Function`

**JSDoc:**
```typescript
/**
	 * Returns the shadow filtering function for the given shadow type.
	 *
	 * @param {number} type - The shadow type.
	 * @return {Function} The filtering function.
	 */
```

**Parameters:**

- **`type`** `number`

**Returns:** `Function`

<details><summary>Code</summary>

```typescript
getShadowFilterFn( type ) {

		return _shadowFilterLib[ type ];

	}
```
</details>

### `ShadowNode.setupRenderTarget(shadow: any, builder: any): { shadowMap: any; depthTexture: DepthTexture; }`

**Parameters:**

- **`shadow`** `any`
- **`builder`** `any`

**Returns:** `{ shadowMap: any; depthTexture: DepthTexture; }`

**Calls:**

- `builder.createRenderTarget`

<details><summary>Code</summary>

```typescript
setupRenderTarget( shadow, builder ) {

		const depthTexture = new DepthTexture( shadow.mapSize.width, shadow.mapSize.height );
		depthTexture.name = 'ShadowDepthTexture';
		depthTexture.compareFunction = LessCompare;

		const shadowMap = builder.createRenderTarget( shadow.mapSize.width, shadow.mapSize.height );
		shadowMap.texture.name = 'ShadowMap';
		shadowMap.texture.type = shadow.mapType;
		shadowMap.depthTexture = depthTexture;

		return { shadowMap, depthTexture };

	}
```
</details>

### `ShadowNode.setupShadow(builder: NodeBuilder): any`

**JSDoc:**
```typescript
/**
	 * Setups the shadow output node.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @return {Node<vec3>} The shadow output node.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `any`

**Calls:**

- `this.setupRenderTarget`
- `shadow.camera.updateProjectionMatrix`
- `builder.createRenderTarget`
- `texture (from ../accessors/TextureNode.js)`
- `shadowPassVertical.depth`
- `shadowPassHorizontal.depth`
- `reference( 'blurSamples', 'float', shadow ).setGroup`
- `reference( 'radius', 'float', shadow ).setGroup`
- `reference( 'mapSize', 'vec2', shadow ).setGroup`
- `VSMPassVertical( { samples, radius, size, shadowPass: shadowPassVertical, depthLayer: this.depthLayer } ).context`
- `builder.getSharedContext`
- `VSMPassHorizontal( { samples, radius, size, shadowPass: shadowPassHorizontal, depthLayer: this.depthLayer } ).context`
- `reference( 'intensity', 'float', shadow ).setGroup`
- `reference( 'normalBias', 'float', shadow ).setGroup`
- `lightShadowMatrix( light ).mul`
- `shadowPositionWorld.add`
- `normalWorld.mul`
- `this.setupShadowCoord`
- `this.getShadowFilterFn`
- `this.setupShadowFilter`
- `shadowColor.depth`
- `mix( 1, shadowNode.rgb.mix( shadowColor, 1 ), shadowIntensity.mul( shadowColor.a ) ).toVar`

**Internal Comments:**
```
// VSM
// (x4)
```

<details><summary>Code</summary>

```typescript
setupShadow( builder ) {

		const { renderer } = builder;

		const { light, shadow } = this;

		const shadowMapType = renderer.shadowMap.type;

		const { depthTexture, shadowMap } = this.setupRenderTarget( shadow, builder );

		shadow.camera.updateProjectionMatrix();

		// VSM

		if ( shadowMapType === VSMShadowMap && shadow.isPointLightShadow !== true ) {

			depthTexture.compareFunction = null; // VSM does not use textureSampleCompare()/texture2DCompare()

			if ( shadowMap.depth > 1 ) {

				if ( ! shadowMap._vsmShadowMapVertical ) {

					shadowMap._vsmShadowMapVertical = builder.createRenderTarget( shadow.mapSize.width, shadow.mapSize.height, { format: RGFormat, type: HalfFloatType, depth: shadowMap.depth, depthBuffer: false } );
					shadowMap._vsmShadowMapVertical.texture.name = 'VSMVertical';

				}

				this.vsmShadowMapVertical = shadowMap._vsmShadowMapVertical;

				if ( ! shadowMap._vsmShadowMapHorizontal ) {

					shadowMap._vsmShadowMapHorizontal = builder.createRenderTarget( shadow.mapSize.width, shadow.mapSize.height, { format: RGFormat, type: HalfFloatType, depth: shadowMap.depth, depthBuffer: false } );
					shadowMap._vsmShadowMapHorizontal.texture.name = 'VSMHorizontal';

				}

				this.vsmShadowMapHorizontal = shadowMap._vsmShadowMapHorizontal;

			} else {

				this.vsmShadowMapVertical = builder.createRenderTarget( shadow.mapSize.width, shadow.mapSize.height, { format: RGFormat, type: HalfFloatType, depthBuffer: false } );
				this.vsmShadowMapHorizontal = builder.createRenderTarget( shadow.mapSize.width, shadow.mapSize.height, { format: RGFormat, type: HalfFloatType, depthBuffer: false } );

			}


			let shadowPassVertical = texture( depthTexture );

			if ( depthTexture.isArrayTexture ) {

				shadowPassVertical = shadowPassVertical.depth( this.depthLayer );

			}

			let shadowPassHorizontal = texture( this.vsmShadowMapVertical.texture );

			if ( depthTexture.isArrayTexture ) {

				shadowPassHorizontal = shadowPassHorizontal.depth( this.depthLayer );

			}

			const samples = reference( 'blurSamples', 'float', shadow ).setGroup( renderGroup );
			const radius = reference( 'radius', 'float', shadow ).setGroup( renderGroup );
			const size = reference( 'mapSize', 'vec2', shadow ).setGroup( renderGroup );

			let material = this.vsmMaterialVertical || ( this.vsmMaterialVertical = new NodeMaterial() );
			material.fragmentNode = VSMPassVertical( { samples, radius, size, shadowPass: shadowPassVertical, depthLayer: this.depthLayer } ).context( builder.getSharedContext() );
			material.name = 'VSMVertical';

			material = this.vsmMaterialHorizontal || ( this.vsmMaterialHorizontal = new NodeMaterial() );
			material.fragmentNode = VSMPassHorizontal( { samples, radius, size, shadowPass: shadowPassHorizontal, depthLayer: this.depthLayer } ).context( builder.getSharedContext() );
			material.name = 'VSMHorizontal';

		}

		//

		const shadowIntensity = reference( 'intensity', 'float', shadow ).setGroup( renderGroup );
		const normalBias = reference( 'normalBias', 'float', shadow ).setGroup( renderGroup );

		const shadowPosition = lightShadowMatrix( light ).mul( shadowPositionWorld.add( normalWorld.mul( normalBias ) ) );
		const shadowCoord = this.setupShadowCoord( builder, shadowPosition );

		//

		const filterFn = shadow.filterNode || this.getShadowFilterFn( renderer.shadowMap.type ) || null;

		if ( filterFn === null ) {

			throw new Error( 'THREE.WebGPURenderer: Shadow map type not supported yet.' );

		}

		const shadowDepthTexture = ( shadowMapType === VSMShadowMap && shadow.isPointLightShadow !== true ) ? this.vsmShadowMapHorizontal.texture : depthTexture;

		const shadowNode = this.setupShadowFilter( builder, { filterFn, shadowTexture: shadowMap.texture, depthTexture: shadowDepthTexture, shadowCoord, shadow, depthLayer: this.depthLayer } );

		let shadowColor = texture( shadowMap.texture, shadowCoord );

		if ( depthTexture.isArrayTexture ) {

			shadowColor = shadowColor.depth( this.depthLayer );

		}

		const shadowOutput = mix( 1, shadowNode.rgb.mix( shadowColor, 1 ), shadowIntensity.mul( shadowColor.a ) ).toVar();

		this.shadowMap = shadowMap;
		this.shadow.map = shadowMap;

		return shadowOutput;

	}
```
</details>

### `ShadowNode.setup(builder: NodeBuilder): ShaderCallNodeInternal`

**JSDoc:**
```typescript
/**
	 * The implementation performs the setup of the output node. An output is only
	 * produces if shadow mapping is globally enabled in the renderer.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @return {ShaderCallNodeInternal} The output node.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `ShaderCallNodeInternal`

**Calls:**

- `complex_call_17378`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		if ( builder.renderer.shadowMap.enabled === false ) return;

		return Fn( () => {

			let node = this._node;

			this.setupShadowPosition( builder );

			if ( node === null ) {

				this._node = node = this.setupShadow( builder );

			}

			if ( builder.material.shadowNode ) { // @deprecated, r171

				console.warn( 'THREE.NodeMaterial: ".shadowNode" is deprecated. Use ".castShadowNode" instead.' );

			}

			if ( builder.material.receivedShadowNode ) {

				node = builder.material.receivedShadowNode( node );

			}

			return node;

		} )();

	}
```
</details>

### `ShadowNode.renderShadow(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
	 * Renders the shadow. The logic of this function could be included
	 * into {@link ShadowNode#updateShadow} however more specialized shadow
	 * nodes might require a custom shadow map rendering. By having a
	 * dedicated method, it's easier to overwrite the default behavior.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
```

**Parameters:**

- **`frame`** `NodeFrame`

**Returns:** `void`

**Calls:**

- `shadow.updateMatrices`
- `shadowMap.setSize`
- `renderer.render`

<details><summary>Code</summary>

```typescript
renderShadow( frame ) {

		const { shadow, shadowMap, light } = this;
		const { renderer, scene } = frame;

		shadow.updateMatrices( light );

		shadowMap.setSize( shadow.mapSize.width, shadow.mapSize.height, shadowMap.depth );

		renderer.render( scene, shadow.camera );

	}
```
</details>

### `ShadowNode.updateShadow(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
	 * Updates the shadow.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
```

**Parameters:**

- **`frame`** `NodeFrame`

**Returns:** `void`

**Calls:**

- `renderer.getRenderObjectFunction`
- `renderer.getMRT`
- `currentMRT.has`
- `resetRendererAndSceneState (from ../../renderers/common/RendererUtils.js)`
- `getShadowMaterial (from ./ShadowFilterNode.js)`
- `renderer.setRenderObjectFunction`
- `getShadowRenderObjectFunction`
- `renderer.setClearColor`
- `renderer.setRenderTarget`
- `this.renderShadow`
- `this.vsmPass`
- `restoreRendererAndSceneState (from ../../renderers/common/RendererUtils.js)`

**Internal Comments:**
```
// vsm blur pass
```

<details><summary>Code</summary>

```typescript
updateShadow( frame ) {

		const { shadowMap, light, shadow } = this;
		const { renderer, scene, camera } = frame;

		const shadowType = renderer.shadowMap.type;

		const depthVersion = shadowMap.depthTexture.version;
		this._depthVersionCached = depthVersion;

		const _shadowCameraLayer = shadow.camera.layers.mask;

		if ( ( shadow.camera.layers.mask & 0xFFFFFFFE ) === 0 ) {

			shadow.camera.layers.mask = camera.layers.mask;

		}

		const currentRenderObjectFunction = renderer.getRenderObjectFunction();

		const currentMRT = renderer.getMRT();
		const useVelocity = currentMRT ? currentMRT.has( 'velocity' ) : false;

		_rendererState = resetRendererAndSceneState( renderer, scene, _rendererState );

		scene.overrideMaterial = getShadowMaterial( light );

		renderer.setRenderObjectFunction( getShadowRenderObjectFunction( renderer, shadow, shadowType, useVelocity ) );

		renderer.setClearColor( 0x000000, 0 );

		renderer.setRenderTarget( shadowMap );

		this.renderShadow( frame );

		renderer.setRenderObjectFunction( currentRenderObjectFunction );

		// vsm blur pass

		if ( shadowType === VSMShadowMap && shadow.isPointLightShadow !== true ) {

			this.vsmPass( renderer );

		}

		shadow.camera.layers.mask = _shadowCameraLayer;

		restoreRendererAndSceneState( renderer, scene, _rendererState );

	}
```
</details>

### `ShadowNode.vsmPass(renderer: Renderer): void`

**JSDoc:**
```typescript
/**
	 * For VSM additional render passes are required.
	 *
	 * @param {Renderer} renderer - A reference to the current renderer.
	 */
```

**Parameters:**

- **`renderer`** `Renderer`

**Returns:** `void`

**Calls:**

- `this.vsmShadowMapVertical.setSize`
- `this.vsmShadowMapHorizontal.setSize`
- `renderer.setRenderTarget`
- `_quadMesh.render`

<details><summary>Code</summary>

```typescript
vsmPass( renderer ) {

		const { shadow } = this;

		const depth = this.shadowMap.depth;
		this.vsmShadowMapVertical.setSize( shadow.mapSize.width, shadow.mapSize.height, depth );
		this.vsmShadowMapHorizontal.setSize( shadow.mapSize.width, shadow.mapSize.height, depth );

		renderer.setRenderTarget( this.vsmShadowMapVertical );
		_quadMesh.material = this.vsmMaterialVertical;
		_quadMesh.render( renderer );

		renderer.setRenderTarget( this.vsmShadowMapHorizontal );
		_quadMesh.material = this.vsmMaterialHorizontal;
		_quadMesh.render( renderer );

	}
```
</details>

### `ShadowNode.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the internal resources of this shadow node.
	 */
```

**Returns:** `void`

**Calls:**

- `this.shadowMap.dispose`
- `this.vsmShadowMapVertical.dispose`
- `this.vsmMaterialVertical.dispose`
- `this.vsmShadowMapHorizontal.dispose`
- `this.vsmMaterialHorizontal.dispose`
- `super.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.shadowMap.dispose();
		this.shadowMap = null;

		if ( this.vsmShadowMapVertical !== null ) {

			this.vsmShadowMapVertical.dispose();
			this.vsmShadowMapVertical = null;

			this.vsmMaterialVertical.dispose();
			this.vsmMaterialVertical = null;

		}

		if ( this.vsmShadowMapHorizontal !== null ) {

			this.vsmShadowMapHorizontal.dispose();
			this.vsmShadowMapHorizontal = null;

			this.vsmMaterialHorizontal.dispose();
			this.vsmMaterialHorizontal = null;

		}

		super.dispose();

	}
```
</details>

### `ShadowNode.updateBefore(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
	 * The implementation performs the update of the shadow map if necessary.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
```

**Parameters:**

- **`frame`** `NodeFrame`

**Returns:** `void`

**Calls:**

- `this.updateShadow`

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		const { shadow } = this;

		let needsUpdate = shadow.needsUpdate || shadow.autoUpdate;

		if ( needsUpdate ) {

			if ( this._cameraFrameId[ frame.camera ] === frame.frameId ) {

				needsUpdate = false;

			}

			this._cameraFrameId[ frame.camera ] = frame.frameId;

		}

		if ( needsUpdate ) {

			this.updateShadow( frame );

			if ( this.shadowMap.depthTexture.version === this._depthVersionCached ) {

				shadow.needsUpdate = false;

			}

		}

	}
```
</details>

### `shadow(light: Light, shadow: LightShadow): ShadowNode`

**Parameters:**

- **`light`** `Light`
- **`shadow`** `LightShadow`

**Returns:** `ShadowNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( light, shadow ) => nodeObject( new ShadowNode( light, shadow ) )
```
</details>


---

## Classes

### `ShadowNode`

<details><summary>Class Code</summary>

```ts
class ShadowNode extends ShadowBaseNode {

	static get type() {

		return 'ShadowNode';

	}

	/**
	 * Constructs a new shadow node.
	 *
	 * @param {Light} light - The shadow casting light.
	 * @param {?LightShadow} [shadow=null] - An optional light shadow.
	 */
	constructor( light, shadow = null ) {

		super( light );

		/**
		 * The light shadow which defines the properties light's
		 * shadow.
		 *
		 * @type {?LightShadow}
		 * @default null
		 */
		this.shadow = shadow || light.shadow;

		/**
		 * A reference to the shadow map which is a render target.
		 *
		 * @type {?RenderTarget}
		 * @default null
		 */
		this.shadowMap = null;

		/**
		 * Only relevant for VSM shadows. Render target for the
		 * first VSM render pass.
		 *
		 * @type {?RenderTarget}
		 * @default null
		 */
		this.vsmShadowMapVertical = null;

		/**
		 * Only relevant for VSM shadows. Render target for the
		 * second VSM render pass.
		 *
		 * @type {?RenderTarget}
		 * @default null
		 */
		this.vsmShadowMapHorizontal = null;

		/**
		 * Only relevant for VSM shadows. Node material which
		 * is used to render the first VSM pass.
		 *
		 * @type {?NodeMaterial}
		 * @default null
		 */
		this.vsmMaterialVertical = null;

		/**
		 * Only relevant for VSM shadows. Node material which
		 * is used to render the second VSM pass.
		 *
		 * @type {?NodeMaterial}
		 * @default null
		 */
		this.vsmMaterialHorizontal = null;

		/**
		 * A reference to the output node which defines the
		 * final result of this shadow node.
		 *
		 * @type {?Node}
		 * @private
		 * @default null
		 */
		this._node = null;

		this._cameraFrameId = new WeakMap();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isShadowNode = true;

		/**
		 * This index can be used when overriding setupRenderTarget with a RenderTarget Array to specify the depth layer.
		 *
		 * @type {number}
		 * @readonly
		 * @default true
		 */
		this.depthLayer = 0;

	}

	/**
	 * Setups the shadow filtering.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @param {Object} inputs - A configuration object that defines the shadow filtering.
	 * @param {Function} inputs.filterFn - This function defines the filtering type of the shadow map e.g. PCF.
	 * @param {DepthTexture} inputs.depthTexture - A reference to the shadow map's texture data.
	 * @param {Node<vec3>} inputs.shadowCoord - Shadow coordinates which are used to sample from the shadow map.
	 * @param {LightShadow} inputs.shadow - The light shadow.
	 * @return {Node<float>} The result node of the shadow filtering.
	 */
	setupShadowFilter( builder, { filterFn, depthTexture, shadowCoord, shadow, depthLayer } ) {

		const frustumTest = shadowCoord.x.greaterThanEqual( 0 )
			.and( shadowCoord.x.lessThanEqual( 1 ) )
			.and( shadowCoord.y.greaterThanEqual( 0 ) )
			.and( shadowCoord.y.lessThanEqual( 1 ) )
			.and( shadowCoord.z.lessThanEqual( 1 ) );

		const shadowNode = filterFn( { depthTexture, shadowCoord, shadow, depthLayer } );

		return frustumTest.select( shadowNode, float( 1 ) );

	}

	/**
	 * Setups the shadow coordinates.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @param {Node<vec3>} shadowPosition - A node representing the shadow position.
	 * @return {Node<vec3>} The shadow coordinates.
	 */
	setupShadowCoord( builder, shadowPosition ) {

		const { shadow } = this;
		const { renderer } = builder;

		const bias = reference( 'bias', 'float', shadow ).setGroup( renderGroup );

		let shadowCoord = shadowPosition;
		let coordZ;

		if ( shadow.camera.isOrthographicCamera || renderer.logarithmicDepthBuffer !== true ) {

			shadowCoord = shadowCoord.xyz.div( shadowCoord.w );

			coordZ = shadowCoord.z;

			if ( renderer.coordinateSystem === WebGPUCoordinateSystem ) {

				coordZ = coordZ.mul( 2 ).sub( 1 ); // WebGPU: Conversion [ 0, 1 ] to [ - 1, 1 ]

			}

		} else {

			const w = shadowCoord.w;
			shadowCoord = shadowCoord.xy.div( w ); // <-- Only divide X/Y coords since we don't need Z

			// The normally available "cameraNear" and "cameraFar" nodes cannot be used here because they do not get
			// updated to use the shadow camera. So, we have to declare our own "local" ones here.
			// TODO: How do we get the cameraNear/cameraFar nodes to use the shadow camera so we don't have to declare local ones here?
			const cameraNearLocal = reference( 'near', 'float', shadow.camera ).setGroup( renderGroup );
			const cameraFarLocal = reference( 'far', 'float', shadow.camera ).setGroup( renderGroup );

			coordZ = viewZToLogarithmicDepth( w.negate(), cameraNearLocal, cameraFarLocal );

		}

		shadowCoord = vec3(
			shadowCoord.x,
			shadowCoord.y.oneMinus(), // follow webgpu standards
			coordZ.add( bias )
		);

		return shadowCoord;

	}

	/**
	 * Returns the shadow filtering function for the given shadow type.
	 *
	 * @param {number} type - The shadow type.
	 * @return {Function} The filtering function.
	 */
	getShadowFilterFn( type ) {

		return _shadowFilterLib[ type ];

	}


	setupRenderTarget( shadow, builder ) {

		const depthTexture = new DepthTexture( shadow.mapSize.width, shadow.mapSize.height );
		depthTexture.name = 'ShadowDepthTexture';
		depthTexture.compareFunction = LessCompare;

		const shadowMap = builder.createRenderTarget( shadow.mapSize.width, shadow.mapSize.height );
		shadowMap.texture.name = 'ShadowMap';
		shadowMap.texture.type = shadow.mapType;
		shadowMap.depthTexture = depthTexture;

		return { shadowMap, depthTexture };

	}

	/**
	 * Setups the shadow output node.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @return {Node<vec3>} The shadow output node.
	 */
	setupShadow( builder ) {

		const { renderer } = builder;

		const { light, shadow } = this;

		const shadowMapType = renderer.shadowMap.type;

		const { depthTexture, shadowMap } = this.setupRenderTarget( shadow, builder );

		shadow.camera.updateProjectionMatrix();

		// VSM

		if ( shadowMapType === VSMShadowMap && shadow.isPointLightShadow !== true ) {

			depthTexture.compareFunction = null; // VSM does not use textureSampleCompare()/texture2DCompare()

			if ( shadowMap.depth > 1 ) {

				if ( ! shadowMap._vsmShadowMapVertical ) {

					shadowMap._vsmShadowMapVertical = builder.createRenderTarget( shadow.mapSize.width, shadow.mapSize.height, { format: RGFormat, type: HalfFloatType, depth: shadowMap.depth, depthBuffer: false } );
					shadowMap._vsmShadowMapVertical.texture.name = 'VSMVertical';

				}

				this.vsmShadowMapVertical = shadowMap._vsmShadowMapVertical;

				if ( ! shadowMap._vsmShadowMapHorizontal ) {

					shadowMap._vsmShadowMapHorizontal = builder.createRenderTarget( shadow.mapSize.width, shadow.mapSize.height, { format: RGFormat, type: HalfFloatType, depth: shadowMap.depth, depthBuffer: false } );
					shadowMap._vsmShadowMapHorizontal.texture.name = 'VSMHorizontal';

				}

				this.vsmShadowMapHorizontal = shadowMap._vsmShadowMapHorizontal;

			} else {

				this.vsmShadowMapVertical = builder.createRenderTarget( shadow.mapSize.width, shadow.mapSize.height, { format: RGFormat, type: HalfFloatType, depthBuffer: false } );
				this.vsmShadowMapHorizontal = builder.createRenderTarget( shadow.mapSize.width, shadow.mapSize.height, { format: RGFormat, type: HalfFloatType, depthBuffer: false } );

			}


			let shadowPassVertical = texture( depthTexture );

			if ( depthTexture.isArrayTexture ) {

				shadowPassVertical = shadowPassVertical.depth( this.depthLayer );

			}

			let shadowPassHorizontal = texture( this.vsmShadowMapVertical.texture );

			if ( depthTexture.isArrayTexture ) {

				shadowPassHorizontal = shadowPassHorizontal.depth( this.depthLayer );

			}

			const samples = reference( 'blurSamples', 'float', shadow ).setGroup( renderGroup );
			const radius = reference( 'radius', 'float', shadow ).setGroup( renderGroup );
			const size = reference( 'mapSize', 'vec2', shadow ).setGroup( renderGroup );

			let material = this.vsmMaterialVertical || ( this.vsmMaterialVertical = new NodeMaterial() );
			material.fragmentNode = VSMPassVertical( { samples, radius, size, shadowPass: shadowPassVertical, depthLayer: this.depthLayer } ).context( builder.getSharedContext() );
			material.name = 'VSMVertical';

			material = this.vsmMaterialHorizontal || ( this.vsmMaterialHorizontal = new NodeMaterial() );
			material.fragmentNode = VSMPassHorizontal( { samples, radius, size, shadowPass: shadowPassHorizontal, depthLayer: this.depthLayer } ).context( builder.getSharedContext() );
			material.name = 'VSMHorizontal';

		}

		//

		const shadowIntensity = reference( 'intensity', 'float', shadow ).setGroup( renderGroup );
		const normalBias = reference( 'normalBias', 'float', shadow ).setGroup( renderGroup );

		const shadowPosition = lightShadowMatrix( light ).mul( shadowPositionWorld.add( normalWorld.mul( normalBias ) ) );
		const shadowCoord = this.setupShadowCoord( builder, shadowPosition );

		//

		const filterFn = shadow.filterNode || this.getShadowFilterFn( renderer.shadowMap.type ) || null;

		if ( filterFn === null ) {

			throw new Error( 'THREE.WebGPURenderer: Shadow map type not supported yet.' );

		}

		const shadowDepthTexture = ( shadowMapType === VSMShadowMap && shadow.isPointLightShadow !== true ) ? this.vsmShadowMapHorizontal.texture : depthTexture;

		const shadowNode = this.setupShadowFilter( builder, { filterFn, shadowTexture: shadowMap.texture, depthTexture: shadowDepthTexture, shadowCoord, shadow, depthLayer: this.depthLayer } );

		let shadowColor = texture( shadowMap.texture, shadowCoord );

		if ( depthTexture.isArrayTexture ) {

			shadowColor = shadowColor.depth( this.depthLayer );

		}

		const shadowOutput = mix( 1, shadowNode.rgb.mix( shadowColor, 1 ), shadowIntensity.mul( shadowColor.a ) ).toVar();

		this.shadowMap = shadowMap;
		this.shadow.map = shadowMap;

		return shadowOutput;

	}

	/**
	 * The implementation performs the setup of the output node. An output is only
	 * produces if shadow mapping is globally enabled in the renderer.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @return {ShaderCallNodeInternal} The output node.
	 */
	setup( builder ) {

		if ( builder.renderer.shadowMap.enabled === false ) return;

		return Fn( () => {

			let node = this._node;

			this.setupShadowPosition( builder );

			if ( node === null ) {

				this._node = node = this.setupShadow( builder );

			}

			if ( builder.material.shadowNode ) { // @deprecated, r171

				console.warn( 'THREE.NodeMaterial: ".shadowNode" is deprecated. Use ".castShadowNode" instead.' );

			}

			if ( builder.material.receivedShadowNode ) {

				node = builder.material.receivedShadowNode( node );

			}

			return node;

		} )();

	}

	/**
	 * Renders the shadow. The logic of this function could be included
	 * into {@link ShadowNode#updateShadow} however more specialized shadow
	 * nodes might require a custom shadow map rendering. By having a
	 * dedicated method, it's easier to overwrite the default behavior.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
	renderShadow( frame ) {

		const { shadow, shadowMap, light } = this;
		const { renderer, scene } = frame;

		shadow.updateMatrices( light );

		shadowMap.setSize( shadow.mapSize.width, shadow.mapSize.height, shadowMap.depth );

		renderer.render( scene, shadow.camera );

	}

	/**
	 * Updates the shadow.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
	updateShadow( frame ) {

		const { shadowMap, light, shadow } = this;
		const { renderer, scene, camera } = frame;

		const shadowType = renderer.shadowMap.type;

		const depthVersion = shadowMap.depthTexture.version;
		this._depthVersionCached = depthVersion;

		const _shadowCameraLayer = shadow.camera.layers.mask;

		if ( ( shadow.camera.layers.mask & 0xFFFFFFFE ) === 0 ) {

			shadow.camera.layers.mask = camera.layers.mask;

		}

		const currentRenderObjectFunction = renderer.getRenderObjectFunction();

		const currentMRT = renderer.getMRT();
		const useVelocity = currentMRT ? currentMRT.has( 'velocity' ) : false;

		_rendererState = resetRendererAndSceneState( renderer, scene, _rendererState );

		scene.overrideMaterial = getShadowMaterial( light );

		renderer.setRenderObjectFunction( getShadowRenderObjectFunction( renderer, shadow, shadowType, useVelocity ) );

		renderer.setClearColor( 0x000000, 0 );

		renderer.setRenderTarget( shadowMap );

		this.renderShadow( frame );

		renderer.setRenderObjectFunction( currentRenderObjectFunction );

		// vsm blur pass

		if ( shadowType === VSMShadowMap && shadow.isPointLightShadow !== true ) {

			this.vsmPass( renderer );

		}

		shadow.camera.layers.mask = _shadowCameraLayer;

		restoreRendererAndSceneState( renderer, scene, _rendererState );

	}

	/**
	 * For VSM additional render passes are required.
	 *
	 * @param {Renderer} renderer - A reference to the current renderer.
	 */
	vsmPass( renderer ) {

		const { shadow } = this;

		const depth = this.shadowMap.depth;
		this.vsmShadowMapVertical.setSize( shadow.mapSize.width, shadow.mapSize.height, depth );
		this.vsmShadowMapHorizontal.setSize( shadow.mapSize.width, shadow.mapSize.height, depth );

		renderer.setRenderTarget( this.vsmShadowMapVertical );
		_quadMesh.material = this.vsmMaterialVertical;
		_quadMesh.render( renderer );

		renderer.setRenderTarget( this.vsmShadowMapHorizontal );
		_quadMesh.material = this.vsmMaterialHorizontal;
		_quadMesh.render( renderer );

	}

	/**
	 * Frees the internal resources of this shadow node.
	 */
	dispose() {

		this.shadowMap.dispose();
		this.shadowMap = null;

		if ( this.vsmShadowMapVertical !== null ) {

			this.vsmShadowMapVertical.dispose();
			this.vsmShadowMapVertical = null;

			this.vsmMaterialVertical.dispose();
			this.vsmMaterialVertical = null;

		}

		if ( this.vsmShadowMapHorizontal !== null ) {

			this.vsmShadowMapHorizontal.dispose();
			this.vsmShadowMapHorizontal = null;

			this.vsmMaterialHorizontal.dispose();
			this.vsmMaterialHorizontal = null;

		}

		super.dispose();

	}

	/**
	 * The implementation performs the update of the shadow map if necessary.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
	updateBefore( frame ) {

		const { shadow } = this;

		let needsUpdate = shadow.needsUpdate || shadow.autoUpdate;

		if ( needsUpdate ) {

			if ( this._cameraFrameId[ frame.camera ] === frame.frameId ) {

				needsUpdate = false;

			}

			this._cameraFrameId[ frame.camera ] = frame.frameId;

		}

		if ( needsUpdate ) {

			this.updateShadow( frame );

			if ( this.shadowMap.depthTexture.version === this._depthVersionCached ) {

				shadow.needsUpdate = false;

			}

		}

	}

}
```
</details>

#### Methods

##### `setupShadowFilter(builder: NodeBuilder, { filterFn, depthTexture, shadowCoord, shadow, depthLayer }: any): any`

<details><summary>Code</summary>

```ts
setupShadowFilter( builder, { filterFn, depthTexture, shadowCoord, shadow, depthLayer } ) {

		const frustumTest = shadowCoord.x.greaterThanEqual( 0 )
			.and( shadowCoord.x.lessThanEqual( 1 ) )
			.and( shadowCoord.y.greaterThanEqual( 0 ) )
			.and( shadowCoord.y.lessThanEqual( 1 ) )
			.and( shadowCoord.z.lessThanEqual( 1 ) );

		const shadowNode = filterFn( { depthTexture, shadowCoord, shadow, depthLayer } );

		return frustumTest.select( shadowNode, float( 1 ) );

	}
```
</details>

##### `setupShadowCoord(builder: NodeBuilder, shadowPosition: any): any`

<details><summary>Code</summary>

```ts
setupShadowCoord( builder, shadowPosition ) {

		const { shadow } = this;
		const { renderer } = builder;

		const bias = reference( 'bias', 'float', shadow ).setGroup( renderGroup );

		let shadowCoord = shadowPosition;
		let coordZ;

		if ( shadow.camera.isOrthographicCamera || renderer.logarithmicDepthBuffer !== true ) {

			shadowCoord = shadowCoord.xyz.div( shadowCoord.w );

			coordZ = shadowCoord.z;

			if ( renderer.coordinateSystem === WebGPUCoordinateSystem ) {

				coordZ = coordZ.mul( 2 ).sub( 1 ); // WebGPU: Conversion [ 0, 1 ] to [ - 1, 1 ]

			}

		} else {

			const w = shadowCoord.w;
			shadowCoord = shadowCoord.xy.div( w ); // <-- Only divide X/Y coords since we don't need Z

			// The normally available "cameraNear" and "cameraFar" nodes cannot be used here because they do not get
			// updated to use the shadow camera. So, we have to declare our own "local" ones here.
			// TODO: How do we get the cameraNear/cameraFar nodes to use the shadow camera so we don't have to declare local ones here?
			const cameraNearLocal = reference( 'near', 'float', shadow.camera ).setGroup( renderGroup );
			const cameraFarLocal = reference( 'far', 'float', shadow.camera ).setGroup( renderGroup );

			coordZ = viewZToLogarithmicDepth( w.negate(), cameraNearLocal, cameraFarLocal );

		}

		shadowCoord = vec3(
			shadowCoord.x,
			shadowCoord.y.oneMinus(), // follow webgpu standards
			coordZ.add( bias )
		);

		return shadowCoord;

	}
```
</details>

##### `getShadowFilterFn(type: number): Function`

<details><summary>Code</summary>

```ts
getShadowFilterFn( type ) {

		return _shadowFilterLib[ type ];

	}
```
</details>

##### `setupRenderTarget(shadow: any, builder: any): { shadowMap: any; depthTexture: DepthTexture; }`

<details><summary>Code</summary>

```ts
setupRenderTarget( shadow, builder ) {

		const depthTexture = new DepthTexture( shadow.mapSize.width, shadow.mapSize.height );
		depthTexture.name = 'ShadowDepthTexture';
		depthTexture.compareFunction = LessCompare;

		const shadowMap = builder.createRenderTarget( shadow.mapSize.width, shadow.mapSize.height );
		shadowMap.texture.name = 'ShadowMap';
		shadowMap.texture.type = shadow.mapType;
		shadowMap.depthTexture = depthTexture;

		return { shadowMap, depthTexture };

	}
```
</details>

##### `setupShadow(builder: NodeBuilder): any`

<details><summary>Code</summary>

```ts
setupShadow( builder ) {

		const { renderer } = builder;

		const { light, shadow } = this;

		const shadowMapType = renderer.shadowMap.type;

		const { depthTexture, shadowMap } = this.setupRenderTarget( shadow, builder );

		shadow.camera.updateProjectionMatrix();

		// VSM

		if ( shadowMapType === VSMShadowMap && shadow.isPointLightShadow !== true ) {

			depthTexture.compareFunction = null; // VSM does not use textureSampleCompare()/texture2DCompare()

			if ( shadowMap.depth > 1 ) {

				if ( ! shadowMap._vsmShadowMapVertical ) {

					shadowMap._vsmShadowMapVertical = builder.createRenderTarget( shadow.mapSize.width, shadow.mapSize.height, { format: RGFormat, type: HalfFloatType, depth: shadowMap.depth, depthBuffer: false } );
					shadowMap._vsmShadowMapVertical.texture.name = 'VSMVertical';

				}

				this.vsmShadowMapVertical = shadowMap._vsmShadowMapVertical;

				if ( ! shadowMap._vsmShadowMapHorizontal ) {

					shadowMap._vsmShadowMapHorizontal = builder.createRenderTarget( shadow.mapSize.width, shadow.mapSize.height, { format: RGFormat, type: HalfFloatType, depth: shadowMap.depth, depthBuffer: false } );
					shadowMap._vsmShadowMapHorizontal.texture.name = 'VSMHorizontal';

				}

				this.vsmShadowMapHorizontal = shadowMap._vsmShadowMapHorizontal;

			} else {

				this.vsmShadowMapVertical = builder.createRenderTarget( shadow.mapSize.width, shadow.mapSize.height, { format: RGFormat, type: HalfFloatType, depthBuffer: false } );
				this.vsmShadowMapHorizontal = builder.createRenderTarget( shadow.mapSize.width, shadow.mapSize.height, { format: RGFormat, type: HalfFloatType, depthBuffer: false } );

			}


			let shadowPassVertical = texture( depthTexture );

			if ( depthTexture.isArrayTexture ) {

				shadowPassVertical = shadowPassVertical.depth( this.depthLayer );

			}

			let shadowPassHorizontal = texture( this.vsmShadowMapVertical.texture );

			if ( depthTexture.isArrayTexture ) {

				shadowPassHorizontal = shadowPassHorizontal.depth( this.depthLayer );

			}

			const samples = reference( 'blurSamples', 'float', shadow ).setGroup( renderGroup );
			const radius = reference( 'radius', 'float', shadow ).setGroup( renderGroup );
			const size = reference( 'mapSize', 'vec2', shadow ).setGroup( renderGroup );

			let material = this.vsmMaterialVertical || ( this.vsmMaterialVertical = new NodeMaterial() );
			material.fragmentNode = VSMPassVertical( { samples, radius, size, shadowPass: shadowPassVertical, depthLayer: this.depthLayer } ).context( builder.getSharedContext() );
			material.name = 'VSMVertical';

			material = this.vsmMaterialHorizontal || ( this.vsmMaterialHorizontal = new NodeMaterial() );
			material.fragmentNode = VSMPassHorizontal( { samples, radius, size, shadowPass: shadowPassHorizontal, depthLayer: this.depthLayer } ).context( builder.getSharedContext() );
			material.name = 'VSMHorizontal';

		}

		//

		const shadowIntensity = reference( 'intensity', 'float', shadow ).setGroup( renderGroup );
		const normalBias = reference( 'normalBias', 'float', shadow ).setGroup( renderGroup );

		const shadowPosition = lightShadowMatrix( light ).mul( shadowPositionWorld.add( normalWorld.mul( normalBias ) ) );
		const shadowCoord = this.setupShadowCoord( builder, shadowPosition );

		//

		const filterFn = shadow.filterNode || this.getShadowFilterFn( renderer.shadowMap.type ) || null;

		if ( filterFn === null ) {

			throw new Error( 'THREE.WebGPURenderer: Shadow map type not supported yet.' );

		}

		const shadowDepthTexture = ( shadowMapType === VSMShadowMap && shadow.isPointLightShadow !== true ) ? this.vsmShadowMapHorizontal.texture : depthTexture;

		const shadowNode = this.setupShadowFilter( builder, { filterFn, shadowTexture: shadowMap.texture, depthTexture: shadowDepthTexture, shadowCoord, shadow, depthLayer: this.depthLayer } );

		let shadowColor = texture( shadowMap.texture, shadowCoord );

		if ( depthTexture.isArrayTexture ) {

			shadowColor = shadowColor.depth( this.depthLayer );

		}

		const shadowOutput = mix( 1, shadowNode.rgb.mix( shadowColor, 1 ), shadowIntensity.mul( shadowColor.a ) ).toVar();

		this.shadowMap = shadowMap;
		this.shadow.map = shadowMap;

		return shadowOutput;

	}
```
</details>

##### `setup(builder: NodeBuilder): ShaderCallNodeInternal`

<details><summary>Code</summary>

```ts
setup( builder ) {

		if ( builder.renderer.shadowMap.enabled === false ) return;

		return Fn( () => {

			let node = this._node;

			this.setupShadowPosition( builder );

			if ( node === null ) {

				this._node = node = this.setupShadow( builder );

			}

			if ( builder.material.shadowNode ) { // @deprecated, r171

				console.warn( 'THREE.NodeMaterial: ".shadowNode" is deprecated. Use ".castShadowNode" instead.' );

			}

			if ( builder.material.receivedShadowNode ) {

				node = builder.material.receivedShadowNode( node );

			}

			return node;

		} )();

	}
```
</details>

##### `renderShadow(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
renderShadow( frame ) {

		const { shadow, shadowMap, light } = this;
		const { renderer, scene } = frame;

		shadow.updateMatrices( light );

		shadowMap.setSize( shadow.mapSize.width, shadow.mapSize.height, shadowMap.depth );

		renderer.render( scene, shadow.camera );

	}
```
</details>

##### `updateShadow(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
updateShadow( frame ) {

		const { shadowMap, light, shadow } = this;
		const { renderer, scene, camera } = frame;

		const shadowType = renderer.shadowMap.type;

		const depthVersion = shadowMap.depthTexture.version;
		this._depthVersionCached = depthVersion;

		const _shadowCameraLayer = shadow.camera.layers.mask;

		if ( ( shadow.camera.layers.mask & 0xFFFFFFFE ) === 0 ) {

			shadow.camera.layers.mask = camera.layers.mask;

		}

		const currentRenderObjectFunction = renderer.getRenderObjectFunction();

		const currentMRT = renderer.getMRT();
		const useVelocity = currentMRT ? currentMRT.has( 'velocity' ) : false;

		_rendererState = resetRendererAndSceneState( renderer, scene, _rendererState );

		scene.overrideMaterial = getShadowMaterial( light );

		renderer.setRenderObjectFunction( getShadowRenderObjectFunction( renderer, shadow, shadowType, useVelocity ) );

		renderer.setClearColor( 0x000000, 0 );

		renderer.setRenderTarget( shadowMap );

		this.renderShadow( frame );

		renderer.setRenderObjectFunction( currentRenderObjectFunction );

		// vsm blur pass

		if ( shadowType === VSMShadowMap && shadow.isPointLightShadow !== true ) {

			this.vsmPass( renderer );

		}

		shadow.camera.layers.mask = _shadowCameraLayer;

		restoreRendererAndSceneState( renderer, scene, _rendererState );

	}
```
</details>

##### `vsmPass(renderer: Renderer): void`

<details><summary>Code</summary>

```ts
vsmPass( renderer ) {

		const { shadow } = this;

		const depth = this.shadowMap.depth;
		this.vsmShadowMapVertical.setSize( shadow.mapSize.width, shadow.mapSize.height, depth );
		this.vsmShadowMapHorizontal.setSize( shadow.mapSize.width, shadow.mapSize.height, depth );

		renderer.setRenderTarget( this.vsmShadowMapVertical );
		_quadMesh.material = this.vsmMaterialVertical;
		_quadMesh.render( renderer );

		renderer.setRenderTarget( this.vsmShadowMapHorizontal );
		_quadMesh.material = this.vsmMaterialHorizontal;
		_quadMesh.render( renderer );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.shadowMap.dispose();
		this.shadowMap = null;

		if ( this.vsmShadowMapVertical !== null ) {

			this.vsmShadowMapVertical.dispose();
			this.vsmShadowMapVertical = null;

			this.vsmMaterialVertical.dispose();
			this.vsmMaterialVertical = null;

		}

		if ( this.vsmShadowMapHorizontal !== null ) {

			this.vsmShadowMapHorizontal.dispose();
			this.vsmShadowMapHorizontal = null;

			this.vsmMaterialHorizontal.dispose();
			this.vsmMaterialHorizontal = null;

		}

		super.dispose();

	}
```
</details>

##### `updateBefore(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		const { shadow } = this;

		let needsUpdate = shadow.needsUpdate || shadow.autoUpdate;

		if ( needsUpdate ) {

			if ( this._cameraFrameId[ frame.camera ] === frame.frameId ) {

				needsUpdate = false;

			}

			this._cameraFrameId[ frame.camera ] = frame.frameId;

		}

		if ( needsUpdate ) {

			this.updateShadow( frame );

			if ( this.shadowMap.depthTexture.version === this._depthVersionCached ) {

				shadow.needsUpdate = false;

			}

		}

	}
```
</details>


---