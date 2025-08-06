[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `ogc-parser.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 14 |
| 📊 Variables & Constants | 22 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/resources/tools/geo-picking/ogc-parser.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `assert` | `{ strictEqual(actual: any, expected: ...` | let/var | `{ strictEqual( actual, expected, ...args ) { args = args \|\| []; if ( actual...` | ✗ |
| `flags` | `any` | let/var | `buf[ 3 ]` | ✗ |
| `flag_x` | `number` | let/var | `( flags >> 5 ) & 1` | ✗ |
| `flag_byteOrder` | `number` | let/var | `( flags >> 0 ) & 1` | ✗ |
| `flag_envelope` | `number` | let/var | `( flags >> 1 ) & 7` | ✗ |
| `envelopeSizes` | `number[]` | let/var | `[ 0, // 0: non 4, // 1: minx, maxx, miny, maxy 6, // 2: minx, maxx, miny, max...` | ✗ |
| `envelopeSize` | `number` | let/var | `envelopeSizes[ flag_envelope ]` | ✗ |
| `headerSize` | `8` | let/var | `8` | ✗ |
| `cursor` | `number` | let/var | `headerSize` | ✗ |
| `dataView` | `DataView<any>` | let/var | `new DataView( buf.buffer )` | ✗ |
| `littleEndian` | `any` | let/var | `*not shown*` | ✗ |
| `endianStack` | `any[]` | let/var | `[]` | ✗ |
| `envelope` | `any[]` | let/var | `[]` | ✗ |
| `primitives` | `any[]` | let/var | `[]` | ✗ |
| `points` | `any[]` | let/var | `[]` | ✗ |
| `rings` | `any[]` | let/var | `[]` | ✗ |
| `points` | `any[]` | let/var | `[]` | ✗ |
| `lineStrings` | `any[]` | let/var | `[]` | ✗ |
| `polygons` | `any[]` | let/var | `[]` | ✗ |
| `typeHandlers` | `((() => { type: string; point: number...` | let/var | `[ undefined, // 0 pointHandler, // 1 lineStringHandler, // 2 polygonHandler, ...` | ✗ |
| `end` | `any` | let/var | `buf.length` | ✗ |
| `handler` | `(() => { type: string; point: number[...` | let/var | `typeHandlers[ type ]` | ✗ |


---

## Functions

### `parse(buf: any): { envelope: number[]; primitives: ({ type: string; point: number[]; } | { type: string; polygons: number[][][]; } | { type: string; points: number[]; } | { type: string; rings: number[][]; } | { type: string; lineStrings: number[][]; })[]; }`

**Parameters:**

- **`buf`** `any`

**Returns:** `{ envelope: number[]; primitives: ({ type: string; point: number[]; } | { type: string; polygons: number[][][]; } | { type: string; points: number[]; } | { type: string; rings: number[][]; } | { type: string; lineStrings: number[][]; })[]; }`

**Calls:**

- `assert.strictEqual`
- `assert.notStrictEqual`
- `endianStack.push`
- `endianStack.pop`
- `dataView.getFloat64`
- `dataView.getInt8`
- `dataView.getUint32`
- `pushByteOrder`
- `envelope.push`
- `getDouble`
- `points.push`
- `rings.push`
- `getPoints`
- `getUint32`
- `getRings`
- `getInt8`
- `popByteOrder`
- `lineStrings.push`
- `polygons.push`
- `primitives.push`
- `handler`

**Internal Comments:**
```
// const flag_empty_geo = (flags >> 4) & 1;  // 1 = empty, 0 non-empty (x2)
/*
  const readBE = {
    getDouble() { const v = buf.readDoubleBE(cursor); cursor += 8 ; return v; },
    getFloat()  { const v = buf.readFloatBE(cursor);  cursor += 4 ; return v; },
    getInt8()   { const v = buf.readInt8(cursor);     cursor += 1 ; return v; },
    getUint8()  { const v = buf.readUInt8(cursor);    cursor += 1 ; return v; },
    getInt16()  { const v = buf.readInt16BE(cursor);  cursor += 2 ; return v; },
    getUint16() { const v = buf.readUInt16BE(cursor); cursor += 2 ; return v; },
    getInt32()  { const v = buf.readInt32BE(cursor);  cursor += 4 ; return v; },
    getUint32() { const v = buf.readUInt32BE(cursor); cursor += 4 ; return v; },
  };

  const readLE = {
    getDouble() { const v = buf.readDoubleLE(cursor); cursor += 8 ; return v; },
    getFloat()  { const v = buf.readFloatLE(cursor);  cursor += 4 ; return v; },
    getInt8()   { const v = buf.readInt8(cursor);     cursor += 1 ; return v; },
    getUint8()  { const v = buf.readUInt8(cursor);    cursor += 1 ; return v; },
    getInt16()  { const v = buf.readInt16LE(cursor);  cursor += 2 ; return v; },
    getUint16() { const v = buf.readUInt16LE(cursor); cursor += 2 ; return v; },
    getInt32()  { const v = buf.readInt32LE(cursor);  cursor += 4 ; return v; },
    getUint32() { const v = buf.readUInt32LE(cursor); cursor += 4 ; return v; },
  };
  */ (x2)
// const getFloat =  () => { const v = dataView.getFloat32(cursor, littleEndian); cursor += 4 ; return v; }; (x2)
// const getUint8 =  () => { const v = dataView.getUint8(cursor, littleEndian);   cursor += 1 ; return v; }; (x2)
// const getInt16 =  () => { const v = dataView.getInt16(cursor, littleEndian);   cursor += 2 ; return v; }; (x2)
// const getUint16 = () => { const v = dataView.getUint16(cursor, littleEndian);  cursor += 2 ; return v; }; (x2)
// const getInt32 =  () => { const v = dataView.getInt32(cursor, littleEndian);   cursor += 4 ; return v; }; (x2)
// WTF? (x6)
```

<details><summary>Code</summary>

```typescript
function parse( buf ) {

	assert.strictEqual( buf[ 0 ], 0x47, 'bad header' );
	assert.strictEqual( buf[ 1 ], 0x50, 'bad header' );
	assert.strictEqual( buf[ 2 ], 0, 'unknown version' ); // version
	const flags = buf[ 3 ];

	const flag_x = ( flags >> 5 ) & 1;
	// const flag_empty_geo = (flags >> 4) & 1;  // 1 = empty, 0 non-empty
	const flag_byteOrder = ( flags >> 0 ) & 1; // 1 = little endian, 0 = big
	const flag_envelope = ( flags >> 1 ) & 7;

	assert.strictEqual( flag_x, 0, 'x must be 0' );

	const envelopeSizes = [
		0, // 0: non
		4, // 1: minx, maxx, miny, maxy
		6, // 2: minx, maxx, miny, maxy, minz, maxz
		6, // 3: minx, maxx, miny, maxy, minm, maxm
		8, // 4: minx, maxx, miny, maxy, minz, maxz, minm, maxm
	];

	const envelopeSize = envelopeSizes[ flag_envelope ];
	assert.notStrictEqual( envelopeSize, undefined );

	const headerSize = 8;
	let cursor = headerSize;

	const dataView = new DataView( buf.buffer );
	/*
  const readBE = {
    getDouble() { const v = buf.readDoubleBE(cursor); cursor += 8 ; return v; },
    getFloat()  { const v = buf.readFloatBE(cursor);  cursor += 4 ; return v; },
    getInt8()   { const v = buf.readInt8(cursor);     cursor += 1 ; return v; },
    getUint8()  { const v = buf.readUInt8(cursor);    cursor += 1 ; return v; },
    getInt16()  { const v = buf.readInt16BE(cursor);  cursor += 2 ; return v; },
    getUint16() { const v = buf.readUInt16BE(cursor); cursor += 2 ; return v; },
    getInt32()  { const v = buf.readInt32BE(cursor);  cursor += 4 ; return v; },
    getUint32() { const v = buf.readUInt32BE(cursor); cursor += 4 ; return v; },
  };

  const readLE = {
    getDouble() { const v = buf.readDoubleLE(cursor); cursor += 8 ; return v; },
    getFloat()  { const v = buf.readFloatLE(cursor);  cursor += 4 ; return v; },
    getInt8()   { const v = buf.readInt8(cursor);     cursor += 1 ; return v; },
    getUint8()  { const v = buf.readUInt8(cursor);    cursor += 1 ; return v; },
    getInt16()  { const v = buf.readInt16LE(cursor);  cursor += 2 ; return v; },
    getUint16() { const v = buf.readUInt16LE(cursor); cursor += 2 ; return v; },
    getInt32()  { const v = buf.readInt32LE(cursor);  cursor += 4 ; return v; },
    getUint32() { const v = buf.readUInt32LE(cursor); cursor += 4 ; return v; },
  };
  */

	let littleEndian;
	const endianStack = [];

	function pushByteOrder( byteOrder ) {

		endianStack.push( littleEndian );
		littleEndian = byteOrder;

	}

	function popByteOrder() {

		littleEndian = endianStack.pop();

	}

	const getDouble = () => {

		const v = dataView.getFloat64( cursor, littleEndian ); cursor += 8; return v;

	};

	// const getFloat =  () => { const v = dataView.getFloat32(cursor, littleEndian); cursor += 4 ; return v; };
	const getInt8 = () => {

		const v = dataView.getInt8( cursor ); cursor += 1; return v;

	};

	// const getUint8 =  () => { const v = dataView.getUint8(cursor, littleEndian);   cursor += 1 ; return v; };
	// const getInt16 =  () => { const v = dataView.getInt16(cursor, littleEndian);   cursor += 2 ; return v; };
	// const getUint16 = () => { const v = dataView.getUint16(cursor, littleEndian);  cursor += 2 ; return v; };
	// const getInt32 =  () => { const v = dataView.getInt32(cursor, littleEndian);   cursor += 4 ; return v; };
	const getUint32 = () => {

		const v = dataView.getUint32( cursor, littleEndian ); cursor += 4; return v;

	};

	pushByteOrder( flag_byteOrder );

	const envelope = [];
	for ( let i = 0; i < envelopeSize; ++ i ) {

		envelope.push( getDouble() );

	}

	const primitives = [];

	function getPoints( num ) {

		const points = [];
		for ( let i = 0; i < num; ++ i ) {

			points.push( getDouble(), getDouble() );

		}

		return points;

	}

	function getRings( num ) {

		const rings = [];
		for ( let i = 0; i < num; ++ i ) {

			rings.push( getPoints( getUint32() ) );

		}

		return rings;

	}

	function pointHandler() {

		return {
			type: 'point',
			point: getPoints( 1 ),
		};

	}

	function lineStringHandler() {

		return {
			type: 'lineString',
			points: getPoints( getUint32() ),
		};

	}

	function polygonHandler() {

		return {
			type: 'polygon',
			rings: getRings( getUint32() ),
		};

	}

	function multiPointHandler() {

		// WTF?
		const points = [];
		const num = getUint32();
		for ( let i = 0; i < num; ++ i ) {

			pushByteOrder( getInt8() );
			const type = getUint32();
			assert.strictEqual( type, 1 ); // must be point
			points.push( getDouble(), getDouble() );
			popByteOrder();

		}

		return {
			type: 'multiPoint',
			points,
		};

	}

	function multiLineStringHandler() {

		// WTF?
		const lineStrings = [];
		const num = getUint32();
		for ( let i = 0; i < num; ++ i ) {

			pushByteOrder( getInt8() );
			const type = getUint32();
			assert.strictEqual( type, 2 ); // must be lineString
			lineStrings.push( getPoints( getUint32() ) );
			popByteOrder();

		}

		return {
			type: 'multiLineString',
			lineStrings,
		};

	}

	function multiPolygonHandler() {

		// WTF?
		const polygons = [];
		const num = getUint32();
		for ( let i = 0; i < num; ++ i ) {

			pushByteOrder( getInt8() );
			const type = getUint32();
			assert.strictEqual( type, 3 ); // must be polygon
			polygons.push( getRings( getUint32() ) );
			popByteOrder();

		}

		return {
			type: 'multiPolygon',
			polygons,
		};

	}

	const typeHandlers = [
		undefined, // 0
		pointHandler, // 1
		lineStringHandler, // 2
		polygonHandler, // 3
		multiPointHandler, // 4
		multiLineStringHandler, // 5,
		multiPolygonHandler, // 6,
	];

	const end = buf.length;
	while ( cursor < end ) {

		pushByteOrder( getInt8() );
		const type = getUint32();
		const handler = typeHandlers[ type ];
		assert.notStrictEqual( handler, undefined, 'unknown type' );
		primitives.push( handler() );
		popByteOrder();

	}

	return {
		envelope,
		primitives,
	};

}
```
</details>

### `pushByteOrder(byteOrder: any): void`

**Parameters:**

- **`byteOrder`** `any`

**Returns:** `void`

**Calls:**

- `endianStack.push`

<details><summary>Code</summary>

```typescript
function pushByteOrder( byteOrder ) {

		endianStack.push( littleEndian );
		littleEndian = byteOrder;

	}
```
</details>

### `popByteOrder(): void`

**Returns:** `void`

**Calls:**

- `endianStack.pop`

<details><summary>Code</summary>

```typescript
function popByteOrder() {

		littleEndian = endianStack.pop();

	}
```
</details>

### `getDouble(): number`

**Returns:** `number`

**Calls:**

- `dataView.getFloat64`

<details><summary>Code</summary>

```typescript
() => {

		const v = dataView.getFloat64( cursor, littleEndian ); cursor += 8; return v;

	}
```
</details>

### `getInt8(): number`

**Returns:** `number`

**Calls:**

- `dataView.getInt8`

<details><summary>Code</summary>

```typescript
() => {

		const v = dataView.getInt8( cursor ); cursor += 1; return v;

	}
```
</details>

### `getUint32(): number`

**Returns:** `number`

**Calls:**

- `dataView.getUint32`

<details><summary>Code</summary>

```typescript
() => {

		const v = dataView.getUint32( cursor, littleEndian ); cursor += 4; return v;

	}
```
</details>

### `getPoints(num: any): number[]`

**Parameters:**

- **`num`** `any`

**Returns:** `number[]`

**Calls:**

- `points.push`
- `getDouble`

<details><summary>Code</summary>

```typescript
function getPoints( num ) {

		const points = [];
		for ( let i = 0; i < num; ++ i ) {

			points.push( getDouble(), getDouble() );

		}

		return points;

	}
```
</details>

### `getRings(num: any): number[][]`

**Parameters:**

- **`num`** `any`

**Returns:** `number[][]`

**Calls:**

- `rings.push`
- `getPoints`
- `getUint32`

<details><summary>Code</summary>

```typescript
function getRings( num ) {

		const rings = [];
		for ( let i = 0; i < num; ++ i ) {

			rings.push( getPoints( getUint32() ) );

		}

		return rings;

	}
```
</details>

### `pointHandler(): { type: string; point: number[]; }`

**Returns:** `{ type: string; point: number[]; }`

**Calls:**

- `getPoints`

<details><summary>Code</summary>

```typescript
function pointHandler() {

		return {
			type: 'point',
			point: getPoints( 1 ),
		};

	}
```
</details>

### `lineStringHandler(): { type: string; points: number[]; }`

**Returns:** `{ type: string; points: number[]; }`

**Calls:**

- `getPoints`
- `getUint32`

<details><summary>Code</summary>

```typescript
function lineStringHandler() {

		return {
			type: 'lineString',
			points: getPoints( getUint32() ),
		};

	}
```
</details>

### `polygonHandler(): { type: string; rings: number[][]; }`

**Returns:** `{ type: string; rings: number[][]; }`

**Calls:**

- `getRings`
- `getUint32`

<details><summary>Code</summary>

```typescript
function polygonHandler() {

		return {
			type: 'polygon',
			rings: getRings( getUint32() ),
		};

	}
```
</details>

### `multiPointHandler(): { type: string; points: number[]; }`

**Returns:** `{ type: string; points: number[]; }`

**Calls:**

- `getUint32`
- `pushByteOrder`
- `getInt8`
- `assert.strictEqual`
- `points.push`
- `getDouble`
- `popByteOrder`

**Internal Comments:**
```
// WTF? (x2)
```

<details><summary>Code</summary>

```typescript
function multiPointHandler() {

		// WTF?
		const points = [];
		const num = getUint32();
		for ( let i = 0; i < num; ++ i ) {

			pushByteOrder( getInt8() );
			const type = getUint32();
			assert.strictEqual( type, 1 ); // must be point
			points.push( getDouble(), getDouble() );
			popByteOrder();

		}

		return {
			type: 'multiPoint',
			points,
		};

	}
```
</details>

### `multiLineStringHandler(): { type: string; lineStrings: number[][]; }`

**Returns:** `{ type: string; lineStrings: number[][]; }`

**Calls:**

- `getUint32`
- `pushByteOrder`
- `getInt8`
- `assert.strictEqual`
- `lineStrings.push`
- `getPoints`
- `popByteOrder`

**Internal Comments:**
```
// WTF? (x2)
```

<details><summary>Code</summary>

```typescript
function multiLineStringHandler() {

		// WTF?
		const lineStrings = [];
		const num = getUint32();
		for ( let i = 0; i < num; ++ i ) {

			pushByteOrder( getInt8() );
			const type = getUint32();
			assert.strictEqual( type, 2 ); // must be lineString
			lineStrings.push( getPoints( getUint32() ) );
			popByteOrder();

		}

		return {
			type: 'multiLineString',
			lineStrings,
		};

	}
```
</details>

### `multiPolygonHandler(): { type: string; polygons: number[][][]; }`

**Returns:** `{ type: string; polygons: number[][][]; }`

**Calls:**

- `getUint32`
- `pushByteOrder`
- `getInt8`
- `assert.strictEqual`
- `polygons.push`
- `getRings`
- `popByteOrder`

**Internal Comments:**
```
// WTF? (x2)
```

<details><summary>Code</summary>

```typescript
function multiPolygonHandler() {

		// WTF?
		const polygons = [];
		const num = getUint32();
		for ( let i = 0; i < num; ++ i ) {

			pushByteOrder( getInt8() );
			const type = getUint32();
			assert.strictEqual( type, 3 ); // must be polygon
			polygons.push( getRings( getUint32() ) );
			popByteOrder();

		}

		return {
			type: 'multiPolygon',
			polygons,
		};

	}
```
</details>


---