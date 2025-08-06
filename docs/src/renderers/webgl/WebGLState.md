[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLState.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 73 |
| 📦 Imports | 41 |
| 📊 Variables & Constants | 61 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLState.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NotEqualDepth` | `../../constants.js` |
| `GreaterDepth` | `../../constants.js` |
| `GreaterEqualDepth` | `../../constants.js` |
| `EqualDepth` | `../../constants.js` |
| `LessEqualDepth` | `../../constants.js` |
| `LessDepth` | `../../constants.js` |
| `AlwaysDepth` | `../../constants.js` |
| `NeverDepth` | `../../constants.js` |
| `CullFaceFront` | `../../constants.js` |
| `CullFaceBack` | `../../constants.js` |
| `CullFaceNone` | `../../constants.js` |
| `DoubleSide` | `../../constants.js` |
| `BackSide` | `../../constants.js` |
| `CustomBlending` | `../../constants.js` |
| `MultiplyBlending` | `../../constants.js` |
| `SubtractiveBlending` | `../../constants.js` |
| `AdditiveBlending` | `../../constants.js` |
| `NoBlending` | `../../constants.js` |
| `NormalBlending` | `../../constants.js` |
| `AddEquation` | `../../constants.js` |
| `SubtractEquation` | `../../constants.js` |
| `ReverseSubtractEquation` | `../../constants.js` |
| `MinEquation` | `../../constants.js` |
| `MaxEquation` | `../../constants.js` |
| `ZeroFactor` | `../../constants.js` |
| `OneFactor` | `../../constants.js` |
| `SrcColorFactor` | `../../constants.js` |
| `SrcAlphaFactor` | `../../constants.js` |
| `SrcAlphaSaturateFactor` | `../../constants.js` |
| `DstColorFactor` | `../../constants.js` |
| `DstAlphaFactor` | `../../constants.js` |
| `OneMinusSrcColorFactor` | `../../constants.js` |
| `OneMinusSrcAlphaFactor` | `../../constants.js` |
| `OneMinusDstColorFactor` | `../../constants.js` |
| `OneMinusDstAlphaFactor` | `../../constants.js` |
| `ConstantColorFactor` | `../../constants.js` |
| `OneMinusConstantColorFactor` | `../../constants.js` |
| `ConstantAlphaFactor` | `../../constants.js` |
| `OneMinusConstantAlphaFactor` | `../../constants.js` |
| `Color` | `../../math/Color.js` |
| `Vector4` | `../../math/Vector4.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `reversedFuncs` | `{ [x: number]: number; }` | let/var | `{ [ NeverDepth ]: AlwaysDepth, [ LessDepth ]: GreaterDepth, [ EqualDepth ]: N...` | ✗ |
| `locked` | `boolean` | let/var | `false` | ✗ |
| `color` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `currentColorMask` | `any` | let/var | `null` | ✗ |
| `currentColorClear` | `Vector4` | let/var | `new Vector4( 0, 0, 0, 0 )` | ✗ |
| `locked` | `boolean` | let/var | `false` | ✗ |
| `currentReversed` | `boolean` | let/var | `false` | ✗ |
| `currentDepthMask` | `any` | let/var | `null` | ✗ |
| `currentDepthFunc` | `any` | let/var | `null` | ✗ |
| `currentDepthClear` | `any` | let/var | `null` | ✗ |
| `oldDepth` | `any` | let/var | `currentDepthClear` | ✗ |
| `locked` | `boolean` | let/var | `false` | ✗ |
| `currentStencilMask` | `any` | let/var | `null` | ✗ |
| `currentStencilFunc` | `any` | let/var | `null` | ✗ |
| `currentStencilRef` | `any` | let/var | `null` | ✗ |
| `currentStencilFuncMask` | `any` | let/var | `null` | ✗ |
| `currentStencilFail` | `any` | let/var | `null` | ✗ |
| `currentStencilZFail` | `any` | let/var | `null` | ✗ |
| `currentStencilZPass` | `any` | let/var | `null` | ✗ |
| `currentStencilClear` | `any` | let/var | `null` | ✗ |
| `colorBuffer` | `any` | let/var | `new ColorBuffer()` | ✗ |
| `depthBuffer` | `any` | let/var | `new DepthBuffer()` | ✗ |
| `stencilBuffer` | `any` | let/var | `new StencilBuffer()` | ✗ |
| `uboBindings` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `uboProgramMap` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `enabledCapabilities` | `{}` | let/var | `{}` | ✗ |
| `currentBoundFramebuffers` | `{}` | let/var | `{}` | ✗ |
| `currentDrawbuffers` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `defaultDrawbuffers` | `any[]` | let/var | `[]` | ✗ |
| `currentProgram` | `any` | let/var | `null` | ✗ |
| `currentBlendingEnabled` | `boolean` | let/var | `false` | ✗ |
| `currentBlending` | `any` | let/var | `null` | ✗ |
| `currentBlendEquation` | `any` | let/var | `null` | ✗ |
| `currentBlendSrc` | `any` | let/var | `null` | ✗ |
| `currentBlendDst` | `any` | let/var | `null` | ✗ |
| `currentBlendEquationAlpha` | `any` | let/var | `null` | ✗ |
| `currentBlendSrcAlpha` | `any` | let/var | `null` | ✗ |
| `currentBlendDstAlpha` | `any` | let/var | `null` | ✗ |
| `currentBlendColor` | `Color` | let/var | `new Color( 0, 0, 0 )` | ✗ |
| `currentBlendAlpha` | `number` | let/var | `0` | ✗ |
| `currentPremultipledAlpha` | `boolean` | let/var | `false` | ✗ |
| `currentFlipSided` | `any` | let/var | `null` | ✗ |
| `currentCullFace` | `any` | let/var | `null` | ✗ |
| `currentLineWidth` | `any` | let/var | `null` | ✗ |
| `currentPolygonOffsetFactor` | `any` | let/var | `null` | ✗ |
| `currentPolygonOffsetUnits` | `any` | let/var | `null` | ✗ |
| `lineWidthAvailable` | `boolean` | let/var | `false` | ✗ |
| `version` | `number` | let/var | `0` | ✗ |
| `currentTextureSlot` | `any` | let/var | `null` | ✗ |
| `currentBoundTextures` | `{}` | let/var | `{}` | ✗ |
| `data` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( 4 )` | ✗ |
| `emptyTextures` | `{}` | let/var | `{}` | ✗ |
| `drawBuffers` | `any[]` | let/var | `defaultDrawbuffers` | ✗ |
| `needsUpdate` | `boolean` | let/var | `false` | ✗ |
| `textures` | `any` | let/var | `renderTarget.textures` | ✗ |
| `equationToGL` | `{ [x: number]: any; }` | let/var | `{ [ AddEquation ]: gl.FUNC_ADD, [ SubtractEquation ]: gl.FUNC_SUBTRACT, [ Rev...` | ✗ |
| `factorToGL` | `{ [x: number]: any; }` | let/var | `{ [ ZeroFactor ]: gl.ZERO, [ OneFactor ]: gl.ONE, [ SrcColorFactor ]: gl.SRC_...` | ✗ |
| `flipSided` | `boolean` | let/var | `( material.side === BackSide )` | ✗ |
| `stencilWrite` | `any` | let/var | `material.stencilWrite` | ✗ |
| `boundTexture` | `any` | let/var | `currentBoundTextures[ webglSlot ]` | ✗ |
| `boundTexture` | `any` | let/var | `currentBoundTextures[ currentTextureSlot ]` | ✗ |


---

## Functions

### `WebGLState(gl: any, extensions: any): { buffers: { color: any; depth: any; stencil: any; }; enable: (id: any) => void; disable: (id: any) => void; bindFramebuffer: (target: any, framebuffer: any) => boolean; drawBuffers: (renderTarget: any, framebuffer: any) => void; ... 25 more ...; reset: () => void; }`

**Parameters:**

- **`gl`** `any`
- **`extensions`** `any`

**Returns:** `{ buffers: { color: any; depth: any; stencil: any; }; enable: (id: any) => void; disable: (id: any) => void; bindFramebuffer: (target: any, framebuffer: any) => boolean; drawBuffers: (renderTarget: any, framebuffer: any) => void; ... 25 more ...; reset: () => void; }`

**Calls:**

- `gl.colorMask`
- `color.set`
- `currentColorClear.equals`
- `gl.clearColor`
- `currentColorClear.copy`
- `currentColorClear.set`
- `extensions.get`
- `ext.clipControlEXT`
- `this.setClear`
- `enable`
- `disable`
- `gl.depthMask`
- `gl.depthFunc`
- `gl.clearDepth`
- `gl.stencilMask`
- `gl.stencilFunc`
- `gl.stencilOp`
- `gl.clearStencil`
- `gl.getParameter`
- `glVersion.indexOf`
- `parseFloat`
- `/^WebGL (\d)/.exec`
- `/^OpenGL ES (\d)/.exec`
- `new Vector4().fromArray`
- `gl.createTexture`
- `gl.bindTexture`
- `gl.texParameteri`
- `gl.texImage3D`
- `gl.texImage2D`
- `createTexture`
- `colorBuffer.setClear`
- `depthBuffer.setClear`
- `stencilBuffer.setClear`
- `depthBuffer.setFunc`
- `setFlipSided`
- `setCullFace`
- `setBlending`
- `gl.enable`
- `gl.disable`
- `gl.bindFramebuffer`
- `currentDrawbuffers.get`
- `currentDrawbuffers.set`
- `gl.drawBuffers`
- `gl.useProgram`
- `gl.blendEquation`
- `gl.blendFuncSeparate`
- `gl.blendFunc`
- `console.error`
- `currentBlendColor.set`
- `gl.blendEquationSeparate`
- `blendColor.equals`
- `gl.blendColor`
- `currentBlendColor.copy`
- `depthBuffer.setTest`
- `depthBuffer.setMask`
- `colorBuffer.setMask`
- `stencilBuffer.setTest`
- `stencilBuffer.setMask`
- `stencilBuffer.setFunc`
- `stencilBuffer.setOp`
- `setPolygonOffset`
- `gl.frontFace`
- `gl.cullFace`
- `gl.lineWidth`
- `gl.polygonOffset`
- `gl.activeTexture`
- `gl.compressedTexImage2D`
- `gl.compressedTexImage3D`
- `gl.texSubImage2D`
- `gl.texSubImage3D`
- `gl.compressedTexSubImage2D`
- `gl.compressedTexSubImage3D`
- `gl.texStorage2D`
- `gl.texStorage3D`
- `currentScissor.equals`
- `gl.scissor`
- `currentScissor.copy`
- `currentViewport.equals`
- `gl.viewport`
- `currentViewport.copy`
- `uboProgramMap.get`
- `uboProgramMap.set`
- `mapping.get`
- `gl.getUniformBlockIndex`
- `mapping.set`
- `uboBindings.get`
- `gl.uniformBlockBinding`
- `uboBindings.set`
- `depthBuffer.setReversed`
- `currentScissor.set`
- `currentViewport.set`
- `colorBuffer.reset`
- `depthBuffer.reset`
- `stencilBuffer.reset`

**Internal Comments:**
```
// (x6)
// init (x4)
// gl.DRAW_FRAMEBUFFER is equivalent to gl.FRAMEBUFFER
// custom blending (x3)
// texture
// bind shader specific block index to global block point (x4)
// reset state (x4)
// reset internals (x3)
```

<details><summary>Code</summary>

```typescript
function WebGLState( gl, extensions ) {

	function ColorBuffer() {

		let locked = false;

		const color = new Vector4();
		let currentColorMask = null;
		const currentColorClear = new Vector4( 0, 0, 0, 0 );

		return {

			setMask: function ( colorMask ) {

				if ( currentColorMask !== colorMask && ! locked ) {

					gl.colorMask( colorMask, colorMask, colorMask, colorMask );
					currentColorMask = colorMask;

				}

			},

			setLocked: function ( lock ) {

				locked = lock;

			},

			setClear: function ( r, g, b, a, premultipliedAlpha ) {

				if ( premultipliedAlpha === true ) {

					r *= a; g *= a; b *= a;

				}

				color.set( r, g, b, a );

				if ( currentColorClear.equals( color ) === false ) {

					gl.clearColor( r, g, b, a );
					currentColorClear.copy( color );

				}

			},

			reset: function () {

				locked = false;

				currentColorMask = null;
				currentColorClear.set( - 1, 0, 0, 0 ); // set to invalid state

			}

		};

	}

	function DepthBuffer() {

		let locked = false;

		let currentReversed = false;
		let currentDepthMask = null;
		let currentDepthFunc = null;
		let currentDepthClear = null;

		return {

			setReversed: function ( reversed ) {

				if ( currentReversed !== reversed ) {

					const ext = extensions.get( 'EXT_clip_control' );

					if ( reversed ) {

						ext.clipControlEXT( ext.LOWER_LEFT_EXT, ext.ZERO_TO_ONE_EXT );

					} else {

						ext.clipControlEXT( ext.LOWER_LEFT_EXT, ext.NEGATIVE_ONE_TO_ONE_EXT );

					}

					currentReversed = reversed;

					const oldDepth = currentDepthClear;
					currentDepthClear = null;
					this.setClear( oldDepth );

				}

			},

			getReversed: function () {

				return currentReversed;

			},

			setTest: function ( depthTest ) {

				if ( depthTest ) {

					enable( gl.DEPTH_TEST );

				} else {

					disable( gl.DEPTH_TEST );

				}

			},

			setMask: function ( depthMask ) {

				if ( currentDepthMask !== depthMask && ! locked ) {

					gl.depthMask( depthMask );
					currentDepthMask = depthMask;

				}

			},

			setFunc: function ( depthFunc ) {

				if ( currentReversed ) depthFunc = reversedFuncs[ depthFunc ];

				if ( currentDepthFunc !== depthFunc ) {

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

					currentDepthFunc = depthFunc;

				}

			},

			setLocked: function ( lock ) {

				locked = lock;

			},

			setClear: function ( depth ) {

				if ( currentDepthClear !== depth ) {

					if ( currentReversed ) {

						depth = 1 - depth;

					}

					gl.clearDepth( depth );
					currentDepthClear = depth;

				}

			},

			reset: function () {

				locked = false;

				currentDepthMask = null;
				currentDepthFunc = null;
				currentDepthClear = null;
				currentReversed = false;

			}

		};

	}

	function StencilBuffer() {

		let locked = false;

		let currentStencilMask = null;
		let currentStencilFunc = null;
		let currentStencilRef = null;
		let currentStencilFuncMask = null;
		let currentStencilFail = null;
		let currentStencilZFail = null;
		let currentStencilZPass = null;
		let currentStencilClear = null;

		return {

			setTest: function ( stencilTest ) {

				if ( ! locked ) {

					if ( stencilTest ) {

						enable( gl.STENCIL_TEST );

					} else {

						disable( gl.STENCIL_TEST );

					}

				}

			},

			setMask: function ( stencilMask ) {

				if ( currentStencilMask !== stencilMask && ! locked ) {

					gl.stencilMask( stencilMask );
					currentStencilMask = stencilMask;

				}

			},

			setFunc: function ( stencilFunc, stencilRef, stencilMask ) {

				if ( currentStencilFunc !== stencilFunc ||
				     currentStencilRef !== stencilRef ||
				     currentStencilFuncMask !== stencilMask ) {

					gl.stencilFunc( stencilFunc, stencilRef, stencilMask );

					currentStencilFunc = stencilFunc;
					currentStencilRef = stencilRef;
					currentStencilFuncMask = stencilMask;

				}

			},

			setOp: function ( stencilFail, stencilZFail, stencilZPass ) {

				if ( currentStencilFail !== stencilFail ||
				     currentStencilZFail !== stencilZFail ||
				     currentStencilZPass !== stencilZPass ) {

					gl.stencilOp( stencilFail, stencilZFail, stencilZPass );

					currentStencilFail = stencilFail;
					currentStencilZFail = stencilZFail;
					currentStencilZPass = stencilZPass;

				}

			},

			setLocked: function ( lock ) {

				locked = lock;

			},

			setClear: function ( stencil ) {

				if ( currentStencilClear !== stencil ) {

					gl.clearStencil( stencil );
					currentStencilClear = stencil;

				}

			},

			reset: function () {

				locked = false;

				currentStencilMask = null;
				currentStencilFunc = null;
				currentStencilRef = null;
				currentStencilFuncMask = null;
				currentStencilFail = null;
				currentStencilZFail = null;
				currentStencilZPass = null;
				currentStencilClear = null;

			}

		};

	}

	//

	const colorBuffer = new ColorBuffer();
	const depthBuffer = new DepthBuffer();
	const stencilBuffer = new StencilBuffer();

	const uboBindings = new WeakMap();
	const uboProgramMap = new WeakMap();

	let enabledCapabilities = {};

	let currentBoundFramebuffers = {};
	let currentDrawbuffers = new WeakMap();
	let defaultDrawbuffers = [];

	let currentProgram = null;

	let currentBlendingEnabled = false;
	let currentBlending = null;
	let currentBlendEquation = null;
	let currentBlendSrc = null;
	let currentBlendDst = null;
	let currentBlendEquationAlpha = null;
	let currentBlendSrcAlpha = null;
	let currentBlendDstAlpha = null;
	let currentBlendColor = new Color( 0, 0, 0 );
	let currentBlendAlpha = 0;
	let currentPremultipledAlpha = false;

	let currentFlipSided = null;
	let currentCullFace = null;

	let currentLineWidth = null;

	let currentPolygonOffsetFactor = null;
	let currentPolygonOffsetUnits = null;

	const maxTextures = gl.getParameter( gl.MAX_COMBINED_TEXTURE_IMAGE_UNITS );

	let lineWidthAvailable = false;
	let version = 0;
	const glVersion = gl.getParameter( gl.VERSION );

	if ( glVersion.indexOf( 'WebGL' ) !== - 1 ) {

		version = parseFloat( /^WebGL (\d)/.exec( glVersion )[ 1 ] );
		lineWidthAvailable = ( version >= 1.0 );

	} else if ( glVersion.indexOf( 'OpenGL ES' ) !== - 1 ) {

		version = parseFloat( /^OpenGL ES (\d)/.exec( glVersion )[ 1 ] );
		lineWidthAvailable = ( version >= 2.0 );

	}

	let currentTextureSlot = null;
	let currentBoundTextures = {};

	const scissorParam = gl.getParameter( gl.SCISSOR_BOX );
	const viewportParam = gl.getParameter( gl.VIEWPORT );

	const currentScissor = new Vector4().fromArray( scissorParam );
	const currentViewport = new Vector4().fromArray( viewportParam );

	function createTexture( type, target, count, dimensions ) {

		const data = new Uint8Array( 4 ); // 4 is required to match default unpack alignment of 4.
		const texture = gl.createTexture();

		gl.bindTexture( type, texture );
		gl.texParameteri( type, gl.TEXTURE_MIN_FILTER, gl.NEAREST );
		gl.texParameteri( type, gl.TEXTURE_MAG_FILTER, gl.NEAREST );

		for ( let i = 0; i < count; i ++ ) {

			if ( type === gl.TEXTURE_3D || type === gl.TEXTURE_2D_ARRAY ) {

				gl.texImage3D( target, 0, gl.RGBA, 1, 1, dimensions, 0, gl.RGBA, gl.UNSIGNED_BYTE, data );

			} else {

				gl.texImage2D( target + i, 0, gl.RGBA, 1, 1, 0, gl.RGBA, gl.UNSIGNED_BYTE, data );

			}

		}

		return texture;

	}

	const emptyTextures = {};
	emptyTextures[ gl.TEXTURE_2D ] = createTexture( gl.TEXTURE_2D, gl.TEXTURE_2D, 1 );
	emptyTextures[ gl.TEXTURE_CUBE_MAP ] = createTexture( gl.TEXTURE_CUBE_MAP, gl.TEXTURE_CUBE_MAP_POSITIVE_X, 6 );
	emptyTextures[ gl.TEXTURE_2D_ARRAY ] = createTexture( gl.TEXTURE_2D_ARRAY, gl.TEXTURE_2D_ARRAY, 1, 1 );
	emptyTextures[ gl.TEXTURE_3D ] = createTexture( gl.TEXTURE_3D, gl.TEXTURE_3D, 1, 1 );

	// init

	colorBuffer.setClear( 0, 0, 0, 1 );
	depthBuffer.setClear( 1 );
	stencilBuffer.setClear( 0 );

	enable( gl.DEPTH_TEST );
	depthBuffer.setFunc( LessEqualDepth );

	setFlipSided( false );
	setCullFace( CullFaceBack );
	enable( gl.CULL_FACE );

	setBlending( NoBlending );

	//

	function enable( id ) {

		if ( enabledCapabilities[ id ] !== true ) {

			gl.enable( id );
			enabledCapabilities[ id ] = true;

		}

	}

	function disable( id ) {

		if ( enabledCapabilities[ id ] !== false ) {

			gl.disable( id );
			enabledCapabilities[ id ] = false;

		}

	}

	function bindFramebuffer( target, framebuffer ) {

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

	function drawBuffers( renderTarget, framebuffer ) {

		let drawBuffers = defaultDrawbuffers;

		let needsUpdate = false;

		if ( renderTarget ) {

			drawBuffers = currentDrawbuffers.get( framebuffer );

			if ( drawBuffers === undefined ) {

				drawBuffers = [];
				currentDrawbuffers.set( framebuffer, drawBuffers );

			}

			const textures = renderTarget.textures;

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

	function useProgram( program ) {

		if ( currentProgram !== program ) {

			gl.useProgram( program );

			currentProgram = program;

			return true;

		}

		return false;

	}

	const equationToGL = {
		[ AddEquation ]: gl.FUNC_ADD,
		[ SubtractEquation ]: gl.FUNC_SUBTRACT,
		[ ReverseSubtractEquation ]: gl.FUNC_REVERSE_SUBTRACT
	};

	equationToGL[ MinEquation ] = gl.MIN;
	equationToGL[ MaxEquation ] = gl.MAX;

	const factorToGL = {
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
		[ OneMinusDstAlphaFactor ]: gl.ONE_MINUS_DST_ALPHA,
		[ ConstantColorFactor ]: gl.CONSTANT_COLOR,
		[ OneMinusConstantColorFactor ]: gl.ONE_MINUS_CONSTANT_COLOR,
		[ ConstantAlphaFactor ]: gl.CONSTANT_ALPHA,
		[ OneMinusConstantAlphaFactor ]: gl.ONE_MINUS_CONSTANT_ALPHA
	};

	function setBlending( blending, blendEquation, blendSrc, blendDst, blendEquationAlpha, blendSrcAlpha, blendDstAlpha, blendColor, blendAlpha, premultipliedAlpha ) {

		if ( blending === NoBlending ) {

			if ( currentBlendingEnabled === true ) {

				disable( gl.BLEND );
				currentBlendingEnabled = false;

			}

			return;

		}

		if ( currentBlendingEnabled === false ) {

			enable( gl.BLEND );
			currentBlendingEnabled = true;

		}

		if ( blending !== CustomBlending ) {

			if ( blending !== currentBlending || premultipliedAlpha !== currentPremultipledAlpha ) {

				if ( currentBlendEquation !== AddEquation || currentBlendEquationAlpha !== AddEquation ) {

					gl.blendEquation( gl.FUNC_ADD );

					currentBlendEquation = AddEquation;
					currentBlendEquationAlpha = AddEquation;

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

				currentBlendSrc = null;
				currentBlendDst = null;
				currentBlendSrcAlpha = null;
				currentBlendDstAlpha = null;
				currentBlendColor.set( 0, 0, 0 );
				currentBlendAlpha = 0;

				currentBlending = blending;
				currentPremultipledAlpha = premultipliedAlpha;

			}

			return;

		}

		// custom blending

		blendEquationAlpha = blendEquationAlpha || blendEquation;
		blendSrcAlpha = blendSrcAlpha || blendSrc;
		blendDstAlpha = blendDstAlpha || blendDst;

		if ( blendEquation !== currentBlendEquation || blendEquationAlpha !== currentBlendEquationAlpha ) {

			gl.blendEquationSeparate( equationToGL[ blendEquation ], equationToGL[ blendEquationAlpha ] );

			currentBlendEquation = blendEquation;
			currentBlendEquationAlpha = blendEquationAlpha;

		}

		if ( blendSrc !== currentBlendSrc || blendDst !== currentBlendDst || blendSrcAlpha !== currentBlendSrcAlpha || blendDstAlpha !== currentBlendDstAlpha ) {

			gl.blendFuncSeparate( factorToGL[ blendSrc ], factorToGL[ blendDst ], factorToGL[ blendSrcAlpha ], factorToGL[ blendDstAlpha ] );

			currentBlendSrc = blendSrc;
			currentBlendDst = blendDst;
			currentBlendSrcAlpha = blendSrcAlpha;
			currentBlendDstAlpha = blendDstAlpha;

		}

		if ( blendColor.equals( currentBlendColor ) === false || blendAlpha !== currentBlendAlpha ) {

			gl.blendColor( blendColor.r, blendColor.g, blendColor.b, blendAlpha );

			currentBlendColor.copy( blendColor );
			currentBlendAlpha = blendAlpha;

		}

		currentBlending = blending;
		currentPremultipledAlpha = false;

	}

	function setMaterial( material, frontFaceCW ) {

		material.side === DoubleSide
			? disable( gl.CULL_FACE )
			: enable( gl.CULL_FACE );

		let flipSided = ( material.side === BackSide );
		if ( frontFaceCW ) flipSided = ! flipSided;

		setFlipSided( flipSided );

		( material.blending === NormalBlending && material.transparent === false )
			? setBlending( NoBlending )
			: setBlending( material.blending, material.blendEquation, material.blendSrc, material.blendDst, material.blendEquationAlpha, material.blendSrcAlpha, material.blendDstAlpha, material.blendColor, material.blendAlpha, material.premultipliedAlpha );

		depthBuffer.setFunc( material.depthFunc );
		depthBuffer.setTest( material.depthTest );
		depthBuffer.setMask( material.depthWrite );
		colorBuffer.setMask( material.colorWrite );

		const stencilWrite = material.stencilWrite;
		stencilBuffer.setTest( stencilWrite );
		if ( stencilWrite ) {

			stencilBuffer.setMask( material.stencilWriteMask );
			stencilBuffer.setFunc( material.stencilFunc, material.stencilRef, material.stencilFuncMask );
			stencilBuffer.setOp( material.stencilFail, material.stencilZFail, material.stencilZPass );

		}

		setPolygonOffset( material.polygonOffset, material.polygonOffsetFactor, material.polygonOffsetUnits );

		material.alphaToCoverage === true
			? enable( gl.SAMPLE_ALPHA_TO_COVERAGE )
			: disable( gl.SAMPLE_ALPHA_TO_COVERAGE );

	}

	//

	function setFlipSided( flipSided ) {

		if ( currentFlipSided !== flipSided ) {

			if ( flipSided ) {

				gl.frontFace( gl.CW );

			} else {

				gl.frontFace( gl.CCW );

			}

			currentFlipSided = flipSided;

		}

	}

	function setCullFace( cullFace ) {

		if ( cullFace !== CullFaceNone ) {

			enable( gl.CULL_FACE );

			if ( cullFace !== currentCullFace ) {

				if ( cullFace === CullFaceBack ) {

					gl.cullFace( gl.BACK );

				} else if ( cullFace === CullFaceFront ) {

					gl.cullFace( gl.FRONT );

				} else {

					gl.cullFace( gl.FRONT_AND_BACK );

				}

			}

		} else {

			disable( gl.CULL_FACE );

		}

		currentCullFace = cullFace;

	}

	function setLineWidth( width ) {

		if ( width !== currentLineWidth ) {

			if ( lineWidthAvailable ) gl.lineWidth( width );

			currentLineWidth = width;

		}

	}

	function setPolygonOffset( polygonOffset, factor, units ) {

		if ( polygonOffset ) {

			enable( gl.POLYGON_OFFSET_FILL );

			if ( currentPolygonOffsetFactor !== factor || currentPolygonOffsetUnits !== units ) {

				gl.polygonOffset( factor, units );

				currentPolygonOffsetFactor = factor;
				currentPolygonOffsetUnits = units;

			}

		} else {

			disable( gl.POLYGON_OFFSET_FILL );

		}

	}

	function setScissorTest( scissorTest ) {

		if ( scissorTest ) {

			enable( gl.SCISSOR_TEST );

		} else {

			disable( gl.SCISSOR_TEST );

		}

	}

	// texture

	function activeTexture( webglSlot ) {

		if ( webglSlot === undefined ) webglSlot = gl.TEXTURE0 + maxTextures - 1;

		if ( currentTextureSlot !== webglSlot ) {

			gl.activeTexture( webglSlot );
			currentTextureSlot = webglSlot;

		}

	}

	function bindTexture( webglType, webglTexture, webglSlot ) {

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
				currentTextureSlot = webglSlot;

			}

			gl.bindTexture( webglType, webglTexture || emptyTextures[ webglType ] );

			boundTexture.type = webglType;
			boundTexture.texture = webglTexture;

		}

	}

	function unbindTexture() {

		const boundTexture = currentBoundTextures[ currentTextureSlot ];

		if ( boundTexture !== undefined && boundTexture.type !== undefined ) {

			gl.bindTexture( boundTexture.type, null );

			boundTexture.type = undefined;
			boundTexture.texture = undefined;

		}

	}

	function compressedTexImage2D() {

		try {

			gl.compressedTexImage2D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}

	function compressedTexImage3D() {

		try {

			gl.compressedTexImage3D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}

	function texSubImage2D() {

		try {

			gl.texSubImage2D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}

	function texSubImage3D() {

		try {

			gl.texSubImage3D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}

	function compressedTexSubImage2D() {

		try {

			gl.compressedTexSubImage2D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}

	function compressedTexSubImage3D() {

		try {

			gl.compressedTexSubImage3D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}

	function texStorage2D() {

		try {

			gl.texStorage2D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}

	function texStorage3D() {

		try {

			gl.texStorage3D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}

	function texImage2D() {

		try {

			gl.texImage2D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}

	function texImage3D() {

		try {

			gl.texImage3D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}

	//

	function scissor( scissor ) {

		if ( currentScissor.equals( scissor ) === false ) {

			gl.scissor( scissor.x, scissor.y, scissor.z, scissor.w );
			currentScissor.copy( scissor );

		}

	}

	function viewport( viewport ) {

		if ( currentViewport.equals( viewport ) === false ) {

			gl.viewport( viewport.x, viewport.y, viewport.z, viewport.w );
			currentViewport.copy( viewport );

		}

	}

	function updateUBOMapping( uniformsGroup, program ) {

		let mapping = uboProgramMap.get( program );

		if ( mapping === undefined ) {

			mapping = new WeakMap();

			uboProgramMap.set( program, mapping );

		}

		let blockIndex = mapping.get( uniformsGroup );

		if ( blockIndex === undefined ) {

			blockIndex = gl.getUniformBlockIndex( program, uniformsGroup.name );

			mapping.set( uniformsGroup, blockIndex );

		}

	}

	function uniformBlockBinding( uniformsGroup, program ) {

		const mapping = uboProgramMap.get( program );
		const blockIndex = mapping.get( uniformsGroup );

		if ( uboBindings.get( program ) !== blockIndex ) {

			// bind shader specific block index to global block point
			gl.uniformBlockBinding( program, blockIndex, uniformsGroup.__bindingPointIndex );

			uboBindings.set( program, blockIndex );

		}

	}

	//

	function reset() {

		// reset state

		gl.disable( gl.BLEND );
		gl.disable( gl.CULL_FACE );
		gl.disable( gl.DEPTH_TEST );
		gl.disable( gl.POLYGON_OFFSET_FILL );
		gl.disable( gl.SCISSOR_TEST );
		gl.disable( gl.STENCIL_TEST );
		gl.disable( gl.SAMPLE_ALPHA_TO_COVERAGE );

		gl.blendEquation( gl.FUNC_ADD );
		gl.blendFunc( gl.ONE, gl.ZERO );
		gl.blendFuncSeparate( gl.ONE, gl.ZERO, gl.ONE, gl.ZERO );
		gl.blendColor( 0, 0, 0, 0 );

		gl.colorMask( true, true, true, true );
		gl.clearColor( 0, 0, 0, 0 );

		gl.depthMask( true );
		gl.depthFunc( gl.LESS );

		depthBuffer.setReversed( false );

		gl.clearDepth( 1 );

		gl.stencilMask( 0xffffffff );
		gl.stencilFunc( gl.ALWAYS, 0, 0xffffffff );
		gl.stencilOp( gl.KEEP, gl.KEEP, gl.KEEP );
		gl.clearStencil( 0 );

		gl.cullFace( gl.BACK );
		gl.frontFace( gl.CCW );

		gl.polygonOffset( 0, 0 );

		gl.activeTexture( gl.TEXTURE0 );

		gl.bindFramebuffer( gl.FRAMEBUFFER, null );
		gl.bindFramebuffer( gl.DRAW_FRAMEBUFFER, null );
		gl.bindFramebuffer( gl.READ_FRAMEBUFFER, null );

		gl.useProgram( null );

		gl.lineWidth( 1 );

		gl.scissor( 0, 0, gl.canvas.width, gl.canvas.height );
		gl.viewport( 0, 0, gl.canvas.width, gl.canvas.height );

		// reset internals

		enabledCapabilities = {};

		currentTextureSlot = null;
		currentBoundTextures = {};

		currentBoundFramebuffers = {};
		currentDrawbuffers = new WeakMap();
		defaultDrawbuffers = [];

		currentProgram = null;

		currentBlendingEnabled = false;
		currentBlending = null;
		currentBlendEquation = null;
		currentBlendSrc = null;
		currentBlendDst = null;
		currentBlendEquationAlpha = null;
		currentBlendSrcAlpha = null;
		currentBlendDstAlpha = null;
		currentBlendColor = new Color( 0, 0, 0 );
		currentBlendAlpha = 0;
		currentPremultipledAlpha = false;

		currentFlipSided = null;
		currentCullFace = null;

		currentLineWidth = null;

		currentPolygonOffsetFactor = null;
		currentPolygonOffsetUnits = null;

		currentScissor.set( 0, 0, gl.canvas.width, gl.canvas.height );
		currentViewport.set( 0, 0, gl.canvas.width, gl.canvas.height );

		colorBuffer.reset();
		depthBuffer.reset();
		stencilBuffer.reset();

	}

	return {

		buffers: {
			color: colorBuffer,
			depth: depthBuffer,
			stencil: stencilBuffer
		},

		enable: enable,
		disable: disable,

		bindFramebuffer: bindFramebuffer,
		drawBuffers: drawBuffers,

		useProgram: useProgram,

		setBlending: setBlending,
		setMaterial: setMaterial,

		setFlipSided: setFlipSided,
		setCullFace: setCullFace,

		setLineWidth: setLineWidth,
		setPolygonOffset: setPolygonOffset,

		setScissorTest: setScissorTest,

		activeTexture: activeTexture,
		bindTexture: bindTexture,
		unbindTexture: unbindTexture,
		compressedTexImage2D: compressedTexImage2D,
		compressedTexImage3D: compressedTexImage3D,
		texImage2D: texImage2D,
		texImage3D: texImage3D,

		updateUBOMapping: updateUBOMapping,
		uniformBlockBinding: uniformBlockBinding,

		texStorage2D: texStorage2D,
		texStorage3D: texStorage3D,
		texSubImage2D: texSubImage2D,
		texSubImage3D: texSubImage3D,
		compressedTexSubImage2D: compressedTexSubImage2D,
		compressedTexSubImage3D: compressedTexSubImage3D,

		scissor: scissor,
		viewport: viewport,

		reset: reset

	};

}
```
</details>

### `ColorBuffer(): { setMask: (colorMask: any) => void; setLocked: (lock: any) => void; setClear: (r: any, g: any, b: any, a: any, premultipliedAlpha: any) => void; reset: () => void; }`

**Returns:** `{ setMask: (colorMask: any) => void; setLocked: (lock: any) => void; setClear: (r: any, g: any, b: any, a: any, premultipliedAlpha: any) => void; reset: () => void; }`

**Calls:**

- `gl.colorMask`
- `color.set`
- `currentColorClear.equals`
- `gl.clearColor`
- `currentColorClear.copy`
- `currentColorClear.set`

<details><summary>Code</summary>

```typescript
function ColorBuffer() {

		let locked = false;

		const color = new Vector4();
		let currentColorMask = null;
		const currentColorClear = new Vector4( 0, 0, 0, 0 );

		return {

			setMask: function ( colorMask ) {

				if ( currentColorMask !== colorMask && ! locked ) {

					gl.colorMask( colorMask, colorMask, colorMask, colorMask );
					currentColorMask = colorMask;

				}

			},

			setLocked: function ( lock ) {

				locked = lock;

			},

			setClear: function ( r, g, b, a, premultipliedAlpha ) {

				if ( premultipliedAlpha === true ) {

					r *= a; g *= a; b *= a;

				}

				color.set( r, g, b, a );

				if ( currentColorClear.equals( color ) === false ) {

					gl.clearColor( r, g, b, a );
					currentColorClear.copy( color );

				}

			},

			reset: function () {

				locked = false;

				currentColorMask = null;
				currentColorClear.set( - 1, 0, 0, 0 ); // set to invalid state

			}

		};

	}
```
</details>

### `setMask(colorMask: any): void`

**Parameters:**

- **`colorMask`** `any`

**Returns:** `void`

**Calls:**

- `gl.colorMask`

<details><summary>Code</summary>

```typescript
function ( colorMask ) {

				if ( currentColorMask !== colorMask && ! locked ) {

					gl.colorMask( colorMask, colorMask, colorMask, colorMask );
					currentColorMask = colorMask;

				}

			}
```
</details>

### `setLocked(lock: any): void`

**Parameters:**

- **`lock`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( lock ) {

				locked = lock;

			}
```
</details>

### `setClear(r: any, g: any, b: any, a: any, premultipliedAlpha: any): void`

**Parameters:**

- **`r`** `any`
- **`g`** `any`
- **`b`** `any`
- **`a`** `any`
- **`premultipliedAlpha`** `any`

**Returns:** `void`

**Calls:**

- `color.set`
- `currentColorClear.equals`
- `gl.clearColor`
- `currentColorClear.copy`

<details><summary>Code</summary>

```typescript
function ( r, g, b, a, premultipliedAlpha ) {

				if ( premultipliedAlpha === true ) {

					r *= a; g *= a; b *= a;

				}

				color.set( r, g, b, a );

				if ( currentColorClear.equals( color ) === false ) {

					gl.clearColor( r, g, b, a );
					currentColorClear.copy( color );

				}

			}
```
</details>

### `reset(): void`

**Returns:** `void`

**Calls:**

- `currentColorClear.set`

<details><summary>Code</summary>

```typescript
function () {

				locked = false;

				currentColorMask = null;
				currentColorClear.set( - 1, 0, 0, 0 ); // set to invalid state

			}
```
</details>

### `setMask(colorMask: any): void`

**Parameters:**

- **`colorMask`** `any`

**Returns:** `void`

**Calls:**

- `gl.colorMask`

<details><summary>Code</summary>

```typescript
function ( colorMask ) {

				if ( currentColorMask !== colorMask && ! locked ) {

					gl.colorMask( colorMask, colorMask, colorMask, colorMask );
					currentColorMask = colorMask;

				}

			}
```
</details>

### `setLocked(lock: any): void`

**Parameters:**

- **`lock`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( lock ) {

				locked = lock;

			}
```
</details>

### `setClear(r: any, g: any, b: any, a: any, premultipliedAlpha: any): void`

**Parameters:**

- **`r`** `any`
- **`g`** `any`
- **`b`** `any`
- **`a`** `any`
- **`premultipliedAlpha`** `any`

**Returns:** `void`

**Calls:**

- `color.set`
- `currentColorClear.equals`
- `gl.clearColor`
- `currentColorClear.copy`

<details><summary>Code</summary>

```typescript
function ( r, g, b, a, premultipliedAlpha ) {

				if ( premultipliedAlpha === true ) {

					r *= a; g *= a; b *= a;

				}

				color.set( r, g, b, a );

				if ( currentColorClear.equals( color ) === false ) {

					gl.clearColor( r, g, b, a );
					currentColorClear.copy( color );

				}

			}
```
</details>

### `reset(): void`

**Returns:** `void`

**Calls:**

- `currentColorClear.set`

<details><summary>Code</summary>

```typescript
function () {

				locked = false;

				currentColorMask = null;
				currentColorClear.set( - 1, 0, 0, 0 ); // set to invalid state

			}
```
</details>

### `DepthBuffer(): { setReversed: (reversed: any) => void; getReversed: () => boolean; setTest: (depthTest: any) => void; setMask: (depthMask: any) => void; setFunc: (depthFunc: any) => void; setLocked: (lock: any) => void; setClear: (depth: any) => void; reset: () => void; }`

**Returns:** `{ setReversed: (reversed: any) => void; getReversed: () => boolean; setTest: (depthTest: any) => void; setMask: (depthMask: any) => void; setFunc: (depthFunc: any) => void; setLocked: (lock: any) => void; setClear: (depth: any) => void; reset: () => void; }`

**Calls:**

- `extensions.get`
- `ext.clipControlEXT`
- `this.setClear`
- `enable`
- `disable`
- `gl.depthMask`
- `gl.depthFunc`
- `gl.clearDepth`

<details><summary>Code</summary>

```typescript
function DepthBuffer() {

		let locked = false;

		let currentReversed = false;
		let currentDepthMask = null;
		let currentDepthFunc = null;
		let currentDepthClear = null;

		return {

			setReversed: function ( reversed ) {

				if ( currentReversed !== reversed ) {

					const ext = extensions.get( 'EXT_clip_control' );

					if ( reversed ) {

						ext.clipControlEXT( ext.LOWER_LEFT_EXT, ext.ZERO_TO_ONE_EXT );

					} else {

						ext.clipControlEXT( ext.LOWER_LEFT_EXT, ext.NEGATIVE_ONE_TO_ONE_EXT );

					}

					currentReversed = reversed;

					const oldDepth = currentDepthClear;
					currentDepthClear = null;
					this.setClear( oldDepth );

				}

			},

			getReversed: function () {

				return currentReversed;

			},

			setTest: function ( depthTest ) {

				if ( depthTest ) {

					enable( gl.DEPTH_TEST );

				} else {

					disable( gl.DEPTH_TEST );

				}

			},

			setMask: function ( depthMask ) {

				if ( currentDepthMask !== depthMask && ! locked ) {

					gl.depthMask( depthMask );
					currentDepthMask = depthMask;

				}

			},

			setFunc: function ( depthFunc ) {

				if ( currentReversed ) depthFunc = reversedFuncs[ depthFunc ];

				if ( currentDepthFunc !== depthFunc ) {

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

					currentDepthFunc = depthFunc;

				}

			},

			setLocked: function ( lock ) {

				locked = lock;

			},

			setClear: function ( depth ) {

				if ( currentDepthClear !== depth ) {

					if ( currentReversed ) {

						depth = 1 - depth;

					}

					gl.clearDepth( depth );
					currentDepthClear = depth;

				}

			},

			reset: function () {

				locked = false;

				currentDepthMask = null;
				currentDepthFunc = null;
				currentDepthClear = null;
				currentReversed = false;

			}

		};

	}
```
</details>

### `setReversed(reversed: any): void`

**Parameters:**

- **`reversed`** `any`

**Returns:** `void`

**Calls:**

- `extensions.get`
- `ext.clipControlEXT`
- `this.setClear`

<details><summary>Code</summary>

```typescript
function ( reversed ) {

				if ( currentReversed !== reversed ) {

					const ext = extensions.get( 'EXT_clip_control' );

					if ( reversed ) {

						ext.clipControlEXT( ext.LOWER_LEFT_EXT, ext.ZERO_TO_ONE_EXT );

					} else {

						ext.clipControlEXT( ext.LOWER_LEFT_EXT, ext.NEGATIVE_ONE_TO_ONE_EXT );

					}

					currentReversed = reversed;

					const oldDepth = currentDepthClear;
					currentDepthClear = null;
					this.setClear( oldDepth );

				}

			}
```
</details>

### `getReversed(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function () {

				return currentReversed;

			}
```
</details>

### `setTest(depthTest: any): void`

**Parameters:**

- **`depthTest`** `any`

**Returns:** `void`

**Calls:**

- `enable`
- `disable`

<details><summary>Code</summary>

```typescript
function ( depthTest ) {

				if ( depthTest ) {

					enable( gl.DEPTH_TEST );

				} else {

					disable( gl.DEPTH_TEST );

				}

			}
```
</details>

### `setMask(depthMask: any): void`

**Parameters:**

- **`depthMask`** `any`

**Returns:** `void`

**Calls:**

- `gl.depthMask`

<details><summary>Code</summary>

```typescript
function ( depthMask ) {

				if ( currentDepthMask !== depthMask && ! locked ) {

					gl.depthMask( depthMask );
					currentDepthMask = depthMask;

				}

			}
```
</details>

### `setFunc(depthFunc: any): void`

**Parameters:**

- **`depthFunc`** `any`

**Returns:** `void`

**Calls:**

- `gl.depthFunc`

<details><summary>Code</summary>

```typescript
function ( depthFunc ) {

				if ( currentReversed ) depthFunc = reversedFuncs[ depthFunc ];

				if ( currentDepthFunc !== depthFunc ) {

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

					currentDepthFunc = depthFunc;

				}

			}
```
</details>

### `setLocked(lock: any): void`

**Parameters:**

- **`lock`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( lock ) {

				locked = lock;

			}
```
</details>

### `setClear(depth: any): void`

**Parameters:**

- **`depth`** `any`

**Returns:** `void`

**Calls:**

- `gl.clearDepth`

<details><summary>Code</summary>

```typescript
function ( depth ) {

				if ( currentDepthClear !== depth ) {

					if ( currentReversed ) {

						depth = 1 - depth;

					}

					gl.clearDepth( depth );
					currentDepthClear = depth;

				}

			}
```
</details>

### `reset(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

				locked = false;

				currentDepthMask = null;
				currentDepthFunc = null;
				currentDepthClear = null;
				currentReversed = false;

			}
```
</details>

### `setReversed(reversed: any): void`

**Parameters:**

- **`reversed`** `any`

**Returns:** `void`

**Calls:**

- `extensions.get`
- `ext.clipControlEXT`
- `this.setClear`

<details><summary>Code</summary>

```typescript
function ( reversed ) {

				if ( currentReversed !== reversed ) {

					const ext = extensions.get( 'EXT_clip_control' );

					if ( reversed ) {

						ext.clipControlEXT( ext.LOWER_LEFT_EXT, ext.ZERO_TO_ONE_EXT );

					} else {

						ext.clipControlEXT( ext.LOWER_LEFT_EXT, ext.NEGATIVE_ONE_TO_ONE_EXT );

					}

					currentReversed = reversed;

					const oldDepth = currentDepthClear;
					currentDepthClear = null;
					this.setClear( oldDepth );

				}

			}
```
</details>

### `getReversed(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function () {

				return currentReversed;

			}
```
</details>

### `setTest(depthTest: any): void`

**Parameters:**

- **`depthTest`** `any`

**Returns:** `void`

**Calls:**

- `enable`
- `disable`

<details><summary>Code</summary>

```typescript
function ( depthTest ) {

				if ( depthTest ) {

					enable( gl.DEPTH_TEST );

				} else {

					disable( gl.DEPTH_TEST );

				}

			}
```
</details>

### `setMask(depthMask: any): void`

**Parameters:**

- **`depthMask`** `any`

**Returns:** `void`

**Calls:**

- `gl.depthMask`

<details><summary>Code</summary>

```typescript
function ( depthMask ) {

				if ( currentDepthMask !== depthMask && ! locked ) {

					gl.depthMask( depthMask );
					currentDepthMask = depthMask;

				}

			}
```
</details>

### `setFunc(depthFunc: any): void`

**Parameters:**

- **`depthFunc`** `any`

**Returns:** `void`

**Calls:**

- `gl.depthFunc`

<details><summary>Code</summary>

```typescript
function ( depthFunc ) {

				if ( currentReversed ) depthFunc = reversedFuncs[ depthFunc ];

				if ( currentDepthFunc !== depthFunc ) {

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

					currentDepthFunc = depthFunc;

				}

			}
```
</details>

### `setLocked(lock: any): void`

**Parameters:**

- **`lock`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( lock ) {

				locked = lock;

			}
```
</details>

### `setClear(depth: any): void`

**Parameters:**

- **`depth`** `any`

**Returns:** `void`

**Calls:**

- `gl.clearDepth`

<details><summary>Code</summary>

```typescript
function ( depth ) {

				if ( currentDepthClear !== depth ) {

					if ( currentReversed ) {

						depth = 1 - depth;

					}

					gl.clearDepth( depth );
					currentDepthClear = depth;

				}

			}
```
</details>

### `reset(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

				locked = false;

				currentDepthMask = null;
				currentDepthFunc = null;
				currentDepthClear = null;
				currentReversed = false;

			}
```
</details>

### `StencilBuffer(): { setTest: (stencilTest: any) => void; setMask: (stencilMask: any) => void; setFunc: (stencilFunc: any, stencilRef: any, stencilMask: any) => void; setOp: (stencilFail: any, stencilZFail: any, stencilZPass: any) => void; setLocked: (lock: any) => void; setClear: (stencil: any) => void; reset: () => void; }`

**Returns:** `{ setTest: (stencilTest: any) => void; setMask: (stencilMask: any) => void; setFunc: (stencilFunc: any, stencilRef: any, stencilMask: any) => void; setOp: (stencilFail: any, stencilZFail: any, stencilZPass: any) => void; setLocked: (lock: any) => void; setClear: (stencil: any) => void; reset: () => void; }`

**Calls:**

- `enable`
- `disable`
- `gl.stencilMask`
- `gl.stencilFunc`
- `gl.stencilOp`
- `gl.clearStencil`

<details><summary>Code</summary>

```typescript
function StencilBuffer() {

		let locked = false;

		let currentStencilMask = null;
		let currentStencilFunc = null;
		let currentStencilRef = null;
		let currentStencilFuncMask = null;
		let currentStencilFail = null;
		let currentStencilZFail = null;
		let currentStencilZPass = null;
		let currentStencilClear = null;

		return {

			setTest: function ( stencilTest ) {

				if ( ! locked ) {

					if ( stencilTest ) {

						enable( gl.STENCIL_TEST );

					} else {

						disable( gl.STENCIL_TEST );

					}

				}

			},

			setMask: function ( stencilMask ) {

				if ( currentStencilMask !== stencilMask && ! locked ) {

					gl.stencilMask( stencilMask );
					currentStencilMask = stencilMask;

				}

			},

			setFunc: function ( stencilFunc, stencilRef, stencilMask ) {

				if ( currentStencilFunc !== stencilFunc ||
				     currentStencilRef !== stencilRef ||
				     currentStencilFuncMask !== stencilMask ) {

					gl.stencilFunc( stencilFunc, stencilRef, stencilMask );

					currentStencilFunc = stencilFunc;
					currentStencilRef = stencilRef;
					currentStencilFuncMask = stencilMask;

				}

			},

			setOp: function ( stencilFail, stencilZFail, stencilZPass ) {

				if ( currentStencilFail !== stencilFail ||
				     currentStencilZFail !== stencilZFail ||
				     currentStencilZPass !== stencilZPass ) {

					gl.stencilOp( stencilFail, stencilZFail, stencilZPass );

					currentStencilFail = stencilFail;
					currentStencilZFail = stencilZFail;
					currentStencilZPass = stencilZPass;

				}

			},

			setLocked: function ( lock ) {

				locked = lock;

			},

			setClear: function ( stencil ) {

				if ( currentStencilClear !== stencil ) {

					gl.clearStencil( stencil );
					currentStencilClear = stencil;

				}

			},

			reset: function () {

				locked = false;

				currentStencilMask = null;
				currentStencilFunc = null;
				currentStencilRef = null;
				currentStencilFuncMask = null;
				currentStencilFail = null;
				currentStencilZFail = null;
				currentStencilZPass = null;
				currentStencilClear = null;

			}

		};

	}
```
</details>

### `setTest(stencilTest: any): void`

**Parameters:**

- **`stencilTest`** `any`

**Returns:** `void`

**Calls:**

- `enable`
- `disable`

<details><summary>Code</summary>

```typescript
function ( stencilTest ) {

				if ( ! locked ) {

					if ( stencilTest ) {

						enable( gl.STENCIL_TEST );

					} else {

						disable( gl.STENCIL_TEST );

					}

				}

			}
```
</details>

### `setMask(stencilMask: any): void`

**Parameters:**

- **`stencilMask`** `any`

**Returns:** `void`

**Calls:**

- `gl.stencilMask`

<details><summary>Code</summary>

```typescript
function ( stencilMask ) {

				if ( currentStencilMask !== stencilMask && ! locked ) {

					gl.stencilMask( stencilMask );
					currentStencilMask = stencilMask;

				}

			}
```
</details>

### `setFunc(stencilFunc: any, stencilRef: any, stencilMask: any): void`

**Parameters:**

- **`stencilFunc`** `any`
- **`stencilRef`** `any`
- **`stencilMask`** `any`

**Returns:** `void`

**Calls:**

- `gl.stencilFunc`

<details><summary>Code</summary>

```typescript
function ( stencilFunc, stencilRef, stencilMask ) {

				if ( currentStencilFunc !== stencilFunc ||
				     currentStencilRef !== stencilRef ||
				     currentStencilFuncMask !== stencilMask ) {

					gl.stencilFunc( stencilFunc, stencilRef, stencilMask );

					currentStencilFunc = stencilFunc;
					currentStencilRef = stencilRef;
					currentStencilFuncMask = stencilMask;

				}

			}
```
</details>

### `setOp(stencilFail: any, stencilZFail: any, stencilZPass: any): void`

**Parameters:**

- **`stencilFail`** `any`
- **`stencilZFail`** `any`
- **`stencilZPass`** `any`

**Returns:** `void`

**Calls:**

- `gl.stencilOp`

<details><summary>Code</summary>

```typescript
function ( stencilFail, stencilZFail, stencilZPass ) {

				if ( currentStencilFail !== stencilFail ||
				     currentStencilZFail !== stencilZFail ||
				     currentStencilZPass !== stencilZPass ) {

					gl.stencilOp( stencilFail, stencilZFail, stencilZPass );

					currentStencilFail = stencilFail;
					currentStencilZFail = stencilZFail;
					currentStencilZPass = stencilZPass;

				}

			}
```
</details>

### `setLocked(lock: any): void`

**Parameters:**

- **`lock`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( lock ) {

				locked = lock;

			}
```
</details>

### `setClear(stencil: any): void`

**Parameters:**

- **`stencil`** `any`

**Returns:** `void`

**Calls:**

- `gl.clearStencil`

<details><summary>Code</summary>

```typescript
function ( stencil ) {

				if ( currentStencilClear !== stencil ) {

					gl.clearStencil( stencil );
					currentStencilClear = stencil;

				}

			}
```
</details>

### `reset(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

				locked = false;

				currentStencilMask = null;
				currentStencilFunc = null;
				currentStencilRef = null;
				currentStencilFuncMask = null;
				currentStencilFail = null;
				currentStencilZFail = null;
				currentStencilZPass = null;
				currentStencilClear = null;

			}
```
</details>

### `setTest(stencilTest: any): void`

**Parameters:**

- **`stencilTest`** `any`

**Returns:** `void`

**Calls:**

- `enable`
- `disable`

<details><summary>Code</summary>

```typescript
function ( stencilTest ) {

				if ( ! locked ) {

					if ( stencilTest ) {

						enable( gl.STENCIL_TEST );

					} else {

						disable( gl.STENCIL_TEST );

					}

				}

			}
```
</details>

### `setMask(stencilMask: any): void`

**Parameters:**

- **`stencilMask`** `any`

**Returns:** `void`

**Calls:**

- `gl.stencilMask`

<details><summary>Code</summary>

```typescript
function ( stencilMask ) {

				if ( currentStencilMask !== stencilMask && ! locked ) {

					gl.stencilMask( stencilMask );
					currentStencilMask = stencilMask;

				}

			}
```
</details>

### `setFunc(stencilFunc: any, stencilRef: any, stencilMask: any): void`

**Parameters:**

- **`stencilFunc`** `any`
- **`stencilRef`** `any`
- **`stencilMask`** `any`

**Returns:** `void`

**Calls:**

- `gl.stencilFunc`

<details><summary>Code</summary>

```typescript
function ( stencilFunc, stencilRef, stencilMask ) {

				if ( currentStencilFunc !== stencilFunc ||
				     currentStencilRef !== stencilRef ||
				     currentStencilFuncMask !== stencilMask ) {

					gl.stencilFunc( stencilFunc, stencilRef, stencilMask );

					currentStencilFunc = stencilFunc;
					currentStencilRef = stencilRef;
					currentStencilFuncMask = stencilMask;

				}

			}
```
</details>

### `setOp(stencilFail: any, stencilZFail: any, stencilZPass: any): void`

**Parameters:**

- **`stencilFail`** `any`
- **`stencilZFail`** `any`
- **`stencilZPass`** `any`

**Returns:** `void`

**Calls:**

- `gl.stencilOp`

<details><summary>Code</summary>

```typescript
function ( stencilFail, stencilZFail, stencilZPass ) {

				if ( currentStencilFail !== stencilFail ||
				     currentStencilZFail !== stencilZFail ||
				     currentStencilZPass !== stencilZPass ) {

					gl.stencilOp( stencilFail, stencilZFail, stencilZPass );

					currentStencilFail = stencilFail;
					currentStencilZFail = stencilZFail;
					currentStencilZPass = stencilZPass;

				}

			}
```
</details>

### `setLocked(lock: any): void`

**Parameters:**

- **`lock`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( lock ) {

				locked = lock;

			}
```
</details>

### `setClear(stencil: any): void`

**Parameters:**

- **`stencil`** `any`

**Returns:** `void`

**Calls:**

- `gl.clearStencil`

<details><summary>Code</summary>

```typescript
function ( stencil ) {

				if ( currentStencilClear !== stencil ) {

					gl.clearStencil( stencil );
					currentStencilClear = stencil;

				}

			}
```
</details>

### `reset(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

				locked = false;

				currentStencilMask = null;
				currentStencilFunc = null;
				currentStencilRef = null;
				currentStencilFuncMask = null;
				currentStencilFail = null;
				currentStencilZFail = null;
				currentStencilZPass = null;
				currentStencilClear = null;

			}
```
</details>

### `createTexture(type: any, target: any, count: any, dimensions: any): any`

**Parameters:**

- **`type`** `any`
- **`target`** `any`
- **`count`** `any`
- **`dimensions`** `any`

**Returns:** `any`

**Calls:**

- `gl.createTexture`
- `gl.bindTexture`
- `gl.texParameteri`
- `gl.texImage3D`
- `gl.texImage2D`

<details><summary>Code</summary>

```typescript
function createTexture( type, target, count, dimensions ) {

		const data = new Uint8Array( 4 ); // 4 is required to match default unpack alignment of 4.
		const texture = gl.createTexture();

		gl.bindTexture( type, texture );
		gl.texParameteri( type, gl.TEXTURE_MIN_FILTER, gl.NEAREST );
		gl.texParameteri( type, gl.TEXTURE_MAG_FILTER, gl.NEAREST );

		for ( let i = 0; i < count; i ++ ) {

			if ( type === gl.TEXTURE_3D || type === gl.TEXTURE_2D_ARRAY ) {

				gl.texImage3D( target, 0, gl.RGBA, 1, 1, dimensions, 0, gl.RGBA, gl.UNSIGNED_BYTE, data );

			} else {

				gl.texImage2D( target + i, 0, gl.RGBA, 1, 1, 0, gl.RGBA, gl.UNSIGNED_BYTE, data );

			}

		}

		return texture;

	}
```
</details>

### `enable(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

**Calls:**

- `gl.enable`

<details><summary>Code</summary>

```typescript
function enable( id ) {

		if ( enabledCapabilities[ id ] !== true ) {

			gl.enable( id );
			enabledCapabilities[ id ] = true;

		}

	}
```
</details>

### `disable(id: any): void`

**Parameters:**

- **`id`** `any`

**Returns:** `void`

**Calls:**

- `gl.disable`

<details><summary>Code</summary>

```typescript
function disable( id ) {

		if ( enabledCapabilities[ id ] !== false ) {

			gl.disable( id );
			enabledCapabilities[ id ] = false;

		}

	}
```
</details>

### `bindFramebuffer(target: any, framebuffer: any): boolean`

**Parameters:**

- **`target`** `any`
- **`framebuffer`** `any`

**Returns:** `boolean`

**Calls:**

- `gl.bindFramebuffer`

**Internal Comments:**
```
// gl.DRAW_FRAMEBUFFER is equivalent to gl.FRAMEBUFFER
```

<details><summary>Code</summary>

```typescript
function bindFramebuffer( target, framebuffer ) {

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

### `drawBuffers(renderTarget: any, framebuffer: any): void`

**Parameters:**

- **`renderTarget`** `any`
- **`framebuffer`** `any`

**Returns:** `void`

**Calls:**

- `currentDrawbuffers.get`
- `currentDrawbuffers.set`
- `gl.drawBuffers`

<details><summary>Code</summary>

```typescript
function drawBuffers( renderTarget, framebuffer ) {

		let drawBuffers = defaultDrawbuffers;

		let needsUpdate = false;

		if ( renderTarget ) {

			drawBuffers = currentDrawbuffers.get( framebuffer );

			if ( drawBuffers === undefined ) {

				drawBuffers = [];
				currentDrawbuffers.set( framebuffer, drawBuffers );

			}

			const textures = renderTarget.textures;

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

### `useProgram(program: any): boolean`

**Parameters:**

- **`program`** `any`

**Returns:** `boolean`

**Calls:**

- `gl.useProgram`

<details><summary>Code</summary>

```typescript
function useProgram( program ) {

		if ( currentProgram !== program ) {

			gl.useProgram( program );

			currentProgram = program;

			return true;

		}

		return false;

	}
```
</details>

### `setBlending(blending: any, blendEquation: any, blendSrc: any, blendDst: any, blendEquationAlpha: any, blendSrcAlpha: any, blendDstAlpha: any, blendColor: any, blendAlpha: any, premultipliedAlpha: any): void`

**Parameters:**

- **`blending`** `any`
- **`blendEquation`** `any`
- **`blendSrc`** `any`
- **`blendDst`** `any`
- **`blendEquationAlpha`** `any`
- **`blendSrcAlpha`** `any`
- **`blendDstAlpha`** `any`
- **`blendColor`** `any`
- **`blendAlpha`** `any`
- **`premultipliedAlpha`** `any`

**Returns:** `void`

**Calls:**

- `disable`
- `enable`
- `gl.blendEquation`
- `gl.blendFuncSeparate`
- `gl.blendFunc`
- `console.error`
- `currentBlendColor.set`
- `gl.blendEquationSeparate`
- `blendColor.equals`
- `gl.blendColor`
- `currentBlendColor.copy`

**Internal Comments:**
```
// custom blending (x3)
```

<details><summary>Code</summary>

```typescript
function setBlending( blending, blendEquation, blendSrc, blendDst, blendEquationAlpha, blendSrcAlpha, blendDstAlpha, blendColor, blendAlpha, premultipliedAlpha ) {

		if ( blending === NoBlending ) {

			if ( currentBlendingEnabled === true ) {

				disable( gl.BLEND );
				currentBlendingEnabled = false;

			}

			return;

		}

		if ( currentBlendingEnabled === false ) {

			enable( gl.BLEND );
			currentBlendingEnabled = true;

		}

		if ( blending !== CustomBlending ) {

			if ( blending !== currentBlending || premultipliedAlpha !== currentPremultipledAlpha ) {

				if ( currentBlendEquation !== AddEquation || currentBlendEquationAlpha !== AddEquation ) {

					gl.blendEquation( gl.FUNC_ADD );

					currentBlendEquation = AddEquation;
					currentBlendEquationAlpha = AddEquation;

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

				currentBlendSrc = null;
				currentBlendDst = null;
				currentBlendSrcAlpha = null;
				currentBlendDstAlpha = null;
				currentBlendColor.set( 0, 0, 0 );
				currentBlendAlpha = 0;

				currentBlending = blending;
				currentPremultipledAlpha = premultipliedAlpha;

			}

			return;

		}

		// custom blending

		blendEquationAlpha = blendEquationAlpha || blendEquation;
		blendSrcAlpha = blendSrcAlpha || blendSrc;
		blendDstAlpha = blendDstAlpha || blendDst;

		if ( blendEquation !== currentBlendEquation || blendEquationAlpha !== currentBlendEquationAlpha ) {

			gl.blendEquationSeparate( equationToGL[ blendEquation ], equationToGL[ blendEquationAlpha ] );

			currentBlendEquation = blendEquation;
			currentBlendEquationAlpha = blendEquationAlpha;

		}

		if ( blendSrc !== currentBlendSrc || blendDst !== currentBlendDst || blendSrcAlpha !== currentBlendSrcAlpha || blendDstAlpha !== currentBlendDstAlpha ) {

			gl.blendFuncSeparate( factorToGL[ blendSrc ], factorToGL[ blendDst ], factorToGL[ blendSrcAlpha ], factorToGL[ blendDstAlpha ] );

			currentBlendSrc = blendSrc;
			currentBlendDst = blendDst;
			currentBlendSrcAlpha = blendSrcAlpha;
			currentBlendDstAlpha = blendDstAlpha;

		}

		if ( blendColor.equals( currentBlendColor ) === false || blendAlpha !== currentBlendAlpha ) {

			gl.blendColor( blendColor.r, blendColor.g, blendColor.b, blendAlpha );

			currentBlendColor.copy( blendColor );
			currentBlendAlpha = blendAlpha;

		}

		currentBlending = blending;
		currentPremultipledAlpha = false;

	}
```
</details>

### `setMaterial(material: any, frontFaceCW: any): void`

**Parameters:**

- **`material`** `any`
- **`frontFaceCW`** `any`

**Returns:** `void`

**Calls:**

- `disable`
- `enable`
- `setFlipSided`
- `setBlending`
- `depthBuffer.setFunc`
- `depthBuffer.setTest`
- `depthBuffer.setMask`
- `colorBuffer.setMask`
- `stencilBuffer.setTest`
- `stencilBuffer.setMask`
- `stencilBuffer.setFunc`
- `stencilBuffer.setOp`
- `setPolygonOffset`

<details><summary>Code</summary>

```typescript
function setMaterial( material, frontFaceCW ) {

		material.side === DoubleSide
			? disable( gl.CULL_FACE )
			: enable( gl.CULL_FACE );

		let flipSided = ( material.side === BackSide );
		if ( frontFaceCW ) flipSided = ! flipSided;

		setFlipSided( flipSided );

		( material.blending === NormalBlending && material.transparent === false )
			? setBlending( NoBlending )
			: setBlending( material.blending, material.blendEquation, material.blendSrc, material.blendDst, material.blendEquationAlpha, material.blendSrcAlpha, material.blendDstAlpha, material.blendColor, material.blendAlpha, material.premultipliedAlpha );

		depthBuffer.setFunc( material.depthFunc );
		depthBuffer.setTest( material.depthTest );
		depthBuffer.setMask( material.depthWrite );
		colorBuffer.setMask( material.colorWrite );

		const stencilWrite = material.stencilWrite;
		stencilBuffer.setTest( stencilWrite );
		if ( stencilWrite ) {

			stencilBuffer.setMask( material.stencilWriteMask );
			stencilBuffer.setFunc( material.stencilFunc, material.stencilRef, material.stencilFuncMask );
			stencilBuffer.setOp( material.stencilFail, material.stencilZFail, material.stencilZPass );

		}

		setPolygonOffset( material.polygonOffset, material.polygonOffsetFactor, material.polygonOffsetUnits );

		material.alphaToCoverage === true
			? enable( gl.SAMPLE_ALPHA_TO_COVERAGE )
			: disable( gl.SAMPLE_ALPHA_TO_COVERAGE );

	}
```
</details>

### `setFlipSided(flipSided: any): void`

**Parameters:**

- **`flipSided`** `any`

**Returns:** `void`

**Calls:**

- `gl.frontFace`

<details><summary>Code</summary>

```typescript
function setFlipSided( flipSided ) {

		if ( currentFlipSided !== flipSided ) {

			if ( flipSided ) {

				gl.frontFace( gl.CW );

			} else {

				gl.frontFace( gl.CCW );

			}

			currentFlipSided = flipSided;

		}

	}
```
</details>

### `setCullFace(cullFace: any): void`

**Parameters:**

- **`cullFace`** `any`

**Returns:** `void`

**Calls:**

- `enable`
- `gl.cullFace`
- `disable`

<details><summary>Code</summary>

```typescript
function setCullFace( cullFace ) {

		if ( cullFace !== CullFaceNone ) {

			enable( gl.CULL_FACE );

			if ( cullFace !== currentCullFace ) {

				if ( cullFace === CullFaceBack ) {

					gl.cullFace( gl.BACK );

				} else if ( cullFace === CullFaceFront ) {

					gl.cullFace( gl.FRONT );

				} else {

					gl.cullFace( gl.FRONT_AND_BACK );

				}

			}

		} else {

			disable( gl.CULL_FACE );

		}

		currentCullFace = cullFace;

	}
```
</details>

### `setLineWidth(width: any): void`

**Parameters:**

- **`width`** `any`

**Returns:** `void`

**Calls:**

- `gl.lineWidth`

<details><summary>Code</summary>

```typescript
function setLineWidth( width ) {

		if ( width !== currentLineWidth ) {

			if ( lineWidthAvailable ) gl.lineWidth( width );

			currentLineWidth = width;

		}

	}
```
</details>

### `setPolygonOffset(polygonOffset: any, factor: any, units: any): void`

**Parameters:**

- **`polygonOffset`** `any`
- **`factor`** `any`
- **`units`** `any`

**Returns:** `void`

**Calls:**

- `enable`
- `gl.polygonOffset`
- `disable`

<details><summary>Code</summary>

```typescript
function setPolygonOffset( polygonOffset, factor, units ) {

		if ( polygonOffset ) {

			enable( gl.POLYGON_OFFSET_FILL );

			if ( currentPolygonOffsetFactor !== factor || currentPolygonOffsetUnits !== units ) {

				gl.polygonOffset( factor, units );

				currentPolygonOffsetFactor = factor;
				currentPolygonOffsetUnits = units;

			}

		} else {

			disable( gl.POLYGON_OFFSET_FILL );

		}

	}
```
</details>

### `setScissorTest(scissorTest: any): void`

**Parameters:**

- **`scissorTest`** `any`

**Returns:** `void`

**Calls:**

- `enable`
- `disable`

<details><summary>Code</summary>

```typescript
function setScissorTest( scissorTest ) {

		if ( scissorTest ) {

			enable( gl.SCISSOR_TEST );

		} else {

			disable( gl.SCISSOR_TEST );

		}

	}
```
</details>

### `activeTexture(webglSlot: any): void`

**Parameters:**

- **`webglSlot`** `any`

**Returns:** `void`

**Calls:**

- `gl.activeTexture`

<details><summary>Code</summary>

```typescript
function activeTexture( webglSlot ) {

		if ( webglSlot === undefined ) webglSlot = gl.TEXTURE0 + maxTextures - 1;

		if ( currentTextureSlot !== webglSlot ) {

			gl.activeTexture( webglSlot );
			currentTextureSlot = webglSlot;

		}

	}
```
</details>

### `bindTexture(webglType: any, webglTexture: any, webglSlot: any): void`

**Parameters:**

- **`webglType`** `any`
- **`webglTexture`** `any`
- **`webglSlot`** `any`

**Returns:** `void`

**Calls:**

- `gl.activeTexture`
- `gl.bindTexture`

<details><summary>Code</summary>

```typescript
function bindTexture( webglType, webglTexture, webglSlot ) {

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
				currentTextureSlot = webglSlot;

			}

			gl.bindTexture( webglType, webglTexture || emptyTextures[ webglType ] );

			boundTexture.type = webglType;
			boundTexture.texture = webglTexture;

		}

	}
```
</details>

### `unbindTexture(): void`

**Returns:** `void`

**Calls:**

- `gl.bindTexture`

<details><summary>Code</summary>

```typescript
function unbindTexture() {

		const boundTexture = currentBoundTextures[ currentTextureSlot ];

		if ( boundTexture !== undefined && boundTexture.type !== undefined ) {

			gl.bindTexture( boundTexture.type, null );

			boundTexture.type = undefined;
			boundTexture.texture = undefined;

		}

	}
```
</details>

### `compressedTexImage2D(): void`

**Returns:** `void`

**Calls:**

- `gl.compressedTexImage2D`
- `console.error`

<details><summary>Code</summary>

```typescript
function compressedTexImage2D() {

		try {

			gl.compressedTexImage2D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}
```
</details>

### `compressedTexImage3D(): void`

**Returns:** `void`

**Calls:**

- `gl.compressedTexImage3D`
- `console.error`

<details><summary>Code</summary>

```typescript
function compressedTexImage3D() {

		try {

			gl.compressedTexImage3D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}
```
</details>

### `texSubImage2D(): void`

**Returns:** `void`

**Calls:**

- `gl.texSubImage2D`
- `console.error`

<details><summary>Code</summary>

```typescript
function texSubImage2D() {

		try {

			gl.texSubImage2D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}
```
</details>

### `texSubImage3D(): void`

**Returns:** `void`

**Calls:**

- `gl.texSubImage3D`
- `console.error`

<details><summary>Code</summary>

```typescript
function texSubImage3D() {

		try {

			gl.texSubImage3D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}
```
</details>

### `compressedTexSubImage2D(): void`

**Returns:** `void`

**Calls:**

- `gl.compressedTexSubImage2D`
- `console.error`

<details><summary>Code</summary>

```typescript
function compressedTexSubImage2D() {

		try {

			gl.compressedTexSubImage2D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}
```
</details>

### `compressedTexSubImage3D(): void`

**Returns:** `void`

**Calls:**

- `gl.compressedTexSubImage3D`
- `console.error`

<details><summary>Code</summary>

```typescript
function compressedTexSubImage3D() {

		try {

			gl.compressedTexSubImage3D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}
```
</details>

### `texStorage2D(): void`

**Returns:** `void`

**Calls:**

- `gl.texStorage2D`
- `console.error`

<details><summary>Code</summary>

```typescript
function texStorage2D() {

		try {

			gl.texStorage2D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}
```
</details>

### `texStorage3D(): void`

**Returns:** `void`

**Calls:**

- `gl.texStorage3D`
- `console.error`

<details><summary>Code</summary>

```typescript
function texStorage3D() {

		try {

			gl.texStorage3D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}
```
</details>

### `texImage2D(): void`

**Returns:** `void`

**Calls:**

- `gl.texImage2D`
- `console.error`

<details><summary>Code</summary>

```typescript
function texImage2D() {

		try {

			gl.texImage2D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}
```
</details>

### `texImage3D(): void`

**Returns:** `void`

**Calls:**

- `gl.texImage3D`
- `console.error`

<details><summary>Code</summary>

```typescript
function texImage3D() {

		try {

			gl.texImage3D( ...arguments );

		} catch ( error ) {

			console.error( 'THREE.WebGLState:', error );

		}

	}
```
</details>

### `scissor(scissor: any): void`

**Parameters:**

- **`scissor`** `any`

**Returns:** `void`

**Calls:**

- `currentScissor.equals`
- `gl.scissor`
- `currentScissor.copy`

<details><summary>Code</summary>

```typescript
function scissor( scissor ) {

		if ( currentScissor.equals( scissor ) === false ) {

			gl.scissor( scissor.x, scissor.y, scissor.z, scissor.w );
			currentScissor.copy( scissor );

		}

	}
```
</details>

### `viewport(viewport: any): void`

**Parameters:**

- **`viewport`** `any`

**Returns:** `void`

**Calls:**

- `currentViewport.equals`
- `gl.viewport`
- `currentViewport.copy`

<details><summary>Code</summary>

```typescript
function viewport( viewport ) {

		if ( currentViewport.equals( viewport ) === false ) {

			gl.viewport( viewport.x, viewport.y, viewport.z, viewport.w );
			currentViewport.copy( viewport );

		}

	}
```
</details>

### `updateUBOMapping(uniformsGroup: any, program: any): void`

**Parameters:**

- **`uniformsGroup`** `any`
- **`program`** `any`

**Returns:** `void`

**Calls:**

- `uboProgramMap.get`
- `uboProgramMap.set`
- `mapping.get`
- `gl.getUniformBlockIndex`
- `mapping.set`

<details><summary>Code</summary>

```typescript
function updateUBOMapping( uniformsGroup, program ) {

		let mapping = uboProgramMap.get( program );

		if ( mapping === undefined ) {

			mapping = new WeakMap();

			uboProgramMap.set( program, mapping );

		}

		let blockIndex = mapping.get( uniformsGroup );

		if ( blockIndex === undefined ) {

			blockIndex = gl.getUniformBlockIndex( program, uniformsGroup.name );

			mapping.set( uniformsGroup, blockIndex );

		}

	}
```
</details>

### `uniformBlockBinding(uniformsGroup: any, program: any): void`

**Parameters:**

- **`uniformsGroup`** `any`
- **`program`** `any`

**Returns:** `void`

**Calls:**

- `uboProgramMap.get`
- `mapping.get`
- `uboBindings.get`
- `gl.uniformBlockBinding`
- `uboBindings.set`

**Internal Comments:**
```
// bind shader specific block index to global block point (x4)
```

<details><summary>Code</summary>

```typescript
function uniformBlockBinding( uniformsGroup, program ) {

		const mapping = uboProgramMap.get( program );
		const blockIndex = mapping.get( uniformsGroup );

		if ( uboBindings.get( program ) !== blockIndex ) {

			// bind shader specific block index to global block point
			gl.uniformBlockBinding( program, blockIndex, uniformsGroup.__bindingPointIndex );

			uboBindings.set( program, blockIndex );

		}

	}
```
</details>

### `reset(): void`

**Returns:** `void`

**Calls:**

- `gl.disable`
- `gl.blendEquation`
- `gl.blendFunc`
- `gl.blendFuncSeparate`
- `gl.blendColor`
- `gl.colorMask`
- `gl.clearColor`
- `gl.depthMask`
- `gl.depthFunc`
- `depthBuffer.setReversed`
- `gl.clearDepth`
- `gl.stencilMask`
- `gl.stencilFunc`
- `gl.stencilOp`
- `gl.clearStencil`
- `gl.cullFace`
- `gl.frontFace`
- `gl.polygonOffset`
- `gl.activeTexture`
- `gl.bindFramebuffer`
- `gl.useProgram`
- `gl.lineWidth`
- `gl.scissor`
- `gl.viewport`
- `currentScissor.set`
- `currentViewport.set`
- `colorBuffer.reset`
- `depthBuffer.reset`
- `stencilBuffer.reset`

**Internal Comments:**
```
// reset state (x4)
// reset internals (x3)
```

<details><summary>Code</summary>

```typescript
function reset() {

		// reset state

		gl.disable( gl.BLEND );
		gl.disable( gl.CULL_FACE );
		gl.disable( gl.DEPTH_TEST );
		gl.disable( gl.POLYGON_OFFSET_FILL );
		gl.disable( gl.SCISSOR_TEST );
		gl.disable( gl.STENCIL_TEST );
		gl.disable( gl.SAMPLE_ALPHA_TO_COVERAGE );

		gl.blendEquation( gl.FUNC_ADD );
		gl.blendFunc( gl.ONE, gl.ZERO );
		gl.blendFuncSeparate( gl.ONE, gl.ZERO, gl.ONE, gl.ZERO );
		gl.blendColor( 0, 0, 0, 0 );

		gl.colorMask( true, true, true, true );
		gl.clearColor( 0, 0, 0, 0 );

		gl.depthMask( true );
		gl.depthFunc( gl.LESS );

		depthBuffer.setReversed( false );

		gl.clearDepth( 1 );

		gl.stencilMask( 0xffffffff );
		gl.stencilFunc( gl.ALWAYS, 0, 0xffffffff );
		gl.stencilOp( gl.KEEP, gl.KEEP, gl.KEEP );
		gl.clearStencil( 0 );

		gl.cullFace( gl.BACK );
		gl.frontFace( gl.CCW );

		gl.polygonOffset( 0, 0 );

		gl.activeTexture( gl.TEXTURE0 );

		gl.bindFramebuffer( gl.FRAMEBUFFER, null );
		gl.bindFramebuffer( gl.DRAW_FRAMEBUFFER, null );
		gl.bindFramebuffer( gl.READ_FRAMEBUFFER, null );

		gl.useProgram( null );

		gl.lineWidth( 1 );

		gl.scissor( 0, 0, gl.canvas.width, gl.canvas.height );
		gl.viewport( 0, 0, gl.canvas.width, gl.canvas.height );

		// reset internals

		enabledCapabilities = {};

		currentTextureSlot = null;
		currentBoundTextures = {};

		currentBoundFramebuffers = {};
		currentDrawbuffers = new WeakMap();
		defaultDrawbuffers = [];

		currentProgram = null;

		currentBlendingEnabled = false;
		currentBlending = null;
		currentBlendEquation = null;
		currentBlendSrc = null;
		currentBlendDst = null;
		currentBlendEquationAlpha = null;
		currentBlendSrcAlpha = null;
		currentBlendDstAlpha = null;
		currentBlendColor = new Color( 0, 0, 0 );
		currentBlendAlpha = 0;
		currentPremultipledAlpha = false;

		currentFlipSided = null;
		currentCullFace = null;

		currentLineWidth = null;

		currentPolygonOffsetFactor = null;
		currentPolygonOffsetUnits = null;

		currentScissor.set( 0, 0, gl.canvas.width, gl.canvas.height );
		currentViewport.set( 0, 0, gl.canvas.width, gl.canvas.height );

		colorBuffer.reset();
		depthBuffer.reset();
		stencilBuffer.reset();

	}
```
</details>


---