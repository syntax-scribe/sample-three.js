[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Background.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 🧱 Classes | 1 |
| 📦 Imports | 13 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/Background.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DataMap` | `./DataMap.js` |
| `Color4` | `./Color4.js` |
| `vec4` | `../../nodes/TSL.js` |
| `context` | `../../nodes/TSL.js` |
| `normalWorldGeometry` | `../../nodes/TSL.js` |
| `backgroundBlurriness` | `../../nodes/TSL.js` |
| `backgroundIntensity` | `../../nodes/TSL.js` |
| `backgroundRotation` | `../../nodes/TSL.js` |
| `modelViewProjection` | `../../nodes/TSL.js` |
| `NodeMaterial` | `../../materials/nodes/NodeMaterial.js` |
| `Mesh` | `../../objects/Mesh.js` |
| `SphereGeometry` | `../../geometries/SphereGeometry.js` |
| `BackSide` | `../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_clearColor` | `Color4` | let/var | `new Color4()` | ✗ |
| `renderer` | `Renderer` | let/var | `this.renderer` | ✗ |
| `background` | `any` | let/var | `this.nodes.getBackgroundNode( scene ) \|\| scene.background` | ✗ |
| `forceClear` | `boolean` | let/var | `false` | ✗ |
| `backgroundNode` | `any` | let/var | `background` | ✗ |
| `backgroundMesh` | `any` | let/var | `sceneData.backgroundMesh` | ✗ |
| `viewProj` | `VaryingNode<vec4>` | let/var | `modelViewProjection` | ✗ |
| `nodeMaterial` | `NodeMaterial` | let/var | `new NodeMaterial()` | ✗ |
| `clearColorValue` | `any` | let/var | `renderContext.clearColorValue` | ✗ |


---

## Functions

### `Background.update(scene: Scene, renderList: RenderList, renderContext: RenderContext): void`

**JSDoc:**
```typescript
/**
	 * Updates the background for the given scene. Depending on how `Scene.background`
	 * or `Scene.backgroundNode` are configured, this method might configure a simple clear
	 * or add a mesh to the render list for rendering the background as a textured plane
	 * or skybox.
	 *
	 * @param {Scene} scene - The scene.
	 * @param {RenderList} renderList - The current render list.
	 * @param {RenderContext} renderContext - The current render context.
	 */
```

**Parameters:**

- **`scene`** `Scene`
- **`renderList`** `RenderList`
- **`renderContext`** `RenderContext`

**Returns:** `void`

**Calls:**

- `this.nodes.getBackgroundNode`
- `renderer._clearColor.getRGB`
- `background.getRGB`
- `this.get`
- `_clearColor.copy`
- `context (from ../../nodes/TSL.js)`
- `vec4( backgroundNode ).mul`
- `backgroundRotation.mul`
- `viewProj.setZ`
- `this.matrixWorld.copyPosition`
- `background.removeEventListener`
- `backgroundMesh.material.dispose`
- `backgroundMesh.geometry.dispose`
- `background.addEventListener`
- `backgroundNode.getCacheKey`
- `renderList.unshift`
- `console.error`
- `renderer.xr.getEnvironmentBlendMode`
- `_clearColor.set`

**Internal Comments:**
```
// no background settings, use clear color configuration from the renderer (x5)
// background is an opaque color (x4)
// @TODO: Add Texture2D support using node context (x2)
// (x7)
// premultiply alpha
```

<details><summary>Code</summary>

```typescript
update( scene, renderList, renderContext ) {

		const renderer = this.renderer;
		const background = this.nodes.getBackgroundNode( scene ) || scene.background;

		let forceClear = false;

		if ( background === null ) {

			// no background settings, use clear color configuration from the renderer

			renderer._clearColor.getRGB( _clearColor );
			_clearColor.a = renderer._clearColor.a;

		} else if ( background.isColor === true ) {

			// background is an opaque color

			background.getRGB( _clearColor );
			_clearColor.a = 1;

			forceClear = true;

		} else if ( background.isNode === true ) {

			const sceneData = this.get( scene );
			const backgroundNode = background;

			_clearColor.copy( renderer._clearColor );

			let backgroundMesh = sceneData.backgroundMesh;

			if ( backgroundMesh === undefined ) {

				const backgroundMeshNode = context( vec4( backgroundNode ).mul( backgroundIntensity ), {
					// @TODO: Add Texture2D support using node context
					getUV: () => backgroundRotation.mul( normalWorldGeometry ),
					getTextureLevel: () => backgroundBlurriness
				} );

				let viewProj = modelViewProjection;
				viewProj = viewProj.setZ( viewProj.w );

				const nodeMaterial = new NodeMaterial();
				nodeMaterial.name = 'Background.material';
				nodeMaterial.side = BackSide;
				nodeMaterial.depthTest = false;
				nodeMaterial.depthWrite = false;
				nodeMaterial.allowOverride = false;
				nodeMaterial.fog = false;
				nodeMaterial.lights = false;
				nodeMaterial.vertexNode = viewProj;
				nodeMaterial.colorNode = backgroundMeshNode;

				sceneData.backgroundMeshNode = backgroundMeshNode;
				sceneData.backgroundMesh = backgroundMesh = new Mesh( new SphereGeometry( 1, 32, 32 ), nodeMaterial );
				backgroundMesh.frustumCulled = false;
				backgroundMesh.name = 'Background.mesh';

				backgroundMesh.onBeforeRender = function ( renderer, scene, camera ) {

					this.matrixWorld.copyPosition( camera.matrixWorld );

				};

				function onBackgroundDispose() {

					background.removeEventListener( 'dispose', onBackgroundDispose );

					backgroundMesh.material.dispose();
					backgroundMesh.geometry.dispose();

				}

				background.addEventListener( 'dispose', onBackgroundDispose );

			}

			const backgroundCacheKey = backgroundNode.getCacheKey();

			if ( sceneData.backgroundCacheKey !== backgroundCacheKey ) {

				sceneData.backgroundMeshNode.node = vec4( backgroundNode ).mul( backgroundIntensity );
				sceneData.backgroundMeshNode.needsUpdate = true;

				backgroundMesh.material.needsUpdate = true;

				sceneData.backgroundCacheKey = backgroundCacheKey;

			}

			renderList.unshift( backgroundMesh, backgroundMesh.geometry, backgroundMesh.material, 0, 0, null, null );

		} else {

			console.error( 'THREE.Renderer: Unsupported background configuration.', background );

		}

		//

		const environmentBlendMode = renderer.xr.getEnvironmentBlendMode();

		if ( environmentBlendMode === 'additive' ) {

			_clearColor.set( 0, 0, 0, 1 );

		} else if ( environmentBlendMode === 'alpha-blend' ) {

			_clearColor.set( 0, 0, 0, 0 );

		}

		//

		if ( renderer.autoClear === true || forceClear === true ) {

			const clearColorValue = renderContext.clearColorValue;

			clearColorValue.r = _clearColor.r;
			clearColorValue.g = _clearColor.g;
			clearColorValue.b = _clearColor.b;
			clearColorValue.a = _clearColor.a;

			// premultiply alpha

			if ( renderer.backend.isWebGLBackend === true || renderer.alpha === true ) {

				clearColorValue.r *= clearColorValue.a;
				clearColorValue.g *= clearColorValue.a;
				clearColorValue.b *= clearColorValue.a;

			}

			//

			renderContext.depthClearValue = renderer._clearDepth;
			renderContext.stencilClearValue = renderer._clearStencil;

			renderContext.clearColor = renderer.autoClearColor === true;
			renderContext.clearDepth = renderer.autoClearDepth === true;
			renderContext.clearStencil = renderer.autoClearStencil === true;

		} else {

			renderContext.clearColor = false;
			renderContext.clearDepth = false;
			renderContext.clearStencil = false;

		}

	}
```
</details>

### `getUV(): any`

**Returns:** `any`

**Calls:**

- `backgroundRotation.mul`

<details><summary>Code</summary>

```typescript
() => backgroundRotation.mul( normalWorldGeometry )
```
</details>

### `getTextureLevel(): SceneNode`

**Returns:** `SceneNode`

<details><summary>Code</summary>

```typescript
() => backgroundBlurriness
```
</details>

### `getUV(): any`

**Returns:** `any`

**Calls:**

- `backgroundRotation.mul`

<details><summary>Code</summary>

```typescript
() => backgroundRotation.mul( normalWorldGeometry )
```
</details>

### `getTextureLevel(): SceneNode`

**Returns:** `SceneNode`

<details><summary>Code</summary>

```typescript
() => backgroundBlurriness
```
</details>

### `getUV(): any`

**Returns:** `any`

**Calls:**

- `backgroundRotation.mul`

<details><summary>Code</summary>

```typescript
() => backgroundRotation.mul( normalWorldGeometry )
```
</details>

### `getTextureLevel(): SceneNode`

**Returns:** `SceneNode`

<details><summary>Code</summary>

```typescript
() => backgroundBlurriness
```
</details>

### `getUV(): any`

**Returns:** `any`

**Calls:**

- `backgroundRotation.mul`

<details><summary>Code</summary>

```typescript
() => backgroundRotation.mul( normalWorldGeometry )
```
</details>

### `getTextureLevel(): SceneNode`

**Returns:** `SceneNode`

<details><summary>Code</summary>

```typescript
() => backgroundBlurriness
```
</details>

### `onBackgroundDispose(): void`

**Returns:** `void`

**Calls:**

- `background.removeEventListener`
- `backgroundMesh.material.dispose`
- `backgroundMesh.geometry.dispose`

<details><summary>Code</summary>

```typescript
function onBackgroundDispose() {

					background.removeEventListener( 'dispose', onBackgroundDispose );

					backgroundMesh.material.dispose();
					backgroundMesh.geometry.dispose();

				}
```
</details>


---

## Classes

### `Background`

<details><summary>Class Code</summary>

```ts
class Background extends DataMap {

	/**
	 * Constructs a new background management component.
	 *
	 * @param {Renderer} renderer - The renderer.
	 * @param {Nodes} nodes - Renderer component for managing nodes related logic.
	 */
	constructor( renderer, nodes ) {

		super();

		/**
		 * The renderer.
		 *
		 * @type {Renderer}
		 */
		this.renderer = renderer;

		/**
		 * Renderer component for managing nodes related logic.
		 *
		 * @type {Nodes}
		 */
		this.nodes = nodes;

	}

	/**
	 * Updates the background for the given scene. Depending on how `Scene.background`
	 * or `Scene.backgroundNode` are configured, this method might configure a simple clear
	 * or add a mesh to the render list for rendering the background as a textured plane
	 * or skybox.
	 *
	 * @param {Scene} scene - The scene.
	 * @param {RenderList} renderList - The current render list.
	 * @param {RenderContext} renderContext - The current render context.
	 */
	update( scene, renderList, renderContext ) {

		const renderer = this.renderer;
		const background = this.nodes.getBackgroundNode( scene ) || scene.background;

		let forceClear = false;

		if ( background === null ) {

			// no background settings, use clear color configuration from the renderer

			renderer._clearColor.getRGB( _clearColor );
			_clearColor.a = renderer._clearColor.a;

		} else if ( background.isColor === true ) {

			// background is an opaque color

			background.getRGB( _clearColor );
			_clearColor.a = 1;

			forceClear = true;

		} else if ( background.isNode === true ) {

			const sceneData = this.get( scene );
			const backgroundNode = background;

			_clearColor.copy( renderer._clearColor );

			let backgroundMesh = sceneData.backgroundMesh;

			if ( backgroundMesh === undefined ) {

				const backgroundMeshNode = context( vec4( backgroundNode ).mul( backgroundIntensity ), {
					// @TODO: Add Texture2D support using node context
					getUV: () => backgroundRotation.mul( normalWorldGeometry ),
					getTextureLevel: () => backgroundBlurriness
				} );

				let viewProj = modelViewProjection;
				viewProj = viewProj.setZ( viewProj.w );

				const nodeMaterial = new NodeMaterial();
				nodeMaterial.name = 'Background.material';
				nodeMaterial.side = BackSide;
				nodeMaterial.depthTest = false;
				nodeMaterial.depthWrite = false;
				nodeMaterial.allowOverride = false;
				nodeMaterial.fog = false;
				nodeMaterial.lights = false;
				nodeMaterial.vertexNode = viewProj;
				nodeMaterial.colorNode = backgroundMeshNode;

				sceneData.backgroundMeshNode = backgroundMeshNode;
				sceneData.backgroundMesh = backgroundMesh = new Mesh( new SphereGeometry( 1, 32, 32 ), nodeMaterial );
				backgroundMesh.frustumCulled = false;
				backgroundMesh.name = 'Background.mesh';

				backgroundMesh.onBeforeRender = function ( renderer, scene, camera ) {

					this.matrixWorld.copyPosition( camera.matrixWorld );

				};

				function onBackgroundDispose() {

					background.removeEventListener( 'dispose', onBackgroundDispose );

					backgroundMesh.material.dispose();
					backgroundMesh.geometry.dispose();

				}

				background.addEventListener( 'dispose', onBackgroundDispose );

			}

			const backgroundCacheKey = backgroundNode.getCacheKey();

			if ( sceneData.backgroundCacheKey !== backgroundCacheKey ) {

				sceneData.backgroundMeshNode.node = vec4( backgroundNode ).mul( backgroundIntensity );
				sceneData.backgroundMeshNode.needsUpdate = true;

				backgroundMesh.material.needsUpdate = true;

				sceneData.backgroundCacheKey = backgroundCacheKey;

			}

			renderList.unshift( backgroundMesh, backgroundMesh.geometry, backgroundMesh.material, 0, 0, null, null );

		} else {

			console.error( 'THREE.Renderer: Unsupported background configuration.', background );

		}

		//

		const environmentBlendMode = renderer.xr.getEnvironmentBlendMode();

		if ( environmentBlendMode === 'additive' ) {

			_clearColor.set( 0, 0, 0, 1 );

		} else if ( environmentBlendMode === 'alpha-blend' ) {

			_clearColor.set( 0, 0, 0, 0 );

		}

		//

		if ( renderer.autoClear === true || forceClear === true ) {

			const clearColorValue = renderContext.clearColorValue;

			clearColorValue.r = _clearColor.r;
			clearColorValue.g = _clearColor.g;
			clearColorValue.b = _clearColor.b;
			clearColorValue.a = _clearColor.a;

			// premultiply alpha

			if ( renderer.backend.isWebGLBackend === true || renderer.alpha === true ) {

				clearColorValue.r *= clearColorValue.a;
				clearColorValue.g *= clearColorValue.a;
				clearColorValue.b *= clearColorValue.a;

			}

			//

			renderContext.depthClearValue = renderer._clearDepth;
			renderContext.stencilClearValue = renderer._clearStencil;

			renderContext.clearColor = renderer.autoClearColor === true;
			renderContext.clearDepth = renderer.autoClearDepth === true;
			renderContext.clearStencil = renderer.autoClearStencil === true;

		} else {

			renderContext.clearColor = false;
			renderContext.clearDepth = false;
			renderContext.clearStencil = false;

		}

	}

}
```
</details>

#### Methods

##### `update(scene: Scene, renderList: RenderList, renderContext: RenderContext): void`

<details><summary>Code</summary>

```ts
update( scene, renderList, renderContext ) {

		const renderer = this.renderer;
		const background = this.nodes.getBackgroundNode( scene ) || scene.background;

		let forceClear = false;

		if ( background === null ) {

			// no background settings, use clear color configuration from the renderer

			renderer._clearColor.getRGB( _clearColor );
			_clearColor.a = renderer._clearColor.a;

		} else if ( background.isColor === true ) {

			// background is an opaque color

			background.getRGB( _clearColor );
			_clearColor.a = 1;

			forceClear = true;

		} else if ( background.isNode === true ) {

			const sceneData = this.get( scene );
			const backgroundNode = background;

			_clearColor.copy( renderer._clearColor );

			let backgroundMesh = sceneData.backgroundMesh;

			if ( backgroundMesh === undefined ) {

				const backgroundMeshNode = context( vec4( backgroundNode ).mul( backgroundIntensity ), {
					// @TODO: Add Texture2D support using node context
					getUV: () => backgroundRotation.mul( normalWorldGeometry ),
					getTextureLevel: () => backgroundBlurriness
				} );

				let viewProj = modelViewProjection;
				viewProj = viewProj.setZ( viewProj.w );

				const nodeMaterial = new NodeMaterial();
				nodeMaterial.name = 'Background.material';
				nodeMaterial.side = BackSide;
				nodeMaterial.depthTest = false;
				nodeMaterial.depthWrite = false;
				nodeMaterial.allowOverride = false;
				nodeMaterial.fog = false;
				nodeMaterial.lights = false;
				nodeMaterial.vertexNode = viewProj;
				nodeMaterial.colorNode = backgroundMeshNode;

				sceneData.backgroundMeshNode = backgroundMeshNode;
				sceneData.backgroundMesh = backgroundMesh = new Mesh( new SphereGeometry( 1, 32, 32 ), nodeMaterial );
				backgroundMesh.frustumCulled = false;
				backgroundMesh.name = 'Background.mesh';

				backgroundMesh.onBeforeRender = function ( renderer, scene, camera ) {

					this.matrixWorld.copyPosition( camera.matrixWorld );

				};

				function onBackgroundDispose() {

					background.removeEventListener( 'dispose', onBackgroundDispose );

					backgroundMesh.material.dispose();
					backgroundMesh.geometry.dispose();

				}

				background.addEventListener( 'dispose', onBackgroundDispose );

			}

			const backgroundCacheKey = backgroundNode.getCacheKey();

			if ( sceneData.backgroundCacheKey !== backgroundCacheKey ) {

				sceneData.backgroundMeshNode.node = vec4( backgroundNode ).mul( backgroundIntensity );
				sceneData.backgroundMeshNode.needsUpdate = true;

				backgroundMesh.material.needsUpdate = true;

				sceneData.backgroundCacheKey = backgroundCacheKey;

			}

			renderList.unshift( backgroundMesh, backgroundMesh.geometry, backgroundMesh.material, 0, 0, null, null );

		} else {

			console.error( 'THREE.Renderer: Unsupported background configuration.', background );

		}

		//

		const environmentBlendMode = renderer.xr.getEnvironmentBlendMode();

		if ( environmentBlendMode === 'additive' ) {

			_clearColor.set( 0, 0, 0, 1 );

		} else if ( environmentBlendMode === 'alpha-blend' ) {

			_clearColor.set( 0, 0, 0, 0 );

		}

		//

		if ( renderer.autoClear === true || forceClear === true ) {

			const clearColorValue = renderContext.clearColorValue;

			clearColorValue.r = _clearColor.r;
			clearColorValue.g = _clearColor.g;
			clearColorValue.b = _clearColor.b;
			clearColorValue.a = _clearColor.a;

			// premultiply alpha

			if ( renderer.backend.isWebGLBackend === true || renderer.alpha === true ) {

				clearColorValue.r *= clearColorValue.a;
				clearColorValue.g *= clearColorValue.a;
				clearColorValue.b *= clearColorValue.a;

			}

			//

			renderContext.depthClearValue = renderer._clearDepth;
			renderContext.stencilClearValue = renderer._clearStencil;

			renderContext.clearColor = renderer.autoClearColor === true;
			renderContext.clearDepth = renderer.autoClearDepth === true;
			renderContext.clearStencil = renderer.autoClearStencil === true;

		} else {

			renderContext.clearColor = false;
			renderContext.clearDepth = false;
			renderContext.clearStencil = false;

		}

	}
```
</details>


---