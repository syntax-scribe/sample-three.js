[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `DDSLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 60 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/DDSLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `CompressedTextureLoader` | `three` |
| `RGBAFormat` | `three` |
| `RGBA_S3TC_DXT3_Format` | `three` |
| `RGBA_S3TC_DXT5_Format` | `three` |
| `RGB_ETC1_Format` | `three` |
| `RGB_S3TC_DXT1_Format` | `three` |
| `RGB_BPTC_SIGNED_Format` | `three` |
| `RGB_BPTC_UNSIGNED_Format` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `dds` | `{ mipmaps: any[]; width: number; heig...` | let/var | `{ mipmaps: [], width: 0, height: 0, format: null, mipmapCount: 1 }` | ✗ |
| `DDS_MAGIC` | `542327876` | let/var | `0x20534444` | ✗ |
| `DDSD_MIPMAPCOUNT` | `131072` | let/var | `0x20000` | ✗ |
| `DDSCAPS2_CUBEMAP` | `512` | let/var | `0x200` | ✗ |
| `DDSCAPS2_CUBEMAP_POSITIVEX` | `1024` | let/var | `0x400` | ✗ |
| `DDSCAPS2_CUBEMAP_NEGATIVEX` | `2048` | let/var | `0x800` | ✗ |
| `DDSCAPS2_CUBEMAP_POSITIVEY` | `4096` | let/var | `0x1000` | ✗ |
| `DDSCAPS2_CUBEMAP_NEGATIVEY` | `8192` | let/var | `0x2000` | ✗ |
| `DDSCAPS2_CUBEMAP_POSITIVEZ` | `16384` | let/var | `0x4000` | ✗ |
| `DDSCAPS2_CUBEMAP_NEGATIVEZ` | `32768` | let/var | `0x8000` | ✗ |
| `DXGI_FORMAT_BC6H_UF16` | `95` | let/var | `95` | ✗ |
| `DXGI_FORMAT_BC6H_SF16` | `96` | let/var | `96` | ✗ |
| `dataLength` | `number` | let/var | `width * height * 4` | ✗ |
| `srcBuffer` | `Uint8Array<any>` | let/var | `new Uint8Array( buffer, dataOffset, dataLength )` | ✗ |
| `byteArray` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( dataLength )` | ✗ |
| `dst` | `number` | let/var | `0` | ✗ |
| `src` | `number` | let/var | `0` | ✗ |
| `b` | `number` | let/var | `srcBuffer[ src ]` | ✗ |
| `g` | `number` | let/var | `srcBuffer[ src ]` | ✗ |
| `r` | `number` | let/var | `srcBuffer[ src ]` | ✗ |
| `a` | `number` | let/var | `srcBuffer[ src ]` | ✗ |
| `dataLength` | `number` | let/var | `width * height * 3` | ✗ |
| `srcBuffer` | `Uint8Array<any>` | let/var | `new Uint8Array( buffer, dataOffset, dataLength )` | ✗ |
| `byteArray` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( width * height * 4 )` | ✗ |
| `dst` | `number` | let/var | `0` | ✗ |
| `src` | `number` | let/var | `0` | ✗ |
| `b` | `number` | let/var | `srcBuffer[ src ]` | ✗ |
| `g` | `number` | let/var | `srcBuffer[ src ]` | ✗ |
| `r` | `number` | let/var | `srcBuffer[ src ]` | ✗ |
| `headerLengthInt` | `31` | let/var | `31` | ✗ |
| `extendedHeaderLengthInt` | `5` | let/var | `5` | ✗ |
| `off_magic` | `0` | let/var | `0` | ✗ |
| `off_size` | `1` | let/var | `1` | ✗ |
| `off_flags` | `2` | let/var | `2` | ✗ |
| `off_height` | `3` | let/var | `3` | ✗ |
| `off_width` | `4` | let/var | `4` | ✗ |
| `off_mipmapCount` | `7` | let/var | `7` | ✗ |
| `off_pfFourCC` | `21` | let/var | `21` | ✗ |
| `off_RGBBitCount` | `22` | let/var | `22` | ✗ |
| `off_RBitMask` | `23` | let/var | `23` | ✗ |
| `off_GBitMask` | `24` | let/var | `24` | ✗ |
| `off_BBitMask` | `25` | let/var | `25` | ✗ |
| `off_ABitMask` | `26` | let/var | `26` | ✗ |
| `off_caps2` | `28` | let/var | `28` | ✗ |
| `off_dxgiFormat` | `0` | let/var | `0` | ✗ |
| `header` | `Int32Array<ArrayBuffer>` | let/var | `new Int32Array( buffer, 0, headerLengthInt )` | ✗ |
| `blockBytes` | `any` | let/var | `*not shown*` | ✗ |
| `fourCC` | `number` | let/var | `header[ off_pfFourCC ]` | ✗ |
| `isRGBAUncompressed` | `boolean` | let/var | `false` | ✗ |
| `isRGBUncompressed` | `boolean` | let/var | `false` | ✗ |
| `dataOffset` | `number` | let/var | `header[ off_size ] + 4` | ✗ |
| `extendedHeader` | `Int32Array<ArrayBuffer>` | let/var | `new Int32Array( buffer, ( headerLengthInt + 1 ) * 4, extendedHeaderLengthInt )` | ✗ |
| `dxgiFormat` | `number` | let/var | `extendedHeader[ off_dxgiFormat ]` | ✗ |
| `caps2` | `number` | let/var | `header[ off_caps2 ]` | ✗ |
| `faces` | `1 \| 6` | let/var | `dds.isCubemap ? 6 : 1` | ✗ |
| `width` | `number` | let/var | `dds.width` | ✗ |
| `height` | `number` | let/var | `dds.height` | ✗ |
| `byteArray` | `any` | let/var | `*not shown*` | ✗ |
| `dataLength` | `any` | let/var | `*not shown*` | ✗ |
| `mipmap` | `{ data: Uint8Array<ArrayBuffer>; widt...` | let/var | `{ 'data': byteArray, 'width': width, 'height': height }` | ✗ |


---

## Functions

### `DDSLoader.parse(buffer: ArrayBuffer, loadMipmaps: boolean): CompressedTextureLoader`

**JSDoc:**
```typescript
/**
	 * Parses the given S3TC texture data.
	 *
	 * @param {ArrayBuffer} buffer - The raw texture data.
	 * @param {boolean} loadMipmaps - Whether to load mipmaps or not.
	 * @return {CompressedTextureLoader~TexData} An object representing the parsed texture data.
	 */
```

**Parameters:**

- **`buffer`** `ArrayBuffer`
- **`loadMipmaps`** `boolean`

**Returns:** `CompressedTextureLoader`

**Calls:**

- `value.charCodeAt`
- `String.fromCharCode`
- `fourCCToInt32`
- `console.error`
- `int32ToFourCC`
- `Math.max`
- `loadARGBMip`
- `loadRGBMip`
- `dds.mipmaps.push`

**Internal Comments:**
```
// Adapted from @toji's DDS utils (x2)
// https://github.com/toji/webgl-texture-utils/blob/master/texture-util/dds.js (x2)
// All values and structures referenced from: (x2)
// http://msdn.microsoft.com/en-us/library/bb943991.aspx/ (x2)
// const DDSD_CAPS = 0x1; (x2)
// const DDSD_HEIGHT = 0x2; (x2)
// const DDSD_WIDTH = 0x4; (x2)
// const DDSD_PITCH = 0x8; (x2)
// const DDSD_PIXELFORMAT = 0x1000; (x2)
// const DDSD_LINEARSIZE = 0x80000; (x2)
// const DDSD_DEPTH = 0x800000; (x2)
// const DDSCAPS_COMPLEX = 0x8; (x2)
// const DDSCAPS_MIPMAP = 0x400000; (x2)
// const DDSCAPS_TEXTURE = 0x1000; (x2)
// const DDSCAPS2_VOLUME = 0x200000; (x2)
// const DDPF_ALPHAPIXELS = 0x1; (x2)
// const DDPF_ALPHA = 0x2; (x2)
// const DDPF_FOURCC = 0x4; (x2)
// const DDPF_RGB = 0x40; (x2)
// const DDPF_YUV = 0x200; (x2)
// const DDPF_LUMINANCE = 0x20000; (x2)
// Offsets into the header array (x2)
// const off_pfFlags = 20; (x2)
// const off_caps = 27; (x2)
// const off_caps3 = 29; (x2)
// const off_caps4 = 30; (x2)
// If fourCC = DX10, the extended header starts after 32 (x2)
// Parse header (x2)
// Extract mipmaps buffers (x2)
```

<details><summary>Code</summary>

```typescript
parse( buffer, loadMipmaps ) {

		const dds = { mipmaps: [], width: 0, height: 0, format: null, mipmapCount: 1 };

		// Adapted from @toji's DDS utils
		// https://github.com/toji/webgl-texture-utils/blob/master/texture-util/dds.js

		// All values and structures referenced from:
		// http://msdn.microsoft.com/en-us/library/bb943991.aspx/

		const DDS_MAGIC = 0x20534444;

		// const DDSD_CAPS = 0x1;
		// const DDSD_HEIGHT = 0x2;
		// const DDSD_WIDTH = 0x4;
		// const DDSD_PITCH = 0x8;
		// const DDSD_PIXELFORMAT = 0x1000;
		const DDSD_MIPMAPCOUNT = 0x20000;
		// const DDSD_LINEARSIZE = 0x80000;
		// const DDSD_DEPTH = 0x800000;

		// const DDSCAPS_COMPLEX = 0x8;
		// const DDSCAPS_MIPMAP = 0x400000;
		// const DDSCAPS_TEXTURE = 0x1000;

		const DDSCAPS2_CUBEMAP = 0x200;
		const DDSCAPS2_CUBEMAP_POSITIVEX = 0x400;
		const DDSCAPS2_CUBEMAP_NEGATIVEX = 0x800;
		const DDSCAPS2_CUBEMAP_POSITIVEY = 0x1000;
		const DDSCAPS2_CUBEMAP_NEGATIVEY = 0x2000;
		const DDSCAPS2_CUBEMAP_POSITIVEZ = 0x4000;
		const DDSCAPS2_CUBEMAP_NEGATIVEZ = 0x8000;
		// const DDSCAPS2_VOLUME = 0x200000;

		// const DDPF_ALPHAPIXELS = 0x1;
		// const DDPF_ALPHA = 0x2;
		// const DDPF_FOURCC = 0x4;
		// const DDPF_RGB = 0x40;
		// const DDPF_YUV = 0x200;
		// const DDPF_LUMINANCE = 0x20000;

		const DXGI_FORMAT_BC6H_UF16 = 95;
		const DXGI_FORMAT_BC6H_SF16 = 96;

		function fourCCToInt32( value ) {

			return value.charCodeAt( 0 ) +
				( value.charCodeAt( 1 ) << 8 ) +
				( value.charCodeAt( 2 ) << 16 ) +
				( value.charCodeAt( 3 ) << 24 );

		}

		function int32ToFourCC( value ) {

			return String.fromCharCode(
				value & 0xff,
				( value >> 8 ) & 0xff,
				( value >> 16 ) & 0xff,
				( value >> 24 ) & 0xff
			);

		}

		function loadARGBMip( buffer, dataOffset, width, height ) {

			const dataLength = width * height * 4;
			const srcBuffer = new Uint8Array( buffer, dataOffset, dataLength );
			const byteArray = new Uint8Array( dataLength );
			let dst = 0;
			let src = 0;
			for ( let y = 0; y < height; y ++ ) {

				for ( let x = 0; x < width; x ++ ) {

					const b = srcBuffer[ src ]; src ++;
					const g = srcBuffer[ src ]; src ++;
					const r = srcBuffer[ src ]; src ++;
					const a = srcBuffer[ src ]; src ++;
					byteArray[ dst ] = r; dst ++;	//r
					byteArray[ dst ] = g; dst ++;	//g
					byteArray[ dst ] = b; dst ++;	//b
					byteArray[ dst ] = a; dst ++;	//a

				}

			}

			return byteArray;

		}

		function loadRGBMip( buffer, dataOffset, width, height ) {

			const dataLength = width * height * 3;
			const srcBuffer = new Uint8Array( buffer, dataOffset, dataLength );
			const byteArray = new Uint8Array( width * height * 4 );
			let dst = 0;
			let src = 0;
			for ( let y = 0; y < height; y ++ ) {

				for ( let x = 0; x < width; x ++ ) {

					const b = srcBuffer[ src ]; src ++;
					const g = srcBuffer[ src ]; src ++;
					const r = srcBuffer[ src ]; src ++;
					byteArray[ dst ] = r; dst ++;	//r
					byteArray[ dst ] = g; dst ++;	//g
					byteArray[ dst ] = b; dst ++;	//b
					byteArray[ dst ] = 255; dst ++; //a

				}

			}

			return byteArray;

		}

		const FOURCC_DXT1 = fourCCToInt32( 'DXT1' );
		const FOURCC_DXT3 = fourCCToInt32( 'DXT3' );
		const FOURCC_DXT5 = fourCCToInt32( 'DXT5' );
		const FOURCC_ETC1 = fourCCToInt32( 'ETC1' );
		const FOURCC_DX10 = fourCCToInt32( 'DX10' );

		const headerLengthInt = 31; // The header length in 32 bit ints
		const extendedHeaderLengthInt = 5; // The extended header length in 32 bit ints

		// Offsets into the header array

		const off_magic = 0;

		const off_size = 1;
		const off_flags = 2;
		const off_height = 3;
		const off_width = 4;

		const off_mipmapCount = 7;

		// const off_pfFlags = 20;
		const off_pfFourCC = 21;
		const off_RGBBitCount = 22;
		const off_RBitMask = 23;
		const off_GBitMask = 24;
		const off_BBitMask = 25;
		const off_ABitMask = 26;

		// const off_caps = 27;
		const off_caps2 = 28;
		// const off_caps3 = 29;
		// const off_caps4 = 30;

		// If fourCC = DX10, the extended header starts after 32
		const off_dxgiFormat = 0;

		// Parse header

		const header = new Int32Array( buffer, 0, headerLengthInt );

		if ( header[ off_magic ] !== DDS_MAGIC ) {

			console.error( 'THREE.DDSLoader.parse: Invalid magic number in DDS header.' );
			return dds;

		}

		let blockBytes;

		const fourCC = header[ off_pfFourCC ];

		let isRGBAUncompressed = false;
		let isRGBUncompressed = false;

		let dataOffset = header[ off_size ] + 4;

		switch ( fourCC ) {

			case FOURCC_DXT1:

				blockBytes = 8;
				dds.format = RGB_S3TC_DXT1_Format;
				break;

			case FOURCC_DXT3:

				blockBytes = 16;
				dds.format = RGBA_S3TC_DXT3_Format;
				break;

			case FOURCC_DXT5:

				blockBytes = 16;
				dds.format = RGBA_S3TC_DXT5_Format;
				break;

			case FOURCC_ETC1:

				blockBytes = 8;
				dds.format = RGB_ETC1_Format;
				break;

			case FOURCC_DX10:

				dataOffset += extendedHeaderLengthInt * 4;
				const extendedHeader = new Int32Array( buffer, ( headerLengthInt + 1 ) * 4, extendedHeaderLengthInt );
				const dxgiFormat = extendedHeader[ off_dxgiFormat ];
				switch ( dxgiFormat ) {

					case DXGI_FORMAT_BC6H_SF16: {

						blockBytes = 16;
						dds.format = RGB_BPTC_SIGNED_Format;
						break;

					}

					case DXGI_FORMAT_BC6H_UF16: {

						blockBytes = 16;
						dds.format = RGB_BPTC_UNSIGNED_Format;
						break;

					}

					default: {

						console.error( 'THREE.DDSLoader.parse: Unsupported DXGI_FORMAT code ', dxgiFormat );
						return dds;

					}

				}

				break;

			default:

				if ( header[ off_RGBBitCount ] === 32
					&& header[ off_RBitMask ] & 0xff0000
					&& header[ off_GBitMask ] & 0xff00
					&& header[ off_BBitMask ] & 0xff
					&& header[ off_ABitMask ] & 0xff000000 ) {

					isRGBAUncompressed = true;
					blockBytes = 64;
					dds.format = RGBAFormat;

				} else if ( header[ off_RGBBitCount ] === 24
					&& header[ off_RBitMask ] & 0xff0000
					&& header[ off_GBitMask ] & 0xff00
					&& header[ off_BBitMask ] & 0xff ) {

				    	isRGBUncompressed = true;
                    			blockBytes = 64;
                    			dds.format = RGBAFormat;

				} else {

					console.error( 'THREE.DDSLoader.parse: Unsupported FourCC code ', int32ToFourCC( fourCC ) );
					return dds;

				}

		}

		dds.mipmapCount = 1;

		if ( header[ off_flags ] & DDSD_MIPMAPCOUNT && loadMipmaps !== false ) {

			dds.mipmapCount = Math.max( 1, header[ off_mipmapCount ] );

		}

		const caps2 = header[ off_caps2 ];
		dds.isCubemap = caps2 & DDSCAPS2_CUBEMAP ? true : false;
		if ( dds.isCubemap && (
			! ( caps2 & DDSCAPS2_CUBEMAP_POSITIVEX ) ||
			! ( caps2 & DDSCAPS2_CUBEMAP_NEGATIVEX ) ||
			! ( caps2 & DDSCAPS2_CUBEMAP_POSITIVEY ) ||
			! ( caps2 & DDSCAPS2_CUBEMAP_NEGATIVEY ) ||
			! ( caps2 & DDSCAPS2_CUBEMAP_POSITIVEZ ) ||
			! ( caps2 & DDSCAPS2_CUBEMAP_NEGATIVEZ )
		) ) {

			console.error( 'THREE.DDSLoader.parse: Incomplete cubemap faces' );
			return dds;

		}

		dds.width = header[ off_width ];
		dds.height = header[ off_height ];

		// Extract mipmaps buffers

		const faces = dds.isCubemap ? 6 : 1;

		for ( let face = 0; face < faces; face ++ ) {

			let width = dds.width;
			let height = dds.height;

			for ( let i = 0; i < dds.mipmapCount; i ++ ) {

				let byteArray, dataLength;

				if ( isRGBAUncompressed ) {

					byteArray = loadARGBMip( buffer, dataOffset, width, height );
					dataLength = byteArray.length;

				} else if ( isRGBUncompressed ) {

					byteArray = loadRGBMip( buffer, dataOffset, width, height );
					dataLength = width * height * 3;

				} else {

					dataLength = Math.max( 4, width ) / 4 * Math.max( 4, height ) / 4 * blockBytes;
					byteArray = new Uint8Array( buffer, dataOffset, dataLength );

				}

				const mipmap = { 'data': byteArray, 'width': width, 'height': height };
				dds.mipmaps.push( mipmap );

				dataOffset += dataLength;

				width = Math.max( width >> 1, 1 );
				height = Math.max( height >> 1, 1 );

			}

		}

		return dds;

	}
```
</details>

### `fourCCToInt32(value: any): any`

**Parameters:**

- **`value`** `any`

**Returns:** `any`

**Calls:**

- `value.charCodeAt`

<details><summary>Code</summary>

```typescript
function fourCCToInt32( value ) {

			return value.charCodeAt( 0 ) +
				( value.charCodeAt( 1 ) << 8 ) +
				( value.charCodeAt( 2 ) << 16 ) +
				( value.charCodeAt( 3 ) << 24 );

		}
```
</details>

### `int32ToFourCC(value: any): string`

**Parameters:**

- **`value`** `any`

**Returns:** `string`

**Calls:**

- `String.fromCharCode`

<details><summary>Code</summary>

```typescript
function int32ToFourCC( value ) {

			return String.fromCharCode(
				value & 0xff,
				( value >> 8 ) & 0xff,
				( value >> 16 ) & 0xff,
				( value >> 24 ) & 0xff
			);

		}
```
</details>

### `loadARGBMip(buffer: any, dataOffset: any, width: any, height: any): Uint8Array<ArrayBuffer>`

**Parameters:**

- **`buffer`** `any`
- **`dataOffset`** `any`
- **`width`** `any`
- **`height`** `any`

**Returns:** `Uint8Array<ArrayBuffer>`

<details><summary>Code</summary>

```typescript
function loadARGBMip( buffer, dataOffset, width, height ) {

			const dataLength = width * height * 4;
			const srcBuffer = new Uint8Array( buffer, dataOffset, dataLength );
			const byteArray = new Uint8Array( dataLength );
			let dst = 0;
			let src = 0;
			for ( let y = 0; y < height; y ++ ) {

				for ( let x = 0; x < width; x ++ ) {

					const b = srcBuffer[ src ]; src ++;
					const g = srcBuffer[ src ]; src ++;
					const r = srcBuffer[ src ]; src ++;
					const a = srcBuffer[ src ]; src ++;
					byteArray[ dst ] = r; dst ++;	//r
					byteArray[ dst ] = g; dst ++;	//g
					byteArray[ dst ] = b; dst ++;	//b
					byteArray[ dst ] = a; dst ++;	//a

				}

			}

			return byteArray;

		}
```
</details>

### `loadRGBMip(buffer: any, dataOffset: any, width: any, height: any): Uint8Array<ArrayBuffer>`

**Parameters:**

- **`buffer`** `any`
- **`dataOffset`** `any`
- **`width`** `any`
- **`height`** `any`

**Returns:** `Uint8Array<ArrayBuffer>`

<details><summary>Code</summary>

```typescript
function loadRGBMip( buffer, dataOffset, width, height ) {

			const dataLength = width * height * 3;
			const srcBuffer = new Uint8Array( buffer, dataOffset, dataLength );
			const byteArray = new Uint8Array( width * height * 4 );
			let dst = 0;
			let src = 0;
			for ( let y = 0; y < height; y ++ ) {

				for ( let x = 0; x < width; x ++ ) {

					const b = srcBuffer[ src ]; src ++;
					const g = srcBuffer[ src ]; src ++;
					const r = srcBuffer[ src ]; src ++;
					byteArray[ dst ] = r; dst ++;	//r
					byteArray[ dst ] = g; dst ++;	//g
					byteArray[ dst ] = b; dst ++;	//b
					byteArray[ dst ] = 255; dst ++; //a

				}

			}

			return byteArray;

		}
```
</details>


---

## Classes

### `DDSLoader`

<details><summary>Class Code</summary>

```ts
class DDSLoader extends CompressedTextureLoader {

	/**
	 * Constructs a new DDS loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Parses the given S3TC texture data.
	 *
	 * @param {ArrayBuffer} buffer - The raw texture data.
	 * @param {boolean} loadMipmaps - Whether to load mipmaps or not.
	 * @return {CompressedTextureLoader~TexData} An object representing the parsed texture data.
	 */
	parse( buffer, loadMipmaps ) {

		const dds = { mipmaps: [], width: 0, height: 0, format: null, mipmapCount: 1 };

		// Adapted from @toji's DDS utils
		// https://github.com/toji/webgl-texture-utils/blob/master/texture-util/dds.js

		// All values and structures referenced from:
		// http://msdn.microsoft.com/en-us/library/bb943991.aspx/

		const DDS_MAGIC = 0x20534444;

		// const DDSD_CAPS = 0x1;
		// const DDSD_HEIGHT = 0x2;
		// const DDSD_WIDTH = 0x4;
		// const DDSD_PITCH = 0x8;
		// const DDSD_PIXELFORMAT = 0x1000;
		const DDSD_MIPMAPCOUNT = 0x20000;
		// const DDSD_LINEARSIZE = 0x80000;
		// const DDSD_DEPTH = 0x800000;

		// const DDSCAPS_COMPLEX = 0x8;
		// const DDSCAPS_MIPMAP = 0x400000;
		// const DDSCAPS_TEXTURE = 0x1000;

		const DDSCAPS2_CUBEMAP = 0x200;
		const DDSCAPS2_CUBEMAP_POSITIVEX = 0x400;
		const DDSCAPS2_CUBEMAP_NEGATIVEX = 0x800;
		const DDSCAPS2_CUBEMAP_POSITIVEY = 0x1000;
		const DDSCAPS2_CUBEMAP_NEGATIVEY = 0x2000;
		const DDSCAPS2_CUBEMAP_POSITIVEZ = 0x4000;
		const DDSCAPS2_CUBEMAP_NEGATIVEZ = 0x8000;
		// const DDSCAPS2_VOLUME = 0x200000;

		// const DDPF_ALPHAPIXELS = 0x1;
		// const DDPF_ALPHA = 0x2;
		// const DDPF_FOURCC = 0x4;
		// const DDPF_RGB = 0x40;
		// const DDPF_YUV = 0x200;
		// const DDPF_LUMINANCE = 0x20000;

		const DXGI_FORMAT_BC6H_UF16 = 95;
		const DXGI_FORMAT_BC6H_SF16 = 96;

		function fourCCToInt32( value ) {

			return value.charCodeAt( 0 ) +
				( value.charCodeAt( 1 ) << 8 ) +
				( value.charCodeAt( 2 ) << 16 ) +
				( value.charCodeAt( 3 ) << 24 );

		}

		function int32ToFourCC( value ) {

			return String.fromCharCode(
				value & 0xff,
				( value >> 8 ) & 0xff,
				( value >> 16 ) & 0xff,
				( value >> 24 ) & 0xff
			);

		}

		function loadARGBMip( buffer, dataOffset, width, height ) {

			const dataLength = width * height * 4;
			const srcBuffer = new Uint8Array( buffer, dataOffset, dataLength );
			const byteArray = new Uint8Array( dataLength );
			let dst = 0;
			let src = 0;
			for ( let y = 0; y < height; y ++ ) {

				for ( let x = 0; x < width; x ++ ) {

					const b = srcBuffer[ src ]; src ++;
					const g = srcBuffer[ src ]; src ++;
					const r = srcBuffer[ src ]; src ++;
					const a = srcBuffer[ src ]; src ++;
					byteArray[ dst ] = r; dst ++;	//r
					byteArray[ dst ] = g; dst ++;	//g
					byteArray[ dst ] = b; dst ++;	//b
					byteArray[ dst ] = a; dst ++;	//a

				}

			}

			return byteArray;

		}

		function loadRGBMip( buffer, dataOffset, width, height ) {

			const dataLength = width * height * 3;
			const srcBuffer = new Uint8Array( buffer, dataOffset, dataLength );
			const byteArray = new Uint8Array( width * height * 4 );
			let dst = 0;
			let src = 0;
			for ( let y = 0; y < height; y ++ ) {

				for ( let x = 0; x < width; x ++ ) {

					const b = srcBuffer[ src ]; src ++;
					const g = srcBuffer[ src ]; src ++;
					const r = srcBuffer[ src ]; src ++;
					byteArray[ dst ] = r; dst ++;	//r
					byteArray[ dst ] = g; dst ++;	//g
					byteArray[ dst ] = b; dst ++;	//b
					byteArray[ dst ] = 255; dst ++; //a

				}

			}

			return byteArray;

		}

		const FOURCC_DXT1 = fourCCToInt32( 'DXT1' );
		const FOURCC_DXT3 = fourCCToInt32( 'DXT3' );
		const FOURCC_DXT5 = fourCCToInt32( 'DXT5' );
		const FOURCC_ETC1 = fourCCToInt32( 'ETC1' );
		const FOURCC_DX10 = fourCCToInt32( 'DX10' );

		const headerLengthInt = 31; // The header length in 32 bit ints
		const extendedHeaderLengthInt = 5; // The extended header length in 32 bit ints

		// Offsets into the header array

		const off_magic = 0;

		const off_size = 1;
		const off_flags = 2;
		const off_height = 3;
		const off_width = 4;

		const off_mipmapCount = 7;

		// const off_pfFlags = 20;
		const off_pfFourCC = 21;
		const off_RGBBitCount = 22;
		const off_RBitMask = 23;
		const off_GBitMask = 24;
		const off_BBitMask = 25;
		const off_ABitMask = 26;

		// const off_caps = 27;
		const off_caps2 = 28;
		// const off_caps3 = 29;
		// const off_caps4 = 30;

		// If fourCC = DX10, the extended header starts after 32
		const off_dxgiFormat = 0;

		// Parse header

		const header = new Int32Array( buffer, 0, headerLengthInt );

		if ( header[ off_magic ] !== DDS_MAGIC ) {

			console.error( 'THREE.DDSLoader.parse: Invalid magic number in DDS header.' );
			return dds;

		}

		let blockBytes;

		const fourCC = header[ off_pfFourCC ];

		let isRGBAUncompressed = false;
		let isRGBUncompressed = false;

		let dataOffset = header[ off_size ] + 4;

		switch ( fourCC ) {

			case FOURCC_DXT1:

				blockBytes = 8;
				dds.format = RGB_S3TC_DXT1_Format;
				break;

			case FOURCC_DXT3:

				blockBytes = 16;
				dds.format = RGBA_S3TC_DXT3_Format;
				break;

			case FOURCC_DXT5:

				blockBytes = 16;
				dds.format = RGBA_S3TC_DXT5_Format;
				break;

			case FOURCC_ETC1:

				blockBytes = 8;
				dds.format = RGB_ETC1_Format;
				break;

			case FOURCC_DX10:

				dataOffset += extendedHeaderLengthInt * 4;
				const extendedHeader = new Int32Array( buffer, ( headerLengthInt + 1 ) * 4, extendedHeaderLengthInt );
				const dxgiFormat = extendedHeader[ off_dxgiFormat ];
				switch ( dxgiFormat ) {

					case DXGI_FORMAT_BC6H_SF16: {

						blockBytes = 16;
						dds.format = RGB_BPTC_SIGNED_Format;
						break;

					}

					case DXGI_FORMAT_BC6H_UF16: {

						blockBytes = 16;
						dds.format = RGB_BPTC_UNSIGNED_Format;
						break;

					}

					default: {

						console.error( 'THREE.DDSLoader.parse: Unsupported DXGI_FORMAT code ', dxgiFormat );
						return dds;

					}

				}

				break;

			default:

				if ( header[ off_RGBBitCount ] === 32
					&& header[ off_RBitMask ] & 0xff0000
					&& header[ off_GBitMask ] & 0xff00
					&& header[ off_BBitMask ] & 0xff
					&& header[ off_ABitMask ] & 0xff000000 ) {

					isRGBAUncompressed = true;
					blockBytes = 64;
					dds.format = RGBAFormat;

				} else if ( header[ off_RGBBitCount ] === 24
					&& header[ off_RBitMask ] & 0xff0000
					&& header[ off_GBitMask ] & 0xff00
					&& header[ off_BBitMask ] & 0xff ) {

				    	isRGBUncompressed = true;
                    			blockBytes = 64;
                    			dds.format = RGBAFormat;

				} else {

					console.error( 'THREE.DDSLoader.parse: Unsupported FourCC code ', int32ToFourCC( fourCC ) );
					return dds;

				}

		}

		dds.mipmapCount = 1;

		if ( header[ off_flags ] & DDSD_MIPMAPCOUNT && loadMipmaps !== false ) {

			dds.mipmapCount = Math.max( 1, header[ off_mipmapCount ] );

		}

		const caps2 = header[ off_caps2 ];
		dds.isCubemap = caps2 & DDSCAPS2_CUBEMAP ? true : false;
		if ( dds.isCubemap && (
			! ( caps2 & DDSCAPS2_CUBEMAP_POSITIVEX ) ||
			! ( caps2 & DDSCAPS2_CUBEMAP_NEGATIVEX ) ||
			! ( caps2 & DDSCAPS2_CUBEMAP_POSITIVEY ) ||
			! ( caps2 & DDSCAPS2_CUBEMAP_NEGATIVEY ) ||
			! ( caps2 & DDSCAPS2_CUBEMAP_POSITIVEZ ) ||
			! ( caps2 & DDSCAPS2_CUBEMAP_NEGATIVEZ )
		) ) {

			console.error( 'THREE.DDSLoader.parse: Incomplete cubemap faces' );
			return dds;

		}

		dds.width = header[ off_width ];
		dds.height = header[ off_height ];

		// Extract mipmaps buffers

		const faces = dds.isCubemap ? 6 : 1;

		for ( let face = 0; face < faces; face ++ ) {

			let width = dds.width;
			let height = dds.height;

			for ( let i = 0; i < dds.mipmapCount; i ++ ) {

				let byteArray, dataLength;

				if ( isRGBAUncompressed ) {

					byteArray = loadARGBMip( buffer, dataOffset, width, height );
					dataLength = byteArray.length;

				} else if ( isRGBUncompressed ) {

					byteArray = loadRGBMip( buffer, dataOffset, width, height );
					dataLength = width * height * 3;

				} else {

					dataLength = Math.max( 4, width ) / 4 * Math.max( 4, height ) / 4 * blockBytes;
					byteArray = new Uint8Array( buffer, dataOffset, dataLength );

				}

				const mipmap = { 'data': byteArray, 'width': width, 'height': height };
				dds.mipmaps.push( mipmap );

				dataOffset += dataLength;

				width = Math.max( width >> 1, 1 );
				height = Math.max( height >> 1, 1 );

			}

		}

		return dds;

	}

}
```
</details>

#### Methods

##### `parse(buffer: ArrayBuffer, loadMipmaps: boolean): CompressedTextureLoader`

<details><summary>Code</summary>

```ts
parse( buffer, loadMipmaps ) {

		const dds = { mipmaps: [], width: 0, height: 0, format: null, mipmapCount: 1 };

		// Adapted from @toji's DDS utils
		// https://github.com/toji/webgl-texture-utils/blob/master/texture-util/dds.js

		// All values and structures referenced from:
		// http://msdn.microsoft.com/en-us/library/bb943991.aspx/

		const DDS_MAGIC = 0x20534444;

		// const DDSD_CAPS = 0x1;
		// const DDSD_HEIGHT = 0x2;
		// const DDSD_WIDTH = 0x4;
		// const DDSD_PITCH = 0x8;
		// const DDSD_PIXELFORMAT = 0x1000;
		const DDSD_MIPMAPCOUNT = 0x20000;
		// const DDSD_LINEARSIZE = 0x80000;
		// const DDSD_DEPTH = 0x800000;

		// const DDSCAPS_COMPLEX = 0x8;
		// const DDSCAPS_MIPMAP = 0x400000;
		// const DDSCAPS_TEXTURE = 0x1000;

		const DDSCAPS2_CUBEMAP = 0x200;
		const DDSCAPS2_CUBEMAP_POSITIVEX = 0x400;
		const DDSCAPS2_CUBEMAP_NEGATIVEX = 0x800;
		const DDSCAPS2_CUBEMAP_POSITIVEY = 0x1000;
		const DDSCAPS2_CUBEMAP_NEGATIVEY = 0x2000;
		const DDSCAPS2_CUBEMAP_POSITIVEZ = 0x4000;
		const DDSCAPS2_CUBEMAP_NEGATIVEZ = 0x8000;
		// const DDSCAPS2_VOLUME = 0x200000;

		// const DDPF_ALPHAPIXELS = 0x1;
		// const DDPF_ALPHA = 0x2;
		// const DDPF_FOURCC = 0x4;
		// const DDPF_RGB = 0x40;
		// const DDPF_YUV = 0x200;
		// const DDPF_LUMINANCE = 0x20000;

		const DXGI_FORMAT_BC6H_UF16 = 95;
		const DXGI_FORMAT_BC6H_SF16 = 96;

		function fourCCToInt32( value ) {

			return value.charCodeAt( 0 ) +
				( value.charCodeAt( 1 ) << 8 ) +
				( value.charCodeAt( 2 ) << 16 ) +
				( value.charCodeAt( 3 ) << 24 );

		}

		function int32ToFourCC( value ) {

			return String.fromCharCode(
				value & 0xff,
				( value >> 8 ) & 0xff,
				( value >> 16 ) & 0xff,
				( value >> 24 ) & 0xff
			);

		}

		function loadARGBMip( buffer, dataOffset, width, height ) {

			const dataLength = width * height * 4;
			const srcBuffer = new Uint8Array( buffer, dataOffset, dataLength );
			const byteArray = new Uint8Array( dataLength );
			let dst = 0;
			let src = 0;
			for ( let y = 0; y < height; y ++ ) {

				for ( let x = 0; x < width; x ++ ) {

					const b = srcBuffer[ src ]; src ++;
					const g = srcBuffer[ src ]; src ++;
					const r = srcBuffer[ src ]; src ++;
					const a = srcBuffer[ src ]; src ++;
					byteArray[ dst ] = r; dst ++;	//r
					byteArray[ dst ] = g; dst ++;	//g
					byteArray[ dst ] = b; dst ++;	//b
					byteArray[ dst ] = a; dst ++;	//a

				}

			}

			return byteArray;

		}

		function loadRGBMip( buffer, dataOffset, width, height ) {

			const dataLength = width * height * 3;
			const srcBuffer = new Uint8Array( buffer, dataOffset, dataLength );
			const byteArray = new Uint8Array( width * height * 4 );
			let dst = 0;
			let src = 0;
			for ( let y = 0; y < height; y ++ ) {

				for ( let x = 0; x < width; x ++ ) {

					const b = srcBuffer[ src ]; src ++;
					const g = srcBuffer[ src ]; src ++;
					const r = srcBuffer[ src ]; src ++;
					byteArray[ dst ] = r; dst ++;	//r
					byteArray[ dst ] = g; dst ++;	//g
					byteArray[ dst ] = b; dst ++;	//b
					byteArray[ dst ] = 255; dst ++; //a

				}

			}

			return byteArray;

		}

		const FOURCC_DXT1 = fourCCToInt32( 'DXT1' );
		const FOURCC_DXT3 = fourCCToInt32( 'DXT3' );
		const FOURCC_DXT5 = fourCCToInt32( 'DXT5' );
		const FOURCC_ETC1 = fourCCToInt32( 'ETC1' );
		const FOURCC_DX10 = fourCCToInt32( 'DX10' );

		const headerLengthInt = 31; // The header length in 32 bit ints
		const extendedHeaderLengthInt = 5; // The extended header length in 32 bit ints

		// Offsets into the header array

		const off_magic = 0;

		const off_size = 1;
		const off_flags = 2;
		const off_height = 3;
		const off_width = 4;

		const off_mipmapCount = 7;

		// const off_pfFlags = 20;
		const off_pfFourCC = 21;
		const off_RGBBitCount = 22;
		const off_RBitMask = 23;
		const off_GBitMask = 24;
		const off_BBitMask = 25;
		const off_ABitMask = 26;

		// const off_caps = 27;
		const off_caps2 = 28;
		// const off_caps3 = 29;
		// const off_caps4 = 30;

		// If fourCC = DX10, the extended header starts after 32
		const off_dxgiFormat = 0;

		// Parse header

		const header = new Int32Array( buffer, 0, headerLengthInt );

		if ( header[ off_magic ] !== DDS_MAGIC ) {

			console.error( 'THREE.DDSLoader.parse: Invalid magic number in DDS header.' );
			return dds;

		}

		let blockBytes;

		const fourCC = header[ off_pfFourCC ];

		let isRGBAUncompressed = false;
		let isRGBUncompressed = false;

		let dataOffset = header[ off_size ] + 4;

		switch ( fourCC ) {

			case FOURCC_DXT1:

				blockBytes = 8;
				dds.format = RGB_S3TC_DXT1_Format;
				break;

			case FOURCC_DXT3:

				blockBytes = 16;
				dds.format = RGBA_S3TC_DXT3_Format;
				break;

			case FOURCC_DXT5:

				blockBytes = 16;
				dds.format = RGBA_S3TC_DXT5_Format;
				break;

			case FOURCC_ETC1:

				blockBytes = 8;
				dds.format = RGB_ETC1_Format;
				break;

			case FOURCC_DX10:

				dataOffset += extendedHeaderLengthInt * 4;
				const extendedHeader = new Int32Array( buffer, ( headerLengthInt + 1 ) * 4, extendedHeaderLengthInt );
				const dxgiFormat = extendedHeader[ off_dxgiFormat ];
				switch ( dxgiFormat ) {

					case DXGI_FORMAT_BC6H_SF16: {

						blockBytes = 16;
						dds.format = RGB_BPTC_SIGNED_Format;
						break;

					}

					case DXGI_FORMAT_BC6H_UF16: {

						blockBytes = 16;
						dds.format = RGB_BPTC_UNSIGNED_Format;
						break;

					}

					default: {

						console.error( 'THREE.DDSLoader.parse: Unsupported DXGI_FORMAT code ', dxgiFormat );
						return dds;

					}

				}

				break;

			default:

				if ( header[ off_RGBBitCount ] === 32
					&& header[ off_RBitMask ] & 0xff0000
					&& header[ off_GBitMask ] & 0xff00
					&& header[ off_BBitMask ] & 0xff
					&& header[ off_ABitMask ] & 0xff000000 ) {

					isRGBAUncompressed = true;
					blockBytes = 64;
					dds.format = RGBAFormat;

				} else if ( header[ off_RGBBitCount ] === 24
					&& header[ off_RBitMask ] & 0xff0000
					&& header[ off_GBitMask ] & 0xff00
					&& header[ off_BBitMask ] & 0xff ) {

				    	isRGBUncompressed = true;
                    			blockBytes = 64;
                    			dds.format = RGBAFormat;

				} else {

					console.error( 'THREE.DDSLoader.parse: Unsupported FourCC code ', int32ToFourCC( fourCC ) );
					return dds;

				}

		}

		dds.mipmapCount = 1;

		if ( header[ off_flags ] & DDSD_MIPMAPCOUNT && loadMipmaps !== false ) {

			dds.mipmapCount = Math.max( 1, header[ off_mipmapCount ] );

		}

		const caps2 = header[ off_caps2 ];
		dds.isCubemap = caps2 & DDSCAPS2_CUBEMAP ? true : false;
		if ( dds.isCubemap && (
			! ( caps2 & DDSCAPS2_CUBEMAP_POSITIVEX ) ||
			! ( caps2 & DDSCAPS2_CUBEMAP_NEGATIVEX ) ||
			! ( caps2 & DDSCAPS2_CUBEMAP_POSITIVEY ) ||
			! ( caps2 & DDSCAPS2_CUBEMAP_NEGATIVEY ) ||
			! ( caps2 & DDSCAPS2_CUBEMAP_POSITIVEZ ) ||
			! ( caps2 & DDSCAPS2_CUBEMAP_NEGATIVEZ )
		) ) {

			console.error( 'THREE.DDSLoader.parse: Incomplete cubemap faces' );
			return dds;

		}

		dds.width = header[ off_width ];
		dds.height = header[ off_height ];

		// Extract mipmaps buffers

		const faces = dds.isCubemap ? 6 : 1;

		for ( let face = 0; face < faces; face ++ ) {

			let width = dds.width;
			let height = dds.height;

			for ( let i = 0; i < dds.mipmapCount; i ++ ) {

				let byteArray, dataLength;

				if ( isRGBAUncompressed ) {

					byteArray = loadARGBMip( buffer, dataOffset, width, height );
					dataLength = byteArray.length;

				} else if ( isRGBUncompressed ) {

					byteArray = loadRGBMip( buffer, dataOffset, width, height );
					dataLength = width * height * 3;

				} else {

					dataLength = Math.max( 4, width ) / 4 * Math.max( 4, height ) / 4 * blockBytes;
					byteArray = new Uint8Array( buffer, dataOffset, dataLength );

				}

				const mipmap = { 'data': byteArray, 'width': width, 'height': height };
				dds.mipmaps.push( mipmap );

				dataOffset += dataLength;

				width = Math.max( width >> 1, 1 );
				height = Math.max( height >> 1, 1 );

			}

		}

		return dds;

	}
```
</details>


---