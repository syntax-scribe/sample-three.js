[⬅️ Back to Table of Contents](../../index.md)

# 📄 `PointLightShadow.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/lights/PointLightShadow.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LightShadow` | `./LightShadow.js` |
| `PerspectiveCamera` | `../cameras/PerspectiveCamera.js` |
| `Matrix4` | `../math/Matrix4.js` |
| `Vector2` | `../math/Vector2.js` |
| `Vector3` | `../math/Vector3.js` |
| `Vector4` | `../math/Vector4.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_projScreenMatrix` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_lightPositionWorld` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_lookTarget` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `camera` | `Camera` | let/var | `this.camera` | ✗ |
| `shadowMatrix` | `Matrix4` | let/var | `this.matrix` | ✗ |
| `far` | `any` | let/var | `light.distance \|\| camera.far` | ✗ |


---

## Functions

### `PointLightShadow.updateMatrices(light: Light, viewportIndex: number): void`

**JSDoc:**
```typescript
/**
	 * Update the matrices for the camera and shadow, used internally by the renderer.
	 *
	 * @param {Light} light - The light for which the shadow is being rendered.
	 * @param {number} [viewportIndex=0] - The viewport index.
	 */
```

**Parameters:**

- **`light`** `Light`
- **`viewportIndex`** `number`

**Returns:** `void`

**Calls:**

- `camera.updateProjectionMatrix`
- `_lightPositionWorld.setFromMatrixPosition`
- `camera.position.copy`
- `_lookTarget.copy`
- `_lookTarget.add`
- `camera.up.copy`
- `camera.lookAt`
- `camera.updateMatrixWorld`
- `shadowMatrix.makeTranslation`
- `_projScreenMatrix.multiplyMatrices`
- `this._frustum.setFromProjectionMatrix`

<details><summary>Code</summary>

```typescript
updateMatrices( light, viewportIndex = 0 ) {

		const camera = this.camera;
		const shadowMatrix = this.matrix;

		const far = light.distance || camera.far;

		if ( far !== camera.far ) {

			camera.far = far;
			camera.updateProjectionMatrix();

		}

		_lightPositionWorld.setFromMatrixPosition( light.matrixWorld );
		camera.position.copy( _lightPositionWorld );

		_lookTarget.copy( camera.position );
		_lookTarget.add( this._cubeDirections[ viewportIndex ] );
		camera.up.copy( this._cubeUps[ viewportIndex ] );
		camera.lookAt( _lookTarget );
		camera.updateMatrixWorld();

		shadowMatrix.makeTranslation( - _lightPositionWorld.x, - _lightPositionWorld.y, - _lightPositionWorld.z );

		_projScreenMatrix.multiplyMatrices( camera.projectionMatrix, camera.matrixWorldInverse );
		this._frustum.setFromProjectionMatrix( _projScreenMatrix, camera.coordinateSystem, camera.reversedDepth );

	}
```
</details>


---

## Classes

### `PointLightShadow`

<details><summary>Class Code</summary>

```ts
class PointLightShadow extends LightShadow {

	/**
	 * Constructs a new point light shadow.
	 */
	constructor() {

		super( new PerspectiveCamera( 90, 1, 0.5, 500 ) );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isPointLightShadow = true;

		this._frameExtents = new Vector2( 4, 2 );

		this._viewportCount = 6;

		this._viewports = [
			// These viewports map a cube-map onto a 2D texture with the
			// following orientation:
			//
			//  xzXZ
			//   y Y
			//
			// X - Positive x direction
			// x - Negative x direction
			// Y - Positive y direction
			// y - Negative y direction
			// Z - Positive z direction
			// z - Negative z direction

			// positive X
			new Vector4( 2, 1, 1, 1 ),
			// negative X
			new Vector4( 0, 1, 1, 1 ),
			// positive Z
			new Vector4( 3, 1, 1, 1 ),
			// negative Z
			new Vector4( 1, 1, 1, 1 ),
			// positive Y
			new Vector4( 3, 0, 1, 1 ),
			// negative Y
			new Vector4( 1, 0, 1, 1 )
		];

		this._cubeDirections = [
			new Vector3( 1, 0, 0 ), new Vector3( - 1, 0, 0 ), new Vector3( 0, 0, 1 ),
			new Vector3( 0, 0, - 1 ), new Vector3( 0, 1, 0 ), new Vector3( 0, - 1, 0 )
		];

		this._cubeUps = [
			new Vector3( 0, 1, 0 ), new Vector3( 0, 1, 0 ), new Vector3( 0, 1, 0 ),
			new Vector3( 0, 1, 0 ), new Vector3( 0, 0, 1 ),	new Vector3( 0, 0, - 1 )
		];

	}

	/**
	 * Update the matrices for the camera and shadow, used internally by the renderer.
	 *
	 * @param {Light} light - The light for which the shadow is being rendered.
	 * @param {number} [viewportIndex=0] - The viewport index.
	 */
	updateMatrices( light, viewportIndex = 0 ) {

		const camera = this.camera;
		const shadowMatrix = this.matrix;

		const far = light.distance || camera.far;

		if ( far !== camera.far ) {

			camera.far = far;
			camera.updateProjectionMatrix();

		}

		_lightPositionWorld.setFromMatrixPosition( light.matrixWorld );
		camera.position.copy( _lightPositionWorld );

		_lookTarget.copy( camera.position );
		_lookTarget.add( this._cubeDirections[ viewportIndex ] );
		camera.up.copy( this._cubeUps[ viewportIndex ] );
		camera.lookAt( _lookTarget );
		camera.updateMatrixWorld();

		shadowMatrix.makeTranslation( - _lightPositionWorld.x, - _lightPositionWorld.y, - _lightPositionWorld.z );

		_projScreenMatrix.multiplyMatrices( camera.projectionMatrix, camera.matrixWorldInverse );
		this._frustum.setFromProjectionMatrix( _projScreenMatrix, camera.coordinateSystem, camera.reversedDepth );

	}

}
```
</details>

#### Methods

##### `updateMatrices(light: Light, viewportIndex: number): void`

<details><summary>Code</summary>

```ts
updateMatrices( light, viewportIndex = 0 ) {

		const camera = this.camera;
		const shadowMatrix = this.matrix;

		const far = light.distance || camera.far;

		if ( far !== camera.far ) {

			camera.far = far;
			camera.updateProjectionMatrix();

		}

		_lightPositionWorld.setFromMatrixPosition( light.matrixWorld );
		camera.position.copy( _lightPositionWorld );

		_lookTarget.copy( camera.position );
		_lookTarget.add( this._cubeDirections[ viewportIndex ] );
		camera.up.copy( this._cubeUps[ viewportIndex ] );
		camera.lookAt( _lookTarget );
		camera.updateMatrixWorld();

		shadowMatrix.makeTranslation( - _lightPositionWorld.x, - _lightPositionWorld.y, - _lightPositionWorld.z );

		_projScreenMatrix.multiplyMatrices( camera.projectionMatrix, camera.matrixWorldInverse );
		this._frustum.setFromProjectionMatrix( _projScreenMatrix, camera.coordinateSystem, camera.reversedDepth );

	}
```
</details>


---