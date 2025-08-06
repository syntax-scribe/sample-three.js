[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `XRHandMeshModel.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/webxr/XRHandMeshModel.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `GLTFLoader` | `../loaders/GLTFLoader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `DEFAULT_HAND_PROFILE_PATH` | `"https://cdn.jsdelivr.net/npm/@webxr-...` | let/var | `'https://cdn.jsdelivr.net/npm/@webxr-input-profiles/assets@1.0/dist/profiles/...` | ✗ |
| `object` | `any` | let/var | `gltf.scene.children[ 0 ]` | ✗ |
| `joints` | `string[]` | let/var | `[ 'wrist', 'thumb-metacarpal', 'thumb-phalanx-proximal', 'thumb-phalanx-dista...` | ✗ |
| `XRJoints` | `any` | let/var | `this.controller.joints` | ✗ |
| `bone` | `Bone` | let/var | `this.bones[ i ]` | ✗ |
| `XRJoint` | `any` | let/var | `XRJoints[ bone.jointName ]` | ✗ |
| `position` | `any` | let/var | `XRJoint.position` | ✗ |


---

## Functions

### `XRHandMeshModel.updateMesh(): void`

**JSDoc:**
```typescript
/**
	 * Updates the mesh based on the tracked XR joints data.
	 */
```

**Returns:** `void`

**Calls:**

- `bone.position.copy`
- `bone.quaternion.copy`

**Internal Comments:**
```
// XR Joints (x2)
```

<details><summary>Code</summary>

```typescript
updateMesh() {

		// XR Joints
		const XRJoints = this.controller.joints;

		for ( let i = 0; i < this.bones.length; i ++ ) {

			const bone = this.bones[ i ];

			if ( bone ) {

				const XRJoint = XRJoints[ bone.jointName ];

				if ( XRJoint.visible ) {

					const position = XRJoint.position;

					bone.position.copy( position );
					bone.quaternion.copy( XRJoint.quaternion );
					// bone.scale.setScalar( XRJoint.jointRadius || defaultRadius );

				}

			}

		}

	}
```
</details>


---

## Classes

### `XRHandMeshModel`

<details><summary>Class Code</summary>

```ts
class XRHandMeshModel {

	/**
	 * Constructs a new XR hand mesh model.
	 *
	 * @param {XRHandModel} handModel - The hand model.
	 * @param {Group} controller - The WebXR controller.
	 * @param {?string} path - The model path.
	 * @param {XRHandedness} handedness - The handedness of the XR input source.
	 * @param {?Loader} [loader=null] - The loader. If not provided, an instance of `GLTFLoader` will be used to load models.
	 * @param {?Function} [onLoad=null] - A callback that is executed when a controller model has been loaded.
	 */
	constructor( handModel, controller, path, handedness, loader = null, onLoad = null ) {

		/**
		 * The WebXR controller.
		 *
		 * @type {Group}
		 */
		this.controller = controller;

		/**
		 * The hand model.
		 *
		 * @type {XRHandModel}
		 */
		this.handModel = handModel;

		/**
		 * An array of bones representing the bones
		 * of the hand skeleton.
		 *
		 * @type {Array<Bone>}
		 */
		this.bones = [];

		if ( loader === null ) {

			loader = new GLTFLoader();
			loader.setPath( path || DEFAULT_HAND_PROFILE_PATH );

		}

		loader.load( `${handedness}.glb`, gltf => {

			const object = gltf.scene.children[ 0 ];
			this.handModel.add( object );

			const mesh = object.getObjectByProperty( 'type', 'SkinnedMesh' );
			mesh.frustumCulled = false;
			mesh.castShadow = true;
			mesh.receiveShadow = true;

			const joints = [
				'wrist',
				'thumb-metacarpal',
				'thumb-phalanx-proximal',
				'thumb-phalanx-distal',
				'thumb-tip',
				'index-finger-metacarpal',
				'index-finger-phalanx-proximal',
				'index-finger-phalanx-intermediate',
				'index-finger-phalanx-distal',
				'index-finger-tip',
				'middle-finger-metacarpal',
				'middle-finger-phalanx-proximal',
				'middle-finger-phalanx-intermediate',
				'middle-finger-phalanx-distal',
				'middle-finger-tip',
				'ring-finger-metacarpal',
				'ring-finger-phalanx-proximal',
				'ring-finger-phalanx-intermediate',
				'ring-finger-phalanx-distal',
				'ring-finger-tip',
				'pinky-finger-metacarpal',
				'pinky-finger-phalanx-proximal',
				'pinky-finger-phalanx-intermediate',
				'pinky-finger-phalanx-distal',
				'pinky-finger-tip',
			];

			joints.forEach( jointName => {

				const bone = object.getObjectByName( jointName );

				if ( bone !== undefined ) {

					bone.jointName = jointName;

				} else {

					console.warn( `Couldn't find ${jointName} in ${handedness} hand mesh` );

				}

				this.bones.push( bone );

			} );

			if ( onLoad ) onLoad( object );

		} );

	}

	/**
	 * Updates the mesh based on the tracked XR joints data.
	 */
	updateMesh() {

		// XR Joints
		const XRJoints = this.controller.joints;

		for ( let i = 0; i < this.bones.length; i ++ ) {

			const bone = this.bones[ i ];

			if ( bone ) {

				const XRJoint = XRJoints[ bone.jointName ];

				if ( XRJoint.visible ) {

					const position = XRJoint.position;

					bone.position.copy( position );
					bone.quaternion.copy( XRJoint.quaternion );
					// bone.scale.setScalar( XRJoint.jointRadius || defaultRadius );

				}

			}

		}

	}

}
```
</details>

#### Methods

##### `updateMesh(): void`

<details><summary>Code</summary>

```ts
updateMesh() {

		// XR Joints
		const XRJoints = this.controller.joints;

		for ( let i = 0; i < this.bones.length; i ++ ) {

			const bone = this.bones[ i ];

			if ( bone ) {

				const XRJoint = XRJoints[ bone.jointName ];

				if ( XRJoint.visible ) {

					const position = XRJoint.position;

					bone.position.copy( position );
					bone.quaternion.copy( XRJoint.quaternion );
					// bone.scale.setScalar( XRJoint.jointRadius || defaultRadius );

				}

			}

		}

	}
```
</details>


---