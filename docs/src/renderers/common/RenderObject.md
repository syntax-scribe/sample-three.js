[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RenderObject.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 18 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 27 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/RenderObject.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `hash` | `../../nodes/core/NodeUtils.js` |
| `hashString` | `../../nodes/core/NodeUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_id` | `number` | let/var | `0` | ✗ |
| `descriptor` | `TypedPropertyDescriptor<any> & Proper...` | let/var | `descriptors[ key ]` | ✗ |
| `nodeAttributes` | `any` | let/var | `this.getNodeBuilderState().nodeAttributes` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `attributes` | `any[]` | let/var | `[]` | ✗ |
| `vertexBuffers` | `Set<any>` | let/var | `new Set()` | ✗ |
| `attributesId` | `{}` | let/var | `{}` | ✗ |
| `attribute` | `any` | let/var | `*not shown*` | ✗ |
| `bufferAttribute` | `any` | let/var | `attribute.isInterleavedBufferAttribute ? attribute.data : attribute` | ✗ |
| `drawParams` | `{ vertexCount: number; firstVertex: n...` | let/var | `this.drawParams \|\| ( this.drawParams = { vertexCount: 0, firstVertex: 0, in...` | ✗ |
| `hasIndex` | `boolean` | let/var | `( index !== null )` | ✗ |
| `instanceCount` | `number` | let/var | `1` | ✗ |
| `rangeFactor` | `number` | let/var | `1` | ✗ |
| `firstVertex` | `number` | let/var | `drawRange.start * rangeFactor` | ✗ |
| `lastVertex` | `number` | let/var | `( drawRange.start + drawRange.count ) * rangeFactor` | ✗ |
| `position` | `any` | let/var | `geometry.attributes.position` | ✗ |
| `itemCount` | `number` | let/var | `Infinity` | ✗ |
| `count` | `number` | let/var | `lastVertex - firstVertex` | ✗ |
| `cacheKey` | `string` | let/var | `''` | ✗ |
| `attribute` | `any` | let/var | `geometry.attributes[ name ]` | ✗ |
| `targets` | `any` | let/var | `geometry.morphAttributes[ name ]` | ✗ |
| `attribute` | `any` | let/var | `targets[ i ]` | ✗ |
| `value` | `Material` | let/var | `material[ property ]` | ✗ |
| `valueKey` | `any` | let/var | `*not shown*` | ✗ |
| `type` | `"string" \| "number" \| "bigint" \| "...` | let/var | `typeof value` | ✗ |
| `attributesId` | `{ [x: string]: number; }` | let/var | `this.attributesId` | ✗ |
| `cacheKey` | `number` | let/var | `0` | ✗ |


---

## Functions

### `getKeys(obj: any): string[]`

**Parameters:**

- **`obj`** `any`

**Returns:** `string[]`

**Calls:**

- `Object.keys`
- `Object.getPrototypeOf`
- `Object.getOwnPropertyDescriptors`
- `keys.push`

<details><summary>Code</summary>

```typescript
function getKeys( obj ) {

	const keys = Object.keys( obj );

	let proto = Object.getPrototypeOf( obj );

	while ( proto ) {

		const descriptors = Object.getOwnPropertyDescriptors( proto );

		for ( const key in descriptors ) {

			if ( descriptors[ key ] !== undefined ) {

				const descriptor = descriptors[ key ];

				if ( descriptor && typeof descriptor.get === 'function' ) {

					keys.push( key );

				}

			}

		}

		proto = Object.getPrototypeOf( proto );

	}

	return keys;

}
```
</details>

### `RenderObject.updateClipping(context: ClippingContext): void`

**JSDoc:**
```typescript
/**
	 * Updates the clipping context.
	 *
	 * @param {ClippingContext} context - The clipping context to set.
	 */
```

**Parameters:**

- **`context`** `ClippingContext`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
updateClipping( context ) {

		this.clippingContext = context;

	}
```
</details>

### `RenderObject.getNodeBuilderState(): NodeBuilderState`

**JSDoc:**
```typescript
/**
	 * Returns the node builder state of this render object.
	 *
	 * @return {NodeBuilderState} The node builder state.
	 */
```

**Returns:** `NodeBuilderState`

**Calls:**

- `this._nodes.getForRender`

<details><summary>Code</summary>

```typescript
getNodeBuilderState() {

		return this._nodeBuilderState || ( this._nodeBuilderState = this._nodes.getForRender( this ) );

	}
```
</details>

### `RenderObject.getMonitor(): NodeMaterialObserver`

**JSDoc:**
```typescript
/**
	 * Returns the node material observer of this render object.
	 *
	 * @return {NodeMaterialObserver} The node material observer.
	 */
```

**Returns:** `NodeMaterialObserver`

**Calls:**

- `this.getNodeBuilderState`

<details><summary>Code</summary>

```typescript
getMonitor() {

		return this._monitor || ( this._monitor = this.getNodeBuilderState().observer );

	}
```
</details>

### `RenderObject.getBindings(): BindGroup[]`

**JSDoc:**
```typescript
/**
	 * Returns an array of bind groups of this render object.
	 *
	 * @return {Array<BindGroup>} The bindings.
	 */
```

**Returns:** `BindGroup[]`

**Calls:**

- `this.getNodeBuilderState().createBindings`

<details><summary>Code</summary>

```typescript
getBindings() {

		return this._bindings || ( this._bindings = this.getNodeBuilderState().createBindings() );

	}
```
</details>

### `RenderObject.getBindingGroup(name: string): BindGroup`

**JSDoc:**
```typescript
/**
	 * Returns a binding group by group name of this render object.
	 *
	 * @param {string} name - The name of the binding group.
	 * @return {?BindGroup} The bindings.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `BindGroup`

**Calls:**

- `this.getBindings`

<details><summary>Code</summary>

```typescript
getBindingGroup( name ) {

		for ( const bindingGroup of this.getBindings() ) {

			if ( bindingGroup.name === name ) {

				return bindingGroup;

			}

		}

	}
```
</details>

### `RenderObject.getIndex(): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Returns the index of the render object's geometry.
	 *
	 * @return {?BufferAttribute} The index. Returns `null` for non-indexed geometries.
	 */
```

**Returns:** `BufferAttribute`

**Calls:**

- `this._geometries.getIndex`

<details><summary>Code</summary>

```typescript
getIndex() {

		return this._geometries.getIndex( this );

	}
```
</details>

### `RenderObject.getIndirect(): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Returns the indirect buffer attribute.
	 *
	 * @return {?BufferAttribute} The indirect attribute. `null` if no indirect drawing is used.
	 */
```

**Returns:** `BufferAttribute`

**Calls:**

- `this._geometries.getIndirect`

<details><summary>Code</summary>

```typescript
getIndirect() {

		return this._geometries.getIndirect( this );

	}
```
</details>

### `RenderObject.getChainArray(): any[]`

**JSDoc:**
```typescript
/**
	 * Returns an array that acts as a key for identifying the render object in a chain map.
	 *
	 * @return {Array<Object>} An array with object references.
	 */
```

**Returns:** `any[]`

<details><summary>Code</summary>

```typescript
getChainArray() {

		return [ this.object, this.material, this.context, this.lightsNode ];

	}
```
</details>

### `RenderObject.setGeometry(geometry: BufferGeometry): void`

**JSDoc:**
```typescript
/**
	 * This method is used when the geometry of a 3D object has been exchanged and the
	 * respective render object now requires an update.
	 *
	 * @param {BufferGeometry} geometry - The geometry to set.
	 */
```

**Parameters:**

- **`geometry`** `BufferGeometry`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setGeometry( geometry ) {

		this.geometry = geometry;
		this.attributes = null;
		this.attributesId = null;

	}
```
</details>

### `RenderObject.getAttributes(): BufferAttribute[]`

**JSDoc:**
```typescript
/**
	 * Returns the buffer attributes of the render object. The returned array holds
	 * attribute definitions on geometry and node level.
	 *
	 * @return {Array<BufferAttribute>} An array with buffer attributes.
	 */
```

**Returns:** `BufferAttribute[]`

**Calls:**

- `this.getNodeBuilderState`
- `geometry.getAttribute`
- `attributes.push`
- `vertexBuffers.add`
- `Array.from`
- `vertexBuffers.values`

**Internal Comments:**
```
// node attribute (x3)
// geometry attribute (x3)
```

<details><summary>Code</summary>

```typescript
getAttributes() {

		if ( this.attributes !== null ) return this.attributes;

		const nodeAttributes = this.getNodeBuilderState().nodeAttributes;
		const geometry = this.geometry;

		const attributes = [];
		const vertexBuffers = new Set();

		const attributesId = {};

		for ( const nodeAttribute of nodeAttributes ) {

			let attribute;

			if ( nodeAttribute.node && nodeAttribute.node.attribute ) {

				// node attribute
				attribute = nodeAttribute.node.attribute;

			} else {

				// geometry attribute
				attribute = geometry.getAttribute( nodeAttribute.name );

				attributesId[ nodeAttribute.name ] = attribute.version;

			}

			if ( attribute === undefined ) continue;

			attributes.push( attribute );

			const bufferAttribute = attribute.isInterleavedBufferAttribute ? attribute.data : attribute;
			vertexBuffers.add( bufferAttribute );

		}

		this.attributes = attributes;
		this.attributesId = attributesId;
		this.vertexBuffers = Array.from( vertexBuffers.values() );

		return attributes;

	}
```
</details>

### `RenderObject.getVertexBuffers(): any[]`

**JSDoc:**
```typescript
/**
	 * Returns the vertex buffers of the render object.
	 *
	 * @return {Array<BufferAttribute|InterleavedBuffer>} An array with buffer attribute or interleaved buffers.
	 */
```

**Returns:** `any[]`

**Calls:**

- `this.getAttributes`

<details><summary>Code</summary>

```typescript
getVertexBuffers() {

		if ( this.vertexBuffers === null ) this.getAttributes();

		return this.vertexBuffers;

	}
```
</details>

### `RenderObject.getDrawParameters(): { vertexCount: number; firstVertex: number; instanceCount: number; firstInstance: number; }`

**JSDoc:**
```typescript
/**
	 * Returns the draw parameters for the render object.
	 *
	 * @return {?{vertexCount: number, firstVertex: number, instanceCount: number, firstInstance: number}} The draw parameters.
	 */
```

**Returns:** `{ vertexCount: number; firstVertex: number; instanceCount: number; firstInstance: number; }`

**Calls:**

- `this.getIndex`
- `Math.max`
- `Math.min`

<details><summary>Code</summary>

```typescript
getDrawParameters() {

		const { object, material, geometry, group, drawRange } = this;

		const drawParams = this.drawParams || ( this.drawParams = {
			vertexCount: 0,
			firstVertex: 0,
			instanceCount: 0,
			firstInstance: 0
		} );

		const index = this.getIndex();
		const hasIndex = ( index !== null );

		let instanceCount = 1;

		if ( geometry.isInstancedBufferGeometry === true ) {

			instanceCount = geometry.instanceCount;

		} else if ( object.count !== undefined ) {

			instanceCount = Math.max( 0, object.count );

		}

		if ( instanceCount === 0 ) return null;

		drawParams.instanceCount = instanceCount;

		if ( object.isBatchedMesh === true ) return drawParams;

		let rangeFactor = 1;

		if ( material.wireframe === true && ! object.isPoints && ! object.isLineSegments && ! object.isLine && ! object.isLineLoop ) {

			rangeFactor = 2;

		}

		let firstVertex = drawRange.start * rangeFactor;
		let lastVertex = ( drawRange.start + drawRange.count ) * rangeFactor;

		if ( group !== null ) {

			firstVertex = Math.max( firstVertex, group.start * rangeFactor );
			lastVertex = Math.min( lastVertex, ( group.start + group.count ) * rangeFactor );

		}

		const position = geometry.attributes.position;
		let itemCount = Infinity;

		if ( hasIndex ) {

			itemCount = index.count;

		} else if ( position !== undefined && position !== null ) {

			itemCount = position.count;

		}

		firstVertex = Math.max( firstVertex, 0 );
		lastVertex = Math.min( lastVertex, itemCount );

		const count = lastVertex - firstVertex;

		if ( count < 0 || count === Infinity ) return null;

		drawParams.vertexCount = count;
		drawParams.firstVertex = firstVertex;

		return drawParams;

	}
```
</details>

### `RenderObject.getGeometryCacheKey(): string`

**JSDoc:**
```typescript
/**
	 * Returns the render object's geometry cache key.
	 *
	 * The geometry cache key is part of the material cache key.
	 *
	 * @return {string} The geometry cache key.
	 */
```

**Returns:** `string`

**Calls:**

- `Object.keys( geometry.attributes ).sort`
- `Object.keys( geometry.morphAttributes ).sort`

**Internal Comments:**
```
// structural equality isn't sufficient for morph targets since the
// data are maintained in textures. only if the targets are all equal
// the texture and thus the instance of `MorphNode` can be shared.
```

<details><summary>Code</summary>

```typescript
getGeometryCacheKey() {

		const { geometry } = this;

		let cacheKey = '';

		for ( const name of Object.keys( geometry.attributes ).sort() ) {

			const attribute = geometry.attributes[ name ];

			cacheKey += name + ',';

			if ( attribute.data ) cacheKey += attribute.data.stride + ',';
			if ( attribute.offset ) cacheKey += attribute.offset + ',';
			if ( attribute.itemSize ) cacheKey += attribute.itemSize + ',';
			if ( attribute.normalized ) cacheKey += 'n,';

		}

		// structural equality isn't sufficient for morph targets since the
		// data are maintained in textures. only if the targets are all equal
		// the texture and thus the instance of `MorphNode` can be shared.

		for ( const name of Object.keys( geometry.morphAttributes ).sort() ) {

			const targets = geometry.morphAttributes[ name ];

			cacheKey += 'morph-' + name + ',';

			for ( let i = 0, l = targets.length; i < l; i ++ ) {

				const attribute = targets[ i ];

				cacheKey += attribute.id + ',';

			}

		}

		if ( geometry.index ) {

			cacheKey += 'index,';

		}

		return cacheKey;

	}
```
</details>

### `RenderObject.getMaterialCacheKey(): number`

**JSDoc:**
```typescript
/**
	 * Returns the render object's material cache key.
	 *
	 * The material cache key is part of the render object cache key.
	 *
	 * @return {number} The material cache key.
	 */
```

**Returns:** `number`

**Calls:**

- `material.customProgramCacheKey`
- `getKeys`
- `/^(is[A-Z]|_)|^(visible|version|uuid|name|opacity|userData)$/.test`
- `String`
- `this.getGeometryCacheKey`
- `hashString (from ../../nodes/core/NodeUtils.js)`

**Internal Comments:**
```
// some material values require a formatting (x2)
// TODO: https://github.com/mrdoob/three.js/pull/29066#issuecomment-2269400850 (x3)
```

<details><summary>Code</summary>

```typescript
getMaterialCacheKey() {

		const { object, material } = this;

		let cacheKey = material.customProgramCacheKey();

		for ( const property of getKeys( material ) ) {

			if ( /^(is[A-Z]|_)|^(visible|version|uuid|name|opacity|userData)$/.test( property ) ) continue;

			const value = material[ property ];

			let valueKey;

			if ( value !== null ) {

				// some material values require a formatting

				const type = typeof value;

				if ( type === 'number' ) {

					valueKey = value !== 0 ? '1' : '0'; // Convert to on/off, important for clearcoat, transmission, etc

				} else if ( type === 'object' ) {

					valueKey = '{';

					if ( value.isTexture ) {

						valueKey += value.mapping;

					}

					valueKey += '}';

				} else {

					valueKey = String( value );

				}

			} else {

				valueKey = String( value );

			}

			cacheKey += /*property + ':' +*/ valueKey + ',';

		}

		cacheKey += this.clippingContextCacheKey + ',';

		if ( object.geometry ) {

			cacheKey += this.getGeometryCacheKey();

		}

		if ( object.skeleton ) {

			cacheKey += object.skeleton.bones.length + ',';

		}

		if ( object.isBatchedMesh ) {

			cacheKey += object._matricesTexture.uuid + ',';

			if ( object._colorsTexture !== null ) {

				cacheKey += object._colorsTexture.uuid + ',';

			}

		}

		if ( object.count > 1 ) {

			// TODO: https://github.com/mrdoob/three.js/pull/29066#issuecomment-2269400850

			cacheKey += object.uuid + ',';

		}

		cacheKey += object.receiveShadow + ',';

		return hashString( cacheKey );

	}
```
</details>

### `RenderObject.getDynamicCacheKey(): number`

**JSDoc:**
```typescript
/**
	 * Returns the dynamic cache key which represents a key that is computed per draw command.
	 *
	 * @return {number} The cache key.
	 */
```

**Returns:** `number`

**Calls:**

- `this._nodes.getCacheKey`
- `hash (from ../../nodes/core/NodeUtils.js)`

**Internal Comments:**
```
// `Nodes.getCacheKey()` returns an environment cache key which is not relevant when
// the renderer is inside a shadow pass.
```

<details><summary>Code</summary>

```typescript
getDynamicCacheKey() {

		let cacheKey = 0;

		// `Nodes.getCacheKey()` returns an environment cache key which is not relevant when
		// the renderer is inside a shadow pass.

		if ( this.material.isShadowPassMaterial !== true ) {

			cacheKey = this._nodes.getCacheKey( this.scene, this.lightsNode );

		}

		if ( this.camera.isArrayCamera ) {

			cacheKey = hash( cacheKey, this.camera.cameras.length );

		}

		if ( this.object.receiveShadow ) {

			cacheKey = hash( cacheKey, 1 );

		}

		return cacheKey;

	}
```
</details>

### `RenderObject.getCacheKey(): number`

**JSDoc:**
```typescript
/**
	 * Returns the render object's cache key.
	 *
	 * @return {number} The cache key.
	 */
```

**Returns:** `number`

**Calls:**

- `this.getMaterialCacheKey`
- `this.getDynamicCacheKey`

<details><summary>Code</summary>

```typescript
getCacheKey() {

		return this.getMaterialCacheKey() + this.getDynamicCacheKey();

	}
```
</details>

### `RenderObject.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources.
	 */
```

**Returns:** `void`

**Calls:**

- `this.material.removeEventListener`
- `this.geometry.removeEventListener`
- `this.onDispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.material.removeEventListener( 'dispose', this.onMaterialDispose );
		this.geometry.removeEventListener( 'dispose', this.onGeometryDispose );

		this.onDispose();

	}
```
</details>


---

## Classes

### `RenderObject`

<details><summary>Class Code</summary>

```ts
class RenderObject {

	/**
	 * Constructs a new render object.
	 *
	 * @param {Nodes} nodes - Renderer component for managing nodes related logic.
	 * @param {Geometries} geometries - Renderer component for managing geometries.
	 * @param {Renderer} renderer - The renderer.
	 * @param {Object3D} object - The 3D object.
	 * @param {Material} material - The 3D object's material.
	 * @param {Scene} scene - The scene the 3D object belongs to.
	 * @param {Camera} camera - The camera the object should be rendered with.
	 * @param {LightsNode} lightsNode - The lights node.
	 * @param {RenderContext} renderContext - The render context.
	 * @param {ClippingContext} clippingContext - The clipping context.
	 */
	constructor( nodes, geometries, renderer, object, material, scene, camera, lightsNode, renderContext, clippingContext ) {

		this.id = _id ++;

		/**
		 * Renderer component for managing nodes related logic.
		 *
		 * @type {Nodes}
		 * @private
		 */
		this._nodes = nodes;

		/**
		 * Renderer component for managing geometries.
		 *
		 * @type {Geometries}
		 * @private
		 */
		this._geometries = geometries;

		/**
		 * The renderer.
		 *
		 * @type {Renderer}
		 */
		this.renderer = renderer;

		/**
		 * The 3D object.
		 *
		 * @type {Object3D}
		 */
		this.object = object;

		/**
		 * The 3D object's material.
		 *
		 * @type {Material}
		 */
		this.material = material;

		/**
		 * The scene the 3D object belongs to.
		 *
		 * @type {Scene}
		 */
		this.scene = scene;

		/**
		 * The camera the 3D object should be rendered with.
		 *
		 * @type {Camera}
		 */
		this.camera = camera;

		/**
		 * The lights node.
		 *
		 * @type {LightsNode}
		 */
		this.lightsNode = lightsNode;

		/**
		 * The render context.
		 *
		 * @type {RenderContext}
		 */
		this.context = renderContext;

		/**
		 * The 3D object's geometry.
		 *
		 * @type {BufferGeometry}
		 */
		this.geometry = object.geometry;

		/**
		 * The render object's version.
		 *
		 * @type {number}
		 */
		this.version = material.version;

		/**
		 * The draw range of the geometry.
		 *
		 * @type {?Object}
		 * @default null
		 */
		this.drawRange = null;

		/**
		 * An array holding the buffer attributes
		 * of the render object. This entails attribute
		 * definitions on geometry and node level.
		 *
		 * @type {?Array<BufferAttribute>}
		 * @default null
		 */
		this.attributes = null;

		/**
		 * An object holding the version of the
		 * attributes. The keys are the attribute names
		 * and the values are the attribute versions.
		 *
		 * @type {?Object<string, number>}
		 * @default null
		 */
		this.attributesId = null;

		/**
		 * A reference to a render pipeline the render
		 * object is processed with.
		 *
		 * @type {RenderPipeline}
		 * @default null
		 */
		this.pipeline = null;

		/**
		 * Only relevant for objects using
		 * multiple materials. This represents a group entry
		 * from the respective `BufferGeometry`.
		 *
		 * @type {?{start: number, count: number}}
		 * @default null
		 */
		this.group = null;

		/**
		 * An array holding the vertex buffers which can
		 * be buffer attributes but also interleaved buffers.
		 *
		 * @type {?Array<BufferAttribute|InterleavedBuffer>}
		 * @default null
		 */
		this.vertexBuffers = null;

		/**
		 * The parameters for the draw command.
		 *
		 * @type {?Object}
		 * @default null
		 */
		this.drawParams = null;

		/**
		 * If this render object is used inside a render bundle,
		 * this property points to the respective bundle group.
		 *
		 * @type {?BundleGroup}
		 * @default null
		 */
		this.bundle = null;

		/**
		 * The clipping context.
		 *
		 * @type {ClippingContext}
		 */
		this.clippingContext = clippingContext;

		/**
		 * The clipping context's cache key.
		 *
		 * @type {string}
		 */
		this.clippingContextCacheKey = clippingContext !== null ? clippingContext.cacheKey : '';

		/**
		 * The initial node cache key.
		 *
		 * @type {number}
		 */
		this.initialNodesCacheKey = this.getDynamicCacheKey();

		/**
		 * The initial cache key.
		 *
		 * @type {number}
		 */
		this.initialCacheKey = this.getCacheKey();

		/**
		 * The node builder state.
		 *
		 * @type {?NodeBuilderState}
		 * @private
		 * @default null
		 */
		this._nodeBuilderState = null;

		/**
		 * An array of bindings.
		 *
		 * @type {?Array<BindGroup>}
		 * @private
		 * @default null
		 */
		this._bindings = null;

		/**
		 * Reference to the node material observer.
		 *
		 * @type {?NodeMaterialObserver}
		 * @private
		 * @default null
		 */
		this._monitor = null;

		/**
		 * An event listener which is defined by `RenderObjects`. It performs
		 * clean up tasks when `dispose()` on this render object.
		 *
		 * @method
		 */
		this.onDispose = null;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isRenderObject = true;

		/**
		 * An event listener which is executed when `dispose()` is called on
		 * the material of this render object.
		 *
		 * @method
		 */
		this.onMaterialDispose = () => {

			this.dispose();

		};

		/**
		 * An event listener which is executed when `dispose()` is called on
		 * the geometry of this render object.
		 *
		 * @method
		 */
		this.onGeometryDispose = () => {

			// clear geometry cache attributes

			this.attributes = null;
			this.attributesId = null;

		};

		this.material.addEventListener( 'dispose', this.onMaterialDispose );
		this.geometry.addEventListener( 'dispose', this.onGeometryDispose );

	}

	/**
	 * Updates the clipping context.
	 *
	 * @param {ClippingContext} context - The clipping context to set.
	 */
	updateClipping( context ) {

		this.clippingContext = context;

	}

	/**
	 * Whether the clipping requires an update or not.
	 *
	 * @type {boolean}
	 * @readonly
	 */
	get clippingNeedsUpdate() {

		if ( this.clippingContext === null || this.clippingContext.cacheKey === this.clippingContextCacheKey ) return false;

		this.clippingContextCacheKey = this.clippingContext.cacheKey;

		return true;

	}

	/**
	 * The number of clipping planes defined in context of hardware clipping.
	 *
	 * @type {number}
	 * @readonly
	 */
	get hardwareClippingPlanes() {

		return this.material.hardwareClipping === true ? this.clippingContext.unionClippingCount : 0;

	}

	/**
	 * Returns the node builder state of this render object.
	 *
	 * @return {NodeBuilderState} The node builder state.
	 */
	getNodeBuilderState() {

		return this._nodeBuilderState || ( this._nodeBuilderState = this._nodes.getForRender( this ) );

	}

	/**
	 * Returns the node material observer of this render object.
	 *
	 * @return {NodeMaterialObserver} The node material observer.
	 */
	getMonitor() {

		return this._monitor || ( this._monitor = this.getNodeBuilderState().observer );

	}

	/**
	 * Returns an array of bind groups of this render object.
	 *
	 * @return {Array<BindGroup>} The bindings.
	 */
	getBindings() {

		return this._bindings || ( this._bindings = this.getNodeBuilderState().createBindings() );

	}

	/**
	 * Returns a binding group by group name of this render object.
	 *
	 * @param {string} name - The name of the binding group.
	 * @return {?BindGroup} The bindings.
	 */
	getBindingGroup( name ) {

		for ( const bindingGroup of this.getBindings() ) {

			if ( bindingGroup.name === name ) {

				return bindingGroup;

			}

		}

	}

	/**
	 * Returns the index of the render object's geometry.
	 *
	 * @return {?BufferAttribute} The index. Returns `null` for non-indexed geometries.
	 */
	getIndex() {

		return this._geometries.getIndex( this );

	}

	/**
	 * Returns the indirect buffer attribute.
	 *
	 * @return {?BufferAttribute} The indirect attribute. `null` if no indirect drawing is used.
	 */
	getIndirect() {

		return this._geometries.getIndirect( this );

	}

	/**
	 * Returns an array that acts as a key for identifying the render object in a chain map.
	 *
	 * @return {Array<Object>} An array with object references.
	 */
	getChainArray() {

		return [ this.object, this.material, this.context, this.lightsNode ];

	}

	/**
	 * This method is used when the geometry of a 3D object has been exchanged and the
	 * respective render object now requires an update.
	 *
	 * @param {BufferGeometry} geometry - The geometry to set.
	 */
	setGeometry( geometry ) {

		this.geometry = geometry;
		this.attributes = null;
		this.attributesId = null;

	}

	/**
	 * Returns the buffer attributes of the render object. The returned array holds
	 * attribute definitions on geometry and node level.
	 *
	 * @return {Array<BufferAttribute>} An array with buffer attributes.
	 */
	getAttributes() {

		if ( this.attributes !== null ) return this.attributes;

		const nodeAttributes = this.getNodeBuilderState().nodeAttributes;
		const geometry = this.geometry;

		const attributes = [];
		const vertexBuffers = new Set();

		const attributesId = {};

		for ( const nodeAttribute of nodeAttributes ) {

			let attribute;

			if ( nodeAttribute.node && nodeAttribute.node.attribute ) {

				// node attribute
				attribute = nodeAttribute.node.attribute;

			} else {

				// geometry attribute
				attribute = geometry.getAttribute( nodeAttribute.name );

				attributesId[ nodeAttribute.name ] = attribute.version;

			}

			if ( attribute === undefined ) continue;

			attributes.push( attribute );

			const bufferAttribute = attribute.isInterleavedBufferAttribute ? attribute.data : attribute;
			vertexBuffers.add( bufferAttribute );

		}

		this.attributes = attributes;
		this.attributesId = attributesId;
		this.vertexBuffers = Array.from( vertexBuffers.values() );

		return attributes;

	}

	/**
	 * Returns the vertex buffers of the render object.
	 *
	 * @return {Array<BufferAttribute|InterleavedBuffer>} An array with buffer attribute or interleaved buffers.
	 */
	getVertexBuffers() {

		if ( this.vertexBuffers === null ) this.getAttributes();

		return this.vertexBuffers;

	}

	/**
	 * Returns the draw parameters for the render object.
	 *
	 * @return {?{vertexCount: number, firstVertex: number, instanceCount: number, firstInstance: number}} The draw parameters.
	 */
	getDrawParameters() {

		const { object, material, geometry, group, drawRange } = this;

		const drawParams = this.drawParams || ( this.drawParams = {
			vertexCount: 0,
			firstVertex: 0,
			instanceCount: 0,
			firstInstance: 0
		} );

		const index = this.getIndex();
		const hasIndex = ( index !== null );

		let instanceCount = 1;

		if ( geometry.isInstancedBufferGeometry === true ) {

			instanceCount = geometry.instanceCount;

		} else if ( object.count !== undefined ) {

			instanceCount = Math.max( 0, object.count );

		}

		if ( instanceCount === 0 ) return null;

		drawParams.instanceCount = instanceCount;

		if ( object.isBatchedMesh === true ) return drawParams;

		let rangeFactor = 1;

		if ( material.wireframe === true && ! object.isPoints && ! object.isLineSegments && ! object.isLine && ! object.isLineLoop ) {

			rangeFactor = 2;

		}

		let firstVertex = drawRange.start * rangeFactor;
		let lastVertex = ( drawRange.start + drawRange.count ) * rangeFactor;

		if ( group !== null ) {

			firstVertex = Math.max( firstVertex, group.start * rangeFactor );
			lastVertex = Math.min( lastVertex, ( group.start + group.count ) * rangeFactor );

		}

		const position = geometry.attributes.position;
		let itemCount = Infinity;

		if ( hasIndex ) {

			itemCount = index.count;

		} else if ( position !== undefined && position !== null ) {

			itemCount = position.count;

		}

		firstVertex = Math.max( firstVertex, 0 );
		lastVertex = Math.min( lastVertex, itemCount );

		const count = lastVertex - firstVertex;

		if ( count < 0 || count === Infinity ) return null;

		drawParams.vertexCount = count;
		drawParams.firstVertex = firstVertex;

		return drawParams;

	}

	/**
	 * Returns the render object's geometry cache key.
	 *
	 * The geometry cache key is part of the material cache key.
	 *
	 * @return {string} The geometry cache key.
	 */
	getGeometryCacheKey() {

		const { geometry } = this;

		let cacheKey = '';

		for ( const name of Object.keys( geometry.attributes ).sort() ) {

			const attribute = geometry.attributes[ name ];

			cacheKey += name + ',';

			if ( attribute.data ) cacheKey += attribute.data.stride + ',';
			if ( attribute.offset ) cacheKey += attribute.offset + ',';
			if ( attribute.itemSize ) cacheKey += attribute.itemSize + ',';
			if ( attribute.normalized ) cacheKey += 'n,';

		}

		// structural equality isn't sufficient for morph targets since the
		// data are maintained in textures. only if the targets are all equal
		// the texture and thus the instance of `MorphNode` can be shared.

		for ( const name of Object.keys( geometry.morphAttributes ).sort() ) {

			const targets = geometry.morphAttributes[ name ];

			cacheKey += 'morph-' + name + ',';

			for ( let i = 0, l = targets.length; i < l; i ++ ) {

				const attribute = targets[ i ];

				cacheKey += attribute.id + ',';

			}

		}

		if ( geometry.index ) {

			cacheKey += 'index,';

		}

		return cacheKey;

	}

	/**
	 * Returns the render object's material cache key.
	 *
	 * The material cache key is part of the render object cache key.
	 *
	 * @return {number} The material cache key.
	 */
	getMaterialCacheKey() {

		const { object, material } = this;

		let cacheKey = material.customProgramCacheKey();

		for ( const property of getKeys( material ) ) {

			if ( /^(is[A-Z]|_)|^(visible|version|uuid|name|opacity|userData)$/.test( property ) ) continue;

			const value = material[ property ];

			let valueKey;

			if ( value !== null ) {

				// some material values require a formatting

				const type = typeof value;

				if ( type === 'number' ) {

					valueKey = value !== 0 ? '1' : '0'; // Convert to on/off, important for clearcoat, transmission, etc

				} else if ( type === 'object' ) {

					valueKey = '{';

					if ( value.isTexture ) {

						valueKey += value.mapping;

					}

					valueKey += '}';

				} else {

					valueKey = String( value );

				}

			} else {

				valueKey = String( value );

			}

			cacheKey += /*property + ':' +*/ valueKey + ',';

		}

		cacheKey += this.clippingContextCacheKey + ',';

		if ( object.geometry ) {

			cacheKey += this.getGeometryCacheKey();

		}

		if ( object.skeleton ) {

			cacheKey += object.skeleton.bones.length + ',';

		}

		if ( object.isBatchedMesh ) {

			cacheKey += object._matricesTexture.uuid + ',';

			if ( object._colorsTexture !== null ) {

				cacheKey += object._colorsTexture.uuid + ',';

			}

		}

		if ( object.count > 1 ) {

			// TODO: https://github.com/mrdoob/three.js/pull/29066#issuecomment-2269400850

			cacheKey += object.uuid + ',';

		}

		cacheKey += object.receiveShadow + ',';

		return hashString( cacheKey );

	}

	/**
	 * Whether the geometry requires an update or not.
	 *
	 * @type {boolean}
	 * @readonly
	 */
	get needsGeometryUpdate() {

		if ( this.geometry.id !== this.object.geometry.id ) return true;

		if ( this.attributes !== null ) {

			const attributesId = this.attributesId;

			for ( const name in attributesId ) {

				const attribute = this.geometry.getAttribute( name );

				if ( attribute === undefined || attributesId[ name ] !== attribute.id ) {

					return true;

				}

			}

		}

		return false;

	}

	/**
	 * Whether the render object requires an update or not.
	 *
	 * Note: There are two distinct places where render objects are checked for an update.
	 *
	 * 1. In `RenderObjects.get()` which is executed when the render object is request. This
	 * method checks the `needsUpdate` flag and recreates the render object if necessary.
	 * 2. In `Renderer._renderObjectDirect()` right after getting the render object via
	 * `RenderObjects.get()`. The render object's NodeMaterialObserver is then used to detect
	 * a need for a refresh due to material, geometry or object related value changes.
	 *
	 * TODO: Investigate if it's possible to merge both steps so there is only a single place
	 * that performs the 'needsUpdate' check.
	 *
	 * @type {boolean}
	 * @readonly
	 */
	get needsUpdate() {

		return /*this.object.static !== true &&*/ ( this.initialNodesCacheKey !== this.getDynamicCacheKey() || this.clippingNeedsUpdate );

	}

	/**
	 * Returns the dynamic cache key which represents a key that is computed per draw command.
	 *
	 * @return {number} The cache key.
	 */
	getDynamicCacheKey() {

		let cacheKey = 0;

		// `Nodes.getCacheKey()` returns an environment cache key which is not relevant when
		// the renderer is inside a shadow pass.

		if ( this.material.isShadowPassMaterial !== true ) {

			cacheKey = this._nodes.getCacheKey( this.scene, this.lightsNode );

		}

		if ( this.camera.isArrayCamera ) {

			cacheKey = hash( cacheKey, this.camera.cameras.length );

		}

		if ( this.object.receiveShadow ) {

			cacheKey = hash( cacheKey, 1 );

		}

		return cacheKey;

	}

	/**
	 * Returns the render object's cache key.
	 *
	 * @return {number} The cache key.
	 */
	getCacheKey() {

		return this.getMaterialCacheKey() + this.getDynamicCacheKey();

	}

	/**
	 * Frees internal resources.
	 */
	dispose() {

		this.material.removeEventListener( 'dispose', this.onMaterialDispose );
		this.geometry.removeEventListener( 'dispose', this.onGeometryDispose );

		this.onDispose();

	}

}
```
</details>

#### Methods

##### `updateClipping(context: ClippingContext): void`

<details><summary>Code</summary>

```ts
updateClipping( context ) {

		this.clippingContext = context;

	}
```
</details>

##### `getNodeBuilderState(): NodeBuilderState`

<details><summary>Code</summary>

```ts
getNodeBuilderState() {

		return this._nodeBuilderState || ( this._nodeBuilderState = this._nodes.getForRender( this ) );

	}
```
</details>

##### `getMonitor(): NodeMaterialObserver`

<details><summary>Code</summary>

```ts
getMonitor() {

		return this._monitor || ( this._monitor = this.getNodeBuilderState().observer );

	}
```
</details>

##### `getBindings(): BindGroup[]`

<details><summary>Code</summary>

```ts
getBindings() {

		return this._bindings || ( this._bindings = this.getNodeBuilderState().createBindings() );

	}
```
</details>

##### `getBindingGroup(name: string): BindGroup`

<details><summary>Code</summary>

```ts
getBindingGroup( name ) {

		for ( const bindingGroup of this.getBindings() ) {

			if ( bindingGroup.name === name ) {

				return bindingGroup;

			}

		}

	}
```
</details>

##### `getIndex(): BufferAttribute`

<details><summary>Code</summary>

```ts
getIndex() {

		return this._geometries.getIndex( this );

	}
```
</details>

##### `getIndirect(): BufferAttribute`

<details><summary>Code</summary>

```ts
getIndirect() {

		return this._geometries.getIndirect( this );

	}
```
</details>

##### `getChainArray(): any[]`

<details><summary>Code</summary>

```ts
getChainArray() {

		return [ this.object, this.material, this.context, this.lightsNode ];

	}
```
</details>

##### `setGeometry(geometry: BufferGeometry): void`

<details><summary>Code</summary>

```ts
setGeometry( geometry ) {

		this.geometry = geometry;
		this.attributes = null;
		this.attributesId = null;

	}
```
</details>

##### `getAttributes(): BufferAttribute[]`

<details><summary>Code</summary>

```ts
getAttributes() {

		if ( this.attributes !== null ) return this.attributes;

		const nodeAttributes = this.getNodeBuilderState().nodeAttributes;
		const geometry = this.geometry;

		const attributes = [];
		const vertexBuffers = new Set();

		const attributesId = {};

		for ( const nodeAttribute of nodeAttributes ) {

			let attribute;

			if ( nodeAttribute.node && nodeAttribute.node.attribute ) {

				// node attribute
				attribute = nodeAttribute.node.attribute;

			} else {

				// geometry attribute
				attribute = geometry.getAttribute( nodeAttribute.name );

				attributesId[ nodeAttribute.name ] = attribute.version;

			}

			if ( attribute === undefined ) continue;

			attributes.push( attribute );

			const bufferAttribute = attribute.isInterleavedBufferAttribute ? attribute.data : attribute;
			vertexBuffers.add( bufferAttribute );

		}

		this.attributes = attributes;
		this.attributesId = attributesId;
		this.vertexBuffers = Array.from( vertexBuffers.values() );

		return attributes;

	}
```
</details>

##### `getVertexBuffers(): any[]`

<details><summary>Code</summary>

```ts
getVertexBuffers() {

		if ( this.vertexBuffers === null ) this.getAttributes();

		return this.vertexBuffers;

	}
```
</details>

##### `getDrawParameters(): { vertexCount: number; firstVertex: number; instanceCount: number; firstInstance: number; }`

<details><summary>Code</summary>

```ts
getDrawParameters() {

		const { object, material, geometry, group, drawRange } = this;

		const drawParams = this.drawParams || ( this.drawParams = {
			vertexCount: 0,
			firstVertex: 0,
			instanceCount: 0,
			firstInstance: 0
		} );

		const index = this.getIndex();
		const hasIndex = ( index !== null );

		let instanceCount = 1;

		if ( geometry.isInstancedBufferGeometry === true ) {

			instanceCount = geometry.instanceCount;

		} else if ( object.count !== undefined ) {

			instanceCount = Math.max( 0, object.count );

		}

		if ( instanceCount === 0 ) return null;

		drawParams.instanceCount = instanceCount;

		if ( object.isBatchedMesh === true ) return drawParams;

		let rangeFactor = 1;

		if ( material.wireframe === true && ! object.isPoints && ! object.isLineSegments && ! object.isLine && ! object.isLineLoop ) {

			rangeFactor = 2;

		}

		let firstVertex = drawRange.start * rangeFactor;
		let lastVertex = ( drawRange.start + drawRange.count ) * rangeFactor;

		if ( group !== null ) {

			firstVertex = Math.max( firstVertex, group.start * rangeFactor );
			lastVertex = Math.min( lastVertex, ( group.start + group.count ) * rangeFactor );

		}

		const position = geometry.attributes.position;
		let itemCount = Infinity;

		if ( hasIndex ) {

			itemCount = index.count;

		} else if ( position !== undefined && position !== null ) {

			itemCount = position.count;

		}

		firstVertex = Math.max( firstVertex, 0 );
		lastVertex = Math.min( lastVertex, itemCount );

		const count = lastVertex - firstVertex;

		if ( count < 0 || count === Infinity ) return null;

		drawParams.vertexCount = count;
		drawParams.firstVertex = firstVertex;

		return drawParams;

	}
```
</details>

##### `getGeometryCacheKey(): string`

<details><summary>Code</summary>

```ts
getGeometryCacheKey() {

		const { geometry } = this;

		let cacheKey = '';

		for ( const name of Object.keys( geometry.attributes ).sort() ) {

			const attribute = geometry.attributes[ name ];

			cacheKey += name + ',';

			if ( attribute.data ) cacheKey += attribute.data.stride + ',';
			if ( attribute.offset ) cacheKey += attribute.offset + ',';
			if ( attribute.itemSize ) cacheKey += attribute.itemSize + ',';
			if ( attribute.normalized ) cacheKey += 'n,';

		}

		// structural equality isn't sufficient for morph targets since the
		// data are maintained in textures. only if the targets are all equal
		// the texture and thus the instance of `MorphNode` can be shared.

		for ( const name of Object.keys( geometry.morphAttributes ).sort() ) {

			const targets = geometry.morphAttributes[ name ];

			cacheKey += 'morph-' + name + ',';

			for ( let i = 0, l = targets.length; i < l; i ++ ) {

				const attribute = targets[ i ];

				cacheKey += attribute.id + ',';

			}

		}

		if ( geometry.index ) {

			cacheKey += 'index,';

		}

		return cacheKey;

	}
```
</details>

##### `getMaterialCacheKey(): number`

<details><summary>Code</summary>

```ts
getMaterialCacheKey() {

		const { object, material } = this;

		let cacheKey = material.customProgramCacheKey();

		for ( const property of getKeys( material ) ) {

			if ( /^(is[A-Z]|_)|^(visible|version|uuid|name|opacity|userData)$/.test( property ) ) continue;

			const value = material[ property ];

			let valueKey;

			if ( value !== null ) {

				// some material values require a formatting

				const type = typeof value;

				if ( type === 'number' ) {

					valueKey = value !== 0 ? '1' : '0'; // Convert to on/off, important for clearcoat, transmission, etc

				} else if ( type === 'object' ) {

					valueKey = '{';

					if ( value.isTexture ) {

						valueKey += value.mapping;

					}

					valueKey += '}';

				} else {

					valueKey = String( value );

				}

			} else {

				valueKey = String( value );

			}

			cacheKey += /*property + ':' +*/ valueKey + ',';

		}

		cacheKey += this.clippingContextCacheKey + ',';

		if ( object.geometry ) {

			cacheKey += this.getGeometryCacheKey();

		}

		if ( object.skeleton ) {

			cacheKey += object.skeleton.bones.length + ',';

		}

		if ( object.isBatchedMesh ) {

			cacheKey += object._matricesTexture.uuid + ',';

			if ( object._colorsTexture !== null ) {

				cacheKey += object._colorsTexture.uuid + ',';

			}

		}

		if ( object.count > 1 ) {

			// TODO: https://github.com/mrdoob/three.js/pull/29066#issuecomment-2269400850

			cacheKey += object.uuid + ',';

		}

		cacheKey += object.receiveShadow + ',';

		return hashString( cacheKey );

	}
```
</details>

##### `getDynamicCacheKey(): number`

<details><summary>Code</summary>

```ts
getDynamicCacheKey() {

		let cacheKey = 0;

		// `Nodes.getCacheKey()` returns an environment cache key which is not relevant when
		// the renderer is inside a shadow pass.

		if ( this.material.isShadowPassMaterial !== true ) {

			cacheKey = this._nodes.getCacheKey( this.scene, this.lightsNode );

		}

		if ( this.camera.isArrayCamera ) {

			cacheKey = hash( cacheKey, this.camera.cameras.length );

		}

		if ( this.object.receiveShadow ) {

			cacheKey = hash( cacheKey, 1 );

		}

		return cacheKey;

	}
```
</details>

##### `getCacheKey(): number`

<details><summary>Code</summary>

```ts
getCacheKey() {

		return this.getMaterialCacheKey() + this.getDynamicCacheKey();

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.material.removeEventListener( 'dispose', this.onMaterialDispose );
		this.geometry.removeEventListener( 'dispose', this.onGeometryDispose );

		this.onDispose();

	}
```
</details>


---