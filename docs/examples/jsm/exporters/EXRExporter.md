[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `EXRExporter.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 22 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 65 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/exporters/EXRExporter.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `FloatType` | `three` |
| `HalfFloatType` | `three` |
| `RGBAFormat` | `three` |
| `DataUtils` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `textEncoder` | `TextEncoder` | let/var | `new TextEncoder()` | ✗ |
| `NO_COMPRESSION` | `0` | let/var | `0` | ✗ |
| `ZIPS_COMPRESSION` | `2` | let/var | `2` | ✗ |
| `ZIP_COMPRESSION` | `3` | let/var | `3` | ✗ |
| `renderer` | `any` | let/var | `arg1` | ✗ |
| `renderTarget` | `any` | let/var | `arg2` | ✗ |
| `options` | `any` | let/var | `arg3` | ✗ |
| `dataBuffer` | `any` | let/var | `await getPixelData( renderer, renderTarget, info )` | ✗ |
| `texture` | `any` | let/var | `arg1` | ✗ |
| `options` | `any` | let/var | `arg2` | ✗ |
| `dataBuffer` | `any` | let/var | `texture.image.data` | ✗ |
| `compressionSizes` | `{ 0: number; 2: number; 3: number; }` | let/var | `{ 0: 1, 2: 1, 3: 16 }` | ✗ |
| `WIDTH` | `any` | let/var | `renderTarget.width` | ✗ |
| `HEIGHT` | `any` | let/var | `renderTarget.height` | ✗ |
| `TYPE` | `any` | let/var | `renderTarget.texture.type` | ✗ |
| `FORMAT` | `any` | let/var | `renderTarget.texture.format` | ✗ |
| `COMPRESSION` | `any` | let/var | `( options.compression !== undefined ) ? options.compression : ZIP_COMPRESSION` | ✗ |
| `EXPORTER_TYPE` | `any` | let/var | `( options.type !== undefined ) ? options.type : HalfFloatType` | ✗ |
| `OUT_TYPE` | `1 \| 2` | let/var | `( EXPORTER_TYPE === FloatType ) ? 2 : 1` | ✗ |
| `COMPRESSION_SIZE` | `any` | let/var | `compressionSizes[ COMPRESSION ]` | ✗ |
| `NUM_CHANNELS` | `4` | let/var | `4` | ✗ |
| `compressionSizes` | `{ 0: number; 2: number; 3: number; }` | let/var | `{ 0: 1, 2: 1, 3: 16 }` | ✗ |
| `WIDTH` | `any` | let/var | `texture.image.width` | ✗ |
| `HEIGHT` | `any` | let/var | `texture.image.height` | ✗ |
| `TYPE` | `any` | let/var | `texture.type` | ✗ |
| `FORMAT` | `any` | let/var | `texture.format` | ✗ |
| `COMPRESSION` | `any` | let/var | `( options.compression !== undefined ) ? options.compression : ZIP_COMPRESSION` | ✗ |
| `EXPORTER_TYPE` | `any` | let/var | `( options.type !== undefined ) ? options.type : HalfFloatType` | ✗ |
| `OUT_TYPE` | `1 \| 2` | let/var | `( EXPORTER_TYPE === FloatType ) ? 2 : 1` | ✗ |
| `COMPRESSION_SIZE` | `any` | let/var | `compressionSizes[ COMPRESSION ]` | ✗ |
| `NUM_CHANNELS` | `4` | let/var | `4` | ✗ |
| `dataBuffer` | `any` | let/var | `*not shown*` | ✗ |
| `w` | `any` | let/var | `info.width` | ✗ |
| `h` | `any` | let/var | `info.height` | ✗ |
| `dec` | `{ r: number; g: number; b: number; a:...` | let/var | `{ r: 0, g: 0, b: 0, a: 0 }` | ✗ |
| `offset` | `{ value: number; }` | let/var | `{ value: 0 }` | ✗ |
| `cOffset` | `1 \| 0` | let/var | `( info.numOutputChannels == 4 ) ? 1 : 0` | ✗ |
| `getValue` | `(arr: any, i: any) => any` | let/var | `( info.type == FloatType ) ? getFloat32 : getFloat16` | ✗ |
| `setValue` | `(dv: any, value: any, offset: any) =>...` | let/var | `( info.dataType == 1 ) ? setFloat16 : setFloat32` | ✗ |
| `outBuffer` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( info.width * info.height * info.numOutputChannels * info.data...` | ✗ |
| `dv` | `DataView<ArrayBuffer>` | let/var | `new DataView( outBuffer.buffer )` | ✗ |
| `i` | `number` | let/var | `y * w * 4 + x * 4` | ✗ |
| `line` | `number` | let/var | `( h - y - 1 ) * w * ( 3 + cOffset ) * info.dataSize` | ✗ |
| `compress` | `any` | let/var | `*not shown*` | ✗ |
| `tmpBuffer` | `any` | let/var | `*not shown*` | ✗ |
| `sum` | `number` | let/var | `0` | ✗ |
| `chunks` | `{ data: any[]; totalSize: number; }` | let/var | `{ data: new Array(), totalSize: 0 }` | ✗ |
| `size` | `number` | let/var | `info.width * info.numOutputChannels * info.blockLines * info.dataSize` | ✗ |
| `t1` | `number` | let/var | `0` | ✗ |
| `s` | `number` | let/var | `0` | ✗ |
| `stop` | `number` | let/var | `data.length - 1` | ✗ |
| `p` | `any` | let/var | `tmpBuffer[ 0 ]` | ✗ |
| `d` | `number` | let/var | `tmpBuffer[ t ] - p + ( 128 + 256 )` | ✗ |
| `offset` | `{ value: number; }` | let/var | `{ value: 0 }` | ✗ |
| `dv` | `DataView<any>` | let/var | `new DataView( outBuffer.buffer )` | ✗ |
| `sum` | `number` | let/var | `offset.value + info.numBlocks * 8` | ✗ |
| `TableSize` | `number` | let/var | `info.numBlocks * 8` | ✗ |
| `HeaderSize` | `number` | let/var | `259 + ( 18 * info.numOutputChannels )` | ✗ |
| `offset` | `{ value: number; }` | let/var | `{ value: HeaderSize + TableSize }` | ✗ |
| `outBuffer` | `Uint8Array<any>` | let/var | `new Uint8Array( HeaderSize + TableSize + chunks.totalSize + info.numBlocks * 8 )` | ✗ |
| `dv` | `DataView<any>` | let/var | `new DataView( outBuffer.buffer )` | ✗ |
| `data` | `any` | let/var | `chunks.data[ i ].dataChunk` | ✗ |
| `size` | `any` | let/var | `chunks.data[ i ].size` | ✗ |
| `exponent` | `number` | let/var | `( binary & 0x7C00 ) >> 10` | ✗ |
| `fraction` | `number` | let/var | `binary & 0x03FF` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `getPixelData` | renderer.readRenderTargetPixelsAsync( rtt, 0, 0, info.width, info.height, dataBuffer ), renderer.readRenderTargetPixelsAsync( rtt, 0, 0, info.width, info.height ) | *none* |


---

## Functions

### `EXRExporter.parse(arg1: any, arg2: any, arg3: any): Promise<Uint8Array<ArrayBufferLike>>`

**JSDoc:**
```typescript
/**
	 * This method has two variants.
	 *
	 * - When exporting a data texture, it receives two parameters. The texture and the exporter options.
	 * - When exporting a render target (e.g. a PMREM), it receives three parameters. The renderer, the
	 * render target and the exporter options.
	 *
	 * @async
	 * @param {(DataTexture|WebGPURenderer|WebGLRenderer)} arg1 - The data texture to export or a renderer.
	 * @param {(EXRExporter~Options|RenderTarget)} arg2 - The exporter options or a render target.
	 * @param {EXRExporter~Options} [arg3] - The exporter options.
	 * @return {Promise<Uint8Array>} A Promise that resolves with the exported EXR.
	 */
```

**Parameters:**

- **`arg1`** `any`
- **`arg2`** `any`
- **`arg3`** `any`

**Returns:** `Promise<Uint8Array<ArrayBufferLike>>`

**Calls:**

- `Error`
- `supportedRTT`
- `buildInfoRTT`
- `getPixelData`
- `reorganizeDataBuffer`
- `compressData`
- `fillData`
- `supportedDT`
- `buildInfoDT`

<details><summary>Code</summary>

```typescript
async parse( arg1, arg2, arg3 ) {

		if ( ! arg1 || ! ( arg1.isWebGLRenderer || arg1.isWebGPURenderer || arg1.isDataTexture ) ) {

			throw Error( 'EXRExporter.parse: Unsupported first parameter, expected instance of WebGLRenderer, WebGPURenderer or DataTexture.' );

		} else if ( arg1.isWebGLRenderer || arg1.isWebGPURenderer ) {

			const renderer = arg1, renderTarget = arg2, options = arg3;

			supportedRTT( renderTarget );

			const info = buildInfoRTT( renderTarget, options ),
				dataBuffer = await getPixelData( renderer, renderTarget, info ),
				rawContentBuffer = reorganizeDataBuffer( dataBuffer, info ),
				chunks = compressData( rawContentBuffer, info );

			return fillData( chunks, info );

		} else if ( arg1.isDataTexture ) {

			const texture = arg1, options = arg2;

			supportedDT( texture );

			const info = buildInfoDT( texture, options ),
				dataBuffer = texture.image.data,
				rawContentBuffer = reorganizeDataBuffer( dataBuffer, info ),
				chunks = compressData( rawContentBuffer, info );

			return fillData( chunks, info );

		}

	}
```
</details>

### `supportedRTT(renderTarget: any): void`

**Parameters:**

- **`renderTarget`** `any`

**Returns:** `void`

**Calls:**

- `Error`

<details><summary>Code</summary>

```typescript
function supportedRTT( renderTarget ) {

	if ( ! renderTarget || ! renderTarget.isRenderTarget ) {

		throw Error( 'EXRExporter.parse: Unsupported second parameter, expected instance of WebGLRenderTarget.' );

	}

	if ( renderTarget.isWebGLCubeRenderTarget || renderTarget.isWebGL3DRenderTarget || renderTarget.isWebGLArrayRenderTarget ) {

		throw Error( 'EXRExporter.parse: Unsupported render target type, expected instance of WebGLRenderTarget.' );

	}

	if ( renderTarget.texture.type !== FloatType && renderTarget.texture.type !== HalfFloatType ) {

		throw Error( 'EXRExporter.parse: Unsupported WebGLRenderTarget texture type.' );

	}

	if ( renderTarget.texture.format !== RGBAFormat ) {

		throw Error( 'EXRExporter.parse: Unsupported WebGLRenderTarget texture format, expected RGBAFormat.' );

	}

}
```
</details>

### `supportedDT(texture: any): void`

**Parameters:**

- **`texture`** `any`

**Returns:** `void`

**Calls:**

- `Error`

<details><summary>Code</summary>

```typescript
function supportedDT( texture ) {

	if ( texture.type !== FloatType && texture.type !== HalfFloatType ) {

		throw Error( 'EXRExporter.parse: Unsupported DataTexture texture type.' );

	}

	if ( texture.format !== RGBAFormat ) {

		throw Error( 'EXRExporter.parse: Unsupported DataTexture texture format, expected RGBAFormat.' );

	}

	if ( ! texture.image.data ) {

		throw Error( 'EXRExporter.parse: Invalid DataTexture image data.' );

	}

	if ( texture.type === FloatType && texture.image.data.constructor.name !== 'Float32Array' ) {

		throw Error( 'EXRExporter.parse: DataTexture image data doesn\'t match type, expected \'Float32Array\'.' );

	}

	if ( texture.type === HalfFloatType && texture.image.data.constructor.name !== 'Uint16Array' ) {

		throw Error( 'EXRExporter.parse: DataTexture image data doesn\'t match type, expected \'Uint16Array\'.' );

	}

}
```
</details>

### `buildInfoRTT(renderTarget: any, options: {}): { width: any; height: any; type: any; format: any; compression: any; blockLines: any; dataType: number; dataSize: number; numBlocks: number; numInputChannels: number; numOutputChannels: number; }`

**Parameters:**

- **`renderTarget`** `any`
- **`options`** `{}`

**Returns:** `{ width: any; height: any; type: any; format: any; compression: any; blockLines: any; dataType: number; dataSize: number; numBlocks: number; numInputChannels: number; numOutputChannels: number; }`

**Calls:**

- `Math.ceil`

<details><summary>Code</summary>

```typescript
function buildInfoRTT( renderTarget, options = {} ) {

	const compressionSizes = {
		0: 1,
		2: 1,
		3: 16
	};

	const WIDTH = renderTarget.width,
		HEIGHT = renderTarget.height,
		TYPE = renderTarget.texture.type,
		FORMAT = renderTarget.texture.format,
		COMPRESSION = ( options.compression !== undefined ) ? options.compression : ZIP_COMPRESSION,
		EXPORTER_TYPE = ( options.type !== undefined ) ? options.type : HalfFloatType,
		OUT_TYPE = ( EXPORTER_TYPE === FloatType ) ? 2 : 1,
		COMPRESSION_SIZE = compressionSizes[ COMPRESSION ],
		NUM_CHANNELS = 4;

	return {
		width: WIDTH,
		height: HEIGHT,
		type: TYPE,
		format: FORMAT,
		compression: COMPRESSION,
		blockLines: COMPRESSION_SIZE,
		dataType: OUT_TYPE,
		dataSize: 2 * OUT_TYPE,
		numBlocks: Math.ceil( HEIGHT / COMPRESSION_SIZE ),
		numInputChannels: 4,
		numOutputChannels: NUM_CHANNELS,
	};

}
```
</details>

### `buildInfoDT(texture: any, options: {}): { width: any; height: any; type: any; format: any; compression: any; blockLines: any; dataType: number; dataSize: number; numBlocks: number; numInputChannels: number; numOutputChannels: number; }`

**Parameters:**

- **`texture`** `any`
- **`options`** `{}`

**Returns:** `{ width: any; height: any; type: any; format: any; compression: any; blockLines: any; dataType: number; dataSize: number; numBlocks: number; numInputChannels: number; numOutputChannels: number; }`

**Calls:**

- `Math.ceil`

<details><summary>Code</summary>

```typescript
function buildInfoDT( texture, options = {} ) {

	const compressionSizes = {
		0: 1,
		2: 1,
		3: 16
	};

	const WIDTH = texture.image.width,
		HEIGHT = texture.image.height,
		TYPE = texture.type,
		FORMAT = texture.format,
		COMPRESSION = ( options.compression !== undefined ) ? options.compression : ZIP_COMPRESSION,
		EXPORTER_TYPE = ( options.type !== undefined ) ? options.type : HalfFloatType,
		OUT_TYPE = ( EXPORTER_TYPE === FloatType ) ? 2 : 1,
		COMPRESSION_SIZE = compressionSizes[ COMPRESSION ],
		NUM_CHANNELS = 4;

	return {
		width: WIDTH,
		height: HEIGHT,
		type: TYPE,
		format: FORMAT,
		compression: COMPRESSION,
		blockLines: COMPRESSION_SIZE,
		dataType: OUT_TYPE,
		dataSize: 2 * OUT_TYPE,
		numBlocks: Math.ceil( HEIGHT / COMPRESSION_SIZE ),
		numInputChannels: 4,
		numOutputChannels: NUM_CHANNELS,
	};

}
```
</details>

### `getPixelData(renderer: any, rtt: any, info: any): Promise<any>`

**Parameters:**

- **`renderer`** `any`
- **`rtt`** `any`
- **`info`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `renderer.readRenderTargetPixelsAsync`

<details><summary>Code</summary>

```typescript
async function getPixelData( renderer, rtt, info ) {

	let dataBuffer;

	if ( renderer.isWebGLRenderer ) {

		if ( info.type === FloatType ) {

			dataBuffer = new Float32Array( info.width * info.height * info.numInputChannels );

		} else {

			dataBuffer = new Uint16Array( info.width * info.height * info.numInputChannels );

		}

		await renderer.readRenderTargetPixelsAsync( rtt, 0, 0, info.width, info.height, dataBuffer );

	} else {

		dataBuffer = await renderer.readRenderTargetPixelsAsync( rtt, 0, 0, info.width, info.height );

	}

	return dataBuffer;

}
```
</details>

### `reorganizeDataBuffer(inBuffer: any, info: any): Uint8Array<ArrayBuffer>`

**Parameters:**

- **`inBuffer`** `any`
- **`info`** `any`

**Returns:** `Uint8Array<ArrayBuffer>`

**Calls:**

- `getValue`
- `decodeLinear`
- `setValue`

<details><summary>Code</summary>

```typescript
function reorganizeDataBuffer( inBuffer, info ) {

	const w = info.width,
		h = info.height,
		dec = { r: 0, g: 0, b: 0, a: 0 },
		offset = { value: 0 },
		cOffset = ( info.numOutputChannels == 4 ) ? 1 : 0,
		getValue = ( info.type == FloatType ) ? getFloat32 : getFloat16,
		setValue = ( info.dataType == 1 ) ? setFloat16 : setFloat32,
		outBuffer = new Uint8Array( info.width * info.height * info.numOutputChannels * info.dataSize ),
		dv = new DataView( outBuffer.buffer );

	for ( let y = 0; y < h; ++ y ) {

		for ( let x = 0; x < w; ++ x ) {

			const i = y * w * 4 + x * 4;

			const r = getValue( inBuffer, i );
			const g = getValue( inBuffer, i + 1 );
			const b = getValue( inBuffer, i + 2 );
			const a = getValue( inBuffer, i + 3 );

			const line = ( h - y - 1 ) * w * ( 3 + cOffset ) * info.dataSize;

			decodeLinear( dec, r, g, b, a );

			offset.value = line + x * info.dataSize;
			setValue( dv, dec.a, offset );

			offset.value = line + ( cOffset ) * w * info.dataSize + x * info.dataSize;
			setValue( dv, dec.b, offset );

			offset.value = line + ( 1 + cOffset ) * w * info.dataSize + x * info.dataSize;
			setValue( dv, dec.g, offset );

			offset.value = line + ( 2 + cOffset ) * w * info.dataSize + x * info.dataSize;
			setValue( dv, dec.r, offset );

		}

	}

	return outBuffer;

}
```
</details>

### `compressData(inBuffer: any, info: any): { data: any[]; totalSize: number; }`

**Parameters:**

- **`inBuffer`** `any`
- **`info`** `any`

**Returns:** `{ data: any[]; totalSize: number; }`

**Calls:**

- `inBuffer.subarray`
- `compress`
- `chunks.data.push`

<details><summary>Code</summary>

```typescript
function compressData( inBuffer, info ) {

	let compress,
		tmpBuffer,
		sum = 0;

	const chunks = { data: new Array(), totalSize: 0 },
		size = info.width * info.numOutputChannels * info.blockLines * info.dataSize;

	switch ( info.compression ) {

		case 0:
			compress = compressNONE;
			break;

		case 2:
		case 3:
			compress = compressZIP;
			break;

	}

	if ( info.compression !== 0 ) {

		tmpBuffer = new Uint8Array( size );

	}

	for ( let i = 0; i < info.numBlocks; ++ i ) {

		const arr = inBuffer.subarray( size * i, size * ( i + 1 ) );

		const block = compress( arr, tmpBuffer );

		sum += block.length;

		chunks.data.push( { dataChunk: block, size: block.length } );

	}

	chunks.totalSize = sum;

	return chunks;

}
```
</details>

### `compressNONE(data: any): any`

**Parameters:**

- **`data`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function compressNONE( data ) {

	return data;

}
```
</details>

### `compressZIP(data: any, tmpBuffer: any): Uint8Array<any>`

**Parameters:**

- **`data`** `any`
- **`tmpBuffer`** `any`

**Returns:** `Uint8Array<any>`

**Calls:**

- `Math.floor`
- `fflate.zlibSync`

**Internal Comments:**
```
// (x8)
// Reorder the pixel data. (x2)
// Predictor. (x2)
```

<details><summary>Code</summary>

```typescript
function compressZIP( data, tmpBuffer ) {

	//
	// Reorder the pixel data.
	//

	let t1 = 0,
		t2 = Math.floor( ( data.length + 1 ) / 2 ),
		s = 0;

	const stop = data.length - 1;

	while ( true ) {

		if ( s > stop ) break;
		tmpBuffer[ t1 ++ ] = data[ s ++ ];

		if ( s > stop ) break;
		tmpBuffer[ t2 ++ ] = data[ s ++ ];

	}

	//
	// Predictor.
	//

	let p = tmpBuffer[ 0 ];

	for ( let t = 1; t < tmpBuffer.length; t ++ ) {

		const d = tmpBuffer[ t ] - p + ( 128 + 256 );
		p = tmpBuffer[ t ];
		tmpBuffer[ t ] = d;

	}

	const deflate = fflate.zlibSync( tmpBuffer );

	return deflate;

}
```
</details>

### `fillHeader(outBuffer: any, chunks: any, info: any): void`

**Parameters:**

- **`outBuffer`** `any`
- **`chunks`** `any`
- **`info`** `any`

**Returns:** `void`

**Calls:**

- `setUint32`
- `setString`
- `setUint8`
- `setFloat32`
- `setUint64`

**Internal Comments:**
```
// = HEADER = (x3)
// null-byte (x3)
// = OFFSET TABLE = (x2)
```

<details><summary>Code</summary>

```typescript
function fillHeader( outBuffer, chunks, info ) {

	const offset = { value: 0 };
	const dv = new DataView( outBuffer.buffer );

	setUint32( dv, 20000630, offset ); // magic
	setUint32( dv, 2, offset ); // mask

	// = HEADER =

	setString( dv, 'compression', offset );
	setString( dv, 'compression', offset );
	setUint32( dv, 1, offset );
	setUint8( dv, info.compression, offset );

	setString( dv, 'screenWindowCenter', offset );
	setString( dv, 'v2f', offset );
	setUint32( dv, 8, offset );
	setUint32( dv, 0, offset );
	setUint32( dv, 0, offset );

	setString( dv, 'screenWindowWidth', offset );
	setString( dv, 'float', offset );
	setUint32( dv, 4, offset );
	setFloat32( dv, 1.0, offset );

	setString( dv, 'pixelAspectRatio', offset );
	setString( dv, 'float', offset );
	setUint32( dv, 4, offset );
	setFloat32( dv, 1.0, offset );

	setString( dv, 'lineOrder', offset );
	setString( dv, 'lineOrder', offset );
	setUint32( dv, 1, offset );
	setUint8( dv, 0, offset );

	setString( dv, 'dataWindow', offset );
	setString( dv, 'box2i', offset );
	setUint32( dv, 16, offset );
	setUint32( dv, 0, offset );
	setUint32( dv, 0, offset );
	setUint32( dv, info.width - 1, offset );
	setUint32( dv, info.height - 1, offset );

	setString( dv, 'displayWindow', offset );
	setString( dv, 'box2i', offset );
	setUint32( dv, 16, offset );
	setUint32( dv, 0, offset );
	setUint32( dv, 0, offset );
	setUint32( dv, info.width - 1, offset );
	setUint32( dv, info.height - 1, offset );

	setString( dv, 'channels', offset );
	setString( dv, 'chlist', offset );
	setUint32( dv, info.numOutputChannels * 18 + 1, offset );

	setString( dv, 'A', offset );
	setUint32( dv, info.dataType, offset );
	offset.value += 4;
	setUint32( dv, 1, offset );
	setUint32( dv, 1, offset );

	setString( dv, 'B', offset );
	setUint32( dv, info.dataType, offset );
	offset.value += 4;
	setUint32( dv, 1, offset );
	setUint32( dv, 1, offset );

	setString( dv, 'G', offset );
	setUint32( dv, info.dataType, offset );
	offset.value += 4;
	setUint32( dv, 1, offset );
	setUint32( dv, 1, offset );

	setString( dv, 'R', offset );
	setUint32( dv, info.dataType, offset );
	offset.value += 4;
	setUint32( dv, 1, offset );
	setUint32( dv, 1, offset );

	setUint8( dv, 0, offset );

	// null-byte
	setUint8( dv, 0, offset );

	// = OFFSET TABLE =

	let sum = offset.value + info.numBlocks * 8;

	for ( let i = 0; i < chunks.data.length; ++ i ) {

		setUint64( dv, sum, offset );

		sum += chunks.data[ i ].size + 8;

	}

}
```
</details>

### `fillData(chunks: any, info: any): Uint8Array<any>`

**Parameters:**

- **`chunks`** `any`
- **`info`** `any`

**Returns:** `Uint8Array<any>`

**Calls:**

- `fillHeader`
- `setUint32`
- `outBuffer.set`

<details><summary>Code</summary>

```typescript
function fillData( chunks, info ) {

	const TableSize = info.numBlocks * 8,
		HeaderSize = 259 + ( 18 * info.numOutputChannels ), // 259 + 18 * chlist
		offset = { value: HeaderSize + TableSize },
		outBuffer = new Uint8Array( HeaderSize + TableSize + chunks.totalSize + info.numBlocks * 8 ),
		dv = new DataView( outBuffer.buffer );

	fillHeader( outBuffer, chunks, info );

	for ( let i = 0; i < chunks.data.length; ++ i ) {

		const data = chunks.data[ i ].dataChunk;
		const size = chunks.data[ i ].size;

		setUint32( dv, i * info.blockLines, offset );
		setUint32( dv, size, offset );

		outBuffer.set( data, offset.value );
		offset.value += size;

	}

	return outBuffer;

}
```
</details>

### `decodeLinear(dec: any, r: any, g: any, b: any, a: any): void`

**Parameters:**

- **`dec`** `any`
- **`r`** `any`
- **`g`** `any`
- **`b`** `any`
- **`a`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function decodeLinear( dec, r, g, b, a ) {

	dec.r = r;
	dec.g = g;
	dec.b = b;
	dec.a = a;

}
```
</details>

### `setUint8(dv: any, value: any, offset: any): void`

**Parameters:**

- **`dv`** `any`
- **`value`** `any`
- **`offset`** `any`

**Returns:** `void`

**Calls:**

- `dv.setUint8`

<details><summary>Code</summary>

```typescript
function setUint8( dv, value, offset ) {

	dv.setUint8( offset.value, value );

	offset.value += 1;

}
```
</details>

### `setUint32(dv: any, value: any, offset: any): void`

**Parameters:**

- **`dv`** `any`
- **`value`** `any`
- **`offset`** `any`

**Returns:** `void`

**Calls:**

- `dv.setUint32`

<details><summary>Code</summary>

```typescript
function setUint32( dv, value, offset ) {

	dv.setUint32( offset.value, value, true );

	offset.value += 4;

}
```
</details>

### `setFloat16(dv: any, value: any, offset: any): void`

**Parameters:**

- **`dv`** `any`
- **`value`** `any`
- **`offset`** `any`

**Returns:** `void`

**Calls:**

- `dv.setUint16`
- `DataUtils.toHalfFloat`

<details><summary>Code</summary>

```typescript
function setFloat16( dv, value, offset ) {

	dv.setUint16( offset.value, DataUtils.toHalfFloat( value ), true );

	offset.value += 2;

}
```
</details>

### `setFloat32(dv: any, value: any, offset: any): void`

**Parameters:**

- **`dv`** `any`
- **`value`** `any`
- **`offset`** `any`

**Returns:** `void`

**Calls:**

- `dv.setFloat32`

<details><summary>Code</summary>

```typescript
function setFloat32( dv, value, offset ) {

	dv.setFloat32( offset.value, value, true );

	offset.value += 4;

}
```
</details>

### `setUint64(dv: any, value: any, offset: any): void`

**Parameters:**

- **`dv`** `any`
- **`value`** `any`
- **`offset`** `any`

**Returns:** `void`

**Calls:**

- `dv.setBigUint64`
- `BigInt`

<details><summary>Code</summary>

```typescript
function setUint64( dv, value, offset ) {

	dv.setBigUint64( offset.value, BigInt( value ), true );

	offset.value += 8;

}
```
</details>

### `setString(dv: any, string: any, offset: any): void`

**Parameters:**

- **`dv`** `any`
- **`string`** `any`
- **`offset`** `any`

**Returns:** `void`

**Calls:**

- `textEncoder.encode`
- `setUint8`

<details><summary>Code</summary>

```typescript
function setString( dv, string, offset ) {

	const tmp = textEncoder.encode( string + '\0' );

	for ( let i = 0; i < tmp.length; ++ i ) {

		setUint8( dv, tmp[ i ], offset );

	}

}
```
</details>

### `decodeFloat16(binary: any): number`

**Parameters:**

- **`binary`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
function decodeFloat16( binary ) {

	const exponent = ( binary & 0x7C00 ) >> 10,
		fraction = binary & 0x03FF;

	return ( binary >> 15 ? - 1 : 1 ) * (
		exponent ?
			(
				exponent === 0x1F ?
					fraction ? NaN : Infinity :
					Math.pow( 2, exponent - 15 ) * ( 1 + fraction / 0x400 )
			) :
			6.103515625e-5 * ( fraction / 0x400 )
	);

}
```
</details>

### `getFloat16(arr: any, i: any): number`

**Parameters:**

- **`arr`** `any`
- **`i`** `any`

**Returns:** `number`

**Calls:**

- `decodeFloat16`

<details><summary>Code</summary>

```typescript
function getFloat16( arr, i ) {

	return decodeFloat16( arr[ i ] );

}
```
</details>

### `getFloat32(arr: any, i: any): any`

**Parameters:**

- **`arr`** `any`
- **`i`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getFloat32( arr, i ) {

	return arr[ i ];

}
```
</details>


---

## Classes

### `EXRExporter`

<details><summary>Class Code</summary>

```ts
class EXRExporter {

	/**
	 * This method has two variants.
	 *
	 * - When exporting a data texture, it receives two parameters. The texture and the exporter options.
	 * - When exporting a render target (e.g. a PMREM), it receives three parameters. The renderer, the
	 * render target and the exporter options.
	 *
	 * @async
	 * @param {(DataTexture|WebGPURenderer|WebGLRenderer)} arg1 - The data texture to export or a renderer.
	 * @param {(EXRExporter~Options|RenderTarget)} arg2 - The exporter options or a render target.
	 * @param {EXRExporter~Options} [arg3] - The exporter options.
	 * @return {Promise<Uint8Array>} A Promise that resolves with the exported EXR.
	 */
	async parse( arg1, arg2, arg3 ) {

		if ( ! arg1 || ! ( arg1.isWebGLRenderer || arg1.isWebGPURenderer || arg1.isDataTexture ) ) {

			throw Error( 'EXRExporter.parse: Unsupported first parameter, expected instance of WebGLRenderer, WebGPURenderer or DataTexture.' );

		} else if ( arg1.isWebGLRenderer || arg1.isWebGPURenderer ) {

			const renderer = arg1, renderTarget = arg2, options = arg3;

			supportedRTT( renderTarget );

			const info = buildInfoRTT( renderTarget, options ),
				dataBuffer = await getPixelData( renderer, renderTarget, info ),
				rawContentBuffer = reorganizeDataBuffer( dataBuffer, info ),
				chunks = compressData( rawContentBuffer, info );

			return fillData( chunks, info );

		} else if ( arg1.isDataTexture ) {

			const texture = arg1, options = arg2;

			supportedDT( texture );

			const info = buildInfoDT( texture, options ),
				dataBuffer = texture.image.data,
				rawContentBuffer = reorganizeDataBuffer( dataBuffer, info ),
				chunks = compressData( rawContentBuffer, info );

			return fillData( chunks, info );

		}

	}

}
```
</details>

#### Methods

##### `parse(arg1: any, arg2: any, arg3: any): Promise<Uint8Array<ArrayBufferLike>>`

<details><summary>Code</summary>

```ts
async parse( arg1, arg2, arg3 ) {

		if ( ! arg1 || ! ( arg1.isWebGLRenderer || arg1.isWebGPURenderer || arg1.isDataTexture ) ) {

			throw Error( 'EXRExporter.parse: Unsupported first parameter, expected instance of WebGLRenderer, WebGPURenderer or DataTexture.' );

		} else if ( arg1.isWebGLRenderer || arg1.isWebGPURenderer ) {

			const renderer = arg1, renderTarget = arg2, options = arg3;

			supportedRTT( renderTarget );

			const info = buildInfoRTT( renderTarget, options ),
				dataBuffer = await getPixelData( renderer, renderTarget, info ),
				rawContentBuffer = reorganizeDataBuffer( dataBuffer, info ),
				chunks = compressData( rawContentBuffer, info );

			return fillData( chunks, info );

		} else if ( arg1.isDataTexture ) {

			const texture = arg1, options = arg2;

			supportedDT( texture );

			const info = buildInfoDT( texture, options ),
				dataBuffer = texture.image.data,
				rawContentBuffer = reorganizeDataBuffer( dataBuffer, info ),
				chunks = compressData( rawContentBuffer, info );

			return fillData( chunks, info );

		}

	}
```
</details>


---