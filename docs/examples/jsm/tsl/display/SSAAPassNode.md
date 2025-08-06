[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `SSAAPassNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 13 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/SSAAPassNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AdditiveBlending` | `three/webgpu` |
| `Color` | `three/webgpu` |
| `Vector2` | `three/webgpu` |
| `RendererUtils` | `three/webgpu` |
| `PassNode` | `three/webgpu` |
| `QuadMesh` | `three/webgpu` |
| `NodeMaterial` | `three/webgpu` |
| `nodeObject` | `three/tsl` |
| `uniform` | `three/tsl` |
| `mrt` | `three/tsl` |
| `texture` | `three/tsl` |
| `getTextureIndex` | `three/tsl` |
| `unpremultiplyAlpha` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_size` | `any` | let/var | `new Vector2()` | ✗ |
| `_rendererState` | `any` | let/var | `*not shown*` | ✗ |
| `jitterOffsets` | `number[][]` | let/var | `_JitterVectors[ Math.max( 0, Math.min( this.sampleLevel, 5 ) ) ]` | ✗ |
| `baseSampleWeight` | `number` | let/var | `1.0 / jitterOffsets.length` | ✗ |
| `roundingRange` | `number` | let/var | `1 / 32` | ✗ |
| `viewOffset` | `{ fullWidth: any; fullHeight: any; of...` | let/var | `{ fullWidth: this.renderTarget.width, fullHeight: this.renderTarget.height, o...` | ✗ |
| `jitterOffset` | `number[]` | let/var | `jitterOffsets[ i ]` | ✗ |
| `uniformCenteredDistribution` | `number` | let/var | `( - 0.5 + ( i + 0.5 ) / jitterOffsets.length )` | ✗ |
| `sampleTexture` | `any` | let/var | `*not shown*` | ✗ |
| `outputs` | `{}` | let/var | `{}` | ✗ |
| `_JitterVectors` | `number[][][]` | let/var | `[ [ [ 0, 0 ] ], [ [ 4, 4 ], [ - 4, - 4 ] ], [ [ - 2, - 6 ], [ 6, - 2 ], [ - 6...` | ✗ |


---

## Functions

### `SSAAPassNode.updateBefore(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
	 * This method is used to render the SSAA effect once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
```

**Parameters:**

- **`frame`** `NodeFrame`

**Returns:** `void`

**Calls:**

- `RendererUtils.resetRendererState`
- `renderer.getPixelRatio`
- `renderer.getSize`
- `this.setSize`
- `this._sampleRenderTarget.setSize`
- `renderer.setMRT`
- `this.getMRT`
- `Math.max`
- `Math.min`
- `Object.assign`
- `camera.setViewOffset`
- `renderer.setClearColor`
- `renderer.setRenderTarget`
- `renderer.clear`
- `renderer.render`
- `this._quadMesh.render`
- `renderer.copyTextureToTexture`
- `camera.clearViewOffset`
- `RendererUtils.restoreRendererState`

**Internal Comments:**
```
// (x13)
// render the scene multiple times, each slightly jitter offset from the last and accumulate the results.
// the theory is that equal weights for each sample lead to an accumulation of rounding errors. (x2)
// The following equation varies the sampleWeight per sample so that it is uniformly distributed (x2)
// across a range of values whose rounding errors cancel each other out. (x2)
// accumulation (x4)
// restore
```

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		const { renderer } = frame;
		const { scene, camera } = this;

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		this._pixelRatio = renderer.getPixelRatio();

		const size = renderer.getSize( _size );

		this.setSize( size.width, size.height );
		this._sampleRenderTarget.setSize( this.renderTarget.width, this.renderTarget.height );

		//

		this._cameraNear.value = camera.near;
		this._cameraFar.value = camera.far;

		renderer.setMRT( this.getMRT() );
		renderer.autoClear = false;

		const jitterOffsets = _JitterVectors[ Math.max( 0, Math.min( this.sampleLevel, 5 ) ) ];

		const baseSampleWeight = 1.0 / jitterOffsets.length;
		const roundingRange = 1 / 32;

		const viewOffset = {

			fullWidth: this.renderTarget.width,
			fullHeight: this.renderTarget.height,
			offsetX: 0,
			offsetY: 0,
			width: this.renderTarget.width,
			height: this.renderTarget.height

		};

		const originalViewOffset = Object.assign( {}, camera.view );

		if ( originalViewOffset.enabled ) Object.assign( viewOffset, originalViewOffset );

		// render the scene multiple times, each slightly jitter offset from the last and accumulate the results.

		for ( let i = 0; i < jitterOffsets.length; i ++ ) {

			const jitterOffset = jitterOffsets[ i ];

			if ( camera.setViewOffset ) {

				camera.setViewOffset(

					viewOffset.fullWidth, viewOffset.fullHeight,

					viewOffset.offsetX + jitterOffset[ 0 ] * 0.0625, viewOffset.offsetY + jitterOffset[ 1 ] * 0.0625, // 0.0625 = 1 / 16

					viewOffset.width, viewOffset.height

				);

			}

			this.sampleWeight.value = baseSampleWeight;

			if ( this.unbiased ) {

				// the theory is that equal weights for each sample lead to an accumulation of rounding errors.
				// The following equation varies the sampleWeight per sample so that it is uniformly distributed
				// across a range of values whose rounding errors cancel each other out.

				const uniformCenteredDistribution = ( - 0.5 + ( i + 0.5 ) / jitterOffsets.length );
				this.sampleWeight.value += roundingRange * uniformCenteredDistribution;

			}

			renderer.setClearColor( this.clearColor, this.clearAlpha );
			renderer.setRenderTarget( this._sampleRenderTarget );
			renderer.clear();
			renderer.render( scene, camera );

			// accumulation

			renderer.setRenderTarget( this.renderTarget );

			if ( i === 0 ) {

				renderer.setClearColor( 0x000000, 0.0 );
				renderer.clear();

			}

			this._quadMesh.render( renderer );

		}

		renderer.copyTextureToTexture( this._sampleRenderTarget.depthTexture, this.renderTarget.depthTexture );

		// restore

		if ( camera.setViewOffset && originalViewOffset.enabled ) {

			camera.setViewOffset(

				originalViewOffset.fullWidth, originalViewOffset.fullHeight,

				originalViewOffset.offsetX, originalViewOffset.offsetY,

				originalViewOffset.width, originalViewOffset.height

			);

		} else if ( camera.clearViewOffset ) {

			camera.clearViewOffset();

		}

		//

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

### `SSAAPassNode.setup(builder: NodeBuilder): PassTextureNode`

**JSDoc:**
```typescript
/**
	 * This method is used to setup the effect's MRT configuration and quad mesh.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {PassTextureNode}
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `PassTextureNode`

**Calls:**

- `this.renderTarget.clone`
- `this.getMRT`
- `getTextureIndex (from three/tsl)`
- `texture( this._sampleRenderTarget.textures[ index ] ).mul`
- `mrt (from three/tsl)`
- `texture( this._sampleRenderTarget.texture ).mul`
- `unpremultiplyAlpha (from three/tsl)`
- `super.setup`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		if ( this._sampleRenderTarget === null ) {

			this._sampleRenderTarget = this.renderTarget.clone();

		}

		let sampleTexture;

		const passMRT = this.getMRT();

		if ( passMRT !== null ) {

			const outputs = {};

			for ( const name in passMRT.outputNodes ) {

				const index = getTextureIndex( this._sampleRenderTarget.textures, name );

				if ( index >= 0 ) {

					outputs[ name ] = texture( this._sampleRenderTarget.textures[ index ] ).mul( this.sampleWeight );

				}

			}

			sampleTexture = mrt( outputs );

		} else {

			sampleTexture = texture( this._sampleRenderTarget.texture ).mul( this.sampleWeight );

		}

		this._quadMesh.material = new NodeMaterial();
		this._quadMesh.material.fragmentNode = unpremultiplyAlpha( sampleTexture );
		this._quadMesh.material.transparent = true;
		this._quadMesh.material.depthTest = false;
		this._quadMesh.material.depthWrite = false;
		this._quadMesh.material.premultipliedAlpha = true;
		this._quadMesh.material.blending = AdditiveBlending;
		this._quadMesh.material.name = 'SSAA';

		return super.setup( builder );

	}
```
</details>

### `SSAAPassNode.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources. This method should be called
	 * when the pass is no longer required.
	 */
```

**Returns:** `void`

**Calls:**

- `super.dispose`
- `this._sampleRenderTarget.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		super.dispose();

		if ( this._sampleRenderTarget !== null ) {

			this._sampleRenderTarget.dispose();

		}

	}
```
</details>

### `ssaaPass(scene: Scene, camera: Camera): SSAAPassNode`

**Parameters:**

- **`scene`** `Scene`
- **`camera`** `Camera`

**Returns:** `SSAAPassNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( scene, camera ) => nodeObject( new SSAAPassNode( scene, camera ) )
```
</details>


---

## Classes

### `SSAAPassNode`

<details><summary>Class Code</summary>

```ts
class SSAAPassNode extends PassNode {

	static get type() {

		return 'SSAAPassNode';

	}

	/**
	 * Constructs a new SSAA pass node.
	 *
	 * @param {Scene} scene - The scene to render.
	 * @param {Camera} camera - The camera to render the scene with.
	 */
	constructor( scene, camera ) {

		super( PassNode.COLOR, scene, camera );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSSAAPassNode = true;

		/**
		 * The sample level specified  as n, where the number of samples is 2^n,
		 * so sampleLevel = 4, is 2^4 samples, 16.
		 *
		 * @type {number}
		 * @default 4
		 */
		this.sampleLevel = 4;

		/**
		 * Whether rounding errors should be mitigated or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.unbiased = true;

		/**
		 * The clear color of the pass.
		 *
		 * @type {Color}
		 * @default 0x000000
		 */
		this.clearColor = new Color( 0x000000 );

		/**
		 * The clear alpha of the pass.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.clearAlpha = 0;

		/**
		 * A uniform node representing the sample weight.
		 *
		 * @type {UniformNode<float>}
		 * @default 1
		 */
		this.sampleWeight = uniform( 1 );

		/**
		 * Reference to the internal render target that holds the current sample.
		 *
		 * @private
		 * @type {?RenderTarget}
		 * @default null
		 */
		this._sampleRenderTarget = null;

		/**
		 * Reference to the internal quad mesh.
		 *
		 * @private
		 * @type {QuadMesh}
		 */
		this._quadMesh = new QuadMesh();

	}

	/**
	 * This method is used to render the SSAA effect once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
	updateBefore( frame ) {

		const { renderer } = frame;
		const { scene, camera } = this;

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		this._pixelRatio = renderer.getPixelRatio();

		const size = renderer.getSize( _size );

		this.setSize( size.width, size.height );
		this._sampleRenderTarget.setSize( this.renderTarget.width, this.renderTarget.height );

		//

		this._cameraNear.value = camera.near;
		this._cameraFar.value = camera.far;

		renderer.setMRT( this.getMRT() );
		renderer.autoClear = false;

		const jitterOffsets = _JitterVectors[ Math.max( 0, Math.min( this.sampleLevel, 5 ) ) ];

		const baseSampleWeight = 1.0 / jitterOffsets.length;
		const roundingRange = 1 / 32;

		const viewOffset = {

			fullWidth: this.renderTarget.width,
			fullHeight: this.renderTarget.height,
			offsetX: 0,
			offsetY: 0,
			width: this.renderTarget.width,
			height: this.renderTarget.height

		};

		const originalViewOffset = Object.assign( {}, camera.view );

		if ( originalViewOffset.enabled ) Object.assign( viewOffset, originalViewOffset );

		// render the scene multiple times, each slightly jitter offset from the last and accumulate the results.

		for ( let i = 0; i < jitterOffsets.length; i ++ ) {

			const jitterOffset = jitterOffsets[ i ];

			if ( camera.setViewOffset ) {

				camera.setViewOffset(

					viewOffset.fullWidth, viewOffset.fullHeight,

					viewOffset.offsetX + jitterOffset[ 0 ] * 0.0625, viewOffset.offsetY + jitterOffset[ 1 ] * 0.0625, // 0.0625 = 1 / 16

					viewOffset.width, viewOffset.height

				);

			}

			this.sampleWeight.value = baseSampleWeight;

			if ( this.unbiased ) {

				// the theory is that equal weights for each sample lead to an accumulation of rounding errors.
				// The following equation varies the sampleWeight per sample so that it is uniformly distributed
				// across a range of values whose rounding errors cancel each other out.

				const uniformCenteredDistribution = ( - 0.5 + ( i + 0.5 ) / jitterOffsets.length );
				this.sampleWeight.value += roundingRange * uniformCenteredDistribution;

			}

			renderer.setClearColor( this.clearColor, this.clearAlpha );
			renderer.setRenderTarget( this._sampleRenderTarget );
			renderer.clear();
			renderer.render( scene, camera );

			// accumulation

			renderer.setRenderTarget( this.renderTarget );

			if ( i === 0 ) {

				renderer.setClearColor( 0x000000, 0.0 );
				renderer.clear();

			}

			this._quadMesh.render( renderer );

		}

		renderer.copyTextureToTexture( this._sampleRenderTarget.depthTexture, this.renderTarget.depthTexture );

		// restore

		if ( camera.setViewOffset && originalViewOffset.enabled ) {

			camera.setViewOffset(

				originalViewOffset.fullWidth, originalViewOffset.fullHeight,

				originalViewOffset.offsetX, originalViewOffset.offsetY,

				originalViewOffset.width, originalViewOffset.height

			);

		} else if ( camera.clearViewOffset ) {

			camera.clearViewOffset();

		}

		//

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}

	/**
	 * This method is used to setup the effect's MRT configuration and quad mesh.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {PassTextureNode}
	 */
	setup( builder ) {

		if ( this._sampleRenderTarget === null ) {

			this._sampleRenderTarget = this.renderTarget.clone();

		}

		let sampleTexture;

		const passMRT = this.getMRT();

		if ( passMRT !== null ) {

			const outputs = {};

			for ( const name in passMRT.outputNodes ) {

				const index = getTextureIndex( this._sampleRenderTarget.textures, name );

				if ( index >= 0 ) {

					outputs[ name ] = texture( this._sampleRenderTarget.textures[ index ] ).mul( this.sampleWeight );

				}

			}

			sampleTexture = mrt( outputs );

		} else {

			sampleTexture = texture( this._sampleRenderTarget.texture ).mul( this.sampleWeight );

		}

		this._quadMesh.material = new NodeMaterial();
		this._quadMesh.material.fragmentNode = unpremultiplyAlpha( sampleTexture );
		this._quadMesh.material.transparent = true;
		this._quadMesh.material.depthTest = false;
		this._quadMesh.material.depthWrite = false;
		this._quadMesh.material.premultipliedAlpha = true;
		this._quadMesh.material.blending = AdditiveBlending;
		this._quadMesh.material.name = 'SSAA';

		return super.setup( builder );

	}

	/**
	 * Frees internal resources. This method should be called
	 * when the pass is no longer required.
	 */
	dispose() {

		super.dispose();

		if ( this._sampleRenderTarget !== null ) {

			this._sampleRenderTarget.dispose();

		}

	}

}
```
</details>

#### Methods

##### `updateBefore(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		const { renderer } = frame;
		const { scene, camera } = this;

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		this._pixelRatio = renderer.getPixelRatio();

		const size = renderer.getSize( _size );

		this.setSize( size.width, size.height );
		this._sampleRenderTarget.setSize( this.renderTarget.width, this.renderTarget.height );

		//

		this._cameraNear.value = camera.near;
		this._cameraFar.value = camera.far;

		renderer.setMRT( this.getMRT() );
		renderer.autoClear = false;

		const jitterOffsets = _JitterVectors[ Math.max( 0, Math.min( this.sampleLevel, 5 ) ) ];

		const baseSampleWeight = 1.0 / jitterOffsets.length;
		const roundingRange = 1 / 32;

		const viewOffset = {

			fullWidth: this.renderTarget.width,
			fullHeight: this.renderTarget.height,
			offsetX: 0,
			offsetY: 0,
			width: this.renderTarget.width,
			height: this.renderTarget.height

		};

		const originalViewOffset = Object.assign( {}, camera.view );

		if ( originalViewOffset.enabled ) Object.assign( viewOffset, originalViewOffset );

		// render the scene multiple times, each slightly jitter offset from the last and accumulate the results.

		for ( let i = 0; i < jitterOffsets.length; i ++ ) {

			const jitterOffset = jitterOffsets[ i ];

			if ( camera.setViewOffset ) {

				camera.setViewOffset(

					viewOffset.fullWidth, viewOffset.fullHeight,

					viewOffset.offsetX + jitterOffset[ 0 ] * 0.0625, viewOffset.offsetY + jitterOffset[ 1 ] * 0.0625, // 0.0625 = 1 / 16

					viewOffset.width, viewOffset.height

				);

			}

			this.sampleWeight.value = baseSampleWeight;

			if ( this.unbiased ) {

				// the theory is that equal weights for each sample lead to an accumulation of rounding errors.
				// The following equation varies the sampleWeight per sample so that it is uniformly distributed
				// across a range of values whose rounding errors cancel each other out.

				const uniformCenteredDistribution = ( - 0.5 + ( i + 0.5 ) / jitterOffsets.length );
				this.sampleWeight.value += roundingRange * uniformCenteredDistribution;

			}

			renderer.setClearColor( this.clearColor, this.clearAlpha );
			renderer.setRenderTarget( this._sampleRenderTarget );
			renderer.clear();
			renderer.render( scene, camera );

			// accumulation

			renderer.setRenderTarget( this.renderTarget );

			if ( i === 0 ) {

				renderer.setClearColor( 0x000000, 0.0 );
				renderer.clear();

			}

			this._quadMesh.render( renderer );

		}

		renderer.copyTextureToTexture( this._sampleRenderTarget.depthTexture, this.renderTarget.depthTexture );

		// restore

		if ( camera.setViewOffset && originalViewOffset.enabled ) {

			camera.setViewOffset(

				originalViewOffset.fullWidth, originalViewOffset.fullHeight,

				originalViewOffset.offsetX, originalViewOffset.offsetY,

				originalViewOffset.width, originalViewOffset.height

			);

		} else if ( camera.clearViewOffset ) {

			camera.clearViewOffset();

		}

		//

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

##### `setup(builder: NodeBuilder): PassTextureNode`

<details><summary>Code</summary>

```ts
setup( builder ) {

		if ( this._sampleRenderTarget === null ) {

			this._sampleRenderTarget = this.renderTarget.clone();

		}

		let sampleTexture;

		const passMRT = this.getMRT();

		if ( passMRT !== null ) {

			const outputs = {};

			for ( const name in passMRT.outputNodes ) {

				const index = getTextureIndex( this._sampleRenderTarget.textures, name );

				if ( index >= 0 ) {

					outputs[ name ] = texture( this._sampleRenderTarget.textures[ index ] ).mul( this.sampleWeight );

				}

			}

			sampleTexture = mrt( outputs );

		} else {

			sampleTexture = texture( this._sampleRenderTarget.texture ).mul( this.sampleWeight );

		}

		this._quadMesh.material = new NodeMaterial();
		this._quadMesh.material.fragmentNode = unpremultiplyAlpha( sampleTexture );
		this._quadMesh.material.transparent = true;
		this._quadMesh.material.depthTest = false;
		this._quadMesh.material.depthWrite = false;
		this._quadMesh.material.premultipliedAlpha = true;
		this._quadMesh.material.blending = AdditiveBlending;
		this._quadMesh.material.name = 'SSAA';

		return super.setup( builder );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		super.dispose();

		if ( this._sampleRenderTarget !== null ) {

			this._sampleRenderTarget.dispose();

		}

	}
```
</details>


---