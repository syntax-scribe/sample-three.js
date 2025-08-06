[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `KTX2Loader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 18 |
| 🧱 Classes | 1 |
| 📦 Imports | 73 |
| 📊 Variables & Constants | 54 |
| ⚡ Async/Await Patterns | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/KTX2Loader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `CompressedArrayTexture` | `three` |
| `CompressedCubeTexture` | `three` |
| `CompressedTexture` | `three` |
| `Data3DTexture` | `three` |
| `DataTexture` | `three` |
| `FileLoader` | `three` |
| `FloatType` | `three` |
| `HalfFloatType` | `three` |
| `LinearFilter` | `three` |
| `LinearMipmapLinearFilter` | `three` |
| `LinearSRGBColorSpace` | `three` |
| `Loader` | `three` |
| `NoColorSpace` | `three` |
| `RGBAFormat` | `three` |
| `RGBA_ASTC_4x4_Format` | `three` |
| `RGBA_ASTC_6x6_Format` | `three` |
| `RGBA_BPTC_Format` | `three` |
| `RGBA_S3TC_DXT3_Format` | `three` |
| `RGBA_ETC2_EAC_Format` | `three` |
| `RGBA_PVRTC_4BPPV1_Format` | `three` |
| `RGBA_S3TC_DXT1_Format` | `three` |
| `RGBA_S3TC_DXT5_Format` | `three` |
| `RGB_BPTC_UNSIGNED_Format` | `three` |
| `RGB_ETC1_Format` | `three` |
| `RGB_ETC2_Format` | `three` |
| `RGB_PVRTC_4BPPV1_Format` | `three` |
| `RGB_S3TC_DXT1_Format` | `three` |
| `RGFormat` | `three` |
| `RedFormat` | `three` |
| `SRGBColorSpace` | `three` |
| `UnsignedByteType` | `three` |
| `WorkerPool` | `../utils/WorkerPool.js` |
| `read` | `../libs/ktx-parse.module.js` |
| `KHR_DF_FLAG_ALPHA_PREMULTIPLIED` | `../libs/ktx-parse.module.js` |
| `KHR_DF_PRIMARIES_BT709` | `../libs/ktx-parse.module.js` |
| `KHR_DF_PRIMARIES_DISPLAYP3` | `../libs/ktx-parse.module.js` |
| `KHR_DF_PRIMARIES_UNSPECIFIED` | `../libs/ktx-parse.module.js` |
| `KHR_DF_TRANSFER_SRGB` | `../libs/ktx-parse.module.js` |
| `KHR_SUPERCOMPRESSION_NONE` | `../libs/ktx-parse.module.js` |
| `KHR_SUPERCOMPRESSION_ZSTD` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_ASTC_4x4_SFLOAT_BLOCK_EXT` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_ASTC_4x4_SRGB_BLOCK` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_ASTC_4x4_UNORM_BLOCK` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_ASTC_6x6_SRGB_BLOCK` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_ASTC_6x6_UNORM_BLOCK` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_BC1_RGBA_SRGB_BLOCK` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_BC1_RGBA_UNORM_BLOCK` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_BC1_RGB_SRGB_BLOCK` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_BC1_RGB_UNORM_BLOCK` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_BC3_SRGB_BLOCK` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_BC3_UNORM_BLOCK` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_BC5_SNORM_BLOCK` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_BC5_UNORM_BLOCK` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_BC7_SRGB_BLOCK` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_BC7_UNORM_BLOCK` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_ETC2_R8G8B8_SRGB_BLOCK` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_ETC2_R8G8B8A8_SRGB_BLOCK` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R16G16B16A16_SFLOAT` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R16G16_SFLOAT` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R16_SFLOAT` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R32G32B32A32_SFLOAT` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R32G32_SFLOAT` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R32_SFLOAT` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R8G8B8A8_SRGB` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R8G8B8A8_UNORM` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R8G8_SRGB` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R8G8_UNORM` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R8_SRGB` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_R8_UNORM` | `../libs/ktx-parse.module.js` |
| `VK_FORMAT_UNDEFINED` | `../libs/ktx-parse.module.js` |
| `ZSTDDecoder` | `../libs/zstddec.module.js` |
| `DisplayP3ColorSpace` | `../math/ColorSpaces.js` |
| `LinearDisplayP3ColorSpace` | `../math/ColorSpaces.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_taskCache` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `_activeLoaders` | `number` | let/var | `0` | ✗ |
| `_zstd` | `any` | let/var | `*not shown*` | ✗ |
| `jsLoader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `binaryLoader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `worker` | `Worker` | let/var | `new Worker( this.workerSourceURL )` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `texture` | `any` | let/var | `*not shown*` | ✗ |
| `mipmaps` | `any` | let/var | `faces[ 0 ].mipmaps` | ✗ |
| `isBasisHDR` | `boolean` | let/var | `container.vkFormat === VK_FORMAT_ASTC_4x4_SFLOAT_BLOCK_EXT && container.dataF...` | ✗ |
| `needsTranscoder` | `boolean` | let/var | `container.vkFormat === VK_FORMAT_UNDEFINED \|\| isBasisHDR && ! this.workerCo...` | ✗ |
| `taskConfig` | `any` | let/var | `config` | ✗ |
| `config` | `any` | let/var | `*not shown*` | ✗ |
| `transcoderPending` | `any` | let/var | `*not shown*` | ✗ |
| `BasisModule` | `any` | let/var | `*not shown*` | ✗ |
| `EngineFormat` | `any` | let/var | `_EngineFormat` | ✗ |
| `EngineType` | `any` | let/var | `_EngineType` | ✗ |
| `TranscoderFormat` | `any` | let/var | `_TranscoderFormat` | ✗ |
| `BasisFormat` | `any` | let/var | `_BasisFormat` | ✗ |
| `message` | `any` | let/var | `e.data` | ✗ |
| `ktx2File` | `any` | let/var | `new BasisModule.KTX2File( new Uint8Array( buffer ) )` | ✗ |
| `basisFormat` | `any` | let/var | `*not shown*` | ✗ |
| `layerCount` | `any` | let/var | `ktx2File.getLayers() \|\| 1` | ✗ |
| `faces` | `any[]` | let/var | `[]` | ✗ |
| `buffers` | `any[]` | let/var | `[]` | ✗ |
| `mipmaps` | `any[]` | let/var | `[]` | ✗ |
| `layerMips` | `any[]` | let/var | `[]` | ✗ |
| `mipWidth` | `any` | let/var | `*not shown*` | ✗ |
| `mipHeight` | `any` | let/var | `*not shown*` | ✗ |
| `dst` | `Uint8Array<any>` | let/var | `new Uint8Array( ktx2File.getImageTranscodedSizeInBytes( mip, layer, 0, transc...` | ✗ |
| `FORMAT_OPTIONS` | `({ if: string; basisFormat: any[]; tr...` | let/var | `[ { if: 'astcSupported', basisFormat: [ BasisFormat.UASTC ], transcoderFormat...` | ✗ |
| `OPTIONS` | `{ [x: number]: ({ if: string; basisFo...` | let/var | `{ // TODO: For ETC1S we intentionally sort by _UASTC_ priority, preserving //...` | ✗ |
| `options` | `({ if: string; basisFormat: any[]; tr...` | let/var | `OPTIONS[ basisFormat ]` | ✗ |
| `opt` | `{ if: string; basisFormat: any[]; tra...` | let/var | `options[ i ]` | ✗ |
| `transcoderFormat` | `any` | let/var | `opt.transcoderFormat[ hasAlpha ? 1 : 0 ]` | ✗ |
| `engineFormat` | `any` | let/var | `opt.engineFormat[ hasAlpha ? 1 : 0 ]` | ✗ |
| `engineType` | `any` | let/var | `opt.engineType[ 0 ]` | ✗ |
| `totalByteLength` | `number` | let/var | `0` | ✗ |
| `array` | `Uint8Array<ArrayBufferLike>` | let/var | `arrays[ i ]` | ✗ |
| `result` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( totalByteLength )` | ✗ |
| `byteOffset` | `number` | let/var | `0` | ✗ |
| `array` | `Uint8Array<ArrayBufferLike>` | let/var | `arrays[ i ]` | ✗ |
| `UNCOMPRESSED_FORMATS` | `Set<any>` | let/var | `new Set( [ RGBAFormat, RGFormat, RedFormat ] )` | ✗ |
| `FORMAT_MAP` | `{ 109: any; 97: any; 37: any; 43: any...` | let/var | `{ [ VK_FORMAT_R32G32B32A32_SFLOAT ]: RGBAFormat, [ VK_FORMAT_R16G16B16A16_SFL...` | ✗ |
| `TYPE_MAP` | `{ 109: any; 97: any; 37: any; 43: any...` | let/var | `{ [ VK_FORMAT_R32G32B32A32_SFLOAT ]: FloatType, [ VK_FORMAT_R16G16B16A16_SFLO...` | ✗ |
| `zstd` | `any` | let/var | `*not shown*` | ✗ |
| `zstd` | `Q` | let/var | `new ZSTDDecoder()` | ✗ |
| `mipmaps` | `any[]` | let/var | `[]` | ✗ |
| `levelDepth` | `number` | let/var | `container.pixelDepth ? Math.max( 1, container.pixelDepth >> levelIndex ) : 0` | ✗ |
| `level` | `any` | let/var | `container.levels[ levelIndex ]` | ✗ |
| `levelData` | `any` | let/var | `*not shown*` | ✗ |
| `data` | `any` | let/var | `*not shown*` | ✗ |
| `texture` | `any` | let/var | `*not shown*` | ✗ |
| `dfd` | `any` | let/var | `container.dataFormatDescriptor[ 0 ]` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| promise-chain | `init` | *none* | new Promise( ( resolve ) => {

			BasisModule = { wasmBinary, onRuntimeInitialized: resolve };
			BASIS( BasisModule ); // eslint-disable-line no-undef

		} ).then, new Promise(...) |
| async-function | `createRawTexture` | zstd.init(), _zstd | new Promise(...), Promise.resolve |


---

## Functions

### `KTX2Loader.setTranscoderPath(path: string): KTX2Loader`

**JSDoc:**
```typescript
/**
	 * Sets the transcoder path.
	 *
	 * The WASM transcoder and JS wrapper are available from the `examples/jsm/libs/basis` directory.
	 *
	 * @param {string} path - The transcoder path to set.
	 * @return {KTX2Loader} A reference to this loader.
	 */
```

**Parameters:**

- **`path`** `string`

**Returns:** `KTX2Loader`

<details><summary>Code</summary>

```typescript
setTranscoderPath( path ) {

		this.transcoderPath = path;

		return this;

	}
```
</details>

### `KTX2Loader.setWorkerLimit(workerLimit: number): KTX2Loader`

**JSDoc:**
```typescript
/**
	 * Sets the maximum number of Web Workers to be allocated by this instance.
	 *
	 * @param {number} workerLimit - The worker limit.
	 * @return {KTX2Loader} A reference to this loader.
	 */
```

**Parameters:**

- **`workerLimit`** `number`

**Returns:** `KTX2Loader`

**Calls:**

- `this.workerPool.setWorkerLimit`

<details><summary>Code</summary>

```typescript
setWorkerLimit( workerLimit ) {

		this.workerPool.setWorkerLimit( workerLimit );

		return this;

	}
```
</details>

### `KTX2Loader.detectSupportAsync(renderer: any): Promise<any>`

**JSDoc:**
```typescript
/**
	 * Async version of {@link KTX2Loader#detectSupport}.
	 *
	 * @async
	 * @param {WebGPURenderer|WebGLRenderer} renderer - The renderer.
	 * @return {Promise} A Promise that resolves when the support has been detected.
	 */
```

**Parameters:**

- **`renderer`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `renderer.hasFeatureAsync`

<details><summary>Code</summary>

```typescript
async detectSupportAsync( renderer ) {

		this.workerConfig = {
			astcSupported: await renderer.hasFeatureAsync( 'texture-compression-astc' ),
			astcHDRSupported: false, // https://github.com/gpuweb/gpuweb/issues/3856
			etc1Supported: await renderer.hasFeatureAsync( 'texture-compression-etc1' ),
			etc2Supported: await renderer.hasFeatureAsync( 'texture-compression-etc2' ),
			dxtSupported: await renderer.hasFeatureAsync( 'texture-compression-bc' ),
			bptcSupported: await renderer.hasFeatureAsync( 'texture-compression-bptc' ),
			pvrtcSupported: await renderer.hasFeatureAsync( 'texture-compression-pvrtc' )
		};

		return this;

	}
```
</details>

### `KTX2Loader.detectSupport(renderer: any): KTX2Loader`

**JSDoc:**
```typescript
/**
	 * Detects hardware support for available compressed texture formats, to determine
	 * the output format for the transcoder. Must be called before loading a texture.
	 *
	 * @param {WebGPURenderer|WebGLRenderer} renderer - The renderer.
	 * @return {KTX2Loader} A reference to this loader.
	 */
```

**Parameters:**

- **`renderer`** `any`

**Returns:** `KTX2Loader`

**Calls:**

- `renderer.hasFeature`
- `renderer.extensions.has`
- `renderer.extensions.get( 'WEBGL_compressed_texture_astc' ).getSupportedProfiles().includes`

<details><summary>Code</summary>

```typescript
detectSupport( renderer ) {

		if ( renderer.isWebGPURenderer === true ) {

			this.workerConfig = {
				astcSupported: renderer.hasFeature( 'texture-compression-astc' ),
				astcHDRSupported: false, // https://github.com/gpuweb/gpuweb/issues/3856
				etc1Supported: renderer.hasFeature( 'texture-compression-etc1' ),
				etc2Supported: renderer.hasFeature( 'texture-compression-etc2' ),
				dxtSupported: renderer.hasFeature( 'texture-compression-bc' ),
				bptcSupported: renderer.hasFeature( 'texture-compression-bptc' ),
				pvrtcSupported: renderer.hasFeature( 'texture-compression-pvrtc' )
			};

		} else {

			this.workerConfig = {
				astcSupported: renderer.extensions.has( 'WEBGL_compressed_texture_astc' ),
				astcHDRSupported: renderer.extensions.has( 'WEBGL_compressed_texture_astc' )
					&& renderer.extensions.get( 'WEBGL_compressed_texture_astc' ).getSupportedProfiles().includes( 'hdr' ),
				etc1Supported: renderer.extensions.has( 'WEBGL_compressed_texture_etc1' ),
				etc2Supported: renderer.extensions.has( 'WEBGL_compressed_texture_etc' ),
				dxtSupported: renderer.extensions.has( 'WEBGL_compressed_texture_s3tc' ),
				bptcSupported: renderer.extensions.has( 'EXT_texture_compression_bptc' ),
				pvrtcSupported: renderer.extensions.has( 'WEBGL_compressed_texture_pvrtc' )
					|| renderer.extensions.has( 'WEBKIT_WEBGL_compressed_texture_pvrtc' )
			};

		}

		return this;

	}
```
</details>

### `KTX2Loader.init(): Promise<void>`

**Returns:** `Promise<void>`

**Calls:**

- `jsLoader.setPath`
- `jsLoader.setWithCredentials`
- `jsLoader.loadAsync`
- `binaryLoader.setPath`
- `binaryLoader.setResponseType`
- `binaryLoader.setWithCredentials`
- `binaryLoader.loadAsync`
- `Promise.all( [ jsContent, binaryContent ] )
				.then`
- `KTX2Loader.BasisWorker.toString`
- `[
						'/* constants */',
						'let _EngineFormat = ' + JSON.stringify( KTX2Loader.EngineFormat ),
						'let _EngineType = ' + JSON.stringify( KTX2Loader.EngineType ),
						'let _TranscoderFormat = ' + JSON.stringify( KTX2Loader.TranscoderFormat ),
						'let _BasisFormat = ' + JSON.stringify( KTX2Loader.BasisFormat ),
						'/* basis_transcoder.js */',
						jsContent,
						'/* worker */',
						fn.substring( fn.indexOf( '{' ) + 1, fn.lastIndexOf( '}' ) )
					].join`
- `JSON.stringify`
- `fn.substring`
- `fn.indexOf`
- `fn.lastIndexOf`
- `URL.createObjectURL`
- `this.workerPool.setWorkerCreator`
- `this.transcoderBinary.slice`
- `worker.postMessage`
- `console.warn`

**Internal Comments:**
```
// Load transcoder wrapper. (x2)
// Load transcoder WASM binary. (x2)
// Each instance loads a transcoder and allocates workers, increasing network and memory cost. (x4)
```

<details><summary>Code</summary>

```typescript
init() {

		if ( ! this.transcoderPending ) {

			// Load transcoder wrapper.
			const jsLoader = new FileLoader( this.manager );
			jsLoader.setPath( this.transcoderPath );
			jsLoader.setWithCredentials( this.withCredentials );
			const jsContent = jsLoader.loadAsync( 'basis_transcoder.js' );

			// Load transcoder WASM binary.
			const binaryLoader = new FileLoader( this.manager );
			binaryLoader.setPath( this.transcoderPath );
			binaryLoader.setResponseType( 'arraybuffer' );
			binaryLoader.setWithCredentials( this.withCredentials );
			const binaryContent = binaryLoader.loadAsync( 'basis_transcoder.wasm' );

			this.transcoderPending = Promise.all( [ jsContent, binaryContent ] )
				.then( ( [ jsContent, binaryContent ] ) => {

					const fn = KTX2Loader.BasisWorker.toString();

					const body = [
						'/* constants */',
						'let _EngineFormat = ' + JSON.stringify( KTX2Loader.EngineFormat ),
						'let _EngineType = ' + JSON.stringify( KTX2Loader.EngineType ),
						'let _TranscoderFormat = ' + JSON.stringify( KTX2Loader.TranscoderFormat ),
						'let _BasisFormat = ' + JSON.stringify( KTX2Loader.BasisFormat ),
						'/* basis_transcoder.js */',
						jsContent,
						'/* worker */',
						fn.substring( fn.indexOf( '{' ) + 1, fn.lastIndexOf( '}' ) )
					].join( '\n' );

					this.workerSourceURL = URL.createObjectURL( new Blob( [ body ] ) );
					this.transcoderBinary = binaryContent;

					this.workerPool.setWorkerCreator( () => {

						const worker = new Worker( this.workerSourceURL );
						const transcoderBinary = this.transcoderBinary.slice( 0 );

						worker.postMessage( { type: 'init', config: this.workerConfig, transcoderBinary }, [ transcoderBinary ] );

						return worker;

					} );

				} );

			if ( _activeLoaders > 0 ) {

				// Each instance loads a transcoder and allocates workers, increasing network and memory cost.

				console.warn(

					'THREE.KTX2Loader: Multiple active KTX2 loaders may cause performance issues.'
					+ ' Use a single KTX2Loader instance, or call .dispose() on old instances.'

				);

			}

			_activeLoaders ++;

		}

		return this.transcoderPending;

	}
```
</details>

### `KTX2Loader.load(url: string, onLoad: (arg0: CompressedTexture) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded KTX2 texture
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(CompressedTexture)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: CompressedTexture) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `loader.setPath`
- `loader.setCrossOrigin`
- `loader.setWithCredentials`
- `loader.setResponseType`
- `loader.load`
- `this.parse`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		if ( this.workerConfig === null ) {

			throw new Error( 'THREE.KTX2Loader: Missing initialization with `.detectSupport( renderer )`.' );

		}

		const loader = new FileLoader( this.manager );

		loader.setPath( this.path );
		loader.setCrossOrigin( this.crossOrigin );
		loader.setWithCredentials( this.withCredentials );
		loader.setResponseType( 'arraybuffer' );

		loader.load( url, ( buffer ) => {

			this.parse( buffer, onLoad, onError );

		}, onProgress, onError );

	}
```
</details>

### `KTX2Loader.parse(buffer: ArrayBuffer, onLoad: (arg0: CompressedTexture) => any, onError: onErrorCallback): Promise<any>`

**JSDoc:**
```typescript
/**
	 * Parses the given KTX2 data.
	 *
	 * @param {ArrayBuffer} buffer - The raw KTX2 data as an array buffer.
	 * @param {function(CompressedTexture)} onLoad - Executed when the loading/parsing process has been finished.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 * @returns {Promise} A Promise that resolves when the parsing has been finished.
	 */
```

**Parameters:**

- **`buffer`** `ArrayBuffer`
- **`onLoad`** `(arg0: CompressedTexture) => any`
- **`onError`** `onErrorCallback`

**Returns:** `Promise<any>`

**Calls:**

- `_taskCache.has`
- `_taskCache.get`
- `cachedTask.promise.then( onLoad ).catch`
- `this._createTexture( buffer )
			.then( ( texture ) => onLoad ? onLoad( texture ) : null )
			.catch`

**Internal Comments:**
```
// Check for an existing task using this buffer. A transferred buffer cannot be transferred
// again from this thread.
```

<details><summary>Code</summary>

```typescript
parse( buffer, onLoad, onError ) {

		if ( this.workerConfig === null ) {

			throw new Error( 'THREE.KTX2Loader: Missing initialization with `.detectSupport( renderer )`.' );

		}

		// Check for an existing task using this buffer. A transferred buffer cannot be transferred
		// again from this thread.
		if ( _taskCache.has( buffer ) ) {

			const cachedTask = _taskCache.get( buffer );

			return cachedTask.promise.then( onLoad ).catch( onError );

		}

		this._createTexture( buffer )
			.then( ( texture ) => onLoad ? onLoad( texture ) : null )
			.catch( onError );

	}
```
</details>

### `KTX2Loader._createTextureFrom(transcodeResult: any, container: any): any`

**Parameters:**

- **`transcodeResult`** `any`
- **`container`** `any`

**Returns:** `any`

**Calls:**

- `Promise.reject`
- `parseColorSpace`

<details><summary>Code</summary>

```typescript
_createTextureFrom( transcodeResult, container ) {

		const { type: messageType, error, data: { faces, width, height, format, type, dfdFlags } } = transcodeResult;

		if ( messageType === 'error' ) return Promise.reject( error );

		let texture;

		if ( container.faceCount === 6 ) {

			texture = new CompressedCubeTexture( faces, format, type );

		} else {

			const mipmaps = faces[ 0 ].mipmaps;

			texture = container.layerCount > 1
				? new CompressedArrayTexture( mipmaps, width, height, container.layerCount, format, type )
				: new CompressedTexture( mipmaps, width, height, format, type );

		}

		texture.minFilter = faces[ 0 ].mipmaps.length === 1 ? LinearFilter : LinearMipmapLinearFilter;
		texture.magFilter = LinearFilter;
		texture.generateMipmaps = false;

		texture.needsUpdate = true;
		texture.colorSpace = parseColorSpace( container );
		texture.premultiplyAlpha = !! ( dfdFlags & KHR_DF_FLAG_ALPHA_PREMULTIPLIED );

		return texture;

	}
```
</details>

### `KTX2Loader._createTexture(buffer: ArrayBuffer, config: any): Promise<any>`

**JSDoc:**
```typescript
/**
	 * @private
	 * @param {ArrayBuffer} buffer
	 * @param {?Object} config
	 * @return {Promise<CompressedTexture|CompressedArrayTexture|DataTexture|Data3DTexture>}
	 */
```

**Parameters:**

- **`buffer`** `ArrayBuffer`
- **`config`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `read (from ../libs/ktx-parse.module.js)`
- `createRawTexture`
- `this.init().then( () => {

			return this.workerPool.postMessage( { type: 'transcode', buffer, taskConfig: taskConfig }, [ buffer ] );

		} ).then`
- `this._createTextureFrom`
- `_taskCache.set`

**Internal Comments:**
```
// Basis UASTC HDR is a subset of ASTC, which can be transcoded efficiently (x2)
// to BC6H. To detect whether a KTX2 file uses Basis UASTC HDR, or default (x2)
// ASTC, inspect the DFD color model. (x2)
// (x4)
// Source: https://github.com/BinomialLLC/basis_universal/issues/381 (x2)
// If the device supports ASTC, Basis UASTC HDR requires no transcoder. (x2)
// Cache the task result. (x4)
```

<details><summary>Code</summary>

```typescript
async _createTexture( buffer, config = {} ) {

		const container = read( new Uint8Array( buffer ) );

		// Basis UASTC HDR is a subset of ASTC, which can be transcoded efficiently
		// to BC6H. To detect whether a KTX2 file uses Basis UASTC HDR, or default
		// ASTC, inspect the DFD color model.
		//
		// Source: https://github.com/BinomialLLC/basis_universal/issues/381
		const isBasisHDR = container.vkFormat === VK_FORMAT_ASTC_4x4_SFLOAT_BLOCK_EXT
			&& container.dataFormatDescriptor[ 0 ].colorModel === 0xA7;

		// If the device supports ASTC, Basis UASTC HDR requires no transcoder.
		const needsTranscoder = container.vkFormat === VK_FORMAT_UNDEFINED
			|| isBasisHDR && ! this.workerConfig.astcHDRSupported;

		if ( ! needsTranscoder ) {

			return createRawTexture( container );

		}

		//
		const taskConfig = config;
		const texturePending = this.init().then( () => {

			return this.workerPool.postMessage( { type: 'transcode', buffer, taskConfig: taskConfig }, [ buffer ] );

		} ).then( ( e ) => this._createTextureFrom( e.data, container ) );

		// Cache the task result.
		_taskCache.set( buffer, { promise: texturePending } );

		return texturePending;

	}
```
</details>

### `KTX2Loader.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources. This method should be called
	 * when the loader is no longer required.
	 */
```

**Returns:** `void`

**Calls:**

- `this.workerPool.dispose`
- `URL.revokeObjectURL`

<details><summary>Code</summary>

```typescript
dispose() {

		this.workerPool.dispose();
		if ( this.workerSourceURL ) URL.revokeObjectURL( this.workerSourceURL );

		_activeLoaders --;

	}
```
</details>

### `init(wasmBinary: any): void`

**Parameters:**

- **`wasmBinary`** `any`

**Returns:** `void`

**Calls:**

- `new Promise( ( resolve ) => {

			BasisModule = { wasmBinary, onRuntimeInitialized: resolve };
			BASIS( BasisModule ); // eslint-disable-line no-undef

		} ).then`
- `BASIS`
- `BasisModule.initializeBasis`
- `console.warn`

<details><summary>Code</summary>

```typescript
function init( wasmBinary ) {

		transcoderPending = new Promise( ( resolve ) => {

			BasisModule = { wasmBinary, onRuntimeInitialized: resolve };
			BASIS( BasisModule ); // eslint-disable-line no-undef

		} ).then( () => {

			BasisModule.initializeBasis();

			if ( BasisModule.KTX2File === undefined ) {

				console.warn( 'THREE.KTX2Loader: Please update Basis Universal transcoder.' );

			}

		} );

	}
```
</details>

### `transcode(buffer: any): { faces: { mipmaps: { data: Uint8Array<ArrayBufferLike>; width: any; height: any; }[]; width: any; height: any; format: any; type: any; }[]; buffers: (ArrayBuffer | SharedArrayBuffer)[]; ... 5 more ...; type: any; }`

**Parameters:**

- **`buffer`** `any`

**Returns:** `{ faces: { mipmaps: { data: Uint8Array<ArrayBufferLike>; width: any; height: any; }[]; width: any; height: any; format: any; type: any; }[]; buffers: (ArrayBuffer | SharedArrayBuffer)[]; ... 5 more ...; type: any; }`

**Calls:**

- `ktx2File.close`
- `ktx2File.delete`
- `ktx2File.isValid`
- `cleanup`
- `ktx2File.isUASTC`
- `ktx2File.isETC1S`
- `ktx2File.isHDR`
- `ktx2File.getWidth`
- `ktx2File.getHeight`
- `ktx2File.getLayers`
- `ktx2File.getLevels`
- `ktx2File.getFaces`
- `ktx2File.getHasAlpha`
- `ktx2File.getDFDFlags`
- `getTranscoderFormat`
- `ktx2File.startTranscoding`
- `ktx2File.getImageLevelInfo`
- `console.warn`
- `ktx2File.getImageTranscodedSizeInBytes`
- `ktx2File.transcodeImage`
- `layerMips.push`
- `concat`
- `mipmaps.push`
- `buffers.push`
- `faces.push`

**Internal Comments:**
```
// Handles non-multiple-of-four dimensions in textures without mipmaps. Textures with (x3)
// mipmaps must use multiple-of-four dimensions, for some texture formats and APIs. (x3)
// See mrdoob/three.js#25908. (x3)
```

<details><summary>Code</summary>

```typescript
function transcode( buffer ) {

		const ktx2File = new BasisModule.KTX2File( new Uint8Array( buffer ) );

		function cleanup() {

			ktx2File.close();
			ktx2File.delete();

		}

		if ( ! ktx2File.isValid() ) {

			cleanup();
			throw new Error( 'THREE.KTX2Loader:	Invalid or unsupported .ktx2 file' );

		}

		let basisFormat;

		if ( ktx2File.isUASTC() ) {

			basisFormat = BasisFormat.UASTC;

		} else if ( ktx2File.isETC1S() ) {

			basisFormat = BasisFormat.ETC1S;

		} else if ( ktx2File.isHDR() ) {

			basisFormat = BasisFormat.UASTC_HDR;

		} else {

			throw new Error( 'THREE.KTX2Loader: Unknown Basis encoding' );

		}

		const width = ktx2File.getWidth();
		const height = ktx2File.getHeight();
		const layerCount = ktx2File.getLayers() || 1;
		const levelCount = ktx2File.getLevels();
		const faceCount = ktx2File.getFaces();
		const hasAlpha = ktx2File.getHasAlpha();
		const dfdFlags = ktx2File.getDFDFlags();

		const { transcoderFormat, engineFormat, engineType } = getTranscoderFormat( basisFormat, width, height, hasAlpha );

		if ( ! width || ! height || ! levelCount ) {

			cleanup();
			throw new Error( 'THREE.KTX2Loader:	Invalid texture' );

		}

		if ( ! ktx2File.startTranscoding() ) {

			cleanup();
			throw new Error( 'THREE.KTX2Loader: .startTranscoding failed' );

		}

		const faces = [];
		const buffers = [];

		for ( let face = 0; face < faceCount; face ++ ) {

			const mipmaps = [];

			for ( let mip = 0; mip < levelCount; mip ++ ) {

				const layerMips = [];

				let mipWidth, mipHeight;

				for ( let layer = 0; layer < layerCount; layer ++ ) {

					const levelInfo = ktx2File.getImageLevelInfo( mip, layer, face );

					if ( face === 0 && mip === 0 && layer === 0 && ( levelInfo.origWidth % 4 !== 0 || levelInfo.origHeight % 4 !== 0 ) ) {

						console.warn( 'THREE.KTX2Loader: ETC1S and UASTC textures should use multiple-of-four dimensions.' );

					}

					if ( levelCount > 1 ) {

						mipWidth = levelInfo.origWidth;
						mipHeight = levelInfo.origHeight;

					} else {

						// Handles non-multiple-of-four dimensions in textures without mipmaps. Textures with
						// mipmaps must use multiple-of-four dimensions, for some texture formats and APIs.
						// See mrdoob/three.js#25908.
						mipWidth = levelInfo.width;
						mipHeight = levelInfo.height;

					}

					let dst = new Uint8Array( ktx2File.getImageTranscodedSizeInBytes( mip, layer, 0, transcoderFormat ) );
					const status = ktx2File.transcodeImage( dst, mip, layer, face, transcoderFormat, 0, - 1, - 1 );

					if ( engineType === EngineType.HalfFloatType ) {

						dst = new Uint16Array( dst.buffer, dst.byteOffset, dst.byteLength / Uint16Array.BYTES_PER_ELEMENT );

					}

					if ( ! status ) {

						cleanup();
						throw new Error( 'THREE.KTX2Loader: .transcodeImage failed.' );

					}

					layerMips.push( dst );

				}

				const mipData = concat( layerMips );

				mipmaps.push( { data: mipData, width: mipWidth, height: mipHeight } );
				buffers.push( mipData.buffer );

			}

			faces.push( { mipmaps, width, height, format: engineFormat, type: engineType } );

		}

		cleanup();

		return { faces, buffers, width, height, hasAlpha, dfdFlags, format: engineFormat, type: engineType };

	}
```
</details>

### `cleanup(): void`

**Returns:** `void`

**Calls:**

- `ktx2File.close`
- `ktx2File.delete`

<details><summary>Code</summary>

```typescript
function cleanup() {

			ktx2File.close();
			ktx2File.delete();

		}
```
</details>

### `getTranscoderFormat(basisFormat: any, width: any, height: any, hasAlpha: any): { transcoderFormat: any; engineFormat: any; engineType: any; }`

**Parameters:**

- **`basisFormat`** `any`
- **`width`** `any`
- **`height`** `any`
- **`hasAlpha`** `any`

**Returns:** `{ transcoderFormat: any; engineFormat: any; engineType: any; }`

**Calls:**

- `opt.basisFormat.includes`
- `isPowerOfTwo`

<details><summary>Code</summary>

```typescript
function getTranscoderFormat( basisFormat, width, height, hasAlpha ) {

		const options = OPTIONS[ basisFormat ];

		for ( let i = 0; i < options.length; i ++ ) {

			const opt = options[ i ];

			if ( opt.if && ! config[ opt.if ] ) continue;
			if ( ! opt.basisFormat.includes( basisFormat ) ) continue;
			if ( hasAlpha && opt.transcoderFormat.length < 2 ) continue;
			if ( opt.needsPowerOfTwo && ! ( isPowerOfTwo( width ) && isPowerOfTwo( height ) ) ) continue;

			const transcoderFormat = opt.transcoderFormat[ hasAlpha ? 1 : 0 ];
			const engineFormat = opt.engineFormat[ hasAlpha ? 1 : 0 ];
			const engineType = opt.engineType[ 0 ];

			return { transcoderFormat, engineFormat, engineType };

		}

		throw new Error( 'THREE.KTX2Loader: Failed to identify transcoding target.' );

	}
```
</details>

### `isPowerOfTwo(value: any): boolean`

**Parameters:**

- **`value`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isPowerOfTwo( value ) {

		if ( value <= 2 ) return true;

		return ( value & ( value - 1 ) ) === 0 && value !== 0;

	}
```
</details>

### `concat(arrays: Uint8Array<ArrayBufferLike>[]): Uint8Array<ArrayBufferLike>`

**JSDoc:**
```typescript
/**
	 * Concatenates N byte arrays.
	 *
	 * @param {Uint8Array[]} arrays
	 * @return {Uint8Array}
	 */
```

**Parameters:**

- **`arrays`** `Uint8Array<ArrayBufferLike>[]`

**Returns:** `Uint8Array<ArrayBufferLike>`

**Calls:**

- `result.set`

<details><summary>Code</summary>

```typescript
function concat( arrays ) {

		if ( arrays.length === 1 ) return arrays[ 0 ];

		let totalByteLength = 0;

		for ( let i = 0; i < arrays.length; i ++ ) {

			const array = arrays[ i ];
			totalByteLength += array.byteLength;

		}

		const result = new Uint8Array( totalByteLength );

		let byteOffset = 0;

		for ( let i = 0; i < arrays.length; i ++ ) {

			const array = arrays[ i ];
			result.set( array, byteOffset );

			byteOffset += array.byteLength;

		}

		return result;

	}
```
</details>

### `createRawTexture(container: any): Promise<any>`

**Parameters:**

- **`container`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `zstd.init`
- `resolve`
- `Math.max`
- `zstd.decode`
- `mipmaps.push`
- `UNCOMPRESSED_FORMATS.has`
- `parseColorSpace`
- `Promise.resolve`

**Internal Comments:**
```
// (x5)
```

<details><summary>Code</summary>

```typescript
async function createRawTexture( container ) {

	const { vkFormat } = container;

	if ( FORMAT_MAP[ vkFormat ] === undefined ) {

		throw new Error( 'THREE.KTX2Loader: Unsupported vkFormat.' );

	}

	//

	let zstd;

	if ( container.supercompressionScheme === KHR_SUPERCOMPRESSION_ZSTD ) {

		if ( ! _zstd ) {

			_zstd = new Promise( async ( resolve ) => {

				const zstd = new ZSTDDecoder();
				await zstd.init();
				resolve( zstd );

			} );

		}

		zstd = await _zstd;

	}

	//

	const mipmaps = [];


	for ( let levelIndex = 0; levelIndex < container.levels.length; levelIndex ++ ) {

		const levelWidth = Math.max( 1, container.pixelWidth >> levelIndex );
		const levelHeight = Math.max( 1, container.pixelHeight >> levelIndex );
		const levelDepth = container.pixelDepth ? Math.max( 1, container.pixelDepth >> levelIndex ) : 0;

		const level = container.levels[ levelIndex ];

		let levelData;

		if ( container.supercompressionScheme === KHR_SUPERCOMPRESSION_NONE ) {

			levelData = level.levelData;

		} else if ( container.supercompressionScheme === KHR_SUPERCOMPRESSION_ZSTD ) {

			levelData = zstd.decode( level.levelData, level.uncompressedByteLength );

		} else {

			throw new Error( 'THREE.KTX2Loader: Unsupported supercompressionScheme.' );

		}

		let data;

		if ( TYPE_MAP[ vkFormat ] === FloatType ) {

			data = new Float32Array(

				levelData.buffer,
				levelData.byteOffset,
				levelData.byteLength / Float32Array.BYTES_PER_ELEMENT

			);

		} else if ( TYPE_MAP[ vkFormat ] === HalfFloatType ) {

			data = new Uint16Array(

				levelData.buffer,
				levelData.byteOffset,
				levelData.byteLength / Uint16Array.BYTES_PER_ELEMENT

			);

		} else {

			data = levelData;

		}

		mipmaps.push( {

			data: data,
			width: levelWidth,
			height: levelHeight,
			depth: levelDepth,

		} );

	}

	let texture;

	if ( UNCOMPRESSED_FORMATS.has( FORMAT_MAP[ vkFormat ] ) ) {

		texture = container.pixelDepth === 0
			? new DataTexture( mipmaps[ 0 ].data, container.pixelWidth, container.pixelHeight )
			: new Data3DTexture( mipmaps[ 0 ].data, container.pixelWidth, container.pixelHeight, container.pixelDepth );

	} else {

		if ( container.pixelDepth > 0 ) throw new Error( 'THREE.KTX2Loader: Unsupported pixelDepth.' );

		texture = new CompressedTexture( mipmaps, container.pixelWidth, container.pixelHeight );

		texture.minFilter = mipmaps.length === 1 ? LinearFilter : LinearMipmapLinearFilter;
		texture.magFilter = LinearFilter;

	}

	texture.mipmaps = mipmaps;

	texture.type = TYPE_MAP[ vkFormat ];
	texture.format = FORMAT_MAP[ vkFormat ];
	texture.colorSpace = parseColorSpace( container );
	texture.needsUpdate = true;

	//

	return Promise.resolve( texture );

}
```
</details>

### `parseColorSpace(container: any): any`

**Parameters:**

- **`container`** `any`

**Returns:** `any`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
function parseColorSpace( container ) {

	const dfd = container.dataFormatDescriptor[ 0 ];

	if ( dfd.colorPrimaries === KHR_DF_PRIMARIES_BT709 ) {

		return dfd.transferFunction === KHR_DF_TRANSFER_SRGB ? SRGBColorSpace : LinearSRGBColorSpace;

	} else if ( dfd.colorPrimaries === KHR_DF_PRIMARIES_DISPLAYP3 ) {

		return dfd.transferFunction === KHR_DF_TRANSFER_SRGB ? DisplayP3ColorSpace : LinearDisplayP3ColorSpace;

	} else if ( dfd.colorPrimaries === KHR_DF_PRIMARIES_UNSPECIFIED ) {

		return NoColorSpace;

	} else {

		console.warn( `THREE.KTX2Loader: Unsupported color primaries, "${ dfd.colorPrimaries }"` );
		return NoColorSpace;

	}

}
```
</details>


---

## Classes

### `KTX2Loader`

<details><summary>Class Code</summary>

```ts
class KTX2Loader extends Loader {

	/**
	 * Constructs a new KTX2 loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		this.transcoderPath = '';
		this.transcoderBinary = null;
		this.transcoderPending = null;

		this.workerPool = new WorkerPool();
		this.workerSourceURL = '';
		this.workerConfig = null;

		if ( typeof MSC_TRANSCODER !== 'undefined' ) {

			console.warn(

				'THREE.KTX2Loader: Please update to latest "basis_transcoder".'
				+ ' "msc_basis_transcoder" is no longer supported in three.js r125+.'

			);

		}

	}

	/**
	 * Sets the transcoder path.
	 *
	 * The WASM transcoder and JS wrapper are available from the `examples/jsm/libs/basis` directory.
	 *
	 * @param {string} path - The transcoder path to set.
	 * @return {KTX2Loader} A reference to this loader.
	 */
	setTranscoderPath( path ) {

		this.transcoderPath = path;

		return this;

	}

	/**
	 * Sets the maximum number of Web Workers to be allocated by this instance.
	 *
	 * @param {number} workerLimit - The worker limit.
	 * @return {KTX2Loader} A reference to this loader.
	 */
	setWorkerLimit( workerLimit ) {

		this.workerPool.setWorkerLimit( workerLimit );

		return this;

	}


	/**
	 * Async version of {@link KTX2Loader#detectSupport}.
	 *
	 * @async
	 * @param {WebGPURenderer|WebGLRenderer} renderer - The renderer.
	 * @return {Promise} A Promise that resolves when the support has been detected.
	 */
	async detectSupportAsync( renderer ) {

		this.workerConfig = {
			astcSupported: await renderer.hasFeatureAsync( 'texture-compression-astc' ),
			astcHDRSupported: false, // https://github.com/gpuweb/gpuweb/issues/3856
			etc1Supported: await renderer.hasFeatureAsync( 'texture-compression-etc1' ),
			etc2Supported: await renderer.hasFeatureAsync( 'texture-compression-etc2' ),
			dxtSupported: await renderer.hasFeatureAsync( 'texture-compression-bc' ),
			bptcSupported: await renderer.hasFeatureAsync( 'texture-compression-bptc' ),
			pvrtcSupported: await renderer.hasFeatureAsync( 'texture-compression-pvrtc' )
		};

		return this;

	}

	/**
	 * Detects hardware support for available compressed texture formats, to determine
	 * the output format for the transcoder. Must be called before loading a texture.
	 *
	 * @param {WebGPURenderer|WebGLRenderer} renderer - The renderer.
	 * @return {KTX2Loader} A reference to this loader.
	 */
	detectSupport( renderer ) {

		if ( renderer.isWebGPURenderer === true ) {

			this.workerConfig = {
				astcSupported: renderer.hasFeature( 'texture-compression-astc' ),
				astcHDRSupported: false, // https://github.com/gpuweb/gpuweb/issues/3856
				etc1Supported: renderer.hasFeature( 'texture-compression-etc1' ),
				etc2Supported: renderer.hasFeature( 'texture-compression-etc2' ),
				dxtSupported: renderer.hasFeature( 'texture-compression-bc' ),
				bptcSupported: renderer.hasFeature( 'texture-compression-bptc' ),
				pvrtcSupported: renderer.hasFeature( 'texture-compression-pvrtc' )
			};

		} else {

			this.workerConfig = {
				astcSupported: renderer.extensions.has( 'WEBGL_compressed_texture_astc' ),
				astcHDRSupported: renderer.extensions.has( 'WEBGL_compressed_texture_astc' )
					&& renderer.extensions.get( 'WEBGL_compressed_texture_astc' ).getSupportedProfiles().includes( 'hdr' ),
				etc1Supported: renderer.extensions.has( 'WEBGL_compressed_texture_etc1' ),
				etc2Supported: renderer.extensions.has( 'WEBGL_compressed_texture_etc' ),
				dxtSupported: renderer.extensions.has( 'WEBGL_compressed_texture_s3tc' ),
				bptcSupported: renderer.extensions.has( 'EXT_texture_compression_bptc' ),
				pvrtcSupported: renderer.extensions.has( 'WEBGL_compressed_texture_pvrtc' )
					|| renderer.extensions.has( 'WEBKIT_WEBGL_compressed_texture_pvrtc' )
			};

		}

		return this;

	}

	// TODO: Make this method private

	init() {

		if ( ! this.transcoderPending ) {

			// Load transcoder wrapper.
			const jsLoader = new FileLoader( this.manager );
			jsLoader.setPath( this.transcoderPath );
			jsLoader.setWithCredentials( this.withCredentials );
			const jsContent = jsLoader.loadAsync( 'basis_transcoder.js' );

			// Load transcoder WASM binary.
			const binaryLoader = new FileLoader( this.manager );
			binaryLoader.setPath( this.transcoderPath );
			binaryLoader.setResponseType( 'arraybuffer' );
			binaryLoader.setWithCredentials( this.withCredentials );
			const binaryContent = binaryLoader.loadAsync( 'basis_transcoder.wasm' );

			this.transcoderPending = Promise.all( [ jsContent, binaryContent ] )
				.then( ( [ jsContent, binaryContent ] ) => {

					const fn = KTX2Loader.BasisWorker.toString();

					const body = [
						'/* constants */',
						'let _EngineFormat = ' + JSON.stringify( KTX2Loader.EngineFormat ),
						'let _EngineType = ' + JSON.stringify( KTX2Loader.EngineType ),
						'let _TranscoderFormat = ' + JSON.stringify( KTX2Loader.TranscoderFormat ),
						'let _BasisFormat = ' + JSON.stringify( KTX2Loader.BasisFormat ),
						'/* basis_transcoder.js */',
						jsContent,
						'/* worker */',
						fn.substring( fn.indexOf( '{' ) + 1, fn.lastIndexOf( '}' ) )
					].join( '\n' );

					this.workerSourceURL = URL.createObjectURL( new Blob( [ body ] ) );
					this.transcoderBinary = binaryContent;

					this.workerPool.setWorkerCreator( () => {

						const worker = new Worker( this.workerSourceURL );
						const transcoderBinary = this.transcoderBinary.slice( 0 );

						worker.postMessage( { type: 'init', config: this.workerConfig, transcoderBinary }, [ transcoderBinary ] );

						return worker;

					} );

				} );

			if ( _activeLoaders > 0 ) {

				// Each instance loads a transcoder and allocates workers, increasing network and memory cost.

				console.warn(

					'THREE.KTX2Loader: Multiple active KTX2 loaders may cause performance issues.'
					+ ' Use a single KTX2Loader instance, or call .dispose() on old instances.'

				);

			}

			_activeLoaders ++;

		}

		return this.transcoderPending;

	}

	/**
	 * Starts loading from the given URL and passes the loaded KTX2 texture
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(CompressedTexture)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		if ( this.workerConfig === null ) {

			throw new Error( 'THREE.KTX2Loader: Missing initialization with `.detectSupport( renderer )`.' );

		}

		const loader = new FileLoader( this.manager );

		loader.setPath( this.path );
		loader.setCrossOrigin( this.crossOrigin );
		loader.setWithCredentials( this.withCredentials );
		loader.setResponseType( 'arraybuffer' );

		loader.load( url, ( buffer ) => {

			this.parse( buffer, onLoad, onError );

		}, onProgress, onError );

	}

	/**
	 * Parses the given KTX2 data.
	 *
	 * @param {ArrayBuffer} buffer - The raw KTX2 data as an array buffer.
	 * @param {function(CompressedTexture)} onLoad - Executed when the loading/parsing process has been finished.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 * @returns {Promise} A Promise that resolves when the parsing has been finished.
	 */
	parse( buffer, onLoad, onError ) {

		if ( this.workerConfig === null ) {

			throw new Error( 'THREE.KTX2Loader: Missing initialization with `.detectSupport( renderer )`.' );

		}

		// Check for an existing task using this buffer. A transferred buffer cannot be transferred
		// again from this thread.
		if ( _taskCache.has( buffer ) ) {

			const cachedTask = _taskCache.get( buffer );

			return cachedTask.promise.then( onLoad ).catch( onError );

		}

		this._createTexture( buffer )
			.then( ( texture ) => onLoad ? onLoad( texture ) : null )
			.catch( onError );

	}

	_createTextureFrom( transcodeResult, container ) {

		const { type: messageType, error, data: { faces, width, height, format, type, dfdFlags } } = transcodeResult;

		if ( messageType === 'error' ) return Promise.reject( error );

		let texture;

		if ( container.faceCount === 6 ) {

			texture = new CompressedCubeTexture( faces, format, type );

		} else {

			const mipmaps = faces[ 0 ].mipmaps;

			texture = container.layerCount > 1
				? new CompressedArrayTexture( mipmaps, width, height, container.layerCount, format, type )
				: new CompressedTexture( mipmaps, width, height, format, type );

		}

		texture.minFilter = faces[ 0 ].mipmaps.length === 1 ? LinearFilter : LinearMipmapLinearFilter;
		texture.magFilter = LinearFilter;
		texture.generateMipmaps = false;

		texture.needsUpdate = true;
		texture.colorSpace = parseColorSpace( container );
		texture.premultiplyAlpha = !! ( dfdFlags & KHR_DF_FLAG_ALPHA_PREMULTIPLIED );

		return texture;

	}

	/**
	 * @private
	 * @param {ArrayBuffer} buffer
	 * @param {?Object} config
	 * @return {Promise<CompressedTexture|CompressedArrayTexture|DataTexture|Data3DTexture>}
	 */
	async _createTexture( buffer, config = {} ) {

		const container = read( new Uint8Array( buffer ) );

		// Basis UASTC HDR is a subset of ASTC, which can be transcoded efficiently
		// to BC6H. To detect whether a KTX2 file uses Basis UASTC HDR, or default
		// ASTC, inspect the DFD color model.
		//
		// Source: https://github.com/BinomialLLC/basis_universal/issues/381
		const isBasisHDR = container.vkFormat === VK_FORMAT_ASTC_4x4_SFLOAT_BLOCK_EXT
			&& container.dataFormatDescriptor[ 0 ].colorModel === 0xA7;

		// If the device supports ASTC, Basis UASTC HDR requires no transcoder.
		const needsTranscoder = container.vkFormat === VK_FORMAT_UNDEFINED
			|| isBasisHDR && ! this.workerConfig.astcHDRSupported;

		if ( ! needsTranscoder ) {

			return createRawTexture( container );

		}

		//
		const taskConfig = config;
		const texturePending = this.init().then( () => {

			return this.workerPool.postMessage( { type: 'transcode', buffer, taskConfig: taskConfig }, [ buffer ] );

		} ).then( ( e ) => this._createTextureFrom( e.data, container ) );

		// Cache the task result.
		_taskCache.set( buffer, { promise: texturePending } );

		return texturePending;

	}

	/**
	 * Frees internal resources. This method should be called
	 * when the loader is no longer required.
	 */
	dispose() {

		this.workerPool.dispose();
		if ( this.workerSourceURL ) URL.revokeObjectURL( this.workerSourceURL );

		_activeLoaders --;

	}

}
```
</details>

#### Methods

##### `setTranscoderPath(path: string): KTX2Loader`

<details><summary>Code</summary>

```ts
setTranscoderPath( path ) {

		this.transcoderPath = path;

		return this;

	}
```
</details>

##### `setWorkerLimit(workerLimit: number): KTX2Loader`

<details><summary>Code</summary>

```ts
setWorkerLimit( workerLimit ) {

		this.workerPool.setWorkerLimit( workerLimit );

		return this;

	}
```
</details>

##### `detectSupportAsync(renderer: any): Promise<any>`

<details><summary>Code</summary>

```ts
async detectSupportAsync( renderer ) {

		this.workerConfig = {
			astcSupported: await renderer.hasFeatureAsync( 'texture-compression-astc' ),
			astcHDRSupported: false, // https://github.com/gpuweb/gpuweb/issues/3856
			etc1Supported: await renderer.hasFeatureAsync( 'texture-compression-etc1' ),
			etc2Supported: await renderer.hasFeatureAsync( 'texture-compression-etc2' ),
			dxtSupported: await renderer.hasFeatureAsync( 'texture-compression-bc' ),
			bptcSupported: await renderer.hasFeatureAsync( 'texture-compression-bptc' ),
			pvrtcSupported: await renderer.hasFeatureAsync( 'texture-compression-pvrtc' )
		};

		return this;

	}
```
</details>

##### `detectSupport(renderer: any): KTX2Loader`

<details><summary>Code</summary>

```ts
detectSupport( renderer ) {

		if ( renderer.isWebGPURenderer === true ) {

			this.workerConfig = {
				astcSupported: renderer.hasFeature( 'texture-compression-astc' ),
				astcHDRSupported: false, // https://github.com/gpuweb/gpuweb/issues/3856
				etc1Supported: renderer.hasFeature( 'texture-compression-etc1' ),
				etc2Supported: renderer.hasFeature( 'texture-compression-etc2' ),
				dxtSupported: renderer.hasFeature( 'texture-compression-bc' ),
				bptcSupported: renderer.hasFeature( 'texture-compression-bptc' ),
				pvrtcSupported: renderer.hasFeature( 'texture-compression-pvrtc' )
			};

		} else {

			this.workerConfig = {
				astcSupported: renderer.extensions.has( 'WEBGL_compressed_texture_astc' ),
				astcHDRSupported: renderer.extensions.has( 'WEBGL_compressed_texture_astc' )
					&& renderer.extensions.get( 'WEBGL_compressed_texture_astc' ).getSupportedProfiles().includes( 'hdr' ),
				etc1Supported: renderer.extensions.has( 'WEBGL_compressed_texture_etc1' ),
				etc2Supported: renderer.extensions.has( 'WEBGL_compressed_texture_etc' ),
				dxtSupported: renderer.extensions.has( 'WEBGL_compressed_texture_s3tc' ),
				bptcSupported: renderer.extensions.has( 'EXT_texture_compression_bptc' ),
				pvrtcSupported: renderer.extensions.has( 'WEBGL_compressed_texture_pvrtc' )
					|| renderer.extensions.has( 'WEBKIT_WEBGL_compressed_texture_pvrtc' )
			};

		}

		return this;

	}
```
</details>

##### `init(): Promise<void>`

<details><summary>Code</summary>

```ts
init() {

		if ( ! this.transcoderPending ) {

			// Load transcoder wrapper.
			const jsLoader = new FileLoader( this.manager );
			jsLoader.setPath( this.transcoderPath );
			jsLoader.setWithCredentials( this.withCredentials );
			const jsContent = jsLoader.loadAsync( 'basis_transcoder.js' );

			// Load transcoder WASM binary.
			const binaryLoader = new FileLoader( this.manager );
			binaryLoader.setPath( this.transcoderPath );
			binaryLoader.setResponseType( 'arraybuffer' );
			binaryLoader.setWithCredentials( this.withCredentials );
			const binaryContent = binaryLoader.loadAsync( 'basis_transcoder.wasm' );

			this.transcoderPending = Promise.all( [ jsContent, binaryContent ] )
				.then( ( [ jsContent, binaryContent ] ) => {

					const fn = KTX2Loader.BasisWorker.toString();

					const body = [
						'/* constants */',
						'let _EngineFormat = ' + JSON.stringify( KTX2Loader.EngineFormat ),
						'let _EngineType = ' + JSON.stringify( KTX2Loader.EngineType ),
						'let _TranscoderFormat = ' + JSON.stringify( KTX2Loader.TranscoderFormat ),
						'let _BasisFormat = ' + JSON.stringify( KTX2Loader.BasisFormat ),
						'/* basis_transcoder.js */',
						jsContent,
						'/* worker */',
						fn.substring( fn.indexOf( '{' ) + 1, fn.lastIndexOf( '}' ) )
					].join( '\n' );

					this.workerSourceURL = URL.createObjectURL( new Blob( [ body ] ) );
					this.transcoderBinary = binaryContent;

					this.workerPool.setWorkerCreator( () => {

						const worker = new Worker( this.workerSourceURL );
						const transcoderBinary = this.transcoderBinary.slice( 0 );

						worker.postMessage( { type: 'init', config: this.workerConfig, transcoderBinary }, [ transcoderBinary ] );

						return worker;

					} );

				} );

			if ( _activeLoaders > 0 ) {

				// Each instance loads a transcoder and allocates workers, increasing network and memory cost.

				console.warn(

					'THREE.KTX2Loader: Multiple active KTX2 loaders may cause performance issues.'
					+ ' Use a single KTX2Loader instance, or call .dispose() on old instances.'

				);

			}

			_activeLoaders ++;

		}

		return this.transcoderPending;

	}
```
</details>

##### `load(url: string, onLoad: (arg0: CompressedTexture) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		if ( this.workerConfig === null ) {

			throw new Error( 'THREE.KTX2Loader: Missing initialization with `.detectSupport( renderer )`.' );

		}

		const loader = new FileLoader( this.manager );

		loader.setPath( this.path );
		loader.setCrossOrigin( this.crossOrigin );
		loader.setWithCredentials( this.withCredentials );
		loader.setResponseType( 'arraybuffer' );

		loader.load( url, ( buffer ) => {

			this.parse( buffer, onLoad, onError );

		}, onProgress, onError );

	}
```
</details>

##### `parse(buffer: ArrayBuffer, onLoad: (arg0: CompressedTexture) => any, onError: onErrorCallback): Promise<any>`

<details><summary>Code</summary>

```ts
parse( buffer, onLoad, onError ) {

		if ( this.workerConfig === null ) {

			throw new Error( 'THREE.KTX2Loader: Missing initialization with `.detectSupport( renderer )`.' );

		}

		// Check for an existing task using this buffer. A transferred buffer cannot be transferred
		// again from this thread.
		if ( _taskCache.has( buffer ) ) {

			const cachedTask = _taskCache.get( buffer );

			return cachedTask.promise.then( onLoad ).catch( onError );

		}

		this._createTexture( buffer )
			.then( ( texture ) => onLoad ? onLoad( texture ) : null )
			.catch( onError );

	}
```
</details>

##### `_createTextureFrom(transcodeResult: any, container: any): any`

<details><summary>Code</summary>

```ts
_createTextureFrom( transcodeResult, container ) {

		const { type: messageType, error, data: { faces, width, height, format, type, dfdFlags } } = transcodeResult;

		if ( messageType === 'error' ) return Promise.reject( error );

		let texture;

		if ( container.faceCount === 6 ) {

			texture = new CompressedCubeTexture( faces, format, type );

		} else {

			const mipmaps = faces[ 0 ].mipmaps;

			texture = container.layerCount > 1
				? new CompressedArrayTexture( mipmaps, width, height, container.layerCount, format, type )
				: new CompressedTexture( mipmaps, width, height, format, type );

		}

		texture.minFilter = faces[ 0 ].mipmaps.length === 1 ? LinearFilter : LinearMipmapLinearFilter;
		texture.magFilter = LinearFilter;
		texture.generateMipmaps = false;

		texture.needsUpdate = true;
		texture.colorSpace = parseColorSpace( container );
		texture.premultiplyAlpha = !! ( dfdFlags & KHR_DF_FLAG_ALPHA_PREMULTIPLIED );

		return texture;

	}
```
</details>

##### `_createTexture(buffer: ArrayBuffer, config: any): Promise<any>`

<details><summary>Code</summary>

```ts
async _createTexture( buffer, config = {} ) {

		const container = read( new Uint8Array( buffer ) );

		// Basis UASTC HDR is a subset of ASTC, which can be transcoded efficiently
		// to BC6H. To detect whether a KTX2 file uses Basis UASTC HDR, or default
		// ASTC, inspect the DFD color model.
		//
		// Source: https://github.com/BinomialLLC/basis_universal/issues/381
		const isBasisHDR = container.vkFormat === VK_FORMAT_ASTC_4x4_SFLOAT_BLOCK_EXT
			&& container.dataFormatDescriptor[ 0 ].colorModel === 0xA7;

		// If the device supports ASTC, Basis UASTC HDR requires no transcoder.
		const needsTranscoder = container.vkFormat === VK_FORMAT_UNDEFINED
			|| isBasisHDR && ! this.workerConfig.astcHDRSupported;

		if ( ! needsTranscoder ) {

			return createRawTexture( container );

		}

		//
		const taskConfig = config;
		const texturePending = this.init().then( () => {

			return this.workerPool.postMessage( { type: 'transcode', buffer, taskConfig: taskConfig }, [ buffer ] );

		} ).then( ( e ) => this._createTextureFrom( e.data, container ) );

		// Cache the task result.
		_taskCache.set( buffer, { promise: texturePending } );

		return texturePending;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.workerPool.dispose();
		if ( this.workerSourceURL ) URL.revokeObjectURL( this.workerSourceURL );

		_activeLoaders --;

	}
```
</details>


---