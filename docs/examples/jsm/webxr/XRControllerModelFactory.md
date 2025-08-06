[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `XRControllerModelFactory.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 2 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/webxr/XRControllerModelFactory.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Mesh` | `three` |
| `MeshBasicMaterial` | `three` |
| `Object3D` | `three` |
| `SphereGeometry` | `three` |
| `GLTFLoader` | `../loaders/GLTFLoader.js` |
| `MotionControllerConstants` | `../libs/motion-controllers.module.js` |
| `fetchProfile` | `../libs/motion-controllers.module.js` |
| `MotionController` | `../libs/motion-controllers.module.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `DEFAULT_PROFILES_PATH` | `"https://cdn.jsdelivr.net/npm/@webxr-...` | let/var | `'https://cdn.jsdelivr.net/npm/@webxr-input-profiles/assets@1.0/dist/profiles'` | ✗ |
| `DEFAULT_PROFILE` | `"generic-trigger"` | let/var | `'generic-trigger'` | ✗ |
| `sphereGeometry` | `any` | let/var | `new SphereGeometry( 0.001 )` | ✗ |
| `material` | `any` | let/var | `new MeshBasicMaterial( { color: 0x0000FF } )` | ✗ |
| `sphere` | `any` | let/var | `new Mesh( sphereGeometry, material )` | ✗ |
| `controllerModel` | `XRControllerModel` | let/var | `new XRControllerModel()` | ✗ |
| `scene` | `any` | let/var | `null` | ✗ |
| `xrInputSource` | `any` | let/var | `event.data` | ✗ |
| `cachedAsset` | `any` | let/var | `this._assetCache[ controllerModel.motionController.assetUrl ]` | ✗ |


---

## Functions

### `XRControllerModel.setEnvironmentMap(envMap: Texture): XRControllerModel`

**JSDoc:**
```typescript
/**
	 * Sets an environment map that is applied to the controller model.
	 *
	 * @param {?Texture} envMap - The environment map to apply.
	 * @return {XRControllerModel} A reference to this instance.
	 */
```

**Parameters:**

- **`envMap`** `Texture`

**Returns:** `XRControllerModel`

**Calls:**

- `this.traverse`

<details><summary>Code</summary>

```typescript
setEnvironmentMap( envMap ) {

		if ( this.envMap == envMap ) {

			return this;

		}

		this.envMap = envMap;
		this.traverse( ( child ) => {

			if ( child.isMesh ) {

				child.material.envMap = this.envMap;
				child.material.needsUpdate = true;

			}

		} );

		return this;

	}
```
</details>

### `XRControllerModel.updateMatrixWorld(force: boolean): void`

**JSDoc:**
```typescript
/**
	 * Overwritten with a custom implementation. Polls data from the XRInputSource and updates the
	 * model's components to match the real world data.
	 *
	 * @param {boolean} [force=false] - When set to `true`, a recomputation of world matrices is forced even
	 * when {@link Object3D#matrixWorldAutoUpdate} is set to `false`.
	 */
```

**Parameters:**

- **`force`** `boolean`

**Returns:** `void`

**Calls:**

- `super.updateMatrixWorld`
- `this.motionController.updateFromGamepad`
- `Object.values( this.motionController.components ).forEach`
- `Object.values( component.visualResponses ).forEach`
- `valueNode.quaternion.slerpQuaternions`
- `valueNode.position.lerpVectors`

**Internal Comments:**
```
// Cause the MotionController to poll the Gamepad for data (x5)
// Update the 3D model to reflect the button, thumbstick, and touchpad state (x6)
// Update node data based on the visual responses' current states (x6)
// Skip if the visual response node is not found. No error is needed,
// because it will have been reported at load time.
// Calculate the new properties based on the weight supplied
```

<details><summary>Code</summary>

```typescript
updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		if ( ! this.motionController ) return;

		// Cause the MotionController to poll the Gamepad for data
		this.motionController.updateFromGamepad();

		// Update the 3D model to reflect the button, thumbstick, and touchpad state
		Object.values( this.motionController.components ).forEach( ( component ) => {

			// Update node data based on the visual responses' current states
			Object.values( component.visualResponses ).forEach( ( visualResponse ) => {

				const { valueNode, minNode, maxNode, value, valueNodeProperty } = visualResponse;

				// Skip if the visual response node is not found. No error is needed,
				// because it will have been reported at load time.
				if ( ! valueNode ) return;

				// Calculate the new properties based on the weight supplied
				if ( valueNodeProperty === MotionControllerConstants.VisualResponseProperty.VISIBILITY ) {

					valueNode.visible = value;

				} else if ( valueNodeProperty === MotionControllerConstants.VisualResponseProperty.TRANSFORM ) {

					valueNode.quaternion.slerpQuaternions(
						minNode.quaternion,
						maxNode.quaternion,
						value
					);

					valueNode.position.lerpVectors(
						minNode.position,
						maxNode.position,
						value
					);

				}

			} );

		} );

	}
```
</details>

### `findNodes(motionController: MotionController, scene: Object3D): void`

**JSDoc:**
```typescript
/**
 * Walks the model's tree to find the nodes needed to animate the components and
 * saves them to the motionController components for use in the frame loop. When
 * touchpads are found, attaches a touch dot to them.
 *
 * @private
 * @param {MotionController} motionController
 * @param {Object3D} scene
 */
```

**Parameters:**

- **`motionController`** `MotionController`
- **`scene`** `Object3D`

**Returns:** `void`

**Calls:**

- `Object.values( motionController.components ).forEach`
- `scene.getObjectByName`
- `component.touchPointNode.add`
- `console.warn`
- `Object.values( visualResponses ).forEach`

**Internal Comments:**
```
// Loop through the components and find the nodes needed for each components' visual responses (x6)
// Attach a touch dot to the touchpad. (x2)
// Loop through all the visual responses to be applied to this component (x6)
// If animating a transform, find the two nodes to be interpolated between.
// If the extents cannot be found, skip this animation
// If the target node cannot be found, skip this animation (x4)
```

<details><summary>Code</summary>

```typescript
function findNodes( motionController, scene ) {

	// Loop through the components and find the nodes needed for each components' visual responses
	Object.values( motionController.components ).forEach( ( component ) => {

		const { type, touchPointNodeName, visualResponses } = component;

		if ( type === MotionControllerConstants.ComponentType.TOUCHPAD ) {

			component.touchPointNode = scene.getObjectByName( touchPointNodeName );
			if ( component.touchPointNode ) {

				// Attach a touch dot to the touchpad.
				const sphereGeometry = new SphereGeometry( 0.001 );
				const material = new MeshBasicMaterial( { color: 0x0000FF } );
				const sphere = new Mesh( sphereGeometry, material );
				component.touchPointNode.add( sphere );

			} else {

				console.warn( `Could not find touch dot, ${component.touchPointNodeName}, in touchpad component ${component.id}` );

			}

		}

		// Loop through all the visual responses to be applied to this component
		Object.values( visualResponses ).forEach( ( visualResponse ) => {

			const { valueNodeName, minNodeName, maxNodeName, valueNodeProperty } = visualResponse;

			// If animating a transform, find the two nodes to be interpolated between.
			if ( valueNodeProperty === MotionControllerConstants.VisualResponseProperty.TRANSFORM ) {

				visualResponse.minNode = scene.getObjectByName( minNodeName );
				visualResponse.maxNode = scene.getObjectByName( maxNodeName );

				// If the extents cannot be found, skip this animation
				if ( ! visualResponse.minNode ) {

					console.warn( `Could not find ${minNodeName} in the model` );
					return;

				}

				if ( ! visualResponse.maxNode ) {

					console.warn( `Could not find ${maxNodeName} in the model` );
					return;

				}

			}

			// If the target node cannot be found, skip this animation
			visualResponse.valueNode = scene.getObjectByName( valueNodeName );
			if ( ! visualResponse.valueNode ) {

				console.warn( `Could not find ${valueNodeName} in the model` );

			}

		} );

	} );

}
```
</details>

### `addAssetSceneToControllerModel(controllerModel: any, scene: any): void`

**Parameters:**

- **`controllerModel`** `any`
- **`scene`** `any`

**Returns:** `void`

**Calls:**

- `findNodes`
- `scene.traverse`
- `controllerModel.add`

**Internal Comments:**
```
// Find the nodes needed for animation and cache them on the motionController. (x3)
// Apply any environment map that the mesh already has set.
// Add the glTF scene to the controllerModel. (x4)
```

<details><summary>Code</summary>

```typescript
function addAssetSceneToControllerModel( controllerModel, scene ) {

	// Find the nodes needed for animation and cache them on the motionController.
	findNodes( controllerModel.motionController, scene );

	// Apply any environment map that the mesh already has set.
	if ( controllerModel.envMap ) {

		scene.traverse( ( child ) => {

			if ( child.isMesh ) {

				child.material.envMap = controllerModel.envMap;
				child.material.needsUpdate = true;

			}

		} );

	}

	// Add the glTF scene to the controllerModel.
	controllerModel.add( scene );

}
```
</details>

### `XRControllerModelFactory.setPath(path: string): XRControllerModelFactory`

**JSDoc:**
```typescript
/**
	 * Sets the path to the model repository.
	 *
	 * @param {string} path - The path to set.
	 * @return {XRControllerModelFactory} A reference to this instance.
	 */
```

**Parameters:**

- **`path`** `string`

**Returns:** `XRControllerModelFactory`

<details><summary>Code</summary>

```typescript
setPath( path ) {

		this.path = path;

		return this;

	}
```
</details>

### `XRControllerModelFactory.createControllerModel(controller: Group): XRControllerModel`

**JSDoc:**
```typescript
/**
	 * Creates a controller model for the given WebXR controller.
	 *
	 * @param {Group} controller - The controller.
	 * @return {XRControllerModel} The XR controller model.
	 */
```

**Parameters:**

- **`controller`** `Group`

**Returns:** `XRControllerModel`

**Calls:**

- `controller.addEventListener`
- `fetchProfile( xrInputSource, this.path, DEFAULT_PROFILE ).then( ( { profile, assetPath } ) => {

				controllerModel.motionController = new MotionController(
					xrInputSource,
					profile,
					assetPath
				);

				const cachedAsset = this._assetCache[ controllerModel.motionController.assetUrl ];
				if ( cachedAsset ) {

					scene = cachedAsset.scene.clone();

					addAssetSceneToControllerModel( controllerModel, scene );

					if ( this.onLoad ) this.onLoad( scene );

				} else {

					if ( ! this.gltfLoader ) {

						throw new Error( 'GLTFLoader not set.' );

					}

					this.gltfLoader.setPath( '' );
					this.gltfLoader.load( controllerModel.motionController.assetUrl, ( asset ) => {

						this._assetCache[ controllerModel.motionController.assetUrl ] = asset;

						scene = asset.scene.clone();

						addAssetSceneToControllerModel( controllerModel, scene );

						if ( this.onLoad ) this.onLoad( scene );

					},
					null,
					() => {

						throw new Error( `Asset ${controllerModel.motionController.assetUrl} missing or malformed.` );

					} );

				}

			} ).catch`
- `console.warn`
- `controllerModel.remove`

<details><summary>Code</summary>

```typescript
createControllerModel( controller ) {

		const controllerModel = new XRControllerModel();
		let scene = null;

		controller.addEventListener( 'connected', ( event ) => {

			const xrInputSource = event.data;

			if ( xrInputSource.targetRayMode !== 'tracked-pointer' || ! xrInputSource.gamepad || xrInputSource.hand ) return;

			fetchProfile( xrInputSource, this.path, DEFAULT_PROFILE ).then( ( { profile, assetPath } ) => {

				controllerModel.motionController = new MotionController(
					xrInputSource,
					profile,
					assetPath
				);

				const cachedAsset = this._assetCache[ controllerModel.motionController.assetUrl ];
				if ( cachedAsset ) {

					scene = cachedAsset.scene.clone();

					addAssetSceneToControllerModel( controllerModel, scene );

					if ( this.onLoad ) this.onLoad( scene );

				} else {

					if ( ! this.gltfLoader ) {

						throw new Error( 'GLTFLoader not set.' );

					}

					this.gltfLoader.setPath( '' );
					this.gltfLoader.load( controllerModel.motionController.assetUrl, ( asset ) => {

						this._assetCache[ controllerModel.motionController.assetUrl ] = asset;

						scene = asset.scene.clone();

						addAssetSceneToControllerModel( controllerModel, scene );

						if ( this.onLoad ) this.onLoad( scene );

					},
					null,
					() => {

						throw new Error( `Asset ${controllerModel.motionController.assetUrl} missing or malformed.` );

					} );

				}

			} ).catch( ( err ) => {

				console.warn( err );

			} );

		} );

		controller.addEventListener( 'disconnected', () => {

			controllerModel.motionController = null;
			controllerModel.remove( scene );
			scene = null;

		} );

		return controllerModel;

	}
```
</details>


---

## Classes

### `XRControllerModel`

<details><summary>Class Code</summary>

```ts
class XRControllerModel extends Object3D {

	/**
	 * Constructs a new XR controller model.
	 */
	constructor() {

		super();

		/**
		 * The motion controller.
		 *
		 * @type {?MotionController}
		 * @default null
		 */
		this.motionController = null;

		/**
		 * The controller's environment map.
		 *
		 * @type {?Texture}
		 * @default null
		 */
		this.envMap = null;

	}

	/**
	 * Sets an environment map that is applied to the controller model.
	 *
	 * @param {?Texture} envMap - The environment map to apply.
	 * @return {XRControllerModel} A reference to this instance.
	 */
	setEnvironmentMap( envMap ) {

		if ( this.envMap == envMap ) {

			return this;

		}

		this.envMap = envMap;
		this.traverse( ( child ) => {

			if ( child.isMesh ) {

				child.material.envMap = this.envMap;
				child.material.needsUpdate = true;

			}

		} );

		return this;

	}

	/**
	 * Overwritten with a custom implementation. Polls data from the XRInputSource and updates the
	 * model's components to match the real world data.
	 *
	 * @param {boolean} [force=false] - When set to `true`, a recomputation of world matrices is forced even
	 * when {@link Object3D#matrixWorldAutoUpdate} is set to `false`.
	 */
	updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		if ( ! this.motionController ) return;

		// Cause the MotionController to poll the Gamepad for data
		this.motionController.updateFromGamepad();

		// Update the 3D model to reflect the button, thumbstick, and touchpad state
		Object.values( this.motionController.components ).forEach( ( component ) => {

			// Update node data based on the visual responses' current states
			Object.values( component.visualResponses ).forEach( ( visualResponse ) => {

				const { valueNode, minNode, maxNode, value, valueNodeProperty } = visualResponse;

				// Skip if the visual response node is not found. No error is needed,
				// because it will have been reported at load time.
				if ( ! valueNode ) return;

				// Calculate the new properties based on the weight supplied
				if ( valueNodeProperty === MotionControllerConstants.VisualResponseProperty.VISIBILITY ) {

					valueNode.visible = value;

				} else if ( valueNodeProperty === MotionControllerConstants.VisualResponseProperty.TRANSFORM ) {

					valueNode.quaternion.slerpQuaternions(
						minNode.quaternion,
						maxNode.quaternion,
						value
					);

					valueNode.position.lerpVectors(
						minNode.position,
						maxNode.position,
						value
					);

				}

			} );

		} );

	}

}
```
</details>

#### Methods

##### `setEnvironmentMap(envMap: Texture): XRControllerModel`

<details><summary>Code</summary>

```ts
setEnvironmentMap( envMap ) {

		if ( this.envMap == envMap ) {

			return this;

		}

		this.envMap = envMap;
		this.traverse( ( child ) => {

			if ( child.isMesh ) {

				child.material.envMap = this.envMap;
				child.material.needsUpdate = true;

			}

		} );

		return this;

	}
```
</details>

##### `updateMatrixWorld(force: boolean): void`

<details><summary>Code</summary>

```ts
updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		if ( ! this.motionController ) return;

		// Cause the MotionController to poll the Gamepad for data
		this.motionController.updateFromGamepad();

		// Update the 3D model to reflect the button, thumbstick, and touchpad state
		Object.values( this.motionController.components ).forEach( ( component ) => {

			// Update node data based on the visual responses' current states
			Object.values( component.visualResponses ).forEach( ( visualResponse ) => {

				const { valueNode, minNode, maxNode, value, valueNodeProperty } = visualResponse;

				// Skip if the visual response node is not found. No error is needed,
				// because it will have been reported at load time.
				if ( ! valueNode ) return;

				// Calculate the new properties based on the weight supplied
				if ( valueNodeProperty === MotionControllerConstants.VisualResponseProperty.VISIBILITY ) {

					valueNode.visible = value;

				} else if ( valueNodeProperty === MotionControllerConstants.VisualResponseProperty.TRANSFORM ) {

					valueNode.quaternion.slerpQuaternions(
						minNode.quaternion,
						maxNode.quaternion,
						value
					);

					valueNode.position.lerpVectors(
						minNode.position,
						maxNode.position,
						value
					);

				}

			} );

		} );

	}
```
</details>

### `XRControllerModelFactory`

<details><summary>Class Code</summary>

```ts
class XRControllerModelFactory {

	/**
	 * Constructs a new XR controller model factory.
	 *
	 * @param {?GLTFLoader} [gltfLoader=null] - A glTF loader that is used to load controller models.
	 * @param {?Function} [onLoad=null] - A callback that is executed when a controller model has been loaded.
	 */
	constructor( gltfLoader = null, onLoad = null ) {

		/**
		 * A glTF loader that is used to load controller models.
		 *
		 * @type {?GLTFLoader}
		 * @default null
		 */
		this.gltfLoader = gltfLoader;

		/**
		 * The path to the model repository.
		 *
		 * @type {string}
		 */
		this.path = DEFAULT_PROFILES_PATH;
		this._assetCache = {};

		/**
		 * A callback that is executed when a controller model has been loaded.
		 *
		 * @type {?Function}
		 * @default null
		 */
		this.onLoad = onLoad;

		// If a GLTFLoader wasn't supplied to the constructor create a new one.
		if ( ! this.gltfLoader ) {

			this.gltfLoader = new GLTFLoader();

		}

	}

	/**
	 * Sets the path to the model repository.
	 *
	 * @param {string} path - The path to set.
	 * @return {XRControllerModelFactory} A reference to this instance.
	 */
	setPath( path ) {

		this.path = path;

		return this;

	}

	/**
	 * Creates a controller model for the given WebXR controller.
	 *
	 * @param {Group} controller - The controller.
	 * @return {XRControllerModel} The XR controller model.
	 */
	createControllerModel( controller ) {

		const controllerModel = new XRControllerModel();
		let scene = null;

		controller.addEventListener( 'connected', ( event ) => {

			const xrInputSource = event.data;

			if ( xrInputSource.targetRayMode !== 'tracked-pointer' || ! xrInputSource.gamepad || xrInputSource.hand ) return;

			fetchProfile( xrInputSource, this.path, DEFAULT_PROFILE ).then( ( { profile, assetPath } ) => {

				controllerModel.motionController = new MotionController(
					xrInputSource,
					profile,
					assetPath
				);

				const cachedAsset = this._assetCache[ controllerModel.motionController.assetUrl ];
				if ( cachedAsset ) {

					scene = cachedAsset.scene.clone();

					addAssetSceneToControllerModel( controllerModel, scene );

					if ( this.onLoad ) this.onLoad( scene );

				} else {

					if ( ! this.gltfLoader ) {

						throw new Error( 'GLTFLoader not set.' );

					}

					this.gltfLoader.setPath( '' );
					this.gltfLoader.load( controllerModel.motionController.assetUrl, ( asset ) => {

						this._assetCache[ controllerModel.motionController.assetUrl ] = asset;

						scene = asset.scene.clone();

						addAssetSceneToControllerModel( controllerModel, scene );

						if ( this.onLoad ) this.onLoad( scene );

					},
					null,
					() => {

						throw new Error( `Asset ${controllerModel.motionController.assetUrl} missing or malformed.` );

					} );

				}

			} ).catch( ( err ) => {

				console.warn( err );

			} );

		} );

		controller.addEventListener( 'disconnected', () => {

			controllerModel.motionController = null;
			controllerModel.remove( scene );
			scene = null;

		} );

		return controllerModel;

	}

}
```
</details>

#### Methods

##### `setPath(path: string): XRControllerModelFactory`

<details><summary>Code</summary>

```ts
setPath( path ) {

		this.path = path;

		return this;

	}
```
</details>

##### `createControllerModel(controller: Group): XRControllerModel`

<details><summary>Code</summary>

```ts
createControllerModel( controller ) {

		const controllerModel = new XRControllerModel();
		let scene = null;

		controller.addEventListener( 'connected', ( event ) => {

			const xrInputSource = event.data;

			if ( xrInputSource.targetRayMode !== 'tracked-pointer' || ! xrInputSource.gamepad || xrInputSource.hand ) return;

			fetchProfile( xrInputSource, this.path, DEFAULT_PROFILE ).then( ( { profile, assetPath } ) => {

				controllerModel.motionController = new MotionController(
					xrInputSource,
					profile,
					assetPath
				);

				const cachedAsset = this._assetCache[ controllerModel.motionController.assetUrl ];
				if ( cachedAsset ) {

					scene = cachedAsset.scene.clone();

					addAssetSceneToControllerModel( controllerModel, scene );

					if ( this.onLoad ) this.onLoad( scene );

				} else {

					if ( ! this.gltfLoader ) {

						throw new Error( 'GLTFLoader not set.' );

					}

					this.gltfLoader.setPath( '' );
					this.gltfLoader.load( controllerModel.motionController.assetUrl, ( asset ) => {

						this._assetCache[ controllerModel.motionController.assetUrl ] = asset;

						scene = asset.scene.clone();

						addAssetSceneToControllerModel( controllerModel, scene );

						if ( this.onLoad ) this.onLoad( scene );

					},
					null,
					() => {

						throw new Error( `Asset ${controllerModel.motionController.assetUrl} missing or malformed.` );

					} );

				}

			} ).catch( ( err ) => {

				console.warn( err );

			} );

		} );

		controller.addEventListener( 'disconnected', () => {

			controllerModel.motionController = null;
			controllerModel.remove( scene );
			scene = null;

		} );

		return controllerModel;

	}
```
</details>


---