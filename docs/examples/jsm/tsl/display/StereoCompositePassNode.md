[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `StereoCompositePassNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/StereoCompositePassNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `RenderTarget` | `three/webgpu` |
| `StereoCamera` | `three/webgpu` |
| `HalfFloatType` | `three/webgpu` |
| `LinearFilter` | `three/webgpu` |
| `NearestFilter` | `three/webgpu` |
| `Vector2` | `three/webgpu` |
| `PassNode` | `three/webgpu` |
| `QuadMesh` | `three/webgpu` |
| `RendererUtils` | `three/webgpu` |
| `texture` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_size` | `any` | let/var | `new Vector2()` | ✗ |
| `_quadMesh` | `any` | let/var | `new QuadMesh()` | ✗ |
| `_rendererState` | `any` | let/var | `*not shown*` | ✗ |
| `_params` | `{ minFilter: any; magFilter: any; typ...` | let/var | `{ minFilter: LinearFilter, magFilter: NearestFilter, type: HalfFloatType }` | ✗ |


---

## Functions

### `StereoCompositePassNode.updateStereoCamera(coordinateSystem: number): void`

**JSDoc:**
```typescript
/**
	 * Updates the internal stereo camera.
	 *
	 * @param {number} coordinateSystem - The current coordinate system.
	 */
```

**Parameters:**

- **`coordinateSystem`** `number`

**Returns:** `void`

**Calls:**

- `this.stereo.update`

<details><summary>Code</summary>

```typescript
updateStereoCamera( coordinateSystem ) {

		this.stereo.cameraL.coordinateSystem = coordinateSystem;
		this.stereo.cameraR.coordinateSystem = coordinateSystem;
		this.stereo.update( this.camera );

	}
```
</details>

### `StereoCompositePassNode.setSize(width: number, height: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the size of the pass.
	 *
	 * @param {number} width - The width of the pass.
	 * @param {number} height - The height of the pass.
	 */
```

**Parameters:**

- **`width`** `number`
- **`height`** `number`

**Returns:** `void`

**Calls:**

- `super.setSize`
- `this._renderTargetL.setSize`
- `this._renderTargetR.setSize`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		super.setSize( width, height );

		this._renderTargetL.setSize( this.renderTarget.width, this.renderTarget.height );
		this._renderTargetR.setSize( this.renderTarget.width, this.renderTarget.height );

	}
```
</details>

### `StereoCompositePassNode.updateBefore(frame: NodeFrame): void`

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
- `renderer.getPixelRatio`
- `this.updateStereoCamera`
- `renderer.getSize`
- `this.setSize`
- `renderer.setRenderTarget`
- `renderer.render`
- `_quadMesh.render`
- `RendererUtils.restoreRendererState`

**Internal Comments:**
```
// (x4)
// left (x4)
// right (x4)
// composite (x4)
// restore (x4)
```

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		const { renderer } = frame;
		const { scene, stereo, renderTarget } = this;

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		this._pixelRatio = renderer.getPixelRatio();

		this.updateStereoCamera( renderer.coordinateSystem );

		const size = renderer.getSize( _size );
		this.setSize( size.width, size.height );

		// left

		renderer.setRenderTarget( this._renderTargetL );
		renderer.render( scene, stereo.cameraL );

		// right

		renderer.setRenderTarget( this._renderTargetR );
		renderer.render( scene, stereo.cameraR );

		// composite

		renderer.setRenderTarget( renderTarget );
		_quadMesh.material = this._material;
		_quadMesh.render( renderer );

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

### `StereoCompositePassNode.dispose(): void`

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
- `this._renderTargetL.dispose`
- `this._renderTargetR.dispose`
- `this._material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		super.dispose();

		this._renderTargetL.dispose();
		this._renderTargetR.dispose();

		if ( this._material !== null ) {

			this._material.dispose();

		}

	}
```
</details>


---

## Classes

### `StereoCompositePassNode`

<details><summary>Class Code</summary>

```ts
class StereoCompositePassNode extends PassNode {

	static get type() {

		return 'StereoCompositePassNode';

	}

	/**
	 * Constructs a new stereo composite pass node.
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
		this.isStereoCompositePassNode = true;

		/**
		 * The internal stereo camera that is used to render the scene.
		 *
		 * @type {StereoCamera}
		 */
		this.stereo = new StereoCamera();
		const _params = { minFilter: LinearFilter, magFilter: NearestFilter, type: HalfFloatType };

		/**
		 * The render target for rendering the left eye's view.
		 *
		 * @type {RenderTarget}
		 */
		this._renderTargetL = new RenderTarget( 1, 1, _params );

		/**
		 * The render target for rendering the right eye's view.
		 *
		 * @type {RenderTarget}
		 */
		this._renderTargetR = new RenderTarget( 1, 1, _params );

		/**
		 * A texture node representing the left's eye view.
		 *
		 * @type {TextureNode}
		 */
		this._mapLeft = texture( this._renderTargetL.texture );

		/**
		 * A texture node representing the right's eye view.
		 *
		 * @type {TextureNode}
		 */
		this._mapRight = texture( this._renderTargetR.texture );

		/**
		 * The node material that implements the composite. All
		 * derived effect passes must provide an instance for rendering.
		 *
		 * @type {NodeMaterial}
		 */
		this._material = null;

	}

	/**
	 * Updates the internal stereo camera.
	 *
	 * @param {number} coordinateSystem - The current coordinate system.
	 */
	updateStereoCamera( coordinateSystem ) {

		this.stereo.cameraL.coordinateSystem = coordinateSystem;
		this.stereo.cameraR.coordinateSystem = coordinateSystem;
		this.stereo.update( this.camera );

	}

	/**
	 * Sets the size of the pass.
	 *
	 * @param {number} width - The width of the pass.
	 * @param {number} height - The height of the pass.
	 */
	setSize( width, height ) {

		super.setSize( width, height );

		this._renderTargetL.setSize( this.renderTarget.width, this.renderTarget.height );
		this._renderTargetR.setSize( this.renderTarget.width, this.renderTarget.height );

	}

	/**
	 * This method is used to render the effect once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
	updateBefore( frame ) {

		const { renderer } = frame;
		const { scene, stereo, renderTarget } = this;

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		this._pixelRatio = renderer.getPixelRatio();

		this.updateStereoCamera( renderer.coordinateSystem );

		const size = renderer.getSize( _size );
		this.setSize( size.width, size.height );

		// left

		renderer.setRenderTarget( this._renderTargetL );
		renderer.render( scene, stereo.cameraL );

		// right

		renderer.setRenderTarget( this._renderTargetR );
		renderer.render( scene, stereo.cameraR );

		// composite

		renderer.setRenderTarget( renderTarget );
		_quadMesh.material = this._material;
		_quadMesh.render( renderer );

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}

	/**
	 * Frees internal resources. This method should be called
	 * when the pass is no longer required.
	 */
	dispose() {

		super.dispose();

		this._renderTargetL.dispose();
		this._renderTargetR.dispose();

		if ( this._material !== null ) {

			this._material.dispose();

		}

	}

}
```
</details>

#### Methods

##### `updateStereoCamera(coordinateSystem: number): void`

<details><summary>Code</summary>

```ts
updateStereoCamera( coordinateSystem ) {

		this.stereo.cameraL.coordinateSystem = coordinateSystem;
		this.stereo.cameraR.coordinateSystem = coordinateSystem;
		this.stereo.update( this.camera );

	}
```
</details>

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		super.setSize( width, height );

		this._renderTargetL.setSize( this.renderTarget.width, this.renderTarget.height );
		this._renderTargetR.setSize( this.renderTarget.width, this.renderTarget.height );

	}
```
</details>

##### `updateBefore(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		const { renderer } = frame;
		const { scene, stereo, renderTarget } = this;

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		this._pixelRatio = renderer.getPixelRatio();

		this.updateStereoCamera( renderer.coordinateSystem );

		const size = renderer.getSize( _size );
		this.setSize( size.width, size.height );

		// left

		renderer.setRenderTarget( this._renderTargetL );
		renderer.render( scene, stereo.cameraL );

		// right

		renderer.setRenderTarget( this._renderTargetR );
		renderer.render( scene, stereo.cameraR );

		// composite

		renderer.setRenderTarget( renderTarget );
		_quadMesh.material = this._material;
		_quadMesh.render( renderer );

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		super.dispose();

		this._renderTargetL.dispose();
		this._renderTargetR.dispose();

		if ( this._material !== null ) {

			this._material.dispose();

		}

	}
```
</details>


---