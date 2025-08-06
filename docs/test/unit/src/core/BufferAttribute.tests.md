[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `BufferAttribute.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 13 |
| 📊 Variables & Constants | 60 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/core/BufferAttribute.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `Int8BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `Uint8BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `Uint8ClampedBufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `Int16BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `Uint16BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `Int32BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `Uint32BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `Float16BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `Float32BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `DynamicDrawUsage` | `../../../../src/constants.js` |
| `toHalfFloat` | `../../../../src/extras/DataUtils.js` |
| `fromHalfFloat` | `../../../../src/extras/DataUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `object` | `BufferAttribute` | let/var | `new BufferAttribute()` | ✗ |
| `attr` | `BufferAttribute` | let/var | `new BufferAttribute()` | ✗ |
| `attr` | `BufferAttribute` | let/var | `new BufferAttribute( new Float32Array( [ 1, 2, 3, 4, 5, 6 ] ), 3 )` | ✗ |
| `attr` | `BufferAttribute` | let/var | `new BufferAttribute( new Float32Array( [ 1, 2, 3, 4, 5, 6, 7, 8, 9 ] ), 3 )` | ✗ |
| `attr2` | `BufferAttribute` | let/var | `new BufferAttribute( new Float32Array( 9 ), 3 )` | ✗ |
| `i` | `TypedArray` | let/var | `attr.array` | ✗ |
| `i2` | `TypedArray` | let/var | `attr2.array` | ✗ |
| `f32a` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 5, 6, 7, 8 ] )` | ✗ |
| `a` | `BufferAttribute` | let/var | `new BufferAttribute( new Float32Array( [ 1, 2, 3, 4 ] ), 2, false )` | ✗ |
| `f32a` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 1, 2, 3, 4 ] )` | ✗ |
| `a` | `BufferAttribute` | let/var | `new BufferAttribute( f32a, 2, false )` | ✗ |
| `expected` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 9, 2, 8, 4 ] )` | ✗ |
| `f32a` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 1, 2, 3, 4, 5, 6, 7, 8 ] )` | ✗ |
| `a` | `BufferAttribute` | let/var | `new BufferAttribute( f32a, 4, false )` | ✗ |
| `expected` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 1, 2, - 3, - 4, - 5, - 6, 7, 8 ] )` | ✗ |
| `f32a` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 1, 2, 3, 4 ] )` | ✗ |
| `a` | `BufferAttribute` | let/var | `new BufferAttribute( f32a, 2, false )` | ✗ |
| `expected` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ - 1, - 2, 3, 4 ] )` | ✗ |
| `f32a` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 1, 2, 3, 4, 5, 6 ] )` | ✗ |
| `a` | `BufferAttribute` | let/var | `new BufferAttribute( f32a, 3, false )` | ✗ |
| `expected` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 1, 2, 3, - 4, - 5, - 6 ] )` | ✗ |
| `f32a` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 1, 2, 3, 4 ] )` | ✗ |
| `a` | `BufferAttribute` | let/var | `new BufferAttribute( f32a, 4, false )` | ✗ |
| `expected` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ - 1, - 2, - 3, - 4 ] )` | ✗ |
| `a` | `BufferAttribute` | let/var | `new BufferAttribute()` | ✗ |
| `attr` | `BufferAttribute` | let/var | `new BufferAttribute( new Float32Array( [ 1, 2, 3, 4, 0.12, - 12 ] ), 2 )` | ✗ |
| `attr` | `BufferAttribute` | let/var | `new BufferAttribute( new Float32Array( [ 1, 2, 3, 4, 5, 6 ] ), 3 )` | ✗ |
| `attr2` | `BufferAttribute` | let/var | `new BufferAttribute( new Float32Array( [ 1, 2, 3, 4, 5, 6 ] ), 3, true )` | ✗ |
| `object` | `Int8BufferAttribute` | let/var | `new Int8BufferAttribute()` | ✗ |
| `object` | `Int8BufferAttribute` | let/var | `new Int8BufferAttribute()` | ✗ |
| `object` | `Uint8BufferAttribute` | let/var | `new Uint8BufferAttribute()` | ✗ |
| `object` | `Uint8BufferAttribute` | let/var | `new Uint8BufferAttribute()` | ✗ |
| `object` | `Uint8ClampedBufferAttribute` | let/var | `new Uint8ClampedBufferAttribute()` | ✗ |
| `object` | `Uint8ClampedBufferAttribute` | let/var | `new Uint8ClampedBufferAttribute()` | ✗ |
| `object` | `Int16BufferAttribute` | let/var | `new Int16BufferAttribute()` | ✗ |
| `object` | `Int16BufferAttribute` | let/var | `new Int16BufferAttribute()` | ✗ |
| `object` | `Uint16BufferAttribute` | let/var | `new Uint16BufferAttribute()` | ✗ |
| `object` | `Uint16BufferAttribute` | let/var | `new Uint16BufferAttribute()` | ✗ |
| `object` | `Int32BufferAttribute` | let/var | `new Int32BufferAttribute()` | ✗ |
| `object` | `Int32BufferAttribute` | let/var | `new Int32BufferAttribute()` | ✗ |
| `object` | `Uint32BufferAttribute` | let/var | `new Uint32BufferAttribute()` | ✗ |
| `object` | `Uint32BufferAttribute` | let/var | `new Uint32BufferAttribute()` | ✗ |
| `object` | `Float16BufferAttribute` | let/var | `new Float16BufferAttribute()` | ✗ |
| `object` | `Float16BufferAttribute` | let/var | `new Float16BufferAttribute()` | ✗ |
| `f16Array` | `Uint16Array<any>` | let/var | `new Uint16Array( f32Array.length )` | ✗ |
| `f32Array` | `Float32Array<any>` | let/var | `new Float32Array( f16Array.length )` | ✗ |
| `f32a` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 1, 2, 3, 4, 5, 6, 7, 8 ] )` | ✗ |
| `a` | `Float16BufferAttribute` | let/var | `new Float16BufferAttribute( toHalfFloatArray( f32a ), 4, false )` | ✗ |
| `expected` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 1, 2, - 3, - 4, - 5, - 6, 7, 8 ] )` | ✗ |
| `f32a` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 1, 2, 3, 4 ] )` | ✗ |
| `a` | `Float16BufferAttribute` | let/var | `new Float16BufferAttribute( toHalfFloatArray( f32a ), 2, false )` | ✗ |
| `expected` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ - 1, - 2, 3, 4 ] )` | ✗ |
| `f32a` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 1, 2, 3, 4, 5, 6 ] )` | ✗ |
| `a` | `Float16BufferAttribute` | let/var | `new Float16BufferAttribute( toHalfFloatArray( f32a ), 3, false )` | ✗ |
| `expected` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 1, 2, 3, - 4, - 5, - 6 ] )` | ✗ |
| `f32a` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ 1, 2, 3, 4 ] )` | ✗ |
| `a` | `Float16BufferAttribute` | let/var | `new Float16BufferAttribute( toHalfFloatArray( f32a ), 4, false )` | ✗ |
| `expected` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ - 1, - 2, - 3, - 4 ] )` | ✗ |
| `object` | `Float32BufferAttribute` | let/var | `new Float32BufferAttribute()` | ✗ |
| `object` | `Float32BufferAttribute` | let/var | `new Float32BufferAttribute()` | ✗ |


---

## Functions

### `func(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () { }
```
</details>

### `toHalfFloatArray(f32Array: any): Uint16Array<any>`

**Parameters:**

- **`f32Array`** `any`

**Returns:** `Uint16Array<any>`

**Calls:**

- `toHalfFloat (from ../../../../src/extras/DataUtils.js)`

<details><summary>Code</summary>

```typescript
( f32Array ) => {

			const f16Array = new Uint16Array( f32Array.length );
			for ( let i = 0, n = f32Array.length; i < n; ++ i ) {

				f16Array[ i ] = toHalfFloat( f32Array[ i ] );

			}

			return f16Array;

		}
```
</details>

### `fromHalfFloatArray(f16Array: any): Float32Array<any>`

**Parameters:**

- **`f16Array`** `any`

**Returns:** `Float32Array<any>`

**Calls:**

- `fromHalfFloat (from ../../../../src/extras/DataUtils.js)`

<details><summary>Code</summary>

```typescript
( f16Array ) => {

			const f32Array = new Float32Array( f16Array.length );
			for ( let i = 0, n = f16Array.length; i < n; ++ i ) {

				f32Array[ i ] = fromHalfFloat( f16Array[ i ] );

			}

			return f32Array;

		}
```
</details>


---