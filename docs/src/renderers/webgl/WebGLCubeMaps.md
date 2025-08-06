[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLCubeMaps.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLCubeMaps.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `CubeReflectionMapping` | `../../constants.js` |
| `CubeRefractionMapping` | `../../constants.js` |
| `EquirectangularReflectionMapping` | `../../constants.js` |
| `EquirectangularRefractionMapping` | `../../constants.js` |
| `WebGLCubeRenderTarget` | `../WebGLCubeRenderTarget.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `cubemaps` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `mapping` | `any` | let/var | `texture.mapping` | ✗ |
| `cubemap` | `any` | let/var | `cubemaps.get( texture ).texture` | ✗ |
| `image` | `any` | let/var | `texture.image` | ✗ |
| `renderTarget` | `WebGLCubeRenderTarget` | let/var | `new WebGLCubeRenderTarget( image.height )` | ✗ |
| `texture` | `any` | let/var | `event.target` | ✗ |


---

## Functions

### `WebGLCubeMaps(renderer: any): { get: (texture: any) => any; dispose: () => void; }`

**Parameters:**

- **`renderer`** `any`

**Returns:** `{ get: (texture: any) => any; dispose: () => void; }`

**Calls:**

- `cubemaps.has`
- `cubemaps.get`
- `mapTextureMapping`
- `renderTarget.fromEquirectangularTexture`
- `cubemaps.set`
- `texture.addEventListener`
- `texture.removeEventListener`
- `cubemaps.delete`
- `cubemap.dispose`

**Internal Comments:**
```
// image not yet ready. try the conversion next frame
```

<details><summary>Code</summary>

```typescript
function WebGLCubeMaps( renderer ) {

	let cubemaps = new WeakMap();

	function mapTextureMapping( texture, mapping ) {

		if ( mapping === EquirectangularReflectionMapping ) {

			texture.mapping = CubeReflectionMapping;

		} else if ( mapping === EquirectangularRefractionMapping ) {

			texture.mapping = CubeRefractionMapping;

		}

		return texture;

	}

	function get( texture ) {

		if ( texture && texture.isTexture ) {

			const mapping = texture.mapping;

			if ( mapping === EquirectangularReflectionMapping || mapping === EquirectangularRefractionMapping ) {

				if ( cubemaps.has( texture ) ) {

					const cubemap = cubemaps.get( texture ).texture;
					return mapTextureMapping( cubemap, texture.mapping );

				} else {

					const image = texture.image;

					if ( image && image.height > 0 ) {

						const renderTarget = new WebGLCubeRenderTarget( image.height );
						renderTarget.fromEquirectangularTexture( renderer, texture );
						cubemaps.set( texture, renderTarget );

						texture.addEventListener( 'dispose', onTextureDispose );

						return mapTextureMapping( renderTarget.texture, texture.mapping );

					} else {

						// image not yet ready. try the conversion next frame

						return null;

					}

				}

			}

		}

		return texture;

	}

	function onTextureDispose( event ) {

		const texture = event.target;

		texture.removeEventListener( 'dispose', onTextureDispose );

		const cubemap = cubemaps.get( texture );

		if ( cubemap !== undefined ) {

			cubemaps.delete( texture );
			cubemap.dispose();

		}

	}

	function dispose() {

		cubemaps = new WeakMap();

	}

	return {
		get: get,
		dispose: dispose
	};

}
```
</details>

### `mapTextureMapping(texture: any, mapping: any): any`

**Parameters:**

- **`texture`** `any`
- **`mapping`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function mapTextureMapping( texture, mapping ) {

		if ( mapping === EquirectangularReflectionMapping ) {

			texture.mapping = CubeReflectionMapping;

		} else if ( mapping === EquirectangularRefractionMapping ) {

			texture.mapping = CubeRefractionMapping;

		}

		return texture;

	}
```
</details>

### `get(texture: any): any`

**Parameters:**

- **`texture`** `any`

**Returns:** `any`

**Calls:**

- `cubemaps.has`
- `cubemaps.get`
- `mapTextureMapping`
- `renderTarget.fromEquirectangularTexture`
- `cubemaps.set`
- `texture.addEventListener`

**Internal Comments:**
```
// image not yet ready. try the conversion next frame
```

<details><summary>Code</summary>

```typescript
function get( texture ) {

		if ( texture && texture.isTexture ) {

			const mapping = texture.mapping;

			if ( mapping === EquirectangularReflectionMapping || mapping === EquirectangularRefractionMapping ) {

				if ( cubemaps.has( texture ) ) {

					const cubemap = cubemaps.get( texture ).texture;
					return mapTextureMapping( cubemap, texture.mapping );

				} else {

					const image = texture.image;

					if ( image && image.height > 0 ) {

						const renderTarget = new WebGLCubeRenderTarget( image.height );
						renderTarget.fromEquirectangularTexture( renderer, texture );
						cubemaps.set( texture, renderTarget );

						texture.addEventListener( 'dispose', onTextureDispose );

						return mapTextureMapping( renderTarget.texture, texture.mapping );

					} else {

						// image not yet ready. try the conversion next frame

						return null;

					}

				}

			}

		}

		return texture;

	}
```
</details>

### `onTextureDispose(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `texture.removeEventListener`
- `cubemaps.get`
- `cubemaps.delete`
- `cubemap.dispose`

<details><summary>Code</summary>

```typescript
function onTextureDispose( event ) {

		const texture = event.target;

		texture.removeEventListener( 'dispose', onTextureDispose );

		const cubemap = cubemaps.get( texture );

		if ( cubemap !== undefined ) {

			cubemaps.delete( texture );
			cubemap.dispose();

		}

	}
```
</details>

### `dispose(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function dispose() {

		cubemaps = new WeakMap();

	}
```
</details>


---