[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PCDLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 45 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/PCDLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `three` |
| `Color` | `three` |
| `FileLoader` | `three` |
| `Float32BufferAttribute` | `three` |
| `Int32BufferAttribute` | `three` |
| `Loader` | `three` |
| `Points` | `three` |
| `PointsMaterial` | `three` |
| `SRGBColorSpace` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( scope.manager )` | ✗ |
| `inLength` | `any` | let/var | `inData.length` | ✗ |
| `outData` | `Uint8Array<any>` | let/var | `new Uint8Array( outLength )` | ✗ |
| `inPtr` | `number` | let/var | `0` | ✗ |
| `outPtr` | `number` | let/var | `0` | ✗ |
| `ctrl` | `any` | let/var | `*not shown*` | ✗ |
| `len` | `any` | let/var | `*not shown*` | ✗ |
| `ref` | `any` | let/var | `*not shown*` | ✗ |
| `PCDheader` | `{ data: string; headerLen: number; st...` | let/var | `{}` | ✗ |
| `buffer` | `Uint8Array<any>` | let/var | `new Uint8Array( binaryData )` | ✗ |
| `data` | `string` | let/var | `''` | ✗ |
| `line` | `string` | let/var | `''` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `end` | `boolean` | let/var | `false` | ✗ |
| `max` | `number` | let/var | `buffer.length` | ✗ |
| `sizeSum` | `number` | let/var | `0` | ✗ |
| `position` | `any[]` | let/var | `[]` | ✗ |
| `normal` | `any[]` | let/var | `[]` | ✗ |
| `color` | `any[]` | let/var | `[]` | ✗ |
| `intensity` | `any[]` | let/var | `[]` | ✗ |
| `label` | `any[]` | let/var | `[]` | ✗ |
| `c` | `any` | let/var | `new Color()` | ✗ |
| `offset` | `{}` | let/var | `PCDheader.offset` | ✗ |
| `rgb_type` | `any` | let/var | `PCDheader.type[ rgb_field_index ]` | ✗ |
| `rgb` | `number` | let/var | `float` | ✗ |
| `farr` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( 1 )` | ✗ |
| `r` | `number` | let/var | `( ( rgb >> 16 ) & 0x0000ff ) / 255` | ✗ |
| `g` | `number` | let/var | `( ( rgb >> 8 ) & 0x0000ff ) / 255` | ✗ |
| `b` | `number` | let/var | `( ( rgb >> 0 ) & 0x0000ff ) / 255` | ✗ |
| `sizes` | `Uint32Array<ArrayBuffer>` | let/var | `new Uint32Array( data.slice( PCDheader.headerLen, PCDheader.headerLen + 8 ) )` | ✗ |
| `compressedSize` | `number` | let/var | `sizes[ 0 ]` | ✗ |
| `decompressedSize` | `number` | let/var | `sizes[ 1 ]` | ✗ |
| `dataview` | `DataView<any>` | let/var | `new DataView( decompressed.buffer )` | ✗ |
| `offset` | `{}` | let/var | `PCDheader.offset` | ✗ |
| `r` | `number` | let/var | `dataview.getUint8( ( PCDheader.points * offset.rgb ) + PCDheader.size[ rgbInd...` | ✗ |
| `g` | `number` | let/var | `dataview.getUint8( ( PCDheader.points * offset.rgb ) + PCDheader.size[ rgbInd...` | ✗ |
| `b` | `number` | let/var | `dataview.getUint8( ( PCDheader.points * offset.rgb ) + PCDheader.size[ rgbInd...` | ✗ |
| `dataview` | `DataView<ArrayBuffer>` | let/var | `new DataView( data, PCDheader.headerLen )` | ✗ |
| `offset` | `{}` | let/var | `PCDheader.offset` | ✗ |
| `r` | `number` | let/var | `dataview.getUint8( row + offset.rgb + 2 ) / 255.0` | ✗ |
| `g` | `number` | let/var | `dataview.getUint8( row + offset.rgb + 1 ) / 255.0` | ✗ |
| `b` | `number` | let/var | `dataview.getUint8( row + offset.rgb + 0 ) / 255.0` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `material` | `any` | let/var | `new PointsMaterial( { size: 0.005 } )` | ✗ |


---

## Functions

### `PCDLoader.load(url: string, onLoad: (arg0: Points) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded PCD asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Points)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: Points) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `loader.setPath`
- `loader.setResponseType`
- `loader.setRequestHeader`
- `loader.setWithCredentials`
- `loader.load`
- `onLoad`
- `scope.parse`
- `onError`
- `console.error`
- `scope.manager.itemError`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( data ) {

			try {

				onLoad( scope.parse( data ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

### `PCDLoader._getDataView(dataview: DataView<ArrayBufferLike>, offset: number, type: "F" | "I" | "U", size: number): number`

**JSDoc:**
```typescript
/**
	 * Get dataview value by field type and size.
	 *
	 * @param {DataView} dataview - The DataView to read from.
	 * @param {number} offset - The offset to start reading from.
	 * @param {'F' | 'U' | 'I'} type - Field type.
	 * @param {number} size - Field size.
	 * @returns {number} Field value.
	 */
```

**Parameters:**

- **`dataview`** `DataView<ArrayBufferLike>`
- **`offset`** `number`
- **`type`** `"F" | "I" | "U"`
- **`size`** `number`

**Returns:** `number`

**Calls:**

- `dataview.getFloat64`
- `dataview.getFloat32`
- `dataview.getInt8`
- `dataview.getInt16`
- `dataview.getInt32`
- `dataview.getUint8`
- `dataview.getUint16`
- `dataview.getUint32`

<details><summary>Code</summary>

```typescript
_getDataView( dataview, offset, type, size ) {

		switch ( type ) {

			case 'F': {

				if ( size === 8 ) {

					return dataview.getFloat64( offset, this.littleEndian );

				}

				return dataview.getFloat32( offset, this.littleEndian );

			}

			case 'I': {

				if ( size === 1 ) {

					return dataview.getInt8( offset );

				}

				if ( size === 2 ) {

					return dataview.getInt16( offset, this.littleEndian );

				}

				return dataview.getInt32( offset, this.littleEndian );

			}

			case 'U': {

				if ( size === 1 ) {

					return dataview.getUint8( offset );

				}

				if ( size === 2 ) {

					return dataview.getUint16( offset, this.littleEndian );

				}

				return dataview.getUint32( offset, this.littleEndian );

			}

		}

	}
```
</details>

### `PCDLoader.parse(data: ArrayBuffer): Points`

**JSDoc:**
```typescript
/**
	 * Parses the given PCD data and returns a point cloud.
	 *
	 * @param {ArrayBuffer} data - The raw PCD data as an array buffer.
	 * @return {Points} The parsed point cloud.
	 */
```

**Parameters:**

- **`data`** `ArrayBuffer`

**Returns:** `Points`

**Calls:**

- `String.fromCharCode`
- `line.trim().toLowerCase().startsWith`
- `data.search`
- `/[\r\n]DATA\s(\S*)\s/i.exec`
- `data.slice`
- `PCDheader.str.replace`
- `/^VERSION (.*)/im.exec`
- `/^FIELDS (.*)/im.exec`
- `/^SIZE (.*)/im.exec`
- `/^TYPE (.*)/im.exec`
- `/^COUNT (.*)/im.exec`
- `/^WIDTH (.*)/im.exec`
- `/^HEIGHT (.*)/im.exec`
- `/^VIEWPOINT (.*)/im.exec`
- `/^POINTS (.*)/im.exec`
- `parseFloat`
- `PCDheader.fields[ 1 ].split`
- `PCDheader.type[ 1 ].split`
- `parseInt`
- `PCDheader.size[ 1 ].split( ' ' ).map`
- `PCDheader.count[ 1 ].split( ' ' ).map`
- `PCDheader.count.push`
- `parseHeader`
- `new TextDecoder().decode`
- `textData.slice`
- `pcdData.split`
- `lines[ i ].split`
- `position.push`
- `PCDheader.fields.findIndex`
- `c.setRGB`
- `color.push`
- `normal.push`
- `intensity.push`
- `label.push`
- `decompressLZF`
- `PCDheader.fields.indexOf`
- `this._getDataView`
- `dataview.getUint8`
- `dataview.getInt32`
- `geometry.setAttribute`
- `geometry.computeBoundingSphere`

**Internal Comments:**
```
// from https://gitlab.com/taketwo/three-pcd-loader/blob/master/decompress-lzf.js
// remove comments (x4)
// parse (x4)
// evaluate
// for binary only (x4)
// parse header (x2)
// parse data (x2)
// ascii
// treat float values as int (x2)
// https://github.com/daavoo/pyntcloud/pull/204/commits/7b4205e64d5ed09abe708b2e91b615690c24d518 (x2)
// binary-compressed
// normally data in PCD files are organized as array of structures: XYZRGBXYZRGB
// binary compressed PCD files organize their data as structure of arrays: XXYYZZRGBRGB
// that requires a totally different parsing approach compared to non-compressed data
// binary
// build geometry (x2)
// build material (x2)
// build point cloud
```

<details><summary>Code</summary>

```typescript
parse( data ) {

		// from https://gitlab.com/taketwo/three-pcd-loader/blob/master/decompress-lzf.js

		function decompressLZF( inData, outLength ) {

			const inLength = inData.length;
			const outData = new Uint8Array( outLength );
			let inPtr = 0;
			let outPtr = 0;
			let ctrl;
			let len;
			let ref;
			do {

				ctrl = inData[ inPtr ++ ];
				if ( ctrl < ( 1 << 5 ) ) {

					ctrl ++;
					if ( outPtr + ctrl > outLength ) throw new Error( 'Output buffer is not large enough' );
					if ( inPtr + ctrl > inLength ) throw new Error( 'Invalid compressed data' );
					do {

						outData[ outPtr ++ ] = inData[ inPtr ++ ];

					} while ( -- ctrl );

				} else {

					len = ctrl >> 5;
					ref = outPtr - ( ( ctrl & 0x1f ) << 8 ) - 1;
					if ( inPtr >= inLength ) throw new Error( 'Invalid compressed data' );
					if ( len === 7 ) {

						len += inData[ inPtr ++ ];
						if ( inPtr >= inLength ) throw new Error( 'Invalid compressed data' );

					}

					ref -= inData[ inPtr ++ ];
					if ( outPtr + len + 2 > outLength ) throw new Error( 'Output buffer is not large enough' );
					if ( ref < 0 ) throw new Error( 'Invalid compressed data' );
					if ( ref >= outPtr ) throw new Error( 'Invalid compressed data' );
					do {

						outData[ outPtr ++ ] = outData[ ref ++ ];

					} while ( -- len + 2 );

				}

			} while ( inPtr < inLength );

			return outData;

		}

		function parseHeader( binaryData ) {

			const PCDheader = {};

			const buffer = new Uint8Array( binaryData );

			let data = '', line = '', i = 0, end = false;

			const max = buffer.length;

			while ( i < max && end === false ) {

				const char = String.fromCharCode( buffer[ i ++ ] );

				if ( char === '\n' || char === '\r' ) {

					if ( line.trim().toLowerCase().startsWith( 'data' ) ) {

						end = true;

					}

					line = '';

				} else {

					line += char;

				}

				data += char;

			}

			const result1 = data.search( /[\r\n]DATA\s(\S*)\s/i );
			const result2 = /[\r\n]DATA\s(\S*)\s/i.exec( data.slice( result1 - 1 ) );

			PCDheader.data = result2[ 1 ];
			PCDheader.headerLen = result2[ 0 ].length + result1;
			PCDheader.str = data.slice( 0, PCDheader.headerLen );

			// remove comments

			PCDheader.str = PCDheader.str.replace( /#.*/gi, '' );

			// parse

			PCDheader.version = /^VERSION (.*)/im.exec( PCDheader.str );
			PCDheader.fields = /^FIELDS (.*)/im.exec( PCDheader.str );
			PCDheader.size = /^SIZE (.*)/im.exec( PCDheader.str );
			PCDheader.type = /^TYPE (.*)/im.exec( PCDheader.str );
			PCDheader.count = /^COUNT (.*)/im.exec( PCDheader.str );
			PCDheader.width = /^WIDTH (.*)/im.exec( PCDheader.str );
			PCDheader.height = /^HEIGHT (.*)/im.exec( PCDheader.str );
			PCDheader.viewpoint = /^VIEWPOINT (.*)/im.exec( PCDheader.str );
			PCDheader.points = /^POINTS (.*)/im.exec( PCDheader.str );

			// evaluate

			if ( PCDheader.version !== null )
				PCDheader.version = parseFloat( PCDheader.version[ 1 ] );

			PCDheader.fields = ( PCDheader.fields !== null ) ? PCDheader.fields[ 1 ].split( ' ' ) : [];

			if ( PCDheader.type !== null )
				PCDheader.type = PCDheader.type[ 1 ].split( ' ' );

			if ( PCDheader.width !== null )
				PCDheader.width = parseInt( PCDheader.width[ 1 ] );

			if ( PCDheader.height !== null )
				PCDheader.height = parseInt( PCDheader.height[ 1 ] );

			if ( PCDheader.viewpoint !== null )
				PCDheader.viewpoint = PCDheader.viewpoint[ 1 ];

			if ( PCDheader.points !== null )
				PCDheader.points = parseInt( PCDheader.points[ 1 ], 10 );

			if ( PCDheader.points === null )
				PCDheader.points = PCDheader.width * PCDheader.height;

			if ( PCDheader.size !== null ) {

				PCDheader.size = PCDheader.size[ 1 ].split( ' ' ).map( function ( x ) {

					return parseInt( x, 10 );

				} );

			}

			if ( PCDheader.count !== null ) {

				PCDheader.count = PCDheader.count[ 1 ].split( ' ' ).map( function ( x ) {

					return parseInt( x, 10 );

				} );

			} else {

				PCDheader.count = [];

				for ( let i = 0, l = PCDheader.fields.length; i < l; i ++ ) {

					PCDheader.count.push( 1 );

				}

			}

			PCDheader.offset = {};

			let sizeSum = 0;

			for ( let i = 0, l = PCDheader.fields.length; i < l; i ++ ) {

				if ( PCDheader.data === 'ascii' ) {

					PCDheader.offset[ PCDheader.fields[ i ] ] = i;

				} else {

					PCDheader.offset[ PCDheader.fields[ i ] ] = sizeSum;
					sizeSum += PCDheader.size[ i ] * PCDheader.count[ i ];

				}

			}

			// for binary only

			PCDheader.rowSize = sizeSum;

			return PCDheader;

		}

		// parse header

		const PCDheader = parseHeader( data );

		// parse data

		const position = [];
		const normal = [];
		const color = [];
		const intensity = [];
		const label = [];

		const c = new Color();

		// ascii

		if ( PCDheader.data === 'ascii' ) {

			const offset = PCDheader.offset;
			const textData = new TextDecoder().decode( data );
			const pcdData = textData.slice( PCDheader.headerLen );
			const lines = pcdData.split( '\n' );

			for ( let i = 0, l = lines.length; i < l; i ++ ) {

				if ( lines[ i ] === '' ) continue;

				const line = lines[ i ].split( ' ' );

				if ( offset.x !== undefined ) {

					position.push( parseFloat( line[ offset.x ] ) );
					position.push( parseFloat( line[ offset.y ] ) );
					position.push( parseFloat( line[ offset.z ] ) );

				}

				if ( offset.rgb !== undefined ) {

					const rgb_field_index = PCDheader.fields.findIndex( ( field ) => field === 'rgb' );
					const rgb_type = PCDheader.type[ rgb_field_index ];

					const float = parseFloat( line[ offset.rgb ] );
					let rgb = float;

					if ( rgb_type === 'F' ) {

						// treat float values as int
						// https://github.com/daavoo/pyntcloud/pull/204/commits/7b4205e64d5ed09abe708b2e91b615690c24d518
						const farr = new Float32Array( 1 );
						farr[ 0 ] = float;
						rgb = new Int32Array( farr.buffer )[ 0 ];

					}

					const r = ( ( rgb >> 16 ) & 0x0000ff ) / 255;
					const g = ( ( rgb >> 8 ) & 0x0000ff ) / 255;
					const b = ( ( rgb >> 0 ) & 0x0000ff ) / 255;

					c.setRGB( r, g, b, SRGBColorSpace );

					color.push( c.r, c.g, c.b );

				}

				if ( offset.normal_x !== undefined ) {

					normal.push( parseFloat( line[ offset.normal_x ] ) );
					normal.push( parseFloat( line[ offset.normal_y ] ) );
					normal.push( parseFloat( line[ offset.normal_z ] ) );

				}

				if ( offset.intensity !== undefined ) {

					intensity.push( parseFloat( line[ offset.intensity ] ) );

				}

				if ( offset.label !== undefined ) {

					label.push( parseInt( line[ offset.label ] ) );

				}

			}

		}

		// binary-compressed

		// normally data in PCD files are organized as array of structures: XYZRGBXYZRGB
		// binary compressed PCD files organize their data as structure of arrays: XXYYZZRGBRGB
		// that requires a totally different parsing approach compared to non-compressed data

		if ( PCDheader.data === 'binary_compressed' ) {

			const sizes = new Uint32Array( data.slice( PCDheader.headerLen, PCDheader.headerLen + 8 ) );
			const compressedSize = sizes[ 0 ];
			const decompressedSize = sizes[ 1 ];
			const decompressed = decompressLZF( new Uint8Array( data, PCDheader.headerLen + 8, compressedSize ), decompressedSize );
			const dataview = new DataView( decompressed.buffer );

			const offset = PCDheader.offset;

			for ( let i = 0; i < PCDheader.points; i ++ ) {

				if ( offset.x !== undefined ) {

					const xIndex = PCDheader.fields.indexOf( 'x' );
					const yIndex = PCDheader.fields.indexOf( 'y' );
					const zIndex = PCDheader.fields.indexOf( 'z' );
					position.push( this._getDataView( dataview, ( PCDheader.points * offset.x ) + PCDheader.size[ xIndex ] * i, PCDheader.type[ xIndex ], PCDheader.size[ xIndex ] ) );
					position.push( this._getDataView( dataview, ( PCDheader.points * offset.y ) + PCDheader.size[ yIndex ] * i, PCDheader.type[ yIndex ], PCDheader.size[ yIndex ] ) );
					position.push( this._getDataView( dataview, ( PCDheader.points * offset.z ) + PCDheader.size[ zIndex ] * i, PCDheader.type[ zIndex ], PCDheader.size[ zIndex ] ) );

				}

				if ( offset.rgb !== undefined ) {

					const rgbIndex = PCDheader.fields.indexOf( 'rgb' );

					const r = dataview.getUint8( ( PCDheader.points * offset.rgb ) + PCDheader.size[ rgbIndex ] * i + 2 ) / 255.0;
					const g = dataview.getUint8( ( PCDheader.points * offset.rgb ) + PCDheader.size[ rgbIndex ] * i + 1 ) / 255.0;
					const b = dataview.getUint8( ( PCDheader.points * offset.rgb ) + PCDheader.size[ rgbIndex ] * i + 0 ) / 255.0;

					c.setRGB( r, g, b, SRGBColorSpace );

					color.push( c.r, c.g, c.b );

				}

				if ( offset.normal_x !== undefined ) {

					const xIndex = PCDheader.fields.indexOf( 'normal_x' );
					const yIndex = PCDheader.fields.indexOf( 'normal_y' );
					const zIndex = PCDheader.fields.indexOf( 'normal_z' );
					normal.push( this._getDataView( dataview, ( PCDheader.points * offset.normal_x ) + PCDheader.size[ xIndex ] * i, PCDheader.type[ xIndex ], PCDheader.size[ xIndex ] ) );
					normal.push( this._getDataView( dataview, ( PCDheader.points * offset.normal_y ) + PCDheader.size[ yIndex ] * i, PCDheader.type[ yIndex ], PCDheader.size[ yIndex ] ) );
					normal.push( this._getDataView( dataview, ( PCDheader.points * offset.normal_z ) + PCDheader.size[ zIndex ] * i, PCDheader.type[ zIndex ], PCDheader.size[ zIndex ] ) );

				}

				if ( offset.intensity !== undefined ) {

					const intensityIndex = PCDheader.fields.indexOf( 'intensity' );
					intensity.push( this._getDataView( dataview, ( PCDheader.points * offset.intensity ) + PCDheader.size[ intensityIndex ] * i, PCDheader.type[ intensityIndex ], PCDheader.size[ intensityIndex ] ) );

				}

				if ( offset.label !== undefined ) {

					const labelIndex = PCDheader.fields.indexOf( 'label' );
					label.push( dataview.getInt32( ( PCDheader.points * offset.label ) + PCDheader.size[ labelIndex ] * i, this.littleEndian ) );

				}

			}

		}

		// binary

		if ( PCDheader.data === 'binary' ) {

			const dataview = new DataView( data, PCDheader.headerLen );
			const offset = PCDheader.offset;

			for ( let i = 0, row = 0; i < PCDheader.points; i ++, row += PCDheader.rowSize ) {

				if ( offset.x !== undefined ) {

					const xIndex = PCDheader.fields.indexOf( 'x' );
					const yIndex = PCDheader.fields.indexOf( 'y' );
					const zIndex = PCDheader.fields.indexOf( 'z' );
					position.push( this._getDataView( dataview, row + offset.x, PCDheader.type[ xIndex ], PCDheader.size[ xIndex ] ) );
					position.push( this._getDataView( dataview, row + offset.y, PCDheader.type[ yIndex ], PCDheader.size[ yIndex ] ) );
					position.push( this._getDataView( dataview, row + offset.z, PCDheader.type[ zIndex ], PCDheader.size[ zIndex ] ) );

				}

				if ( offset.rgb !== undefined ) {

					const r = dataview.getUint8( row + offset.rgb + 2 ) / 255.0;
					const g = dataview.getUint8( row + offset.rgb + 1 ) / 255.0;
					const b = dataview.getUint8( row + offset.rgb + 0 ) / 255.0;

					c.setRGB( r, g, b, SRGBColorSpace );

					color.push( c.r, c.g, c.b );

				}

				if ( offset.normal_x !== undefined ) {

					const xIndex = PCDheader.fields.indexOf( 'normal_x' );
					const yIndex = PCDheader.fields.indexOf( 'normal_y' );
					const zIndex = PCDheader.fields.indexOf( 'normal_z' );
					normal.push( this._getDataView( dataview, row + offset.normal_x, PCDheader.type[ xIndex ], PCDheader.size[ xIndex ] ) );
					normal.push( this._getDataView( dataview, row + offset.normal_y, PCDheader.type[ yIndex ], PCDheader.size[ yIndex ] ) );
					normal.push( this._getDataView( dataview, row + offset.normal_z, PCDheader.type[ zIndex ], PCDheader.size[ zIndex ] ) );

				}

				if ( offset.intensity !== undefined ) {

					const intensityIndex = PCDheader.fields.indexOf( 'intensity' );
					intensity.push( this._getDataView( dataview, row + offset.intensity, PCDheader.type[ intensityIndex ], PCDheader.size[ intensityIndex ] ) );

				}

				if ( offset.label !== undefined ) {

					label.push( dataview.getInt32( row + offset.label, this.littleEndian ) );

				}

			}

		}

		// build geometry

		const geometry = new BufferGeometry();

		if ( position.length > 0 ) geometry.setAttribute( 'position', new Float32BufferAttribute( position, 3 ) );
		if ( normal.length > 0 ) geometry.setAttribute( 'normal', new Float32BufferAttribute( normal, 3 ) );
		if ( color.length > 0 ) geometry.setAttribute( 'color', new Float32BufferAttribute( color, 3 ) );
		if ( intensity.length > 0 ) geometry.setAttribute( 'intensity', new Float32BufferAttribute( intensity, 1 ) );
		if ( label.length > 0 ) geometry.setAttribute( 'label', new Int32BufferAttribute( label, 1 ) );

		geometry.computeBoundingSphere();

		// build material

		const material = new PointsMaterial( { size: 0.005 } );

		if ( color.length > 0 ) {

			material.vertexColors = true;

		}

		// build point cloud

		return new Points( geometry, material );

	}
```
</details>

### `decompressLZF(inData: any, outLength: any): Uint8Array<any>`

**Parameters:**

- **`inData`** `any`
- **`outLength`** `any`

**Returns:** `Uint8Array<any>`

<details><summary>Code</summary>

```typescript
function decompressLZF( inData, outLength ) {

			const inLength = inData.length;
			const outData = new Uint8Array( outLength );
			let inPtr = 0;
			let outPtr = 0;
			let ctrl;
			let len;
			let ref;
			do {

				ctrl = inData[ inPtr ++ ];
				if ( ctrl < ( 1 << 5 ) ) {

					ctrl ++;
					if ( outPtr + ctrl > outLength ) throw new Error( 'Output buffer is not large enough' );
					if ( inPtr + ctrl > inLength ) throw new Error( 'Invalid compressed data' );
					do {

						outData[ outPtr ++ ] = inData[ inPtr ++ ];

					} while ( -- ctrl );

				} else {

					len = ctrl >> 5;
					ref = outPtr - ( ( ctrl & 0x1f ) << 8 ) - 1;
					if ( inPtr >= inLength ) throw new Error( 'Invalid compressed data' );
					if ( len === 7 ) {

						len += inData[ inPtr ++ ];
						if ( inPtr >= inLength ) throw new Error( 'Invalid compressed data' );

					}

					ref -= inData[ inPtr ++ ];
					if ( outPtr + len + 2 > outLength ) throw new Error( 'Output buffer is not large enough' );
					if ( ref < 0 ) throw new Error( 'Invalid compressed data' );
					if ( ref >= outPtr ) throw new Error( 'Invalid compressed data' );
					do {

						outData[ outPtr ++ ] = outData[ ref ++ ];

					} while ( -- len + 2 );

				}

			} while ( inPtr < inLength );

			return outData;

		}
```
</details>

### `parseHeader(binaryData: any): { data: string; headerLen: number; str: any; version: any; fields: any; size: any; type: any; count: any; width: any; height: number | RegExpExecArray; viewpoint: any; points: number | RegExpExecArray; offset: {}; rowSize: number; }`

**Parameters:**

- **`binaryData`** `any`

**Returns:** `{ data: string; headerLen: number; str: any; version: any; fields: any; size: any; type: any; count: any; width: any; height: number | RegExpExecArray; viewpoint: any; points: number | RegExpExecArray; offset: {}; rowSize: number; }`

**Calls:**

- `String.fromCharCode`
- `line.trim().toLowerCase().startsWith`
- `data.search`
- `/[\r\n]DATA\s(\S*)\s/i.exec`
- `data.slice`
- `PCDheader.str.replace`
- `/^VERSION (.*)/im.exec`
- `/^FIELDS (.*)/im.exec`
- `/^SIZE (.*)/im.exec`
- `/^TYPE (.*)/im.exec`
- `/^COUNT (.*)/im.exec`
- `/^WIDTH (.*)/im.exec`
- `/^HEIGHT (.*)/im.exec`
- `/^VIEWPOINT (.*)/im.exec`
- `/^POINTS (.*)/im.exec`
- `parseFloat`
- `PCDheader.fields[ 1 ].split`
- `PCDheader.type[ 1 ].split`
- `parseInt`
- `PCDheader.size[ 1 ].split( ' ' ).map`
- `PCDheader.count[ 1 ].split( ' ' ).map`
- `PCDheader.count.push`

**Internal Comments:**
```
// remove comments (x4)
// parse (x4)
// evaluate
// for binary only (x4)
```

<details><summary>Code</summary>

```typescript
function parseHeader( binaryData ) {

			const PCDheader = {};

			const buffer = new Uint8Array( binaryData );

			let data = '', line = '', i = 0, end = false;

			const max = buffer.length;

			while ( i < max && end === false ) {

				const char = String.fromCharCode( buffer[ i ++ ] );

				if ( char === '\n' || char === '\r' ) {

					if ( line.trim().toLowerCase().startsWith( 'data' ) ) {

						end = true;

					}

					line = '';

				} else {

					line += char;

				}

				data += char;

			}

			const result1 = data.search( /[\r\n]DATA\s(\S*)\s/i );
			const result2 = /[\r\n]DATA\s(\S*)\s/i.exec( data.slice( result1 - 1 ) );

			PCDheader.data = result2[ 1 ];
			PCDheader.headerLen = result2[ 0 ].length + result1;
			PCDheader.str = data.slice( 0, PCDheader.headerLen );

			// remove comments

			PCDheader.str = PCDheader.str.replace( /#.*/gi, '' );

			// parse

			PCDheader.version = /^VERSION (.*)/im.exec( PCDheader.str );
			PCDheader.fields = /^FIELDS (.*)/im.exec( PCDheader.str );
			PCDheader.size = /^SIZE (.*)/im.exec( PCDheader.str );
			PCDheader.type = /^TYPE (.*)/im.exec( PCDheader.str );
			PCDheader.count = /^COUNT (.*)/im.exec( PCDheader.str );
			PCDheader.width = /^WIDTH (.*)/im.exec( PCDheader.str );
			PCDheader.height = /^HEIGHT (.*)/im.exec( PCDheader.str );
			PCDheader.viewpoint = /^VIEWPOINT (.*)/im.exec( PCDheader.str );
			PCDheader.points = /^POINTS (.*)/im.exec( PCDheader.str );

			// evaluate

			if ( PCDheader.version !== null )
				PCDheader.version = parseFloat( PCDheader.version[ 1 ] );

			PCDheader.fields = ( PCDheader.fields !== null ) ? PCDheader.fields[ 1 ].split( ' ' ) : [];

			if ( PCDheader.type !== null )
				PCDheader.type = PCDheader.type[ 1 ].split( ' ' );

			if ( PCDheader.width !== null )
				PCDheader.width = parseInt( PCDheader.width[ 1 ] );

			if ( PCDheader.height !== null )
				PCDheader.height = parseInt( PCDheader.height[ 1 ] );

			if ( PCDheader.viewpoint !== null )
				PCDheader.viewpoint = PCDheader.viewpoint[ 1 ];

			if ( PCDheader.points !== null )
				PCDheader.points = parseInt( PCDheader.points[ 1 ], 10 );

			if ( PCDheader.points === null )
				PCDheader.points = PCDheader.width * PCDheader.height;

			if ( PCDheader.size !== null ) {

				PCDheader.size = PCDheader.size[ 1 ].split( ' ' ).map( function ( x ) {

					return parseInt( x, 10 );

				} );

			}

			if ( PCDheader.count !== null ) {

				PCDheader.count = PCDheader.count[ 1 ].split( ' ' ).map( function ( x ) {

					return parseInt( x, 10 );

				} );

			} else {

				PCDheader.count = [];

				for ( let i = 0, l = PCDheader.fields.length; i < l; i ++ ) {

					PCDheader.count.push( 1 );

				}

			}

			PCDheader.offset = {};

			let sizeSum = 0;

			for ( let i = 0, l = PCDheader.fields.length; i < l; i ++ ) {

				if ( PCDheader.data === 'ascii' ) {

					PCDheader.offset[ PCDheader.fields[ i ] ] = i;

				} else {

					PCDheader.offset[ PCDheader.fields[ i ] ] = sizeSum;
					sizeSum += PCDheader.size[ i ] * PCDheader.count[ i ];

				}

			}

			// for binary only

			PCDheader.rowSize = sizeSum;

			return PCDheader;

		}
```
</details>


---

## Classes

### `PCDLoader`

<details><summary>Class Code</summary>

```ts
class PCDLoader extends Loader {

	/**
	 * Constructs a new PCD loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		/**
		 * Whether to use little Endian or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.littleEndian = true;

	}

	/**
	 * Starts loading from the given URL and passes the loaded PCD asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Points)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( data ) {

			try {

				onLoad( scope.parse( data ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}

	/**
	 * Get dataview value by field type and size.
	 *
	 * @param {DataView} dataview - The DataView to read from.
	 * @param {number} offset - The offset to start reading from.
	 * @param {'F' | 'U' | 'I'} type - Field type.
	 * @param {number} size - Field size.
	 * @returns {number} Field value.
	 */
	_getDataView( dataview, offset, type, size ) {

		switch ( type ) {

			case 'F': {

				if ( size === 8 ) {

					return dataview.getFloat64( offset, this.littleEndian );

				}

				return dataview.getFloat32( offset, this.littleEndian );

			}

			case 'I': {

				if ( size === 1 ) {

					return dataview.getInt8( offset );

				}

				if ( size === 2 ) {

					return dataview.getInt16( offset, this.littleEndian );

				}

				return dataview.getInt32( offset, this.littleEndian );

			}

			case 'U': {

				if ( size === 1 ) {

					return dataview.getUint8( offset );

				}

				if ( size === 2 ) {

					return dataview.getUint16( offset, this.littleEndian );

				}

				return dataview.getUint32( offset, this.littleEndian );

			}

		}

	}

	/**
	 * Parses the given PCD data and returns a point cloud.
	 *
	 * @param {ArrayBuffer} data - The raw PCD data as an array buffer.
	 * @return {Points} The parsed point cloud.
	 */
	parse( data ) {

		// from https://gitlab.com/taketwo/three-pcd-loader/blob/master/decompress-lzf.js

		function decompressLZF( inData, outLength ) {

			const inLength = inData.length;
			const outData = new Uint8Array( outLength );
			let inPtr = 0;
			let outPtr = 0;
			let ctrl;
			let len;
			let ref;
			do {

				ctrl = inData[ inPtr ++ ];
				if ( ctrl < ( 1 << 5 ) ) {

					ctrl ++;
					if ( outPtr + ctrl > outLength ) throw new Error( 'Output buffer is not large enough' );
					if ( inPtr + ctrl > inLength ) throw new Error( 'Invalid compressed data' );
					do {

						outData[ outPtr ++ ] = inData[ inPtr ++ ];

					} while ( -- ctrl );

				} else {

					len = ctrl >> 5;
					ref = outPtr - ( ( ctrl & 0x1f ) << 8 ) - 1;
					if ( inPtr >= inLength ) throw new Error( 'Invalid compressed data' );
					if ( len === 7 ) {

						len += inData[ inPtr ++ ];
						if ( inPtr >= inLength ) throw new Error( 'Invalid compressed data' );

					}

					ref -= inData[ inPtr ++ ];
					if ( outPtr + len + 2 > outLength ) throw new Error( 'Output buffer is not large enough' );
					if ( ref < 0 ) throw new Error( 'Invalid compressed data' );
					if ( ref >= outPtr ) throw new Error( 'Invalid compressed data' );
					do {

						outData[ outPtr ++ ] = outData[ ref ++ ];

					} while ( -- len + 2 );

				}

			} while ( inPtr < inLength );

			return outData;

		}

		function parseHeader( binaryData ) {

			const PCDheader = {};

			const buffer = new Uint8Array( binaryData );

			let data = '', line = '', i = 0, end = false;

			const max = buffer.length;

			while ( i < max && end === false ) {

				const char = String.fromCharCode( buffer[ i ++ ] );

				if ( char === '\n' || char === '\r' ) {

					if ( line.trim().toLowerCase().startsWith( 'data' ) ) {

						end = true;

					}

					line = '';

				} else {

					line += char;

				}

				data += char;

			}

			const result1 = data.search( /[\r\n]DATA\s(\S*)\s/i );
			const result2 = /[\r\n]DATA\s(\S*)\s/i.exec( data.slice( result1 - 1 ) );

			PCDheader.data = result2[ 1 ];
			PCDheader.headerLen = result2[ 0 ].length + result1;
			PCDheader.str = data.slice( 0, PCDheader.headerLen );

			// remove comments

			PCDheader.str = PCDheader.str.replace( /#.*/gi, '' );

			// parse

			PCDheader.version = /^VERSION (.*)/im.exec( PCDheader.str );
			PCDheader.fields = /^FIELDS (.*)/im.exec( PCDheader.str );
			PCDheader.size = /^SIZE (.*)/im.exec( PCDheader.str );
			PCDheader.type = /^TYPE (.*)/im.exec( PCDheader.str );
			PCDheader.count = /^COUNT (.*)/im.exec( PCDheader.str );
			PCDheader.width = /^WIDTH (.*)/im.exec( PCDheader.str );
			PCDheader.height = /^HEIGHT (.*)/im.exec( PCDheader.str );
			PCDheader.viewpoint = /^VIEWPOINT (.*)/im.exec( PCDheader.str );
			PCDheader.points = /^POINTS (.*)/im.exec( PCDheader.str );

			// evaluate

			if ( PCDheader.version !== null )
				PCDheader.version = parseFloat( PCDheader.version[ 1 ] );

			PCDheader.fields = ( PCDheader.fields !== null ) ? PCDheader.fields[ 1 ].split( ' ' ) : [];

			if ( PCDheader.type !== null )
				PCDheader.type = PCDheader.type[ 1 ].split( ' ' );

			if ( PCDheader.width !== null )
				PCDheader.width = parseInt( PCDheader.width[ 1 ] );

			if ( PCDheader.height !== null )
				PCDheader.height = parseInt( PCDheader.height[ 1 ] );

			if ( PCDheader.viewpoint !== null )
				PCDheader.viewpoint = PCDheader.viewpoint[ 1 ];

			if ( PCDheader.points !== null )
				PCDheader.points = parseInt( PCDheader.points[ 1 ], 10 );

			if ( PCDheader.points === null )
				PCDheader.points = PCDheader.width * PCDheader.height;

			if ( PCDheader.size !== null ) {

				PCDheader.size = PCDheader.size[ 1 ].split( ' ' ).map( function ( x ) {

					return parseInt( x, 10 );

				} );

			}

			if ( PCDheader.count !== null ) {

				PCDheader.count = PCDheader.count[ 1 ].split( ' ' ).map( function ( x ) {

					return parseInt( x, 10 );

				} );

			} else {

				PCDheader.count = [];

				for ( let i = 0, l = PCDheader.fields.length; i < l; i ++ ) {

					PCDheader.count.push( 1 );

				}

			}

			PCDheader.offset = {};

			let sizeSum = 0;

			for ( let i = 0, l = PCDheader.fields.length; i < l; i ++ ) {

				if ( PCDheader.data === 'ascii' ) {

					PCDheader.offset[ PCDheader.fields[ i ] ] = i;

				} else {

					PCDheader.offset[ PCDheader.fields[ i ] ] = sizeSum;
					sizeSum += PCDheader.size[ i ] * PCDheader.count[ i ];

				}

			}

			// for binary only

			PCDheader.rowSize = sizeSum;

			return PCDheader;

		}

		// parse header

		const PCDheader = parseHeader( data );

		// parse data

		const position = [];
		const normal = [];
		const color = [];
		const intensity = [];
		const label = [];

		const c = new Color();

		// ascii

		if ( PCDheader.data === 'ascii' ) {

			const offset = PCDheader.offset;
			const textData = new TextDecoder().decode( data );
			const pcdData = textData.slice( PCDheader.headerLen );
			const lines = pcdData.split( '\n' );

			for ( let i = 0, l = lines.length; i < l; i ++ ) {

				if ( lines[ i ] === '' ) continue;

				const line = lines[ i ].split( ' ' );

				if ( offset.x !== undefined ) {

					position.push( parseFloat( line[ offset.x ] ) );
					position.push( parseFloat( line[ offset.y ] ) );
					position.push( parseFloat( line[ offset.z ] ) );

				}

				if ( offset.rgb !== undefined ) {

					const rgb_field_index = PCDheader.fields.findIndex( ( field ) => field === 'rgb' );
					const rgb_type = PCDheader.type[ rgb_field_index ];

					const float = parseFloat( line[ offset.rgb ] );
					let rgb = float;

					if ( rgb_type === 'F' ) {

						// treat float values as int
						// https://github.com/daavoo/pyntcloud/pull/204/commits/7b4205e64d5ed09abe708b2e91b615690c24d518
						const farr = new Float32Array( 1 );
						farr[ 0 ] = float;
						rgb = new Int32Array( farr.buffer )[ 0 ];

					}

					const r = ( ( rgb >> 16 ) & 0x0000ff ) / 255;
					const g = ( ( rgb >> 8 ) & 0x0000ff ) / 255;
					const b = ( ( rgb >> 0 ) & 0x0000ff ) / 255;

					c.setRGB( r, g, b, SRGBColorSpace );

					color.push( c.r, c.g, c.b );

				}

				if ( offset.normal_x !== undefined ) {

					normal.push( parseFloat( line[ offset.normal_x ] ) );
					normal.push( parseFloat( line[ offset.normal_y ] ) );
					normal.push( parseFloat( line[ offset.normal_z ] ) );

				}

				if ( offset.intensity !== undefined ) {

					intensity.push( parseFloat( line[ offset.intensity ] ) );

				}

				if ( offset.label !== undefined ) {

					label.push( parseInt( line[ offset.label ] ) );

				}

			}

		}

		// binary-compressed

		// normally data in PCD files are organized as array of structures: XYZRGBXYZRGB
		// binary compressed PCD files organize their data as structure of arrays: XXYYZZRGBRGB
		// that requires a totally different parsing approach compared to non-compressed data

		if ( PCDheader.data === 'binary_compressed' ) {

			const sizes = new Uint32Array( data.slice( PCDheader.headerLen, PCDheader.headerLen + 8 ) );
			const compressedSize = sizes[ 0 ];
			const decompressedSize = sizes[ 1 ];
			const decompressed = decompressLZF( new Uint8Array( data, PCDheader.headerLen + 8, compressedSize ), decompressedSize );
			const dataview = new DataView( decompressed.buffer );

			const offset = PCDheader.offset;

			for ( let i = 0; i < PCDheader.points; i ++ ) {

				if ( offset.x !== undefined ) {

					const xIndex = PCDheader.fields.indexOf( 'x' );
					const yIndex = PCDheader.fields.indexOf( 'y' );
					const zIndex = PCDheader.fields.indexOf( 'z' );
					position.push( this._getDataView( dataview, ( PCDheader.points * offset.x ) + PCDheader.size[ xIndex ] * i, PCDheader.type[ xIndex ], PCDheader.size[ xIndex ] ) );
					position.push( this._getDataView( dataview, ( PCDheader.points * offset.y ) + PCDheader.size[ yIndex ] * i, PCDheader.type[ yIndex ], PCDheader.size[ yIndex ] ) );
					position.push( this._getDataView( dataview, ( PCDheader.points * offset.z ) + PCDheader.size[ zIndex ] * i, PCDheader.type[ zIndex ], PCDheader.size[ zIndex ] ) );

				}

				if ( offset.rgb !== undefined ) {

					const rgbIndex = PCDheader.fields.indexOf( 'rgb' );

					const r = dataview.getUint8( ( PCDheader.points * offset.rgb ) + PCDheader.size[ rgbIndex ] * i + 2 ) / 255.0;
					const g = dataview.getUint8( ( PCDheader.points * offset.rgb ) + PCDheader.size[ rgbIndex ] * i + 1 ) / 255.0;
					const b = dataview.getUint8( ( PCDheader.points * offset.rgb ) + PCDheader.size[ rgbIndex ] * i + 0 ) / 255.0;

					c.setRGB( r, g, b, SRGBColorSpace );

					color.push( c.r, c.g, c.b );

				}

				if ( offset.normal_x !== undefined ) {

					const xIndex = PCDheader.fields.indexOf( 'normal_x' );
					const yIndex = PCDheader.fields.indexOf( 'normal_y' );
					const zIndex = PCDheader.fields.indexOf( 'normal_z' );
					normal.push( this._getDataView( dataview, ( PCDheader.points * offset.normal_x ) + PCDheader.size[ xIndex ] * i, PCDheader.type[ xIndex ], PCDheader.size[ xIndex ] ) );
					normal.push( this._getDataView( dataview, ( PCDheader.points * offset.normal_y ) + PCDheader.size[ yIndex ] * i, PCDheader.type[ yIndex ], PCDheader.size[ yIndex ] ) );
					normal.push( this._getDataView( dataview, ( PCDheader.points * offset.normal_z ) + PCDheader.size[ zIndex ] * i, PCDheader.type[ zIndex ], PCDheader.size[ zIndex ] ) );

				}

				if ( offset.intensity !== undefined ) {

					const intensityIndex = PCDheader.fields.indexOf( 'intensity' );
					intensity.push( this._getDataView( dataview, ( PCDheader.points * offset.intensity ) + PCDheader.size[ intensityIndex ] * i, PCDheader.type[ intensityIndex ], PCDheader.size[ intensityIndex ] ) );

				}

				if ( offset.label !== undefined ) {

					const labelIndex = PCDheader.fields.indexOf( 'label' );
					label.push( dataview.getInt32( ( PCDheader.points * offset.label ) + PCDheader.size[ labelIndex ] * i, this.littleEndian ) );

				}

			}

		}

		// binary

		if ( PCDheader.data === 'binary' ) {

			const dataview = new DataView( data, PCDheader.headerLen );
			const offset = PCDheader.offset;

			for ( let i = 0, row = 0; i < PCDheader.points; i ++, row += PCDheader.rowSize ) {

				if ( offset.x !== undefined ) {

					const xIndex = PCDheader.fields.indexOf( 'x' );
					const yIndex = PCDheader.fields.indexOf( 'y' );
					const zIndex = PCDheader.fields.indexOf( 'z' );
					position.push( this._getDataView( dataview, row + offset.x, PCDheader.type[ xIndex ], PCDheader.size[ xIndex ] ) );
					position.push( this._getDataView( dataview, row + offset.y, PCDheader.type[ yIndex ], PCDheader.size[ yIndex ] ) );
					position.push( this._getDataView( dataview, row + offset.z, PCDheader.type[ zIndex ], PCDheader.size[ zIndex ] ) );

				}

				if ( offset.rgb !== undefined ) {

					const r = dataview.getUint8( row + offset.rgb + 2 ) / 255.0;
					const g = dataview.getUint8( row + offset.rgb + 1 ) / 255.0;
					const b = dataview.getUint8( row + offset.rgb + 0 ) / 255.0;

					c.setRGB( r, g, b, SRGBColorSpace );

					color.push( c.r, c.g, c.b );

				}

				if ( offset.normal_x !== undefined ) {

					const xIndex = PCDheader.fields.indexOf( 'normal_x' );
					const yIndex = PCDheader.fields.indexOf( 'normal_y' );
					const zIndex = PCDheader.fields.indexOf( 'normal_z' );
					normal.push( this._getDataView( dataview, row + offset.normal_x, PCDheader.type[ xIndex ], PCDheader.size[ xIndex ] ) );
					normal.push( this._getDataView( dataview, row + offset.normal_y, PCDheader.type[ yIndex ], PCDheader.size[ yIndex ] ) );
					normal.push( this._getDataView( dataview, row + offset.normal_z, PCDheader.type[ zIndex ], PCDheader.size[ zIndex ] ) );

				}

				if ( offset.intensity !== undefined ) {

					const intensityIndex = PCDheader.fields.indexOf( 'intensity' );
					intensity.push( this._getDataView( dataview, row + offset.intensity, PCDheader.type[ intensityIndex ], PCDheader.size[ intensityIndex ] ) );

				}

				if ( offset.label !== undefined ) {

					label.push( dataview.getInt32( row + offset.label, this.littleEndian ) );

				}

			}

		}

		// build geometry

		const geometry = new BufferGeometry();

		if ( position.length > 0 ) geometry.setAttribute( 'position', new Float32BufferAttribute( position, 3 ) );
		if ( normal.length > 0 ) geometry.setAttribute( 'normal', new Float32BufferAttribute( normal, 3 ) );
		if ( color.length > 0 ) geometry.setAttribute( 'color', new Float32BufferAttribute( color, 3 ) );
		if ( intensity.length > 0 ) geometry.setAttribute( 'intensity', new Float32BufferAttribute( intensity, 1 ) );
		if ( label.length > 0 ) geometry.setAttribute( 'label', new Int32BufferAttribute( label, 1 ) );

		geometry.computeBoundingSphere();

		// build material

		const material = new PointsMaterial( { size: 0.005 } );

		if ( color.length > 0 ) {

			material.vertexColors = true;

		}

		// build point cloud

		return new Points( geometry, material );

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: Points) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( data ) {

			try {

				onLoad( scope.parse( data ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

##### `_getDataView(dataview: DataView<ArrayBufferLike>, offset: number, type: "F" | "I" | "U", size: number): number`

<details><summary>Code</summary>

```ts
_getDataView( dataview, offset, type, size ) {

		switch ( type ) {

			case 'F': {

				if ( size === 8 ) {

					return dataview.getFloat64( offset, this.littleEndian );

				}

				return dataview.getFloat32( offset, this.littleEndian );

			}

			case 'I': {

				if ( size === 1 ) {

					return dataview.getInt8( offset );

				}

				if ( size === 2 ) {

					return dataview.getInt16( offset, this.littleEndian );

				}

				return dataview.getInt32( offset, this.littleEndian );

			}

			case 'U': {

				if ( size === 1 ) {

					return dataview.getUint8( offset );

				}

				if ( size === 2 ) {

					return dataview.getUint16( offset, this.littleEndian );

				}

				return dataview.getUint32( offset, this.littleEndian );

			}

		}

	}
```
</details>

##### `parse(data: ArrayBuffer): Points`

<details><summary>Code</summary>

```ts
parse( data ) {

		// from https://gitlab.com/taketwo/three-pcd-loader/blob/master/decompress-lzf.js

		function decompressLZF( inData, outLength ) {

			const inLength = inData.length;
			const outData = new Uint8Array( outLength );
			let inPtr = 0;
			let outPtr = 0;
			let ctrl;
			let len;
			let ref;
			do {

				ctrl = inData[ inPtr ++ ];
				if ( ctrl < ( 1 << 5 ) ) {

					ctrl ++;
					if ( outPtr + ctrl > outLength ) throw new Error( 'Output buffer is not large enough' );
					if ( inPtr + ctrl > inLength ) throw new Error( 'Invalid compressed data' );
					do {

						outData[ outPtr ++ ] = inData[ inPtr ++ ];

					} while ( -- ctrl );

				} else {

					len = ctrl >> 5;
					ref = outPtr - ( ( ctrl & 0x1f ) << 8 ) - 1;
					if ( inPtr >= inLength ) throw new Error( 'Invalid compressed data' );
					if ( len === 7 ) {

						len += inData[ inPtr ++ ];
						if ( inPtr >= inLength ) throw new Error( 'Invalid compressed data' );

					}

					ref -= inData[ inPtr ++ ];
					if ( outPtr + len + 2 > outLength ) throw new Error( 'Output buffer is not large enough' );
					if ( ref < 0 ) throw new Error( 'Invalid compressed data' );
					if ( ref >= outPtr ) throw new Error( 'Invalid compressed data' );
					do {

						outData[ outPtr ++ ] = outData[ ref ++ ];

					} while ( -- len + 2 );

				}

			} while ( inPtr < inLength );

			return outData;

		}

		function parseHeader( binaryData ) {

			const PCDheader = {};

			const buffer = new Uint8Array( binaryData );

			let data = '', line = '', i = 0, end = false;

			const max = buffer.length;

			while ( i < max && end === false ) {

				const char = String.fromCharCode( buffer[ i ++ ] );

				if ( char === '\n' || char === '\r' ) {

					if ( line.trim().toLowerCase().startsWith( 'data' ) ) {

						end = true;

					}

					line = '';

				} else {

					line += char;

				}

				data += char;

			}

			const result1 = data.search( /[\r\n]DATA\s(\S*)\s/i );
			const result2 = /[\r\n]DATA\s(\S*)\s/i.exec( data.slice( result1 - 1 ) );

			PCDheader.data = result2[ 1 ];
			PCDheader.headerLen = result2[ 0 ].length + result1;
			PCDheader.str = data.slice( 0, PCDheader.headerLen );

			// remove comments

			PCDheader.str = PCDheader.str.replace( /#.*/gi, '' );

			// parse

			PCDheader.version = /^VERSION (.*)/im.exec( PCDheader.str );
			PCDheader.fields = /^FIELDS (.*)/im.exec( PCDheader.str );
			PCDheader.size = /^SIZE (.*)/im.exec( PCDheader.str );
			PCDheader.type = /^TYPE (.*)/im.exec( PCDheader.str );
			PCDheader.count = /^COUNT (.*)/im.exec( PCDheader.str );
			PCDheader.width = /^WIDTH (.*)/im.exec( PCDheader.str );
			PCDheader.height = /^HEIGHT (.*)/im.exec( PCDheader.str );
			PCDheader.viewpoint = /^VIEWPOINT (.*)/im.exec( PCDheader.str );
			PCDheader.points = /^POINTS (.*)/im.exec( PCDheader.str );

			// evaluate

			if ( PCDheader.version !== null )
				PCDheader.version = parseFloat( PCDheader.version[ 1 ] );

			PCDheader.fields = ( PCDheader.fields !== null ) ? PCDheader.fields[ 1 ].split( ' ' ) : [];

			if ( PCDheader.type !== null )
				PCDheader.type = PCDheader.type[ 1 ].split( ' ' );

			if ( PCDheader.width !== null )
				PCDheader.width = parseInt( PCDheader.width[ 1 ] );

			if ( PCDheader.height !== null )
				PCDheader.height = parseInt( PCDheader.height[ 1 ] );

			if ( PCDheader.viewpoint !== null )
				PCDheader.viewpoint = PCDheader.viewpoint[ 1 ];

			if ( PCDheader.points !== null )
				PCDheader.points = parseInt( PCDheader.points[ 1 ], 10 );

			if ( PCDheader.points === null )
				PCDheader.points = PCDheader.width * PCDheader.height;

			if ( PCDheader.size !== null ) {

				PCDheader.size = PCDheader.size[ 1 ].split( ' ' ).map( function ( x ) {

					return parseInt( x, 10 );

				} );

			}

			if ( PCDheader.count !== null ) {

				PCDheader.count = PCDheader.count[ 1 ].split( ' ' ).map( function ( x ) {

					return parseInt( x, 10 );

				} );

			} else {

				PCDheader.count = [];

				for ( let i = 0, l = PCDheader.fields.length; i < l; i ++ ) {

					PCDheader.count.push( 1 );

				}

			}

			PCDheader.offset = {};

			let sizeSum = 0;

			for ( let i = 0, l = PCDheader.fields.length; i < l; i ++ ) {

				if ( PCDheader.data === 'ascii' ) {

					PCDheader.offset[ PCDheader.fields[ i ] ] = i;

				} else {

					PCDheader.offset[ PCDheader.fields[ i ] ] = sizeSum;
					sizeSum += PCDheader.size[ i ] * PCDheader.count[ i ];

				}

			}

			// for binary only

			PCDheader.rowSize = sizeSum;

			return PCDheader;

		}

		// parse header

		const PCDheader = parseHeader( data );

		// parse data

		const position = [];
		const normal = [];
		const color = [];
		const intensity = [];
		const label = [];

		const c = new Color();

		// ascii

		if ( PCDheader.data === 'ascii' ) {

			const offset = PCDheader.offset;
			const textData = new TextDecoder().decode( data );
			const pcdData = textData.slice( PCDheader.headerLen );
			const lines = pcdData.split( '\n' );

			for ( let i = 0, l = lines.length; i < l; i ++ ) {

				if ( lines[ i ] === '' ) continue;

				const line = lines[ i ].split( ' ' );

				if ( offset.x !== undefined ) {

					position.push( parseFloat( line[ offset.x ] ) );
					position.push( parseFloat( line[ offset.y ] ) );
					position.push( parseFloat( line[ offset.z ] ) );

				}

				if ( offset.rgb !== undefined ) {

					const rgb_field_index = PCDheader.fields.findIndex( ( field ) => field === 'rgb' );
					const rgb_type = PCDheader.type[ rgb_field_index ];

					const float = parseFloat( line[ offset.rgb ] );
					let rgb = float;

					if ( rgb_type === 'F' ) {

						// treat float values as int
						// https://github.com/daavoo/pyntcloud/pull/204/commits/7b4205e64d5ed09abe708b2e91b615690c24d518
						const farr = new Float32Array( 1 );
						farr[ 0 ] = float;
						rgb = new Int32Array( farr.buffer )[ 0 ];

					}

					const r = ( ( rgb >> 16 ) & 0x0000ff ) / 255;
					const g = ( ( rgb >> 8 ) & 0x0000ff ) / 255;
					const b = ( ( rgb >> 0 ) & 0x0000ff ) / 255;

					c.setRGB( r, g, b, SRGBColorSpace );

					color.push( c.r, c.g, c.b );

				}

				if ( offset.normal_x !== undefined ) {

					normal.push( parseFloat( line[ offset.normal_x ] ) );
					normal.push( parseFloat( line[ offset.normal_y ] ) );
					normal.push( parseFloat( line[ offset.normal_z ] ) );

				}

				if ( offset.intensity !== undefined ) {

					intensity.push( parseFloat( line[ offset.intensity ] ) );

				}

				if ( offset.label !== undefined ) {

					label.push( parseInt( line[ offset.label ] ) );

				}

			}

		}

		// binary-compressed

		// normally data in PCD files are organized as array of structures: XYZRGBXYZRGB
		// binary compressed PCD files organize their data as structure of arrays: XXYYZZRGBRGB
		// that requires a totally different parsing approach compared to non-compressed data

		if ( PCDheader.data === 'binary_compressed' ) {

			const sizes = new Uint32Array( data.slice( PCDheader.headerLen, PCDheader.headerLen + 8 ) );
			const compressedSize = sizes[ 0 ];
			const decompressedSize = sizes[ 1 ];
			const decompressed = decompressLZF( new Uint8Array( data, PCDheader.headerLen + 8, compressedSize ), decompressedSize );
			const dataview = new DataView( decompressed.buffer );

			const offset = PCDheader.offset;

			for ( let i = 0; i < PCDheader.points; i ++ ) {

				if ( offset.x !== undefined ) {

					const xIndex = PCDheader.fields.indexOf( 'x' );
					const yIndex = PCDheader.fields.indexOf( 'y' );
					const zIndex = PCDheader.fields.indexOf( 'z' );
					position.push( this._getDataView( dataview, ( PCDheader.points * offset.x ) + PCDheader.size[ xIndex ] * i, PCDheader.type[ xIndex ], PCDheader.size[ xIndex ] ) );
					position.push( this._getDataView( dataview, ( PCDheader.points * offset.y ) + PCDheader.size[ yIndex ] * i, PCDheader.type[ yIndex ], PCDheader.size[ yIndex ] ) );
					position.push( this._getDataView( dataview, ( PCDheader.points * offset.z ) + PCDheader.size[ zIndex ] * i, PCDheader.type[ zIndex ], PCDheader.size[ zIndex ] ) );

				}

				if ( offset.rgb !== undefined ) {

					const rgbIndex = PCDheader.fields.indexOf( 'rgb' );

					const r = dataview.getUint8( ( PCDheader.points * offset.rgb ) + PCDheader.size[ rgbIndex ] * i + 2 ) / 255.0;
					const g = dataview.getUint8( ( PCDheader.points * offset.rgb ) + PCDheader.size[ rgbIndex ] * i + 1 ) / 255.0;
					const b = dataview.getUint8( ( PCDheader.points * offset.rgb ) + PCDheader.size[ rgbIndex ] * i + 0 ) / 255.0;

					c.setRGB( r, g, b, SRGBColorSpace );

					color.push( c.r, c.g, c.b );

				}

				if ( offset.normal_x !== undefined ) {

					const xIndex = PCDheader.fields.indexOf( 'normal_x' );
					const yIndex = PCDheader.fields.indexOf( 'normal_y' );
					const zIndex = PCDheader.fields.indexOf( 'normal_z' );
					normal.push( this._getDataView( dataview, ( PCDheader.points * offset.normal_x ) + PCDheader.size[ xIndex ] * i, PCDheader.type[ xIndex ], PCDheader.size[ xIndex ] ) );
					normal.push( this._getDataView( dataview, ( PCDheader.points * offset.normal_y ) + PCDheader.size[ yIndex ] * i, PCDheader.type[ yIndex ], PCDheader.size[ yIndex ] ) );
					normal.push( this._getDataView( dataview, ( PCDheader.points * offset.normal_z ) + PCDheader.size[ zIndex ] * i, PCDheader.type[ zIndex ], PCDheader.size[ zIndex ] ) );

				}

				if ( offset.intensity !== undefined ) {

					const intensityIndex = PCDheader.fields.indexOf( 'intensity' );
					intensity.push( this._getDataView( dataview, ( PCDheader.points * offset.intensity ) + PCDheader.size[ intensityIndex ] * i, PCDheader.type[ intensityIndex ], PCDheader.size[ intensityIndex ] ) );

				}

				if ( offset.label !== undefined ) {

					const labelIndex = PCDheader.fields.indexOf( 'label' );
					label.push( dataview.getInt32( ( PCDheader.points * offset.label ) + PCDheader.size[ labelIndex ] * i, this.littleEndian ) );

				}

			}

		}

		// binary

		if ( PCDheader.data === 'binary' ) {

			const dataview = new DataView( data, PCDheader.headerLen );
			const offset = PCDheader.offset;

			for ( let i = 0, row = 0; i < PCDheader.points; i ++, row += PCDheader.rowSize ) {

				if ( offset.x !== undefined ) {

					const xIndex = PCDheader.fields.indexOf( 'x' );
					const yIndex = PCDheader.fields.indexOf( 'y' );
					const zIndex = PCDheader.fields.indexOf( 'z' );
					position.push( this._getDataView( dataview, row + offset.x, PCDheader.type[ xIndex ], PCDheader.size[ xIndex ] ) );
					position.push( this._getDataView( dataview, row + offset.y, PCDheader.type[ yIndex ], PCDheader.size[ yIndex ] ) );
					position.push( this._getDataView( dataview, row + offset.z, PCDheader.type[ zIndex ], PCDheader.size[ zIndex ] ) );

				}

				if ( offset.rgb !== undefined ) {

					const r = dataview.getUint8( row + offset.rgb + 2 ) / 255.0;
					const g = dataview.getUint8( row + offset.rgb + 1 ) / 255.0;
					const b = dataview.getUint8( row + offset.rgb + 0 ) / 255.0;

					c.setRGB( r, g, b, SRGBColorSpace );

					color.push( c.r, c.g, c.b );

				}

				if ( offset.normal_x !== undefined ) {

					const xIndex = PCDheader.fields.indexOf( 'normal_x' );
					const yIndex = PCDheader.fields.indexOf( 'normal_y' );
					const zIndex = PCDheader.fields.indexOf( 'normal_z' );
					normal.push( this._getDataView( dataview, row + offset.normal_x, PCDheader.type[ xIndex ], PCDheader.size[ xIndex ] ) );
					normal.push( this._getDataView( dataview, row + offset.normal_y, PCDheader.type[ yIndex ], PCDheader.size[ yIndex ] ) );
					normal.push( this._getDataView( dataview, row + offset.normal_z, PCDheader.type[ zIndex ], PCDheader.size[ zIndex ] ) );

				}

				if ( offset.intensity !== undefined ) {

					const intensityIndex = PCDheader.fields.indexOf( 'intensity' );
					intensity.push( this._getDataView( dataview, row + offset.intensity, PCDheader.type[ intensityIndex ], PCDheader.size[ intensityIndex ] ) );

				}

				if ( offset.label !== undefined ) {

					label.push( dataview.getInt32( row + offset.label, this.littleEndian ) );

				}

			}

		}

		// build geometry

		const geometry = new BufferGeometry();

		if ( position.length > 0 ) geometry.setAttribute( 'position', new Float32BufferAttribute( position, 3 ) );
		if ( normal.length > 0 ) geometry.setAttribute( 'normal', new Float32BufferAttribute( normal, 3 ) );
		if ( color.length > 0 ) geometry.setAttribute( 'color', new Float32BufferAttribute( color, 3 ) );
		if ( intensity.length > 0 ) geometry.setAttribute( 'intensity', new Float32BufferAttribute( intensity, 1 ) );
		if ( label.length > 0 ) geometry.setAttribute( 'label', new Int32BufferAttribute( label, 1 ) );

		geometry.computeBoundingSphere();

		// build material

		const material = new PointsMaterial( { size: 0.005 } );

		if ( color.length > 0 ) {

			material.vertexColors = true;

		}

		// build point cloud

		return new Points( geometry, material );

	}
```
</details>


---