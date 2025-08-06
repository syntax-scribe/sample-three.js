[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLUniformsGroups.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 11 |
| 📊 Variables & Constants | 34 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLUniformsGroups.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `buffers` | `{}` | let/var | `{}` | ✗ |
| `updateList` | `{}` | let/var | `{}` | ✗ |
| `allocatedBindingPoints` | `any[]` | let/var | `[]` | ✗ |
| `webglProgram` | `any` | let/var | `program.program` | ✗ |
| `buffer` | `any` | let/var | `buffers[ uniformsGroup.id ]` | ✗ |
| `webglProgram` | `any` | let/var | `program.program` | ✗ |
| `frame` | `any` | let/var | `info.render.frame` | ✗ |
| `size` | `any` | let/var | `uniformsGroup.__size` | ✗ |
| `usage` | `any` | let/var | `uniformsGroup.usage` | ✗ |
| `buffer` | `any` | let/var | `buffers[ uniformsGroup.id ]` | ✗ |
| `uniforms` | `any` | let/var | `uniformsGroup.uniforms` | ✗ |
| `cache` | `any` | let/var | `uniformsGroup.__cache` | ✗ |
| `uniformArray` | `any` | let/var | `Array.isArray( uniforms[ i ] ) ? uniforms[ i ] : [ uniforms[ i ] ]` | ✗ |
| `uniform` | `any` | let/var | `uniformArray[ j ]` | ✗ |
| `offset` | `any` | let/var | `uniform.__offset` | ✗ |
| `values` | `any` | let/var | `Array.isArray( uniform.value ) ? uniform.value : [ uniform.value ]` | ✗ |
| `arrayOffset` | `number` | let/var | `0` | ✗ |
| `value` | `any` | let/var | `values[ k ]` | ✗ |
| `value` | `any` | let/var | `uniform.value` | ✗ |
| `indexString` | `string` | let/var | `index + '_' + indexArray` | ✗ |
| `cachedObject` | `any` | let/var | `cache[ indexString ]` | ✗ |
| `uniforms` | `any` | let/var | `uniformsGroup.uniforms` | ✗ |
| `offset` | `number` | let/var | `0` | ✗ |
| `chunkSize` | `16` | let/var | `16` | ✗ |
| `uniformArray` | `any` | let/var | `Array.isArray( uniforms[ i ] ) ? uniforms[ i ] : [ uniforms[ i ] ]` | ✗ |
| `uniform` | `any` | let/var | `uniformArray[ j ]` | ✗ |
| `values` | `any` | let/var | `Array.isArray( uniform.value ) ? uniform.value : [ uniform.value ]` | ✗ |
| `value` | `any` | let/var | `values[ k ]` | ✗ |
| `chunkOffset` | `number` | let/var | `offset % chunkSize` | ✗ |
| `chunkPadding` | `number` | let/var | `chunkOffset % info.boundary` | ✗ |
| `chunkStart` | `number` | let/var | `chunkOffset + chunkPadding` | ✗ |
| `chunkOffset` | `number` | let/var | `offset % chunkSize` | ✗ |
| `info` | `{ boundary: number; storage: number; }` | let/var | `{ boundary: 0, // bytes storage: 0 // bytes }` | ✗ |
| `uniformsGroup` | `any` | let/var | `event.target` | ✗ |


---

## Functions

### `WebGLUniformsGroups(gl: any, info: any, capabilities: any, state: any): { bind: (uniformsGroup: any, program: any) => void; update: (uniformsGroup: any, program: any) => void; dispose: () => void; }`

**Parameters:**

- **`gl`** `any`
- **`info`** `any`
- **`capabilities`** `any`
- **`state`** `any`

**Returns:** `{ bind: (uniformsGroup: any, program: any) => void; update: (uniformsGroup: any, program: any) => void; dispose: () => void; }`

**Calls:**

- `gl.getParameter`
- `state.uniformBlockBinding`
- `prepareUniformsGroup`
- `createBuffer`
- `uniformsGroup.addEventListener`
- `state.updateUBOMapping`
- `updateBufferData`
- `allocateBindingPointIndex`
- `gl.createBuffer`
- `gl.bindBuffer`
- `gl.bufferData`
- `gl.bindBufferBase`
- `allocatedBindingPoints.indexOf`
- `allocatedBindingPoints.push`
- `console.error`
- `Array.isArray`
- `hasUniformChanged`
- `getUniformSize`
- `gl.bufferSubData`
- `value.toArray`
- `value.clone`
- `cachedObject.equals`
- `cachedObject.copy`
- `console.warn`
- `uniformsGroup.removeEventListener`
- `allocatedBindingPoints.splice`
- `gl.deleteBuffer`

**Internal Comments:**
```
// ensure to update the binding points/block indices mapping for this program (x2)
// update UBO once per frame (x2)
// the setup of an UBO is independent of a particular shader program but global (x2)
// TODO add integer and struct support
// manually converting 3x3 to 3x4 (x5)
// cache entry does not exist so far
// compare current value with cached entry
// determine total buffer size according to the STD140 layout (x2)
// Hint: STD140 is the only supported layout in WebGL 2 (x2)
// Check for chunk overflow
// Add padding and adjust offset (x3)
// the following two properties will be used for partial buffer updates (x4)
// Update the global offset (x3)
// ensure correct final padding (x2)
// (x4)
// determine sizes according to STD140
// float/int/bool (x4)
// vec2 (x4)
// vec3 (x4)
// vec4 (x4)
// mat3 (in STD140 a 3x3 matrix is represented as 3x4) (x4)
// mat4 (x4)
```

<details><summary>Code</summary>

```typescript
function WebGLUniformsGroups( gl, info, capabilities, state ) {

	let buffers = {};
	let updateList = {};
	let allocatedBindingPoints = [];

	const maxBindingPoints = gl.getParameter( gl.MAX_UNIFORM_BUFFER_BINDINGS ); // binding points are global whereas block indices are per shader program

	function bind( uniformsGroup, program ) {

		const webglProgram = program.program;
		state.uniformBlockBinding( uniformsGroup, webglProgram );

	}

	function update( uniformsGroup, program ) {

		let buffer = buffers[ uniformsGroup.id ];

		if ( buffer === undefined ) {

			prepareUniformsGroup( uniformsGroup );

			buffer = createBuffer( uniformsGroup );
			buffers[ uniformsGroup.id ] = buffer;

			uniformsGroup.addEventListener( 'dispose', onUniformsGroupsDispose );

		}

		// ensure to update the binding points/block indices mapping for this program

		const webglProgram = program.program;
		state.updateUBOMapping( uniformsGroup, webglProgram );

		// update UBO once per frame

		const frame = info.render.frame;

		if ( updateList[ uniformsGroup.id ] !== frame ) {

			updateBufferData( uniformsGroup );

			updateList[ uniformsGroup.id ] = frame;

		}

	}

	function createBuffer( uniformsGroup ) {

		// the setup of an UBO is independent of a particular shader program but global

		const bindingPointIndex = allocateBindingPointIndex();
		uniformsGroup.__bindingPointIndex = bindingPointIndex;

		const buffer = gl.createBuffer();
		const size = uniformsGroup.__size;
		const usage = uniformsGroup.usage;

		gl.bindBuffer( gl.UNIFORM_BUFFER, buffer );
		gl.bufferData( gl.UNIFORM_BUFFER, size, usage );
		gl.bindBuffer( gl.UNIFORM_BUFFER, null );
		gl.bindBufferBase( gl.UNIFORM_BUFFER, bindingPointIndex, buffer );

		return buffer;

	}

	function allocateBindingPointIndex() {

		for ( let i = 0; i < maxBindingPoints; i ++ ) {

			if ( allocatedBindingPoints.indexOf( i ) === - 1 ) {

				allocatedBindingPoints.push( i );
				return i;

			}

		}

		console.error( 'THREE.WebGLRenderer: Maximum number of simultaneously usable uniforms groups reached.' );

		return 0;

	}

	function updateBufferData( uniformsGroup ) {

		const buffer = buffers[ uniformsGroup.id ];
		const uniforms = uniformsGroup.uniforms;
		const cache = uniformsGroup.__cache;

		gl.bindBuffer( gl.UNIFORM_BUFFER, buffer );

		for ( let i = 0, il = uniforms.length; i < il; i ++ ) {

			const uniformArray = Array.isArray( uniforms[ i ] ) ? uniforms[ i ] : [ uniforms[ i ] ];

			for ( let j = 0, jl = uniformArray.length; j < jl; j ++ ) {

				const uniform = uniformArray[ j ];

				if ( hasUniformChanged( uniform, i, j, cache ) === true ) {

					const offset = uniform.__offset;

					const values = Array.isArray( uniform.value ) ? uniform.value : [ uniform.value ];

					let arrayOffset = 0;

					for ( let k = 0; k < values.length; k ++ ) {

						const value = values[ k ];

						const info = getUniformSize( value );

						// TODO add integer and struct support
						if ( typeof value === 'number' || typeof value === 'boolean' ) {

							uniform.__data[ 0 ] = value;
							gl.bufferSubData( gl.UNIFORM_BUFFER, offset + arrayOffset, uniform.__data );

						} else if ( value.isMatrix3 ) {

							// manually converting 3x3 to 3x4

							uniform.__data[ 0 ] = value.elements[ 0 ];
							uniform.__data[ 1 ] = value.elements[ 1 ];
							uniform.__data[ 2 ] = value.elements[ 2 ];
							uniform.__data[ 3 ] = 0;
							uniform.__data[ 4 ] = value.elements[ 3 ];
							uniform.__data[ 5 ] = value.elements[ 4 ];
							uniform.__data[ 6 ] = value.elements[ 5 ];
							uniform.__data[ 7 ] = 0;
							uniform.__data[ 8 ] = value.elements[ 6 ];
							uniform.__data[ 9 ] = value.elements[ 7 ];
							uniform.__data[ 10 ] = value.elements[ 8 ];
							uniform.__data[ 11 ] = 0;

						} else {

							value.toArray( uniform.__data, arrayOffset );

							arrayOffset += info.storage / Float32Array.BYTES_PER_ELEMENT;

						}

					}

					gl.bufferSubData( gl.UNIFORM_BUFFER, offset, uniform.__data );

				}

			}

		}

		gl.bindBuffer( gl.UNIFORM_BUFFER, null );

	}

	function hasUniformChanged( uniform, index, indexArray, cache ) {

		const value = uniform.value;
		const indexString = index + '_' + indexArray;

		if ( cache[ indexString ] === undefined ) {

			// cache entry does not exist so far

			if ( typeof value === 'number' || typeof value === 'boolean' ) {

				cache[ indexString ] = value;

			} else {

				cache[ indexString ] = value.clone();

			}

			return true;

		} else {

			const cachedObject = cache[ indexString ];

			// compare current value with cached entry

			if ( typeof value === 'number' || typeof value === 'boolean' ) {

				if ( cachedObject !== value ) {

					cache[ indexString ] = value;
					return true;

				}

			} else {

				if ( cachedObject.equals( value ) === false ) {

					cachedObject.copy( value );
					return true;

				}

			}

		}

		return false;

	}

	function prepareUniformsGroup( uniformsGroup ) {

		// determine total buffer size according to the STD140 layout
		// Hint: STD140 is the only supported layout in WebGL 2

		const uniforms = uniformsGroup.uniforms;

		let offset = 0; // global buffer offset in bytes
		const chunkSize = 16; // size of a chunk in bytes

		for ( let i = 0, l = uniforms.length; i < l; i ++ ) {

			const uniformArray = Array.isArray( uniforms[ i ] ) ? uniforms[ i ] : [ uniforms[ i ] ];

			for ( let j = 0, jl = uniformArray.length; j < jl; j ++ ) {

				const uniform = uniformArray[ j ];

				const values = Array.isArray( uniform.value ) ? uniform.value : [ uniform.value ];

				for ( let k = 0, kl = values.length; k < kl; k ++ ) {

					const value = values[ k ];

					const info = getUniformSize( value );

					const chunkOffset = offset % chunkSize; // offset in the current chunk
					const chunkPadding = chunkOffset % info.boundary; // required padding to match boundary
					const chunkStart = chunkOffset + chunkPadding; // the start position in the current chunk for the data

					offset += chunkPadding;

					// Check for chunk overflow
					if ( chunkStart !== 0 && ( chunkSize - chunkStart ) < info.storage ) {

						// Add padding and adjust offset
						offset += ( chunkSize - chunkStart );

					}

					// the following two properties will be used for partial buffer updates
					uniform.__data = new Float32Array( info.storage / Float32Array.BYTES_PER_ELEMENT );
					uniform.__offset = offset;

					// Update the global offset
					offset += info.storage;

				}

			}

		}

		// ensure correct final padding

		const chunkOffset = offset % chunkSize;

		if ( chunkOffset > 0 ) offset += ( chunkSize - chunkOffset );

		//

		uniformsGroup.__size = offset;
		uniformsGroup.__cache = {};

		return this;

	}

	function getUniformSize( value ) {

		const info = {
			boundary: 0, // bytes
			storage: 0 // bytes
		};

		// determine sizes according to STD140

		if ( typeof value === 'number' || typeof value === 'boolean' ) {

			// float/int/bool

			info.boundary = 4;
			info.storage = 4;

		} else if ( value.isVector2 ) {

			// vec2

			info.boundary = 8;
			info.storage = 8;

		} else if ( value.isVector3 || value.isColor ) {

			// vec3

			info.boundary = 16;
			info.storage = 12; // evil: vec3 must start on a 16-byte boundary but it only consumes 12 bytes

		} else if ( value.isVector4 ) {

			// vec4

			info.boundary = 16;
			info.storage = 16;

		} else if ( value.isMatrix3 ) {

			// mat3 (in STD140 a 3x3 matrix is represented as 3x4)

			info.boundary = 48;
			info.storage = 48;

		} else if ( value.isMatrix4 ) {

			// mat4

			info.boundary = 64;
			info.storage = 64;

		} else if ( value.isTexture ) {

			console.warn( 'THREE.WebGLRenderer: Texture samplers can not be part of an uniforms group.' );

		} else {

			console.warn( 'THREE.WebGLRenderer: Unsupported uniform value type.', value );

		}

		return info;

	}

	function onUniformsGroupsDispose( event ) {

		const uniformsGroup = event.target;

		uniformsGroup.removeEventListener( 'dispose', onUniformsGroupsDispose );

		const index = allocatedBindingPoints.indexOf( uniformsGroup.__bindingPointIndex );
		allocatedBindingPoints.splice( index, 1 );

		gl.deleteBuffer( buffers[ uniformsGroup.id ] );

		delete buffers[ uniformsGroup.id ];
		delete updateList[ uniformsGroup.id ];

	}

	function dispose() {

		for ( const id in buffers ) {

			gl.deleteBuffer( buffers[ id ] );

		}

		allocatedBindingPoints = [];
		buffers = {};
		updateList = {};

	}

	return {

		bind: bind,
		update: update,

		dispose: dispose

	};

}
```
</details>

### `bind(uniformsGroup: any, program: any): void`

**Parameters:**

- **`uniformsGroup`** `any`
- **`program`** `any`

**Returns:** `void`

**Calls:**

- `state.uniformBlockBinding`

<details><summary>Code</summary>

```typescript
function bind( uniformsGroup, program ) {

		const webglProgram = program.program;
		state.uniformBlockBinding( uniformsGroup, webglProgram );

	}
```
</details>

### `update(uniformsGroup: any, program: any): void`

**Parameters:**

- **`uniformsGroup`** `any`
- **`program`** `any`

**Returns:** `void`

**Calls:**

- `prepareUniformsGroup`
- `createBuffer`
- `uniformsGroup.addEventListener`
- `state.updateUBOMapping`
- `updateBufferData`

**Internal Comments:**
```
// ensure to update the binding points/block indices mapping for this program (x2)
// update UBO once per frame (x2)
```

<details><summary>Code</summary>

```typescript
function update( uniformsGroup, program ) {

		let buffer = buffers[ uniformsGroup.id ];

		if ( buffer === undefined ) {

			prepareUniformsGroup( uniformsGroup );

			buffer = createBuffer( uniformsGroup );
			buffers[ uniformsGroup.id ] = buffer;

			uniformsGroup.addEventListener( 'dispose', onUniformsGroupsDispose );

		}

		// ensure to update the binding points/block indices mapping for this program

		const webglProgram = program.program;
		state.updateUBOMapping( uniformsGroup, webglProgram );

		// update UBO once per frame

		const frame = info.render.frame;

		if ( updateList[ uniformsGroup.id ] !== frame ) {

			updateBufferData( uniformsGroup );

			updateList[ uniformsGroup.id ] = frame;

		}

	}
```
</details>

### `createBuffer(uniformsGroup: any): any`

**Parameters:**

- **`uniformsGroup`** `any`

**Returns:** `any`

**Calls:**

- `allocateBindingPointIndex`
- `gl.createBuffer`
- `gl.bindBuffer`
- `gl.bufferData`
- `gl.bindBufferBase`

**Internal Comments:**
```
// the setup of an UBO is independent of a particular shader program but global (x2)
```

<details><summary>Code</summary>

```typescript
function createBuffer( uniformsGroup ) {

		// the setup of an UBO is independent of a particular shader program but global

		const bindingPointIndex = allocateBindingPointIndex();
		uniformsGroup.__bindingPointIndex = bindingPointIndex;

		const buffer = gl.createBuffer();
		const size = uniformsGroup.__size;
		const usage = uniformsGroup.usage;

		gl.bindBuffer( gl.UNIFORM_BUFFER, buffer );
		gl.bufferData( gl.UNIFORM_BUFFER, size, usage );
		gl.bindBuffer( gl.UNIFORM_BUFFER, null );
		gl.bindBufferBase( gl.UNIFORM_BUFFER, bindingPointIndex, buffer );

		return buffer;

	}
```
</details>

### `allocateBindingPointIndex(): number`

**Returns:** `number`

**Calls:**

- `allocatedBindingPoints.indexOf`
- `allocatedBindingPoints.push`
- `console.error`

<details><summary>Code</summary>

```typescript
function allocateBindingPointIndex() {

		for ( let i = 0; i < maxBindingPoints; i ++ ) {

			if ( allocatedBindingPoints.indexOf( i ) === - 1 ) {

				allocatedBindingPoints.push( i );
				return i;

			}

		}

		console.error( 'THREE.WebGLRenderer: Maximum number of simultaneously usable uniforms groups reached.' );

		return 0;

	}
```
</details>

### `updateBufferData(uniformsGroup: any): void`

**Parameters:**

- **`uniformsGroup`** `any`

**Returns:** `void`

**Calls:**

- `gl.bindBuffer`
- `Array.isArray`
- `hasUniformChanged`
- `getUniformSize`
- `gl.bufferSubData`
- `value.toArray`

**Internal Comments:**
```
// TODO add integer and struct support
// manually converting 3x3 to 3x4 (x5)
```

<details><summary>Code</summary>

```typescript
function updateBufferData( uniformsGroup ) {

		const buffer = buffers[ uniformsGroup.id ];
		const uniforms = uniformsGroup.uniforms;
		const cache = uniformsGroup.__cache;

		gl.bindBuffer( gl.UNIFORM_BUFFER, buffer );

		for ( let i = 0, il = uniforms.length; i < il; i ++ ) {

			const uniformArray = Array.isArray( uniforms[ i ] ) ? uniforms[ i ] : [ uniforms[ i ] ];

			for ( let j = 0, jl = uniformArray.length; j < jl; j ++ ) {

				const uniform = uniformArray[ j ];

				if ( hasUniformChanged( uniform, i, j, cache ) === true ) {

					const offset = uniform.__offset;

					const values = Array.isArray( uniform.value ) ? uniform.value : [ uniform.value ];

					let arrayOffset = 0;

					for ( let k = 0; k < values.length; k ++ ) {

						const value = values[ k ];

						const info = getUniformSize( value );

						// TODO add integer and struct support
						if ( typeof value === 'number' || typeof value === 'boolean' ) {

							uniform.__data[ 0 ] = value;
							gl.bufferSubData( gl.UNIFORM_BUFFER, offset + arrayOffset, uniform.__data );

						} else if ( value.isMatrix3 ) {

							// manually converting 3x3 to 3x4

							uniform.__data[ 0 ] = value.elements[ 0 ];
							uniform.__data[ 1 ] = value.elements[ 1 ];
							uniform.__data[ 2 ] = value.elements[ 2 ];
							uniform.__data[ 3 ] = 0;
							uniform.__data[ 4 ] = value.elements[ 3 ];
							uniform.__data[ 5 ] = value.elements[ 4 ];
							uniform.__data[ 6 ] = value.elements[ 5 ];
							uniform.__data[ 7 ] = 0;
							uniform.__data[ 8 ] = value.elements[ 6 ];
							uniform.__data[ 9 ] = value.elements[ 7 ];
							uniform.__data[ 10 ] = value.elements[ 8 ];
							uniform.__data[ 11 ] = 0;

						} else {

							value.toArray( uniform.__data, arrayOffset );

							arrayOffset += info.storage / Float32Array.BYTES_PER_ELEMENT;

						}

					}

					gl.bufferSubData( gl.UNIFORM_BUFFER, offset, uniform.__data );

				}

			}

		}

		gl.bindBuffer( gl.UNIFORM_BUFFER, null );

	}
```
</details>

### `hasUniformChanged(uniform: any, index: any, indexArray: any, cache: any): boolean`

**Parameters:**

- **`uniform`** `any`
- **`index`** `any`
- **`indexArray`** `any`
- **`cache`** `any`

**Returns:** `boolean`

**Calls:**

- `value.clone`
- `cachedObject.equals`
- `cachedObject.copy`

**Internal Comments:**
```
// cache entry does not exist so far
// compare current value with cached entry
```

<details><summary>Code</summary>

```typescript
function hasUniformChanged( uniform, index, indexArray, cache ) {

		const value = uniform.value;
		const indexString = index + '_' + indexArray;

		if ( cache[ indexString ] === undefined ) {

			// cache entry does not exist so far

			if ( typeof value === 'number' || typeof value === 'boolean' ) {

				cache[ indexString ] = value;

			} else {

				cache[ indexString ] = value.clone();

			}

			return true;

		} else {

			const cachedObject = cache[ indexString ];

			// compare current value with cached entry

			if ( typeof value === 'number' || typeof value === 'boolean' ) {

				if ( cachedObject !== value ) {

					cache[ indexString ] = value;
					return true;

				}

			} else {

				if ( cachedObject.equals( value ) === false ) {

					cachedObject.copy( value );
					return true;

				}

			}

		}

		return false;

	}
```
</details>

### `prepareUniformsGroup(uniformsGroup: any): any`

**Parameters:**

- **`uniformsGroup`** `any`

**Returns:** `any`

**Calls:**

- `Array.isArray`
- `getUniformSize`

**Internal Comments:**
```
// determine total buffer size according to the STD140 layout (x2)
// Hint: STD140 is the only supported layout in WebGL 2 (x2)
// Check for chunk overflow
// Add padding and adjust offset (x3)
// the following two properties will be used for partial buffer updates (x4)
// Update the global offset (x3)
// ensure correct final padding (x2)
// (x4)
```

<details><summary>Code</summary>

```typescript
function prepareUniformsGroup( uniformsGroup ) {

		// determine total buffer size according to the STD140 layout
		// Hint: STD140 is the only supported layout in WebGL 2

		const uniforms = uniformsGroup.uniforms;

		let offset = 0; // global buffer offset in bytes
		const chunkSize = 16; // size of a chunk in bytes

		for ( let i = 0, l = uniforms.length; i < l; i ++ ) {

			const uniformArray = Array.isArray( uniforms[ i ] ) ? uniforms[ i ] : [ uniforms[ i ] ];

			for ( let j = 0, jl = uniformArray.length; j < jl; j ++ ) {

				const uniform = uniformArray[ j ];

				const values = Array.isArray( uniform.value ) ? uniform.value : [ uniform.value ];

				for ( let k = 0, kl = values.length; k < kl; k ++ ) {

					const value = values[ k ];

					const info = getUniformSize( value );

					const chunkOffset = offset % chunkSize; // offset in the current chunk
					const chunkPadding = chunkOffset % info.boundary; // required padding to match boundary
					const chunkStart = chunkOffset + chunkPadding; // the start position in the current chunk for the data

					offset += chunkPadding;

					// Check for chunk overflow
					if ( chunkStart !== 0 && ( chunkSize - chunkStart ) < info.storage ) {

						// Add padding and adjust offset
						offset += ( chunkSize - chunkStart );

					}

					// the following two properties will be used for partial buffer updates
					uniform.__data = new Float32Array( info.storage / Float32Array.BYTES_PER_ELEMENT );
					uniform.__offset = offset;

					// Update the global offset
					offset += info.storage;

				}

			}

		}

		// ensure correct final padding

		const chunkOffset = offset % chunkSize;

		if ( chunkOffset > 0 ) offset += ( chunkSize - chunkOffset );

		//

		uniformsGroup.__size = offset;
		uniformsGroup.__cache = {};

		return this;

	}
```
</details>

### `getUniformSize(value: any): { boundary: number; storage: number; }`

**Parameters:**

- **`value`** `any`

**Returns:** `{ boundary: number; storage: number; }`

**Calls:**

- `console.warn`

**Internal Comments:**
```
// determine sizes according to STD140
// float/int/bool (x4)
// vec2 (x4)
// vec3 (x4)
// vec4 (x4)
// mat3 (in STD140 a 3x3 matrix is represented as 3x4) (x4)
// mat4 (x4)
```

<details><summary>Code</summary>

```typescript
function getUniformSize( value ) {

		const info = {
			boundary: 0, // bytes
			storage: 0 // bytes
		};

		// determine sizes according to STD140

		if ( typeof value === 'number' || typeof value === 'boolean' ) {

			// float/int/bool

			info.boundary = 4;
			info.storage = 4;

		} else if ( value.isVector2 ) {

			// vec2

			info.boundary = 8;
			info.storage = 8;

		} else if ( value.isVector3 || value.isColor ) {

			// vec3

			info.boundary = 16;
			info.storage = 12; // evil: vec3 must start on a 16-byte boundary but it only consumes 12 bytes

		} else if ( value.isVector4 ) {

			// vec4

			info.boundary = 16;
			info.storage = 16;

		} else if ( value.isMatrix3 ) {

			// mat3 (in STD140 a 3x3 matrix is represented as 3x4)

			info.boundary = 48;
			info.storage = 48;

		} else if ( value.isMatrix4 ) {

			// mat4

			info.boundary = 64;
			info.storage = 64;

		} else if ( value.isTexture ) {

			console.warn( 'THREE.WebGLRenderer: Texture samplers can not be part of an uniforms group.' );

		} else {

			console.warn( 'THREE.WebGLRenderer: Unsupported uniform value type.', value );

		}

		return info;

	}
```
</details>

### `onUniformsGroupsDispose(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `uniformsGroup.removeEventListener`
- `allocatedBindingPoints.indexOf`
- `allocatedBindingPoints.splice`
- `gl.deleteBuffer`

<details><summary>Code</summary>

```typescript
function onUniformsGroupsDispose( event ) {

		const uniformsGroup = event.target;

		uniformsGroup.removeEventListener( 'dispose', onUniformsGroupsDispose );

		const index = allocatedBindingPoints.indexOf( uniformsGroup.__bindingPointIndex );
		allocatedBindingPoints.splice( index, 1 );

		gl.deleteBuffer( buffers[ uniformsGroup.id ] );

		delete buffers[ uniformsGroup.id ];
		delete updateList[ uniformsGroup.id ];

	}
```
</details>

### `dispose(): void`

**Returns:** `void`

**Calls:**

- `gl.deleteBuffer`

<details><summary>Code</summary>

```typescript
function dispose() {

		for ( const id in buffers ) {

			gl.deleteBuffer( buffers[ id ] );

		}

		allocatedBindingPoints = [];
		buffers = {};
		updateList = {};

	}
```
</details>


---