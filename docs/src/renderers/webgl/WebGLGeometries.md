[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLGeometries.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 18 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLGeometries.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Uint16BufferAttribute` | `../../core/BufferAttribute.js` |
| `Uint32BufferAttribute` | `../../core/BufferAttribute.js` |
| `arrayNeedsUint32` | `../../utils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `geometries` | `{}` | let/var | `{}` | ✗ |
| `wireframeAttributes` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `geometry` | `any` | let/var | `event.target` | ✗ |
| `geometryAttributes` | `any` | let/var | `geometry.attributes` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `geometryIndex` | `any` | let/var | `geometry.index` | ✗ |
| `geometryPosition` | `any` | let/var | `geometry.attributes.position` | ✗ |
| `version` | `number` | let/var | `0` | ✗ |
| `array` | `any` | let/var | `geometryIndex.array` | ✗ |
| `a` | `any` | let/var | `array[ i + 0 ]` | ✗ |
| `b` | `any` | let/var | `array[ i + 1 ]` | ✗ |
| `c` | `any` | let/var | `array[ i + 2 ]` | ✗ |
| `array` | `any` | let/var | `geometryPosition.array` | ✗ |
| `a` | `number` | let/var | `i + 0` | ✗ |
| `b` | `number` | let/var | `i + 1` | ✗ |
| `c` | `number` | let/var | `i + 2` | ✗ |
| `attribute` | `Uint32BufferAttribute \| Uint16Buffer...` | let/var | `new ( arrayNeedsUint32( indices ) ? Uint32BufferAttribute : Uint16BufferAttri...` | ✗ |
| `geometryIndex` | `any` | let/var | `geometry.index` | ✗ |


---

## Functions

### `WebGLGeometries(gl: any, attributes: any, info: any, bindingStates: any): { get: (object: any, geometry: any) => any; update: (geometry: any) => void; getWireframeAttribute: (geometry: any) => any; }`

**Parameters:**

- **`gl`** `any`
- **`attributes`** `any`
- **`info`** `any`
- **`bindingStates`** `any`

**Returns:** `{ get: (object: any, geometry: any) => any; update: (geometry: any) => void; getWireframeAttribute: (geometry: any) => any; }`

**Calls:**

- `attributes.remove`
- `geometry.removeEventListener`
- `wireframeAttributes.get`
- `wireframeAttributes.delete`
- `bindingStates.releaseStatesOfGeometry`
- `geometry.addEventListener`
- `attributes.update`
- `indices.push`
- `arrayNeedsUint32 (from ../../utils.js)`
- `wireframeAttributes.set`
- `updateWireframeAttribute`

**Internal Comments:**
```
// (x11)
// Updating index buffer in VAO now. See WebGLBindingStates.
// Updating index buffer in VAO now. See WebGLBindingStates (x2)
// if the attribute is obsolete, create a new one
```

<details><summary>Code</summary>

```typescript
function WebGLGeometries( gl, attributes, info, bindingStates ) {

	const geometries = {};
	const wireframeAttributes = new WeakMap();

	function onGeometryDispose( event ) {

		const geometry = event.target;

		if ( geometry.index !== null ) {

			attributes.remove( geometry.index );

		}

		for ( const name in geometry.attributes ) {

			attributes.remove( geometry.attributes[ name ] );

		}

		geometry.removeEventListener( 'dispose', onGeometryDispose );

		delete geometries[ geometry.id ];

		const attribute = wireframeAttributes.get( geometry );

		if ( attribute ) {

			attributes.remove( attribute );
			wireframeAttributes.delete( geometry );

		}

		bindingStates.releaseStatesOfGeometry( geometry );

		if ( geometry.isInstancedBufferGeometry === true ) {

			delete geometry._maxInstanceCount;

		}

		//

		info.memory.geometries --;

	}

	function get( object, geometry ) {

		if ( geometries[ geometry.id ] === true ) return geometry;

		geometry.addEventListener( 'dispose', onGeometryDispose );

		geometries[ geometry.id ] = true;

		info.memory.geometries ++;

		return geometry;

	}

	function update( geometry ) {

		const geometryAttributes = geometry.attributes;

		// Updating index buffer in VAO now. See WebGLBindingStates.

		for ( const name in geometryAttributes ) {

			attributes.update( geometryAttributes[ name ], gl.ARRAY_BUFFER );

		}

	}

	function updateWireframeAttribute( geometry ) {

		const indices = [];

		const geometryIndex = geometry.index;
		const geometryPosition = geometry.attributes.position;
		let version = 0;

		if ( geometryIndex !== null ) {

			const array = geometryIndex.array;
			version = geometryIndex.version;

			for ( let i = 0, l = array.length; i < l; i += 3 ) {

				const a = array[ i + 0 ];
				const b = array[ i + 1 ];
				const c = array[ i + 2 ];

				indices.push( a, b, b, c, c, a );

			}

		} else if ( geometryPosition !== undefined ) {

			const array = geometryPosition.array;
			version = geometryPosition.version;

			for ( let i = 0, l = ( array.length / 3 ) - 1; i < l; i += 3 ) {

				const a = i + 0;
				const b = i + 1;
				const c = i + 2;

				indices.push( a, b, b, c, c, a );

			}

		} else {

			return;

		}

		const attribute = new ( arrayNeedsUint32( indices ) ? Uint32BufferAttribute : Uint16BufferAttribute )( indices, 1 );
		attribute.version = version;

		// Updating index buffer in VAO now. See WebGLBindingStates

		//

		const previousAttribute = wireframeAttributes.get( geometry );

		if ( previousAttribute ) attributes.remove( previousAttribute );

		//

		wireframeAttributes.set( geometry, attribute );

	}

	function getWireframeAttribute( geometry ) {

		const currentAttribute = wireframeAttributes.get( geometry );

		if ( currentAttribute ) {

			const geometryIndex = geometry.index;

			if ( geometryIndex !== null ) {

				// if the attribute is obsolete, create a new one

				if ( currentAttribute.version < geometryIndex.version ) {

					updateWireframeAttribute( geometry );

				}

			}

		} else {

			updateWireframeAttribute( geometry );

		}

		return wireframeAttributes.get( geometry );

	}

	return {

		get: get,
		update: update,

		getWireframeAttribute: getWireframeAttribute

	};

}
```
</details>

### `onGeometryDispose(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `attributes.remove`
- `geometry.removeEventListener`
- `wireframeAttributes.get`
- `wireframeAttributes.delete`
- `bindingStates.releaseStatesOfGeometry`

**Internal Comments:**
```
// (x5)
```

<details><summary>Code</summary>

```typescript
function onGeometryDispose( event ) {

		const geometry = event.target;

		if ( geometry.index !== null ) {

			attributes.remove( geometry.index );

		}

		for ( const name in geometry.attributes ) {

			attributes.remove( geometry.attributes[ name ] );

		}

		geometry.removeEventListener( 'dispose', onGeometryDispose );

		delete geometries[ geometry.id ];

		const attribute = wireframeAttributes.get( geometry );

		if ( attribute ) {

			attributes.remove( attribute );
			wireframeAttributes.delete( geometry );

		}

		bindingStates.releaseStatesOfGeometry( geometry );

		if ( geometry.isInstancedBufferGeometry === true ) {

			delete geometry._maxInstanceCount;

		}

		//

		info.memory.geometries --;

	}
```
</details>

### `get(object: any, geometry: any): any`

**Parameters:**

- **`object`** `any`
- **`geometry`** `any`

**Returns:** `any`

**Calls:**

- `geometry.addEventListener`

<details><summary>Code</summary>

```typescript
function get( object, geometry ) {

		if ( geometries[ geometry.id ] === true ) return geometry;

		geometry.addEventListener( 'dispose', onGeometryDispose );

		geometries[ geometry.id ] = true;

		info.memory.geometries ++;

		return geometry;

	}
```
</details>

### `update(geometry: any): void`

**Parameters:**

- **`geometry`** `any`

**Returns:** `void`

**Calls:**

- `attributes.update`

**Internal Comments:**
```
// Updating index buffer in VAO now. See WebGLBindingStates.
```

<details><summary>Code</summary>

```typescript
function update( geometry ) {

		const geometryAttributes = geometry.attributes;

		// Updating index buffer in VAO now. See WebGLBindingStates.

		for ( const name in geometryAttributes ) {

			attributes.update( geometryAttributes[ name ], gl.ARRAY_BUFFER );

		}

	}
```
</details>

### `updateWireframeAttribute(geometry: any): void`

**Parameters:**

- **`geometry`** `any`

**Returns:** `void`

**Calls:**

- `indices.push`
- `arrayNeedsUint32 (from ../../utils.js)`
- `wireframeAttributes.get`
- `attributes.remove`
- `wireframeAttributes.set`

**Internal Comments:**
```
// Updating index buffer in VAO now. See WebGLBindingStates (x2)
// (x6)
```

<details><summary>Code</summary>

```typescript
function updateWireframeAttribute( geometry ) {

		const indices = [];

		const geometryIndex = geometry.index;
		const geometryPosition = geometry.attributes.position;
		let version = 0;

		if ( geometryIndex !== null ) {

			const array = geometryIndex.array;
			version = geometryIndex.version;

			for ( let i = 0, l = array.length; i < l; i += 3 ) {

				const a = array[ i + 0 ];
				const b = array[ i + 1 ];
				const c = array[ i + 2 ];

				indices.push( a, b, b, c, c, a );

			}

		} else if ( geometryPosition !== undefined ) {

			const array = geometryPosition.array;
			version = geometryPosition.version;

			for ( let i = 0, l = ( array.length / 3 ) - 1; i < l; i += 3 ) {

				const a = i + 0;
				const b = i + 1;
				const c = i + 2;

				indices.push( a, b, b, c, c, a );

			}

		} else {

			return;

		}

		const attribute = new ( arrayNeedsUint32( indices ) ? Uint32BufferAttribute : Uint16BufferAttribute )( indices, 1 );
		attribute.version = version;

		// Updating index buffer in VAO now. See WebGLBindingStates

		//

		const previousAttribute = wireframeAttributes.get( geometry );

		if ( previousAttribute ) attributes.remove( previousAttribute );

		//

		wireframeAttributes.set( geometry, attribute );

	}
```
</details>

### `getWireframeAttribute(geometry: any): any`

**Parameters:**

- **`geometry`** `any`

**Returns:** `any`

**Calls:**

- `wireframeAttributes.get`
- `updateWireframeAttribute`

**Internal Comments:**
```
// if the attribute is obsolete, create a new one
```

<details><summary>Code</summary>

```typescript
function getWireframeAttribute( geometry ) {

		const currentAttribute = wireframeAttributes.get( geometry );

		if ( currentAttribute ) {

			const geometryIndex = geometry.index;

			if ( geometryIndex !== null ) {

				// if the attribute is obsolete, create a new one

				if ( currentAttribute.version < geometryIndex.version ) {

					updateWireframeAttribute( geometry );

				}

			}

		} else {

			updateWireframeAttribute( geometry );

		}

		return wireframeAttributes.get( geometry );

	}
```
</details>


---