[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLShaderCache.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 2 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLShaderCache.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_id` | `number` | let/var | `0` | ✗ |
| `vertexShader` | `any` | let/var | `material.vertexShader` | ✗ |
| `fragmentShader` | `any` | let/var | `material.fragmentShader` | ✗ |
| `cache` | `Map<any, any>` | let/var | `this.materialCache` | ✗ |
| `cache` | `Map<any, any>` | let/var | `this.shaderCache` | ✗ |


---

## Functions

### `WebGLShaderCache.update(material: any): this`

**Parameters:**

- **`material`** `any`

**Returns:** `this`

**Calls:**

- `this._getShaderStage`
- `this._getShaderCacheForMaterial`
- `materialShaders.has`
- `materialShaders.add`

<details><summary>Code</summary>

```typescript
update( material ) {

		const vertexShader = material.vertexShader;
		const fragmentShader = material.fragmentShader;

		const vertexShaderStage = this._getShaderStage( vertexShader );
		const fragmentShaderStage = this._getShaderStage( fragmentShader );

		const materialShaders = this._getShaderCacheForMaterial( material );

		if ( materialShaders.has( vertexShaderStage ) === false ) {

			materialShaders.add( vertexShaderStage );
			vertexShaderStage.usedTimes ++;

		}

		if ( materialShaders.has( fragmentShaderStage ) === false ) {

			materialShaders.add( fragmentShaderStage );
			fragmentShaderStage.usedTimes ++;

		}

		return this;

	}
```
</details>

### `WebGLShaderCache.remove(material: any): this`

**Parameters:**

- **`material`** `any`

**Returns:** `this`

**Calls:**

- `this.materialCache.get`
- `this.shaderCache.delete`
- `this.materialCache.delete`

<details><summary>Code</summary>

```typescript
remove( material ) {

		const materialShaders = this.materialCache.get( material );

		for ( const shaderStage of materialShaders ) {

			shaderStage.usedTimes --;

			if ( shaderStage.usedTimes === 0 ) this.shaderCache.delete( shaderStage.code );

		}

		this.materialCache.delete( material );

		return this;

	}
```
</details>

### `WebGLShaderCache.getVertexShaderID(material: any): any`

**Parameters:**

- **`material`** `any`

**Returns:** `any`

**Calls:**

- `this._getShaderStage`

<details><summary>Code</summary>

```typescript
getVertexShaderID( material ) {

		return this._getShaderStage( material.vertexShader ).id;

	}
```
</details>

### `WebGLShaderCache.getFragmentShaderID(material: any): any`

**Parameters:**

- **`material`** `any`

**Returns:** `any`

**Calls:**

- `this._getShaderStage`

<details><summary>Code</summary>

```typescript
getFragmentShaderID( material ) {

		return this._getShaderStage( material.fragmentShader ).id;

	}
```
</details>

### `WebGLShaderCache.dispose(): void`

**Returns:** `void`

**Calls:**

- `this.shaderCache.clear`
- `this.materialCache.clear`

<details><summary>Code</summary>

```typescript
dispose() {

		this.shaderCache.clear();
		this.materialCache.clear();

	}
```
</details>

### `WebGLShaderCache._getShaderCacheForMaterial(material: any): any`

**Parameters:**

- **`material`** `any`

**Returns:** `any`

**Calls:**

- `cache.get`
- `cache.set`

<details><summary>Code</summary>

```typescript
_getShaderCacheForMaterial( material ) {

		const cache = this.materialCache;
		let set = cache.get( material );

		if ( set === undefined ) {

			set = new Set();
			cache.set( material, set );

		}

		return set;

	}
```
</details>

### `WebGLShaderCache._getShaderStage(code: any): any`

**Parameters:**

- **`code`** `any`

**Returns:** `any`

**Calls:**

- `cache.get`
- `cache.set`

<details><summary>Code</summary>

```typescript
_getShaderStage( code ) {

		const cache = this.shaderCache;
		let stage = cache.get( code );

		if ( stage === undefined ) {

			stage = new WebGLShaderStage( code );
			cache.set( code, stage );

		}

		return stage;

	}
```
</details>


---

## Classes

### `WebGLShaderCache`

<details><summary>Class Code</summary>

```ts
class WebGLShaderCache {

	constructor() {

		this.shaderCache = new Map();
		this.materialCache = new Map();

	}

	update( material ) {

		const vertexShader = material.vertexShader;
		const fragmentShader = material.fragmentShader;

		const vertexShaderStage = this._getShaderStage( vertexShader );
		const fragmentShaderStage = this._getShaderStage( fragmentShader );

		const materialShaders = this._getShaderCacheForMaterial( material );

		if ( materialShaders.has( vertexShaderStage ) === false ) {

			materialShaders.add( vertexShaderStage );
			vertexShaderStage.usedTimes ++;

		}

		if ( materialShaders.has( fragmentShaderStage ) === false ) {

			materialShaders.add( fragmentShaderStage );
			fragmentShaderStage.usedTimes ++;

		}

		return this;

	}

	remove( material ) {

		const materialShaders = this.materialCache.get( material );

		for ( const shaderStage of materialShaders ) {

			shaderStage.usedTimes --;

			if ( shaderStage.usedTimes === 0 ) this.shaderCache.delete( shaderStage.code );

		}

		this.materialCache.delete( material );

		return this;

	}

	getVertexShaderID( material ) {

		return this._getShaderStage( material.vertexShader ).id;

	}

	getFragmentShaderID( material ) {

		return this._getShaderStage( material.fragmentShader ).id;

	}

	dispose() {

		this.shaderCache.clear();
		this.materialCache.clear();

	}

	_getShaderCacheForMaterial( material ) {

		const cache = this.materialCache;
		let set = cache.get( material );

		if ( set === undefined ) {

			set = new Set();
			cache.set( material, set );

		}

		return set;

	}

	_getShaderStage( code ) {

		const cache = this.shaderCache;
		let stage = cache.get( code );

		if ( stage === undefined ) {

			stage = new WebGLShaderStage( code );
			cache.set( code, stage );

		}

		return stage;

	}

}
```
</details>

#### Methods

##### `update(material: any): this`

<details><summary>Code</summary>

```ts
update( material ) {

		const vertexShader = material.vertexShader;
		const fragmentShader = material.fragmentShader;

		const vertexShaderStage = this._getShaderStage( vertexShader );
		const fragmentShaderStage = this._getShaderStage( fragmentShader );

		const materialShaders = this._getShaderCacheForMaterial( material );

		if ( materialShaders.has( vertexShaderStage ) === false ) {

			materialShaders.add( vertexShaderStage );
			vertexShaderStage.usedTimes ++;

		}

		if ( materialShaders.has( fragmentShaderStage ) === false ) {

			materialShaders.add( fragmentShaderStage );
			fragmentShaderStage.usedTimes ++;

		}

		return this;

	}
```
</details>

##### `remove(material: any): this`

<details><summary>Code</summary>

```ts
remove( material ) {

		const materialShaders = this.materialCache.get( material );

		for ( const shaderStage of materialShaders ) {

			shaderStage.usedTimes --;

			if ( shaderStage.usedTimes === 0 ) this.shaderCache.delete( shaderStage.code );

		}

		this.materialCache.delete( material );

		return this;

	}
```
</details>

##### `getVertexShaderID(material: any): any`

<details><summary>Code</summary>

```ts
getVertexShaderID( material ) {

		return this._getShaderStage( material.vertexShader ).id;

	}
```
</details>

##### `getFragmentShaderID(material: any): any`

<details><summary>Code</summary>

```ts
getFragmentShaderID( material ) {

		return this._getShaderStage( material.fragmentShader ).id;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.shaderCache.clear();
		this.materialCache.clear();

	}
```
</details>

##### `_getShaderCacheForMaterial(material: any): any`

<details><summary>Code</summary>

```ts
_getShaderCacheForMaterial( material ) {

		const cache = this.materialCache;
		let set = cache.get( material );

		if ( set === undefined ) {

			set = new Set();
			cache.set( material, set );

		}

		return set;

	}
```
</details>

##### `_getShaderStage(code: any): any`

<details><summary>Code</summary>

```ts
_getShaderStage( code ) {

		const cache = this.shaderCache;
		let stage = cache.get( code );

		if ( stage === undefined ) {

			stage = new WebGLShaderStage( code );
			cache.set( code, stage );

		}

		return stage;

	}
```
</details>

### `WebGLShaderStage`

<details><summary>Class Code</summary>

```ts
class WebGLShaderStage {

	constructor( code ) {

		this.id = _id ++;

		this.code = code;
		this.usedTimes = 0;

	}

}
```
</details>


---