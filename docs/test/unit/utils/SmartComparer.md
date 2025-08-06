[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SmartComparer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/utils/SmartComparer.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `message` | `any` | let/var | `*not shown*` | ✗ |
| `tag` | `any` | let/var | `isObject( value ) ? Object.prototype.toString.call( value ) : ''` | ✗ |
| `type` | `"string" \| "number" \| "bigint" \| "...` | let/var | `typeof value` | ✗ |
| `N1` | `number` | let/var | `val1.length` | ✗ |
| `N2` | `any` | let/var | `val2.length` | ✗ |
| `hadDifference` | `boolean` | let/var | `false` | ✗ |
| `key` | `string` | let/var | `keys1[ i ]` | ✗ |
| `prop1` | `any` | let/var | `val1[ key ]` | ✗ |
| `prop2` | `any` | let/var | `val2[ key ]` | ✗ |


---

## Functions

### `SmartComparer(): { areEqual: (val1: any, val2: any) => boolean; getDiagnostic: () => any; }`

**Returns:** `{ areEqual: (val1: any, val2: any) => boolean; getDiagnostic: () => any; }`

**Calls:**

- `makeFail`
- `isFunction`
- `compareArrays`
- `val1.equals`
- `compareObjects`
- `isObject`
- `Object.prototype.toString.call`
- `Array.isArray`
- `areEqual`
- `addContext`
- `Object.keys`
- `keys2.indexOf`
- `keys1.indexOf`

**Internal Comments:**
```
// Diagnostic message, when comparison fails. (x2)
// val1 - first value to compare (typically the actual value)
// val2 - other value to compare (typically the expected value)
// Values are strictly equal.
// Null or undefined values.
/* jshint eqnull:true */
// Both null / undefined.
// Don't compare functions.
// Array comparison. (x2)
// Has custom equality comparer.
// Object comparison. (x2)
// if (JSON.stringify( val1 ) == JSON.stringify( val2 ) ) return true;
// Object differs (unknown reason).
// The use of `Object#toString` avoids issues with the `typeof` operator (x2)
// in Safari 8 which returns 'object' for typed array constructors, and (x2)
// PhantomJS 1.9 which returns 'function' for `NodeList` instances. (x2)
// Avoid a V8 JIT bug in Chrome 19-20. (x2)
// See https://code.google.com/p/v8/issues/detail?id=2291 for more details. (x2)
// Compare type. (x2)
// Not arrays. Continue.
// Compare length. (x2)
// Compare content at each index.
// Arrays are equal.
// Not objects. Continue.
// Compare keys. (x2)
// Keys are the same. For each key, compare content until a difference is found. (x2)
// Compare property content. (x2)
// In case of failure, an message should already be set.
// Add context to low level message.
// There should already be a validation message. Add more context to it. (x3)
```

<details><summary>Code</summary>

```typescript
function SmartComparer() {

	'use strict';

	// Diagnostic message, when comparison fails.
	let message;

	return {

		areEqual: areEqual,

		getDiagnostic: function () {

			return message;

		}

	};

	// val1 - first value to compare (typically the actual value)
	// val2 - other value to compare (typically the expected value)
	function areEqual( val1, val2 ) {

		// Values are strictly equal.
		if ( val1 === val2 ) return true;

		// Null or undefined values.
		/* jshint eqnull:true */
		if ( val1 == null || val2 == null ) {

			if ( val1 != val2 ) {

				return makeFail( 'One value is undefined or null', val1, val2 );

			}

			// Both null / undefined.
			return true;

		}

		// Don't compare functions.
		if ( isFunction( val1 ) && isFunction( val2 ) ) return true;

		// Array comparison.
		const arrCmp = compareArrays( val1, val2 );
		if ( arrCmp !== undefined ) return arrCmp;

		// Has custom equality comparer.
		if ( val1.equals ) {

			if ( val1.equals( val2 ) ) return true;

			return makeFail( 'Comparison with .equals method returned false' );

		}

		// Object comparison.
		const objCmp = compareObjects( val1, val2 );
		if ( objCmp !== undefined ) return objCmp;

		// if (JSON.stringify( val1 ) == JSON.stringify( val2 ) ) return true;

		// Object differs (unknown reason).
		return makeFail( 'Values differ', val1, val2 );

	}

	function isFunction( value ) {

		// The use of `Object#toString` avoids issues with the `typeof` operator
		// in Safari 8 which returns 'object' for typed array constructors, and
		// PhantomJS 1.9 which returns 'function' for `NodeList` instances.
		const tag = isObject( value ) ? Object.prototype.toString.call( value ) : '';

		return tag == '[object Function]' || tag == '[object GeneratorFunction]';

	}

	function isObject( value ) {

		// Avoid a V8 JIT bug in Chrome 19-20.
		// See https://code.google.com/p/v8/issues/detail?id=2291 for more details.
		const type = typeof value;

		return !! value && ( type == 'object' || type == 'function' );

	}

	function compareArrays( val1, val2 ) {

		const isArr1 = Array.isArray( val1 );
		const isArr2 = Array.isArray( val2 );

		// Compare type.
		if ( isArr1 !== isArr2 ) return makeFail( 'Values are not both arrays' );

		// Not arrays. Continue.
		if ( ! isArr1 ) return undefined;

		// Compare length.
		const N1 = val1.length;
		const N2 = val2.length;
		if ( N1 !== val2.length ) return makeFail( 'Array length differs', N1, N2 );

		// Compare content at each index.
		for ( let i = 0; i < N1; i ++ ) {

			const cmp = areEqual( val1[ i ], val2[ i ] );
			if ( ! cmp )	return addContext( 'array index "' + i + '"' );

		}

		// Arrays are equal.
		return true;

	}

	function compareObjects( val1, val2 ) {

		const isObj1 = isObject( val1 );
		const isObj2 = isObject( val2 );

		// Compare type.
		if ( isObj1 !== isObj2 ) return makeFail( 'Values are not both objects' );

		// Not objects. Continue.
		if ( ! isObj1 ) return undefined;

		// Compare keys.
		const keys1 = Object.keys( val1 );
		const keys2 = Object.keys( val2 );

		for ( let i = 0, l = keys1.length; i < l; i ++ ) {

			if ( keys2.indexOf( keys1[ i ] ) < 0 ) {

				return makeFail( 'Property "' + keys1[ i ] + '" is unexpected.' );

			}

		}

		for ( let i = 0, l = keys2.length; i < l; i ++ ) {

			if ( keys1.indexOf( keys2[ i ] ) < 0 ) {

				return makeFail( 'Property "' + keys2[ i ] + '" is missing.' );

			}

		}

		// Keys are the same. For each key, compare content until a difference is found.
		let hadDifference = false;

		for ( let i = 0, l = keys1.length; i < l; i ++ ) {

			const key = keys1[ i ];

			if ( key === 'uuid' || key === 'id' ) {

				continue;

			}

			const prop1 = val1[ key ];
			const prop2 = val2[ key ];

			// Compare property content.
			const eq = areEqual( prop1, prop2 );

			// In case of failure, an message should already be set.
			// Add context to low level message.
			if ( ! eq ) {

				addContext( 'property "' + key + '"' );
				hadDifference = true;

			}

		}

		return ! hadDifference;

	}

	function makeFail( msg, val1, val2 ) {

		message = msg;
		if ( arguments.length > 1 ) message += ' (' + val1 + ' vs ' + val2 + ')';

		return false;

	}

	function addContext( msg ) {

		// There should already be a validation message. Add more context to it.
		message = message || 'Error';
		message += ', at ' + msg;

		return false;

	}

}
```
</details>

### `getDiagnostic(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

			return message;

		}
```
</details>

### `getDiagnostic(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

			return message;

		}
```
</details>

### `areEqual(val1: any, val2: any): boolean`

**Parameters:**

- **`val1`** `any`
- **`val2`** `any`

**Returns:** `boolean`

**Calls:**

- `makeFail`
- `isFunction`
- `compareArrays`
- `val1.equals`
- `compareObjects`

**Internal Comments:**
```
// Values are strictly equal.
// Null or undefined values.
/* jshint eqnull:true */
// Both null / undefined.
// Don't compare functions.
// Array comparison. (x2)
// Has custom equality comparer.
// Object comparison. (x2)
// if (JSON.stringify( val1 ) == JSON.stringify( val2 ) ) return true;
// Object differs (unknown reason).
```

<details><summary>Code</summary>

```typescript
function areEqual( val1, val2 ) {

		// Values are strictly equal.
		if ( val1 === val2 ) return true;

		// Null or undefined values.
		/* jshint eqnull:true */
		if ( val1 == null || val2 == null ) {

			if ( val1 != val2 ) {

				return makeFail( 'One value is undefined or null', val1, val2 );

			}

			// Both null / undefined.
			return true;

		}

		// Don't compare functions.
		if ( isFunction( val1 ) && isFunction( val2 ) ) return true;

		// Array comparison.
		const arrCmp = compareArrays( val1, val2 );
		if ( arrCmp !== undefined ) return arrCmp;

		// Has custom equality comparer.
		if ( val1.equals ) {

			if ( val1.equals( val2 ) ) return true;

			return makeFail( 'Comparison with .equals method returned false' );

		}

		// Object comparison.
		const objCmp = compareObjects( val1, val2 );
		if ( objCmp !== undefined ) return objCmp;

		// if (JSON.stringify( val1 ) == JSON.stringify( val2 ) ) return true;

		// Object differs (unknown reason).
		return makeFail( 'Values differ', val1, val2 );

	}
```
</details>

### `isFunction(value: any): boolean`

**Parameters:**

- **`value`** `any`

**Returns:** `boolean`

**Calls:**

- `isObject`
- `Object.prototype.toString.call`

**Internal Comments:**
```
// The use of `Object#toString` avoids issues with the `typeof` operator (x2)
// in Safari 8 which returns 'object' for typed array constructors, and (x2)
// PhantomJS 1.9 which returns 'function' for `NodeList` instances. (x2)
```

<details><summary>Code</summary>

```typescript
function isFunction( value ) {

		// The use of `Object#toString` avoids issues with the `typeof` operator
		// in Safari 8 which returns 'object' for typed array constructors, and
		// PhantomJS 1.9 which returns 'function' for `NodeList` instances.
		const tag = isObject( value ) ? Object.prototype.toString.call( value ) : '';

		return tag == '[object Function]' || tag == '[object GeneratorFunction]';

	}
```
</details>

### `isObject(value: any): boolean`

**Parameters:**

- **`value`** `any`

**Returns:** `boolean`

**Internal Comments:**
```
// Avoid a V8 JIT bug in Chrome 19-20. (x2)
// See https://code.google.com/p/v8/issues/detail?id=2291 for more details. (x2)
```

<details><summary>Code</summary>

```typescript
function isObject( value ) {

		// Avoid a V8 JIT bug in Chrome 19-20.
		// See https://code.google.com/p/v8/issues/detail?id=2291 for more details.
		const type = typeof value;

		return !! value && ( type == 'object' || type == 'function' );

	}
```
</details>

### `compareArrays(val1: any, val2: any): boolean`

**Parameters:**

- **`val1`** `any`
- **`val2`** `any`

**Returns:** `boolean`

**Calls:**

- `Array.isArray`
- `makeFail`
- `areEqual`
- `addContext`

**Internal Comments:**
```
// Compare type.
// Not arrays. Continue.
// Compare length. (x2)
// Compare content at each index.
// Arrays are equal.
```

<details><summary>Code</summary>

```typescript
function compareArrays( val1, val2 ) {

		const isArr1 = Array.isArray( val1 );
		const isArr2 = Array.isArray( val2 );

		// Compare type.
		if ( isArr1 !== isArr2 ) return makeFail( 'Values are not both arrays' );

		// Not arrays. Continue.
		if ( ! isArr1 ) return undefined;

		// Compare length.
		const N1 = val1.length;
		const N2 = val2.length;
		if ( N1 !== val2.length ) return makeFail( 'Array length differs', N1, N2 );

		// Compare content at each index.
		for ( let i = 0; i < N1; i ++ ) {

			const cmp = areEqual( val1[ i ], val2[ i ] );
			if ( ! cmp )	return addContext( 'array index "' + i + '"' );

		}

		// Arrays are equal.
		return true;

	}
```
</details>

### `compareObjects(val1: any, val2: any): boolean`

**Parameters:**

- **`val1`** `any`
- **`val2`** `any`

**Returns:** `boolean`

**Calls:**

- `isObject`
- `makeFail`
- `Object.keys`
- `keys2.indexOf`
- `keys1.indexOf`
- `areEqual`
- `addContext`

**Internal Comments:**
```
// Compare type.
// Not objects. Continue.
// Compare keys. (x2)
// Keys are the same. For each key, compare content until a difference is found. (x2)
// Compare property content. (x2)
// In case of failure, an message should already be set.
// Add context to low level message.
```

<details><summary>Code</summary>

```typescript
function compareObjects( val1, val2 ) {

		const isObj1 = isObject( val1 );
		const isObj2 = isObject( val2 );

		// Compare type.
		if ( isObj1 !== isObj2 ) return makeFail( 'Values are not both objects' );

		// Not objects. Continue.
		if ( ! isObj1 ) return undefined;

		// Compare keys.
		const keys1 = Object.keys( val1 );
		const keys2 = Object.keys( val2 );

		for ( let i = 0, l = keys1.length; i < l; i ++ ) {

			if ( keys2.indexOf( keys1[ i ] ) < 0 ) {

				return makeFail( 'Property "' + keys1[ i ] + '" is unexpected.' );

			}

		}

		for ( let i = 0, l = keys2.length; i < l; i ++ ) {

			if ( keys1.indexOf( keys2[ i ] ) < 0 ) {

				return makeFail( 'Property "' + keys2[ i ] + '" is missing.' );

			}

		}

		// Keys are the same. For each key, compare content until a difference is found.
		let hadDifference = false;

		for ( let i = 0, l = keys1.length; i < l; i ++ ) {

			const key = keys1[ i ];

			if ( key === 'uuid' || key === 'id' ) {

				continue;

			}

			const prop1 = val1[ key ];
			const prop2 = val2[ key ];

			// Compare property content.
			const eq = areEqual( prop1, prop2 );

			// In case of failure, an message should already be set.
			// Add context to low level message.
			if ( ! eq ) {

				addContext( 'property "' + key + '"' );
				hadDifference = true;

			}

		}

		return ! hadDifference;

	}
```
</details>

### `makeFail(msg: any, val1: any, val2: any): boolean`

**Parameters:**

- **`msg`** `any`
- **`val1`** `any`
- **`val2`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function makeFail( msg, val1, val2 ) {

		message = msg;
		if ( arguments.length > 1 ) message += ' (' + val1 + ' vs ' + val2 + ')';

		return false;

	}
```
</details>

### `addContext(msg: any): boolean`

**Parameters:**

- **`msg`** `any`

**Returns:** `boolean`

**Internal Comments:**
```
// There should already be a validation message. Add more context to it. (x3)
```

<details><summary>Code</summary>

```typescript
function addContext( msg ) {

		// There should already be a validation message. Add more context to it.
		message = message || 'Error';
		message += ', at ' + msg;

		return false;

	}
```
</details>


---