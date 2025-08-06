[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Loader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/loaders/Loader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DefaultLoadingManager` | `./LoadingManager.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |


---

## Functions

### `Loader.load(): void`

**JSDoc:**
```typescript
/**
	 * This method needs to be implemented by all concrete loaders. It holds the
	 * logic for loading assets from the backend.
	 *
	 * @abstract
	 * @param {string} url - The path/URL of the file to be loaded.
	 * @param {Function} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} [onProgress] - Executed while the loading is in progress.
	 * @param {onErrorCallback} [onError] - Executed when errors occur.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
load( /* url, onLoad, onProgress, onError */ ) {}
```
</details>

### `Loader.loadAsync(url: string, onProgress: onProgressCallback): Promise<any>`

**JSDoc:**
```typescript
/**
	 * A async version of {@link Loader#load}.
	 *
	 * @param {string} url - The path/URL of the file to be loaded.
	 * @param {onProgressCallback} [onProgress] - Executed while the loading is in progress.
	 * @return {Promise} A Promise that resolves when the asset has been loaded.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onProgress`** `onProgressCallback`

**Returns:** `Promise<any>`

**Calls:**

- `scope.load`

<details><summary>Code</summary>

```typescript
loadAsync( url, onProgress ) {

		const scope = this;

		return new Promise( function ( resolve, reject ) {

			scope.load( url, resolve, onProgress, reject );

		} );

	}
```
</details>

### `Loader.parse(): void`

**JSDoc:**
```typescript
/**
	 * This method needs to be implemented by all concrete loaders. It holds the
	 * logic for parsing the asset into three.js entities.
	 *
	 * @abstract
	 * @param {any} data - The data to parse.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
parse( /* data */ ) {}
```
</details>

### `Loader.setCrossOrigin(crossOrigin: string): Loader`

**JSDoc:**
```typescript
/**
	 * Sets the `crossOrigin` String to implement CORS for loading the URL
	 * from a different domain that allows CORS.
	 *
	 * @param {string} crossOrigin - The `crossOrigin` value.
	 * @return {Loader} A reference to this instance.
	 */
```

**Parameters:**

- **`crossOrigin`** `string`

**Returns:** `Loader`

<details><summary>Code</summary>

```typescript
setCrossOrigin( crossOrigin ) {

		this.crossOrigin = crossOrigin;
		return this;

	}
```
</details>

### `Loader.setWithCredentials(value: boolean): Loader`

**JSDoc:**
```typescript
/**
	 * Whether the XMLHttpRequest uses credentials such as cookies, authorization
	 * headers or TLS client certificates, see [XMLHttpRequest.withCredentials]{@link https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/withCredentials}.
	 *
	 * Note: This setting has no effect if you are loading files locally or from the same domain.
	 *
	 * @param {boolean} value - The `withCredentials` value.
	 * @return {Loader} A reference to this instance.
	 */
```

**Parameters:**

- **`value`** `boolean`

**Returns:** `Loader`

<details><summary>Code</summary>

```typescript
setWithCredentials( value ) {

		this.withCredentials = value;
		return this;

	}
```
</details>

### `Loader.setPath(path: string): Loader`

**JSDoc:**
```typescript
/**
	 * Sets the base path for the asset.
	 *
	 * @param {string} path - The base path.
	 * @return {Loader} A reference to this instance.
	 */
```

**Parameters:**

- **`path`** `string`

**Returns:** `Loader`

<details><summary>Code</summary>

```typescript
setPath( path ) {

		this.path = path;
		return this;

	}
```
</details>

### `Loader.setResourcePath(resourcePath: string): Loader`

**JSDoc:**
```typescript
/**
	 * Sets the base path for dependent resources like textures.
	 *
	 * @param {string} resourcePath - The resource path.
	 * @return {Loader} A reference to this instance.
	 */
```

**Parameters:**

- **`resourcePath`** `string`

**Returns:** `Loader`

<details><summary>Code</summary>

```typescript
setResourcePath( resourcePath ) {

		this.resourcePath = resourcePath;
		return this;

	}
```
</details>

### `Loader.setRequestHeader(requestHeader: any): Loader`

**JSDoc:**
```typescript
/**
	 * Sets the given request header.
	 *
	 * @param {Object} requestHeader - A [request header]{@link https://developer.mozilla.org/en-US/docs/Glossary/Request_header}
	 * for configuring the HTTP request.
	 * @return {Loader} A reference to this instance.
	 */
```

**Parameters:**

- **`requestHeader`** `any`

**Returns:** `Loader`

<details><summary>Code</summary>

```typescript
setRequestHeader( requestHeader ) {

		this.requestHeader = requestHeader;
		return this;

	}
```
</details>

### `Loader.abort(): Loader`

**JSDoc:**
```typescript
/**
	 * This method can be implemented in loaders for aborting ongoing requests.
	 *
	 * @abstract
	 * @return {Loader} A reference to this instance.
	 */
```

**Returns:** `Loader`

<details><summary>Code</summary>

```typescript
abort() {

		return this;

	}
```
</details>


---

## Classes

### `Loader`

<details><summary>Class Code</summary>

```ts
class Loader {

	/**
	 * Constructs a new loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		/**
		 * The loading manager.
		 *
		 * @type {LoadingManager}
		 * @default DefaultLoadingManager
		 */
		this.manager = ( manager !== undefined ) ? manager : DefaultLoadingManager;

		/**
		 * The crossOrigin string to implement CORS for loading the url from a
		 * different domain that allows CORS.
		 *
		 * @type {string}
		 * @default 'anonymous'
		 */
		this.crossOrigin = 'anonymous';

		/**
		 * Whether the XMLHttpRequest uses credentials.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.withCredentials = false;

		/**
		 * The base path from which the asset will be loaded.
		 *
		 * @type {string}
		 */
		this.path = '';

		/**
		 * The base path from which additional resources like textures will be loaded.
		 *
		 * @type {string}
		 */
		this.resourcePath = '';

		/**
		 * The [request header]{@link https://developer.mozilla.org/en-US/docs/Glossary/Request_header}
		 * used in HTTP request.
		 *
		 * @type {Object<string, any>}
		 */
		this.requestHeader = {};

	}

	/**
	 * This method needs to be implemented by all concrete loaders. It holds the
	 * logic for loading assets from the backend.
	 *
	 * @abstract
	 * @param {string} url - The path/URL of the file to be loaded.
	 * @param {Function} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} [onProgress] - Executed while the loading is in progress.
	 * @param {onErrorCallback} [onError] - Executed when errors occur.
	 */
	load( /* url, onLoad, onProgress, onError */ ) {}

	/**
	 * A async version of {@link Loader#load}.
	 *
	 * @param {string} url - The path/URL of the file to be loaded.
	 * @param {onProgressCallback} [onProgress] - Executed while the loading is in progress.
	 * @return {Promise} A Promise that resolves when the asset has been loaded.
	 */
	loadAsync( url, onProgress ) {

		const scope = this;

		return new Promise( function ( resolve, reject ) {

			scope.load( url, resolve, onProgress, reject );

		} );

	}

	/**
	 * This method needs to be implemented by all concrete loaders. It holds the
	 * logic for parsing the asset into three.js entities.
	 *
	 * @abstract
	 * @param {any} data - The data to parse.
	 */
	parse( /* data */ ) {}

	/**
	 * Sets the `crossOrigin` String to implement CORS for loading the URL
	 * from a different domain that allows CORS.
	 *
	 * @param {string} crossOrigin - The `crossOrigin` value.
	 * @return {Loader} A reference to this instance.
	 */
	setCrossOrigin( crossOrigin ) {

		this.crossOrigin = crossOrigin;
		return this;

	}

	/**
	 * Whether the XMLHttpRequest uses credentials such as cookies, authorization
	 * headers or TLS client certificates, see [XMLHttpRequest.withCredentials]{@link https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/withCredentials}.
	 *
	 * Note: This setting has no effect if you are loading files locally or from the same domain.
	 *
	 * @param {boolean} value - The `withCredentials` value.
	 * @return {Loader} A reference to this instance.
	 */
	setWithCredentials( value ) {

		this.withCredentials = value;
		return this;

	}

	/**
	 * Sets the base path for the asset.
	 *
	 * @param {string} path - The base path.
	 * @return {Loader} A reference to this instance.
	 */
	setPath( path ) {

		this.path = path;
		return this;

	}

	/**
	 * Sets the base path for dependent resources like textures.
	 *
	 * @param {string} resourcePath - The resource path.
	 * @return {Loader} A reference to this instance.
	 */
	setResourcePath( resourcePath ) {

		this.resourcePath = resourcePath;
		return this;

	}

	/**
	 * Sets the given request header.
	 *
	 * @param {Object} requestHeader - A [request header]{@link https://developer.mozilla.org/en-US/docs/Glossary/Request_header}
	 * for configuring the HTTP request.
	 * @return {Loader} A reference to this instance.
	 */
	setRequestHeader( requestHeader ) {

		this.requestHeader = requestHeader;
		return this;

	}

	/**
	 * This method can be implemented in loaders for aborting ongoing requests.
	 *
	 * @abstract
	 * @return {Loader} A reference to this instance.
	 */
	abort() {

		return this;

	}

}
```
</details>

#### Methods

##### `load(): void`

<details><summary>Code</summary>

```ts
load( /* url, onLoad, onProgress, onError */ ) {}
```
</details>

##### `loadAsync(url: string, onProgress: onProgressCallback): Promise<any>`

<details><summary>Code</summary>

```ts
loadAsync( url, onProgress ) {

		const scope = this;

		return new Promise( function ( resolve, reject ) {

			scope.load( url, resolve, onProgress, reject );

		} );

	}
```
</details>

##### `parse(): void`

<details><summary>Code</summary>

```ts
parse( /* data */ ) {}
```
</details>

##### `setCrossOrigin(crossOrigin: string): Loader`

<details><summary>Code</summary>

```ts
setCrossOrigin( crossOrigin ) {

		this.crossOrigin = crossOrigin;
		return this;

	}
```
</details>

##### `setWithCredentials(value: boolean): Loader`

<details><summary>Code</summary>

```ts
setWithCredentials( value ) {

		this.withCredentials = value;
		return this;

	}
```
</details>

##### `setPath(path: string): Loader`

<details><summary>Code</summary>

```ts
setPath( path ) {

		this.path = path;
		return this;

	}
```
</details>

##### `setResourcePath(resourcePath: string): Loader`

<details><summary>Code</summary>

```ts
setResourcePath( resourcePath ) {

		this.resourcePath = resourcePath;
		return this;

	}
```
</details>

##### `setRequestHeader(requestHeader: any): Loader`

<details><summary>Code</summary>

```ts
setRequestHeader( requestHeader ) {

		this.requestHeader = requestHeader;
		return this;

	}
```
</details>

##### `abort(): Loader`

<details><summary>Code</summary>

```ts
abort() {

		return this;

	}
```
</details>


---