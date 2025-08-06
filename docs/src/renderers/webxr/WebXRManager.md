[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebXRManager.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 19 |
| 📊 Variables & Constants | 78 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webxr/WebXRManager.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ArrayCamera` | `../../cameras/ArrayCamera.js` |
| `EventDispatcher` | `../../core/EventDispatcher.js` |
| `PerspectiveCamera` | `../../cameras/PerspectiveCamera.js` |
| `Vector2` | `../../math/Vector2.js` |
| `Vector3` | `../../math/Vector3.js` |
| `Vector4` | `../../math/Vector4.js` |
| `RAD2DEG` | `../../math/MathUtils.js` |
| `WebGLAnimation` | `../webgl/WebGLAnimation.js` |
| `WebGLRenderTarget` | `../WebGLRenderTarget.js` |
| `WebXRController` | `./WebXRController.js` |
| `DepthTexture` | `../../textures/DepthTexture.js` |
| `ExternalTexture` | `../../textures/ExternalTexture.js` |
| `DepthFormat` | `../../constants.js` |
| `DepthStencilFormat` | `../../constants.js` |
| `RGBAFormat` | `../../constants.js` |
| `UnsignedByteType` | `../../constants.js` |
| `UnsignedIntType` | `../../constants.js` |
| `UnsignedInt248Type` | `../../constants.js` |
| `WebXRDepthSensing` | `./WebXRDepthSensing.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `session` | `any` | let/var | `null` | ✗ |
| `framebufferScaleFactor` | `number` | let/var | `1.0` | ✗ |
| `referenceSpace` | `any` | let/var | `null` | ✗ |
| `referenceSpaceType` | `string` | let/var | `'local-floor'` | ✗ |
| `foveation` | `number` | let/var | `1.0` | ✗ |
| `customReferenceSpace` | `any` | let/var | `null` | ✗ |
| `pose` | `any` | let/var | `null` | ✗ |
| `glBinding` | `any` | let/var | `null` | ✗ |
| `glProjLayer` | `any` | let/var | `null` | ✗ |
| `glBaseLayer` | `any` | let/var | `null` | ✗ |
| `xrFrame` | `any` | let/var | `null` | ✗ |
| `depthSensing` | `WebXRDepthSensing` | let/var | `new WebXRDepthSensing()` | ✗ |
| `cameraAccessTextures` | `{}` | let/var | `{}` | ✗ |
| `initialRenderTarget` | `any` | let/var | `null` | ✗ |
| `newRenderTarget` | `any` | let/var | `null` | ✗ |
| `controllers` | `any[]` | let/var | `[]` | ✗ |
| `controllerInputSources` | `any[]` | let/var | `[]` | ✗ |
| `currentSize` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `currentPixelRatio` | `any` | let/var | `null` | ✗ |
| `cameraL` | `PerspectiveCamera` | let/var | `new PerspectiveCamera()` | ✗ |
| `cameraR` | `PerspectiveCamera` | let/var | `new PerspectiveCamera()` | ✗ |
| `cameras` | `PerspectiveCamera[]` | let/var | `[ cameraL, cameraR ]` | ✗ |
| `cameraXR` | `ArrayCamera` | let/var | `new ArrayCamera()` | ✗ |
| `_currentDepthNear` | `any` | let/var | `null` | ✗ |
| `_currentDepthFar` | `any` | let/var | `null` | ✗ |
| `controller` | `any` | let/var | `controllers[ index ]` | ✗ |
| `controller` | `any` | let/var | `controllers[ index ]` | ✗ |
| `controller` | `any` | let/var | `controllers[ index ]` | ✗ |
| `controller` | `any` | let/var | `controllers[ controllerIndex ]` | ✗ |
| `inputSource` | `any` | let/var | `controllerInputSources[ i ]` | ✗ |
| `useLayers` | `boolean` | let/var | `glBinding !== null && 'createProjectionLayer' in XRWebGLBinding.prototype` | ✗ |
| `layerInit` | `{ antialias: boolean; alpha: boolean;...` | let/var | `{ antialias: attributes.antialias, alpha: true, depth: attributes.depth, sten...` | ✗ |
| `depthFormat` | `any` | let/var | `null` | ✗ |
| `depthType` | `any` | let/var | `null` | ✗ |
| `glDepthFormat` | `any` | let/var | `null` | ✗ |
| `projectionlayerInit` | `{ colorFormat: 32856; depthFormat: 35...` | let/var | `{ colorFormat: gl.RGBA8, depthFormat: glDepthFormat, scaleFactor: framebuffer...` | ✗ |
| `inputSource` | `any` | let/var | `event.removed[ i ]` | ✗ |
| `inputSource` | `any` | let/var | `event.added[ i ]` | ✗ |
| `controller` | `any` | let/var | `controllers[ controllerIndex ]` | ✗ |
| `cameraLPos` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `cameraRPos` | `Vector3` | let/var | `new Vector3()` | ✗ |
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
| `depthNear` | `any` | let/var | `camera.near` | ✗ |
| `depthFar` | `any` | let/var | `camera.far` | ✗ |
| `parent` | `any` | let/var | `camera.parent` | ✗ |
| `cameras` | `PerspectiveCamera[]` | let/var | `cameraXR.cameras` | ✗ |
| `onAnimationFrameCallback` | `any` | let/var | `null` | ✗ |
| `views` | `any` | let/var | `pose.views` | ✗ |
| `cameraXRNeedsUpdate` | `boolean` | let/var | `false` | ✗ |
| `view` | `any` | let/var | `views[ i ]` | ✗ |
| `viewport` | `any` | let/var | `null` | ✗ |
| `camera` | `PerspectiveCamera` | let/var | `cameras[ i ]` | ✗ |
| `enabledFeatures` | `any` | let/var | `session.enabledFeatures` | ✗ |
| `gpuDepthSensingEnabled` | `boolean` | let/var | `enabledFeatures && enabledFeatures.includes( 'depth-sensing' ) && session.dep...` | ✗ |
| `cameraAccessEnabled` | `any` | let/var | `enabledFeatures && enabledFeatures.includes( 'camera-access' )` | ✗ |
| `camera` | `any` | let/var | `views[ i ].camera` | ✗ |
| `cameraTex` | `any` | let/var | `cameraAccessTextures[ camera ]` | ✗ |
| `inputSource` | `any` | let/var | `controllerInputSources[ i ]` | ✗ |
| `controller` | `any` | let/var | `controllers[ i ]` | ✗ |
| `animation` | `any` | let/var | `new WebGLAnimation()` | ✗ |


---

## Functions

### `onSessionEvent(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `controllerInputSources.indexOf`
- `controller.update`
- `controller.dispatchEvent`

<details><summary>Code</summary>

```typescript
function onSessionEvent( event ) {

			const controllerIndex = controllerInputSources.indexOf( event.inputSource );

			if ( controllerIndex === - 1 ) {

				return;

			}

			const controller = controllers[ controllerIndex ];

			if ( controller !== undefined ) {

				controller.update( event.inputSource, event.frame, customReferenceSpace || referenceSpace );
				controller.dispatchEvent( { type: event.type, data: event.inputSource } );

			}

		}
```
</details>

### `onSessionEnd(): void`

**Returns:** `void`

**Calls:**

- `session.removeEventListener`
- `controllers[ i ].disconnect`
- `depthSensing.reset`
- `renderer.setRenderTarget`
- `animation.stop`
- `renderer.setPixelRatio`
- `renderer.setSize`
- `scope.dispatchEvent`

**Internal Comments:**
```
// restore framebuffer/rendering state (x4)
// (x4)
```

<details><summary>Code</summary>

```typescript
function onSessionEnd() {

			session.removeEventListener( 'select', onSessionEvent );
			session.removeEventListener( 'selectstart', onSessionEvent );
			session.removeEventListener( 'selectend', onSessionEvent );
			session.removeEventListener( 'squeeze', onSessionEvent );
			session.removeEventListener( 'squeezestart', onSessionEvent );
			session.removeEventListener( 'squeezeend', onSessionEvent );
			session.removeEventListener( 'end', onSessionEnd );
			session.removeEventListener( 'inputsourceschange', onInputSourcesChange );

			for ( let i = 0; i < controllers.length; i ++ ) {

				const inputSource = controllerInputSources[ i ];

				if ( inputSource === null ) continue;

				controllerInputSources[ i ] = null;

				controllers[ i ].disconnect( inputSource );

			}

			_currentDepthNear = null;
			_currentDepthFar = null;

			depthSensing.reset();
			for ( const key in cameraAccessTextures ) {

				delete cameraAccessTextures[ key ];

			}

			// restore framebuffer/rendering state

			renderer.setRenderTarget( initialRenderTarget );

			glBaseLayer = null;
			glProjLayer = null;
			glBinding = null;
			session = null;
			newRenderTarget = null;

			//

			animation.stop();

			scope.isPresenting = false;

			renderer.setPixelRatio( currentPixelRatio );
			renderer.setSize( currentSize.width, currentSize.height, false );

			scope.dispatchEvent( { type: 'sessionend' } );

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

- `cameraLPos.setFromMatrixPosition`
- `cameraRPos.setFromMatrixPosition`
- `cameraLPos.distanceTo`
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

			cameraLPos.setFromMatrixPosition( cameraL.matrixWorld );
			cameraRPos.setFromMatrixPosition( cameraR.matrixWorld );

			const ipd = cameraLPos.distanceTo( cameraRPos );

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

### `updateCamera(camera: any, parent: any): void`

**Parameters:**

- **`camera`** `any`
- **`parent`** `any`

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

### `updateUserCamera(camera: any, cameraXR: any, parent: any): void`

**Parameters:**

- **`camera`** `any`
- **`cameraXR`** `any`
- **`parent`** `any`

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

### `onAnimationFrame(time: any, frame: any): void`

**Parameters:**

- **`time`** `any`
- **`frame`** `any`

**Returns:** `void`

**Calls:**

- `frame.getViewerPose`
- `renderer.setRenderTargetFramebuffer`
- `renderer.setRenderTarget`
- `glBaseLayer.getViewport`
- `glBinding.getViewSubImage`
- `renderer.setRenderTargetTextures`
- `camera.layers.enable`
- `camera.matrix.fromArray`
- `camera.matrix.decompose`
- `camera.projectionMatrix.fromArray`
- `camera.projectionMatrixInverse.copy( camera.projectionMatrix ).invert`
- `camera.viewport.set`
- `cameraXR.matrix.copy`
- `cameraXR.matrix.decompose`
- `cameraXR.cameras.push`
- `enabledFeatures.includes`
- `glBinding.getDepthInformation`
- `depthSensing.init`
- `renderer.state.unbindTexture`
- `glBinding.getCameraImage`
- `controller.update`
- `onAnimationFrameCallback`
- `scope.dispatchEvent`

**Internal Comments:**
```
// check if it's necessary to rebuild cameraXR's camera list
// For side-by-side projection, we only produce a single texture for both eyes.
// (x3)
```

<details><summary>Code</summary>

```typescript
function onAnimationFrame( time, frame ) {

			pose = frame.getViewerPose( customReferenceSpace || referenceSpace );
			xrFrame = frame;

			if ( pose !== null ) {

				const views = pose.views;

				if ( glBaseLayer !== null ) {

					renderer.setRenderTargetFramebuffer( newRenderTarget, glBaseLayer.framebuffer );
					renderer.setRenderTarget( newRenderTarget );

				}

				let cameraXRNeedsUpdate = false;

				// check if it's necessary to rebuild cameraXR's camera list

				if ( views.length !== cameraXR.cameras.length ) {

					cameraXR.cameras.length = 0;
					cameraXRNeedsUpdate = true;

				}

				for ( let i = 0; i < views.length; i ++ ) {

					const view = views[ i ];

					let viewport = null;

					if ( glBaseLayer !== null ) {

						viewport = glBaseLayer.getViewport( view );

					} else {

						const glSubImage = glBinding.getViewSubImage( glProjLayer, view );
						viewport = glSubImage.viewport;

						// For side-by-side projection, we only produce a single texture for both eyes.
						if ( i === 0 ) {

							renderer.setRenderTargetTextures(
								newRenderTarget,
								glSubImage.colorTexture,
								glSubImage.depthStencilTexture );

							renderer.setRenderTarget( newRenderTarget );

						}

					}

					let camera = cameras[ i ];

					if ( camera === undefined ) {

						camera = new PerspectiveCamera();
						camera.layers.enable( i );
						camera.viewport = new Vector4();
						cameras[ i ] = camera;

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

				//

				const enabledFeatures = session.enabledFeatures;
				const gpuDepthSensingEnabled = enabledFeatures &&
					enabledFeatures.includes( 'depth-sensing' ) &&
					session.depthUsage == 'gpu-optimized';

				if ( gpuDepthSensingEnabled && glBinding ) {

					const depthData = glBinding.getDepthInformation( views[ 0 ] );

					if ( depthData && depthData.isValid && depthData.texture ) {

						depthSensing.init( depthData, session.renderState );

					}

				}

				const cameraAccessEnabled = enabledFeatures &&
				    enabledFeatures.includes( 'camera-access' );

				if ( cameraAccessEnabled ) {

					renderer.state.unbindTexture();

					if ( glBinding ) {

						for ( let i = 0; i < views.length; i ++ ) {

							const camera = views[ i ].camera;

							if ( camera ) {

								let cameraTex = cameraAccessTextures[ camera ];

								if ( ! cameraTex ) {

									cameraTex = new ExternalTexture();
									cameraAccessTextures[ camera ] = cameraTex;

								}

								const glTexture = glBinding.getCameraImage( camera );
								cameraTex.sourceTexture = glTexture;

							}

						}

					}

				}

			}

			//

			for ( let i = 0; i < controllers.length; i ++ ) {

				const inputSource = controllerInputSources[ i ];
				const controller = controllers[ i ];

				if ( inputSource !== null && controller !== undefined ) {

					controller.update( inputSource, frame, customReferenceSpace || referenceSpace );

				}

			}

			if ( onAnimationFrameCallback ) onAnimationFrameCallback( time, frame );

			if ( frame.detectedPlanes ) {

				scope.dispatchEvent( { type: 'planesdetected', data: frame } );

			}

			xrFrame = null;

		}
```
</details>


---

## Classes

### `WebXRManager`

<details><summary>Class Code</summary>

```ts
class WebXRManager extends EventDispatcher {

	/**
	 * Constructs a new WebGL renderer.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {WebGL2RenderingContext} gl - The rendering context.
	 */
	constructor( renderer, gl ) {

		super();

		const scope = this;

		let session = null;

		let framebufferScaleFactor = 1.0;

		let referenceSpace = null;
		let referenceSpaceType = 'local-floor';
		// Set default foveation to maximum.
		let foveation = 1.0;
		let customReferenceSpace = null;

		let pose = null;
		let glBinding = null;
		let glProjLayer = null;
		let glBaseLayer = null;
		let xrFrame = null;

		const depthSensing = new WebXRDepthSensing();
		const cameraAccessTextures = {};
		const attributes = gl.getContextAttributes();

		let initialRenderTarget = null;
		let newRenderTarget = null;

		const controllers = [];
		const controllerInputSources = [];

		const currentSize = new Vector2();
		let currentPixelRatio = null;

		//

		const cameraL = new PerspectiveCamera();
		cameraL.viewport = new Vector4();

		const cameraR = new PerspectiveCamera();
		cameraR.viewport = new Vector4();

		const cameras = [ cameraL, cameraR ];

		const cameraXR = new ArrayCamera();

		let _currentDepthNear = null;
		let _currentDepthFar = null;

		//

		/**
		 * Whether the manager's XR camera should be automatically updated or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.cameraAutoUpdate = true;

		/**
		 * This flag notifies the renderer to be ready for XR rendering. Set it to `true`
		 * if you are going to use XR in your app.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.enabled = false;

		/**
		 * Whether XR presentation is active or not.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default false
		 */
		this.isPresenting = false;

		/**
		 * Returns a group representing the `target ray` space of the XR controller.
		 * Use this space for visualizing 3D objects that support the user in pointing
		 * tasks like UI interaction.
		 *
		 * @param {number} index - The index of the controller.
		 * @return {Group} A group representing the `target ray` space.
		 */
		this.getController = function ( index ) {

			let controller = controllers[ index ];

			if ( controller === undefined ) {

				controller = new WebXRController();
				controllers[ index ] = controller;

			}

			return controller.getTargetRaySpace();

		};

		/**
		 * Returns a group representing the `grip` space of the XR controller.
		 * Use this space for visualizing 3D objects that support the user in pointing
		 * tasks like UI interaction.
		 *
		 * Note: If you want to show something in the user's hand AND offer a
		 * pointing ray at the same time, you'll want to attached the handheld object
		 * to the group returned by `getControllerGrip()` and the ray to the
		 * group returned by `getController()`. The idea is to have two
		 * different groups in two different coordinate spaces for the same WebXR
		 * controller.
		 *
		 * @param {number} index - The index of the controller.
		 * @return {Group} A group representing the `grip` space.
		 */
		this.getControllerGrip = function ( index ) {

			let controller = controllers[ index ];

			if ( controller === undefined ) {

				controller = new WebXRController();
				controllers[ index ] = controller;

			}

			return controller.getGripSpace();

		};

		/**
		 * Returns a group representing the `hand` space of the XR controller.
		 * Use this space for visualizing 3D objects that support the user in pointing
		 * tasks like UI interaction.
		 *
		 * @param {number} index - The index of the controller.
		 * @return {Group} A group representing the `hand` space.
		 */
		this.getHand = function ( index ) {

			let controller = controllers[ index ];

			if ( controller === undefined ) {

				controller = new WebXRController();
				controllers[ index ] = controller;

			}

			return controller.getHandSpace();

		};

		//

		function onSessionEvent( event ) {

			const controllerIndex = controllerInputSources.indexOf( event.inputSource );

			if ( controllerIndex === - 1 ) {

				return;

			}

			const controller = controllers[ controllerIndex ];

			if ( controller !== undefined ) {

				controller.update( event.inputSource, event.frame, customReferenceSpace || referenceSpace );
				controller.dispatchEvent( { type: event.type, data: event.inputSource } );

			}

		}

		function onSessionEnd() {

			session.removeEventListener( 'select', onSessionEvent );
			session.removeEventListener( 'selectstart', onSessionEvent );
			session.removeEventListener( 'selectend', onSessionEvent );
			session.removeEventListener( 'squeeze', onSessionEvent );
			session.removeEventListener( 'squeezestart', onSessionEvent );
			session.removeEventListener( 'squeezeend', onSessionEvent );
			session.removeEventListener( 'end', onSessionEnd );
			session.removeEventListener( 'inputsourceschange', onInputSourcesChange );

			for ( let i = 0; i < controllers.length; i ++ ) {

				const inputSource = controllerInputSources[ i ];

				if ( inputSource === null ) continue;

				controllerInputSources[ i ] = null;

				controllers[ i ].disconnect( inputSource );

			}

			_currentDepthNear = null;
			_currentDepthFar = null;

			depthSensing.reset();
			for ( const key in cameraAccessTextures ) {

				delete cameraAccessTextures[ key ];

			}

			// restore framebuffer/rendering state

			renderer.setRenderTarget( initialRenderTarget );

			glBaseLayer = null;
			glProjLayer = null;
			glBinding = null;
			session = null;
			newRenderTarget = null;

			//

			animation.stop();

			scope.isPresenting = false;

			renderer.setPixelRatio( currentPixelRatio );
			renderer.setSize( currentSize.width, currentSize.height, false );

			scope.dispatchEvent( { type: 'sessionend' } );

		}

		/**
		 * Sets the framebuffer scale factor.
		 *
		 * This method can not be used during a XR session.
		 *
		 * @param {number} value - The framebuffer scale factor.
		 */
		this.setFramebufferScaleFactor = function ( value ) {

			framebufferScaleFactor = value;

			if ( scope.isPresenting === true ) {

				console.warn( 'THREE.WebXRManager: Cannot change framebuffer scale while presenting.' );

			}

		};

		/**
		 * Sets the reference space type. Can be used to configure a spatial relationship with the user's physical
		 * environment. Depending on how the user moves in 3D space, setting an appropriate reference space can
		 * improve tracking. Default is `local-floor`. Valid values can be found here
		 * https://developer.mozilla.org/en-US/docs/Web/API/XRReferenceSpace#reference_space_types.
		 *
		 * This method can not be used during a XR session.
		 *
		 * @param {string} value - The reference space type.
		 */
		this.setReferenceSpaceType = function ( value ) {

			referenceSpaceType = value;

			if ( scope.isPresenting === true ) {

				console.warn( 'THREE.WebXRManager: Cannot change reference space type while presenting.' );

			}

		};

		/**
		 * Returns the XR reference space.
		 *
		 * @return {XRReferenceSpace} The XR reference space.
		 */
		this.getReferenceSpace = function () {

			return customReferenceSpace || referenceSpace;

		};

		/**
		 * Sets a custom XR reference space.
		 *
		 * @param {XRReferenceSpace} space - The XR reference space.
		 */
		this.setReferenceSpace = function ( space ) {

			customReferenceSpace = space;

		};

		/**
		 * Returns the current base layer.
		 *
		 * @return {?(XRWebGLLayer|XRProjectionLayer)} The XR base layer.
		 */
		this.getBaseLayer = function () {

			return glProjLayer !== null ? glProjLayer : glBaseLayer;

		};

		/**
		 * Returns the current XR binding.
		 *
		 * @return {?XRWebGLBinding} The XR binding.
		 */
		this.getBinding = function () {

			return glBinding;

		};

		/**
		 * Returns the current XR frame.
		 *
		 * @return {?XRFrame} The XR frame. Returns `null` when used outside a XR session.
		 */
		this.getFrame = function () {

			return xrFrame;

		};

		/**
		 * Returns the current XR session.
		 *
		 * @return {?XRSession} The XR session. Returns `null` when used outside a XR session.
		 */
		this.getSession = function () {

			return session;

		};

		/**
		 * After a XR session has been requested usually with one of the `*Button` modules, it
		 * is injected into the renderer with this method. This method triggers the start of
		 * the actual XR rendering.
		 *
		 * @async
		 * @param {XRSession} value - The XR session to set.
		 * @return {Promise} A Promise that resolves when the session has been set.
		 */
		this.setSession = async function ( value ) {

			session = value;

			if ( session !== null ) {

				initialRenderTarget = renderer.getRenderTarget();

				session.addEventListener( 'select', onSessionEvent );
				session.addEventListener( 'selectstart', onSessionEvent );
				session.addEventListener( 'selectend', onSessionEvent );
				session.addEventListener( 'squeeze', onSessionEvent );
				session.addEventListener( 'squeezestart', onSessionEvent );
				session.addEventListener( 'squeezeend', onSessionEvent );
				session.addEventListener( 'end', onSessionEnd );
				session.addEventListener( 'inputsourceschange', onInputSourcesChange );

				if ( attributes.xrCompatible !== true ) {

					await gl.makeXRCompatible();

				}

				currentPixelRatio = renderer.getPixelRatio();
				renderer.getSize( currentSize );

				if ( typeof XRWebGLBinding !== 'undefined' ) {

					glBinding = new XRWebGLBinding( session, gl );

				}

				// Check that the browser implements the necessary APIs to use an
				// XRProjectionLayer rather than an XRWebGLLayer
				const useLayers = glBinding !== null && 'createProjectionLayer' in XRWebGLBinding.prototype;

				if ( ! useLayers ) {

					const layerInit = {
						antialias: attributes.antialias,
						alpha: true,
						depth: attributes.depth,
						stencil: attributes.stencil,
						framebufferScaleFactor: framebufferScaleFactor
					};

					glBaseLayer = new XRWebGLLayer( session, gl, layerInit );

					session.updateRenderState( { baseLayer: glBaseLayer } );

					renderer.setPixelRatio( 1 );
					renderer.setSize( glBaseLayer.framebufferWidth, glBaseLayer.framebufferHeight, false );

					newRenderTarget = new WebGLRenderTarget(
						glBaseLayer.framebufferWidth,
						glBaseLayer.framebufferHeight,
						{
							format: RGBAFormat,
							type: UnsignedByteType,
							colorSpace: renderer.outputColorSpace,
							stencilBuffer: attributes.stencil,
							resolveDepthBuffer: ( glBaseLayer.ignoreDepthValues === false ),
							resolveStencilBuffer: ( glBaseLayer.ignoreDepthValues === false )

						}
					);

				} else {

					let depthFormat = null;
					let depthType = null;
					let glDepthFormat = null;

					if ( attributes.depth ) {

						glDepthFormat = attributes.stencil ? gl.DEPTH24_STENCIL8 : gl.DEPTH_COMPONENT24;
						depthFormat = attributes.stencil ? DepthStencilFormat : DepthFormat;
						depthType = attributes.stencil ? UnsignedInt248Type : UnsignedIntType;

					}

					const projectionlayerInit = {
						colorFormat: gl.RGBA8,
						depthFormat: glDepthFormat,
						scaleFactor: framebufferScaleFactor
					};

					glProjLayer = glBinding.createProjectionLayer( projectionlayerInit );

					session.updateRenderState( { layers: [ glProjLayer ] } );

					renderer.setPixelRatio( 1 );
					renderer.setSize( glProjLayer.textureWidth, glProjLayer.textureHeight, false );

					newRenderTarget = new WebGLRenderTarget(
						glProjLayer.textureWidth,
						glProjLayer.textureHeight,
						{
							format: RGBAFormat,
							type: UnsignedByteType,
							depthTexture: new DepthTexture( glProjLayer.textureWidth, glProjLayer.textureHeight, depthType, undefined, undefined, undefined, undefined, undefined, undefined, depthFormat ),
							stencilBuffer: attributes.stencil,
							colorSpace: renderer.outputColorSpace,
							samples: attributes.antialias ? 4 : 0,
							resolveDepthBuffer: ( glProjLayer.ignoreDepthValues === false ),
							resolveStencilBuffer: ( glProjLayer.ignoreDepthValues === false )
						} );

				}

				newRenderTarget.isXRRenderTarget = true; // TODO Remove this when possible, see #23278

				this.setFoveation( foveation );

				customReferenceSpace = null;
				referenceSpace = await session.requestReferenceSpace( referenceSpaceType );

				animation.setContext( session );
				animation.start();

				scope.isPresenting = true;

				scope.dispatchEvent( { type: 'sessionstart' } );

			}

		};

		/**
		 * Returns the environment blend mode from the current XR session.
		 *
		 * @return {'opaque'|'additive'|'alpha-blend'|undefined} The environment blend mode. Returns `undefined` when used outside of a XR session.
		 */
		this.getEnvironmentBlendMode = function () {

			if ( session !== null ) {

				return session.environmentBlendMode;

			}

		};

		/**
		 * Returns the current depth texture computed via depth sensing.
		 *
		 * @return {?Texture} The depth texture.
		 */
		this.getDepthTexture = function () {

			return depthSensing.getDepthTexture();

		};

		function onInputSourcesChange( event ) {

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

		//

		const cameraLPos = new Vector3();
		const cameraRPos = new Vector3();

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
		function setProjectionFromUnion( camera, cameraL, cameraR ) {

			cameraLPos.setFromMatrixPosition( cameraL.matrixWorld );
			cameraRPos.setFromMatrixPosition( cameraR.matrixWorld );

			const ipd = cameraLPos.distanceTo( cameraRPos );

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

		function updateCamera( camera, parent ) {

			if ( parent === null ) {

				camera.matrixWorld.copy( camera.matrix );

			} else {

				camera.matrixWorld.multiplyMatrices( parent.matrixWorld, camera.matrix );

			}

			camera.matrixWorldInverse.copy( camera.matrixWorld ).invert();

		}

		/**
		 * Updates the state of the XR camera. Use this method on app level if you
		 * set cameraAutoUpdate` to `false`. The method requires the non-XR
		 * camera of the scene as a parameter. The passed in camera's transformation
		 * is automatically adjusted to the position of the XR camera when calling
		 * this method.
		 *
		 * @param {Camera} camera - The camera.
		 */
		this.updateCamera = function ( camera ) {

			if ( session === null ) return;

			let depthNear = camera.near;
			let depthFar = camera.far;

			if ( depthSensing.texture !== null ) {

				if ( depthSensing.depthNear > 0 ) depthNear = depthSensing.depthNear;
				if ( depthSensing.depthFar > 0 ) depthFar = depthSensing.depthFar;

			}

			cameraXR.near = cameraR.near = cameraL.near = depthNear;
			cameraXR.far = cameraR.far = cameraL.far = depthFar;

			if ( _currentDepthNear !== cameraXR.near || _currentDepthFar !== cameraXR.far ) {

				// Note that the new renderState won't apply until the next frame. See #18320

				session.updateRenderState( {
					depthNear: cameraXR.near,
					depthFar: cameraXR.far
				} );

				_currentDepthNear = cameraXR.near;
				_currentDepthFar = cameraXR.far;

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

		};

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

		/**
		 * Returns an instance of {@link ArrayCamera} which represents the XR camera
		 * of the active XR session. For each view it holds a separate camera object.
		 *
		 * The camera's `fov` is currently not used and does not reflect the fov of
		 * the XR camera. If you need the fov on app level, you have to compute in
		 * manually from the XR camera's projection matrices.
		 *
		 * @return {ArrayCamera} The XR camera.
		 */
		this.getCamera = function () {

			return cameraXR;

		};

		/**
		 * Returns the amount of foveation used by the XR compositor for the projection layer.
		 *
		 * @return {number|undefined} The amount of foveation.
		 */
		this.getFoveation = function () {

			if ( glProjLayer === null && glBaseLayer === null ) {

				return undefined;

			}

			return foveation;

		};

		/**
		 * Sets the foveation value.
		 *
		 * @param {number} value - A number in the range `[0,1]` where `0` means no foveation (full resolution)
		 * and `1` means maximum foveation (the edges render at lower resolution).
		 */
		this.setFoveation = function ( value ) {

			// 0 = no foveation = full resolution
			// 1 = maximum foveation = the edges render at lower resolution

			foveation = value;

			if ( glProjLayer !== null ) {

				glProjLayer.fixedFoveation = value;

			}

			if ( glBaseLayer !== null && glBaseLayer.fixedFoveation !== undefined ) {

				glBaseLayer.fixedFoveation = value;

			}

		};

		/**
		 * Returns `true` if depth sensing is supported.
		 *
		 * @return {boolean} Whether depth sensing is supported or not.
		 */
		this.hasDepthSensing = function () {

			return depthSensing.texture !== null;

		};

		/**
		 * Returns the depth sensing mesh.
		 *
		 * @return {Mesh} The depth sensing mesh.
		 */
		this.getDepthSensingMesh = function () {

			return depthSensing.getMesh( cameraXR );

		};

		/**
		 * Retrieves an opaque texture from the view-aligned {@link XRCamera}.
		 * Only available during the current animation loop.
		 *
		 * @param {XRCamera} xrCamera - The camera to query.
		 * @return {?Texture} An opaque texture representing the current raw camera frame.
		 */
		this.getCameraTexture = function ( xrCamera ) {

			return cameraAccessTextures[ xrCamera ];

		};

		// Animation Loop

		let onAnimationFrameCallback = null;

		function onAnimationFrame( time, frame ) {

			pose = frame.getViewerPose( customReferenceSpace || referenceSpace );
			xrFrame = frame;

			if ( pose !== null ) {

				const views = pose.views;

				if ( glBaseLayer !== null ) {

					renderer.setRenderTargetFramebuffer( newRenderTarget, glBaseLayer.framebuffer );
					renderer.setRenderTarget( newRenderTarget );

				}

				let cameraXRNeedsUpdate = false;

				// check if it's necessary to rebuild cameraXR's camera list

				if ( views.length !== cameraXR.cameras.length ) {

					cameraXR.cameras.length = 0;
					cameraXRNeedsUpdate = true;

				}

				for ( let i = 0; i < views.length; i ++ ) {

					const view = views[ i ];

					let viewport = null;

					if ( glBaseLayer !== null ) {

						viewport = glBaseLayer.getViewport( view );

					} else {

						const glSubImage = glBinding.getViewSubImage( glProjLayer, view );
						viewport = glSubImage.viewport;

						// For side-by-side projection, we only produce a single texture for both eyes.
						if ( i === 0 ) {

							renderer.setRenderTargetTextures(
								newRenderTarget,
								glSubImage.colorTexture,
								glSubImage.depthStencilTexture );

							renderer.setRenderTarget( newRenderTarget );

						}

					}

					let camera = cameras[ i ];

					if ( camera === undefined ) {

						camera = new PerspectiveCamera();
						camera.layers.enable( i );
						camera.viewport = new Vector4();
						cameras[ i ] = camera;

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

				//

				const enabledFeatures = session.enabledFeatures;
				const gpuDepthSensingEnabled = enabledFeatures &&
					enabledFeatures.includes( 'depth-sensing' ) &&
					session.depthUsage == 'gpu-optimized';

				if ( gpuDepthSensingEnabled && glBinding ) {

					const depthData = glBinding.getDepthInformation( views[ 0 ] );

					if ( depthData && depthData.isValid && depthData.texture ) {

						depthSensing.init( depthData, session.renderState );

					}

				}

				const cameraAccessEnabled = enabledFeatures &&
				    enabledFeatures.includes( 'camera-access' );

				if ( cameraAccessEnabled ) {

					renderer.state.unbindTexture();

					if ( glBinding ) {

						for ( let i = 0; i < views.length; i ++ ) {

							const camera = views[ i ].camera;

							if ( camera ) {

								let cameraTex = cameraAccessTextures[ camera ];

								if ( ! cameraTex ) {

									cameraTex = new ExternalTexture();
									cameraAccessTextures[ camera ] = cameraTex;

								}

								const glTexture = glBinding.getCameraImage( camera );
								cameraTex.sourceTexture = glTexture;

							}

						}

					}

				}

			}

			//

			for ( let i = 0; i < controllers.length; i ++ ) {

				const inputSource = controllerInputSources[ i ];
				const controller = controllers[ i ];

				if ( inputSource !== null && controller !== undefined ) {

					controller.update( inputSource, frame, customReferenceSpace || referenceSpace );

				}

			}

			if ( onAnimationFrameCallback ) onAnimationFrameCallback( time, frame );

			if ( frame.detectedPlanes ) {

				scope.dispatchEvent( { type: 'planesdetected', data: frame } );

			}

			xrFrame = null;

		}

		const animation = new WebGLAnimation();

		animation.setAnimationLoop( onAnimationFrame );

		this.setAnimationLoop = function ( callback ) {

			onAnimationFrameCallback = callback;

		};

		this.dispose = function () {};

	}

}
```
</details>


---