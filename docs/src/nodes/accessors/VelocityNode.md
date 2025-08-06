[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `VelocityNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 11 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/VelocityNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `../core/TempNode.js` |
| `modelViewMatrix` | `./ModelNode.js` |
| `positionLocal` | `./Position.js` |
| `positionPrevious` | `./Position.js` |
| `nodeImmutable` | `../tsl/TSLBase.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `Matrix4` | `../../math/Matrix4.js` |
| `uniform` | `../core/UniformNode.js` |
| `sub` | `../math/OperatorNode.js` |
| `cameraProjectionMatrix` | `./Camera.js` |
| `renderGroup` | `../core/UniformGroupNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_objectData` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `projectionMatrix` | `any` | let/var | `( this.projectionMatrix === null ) ? cameraProjectionMatrix : uniform( this.p...` | ✗ |
| `matrix` | `any` | let/var | `objectData[ index ]` | ✗ |


---

## Functions

### `VelocityNode.setProjectionMatrix(projectionMatrix: Matrix4): void`

**JSDoc:**
```typescript
/**
	 * Sets the given projection matrix.
	 *
	 * @param {Matrix4} projectionMatrix - The projection matrix to set.
	 */
```

**Parameters:**

- **`projectionMatrix`** `Matrix4`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setProjectionMatrix( projectionMatrix ) {

		this.projectionMatrix = projectionMatrix;

	}
```
</details>

### `VelocityNode.update({ frameId, camera, object }: any): void`

**JSDoc:**
```typescript
/**
	 * Updates velocity specific uniforms.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
```

**Parameters:**

- **`{ frameId, camera, object }`** `any`

**Returns:** `void`

**Calls:**

- `getPreviousMatrix`
- `this.previousModelWorldMatrix.value.copy`
- `getData`
- `cameraData.previousProjectionMatrix.copy`
- `cameraData.previousCameraViewMatrix.copy`
- `cameraData.currentProjectionMatrix.copy`
- `cameraData.currentCameraViewMatrix.copy`
- `this.previousProjectionMatrix.value.copy`
- `this.previousCameraViewMatrix.value.copy`

**Internal Comments:**
```
// (x2)
```

<details><summary>Code</summary>

```typescript
update( { frameId, camera, object } ) {

		const previousModelMatrix = getPreviousMatrix( object );

		this.previousModelWorldMatrix.value.copy( previousModelMatrix );

		//

		const cameraData = getData( camera );

		if ( cameraData.frameId !== frameId ) {

			cameraData.frameId = frameId;

			if ( cameraData.previousProjectionMatrix === undefined ) {

				cameraData.previousProjectionMatrix = new Matrix4();
				cameraData.previousCameraViewMatrix = new Matrix4();

				cameraData.currentProjectionMatrix = new Matrix4();
				cameraData.currentCameraViewMatrix = new Matrix4();

				cameraData.previousProjectionMatrix.copy( this.projectionMatrix || camera.projectionMatrix );
				cameraData.previousCameraViewMatrix.copy( camera.matrixWorldInverse );

			} else {

				cameraData.previousProjectionMatrix.copy( cameraData.currentProjectionMatrix );
				cameraData.previousCameraViewMatrix.copy( cameraData.currentCameraViewMatrix );

			}

			cameraData.currentProjectionMatrix.copy( this.projectionMatrix || camera.projectionMatrix );
			cameraData.currentCameraViewMatrix.copy( camera.matrixWorldInverse );

			this.previousProjectionMatrix.value.copy( cameraData.previousProjectionMatrix );
			this.previousCameraViewMatrix.value.copy( cameraData.previousCameraViewMatrix );

		}

	}
```
</details>

### `VelocityNode.updateAfter({ object }: any): void`

**JSDoc:**
```typescript
/**
	 * Overwritten to updated velocity specific uniforms.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
```

**Parameters:**

- **`{ object }`** `any`

**Returns:** `void`

**Calls:**

- `getPreviousMatrix( object ).copy`

<details><summary>Code</summary>

```typescript
updateAfter( { object } ) {

		getPreviousMatrix( object ).copy( object.matrixWorld );

	}
```
</details>

### `VelocityNode.setup(): any`

**JSDoc:**
```typescript
/**
	 * Implements the velocity computation based on the previous and current vertex data.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @return {Node<vec2>} The motion vector.
	 */
```

**Returns:** `any`

**Calls:**

- `uniform (from ../core/UniformNode.js)`
- `this.previousCameraViewMatrix.mul`
- `projectionMatrix.mul( modelViewMatrix ).mul`
- `this.previousProjectionMatrix.mul( previousModelViewMatrix ).mul`
- `clipPositionCurrent.xy.div`
- `clipPositionPrevious.xy.div`
- `sub (from ../math/OperatorNode.js)`

<details><summary>Code</summary>

```typescript
setup( /*builder*/ ) {

		const projectionMatrix = ( this.projectionMatrix === null ) ? cameraProjectionMatrix : uniform( this.projectionMatrix );

		const previousModelViewMatrix = this.previousCameraViewMatrix.mul( this.previousModelWorldMatrix );

		const clipPositionCurrent = projectionMatrix.mul( modelViewMatrix ).mul( positionLocal );
		const clipPositionPrevious = this.previousProjectionMatrix.mul( previousModelViewMatrix ).mul( positionPrevious );

		const ndcPositionCurrent = clipPositionCurrent.xy.div( clipPositionCurrent.w );
		const ndcPositionPrevious = clipPositionPrevious.xy.div( clipPositionPrevious.w );

		const velocity = sub( ndcPositionCurrent, ndcPositionPrevious );

		return velocity;

	}
```
</details>

### `getData(object: any): any`

**Parameters:**

- **`object`** `any`

**Returns:** `any`

**Calls:**

- `_objectData.get`
- `_objectData.set`

<details><summary>Code</summary>

```typescript
function getData( object ) {

	let objectData = _objectData.get( object );

	if ( objectData === undefined ) {

		objectData = {};
		_objectData.set( object, objectData );

	}

	return objectData;

}
```
</details>

### `getPreviousMatrix(object: any, index: number): any`

**Parameters:**

- **`object`** `any`
- **`index`** `number`

**Returns:** `any`

**Calls:**

- `getData`
- `objectData[ index ].copy`

<details><summary>Code</summary>

```typescript
function getPreviousMatrix( object, index = 0 ) {

	const objectData = getData( object );

	let matrix = objectData[ index ];

	if ( matrix === undefined ) {

		objectData[ index ] = matrix = new Matrix4();
		objectData[ index ].copy( object.matrixWorld );

	}

	return matrix;

}
```
</details>


---

## Classes

### `VelocityNode`

<details><summary>Class Code</summary>

```ts
class VelocityNode extends TempNode {

	static get type() {

		return 'VelocityNode';

	}

	/**
	 * Constructs a new vertex color node.
	 */
	constructor() {

		super( 'vec2' );

		/**
		 * The current projection matrix.
		 *
		 * @type {?Matrix4}
		 * @default null
		 */
		this.projectionMatrix = null;

		/**
		 * Overwritten since velocity nodes are updated per object.
		 *
		 * @type {string}
		 * @default 'object'
		 */
		this.updateType = NodeUpdateType.OBJECT;

		/**
		 * Overwritten since velocity nodes save data after the update.
		 *
		 * @type {string}
		 * @default 'object'
		 */
		this.updateAfterType = NodeUpdateType.OBJECT;

		/**
		 * Uniform node representing the previous model matrix in world space.
		 *
		 * @type {UniformNode<mat4>}
		 * @default null
		 */
		this.previousModelWorldMatrix = uniform( new Matrix4() );

		/**
		 * Uniform node representing the previous projection matrix.
		 *
		 * @type {UniformNode<mat4>}
		 * @default null
		 */
		this.previousProjectionMatrix = uniform( new Matrix4() ).setGroup( renderGroup );

		/**
		 * Uniform node representing the previous view matrix.
		 *
		 * @type {UniformNode<mat4>}
		 * @default null
		 */
		this.previousCameraViewMatrix = uniform( new Matrix4() );

	}

	/**
	 * Sets the given projection matrix.
	 *
	 * @param {Matrix4} projectionMatrix - The projection matrix to set.
	 */
	setProjectionMatrix( projectionMatrix ) {

		this.projectionMatrix = projectionMatrix;

	}

	/**
	 * Updates velocity specific uniforms.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
	update( { frameId, camera, object } ) {

		const previousModelMatrix = getPreviousMatrix( object );

		this.previousModelWorldMatrix.value.copy( previousModelMatrix );

		//

		const cameraData = getData( camera );

		if ( cameraData.frameId !== frameId ) {

			cameraData.frameId = frameId;

			if ( cameraData.previousProjectionMatrix === undefined ) {

				cameraData.previousProjectionMatrix = new Matrix4();
				cameraData.previousCameraViewMatrix = new Matrix4();

				cameraData.currentProjectionMatrix = new Matrix4();
				cameraData.currentCameraViewMatrix = new Matrix4();

				cameraData.previousProjectionMatrix.copy( this.projectionMatrix || camera.projectionMatrix );
				cameraData.previousCameraViewMatrix.copy( camera.matrixWorldInverse );

			} else {

				cameraData.previousProjectionMatrix.copy( cameraData.currentProjectionMatrix );
				cameraData.previousCameraViewMatrix.copy( cameraData.currentCameraViewMatrix );

			}

			cameraData.currentProjectionMatrix.copy( this.projectionMatrix || camera.projectionMatrix );
			cameraData.currentCameraViewMatrix.copy( camera.matrixWorldInverse );

			this.previousProjectionMatrix.value.copy( cameraData.previousProjectionMatrix );
			this.previousCameraViewMatrix.value.copy( cameraData.previousCameraViewMatrix );

		}

	}

	/**
	 * Overwritten to updated velocity specific uniforms.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
	updateAfter( { object } ) {

		getPreviousMatrix( object ).copy( object.matrixWorld );

	}

	/**
	 * Implements the velocity computation based on the previous and current vertex data.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @return {Node<vec2>} The motion vector.
	 */
	setup( /*builder*/ ) {

		const projectionMatrix = ( this.projectionMatrix === null ) ? cameraProjectionMatrix : uniform( this.projectionMatrix );

		const previousModelViewMatrix = this.previousCameraViewMatrix.mul( this.previousModelWorldMatrix );

		const clipPositionCurrent = projectionMatrix.mul( modelViewMatrix ).mul( positionLocal );
		const clipPositionPrevious = this.previousProjectionMatrix.mul( previousModelViewMatrix ).mul( positionPrevious );

		const ndcPositionCurrent = clipPositionCurrent.xy.div( clipPositionCurrent.w );
		const ndcPositionPrevious = clipPositionPrevious.xy.div( clipPositionPrevious.w );

		const velocity = sub( ndcPositionCurrent, ndcPositionPrevious );

		return velocity;

	}

}
```
</details>

#### Methods

##### `setProjectionMatrix(projectionMatrix: Matrix4): void`

<details><summary>Code</summary>

```ts
setProjectionMatrix( projectionMatrix ) {

		this.projectionMatrix = projectionMatrix;

	}
```
</details>

##### `update({ frameId, camera, object }: any): void`

<details><summary>Code</summary>

```ts
update( { frameId, camera, object } ) {

		const previousModelMatrix = getPreviousMatrix( object );

		this.previousModelWorldMatrix.value.copy( previousModelMatrix );

		//

		const cameraData = getData( camera );

		if ( cameraData.frameId !== frameId ) {

			cameraData.frameId = frameId;

			if ( cameraData.previousProjectionMatrix === undefined ) {

				cameraData.previousProjectionMatrix = new Matrix4();
				cameraData.previousCameraViewMatrix = new Matrix4();

				cameraData.currentProjectionMatrix = new Matrix4();
				cameraData.currentCameraViewMatrix = new Matrix4();

				cameraData.previousProjectionMatrix.copy( this.projectionMatrix || camera.projectionMatrix );
				cameraData.previousCameraViewMatrix.copy( camera.matrixWorldInverse );

			} else {

				cameraData.previousProjectionMatrix.copy( cameraData.currentProjectionMatrix );
				cameraData.previousCameraViewMatrix.copy( cameraData.currentCameraViewMatrix );

			}

			cameraData.currentProjectionMatrix.copy( this.projectionMatrix || camera.projectionMatrix );
			cameraData.currentCameraViewMatrix.copy( camera.matrixWorldInverse );

			this.previousProjectionMatrix.value.copy( cameraData.previousProjectionMatrix );
			this.previousCameraViewMatrix.value.copy( cameraData.previousCameraViewMatrix );

		}

	}
```
</details>

##### `updateAfter({ object }: any): void`

<details><summary>Code</summary>

```ts
updateAfter( { object } ) {

		getPreviousMatrix( object ).copy( object.matrixWorld );

	}
```
</details>

##### `setup(): any`

<details><summary>Code</summary>

```ts
setup( /*builder*/ ) {

		const projectionMatrix = ( this.projectionMatrix === null ) ? cameraProjectionMatrix : uniform( this.projectionMatrix );

		const previousModelViewMatrix = this.previousCameraViewMatrix.mul( this.previousModelWorldMatrix );

		const clipPositionCurrent = projectionMatrix.mul( modelViewMatrix ).mul( positionLocal );
		const clipPositionPrevious = this.previousProjectionMatrix.mul( previousModelViewMatrix ).mul( positionPrevious );

		const ndcPositionCurrent = clipPositionCurrent.xy.div( clipPositionCurrent.w );
		const ndcPositionPrevious = clipPositionPrevious.xy.div( clipPositionPrevious.w );

		const velocity = sub( ndcPositionCurrent, ndcPositionPrevious );

		return velocity;

	}
```
</details>


---