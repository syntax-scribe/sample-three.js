[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PMREMNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 14 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/pmrem/PMREMNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `../core/TempNode.js` |
| `texture` | `../accessors/TextureNode.js` |
| `textureCubeUV` | `./PMREMUtils.js` |
| `uniform` | `../core/UniformNode.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `vec3` | `../tsl/TSLBase.js` |
| `Texture` | `../../textures/Texture.js` |
| `PMREMGenerator` | `../../renderers/common/extras/PMREMGenerator.js` |
| `materialEnvRotation` | `../accessors/MaterialProperties.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_cache` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `maxMip` | `number` | let/var | `Math.log2( imageHeight ) - 2` | ✗ |
| `texelHeight` | `number` | let/var | `1.0 / imageHeight` | ✗ |
| `texelWidth` | `number` | let/var | `1.0 / ( 3 * Math.max( Math.pow( 2, maxMip ), 7 * 16 ) )` | ✗ |
| `pmremVersion` | `number` | let/var | `cacheTexture !== undefined ? cacheTexture.pmremVersion : - 1` | ✗ |
| `image` | `any` | let/var | `texture.image` | ✗ |
| `defaultTexture` | `Texture` | let/var | `new Texture()` | ✗ |
| `pmrem` | `Texture` | let/var | `this._pmrem` | ✗ |
| `pmremVersion` | `number` | let/var | `pmrem ? pmrem.pmremVersion : - 1` | ✗ |
| `texture` | `Texture` | let/var | `this._value` | ✗ |
| `uvNode` | `any` | let/var | `this.uvNode` | ✗ |
| `levelNode` | `any` | let/var | `this.levelNode` | ✗ |
| `count` | `number` | let/var | `0` | ✗ |
| `length` | `6` | let/var | `6` | ✗ |


---

## Functions

### `_generateCubeUVSize(imageHeight: number): { texelWidth: number; texelHeight: number; maxMip: number; }`

**JSDoc:**
```typescript
/**
 * Generates the cubeUV size based on the given image height.
 *
 * @private
 * @param {number} imageHeight - The image height.
 * @return {{texelWidth: number,texelHeight: number, maxMip: number}} The result object.
 */
```

**Parameters:**

- **`imageHeight`** `number`

**Returns:** `{ texelWidth: number; texelHeight: number; maxMip: number; }`

**Calls:**

- `Math.log2`
- `Math.max`
- `Math.pow`

<details><summary>Code</summary>

```typescript
function _generateCubeUVSize( imageHeight ) {

	const maxMip = Math.log2( imageHeight ) - 2;

	const texelHeight = 1.0 / imageHeight;

	const texelWidth = 1.0 / ( 3 * Math.max( Math.pow( 2, maxMip ), 7 * 16 ) );

	return { texelWidth, texelHeight, maxMip };

}
```
</details>

### `_getPMREMFromTexture(texture: Texture, renderer: Renderer, generator: PMREMGenerator): Texture`

**JSDoc:**
```typescript
/**
 * Generates a PMREM from the given texture.
 *
 * @private
 * @param {Texture} texture - The texture to create the PMREM for.
 * @param {Renderer} renderer - The renderer.
 * @param {PMREMGenerator} generator - The PMREM generator.
 * @return {?Texture} The PMREM.
 */
```

**Parameters:**

- **`texture`** `Texture`
- **`renderer`** `Renderer`
- **`generator`** `PMREMGenerator`

**Returns:** `Texture`

**Calls:**

- `_getCache`
- `cache.get`
- `isCubeMapReady`
- `generator.fromCubemap`
- `isEquirectangularMapReady`
- `generator.fromEquirectangular`
- `cache.set`

<details><summary>Code</summary>

```typescript
function _getPMREMFromTexture( texture, renderer, generator ) {

	const cache = _getCache( renderer );

	let cacheTexture = cache.get( texture );

	const pmremVersion = cacheTexture !== undefined ? cacheTexture.pmremVersion : - 1;

	if ( pmremVersion !== texture.pmremVersion ) {

		const image = texture.image;

		if ( texture.isCubeTexture ) {

			if ( isCubeMapReady( image ) ) {

				cacheTexture = generator.fromCubemap( texture, cacheTexture );

			} else {

				return null;

			}


		} else {

			if ( isEquirectangularMapReady( image ) ) {

				cacheTexture = generator.fromEquirectangular( texture, cacheTexture );

			} else {

				return null;

			}

		}

		cacheTexture.pmremVersion = texture.pmremVersion;

		cache.set( texture, cacheTexture );

	}

	return cacheTexture.texture;

}
```
</details>

### `_getCache(renderer: Renderer): WeakMap<Texture, Texture>`

**JSDoc:**
```typescript
/**
 * Returns a cache that stores generated PMREMs for the respective textures.
 * A cache must be maintained per renderer since PMREMs are render target textures
 * which can't be shared across render contexts.
 *
 * @private
 * @param {Renderer} renderer - The renderer.
 * @return {WeakMap<Texture, Texture>} The PMREM cache.
 */
```

**Parameters:**

- **`renderer`** `Renderer`

**Returns:** `WeakMap<Texture, Texture>`

**Calls:**

- `_cache.get`
- `_cache.set`

<details><summary>Code</summary>

```typescript
function _getCache( renderer ) {

	let rendererCache = _cache.get( renderer );

	if ( rendererCache === undefined ) {

		rendererCache = new WeakMap();
		_cache.set( renderer, rendererCache );

	}

	return rendererCache;

}
```
</details>

### `PMREMNode.updateFromTexture(texture: Texture): void`

**JSDoc:**
```typescript
/**
	 * Uses the given PMREM texture to update internal values.
	 *
	 * @param {Texture} texture - The PMREM texture.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `void`

**Calls:**

- `_generateCubeUVSize`

<details><summary>Code</summary>

```typescript
updateFromTexture( texture ) {

		const cubeUVSize = _generateCubeUVSize( texture.image.height );

		this._texture.value = texture;
		this._width.value = cubeUVSize.texelWidth;
		this._height.value = cubeUVSize.texelHeight;
		this._maxMip.value = cubeUVSize.maxMip;

	}
```
</details>

### `PMREMNode.updateBefore(frame: any): void`

**Parameters:**

- **`frame`** `any`

**Returns:** `void`

**Calls:**

- `_getPMREMFromTexture`
- `this.updateFromTexture`

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		let pmrem = this._pmrem;

		const pmremVersion = pmrem ? pmrem.pmremVersion : - 1;
		const texture = this._value;

		if ( pmremVersion !== texture.pmremVersion ) {

			if ( texture.isPMREMTexture === true ) {

				pmrem = texture;

			} else {

				pmrem = _getPMREMFromTexture( texture, frame.renderer, this._generator );

			}

			if ( pmrem !== null ) {

				this._pmrem = pmrem;

				this.updateFromTexture( pmrem );

			}

		}

	}
```
</details>

### `PMREMNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `this.updateBefore`
- `builder.context.getUV`
- `materialEnvRotation.mul`
- `vec3 (from ../tsl/TSLBase.js)`
- `uvNode.y.negate`
- `builder.context.getTextureLevel`
- `textureCubeUV (from ./PMREMUtils.js)`

**Internal Comments:**
```
// (x8)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		if ( this._generator === null ) {

			this._generator = new PMREMGenerator( builder.renderer );

		}

		this.updateBefore( builder );

		//

		let uvNode = this.uvNode;

		if ( uvNode === null && builder.context.getUV ) {

			uvNode = builder.context.getUV( this );

		}

		//

		uvNode = materialEnvRotation.mul( vec3( uvNode.x, uvNode.y.negate(), uvNode.z ) );

		//

		let levelNode = this.levelNode;

		if ( levelNode === null && builder.context.getTextureLevel ) {

			levelNode = builder.context.getTextureLevel( this );

		}

		//

		return textureCubeUV( this._texture, uvNode, levelNode, this._width, this._height, this._maxMip );

	}
```
</details>

### `PMREMNode.dispose(): void`

**Returns:** `void`

**Calls:**

- `super.dispose`
- `this._generator.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		super.dispose();

		if ( this._generator !== null ) this._generator.dispose();

	}
```
</details>

### `isCubeMapReady(image: any[]): boolean`

**JSDoc:**
```typescript
/**
 * Returns `true` if the given cube map image has been fully loaded.
 *
 * @private
 * @param {?Array<(Image|Object)>} [image] - The cube map image.
 * @return {boolean} Whether the given cube map is ready or not.
 */
```

**Parameters:**

- **`image`** `any[]`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isCubeMapReady( image ) {

	if ( image === null || image === undefined ) return false;

	let count = 0;
	const length = 6;

	for ( let i = 0; i < length; i ++ ) {

		if ( image[ i ] !== undefined ) count ++;

	}

	return count === length;


}
```
</details>

### `isEquirectangularMapReady(image: any): boolean`

**JSDoc:**
```typescript
/**
 * Returns `true` if the given equirectangular image has been fully loaded.
 *
 * @private
 * @param {(Image|Object)} image - The equirectangular image.
 * @return {boolean} Whether the given cube map is ready or not.
 */
```

**Parameters:**

- **`image`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isEquirectangularMapReady( image ) {

	if ( image === null || image === undefined ) return false;

	return image.height > 0;

}
```
</details>


---

## Classes

### `PMREMNode`

<details><summary>Class Code</summary>

```ts
class PMREMNode extends TempNode {

	static get type() {

		return 'PMREMNode';

	}

	/**
	 * Constructs a new function overloading node.
	 *
	 * @param {Texture} value - The input texture.
	 * @param {Node<vec2>} [uvNode=null] - The uv node.
	 * @param {Node<float>} [levelNode=null] - The level node.
	 */
	constructor( value, uvNode = null, levelNode = null ) {

		super( 'vec3' );

		/**
		 * Reference to the input texture.
		 *
		 * @private
		 * @type {Texture}
		 */
		this._value = value;

		/**
		 * Reference to the generated PMREM.
		 *
		 * @private
		 * @type {Texture | null}
		 * @default null
		 */
		this._pmrem = null;

		/**
		 *  The uv node.
		 *
		 * @type {Node<vec2>}
		 */
		this.uvNode = uvNode;

		/**
		 *  The level node.
		 *
		 * @type {Node<float>}
		 */
		this.levelNode = levelNode;

		/**
		 * Reference to a PMREM generator.
		 *
		 * @private
		 * @type {?PMREMGenerator}
		 * @default null
		 */
		this._generator = null;

		const defaultTexture = new Texture();
		defaultTexture.isRenderTargetTexture = true;

		/**
		 * The texture node holding the generated PMREM.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._texture = texture( defaultTexture );

		/**
		 * A uniform representing the PMREM's width.
		 *
		 * @private
		 * @type {UniformNode<float>}
		 */
		this._width = uniform( 0 );

		/**
		 * A uniform representing the PMREM's height.
		 *
		 * @private
		 * @type {UniformNode<float>}
		 */
		this._height = uniform( 0 );

		/**
		 * A uniform representing the PMREM's max Mip.
		 *
		 * @private
		 * @type {UniformNode<float>}
		 */
		this._maxMip = uniform( 0 );

		/**
		 * The `updateBeforeType` is set to `NodeUpdateType.RENDER`.
		 *
		 * @type {string}
		 * @default 'render'
		 */
		this.updateBeforeType = NodeUpdateType.RENDER;

	}

	set value( value ) {

		this._value = value;
		this._pmrem = null;

	}

	/**
	 * The node's texture value.
	 *
	 * @type {Texture}
	 */
	get value() {

		return this._value;

	}

	/**
	 * Uses the given PMREM texture to update internal values.
	 *
	 * @param {Texture} texture - The PMREM texture.
	 */
	updateFromTexture( texture ) {

		const cubeUVSize = _generateCubeUVSize( texture.image.height );

		this._texture.value = texture;
		this._width.value = cubeUVSize.texelWidth;
		this._height.value = cubeUVSize.texelHeight;
		this._maxMip.value = cubeUVSize.maxMip;

	}

	updateBefore( frame ) {

		let pmrem = this._pmrem;

		const pmremVersion = pmrem ? pmrem.pmremVersion : - 1;
		const texture = this._value;

		if ( pmremVersion !== texture.pmremVersion ) {

			if ( texture.isPMREMTexture === true ) {

				pmrem = texture;

			} else {

				pmrem = _getPMREMFromTexture( texture, frame.renderer, this._generator );

			}

			if ( pmrem !== null ) {

				this._pmrem = pmrem;

				this.updateFromTexture( pmrem );

			}

		}

	}

	setup( builder ) {

		if ( this._generator === null ) {

			this._generator = new PMREMGenerator( builder.renderer );

		}

		this.updateBefore( builder );

		//

		let uvNode = this.uvNode;

		if ( uvNode === null && builder.context.getUV ) {

			uvNode = builder.context.getUV( this );

		}

		//

		uvNode = materialEnvRotation.mul( vec3( uvNode.x, uvNode.y.negate(), uvNode.z ) );

		//

		let levelNode = this.levelNode;

		if ( levelNode === null && builder.context.getTextureLevel ) {

			levelNode = builder.context.getTextureLevel( this );

		}

		//

		return textureCubeUV( this._texture, uvNode, levelNode, this._width, this._height, this._maxMip );

	}

	dispose() {

		super.dispose();

		if ( this._generator !== null ) this._generator.dispose();

	}

}
```
</details>

#### Methods

##### `updateFromTexture(texture: Texture): void`

<details><summary>Code</summary>

```ts
updateFromTexture( texture ) {

		const cubeUVSize = _generateCubeUVSize( texture.image.height );

		this._texture.value = texture;
		this._width.value = cubeUVSize.texelWidth;
		this._height.value = cubeUVSize.texelHeight;
		this._maxMip.value = cubeUVSize.maxMip;

	}
```
</details>

##### `updateBefore(frame: any): void`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		let pmrem = this._pmrem;

		const pmremVersion = pmrem ? pmrem.pmremVersion : - 1;
		const texture = this._value;

		if ( pmremVersion !== texture.pmremVersion ) {

			if ( texture.isPMREMTexture === true ) {

				pmrem = texture;

			} else {

				pmrem = _getPMREMFromTexture( texture, frame.renderer, this._generator );

			}

			if ( pmrem !== null ) {

				this._pmrem = pmrem;

				this.updateFromTexture( pmrem );

			}

		}

	}
```
</details>

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		if ( this._generator === null ) {

			this._generator = new PMREMGenerator( builder.renderer );

		}

		this.updateBefore( builder );

		//

		let uvNode = this.uvNode;

		if ( uvNode === null && builder.context.getUV ) {

			uvNode = builder.context.getUV( this );

		}

		//

		uvNode = materialEnvRotation.mul( vec3( uvNode.x, uvNode.y.negate(), uvNode.z ) );

		//

		let levelNode = this.levelNode;

		if ( levelNode === null && builder.context.getTextureLevel ) {

			levelNode = builder.context.getTextureLevel( this );

		}

		//

		return textureCubeUV( this._texture, uvNode, levelNode, this._width, this._height, this._maxMip );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		super.dispose();

		if ( this._generator !== null ) this._generator.dispose();

	}
```
</details>


---