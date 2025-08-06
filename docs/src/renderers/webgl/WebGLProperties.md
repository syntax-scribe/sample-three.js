[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLProperties.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLProperties.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `properties` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |


---

## Functions

### `WebGLProperties(): { has: (object: any) => boolean; get: (object: any) => any; remove: (object: any) => void; update: (object: any, key: any, value: any) => void; dispose: () => void; }`

**Returns:** `{ has: (object: any) => boolean; get: (object: any) => any; remove: (object: any) => void; update: (object: any, key: any, value: any) => void; dispose: () => void; }`

**Calls:**

- `properties.has`
- `properties.get`
- `properties.set`
- `properties.delete`

<details><summary>Code</summary>

```typescript
function WebGLProperties() {

	let properties = new WeakMap();

	function has( object ) {

		return properties.has( object );

	}

	function get( object ) {

		let map = properties.get( object );

		if ( map === undefined ) {

			map = {};
			properties.set( object, map );

		}

		return map;

	}

	function remove( object ) {

		properties.delete( object );

	}

	function update( object, key, value ) {

		properties.get( object )[ key ] = value;

	}

	function dispose() {

		properties = new WeakMap();

	}

	return {
		has: has,
		get: get,
		remove: remove,
		update: update,
		dispose: dispose
	};

}
```
</details>

### `has(object: any): boolean`

**Parameters:**

- **`object`** `any`

**Returns:** `boolean`

**Calls:**

- `properties.has`

<details><summary>Code</summary>

```typescript
function has( object ) {

		return properties.has( object );

	}
```
</details>

### `get(object: any): any`

**Parameters:**

- **`object`** `any`

**Returns:** `any`

**Calls:**

- `properties.get`
- `properties.set`

<details><summary>Code</summary>

```typescript
function get( object ) {

		let map = properties.get( object );

		if ( map === undefined ) {

			map = {};
			properties.set( object, map );

		}

		return map;

	}
```
</details>

### `remove(object: any): void`

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `properties.delete`

<details><summary>Code</summary>

```typescript
function remove( object ) {

		properties.delete( object );

	}
```
</details>

### `update(object: any, key: any, value: any): void`

**Parameters:**

- **`object`** `any`
- **`key`** `any`
- **`value`** `any`

**Returns:** `void`

**Calls:**

- `properties.get`

<details><summary>Code</summary>

```typescript
function update( object, key, value ) {

		properties.get( object )[ key ] = value;

	}
```
</details>

### `dispose(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function dispose() {

		properties = new WeakMap();

	}
```
</details>


---