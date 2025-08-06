[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LUTCubeLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 14 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/LUTCubeLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ClampToEdgeWrapping` | `three` |
| `Data3DTexture` | `three` |
| `FileLoader` | `three` |
| `LinearFilter` | `three` |
| `Loader` | `three` |
| `UnsignedByteType` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `regExpTitle` | `RegExp` | let/var | `/TITLE +"([^"]*)"/` | ✗ |
| `regExpSize` | `RegExp` | let/var | `/LUT_3D_SIZE +(\d+)/` | ✗ |
| `regExpDomainMin` | `RegExp` | let/var | `/DOMAIN_MIN +([\d.]+) +([\d.]+) +([\d.]+)/` | ✗ |
| `regExpDomainMax` | `RegExp` | let/var | `/DOMAIN_MAX +([\d.]+) +([\d.]+) +([\d.]+)/` | ✗ |
| `regExpDataPoints` | `RegExp` | let/var | `/^([\d.e+-]+) +([\d.e+-]+) +([\d.e+-]+) *$/gm` | ✗ |
| `title` | `string` | let/var | `( result !== null ) ? result[ 1 ] : null` | ✗ |
| `length` | `number` | let/var | `size ** 3 * 4` | ✗ |
| `data` | `Float32Array<ArrayBuffer> \| Uint8Arr...` | let/var | `this.type === UnsignedByteType ? new Uint8Array( length ) : new Float32Array(...` | ✗ |
| `domainMin` | `any` | let/var | `new Vector3( 0, 0, 0 )` | ✗ |
| `domainMax` | `any` | let/var | `new Vector3( 1, 1, 1 )` | ✗ |
| `scale` | `1 \| 255` | let/var | `this.type === UnsignedByteType ? 255 : 1` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `texture3D` | `any` | let/var | `new Data3DTexture()` | ✗ |


---

## Functions

### `LUTCubeLoader.setType(type: any): LUTCubeLoader`

**JSDoc:**
```typescript
/**
	 * Sets the texture type.
	 *
	 * @param {(UnsignedByteType|FloatType)} type - The texture type to set.
	 * @return {LUTCubeLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`type`** `any`

**Returns:** `LUTCubeLoader`

<details><summary>Code</summary>

```typescript
setType( type ) {

		this.type = type;

		return this;

	}
```
</details>

### `LUTCubeLoader.load(url: string, onLoad: (arg0: { title: string; size: number; domainMin: Vector3; domainMax: Vector3; texture3D: Data3DTexture; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded Cube LUT asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({title:string,size:number,domainMin:Vector3,domainMax:Vector3,texture3D:Data3DTexture})} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: { title: string; size: number; domainMin: Vector3; domainMax: Vector3; texture3D: Data3DTexture; }) => any`
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

### `LUTCubeLoader.parse(input: string): { title: string; size: number; domainMin: Vector3; domainMax: Vector3; texture3D: Data3DTexture; }`

**JSDoc:**
```typescript
/**
	 * Parses the given Cube LUT data and returns the resulting 3D data texture.
	 *
	 * @param {string} input - The raw Cube LUT data as a string.
	 * @return {{title:string,size:number,domainMin:Vector3,domainMax:Vector3,texture3D:Data3DTexture}} The parsed Cube LUT.
	 */
```

**Parameters:**

- **`input`** `string`

**Returns:** `{ title: string; size: number; domainMin: Vector3; domainMax: Vector3; texture3D: Data3DTexture; }`

**Calls:**

- `regExpTitle.exec`
- `regExpSize.exec`
- `Number`
- `regExpDomainMin.exec`
- `domainMin.set`
- `regExpDomainMax.exec`
- `domainMax.set`
- `regExpDataPoints.exec`

<details><summary>Code</summary>

```typescript
parse( input ) {

		const regExpTitle = /TITLE +"([^"]*)"/;
		const regExpSize = /LUT_3D_SIZE +(\d+)/;
		const regExpDomainMin = /DOMAIN_MIN +([\d.]+) +([\d.]+) +([\d.]+)/;
		const regExpDomainMax = /DOMAIN_MAX +([\d.]+) +([\d.]+) +([\d.]+)/;
		const regExpDataPoints = /^([\d.e+-]+) +([\d.e+-]+) +([\d.e+-]+) *$/gm;

		let result = regExpTitle.exec( input );
		const title = ( result !== null ) ? result[ 1 ] : null;

		result = regExpSize.exec( input );

		if ( result === null ) {

			throw new Error( 'LUTCubeLoader: Missing LUT_3D_SIZE information' );

		}

		const size = Number( result[ 1 ] );
		const length = size ** 3 * 4;
		const data = this.type === UnsignedByteType ? new Uint8Array( length ) : new Float32Array( length );

		const domainMin = new Vector3( 0, 0, 0 );
		const domainMax = new Vector3( 1, 1, 1 );

		result = regExpDomainMin.exec( input );

		if ( result !== null ) {

			domainMin.set( Number( result[ 1 ] ), Number( result[ 2 ] ), Number( result[ 3 ] ) );

		}

		result = regExpDomainMax.exec( input );

		if ( result !== null ) {

			domainMax.set( Number( result[ 1 ] ), Number( result[ 2 ] ), Number( result[ 3 ] ) );

		}

		if ( domainMin.x > domainMax.x || domainMin.y > domainMax.y || domainMin.z > domainMax.z ) {

			throw new Error( 'LUTCubeLoader: Invalid input domain' );

		}

		const scale = this.type === UnsignedByteType ? 255 : 1;
		let i = 0;

		while ( ( result = regExpDataPoints.exec( input ) ) !== null ) {

			data[ i ++ ] = Number( result[ 1 ] ) * scale;
			data[ i ++ ] = Number( result[ 2 ] ) * scale;
			data[ i ++ ] = Number( result[ 3 ] ) * scale;
			data[ i ++ ] = scale;

		}

		const texture3D = new Data3DTexture();
		texture3D.image.data = data;
		texture3D.image.width = size;
		texture3D.image.height = size;
		texture3D.image.depth = size;
		texture3D.type = this.type;
		texture3D.magFilter = LinearFilter;
		texture3D.minFilter = LinearFilter;
		texture3D.wrapS = ClampToEdgeWrapping;
		texture3D.wrapT = ClampToEdgeWrapping;
		texture3D.wrapR = ClampToEdgeWrapping;
		texture3D.generateMipmaps = false;
		texture3D.needsUpdate = true;

		return {
			title,
			size,
			domainMin,
			domainMax,
			texture3D,
		};

	}
```
</details>


---

## Classes

### `LUTCubeLoader`

<details><summary>Class Code</summary>

```ts
export class LUTCubeLoader extends Loader {

	/**
	 * Constructs a new Cube LUT loader.
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
	 * @return {LUTCubeLoader} A reference to this loader.
	 */
	setType( type ) {

		this.type = type;

		return this;

	}

	/**
	 * Starts loading from the given URL and passes the loaded Cube LUT asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({title:string,size:number,domainMin:Vector3,domainMax:Vector3,texture3D:Data3DTexture})} onLoad - Executed when the loading process has been finished.
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
	 * Parses the given Cube LUT data and returns the resulting 3D data texture.
	 *
	 * @param {string} input - The raw Cube LUT data as a string.
	 * @return {{title:string,size:number,domainMin:Vector3,domainMax:Vector3,texture3D:Data3DTexture}} The parsed Cube LUT.
	 */
	parse( input ) {

		const regExpTitle = /TITLE +"([^"]*)"/;
		const regExpSize = /LUT_3D_SIZE +(\d+)/;
		const regExpDomainMin = /DOMAIN_MIN +([\d.]+) +([\d.]+) +([\d.]+)/;
		const regExpDomainMax = /DOMAIN_MAX +([\d.]+) +([\d.]+) +([\d.]+)/;
		const regExpDataPoints = /^([\d.e+-]+) +([\d.e+-]+) +([\d.e+-]+) *$/gm;

		let result = regExpTitle.exec( input );
		const title = ( result !== null ) ? result[ 1 ] : null;

		result = regExpSize.exec( input );

		if ( result === null ) {

			throw new Error( 'LUTCubeLoader: Missing LUT_3D_SIZE information' );

		}

		const size = Number( result[ 1 ] );
		const length = size ** 3 * 4;
		const data = this.type === UnsignedByteType ? new Uint8Array( length ) : new Float32Array( length );

		const domainMin = new Vector3( 0, 0, 0 );
		const domainMax = new Vector3( 1, 1, 1 );

		result = regExpDomainMin.exec( input );

		if ( result !== null ) {

			domainMin.set( Number( result[ 1 ] ), Number( result[ 2 ] ), Number( result[ 3 ] ) );

		}

		result = regExpDomainMax.exec( input );

		if ( result !== null ) {

			domainMax.set( Number( result[ 1 ] ), Number( result[ 2 ] ), Number( result[ 3 ] ) );

		}

		if ( domainMin.x > domainMax.x || domainMin.y > domainMax.y || domainMin.z > domainMax.z ) {

			throw new Error( 'LUTCubeLoader: Invalid input domain' );

		}

		const scale = this.type === UnsignedByteType ? 255 : 1;
		let i = 0;

		while ( ( result = regExpDataPoints.exec( input ) ) !== null ) {

			data[ i ++ ] = Number( result[ 1 ] ) * scale;
			data[ i ++ ] = Number( result[ 2 ] ) * scale;
			data[ i ++ ] = Number( result[ 3 ] ) * scale;
			data[ i ++ ] = scale;

		}

		const texture3D = new Data3DTexture();
		texture3D.image.data = data;
		texture3D.image.width = size;
		texture3D.image.height = size;
		texture3D.image.depth = size;
		texture3D.type = this.type;
		texture3D.magFilter = LinearFilter;
		texture3D.minFilter = LinearFilter;
		texture3D.wrapS = ClampToEdgeWrapping;
		texture3D.wrapT = ClampToEdgeWrapping;
		texture3D.wrapR = ClampToEdgeWrapping;
		texture3D.generateMipmaps = false;
		texture3D.needsUpdate = true;

		return {
			title,
			size,
			domainMin,
			domainMax,
			texture3D,
		};

	}

}
```
</details>

#### Methods

##### `setType(type: any): LUTCubeLoader`

<details><summary>Code</summary>

```ts
setType( type ) {

		this.type = type;

		return this;

	}
```
</details>

##### `load(url: string, onLoad: (arg0: { title: string; size: number; domainMin: Vector3; domainMax: Vector3; texture3D: Data3DTexture; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

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

##### `parse(input: string): { title: string; size: number; domainMin: Vector3; domainMax: Vector3; texture3D: Data3DTexture; }`

<details><summary>Code</summary>

```ts
parse( input ) {

		const regExpTitle = /TITLE +"([^"]*)"/;
		const regExpSize = /LUT_3D_SIZE +(\d+)/;
		const regExpDomainMin = /DOMAIN_MIN +([\d.]+) +([\d.]+) +([\d.]+)/;
		const regExpDomainMax = /DOMAIN_MAX +([\d.]+) +([\d.]+) +([\d.]+)/;
		const regExpDataPoints = /^([\d.e+-]+) +([\d.e+-]+) +([\d.e+-]+) *$/gm;

		let result = regExpTitle.exec( input );
		const title = ( result !== null ) ? result[ 1 ] : null;

		result = regExpSize.exec( input );

		if ( result === null ) {

			throw new Error( 'LUTCubeLoader: Missing LUT_3D_SIZE information' );

		}

		const size = Number( result[ 1 ] );
		const length = size ** 3 * 4;
		const data = this.type === UnsignedByteType ? new Uint8Array( length ) : new Float32Array( length );

		const domainMin = new Vector3( 0, 0, 0 );
		const domainMax = new Vector3( 1, 1, 1 );

		result = regExpDomainMin.exec( input );

		if ( result !== null ) {

			domainMin.set( Number( result[ 1 ] ), Number( result[ 2 ] ), Number( result[ 3 ] ) );

		}

		result = regExpDomainMax.exec( input );

		if ( result !== null ) {

			domainMax.set( Number( result[ 1 ] ), Number( result[ 2 ] ), Number( result[ 3 ] ) );

		}

		if ( domainMin.x > domainMax.x || domainMin.y > domainMax.y || domainMin.z > domainMax.z ) {

			throw new Error( 'LUTCubeLoader: Invalid input domain' );

		}

		const scale = this.type === UnsignedByteType ? 255 : 1;
		let i = 0;

		while ( ( result = regExpDataPoints.exec( input ) ) !== null ) {

			data[ i ++ ] = Number( result[ 1 ] ) * scale;
			data[ i ++ ] = Number( result[ 2 ] ) * scale;
			data[ i ++ ] = Number( result[ 3 ] ) * scale;
			data[ i ++ ] = scale;

		}

		const texture3D = new Data3DTexture();
		texture3D.image.data = data;
		texture3D.image.width = size;
		texture3D.image.height = size;
		texture3D.image.depth = size;
		texture3D.type = this.type;
		texture3D.magFilter = LinearFilter;
		texture3D.minFilter = LinearFilter;
		texture3D.wrapS = ClampToEdgeWrapping;
		texture3D.wrapT = ClampToEdgeWrapping;
		texture3D.wrapR = ClampToEdgeWrapping;
		texture3D.generateMipmaps = false;
		texture3D.needsUpdate = true;

		return {
			title,
			size,
			domainMin,
			domainMax,
			texture3D,
		};

	}
```
</details>


---