[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `KTX2Exporter.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 41 |
| 📊 Variables & Constants | 14 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/exporters/KTX2Exporter.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ColorManagement` | `three` |
| `FloatType` | `three` |
| `HalfFloatType` | `three` |
| `UnsignedByteType` | `three` |
| `RGBAFormat` | `three` |
| `RGFormat` | `three` |
| `RGIntegerFormat` | `three` |
| `RedFormat` | `three` |
| `RedIntegerFormat` | `three` |
| `NoColorSpace` | `three` |
| `LinearSRGBColorSpace` | `three` |
| `SRGBColorSpace` | `three` |
| `SRGBTransfer` | `three` |
| `DataTexture` | `three` |
| `REVISION` | `three` |
| `write` | `../libs/ktx-parse.module.js` |
| `KTX2Container` | `../libs/ktx-parse.module.js` |
| `KHR_DF_CHANNEL_RGBSDA_ALPHA` | `../libs/ktx-parse.module.js` |
| `KHR_DF_CHANNEL_RGBSDA_BLUE` | `../libs/ktx-parse.module.js` |
| `KHR_DF_CHANNEL_RGBSDA_GREEN` | `../libs/ktx-parse.module.js` |
| `KHR_DF_CHANNEL_RGBSDA_RED` | `../libs/ktx-parse.module.js` |
| `KHR_DF_MODEL_RGBSDA` | `../libs/ktx-parse.module.js` |
| `KHR_DF_PRIMARIES_BT709` | `../libs/ktx-parse.module.js` |
| `KHR_DF_PRIMARIES_UNSPECIFIED` | `../libs/ktx-parse.module.js` |
| `KHR_DF_SAMPLE_DATATYPE_FLOAT` | `../libs/ktx-parse.module.js` |
| `KHR_DF_SAMPLE_DATATYPE_LINEAR` | `../libs/ktx-parse.module.js` |
| `KHR_DF_SAMPLE_DATATYPE_SIGNED` | `../libs/ktx-parse.module.js` |
| `KHR_DF_TRANSFER_LINEAR` | `../libs/ktx-parse.module.js` |
| `KHR_DF_TRANSFER_SRGB` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R16_SFLOAT` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R16G16_SFLOAT` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R16G16B16A16_SFLOAT` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R32_SFLOAT` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R32G32_SFLOAT` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R32G32B32A32_SFLOAT` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R8_SRGB` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R8_UNORM` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R8G8_SRGB` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R8G8_UNORM` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R8G8B8A8_SRGB` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R8G8B8A8_UNORM` | `../libs/ktx-parse.module.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `VK_FORMAT_MAP` | `{ [x: number]: { [x: number]: { [x: n...` | let/var | `{ [ RGBAFormat ]: { [ FloatType ]: { [ NoColorSpace ]: VK_FORMAT_R32G32B32A32...` | ✗ |
| `KHR_DF_CHANNEL_MAP` | `number[]` | let/var | `[ KHR_DF_CHANNEL_RGBSDA_RED, KHR_DF_CHANNEL_RGBSDA_GREEN, KHR_DF_CHANNEL_RGBS...` | ✗ |
| `KHR_DF_CHANNEL_SAMPLE_LOWER...` | `{ [x: number]: number[]; }` | let/var | `{ [ FloatType ]: [ 0xbf800000, 0x3f800000 ], [ HalfFloatType ]: [ 0xbf800000,...` | ✗ |
| `ERROR_INPUT` | `"THREE.KTX2Exporter: Supported inputs...` | let/var | `'THREE.KTX2Exporter: Supported inputs are DataTexture, Data3DTexture, or WebG...` | ✗ |
| `ERROR_FORMAT` | `"THREE.KTX2Exporter: Supported format...` | let/var | `'THREE.KTX2Exporter: Supported formats are RGBAFormat, RGFormat, or RedFormat.'` | ✗ |
| `ERROR_TYPE` | `"THREE.KTX2Exporter: Supported types ...` | let/var | `'THREE.KTX2Exporter: Supported types are FloatType, HalfFloatType, or Unsigne...` | ✗ |
| `ERROR_COLOR_SPACE` | `"THREE.KTX2Exporter: Supported color ...` | let/var | `'THREE.KTX2Exporter: Supported color spaces are SRGBColorSpace (UnsignedByteT...` | ✗ |
| `texture` | `any` | let/var | `*not shown*` | ✗ |
| `array` | `any` | let/var | `texture.image.data` | ✗ |
| `container` | `Ii` | let/var | `new KTX2Container()` | ✗ |
| `basicDesc` | `{ vendorId: number; descriptorType: n...` | let/var | `container.dataFormatDescriptor[ 0 ]` | ✗ |
| `channelType` | `number` | let/var | `KHR_DF_CHANNEL_MAP[ i ]` | ✗ |
| `view` | `any` | let/var | `*not shown*` | ✗ |
| `texture` | `any` | let/var | `new DataTexture( view, rtt.width, rtt.height, rtt.texture.format, rtt.texture...` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `toDataTexture` | renderer.readRenderTargetPixelsAsync( rtt, 0, 0, rtt.width, rtt.height, view ), renderer.readRenderTargetPixelsAsync( rtt, 0, 0, rtt.width, rtt.height ) | *none* |


---

## Functions

### `KTX2Exporter.parse(arg1: any, arg2: RenderTarget): Promise<Uint8Array<ArrayBufferLike>>`

**JSDoc:**
```typescript
/**
	 * This method has two variants.
	 *
	 * - When exporting a data texture, it receives one parameter. The data or 3D data texture.
	 * - When exporting a render target (e.g. a PMREM), it receives two parameters. The renderer and the
	 * render target.
	 *
	 * @async
	 * @param {(DataTexture|Data3DTexture|WebGPURenderer|WebGLRenderer)} arg1 - The data texture to export or a renderer.
	 * @param {RenderTarget} [arg2] - The render target that should be exported
	 * @return {Promise<Uint8Array>} A Promise that resolves with the exported KTX2.
	 */
```

**Parameters:**

- **`arg1`** `any`
- **`arg2`** `RenderTarget`

**Returns:** `Promise<Uint8Array<ArrayBufferLike>>`

**Calls:**

- `toDataTexture`
- `getChannelCount`
- `ColorManagement.getTransfer`
- `basicDesc.samples.push`
- `write (from ../libs/ktx-parse.module.js)`

**Internal Comments:**
```
// (x14)
// Assign KHR_DF_SAMPLE_DATATYPE_LINEAR if the channel is linear _and_ differs from the transfer function.
```

<details><summary>Code</summary>

```typescript
async parse( arg1, arg2 ) {

		let texture;

		if ( arg1.isDataTexture || arg1.isData3DTexture ) {

			texture = arg1;

		} else if ( ( arg1.isWebGLRenderer || arg1.isWebGPURenderer ) && arg2.isRenderTarget ) {

			texture = await toDataTexture( arg1, arg2 );

		} else {

			throw new Error( ERROR_INPUT );

		}

		if ( VK_FORMAT_MAP[ texture.format ] === undefined ) {

			throw new Error( ERROR_FORMAT );

		}

		if ( VK_FORMAT_MAP[ texture.format ][ texture.type ] === undefined ) {

			throw new Error( ERROR_TYPE );

		}

		if ( VK_FORMAT_MAP[ texture.format ][ texture.type ][ texture.colorSpace ] === undefined ) {

			throw new Error( ERROR_COLOR_SPACE );

		}

		//

		const array = texture.image.data;
		const channelCount = getChannelCount( texture );
		const container = new KTX2Container();

		container.vkFormat = VK_FORMAT_MAP[ texture.format ][ texture.type ][ texture.colorSpace ];
		container.typeSize = array.BYTES_PER_ELEMENT;
		container.pixelWidth = texture.image.width;
		container.pixelHeight = texture.image.height;

		if ( texture.isData3DTexture ) {

			container.pixelDepth = texture.image.depth;

		}

		//

		const basicDesc = container.dataFormatDescriptor[ 0 ];

		basicDesc.colorModel = KHR_DF_MODEL_RGBSDA;
		basicDesc.colorPrimaries = texture.colorSpace === NoColorSpace
			? KHR_DF_PRIMARIES_UNSPECIFIED
			: KHR_DF_PRIMARIES_BT709;
		basicDesc.transferFunction = ColorManagement.getTransfer( texture.colorSpace ) === SRGBTransfer
			? KHR_DF_TRANSFER_SRGB
			: KHR_DF_TRANSFER_LINEAR;

		basicDesc.texelBlockDimension = [ 0, 0, 0, 0 ];

		basicDesc.bytesPlane = [

			container.typeSize * channelCount, 0, 0, 0, 0, 0, 0, 0,

		];

		for ( let i = 0; i < channelCount; ++ i ) {

			let channelType = KHR_DF_CHANNEL_MAP[ i ];

			// Assign KHR_DF_SAMPLE_DATATYPE_LINEAR if the channel is linear _and_ differs from the transfer function.
			if ( channelType === KHR_DF_CHANNEL_RGBSDA_ALPHA && basicDesc.transferFunction !== KHR_DF_TRANSFER_LINEAR ) {

				channelType |= KHR_DF_SAMPLE_DATATYPE_LINEAR;

			}

			if ( texture.type === FloatType || texture.type === HalfFloatType ) {

				channelType |= KHR_DF_SAMPLE_DATATYPE_FLOAT;
				channelType |= KHR_DF_SAMPLE_DATATYPE_SIGNED;

			}

			basicDesc.samples.push( {

				channelType: channelType,
				bitOffset: i * array.BYTES_PER_ELEMENT * 8,
				bitLength: array.BYTES_PER_ELEMENT * 8 - 1,
				samplePosition: [ 0, 0, 0, 0 ],
				sampleLower: KHR_DF_CHANNEL_SAMPLE_LOWER_UPPER[ texture.type ][ 0 ],
				sampleUpper: KHR_DF_CHANNEL_SAMPLE_LOWER_UPPER[ texture.type ][ 1 ],

			} );

		}

		//

		container.levels = [ {

			levelData: new Uint8Array( array.buffer, array.byteOffset, array.byteLength ),
			uncompressedByteLength: array.byteLength,

		} ];

		//

		container.keyValue[ 'KTXwriter' ] = `three.js ${ REVISION }`;

		//

		return write( container, { keepWriter: true } );

	}
```
</details>

### `toDataTexture(renderer: any, rtt: any): Promise<any>`

**Parameters:**

- **`renderer`** `any`
- **`rtt`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `getChannelCount`
- `renderer.readRenderTargetPixelsAsync`

<details><summary>Code</summary>

```typescript
async function toDataTexture( renderer, rtt ) {

	const channelCount = getChannelCount( rtt.texture );

	let view;

	if ( renderer.isWebGLRenderer ) {

		if ( rtt.texture.type === FloatType ) {

			view = new Float32Array( rtt.width * rtt.height * channelCount );

		} else if ( rtt.texture.type === HalfFloatType ) {

			view = new Uint16Array( rtt.width * rtt.height * channelCount );

		} else if ( rtt.texture.type === UnsignedByteType ) {

			view = new Uint8Array( rtt.width * rtt.height * channelCount );

		} else {

			throw new Error( ERROR_TYPE );

		}

		await renderer.readRenderTargetPixelsAsync( rtt, 0, 0, rtt.width, rtt.height, view );

	} else {

		view = await renderer.readRenderTargetPixelsAsync( rtt, 0, 0, rtt.width, rtt.height );

	}

	const texture = new DataTexture( view, rtt.width, rtt.height, rtt.texture.format, rtt.texture.type );

	texture.colorSpace = rtt.texture.colorSpace;

	return texture;

}
```
</details>

### `getChannelCount(texture: any): 1 | 2 | 4`

**Parameters:**

- **`texture`** `any`

**Returns:** `1 | 2 | 4`

<details><summary>Code</summary>

```typescript
function getChannelCount( texture ) {

	switch ( texture.format ) {

		case RGBAFormat:

			return 4;

		case RGFormat:
		case RGIntegerFormat:

			return 2;

		case RedFormat:
		case RedIntegerFormat:

			return 1;

		default:

			throw new Error( ERROR_FORMAT );

	}

}
```
</details>


---

## Classes

### `KTX2Exporter`

<details><summary>Class Code</summary>

```ts
export class KTX2Exporter {

	/**
	 * This method has two variants.
	 *
	 * - When exporting a data texture, it receives one parameter. The data or 3D data texture.
	 * - When exporting a render target (e.g. a PMREM), it receives two parameters. The renderer and the
	 * render target.
	 *
	 * @async
	 * @param {(DataTexture|Data3DTexture|WebGPURenderer|WebGLRenderer)} arg1 - The data texture to export or a renderer.
	 * @param {RenderTarget} [arg2] - The render target that should be exported
	 * @return {Promise<Uint8Array>} A Promise that resolves with the exported KTX2.
	 */
	async parse( arg1, arg2 ) {

		let texture;

		if ( arg1.isDataTexture || arg1.isData3DTexture ) {

			texture = arg1;

		} else if ( ( arg1.isWebGLRenderer || arg1.isWebGPURenderer ) && arg2.isRenderTarget ) {

			texture = await toDataTexture( arg1, arg2 );

		} else {

			throw new Error( ERROR_INPUT );

		}

		if ( VK_FORMAT_MAP[ texture.format ] === undefined ) {

			throw new Error( ERROR_FORMAT );

		}

		if ( VK_FORMAT_MAP[ texture.format ][ texture.type ] === undefined ) {

			throw new Error( ERROR_TYPE );

		}

		if ( VK_FORMAT_MAP[ texture.format ][ texture.type ][ texture.colorSpace ] === undefined ) {

			throw new Error( ERROR_COLOR_SPACE );

		}

		//

		const array = texture.image.data;
		const channelCount = getChannelCount( texture );
		const container = new KTX2Container();

		container.vkFormat = VK_FORMAT_MAP[ texture.format ][ texture.type ][ texture.colorSpace ];
		container.typeSize = array.BYTES_PER_ELEMENT;
		container.pixelWidth = texture.image.width;
		container.pixelHeight = texture.image.height;

		if ( texture.isData3DTexture ) {

			container.pixelDepth = texture.image.depth;

		}

		//

		const basicDesc = container.dataFormatDescriptor[ 0 ];

		basicDesc.colorModel = KHR_DF_MODEL_RGBSDA;
		basicDesc.colorPrimaries = texture.colorSpace === NoColorSpace
			? KHR_DF_PRIMARIES_UNSPECIFIED
			: KHR_DF_PRIMARIES_BT709;
		basicDesc.transferFunction = ColorManagement.getTransfer( texture.colorSpace ) === SRGBTransfer
			? KHR_DF_TRANSFER_SRGB
			: KHR_DF_TRANSFER_LINEAR;

		basicDesc.texelBlockDimension = [ 0, 0, 0, 0 ];

		basicDesc.bytesPlane = [

			container.typeSize * channelCount, 0, 0, 0, 0, 0, 0, 0,

		];

		for ( let i = 0; i < channelCount; ++ i ) {

			let channelType = KHR_DF_CHANNEL_MAP[ i ];

			// Assign KHR_DF_SAMPLE_DATATYPE_LINEAR if the channel is linear _and_ differs from the transfer function.
			if ( channelType === KHR_DF_CHANNEL_RGBSDA_ALPHA && basicDesc.transferFunction !== KHR_DF_TRANSFER_LINEAR ) {

				channelType |= KHR_DF_SAMPLE_DATATYPE_LINEAR;

			}

			if ( texture.type === FloatType || texture.type === HalfFloatType ) {

				channelType |= KHR_DF_SAMPLE_DATATYPE_FLOAT;
				channelType |= KHR_DF_SAMPLE_DATATYPE_SIGNED;

			}

			basicDesc.samples.push( {

				channelType: channelType,
				bitOffset: i * array.BYTES_PER_ELEMENT * 8,
				bitLength: array.BYTES_PER_ELEMENT * 8 - 1,
				samplePosition: [ 0, 0, 0, 0 ],
				sampleLower: KHR_DF_CHANNEL_SAMPLE_LOWER_UPPER[ texture.type ][ 0 ],
				sampleUpper: KHR_DF_CHANNEL_SAMPLE_LOWER_UPPER[ texture.type ][ 1 ],

			} );

		}

		//

		container.levels = [ {

			levelData: new Uint8Array( array.buffer, array.byteOffset, array.byteLength ),
			uncompressedByteLength: array.byteLength,

		} ];

		//

		container.keyValue[ 'KTXwriter' ] = `three.js ${ REVISION }`;

		//

		return write( container, { keepWriter: true } );

	}

}
```
</details>

#### Methods

##### `parse(arg1: any, arg2: RenderTarget): Promise<Uint8Array<ArrayBufferLike>>`

<details><summary>Code</summary>

```ts
async parse( arg1, arg2 ) {

		let texture;

		if ( arg1.isDataTexture || arg1.isData3DTexture ) {

			texture = arg1;

		} else if ( ( arg1.isWebGLRenderer || arg1.isWebGPURenderer ) && arg2.isRenderTarget ) {

			texture = await toDataTexture( arg1, arg2 );

		} else {

			throw new Error( ERROR_INPUT );

		}

		if ( VK_FORMAT_MAP[ texture.format ] === undefined ) {

			throw new Error( ERROR_FORMAT );

		}

		if ( VK_FORMAT_MAP[ texture.format ][ texture.type ] === undefined ) {

			throw new Error( ERROR_TYPE );

		}

		if ( VK_FORMAT_MAP[ texture.format ][ texture.type ][ texture.colorSpace ] === undefined ) {

			throw new Error( ERROR_COLOR_SPACE );

		}

		//

		const array = texture.image.data;
		const channelCount = getChannelCount( texture );
		const container = new KTX2Container();

		container.vkFormat = VK_FORMAT_MAP[ texture.format ][ texture.type ][ texture.colorSpace ];
		container.typeSize = array.BYTES_PER_ELEMENT;
		container.pixelWidth = texture.image.width;
		container.pixelHeight = texture.image.height;

		if ( texture.isData3DTexture ) {

			container.pixelDepth = texture.image.depth;

		}

		//

		const basicDesc = container.dataFormatDescriptor[ 0 ];

		basicDesc.colorModel = KHR_DF_MODEL_RGBSDA;
		basicDesc.colorPrimaries = texture.colorSpace === NoColorSpace
			? KHR_DF_PRIMARIES_UNSPECIFIED
			: KHR_DF_PRIMARIES_BT709;
		basicDesc.transferFunction = ColorManagement.getTransfer( texture.colorSpace ) === SRGBTransfer
			? KHR_DF_TRANSFER_SRGB
			: KHR_DF_TRANSFER_LINEAR;

		basicDesc.texelBlockDimension = [ 0, 0, 0, 0 ];

		basicDesc.bytesPlane = [

			container.typeSize * channelCount, 0, 0, 0, 0, 0, 0, 0,

		];

		for ( let i = 0; i < channelCount; ++ i ) {

			let channelType = KHR_DF_CHANNEL_MAP[ i ];

			// Assign KHR_DF_SAMPLE_DATATYPE_LINEAR if the channel is linear _and_ differs from the transfer function.
			if ( channelType === KHR_DF_CHANNEL_RGBSDA_ALPHA && basicDesc.transferFunction !== KHR_DF_TRANSFER_LINEAR ) {

				channelType |= KHR_DF_SAMPLE_DATATYPE_LINEAR;

			}

			if ( texture.type === FloatType || texture.type === HalfFloatType ) {

				channelType |= KHR_DF_SAMPLE_DATATYPE_FLOAT;
				channelType |= KHR_DF_SAMPLE_DATATYPE_SIGNED;

			}

			basicDesc.samples.push( {

				channelType: channelType,
				bitOffset: i * array.BYTES_PER_ELEMENT * 8,
				bitLength: array.BYTES_PER_ELEMENT * 8 - 1,
				samplePosition: [ 0, 0, 0, 0 ],
				sampleLower: KHR_DF_CHANNEL_SAMPLE_LOWER_UPPER[ texture.type ][ 0 ],
				sampleUpper: KHR_DF_CHANNEL_SAMPLE_LOWER_UPPER[ texture.type ][ 1 ],

			} );

		}

		//

		container.levels = [ {

			levelData: new Uint8Array( array.buffer, array.byteOffset, array.byteLength ),
			uncompressedByteLength: array.byteLength,

		} ];

		//

		container.keyValue[ 'KTXwriter' ] = `three.js ${ REVISION }`;

		//

		return write( container, { keepWriter: true } );

	}
```
</details>


---