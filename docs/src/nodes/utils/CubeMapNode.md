[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CubeMapNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 8 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/utils/CubeMapNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `../core/TempNode.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `CubeTexture` | `../../textures/CubeTexture.js` |
| `cubeTexture` | `../accessors/CubeTextureNode.js` |
| `CubeRenderTarget` | `../../renderers/common/CubeRenderTarget.js` |
| `CubeReflectionMapping` | `../../constants.js` |
| `CubeRefractionMapping` | `../../constants.js` |
| `EquirectangularReflectionMapping` | `../../constants.js` |
| `EquirectangularRefractionMapping` | `../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_cache` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `defaultTexture` | `CubeTexture` | let/var | `new CubeTexture()` | ✗ |
| `envNode` | `Node` | let/var | `this.envNode` | ✗ |
| `texture` | `any` | let/var | `( envNode.isTextureNode ) ? envNode.value : material[ envNode.property ]` | ✗ |
| `mapping` | `any` | let/var | `texture.mapping` | ✗ |
| `image` | `any` | let/var | `texture.image` | ✗ |
| `renderTarget` | `CubeRenderTarget` | let/var | `new CubeRenderTarget( image.height )` | ✗ |
| `texture` | `any` | let/var | `event.target` | ✗ |


---

## Functions

### `CubeMapNode.updateBefore(frame: any): void`

**Parameters:**

- **`frame`** `any`

**Returns:** `void`

**Calls:**

- `_cache.has`
- `_cache.get`
- `mapTextureMapping`
- `isEquirectangularMapReady`
- `renderTarget.fromEquirectangularTexture`
- `_cache.set`
- `texture.addEventListener`

**Internal Comments:**
```
// check for converted cubemap map
// create cube map from equirectangular map (x2)
// default cube texture as fallback when equirectangular texture is not yet loaded (x4)
// (x5)
// envNode already refers to a cube map (x4)
```

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		const { renderer, material } = frame;

		const envNode = this.envNode;

		if ( envNode.isTextureNode || envNode.isMaterialReferenceNode ) {

			const texture = ( envNode.isTextureNode ) ? envNode.value : material[ envNode.property ];

			if ( texture && texture.isTexture ) {

				const mapping = texture.mapping;

				if ( mapping === EquirectangularReflectionMapping || mapping === EquirectangularRefractionMapping ) {

					// check for converted cubemap map

					if ( _cache.has( texture ) ) {

						const cubeMap = _cache.get( texture );

						mapTextureMapping( cubeMap, texture.mapping );
						this._cubeTexture = cubeMap;

					} else {

						// create cube map from equirectangular map

						const image = texture.image;

						if ( isEquirectangularMapReady( image ) ) {

							const renderTarget = new CubeRenderTarget( image.height );
							renderTarget.fromEquirectangularTexture( renderer, texture );

							mapTextureMapping( renderTarget.texture, texture.mapping );
							this._cubeTexture = renderTarget.texture;

							_cache.set( texture, renderTarget.texture );

							texture.addEventListener( 'dispose', onTextureDispose );

						} else {

							// default cube texture as fallback when equirectangular texture is not yet loaded

							this._cubeTexture = this._defaultTexture;

						}

					}

					//

					this._cubeTextureNode.value = this._cubeTexture;

				} else {

					// envNode already refers to a cube map

					this._cubeTextureNode = this.envNode;

				}

			}

		}

	}
```
</details>

### `CubeMapNode.setup(builder: any): CubeTextureNode`

**Parameters:**

- **`builder`** `any`

**Returns:** `CubeTextureNode`

**Calls:**

- `this.updateBefore`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		this.updateBefore( builder );

		return this._cubeTextureNode;

	}
```
</details>

### `isEquirectangularMapReady(image: new (width?: number, height?: number) => HTMLImageElement): boolean`

**JSDoc:**
```typescript
/**
 * Returns true if the given equirectangular image has been fully loaded
 * and is ready for further processing.
 *
 * @private
 * @param {Image} image - The equirectangular image to check.
 * @return {boolean} Whether the image is ready or not.
 */
```

**Parameters:**

- **`image`** `new (width?: number, height?: number) => HTMLImageElement`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isEquirectangularMapReady( image ) {

	if ( image === null || image === undefined ) return false;

	return image.height > 0;

}
```
</details>

### `onTextureDispose(event: any): void`

**JSDoc:**
```typescript
/**
 * This function is executed when `dispose()` is called on the equirectangular
 * texture. In this case, the generated cube map with its render target
 * is deleted as well.
 *
 * @private
 * @param {Object} event - The event object.
 */
```

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `texture.removeEventListener`
- `_cache.get`
- `_cache.delete`
- `renderTarget.dispose`

<details><summary>Code</summary>

```typescript
function onTextureDispose( event ) {

	const texture = event.target;

	texture.removeEventListener( 'dispose', onTextureDispose );

	const renderTarget = _cache.get( texture );

	if ( renderTarget !== undefined ) {

		_cache.delete( texture );

		renderTarget.dispose();

	}

}
```
</details>

### `mapTextureMapping(texture: Texture, mapping: number): void`

**JSDoc:**
```typescript
/**
 * This function makes sure the generated cube map uses the correct
 * texture mapping that corresponds to the equirectangular original.
 *
 * @private
 * @param {Texture} texture - The cube texture.
 * @param {number} mapping - The original texture mapping.
 */
```

**Parameters:**

- **`texture`** `Texture`
- **`mapping`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function mapTextureMapping( texture, mapping ) {

	if ( mapping === EquirectangularReflectionMapping ) {

		texture.mapping = CubeReflectionMapping;

	} else if ( mapping === EquirectangularRefractionMapping ) {

		texture.mapping = CubeRefractionMapping;

	}

}
```
</details>


---

## Classes

### `CubeMapNode`

<details><summary>Class Code</summary>

```ts
class CubeMapNode extends TempNode {

	static get type() {

		return 'CubeMapNode';

	}

	/**
	 * Constructs a new cube map node.
	 *
	 * @param {Node} envNode - The node representing the environment map.
	 */
	constructor( envNode ) {

		super( 'vec3' );

		/**
		 * The node representing the environment map.
		 *
		 * @type {Node}
		 */
		this.envNode = envNode;

		/**
		 * A reference to the internal cube texture.
		 *
		 * @private
		 * @type {?CubeTexture}
		 * @default null
		 */
		this._cubeTexture = null;

		/**
		 * A reference to the internal cube texture node.
		 *
		 * @private
		 * @type {CubeTextureNode}
		 */
		this._cubeTextureNode = cubeTexture( null );

		const defaultTexture = new CubeTexture();
		defaultTexture.isRenderTargetTexture = true;

		/**
		 * A default cube texture that acts as a placeholder.
		 * It is used when the conversion from equirectangular to cube
		 * map has not finished yet for a given texture.
		 *
		 * @private
		 * @type {CubeTexture}
		 */
		this._defaultTexture = defaultTexture;

		/**
		 * The `updateBeforeType` is set to `NodeUpdateType.RENDER` since the node updates
		 * the texture once per render in its {@link CubeMapNode#updateBefore} method.
		 *
		 * @type {string}
		 * @default 'render'
		 */
		this.updateBeforeType = NodeUpdateType.RENDER;

	}

	updateBefore( frame ) {

		const { renderer, material } = frame;

		const envNode = this.envNode;

		if ( envNode.isTextureNode || envNode.isMaterialReferenceNode ) {

			const texture = ( envNode.isTextureNode ) ? envNode.value : material[ envNode.property ];

			if ( texture && texture.isTexture ) {

				const mapping = texture.mapping;

				if ( mapping === EquirectangularReflectionMapping || mapping === EquirectangularRefractionMapping ) {

					// check for converted cubemap map

					if ( _cache.has( texture ) ) {

						const cubeMap = _cache.get( texture );

						mapTextureMapping( cubeMap, texture.mapping );
						this._cubeTexture = cubeMap;

					} else {

						// create cube map from equirectangular map

						const image = texture.image;

						if ( isEquirectangularMapReady( image ) ) {

							const renderTarget = new CubeRenderTarget( image.height );
							renderTarget.fromEquirectangularTexture( renderer, texture );

							mapTextureMapping( renderTarget.texture, texture.mapping );
							this._cubeTexture = renderTarget.texture;

							_cache.set( texture, renderTarget.texture );

							texture.addEventListener( 'dispose', onTextureDispose );

						} else {

							// default cube texture as fallback when equirectangular texture is not yet loaded

							this._cubeTexture = this._defaultTexture;

						}

					}

					//

					this._cubeTextureNode.value = this._cubeTexture;

				} else {

					// envNode already refers to a cube map

					this._cubeTextureNode = this.envNode;

				}

			}

		}

	}

	setup( builder ) {

		this.updateBefore( builder );

		return this._cubeTextureNode;

	}

}
```
</details>

#### Methods

##### `updateBefore(frame: any): void`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		const { renderer, material } = frame;

		const envNode = this.envNode;

		if ( envNode.isTextureNode || envNode.isMaterialReferenceNode ) {

			const texture = ( envNode.isTextureNode ) ? envNode.value : material[ envNode.property ];

			if ( texture && texture.isTexture ) {

				const mapping = texture.mapping;

				if ( mapping === EquirectangularReflectionMapping || mapping === EquirectangularRefractionMapping ) {

					// check for converted cubemap map

					if ( _cache.has( texture ) ) {

						const cubeMap = _cache.get( texture );

						mapTextureMapping( cubeMap, texture.mapping );
						this._cubeTexture = cubeMap;

					} else {

						// create cube map from equirectangular map

						const image = texture.image;

						if ( isEquirectangularMapReady( image ) ) {

							const renderTarget = new CubeRenderTarget( image.height );
							renderTarget.fromEquirectangularTexture( renderer, texture );

							mapTextureMapping( renderTarget.texture, texture.mapping );
							this._cubeTexture = renderTarget.texture;

							_cache.set( texture, renderTarget.texture );

							texture.addEventListener( 'dispose', onTextureDispose );

						} else {

							// default cube texture as fallback when equirectangular texture is not yet loaded

							this._cubeTexture = this._defaultTexture;

						}

					}

					//

					this._cubeTextureNode.value = this._cubeTexture;

				} else {

					// envNode already refers to a cube map

					this._cubeTextureNode = this.envNode;

				}

			}

		}

	}
```
</details>

##### `setup(builder: any): CubeTextureNode`

<details><summary>Code</summary>

```ts
setup( builder ) {

		this.updateBefore( builder );

		return this._cubeTextureNode;

	}
```
</details>


---