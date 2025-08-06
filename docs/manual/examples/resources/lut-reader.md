[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `lut-reader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 12 |
| 📊 Variables & Constants | 28 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/examples/resources/lut-reader.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `strings` | `any[]` | let/var | `[]` | ✗ |
| `quoteType` | `any` | let/var | `*not shown*` | ✗ |
| `escape` | `any` | let/var | `*not shown*` | ✗ |
| `s` | `any[]` | let/var | `[]` | ✗ |
| `c` | `any` | let/var | `str[ i ]` | ✗ |
| `startWhitespaceRE` | `RegExp` | let/var | `/^\s/` | ✗ |
| `intRE` | `RegExp` | let/var | `/^\d+$/` | ✗ |
| `quotesRE` | `RegExp` | let/var | `/^".*"$/` | ✗ |
| `data` | `any[]` | let/var | `[]` | ✗ |
| `lut` | `{ name: string; type: string; size: n...` | let/var | `{ name: 'unknown', type: '1D', size: 0, data, min: [ 0, 0, 0 ], max: [ 1, 1, ...` | ✗ |
| `lineNdx` | `number` | let/var | `2` | ✗ |
| `line` | `any` | let/var | `lines[ lineNdx ]` | ✗ |
| `data` | `any[]` | let/var | `[]` | ✗ |
| `lut` | `{ name: string; type: string; size: n...` | let/var | `{ name: 'unknown', type: '1D', size: 0, data, min: [ 0, 0, 0 ], max: [ 1, 1, ...` | ✗ |
| `line` | `any` | let/var | `hashNdx >= 0 ? origLine.substring( 0, hashNdx ) : origLine` | ✗ |
| `src` | `any` | let/var | `lut.data` | ✗ |
| `u` | `number` | let/var | `i / lut.size * lut.data.length` | ✗ |
| `i0` | `number` | let/var | `( u \| 0 ) * 3` | ✗ |
| `i1` | `number` | let/var | `i0 + 3` | ✗ |
| `t` | `number` | let/var | `u % 1` | ✗ |
| `data` | `any[]` | let/var | `[]` | ✗ |
| `parsers` | `{ cube: (str: any) => { name: string;...` | let/var | `{ 'cube': parseCUBE, 'csp': parseCSP, }` | ✗ |
| `parser` | `any` | let/var | `parsers[ format.toLowerCase() ]` | ✗ |
| `src` | `any` | let/var | `lut.data` | ✗ |
| `data` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( size * size * size * 4 )` | ✗ |
| `sx` | `number` | let/var | `dx` | ✗ |
| `sy` | `number` | let/var | `dz` | ✗ |
| `sz` | `number` | let/var | `dy` | ✗ |


---

## Functions

### `splitOnSpaceHandleQuotesWithEscapes(str: any, splits: string): string[]`

**Parameters:**

- **`str`** `any`
- **`splits`** `string`

**Returns:** `string[]`

**Calls:**

- `s.push`
- `strings.push`
- `s.join`
- `splits.indexOf`

<details><summary>Code</summary>

```typescript
function splitOnSpaceHandleQuotesWithEscapes( str, splits = ' \t\n\r' ) {

	const strings = [];
	let quoteType;
	let escape;
	let s = [];
	for ( let i = 0; i < str.length; ++ i ) {

		const c = str[ i ];
		if ( escape ) {

			escape = false;
			s.push( c );

		} else {

			if ( quoteType ) { // we're inside quotes

				if ( c === quoteType ) {

					quoteType = undefined;
					strings.push( s.join( '' ) );
					s = [];

				} else if ( c === '\\' ) {

					escape = true;

				} else {

					s.push( c );

				}

			} else { // we're not in quotes

				if ( splits.indexOf( c ) >= 0 ) {

					if ( s.length ) {

						strings.push( s.join( '' ) );
						s = [];

					}

				} else if ( c === '"' || c === '\'' ) {

					if ( s.length ) { // its in th middle of a word

						s.push( c );

					} else {

						quoteType = c;

					}

				} else {

					s.push( c );

				}

			}

		}

	}

	if ( s.length || strings.length === 0 ) {

		strings.push( s.join( '' ) );

	}

	return strings;

}
```
</details>

### `isNum(s: any): boolean`

**Parameters:**

- **`s`** `any`

**Returns:** `boolean`

**Calls:**

- `intRE.test`

<details><summary>Code</summary>

```typescript
s => intRE.test( s )
```
</details>

### `trimQuotes(s: any): any`

**Parameters:**

- **`s`** `any`

**Returns:** `any`

**Calls:**

- `quotesRE.test`
- `s.slice`

<details><summary>Code</summary>

```typescript
function trimQuotes( s ) {

	return quotesRE.test( s ) ? s.slice( 1, - 1 ) : s;

}
```
</details>

### `splitToNumbers(s: any): any`

**Parameters:**

- **`s`** `any`

**Returns:** `any`

**Calls:**

- `s.split( ' ' ).map`

<details><summary>Code</summary>

```typescript
s => s.split( ' ' ).map( parseFloat )
```
</details>

### `parseCSP(str: any): { name: string; type: string; size: number; data: any[]; min: number[]; max: number[]; }`

**Parameters:**

- **`str`** `any`

**Returns:** `{ name: string; type: string; size: number; data: any[]; min: number[]; max: number[]; }`

**Calls:**

- `str.split( '\n' ).map( s => s.trim() ).filter`
- `startWhitespaceRE.test`
- `isNum`
- `line.startsWith`
- `trimQuotes`
- `line.slice( 6 ).trim`
- `splitToNumbers`
- `data.push`

**Internal Comments:**
```
// check header (x4)
// skip meta (read to first number) (x2)
// read ranges
// read sizes (x2)
// read data
```

<details><summary>Code</summary>

```typescript
export function parseCSP( str ) {

	const data = [];
	const lut = {
		name: 'unknown',
		type: '1D',
		size: 0,
		data,
		min: [ 0, 0, 0 ],
		max: [ 1, 1, 1 ],
	};

	const lines = str.split( '\n' ).map( s => s.trim() ).filter( s => s.length > 0 && ! startWhitespaceRE.test( s ) );

	// check header
	lut.type = lines[ 1 ];
	if ( lines[ 0 ] !== 'CSPLUTV100' ||
       ( lut.type !== '1D' && lut.type !== '3D' ) ) {

		throw new Error( 'not CSP' );

	}

	// skip meta (read to first number)
	let lineNdx = 2;
	for ( ; lineNdx < lines.length; ++ lineNdx ) {

		const line = lines[ lineNdx ];
		if ( isNum( line ) ) {

			break;

		}

		if ( line.startsWith( 'TITLE ' ) ) {

			lut.name = trimQuotes( line.slice( 6 ).trim() );

		}

	}

	// read ranges
	for ( let i = 0; i < 3; ++ i ) {

		++ lineNdx;
		const input = splitToNumbers( lines[ lineNdx ++ ] );
		const output = splitToNumbers( lines[ lineNdx ++ ] );
		if ( input.length !== 2 || output.length !== 2 ||
        input[ 0 ] !== 0 || input[ 1 ] !== 1 ||
        output[ 0 ] !== 0 || output[ 1 ] !== 1 ) {

			throw new Error( 'mapped ranges not support' );

		}

	}

	// read sizes
	const sizes = splitToNumbers( lines[ lineNdx ++ ] );
	if ( sizes[ 0 ] !== sizes[ 1 ] || sizes[ 0 ] !== sizes[ 2 ] ) {

		throw new Error( 'only cubic sizes supported' );

	}

	lut.size = sizes[ 0 ];

	// read data
	for ( ; lineNdx < lines.length; ++ lineNdx ) {

		const parts = splitToNumbers( lines[ lineNdx ] );
		if ( parts.length !== 3 ) {

			throw new Error( 'malformed file' );

		}

		data.push( ...parts );

	}

	return lut;

}
```
</details>

### `parseCUBE(str: any): { name: string; type: string; size: number; data: any[]; min: number[]; max: number[]; }`

**Parameters:**

- **`str`** `any`

**Returns:** `{ name: string; type: string; size: number; data: any[]; min: number[]; max: number[]; }`

**Calls:**

- `str.split`
- `origLine.indexOf`
- `origLine.substring`
- `splitOnSpaceHandleQuotesWithEscapes`
- `parts[ 0 ].toUpperCase`
- `parseInt`
- `parts.slice( 1 ).map`
- `data.push`
- `parts.map`
- `Math.cbrt`

<details><summary>Code</summary>

```typescript
export function parseCUBE( str ) {

	const data = [];
	const lut = {
		name: 'unknown',
		type: '1D',
		size: 0,
		data,
		min: [ 0, 0, 0 ],
		max: [ 1, 1, 1 ],
	};

	const lines = str.split( '\n' );
	for ( const origLine of lines ) {

		const hashNdx = origLine.indexOf( '#' );
		const line = hashNdx >= 0 ? origLine.substring( 0, hashNdx ) : origLine;
		const parts = splitOnSpaceHandleQuotesWithEscapes( line );
		switch ( parts[ 0 ].toUpperCase() ) {

			case 'TITLE':
				lut.name = parts[ 1 ];
				break;
			case 'LUT_1D_SIZE':
				lut.size = parseInt( parts[ 1 ] );
				lut.type = '1D';
				break;
			case 'LUT_3D_SIZE':
				lut.size = parseInt( parts[ 1 ] );
				lut.type = '3D';
				break;
			case 'DOMAIN_MIN':
				lut.min = parts.slice( 1 ).map( parseFloat );
				break;
			case 'DOMAIN_MAX':
				lut.max = parts.slice( 1 ).map( parseFloat );
				break;
			default:
				if ( parts.length === 3 ) {

					data.push( ...parts.map( parseFloat ) );

				}

				break;

		}

	}

	if ( ! lut.size ) {

		lut.size = lut.type === '1D'
			? ( data.length / 3 )
			: Math.cbrt( data.length / 3 );

	}

	return lut;

}
```
</details>

### `lerp(a: any, b: any, t: any): any`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function lerp( a, b, t ) {

	return a + ( b - a ) * t;

}
```
</details>

### `lut1Dto3D(lut: any): any`

**Parameters:**

- **`lut`** `any`

**Returns:** `any`

**Calls:**

- `src.push`
- `lerp`
- `data.push`

<details><summary>Code</summary>

```typescript
function lut1Dto3D( lut ) {

	let src = lut.data;
	if ( src.length / 3 !== lut.size ) {

		src = [];
		for ( let i = 0; i < lut.size; ++ i ) {

			const u = i / lut.size * lut.data.length;
			const i0 = ( u | 0 ) * 3;
			const i1 = i0 + 3;
			const t = u % 1;
			src.push(
				lerp( lut.data[ i0 + 0 ], lut.data[ i1 + 0 ], t ),
				lerp( lut.data[ i0 + 0 ], lut.data[ i1 + 1 ], t ),
				lerp( lut.data[ i0 + 0 ], lut.data[ i1 + 2 ], t ),
			);

		}

	}

	const data = [];
	for ( let i = 0; i < lut.size * lut.size; ++ i ) {

		data.push( ...src );

	}

	return { ...lut, data };

}
```
</details>

### `parse(str: any, format: string): any`

**Parameters:**

- **`str`** `any`
- **`format`** `string`

**Returns:** `any`

**Calls:**

- `format.toLowerCase`
- `parser`

<details><summary>Code</summary>

```typescript
export function parse( str, format = 'cube' ) {

	const parser = parsers[ format.toLowerCase() ];
	if ( ! parser ) {

		throw new Error( `no parser for format: ${format}` );

	}

	return parser( str );

}
```
</details>

### `lutTo2D3Drgba8(lut: any): any`

**Parameters:**

- **`lut`** `any`

**Returns:** `any`

**Calls:**

- `lut1Dto3D`
- `min.map`
- `srcOffset`
- `dOffset`

<details><summary>Code</summary>

```typescript
export function lutTo2D3Drgba8( lut ) {

	if ( lut.type === '1D' ) {

		lut = lut1Dto3D( lut );

	}

	const { min, max, size } = lut;
	const range = min.map( ( min, ndx ) => {

		return max[ ndx ] - min;

	} );
	const src = lut.data;
	const data = new Uint8Array( size * size * size * 4 );
	const srcOffset = ( offX, offY, offZ ) => {

		return ( offX + offY * size + offZ * size * size ) * 3;

	};

	const dOffset = ( offX, offY, offZ ) => {

		return ( offX + offY * size + offZ * size * size ) * 4;

	};

	for ( let dz = 0; dz < size; ++ dz ) {

		for ( let dy = 0; dy < size; ++ dy ) {

			for ( let dx = 0; dx < size; ++ dx ) {

				const sx = dx;
				const sy = dz;
				const sz = dy;
				const sOff = srcOffset( sx, sy, sz );
				const dOff = dOffset( dx, dy, dz );
				data[ dOff + 0 ] = ( src[ sOff + 0 ] - min[ 0 ] ) / range[ 0 ] * 255;
				data[ dOff + 1 ] = ( src[ sOff + 1 ] - min[ 1 ] ) / range[ 1 ] * 255;
				data[ dOff + 2 ] = ( src[ sOff + 2 ] - min[ 2 ] ) / range[ 2 ] * 255;
				data[ dOff + 3 ] = 255;

			}

		}

	}

	return { ...lut, data };

}
```
</details>

### `srcOffset(offX: any, offY: any, offZ: any): number`

**Parameters:**

- **`offX`** `any`
- **`offY`** `any`
- **`offZ`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
( offX, offY, offZ ) => {

		return ( offX + offY * size + offZ * size * size ) * 3;

	}
```
</details>

### `dOffset(offX: any, offY: any, offZ: any): number`

**Parameters:**

- **`offX`** `any`
- **`offY`** `any`
- **`offZ`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
( offX, offY, offZ ) => {

		return ( offX + offY * size + offZ * size * size ) * 4;

	}
```
</details>


---