[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NRRDLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 50 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 48 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/NRRDLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `FileLoader` | `three` |
| `Loader` | `three` |
| `Matrix4` | `three` |
| `Vector3` | `three` |
| `Volume` | `../misc/Volume.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( scope.manager )` | ✗ |
| `_data` | `ArrayBuffer` | let/var | `data` | ✗ |
| `_dataPointer` | `number` | let/var | `0` | ✗ |
| `_nativeLittleEndian` | `boolean` | let/var | `new Int8Array( new Int16Array( [ 1 ] ).buffer )[ 0 ] > 0` | ✗ |
| `_littleEndian` | `true` | let/var | `true` | ✗ |
| `headerObject` | `{}` | let/var | `{}` | ✗ |
| `_chunkSize` | `number` | let/var | `1` | ✗ |
| `_array_type` | `Uint8ArrayConstructor` | let/var | `Uint8Array` | ✗ |
| `_bytes` | `Uint8Array<ArrayBuffer>` | let/var | `new _array_type( _data.slice( _dataPointer, _dataPointer += chunks * _chunkSi...` | ✗ |
| `u8` | `Uint8Array<any>` | let/var | `new Uint8Array( array.buffer, array.byteOffset, array.byteLength )` | ✗ |
| `tmp` | `number` | let/var | `u8[ k ]` | ✗ |
| `data` | `any` | let/var | `*not shown*` | ✗ |
| `field` | `any` | let/var | `*not shown*` | ✗ |
| `fn` | `any` | let/var | `*not shown*` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `l` | `any` | let/var | `*not shown*` | ✗ |
| `m` | `any` | let/var | `*not shown*` | ✗ |
| `_i` | `any` | let/var | `*not shown*` | ✗ |
| `_len` | `any` | let/var | `*not shown*` | ✗ |
| `number` | `string` | let/var | `''` | ✗ |
| `value` | `any` | let/var | `*not shown*` | ✗ |
| `base` | `number` | let/var | `10` | ✗ |
| `result` | `any` | let/var | `new headerObject.__array( lengthOfTheResult )` | ✗ |
| `resultIndex` | `number` | let/var | `0` | ✗ |
| `parsingFunction` | `(string: string, radix?: number) => n...` | let/var | `parseInt` | ✗ |
| `_length` | `number` | let/var | `_bytes.length` | ✗ |
| `_header` | `any` | let/var | `null` | ✗ |
| `_data_start` | `number` | let/var | `0` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `_copy` | `Uint8Array<any>` | let/var | `new Uint8Array( _data.length )` | ✗ |
| `volume` | `Volume` | let/var | `new Volume()` | ✗ |
| `min` | `number` | let/var | `min_max[ 0 ]` | ✗ |
| `max` | `number` | let/var | `min_max[ 1 ]` | ✗ |
| `axisOrder` | `any[]` | let/var | `[]` | ✗ |
| `transitionMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `v` | `any` | let/var | `headerObject.vectors` | ✗ |
| `output` | `string` | let/var | `''` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `_results` | `any[]` | let/var | `[]` | ✗ |
| `f` | `any` | let/var | `*not shown*` | ✗ |
| `v` | `any` | let/var | `*not shown*` | ✗ |
| `_results` | `any[]` | let/var | `[]` | ✗ |
| `_results2` | `any[]` | let/var | `[]` | ✗ |
| `f` | `any` | let/var | `*not shown*` | ✗ |
| `_results` | `any[]` | let/var | `[]` | ✗ |
| `_fieldFunctions` | `{ type: typeof type; endian: typeof e...` | let/var | `{ type: function ( data ) { switch ( data ) { case 'uchar': case 'unsigned ch...` | ✗ |


---

## Functions

### `NRRDLoader.load(url: string, onLoad: (arg0: Volume) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded NRRD asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Volume)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: Volume) => any`
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

### `NRRDLoader.setSegmentation(segmentation: boolean): void`

**JSDoc:**
```typescript
/**
	 * Toggles the segmentation mode.
	 *
	 * @param {boolean} segmentation - Whether to use segmentation mode or not.
	 */
```

**Parameters:**

- **`segmentation`** `boolean`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setSegmentation( segmentation ) {

		this.segmentation = segmentation;

	}
```
</details>

### `NRRDLoader.parse(data: ArrayBuffer): Volume`

**JSDoc:**
```typescript
/**
	 * Parses the given NRRD data and returns the resulting volume data.
	 *
	 * @param {ArrayBuffer} data - The raw NRRD data as an array buffer.
	 * @return {Volume} The parsed volume.
	 */
```

**Parameters:**

- **`data`** `ArrayBuffer`

**Returns:** `Volume`

**Calls:**

- `_data.slice`
- `flipEndianness`
- `header.split`
- `l.match`
- `m[ 1 ].trim`
- `m[ 2 ].trim`
- `fn.call`
- `headerObject.vectors.push`
- `isNaN`
- `headerObject.sizes.reduce`
- `String.fromCharCode`
- `parsingFunction`
- `scan`
- `this._parseChars`
- `parseHeader`
- `_bytes.subarray`
- `headerObject.encoding.substring`
- `fflate.gunzipSync`
- `parseDataAsText`
- `volume.computeMinMax`
- `headerObject.vectors.findIndex`
- `new Vector3().fromArray( headerObject.vectors[ 0 ] ).length`
- `new Vector3().fromArray( headerObject.vectors[ 1 ] ).length`
- `new Vector3().fromArray( headerObject.vectors[ 2 ] ).length`
- `transitionMatrix.set`
- `volume.matrix.set`
- `new Matrix4().set`
- `new Matrix4().multiplyMatrices`
- `volume.inverseMatrix.copy( volume.matrix ).invert`
- `Math.floor`

**Internal Comments:**
```
// this parser is largely inspired from the XTK NRRD parser : https://github.com/xtk/X (x2)
// 1 byte data types
// 2 byte data types
// 4 byte data types
// increase the data pointer in-place (x2)
// if required, flip the endianness of the bytes
// we need to flip here since the format doesn't match the native endianness (x3)
// return the byte array
//Flips typed array endianness in-place. Based on https://github.com/kig/DataStream.js/blob/master/DataStream.js.
//parse the header
//if no space direction is set, let's use the identity (x4)
//apply spacing if defined
//parse the data when registered as one of this type : 'text', 'ascii', 'txt'
//length of the result is the product of the sizes (x2)
//if value is not a space
// we found two line breaks in a row (x3)
// now we know what the header is (x3)
// this is were the data starts (x3)
// parse the header (x3)
// we need to decompress the datastream (x3)
// here we start the unzipping and get a typed Uint8Array back (x3)
//we need to copy the array to create a new array buffer, else we retrieve the original arraybuffer with the header (x2)
// .. let's use the underlying array buffer (x3)
// (x8)
// parse the (unzipped) data to a datastream of the correct type (x4)
// get the min and max intensities (x2)
// attach the scalar range to the volume (x4)
// get the image dimensions (x4)
// Identify axis order in the space-directions matrix from the header if possible.
// spacing (x2)
// Create IJKtoRAS matrix (x4)
// .. and set the default threshold
// only if the threshold was not already set
```

<details><summary>Code</summary>

```typescript
parse( data ) {

		// this parser is largely inspired from the XTK NRRD parser : https://github.com/xtk/X

		let _data = data;

		let _dataPointer = 0;

		const _nativeLittleEndian = new Int8Array( new Int16Array( [ 1 ] ).buffer )[ 0 ] > 0;

		const _littleEndian = true;

		const headerObject = {};

		function scan( type, chunks ) {

			let _chunkSize = 1;
			let _array_type = Uint8Array;

			switch ( type ) {

				// 1 byte data types
				case 'uchar':
					break;
				case 'schar':
					_array_type = Int8Array;
					break;
				// 2 byte data types
				case 'ushort':
					_array_type = Uint16Array;
					_chunkSize = 2;
					break;
				case 'sshort':
					_array_type = Int16Array;
					_chunkSize = 2;
					break;
				// 4 byte data types
				case 'uint':
					_array_type = Uint32Array;
					_chunkSize = 4;
					break;
				case 'sint':
					_array_type = Int32Array;
					_chunkSize = 4;
					break;
				case 'float':
					_array_type = Float32Array;
					_chunkSize = 4;
					break;
				case 'complex':
					_array_type = Float64Array;
					_chunkSize = 8;
					break;
				case 'double':
					_array_type = Float64Array;
					_chunkSize = 8;
					break;

			}

			// increase the data pointer in-place
			let _bytes = new _array_type( _data.slice( _dataPointer,
				_dataPointer += chunks * _chunkSize ) );

			// if required, flip the endianness of the bytes
			if ( _nativeLittleEndian != _littleEndian ) {

				// we need to flip here since the format doesn't match the native endianness
				_bytes = flipEndianness( _bytes, _chunkSize );

			}

			// return the byte array
			return _bytes;

		}

		//Flips typed array endianness in-place. Based on https://github.com/kig/DataStream.js/blob/master/DataStream.js.

		function flipEndianness( array, chunkSize ) {

			const u8 = new Uint8Array( array.buffer, array.byteOffset, array.byteLength );
			for ( let i = 0; i < array.byteLength; i += chunkSize ) {

				for ( let j = i + chunkSize - 1, k = i; j > k; j --, k ++ ) {

					const tmp = u8[ k ];
					u8[ k ] = u8[ j ];
					u8[ j ] = tmp;

				}

			}

			return array;

		}

		//parse the header
		function parseHeader( header ) {

			let data, field, fn, i, l, m, _i, _len;
			const lines = header.split( /\r?\n/ );
			for ( _i = 0, _len = lines.length; _i < _len; _i ++ ) {

				l = lines[ _i ];
				if ( l.match( /NRRD\d+/ ) ) {

					headerObject.isNrrd = true;

				} else if ( ! l.match( /^#/ ) && ( m = l.match( /(.*):(.*)/ ) ) ) {

					field = m[ 1 ].trim();
					data = m[ 2 ].trim();
					fn = _fieldFunctions[ field ];
					if ( fn ) {

						fn.call( headerObject, data );

					} else {

						headerObject[ field ] = data;

					}

				}

			}

			if ( ! headerObject.isNrrd ) {

				throw new Error( 'Not an NRRD file' );

			}

			if ( headerObject.encoding === 'bz2' || headerObject.encoding === 'bzip2' ) {

				throw new Error( 'Bzip is not supported' );

			}

			if ( ! headerObject.vectors ) {

				//if no space direction is set, let's use the identity
				headerObject.vectors = [ ];
				headerObject.vectors.push( [ 1, 0, 0 ] );
				headerObject.vectors.push( [ 0, 1, 0 ] );
				headerObject.vectors.push( [ 0, 0, 1 ] );

				//apply spacing if defined
				if ( headerObject.spacings ) {

					for ( i = 0; i <= 2; i ++ ) {

						if ( ! isNaN( headerObject.spacings[ i ] ) ) {

							for ( let j = 0; j <= 2; j ++ ) {

								headerObject.vectors[ i ][ j ] *= headerObject.spacings[ i ];

							}

						}

					}

				}

			}

		}

		//parse the data when registered as one of this type : 'text', 'ascii', 'txt'
		function parseDataAsText( data, start, end ) {

			let number = '';
			start = start || 0;
			end = end || data.length;
			let value;
			//length of the result is the product of the sizes
			const lengthOfTheResult = headerObject.sizes.reduce( function ( previous, current ) {

				return previous * current;

			}, 1 );

			let base = 10;
			if ( headerObject.encoding === 'hex' ) {

				base = 16;

			}

			const result = new headerObject.__array( lengthOfTheResult );
			let resultIndex = 0;
			let parsingFunction = parseInt;
			if ( headerObject.__array === Float32Array || headerObject.__array === Float64Array ) {

				parsingFunction = parseFloat;

			}

			for ( let i = start; i < end; i ++ ) {

				value = data[ i ];
				//if value is not a space
				if ( ( value < 9 || value > 13 ) && value !== 32 ) {

					number += String.fromCharCode( value );

				} else {

					if ( number !== '' ) {

						result[ resultIndex ] = parsingFunction( number, base );
						resultIndex ++;

					}

					number = '';

				}

			}

			if ( number !== '' ) {

				result[ resultIndex ] = parsingFunction( number, base );
				resultIndex ++;

			}

			return result;

		}

		const _bytes = scan( 'uchar', data.byteLength );
		const _length = _bytes.length;
		let _header = null;
		let _data_start = 0;
		let i;
		for ( i = 1; i < _length; i ++ ) {

			if ( _bytes[ i - 1 ] == 10 && _bytes[ i ] == 10 ) {

				// we found two line breaks in a row
				// now we know what the header is
				_header = this._parseChars( _bytes, 0, i - 2 );
				// this is were the data starts
				_data_start = i + 1;
				break;

			}

		}

		// parse the header
		parseHeader( _header );

		_data = _bytes.subarray( _data_start ); // the data without header
		if ( headerObject.encoding.substring( 0, 2 ) === 'gz' ) {

			// we need to decompress the datastream
			// here we start the unzipping and get a typed Uint8Array back
			_data = fflate.gunzipSync( new Uint8Array( _data ) );

		} else if ( headerObject.encoding === 'ascii' || headerObject.encoding === 'text' || headerObject.encoding === 'txt' || headerObject.encoding === 'hex' ) {

			_data = parseDataAsText( _data );

		} else if ( headerObject.encoding === 'raw' ) {

			//we need to copy the array to create a new array buffer, else we retrieve the original arraybuffer with the header
			const _copy = new Uint8Array( _data.length );

			for ( let i = 0; i < _data.length; i ++ ) {

				_copy[ i ] = _data[ i ];

			}

			_data = _copy;

		}

		// .. let's use the underlying array buffer
		_data = _data.buffer;

		const volume = new Volume();
		volume.header = headerObject;
		volume.segmentation = this.segmentation;
		//
		// parse the (unzipped) data to a datastream of the correct type
		//
		volume.data = new headerObject.__array( _data );
		// get the min and max intensities
		const min_max = volume.computeMinMax();
		const min = min_max[ 0 ];
		const max = min_max[ 1 ];
		// attach the scalar range to the volume
		volume.windowLow = min;
		volume.windowHigh = max;

		// get the image dimensions
		volume.dimensions = [ headerObject.sizes[ 0 ], headerObject.sizes[ 1 ], headerObject.sizes[ 2 ] ];
		volume.xLength = volume.dimensions[ 0 ];
		volume.yLength = volume.dimensions[ 1 ];
		volume.zLength = volume.dimensions[ 2 ];

		// Identify axis order in the space-directions matrix from the header if possible.
		if ( headerObject.vectors ) {

			const xIndex = headerObject.vectors.findIndex( vector => vector[ 0 ] !== 0 );
			const yIndex = headerObject.vectors.findIndex( vector => vector[ 1 ] !== 0 );
			const zIndex = headerObject.vectors.findIndex( vector => vector[ 2 ] !== 0 );

			const axisOrder = [];

			if ( xIndex !== yIndex && xIndex !== zIndex && yIndex !== zIndex ) {

				axisOrder[ xIndex ] = 'x';
				axisOrder[ yIndex ] = 'y';
				axisOrder[ zIndex ] = 'z';

			} else {

				axisOrder[ 0 ] = 'x';
				axisOrder[ 1 ] = 'y';
				axisOrder[ 2 ] = 'z';

			}

			volume.axisOrder = axisOrder;

		} else {

			volume.axisOrder = [ 'x', 'y', 'z' ];

		}

		// spacing
		const spacingX = new Vector3().fromArray( headerObject.vectors[ 0 ] ).length();
		const spacingY = new Vector3().fromArray( headerObject.vectors[ 1 ] ).length();
		const spacingZ = new Vector3().fromArray( headerObject.vectors[ 2 ] ).length();
		volume.spacing = [ spacingX, spacingY, spacingZ ];


		// Create IJKtoRAS matrix
		volume.matrix = new Matrix4();

		const transitionMatrix = new Matrix4();

		if ( headerObject.space === 'left-posterior-superior' ) {

			transitionMatrix.set(
				- 1, 0, 0, 0,
				0, - 1, 0, 0,
				0, 0, 1, 0,
				0, 0, 0, 1
			);

		} else if ( headerObject.space === 'left-anterior-superior' ) {

			transitionMatrix.set(
				1, 0, 0, 0,
				0, 1, 0, 0,
				0, 0, - 1, 0,
				0, 0, 0, 1
			);

		}


		if ( ! headerObject.vectors ) {

			volume.matrix.set(
				1, 0, 0, 0,
				0, 1, 0, 0,
				0, 0, 1, 0,
				0, 0, 0, 1 );

		} else {

			const v = headerObject.vectors;

			const ijk_to_transition = new Matrix4().set(
				v[ 0 ][ 0 ], v[ 1 ][ 0 ], v[ 2 ][ 0 ], 0,
				v[ 0 ][ 1 ], v[ 1 ][ 1 ], v[ 2 ][ 1 ], 0,
				v[ 0 ][ 2 ], v[ 1 ][ 2 ], v[ 2 ][ 2 ], 0,
				0, 0, 0, 1
			);

			const transition_to_ras = new Matrix4().multiplyMatrices( ijk_to_transition, transitionMatrix );

			volume.matrix = transition_to_ras;

		}

		volume.inverseMatrix = new Matrix4();
		volume.inverseMatrix.copy( volume.matrix ).invert();

		volume.RASDimensions = [
			Math.floor( volume.xLength * spacingX ),
			Math.floor( volume.yLength * spacingY ),
			Math.floor( volume.zLength * spacingZ )
		];

		// .. and set the default threshold
		// only if the threshold was not already set
		if ( volume.lowerThreshold === - Infinity ) {

			volume.lowerThreshold = min;

		}

		if ( volume.upperThreshold === Infinity ) {

			volume.upperThreshold = max;

		}

		return volume;

	}
```
</details>

### `NRRDLoader._parseChars(array: any, start: any, end: any): string`

**Parameters:**

- **`array`** `any`
- **`start`** `any`
- **`end`** `any`

**Returns:** `string`

**Calls:**

- `String.fromCharCode`

**Internal Comments:**
```
// without borders, use the whole array
// create and append the chars (x2)
```

<details><summary>Code</summary>

```typescript
_parseChars( array, start, end ) {

		// without borders, use the whole array
		if ( start === undefined ) {

			start = 0;

		}

		if ( end === undefined ) {

			end = array.length;

		}

		let output = '';
		// create and append the chars
		let i = 0;
		for ( i = start; i < end; ++ i ) {

			output += String.fromCharCode( array[ i ] );

		}

		return output;

	}
```
</details>

### `scan(type: any, chunks: any): Uint8Array<ArrayBuffer>`

**Parameters:**

- **`type`** `any`
- **`chunks`** `any`

**Returns:** `Uint8Array<ArrayBuffer>`

**Calls:**

- `_data.slice`
- `flipEndianness`

**Internal Comments:**
```
// 1 byte data types
// 2 byte data types
// 4 byte data types
// increase the data pointer in-place (x2)
// if required, flip the endianness of the bytes
// we need to flip here since the format doesn't match the native endianness (x3)
// return the byte array
```

<details><summary>Code</summary>

```typescript
function scan( type, chunks ) {

			let _chunkSize = 1;
			let _array_type = Uint8Array;

			switch ( type ) {

				// 1 byte data types
				case 'uchar':
					break;
				case 'schar':
					_array_type = Int8Array;
					break;
				// 2 byte data types
				case 'ushort':
					_array_type = Uint16Array;
					_chunkSize = 2;
					break;
				case 'sshort':
					_array_type = Int16Array;
					_chunkSize = 2;
					break;
				// 4 byte data types
				case 'uint':
					_array_type = Uint32Array;
					_chunkSize = 4;
					break;
				case 'sint':
					_array_type = Int32Array;
					_chunkSize = 4;
					break;
				case 'float':
					_array_type = Float32Array;
					_chunkSize = 4;
					break;
				case 'complex':
					_array_type = Float64Array;
					_chunkSize = 8;
					break;
				case 'double':
					_array_type = Float64Array;
					_chunkSize = 8;
					break;

			}

			// increase the data pointer in-place
			let _bytes = new _array_type( _data.slice( _dataPointer,
				_dataPointer += chunks * _chunkSize ) );

			// if required, flip the endianness of the bytes
			if ( _nativeLittleEndian != _littleEndian ) {

				// we need to flip here since the format doesn't match the native endianness
				_bytes = flipEndianness( _bytes, _chunkSize );

			}

			// return the byte array
			return _bytes;

		}
```
</details>

### `flipEndianness(array: any, chunkSize: any): any`

**Parameters:**

- **`array`** `any`
- **`chunkSize`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function flipEndianness( array, chunkSize ) {

			const u8 = new Uint8Array( array.buffer, array.byteOffset, array.byteLength );
			for ( let i = 0; i < array.byteLength; i += chunkSize ) {

				for ( let j = i + chunkSize - 1, k = i; j > k; j --, k ++ ) {

					const tmp = u8[ k ];
					u8[ k ] = u8[ j ];
					u8[ j ] = tmp;

				}

			}

			return array;

		}
```
</details>

### `parseHeader(header: any): void`

**Parameters:**

- **`header`** `any`

**Returns:** `void`

**Calls:**

- `header.split`
- `l.match`
- `m[ 1 ].trim`
- `m[ 2 ].trim`
- `fn.call`
- `headerObject.vectors.push`
- `isNaN`

**Internal Comments:**
```
//if no space direction is set, let's use the identity (x4)
//apply spacing if defined
```

<details><summary>Code</summary>

```typescript
function parseHeader( header ) {

			let data, field, fn, i, l, m, _i, _len;
			const lines = header.split( /\r?\n/ );
			for ( _i = 0, _len = lines.length; _i < _len; _i ++ ) {

				l = lines[ _i ];
				if ( l.match( /NRRD\d+/ ) ) {

					headerObject.isNrrd = true;

				} else if ( ! l.match( /^#/ ) && ( m = l.match( /(.*):(.*)/ ) ) ) {

					field = m[ 1 ].trim();
					data = m[ 2 ].trim();
					fn = _fieldFunctions[ field ];
					if ( fn ) {

						fn.call( headerObject, data );

					} else {

						headerObject[ field ] = data;

					}

				}

			}

			if ( ! headerObject.isNrrd ) {

				throw new Error( 'Not an NRRD file' );

			}

			if ( headerObject.encoding === 'bz2' || headerObject.encoding === 'bzip2' ) {

				throw new Error( 'Bzip is not supported' );

			}

			if ( ! headerObject.vectors ) {

				//if no space direction is set, let's use the identity
				headerObject.vectors = [ ];
				headerObject.vectors.push( [ 1, 0, 0 ] );
				headerObject.vectors.push( [ 0, 1, 0 ] );
				headerObject.vectors.push( [ 0, 0, 1 ] );

				//apply spacing if defined
				if ( headerObject.spacings ) {

					for ( i = 0; i <= 2; i ++ ) {

						if ( ! isNaN( headerObject.spacings[ i ] ) ) {

							for ( let j = 0; j <= 2; j ++ ) {

								headerObject.vectors[ i ][ j ] *= headerObject.spacings[ i ];

							}

						}

					}

				}

			}

		}
```
</details>

### `parseDataAsText(data: any, start: any, end: any): any`

**Parameters:**

- **`data`** `any`
- **`start`** `any`
- **`end`** `any`

**Returns:** `any`

**Calls:**

- `headerObject.sizes.reduce`
- `String.fromCharCode`
- `parsingFunction`

**Internal Comments:**
```
//length of the result is the product of the sizes (x2)
//if value is not a space
```

<details><summary>Code</summary>

```typescript
function parseDataAsText( data, start, end ) {

			let number = '';
			start = start || 0;
			end = end || data.length;
			let value;
			//length of the result is the product of the sizes
			const lengthOfTheResult = headerObject.sizes.reduce( function ( previous, current ) {

				return previous * current;

			}, 1 );

			let base = 10;
			if ( headerObject.encoding === 'hex' ) {

				base = 16;

			}

			const result = new headerObject.__array( lengthOfTheResult );
			let resultIndex = 0;
			let parsingFunction = parseInt;
			if ( headerObject.__array === Float32Array || headerObject.__array === Float64Array ) {

				parsingFunction = parseFloat;

			}

			for ( let i = start; i < end; i ++ ) {

				value = data[ i ];
				//if value is not a space
				if ( ( value < 9 || value > 13 ) && value !== 32 ) {

					number += String.fromCharCode( value );

				} else {

					if ( number !== '' ) {

						result[ resultIndex ] = parsingFunction( number, base );
						resultIndex ++;

					}

					number = '';

				}

			}

			if ( number !== '' ) {

				result[ resultIndex ] = parsingFunction( number, base );
				resultIndex ++;

			}

			return result;

		}
```
</details>

### `type(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		switch ( data ) {

			case 'uchar':
			case 'unsigned char':
			case 'uint8':
			case 'uint8_t':
				this.__array = Uint8Array;
				break;
			case 'signed char':
			case 'int8':
			case 'int8_t':
				this.__array = Int8Array;
				break;
			case 'short':
			case 'short int':
			case 'signed short':
			case 'signed short int':
			case 'int16':
			case 'int16_t':
				this.__array = Int16Array;
				break;
			case 'ushort':
			case 'unsigned short':
			case 'unsigned short int':
			case 'uint16':
			case 'uint16_t':
				this.__array = Uint16Array;
				break;
			case 'int':
			case 'signed int':
			case 'int32':
			case 'int32_t':
				this.__array = Int32Array;
				break;
			case 'uint':
			case 'unsigned int':
			case 'uint32':
			case 'uint32_t':
				this.__array = Uint32Array;
				break;
			case 'float':
				this.__array = Float32Array;
				break;
			case 'double':
				this.__array = Float64Array;
				break;
			default:
				throw new Error( 'Unsupported NRRD data type: ' + data );

		}

		return this.type = data;

	}
```
</details>

### `endian(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.endian = data;

	}
```
</details>

### `encoding(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.encoding = data;

	}
```
</details>

### `dimension(data: any): number`

**Parameters:**

- **`data`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.dim = parseInt( data, 10 );

	}
```
</details>

### `sizes(data: any): number[]`

**Parameters:**

- **`data`** `any`

**Returns:** `number[]`

**Calls:**

- `complex_call_13200`
- `data.split`
- `_results.push`
- `parseInt`

<details><summary>Code</summary>

```typescript
function ( data ) {

		let i;
		return this.sizes = ( function () {

			const _ref = data.split( /\s+/ );
			const _results = [];

			for ( let _i = 0, _len = _ref.length; _i < _len; _i ++ ) {

				i = _ref[ _i ];
				_results.push( parseInt( i, 10 ) );

			}

			return _results;

		} )();

	}
```
</details>

### `space(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.space = data;

	}
```
</details>

### `spacings(data: any): number[]`

**Parameters:**

- **`data`** `any`

**Returns:** `number[]`

**Calls:**

- `data.split`
- `complex_call_14319`
- `_results.push`
- `parseFloat`

<details><summary>Code</summary>

```typescript
function ( data ) {

		let f;
		const parts = data.split( /\s+/ );
		return this.spacings = ( function () {

			const _results = [];

			for ( let _i = 0, _len = parts.length; _i < _len; _i ++ ) {

				f = parts[ _i ];
				_results.push( parseFloat( f ) );

			}

			return _results;

		} )();

	}
```
</details>

### `type(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		switch ( data ) {

			case 'uchar':
			case 'unsigned char':
			case 'uint8':
			case 'uint8_t':
				this.__array = Uint8Array;
				break;
			case 'signed char':
			case 'int8':
			case 'int8_t':
				this.__array = Int8Array;
				break;
			case 'short':
			case 'short int':
			case 'signed short':
			case 'signed short int':
			case 'int16':
			case 'int16_t':
				this.__array = Int16Array;
				break;
			case 'ushort':
			case 'unsigned short':
			case 'unsigned short int':
			case 'uint16':
			case 'uint16_t':
				this.__array = Uint16Array;
				break;
			case 'int':
			case 'signed int':
			case 'int32':
			case 'int32_t':
				this.__array = Int32Array;
				break;
			case 'uint':
			case 'unsigned int':
			case 'uint32':
			case 'uint32_t':
				this.__array = Uint32Array;
				break;
			case 'float':
				this.__array = Float32Array;
				break;
			case 'double':
				this.__array = Float64Array;
				break;
			default:
				throw new Error( 'Unsupported NRRD data type: ' + data );

		}

		return this.type = data;

	}
```
</details>

### `endian(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.endian = data;

	}
```
</details>

### `encoding(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.encoding = data;

	}
```
</details>

### `dimension(data: any): number`

**Parameters:**

- **`data`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.dim = parseInt( data, 10 );

	}
```
</details>

### `sizes(data: any): number[]`

**Parameters:**

- **`data`** `any`

**Returns:** `number[]`

**Calls:**

- `complex_call_13200`
- `data.split`
- `_results.push`
- `parseInt`

<details><summary>Code</summary>

```typescript
function ( data ) {

		let i;
		return this.sizes = ( function () {

			const _ref = data.split( /\s+/ );
			const _results = [];

			for ( let _i = 0, _len = _ref.length; _i < _len; _i ++ ) {

				i = _ref[ _i ];
				_results.push( parseInt( i, 10 ) );

			}

			return _results;

		} )();

	}
```
</details>

### `space(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.space = data;

	}
```
</details>

### `spacings(data: any): number[]`

**Parameters:**

- **`data`** `any`

**Returns:** `number[]`

**Calls:**

- `data.split`
- `complex_call_14319`
- `_results.push`
- `parseFloat`

<details><summary>Code</summary>

```typescript
function ( data ) {

		let f;
		const parts = data.split( /\s+/ );
		return this.spacings = ( function () {

			const _results = [];

			for ( let _i = 0, _len = parts.length; _i < _len; _i ++ ) {

				f = parts[ _i ];
				_results.push( parseFloat( f ) );

			}

			return _results;

		} )();

	}
```
</details>

### `type(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		switch ( data ) {

			case 'uchar':
			case 'unsigned char':
			case 'uint8':
			case 'uint8_t':
				this.__array = Uint8Array;
				break;
			case 'signed char':
			case 'int8':
			case 'int8_t':
				this.__array = Int8Array;
				break;
			case 'short':
			case 'short int':
			case 'signed short':
			case 'signed short int':
			case 'int16':
			case 'int16_t':
				this.__array = Int16Array;
				break;
			case 'ushort':
			case 'unsigned short':
			case 'unsigned short int':
			case 'uint16':
			case 'uint16_t':
				this.__array = Uint16Array;
				break;
			case 'int':
			case 'signed int':
			case 'int32':
			case 'int32_t':
				this.__array = Int32Array;
				break;
			case 'uint':
			case 'unsigned int':
			case 'uint32':
			case 'uint32_t':
				this.__array = Uint32Array;
				break;
			case 'float':
				this.__array = Float32Array;
				break;
			case 'double':
				this.__array = Float64Array;
				break;
			default:
				throw new Error( 'Unsupported NRRD data type: ' + data );

		}

		return this.type = data;

	}
```
</details>

### `endian(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.endian = data;

	}
```
</details>

### `encoding(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.encoding = data;

	}
```
</details>

### `dimension(data: any): number`

**Parameters:**

- **`data`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.dim = parseInt( data, 10 );

	}
```
</details>

### `sizes(data: any): number[]`

**Parameters:**

- **`data`** `any`

**Returns:** `number[]`

**Calls:**

- `complex_call_13200`
- `data.split`
- `_results.push`
- `parseInt`

<details><summary>Code</summary>

```typescript
function ( data ) {

		let i;
		return this.sizes = ( function () {

			const _ref = data.split( /\s+/ );
			const _results = [];

			for ( let _i = 0, _len = _ref.length; _i < _len; _i ++ ) {

				i = _ref[ _i ];
				_results.push( parseInt( i, 10 ) );

			}

			return _results;

		} )();

	}
```
</details>

### `space(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.space = data;

	}
```
</details>

### `spacings(data: any): number[]`

**Parameters:**

- **`data`** `any`

**Returns:** `number[]`

**Calls:**

- `data.split`
- `complex_call_14319`
- `_results.push`
- `parseFloat`

<details><summary>Code</summary>

```typescript
function ( data ) {

		let f;
		const parts = data.split( /\s+/ );
		return this.spacings = ( function () {

			const _results = [];

			for ( let _i = 0, _len = parts.length; _i < _len; _i ++ ) {

				f = parts[ _i ];
				_results.push( parseFloat( f ) );

			}

			return _results;

		} )();

	}
```
</details>

### `type(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		switch ( data ) {

			case 'uchar':
			case 'unsigned char':
			case 'uint8':
			case 'uint8_t':
				this.__array = Uint8Array;
				break;
			case 'signed char':
			case 'int8':
			case 'int8_t':
				this.__array = Int8Array;
				break;
			case 'short':
			case 'short int':
			case 'signed short':
			case 'signed short int':
			case 'int16':
			case 'int16_t':
				this.__array = Int16Array;
				break;
			case 'ushort':
			case 'unsigned short':
			case 'unsigned short int':
			case 'uint16':
			case 'uint16_t':
				this.__array = Uint16Array;
				break;
			case 'int':
			case 'signed int':
			case 'int32':
			case 'int32_t':
				this.__array = Int32Array;
				break;
			case 'uint':
			case 'unsigned int':
			case 'uint32':
			case 'uint32_t':
				this.__array = Uint32Array;
				break;
			case 'float':
				this.__array = Float32Array;
				break;
			case 'double':
				this.__array = Float64Array;
				break;
			default:
				throw new Error( 'Unsupported NRRD data type: ' + data );

		}

		return this.type = data;

	}
```
</details>

### `endian(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.endian = data;

	}
```
</details>

### `encoding(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.encoding = data;

	}
```
</details>

### `dimension(data: any): number`

**Parameters:**

- **`data`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.dim = parseInt( data, 10 );

	}
```
</details>

### `sizes(data: any): number[]`

**Parameters:**

- **`data`** `any`

**Returns:** `number[]`

**Calls:**

- `complex_call_13200`
- `data.split`
- `_results.push`
- `parseInt`

<details><summary>Code</summary>

```typescript
function ( data ) {

		let i;
		return this.sizes = ( function () {

			const _ref = data.split( /\s+/ );
			const _results = [];

			for ( let _i = 0, _len = _ref.length; _i < _len; _i ++ ) {

				i = _ref[ _i ];
				_results.push( parseInt( i, 10 ) );

			}

			return _results;

		} )();

	}
```
</details>

### `space(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.space = data;

	}
```
</details>

### `spacings(data: any): number[]`

**Parameters:**

- **`data`** `any`

**Returns:** `number[]`

**Calls:**

- `data.split`
- `complex_call_14319`
- `_results.push`
- `parseFloat`

<details><summary>Code</summary>

```typescript
function ( data ) {

		let f;
		const parts = data.split( /\s+/ );
		return this.spacings = ( function () {

			const _results = [];

			for ( let _i = 0, _len = parts.length; _i < _len; _i ++ ) {

				f = parts[ _i ];
				_results.push( parseFloat( f ) );

			}

			return _results;

		} )();

	}
```
</details>

### `type(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		switch ( data ) {

			case 'uchar':
			case 'unsigned char':
			case 'uint8':
			case 'uint8_t':
				this.__array = Uint8Array;
				break;
			case 'signed char':
			case 'int8':
			case 'int8_t':
				this.__array = Int8Array;
				break;
			case 'short':
			case 'short int':
			case 'signed short':
			case 'signed short int':
			case 'int16':
			case 'int16_t':
				this.__array = Int16Array;
				break;
			case 'ushort':
			case 'unsigned short':
			case 'unsigned short int':
			case 'uint16':
			case 'uint16_t':
				this.__array = Uint16Array;
				break;
			case 'int':
			case 'signed int':
			case 'int32':
			case 'int32_t':
				this.__array = Int32Array;
				break;
			case 'uint':
			case 'unsigned int':
			case 'uint32':
			case 'uint32_t':
				this.__array = Uint32Array;
				break;
			case 'float':
				this.__array = Float32Array;
				break;
			case 'double':
				this.__array = Float64Array;
				break;
			default:
				throw new Error( 'Unsupported NRRD data type: ' + data );

		}

		return this.type = data;

	}
```
</details>

### `endian(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.endian = data;

	}
```
</details>

### `encoding(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.encoding = data;

	}
```
</details>

### `dimension(data: any): number`

**Parameters:**

- **`data`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.dim = parseInt( data, 10 );

	}
```
</details>

### `sizes(data: any): number[]`

**Parameters:**

- **`data`** `any`

**Returns:** `number[]`

**Calls:**

- `complex_call_13200`
- `data.split`
- `_results.push`
- `parseInt`

<details><summary>Code</summary>

```typescript
function ( data ) {

		let i;
		return this.sizes = ( function () {

			const _ref = data.split( /\s+/ );
			const _results = [];

			for ( let _i = 0, _len = _ref.length; _i < _len; _i ++ ) {

				i = _ref[ _i ];
				_results.push( parseInt( i, 10 ) );

			}

			return _results;

		} )();

	}
```
</details>

### `space(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.space = data;

	}
```
</details>

### `spacings(data: any): number[]`

**Parameters:**

- **`data`** `any`

**Returns:** `number[]`

**Calls:**

- `data.split`
- `complex_call_14319`
- `_results.push`
- `parseFloat`

<details><summary>Code</summary>

```typescript
function ( data ) {

		let f;
		const parts = data.split( /\s+/ );
		return this.spacings = ( function () {

			const _results = [];

			for ( let _i = 0, _len = parts.length; _i < _len; _i ++ ) {

				f = parts[ _i ];
				_results.push( parseFloat( f ) );

			}

			return _results;

		} )();

	}
```
</details>

### `type(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		switch ( data ) {

			case 'uchar':
			case 'unsigned char':
			case 'uint8':
			case 'uint8_t':
				this.__array = Uint8Array;
				break;
			case 'signed char':
			case 'int8':
			case 'int8_t':
				this.__array = Int8Array;
				break;
			case 'short':
			case 'short int':
			case 'signed short':
			case 'signed short int':
			case 'int16':
			case 'int16_t':
				this.__array = Int16Array;
				break;
			case 'ushort':
			case 'unsigned short':
			case 'unsigned short int':
			case 'uint16':
			case 'uint16_t':
				this.__array = Uint16Array;
				break;
			case 'int':
			case 'signed int':
			case 'int32':
			case 'int32_t':
				this.__array = Int32Array;
				break;
			case 'uint':
			case 'unsigned int':
			case 'uint32':
			case 'uint32_t':
				this.__array = Uint32Array;
				break;
			case 'float':
				this.__array = Float32Array;
				break;
			case 'double':
				this.__array = Float64Array;
				break;
			default:
				throw new Error( 'Unsupported NRRD data type: ' + data );

		}

		return this.type = data;

	}
```
</details>

### `endian(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.endian = data;

	}
```
</details>

### `encoding(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.encoding = data;

	}
```
</details>

### `dimension(data: any): number`

**Parameters:**

- **`data`** `any`

**Returns:** `number`

**Calls:**

- `parseInt`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.dim = parseInt( data, 10 );

	}
```
</details>

### `sizes(data: any): number[]`

**Parameters:**

- **`data`** `any`

**Returns:** `number[]`

**Calls:**

- `complex_call_13200`
- `data.split`
- `_results.push`
- `parseInt`

<details><summary>Code</summary>

```typescript
function ( data ) {

		let i;
		return this.sizes = ( function () {

			const _ref = data.split( /\s+/ );
			const _results = [];

			for ( let _i = 0, _len = _ref.length; _i < _len; _i ++ ) {

				i = _ref[ _i ];
				_results.push( parseInt( i, 10 ) );

			}

			return _results;

		} )();

	}
```
</details>

### `space(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( data ) {

		return this.space = data;

	}
```
</details>

### `spacings(data: any): number[]`

**Parameters:**

- **`data`** `any`

**Returns:** `number[]`

**Calls:**

- `data.split`
- `complex_call_14319`
- `_results.push`
- `parseFloat`

<details><summary>Code</summary>

```typescript
function ( data ) {

		let f;
		const parts = data.split( /\s+/ );
		return this.spacings = ( function () {

			const _results = [];

			for ( let _i = 0, _len = parts.length; _i < _len; _i ++ ) {

				f = parts[ _i ];
				_results.push( parseFloat( f ) );

			}

			return _results;

		} )();

	}
```
</details>


---

## Classes

### `NRRDLoader`

<details><summary>Class Code</summary>

```ts
class NRRDLoader extends Loader {

	/**
	 * Constructs a new NRRD loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Starts loading from the given URL and passes the loaded NRRD asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Volume)} onLoad - Executed when the loading process has been finished.
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
	 * Toggles the segmentation mode.
	 *
	 * @param {boolean} segmentation - Whether to use segmentation mode or not.
	 */
	setSegmentation( segmentation ) {

		this.segmentation = segmentation;

	}

	/**
	 * Parses the given NRRD data and returns the resulting volume data.
	 *
	 * @param {ArrayBuffer} data - The raw NRRD data as an array buffer.
	 * @return {Volume} The parsed volume.
	 */
	parse( data ) {

		// this parser is largely inspired from the XTK NRRD parser : https://github.com/xtk/X

		let _data = data;

		let _dataPointer = 0;

		const _nativeLittleEndian = new Int8Array( new Int16Array( [ 1 ] ).buffer )[ 0 ] > 0;

		const _littleEndian = true;

		const headerObject = {};

		function scan( type, chunks ) {

			let _chunkSize = 1;
			let _array_type = Uint8Array;

			switch ( type ) {

				// 1 byte data types
				case 'uchar':
					break;
				case 'schar':
					_array_type = Int8Array;
					break;
				// 2 byte data types
				case 'ushort':
					_array_type = Uint16Array;
					_chunkSize = 2;
					break;
				case 'sshort':
					_array_type = Int16Array;
					_chunkSize = 2;
					break;
				// 4 byte data types
				case 'uint':
					_array_type = Uint32Array;
					_chunkSize = 4;
					break;
				case 'sint':
					_array_type = Int32Array;
					_chunkSize = 4;
					break;
				case 'float':
					_array_type = Float32Array;
					_chunkSize = 4;
					break;
				case 'complex':
					_array_type = Float64Array;
					_chunkSize = 8;
					break;
				case 'double':
					_array_type = Float64Array;
					_chunkSize = 8;
					break;

			}

			// increase the data pointer in-place
			let _bytes = new _array_type( _data.slice( _dataPointer,
				_dataPointer += chunks * _chunkSize ) );

			// if required, flip the endianness of the bytes
			if ( _nativeLittleEndian != _littleEndian ) {

				// we need to flip here since the format doesn't match the native endianness
				_bytes = flipEndianness( _bytes, _chunkSize );

			}

			// return the byte array
			return _bytes;

		}

		//Flips typed array endianness in-place. Based on https://github.com/kig/DataStream.js/blob/master/DataStream.js.

		function flipEndianness( array, chunkSize ) {

			const u8 = new Uint8Array( array.buffer, array.byteOffset, array.byteLength );
			for ( let i = 0; i < array.byteLength; i += chunkSize ) {

				for ( let j = i + chunkSize - 1, k = i; j > k; j --, k ++ ) {

					const tmp = u8[ k ];
					u8[ k ] = u8[ j ];
					u8[ j ] = tmp;

				}

			}

			return array;

		}

		//parse the header
		function parseHeader( header ) {

			let data, field, fn, i, l, m, _i, _len;
			const lines = header.split( /\r?\n/ );
			for ( _i = 0, _len = lines.length; _i < _len; _i ++ ) {

				l = lines[ _i ];
				if ( l.match( /NRRD\d+/ ) ) {

					headerObject.isNrrd = true;

				} else if ( ! l.match( /^#/ ) && ( m = l.match( /(.*):(.*)/ ) ) ) {

					field = m[ 1 ].trim();
					data = m[ 2 ].trim();
					fn = _fieldFunctions[ field ];
					if ( fn ) {

						fn.call( headerObject, data );

					} else {

						headerObject[ field ] = data;

					}

				}

			}

			if ( ! headerObject.isNrrd ) {

				throw new Error( 'Not an NRRD file' );

			}

			if ( headerObject.encoding === 'bz2' || headerObject.encoding === 'bzip2' ) {

				throw new Error( 'Bzip is not supported' );

			}

			if ( ! headerObject.vectors ) {

				//if no space direction is set, let's use the identity
				headerObject.vectors = [ ];
				headerObject.vectors.push( [ 1, 0, 0 ] );
				headerObject.vectors.push( [ 0, 1, 0 ] );
				headerObject.vectors.push( [ 0, 0, 1 ] );

				//apply spacing if defined
				if ( headerObject.spacings ) {

					for ( i = 0; i <= 2; i ++ ) {

						if ( ! isNaN( headerObject.spacings[ i ] ) ) {

							for ( let j = 0; j <= 2; j ++ ) {

								headerObject.vectors[ i ][ j ] *= headerObject.spacings[ i ];

							}

						}

					}

				}

			}

		}

		//parse the data when registered as one of this type : 'text', 'ascii', 'txt'
		function parseDataAsText( data, start, end ) {

			let number = '';
			start = start || 0;
			end = end || data.length;
			let value;
			//length of the result is the product of the sizes
			const lengthOfTheResult = headerObject.sizes.reduce( function ( previous, current ) {

				return previous * current;

			}, 1 );

			let base = 10;
			if ( headerObject.encoding === 'hex' ) {

				base = 16;

			}

			const result = new headerObject.__array( lengthOfTheResult );
			let resultIndex = 0;
			let parsingFunction = parseInt;
			if ( headerObject.__array === Float32Array || headerObject.__array === Float64Array ) {

				parsingFunction = parseFloat;

			}

			for ( let i = start; i < end; i ++ ) {

				value = data[ i ];
				//if value is not a space
				if ( ( value < 9 || value > 13 ) && value !== 32 ) {

					number += String.fromCharCode( value );

				} else {

					if ( number !== '' ) {

						result[ resultIndex ] = parsingFunction( number, base );
						resultIndex ++;

					}

					number = '';

				}

			}

			if ( number !== '' ) {

				result[ resultIndex ] = parsingFunction( number, base );
				resultIndex ++;

			}

			return result;

		}

		const _bytes = scan( 'uchar', data.byteLength );
		const _length = _bytes.length;
		let _header = null;
		let _data_start = 0;
		let i;
		for ( i = 1; i < _length; i ++ ) {

			if ( _bytes[ i - 1 ] == 10 && _bytes[ i ] == 10 ) {

				// we found two line breaks in a row
				// now we know what the header is
				_header = this._parseChars( _bytes, 0, i - 2 );
				// this is were the data starts
				_data_start = i + 1;
				break;

			}

		}

		// parse the header
		parseHeader( _header );

		_data = _bytes.subarray( _data_start ); // the data without header
		if ( headerObject.encoding.substring( 0, 2 ) === 'gz' ) {

			// we need to decompress the datastream
			// here we start the unzipping and get a typed Uint8Array back
			_data = fflate.gunzipSync( new Uint8Array( _data ) );

		} else if ( headerObject.encoding === 'ascii' || headerObject.encoding === 'text' || headerObject.encoding === 'txt' || headerObject.encoding === 'hex' ) {

			_data = parseDataAsText( _data );

		} else if ( headerObject.encoding === 'raw' ) {

			//we need to copy the array to create a new array buffer, else we retrieve the original arraybuffer with the header
			const _copy = new Uint8Array( _data.length );

			for ( let i = 0; i < _data.length; i ++ ) {

				_copy[ i ] = _data[ i ];

			}

			_data = _copy;

		}

		// .. let's use the underlying array buffer
		_data = _data.buffer;

		const volume = new Volume();
		volume.header = headerObject;
		volume.segmentation = this.segmentation;
		//
		// parse the (unzipped) data to a datastream of the correct type
		//
		volume.data = new headerObject.__array( _data );
		// get the min and max intensities
		const min_max = volume.computeMinMax();
		const min = min_max[ 0 ];
		const max = min_max[ 1 ];
		// attach the scalar range to the volume
		volume.windowLow = min;
		volume.windowHigh = max;

		// get the image dimensions
		volume.dimensions = [ headerObject.sizes[ 0 ], headerObject.sizes[ 1 ], headerObject.sizes[ 2 ] ];
		volume.xLength = volume.dimensions[ 0 ];
		volume.yLength = volume.dimensions[ 1 ];
		volume.zLength = volume.dimensions[ 2 ];

		// Identify axis order in the space-directions matrix from the header if possible.
		if ( headerObject.vectors ) {

			const xIndex = headerObject.vectors.findIndex( vector => vector[ 0 ] !== 0 );
			const yIndex = headerObject.vectors.findIndex( vector => vector[ 1 ] !== 0 );
			const zIndex = headerObject.vectors.findIndex( vector => vector[ 2 ] !== 0 );

			const axisOrder = [];

			if ( xIndex !== yIndex && xIndex !== zIndex && yIndex !== zIndex ) {

				axisOrder[ xIndex ] = 'x';
				axisOrder[ yIndex ] = 'y';
				axisOrder[ zIndex ] = 'z';

			} else {

				axisOrder[ 0 ] = 'x';
				axisOrder[ 1 ] = 'y';
				axisOrder[ 2 ] = 'z';

			}

			volume.axisOrder = axisOrder;

		} else {

			volume.axisOrder = [ 'x', 'y', 'z' ];

		}

		// spacing
		const spacingX = new Vector3().fromArray( headerObject.vectors[ 0 ] ).length();
		const spacingY = new Vector3().fromArray( headerObject.vectors[ 1 ] ).length();
		const spacingZ = new Vector3().fromArray( headerObject.vectors[ 2 ] ).length();
		volume.spacing = [ spacingX, spacingY, spacingZ ];


		// Create IJKtoRAS matrix
		volume.matrix = new Matrix4();

		const transitionMatrix = new Matrix4();

		if ( headerObject.space === 'left-posterior-superior' ) {

			transitionMatrix.set(
				- 1, 0, 0, 0,
				0, - 1, 0, 0,
				0, 0, 1, 0,
				0, 0, 0, 1
			);

		} else if ( headerObject.space === 'left-anterior-superior' ) {

			transitionMatrix.set(
				1, 0, 0, 0,
				0, 1, 0, 0,
				0, 0, - 1, 0,
				0, 0, 0, 1
			);

		}


		if ( ! headerObject.vectors ) {

			volume.matrix.set(
				1, 0, 0, 0,
				0, 1, 0, 0,
				0, 0, 1, 0,
				0, 0, 0, 1 );

		} else {

			const v = headerObject.vectors;

			const ijk_to_transition = new Matrix4().set(
				v[ 0 ][ 0 ], v[ 1 ][ 0 ], v[ 2 ][ 0 ], 0,
				v[ 0 ][ 1 ], v[ 1 ][ 1 ], v[ 2 ][ 1 ], 0,
				v[ 0 ][ 2 ], v[ 1 ][ 2 ], v[ 2 ][ 2 ], 0,
				0, 0, 0, 1
			);

			const transition_to_ras = new Matrix4().multiplyMatrices( ijk_to_transition, transitionMatrix );

			volume.matrix = transition_to_ras;

		}

		volume.inverseMatrix = new Matrix4();
		volume.inverseMatrix.copy( volume.matrix ).invert();

		volume.RASDimensions = [
			Math.floor( volume.xLength * spacingX ),
			Math.floor( volume.yLength * spacingY ),
			Math.floor( volume.zLength * spacingZ )
		];

		// .. and set the default threshold
		// only if the threshold was not already set
		if ( volume.lowerThreshold === - Infinity ) {

			volume.lowerThreshold = min;

		}

		if ( volume.upperThreshold === Infinity ) {

			volume.upperThreshold = max;

		}

		return volume;

	}

	_parseChars( array, start, end ) {

		// without borders, use the whole array
		if ( start === undefined ) {

			start = 0;

		}

		if ( end === undefined ) {

			end = array.length;

		}

		let output = '';
		// create and append the chars
		let i = 0;
		for ( i = start; i < end; ++ i ) {

			output += String.fromCharCode( array[ i ] );

		}

		return output;

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: Volume) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

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

##### `setSegmentation(segmentation: boolean): void`

<details><summary>Code</summary>

```ts
setSegmentation( segmentation ) {

		this.segmentation = segmentation;

	}
```
</details>

##### `parse(data: ArrayBuffer): Volume`

<details><summary>Code</summary>

```ts
parse( data ) {

		// this parser is largely inspired from the XTK NRRD parser : https://github.com/xtk/X

		let _data = data;

		let _dataPointer = 0;

		const _nativeLittleEndian = new Int8Array( new Int16Array( [ 1 ] ).buffer )[ 0 ] > 0;

		const _littleEndian = true;

		const headerObject = {};

		function scan( type, chunks ) {

			let _chunkSize = 1;
			let _array_type = Uint8Array;

			switch ( type ) {

				// 1 byte data types
				case 'uchar':
					break;
				case 'schar':
					_array_type = Int8Array;
					break;
				// 2 byte data types
				case 'ushort':
					_array_type = Uint16Array;
					_chunkSize = 2;
					break;
				case 'sshort':
					_array_type = Int16Array;
					_chunkSize = 2;
					break;
				// 4 byte data types
				case 'uint':
					_array_type = Uint32Array;
					_chunkSize = 4;
					break;
				case 'sint':
					_array_type = Int32Array;
					_chunkSize = 4;
					break;
				case 'float':
					_array_type = Float32Array;
					_chunkSize = 4;
					break;
				case 'complex':
					_array_type = Float64Array;
					_chunkSize = 8;
					break;
				case 'double':
					_array_type = Float64Array;
					_chunkSize = 8;
					break;

			}

			// increase the data pointer in-place
			let _bytes = new _array_type( _data.slice( _dataPointer,
				_dataPointer += chunks * _chunkSize ) );

			// if required, flip the endianness of the bytes
			if ( _nativeLittleEndian != _littleEndian ) {

				// we need to flip here since the format doesn't match the native endianness
				_bytes = flipEndianness( _bytes, _chunkSize );

			}

			// return the byte array
			return _bytes;

		}

		//Flips typed array endianness in-place. Based on https://github.com/kig/DataStream.js/blob/master/DataStream.js.

		function flipEndianness( array, chunkSize ) {

			const u8 = new Uint8Array( array.buffer, array.byteOffset, array.byteLength );
			for ( let i = 0; i < array.byteLength; i += chunkSize ) {

				for ( let j = i + chunkSize - 1, k = i; j > k; j --, k ++ ) {

					const tmp = u8[ k ];
					u8[ k ] = u8[ j ];
					u8[ j ] = tmp;

				}

			}

			return array;

		}

		//parse the header
		function parseHeader( header ) {

			let data, field, fn, i, l, m, _i, _len;
			const lines = header.split( /\r?\n/ );
			for ( _i = 0, _len = lines.length; _i < _len; _i ++ ) {

				l = lines[ _i ];
				if ( l.match( /NRRD\d+/ ) ) {

					headerObject.isNrrd = true;

				} else if ( ! l.match( /^#/ ) && ( m = l.match( /(.*):(.*)/ ) ) ) {

					field = m[ 1 ].trim();
					data = m[ 2 ].trim();
					fn = _fieldFunctions[ field ];
					if ( fn ) {

						fn.call( headerObject, data );

					} else {

						headerObject[ field ] = data;

					}

				}

			}

			if ( ! headerObject.isNrrd ) {

				throw new Error( 'Not an NRRD file' );

			}

			if ( headerObject.encoding === 'bz2' || headerObject.encoding === 'bzip2' ) {

				throw new Error( 'Bzip is not supported' );

			}

			if ( ! headerObject.vectors ) {

				//if no space direction is set, let's use the identity
				headerObject.vectors = [ ];
				headerObject.vectors.push( [ 1, 0, 0 ] );
				headerObject.vectors.push( [ 0, 1, 0 ] );
				headerObject.vectors.push( [ 0, 0, 1 ] );

				//apply spacing if defined
				if ( headerObject.spacings ) {

					for ( i = 0; i <= 2; i ++ ) {

						if ( ! isNaN( headerObject.spacings[ i ] ) ) {

							for ( let j = 0; j <= 2; j ++ ) {

								headerObject.vectors[ i ][ j ] *= headerObject.spacings[ i ];

							}

						}

					}

				}

			}

		}

		//parse the data when registered as one of this type : 'text', 'ascii', 'txt'
		function parseDataAsText( data, start, end ) {

			let number = '';
			start = start || 0;
			end = end || data.length;
			let value;
			//length of the result is the product of the sizes
			const lengthOfTheResult = headerObject.sizes.reduce( function ( previous, current ) {

				return previous * current;

			}, 1 );

			let base = 10;
			if ( headerObject.encoding === 'hex' ) {

				base = 16;

			}

			const result = new headerObject.__array( lengthOfTheResult );
			let resultIndex = 0;
			let parsingFunction = parseInt;
			if ( headerObject.__array === Float32Array || headerObject.__array === Float64Array ) {

				parsingFunction = parseFloat;

			}

			for ( let i = start; i < end; i ++ ) {

				value = data[ i ];
				//if value is not a space
				if ( ( value < 9 || value > 13 ) && value !== 32 ) {

					number += String.fromCharCode( value );

				} else {

					if ( number !== '' ) {

						result[ resultIndex ] = parsingFunction( number, base );
						resultIndex ++;

					}

					number = '';

				}

			}

			if ( number !== '' ) {

				result[ resultIndex ] = parsingFunction( number, base );
				resultIndex ++;

			}

			return result;

		}

		const _bytes = scan( 'uchar', data.byteLength );
		const _length = _bytes.length;
		let _header = null;
		let _data_start = 0;
		let i;
		for ( i = 1; i < _length; i ++ ) {

			if ( _bytes[ i - 1 ] == 10 && _bytes[ i ] == 10 ) {

				// we found two line breaks in a row
				// now we know what the header is
				_header = this._parseChars( _bytes, 0, i - 2 );
				// this is were the data starts
				_data_start = i + 1;
				break;

			}

		}

		// parse the header
		parseHeader( _header );

		_data = _bytes.subarray( _data_start ); // the data without header
		if ( headerObject.encoding.substring( 0, 2 ) === 'gz' ) {

			// we need to decompress the datastream
			// here we start the unzipping and get a typed Uint8Array back
			_data = fflate.gunzipSync( new Uint8Array( _data ) );

		} else if ( headerObject.encoding === 'ascii' || headerObject.encoding === 'text' || headerObject.encoding === 'txt' || headerObject.encoding === 'hex' ) {

			_data = parseDataAsText( _data );

		} else if ( headerObject.encoding === 'raw' ) {

			//we need to copy the array to create a new array buffer, else we retrieve the original arraybuffer with the header
			const _copy = new Uint8Array( _data.length );

			for ( let i = 0; i < _data.length; i ++ ) {

				_copy[ i ] = _data[ i ];

			}

			_data = _copy;

		}

		// .. let's use the underlying array buffer
		_data = _data.buffer;

		const volume = new Volume();
		volume.header = headerObject;
		volume.segmentation = this.segmentation;
		//
		// parse the (unzipped) data to a datastream of the correct type
		//
		volume.data = new headerObject.__array( _data );
		// get the min and max intensities
		const min_max = volume.computeMinMax();
		const min = min_max[ 0 ];
		const max = min_max[ 1 ];
		// attach the scalar range to the volume
		volume.windowLow = min;
		volume.windowHigh = max;

		// get the image dimensions
		volume.dimensions = [ headerObject.sizes[ 0 ], headerObject.sizes[ 1 ], headerObject.sizes[ 2 ] ];
		volume.xLength = volume.dimensions[ 0 ];
		volume.yLength = volume.dimensions[ 1 ];
		volume.zLength = volume.dimensions[ 2 ];

		// Identify axis order in the space-directions matrix from the header if possible.
		if ( headerObject.vectors ) {

			const xIndex = headerObject.vectors.findIndex( vector => vector[ 0 ] !== 0 );
			const yIndex = headerObject.vectors.findIndex( vector => vector[ 1 ] !== 0 );
			const zIndex = headerObject.vectors.findIndex( vector => vector[ 2 ] !== 0 );

			const axisOrder = [];

			if ( xIndex !== yIndex && xIndex !== zIndex && yIndex !== zIndex ) {

				axisOrder[ xIndex ] = 'x';
				axisOrder[ yIndex ] = 'y';
				axisOrder[ zIndex ] = 'z';

			} else {

				axisOrder[ 0 ] = 'x';
				axisOrder[ 1 ] = 'y';
				axisOrder[ 2 ] = 'z';

			}

			volume.axisOrder = axisOrder;

		} else {

			volume.axisOrder = [ 'x', 'y', 'z' ];

		}

		// spacing
		const spacingX = new Vector3().fromArray( headerObject.vectors[ 0 ] ).length();
		const spacingY = new Vector3().fromArray( headerObject.vectors[ 1 ] ).length();
		const spacingZ = new Vector3().fromArray( headerObject.vectors[ 2 ] ).length();
		volume.spacing = [ spacingX, spacingY, spacingZ ];


		// Create IJKtoRAS matrix
		volume.matrix = new Matrix4();

		const transitionMatrix = new Matrix4();

		if ( headerObject.space === 'left-posterior-superior' ) {

			transitionMatrix.set(
				- 1, 0, 0, 0,
				0, - 1, 0, 0,
				0, 0, 1, 0,
				0, 0, 0, 1
			);

		} else if ( headerObject.space === 'left-anterior-superior' ) {

			transitionMatrix.set(
				1, 0, 0, 0,
				0, 1, 0, 0,
				0, 0, - 1, 0,
				0, 0, 0, 1
			);

		}


		if ( ! headerObject.vectors ) {

			volume.matrix.set(
				1, 0, 0, 0,
				0, 1, 0, 0,
				0, 0, 1, 0,
				0, 0, 0, 1 );

		} else {

			const v = headerObject.vectors;

			const ijk_to_transition = new Matrix4().set(
				v[ 0 ][ 0 ], v[ 1 ][ 0 ], v[ 2 ][ 0 ], 0,
				v[ 0 ][ 1 ], v[ 1 ][ 1 ], v[ 2 ][ 1 ], 0,
				v[ 0 ][ 2 ], v[ 1 ][ 2 ], v[ 2 ][ 2 ], 0,
				0, 0, 0, 1
			);

			const transition_to_ras = new Matrix4().multiplyMatrices( ijk_to_transition, transitionMatrix );

			volume.matrix = transition_to_ras;

		}

		volume.inverseMatrix = new Matrix4();
		volume.inverseMatrix.copy( volume.matrix ).invert();

		volume.RASDimensions = [
			Math.floor( volume.xLength * spacingX ),
			Math.floor( volume.yLength * spacingY ),
			Math.floor( volume.zLength * spacingZ )
		];

		// .. and set the default threshold
		// only if the threshold was not already set
		if ( volume.lowerThreshold === - Infinity ) {

			volume.lowerThreshold = min;

		}

		if ( volume.upperThreshold === Infinity ) {

			volume.upperThreshold = max;

		}

		return volume;

	}
```
</details>

##### `_parseChars(array: any, start: any, end: any): string`

<details><summary>Code</summary>

```ts
_parseChars( array, start, end ) {

		// without borders, use the whole array
		if ( start === undefined ) {

			start = 0;

		}

		if ( end === undefined ) {

			end = array.length;

		}

		let output = '';
		// create and append the chars
		let i = 0;
		for ( i = start; i < end; ++ i ) {

			output += String.fromCharCode( array[ i ] );

		}

		return output;

	}
```
</details>


---