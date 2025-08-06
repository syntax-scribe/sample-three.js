[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `KMZLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/KMZLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `FileLoader` | `three` |
| `Group` | `three` |
| `Loader` | `three` |
| `LoadingManager` | `three` |
| `ColladaLoader` | `../loaders/ColladaLoader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( scope.manager )` | ✗ |
| `manager` | `any` | let/var | `new LoadingManager()` | ✗ |
| `blob` | `Blob` | let/var | `new Blob( [ image.buffer ], { type: 'application/octet-stream' } )` | ✗ |
| `loader` | `ColladaLoader` | let/var | `new ColladaLoader( manager )` | ✗ |
| `loader` | `ColladaLoader` | let/var | `new ColladaLoader( manager )` | ✗ |


---

## Functions

### `KMZLoader.load(url: string, onLoad: (arg0: { scene: Group; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded KMZ asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({scene:Group})} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: { scene: Group; }) => any`
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

### `KMZLoader.parse(data: ArrayBuffer): { scene: Group; }`

**JSDoc:**
```typescript
/**
	 * Parses the given KMZ data and returns an object holding the scene.
	 *
	 * @param {ArrayBuffer} data - The raw KMZ data as an array buffer.
	 * @return {{scene:Group}} The parsed KMZ asset.
	 */
```

**Parameters:**

- **`data`** `ArrayBuffer`

**Returns:** `{ scene: Group; }`

**Calls:**

- `path.slice`
- `manager.setURLModifier`
- `findFile`
- `console.log`
- `URL.createObjectURL`
- `fflate.unzipSync`
- `new DOMParser().parseFromString`
- `fflate.strFromU8`
- `xml.querySelector`
- `loader.parse`
- `console.warn`
- `path.split( '.' ).pop().toLowerCase`
- `console.error`

**Internal Comments:**
```
// (x2)
```

<details><summary>Code</summary>

```typescript
parse( data ) {

		function findFile( url ) {

			for ( const path in zip ) {

				if ( path.slice( - url.length ) === url ) {

					return zip[ path ];

				}

			}

		}

		const manager = new LoadingManager();
		manager.setURLModifier( function ( url ) {

			const image = findFile( url );

			if ( image ) {

				console.log( 'Loading', url );

				const blob = new Blob( [ image.buffer ], { type: 'application/octet-stream' } );
				return URL.createObjectURL( blob );

			}

			return url;

		} );

		//

		const zip = fflate.unzipSync( new Uint8Array( data ) );

		if ( zip[ 'doc.kml' ] ) {

			const xml = new DOMParser().parseFromString( fflate.strFromU8( zip[ 'doc.kml' ] ), 'application/xml' );

			const model = xml.querySelector( 'Placemark Model Link href' );

			if ( model ) {

				const loader = new ColladaLoader( manager );
				return loader.parse( fflate.strFromU8( zip[ model.textContent ] ) );

			}

		} else {

			console.warn( 'KMZLoader: Missing doc.kml file.' );

			for ( const path in zip ) {

				const extension = path.split( '.' ).pop().toLowerCase();

				if ( extension === 'dae' ) {

					const loader = new ColladaLoader( manager );
					return loader.parse( fflate.strFromU8( zip[ path ] ) );

				}

			}

		}

		console.error( 'KMZLoader: Couldn\'t find .dae file.' );
		return { scene: new Group() };

	}
```
</details>

### `findFile(url: any): any`

**Parameters:**

- **`url`** `any`

**Returns:** `any`

**Calls:**

- `path.slice`

<details><summary>Code</summary>

```typescript
function findFile( url ) {

			for ( const path in zip ) {

				if ( path.slice( - url.length ) === url ) {

					return zip[ path ];

				}

			}

		}
```
</details>


---

## Classes

### `KMZLoader`

<details><summary>Class Code</summary>

```ts
class KMZLoader extends Loader {

	/**
	 * Constructs a new KMZ loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

	}

	/**
	 * Starts loading from the given URL and passes the loaded KMZ asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({scene:Group})} onLoad - Executed when the loading process has been finished.
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
	 * Parses the given KMZ data and returns an object holding the scene.
	 *
	 * @param {ArrayBuffer} data - The raw KMZ data as an array buffer.
	 * @return {{scene:Group}} The parsed KMZ asset.
	 */
	parse( data ) {

		function findFile( url ) {

			for ( const path in zip ) {

				if ( path.slice( - url.length ) === url ) {

					return zip[ path ];

				}

			}

		}

		const manager = new LoadingManager();
		manager.setURLModifier( function ( url ) {

			const image = findFile( url );

			if ( image ) {

				console.log( 'Loading', url );

				const blob = new Blob( [ image.buffer ], { type: 'application/octet-stream' } );
				return URL.createObjectURL( blob );

			}

			return url;

		} );

		//

		const zip = fflate.unzipSync( new Uint8Array( data ) );

		if ( zip[ 'doc.kml' ] ) {

			const xml = new DOMParser().parseFromString( fflate.strFromU8( zip[ 'doc.kml' ] ), 'application/xml' );

			const model = xml.querySelector( 'Placemark Model Link href' );

			if ( model ) {

				const loader = new ColladaLoader( manager );
				return loader.parse( fflate.strFromU8( zip[ model.textContent ] ) );

			}

		} else {

			console.warn( 'KMZLoader: Missing doc.kml file.' );

			for ( const path in zip ) {

				const extension = path.split( '.' ).pop().toLowerCase();

				if ( extension === 'dae' ) {

					const loader = new ColladaLoader( manager );
					return loader.parse( fflate.strFromU8( zip[ path ] ) );

				}

			}

		}

		console.error( 'KMZLoader: Couldn\'t find .dae file.' );
		return { scene: new Group() };

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: { scene: Group; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

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

##### `parse(data: ArrayBuffer): { scene: Group; }`

<details><summary>Code</summary>

```ts
parse( data ) {

		function findFile( url ) {

			for ( const path in zip ) {

				if ( path.slice( - url.length ) === url ) {

					return zip[ path ];

				}

			}

		}

		const manager = new LoadingManager();
		manager.setURLModifier( function ( url ) {

			const image = findFile( url );

			if ( image ) {

				console.log( 'Loading', url );

				const blob = new Blob( [ image.buffer ], { type: 'application/octet-stream' } );
				return URL.createObjectURL( blob );

			}

			return url;

		} );

		//

		const zip = fflate.unzipSync( new Uint8Array( data ) );

		if ( zip[ 'doc.kml' ] ) {

			const xml = new DOMParser().parseFromString( fflate.strFromU8( zip[ 'doc.kml' ] ), 'application/xml' );

			const model = xml.querySelector( 'Placemark Model Link href' );

			if ( model ) {

				const loader = new ColladaLoader( manager );
				return loader.parse( fflate.strFromU8( zip[ model.textContent ] ) );

			}

		} else {

			console.warn( 'KMZLoader: Missing doc.kml file.' );

			for ( const path in zip ) {

				const extension = path.split( '.' ).pop().toLowerCase();

				if ( extension === 'dae' ) {

					const loader = new ColladaLoader( manager );
					return loader.parse( fflate.strFromU8( zip[ path ] ) );

				}

			}

		}

		console.error( 'KMZLoader: Couldn\'t find .dae file.' );
		return { scene: new Group() };

	}
```
</details>


---