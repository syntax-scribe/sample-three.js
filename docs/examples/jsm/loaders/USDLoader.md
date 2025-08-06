[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `USDLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/USDLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `FileLoader` | `three` |
| `Loader` | `three` |
| `USDAParser` | `./usd/USDAParser.js` |
| `USDCParser` | `./usd/USDCParser.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( scope.manager )` | ✗ |
| `usda` | `USDAParser` | let/var | `new USDAParser()` | ✗ |
| `usdc` | `USDCParser` | let/var | `new USDCParser()` | ✗ |
| `data` | `{}` | let/var | `{}` | ✗ |
| `loader` | `any` | let/var | `new FileLoader()` | ✗ |
| `blob` | `Blob` | let/var | `new Blob( [ zip[ filename ] ], { type: 'image/png' } )` | ✗ |
| `crateHeader` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( [ 0x50, 0x58, 0x52, 0x2D, 0x55, 0x53, 0x44, 0x43 ] )` | ✗ |
| `view` | `Uint8Array<any>` | let/var | `new Uint8Array( buffer, 0, crateHeader.length )` | ✗ |
| `firstFileName` | `string` | let/var | `Object.keys( zip )[ 0 ]` | ✗ |
| `isCrate` | `boolean` | let/var | `false` | ✗ |


---

## Functions

### `USDLoader.load(url: string, onLoad: (arg0: Group) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded USDZ asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Group)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: Group) => any`
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
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

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

### `USDLoader.parse(buffer: string | ArrayBuffer): Group`

**JSDoc:**
```typescript
/**
	 * Parses the given USDZ data and returns the resulting group.
	 *
	 * @param {ArrayBuffer|string} buffer - The raw USDZ data as an array buffer.
	 * @return {Group} The parsed asset as a group.
	 */
```

**Parameters:**

- **`buffer`** `string | ArrayBuffer`

**Returns:** `Group`

**Calls:**

- `loader.setResponseType`
- `filename.endsWith`
- `URL.createObjectURL`
- `isCrateFile`
- `usdc.parse`
- `fflate.strFromU8`
- `usda.parseText`
- `Object.keys`
- `firstFileName.endsWith`
- `usda.parse`
- `fflate.unzipSync`
- `parseAssets`
- `findUSD`

**Internal Comments:**
```
// As per the USD specification, the first entry in the zip archive is used as the main file ("UsdStage").
// ASCII files can end in either .usda or .usd.
// See https://openusd.org/release/spec_usdz.html#layout
// If this is not a crate file, we assume it is a plain USDA file.
// USDA
// USDC
// USDZ (x2)
// console.log( assets ); (x2)
```

<details><summary>Code</summary>

```typescript
parse( buffer ) {

		const usda = new USDAParser();
		const usdc = new USDCParser();

		function parseAssets( zip ) {

			const data = {};
			const loader = new FileLoader();
			loader.setResponseType( 'arraybuffer' );

			for ( const filename in zip ) {

				if ( filename.endsWith( 'png' ) ) {

					const blob = new Blob( [ zip[ filename ] ], { type: 'image/png' } );
					data[ filename ] = URL.createObjectURL( blob );

				}

				if ( filename.endsWith( 'usd' ) || filename.endsWith( 'usda' ) || filename.endsWith( 'usdc' ) ) {

					if ( isCrateFile( zip[ filename ] ) ) {

						data[ filename ] = usdc.parse( zip[ filename ].buffer, data );

					} else {

						const text = fflate.strFromU8( zip[ filename ] );
						data[ filename ] = usda.parseText( text );

					}

				}

			}

			return data;

		}

		function isCrateFile( buffer ) {

			const crateHeader = new Uint8Array( [ 0x50, 0x58, 0x52, 0x2D, 0x55, 0x53, 0x44, 0x43 ] ); // PXR-USDC

			if ( buffer.byteLength < crateHeader.length ) return false;

			const view = new Uint8Array( buffer, 0, crateHeader.length );

			for ( let i = 0; i < crateHeader.length; i ++ ) {

				if ( view[ i ] !== crateHeader[ i ] ) return false;

			}

			return true;

		}

		function findUSD( zip ) {

			if ( zip.length < 1 ) return undefined;

			const firstFileName = Object.keys( zip )[ 0 ];
			let isCrate = false;

			// As per the USD specification, the first entry in the zip archive is used as the main file ("UsdStage").
			// ASCII files can end in either .usda or .usd.
			// See https://openusd.org/release/spec_usdz.html#layout
			if ( firstFileName.endsWith( 'usda' ) ) return zip[ firstFileName ];

			if ( firstFileName.endsWith( 'usdc' ) ) {

				isCrate = true;

			} else if ( firstFileName.endsWith( 'usd' ) ) {

				// If this is not a crate file, we assume it is a plain USDA file.
				if ( ! isCrateFile( zip[ firstFileName ] ) ) {

					return zip[ firstFileName ];

				} else {

					isCrate = true;

				}

			}

			if ( isCrate ) {

				return zip[ firstFileName ];

			}

		}

		// USDA

		if ( typeof buffer === 'string' ) {

			return usda.parse( buffer, {} );

		}

		// USDC

		if ( isCrateFile( buffer ) ) {

			return usdc.parse( buffer );

		}

		// USDZ

		const zip = fflate.unzipSync( new Uint8Array( buffer ) );

		const assets = parseAssets( zip );

		// console.log( assets );

		const file = findUSD( zip );

		const text = fflate.strFromU8( file );

		return usda.parse( text, assets );

	}
```
</details>

### `parseAssets(zip: any): {}`

**Parameters:**

- **`zip`** `any`

**Returns:** `{}`

**Calls:**

- `loader.setResponseType`
- `filename.endsWith`
- `URL.createObjectURL`
- `isCrateFile`
- `usdc.parse`
- `fflate.strFromU8`
- `usda.parseText`

<details><summary>Code</summary>

```typescript
function parseAssets( zip ) {

			const data = {};
			const loader = new FileLoader();
			loader.setResponseType( 'arraybuffer' );

			for ( const filename in zip ) {

				if ( filename.endsWith( 'png' ) ) {

					const blob = new Blob( [ zip[ filename ] ], { type: 'image/png' } );
					data[ filename ] = URL.createObjectURL( blob );

				}

				if ( filename.endsWith( 'usd' ) || filename.endsWith( 'usda' ) || filename.endsWith( 'usdc' ) ) {

					if ( isCrateFile( zip[ filename ] ) ) {

						data[ filename ] = usdc.parse( zip[ filename ].buffer, data );

					} else {

						const text = fflate.strFromU8( zip[ filename ] );
						data[ filename ] = usda.parseText( text );

					}

				}

			}

			return data;

		}
```
</details>

### `isCrateFile(buffer: any): boolean`

**Parameters:**

- **`buffer`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isCrateFile( buffer ) {

			const crateHeader = new Uint8Array( [ 0x50, 0x58, 0x52, 0x2D, 0x55, 0x53, 0x44, 0x43 ] ); // PXR-USDC

			if ( buffer.byteLength < crateHeader.length ) return false;

			const view = new Uint8Array( buffer, 0, crateHeader.length );

			for ( let i = 0; i < crateHeader.length; i ++ ) {

				if ( view[ i ] !== crateHeader[ i ] ) return false;

			}

			return true;

		}
```
</details>

### `findUSD(zip: any): any`

**Parameters:**

- **`zip`** `any`

**Returns:** `any`

**Calls:**

- `Object.keys`
- `firstFileName.endsWith`
- `isCrateFile`

**Internal Comments:**
```
// As per the USD specification, the first entry in the zip archive is used as the main file ("UsdStage").
// ASCII files can end in either .usda or .usd.
// See https://openusd.org/release/spec_usdz.html#layout
// If this is not a crate file, we assume it is a plain USDA file.
```

<details><summary>Code</summary>

```typescript
function findUSD( zip ) {

			if ( zip.length < 1 ) return undefined;

			const firstFileName = Object.keys( zip )[ 0 ];
			let isCrate = false;

			// As per the USD specification, the first entry in the zip archive is used as the main file ("UsdStage").
			// ASCII files can end in either .usda or .usd.
			// See https://openusd.org/release/spec_usdz.html#layout
			if ( firstFileName.endsWith( 'usda' ) ) return zip[ firstFileName ];

			if ( firstFileName.endsWith( 'usdc' ) ) {

				isCrate = true;

			} else if ( firstFileName.endsWith( 'usd' ) ) {

				// If this is not a crate file, we assume it is a plain USDA file.
				if ( ! isCrateFile( zip[ firstFileName ] ) ) {

					return zip[ firstFileName ];

				} else {

					isCrate = true;

				}

			}

			if ( isCrate ) {

				return zip[ firstFileName ];

			}

		}
```
</details>


---

## Classes

### `USDLoader`

<details><summary>Class Code</summary>

```ts
class USDLoader extends Loader {

	/**
	 * Constructs a new USDZ loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Starts loading from the given URL and passes the loaded USDZ asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Group)} onLoad - Executed when the loading process has been finished.
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
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

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
	 * Parses the given USDZ data and returns the resulting group.
	 *
	 * @param {ArrayBuffer|string} buffer - The raw USDZ data as an array buffer.
	 * @return {Group} The parsed asset as a group.
	 */
	parse( buffer ) {

		const usda = new USDAParser();
		const usdc = new USDCParser();

		function parseAssets( zip ) {

			const data = {};
			const loader = new FileLoader();
			loader.setResponseType( 'arraybuffer' );

			for ( const filename in zip ) {

				if ( filename.endsWith( 'png' ) ) {

					const blob = new Blob( [ zip[ filename ] ], { type: 'image/png' } );
					data[ filename ] = URL.createObjectURL( blob );

				}

				if ( filename.endsWith( 'usd' ) || filename.endsWith( 'usda' ) || filename.endsWith( 'usdc' ) ) {

					if ( isCrateFile( zip[ filename ] ) ) {

						data[ filename ] = usdc.parse( zip[ filename ].buffer, data );

					} else {

						const text = fflate.strFromU8( zip[ filename ] );
						data[ filename ] = usda.parseText( text );

					}

				}

			}

			return data;

		}

		function isCrateFile( buffer ) {

			const crateHeader = new Uint8Array( [ 0x50, 0x58, 0x52, 0x2D, 0x55, 0x53, 0x44, 0x43 ] ); // PXR-USDC

			if ( buffer.byteLength < crateHeader.length ) return false;

			const view = new Uint8Array( buffer, 0, crateHeader.length );

			for ( let i = 0; i < crateHeader.length; i ++ ) {

				if ( view[ i ] !== crateHeader[ i ] ) return false;

			}

			return true;

		}

		function findUSD( zip ) {

			if ( zip.length < 1 ) return undefined;

			const firstFileName = Object.keys( zip )[ 0 ];
			let isCrate = false;

			// As per the USD specification, the first entry in the zip archive is used as the main file ("UsdStage").
			// ASCII files can end in either .usda or .usd.
			// See https://openusd.org/release/spec_usdz.html#layout
			if ( firstFileName.endsWith( 'usda' ) ) return zip[ firstFileName ];

			if ( firstFileName.endsWith( 'usdc' ) ) {

				isCrate = true;

			} else if ( firstFileName.endsWith( 'usd' ) ) {

				// If this is not a crate file, we assume it is a plain USDA file.
				if ( ! isCrateFile( zip[ firstFileName ] ) ) {

					return zip[ firstFileName ];

				} else {

					isCrate = true;

				}

			}

			if ( isCrate ) {

				return zip[ firstFileName ];

			}

		}

		// USDA

		if ( typeof buffer === 'string' ) {

			return usda.parse( buffer, {} );

		}

		// USDC

		if ( isCrateFile( buffer ) ) {

			return usdc.parse( buffer );

		}

		// USDZ

		const zip = fflate.unzipSync( new Uint8Array( buffer ) );

		const assets = parseAssets( zip );

		// console.log( assets );

		const file = findUSD( zip );

		const text = fflate.strFromU8( file );

		return usda.parse( text, assets );

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: Group) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setResponseType( 'arraybuffer' );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

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

##### `parse(buffer: string | ArrayBuffer): Group`

<details><summary>Code</summary>

```ts
parse( buffer ) {

		const usda = new USDAParser();
		const usdc = new USDCParser();

		function parseAssets( zip ) {

			const data = {};
			const loader = new FileLoader();
			loader.setResponseType( 'arraybuffer' );

			for ( const filename in zip ) {

				if ( filename.endsWith( 'png' ) ) {

					const blob = new Blob( [ zip[ filename ] ], { type: 'image/png' } );
					data[ filename ] = URL.createObjectURL( blob );

				}

				if ( filename.endsWith( 'usd' ) || filename.endsWith( 'usda' ) || filename.endsWith( 'usdc' ) ) {

					if ( isCrateFile( zip[ filename ] ) ) {

						data[ filename ] = usdc.parse( zip[ filename ].buffer, data );

					} else {

						const text = fflate.strFromU8( zip[ filename ] );
						data[ filename ] = usda.parseText( text );

					}

				}

			}

			return data;

		}

		function isCrateFile( buffer ) {

			const crateHeader = new Uint8Array( [ 0x50, 0x58, 0x52, 0x2D, 0x55, 0x53, 0x44, 0x43 ] ); // PXR-USDC

			if ( buffer.byteLength < crateHeader.length ) return false;

			const view = new Uint8Array( buffer, 0, crateHeader.length );

			for ( let i = 0; i < crateHeader.length; i ++ ) {

				if ( view[ i ] !== crateHeader[ i ] ) return false;

			}

			return true;

		}

		function findUSD( zip ) {

			if ( zip.length < 1 ) return undefined;

			const firstFileName = Object.keys( zip )[ 0 ];
			let isCrate = false;

			// As per the USD specification, the first entry in the zip archive is used as the main file ("UsdStage").
			// ASCII files can end in either .usda or .usd.
			// See https://openusd.org/release/spec_usdz.html#layout
			if ( firstFileName.endsWith( 'usda' ) ) return zip[ firstFileName ];

			if ( firstFileName.endsWith( 'usdc' ) ) {

				isCrate = true;

			} else if ( firstFileName.endsWith( 'usd' ) ) {

				// If this is not a crate file, we assume it is a plain USDA file.
				if ( ! isCrateFile( zip[ firstFileName ] ) ) {

					return zip[ firstFileName ];

				} else {

					isCrate = true;

				}

			}

			if ( isCrate ) {

				return zip[ firstFileName ];

			}

		}

		// USDA

		if ( typeof buffer === 'string' ) {

			return usda.parse( buffer, {} );

		}

		// USDC

		if ( isCrateFile( buffer ) ) {

			return usdc.parse( buffer );

		}

		// USDZ

		const zip = fflate.unzipSync( new Uint8Array( buffer ) );

		const assets = parseAssets( zip );

		// console.log( assets );

		const file = findUSD( zip );

		const text = fflate.strFromU8( file );

		return usda.parse( text, assets );

	}
```
</details>


---