[⬅️ Back to Table of Contents](../../index.md)

# 📄 `DataUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 14 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/extras/DataUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `clamp` | `../math/MathUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `buffer` | `ArrayBuffer` | let/var | `new ArrayBuffer( 4 )` | ✗ |
| `floatView` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( buffer )` | ✗ |
| `uint32View` | `Uint32Array<ArrayBuffer>` | let/var | `new Uint32Array( buffer )` | ✗ |
| `baseTable` | `Uint32Array<ArrayBuffer>` | let/var | `new Uint32Array( 512 )` | ✗ |
| `shiftTable` | `Uint32Array<ArrayBuffer>` | let/var | `new Uint32Array( 512 )` | ✗ |
| `e` | `number` | let/var | `i - 127` | ✗ |
| `mantissaTable` | `Uint32Array<ArrayBuffer>` | let/var | `new Uint32Array( 2048 )` | ✗ |
| `exponentTable` | `Uint32Array<ArrayBuffer>` | let/var | `new Uint32Array( 64 )` | ✗ |
| `offsetTable` | `Uint32Array<ArrayBuffer>` | let/var | `new Uint32Array( 64 )` | ✗ |
| `m` | `number` | let/var | `i << 13` | ✗ |
| `e` | `number` | let/var | `0` | ✗ |
| `f` | `number` | let/var | `_tables.uint32View[ 0 ]` | ✗ |
| `e` | `number` | let/var | `( f >> 23 ) & 0x1ff` | ✗ |
| `m` | `number` | let/var | `val >> 10` | ✗ |


---

## Functions

### `_generateTables(): { floatView: Float32Array<ArrayBuffer>; uint32View: Uint32Array<ArrayBuffer>; baseTable: Uint32Array<ArrayBuffer>; shiftTable: Uint32Array<...>; mantissaTable: Uint32Array<...>; exponentTable: Uint32Array<...>; offsetTable: Uint32Array<...>; }`

**Returns:** `{ floatView: Float32Array<ArrayBuffer>; uint32View: Uint32Array<ArrayBuffer>; baseTable: Uint32Array<ArrayBuffer>; shiftTable: Uint32Array<...>; mantissaTable: Uint32Array<...>; exponentTable: Uint32Array<...>; offsetTable: Uint32Array<...>; }`

**Internal Comments:**
```
// float32 to float16 helpers (x2)
// very small number (0, -0)
// float16 to float32 helpers (x2)
// normalized
```

<details><summary>Code</summary>

```typescript
function _generateTables() {

	// float32 to float16 helpers

	const buffer = new ArrayBuffer( 4 );
	const floatView = new Float32Array( buffer );
	const uint32View = new Uint32Array( buffer );

	const baseTable = new Uint32Array( 512 );
	const shiftTable = new Uint32Array( 512 );

	for ( let i = 0; i < 256; ++ i ) {

		const e = i - 127;

		// very small number (0, -0)

		if ( e < - 27 ) {

			baseTable[ i ] = 0x0000;
			baseTable[ i | 0x100 ] = 0x8000;
			shiftTable[ i ] = 24;
			shiftTable[ i | 0x100 ] = 24;

			// small number (denorm)

		} else if ( e < - 14 ) {

			baseTable[ i ] = 0x0400 >> ( - e - 14 );
			baseTable[ i | 0x100 ] = ( 0x0400 >> ( - e - 14 ) ) | 0x8000;
			shiftTable[ i ] = - e - 1;
			shiftTable[ i | 0x100 ] = - e - 1;

			// normal number

		} else if ( e <= 15 ) {

			baseTable[ i ] = ( e + 15 ) << 10;
			baseTable[ i | 0x100 ] = ( ( e + 15 ) << 10 ) | 0x8000;
			shiftTable[ i ] = 13;
			shiftTable[ i | 0x100 ] = 13;

			// large number (Infinity, -Infinity)

		} else if ( e < 128 ) {

			baseTable[ i ] = 0x7c00;
			baseTable[ i | 0x100 ] = 0xfc00;
			shiftTable[ i ] = 24;
			shiftTable[ i | 0x100 ] = 24;

			// stay (NaN, Infinity, -Infinity)

		} else {

			baseTable[ i ] = 0x7c00;
			baseTable[ i | 0x100 ] = 0xfc00;
			shiftTable[ i ] = 13;
			shiftTable[ i | 0x100 ] = 13;

		}

	}

	// float16 to float32 helpers

	const mantissaTable = new Uint32Array( 2048 );
	const exponentTable = new Uint32Array( 64 );
	const offsetTable = new Uint32Array( 64 );

	for ( let i = 1; i < 1024; ++ i ) {

		let m = i << 13; // zero pad mantissa bits
		let e = 0; // zero exponent

		// normalized
		while ( ( m & 0x00800000 ) === 0 ) {

			m <<= 1;
			e -= 0x00800000; // decrement exponent

		}

		m &= ~ 0x00800000; // clear leading 1 bit
		e += 0x38800000; // adjust bias

		mantissaTable[ i ] = m | e;

	}

	for ( let i = 1024; i < 2048; ++ i ) {

		mantissaTable[ i ] = 0x38000000 + ( ( i - 1024 ) << 13 );

	}

	for ( let i = 1; i < 31; ++ i ) {

		exponentTable[ i ] = i << 23;

	}

	exponentTable[ 31 ] = 0x47800000;
	exponentTable[ 32 ] = 0x80000000;

	for ( let i = 33; i < 63; ++ i ) {

		exponentTable[ i ] = 0x80000000 + ( ( i - 32 ) << 23 );

	}

	exponentTable[ 63 ] = 0xc7800000;

	for ( let i = 1; i < 64; ++ i ) {

		if ( i !== 32 ) {

			offsetTable[ i ] = 1024;

		}

	}

	return {
		floatView: floatView,
		uint32View: uint32View,
		baseTable: baseTable,
		shiftTable: shiftTable,
		mantissaTable: mantissaTable,
		exponentTable: exponentTable,
		offsetTable: offsetTable
	};

}
```
</details>

### `toHalfFloat(val: number): number`

**JSDoc:**
```typescript
/**
 * Returns a half precision floating point value (FP16) from the given single
 * precision floating point value (FP32).
 *
 * @param {number} val - A single precision floating point value.
 * @return {number} The FP16 value.
 */
```

**Parameters:**

- **`val`** `number`

**Returns:** `number`

**Calls:**

- `Math.abs`
- `console.warn`
- `clamp (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
function toHalfFloat( val ) {

	if ( Math.abs( val ) > 65504 ) console.warn( 'THREE.DataUtils.toHalfFloat(): Value out of range.' );

	val = clamp( val, - 65504, 65504 );

	_tables.floatView[ 0 ] = val;
	const f = _tables.uint32View[ 0 ];
	const e = ( f >> 23 ) & 0x1ff;
	return _tables.baseTable[ e ] + ( ( f & 0x007fffff ) >> _tables.shiftTable[ e ] );

}
```
</details>

### `fromHalfFloat(val: number): number`

**JSDoc:**
```typescript
/**
 * Returns a single precision floating point value (FP32) from the given half
 * precision floating point value (FP16).
 *
 * @param {number} val - A half precision floating point value.
 * @return {number} The FP32 value.
 */
```

**Parameters:**

- **`val`** `number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function fromHalfFloat( val ) {

	const m = val >> 10;
	_tables.uint32View[ 0 ] = _tables.mantissaTable[ _tables.offsetTable[ m ] + ( val & 0x3ff ) ] + _tables.exponentTable[ m ];
	return _tables.floatView[ 0 ];

}
```
</details>

### `DataUtils.toHalfFloat(val: number): number`

**JSDoc:**
```typescript
/**
	 * Returns a half precision floating point value (FP16) from the given single
	 * precision floating point value (FP32).
	 *
	 * @param {number} val - A single precision floating point value.
	 * @return {number} The FP16 value.
	 */
```

**Parameters:**

- **`val`** `number`

**Returns:** `number`

**Calls:**

- `toHalfFloat`

<details><summary>Code</summary>

```typescript
static toHalfFloat( val ) {

		return toHalfFloat( val );

	}
```
</details>

### `DataUtils.fromHalfFloat(val: number): number`

**JSDoc:**
```typescript
/**
	 * Returns a single precision floating point value (FP32) from the given half
	 * precision floating point value (FP16).
	 *
	 * @param {number} val - A half precision floating point value.
	 * @return {number} The FP32 value.
	 */
```

**Parameters:**

- **`val`** `number`

**Returns:** `number`

**Calls:**

- `fromHalfFloat`

<details><summary>Code</summary>

```typescript
static fromHalfFloat( val ) {

		return fromHalfFloat( val );

	}
```
</details>


---

## Classes

### `DataUtils`

<details><summary>Class Code</summary>

```ts
class DataUtils {

	/**
	 * Returns a half precision floating point value (FP16) from the given single
	 * precision floating point value (FP32).
	 *
	 * @param {number} val - A single precision floating point value.
	 * @return {number} The FP16 value.
	 */
	static toHalfFloat( val ) {

		return toHalfFloat( val );

	}

	/**
	 * Returns a single precision floating point value (FP32) from the given half
	 * precision floating point value (FP16).
	 *
	 * @param {number} val - A half precision floating point value.
	 * @return {number} The FP32 value.
	 */
	static fromHalfFloat( val ) {

		return fromHalfFloat( val );

	}

}
```
</details>

#### Methods

##### `toHalfFloat(val: number): number`

<details><summary>Code</summary>

```ts
static toHalfFloat( val ) {

		return toHalfFloat( val );

	}
```
</details>

##### `fromHalfFloat(val: number): number`

<details><summary>Code</summary>

```ts
static fromHalfFloat( val ) {

		return fromHalfFloat( val );

	}
```
</details>


---