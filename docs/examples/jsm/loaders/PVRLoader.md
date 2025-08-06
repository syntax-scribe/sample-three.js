[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PVRLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 43 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/PVRLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `CompressedTextureLoader` | `three` |
| `RGBA_PVRTC_2BPPV1_Format` | `three` |
| `RGBA_PVRTC_4BPPV1_Format` | `three` |
| `RGB_PVRTC_2BPPV1_Format` | `three` |
| `RGB_PVRTC_4BPPV1_Format` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `headerLengthInt` | `13` | let/var | `13` | ✗ |
| `header` | `Uint32Array<ArrayBuffer>` | let/var | `new Uint32Array( buffer, 0, headerLengthInt )` | ✗ |
| `pvrDatas` | `{ buffer: ArrayBuffer; header: Uint32...` | let/var | `{ buffer: buffer, header: header, loadMipmaps: loadMipmaps }` | ✗ |
| `header` | `any` | let/var | `pvrDatas.header` | ✗ |
| `bpp` | `any` | let/var | `*not shown*` | ✗ |
| `format` | `any` | let/var | `*not shown*` | ✗ |
| `metaLen` | `any` | let/var | `header[ 12 ]` | ✗ |
| `pixelFormat` | `any` | let/var | `header[ 2 ]` | ✗ |
| `height` | `any` | let/var | `header[ 6 ]` | ✗ |
| `width` | `any` | let/var | `header[ 7 ]` | ✗ |
| `numFaces` | `any` | let/var | `header[ 10 ]` | ✗ |
| `numMipmaps` | `any` | let/var | `header[ 11 ]` | ✗ |
| `header` | `any` | let/var | `pvrDatas.header` | ✗ |
| `headerLength` | `any` | let/var | `header[ 0 ]` | ✗ |
| `height` | `any` | let/var | `header[ 1 ]` | ✗ |
| `width` | `any` | let/var | `header[ 2 ]` | ✗ |
| `numMipmaps` | `any` | let/var | `header[ 3 ]` | ✗ |
| `flags` | `any` | let/var | `header[ 4 ]` | ✗ |
| `bitmaskAlpha` | `any` | let/var | `header[ 10 ]` | ✗ |
| `numSurfs` | `any` | let/var | `header[ 12 ]` | ✗ |
| `TYPE_MASK` | `255` | let/var | `0xff` | ✗ |
| `PVRTC_2` | `24` | let/var | `24` | ✗ |
| `PVRTC_4` | `25` | let/var | `25` | ✗ |
| `formatFlags` | `number` | let/var | `flags & TYPE_MASK` | ✗ |
| `bpp` | `any` | let/var | `*not shown*` | ✗ |
| `format` | `any` | let/var | `*not shown*` | ✗ |
| `_hasAlpha` | `boolean` | let/var | `bitmaskAlpha > 0` | ✗ |
| `pvr` | `{ mipmaps: any[]; width: any; height:...` | let/var | `{ mipmaps: [], width: pvrDatas.width, height: pvrDatas.height, format: pvrDat...` | ✗ |
| `buffer` | `any` | let/var | `pvrDatas.buffer` | ✗ |
| `dataOffset` | `any` | let/var | `pvrDatas.dataPtr` | ✗ |
| `dataSize` | `number` | let/var | `0` | ✗ |
| `blockSize` | `number` | let/var | `0` | ✗ |
| `blockWidth` | `number` | let/var | `0` | ✗ |
| `blockHeight` | `number` | let/var | `0` | ✗ |
| `widthBlocks` | `number` | let/var | `0` | ✗ |
| `heightBlocks` | `number` | let/var | `0` | ✗ |
| `bpp` | `any` | let/var | `pvrDatas.bpp` | ✗ |
| `numSurfs` | `any` | let/var | `pvrDatas.numSurfaces` | ✗ |
| `mipLevel` | `number` | let/var | `0` | ✗ |
| `sWidth` | `number` | let/var | `pvrDatas.width >> mipLevel` | ✗ |
| `sHeight` | `number` | let/var | `pvrDatas.height >> mipLevel` | ✗ |
| `byteArray` | `Uint8Array<any>` | let/var | `new Uint8Array( buffer, dataOffset, dataSize )` | ✗ |
| `mipmap` | `{ data: Uint8Array<any>; width: numbe...` | let/var | `{ data: byteArray, width: sWidth, height: sHeight }` | ✗ |


---

## Functions

### `PVRLoader.parse(buffer: ArrayBuffer, loadMipmaps: boolean): CompressedTextureLoader`

**JSDoc:**
```typescript
/**
	 * Parses the given PVRTC texture data.
	 *
	 * @param {ArrayBuffer} buffer - The raw texture data.
	 * @param {boolean} loadMipmaps - Whether to load mipmaps or not. This option is not yet supported by the loader.
	 * @return {CompressedTextureLoader~TexData} An object representing the parsed texture data.
	 */
```

**Parameters:**

- **`buffer`** `ArrayBuffer`
- **`loadMipmaps`** `boolean`

**Returns:** `CompressedTextureLoader`

**Calls:**

- `_parseV3`
- `_parseV2`
- `console.error`

**Internal Comments:**
```
// PVR v3
// PVR v2
```

<details><summary>Code</summary>

```typescript
parse( buffer, loadMipmaps ) {

		const headerLengthInt = 13;
		const header = new Uint32Array( buffer, 0, headerLengthInt );

		const pvrDatas = {
			buffer: buffer,
			header: header,
			loadMipmaps: loadMipmaps
		};

		if ( header[ 0 ] === 0x03525650 ) {

			// PVR v3

			return _parseV3( pvrDatas );

		} else if ( header[ 11 ] === 0x21525650 ) {

			// PVR v2

			return _parseV2( pvrDatas );

		} else {

			console.error( 'THREE.PVRLoader: Unknown PVR format.' );

		}

	}
```
</details>

### `_parseV3(pvrDatas: any): { mipmaps: any[]; width: any; height: any; format: any; mipmapCount: any; isCubemap: any; }`

**Parameters:**

- **`pvrDatas`** `any`

**Returns:** `{ mipmaps: any[]; width: any; height: any; format: any; mipmapCount: any; isCubemap: any; }`

**Calls:**

- `console.error`
- `_extract`

**Internal Comments:**
```
// numSurfs = header[ 9 ], (x2)
```

<details><summary>Code</summary>

```typescript
function _parseV3( pvrDatas ) {

	const header = pvrDatas.header;
	let bpp, format;


	const metaLen = header[ 12 ],
		pixelFormat = header[ 2 ],
		height = header[ 6 ],
		width = header[ 7 ],
		// numSurfs = header[ 9 ],
		numFaces = header[ 10 ],
		numMipmaps = header[ 11 ];

	switch ( pixelFormat ) {

		case 0 : // PVRTC 2bpp RGB
			bpp = 2;
			format = RGB_PVRTC_2BPPV1_Format;
			break;

		case 1 : // PVRTC 2bpp RGBA
			bpp = 2;
			format = RGBA_PVRTC_2BPPV1_Format;
			break;

		case 2 : // PVRTC 4bpp RGB
			bpp = 4;
			format = RGB_PVRTC_4BPPV1_Format;
			break;

		case 3 : // PVRTC 4bpp RGBA
			bpp = 4;
			format = RGBA_PVRTC_4BPPV1_Format;
			break;

		default :
			console.error( 'THREE.PVRLoader: Unsupported PVR format:', pixelFormat );

	}

	pvrDatas.dataPtr = 52 + metaLen;
	pvrDatas.bpp = bpp;
	pvrDatas.format = format;
	pvrDatas.width = width;
	pvrDatas.height = height;
	pvrDatas.numSurfaces = numFaces;
	pvrDatas.numMipmaps = numMipmaps;
	pvrDatas.isCubemap 	= ( numFaces === 6 );

	return _extract( pvrDatas );

}
```
</details>

### `_parseV2(pvrDatas: any): { mipmaps: any[]; width: any; height: any; format: any; mipmapCount: any; isCubemap: any; }`

**Parameters:**

- **`pvrDatas`** `any`

**Returns:** `{ mipmaps: any[]; width: any; height: any; format: any; mipmapCount: any; isCubemap: any; }`

**Calls:**

- `console.error`
- `_extract`

**Internal Comments:**
```
// dataLength = header[ 5 ], (x2)
// bpp =  header[ 6 ], (x2)
// bitmaskRed = header[ 7 ], (x2)
// bitmaskGreen = header[ 8 ], (x2)
// bitmaskBlue = header[ 9 ], (x2)
// pvrTag = header[ 11 ], (x2)
// guess cubemap type seems tricky in v2 (x4)
// it's just a pvr containing 6 surface (no explicit cubemap type) (x4)
```

<details><summary>Code</summary>

```typescript
function _parseV2( pvrDatas ) {

	const header = pvrDatas.header;

	const headerLength = header[ 0 ],
		height = header[ 1 ],
		width = header[ 2 ],
		numMipmaps = header[ 3 ],
		flags = header[ 4 ],
		// dataLength = header[ 5 ],
		// bpp =  header[ 6 ],
		// bitmaskRed = header[ 7 ],
		// bitmaskGreen = header[ 8 ],
		// bitmaskBlue = header[ 9 ],
		bitmaskAlpha = header[ 10 ],
		// pvrTag = header[ 11 ],
		numSurfs = header[ 12 ];


	const TYPE_MASK = 0xff;
	const PVRTC_2 = 24,
		PVRTC_4 = 25;

	const formatFlags = flags & TYPE_MASK;

	let bpp, format;
	const _hasAlpha = bitmaskAlpha > 0;

	if ( formatFlags === PVRTC_4 ) {

		format = _hasAlpha ? RGBA_PVRTC_4BPPV1_Format : RGB_PVRTC_4BPPV1_Format;
		bpp = 4;

	} else if ( formatFlags === PVRTC_2 ) {

		format = _hasAlpha ? RGBA_PVRTC_2BPPV1_Format : RGB_PVRTC_2BPPV1_Format;
		bpp = 2;

	} else {

		console.error( 'THREE.PVRLoader: Unknown PVR format:', formatFlags );

	}

	pvrDatas.dataPtr = headerLength;
	pvrDatas.bpp = bpp;
	pvrDatas.format = format;
	pvrDatas.width = width;
	pvrDatas.height = height;
	pvrDatas.numSurfaces = numSurfs;
	pvrDatas.numMipmaps = numMipmaps + 1;

	// guess cubemap type seems tricky in v2
	// it's just a pvr containing 6 surface (no explicit cubemap type)
	pvrDatas.isCubemap 	= ( numSurfs === 6 );

	return _extract( pvrDatas );

}
```
</details>

### `_extract(pvrDatas: any): { mipmaps: any[]; width: any; height: any; format: any; mipmapCount: any; isCubemap: any; }`

**Parameters:**

- **`pvrDatas`** `any`

**Returns:** `{ mipmaps: any[]; width: any; height: any; format: any; mipmapCount: any; isCubemap: any; }`

**Internal Comments:**
```
// Clamp to minimum number of blocks
```

<details><summary>Code</summary>

```typescript
function _extract( pvrDatas ) {

	const pvr = {
		mipmaps: [],
		width: pvrDatas.width,
		height: pvrDatas.height,
		format: pvrDatas.format,
		mipmapCount: pvrDatas.numMipmaps,
		isCubemap: pvrDatas.isCubemap
	};

	const buffer = pvrDatas.buffer;

	let dataOffset = pvrDatas.dataPtr,
		dataSize = 0,
		blockSize = 0,
		blockWidth = 0,
		blockHeight = 0,
		widthBlocks = 0,
		heightBlocks = 0;

	const bpp = pvrDatas.bpp,
		numSurfs = pvrDatas.numSurfaces;

	if ( bpp === 2 ) {

		blockWidth = 8;
		blockHeight = 4;

	} else {

		blockWidth = 4;
		blockHeight = 4;

	}

	blockSize = ( blockWidth * blockHeight ) * bpp / 8;

	pvr.mipmaps.length = pvrDatas.numMipmaps * numSurfs;

	let mipLevel = 0;

	while ( mipLevel < pvrDatas.numMipmaps ) {

		const sWidth = pvrDatas.width >> mipLevel,
			sHeight = pvrDatas.height >> mipLevel;

		widthBlocks = sWidth / blockWidth;
		heightBlocks = sHeight / blockHeight;

		// Clamp to minimum number of blocks
		if ( widthBlocks < 2 ) widthBlocks = 2;
		if ( heightBlocks < 2 ) heightBlocks = 2;

		dataSize = widthBlocks * heightBlocks * blockSize;

		for ( let surfIndex = 0; surfIndex < numSurfs; surfIndex ++ ) {

			const byteArray = new Uint8Array( buffer, dataOffset, dataSize );

			const mipmap = {
				data: byteArray,
				width: sWidth,
				height: sHeight
			};

			pvr.mipmaps[ surfIndex * pvrDatas.numMipmaps + mipLevel ] = mipmap;

			dataOffset += dataSize;

		}

		mipLevel ++;

	}

	return pvr;

}
```
</details>


---

## Classes

### `PVRLoader`

<details><summary>Class Code</summary>

```ts
class PVRLoader extends CompressedTextureLoader {

	/**
	 * Constructs a new PVR loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Parses the given PVRTC texture data.
	 *
	 * @param {ArrayBuffer} buffer - The raw texture data.
	 * @param {boolean} loadMipmaps - Whether to load mipmaps or not. This option is not yet supported by the loader.
	 * @return {CompressedTextureLoader~TexData} An object representing the parsed texture data.
	 */
	parse( buffer, loadMipmaps ) {

		const headerLengthInt = 13;
		const header = new Uint32Array( buffer, 0, headerLengthInt );

		const pvrDatas = {
			buffer: buffer,
			header: header,
			loadMipmaps: loadMipmaps
		};

		if ( header[ 0 ] === 0x03525650 ) {

			// PVR v3

			return _parseV3( pvrDatas );

		} else if ( header[ 11 ] === 0x21525650 ) {

			// PVR v2

			return _parseV2( pvrDatas );

		} else {

			console.error( 'THREE.PVRLoader: Unknown PVR format.' );

		}

	}

}
```
</details>

#### Methods

##### `parse(buffer: ArrayBuffer, loadMipmaps: boolean): CompressedTextureLoader`

<details><summary>Code</summary>

```ts
parse( buffer, loadMipmaps ) {

		const headerLengthInt = 13;
		const header = new Uint32Array( buffer, 0, headerLengthInt );

		const pvrDatas = {
			buffer: buffer,
			header: header,
			loadMipmaps: loadMipmaps
		};

		if ( header[ 0 ] === 0x03525650 ) {

			// PVR v3

			return _parseV3( pvrDatas );

		} else if ( header[ 11 ] === 0x21525650 ) {

			// PVR v2

			return _parseV2( pvrDatas );

		} else {

			console.error( 'THREE.PVRLoader: Unknown PVR format.' );

		}

	}
```
</details>


---