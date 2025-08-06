[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `WebGLState.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 29 |
| 🧱 Classes | 1 |
| 📦 Imports | 34 |
| 📊 Variables & Constants | 15 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgl-fallback/utils/WebGLState.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `CullFaceNone` | `../../../constants.js` |
| `CullFaceBack` | `../../../constants.js` |
| `CullFaceFront` | `../../../constants.js` |
| `DoubleSide` | `../../../constants.js` |
| `BackSide` | `../../../constants.js` |
| `NormalBlending` | `../../../constants.js` |
| `NoBlending` | `../../../constants.js` |
| `CustomBlending` | `../../../constants.js` |
| `AddEquation` | `../../../constants.js` |
| `AdditiveBlending` | `../../../constants.js` |
| `SubtractiveBlending` | `../../../constants.js` |
| `MultiplyBlending` | `../../../constants.js` |
| `SubtractEquation` | `../../../constants.js` |
| `ReverseSubtractEquation` | `../../../constants.js` |
| `ZeroFactor` | `../../../constants.js` |
| `OneFactor` | `../../../constants.js` |
| `SrcColorFactor` | `../../../constants.js` |
| `SrcAlphaFactor` | `../../../constants.js` |
| `SrcAlphaSaturateFactor` | `../../../constants.js` |
| `DstColorFactor` | `../../../constants.js` |
| `DstAlphaFactor` | `../../../constants.js` |
| `OneMinusSrcColorFactor` | `../../../constants.js` |
| `OneMinusSrcAlphaFactor` | `../../../constants.js` |
| `OneMinusDstColorFactor` | `../../../constants.js` |
| `OneMinusDstAlphaFactor` | `../../../constants.js` |
| `NeverDepth` | `../../../constants.js` |
| `AlwaysDepth` | `../../../constants.js` |
| `LessDepth` | `../../../constants.js` |
| `LessEqualDepth` | `../../../constants.js` |
| `EqualDepth` | `../../../constants.js` |
| `GreaterEqualDepth` | `../../../constants.js` |
| `GreaterDepth` | `../../../constants.js` |
| `NotEqualDepth` | `../../../constants.js` |
| `Vector4` | `../../../math/Vector4.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `equationToGL` | `any` | let/var | `*not shown*` | ✗ |
| `factorToGL` | `any` | let/var | `*not shown*` | ✗ |
| `gl` | `WebGL2RenderingContext` | let/var | `this.gl` | ✗ |
| `gl` | `WebGL2RenderingContext` | let/var | `this.gl` | ✗ |
| `flipSided` | `boolean` | let/var | `( material.side === BackSide )` | ✗ |
| `stencilWrite` | `any` | let/var | `material.stencilWrite` | ✗ |
| `CLIP_DISTANCE0_WEBGL` | `12288` | let/var | `0x3000` | ✗ |
| `gl` | `WebGL2RenderingContext` | let/var | `this.gl` | ✗ |
| `gl` | `WebGL2RenderingContext` | let/var | `this.gl` | ✗ |
| `drawBuffers` | `any[]` | let/var | `[]` | ✗ |
| `needsUpdate` | `boolean` | let/var | `false` | ✗ |
| `textures` | `any` | let/var | `renderContext.textures` | ✗ |
| `boundTexture` | `any` | let/var | `currentBoundTextures[ webglSlot ]` | ✗ |
| `key` | `string` | let/var | ``${target}-${index}`` | ✗ |
| `boundTexture` | `any` | let/var | `currentBoundTextures[ currentTextureSlot ]` | ✗ |


---

## Functions

### `WebGLState._init(): void`

**JSDoc:**
```typescript
/**
	 * Inits the state of the utility.
	 *
	 * @private
	 */
```

**Returns:** `void`

**Calls:**

- `gl.getParameter`
- `new Vector4().fromArray`

**Internal Comments:**
```
// Store only WebGL constants here. (x3)
```

<details><summary>Code</summary>

```typescript
_init() {

		const gl = this.gl;

		// Store only WebGL constants here.

		equationToGL = {
			[ AddEquation ]: gl.FUNC_ADD,
			[ SubtractEquation ]: gl.FUNC_SUBTRACT,
			[ ReverseSubtractEquation ]: gl.FUNC_REVERSE_SUBTRACT
		};

		factorToGL = {
			[ ZeroFactor ]: gl.ZERO,
			[ OneFactor ]: gl.ONE,
			[ SrcColorFactor ]: gl.SRC_COLOR,
			[ SrcAlphaFactor ]: gl.SRC_ALPHA,
			[ SrcAlphaSaturateFactor ]: gl.SRC_ALPHA_SATURATE,
			[ DstColorFactor ]: gl.DST_COLOR,
			[ DstAlphaFactor ]: gl.DST_ALPHA,
			[ OneMinusSrcColorFactor ]: gl.ONE_MINUS_SRC_COLOR,
			[ OneMinusSrcAlphaFactor ]: gl.ONE_MINUS_SRC_ALPHA,
			[ OneMinusDstColorFactor ]: gl.ONE_MINUS_DST_COLOR,
			[ OneMinusDstAlphaFactor ]: gl.ONE_MINUS_DST_ALPHA
		};

		const scissorParam = gl.getParameter( gl.SCISSOR_BOX );
		const viewportParam = gl.getParameter( gl.VIEWPORT );

		this.currentScissor = new Vector4().fromArray( scissorParam );
		this.currentViewport = new Vector4().fromArray( viewportParam );

		this._tempVec4 = new Vector4();

	}
```
</details>

### `WebGLState.enable(id: number): void`

**JSDoc:**
```typescript
/**
	 * Enables the given WebGL capability.
	 *
	 * This method caches the capability state so
	 * `gl.enable()` is only called when necessary.
	 *
	 * @param {GLenum} id - The capability to enable.
	 */
```

**Parameters:**

- **`id`** `number`

**Returns:** `void`

**Calls:**

- `this.gl.enable`

<details><summary>Code</summary>

```typescript
enable( id ) {

		const { enabled } = this;

		if ( enabled[ id ] !== true ) {

			this.gl.enable( id );
			enabled[ id ] = true;

		}

	}
```
</details>

### `WebGLState.disable(id: number): void`

**JSDoc:**
```typescript
/**
	 * Disables the given WebGL capability.
	 *
	 * This method caches the capability state so
	 * `gl.disable()` is only called when necessary.
	 *
	 * @param {GLenum} id - The capability to enable.
	 */
```

**Parameters:**

- **`id`** `number`

**Returns:** `void`

**Calls:**

- `this.gl.disable`

<details><summary>Code</summary>

```typescript
disable( id ) {

		const { enabled } = this;

		if ( enabled[ id ] !== false ) {

			this.gl.disable( id );
			enabled[ id ] = false;

		}

	}
```
</details>

### `WebGLState.setFlipSided(flipSided: boolean): void`

**JSDoc:**
```typescript
/**
	 * Specifies whether polygons are front- or back-facing
	 * by setting the winding orientation.
	 *
	 * This method caches the state so `gl.frontFace()` is only
	 * called when necessary.
	 *
	 * @param {boolean} flipSided - Whether triangles flipped their sides or not.
	 */
```

**Parameters:**

- **`flipSided`** `boolean`

**Returns:** `void`

**Calls:**

- `gl.frontFace`

<details><summary>Code</summary>

```typescript
setFlipSided( flipSided ) {

		if ( this.currentFlipSided !== flipSided ) {

			const { gl } = this;

			if ( flipSided ) {

				gl.frontFace( gl.CW );

			} else {

				gl.frontFace( gl.CCW );

			}

			this.currentFlipSided = flipSided;

		}

	}
```
</details>

### `WebGLState.setCullFace(cullFace: number): void`

**JSDoc:**
```typescript
/**
	 * Specifies whether or not front- and/or back-facing
	 * polygons can be culled.
	 *
	 * This method caches the state so `gl.cullFace()` is only
	 * called when necessary.
	 *
	 * @param {number} cullFace - Defines which polygons are candidates for culling.
	 */
```

**Parameters:**

- **`cullFace`** `number`

**Returns:** `void`

**Calls:**

- `this.enable`
- `gl.cullFace`
- `this.disable`

<details><summary>Code</summary>

```typescript
setCullFace( cullFace ) {

		const { gl } = this;

		if ( cullFace !== CullFaceNone ) {

			this.enable( gl.CULL_FACE );

			if ( cullFace !== this.currentCullFace ) {

				if ( cullFace === CullFaceBack ) {

					gl.cullFace( gl.BACK );

				} else if ( cullFace === CullFaceFront ) {

					gl.cullFace( gl.FRONT );

				} else {

					gl.cullFace( gl.FRONT_AND_BACK );

				}

			}

		} else {

			this.disable( gl.CULL_FACE );

		}

		this.currentCullFace = cullFace;

	}
```
</details>

### `WebGLState.setLineWidth(width: number): void`

**JSDoc:**
```typescript
/**
	 * Specifies the width of line primitives.
	 *
	 * This method caches the state so `gl.lineWidth()` is only
	 * called when necessary.
	 *
	 * @param {number} width - The line width.
	 */
```

**Parameters:**

- **`width`** `number`

**Returns:** `void`

**Calls:**

- `gl.lineWidth`

<details><summary>Code</summary>

```typescript
setLineWidth( width ) {

		const { currentLineWidth, gl } = this;

		if ( width !== currentLineWidth ) {

			gl.lineWidth( width );

			this.currentLineWidth = width;

		}

	}
```
</details>

### `WebGLState.setBlending(blending: number, blendEquation: number, blendSrc: number, blendDst: number, blendEquationAlpha: number, blendSrcAlpha: number, blendDstAlpha: number, premultipliedAlpha: boolean): void`

**JSDoc:**
```typescript
/**
	 * Defines the blending.
	 *
	 * This method caches the state so `gl.blendEquation()`, `gl.blendEquationSeparate()`,
	 * `gl.blendFunc()` and  `gl.blendFuncSeparate()` are only called when necessary.
	 *
	 * @param {number} blending - The blending type.
	 * @param {number} blendEquation - The blending equation.
	 * @param {number} blendSrc - Only relevant for custom blending. The RGB source blending factor.
	 * @param {number} blendDst - Only relevant for custom blending. The RGB destination blending factor.
	 * @param {number} blendEquationAlpha - Only relevant for custom blending. The blending equation for alpha.
	 * @param {number} blendSrcAlpha - Only relevant for custom blending. The alpha source blending factor.
	 * @param {number} blendDstAlpha - Only relevant for custom blending. The alpha destination blending factor.
	 * @param {boolean} premultipliedAlpha - Whether premultiplied alpha is enabled or not.
	 */
```

**Parameters:**

- **`blending`** `number`
- **`blendEquation`** `number`
- **`blendSrc`** `number`
- **`blendDst`** `number`
- **`blendEquationAlpha`** `number`
- **`blendSrcAlpha`** `number`
- **`blendDstAlpha`** `number`
- **`premultipliedAlpha`** `boolean`

**Returns:** `void`

**Calls:**

- `this.disable`
- `this.enable`
- `gl.blendEquation`
- `gl.blendFuncSeparate`
- `gl.blendFunc`
- `console.error`
- `gl.blendEquationSeparate`

**Internal Comments:**
```
// custom blending (x3)
```

<details><summary>Code</summary>

```typescript
setBlending( blending, blendEquation, blendSrc, blendDst, blendEquationAlpha, blendSrcAlpha, blendDstAlpha, premultipliedAlpha ) {

		const { gl } = this;

		if ( blending === NoBlending ) {

			if ( this.currentBlendingEnabled === true ) {

				this.disable( gl.BLEND );
				this.currentBlendingEnabled = false;

			}

			return;

		}

		if ( this.currentBlendingEnabled === false ) {

			this.enable( gl.BLEND );
			this.currentBlendingEnabled = true;

		}

		if ( blending !== CustomBlending ) {

			if ( blending !== this.currentBlending || premultipliedAlpha !== this.currentPremultipledAlpha ) {

				if ( this.currentBlendEquation !== AddEquation || this.currentBlendEquationAlpha !== AddEquation ) {

					gl.blendEquation( gl.FUNC_ADD );

					this.currentBlendEquation = AddEquation;
					this.currentBlendEquationAlpha = AddEquation;

				}

				if ( premultipliedAlpha ) {

					switch ( blending ) {

						case NormalBlending:
							gl.blendFuncSeparate( gl.ONE, gl.ONE_MINUS_SRC_ALPHA, gl.ONE, gl.ONE_MINUS_SRC_ALPHA );
							break;

						case AdditiveBlending:
							gl.blendFunc( gl.ONE, gl.ONE );
							break;

						case SubtractiveBlending:
							gl.blendFuncSeparate( gl.ZERO, gl.ONE_MINUS_SRC_COLOR, gl.ZERO, gl.ONE );
							break;

						case MultiplyBlending:
							gl.blendFuncSeparate( gl.DST_COLOR, gl.ONE_MINUS_SRC_ALPHA, gl.ZERO, gl.ONE );
							break;

						default:
							console.error( 'THREE.WebGLState: Invalid blending: ', blending );
							break;

					}

				} else {

					switch ( blending ) {

						case NormalBlending:
							gl.blendFuncSeparate( gl.SRC_ALPHA, gl.ONE_MINUS_SRC_ALPHA, gl.ONE, gl.ONE_MINUS_SRC_ALPHA );
							break;

						case AdditiveBlending:
							gl.blendFuncSeparate( gl.SRC_ALPHA, gl.ONE, gl.ONE, gl.ONE );
							break;

						case SubtractiveBlending:
							console.error( 'THREE.WebGLState: SubtractiveBlending requires material.premultipliedAlpha = true' );
							break;

						case MultiplyBlending:
							console.error( 'THREE.WebGLState: MultiplyBlending requires material.premultipliedAlpha = true' );
							break;

						default:
							console.error( 'THREE.WebGLState: Invalid blending: ', blending );
							break;

					}

				}

				this.currentBlendSrc = null;
				this.currentBlendDst = null;
				this.currentBlendSrcAlpha = null;
				this.currentBlendDstAlpha = null;

				this.currentBlending = blending;
				this.currentPremultipledAlpha = premultipliedAlpha;

			}

			return;

		}

		// custom blending

		blendEquationAlpha = blendEquationAlpha || blendEquation;
		blendSrcAlpha = blendSrcAlpha || blendSrc;
		blendDstAlpha = blendDstAlpha || blendDst;

		if ( blendEquation !== this.currentBlendEquation || blendEquationAlpha !== this.currentBlendEquationAlpha ) {

			gl.blendEquationSeparate( equationToGL[ blendEquation ], equationToGL[ blendEquationAlpha ] );

			this.currentBlendEquation = blendEquation;
			this.currentBlendEquationAlpha = blendEquationAlpha;

		}

		if ( blendSrc !== this.currentBlendSrc || blendDst !== this.currentBlendDst || blendSrcAlpha !== this.currentBlendSrcAlpha || blendDstAlpha !== this.currentBlendDstAlpha ) {

			gl.blendFuncSeparate( factorToGL[ blendSrc ], factorToGL[ blendDst ], factorToGL[ blendSrcAlpha ], factorToGL[ blendDstAlpha ] );

			this.currentBlendSrc = blendSrc;
			this.currentBlendDst = blendDst;
			this.currentBlendSrcAlpha = blendSrcAlpha;
			this.currentBlendDstAlpha = blendDstAlpha;

		}

		this.currentBlending = blending;
		this.currentPremultipledAlpha = false;

	}
```
</details>

### `WebGLState.setColorMask(colorMask: boolean): void`

**JSDoc:**
```typescript
/**
	 * Specifies whether colors can be written when rendering
	 * into a framebuffer or not.
	 *
	 * This method caches the state so `gl.colorMask()` is only
	 * called when necessary.
	 *
	 * @param {boolean} colorMask - The color mask.
	 */
```

**Parameters:**

- **`colorMask`** `boolean`

**Returns:** `void`

**Calls:**

- `this.gl.colorMask`

<details><summary>Code</summary>

```typescript
setColorMask( colorMask ) {

		if ( this.currentColorMask !== colorMask ) {

			this.gl.colorMask( colorMask, colorMask, colorMask, colorMask );
			this.currentColorMask = colorMask;

		}

	}
```
</details>

### `WebGLState.setDepthTest(depthTest: boolean): void`

**JSDoc:**
```typescript
/**
	 * Specifies whether the depth test is enabled or not.
	 *
	 * @param {boolean} depthTest - Whether the depth test is enabled or not.
	 */
```

**Parameters:**

- **`depthTest`** `boolean`

**Returns:** `void`

**Calls:**

- `this.enable`
- `this.disable`

<details><summary>Code</summary>

```typescript
setDepthTest( depthTest ) {

		const { gl } = this;

		if ( depthTest ) {

			this.enable( gl.DEPTH_TEST );

		} else {

			this.disable( gl.DEPTH_TEST );

		}

	}
```
</details>

### `WebGLState.setDepthMask(depthMask: boolean): void`

**JSDoc:**
```typescript
/**
	 * Specifies whether depth values can be written when rendering
	 * into a framebuffer or not.
	 *
	 * This method caches the state so `gl.depthMask()` is only
	 * called when necessary.
	 *
	 * @param {boolean} depthMask - The depth mask.
	 */
```

**Parameters:**

- **`depthMask`** `boolean`

**Returns:** `void`

**Calls:**

- `this.gl.depthMask`

<details><summary>Code</summary>

```typescript
setDepthMask( depthMask ) {

		if ( this.currentDepthMask !== depthMask ) {

			this.gl.depthMask( depthMask );
			this.currentDepthMask = depthMask;

		}

	}
```
</details>

### `WebGLState.setDepthFunc(depthFunc: number): void`

**JSDoc:**
```typescript
/**
	 * Specifies the depth compare function.
	 *
	 * This method caches the state so `gl.depthFunc()` is only
	 * called when necessary.
	 *
	 * @param {number} depthFunc - The depth compare function.
	 */
```

**Parameters:**

- **`depthFunc`** `number`

**Returns:** `void`

**Calls:**

- `gl.depthFunc`

<details><summary>Code</summary>

```typescript
setDepthFunc( depthFunc ) {

		if ( this.currentDepthFunc !== depthFunc ) {

			const { gl } = this;

			switch ( depthFunc ) {

				case NeverDepth:

					gl.depthFunc( gl.NEVER );
					break;

				case AlwaysDepth:

					gl.depthFunc( gl.ALWAYS );
					break;

				case LessDepth:

					gl.depthFunc( gl.LESS );
					break;

				case LessEqualDepth:

					gl.depthFunc( gl.LEQUAL );
					break;

				case EqualDepth:

					gl.depthFunc( gl.EQUAL );
					break;

				case GreaterEqualDepth:

					gl.depthFunc( gl.GEQUAL );
					break;

				case GreaterDepth:

					gl.depthFunc( gl.GREATER );
					break;

				case NotEqualDepth:

					gl.depthFunc( gl.NOTEQUAL );
					break;

				default:

					gl.depthFunc( gl.LEQUAL );

			}

			this.currentDepthFunc = depthFunc;

		}

	}
```
</details>

### `WebGLState.scissor(x: number, y: number, width: number, height: number): void`

**JSDoc:**
```typescript
/**
	 * Specifies the scissor box.
	 *
	 * @param {number} x - The x-coordinate of the lower left corner of the viewport.
	 * @param {number} y - The y-coordinate of the lower left corner of the viewport.
	 * @param {number} width - The width of the viewport.
	 * @param {number} height - The height of the viewport.
	 *
	 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`
- **`width`** `number`
- **`height`** `number`

**Returns:** `void`

**Calls:**

- `this._tempVec4.set`
- `this.currentScissor.equals`
- `gl.scissor`
- `this.currentScissor.copy`

<details><summary>Code</summary>

```typescript
scissor( x, y, width, height ) {

		const scissor = this._tempVec4.set( x, y, width, height );

		if ( this.currentScissor.equals( scissor ) === false ) {

			const { gl } = this;

			gl.scissor( scissor.x, scissor.y, scissor.z, scissor.w );
			this.currentScissor.copy( scissor );

		}

	}
```
</details>

### `WebGLState.viewport(x: number, y: number, width: number, height: number): void`

**JSDoc:**
```typescript
/**
	 * Specifies the viewport.
	 *
	 * @param {number} x - The x-coordinate of the lower left corner of the viewport.
	 * @param {number} y - The y-coordinate of the lower left corner of the viewport.
	 * @param {number} width - The width of the viewport.
	 * @param {number} height - The height of the viewport.
	 *
	 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`
- **`width`** `number`
- **`height`** `number`

**Returns:** `void`

**Calls:**

- `this._tempVec4.set`
- `this.currentViewport.equals`
- `gl.viewport`
- `this.currentViewport.copy`

<details><summary>Code</summary>

```typescript
viewport( x, y, width, height ) {

		const viewport = this._tempVec4.set( x, y, width, height );

		if ( this.currentViewport.equals( viewport ) === false ) {

			const { gl } = this;

			gl.viewport( viewport.x, viewport.y, viewport.z, viewport.w );
			this.currentViewport.copy( viewport );

		}

	}
```
</details>

### `WebGLState.setScissorTest(boolean: boolean): void`

**JSDoc:**
```typescript
/**
	 * Defines the scissor test.
	 *
	 * @param {boolean} boolean - Whether the scissor test should be enabled or not.
	 */
```

**Parameters:**

- **`boolean`** `boolean`

**Returns:** `void`

**Calls:**

- `gl.enable`
- `gl.disable`

<details><summary>Code</summary>

```typescript
setScissorTest( boolean ) {

		const gl = this.gl;

		if ( boolean ) {

			gl.enable( gl.SCISSOR_TEST );

		} else {

			gl.disable( gl.SCISSOR_TEST );

		}

	}
```
</details>

### `WebGLState.setStencilTest(stencilTest: boolean): void`

**JSDoc:**
```typescript
/**
	 * Specifies whether the stencil test is enabled or not.
	 *
	 * @param {boolean} stencilTest - Whether the stencil test is enabled or not.
	 */
```

**Parameters:**

- **`stencilTest`** `boolean`

**Returns:** `void`

**Calls:**

- `this.enable`
- `this.disable`

<details><summary>Code</summary>

```typescript
setStencilTest( stencilTest ) {

		const { gl } = this;

		if ( stencilTest ) {

			this.enable( gl.STENCIL_TEST );

		} else {

			this.disable( gl.STENCIL_TEST );

		}

	}
```
</details>

### `WebGLState.setStencilMask(stencilMask: boolean): void`

**JSDoc:**
```typescript
/**
	 * Specifies whether stencil values can be written when rendering
	 * into a framebuffer or not.
	 *
	 * This method caches the state so `gl.stencilMask()` is only
	 * called when necessary.
	 *
	 * @param {boolean} stencilMask - The stencil mask.
	 */
```

**Parameters:**

- **`stencilMask`** `boolean`

**Returns:** `void`

**Calls:**

- `this.gl.stencilMask`

<details><summary>Code</summary>

```typescript
setStencilMask( stencilMask ) {

		if ( this.currentStencilMask !== stencilMask ) {

			this.gl.stencilMask( stencilMask );
			this.currentStencilMask = stencilMask;

		}

	}
```
</details>

### `WebGLState.setStencilFunc(stencilFunc: number, stencilRef: number, stencilMask: number): void`

**JSDoc:**
```typescript
/**
	 * Specifies whether the stencil test functions.
	 *
	 * This method caches the state so `gl.stencilFunc()` is only
	 * called when necessary.
	 *
	 * @param {number} stencilFunc - The stencil compare function.
	 * @param {number} stencilRef - The reference value for the stencil test.
	 * @param {number} stencilMask - A bit-wise mask that is used to AND the reference value and the stored stencil value when the test is done.
	 */
```

**Parameters:**

- **`stencilFunc`** `number`
- **`stencilRef`** `number`
- **`stencilMask`** `number`

**Returns:** `void`

**Calls:**

- `this.gl.stencilFunc`

<details><summary>Code</summary>

```typescript
setStencilFunc( stencilFunc, stencilRef, stencilMask ) {

		if ( this.currentStencilFunc !== stencilFunc ||
			 this.currentStencilRef !== stencilRef ||
			 this.currentStencilFuncMask !== stencilMask ) {

			this.gl.stencilFunc( stencilFunc, stencilRef, stencilMask );

			this.currentStencilFunc = stencilFunc;
			this.currentStencilRef = stencilRef;
			this.currentStencilFuncMask = stencilMask;

		}

	}
```
</details>

### `WebGLState.setStencilOp(stencilFail: number, stencilZFail: number, stencilZPass: number): void`

**JSDoc:**
```typescript
/**
	 * Specifies whether the stencil test operation.
	 *
	 * This method caches the state so `gl.stencilOp()` is only
	 * called when necessary.
	 *
	 * @param {number} stencilFail - The function to use when the stencil test fails.
	 * @param {number} stencilZFail - The function to use when the stencil test passes, but the depth test fail.
	 * @param {number} stencilZPass - The function to use when both the stencil test and the depth test pass,
	 * or when the stencil test passes and there is no depth buffer or depth testing is disabled.
	 */
```

**Parameters:**

- **`stencilFail`** `number`
- **`stencilZFail`** `number`
- **`stencilZPass`** `number`

**Returns:** `void`

**Calls:**

- `this.gl.stencilOp`

<details><summary>Code</summary>

```typescript
setStencilOp( stencilFail, stencilZFail, stencilZPass ) {

		if ( this.currentStencilFail !== stencilFail ||
			 this.currentStencilZFail !== stencilZFail ||
			 this.currentStencilZPass !== stencilZPass ) {

			this.gl.stencilOp( stencilFail, stencilZFail, stencilZPass );

			this.currentStencilFail = stencilFail;
			this.currentStencilZFail = stencilZFail;
			this.currentStencilZPass = stencilZPass;

		}

	}
```
</details>

### `WebGLState.setMaterial(material: Material, frontFaceCW: number, hardwareClippingPlanes: number): void`

**JSDoc:**
```typescript
/**
	 * Configures the WebGL state for the given material.
	 *
	 * @param {Material} material - The material to configure the state for.
	 * @param {number} frontFaceCW - Whether the front faces are counter-clockwise or not.
	 * @param {number} hardwareClippingPlanes - The number of hardware clipping planes.
	 */
```

**Parameters:**

- **`material`** `Material`
- **`frontFaceCW`** `number`
- **`hardwareClippingPlanes`** `number`

**Returns:** `void`

**Calls:**

- `this.disable`
- `this.enable`
- `this.setFlipSided`
- `this.setBlending`
- `this.setDepthFunc`
- `this.setDepthTest`
- `this.setDepthMask`
- `this.setColorMask`
- `this.setStencilTest`
- `this.setStencilMask`
- `this.setStencilFunc`
- `this.setStencilOp`
- `this.setPolygonOffset`

<details><summary>Code</summary>

```typescript
setMaterial( material, frontFaceCW, hardwareClippingPlanes ) {

		const { gl } = this;

		material.side === DoubleSide
			? this.disable( gl.CULL_FACE )
			: this.enable( gl.CULL_FACE );

		let flipSided = ( material.side === BackSide );
		if ( frontFaceCW ) flipSided = ! flipSided;

		this.setFlipSided( flipSided );

		( material.blending === NormalBlending && material.transparent === false )
			? this.setBlending( NoBlending )
			: this.setBlending( material.blending, material.blendEquation, material.blendSrc, material.blendDst, material.blendEquationAlpha, material.blendSrcAlpha, material.blendDstAlpha, material.premultipliedAlpha );

		this.setDepthFunc( material.depthFunc );
		this.setDepthTest( material.depthTest );
		this.setDepthMask( material.depthWrite );
		this.setColorMask( material.colorWrite );

		const stencilWrite = material.stencilWrite;
		this.setStencilTest( stencilWrite );
		if ( stencilWrite ) {

			this.setStencilMask( material.stencilWriteMask );
			this.setStencilFunc( material.stencilFunc, material.stencilRef, material.stencilFuncMask );
			this.setStencilOp( material.stencilFail, material.stencilZFail, material.stencilZPass );

		}

		this.setPolygonOffset( material.polygonOffset, material.polygonOffsetFactor, material.polygonOffsetUnits );

		material.alphaToCoverage === true && this.backend.renderer.samples > 1
			? this.enable( gl.SAMPLE_ALPHA_TO_COVERAGE )
			: this.disable( gl.SAMPLE_ALPHA_TO_COVERAGE );

		if ( hardwareClippingPlanes > 0 ) {

			if ( this.currentClippingPlanes !== hardwareClippingPlanes ) {

				const CLIP_DISTANCE0_WEBGL = 0x3000;

				for ( let i = 0; i < 8; i ++ ) {

					if ( i < hardwareClippingPlanes ) {

						this.enable( CLIP_DISTANCE0_WEBGL + i );

					} else {

						this.disable( CLIP_DISTANCE0_WEBGL + i );

					}

				}

			}

		}

	}
```
</details>

### `WebGLState.setPolygonOffset(polygonOffset: boolean, factor: number, units: number): void`

**JSDoc:**
```typescript
/**
	 * Specifies the polygon offset.
	 *
	 * This method caches the state so `gl.polygonOffset()` is only
	 * called when necessary.
	 *
	 * @param {boolean} polygonOffset - Whether polygon offset is enabled or not.
	 * @param {number} factor - The scale factor for the variable depth offset for each polygon.
	 * @param {number} units - The multiplier by which an implementation-specific value is multiplied with to create a constant depth offset.
	 */
```

**Parameters:**

- **`polygonOffset`** `boolean`
- **`factor`** `number`
- **`units`** `number`

**Returns:** `void`

**Calls:**

- `this.enable`
- `gl.polygonOffset`
- `this.disable`

<details><summary>Code</summary>

```typescript
setPolygonOffset( polygonOffset, factor, units ) {

		const { gl } = this;

		if ( polygonOffset ) {

			this.enable( gl.POLYGON_OFFSET_FILL );

			if ( this.currentPolygonOffsetFactor !== factor || this.currentPolygonOffsetUnits !== units ) {

				gl.polygonOffset( factor, units );

				this.currentPolygonOffsetFactor = factor;
				this.currentPolygonOffsetUnits = units;

			}

		} else {

			this.disable( gl.POLYGON_OFFSET_FILL );

		}

	}
```
</details>

### `WebGLState.useProgram(program: WebGLProgram): boolean`

**JSDoc:**
```typescript
/**
	 * Defines the usage of the given WebGL program.
	 *
	 * This method caches the state so `gl.useProgram()` is only
	 * called when necessary.
	 *
	 * @param {WebGLProgram} program - The WebGL program to use.
	 * @return {boolean} Whether a program change has been executed or not.
	 */
```

**Parameters:**

- **`program`** `WebGLProgram`

**Returns:** `boolean`

**Calls:**

- `this.gl.useProgram`

<details><summary>Code</summary>

```typescript
useProgram( program ) {

		if ( this.currentProgram !== program ) {

			this.gl.useProgram( program );

			this.currentProgram = program;

			return true;

		}

		return false;

	}
```
</details>

### `WebGLState.setVertexState(vao: WebGLVertexArrayObject, indexBuffer: WebGLBuffer): boolean`

**JSDoc:**
```typescript
/**
	 * Sets the vertex state by binding the given VAO and element buffer.
	 *
	 * @param {WebGLVertexArrayObject} vao - The VAO.
	 * @param {WebGLBuffer} indexBuffer - The index buffer.
	 * @return {boolean} Whether a vertex state has been changed or not.
	 */
```

**Parameters:**

- **`vao`** `WebGLVertexArrayObject`
- **`indexBuffer`** `WebGLBuffer`

**Returns:** `boolean`

**Calls:**

- `gl.bindVertexArray`
- `gl.bindBuffer`

<details><summary>Code</summary>

```typescript
setVertexState( vao, indexBuffer = null ) {

		const gl = this.gl;

		if ( this.currentVAO !== vao || this.currentIndex !== indexBuffer ) {

			gl.bindVertexArray( vao );

			if ( indexBuffer !== null ) {

				gl.bindBuffer( gl.ELEMENT_ARRAY_BUFFER, indexBuffer );

			}

			this.currentVAO = vao;
			this.currentIndex = indexBuffer;

			return true;

		}

		return false;

	}
```
</details>

### `WebGLState.resetVertexState(): void`

**JSDoc:**
```typescript
/**
	 * Resets the vertex array state by resetting the VAO and element buffer.
	 */
```

**Returns:** `void`

**Calls:**

- `gl.bindVertexArray`
- `gl.bindBuffer`

<details><summary>Code</summary>

```typescript
resetVertexState() {

		const gl = this.gl;

		gl.bindVertexArray( null );
		gl.bindBuffer( gl.ELEMENT_ARRAY_BUFFER, null );

		this.currentVAO = null;
		this.currentIndex = null;

	}
```
</details>

### `WebGLState.bindFramebuffer(target: number, framebuffer: WebGLFramebuffer): boolean`

**JSDoc:**
```typescript
/**
	 * Binds the given framebuffer.
	 *
	 * This method caches the state so `gl.bindFramebuffer()` is only
	 * called when necessary.
	 *
	 * @param {number} target - The binding point (target).
	 * @param {WebGLFramebuffer} framebuffer - The WebGL framebuffer to bind.
	 * @return {boolean} Whether a bind has been executed or not.
	 */
```

**Parameters:**

- **`target`** `number`
- **`framebuffer`** `WebGLFramebuffer`

**Returns:** `boolean`

**Calls:**

- `gl.bindFramebuffer`

**Internal Comments:**
```
// gl.DRAW_FRAMEBUFFER is equivalent to gl.FRAMEBUFFER
```

<details><summary>Code</summary>

```typescript
bindFramebuffer( target, framebuffer ) {

		const { gl, currentBoundFramebuffers } = this;

		if ( currentBoundFramebuffers[ target ] !== framebuffer ) {

			gl.bindFramebuffer( target, framebuffer );

			currentBoundFramebuffers[ target ] = framebuffer;

			// gl.DRAW_FRAMEBUFFER is equivalent to gl.FRAMEBUFFER

			if ( target === gl.DRAW_FRAMEBUFFER ) {

				currentBoundFramebuffers[ gl.FRAMEBUFFER ] = framebuffer;

			}

			if ( target === gl.FRAMEBUFFER ) {

				currentBoundFramebuffers[ gl.DRAW_FRAMEBUFFER ] = framebuffer;

			}

			return true;

		}

		return false;

	}
```
</details>

### `WebGLState.drawBuffers(renderContext: RenderContext, framebuffer: WebGLFramebuffer): void`

**JSDoc:**
```typescript
/**
	 * Defines draw buffers to which fragment colors are written into.
	 * Configures the MRT setup of custom framebuffers.
	 *
	 * This method caches the state so `gl.drawBuffers()` is only
	 * called when necessary.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @param {WebGLFramebuffer} framebuffer - The WebGL framebuffer.
	 */
```

**Parameters:**

- **`renderContext`** `RenderContext`
- **`framebuffer`** `WebGLFramebuffer`

**Returns:** `void`

**Calls:**

- `this.currentDrawbuffers.get`
- `this.currentDrawbuffers.set`
- `gl.drawBuffers`

<details><summary>Code</summary>

```typescript
drawBuffers( renderContext, framebuffer ) {

		const { gl } = this;

		let drawBuffers = [];

		let needsUpdate = false;

		if ( renderContext.textures !== null ) {

			drawBuffers = this.currentDrawbuffers.get( framebuffer );

			if ( drawBuffers === undefined ) {

				drawBuffers = [];
				this.currentDrawbuffers.set( framebuffer, drawBuffers );

			}


			const textures = renderContext.textures;

			if ( drawBuffers.length !== textures.length || drawBuffers[ 0 ] !== gl.COLOR_ATTACHMENT0 ) {

				for ( let i = 0, il = textures.length; i < il; i ++ ) {

					drawBuffers[ i ] = gl.COLOR_ATTACHMENT0 + i;

				}

				drawBuffers.length = textures.length;

				needsUpdate = true;

			}


		} else {

			if ( drawBuffers[ 0 ] !== gl.BACK ) {

				drawBuffers[ 0 ] = gl.BACK;

				needsUpdate = true;

			}

		}

		if ( needsUpdate ) {

			gl.drawBuffers( drawBuffers );

		}

	}
```
</details>

### `WebGLState.activeTexture(webglSlot: number): void`

**JSDoc:**
```typescript
/**
	 * Makes the given texture unit active.
	 *
	 * This method caches the state so `gl.activeTexture()` is only
	 * called when necessary.
	 *
	 * @param {number} webglSlot - The texture unit to make active.
	 */
```

**Parameters:**

- **`webglSlot`** `number`

**Returns:** `void`

**Calls:**

- `gl.activeTexture`

<details><summary>Code</summary>

```typescript
activeTexture( webglSlot ) {

		const { gl, currentTextureSlot, maxTextures } = this;

		if ( webglSlot === undefined ) webglSlot = gl.TEXTURE0 + maxTextures - 1;

		if ( currentTextureSlot !== webglSlot ) {

			gl.activeTexture( webglSlot );
			this.currentTextureSlot = webglSlot;

		}

	}
```
</details>

### `WebGLState.bindTexture(webglType: number, webglTexture: WebGLTexture, webglSlot: number): void`

**JSDoc:**
```typescript
/**
	 * Binds the given WebGL texture to a target.
	 *
	 * This method caches the state so `gl.bindTexture()` is only
	 * called when necessary.
	 *
	 * @param {number} webglType - The binding point (target).
	 * @param {WebGLTexture} webglTexture - The WebGL texture to bind.
	 * @param {number} webglSlot - The texture.
	 */
```

**Parameters:**

- **`webglType`** `number`
- **`webglTexture`** `WebGLTexture`
- **`webglSlot`** `number`

**Returns:** `void`

**Calls:**

- `gl.activeTexture`
- `gl.bindTexture`

<details><summary>Code</summary>

```typescript
bindTexture( webglType, webglTexture, webglSlot ) {

		const { gl, currentTextureSlot, currentBoundTextures, maxTextures } = this;

		if ( webglSlot === undefined ) {

			if ( currentTextureSlot === null ) {

				webglSlot = gl.TEXTURE0 + maxTextures - 1;

			} else {

				webglSlot = currentTextureSlot;

			}

		}

		let boundTexture = currentBoundTextures[ webglSlot ];

		if ( boundTexture === undefined ) {

			boundTexture = { type: undefined, texture: undefined };
			currentBoundTextures[ webglSlot ] = boundTexture;

		}

		if ( boundTexture.type !== webglType || boundTexture.texture !== webglTexture ) {

			if ( currentTextureSlot !== webglSlot ) {

				gl.activeTexture( webglSlot );
				this.currentTextureSlot = webglSlot;

			}

			gl.bindTexture( webglType, webglTexture );

			boundTexture.type = webglType;
			boundTexture.texture = webglTexture;

		}

	}
```
</details>

### `WebGLState.bindBufferBase(target: number, index: number, buffer: WebGLBuffer): boolean`

**JSDoc:**
```typescript
/**
	 * Binds a given WebGL buffer to a given binding point (target) at a given index.
	 *
	 * This method caches the state so `gl.bindBufferBase()` is only
	 * called when necessary.
	 *
	 * @param {number} target - The target for the bind operation.
	 * @param {number} index - The index of the target.
	 * @param {WebGLBuffer} buffer - The WebGL buffer.
	 * @return {boolean} Whether a bind has been executed or not.
	 */
```

**Parameters:**

- **`target`** `number`
- **`index`** `number`
- **`buffer`** `WebGLBuffer`

**Returns:** `boolean`

**Calls:**

- `gl.bindBufferBase`

<details><summary>Code</summary>

```typescript
bindBufferBase( target, index, buffer ) {

		const { gl } = this;

		const key = `${target}-${index}`;

		if ( this.currentBoundBufferBases[ key ] !== buffer ) {

			gl.bindBufferBase( target, index, buffer );
			this.currentBoundBufferBases[ key ] = buffer;

			return true;

		}

		return false;

	}
```
</details>

### `WebGLState.unbindTexture(): void`

**JSDoc:**
```typescript
/**
	 * Unbinds the current bound texture.
	 *
	 * This method caches the state so `gl.bindTexture()` is only
	 * called when necessary.
	 */
```

**Returns:** `void`

**Calls:**

- `gl.bindTexture`

<details><summary>Code</summary>

```typescript
unbindTexture() {

		const { gl, currentTextureSlot, currentBoundTextures } = this;

		const boundTexture = currentBoundTextures[ currentTextureSlot ];

		if ( boundTexture !== undefined && boundTexture.type !== undefined ) {

			gl.bindTexture( boundTexture.type, null );

			boundTexture.type = undefined;
			boundTexture.texture = undefined;

		}

	}
```
</details>


---

## Classes

### `WebGLState`

<details><summary>Class Code</summary>

```ts
class WebGLState {

	/**
	 * Constructs a new utility object.
	 *
	 * @param {WebGLBackend} backend - The WebGL 2 backend.
	 */
	constructor( backend ) {

		/**
		 * A reference to the WebGL 2 backend.
		 *
		 * @type {WebGLBackend}
		 */
		this.backend = backend;

		/**
		 * A reference to the rendering context.
		 *
		 * @type {WebGL2RenderingContext}
		 */
		this.gl = this.backend.gl;

		// Below properties are intended to cache
		// the WebGL state and are not explicitly
		// documented for convenience reasons.

		this.enabled = {};
		this.currentFlipSided = null;
		this.currentCullFace = null;
		this.currentProgram = null;
		this.currentBlendingEnabled = false;
		this.currentBlending = null;
		this.currentBlendSrc = null;
		this.currentBlendDst = null;
		this.currentBlendSrcAlpha = null;
		this.currentBlendDstAlpha = null;
		this.currentPremultipledAlpha = null;
		this.currentPolygonOffsetFactor = null;
		this.currentPolygonOffsetUnits = null;
		this.currentColorMask = null;
		this.currentDepthFunc = null;
		this.currentDepthMask = null;
		this.currentStencilFunc = null;
		this.currentStencilRef = null;
		this.currentStencilFuncMask = null;
		this.currentStencilFail = null;
		this.currentStencilZFail = null;
		this.currentStencilZPass = null;
		this.currentStencilMask = null;
		this.currentLineWidth = null;
		this.currentClippingPlanes = 0;

		this.currentVAO = null;
		this.currentIndex = null;

		this.currentBoundFramebuffers = {};
		this.currentDrawbuffers = new WeakMap();

		this.maxTextures = this.gl.getParameter( this.gl.MAX_TEXTURE_IMAGE_UNITS );
		this.currentTextureSlot = null;
		this.currentBoundTextures = {};
		this.currentBoundBufferBases = {};


		this._init();

	}

	/**
	 * Inits the state of the utility.
	 *
	 * @private
	 */
	_init() {

		const gl = this.gl;

		// Store only WebGL constants here.

		equationToGL = {
			[ AddEquation ]: gl.FUNC_ADD,
			[ SubtractEquation ]: gl.FUNC_SUBTRACT,
			[ ReverseSubtractEquation ]: gl.FUNC_REVERSE_SUBTRACT
		};

		factorToGL = {
			[ ZeroFactor ]: gl.ZERO,
			[ OneFactor ]: gl.ONE,
			[ SrcColorFactor ]: gl.SRC_COLOR,
			[ SrcAlphaFactor ]: gl.SRC_ALPHA,
			[ SrcAlphaSaturateFactor ]: gl.SRC_ALPHA_SATURATE,
			[ DstColorFactor ]: gl.DST_COLOR,
			[ DstAlphaFactor ]: gl.DST_ALPHA,
			[ OneMinusSrcColorFactor ]: gl.ONE_MINUS_SRC_COLOR,
			[ OneMinusSrcAlphaFactor ]: gl.ONE_MINUS_SRC_ALPHA,
			[ OneMinusDstColorFactor ]: gl.ONE_MINUS_DST_COLOR,
			[ OneMinusDstAlphaFactor ]: gl.ONE_MINUS_DST_ALPHA
		};

		const scissorParam = gl.getParameter( gl.SCISSOR_BOX );
		const viewportParam = gl.getParameter( gl.VIEWPORT );

		this.currentScissor = new Vector4().fromArray( scissorParam );
		this.currentViewport = new Vector4().fromArray( viewportParam );

		this._tempVec4 = new Vector4();

	}

	/**
	 * Enables the given WebGL capability.
	 *
	 * This method caches the capability state so
	 * `gl.enable()` is only called when necessary.
	 *
	 * @param {GLenum} id - The capability to enable.
	 */
	enable( id ) {

		const { enabled } = this;

		if ( enabled[ id ] !== true ) {

			this.gl.enable( id );
			enabled[ id ] = true;

		}

	}

	/**
	 * Disables the given WebGL capability.
	 *
	 * This method caches the capability state so
	 * `gl.disable()` is only called when necessary.
	 *
	 * @param {GLenum} id - The capability to enable.
	 */
	disable( id ) {

		const { enabled } = this;

		if ( enabled[ id ] !== false ) {

			this.gl.disable( id );
			enabled[ id ] = false;

		}

	}

	/**
	 * Specifies whether polygons are front- or back-facing
	 * by setting the winding orientation.
	 *
	 * This method caches the state so `gl.frontFace()` is only
	 * called when necessary.
	 *
	 * @param {boolean} flipSided - Whether triangles flipped their sides or not.
	 */
	setFlipSided( flipSided ) {

		if ( this.currentFlipSided !== flipSided ) {

			const { gl } = this;

			if ( flipSided ) {

				gl.frontFace( gl.CW );

			} else {

				gl.frontFace( gl.CCW );

			}

			this.currentFlipSided = flipSided;

		}

	}

	/**
	 * Specifies whether or not front- and/or back-facing
	 * polygons can be culled.
	 *
	 * This method caches the state so `gl.cullFace()` is only
	 * called when necessary.
	 *
	 * @param {number} cullFace - Defines which polygons are candidates for culling.
	 */
	setCullFace( cullFace ) {

		const { gl } = this;

		if ( cullFace !== CullFaceNone ) {

			this.enable( gl.CULL_FACE );

			if ( cullFace !== this.currentCullFace ) {

				if ( cullFace === CullFaceBack ) {

					gl.cullFace( gl.BACK );

				} else if ( cullFace === CullFaceFront ) {

					gl.cullFace( gl.FRONT );

				} else {

					gl.cullFace( gl.FRONT_AND_BACK );

				}

			}

		} else {

			this.disable( gl.CULL_FACE );

		}

		this.currentCullFace = cullFace;

	}

	/**
	 * Specifies the width of line primitives.
	 *
	 * This method caches the state so `gl.lineWidth()` is only
	 * called when necessary.
	 *
	 * @param {number} width - The line width.
	 */
	setLineWidth( width ) {

		const { currentLineWidth, gl } = this;

		if ( width !== currentLineWidth ) {

			gl.lineWidth( width );

			this.currentLineWidth = width;

		}

	}

	/**
	 * Defines the blending.
	 *
	 * This method caches the state so `gl.blendEquation()`, `gl.blendEquationSeparate()`,
	 * `gl.blendFunc()` and  `gl.blendFuncSeparate()` are only called when necessary.
	 *
	 * @param {number} blending - The blending type.
	 * @param {number} blendEquation - The blending equation.
	 * @param {number} blendSrc - Only relevant for custom blending. The RGB source blending factor.
	 * @param {number} blendDst - Only relevant for custom blending. The RGB destination blending factor.
	 * @param {number} blendEquationAlpha - Only relevant for custom blending. The blending equation for alpha.
	 * @param {number} blendSrcAlpha - Only relevant for custom blending. The alpha source blending factor.
	 * @param {number} blendDstAlpha - Only relevant for custom blending. The alpha destination blending factor.
	 * @param {boolean} premultipliedAlpha - Whether premultiplied alpha is enabled or not.
	 */
	setBlending( blending, blendEquation, blendSrc, blendDst, blendEquationAlpha, blendSrcAlpha, blendDstAlpha, premultipliedAlpha ) {

		const { gl } = this;

		if ( blending === NoBlending ) {

			if ( this.currentBlendingEnabled === true ) {

				this.disable( gl.BLEND );
				this.currentBlendingEnabled = false;

			}

			return;

		}

		if ( this.currentBlendingEnabled === false ) {

			this.enable( gl.BLEND );
			this.currentBlendingEnabled = true;

		}

		if ( blending !== CustomBlending ) {

			if ( blending !== this.currentBlending || premultipliedAlpha !== this.currentPremultipledAlpha ) {

				if ( this.currentBlendEquation !== AddEquation || this.currentBlendEquationAlpha !== AddEquation ) {

					gl.blendEquation( gl.FUNC_ADD );

					this.currentBlendEquation = AddEquation;
					this.currentBlendEquationAlpha = AddEquation;

				}

				if ( premultipliedAlpha ) {

					switch ( blending ) {

						case NormalBlending:
							gl.blendFuncSeparate( gl.ONE, gl.ONE_MINUS_SRC_ALPHA, gl.ONE, gl.ONE_MINUS_SRC_ALPHA );
							break;

						case AdditiveBlending:
							gl.blendFunc( gl.ONE, gl.ONE );
							break;

						case SubtractiveBlending:
							gl.blendFuncSeparate( gl.ZERO, gl.ONE_MINUS_SRC_COLOR, gl.ZERO, gl.ONE );
							break;

						case MultiplyBlending:
							gl.blendFuncSeparate( gl.DST_COLOR, gl.ONE_MINUS_SRC_ALPHA, gl.ZERO, gl.ONE );
							break;

						default:
							console.error( 'THREE.WebGLState: Invalid blending: ', blending );
							break;

					}

				} else {

					switch ( blending ) {

						case NormalBlending:
							gl.blendFuncSeparate( gl.SRC_ALPHA, gl.ONE_MINUS_SRC_ALPHA, gl.ONE, gl.ONE_MINUS_SRC_ALPHA );
							break;

						case AdditiveBlending:
							gl.blendFuncSeparate( gl.SRC_ALPHA, gl.ONE, gl.ONE, gl.ONE );
							break;

						case SubtractiveBlending:
							console.error( 'THREE.WebGLState: SubtractiveBlending requires material.premultipliedAlpha = true' );
							break;

						case MultiplyBlending:
							console.error( 'THREE.WebGLState: MultiplyBlending requires material.premultipliedAlpha = true' );
							break;

						default:
							console.error( 'THREE.WebGLState: Invalid blending: ', blending );
							break;

					}

				}

				this.currentBlendSrc = null;
				this.currentBlendDst = null;
				this.currentBlendSrcAlpha = null;
				this.currentBlendDstAlpha = null;

				this.currentBlending = blending;
				this.currentPremultipledAlpha = premultipliedAlpha;

			}

			return;

		}

		// custom blending

		blendEquationAlpha = blendEquationAlpha || blendEquation;
		blendSrcAlpha = blendSrcAlpha || blendSrc;
		blendDstAlpha = blendDstAlpha || blendDst;

		if ( blendEquation !== this.currentBlendEquation || blendEquationAlpha !== this.currentBlendEquationAlpha ) {

			gl.blendEquationSeparate( equationToGL[ blendEquation ], equationToGL[ blendEquationAlpha ] );

			this.currentBlendEquation = blendEquation;
			this.currentBlendEquationAlpha = blendEquationAlpha;

		}

		if ( blendSrc !== this.currentBlendSrc || blendDst !== this.currentBlendDst || blendSrcAlpha !== this.currentBlendSrcAlpha || blendDstAlpha !== this.currentBlendDstAlpha ) {

			gl.blendFuncSeparate( factorToGL[ blendSrc ], factorToGL[ blendDst ], factorToGL[ blendSrcAlpha ], factorToGL[ blendDstAlpha ] );

			this.currentBlendSrc = blendSrc;
			this.currentBlendDst = blendDst;
			this.currentBlendSrcAlpha = blendSrcAlpha;
			this.currentBlendDstAlpha = blendDstAlpha;

		}

		this.currentBlending = blending;
		this.currentPremultipledAlpha = false;

	}

	/**
	 * Specifies whether colors can be written when rendering
	 * into a framebuffer or not.
	 *
	 * This method caches the state so `gl.colorMask()` is only
	 * called when necessary.
	 *
	 * @param {boolean} colorMask - The color mask.
	 */
	setColorMask( colorMask ) {

		if ( this.currentColorMask !== colorMask ) {

			this.gl.colorMask( colorMask, colorMask, colorMask, colorMask );
			this.currentColorMask = colorMask;

		}

	}

	/**
	 * Specifies whether the depth test is enabled or not.
	 *
	 * @param {boolean} depthTest - Whether the depth test is enabled or not.
	 */
	setDepthTest( depthTest ) {

		const { gl } = this;

		if ( depthTest ) {

			this.enable( gl.DEPTH_TEST );

		} else {

			this.disable( gl.DEPTH_TEST );

		}

	}

	/**
	 * Specifies whether depth values can be written when rendering
	 * into a framebuffer or not.
	 *
	 * This method caches the state so `gl.depthMask()` is only
	 * called when necessary.
	 *
	 * @param {boolean} depthMask - The depth mask.
	 */
	setDepthMask( depthMask ) {

		if ( this.currentDepthMask !== depthMask ) {

			this.gl.depthMask( depthMask );
			this.currentDepthMask = depthMask;

		}

	}

	/**
	 * Specifies the depth compare function.
	 *
	 * This method caches the state so `gl.depthFunc()` is only
	 * called when necessary.
	 *
	 * @param {number} depthFunc - The depth compare function.
	 */
	setDepthFunc( depthFunc ) {

		if ( this.currentDepthFunc !== depthFunc ) {

			const { gl } = this;

			switch ( depthFunc ) {

				case NeverDepth:

					gl.depthFunc( gl.NEVER );
					break;

				case AlwaysDepth:

					gl.depthFunc( gl.ALWAYS );
					break;

				case LessDepth:

					gl.depthFunc( gl.LESS );
					break;

				case LessEqualDepth:

					gl.depthFunc( gl.LEQUAL );
					break;

				case EqualDepth:

					gl.depthFunc( gl.EQUAL );
					break;

				case GreaterEqualDepth:

					gl.depthFunc( gl.GEQUAL );
					break;

				case GreaterDepth:

					gl.depthFunc( gl.GREATER );
					break;

				case NotEqualDepth:

					gl.depthFunc( gl.NOTEQUAL );
					break;

				default:

					gl.depthFunc( gl.LEQUAL );

			}

			this.currentDepthFunc = depthFunc;

		}

	}

	/**
	 * Specifies the scissor box.
	 *
	 * @param {number} x - The x-coordinate of the lower left corner of the viewport.
	 * @param {number} y - The y-coordinate of the lower left corner of the viewport.
	 * @param {number} width - The width of the viewport.
	 * @param {number} height - The height of the viewport.
	 *
	 */
	scissor( x, y, width, height ) {

		const scissor = this._tempVec4.set( x, y, width, height );

		if ( this.currentScissor.equals( scissor ) === false ) {

			const { gl } = this;

			gl.scissor( scissor.x, scissor.y, scissor.z, scissor.w );
			this.currentScissor.copy( scissor );

		}

	}

	/**
	 * Specifies the viewport.
	 *
	 * @param {number} x - The x-coordinate of the lower left corner of the viewport.
	 * @param {number} y - The y-coordinate of the lower left corner of the viewport.
	 * @param {number} width - The width of the viewport.
	 * @param {number} height - The height of the viewport.
	 *
	 */
	viewport( x, y, width, height ) {

		const viewport = this._tempVec4.set( x, y, width, height );

		if ( this.currentViewport.equals( viewport ) === false ) {

			const { gl } = this;

			gl.viewport( viewport.x, viewport.y, viewport.z, viewport.w );
			this.currentViewport.copy( viewport );

		}

	}

	/**
	 * Defines the scissor test.
	 *
	 * @param {boolean} boolean - Whether the scissor test should be enabled or not.
	 */
	setScissorTest( boolean ) {

		const gl = this.gl;

		if ( boolean ) {

			gl.enable( gl.SCISSOR_TEST );

		} else {

			gl.disable( gl.SCISSOR_TEST );

		}

	}

	/**
	 * Specifies whether the stencil test is enabled or not.
	 *
	 * @param {boolean} stencilTest - Whether the stencil test is enabled or not.
	 */
	setStencilTest( stencilTest ) {

		const { gl } = this;

		if ( stencilTest ) {

			this.enable( gl.STENCIL_TEST );

		} else {

			this.disable( gl.STENCIL_TEST );

		}

	}

	/**
	 * Specifies whether stencil values can be written when rendering
	 * into a framebuffer or not.
	 *
	 * This method caches the state so `gl.stencilMask()` is only
	 * called when necessary.
	 *
	 * @param {boolean} stencilMask - The stencil mask.
	 */
	setStencilMask( stencilMask ) {

		if ( this.currentStencilMask !== stencilMask ) {

			this.gl.stencilMask( stencilMask );
			this.currentStencilMask = stencilMask;

		}

	}

	/**
	 * Specifies whether the stencil test functions.
	 *
	 * This method caches the state so `gl.stencilFunc()` is only
	 * called when necessary.
	 *
	 * @param {number} stencilFunc - The stencil compare function.
	 * @param {number} stencilRef - The reference value for the stencil test.
	 * @param {number} stencilMask - A bit-wise mask that is used to AND the reference value and the stored stencil value when the test is done.
	 */
	setStencilFunc( stencilFunc, stencilRef, stencilMask ) {

		if ( this.currentStencilFunc !== stencilFunc ||
			 this.currentStencilRef !== stencilRef ||
			 this.currentStencilFuncMask !== stencilMask ) {

			this.gl.stencilFunc( stencilFunc, stencilRef, stencilMask );

			this.currentStencilFunc = stencilFunc;
			this.currentStencilRef = stencilRef;
			this.currentStencilFuncMask = stencilMask;

		}

	}

	/**
	 * Specifies whether the stencil test operation.
	 *
	 * This method caches the state so `gl.stencilOp()` is only
	 * called when necessary.
	 *
	 * @param {number} stencilFail - The function to use when the stencil test fails.
	 * @param {number} stencilZFail - The function to use when the stencil test passes, but the depth test fail.
	 * @param {number} stencilZPass - The function to use when both the stencil test and the depth test pass,
	 * or when the stencil test passes and there is no depth buffer or depth testing is disabled.
	 */
	setStencilOp( stencilFail, stencilZFail, stencilZPass ) {

		if ( this.currentStencilFail !== stencilFail ||
			 this.currentStencilZFail !== stencilZFail ||
			 this.currentStencilZPass !== stencilZPass ) {

			this.gl.stencilOp( stencilFail, stencilZFail, stencilZPass );

			this.currentStencilFail = stencilFail;
			this.currentStencilZFail = stencilZFail;
			this.currentStencilZPass = stencilZPass;

		}

	}

	/**
	 * Configures the WebGL state for the given material.
	 *
	 * @param {Material} material - The material to configure the state for.
	 * @param {number} frontFaceCW - Whether the front faces are counter-clockwise or not.
	 * @param {number} hardwareClippingPlanes - The number of hardware clipping planes.
	 */
	setMaterial( material, frontFaceCW, hardwareClippingPlanes ) {

		const { gl } = this;

		material.side === DoubleSide
			? this.disable( gl.CULL_FACE )
			: this.enable( gl.CULL_FACE );

		let flipSided = ( material.side === BackSide );
		if ( frontFaceCW ) flipSided = ! flipSided;

		this.setFlipSided( flipSided );

		( material.blending === NormalBlending && material.transparent === false )
			? this.setBlending( NoBlending )
			: this.setBlending( material.blending, material.blendEquation, material.blendSrc, material.blendDst, material.blendEquationAlpha, material.blendSrcAlpha, material.blendDstAlpha, material.premultipliedAlpha );

		this.setDepthFunc( material.depthFunc );
		this.setDepthTest( material.depthTest );
		this.setDepthMask( material.depthWrite );
		this.setColorMask( material.colorWrite );

		const stencilWrite = material.stencilWrite;
		this.setStencilTest( stencilWrite );
		if ( stencilWrite ) {

			this.setStencilMask( material.stencilWriteMask );
			this.setStencilFunc( material.stencilFunc, material.stencilRef, material.stencilFuncMask );
			this.setStencilOp( material.stencilFail, material.stencilZFail, material.stencilZPass );

		}

		this.setPolygonOffset( material.polygonOffset, material.polygonOffsetFactor, material.polygonOffsetUnits );

		material.alphaToCoverage === true && this.backend.renderer.samples > 1
			? this.enable( gl.SAMPLE_ALPHA_TO_COVERAGE )
			: this.disable( gl.SAMPLE_ALPHA_TO_COVERAGE );

		if ( hardwareClippingPlanes > 0 ) {

			if ( this.currentClippingPlanes !== hardwareClippingPlanes ) {

				const CLIP_DISTANCE0_WEBGL = 0x3000;

				for ( let i = 0; i < 8; i ++ ) {

					if ( i < hardwareClippingPlanes ) {

						this.enable( CLIP_DISTANCE0_WEBGL + i );

					} else {

						this.disable( CLIP_DISTANCE0_WEBGL + i );

					}

				}

			}

		}

	}

	/**
	 * Specifies the polygon offset.
	 *
	 * This method caches the state so `gl.polygonOffset()` is only
	 * called when necessary.
	 *
	 * @param {boolean} polygonOffset - Whether polygon offset is enabled or not.
	 * @param {number} factor - The scale factor for the variable depth offset for each polygon.
	 * @param {number} units - The multiplier by which an implementation-specific value is multiplied with to create a constant depth offset.
	 */
	setPolygonOffset( polygonOffset, factor, units ) {

		const { gl } = this;

		if ( polygonOffset ) {

			this.enable( gl.POLYGON_OFFSET_FILL );

			if ( this.currentPolygonOffsetFactor !== factor || this.currentPolygonOffsetUnits !== units ) {

				gl.polygonOffset( factor, units );

				this.currentPolygonOffsetFactor = factor;
				this.currentPolygonOffsetUnits = units;

			}

		} else {

			this.disable( gl.POLYGON_OFFSET_FILL );

		}

	}

	/**
	 * Defines the usage of the given WebGL program.
	 *
	 * This method caches the state so `gl.useProgram()` is only
	 * called when necessary.
	 *
	 * @param {WebGLProgram} program - The WebGL program to use.
	 * @return {boolean} Whether a program change has been executed or not.
	 */
	useProgram( program ) {

		if ( this.currentProgram !== program ) {

			this.gl.useProgram( program );

			this.currentProgram = program;

			return true;

		}

		return false;

	}

	/**
	 * Sets the vertex state by binding the given VAO and element buffer.
	 *
	 * @param {WebGLVertexArrayObject} vao - The VAO.
	 * @param {WebGLBuffer} indexBuffer - The index buffer.
	 * @return {boolean} Whether a vertex state has been changed or not.
	 */
	setVertexState( vao, indexBuffer = null ) {

		const gl = this.gl;

		if ( this.currentVAO !== vao || this.currentIndex !== indexBuffer ) {

			gl.bindVertexArray( vao );

			if ( indexBuffer !== null ) {

				gl.bindBuffer( gl.ELEMENT_ARRAY_BUFFER, indexBuffer );

			}

			this.currentVAO = vao;
			this.currentIndex = indexBuffer;

			return true;

		}

		return false;

	}

	/**
	 * Resets the vertex array state by resetting the VAO and element buffer.
	 */
	resetVertexState() {

		const gl = this.gl;

		gl.bindVertexArray( null );
		gl.bindBuffer( gl.ELEMENT_ARRAY_BUFFER, null );

		this.currentVAO = null;
		this.currentIndex = null;

	}

	// framebuffer


	/**
	 * Binds the given framebuffer.
	 *
	 * This method caches the state so `gl.bindFramebuffer()` is only
	 * called when necessary.
	 *
	 * @param {number} target - The binding point (target).
	 * @param {WebGLFramebuffer} framebuffer - The WebGL framebuffer to bind.
	 * @return {boolean} Whether a bind has been executed or not.
	 */
	bindFramebuffer( target, framebuffer ) {

		const { gl, currentBoundFramebuffers } = this;

		if ( currentBoundFramebuffers[ target ] !== framebuffer ) {

			gl.bindFramebuffer( target, framebuffer );

			currentBoundFramebuffers[ target ] = framebuffer;

			// gl.DRAW_FRAMEBUFFER is equivalent to gl.FRAMEBUFFER

			if ( target === gl.DRAW_FRAMEBUFFER ) {

				currentBoundFramebuffers[ gl.FRAMEBUFFER ] = framebuffer;

			}

			if ( target === gl.FRAMEBUFFER ) {

				currentBoundFramebuffers[ gl.DRAW_FRAMEBUFFER ] = framebuffer;

			}

			return true;

		}

		return false;

	}

	/**
	 * Defines draw buffers to which fragment colors are written into.
	 * Configures the MRT setup of custom framebuffers.
	 *
	 * This method caches the state so `gl.drawBuffers()` is only
	 * called when necessary.
	 *
	 * @param {RenderContext} renderContext - The render context.
	 * @param {WebGLFramebuffer} framebuffer - The WebGL framebuffer.
	 */
	drawBuffers( renderContext, framebuffer ) {

		const { gl } = this;

		let drawBuffers = [];

		let needsUpdate = false;

		if ( renderContext.textures !== null ) {

			drawBuffers = this.currentDrawbuffers.get( framebuffer );

			if ( drawBuffers === undefined ) {

				drawBuffers = [];
				this.currentDrawbuffers.set( framebuffer, drawBuffers );

			}


			const textures = renderContext.textures;

			if ( drawBuffers.length !== textures.length || drawBuffers[ 0 ] !== gl.COLOR_ATTACHMENT0 ) {

				for ( let i = 0, il = textures.length; i < il; i ++ ) {

					drawBuffers[ i ] = gl.COLOR_ATTACHMENT0 + i;

				}

				drawBuffers.length = textures.length;

				needsUpdate = true;

			}


		} else {

			if ( drawBuffers[ 0 ] !== gl.BACK ) {

				drawBuffers[ 0 ] = gl.BACK;

				needsUpdate = true;

			}

		}

		if ( needsUpdate ) {

			gl.drawBuffers( drawBuffers );

		}

	}


	// texture

	/**
	 * Makes the given texture unit active.
	 *
	 * This method caches the state so `gl.activeTexture()` is only
	 * called when necessary.
	 *
	 * @param {number} webglSlot - The texture unit to make active.
	 */
	activeTexture( webglSlot ) {

		const { gl, currentTextureSlot, maxTextures } = this;

		if ( webglSlot === undefined ) webglSlot = gl.TEXTURE0 + maxTextures - 1;

		if ( currentTextureSlot !== webglSlot ) {

			gl.activeTexture( webglSlot );
			this.currentTextureSlot = webglSlot;

		}

	}

	/**
	 * Binds the given WebGL texture to a target.
	 *
	 * This method caches the state so `gl.bindTexture()` is only
	 * called when necessary.
	 *
	 * @param {number} webglType - The binding point (target).
	 * @param {WebGLTexture} webglTexture - The WebGL texture to bind.
	 * @param {number} webglSlot - The texture.
	 */
	bindTexture( webglType, webglTexture, webglSlot ) {

		const { gl, currentTextureSlot, currentBoundTextures, maxTextures } = this;

		if ( webglSlot === undefined ) {

			if ( currentTextureSlot === null ) {

				webglSlot = gl.TEXTURE0 + maxTextures - 1;

			} else {

				webglSlot = currentTextureSlot;

			}

		}

		let boundTexture = currentBoundTextures[ webglSlot ];

		if ( boundTexture === undefined ) {

			boundTexture = { type: undefined, texture: undefined };
			currentBoundTextures[ webglSlot ] = boundTexture;

		}

		if ( boundTexture.type !== webglType || boundTexture.texture !== webglTexture ) {

			if ( currentTextureSlot !== webglSlot ) {

				gl.activeTexture( webglSlot );
				this.currentTextureSlot = webglSlot;

			}

			gl.bindTexture( webglType, webglTexture );

			boundTexture.type = webglType;
			boundTexture.texture = webglTexture;

		}

	}

	/**
	 * Binds a given WebGL buffer to a given binding point (target) at a given index.
	 *
	 * This method caches the state so `gl.bindBufferBase()` is only
	 * called when necessary.
	 *
	 * @param {number} target - The target for the bind operation.
	 * @param {number} index - The index of the target.
	 * @param {WebGLBuffer} buffer - The WebGL buffer.
	 * @return {boolean} Whether a bind has been executed or not.
	 */
	bindBufferBase( target, index, buffer ) {

		const { gl } = this;

		const key = `${target}-${index}`;

		if ( this.currentBoundBufferBases[ key ] !== buffer ) {

			gl.bindBufferBase( target, index, buffer );
			this.currentBoundBufferBases[ key ] = buffer;

			return true;

		}

		return false;

	}


	/**
	 * Unbinds the current bound texture.
	 *
	 * This method caches the state so `gl.bindTexture()` is only
	 * called when necessary.
	 */
	unbindTexture() {

		const { gl, currentTextureSlot, currentBoundTextures } = this;

		const boundTexture = currentBoundTextures[ currentTextureSlot ];

		if ( boundTexture !== undefined && boundTexture.type !== undefined ) {

			gl.bindTexture( boundTexture.type, null );

			boundTexture.type = undefined;
			boundTexture.texture = undefined;

		}

	}

}
```
</details>

#### Methods

##### `_init(): void`

<details><summary>Code</summary>

```ts
_init() {

		const gl = this.gl;

		// Store only WebGL constants here.

		equationToGL = {
			[ AddEquation ]: gl.FUNC_ADD,
			[ SubtractEquation ]: gl.FUNC_SUBTRACT,
			[ ReverseSubtractEquation ]: gl.FUNC_REVERSE_SUBTRACT
		};

		factorToGL = {
			[ ZeroFactor ]: gl.ZERO,
			[ OneFactor ]: gl.ONE,
			[ SrcColorFactor ]: gl.SRC_COLOR,
			[ SrcAlphaFactor ]: gl.SRC_ALPHA,
			[ SrcAlphaSaturateFactor ]: gl.SRC_ALPHA_SATURATE,
			[ DstColorFactor ]: gl.DST_COLOR,
			[ DstAlphaFactor ]: gl.DST_ALPHA,
			[ OneMinusSrcColorFactor ]: gl.ONE_MINUS_SRC_COLOR,
			[ OneMinusSrcAlphaFactor ]: gl.ONE_MINUS_SRC_ALPHA,
			[ OneMinusDstColorFactor ]: gl.ONE_MINUS_DST_COLOR,
			[ OneMinusDstAlphaFactor ]: gl.ONE_MINUS_DST_ALPHA
		};

		const scissorParam = gl.getParameter( gl.SCISSOR_BOX );
		const viewportParam = gl.getParameter( gl.VIEWPORT );

		this.currentScissor = new Vector4().fromArray( scissorParam );
		this.currentViewport = new Vector4().fromArray( viewportParam );

		this._tempVec4 = new Vector4();

	}
```
</details>

##### `enable(id: number): void`

<details><summary>Code</summary>

```ts
enable( id ) {

		const { enabled } = this;

		if ( enabled[ id ] !== true ) {

			this.gl.enable( id );
			enabled[ id ] = true;

		}

	}
```
</details>

##### `disable(id: number): void`

<details><summary>Code</summary>

```ts
disable( id ) {

		const { enabled } = this;

		if ( enabled[ id ] !== false ) {

			this.gl.disable( id );
			enabled[ id ] = false;

		}

	}
```
</details>

##### `setFlipSided(flipSided: boolean): void`

<details><summary>Code</summary>

```ts
setFlipSided( flipSided ) {

		if ( this.currentFlipSided !== flipSided ) {

			const { gl } = this;

			if ( flipSided ) {

				gl.frontFace( gl.CW );

			} else {

				gl.frontFace( gl.CCW );

			}

			this.currentFlipSided = flipSided;

		}

	}
```
</details>

##### `setCullFace(cullFace: number): void`

<details><summary>Code</summary>

```ts
setCullFace( cullFace ) {

		const { gl } = this;

		if ( cullFace !== CullFaceNone ) {

			this.enable( gl.CULL_FACE );

			if ( cullFace !== this.currentCullFace ) {

				if ( cullFace === CullFaceBack ) {

					gl.cullFace( gl.BACK );

				} else if ( cullFace === CullFaceFront ) {

					gl.cullFace( gl.FRONT );

				} else {

					gl.cullFace( gl.FRONT_AND_BACK );

				}

			}

		} else {

			this.disable( gl.CULL_FACE );

		}

		this.currentCullFace = cullFace;

	}
```
</details>

##### `setLineWidth(width: number): void`

<details><summary>Code</summary>

```ts
setLineWidth( width ) {

		const { currentLineWidth, gl } = this;

		if ( width !== currentLineWidth ) {

			gl.lineWidth( width );

			this.currentLineWidth = width;

		}

	}
```
</details>

##### `setBlending(blending: number, blendEquation: number, blendSrc: number, blendDst: number, blendEquationAlpha: number, blendSrcAlpha: number, blendDstAlpha: number, premultipliedAlpha: boolean): void`

<details><summary>Code</summary>

```ts
setBlending( blending, blendEquation, blendSrc, blendDst, blendEquationAlpha, blendSrcAlpha, blendDstAlpha, premultipliedAlpha ) {

		const { gl } = this;

		if ( blending === NoBlending ) {

			if ( this.currentBlendingEnabled === true ) {

				this.disable( gl.BLEND );
				this.currentBlendingEnabled = false;

			}

			return;

		}

		if ( this.currentBlendingEnabled === false ) {

			this.enable( gl.BLEND );
			this.currentBlendingEnabled = true;

		}

		if ( blending !== CustomBlending ) {

			if ( blending !== this.currentBlending || premultipliedAlpha !== this.currentPremultipledAlpha ) {

				if ( this.currentBlendEquation !== AddEquation || this.currentBlendEquationAlpha !== AddEquation ) {

					gl.blendEquation( gl.FUNC_ADD );

					this.currentBlendEquation = AddEquation;
					this.currentBlendEquationAlpha = AddEquation;

				}

				if ( premultipliedAlpha ) {

					switch ( blending ) {

						case NormalBlending:
							gl.blendFuncSeparate( gl.ONE, gl.ONE_MINUS_SRC_ALPHA, gl.ONE, gl.ONE_MINUS_SRC_ALPHA );
							break;

						case AdditiveBlending:
							gl.blendFunc( gl.ONE, gl.ONE );
							break;

						case SubtractiveBlending:
							gl.blendFuncSeparate( gl.ZERO, gl.ONE_MINUS_SRC_COLOR, gl.ZERO, gl.ONE );
							break;

						case MultiplyBlending:
							gl.blendFuncSeparate( gl.DST_COLOR, gl.ONE_MINUS_SRC_ALPHA, gl.ZERO, gl.ONE );
							break;

						default:
							console.error( 'THREE.WebGLState: Invalid blending: ', blending );
							break;

					}

				} else {

					switch ( blending ) {

						case NormalBlending:
							gl.blendFuncSeparate( gl.SRC_ALPHA, gl.ONE_MINUS_SRC_ALPHA, gl.ONE, gl.ONE_MINUS_SRC_ALPHA );
							break;

						case AdditiveBlending:
							gl.blendFuncSeparate( gl.SRC_ALPHA, gl.ONE, gl.ONE, gl.ONE );
							break;

						case SubtractiveBlending:
							console.error( 'THREE.WebGLState: SubtractiveBlending requires material.premultipliedAlpha = true' );
							break;

						case MultiplyBlending:
							console.error( 'THREE.WebGLState: MultiplyBlending requires material.premultipliedAlpha = true' );
							break;

						default:
							console.error( 'THREE.WebGLState: Invalid blending: ', blending );
							break;

					}

				}

				this.currentBlendSrc = null;
				this.currentBlendDst = null;
				this.currentBlendSrcAlpha = null;
				this.currentBlendDstAlpha = null;

				this.currentBlending = blending;
				this.currentPremultipledAlpha = premultipliedAlpha;

			}

			return;

		}

		// custom blending

		blendEquationAlpha = blendEquationAlpha || blendEquation;
		blendSrcAlpha = blendSrcAlpha || blendSrc;
		blendDstAlpha = blendDstAlpha || blendDst;

		if ( blendEquation !== this.currentBlendEquation || blendEquationAlpha !== this.currentBlendEquationAlpha ) {

			gl.blendEquationSeparate( equationToGL[ blendEquation ], equationToGL[ blendEquationAlpha ] );

			this.currentBlendEquation = blendEquation;
			this.currentBlendEquationAlpha = blendEquationAlpha;

		}

		if ( blendSrc !== this.currentBlendSrc || blendDst !== this.currentBlendDst || blendSrcAlpha !== this.currentBlendSrcAlpha || blendDstAlpha !== this.currentBlendDstAlpha ) {

			gl.blendFuncSeparate( factorToGL[ blendSrc ], factorToGL[ blendDst ], factorToGL[ blendSrcAlpha ], factorToGL[ blendDstAlpha ] );

			this.currentBlendSrc = blendSrc;
			this.currentBlendDst = blendDst;
			this.currentBlendSrcAlpha = blendSrcAlpha;
			this.currentBlendDstAlpha = blendDstAlpha;

		}

		this.currentBlending = blending;
		this.currentPremultipledAlpha = false;

	}
```
</details>

##### `setColorMask(colorMask: boolean): void`

<details><summary>Code</summary>

```ts
setColorMask( colorMask ) {

		if ( this.currentColorMask !== colorMask ) {

			this.gl.colorMask( colorMask, colorMask, colorMask, colorMask );
			this.currentColorMask = colorMask;

		}

	}
```
</details>

##### `setDepthTest(depthTest: boolean): void`

<details><summary>Code</summary>

```ts
setDepthTest( depthTest ) {

		const { gl } = this;

		if ( depthTest ) {

			this.enable( gl.DEPTH_TEST );

		} else {

			this.disable( gl.DEPTH_TEST );

		}

	}
```
</details>

##### `setDepthMask(depthMask: boolean): void`

<details><summary>Code</summary>

```ts
setDepthMask( depthMask ) {

		if ( this.currentDepthMask !== depthMask ) {

			this.gl.depthMask( depthMask );
			this.currentDepthMask = depthMask;

		}

	}
```
</details>

##### `setDepthFunc(depthFunc: number): void`

<details><summary>Code</summary>

```ts
setDepthFunc( depthFunc ) {

		if ( this.currentDepthFunc !== depthFunc ) {

			const { gl } = this;

			switch ( depthFunc ) {

				case NeverDepth:

					gl.depthFunc( gl.NEVER );
					break;

				case AlwaysDepth:

					gl.depthFunc( gl.ALWAYS );
					break;

				case LessDepth:

					gl.depthFunc( gl.LESS );
					break;

				case LessEqualDepth:

					gl.depthFunc( gl.LEQUAL );
					break;

				case EqualDepth:

					gl.depthFunc( gl.EQUAL );
					break;

				case GreaterEqualDepth:

					gl.depthFunc( gl.GEQUAL );
					break;

				case GreaterDepth:

					gl.depthFunc( gl.GREATER );
					break;

				case NotEqualDepth:

					gl.depthFunc( gl.NOTEQUAL );
					break;

				default:

					gl.depthFunc( gl.LEQUAL );

			}

			this.currentDepthFunc = depthFunc;

		}

	}
```
</details>

##### `scissor(x: number, y: number, width: number, height: number): void`

<details><summary>Code</summary>

```ts
scissor( x, y, width, height ) {

		const scissor = this._tempVec4.set( x, y, width, height );

		if ( this.currentScissor.equals( scissor ) === false ) {

			const { gl } = this;

			gl.scissor( scissor.x, scissor.y, scissor.z, scissor.w );
			this.currentScissor.copy( scissor );

		}

	}
```
</details>

##### `viewport(x: number, y: number, width: number, height: number): void`

<details><summary>Code</summary>

```ts
viewport( x, y, width, height ) {

		const viewport = this._tempVec4.set( x, y, width, height );

		if ( this.currentViewport.equals( viewport ) === false ) {

			const { gl } = this;

			gl.viewport( viewport.x, viewport.y, viewport.z, viewport.w );
			this.currentViewport.copy( viewport );

		}

	}
```
</details>

##### `setScissorTest(boolean: boolean): void`

<details><summary>Code</summary>

```ts
setScissorTest( boolean ) {

		const gl = this.gl;

		if ( boolean ) {

			gl.enable( gl.SCISSOR_TEST );

		} else {

			gl.disable( gl.SCISSOR_TEST );

		}

	}
```
</details>

##### `setStencilTest(stencilTest: boolean): void`

<details><summary>Code</summary>

```ts
setStencilTest( stencilTest ) {

		const { gl } = this;

		if ( stencilTest ) {

			this.enable( gl.STENCIL_TEST );

		} else {

			this.disable( gl.STENCIL_TEST );

		}

	}
```
</details>

##### `setStencilMask(stencilMask: boolean): void`

<details><summary>Code</summary>

```ts
setStencilMask( stencilMask ) {

		if ( this.currentStencilMask !== stencilMask ) {

			this.gl.stencilMask( stencilMask );
			this.currentStencilMask = stencilMask;

		}

	}
```
</details>

##### `setStencilFunc(stencilFunc: number, stencilRef: number, stencilMask: number): void`

<details><summary>Code</summary>

```ts
setStencilFunc( stencilFunc, stencilRef, stencilMask ) {

		if ( this.currentStencilFunc !== stencilFunc ||
			 this.currentStencilRef !== stencilRef ||
			 this.currentStencilFuncMask !== stencilMask ) {

			this.gl.stencilFunc( stencilFunc, stencilRef, stencilMask );

			this.currentStencilFunc = stencilFunc;
			this.currentStencilRef = stencilRef;
			this.currentStencilFuncMask = stencilMask;

		}

	}
```
</details>

##### `setStencilOp(stencilFail: number, stencilZFail: number, stencilZPass: number): void`

<details><summary>Code</summary>

```ts
setStencilOp( stencilFail, stencilZFail, stencilZPass ) {

		if ( this.currentStencilFail !== stencilFail ||
			 this.currentStencilZFail !== stencilZFail ||
			 this.currentStencilZPass !== stencilZPass ) {

			this.gl.stencilOp( stencilFail, stencilZFail, stencilZPass );

			this.currentStencilFail = stencilFail;
			this.currentStencilZFail = stencilZFail;
			this.currentStencilZPass = stencilZPass;

		}

	}
```
</details>

##### `setMaterial(material: Material, frontFaceCW: number, hardwareClippingPlanes: number): void`

<details><summary>Code</summary>

```ts
setMaterial( material, frontFaceCW, hardwareClippingPlanes ) {

		const { gl } = this;

		material.side === DoubleSide
			? this.disable( gl.CULL_FACE )
			: this.enable( gl.CULL_FACE );

		let flipSided = ( material.side === BackSide );
		if ( frontFaceCW ) flipSided = ! flipSided;

		this.setFlipSided( flipSided );

		( material.blending === NormalBlending && material.transparent === false )
			? this.setBlending( NoBlending )
			: this.setBlending( material.blending, material.blendEquation, material.blendSrc, material.blendDst, material.blendEquationAlpha, material.blendSrcAlpha, material.blendDstAlpha, material.premultipliedAlpha );

		this.setDepthFunc( material.depthFunc );
		this.setDepthTest( material.depthTest );
		this.setDepthMask( material.depthWrite );
		this.setColorMask( material.colorWrite );

		const stencilWrite = material.stencilWrite;
		this.setStencilTest( stencilWrite );
		if ( stencilWrite ) {

			this.setStencilMask( material.stencilWriteMask );
			this.setStencilFunc( material.stencilFunc, material.stencilRef, material.stencilFuncMask );
			this.setStencilOp( material.stencilFail, material.stencilZFail, material.stencilZPass );

		}

		this.setPolygonOffset( material.polygonOffset, material.polygonOffsetFactor, material.polygonOffsetUnits );

		material.alphaToCoverage === true && this.backend.renderer.samples > 1
			? this.enable( gl.SAMPLE_ALPHA_TO_COVERAGE )
			: this.disable( gl.SAMPLE_ALPHA_TO_COVERAGE );

		if ( hardwareClippingPlanes > 0 ) {

			if ( this.currentClippingPlanes !== hardwareClippingPlanes ) {

				const CLIP_DISTANCE0_WEBGL = 0x3000;

				for ( let i = 0; i < 8; i ++ ) {

					if ( i < hardwareClippingPlanes ) {

						this.enable( CLIP_DISTANCE0_WEBGL + i );

					} else {

						this.disable( CLIP_DISTANCE0_WEBGL + i );

					}

				}

			}

		}

	}
```
</details>

##### `setPolygonOffset(polygonOffset: boolean, factor: number, units: number): void`

<details><summary>Code</summary>

```ts
setPolygonOffset( polygonOffset, factor, units ) {

		const { gl } = this;

		if ( polygonOffset ) {

			this.enable( gl.POLYGON_OFFSET_FILL );

			if ( this.currentPolygonOffsetFactor !== factor || this.currentPolygonOffsetUnits !== units ) {

				gl.polygonOffset( factor, units );

				this.currentPolygonOffsetFactor = factor;
				this.currentPolygonOffsetUnits = units;

			}

		} else {

			this.disable( gl.POLYGON_OFFSET_FILL );

		}

	}
```
</details>

##### `useProgram(program: WebGLProgram): boolean`

<details><summary>Code</summary>

```ts
useProgram( program ) {

		if ( this.currentProgram !== program ) {

			this.gl.useProgram( program );

			this.currentProgram = program;

			return true;

		}

		return false;

	}
```
</details>

##### `setVertexState(vao: WebGLVertexArrayObject, indexBuffer: WebGLBuffer): boolean`

<details><summary>Code</summary>

```ts
setVertexState( vao, indexBuffer = null ) {

		const gl = this.gl;

		if ( this.currentVAO !== vao || this.currentIndex !== indexBuffer ) {

			gl.bindVertexArray( vao );

			if ( indexBuffer !== null ) {

				gl.bindBuffer( gl.ELEMENT_ARRAY_BUFFER, indexBuffer );

			}

			this.currentVAO = vao;
			this.currentIndex = indexBuffer;

			return true;

		}

		return false;

	}
```
</details>

##### `resetVertexState(): void`

<details><summary>Code</summary>

```ts
resetVertexState() {

		const gl = this.gl;

		gl.bindVertexArray( null );
		gl.bindBuffer( gl.ELEMENT_ARRAY_BUFFER, null );

		this.currentVAO = null;
		this.currentIndex = null;

	}
```
</details>

##### `bindFramebuffer(target: number, framebuffer: WebGLFramebuffer): boolean`

<details><summary>Code</summary>

```ts
bindFramebuffer( target, framebuffer ) {

		const { gl, currentBoundFramebuffers } = this;

		if ( currentBoundFramebuffers[ target ] !== framebuffer ) {

			gl.bindFramebuffer( target, framebuffer );

			currentBoundFramebuffers[ target ] = framebuffer;

			// gl.DRAW_FRAMEBUFFER is equivalent to gl.FRAMEBUFFER

			if ( target === gl.DRAW_FRAMEBUFFER ) {

				currentBoundFramebuffers[ gl.FRAMEBUFFER ] = framebuffer;

			}

			if ( target === gl.FRAMEBUFFER ) {

				currentBoundFramebuffers[ gl.DRAW_FRAMEBUFFER ] = framebuffer;

			}

			return true;

		}

		return false;

	}
```
</details>

##### `drawBuffers(renderContext: RenderContext, framebuffer: WebGLFramebuffer): void`

<details><summary>Code</summary>

```ts
drawBuffers( renderContext, framebuffer ) {

		const { gl } = this;

		let drawBuffers = [];

		let needsUpdate = false;

		if ( renderContext.textures !== null ) {

			drawBuffers = this.currentDrawbuffers.get( framebuffer );

			if ( drawBuffers === undefined ) {

				drawBuffers = [];
				this.currentDrawbuffers.set( framebuffer, drawBuffers );

			}


			const textures = renderContext.textures;

			if ( drawBuffers.length !== textures.length || drawBuffers[ 0 ] !== gl.COLOR_ATTACHMENT0 ) {

				for ( let i = 0, il = textures.length; i < il; i ++ ) {

					drawBuffers[ i ] = gl.COLOR_ATTACHMENT0 + i;

				}

				drawBuffers.length = textures.length;

				needsUpdate = true;

			}


		} else {

			if ( drawBuffers[ 0 ] !== gl.BACK ) {

				drawBuffers[ 0 ] = gl.BACK;

				needsUpdate = true;

			}

		}

		if ( needsUpdate ) {

			gl.drawBuffers( drawBuffers );

		}

	}
```
</details>

##### `activeTexture(webglSlot: number): void`

<details><summary>Code</summary>

```ts
activeTexture( webglSlot ) {

		const { gl, currentTextureSlot, maxTextures } = this;

		if ( webglSlot === undefined ) webglSlot = gl.TEXTURE0 + maxTextures - 1;

		if ( currentTextureSlot !== webglSlot ) {

			gl.activeTexture( webglSlot );
			this.currentTextureSlot = webglSlot;

		}

	}
```
</details>

##### `bindTexture(webglType: number, webglTexture: WebGLTexture, webglSlot: number): void`

<details><summary>Code</summary>

```ts
bindTexture( webglType, webglTexture, webglSlot ) {

		const { gl, currentTextureSlot, currentBoundTextures, maxTextures } = this;

		if ( webglSlot === undefined ) {

			if ( currentTextureSlot === null ) {

				webglSlot = gl.TEXTURE0 + maxTextures - 1;

			} else {

				webglSlot = currentTextureSlot;

			}

		}

		let boundTexture = currentBoundTextures[ webglSlot ];

		if ( boundTexture === undefined ) {

			boundTexture = { type: undefined, texture: undefined };
			currentBoundTextures[ webglSlot ] = boundTexture;

		}

		if ( boundTexture.type !== webglType || boundTexture.texture !== webglTexture ) {

			if ( currentTextureSlot !== webglSlot ) {

				gl.activeTexture( webglSlot );
				this.currentTextureSlot = webglSlot;

			}

			gl.bindTexture( webglType, webglTexture );

			boundTexture.type = webglType;
			boundTexture.texture = webglTexture;

		}

	}
```
</details>

##### `bindBufferBase(target: number, index: number, buffer: WebGLBuffer): boolean`

<details><summary>Code</summary>

```ts
bindBufferBase( target, index, buffer ) {

		const { gl } = this;

		const key = `${target}-${index}`;

		if ( this.currentBoundBufferBases[ key ] !== buffer ) {

			gl.bindBufferBase( target, index, buffer );
			this.currentBoundBufferBases[ key ] = buffer;

			return true;

		}

		return false;

	}
```
</details>

##### `unbindTexture(): void`

<details><summary>Code</summary>

```ts
unbindTexture() {

		const { gl, currentTextureSlot, currentBoundTextures } = this;

		const boundTexture = currentBoundTextures[ currentTextureSlot ];

		if ( boundTexture !== undefined && boundTexture.type !== undefined ) {

			gl.bindTexture( boundTexture.type, null );

			boundTexture.type = undefined;
			boundTexture.texture = undefined;

		}

	}
```
</details>


---