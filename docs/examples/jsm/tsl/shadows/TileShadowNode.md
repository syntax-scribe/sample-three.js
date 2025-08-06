[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `TileShadowNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 🧱 Classes | 2 |
| 📦 Imports | 19 |
| 📊 Variables & Constants | 45 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/shadows/TileShadowNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `three/webgpu` |
| `Object3D` | `three/webgpu` |
| `ShadowBaseNode` | `three/webgpu` |
| `Plane` | `three/webgpu` |
| `Line3` | `three/webgpu` |
| `DepthTexture` | `three/webgpu` |
| `LessCompare` | `three/webgpu` |
| `Vector2` | `three/webgpu` |
| `RedFormat` | `three/webgpu` |
| `ArrayCamera` | `three/webgpu` |
| `VSMShadowMap` | `three/webgpu` |
| `RendererUtils` | `three/webgpu` |
| `Quaternion` | `three/webgpu` |
| `min` | `three/tsl` |
| `Fn` | `three/tsl` |
| `shadow` | `three/tsl` |
| `NodeUpdateType` | `three/tsl` |
| `getShadowMaterial` | `three/tsl` |
| `getShadowRenderObjectFunction` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_rendererState` | `any` | let/var | `*not shown*` | ✗ |
| `_cameraLayers` | `any[]` | let/var | `[]` | ✗ |
| `_vec3Temp1` | `any` | let/var | `new Vector3()` | ✗ |
| `_vec3Temp2` | `any` | let/var | `new Vector3()` | ✗ |
| `_vec3Temp3` | `any` | let/var | `new Vector3()` | ✗ |
| `_quatTemp1` | `any` | let/var | `new Quaternion()` | ✗ |
| `tiles` | `any[]` | let/var | `[]` | ✗ |
| `tileWidth` | `number` | let/var | `1 / tilesX` | ✗ |
| `tileHeight` | `number` | let/var | `1 / tilesY` | ✗ |
| `light` | `Light` | let/var | `this.originalLight` | ✗ |
| `parent` | `any` | let/var | `light.parent` | ✗ |
| `width` | `number` | let/var | `this.shadowSize.right - this.shadowSize.left` | ✗ |
| `height` | `number` | let/var | `this.shadowSize.top - this.shadowSize.bottom` | ✗ |
| `tileCount` | `number` | let/var | `this.tiles.length` | ✗ |
| `shadowWidth` | `any` | let/var | `this.config.resolution.width` | ✗ |
| `shadowHeight` | `any` | let/var | `this.config.resolution.height` | ✗ |
| `depthTexture` | `any` | let/var | `new DepthTexture( shadowWidth, shadowHeight, undefined, undefined, undefined,...` | ✗ |
| `cameras` | `any[]` | let/var | `[]` | ✗ |
| `lwLight` | `LwLight` | let/var | `new LwLight()` | ✗ |
| `tile` | `any` | let/var | `this.tiles[ i ]` | ✗ |
| `cameraArray` | `any` | let/var | `new ArrayCamera( cameras )` | ✗ |
| `light` | `Light` | let/var | `this.originalLight` | ✗ |
| `shadowCam` | `any` | let/var | `light.shadow.camera` | ✗ |
| `lsMin` | `any` | let/var | `new Vector2( shadowCam.left, shadowCam.bottom )` | ✗ |
| `lsMax` | `any` | let/var | `new Vector2( shadowCam.right, shadowCam.top )` | ✗ |
| `fullWidth` | `number` | let/var | `lsMax.x - lsMin.x` | ✗ |
| `fullHeight` | `number` | let/var | `lsMax.y - lsMin.y` | ✗ |
| `lwLight` | `any` | let/var | `this.lights[ i ]` | ✗ |
| `tile` | `any` | let/var | `this.tiles[ i ]` | ✗ |
| `lShadow` | `any` | let/var | `lwLight.shadow` | ✗ |
| `tileLeft` | `any` | let/var | `lsMin.x + tile.x[ 0 ] * fullWidth` | ✗ |
| `tileRight` | `any` | let/var | `lsMin.x + tile.x[ 1 ] * fullWidth` | ✗ |
| `tileBottom` | `any` | let/var | `lsMin.y + tile.y[ 0 ] * fullHeight` | ✗ |
| `tileTop` | `any` | let/var | `lsMin.y + tile.y[ 1 ] * fullHeight` | ✗ |
| `shadowType` | `any` | let/var | `renderer.shadowMap.type` | ✗ |
| `depthVersion` | `any` | let/var | `shadowMap.depthTexture.version` | ✗ |
| `useVelocity` | `any` | let/var | `currentMRT ? currentMRT.has( 'velocity' ) : false` | ✗ |
| `light` | `any` | let/var | `this.lights[ index ]` | ✗ |
| `shadow` | `any` | let/var | `light.shadow` | ✗ |
| `_shadowCameraLayer` | `any` | let/var | `shadow.camera.layers.mask` | ✗ |
| `light` | `any` | let/var | `this.lights[ index ]` | ✗ |
| `shadow` | `any` | let/var | `light.shadow` | ✗ |
| `shadow` | `any` | let/var | `this.originalLight.shadow` | ✗ |
| `needsUpdate` | `any` | let/var | `shadow.needsUpdate \|\| shadow.autoUpdate` | ✗ |
| `parent` | `any` | let/var | `light.parent` | ✗ |


---

## Functions

### `TileShadowNode.generateTiles(tilesX: number, tilesY: number): any[]`

**JSDoc:**
```typescript
/**
	 * Generates the tiles for the shadow map based on the specified number of tiles along the X and Y axes.
	 *
	 * @param {number} tilesX - The number of tiles along the X-axis.
	 * @param {number} tilesY - The number of tiles along the Y-axis.
	 * @returns {Array<Object>} An array of tile objects, each containing the tile's bounds and index.
	 */
```

**Parameters:**

- **`tilesX`** `number`
- **`tilesY`** `number`

**Returns:** `any[]`

**Calls:**

- `tiles.push`

<details><summary>Code</summary>

```typescript
generateTiles( tilesX, tilesY ) {

		const tiles = [];
		const tileWidth = 1 / tilesX;
		const tileHeight = 1 / tilesY;

		for ( let y = 0; y < tilesY; y ++ ) {

			for ( let x = 0; x < tilesX; x ++ ) {

				tiles.push( {
					x: [ x * tileWidth, ( x + 1 ) * tileWidth ],
					y: [ ( tilesY - 1 - y ) * tileHeight, ( tilesY - y ) * tileHeight ], // Start from top row
					index: y * tilesX + x
				} );

			}

		}

		return tiles;

	}
```
</details>

### `TileShadowNode.updateLightDirection(): void`

**JSDoc:**
```typescript
/**
	 * Updates the initial light direction based on the light's target position.
	 */
```

**Returns:** `void`

**Calls:**

- `this.initialLightDirection.subVectors(
			this.originalLight.target.getWorldPosition( new Vector3() ),
			this.originalLight.getWorldPosition( new Vector3() )
		).normalize`

<details><summary>Code</summary>

```typescript
updateLightDirection() {

		this.initialLightDirection.subVectors(
			this.originalLight.target.getWorldPosition( new Vector3() ),
			this.originalLight.getWorldPosition( new Vector3() )
		).normalize();

	}
```
</details>

### `TileShadowNode.init(builder: Builder): void`

**JSDoc:**
```typescript
/**
	 * Initializes the tiled shadow node by creating lights, cameras, and shadow maps for each tile.
	 *
	 * @param {Builder} builder - The builder used to create render targets and other resources.
	 */
```

**Parameters:**

- **`builder`** `Builder`

**Returns:** `void`

**Calls:**

- `this.disposeLightsAndNodes`
- `builder.createRenderTarget`
- `light.shadow.clone`
- `parent.add`
- `console.warn`
- `this.syncLightTransformation`
- `this.lights.push`
- `lShadow.camera.updateMatrixWorld`
- `cameras.push`
- `shadow (from three/tsl)`
- `this._shadowNodes.push`

**Internal Comments:**
```
// Clear existing lights/nodes if re-initializing (x4)
// Create lights, one for each tile
```

<details><summary>Code</summary>

```typescript
init( builder ) {

		const light = this.originalLight;
		const parent = light.parent;

		const width = this.shadowSize.right - this.shadowSize.left;
		const height = this.shadowSize.top - this.shadowSize.bottom;

		const tileCount = this.tiles.length;
		const shadowWidth = this.config.resolution.width;
		const shadowHeight = this.config.resolution.height;

		// Clear existing lights/nodes if re-initializing
		this.disposeLightsAndNodes();

		const depthTexture = new DepthTexture( shadowWidth, shadowHeight, undefined, undefined, undefined, undefined, undefined, undefined, undefined, undefined, tileCount );
		depthTexture.compareFunction = LessCompare;
		depthTexture.name = 'ShadowDepthArrayTexture';
		const shadowMap = builder.createRenderTarget( shadowWidth, shadowHeight, { format: RedFormat, depth: tileCount } );
		shadowMap.depthTexture = depthTexture;
		shadowMap.texture.name = 'ShadowTexture';
		this.shadowMap = shadowMap;
		const cameras = [];


		// Create lights, one for each tile
		for ( let i = 0; i < tileCount; i ++ ) {

			const lwLight = new LwLight();
			lwLight.castShadow = true;
			const lShadow = light.shadow.clone();
			lShadow.filterNode = light.shadow.filterNode;
			const tile = this.tiles[ i ];
			lShadow.camera.left = this.shadowSize.left + width * tile.x[ 0 ];
			lShadow.camera.right = this.shadowSize.left + width * tile.x[ 1 ];
			lShadow.camera.top = this.shadowSize.bottom + height * tile.y[ 1 ];
			lShadow.camera.bottom = this.shadowSize.bottom + height * tile.y[ 0 ];
			lShadow.bias = light.shadow.bias;
			lShadow.camera.near = light.shadow.camera.near;
			lShadow.camera.far = light.shadow.camera.far;
			lShadow.camera.userData.tileIndex = i;
			lwLight.shadow = lShadow;

			if ( parent ) {

				parent.add( lwLight );
				parent.add( lwLight.target );

			} else {

				console.warn( 'TileShadowNode: Original light has no parent during init. Tile lights not added to scene graph directly.' );

			}

			this.syncLightTransformation( lwLight, light );

			this.lights.push( lwLight );
			lShadow.camera.updateMatrixWorld();

			cameras.push( lShadow.camera );
			const shadowNode = shadow( lwLight, lShadow );
			shadowNode.depthLayer = i;
			shadowNode.updateBeforeType = NodeUpdateType.NONE;

			shadowNode.setupRenderTarget = () => {

				return { shadowMap, depthTexture };

			};

			this._shadowNodes.push( shadowNode );

		}

		const cameraArray = new ArrayCamera( cameras );
		this.cameraArray = cameraArray;

	}
```
</details>

### `TileShadowNode.update(): void`

**JSDoc:**
```typescript
/**
	 * Updates the light transformations and shadow cameras for each tile.
	 */
```

**Returns:** `void`

**Calls:**

- `this.syncLightTransformation`
- `lShadow.camera.updateProjectionMatrix`
- `lShadow.camera.updateWorldMatrix`
- `lShadow.camera.updateMatrixWorld`

<details><summary>Code</summary>

```typescript
update() {

		const light = this.originalLight;

		const shadowCam = light.shadow.camera;
		const lsMin = new Vector2( shadowCam.left, shadowCam.bottom );
		const lsMax = new Vector2( shadowCam.right, shadowCam.top );
		const fullWidth = lsMax.x - lsMin.x;
		const fullHeight = lsMax.y - lsMin.y;

		for ( let i = 0; i < this.lights.length; i ++ ) {

			const lwLight = this.lights[ i ];
			const tile = this.tiles[ i ];
			this.syncLightTransformation( lwLight, light );
			const lShadow = lwLight.shadow;
			const tileLeft = lsMin.x + tile.x[ 0 ] * fullWidth;
			const tileRight = lsMin.x + tile.x[ 1 ] * fullWidth;
			const tileBottom = lsMin.y + tile.y[ 0 ] * fullHeight;
			const tileTop = lsMin.y + tile.y[ 1 ] * fullHeight;
			lShadow.camera.left = tileLeft;
			lShadow.camera.right = tileRight;
			lShadow.camera.bottom = tileBottom;
			lShadow.camera.top = tileTop;
			lShadow.camera.near = light.shadow.camera.near;
			lShadow.camera.far = light.shadow.camera.far;
			lShadow.camera.updateProjectionMatrix();
			lShadow.camera.updateWorldMatrix( true, false );
			lShadow.camera.updateMatrixWorld( true );
			this._shadowNodes[ i ].shadow.needsUpdate = true;

		}

	}
```
</details>

### `TileShadowNode.updateShadow(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
     * Updates the shadow map rendering.
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
- `resetRendererAndSceneState`
- `getShadowMaterial (from three/tsl)`
- `renderer.setRenderTarget`
- `_cameraLayers.push`
- `shadow.updateMatrices`
- `renderer.setRenderObjectFunction`
- `getShadowRenderObjectFunction (from three/tsl)`
- `this.shadowMap.setSize`
- `renderer.render`
- `console.warn`
- `restoreRendererAndSceneState`

<details><summary>Code</summary>

```typescript
updateShadow( frame ) {

		const { shadowMap, light } = this;
		const { renderer, scene, camera } = frame;
		const shadowType = renderer.shadowMap.type;
		const depthVersion = shadowMap.depthTexture.version;
		this._depthVersionCached = depthVersion;
		const currentRenderObjectFunction = renderer.getRenderObjectFunction();
		const currentMRT = renderer.getMRT();
		const useVelocity = currentMRT ? currentMRT.has( 'velocity' ) : false;

		_rendererState = resetRendererAndSceneState( renderer, scene, _rendererState );
		scene.overrideMaterial = getShadowMaterial( light );
		renderer.setRenderTarget( this.shadowMap );


		for ( let index = 0; index < this.lights.length; index ++ ) {

			const light = this.lights[ index ];
			const shadow = light.shadow;

			const _shadowCameraLayer = shadow.camera.layers.mask;
			_cameraLayers.push( _shadowCameraLayer );

			if ( ( shadow.camera.layers.mask & 0xFFFFFFFE ) === 0 ) {

				shadow.camera.layers.mask = camera.layers.mask;

			}

			shadow.updateMatrices( light );

			renderer.setRenderObjectFunction( getShadowRenderObjectFunction( renderer, shadow, shadowType, useVelocity ) );
			this.shadowMap.setSize( shadow.mapSize.width, shadow.mapSize.height, shadowMap.depth );

		}

		renderer.render( scene, this.cameraArray );
		renderer.setRenderObjectFunction( currentRenderObjectFunction );

		if ( light.isPointLight !== true && shadowType === VSMShadowMap ) {

			console.warn( 'THREE.TileShadowNode: VSM shadow map is not supported yet.' );
			// this.vsmPass( renderer );

		}

		restoreRendererAndSceneState( renderer, scene, _rendererState );

		for ( let index = 0; index < this.lights.length; index ++ ) {

			const light = this.lights[ index ];
			const shadow = light.shadow;

			shadow.camera.layers.mask = _cameraLayers[ index ];

		}

		_cameraLayers.length = 0;

	}
```
</details>

### `TileShadowNode.updateBefore(frame: NodeFrame): void`

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

- `this.update`
- `this.updateShadow`

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		const shadow = this.originalLight.shadow;

		let needsUpdate = shadow.needsUpdate || shadow.autoUpdate;

		if ( needsUpdate ) {

			if ( this._cameraFrameId[ frame.camera ] === frame.frameId ) {

				needsUpdate = false;

			}

			this._cameraFrameId[ frame.camera ] = frame.frameId;

		}

		if ( needsUpdate ) {

			this.update();
			this.updateShadow( frame );

			if ( this.shadowMap.depthTexture.version === this._depthVersionCached ) {

				shadow.needsUpdate = false;

			}

		}

	}
```
</details>

### `TileShadowNode.syncLightTransformation(lwLight: LwLight, sourceLight: Light): void`

**JSDoc:**
```typescript
/**
	 * Synchronizes the transformation of a tile light with the source light.
	 *
	 * @param {LwLight} lwLight - The tile light to synchronize.
	 * @param {Light} sourceLight - The source light to copy transformations from.
	 */
```

**Parameters:**

- **`lwLight`** `LwLight`
- **`sourceLight`** `Light`

**Returns:** `void`

**Calls:**

- `sourceLight.getWorldPosition`
- `sourceLight.target.getWorldPosition`
- `_vec3Temp3.subVectors`
- `forward.length`
- `forward.normalize`
- `lwLight.position.copy`
- `lwLight.target.position.copy( sourceWorldPos ).add`
- `forward.multiplyScalar`
- `lwLight.quaternion.copy`
- `sourceLight.getWorldQuaternion`
- `lwLight.scale.copy`
- `lwLight.updateMatrix`
- `lwLight.updateMatrixWorld`
- `lwLight.target.updateMatrix`
- `lwLight.target.updateMatrixWorld`

<details><summary>Code</summary>

```typescript
syncLightTransformation( lwLight, sourceLight ) {

		const sourceWorldPos = sourceLight.getWorldPosition( _vec3Temp1 );
		const targetWorldPos = sourceLight.target.getWorldPosition( _vec3Temp2 );
		const forward = _vec3Temp3.subVectors( targetWorldPos, sourceWorldPos );
		const targetDistance = forward.length();
		forward.normalize();
		lwLight.position.copy( sourceWorldPos );
		lwLight.target.position.copy( sourceWorldPos ).add( forward.multiplyScalar( targetDistance ) );
		lwLight.quaternion.copy( sourceLight.getWorldQuaternion( _quatTemp1 ) );
		lwLight.scale.copy( sourceLight.scale );
		lwLight.updateMatrix();
		lwLight.updateMatrixWorld( true );
		lwLight.target.updateMatrix();
		lwLight.target.updateMatrixWorld( true );

	}
```
</details>

### `TileShadowNode.setup(builder: Builder): Node`

**JSDoc:**
```typescript
/**
	 * Sets up the shadow node for rendering.
	 *
	 * @param {Builder} builder - The builder used to set up the shadow node.
	 * @returns {Node} A node representing the shadow value.
	 */
```

**Parameters:**

- **`builder`** `Builder`

**Returns:** `Node`

**Calls:**

- `this.init`
- `complex_call_11594`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		if ( this.lights.length === 0 ) {

			this.init( builder );

		}

		return Fn( ( builder ) => {

			this.setupShadowPosition( builder );
			return min( ...this._shadowNodes ).toVar( 'shadowValue' );

		} )();

	}
```
</details>

### `TileShadowNode.disposeLightsAndNodes(): void`

**JSDoc:**
```typescript
/**
     * Helper method to remove lights and associated nodes/targets.
     * Used internally during dispose and potential re-initialization.
     */
```

**Returns:** `void`

**Calls:**

- `parent.remove`
- `this.shadowMap.dispose`

<details><summary>Code</summary>

```typescript
disposeLightsAndNodes() {

		for ( const light of this.lights ) {

			const parent = light.parent;
			if ( parent ) {

				parent.remove( light.target );
				parent.remove( light );

			}

		}

		this.lights = [];
		this._shadowNodes = [];

		if ( this.shadowMap ) {

			this.shadowMap.dispose(); // Disposes render target and textures
			this.shadowMap = null;

		}

	}
```
</details>

### `TileShadowNode.dispose(): void`

**Returns:** `void`

**Calls:**

- `this.disposeLightsAndNodes`
- `super.dispose`

**Internal Comments:**
```
// Dispose lights, nodes, and shadow map (x4)
```

<details><summary>Code</summary>

```typescript
dispose() {

		// Dispose lights, nodes, and shadow map
		this.disposeLightsAndNodes();
		super.dispose();

	}
```
</details>


---

## Classes

### `LwLight`

<details><summary>Class Code</summary>

```ts
class LwLight extends Object3D {

	constructor() {

		super();
		this.target = new Object3D();

	}

}
```
</details>

### `TileShadowNode`

<details><summary>Class Code</summary>

```ts
class TileShadowNode extends ShadowBaseNode {

	/**
	 * Creates an instance of `TileShadowNode`.
	 *
	 * @param {Light} light - The original light source used for shadow mapping.
	 * @param {Object} [options={}] - Configuration options for the tiled shadow node.
	 * @param {number} [options.tilesX=2] - The number of tiles along the X-axis.
	 * @param {number} [options.tilesY=2] - The number of tiles along the Y-axis.
	 * @param {Object} [options.resolution] - The resolution of the shadow map.
	 * @param {boolean} [options.debug=false] - Whether to enable debug mode.
	 */
	constructor( light, options = {} ) {

		super( light );

		// Default configuration with sensible defaults
		this.config = {
			tilesX: options.tilesX || 2,
			tilesY: options.tilesY || 2,
			resolution: options.resolution || light.shadow.mapSize,
			debug: options.debug !== undefined ? options.debug : false
		};

		this.debug = this.config.debug;

		this.originalLight = light;
		this.lightPlane = new Plane( new Vector3( 0, 1, 0 ), 0 );
		this.line = new Line3();

		this.initialLightDirection = new Vector3();
		this.updateLightDirection();

		this._cameraFrameId = new WeakMap();

		this.shadowSize = {
			top: light.shadow.camera.top,
			bottom: light.shadow.camera.bottom,
			left: light.shadow.camera.left,
			right: light.shadow.camera.right,
		};

		this.lights = [];
		this._shadowNodes = [];

		this.tiles = this.generateTiles( this.config.tilesX, this.config.tilesY );

	}

	/**
	 * Generates the tiles for the shadow map based on the specified number of tiles along the X and Y axes.
	 *
	 * @param {number} tilesX - The number of tiles along the X-axis.
	 * @param {number} tilesY - The number of tiles along the Y-axis.
	 * @returns {Array<Object>} An array of tile objects, each containing the tile's bounds and index.
	 */
	generateTiles( tilesX, tilesY ) {

		const tiles = [];
		const tileWidth = 1 / tilesX;
		const tileHeight = 1 / tilesY;

		for ( let y = 0; y < tilesY; y ++ ) {

			for ( let x = 0; x < tilesX; x ++ ) {

				tiles.push( {
					x: [ x * tileWidth, ( x + 1 ) * tileWidth ],
					y: [ ( tilesY - 1 - y ) * tileHeight, ( tilesY - y ) * tileHeight ], // Start from top row
					index: y * tilesX + x
				} );

			}

		}

		return tiles;

	}

	/**
	 * Updates the initial light direction based on the light's target position.
	 */
	updateLightDirection() {

		this.initialLightDirection.subVectors(
			this.originalLight.target.getWorldPosition( new Vector3() ),
			this.originalLight.getWorldPosition( new Vector3() )
		).normalize();

	}

	/**
	 * Initializes the tiled shadow node by creating lights, cameras, and shadow maps for each tile.
	 *
	 * @param {Builder} builder - The builder used to create render targets and other resources.
	 */
	init( builder ) {

		const light = this.originalLight;
		const parent = light.parent;

		const width = this.shadowSize.right - this.shadowSize.left;
		const height = this.shadowSize.top - this.shadowSize.bottom;

		const tileCount = this.tiles.length;
		const shadowWidth = this.config.resolution.width;
		const shadowHeight = this.config.resolution.height;

		// Clear existing lights/nodes if re-initializing
		this.disposeLightsAndNodes();

		const depthTexture = new DepthTexture( shadowWidth, shadowHeight, undefined, undefined, undefined, undefined, undefined, undefined, undefined, undefined, tileCount );
		depthTexture.compareFunction = LessCompare;
		depthTexture.name = 'ShadowDepthArrayTexture';
		const shadowMap = builder.createRenderTarget( shadowWidth, shadowHeight, { format: RedFormat, depth: tileCount } );
		shadowMap.depthTexture = depthTexture;
		shadowMap.texture.name = 'ShadowTexture';
		this.shadowMap = shadowMap;
		const cameras = [];


		// Create lights, one for each tile
		for ( let i = 0; i < tileCount; i ++ ) {

			const lwLight = new LwLight();
			lwLight.castShadow = true;
			const lShadow = light.shadow.clone();
			lShadow.filterNode = light.shadow.filterNode;
			const tile = this.tiles[ i ];
			lShadow.camera.left = this.shadowSize.left + width * tile.x[ 0 ];
			lShadow.camera.right = this.shadowSize.left + width * tile.x[ 1 ];
			lShadow.camera.top = this.shadowSize.bottom + height * tile.y[ 1 ];
			lShadow.camera.bottom = this.shadowSize.bottom + height * tile.y[ 0 ];
			lShadow.bias = light.shadow.bias;
			lShadow.camera.near = light.shadow.camera.near;
			lShadow.camera.far = light.shadow.camera.far;
			lShadow.camera.userData.tileIndex = i;
			lwLight.shadow = lShadow;

			if ( parent ) {

				parent.add( lwLight );
				parent.add( lwLight.target );

			} else {

				console.warn( 'TileShadowNode: Original light has no parent during init. Tile lights not added to scene graph directly.' );

			}

			this.syncLightTransformation( lwLight, light );

			this.lights.push( lwLight );
			lShadow.camera.updateMatrixWorld();

			cameras.push( lShadow.camera );
			const shadowNode = shadow( lwLight, lShadow );
			shadowNode.depthLayer = i;
			shadowNode.updateBeforeType = NodeUpdateType.NONE;

			shadowNode.setupRenderTarget = () => {

				return { shadowMap, depthTexture };

			};

			this._shadowNodes.push( shadowNode );

		}

		const cameraArray = new ArrayCamera( cameras );
		this.cameraArray = cameraArray;

	}

	/**
	 * Updates the light transformations and shadow cameras for each tile.
	 */
	update() {

		const light = this.originalLight;

		const shadowCam = light.shadow.camera;
		const lsMin = new Vector2( shadowCam.left, shadowCam.bottom );
		const lsMax = new Vector2( shadowCam.right, shadowCam.top );
		const fullWidth = lsMax.x - lsMin.x;
		const fullHeight = lsMax.y - lsMin.y;

		for ( let i = 0; i < this.lights.length; i ++ ) {

			const lwLight = this.lights[ i ];
			const tile = this.tiles[ i ];
			this.syncLightTransformation( lwLight, light );
			const lShadow = lwLight.shadow;
			const tileLeft = lsMin.x + tile.x[ 0 ] * fullWidth;
			const tileRight = lsMin.x + tile.x[ 1 ] * fullWidth;
			const tileBottom = lsMin.y + tile.y[ 0 ] * fullHeight;
			const tileTop = lsMin.y + tile.y[ 1 ] * fullHeight;
			lShadow.camera.left = tileLeft;
			lShadow.camera.right = tileRight;
			lShadow.camera.bottom = tileBottom;
			lShadow.camera.top = tileTop;
			lShadow.camera.near = light.shadow.camera.near;
			lShadow.camera.far = light.shadow.camera.far;
			lShadow.camera.updateProjectionMatrix();
			lShadow.camera.updateWorldMatrix( true, false );
			lShadow.camera.updateMatrixWorld( true );
			this._shadowNodes[ i ].shadow.needsUpdate = true;

		}

	}

	/**
     * Updates the shadow map rendering.
     * @param {NodeFrame} frame - A reference to the current node frame.
     */
	updateShadow( frame ) {

		const { shadowMap, light } = this;
		const { renderer, scene, camera } = frame;
		const shadowType = renderer.shadowMap.type;
		const depthVersion = shadowMap.depthTexture.version;
		this._depthVersionCached = depthVersion;
		const currentRenderObjectFunction = renderer.getRenderObjectFunction();
		const currentMRT = renderer.getMRT();
		const useVelocity = currentMRT ? currentMRT.has( 'velocity' ) : false;

		_rendererState = resetRendererAndSceneState( renderer, scene, _rendererState );
		scene.overrideMaterial = getShadowMaterial( light );
		renderer.setRenderTarget( this.shadowMap );


		for ( let index = 0; index < this.lights.length; index ++ ) {

			const light = this.lights[ index ];
			const shadow = light.shadow;

			const _shadowCameraLayer = shadow.camera.layers.mask;
			_cameraLayers.push( _shadowCameraLayer );

			if ( ( shadow.camera.layers.mask & 0xFFFFFFFE ) === 0 ) {

				shadow.camera.layers.mask = camera.layers.mask;

			}

			shadow.updateMatrices( light );

			renderer.setRenderObjectFunction( getShadowRenderObjectFunction( renderer, shadow, shadowType, useVelocity ) );
			this.shadowMap.setSize( shadow.mapSize.width, shadow.mapSize.height, shadowMap.depth );

		}

		renderer.render( scene, this.cameraArray );
		renderer.setRenderObjectFunction( currentRenderObjectFunction );

		if ( light.isPointLight !== true && shadowType === VSMShadowMap ) {

			console.warn( 'THREE.TileShadowNode: VSM shadow map is not supported yet.' );
			// this.vsmPass( renderer );

		}

		restoreRendererAndSceneState( renderer, scene, _rendererState );

		for ( let index = 0; index < this.lights.length; index ++ ) {

			const light = this.lights[ index ];
			const shadow = light.shadow;

			shadow.camera.layers.mask = _cameraLayers[ index ];

		}

		_cameraLayers.length = 0;

	}

	/**
	 * The implementation performs the update of the shadow map if necessary.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
	updateBefore( frame ) {

		const shadow = this.originalLight.shadow;

		let needsUpdate = shadow.needsUpdate || shadow.autoUpdate;

		if ( needsUpdate ) {

			if ( this._cameraFrameId[ frame.camera ] === frame.frameId ) {

				needsUpdate = false;

			}

			this._cameraFrameId[ frame.camera ] = frame.frameId;

		}

		if ( needsUpdate ) {

			this.update();
			this.updateShadow( frame );

			if ( this.shadowMap.depthTexture.version === this._depthVersionCached ) {

				shadow.needsUpdate = false;

			}

		}

	}

	/**
	 * Synchronizes the transformation of a tile light with the source light.
	 *
	 * @param {LwLight} lwLight - The tile light to synchronize.
	 * @param {Light} sourceLight - The source light to copy transformations from.
	 */
	syncLightTransformation( lwLight, sourceLight ) {

		const sourceWorldPos = sourceLight.getWorldPosition( _vec3Temp1 );
		const targetWorldPos = sourceLight.target.getWorldPosition( _vec3Temp2 );
		const forward = _vec3Temp3.subVectors( targetWorldPos, sourceWorldPos );
		const targetDistance = forward.length();
		forward.normalize();
		lwLight.position.copy( sourceWorldPos );
		lwLight.target.position.copy( sourceWorldPos ).add( forward.multiplyScalar( targetDistance ) );
		lwLight.quaternion.copy( sourceLight.getWorldQuaternion( _quatTemp1 ) );
		lwLight.scale.copy( sourceLight.scale );
		lwLight.updateMatrix();
		lwLight.updateMatrixWorld( true );
		lwLight.target.updateMatrix();
		lwLight.target.updateMatrixWorld( true );

	}

	/**
	 * Sets up the shadow node for rendering.
	 *
	 * @param {Builder} builder - The builder used to set up the shadow node.
	 * @returns {Node} A node representing the shadow value.
	 */
	setup( builder ) {

		if ( this.lights.length === 0 ) {

			this.init( builder );

		}

		return Fn( ( builder ) => {

			this.setupShadowPosition( builder );
			return min( ...this._shadowNodes ).toVar( 'shadowValue' );

		} )();

	}

	/**
     * Helper method to remove lights and associated nodes/targets.
     * Used internally during dispose and potential re-initialization.
     */
	disposeLightsAndNodes() {

		for ( const light of this.lights ) {

			const parent = light.parent;
			if ( parent ) {

				parent.remove( light.target );
				parent.remove( light );

			}

		}

		this.lights = [];
		this._shadowNodes = [];

		if ( this.shadowMap ) {

			this.shadowMap.dispose(); // Disposes render target and textures
			this.shadowMap = null;

		}

	}


	dispose() {

		// Dispose lights, nodes, and shadow map
		this.disposeLightsAndNodes();
		super.dispose();

	}

}
```
</details>

#### Methods

##### `generateTiles(tilesX: number, tilesY: number): any[]`

<details><summary>Code</summary>

```ts
generateTiles( tilesX, tilesY ) {

		const tiles = [];
		const tileWidth = 1 / tilesX;
		const tileHeight = 1 / tilesY;

		for ( let y = 0; y < tilesY; y ++ ) {

			for ( let x = 0; x < tilesX; x ++ ) {

				tiles.push( {
					x: [ x * tileWidth, ( x + 1 ) * tileWidth ],
					y: [ ( tilesY - 1 - y ) * tileHeight, ( tilesY - y ) * tileHeight ], // Start from top row
					index: y * tilesX + x
				} );

			}

		}

		return tiles;

	}
```
</details>

##### `updateLightDirection(): void`

<details><summary>Code</summary>

```ts
updateLightDirection() {

		this.initialLightDirection.subVectors(
			this.originalLight.target.getWorldPosition( new Vector3() ),
			this.originalLight.getWorldPosition( new Vector3() )
		).normalize();

	}
```
</details>

##### `init(builder: Builder): void`

<details><summary>Code</summary>

```ts
init( builder ) {

		const light = this.originalLight;
		const parent = light.parent;

		const width = this.shadowSize.right - this.shadowSize.left;
		const height = this.shadowSize.top - this.shadowSize.bottom;

		const tileCount = this.tiles.length;
		const shadowWidth = this.config.resolution.width;
		const shadowHeight = this.config.resolution.height;

		// Clear existing lights/nodes if re-initializing
		this.disposeLightsAndNodes();

		const depthTexture = new DepthTexture( shadowWidth, shadowHeight, undefined, undefined, undefined, undefined, undefined, undefined, undefined, undefined, tileCount );
		depthTexture.compareFunction = LessCompare;
		depthTexture.name = 'ShadowDepthArrayTexture';
		const shadowMap = builder.createRenderTarget( shadowWidth, shadowHeight, { format: RedFormat, depth: tileCount } );
		shadowMap.depthTexture = depthTexture;
		shadowMap.texture.name = 'ShadowTexture';
		this.shadowMap = shadowMap;
		const cameras = [];


		// Create lights, one for each tile
		for ( let i = 0; i < tileCount; i ++ ) {

			const lwLight = new LwLight();
			lwLight.castShadow = true;
			const lShadow = light.shadow.clone();
			lShadow.filterNode = light.shadow.filterNode;
			const tile = this.tiles[ i ];
			lShadow.camera.left = this.shadowSize.left + width * tile.x[ 0 ];
			lShadow.camera.right = this.shadowSize.left + width * tile.x[ 1 ];
			lShadow.camera.top = this.shadowSize.bottom + height * tile.y[ 1 ];
			lShadow.camera.bottom = this.shadowSize.bottom + height * tile.y[ 0 ];
			lShadow.bias = light.shadow.bias;
			lShadow.camera.near = light.shadow.camera.near;
			lShadow.camera.far = light.shadow.camera.far;
			lShadow.camera.userData.tileIndex = i;
			lwLight.shadow = lShadow;

			if ( parent ) {

				parent.add( lwLight );
				parent.add( lwLight.target );

			} else {

				console.warn( 'TileShadowNode: Original light has no parent during init. Tile lights not added to scene graph directly.' );

			}

			this.syncLightTransformation( lwLight, light );

			this.lights.push( lwLight );
			lShadow.camera.updateMatrixWorld();

			cameras.push( lShadow.camera );
			const shadowNode = shadow( lwLight, lShadow );
			shadowNode.depthLayer = i;
			shadowNode.updateBeforeType = NodeUpdateType.NONE;

			shadowNode.setupRenderTarget = () => {

				return { shadowMap, depthTexture };

			};

			this._shadowNodes.push( shadowNode );

		}

		const cameraArray = new ArrayCamera( cameras );
		this.cameraArray = cameraArray;

	}
```
</details>

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		const light = this.originalLight;

		const shadowCam = light.shadow.camera;
		const lsMin = new Vector2( shadowCam.left, shadowCam.bottom );
		const lsMax = new Vector2( shadowCam.right, shadowCam.top );
		const fullWidth = lsMax.x - lsMin.x;
		const fullHeight = lsMax.y - lsMin.y;

		for ( let i = 0; i < this.lights.length; i ++ ) {

			const lwLight = this.lights[ i ];
			const tile = this.tiles[ i ];
			this.syncLightTransformation( lwLight, light );
			const lShadow = lwLight.shadow;
			const tileLeft = lsMin.x + tile.x[ 0 ] * fullWidth;
			const tileRight = lsMin.x + tile.x[ 1 ] * fullWidth;
			const tileBottom = lsMin.y + tile.y[ 0 ] * fullHeight;
			const tileTop = lsMin.y + tile.y[ 1 ] * fullHeight;
			lShadow.camera.left = tileLeft;
			lShadow.camera.right = tileRight;
			lShadow.camera.bottom = tileBottom;
			lShadow.camera.top = tileTop;
			lShadow.camera.near = light.shadow.camera.near;
			lShadow.camera.far = light.shadow.camera.far;
			lShadow.camera.updateProjectionMatrix();
			lShadow.camera.updateWorldMatrix( true, false );
			lShadow.camera.updateMatrixWorld( true );
			this._shadowNodes[ i ].shadow.needsUpdate = true;

		}

	}
```
</details>

##### `updateShadow(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
updateShadow( frame ) {

		const { shadowMap, light } = this;
		const { renderer, scene, camera } = frame;
		const shadowType = renderer.shadowMap.type;
		const depthVersion = shadowMap.depthTexture.version;
		this._depthVersionCached = depthVersion;
		const currentRenderObjectFunction = renderer.getRenderObjectFunction();
		const currentMRT = renderer.getMRT();
		const useVelocity = currentMRT ? currentMRT.has( 'velocity' ) : false;

		_rendererState = resetRendererAndSceneState( renderer, scene, _rendererState );
		scene.overrideMaterial = getShadowMaterial( light );
		renderer.setRenderTarget( this.shadowMap );


		for ( let index = 0; index < this.lights.length; index ++ ) {

			const light = this.lights[ index ];
			const shadow = light.shadow;

			const _shadowCameraLayer = shadow.camera.layers.mask;
			_cameraLayers.push( _shadowCameraLayer );

			if ( ( shadow.camera.layers.mask & 0xFFFFFFFE ) === 0 ) {

				shadow.camera.layers.mask = camera.layers.mask;

			}

			shadow.updateMatrices( light );

			renderer.setRenderObjectFunction( getShadowRenderObjectFunction( renderer, shadow, shadowType, useVelocity ) );
			this.shadowMap.setSize( shadow.mapSize.width, shadow.mapSize.height, shadowMap.depth );

		}

		renderer.render( scene, this.cameraArray );
		renderer.setRenderObjectFunction( currentRenderObjectFunction );

		if ( light.isPointLight !== true && shadowType === VSMShadowMap ) {

			console.warn( 'THREE.TileShadowNode: VSM shadow map is not supported yet.' );
			// this.vsmPass( renderer );

		}

		restoreRendererAndSceneState( renderer, scene, _rendererState );

		for ( let index = 0; index < this.lights.length; index ++ ) {

			const light = this.lights[ index ];
			const shadow = light.shadow;

			shadow.camera.layers.mask = _cameraLayers[ index ];

		}

		_cameraLayers.length = 0;

	}
```
</details>

##### `updateBefore(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		const shadow = this.originalLight.shadow;

		let needsUpdate = shadow.needsUpdate || shadow.autoUpdate;

		if ( needsUpdate ) {

			if ( this._cameraFrameId[ frame.camera ] === frame.frameId ) {

				needsUpdate = false;

			}

			this._cameraFrameId[ frame.camera ] = frame.frameId;

		}

		if ( needsUpdate ) {

			this.update();
			this.updateShadow( frame );

			if ( this.shadowMap.depthTexture.version === this._depthVersionCached ) {

				shadow.needsUpdate = false;

			}

		}

	}
```
</details>

##### `syncLightTransformation(lwLight: LwLight, sourceLight: Light): void`

<details><summary>Code</summary>

```ts
syncLightTransformation( lwLight, sourceLight ) {

		const sourceWorldPos = sourceLight.getWorldPosition( _vec3Temp1 );
		const targetWorldPos = sourceLight.target.getWorldPosition( _vec3Temp2 );
		const forward = _vec3Temp3.subVectors( targetWorldPos, sourceWorldPos );
		const targetDistance = forward.length();
		forward.normalize();
		lwLight.position.copy( sourceWorldPos );
		lwLight.target.position.copy( sourceWorldPos ).add( forward.multiplyScalar( targetDistance ) );
		lwLight.quaternion.copy( sourceLight.getWorldQuaternion( _quatTemp1 ) );
		lwLight.scale.copy( sourceLight.scale );
		lwLight.updateMatrix();
		lwLight.updateMatrixWorld( true );
		lwLight.target.updateMatrix();
		lwLight.target.updateMatrixWorld( true );

	}
```
</details>

##### `setup(builder: Builder): Node`

<details><summary>Code</summary>

```ts
setup( builder ) {

		if ( this.lights.length === 0 ) {

			this.init( builder );

		}

		return Fn( ( builder ) => {

			this.setupShadowPosition( builder );
			return min( ...this._shadowNodes ).toVar( 'shadowValue' );

		} )();

	}
```
</details>

##### `disposeLightsAndNodes(): void`

<details><summary>Code</summary>

```ts
disposeLightsAndNodes() {

		for ( const light of this.lights ) {

			const parent = light.parent;
			if ( parent ) {

				parent.remove( light.target );
				parent.remove( light );

			}

		}

		this.lights = [];
		this._shadowNodes = [];

		if ( this.shadowMap ) {

			this.shadowMap.dispose(); // Disposes render target and textures
			this.shadowMap = null;

		}

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		// Dispose lights, nodes, and shadow map
		this.disposeLightsAndNodes();
		super.dispose();

	}
```
</details>


---