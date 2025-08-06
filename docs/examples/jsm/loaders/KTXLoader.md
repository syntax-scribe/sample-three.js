[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `KTXLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 2 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 14 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/KTXLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `CompressedTextureLoader` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `ktx` | `any` | let/var | `new KhronosTextureContainer( buffer, 1 )` | ✗ |
| `HEADER_LEN` | `number` | let/var | `12 + ( 13 * 4 )` | ✗ |
| `COMPRESSED_2D` | `0` | let/var | `0` | ✗ |
| `identifier` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( this.arrayBuffer, 0, 12 )` | ✗ |
| `dataSize` | `number` | let/var | `Uint32Array.BYTES_PER_ELEMENT` | ✗ |
| `headerDataView` | `DataView<ArrayBuffer>` | let/var | `new DataView( this.arrayBuffer, 12, 13 * dataSize )` | ✗ |
| `littleEndian` | `boolean` | let/var | `endianness === 0x04030201` | ✗ |
| `mipmaps` | `any[]` | let/var | `[]` | ✗ |
| `dataOffset` | `number` | let/var | `HEADER_LEN + this.bytesOfKeyValueData` | ✗ |
| `width` | `number` | let/var | `this.pixelWidth` | ✗ |
| `height` | `number` | let/var | `this.pixelHeight` | ✗ |
| `mipmapCount` | `number` | let/var | `loadMipmaps ? this.numberOfMipmapLevels : 1` | ✗ |
| `imageSize` | `number` | let/var | `new Int32Array( this.arrayBuffer, dataOffset, 1 )[ 0 ]` | ✗ |
| `byteArray` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( this.arrayBuffer, dataOffset, imageSize )` | ✗ |


---

## Functions

### `KTXLoader.parse(buffer: ArrayBuffer, loadMipmaps: boolean): CompressedTextureLoader`

**JSDoc:**
```typescript
/**
	 * Parses the given KTX texture data.
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

- `ktx.mipmaps`

<details><summary>Code</summary>

```typescript
parse( buffer, loadMipmaps ) {

		const ktx = new KhronosTextureContainer( buffer, 1 );

		return {
			mipmaps: ktx.mipmaps( loadMipmaps ),
			width: ktx.pixelWidth,
			height: ktx.pixelHeight,
			format: ktx.glInternalFormat,
			isCubemap: ktx.numberOfFaces === 6,
			mipmapCount: ktx.numberOfMipmapLevels
		};

	}
```
</details>

### `KhronosTextureContainer.mipmaps(loadMipmaps: any): { data: Uint8Array<ArrayBuffer>; width: number; height: number; }[]`

**Parameters:**

- **`loadMipmaps`** `any`

**Returns:** `{ data: Uint8Array<ArrayBuffer>; width: number; height: number; }[]`

**Calls:**

- `mipmaps.push`
- `Math.max`

**Internal Comments:**
```
// initialize width & height for level 1 (x2)
```

<details><summary>Code</summary>

```typescript
mipmaps( loadMipmaps ) {

		const mipmaps = [];

		// initialize width & height for level 1
		let dataOffset = HEADER_LEN + this.bytesOfKeyValueData;
		let width = this.pixelWidth;
		let height = this.pixelHeight;
		const mipmapCount = loadMipmaps ? this.numberOfMipmapLevels : 1;

		for ( let level = 0; level < mipmapCount; level ++ ) {

			const imageSize = new Int32Array( this.arrayBuffer, dataOffset, 1 )[ 0 ]; // size per face, since not supporting array cubemaps
			dataOffset += 4; // size of the image + 4 for the imageSize field

			for ( let face = 0; face < this.numberOfFaces; face ++ ) {

				const byteArray = new Uint8Array( this.arrayBuffer, dataOffset, imageSize );

				mipmaps.push( { 'data': byteArray, 'width': width, 'height': height } );

				dataOffset += imageSize;
				dataOffset += 3 - ( ( imageSize + 3 ) % 4 ); // add padding for odd sized image

			}

			width = Math.max( 1.0, width * 0.5 );
			height = Math.max( 1.0, height * 0.5 );

		}

		return mipmaps;

	}
```
</details>


---

## Classes

### `KTXLoader`

<details><summary>Class Code</summary>

```ts
class KTXLoader extends CompressedTextureLoader {

	/**
	 * Constructs a new KTX loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Parses the given KTX texture data.
	 *
	 * @param {ArrayBuffer} buffer - The raw texture data.
	 * @param {boolean} loadMipmaps - Whether to load mipmaps or not.
	 * @return {CompressedTextureLoader~TexData} An object representing the parsed texture data.
	 */
	parse( buffer, loadMipmaps ) {

		const ktx = new KhronosTextureContainer( buffer, 1 );

		return {
			mipmaps: ktx.mipmaps( loadMipmaps ),
			width: ktx.pixelWidth,
			height: ktx.pixelHeight,
			format: ktx.glInternalFormat,
			isCubemap: ktx.numberOfFaces === 6,
			mipmapCount: ktx.numberOfMipmapLevels
		};

	}

}
```
</details>

#### Methods

##### `parse(buffer: ArrayBuffer, loadMipmaps: boolean): CompressedTextureLoader`

<details><summary>Code</summary>

```ts
parse( buffer, loadMipmaps ) {

		const ktx = new KhronosTextureContainer( buffer, 1 );

		return {
			mipmaps: ktx.mipmaps( loadMipmaps ),
			width: ktx.pixelWidth,
			height: ktx.pixelHeight,
			format: ktx.glInternalFormat,
			isCubemap: ktx.numberOfFaces === 6,
			mipmapCount: ktx.numberOfMipmapLevels
		};

	}
```
</details>

### `KhronosTextureContainer`

<details><summary>Class Code</summary>

```ts
class KhronosTextureContainer {

	/**
	 * @private
	 * @param {ArrayBuffer} arrayBuffer - contents of the KTX container file
	 * @param {number} facesExpected - should be either 1 or 6, based whether a cube texture or or
	 * @param {boolean} threeDExpected - provision for indicating that data should be a 3D texture, not implemented
	 * @param {boolean} textureArrayExpected - provision for indicating that data should be a texture array, not implemented
	 */
	constructor( arrayBuffer, facesExpected /*, threeDExpected, textureArrayExpected */ ) {

		this.arrayBuffer = arrayBuffer;

		// Test that it is a ktx formatted file, based on the first 12 bytes, character representation is:
		// '´', 'K', 'T', 'X', ' ', '1', '1', 'ª', '\r', '\n', '\x1A', '\n'
		// 0xAB, 0x4B, 0x54, 0x58, 0x20, 0x31, 0x31, 0xBB, 0x0D, 0x0A, 0x1A, 0x0A
		const identifier = new Uint8Array( this.arrayBuffer, 0, 12 );
		if ( identifier[ 0 ] !== 0xAB ||
			identifier[ 1 ] !== 0x4B ||
			identifier[ 2 ] !== 0x54 ||
			identifier[ 3 ] !== 0x58 ||
			identifier[ 4 ] !== 0x20 ||
			identifier[ 5 ] !== 0x31 ||
			identifier[ 6 ] !== 0x31 ||
			identifier[ 7 ] !== 0xBB ||
			identifier[ 8 ] !== 0x0D ||
			identifier[ 9 ] !== 0x0A ||
			identifier[ 10 ] !== 0x1A ||
			identifier[ 11 ] !== 0x0A ) {

			console.error( 'texture missing KTX identifier' );
			return;

		}

		// load the reset of the header in native 32 bit uint
		const dataSize = Uint32Array.BYTES_PER_ELEMENT;
		const headerDataView = new DataView( this.arrayBuffer, 12, 13 * dataSize );
		const endianness = headerDataView.getUint32( 0, true );
		const littleEndian = endianness === 0x04030201;

		this.glType = headerDataView.getUint32( 1 * dataSize, littleEndian ); // must be 0 for compressed textures
		this.glTypeSize = headerDataView.getUint32( 2 * dataSize, littleEndian ); // must be 1 for compressed textures
		this.glFormat = headerDataView.getUint32( 3 * dataSize, littleEndian ); // must be 0 for compressed textures
		this.glInternalFormat = headerDataView.getUint32( 4 * dataSize, littleEndian ); // the value of arg passed to gl.compressedTexImage2D(,,x,,,,)
		this.glBaseInternalFormat = headerDataView.getUint32( 5 * dataSize, littleEndian ); // specify GL_RGB, GL_RGBA, GL_ALPHA, etc (un-compressed only)
		this.pixelWidth = headerDataView.getUint32( 6 * dataSize, littleEndian ); // level 0 value of arg passed to gl.compressedTexImage2D(,,,x,,,)
		this.pixelHeight = headerDataView.getUint32( 7 * dataSize, littleEndian ); // level 0 value of arg passed to gl.compressedTexImage2D(,,,,x,,)
		this.pixelDepth = headerDataView.getUint32( 8 * dataSize, littleEndian ); // level 0 value of arg passed to gl.compressedTexImage3D(,,,,,x,,)
		this.numberOfArrayElements = headerDataView.getUint32( 9 * dataSize, littleEndian ); // used for texture arrays
		this.numberOfFaces = headerDataView.getUint32( 10 * dataSize, littleEndian ); // used for cubemap textures, should either be 1 or 6
		this.numberOfMipmapLevels = headerDataView.getUint32( 11 * dataSize, littleEndian ); // number of levels; disregard possibility of 0 for compressed textures
		this.bytesOfKeyValueData = headerDataView.getUint32( 12 * dataSize, littleEndian ); // the amount of space after the header for meta-data

		// Make sure we have a compressed type.  Not only reduces work, but probably better to let dev know they are not compressing.
		if ( this.glType !== 0 ) {

			console.warn( 'only compressed formats currently supported' );
			return;

		} else {

			// value of zero is an indication to generate mipmaps @ runtime.  Not usually allowed for compressed, so disregard.
			this.numberOfMipmapLevels = Math.max( 1, this.numberOfMipmapLevels );

		}

		if ( this.pixelHeight === 0 || this.pixelDepth !== 0 ) {

			console.warn( 'only 2D textures currently supported' );
			return;

		}

		if ( this.numberOfArrayElements !== 0 ) {

			console.warn( 'texture arrays not currently supported' );
			return;

		}

		if ( this.numberOfFaces !== facesExpected ) {

			console.warn( 'number of faces expected' + facesExpected + ', but found ' + this.numberOfFaces );
			return;

		}

		// we now have a completely validated file, so could use existence of loadType as success
		// would need to make this more elaborate & adjust checks above to support more than one load type
		this.loadType = COMPRESSED_2D;

	}

	mipmaps( loadMipmaps ) {

		const mipmaps = [];

		// initialize width & height for level 1
		let dataOffset = HEADER_LEN + this.bytesOfKeyValueData;
		let width = this.pixelWidth;
		let height = this.pixelHeight;
		const mipmapCount = loadMipmaps ? this.numberOfMipmapLevels : 1;

		for ( let level = 0; level < mipmapCount; level ++ ) {

			const imageSize = new Int32Array( this.arrayBuffer, dataOffset, 1 )[ 0 ]; // size per face, since not supporting array cubemaps
			dataOffset += 4; // size of the image + 4 for the imageSize field

			for ( let face = 0; face < this.numberOfFaces; face ++ ) {

				const byteArray = new Uint8Array( this.arrayBuffer, dataOffset, imageSize );

				mipmaps.push( { 'data': byteArray, 'width': width, 'height': height } );

				dataOffset += imageSize;
				dataOffset += 3 - ( ( imageSize + 3 ) % 4 ); // add padding for odd sized image

			}

			width = Math.max( 1.0, width * 0.5 );
			height = Math.max( 1.0, height * 0.5 );

		}

		return mipmaps;

	}

}
```
</details>

#### Methods

##### `mipmaps(loadMipmaps: any): { data: Uint8Array<ArrayBuffer>; width: number; height: number; }[]`

<details><summary>Code</summary>

```ts
mipmaps( loadMipmaps ) {

		const mipmaps = [];

		// initialize width & height for level 1
		let dataOffset = HEADER_LEN + this.bytesOfKeyValueData;
		let width = this.pixelWidth;
		let height = this.pixelHeight;
		const mipmapCount = loadMipmaps ? this.numberOfMipmapLevels : 1;

		for ( let level = 0; level < mipmapCount; level ++ ) {

			const imageSize = new Int32Array( this.arrayBuffer, dataOffset, 1 )[ 0 ]; // size per face, since not supporting array cubemaps
			dataOffset += 4; // size of the image + 4 for the imageSize field

			for ( let face = 0; face < this.numberOfFaces; face ++ ) {

				const byteArray = new Uint8Array( this.arrayBuffer, dataOffset, imageSize );

				mipmaps.push( { 'data': byteArray, 'width': width, 'height': height } );

				dataOffset += imageSize;
				dataOffset += 3 - ( ( imageSize + 3 ) % 4 ); // add padding for odd sized image

			}

			width = Math.max( 1.0, width * 0.5 );
			height = Math.max( 1.0, height * 0.5 );

		}

		return mipmaps;

	}
```
</details>


---