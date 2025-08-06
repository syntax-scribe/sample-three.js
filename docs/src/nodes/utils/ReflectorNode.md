[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ReflectorNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 11 |
| 🧱 Classes | 2 |
| 📦 Imports | 16 |
| 📊 Variables & Constants | 20 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/utils/ReflectorNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `TextureNode` | `../accessors/TextureNode.js` |
| `nodeObject` | `../tsl/TSLBase.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `screenUV` | `../display/ScreenNode.js` |
| `HalfFloatType` | `../../constants.js` |
| `LinearMipMapLinearFilter` | `../../constants.js` |
| `WebGPUCoordinateSystem` | `../../constants.js` |
| `Plane` | `../../math/Plane.js` |
| `Object3D` | `../../core/Object3D.js` |
| `Vector2` | `../../math/Vector2.js` |
| `Vector3` | `../../math/Vector3.js` |
| `Vector4` | `../../math/Vector4.js` |
| `Matrix4` | `../../math/Matrix4.js` |
| `RenderTarget` | `../../core/RenderTarget.js` |
| `DepthTexture` | `../../textures/DepthTexture.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_reflectorPlane` | `Plane` | let/var | `new Plane()` | ✗ |
| `_normal` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_reflectorWorldPosition` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_cameraWorldPosition` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_rotationMatrix` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_lookAtPosition` | `Vector3` | let/var | `new Vector3( 0, 0, - 1 )` | ✗ |
| `clipPlane` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `_view` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_target` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_q` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `_size` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `_defaultRT` | `RenderTarget` | let/var | `new RenderTarget()` | ✗ |
| `_inReflector` | `boolean` | let/var | `false` | ✗ |
| `newNode` | `any` | let/var | `new this.constructor( this.reflectorNode )` | ✗ |
| `resolution` | `number` | let/var | `this.resolution` | ✗ |
| `isFacingAway` | `boolean` | let/var | `_view.dot( _normal ) > 0` | ✗ |
| `needsClear` | `boolean` | let/var | `false` | ✗ |
| `projectionMatrix` | `any` | let/var | `virtualCamera.projectionMatrix` | ✗ |
| `clipBias` | `0` | let/var | `0` | ✗ |
| `currentAutoClear` | `any` | let/var | `renderer.autoClear` | ✗ |


---

## Functions

### `ReflectorNode.getDepthNode(): Node`

**JSDoc:**
```typescript
/**
	 * Returns a node representing the mirror's depth. That can be used
	 * to implement more advanced reflection effects like distance attenuation.
	 *
	 * @return {Node} The depth node.
	 */
```

**Returns:** `Node`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
getDepthNode() {

		if ( this._depthNode === null ) {

			if ( this._reflectorBaseNode.depth !== true ) {

				throw new Error( 'THREE.ReflectorNode: Depth node can only be requested when the reflector is created with { depth: true }. ' );

			}

			this._depthNode = nodeObject( new ReflectorNode( {
				defaultTexture: _defaultRT.depthTexture,
				reflector: this._reflectorBaseNode
			} ) );

		}

		return this._depthNode;

	}
```
</details>

### `ReflectorNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `this._reflectorBaseNode.build`
- `super.setup`

**Internal Comments:**
```
// ignore if used in post-processing
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		// ignore if used in post-processing
		if ( ! builder.object.isQuadMesh ) this._reflectorBaseNode.build( builder );

		return super.setup( builder );

	}
```
</details>

### `ReflectorNode.clone(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
clone() {

		const newNode = new this.constructor( this.reflectorNode );
		newNode.uvNode = this.uvNode;
		newNode.levelNode = this.levelNode;
		newNode.biasNode = this.biasNode;
		newNode.sampler = this.sampler;
		newNode.depthNode = this.depthNode;
		newNode.compareNode = this.compareNode;
		newNode.gradNode = this.gradNode;
		newNode._reflectorBaseNode = this._reflectorBaseNode;

		return newNode;

	}
```
</details>

### `ReflectorNode.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources. Should be called when the node is no longer in use.
	 */
```

**Returns:** `void`

**Calls:**

- `super.dispose`
- `this._reflectorBaseNode.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		super.dispose();

		this._reflectorBaseNode.dispose();

	}
```
</details>

### `ReflectorBaseNode._updateResolution(renderTarget: RenderTarget, renderer: Renderer): void`

**JSDoc:**
```typescript
/**
	 * Updates the resolution of the internal render target.
	 *
	 * @private
	 * @param {RenderTarget} renderTarget - The render target to resize.
	 * @param {Renderer} renderer - The renderer that is used to determine the new size.
	 */
```

**Parameters:**

- **`renderTarget`** `RenderTarget`
- **`renderer`** `Renderer`

**Returns:** `void`

**Calls:**

- `renderer.getDrawingBufferSize`
- `renderTarget.setSize`
- `Math.round`

<details><summary>Code</summary>

```typescript
_updateResolution( renderTarget, renderer ) {

		const resolution = this.resolution;

		renderer.getDrawingBufferSize( _size );

		renderTarget.setSize( Math.round( _size.width * resolution ), Math.round( _size.height * resolution ) );

	}
```
</details>

### `ReflectorBaseNode.setup(builder: any): Node`

**Parameters:**

- **`builder`** `any`

**Returns:** `Node`

**Calls:**

- `this._updateResolution`
- `super.setup`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		this._updateResolution( _defaultRT, builder.renderer );

		return super.setup( builder );

	}
```
</details>

### `ReflectorBaseNode.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources. Should be called when the node is no longer in use.
	 */
```

**Returns:** `void`

**Calls:**

- `super.dispose`
- `this.renderTargets.values`
- `renderTarget.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		super.dispose();

		for ( const renderTarget of this.renderTargets.values() ) {

			renderTarget.dispose();

		}

	}
```
</details>

### `ReflectorBaseNode.getVirtualCamera(camera: Camera): Camera`

**JSDoc:**
```typescript
/**
	 * Returns a virtual camera for the given camera. The virtual camera is used to
	 * render the scene from the reflector's view so correct reflections can be produced.
	 *
	 * @param {Camera} camera - The scene's camera.
	 * @return {Camera} The corresponding virtual camera.
	 */
```

**Parameters:**

- **`camera`** `Camera`

**Returns:** `Camera`

**Calls:**

- `this.virtualCameras.get`
- `camera.clone`
- `this.virtualCameras.set`

<details><summary>Code</summary>

```typescript
getVirtualCamera( camera ) {

		let virtualCamera = this.virtualCameras.get( camera );

		if ( virtualCamera === undefined ) {

			virtualCamera = camera.clone();

			this.virtualCameras.set( camera, virtualCamera );

		}

		return virtualCamera;

	}
```
</details>

### `ReflectorBaseNode.getRenderTarget(camera: Camera): RenderTarget`

**JSDoc:**
```typescript
/**
	 * Returns a render target for the given camera. The reflections are rendered
	 * into this render target.
	 *
	 * @param {Camera} camera - The scene's camera.
	 * @return {RenderTarget} The render target.
	 */
```

**Parameters:**

- **`camera`** `Camera`

**Returns:** `RenderTarget`

**Calls:**

- `this.renderTargets.get`
- `this.renderTargets.set`

<details><summary>Code</summary>

```typescript
getRenderTarget( camera ) {

		let renderTarget = this.renderTargets.get( camera );

		if ( renderTarget === undefined ) {

			renderTarget = new RenderTarget( 0, 0, { type: HalfFloatType, samples: this.samples } );

			if ( this.generateMipmaps === true ) {

				renderTarget.texture.minFilter = LinearMipMapLinearFilter;
				renderTarget.texture.generateMipmaps = true;

			}

			if ( this.depth === true ) {

				renderTarget.depthTexture = new DepthTexture();

			}

			this.renderTargets.set( camera, renderTarget );

		}

		return renderTarget;

	}
```
</details>

### `ReflectorBaseNode.updateBefore(frame: any): boolean`

**Parameters:**

- **`frame`** `any`

**Returns:** `boolean`

**Calls:**

- `this.getVirtualCamera`
- `this.getRenderTarget`
- `renderer.getDrawingBufferSize`
- `this._updateResolution`
- `_reflectorWorldPosition.setFromMatrixPosition`
- `_cameraWorldPosition.setFromMatrixPosition`
- `_rotationMatrix.extractRotation`
- `_normal.set`
- `_normal.applyMatrix4`
- `_view.subVectors`
- `_view.dot`
- `_view.reflect( _normal ).negate`
- `_view.add`
- `_lookAtPosition.set`
- `_lookAtPosition.applyMatrix4`
- `_lookAtPosition.add`
- `_target.subVectors`
- `_target.reflect( _normal ).negate`
- `_target.add`
- `virtualCamera.position.copy`
- `virtualCamera.up.set`
- `virtualCamera.up.applyMatrix4`
- `virtualCamera.up.reflect`
- `virtualCamera.lookAt`
- `virtualCamera.updateMatrixWorld`
- `virtualCamera.projectionMatrix.copy`
- `_reflectorPlane.setFromNormalAndCoplanarPoint`
- `_reflectorPlane.applyMatrix4`
- `clipPlane.set`
- `Math.sign`
- `clipPlane.multiplyScalar`
- `clipPlane.dot`
- `this.textureNode.getDepthNode`
- `renderer.getRenderTarget`
- `renderer.getMRT`
- `renderer.setMRT`
- `renderer.setRenderTarget`
- `renderer.clear`
- `renderer.render`

**Internal Comments:**
```
// (x13)
// Avoid rendering when reflector is facing away unless forcing an update (x2)
// Now update projection matrix with new clip plane, implementing code from: http://www.terathon.com/code/oblique.html (x4)
// Paper explaining this technique: http://www.terathon.com/lengyel/Lengyel-Oblique.pdf (x4)
// Calculate the scaled plane vector (x4)
// Replacing the third row of the projection matrix (x5)
```

<details><summary>Code</summary>

```typescript
updateBefore( frame ) {

		if ( this.bounces === false && _inReflector ) return false;

		_inReflector = true;

		const { scene, camera, renderer, material } = frame;
		const { target } = this;

		const virtualCamera = this.getVirtualCamera( camera );
		const renderTarget = this.getRenderTarget( virtualCamera );

		renderer.getDrawingBufferSize( _size );

		this._updateResolution( renderTarget, renderer );

		//

		_reflectorWorldPosition.setFromMatrixPosition( target.matrixWorld );
		_cameraWorldPosition.setFromMatrixPosition( camera.matrixWorld );

		_rotationMatrix.extractRotation( target.matrixWorld );

		_normal.set( 0, 0, 1 );
		_normal.applyMatrix4( _rotationMatrix );

		_view.subVectors( _reflectorWorldPosition, _cameraWorldPosition );

		// Avoid rendering when reflector is facing away unless forcing an update
		const isFacingAway = _view.dot( _normal ) > 0;

		let needsClear = false;

		if ( isFacingAway === true && this.forceUpdate === false ) {

			if ( this.hasOutput === false ) {

				_inReflector = false;

				return;

			}

			needsClear = true;

		}

		_view.reflect( _normal ).negate();
		_view.add( _reflectorWorldPosition );

		_rotationMatrix.extractRotation( camera.matrixWorld );

		_lookAtPosition.set( 0, 0, - 1 );
		_lookAtPosition.applyMatrix4( _rotationMatrix );
		_lookAtPosition.add( _cameraWorldPosition );

		_target.subVectors( _reflectorWorldPosition, _lookAtPosition );
		_target.reflect( _normal ).negate();
		_target.add( _reflectorWorldPosition );

		//

		virtualCamera.coordinateSystem = camera.coordinateSystem;
		virtualCamera.position.copy( _view );
		virtualCamera.up.set( 0, 1, 0 );
		virtualCamera.up.applyMatrix4( _rotationMatrix );
		virtualCamera.up.reflect( _normal );
		virtualCamera.lookAt( _target );

		virtualCamera.near = camera.near;
		virtualCamera.far = camera.far;

		virtualCamera.updateMatrixWorld();
		virtualCamera.projectionMatrix.copy( camera.projectionMatrix );

		// Now update projection matrix with new clip plane, implementing code from: http://www.terathon.com/code/oblique.html
		// Paper explaining this technique: http://www.terathon.com/lengyel/Lengyel-Oblique.pdf
		_reflectorPlane.setFromNormalAndCoplanarPoint( _normal, _reflectorWorldPosition );
		_reflectorPlane.applyMatrix4( virtualCamera.matrixWorldInverse );

		clipPlane.set( _reflectorPlane.normal.x, _reflectorPlane.normal.y, _reflectorPlane.normal.z, _reflectorPlane.constant );

		const projectionMatrix = virtualCamera.projectionMatrix;

		_q.x = ( Math.sign( clipPlane.x ) + projectionMatrix.elements[ 8 ] ) / projectionMatrix.elements[ 0 ];
		_q.y = ( Math.sign( clipPlane.y ) + projectionMatrix.elements[ 9 ] ) / projectionMatrix.elements[ 5 ];
		_q.z = - 1.0;
		_q.w = ( 1.0 + projectionMatrix.elements[ 10 ] ) / projectionMatrix.elements[ 14 ];

		// Calculate the scaled plane vector
		clipPlane.multiplyScalar( 1.0 / clipPlane.dot( _q ) );

		const clipBias = 0;

		// Replacing the third row of the projection matrix
		projectionMatrix.elements[ 2 ] = clipPlane.x;
		projectionMatrix.elements[ 6 ] = clipPlane.y;
		projectionMatrix.elements[ 10 ] = ( renderer.coordinateSystem === WebGPUCoordinateSystem ) ? ( clipPlane.z - clipBias ) : ( clipPlane.z + 1.0 - clipBias );
		projectionMatrix.elements[ 14 ] = clipPlane.w;

		//

		this.textureNode.value = renderTarget.texture;

		if ( this.depth === true ) {

			this.textureNode.getDepthNode().value = renderTarget.depthTexture;

		}

		material.visible = false;

		const currentRenderTarget = renderer.getRenderTarget();
		const currentMRT = renderer.getMRT();
		const currentAutoClear = renderer.autoClear;

		renderer.setMRT( null );
		renderer.setRenderTarget( renderTarget );
		renderer.autoClear = true;

		if ( needsClear ) {

			renderer.clear();

			this.hasOutput = false;

		} else {

			renderer.render( scene, virtualCamera );

			this.hasOutput = true;

		}

		renderer.setMRT( currentMRT );
		renderer.setRenderTarget( currentRenderTarget );
		renderer.autoClear = currentAutoClear;

		material.visible = true;

		_inReflector = false;

		this.forceUpdate = false;

	}
```
</details>

### `reflector(parameters: { target?: Object3D; resolution?: number; generateMipmaps?: boolean; bounces?: boolean; depth?: boolean; samples?: number; defaultTexture?: TextureNode; reflector?: ReflectorBaseNode; }): ReflectorNode`

**Parameters:**

- **`parameters`** `{ target?: Object3D; resolution?: number; generateMipmaps?: boolean; bounces?: boolean; depth?: boolean; samples?: number; defaultTexture?: TextureNode; reflector?: ReflectorBaseNode; }`

**Returns:** `ReflectorNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( parameters ) => nodeObject( new ReflectorNode( parameters ) )
```
</details>


---

## Classes

### `ReflectorNode`

<details><summary>Class Code</summary>

```ts
class ReflectorNode extends TextureNode {

	static get type() {

		return 'ReflectorNode';

	}

	/**
	 * Constructs a new reflector node.
	 *
	 * @param {Object} [parameters={}] - An object holding configuration parameters.
	 * @param {Object3D} [parameters.target=new Object3D()] - The 3D object the reflector is linked to.
	 * @param {number} [parameters.resolution=1] - The resolution scale.
	 * @param {boolean} [parameters.generateMipmaps=false] - Whether mipmaps should be generated or not.
	 * @param {boolean} [parameters.bounces=true] - Whether reflectors can render other reflector nodes or not.
	 * @param {boolean} [parameters.depth=false] - Whether depth data should be generated or not.
	 * @param {number} [parameters.samples] - Anti-Aliasing samples of the internal render-target.
	 * @param {TextureNode} [parameters.defaultTexture] - The default texture node.
	 * @param {ReflectorBaseNode} [parameters.reflector] - The reflector base node.
	 */
	constructor( parameters = {} ) {

		super( parameters.defaultTexture || _defaultRT.texture, _defaultUV );

		/**
		 * A reference to the internal reflector base node which holds the actual implementation.
		 *
		 * @private
		 * @type {ReflectorBaseNode}
		 * @default ReflectorBaseNode
		 */
		this._reflectorBaseNode = parameters.reflector || new ReflectorBaseNode( this, parameters );

		/**
		 * A reference to the internal depth node.
		 *
		 * @private
		 * @type {?Node}
		 * @default null
		 */
		this._depthNode = null;

		this.setUpdateMatrix( false );

	}

	/**
	 * A reference to the internal reflector node.
	 *
	 * @type {ReflectorBaseNode}
	 */
	get reflector() {

		return this._reflectorBaseNode;

	}

	/**
	 * A reference to 3D object the reflector is linked to.
	 *
	 * @type {Object3D}
	 */
	get target() {

		return this._reflectorBaseNode.target;

	}

	/**
	 * Returns a node representing the mirror's depth. That can be used
	 * to implement more advanced reflection effects like distance attenuation.
	 *
	 * @return {Node} The depth node.
	 */
	getDepthNode() {

		if ( this._depthNode === null ) {

			if ( this._reflectorBaseNode.depth !== true ) {

				throw new Error( 'THREE.ReflectorNode: Depth node can only be requested when the reflector is created with { depth: true }. ' );

			}

			this._depthNode = nodeObject( new ReflectorNode( {
				defaultTexture: _defaultRT.depthTexture,
				reflector: this._reflectorBaseNode
			} ) );

		}

		return this._depthNode;

	}

	setup( builder ) {

		// ignore if used in post-processing
		if ( ! builder.object.isQuadMesh ) this._reflectorBaseNode.build( builder );

		return super.setup( builder );

	}

	clone() {

		const newNode = new this.constructor( this.reflectorNode );
		newNode.uvNode = this.uvNode;
		newNode.levelNode = this.levelNode;
		newNode.biasNode = this.biasNode;
		newNode.sampler = this.sampler;
		newNode.depthNode = this.depthNode;
		newNode.compareNode = this.compareNode;
		newNode.gradNode = this.gradNode;
		newNode._reflectorBaseNode = this._reflectorBaseNode;

		return newNode;

	}

	/**
	 * Frees internal resources. Should be called when the node is no longer in use.
	 */
	dispose() {

		super.dispose();

		this._reflectorBaseNode.dispose();

	}

}
```
</details>

#### Methods

##### `getDepthNode(): Node`

<details><summary>Code</summary>

```ts
getDepthNode() {

		if ( this._depthNode === null ) {

			if ( this._reflectorBaseNode.depth !== true ) {

				throw new Error( 'THREE.ReflectorNode: Depth node can only be requested when the reflector is created with { depth: true }. ' );

			}

			this._depthNode = nodeObject( new ReflectorNode( {
				defaultTexture: _defaultRT.depthTexture,
				reflector: this._reflectorBaseNode
			} ) );

		}

		return this._depthNode;

	}
```
</details>

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		// ignore if used in post-processing
		if ( ! builder.object.isQuadMesh ) this._reflectorBaseNode.build( builder );

		return super.setup( builder );

	}
```
</details>

##### `clone(): any`

<details><summary>Code</summary>

```ts
clone() {

		const newNode = new this.constructor( this.reflectorNode );
		newNode.uvNode = this.uvNode;
		newNode.levelNode = this.levelNode;
		newNode.biasNode = this.biasNode;
		newNode.sampler = this.sampler;
		newNode.depthNode = this.depthNode;
		newNode.compareNode = this.compareNode;
		newNode.gradNode = this.gradNode;
		newNode._reflectorBaseNode = this._reflectorBaseNode;

		return newNode;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		super.dispose();

		this._reflectorBaseNode.dispose();

	}
```
</details>

### `ReflectorBaseNode`

<details><summary>Class Code</summary>

```ts
class ReflectorBaseNode extends Node {

	static get type() {

		return 'ReflectorBaseNode';

	}

	/**
	 * Constructs a new reflector base node.
	 *
	 * @param {TextureNode} textureNode - Represents the rendered reflections as a texture node.
	 * @param {Object} [parameters={}] - An object holding configuration parameters.
	 * @param {Object3D} [parameters.target=new Object3D()] - The 3D object the reflector is linked to.
	 * @param {number} [parameters.resolution=1] - The resolution scale.
	 * @param {boolean} [parameters.generateMipmaps=false] - Whether mipmaps should be generated or not.
	 * @param {boolean} [parameters.bounces=true] - Whether reflectors can render other reflector nodes or not.
	 * @param {boolean} [parameters.depth=false] - Whether depth data should be generated or not.
	 * @param {number} [parameters.samples] - Anti-Aliasing samples of the internal render-target.
	 */
	constructor( textureNode, parameters = {} ) {

		super();

		const {
			target = new Object3D(),
			resolution = 1,
			generateMipmaps = false,
			bounces = true,
			depth = false,
			samples = 0
		} = parameters;

		/**
		 * Represents the rendered reflections as a texture node.
		 *
		 * @type {TextureNode}
		 */
		this.textureNode = textureNode;

		/**
		 * The 3D object the reflector is linked to.
		 *
		 * @type {Object3D}
		 * @default {new Object3D()}
		 */
		this.target = target;

		/**
		 * The resolution scale.
		 *
		 * @type {number}
		 * @default {1}
		 */
		this.resolution = resolution;

		/**
		 * Whether mipmaps should be generated or not.
		 *
		 * @type {boolean}
		 * @default {false}
		 */
		this.generateMipmaps = generateMipmaps;

		/**
		 * Whether reflectors can render other reflector nodes or not.
		 *
		 * @type {boolean}
		 * @default {true}
		 */
		this.bounces = bounces;

		/**
		 * Whether depth data should be generated or not.
		 *
		 * @type {boolean}
		 * @default {false}
		 */
		this.depth = depth;

		/**
		 * The number of anti-aliasing samples for the render-target
		 *
		 * @type {number}
		 * @default {0}
		 */
		this.samples = samples;

		/**
		 * The `updateBeforeType` is set to `NodeUpdateType.RENDER` when {@link ReflectorBaseNode#bounces}
		 * is `true`. Otherwise it's `NodeUpdateType.FRAME`.
		 *
		 * @type {string}
		 * @default 'render'
		 */
		this.updateBeforeType = bounces ? NodeUpdateType.RENDER : NodeUpdateType.FRAME;

		/**
		 * Weak map for managing virtual cameras.
		 *
		 * @type {WeakMap<Camera, Camera>}
		 */
		this.virtualCameras = new WeakMap();

		/**
		 * Weak map for managing render targets.
		 *
		 * @type {Map<Camera, RenderTarget>}
		 */
		this.renderTargets = new Map();

		/**
		 * Force render even if reflector is facing away from camera.
		 *
		 * @type {boolean}
		 * @default {false}
		 */
		this.forceUpdate = false;

		/**
		 * Whether the reflector has been rendered or not.
		 *
		 * When the reflector is facing away from the camera,
		 * this flag is set to `false` and the texture will be empty(black).
		 *
		 * @type {boolean}
		 * @default {false}
		 */
		this.hasOutput = false;

	}

	/**
	 * Updates the resolution of the internal render target.
	 *
	 * @private
	 * @param {RenderTarget} renderTarget - The render target to resize.
	 * @param {Renderer} renderer - The renderer that is used to determine the new size.
	 */
	_updateResolution( renderTarget, renderer ) {

		const resolution = this.resolution;

		renderer.getDrawingBufferSize( _size );

		renderTarget.setSize( Math.round( _size.width * resolution ), Math.round( _size.height * resolution ) );

	}

	setup( builder ) {

		this._updateResolution( _defaultRT, builder.renderer );

		return super.setup( builder );

	}

	/**
	 * Frees internal resources. Should be called when the node is no longer in use.
	 */
	dispose() {

		super.dispose();

		for ( const renderTarget of this.renderTargets.values() ) {

			renderTarget.dispose();

		}

	}

	/**
	 * Returns a virtual camera for the given camera. The virtual camera is used to
	 * render the scene from the reflector's view so correct reflections can be produced.
	 *
	 * @param {Camera} camera - The scene's camera.
	 * @return {Camera} The corresponding virtual camera.
	 */
	getVirtualCamera( camera ) {

		let virtualCamera = this.virtualCameras.get( camera );

		if ( virtualCamera === undefined ) {

			virtualCamera = camera.clone();

			this.virtualCameras.set( camera, virtualCamera );

		}

		return virtualCamera;

	}

	/**
	 * Returns a render target for the given camera. The reflections are rendered
	 * into this render target.
	 *
	 * @param {Camera} camera - The scene's camera.
	 * @return {RenderTarget} The render target.
	 */
	getRenderTarget( camera ) {

		let renderTarget = this.renderTargets.get( camera );

		if ( renderTarget === undefined ) {

			renderTarget = new RenderTarget( 0, 0, { type: HalfFloatType, samples: this.samples } );

			if ( this.generateMipmaps === true ) {

				renderTarget.texture.minFilter = LinearMipMapLinearFilter;
				renderTarget.texture.generateMipmaps = true;

			}

			if ( this.depth === true ) {

				renderTarget.depthTexture = new DepthTexture();

			}

			this.renderTargets.set( camera, renderTarget );

		}

		return renderTarget;

	}

	updateBefore( frame ) {

		if ( this.bounces === false && _inReflector ) return false;

		_inReflector = true;

		const { scene, camera, renderer, material } = frame;
		const { target } = this;

		const virtualCamera = this.getVirtualCamera( camera );
		const renderTarget = this.getRenderTarget( virtualCamera );

		renderer.getDrawingBufferSize( _size );

		this._updateResolution( renderTarget, renderer );

		//

		_reflectorWorldPosition.setFromMatrixPosition( target.matrixWorld );
		_cameraWorldPosition.setFromMatrixPosition( camera.matrixWorld );

		_rotationMatrix.extractRotation( target.matrixWorld );

		_normal.set( 0, 0, 1 );
		_normal.applyMatrix4( _rotationMatrix );

		_view.subVectors( _reflectorWorldPosition, _cameraWorldPosition );

		// Avoid rendering when reflector is facing away unless forcing an update
		const isFacingAway = _view.dot( _normal ) > 0;

		let needsClear = false;

		if ( isFacingAway === true && this.forceUpdate === false ) {

			if ( this.hasOutput === false ) {

				_inReflector = false;

				return;

			}

			needsClear = true;

		}

		_view.reflect( _normal ).negate();
		_view.add( _reflectorWorldPosition );

		_rotationMatrix.extractRotation( camera.matrixWorld );

		_lookAtPosition.set( 0, 0, - 1 );
		_lookAtPosition.applyMatrix4( _rotationMatrix );
		_lookAtPosition.add( _cameraWorldPosition );

		_target.subVectors( _reflectorWorldPosition, _lookAtPosition );
		_target.reflect( _normal ).negate();
		_target.add( _reflectorWorldPosition );

		//

		virtualCamera.coordinateSystem = camera.coordinateSystem;
		virtualCamera.position.copy( _view );
		virtualCamera.up.set( 0, 1, 0 );
		virtualCamera.up.applyMatrix4( _rotationMatrix );
		virtualCamera.up.reflect( _normal );
		virtualCamera.lookAt( _target );

		virtualCamera.near = camera.near;
		virtualCamera.far = camera.far;

		virtualCamera.updateMatrixWorld();
		virtualCamera.projectionMatrix.copy( camera.projectionMatrix );

		// Now update projection matrix with new clip plane, implementing code from: http://www.terathon.com/code/oblique.html
		// Paper explaining this technique: http://www.terathon.com/lengyel/Lengyel-Oblique.pdf
		_reflectorPlane.setFromNormalAndCoplanarPoint( _normal, _reflectorWorldPosition );
		_reflectorPlane.applyMatrix4( virtualCamera.matrixWorldInverse );

		clipPlane.set( _reflectorPlane.normal.x, _reflectorPlane.normal.y, _reflectorPlane.normal.z, _reflectorPlane.constant );

		const projectionMatrix = virtualCamera.projectionMatrix;

		_q.x = ( Math.sign( clipPlane.x ) + projectionMatrix.elements[ 8 ] ) / projectionMatrix.elements[ 0 ];
		_q.y = ( Math.sign( clipPlane.y ) + projectionMatrix.elements[ 9 ] ) / projectionMatrix.elements[ 5 ];
		_q.z = - 1.0;
		_q.w = ( 1.0 + projectionMatrix.elements[ 10 ] ) / projectionMatrix.elements[ 14 ];

		// Calculate the scaled plane vector
		clipPlane.multiplyScalar( 1.0 / clipPlane.dot( _q ) );

		const clipBias = 0;

		// Replacing the third row of the projection matrix
		projectionMatrix.elements[ 2 ] = clipPlane.x;
		projectionMatrix.elements[ 6 ] = clipPlane.y;
		projectionMatrix.elements[ 10 ] = ( renderer.coordinateSystem === WebGPUCoordinateSystem ) ? ( clipPlane.z - clipBias ) : ( clipPlane.z + 1.0 - clipBias );
		projectionMatrix.elements[ 14 ] = clipPlane.w;

		//

		this.textureNode.value = renderTarget.texture;

		if ( this.depth === true ) {

			this.textureNode.getDepthNode().value = renderTarget.depthTexture;

		}

		material.visible = false;

		const currentRenderTarget = renderer.getRenderTarget();
		const currentMRT = renderer.getMRT();
		const currentAutoClear = renderer.autoClear;

		renderer.setMRT( null );
		renderer.setRenderTarget( renderTarget );
		renderer.autoClear = true;

		if ( needsClear ) {

			renderer.clear();

			this.hasOutput = false;

		} else {

			renderer.render( scene, virtualCamera );

			this.hasOutput = true;

		}

		renderer.setMRT( currentMRT );
		renderer.setRenderTarget( currentRenderTarget );
		renderer.autoClear = currentAutoClear;

		material.visible = true;

		_inReflector = false;

		this.forceUpdate = false;

	}

}
```
</details>

#### Methods

##### `_updateResolution(renderTarget: RenderTarget, renderer: Renderer): void`

<details><summary>Code</summary>

```ts
_updateResolution( renderTarget, renderer ) {

		const resolution = this.resolution;

		renderer.getDrawingBufferSize( _size );

		renderTarget.setSize( Math.round( _size.width * resolution ), Math.round( _size.height * resolution ) );

	}
```
</details>

##### `setup(builder: any): Node`

<details><summary>Code</summary>

```ts
setup( builder ) {

		this._updateResolution( _defaultRT, builder.renderer );

		return super.setup( builder );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		super.dispose();

		for ( const renderTarget of this.renderTargets.values() ) {

			renderTarget.dispose();

		}

	}
```
</details>

##### `getVirtualCamera(camera: Camera): Camera`

<details><summary>Code</summary>

```ts
getVirtualCamera( camera ) {

		let virtualCamera = this.virtualCameras.get( camera );

		if ( virtualCamera === undefined ) {

			virtualCamera = camera.clone();

			this.virtualCameras.set( camera, virtualCamera );

		}

		return virtualCamera;

	}
```
</details>

##### `getRenderTarget(camera: Camera): RenderTarget`

<details><summary>Code</summary>

```ts
getRenderTarget( camera ) {

		let renderTarget = this.renderTargets.get( camera );

		if ( renderTarget === undefined ) {

			renderTarget = new RenderTarget( 0, 0, { type: HalfFloatType, samples: this.samples } );

			if ( this.generateMipmaps === true ) {

				renderTarget.texture.minFilter = LinearMipMapLinearFilter;
				renderTarget.texture.generateMipmaps = true;

			}

			if ( this.depth === true ) {

				renderTarget.depthTexture = new DepthTexture();

			}

			this.renderTargets.set( camera, renderTarget );

		}

		return renderTarget;

	}
```
</details>

##### `updateBefore(frame: any): boolean`

<details><summary>Code</summary>

```ts
updateBefore( frame ) {

		if ( this.bounces === false && _inReflector ) return false;

		_inReflector = true;

		const { scene, camera, renderer, material } = frame;
		const { target } = this;

		const virtualCamera = this.getVirtualCamera( camera );
		const renderTarget = this.getRenderTarget( virtualCamera );

		renderer.getDrawingBufferSize( _size );

		this._updateResolution( renderTarget, renderer );

		//

		_reflectorWorldPosition.setFromMatrixPosition( target.matrixWorld );
		_cameraWorldPosition.setFromMatrixPosition( camera.matrixWorld );

		_rotationMatrix.extractRotation( target.matrixWorld );

		_normal.set( 0, 0, 1 );
		_normal.applyMatrix4( _rotationMatrix );

		_view.subVectors( _reflectorWorldPosition, _cameraWorldPosition );

		// Avoid rendering when reflector is facing away unless forcing an update
		const isFacingAway = _view.dot( _normal ) > 0;

		let needsClear = false;

		if ( isFacingAway === true && this.forceUpdate === false ) {

			if ( this.hasOutput === false ) {

				_inReflector = false;

				return;

			}

			needsClear = true;

		}

		_view.reflect( _normal ).negate();
		_view.add( _reflectorWorldPosition );

		_rotationMatrix.extractRotation( camera.matrixWorld );

		_lookAtPosition.set( 0, 0, - 1 );
		_lookAtPosition.applyMatrix4( _rotationMatrix );
		_lookAtPosition.add( _cameraWorldPosition );

		_target.subVectors( _reflectorWorldPosition, _lookAtPosition );
		_target.reflect( _normal ).negate();
		_target.add( _reflectorWorldPosition );

		//

		virtualCamera.coordinateSystem = camera.coordinateSystem;
		virtualCamera.position.copy( _view );
		virtualCamera.up.set( 0, 1, 0 );
		virtualCamera.up.applyMatrix4( _rotationMatrix );
		virtualCamera.up.reflect( _normal );
		virtualCamera.lookAt( _target );

		virtualCamera.near = camera.near;
		virtualCamera.far = camera.far;

		virtualCamera.updateMatrixWorld();
		virtualCamera.projectionMatrix.copy( camera.projectionMatrix );

		// Now update projection matrix with new clip plane, implementing code from: http://www.terathon.com/code/oblique.html
		// Paper explaining this technique: http://www.terathon.com/lengyel/Lengyel-Oblique.pdf
		_reflectorPlane.setFromNormalAndCoplanarPoint( _normal, _reflectorWorldPosition );
		_reflectorPlane.applyMatrix4( virtualCamera.matrixWorldInverse );

		clipPlane.set( _reflectorPlane.normal.x, _reflectorPlane.normal.y, _reflectorPlane.normal.z, _reflectorPlane.constant );

		const projectionMatrix = virtualCamera.projectionMatrix;

		_q.x = ( Math.sign( clipPlane.x ) + projectionMatrix.elements[ 8 ] ) / projectionMatrix.elements[ 0 ];
		_q.y = ( Math.sign( clipPlane.y ) + projectionMatrix.elements[ 9 ] ) / projectionMatrix.elements[ 5 ];
		_q.z = - 1.0;
		_q.w = ( 1.0 + projectionMatrix.elements[ 10 ] ) / projectionMatrix.elements[ 14 ];

		// Calculate the scaled plane vector
		clipPlane.multiplyScalar( 1.0 / clipPlane.dot( _q ) );

		const clipBias = 0;

		// Replacing the third row of the projection matrix
		projectionMatrix.elements[ 2 ] = clipPlane.x;
		projectionMatrix.elements[ 6 ] = clipPlane.y;
		projectionMatrix.elements[ 10 ] = ( renderer.coordinateSystem === WebGPUCoordinateSystem ) ? ( clipPlane.z - clipBias ) : ( clipPlane.z + 1.0 - clipBias );
		projectionMatrix.elements[ 14 ] = clipPlane.w;

		//

		this.textureNode.value = renderTarget.texture;

		if ( this.depth === true ) {

			this.textureNode.getDepthNode().value = renderTarget.depthTexture;

		}

		material.visible = false;

		const currentRenderTarget = renderer.getRenderTarget();
		const currentMRT = renderer.getMRT();
		const currentAutoClear = renderer.autoClear;

		renderer.setMRT( null );
		renderer.setRenderTarget( renderTarget );
		renderer.autoClear = true;

		if ( needsClear ) {

			renderer.clear();

			this.hasOutput = false;

		} else {

			renderer.render( scene, virtualCamera );

			this.hasOutput = true;

		}

		renderer.setMRT( currentMRT );
		renderer.setRenderTarget( currentRenderTarget );
		renderer.autoClear = currentAutoClear;

		material.visible = true;

		_inReflector = false;

		this.forceUpdate = false;

	}
```
</details>


---