[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `EffectComposer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/EffectComposer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Clock` | `three` |
| `HalfFloatType` | `three` |
| `NoBlending` | `three` |
| `Vector2` | `three` |
| `WebGLRenderTarget` | `three` |
| `CopyShader` | `../shaders/CopyShader.js` |
| `ShaderPass` | `./ShaderPass.js` |
| `ClearMaskPass` | `./MaskPass.js` |
| `MaskPass` | `./MaskPass.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `tmp` | `WebGLRenderTarget` | let/var | `this.readBuffer` | ✗ |
| `maskActive` | `boolean` | let/var | `false` | ✗ |
| `pass` | `Pass` | let/var | `this.passes[ i ]` | ✗ |
| `stencil` | `any` | let/var | `this.renderer.state.buffers.stencil` | ✗ |
| `effectiveWidth` | `number` | let/var | `this._width * this._pixelRatio` | ✗ |
| `effectiveHeight` | `number` | let/var | `this._height * this._pixelRatio` | ✗ |


---

## Functions

### `EffectComposer.swapBuffers(): void`

**JSDoc:**
```typescript
/**
	 * Swaps the internal read/write buffers.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
swapBuffers() {

		const tmp = this.readBuffer;
		this.readBuffer = this.writeBuffer;
		this.writeBuffer = tmp;

	}
```
</details>

### `EffectComposer.addPass(pass: Pass): void`

**JSDoc:**
```typescript
/**
	 * Adds the given pass to the pass chain.
	 *
	 * @param {Pass} pass - The pass to add.
	 */
```

**Parameters:**

- **`pass`** `Pass`

**Returns:** `void`

**Calls:**

- `this.passes.push`
- `pass.setSize`

<details><summary>Code</summary>

```typescript
addPass( pass ) {

		this.passes.push( pass );
		pass.setSize( this._width * this._pixelRatio, this._height * this._pixelRatio );

	}
```
</details>

### `EffectComposer.insertPass(pass: Pass, index: number): void`

**JSDoc:**
```typescript
/**
	 * Inserts the given pass at a given index.
	 *
	 * @param {Pass} pass - The pass to insert.
	 * @param {number} index - The index into the pass chain.
	 */
```

**Parameters:**

- **`pass`** `Pass`
- **`index`** `number`

**Returns:** `void`

**Calls:**

- `this.passes.splice`
- `pass.setSize`

<details><summary>Code</summary>

```typescript
insertPass( pass, index ) {

		this.passes.splice( index, 0, pass );
		pass.setSize( this._width * this._pixelRatio, this._height * this._pixelRatio );

	}
```
</details>

### `EffectComposer.removePass(pass: Pass): void`

**JSDoc:**
```typescript
/**
	 * Removes the given pass from the pass chain.
	 *
	 * @param {Pass} pass - The pass to remove.
	 */
```

**Parameters:**

- **`pass`** `Pass`

**Returns:** `void`

**Calls:**

- `this.passes.indexOf`
- `this.passes.splice`

<details><summary>Code</summary>

```typescript
removePass( pass ) {

		const index = this.passes.indexOf( pass );

		if ( index !== - 1 ) {

			this.passes.splice( index, 1 );

		}

	}
```
</details>

### `EffectComposer.isLastEnabledPass(passIndex: number): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the pass for the given index is the last enabled pass in the pass chain.
	 *
	 * @param {number} passIndex - The pass index.
	 * @return {boolean} Whether the pass for the given index is the last pass in the pass chain.
	 */
```

**Parameters:**

- **`passIndex`** `number`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
isLastEnabledPass( passIndex ) {

		for ( let i = passIndex + 1; i < this.passes.length; i ++ ) {

			if ( this.passes[ i ].enabled ) {

				return false;

			}

		}

		return true;

	}
```
</details>

### `EffectComposer.render(deltaTime: number): void`

**JSDoc:**
```typescript
/**
	 * Executes all enabled post-processing passes in order to produce the final frame.
	 *
	 * @param {number} deltaTime - The delta time in seconds. If not given, the composer computes
	 * its own time delta value.
	 */
```

**Parameters:**

- **`deltaTime`** `number`

**Returns:** `void`

**Calls:**

- `this.clock.getDelta`
- `this.renderer.getRenderTarget`
- `this.isLastEnabledPass`
- `pass.render`
- `this.renderer.getContext`
- `stencil.setFunc`
- `this.copyPass.render`
- `this.swapBuffers`
- `this.renderer.setRenderTarget`

**Internal Comments:**
```
// deltaTime value is in seconds
//context.stencilFunc( context.NOTEQUAL, 1, 0xffffffff ); (x4)
//context.stencilFunc( context.EQUAL, 1, 0xffffffff ); (x4)
```

<details><summary>Code</summary>

```typescript
render( deltaTime ) {

		// deltaTime value is in seconds

		if ( deltaTime === undefined ) {

			deltaTime = this.clock.getDelta();

		}

		const currentRenderTarget = this.renderer.getRenderTarget();

		let maskActive = false;

		for ( let i = 0, il = this.passes.length; i < il; i ++ ) {

			const pass = this.passes[ i ];

			if ( pass.enabled === false ) continue;

			pass.renderToScreen = ( this.renderToScreen && this.isLastEnabledPass( i ) );
			pass.render( this.renderer, this.writeBuffer, this.readBuffer, deltaTime, maskActive );

			if ( pass.needsSwap ) {

				if ( maskActive ) {

					const context = this.renderer.getContext();
					const stencil = this.renderer.state.buffers.stencil;

					//context.stencilFunc( context.NOTEQUAL, 1, 0xffffffff );
					stencil.setFunc( context.NOTEQUAL, 1, 0xffffffff );

					this.copyPass.render( this.renderer, this.writeBuffer, this.readBuffer, deltaTime );

					//context.stencilFunc( context.EQUAL, 1, 0xffffffff );
					stencil.setFunc( context.EQUAL, 1, 0xffffffff );

				}

				this.swapBuffers();

			}

			if ( MaskPass !== undefined ) {

				if ( pass instanceof MaskPass ) {

					maskActive = true;

				} else if ( pass instanceof ClearMaskPass ) {

					maskActive = false;

				}

			}

		}

		this.renderer.setRenderTarget( currentRenderTarget );

	}
```
</details>

### `EffectComposer.reset(renderTarget: WebGLRenderTarget): void`

**JSDoc:**
```typescript
/**
	 * Resets the internal state of the EffectComposer.
	 *
	 * @param {WebGLRenderTarget} [renderTarget] - This render target has the same purpose like
	 * the one from the constructor. If set, it is used to setup the read and write buffers.
	 */
```

**Parameters:**

- **`renderTarget`** `WebGLRenderTarget`

**Returns:** `void`

**Calls:**

- `this.renderer.getSize`
- `this.renderer.getPixelRatio`
- `this.renderTarget1.clone`
- `renderTarget.setSize`
- `this.renderTarget1.dispose`
- `this.renderTarget2.dispose`
- `renderTarget.clone`

<details><summary>Code</summary>

```typescript
reset( renderTarget ) {

		if ( renderTarget === undefined ) {

			const size = this.renderer.getSize( new Vector2() );
			this._pixelRatio = this.renderer.getPixelRatio();
			this._width = size.width;
			this._height = size.height;

			renderTarget = this.renderTarget1.clone();
			renderTarget.setSize( this._width * this._pixelRatio, this._height * this._pixelRatio );

		}

		this.renderTarget1.dispose();
		this.renderTarget2.dispose();
		this.renderTarget1 = renderTarget;
		this.renderTarget2 = renderTarget.clone();

		this.writeBuffer = this.renderTarget1;
		this.readBuffer = this.renderTarget2;

	}
```
</details>

### `EffectComposer.setSize(width: number, height: number): void`

**JSDoc:**
```typescript
/**
	 * Resizes the internal read and write buffers as well as all passes. Similar to {@link WebGLRenderer#setSize},
	 * this method honors the current pixel ration.
	 *
	 * @param {number} width - The width in logical pixels.
	 * @param {number} height - The height in logical pixels.
	 */
```

**Parameters:**

- **`width`** `number`
- **`height`** `number`

**Returns:** `void`

**Calls:**

- `this.renderTarget1.setSize`
- `this.renderTarget2.setSize`
- `this.passes[ i ].setSize`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		this._width = width;
		this._height = height;

		const effectiveWidth = this._width * this._pixelRatio;
		const effectiveHeight = this._height * this._pixelRatio;

		this.renderTarget1.setSize( effectiveWidth, effectiveHeight );
		this.renderTarget2.setSize( effectiveWidth, effectiveHeight );

		for ( let i = 0; i < this.passes.length; i ++ ) {

			this.passes[ i ].setSize( effectiveWidth, effectiveHeight );

		}

	}
```
</details>

### `EffectComposer.setPixelRatio(pixelRatio: number): void`

**JSDoc:**
```typescript
/**
	 * Sets device pixel ratio. This is usually used for HiDPI device to prevent blurring output.
	 * Setting the pixel ratio will automatically resize the composer.
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

### `EffectComposer.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the composer is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.renderTarget1.dispose`
- `this.renderTarget2.dispose`
- `this.copyPass.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.renderTarget1.dispose();
		this.renderTarget2.dispose();

		this.copyPass.dispose();

	}
```
</details>


---

## Classes

### `EffectComposer`

<details><summary>Class Code</summary>

```ts
class EffectComposer {

	/**
	 * Constructs a new effect composer.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {WebGLRenderTarget} [renderTarget] - This render target and a clone will
	 * be used as the internal read and write buffers. If not given, the composer creates
	 * the buffers automatically.
	 */
	constructor( renderer, renderTarget ) {

		/**
		 * The renderer.
		 *
		 * @type {WebGLRenderer}
		 */
		this.renderer = renderer;

		this._pixelRatio = renderer.getPixelRatio();

		if ( renderTarget === undefined ) {

			const size = renderer.getSize( new Vector2() );
			this._width = size.width;
			this._height = size.height;

			renderTarget = new WebGLRenderTarget( this._width * this._pixelRatio, this._height * this._pixelRatio, { type: HalfFloatType } );
			renderTarget.texture.name = 'EffectComposer.rt1';

		} else {

			this._width = renderTarget.width;
			this._height = renderTarget.height;

		}

		this.renderTarget1 = renderTarget;
		this.renderTarget2 = renderTarget.clone();
		this.renderTarget2.texture.name = 'EffectComposer.rt2';

		/**
		 * A reference to the internal write buffer. Passes usually write
		 * their result into this buffer.
		 *
		 * @type {WebGLRenderTarget}
		 */
		this.writeBuffer = this.renderTarget1;

		/**
		 * A reference to the internal read buffer. Passes usually read
		 * the previous render result from this buffer.
		 *
		 * @type {WebGLRenderTarget}
		 */
		this.readBuffer = this.renderTarget2;

		/**
		 * Whether the final pass is rendered to the screen (default framebuffer) or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.renderToScreen = true;

		/**
		 * An array representing the (ordered) chain of post-processing passes.
		 *
		 * @type {Array<Pass>}
		 */
		this.passes = [];

		/**
		 * A copy pass used for internal swap operations.
		 *
		 * @private
		 * @type {ShaderPass}
		 */
		this.copyPass = new ShaderPass( CopyShader );
		this.copyPass.material.blending = NoBlending;

		/**
		 * The internal clock for managing time data.
		 *
		 * @private
		 * @type {Clock}
		 */
		this.clock = new Clock();

	}

	/**
	 * Swaps the internal read/write buffers.
	 */
	swapBuffers() {

		const tmp = this.readBuffer;
		this.readBuffer = this.writeBuffer;
		this.writeBuffer = tmp;

	}

	/**
	 * Adds the given pass to the pass chain.
	 *
	 * @param {Pass} pass - The pass to add.
	 */
	addPass( pass ) {

		this.passes.push( pass );
		pass.setSize( this._width * this._pixelRatio, this._height * this._pixelRatio );

	}

	/**
	 * Inserts the given pass at a given index.
	 *
	 * @param {Pass} pass - The pass to insert.
	 * @param {number} index - The index into the pass chain.
	 */
	insertPass( pass, index ) {

		this.passes.splice( index, 0, pass );
		pass.setSize( this._width * this._pixelRatio, this._height * this._pixelRatio );

	}

	/**
	 * Removes the given pass from the pass chain.
	 *
	 * @param {Pass} pass - The pass to remove.
	 */
	removePass( pass ) {

		const index = this.passes.indexOf( pass );

		if ( index !== - 1 ) {

			this.passes.splice( index, 1 );

		}

	}

	/**
	 * Returns `true` if the pass for the given index is the last enabled pass in the pass chain.
	 *
	 * @param {number} passIndex - The pass index.
	 * @return {boolean} Whether the pass for the given index is the last pass in the pass chain.
	 */
	isLastEnabledPass( passIndex ) {

		for ( let i = passIndex + 1; i < this.passes.length; i ++ ) {

			if ( this.passes[ i ].enabled ) {

				return false;

			}

		}

		return true;

	}

	/**
	 * Executes all enabled post-processing passes in order to produce the final frame.
	 *
	 * @param {number} deltaTime - The delta time in seconds. If not given, the composer computes
	 * its own time delta value.
	 */
	render( deltaTime ) {

		// deltaTime value is in seconds

		if ( deltaTime === undefined ) {

			deltaTime = this.clock.getDelta();

		}

		const currentRenderTarget = this.renderer.getRenderTarget();

		let maskActive = false;

		for ( let i = 0, il = this.passes.length; i < il; i ++ ) {

			const pass = this.passes[ i ];

			if ( pass.enabled === false ) continue;

			pass.renderToScreen = ( this.renderToScreen && this.isLastEnabledPass( i ) );
			pass.render( this.renderer, this.writeBuffer, this.readBuffer, deltaTime, maskActive );

			if ( pass.needsSwap ) {

				if ( maskActive ) {

					const context = this.renderer.getContext();
					const stencil = this.renderer.state.buffers.stencil;

					//context.stencilFunc( context.NOTEQUAL, 1, 0xffffffff );
					stencil.setFunc( context.NOTEQUAL, 1, 0xffffffff );

					this.copyPass.render( this.renderer, this.writeBuffer, this.readBuffer, deltaTime );

					//context.stencilFunc( context.EQUAL, 1, 0xffffffff );
					stencil.setFunc( context.EQUAL, 1, 0xffffffff );

				}

				this.swapBuffers();

			}

			if ( MaskPass !== undefined ) {

				if ( pass instanceof MaskPass ) {

					maskActive = true;

				} else if ( pass instanceof ClearMaskPass ) {

					maskActive = false;

				}

			}

		}

		this.renderer.setRenderTarget( currentRenderTarget );

	}

	/**
	 * Resets the internal state of the EffectComposer.
	 *
	 * @param {WebGLRenderTarget} [renderTarget] - This render target has the same purpose like
	 * the one from the constructor. If set, it is used to setup the read and write buffers.
	 */
	reset( renderTarget ) {

		if ( renderTarget === undefined ) {

			const size = this.renderer.getSize( new Vector2() );
			this._pixelRatio = this.renderer.getPixelRatio();
			this._width = size.width;
			this._height = size.height;

			renderTarget = this.renderTarget1.clone();
			renderTarget.setSize( this._width * this._pixelRatio, this._height * this._pixelRatio );

		}

		this.renderTarget1.dispose();
		this.renderTarget2.dispose();
		this.renderTarget1 = renderTarget;
		this.renderTarget2 = renderTarget.clone();

		this.writeBuffer = this.renderTarget1;
		this.readBuffer = this.renderTarget2;

	}

	/**
	 * Resizes the internal read and write buffers as well as all passes. Similar to {@link WebGLRenderer#setSize},
	 * this method honors the current pixel ration.
	 *
	 * @param {number} width - The width in logical pixels.
	 * @param {number} height - The height in logical pixels.
	 */
	setSize( width, height ) {

		this._width = width;
		this._height = height;

		const effectiveWidth = this._width * this._pixelRatio;
		const effectiveHeight = this._height * this._pixelRatio;

		this.renderTarget1.setSize( effectiveWidth, effectiveHeight );
		this.renderTarget2.setSize( effectiveWidth, effectiveHeight );

		for ( let i = 0; i < this.passes.length; i ++ ) {

			this.passes[ i ].setSize( effectiveWidth, effectiveHeight );

		}

	}

	/**
	 * Sets device pixel ratio. This is usually used for HiDPI device to prevent blurring output.
	 * Setting the pixel ratio will automatically resize the composer.
	 *
	 * @param {number} pixelRatio - The pixel ratio to set.
	 */
	setPixelRatio( pixelRatio ) {

		this._pixelRatio = pixelRatio;

		this.setSize( this._width, this._height );

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the composer is no longer used in your app.
	 */
	dispose() {

		this.renderTarget1.dispose();
		this.renderTarget2.dispose();

		this.copyPass.dispose();

	}

}
```
</details>

#### Methods

##### `swapBuffers(): void`

<details><summary>Code</summary>

```ts
swapBuffers() {

		const tmp = this.readBuffer;
		this.readBuffer = this.writeBuffer;
		this.writeBuffer = tmp;

	}
```
</details>

##### `addPass(pass: Pass): void`

<details><summary>Code</summary>

```ts
addPass( pass ) {

		this.passes.push( pass );
		pass.setSize( this._width * this._pixelRatio, this._height * this._pixelRatio );

	}
```
</details>

##### `insertPass(pass: Pass, index: number): void`

<details><summary>Code</summary>

```ts
insertPass( pass, index ) {

		this.passes.splice( index, 0, pass );
		pass.setSize( this._width * this._pixelRatio, this._height * this._pixelRatio );

	}
```
</details>

##### `removePass(pass: Pass): void`

<details><summary>Code</summary>

```ts
removePass( pass ) {

		const index = this.passes.indexOf( pass );

		if ( index !== - 1 ) {

			this.passes.splice( index, 1 );

		}

	}
```
</details>

##### `isLastEnabledPass(passIndex: number): boolean`

<details><summary>Code</summary>

```ts
isLastEnabledPass( passIndex ) {

		for ( let i = passIndex + 1; i < this.passes.length; i ++ ) {

			if ( this.passes[ i ].enabled ) {

				return false;

			}

		}

		return true;

	}
```
</details>

##### `render(deltaTime: number): void`

<details><summary>Code</summary>

```ts
render( deltaTime ) {

		// deltaTime value is in seconds

		if ( deltaTime === undefined ) {

			deltaTime = this.clock.getDelta();

		}

		const currentRenderTarget = this.renderer.getRenderTarget();

		let maskActive = false;

		for ( let i = 0, il = this.passes.length; i < il; i ++ ) {

			const pass = this.passes[ i ];

			if ( pass.enabled === false ) continue;

			pass.renderToScreen = ( this.renderToScreen && this.isLastEnabledPass( i ) );
			pass.render( this.renderer, this.writeBuffer, this.readBuffer, deltaTime, maskActive );

			if ( pass.needsSwap ) {

				if ( maskActive ) {

					const context = this.renderer.getContext();
					const stencil = this.renderer.state.buffers.stencil;

					//context.stencilFunc( context.NOTEQUAL, 1, 0xffffffff );
					stencil.setFunc( context.NOTEQUAL, 1, 0xffffffff );

					this.copyPass.render( this.renderer, this.writeBuffer, this.readBuffer, deltaTime );

					//context.stencilFunc( context.EQUAL, 1, 0xffffffff );
					stencil.setFunc( context.EQUAL, 1, 0xffffffff );

				}

				this.swapBuffers();

			}

			if ( MaskPass !== undefined ) {

				if ( pass instanceof MaskPass ) {

					maskActive = true;

				} else if ( pass instanceof ClearMaskPass ) {

					maskActive = false;

				}

			}

		}

		this.renderer.setRenderTarget( currentRenderTarget );

	}
```
</details>

##### `reset(renderTarget: WebGLRenderTarget): void`

<details><summary>Code</summary>

```ts
reset( renderTarget ) {

		if ( renderTarget === undefined ) {

			const size = this.renderer.getSize( new Vector2() );
			this._pixelRatio = this.renderer.getPixelRatio();
			this._width = size.width;
			this._height = size.height;

			renderTarget = this.renderTarget1.clone();
			renderTarget.setSize( this._width * this._pixelRatio, this._height * this._pixelRatio );

		}

		this.renderTarget1.dispose();
		this.renderTarget2.dispose();
		this.renderTarget1 = renderTarget;
		this.renderTarget2 = renderTarget.clone();

		this.writeBuffer = this.renderTarget1;
		this.readBuffer = this.renderTarget2;

	}
```
</details>

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		this._width = width;
		this._height = height;

		const effectiveWidth = this._width * this._pixelRatio;
		const effectiveHeight = this._height * this._pixelRatio;

		this.renderTarget1.setSize( effectiveWidth, effectiveHeight );
		this.renderTarget2.setSize( effectiveWidth, effectiveHeight );

		for ( let i = 0; i < this.passes.length; i ++ ) {

			this.passes[ i ].setSize( effectiveWidth, effectiveHeight );

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

		this.renderTarget1.dispose();
		this.renderTarget2.dispose();

		this.copyPass.dispose();

	}
```
</details>


---