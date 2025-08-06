[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `UltraHDRLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 11 |
| 📊 Variables & Constants | 27 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/UltraHDRLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ClampToEdgeWrapping` | `three` |
| `DataTexture` | `three` |
| `DataUtils` | `three` |
| `FileLoader` | `three` |
| `HalfFloatType` | `three` |
| `LinearFilter` | `three` |
| `LinearMipMapLinearFilter` | `three` |
| `LinearSRGBColorSpace` | `three` |
| `Loader` | `three` |
| `RGBAFormat` | `three` |
| `UVMapping` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `xmpMetadata` | `{ version: any; baseRenditionIsHDR: a...` | let/var | `{ version: null, baseRenditionIsHDR: null, gainMapMin: null, gainMapMax: null...` | ✗ |
| `textDecoder` | `TextDecoder` | let/var | `new TextDecoder()` | ✗ |
| `data` | `DataView<ArrayBuffer>` | let/var | `new DataView( buffer )` | ✗ |
| `byteOffset` | `number` | let/var | `0` | ✗ |
| `sections` | `any[]` | let/var | `[]` | ✗ |
| `primaryImage` | `any` | let/var | `*not shown*` | ✗ |
| `gainmapImage` | `any` | let/var | `*not shown*` | ✗ |
| `sectionData` | `DataView<ArrayBuffer>` | let/var | `new DataView( new Uint8Array( section.slice( 2 ) ).buffer )` | ✗ |
| `mpfLittleEndian` | `boolean` | let/var | `sectionData.getUint32( 6 ) === 0x49492a00` | ✗ |
| `mpfBytesOffset` | `60` | let/var | `60` | ✗ |
| `gainmapImageOffset` | `number` | let/var | `sectionData.getUint32( mpfBytesOffset + 20, mpfLittleEndian ) + sectionOffset...` | ✗ |
| `texture` | `any` | let/var | `new DataTexture( this.type === HalfFloatType ? new Uint16Array() : new Float3...` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `domParser` | `DOMParser` | let/var | `new DOMParser()` | ✗ |
| `image` | `{ width: number; height: number; sour...` | let/var | `{ width: imageLoader.naturalWidth, height: imageLoader.naturalHeight, source:...` | ✗ |
| `sdrImageAspect` | `number` | let/var | `sdrImage.width / sdrImage.height` | ✗ |
| `gainmapImageAspect` | `number` | let/var | `gainmapImage.width / gainmapImage.height` | ✗ |
| `hdrBuffer` | `any` | let/var | `*not shown*` | ✗ |
| `unclampedWeightFactor` | `number` | let/var | `( Math.log2( maxDisplayBoost ) - xmpMetadata.hdrCapacityMin ) / ( xmpMetadata...` | ✗ |
| `useGammaOne` | `boolean` | let/var | `xmpMetadata.gamma === 1.0` | ✗ |
| `x` | `number` | let/var | `( pixelIndex / 4 ) % sdrImage.width` | ✗ |
| `sdrValue` | `number` | let/var | `sdrImageData.data[ pixelIndex + channelIndex ]` | ✗ |
| `gainmapIndex` | `number` | let/var | `( y * sdrImage.width + x ) * 4 + channelIndex` | ✗ |
| `gainmapValue` | `number` | let/var | `gainmapImageData.data[ gainmapIndex ] / 255.0` | ✗ |
| `logRecovery` | `number` | let/var | `useGammaOne ? gainmapValue : Math.pow( gainmapValue, 1.0 / xmpMetadata.gamma )` | ✗ |
| `logBoost` | `number` | let/var | `xmpMetadata.gainMapMin * ( 1.0 - logRecovery ) + xmpMetadata.gainMapMax * log...` | ✗ |
| `hdrValue` | `number` | let/var | `( sdrValue + xmpMetadata.offsetSDR ) * ( logBoost * weightFactor === 0.0 ? 1....` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| promise-chain | `getImageDataFromBuffer` | *none* | new Promise(...) |


---

## Functions

### `UltraHDRLoader.setDataType(value: any): RGBELoader`

**JSDoc:**
```typescript
/**
	 * Sets the texture type.
	 *
	 * @param {(HalfFloatType|FloatType)} value - The texture type to set.
	 * @return {RGBELoader} A reference to this loader.
	 */
```

**Parameters:**

- **`value`** `any`

**Returns:** `RGBELoader`

<details><summary>Code</summary>

```typescript
setDataType( value ) {

		this.type = value;

		return this;

	}
```
</details>

### `UltraHDRLoader.parse(buffer: ArrayBuffer, onLoad: Function): void`

**JSDoc:**
```typescript
/**
	 * Parses the given Ultra HDR texture data.
	 *
	 * @param {ArrayBuffer} buffer - The raw texture data.
	 * @param {Function} onLoad - The `onLoad` callback.
	 */
```

**Parameters:**

- **`buffer`** `ArrayBuffer`
- **`onLoad`** `Function`

**Returns:** `void`

**Calls:**

- `data.getUint8`
- `[
						/* Valid section headers */
						0xd8, // SOI
						0xe0, // APP0
						0xe1, // APP1
						0xe2, // APP2
					].includes`
- `sections.push`
- `sections[ sections.length - 1 ].section.push`
- `this._parseXMPMetadata`
- `textDecoder.decode`
- `section.slice`
- `sectionData.getUint32`
- `this._applyGainmapToSDR`
- `onLoad`

**Internal Comments:**
```
/* Valid section headers */
/* XMP Metadata */ (x4)
/* Data Sections - MPF / EXIF / ICC Profile */ (x2)
/* MPF Section */ (x2)
/* Section contains a list of static bytes and ends with offsets indicating location of SDR and gainmap images */ (x2)
/* First bytes after header indicate little / big endian ordering (0x49492A00 - LE / 0x4D4D002A - BE) */ (x2)
/*
					... 60 bytes indicating tags, versions, etc. ...

					bytes | bits | description

					4       32     primary image size
					4       32     primary image offset
					2       16     0x0000
					2       16     0x0000

					4       32     0x00000000
					4       32     gainmap image size
					4       32     gainmap image offset
					2       16     0x0000
					2       16     0x0000
					*/ (x2)
/* SDR size includes the metadata length, SDR offset is always 0 */ (x2)
/* Gainmap size is an absolute value starting from its offset, gainmap offset needs 6 bytes padding to take into account 0x00 bytes at the end of XMP */ (x2)
/* Minimal sufficient validation - https://developer.android.com/media/platform/hdr-image-format#signal_of_the_format */
```

<details><summary>Code</summary>

```typescript
parse( buffer, onLoad ) {

		const xmpMetadata = {
			version: null,
			baseRenditionIsHDR: null,
			gainMapMin: null,
			gainMapMax: null,
			gamma: null,
			offsetSDR: null,
			offsetHDR: null,
			hdrCapacityMin: null,
			hdrCapacityMax: null,
		};
		const textDecoder = new TextDecoder();

		const data = new DataView( buffer );

		let byteOffset = 0;
		const sections = [];

		while ( byteOffset < data.byteLength ) {

			const byte = data.getUint8( byteOffset );

			if ( byte === 0xff ) {

				const leadingByte = data.getUint8( byteOffset + 1 );

				if (
					[
						/* Valid section headers */
						0xd8, // SOI
						0xe0, // APP0
						0xe1, // APP1
						0xe2, // APP2
					].includes( leadingByte )
				) {

					sections.push( {
						sectionType: leadingByte,
						section: [ byte, leadingByte ],
						sectionOffset: byteOffset + 2,
					} );

					byteOffset += 2;

				} else {

					sections[ sections.length - 1 ].section.push( byte, leadingByte );

					byteOffset += 2;

				}

			} else {

				sections[ sections.length - 1 ].section.push( byte );

				byteOffset ++;

			}

		}

		let primaryImage, gainmapImage;

		for ( let i = 0; i < sections.length; i ++ ) {

			const { sectionType, section, sectionOffset } = sections[ i ];

			if ( sectionType === 0xe0 ) {
				/* JPEG Header - no useful information */
			} else if ( sectionType === 0xe1 ) {

				/* XMP Metadata */

				this._parseXMPMetadata(
					textDecoder.decode( new Uint8Array( section ) ),
					xmpMetadata
				);

			} else if ( sectionType === 0xe2 ) {

				/* Data Sections - MPF / EXIF / ICC Profile */

				const sectionData = new DataView(
					new Uint8Array( section.slice( 2 ) ).buffer
				);
				const sectionHeader = sectionData.getUint32( 2, false );

				if ( sectionHeader === 0x4d504600 ) {

					/* MPF Section */

					/* Section contains a list of static bytes and ends with offsets indicating location of SDR and gainmap images */
					/* First bytes after header indicate little / big endian ordering (0x49492A00 - LE / 0x4D4D002A - BE) */
					/*
					... 60 bytes indicating tags, versions, etc. ...

					bytes | bits | description

					4       32     primary image size
					4       32     primary image offset
					2       16     0x0000
					2       16     0x0000

					4       32     0x00000000
					4       32     gainmap image size
					4       32     gainmap image offset
					2       16     0x0000
					2       16     0x0000
					*/

					const mpfLittleEndian = sectionData.getUint32( 6 ) === 0x49492a00;
					const mpfBytesOffset = 60;

					/* SDR size includes the metadata length, SDR offset is always 0 */

					const primaryImageSize = sectionData.getUint32(
						mpfBytesOffset,
						mpfLittleEndian
					);
					const primaryImageOffset = sectionData.getUint32(
						mpfBytesOffset + 4,
						mpfLittleEndian
					);

					/* Gainmap size is an absolute value starting from its offset, gainmap offset needs 6 bytes padding to take into account 0x00 bytes at the end of XMP */
					const gainmapImageSize = sectionData.getUint32(
						mpfBytesOffset + 16,
						mpfLittleEndian
					);
					const gainmapImageOffset =
						sectionData.getUint32( mpfBytesOffset + 20, mpfLittleEndian ) +
						sectionOffset +
						6;

					primaryImage = new Uint8Array(
						data.buffer,
						primaryImageOffset,
						primaryImageSize
					);

					gainmapImage = new Uint8Array(
						data.buffer,
						gainmapImageOffset,
						gainmapImageSize
					);

				}

			}

		}

		/* Minimal sufficient validation - https://developer.android.com/media/platform/hdr-image-format#signal_of_the_format */
		if ( ! xmpMetadata.version ) {

			throw new Error( 'THREE.UltraHDRLoader: Not a valid UltraHDR image' );

		}

		if ( primaryImage && gainmapImage ) {

			this._applyGainmapToSDR(
				xmpMetadata,
				primaryImage,
				gainmapImage,
				( hdrBuffer, width, height ) => {

					onLoad( {
						width,
						height,
						data: hdrBuffer,
						format: RGBAFormat,
						type: this.type,
					} );

				},
				( error ) => {

					throw new Error( error );

				}
			);

		} else {

			throw new Error( 'THREE.UltraHDRLoader: Could not parse UltraHDR images' );

		}

	}
```
</details>

### `UltraHDRLoader.load(url: string, onLoad: (arg0: DataTexture, arg1: any) => any, onProgress: onProgressCallback, onError: onErrorCallback): DataTexture`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded Ultra HDR texture
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the files to be loaded. This can also be a data URI.
	 * @param {function(DataTexture, Object)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 * @return {DataTexture} The Ultra HDR texture.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: DataTexture, arg1: any) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `DataTexture`

**Calls:**

- `loader.setResponseType`
- `loader.setRequestHeader`
- `loader.setPath`
- `loader.setWithCredentials`
- `loader.load`
- `this.parse`
- `onLoad`
- `onError`
- `console.error`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const texture = new DataTexture(
			this.type === HalfFloatType ? new Uint16Array() : new Float32Array(),
			0,
			0,
			RGBAFormat,
			this.type,
			UVMapping,
			ClampToEdgeWrapping,
			ClampToEdgeWrapping,
			LinearFilter,
			LinearMipMapLinearFilter,
			1,
			LinearSRGBColorSpace
		);
		texture.generateMipmaps = true;
		texture.flipY = true;

		const loader = new FileLoader( this.manager );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( this.requestHeader );
		loader.setPath( this.path );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, ( buffer ) => {

			try {

				this.parse(
					buffer,
					( texData ) => {

						texture.image = {
							data: texData.data,
							width: texData.width,
							height: texData.height,
						};
						texture.needsUpdate = true;

						if ( onLoad ) onLoad( texture, texData );

					}
				);

			} catch ( error ) {

				if ( onError ) onError( error );

				console.error( error );

			}

		}, onProgress, onError );

		return texture;

	}
```
</details>

### `UltraHDRLoader._parseXMPMetadata(xmpDataString: any, xmpMetadata: any): void`

**Parameters:**

- **`xmpDataString`** `any`
- **`xmpMetadata`** `any`

**Returns:** `void`

**Calls:**

- `domParser.parseFromString`
- `xmpDataString.substring`
- `xmpDataString.indexOf`
- `xmpDataString.lastIndexOf`
- `xmpXml.getElementsByTagName`
- `gainmapNode.getAttribute`
- `parseFloat`

**Internal Comments:**
```
/* Determine if given XMP metadata is the primary GContainer descriptor or a gainmap descriptor */ (x2)
/* Gainmap descriptor - defaults from https://developer.android.com/media/platform/hdr-image-format#HDR_gain_map_metadata */ (x2)
```

<details><summary>Code</summary>

```typescript
_parseXMPMetadata( xmpDataString, xmpMetadata ) {

		const domParser = new DOMParser();

		const xmpXml = domParser.parseFromString(
			xmpDataString.substring(
				xmpDataString.indexOf( '<' ),
				xmpDataString.lastIndexOf( '>' ) + 1
			),
			'text/xml'
		);

		/* Determine if given XMP metadata is the primary GContainer descriptor or a gainmap descriptor */
		const [ hasHDRContainerDescriptor ] = xmpXml.getElementsByTagName(
			'Container:Directory'
		);

		if ( hasHDRContainerDescriptor ) {
			/* There's not much useful information in the container descriptor besides memory-validation */
		} else {

			/* Gainmap descriptor - defaults from https://developer.android.com/media/platform/hdr-image-format#HDR_gain_map_metadata */

			const [ gainmapNode ] = xmpXml.getElementsByTagName( 'rdf:Description' );

			xmpMetadata.version = gainmapNode.getAttribute( 'hdrgm:Version' );
			xmpMetadata.baseRenditionIsHDR =
				gainmapNode.getAttribute( 'hdrgm:BaseRenditionIsHDR' ) === 'True';
			xmpMetadata.gainMapMin = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:GainMapMin' ) || 0.0
			);
			xmpMetadata.gainMapMax = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:GainMapMax' ) || 1.0
			);
			xmpMetadata.gamma = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:Gamma' ) || 1.0
			);
			xmpMetadata.offsetSDR = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:OffsetSDR' ) / ( 1 / 64 )
			);
			xmpMetadata.offsetHDR = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:OffsetHDR' ) / ( 1 / 64 )
			);
			xmpMetadata.hdrCapacityMin = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:HDRCapacityMin' ) || 0.0
			);
			xmpMetadata.hdrCapacityMax = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:HDRCapacityMax' ) || 1.0
			);

		}

	}
```
</details>

### `UltraHDRLoader._srgbToLinear(value: any): number`

**Parameters:**

- **`value`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
_srgbToLinear( value ) {

		if ( value / 255 < 0.04045 ) {

			return ( value / 255 ) * 0.0773993808;

		}

		if ( value < 1024 ) {

			return SRGB_TO_LINEAR[ ~ ~ value ];

		}

		return Math.pow( ( value / 255 ) * 0.9478672986 + 0.0521327014, 2.4 );

	}
```
</details>

### `UltraHDRLoader._applyGainmapToSDR(xmpMetadata: any, sdrBuffer: any, gainmapBuffer: any, onSuccess: any, onError: any): void`

**Parameters:**

- **`xmpMetadata`** `any`
- **`sdrBuffer`** `any`
- **`gainmapBuffer`** `any`
- **`onSuccess`** `any`
- **`onError`** `any`

**Returns:** `void`

**Calls:**

- `document.createElement`
- `URL.revokeObjectURL`
- `resolve`
- `reject`
- `URL.createObjectURL`
- `Promise.all( [
			getImageDataFromBuffer( sdrBuffer ),
			getImageDataFromBuffer( gainmapBuffer ),
		] )
			.then( ( [ sdrImage, gainmapImage ] ) => {

				const sdrImageAspect = sdrImage.width / sdrImage.height;
				const gainmapImageAspect = gainmapImage.width / gainmapImage.height;

				if ( sdrImageAspect !== gainmapImageAspect ) {

					onError(
						'THREE.UltraHDRLoader Error: Aspect ratio mismatch between SDR and Gainmap images'
					);

					return;

				}

				const canvas = document.createElement( 'canvas' );
				const ctx = canvas.getContext( '2d', {
					willReadFrequently: true,
					colorSpace: 'srgb',
				} );

				canvas.width = sdrImage.width;
				canvas.height = sdrImage.height;

				/* Use out-of-the-box interpolation of Canvas API to scale gainmap to fit the SDR resolution */
				ctx.drawImage(
					gainmapImage.source,
					0,
					0,
					gainmapImage.width,
					gainmapImage.height,
					0,
					0,
					sdrImage.width,
					sdrImage.height
				);
				const gainmapImageData = ctx.getImageData(
					0,
					0,
					sdrImage.width,
					sdrImage.height,
					{ colorSpace: 'srgb' }
				);

				ctx.drawImage( sdrImage.source, 0, 0 );
				const sdrImageData = ctx.getImageData(
					0,
					0,
					sdrImage.width,
					sdrImage.height,
					{ colorSpace: 'srgb' }
				);

				/* HDR Recovery formula - https://developer.android.com/media/platform/hdr-image-format#use_the_gain_map_to_create_adapted_HDR_rendition */
				let hdrBuffer;

				if ( this.type === HalfFloatType ) {

					hdrBuffer = new Uint16Array( sdrImageData.data.length ).fill( 23544 );

				} else {

					hdrBuffer = new Float32Array( sdrImageData.data.length ).fill( 255 );

				}

				const maxDisplayBoost = Math.sqrt(
					Math.pow(
						/* 1.8 instead of 2 near-perfectly rectifies approximations introduced by precalculated SRGB_TO_LINEAR values */
						1.8,
						xmpMetadata.hdrCapacityMax
					)
				);
				const unclampedWeightFactor =
					( Math.log2( maxDisplayBoost ) - xmpMetadata.hdrCapacityMin ) /
					( xmpMetadata.hdrCapacityMax - xmpMetadata.hdrCapacityMin );
				const weightFactor = Math.min(
					Math.max( unclampedWeightFactor, 0.0 ),
					1.0
				);
				const useGammaOne = xmpMetadata.gamma === 1.0;

				for (
					let pixelIndex = 0;
					pixelIndex < sdrImageData.data.length;
					pixelIndex += 4
				) {

					const x = ( pixelIndex / 4 ) % sdrImage.width;
					const y = Math.floor( pixelIndex / 4 / sdrImage.width );

					for ( let channelIndex = 0; channelIndex < 3; channelIndex ++ ) {

						const sdrValue = sdrImageData.data[ pixelIndex + channelIndex ];

						const gainmapIndex = ( y * sdrImage.width + x ) * 4 + channelIndex;
						const gainmapValue = gainmapImageData.data[ gainmapIndex ] / 255.0;

						/* Gamma is 1.0 by default */
						const logRecovery = useGammaOne
							? gainmapValue
							: Math.pow( gainmapValue, 1.0 / xmpMetadata.gamma );

						const logBoost =
							xmpMetadata.gainMapMin * ( 1.0 - logRecovery ) +
							xmpMetadata.gainMapMax * logRecovery;

						const hdrValue =
							( sdrValue + xmpMetadata.offsetSDR ) *
								( logBoost * weightFactor === 0.0
									? 1.0
									: Math.pow( 2, logBoost * weightFactor ) ) -
							xmpMetadata.offsetHDR;

						const linearHDRValue = Math.min(
							Math.max( this._srgbToLinear( hdrValue ), 0 ),
							65504
						);

						hdrBuffer[ pixelIndex + channelIndex ] =
							this.type === HalfFloatType
								? DataUtils.toHalfFloat( linearHDRValue )
								: linearHDRValue;

					}

				}

				onSuccess( hdrBuffer, sdrImage.width, sdrImage.height );

			} )
			.catch`

**Internal Comments:**
```
/* Use out-of-the-box interpolation of Canvas API to scale gainmap to fit the SDR resolution */ (x4)
/* HDR Recovery formula - https://developer.android.com/media/platform/hdr-image-format#use_the_gain_map_to_create_adapted_HDR_rendition */ (x2)
/* 1.8 instead of 2 near-perfectly rectifies approximations introduced by precalculated SRGB_TO_LINEAR values */
/* Gamma is 1.0 by default */ (x2)
```

<details><summary>Code</summary>

```typescript
_applyGainmapToSDR(
		xmpMetadata,
		sdrBuffer,
		gainmapBuffer,
		onSuccess,
		onError
	) {

		const getImageDataFromBuffer = ( buffer ) =>
			new Promise( ( resolve, reject ) => {

				const imageLoader = document.createElement( 'img' );

				imageLoader.onload = () => {

					const image = {
						width: imageLoader.naturalWidth,
						height: imageLoader.naturalHeight,
						source: imageLoader,
					};

					URL.revokeObjectURL( imageLoader.src );

					resolve( image );

				};

				imageLoader.onerror = () => {

					URL.revokeObjectURL( imageLoader.src );

					reject();

				};

				imageLoader.src = URL.createObjectURL(
					new Blob( [ buffer ], { type: 'image/jpeg' } )
				);

			} );

		Promise.all( [
			getImageDataFromBuffer( sdrBuffer ),
			getImageDataFromBuffer( gainmapBuffer ),
		] )
			.then( ( [ sdrImage, gainmapImage ] ) => {

				const sdrImageAspect = sdrImage.width / sdrImage.height;
				const gainmapImageAspect = gainmapImage.width / gainmapImage.height;

				if ( sdrImageAspect !== gainmapImageAspect ) {

					onError(
						'THREE.UltraHDRLoader Error: Aspect ratio mismatch between SDR and Gainmap images'
					);

					return;

				}

				const canvas = document.createElement( 'canvas' );
				const ctx = canvas.getContext( '2d', {
					willReadFrequently: true,
					colorSpace: 'srgb',
				} );

				canvas.width = sdrImage.width;
				canvas.height = sdrImage.height;

				/* Use out-of-the-box interpolation of Canvas API to scale gainmap to fit the SDR resolution */
				ctx.drawImage(
					gainmapImage.source,
					0,
					0,
					gainmapImage.width,
					gainmapImage.height,
					0,
					0,
					sdrImage.width,
					sdrImage.height
				);
				const gainmapImageData = ctx.getImageData(
					0,
					0,
					sdrImage.width,
					sdrImage.height,
					{ colorSpace: 'srgb' }
				);

				ctx.drawImage( sdrImage.source, 0, 0 );
				const sdrImageData = ctx.getImageData(
					0,
					0,
					sdrImage.width,
					sdrImage.height,
					{ colorSpace: 'srgb' }
				);

				/* HDR Recovery formula - https://developer.android.com/media/platform/hdr-image-format#use_the_gain_map_to_create_adapted_HDR_rendition */
				let hdrBuffer;

				if ( this.type === HalfFloatType ) {

					hdrBuffer = new Uint16Array( sdrImageData.data.length ).fill( 23544 );

				} else {

					hdrBuffer = new Float32Array( sdrImageData.data.length ).fill( 255 );

				}

				const maxDisplayBoost = Math.sqrt(
					Math.pow(
						/* 1.8 instead of 2 near-perfectly rectifies approximations introduced by precalculated SRGB_TO_LINEAR values */
						1.8,
						xmpMetadata.hdrCapacityMax
					)
				);
				const unclampedWeightFactor =
					( Math.log2( maxDisplayBoost ) - xmpMetadata.hdrCapacityMin ) /
					( xmpMetadata.hdrCapacityMax - xmpMetadata.hdrCapacityMin );
				const weightFactor = Math.min(
					Math.max( unclampedWeightFactor, 0.0 ),
					1.0
				);
				const useGammaOne = xmpMetadata.gamma === 1.0;

				for (
					let pixelIndex = 0;
					pixelIndex < sdrImageData.data.length;
					pixelIndex += 4
				) {

					const x = ( pixelIndex / 4 ) % sdrImage.width;
					const y = Math.floor( pixelIndex / 4 / sdrImage.width );

					for ( let channelIndex = 0; channelIndex < 3; channelIndex ++ ) {

						const sdrValue = sdrImageData.data[ pixelIndex + channelIndex ];

						const gainmapIndex = ( y * sdrImage.width + x ) * 4 + channelIndex;
						const gainmapValue = gainmapImageData.data[ gainmapIndex ] / 255.0;

						/* Gamma is 1.0 by default */
						const logRecovery = useGammaOne
							? gainmapValue
							: Math.pow( gainmapValue, 1.0 / xmpMetadata.gamma );

						const logBoost =
							xmpMetadata.gainMapMin * ( 1.0 - logRecovery ) +
							xmpMetadata.gainMapMax * logRecovery;

						const hdrValue =
							( sdrValue + xmpMetadata.offsetSDR ) *
								( logBoost * weightFactor === 0.0
									? 1.0
									: Math.pow( 2, logBoost * weightFactor ) ) -
							xmpMetadata.offsetHDR;

						const linearHDRValue = Math.min(
							Math.max( this._srgbToLinear( hdrValue ), 0 ),
							65504
						);

						hdrBuffer[ pixelIndex + channelIndex ] =
							this.type === HalfFloatType
								? DataUtils.toHalfFloat( linearHDRValue )
								: linearHDRValue;

					}

				}

				onSuccess( hdrBuffer, sdrImage.width, sdrImage.height );

			} )
			.catch( () => {

				throw new Error(
					'THREE.UltraHDRLoader Error: Could not parse UltraHDR images'
				);

			} );

	}
```
</details>

### `getImageDataFromBuffer(buffer: any): Promise<any>`

**Parameters:**

- **`buffer`** `any`

**Returns:** `Promise<any>`

<details><summary>Code</summary>

```typescript
( buffer ) =>
			new Promise( ( resolve, reject ) => {

				const imageLoader = document.createElement( 'img' );

				imageLoader.onload = () => {

					const image = {
						width: imageLoader.naturalWidth,
						height: imageLoader.naturalHeight,
						source: imageLoader,
					};

					URL.revokeObjectURL( imageLoader.src );

					resolve( image );

				};

				imageLoader.onerror = () => {

					URL.revokeObjectURL( imageLoader.src );

					reject();

				};

				imageLoader.src = URL.createObjectURL(
					new Blob( [ buffer ], { type: 'image/jpeg' } )
				);

			} )
```
</details>


---

## Classes

### `UltraHDRLoader`

<details><summary>Class Code</summary>

```ts
class UltraHDRLoader extends Loader {

	/**
	 * Constructs a new Ultra HDR loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		/**
		 * The texture type.
		 *
		 * @type {(HalfFloatType|FloatType)}
		 * @default HalfFloatType
		 */
		this.type = HalfFloatType;

	}

	/**
	 * Sets the texture type.
	 *
	 * @param {(HalfFloatType|FloatType)} value - The texture type to set.
	 * @return {RGBELoader} A reference to this loader.
	 */
	setDataType( value ) {

		this.type = value;

		return this;

	}

	/**
	 * Parses the given Ultra HDR texture data.
	 *
	 * @param {ArrayBuffer} buffer - The raw texture data.
	 * @param {Function} onLoad - The `onLoad` callback.
	 */
	parse( buffer, onLoad ) {

		const xmpMetadata = {
			version: null,
			baseRenditionIsHDR: null,
			gainMapMin: null,
			gainMapMax: null,
			gamma: null,
			offsetSDR: null,
			offsetHDR: null,
			hdrCapacityMin: null,
			hdrCapacityMax: null,
		};
		const textDecoder = new TextDecoder();

		const data = new DataView( buffer );

		let byteOffset = 0;
		const sections = [];

		while ( byteOffset < data.byteLength ) {

			const byte = data.getUint8( byteOffset );

			if ( byte === 0xff ) {

				const leadingByte = data.getUint8( byteOffset + 1 );

				if (
					[
						/* Valid section headers */
						0xd8, // SOI
						0xe0, // APP0
						0xe1, // APP1
						0xe2, // APP2
					].includes( leadingByte )
				) {

					sections.push( {
						sectionType: leadingByte,
						section: [ byte, leadingByte ],
						sectionOffset: byteOffset + 2,
					} );

					byteOffset += 2;

				} else {

					sections[ sections.length - 1 ].section.push( byte, leadingByte );

					byteOffset += 2;

				}

			} else {

				sections[ sections.length - 1 ].section.push( byte );

				byteOffset ++;

			}

		}

		let primaryImage, gainmapImage;

		for ( let i = 0; i < sections.length; i ++ ) {

			const { sectionType, section, sectionOffset } = sections[ i ];

			if ( sectionType === 0xe0 ) {
				/* JPEG Header - no useful information */
			} else if ( sectionType === 0xe1 ) {

				/* XMP Metadata */

				this._parseXMPMetadata(
					textDecoder.decode( new Uint8Array( section ) ),
					xmpMetadata
				);

			} else if ( sectionType === 0xe2 ) {

				/* Data Sections - MPF / EXIF / ICC Profile */

				const sectionData = new DataView(
					new Uint8Array( section.slice( 2 ) ).buffer
				);
				const sectionHeader = sectionData.getUint32( 2, false );

				if ( sectionHeader === 0x4d504600 ) {

					/* MPF Section */

					/* Section contains a list of static bytes and ends with offsets indicating location of SDR and gainmap images */
					/* First bytes after header indicate little / big endian ordering (0x49492A00 - LE / 0x4D4D002A - BE) */
					/*
					... 60 bytes indicating tags, versions, etc. ...

					bytes | bits | description

					4       32     primary image size
					4       32     primary image offset
					2       16     0x0000
					2       16     0x0000

					4       32     0x00000000
					4       32     gainmap image size
					4       32     gainmap image offset
					2       16     0x0000
					2       16     0x0000
					*/

					const mpfLittleEndian = sectionData.getUint32( 6 ) === 0x49492a00;
					const mpfBytesOffset = 60;

					/* SDR size includes the metadata length, SDR offset is always 0 */

					const primaryImageSize = sectionData.getUint32(
						mpfBytesOffset,
						mpfLittleEndian
					);
					const primaryImageOffset = sectionData.getUint32(
						mpfBytesOffset + 4,
						mpfLittleEndian
					);

					/* Gainmap size is an absolute value starting from its offset, gainmap offset needs 6 bytes padding to take into account 0x00 bytes at the end of XMP */
					const gainmapImageSize = sectionData.getUint32(
						mpfBytesOffset + 16,
						mpfLittleEndian
					);
					const gainmapImageOffset =
						sectionData.getUint32( mpfBytesOffset + 20, mpfLittleEndian ) +
						sectionOffset +
						6;

					primaryImage = new Uint8Array(
						data.buffer,
						primaryImageOffset,
						primaryImageSize
					);

					gainmapImage = new Uint8Array(
						data.buffer,
						gainmapImageOffset,
						gainmapImageSize
					);

				}

			}

		}

		/* Minimal sufficient validation - https://developer.android.com/media/platform/hdr-image-format#signal_of_the_format */
		if ( ! xmpMetadata.version ) {

			throw new Error( 'THREE.UltraHDRLoader: Not a valid UltraHDR image' );

		}

		if ( primaryImage && gainmapImage ) {

			this._applyGainmapToSDR(
				xmpMetadata,
				primaryImage,
				gainmapImage,
				( hdrBuffer, width, height ) => {

					onLoad( {
						width,
						height,
						data: hdrBuffer,
						format: RGBAFormat,
						type: this.type,
					} );

				},
				( error ) => {

					throw new Error( error );

				}
			);

		} else {

			throw new Error( 'THREE.UltraHDRLoader: Could not parse UltraHDR images' );

		}

	}

	/**
	 * Starts loading from the given URL and passes the loaded Ultra HDR texture
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the files to be loaded. This can also be a data URI.
	 * @param {function(DataTexture, Object)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 * @return {DataTexture} The Ultra HDR texture.
	 */
	load( url, onLoad, onProgress, onError ) {

		const texture = new DataTexture(
			this.type === HalfFloatType ? new Uint16Array() : new Float32Array(),
			0,
			0,
			RGBAFormat,
			this.type,
			UVMapping,
			ClampToEdgeWrapping,
			ClampToEdgeWrapping,
			LinearFilter,
			LinearMipMapLinearFilter,
			1,
			LinearSRGBColorSpace
		);
		texture.generateMipmaps = true;
		texture.flipY = true;

		const loader = new FileLoader( this.manager );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( this.requestHeader );
		loader.setPath( this.path );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, ( buffer ) => {

			try {

				this.parse(
					buffer,
					( texData ) => {

						texture.image = {
							data: texData.data,
							width: texData.width,
							height: texData.height,
						};
						texture.needsUpdate = true;

						if ( onLoad ) onLoad( texture, texData );

					}
				);

			} catch ( error ) {

				if ( onError ) onError( error );

				console.error( error );

			}

		}, onProgress, onError );

		return texture;

	}

	_parseXMPMetadata( xmpDataString, xmpMetadata ) {

		const domParser = new DOMParser();

		const xmpXml = domParser.parseFromString(
			xmpDataString.substring(
				xmpDataString.indexOf( '<' ),
				xmpDataString.lastIndexOf( '>' ) + 1
			),
			'text/xml'
		);

		/* Determine if given XMP metadata is the primary GContainer descriptor or a gainmap descriptor */
		const [ hasHDRContainerDescriptor ] = xmpXml.getElementsByTagName(
			'Container:Directory'
		);

		if ( hasHDRContainerDescriptor ) {
			/* There's not much useful information in the container descriptor besides memory-validation */
		} else {

			/* Gainmap descriptor - defaults from https://developer.android.com/media/platform/hdr-image-format#HDR_gain_map_metadata */

			const [ gainmapNode ] = xmpXml.getElementsByTagName( 'rdf:Description' );

			xmpMetadata.version = gainmapNode.getAttribute( 'hdrgm:Version' );
			xmpMetadata.baseRenditionIsHDR =
				gainmapNode.getAttribute( 'hdrgm:BaseRenditionIsHDR' ) === 'True';
			xmpMetadata.gainMapMin = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:GainMapMin' ) || 0.0
			);
			xmpMetadata.gainMapMax = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:GainMapMax' ) || 1.0
			);
			xmpMetadata.gamma = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:Gamma' ) || 1.0
			);
			xmpMetadata.offsetSDR = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:OffsetSDR' ) / ( 1 / 64 )
			);
			xmpMetadata.offsetHDR = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:OffsetHDR' ) / ( 1 / 64 )
			);
			xmpMetadata.hdrCapacityMin = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:HDRCapacityMin' ) || 0.0
			);
			xmpMetadata.hdrCapacityMax = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:HDRCapacityMax' ) || 1.0
			);

		}

	}

	_srgbToLinear( value ) {

		if ( value / 255 < 0.04045 ) {

			return ( value / 255 ) * 0.0773993808;

		}

		if ( value < 1024 ) {

			return SRGB_TO_LINEAR[ ~ ~ value ];

		}

		return Math.pow( ( value / 255 ) * 0.9478672986 + 0.0521327014, 2.4 );

	}

	_applyGainmapToSDR(
		xmpMetadata,
		sdrBuffer,
		gainmapBuffer,
		onSuccess,
		onError
	) {

		const getImageDataFromBuffer = ( buffer ) =>
			new Promise( ( resolve, reject ) => {

				const imageLoader = document.createElement( 'img' );

				imageLoader.onload = () => {

					const image = {
						width: imageLoader.naturalWidth,
						height: imageLoader.naturalHeight,
						source: imageLoader,
					};

					URL.revokeObjectURL( imageLoader.src );

					resolve( image );

				};

				imageLoader.onerror = () => {

					URL.revokeObjectURL( imageLoader.src );

					reject();

				};

				imageLoader.src = URL.createObjectURL(
					new Blob( [ buffer ], { type: 'image/jpeg' } )
				);

			} );

		Promise.all( [
			getImageDataFromBuffer( sdrBuffer ),
			getImageDataFromBuffer( gainmapBuffer ),
		] )
			.then( ( [ sdrImage, gainmapImage ] ) => {

				const sdrImageAspect = sdrImage.width / sdrImage.height;
				const gainmapImageAspect = gainmapImage.width / gainmapImage.height;

				if ( sdrImageAspect !== gainmapImageAspect ) {

					onError(
						'THREE.UltraHDRLoader Error: Aspect ratio mismatch between SDR and Gainmap images'
					);

					return;

				}

				const canvas = document.createElement( 'canvas' );
				const ctx = canvas.getContext( '2d', {
					willReadFrequently: true,
					colorSpace: 'srgb',
				} );

				canvas.width = sdrImage.width;
				canvas.height = sdrImage.height;

				/* Use out-of-the-box interpolation of Canvas API to scale gainmap to fit the SDR resolution */
				ctx.drawImage(
					gainmapImage.source,
					0,
					0,
					gainmapImage.width,
					gainmapImage.height,
					0,
					0,
					sdrImage.width,
					sdrImage.height
				);
				const gainmapImageData = ctx.getImageData(
					0,
					0,
					sdrImage.width,
					sdrImage.height,
					{ colorSpace: 'srgb' }
				);

				ctx.drawImage( sdrImage.source, 0, 0 );
				const sdrImageData = ctx.getImageData(
					0,
					0,
					sdrImage.width,
					sdrImage.height,
					{ colorSpace: 'srgb' }
				);

				/* HDR Recovery formula - https://developer.android.com/media/platform/hdr-image-format#use_the_gain_map_to_create_adapted_HDR_rendition */
				let hdrBuffer;

				if ( this.type === HalfFloatType ) {

					hdrBuffer = new Uint16Array( sdrImageData.data.length ).fill( 23544 );

				} else {

					hdrBuffer = new Float32Array( sdrImageData.data.length ).fill( 255 );

				}

				const maxDisplayBoost = Math.sqrt(
					Math.pow(
						/* 1.8 instead of 2 near-perfectly rectifies approximations introduced by precalculated SRGB_TO_LINEAR values */
						1.8,
						xmpMetadata.hdrCapacityMax
					)
				);
				const unclampedWeightFactor =
					( Math.log2( maxDisplayBoost ) - xmpMetadata.hdrCapacityMin ) /
					( xmpMetadata.hdrCapacityMax - xmpMetadata.hdrCapacityMin );
				const weightFactor = Math.min(
					Math.max( unclampedWeightFactor, 0.0 ),
					1.0
				);
				const useGammaOne = xmpMetadata.gamma === 1.0;

				for (
					let pixelIndex = 0;
					pixelIndex < sdrImageData.data.length;
					pixelIndex += 4
				) {

					const x = ( pixelIndex / 4 ) % sdrImage.width;
					const y = Math.floor( pixelIndex / 4 / sdrImage.width );

					for ( let channelIndex = 0; channelIndex < 3; channelIndex ++ ) {

						const sdrValue = sdrImageData.data[ pixelIndex + channelIndex ];

						const gainmapIndex = ( y * sdrImage.width + x ) * 4 + channelIndex;
						const gainmapValue = gainmapImageData.data[ gainmapIndex ] / 255.0;

						/* Gamma is 1.0 by default */
						const logRecovery = useGammaOne
							? gainmapValue
							: Math.pow( gainmapValue, 1.0 / xmpMetadata.gamma );

						const logBoost =
							xmpMetadata.gainMapMin * ( 1.0 - logRecovery ) +
							xmpMetadata.gainMapMax * logRecovery;

						const hdrValue =
							( sdrValue + xmpMetadata.offsetSDR ) *
								( logBoost * weightFactor === 0.0
									? 1.0
									: Math.pow( 2, logBoost * weightFactor ) ) -
							xmpMetadata.offsetHDR;

						const linearHDRValue = Math.min(
							Math.max( this._srgbToLinear( hdrValue ), 0 ),
							65504
						);

						hdrBuffer[ pixelIndex + channelIndex ] =
							this.type === HalfFloatType
								? DataUtils.toHalfFloat( linearHDRValue )
								: linearHDRValue;

					}

				}

				onSuccess( hdrBuffer, sdrImage.width, sdrImage.height );

			} )
			.catch( () => {

				throw new Error(
					'THREE.UltraHDRLoader Error: Could not parse UltraHDR images'
				);

			} );

	}

}
```
</details>

#### Methods

##### `setDataType(value: any): RGBELoader`

<details><summary>Code</summary>

```ts
setDataType( value ) {

		this.type = value;

		return this;

	}
```
</details>

##### `parse(buffer: ArrayBuffer, onLoad: Function): void`

<details><summary>Code</summary>

```ts
parse( buffer, onLoad ) {

		const xmpMetadata = {
			version: null,
			baseRenditionIsHDR: null,
			gainMapMin: null,
			gainMapMax: null,
			gamma: null,
			offsetSDR: null,
			offsetHDR: null,
			hdrCapacityMin: null,
			hdrCapacityMax: null,
		};
		const textDecoder = new TextDecoder();

		const data = new DataView( buffer );

		let byteOffset = 0;
		const sections = [];

		while ( byteOffset < data.byteLength ) {

			const byte = data.getUint8( byteOffset );

			if ( byte === 0xff ) {

				const leadingByte = data.getUint8( byteOffset + 1 );

				if (
					[
						/* Valid section headers */
						0xd8, // SOI
						0xe0, // APP0
						0xe1, // APP1
						0xe2, // APP2
					].includes( leadingByte )
				) {

					sections.push( {
						sectionType: leadingByte,
						section: [ byte, leadingByte ],
						sectionOffset: byteOffset + 2,
					} );

					byteOffset += 2;

				} else {

					sections[ sections.length - 1 ].section.push( byte, leadingByte );

					byteOffset += 2;

				}

			} else {

				sections[ sections.length - 1 ].section.push( byte );

				byteOffset ++;

			}

		}

		let primaryImage, gainmapImage;

		for ( let i = 0; i < sections.length; i ++ ) {

			const { sectionType, section, sectionOffset } = sections[ i ];

			if ( sectionType === 0xe0 ) {
				/* JPEG Header - no useful information */
			} else if ( sectionType === 0xe1 ) {

				/* XMP Metadata */

				this._parseXMPMetadata(
					textDecoder.decode( new Uint8Array( section ) ),
					xmpMetadata
				);

			} else if ( sectionType === 0xe2 ) {

				/* Data Sections - MPF / EXIF / ICC Profile */

				const sectionData = new DataView(
					new Uint8Array( section.slice( 2 ) ).buffer
				);
				const sectionHeader = sectionData.getUint32( 2, false );

				if ( sectionHeader === 0x4d504600 ) {

					/* MPF Section */

					/* Section contains a list of static bytes and ends with offsets indicating location of SDR and gainmap images */
					/* First bytes after header indicate little / big endian ordering (0x49492A00 - LE / 0x4D4D002A - BE) */
					/*
					... 60 bytes indicating tags, versions, etc. ...

					bytes | bits | description

					4       32     primary image size
					4       32     primary image offset
					2       16     0x0000
					2       16     0x0000

					4       32     0x00000000
					4       32     gainmap image size
					4       32     gainmap image offset
					2       16     0x0000
					2       16     0x0000
					*/

					const mpfLittleEndian = sectionData.getUint32( 6 ) === 0x49492a00;
					const mpfBytesOffset = 60;

					/* SDR size includes the metadata length, SDR offset is always 0 */

					const primaryImageSize = sectionData.getUint32(
						mpfBytesOffset,
						mpfLittleEndian
					);
					const primaryImageOffset = sectionData.getUint32(
						mpfBytesOffset + 4,
						mpfLittleEndian
					);

					/* Gainmap size is an absolute value starting from its offset, gainmap offset needs 6 bytes padding to take into account 0x00 bytes at the end of XMP */
					const gainmapImageSize = sectionData.getUint32(
						mpfBytesOffset + 16,
						mpfLittleEndian
					);
					const gainmapImageOffset =
						sectionData.getUint32( mpfBytesOffset + 20, mpfLittleEndian ) +
						sectionOffset +
						6;

					primaryImage = new Uint8Array(
						data.buffer,
						primaryImageOffset,
						primaryImageSize
					);

					gainmapImage = new Uint8Array(
						data.buffer,
						gainmapImageOffset,
						gainmapImageSize
					);

				}

			}

		}

		/* Minimal sufficient validation - https://developer.android.com/media/platform/hdr-image-format#signal_of_the_format */
		if ( ! xmpMetadata.version ) {

			throw new Error( 'THREE.UltraHDRLoader: Not a valid UltraHDR image' );

		}

		if ( primaryImage && gainmapImage ) {

			this._applyGainmapToSDR(
				xmpMetadata,
				primaryImage,
				gainmapImage,
				( hdrBuffer, width, height ) => {

					onLoad( {
						width,
						height,
						data: hdrBuffer,
						format: RGBAFormat,
						type: this.type,
					} );

				},
				( error ) => {

					throw new Error( error );

				}
			);

		} else {

			throw new Error( 'THREE.UltraHDRLoader: Could not parse UltraHDR images' );

		}

	}
```
</details>

##### `load(url: string, onLoad: (arg0: DataTexture, arg1: any) => any, onProgress: onProgressCallback, onError: onErrorCallback): DataTexture`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const texture = new DataTexture(
			this.type === HalfFloatType ? new Uint16Array() : new Float32Array(),
			0,
			0,
			RGBAFormat,
			this.type,
			UVMapping,
			ClampToEdgeWrapping,
			ClampToEdgeWrapping,
			LinearFilter,
			LinearMipMapLinearFilter,
			1,
			LinearSRGBColorSpace
		);
		texture.generateMipmaps = true;
		texture.flipY = true;

		const loader = new FileLoader( this.manager );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( this.requestHeader );
		loader.setPath( this.path );
		loader.setWithCredentials( this.withCredentials );
		loader.load( url, ( buffer ) => {

			try {

				this.parse(
					buffer,
					( texData ) => {

						texture.image = {
							data: texData.data,
							width: texData.width,
							height: texData.height,
						};
						texture.needsUpdate = true;

						if ( onLoad ) onLoad( texture, texData );

					}
				);

			} catch ( error ) {

				if ( onError ) onError( error );

				console.error( error );

			}

		}, onProgress, onError );

		return texture;

	}
```
</details>

##### `_parseXMPMetadata(xmpDataString: any, xmpMetadata: any): void`

<details><summary>Code</summary>

```ts
_parseXMPMetadata( xmpDataString, xmpMetadata ) {

		const domParser = new DOMParser();

		const xmpXml = domParser.parseFromString(
			xmpDataString.substring(
				xmpDataString.indexOf( '<' ),
				xmpDataString.lastIndexOf( '>' ) + 1
			),
			'text/xml'
		);

		/* Determine if given XMP metadata is the primary GContainer descriptor or a gainmap descriptor */
		const [ hasHDRContainerDescriptor ] = xmpXml.getElementsByTagName(
			'Container:Directory'
		);

		if ( hasHDRContainerDescriptor ) {
			/* There's not much useful information in the container descriptor besides memory-validation */
		} else {

			/* Gainmap descriptor - defaults from https://developer.android.com/media/platform/hdr-image-format#HDR_gain_map_metadata */

			const [ gainmapNode ] = xmpXml.getElementsByTagName( 'rdf:Description' );

			xmpMetadata.version = gainmapNode.getAttribute( 'hdrgm:Version' );
			xmpMetadata.baseRenditionIsHDR =
				gainmapNode.getAttribute( 'hdrgm:BaseRenditionIsHDR' ) === 'True';
			xmpMetadata.gainMapMin = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:GainMapMin' ) || 0.0
			);
			xmpMetadata.gainMapMax = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:GainMapMax' ) || 1.0
			);
			xmpMetadata.gamma = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:Gamma' ) || 1.0
			);
			xmpMetadata.offsetSDR = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:OffsetSDR' ) / ( 1 / 64 )
			);
			xmpMetadata.offsetHDR = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:OffsetHDR' ) / ( 1 / 64 )
			);
			xmpMetadata.hdrCapacityMin = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:HDRCapacityMin' ) || 0.0
			);
			xmpMetadata.hdrCapacityMax = parseFloat(
				gainmapNode.getAttribute( 'hdrgm:HDRCapacityMax' ) || 1.0
			);

		}

	}
```
</details>

##### `_srgbToLinear(value: any): number`

<details><summary>Code</summary>

```ts
_srgbToLinear( value ) {

		if ( value / 255 < 0.04045 ) {

			return ( value / 255 ) * 0.0773993808;

		}

		if ( value < 1024 ) {

			return SRGB_TO_LINEAR[ ~ ~ value ];

		}

		return Math.pow( ( value / 255 ) * 0.9478672986 + 0.0521327014, 2.4 );

	}
```
</details>

##### `_applyGainmapToSDR(xmpMetadata: any, sdrBuffer: any, gainmapBuffer: any, onSuccess: any, onError: any): void`

<details><summary>Code</summary>

```ts
_applyGainmapToSDR(
		xmpMetadata,
		sdrBuffer,
		gainmapBuffer,
		onSuccess,
		onError
	) {

		const getImageDataFromBuffer = ( buffer ) =>
			new Promise( ( resolve, reject ) => {

				const imageLoader = document.createElement( 'img' );

				imageLoader.onload = () => {

					const image = {
						width: imageLoader.naturalWidth,
						height: imageLoader.naturalHeight,
						source: imageLoader,
					};

					URL.revokeObjectURL( imageLoader.src );

					resolve( image );

				};

				imageLoader.onerror = () => {

					URL.revokeObjectURL( imageLoader.src );

					reject();

				};

				imageLoader.src = URL.createObjectURL(
					new Blob( [ buffer ], { type: 'image/jpeg' } )
				);

			} );

		Promise.all( [
			getImageDataFromBuffer( sdrBuffer ),
			getImageDataFromBuffer( gainmapBuffer ),
		] )
			.then( ( [ sdrImage, gainmapImage ] ) => {

				const sdrImageAspect = sdrImage.width / sdrImage.height;
				const gainmapImageAspect = gainmapImage.width / gainmapImage.height;

				if ( sdrImageAspect !== gainmapImageAspect ) {

					onError(
						'THREE.UltraHDRLoader Error: Aspect ratio mismatch between SDR and Gainmap images'
					);

					return;

				}

				const canvas = document.createElement( 'canvas' );
				const ctx = canvas.getContext( '2d', {
					willReadFrequently: true,
					colorSpace: 'srgb',
				} );

				canvas.width = sdrImage.width;
				canvas.height = sdrImage.height;

				/* Use out-of-the-box interpolation of Canvas API to scale gainmap to fit the SDR resolution */
				ctx.drawImage(
					gainmapImage.source,
					0,
					0,
					gainmapImage.width,
					gainmapImage.height,
					0,
					0,
					sdrImage.width,
					sdrImage.height
				);
				const gainmapImageData = ctx.getImageData(
					0,
					0,
					sdrImage.width,
					sdrImage.height,
					{ colorSpace: 'srgb' }
				);

				ctx.drawImage( sdrImage.source, 0, 0 );
				const sdrImageData = ctx.getImageData(
					0,
					0,
					sdrImage.width,
					sdrImage.height,
					{ colorSpace: 'srgb' }
				);

				/* HDR Recovery formula - https://developer.android.com/media/platform/hdr-image-format#use_the_gain_map_to_create_adapted_HDR_rendition */
				let hdrBuffer;

				if ( this.type === HalfFloatType ) {

					hdrBuffer = new Uint16Array( sdrImageData.data.length ).fill( 23544 );

				} else {

					hdrBuffer = new Float32Array( sdrImageData.data.length ).fill( 255 );

				}

				const maxDisplayBoost = Math.sqrt(
					Math.pow(
						/* 1.8 instead of 2 near-perfectly rectifies approximations introduced by precalculated SRGB_TO_LINEAR values */
						1.8,
						xmpMetadata.hdrCapacityMax
					)
				);
				const unclampedWeightFactor =
					( Math.log2( maxDisplayBoost ) - xmpMetadata.hdrCapacityMin ) /
					( xmpMetadata.hdrCapacityMax - xmpMetadata.hdrCapacityMin );
				const weightFactor = Math.min(
					Math.max( unclampedWeightFactor, 0.0 ),
					1.0
				);
				const useGammaOne = xmpMetadata.gamma === 1.0;

				for (
					let pixelIndex = 0;
					pixelIndex < sdrImageData.data.length;
					pixelIndex += 4
				) {

					const x = ( pixelIndex / 4 ) % sdrImage.width;
					const y = Math.floor( pixelIndex / 4 / sdrImage.width );

					for ( let channelIndex = 0; channelIndex < 3; channelIndex ++ ) {

						const sdrValue = sdrImageData.data[ pixelIndex + channelIndex ];

						const gainmapIndex = ( y * sdrImage.width + x ) * 4 + channelIndex;
						const gainmapValue = gainmapImageData.data[ gainmapIndex ] / 255.0;

						/* Gamma is 1.0 by default */
						const logRecovery = useGammaOne
							? gainmapValue
							: Math.pow( gainmapValue, 1.0 / xmpMetadata.gamma );

						const logBoost =
							xmpMetadata.gainMapMin * ( 1.0 - logRecovery ) +
							xmpMetadata.gainMapMax * logRecovery;

						const hdrValue =
							( sdrValue + xmpMetadata.offsetSDR ) *
								( logBoost * weightFactor === 0.0
									? 1.0
									: Math.pow( 2, logBoost * weightFactor ) ) -
							xmpMetadata.offsetHDR;

						const linearHDRValue = Math.min(
							Math.max( this._srgbToLinear( hdrValue ), 0 ),
							65504
						);

						hdrBuffer[ pixelIndex + channelIndex ] =
							this.type === HalfFloatType
								? DataUtils.toHalfFloat( linearHDRValue )
								: linearHDRValue;

					}

				}

				onSuccess( hdrBuffer, sdrImage.width, sdrImage.height );

			} )
			.catch( () => {

				throw new Error(
					'THREE.UltraHDRLoader Error: Could not parse UltraHDR images'
				);

			} );

	}
```
</details>


---