[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebXRController.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 13 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webxr/WebXRController.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `../../math/Vector3.js` |
| `Group` | `../../objects/Group.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_moveEvent` | `{ type: string; }` | let/var | `{ type: 'move' }` | ✗ |
| `hand` | `Group` | let/var | `this._hand` | ✗ |
| `inputPose` | `any` | let/var | `null` | ✗ |
| `gripPose` | `any` | let/var | `null` | ✗ |
| `handPose` | `any` | let/var | `null` | ✗ |
| `targetRay` | `Group` | let/var | `this._targetRay` | ✗ |
| `grip` | `Group` | let/var | `this._grip` | ✗ |
| `hand` | `Group` | let/var | `this._hand` | ✗ |
| `indexTip` | `any` | let/var | `hand.joints[ 'index-finger-tip' ]` | ✗ |
| `thumbTip` | `any` | let/var | `hand.joints[ 'thumb-tip' ]` | ✗ |
| `distanceToPinch` | `0.02` | let/var | `0.02` | ✗ |
| `threshold` | `0.005` | let/var | `0.005` | ✗ |
| `joint` | `Group` | let/var | `new Group()` | ✗ |


---

## Functions

### `WebXRController.getHandSpace(): Group`

**JSDoc:**
```typescript
/**
	 * Returns a group representing the hand space of the XR controller.
	 *
	 * @return {Group} A group representing the hand space of the XR controller.
	 */
```

**Returns:** `Group`

<details><summary>Code</summary>

```typescript
getHandSpace() {

		if ( this._hand === null ) {

			this._hand = new Group();
			this._hand.matrixAutoUpdate = false;
			this._hand.visible = false;

			this._hand.joints = {};
			this._hand.inputState = { pinching: false };

		}

		return this._hand;

	}
```
</details>

### `WebXRController.getTargetRaySpace(): Group`

**JSDoc:**
```typescript
/**
	 * Returns a group representing the target ray space of the XR controller.
	 *
	 * @return {Group} A group representing the target ray space of the XR controller.
	 */
```

**Returns:** `Group`

<details><summary>Code</summary>

```typescript
getTargetRaySpace() {

		if ( this._targetRay === null ) {

			this._targetRay = new Group();
			this._targetRay.matrixAutoUpdate = false;
			this._targetRay.visible = false;
			this._targetRay.hasLinearVelocity = false;
			this._targetRay.linearVelocity = new Vector3();
			this._targetRay.hasAngularVelocity = false;
			this._targetRay.angularVelocity = new Vector3();

		}

		return this._targetRay;

	}
```
</details>

### `WebXRController.getGripSpace(): Group`

**JSDoc:**
```typescript
/**
	 * Returns a group representing the grip space of the XR controller.
	 *
	 * @return {Group} A group representing the grip space of the XR controller.
	 */
```

**Returns:** `Group`

<details><summary>Code</summary>

```typescript
getGripSpace() {

		if ( this._grip === null ) {

			this._grip = new Group();
			this._grip.matrixAutoUpdate = false;
			this._grip.visible = false;
			this._grip.hasLinearVelocity = false;
			this._grip.linearVelocity = new Vector3();
			this._grip.hasAngularVelocity = false;
			this._grip.angularVelocity = new Vector3();

		}

		return this._grip;

	}
```
</details>

### `WebXRController.dispatchEvent(event: any): WebXRController`

**JSDoc:**
```typescript
/**
	 * Dispatches the given event to the groups representing
	 * the different coordinate spaces of the XR controller.
	 *
	 * @param {Object} event - The event to dispatch.
	 * @return {WebXRController} A reference to this instance.
	 */
```

**Parameters:**

- **`event`** `any`

**Returns:** `WebXRController`

**Calls:**

- `this._targetRay.dispatchEvent`
- `this._grip.dispatchEvent`
- `this._hand.dispatchEvent`

<details><summary>Code</summary>

```typescript
dispatchEvent( event ) {

		if ( this._targetRay !== null ) {

			this._targetRay.dispatchEvent( event );

		}

		if ( this._grip !== null ) {

			this._grip.dispatchEvent( event );

		}

		if ( this._hand !== null ) {

			this._hand.dispatchEvent( event );

		}

		return this;

	}
```
</details>

### `WebXRController.connect(inputSource: XRInputSource): WebXRController`

**JSDoc:**
```typescript
/**
	 * Connects the controller with the given XR input source.
	 *
	 * @param {XRInputSource} inputSource - The input source.
	 * @return {WebXRController} A reference to this instance.
	 */
```

**Parameters:**

- **`inputSource`** `XRInputSource`

**Returns:** `WebXRController`

**Calls:**

- `inputSource.hand.values`
- `this._getHandJoint`
- `this.dispatchEvent`

**Internal Comments:**
```
// Initialize hand with joints when connected (x4)
```

<details><summary>Code</summary>

```typescript
connect( inputSource ) {

		if ( inputSource && inputSource.hand ) {

			const hand = this._hand;

			if ( hand ) {

				for ( const inputjoint of inputSource.hand.values() ) {

					// Initialize hand with joints when connected
					this._getHandJoint( hand, inputjoint );

				}

			}

		}

		this.dispatchEvent( { type: 'connected', data: inputSource } );

		return this;

	}
```
</details>

### `WebXRController.disconnect(inputSource: XRInputSource): WebXRController`

**JSDoc:**
```typescript
/**
	 * Disconnects the controller from the given XR input source.
	 *
	 * @param {XRInputSource} inputSource - The input source.
	 * @return {WebXRController} A reference to this instance.
	 */
```

**Parameters:**

- **`inputSource`** `XRInputSource`

**Returns:** `WebXRController`

**Calls:**

- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
disconnect( inputSource ) {

		this.dispatchEvent( { type: 'disconnected', data: inputSource } );

		if ( this._targetRay !== null ) {

			this._targetRay.visible = false;

		}

		if ( this._grip !== null ) {

			this._grip.visible = false;

		}

		if ( this._hand !== null ) {

			this._hand.visible = false;

		}

		return this;

	}
```
</details>

### `WebXRController.update(inputSource: XRInputSource, frame: XRFrame, referenceSpace: XRReferenceSpace): WebXRController`

**JSDoc:**
```typescript
/**
	 * Updates the controller with the given input source, XR frame and reference space.
	 * This updates the transformations of the groups that represent the different
	 * coordinate systems of the controller.
	 *
	 * @param {XRInputSource} inputSource - The input source.
	 * @param {XRFrame} frame - The XR frame.
	 * @param {XRReferenceSpace} referenceSpace - The reference space.
	 * @return {WebXRController} A reference to this instance.
	 */
```

**Parameters:**

- **`inputSource`** `XRInputSource`
- **`frame`** `XRFrame`
- **`referenceSpace`** `XRReferenceSpace`

**Returns:** `WebXRController`

**Calls:**

- `inputSource.hand.values`
- `frame.getJointPose`
- `this._getHandJoint`
- `joint.matrix.fromArray`
- `joint.matrix.decompose`
- `indexTip.position.distanceTo`
- `this.dispatchEvent`
- `frame.getPose`
- `grip.matrix.fromArray`
- `grip.matrix.decompose`
- `grip.linearVelocity.copy`
- `grip.angularVelocity.copy`
- `targetRay.matrix.fromArray`
- `targetRay.matrix.decompose`
- `targetRay.linearVelocity.copy`
- `targetRay.angularVelocity.copy`

**Internal Comments:**
```
// Update the joints groups with the XRJoint poses (x2)
// The transform of this joint will be updated with the joint pose on each frame (x2)
// Custom events (x2)
// Check pinchz (x2)
// Some runtimes (namely Vive Cosmos with Vive OpenXR Runtime) have only grip space and ray space is equal to it
```

<details><summary>Code</summary>

```typescript
update( inputSource, frame, referenceSpace ) {

		let inputPose = null;
		let gripPose = null;
		let handPose = null;

		const targetRay = this._targetRay;
		const grip = this._grip;
		const hand = this._hand;

		if ( inputSource && frame.session.visibilityState !== 'visible-blurred' ) {

			if ( hand && inputSource.hand ) {

				handPose = true;

				for ( const inputjoint of inputSource.hand.values() ) {

					// Update the joints groups with the XRJoint poses
					const jointPose = frame.getJointPose( inputjoint, referenceSpace );

					// The transform of this joint will be updated with the joint pose on each frame
					const joint = this._getHandJoint( hand, inputjoint );

					if ( jointPose !== null ) {

						joint.matrix.fromArray( jointPose.transform.matrix );
						joint.matrix.decompose( joint.position, joint.rotation, joint.scale );
						joint.matrixWorldNeedsUpdate = true;
						joint.jointRadius = jointPose.radius;

					}

					joint.visible = jointPose !== null;

				}

				// Custom events

				// Check pinchz
				const indexTip = hand.joints[ 'index-finger-tip' ];
				const thumbTip = hand.joints[ 'thumb-tip' ];
				const distance = indexTip.position.distanceTo( thumbTip.position );

				const distanceToPinch = 0.02;
				const threshold = 0.005;

				if ( hand.inputState.pinching && distance > distanceToPinch + threshold ) {

					hand.inputState.pinching = false;
					this.dispatchEvent( {
						type: 'pinchend',
						handedness: inputSource.handedness,
						target: this
					} );

				} else if ( ! hand.inputState.pinching && distance <= distanceToPinch - threshold ) {

					hand.inputState.pinching = true;
					this.dispatchEvent( {
						type: 'pinchstart',
						handedness: inputSource.handedness,
						target: this
					} );

				}

			} else {

				if ( grip !== null && inputSource.gripSpace ) {

					gripPose = frame.getPose( inputSource.gripSpace, referenceSpace );

					if ( gripPose !== null ) {

						grip.matrix.fromArray( gripPose.transform.matrix );
						grip.matrix.decompose( grip.position, grip.rotation, grip.scale );
						grip.matrixWorldNeedsUpdate = true;

						if ( gripPose.linearVelocity ) {

							grip.hasLinearVelocity = true;
							grip.linearVelocity.copy( gripPose.linearVelocity );

						} else {

							grip.hasLinearVelocity = false;

						}

						if ( gripPose.angularVelocity ) {

							grip.hasAngularVelocity = true;
							grip.angularVelocity.copy( gripPose.angularVelocity );

						} else {

							grip.hasAngularVelocity = false;

						}

					}

				}

			}

			if ( targetRay !== null ) {

				inputPose = frame.getPose( inputSource.targetRaySpace, referenceSpace );

				// Some runtimes (namely Vive Cosmos with Vive OpenXR Runtime) have only grip space and ray space is equal to it
				if ( inputPose === null && gripPose !== null ) {

					inputPose = gripPose;

				}

				if ( inputPose !== null ) {

					targetRay.matrix.fromArray( inputPose.transform.matrix );
					targetRay.matrix.decompose( targetRay.position, targetRay.rotation, targetRay.scale );
					targetRay.matrixWorldNeedsUpdate = true;

					if ( inputPose.linearVelocity ) {

						targetRay.hasLinearVelocity = true;
						targetRay.linearVelocity.copy( inputPose.linearVelocity );

					} else {

						targetRay.hasLinearVelocity = false;

					}

					if ( inputPose.angularVelocity ) {

						targetRay.hasAngularVelocity = true;
						targetRay.angularVelocity.copy( inputPose.angularVelocity );

					} else {

						targetRay.hasAngularVelocity = false;

					}

					this.dispatchEvent( _moveEvent );

				}

			}


		}

		if ( targetRay !== null ) {

			targetRay.visible = ( inputPose !== null );

		}

		if ( grip !== null ) {

			grip.visible = ( gripPose !== null );

		}

		if ( hand !== null ) {

			hand.visible = ( handPose !== null );

		}

		return this;

	}
```
</details>

### `WebXRController._getHandJoint(hand: Group, inputjoint: XRJointSpace): Group`

**JSDoc:**
```typescript
/**
	 * Returns a group representing the hand joint for the given input joint.
	 *
	 * @private
	 * @param {Group} hand - The group representing the hand space.
	 * @param {XRJointSpace} inputjoint - The hand joint data.
	 * @return {Group} A group representing the hand joint for the given input joint.
	 */
```

**Parameters:**

- **`hand`** `Group`
- **`inputjoint`** `XRJointSpace`

**Returns:** `Group`

**Calls:**

- `hand.add`

<details><summary>Code</summary>

```typescript
_getHandJoint( hand, inputjoint ) {

		if ( hand.joints[ inputjoint.jointName ] === undefined ) {

			const joint = new Group();
			joint.matrixAutoUpdate = false;
			joint.visible = false;
			hand.joints[ inputjoint.jointName ] = joint;

			hand.add( joint );

		}

		return hand.joints[ inputjoint.jointName ];

	}
```
</details>


---

## Classes

### `WebXRController`

<details><summary>Class Code</summary>

```ts
class WebXRController {

	/**
	 * Constructs a new XR controller.
	 */
	constructor() {

		/**
		 * A group representing the target ray space
		 * of the XR controller.
		 *
		 * @private
		 * @type {?Group}
		 * @default null
		 */
		this._targetRay = null;

		/**
		 * A group representing the grip space
		 * of the XR controller.
		 *
		 * @private
		 * @type {?Group}
		 * @default null
		 */
		this._grip = null;

		/**
		 * A group representing the hand space
		 * of the XR controller.
		 *
		 * @private
		 * @type {?Group}
		 * @default null
		 */
		this._hand = null;

	}

	/**
	 * Returns a group representing the hand space of the XR controller.
	 *
	 * @return {Group} A group representing the hand space of the XR controller.
	 */
	getHandSpace() {

		if ( this._hand === null ) {

			this._hand = new Group();
			this._hand.matrixAutoUpdate = false;
			this._hand.visible = false;

			this._hand.joints = {};
			this._hand.inputState = { pinching: false };

		}

		return this._hand;

	}

	/**
	 * Returns a group representing the target ray space of the XR controller.
	 *
	 * @return {Group} A group representing the target ray space of the XR controller.
	 */
	getTargetRaySpace() {

		if ( this._targetRay === null ) {

			this._targetRay = new Group();
			this._targetRay.matrixAutoUpdate = false;
			this._targetRay.visible = false;
			this._targetRay.hasLinearVelocity = false;
			this._targetRay.linearVelocity = new Vector3();
			this._targetRay.hasAngularVelocity = false;
			this._targetRay.angularVelocity = new Vector3();

		}

		return this._targetRay;

	}

	/**
	 * Returns a group representing the grip space of the XR controller.
	 *
	 * @return {Group} A group representing the grip space of the XR controller.
	 */
	getGripSpace() {

		if ( this._grip === null ) {

			this._grip = new Group();
			this._grip.matrixAutoUpdate = false;
			this._grip.visible = false;
			this._grip.hasLinearVelocity = false;
			this._grip.linearVelocity = new Vector3();
			this._grip.hasAngularVelocity = false;
			this._grip.angularVelocity = new Vector3();

		}

		return this._grip;

	}

	/**
	 * Dispatches the given event to the groups representing
	 * the different coordinate spaces of the XR controller.
	 *
	 * @param {Object} event - The event to dispatch.
	 * @return {WebXRController} A reference to this instance.
	 */
	dispatchEvent( event ) {

		if ( this._targetRay !== null ) {

			this._targetRay.dispatchEvent( event );

		}

		if ( this._grip !== null ) {

			this._grip.dispatchEvent( event );

		}

		if ( this._hand !== null ) {

			this._hand.dispatchEvent( event );

		}

		return this;

	}

	/**
	 * Connects the controller with the given XR input source.
	 *
	 * @param {XRInputSource} inputSource - The input source.
	 * @return {WebXRController} A reference to this instance.
	 */
	connect( inputSource ) {

		if ( inputSource && inputSource.hand ) {

			const hand = this._hand;

			if ( hand ) {

				for ( const inputjoint of inputSource.hand.values() ) {

					// Initialize hand with joints when connected
					this._getHandJoint( hand, inputjoint );

				}

			}

		}

		this.dispatchEvent( { type: 'connected', data: inputSource } );

		return this;

	}

	/**
	 * Disconnects the controller from the given XR input source.
	 *
	 * @param {XRInputSource} inputSource - The input source.
	 * @return {WebXRController} A reference to this instance.
	 */
	disconnect( inputSource ) {

		this.dispatchEvent( { type: 'disconnected', data: inputSource } );

		if ( this._targetRay !== null ) {

			this._targetRay.visible = false;

		}

		if ( this._grip !== null ) {

			this._grip.visible = false;

		}

		if ( this._hand !== null ) {

			this._hand.visible = false;

		}

		return this;

	}

	/**
	 * Updates the controller with the given input source, XR frame and reference space.
	 * This updates the transformations of the groups that represent the different
	 * coordinate systems of the controller.
	 *
	 * @param {XRInputSource} inputSource - The input source.
	 * @param {XRFrame} frame - The XR frame.
	 * @param {XRReferenceSpace} referenceSpace - The reference space.
	 * @return {WebXRController} A reference to this instance.
	 */
	update( inputSource, frame, referenceSpace ) {

		let inputPose = null;
		let gripPose = null;
		let handPose = null;

		const targetRay = this._targetRay;
		const grip = this._grip;
		const hand = this._hand;

		if ( inputSource && frame.session.visibilityState !== 'visible-blurred' ) {

			if ( hand && inputSource.hand ) {

				handPose = true;

				for ( const inputjoint of inputSource.hand.values() ) {

					// Update the joints groups with the XRJoint poses
					const jointPose = frame.getJointPose( inputjoint, referenceSpace );

					// The transform of this joint will be updated with the joint pose on each frame
					const joint = this._getHandJoint( hand, inputjoint );

					if ( jointPose !== null ) {

						joint.matrix.fromArray( jointPose.transform.matrix );
						joint.matrix.decompose( joint.position, joint.rotation, joint.scale );
						joint.matrixWorldNeedsUpdate = true;
						joint.jointRadius = jointPose.radius;

					}

					joint.visible = jointPose !== null;

				}

				// Custom events

				// Check pinchz
				const indexTip = hand.joints[ 'index-finger-tip' ];
				const thumbTip = hand.joints[ 'thumb-tip' ];
				const distance = indexTip.position.distanceTo( thumbTip.position );

				const distanceToPinch = 0.02;
				const threshold = 0.005;

				if ( hand.inputState.pinching && distance > distanceToPinch + threshold ) {

					hand.inputState.pinching = false;
					this.dispatchEvent( {
						type: 'pinchend',
						handedness: inputSource.handedness,
						target: this
					} );

				} else if ( ! hand.inputState.pinching && distance <= distanceToPinch - threshold ) {

					hand.inputState.pinching = true;
					this.dispatchEvent( {
						type: 'pinchstart',
						handedness: inputSource.handedness,
						target: this
					} );

				}

			} else {

				if ( grip !== null && inputSource.gripSpace ) {

					gripPose = frame.getPose( inputSource.gripSpace, referenceSpace );

					if ( gripPose !== null ) {

						grip.matrix.fromArray( gripPose.transform.matrix );
						grip.matrix.decompose( grip.position, grip.rotation, grip.scale );
						grip.matrixWorldNeedsUpdate = true;

						if ( gripPose.linearVelocity ) {

							grip.hasLinearVelocity = true;
							grip.linearVelocity.copy( gripPose.linearVelocity );

						} else {

							grip.hasLinearVelocity = false;

						}

						if ( gripPose.angularVelocity ) {

							grip.hasAngularVelocity = true;
							grip.angularVelocity.copy( gripPose.angularVelocity );

						} else {

							grip.hasAngularVelocity = false;

						}

					}

				}

			}

			if ( targetRay !== null ) {

				inputPose = frame.getPose( inputSource.targetRaySpace, referenceSpace );

				// Some runtimes (namely Vive Cosmos with Vive OpenXR Runtime) have only grip space and ray space is equal to it
				if ( inputPose === null && gripPose !== null ) {

					inputPose = gripPose;

				}

				if ( inputPose !== null ) {

					targetRay.matrix.fromArray( inputPose.transform.matrix );
					targetRay.matrix.decompose( targetRay.position, targetRay.rotation, targetRay.scale );
					targetRay.matrixWorldNeedsUpdate = true;

					if ( inputPose.linearVelocity ) {

						targetRay.hasLinearVelocity = true;
						targetRay.linearVelocity.copy( inputPose.linearVelocity );

					} else {

						targetRay.hasLinearVelocity = false;

					}

					if ( inputPose.angularVelocity ) {

						targetRay.hasAngularVelocity = true;
						targetRay.angularVelocity.copy( inputPose.angularVelocity );

					} else {

						targetRay.hasAngularVelocity = false;

					}

					this.dispatchEvent( _moveEvent );

				}

			}


		}

		if ( targetRay !== null ) {

			targetRay.visible = ( inputPose !== null );

		}

		if ( grip !== null ) {

			grip.visible = ( gripPose !== null );

		}

		if ( hand !== null ) {

			hand.visible = ( handPose !== null );

		}

		return this;

	}

	/**
	 * Returns a group representing the hand joint for the given input joint.
	 *
	 * @private
	 * @param {Group} hand - The group representing the hand space.
	 * @param {XRJointSpace} inputjoint - The hand joint data.
	 * @return {Group} A group representing the hand joint for the given input joint.
	 */
	_getHandJoint( hand, inputjoint ) {

		if ( hand.joints[ inputjoint.jointName ] === undefined ) {

			const joint = new Group();
			joint.matrixAutoUpdate = false;
			joint.visible = false;
			hand.joints[ inputjoint.jointName ] = joint;

			hand.add( joint );

		}

		return hand.joints[ inputjoint.jointName ];

	}

}
```
</details>

#### Methods

##### `getHandSpace(): Group`

<details><summary>Code</summary>

```ts
getHandSpace() {

		if ( this._hand === null ) {

			this._hand = new Group();
			this._hand.matrixAutoUpdate = false;
			this._hand.visible = false;

			this._hand.joints = {};
			this._hand.inputState = { pinching: false };

		}

		return this._hand;

	}
```
</details>

##### `getTargetRaySpace(): Group`

<details><summary>Code</summary>

```ts
getTargetRaySpace() {

		if ( this._targetRay === null ) {

			this._targetRay = new Group();
			this._targetRay.matrixAutoUpdate = false;
			this._targetRay.visible = false;
			this._targetRay.hasLinearVelocity = false;
			this._targetRay.linearVelocity = new Vector3();
			this._targetRay.hasAngularVelocity = false;
			this._targetRay.angularVelocity = new Vector3();

		}

		return this._targetRay;

	}
```
</details>

##### `getGripSpace(): Group`

<details><summary>Code</summary>

```ts
getGripSpace() {

		if ( this._grip === null ) {

			this._grip = new Group();
			this._grip.matrixAutoUpdate = false;
			this._grip.visible = false;
			this._grip.hasLinearVelocity = false;
			this._grip.linearVelocity = new Vector3();
			this._grip.hasAngularVelocity = false;
			this._grip.angularVelocity = new Vector3();

		}

		return this._grip;

	}
```
</details>

##### `dispatchEvent(event: any): WebXRController`

<details><summary>Code</summary>

```ts
dispatchEvent( event ) {

		if ( this._targetRay !== null ) {

			this._targetRay.dispatchEvent( event );

		}

		if ( this._grip !== null ) {

			this._grip.dispatchEvent( event );

		}

		if ( this._hand !== null ) {

			this._hand.dispatchEvent( event );

		}

		return this;

	}
```
</details>

##### `connect(inputSource: XRInputSource): WebXRController`

<details><summary>Code</summary>

```ts
connect( inputSource ) {

		if ( inputSource && inputSource.hand ) {

			const hand = this._hand;

			if ( hand ) {

				for ( const inputjoint of inputSource.hand.values() ) {

					// Initialize hand with joints when connected
					this._getHandJoint( hand, inputjoint );

				}

			}

		}

		this.dispatchEvent( { type: 'connected', data: inputSource } );

		return this;

	}
```
</details>

##### `disconnect(inputSource: XRInputSource): WebXRController`

<details><summary>Code</summary>

```ts
disconnect( inputSource ) {

		this.dispatchEvent( { type: 'disconnected', data: inputSource } );

		if ( this._targetRay !== null ) {

			this._targetRay.visible = false;

		}

		if ( this._grip !== null ) {

			this._grip.visible = false;

		}

		if ( this._hand !== null ) {

			this._hand.visible = false;

		}

		return this;

	}
```
</details>

##### `update(inputSource: XRInputSource, frame: XRFrame, referenceSpace: XRReferenceSpace): WebXRController`

<details><summary>Code</summary>

```ts
update( inputSource, frame, referenceSpace ) {

		let inputPose = null;
		let gripPose = null;
		let handPose = null;

		const targetRay = this._targetRay;
		const grip = this._grip;
		const hand = this._hand;

		if ( inputSource && frame.session.visibilityState !== 'visible-blurred' ) {

			if ( hand && inputSource.hand ) {

				handPose = true;

				for ( const inputjoint of inputSource.hand.values() ) {

					// Update the joints groups with the XRJoint poses
					const jointPose = frame.getJointPose( inputjoint, referenceSpace );

					// The transform of this joint will be updated with the joint pose on each frame
					const joint = this._getHandJoint( hand, inputjoint );

					if ( jointPose !== null ) {

						joint.matrix.fromArray( jointPose.transform.matrix );
						joint.matrix.decompose( joint.position, joint.rotation, joint.scale );
						joint.matrixWorldNeedsUpdate = true;
						joint.jointRadius = jointPose.radius;

					}

					joint.visible = jointPose !== null;

				}

				// Custom events

				// Check pinchz
				const indexTip = hand.joints[ 'index-finger-tip' ];
				const thumbTip = hand.joints[ 'thumb-tip' ];
				const distance = indexTip.position.distanceTo( thumbTip.position );

				const distanceToPinch = 0.02;
				const threshold = 0.005;

				if ( hand.inputState.pinching && distance > distanceToPinch + threshold ) {

					hand.inputState.pinching = false;
					this.dispatchEvent( {
						type: 'pinchend',
						handedness: inputSource.handedness,
						target: this
					} );

				} else if ( ! hand.inputState.pinching && distance <= distanceToPinch - threshold ) {

					hand.inputState.pinching = true;
					this.dispatchEvent( {
						type: 'pinchstart',
						handedness: inputSource.handedness,
						target: this
					} );

				}

			} else {

				if ( grip !== null && inputSource.gripSpace ) {

					gripPose = frame.getPose( inputSource.gripSpace, referenceSpace );

					if ( gripPose !== null ) {

						grip.matrix.fromArray( gripPose.transform.matrix );
						grip.matrix.decompose( grip.position, grip.rotation, grip.scale );
						grip.matrixWorldNeedsUpdate = true;

						if ( gripPose.linearVelocity ) {

							grip.hasLinearVelocity = true;
							grip.linearVelocity.copy( gripPose.linearVelocity );

						} else {

							grip.hasLinearVelocity = false;

						}

						if ( gripPose.angularVelocity ) {

							grip.hasAngularVelocity = true;
							grip.angularVelocity.copy( gripPose.angularVelocity );

						} else {

							grip.hasAngularVelocity = false;

						}

					}

				}

			}

			if ( targetRay !== null ) {

				inputPose = frame.getPose( inputSource.targetRaySpace, referenceSpace );

				// Some runtimes (namely Vive Cosmos with Vive OpenXR Runtime) have only grip space and ray space is equal to it
				if ( inputPose === null && gripPose !== null ) {

					inputPose = gripPose;

				}

				if ( inputPose !== null ) {

					targetRay.matrix.fromArray( inputPose.transform.matrix );
					targetRay.matrix.decompose( targetRay.position, targetRay.rotation, targetRay.scale );
					targetRay.matrixWorldNeedsUpdate = true;

					if ( inputPose.linearVelocity ) {

						targetRay.hasLinearVelocity = true;
						targetRay.linearVelocity.copy( inputPose.linearVelocity );

					} else {

						targetRay.hasLinearVelocity = false;

					}

					if ( inputPose.angularVelocity ) {

						targetRay.hasAngularVelocity = true;
						targetRay.angularVelocity.copy( inputPose.angularVelocity );

					} else {

						targetRay.hasAngularVelocity = false;

					}

					this.dispatchEvent( _moveEvent );

				}

			}


		}

		if ( targetRay !== null ) {

			targetRay.visible = ( inputPose !== null );

		}

		if ( grip !== null ) {

			grip.visible = ( gripPose !== null );

		}

		if ( hand !== null ) {

			hand.visible = ( handPose !== null );

		}

		return this;

	}
```
</details>

##### `_getHandJoint(hand: Group, inputjoint: XRJointSpace): Group`

<details><summary>Code</summary>

```ts
_getHandJoint( hand, inputjoint ) {

		if ( hand.joints[ inputjoint.jointName ] === undefined ) {

			const joint = new Group();
			joint.matrixAutoUpdate = false;
			joint.visible = false;
			hand.joints[ inputjoint.jointName ] = joint;

			hand.add( joint );

		}

		return hand.joints[ inputjoint.jointName ];

	}
```
</details>


---