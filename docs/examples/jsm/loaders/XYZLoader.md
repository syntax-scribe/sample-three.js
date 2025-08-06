[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `XYZLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/XYZLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `three` |
| `Color` | `three` |
| `FileLoader` | `three` |
| `Float32BufferAttribute` | `three` |
| `Loader` | `three` |
| `SRGBColorSpace` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `colors` | `any[]` | let/var | `[]` | ✗ |
| `color` | `any` | let/var | `new Color()` | ✗ |
| `r` | `number` | let/var | `parseFloat( lineValues[ 3 ] ) / 255` | ✗ |
| `g` | `number` | let/var | `parseFloat( lineValues[ 4 ] ) / 255` | ✗ |
| `b` | `number` | let/var | `parseFloat( lineValues[ 5 ] ) / 255` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |


---

## Functions

### `XYZLoader.load(url: string, onLoad: (arg0: BufferGeometry) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded XYZ asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(BufferGeometry)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: BufferGeometry) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `loader.setPath`
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

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
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

### `XYZLoader.parse(text: string): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Parses the given XYZ data and returns the resulting geometry.
	 *
	 * @param {string} text - The raw XYZ data as a string.
	 * @return {BufferGeometry} The geometry representing the point cloud.
	 */
```

**Parameters:**

- **`text`** `string`

**Returns:** `BufferGeometry`

**Calls:**

- `text.split`
- `line.trim`
- `line.charAt`
- `line.split`
- `vertices.push`
- `parseFloat`
- `color.setRGB`
- `colors.push`
- `geometry.setAttribute`

**Internal Comments:**
```
// XYZ (x4)
// XYZRGB (x4)
```

<details><summary>Code</summary>

```typescript
parse( text ) {

		const lines = text.split( '\n' );

		const vertices = [];
		const colors = [];
		const color = new Color();

		for ( let line of lines ) {

			line = line.trim();

			if ( line.charAt( 0 ) === '#' ) continue; // skip comments

			const lineValues = line.split( /\s+/ );

			if ( lineValues.length === 3 ) {

				// XYZ

				vertices.push( parseFloat( lineValues[ 0 ] ) );
				vertices.push( parseFloat( lineValues[ 1 ] ) );
				vertices.push( parseFloat( lineValues[ 2 ] ) );

			}

			if ( lineValues.length === 6 ) {

				// XYZRGB

				vertices.push( parseFloat( lineValues[ 0 ] ) );
				vertices.push( parseFloat( lineValues[ 1 ] ) );
				vertices.push( parseFloat( lineValues[ 2 ] ) );

				const r = parseFloat( lineValues[ 3 ] ) / 255;
				const g = parseFloat( lineValues[ 4 ] ) / 255;
				const b = parseFloat( lineValues[ 5 ] ) / 255;

				color.setRGB( r, g, b, SRGBColorSpace );

				colors.push( color.r, color.g, color.b );

			}

		}

		const geometry = new BufferGeometry();
		geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );

		if ( colors.length > 0 ) {

			geometry.setAttribute( 'color', new Float32BufferAttribute( colors, 3 ) );

		}

		return geometry;

	}
```
</details>


---

## Classes

### `XYZLoader`

<details><summary>Class Code</summary>

```ts
class XYZLoader extends Loader {

	/**
	 * Starts loading from the given URL and passes the loaded XYZ asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(BufferGeometry)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
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
	 * Parses the given XYZ data and returns the resulting geometry.
	 *
	 * @param {string} text - The raw XYZ data as a string.
	 * @return {BufferGeometry} The geometry representing the point cloud.
	 */
	parse( text ) {

		const lines = text.split( '\n' );

		const vertices = [];
		const colors = [];
		const color = new Color();

		for ( let line of lines ) {

			line = line.trim();

			if ( line.charAt( 0 ) === '#' ) continue; // skip comments

			const lineValues = line.split( /\s+/ );

			if ( lineValues.length === 3 ) {

				// XYZ

				vertices.push( parseFloat( lineValues[ 0 ] ) );
				vertices.push( parseFloat( lineValues[ 1 ] ) );
				vertices.push( parseFloat( lineValues[ 2 ] ) );

			}

			if ( lineValues.length === 6 ) {

				// XYZRGB

				vertices.push( parseFloat( lineValues[ 0 ] ) );
				vertices.push( parseFloat( lineValues[ 1 ] ) );
				vertices.push( parseFloat( lineValues[ 2 ] ) );

				const r = parseFloat( lineValues[ 3 ] ) / 255;
				const g = parseFloat( lineValues[ 4 ] ) / 255;
				const b = parseFloat( lineValues[ 5 ] ) / 255;

				color.setRGB( r, g, b, SRGBColorSpace );

				colors.push( color.r, color.g, color.b );

			}

		}

		const geometry = new BufferGeometry();
		geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );

		if ( colors.length > 0 ) {

			geometry.setAttribute( 'color', new Float32BufferAttribute( colors, 3 ) );

		}

		return geometry;

	}

}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: BufferGeometry) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( this.manager );
		loader.setPath( this.path );
		loader.setRequestHeader( this.requestHeader );
		loader.setWithCredentials( this.withCredentials );
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

##### `parse(text: string): BufferGeometry`

<details><summary>Code</summary>

```ts
parse( text ) {

		const lines = text.split( '\n' );

		const vertices = [];
		const colors = [];
		const color = new Color();

		for ( let line of lines ) {

			line = line.trim();

			if ( line.charAt( 0 ) === '#' ) continue; // skip comments

			const lineValues = line.split( /\s+/ );

			if ( lineValues.length === 3 ) {

				// XYZ

				vertices.push( parseFloat( lineValues[ 0 ] ) );
				vertices.push( parseFloat( lineValues[ 1 ] ) );
				vertices.push( parseFloat( lineValues[ 2 ] ) );

			}

			if ( lineValues.length === 6 ) {

				// XYZRGB

				vertices.push( parseFloat( lineValues[ 0 ] ) );
				vertices.push( parseFloat( lineValues[ 1 ] ) );
				vertices.push( parseFloat( lineValues[ 2 ] ) );

				const r = parseFloat( lineValues[ 3 ] ) / 255;
				const g = parseFloat( lineValues[ 4 ] ) / 255;
				const b = parseFloat( lineValues[ 5 ] ) / 255;

				color.setRGB( r, g, b, SRGBColorSpace );

				colors.push( color.r, color.g, color.b );

			}

		}

		const geometry = new BufferGeometry();
		geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );

		if ( colors.length > 0 ) {

			geometry.setAttribute( 'color', new Float32BufferAttribute( colors, 3 ) );

		}

		return geometry;

	}
```
</details>


---