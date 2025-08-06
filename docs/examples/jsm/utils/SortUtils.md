[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SortUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 📊 Variables & Constants | 34 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/utils/SortUtils.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `POWER` | `3` | let/var | `3` | ✗ |
| `BIT_MAX` | `32` | let/var | `32` | ✗ |
| `BIN_BITS` | `number` | let/var | `1 << POWER` | ✗ |
| `BIN_SIZE` | `number` | let/var | `1 << BIN_BITS` | ✗ |
| `BIN_MAX` | `number` | let/var | `BIN_SIZE - 1` | ✗ |
| `ITERATIONS` | `number` | let/var | `BIT_MAX / BIN_BITS` | ✗ |
| `bins` | `any[]` | let/var | `new Array( ITERATIONS )` | ✗ |
| `bins_buffer` | `ArrayBuffer` | let/var | `new ArrayBuffer( ( ITERATIONS + 1 ) * BIN_SIZE * 4 )` | ✗ |
| `c` | `number` | let/var | `0` | ✗ |
| `len` | `number` | let/var | `arr.length` | ✗ |
| `options` | `any` | let/var | `opt \|\| {}` | ✗ |
| `aux` | `any` | let/var | `options.aux \|\| new arr.constructor( len )` | ✗ |
| `get` | `any` | let/var | `options.get \|\| defaultGet` | ✗ |
| `data` | `any[]` | let/var | `[ arr, aux ]` | ✗ |
| `compare` | `any` | let/var | `*not shown*` | ✗ |
| `accumulate` | `any` | let/var | `*not shown*` | ✗ |
| `recurse` | `any` | let/var | `*not shown*` | ✗ |
| `prev` | `number` | let/var | `0` | ✗ |
| `cur` | `any` | let/var | `cache[ j ]` | ✗ |
| `diff` | `number` | let/var | `cur - prev` | ✗ |
| `prev` | `number` | let/var | `0` | ✗ |
| `cur` | `any` | let/var | `cache[ j ]` | ✗ |
| `diff` | `number` | let/var | `cur - prev` | ✗ |
| `a` | `any` | let/var | `data[ depth & 1 ]` | ✗ |
| `b` | `any` | let/var | `data[ ( depth + 1 ) & 1 ]` | ✗ |
| `p` | `any` | let/var | `a[ j ]` | ✗ |
| `t` | `number` | let/var | `get( p ) >>> 0` | ✗ |
| `i` | `any` | let/var | `j` | ✗ |
| `a` | `any` | let/var | `data[ depth & 1 ]` | ✗ |
| `b` | `any` | let/var | `data[ ( depth + 1 ) & 1 ]` | ✗ |
| `shift` | `number` | let/var | `( 3 - depth ) << POWER` | ✗ |
| `end` | `any` | let/var | `start + len` | ✗ |
| `cache` | `any` | let/var | `bins[ depth ]` | ✗ |
| `bin` | `any` | let/var | `bins[ depth + 1 ]` | ✗ |


---

## Functions

### `defaultGet(el: any): any`

**Parameters:**

- **`el`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
( el ) => el
```
</details>

### `radixSort(arr: any[], opt: any): void`

**Parameters:**

- **`arr`** `any[]`
- **`opt`** `any`

**Returns:** `void`

**Calls:**

- `radixSortBlock`
- `insertionSortBlock`
- `get`
- `compare`
- `bin.fill`
- `accumulate`
- `cache.set`
- `recurse`

<details><summary>Code</summary>

```typescript
( arr, opt ) => {

	const len = arr.length;

	const options = opt || {};
	const aux = options.aux || new arr.constructor( len );
	const get = options.get || defaultGet;

	const data = [ arr, aux ];

	let compare, accumulate, recurse;

	if ( options.reversed ) {

		compare = ( a, b ) => a < b;
		accumulate = ( bin ) => {

			for ( let j = BIN_SIZE - 2; j >= 0; j -- )
				bin[ j ] += bin[ j + 1 ];

		};

		recurse = ( cache, depth, start ) => {

			let prev = 0;
			for ( let j = BIN_MAX; j >= 0; j -- ) {

				const cur = cache[ j ], diff = cur - prev;
				if ( diff != 0 ) {

					if ( diff > 32 )
						radixSortBlock( depth + 1, start + prev, diff );
					else
						insertionSortBlock( depth + 1, start + prev, diff );
					prev = cur;

				}

			}

		};

	} else {

		compare = ( a, b ) => a > b;
		accumulate = ( bin ) => {

			for ( let j = 1; j < BIN_SIZE; j ++ )
				bin[ j ] += bin[ j - 1 ];

		};

		recurse = ( cache, depth, start ) => {

			let prev = 0;
			for ( let j = 0; j < BIN_SIZE; j ++ ) {

				const cur = cache[ j ], diff = cur - prev;
				if ( diff != 0 ) {

					if ( diff > 32 )
						radixSortBlock( depth + 1, start + prev, diff );
					else
						insertionSortBlock( depth + 1, start + prev, diff );
					prev = cur;

				}

			}

		};

	}

	const insertionSortBlock = ( depth, start, len ) => {

		const a = data[ depth & 1 ];
		const b = data[ ( depth + 1 ) & 1 ];

		for ( let j = start + 1; j < start + len; j ++ ) {

			const p = a[ j ], t = get( p ) >>> 0;
			let i = j;
			while ( i > start ) {

				if ( compare( get( a[ i - 1 ] ) >>> 0, t ) )
					a[ i ] = a[ -- i ];
				else
					break;

			}

			a[ i ] = p;

		}

		if ( ( depth & 1 ) == 1 ) {

			for ( let i = start; i < start + len; i ++ )
				b[ i ] = a[ i ];

		}

	};

	const radixSortBlock = ( depth, start, len ) => {

		const a = data[ depth & 1 ];
		const b = data[ ( depth + 1 ) & 1 ];

		const shift = ( 3 - depth ) << POWER;
		const end = start + len;

		const cache = bins[ depth ];
		const bin = bins[ depth + 1 ];

		bin.fill( 0 );

		for ( let j = start; j < end; j ++ )
			bin[ ( get( a[ j ] ) >>> shift ) & BIN_MAX ] ++;

		accumulate( bin );

		cache.set( bin );

		for ( let j = end - 1; j >= start; j -- )
			b[ start + -- bin[ ( get( a[ j ] ) >>> shift ) & BIN_MAX ] ] = a[ j ];

		if ( depth == ITERATIONS - 1 ) return;

		recurse( cache, depth, start );

	};

	radixSortBlock( 0, 0, len );

}
```
</details>

### `insertionSortBlock(depth: any, start: any, len: any): void`

**Parameters:**

- **`depth`** `any`
- **`start`** `any`
- **`len`** `any`

**Returns:** `void`

**Calls:**

- `get`
- `compare`

<details><summary>Code</summary>

```typescript
( depth, start, len ) => {

		const a = data[ depth & 1 ];
		const b = data[ ( depth + 1 ) & 1 ];

		for ( let j = start + 1; j < start + len; j ++ ) {

			const p = a[ j ], t = get( p ) >>> 0;
			let i = j;
			while ( i > start ) {

				if ( compare( get( a[ i - 1 ] ) >>> 0, t ) )
					a[ i ] = a[ -- i ];
				else
					break;

			}

			a[ i ] = p;

		}

		if ( ( depth & 1 ) == 1 ) {

			for ( let i = start; i < start + len; i ++ )
				b[ i ] = a[ i ];

		}

	}
```
</details>

### `radixSortBlock(depth: any, start: any, len: any): void`

**Parameters:**

- **`depth`** `any`
- **`start`** `any`
- **`len`** `any`

**Returns:** `void`

**Calls:**

- `bin.fill`
- `get`
- `accumulate`
- `cache.set`
- `recurse`

<details><summary>Code</summary>

```typescript
( depth, start, len ) => {

		const a = data[ depth & 1 ];
		const b = data[ ( depth + 1 ) & 1 ];

		const shift = ( 3 - depth ) << POWER;
		const end = start + len;

		const cache = bins[ depth ];
		const bin = bins[ depth + 1 ];

		bin.fill( 0 );

		for ( let j = start; j < end; j ++ )
			bin[ ( get( a[ j ] ) >>> shift ) & BIN_MAX ] ++;

		accumulate( bin );

		cache.set( bin );

		for ( let j = end - 1; j >= start; j -- )
			b[ start + -- bin[ ( get( a[ j ] ) >>> shift ) & BIN_MAX ] ] = a[ j ];

		if ( depth == ITERATIONS - 1 ) return;

		recurse( cache, depth, start );

	}
```
</details>


---