[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `StereoPassNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/StereoPassNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `StereoCamera` | `three/webgpu` |
| `Vector2` | `three/webgpu` |
| `PassNode` | `three/webgpu` |
| `RendererUtils` | `three/webgpu` |
| `nodeObject` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_size` | `any` | let/var | `new Vector2()` | ✗ |
| `_rendererState` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `StereoPassNode.updateBefore(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
	 * This method is used to render the stereo effect once per frame.
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
- `stereo.update`
- `renderer.getSize`
- `this.setSize`
- `this.toggleTexture`
- `renderer.setRenderTarget`
- `renderer.setMRT`
- `renderer.clear`
- `renderTarget.scissor.set`
- `renderTarget.viewport.set`
- `renderer.render`
- `RendererUtils.restoreRendererState`

**Internal Comments:**
```
// (x4)
// restore (x4)
```

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		const { renderer } = frame;
		const { scene, camera, stereo, renderTarget } = this;

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		this._pixelRatio = renderer.getPixelRatio();

		stereo.cameraL.coordinateSystem = renderer.coordinateSystem;
		stereo.cameraR.coordinateSystem = renderer.coordinateSystem;
		stereo.update( camera );

		const size = renderer.getSize( _size );
		this.setSize( size.width, size.height );

		renderer.autoClear = false;

		this._cameraNear.value = camera.near;
		this._cameraFar.value = camera.far;

		for ( const name in this._previousTextures ) {

			this.toggleTexture( name );

		}

		renderer.setRenderTarget( renderTarget );
		renderer.setMRT( this._mrt );
		renderer.clear();

		renderTarget.scissorTest = true;

		renderTarget.scissor.set( 0, 0, renderTarget.width / 2, renderTarget.height );
		renderTarget.viewport.set( 0, 0, renderTarget.width / 2, renderTarget.height );
		renderer.render( scene, stereo.cameraL );

		renderTarget.scissor.set( renderTarget.width / 2, 0, renderTarget.width / 2, renderTarget.height );
		renderTarget.viewport.set( renderTarget.width / 2, 0, renderTarget.width / 2, renderTarget.height );
		renderer.render( scene, stereo.cameraR );

		renderTarget.scissorTest = false;

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>

### `stereoPass(scene: Scene, camera: Camera): StereoPassNode`

**Parameters:**

- **`scene`** `Scene`
- **`camera`** `Camera`

**Returns:** `StereoPassNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( scene, camera ) => nodeObject( new StereoPassNode( scene, camera ) )
```
</details>


---

## Classes

### `StereoPassNode`

<details><summary>Class Code</summary>

```ts
class StereoPassNode extends PassNode {

	static get type() {

		return 'StereoPassNode';

	}

	/**
	 * Constructs a new stereo pass node.
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
		this.isStereoPassNode = true;

		/**
		 * The internal stereo camera that is used to render the scene.
		 *
		 * @type {StereoCamera}
		 */
		this.stereo = new StereoCamera();
		this.stereo.aspect = 0.5;

	}

	/**
	 * This method is used to render the stereo effect once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
	updateBefore( frame ) {

		const { renderer } = frame;
		const { scene, camera, stereo, renderTarget } = this;

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		this._pixelRatio = renderer.getPixelRatio();

		stereo.cameraL.coordinateSystem = renderer.coordinateSystem;
		stereo.cameraR.coordinateSystem = renderer.coordinateSystem;
		stereo.update( camera );

		const size = renderer.getSize( _size );
		this.setSize( size.width, size.height );

		renderer.autoClear = false;

		this._cameraNear.value = camera.near;
		this._cameraFar.value = camera.far;

		for ( const name in this._previousTextures ) {

			this.toggleTexture( name );

		}

		renderer.setRenderTarget( renderTarget );
		renderer.setMRT( this._mrt );
		renderer.clear();

		renderTarget.scissorTest = true;

		renderTarget.scissor.set( 0, 0, renderTarget.width / 2, renderTarget.height );
		renderTarget.viewport.set( 0, 0, renderTarget.width / 2, renderTarget.height );
		renderer.render( scene, stereo.cameraL );

		renderTarget.scissor.set( renderTarget.width / 2, 0, renderTarget.width / 2, renderTarget.height );
		renderTarget.viewport.set( renderTarget.width / 2, 0, renderTarget.width / 2, renderTarget.height );
		renderer.render( scene, stereo.cameraR );

		renderTarget.scissorTest = false;

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

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
		const { scene, camera, stereo, renderTarget } = this;

		_rendererState = RendererUtils.resetRendererState( renderer, _rendererState );

		//

		this._pixelRatio = renderer.getPixelRatio();

		stereo.cameraL.coordinateSystem = renderer.coordinateSystem;
		stereo.cameraR.coordinateSystem = renderer.coordinateSystem;
		stereo.update( camera );

		const size = renderer.getSize( _size );
		this.setSize( size.width, size.height );

		renderer.autoClear = false;

		this._cameraNear.value = camera.near;
		this._cameraFar.value = camera.far;

		for ( const name in this._previousTextures ) {

			this.toggleTexture( name );

		}

		renderer.setRenderTarget( renderTarget );
		renderer.setMRT( this._mrt );
		renderer.clear();

		renderTarget.scissorTest = true;

		renderTarget.scissor.set( 0, 0, renderTarget.width / 2, renderTarget.height );
		renderTarget.viewport.set( 0, 0, renderTarget.width / 2, renderTarget.height );
		renderer.render( scene, stereo.cameraL );

		renderTarget.scissor.set( renderTarget.width / 2, 0, renderTarget.width / 2, renderTarget.height );
		renderTarget.viewport.set( renderTarget.width / 2, 0, renderTarget.width / 2, renderTarget.height );
		renderer.render( scene, stereo.cameraR );

		renderTarget.scissorTest = false;

		// restore

		RendererUtils.restoreRendererState( renderer, _rendererState );

	}
```
</details>


---