[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SelectionBox.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 20 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/interactive/SelectionBox.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Frustum` | `three` |
| `Vector3` | `three` |
| `Matrix4` | `three` |
| `Quaternion` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_frustum` | `any` | let/var | `new Frustum()` | ✗ |
| `_center` | `any` | let/var | `new Vector3()` | ✗ |
| `_tmpPoint` | `any` | let/var | `new Vector3()` | ✗ |
| `_vecNear` | `any` | let/var | `new Vector3()` | ✗ |
| `_vecTopLeft` | `any` | let/var | `new Vector3()` | ✗ |
| `_vecTopRight` | `any` | let/var | `new Vector3()` | ✗ |
| `_vecDownRight` | `any` | let/var | `new Vector3()` | ✗ |
| `_vecDownLeft` | `any` | let/var | `new Vector3()` | ✗ |
| `_vecFarTopLeft` | `any` | let/var | `new Vector3()` | ✗ |
| `_vecFarTopRight` | `any` | let/var | `new Vector3()` | ✗ |
| `_vecFarDownRight` | `any` | let/var | `new Vector3()` | ✗ |
| `_vecFarDownLeft` | `any` | let/var | `new Vector3()` | ✗ |
| `_vectemp1` | `any` | let/var | `new Vector3()` | ✗ |
| `_vectemp2` | `any` | let/var | `new Vector3()` | ✗ |
| `_vectemp3` | `any` | let/var | `new Vector3()` | ✗ |
| `_matrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `_quaternion` | `any` | let/var | `new Quaternion()` | ✗ |
| `_scale` | `any` | let/var | `new Vector3()` | ✗ |
| `planes` | `any` | let/var | `_frustum.planes` | ✗ |
| `planes` | `any` | let/var | `_frustum.planes` | ✗ |


---

## Functions

### `SelectionBox.select(startPoint: Vector3, endPoint: Vector3): Object3D[]`

**JSDoc:**
```typescript
/**
	 * This method selects 3D objects in the scene based on the given start
	 * and end point. If no parameters are provided, the method uses the start
	 * and end values of the respective members.
	 *
	 * @param {Vector3} [startPoint] - The start point.
	 * @param {Vector3} [endPoint] - The end point.
	 * @return {Array<Object3D>} The selected 3D objects.
	 */
```

**Parameters:**

- **`startPoint`** `Vector3`
- **`endPoint`** `Vector3`

**Returns:** `Object3D[]`

**Calls:**

- `this._updateFrustum`
- `this._searchChildInFrustum`

<details><summary>Code</summary>

```typescript
select( startPoint, endPoint ) {

		this.startPoint = startPoint || this.startPoint;
		this.endPoint = endPoint || this.endPoint;
		this.collection = [];

		this._updateFrustum( this.startPoint, this.endPoint );
		this._searchChildInFrustum( _frustum, this.scene );

		return this.collection;

	}
```
</details>

### `SelectionBox._updateFrustum(startPoint: any, endPoint: any): void`

**Parameters:**

- **`startPoint`** `any`
- **`endPoint`** `any`

**Returns:** `void`

**Calls:**

- `this.camera.updateProjectionMatrix`
- `this.camera.updateMatrixWorld`
- `_tmpPoint.copy`
- `Math.min`
- `Math.max`
- `_vecNear.setFromMatrixPosition`
- `_vecTopLeft.copy`
- `_vecTopRight.set`
- `_vecDownRight.copy`
- `_vecDownLeft.set`
- `_vecTopLeft.unproject`
- `_vecTopRight.unproject`
- `_vecDownRight.unproject`
- `_vecDownLeft.unproject`
- `_vectemp1.copy( _vecTopLeft ).sub`
- `_vectemp2.copy( _vecTopRight ).sub`
- `_vectemp3.copy( _vecDownRight ).sub`
- `_vectemp1.normalize`
- `_vectemp2.normalize`
- `_vectemp3.normalize`
- `_vectemp1.multiplyScalar`
- `_vectemp2.multiplyScalar`
- `_vectemp3.multiplyScalar`
- `_vectemp1.add`
- `_vectemp2.add`
- `_vectemp3.add`
- `planes[ 0 ].setFromCoplanarPoints`
- `planes[ 1 ].setFromCoplanarPoints`
- `planes[ 2 ].setFromCoplanarPoints`
- `planes[ 3 ].setFromCoplanarPoints`
- `planes[ 4 ].setFromCoplanarPoints`
- `planes[ 5 ].setFromCoplanarPoints`
- `planes[ 5 ].normal.multiplyScalar`
- `_vecTopLeft.set`
- `_vecDownRight.set`
- `_vecFarTopLeft.set`
- `_vecFarTopRight.set`
- `_vecFarDownRight.set`
- `_vecFarDownLeft.set`
- `_vecFarTopLeft.unproject`
- `_vecFarTopRight.unproject`
- `_vecFarDownRight.unproject`
- `_vecFarDownLeft.unproject`
- `console.error`

**Internal Comments:**
```
// Avoid invalid frustum
```

<details><summary>Code</summary>

```typescript
_updateFrustum( startPoint, endPoint ) {

		startPoint = startPoint || this.startPoint;
		endPoint = endPoint || this.endPoint;

		// Avoid invalid frustum

		if ( startPoint.x === endPoint.x ) {

			endPoint.x += Number.EPSILON;

		}

		if ( startPoint.y === endPoint.y ) {

			endPoint.y += Number.EPSILON;

		}

		this.camera.updateProjectionMatrix();
		this.camera.updateMatrixWorld();

		if ( this.camera.isPerspectiveCamera ) {

			_tmpPoint.copy( startPoint );
			_tmpPoint.x = Math.min( startPoint.x, endPoint.x );
			_tmpPoint.y = Math.max( startPoint.y, endPoint.y );
			endPoint.x = Math.max( startPoint.x, endPoint.x );
			endPoint.y = Math.min( startPoint.y, endPoint.y );

			_vecNear.setFromMatrixPosition( this.camera.matrixWorld );
			_vecTopLeft.copy( _tmpPoint );
			_vecTopRight.set( endPoint.x, _tmpPoint.y, 0 );
			_vecDownRight.copy( endPoint );
			_vecDownLeft.set( _tmpPoint.x, endPoint.y, 0 );

			_vecTopLeft.unproject( this.camera );
			_vecTopRight.unproject( this.camera );
			_vecDownRight.unproject( this.camera );
			_vecDownLeft.unproject( this.camera );

			_vectemp1.copy( _vecTopLeft ).sub( _vecNear );
			_vectemp2.copy( _vecTopRight ).sub( _vecNear );
			_vectemp3.copy( _vecDownRight ).sub( _vecNear );
			_vectemp1.normalize();
			_vectemp2.normalize();
			_vectemp3.normalize();

			_vectemp1.multiplyScalar( this.deep );
			_vectemp2.multiplyScalar( this.deep );
			_vectemp3.multiplyScalar( this.deep );
			_vectemp1.add( _vecNear );
			_vectemp2.add( _vecNear );
			_vectemp3.add( _vecNear );

			const planes = _frustum.planes;

			planes[ 0 ].setFromCoplanarPoints( _vecNear, _vecTopLeft, _vecTopRight );
			planes[ 1 ].setFromCoplanarPoints( _vecNear, _vecTopRight, _vecDownRight );
			planes[ 2 ].setFromCoplanarPoints( _vecDownRight, _vecDownLeft, _vecNear );
			planes[ 3 ].setFromCoplanarPoints( _vecDownLeft, _vecTopLeft, _vecNear );
			planes[ 4 ].setFromCoplanarPoints( _vecTopRight, _vecDownRight, _vecDownLeft );
			planes[ 5 ].setFromCoplanarPoints( _vectemp3, _vectemp2, _vectemp1 );
			planes[ 5 ].normal.multiplyScalar( - 1 );

		} else if ( this.camera.isOrthographicCamera ) {

			const left = Math.min( startPoint.x, endPoint.x );
			const top = Math.max( startPoint.y, endPoint.y );
			const right = Math.max( startPoint.x, endPoint.x );
			const down = Math.min( startPoint.y, endPoint.y );

			_vecTopLeft.set( left, top, - 1 );
			_vecTopRight.set( right, top, - 1 );
			_vecDownRight.set( right, down, - 1 );
			_vecDownLeft.set( left, down, - 1 );

			_vecFarTopLeft.set( left, top, 1 );
			_vecFarTopRight.set( right, top, 1 );
			_vecFarDownRight.set( right, down, 1 );
			_vecFarDownLeft.set( left, down, 1 );

			_vecTopLeft.unproject( this.camera );
			_vecTopRight.unproject( this.camera );
			_vecDownRight.unproject( this.camera );
			_vecDownLeft.unproject( this.camera );

			_vecFarTopLeft.unproject( this.camera );
			_vecFarTopRight.unproject( this.camera );
			_vecFarDownRight.unproject( this.camera );
			_vecFarDownLeft.unproject( this.camera );

			const planes = _frustum.planes;

			planes[ 0 ].setFromCoplanarPoints( _vecTopLeft, _vecFarTopLeft, _vecFarTopRight );
			planes[ 1 ].setFromCoplanarPoints( _vecTopRight, _vecFarTopRight, _vecFarDownRight );
			planes[ 2 ].setFromCoplanarPoints( _vecFarDownRight, _vecFarDownLeft, _vecDownLeft );
			planes[ 3 ].setFromCoplanarPoints( _vecFarDownLeft, _vecFarTopLeft, _vecTopLeft );
			planes[ 4 ].setFromCoplanarPoints( _vecTopRight, _vecDownRight, _vecDownLeft );
			planes[ 5 ].setFromCoplanarPoints( _vecFarDownRight, _vecFarTopRight, _vecFarTopLeft );
			planes[ 5 ].normal.multiplyScalar( - 1 );

		} else {

			console.error( 'THREE.SelectionBox: Unsupported camera type.' );

		}

	}
```
</details>

### `SelectionBox._searchChildInFrustum(frustum: any, object: any): void`

**Parameters:**

- **`frustum`** `any`
- **`object`** `any`

**Returns:** `void`

**Calls:**

- `object.getMatrixAt`
- `_matrix.decompose`
- `_center.applyMatrix4`
- `frustum.containsPoint`
- `this.instances[ object.uuid ].push`
- `object.geometry.computeBoundingSphere`
- `_center.copy`
- `this.collection.push`
- `this._searchChildInFrustum`

<details><summary>Code</summary>

```typescript
_searchChildInFrustum( frustum, object ) {

		if ( object.isMesh || object.isLine || object.isPoints ) {

			if ( object.isInstancedMesh ) {

				this.instances[ object.uuid ] = [];

				for ( let instanceId = 0; instanceId < object.count; instanceId ++ ) {

					object.getMatrixAt( instanceId, _matrix );
					_matrix.decompose( _center, _quaternion, _scale );
					_center.applyMatrix4( object.matrixWorld );

					if ( frustum.containsPoint( _center ) ) {

						this.instances[ object.uuid ].push( instanceId );

					}

				}

			} else {

				if ( object.geometry.boundingSphere === null ) object.geometry.computeBoundingSphere();

				_center.copy( object.geometry.boundingSphere.center );

				_center.applyMatrix4( object.matrixWorld );

				if ( frustum.containsPoint( _center ) ) {

					this.collection.push( object );

				}

			}

		}

		if ( object.children.length > 0 ) {

			for ( let x = 0; x < object.children.length; x ++ ) {

				this._searchChildInFrustum( frustum, object.children[ x ] );

			}

		}

	}
```
</details>


---

## Classes

### `SelectionBox`

<details><summary>Class Code</summary>

```ts
class SelectionBox {

	/**
	 * Constructs a new selection box.
	 *
	 * @param {Camera} camera - The camera the scene is rendered with.
	 * @param {Scene} scene - The scene.
	 * @param {number} [deep=Number.MAX_VALUE] - How deep the selection frustum of perspective cameras should extend.
	 */
	constructor( camera, scene, deep = Number.MAX_VALUE ) {

		/**
		 * The camera the scene is rendered with.
		 *
		 * @type {Camera}
		 */
		this.camera = camera;

		/**
		 * The camera the scene is rendered with.
		 *
		 * @type {Scene}
		 */
		this.scene = scene;

		/**
		 * The start point of the selection.
		 *
		 * @type {Vector3}
		 */
		this.startPoint = new Vector3();

		/**
		 * The end point of the selection.
		 *
		 * @type {Vector3}
		 */
		this.endPoint = new Vector3();

		/**
		 * The selected 3D objects.
		 *
		 * @type {Array<Object3D>}
		 */
		this.collection = [];

		/**
		 * The selected instance IDs of instanced meshes.
		 *
		 * @type {Object}
		 */
		this.instances = {};

		/**
		 * How deep the selection frustum of perspective cameras should extend.
		 *
		 * @type {number}
		 * @default Number.MAX_VALUE
		 */
		this.deep = deep;

	}

	/**
	 * This method selects 3D objects in the scene based on the given start
	 * and end point. If no parameters are provided, the method uses the start
	 * and end values of the respective members.
	 *
	 * @param {Vector3} [startPoint] - The start point.
	 * @param {Vector3} [endPoint] - The end point.
	 * @return {Array<Object3D>} The selected 3D objects.
	 */
	select( startPoint, endPoint ) {

		this.startPoint = startPoint || this.startPoint;
		this.endPoint = endPoint || this.endPoint;
		this.collection = [];

		this._updateFrustum( this.startPoint, this.endPoint );
		this._searchChildInFrustum( _frustum, this.scene );

		return this.collection;

	}

	// private

	_updateFrustum( startPoint, endPoint ) {

		startPoint = startPoint || this.startPoint;
		endPoint = endPoint || this.endPoint;

		// Avoid invalid frustum

		if ( startPoint.x === endPoint.x ) {

			endPoint.x += Number.EPSILON;

		}

		if ( startPoint.y === endPoint.y ) {

			endPoint.y += Number.EPSILON;

		}

		this.camera.updateProjectionMatrix();
		this.camera.updateMatrixWorld();

		if ( this.camera.isPerspectiveCamera ) {

			_tmpPoint.copy( startPoint );
			_tmpPoint.x = Math.min( startPoint.x, endPoint.x );
			_tmpPoint.y = Math.max( startPoint.y, endPoint.y );
			endPoint.x = Math.max( startPoint.x, endPoint.x );
			endPoint.y = Math.min( startPoint.y, endPoint.y );

			_vecNear.setFromMatrixPosition( this.camera.matrixWorld );
			_vecTopLeft.copy( _tmpPoint );
			_vecTopRight.set( endPoint.x, _tmpPoint.y, 0 );
			_vecDownRight.copy( endPoint );
			_vecDownLeft.set( _tmpPoint.x, endPoint.y, 0 );

			_vecTopLeft.unproject( this.camera );
			_vecTopRight.unproject( this.camera );
			_vecDownRight.unproject( this.camera );
			_vecDownLeft.unproject( this.camera );

			_vectemp1.copy( _vecTopLeft ).sub( _vecNear );
			_vectemp2.copy( _vecTopRight ).sub( _vecNear );
			_vectemp3.copy( _vecDownRight ).sub( _vecNear );
			_vectemp1.normalize();
			_vectemp2.normalize();
			_vectemp3.normalize();

			_vectemp1.multiplyScalar( this.deep );
			_vectemp2.multiplyScalar( this.deep );
			_vectemp3.multiplyScalar( this.deep );
			_vectemp1.add( _vecNear );
			_vectemp2.add( _vecNear );
			_vectemp3.add( _vecNear );

			const planes = _frustum.planes;

			planes[ 0 ].setFromCoplanarPoints( _vecNear, _vecTopLeft, _vecTopRight );
			planes[ 1 ].setFromCoplanarPoints( _vecNear, _vecTopRight, _vecDownRight );
			planes[ 2 ].setFromCoplanarPoints( _vecDownRight, _vecDownLeft, _vecNear );
			planes[ 3 ].setFromCoplanarPoints( _vecDownLeft, _vecTopLeft, _vecNear );
			planes[ 4 ].setFromCoplanarPoints( _vecTopRight, _vecDownRight, _vecDownLeft );
			planes[ 5 ].setFromCoplanarPoints( _vectemp3, _vectemp2, _vectemp1 );
			planes[ 5 ].normal.multiplyScalar( - 1 );

		} else if ( this.camera.isOrthographicCamera ) {

			const left = Math.min( startPoint.x, endPoint.x );
			const top = Math.max( startPoint.y, endPoint.y );
			const right = Math.max( startPoint.x, endPoint.x );
			const down = Math.min( startPoint.y, endPoint.y );

			_vecTopLeft.set( left, top, - 1 );
			_vecTopRight.set( right, top, - 1 );
			_vecDownRight.set( right, down, - 1 );
			_vecDownLeft.set( left, down, - 1 );

			_vecFarTopLeft.set( left, top, 1 );
			_vecFarTopRight.set( right, top, 1 );
			_vecFarDownRight.set( right, down, 1 );
			_vecFarDownLeft.set( left, down, 1 );

			_vecTopLeft.unproject( this.camera );
			_vecTopRight.unproject( this.camera );
			_vecDownRight.unproject( this.camera );
			_vecDownLeft.unproject( this.camera );

			_vecFarTopLeft.unproject( this.camera );
			_vecFarTopRight.unproject( this.camera );
			_vecFarDownRight.unproject( this.camera );
			_vecFarDownLeft.unproject( this.camera );

			const planes = _frustum.planes;

			planes[ 0 ].setFromCoplanarPoints( _vecTopLeft, _vecFarTopLeft, _vecFarTopRight );
			planes[ 1 ].setFromCoplanarPoints( _vecTopRight, _vecFarTopRight, _vecFarDownRight );
			planes[ 2 ].setFromCoplanarPoints( _vecFarDownRight, _vecFarDownLeft, _vecDownLeft );
			planes[ 3 ].setFromCoplanarPoints( _vecFarDownLeft, _vecFarTopLeft, _vecTopLeft );
			planes[ 4 ].setFromCoplanarPoints( _vecTopRight, _vecDownRight, _vecDownLeft );
			planes[ 5 ].setFromCoplanarPoints( _vecFarDownRight, _vecFarTopRight, _vecFarTopLeft );
			planes[ 5 ].normal.multiplyScalar( - 1 );

		} else {

			console.error( 'THREE.SelectionBox: Unsupported camera type.' );

		}

	}

	_searchChildInFrustum( frustum, object ) {

		if ( object.isMesh || object.isLine || object.isPoints ) {

			if ( object.isInstancedMesh ) {

				this.instances[ object.uuid ] = [];

				for ( let instanceId = 0; instanceId < object.count; instanceId ++ ) {

					object.getMatrixAt( instanceId, _matrix );
					_matrix.decompose( _center, _quaternion, _scale );
					_center.applyMatrix4( object.matrixWorld );

					if ( frustum.containsPoint( _center ) ) {

						this.instances[ object.uuid ].push( instanceId );

					}

				}

			} else {

				if ( object.geometry.boundingSphere === null ) object.geometry.computeBoundingSphere();

				_center.copy( object.geometry.boundingSphere.center );

				_center.applyMatrix4( object.matrixWorld );

				if ( frustum.containsPoint( _center ) ) {

					this.collection.push( object );

				}

			}

		}

		if ( object.children.length > 0 ) {

			for ( let x = 0; x < object.children.length; x ++ ) {

				this._searchChildInFrustum( frustum, object.children[ x ] );

			}

		}

	}

}
```
</details>

#### Methods

##### `select(startPoint: Vector3, endPoint: Vector3): Object3D[]`

<details><summary>Code</summary>

```ts
select( startPoint, endPoint ) {

		this.startPoint = startPoint || this.startPoint;
		this.endPoint = endPoint || this.endPoint;
		this.collection = [];

		this._updateFrustum( this.startPoint, this.endPoint );
		this._searchChildInFrustum( _frustum, this.scene );

		return this.collection;

	}
```
</details>

##### `_updateFrustum(startPoint: any, endPoint: any): void`

<details><summary>Code</summary>

```ts
_updateFrustum( startPoint, endPoint ) {

		startPoint = startPoint || this.startPoint;
		endPoint = endPoint || this.endPoint;

		// Avoid invalid frustum

		if ( startPoint.x === endPoint.x ) {

			endPoint.x += Number.EPSILON;

		}

		if ( startPoint.y === endPoint.y ) {

			endPoint.y += Number.EPSILON;

		}

		this.camera.updateProjectionMatrix();
		this.camera.updateMatrixWorld();

		if ( this.camera.isPerspectiveCamera ) {

			_tmpPoint.copy( startPoint );
			_tmpPoint.x = Math.min( startPoint.x, endPoint.x );
			_tmpPoint.y = Math.max( startPoint.y, endPoint.y );
			endPoint.x = Math.max( startPoint.x, endPoint.x );
			endPoint.y = Math.min( startPoint.y, endPoint.y );

			_vecNear.setFromMatrixPosition( this.camera.matrixWorld );
			_vecTopLeft.copy( _tmpPoint );
			_vecTopRight.set( endPoint.x, _tmpPoint.y, 0 );
			_vecDownRight.copy( endPoint );
			_vecDownLeft.set( _tmpPoint.x, endPoint.y, 0 );

			_vecTopLeft.unproject( this.camera );
			_vecTopRight.unproject( this.camera );
			_vecDownRight.unproject( this.camera );
			_vecDownLeft.unproject( this.camera );

			_vectemp1.copy( _vecTopLeft ).sub( _vecNear );
			_vectemp2.copy( _vecTopRight ).sub( _vecNear );
			_vectemp3.copy( _vecDownRight ).sub( _vecNear );
			_vectemp1.normalize();
			_vectemp2.normalize();
			_vectemp3.normalize();

			_vectemp1.multiplyScalar( this.deep );
			_vectemp2.multiplyScalar( this.deep );
			_vectemp3.multiplyScalar( this.deep );
			_vectemp1.add( _vecNear );
			_vectemp2.add( _vecNear );
			_vectemp3.add( _vecNear );

			const planes = _frustum.planes;

			planes[ 0 ].setFromCoplanarPoints( _vecNear, _vecTopLeft, _vecTopRight );
			planes[ 1 ].setFromCoplanarPoints( _vecNear, _vecTopRight, _vecDownRight );
			planes[ 2 ].setFromCoplanarPoints( _vecDownRight, _vecDownLeft, _vecNear );
			planes[ 3 ].setFromCoplanarPoints( _vecDownLeft, _vecTopLeft, _vecNear );
			planes[ 4 ].setFromCoplanarPoints( _vecTopRight, _vecDownRight, _vecDownLeft );
			planes[ 5 ].setFromCoplanarPoints( _vectemp3, _vectemp2, _vectemp1 );
			planes[ 5 ].normal.multiplyScalar( - 1 );

		} else if ( this.camera.isOrthographicCamera ) {

			const left = Math.min( startPoint.x, endPoint.x );
			const top = Math.max( startPoint.y, endPoint.y );
			const right = Math.max( startPoint.x, endPoint.x );
			const down = Math.min( startPoint.y, endPoint.y );

			_vecTopLeft.set( left, top, - 1 );
			_vecTopRight.set( right, top, - 1 );
			_vecDownRight.set( right, down, - 1 );
			_vecDownLeft.set( left, down, - 1 );

			_vecFarTopLeft.set( left, top, 1 );
			_vecFarTopRight.set( right, top, 1 );
			_vecFarDownRight.set( right, down, 1 );
			_vecFarDownLeft.set( left, down, 1 );

			_vecTopLeft.unproject( this.camera );
			_vecTopRight.unproject( this.camera );
			_vecDownRight.unproject( this.camera );
			_vecDownLeft.unproject( this.camera );

			_vecFarTopLeft.unproject( this.camera );
			_vecFarTopRight.unproject( this.camera );
			_vecFarDownRight.unproject( this.camera );
			_vecFarDownLeft.unproject( this.camera );

			const planes = _frustum.planes;

			planes[ 0 ].setFromCoplanarPoints( _vecTopLeft, _vecFarTopLeft, _vecFarTopRight );
			planes[ 1 ].setFromCoplanarPoints( _vecTopRight, _vecFarTopRight, _vecFarDownRight );
			planes[ 2 ].setFromCoplanarPoints( _vecFarDownRight, _vecFarDownLeft, _vecDownLeft );
			planes[ 3 ].setFromCoplanarPoints( _vecFarDownLeft, _vecFarTopLeft, _vecTopLeft );
			planes[ 4 ].setFromCoplanarPoints( _vecTopRight, _vecDownRight, _vecDownLeft );
			planes[ 5 ].setFromCoplanarPoints( _vecFarDownRight, _vecFarTopRight, _vecFarTopLeft );
			planes[ 5 ].normal.multiplyScalar( - 1 );

		} else {

			console.error( 'THREE.SelectionBox: Unsupported camera type.' );

		}

	}
```
</details>

##### `_searchChildInFrustum(frustum: any, object: any): void`

<details><summary>Code</summary>

```ts
_searchChildInFrustum( frustum, object ) {

		if ( object.isMesh || object.isLine || object.isPoints ) {

			if ( object.isInstancedMesh ) {

				this.instances[ object.uuid ] = [];

				for ( let instanceId = 0; instanceId < object.count; instanceId ++ ) {

					object.getMatrixAt( instanceId, _matrix );
					_matrix.decompose( _center, _quaternion, _scale );
					_center.applyMatrix4( object.matrixWorld );

					if ( frustum.containsPoint( _center ) ) {

						this.instances[ object.uuid ].push( instanceId );

					}

				}

			} else {

				if ( object.geometry.boundingSphere === null ) object.geometry.computeBoundingSphere();

				_center.copy( object.geometry.boundingSphere.center );

				_center.applyMatrix4( object.matrixWorld );

				if ( frustum.containsPoint( _center ) ) {

					this.collection.push( object );

				}

			}

		}

		if ( object.children.length > 0 ) {

			for ( let x = 0; x < object.children.length; x ++ ) {

				this._searchChildInFrustum( frustum, object.children[ x ] );

			}

		}

	}
```
</details>


---