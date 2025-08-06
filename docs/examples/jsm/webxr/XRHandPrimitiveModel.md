[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `XRHandPrimitiveModel.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 8 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/webxr/XRHandPrimitiveModel.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DynamicDrawUsage` | `three` |
| `SphereGeometry` | `three` |
| `BoxGeometry` | `three` |
| `MeshStandardMaterial` | `three` |
| `InstancedMesh` | `three` |
| `Matrix4` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_matrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `_vector` | `any` | let/var | `new Vector3()` | ✗ |
| `geometry` | `any` | let/var | `*not shown*` | ✗ |
| `material` | `any` | let/var | `new MeshStandardMaterial()` | ✗ |
| `defaultRadius` | `0.008` | let/var | `0.008` | ✗ |
| `joints` | `any` | let/var | `this.controller.joints` | ✗ |
| `count` | `number` | let/var | `0` | ✗ |
| `joint` | `any` | let/var | `joints[ this.joints[ i ] ]` | ✗ |


---

## Functions

### `XRHandPrimitiveModel.updateMesh(): void`

**JSDoc:**
```typescript
/**
	 * Updates the mesh based on the tracked XR joints data.
	 */
```

**Returns:** `void`

**Calls:**

- `_vector.setScalar`
- `_matrix.compose`
- `this.handMesh.setMatrixAt`

<details><summary>Code</summary>

```typescript
updateMesh() {

		const defaultRadius = 0.008;
		const joints = this.controller.joints;

		let count = 0;

		for ( let i = 0; i < this.joints.length; i ++ ) {

			const joint = joints[ this.joints[ i ] ];

			if ( joint.visible ) {

				_vector.setScalar( joint.jointRadius || defaultRadius );
				_matrix.compose( joint.position, joint.quaternion, _vector );
				this.handMesh.setMatrixAt( i, _matrix );

				count ++;

			}

		}

		this.handMesh.count = count;
		this.handMesh.instanceMatrix.needsUpdate = true;

	}
```
</details>


---

## Classes

### `XRHandPrimitiveModel`

<details><summary>Class Code</summary>

```ts
class XRHandPrimitiveModel {

	/**
	 * Constructs a new XR hand primitive model.
	 *
	 * @param {XRHandModel} handModel - The hand model.
	 * @param {Group} controller - The WebXR controller.
	 * @param {string} path - The model path.
	 * @param {XRHandedness} handedness - The handedness of the XR input source.
	 * @param {XRHandPrimitiveModel~Options} options - The model options.
	 */
	constructor( handModel, controller, path, handedness, options ) {

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
		 * The model's environment map.
		 *
		 * @type {?Texture}
		 * @default null
		 */
		this.envMap = null;

		let geometry;

		if ( ! options || ! options.primitive || options.primitive === 'sphere' ) {

			geometry = new SphereGeometry( 1, 10, 10 );

		} else if ( options.primitive === 'box' ) {

			geometry = new BoxGeometry( 1, 1, 1 );

		}

		const material = new MeshStandardMaterial();

		this.handMesh = new InstancedMesh( geometry, material, 30 );
		this.handMesh.frustumCulled = false;
		this.handMesh.instanceMatrix.setUsage( DynamicDrawUsage ); // will be updated every frame
		this.handMesh.castShadow = true;
		this.handMesh.receiveShadow = true;
		this.handModel.add( this.handMesh );

		this.joints = [
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
			'pinky-finger-tip'
		];

	}

	/**
	 * Updates the mesh based on the tracked XR joints data.
	 */
	updateMesh() {

		const defaultRadius = 0.008;
		const joints = this.controller.joints;

		let count = 0;

		for ( let i = 0; i < this.joints.length; i ++ ) {

			const joint = joints[ this.joints[ i ] ];

			if ( joint.visible ) {

				_vector.setScalar( joint.jointRadius || defaultRadius );
				_matrix.compose( joint.position, joint.quaternion, _vector );
				this.handMesh.setMatrixAt( i, _matrix );

				count ++;

			}

		}

		this.handMesh.count = count;
		this.handMesh.instanceMatrix.needsUpdate = true;

	}

}
```
</details>

#### Methods

##### `updateMesh(): void`

<details><summary>Code</summary>

```ts
updateMesh() {

		const defaultRadius = 0.008;
		const joints = this.controller.joints;

		let count = 0;

		for ( let i = 0; i < this.joints.length; i ++ ) {

			const joint = joints[ this.joints[ i ] ];

			if ( joint.visible ) {

				_vector.setScalar( joint.jointRadius || defaultRadius );
				_matrix.compose( joint.position, joint.quaternion, _vector );
				this.handMesh.setMatrixAt( i, _matrix );

				count ++;

			}

		}

		this.handMesh.count = count;
		this.handMesh.instanceMatrix.needsUpdate = true;

	}
```
</details>


---