[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Nodes.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 25 |
| 🧱 Classes | 1 |
| 📦 Imports | 23 |
| 📊 Variables & Constants | 24 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/nodes/Nodes.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DataMap` | `../DataMap.js` |
| `ChainMap` | `../ChainMap.js` |
| `NodeBuilderState` | `./NodeBuilderState.js` |
| `cubeMapNode` | `../../../nodes/utils/CubeMapNode.js` |
| `NodeFrame` | `../../../nodes/Nodes.js` |
| `objectGroup` | `../../../nodes/TSL.js` |
| `renderGroup` | `../../../nodes/TSL.js` |
| `frameGroup` | `../../../nodes/TSL.js` |
| `cubeTexture` | `../../../nodes/TSL.js` |
| `texture` | `../../../nodes/TSL.js` |
| `texture3D` | `../../../nodes/TSL.js` |
| `vec3` | `../../../nodes/TSL.js` |
| `fog` | `../../../nodes/TSL.js` |
| `rangeFogFactor` | `../../../nodes/TSL.js` |
| `densityFogFactor` | `../../../nodes/TSL.js` |
| `reference` | `../../../nodes/TSL.js` |
| `pmremTexture` | `../../../nodes/TSL.js` |
| `screenUV` | `../../../nodes/TSL.js` |
| `builtin` | `../../../nodes/accessors/BuiltinNode.js` |
| `CubeUVReflectionMapping` | `../../../constants.js` |
| `EquirectangularReflectionMapping` | `../../../constants.js` |
| `EquirectangularRefractionMapping` | `../../../constants.js` |
| `hashArray` | `../../../nodes/core/NodeUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_outputNodeMap` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `_chainKeys` | `any[]` | let/var | `[]` | ✗ |
| `_cacheKeyValues` | `any[]` | let/var | `[]` | ✗ |
| `groupNode` | `any` | let/var | `nodeUniformsGroup.groupNode` | ✗ |
| `name` | `any` | let/var | `groupNode.name` | ✗ |
| `renderId` | `any` | let/var | `this.nodeFrame.renderId` | ✗ |
| `frameId` | `any` | let/var | `this.nodeFrame.frameId` | ✗ |
| `nodeBuilderState` | `any` | let/var | `renderObjectData.nodeBuilderState` | ✗ |
| `nodeBuilderState` | `any` | let/var | `this.get( object ).nodeBuilderState` | ✗ |
| `nodeBuilderState` | `any` | let/var | `computeData.nodeBuilderState` | ✗ |
| `environmentNode` | `any` | let/var | `null` | ✗ |
| `backgroundNode` | `any` | let/var | `null` | ✗ |
| `callId` | `any` | let/var | `this.renderer.info.calls` | ✗ |
| `cacheKeyData` | `any` | let/var | `this.callHashCache.get( _chainKeys ) \|\| {}` | ✗ |
| `background` | `any` | let/var | `scene.background` | ✗ |
| `forceUpdate` | `boolean` | let/var | `( scene.backgroundBlurriness === 0 && sceneData.backgroundBlurriness > 0 ) \|...` | ✗ |
| `envMap` | `any` | let/var | `*not shown*` | ✗ |
| `nodeCache` | `WeakMap<any, any>` | let/var | `this.cacheLib[ type ] \|\| ( this.cacheLib[ type ] = new WeakMap() )` | ✗ |
| `sceneFog` | `any` | let/var | `scene.fog` | ✗ |
| `environment` | `any` | let/var | `scene.environment` | ✗ |
| `nodeFrame` | `Renderer` | let/var | `this.nodeFrame` | ✗ |
| `renderer` | `Renderer` | let/var | `this.renderer` | ✗ |
| `renderer` | `Renderer` | let/var | `this.renderer` | ✗ |
| `output` | `any` | let/var | `outputTarget.isArrayTexture ? texture3D( outputTarget, vec3( screenUV, builti...` | ✗ |


---

## Functions

### `Nodes.updateGroup(nodeUniformsGroup: NodeUniformsGroup): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given node uniforms group must be updated or not.
	 *
	 * @param {NodeUniformsGroup} nodeUniformsGroup - The node uniforms group.
	 * @return {boolean} Whether the node uniforms group requires an update or not.
	 */
```

**Parameters:**

- **`nodeUniformsGroup`** `NodeUniformsGroup`

**Returns:** `boolean`

**Calls:**

- `this.get`
- `this.groupsData.get`
- `this.groupsData.set`

**Internal Comments:**
```
// objectGroup is always updated
// renderGroup is updated once per render/compute call
// frameGroup is updated once per frame
// other groups are updated just when groupNode.needsUpdate is true (x4)
```

<details><summary>Code</summary>

```typescript
updateGroup( nodeUniformsGroup ) {

		const groupNode = nodeUniformsGroup.groupNode;
		const name = groupNode.name;

		// objectGroup is always updated

		if ( name === objectGroup.name ) return true;

		// renderGroup is updated once per render/compute call

		if ( name === renderGroup.name ) {

			const uniformsGroupData = this.get( nodeUniformsGroup );
			const renderId = this.nodeFrame.renderId;

			if ( uniformsGroupData.renderId !== renderId ) {

				uniformsGroupData.renderId = renderId;

				return true;

			}

			return false;

		}

		// frameGroup is updated once per frame

		if ( name === frameGroup.name ) {

			const uniformsGroupData = this.get( nodeUniformsGroup );
			const frameId = this.nodeFrame.frameId;

			if ( uniformsGroupData.frameId !== frameId ) {

				uniformsGroupData.frameId = frameId;

				return true;

			}

			return false;

		}

		// other groups are updated just when groupNode.needsUpdate is true

		_chainKeys[ 0 ] = groupNode;
		_chainKeys[ 1 ] = nodeUniformsGroup;

		let groupData = this.groupsData.get( _chainKeys );
		if ( groupData === undefined ) this.groupsData.set( _chainKeys, groupData = {} );

		_chainKeys.length = 0;

		if ( groupData.version !== groupNode.version ) {

			groupData.version = groupNode.version;

			return true;

		}

		return false;

	}
```
</details>

### `Nodes.getForRenderCacheKey(renderObject: RenderObject): number`

**JSDoc:**
```typescript
/**
	 * Returns the cache key for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {number} The cache key.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getForRenderCacheKey( renderObject ) {

		return renderObject.initialCacheKey;

	}
```
</details>

### `Nodes.getForRender(renderObject: RenderObject): NodeBuilderState`

**JSDoc:**
```typescript
/**
	 * Returns a node builder state for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {NodeBuilderState} The node builder state.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `NodeBuilderState`

**Calls:**

- `this.get`
- `this.getForRenderCacheKey`
- `nodeBuilderCache.get`
- `this.backend.createNodeBuilder`
- `this.getEnvironmentNode`
- `this.getFogNode`
- `this.renderer.getOutputRenderTarget`
- `nodeBuilder.enableMultiview`
- `nodeBuilder.build`
- `this._createNodeBuilderState`
- `nodeBuilderCache.set`

<details><summary>Code</summary>

```typescript
getForRender( renderObject ) {

		const renderObjectData = this.get( renderObject );

		let nodeBuilderState = renderObjectData.nodeBuilderState;

		if ( nodeBuilderState === undefined ) {

			const { nodeBuilderCache } = this;

			const cacheKey = this.getForRenderCacheKey( renderObject );

			nodeBuilderState = nodeBuilderCache.get( cacheKey );

			if ( nodeBuilderState === undefined ) {

				const nodeBuilder = this.backend.createNodeBuilder( renderObject.object, this.renderer );
				nodeBuilder.scene = renderObject.scene;
				nodeBuilder.material = renderObject.material;
				nodeBuilder.camera = renderObject.camera;
				nodeBuilder.context.material = renderObject.material;
				nodeBuilder.lightsNode = renderObject.lightsNode;
				nodeBuilder.environmentNode = this.getEnvironmentNode( renderObject.scene );
				nodeBuilder.fogNode = this.getFogNode( renderObject.scene );
				nodeBuilder.clippingContext = renderObject.clippingContext;
				if ( this.renderer.getOutputRenderTarget() ? this.renderer.getOutputRenderTarget().multiview : false ) {

					nodeBuilder.enableMultiview();

				}

				nodeBuilder.build();

				nodeBuilderState = this._createNodeBuilderState( nodeBuilder );

				nodeBuilderCache.set( cacheKey, nodeBuilderState );

			}

			nodeBuilderState.usedTimes ++;

			renderObjectData.nodeBuilderState = nodeBuilderState;

		}

		return nodeBuilderState;

	}
```
</details>

### `Nodes.delete(object: any): any`

**JSDoc:**
```typescript
/**
	 * Deletes the given object from the internal data map
	 *
	 * @param {any} object - The object to delete.
	 * @return {?Object} The deleted dictionary.
	 */
```

**Parameters:**

- **`object`** `any`

**Returns:** `any`

**Calls:**

- `this.get`
- `this.nodeBuilderCache.delete`
- `this.getForRenderCacheKey`
- `super.delete`

<details><summary>Code</summary>

```typescript
delete( object ) {

		if ( object.isRenderObject ) {

			const nodeBuilderState = this.get( object ).nodeBuilderState;
			nodeBuilderState.usedTimes --;

			if ( nodeBuilderState.usedTimes === 0 ) {

				this.nodeBuilderCache.delete( this.getForRenderCacheKey( object ) );

			}

		}

		return super.delete( object );

	}
```
</details>

### `Nodes.getForCompute(computeNode: Node): NodeBuilderState`

**JSDoc:**
```typescript
/**
	 * Returns a node builder state for the given compute node.
	 *
	 * @param {Node} computeNode - The compute node.
	 * @return {NodeBuilderState} The node builder state.
	 */
```

**Parameters:**

- **`computeNode`** `Node`

**Returns:** `NodeBuilderState`

**Calls:**

- `this.get`
- `this.backend.createNodeBuilder`
- `nodeBuilder.build`
- `this._createNodeBuilderState`

<details><summary>Code</summary>

```typescript
getForCompute( computeNode ) {

		const computeData = this.get( computeNode );

		let nodeBuilderState = computeData.nodeBuilderState;

		if ( nodeBuilderState === undefined ) {

			const nodeBuilder = this.backend.createNodeBuilder( computeNode, this.renderer );
			nodeBuilder.build();

			nodeBuilderState = this._createNodeBuilderState( nodeBuilder );

			computeData.nodeBuilderState = nodeBuilderState;

		}

		return nodeBuilderState;

	}
```
</details>

### `Nodes._createNodeBuilderState(nodeBuilder: NodeBuilder): NodeBuilderState`

**JSDoc:**
```typescript
/**
	 * Creates a node builder state for the given node builder.
	 *
	 * @private
	 * @param {NodeBuilder} nodeBuilder - The node builder.
	 * @return {NodeBuilderState} The node builder state.
	 */
```

**Parameters:**

- **`nodeBuilder`** `NodeBuilder`

**Returns:** `NodeBuilderState`

**Calls:**

- `nodeBuilder.getAttributesArray`
- `nodeBuilder.getBindings`

<details><summary>Code</summary>

```typescript
_createNodeBuilderState( nodeBuilder ) {

		return new NodeBuilderState(
			nodeBuilder.vertexShader,
			nodeBuilder.fragmentShader,
			nodeBuilder.computeShader,
			nodeBuilder.getAttributesArray(),
			nodeBuilder.getBindings(),
			nodeBuilder.updateNodes,
			nodeBuilder.updateBeforeNodes,
			nodeBuilder.updateAfterNodes,
			nodeBuilder.observer,
			nodeBuilder.transforms
		);

	}
```
</details>

### `Nodes.getEnvironmentNode(scene: Scene): Node`

**JSDoc:**
```typescript
/**
	 * Returns an environment node for the current configured
	 * scene environment.
	 *
	 * @param {Scene} scene - The scene.
	 * @return {Node} A node representing the current scene environment.
	 */
```

**Parameters:**

- **`scene`** `Scene`

**Returns:** `Node`

**Calls:**

- `this.updateEnvironment`
- `this.get`

<details><summary>Code</summary>

```typescript
getEnvironmentNode( scene ) {

		this.updateEnvironment( scene );

		let environmentNode = null;

		if ( scene.environmentNode && scene.environmentNode.isNode ) {

			environmentNode = scene.environmentNode;

		} else {

			const sceneData = this.get( scene );

			if ( sceneData.environmentNode ) {

				environmentNode = sceneData.environmentNode;

			}

		}

		return environmentNode;

	}
```
</details>

### `Nodes.getBackgroundNode(scene: Scene): Node`

**JSDoc:**
```typescript
/**
	 * Returns a background node for the current configured
	 * scene background.
	 *
	 * @param {Scene} scene - The scene.
	 * @return {Node} A node representing the current scene background.
	 */
```

**Parameters:**

- **`scene`** `Scene`

**Returns:** `Node`

**Calls:**

- `this.updateBackground`
- `this.get`

<details><summary>Code</summary>

```typescript
getBackgroundNode( scene ) {

		this.updateBackground( scene );

		let backgroundNode = null;

		if ( scene.backgroundNode && scene.backgroundNode.isNode ) {

			backgroundNode = scene.backgroundNode;

		} else {

			const sceneData = this.get( scene );

			if ( sceneData.backgroundNode ) {

				backgroundNode = sceneData.backgroundNode;

			}

		}

		return backgroundNode;

	}
```
</details>

### `Nodes.getFogNode(scene: Scene): Node`

**JSDoc:**
```typescript
/**
	 * Returns a fog node for the current configured scene fog.
	 *
	 * @param {Scene} scene - The scene.
	 * @return {Node} A node representing the current scene fog.
	 */
```

**Parameters:**

- **`scene`** `Scene`

**Returns:** `Node`

**Calls:**

- `this.updateFog`
- `this.get`

<details><summary>Code</summary>

```typescript
getFogNode( scene ) {

		this.updateFog( scene );

		return scene.fogNode || this.get( scene ).fogNode || null;

	}
```
</details>

### `Nodes.getCacheKey(scene: Scene, lightsNode: LightsNode): number`

**JSDoc:**
```typescript
/**
	 * Returns a cache key for the given scene and lights node.
	 * This key is used by `RenderObject` as a part of the dynamic
	 * cache key (a key that must be checked every time the render
	 * objects is drawn).
	 *
	 * @param {Scene} scene - The scene.
	 * @param {LightsNode} lightsNode - The lights node.
	 * @return {number} The cache key.
	 */
```

**Parameters:**

- **`scene`** `Scene`
- **`lightsNode`** `LightsNode`

**Returns:** `number`

**Calls:**

- `this.callHashCache.get`
- `this.getEnvironmentNode`
- `this.getFogNode`
- `_cacheKeyValues.push`
- `lightsNode.getCacheKey`
- `environmentNode.getCacheKey`
- `fogNode.getCacheKey`
- `this.renderer.getOutputRenderTarget`
- `hashArray (from ../../../nodes/core/NodeUtils.js)`
- `this.callHashCache.set`

<details><summary>Code</summary>

```typescript
getCacheKey( scene, lightsNode ) {

		_chainKeys[ 0 ] = scene;
		_chainKeys[ 1 ] = lightsNode;

		const callId = this.renderer.info.calls;

		const cacheKeyData = this.callHashCache.get( _chainKeys ) || {};

		if ( cacheKeyData.callId !== callId ) {

			const environmentNode = this.getEnvironmentNode( scene );
			const fogNode = this.getFogNode( scene );

			if ( lightsNode ) _cacheKeyValues.push( lightsNode.getCacheKey( true ) );
			if ( environmentNode ) _cacheKeyValues.push( environmentNode.getCacheKey() );
			if ( fogNode ) _cacheKeyValues.push( fogNode.getCacheKey() );

			_cacheKeyValues.push( this.renderer.getOutputRenderTarget() && this.renderer.getOutputRenderTarget().multiview ? 1 : 0 );
			_cacheKeyValues.push( this.renderer.shadowMap.enabled ? 1 : 0 );

			cacheKeyData.callId = callId;
			cacheKeyData.cacheKey = hashArray( _cacheKeyValues );

			this.callHashCache.set( _chainKeys, cacheKeyData );

			_cacheKeyValues.length = 0;

		}

		_chainKeys.length = 0;

		return cacheKeyData.cacheKey;

	}
```
</details>

### `Nodes.updateBackground(scene: Scene): void`

**JSDoc:**
```typescript
/**
	 * If a scene background is configured, this method makes sure to
	 * represent the background with a corresponding node-based implementation.
	 *
	 * @param {Scene} scene - The scene.
	 */
```

**Parameters:**

- **`scene`** `Scene`

**Returns:** `void`

**Calls:**

- `this.get`
- `this.getCacheNode`
- `pmremTexture (from ../../../nodes/TSL.js)`
- `cubeTexture (from ../../../nodes/TSL.js)`
- `texture (from ../../../nodes/TSL.js)`
- `cubeMapNode (from ../../../nodes/utils/CubeMapNode.js)`
- `texture( background, screenUV.flipY() ).setUpdateMatrix`
- `console.error`

<details><summary>Code</summary>

```typescript
updateBackground( scene ) {

		const sceneData = this.get( scene );
		const background = scene.background;

		if ( background ) {

			const forceUpdate = ( scene.backgroundBlurriness === 0 && sceneData.backgroundBlurriness > 0 ) || ( scene.backgroundBlurriness > 0 && sceneData.backgroundBlurriness === 0 );

			if ( sceneData.background !== background || forceUpdate ) {

				const backgroundNode = this.getCacheNode( 'background', background, () => {

					if ( background.isCubeTexture === true || ( background.mapping === EquirectangularReflectionMapping || background.mapping === EquirectangularRefractionMapping || background.mapping === CubeUVReflectionMapping ) ) {

						if ( scene.backgroundBlurriness > 0 || background.mapping === CubeUVReflectionMapping ) {

							return pmremTexture( background );

						} else {

							let envMap;

							if ( background.isCubeTexture === true ) {

								envMap = cubeTexture( background );

							} else {

								envMap = texture( background );

							}

							return cubeMapNode( envMap );

						}

					} else if ( background.isTexture === true ) {

						return texture( background, screenUV.flipY() ).setUpdateMatrix( true );

					} else if ( background.isColor !== true ) {

						console.error( 'WebGPUNodes: Unsupported background configuration.', background );

					}

				}, forceUpdate );

				sceneData.backgroundNode = backgroundNode;
				sceneData.background = background;
				sceneData.backgroundBlurriness = scene.backgroundBlurriness;

			}

		} else if ( sceneData.backgroundNode ) {

			delete sceneData.backgroundNode;
			delete sceneData.background;

		}

	}
```
</details>

### `Nodes.getCacheNode(type: string, object: any, callback: Function, forceUpdate: boolean): Node`

**JSDoc:**
```typescript
/**
	 * This method is part of the caching of nodes which are used to represents the
	 * scene's background, fog or environment.
	 *
	 * @param {string} type - The type of object to cache.
	 * @param {Object} object - The object.
	 * @param {Function} callback - A callback that produces a node representation for the given object.
	 * @param {boolean} [forceUpdate=false] - Whether an update should be enforced or not.
	 * @return {Node} The node representation.
	 */
```

**Parameters:**

- **`type`** `string`
- **`object`** `any`
- **`callback`** `Function`
- **`forceUpdate`** `boolean`

**Returns:** `Node`

**Calls:**

- `nodeCache.get`
- `callback`
- `nodeCache.set`

<details><summary>Code</summary>

```typescript
getCacheNode( type, object, callback, forceUpdate = false ) {

		const nodeCache = this.cacheLib[ type ] || ( this.cacheLib[ type ] = new WeakMap() );

		let node = nodeCache.get( object );

		if ( node === undefined || forceUpdate ) {

			node = callback();
			nodeCache.set( object, node );

		}

		return node;

	}
```
</details>

### `Nodes.updateFog(scene: Scene): void`

**JSDoc:**
```typescript
/**
	 * If a scene fog is configured, this method makes sure to
	 * represent the fog with a corresponding node-based implementation.
	 *
	 * @param {Scene} scene - The scene.
	 */
```

**Parameters:**

- **`scene`** `Scene`

**Returns:** `void`

**Calls:**

- `this.get`
- `this.getCacheNode`
- `reference( 'color', 'color', sceneFog ).setGroup`
- `reference( 'density', 'float', sceneFog ).setGroup`
- `fog (from ../../../nodes/TSL.js)`
- `densityFogFactor (from ../../../nodes/TSL.js)`
- `reference( 'near', 'float', sceneFog ).setGroup`
- `reference( 'far', 'float', sceneFog ).setGroup`
- `rangeFogFactor (from ../../../nodes/TSL.js)`
- `console.error`

<details><summary>Code</summary>

```typescript
updateFog( scene ) {

		const sceneData = this.get( scene );
		const sceneFog = scene.fog;

		if ( sceneFog ) {

			if ( sceneData.fog !== sceneFog ) {

				const fogNode = this.getCacheNode( 'fog', sceneFog, () => {

					if ( sceneFog.isFogExp2 ) {

						const color = reference( 'color', 'color', sceneFog ).setGroup( renderGroup );
						const density = reference( 'density', 'float', sceneFog ).setGroup( renderGroup );

						return fog( color, densityFogFactor( density ) );

					} else if ( sceneFog.isFog ) {

						const color = reference( 'color', 'color', sceneFog ).setGroup( renderGroup );
						const near = reference( 'near', 'float', sceneFog ).setGroup( renderGroup );
						const far = reference( 'far', 'float', sceneFog ).setGroup( renderGroup );

						return fog( color, rangeFogFactor( near, far ) );

					} else {

						console.error( 'THREE.Renderer: Unsupported fog configuration.', sceneFog );

					}

				} );

				sceneData.fogNode = fogNode;
				sceneData.fog = sceneFog;

			}

		} else {

			delete sceneData.fogNode;
			delete sceneData.fog;

		}

	}
```
</details>

### `Nodes.updateEnvironment(scene: Scene): void`

**JSDoc:**
```typescript
/**
	 * If a scene environment is configured, this method makes sure to
	 * represent the environment with a corresponding node-based implementation.
	 *
	 * @param {Scene} scene - The scene.
	 */
```

**Parameters:**

- **`scene`** `Scene`

**Returns:** `void`

**Calls:**

- `this.get`
- `this.getCacheNode`
- `cubeTexture (from ../../../nodes/TSL.js)`
- `texture (from ../../../nodes/TSL.js)`
- `console.error`

<details><summary>Code</summary>

```typescript
updateEnvironment( scene ) {

		const sceneData = this.get( scene );
		const environment = scene.environment;

		if ( environment ) {

			if ( sceneData.environment !== environment ) {

				const environmentNode = this.getCacheNode( 'environment', environment, () => {

					if ( environment.isCubeTexture === true ) {

						return cubeTexture( environment );

					} else if ( environment.isTexture === true ) {

						return texture( environment );

					} else {

						console.error( 'Nodes: Unsupported environment configuration.', environment );

					}

				} );

				sceneData.environmentNode = environmentNode;
				sceneData.environment = environment;

			}

		} else if ( sceneData.environmentNode ) {

			delete sceneData.environmentNode;
			delete sceneData.environment;

		}

	}
```
</details>

### `Nodes.getNodeFrame(renderer: Renderer, scene: any, object: any, camera: any, material: any): Renderer`

**Parameters:**

- **`renderer`** `Renderer`
- **`scene`** `any`
- **`object`** `any`
- **`camera`** `any`
- **`material`** `any`

**Returns:** `Renderer`

<details><summary>Code</summary>

```typescript
getNodeFrame( renderer = this.renderer, scene = null, object = null, camera = null, material = null ) {

		const nodeFrame = this.nodeFrame;
		nodeFrame.renderer = renderer;
		nodeFrame.scene = scene;
		nodeFrame.object = object;
		nodeFrame.camera = camera;
		nodeFrame.material = material;

		return nodeFrame;

	}
```
</details>

### `Nodes.getNodeFrameForRender(renderObject: any): Renderer`

**Parameters:**

- **`renderObject`** `any`

**Returns:** `Renderer`

**Calls:**

- `this.getNodeFrame`

<details><summary>Code</summary>

```typescript
getNodeFrameForRender( renderObject ) {

		return this.getNodeFrame( renderObject.renderer, renderObject.scene, renderObject.object, renderObject.camera, renderObject.material );

	}
```
</details>

### `Nodes.getOutputCacheKey(): string`

**JSDoc:**
```typescript
/**
	 * Returns the current output cache key.
	 *
	 * @return {string} The output cache key.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getOutputCacheKey() {

		const renderer = this.renderer;

		return renderer.toneMapping + ',' + renderer.currentColorSpace + ',' + renderer.xr.isPresenting;

	}
```
</details>

### `Nodes.hasOutputChange(outputTarget: Texture): boolean`

**JSDoc:**
```typescript
/**
	 * Checks if the output configuration (tone mapping and color space) for
	 * the given target has changed.
	 *
	 * @param {Texture} outputTarget - The output target.
	 * @return {boolean} Whether the output configuration has changed or not.
	 */
```

**Parameters:**

- **`outputTarget`** `Texture`

**Returns:** `boolean`

**Calls:**

- `_outputNodeMap.get`
- `this.getOutputCacheKey`

<details><summary>Code</summary>

```typescript
hasOutputChange( outputTarget ) {

		const cacheKey = _outputNodeMap.get( outputTarget );

		return cacheKey !== this.getOutputCacheKey();

	}
```
</details>

### `Nodes.getOutputNode(outputTarget: Texture): Node`

**JSDoc:**
```typescript
/**
	 * Returns a node that represents the output configuration (tone mapping and
	 * color space) for the current target.
	 *
	 * @param {Texture} outputTarget - The output target.
	 * @return {Node} The output node.
	 */
```

**Parameters:**

- **`outputTarget`** `Texture`

**Returns:** `Node`

**Calls:**

- `this.getOutputCacheKey`
- `texture3D( outputTarget, vec3( screenUV, builtin( 'gl_ViewID_OVR' ) ) ).renderOutput`
- `texture( outputTarget, screenUV ).renderOutput`
- `_outputNodeMap.set`

<details><summary>Code</summary>

```typescript
getOutputNode( outputTarget ) {

		const renderer = this.renderer;
		const cacheKey = this.getOutputCacheKey();

		const output = outputTarget.isArrayTexture ?
			texture3D( outputTarget, vec3( screenUV, builtin( 'gl_ViewID_OVR' ) ) ).renderOutput( renderer.toneMapping, renderer.currentColorSpace ) :
			texture( outputTarget, screenUV ).renderOutput( renderer.toneMapping, renderer.currentColorSpace );

		_outputNodeMap.set( outputTarget, cacheKey );

		return output;

	}
```
</details>

### `Nodes.updateBefore(renderObject: RenderObject): void`

**JSDoc:**
```typescript
/**
	 * Triggers the call of `updateBefore()` methods
	 * for all nodes of the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `void`

**Calls:**

- `renderObject.getNodeBuilderState`
- `this.getNodeFrameForRender( renderObject ).updateBeforeNode`

**Internal Comments:**
```
// update frame state for each node (x6)
```

<details><summary>Code</summary>

```typescript
updateBefore( renderObject ) {

		const nodeBuilder = renderObject.getNodeBuilderState();

		for ( const node of nodeBuilder.updateBeforeNodes ) {

			// update frame state for each node

			this.getNodeFrameForRender( renderObject ).updateBeforeNode( node );

		}

	}
```
</details>

### `Nodes.updateAfter(renderObject: RenderObject): void`

**JSDoc:**
```typescript
/**
	 * Triggers the call of `updateAfter()` methods
	 * for all nodes of the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `void`

**Calls:**

- `renderObject.getNodeBuilderState`
- `this.getNodeFrameForRender( renderObject ).updateAfterNode`

**Internal Comments:**
```
// update frame state for each node (x6)
```

<details><summary>Code</summary>

```typescript
updateAfter( renderObject ) {

		const nodeBuilder = renderObject.getNodeBuilderState();

		for ( const node of nodeBuilder.updateAfterNodes ) {

			// update frame state for each node

			this.getNodeFrameForRender( renderObject ).updateAfterNode( node );

		}

	}
```
</details>

### `Nodes.updateForCompute(computeNode: Node): void`

**JSDoc:**
```typescript
/**
	 * Triggers the call of `update()` methods
	 * for all nodes of the given compute node.
	 *
	 * @param {Node} computeNode - The compute node.
	 */
```

**Parameters:**

- **`computeNode`** `Node`

**Returns:** `void`

**Calls:**

- `this.getNodeFrame`
- `this.getForCompute`
- `nodeFrame.updateNode`

<details><summary>Code</summary>

```typescript
updateForCompute( computeNode ) {

		const nodeFrame = this.getNodeFrame();
		const nodeBuilder = this.getForCompute( computeNode );

		for ( const node of nodeBuilder.updateNodes ) {

			nodeFrame.updateNode( node );

		}

	}
```
</details>

### `Nodes.updateForRender(renderObject: RenderObject): void`

**JSDoc:**
```typescript
/**
	 * Triggers the call of `update()` methods
	 * for all nodes of the given compute node.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `void`

**Calls:**

- `this.getNodeFrameForRender`
- `renderObject.getNodeBuilderState`
- `nodeFrame.updateNode`

<details><summary>Code</summary>

```typescript
updateForRender( renderObject ) {

		const nodeFrame = this.getNodeFrameForRender( renderObject );
		const nodeBuilder = renderObject.getNodeBuilderState();

		for ( const node of nodeBuilder.updateNodes ) {

			nodeFrame.updateNode( node );

		}

	}
```
</details>

### `Nodes.needsRefresh(renderObject: RenderObject): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given render object requires a refresh.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {boolean} Whether the given render object requires a refresh or not.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `boolean`

**Calls:**

- `this.getNodeFrameForRender`
- `renderObject.getMonitor`
- `monitor.needsRefresh`

<details><summary>Code</summary>

```typescript
needsRefresh( renderObject ) {

		const nodeFrame = this.getNodeFrameForRender( renderObject );
		const monitor = renderObject.getMonitor();

		return monitor.needsRefresh( renderObject, nodeFrame );

	}
```
</details>

### `Nodes.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the internal resources.
	 */
```

**Returns:** `void`

**Calls:**

- `super.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		super.dispose();

		this.nodeFrame = new NodeFrame();
		this.nodeBuilderCache = new Map();
		this.cacheLib = {};

	}
```
</details>


---

## Classes

### `Nodes`

<details><summary>Class Code</summary>

```ts
class Nodes extends DataMap {

	/**
	 * Constructs a new nodes management component.
	 *
	 * @param {Renderer} renderer - The renderer.
	 * @param {Backend} backend - The renderer's backend.
	 */
	constructor( renderer, backend ) {

		super();

		/**
		 * The renderer.
		 *
		 * @type {Renderer}
		 */
		this.renderer = renderer;

		/**
		 * The renderer's backend.
		 *
		 * @type {Backend}
		 */
		this.backend = backend;

		/**
		 * The node frame.
		 *
		 * @type {Renderer}
		 */
		this.nodeFrame = new NodeFrame();

		/**
		 * A cache for managing node builder states.
		 *
		 * @type {Map<number,NodeBuilderState>}
		 */
		this.nodeBuilderCache = new Map();

		/**
		 * A cache for managing data cache key data.
		 *
		 * @type {ChainMap}
		 */
		this.callHashCache = new ChainMap();

		/**
		 * A cache for managing node uniforms group data.
		 *
		 * @type {ChainMap}
		 */
		this.groupsData = new ChainMap();

		/**
		 * A cache for managing node objects of
		 * scene properties like fog or environments.
		 *
		 * @type {Object<string,WeakMap>}
		 */
		this.cacheLib = {};

	}

	/**
	 * Returns `true` if the given node uniforms group must be updated or not.
	 *
	 * @param {NodeUniformsGroup} nodeUniformsGroup - The node uniforms group.
	 * @return {boolean} Whether the node uniforms group requires an update or not.
	 */
	updateGroup( nodeUniformsGroup ) {

		const groupNode = nodeUniformsGroup.groupNode;
		const name = groupNode.name;

		// objectGroup is always updated

		if ( name === objectGroup.name ) return true;

		// renderGroup is updated once per render/compute call

		if ( name === renderGroup.name ) {

			const uniformsGroupData = this.get( nodeUniformsGroup );
			const renderId = this.nodeFrame.renderId;

			if ( uniformsGroupData.renderId !== renderId ) {

				uniformsGroupData.renderId = renderId;

				return true;

			}

			return false;

		}

		// frameGroup is updated once per frame

		if ( name === frameGroup.name ) {

			const uniformsGroupData = this.get( nodeUniformsGroup );
			const frameId = this.nodeFrame.frameId;

			if ( uniformsGroupData.frameId !== frameId ) {

				uniformsGroupData.frameId = frameId;

				return true;

			}

			return false;

		}

		// other groups are updated just when groupNode.needsUpdate is true

		_chainKeys[ 0 ] = groupNode;
		_chainKeys[ 1 ] = nodeUniformsGroup;

		let groupData = this.groupsData.get( _chainKeys );
		if ( groupData === undefined ) this.groupsData.set( _chainKeys, groupData = {} );

		_chainKeys.length = 0;

		if ( groupData.version !== groupNode.version ) {

			groupData.version = groupNode.version;

			return true;

		}

		return false;

	}

	/**
	 * Returns the cache key for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {number} The cache key.
	 */
	getForRenderCacheKey( renderObject ) {

		return renderObject.initialCacheKey;

	}

	/**
	 * Returns a node builder state for the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {NodeBuilderState} The node builder state.
	 */
	getForRender( renderObject ) {

		const renderObjectData = this.get( renderObject );

		let nodeBuilderState = renderObjectData.nodeBuilderState;

		if ( nodeBuilderState === undefined ) {

			const { nodeBuilderCache } = this;

			const cacheKey = this.getForRenderCacheKey( renderObject );

			nodeBuilderState = nodeBuilderCache.get( cacheKey );

			if ( nodeBuilderState === undefined ) {

				const nodeBuilder = this.backend.createNodeBuilder( renderObject.object, this.renderer );
				nodeBuilder.scene = renderObject.scene;
				nodeBuilder.material = renderObject.material;
				nodeBuilder.camera = renderObject.camera;
				nodeBuilder.context.material = renderObject.material;
				nodeBuilder.lightsNode = renderObject.lightsNode;
				nodeBuilder.environmentNode = this.getEnvironmentNode( renderObject.scene );
				nodeBuilder.fogNode = this.getFogNode( renderObject.scene );
				nodeBuilder.clippingContext = renderObject.clippingContext;
				if ( this.renderer.getOutputRenderTarget() ? this.renderer.getOutputRenderTarget().multiview : false ) {

					nodeBuilder.enableMultiview();

				}

				nodeBuilder.build();

				nodeBuilderState = this._createNodeBuilderState( nodeBuilder );

				nodeBuilderCache.set( cacheKey, nodeBuilderState );

			}

			nodeBuilderState.usedTimes ++;

			renderObjectData.nodeBuilderState = nodeBuilderState;

		}

		return nodeBuilderState;

	}

	/**
	 * Deletes the given object from the internal data map
	 *
	 * @param {any} object - The object to delete.
	 * @return {?Object} The deleted dictionary.
	 */
	delete( object ) {

		if ( object.isRenderObject ) {

			const nodeBuilderState = this.get( object ).nodeBuilderState;
			nodeBuilderState.usedTimes --;

			if ( nodeBuilderState.usedTimes === 0 ) {

				this.nodeBuilderCache.delete( this.getForRenderCacheKey( object ) );

			}

		}

		return super.delete( object );

	}

	/**
	 * Returns a node builder state for the given compute node.
	 *
	 * @param {Node} computeNode - The compute node.
	 * @return {NodeBuilderState} The node builder state.
	 */
	getForCompute( computeNode ) {

		const computeData = this.get( computeNode );

		let nodeBuilderState = computeData.nodeBuilderState;

		if ( nodeBuilderState === undefined ) {

			const nodeBuilder = this.backend.createNodeBuilder( computeNode, this.renderer );
			nodeBuilder.build();

			nodeBuilderState = this._createNodeBuilderState( nodeBuilder );

			computeData.nodeBuilderState = nodeBuilderState;

		}

		return nodeBuilderState;

	}

	/**
	 * Creates a node builder state for the given node builder.
	 *
	 * @private
	 * @param {NodeBuilder} nodeBuilder - The node builder.
	 * @return {NodeBuilderState} The node builder state.
	 */
	_createNodeBuilderState( nodeBuilder ) {

		return new NodeBuilderState(
			nodeBuilder.vertexShader,
			nodeBuilder.fragmentShader,
			nodeBuilder.computeShader,
			nodeBuilder.getAttributesArray(),
			nodeBuilder.getBindings(),
			nodeBuilder.updateNodes,
			nodeBuilder.updateBeforeNodes,
			nodeBuilder.updateAfterNodes,
			nodeBuilder.observer,
			nodeBuilder.transforms
		);

	}

	/**
	 * Returns an environment node for the current configured
	 * scene environment.
	 *
	 * @param {Scene} scene - The scene.
	 * @return {Node} A node representing the current scene environment.
	 */
	getEnvironmentNode( scene ) {

		this.updateEnvironment( scene );

		let environmentNode = null;

		if ( scene.environmentNode && scene.environmentNode.isNode ) {

			environmentNode = scene.environmentNode;

		} else {

			const sceneData = this.get( scene );

			if ( sceneData.environmentNode ) {

				environmentNode = sceneData.environmentNode;

			}

		}

		return environmentNode;

	}

	/**
	 * Returns a background node for the current configured
	 * scene background.
	 *
	 * @param {Scene} scene - The scene.
	 * @return {Node} A node representing the current scene background.
	 */
	getBackgroundNode( scene ) {

		this.updateBackground( scene );

		let backgroundNode = null;

		if ( scene.backgroundNode && scene.backgroundNode.isNode ) {

			backgroundNode = scene.backgroundNode;

		} else {

			const sceneData = this.get( scene );

			if ( sceneData.backgroundNode ) {

				backgroundNode = sceneData.backgroundNode;

			}

		}

		return backgroundNode;

	}

	/**
	 * Returns a fog node for the current configured scene fog.
	 *
	 * @param {Scene} scene - The scene.
	 * @return {Node} A node representing the current scene fog.
	 */
	getFogNode( scene ) {

		this.updateFog( scene );

		return scene.fogNode || this.get( scene ).fogNode || null;

	}

	/**
	 * Returns a cache key for the given scene and lights node.
	 * This key is used by `RenderObject` as a part of the dynamic
	 * cache key (a key that must be checked every time the render
	 * objects is drawn).
	 *
	 * @param {Scene} scene - The scene.
	 * @param {LightsNode} lightsNode - The lights node.
	 * @return {number} The cache key.
	 */
	getCacheKey( scene, lightsNode ) {

		_chainKeys[ 0 ] = scene;
		_chainKeys[ 1 ] = lightsNode;

		const callId = this.renderer.info.calls;

		const cacheKeyData = this.callHashCache.get( _chainKeys ) || {};

		if ( cacheKeyData.callId !== callId ) {

			const environmentNode = this.getEnvironmentNode( scene );
			const fogNode = this.getFogNode( scene );

			if ( lightsNode ) _cacheKeyValues.push( lightsNode.getCacheKey( true ) );
			if ( environmentNode ) _cacheKeyValues.push( environmentNode.getCacheKey() );
			if ( fogNode ) _cacheKeyValues.push( fogNode.getCacheKey() );

			_cacheKeyValues.push( this.renderer.getOutputRenderTarget() && this.renderer.getOutputRenderTarget().multiview ? 1 : 0 );
			_cacheKeyValues.push( this.renderer.shadowMap.enabled ? 1 : 0 );

			cacheKeyData.callId = callId;
			cacheKeyData.cacheKey = hashArray( _cacheKeyValues );

			this.callHashCache.set( _chainKeys, cacheKeyData );

			_cacheKeyValues.length = 0;

		}

		_chainKeys.length = 0;

		return cacheKeyData.cacheKey;

	}

	/**
	 * A boolean that indicates whether tone mapping should be enabled
	 * or not.
	 *
	 * @type {boolean}
	 */
	get isToneMappingState() {

		return this.renderer.getRenderTarget() ? false : true;

	}

	/**
	 * If a scene background is configured, this method makes sure to
	 * represent the background with a corresponding node-based implementation.
	 *
	 * @param {Scene} scene - The scene.
	 */
	updateBackground( scene ) {

		const sceneData = this.get( scene );
		const background = scene.background;

		if ( background ) {

			const forceUpdate = ( scene.backgroundBlurriness === 0 && sceneData.backgroundBlurriness > 0 ) || ( scene.backgroundBlurriness > 0 && sceneData.backgroundBlurriness === 0 );

			if ( sceneData.background !== background || forceUpdate ) {

				const backgroundNode = this.getCacheNode( 'background', background, () => {

					if ( background.isCubeTexture === true || ( background.mapping === EquirectangularReflectionMapping || background.mapping === EquirectangularRefractionMapping || background.mapping === CubeUVReflectionMapping ) ) {

						if ( scene.backgroundBlurriness > 0 || background.mapping === CubeUVReflectionMapping ) {

							return pmremTexture( background );

						} else {

							let envMap;

							if ( background.isCubeTexture === true ) {

								envMap = cubeTexture( background );

							} else {

								envMap = texture( background );

							}

							return cubeMapNode( envMap );

						}

					} else if ( background.isTexture === true ) {

						return texture( background, screenUV.flipY() ).setUpdateMatrix( true );

					} else if ( background.isColor !== true ) {

						console.error( 'WebGPUNodes: Unsupported background configuration.', background );

					}

				}, forceUpdate );

				sceneData.backgroundNode = backgroundNode;
				sceneData.background = background;
				sceneData.backgroundBlurriness = scene.backgroundBlurriness;

			}

		} else if ( sceneData.backgroundNode ) {

			delete sceneData.backgroundNode;
			delete sceneData.background;

		}

	}

	/**
	 * This method is part of the caching of nodes which are used to represents the
	 * scene's background, fog or environment.
	 *
	 * @param {string} type - The type of object to cache.
	 * @param {Object} object - The object.
	 * @param {Function} callback - A callback that produces a node representation for the given object.
	 * @param {boolean} [forceUpdate=false] - Whether an update should be enforced or not.
	 * @return {Node} The node representation.
	 */
	getCacheNode( type, object, callback, forceUpdate = false ) {

		const nodeCache = this.cacheLib[ type ] || ( this.cacheLib[ type ] = new WeakMap() );

		let node = nodeCache.get( object );

		if ( node === undefined || forceUpdate ) {

			node = callback();
			nodeCache.set( object, node );

		}

		return node;

	}

	/**
	 * If a scene fog is configured, this method makes sure to
	 * represent the fog with a corresponding node-based implementation.
	 *
	 * @param {Scene} scene - The scene.
	 */
	updateFog( scene ) {

		const sceneData = this.get( scene );
		const sceneFog = scene.fog;

		if ( sceneFog ) {

			if ( sceneData.fog !== sceneFog ) {

				const fogNode = this.getCacheNode( 'fog', sceneFog, () => {

					if ( sceneFog.isFogExp2 ) {

						const color = reference( 'color', 'color', sceneFog ).setGroup( renderGroup );
						const density = reference( 'density', 'float', sceneFog ).setGroup( renderGroup );

						return fog( color, densityFogFactor( density ) );

					} else if ( sceneFog.isFog ) {

						const color = reference( 'color', 'color', sceneFog ).setGroup( renderGroup );
						const near = reference( 'near', 'float', sceneFog ).setGroup( renderGroup );
						const far = reference( 'far', 'float', sceneFog ).setGroup( renderGroup );

						return fog( color, rangeFogFactor( near, far ) );

					} else {

						console.error( 'THREE.Renderer: Unsupported fog configuration.', sceneFog );

					}

				} );

				sceneData.fogNode = fogNode;
				sceneData.fog = sceneFog;

			}

		} else {

			delete sceneData.fogNode;
			delete sceneData.fog;

		}

	}

	/**
	 * If a scene environment is configured, this method makes sure to
	 * represent the environment with a corresponding node-based implementation.
	 *
	 * @param {Scene} scene - The scene.
	 */
	updateEnvironment( scene ) {

		const sceneData = this.get( scene );
		const environment = scene.environment;

		if ( environment ) {

			if ( sceneData.environment !== environment ) {

				const environmentNode = this.getCacheNode( 'environment', environment, () => {

					if ( environment.isCubeTexture === true ) {

						return cubeTexture( environment );

					} else if ( environment.isTexture === true ) {

						return texture( environment );

					} else {

						console.error( 'Nodes: Unsupported environment configuration.', environment );

					}

				} );

				sceneData.environmentNode = environmentNode;
				sceneData.environment = environment;

			}

		} else if ( sceneData.environmentNode ) {

			delete sceneData.environmentNode;
			delete sceneData.environment;

		}

	}

	getNodeFrame( renderer = this.renderer, scene = null, object = null, camera = null, material = null ) {

		const nodeFrame = this.nodeFrame;
		nodeFrame.renderer = renderer;
		nodeFrame.scene = scene;
		nodeFrame.object = object;
		nodeFrame.camera = camera;
		nodeFrame.material = material;

		return nodeFrame;

	}

	getNodeFrameForRender( renderObject ) {

		return this.getNodeFrame( renderObject.renderer, renderObject.scene, renderObject.object, renderObject.camera, renderObject.material );

	}

	/**
	 * Returns the current output cache key.
	 *
	 * @return {string} The output cache key.
	 */
	getOutputCacheKey() {

		const renderer = this.renderer;

		return renderer.toneMapping + ',' + renderer.currentColorSpace + ',' + renderer.xr.isPresenting;

	}

	/**
	 * Checks if the output configuration (tone mapping and color space) for
	 * the given target has changed.
	 *
	 * @param {Texture} outputTarget - The output target.
	 * @return {boolean} Whether the output configuration has changed or not.
	 */
	hasOutputChange( outputTarget ) {

		const cacheKey = _outputNodeMap.get( outputTarget );

		return cacheKey !== this.getOutputCacheKey();

	}

	/**
	 * Returns a node that represents the output configuration (tone mapping and
	 * color space) for the current target.
	 *
	 * @param {Texture} outputTarget - The output target.
	 * @return {Node} The output node.
	 */
	getOutputNode( outputTarget ) {

		const renderer = this.renderer;
		const cacheKey = this.getOutputCacheKey();

		const output = outputTarget.isArrayTexture ?
			texture3D( outputTarget, vec3( screenUV, builtin( 'gl_ViewID_OVR' ) ) ).renderOutput( renderer.toneMapping, renderer.currentColorSpace ) :
			texture( outputTarget, screenUV ).renderOutput( renderer.toneMapping, renderer.currentColorSpace );

		_outputNodeMap.set( outputTarget, cacheKey );

		return output;

	}

	/**
	 * Triggers the call of `updateBefore()` methods
	 * for all nodes of the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 */
	updateBefore( renderObject ) {

		const nodeBuilder = renderObject.getNodeBuilderState();

		for ( const node of nodeBuilder.updateBeforeNodes ) {

			// update frame state for each node

			this.getNodeFrameForRender( renderObject ).updateBeforeNode( node );

		}

	}

	/**
	 * Triggers the call of `updateAfter()` methods
	 * for all nodes of the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 */
	updateAfter( renderObject ) {

		const nodeBuilder = renderObject.getNodeBuilderState();

		for ( const node of nodeBuilder.updateAfterNodes ) {

			// update frame state for each node

			this.getNodeFrameForRender( renderObject ).updateAfterNode( node );

		}

	}

	/**
	 * Triggers the call of `update()` methods
	 * for all nodes of the given compute node.
	 *
	 * @param {Node} computeNode - The compute node.
	 */
	updateForCompute( computeNode ) {

		const nodeFrame = this.getNodeFrame();
		const nodeBuilder = this.getForCompute( computeNode );

		for ( const node of nodeBuilder.updateNodes ) {

			nodeFrame.updateNode( node );

		}

	}

	/**
	 * Triggers the call of `update()` methods
	 * for all nodes of the given compute node.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 */
	updateForRender( renderObject ) {

		const nodeFrame = this.getNodeFrameForRender( renderObject );
		const nodeBuilder = renderObject.getNodeBuilderState();

		for ( const node of nodeBuilder.updateNodes ) {

			nodeFrame.updateNode( node );

		}

	}

	/**
	 * Returns `true` if the given render object requires a refresh.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {boolean} Whether the given render object requires a refresh or not.
	 */
	needsRefresh( renderObject ) {

		const nodeFrame = this.getNodeFrameForRender( renderObject );
		const monitor = renderObject.getMonitor();

		return monitor.needsRefresh( renderObject, nodeFrame );

	}

	/**
	 * Frees the internal resources.
	 */
	dispose() {

		super.dispose();

		this.nodeFrame = new NodeFrame();
		this.nodeBuilderCache = new Map();
		this.cacheLib = {};

	}

}
```
</details>

#### Methods

##### `updateGroup(nodeUniformsGroup: NodeUniformsGroup): boolean`

<details><summary>Code</summary>

```ts
updateGroup( nodeUniformsGroup ) {

		const groupNode = nodeUniformsGroup.groupNode;
		const name = groupNode.name;

		// objectGroup is always updated

		if ( name === objectGroup.name ) return true;

		// renderGroup is updated once per render/compute call

		if ( name === renderGroup.name ) {

			const uniformsGroupData = this.get( nodeUniformsGroup );
			const renderId = this.nodeFrame.renderId;

			if ( uniformsGroupData.renderId !== renderId ) {

				uniformsGroupData.renderId = renderId;

				return true;

			}

			return false;

		}

		// frameGroup is updated once per frame

		if ( name === frameGroup.name ) {

			const uniformsGroupData = this.get( nodeUniformsGroup );
			const frameId = this.nodeFrame.frameId;

			if ( uniformsGroupData.frameId !== frameId ) {

				uniformsGroupData.frameId = frameId;

				return true;

			}

			return false;

		}

		// other groups are updated just when groupNode.needsUpdate is true

		_chainKeys[ 0 ] = groupNode;
		_chainKeys[ 1 ] = nodeUniformsGroup;

		let groupData = this.groupsData.get( _chainKeys );
		if ( groupData === undefined ) this.groupsData.set( _chainKeys, groupData = {} );

		_chainKeys.length = 0;

		if ( groupData.version !== groupNode.version ) {

			groupData.version = groupNode.version;

			return true;

		}

		return false;

	}
```
</details>

##### `getForRenderCacheKey(renderObject: RenderObject): number`

<details><summary>Code</summary>

```ts
getForRenderCacheKey( renderObject ) {

		return renderObject.initialCacheKey;

	}
```
</details>

##### `getForRender(renderObject: RenderObject): NodeBuilderState`

<details><summary>Code</summary>

```ts
getForRender( renderObject ) {

		const renderObjectData = this.get( renderObject );

		let nodeBuilderState = renderObjectData.nodeBuilderState;

		if ( nodeBuilderState === undefined ) {

			const { nodeBuilderCache } = this;

			const cacheKey = this.getForRenderCacheKey( renderObject );

			nodeBuilderState = nodeBuilderCache.get( cacheKey );

			if ( nodeBuilderState === undefined ) {

				const nodeBuilder = this.backend.createNodeBuilder( renderObject.object, this.renderer );
				nodeBuilder.scene = renderObject.scene;
				nodeBuilder.material = renderObject.material;
				nodeBuilder.camera = renderObject.camera;
				nodeBuilder.context.material = renderObject.material;
				nodeBuilder.lightsNode = renderObject.lightsNode;
				nodeBuilder.environmentNode = this.getEnvironmentNode( renderObject.scene );
				nodeBuilder.fogNode = this.getFogNode( renderObject.scene );
				nodeBuilder.clippingContext = renderObject.clippingContext;
				if ( this.renderer.getOutputRenderTarget() ? this.renderer.getOutputRenderTarget().multiview : false ) {

					nodeBuilder.enableMultiview();

				}

				nodeBuilder.build();

				nodeBuilderState = this._createNodeBuilderState( nodeBuilder );

				nodeBuilderCache.set( cacheKey, nodeBuilderState );

			}

			nodeBuilderState.usedTimes ++;

			renderObjectData.nodeBuilderState = nodeBuilderState;

		}

		return nodeBuilderState;

	}
```
</details>

##### `delete(object: any): any`

<details><summary>Code</summary>

```ts
delete( object ) {

		if ( object.isRenderObject ) {

			const nodeBuilderState = this.get( object ).nodeBuilderState;
			nodeBuilderState.usedTimes --;

			if ( nodeBuilderState.usedTimes === 0 ) {

				this.nodeBuilderCache.delete( this.getForRenderCacheKey( object ) );

			}

		}

		return super.delete( object );

	}
```
</details>

##### `getForCompute(computeNode: Node): NodeBuilderState`

<details><summary>Code</summary>

```ts
getForCompute( computeNode ) {

		const computeData = this.get( computeNode );

		let nodeBuilderState = computeData.nodeBuilderState;

		if ( nodeBuilderState === undefined ) {

			const nodeBuilder = this.backend.createNodeBuilder( computeNode, this.renderer );
			nodeBuilder.build();

			nodeBuilderState = this._createNodeBuilderState( nodeBuilder );

			computeData.nodeBuilderState = nodeBuilderState;

		}

		return nodeBuilderState;

	}
```
</details>

##### `_createNodeBuilderState(nodeBuilder: NodeBuilder): NodeBuilderState`

<details><summary>Code</summary>

```ts
_createNodeBuilderState( nodeBuilder ) {

		return new NodeBuilderState(
			nodeBuilder.vertexShader,
			nodeBuilder.fragmentShader,
			nodeBuilder.computeShader,
			nodeBuilder.getAttributesArray(),
			nodeBuilder.getBindings(),
			nodeBuilder.updateNodes,
			nodeBuilder.updateBeforeNodes,
			nodeBuilder.updateAfterNodes,
			nodeBuilder.observer,
			nodeBuilder.transforms
		);

	}
```
</details>

##### `getEnvironmentNode(scene: Scene): Node`

<details><summary>Code</summary>

```ts
getEnvironmentNode( scene ) {

		this.updateEnvironment( scene );

		let environmentNode = null;

		if ( scene.environmentNode && scene.environmentNode.isNode ) {

			environmentNode = scene.environmentNode;

		} else {

			const sceneData = this.get( scene );

			if ( sceneData.environmentNode ) {

				environmentNode = sceneData.environmentNode;

			}

		}

		return environmentNode;

	}
```
</details>

##### `getBackgroundNode(scene: Scene): Node`

<details><summary>Code</summary>

```ts
getBackgroundNode( scene ) {

		this.updateBackground( scene );

		let backgroundNode = null;

		if ( scene.backgroundNode && scene.backgroundNode.isNode ) {

			backgroundNode = scene.backgroundNode;

		} else {

			const sceneData = this.get( scene );

			if ( sceneData.backgroundNode ) {

				backgroundNode = sceneData.backgroundNode;

			}

		}

		return backgroundNode;

	}
```
</details>

##### `getFogNode(scene: Scene): Node`

<details><summary>Code</summary>

```ts
getFogNode( scene ) {

		this.updateFog( scene );

		return scene.fogNode || this.get( scene ).fogNode || null;

	}
```
</details>

##### `getCacheKey(scene: Scene, lightsNode: LightsNode): number`

<details><summary>Code</summary>

```ts
getCacheKey( scene, lightsNode ) {

		_chainKeys[ 0 ] = scene;
		_chainKeys[ 1 ] = lightsNode;

		const callId = this.renderer.info.calls;

		const cacheKeyData = this.callHashCache.get( _chainKeys ) || {};

		if ( cacheKeyData.callId !== callId ) {

			const environmentNode = this.getEnvironmentNode( scene );
			const fogNode = this.getFogNode( scene );

			if ( lightsNode ) _cacheKeyValues.push( lightsNode.getCacheKey( true ) );
			if ( environmentNode ) _cacheKeyValues.push( environmentNode.getCacheKey() );
			if ( fogNode ) _cacheKeyValues.push( fogNode.getCacheKey() );

			_cacheKeyValues.push( this.renderer.getOutputRenderTarget() && this.renderer.getOutputRenderTarget().multiview ? 1 : 0 );
			_cacheKeyValues.push( this.renderer.shadowMap.enabled ? 1 : 0 );

			cacheKeyData.callId = callId;
			cacheKeyData.cacheKey = hashArray( _cacheKeyValues );

			this.callHashCache.set( _chainKeys, cacheKeyData );

			_cacheKeyValues.length = 0;

		}

		_chainKeys.length = 0;

		return cacheKeyData.cacheKey;

	}
```
</details>

##### `updateBackground(scene: Scene): void`

<details><summary>Code</summary>

```ts
updateBackground( scene ) {

		const sceneData = this.get( scene );
		const background = scene.background;

		if ( background ) {

			const forceUpdate = ( scene.backgroundBlurriness === 0 && sceneData.backgroundBlurriness > 0 ) || ( scene.backgroundBlurriness > 0 && sceneData.backgroundBlurriness === 0 );

			if ( sceneData.background !== background || forceUpdate ) {

				const backgroundNode = this.getCacheNode( 'background', background, () => {

					if ( background.isCubeTexture === true || ( background.mapping === EquirectangularReflectionMapping || background.mapping === EquirectangularRefractionMapping || background.mapping === CubeUVReflectionMapping ) ) {

						if ( scene.backgroundBlurriness > 0 || background.mapping === CubeUVReflectionMapping ) {

							return pmremTexture( background );

						} else {

							let envMap;

							if ( background.isCubeTexture === true ) {

								envMap = cubeTexture( background );

							} else {

								envMap = texture( background );

							}

							return cubeMapNode( envMap );

						}

					} else if ( background.isTexture === true ) {

						return texture( background, screenUV.flipY() ).setUpdateMatrix( true );

					} else if ( background.isColor !== true ) {

						console.error( 'WebGPUNodes: Unsupported background configuration.', background );

					}

				}, forceUpdate );

				sceneData.backgroundNode = backgroundNode;
				sceneData.background = background;
				sceneData.backgroundBlurriness = scene.backgroundBlurriness;

			}

		} else if ( sceneData.backgroundNode ) {

			delete sceneData.backgroundNode;
			delete sceneData.background;

		}

	}
```
</details>

##### `getCacheNode(type: string, object: any, callback: Function, forceUpdate: boolean): Node`

<details><summary>Code</summary>

```ts
getCacheNode( type, object, callback, forceUpdate = false ) {

		const nodeCache = this.cacheLib[ type ] || ( this.cacheLib[ type ] = new WeakMap() );

		let node = nodeCache.get( object );

		if ( node === undefined || forceUpdate ) {

			node = callback();
			nodeCache.set( object, node );

		}

		return node;

	}
```
</details>

##### `updateFog(scene: Scene): void`

<details><summary>Code</summary>

```ts
updateFog( scene ) {

		const sceneData = this.get( scene );
		const sceneFog = scene.fog;

		if ( sceneFog ) {

			if ( sceneData.fog !== sceneFog ) {

				const fogNode = this.getCacheNode( 'fog', sceneFog, () => {

					if ( sceneFog.isFogExp2 ) {

						const color = reference( 'color', 'color', sceneFog ).setGroup( renderGroup );
						const density = reference( 'density', 'float', sceneFog ).setGroup( renderGroup );

						return fog( color, densityFogFactor( density ) );

					} else if ( sceneFog.isFog ) {

						const color = reference( 'color', 'color', sceneFog ).setGroup( renderGroup );
						const near = reference( 'near', 'float', sceneFog ).setGroup( renderGroup );
						const far = reference( 'far', 'float', sceneFog ).setGroup( renderGroup );

						return fog( color, rangeFogFactor( near, far ) );

					} else {

						console.error( 'THREE.Renderer: Unsupported fog configuration.', sceneFog );

					}

				} );

				sceneData.fogNode = fogNode;
				sceneData.fog = sceneFog;

			}

		} else {

			delete sceneData.fogNode;
			delete sceneData.fog;

		}

	}
```
</details>

##### `updateEnvironment(scene: Scene): void`

<details><summary>Code</summary>

```ts
updateEnvironment( scene ) {

		const sceneData = this.get( scene );
		const environment = scene.environment;

		if ( environment ) {

			if ( sceneData.environment !== environment ) {

				const environmentNode = this.getCacheNode( 'environment', environment, () => {

					if ( environment.isCubeTexture === true ) {

						return cubeTexture( environment );

					} else if ( environment.isTexture === true ) {

						return texture( environment );

					} else {

						console.error( 'Nodes: Unsupported environment configuration.', environment );

					}

				} );

				sceneData.environmentNode = environmentNode;
				sceneData.environment = environment;

			}

		} else if ( sceneData.environmentNode ) {

			delete sceneData.environmentNode;
			delete sceneData.environment;

		}

	}
```
</details>

##### `getNodeFrame(renderer: Renderer, scene: any, object: any, camera: any, material: any): Renderer`

<details><summary>Code</summary>

```ts
getNodeFrame( renderer = this.renderer, scene = null, object = null, camera = null, material = null ) {

		const nodeFrame = this.nodeFrame;
		nodeFrame.renderer = renderer;
		nodeFrame.scene = scene;
		nodeFrame.object = object;
		nodeFrame.camera = camera;
		nodeFrame.material = material;

		return nodeFrame;

	}
```
</details>

##### `getNodeFrameForRender(renderObject: any): Renderer`

<details><summary>Code</summary>

```ts
getNodeFrameForRender( renderObject ) {

		return this.getNodeFrame( renderObject.renderer, renderObject.scene, renderObject.object, renderObject.camera, renderObject.material );

	}
```
</details>

##### `getOutputCacheKey(): string`

<details><summary>Code</summary>

```ts
getOutputCacheKey() {

		const renderer = this.renderer;

		return renderer.toneMapping + ',' + renderer.currentColorSpace + ',' + renderer.xr.isPresenting;

	}
```
</details>

##### `hasOutputChange(outputTarget: Texture): boolean`

<details><summary>Code</summary>

```ts
hasOutputChange( outputTarget ) {

		const cacheKey = _outputNodeMap.get( outputTarget );

		return cacheKey !== this.getOutputCacheKey();

	}
```
</details>

##### `getOutputNode(outputTarget: Texture): Node`

<details><summary>Code</summary>

```ts
getOutputNode( outputTarget ) {

		const renderer = this.renderer;
		const cacheKey = this.getOutputCacheKey();

		const output = outputTarget.isArrayTexture ?
			texture3D( outputTarget, vec3( screenUV, builtin( 'gl_ViewID_OVR' ) ) ).renderOutput( renderer.toneMapping, renderer.currentColorSpace ) :
			texture( outputTarget, screenUV ).renderOutput( renderer.toneMapping, renderer.currentColorSpace );

		_outputNodeMap.set( outputTarget, cacheKey );

		return output;

	}
```
</details>

##### `updateBefore(renderObject: RenderObject): void`

<details><summary>Code</summary>

```ts
updateBefore( renderObject ) {

		const nodeBuilder = renderObject.getNodeBuilderState();

		for ( const node of nodeBuilder.updateBeforeNodes ) {

			// update frame state for each node

			this.getNodeFrameForRender( renderObject ).updateBeforeNode( node );

		}

	}
```
</details>

##### `updateAfter(renderObject: RenderObject): void`

<details><summary>Code</summary>

```ts
updateAfter( renderObject ) {

		const nodeBuilder = renderObject.getNodeBuilderState();

		for ( const node of nodeBuilder.updateAfterNodes ) {

			// update frame state for each node

			this.getNodeFrameForRender( renderObject ).updateAfterNode( node );

		}

	}
```
</details>

##### `updateForCompute(computeNode: Node): void`

<details><summary>Code</summary>

```ts
updateForCompute( computeNode ) {

		const nodeFrame = this.getNodeFrame();
		const nodeBuilder = this.getForCompute( computeNode );

		for ( const node of nodeBuilder.updateNodes ) {

			nodeFrame.updateNode( node );

		}

	}
```
</details>

##### `updateForRender(renderObject: RenderObject): void`

<details><summary>Code</summary>

```ts
updateForRender( renderObject ) {

		const nodeFrame = this.getNodeFrameForRender( renderObject );
		const nodeBuilder = renderObject.getNodeBuilderState();

		for ( const node of nodeBuilder.updateNodes ) {

			nodeFrame.updateNode( node );

		}

	}
```
</details>

##### `needsRefresh(renderObject: RenderObject): boolean`

<details><summary>Code</summary>

```ts
needsRefresh( renderObject ) {

		const nodeFrame = this.getNodeFrameForRender( renderObject );
		const monitor = renderObject.getMonitor();

		return monitor.needsRefresh( renderObject, nodeFrame );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		super.dispose();

		this.nodeFrame = new NodeFrame();
		this.nodeBuilderCache = new Map();
		this.cacheLib = {};

	}
```
</details>


---