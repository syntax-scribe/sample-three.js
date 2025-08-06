[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PassNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 29 |
| 🧱 Classes | 3 |
| 📦 Imports | 12 |
| 📊 Variables & Constants | 22 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/display/PassNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `../core/TempNode.js` |
| `TextureNode` | `../accessors/TextureNode.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `nodeObject` | `../tsl/TSLBase.js` |
| `uniform` | `../core/UniformNode.js` |
| `viewZToOrthographicDepth` | `./ViewportDepthNode.js` |
| `perspectiveDepthToViewZ` | `./ViewportDepthNode.js` |
| `HalfFloatType` | `../../constants.js` |
| `Vector2` | `../../math/Vector2.js` |
| `Vector4` | `../../math/Vector4.js` |
| `DepthTexture` | `../../textures/DepthTexture.js` |
| `RenderTarget` | `../../core/RenderTarget.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_size` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `newNode` | `any` | let/var | `new this.constructor( this.passNode, this.textureName, this.previousTexture )` | ✗ |
| `depthTexture` | `DepthTexture` | let/var | `new DepthTexture()` | ✗ |
| `renderTarget` | `RenderTarget` | let/var | `new RenderTarget( this._width * this._pixelRatio, this._height * this._pixelR...` | ✗ |
| `texture` | `Texture` | let/var | `this._textures[ name ]` | ✗ |
| `refTexture` | `Texture` | let/var | `this.renderTarget.texture` | ✗ |
| `texture` | `Texture` | let/var | `this._previousTextures[ name ]` | ✗ |
| `prevTexture` | `Texture` | let/var | `this._previousTextures[ name ]` | ✗ |
| `texture` | `Texture` | let/var | `this._textures[ name ]` | ✗ |
| `textureNode` | `TextureNode` | let/var | `this._textureNodes[ name ]` | ✗ |
| `textureNode` | `TextureNode` | let/var | `this._previousTextureNodes[ name ]` | ✗ |
| `viewZNode` | `any` | let/var | `this._viewZNodes[ name ]` | ✗ |
| `cameraNear` | `UniformNode` | let/var | `this._cameraNear` | ✗ |
| `cameraFar` | `UniformNode` | let/var | `this._cameraFar` | ✗ |
| `linearDepthNode` | `any` | let/var | `this._linearDepthNodes[ name ]` | ✗ |
| `cameraNear` | `UniformNode` | let/var | `this._cameraNear` | ✗ |
| `cameraFar` | `UniformNode` | let/var | `this._cameraFar` | ✗ |
| `camera` | `any` | let/var | `*not shown*` | ✗ |
| `pixelRatio` | `any` | let/var | `*not shown*` | ✗ |
| `currentMask` | `any` | let/var | `camera.layers.mask` | ✗ |
| `effectiveWidth` | `number` | let/var | `this._width * this._pixelRatio * this._resolution` | ✗ |
| `effectiveHeight` | `number` | let/var | `this._height * this._pixelRatio * this._resolution` | ✗ |


---

## Functions

### `PassTextureNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `this.passNode.build`
- `super.setup`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		this.passNode.build( builder );

		return super.setup( builder );

	}
```
</details>

### `PassTextureNode.clone(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor( this.passNode, this.value );

	}
```
</details>

### `PassMultipleTextureNode.updateTexture(): void`

**JSDoc:**
```typescript
/**
	 * Updates the texture reference of this node.
	 */
```

**Returns:** `void`

**Calls:**

- `this.passNode.getPreviousTexture`
- `this.passNode.getTexture`

<details><summary>Code</summary>

```typescript
updateTexture() {

		this.value = this.previousTexture ? this.passNode.getPreviousTexture( this.textureName ) : this.passNode.getTexture( this.textureName );

	}
```
</details>

### `PassMultipleTextureNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `this.updateTexture`
- `super.setup`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		this.updateTexture();

		return super.setup( builder );

	}
```
</details>

### `PassMultipleTextureNode.clone(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
clone() {

		const newNode = new this.constructor( this.passNode, this.textureName, this.previousTexture );
		newNode.uvNode = this.uvNode;
		newNode.levelNode = this.levelNode;
		newNode.biasNode = this.biasNode;
		newNode.sampler = this.sampler;
		newNode.depthNode = this.depthNode;
		newNode.compareNode = this.compareNode;
		newNode.gradNode = this.gradNode;

		return newNode;

	}
```
</details>

### `PassNode.setResolution(resolution: number): PassNode`

**JSDoc:**
```typescript
/**
	 * Sets the resolution for the pass.
	 * The resolution is a factor that is multiplied with the renderer's width and height.
	 *
	 * @param {number} resolution - The resolution to set. A value of `1` means full resolution.
	 * @return {PassNode} A reference to this pass.
	 */
```

**Parameters:**

- **`resolution`** `number`

**Returns:** `PassNode`

<details><summary>Code</summary>

```typescript
setResolution( resolution ) {

		this._resolution = resolution;

		return this;

	}
```
</details>

### `PassNode.getResolution(): number`

**JSDoc:**
```typescript
/**
	 * Gets the current resolution of the pass.
	 *
	 * @return {number} The current resolution. A value of `1` means full resolution.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getResolution() {

		return this._resolution;

	}
```
</details>

### `PassNode.setLayers(layers: Layers): PassNode`

**JSDoc:**
```typescript
/**
	 * Sets the layer configuration that should be used when rendering the pass.
	 *
	 * @param {Layers} layers - The layers object to set.
	 * @return {PassNode} A reference to this pass.
	 */
```

**Parameters:**

- **`layers`** `Layers`

**Returns:** `PassNode`

<details><summary>Code</summary>

```typescript
setLayers( layers ) {

		this._layers = layers;

		return this;

	}
```
</details>

### `PassNode.getLayers(): Layers`

**JSDoc:**
```typescript
/**
	 * Gets the current layer configuration of the pass.
	 *
	 * @return {?Layers} .
	 */
```

**Returns:** `Layers`

<details><summary>Code</summary>

```typescript
getLayers() {

		return this._layers;

	}
```
</details>

### `PassNode.setMRT(mrt: MRTNode): PassNode`

**JSDoc:**
```typescript
/**
	 * Sets the given MRT node to setup MRT for this pass.
	 *
	 * @param {MRTNode} mrt - The MRT object.
	 * @return {PassNode} A reference to this pass.
	 */
```

**Parameters:**

- **`mrt`** `MRTNode`

**Returns:** `PassNode`

<details><summary>Code</summary>

```typescript
setMRT( mrt ) {

		this._mrt = mrt;

		return this;

	}
```
</details>

### `PassNode.getMRT(): MRTNode`

**JSDoc:**
```typescript
/**
	 * Returns the current MRT node.
	 *
	 * @return {MRTNode} The current MRT node.
	 */
```

**Returns:** `MRTNode`

<details><summary>Code</summary>

```typescript
getMRT() {

		return this._mrt;

	}
```
</details>

### `PassNode.getTexture(name: string): Texture`

**JSDoc:**
```typescript
/**
	 * Returns the texture for the given output name.
	 *
	 * @param {string} name - The output name to get the texture for.
	 * @return {Texture} The texture.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `Texture`

**Calls:**

- `refTexture.clone`
- `this.renderTarget.textures.push`

<details><summary>Code</summary>

```typescript
getTexture( name ) {

		let texture = this._textures[ name ];

		if ( texture === undefined ) {

			const refTexture = this.renderTarget.texture;

			texture = refTexture.clone();
			texture.name = name;

			this._textures[ name ] = texture;

			this.renderTarget.textures.push( texture );

		}

		return texture;

	}
```
</details>

### `PassNode.getPreviousTexture(name: string): Texture`

**JSDoc:**
```typescript
/**
	 * Returns the texture holding the data of the previous frame for the given output name.
	 *
	 * @param {string} name - The output name to get the texture for.
	 * @return {Texture} The texture holding the data of the previous frame.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `Texture`

**Calls:**

- `this.getTexture( name ).clone`

<details><summary>Code</summary>

```typescript
getPreviousTexture( name ) {

		let texture = this._previousTextures[ name ];

		if ( texture === undefined ) {

			texture = this.getTexture( name ).clone();

			this._previousTextures[ name ] = texture;

		}

		return texture;

	}
```
</details>

### `PassNode.toggleTexture(name: string): void`

**JSDoc:**
```typescript
/**
	 * Switches current and previous textures for the given output name.
	 *
	 * @param {string} name - The output name.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `void`

**Calls:**

- `this.renderTarget.textures.indexOf`
- `this._textureNodes[ name ].updateTexture`
- `this._previousTextureNodes[ name ].updateTexture`

<details><summary>Code</summary>

```typescript
toggleTexture( name ) {

		const prevTexture = this._previousTextures[ name ];

		if ( prevTexture !== undefined ) {

			const texture = this._textures[ name ];

			const index = this.renderTarget.textures.indexOf( texture );
			this.renderTarget.textures[ index ] = prevTexture;

			this._textures[ name ] = prevTexture;
			this._previousTextures[ name ] = texture;

			this._textureNodes[ name ].updateTexture();
			this._previousTextureNodes[ name ].updateTexture();

		}

	}
```
</details>

### `PassNode.getTextureNode(name: string): TextureNode`

**JSDoc:**
```typescript
/**
	 * Returns the texture node for the given output name.
	 *
	 * @param {string} [name='output'] - The output name to get the texture node for.
	 * @return {TextureNode} The texture node.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `TextureNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`
- `textureNode.updateTexture`

<details><summary>Code</summary>

```typescript
getTextureNode( name = 'output' ) {

		let textureNode = this._textureNodes[ name ];

		if ( textureNode === undefined ) {

			textureNode = nodeObject( new PassMultipleTextureNode( this, name ) );
			textureNode.updateTexture();
			this._textureNodes[ name ] = textureNode;

		}

		return textureNode;

	}
```
</details>

### `PassNode.getPreviousTextureNode(name: string): TextureNode`

**JSDoc:**
```typescript
/**
	 * Returns the previous texture node for the given output name.
	 *
	 * @param {string} [name='output'] - The output name to get the previous texture node for.
	 * @return {TextureNode} The previous texture node.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `TextureNode`

**Calls:**

- `this.getTextureNode`
- `nodeObject (from ../tsl/TSLBase.js)`
- `textureNode.updateTexture`

<details><summary>Code</summary>

```typescript
getPreviousTextureNode( name = 'output' ) {

		let textureNode = this._previousTextureNodes[ name ];

		if ( textureNode === undefined ) {

			if ( this._textureNodes[ name ] === undefined ) this.getTextureNode( name );

			textureNode = nodeObject( new PassMultipleTextureNode( this, name, true ) );
			textureNode.updateTexture();
			this._previousTextureNodes[ name ] = textureNode;

		}

		return textureNode;

	}
```
</details>

### `PassNode.getViewZNode(name: string): Node`

**JSDoc:**
```typescript
/**
	 * Returns a viewZ node of this pass.
	 *
	 * @param {string} [name='depth'] - The output name to get the viewZ node for. In most cases the default `'depth'` can be used however the parameter exists for custom depth outputs.
	 * @return {Node} The viewZ node.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `Node`

**Calls:**

- `perspectiveDepthToViewZ (from ./ViewportDepthNode.js)`
- `this.getTextureNode`

<details><summary>Code</summary>

```typescript
getViewZNode( name = 'depth' ) {

		let viewZNode = this._viewZNodes[ name ];

		if ( viewZNode === undefined ) {

			const cameraNear = this._cameraNear;
			const cameraFar = this._cameraFar;

			this._viewZNodes[ name ] = viewZNode = perspectiveDepthToViewZ( this.getTextureNode( name ), cameraNear, cameraFar );

		}

		return viewZNode;

	}
```
</details>

### `PassNode.getLinearDepthNode(name: string): Node`

**JSDoc:**
```typescript
/**
	 * Returns a linear depth node of this pass.
	 *
	 * @param {string} [name='depth'] - The output name to get the linear depth node for. In most cases the default `'depth'` can be used however the parameter exists for custom depth outputs.
	 * @return {Node} The linear depth node.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `Node`

**Calls:**

- `this.getViewZNode`
- `viewZToOrthographicDepth (from ./ViewportDepthNode.js)`

**Internal Comments:**
```
// TODO: just if ( builder.camera.isPerspectiveCamera ) (x5)
```

<details><summary>Code</summary>

```typescript
getLinearDepthNode( name = 'depth' ) {

		let linearDepthNode = this._linearDepthNodes[ name ];

		if ( linearDepthNode === undefined ) {

			const cameraNear = this._cameraNear;
			const cameraFar = this._cameraFar;
			const viewZNode = this.getViewZNode( name );

			// TODO: just if ( builder.camera.isPerspectiveCamera )

			this._linearDepthNodes[ name ] = linearDepthNode = viewZToOrthographicDepth( viewZNode, cameraNear, cameraFar );

		}

		return linearDepthNode;

	}
```
</details>

### `PassNode.compileAsync(renderer: Renderer): Promise<any>`

**JSDoc:**
```typescript
/**
	 * Precompiles the pass.
	 *
	 * Note that this method must be called after the pass configuartion is complete.
	 * So calls like `setMRT()` and `getTextureNode()` must proceed the precompilation.
	 *
	 * @async
	 * @param {Renderer} renderer - The renderer.
	 * @return {Promise} A Promise that resolves when the compile has been finished.
	 * @see {@link Renderer#compileAsync}
	 */
```

**Parameters:**

- **`renderer`** `Renderer`

**Returns:** `Promise<any>`

**Calls:**

- `renderer.getRenderTarget`
- `renderer.getMRT`
- `renderer.setRenderTarget`
- `renderer.setMRT`
- `renderer.compileAsync`

<details><summary>Code</summary>

```typescript
async compileAsync( renderer ) {

		const currentRenderTarget = renderer.getRenderTarget();
		const currentMRT = renderer.getMRT();

		renderer.setRenderTarget( this.renderTarget );
		renderer.setMRT( this._mrt );

		await renderer.compileAsync( this.scene, this.camera );

		renderer.setRenderTarget( currentRenderTarget );
		renderer.setMRT( currentMRT );

	}
```
</details>

### `PassNode.setup({ renderer }: any): Node | TextureNode`

**Parameters:**

- **`{ renderer }`** `any`

**Returns:** `Node | TextureNode`

**Calls:**

- `renderer.getColorBufferType`
- `this.getTextureNode`
- `this.getLinearDepthNode`

<details><summary>Code</summary>

```typescript
setup( { renderer } ) {

		this.renderTarget.samples = this.options.samples === undefined ? renderer.samples : this.options.samples;

		this.renderTarget.texture.type = renderer.getColorBufferType();

		return this.scope === PassNode.COLOR ? this.getTextureNode() : this.getLinearDepthNode();

	}
```
</details>

### `PassNode.updateBefore(frame: any): void`

**Parameters:**

- **`frame`** `any`

**Returns:** `void`

**Calls:**

- `renderer.getOutputRenderTarget`
- `renderer.xr.getCamera`
- `renderer.xr.updateCamera`
- `_size.set`
- `renderer.getPixelRatio`
- `renderer.getSize`
- `this.setSize`
- `renderer.getRenderTarget`
- `renderer.getMRT`
- `this.toggleTexture`
- `renderer.setRenderTarget`
- `renderer.setMRT`
- `renderer.render`

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		const { renderer } = frame;
		const { scene } = this;

		let camera;
		let pixelRatio;

		const outputRenderTarget = renderer.getOutputRenderTarget();

		if ( outputRenderTarget && outputRenderTarget.isXRRenderTarget === true ) {

			pixelRatio = 1;
			camera = renderer.xr.getCamera();

			renderer.xr.updateCamera( camera );

			_size.set( outputRenderTarget.width, outputRenderTarget.height );

		} else {

			camera = this.camera;
			pixelRatio = renderer.getPixelRatio();

			renderer.getSize( _size );

		}

		this._pixelRatio = pixelRatio;

		this.setSize( _size.width, _size.height );

		const currentRenderTarget = renderer.getRenderTarget();
		const currentMRT = renderer.getMRT();
		const currentMask = camera.layers.mask;

		this._cameraNear.value = camera.near;
		this._cameraFar.value = camera.far;

		if ( this._layers !== null ) {

			camera.layers.mask = this._layers.mask;

		}

		for ( const name in this._previousTextures ) {

			this.toggleTexture( name );

		}

		renderer.setRenderTarget( this.renderTarget );
		renderer.setMRT( this._mrt );

		renderer.render( scene, camera );

		renderer.setRenderTarget( currentRenderTarget );
		renderer.setMRT( currentMRT );

		camera.layers.mask = currentMask;

	}
```
</details>

### `PassNode.setSize(width: number, height: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the size of the pass's render target. Honors the pixel ratio.
	 *
	 * @param {number} width - The width to set.
	 * @param {number} height - The height to set.
	 */
```

**Parameters:**

- **`width`** `number`
- **`height`** `number`

**Returns:** `void`

**Calls:**

- `this.renderTarget.setSize`
- `this.renderTarget.scissor.copy`
- `this.renderTarget.viewport.copy`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this._width = width;
		this._height = height;

		const effectiveWidth = this._width * this._pixelRatio * this._resolution;
		const effectiveHeight = this._height * this._pixelRatio * this._resolution;

		this.renderTarget.setSize( effectiveWidth, effectiveHeight );

		if ( this._scissor !== null ) this.renderTarget.scissor.copy( this._scissor );
		if ( this._viewport !== null ) this.renderTarget.viewport.copy( this._viewport );

	}
```
</details>

### `PassNode.setScissor(x: number | Vector4, y: number, width: number, height: number): void`

**JSDoc:**
```typescript
/**
	 * This method allows to define the pass's scissor rectangle. By default, the scissor rectangle is kept
	 * in sync with the pass's dimensions. To reverse the process and use auto-sizing again, call the method
	 * with `null` as the single argument.
	 *
	 * @param {?(number | Vector4)} x - The horizontal coordinate for the lower left corner of the box in logical pixel unit.
	 * Instead of passing four arguments, the method also works with a single four-dimensional vector.
	 * @param {number} y - The vertical coordinate for the lower left corner of the box in logical pixel unit.
	 * @param {number} width - The width of the scissor box in logical pixel unit.
	 * @param {number} height - The height of the scissor box in logical pixel unit.
	 */
```

**Parameters:**

- **`x`** `number | Vector4`
- **`y`** `number`
- **`width`** `number`
- **`height`** `number`

**Returns:** `void`

**Calls:**

- `this._scissor.copy`
- `this._scissor.set`
- `this._scissor.multiplyScalar( this._pixelRatio * this._resolution ).floor`

<details><summary>Code</summary>

```typescript
setScissor( x, y, width, height ) {

		if ( x === null ) {

			this._scissor = null;

		} else {

			if ( this._scissor === null ) this._scissor = new Vector4();

			if ( x.isVector4 ) {

				this._scissor.copy( x );

			} else {

				this._scissor.set( x, y, width, height );

			}

			this._scissor.multiplyScalar( this._pixelRatio * this._resolution ).floor();

		}

	}
```
</details>

### `PassNode.setViewport(x: number | Vector4, y: number, width: number, height: number): void`

**JSDoc:**
```typescript
/**
	 * This method allows to define the pass's viewport. By default, the viewport is kept in sync
	 * with the pass's dimensions. To reverse the process and use auto-sizing again, call the method
	 * with `null` as the single argument.
	 *
	 * @param {number | Vector4} x - The horizontal coordinate for the lower left corner of the viewport origin in logical pixel unit.
	 * @param {number} y - The vertical coordinate for the lower left corner of the viewport origin  in logical pixel unit.
	 * @param {number} width - The width of the viewport in logical pixel unit.
	 * @param {number} height - The height of the viewport in logical pixel unit.
	 */
```

**Parameters:**

- **`x`** `number | Vector4`
- **`y`** `number`
- **`width`** `number`
- **`height`** `number`

**Returns:** `void`

**Calls:**

- `this._viewport.copy`
- `this._viewport.set`
- `this._viewport.multiplyScalar( this._pixelRatio * this._resolution ).floor`

<details><summary>Code</summary>

```typescript
setViewport( x, y, width, height ) {

		if ( x === null ) {

			this._viewport = null;

		} else {

			if ( this._viewport === null ) this._viewport = new Vector4();

			if ( x.isVector4 ) {

				this._viewport.copy( x );

			} else {

				this._viewport.set( x, y, width, height );

			}

			this._viewport.multiplyScalar( this._pixelRatio * this._resolution ).floor();

		}

	}
```
</details>

### `PassNode.setPixelRatio(pixelRatio: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the pixel ratio the pass's render target and updates the size.
	 *
	 * @param {number} pixelRatio - The pixel ratio to set.
	 */
```

**Parameters:**

- **`pixelRatio`** `number`

**Returns:** `void`

**Calls:**

- `this.setSize`

<details><summary>Code</summary>

```typescript
setPixelRatio( pixelRatio ) {

		this._pixelRatio = pixelRatio;

		this.setSize( this._width, this._height );

	}
```
</details>

### `PassNode.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources. Should be called when the node is no longer in use.
	 */
```

**Returns:** `void`

**Calls:**

- `this.renderTarget.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.renderTarget.dispose();

	}
```
</details>

### `pass(scene: Scene, camera: Camera, options: any): PassNode`

**Parameters:**

- **`scene`** `Scene`
- **`camera`** `Camera`
- **`options`** `any`

**Returns:** `PassNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( scene, camera, options ) => nodeObject( new PassNode( PassNode.COLOR, scene, camera, options ) )
```
</details>

### `passTexture(pass: PassNode, texture: Texture): PassTextureNode`

**Parameters:**

- **`pass`** `PassNode`
- **`texture`** `Texture`

**Returns:** `PassTextureNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( pass, texture ) => nodeObject( new PassTextureNode( pass, texture ) )
```
</details>

### `depthPass(scene: Scene, camera: Camera, options: any): PassNode`

**Parameters:**

- **`scene`** `Scene`
- **`camera`** `Camera`
- **`options`** `any`

**Returns:** `PassNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( scene, camera, options ) => nodeObject( new PassNode( PassNode.DEPTH, scene, camera, options ) )
```
</details>


---

## Classes

### `PassTextureNode`

<details><summary>Class Code</summary>

```ts
class PassTextureNode extends TextureNode {

	static get type() {

		return 'PassTextureNode';

	}

	/**
	 * Constructs a new pass texture node.
	 *
	 * @param {PassNode} passNode - The pass node.
	 * @param {Texture} texture - The output texture.
	 */
	constructor( passNode, texture ) {

		super( texture );

		/**
		 * A reference to the pass node.
		 *
		 * @type {PassNode}
		 */
		this.passNode = passNode;

		this.setUpdateMatrix( false );

	}

	setup( builder ) {

		this.passNode.build( builder );

		return super.setup( builder );

	}

	clone() {

		return new this.constructor( this.passNode, this.value );

	}

}
```
</details>

#### Methods

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		this.passNode.build( builder );

		return super.setup( builder );

	}
```
</details>

##### `clone(): any`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor( this.passNode, this.value );

	}
```
</details>

### `PassMultipleTextureNode`

<details><summary>Class Code</summary>

```ts
class PassMultipleTextureNode extends PassTextureNode {

	static get type() {

		return 'PassMultipleTextureNode';

	}

	/**
	 * Constructs a new pass texture node.
	 *
	 * @param {PassNode} passNode - The pass node.
	 * @param {string} textureName - The output texture name.
	 * @param {boolean} [previousTexture=false] - Whether previous frame data should be used or not.
	 */
	constructor( passNode, textureName, previousTexture = false ) {

		// null is passed to the super call since this class does not
		// use an external texture for rendering pass data into. Instead
		// the texture is managed by the pass node itself

		super( passNode, null );

		/**
		 * The output texture name.
		 *
		 * @type {string}
		 */
		this.textureName = textureName;

		/**
		 * Whether previous frame data should be used or not.
		 *
		 * @type {boolean}
		 */
		this.previousTexture = previousTexture;

	}

	/**
	 * Updates the texture reference of this node.
	 */
	updateTexture() {

		this.value = this.previousTexture ? this.passNode.getPreviousTexture( this.textureName ) : this.passNode.getTexture( this.textureName );

	}

	setup( builder ) {

		this.updateTexture();

		return super.setup( builder );

	}

	clone() {

		const newNode = new this.constructor( this.passNode, this.textureName, this.previousTexture );
		newNode.uvNode = this.uvNode;
		newNode.levelNode = this.levelNode;
		newNode.biasNode = this.biasNode;
		newNode.sampler = this.sampler;
		newNode.depthNode = this.depthNode;
		newNode.compareNode = this.compareNode;
		newNode.gradNode = this.gradNode;

		return newNode;

	}

}
```
</details>

#### Methods

##### `updateTexture(): void`

<details><summary>Code</summary>

```ts
updateTexture() {

		this.value = this.previousTexture ? this.passNode.getPreviousTexture( this.textureName ) : this.passNode.getTexture( this.textureName );

	}
```
</details>

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		this.updateTexture();

		return super.setup( builder );

	}
```
</details>

##### `clone(): any`

<details><summary>Code</summary>

```ts
clone() {

		const newNode = new this.constructor( this.passNode, this.textureName, this.previousTexture );
		newNode.uvNode = this.uvNode;
		newNode.levelNode = this.levelNode;
		newNode.biasNode = this.biasNode;
		newNode.sampler = this.sampler;
		newNode.depthNode = this.depthNode;
		newNode.compareNode = this.compareNode;
		newNode.gradNode = this.gradNode;

		return newNode;

	}
```
</details>

### `PassNode`

<details><summary>Class Code</summary>

```ts
class PassNode extends TempNode {

	static get type() {

		return 'PassNode';

	}

	/**
	 * Constructs a new pass node.
	 *
	 * @param {('color'|'depth')} scope - The scope of the pass. The scope determines whether the node outputs color or depth.
	 * @param {Scene} scene - A reference to the scene.
	 * @param {Camera} camera - A reference to the camera.
	 * @param {Object} options - Options for the internal render target.
	 */
	constructor( scope, scene, camera, options = {} ) {

		super( 'vec4' );

		/**
		 * The scope of the pass. The scope determines whether the node outputs color or depth.
		 *
		 * @type {('color'|'depth')}
		 */
		this.scope = scope;

		/**
		 * A reference to the scene.
		 *
		 * @type {Scene}
		 */
		this.scene = scene;

		/**
		 * A reference to the camera.
		 *
		 * @type {Camera}
		 */
		this.camera = camera;

		/**
		 * Options for the internal render target.
		 *
		 * @type {Object}
		 */
		this.options = options;

		/**
		 * The pass's pixel ratio. Will be kept automatically kept in sync with the renderer's pixel ratio.
		 *
		 * @private
		 * @type {number}
		 * @default 1
		 */
		this._pixelRatio = 1;

		/**
		 * The pass's pixel width. Will be kept automatically kept in sync with the renderer's width.
		 * @private
		 * @type {number}
		 * @default 1
		 */
		this._width = 1;

		/**
		 * The pass's pixel height. Will be kept automatically kept in sync with the renderer's height.
		 * @private
		 * @type {number}
		 * @default 1
		 */
		this._height = 1;

		const depthTexture = new DepthTexture();
		depthTexture.isRenderTargetTexture = true;
		//depthTexture.type = FloatType;
		depthTexture.name = 'depth';

		const renderTarget = new RenderTarget( this._width * this._pixelRatio, this._height * this._pixelRatio, { type: HalfFloatType, ...options, } );
		renderTarget.texture.name = 'output';
		renderTarget.depthTexture = depthTexture;

		/**
		 * The pass's render target.
		 *
		 * @type {RenderTarget}
		 */
		this.renderTarget = renderTarget;

		/**
		 * A dictionary holding the internal result textures.
		 *
		 * @private
		 * @type {Object<string, Texture>}
		 */
		this._textures = {
			output: renderTarget.texture,
			depth: depthTexture
		};

		/**
		 * A dictionary holding the internal texture nodes.
		 *
		 * @private
		 * @type {Object<string, TextureNode>}
		 */
		this._textureNodes = {};

		/**
		 * A dictionary holding the internal depth nodes.
		 *
		 * @private
		 * @type {Object}
		 */
		this._linearDepthNodes = {};

		/**
		 * A dictionary holding the internal viewZ nodes.
		 *
		 * @private
		 * @type {Object}
		 */
		this._viewZNodes = {};

		/**
		 * A dictionary holding the texture data of the previous frame.
		 * Used for computing velocity/motion vectors.
		 *
		 * @private
		 * @type {Object<string, Texture>}
		 */
		this._previousTextures = {};

		/**
		 * A dictionary holding the texture nodes of the previous frame.
		 * Used for computing velocity/motion vectors.
		 *
		 * @private
		 * @type {Object<string, TextureNode>}
		 */
		this._previousTextureNodes = {};

		/**
		 * The `near` property of the camera as a uniform.
		 *
		 * @private
		 * @type {UniformNode}
		 */
		this._cameraNear = uniform( 0 );

		/**
		 * The `far` property of the camera as a uniform.
		 *
		 * @private
		 * @type {UniformNode}
		 */
		this._cameraFar = uniform( 0 );

		/**
		 * A MRT node configuring the MRT settings.
		 *
		 * @private
		 * @type {?MRTNode}
		 * @default null
		 */
		this._mrt = null;

		/**
		 * Layer object for configuring the camera that is used
		 * to produce the pass.
		 *
		 * @private
		 * @type {?Layers}
		 * @default null
		 */
		this._layers = null;

		/**
		 * Scales the resolution of the internal render target.
		 *
		 * @private
		 * @type {number}
		 * @default 1
		 */
		this._resolution = 1;

		/**
		 * Custom viewport definition.
		 *
		 * @private
		 * @type {?Vector4}
		 * @default null
		 */
		this._viewport = null;

		/**
		 * Custom scissor definition.
		 *
		 * @private
		 * @type {?Vector4}
		 * @default null
		 */
		this._scissor = null;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isPassNode = true;

		/**
		 * The `updateBeforeType` is set to `NodeUpdateType.FRAME` since the node renders the
		 * scene once per frame in its {@link PassNode#updateBefore} method.
		 *
		 * @type {string}
		 * @default 'frame'
		 */
		this.updateBeforeType = NodeUpdateType.FRAME;

		/**
		 * This flag is used for global cache.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.global = true;

	}

	/**
	 * Sets the resolution for the pass.
	 * The resolution is a factor that is multiplied with the renderer's width and height.
	 *
	 * @param {number} resolution - The resolution to set. A value of `1` means full resolution.
	 * @return {PassNode} A reference to this pass.
	 */
	setResolution( resolution ) {

		this._resolution = resolution;

		return this;

	}

	/**
	 * Gets the current resolution of the pass.
	 *
	 * @return {number} The current resolution. A value of `1` means full resolution.
	 */
	getResolution() {

		return this._resolution;

	}

	/**
	 * Sets the layer configuration that should be used when rendering the pass.
	 *
	 * @param {Layers} layers - The layers object to set.
	 * @return {PassNode} A reference to this pass.
	 */
	setLayers( layers ) {

		this._layers = layers;

		return this;

	}

	/**
	 * Gets the current layer configuration of the pass.
	 *
	 * @return {?Layers} .
	 */
	getLayers() {

		return this._layers;

	}

	/**
	 * Sets the given MRT node to setup MRT for this pass.
	 *
	 * @param {MRTNode} mrt - The MRT object.
	 * @return {PassNode} A reference to this pass.
	 */
	setMRT( mrt ) {

		this._mrt = mrt;

		return this;

	}

	/**
	 * Returns the current MRT node.
	 *
	 * @return {MRTNode} The current MRT node.
	 */
	getMRT() {

		return this._mrt;

	}

	/**
	 * Returns the texture for the given output name.
	 *
	 * @param {string} name - The output name to get the texture for.
	 * @return {Texture} The texture.
	 */
	getTexture( name ) {

		let texture = this._textures[ name ];

		if ( texture === undefined ) {

			const refTexture = this.renderTarget.texture;

			texture = refTexture.clone();
			texture.name = name;

			this._textures[ name ] = texture;

			this.renderTarget.textures.push( texture );

		}

		return texture;

	}

	/**
	 * Returns the texture holding the data of the previous frame for the given output name.
	 *
	 * @param {string} name - The output name to get the texture for.
	 * @return {Texture} The texture holding the data of the previous frame.
	 */
	getPreviousTexture( name ) {

		let texture = this._previousTextures[ name ];

		if ( texture === undefined ) {

			texture = this.getTexture( name ).clone();

			this._previousTextures[ name ] = texture;

		}

		return texture;

	}

	/**
	 * Switches current and previous textures for the given output name.
	 *
	 * @param {string} name - The output name.
	 */
	toggleTexture( name ) {

		const prevTexture = this._previousTextures[ name ];

		if ( prevTexture !== undefined ) {

			const texture = this._textures[ name ];

			const index = this.renderTarget.textures.indexOf( texture );
			this.renderTarget.textures[ index ] = prevTexture;

			this._textures[ name ] = prevTexture;
			this._previousTextures[ name ] = texture;

			this._textureNodes[ name ].updateTexture();
			this._previousTextureNodes[ name ].updateTexture();

		}

	}

	/**
	 * Returns the texture node for the given output name.
	 *
	 * @param {string} [name='output'] - The output name to get the texture node for.
	 * @return {TextureNode} The texture node.
	 */
	getTextureNode( name = 'output' ) {

		let textureNode = this._textureNodes[ name ];

		if ( textureNode === undefined ) {

			textureNode = nodeObject( new PassMultipleTextureNode( this, name ) );
			textureNode.updateTexture();
			this._textureNodes[ name ] = textureNode;

		}

		return textureNode;

	}

	/**
	 * Returns the previous texture node for the given output name.
	 *
	 * @param {string} [name='output'] - The output name to get the previous texture node for.
	 * @return {TextureNode} The previous texture node.
	 */
	getPreviousTextureNode( name = 'output' ) {

		let textureNode = this._previousTextureNodes[ name ];

		if ( textureNode === undefined ) {

			if ( this._textureNodes[ name ] === undefined ) this.getTextureNode( name );

			textureNode = nodeObject( new PassMultipleTextureNode( this, name, true ) );
			textureNode.updateTexture();
			this._previousTextureNodes[ name ] = textureNode;

		}

		return textureNode;

	}

	/**
	 * Returns a viewZ node of this pass.
	 *
	 * @param {string} [name='depth'] - The output name to get the viewZ node for. In most cases the default `'depth'` can be used however the parameter exists for custom depth outputs.
	 * @return {Node} The viewZ node.
	 */
	getViewZNode( name = 'depth' ) {

		let viewZNode = this._viewZNodes[ name ];

		if ( viewZNode === undefined ) {

			const cameraNear = this._cameraNear;
			const cameraFar = this._cameraFar;

			this._viewZNodes[ name ] = viewZNode = perspectiveDepthToViewZ( this.getTextureNode( name ), cameraNear, cameraFar );

		}

		return viewZNode;

	}

	/**
	 * Returns a linear depth node of this pass.
	 *
	 * @param {string} [name='depth'] - The output name to get the linear depth node for. In most cases the default `'depth'` can be used however the parameter exists for custom depth outputs.
	 * @return {Node} The linear depth node.
	 */
	getLinearDepthNode( name = 'depth' ) {

		let linearDepthNode = this._linearDepthNodes[ name ];

		if ( linearDepthNode === undefined ) {

			const cameraNear = this._cameraNear;
			const cameraFar = this._cameraFar;
			const viewZNode = this.getViewZNode( name );

			// TODO: just if ( builder.camera.isPerspectiveCamera )

			this._linearDepthNodes[ name ] = linearDepthNode = viewZToOrthographicDepth( viewZNode, cameraNear, cameraFar );

		}

		return linearDepthNode;

	}

	/**
	 * Precompiles the pass.
	 *
	 * Note that this method must be called after the pass configuartion is complete.
	 * So calls like `setMRT()` and `getTextureNode()` must proceed the precompilation.
	 *
	 * @async
	 * @param {Renderer} renderer - The renderer.
	 * @return {Promise} A Promise that resolves when the compile has been finished.
	 * @see {@link Renderer#compileAsync}
	 */
	async compileAsync( renderer ) {

		const currentRenderTarget = renderer.getRenderTarget();
		const currentMRT = renderer.getMRT();

		renderer.setRenderTarget( this.renderTarget );
		renderer.setMRT( this._mrt );

		await renderer.compileAsync( this.scene, this.camera );

		renderer.setRenderTarget( currentRenderTarget );
		renderer.setMRT( currentMRT );

	}

	setup( { renderer } ) {

		this.renderTarget.samples = this.options.samples === undefined ? renderer.samples : this.options.samples;

		this.renderTarget.texture.type = renderer.getColorBufferType();

		return this.scope === PassNode.COLOR ? this.getTextureNode() : this.getLinearDepthNode();

	}

	updateBefore( frame ) {

		const { renderer } = frame;
		const { scene } = this;

		let camera;
		let pixelRatio;

		const outputRenderTarget = renderer.getOutputRenderTarget();

		if ( outputRenderTarget && outputRenderTarget.isXRRenderTarget === true ) {

			pixelRatio = 1;
			camera = renderer.xr.getCamera();

			renderer.xr.updateCamera( camera );

			_size.set( outputRenderTarget.width, outputRenderTarget.height );

		} else {

			camera = this.camera;
			pixelRatio = renderer.getPixelRatio();

			renderer.getSize( _size );

		}

		this._pixelRatio = pixelRatio;

		this.setSize( _size.width, _size.height );

		const currentRenderTarget = renderer.getRenderTarget();
		const currentMRT = renderer.getMRT();
		const currentMask = camera.layers.mask;

		this._cameraNear.value = camera.near;
		this._cameraFar.value = camera.far;

		if ( this._layers !== null ) {

			camera.layers.mask = this._layers.mask;

		}

		for ( const name in this._previousTextures ) {

			this.toggleTexture( name );

		}

		renderer.setRenderTarget( this.renderTarget );
		renderer.setMRT( this._mrt );

		renderer.render( scene, camera );

		renderer.setRenderTarget( currentRenderTarget );
		renderer.setMRT( currentMRT );

		camera.layers.mask = currentMask;

	}

	/**
	 * Sets the size of the pass's render target. Honors the pixel ratio.
	 *
	 * @param {number} width - The width to set.
	 * @param {number} height - The height to set.
	 */
	setSize( width, height ) {

		this._width = width;
		this._height = height;

		const effectiveWidth = this._width * this._pixelRatio * this._resolution;
		const effectiveHeight = this._height * this._pixelRatio * this._resolution;

		this.renderTarget.setSize( effectiveWidth, effectiveHeight );

		if ( this._scissor !== null ) this.renderTarget.scissor.copy( this._scissor );
		if ( this._viewport !== null ) this.renderTarget.viewport.copy( this._viewport );

	}

	/**
	 * This method allows to define the pass's scissor rectangle. By default, the scissor rectangle is kept
	 * in sync with the pass's dimensions. To reverse the process and use auto-sizing again, call the method
	 * with `null` as the single argument.
	 *
	 * @param {?(number | Vector4)} x - The horizontal coordinate for the lower left corner of the box in logical pixel unit.
	 * Instead of passing four arguments, the method also works with a single four-dimensional vector.
	 * @param {number} y - The vertical coordinate for the lower left corner of the box in logical pixel unit.
	 * @param {number} width - The width of the scissor box in logical pixel unit.
	 * @param {number} height - The height of the scissor box in logical pixel unit.
	 */
	setScissor( x, y, width, height ) {

		if ( x === null ) {

			this._scissor = null;

		} else {

			if ( this._scissor === null ) this._scissor = new Vector4();

			if ( x.isVector4 ) {

				this._scissor.copy( x );

			} else {

				this._scissor.set( x, y, width, height );

			}

			this._scissor.multiplyScalar( this._pixelRatio * this._resolution ).floor();

		}

	}

	/**
	 * This method allows to define the pass's viewport. By default, the viewport is kept in sync
	 * with the pass's dimensions. To reverse the process and use auto-sizing again, call the method
	 * with `null` as the single argument.
	 *
	 * @param {number | Vector4} x - The horizontal coordinate for the lower left corner of the viewport origin in logical pixel unit.
	 * @param {number} y - The vertical coordinate for the lower left corner of the viewport origin  in logical pixel unit.
	 * @param {number} width - The width of the viewport in logical pixel unit.
	 * @param {number} height - The height of the viewport in logical pixel unit.
	 */
	setViewport( x, y, width, height ) {

		if ( x === null ) {

			this._viewport = null;

		} else {

			if ( this._viewport === null ) this._viewport = new Vector4();

			if ( x.isVector4 ) {

				this._viewport.copy( x );

			} else {

				this._viewport.set( x, y, width, height );

			}

			this._viewport.multiplyScalar( this._pixelRatio * this._resolution ).floor();

		}

	}

	/**
	 * Sets the pixel ratio the pass's render target and updates the size.
	 *
	 * @param {number} pixelRatio - The pixel ratio to set.
	 */
	setPixelRatio( pixelRatio ) {

		this._pixelRatio = pixelRatio;

		this.setSize( this._width, this._height );

	}

	/**
	 * Frees internal resources. Should be called when the node is no longer in use.
	 */
	dispose() {

		this.renderTarget.dispose();

	}


}
```
</details>

#### Methods

##### `setResolution(resolution: number): PassNode`

<details><summary>Code</summary>

```ts
setResolution( resolution ) {

		this._resolution = resolution;

		return this;

	}
```
</details>

##### `getResolution(): number`

<details><summary>Code</summary>

```ts
getResolution() {

		return this._resolution;

	}
```
</details>

##### `setLayers(layers: Layers): PassNode`

<details><summary>Code</summary>

```ts
setLayers( layers ) {

		this._layers = layers;

		return this;

	}
```
</details>

##### `getLayers(): Layers`

<details><summary>Code</summary>

```ts
getLayers() {

		return this._layers;

	}
```
</details>

##### `setMRT(mrt: MRTNode): PassNode`

<details><summary>Code</summary>

```ts
setMRT( mrt ) {

		this._mrt = mrt;

		return this;

	}
```
</details>

##### `getMRT(): MRTNode`

<details><summary>Code</summary>

```ts
getMRT() {

		return this._mrt;

	}
```
</details>

##### `getTexture(name: string): Texture`

<details><summary>Code</summary>

```ts
getTexture( name ) {

		let texture = this._textures[ name ];

		if ( texture === undefined ) {

			const refTexture = this.renderTarget.texture;

			texture = refTexture.clone();
			texture.name = name;

			this._textures[ name ] = texture;

			this.renderTarget.textures.push( texture );

		}

		return texture;

	}
```
</details>

##### `getPreviousTexture(name: string): Texture`

<details><summary>Code</summary>

```ts
getPreviousTexture( name ) {

		let texture = this._previousTextures[ name ];

		if ( texture === undefined ) {

			texture = this.getTexture( name ).clone();

			this._previousTextures[ name ] = texture;

		}

		return texture;

	}
```
</details>

##### `toggleTexture(name: string): void`

<details><summary>Code</summary>

```ts
toggleTexture( name ) {

		const prevTexture = this._previousTextures[ name ];

		if ( prevTexture !== undefined ) {

			const texture = this._textures[ name ];

			const index = this.renderTarget.textures.indexOf( texture );
			this.renderTarget.textures[ index ] = prevTexture;

			this._textures[ name ] = prevTexture;
			this._previousTextures[ name ] = texture;

			this._textureNodes[ name ].updateTexture();
			this._previousTextureNodes[ name ].updateTexture();

		}

	}
```
</details>

##### `getTextureNode(name: string): TextureNode`

<details><summary>Code</summary>

```ts
getTextureNode( name = 'output' ) {

		let textureNode = this._textureNodes[ name ];

		if ( textureNode === undefined ) {

			textureNode = nodeObject( new PassMultipleTextureNode( this, name ) );
			textureNode.updateTexture();
			this._textureNodes[ name ] = textureNode;

		}

		return textureNode;

	}
```
</details>

##### `getPreviousTextureNode(name: string): TextureNode`

<details><summary>Code</summary>

```ts
getPreviousTextureNode( name = 'output' ) {

		let textureNode = this._previousTextureNodes[ name ];

		if ( textureNode === undefined ) {

			if ( this._textureNodes[ name ] === undefined ) this.getTextureNode( name );

			textureNode = nodeObject( new PassMultipleTextureNode( this, name, true ) );
			textureNode.updateTexture();
			this._previousTextureNodes[ name ] = textureNode;

		}

		return textureNode;

	}
```
</details>

##### `getViewZNode(name: string): Node`

<details><summary>Code</summary>

```ts
getViewZNode( name = 'depth' ) {

		let viewZNode = this._viewZNodes[ name ];

		if ( viewZNode === undefined ) {

			const cameraNear = this._cameraNear;
			const cameraFar = this._cameraFar;

			this._viewZNodes[ name ] = viewZNode = perspectiveDepthToViewZ( this.getTextureNode( name ), cameraNear, cameraFar );

		}

		return viewZNode;

	}
```
</details>

##### `getLinearDepthNode(name: string): Node`

<details><summary>Code</summary>

```ts
getLinearDepthNode( name = 'depth' ) {

		let linearDepthNode = this._linearDepthNodes[ name ];

		if ( linearDepthNode === undefined ) {

			const cameraNear = this._cameraNear;
			const cameraFar = this._cameraFar;
			const viewZNode = this.getViewZNode( name );

			// TODO: just if ( builder.camera.isPerspectiveCamera )

			this._linearDepthNodes[ name ] = linearDepthNode = viewZToOrthographicDepth( viewZNode, cameraNear, cameraFar );

		}

		return linearDepthNode;

	}
```
</details>

##### `compileAsync(renderer: Renderer): Promise<any>`

<details><summary>Code</summary>

```ts
async compileAsync( renderer ) {

		const currentRenderTarget = renderer.getRenderTarget();
		const currentMRT = renderer.getMRT();

		renderer.setRenderTarget( this.renderTarget );
		renderer.setMRT( this._mrt );

		await renderer.compileAsync( this.scene, this.camera );

		renderer.setRenderTarget( currentRenderTarget );
		renderer.setMRT( currentMRT );

	}
```
</details>

##### `setup({ renderer }: any): Node | TextureNode`

<details><summary>Code</summary>

```ts
setup( { renderer } ) {

		this.renderTarget.samples = this.options.samples === undefined ? renderer.samples : this.options.samples;

		this.renderTarget.texture.type = renderer.getColorBufferType();

		return this.scope === PassNode.COLOR ? this.getTextureNode() : this.getLinearDepthNode();

	}
```
</details>

##### `updateBefore(frame: any): void`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		const { renderer } = frame;
		const { scene } = this;

		let camera;
		let pixelRatio;

		const outputRenderTarget = renderer.getOutputRenderTarget();

		if ( outputRenderTarget && outputRenderTarget.isXRRenderTarget === true ) {

			pixelRatio = 1;
			camera = renderer.xr.getCamera();

			renderer.xr.updateCamera( camera );

			_size.set( outputRenderTarget.width, outputRenderTarget.height );

		} else {

			camera = this.camera;
			pixelRatio = renderer.getPixelRatio();

			renderer.getSize( _size );

		}

		this._pixelRatio = pixelRatio;

		this.setSize( _size.width, _size.height );

		const currentRenderTarget = renderer.getRenderTarget();
		const currentMRT = renderer.getMRT();
		const currentMask = camera.layers.mask;

		this._cameraNear.value = camera.near;
		this._cameraFar.value = camera.far;

		if ( this._layers !== null ) {

			camera.layers.mask = this._layers.mask;

		}

		for ( const name in this._previousTextures ) {

			this.toggleTexture( name );

		}

		renderer.setRenderTarget( this.renderTarget );
		renderer.setMRT( this._mrt );

		renderer.render( scene, camera );

		renderer.setRenderTarget( currentRenderTarget );
		renderer.setMRT( currentMRT );

		camera.layers.mask = currentMask;

	}
```
</details>

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		this._width = width;
		this._height = height;

		const effectiveWidth = this._width * this._pixelRatio * this._resolution;
		const effectiveHeight = this._height * this._pixelRatio * this._resolution;

		this.renderTarget.setSize( effectiveWidth, effectiveHeight );

		if ( this._scissor !== null ) this.renderTarget.scissor.copy( this._scissor );
		if ( this._viewport !== null ) this.renderTarget.viewport.copy( this._viewport );

	}
```
</details>

##### `setScissor(x: number | Vector4, y: number, width: number, height: number): void`

<details><summary>Code</summary>

```ts
setScissor( x, y, width, height ) {

		if ( x === null ) {

			this._scissor = null;

		} else {

			if ( this._scissor === null ) this._scissor = new Vector4();

			if ( x.isVector4 ) {

				this._scissor.copy( x );

			} else {

				this._scissor.set( x, y, width, height );

			}

			this._scissor.multiplyScalar( this._pixelRatio * this._resolution ).floor();

		}

	}
```
</details>

##### `setViewport(x: number | Vector4, y: number, width: number, height: number): void`

<details><summary>Code</summary>

```ts
setViewport( x, y, width, height ) {

		if ( x === null ) {

			this._viewport = null;

		} else {

			if ( this._viewport === null ) this._viewport = new Vector4();

			if ( x.isVector4 ) {

				this._viewport.copy( x );

			} else {

				this._viewport.set( x, y, width, height );

			}

			this._viewport.multiplyScalar( this._pixelRatio * this._resolution ).floor();

		}

	}
```
</details>

##### `setPixelRatio(pixelRatio: number): void`

<details><summary>Code</summary>

```ts
setPixelRatio( pixelRatio ) {

		this._pixelRatio = pixelRatio;

		this.setSize( this._width, this._height );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.renderTarget.dispose();

	}
```
</details>


---