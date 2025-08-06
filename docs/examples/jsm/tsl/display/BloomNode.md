[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `BloomNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 24 |
| 📊 Variables & Constants | 15 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/BloomNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `HalfFloatType` | `three/webgpu` |
| `RenderTarget` | `three/webgpu` |
| `Vector2` | `three/webgpu` |
| `Vector3` | `three/webgpu` |
| `TempNode` | `three/webgpu` |
| `QuadMesh` | `three/webgpu` |
| `NodeMaterial` | `three/webgpu` |
| `RendererUtils` | `three/webgpu` |
| `NodeUpdateType` | `three/webgpu` |
| `nodeObject` | `three/tsl` |
| `Fn` | `three/tsl` |
| `float` | `three/tsl` |
| `uv` | `three/tsl` |
| `passTexture` | `three/tsl` |
| `uniform` | `three/tsl` |
| `Loop` | `three/tsl` |
| `texture` | `three/tsl` |
| `luminance` | `three/tsl` |
| `smoothstep` | `three/tsl` |
| `mix` | `three/tsl` |
| `vec4` | `three/tsl` |
| `uniformArray` | `three/tsl` |
| `add` | `three/tsl` |
| `int` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_quadMesh` | `any` | let/var | `new QuadMesh()` | ✗ |
| `_size` | `any` | let/var | `new Vector2()` | ✗ |
| `_BlurDirectionX` | `any` | let/var | `new Vector2( 1.0, 0.0 )` | ✗ |
| `_BlurDirectionY` | `any` | let/var | `new Vector2( 0.0, 1.0 )` | ✗ |
| `_rendererState` | `any` | let/var | `*not shown*` | ✗ |
| `renderTargetHorizontal` | `any` | let/var | `new RenderTarget( 1, 1, { depthBuffer: false, type: HalfFloatType } )` | ✗ |
| `renderTargetVertical` | `any` | let/var | `new RenderTarget( 1, 1, { depthBuffer: false, type: HalfFloatType } )` | ✗ |
| `inputRenderTarget` | `RenderTarget` | let/var | `this._renderTargetBright` | ✗ |
| `texel` | `any` | let/var | `this.inputNode` | ✗ |
| `kernelSizeArray` | `number[]` | let/var | `[ 6, 10, 14, 18, 22 ]` | ✗ |
| `coefficients` | `any[]` | let/var | `[]` | ✗ |
| `sigma` | `number` | let/var | `kernelRadius / 3` | ✗ |
| `sample1` | `any` | let/var | `sampleTexel( uvNode.add( uvOffset ) ).rgb` | ✗ |
| `sample2` | `any` | let/var | `sampleTexel( uvNode.sub( uvOffset ) ).rgb` | ✗ |
| `separableBlurMaterial` | `any` | let/var | `new NodeMaterial()` | ✗ |


---

## Functions

### `BloomNode.getTextureNode(): PassTextureNode`

**JSDoc:**
```typescript
/**
	 * Returns the result of the effect as a texture node.
	 *
	 * @return {PassTextureNode} A texture node that represents the result of the effect.
	 */
```

**Returns:** `PassTextureNode`

<details><summary>Code</summary>

```typescript
getTextureNode() {

		return this._textureOutput;

	}
```
</details>

### `BloomNode.setSize(width: number, height: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the size of the effect.
	 *
	 * @param {number} width - The width of the effect.
	 * @param {number} height - The height of the effect.
	 */
```

**Parameters:**

- **`width`** `number`
- **`height`** `number`

**Returns:** `void`

**Calls:**

- `Math.round`
- `this._renderTargetBright.setSize`
- `this._renderTargetsHorizontal[ i ].setSize`
- `this._renderTargetsVertical[ i ].setSize`
- `this._separableBlurMaterials[ i ].invSize.value.set`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		let resx = Math.round( width / 2 );
		let resy = Math.round( height / 2 );

		this._renderTargetBright.setSize( resx, resy );

		for ( let i = 0; i < this._nMips; i ++ ) {

			this._renderTargetsHorizontal[ i ].setSize( resx, resy );
			this._renderTargetsVertical[ i ].setSize( resx, resy );

			this._separableBlurMaterials[ i ].invSize.value.set( 1 / resx, 1 / resy );

			resx = Math.round( resx / 2 );
			resy = Math.round( resy / 2 );

		}

	}
```
</details>

### `BloomNode.updateBefore(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
	 * This method is used to render the effect once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
```

**Parameters:**

- **`frame`** `NodeFrame`

**Returns:** `void`

**Calls:**

- `RendererUtils.resetRendererState`
- `renderer.getDrawingBufferSize`
- `this.setSize`
- `renderer.setRenderTarget`
- `_quadMesh.render`
- `RendererUtils.restoreRendererState`

**Internal Comments:**
```
// (x2)
// 1. Extract bright areas (x4)
// 2. Blur all the mips progressively (x2)
// 3. Composite all the mips (x4)
// restore (x4)
```

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		const { renderer } = frame;

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		const size = renderer.getDrawingBufferSize( _size );
		this.setSize( size.width, size.height );

		// 1. Extract bright areas

		renderer.setRenderTarget( this._renderTargetBright );
		_quadMesh.material = this._highPassFilterMaterial;
		_quadMesh.render( renderer );

		// 2. Blur all the mips progressively

		let inputRenderTarget = this._renderTargetBright;

		for ( let i = 0; i < this._nMips; i ++ ) {

			_quadMesh.material = this._separableBlurMaterials[ i ];

			this._separableBlurMaterials[ i ].colorTexture.value = inputRenderTarget.texture;
			this._separableBlurMaterials[ i ].direction.value = _BlurDirectionX;
			renderer.setRenderTarget( this._renderTargetsHorizontal[ i ] );
			_quadMesh.render( renderer );

			this._separableBlurMaterials[ i ].colorTexture.value = this._renderTargetsHorizontal[ i ].texture;
			this._separableBlurMaterials[ i ].direction.value = _BlurDirectionY;
			renderer.setRenderTarget( this._renderTargetsVertical[ i ] );
			_quadMesh.render( renderer );

			inputRenderTarget = this._renderTargetsVertical[ i ];

		}

		// 3. Composite all the mips

		renderer.setRenderTarget( this._renderTargetsHorizontal[ 0 ] );
		_quadMesh.material = this._compositeMaterial;
		_quadMesh.render( renderer );

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

### `BloomNode.setup(builder: NodeBuilder): PassTextureNode`

**JSDoc:**
```typescript
/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {PassTextureNode}
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `PassTextureNode`

**Calls:**

- `Fn (from three/tsl)`
- `luminance (from three/tsl)`
- `smoothstep (from three/tsl)`
- `this.threshold.add`
- `mix (from three/tsl)`
- `vec4 (from three/tsl)`
- `luminosityHighPass().context`
- `builder.getSharedContext`
- `this._separableBlurMaterials.push`
- `this._getSeparableBlurMaterial`
- `uniformArray (from three/tsl)`
- `Fn( ( [ factor, radius ] ) => {

			const mirrorFactor = float( 1.2 ).sub( factor );
			return mix( factor, mirrorFactor, radius );

		} ).setLayout`
- `lerpBloomFactor( bloomFactors.element( 0 ), this.radius ).mul( vec4( bloomTintColors.element( 0 ), 1.0 ) ).mul`
- `lerpBloomFactor( bloomFactors.element( 1 ), this.radius ).mul( vec4( bloomTintColors.element( 1 ), 1.0 ) ).mul`
- `lerpBloomFactor( bloomFactors.element( 2 ), this.radius ).mul( vec4( bloomTintColors.element( 2 ), 1.0 ) ).mul`
- `lerpBloomFactor( bloomFactors.element( 3 ), this.radius ).mul( vec4( bloomTintColors.element( 3 ), 1.0 ) ).mul`
- `lerpBloomFactor( bloomFactors.element( 4 ), this.radius ).mul( vec4( bloomTintColors.element( 4 ), 1.0 ) ).mul`
- `color0.add( color1 ).add( color2 ).add( color3 ).add`
- `sum.mul`
- `compositePass().context`

**Internal Comments:**
```
// luminosity high pass material (x2)
// gaussian blur materials (x2)
// These sizes have been changed to account for the altered coefficents-calculation to avoid blockiness, (x2)
// while retaining the same blur-strength. For details see https://github.com/mrdoob/three.js/pull/31528 (x2)
// composite material (x2)
//
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		// luminosity high pass material

		const luminosityHighPass = Fn( () => {

			const texel = this.inputNode;
			const v = luminance( texel.rgb );

			const alpha = smoothstep( this.threshold, this.threshold.add( this.smoothWidth ), v );

			return mix( vec4( 0 ), texel, alpha );

		} );

		this._highPassFilterMaterial = this._highPassFilterMaterial || new NodeMaterial();
		this._highPassFilterMaterial.fragmentNode = luminosityHighPass().context( builder.getSharedContext() );
		this._highPassFilterMaterial.name = 'Bloom_highPass';
		this._highPassFilterMaterial.needsUpdate = true;

		// gaussian blur materials

		// These sizes have been changed to account for the altered coefficents-calculation to avoid blockiness,
		// while retaining the same blur-strength. For details see https://github.com/mrdoob/three.js/pull/31528
		const kernelSizeArray = [ 6, 10, 14, 18, 22 ];

		for ( let i = 0; i < this._nMips; i ++ ) {

			this._separableBlurMaterials.push( this._getSeparableBlurMaterial( builder, kernelSizeArray[ i ] ) );

		}

		// composite material

		const bloomFactors = uniformArray( [ 1.0, 0.8, 0.6, 0.4, 0.2 ] );
		const bloomTintColors = uniformArray( [ new Vector3( 1, 1, 1 ), new Vector3( 1, 1, 1 ), new Vector3( 1, 1, 1 ), new Vector3( 1, 1, 1 ), new Vector3( 1, 1, 1 ) ] );

		const lerpBloomFactor = Fn( ( [ factor, radius ] ) => {

			const mirrorFactor = float( 1.2 ).sub( factor );
			return mix( factor, mirrorFactor, radius );

		} ).setLayout( {
			name: 'lerpBloomFactor',
			type: 'float',
			inputs: [
				{ name: 'factor', type: 'float' },
				{ name: 'radius', type: 'float' },
			]
		} );


		const compositePass = Fn( () => {

			const color0 = lerpBloomFactor( bloomFactors.element( 0 ), this.radius ).mul( vec4( bloomTintColors.element( 0 ), 1.0 ) ).mul( this._textureNodeBlur0 );
			const color1 = lerpBloomFactor( bloomFactors.element( 1 ), this.radius ).mul( vec4( bloomTintColors.element( 1 ), 1.0 ) ).mul( this._textureNodeBlur1 );
			const color2 = lerpBloomFactor( bloomFactors.element( 2 ), this.radius ).mul( vec4( bloomTintColors.element( 2 ), 1.0 ) ).mul( this._textureNodeBlur2 );
			const color3 = lerpBloomFactor( bloomFactors.element( 3 ), this.radius ).mul( vec4( bloomTintColors.element( 3 ), 1.0 ) ).mul( this._textureNodeBlur3 );
			const color4 = lerpBloomFactor( bloomFactors.element( 4 ), this.radius ).mul( vec4( bloomTintColors.element( 4 ), 1.0 ) ).mul( this._textureNodeBlur4 );

			const sum = color0.add( color1 ).add( color2 ).add( color3 ).add( color4 );

			return sum.mul( this.strength );

		} );

		this._compositeMaterial = this._compositeMaterial || new NodeMaterial();
		this._compositeMaterial.fragmentNode = compositePass().context( builder.getSharedContext() );
		this._compositeMaterial.name = 'Bloom_comp';
		this._compositeMaterial.needsUpdate = true;

		//

		return this._textureOutput;

	}
```
</details>

### `BloomNode.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources. This method should be called
	 * when the effect is no longer required.
	 */
```

**Returns:** `void`

**Calls:**

- `this._renderTargetsHorizontal[ i ].dispose`
- `this._renderTargetsVertical[ i ].dispose`
- `this._renderTargetBright.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		for ( let i = 0; i < this._renderTargetsHorizontal.length; i ++ ) {

			this._renderTargetsHorizontal[ i ].dispose();

		}

		for ( let i = 0; i < this._renderTargetsVertical.length; i ++ ) {

			this._renderTargetsVertical[ i ].dispose();

		}

		this._renderTargetBright.dispose();

	}
```
</details>

### `BloomNode._getSeparableBlurMaterial(builder: NodeBuilder, kernelRadius: number): NodeMaterial`

**JSDoc:**
```typescript
/**
	 * Create a separable blur material for the given kernel radius.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {number} kernelRadius - The kernel radius.
	 * @return {NodeMaterial}
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`kernelRadius`** `number`

**Returns:** `NodeMaterial`

**Calls:**

- `coefficients.push`
- `Math.exp`
- `texture (from three/tsl)`
- `uniformArray (from three/tsl)`
- `uniform (from three/tsl)`
- `uv (from three/tsl)`
- `colorTexture.sample`
- `Fn (from three/tsl)`
- `sampleTexel( uvNode ).rgb.mul( gaussianCoefficients.element( 0 ) ).toVar`
- `Loop (from three/tsl)`
- `int (from three/tsl)`
- `float (from three/tsl)`
- `gaussianCoefficients.element`
- `direction.mul( invSize ).mul`
- `sampleTexel`
- `uvNode.add`
- `uvNode.sub`
- `diffuseSum.addAssign`
- `add( sample1, sample2 ).mul`
- `vec4 (from three/tsl)`
- `separableBlurPass().context`
- `builder.getSharedContext`

**Internal Comments:**
```
// (x2)
// uniforms (x4)
```

<details><summary>Code</summary>

```typescript
_getSeparableBlurMaterial( builder, kernelRadius ) {

		const coefficients = [];
		const sigma = kernelRadius / 3;

		for ( let i = 0; i < kernelRadius; i ++ ) {

			coefficients.push( 0.39894 * Math.exp( - 0.5 * i * i / ( sigma * sigma ) ) / sigma );

		}

		//

		const colorTexture = texture( null );
		const gaussianCoefficients = uniformArray( coefficients );
		const invSize = uniform( new Vector2() );
		const direction = uniform( new Vector2( 0.5, 0.5 ) );

		const uvNode = uv();
		const sampleTexel = ( uv ) => colorTexture.sample( uv );

		const separableBlurPass = Fn( () => {

			const diffuseSum = sampleTexel( uvNode ).rgb.mul( gaussianCoefficients.element( 0 ) ).toVar();

			Loop( { start: int( 1 ), end: int( kernelRadius ), type: 'int', condition: '<' }, ( { i } ) => {

				const x = float( i );
				const w = gaussianCoefficients.element( i );
				const uvOffset = direction.mul( invSize ).mul( x );
				const sample1 = sampleTexel( uvNode.add( uvOffset ) ).rgb;
				const sample2 = sampleTexel( uvNode.sub( uvOffset ) ).rgb;
				diffuseSum.addAssign( add( sample1, sample2 ).mul( w ) );

			} );

			return vec4( diffuseSum, 1.0 );

		} );

		const separableBlurMaterial = new NodeMaterial();
		separableBlurMaterial.fragmentNode = separableBlurPass().context( builder.getSharedContext() );
		separableBlurMaterial.name = 'Bloom_separable';
		separableBlurMaterial.needsUpdate = true;

		// uniforms
		separableBlurMaterial.colorTexture = colorTexture;
		separableBlurMaterial.direction = direction;
		separableBlurMaterial.invSize = invSize;

		return separableBlurMaterial;

	}
```
</details>

### `sampleTexel(uv: any): any`

**Parameters:**

- **`uv`** `any`

**Returns:** `any`

**Calls:**

- `colorTexture.sample`

<details><summary>Code</summary>

```typescript
( uv ) => colorTexture.sample( uv )
```
</details>

### `bloom(node: any, strength: number, radius: number, threshold: number): BloomNode`

**Parameters:**

- **`node`** `any`
- **`strength`** `number`
- **`radius`** `number`
- **`threshold`** `number`

**Returns:** `BloomNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( node, strength, radius, threshold ) => nodeObject( new BloomNode( nodeObject( node ), strength, radius, threshold ) )
```
</details>


---

## Classes

### `BloomNode`

<details><summary>Class Code</summary>

```ts
class BloomNode extends TempNode {

	static get type() {

		return 'BloomNode';

	}

	/**
	 * Constructs a new bloom node.
	 *
	 * @param {Node<vec4>} inputNode - The node that represents the input of the effect.
	 * @param {number} [strength=1] - The strength of the bloom.
	 * @param {number} [radius=0] - The radius of the bloom.
	 * @param {number} [threshold=0] - The luminance threshold limits which bright areas contribute to the bloom effect.
	 */
	constructor( inputNode, strength = 1, radius = 0, threshold = 0 ) {

		super( 'vec4' );

		/**
		 * The node that represents the input of the effect.
		 *
		 * @type {Node<vec4>}
		 */
		this.inputNode = inputNode;

		/**
		 * The strength of the bloom.
		 *
		 * @type {UniformNode<float>}
		 */
		this.strength = uniform( strength );

		/**
		 * The radius of the bloom.
		 *
		 * @type {UniformNode<float>}
		 */
		this.radius = uniform( radius );

		/**
		 * The luminance threshold limits which bright areas contribute to the bloom effect.
		 *
		 * @type {UniformNode<float>}
		 */
		this.threshold = uniform( threshold );

		/**
		 * Can be used to tweak the extracted luminance from the scene.
		 *
		 * @type {UniformNode<float>}
		 */
		this.smoothWidth = uniform( 0.01 );

		/**
		 * An array that holds the render targets for the horizontal blur passes.
		 *
		 * @private
		 * @type {Array<RenderTarget>}
		 */
		this._renderTargetsHorizontal = [];

		/**
		 * An array that holds the render targets for the vertical blur passes.
		 *
		 * @private
		 * @type {Array<RenderTarget>}
		 */
		this._renderTargetsVertical = [];

		/**
		 * The number if blur mips.
		 *
		 * @private
		 * @type {number}
		 */
		this._nMips = 5;

		/**
		 * The render target for the luminance pass.
		 *
		 * @private
		 * @type {RenderTarget}
		 */
		this._renderTargetBright = new RenderTarget( 1, 1, { depthBuffer: false, type: HalfFloatType } );
		this._renderTargetBright.texture.name = 'UnrealBloomPass.bright';
		this._renderTargetBright.texture.generateMipmaps = false;

		//

		for ( let i = 0; i < this._nMips; i ++ ) {

			const renderTargetHorizontal = new RenderTarget( 1, 1, { depthBuffer: false, type: HalfFloatType } );

			renderTargetHorizontal.texture.name = 'UnrealBloomPass.h' + i;
			renderTargetHorizontal.texture.generateMipmaps = false;

			this._renderTargetsHorizontal.push( renderTargetHorizontal );

			const renderTargetVertical = new RenderTarget( 1, 1, { depthBuffer: false, type: HalfFloatType } );

			renderTargetVertical.texture.name = 'UnrealBloomPass.v' + i;
			renderTargetVertical.texture.generateMipmaps = false;

			this._renderTargetsVertical.push( renderTargetVertical );

		}

		/**
		 * The material for the composite pass.
		 *
		 * @private
		 * @type {?NodeMaterial}
		 */
		this._compositeMaterial = null;

		/**
		 * The material for the luminance pass.
		 *
		 * @private
		 * @type {?NodeMaterial}
		 */
		this._highPassFilterMaterial = null;

		/**
		 * The materials for the blur pass.
		 *
		 * @private
		 * @type {Array<NodeMaterial>}
		 */
		this._separableBlurMaterials = [];

		/**
		 * The result of the luminance pass as a texture node for further processing.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._textureNodeBright = texture( this._renderTargetBright.texture );

		/**
		 * The result of the first blur pass as a texture node for further processing.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._textureNodeBlur0 = texture( this._renderTargetsVertical[ 0 ].texture );

		/**
		 * The result of the second blur pass as a texture node for further processing.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._textureNodeBlur1 = texture( this._renderTargetsVertical[ 1 ].texture );

		/**
		 * The result of the third blur pass as a texture node for further processing.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._textureNodeBlur2 = texture( this._renderTargetsVertical[ 2 ].texture );

		/**
		 * The result of the fourth blur pass as a texture node for further processing.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._textureNodeBlur3 = texture( this._renderTargetsVertical[ 3 ].texture );

		/**
		 * The result of the fifth blur pass as a texture node for further processing.
		 *
		 * @private
		 * @type {TextureNode}
		 */
		this._textureNodeBlur4 = texture( this._renderTargetsVertical[ 4 ].texture );

		/**
		 * The result of the effect is represented as a separate texture node.
		 *
		 * @private
		 * @type {PassTextureNode}
		 */
		this._textureOutput = passTexture( this, this._renderTargetsHorizontal[ 0 ].texture );

		/**
		 * The `updateBeforeType` is set to `NodeUpdateType.FRAME` since the node renders
		 * its effect once per frame in `updateBefore()`.
		 *
		 * @type {string}
		 * @default 'frame'
		 */
		this.updateBeforeType = NodeUpdateType.FRAME;

	}

	/**
	 * Returns the result of the effect as a texture node.
	 *
	 * @return {PassTextureNode} A texture node that represents the result of the effect.
	 */
	getTextureNode() {

		return this._textureOutput;

	}

	/**
	 * Sets the size of the effect.
	 *
	 * @param {number} width - The width of the effect.
	 * @param {number} height - The height of the effect.
	 */
	setSize( width, height ) {

		let resx = Math.round( width / 2 );
		let resy = Math.round( height / 2 );

		this._renderTargetBright.setSize( resx, resy );

		for ( let i = 0; i < this._nMips; i ++ ) {

			this._renderTargetsHorizontal[ i ].setSize( resx, resy );
			this._renderTargetsVertical[ i ].setSize( resx, resy );

			this._separableBlurMaterials[ i ].invSize.value.set( 1 / resx, 1 / resy );

			resx = Math.round( resx / 2 );
			resy = Math.round( resy / 2 );

		}

	}

	/**
	 * This method is used to render the effect once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
	updateBefore( frame ) {

		const { renderer } = frame;

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		const size = renderer.getDrawingBufferSize( _size );
		this.setSize( size.width, size.height );

		// 1. Extract bright areas

		renderer.setRenderTarget( this._renderTargetBright );
		_quadMesh.material = this._highPassFilterMaterial;
		_quadMesh.render( renderer );

		// 2. Blur all the mips progressively

		let inputRenderTarget = this._renderTargetBright;

		for ( let i = 0; i < this._nMips; i ++ ) {

			_quadMesh.material = this._separableBlurMaterials[ i ];

			this._separableBlurMaterials[ i ].colorTexture.value = inputRenderTarget.texture;
			this._separableBlurMaterials[ i ].direction.value = _BlurDirectionX;
			renderer.setRenderTarget( this._renderTargetsHorizontal[ i ] );
			_quadMesh.render( renderer );

			this._separableBlurMaterials[ i ].colorTexture.value = this._renderTargetsHorizontal[ i ].texture;
			this._separableBlurMaterials[ i ].direction.value = _BlurDirectionY;
			renderer.setRenderTarget( this._renderTargetsVertical[ i ] );
			_quadMesh.render( renderer );

			inputRenderTarget = this._renderTargetsVertical[ i ];

		}

		// 3. Composite all the mips

		renderer.setRenderTarget( this._renderTargetsHorizontal[ 0 ] );
		_quadMesh.material = this._compositeMaterial;
		_quadMesh.render( renderer );

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}

	/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {PassTextureNode}
	 */
	setup( builder ) {

		// luminosity high pass material

		const luminosityHighPass = Fn( () => {

			const texel = this.inputNode;
			const v = luminance( texel.rgb );

			const alpha = smoothstep( this.threshold, this.threshold.add( this.smoothWidth ), v );

			return mix( vec4( 0 ), texel, alpha );

		} );

		this._highPassFilterMaterial = this._highPassFilterMaterial || new NodeMaterial();
		this._highPassFilterMaterial.fragmentNode = luminosityHighPass().context( builder.getSharedContext() );
		this._highPassFilterMaterial.name = 'Bloom_highPass';
		this._highPassFilterMaterial.needsUpdate = true;

		// gaussian blur materials

		// These sizes have been changed to account for the altered coefficents-calculation to avoid blockiness,
		// while retaining the same blur-strength. For details see https://github.com/mrdoob/three.js/pull/31528
		const kernelSizeArray = [ 6, 10, 14, 18, 22 ];

		for ( let i = 0; i < this._nMips; i ++ ) {

			this._separableBlurMaterials.push( this._getSeparableBlurMaterial( builder, kernelSizeArray[ i ] ) );

		}

		// composite material

		const bloomFactors = uniformArray( [ 1.0, 0.8, 0.6, 0.4, 0.2 ] );
		const bloomTintColors = uniformArray( [ new Vector3( 1, 1, 1 ), new Vector3( 1, 1, 1 ), new Vector3( 1, 1, 1 ), new Vector3( 1, 1, 1 ), new Vector3( 1, 1, 1 ) ] );

		const lerpBloomFactor = Fn( ( [ factor, radius ] ) => {

			const mirrorFactor = float( 1.2 ).sub( factor );
			return mix( factor, mirrorFactor, radius );

		} ).setLayout( {
			name: 'lerpBloomFactor',
			type: 'float',
			inputs: [
				{ name: 'factor', type: 'float' },
				{ name: 'radius', type: 'float' },
			]
		} );


		const compositePass = Fn( () => {

			const color0 = lerpBloomFactor( bloomFactors.element( 0 ), this.radius ).mul( vec4( bloomTintColors.element( 0 ), 1.0 ) ).mul( this._textureNodeBlur0 );
			const color1 = lerpBloomFactor( bloomFactors.element( 1 ), this.radius ).mul( vec4( bloomTintColors.element( 1 ), 1.0 ) ).mul( this._textureNodeBlur1 );
			const color2 = lerpBloomFactor( bloomFactors.element( 2 ), this.radius ).mul( vec4( bloomTintColors.element( 2 ), 1.0 ) ).mul( this._textureNodeBlur2 );
			const color3 = lerpBloomFactor( bloomFactors.element( 3 ), this.radius ).mul( vec4( bloomTintColors.element( 3 ), 1.0 ) ).mul( this._textureNodeBlur3 );
			const color4 = lerpBloomFactor( bloomFactors.element( 4 ), this.radius ).mul( vec4( bloomTintColors.element( 4 ), 1.0 ) ).mul( this._textureNodeBlur4 );

			const sum = color0.add( color1 ).add( color2 ).add( color3 ).add( color4 );

			return sum.mul( this.strength );

		} );

		this._compositeMaterial = this._compositeMaterial || new NodeMaterial();
		this._compositeMaterial.fragmentNode = compositePass().context( builder.getSharedContext() );
		this._compositeMaterial.name = 'Bloom_comp';
		this._compositeMaterial.needsUpdate = true;

		//

		return this._textureOutput;

	}

	/**
	 * Frees internal resources. This method should be called
	 * when the effect is no longer required.
	 */
	dispose() {

		for ( let i = 0; i < this._renderTargetsHorizontal.length; i ++ ) {

			this._renderTargetsHorizontal[ i ].dispose();

		}

		for ( let i = 0; i < this._renderTargetsVertical.length; i ++ ) {

			this._renderTargetsVertical[ i ].dispose();

		}

		this._renderTargetBright.dispose();

	}

	/**
	 * Create a separable blur material for the given kernel radius.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {number} kernelRadius - The kernel radius.
	 * @return {NodeMaterial}
	 */
	_getSeparableBlurMaterial( builder, kernelRadius ) {

		const coefficients = [];
		const sigma = kernelRadius / 3;

		for ( let i = 0; i < kernelRadius; i ++ ) {

			coefficients.push( 0.39894 * Math.exp( - 0.5 * i * i / ( sigma * sigma ) ) / sigma );

		}

		//

		const colorTexture = texture( null );
		const gaussianCoefficients = uniformArray( coefficients );
		const invSize = uniform( new Vector2() );
		const direction = uniform( new Vector2( 0.5, 0.5 ) );

		const uvNode = uv();
		const sampleTexel = ( uv ) => colorTexture.sample( uv );

		const separableBlurPass = Fn( () => {

			const diffuseSum = sampleTexel( uvNode ).rgb.mul( gaussianCoefficients.element( 0 ) ).toVar();

			Loop( { start: int( 1 ), end: int( kernelRadius ), type: 'int', condition: '<' }, ( { i } ) => {

				const x = float( i );
				const w = gaussianCoefficients.element( i );
				const uvOffset = direction.mul( invSize ).mul( x );
				const sample1 = sampleTexel( uvNode.add( uvOffset ) ).rgb;
				const sample2 = sampleTexel( uvNode.sub( uvOffset ) ).rgb;
				diffuseSum.addAssign( add( sample1, sample2 ).mul( w ) );

			} );

			return vec4( diffuseSum, 1.0 );

		} );

		const separableBlurMaterial = new NodeMaterial();
		separableBlurMaterial.fragmentNode = separableBlurPass().context( builder.getSharedContext() );
		separableBlurMaterial.name = 'Bloom_separable';
		separableBlurMaterial.needsUpdate = true;

		// uniforms
		separableBlurMaterial.colorTexture = colorTexture;
		separableBlurMaterial.direction = direction;
		separableBlurMaterial.invSize = invSize;

		return separableBlurMaterial;

	}

}
```
</details>

#### Methods

##### `getTextureNode(): PassTextureNode`

<details><summary>Code</summary>

```ts
getTextureNode() {

		return this._textureOutput;

	}
```
</details>

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		let resx = Math.round( width / 2 );
		let resy = Math.round( height / 2 );

		this._renderTargetBright.setSize( resx, resy );

		for ( let i = 0; i < this._nMips; i ++ ) {

			this._renderTargetsHorizontal[ i ].setSize( resx, resy );
			this._renderTargetsVertical[ i ].setSize( resx, resy );

			this._separableBlurMaterials[ i ].invSize.value.set( 1 / resx, 1 / resy );

			resx = Math.round( resx / 2 );
			resy = Math.round( resy / 2 );

		}

	}
```
</details>

##### `updateBefore(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		const { renderer } = frame;

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		const size = renderer.getDrawingBufferSize( _size );
		this.setSize( size.width, size.height );

		// 1. Extract bright areas

		renderer.setRenderTarget( this._renderTargetBright );
		_quadMesh.material = this._highPassFilterMaterial;
		_quadMesh.render( renderer );

		// 2. Blur all the mips progressively

		let inputRenderTarget = this._renderTargetBright;

		for ( let i = 0; i < this._nMips; i ++ ) {

			_quadMesh.material = this._separableBlurMaterials[ i ];

			this._separableBlurMaterials[ i ].colorTexture.value = inputRenderTarget.texture;
			this._separableBlurMaterials[ i ].direction.value = _BlurDirectionX;
			renderer.setRenderTarget( this._renderTargetsHorizontal[ i ] );
			_quadMesh.render( renderer );

			this._separableBlurMaterials[ i ].colorTexture.value = this._renderTargetsHorizontal[ i ].texture;
			this._separableBlurMaterials[ i ].direction.value = _BlurDirectionY;
			renderer.setRenderTarget( this._renderTargetsVertical[ i ] );
			_quadMesh.render( renderer );

			inputRenderTarget = this._renderTargetsVertical[ i ];

		}

		// 3. Composite all the mips

		renderer.setRenderTarget( this._renderTargetsHorizontal[ 0 ] );
		_quadMesh.material = this._compositeMaterial;
		_quadMesh.render( renderer );

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

##### `setup(builder: NodeBuilder): PassTextureNode`

<details><summary>Code</summary>

```ts
setup( builder ) {

		// luminosity high pass material

		const luminosityHighPass = Fn( () => {

			const texel = this.inputNode;
			const v = luminance( texel.rgb );

			const alpha = smoothstep( this.threshold, this.threshold.add( this.smoothWidth ), v );

			return mix( vec4( 0 ), texel, alpha );

		} );

		this._highPassFilterMaterial = this._highPassFilterMaterial || new NodeMaterial();
		this._highPassFilterMaterial.fragmentNode = luminosityHighPass().context( builder.getSharedContext() );
		this._highPassFilterMaterial.name = 'Bloom_highPass';
		this._highPassFilterMaterial.needsUpdate = true;

		// gaussian blur materials

		// These sizes have been changed to account for the altered coefficents-calculation to avoid blockiness,
		// while retaining the same blur-strength. For details see https://github.com/mrdoob/three.js/pull/31528
		const kernelSizeArray = [ 6, 10, 14, 18, 22 ];

		for ( let i = 0; i < this._nMips; i ++ ) {

			this._separableBlurMaterials.push( this._getSeparableBlurMaterial( builder, kernelSizeArray[ i ] ) );

		}

		// composite material

		const bloomFactors = uniformArray( [ 1.0, 0.8, 0.6, 0.4, 0.2 ] );
		const bloomTintColors = uniformArray( [ new Vector3( 1, 1, 1 ), new Vector3( 1, 1, 1 ), new Vector3( 1, 1, 1 ), new Vector3( 1, 1, 1 ), new Vector3( 1, 1, 1 ) ] );

		const lerpBloomFactor = Fn( ( [ factor, radius ] ) => {

			const mirrorFactor = float( 1.2 ).sub( factor );
			return mix( factor, mirrorFactor, radius );

		} ).setLayout( {
			name: 'lerpBloomFactor',
			type: 'float',
			inputs: [
				{ name: 'factor', type: 'float' },
				{ name: 'radius', type: 'float' },
			]
		} );


		const compositePass = Fn( () => {

			const color0 = lerpBloomFactor( bloomFactors.element( 0 ), this.radius ).mul( vec4( bloomTintColors.element( 0 ), 1.0 ) ).mul( this._textureNodeBlur0 );
			const color1 = lerpBloomFactor( bloomFactors.element( 1 ), this.radius ).mul( vec4( bloomTintColors.element( 1 ), 1.0 ) ).mul( this._textureNodeBlur1 );
			const color2 = lerpBloomFactor( bloomFactors.element( 2 ), this.radius ).mul( vec4( bloomTintColors.element( 2 ), 1.0 ) ).mul( this._textureNodeBlur2 );
			const color3 = lerpBloomFactor( bloomFactors.element( 3 ), this.radius ).mul( vec4( bloomTintColors.element( 3 ), 1.0 ) ).mul( this._textureNodeBlur3 );
			const color4 = lerpBloomFactor( bloomFactors.element( 4 ), this.radius ).mul( vec4( bloomTintColors.element( 4 ), 1.0 ) ).mul( this._textureNodeBlur4 );

			const sum = color0.add( color1 ).add( color2 ).add( color3 ).add( color4 );

			return sum.mul( this.strength );

		} );

		this._compositeMaterial = this._compositeMaterial || new NodeMaterial();
		this._compositeMaterial.fragmentNode = compositePass().context( builder.getSharedContext() );
		this._compositeMaterial.name = 'Bloom_comp';
		this._compositeMaterial.needsUpdate = true;

		//

		return this._textureOutput;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		for ( let i = 0; i < this._renderTargetsHorizontal.length; i ++ ) {

			this._renderTargetsHorizontal[ i ].dispose();

		}

		for ( let i = 0; i < this._renderTargetsVertical.length; i ++ ) {

			this._renderTargetsVertical[ i ].dispose();

		}

		this._renderTargetBright.dispose();

	}
```
</details>

##### `_getSeparableBlurMaterial(builder: NodeBuilder, kernelRadius: number): NodeMaterial`

<details><summary>Code</summary>

```ts
_getSeparableBlurMaterial( builder, kernelRadius ) {

		const coefficients = [];
		const sigma = kernelRadius / 3;

		for ( let i = 0; i < kernelRadius; i ++ ) {

			coefficients.push( 0.39894 * Math.exp( - 0.5 * i * i / ( sigma * sigma ) ) / sigma );

		}

		//

		const colorTexture = texture( null );
		const gaussianCoefficients = uniformArray( coefficients );
		const invSize = uniform( new Vector2() );
		const direction = uniform( new Vector2( 0.5, 0.5 ) );

		const uvNode = uv();
		const sampleTexel = ( uv ) => colorTexture.sample( uv );

		const separableBlurPass = Fn( () => {

			const diffuseSum = sampleTexel( uvNode ).rgb.mul( gaussianCoefficients.element( 0 ) ).toVar();

			Loop( { start: int( 1 ), end: int( kernelRadius ), type: 'int', condition: '<' }, ( { i } ) => {

				const x = float( i );
				const w = gaussianCoefficients.element( i );
				const uvOffset = direction.mul( invSize ).mul( x );
				const sample1 = sampleTexel( uvNode.add( uvOffset ) ).rgb;
				const sample2 = sampleTexel( uvNode.sub( uvOffset ) ).rgb;
				diffuseSum.addAssign( add( sample1, sample2 ).mul( w ) );

			} );

			return vec4( diffuseSum, 1.0 );

		} );

		const separableBlurMaterial = new NodeMaterial();
		separableBlurMaterial.fragmentNode = separableBlurPass().context( builder.getSharedContext() );
		separableBlurMaterial.name = 'Bloom_separable';
		separableBlurMaterial.needsUpdate = true;

		// uniforms
		separableBlurMaterial.colorTexture = colorTexture;
		separableBlurMaterial.direction = direction;
		separableBlurMaterial.invSize = invSize;

		return separableBlurMaterial;

	}
```
</details>


---