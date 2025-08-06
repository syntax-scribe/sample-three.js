[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `OculusHandModel.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/webxr/OculusHandModel.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Object3D` | `three` |
| `Sphere` | `three` |
| `Box3` | `three` |
| `XRHandMeshModel` | `./XRHandMeshModel.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `TOUCH_RADIUS` | `0.01` | let/var | `0.01` | ✗ |
| `POINTING_JOINT` | `"index-finger-tip"` | let/var | `'index-finger-tip'` | ✗ |
| `xrInputSource` | `any` | let/var | `event.data` | ✗ |
| `indexFingerTip` | `any` | let/var | `this.controller.joints[ POINTING_JOINT ]` | ✗ |
| `indexSphere` | `any` | let/var | `new Sphere( pointerPosition, TOUCH_RADIUS )` | ✗ |


---

## Functions

### `OculusHandModel.updateMatrixWorld(force: boolean): void`

**JSDoc:**
```typescript
/**
	 * Overwritten with a custom implementation. Makes sure the motion controller updates the mesh.
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
- `this.motionController.updateMesh`

<details><summary>Code</summary>

```typescript
updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		if ( this.motionController ) {

			this.motionController.updateMesh();

		}

	}
```
</details>

### `OculusHandModel.getPointerPosition(): any`

**JSDoc:**
```typescript
/**
	 * Returns the pointer position which is the position of the index finger tip.
	 *
	 * @return {Vector3|null} The pointer position. Returns `null` if not index finger tip joint was found.
	 */
```

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getPointerPosition() {

		const indexFingerTip = this.controller.joints[ POINTING_JOINT ];
		if ( indexFingerTip ) {

			return indexFingerTip.position;

		} else {

			return null;

		}

	}
```
</details>

### `OculusHandModel.intersectBoxObject(boxObject: Mesh): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the current pointer position (the index finger tip) intersections
	 * with the given box object.
	 *
	 *  @param {Mesh} boxObject - The box object.
	 * @return {boolean} Whether an intersection was found or not.
	 */
```

**Parameters:**

- **`boxObject`** `Mesh`

**Returns:** `boolean`

**Calls:**

- `this.getPointerPosition`
- `new Box3().setFromObject`
- `indexSphere.intersectsBox`

<details><summary>Code</summary>

```typescript
intersectBoxObject( boxObject ) {

		const pointerPosition = this.getPointerPosition();
		if ( pointerPosition ) {

			const indexSphere = new Sphere( pointerPosition, TOUCH_RADIUS );
			const box = new Box3().setFromObject( boxObject );
			return indexSphere.intersectsBox( box );

		} else {

			return false;

		}

	}
```
</details>

### `OculusHandModel.checkButton(button: any): void`

**JSDoc:**
```typescript
/**
	 * Executed actions depending on the interaction state with
	 * the given button.
	 *
	 *  @param {Object} button - The button.
	 */
```

**Parameters:**

- **`button`** `any`

**Returns:** `void`

**Calls:**

- `this.intersectBoxObject`
- `button.onPress`
- `button.onClear`
- `button.isPressed`
- `button.whilePressed`

<details><summary>Code</summary>

```typescript
checkButton( button ) {

		if ( this.intersectBoxObject( button ) ) {

			button.onPress();

		} else {

			button.onClear();

		}

		if ( button.isPressed() ) {

			button.whilePressed();

		}

	}
```
</details>


---

## Classes

### `OculusHandModel`

<details><summary>Class Code</summary>

```ts
class OculusHandModel extends Object3D {

	/**
	 * Constructs a new Oculus hand model.
	 *
	 * @param {Group} controller - The hand controller.
	 * @param {?Loader} [loader=null] - A loader that is used to load hand models.
	 * @param {?Function} [onLoad=null] - A callback that is executed when a hand model has been loaded.
	 */
	constructor( controller, loader = null, onLoad = null ) {

		super();

		/**
		 * The hand controller.
		 *
		 * @type {Group}
		 */
		this.controller = controller;

		/**
		 * The motion controller.
		 *
		 * @type {?MotionController}
		 * @default null
		 */
		this.motionController = null;

		/**
		 * The model's environment map.
		 *
		 * @type {?Texture}
		 * @default null
		 */
		this.envMap = null;

		/**
		 * A loader that is used to load hand models.
		 *
		 * @type {?Loader}
		 * @default null
		 */
		this.loader = loader;

		/**
		 * A callback that is executed when a hand model has been loaded.
		 *
		 * @type {?Function}
		 * @default null
		 */
		this.onLoad = onLoad;

		/**
		 * The path to the model repository.
		 *
		 * @type {?string}
		 * @default null
		 */
		this.path = null;

		/**
		 * The model mesh.
		 *
		 * @type {Mesh}
		 * @default null
		 */
		this.mesh = null;

		controller.addEventListener( 'connected', ( event ) => {

			const xrInputSource = event.data;

			if ( xrInputSource.hand && ! this.motionController ) {

				this.xrInputSource = xrInputSource;

				this.motionController = new XRHandMeshModel( this, controller, this.path, xrInputSource.handedness, this.loader, this.onLoad );

			}

		} );

		controller.addEventListener( 'disconnected', () => {

			this.clear();
			this.motionController = null;

		} );

	}

	/**
	 * Overwritten with a custom implementation. Makes sure the motion controller updates the mesh.
	 *
	 * @param {boolean} [force=false] - When set to `true`, a recomputation of world matrices is forced even
	 * when {@link Object3D#matrixWorldAutoUpdate} is set to `false`.
	 */
	updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		if ( this.motionController ) {

			this.motionController.updateMesh();

		}

	}

	/**
	 * Returns the pointer position which is the position of the index finger tip.
	 *
	 * @return {Vector3|null} The pointer position. Returns `null` if not index finger tip joint was found.
	 */
	getPointerPosition() {

		const indexFingerTip = this.controller.joints[ POINTING_JOINT ];
		if ( indexFingerTip ) {

			return indexFingerTip.position;

		} else {

			return null;

		}

	}

	/**
	 * Returns `true` if the current pointer position (the index finger tip) intersections
	 * with the given box object.
	 *
	 *  @param {Mesh} boxObject - The box object.
	 * @return {boolean} Whether an intersection was found or not.
	 */
	intersectBoxObject( boxObject ) {

		const pointerPosition = this.getPointerPosition();
		if ( pointerPosition ) {

			const indexSphere = new Sphere( pointerPosition, TOUCH_RADIUS );
			const box = new Box3().setFromObject( boxObject );
			return indexSphere.intersectsBox( box );

		} else {

			return false;

		}

	}

	/**
	 * Executed actions depending on the interaction state with
	 * the given button.
	 *
	 *  @param {Object} button - The button.
	 */
	checkButton( button ) {

		if ( this.intersectBoxObject( button ) ) {

			button.onPress();

		} else {

			button.onClear();

		}

		if ( button.isPressed() ) {

			button.whilePressed();

		}

	}

}
```
</details>

#### Methods

##### `updateMatrixWorld(force: boolean): void`

<details><summary>Code</summary>

```ts
updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		if ( this.motionController ) {

			this.motionController.updateMesh();

		}

	}
```
</details>

##### `getPointerPosition(): any`

<details><summary>Code</summary>

```ts
getPointerPosition() {

		const indexFingerTip = this.controller.joints[ POINTING_JOINT ];
		if ( indexFingerTip ) {

			return indexFingerTip.position;

		} else {

			return null;

		}

	}
```
</details>

##### `intersectBoxObject(boxObject: Mesh): boolean`

<details><summary>Code</summary>

```ts
intersectBoxObject( boxObject ) {

		const pointerPosition = this.getPointerPosition();
		if ( pointerPosition ) {

			const indexSphere = new Sphere( pointerPosition, TOUCH_RADIUS );
			const box = new Box3().setFromObject( boxObject );
			return indexSphere.intersectsBox( box );

		} else {

			return false;

		}

	}
```
</details>

##### `checkButton(button: any): void`

<details><summary>Code</summary>

```ts
checkButton( button ) {

		if ( this.intersectBoxObject( button ) ) {

			button.onPress();

		} else {

			button.onClear();

		}

		if ( button.isPressed() ) {

			button.whilePressed();

		}

	}
```
</details>


---