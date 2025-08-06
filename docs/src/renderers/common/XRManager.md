[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `XRManager.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 30 |
| 🧱 Classes | 1 |
| 📦 Imports | 28 |
| 📊 Variables & Constants | 81 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/XRManager.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ArrayCamera` | `../../cameras/ArrayCamera.js` |
| `EventDispatcher` | `../../core/EventDispatcher.js` |
| `PerspectiveCamera` | `../../cameras/PerspectiveCamera.js` |
| `Quaternion` | `../../math/Quaternion.js` |
| `RAD2DEG` | `../../math/MathUtils.js` |
| `Vector2` | `../../math/Vector2.js` |
| `Vector3` | `../../math/Vector3.js` |
| `Vector4` | `../../math/Vector4.js` |
| `WebXRController` | `../webxr/WebXRController.js` |
| `AddEquation` | `../../constants.js` |
| `BackSide` | `../../constants.js` |
| `CustomBlending` | `../../constants.js` |
| `DepthFormat` | `../../constants.js` |
| `DepthStencilFormat` | `../../constants.js` |
| `FrontSide` | `../../constants.js` |
| `RGBAFormat` | `../../constants.js` |
| `UnsignedByteType` | `../../constants.js` |
| `UnsignedInt248Type` | `../../constants.js` |
| `UnsignedIntType` | `../../constants.js` |
| `ZeroFactor` | `../../constants.js` |
| `DepthTexture` | `../../textures/DepthTexture.js` |
| `XRRenderTarget` | `./XRRenderTarget.js` |
| `CylinderGeometry` | `../../geometries/CylinderGeometry.js` |
| `QuadMesh` | `./QuadMesh.js` |
| `NodeMaterial` | `../../materials/nodes/NodeMaterial.js` |
| `PlaneGeometry` | `../../geometries/PlaneGeometry.js` |
| `MeshBasicMaterial` | `../../materials/MeshBasicMaterial.js` |
| `Mesh` | `../../objects/Mesh.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_cameraLPos` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_cameraRPos` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `geometry` | `PlaneGeometry` | let/var | `new PlaneGeometry( width, height )` | ✗ |
| `renderTarget` | `XRRenderTarget` | let/var | `new XRRenderTarget( pixelwidth, pixelheight, { format: RGBAFormat, type: Unsi...` | ✗ |
| `material` | `MeshBasicMaterial` | let/var | `new MeshBasicMaterial( { color: 0xffffff, side: FrontSide } )` | ✗ |
| `plane` | `Mesh` | let/var | `new Mesh( geometry, material )` | ✗ |
| `layer` | `{ type: string; width: number; height...` | let/var | `{ type: 'quad', width: width, height: height, translation: translation, quate...` | ✗ |
| `xrlayers` | `any` | let/var | `this._session.renderState.layers` | ✗ |
| `geometry` | `CylinderGeometry` | let/var | `new CylinderGeometry( radius, radius, radius * centralAngle / aspectratio, 64...` | ✗ |
| `renderTarget` | `XRRenderTarget` | let/var | `new XRRenderTarget( pixelwidth, pixelheight, { format: RGBAFormat, type: Unsi...` | ✗ |
| `material` | `MeshBasicMaterial` | let/var | `new MeshBasicMaterial( { color: 0xffffff, side: BackSide } )` | ✗ |
| `plane` | `Mesh` | let/var | `new Mesh( geometry, material )` | ✗ |
| `layer` | `{ type: string; radius: number; centr...` | let/var | `{ type: 'cylinder', radius: radius, centralAngle: centralAngle, aspectratio: ...` | ✗ |
| `xrlayers` | `any` | let/var | `this._session.renderState.layers` | ✗ |
| `translationObject` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `quaternionObject` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `renderer` | `Renderer` | let/var | `this._renderer` | ✗ |
| `wasPresenting` | `boolean` | let/var | `this.isPresenting` | ✗ |
| `rendererFramebufferTarget` | `any` | let/var | `renderer._frameBufferTarget` | ✗ |
| `rendererSize` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `rendererQuad` | `any` | let/var | `renderer._quad` | ✗ |
| `renderer` | `Renderer` | let/var | `this._renderer` | ✗ |
| `backend` | `any` | let/var | `renderer.backend` | ✗ |
| `gl` | `WebGL2RenderingContext` | let/var | `this._gl` | ✗ |
| `glBinding` | `any` | let/var | `new XRWebGLBinding( session, gl )` | ✗ |
| `depthFormat` | `any` | let/var | `null` | ✗ |
| `depthType` | `any` | let/var | `null` | ✗ |
| `glDepthFormat` | `any` | let/var | `null` | ✗ |
| `projectionlayerInit` | `{ colorFormat: 32856; depthFormat: 35...` | let/var | `{ colorFormat: gl.RGBA8, depthFormat: glDepthFormat, scaleFactor: this._frame...` | ✗ |
| `layersArray` | `any[]` | let/var | `[ glProjLayer ]` | ✗ |
| `depth` | `1 \| 2` | let/var | `this._useMultiview ? 2 : 1` | ✗ |
| `depthTexture` | `DepthTexture` | let/var | `new DepthTexture( glProjLayer.textureWidth, glProjLayer.textureHeight, depthT...` | ✗ |
| `layerInit` | `{ antialias: boolean; alpha: boolean;...` | let/var | `{ antialias: renderer.samples > 0, alpha: true, depth: renderer.depth, stenci...` | ✗ |
| `glBaseLayer` | `any` | let/var | `new XRWebGLLayer( session, gl, layerInit )` | ✗ |
| `session` | `XRSession` | let/var | `this._session` | ✗ |
| `depthNear` | `number` | let/var | `camera.near` | ✗ |
| `depthFar` | `number` | let/var | `camera.far` | ✗ |
| `cameraXR` | `ArrayCamera` | let/var | `this._cameraXR` | ✗ |
| `cameraL` | `PerspectiveCamera` | let/var | `this._cameraL` | ✗ |
| `cameraR` | `PerspectiveCamera` | let/var | `this._cameraR` | ✗ |
| `parent` | `Object3D` | let/var | `camera.parent` | ✗ |
| `cameras` | `PerspectiveCamera[]` | let/var | `cameraXR.cameras` | ✗ |
| `controller` | `WebXRController` | let/var | `this._controllers[ index ]` | ✗ |
| `projL` | `number[]` | let/var | `cameraL.projectionMatrix.elements` | ✗ |
| `projR` | `number[]` | let/var | `cameraR.projectionMatrix.elements` | ✗ |
| `near` | `number` | let/var | `projL[ 14 ] / ( projL[ 10 ] - 1 )` | ✗ |
| `far` | `number` | let/var | `projL[ 14 ] / ( projL[ 10 ] + 1 )` | ✗ |
| `topFov` | `number` | let/var | `( projL[ 9 ] + 1 ) / projL[ 5 ]` | ✗ |
| `bottomFov` | `number` | let/var | `( projL[ 9 ] - 1 ) / projL[ 5 ]` | ✗ |
| `leftFov` | `number` | let/var | `( projL[ 8 ] - 1 ) / projL[ 0 ]` | ✗ |
| `rightFov` | `number` | let/var | `( projR[ 8 ] + 1 ) / projR[ 0 ]` | ✗ |
| `left` | `number` | let/var | `near * leftFov` | ✗ |
| `right` | `number` | let/var | `near * rightFov` | ✗ |
| `zOffset` | `number` | let/var | `ipd / ( - leftFov + rightFov )` | ✗ |
| `xOffset` | `number` | let/var | `zOffset * - leftFov` | ✗ |
| `near2` | `number` | let/var | `near + zOffset` | ✗ |
| `far2` | `number` | let/var | `far + zOffset` | ✗ |
| `left2` | `number` | let/var | `left - xOffset` | ✗ |
| `right2` | `number` | let/var | `right + ( ipd - xOffset )` | ✗ |
| `top2` | `number` | let/var | `topFov * far / far2 * near2` | ✗ |
| `bottom2` | `number` | let/var | `bottomFov * far / far2 * near2` | ✗ |
| `controller` | `any` | let/var | `this._controllers[ controllerIndex ]` | ✗ |
| `session` | `undefined` | let/var | `this._session` | ✗ |
| `renderer` | `any` | let/var | `this._renderer` | ✗ |
| `inputSource` | `any` | let/var | `this._controllerInputSources[ i ]` | ✗ |
| `controllers` | `any` | let/var | `this._controllers` | ✗ |
| `controllerInputSources` | `any` | let/var | `this._controllerInputSources` | ✗ |
| `inputSource` | `any` | let/var | `event.removed[ i ]` | ✗ |
| `inputSource` | `any` | let/var | `event.added[ i ]` | ✗ |
| `controller` | `any` | let/var | `controllers[ controllerIndex ]` | ✗ |
| `cameraXR` | `any` | let/var | `this._cameraXR` | ✗ |
| `renderer` | `any` | let/var | `this._renderer` | ✗ |
| `backend` | `any` | let/var | `renderer.backend` | ✗ |
| `glBaseLayer` | `any` | let/var | `this._glBaseLayer` | ✗ |
| `views` | `any` | let/var | `pose.views` | ✗ |
| `cameraXRNeedsUpdate` | `boolean` | let/var | `false` | ✗ |
| `view` | `any` | let/var | `views[ i ]` | ✗ |
| `viewport` | `any` | let/var | `*not shown*` | ✗ |
| `camera` | `any` | let/var | `this._cameras[ i ]` | ✗ |
| `inputSource` | `any` | let/var | `this._controllerInputSources[ i ]` | ✗ |
| `controller` | `any` | let/var | `this._controllers[ i ]` | ✗ |


---

## Functions

### `XRManager.getController(index: number): Group`

**JSDoc:**
```typescript
/**
	 * Returns an instance of `THREE.Group` that represents the transformation
	 * of a XR controller in target ray space. The requested controller is defined
	 * by the given index.
	 *
	 * @param {number} index - The index of the XR controller.
	 * @return {Group} A group that represents the controller's transformation.
	 */
```

**Parameters:**

- **`index`** `number`

**Returns:** `Group`

**Calls:**

- `this._getController`
- `controller.getTargetRaySpace`

<details><summary>Code</summary>

```typescript
getController( index ) {

		const controller = this._getController( index );

		return controller.getTargetRaySpace();

	}
```
</details>

### `XRManager.getControllerGrip(index: number): Group`

**JSDoc:**
```typescript
/**
	 * Returns an instance of `THREE.Group` that represents the transformation
	 * of a XR controller in grip space. The requested controller is defined
	 * by the given index.
	 *
	 * @param {number} index - The index of the XR controller.
	 * @return {Group} A group that represents the controller's transformation.
	 */
```

**Parameters:**

- **`index`** `number`

**Returns:** `Group`

**Calls:**

- `this._getController`
- `controller.getGripSpace`

<details><summary>Code</summary>

```typescript
getControllerGrip( index ) {

		const controller = this._getController( index );

		return controller.getGripSpace();

	}
```
</details>

### `XRManager.getHand(index: number): Group`

**JSDoc:**
```typescript
/**
	 * Returns an instance of `THREE.Group` that represents the transformation
	 * of a XR controller in hand space. The requested controller is defined
	 * by the given index.
	 *
	 * @param {number} index - The index of the XR controller.
	 * @return {Group} A group that represents the controller's transformation.
	 */
```

**Parameters:**

- **`index`** `number`

**Returns:** `Group`

**Calls:**

- `this._getController`
- `controller.getHandSpace`

<details><summary>Code</summary>

```typescript
getHand( index ) {

		const controller = this._getController( index );

		return controller.getHandSpace();

	}
```
</details>

### `XRManager.getFoveation(): number`

**JSDoc:**
```typescript
/**
	 * Returns the foveation value.
	 *
	 * @return {number|undefined} The foveation value. Returns `undefined` if no base or projection layer is defined.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getFoveation() {

		if ( this._glProjLayer === null && this._glBaseLayer === null ) {

			return undefined;

		}

		return this._foveation;

	}
```
</details>

### `XRManager.setFoveation(foveation: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the foveation value.
	 *
	 * @param {number} foveation - A number in the range `[0,1]` where `0` means no foveation (full resolution)
	 * and `1` means maximum foveation (the edges render at lower resolution).
	 */
```

**Parameters:**

- **`foveation`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setFoveation( foveation ) {

		this._foveation = foveation;

		if ( this._glProjLayer !== null ) {

			this._glProjLayer.fixedFoveation = foveation;

		}

		if ( this._glBaseLayer !== null && this._glBaseLayer.fixedFoveation !== undefined ) {

			this._glBaseLayer.fixedFoveation = foveation;

		}

	}
```
</details>

### `XRManager.getFramebufferScaleFactor(): number`

**JSDoc:**
```typescript
/**
	 * Returns the framebuffer scale factor.
	 *
	 * @return {number} The framebuffer scale factor.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getFramebufferScaleFactor() {

		return this._framebufferScaleFactor;

	}
```
</details>

### `XRManager.setFramebufferScaleFactor(factor: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the framebuffer scale factor.
	 *
	 * This method can not be used during a XR session.
	 *
	 * @param {number} factor - The framebuffer scale factor.
	 */
```

**Parameters:**

- **`factor`** `number`

**Returns:** `void`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
setFramebufferScaleFactor( factor ) {

		this._framebufferScaleFactor = factor;

		if ( this.isPresenting === true ) {

			console.warn( 'THREE.XRManager: Cannot change framebuffer scale while presenting.' );

		}

	}
```
</details>

### `XRManager.getReferenceSpaceType(): XRReferenceSpaceType`

**JSDoc:**
```typescript
/**
	 * Returns the reference space type.
	 *
	 * @return {XRReferenceSpaceType} The reference space type.
	 */
```

**Returns:** `XRReferenceSpaceType`

<details><summary>Code</summary>

```typescript
getReferenceSpaceType() {

		return this._referenceSpaceType;

	}
```
</details>

### `XRManager.setReferenceSpaceType(type: XRReferenceSpaceType): void`

**JSDoc:**
```typescript
/**
	 * Sets the reference space type.
	 *
	 * This method can not be used during a XR session.
	 *
	 * @param {XRReferenceSpaceType} type - The reference space type.
	 */
```

**Parameters:**

- **`type`** `XRReferenceSpaceType`

**Returns:** `void`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
setReferenceSpaceType( type ) {

		this._referenceSpaceType = type;

		if ( this.isPresenting === true ) {

			console.warn( 'THREE.XRManager: Cannot change reference space type while presenting.' );

		}

	}
```
</details>

### `XRManager.getReferenceSpace(): XRReferenceSpace`

**JSDoc:**
```typescript
/**
	 * Returns the XR reference space.
	 *
	 * @return {XRReferenceSpace} The XR reference space.
	 */
```

**Returns:** `XRReferenceSpace`

<details><summary>Code</summary>

```typescript
getReferenceSpace() {

		return this._customReferenceSpace || this._referenceSpace;

	}
```
</details>

### `XRManager.setReferenceSpace(space: XRReferenceSpace): void`

**JSDoc:**
```typescript
/**
	 * Sets a custom XR reference space.
	 *
	 * @param {XRReferenceSpace} space - The XR reference space.
	 */
```

**Parameters:**

- **`space`** `XRReferenceSpace`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setReferenceSpace( space ) {

		this._customReferenceSpace = space;

	}
```
</details>

### `XRManager.getCamera(): ArrayCamera`

**JSDoc:**
```typescript
/**
	 * Returns the XR camera.
	 *
	 * @return {ArrayCamera} The XR camera.
	 */
```

**Returns:** `ArrayCamera`

<details><summary>Code</summary>

```typescript
getCamera() {

		return this._cameraXR;

	}
```
</details>

### `XRManager.getEnvironmentBlendMode(): "opaque" | "additive" | "alpha-blend"`

**JSDoc:**
```typescript
/**
	 * Returns the environment blend mode from the current XR session.
	 *
	 * @return {'opaque'|'additive'|'alpha-blend'|undefined} The environment blend mode. Returns `undefined` when used outside of a XR session.
	 */
```

**Returns:** `"opaque" | "additive" | "alpha-blend"`

<details><summary>Code</summary>

```typescript
getEnvironmentBlendMode() {

		if ( this._session !== null ) {

			return this._session.environmentBlendMode;

		}

	}
```
</details>

### `XRManager.getFrame(): XRFrame`

**JSDoc:**
```typescript
/**
	 * Returns the current XR frame.
	 *
	 * @return {?XRFrame} The XR frame. Returns `null` when used outside a XR session.
	 */
```

**Returns:** `XRFrame`

<details><summary>Code</summary>

```typescript
getFrame() {

		return this._xrFrame;

	}
```
</details>

### `XRManager.useMultiview(): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the engine renders to a multiview target.
	 *
	 * @return {boolean} Whether the engine renders to a multiview render target or not.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
useMultiview() {

		return this._useMultiview;

	}
```
</details>

### `XRManager.createQuadLayer(width: number, height: number, translation: Vector3, quaternion: Quaternion, pixelwidth: number, pixelheight: number, rendercall: Function, attributes: any): Mesh`

**JSDoc:**
```typescript
/**
	 * This method can be used in XR applications to create a quadratic layer that presents a separate
	 * rendered scene.
	 *
	 * @param {number} width - The width of the layer plane in world units.
	 * @param {number} height - The height of the layer plane in world units.
	 * @param {Vector3} translation - The position/translation of the layer plane in world units.
	 * @param {Quaternion} quaternion - The orientation of the layer plane expressed as a quaternion.
	 * @param {number} pixelwidth - The width of the layer's render target in pixels.
	 * @param {number} pixelheight - The height of the layer's render target in pixels.
	 * @param {Function} rendercall - A callback function that renders the layer. Similar to code in
	 * the default animation loop, this method can be used to update/transform 3D object in the layer's scene.
	 * @param {Object} [attributes={}] - Allows to configure the layer's render target.
	 * @return {Mesh} A mesh representing the quadratic XR layer. This mesh should be added to the XR scene.
	 */
```

**Parameters:**

- **`width`** `number`
- **`height`** `number`
- **`translation`** `Vector3`
- **`quaternion`** `Quaternion`
- **`pixelwidth`** `number`
- **`pixelheight`** `number`
- **`rendercall`** `Function`
- **`attributes`** `any`

**Returns:** `Mesh`

**Calls:**

- `plane.position.copy`
- `plane.quaternion.copy`
- `this._layers.push`
- `this._createXRLayer`
- `xrlayers.unshift`
- `this._session.updateRenderState`

<details><summary>Code</summary>

```typescript
createQuadLayer( width, height, translation, quaternion, pixelwidth, pixelheight, rendercall, attributes = {} ) {

		const geometry = new PlaneGeometry( width, height );
		const renderTarget = new XRRenderTarget(
			pixelwidth,
			pixelheight,
			{
				format: RGBAFormat,
				type: UnsignedByteType,
				depthTexture: new DepthTexture(
					pixelwidth,
					pixelheight,
					attributes.stencil ? UnsignedInt248Type : UnsignedIntType,
					undefined,
					undefined,
					undefined,
					undefined,
					undefined,
					undefined,
					attributes.stencil ? DepthStencilFormat : DepthFormat
				),
				stencilBuffer: attributes.stencil,
				resolveDepthBuffer: false,
				resolveStencilBuffer: false
			} );

		renderTarget._autoAllocateDepthBuffer = true;

		const material = new MeshBasicMaterial( { color: 0xffffff, side: FrontSide } );
		material.map = renderTarget.texture;
		material.map.offset.y = 1;
		material.map.repeat.y = - 1;
		const plane = new Mesh( geometry, material );
		plane.position.copy( translation );
		plane.quaternion.copy( quaternion );

		const layer = {
			type: 'quad',
			width: width,
			height: height,
			translation: translation,
			quaternion: quaternion,
			pixelwidth: pixelwidth,
			pixelheight: pixelheight,
			plane: plane,
			material: material,
			rendercall: rendercall,
			renderTarget: renderTarget };

		this._layers.push( layer );

		if ( this._session !== null ) {

			layer.plane.material = new MeshBasicMaterial( { color: 0xffffff, side: FrontSide } );
			layer.plane.material.blending = CustomBlending;
			layer.plane.material.blendEquation = AddEquation;
			layer.plane.material.blendSrc = ZeroFactor;
			layer.plane.material.blendDst = ZeroFactor;

			layer.xrlayer = this._createXRLayer( layer );

			const xrlayers = this._session.renderState.layers;
			xrlayers.unshift( layer.xrlayer );
			this._session.updateRenderState( { layers: xrlayers } );

		} else {

			renderTarget.isXRRenderTarget = false;

		}

		return plane;

	}
```
</details>

### `XRManager.createCylinderLayer(radius: number, centralAngle: number, aspectratio: number, translation: Vector3, quaternion: Quaternion, pixelwidth: number, pixelheight: number, rendercall: Function, attributes: any): Mesh`

**JSDoc:**
```typescript
/**
	 * This method can be used in XR applications to create a cylindrical layer that presents a separate
	 * rendered scene.
	 *
	 * @param {number} radius - The radius of the cylinder in world units.
	 * @param {number} centralAngle - The central angle of the cylinder in radians.
	 * @param {number} aspectratio - The aspect ratio.
	 * @param {Vector3} translation - The position/translation of the layer plane in world units.
	 * @param {Quaternion} quaternion - The orientation of the layer plane expressed as a quaternion.
	 * @param {number} pixelwidth - The width of the layer's render target in pixels.
	 * @param {number} pixelheight - The height of the layer's render target in pixels.
	 * @param {Function} rendercall - A callback function that renders the layer. Similar to code in
	 * the default animation loop, this method can be used to update/transform 3D object in the layer's scene.
	 * @param {Object} [attributes={}] - Allows to configure the layer's render target.
	 * @return {Mesh} A mesh representing the cylindrical XR layer. This mesh should be added to the XR scene.
	 */
```

**Parameters:**

- **`radius`** `number`
- **`centralAngle`** `number`
- **`aspectratio`** `number`
- **`translation`** `Vector3`
- **`quaternion`** `Quaternion`
- **`pixelwidth`** `number`
- **`pixelheight`** `number`
- **`rendercall`** `Function`
- **`attributes`** `any`

**Returns:** `Mesh`

**Calls:**

- `plane.position.copy`
- `plane.quaternion.copy`
- `this._layers.push`
- `this._createXRLayer`
- `xrlayers.unshift`
- `this._session.updateRenderState`

<details><summary>Code</summary>

```typescript
createCylinderLayer( radius, centralAngle, aspectratio, translation, quaternion, pixelwidth, pixelheight, rendercall, attributes = {} ) {

		const geometry = new CylinderGeometry( radius, radius, radius * centralAngle / aspectratio, 64, 64, true, Math.PI - centralAngle / 2, centralAngle );
		const renderTarget = new XRRenderTarget(
			pixelwidth,
			pixelheight,
			{
				format: RGBAFormat,
				type: UnsignedByteType,
				depthTexture: new DepthTexture(
					pixelwidth,
					pixelheight,
					attributes.stencil ? UnsignedInt248Type : UnsignedIntType,
					undefined,
					undefined,
					undefined,
					undefined,
					undefined,
					undefined,
					attributes.stencil ? DepthStencilFormat : DepthFormat
				),
				stencilBuffer: attributes.stencil,
				resolveDepthBuffer: false,
				resolveStencilBuffer: false
			} );

		renderTarget._autoAllocateDepthBuffer = true;

		const material = new MeshBasicMaterial( { color: 0xffffff, side: BackSide } );
		material.map = renderTarget.texture;
		material.map.offset.y = 1;
		material.map.repeat.y = - 1;
		const plane = new Mesh( geometry, material );
		plane.position.copy( translation );
		plane.quaternion.copy( quaternion );

		const layer = {
			type: 'cylinder',
			radius: radius,
			centralAngle: centralAngle,
			aspectratio: aspectratio,
			translation: translation,
			quaternion: quaternion,
			pixelwidth: pixelwidth,
			pixelheight: pixelheight,
			plane: plane,
			material: material,
			rendercall: rendercall,
			renderTarget: renderTarget };

		this._layers.push( layer );

		if ( this._session !== null ) {

			layer.plane.material = new MeshBasicMaterial( { color: 0xffffff, side: BackSide } );
			layer.plane.material.blending = CustomBlending;
			layer.plane.material.blendEquation = AddEquation;
			layer.plane.material.blendSrc = ZeroFactor;
			layer.plane.material.blendDst = ZeroFactor;

			layer.xrlayer = this._createXRLayer( layer );

			const xrlayers = this._session.renderState.layers;
			xrlayers.unshift( layer.xrlayer );
			this._session.updateRenderState( { layers: xrlayers } );

		} else {

			renderTarget.isXRRenderTarget = false;

		}

		return plane;

	}
```
</details>

### `XRManager.renderLayers(): void`

**JSDoc:**
```typescript
/**
	 * Renders the XR layers that have been previously added to the scene.
	 *
	 * This method is usually called in your animation loop before rendering
	 * the actual scene via `renderer.render( scene, camera );`.
	 */
```

**Returns:** `void`

**Calls:**

- `renderer.getOutputRenderTarget`
- `renderer.getSize`
- `layer.plane.getWorldPosition`
- `layer.plane.getWorldQuaternion`
- `this._glBinding.getSubImage`
- `renderer.backend.setXRRenderTargetTextures`
- `renderer._setXRLayerSize`
- `renderer.setOutputRenderTarget`
- `renderer.setRenderTarget`
- `this._frameBufferTargets.get`
- `this._frameBufferTargets.set`
- `renderer._getFrameBufferTarget`
- `layer.rendercall`

<details><summary>Code</summary>

```typescript
renderLayers( ) {

		const translationObject = new Vector3();
		const quaternionObject = new Quaternion();
		const renderer = this._renderer;

		const wasPresenting = this.isPresenting;
		const rendererOutputTarget = renderer.getOutputRenderTarget();
		const rendererFramebufferTarget = renderer._frameBufferTarget;
		this.isPresenting = false;

		const rendererSize = new Vector2();
		renderer.getSize( rendererSize );
		const rendererQuad = renderer._quad;

		for ( const layer of this._layers ) {

			layer.renderTarget.isXRRenderTarget = this._session !== null;
			layer.renderTarget._hasExternalTextures = layer.renderTarget.isXRRenderTarget;

			if ( layer.renderTarget.isXRRenderTarget && this._supportsLayers ) {

				layer.xrlayer.transform = new XRRigidTransform( layer.plane.getWorldPosition( translationObject ), layer.plane.getWorldQuaternion( quaternionObject ) );

				const glSubImage = this._glBinding.getSubImage( layer.xrlayer, this._xrFrame );
				renderer.backend.setXRRenderTargetTextures(
					layer.renderTarget,
					glSubImage.colorTexture,
					undefined );

				renderer._setXRLayerSize( layer.renderTarget.width, layer.renderTarget.height );
				renderer.setOutputRenderTarget( layer.renderTarget );
				renderer.setRenderTarget( null );
				renderer._frameBufferTarget = null;

				this._frameBufferTargets || ( this._frameBufferTargets = new WeakMap() );
				const { frameBufferTarget, quad } = this._frameBufferTargets.get( layer.renderTarget ) || { frameBufferTarget: null, quad: null };
				if ( ! frameBufferTarget ) {

					renderer._quad = new QuadMesh( new NodeMaterial() );
					this._frameBufferTargets.set( layer.renderTarget, { frameBufferTarget: renderer._getFrameBufferTarget(), quad: renderer._quad } );

				} else {

					renderer._frameBufferTarget = frameBufferTarget;
					renderer._quad = quad;

				}

				layer.rendercall();

				renderer._frameBufferTarget = null;

			} else {

				renderer.setRenderTarget( layer.renderTarget );
				layer.rendercall();

			}

		}

		renderer.setRenderTarget( null );
		renderer.setOutputRenderTarget( rendererOutputTarget );
		renderer._frameBufferTarget = rendererFramebufferTarget;
		renderer._setXRLayerSize( rendererSize.x, rendererSize.y );
		renderer._quad = rendererQuad;
		this.isPresenting = wasPresenting;

	}
```
</details>

### `XRManager.getSession(): XRSession`

**JSDoc:**
```typescript
/**
	 * Returns the current XR session.
	 *
	 * @return {?XRSession} The XR session. Returns `null` when used outside a XR session.
	 */
```

**Returns:** `XRSession`

<details><summary>Code</summary>

```typescript
getSession() {

		return this._session;

	}
```
</details>

### `XRManager.setSession(session: XRSession): Promise<any>`

**JSDoc:**
```typescript
/**
	 * After a XR session has been requested usually with one of the `*Button` modules, it
	 * is injected into the renderer with this method. This method triggers the start of
	 * the actual XR rendering.
	 *
	 * @async
	 * @param {XRSession} session - The XR session to set.
	 * @return {Promise} A Promise that resolves when the session has been set.
	 */
```

**Parameters:**

- **`session`** `XRSession`

**Returns:** `Promise<any>`

**Calls:**

- `renderer.getContext`
- `gl.getContextAttributes`
- `session.addEventListener`
- `backend.makeXRCompatible`
- `renderer.getPixelRatio`
- `renderer.getSize`
- `renderer._animation.getContext`
- `renderer._animation.getAnimationLoop`
- `renderer._animation.stop`
- `renderer.hasFeature`
- `this._glBinding.createProjectionLayer`
- `renderer.setPixelRatio`
- `renderer._setXRLayerSize`
- `session.enabledFeatures.includes`
- `session.requestReferenceSpace`
- `this.getReferenceSpaceType`
- `this._createXRLayer`
- `layersArray.unshift`
- `session.updateRenderState`
- `this.getFramebufferScaleFactor`
- `this.setFoveation`
- `this.getFoveation`
- `renderer._animation.setAnimationLoop`
- `renderer._animation.setContext`
- `renderer._animation.start`
- `this.dispatchEvent`

**Internal Comments:**
```
// (x6)
// default path using XRProjectionLayer (x2)
// switch layers to native
// change material so it "punches" out a hole to show the XR Layer. (x5)
// fallback to XRWebGLLayer (x2)
```

<details><summary>Code</summary>

```typescript
async setSession( session ) {

		const renderer = this._renderer;
		const backend = renderer.backend;

		this._gl = renderer.getContext();
		const gl = this._gl;
		const attributes = gl.getContextAttributes();

		this._session = session;

		if ( session !== null ) {

			if ( backend.isWebGPUBackend === true ) throw new Error( 'THREE.XRManager: XR is currently not supported with a WebGPU backend. Use WebGL by passing "{ forceWebGL: true }" to the constructor of the renderer.' );

			session.addEventListener( 'select', this._onSessionEvent );
			session.addEventListener( 'selectstart', this._onSessionEvent );
			session.addEventListener( 'selectend', this._onSessionEvent );
			session.addEventListener( 'squeeze', this._onSessionEvent );
			session.addEventListener( 'squeezestart', this._onSessionEvent );
			session.addEventListener( 'squeezeend', this._onSessionEvent );
			session.addEventListener( 'end', this._onSessionEnd );
			session.addEventListener( 'inputsourceschange', this._onInputSourcesChange );

			await backend.makeXRCompatible();

			this._currentPixelRatio = renderer.getPixelRatio();
			renderer.getSize( this._currentSize );

			this._currentAnimationContext = renderer._animation.getContext();
			this._currentAnimationLoop = renderer._animation.getAnimationLoop();
			renderer._animation.stop();

			//

			if ( this._supportsGlBinding ) {

				const glBinding = new XRWebGLBinding( session, gl );
				this._glBinding = glBinding;

			}

			//

			if ( this._useLayers === true ) {

				// default path using XRProjectionLayer

				let depthFormat = null;
				let depthType = null;
				let glDepthFormat = null;

				if ( renderer.depth ) {

					glDepthFormat = renderer.stencil ? gl.DEPTH24_STENCIL8 : gl.DEPTH_COMPONENT24;
					depthFormat = renderer.stencil ? DepthStencilFormat : DepthFormat;
					depthType = renderer.stencil ? UnsignedInt248Type : UnsignedIntType;

				}

				const projectionlayerInit = {
					colorFormat: gl.RGBA8,
					depthFormat: glDepthFormat,
					scaleFactor: this._framebufferScaleFactor,
					clearOnAccess: false
				};

				if ( this._useMultiviewIfPossible && renderer.hasFeature( 'OVR_multiview2' ) ) {

					projectionlayerInit.textureType = 'texture-array';
					this._useMultiview = true;

				}

				const glProjLayer = this._glBinding.createProjectionLayer( projectionlayerInit );
				const layersArray = [ glProjLayer ];

				this._glProjLayer = glProjLayer;

				renderer.setPixelRatio( 1 );
				renderer._setXRLayerSize( glProjLayer.textureWidth, glProjLayer.textureHeight );

				const depth = this._useMultiview ? 2 : 1;
				const depthTexture = new DepthTexture( glProjLayer.textureWidth, glProjLayer.textureHeight, depthType, undefined, undefined, undefined, undefined, undefined, undefined, depthFormat, depth );

				this._xrRenderTarget = new XRRenderTarget(
					glProjLayer.textureWidth,
					glProjLayer.textureHeight,
					{
						format: RGBAFormat,
						type: UnsignedByteType,
						colorSpace: renderer.outputColorSpace,
						depthTexture: depthTexture,
						stencilBuffer: renderer.stencil,
						samples: attributes.antialias ? 4 : 0,
						resolveDepthBuffer: ( glProjLayer.ignoreDepthValues === false ),
						resolveStencilBuffer: ( glProjLayer.ignoreDepthValues === false ),
						depth: this._useMultiview ? 2 : 1,
						multiview: this._useMultiview
					} );

				this._xrRenderTarget._hasExternalTextures = true;
				this._xrRenderTarget.depth = this._useMultiview ? 2 : 1;

				this._supportsLayers = session.enabledFeatures.includes( 'layers' );

				this._referenceSpace = await session.requestReferenceSpace( this.getReferenceSpaceType() );

				if ( this._supportsLayers ) {

					// switch layers to native
					for ( const layer of this._layers ) {

						// change material so it "punches" out a hole to show the XR Layer.
						layer.plane.material = new MeshBasicMaterial( { color: 0xffffff, side: layer.type === 'cylinder' ? BackSide : FrontSide } );
						layer.plane.material.blending = CustomBlending;
						layer.plane.material.blendEquation = AddEquation;
						layer.plane.material.blendSrc = ZeroFactor;
						layer.plane.material.blendDst = ZeroFactor;

						layer.xrlayer = this._createXRLayer( layer );

						layersArray.unshift( layer.xrlayer );

					}

				}

				session.updateRenderState( { layers: layersArray } );

			} else {

				// fallback to XRWebGLLayer

				const layerInit = {
					antialias: renderer.samples > 0,
					alpha: true,
					depth: renderer.depth,
					stencil: renderer.stencil,
					framebufferScaleFactor: this.getFramebufferScaleFactor()
				};

				const glBaseLayer = new XRWebGLLayer( session, gl, layerInit );
				this._glBaseLayer = glBaseLayer;

				session.updateRenderState( { baseLayer: glBaseLayer } );

				renderer.setPixelRatio( 1 );
				renderer._setXRLayerSize( glBaseLayer.framebufferWidth, glBaseLayer.framebufferHeight );

				this._xrRenderTarget = new XRRenderTarget(
					glBaseLayer.framebufferWidth,
					glBaseLayer.framebufferHeight,
					{
						format: RGBAFormat,
						type: UnsignedByteType,
						colorSpace: renderer.outputColorSpace,
						stencilBuffer: renderer.stencil,
						resolveDepthBuffer: ( glBaseLayer.ignoreDepthValues === false ),
						resolveStencilBuffer: ( glBaseLayer.ignoreDepthValues === false ),
					}
				);

				this._xrRenderTarget._isOpaqueFramebuffer = true;
				this._referenceSpace = await session.requestReferenceSpace( this.getReferenceSpaceType() );

			}

			//

			this.setFoveation( this.getFoveation() );

			renderer._animation.setAnimationLoop( this._onAnimationFrame );
			renderer._animation.setContext( session );
			renderer._animation.start();

			this.isPresenting = true;

			this.dispatchEvent( { type: 'sessionstart' } );

		}

	}
```
</details>

### `XRManager.updateCamera(camera: PerspectiveCamera): void`

**JSDoc:**
```typescript
/**
	 * This method is called by the renderer per frame and updates the XR camera
	 * and it sub cameras based on the given camera. The given camera is the "user"
	 * camera created on application level and used for non-XR rendering.
	 *
	 * @param {PerspectiveCamera} camera - The camera.
	 */
```

**Parameters:**

- **`camera`** `PerspectiveCamera`

**Returns:** `void`

**Calls:**

- `session.updateRenderState`
- `updateCamera`
- `setProjectionFromUnion`
- `cameraXR.projectionMatrix.copy`
- `updateUserCamera`

**Internal Comments:**
```
// Note that the new renderState won't apply until the next frame. See #18320 (x4)
// inherit camera layers and enable eye layers (1 = left, 2 = right) (x5)
// update projection matrix for proper view frustum culling
// assume single camera setup (AR) (x5)
// update user camera and its children (x3)
```

<details><summary>Code</summary>

```typescript
updateCamera( camera ) {

		const session = this._session;

		if ( session === null ) return;

		const depthNear = camera.near;
		const depthFar = camera.far;

		const cameraXR = this._cameraXR;
		const cameraL = this._cameraL;
		const cameraR = this._cameraR;

		cameraXR.near = cameraR.near = cameraL.near = depthNear;
		cameraXR.far = cameraR.far = cameraL.far = depthFar;
		cameraXR.isMultiViewCamera = this._useMultiview;

		if ( this._currentDepthNear !== cameraXR.near || this._currentDepthFar !== cameraXR.far ) {

			// Note that the new renderState won't apply until the next frame. See #18320

			session.updateRenderState( {
				depthNear: cameraXR.near,
				depthFar: cameraXR.far
			} );

			this._currentDepthNear = cameraXR.near;
			this._currentDepthFar = cameraXR.far;

		}

		// inherit camera layers and enable eye layers (1 = left, 2 = right)
		cameraXR.layers.mask = camera.layers.mask | 0b110;
		cameraL.layers.mask = cameraXR.layers.mask & 0b011;
		cameraR.layers.mask = cameraXR.layers.mask & 0b101;


		const parent = camera.parent;
		const cameras = cameraXR.cameras;

		updateCamera( cameraXR, parent );

		for ( let i = 0; i < cameras.length; i ++ ) {

			updateCamera( cameras[ i ], parent );

		}

		// update projection matrix for proper view frustum culling

		if ( cameras.length === 2 ) {

			setProjectionFromUnion( cameraXR, cameraL, cameraR );

		} else {

			// assume single camera setup (AR)

			cameraXR.projectionMatrix.copy( cameraL.projectionMatrix );

		}

		// update user camera and its children

		updateUserCamera( camera, cameraXR, parent );


	}
```
</details>

### `XRManager._getController(index: number): WebXRController`

**JSDoc:**
```typescript
/**
	 * Returns a WebXR controller for the given controller index.
	 *
	 * @private
	 * @param {number} index - The controller index.
	 * @return {WebXRController} The XR controller.
	 */
```

**Parameters:**

- **`index`** `number`

**Returns:** `WebXRController`

<details><summary>Code</summary>

```typescript
_getController( index ) {

		let controller = this._controllers[ index ];

		if ( controller === undefined ) {

			controller = new WebXRController();
			this._controllers[ index ] = controller;

		}

		return controller;

	}
```
</details>

### `setProjectionFromUnion(camera: ArrayCamera, cameraL: PerspectiveCamera, cameraR: PerspectiveCamera): void`

**JSDoc:**
```typescript
/**
 * Assumes 2 cameras that are parallel and share an X-axis, and that
 * the cameras' projection and world matrices have already been set.
 * And that near and far planes are identical for both cameras.
 * Visualization of this technique: https://computergraphics.stackexchange.com/a/4765
 *
 * @param {ArrayCamera} camera - The camera to update.
 * @param {PerspectiveCamera} cameraL - The left camera.
 * @param {PerspectiveCamera} cameraR - The right camera.
 */
```

**Parameters:**

- **`camera`** `ArrayCamera`
- **`cameraL`** `PerspectiveCamera`
- **`cameraR`** `PerspectiveCamera`

**Returns:** `void`

**Calls:**

- `_cameraLPos.setFromMatrixPosition`
- `_cameraRPos.setFromMatrixPosition`
- `_cameraLPos.distanceTo`
- `cameraL.matrixWorld.decompose`
- `camera.translateX`
- `camera.translateZ`
- `camera.matrixWorld.compose`
- `camera.matrixWorldInverse.copy( camera.matrixWorld ).invert`
- `camera.projectionMatrix.copy`
- `camera.projectionMatrixInverse.copy`
- `camera.projectionMatrix.makePerspective`
- `camera.projectionMatrixInverse.copy( camera.projectionMatrix ).invert`

**Internal Comments:**
```
// VR systems will have identical far and near planes, and (x2)
// most likely identical top and bottom frustum extents. (x2)
// Use the left camera for these values. (x2)
// Calculate the new camera's position offset from the (x2)
// left camera. xOffset should be roughly half `ipd`. (x2)
// TODO: Better way to apply this offset? (x5)
// Check if the projection uses an infinite far plane.
// Use the projection matrix from the left eye. (x5)
// The camera offset is sufficient to include the view volumes (x5)
// of both eyes (assuming symmetric projections). (x5)
// Find the union of the frustum values of the cameras and scale (x2)
// the values so that the near plane's position does not change in world space, (x2)
// although must now be relative to the new union camera. (x2)
```

<details><summary>Code</summary>

```typescript
function setProjectionFromUnion( camera, cameraL, cameraR ) {

	_cameraLPos.setFromMatrixPosition( cameraL.matrixWorld );
	_cameraRPos.setFromMatrixPosition( cameraR.matrixWorld );

	const ipd = _cameraLPos.distanceTo( _cameraRPos );

	const projL = cameraL.projectionMatrix.elements;
	const projR = cameraR.projectionMatrix.elements;

	// VR systems will have identical far and near planes, and
	// most likely identical top and bottom frustum extents.
	// Use the left camera for these values.
	const near = projL[ 14 ] / ( projL[ 10 ] - 1 );
	const far = projL[ 14 ] / ( projL[ 10 ] + 1 );
	const topFov = ( projL[ 9 ] + 1 ) / projL[ 5 ];
	const bottomFov = ( projL[ 9 ] - 1 ) / projL[ 5 ];

	const leftFov = ( projL[ 8 ] - 1 ) / projL[ 0 ];
	const rightFov = ( projR[ 8 ] + 1 ) / projR[ 0 ];
	const left = near * leftFov;
	const right = near * rightFov;

	// Calculate the new camera's position offset from the
	// left camera. xOffset should be roughly half `ipd`.
	const zOffset = ipd / ( - leftFov + rightFov );
	const xOffset = zOffset * - leftFov;

	// TODO: Better way to apply this offset?
	cameraL.matrixWorld.decompose( camera.position, camera.quaternion, camera.scale );
	camera.translateX( xOffset );
	camera.translateZ( zOffset );
	camera.matrixWorld.compose( camera.position, camera.quaternion, camera.scale );
	camera.matrixWorldInverse.copy( camera.matrixWorld ).invert();

	// Check if the projection uses an infinite far plane.
	if ( projL[ 10 ] === - 1.0 ) {

		// Use the projection matrix from the left eye.
		// The camera offset is sufficient to include the view volumes
		// of both eyes (assuming symmetric projections).
		camera.projectionMatrix.copy( cameraL.projectionMatrix );
		camera.projectionMatrixInverse.copy( cameraL.projectionMatrixInverse );

	} else {

		// Find the union of the frustum values of the cameras and scale
		// the values so that the near plane's position does not change in world space,
		// although must now be relative to the new union camera.
		const near2 = near + zOffset;
		const far2 = far + zOffset;
		const left2 = left - xOffset;
		const right2 = right + ( ipd - xOffset );
		const top2 = topFov * far / far2 * near2;
		const bottom2 = bottomFov * far / far2 * near2;

		camera.projectionMatrix.makePerspective( left2, right2, top2, bottom2, near2, far2 );
		camera.projectionMatrixInverse.copy( camera.projectionMatrix ).invert();

	}

}
```
</details>

### `updateCamera(camera: Camera, parent: Object3D): void`

**JSDoc:**
```typescript
/**
 * Updates the world matrices for the given camera based on the parent 3D object.
 *
 * @inner
 * @param {Camera} camera - The camera to update.
 * @param {Object3D} parent - The parent 3D object.
 */
```

**Parameters:**

- **`camera`** `Camera`
- **`parent`** `Object3D`

**Returns:** `void`

**Calls:**

- `camera.matrixWorld.copy`
- `camera.matrixWorld.multiplyMatrices`
- `camera.matrixWorldInverse.copy( camera.matrixWorld ).invert`

<details><summary>Code</summary>

```typescript
function updateCamera( camera, parent ) {

	if ( parent === null ) {

		camera.matrixWorld.copy( camera.matrix );

	} else {

		camera.matrixWorld.multiplyMatrices( parent.matrixWorld, camera.matrix );

	}

	camera.matrixWorldInverse.copy( camera.matrixWorld ).invert();

}
```
</details>

### `updateUserCamera(camera: Camera, cameraXR: ArrayCamera, parent: Object3D): void`

**JSDoc:**
```typescript
/**
 * Updates the given camera with the transformation of the XR camera and parent object.
 *
 * @inner
 * @param {Camera} camera - The camera to update.
 * @param {ArrayCamera} cameraXR - The XR camera.
 * @param {Object3D} parent - The parent 3D object.
 */
```

**Parameters:**

- **`camera`** `Camera`
- **`cameraXR`** `ArrayCamera`
- **`parent`** `Object3D`

**Returns:** `void`

**Calls:**

- `camera.matrix.copy`
- `camera.matrix.invert`
- `camera.matrix.multiply`
- `camera.matrix.decompose`
- `camera.updateMatrixWorld`
- `camera.projectionMatrix.copy`
- `camera.projectionMatrixInverse.copy`
- `Math.atan`

<details><summary>Code</summary>

```typescript
function updateUserCamera( camera, cameraXR, parent ) {

	if ( parent === null ) {

		camera.matrix.copy( cameraXR.matrixWorld );

	} else {

		camera.matrix.copy( parent.matrixWorld );
		camera.matrix.invert();
		camera.matrix.multiply( cameraXR.matrixWorld );

	}

	camera.matrix.decompose( camera.position, camera.quaternion, camera.scale );
	camera.updateMatrixWorld( true );

	camera.projectionMatrix.copy( cameraXR.projectionMatrix );
	camera.projectionMatrixInverse.copy( cameraXR.projectionMatrixInverse );

	if ( camera.isPerspectiveCamera ) {

		camera.fov = RAD2DEG * 2 * Math.atan( 1 / camera.projectionMatrix.elements[ 5 ] );
		camera.zoom = 1;

	}

}
```
</details>

### `onSessionEvent(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `this._controllerInputSources.indexOf`
- `this.getReferenceSpace`
- `controller.update`
- `controller.dispatchEvent`

<details><summary>Code</summary>

```typescript
function onSessionEvent( event ) {

	const controllerIndex = this._controllerInputSources.indexOf( event.inputSource );

	if ( controllerIndex === - 1 ) {

		return;

	}

	const controller = this._controllers[ controllerIndex ];

	if ( controller !== undefined ) {

		const referenceSpace = this.getReferenceSpace();

		controller.update( event.inputSource, event.frame, referenceSpace );
		controller.dispatchEvent( { type: event.type, data: event.inputSource } );

	}

}
```
</details>

### `onSessionEnd(): void`

**Returns:** `void`

**Calls:**

- `session.removeEventListener`
- `this._controllers[ i ].disconnect`
- `renderer._resetXRState`
- `renderer._animation.stop`
- `renderer._animation.setAnimationLoop`
- `renderer._animation.setContext`
- `renderer._animation.start`
- `renderer.setPixelRatio`
- `renderer.setSize`
- `this.dispatchEvent`

**Internal Comments:**
```
// restore framebuffer/rendering state (x4)
// switch layers back to emulated
// Recreate layer render target to reset state (x4)
// (x4)
```

<details><summary>Code</summary>

```typescript
function onSessionEnd() {

	const session = this._session;
	const renderer = this._renderer;

	session.removeEventListener( 'select', this._onSessionEvent );
	session.removeEventListener( 'selectstart', this._onSessionEvent );
	session.removeEventListener( 'selectend', this._onSessionEvent );
	session.removeEventListener( 'squeeze', this._onSessionEvent );
	session.removeEventListener( 'squeezestart', this._onSessionEvent );
	session.removeEventListener( 'squeezeend', this._onSessionEvent );
	session.removeEventListener( 'end', this._onSessionEnd );
	session.removeEventListener( 'inputsourceschange', this._onInputSourcesChange );

	for ( let i = 0; i < this._controllers.length; i ++ ) {

		const inputSource = this._controllerInputSources[ i ];

		if ( inputSource === null ) continue;

		this._controllerInputSources[ i ] = null;

		this._controllers[ i ].disconnect( inputSource );

	}

	this._currentDepthNear = null;
	this._currentDepthFar = null;

	// restore framebuffer/rendering state

	renderer._resetXRState();

	this._session = null;
	this._xrRenderTarget = null;

	// switch layers back to emulated
	if ( this._supportsLayers === true ) {

		for ( const layer of this._layers ) {

			// Recreate layer render target to reset state
			layer.renderTarget = new XRRenderTarget(
				layer.pixelwidth,
				layer.pixelheight,
				{
					format: RGBAFormat,
					type: UnsignedByteType,
					depthTexture: new DepthTexture(
						layer.pixelwidth,
						layer.pixelheight,
						layer.stencilBuffer ? UnsignedInt248Type : UnsignedIntType,
						undefined,
						undefined,
						undefined,
						undefined,
						undefined,
						undefined,
						layer.stencilBuffer ? DepthStencilFormat : DepthFormat
					),
					stencilBuffer: layer.stencilBuffer,
					resolveDepthBuffer: false,
					resolveStencilBuffer: false
				} );

			layer.renderTarget.isXRRenderTarget = false;

			layer.plane.material = layer.material;
			layer.material.map = layer.renderTarget.texture;
			layer.material.map.offset.y = 1;
			layer.material.map.repeat.y = - 1;
			delete layer.xrlayer;

		}

	}

	//

	this.isPresenting = false;
	this._useMultiview = false;

	renderer._animation.stop();
	renderer._animation.setAnimationLoop( this._currentAnimationLoop );
	renderer._animation.setContext( this._currentAnimationContext );
	renderer._animation.start();

	renderer.setPixelRatio( this._currentPixelRatio );
	renderer.setSize( this._currentSize.width, this._currentSize.height, false );

	this.dispatchEvent( { type: 'sessionend' } );

}
```
</details>

### `onInputSourcesChange(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `controllerInputSources.indexOf`
- `controllers[ index ].disconnect`
- `controllerInputSources.push`
- `controller.connect`

**Internal Comments:**
```
// Notify disconnected
// Notify connected
// Assign input source a controller that currently has no input source
// If all controllers do currently receive input we ignore new ones
```

<details><summary>Code</summary>

```typescript
function onInputSourcesChange( event ) {

	const controllers = this._controllers;
	const controllerInputSources = this._controllerInputSources;

	// Notify disconnected

	for ( let i = 0; i < event.removed.length; i ++ ) {

		const inputSource = event.removed[ i ];
		const index = controllerInputSources.indexOf( inputSource );

		if ( index >= 0 ) {

			controllerInputSources[ index ] = null;
			controllers[ index ].disconnect( inputSource );

		}

	}

	// Notify connected

	for ( let i = 0; i < event.added.length; i ++ ) {

		const inputSource = event.added[ i ];

		let controllerIndex = controllerInputSources.indexOf( inputSource );

		if ( controllerIndex === - 1 ) {

			// Assign input source a controller that currently has no input source

			for ( let i = 0; i < controllers.length; i ++ ) {

				if ( i >= controllerInputSources.length ) {

					controllerInputSources.push( inputSource );
					controllerIndex = i;
					break;

				} else if ( controllerInputSources[ i ] === null ) {

					controllerInputSources[ i ] = inputSource;
					controllerIndex = i;
					break;

				}

			}

			// If all controllers do currently receive input we ignore new ones

			if ( controllerIndex === - 1 ) break;

		}

		const controller = controllers[ controllerIndex ];

		if ( controller ) {

			controller.connect( inputSource );

		}

	}

}
```
</details>

### `createXRLayer(layer: any): any`

**Parameters:**

- **`layer`** `any`

**Returns:** `any`

**Calls:**

- `this._glBinding.createQuadLayer`
- `this._glBinding.createCylinderLayer`

<details><summary>Code</summary>

```typescript
function createXRLayer( layer ) {

	if ( layer.type === 'quad' ) {

		return this._glBinding.createQuadLayer( {
			transform: new XRRigidTransform( layer.translation, layer.quaternion ),
			width: layer.width / 2,
			height: layer.height / 2,
			space: this._referenceSpace,
			viewPixelWidth: layer.pixelwidth,
			viewPixelHeight: layer.pixelheight,
			clearOnAccess: false
		} );

	} else {

		return this._glBinding.createCylinderLayer( {
			transform: new XRRigidTransform( layer.translation, layer.quaternion ),
			radius: layer.radius,
			centralAngle: layer.centralAngle,
			aspectRatio: layer.aspectRatio,
			space: this._referenceSpace,
			viewPixelWidth: layer.pixelwidth,
			viewPixelHeight: layer.pixelheight,
			clearOnAccess: false
		} );

	}

}
```
</details>

### `onAnimationFrame(time: any, frame: any): void`

**Parameters:**

- **`time`** `any`
- **`frame`** `any`

**Returns:** `void`

**Calls:**

- `this.getReferenceSpace`
- `frame.getViewerPose`
- `backend.setXRTarget`
- `this._glBinding.getViewSubImage`
- `backend.setXRRenderTargetTextures`
- `glBaseLayer.getViewport`
- `camera.layers.enable`
- `camera.matrix.fromArray`
- `camera.matrix.decompose`
- `camera.projectionMatrix.fromArray`
- `camera.projectionMatrixInverse.copy( camera.projectionMatrix ).invert`
- `camera.viewport.set`
- `cameraXR.matrix.copy`
- `cameraXR.matrix.decompose`
- `cameraXR.cameras.push`
- `renderer.setOutputRenderTarget`
- `controller.update`
- `this._currentAnimationLoop`
- `this.dispatchEvent`

**Internal Comments:**
```
// check if it's necessary to rebuild cameraXR's camera list
// For side-by-side projection, we only produce a single texture for both eyes.
//
```

<details><summary>Code</summary>

```typescript
function onAnimationFrame( time, frame ) {

	if ( frame === undefined ) return;

	const cameraXR = this._cameraXR;
	const renderer = this._renderer;
	const backend = renderer.backend;

	const glBaseLayer = this._glBaseLayer;

	const referenceSpace = this.getReferenceSpace();
	const pose = frame.getViewerPose( referenceSpace );

	this._xrFrame = frame;

	if ( pose !== null ) {

		const views = pose.views;

		if ( this._glBaseLayer !== null ) {

			backend.setXRTarget( glBaseLayer.framebuffer );

		}

		let cameraXRNeedsUpdate = false;

		// check if it's necessary to rebuild cameraXR's camera list

		if ( views.length !== cameraXR.cameras.length ) {

			cameraXR.cameras.length = 0;
			cameraXRNeedsUpdate = true;

		}

		for ( let i = 0; i < views.length; i ++ ) {

			const view = views[ i ];

			let viewport;

			if ( this._useLayers === true ) {

				const glSubImage = this._glBinding.getViewSubImage( this._glProjLayer, view );
				viewport = glSubImage.viewport;

				// For side-by-side projection, we only produce a single texture for both eyes.
				if ( i === 0 ) {

					backend.setXRRenderTargetTextures(
						this._xrRenderTarget,
						glSubImage.colorTexture,
						( this._glProjLayer.ignoreDepthValues && ! this._useMultiview ) ? undefined : glSubImage.depthStencilTexture
					);

				}

			} else {

				viewport = glBaseLayer.getViewport( view );

			}

			let camera = this._cameras[ i ];

			if ( camera === undefined ) {

				camera = new PerspectiveCamera();
				camera.layers.enable( i );
				camera.viewport = new Vector4();
				this._cameras[ i ] = camera;

			}

			camera.matrix.fromArray( view.transform.matrix );
			camera.matrix.decompose( camera.position, camera.quaternion, camera.scale );
			camera.projectionMatrix.fromArray( view.projectionMatrix );
			camera.projectionMatrixInverse.copy( camera.projectionMatrix ).invert();
			camera.viewport.set( viewport.x, viewport.y, viewport.width, viewport.height );

			if ( i === 0 ) {

				cameraXR.matrix.copy( camera.matrix );
				cameraXR.matrix.decompose( cameraXR.position, cameraXR.quaternion, cameraXR.scale );

			}

			if ( cameraXRNeedsUpdate === true ) {

				cameraXR.cameras.push( camera );

			}

		}

		renderer.setOutputRenderTarget( this._xrRenderTarget );

	}

	//

	for ( let i = 0; i < this._controllers.length; i ++ ) {

		const inputSource = this._controllerInputSources[ i ];
		const controller = this._controllers[ i ];

		if ( inputSource !== null && controller !== undefined ) {

			controller.update( inputSource, frame, referenceSpace );

		}

	}

	if ( this._currentAnimationLoop ) this._currentAnimationLoop( time, frame );

	if ( frame.detectedPlanes ) {

		this.dispatchEvent( { type: 'planesdetected', data: frame } );

	}

	this._xrFrame = null;

}
```
</details>


---

## Classes

### `XRManager`

<details><summary>Class Code</summary>

```ts
class XRManager extends EventDispatcher {

	/**
	 * Constructs a new XR manager.
	 *
	 * @param {Renderer} renderer - The renderer.
	 * @param {boolean} [multiview=false] - Enables multiview if the device supports it.
	 */
	constructor( renderer, multiview = false ) {

		super();

		/**
		 * This flag globally enables XR rendering.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.enabled = false;

		/**
		 * Whether the XR device is currently presenting or not.
		 *
		 * @type {boolean}
		 * @default false
		 * @readonly
		 */
		this.isPresenting = false;

		/**
		 * Whether the XR camera should automatically be updated or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.cameraAutoUpdate = true;

		/**
		 * The renderer.
		 *
		 * @private
		 * @type {Renderer}
		 */
		this._renderer = renderer;

		// camera

		/**
		 * Represents the camera for the left eye.
		 *
		 * @private
		 * @type {PerspectiveCamera}
		 */
		this._cameraL = new PerspectiveCamera();
		this._cameraL.viewport = new Vector4();

		/**
		 * Represents the camera for the right eye.
		 *
		 * @private
		 * @type {PerspectiveCamera}
		 */
		this._cameraR = new PerspectiveCamera();
		this._cameraR.viewport = new Vector4();

		/**
		 * A list of cameras used for rendering the XR views.
		 *
		 * @private
		 * @type {Array<Camera>}
		 */
		this._cameras = [ this._cameraL, this._cameraR ];

		/**
		 * The main XR camera.
		 *
		 * @private
		 * @type {ArrayCamera}
		 */
		this._cameraXR = new ArrayCamera();

		/**
		 * The current near value of the XR camera.
		 *
		 * @private
		 * @type {?number}
		 * @default null
		 */
		this._currentDepthNear = null;

		/**
		 * The current far value of the XR camera.
		 *
		 * @private
		 * @type {?number}
		 * @default null
		 */
		this._currentDepthFar = null;

		/**
		 * A list of WebXR controllers requested by the application.
		 *
		 * @private
		 * @type {Array<WebXRController>}
		 */
		this._controllers = [];

		/**
		 * A list of XR input source. Each input source belongs to
		 * an instance of WebXRController.
		 *
		 * @private
		 * @type {Array<XRInputSource?>}
		 */
		this._controllerInputSources = [];

		/**
		 * The XR render target that represents the rendering destination
		 * during an active XR session.
		 *
		 * @private
		 * @type {?RenderTarget}
		 * @default null
		 */
		this._xrRenderTarget = null;

		/**
		 * An array holding all the non-projection layers
		 *
		 * @private
		 * @type {Array<Object>}
		 * @default []
		 */
		this._layers = [];

		/**
		 * Whether the device has support for all layer types.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this._supportsLayers = false;

		/**
		 * Whether the device supports binding gl objects.
		 *
		 * @private
		 * @type {boolean}
		 * @readonly
		 */
		this._supportsGlBinding = typeof XRWebGLBinding !== 'undefined';

		this._frameBufferTargets = null;

		/**
		 * Helper function to create native WebXR Layer.
		 *
		 * @private
		 * @type {Function}
		 */
		this._createXRLayer = createXRLayer.bind( this );

		/**
		* The current WebGL context.
		*
		* @private
		* @type {?WebGL2RenderingContext}
		* @default null
		*/
		this._gl = null;

		/**
		 * The current animation context.
		 *
		 * @private
		 * @type {?Window}
		 * @default null
		 */
		this._currentAnimationContext = null;

		/**
		 * The current animation loop.
		 *
		 * @private
		 * @type {?Function}
		 * @default null
		 */
		this._currentAnimationLoop = null;

		/**
		 * The current pixel ratio.
		 *
		 * @private
		 * @type {?number}
		 * @default null
		 */
		this._currentPixelRatio = null;

		/**
		 * The current size of the renderer's canvas
		 * in logical pixel unit.
		 *
		 * @private
		 * @type {Vector2}
		 */
		this._currentSize = new Vector2();

		/**
		 * The default event listener for handling events inside a XR session.
		 *
		 * @private
		 * @type {Function}
		 */
		this._onSessionEvent = onSessionEvent.bind( this );

		/**
		 * The event listener for handling the end of a XR session.
		 *
		 * @private
		 * @type {Function}
		 */
		this._onSessionEnd = onSessionEnd.bind( this );

		/**
		 * The event listener for handling the `inputsourceschange` event.
		 *
		 * @private
		 * @type {Function}
		 */
		this._onInputSourcesChange = onInputSourcesChange.bind( this );

		/**
		 * The animation loop which is used as a replacement for the default
		 * animation loop of the application. It is only used when a XR session
		 * is active.
		 *
		 * @private
		 * @type {Function}
		 */
		this._onAnimationFrame = onAnimationFrame.bind( this );

		/**
		 * The current XR reference space.
		 *
		 * @private
		 * @type {?XRReferenceSpace}
		 * @default null
		 */
		this._referenceSpace = null;

		/**
		 * The current XR reference space type.
		 *
		 * @private
		 * @type {XRReferenceSpaceType}
		 * @default 'local-floor'
		 */
		this._referenceSpaceType = 'local-floor';

		/**
		 * A custom reference space defined by the application.
		 *
		 * @private
		 * @type {?XRReferenceSpace}
		 * @default null
		 */
		this._customReferenceSpace = null;

		/**
		 * The framebuffer scale factor.
		 *
		 * @private
		 * @type {number}
		 * @default 1
		 */
		this._framebufferScaleFactor = 1;

		/**
		 * The foveation factor.
		 *
		 * @private
		 * @type {number}
		 * @default 1
		 */
		this._foveation = 1.0;

		/**
		 * A reference to the current XR session.
		 *
		 * @private
		 * @type {?XRSession}
		 * @default null
		 */
		this._session = null;

		/**
		 * A reference to the current XR base layer.
		 *
		 * @private
		 * @type {?XRWebGLLayer}
		 * @default null
		 */
		this._glBaseLayer = null;

		/**
		 * A reference to the current XR binding.
		 *
		 * @private
		 * @type {?XRWebGLBinding}
		 * @default null
		 */
		this._glBinding = null;

		/**
		 * A reference to the current XR projection layer.
		 *
		 * @private
		 * @type {?XRProjectionLayer}
		 * @default null
		 */
		this._glProjLayer = null;

		/**
		 * A reference to the current XR frame.
		 *
		 * @private
		 * @type {?XRFrame}
		 * @default null
		 */
		this._xrFrame = null;

		/**
		 * Whether to use the WebXR Layers API or not.
		 *
		 * @private
		 * @type {boolean}
		 * @readonly
		 */
		this._useLayers = ( this._supportsGlBinding && 'createProjectionLayer' in XRWebGLBinding.prototype ); // eslint-disable-line compat/compat

		/**
		 * Whether the usage of multiview has been requested by the application or not.
		 *
		 * @private
		 * @type {boolean}
		 * @default false
		 * @readonly
		 */
		this._useMultiviewIfPossible = multiview;

		/**
		 * Whether the usage of multiview is actually enabled. This flag only evaluates to `true`
		 * if multiview has been requested by the application and the `OVR_multiview2` is available.
		 *
		 * @private
		 * @type {boolean}
		 * @readonly
		 */
		this._useMultiview = false;

	}

	/**
	 * Returns an instance of `THREE.Group` that represents the transformation
	 * of a XR controller in target ray space. The requested controller is defined
	 * by the given index.
	 *
	 * @param {number} index - The index of the XR controller.
	 * @return {Group} A group that represents the controller's transformation.
	 */
	getController( index ) {

		const controller = this._getController( index );

		return controller.getTargetRaySpace();

	}

	/**
	 * Returns an instance of `THREE.Group` that represents the transformation
	 * of a XR controller in grip space. The requested controller is defined
	 * by the given index.
	 *
	 * @param {number} index - The index of the XR controller.
	 * @return {Group} A group that represents the controller's transformation.
	 */
	getControllerGrip( index ) {

		const controller = this._getController( index );

		return controller.getGripSpace();

	}

	/**
	 * Returns an instance of `THREE.Group` that represents the transformation
	 * of a XR controller in hand space. The requested controller is defined
	 * by the given index.
	 *
	 * @param {number} index - The index of the XR controller.
	 * @return {Group} A group that represents the controller's transformation.
	 */
	getHand( index ) {

		const controller = this._getController( index );

		return controller.getHandSpace();

	}

	/**
	 * Returns the foveation value.
	 *
	 * @return {number|undefined} The foveation value. Returns `undefined` if no base or projection layer is defined.
	 */
	getFoveation() {

		if ( this._glProjLayer === null && this._glBaseLayer === null ) {

			return undefined;

		}

		return this._foveation;

	}

	/**
	 * Sets the foveation value.
	 *
	 * @param {number} foveation - A number in the range `[0,1]` where `0` means no foveation (full resolution)
	 * and `1` means maximum foveation (the edges render at lower resolution).
	 */
	setFoveation( foveation ) {

		this._foveation = foveation;

		if ( this._glProjLayer !== null ) {

			this._glProjLayer.fixedFoveation = foveation;

		}

		if ( this._glBaseLayer !== null && this._glBaseLayer.fixedFoveation !== undefined ) {

			this._glBaseLayer.fixedFoveation = foveation;

		}

	}

	/**
	 * Returns the framebuffer scale factor.
	 *
	 * @return {number} The framebuffer scale factor.
	 */
	getFramebufferScaleFactor() {

		return this._framebufferScaleFactor;

	}

	/**
	 * Sets the framebuffer scale factor.
	 *
	 * This method can not be used during a XR session.
	 *
	 * @param {number} factor - The framebuffer scale factor.
	 */
	setFramebufferScaleFactor( factor ) {

		this._framebufferScaleFactor = factor;

		if ( this.isPresenting === true ) {

			console.warn( 'THREE.XRManager: Cannot change framebuffer scale while presenting.' );

		}

	}

	/**
	 * Returns the reference space type.
	 *
	 * @return {XRReferenceSpaceType} The reference space type.
	 */
	getReferenceSpaceType() {

		return this._referenceSpaceType;

	}

	/**
	 * Sets the reference space type.
	 *
	 * This method can not be used during a XR session.
	 *
	 * @param {XRReferenceSpaceType} type - The reference space type.
	 */
	setReferenceSpaceType( type ) {

		this._referenceSpaceType = type;

		if ( this.isPresenting === true ) {

			console.warn( 'THREE.XRManager: Cannot change reference space type while presenting.' );

		}

	}

	/**
	 * Returns the XR reference space.
	 *
	 * @return {XRReferenceSpace} The XR reference space.
	 */
	getReferenceSpace() {

		return this._customReferenceSpace || this._referenceSpace;

	}

	/**
	 * Sets a custom XR reference space.
	 *
	 * @param {XRReferenceSpace} space - The XR reference space.
	 */
	setReferenceSpace( space ) {

		this._customReferenceSpace = space;

	}

	/**
	 * Returns the XR camera.
	 *
	 * @return {ArrayCamera} The XR camera.
	 */
	getCamera() {

		return this._cameraXR;

	}

	/**
	 * Returns the environment blend mode from the current XR session.
	 *
	 * @return {'opaque'|'additive'|'alpha-blend'|undefined} The environment blend mode. Returns `undefined` when used outside of a XR session.
	 */
	getEnvironmentBlendMode() {

		if ( this._session !== null ) {

			return this._session.environmentBlendMode;

		}

	}

	/**
	 * Returns the current XR frame.
	 *
	 * @return {?XRFrame} The XR frame. Returns `null` when used outside a XR session.
	 */
	getFrame() {

		return this._xrFrame;

	}

	/**
	 * Returns `true` if the engine renders to a multiview target.
	 *
	 * @return {boolean} Whether the engine renders to a multiview render target or not.
	 */
	useMultiview() {

		return this._useMultiview;

	}

	/**
	 * This method can be used in XR applications to create a quadratic layer that presents a separate
	 * rendered scene.
	 *
	 * @param {number} width - The width of the layer plane in world units.
	 * @param {number} height - The height of the layer plane in world units.
	 * @param {Vector3} translation - The position/translation of the layer plane in world units.
	 * @param {Quaternion} quaternion - The orientation of the layer plane expressed as a quaternion.
	 * @param {number} pixelwidth - The width of the layer's render target in pixels.
	 * @param {number} pixelheight - The height of the layer's render target in pixels.
	 * @param {Function} rendercall - A callback function that renders the layer. Similar to code in
	 * the default animation loop, this method can be used to update/transform 3D object in the layer's scene.
	 * @param {Object} [attributes={}] - Allows to configure the layer's render target.
	 * @return {Mesh} A mesh representing the quadratic XR layer. This mesh should be added to the XR scene.
	 */
	createQuadLayer( width, height, translation, quaternion, pixelwidth, pixelheight, rendercall, attributes = {} ) {

		const geometry = new PlaneGeometry( width, height );
		const renderTarget = new XRRenderTarget(
			pixelwidth,
			pixelheight,
			{
				format: RGBAFormat,
				type: UnsignedByteType,
				depthTexture: new DepthTexture(
					pixelwidth,
					pixelheight,
					attributes.stencil ? UnsignedInt248Type : UnsignedIntType,
					undefined,
					undefined,
					undefined,
					undefined,
					undefined,
					undefined,
					attributes.stencil ? DepthStencilFormat : DepthFormat
				),
				stencilBuffer: attributes.stencil,
				resolveDepthBuffer: false,
				resolveStencilBuffer: false
			} );

		renderTarget._autoAllocateDepthBuffer = true;

		const material = new MeshBasicMaterial( { color: 0xffffff, side: FrontSide } );
		material.map = renderTarget.texture;
		material.map.offset.y = 1;
		material.map.repeat.y = - 1;
		const plane = new Mesh( geometry, material );
		plane.position.copy( translation );
		plane.quaternion.copy( quaternion );

		const layer = {
			type: 'quad',
			width: width,
			height: height,
			translation: translation,
			quaternion: quaternion,
			pixelwidth: pixelwidth,
			pixelheight: pixelheight,
			plane: plane,
			material: material,
			rendercall: rendercall,
			renderTarget: renderTarget };

		this._layers.push( layer );

		if ( this._session !== null ) {

			layer.plane.material = new MeshBasicMaterial( { color: 0xffffff, side: FrontSide } );
			layer.plane.material.blending = CustomBlending;
			layer.plane.material.blendEquation = AddEquation;
			layer.plane.material.blendSrc = ZeroFactor;
			layer.plane.material.blendDst = ZeroFactor;

			layer.xrlayer = this._createXRLayer( layer );

			const xrlayers = this._session.renderState.layers;
			xrlayers.unshift( layer.xrlayer );
			this._session.updateRenderState( { layers: xrlayers } );

		} else {

			renderTarget.isXRRenderTarget = false;

		}

		return plane;

	}

	/**
	 * This method can be used in XR applications to create a cylindrical layer that presents a separate
	 * rendered scene.
	 *
	 * @param {number} radius - The radius of the cylinder in world units.
	 * @param {number} centralAngle - The central angle of the cylinder in radians.
	 * @param {number} aspectratio - The aspect ratio.
	 * @param {Vector3} translation - The position/translation of the layer plane in world units.
	 * @param {Quaternion} quaternion - The orientation of the layer plane expressed as a quaternion.
	 * @param {number} pixelwidth - The width of the layer's render target in pixels.
	 * @param {number} pixelheight - The height of the layer's render target in pixels.
	 * @param {Function} rendercall - A callback function that renders the layer. Similar to code in
	 * the default animation loop, this method can be used to update/transform 3D object in the layer's scene.
	 * @param {Object} [attributes={}] - Allows to configure the layer's render target.
	 * @return {Mesh} A mesh representing the cylindrical XR layer. This mesh should be added to the XR scene.
	 */
	createCylinderLayer( radius, centralAngle, aspectratio, translation, quaternion, pixelwidth, pixelheight, rendercall, attributes = {} ) {

		const geometry = new CylinderGeometry( radius, radius, radius * centralAngle / aspectratio, 64, 64, true, Math.PI - centralAngle / 2, centralAngle );
		const renderTarget = new XRRenderTarget(
			pixelwidth,
			pixelheight,
			{
				format: RGBAFormat,
				type: UnsignedByteType,
				depthTexture: new DepthTexture(
					pixelwidth,
					pixelheight,
					attributes.stencil ? UnsignedInt248Type : UnsignedIntType,
					undefined,
					undefined,
					undefined,
					undefined,
					undefined,
					undefined,
					attributes.stencil ? DepthStencilFormat : DepthFormat
				),
				stencilBuffer: attributes.stencil,
				resolveDepthBuffer: false,
				resolveStencilBuffer: false
			} );

		renderTarget._autoAllocateDepthBuffer = true;

		const material = new MeshBasicMaterial( { color: 0xffffff, side: BackSide } );
		material.map = renderTarget.texture;
		material.map.offset.y = 1;
		material.map.repeat.y = - 1;
		const plane = new Mesh( geometry, material );
		plane.position.copy( translation );
		plane.quaternion.copy( quaternion );

		const layer = {
			type: 'cylinder',
			radius: radius,
			centralAngle: centralAngle,
			aspectratio: aspectratio,
			translation: translation,
			quaternion: quaternion,
			pixelwidth: pixelwidth,
			pixelheight: pixelheight,
			plane: plane,
			material: material,
			rendercall: rendercall,
			renderTarget: renderTarget };

		this._layers.push( layer );

		if ( this._session !== null ) {

			layer.plane.material = new MeshBasicMaterial( { color: 0xffffff, side: BackSide } );
			layer.plane.material.blending = CustomBlending;
			layer.plane.material.blendEquation = AddEquation;
			layer.plane.material.blendSrc = ZeroFactor;
			layer.plane.material.blendDst = ZeroFactor;

			layer.xrlayer = this._createXRLayer( layer );

			const xrlayers = this._session.renderState.layers;
			xrlayers.unshift( layer.xrlayer );
			this._session.updateRenderState( { layers: xrlayers } );

		} else {

			renderTarget.isXRRenderTarget = false;

		}

		return plane;

	}

	/**
	 * Renders the XR layers that have been previously added to the scene.
	 *
	 * This method is usually called in your animation loop before rendering
	 * the actual scene via `renderer.render( scene, camera );`.
	 */
	renderLayers( ) {

		const translationObject = new Vector3();
		const quaternionObject = new Quaternion();
		const renderer = this._renderer;

		const wasPresenting = this.isPresenting;
		const rendererOutputTarget = renderer.getOutputRenderTarget();
		const rendererFramebufferTarget = renderer._frameBufferTarget;
		this.isPresenting = false;

		const rendererSize = new Vector2();
		renderer.getSize( rendererSize );
		const rendererQuad = renderer._quad;

		for ( const layer of this._layers ) {

			layer.renderTarget.isXRRenderTarget = this._session !== null;
			layer.renderTarget._hasExternalTextures = layer.renderTarget.isXRRenderTarget;

			if ( layer.renderTarget.isXRRenderTarget && this._supportsLayers ) {

				layer.xrlayer.transform = new XRRigidTransform( layer.plane.getWorldPosition( translationObject ), layer.plane.getWorldQuaternion( quaternionObject ) );

				const glSubImage = this._glBinding.getSubImage( layer.xrlayer, this._xrFrame );
				renderer.backend.setXRRenderTargetTextures(
					layer.renderTarget,
					glSubImage.colorTexture,
					undefined );

				renderer._setXRLayerSize( layer.renderTarget.width, layer.renderTarget.height );
				renderer.setOutputRenderTarget( layer.renderTarget );
				renderer.setRenderTarget( null );
				renderer._frameBufferTarget = null;

				this._frameBufferTargets || ( this._frameBufferTargets = new WeakMap() );
				const { frameBufferTarget, quad } = this._frameBufferTargets.get( layer.renderTarget ) || { frameBufferTarget: null, quad: null };
				if ( ! frameBufferTarget ) {

					renderer._quad = new QuadMesh( new NodeMaterial() );
					this._frameBufferTargets.set( layer.renderTarget, { frameBufferTarget: renderer._getFrameBufferTarget(), quad: renderer._quad } );

				} else {

					renderer._frameBufferTarget = frameBufferTarget;
					renderer._quad = quad;

				}

				layer.rendercall();

				renderer._frameBufferTarget = null;

			} else {

				renderer.setRenderTarget( layer.renderTarget );
				layer.rendercall();

			}

		}

		renderer.setRenderTarget( null );
		renderer.setOutputRenderTarget( rendererOutputTarget );
		renderer._frameBufferTarget = rendererFramebufferTarget;
		renderer._setXRLayerSize( rendererSize.x, rendererSize.y );
		renderer._quad = rendererQuad;
		this.isPresenting = wasPresenting;

	}


	/**
	 * Returns the current XR session.
	 *
	 * @return {?XRSession} The XR session. Returns `null` when used outside a XR session.
	 */
	getSession() {

		return this._session;

	}

	/**
	 * After a XR session has been requested usually with one of the `*Button` modules, it
	 * is injected into the renderer with this method. This method triggers the start of
	 * the actual XR rendering.
	 *
	 * @async
	 * @param {XRSession} session - The XR session to set.
	 * @return {Promise} A Promise that resolves when the session has been set.
	 */
	async setSession( session ) {

		const renderer = this._renderer;
		const backend = renderer.backend;

		this._gl = renderer.getContext();
		const gl = this._gl;
		const attributes = gl.getContextAttributes();

		this._session = session;

		if ( session !== null ) {

			if ( backend.isWebGPUBackend === true ) throw new Error( 'THREE.XRManager: XR is currently not supported with a WebGPU backend. Use WebGL by passing "{ forceWebGL: true }" to the constructor of the renderer.' );

			session.addEventListener( 'select', this._onSessionEvent );
			session.addEventListener( 'selectstart', this._onSessionEvent );
			session.addEventListener( 'selectend', this._onSessionEvent );
			session.addEventListener( 'squeeze', this._onSessionEvent );
			session.addEventListener( 'squeezestart', this._onSessionEvent );
			session.addEventListener( 'squeezeend', this._onSessionEvent );
			session.addEventListener( 'end', this._onSessionEnd );
			session.addEventListener( 'inputsourceschange', this._onInputSourcesChange );

			await backend.makeXRCompatible();

			this._currentPixelRatio = renderer.getPixelRatio();
			renderer.getSize( this._currentSize );

			this._currentAnimationContext = renderer._animation.getContext();
			this._currentAnimationLoop = renderer._animation.getAnimationLoop();
			renderer._animation.stop();

			//

			if ( this._supportsGlBinding ) {

				const glBinding = new XRWebGLBinding( session, gl );
				this._glBinding = glBinding;

			}

			//

			if ( this._useLayers === true ) {

				// default path using XRProjectionLayer

				let depthFormat = null;
				let depthType = null;
				let glDepthFormat = null;

				if ( renderer.depth ) {

					glDepthFormat = renderer.stencil ? gl.DEPTH24_STENCIL8 : gl.DEPTH_COMPONENT24;
					depthFormat = renderer.stencil ? DepthStencilFormat : DepthFormat;
					depthType = renderer.stencil ? UnsignedInt248Type : UnsignedIntType;

				}

				const projectionlayerInit = {
					colorFormat: gl.RGBA8,
					depthFormat: glDepthFormat,
					scaleFactor: this._framebufferScaleFactor,
					clearOnAccess: false
				};

				if ( this._useMultiviewIfPossible && renderer.hasFeature( 'OVR_multiview2' ) ) {

					projectionlayerInit.textureType = 'texture-array';
					this._useMultiview = true;

				}

				const glProjLayer = this._glBinding.createProjectionLayer( projectionlayerInit );
				const layersArray = [ glProjLayer ];

				this._glProjLayer = glProjLayer;

				renderer.setPixelRatio( 1 );
				renderer._setXRLayerSize( glProjLayer.textureWidth, glProjLayer.textureHeight );

				const depth = this._useMultiview ? 2 : 1;
				const depthTexture = new DepthTexture( glProjLayer.textureWidth, glProjLayer.textureHeight, depthType, undefined, undefined, undefined, undefined, undefined, undefined, depthFormat, depth );

				this._xrRenderTarget = new XRRenderTarget(
					glProjLayer.textureWidth,
					glProjLayer.textureHeight,
					{
						format: RGBAFormat,
						type: UnsignedByteType,
						colorSpace: renderer.outputColorSpace,
						depthTexture: depthTexture,
						stencilBuffer: renderer.stencil,
						samples: attributes.antialias ? 4 : 0,
						resolveDepthBuffer: ( glProjLayer.ignoreDepthValues === false ),
						resolveStencilBuffer: ( glProjLayer.ignoreDepthValues === false ),
						depth: this._useMultiview ? 2 : 1,
						multiview: this._useMultiview
					} );

				this._xrRenderTarget._hasExternalTextures = true;
				this._xrRenderTarget.depth = this._useMultiview ? 2 : 1;

				this._supportsLayers = session.enabledFeatures.includes( 'layers' );

				this._referenceSpace = await session.requestReferenceSpace( this.getReferenceSpaceType() );

				if ( this._supportsLayers ) {

					// switch layers to native
					for ( const layer of this._layers ) {

						// change material so it "punches" out a hole to show the XR Layer.
						layer.plane.material = new MeshBasicMaterial( { color: 0xffffff, side: layer.type === 'cylinder' ? BackSide : FrontSide } );
						layer.plane.material.blending = CustomBlending;
						layer.plane.material.blendEquation = AddEquation;
						layer.plane.material.blendSrc = ZeroFactor;
						layer.plane.material.blendDst = ZeroFactor;

						layer.xrlayer = this._createXRLayer( layer );

						layersArray.unshift( layer.xrlayer );

					}

				}

				session.updateRenderState( { layers: layersArray } );

			} else {

				// fallback to XRWebGLLayer

				const layerInit = {
					antialias: renderer.samples > 0,
					alpha: true,
					depth: renderer.depth,
					stencil: renderer.stencil,
					framebufferScaleFactor: this.getFramebufferScaleFactor()
				};

				const glBaseLayer = new XRWebGLLayer( session, gl, layerInit );
				this._glBaseLayer = glBaseLayer;

				session.updateRenderState( { baseLayer: glBaseLayer } );

				renderer.setPixelRatio( 1 );
				renderer._setXRLayerSize( glBaseLayer.framebufferWidth, glBaseLayer.framebufferHeight );

				this._xrRenderTarget = new XRRenderTarget(
					glBaseLayer.framebufferWidth,
					glBaseLayer.framebufferHeight,
					{
						format: RGBAFormat,
						type: UnsignedByteType,
						colorSpace: renderer.outputColorSpace,
						stencilBuffer: renderer.stencil,
						resolveDepthBuffer: ( glBaseLayer.ignoreDepthValues === false ),
						resolveStencilBuffer: ( glBaseLayer.ignoreDepthValues === false ),
					}
				);

				this._xrRenderTarget._isOpaqueFramebuffer = true;
				this._referenceSpace = await session.requestReferenceSpace( this.getReferenceSpaceType() );

			}

			//

			this.setFoveation( this.getFoveation() );

			renderer._animation.setAnimationLoop( this._onAnimationFrame );
			renderer._animation.setContext( session );
			renderer._animation.start();

			this.isPresenting = true;

			this.dispatchEvent( { type: 'sessionstart' } );

		}

	}

	/**
	 * This method is called by the renderer per frame and updates the XR camera
	 * and it sub cameras based on the given camera. The given camera is the "user"
	 * camera created on application level and used for non-XR rendering.
	 *
	 * @param {PerspectiveCamera} camera - The camera.
	 */
	updateCamera( camera ) {

		const session = this._session;

		if ( session === null ) return;

		const depthNear = camera.near;
		const depthFar = camera.far;

		const cameraXR = this._cameraXR;
		const cameraL = this._cameraL;
		const cameraR = this._cameraR;

		cameraXR.near = cameraR.near = cameraL.near = depthNear;
		cameraXR.far = cameraR.far = cameraL.far = depthFar;
		cameraXR.isMultiViewCamera = this._useMultiview;

		if ( this._currentDepthNear !== cameraXR.near || this._currentDepthFar !== cameraXR.far ) {

			// Note that the new renderState won't apply until the next frame. See #18320

			session.updateRenderState( {
				depthNear: cameraXR.near,
				depthFar: cameraXR.far
			} );

			this._currentDepthNear = cameraXR.near;
			this._currentDepthFar = cameraXR.far;

		}

		// inherit camera layers and enable eye layers (1 = left, 2 = right)
		cameraXR.layers.mask = camera.layers.mask | 0b110;
		cameraL.layers.mask = cameraXR.layers.mask & 0b011;
		cameraR.layers.mask = cameraXR.layers.mask & 0b101;


		const parent = camera.parent;
		const cameras = cameraXR.cameras;

		updateCamera( cameraXR, parent );

		for ( let i = 0; i < cameras.length; i ++ ) {

			updateCamera( cameras[ i ], parent );

		}

		// update projection matrix for proper view frustum culling

		if ( cameras.length === 2 ) {

			setProjectionFromUnion( cameraXR, cameraL, cameraR );

		} else {

			// assume single camera setup (AR)

			cameraXR.projectionMatrix.copy( cameraL.projectionMatrix );

		}

		// update user camera and its children

		updateUserCamera( camera, cameraXR, parent );


	}

	/**
	 * Returns a WebXR controller for the given controller index.
	 *
	 * @private
	 * @param {number} index - The controller index.
	 * @return {WebXRController} The XR controller.
	 */
	_getController( index ) {

		let controller = this._controllers[ index ];

		if ( controller === undefined ) {

			controller = new WebXRController();
			this._controllers[ index ] = controller;

		}

		return controller;

	}

}
```
</details>

#### Methods

##### `getController(index: number): Group`

<details><summary>Code</summary>

```ts
getController( index ) {

		const controller = this._getController( index );

		return controller.getTargetRaySpace();

	}
```
</details>

##### `getControllerGrip(index: number): Group`

<details><summary>Code</summary>

```ts
getControllerGrip( index ) {

		const controller = this._getController( index );

		return controller.getGripSpace();

	}
```
</details>

##### `getHand(index: number): Group`

<details><summary>Code</summary>

```ts
getHand( index ) {

		const controller = this._getController( index );

		return controller.getHandSpace();

	}
```
</details>

##### `getFoveation(): number`

<details><summary>Code</summary>

```ts
getFoveation() {

		if ( this._glProjLayer === null && this._glBaseLayer === null ) {

			return undefined;

		}

		return this._foveation;

	}
```
</details>

##### `setFoveation(foveation: number): void`

<details><summary>Code</summary>

```ts
setFoveation( foveation ) {

		this._foveation = foveation;

		if ( this._glProjLayer !== null ) {

			this._glProjLayer.fixedFoveation = foveation;

		}

		if ( this._glBaseLayer !== null && this._glBaseLayer.fixedFoveation !== undefined ) {

			this._glBaseLayer.fixedFoveation = foveation;

		}

	}
```
</details>

##### `getFramebufferScaleFactor(): number`

<details><summary>Code</summary>

```ts
getFramebufferScaleFactor() {

		return this._framebufferScaleFactor;

	}
```
</details>

##### `setFramebufferScaleFactor(factor: number): void`

<details><summary>Code</summary>

```ts
setFramebufferScaleFactor( factor ) {

		this._framebufferScaleFactor = factor;

		if ( this.isPresenting === true ) {

			console.warn( 'THREE.XRManager: Cannot change framebuffer scale while presenting.' );

		}

	}
```
</details>

##### `getReferenceSpaceType(): XRReferenceSpaceType`

<details><summary>Code</summary>

```ts
getReferenceSpaceType() {

		return this._referenceSpaceType;

	}
```
</details>

##### `setReferenceSpaceType(type: XRReferenceSpaceType): void`

<details><summary>Code</summary>

```ts
setReferenceSpaceType( type ) {

		this._referenceSpaceType = type;

		if ( this.isPresenting === true ) {

			console.warn( 'THREE.XRManager: Cannot change reference space type while presenting.' );

		}

	}
```
</details>

##### `getReferenceSpace(): XRReferenceSpace`

<details><summary>Code</summary>

```ts
getReferenceSpace() {

		return this._customReferenceSpace || this._referenceSpace;

	}
```
</details>

##### `setReferenceSpace(space: XRReferenceSpace): void`

<details><summary>Code</summary>

```ts
setReferenceSpace( space ) {

		this._customReferenceSpace = space;

	}
```
</details>

##### `getCamera(): ArrayCamera`

<details><summary>Code</summary>

```ts
getCamera() {

		return this._cameraXR;

	}
```
</details>

##### `getEnvironmentBlendMode(): "opaque" | "additive" | "alpha-blend"`

<details><summary>Code</summary>

```ts
getEnvironmentBlendMode() {

		if ( this._session !== null ) {

			return this._session.environmentBlendMode;

		}

	}
```
</details>

##### `getFrame(): XRFrame`

<details><summary>Code</summary>

```ts
getFrame() {

		return this._xrFrame;

	}
```
</details>

##### `useMultiview(): boolean`

<details><summary>Code</summary>

```ts
useMultiview() {

		return this._useMultiview;

	}
```
</details>

##### `createQuadLayer(width: number, height: number, translation: Vector3, quaternion: Quaternion, pixelwidth: number, pixelheight: number, rendercall: Function, attributes: any): Mesh`

<details><summary>Code</summary>

```ts
createQuadLayer( width, height, translation, quaternion, pixelwidth, pixelheight, rendercall, attributes = {} ) {

		const geometry = new PlaneGeometry( width, height );
		const renderTarget = new XRRenderTarget(
			pixelwidth,
			pixelheight,
			{
				format: RGBAFormat,
				type: UnsignedByteType,
				depthTexture: new DepthTexture(
					pixelwidth,
					pixelheight,
					attributes.stencil ? UnsignedInt248Type : UnsignedIntType,
					undefined,
					undefined,
					undefined,
					undefined,
					undefined,
					undefined,
					attributes.stencil ? DepthStencilFormat : DepthFormat
				),
				stencilBuffer: attributes.stencil,
				resolveDepthBuffer: false,
				resolveStencilBuffer: false
			} );

		renderTarget._autoAllocateDepthBuffer = true;

		const material = new MeshBasicMaterial( { color: 0xffffff, side: FrontSide } );
		material.map = renderTarget.texture;
		material.map.offset.y = 1;
		material.map.repeat.y = - 1;
		const plane = new Mesh( geometry, material );
		plane.position.copy( translation );
		plane.quaternion.copy( quaternion );

		const layer = {
			type: 'quad',
			width: width,
			height: height,
			translation: translation,
			quaternion: quaternion,
			pixelwidth: pixelwidth,
			pixelheight: pixelheight,
			plane: plane,
			material: material,
			rendercall: rendercall,
			renderTarget: renderTarget };

		this._layers.push( layer );

		if ( this._session !== null ) {

			layer.plane.material = new MeshBasicMaterial( { color: 0xffffff, side: FrontSide } );
			layer.plane.material.blending = CustomBlending;
			layer.plane.material.blendEquation = AddEquation;
			layer.plane.material.blendSrc = ZeroFactor;
			layer.plane.material.blendDst = ZeroFactor;

			layer.xrlayer = this._createXRLayer( layer );

			const xrlayers = this._session.renderState.layers;
			xrlayers.unshift( layer.xrlayer );
			this._session.updateRenderState( { layers: xrlayers } );

		} else {

			renderTarget.isXRRenderTarget = false;

		}

		return plane;

	}
```
</details>

##### `createCylinderLayer(radius: number, centralAngle: number, aspectratio: number, translation: Vector3, quaternion: Quaternion, pixelwidth: number, pixelheight: number, rendercall: Function, attributes: any): Mesh`

<details><summary>Code</summary>

```ts
createCylinderLayer( radius, centralAngle, aspectratio, translation, quaternion, pixelwidth, pixelheight, rendercall, attributes = {} ) {

		const geometry = new CylinderGeometry( radius, radius, radius * centralAngle / aspectratio, 64, 64, true, Math.PI - centralAngle / 2, centralAngle );
		const renderTarget = new XRRenderTarget(
			pixelwidth,
			pixelheight,
			{
				format: RGBAFormat,
				type: UnsignedByteType,
				depthTexture: new DepthTexture(
					pixelwidth,
					pixelheight,
					attributes.stencil ? UnsignedInt248Type : UnsignedIntType,
					undefined,
					undefined,
					undefined,
					undefined,
					undefined,
					undefined,
					attributes.stencil ? DepthStencilFormat : DepthFormat
				),
				stencilBuffer: attributes.stencil,
				resolveDepthBuffer: false,
				resolveStencilBuffer: false
			} );

		renderTarget._autoAllocateDepthBuffer = true;

		const material = new MeshBasicMaterial( { color: 0xffffff, side: BackSide } );
		material.map = renderTarget.texture;
		material.map.offset.y = 1;
		material.map.repeat.y = - 1;
		const plane = new Mesh( geometry, material );
		plane.position.copy( translation );
		plane.quaternion.copy( quaternion );

		const layer = {
			type: 'cylinder',
			radius: radius,
			centralAngle: centralAngle,
			aspectratio: aspectratio,
			translation: translation,
			quaternion: quaternion,
			pixelwidth: pixelwidth,
			pixelheight: pixelheight,
			plane: plane,
			material: material,
			rendercall: rendercall,
			renderTarget: renderTarget };

		this._layers.push( layer );

		if ( this._session !== null ) {

			layer.plane.material = new MeshBasicMaterial( { color: 0xffffff, side: BackSide } );
			layer.plane.material.blending = CustomBlending;
			layer.plane.material.blendEquation = AddEquation;
			layer.plane.material.blendSrc = ZeroFactor;
			layer.plane.material.blendDst = ZeroFactor;

			layer.xrlayer = this._createXRLayer( layer );

			const xrlayers = this._session.renderState.layers;
			xrlayers.unshift( layer.xrlayer );
			this._session.updateRenderState( { layers: xrlayers } );

		} else {

			renderTarget.isXRRenderTarget = false;

		}

		return plane;

	}
```
</details>

##### `renderLayers(): void`

<details><summary>Code</summary>

```ts
renderLayers( ) {

		const translationObject = new Vector3();
		const quaternionObject = new Quaternion();
		const renderer = this._renderer;

		const wasPresenting = this.isPresenting;
		const rendererOutputTarget = renderer.getOutputRenderTarget();
		const rendererFramebufferTarget = renderer._frameBufferTarget;
		this.isPresenting = false;

		const rendererSize = new Vector2();
		renderer.getSize( rendererSize );
		const rendererQuad = renderer._quad;

		for ( const layer of this._layers ) {

			layer.renderTarget.isXRRenderTarget = this._session !== null;
			layer.renderTarget._hasExternalTextures = layer.renderTarget.isXRRenderTarget;

			if ( layer.renderTarget.isXRRenderTarget && this._supportsLayers ) {

				layer.xrlayer.transform = new XRRigidTransform( layer.plane.getWorldPosition( translationObject ), layer.plane.getWorldQuaternion( quaternionObject ) );

				const glSubImage = this._glBinding.getSubImage( layer.xrlayer, this._xrFrame );
				renderer.backend.setXRRenderTargetTextures(
					layer.renderTarget,
					glSubImage.colorTexture,
					undefined );

				renderer._setXRLayerSize( layer.renderTarget.width, layer.renderTarget.height );
				renderer.setOutputRenderTarget( layer.renderTarget );
				renderer.setRenderTarget( null );
				renderer._frameBufferTarget = null;

				this._frameBufferTargets || ( this._frameBufferTargets = new WeakMap() );
				const { frameBufferTarget, quad } = this._frameBufferTargets.get( layer.renderTarget ) || { frameBufferTarget: null, quad: null };
				if ( ! frameBufferTarget ) {

					renderer._quad = new QuadMesh( new NodeMaterial() );
					this._frameBufferTargets.set( layer.renderTarget, { frameBufferTarget: renderer._getFrameBufferTarget(), quad: renderer._quad } );

				} else {

					renderer._frameBufferTarget = frameBufferTarget;
					renderer._quad = quad;

				}

				layer.rendercall();

				renderer._frameBufferTarget = null;

			} else {

				renderer.setRenderTarget( layer.renderTarget );
				layer.rendercall();

			}

		}

		renderer.setRenderTarget( null );
		renderer.setOutputRenderTarget( rendererOutputTarget );
		renderer._frameBufferTarget = rendererFramebufferTarget;
		renderer._setXRLayerSize( rendererSize.x, rendererSize.y );
		renderer._quad = rendererQuad;
		this.isPresenting = wasPresenting;

	}
```
</details>

##### `getSession(): XRSession`

<details><summary>Code</summary>

```ts
getSession() {

		return this._session;

	}
```
</details>

##### `setSession(session: XRSession): Promise<any>`

<details><summary>Code</summary>

```ts
async setSession( session ) {

		const renderer = this._renderer;
		const backend = renderer.backend;

		this._gl = renderer.getContext();
		const gl = this._gl;
		const attributes = gl.getContextAttributes();

		this._session = session;

		if ( session !== null ) {

			if ( backend.isWebGPUBackend === true ) throw new Error( 'THREE.XRManager: XR is currently not supported with a WebGPU backend. Use WebGL by passing "{ forceWebGL: true }" to the constructor of the renderer.' );

			session.addEventListener( 'select', this._onSessionEvent );
			session.addEventListener( 'selectstart', this._onSessionEvent );
			session.addEventListener( 'selectend', this._onSessionEvent );
			session.addEventListener( 'squeeze', this._onSessionEvent );
			session.addEventListener( 'squeezestart', this._onSessionEvent );
			session.addEventListener( 'squeezeend', this._onSessionEvent );
			session.addEventListener( 'end', this._onSessionEnd );
			session.addEventListener( 'inputsourceschange', this._onInputSourcesChange );

			await backend.makeXRCompatible();

			this._currentPixelRatio = renderer.getPixelRatio();
			renderer.getSize( this._currentSize );

			this._currentAnimationContext = renderer._animation.getContext();
			this._currentAnimationLoop = renderer._animation.getAnimationLoop();
			renderer._animation.stop();

			//

			if ( this._supportsGlBinding ) {

				const glBinding = new XRWebGLBinding( session, gl );
				this._glBinding = glBinding;

			}

			//

			if ( this._useLayers === true ) {

				// default path using XRProjectionLayer

				let depthFormat = null;
				let depthType = null;
				let glDepthFormat = null;

				if ( renderer.depth ) {

					glDepthFormat = renderer.stencil ? gl.DEPTH24_STENCIL8 : gl.DEPTH_COMPONENT24;
					depthFormat = renderer.stencil ? DepthStencilFormat : DepthFormat;
					depthType = renderer.stencil ? UnsignedInt248Type : UnsignedIntType;

				}

				const projectionlayerInit = {
					colorFormat: gl.RGBA8,
					depthFormat: glDepthFormat,
					scaleFactor: this._framebufferScaleFactor,
					clearOnAccess: false
				};

				if ( this._useMultiviewIfPossible && renderer.hasFeature( 'OVR_multiview2' ) ) {

					projectionlayerInit.textureType = 'texture-array';
					this._useMultiview = true;

				}

				const glProjLayer = this._glBinding.createProjectionLayer( projectionlayerInit );
				const layersArray = [ glProjLayer ];

				this._glProjLayer = glProjLayer;

				renderer.setPixelRatio( 1 );
				renderer._setXRLayerSize( glProjLayer.textureWidth, glProjLayer.textureHeight );

				const depth = this._useMultiview ? 2 : 1;
				const depthTexture = new DepthTexture( glProjLayer.textureWidth, glProjLayer.textureHeight, depthType, undefined, undefined, undefined, undefined, undefined, undefined, depthFormat, depth );

				this._xrRenderTarget = new XRRenderTarget(
					glProjLayer.textureWidth,
					glProjLayer.textureHeight,
					{
						format: RGBAFormat,
						type: UnsignedByteType,
						colorSpace: renderer.outputColorSpace,
						depthTexture: depthTexture,
						stencilBuffer: renderer.stencil,
						samples: attributes.antialias ? 4 : 0,
						resolveDepthBuffer: ( glProjLayer.ignoreDepthValues === false ),
						resolveStencilBuffer: ( glProjLayer.ignoreDepthValues === false ),
						depth: this._useMultiview ? 2 : 1,
						multiview: this._useMultiview
					} );

				this._xrRenderTarget._hasExternalTextures = true;
				this._xrRenderTarget.depth = this._useMultiview ? 2 : 1;

				this._supportsLayers = session.enabledFeatures.includes( 'layers' );

				this._referenceSpace = await session.requestReferenceSpace( this.getReferenceSpaceType() );

				if ( this._supportsLayers ) {

					// switch layers to native
					for ( const layer of this._layers ) {

						// change material so it "punches" out a hole to show the XR Layer.
						layer.plane.material = new MeshBasicMaterial( { color: 0xffffff, side: layer.type === 'cylinder' ? BackSide : FrontSide } );
						layer.plane.material.blending = CustomBlending;
						layer.plane.material.blendEquation = AddEquation;
						layer.plane.material.blendSrc = ZeroFactor;
						layer.plane.material.blendDst = ZeroFactor;

						layer.xrlayer = this._createXRLayer( layer );

						layersArray.unshift( layer.xrlayer );

					}

				}

				session.updateRenderState( { layers: layersArray } );

			} else {

				// fallback to XRWebGLLayer

				const layerInit = {
					antialias: renderer.samples > 0,
					alpha: true,
					depth: renderer.depth,
					stencil: renderer.stencil,
					framebufferScaleFactor: this.getFramebufferScaleFactor()
				};

				const glBaseLayer = new XRWebGLLayer( session, gl, layerInit );
				this._glBaseLayer = glBaseLayer;

				session.updateRenderState( { baseLayer: glBaseLayer } );

				renderer.setPixelRatio( 1 );
				renderer._setXRLayerSize( glBaseLayer.framebufferWidth, glBaseLayer.framebufferHeight );

				this._xrRenderTarget = new XRRenderTarget(
					glBaseLayer.framebufferWidth,
					glBaseLayer.framebufferHeight,
					{
						format: RGBAFormat,
						type: UnsignedByteType,
						colorSpace: renderer.outputColorSpace,
						stencilBuffer: renderer.stencil,
						resolveDepthBuffer: ( glBaseLayer.ignoreDepthValues === false ),
						resolveStencilBuffer: ( glBaseLayer.ignoreDepthValues === false ),
					}
				);

				this._xrRenderTarget._isOpaqueFramebuffer = true;
				this._referenceSpace = await session.requestReferenceSpace( this.getReferenceSpaceType() );

			}

			//

			this.setFoveation( this.getFoveation() );

			renderer._animation.setAnimationLoop( this._onAnimationFrame );
			renderer._animation.setContext( session );
			renderer._animation.start();

			this.isPresenting = true;

			this.dispatchEvent( { type: 'sessionstart' } );

		}

	}
```
</details>

##### `updateCamera(camera: PerspectiveCamera): void`

<details><summary>Code</summary>

```ts
updateCamera( camera ) {

		const session = this._session;

		if ( session === null ) return;

		const depthNear = camera.near;
		const depthFar = camera.far;

		const cameraXR = this._cameraXR;
		const cameraL = this._cameraL;
		const cameraR = this._cameraR;

		cameraXR.near = cameraR.near = cameraL.near = depthNear;
		cameraXR.far = cameraR.far = cameraL.far = depthFar;
		cameraXR.isMultiViewCamera = this._useMultiview;

		if ( this._currentDepthNear !== cameraXR.near || this._currentDepthFar !== cameraXR.far ) {

			// Note that the new renderState won't apply until the next frame. See #18320

			session.updateRenderState( {
				depthNear: cameraXR.near,
				depthFar: cameraXR.far
			} );

			this._currentDepthNear = cameraXR.near;
			this._currentDepthFar = cameraXR.far;

		}

		// inherit camera layers and enable eye layers (1 = left, 2 = right)
		cameraXR.layers.mask = camera.layers.mask | 0b110;
		cameraL.layers.mask = cameraXR.layers.mask & 0b011;
		cameraR.layers.mask = cameraXR.layers.mask & 0b101;


		const parent = camera.parent;
		const cameras = cameraXR.cameras;

		updateCamera( cameraXR, parent );

		for ( let i = 0; i < cameras.length; i ++ ) {

			updateCamera( cameras[ i ], parent );

		}

		// update projection matrix for proper view frustum culling

		if ( cameras.length === 2 ) {

			setProjectionFromUnion( cameraXR, cameraL, cameraR );

		} else {

			// assume single camera setup (AR)

			cameraXR.projectionMatrix.copy( cameraL.projectionMatrix );

		}

		// update user camera and its children

		updateUserCamera( camera, cameraXR, parent );


	}
```
</details>

##### `_getController(index: number): WebXRController`

<details><summary>Code</summary>

```ts
_getController( index ) {

		let controller = this._controllers[ index ];

		if ( controller === undefined ) {

			controller = new WebXRController();
			this._controllers[ index ] = controller;

		}

		return controller;

	}
```
</details>


---