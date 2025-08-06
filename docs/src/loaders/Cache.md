[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Cache.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 24 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/loaders/Cache.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `Cache` | `{ enabled: boolean; files: { [x: stri...` | let/var | `{ /** * Whether caching is enabled or not. * * @static * @type {boolean} * @d...` | ✗ |


---

## Functions

### `add(key: string, file: any): void`

**Parameters:**

- **`key`** `string`
- **`file`** `any`

**Returns:** `void`

**Internal Comments:**
```
// console.log( 'THREE.Cache', 'Adding key:', key ); (x5)
```

<details><summary>Code</summary>

```typescript
function ( key, file ) {

		if ( this.enabled === false ) return;

		// console.log( 'THREE.Cache', 'Adding key:', key );

		this.files[ key ] = file;

	}
```
</details>

### `get(key: string): any`

**Parameters:**

- **`key`** `string`

**Returns:** `any`

**Internal Comments:**
```
// console.log( 'THREE.Cache', 'Checking key:', key );
```

<details><summary>Code</summary>

```typescript
function ( key ) {

		if ( this.enabled === false ) return;

		// console.log( 'THREE.Cache', 'Checking key:', key );

		return this.files[ key ];

	}
```
</details>

### `remove(key: string): void`

**Parameters:**

- **`key`** `string`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( key ) {

		delete this.files[ key ];

	}
```
</details>

### `clear(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

		this.files = {};

	}
```
</details>

### `add(key: string, file: any): void`

**Parameters:**

- **`key`** `string`
- **`file`** `any`

**Returns:** `void`

**Internal Comments:**
```
// console.log( 'THREE.Cache', 'Adding key:', key ); (x5)
```

<details><summary>Code</summary>

```typescript
function ( key, file ) {

		if ( this.enabled === false ) return;

		// console.log( 'THREE.Cache', 'Adding key:', key );

		this.files[ key ] = file;

	}
```
</details>

### `get(key: string): any`

**Parameters:**

- **`key`** `string`

**Returns:** `any`

**Internal Comments:**
```
// console.log( 'THREE.Cache', 'Checking key:', key );
```

<details><summary>Code</summary>

```typescript
function ( key ) {

		if ( this.enabled === false ) return;

		// console.log( 'THREE.Cache', 'Checking key:', key );

		return this.files[ key ];

	}
```
</details>

### `remove(key: string): void`

**Parameters:**

- **`key`** `string`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( key ) {

		delete this.files[ key ];

	}
```
</details>

### `clear(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

		this.files = {};

	}
```
</details>

### `add(key: string, file: any): void`

**Parameters:**

- **`key`** `string`
- **`file`** `any`

**Returns:** `void`

**Internal Comments:**
```
// console.log( 'THREE.Cache', 'Adding key:', key ); (x5)
```

<details><summary>Code</summary>

```typescript
function ( key, file ) {

		if ( this.enabled === false ) return;

		// console.log( 'THREE.Cache', 'Adding key:', key );

		this.files[ key ] = file;

	}
```
</details>

### `get(key: string): any`

**Parameters:**

- **`key`** `string`

**Returns:** `any`

**Internal Comments:**
```
// console.log( 'THREE.Cache', 'Checking key:', key );
```

<details><summary>Code</summary>

```typescript
function ( key ) {

		if ( this.enabled === false ) return;

		// console.log( 'THREE.Cache', 'Checking key:', key );

		return this.files[ key ];

	}
```
</details>

### `remove(key: string): void`

**Parameters:**

- **`key`** `string`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( key ) {

		delete this.files[ key ];

	}
```
</details>

### `clear(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

		this.files = {};

	}
```
</details>

### `add(key: string, file: any): void`

**Parameters:**

- **`key`** `string`
- **`file`** `any`

**Returns:** `void`

**Internal Comments:**
```
// console.log( 'THREE.Cache', 'Adding key:', key ); (x5)
```

<details><summary>Code</summary>

```typescript
function ( key, file ) {

		if ( this.enabled === false ) return;

		// console.log( 'THREE.Cache', 'Adding key:', key );

		this.files[ key ] = file;

	}
```
</details>

### `get(key: string): any`

**Parameters:**

- **`key`** `string`

**Returns:** `any`

**Internal Comments:**
```
// console.log( 'THREE.Cache', 'Checking key:', key );
```

<details><summary>Code</summary>

```typescript
function ( key ) {

		if ( this.enabled === false ) return;

		// console.log( 'THREE.Cache', 'Checking key:', key );

		return this.files[ key ];

	}
```
</details>

### `remove(key: string): void`

**Parameters:**

- **`key`** `string`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( key ) {

		delete this.files[ key ];

	}
```
</details>

### `clear(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

		this.files = {};

	}
```
</details>

### `add(key: string, file: any): void`

**Parameters:**

- **`key`** `string`
- **`file`** `any`

**Returns:** `void`

**Internal Comments:**
```
// console.log( 'THREE.Cache', 'Adding key:', key ); (x5)
```

<details><summary>Code</summary>

```typescript
function ( key, file ) {

		if ( this.enabled === false ) return;

		// console.log( 'THREE.Cache', 'Adding key:', key );

		this.files[ key ] = file;

	}
```
</details>

### `get(key: string): any`

**Parameters:**

- **`key`** `string`

**Returns:** `any`

**Internal Comments:**
```
// console.log( 'THREE.Cache', 'Checking key:', key );
```

<details><summary>Code</summary>

```typescript
function ( key ) {

		if ( this.enabled === false ) return;

		// console.log( 'THREE.Cache', 'Checking key:', key );

		return this.files[ key ];

	}
```
</details>

### `remove(key: string): void`

**Parameters:**

- **`key`** `string`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( key ) {

		delete this.files[ key ];

	}
```
</details>

### `clear(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

		this.files = {};

	}
```
</details>

### `add(key: string, file: any): void`

**Parameters:**

- **`key`** `string`
- **`file`** `any`

**Returns:** `void`

**Internal Comments:**
```
// console.log( 'THREE.Cache', 'Adding key:', key ); (x5)
```

<details><summary>Code</summary>

```typescript
function ( key, file ) {

		if ( this.enabled === false ) return;

		// console.log( 'THREE.Cache', 'Adding key:', key );

		this.files[ key ] = file;

	}
```
</details>

### `get(key: string): any`

**Parameters:**

- **`key`** `string`

**Returns:** `any`

**Internal Comments:**
```
// console.log( 'THREE.Cache', 'Checking key:', key );
```

<details><summary>Code</summary>

```typescript
function ( key ) {

		if ( this.enabled === false ) return;

		// console.log( 'THREE.Cache', 'Checking key:', key );

		return this.files[ key ];

	}
```
</details>

### `remove(key: string): void`

**Parameters:**

- **`key`** `string`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( key ) {

		delete this.files[ key ];

	}
```
</details>

### `clear(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

		this.files = {};

	}
```
</details>


---