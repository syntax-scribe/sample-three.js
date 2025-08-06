[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Storage.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 17 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Storage.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `indexedDB` | `IDBFactory` | let/var | `window.indexedDB` | ✗ |
| `name` | `"threejs-editor"` | let/var | `'threejs-editor'` | ✗ |
| `version` | `1` | let/var | `1` | ✗ |
| `database` | `any` | let/var | `*not shown*` | ✗ |
| `db` | `any` | let/var | `event.target.result` | ✗ |


---

## Functions

### `Storage(): { init: (callback: any) => void; get: (callback: any) => void; set: (data: any) => void; clear: () => void; }`

**Returns:** `{ init: (callback: any) => void; get: (callback: any) => void; set: (data: any) => void; clear: () => void; }`

**Calls:**

- `console.warn`
- `indexedDB.open`
- `db.objectStoreNames.contains`
- `db.createObjectStore`
- `callback`
- `console.error`
- `database.transaction`
- `transaction.objectStore`
- `objectStore.get`
- `performance.now`
- `objectStore.put`
- `console.log`
- `/\d\d\:\d\d\:\d\d/.exec`
- `( performance.now() - start ).toFixed`
- `objectStore.clear`

<details><summary>Code</summary>

```typescript
function Storage() {

	const indexedDB = window.indexedDB;

	if ( indexedDB === undefined ) {

		console.warn( 'Storage: IndexedDB not available.' );
		return { init: function () {}, get: function () {}, set: function () {}, clear: function () {} };

	}

	const name = 'threejs-editor';
	const version = 1;

	let database;

	return {

		init: function ( callback ) {

			const request = indexedDB.open( name, version );
			request.onupgradeneeded = function ( event ) {

				const db = event.target.result;

				if ( db.objectStoreNames.contains( 'states' ) === false ) {

					db.createObjectStore( 'states' );

				}

			};

			request.onsuccess = function ( event ) {

				database = event.target.result;

				callback();

			};

			request.onerror = function ( event ) {

				console.error( 'IndexedDB', event );

			};


		},

		get: function ( callback ) {

			const transaction = database.transaction( [ 'states' ], 'readonly' );
			const objectStore = transaction.objectStore( 'states' );
			const request = objectStore.get( 0 );
			request.onsuccess = function ( event ) {

				callback( event.target.result );

			};

		},

		set: function ( data ) {

			const start = performance.now();

			const transaction = database.transaction( [ 'states' ], 'readwrite' );
			const objectStore = transaction.objectStore( 'states' );
			const request = objectStore.put( data, 0 );
			request.onsuccess = function () {

				console.log( '[' + /\d\d\:\d\d\:\d\d/.exec( new Date() )[ 0 ] + ']', 'Saved state to IndexedDB. ' + ( performance.now() - start ).toFixed( 2 ) + 'ms' );

			};

		},

		clear: function () {

			if ( database === undefined ) return;

			const transaction = database.transaction( [ 'states' ], 'readwrite' );
			const objectStore = transaction.objectStore( 'states' );
			const request = objectStore.clear();
			request.onsuccess = function () {

				console.log( '[' + /\d\d\:\d\d\:\d\d/.exec( new Date() )[ 0 ] + ']', 'Cleared IndexedDB.' );

			};

		}

	};

}
```
</details>

### `init(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `get(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `set(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `clear(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `init(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `get(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `set(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `clear(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {}
```
</details>

### `init(callback: any): void`

**Parameters:**

- **`callback`** `any`

**Returns:** `void`

**Calls:**

- `indexedDB.open`
- `db.objectStoreNames.contains`
- `db.createObjectStore`
- `callback`
- `console.error`

<details><summary>Code</summary>

```typescript
function ( callback ) {

			const request = indexedDB.open( name, version );
			request.onupgradeneeded = function ( event ) {

				const db = event.target.result;

				if ( db.objectStoreNames.contains( 'states' ) === false ) {

					db.createObjectStore( 'states' );

				}

			};

			request.onsuccess = function ( event ) {

				database = event.target.result;

				callback();

			};

			request.onerror = function ( event ) {

				console.error( 'IndexedDB', event );

			};


		}
```
</details>

### `get(callback: any): void`

**Parameters:**

- **`callback`** `any`

**Returns:** `void`

**Calls:**

- `database.transaction`
- `transaction.objectStore`
- `objectStore.get`
- `callback`

<details><summary>Code</summary>

```typescript
function ( callback ) {

			const transaction = database.transaction( [ 'states' ], 'readonly' );
			const objectStore = transaction.objectStore( 'states' );
			const request = objectStore.get( 0 );
			request.onsuccess = function ( event ) {

				callback( event.target.result );

			};

		}
```
</details>

### `set(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `performance.now`
- `database.transaction`
- `transaction.objectStore`
- `objectStore.put`
- `console.log`
- `/\d\d\:\d\d\:\d\d/.exec`
- `( performance.now() - start ).toFixed`

<details><summary>Code</summary>

```typescript
function ( data ) {

			const start = performance.now();

			const transaction = database.transaction( [ 'states' ], 'readwrite' );
			const objectStore = transaction.objectStore( 'states' );
			const request = objectStore.put( data, 0 );
			request.onsuccess = function () {

				console.log( '[' + /\d\d\:\d\d\:\d\d/.exec( new Date() )[ 0 ] + ']', 'Saved state to IndexedDB. ' + ( performance.now() - start ).toFixed( 2 ) + 'ms' );

			};

		}
```
</details>

### `clear(): void`

**Returns:** `void`

**Calls:**

- `database.transaction`
- `transaction.objectStore`
- `objectStore.clear`
- `console.log`
- `/\d\d\:\d\d\:\d\d/.exec`

<details><summary>Code</summary>

```typescript
function () {

			if ( database === undefined ) return;

			const transaction = database.transaction( [ 'states' ], 'readwrite' );
			const objectStore = transaction.objectStore( 'states' );
			const request = objectStore.clear();
			request.onsuccess = function () {

				console.log( '[' + /\d\d\:\d\d\:\d\d/.exec( new Date() )[ 0 ] + ']', 'Cleared IndexedDB.' );

			};

		}
```
</details>

### `init(callback: any): void`

**Parameters:**

- **`callback`** `any`

**Returns:** `void`

**Calls:**

- `indexedDB.open`
- `db.objectStoreNames.contains`
- `db.createObjectStore`
- `callback`
- `console.error`

<details><summary>Code</summary>

```typescript
function ( callback ) {

			const request = indexedDB.open( name, version );
			request.onupgradeneeded = function ( event ) {

				const db = event.target.result;

				if ( db.objectStoreNames.contains( 'states' ) === false ) {

					db.createObjectStore( 'states' );

				}

			};

			request.onsuccess = function ( event ) {

				database = event.target.result;

				callback();

			};

			request.onerror = function ( event ) {

				console.error( 'IndexedDB', event );

			};


		}
```
</details>

### `get(callback: any): void`

**Parameters:**

- **`callback`** `any`

**Returns:** `void`

**Calls:**

- `database.transaction`
- `transaction.objectStore`
- `objectStore.get`
- `callback`

<details><summary>Code</summary>

```typescript
function ( callback ) {

			const transaction = database.transaction( [ 'states' ], 'readonly' );
			const objectStore = transaction.objectStore( 'states' );
			const request = objectStore.get( 0 );
			request.onsuccess = function ( event ) {

				callback( event.target.result );

			};

		}
```
</details>

### `set(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `performance.now`
- `database.transaction`
- `transaction.objectStore`
- `objectStore.put`
- `console.log`
- `/\d\d\:\d\d\:\d\d/.exec`
- `( performance.now() - start ).toFixed`

<details><summary>Code</summary>

```typescript
function ( data ) {

			const start = performance.now();

			const transaction = database.transaction( [ 'states' ], 'readwrite' );
			const objectStore = transaction.objectStore( 'states' );
			const request = objectStore.put( data, 0 );
			request.onsuccess = function () {

				console.log( '[' + /\d\d\:\d\d\:\d\d/.exec( new Date() )[ 0 ] + ']', 'Saved state to IndexedDB. ' + ( performance.now() - start ).toFixed( 2 ) + 'ms' );

			};

		}
```
</details>

### `clear(): void`

**Returns:** `void`

**Calls:**

- `database.transaction`
- `transaction.objectStore`
- `objectStore.clear`
- `console.log`
- `/\d\d\:\d\d\:\d\d/.exec`

<details><summary>Code</summary>

```typescript
function () {

			if ( database === undefined ) return;

			const transaction = database.transaction( [ 'states' ], 'readwrite' );
			const objectStore = transaction.objectStore( 'states' );
			const request = objectStore.clear();
			request.onsuccess = function () {

				console.log( '[' + /\d\d\:\d\d\:\d\d/.exec( new Date() )[ 0 ] + ']', 'Cleared IndexedDB.' );

			};

		}
```
</details>


---