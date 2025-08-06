[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ViewportTextureNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/display/ViewportTextureNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TextureNode` | `../accessors/TextureNode.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `screenUV` | `./ScreenNode.js` |
| `Vector2` | `../../math/Vector2.js` |
| `FramebufferTexture` | `../../textures/FramebufferTexture.js` |
| `LinearMipmapLinearFilter` | `../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_size` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `defaultFramebuffer` | `any` | let/var | `null` | ✗ |
| `defaultFramebuffer` | `any` | let/var | `this.referenceNode ? this.referenceNode.defaultFramebuffer : this.defaultFram...` | ✗ |
| `renderer` | `any` | let/var | `frame.renderer` | ✗ |
| `currentGenerateMipmaps` | `any` | let/var | `framebufferTexture.generateMipmaps` | ✗ |
| `viewportTextureNode` | `any` | let/var | `new this.constructor( this.uvNode, this.levelNode, this.value )` | ✗ |


---

## Functions

### `ViewportTextureNode.getFrameBufferTexture(reference: any): any`

**Parameters:**

- **`reference`** `any`

**Returns:** `any`

**Calls:**

- `this._textures.has`
- `defaultFramebuffer.clone`
- `this._textures.set`
- `this._textures.get`

<details><summary>Code</summary>

```typescript
getFrameBufferTexture( reference = null ) {

		const defaultFramebuffer = this.referenceNode ? this.referenceNode.defaultFramebuffer : this.defaultFramebuffer;

		if ( reference === null ) {

			return defaultFramebuffer;

		}

		if ( this._textures.has( reference ) === false ) {

			const framebufferTexture = defaultFramebuffer.clone();

			this._textures.set( reference, framebufferTexture );

		}

		return this._textures.get( reference );

	}
```
</details>

### `ViewportTextureNode.updateBefore(frame: any): void`

**Parameters:**

- **`frame`** `any`

**Returns:** `void`

**Calls:**

- `renderer.getRenderTarget`
- `renderer.getDrawingBufferSize`
- `_size.set`
- `this.getFrameBufferTexture`
- `renderer.copyFramebufferToTexture`

**Internal Comments:**
```
// (x4)
```

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		const renderer = frame.renderer;
		const renderTarget = renderer.getRenderTarget();

		if ( renderTarget === null ) {

			renderer.getDrawingBufferSize( _size );

		} else {

			_size.set( renderTarget.width, renderTarget.height );

		}

		//

		const framebufferTexture = this.getFrameBufferTexture( renderTarget );

		if ( framebufferTexture.image.width !== _size.width || framebufferTexture.image.height !== _size.height ) {

			framebufferTexture.image.width = _size.width;
			framebufferTexture.image.height = _size.height;
			framebufferTexture.needsUpdate = true;

		}

		//

		const currentGenerateMipmaps = framebufferTexture.generateMipmaps;
		framebufferTexture.generateMipmaps = this.generateMipmaps;

		renderer.copyFramebufferToTexture( framebufferTexture );

		framebufferTexture.generateMipmaps = currentGenerateMipmaps;

		this.value = framebufferTexture;

	}
```
</details>

### `ViewportTextureNode.clone(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
clone() {

		const viewportTextureNode = new this.constructor( this.uvNode, this.levelNode, this.value );
		viewportTextureNode.generateMipmaps = this.generateMipmaps;

		return viewportTextureNode;

	}
```
</details>


---

## Classes

### `ViewportTextureNode`

<details><summary>Class Code</summary>

```ts
class ViewportTextureNode extends TextureNode {

	static get type() {

		return 'ViewportTextureNode';

	}

	/**
	 * Constructs a new viewport texture node.
	 *
	 * @param {Node} [uvNode=screenUV] - The uv node.
	 * @param {?Node} [levelNode=null] - The level node.
	 * @param {?Texture} [framebufferTexture=null] - A framebuffer texture holding the viewport data. If not provided, a framebuffer texture is created automatically.
	 */
	constructor( uvNode = screenUV, levelNode = null, framebufferTexture = null ) {

		let defaultFramebuffer = null;

		if ( framebufferTexture === null ) {

			defaultFramebuffer = new FramebufferTexture();
			defaultFramebuffer.minFilter = LinearMipmapLinearFilter;

			framebufferTexture = defaultFramebuffer;

		} else {

			defaultFramebuffer = framebufferTexture;

		}

		super( framebufferTexture, uvNode, levelNode );

		/**
		 * Whether to generate mipmaps or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.generateMipmaps = false;

		/**
		 * The reference framebuffer texture. This is used to store the framebuffer texture
		 * for the current render target. If the render target changes, a new framebuffer texture
		 * is created automatically.
		 *
		 * @type {FramebufferTexture}
		 * @default null
		 */
		this.defaultFramebuffer = defaultFramebuffer;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isOutputTextureNode = true;

		/**
		 * The `updateBeforeType` is set to `NodeUpdateType.RENDER` since the node renders the
		 * scene once per render in its {@link ViewportTextureNode#updateBefore} method.
		 *
		 * @type {string}
		 * @default 'frame'
		 */
		this.updateBeforeType = NodeUpdateType.RENDER;

		/**
		 * The framebuffer texture for the current renderer context.
		 *
		 * @type {WeakMap<RenderTarget, FramebufferTexture>}
		 * @private
		 */
		this._textures = new WeakMap();

	}

	getFrameBufferTexture( reference = null ) {

		const defaultFramebuffer = this.referenceNode ? this.referenceNode.defaultFramebuffer : this.defaultFramebuffer;

		if ( reference === null ) {

			return defaultFramebuffer;

		}

		if ( this._textures.has( reference ) === false ) {

			const framebufferTexture = defaultFramebuffer.clone();

			this._textures.set( reference, framebufferTexture );

		}

		return this._textures.get( reference );

	}

	updateBefore( frame ) {

		const renderer = frame.renderer;
		const renderTarget = renderer.getRenderTarget();

		if ( renderTarget === null ) {

			renderer.getDrawingBufferSize( _size );

		} else {

			_size.set( renderTarget.width, renderTarget.height );

		}

		//

		const framebufferTexture = this.getFrameBufferTexture( renderTarget );

		if ( framebufferTexture.image.width !== _size.width || framebufferTexture.image.height !== _size.height ) {

			framebufferTexture.image.width = _size.width;
			framebufferTexture.image.height = _size.height;
			framebufferTexture.needsUpdate = true;

		}

		//

		const currentGenerateMipmaps = framebufferTexture.generateMipmaps;
		framebufferTexture.generateMipmaps = this.generateMipmaps;

		renderer.copyFramebufferToTexture( framebufferTexture );

		framebufferTexture.generateMipmaps = currentGenerateMipmaps;

		this.value = framebufferTexture;

	}

	clone() {

		const viewportTextureNode = new this.constructor( this.uvNode, this.levelNode, this.value );
		viewportTextureNode.generateMipmaps = this.generateMipmaps;

		return viewportTextureNode;

	}

}
```
</details>

#### Methods

##### `getFrameBufferTexture(reference: any): any`

<details><summary>Code</summary>

```ts
getFrameBufferTexture( reference = null ) {

		const defaultFramebuffer = this.referenceNode ? this.referenceNode.defaultFramebuffer : this.defaultFramebuffer;

		if ( reference === null ) {

			return defaultFramebuffer;

		}

		if ( this._textures.has( reference ) === false ) {

			const framebufferTexture = defaultFramebuffer.clone();

			this._textures.set( reference, framebufferTexture );

		}

		return this._textures.get( reference );

	}
```
</details>

##### `updateBefore(frame: any): void`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		const renderer = frame.renderer;
		const renderTarget = renderer.getRenderTarget();

		if ( renderTarget === null ) {

			renderer.getDrawingBufferSize( _size );

		} else {

			_size.set( renderTarget.width, renderTarget.height );

		}

		//

		const framebufferTexture = this.getFrameBufferTexture( renderTarget );

		if ( framebufferTexture.image.width !== _size.width || framebufferTexture.image.height !== _size.height ) {

			framebufferTexture.image.width = _size.width;
			framebufferTexture.image.height = _size.height;
			framebufferTexture.needsUpdate = true;

		}

		//

		const currentGenerateMipmaps = framebufferTexture.generateMipmaps;
		framebufferTexture.generateMipmaps = this.generateMipmaps;

		renderer.copyFramebufferToTexture( framebufferTexture );

		framebufferTexture.generateMipmaps = currentGenerateMipmaps;

		this.value = framebufferTexture;

	}
```
</details>

##### `clone(): any`

<details><summary>Code</summary>

```ts
clone() {

		const viewportTextureNode = new this.constructor( this.uvNode, this.levelNode, this.value );
		viewportTextureNode.generateMipmaps = this.generateMipmaps;

		return viewportTextureNode;

	}
```
</details>


---