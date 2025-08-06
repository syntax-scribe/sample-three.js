[⬅️ Back to Table of Contents](../index.md)

# 📄 `sw.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📊 Variables & Constants | 8 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/sw.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `cacheName` | `"threejs-editor"` | let/var | `'threejs-editor'` | ✗ |
| `assets` | `string[]` | let/var | `[ './', './manifest.json', './images/icon.png', '../files/favicon.ico', '../b...` | ✗ |
| `cache` | `Cache` | let/var | `await caches.open( cacheName )` | ✗ |
| `request` | `any` | let/var | `event.request` | ✗ |
| `response` | `Response` | let/var | `await fetch( request )` | ✗ |
| `newHeaders` | `Headers` | let/var | `new Headers( response.headers )` | ✗ |
| `cache` | `Cache` | let/var | `await caches.open( cacheName )` | ✗ |
| `cachedResponse` | `Response` | let/var | `await caches.match( request )` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `networkFirst` | fetch( request ), caches.open( cacheName ), caches.match( request ) | *none* |


---

## Functions

### `networkFirst(request: any): Promise<Response>`

**Parameters:**

- **`request`** `any`

**Returns:** `Promise<Response>`

**Calls:**

- `fetch`
- `request.url.endsWith`
- `newHeaders.set`
- `caches.open`
- `cache.put`
- `response.clone`
- `caches.match`
- `console.warn`

<details><summary>Code</summary>

```typescript
async function networkFirst( request ) {

	try {

		let response = await fetch( request );

		if ( request.url.endsWith( 'editor/' ) || request.url.endsWith( 'editor/index.html' ) ) { // copied from coi-serviceworker

			const newHeaders = new Headers( response.headers );
			newHeaders.set( 'Cross-Origin-Embedder-Policy', 'require-corp' );
			newHeaders.set( 'Cross-Origin-Opener-Policy', 'same-origin' );

			response = new Response( response.body, { status: response.status, statusText: response.statusText, headers: newHeaders } );

		}

		if ( request.method === 'GET' ) {

			const cache = await caches.open( cacheName );
			cache.put( request, response.clone() );

		}

		return response;

	} catch {

		const cachedResponse = await caches.match( request );

		if ( cachedResponse === undefined ) {

			console.warn( '[SW] Not cached:', request.url );

		}

		return cachedResponse;

	}

}
```
</details>


---