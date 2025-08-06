[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LightsNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 14 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 16 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/LightsNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `nodeObject` | `../tsl/TSLBase.js` |
| `property` | `../tsl/TSLBase.js` |
| `vec3` | `../tsl/TSLBase.js` |
| `hashArray` | `../core/NodeUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_lightsNodeRef` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `_hashData` | `any[]` | let/var | `[]` | ✗ |
| `lights` | `Light[]` | let/var | `this._lights` | ✗ |
| `light` | `Light` | let/var | `lights[ i ]` | ✗ |
| `hashMap` | `any` | let/var | `( light.map !== null ) ? light.map.id : - 1` | ✗ |
| `hashColorNode` | `any` | let/var | `( light.colorNode ) ? light.colorNode.getCacheKey() : - 1` | ✗ |
| `hash` | `any[]` | let/var | `[]` | ✗ |
| `lightNodes` | `any[]` | let/var | `[]` | ✗ |
| `previousLightNodes` | `LightingNode[]` | let/var | `this._lightNodes` | ✗ |
| `nodeLibrary` | `any` | let/var | `builder.renderer.library` | ✗ |
| `lightNode` | `any` | let/var | `null` | ✗ |
| `lightNode` | `any` | let/var | `null` | ✗ |
| `currentLightsNode` | `any` | let/var | `builder.lightsNode` | ✗ |
| `outgoingLightNode` | `any` | let/var | `this.outgoingLightNode` | ✗ |
| `context` | `any` | let/var | `builder.context` | ✗ |
| `lightingModel` | `any` | let/var | `context.lightingModel` | ✗ |


---

## Functions

### `sortLights(lights: any): any`

**Parameters:**

- **`lights`** `any`

**Returns:** `any`

**Calls:**

- `lights.sort`

<details><summary>Code</summary>

```typescript
( lights ) => {

	return lights.sort( ( a, b ) => a.id - b.id );

}
```
</details>

### `getLightNodeById(id: any, lightNodes: any): any`

**Parameters:**

- **`id`** `any`
- **`lightNodes`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
( id, lightNodes ) => {

	for ( const lightNode of lightNodes ) {

		if ( lightNode.isAnalyticLightNode && lightNode.light.id === id ) {

			return lightNode;

		}

	}

	return null;

}
```
</details>

### `LightsNode.customCacheKey(): number`

**JSDoc:**
```typescript
/**
	 * Overwrites the default {@link Node#customCacheKey} implementation by including
	 * light data into the cache key.
	 *
	 * @return {number} The custom cache key.
	 */
```

**Returns:** `number`

**Calls:**

- `_hashData.push`
- `light.colorNode.getCacheKey`
- `hashArray (from ../core/NodeUtils.js)`

<details><summary>Code</summary>

```typescript
customCacheKey() {

		const lights = this._lights;

		for ( let i = 0; i < lights.length; i ++ ) {

			const light = lights[ i ];

			_hashData.push( light.id );
			_hashData.push( light.castShadow ? 1 : 0 );

			if ( light.isSpotLight === true ) {

				const hashMap = ( light.map !== null ) ? light.map.id : - 1;
				const hashColorNode = ( light.colorNode ) ? light.colorNode.getCacheKey() : - 1;

				_hashData.push( hashMap, hashColorNode );

			}

		}

		const cacheKey = hashArray( _hashData );

		_hashData.length = 0;

		return cacheKey;

	}
```
</details>

### `LightsNode.getHash(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * Computes a hash value for identifying the current light nodes setup.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @return {string} The computed hash.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.setupLightsNode`
- `hash.push`
- `lightNode.getSelf().getHash`
- `hash.join`

<details><summary>Code</summary>

```typescript
getHash( builder ) {

		if ( this._lightNodesHash === null ) {

			if ( this._lightNodes === null ) this.setupLightsNode( builder );

			const hash = [];

			for ( const lightNode of this._lightNodes ) {

				hash.push( lightNode.getSelf().getHash() );

			}

			this._lightNodesHash = 'lights-' + hash.join( ',' );

		}

		return this._lightNodesHash;

	}
```
</details>

### `LightsNode.analyze(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `builder.getNodeProperties`
- `node.build`
- `properties.outputNode.build`

<details><summary>Code</summary>

```typescript
analyze( builder ) {

		const properties = builder.getNodeProperties( this );

		for ( const node of properties.nodes ) {

			node.build( builder );

		}

		properties.outputNode.build( builder );

	}
```
</details>

### `LightsNode.setupLightsNode(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Creates lighting nodes for each scene light. This makes it possible to further
	 * process lights in the node system.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `sortLights`
- `lightNodes.push`
- `nodeObject (from ../tsl/TSLBase.js)`
- `getLightNodeById`
- `nodeLibrary.getLightNodeClass`
- `console.warn`
- `_lightsNodeRef.has`
- `_lightsNodeRef.set`
- `_lightsNodeRef.get`

**Internal Comments:**
```
// find the corresponding node type for a given light (x2)
```

<details><summary>Code</summary>

```typescript
setupLightsNode( builder ) {

		const lightNodes = [];

		const previousLightNodes = this._lightNodes;

		const lights = sortLights( this._lights );
		const nodeLibrary = builder.renderer.library;

		for ( const light of lights ) {

			if ( light.isNode ) {

				lightNodes.push( nodeObject( light ) );

			} else {

				let lightNode = null;

				if ( previousLightNodes !== null ) {

					lightNode = getLightNodeById( light.id, previousLightNodes ); // reuse existing light node

				}

				if ( lightNode === null ) {

					// find the corresponding node type for a given light

					const lightNodeClass = nodeLibrary.getLightNodeClass( light.constructor );

					if ( lightNodeClass === null ) {

						console.warn( `LightsNode.setupNodeLights: Light node not found for ${ light.constructor.name }` );
						continue;

					}

					let lightNode = null;

					if ( ! _lightsNodeRef.has( light ) ) {

						lightNode = nodeObject( new lightNodeClass( light ) );
						_lightsNodeRef.set( light, lightNode );

					} else {

						lightNode = _lightsNodeRef.get( light );

					}

					lightNodes.push( lightNode );

				}

			}

		}

		this._lightNodes = lightNodes;

	}
```
</details>

### `LightsNode.setupDirectLight(builder: any, lightNode: any, lightData: any): void`

**JSDoc:**
```typescript
/**
	 * Sets up a direct light in the lighting model.
	 *
	 * @param {Object} builder - The builder object containing the context and stack.
	 * @param {Object} lightNode - The light node.
	 * @param {Object} lightData - The light object containing color and direction properties.
	 */
```

**Parameters:**

- **`builder`** `any`
- **`lightNode`** `any`
- **`lightData`** `any`

**Returns:** `void`

**Calls:**

- `lightingModel.direct`

<details><summary>Code</summary>

```typescript
setupDirectLight( builder, lightNode, lightData ) {

		const { lightingModel, reflectedLight } = builder.context;

		lightingModel.direct( {
			...lightData,
			lightNode,
			reflectedLight
		}, builder );

	}
```
</details>

### `LightsNode.setupDirectRectAreaLight(builder: any, lightNode: any, lightData: any): void`

**Parameters:**

- **`builder`** `any`
- **`lightNode`** `any`
- **`lightData`** `any`

**Returns:** `void`

**Calls:**

- `lightingModel.directRectArea`

<details><summary>Code</summary>

```typescript
setupDirectRectAreaLight( builder, lightNode, lightData ) {

		const { lightingModel, reflectedLight } = builder.context;

		lightingModel.directRectArea( {
			...lightData,
			lightNode,
			reflectedLight
		}, builder );

	}
```
</details>

### `LightsNode.setupLights(builder: NodeBuilder, lightNodes: LightingNode[]): void`

**JSDoc:**
```typescript
/**
	 * Setups the internal lights by building all respective
	 * light nodes.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @param {Array<LightingNode>} lightNodes - An array of lighting nodes.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`lightNodes`** `LightingNode[]`

**Returns:** `void`

**Calls:**

- `lightNode.build`

<details><summary>Code</summary>

```typescript
setupLights( builder, lightNodes ) {

		for ( const lightNode of lightNodes ) {

			lightNode.build( builder );

		}

	}
```
</details>

### `LightsNode.getLightNodes(builder: any): LightingNode[]`

**Parameters:**

- **`builder`** `any`

**Returns:** `LightingNode[]`

**Calls:**

- `this.setupLightsNode`

<details><summary>Code</summary>

```typescript
getLightNodes( builder ) {

		if ( this._lightNodes === null ) this.setupLightsNode( builder );

		return this._lightNodes;

	}
```
</details>

### `LightsNode.setup(builder: NodeBuilder): any`

**JSDoc:**
```typescript
/**
	 * The implementation makes sure that for each light in the scene
	 * there is a corresponding light node. By building the light nodes
	 * and evaluating the lighting model the outgoing light is computed.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @return {Node<vec3>} A node representing the outgoing light.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `any`

**Calls:**

- `builder.getNodeProperties`
- `builder.addStack`
- `lightingModel.start`
- `directDiffuse.add`
- `vec3 (from ../tsl/TSLBase.js)`
- `backdropAlpha.mix`
- `totalDiffuseNode.assign`
- `totalSpecularNode.assign`
- `directSpecular.add`
- `outgoingLightNode.assign`
- `totalDiffuseNode.add`
- `lightingModel.finish`
- `outgoingLightNode.bypass`
- `builder.removeStack`

**Internal Comments:**
```
// (x23)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const currentLightsNode = builder.lightsNode;

		builder.lightsNode = this;

		//

		let outgoingLightNode = this.outgoingLightNode;

		const context = builder.context;
		const lightingModel = context.lightingModel;

		const properties = builder.getNodeProperties( this );

		if ( lightingModel ) {

			const { totalDiffuseNode, totalSpecularNode } = this;

			context.outgoingLight = outgoingLightNode;

			const stack = builder.addStack();

			//

			properties.nodes = stack.nodes;

			//

			lightingModel.start( builder );

			//

			const { backdrop, backdropAlpha } = context;
			const { directDiffuse, directSpecular, indirectDiffuse, indirectSpecular } = context.reflectedLight;

			let totalDiffuse = directDiffuse.add( indirectDiffuse );

			if ( backdrop !== null ) {

				if ( backdropAlpha !== null ) {

					totalDiffuse = vec3( backdropAlpha.mix( totalDiffuse, backdrop ) );

				} else {

					totalDiffuse = vec3( backdrop );

				}

				context.material.transparent = true;

			}

			totalDiffuseNode.assign( totalDiffuse );
			totalSpecularNode.assign( directSpecular.add( indirectSpecular ) );

			outgoingLightNode.assign( totalDiffuseNode.add( totalSpecularNode ) );

			//

			lightingModel.finish( builder );

			//

			outgoingLightNode = outgoingLightNode.bypass( builder.removeStack() );

		} else {

			properties.nodes = [];

		}

		//

		builder.lightsNode = currentLightsNode;

		return outgoingLightNode;

	}
```
</details>

### `LightsNode.setLights(lights: Light[]): LightsNode`

**JSDoc:**
```typescript
/**
	 * Configures this node with an array of lights.
	 *
	 * @param {Array<Light>} lights - An array of lights.
	 * @return {LightsNode} A reference to this node.
	 */
```

**Parameters:**

- **`lights`** `Light[]`

**Returns:** `LightsNode`

<details><summary>Code</summary>

```typescript
setLights( lights ) {

		this._lights = lights;

		this._lightNodes = null;
		this._lightNodesHash = null;

		return this;

	}
```
</details>

### `LightsNode.getLights(): Light[]`

**JSDoc:**
```typescript
/**
	 * Returns an array of the scene's lights.
	 *
	 * @return {Array<Light>} The scene's lights.
	 */
```

**Returns:** `Light[]`

<details><summary>Code</summary>

```typescript
getLights() {

		return this._lights;

	}
```
</details>

### `lights(lights: Light[]): LightsNode`

**Parameters:**

- **`lights`** `Light[]`

**Returns:** `LightsNode`

**Calls:**

- `nodeObject( new LightsNode() ).setLights`

<details><summary>Code</summary>

```typescript
( lights = [] ) => nodeObject( new LightsNode() ).setLights( lights )
```
</details>


---

## Classes

### `LightsNode`

<details><summary>Class Code</summary>

```ts
class LightsNode extends Node {

	static get type() {

		return 'LightsNode';

	}

	/**
	 * Constructs a new lights node.
	 */
	constructor() {

		super( 'vec3' );

		/**
		 * A node representing the total diffuse light.
		 *
		 * @type {Node<vec3>}
		 */
		this.totalDiffuseNode = property( 'vec3', 'totalDiffuse' );

		/**
		 * A node representing the total specular light.
		 *
		 * @type {Node<vec3>}
		 */
		this.totalSpecularNode = property( 'vec3', 'totalSpecular' );

		/**
		 * A node representing the outgoing light.
		 *
		 * @type {Node<vec3>}
		 */
		this.outgoingLightNode = property( 'vec3', 'outgoingLight' );

		/**
		 * An array representing the lights in the scene.
		 *
		 * @private
		 * @type {Array<Light>}
		 */
		this._lights = [];

		/**
		 * For each light in the scene, this node will create a
		 * corresponding light node.
		 *
		 * @private
		 * @type {?Array<LightingNode>}
		 * @default null
		 */
		this._lightNodes = null;

		/**
		 * A hash for identifying the current light nodes setup.
		 *
		 * @private
		 * @type {?string}
		 * @default null
		 */
		this._lightNodesHash = null;

		/**
		 * `LightsNode` sets this property to `true` by default.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.global = true;

	}

	/**
	 * Overwrites the default {@link Node#customCacheKey} implementation by including
	 * light data into the cache key.
	 *
	 * @return {number} The custom cache key.
	 */
	customCacheKey() {

		const lights = this._lights;

		for ( let i = 0; i < lights.length; i ++ ) {

			const light = lights[ i ];

			_hashData.push( light.id );
			_hashData.push( light.castShadow ? 1 : 0 );

			if ( light.isSpotLight === true ) {

				const hashMap = ( light.map !== null ) ? light.map.id : - 1;
				const hashColorNode = ( light.colorNode ) ? light.colorNode.getCacheKey() : - 1;

				_hashData.push( hashMap, hashColorNode );

			}

		}

		const cacheKey = hashArray( _hashData );

		_hashData.length = 0;

		return cacheKey;

	}

	/**
	 * Computes a hash value for identifying the current light nodes setup.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @return {string} The computed hash.
	 */
	getHash( builder ) {

		if ( this._lightNodesHash === null ) {

			if ( this._lightNodes === null ) this.setupLightsNode( builder );

			const hash = [];

			for ( const lightNode of this._lightNodes ) {

				hash.push( lightNode.getSelf().getHash() );

			}

			this._lightNodesHash = 'lights-' + hash.join( ',' );

		}

		return this._lightNodesHash;

	}

	analyze( builder ) {

		const properties = builder.getNodeProperties( this );

		for ( const node of properties.nodes ) {

			node.build( builder );

		}

		properties.outputNode.build( builder );

	}

	/**
	 * Creates lighting nodes for each scene light. This makes it possible to further
	 * process lights in the node system.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 */
	setupLightsNode( builder ) {

		const lightNodes = [];

		const previousLightNodes = this._lightNodes;

		const lights = sortLights( this._lights );
		const nodeLibrary = builder.renderer.library;

		for ( const light of lights ) {

			if ( light.isNode ) {

				lightNodes.push( nodeObject( light ) );

			} else {

				let lightNode = null;

				if ( previousLightNodes !== null ) {

					lightNode = getLightNodeById( light.id, previousLightNodes ); // reuse existing light node

				}

				if ( lightNode === null ) {

					// find the corresponding node type for a given light

					const lightNodeClass = nodeLibrary.getLightNodeClass( light.constructor );

					if ( lightNodeClass === null ) {

						console.warn( `LightsNode.setupNodeLights: Light node not found for ${ light.constructor.name }` );
						continue;

					}

					let lightNode = null;

					if ( ! _lightsNodeRef.has( light ) ) {

						lightNode = nodeObject( new lightNodeClass( light ) );
						_lightsNodeRef.set( light, lightNode );

					} else {

						lightNode = _lightsNodeRef.get( light );

					}

					lightNodes.push( lightNode );

				}

			}

		}

		this._lightNodes = lightNodes;

	}

	/**
	 * Sets up a direct light in the lighting model.
	 *
	 * @param {Object} builder - The builder object containing the context and stack.
	 * @param {Object} lightNode - The light node.
	 * @param {Object} lightData - The light object containing color and direction properties.
	 */
	setupDirectLight( builder, lightNode, lightData ) {

		const { lightingModel, reflectedLight } = builder.context;

		lightingModel.direct( {
			...lightData,
			lightNode,
			reflectedLight
		}, builder );

	}

	setupDirectRectAreaLight( builder, lightNode, lightData ) {

		const { lightingModel, reflectedLight } = builder.context;

		lightingModel.directRectArea( {
			...lightData,
			lightNode,
			reflectedLight
		}, builder );

	}

	/**
	 * Setups the internal lights by building all respective
	 * light nodes.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @param {Array<LightingNode>} lightNodes - An array of lighting nodes.
	 */
	setupLights( builder, lightNodes ) {

		for ( const lightNode of lightNodes ) {

			lightNode.build( builder );

		}

	}

	getLightNodes( builder ) {

		if ( this._lightNodes === null ) this.setupLightsNode( builder );

		return this._lightNodes;

	}

	/**
	 * The implementation makes sure that for each light in the scene
	 * there is a corresponding light node. By building the light nodes
	 * and evaluating the lighting model the outgoing light is computed.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @return {Node<vec3>} A node representing the outgoing light.
	 */
	setup( builder ) {

		const currentLightsNode = builder.lightsNode;

		builder.lightsNode = this;

		//

		let outgoingLightNode = this.outgoingLightNode;

		const context = builder.context;
		const lightingModel = context.lightingModel;

		const properties = builder.getNodeProperties( this );

		if ( lightingModel ) {

			const { totalDiffuseNode, totalSpecularNode } = this;

			context.outgoingLight = outgoingLightNode;

			const stack = builder.addStack();

			//

			properties.nodes = stack.nodes;

			//

			lightingModel.start( builder );

			//

			const { backdrop, backdropAlpha } = context;
			const { directDiffuse, directSpecular, indirectDiffuse, indirectSpecular } = context.reflectedLight;

			let totalDiffuse = directDiffuse.add( indirectDiffuse );

			if ( backdrop !== null ) {

				if ( backdropAlpha !== null ) {

					totalDiffuse = vec3( backdropAlpha.mix( totalDiffuse, backdrop ) );

				} else {

					totalDiffuse = vec3( backdrop );

				}

				context.material.transparent = true;

			}

			totalDiffuseNode.assign( totalDiffuse );
			totalSpecularNode.assign( directSpecular.add( indirectSpecular ) );

			outgoingLightNode.assign( totalDiffuseNode.add( totalSpecularNode ) );

			//

			lightingModel.finish( builder );

			//

			outgoingLightNode = outgoingLightNode.bypass( builder.removeStack() );

		} else {

			properties.nodes = [];

		}

		//

		builder.lightsNode = currentLightsNode;

		return outgoingLightNode;

	}

	/**
	 * Configures this node with an array of lights.
	 *
	 * @param {Array<Light>} lights - An array of lights.
	 * @return {LightsNode} A reference to this node.
	 */
	setLights( lights ) {

		this._lights = lights;

		this._lightNodes = null;
		this._lightNodesHash = null;

		return this;

	}

	/**
	 * Returns an array of the scene's lights.
	 *
	 * @return {Array<Light>} The scene's lights.
	 */
	getLights() {

		return this._lights;

	}

	/**
	 * Whether the scene has lights or not.
	 *
	 * @type {boolean}
	 */
	get hasLights() {

		return this._lights.length > 0;

	}

}
```
</details>

#### Methods

##### `customCacheKey(): number`

<details><summary>Code</summary>

```ts
customCacheKey() {

		const lights = this._lights;

		for ( let i = 0; i < lights.length; i ++ ) {

			const light = lights[ i ];

			_hashData.push( light.id );
			_hashData.push( light.castShadow ? 1 : 0 );

			if ( light.isSpotLight === true ) {

				const hashMap = ( light.map !== null ) ? light.map.id : - 1;
				const hashColorNode = ( light.colorNode ) ? light.colorNode.getCacheKey() : - 1;

				_hashData.push( hashMap, hashColorNode );

			}

		}

		const cacheKey = hashArray( _hashData );

		_hashData.length = 0;

		return cacheKey;

	}
```
</details>

##### `getHash(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getHash( builder ) {

		if ( this._lightNodesHash === null ) {

			if ( this._lightNodes === null ) this.setupLightsNode( builder );

			const hash = [];

			for ( const lightNode of this._lightNodes ) {

				hash.push( lightNode.getSelf().getHash() );

			}

			this._lightNodesHash = 'lights-' + hash.join( ',' );

		}

		return this._lightNodesHash;

	}
```
</details>

##### `analyze(builder: any): void`

<details><summary>Code</summary>

```ts
analyze( builder ) {

		const properties = builder.getNodeProperties( this );

		for ( const node of properties.nodes ) {

			node.build( builder );

		}

		properties.outputNode.build( builder );

	}
```
</details>

##### `setupLightsNode(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
setupLightsNode( builder ) {

		const lightNodes = [];

		const previousLightNodes = this._lightNodes;

		const lights = sortLights( this._lights );
		const nodeLibrary = builder.renderer.library;

		for ( const light of lights ) {

			if ( light.isNode ) {

				lightNodes.push( nodeObject( light ) );

			} else {

				let lightNode = null;

				if ( previousLightNodes !== null ) {

					lightNode = getLightNodeById( light.id, previousLightNodes ); // reuse existing light node

				}

				if ( lightNode === null ) {

					// find the corresponding node type for a given light

					const lightNodeClass = nodeLibrary.getLightNodeClass( light.constructor );

					if ( lightNodeClass === null ) {

						console.warn( `LightsNode.setupNodeLights: Light node not found for ${ light.constructor.name }` );
						continue;

					}

					let lightNode = null;

					if ( ! _lightsNodeRef.has( light ) ) {

						lightNode = nodeObject( new lightNodeClass( light ) );
						_lightsNodeRef.set( light, lightNode );

					} else {

						lightNode = _lightsNodeRef.get( light );

					}

					lightNodes.push( lightNode );

				}

			}

		}

		this._lightNodes = lightNodes;

	}
```
</details>

##### `setupDirectLight(builder: any, lightNode: any, lightData: any): void`

<details><summary>Code</summary>

```ts
setupDirectLight( builder, lightNode, lightData ) {

		const { lightingModel, reflectedLight } = builder.context;

		lightingModel.direct( {
			...lightData,
			lightNode,
			reflectedLight
		}, builder );

	}
```
</details>

##### `setupDirectRectAreaLight(builder: any, lightNode: any, lightData: any): void`

<details><summary>Code</summary>

```ts
setupDirectRectAreaLight( builder, lightNode, lightData ) {

		const { lightingModel, reflectedLight } = builder.context;

		lightingModel.directRectArea( {
			...lightData,
			lightNode,
			reflectedLight
		}, builder );

	}
```
</details>

##### `setupLights(builder: NodeBuilder, lightNodes: LightingNode[]): void`

<details><summary>Code</summary>

```ts
setupLights( builder, lightNodes ) {

		for ( const lightNode of lightNodes ) {

			lightNode.build( builder );

		}

	}
```
</details>

##### `getLightNodes(builder: any): LightingNode[]`

<details><summary>Code</summary>

```ts
getLightNodes( builder ) {

		if ( this._lightNodes === null ) this.setupLightsNode( builder );

		return this._lightNodes;

	}
```
</details>

##### `setup(builder: NodeBuilder): any`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const currentLightsNode = builder.lightsNode;

		builder.lightsNode = this;

		//

		let outgoingLightNode = this.outgoingLightNode;

		const context = builder.context;
		const lightingModel = context.lightingModel;

		const properties = builder.getNodeProperties( this );

		if ( lightingModel ) {

			const { totalDiffuseNode, totalSpecularNode } = this;

			context.outgoingLight = outgoingLightNode;

			const stack = builder.addStack();

			//

			properties.nodes = stack.nodes;

			//

			lightingModel.start( builder );

			//

			const { backdrop, backdropAlpha } = context;
			const { directDiffuse, directSpecular, indirectDiffuse, indirectSpecular } = context.reflectedLight;

			let totalDiffuse = directDiffuse.add( indirectDiffuse );

			if ( backdrop !== null ) {

				if ( backdropAlpha !== null ) {

					totalDiffuse = vec3( backdropAlpha.mix( totalDiffuse, backdrop ) );

				} else {

					totalDiffuse = vec3( backdrop );

				}

				context.material.transparent = true;

			}

			totalDiffuseNode.assign( totalDiffuse );
			totalSpecularNode.assign( directSpecular.add( indirectSpecular ) );

			outgoingLightNode.assign( totalDiffuseNode.add( totalSpecularNode ) );

			//

			lightingModel.finish( builder );

			//

			outgoingLightNode = outgoingLightNode.bypass( builder.removeStack() );

		} else {

			properties.nodes = [];

		}

		//

		builder.lightsNode = currentLightsNode;

		return outgoingLightNode;

	}
```
</details>

##### `setLights(lights: Light[]): LightsNode`

<details><summary>Code</summary>

```ts
setLights( lights ) {

		this._lights = lights;

		this._lightNodes = null;
		this._lightNodesHash = null;

		return this;

	}
```
</details>

##### `getLights(): Light[]`

<details><summary>Code</summary>

```ts
getLights() {

		return this._lights;

	}
```
</details>


---