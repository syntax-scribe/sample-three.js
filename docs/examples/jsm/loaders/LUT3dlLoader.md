[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LUT3dlLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 19 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/LUT3dlLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ClampToEdgeWrapping` | `three` |
| `Data3DTexture` | `three` |
| `FileLoader` | `three` |
| `LinearFilter` | `three` |
| `Loader` | `three` |
| `RGBAFormat` | `three` |
| `UnsignedByteType` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `regExpGridInfo` | `RegExp` | let/var | `/^[\d ]+$/m` | ✗ |
| `regExpDataPoints` | `RegExp` | let/var | `/^([\d.e+-]+) +([\d.e+-]+) +([\d.e+-]+) *$/gm` | ✗ |
| `gridStep` | `number` | let/var | `gridLines[ 1 ] - gridLines[ 0 ]` | ✗ |
| `size` | `number` | let/var | `gridLines.length` | ✗ |
| `sizeSq` | `number` | let/var | `size ** 2` | ✗ |
| `dataFloat` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( size ** 3 * 4 )` | ✗ |
| `maxValue` | `number` | let/var | `0.0` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `bLayer` | `number` | let/var | `index % size` | ✗ |
| `gLayer` | `number` | let/var | `Math.floor( index / size ) % size` | ✗ |
| `rLayer` | `number` | let/var | `Math.floor( index / ( sizeSq ) ) % size` | ✗ |
| `d4` | `number` | let/var | `( bLayer * sizeSq + gLayer * size + rLayer ) * 4` | ✗ |
| `data` | `Float32Array<ArrayBuffer> \| Uint8Arr...` | let/var | `this.type === UnsignedByteType ? new Uint8Array( dataFloat.length ) : dataFloat` | ✗ |
| `scale` | `1 \| 255` | let/var | `this.type === UnsignedByteType ? 255 : 1` | ✗ |
| `i1` | `number` | let/var | `i + 1` | ✗ |
| `i2` | `number` | let/var | `i + 2` | ✗ |
| `i3` | `number` | let/var | `i + 3` | ✗ |
| `texture3D` | `any` | let/var | `new Data3DTexture()` | ✗ |


---

## Functions

### `LUT3dlLoader.setType(type: any): LUT3dlLoader`

**JSDoc:**
```typescript
/**
	 * Sets the texture type.
	 *
	 * @param {(UnsignedByteType|FloatType)} type - The texture type to set.
	 * @return {LUT3dlLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`type`** `any`

**Returns:** `LUT3dlLoader`

<details><summary>Code</summary>

```typescript
setType( type ) {

		this.type = type;

		return this;

	}
```
</details>

### `LUT3dlLoader.load(url: string, onLoad: (arg0: { size: number; texture3D: Data3DTexture; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded 3DL LUT asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({size:number,texture3D:Data3DTexture})} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: { size: number; texture3D: Data3DTexture; }) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `loader.setPath`
- `loader.setResponseType`
- `loader.load`
- `onLoad`
- `this.parse`
- `onError`
- `console.error`
- `this.manager.itemError`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setResponseType( 'text' );
		loader.load( url, text => {

			try {

				onLoad( this.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				this.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

### `LUT3dlLoader.parse(input: string): { size: number; texture3D: Data3DTexture; }`

**JSDoc:**
```typescript
/**
	 * Parses the given 3DL LUT data and returns the resulting 3D data texture.
	 *
	 * @param {string} input - The raw 3DL LUT data as a string.
	 * @return {{size:number,texture3D:Data3DTexture}} The parsed 3DL LUT.
	 */
```

**Parameters:**

- **`input`** `string`

**Returns:** `{ size: number; texture3D: Data3DTexture; }`

**Calls:**

- `regExpGridInfo.exec`
- `result[ 0 ].trim().split( /\s+/g ).map`
- `regExpDataPoints.exec`
- `Number`
- `Math.max`
- `Math.floor`
- `Math.ceil`
- `Math.log2`
- `Math.pow`

**Internal Comments:**
```
// The first line describes the positions of values on the LUT grid. (x2)
// b grows first, then g, then r. (x2)
// Determine the bit depth to scale the values to [0.0, 1.0]. (x2)
// Note: data is dataFloat when type is FloatType. (x4)
```

<details><summary>Code</summary>

```typescript
parse( input ) {

		const regExpGridInfo = /^[\d ]+$/m;
		const regExpDataPoints = /^([\d.e+-]+) +([\d.e+-]+) +([\d.e+-]+) *$/gm;

		// The first line describes the positions of values on the LUT grid.
		let result = regExpGridInfo.exec( input );

		if ( result === null ) {

			throw new Error( 'LUT3dlLoader: Missing grid information' );

		}

		const gridLines = result[ 0 ].trim().split( /\s+/g ).map( Number );
		const gridStep = gridLines[ 1 ] - gridLines[ 0 ];
		const size = gridLines.length;
		const sizeSq = size ** 2;

		for ( let i = 1, l = gridLines.length; i < l; ++ i ) {

			if ( gridStep !== ( gridLines[ i ] - gridLines[ i - 1 ] ) ) {

				throw new Error( 'LUT3dlLoader: Inconsistent grid size' );

			}

		}

		const dataFloat = new Float32Array( size ** 3 * 4 );
		let maxValue = 0.0;
		let index = 0;

		while ( ( result = regExpDataPoints.exec( input ) ) !== null ) {

			const r = Number( result[ 1 ] );
			const g = Number( result[ 2 ] );
			const b = Number( result[ 3 ] );

			maxValue = Math.max( maxValue, r, g, b );

			const bLayer = index % size;
			const gLayer = Math.floor( index / size ) % size;
			const rLayer = Math.floor( index / ( sizeSq ) ) % size;

			// b grows first, then g, then r.
			const d4 = ( bLayer * sizeSq + gLayer * size + rLayer ) * 4;
			dataFloat[ d4 + 0 ] = r;
			dataFloat[ d4 + 1 ] = g;
			dataFloat[ d4 + 2 ] = b;

			++ index;

		}

		// Determine the bit depth to scale the values to [0.0, 1.0].
		const bits = Math.ceil( Math.log2( maxValue ) );
		const maxBitValue = Math.pow( 2, bits );

		const data = this.type === UnsignedByteType ? new Uint8Array( dataFloat.length ) : dataFloat;
		const scale = this.type === UnsignedByteType ? 255 : 1;

		for ( let i = 0, l = data.length; i < l; i += 4 ) {

			const i1 = i + 1;
			const i2 = i + 2;
			const i3 = i + 3;

			// Note: data is dataFloat when type is FloatType.
			data[ i ] = dataFloat[ i ] / maxBitValue * scale;
			data[ i1 ] = dataFloat[ i1 ] / maxBitValue * scale;
			data[ i2 ] = dataFloat[ i2 ] / maxBitValue * scale;
			data[ i3 ] = scale;

		}

		const texture3D = new Data3DTexture();
		texture3D.image.data = data;
		texture3D.image.width = size;
		texture3D.image.height = size;
		texture3D.image.depth = size;
		texture3D.format = RGBAFormat;
		texture3D.type = this.type;
		texture3D.magFilter = LinearFilter;
		texture3D.minFilter = LinearFilter;
		texture3D.wrapS = ClampToEdgeWrapping;
		texture3D.wrapT = ClampToEdgeWrapping;
		texture3D.wrapR = ClampToEdgeWrapping;
		texture3D.generateMipmaps = false;
		texture3D.needsUpdate = true;

		return {
			size,
			texture3D,
		};

	}
```
</details>


---

## Classes

### `LUT3dlLoader`

<details><summary>Class Code</summary>

```ts
export class LUT3dlLoader extends Loader {

	/**
	 * Constructs a new 3DL LUT loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		/**
		 * The texture type.
		 *
		 * @type {(UnsignedByteType|FloatType)}
		 * @default UnsignedByteType
		 */
		this.type = UnsignedByteType;

	}

	/**
	 * Sets the texture type.
	 *
	 * @param {(UnsignedByteType|FloatType)} type - The texture type to set.
	 * @return {LUT3dlLoader} A reference to this loader.
	 */
	setType( type ) {

		this.type = type;

		return this;

	}

	/**
	 * Starts loading from the given URL and passes the loaded 3DL LUT asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({size:number,texture3D:Data3DTexture})} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setResponseType( 'text' );
		loader.load( url, text => {

			try {

				onLoad( this.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				this.manager.itemError( url );

			}

		}, onProgress, onError );

	}

	/**
	 * Parses the given 3DL LUT data and returns the resulting 3D data texture.
	 *
	 * @param {string} input - The raw 3DL LUT data as a string.
	 * @return {{size:number,texture3D:Data3DTexture}} The parsed 3DL LUT.
	 */
	parse( input ) {

		const regExpGridInfo = /^[\d ]+$/m;
		const regExpDataPoints = /^([\d.e+-]+) +([\d.e+-]+) +([\d.e+-]+) *$/gm;

		// The first line describes the positions of values on the LUT grid.
		let result = regExpGridInfo.exec( input );

		if ( result === null ) {

			throw new Error( 'LUT3dlLoader: Missing grid information' );

		}

		const gridLines = result[ 0 ].trim().split( /\s+/g ).map( Number );
		const gridStep = gridLines[ 1 ] - gridLines[ 0 ];
		const size = gridLines.length;
		const sizeSq = size ** 2;

		for ( let i = 1, l = gridLines.length; i < l; ++ i ) {

			if ( gridStep !== ( gridLines[ i ] - gridLines[ i - 1 ] ) ) {

				throw new Error( 'LUT3dlLoader: Inconsistent grid size' );

			}

		}

		const dataFloat = new Float32Array( size ** 3 * 4 );
		let maxValue = 0.0;
		let index = 0;

		while ( ( result = regExpDataPoints.exec( input ) ) !== null ) {

			const r = Number( result[ 1 ] );
			const g = Number( result[ 2 ] );
			const b = Number( result[ 3 ] );

			maxValue = Math.max( maxValue, r, g, b );

			const bLayer = index % size;
			const gLayer = Math.floor( index / size ) % size;
			const rLayer = Math.floor( index / ( sizeSq ) ) % size;

			// b grows first, then g, then r.
			const d4 = ( bLayer * sizeSq + gLayer * size + rLayer ) * 4;
			dataFloat[ d4 + 0 ] = r;
			dataFloat[ d4 + 1 ] = g;
			dataFloat[ d4 + 2 ] = b;

			++ index;

		}

		// Determine the bit depth to scale the values to [0.0, 1.0].
		const bits = Math.ceil( Math.log2( maxValue ) );
		const maxBitValue = Math.pow( 2, bits );

		const data = this.type === UnsignedByteType ? new Uint8Array( dataFloat.length ) : dataFloat;
		const scale = this.type === UnsignedByteType ? 255 : 1;

		for ( let i = 0, l = data.length; i < l; i += 4 ) {

			const i1 = i + 1;
			const i2 = i + 2;
			const i3 = i + 3;

			// Note: data is dataFloat when type is FloatType.
			data[ i ] = dataFloat[ i ] / maxBitValue * scale;
			data[ i1 ] = dataFloat[ i1 ] / maxBitValue * scale;
			data[ i2 ] = dataFloat[ i2 ] / maxBitValue * scale;
			data[ i3 ] = scale;

		}

		const texture3D = new Data3DTexture();
		texture3D.image.data = data;
		texture3D.image.width = size;
		texture3D.image.height = size;
		texture3D.image.depth = size;
		texture3D.format = RGBAFormat;
		texture3D.type = this.type;
		texture3D.magFilter = LinearFilter;
		texture3D.minFilter = LinearFilter;
		texture3D.wrapS = ClampToEdgeWrapping;
		texture3D.wrapT = ClampToEdgeWrapping;
		texture3D.wrapR = ClampToEdgeWrapping;
		texture3D.generateMipmaps = false;
		texture3D.needsUpdate = true;

		return {
			size,
			texture3D,
		};

	}

}
```
</details>

#### Methods

##### `setType(type: any): LUT3dlLoader`

<details><summary>Code</summary>

```ts
setType( type ) {

		this.type = type;

		return this;

	}
```
</details>

##### `load(url: string, onLoad: (arg0: { size: number; texture3D: Data3DTexture; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setResponseType( 'text' );
		loader.load( url, text => {

			try {

				onLoad( this.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				this.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

##### `parse(input: string): { size: number; texture3D: Data3DTexture; }`

<details><summary>Code</summary>

```ts
parse( input ) {

		const regExpGridInfo = /^[\d ]+$/m;
		const regExpDataPoints = /^([\d.e+-]+) +([\d.e+-]+) +([\d.e+-]+) *$/gm;

		// The first line describes the positions of values on the LUT grid.
		let result = regExpGridInfo.exec( input );

		if ( result === null ) {

			throw new Error( 'LUT3dlLoader: Missing grid information' );

		}

		const gridLines = result[ 0 ].trim().split( /\s+/g ).map( Number );
		const gridStep = gridLines[ 1 ] - gridLines[ 0 ];
		const size = gridLines.length;
		const sizeSq = size ** 2;

		for ( let i = 1, l = gridLines.length; i < l; ++ i ) {

			if ( gridStep !== ( gridLines[ i ] - gridLines[ i - 1 ] ) ) {

				throw new Error( 'LUT3dlLoader: Inconsistent grid size' );

			}

		}

		const dataFloat = new Float32Array( size ** 3 * 4 );
		let maxValue = 0.0;
		let index = 0;

		while ( ( result = regExpDataPoints.exec( input ) ) !== null ) {

			const r = Number( result[ 1 ] );
			const g = Number( result[ 2 ] );
			const b = Number( result[ 3 ] );

			maxValue = Math.max( maxValue, r, g, b );

			const bLayer = index % size;
			const gLayer = Math.floor( index / size ) % size;
			const rLayer = Math.floor( index / ( sizeSq ) ) % size;

			// b grows first, then g, then r.
			const d4 = ( bLayer * sizeSq + gLayer * size + rLayer ) * 4;
			dataFloat[ d4 + 0 ] = r;
			dataFloat[ d4 + 1 ] = g;
			dataFloat[ d4 + 2 ] = b;

			++ index;

		}

		// Determine the bit depth to scale the values to [0.0, 1.0].
		const bits = Math.ceil( Math.log2( maxValue ) );
		const maxBitValue = Math.pow( 2, bits );

		const data = this.type === UnsignedByteType ? new Uint8Array( dataFloat.length ) : dataFloat;
		const scale = this.type === UnsignedByteType ? 255 : 1;

		for ( let i = 0, l = data.length; i < l; i += 4 ) {

			const i1 = i + 1;
			const i2 = i + 2;
			const i3 = i + 3;

			// Note: data is dataFloat when type is FloatType.
			data[ i ] = dataFloat[ i ] / maxBitValue * scale;
			data[ i1 ] = dataFloat[ i1 ] / maxBitValue * scale;
			data[ i2 ] = dataFloat[ i2 ] / maxBitValue * scale;
			data[ i3 ] = scale;

		}

		const texture3D = new Data3DTexture();
		texture3D.image.data = data;
		texture3D.image.width = size;
		texture3D.image.height = size;
		texture3D.image.depth = size;
		texture3D.format = RGBAFormat;
		texture3D.type = this.type;
		texture3D.magFilter = LinearFilter;
		texture3D.minFilter = LinearFilter;
		texture3D.wrapS = ClampToEdgeWrapping;
		texture3D.wrapT = ClampToEdgeWrapping;
		texture3D.wrapR = ClampToEdgeWrapping;
		texture3D.generateMipmaps = false;
		texture3D.needsUpdate = true;

		return {
			size,
			texture3D,
		};

	}
```
</details>


---