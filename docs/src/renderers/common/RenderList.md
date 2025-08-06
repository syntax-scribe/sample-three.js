[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RenderList.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 11 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/RenderList.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DoubleSide` | `../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `hasTransmission` | `any` | let/var | `material.transmission > 0 \|\| material.transmissionNode` | ✗ |
| `renderItem` | `any` | let/var | `this.renderItems[ this.renderItemsIndex ]` | ✗ |
| `renderItem` | `any` | let/var | `this.renderItems[ i ]` | ✗ |


---

## Functions

### `painterSortStable(a: any, b: any): number`

**JSDoc:**
```typescript
/**
 * Default sorting function for opaque render items.
 *
 * @private
 * @function
 * @param {Object} a - The first render item.
 * @param {Object} b - The second render item.
 * @return {number} A numeric value which defines the sort order.
 */
```

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function painterSortStable( a, b ) {

	if ( a.groupOrder !== b.groupOrder ) {

		return a.groupOrder - b.groupOrder;

	} else if ( a.renderOrder !== b.renderOrder ) {

		return a.renderOrder - b.renderOrder;

	} else if ( a.z !== b.z ) {

		return a.z - b.z;

	} else {

		return a.id - b.id;

	}

}
```
</details>

### `reversePainterSortStable(a: any, b: any): number`

**JSDoc:**
```typescript
/**
 * Default sorting function for transparent render items.
 *
 * @private
 * @function
 * @param {Object} a - The first render item.
 * @param {Object} b - The second render item.
 * @return {number} A numeric value which defines the sort order.
 */
```

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function reversePainterSortStable( a, b ) {

	if ( a.groupOrder !== b.groupOrder ) {

		return a.groupOrder - b.groupOrder;

	} else if ( a.renderOrder !== b.renderOrder ) {

		return a.renderOrder - b.renderOrder;

	} else if ( a.z !== b.z ) {

		return b.z - a.z;

	} else {

		return a.id - b.id;

	}

}
```
</details>

### `needsDoublePass(material: Material): boolean`

**JSDoc:**
```typescript
/**
 * Returns `true` if the given transparent material requires a double pass.
 *
 * @private
 * @function
 * @param {Material} material - The transparent material.
 * @return {boolean} Whether the given material requires a double pass or not.
 */
```

**Parameters:**

- **`material`** `Material`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function needsDoublePass( material ) {

	const hasTransmission = material.transmission > 0 || material.transmissionNode;

	return hasTransmission && material.side === DoubleSide && material.forceSinglePass === false;

}
```
</details>

### `RenderList.begin(): RenderList`

**JSDoc:**
```typescript
/**
	 * This method is called right at the beginning of a render call
	 * before the scene is analyzed. It prepares the internal data
	 * structures for the upcoming render lists generation.
	 *
	 * @return {RenderList} A reference to this render list.
	 */
```

**Returns:** `RenderList`

<details><summary>Code</summary>

```typescript
begin() {

		this.renderItemsIndex = 0;

		this.opaque.length = 0;
		this.transparentDoublePass.length = 0;
		this.transparent.length = 0;
		this.bundles.length = 0;

		this.lightsArray.length = 0;

		this.occlusionQueryCount = 0;

		return this;

	}
```
</details>

### `RenderList.getNextRenderItem(object: Object3D, geometry: BufferGeometry, material: Material, groupOrder: number, z: number, group: number, clippingContext: ClippingContext): any`

**JSDoc:**
```typescript
/**
	 * Returns a render item for the giving render item state. The state is defined
	 * by a series of object-related parameters.
	 *
	 * The method avoids object creation by holding render items and reusing them in
	 * subsequent render calls (just with different property values).
	 *
	 * @param {Object3D} object - The 3D object.
	 * @param {BufferGeometry} geometry - The 3D object's geometry.
	 * @param {Material} material - The 3D object's material.
	 * @param {number} groupOrder - The current group order.
	 * @param {number} z - Th 3D object's depth value (z value in clip space).
	 * @param {?number} group - {?Object} group - Only relevant for objects using multiple materials. This represents a group entry from the respective `BufferGeometry`.
	 * @param {ClippingContext} clippingContext - The current clipping context.
	 * @return {Object} The render item.
	 */
```

**Parameters:**

- **`object`** `Object3D`
- **`geometry`** `BufferGeometry`
- **`material`** `Material`
- **`groupOrder`** `number`
- **`z`** `number`
- **`group`** `number`
- **`clippingContext`** `ClippingContext`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getNextRenderItem( object, geometry, material, groupOrder, z, group, clippingContext ) {

		let renderItem = this.renderItems[ this.renderItemsIndex ];

		if ( renderItem === undefined ) {

			renderItem = {
				id: object.id,
				object: object,
				geometry: geometry,
				material: material,
				groupOrder: groupOrder,
				renderOrder: object.renderOrder,
				z: z,
				group: group,
				clippingContext: clippingContext
			};

			this.renderItems[ this.renderItemsIndex ] = renderItem;

		} else {

			renderItem.id = object.id;
			renderItem.object = object;
			renderItem.geometry = geometry;
			renderItem.material = material;
			renderItem.groupOrder = groupOrder;
			renderItem.renderOrder = object.renderOrder;
			renderItem.z = z;
			renderItem.group = group;
			renderItem.clippingContext = clippingContext;

		}

		this.renderItemsIndex ++;

		return renderItem;

	}
```
</details>

### `RenderList.push(object: Object3D, geometry: BufferGeometry, material: Material, groupOrder: number, z: number, group: number, clippingContext: ClippingContext): void`

**JSDoc:**
```typescript
/**
	 * Pushes the given object as a render item to the internal render lists.
	 * The selected lists depend on the object properties.
	 *
	 * @param {Object3D} object - The 3D object.
	 * @param {BufferGeometry} geometry - The 3D object's geometry.
	 * @param {Material} material - The 3D object's material.
	 * @param {number} groupOrder - The current group order.
	 * @param {number} z - Th 3D object's depth value (z value in clip space).
	 * @param {?number} group - {?Object} group - Only relevant for objects using multiple materials. This represents a group entry from the respective `BufferGeometry`.
	 * @param {ClippingContext} clippingContext - The current clipping context.
	 */
```

**Parameters:**

- **`object`** `Object3D`
- **`geometry`** `BufferGeometry`
- **`material`** `Material`
- **`groupOrder`** `number`
- **`z`** `number`
- **`group`** `number`
- **`clippingContext`** `ClippingContext`

**Returns:** `void`

**Calls:**

- `this.getNextRenderItem`
- `needsDoublePass`
- `this.transparentDoublePass.push`
- `this.transparent.push`
- `this.opaque.push`

<details><summary>Code</summary>

```typescript
push( object, geometry, material, groupOrder, z, group, clippingContext ) {

		const renderItem = this.getNextRenderItem( object, geometry, material, groupOrder, z, group, clippingContext );

		if ( object.occlusionTest === true ) this.occlusionQueryCount ++;

		if ( material.transparent === true || material.transmission > 0 ) {

			if ( needsDoublePass( material ) ) this.transparentDoublePass.push( renderItem );

			this.transparent.push( renderItem );

		} else {

			this.opaque.push( renderItem );

		}

	}
```
</details>

### `RenderList.unshift(object: Object3D, geometry: BufferGeometry, material: Material, groupOrder: number, z: number, group: number, clippingContext: ClippingContext): void`

**JSDoc:**
```typescript
/**
	 * Inserts the given object as a render item at the start of the internal render lists.
	 * The selected lists depend on the object properties.
	 *
	 * @param {Object3D} object - The 3D object.
	 * @param {BufferGeometry} geometry - The 3D object's geometry.
	 * @param {Material} material - The 3D object's material.
	 * @param {number} groupOrder - The current group order.
	 * @param {number} z - Th 3D object's depth value (z value in clip space).
	 * @param {?number} group - {?Object} group - Only relevant for objects using multiple materials. This represents a group entry from the respective `BufferGeometry`.
	 * @param {ClippingContext} clippingContext - The current clipping context.
	 */
```

**Parameters:**

- **`object`** `Object3D`
- **`geometry`** `BufferGeometry`
- **`material`** `Material`
- **`groupOrder`** `number`
- **`z`** `number`
- **`group`** `number`
- **`clippingContext`** `ClippingContext`

**Returns:** `void`

**Calls:**

- `this.getNextRenderItem`
- `needsDoublePass`
- `this.transparentDoublePass.unshift`
- `this.transparent.unshift`
- `this.opaque.unshift`

<details><summary>Code</summary>

```typescript
unshift( object, geometry, material, groupOrder, z, group, clippingContext ) {

		const renderItem = this.getNextRenderItem( object, geometry, material, groupOrder, z, group, clippingContext );

		if ( material.transparent === true || material.transmission > 0 ) {

			if ( needsDoublePass( material ) ) this.transparentDoublePass.unshift( renderItem );

			this.transparent.unshift( renderItem );

		} else {

			this.opaque.unshift( renderItem );

		}

	}
```
</details>

### `RenderList.pushBundle(group: any): void`

**JSDoc:**
```typescript
/**
	 * Pushes render bundle group data into the render list.
	 *
	 * @param {Object} group - Bundle group data.
	 */
```

**Parameters:**

- **`group`** `any`

**Returns:** `void`

**Calls:**

- `this.bundles.push`

<details><summary>Code</summary>

```typescript
pushBundle( group ) {

		this.bundles.push( group );

	}
```
</details>

### `RenderList.pushLight(light: Light): void`

**JSDoc:**
```typescript
/**
	 * Pushes a light into the render list.
	 *
	 * @param {Light} light - The light.
	 */
```

**Parameters:**

- **`light`** `Light`

**Returns:** `void`

**Calls:**

- `this.lightsArray.push`

<details><summary>Code</summary>

```typescript
pushLight( light ) {

		this.lightsArray.push( light );

	}
```
</details>

### `RenderList.sort(customOpaqueSort: (arg0: any, arg1: any) => number, customTransparentSort: (arg0: any, arg1: any) => number): void`

**JSDoc:**
```typescript
/**
	 * Sorts the internal render lists.
	 *
	 * @param {?function(any, any): number} customOpaqueSort - A custom sort function for opaque objects.
	 * @param {?function(any, any): number} customTransparentSort -  A custom sort function for transparent objects.
	 */
```

**Parameters:**

- **`customOpaqueSort`** `(arg0: any, arg1: any) => number`
- **`customTransparentSort`** `(arg0: any, arg1: any) => number`

**Returns:** `void`

**Calls:**

- `this.opaque.sort`
- `this.transparentDoublePass.sort`
- `this.transparent.sort`

<details><summary>Code</summary>

```typescript
sort( customOpaqueSort, customTransparentSort ) {

		if ( this.opaque.length > 1 ) this.opaque.sort( customOpaqueSort || painterSortStable );
		if ( this.transparentDoublePass.length > 1 ) this.transparentDoublePass.sort( customTransparentSort || reversePainterSortStable );
		if ( this.transparent.length > 1 ) this.transparent.sort( customTransparentSort || reversePainterSortStable );

	}
```
</details>

### `RenderList.finish(): void`

**JSDoc:**
```typescript
/**
	 * This method performs finalizing tasks right after the render lists
	 * have been generated.
	 */
```

**Returns:** `void`

**Calls:**

- `this.lightsNode.setLights`

**Internal Comments:**
```
// update lights (x5)
// Clear references from inactive renderItems in the list
```

<details><summary>Code</summary>

```typescript
finish() {

		// update lights

		this.lightsNode.setLights( this.lightsArray );

		// Clear references from inactive renderItems in the list

		for ( let i = this.renderItemsIndex, il = this.renderItems.length; i < il; i ++ ) {

			const renderItem = this.renderItems[ i ];

			if ( renderItem.id === null ) break;

			renderItem.id = null;
			renderItem.object = null;
			renderItem.geometry = null;
			renderItem.material = null;
			renderItem.groupOrder = null;
			renderItem.renderOrder = null;
			renderItem.z = null;
			renderItem.group = null;
			renderItem.clippingContext = null;

		}

	}
```
</details>


---

## Classes

### `RenderList`

<details><summary>Class Code</summary>

```ts
class RenderList {

	/**
	 * Constructs a render list.
	 *
	 * @param {Lighting} lighting - The lighting management component.
	 * @param {Scene} scene - The scene.
	 * @param {Camera} camera - The camera the scene is rendered with.
	 */
	constructor( lighting, scene, camera ) {

		/**
		 * 3D objects are transformed into render items and stored in this array.
		 *
		 * @type {Array<Object>}
		 */
		this.renderItems = [];

		/**
		 * The current render items index.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.renderItemsIndex = 0;

		/**
		 * A list with opaque render items.
		 *
		 * @type {Array<Object>}
		 */
		this.opaque = [];

		/**
		 * A list with transparent render items which require
		 * double pass rendering (e.g. transmissive objects).
		 *
		 * @type {Array<Object>}
		 */
		this.transparentDoublePass = [];

		/**
		 * A list with transparent render items.
		 *
		 * @type {Array<Object>}
		 */
		this.transparent = [];

		/**
		 * A list with transparent render bundle data.
		 *
		 * @type {Array<Object>}
		 */
		this.bundles = [];

		/**
		 * The render list's lights node. This node is later
		 * relevant for the actual analytical light nodes which
		 * compute the scene's lighting in the shader.
		 *
		 * @type {LightsNode}
		 */
		this.lightsNode = lighting.getNode( scene, camera );

		/**
		 * The scene's lights stored in an array. This array
		 * is used to setup the lights node.
		 *
		 * @type {Array<Light>}
		 */
		this.lightsArray = [];

		/**
		 * The scene.
		 *
		 * @type {Scene}
		 */
		this.scene = scene;

		/**
		 * The camera the scene is rendered with.
		 *
		 * @type {Camera}
		 */
		this.camera = camera;

		/**
		 * How many objects perform occlusion query tests.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.occlusionQueryCount = 0;

	}

	/**
	 * This method is called right at the beginning of a render call
	 * before the scene is analyzed. It prepares the internal data
	 * structures for the upcoming render lists generation.
	 *
	 * @return {RenderList} A reference to this render list.
	 */
	begin() {

		this.renderItemsIndex = 0;

		this.opaque.length = 0;
		this.transparentDoublePass.length = 0;
		this.transparent.length = 0;
		this.bundles.length = 0;

		this.lightsArray.length = 0;

		this.occlusionQueryCount = 0;

		return this;

	}

	/**
	 * Returns a render item for the giving render item state. The state is defined
	 * by a series of object-related parameters.
	 *
	 * The method avoids object creation by holding render items and reusing them in
	 * subsequent render calls (just with different property values).
	 *
	 * @param {Object3D} object - The 3D object.
	 * @param {BufferGeometry} geometry - The 3D object's geometry.
	 * @param {Material} material - The 3D object's material.
	 * @param {number} groupOrder - The current group order.
	 * @param {number} z - Th 3D object's depth value (z value in clip space).
	 * @param {?number} group - {?Object} group - Only relevant for objects using multiple materials. This represents a group entry from the respective `BufferGeometry`.
	 * @param {ClippingContext} clippingContext - The current clipping context.
	 * @return {Object} The render item.
	 */
	getNextRenderItem( object, geometry, material, groupOrder, z, group, clippingContext ) {

		let renderItem = this.renderItems[ this.renderItemsIndex ];

		if ( renderItem === undefined ) {

			renderItem = {
				id: object.id,
				object: object,
				geometry: geometry,
				material: material,
				groupOrder: groupOrder,
				renderOrder: object.renderOrder,
				z: z,
				group: group,
				clippingContext: clippingContext
			};

			this.renderItems[ this.renderItemsIndex ] = renderItem;

		} else {

			renderItem.id = object.id;
			renderItem.object = object;
			renderItem.geometry = geometry;
			renderItem.material = material;
			renderItem.groupOrder = groupOrder;
			renderItem.renderOrder = object.renderOrder;
			renderItem.z = z;
			renderItem.group = group;
			renderItem.clippingContext = clippingContext;

		}

		this.renderItemsIndex ++;

		return renderItem;

	}

	/**
	 * Pushes the given object as a render item to the internal render lists.
	 * The selected lists depend on the object properties.
	 *
	 * @param {Object3D} object - The 3D object.
	 * @param {BufferGeometry} geometry - The 3D object's geometry.
	 * @param {Material} material - The 3D object's material.
	 * @param {number} groupOrder - The current group order.
	 * @param {number} z - Th 3D object's depth value (z value in clip space).
	 * @param {?number} group - {?Object} group - Only relevant for objects using multiple materials. This represents a group entry from the respective `BufferGeometry`.
	 * @param {ClippingContext} clippingContext - The current clipping context.
	 */
	push( object, geometry, material, groupOrder, z, group, clippingContext ) {

		const renderItem = this.getNextRenderItem( object, geometry, material, groupOrder, z, group, clippingContext );

		if ( object.occlusionTest === true ) this.occlusionQueryCount ++;

		if ( material.transparent === true || material.transmission > 0 ) {

			if ( needsDoublePass( material ) ) this.transparentDoublePass.push( renderItem );

			this.transparent.push( renderItem );

		} else {

			this.opaque.push( renderItem );

		}

	}

	/**
	 * Inserts the given object as a render item at the start of the internal render lists.
	 * The selected lists depend on the object properties.
	 *
	 * @param {Object3D} object - The 3D object.
	 * @param {BufferGeometry} geometry - The 3D object's geometry.
	 * @param {Material} material - The 3D object's material.
	 * @param {number} groupOrder - The current group order.
	 * @param {number} z - Th 3D object's depth value (z value in clip space).
	 * @param {?number} group - {?Object} group - Only relevant for objects using multiple materials. This represents a group entry from the respective `BufferGeometry`.
	 * @param {ClippingContext} clippingContext - The current clipping context.
	 */
	unshift( object, geometry, material, groupOrder, z, group, clippingContext ) {

		const renderItem = this.getNextRenderItem( object, geometry, material, groupOrder, z, group, clippingContext );

		if ( material.transparent === true || material.transmission > 0 ) {

			if ( needsDoublePass( material ) ) this.transparentDoublePass.unshift( renderItem );

			this.transparent.unshift( renderItem );

		} else {

			this.opaque.unshift( renderItem );

		}

	}

	/**
	 * Pushes render bundle group data into the render list.
	 *
	 * @param {Object} group - Bundle group data.
	 */
	pushBundle( group ) {

		this.bundles.push( group );

	}

	/**
	 * Pushes a light into the render list.
	 *
	 * @param {Light} light - The light.
	 */
	pushLight( light ) {

		this.lightsArray.push( light );

	}

	/**
	 * Sorts the internal render lists.
	 *
	 * @param {?function(any, any): number} customOpaqueSort - A custom sort function for opaque objects.
	 * @param {?function(any, any): number} customTransparentSort -  A custom sort function for transparent objects.
	 */
	sort( customOpaqueSort, customTransparentSort ) {

		if ( this.opaque.length > 1 ) this.opaque.sort( customOpaqueSort || painterSortStable );
		if ( this.transparentDoublePass.length > 1 ) this.transparentDoublePass.sort( customTransparentSort || reversePainterSortStable );
		if ( this.transparent.length > 1 ) this.transparent.sort( customTransparentSort || reversePainterSortStable );

	}

	/**
	 * This method performs finalizing tasks right after the render lists
	 * have been generated.
	 */
	finish() {

		// update lights

		this.lightsNode.setLights( this.lightsArray );

		// Clear references from inactive renderItems in the list

		for ( let i = this.renderItemsIndex, il = this.renderItems.length; i < il; i ++ ) {

			const renderItem = this.renderItems[ i ];

			if ( renderItem.id === null ) break;

			renderItem.id = null;
			renderItem.object = null;
			renderItem.geometry = null;
			renderItem.material = null;
			renderItem.groupOrder = null;
			renderItem.renderOrder = null;
			renderItem.z = null;
			renderItem.group = null;
			renderItem.clippingContext = null;

		}

	}

}
```
</details>

#### Methods

##### `begin(): RenderList`

<details><summary>Code</summary>

```ts
begin() {

		this.renderItemsIndex = 0;

		this.opaque.length = 0;
		this.transparentDoublePass.length = 0;
		this.transparent.length = 0;
		this.bundles.length = 0;

		this.lightsArray.length = 0;

		this.occlusionQueryCount = 0;

		return this;

	}
```
</details>

##### `getNextRenderItem(object: Object3D, geometry: BufferGeometry, material: Material, groupOrder: number, z: number, group: number, clippingContext: ClippingContext): any`

<details><summary>Code</summary>

```ts
getNextRenderItem( object, geometry, material, groupOrder, z, group, clippingContext ) {

		let renderItem = this.renderItems[ this.renderItemsIndex ];

		if ( renderItem === undefined ) {

			renderItem = {
				id: object.id,
				object: object,
				geometry: geometry,
				material: material,
				groupOrder: groupOrder,
				renderOrder: object.renderOrder,
				z: z,
				group: group,
				clippingContext: clippingContext
			};

			this.renderItems[ this.renderItemsIndex ] = renderItem;

		} else {

			renderItem.id = object.id;
			renderItem.object = object;
			renderItem.geometry = geometry;
			renderItem.material = material;
			renderItem.groupOrder = groupOrder;
			renderItem.renderOrder = object.renderOrder;
			renderItem.z = z;
			renderItem.group = group;
			renderItem.clippingContext = clippingContext;

		}

		this.renderItemsIndex ++;

		return renderItem;

	}
```
</details>

##### `push(object: Object3D, geometry: BufferGeometry, material: Material, groupOrder: number, z: number, group: number, clippingContext: ClippingContext): void`

<details><summary>Code</summary>

```ts
push( object, geometry, material, groupOrder, z, group, clippingContext ) {

		const renderItem = this.getNextRenderItem( object, geometry, material, groupOrder, z, group, clippingContext );

		if ( object.occlusionTest === true ) this.occlusionQueryCount ++;

		if ( material.transparent === true || material.transmission > 0 ) {

			if ( needsDoublePass( material ) ) this.transparentDoublePass.push( renderItem );

			this.transparent.push( renderItem );

		} else {

			this.opaque.push( renderItem );

		}

	}
```
</details>

##### `unshift(object: Object3D, geometry: BufferGeometry, material: Material, groupOrder: number, z: number, group: number, clippingContext: ClippingContext): void`

<details><summary>Code</summary>

```ts
unshift( object, geometry, material, groupOrder, z, group, clippingContext ) {

		const renderItem = this.getNextRenderItem( object, geometry, material, groupOrder, z, group, clippingContext );

		if ( material.transparent === true || material.transmission > 0 ) {

			if ( needsDoublePass( material ) ) this.transparentDoublePass.unshift( renderItem );

			this.transparent.unshift( renderItem );

		} else {

			this.opaque.unshift( renderItem );

		}

	}
```
</details>

##### `pushBundle(group: any): void`

<details><summary>Code</summary>

```ts
pushBundle( group ) {

		this.bundles.push( group );

	}
```
</details>

##### `pushLight(light: Light): void`

<details><summary>Code</summary>

```ts
pushLight( light ) {

		this.lightsArray.push( light );

	}
```
</details>

##### `sort(customOpaqueSort: (arg0: any, arg1: any) => number, customTransparentSort: (arg0: any, arg1: any) => number): void`

<details><summary>Code</summary>

```ts
sort( customOpaqueSort, customTransparentSort ) {

		if ( this.opaque.length > 1 ) this.opaque.sort( customOpaqueSort || painterSortStable );
		if ( this.transparentDoublePass.length > 1 ) this.transparentDoublePass.sort( customTransparentSort || reversePainterSortStable );
		if ( this.transparent.length > 1 ) this.transparent.sort( customTransparentSort || reversePainterSortStable );

	}
```
</details>

##### `finish(): void`

<details><summary>Code</summary>

```ts
finish() {

		// update lights

		this.lightsNode.setLights( this.lightsArray );

		// Clear references from inactive renderItems in the list

		for ( let i = this.renderItemsIndex, il = this.renderItems.length; i < il; i ++ ) {

			const renderItem = this.renderItems[ i ];

			if ( renderItem.id === null ) break;

			renderItem.id = null;
			renderItem.object = null;
			renderItem.geometry = null;
			renderItem.material = null;
			renderItem.groupOrder = null;
			renderItem.renderOrder = null;
			renderItem.z = null;
			renderItem.group = null;
			renderItem.clippingContext = null;

		}

	}
```
</details>


---