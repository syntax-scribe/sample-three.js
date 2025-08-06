[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLCubeUVMaps.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 10 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLCubeUVMaps.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `CubeReflectionMapping` | `../../constants.js` |
| `CubeRefractionMapping` | `../../constants.js` |
| `EquirectangularReflectionMapping` | `../../constants.js` |
| `EquirectangularRefractionMapping` | `../../constants.js` |
| `PMREMGenerator` | `../../extras/PMREMGenerator.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `cubeUVmaps` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `pmremGenerator` | `any` | let/var | `null` | ✗ |
| `mapping` | `any` | let/var | `texture.mapping` | ✗ |
| `isEquirectMap` | `boolean` | let/var | `( mapping === EquirectangularReflectionMapping \|\| mapping === Equirectangul...` | ✗ |
| `isCubeMap` | `boolean` | let/var | `( mapping === CubeReflectionMapping \|\| mapping === CubeRefractionMapping )` | ✗ |
| `currentPMREMVersion` | `any` | let/var | `renderTarget !== undefined ? renderTarget.texture.pmremVersion : 0` | ✗ |
| `image` | `any` | let/var | `texture.image` | ✗ |
| `count` | `number` | let/var | `0` | ✗ |
| `length` | `6` | let/var | `6` | ✗ |
| `texture` | `any` | let/var | `event.target` | ✗ |


---

## Functions

### `WebGLCubeUVMaps(renderer: any): { get: (texture: any) => any; dispose: () => void; }`

**Parameters:**

- **`renderer`** `any`

**Returns:** `{ get: (texture: any) => any; dispose: () => void; }`

**Calls:**

- `cubeUVmaps.get`
- `pmremGenerator.fromEquirectangular`
- `pmremGenerator.fromCubemap`
- `cubeUVmaps.set`
- `isCubeTextureComplete`
- `texture.addEventListener`
- `texture.removeEventListener`
- `cubeUVmaps.delete`
- `cubemapUV.dispose`
- `pmremGenerator.dispose`

**Internal Comments:**
```
// equirect/cube map to cubeUV conversion
// image not yet ready. try the conversion next frame
```

<details><summary>Code</summary>

```typescript
function WebGLCubeUVMaps( renderer ) {

	let cubeUVmaps = new WeakMap();

	let pmremGenerator = null;

	function get( texture ) {

		if ( texture && texture.isTexture ) {

			const mapping = texture.mapping;

			const isEquirectMap = ( mapping === EquirectangularReflectionMapping || mapping === EquirectangularRefractionMapping );
			const isCubeMap = ( mapping === CubeReflectionMapping || mapping === CubeRefractionMapping );

			// equirect/cube map to cubeUV conversion

			if ( isEquirectMap || isCubeMap ) {

				let renderTarget = cubeUVmaps.get( texture );

				const currentPMREMVersion = renderTarget !== undefined ? renderTarget.texture.pmremVersion : 0;

				if ( texture.isRenderTargetTexture && texture.pmremVersion !== currentPMREMVersion ) {

					if ( pmremGenerator === null ) pmremGenerator = new PMREMGenerator( renderer );

					renderTarget = isEquirectMap ? pmremGenerator.fromEquirectangular( texture, renderTarget ) : pmremGenerator.fromCubemap( texture, renderTarget );
					renderTarget.texture.pmremVersion = texture.pmremVersion;

					cubeUVmaps.set( texture, renderTarget );

					return renderTarget.texture;

				} else {

					if ( renderTarget !== undefined ) {

						return renderTarget.texture;

					} else {

						const image = texture.image;

						if ( ( isEquirectMap && image && image.height > 0 ) || ( isCubeMap && image && isCubeTextureComplete( image ) ) ) {

							if ( pmremGenerator === null ) pmremGenerator = new PMREMGenerator( renderer );

							renderTarget = isEquirectMap ? pmremGenerator.fromEquirectangular( texture ) : pmremGenerator.fromCubemap( texture );
							renderTarget.texture.pmremVersion = texture.pmremVersion;

							cubeUVmaps.set( texture, renderTarget );

							texture.addEventListener( 'dispose', onTextureDispose );

							return renderTarget.texture;

						} else {

							// image not yet ready. try the conversion next frame

							return null;

						}

					}

				}

			}

		}

		return texture;

	}

	function isCubeTextureComplete( image ) {

		let count = 0;
		const length = 6;

		for ( let i = 0; i < length; i ++ ) {

			if ( image[ i ] !== undefined ) count ++;

		}

		return count === length;


	}

	function onTextureDispose( event ) {

		const texture = event.target;

		texture.removeEventListener( 'dispose', onTextureDispose );

		const cubemapUV = cubeUVmaps.get( texture );

		if ( cubemapUV !== undefined ) {

			cubeUVmaps.delete( texture );
			cubemapUV.dispose();

		}

	}

	function dispose() {

		cubeUVmaps = new WeakMap();

		if ( pmremGenerator !== null ) {

			pmremGenerator.dispose();
			pmremGenerator = null;

		}

	}

	return {
		get: get,
		dispose: dispose
	};

}
```
</details>

### `get(texture: any): any`

**Parameters:**

- **`texture`** `any`

**Returns:** `any`

**Calls:**

- `cubeUVmaps.get`
- `pmremGenerator.fromEquirectangular`
- `pmremGenerator.fromCubemap`
- `cubeUVmaps.set`
- `isCubeTextureComplete`
- `texture.addEventListener`

**Internal Comments:**
```
// equirect/cube map to cubeUV conversion
// image not yet ready. try the conversion next frame
```

<details><summary>Code</summary>

```typescript
function get( texture ) {

		if ( texture && texture.isTexture ) {

			const mapping = texture.mapping;

			const isEquirectMap = ( mapping === EquirectangularReflectionMapping || mapping === EquirectangularRefractionMapping );
			const isCubeMap = ( mapping === CubeReflectionMapping || mapping === CubeRefractionMapping );

			// equirect/cube map to cubeUV conversion

			if ( isEquirectMap || isCubeMap ) {

				let renderTarget = cubeUVmaps.get( texture );

				const currentPMREMVersion = renderTarget !== undefined ? renderTarget.texture.pmremVersion : 0;

				if ( texture.isRenderTargetTexture && texture.pmremVersion !== currentPMREMVersion ) {

					if ( pmremGenerator === null ) pmremGenerator = new PMREMGenerator( renderer );

					renderTarget = isEquirectMap ? pmremGenerator.fromEquirectangular( texture, renderTarget ) : pmremGenerator.fromCubemap( texture, renderTarget );
					renderTarget.texture.pmremVersion = texture.pmremVersion;

					cubeUVmaps.set( texture, renderTarget );

					return renderTarget.texture;

				} else {

					if ( renderTarget !== undefined ) {

						return renderTarget.texture;

					} else {

						const image = texture.image;

						if ( ( isEquirectMap && image && image.height > 0 ) || ( isCubeMap && image && isCubeTextureComplete( image ) ) ) {

							if ( pmremGenerator === null ) pmremGenerator = new PMREMGenerator( renderer );

							renderTarget = isEquirectMap ? pmremGenerator.fromEquirectangular( texture ) : pmremGenerator.fromCubemap( texture );
							renderTarget.texture.pmremVersion = texture.pmremVersion;

							cubeUVmaps.set( texture, renderTarget );

							texture.addEventListener( 'dispose', onTextureDispose );

							return renderTarget.texture;

						} else {

							// image not yet ready. try the conversion next frame

							return null;

						}

					}

				}

			}

		}

		return texture;

	}
```
</details>

### `isCubeTextureComplete(image: any): boolean`

**Parameters:**

- **`image`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isCubeTextureComplete( image ) {

		let count = 0;
		const length = 6;

		for ( let i = 0; i < length; i ++ ) {

			if ( image[ i ] !== undefined ) count ++;

		}

		return count === length;


	}
```
</details>

### `onTextureDispose(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `texture.removeEventListener`
- `cubeUVmaps.get`
- `cubeUVmaps.delete`
- `cubemapUV.dispose`

<details><summary>Code</summary>

```typescript
function onTextureDispose( event ) {

		const texture = event.target;

		texture.removeEventListener( 'dispose', onTextureDispose );

		const cubemapUV = cubeUVmaps.get( texture );

		if ( cubemapUV !== undefined ) {

			cubeUVmaps.delete( texture );
			cubemapUV.dispose();

		}

	}
```
</details>

### `dispose(): void`

**Returns:** `void`

**Calls:**

- `pmremGenerator.dispose`

<details><summary>Code</summary>

```typescript
function dispose() {

		cubeUVmaps = new WeakMap();

		if ( pmremGenerator !== null ) {

			pmremGenerator.dispose();
			pmremGenerator = null;

		}

	}
```
</details>


---