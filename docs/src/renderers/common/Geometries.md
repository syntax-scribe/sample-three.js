[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Geometries.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 19 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/Geometries.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DataMap` | `./DataMap.js` |
| `AttributeType` | `./Constants.js` |
| `arrayNeedsUint32` | `../../utils.js` |
| `Uint16BufferAttribute` | `../../core/BufferAttribute.js` |
| `Uint32BufferAttribute` | `../../core/BufferAttribute.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `geometryIndex` | `any` | let/var | `geometry.index` | ✗ |
| `geometryPosition` | `any` | let/var | `geometry.attributes.position` | ✗ |
| `array` | `any` | let/var | `geometryIndex.array` | ✗ |
| `a` | `any` | let/var | `array[ i + 0 ]` | ✗ |
| `b` | `any` | let/var | `array[ i + 1 ]` | ✗ |
| `c` | `any` | let/var | `array[ i + 2 ]` | ✗ |
| `array` | `any` | let/var | `geometryPosition.array` | ✗ |
| `a` | `number` | let/var | `i + 0` | ✗ |
| `b` | `number` | let/var | `i + 1` | ✗ |
| `c` | `number` | let/var | `i + 2` | ✗ |
| `attribute` | `Uint32BufferAttribute \| Uint16Buffer...` | let/var | `new ( arrayNeedsUint32( indices ) ? Uint32BufferAttribute : Uint16BufferAttri...` | ✗ |
| `geometry` | `any` | let/var | `renderObject.geometry` | ✗ |
| `geometry` | `any` | let/var | `renderObject.geometry` | ✗ |
| `index` | `any` | let/var | `geometry.index` | ✗ |
| `indirect` | `any` | let/var | `renderObject.geometry.indirect` | ✗ |
| `callId` | `any` | let/var | `this.info.render.calls` | ✗ |
| `index` | `any` | let/var | `geometry.index` | ✗ |
| `wireframes` | `WeakMap<BufferGeometry, BufferAttribute>` | let/var | `this.wireframes` | ✗ |


---

## Functions

### `getWireframeVersion(geometry: BufferGeometry): number`

**JSDoc:**
```typescript
/**
 * Returns the wireframe version for the given geometry.
 *
 * @private
 * @function
 * @param {BufferGeometry} geometry - The geometry.
 * @return {number} The version.
 */
```

**Parameters:**

- **`geometry`** `BufferGeometry`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function getWireframeVersion( geometry ) {

	return ( geometry.index !== null ) ? geometry.index.version : geometry.attributes.position.version;

}
```
</details>

### `getWireframeIndex(geometry: BufferGeometry): BufferAttribute`

**JSDoc:**
```typescript
/**
 * Returns a wireframe index attribute for the given geometry.
 *
 * @private
 * @function
 * @param {BufferGeometry} geometry - The geometry.
 * @return {BufferAttribute} The wireframe index attribute.
 */
```

**Parameters:**

- **`geometry`** `BufferGeometry`

**Returns:** `BufferAttribute`

**Calls:**

- `indices.push`
- `arrayNeedsUint32 (from ../../utils.js)`
- `getWireframeVersion`

<details><summary>Code</summary>

```typescript
function getWireframeIndex( geometry ) {

	const indices = [];

	const geometryIndex = geometry.index;
	const geometryPosition = geometry.attributes.position;

	if ( geometryIndex !== null ) {

		const array = geometryIndex.array;

		for ( let i = 0, l = array.length; i < l; i += 3 ) {

			const a = array[ i + 0 ];
			const b = array[ i + 1 ];
			const c = array[ i + 2 ];

			indices.push( a, b, b, c, c, a );

		}

	} else {

		const array = geometryPosition.array;

		for ( let i = 0, l = ( array.length / 3 ) - 1; i < l; i += 3 ) {

			const a = i + 0;
			const b = i + 1;
			const c = i + 2;

			indices.push( a, b, b, c, c, a );

		}

	}

	const attribute = new ( arrayNeedsUint32( indices ) ? Uint32BufferAttribute : Uint16BufferAttribute )( indices, 1 );
	attribute.version = getWireframeVersion( geometry );

	return attribute;

}
```
</details>

### `Geometries.has(renderObject: RenderObject): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given render object has an initialized geometry.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {boolean} Whether if the given render object has an initialized geometry or not.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `boolean`

**Calls:**

- `super.has`
- `this.get`

<details><summary>Code</summary>

```typescript
has( renderObject ) {

		const geometry = renderObject.geometry;

		return super.has( geometry ) && this.get( geometry ).initialized === true;

	}
```
</details>

### `Geometries.updateForRender(renderObject: RenderObject): void`

**JSDoc:**
```typescript
/**
	 * Prepares the geometry of the given render object for rendering.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `void`

**Calls:**

- `this.has`
- `this.initGeometry`
- `this.updateAttributes`

<details><summary>Code</summary>

```typescript
updateForRender( renderObject ) {

		if ( this.has( renderObject ) === false ) this.initGeometry( renderObject );

		this.updateAttributes( renderObject );

	}
```
</details>

### `Geometries.initGeometry(renderObject: RenderObject): void`

**JSDoc:**
```typescript
/**
	 * Initializes the geometry of the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `void`

**Calls:**

- `this.get`
- `renderObject.getAttributes`
- `this.attributes.delete`
- `this.wireframes.get`
- `geometry.removeEventListener`
- `geometry.addEventListener`

<details><summary>Code</summary>

```typescript
initGeometry( renderObject ) {

		const geometry = renderObject.geometry;
		const geometryData = this.get( geometry );

		geometryData.initialized = true;

		this.info.memory.geometries ++;

		const onDispose = () => {

			this.info.memory.geometries --;

			const index = geometry.index;
			const geometryAttributes = renderObject.getAttributes();

			if ( index !== null ) {

				this.attributes.delete( index );

			}

			for ( const geometryAttribute of geometryAttributes ) {

				this.attributes.delete( geometryAttribute );

			}

			const wireframeAttribute = this.wireframes.get( geometry );

			if ( wireframeAttribute !== undefined ) {

				this.attributes.delete( wireframeAttribute );

			}

			geometry.removeEventListener( 'dispose', onDispose );

		};

		geometry.addEventListener( 'dispose', onDispose );

	}
```
</details>

### `Geometries.updateAttributes(renderObject: RenderObject): void`

**JSDoc:**
```typescript
/**
	 * Updates the geometry attributes of the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `void`

**Calls:**

- `renderObject.getAttributes`
- `this.updateAttribute`
- `this.getIndex`

**Internal Comments:**
```
// attributes (x2)
// indexes (x2)
// indirect (x2)
```

<details><summary>Code</summary>

```typescript
updateAttributes( renderObject ) {

		// attributes

		const attributes = renderObject.getAttributes();

		for ( const attribute of attributes ) {

			if ( attribute.isStorageBufferAttribute || attribute.isStorageInstancedBufferAttribute ) {

				this.updateAttribute( attribute, AttributeType.STORAGE );

			} else {

				this.updateAttribute( attribute, AttributeType.VERTEX );

			}

		}

		// indexes

		const index = this.getIndex( renderObject );

		if ( index !== null ) {

			this.updateAttribute( index, AttributeType.INDEX );

		}

		// indirect

		const indirect = renderObject.geometry.indirect;

		if ( indirect !== null ) {

			this.updateAttribute( indirect, AttributeType.INDIRECT );

		}

	}
```
</details>

### `Geometries.updateAttribute(attribute: BufferAttribute, type: number): void`

**JSDoc:**
```typescript
/**
	 * Updates the given attribute.
	 *
	 * @param {BufferAttribute} attribute - The attribute to update.
	 * @param {number} type - The attribute type.
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`
- **`type`** `number`

**Returns:** `void`

**Calls:**

- `this.attributeCall.get`
- `this.attributes.update`
- `this.attributeCall.set`

<details><summary>Code</summary>

```typescript
updateAttribute( attribute, type ) {

		const callId = this.info.render.calls;

		if ( ! attribute.isInterleavedBufferAttribute ) {

			if ( this.attributeCall.get( attribute ) !== callId ) {

				this.attributes.update( attribute, type );

				this.attributeCall.set( attribute, callId );

			}

		} else {

			if ( this.attributeCall.get( attribute ) === undefined ) {

				this.attributes.update( attribute, type );

				this.attributeCall.set( attribute, callId );

			} else if ( this.attributeCall.get( attribute.data ) !== callId ) {

				this.attributes.update( attribute, type );

				this.attributeCall.set( attribute.data, callId );

				this.attributeCall.set( attribute, callId );

			}

		}

	}
```
</details>

### `Geometries.getIndirect(renderObject: RenderObject): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Returns the indirect buffer attribute of the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {?BufferAttribute} The indirect attribute. `null` if no indirect drawing is used.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `BufferAttribute`

<details><summary>Code</summary>

```typescript
getIndirect( renderObject ) {

		return renderObject.geometry.indirect;

	}
```
</details>

### `Geometries.getIndex(renderObject: RenderObject): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Returns the index of the given render object's geometry. This is implemented
	 * in a method to return a wireframe index if necessary.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {?BufferAttribute} The index. Returns `null` for non-indexed geometries.
	 */
```

**Parameters:**

- **`renderObject`** `RenderObject`

**Returns:** `BufferAttribute`

**Calls:**

- `wireframes.get`
- `getWireframeIndex`
- `wireframes.set`
- `getWireframeVersion`
- `this.attributes.delete`

<details><summary>Code</summary>

```typescript
getIndex( renderObject ) {

		const { geometry, material } = renderObject;

		let index = geometry.index;

		if ( material.wireframe === true ) {

			const wireframes = this.wireframes;

			let wireframeAttribute = wireframes.get( geometry );

			if ( wireframeAttribute === undefined ) {

				wireframeAttribute = getWireframeIndex( geometry );

				wireframes.set( geometry, wireframeAttribute );

			} else if ( wireframeAttribute.version !== getWireframeVersion( geometry ) ) {

				this.attributes.delete( wireframeAttribute );

				wireframeAttribute = getWireframeIndex( geometry );

				wireframes.set( geometry, wireframeAttribute );

			}

			index = wireframeAttribute;

		}

		return index;

	}
```
</details>

### `onDispose(): void`

**Returns:** `void`

**Calls:**

- `renderObject.getAttributes`
- `this.attributes.delete`
- `this.wireframes.get`
- `geometry.removeEventListener`

<details><summary>Code</summary>

```typescript
() => {

			this.info.memory.geometries --;

			const index = geometry.index;
			const geometryAttributes = renderObject.getAttributes();

			if ( index !== null ) {

				this.attributes.delete( index );

			}

			for ( const geometryAttribute of geometryAttributes ) {

				this.attributes.delete( geometryAttribute );

			}

			const wireframeAttribute = this.wireframes.get( geometry );

			if ( wireframeAttribute !== undefined ) {

				this.attributes.delete( wireframeAttribute );

			}

			geometry.removeEventListener( 'dispose', onDispose );

		}
```
</details>


---

## Classes

### `Geometries`

<details><summary>Class Code</summary>

```ts
class Geometries extends DataMap {

	/**
	 * Constructs a new geometry management component.
	 *
	 * @param {Attributes} attributes - Renderer component for managing attributes.
	 * @param {Info} info - Renderer component for managing metrics and monitoring data.
	 */
	constructor( attributes, info ) {

		super();

		/**
		 * Renderer component for managing attributes.
		 *
		 * @type {Attributes}
		 */
		this.attributes = attributes;

		/**
		 * Renderer component for managing metrics and monitoring data.
		 *
		 * @type {Info}
		 */
		this.info = info;

		/**
		 * Weak Map for managing attributes for wireframe rendering.
		 *
		 * @type {WeakMap<BufferGeometry,BufferAttribute>}
		 */
		this.wireframes = new WeakMap();

		/**
		 * This Weak Map is used to make sure buffer attributes are
		 * updated only once per render call.
		 *
		 * @type {WeakMap<BufferAttribute,number>}
		 */
		this.attributeCall = new WeakMap();

	}

	/**
	 * Returns `true` if the given render object has an initialized geometry.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {boolean} Whether if the given render object has an initialized geometry or not.
	 */
	has( renderObject ) {

		const geometry = renderObject.geometry;

		return super.has( geometry ) && this.get( geometry ).initialized === true;

	}

	/**
	 * Prepares the geometry of the given render object for rendering.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 */
	updateForRender( renderObject ) {

		if ( this.has( renderObject ) === false ) this.initGeometry( renderObject );

		this.updateAttributes( renderObject );

	}

	/**
	 * Initializes the geometry of the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 */
	initGeometry( renderObject ) {

		const geometry = renderObject.geometry;
		const geometryData = this.get( geometry );

		geometryData.initialized = true;

		this.info.memory.geometries ++;

		const onDispose = () => {

			this.info.memory.geometries --;

			const index = geometry.index;
			const geometryAttributes = renderObject.getAttributes();

			if ( index !== null ) {

				this.attributes.delete( index );

			}

			for ( const geometryAttribute of geometryAttributes ) {

				this.attributes.delete( geometryAttribute );

			}

			const wireframeAttribute = this.wireframes.get( geometry );

			if ( wireframeAttribute !== undefined ) {

				this.attributes.delete( wireframeAttribute );

			}

			geometry.removeEventListener( 'dispose', onDispose );

		};

		geometry.addEventListener( 'dispose', onDispose );

	}

	/**
	 * Updates the geometry attributes of the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 */
	updateAttributes( renderObject ) {

		// attributes

		const attributes = renderObject.getAttributes();

		for ( const attribute of attributes ) {

			if ( attribute.isStorageBufferAttribute || attribute.isStorageInstancedBufferAttribute ) {

				this.updateAttribute( attribute, AttributeType.STORAGE );

			} else {

				this.updateAttribute( attribute, AttributeType.VERTEX );

			}

		}

		// indexes

		const index = this.getIndex( renderObject );

		if ( index !== null ) {

			this.updateAttribute( index, AttributeType.INDEX );

		}

		// indirect

		const indirect = renderObject.geometry.indirect;

		if ( indirect !== null ) {

			this.updateAttribute( indirect, AttributeType.INDIRECT );

		}

	}

	/**
	 * Updates the given attribute.
	 *
	 * @param {BufferAttribute} attribute - The attribute to update.
	 * @param {number} type - The attribute type.
	 */
	updateAttribute( attribute, type ) {

		const callId = this.info.render.calls;

		if ( ! attribute.isInterleavedBufferAttribute ) {

			if ( this.attributeCall.get( attribute ) !== callId ) {

				this.attributes.update( attribute, type );

				this.attributeCall.set( attribute, callId );

			}

		} else {

			if ( this.attributeCall.get( attribute ) === undefined ) {

				this.attributes.update( attribute, type );

				this.attributeCall.set( attribute, callId );

			} else if ( this.attributeCall.get( attribute.data ) !== callId ) {

				this.attributes.update( attribute, type );

				this.attributeCall.set( attribute.data, callId );

				this.attributeCall.set( attribute, callId );

			}

		}

	}

	/**
	 * Returns the indirect buffer attribute of the given render object.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {?BufferAttribute} The indirect attribute. `null` if no indirect drawing is used.
	 */
	getIndirect( renderObject ) {

		return renderObject.geometry.indirect;

	}

	/**
	 * Returns the index of the given render object's geometry. This is implemented
	 * in a method to return a wireframe index if necessary.
	 *
	 * @param {RenderObject} renderObject - The render object.
	 * @return {?BufferAttribute} The index. Returns `null` for non-indexed geometries.
	 */
	getIndex( renderObject ) {

		const { geometry, material } = renderObject;

		let index = geometry.index;

		if ( material.wireframe === true ) {

			const wireframes = this.wireframes;

			let wireframeAttribute = wireframes.get( geometry );

			if ( wireframeAttribute === undefined ) {

				wireframeAttribute = getWireframeIndex( geometry );

				wireframes.set( geometry, wireframeAttribute );

			} else if ( wireframeAttribute.version !== getWireframeVersion( geometry ) ) {

				this.attributes.delete( wireframeAttribute );

				wireframeAttribute = getWireframeIndex( geometry );

				wireframes.set( geometry, wireframeAttribute );

			}

			index = wireframeAttribute;

		}

		return index;

	}

}
```
</details>

#### Methods

##### `has(renderObject: RenderObject): boolean`

<details><summary>Code</summary>

```ts
has( renderObject ) {

		const geometry = renderObject.geometry;

		return super.has( geometry ) && this.get( geometry ).initialized === true;

	}
```
</details>

##### `updateForRender(renderObject: RenderObject): void`

<details><summary>Code</summary>

```ts
updateForRender( renderObject ) {

		if ( this.has( renderObject ) === false ) this.initGeometry( renderObject );

		this.updateAttributes( renderObject );

	}
```
</details>

##### `initGeometry(renderObject: RenderObject): void`

<details><summary>Code</summary>

```ts
initGeometry( renderObject ) {

		const geometry = renderObject.geometry;
		const geometryData = this.get( geometry );

		geometryData.initialized = true;

		this.info.memory.geometries ++;

		const onDispose = () => {

			this.info.memory.geometries --;

			const index = geometry.index;
			const geometryAttributes = renderObject.getAttributes();

			if ( index !== null ) {

				this.attributes.delete( index );

			}

			for ( const geometryAttribute of geometryAttributes ) {

				this.attributes.delete( geometryAttribute );

			}

			const wireframeAttribute = this.wireframes.get( geometry );

			if ( wireframeAttribute !== undefined ) {

				this.attributes.delete( wireframeAttribute );

			}

			geometry.removeEventListener( 'dispose', onDispose );

		};

		geometry.addEventListener( 'dispose', onDispose );

	}
```
</details>

##### `updateAttributes(renderObject: RenderObject): void`

<details><summary>Code</summary>

```ts
updateAttributes( renderObject ) {

		// attributes

		const attributes = renderObject.getAttributes();

		for ( const attribute of attributes ) {

			if ( attribute.isStorageBufferAttribute || attribute.isStorageInstancedBufferAttribute ) {

				this.updateAttribute( attribute, AttributeType.STORAGE );

			} else {

				this.updateAttribute( attribute, AttributeType.VERTEX );

			}

		}

		// indexes

		const index = this.getIndex( renderObject );

		if ( index !== null ) {

			this.updateAttribute( index, AttributeType.INDEX );

		}

		// indirect

		const indirect = renderObject.geometry.indirect;

		if ( indirect !== null ) {

			this.updateAttribute( indirect, AttributeType.INDIRECT );

		}

	}
```
</details>

##### `updateAttribute(attribute: BufferAttribute, type: number): void`

<details><summary>Code</summary>

```ts
updateAttribute( attribute, type ) {

		const callId = this.info.render.calls;

		if ( ! attribute.isInterleavedBufferAttribute ) {

			if ( this.attributeCall.get( attribute ) !== callId ) {

				this.attributes.update( attribute, type );

				this.attributeCall.set( attribute, callId );

			}

		} else {

			if ( this.attributeCall.get( attribute ) === undefined ) {

				this.attributes.update( attribute, type );

				this.attributeCall.set( attribute, callId );

			} else if ( this.attributeCall.get( attribute.data ) !== callId ) {

				this.attributes.update( attribute, type );

				this.attributeCall.set( attribute.data, callId );

				this.attributeCall.set( attribute, callId );

			}

		}

	}
```
</details>

##### `getIndirect(renderObject: RenderObject): BufferAttribute`

<details><summary>Code</summary>

```ts
getIndirect( renderObject ) {

		return renderObject.geometry.indirect;

	}
```
</details>

##### `getIndex(renderObject: RenderObject): BufferAttribute`

<details><summary>Code</summary>

```ts
getIndex( renderObject ) {

		const { geometry, material } = renderObject;

		let index = geometry.index;

		if ( material.wireframe === true ) {

			const wireframes = this.wireframes;

			let wireframeAttribute = wireframes.get( geometry );

			if ( wireframeAttribute === undefined ) {

				wireframeAttribute = getWireframeIndex( geometry );

				wireframes.set( geometry, wireframeAttribute );

			} else if ( wireframeAttribute.version !== getWireframeVersion( geometry ) ) {

				this.attributes.delete( wireframeAttribute );

				wireframeAttribute = getWireframeIndex( geometry );

				wireframes.set( geometry, wireframeAttribute );

			}

			index = wireframeAttribute;

		}

		return index;

	}
```
</details>


---