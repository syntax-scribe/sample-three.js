[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NodeUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 16 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 12 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/nodes/core/NodeUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `../../math/Color.js` |
| `Matrix2` | `../../math/Matrix2.js` |
| `Matrix3` | `../../math/Matrix3.js` |
| `Matrix4` | `../../math/Matrix4.js` |
| `Vector2` | `../../math/Vector2.js` |
| `Vector3` | `../../math/Vector3.js` |
| `Vector4` | `../../math/Vector4.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `h1` | `number` | let/var | `0xdeadbeef ^ seed` | ✗ |
| `h2` | `number` | let/var | `0x41c6ce57 ^ seed` | ✗ |
| `values` | `any[]` | let/var | `[]` | ✗ |
| `object` | `any` | let/var | `node[ property ]` | ✗ |
| `child` | `any` | let/var | `object[ i ]` | ✗ |
| `child` | `any` | let/var | `object[ subProperty ]` | ✗ |
| `typeFromLength` | `Map<number, string>` | let/var | `new Map( [ [ 1, 'float' ], [ 2, 'vec2' ], [ 3, 'vec3' ], [ 4, 'vec4' ], [ 9, ...` | ✗ |
| `dataFromObject` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `typeOf` | `"string" \| "number" \| "bigint" \| "...` | let/var | `typeof value` | ✗ |
| `last4` | `string` | let/var | `type ? type.slice( - 4 ) : undefined` | ✗ |
| `chars` | `string` | let/var | `''` | ✗ |
| `array` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( arrayBuffer )` | ✗ |


---

## Functions

### `cyrb53(value: any, seed: number): number`

**Parameters:**

- **`value`** `any`
- **`seed`** `number`

**Returns:** `number`

**Calls:**

- `Math.imul`
- `value.charCodeAt`

<details><summary>Code</summary>

```typescript
function cyrb53( value, seed = 0 ) {

	let h1 = 0xdeadbeef ^ seed, h2 = 0x41c6ce57 ^ seed;

	if ( value instanceof Array ) {

		for ( let i = 0, val; i < value.length; i ++ ) {

			val = value[ i ];
			h1 = Math.imul( h1 ^ val, 2654435761 );
			h2 = Math.imul( h2 ^ val, 1597334677 );

		}

	} else {

		for ( let i = 0, ch; i < value.length; i ++ ) {

			ch = value.charCodeAt( i );
			h1 = Math.imul( h1 ^ ch, 2654435761 );
			h2 = Math.imul( h2 ^ ch, 1597334677 );

		}

	}

	h1 = Math.imul( h1 ^ ( h1 >>> 16 ), 2246822507 );
	h1 ^= Math.imul( h2 ^ ( h2 >>> 13 ), 3266489909 );
	h2 = Math.imul( h2 ^ ( h2 >>> 16 ), 2246822507 );
	h2 ^= Math.imul( h1 ^ ( h1 >>> 13 ), 3266489909 );

	return 4294967296 * ( 2097151 & h2 ) + ( h1 >>> 0 );

}
```
</details>

### `hashString(str: string): number`

**Parameters:**

- **`str`** `string`

**Returns:** `number`

**Calls:**

- `cyrb53`

<details><summary>Code</summary>

```typescript
( str ) => cyrb53( str )
```
</details>

### `hashArray(array: number[]): number`

**Parameters:**

- **`array`** `number[]`

**Returns:** `number`

**Calls:**

- `cyrb53`

<details><summary>Code</summary>

```typescript
( array ) => cyrb53( array )
```
</details>

### `hash(params: number[]): number`

**Parameters:**

- **`params`** `number[]`

**Returns:** `number`

**Calls:**

- `cyrb53`

<details><summary>Code</summary>

```typescript
( ...params ) => cyrb53( params )
```
</details>

### `getCacheKey(object: any, force: boolean): number`

**JSDoc:**
```typescript
/**
 * Computes a cache key for the given node.
 *
 * @method
 * @param {Object|Node} object - The object to be hashed.
 * @param {boolean} [force=false] - Whether to force a cache key computation or not.
 * @return {number} The hash.
 */
```

**Parameters:**

- **`object`** `any`
- **`force`** `boolean`

**Returns:** `number`

**Calls:**

- `values.push`
- `object.getSelf`
- `getNodeChildren`
- `cyrb53`
- `property.slice`
- `childNode.getCacheKey`

<details><summary>Code</summary>

```typescript
export function getCacheKey( object, force = false ) {

	const values = [];

	if ( object.isNode === true ) {

		values.push( object.id );
		object = object.getSelf();

	}

	for ( const { property, childNode } of getNodeChildren( object ) ) {

		values.push( cyrb53( property.slice( 0, - 4 ) ), childNode.getCacheKey( force ) );

	}

	return cyrb53( values );

}
```
</details>

### `getNodeChildren(node: any, toJSON: boolean): Generator<{ property: string; index: number; childNode: any; } | { property: string; childNode: any; index?: undefined; } | { property: string; index: string; childNode: any; }, void, unknown>`

**JSDoc:**
```typescript
/**
 * This generator function can be used to iterate over the node children
 * of the given object.
 *
 * @generator
 * @param {Object} node - The object to be hashed.
 * @param {boolean} [toJSON=false] - Whether to return JSON or not.
 * @yields {Object} A result node holding the property, index (if available) and the child node.
 */
```

**Parameters:**

- **`node`** `any`
- **`toJSON`** `boolean`

**Returns:** `Generator<{ property: string; index: number; childNode: any; } | { property: string; childNode: any; index?: undefined; } | { property: string; index: string; childNode: any; }, void, unknown>`

**Calls:**

- `property.startsWith`
- `Array.isArray`
- `Object.getPrototypeOf`
- `subProperty.startsWith`

**Internal Comments:**
```
// Ignore private properties. (x2)
```

<details><summary>Code</summary>

```typescript
export function* getNodeChildren( node, toJSON = false ) {

	for ( const property in node ) {

		// Ignore private properties.
		if ( property.startsWith( '_' ) === true ) continue;

		const object = node[ property ];

		if ( Array.isArray( object ) === true ) {

			for ( let i = 0; i < object.length; i ++ ) {

				const child = object[ i ];

				if ( child && ( child.isNode === true || toJSON && typeof child.toJSON === 'function' ) ) {

					yield { property, index: i, childNode: child };

				}

			}

		} else if ( object && object.isNode === true ) {

			yield { property, childNode: object };

		} else if ( object && Object.getPrototypeOf( object ) === Object.prototype ) {

			for ( const subProperty in object ) {

				// Ignore private properties.
				if ( subProperty.startsWith( '_' ) === true ) continue;

				const child = object[ subProperty ];

				if ( child && ( child.isNode === true || toJSON && typeof child.toJSON === 'function' ) ) {

					yield { property, index: subProperty, childNode: child };

				}

			}

		}

	}

}
```
</details>

### `getTypeFromLength(length: number): string`

**JSDoc:**
```typescript
/**
 * Returns the data type for the given the length.
 *
 * @method
 * @param {number} length - The length.
 * @return {string} The data type.
 */
```

**Parameters:**

- **`length`** `number`

**Returns:** `string`

**Calls:**

- `typeFromLength.get`

<details><summary>Code</summary>

```typescript
export function getTypeFromLength( length ) {

	return typeFromLength.get( length );

}
```
</details>

### `getTypedArrayFromType(type: string): TypedArray`

**JSDoc:**
```typescript
/**
 * Returns the typed array for the given data type.
 *
 * @method
 * @param {string} type - The data type.
 * @return {TypedArray} The typed array.
 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `TypedArray`

**Calls:**

- `/[iu]?vec\d/.test`
- `type.startsWith`
- `/mat\d/.test`
- `/float/.test`
- `/uint/.test`
- `/int/.test`

**Internal Comments:**
```
// Handle component type for vectors and matrices
// Handle int vectors
// Handle uint vectors
// Default to float vectors
// Handle matrices (always float)
// Basic types
```

<details><summary>Code</summary>

```typescript
export function getTypedArrayFromType( type ) {

	// Handle component type for vectors and matrices
	if ( /[iu]?vec\d/.test( type ) ) {

		// Handle int vectors
		if ( type.startsWith( 'ivec' ) ) return Int32Array;
		// Handle uint vectors
		if ( type.startsWith( 'uvec' ) ) return Uint32Array;
		// Default to float vectors
		return Float32Array;

	}

	// Handle matrices (always float)
	if ( /mat\d/.test( type ) ) return Float32Array;

	// Basic types
	if ( /float/.test( type ) ) return Float32Array;
	if ( /uint/.test( type ) ) return Uint32Array;
	if ( /int/.test( type ) ) return Int32Array;

	throw new Error( `THREE.NodeUtils: Unsupported type: ${type}` );

}
```
</details>

### `getLengthFromType(type: string): number`

**JSDoc:**
```typescript
/**
 * Returns the length for the given data type.
 *
 * @method
 * @param {string} type - The data type.
 * @return {number} The length.
 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `number`

**Calls:**

- `/float|int|uint/.test`
- `/vec2/.test`
- `/vec3/.test`
- `/vec4/.test`
- `/mat2/.test`
- `/mat3/.test`
- `/mat4/.test`
- `console.error`

<details><summary>Code</summary>

```typescript
export function getLengthFromType( type ) {

	if ( /float|int|uint/.test( type ) ) return 1;
	if ( /vec2/.test( type ) ) return 2;
	if ( /vec3/.test( type ) ) return 3;
	if ( /vec4/.test( type ) ) return 4;
	if ( /mat2/.test( type ) ) return 4;
	if ( /mat3/.test( type ) ) return 9;
	if ( /mat4/.test( type ) ) return 16;

	console.error( 'THREE.TSL: Unsupported type:', type );

}
```
</details>

### `getMemoryLengthFromType(type: string): number`

**JSDoc:**
```typescript
/**
 * Returns the gpu memory length for the given data type.
 *
 * @method
 * @param {string} type - The data type.
 * @return {number} The length.
 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `number`

**Calls:**

- `/float|int|uint/.test`
- `/vec2/.test`
- `/vec3/.test`
- `/vec4/.test`
- `/mat2/.test`
- `/mat3/.test`
- `/mat4/.test`
- `console.error`

<details><summary>Code</summary>

```typescript
export function getMemoryLengthFromType( type ) {

	if ( /float|int|uint/.test( type ) ) return 1;
	if ( /vec2/.test( type ) ) return 2;
	if ( /vec3/.test( type ) ) return 3;
	if ( /vec4/.test( type ) ) return 4;
	if ( /mat2/.test( type ) ) return 4;
	if ( /mat3/.test( type ) ) return 12;
	if ( /mat4/.test( type ) ) return 16;

	console.error( 'THREE.TSL: Unsupported type:', type );

}
```
</details>

### `getByteBoundaryFromType(type: string): number`

**JSDoc:**
```typescript
/**
 * Returns the byte boundary for the given data type.
 *
 * @method
 * @param {string} type - The data type.
 * @return {number} The byte boundary.
 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `number`

**Calls:**

- `/float|int|uint/.test`
- `/vec2/.test`
- `/vec3/.test`
- `/vec4/.test`
- `/mat2/.test`
- `/mat3/.test`
- `/mat4/.test`
- `console.error`

<details><summary>Code</summary>

```typescript
export function getByteBoundaryFromType( type ) {

	if ( /float|int|uint/.test( type ) ) return 4;
	if ( /vec2/.test( type ) ) return 8;
	if ( /vec3/.test( type ) ) return 16;
	if ( /vec4/.test( type ) ) return 16;
	if ( /mat2/.test( type ) ) return 8;
	if ( /mat3/.test( type ) ) return 48;
	if ( /mat4/.test( type ) ) return 64;

	console.error( 'THREE.TSL: Unsupported type:', type );

}
```
</details>

### `getValueType(value: any): string`

**JSDoc:**
```typescript
/**
 * Returns the data type for the given value.
 *
 * @method
 * @param {any} value - The value.
 * @return {?string} The data type.
 */
```

**Parameters:**

- **`value`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
export function getValueType( value ) {

	if ( value === undefined || value === null ) return null;

	const typeOf = typeof value;

	if ( value.isNode === true ) {

		return 'node';

	} else if ( typeOf === 'number' ) {

		return 'float';

	} else if ( typeOf === 'boolean' ) {

		return 'bool';

	} else if ( typeOf === 'string' ) {

		return 'string';

	} else if ( typeOf === 'function' ) {

		return 'shader';

	} else if ( value.isVector2 === true ) {

		return 'vec2';

	} else if ( value.isVector3 === true ) {

		return 'vec3';

	} else if ( value.isVector4 === true ) {

		return 'vec4';

	} else if ( value.isMatrix2 === true ) {

		return 'mat2';

	} else if ( value.isMatrix3 === true ) {

		return 'mat3';

	} else if ( value.isMatrix4 === true ) {

		return 'mat4';

	} else if ( value.isColor === true ) {

		return 'color';

	} else if ( value instanceof ArrayBuffer ) {

		return 'ArrayBuffer';

	}

	return null;

}
```
</details>

### `getValueFromType(type: string, params: any[]): any`

**JSDoc:**
```typescript
/**
 * Returns the value/object for the given data type and parameters.
 *
 * @method
 * @param {string} type - The given type.
 * @param {...any} params - A parameter list.
 * @return {any} The value/object.
 */
```

**Parameters:**

- **`type`** `string`
- **`params`** `any[]`

**Returns:** `any`

**Calls:**

- `type.slice`
- `base64ToArrayBuffer`

<details><summary>Code</summary>

```typescript
export function getValueFromType( type, ...params ) {

	const last4 = type ? type.slice( - 4 ) : undefined;

	if ( params.length === 1 ) { // ensure same behaviour as in NodeBuilder.format()

		if ( last4 === 'vec2' ) params = [ params[ 0 ], params[ 0 ] ];
		else if ( last4 === 'vec3' ) params = [ params[ 0 ], params[ 0 ], params[ 0 ] ];
		else if ( last4 === 'vec4' ) params = [ params[ 0 ], params[ 0 ], params[ 0 ], params[ 0 ] ];

	}

	if ( type === 'color' ) {

		return new Color( ...params );

	} else if ( last4 === 'vec2' ) {

		return new Vector2( ...params );

	} else if ( last4 === 'vec3' ) {

		return new Vector3( ...params );

	} else if ( last4 === 'vec4' ) {

		return new Vector4( ...params );

	} else if ( last4 === 'mat2' ) {

		return new Matrix2( ...params );

	} else if ( last4 === 'mat3' ) {

		return new Matrix3( ...params );

	} else if ( last4 === 'mat4' ) {

		return new Matrix4( ...params );

	} else if ( type === 'bool' ) {

		return params[ 0 ] || false;

	} else if ( ( type === 'float' ) || ( type === 'int' ) || ( type === 'uint' ) ) {

		return params[ 0 ] || 0;

	} else if ( type === 'string' ) {

		return params[ 0 ] || '';

	} else if ( type === 'ArrayBuffer' ) {

		return base64ToArrayBuffer( params[ 0 ] );

	}

	return null;

}
```
</details>

### `getDataFromObject(object: any): any`

**JSDoc:**
```typescript
/**
 * Gets the object data that can be shared between different rendering steps.
 *
 * @param {Object} object - The object to get the data for.
 * @return {Object} The object data.
 */
```

**Parameters:**

- **`object`** `any`

**Returns:** `any`

**Calls:**

- `dataFromObject.get`
- `dataFromObject.set`

<details><summary>Code</summary>

```typescript
export function getDataFromObject( object ) {

	let data = dataFromObject.get( object );

	if ( data === undefined ) {

		data = {};
		dataFromObject.set( object, data );

	}

	return data;

}
```
</details>

### `arrayBufferToBase64(arrayBuffer: ArrayBuffer): string`

**JSDoc:**
```typescript
/**
 * Converts the given array buffer to a Base64 string.
 *
 * @method
 * @param {ArrayBuffer} arrayBuffer - The array buffer.
 * @return {string} The Base64 string.
 */
```

**Parameters:**

- **`arrayBuffer`** `ArrayBuffer`

**Returns:** `string`

**Calls:**

- `String.fromCharCode`
- `btoa`

<details><summary>Code</summary>

```typescript
export function arrayBufferToBase64( arrayBuffer ) {

	let chars = '';

	const array = new Uint8Array( arrayBuffer );

	for ( let i = 0; i < array.length; i ++ ) {

		chars += String.fromCharCode( array[ i ] );

	}

	return btoa( chars );

}
```
</details>

### `base64ToArrayBuffer(base64: string): ArrayBuffer`

**JSDoc:**
```typescript
/**
 * Converts the given Base64 string to an array buffer.
 *
 * @method
 * @param {string} base64 - The Base64 string.
 * @return {ArrayBuffer} The array buffer.
 */
```

**Parameters:**

- **`base64`** `string`

**Returns:** `ArrayBuffer`

**Calls:**

- `Uint8Array.from`
- `atob`
- `c.charCodeAt`

<details><summary>Code</summary>

```typescript
export function base64ToArrayBuffer( base64 ) {

	return Uint8Array.from( atob( base64 ), c => c.charCodeAt( 0 ) ).buffer;

}
```
</details>


---