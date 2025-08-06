[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RenderObjects.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/RenderObjects.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ChainMap` | `./ChainMap.js` |
| `RenderObject` | `./RenderObject.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_chainKeys` | `any[]` | let/var | `[]` | ✗ |
| `renderObject` | `RenderObject` | let/var | `new RenderObject( nodes, geometries, renderer, object, material, scene, camer...` | ✗ |


---

## Functions

### `RenderObjects.get(object: Object3D, material: Material, scene: Scene, camera: Camera, lightsNode: LightsNode, renderContext: RenderContext, clippingContext: ClippingContext, passId: string): RenderObject`

**JSDoc:**
```typescript
/**
	 * Returns a render object for the given object and state data.
	 *
	 * @param {Object3D} object - The 3D object.
	 * @param {Material} material - The 3D object's material.
	 * @param {Scene} scene - The scene the 3D object belongs to.
	 * @param {Camera} camera - The camera the 3D object should be rendered with.
	 * @param {LightsNode} lightsNode - The lights node.
	 * @param {RenderContext} renderContext - The render context.
	 * @param {ClippingContext} clippingContext - The clipping context.
	 * @param {string} [passId] - An optional ID for identifying the pass.
	 * @return {RenderObject} The render object.
	 */
```

**Parameters:**

- **`object`** `Object3D`
- **`material`** `Material`
- **`scene`** `Scene`
- **`camera`** `Camera`
- **`lightsNode`** `LightsNode`
- **`renderContext`** `RenderContext`
- **`clippingContext`** `ClippingContext`
- **`passId`** `string`

**Returns:** `RenderObject`

**Calls:**

- `this.getChainMap`
- `chainMap.get`
- `this.createRenderObject`
- `chainMap.set`
- `renderObject.updateClipping`
- `renderObject.setGeometry`
- `renderObject.getCacheKey`
- `renderObject.dispose`
- `this.get`

**Internal Comments:**
```
// reuse chainArray (x4)
```

<details><summary>Code</summary>

```typescript
get( object, material, scene, camera, lightsNode, renderContext, clippingContext, passId ) {

		const chainMap = this.getChainMap( passId );

		// reuse chainArray
		_chainKeys[ 0 ] = object;
		_chainKeys[ 1 ] = material;
		_chainKeys[ 2 ] = renderContext;
		_chainKeys[ 3 ] = lightsNode;

		let renderObject = chainMap.get( _chainKeys );

		if ( renderObject === undefined ) {

			renderObject = this.createRenderObject( this.nodes, this.geometries, this.renderer, object, material, scene, camera, lightsNode, renderContext, clippingContext, passId );

			chainMap.set( _chainKeys, renderObject );

		} else {

			renderObject.updateClipping( clippingContext );

			if ( renderObject.needsGeometryUpdate ) {

				renderObject.setGeometry( object.geometry );

			}

			if ( renderObject.version !== material.version || renderObject.needsUpdate ) {

				if ( renderObject.initialCacheKey !== renderObject.getCacheKey() ) {

					renderObject.dispose();

					renderObject = this.get( object, material, scene, camera, lightsNode, renderContext, clippingContext, passId );

				} else {

					renderObject.version = material.version;

				}

			}

		}

		_chainKeys.length = 0;

		return renderObject;

	}
```
</details>

### `RenderObjects.getChainMap(passId: string): ChainMap`

**JSDoc:**
```typescript
/**
	 * Returns a chain map for the given pass ID.
	 *
	 * @param {string} [passId='default'] - The pass ID.
	 * @return {ChainMap} The chain map.
	 */
```

**Parameters:**

- **`passId`** `string`

**Returns:** `ChainMap`

<details><summary>Code</summary>

```typescript
getChainMap( passId = 'default' ) {

		return this.chainMaps[ passId ] || ( this.chainMaps[ passId ] = new ChainMap() );

	}
```
</details>

### `RenderObjects.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
dispose() {

		this.chainMaps = {};

	}
```
</details>

### `RenderObjects.createRenderObject(nodes: Nodes, geometries: Geometries, renderer: Renderer, object: Object3D, material: Material, scene: Scene, camera: Camera, lightsNode: LightsNode, renderContext: RenderContext, clippingContext: ClippingContext, passId: string): RenderObject`

**JSDoc:**
```typescript
/**
	 * Factory method for creating render objects with the given list of parameters.
	 *
	 * @param {Nodes} nodes - Renderer component for managing nodes related logic.
	 * @param {Geometries} geometries - Renderer component for managing geometries.
	 * @param {Renderer} renderer - The renderer.
	 * @param {Object3D} object - The 3D object.
	 * @param {Material} material - The object's material.
	 * @param {Scene} scene - The scene the 3D object belongs to.
	 * @param {Camera} camera - The camera the object should be rendered with.
	 * @param {LightsNode} lightsNode - The lights node.
	 * @param {RenderContext} renderContext - The render context.
	 * @param {ClippingContext} clippingContext - The clipping context.
	 * @param {string} [passId] - An optional ID for identifying the pass.
	 * @return {RenderObject} The render object.
	 */
```

**Parameters:**

- **`nodes`** `Nodes`
- **`geometries`** `Geometries`
- **`renderer`** `Renderer`
- **`object`** `Object3D`
- **`material`** `Material`
- **`scene`** `Scene`
- **`camera`** `Camera`
- **`lightsNode`** `LightsNode`
- **`renderContext`** `RenderContext`
- **`clippingContext`** `ClippingContext`
- **`passId`** `string`

**Returns:** `RenderObject`

**Calls:**

- `this.getChainMap`
- `this.pipelines.delete`
- `this.bindings.delete`
- `this.nodes.delete`
- `chainMap.delete`
- `renderObject.getChainArray`

<details><summary>Code</summary>

```typescript
createRenderObject( nodes, geometries, renderer, object, material, scene, camera, lightsNode, renderContext, clippingContext, passId ) {

		const chainMap = this.getChainMap( passId );

		const renderObject = new RenderObject( nodes, geometries, renderer, object, material, scene, camera, lightsNode, renderContext, clippingContext );

		renderObject.onDispose = () => {

			this.pipelines.delete( renderObject );
			this.bindings.delete( renderObject );
			this.nodes.delete( renderObject );

			chainMap.delete( renderObject.getChainArray() );

		};

		return renderObject;

	}
```
</details>


---

## Classes

### `RenderObjects`

<details><summary>Class Code</summary>

```ts
class RenderObjects {

	/**
	 * Constructs a new render object management component.
	 *
	 * @param {Renderer} renderer - The renderer.
	 * @param {Nodes} nodes - Renderer component for managing nodes related logic.
	 * @param {Geometries} geometries - Renderer component for managing geometries.
	 * @param {Pipelines} pipelines - Renderer component for managing pipelines.
	 * @param {Bindings} bindings - Renderer component for managing bindings.
	 * @param {Info} info - Renderer component for managing metrics and monitoring data.
	 */
	constructor( renderer, nodes, geometries, pipelines, bindings, info ) {

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

		/**
		 * Renderer component for managing geometries.
		 *
		 * @type {Geometries}
		 */
		this.geometries = geometries;

		/**
		 * Renderer component for managing pipelines.
		 *
		 * @type {Pipelines}
		 */
		this.pipelines = pipelines;

		/**
		 * Renderer component for managing bindings.
		 *
		 * @type {Bindings}
		 */
		this.bindings = bindings;

		/**
		 * Renderer component for managing metrics and monitoring data.
		 *
		 * @type {Info}
		 */
		this.info = info;

		/**
		 * A dictionary that manages render contexts in chain maps
		 * for each pass ID.
		 *
		 * @type {Object<string,ChainMap>}
		 */
		this.chainMaps = {};

	}

	/**
	 * Returns a render object for the given object and state data.
	 *
	 * @param {Object3D} object - The 3D object.
	 * @param {Material} material - The 3D object's material.
	 * @param {Scene} scene - The scene the 3D object belongs to.
	 * @param {Camera} camera - The camera the 3D object should be rendered with.
	 * @param {LightsNode} lightsNode - The lights node.
	 * @param {RenderContext} renderContext - The render context.
	 * @param {ClippingContext} clippingContext - The clipping context.
	 * @param {string} [passId] - An optional ID for identifying the pass.
	 * @return {RenderObject} The render object.
	 */
	get( object, material, scene, camera, lightsNode, renderContext, clippingContext, passId ) {

		const chainMap = this.getChainMap( passId );

		// reuse chainArray
		_chainKeys[ 0 ] = object;
		_chainKeys[ 1 ] = material;
		_chainKeys[ 2 ] = renderContext;
		_chainKeys[ 3 ] = lightsNode;

		let renderObject = chainMap.get( _chainKeys );

		if ( renderObject === undefined ) {

			renderObject = this.createRenderObject( this.nodes, this.geometries, this.renderer, object, material, scene, camera, lightsNode, renderContext, clippingContext, passId );

			chainMap.set( _chainKeys, renderObject );

		} else {

			renderObject.updateClipping( clippingContext );

			if ( renderObject.needsGeometryUpdate ) {

				renderObject.setGeometry( object.geometry );

			}

			if ( renderObject.version !== material.version || renderObject.needsUpdate ) {

				if ( renderObject.initialCacheKey !== renderObject.getCacheKey() ) {

					renderObject.dispose();

					renderObject = this.get( object, material, scene, camera, lightsNode, renderContext, clippingContext, passId );

				} else {

					renderObject.version = material.version;

				}

			}

		}

		_chainKeys.length = 0;

		return renderObject;

	}

	/**
	 * Returns a chain map for the given pass ID.
	 *
	 * @param {string} [passId='default'] - The pass ID.
	 * @return {ChainMap} The chain map.
	 */
	getChainMap( passId = 'default' ) {

		return this.chainMaps[ passId ] || ( this.chainMaps[ passId ] = new ChainMap() );

	}

	/**
	 * Frees internal resources.
	 */
	dispose() {

		this.chainMaps = {};

	}

	/**
	 * Factory method for creating render objects with the given list of parameters.
	 *
	 * @param {Nodes} nodes - Renderer component for managing nodes related logic.
	 * @param {Geometries} geometries - Renderer component for managing geometries.
	 * @param {Renderer} renderer - The renderer.
	 * @param {Object3D} object - The 3D object.
	 * @param {Material} material - The object's material.
	 * @param {Scene} scene - The scene the 3D object belongs to.
	 * @param {Camera} camera - The camera the object should be rendered with.
	 * @param {LightsNode} lightsNode - The lights node.
	 * @param {RenderContext} renderContext - The render context.
	 * @param {ClippingContext} clippingContext - The clipping context.
	 * @param {string} [passId] - An optional ID for identifying the pass.
	 * @return {RenderObject} The render object.
	 */
	createRenderObject( nodes, geometries, renderer, object, material, scene, camera, lightsNode, renderContext, clippingContext, passId ) {

		const chainMap = this.getChainMap( passId );

		const renderObject = new RenderObject( nodes, geometries, renderer, object, material, scene, camera, lightsNode, renderContext, clippingContext );

		renderObject.onDispose = () => {

			this.pipelines.delete( renderObject );
			this.bindings.delete( renderObject );
			this.nodes.delete( renderObject );

			chainMap.delete( renderObject.getChainArray() );

		};

		return renderObject;

	}


}
```
</details>

#### Methods

##### `get(object: Object3D, material: Material, scene: Scene, camera: Camera, lightsNode: LightsNode, renderContext: RenderContext, clippingContext: ClippingContext, passId: string): RenderObject`

<details><summary>Code</summary>

```ts
get( object, material, scene, camera, lightsNode, renderContext, clippingContext, passId ) {

		const chainMap = this.getChainMap( passId );

		// reuse chainArray
		_chainKeys[ 0 ] = object;
		_chainKeys[ 1 ] = material;
		_chainKeys[ 2 ] = renderContext;
		_chainKeys[ 3 ] = lightsNode;

		let renderObject = chainMap.get( _chainKeys );

		if ( renderObject === undefined ) {

			renderObject = this.createRenderObject( this.nodes, this.geometries, this.renderer, object, material, scene, camera, lightsNode, renderContext, clippingContext, passId );

			chainMap.set( _chainKeys, renderObject );

		} else {

			renderObject.updateClipping( clippingContext );

			if ( renderObject.needsGeometryUpdate ) {

				renderObject.setGeometry( object.geometry );

			}

			if ( renderObject.version !== material.version || renderObject.needsUpdate ) {

				if ( renderObject.initialCacheKey !== renderObject.getCacheKey() ) {

					renderObject.dispose();

					renderObject = this.get( object, material, scene, camera, lightsNode, renderContext, clippingContext, passId );

				} else {

					renderObject.version = material.version;

				}

			}

		}

		_chainKeys.length = 0;

		return renderObject;

	}
```
</details>

##### `getChainMap(passId: string): ChainMap`

<details><summary>Code</summary>

```ts
getChainMap( passId = 'default' ) {

		return this.chainMaps[ passId ] || ( this.chainMaps[ passId ] = new ChainMap() );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.chainMaps = {};

	}
```
</details>

##### `createRenderObject(nodes: Nodes, geometries: Geometries, renderer: Renderer, object: Object3D, material: Material, scene: Scene, camera: Camera, lightsNode: LightsNode, renderContext: RenderContext, clippingContext: ClippingContext, passId: string): RenderObject`

<details><summary>Code</summary>

```ts
createRenderObject( nodes, geometries, renderer, object, material, scene, camera, lightsNode, renderContext, clippingContext, passId ) {

		const chainMap = this.getChainMap( passId );

		const renderObject = new RenderObject( nodes, geometries, renderer, object, material, scene, camera, lightsNode, renderContext, clippingContext );

		renderObject.onDispose = () => {

			this.pipelines.delete( renderObject );
			this.bindings.delete( renderObject );
			this.nodes.delete( renderObject );

			chainMap.delete( renderObject.getChainArray() );

		};

		return renderObject;

	}
```
</details>


---