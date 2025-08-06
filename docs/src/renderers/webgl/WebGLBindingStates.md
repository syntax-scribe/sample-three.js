[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLBindingStates.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 20 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 49 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLBindingStates.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `IntType` | `../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `bindingStates` | `{}` | let/var | `{}` | ✗ |
| `currentState` | `{ geometry: any; program: any; wirefr...` | let/var | `defaultState` | ✗ |
| `forceUpdate` | `boolean` | let/var | `false` | ✗ |
| `updateBuffers` | `boolean` | let/var | `false` | ✗ |
| `wireframe` | `boolean` | let/var | `( material.wireframe === true )` | ✗ |
| `programMap` | `any` | let/var | `bindingStates[ geometry.id ]` | ✗ |
| `stateMap` | `any` | let/var | `programMap[ program.id ]` | ✗ |
| `state` | `any` | let/var | `stateMap[ wireframe ]` | ✗ |
| `newAttributes` | `any[]` | let/var | `[]` | ✗ |
| `enabledAttributes` | `any[]` | let/var | `[]` | ✗ |
| `attributeDivisors` | `any[]` | let/var | `[]` | ✗ |
| `cachedAttributes` | `{}` | let/var | `currentState.attributes` | ✗ |
| `geometryAttributes` | `any` | let/var | `geometry.attributes` | ✗ |
| `attributesNum` | `number` | let/var | `0` | ✗ |
| `programAttribute` | `any` | let/var | `programAttributes[ name ]` | ✗ |
| `cachedAttribute` | `any` | let/var | `cachedAttributes[ name ]` | ✗ |
| `geometryAttribute` | `any` | let/var | `geometryAttributes[ name ]` | ✗ |
| `cache` | `{}` | let/var | `{}` | ✗ |
| `attributes` | `any` | let/var | `geometry.attributes` | ✗ |
| `attributesNum` | `number` | let/var | `0` | ✗ |
| `programAttribute` | `any` | let/var | `programAttributes[ name ]` | ✗ |
| `attribute` | `any` | let/var | `attributes[ name ]` | ✗ |
| `data` | `{ attribute: any; }` | let/var | `{}` | ✗ |
| `newAttributes` | `number[]` | let/var | `currentState.newAttributes` | ✗ |
| `newAttributes` | `number[]` | let/var | `currentState.newAttributes` | ✗ |
| `enabledAttributes` | `number[]` | let/var | `currentState.enabledAttributes` | ✗ |
| `attributeDivisors` | `number[]` | let/var | `currentState.attributeDivisors` | ✗ |
| `newAttributes` | `number[]` | let/var | `currentState.newAttributes` | ✗ |
| `enabledAttributes` | `number[]` | let/var | `currentState.enabledAttributes` | ✗ |
| `geometryAttributes` | `any` | let/var | `geometry.attributes` | ✗ |
| `materialDefaultAttributeValues` | `any` | let/var | `material.defaultAttributeValues` | ✗ |
| `programAttribute` | `any` | let/var | `programAttributes[ name ]` | ✗ |
| `geometryAttribute` | `any` | let/var | `geometryAttributes[ name ]` | ✗ |
| `normalized` | `any` | let/var | `geometryAttribute.normalized` | ✗ |
| `size` | `any` | let/var | `geometryAttribute.itemSize` | ✗ |
| `buffer` | `any` | let/var | `attribute.buffer` | ✗ |
| `type` | `any` | let/var | `attribute.type` | ✗ |
| `bytesPerElement` | `any` | let/var | `attribute.bytesPerElement` | ✗ |
| `integer` | `boolean` | let/var | `( type === gl.INT \|\| type === gl.UNSIGNED_INT \|\| geometryAttribute.gpuTyp...` | ✗ |
| `data` | `any` | let/var | `geometryAttribute.data` | ✗ |
| `stride` | `any` | let/var | `data.stride` | ✗ |
| `offset` | `any` | let/var | `geometryAttribute.offset` | ✗ |
| `value` | `any` | let/var | `materialDefaultAttributeValues[ name ]` | ✗ |
| `programMap` | `any` | let/var | `bindingStates[ geometryId ]` | ✗ |
| `stateMap` | `any` | let/var | `programMap[ programId ]` | ✗ |
| `programMap` | `any` | let/var | `bindingStates[ geometry.id ]` | ✗ |
| `stateMap` | `any` | let/var | `programMap[ programId ]` | ✗ |
| `programMap` | `any` | let/var | `bindingStates[ geometryId ]` | ✗ |
| `stateMap` | `any` | let/var | `programMap[ program.id ]` | ✗ |


---

## Functions

### `WebGLBindingStates(gl: any, attributes: any): { setup: (object: any, material: any, program: any, geometry: any, index: any) => void; reset: () => void; resetDefaultState: () => void; dispose: () => void; releaseStatesOfGeometry: (geometry: any) => void; releaseStatesOfProgram: (program: any) => void; initAttributes: () => void; enableAttribute: (attribute: any...`

**Parameters:**

- **`gl`** `any`
- **`attributes`** `any`

**Returns:** `{ setup: (object: any, material: any, program: any, geometry: any, index: any) => void; reset: () => void; resetDefaultState: () => void; dispose: () => void; releaseStatesOfGeometry: (geometry: any) => void; releaseStatesOfProgram: (program: any) => void; initAttributes: () => void; enableAttribute: (attribute: any...`

**Calls:**

- `gl.getParameter`
- `createBindingState`
- `getBindingState`
- `bindVertexArrayObject`
- `needsUpdate`
- `saveCache`
- `attributes.update`
- `setupVertexAttributes`
- `gl.bindBuffer`
- `attributes.get`
- `gl.createVertexArray`
- `gl.bindVertexArray`
- `gl.deleteVertexArray`
- `createVertexArrayObject`
- `program.getAttributes`
- `enableAttributeAndDivisor`
- `gl.enableVertexAttribArray`
- `gl.vertexAttribDivisor`
- `gl.disableVertexAttribArray`
- `gl.vertexAttribIPointer`
- `gl.vertexAttribPointer`
- `initAttributes`
- `enableAttribute`
- `vertexAttribPointer`
- `gl.vertexAttrib2fv`
- `gl.vertexAttrib3fv`
- `gl.vertexAttrib4fv`
- `gl.vertexAttrib1fv`
- `disableUnusedAttributes`
- `reset`
- `deleteVertexArrayObject`
- `resetDefaultState`

**Internal Comments:**
```
// for backward compatibility on non-VAO support browser (x2)
// TODO Attribute may not be available on context restore
// check for integer attributes (x2)
// for backward-compatibility
```

<details><summary>Code</summary>

```typescript
function WebGLBindingStates( gl, attributes ) {

	const maxVertexAttributes = gl.getParameter( gl.MAX_VERTEX_ATTRIBS );

	const bindingStates = {};

	const defaultState = createBindingState( null );
	let currentState = defaultState;
	let forceUpdate = false;

	function setup( object, material, program, geometry, index ) {

		let updateBuffers = false;

		const state = getBindingState( geometry, program, material );

		if ( currentState !== state ) {

			currentState = state;
			bindVertexArrayObject( currentState.object );

		}

		updateBuffers = needsUpdate( object, geometry, program, index );

		if ( updateBuffers ) saveCache( object, geometry, program, index );

		if ( index !== null ) {

			attributes.update( index, gl.ELEMENT_ARRAY_BUFFER );

		}

		if ( updateBuffers || forceUpdate ) {

			forceUpdate = false;

			setupVertexAttributes( object, material, program, geometry );

			if ( index !== null ) {

				gl.bindBuffer( gl.ELEMENT_ARRAY_BUFFER, attributes.get( index ).buffer );

			}

		}

	}

	function createVertexArrayObject() {

		return gl.createVertexArray();

	}

	function bindVertexArrayObject( vao ) {

		return gl.bindVertexArray( vao );

	}

	function deleteVertexArrayObject( vao ) {

		return gl.deleteVertexArray( vao );

	}

	function getBindingState( geometry, program, material ) {

		const wireframe = ( material.wireframe === true );

		let programMap = bindingStates[ geometry.id ];

		if ( programMap === undefined ) {

			programMap = {};
			bindingStates[ geometry.id ] = programMap;

		}

		let stateMap = programMap[ program.id ];

		if ( stateMap === undefined ) {

			stateMap = {};
			programMap[ program.id ] = stateMap;

		}

		let state = stateMap[ wireframe ];

		if ( state === undefined ) {

			state = createBindingState( createVertexArrayObject() );
			stateMap[ wireframe ] = state;

		}

		return state;

	}

	function createBindingState( vao ) {

		const newAttributes = [];
		const enabledAttributes = [];
		const attributeDivisors = [];

		for ( let i = 0; i < maxVertexAttributes; i ++ ) {

			newAttributes[ i ] = 0;
			enabledAttributes[ i ] = 0;
			attributeDivisors[ i ] = 0;

		}

		return {

			// for backward compatibility on non-VAO support browser
			geometry: null,
			program: null,
			wireframe: false,

			newAttributes: newAttributes,
			enabledAttributes: enabledAttributes,
			attributeDivisors: attributeDivisors,
			object: vao,
			attributes: {},
			index: null

		};

	}

	function needsUpdate( object, geometry, program, index ) {

		const cachedAttributes = currentState.attributes;
		const geometryAttributes = geometry.attributes;

		let attributesNum = 0;

		const programAttributes = program.getAttributes();

		for ( const name in programAttributes ) {

			const programAttribute = programAttributes[ name ];

			if ( programAttribute.location >= 0 ) {

				const cachedAttribute = cachedAttributes[ name ];
				let geometryAttribute = geometryAttributes[ name ];

				if ( geometryAttribute === undefined ) {

					if ( name === 'instanceMatrix' && object.instanceMatrix ) geometryAttribute = object.instanceMatrix;
					if ( name === 'instanceColor' && object.instanceColor ) geometryAttribute = object.instanceColor;

				}

				if ( cachedAttribute === undefined ) return true;

				if ( cachedAttribute.attribute !== geometryAttribute ) return true;

				if ( geometryAttribute && cachedAttribute.data !== geometryAttribute.data ) return true;

				attributesNum ++;

			}

		}

		if ( currentState.attributesNum !== attributesNum ) return true;

		if ( currentState.index !== index ) return true;

		return false;

	}

	function saveCache( object, geometry, program, index ) {

		const cache = {};
		const attributes = geometry.attributes;
		let attributesNum = 0;

		const programAttributes = program.getAttributes();

		for ( const name in programAttributes ) {

			const programAttribute = programAttributes[ name ];

			if ( programAttribute.location >= 0 ) {

				let attribute = attributes[ name ];

				if ( attribute === undefined ) {

					if ( name === 'instanceMatrix' && object.instanceMatrix ) attribute = object.instanceMatrix;
					if ( name === 'instanceColor' && object.instanceColor ) attribute = object.instanceColor;

				}

				const data = {};
				data.attribute = attribute;

				if ( attribute && attribute.data ) {

					data.data = attribute.data;

				}

				cache[ name ] = data;

				attributesNum ++;

			}

		}

		currentState.attributes = cache;
		currentState.attributesNum = attributesNum;

		currentState.index = index;

	}

	function initAttributes() {

		const newAttributes = currentState.newAttributes;

		for ( let i = 0, il = newAttributes.length; i < il; i ++ ) {

			newAttributes[ i ] = 0;

		}

	}

	function enableAttribute( attribute ) {

		enableAttributeAndDivisor( attribute, 0 );

	}

	function enableAttributeAndDivisor( attribute, meshPerAttribute ) {

		const newAttributes = currentState.newAttributes;
		const enabledAttributes = currentState.enabledAttributes;
		const attributeDivisors = currentState.attributeDivisors;

		newAttributes[ attribute ] = 1;

		if ( enabledAttributes[ attribute ] === 0 ) {

			gl.enableVertexAttribArray( attribute );
			enabledAttributes[ attribute ] = 1;

		}

		if ( attributeDivisors[ attribute ] !== meshPerAttribute ) {

			gl.vertexAttribDivisor( attribute, meshPerAttribute );
			attributeDivisors[ attribute ] = meshPerAttribute;

		}

	}

	function disableUnusedAttributes() {

		const newAttributes = currentState.newAttributes;
		const enabledAttributes = currentState.enabledAttributes;

		for ( let i = 0, il = enabledAttributes.length; i < il; i ++ ) {

			if ( enabledAttributes[ i ] !== newAttributes[ i ] ) {

				gl.disableVertexAttribArray( i );
				enabledAttributes[ i ] = 0;

			}

		}

	}

	function vertexAttribPointer( index, size, type, normalized, stride, offset, integer ) {

		if ( integer === true ) {

			gl.vertexAttribIPointer( index, size, type, stride, offset );

		} else {

			gl.vertexAttribPointer( index, size, type, normalized, stride, offset );

		}

	}

	function setupVertexAttributes( object, material, program, geometry ) {

		initAttributes();

		const geometryAttributes = geometry.attributes;

		const programAttributes = program.getAttributes();

		const materialDefaultAttributeValues = material.defaultAttributeValues;

		for ( const name in programAttributes ) {

			const programAttribute = programAttributes[ name ];

			if ( programAttribute.location >= 0 ) {

				let geometryAttribute = geometryAttributes[ name ];

				if ( geometryAttribute === undefined ) {

					if ( name === 'instanceMatrix' && object.instanceMatrix ) geometryAttribute = object.instanceMatrix;
					if ( name === 'instanceColor' && object.instanceColor ) geometryAttribute = object.instanceColor;

				}

				if ( geometryAttribute !== undefined ) {

					const normalized = geometryAttribute.normalized;
					const size = geometryAttribute.itemSize;

					const attribute = attributes.get( geometryAttribute );

					// TODO Attribute may not be available on context restore

					if ( attribute === undefined ) continue;

					const buffer = attribute.buffer;
					const type = attribute.type;
					const bytesPerElement = attribute.bytesPerElement;

					// check for integer attributes

					const integer = ( type === gl.INT || type === gl.UNSIGNED_INT || geometryAttribute.gpuType === IntType );

					if ( geometryAttribute.isInterleavedBufferAttribute ) {

						const data = geometryAttribute.data;
						const stride = data.stride;
						const offset = geometryAttribute.offset;

						if ( data.isInstancedInterleavedBuffer ) {

							for ( let i = 0; i < programAttribute.locationSize; i ++ ) {

								enableAttributeAndDivisor( programAttribute.location + i, data.meshPerAttribute );

							}

							if ( object.isInstancedMesh !== true && geometry._maxInstanceCount === undefined ) {

								geometry._maxInstanceCount = data.meshPerAttribute * data.count;

							}

						} else {

							for ( let i = 0; i < programAttribute.locationSize; i ++ ) {

								enableAttribute( programAttribute.location + i );

							}

						}

						gl.bindBuffer( gl.ARRAY_BUFFER, buffer );

						for ( let i = 0; i < programAttribute.locationSize; i ++ ) {

							vertexAttribPointer(
								programAttribute.location + i,
								size / programAttribute.locationSize,
								type,
								normalized,
								stride * bytesPerElement,
								( offset + ( size / programAttribute.locationSize ) * i ) * bytesPerElement,
								integer
							);

						}

					} else {

						if ( geometryAttribute.isInstancedBufferAttribute ) {

							for ( let i = 0; i < programAttribute.locationSize; i ++ ) {

								enableAttributeAndDivisor( programAttribute.location + i, geometryAttribute.meshPerAttribute );

							}

							if ( object.isInstancedMesh !== true && geometry._maxInstanceCount === undefined ) {

								geometry._maxInstanceCount = geometryAttribute.meshPerAttribute * geometryAttribute.count;

							}

						} else {

							for ( let i = 0; i < programAttribute.locationSize; i ++ ) {

								enableAttribute( programAttribute.location + i );

							}

						}

						gl.bindBuffer( gl.ARRAY_BUFFER, buffer );

						for ( let i = 0; i < programAttribute.locationSize; i ++ ) {

							vertexAttribPointer(
								programAttribute.location + i,
								size / programAttribute.locationSize,
								type,
								normalized,
								size * bytesPerElement,
								( size / programAttribute.locationSize ) * i * bytesPerElement,
								integer
							);

						}

					}

				} else if ( materialDefaultAttributeValues !== undefined ) {

					const value = materialDefaultAttributeValues[ name ];

					if ( value !== undefined ) {

						switch ( value.length ) {

							case 2:
								gl.vertexAttrib2fv( programAttribute.location, value );
								break;

							case 3:
								gl.vertexAttrib3fv( programAttribute.location, value );
								break;

							case 4:
								gl.vertexAttrib4fv( programAttribute.location, value );
								break;

							default:
								gl.vertexAttrib1fv( programAttribute.location, value );

						}

					}

				}

			}

		}

		disableUnusedAttributes();

	}

	function dispose() {

		reset();

		for ( const geometryId in bindingStates ) {

			const programMap = bindingStates[ geometryId ];

			for ( const programId in programMap ) {

				const stateMap = programMap[ programId ];

				for ( const wireframe in stateMap ) {

					deleteVertexArrayObject( stateMap[ wireframe ].object );

					delete stateMap[ wireframe ];

				}

				delete programMap[ programId ];

			}

			delete bindingStates[ geometryId ];

		}

	}

	function releaseStatesOfGeometry( geometry ) {

		if ( bindingStates[ geometry.id ] === undefined ) return;

		const programMap = bindingStates[ geometry.id ];

		for ( const programId in programMap ) {

			const stateMap = programMap[ programId ];

			for ( const wireframe in stateMap ) {

				deleteVertexArrayObject( stateMap[ wireframe ].object );

				delete stateMap[ wireframe ];

			}

			delete programMap[ programId ];

		}

		delete bindingStates[ geometry.id ];

	}

	function releaseStatesOfProgram( program ) {

		for ( const geometryId in bindingStates ) {

			const programMap = bindingStates[ geometryId ];

			if ( programMap[ program.id ] === undefined ) continue;

			const stateMap = programMap[ program.id ];

			for ( const wireframe in stateMap ) {

				deleteVertexArrayObject( stateMap[ wireframe ].object );

				delete stateMap[ wireframe ];

			}

			delete programMap[ program.id ];

		}

	}

	function reset() {

		resetDefaultState();
		forceUpdate = true;

		if ( currentState === defaultState ) return;

		currentState = defaultState;
		bindVertexArrayObject( currentState.object );

	}

	// for backward-compatibility

	function resetDefaultState() {

		defaultState.geometry = null;
		defaultState.program = null;
		defaultState.wireframe = false;

	}

	return {

		setup: setup,
		reset: reset,
		resetDefaultState: resetDefaultState,
		dispose: dispose,
		releaseStatesOfGeometry: releaseStatesOfGeometry,
		releaseStatesOfProgram: releaseStatesOfProgram,

		initAttributes: initAttributes,
		enableAttribute: enableAttribute,
		disableUnusedAttributes: disableUnusedAttributes

	};

}
```
</details>

### `setup(object: any, material: any, program: any, geometry: any, index: any): void`

**Parameters:**

- **`object`** `any`
- **`material`** `any`
- **`program`** `any`
- **`geometry`** `any`
- **`index`** `any`

**Returns:** `void`

**Calls:**

- `getBindingState`
- `bindVertexArrayObject`
- `needsUpdate`
- `saveCache`
- `attributes.update`
- `setupVertexAttributes`
- `gl.bindBuffer`
- `attributes.get`

<details><summary>Code</summary>

```typescript
function setup( object, material, program, geometry, index ) {

		let updateBuffers = false;

		const state = getBindingState( geometry, program, material );

		if ( currentState !== state ) {

			currentState = state;
			bindVertexArrayObject( currentState.object );

		}

		updateBuffers = needsUpdate( object, geometry, program, index );

		if ( updateBuffers ) saveCache( object, geometry, program, index );

		if ( index !== null ) {

			attributes.update( index, gl.ELEMENT_ARRAY_BUFFER );

		}

		if ( updateBuffers || forceUpdate ) {

			forceUpdate = false;

			setupVertexAttributes( object, material, program, geometry );

			if ( index !== null ) {

				gl.bindBuffer( gl.ELEMENT_ARRAY_BUFFER, attributes.get( index ).buffer );

			}

		}

	}
```
</details>

### `createVertexArrayObject(): any`

**Returns:** `any`

**Calls:**

- `gl.createVertexArray`

<details><summary>Code</summary>

```typescript
function createVertexArrayObject() {

		return gl.createVertexArray();

	}
```
</details>

### `bindVertexArrayObject(vao: any): any`

**Parameters:**

- **`vao`** `any`

**Returns:** `any`

**Calls:**

- `gl.bindVertexArray`

<details><summary>Code</summary>

```typescript
function bindVertexArrayObject( vao ) {

		return gl.bindVertexArray( vao );

	}
```
</details>

### `deleteVertexArrayObject(vao: any): any`

**Parameters:**

- **`vao`** `any`

**Returns:** `any`

**Calls:**

- `gl.deleteVertexArray`

<details><summary>Code</summary>

```typescript
function deleteVertexArrayObject( vao ) {

		return gl.deleteVertexArray( vao );

	}
```
</details>

### `getBindingState(geometry: any, program: any, material: any): any`

**Parameters:**

- **`geometry`** `any`
- **`program`** `any`
- **`material`** `any`

**Returns:** `any`

**Calls:**

- `createBindingState`
- `createVertexArrayObject`

<details><summary>Code</summary>

```typescript
function getBindingState( geometry, program, material ) {

		const wireframe = ( material.wireframe === true );

		let programMap = bindingStates[ geometry.id ];

		if ( programMap === undefined ) {

			programMap = {};
			bindingStates[ geometry.id ] = programMap;

		}

		let stateMap = programMap[ program.id ];

		if ( stateMap === undefined ) {

			stateMap = {};
			programMap[ program.id ] = stateMap;

		}

		let state = stateMap[ wireframe ];

		if ( state === undefined ) {

			state = createBindingState( createVertexArrayObject() );
			stateMap[ wireframe ] = state;

		}

		return state;

	}
```
</details>

### `createBindingState(vao: any): { geometry: any; program: any; wireframe: boolean; newAttributes: number[]; enabledAttributes: number[]; attributeDivisors: number[]; object: any; attributes: {}; index: any; }`

**Parameters:**

- **`vao`** `any`

**Returns:** `{ geometry: any; program: any; wireframe: boolean; newAttributes: number[]; enabledAttributes: number[]; attributeDivisors: number[]; object: any; attributes: {}; index: any; }`

**Internal Comments:**
```
// for backward compatibility on non-VAO support browser (x2)
```

<details><summary>Code</summary>

```typescript
function createBindingState( vao ) {

		const newAttributes = [];
		const enabledAttributes = [];
		const attributeDivisors = [];

		for ( let i = 0; i < maxVertexAttributes; i ++ ) {

			newAttributes[ i ] = 0;
			enabledAttributes[ i ] = 0;
			attributeDivisors[ i ] = 0;

		}

		return {

			// for backward compatibility on non-VAO support browser
			geometry: null,
			program: null,
			wireframe: false,

			newAttributes: newAttributes,
			enabledAttributes: enabledAttributes,
			attributeDivisors: attributeDivisors,
			object: vao,
			attributes: {},
			index: null

		};

	}
```
</details>

### `needsUpdate(object: any, geometry: any, program: any, index: any): boolean`

**Parameters:**

- **`object`** `any`
- **`geometry`** `any`
- **`program`** `any`
- **`index`** `any`

**Returns:** `boolean`

**Calls:**

- `program.getAttributes`

<details><summary>Code</summary>

```typescript
function needsUpdate( object, geometry, program, index ) {

		const cachedAttributes = currentState.attributes;
		const geometryAttributes = geometry.attributes;

		let attributesNum = 0;

		const programAttributes = program.getAttributes();

		for ( const name in programAttributes ) {

			const programAttribute = programAttributes[ name ];

			if ( programAttribute.location >= 0 ) {

				const cachedAttribute = cachedAttributes[ name ];
				let geometryAttribute = geometryAttributes[ name ];

				if ( geometryAttribute === undefined ) {

					if ( name === 'instanceMatrix' && object.instanceMatrix ) geometryAttribute = object.instanceMatrix;
					if ( name === 'instanceColor' && object.instanceColor ) geometryAttribute = object.instanceColor;

				}

				if ( cachedAttribute === undefined ) return true;

				if ( cachedAttribute.attribute !== geometryAttribute ) return true;

				if ( geometryAttribute && cachedAttribute.data !== geometryAttribute.data ) return true;

				attributesNum ++;

			}

		}

		if ( currentState.attributesNum !== attributesNum ) return true;

		if ( currentState.index !== index ) return true;

		return false;

	}
```
</details>

### `saveCache(object: any, geometry: any, program: any, index: any): void`

**Parameters:**

- **`object`** `any`
- **`geometry`** `any`
- **`program`** `any`
- **`index`** `any`

**Returns:** `void`

**Calls:**

- `program.getAttributes`

<details><summary>Code</summary>

```typescript
function saveCache( object, geometry, program, index ) {

		const cache = {};
		const attributes = geometry.attributes;
		let attributesNum = 0;

		const programAttributes = program.getAttributes();

		for ( const name in programAttributes ) {

			const programAttribute = programAttributes[ name ];

			if ( programAttribute.location >= 0 ) {

				let attribute = attributes[ name ];

				if ( attribute === undefined ) {

					if ( name === 'instanceMatrix' && object.instanceMatrix ) attribute = object.instanceMatrix;
					if ( name === 'instanceColor' && object.instanceColor ) attribute = object.instanceColor;

				}

				const data = {};
				data.attribute = attribute;

				if ( attribute && attribute.data ) {

					data.data = attribute.data;

				}

				cache[ name ] = data;

				attributesNum ++;

			}

		}

		currentState.attributes = cache;
		currentState.attributesNum = attributesNum;

		currentState.index = index;

	}
```
</details>

### `initAttributes(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function initAttributes() {

		const newAttributes = currentState.newAttributes;

		for ( let i = 0, il = newAttributes.length; i < il; i ++ ) {

			newAttributes[ i ] = 0;

		}

	}
```
</details>

### `enableAttribute(attribute: any): void`

**Parameters:**

- **`attribute`** `any`

**Returns:** `void`

**Calls:**

- `enableAttributeAndDivisor`

<details><summary>Code</summary>

```typescript
function enableAttribute( attribute ) {

		enableAttributeAndDivisor( attribute, 0 );

	}
```
</details>

### `enableAttributeAndDivisor(attribute: any, meshPerAttribute: any): void`

**Parameters:**

- **`attribute`** `any`
- **`meshPerAttribute`** `any`

**Returns:** `void`

**Calls:**

- `gl.enableVertexAttribArray`
- `gl.vertexAttribDivisor`

<details><summary>Code</summary>

```typescript
function enableAttributeAndDivisor( attribute, meshPerAttribute ) {

		const newAttributes = currentState.newAttributes;
		const enabledAttributes = currentState.enabledAttributes;
		const attributeDivisors = currentState.attributeDivisors;

		newAttributes[ attribute ] = 1;

		if ( enabledAttributes[ attribute ] === 0 ) {

			gl.enableVertexAttribArray( attribute );
			enabledAttributes[ attribute ] = 1;

		}

		if ( attributeDivisors[ attribute ] !== meshPerAttribute ) {

			gl.vertexAttribDivisor( attribute, meshPerAttribute );
			attributeDivisors[ attribute ] = meshPerAttribute;

		}

	}
```
</details>

### `disableUnusedAttributes(): void`

**Returns:** `void`

**Calls:**

- `gl.disableVertexAttribArray`

<details><summary>Code</summary>

```typescript
function disableUnusedAttributes() {

		const newAttributes = currentState.newAttributes;
		const enabledAttributes = currentState.enabledAttributes;

		for ( let i = 0, il = enabledAttributes.length; i < il; i ++ ) {

			if ( enabledAttributes[ i ] !== newAttributes[ i ] ) {

				gl.disableVertexAttribArray( i );
				enabledAttributes[ i ] = 0;

			}

		}

	}
```
</details>

### `vertexAttribPointer(index: any, size: any, type: any, normalized: any, stride: any, offset: any, integer: any): void`

**Parameters:**

- **`index`** `any`
- **`size`** `any`
- **`type`** `any`
- **`normalized`** `any`
- **`stride`** `any`
- **`offset`** `any`
- **`integer`** `any`

**Returns:** `void`

**Calls:**

- `gl.vertexAttribIPointer`
- `gl.vertexAttribPointer`

<details><summary>Code</summary>

```typescript
function vertexAttribPointer( index, size, type, normalized, stride, offset, integer ) {

		if ( integer === true ) {

			gl.vertexAttribIPointer( index, size, type, stride, offset );

		} else {

			gl.vertexAttribPointer( index, size, type, normalized, stride, offset );

		}

	}
```
</details>

### `setupVertexAttributes(object: any, material: any, program: any, geometry: any): void`

**Parameters:**

- **`object`** `any`
- **`material`** `any`
- **`program`** `any`
- **`geometry`** `any`

**Returns:** `void`

**Calls:**

- `initAttributes`
- `program.getAttributes`
- `attributes.get`
- `enableAttributeAndDivisor`
- `enableAttribute`
- `gl.bindBuffer`
- `vertexAttribPointer`
- `gl.vertexAttrib2fv`
- `gl.vertexAttrib3fv`
- `gl.vertexAttrib4fv`
- `gl.vertexAttrib1fv`
- `disableUnusedAttributes`

**Internal Comments:**
```
// TODO Attribute may not be available on context restore
// check for integer attributes (x2)
```

<details><summary>Code</summary>

```typescript
function setupVertexAttributes( object, material, program, geometry ) {

		initAttributes();

		const geometryAttributes = geometry.attributes;

		const programAttributes = program.getAttributes();

		const materialDefaultAttributeValues = material.defaultAttributeValues;

		for ( const name in programAttributes ) {

			const programAttribute = programAttributes[ name ];

			if ( programAttribute.location >= 0 ) {

				let geometryAttribute = geometryAttributes[ name ];

				if ( geometryAttribute === undefined ) {

					if ( name === 'instanceMatrix' && object.instanceMatrix ) geometryAttribute = object.instanceMatrix;
					if ( name === 'instanceColor' && object.instanceColor ) geometryAttribute = object.instanceColor;

				}

				if ( geometryAttribute !== undefined ) {

					const normalized = geometryAttribute.normalized;
					const size = geometryAttribute.itemSize;

					const attribute = attributes.get( geometryAttribute );

					// TODO Attribute may not be available on context restore

					if ( attribute === undefined ) continue;

					const buffer = attribute.buffer;
					const type = attribute.type;
					const bytesPerElement = attribute.bytesPerElement;

					// check for integer attributes

					const integer = ( type === gl.INT || type === gl.UNSIGNED_INT || geometryAttribute.gpuType === IntType );

					if ( geometryAttribute.isInterleavedBufferAttribute ) {

						const data = geometryAttribute.data;
						const stride = data.stride;
						const offset = geometryAttribute.offset;

						if ( data.isInstancedInterleavedBuffer ) {

							for ( let i = 0; i < programAttribute.locationSize; i ++ ) {

								enableAttributeAndDivisor( programAttribute.location + i, data.meshPerAttribute );

							}

							if ( object.isInstancedMesh !== true && geometry._maxInstanceCount === undefined ) {

								geometry._maxInstanceCount = data.meshPerAttribute * data.count;

							}

						} else {

							for ( let i = 0; i < programAttribute.locationSize; i ++ ) {

								enableAttribute( programAttribute.location + i );

							}

						}

						gl.bindBuffer( gl.ARRAY_BUFFER, buffer );

						for ( let i = 0; i < programAttribute.locationSize; i ++ ) {

							vertexAttribPointer(
								programAttribute.location + i,
								size / programAttribute.locationSize,
								type,
								normalized,
								stride * bytesPerElement,
								( offset + ( size / programAttribute.locationSize ) * i ) * bytesPerElement,
								integer
							);

						}

					} else {

						if ( geometryAttribute.isInstancedBufferAttribute ) {

							for ( let i = 0; i < programAttribute.locationSize; i ++ ) {

								enableAttributeAndDivisor( programAttribute.location + i, geometryAttribute.meshPerAttribute );

							}

							if ( object.isInstancedMesh !== true && geometry._maxInstanceCount === undefined ) {

								geometry._maxInstanceCount = geometryAttribute.meshPerAttribute * geometryAttribute.count;

							}

						} else {

							for ( let i = 0; i < programAttribute.locationSize; i ++ ) {

								enableAttribute( programAttribute.location + i );

							}

						}

						gl.bindBuffer( gl.ARRAY_BUFFER, buffer );

						for ( let i = 0; i < programAttribute.locationSize; i ++ ) {

							vertexAttribPointer(
								programAttribute.location + i,
								size / programAttribute.locationSize,
								type,
								normalized,
								size * bytesPerElement,
								( size / programAttribute.locationSize ) * i * bytesPerElement,
								integer
							);

						}

					}

				} else if ( materialDefaultAttributeValues !== undefined ) {

					const value = materialDefaultAttributeValues[ name ];

					if ( value !== undefined ) {

						switch ( value.length ) {

							case 2:
								gl.vertexAttrib2fv( programAttribute.location, value );
								break;

							case 3:
								gl.vertexAttrib3fv( programAttribute.location, value );
								break;

							case 4:
								gl.vertexAttrib4fv( programAttribute.location, value );
								break;

							default:
								gl.vertexAttrib1fv( programAttribute.location, value );

						}

					}

				}

			}

		}

		disableUnusedAttributes();

	}
```
</details>

### `dispose(): void`

**Returns:** `void`

**Calls:**

- `reset`
- `deleteVertexArrayObject`

<details><summary>Code</summary>

```typescript
function dispose() {

		reset();

		for ( const geometryId in bindingStates ) {

			const programMap = bindingStates[ geometryId ];

			for ( const programId in programMap ) {

				const stateMap = programMap[ programId ];

				for ( const wireframe in stateMap ) {

					deleteVertexArrayObject( stateMap[ wireframe ].object );

					delete stateMap[ wireframe ];

				}

				delete programMap[ programId ];

			}

			delete bindingStates[ geometryId ];

		}

	}
```
</details>

### `releaseStatesOfGeometry(geometry: any): void`

**Parameters:**

- **`geometry`** `any`

**Returns:** `void`

**Calls:**

- `deleteVertexArrayObject`

<details><summary>Code</summary>

```typescript
function releaseStatesOfGeometry( geometry ) {

		if ( bindingStates[ geometry.id ] === undefined ) return;

		const programMap = bindingStates[ geometry.id ];

		for ( const programId in programMap ) {

			const stateMap = programMap[ programId ];

			for ( const wireframe in stateMap ) {

				deleteVertexArrayObject( stateMap[ wireframe ].object );

				delete stateMap[ wireframe ];

			}

			delete programMap[ programId ];

		}

		delete bindingStates[ geometry.id ];

	}
```
</details>

### `releaseStatesOfProgram(program: any): void`

**Parameters:**

- **`program`** `any`

**Returns:** `void`

**Calls:**

- `deleteVertexArrayObject`

<details><summary>Code</summary>

```typescript
function releaseStatesOfProgram( program ) {

		for ( const geometryId in bindingStates ) {

			const programMap = bindingStates[ geometryId ];

			if ( programMap[ program.id ] === undefined ) continue;

			const stateMap = programMap[ program.id ];

			for ( const wireframe in stateMap ) {

				deleteVertexArrayObject( stateMap[ wireframe ].object );

				delete stateMap[ wireframe ];

			}

			delete programMap[ program.id ];

		}

	}
```
</details>

### `reset(): void`

**Returns:** `void`

**Calls:**

- `resetDefaultState`
- `bindVertexArrayObject`

<details><summary>Code</summary>

```typescript
function reset() {

		resetDefaultState();
		forceUpdate = true;

		if ( currentState === defaultState ) return;

		currentState = defaultState;
		bindVertexArrayObject( currentState.object );

	}
```
</details>

### `resetDefaultState(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function resetDefaultState() {

		defaultState.geometry = null;
		defaultState.program = null;
		defaultState.wireframe = false;

	}
```
</details>


---