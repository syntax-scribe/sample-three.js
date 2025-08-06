[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TransformControls.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 38 |
| 🧱 Classes | 4 |
| 📦 Imports | 20 |
| 📊 Variables & Constants | 78 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/controls/TransformControls.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BoxGeometry` | `three` |
| `BufferGeometry` | `three` |
| `Controls` | `three` |
| `CylinderGeometry` | `three` |
| `DoubleSide` | `three` |
| `Euler` | `three` |
| `Float32BufferAttribute` | `three` |
| `Line` | `three` |
| `LineBasicMaterial` | `three` |
| `Matrix4` | `three` |
| `Mesh` | `three` |
| `MeshBasicMaterial` | `three` |
| `Object3D` | `three` |
| `OctahedronGeometry` | `three` |
| `PlaneGeometry` | `three` |
| `Quaternion` | `three` |
| `Raycaster` | `three` |
| `SphereGeometry` | `three` |
| `TorusGeometry` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_raycaster` | `any` | let/var | `new Raycaster()` | ✗ |
| `_tempVector` | `any` | let/var | `new Vector3()` | ✗ |
| `_tempVector2` | `any` | let/var | `new Vector3()` | ✗ |
| `_tempQuaternion` | `any` | let/var | `new Quaternion()` | ✗ |
| `_unit` | `{ X: any; Y: any; Z: any; }` | let/var | `{ X: new Vector3( 1, 0, 0 ), Y: new Vector3( 0, 1, 0 ), Z: new Vector3( 0, 0,...` | ✗ |
| `_changeEvent` | `any` | let/var | `{ type: 'change' }` | ✗ |
| `_mouseDownEvent` | `any` | let/var | `{ type: 'mouseDown', mode: null }` | ✗ |
| `_mouseUpEvent` | `any` | let/var | `{ type: 'mouseUp', mode: null }` | ✗ |
| `_objectChangeEvent` | `any` | let/var | `{ type: 'objectChange' }` | ✗ |
| `root` | `TransformControlsRoot` | let/var | `new TransformControlsRoot( this )` | ✗ |
| `gizmo` | `TransformControlsGizmo` | let/var | `new TransformControlsGizmo()` | ✗ |
| `plane` | `TransformControlsPlane` | let/var | `new TransformControlsPlane()` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `propValue` | `any` | let/var | `defaultValue` | ✗ |
| `worldPosition` | `any` | let/var | `new Vector3()` | ✗ |
| `worldPositionStart` | `any` | let/var | `new Vector3()` | ✗ |
| `worldQuaternion` | `any` | let/var | `new Quaternion()` | ✗ |
| `worldQuaternionStart` | `any` | let/var | `new Quaternion()` | ✗ |
| `cameraPosition` | `any` | let/var | `new Vector3()` | ✗ |
| `cameraQuaternion` | `any` | let/var | `new Quaternion()` | ✗ |
| `pointStart` | `any` | let/var | `new Vector3()` | ✗ |
| `pointEnd` | `any` | let/var | `new Vector3()` | ✗ |
| `rotationAxis` | `any` | let/var | `new Vector3()` | ✗ |
| `rotationAngle` | `0` | let/var | `0` | ✗ |
| `eye` | `any` | let/var | `new Vector3()` | ✗ |
| `axis` | `any` | let/var | `this.axis` | ✗ |
| `mode` | `"translate" \| "scale" \| "rotate"` | let/var | `this.mode` | ✗ |
| `object` | `any` | let/var | `this.object` | ✗ |
| `space` | `"local" \| "world"` | let/var | `this.space` | ✗ |
| `d` | `number` | let/var | `this.pointEnd.length() / this.pointStart.length()` | ✗ |
| `ROTATION_SPEED` | `number` | let/var | `20 / this.worldPosition.distanceTo( _tempVector.setFromMatrixPosition( this.c...` | ✗ |
| `_inPlaneRotation` | `boolean` | let/var | `false` | ✗ |
| `materialLib` | `{ xAxis: any; yAxis: any; zAxis: any;...` | let/var | `this._gizmo.materialLib` | ✗ |
| `_tempEuler` | `any` | let/var | `new Euler()` | ✗ |
| `_alignVector` | `any` | let/var | `new Vector3( 0, 1, 0 )` | ✗ |
| `_zeroVector` | `any` | let/var | `new Vector3( 0, 0, 0 )` | ✗ |
| `_lookAtMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `_tempQuaternion2` | `any` | let/var | `new Quaternion()` | ✗ |
| `_identityQuaternion` | `any` | let/var | `new Quaternion()` | ✗ |
| `_dirVector` | `any` | let/var | `new Vector3()` | ✗ |
| `_tempMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `_unitX` | `any` | let/var | `new Vector3( 1, 0, 0 )` | ✗ |
| `_unitY` | `any` | let/var | `new Vector3( 0, 1, 0 )` | ✗ |
| `_unitZ` | `any` | let/var | `new Vector3( 0, 0, 1 )` | ✗ |
| `_v1` | `any` | let/var | `new Vector3()` | ✗ |
| `_v2` | `any` | let/var | `new Vector3()` | ✗ |
| `_v3` | `any` | let/var | `new Vector3()` | ✗ |
| `controls` | `any` | let/var | `this.controls` | ✗ |
| `gizmoMaterial` | `any` | let/var | `new MeshBasicMaterial( { depthTest: false, depthWrite: false, fog: false, ton...` | ✗ |
| `gizmoLineMaterial` | `any` | let/var | `new LineBasicMaterial( { depthTest: false, depthWrite: false, fog: false, ton...` | ✗ |
| `arrowGeometry` | `any` | let/var | `new CylinderGeometry( 0, 0.04, 0.1, 12 )` | ✗ |
| `scaleHandleGeometry` | `any` | let/var | `new BoxGeometry( 0.08, 0.08, 0.08 )` | ✗ |
| `lineGeometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `lineGeometry2` | `any` | let/var | `new CylinderGeometry( 0.0075, 0.0075, 0.5, 3 )` | ✗ |
| `geometry` | `any` | let/var | `new TorusGeometry( radius, 0.0075, 3, 64, arc * Math.PI * 2 )` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `gizmoTranslate` | `{ X: any[][]; Y: any[][]; Z: any[][];...` | let/var | `{ X: [ [ new Mesh( arrowGeometry, matRed ), [ 0.5, 0, 0 ], [ 0, 0, - Math.PI ...` | ✗ |
| `pickerTranslate` | `{ X: any[][]; Y: any[][]; Z: any[][];...` | let/var | `{ X: [ [ new Mesh( new CylinderGeometry( 0.2, 0, 0.6, 4 ), matInvisible ), [ ...` | ✗ |
| `helperTranslate` | `{ START: any[][]; END: any[][]; DELTA...` | let/var | `{ START: [ [ new Mesh( new OctahedronGeometry( 0.01, 2 ), matHelper ), null, ...` | ✗ |
| `gizmoRotate` | `{ XYZE: any[][]; X: any[][]; Y: any[]...` | let/var | `{ XYZE: [ [ new Mesh( CircleGeometry( 0.5, 1 ), matGray ), null, [ 0, Math.PI...` | ✗ |
| `helperRotate` | `{ AXIS: any[][]; }` | let/var | `{ AXIS: [ [ new Line( lineGeometry, matHelper ), [ - 1e3, 0, 0 ], null, [ 1e6...` | ✗ |
| `pickerRotate` | `{ XYZE: any[][]; X: any[][]; Y: any[]...` | let/var | `{ XYZE: [ [ new Mesh( new SphereGeometry( 0.25, 10, 8 ), matInvisible ) ] ], ...` | ✗ |
| `gizmoScale` | `{ X: any[][]; Y: any[][]; Z: any[][];...` | let/var | `{ X: [ [ new Mesh( scaleHandleGeometry, matRed ), [ 0.5, 0, 0 ], [ 0, 0, - Ma...` | ✗ |
| `pickerScale` | `{ X: any[][]; Y: any[][]; Z: any[][];...` | let/var | `{ X: [ [ new Mesh( new CylinderGeometry( 0.2, 0, 0.6, 4 ), matInvisible ), [ ...` | ✗ |
| `helperScale` | `{ X: any[][]; Y: any[][]; Z: any[][]; }` | let/var | `{ X: [ [ new Line( lineGeometry, matHelper ), [ - 1e3, 0, 0 ], null, [ 1e6, 1...` | ✗ |
| `gizmo` | `any` | let/var | `new Object3D()` | ✗ |
| `position` | `any` | let/var | `gizmoMap[ name ][ i ][ 1 ]` | ✗ |
| `rotation` | `any` | let/var | `gizmoMap[ name ][ i ][ 2 ]` | ✗ |
| `scale` | `any` | let/var | `gizmoMap[ name ][ i ][ 3 ]` | ✗ |
| `tag` | `any` | let/var | `gizmoMap[ name ][ i ][ 4 ]` | ✗ |
| `space` | `any` | let/var | `( this.mode === 'scale' ) ? 'local' : this.space` | ✗ |
| `quaternion` | `any` | let/var | `( space === 'local' ) ? this.worldQuaternion : _identityQuaternion` | ✗ |
| `handles` | `any[]` | let/var | `[]` | ✗ |
| `handle` | `any` | let/var | `handles[ i ]` | ✗ |
| `factor` | `any` | let/var | `*not shown*` | ✗ |
| `AXIS_HIDE_THRESHOLD` | `0.99` | let/var | `0.99` | ✗ |
| `PLANE_HIDE_THRESHOLD` | `0.2` | let/var | `0.2` | ✗ |
| `space` | `any` | let/var | `this.space` | ✗ |


---

## Functions

### `TransformControls.connect(element: any): void`

**Parameters:**

- **`element`** `any`

**Returns:** `void`

**Calls:**

- `super.connect`
- `this.domElement.addEventListener`

<details><summary>Code</summary>

```typescript
connect( element ) {

		super.connect( element );

		this.domElement.addEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.addEventListener( 'pointermove', this._onPointerHover );
		this.domElement.addEventListener( 'pointerup', this._onPointerUp );

		this.domElement.style.touchAction = 'none'; // disable touch scroll

	}
```
</details>

### `TransformControls.disconnect(): void`

**Returns:** `void`

**Calls:**

- `this.domElement.removeEventListener`

<details><summary>Code</summary>

```typescript
disconnect() {

		this.domElement.removeEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.removeEventListener( 'pointermove', this._onPointerHover );
		this.domElement.removeEventListener( 'pointermove', this._onPointerMove );
		this.domElement.removeEventListener( 'pointerup', this._onPointerUp );

		this.domElement.style.touchAction = 'auto';

	}
```
</details>

### `TransformControls.getHelper(): TransformControlsRoot`

**JSDoc:**
```typescript
/**
	 * Returns the visual representation of the controls. Add the helper to your scene to
	 * visually transform the attached  3D object.
	 *
	 * @return {TransformControlsRoot} The helper.
	 */
```

**Returns:** `TransformControlsRoot`

<details><summary>Code</summary>

```typescript
getHelper() {

		return this._root;

	}
```
</details>

### `TransformControls.pointerHover(pointer: any): void`

**Parameters:**

- **`pointer`** `any`

**Returns:** `void`

**Calls:**

- `_raycaster.setFromCamera`
- `intersectObjectWithRay`

<details><summary>Code</summary>

```typescript
pointerHover( pointer ) {

		if ( this.object === undefined || this.dragging === true ) return;

		if ( pointer !== null ) _raycaster.setFromCamera( pointer, this.camera );

		const intersect = intersectObjectWithRay( this._gizmo.picker[ this.mode ], _raycaster );

		if ( intersect ) {

			this.axis = intersect.object.name;

		} else {

			this.axis = null;

		}

	}
```
</details>

### `TransformControls.pointerDown(pointer: any): void`

**Parameters:**

- **`pointer`** `any`

**Returns:** `void`

**Calls:**

- `_raycaster.setFromCamera`
- `intersectObjectWithRay`
- `this.object.updateMatrixWorld`
- `this.object.parent.updateMatrixWorld`
- `this._positionStart.copy`
- `this._quaternionStart.copy`
- `this._scaleStart.copy`
- `this.object.matrixWorld.decompose`
- `this.pointStart.copy( planeIntersect.point ).sub`
- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
pointerDown( pointer ) {

		if ( this.object === undefined || this.dragging === true || ( pointer != null && pointer.button !== 0 ) ) return;

		if ( this.axis !== null ) {

			if ( pointer !== null ) _raycaster.setFromCamera( pointer, this.camera );

			const planeIntersect = intersectObjectWithRay( this._plane, _raycaster, true );

			if ( planeIntersect ) {

				this.object.updateMatrixWorld();
				this.object.parent.updateMatrixWorld();

				this._positionStart.copy( this.object.position );
				this._quaternionStart.copy( this.object.quaternion );
				this._scaleStart.copy( this.object.scale );

				this.object.matrixWorld.decompose( this.worldPositionStart, this.worldQuaternionStart, this._worldScaleStart );

				this.pointStart.copy( planeIntersect.point ).sub( this.worldPositionStart );

			}

			this.dragging = true;
			_mouseDownEvent.mode = this.mode;
			this.dispatchEvent( _mouseDownEvent );

		}

	}
```
</details>

### `TransformControls.pointerMove(pointer: any): void`

**Parameters:**

- **`pointer`** `any`

**Returns:** `void`

**Calls:**

- `_raycaster.setFromCamera`
- `intersectObjectWithRay`
- `this.pointEnd.copy( planeIntersect.point ).sub`
- `this._offset.copy( this.pointEnd ).sub`
- `this._offset.applyQuaternion`
- `axis.indexOf`
- `this._offset.applyQuaternion( this._quaternionStart ).divide`
- `this._offset.applyQuaternion( this._parentQuaternionInv ).divide`
- `object.position.copy( this._offset ).add`
- `object.position.applyQuaternion`
- `_tempQuaternion.copy( this._quaternionStart ).invert`
- `axis.search`
- `Math.round`
- `object.position.add`
- `_tempVector.setFromMatrixPosition`
- `object.position.sub`
- `Math.max`
- `Math.min`
- `this.pointEnd.length`
- `this.pointStart.length`
- `this.pointEnd.dot`
- `_tempVector2.set`
- `_tempVector.copy`
- `_tempVector2.copy`
- `_tempVector.applyQuaternion`
- `_tempVector2.applyQuaternion`
- `_tempVector2.divide`
- `object.scale.copy( this._scaleStart ).multiply`
- `this.worldPosition.distanceTo`
- `this.rotationAxis.copy( this._offset ).cross( this.eye ).normalize`
- `this._offset.dot`
- `_tempVector.copy( this.rotationAxis ).cross`
- `this.rotationAxis.copy`
- `_tempVector.cross`
- `_tempVector.length`
- `_tempVector.normalize`
- `this.pointEnd.angleTo`
- `this._startNorm.copy( this.pointStart ).normalize`
- `this._endNorm.copy( this.pointEnd ).normalize`
- `this._endNorm.cross( this._startNorm ).dot`
- `object.quaternion.copy`
- `object.quaternion.multiply( _tempQuaternion.setFromAxisAngle( this.rotationAxis, this.rotationAngle ) ).normalize`
- `this.rotationAxis.applyQuaternion`
- `_tempQuaternion.setFromAxisAngle`
- `object.quaternion.multiply( this._quaternionStart ).normalize`
- `this.dispatchEvent`

**Internal Comments:**
```
// Apply translate (x7)
// Apply translation snap
// Apply scale (x7)
// When _tempVector is 0 after cross with this.eye the vectors are parallel and should use in-plane rotation logic.
// Apply rotation snap
// Apply rotate
```

<details><summary>Code</summary>

```typescript
pointerMove( pointer ) {

		const axis = this.axis;
		const mode = this.mode;
		const object = this.object;
		let space = this.space;

		if ( mode === 'scale' ) {

			space = 'local';

		} else if ( axis === 'E' || axis === 'XYZE' || axis === 'XYZ' ) {

			space = 'world';

		}

		if ( object === undefined || axis === null || this.dragging === false || ( pointer !== null && pointer.button !== - 1 ) ) return;

		if ( pointer !== null ) _raycaster.setFromCamera( pointer, this.camera );

		const planeIntersect = intersectObjectWithRay( this._plane, _raycaster, true );

		if ( ! planeIntersect ) return;

		this.pointEnd.copy( planeIntersect.point ).sub( this.worldPositionStart );

		if ( mode === 'translate' ) {

			// Apply translate

			this._offset.copy( this.pointEnd ).sub( this.pointStart );

			if ( space === 'local' && axis !== 'XYZ' ) {

				this._offset.applyQuaternion( this._worldQuaternionInv );

			}

			if ( axis.indexOf( 'X' ) === - 1 ) this._offset.x = 0;
			if ( axis.indexOf( 'Y' ) === - 1 ) this._offset.y = 0;
			if ( axis.indexOf( 'Z' ) === - 1 ) this._offset.z = 0;

			if ( space === 'local' && axis !== 'XYZ' ) {

				this._offset.applyQuaternion( this._quaternionStart ).divide( this._parentScale );

			} else {

				this._offset.applyQuaternion( this._parentQuaternionInv ).divide( this._parentScale );

			}

			object.position.copy( this._offset ).add( this._positionStart );

			// Apply translation snap

			if ( this.translationSnap ) {

				if ( space === 'local' ) {

					object.position.applyQuaternion( _tempQuaternion.copy( this._quaternionStart ).invert() );

					if ( axis.search( 'X' ) !== - 1 ) {

						object.position.x = Math.round( object.position.x / this.translationSnap ) * this.translationSnap;

					}

					if ( axis.search( 'Y' ) !== - 1 ) {

						object.position.y = Math.round( object.position.y / this.translationSnap ) * this.translationSnap;

					}

					if ( axis.search( 'Z' ) !== - 1 ) {

						object.position.z = Math.round( object.position.z / this.translationSnap ) * this.translationSnap;

					}

					object.position.applyQuaternion( this._quaternionStart );

				}

				if ( space === 'world' ) {

					if ( object.parent ) {

						object.position.add( _tempVector.setFromMatrixPosition( object.parent.matrixWorld ) );

					}

					if ( axis.search( 'X' ) !== - 1 ) {

						object.position.x = Math.round( object.position.x / this.translationSnap ) * this.translationSnap;

					}

					if ( axis.search( 'Y' ) !== - 1 ) {

						object.position.y = Math.round( object.position.y / this.translationSnap ) * this.translationSnap;

					}

					if ( axis.search( 'Z' ) !== - 1 ) {

						object.position.z = Math.round( object.position.z / this.translationSnap ) * this.translationSnap;

					}

					if ( object.parent ) {

						object.position.sub( _tempVector.setFromMatrixPosition( object.parent.matrixWorld ) );

					}

				}

			}

			object.position.x = Math.max( this.minX, Math.min( this.maxX, object.position.x ) );
			object.position.y = Math.max( this.minY, Math.min( this.maxY, object.position.y ) );
			object.position.z = Math.max( this.minZ, Math.min( this.maxZ, object.position.z ) );

		} else if ( mode === 'scale' ) {

			if ( axis.search( 'XYZ' ) !== - 1 ) {

				let d = this.pointEnd.length() / this.pointStart.length();

				if ( this.pointEnd.dot( this.pointStart ) < 0 ) d *= - 1;

				_tempVector2.set( d, d, d );

			} else {

				_tempVector.copy( this.pointStart );
				_tempVector2.copy( this.pointEnd );

				_tempVector.applyQuaternion( this._worldQuaternionInv );
				_tempVector2.applyQuaternion( this._worldQuaternionInv );

				_tempVector2.divide( _tempVector );

				if ( axis.search( 'X' ) === - 1 ) {

					_tempVector2.x = 1;

				}

				if ( axis.search( 'Y' ) === - 1 ) {

					_tempVector2.y = 1;

				}

				if ( axis.search( 'Z' ) === - 1 ) {

					_tempVector2.z = 1;

				}

			}

			// Apply scale

			object.scale.copy( this._scaleStart ).multiply( _tempVector2 );

			if ( this.scaleSnap ) {

				if ( axis.search( 'X' ) !== - 1 ) {

					object.scale.x = Math.round( object.scale.x / this.scaleSnap ) * this.scaleSnap || this.scaleSnap;

				}

				if ( axis.search( 'Y' ) !== - 1 ) {

					object.scale.y = Math.round( object.scale.y / this.scaleSnap ) * this.scaleSnap || this.scaleSnap;

				}

				if ( axis.search( 'Z' ) !== - 1 ) {

					object.scale.z = Math.round( object.scale.z / this.scaleSnap ) * this.scaleSnap || this.scaleSnap;

				}

			}

		} else if ( mode === 'rotate' ) {

			this._offset.copy( this.pointEnd ).sub( this.pointStart );

			const ROTATION_SPEED = 20 / this.worldPosition.distanceTo( _tempVector.setFromMatrixPosition( this.camera.matrixWorld ) );

			let _inPlaneRotation = false;

			if ( axis === 'XYZE' ) {

				this.rotationAxis.copy( this._offset ).cross( this.eye ).normalize();
				this.rotationAngle = this._offset.dot( _tempVector.copy( this.rotationAxis ).cross( this.eye ) ) * ROTATION_SPEED;

			} else if ( axis === 'X' || axis === 'Y' || axis === 'Z' ) {

				this.rotationAxis.copy( _unit[ axis ] );

				_tempVector.copy( _unit[ axis ] );

				if ( space === 'local' ) {

					_tempVector.applyQuaternion( this.worldQuaternion );

				}

				_tempVector.cross( this.eye );

				// When _tempVector is 0 after cross with this.eye the vectors are parallel and should use in-plane rotation logic.
				if ( _tempVector.length() === 0 ) {

					_inPlaneRotation = true;

				} else {

					this.rotationAngle = this._offset.dot( _tempVector.normalize() ) * ROTATION_SPEED;

				}


			}

			if ( axis === 'E' || _inPlaneRotation ) {

				this.rotationAxis.copy( this.eye );
				this.rotationAngle = this.pointEnd.angleTo( this.pointStart );

				this._startNorm.copy( this.pointStart ).normalize();
				this._endNorm.copy( this.pointEnd ).normalize();

				this.rotationAngle *= ( this._endNorm.cross( this._startNorm ).dot( this.eye ) < 0 ? 1 : - 1 );

			}

			// Apply rotation snap

			if ( this.rotationSnap ) this.rotationAngle = Math.round( this.rotationAngle / this.rotationSnap ) * this.rotationSnap;

			// Apply rotate
			if ( space === 'local' && axis !== 'E' && axis !== 'XYZE' ) {

				object.quaternion.copy( this._quaternionStart );
				object.quaternion.multiply( _tempQuaternion.setFromAxisAngle( this.rotationAxis, this.rotationAngle ) ).normalize();

			} else {

				this.rotationAxis.applyQuaternion( this._parentQuaternionInv );
				object.quaternion.copy( _tempQuaternion.setFromAxisAngle( this.rotationAxis, this.rotationAngle ) );
				object.quaternion.multiply( this._quaternionStart ).normalize();

			}

		}

		this.dispatchEvent( _changeEvent );
		this.dispatchEvent( _objectChangeEvent );

	}
```
</details>

### `TransformControls.pointerUp(pointer: any): void`

**Parameters:**

- **`pointer`** `any`

**Returns:** `void`

**Calls:**

- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
pointerUp( pointer ) {

		if ( pointer !== null && pointer.button !== 0 ) return;

		if ( this.dragging && ( this.axis !== null ) ) {

			_mouseUpEvent.mode = this.mode;
			this.dispatchEvent( _mouseUpEvent );

		}

		this.dragging = false;
		this.axis = null;

	}
```
</details>

### `TransformControls.dispose(): void`

**Returns:** `void`

**Calls:**

- `this.disconnect`
- `this._root.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.disconnect();

		this._root.dispose();

	}
```
</details>

### `TransformControls.attach(object: Object3D): TransformControls`

**JSDoc:**
```typescript
/**
	 * Sets the 3D object that should be transformed and ensures the controls UI is visible.
	 *
	 * @param {Object3D} object -  The 3D object that should be transformed.
	 * @return {TransformControls} A reference to this controls.
	 */
```

**Parameters:**

- **`object`** `Object3D`

**Returns:** `TransformControls`

<details><summary>Code</summary>

```typescript
attach( object ) {

		this.object = object;
		this._root.visible = true;

		return this;

	}
```
</details>

### `TransformControls.detach(): TransformControls`

**JSDoc:**
```typescript
/**
	 * Removes the current 3D object from the controls and makes the helper UI invisible.
	 *
	 * @return {TransformControls} A reference to this controls.
	 */
```

**Returns:** `TransformControls`

<details><summary>Code</summary>

```typescript
detach() {

		this.object = undefined;
		this.axis = null;

		this._root.visible = false;

		return this;

	}
```
</details>

### `TransformControls.reset(): void`

**JSDoc:**
```typescript
/**
	 * Resets the object's position, rotation and scale to when the current transform began.
	 */
```

**Returns:** `void`

**Calls:**

- `this.object.position.copy`
- `this.object.quaternion.copy`
- `this.object.scale.copy`
- `this.dispatchEvent`
- `this.pointStart.copy`

<details><summary>Code</summary>

```typescript
reset() {

		if ( ! this.enabled ) return;

		if ( this.dragging ) {

			this.object.position.copy( this._positionStart );
			this.object.quaternion.copy( this._quaternionStart );
			this.object.scale.copy( this._scaleStart );

			this.dispatchEvent( _changeEvent );
			this.dispatchEvent( _objectChangeEvent );

			this.pointStart.copy( this.pointEnd );

		}

	}
```
</details>

### `TransformControls.getRaycaster(): Raycaster`

**JSDoc:**
```typescript
/**
	 * Returns the raycaster that is used for user interaction. This object is shared between all
	 * instances of `TransformControls`.
	 *
	 * @returns {Raycaster} The internal raycaster.
	 */
```

**Returns:** `Raycaster`

<details><summary>Code</summary>

```typescript
getRaycaster() {

		return _raycaster;

	}
```
</details>

### `TransformControls.getMode(): "translate" | "scale" | "rotate"`

**JSDoc:**
```typescript
/**
	 * Returns the transformation mode.
	 *
	 * @returns {'translate'|'rotate'|'scale'} The transformation mode.
	 */
```

**Returns:** `"translate" | "scale" | "rotate"`

<details><summary>Code</summary>

```typescript
getMode() {

		return this.mode;

	}
```
</details>

### `TransformControls.setMode(mode: "translate" | "scale" | "rotate"): void`

**JSDoc:**
```typescript
/**
	 * Sets the given transformation mode.
	 *
	 * @param {'translate'|'rotate'|'scale'} mode - The transformation mode to set.
	 */
```

**Parameters:**

- **`mode`** `"translate" | "scale" | "rotate"`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setMode( mode ) {

		this.mode = mode;

	}
```
</details>

### `TransformControls.setTranslationSnap(translationSnap: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the translation snap.
	 *
	 * @param {?number} translationSnap - The translation snap to set.
	 */
```

**Parameters:**

- **`translationSnap`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setTranslationSnap( translationSnap ) {

		this.translationSnap = translationSnap;

	}
```
</details>

### `TransformControls.setRotationSnap(rotationSnap: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the rotation snap.
	 *
	 * @param {?number} rotationSnap - The rotation snap to set.
	 */
```

**Parameters:**

- **`rotationSnap`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setRotationSnap( rotationSnap ) {

		this.rotationSnap = rotationSnap;

	}
```
</details>

### `TransformControls.setScaleSnap(scaleSnap: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the scale snap.
	 *
	 * @param {?number} scaleSnap - The scale snap to set.
	 */
```

**Parameters:**

- **`scaleSnap`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setScaleSnap( scaleSnap ) {

		this.scaleSnap = scaleSnap;

	}
```
</details>

### `TransformControls.setSize(size: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the size of the helper UI.
	 *
	 * @param {number} size - The size to set.
	 */
```

**Parameters:**

- **`size`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setSize( size ) {

		this.size = size;

	}
```
</details>

### `TransformControls.setSpace(space: "local" | "world"): void`

**JSDoc:**
```typescript
/**
	 * Sets the coordinate space in which transformations are applied.
	 *
	 * @param {'world'|'local'} space - The space to set.
	 */
```

**Parameters:**

- **`space`** `"local" | "world"`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setSpace( space ) {

		this.space = space;

	}
```
</details>

### `TransformControls.setColors(xAxis: any, yAxis: any, zAxis: any, active: any): void`

**JSDoc:**
```typescript
/**
	 * Sets the colors of the control's gizmo.
	 *
	 * @param {number|Color|string} xAxis - The x-axis color.
	 * @param {number|Color|string} yAxis - The y-axis color.
	 * @param {number|Color|string} zAxis - The z-axis color.
	 * @param {number|Color|string} active - The color for active elements.
	 */
```

**Parameters:**

- **`xAxis`** `any`
- **`yAxis`** `any`
- **`zAxis`** `any`
- **`active`** `any`

**Returns:** `void`

**Calls:**

- `materialLib.xAxis.color.set`
- `materialLib.yAxis.color.set`
- `materialLib.zAxis.color.set`
- `materialLib.active.color.set`
- `materialLib.xAxisTransparent.color.set`
- `materialLib.yAxisTransparent.color.set`
- `materialLib.zAxisTransparent.color.set`
- `materialLib.activeTransparent.color.set`
- `materialLib.xAxis._color.set`
- `materialLib.yAxis._color.set`
- `materialLib.zAxis._color.set`
- `materialLib.active._color.set`
- `materialLib.xAxisTransparent._color.set`
- `materialLib.yAxisTransparent._color.set`
- `materialLib.zAxisTransparent._color.set`
- `materialLib.activeTransparent._color.set`

**Internal Comments:**
```
// update color caches
```

<details><summary>Code</summary>

```typescript
setColors( xAxis, yAxis, zAxis, active ) {

		const materialLib = this._gizmo.materialLib;

		materialLib.xAxis.color.set( xAxis );
		materialLib.yAxis.color.set( yAxis );
		materialLib.zAxis.color.set( zAxis );
		materialLib.active.color.set( active );
		materialLib.xAxisTransparent.color.set( xAxis );
		materialLib.yAxisTransparent.color.set( yAxis );
		materialLib.zAxisTransparent.color.set( zAxis );
		materialLib.activeTransparent.color.set( active );

		// update color caches

		if ( materialLib.xAxis._color ) materialLib.xAxis._color.set( xAxis );
		if ( materialLib.yAxis._color ) materialLib.yAxis._color.set( yAxis );
		if ( materialLib.zAxis._color ) materialLib.zAxis._color.set( zAxis );
		if ( materialLib.active._color ) materialLib.active._color.set( active );
		if ( materialLib.xAxisTransparent._color ) materialLib.xAxisTransparent._color.set( xAxis );
		if ( materialLib.yAxisTransparent._color ) materialLib.yAxisTransparent._color.set( yAxis );
		if ( materialLib.zAxisTransparent._color ) materialLib.zAxisTransparent._color.set( zAxis );
		if ( materialLib.activeTransparent._color ) materialLib.activeTransparent._color.set( active );

	}
```
</details>

### `defineProperty(propName: any, defaultValue: any): void`

**Parameters:**

- **`propName`** `any`
- **`defaultValue`** `any`

**Returns:** `void`

**Calls:**

- `Object.defineProperty`
- `scope.dispatchEvent`

<details><summary>Code</summary>

```typescript
function defineProperty( propName, defaultValue ) {

			let propValue = defaultValue;

			Object.defineProperty( scope, propName, {

				get: function () {

					return propValue !== undefined ? propValue : defaultValue;

				},

				set: function ( value ) {

					if ( propValue !== value ) {

						propValue = value;
						plane[ propName ] = value;
						gizmo[ propName ] = value;

						scope.dispatchEvent( { type: propName + '-changed', value: value } );
						scope.dispatchEvent( _changeEvent );

					}

				}

			} );

			scope[ propName ] = defaultValue;
			plane[ propName ] = defaultValue;
			gizmo[ propName ] = defaultValue;

		}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					return propValue !== undefined ? propValue : defaultValue;

				}
```
</details>

### `set(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

**Calls:**

- `scope.dispatchEvent`

<details><summary>Code</summary>

```typescript
function ( value ) {

					if ( propValue !== value ) {

						propValue = value;
						plane[ propName ] = value;
						gizmo[ propName ] = value;

						scope.dispatchEvent( { type: propName + '-changed', value: value } );
						scope.dispatchEvent( _changeEvent );

					}

				}
```
</details>

### `get(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function () {

					return propValue !== undefined ? propValue : defaultValue;

				}
```
</details>

### `set(value: any): void`

**Parameters:**

- **`value`** `any`

**Returns:** `void`

**Calls:**

- `scope.dispatchEvent`

<details><summary>Code</summary>

```typescript
function ( value ) {

					if ( propValue !== value ) {

						propValue = value;
						plane[ propName ] = value;
						gizmo[ propName ] = value;

						scope.dispatchEvent( { type: propName + '-changed', value: value } );
						scope.dispatchEvent( _changeEvent );

					}

				}
```
</details>

### `getPointer(event: any): { x: number; y: number; button: any; }`

**Parameters:**

- **`event`** `any`

**Returns:** `{ x: number; y: number; button: any; }`

**Calls:**

- `this.domElement.getBoundingClientRect`

<details><summary>Code</summary>

```typescript
function getPointer( event ) {

	if ( this.domElement.ownerDocument.pointerLockElement ) {

		return {
			x: 0,
			y: 0,
			button: event.button
		};

	} else {

		const rect = this.domElement.getBoundingClientRect();

		return {
			x: ( event.clientX - rect.left ) / rect.width * 2 - 1,
			y: - ( event.clientY - rect.top ) / rect.height * 2 + 1,
			button: event.button
		};

	}

}
```
</details>

### `onPointerHover(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `this.pointerHover`
- `this._getPointer`

<details><summary>Code</summary>

```typescript
function onPointerHover( event ) {

	if ( ! this.enabled ) return;

	switch ( event.pointerType ) {

		case 'mouse':
		case 'pen':
			this.pointerHover( this._getPointer( event ) );
			break;

	}

}
```
</details>

### `onPointerDown(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `this.domElement.setPointerCapture`
- `this.domElement.addEventListener`
- `this.pointerHover`
- `this._getPointer`
- `this.pointerDown`

<details><summary>Code</summary>

```typescript
function onPointerDown( event ) {

	if ( ! this.enabled ) return;

	if ( ! document.pointerLockElement ) {

		this.domElement.setPointerCapture( event.pointerId );

	}

	this.domElement.addEventListener( 'pointermove', this._onPointerMove );

	this.pointerHover( this._getPointer( event ) );
	this.pointerDown( this._getPointer( event ) );

}
```
</details>

### `onPointerMove(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `this.pointerMove`
- `this._getPointer`

<details><summary>Code</summary>

```typescript
function onPointerMove( event ) {

	if ( ! this.enabled ) return;

	this.pointerMove( this._getPointer( event ) );

}
```
</details>

### `onPointerUp(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `this.domElement.releasePointerCapture`
- `this.domElement.removeEventListener`
- `this.pointerUp`
- `this._getPointer`

<details><summary>Code</summary>

```typescript
function onPointerUp( event ) {

	if ( ! this.enabled ) return;

	this.domElement.releasePointerCapture( event.pointerId );

	this.domElement.removeEventListener( 'pointermove', this._onPointerMove );

	this.pointerUp( this._getPointer( event ) );

}
```
</details>

### `intersectObjectWithRay(object: any, raycaster: any, includeInvisible: any): any`

**Parameters:**

- **`object`** `any`
- **`raycaster`** `any`
- **`includeInvisible`** `any`

**Returns:** `any`

**Calls:**

- `raycaster.intersectObject`

<details><summary>Code</summary>

```typescript
function intersectObjectWithRay( object, raycaster, includeInvisible ) {

	const allIntersections = raycaster.intersectObject( object, true );

	for ( let i = 0; i < allIntersections.length; i ++ ) {

		if ( allIntersections[ i ].object.visible || includeInvisible ) {

			return allIntersections[ i ];

		}

	}

	return false;

}
```
</details>

### `TransformControlsRoot.updateMatrixWorld(force: any): void`

**Parameters:**

- **`force`** `any`

**Returns:** `void`

**Calls:**

- `controls.object.updateMatrixWorld`
- `console.error`
- `controls.object.parent.matrixWorld.decompose`
- `controls.object.matrixWorld.decompose`
- `controls._parentQuaternionInv.copy( controls._parentQuaternion ).invert`
- `controls._worldQuaternionInv.copy( controls.worldQuaternion ).invert`
- `controls.camera.updateMatrixWorld`
- `controls.camera.matrixWorld.decompose`
- `controls.camera.getWorldDirection( controls.eye ).negate`
- `controls.eye.copy( controls.cameraPosition ).sub( controls.worldPosition ).normalize`
- `super.updateMatrixWorld`

<details><summary>Code</summary>

```typescript
updateMatrixWorld( force ) {

		const controls = this.controls;

		if ( controls.object !== undefined ) {

			controls.object.updateMatrixWorld();

			if ( controls.object.parent === null ) {

				console.error( 'TransformControls: The attached 3D object must be a part of the scene graph.' );

			} else {

				controls.object.parent.matrixWorld.decompose( controls._parentPosition, controls._parentQuaternion, controls._parentScale );

			}

			controls.object.matrixWorld.decompose( controls.worldPosition, controls.worldQuaternion, controls._worldScale );

			controls._parentQuaternionInv.copy( controls._parentQuaternion ).invert();
			controls._worldQuaternionInv.copy( controls.worldQuaternion ).invert();

		}

		controls.camera.updateMatrixWorld();
		controls.camera.matrixWorld.decompose( controls.cameraPosition, controls.cameraQuaternion, controls._cameraScale );

		if ( controls.camera.isOrthographicCamera ) {

			controls.camera.getWorldDirection( controls.eye ).negate();

		} else {

			controls.eye.copy( controls.cameraPosition ).sub( controls.worldPosition ).normalize();

		}

		super.updateMatrixWorld( force );

	}
```
</details>

### `TransformControlsRoot.dispose(): void`

**Returns:** `void`

**Calls:**

- `this.traverse`
- `child.geometry.dispose`
- `child.material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.traverse( function ( child ) {

			if ( child.geometry ) child.geometry.dispose();
			if ( child.material ) child.material.dispose();

		} );

	}
```
</details>

### `TransformControlsGizmo.updateMatrixWorld(force: any): void`

**Parameters:**

- **`force`** `any`

**Returns:** `void`

**Calls:**

- `handles.concat`
- `handle.rotation.set`
- `handle.position.copy`
- `this.worldPosition.distanceTo`
- `Math.min`
- `Math.tan`
- `handle.scale.set( 1, 1, 1 ).multiplyScalar`
- `_tempQuaternion.setFromEuler`
- `_tempEuler.set`
- `handle.quaternion.copy( quaternion ).multiply`
- `Math.abs`
- `_alignVector.copy( _unitX ).applyQuaternion( quaternion ).dot`
- `_alignVector.copy( _unitY ).applyQuaternion( quaternion ).dot`
- `_alignVector.copy( _unitZ ).applyQuaternion( quaternion ).dot`
- `_alignVector.copy`
- `handle.quaternion.setFromRotationMatrix`
- `_lookAtMatrix.lookAt`
- `handle.quaternion.multiply`
- `handle.quaternion.copy`
- `_tempVector.set( 1e-10, 1e-10, 1e-10 ).add( this.worldPositionStart ).sub( this.worldPosition ).multiplyScalar`
- `_tempVector.applyQuaternion`
- `this.worldQuaternionStart.clone().invert`
- `handle.scale.copy`
- `this.axis.search`
- `handle.scale.set`
- `_tempQuaternion2.copy`
- `_alignVector.copy( this.eye ).applyQuaternion`
- `_tempQuaternion.copy( quaternion ).invert`
- `handle.name.search`
- `_tempQuaternion.setFromAxisAngle`
- `Math.atan2`
- `_tempQuaternion.multiplyQuaternions`
- `handle.name.indexOf`
- `handle.material.color.clone`
- `handle.material.color.copy`
- `this.axis.split( '' ).some`
- `super.updateMatrixWorld`

**Internal Comments:**
```
// Show only gizmos for current transform mode (x6)
// hide aligned to camera (x4)
// TODO: simplify helpers and consider decoupling from gizmo
// If updating helper, skip rest of the loop
// Align handles to current local or world rotation (x9)
// Hide translate and scale axis facing the camera (x2)
// Hide disabled axes (x4)
// highlight selected axis (x5)
```

<details><summary>Code</summary>

```typescript
updateMatrixWorld( force ) {

		const space = ( this.mode === 'scale' ) ? 'local' : this.space; // scale always oriented to local rotation

		const quaternion = ( space === 'local' ) ? this.worldQuaternion : _identityQuaternion;

		// Show only gizmos for current transform mode

		this.gizmo[ 'translate' ].visible = this.mode === 'translate';
		this.gizmo[ 'rotate' ].visible = this.mode === 'rotate';
		this.gizmo[ 'scale' ].visible = this.mode === 'scale';

		this.helper[ 'translate' ].visible = this.mode === 'translate';
		this.helper[ 'rotate' ].visible = this.mode === 'rotate';
		this.helper[ 'scale' ].visible = this.mode === 'scale';


		let handles = [];
		handles = handles.concat( this.picker[ this.mode ].children );
		handles = handles.concat( this.gizmo[ this.mode ].children );
		handles = handles.concat( this.helper[ this.mode ].children );

		for ( let i = 0; i < handles.length; i ++ ) {

			const handle = handles[ i ];

			// hide aligned to camera

			handle.visible = true;
			handle.rotation.set( 0, 0, 0 );
			handle.position.copy( this.worldPosition );

			let factor;

			if ( this.camera.isOrthographicCamera ) {

				factor = ( this.camera.top - this.camera.bottom ) / this.camera.zoom;

			} else {

				factor = this.worldPosition.distanceTo( this.cameraPosition ) * Math.min( 1.9 * Math.tan( Math.PI * this.camera.fov / 360 ) / this.camera.zoom, 7 );

			}

			handle.scale.set( 1, 1, 1 ).multiplyScalar( factor * this.size / 4 );

			// TODO: simplify helpers and consider decoupling from gizmo

			if ( handle.tag === 'helper' ) {

				handle.visible = false;

				if ( handle.name === 'AXIS' ) {

					handle.visible = !! this.axis;

					if ( this.axis === 'X' ) {

						_tempQuaternion.setFromEuler( _tempEuler.set( 0, 0, 0 ) );
						handle.quaternion.copy( quaternion ).multiply( _tempQuaternion );

						if ( Math.abs( _alignVector.copy( _unitX ).applyQuaternion( quaternion ).dot( this.eye ) ) > 0.9 ) {

							handle.visible = false;

						}

					}

					if ( this.axis === 'Y' ) {

						_tempQuaternion.setFromEuler( _tempEuler.set( 0, 0, Math.PI / 2 ) );
						handle.quaternion.copy( quaternion ).multiply( _tempQuaternion );

						if ( Math.abs( _alignVector.copy( _unitY ).applyQuaternion( quaternion ).dot( this.eye ) ) > 0.9 ) {

							handle.visible = false;

						}

					}

					if ( this.axis === 'Z' ) {

						_tempQuaternion.setFromEuler( _tempEuler.set( 0, Math.PI / 2, 0 ) );
						handle.quaternion.copy( quaternion ).multiply( _tempQuaternion );

						if ( Math.abs( _alignVector.copy( _unitZ ).applyQuaternion( quaternion ).dot( this.eye ) ) > 0.9 ) {

							handle.visible = false;

						}

					}

					if ( this.axis === 'XYZE' ) {

						_tempQuaternion.setFromEuler( _tempEuler.set( 0, Math.PI / 2, 0 ) );
						_alignVector.copy( this.rotationAxis );
						handle.quaternion.setFromRotationMatrix( _lookAtMatrix.lookAt( _zeroVector, _alignVector, _unitY ) );
						handle.quaternion.multiply( _tempQuaternion );
						handle.visible = this.dragging;

					}

					if ( this.axis === 'E' ) {

						handle.visible = false;

					}


				} else if ( handle.name === 'START' ) {

					handle.position.copy( this.worldPositionStart );
					handle.visible = this.dragging;

				} else if ( handle.name === 'END' ) {

					handle.position.copy( this.worldPosition );
					handle.visible = this.dragging;

				} else if ( handle.name === 'DELTA' ) {

					handle.position.copy( this.worldPositionStart );
					handle.quaternion.copy( this.worldQuaternionStart );
					_tempVector.set( 1e-10, 1e-10, 1e-10 ).add( this.worldPositionStart ).sub( this.worldPosition ).multiplyScalar( - 1 );
					_tempVector.applyQuaternion( this.worldQuaternionStart.clone().invert() );
					handle.scale.copy( _tempVector );
					handle.visible = this.dragging;

				} else {

					handle.quaternion.copy( quaternion );

					if ( this.dragging ) {

						handle.position.copy( this.worldPositionStart );

					} else {

						handle.position.copy( this.worldPosition );

					}

					if ( this.axis ) {

						handle.visible = this.axis.search( handle.name ) !== - 1;

					}

				}

				// If updating helper, skip rest of the loop
				continue;

			}

			// Align handles to current local or world rotation

			handle.quaternion.copy( quaternion );

			if ( this.mode === 'translate' || this.mode === 'scale' ) {

				// Hide translate and scale axis facing the camera

				const AXIS_HIDE_THRESHOLD = 0.99;
				const PLANE_HIDE_THRESHOLD = 0.2;

				if ( handle.name === 'X' ) {

					if ( Math.abs( _alignVector.copy( _unitX ).applyQuaternion( quaternion ).dot( this.eye ) ) > AXIS_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

				if ( handle.name === 'Y' ) {

					if ( Math.abs( _alignVector.copy( _unitY ).applyQuaternion( quaternion ).dot( this.eye ) ) > AXIS_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

				if ( handle.name === 'Z' ) {

					if ( Math.abs( _alignVector.copy( _unitZ ).applyQuaternion( quaternion ).dot( this.eye ) ) > AXIS_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

				if ( handle.name === 'XY' ) {

					if ( Math.abs( _alignVector.copy( _unitZ ).applyQuaternion( quaternion ).dot( this.eye ) ) < PLANE_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

				if ( handle.name === 'YZ' ) {

					if ( Math.abs( _alignVector.copy( _unitX ).applyQuaternion( quaternion ).dot( this.eye ) ) < PLANE_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

				if ( handle.name === 'XZ' ) {

					if ( Math.abs( _alignVector.copy( _unitY ).applyQuaternion( quaternion ).dot( this.eye ) ) < PLANE_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

			} else if ( this.mode === 'rotate' ) {

				// Align handles to current local or world rotation

				_tempQuaternion2.copy( quaternion );
				_alignVector.copy( this.eye ).applyQuaternion( _tempQuaternion.copy( quaternion ).invert() );

				if ( handle.name.search( 'E' ) !== - 1 ) {

					handle.quaternion.setFromRotationMatrix( _lookAtMatrix.lookAt( this.eye, _zeroVector, _unitY ) );

				}

				if ( handle.name === 'X' ) {

					_tempQuaternion.setFromAxisAngle( _unitX, Math.atan2( - _alignVector.y, _alignVector.z ) );
					_tempQuaternion.multiplyQuaternions( _tempQuaternion2, _tempQuaternion );
					handle.quaternion.copy( _tempQuaternion );

				}

				if ( handle.name === 'Y' ) {

					_tempQuaternion.setFromAxisAngle( _unitY, Math.atan2( _alignVector.x, _alignVector.z ) );
					_tempQuaternion.multiplyQuaternions( _tempQuaternion2, _tempQuaternion );
					handle.quaternion.copy( _tempQuaternion );

				}

				if ( handle.name === 'Z' ) {

					_tempQuaternion.setFromAxisAngle( _unitZ, Math.atan2( _alignVector.y, _alignVector.x ) );
					_tempQuaternion.multiplyQuaternions( _tempQuaternion2, _tempQuaternion );
					handle.quaternion.copy( _tempQuaternion );

				}

			}

			// Hide disabled axes
			handle.visible = handle.visible && ( handle.name.indexOf( 'X' ) === - 1 || this.showX );
			handle.visible = handle.visible && ( handle.name.indexOf( 'Y' ) === - 1 || this.showY );
			handle.visible = handle.visible && ( handle.name.indexOf( 'Z' ) === - 1 || this.showZ );
			handle.visible = handle.visible && ( handle.name.indexOf( 'E' ) === - 1 || ( this.showX && this.showY && this.showZ ) );

			// highlight selected axis

			handle.material._color = handle.material._color || handle.material.color.clone();
			handle.material._opacity = handle.material._opacity || handle.material.opacity;

			handle.material.color.copy( handle.material._color );
			handle.material.opacity = handle.material._opacity;

			if ( this.enabled && this.axis ) {

				if ( handle.name === this.axis ) {

					handle.material.color.copy( this.materialLib.active.color );
					handle.material.opacity = 1.0;

				} else if ( this.axis.split( '' ).some( function ( a ) {

					return handle.name === a;

				} ) ) {

					handle.material.color.copy( this.materialLib.active.color );
					handle.material.opacity = 1.0;

				}

			}

		}

		super.updateMatrixWorld( force );

	}
```
</details>

### `CircleGeometry(radius: any, arc: any): any`

**Parameters:**

- **`radius`** `any`
- **`arc`** `any`

**Returns:** `any`

**Calls:**

- `geometry.rotateY`
- `geometry.rotateX`

<details><summary>Code</summary>

```typescript
function CircleGeometry( radius, arc ) {

			const geometry = new TorusGeometry( radius, 0.0075, 3, 64, arc * Math.PI * 2 );
			geometry.rotateY( Math.PI / 2 );
			geometry.rotateX( Math.PI / 2 );
			return geometry;

		}
```
</details>

### `TranslateHelperGeometry(): any`

**Returns:** `any`

**Calls:**

- `geometry.setAttribute`

<details><summary>Code</summary>

```typescript
function TranslateHelperGeometry() {

			const geometry = new BufferGeometry();

			geometry.setAttribute( 'position', new Float32BufferAttribute( [ 0, 0, 0, 1, 1, 1 ], 3 ) );

			return geometry;

		}
```
</details>

### `setupGizmo(gizmoMap: any): any`

**Parameters:**

- **`gizmoMap`** `any`

**Returns:** `any`

**Calls:**

- `gizmoMap[ name ][ i ][ 0 ].clone`
- `object.position.set`
- `object.rotation.set`
- `object.scale.set`
- `object.updateMatrix`
- `object.geometry.clone`
- `tempGeometry.applyMatrix4`
- `gizmo.add`

**Internal Comments:**
```
// name and tag properties are essential for picking and updating logic. (x4)
```

<details><summary>Code</summary>

```typescript
function setupGizmo( gizmoMap ) {

			const gizmo = new Object3D();

			for ( const name in gizmoMap ) {

				for ( let i = gizmoMap[ name ].length; i --; ) {

					const object = gizmoMap[ name ][ i ][ 0 ].clone();
					const position = gizmoMap[ name ][ i ][ 1 ];
					const rotation = gizmoMap[ name ][ i ][ 2 ];
					const scale = gizmoMap[ name ][ i ][ 3 ];
					const tag = gizmoMap[ name ][ i ][ 4 ];

					// name and tag properties are essential for picking and updating logic.
					object.name = name;
					object.tag = tag;

					if ( position ) {

						object.position.set( position[ 0 ], position[ 1 ], position[ 2 ] );

					}

					if ( rotation ) {

						object.rotation.set( rotation[ 0 ], rotation[ 1 ], rotation[ 2 ] );

					}

					if ( scale ) {

						object.scale.set( scale[ 0 ], scale[ 1 ], scale[ 2 ] );

					}

					object.updateMatrix();

					const tempGeometry = object.geometry.clone();
					tempGeometry.applyMatrix4( object.matrix );
					object.geometry = tempGeometry;
					object.renderOrder = Infinity;

					object.position.set( 0, 0, 0 );
					object.rotation.set( 0, 0, 0 );
					object.scale.set( 1, 1, 1 );

					gizmo.add( object );

				}

			}

			return gizmo;

		}
```
</details>

### `TransformControlsPlane.updateMatrixWorld(force: any): void`

**Parameters:**

- **`force`** `any`

**Returns:** `void`

**Calls:**

- `this.position.copy`
- `_v1.copy( _unitX ).applyQuaternion`
- `_v2.copy( _unitY ).applyQuaternion`
- `_v3.copy( _unitZ ).applyQuaternion`
- `_alignVector.copy`
- `_alignVector.copy( this.eye ).cross`
- `_dirVector.copy( _v1 ).cross`
- `_dirVector.copy( _v2 ).cross`
- `_dirVector.copy( _v3 ).cross`
- `_dirVector.copy`
- `_dirVector.set`
- `_dirVector.length`
- `this.quaternion.copy`
- `_tempMatrix.lookAt`
- `_tempVector.set`
- `this.quaternion.setFromRotationMatrix`
- `super.updateMatrixWorld`

**Internal Comments:**
```
// Align the plane for current transform mode, axis and space. (x4)
// special case for rotate (x4)
// If in rotate mode, make the plane parallel to camera (x5)
```

<details><summary>Code</summary>

```typescript
updateMatrixWorld( force ) {

		let space = this.space;

		this.position.copy( this.worldPosition );

		if ( this.mode === 'scale' ) space = 'local'; // scale always oriented to local rotation

		_v1.copy( _unitX ).applyQuaternion( space === 'local' ? this.worldQuaternion : _identityQuaternion );
		_v2.copy( _unitY ).applyQuaternion( space === 'local' ? this.worldQuaternion : _identityQuaternion );
		_v3.copy( _unitZ ).applyQuaternion( space === 'local' ? this.worldQuaternion : _identityQuaternion );

		// Align the plane for current transform mode, axis and space.

		_alignVector.copy( _v2 );

		switch ( this.mode ) {

			case 'translate':
			case 'scale':
				switch ( this.axis ) {

					case 'X':
						_alignVector.copy( this.eye ).cross( _v1 );
						_dirVector.copy( _v1 ).cross( _alignVector );
						break;
					case 'Y':
						_alignVector.copy( this.eye ).cross( _v2 );
						_dirVector.copy( _v2 ).cross( _alignVector );
						break;
					case 'Z':
						_alignVector.copy( this.eye ).cross( _v3 );
						_dirVector.copy( _v3 ).cross( _alignVector );
						break;
					case 'XY':
						_dirVector.copy( _v3 );
						break;
					case 'YZ':
						_dirVector.copy( _v1 );
						break;
					case 'XZ':
						_alignVector.copy( _v3 );
						_dirVector.copy( _v2 );
						break;
					case 'XYZ':
					case 'E':
						_dirVector.set( 0, 0, 0 );
						break;

				}

				break;
			case 'rotate':
			default:
				// special case for rotate
				_dirVector.set( 0, 0, 0 );

		}

		if ( _dirVector.length() === 0 ) {

			// If in rotate mode, make the plane parallel to camera
			this.quaternion.copy( this.cameraQuaternion );

		} else {

			_tempMatrix.lookAt( _tempVector.set( 0, 0, 0 ), _dirVector, _alignVector );

			this.quaternion.setFromRotationMatrix( _tempMatrix );

		}

		super.updateMatrixWorld( force );

	}
```
</details>


---

## Classes

### `TransformControls`

<details><summary>Class Code</summary>

```ts
class TransformControls extends Controls {

	/**
	 * Constructs a new controls instance.
	 *
	 * @param {Camera} camera - The camera of the rendered scene.
	 * @param {?HTMLDOMElement} domElement - The HTML element used for event listeners.
	 */
	constructor( camera, domElement = null ) {

		super( undefined, domElement );

		const root = new TransformControlsRoot( this );
		this._root = root;

		const gizmo = new TransformControlsGizmo();
		this._gizmo = gizmo;
		root.add( gizmo );

		const plane = new TransformControlsPlane();
		this._plane = plane;
		root.add( plane );

		const scope = this;

		// Defined getter, setter and store for a property
		function defineProperty( propName, defaultValue ) {

			let propValue = defaultValue;

			Object.defineProperty( scope, propName, {

				get: function () {

					return propValue !== undefined ? propValue : defaultValue;

				},

				set: function ( value ) {

					if ( propValue !== value ) {

						propValue = value;
						plane[ propName ] = value;
						gizmo[ propName ] = value;

						scope.dispatchEvent( { type: propName + '-changed', value: value } );
						scope.dispatchEvent( _changeEvent );

					}

				}

			} );

			scope[ propName ] = defaultValue;
			plane[ propName ] = defaultValue;
			gizmo[ propName ] = defaultValue;

		}

		// Define properties with getters/setter
		// Setting the defined property will automatically trigger change event
		// Defined properties are passed down to gizmo and plane

		/**
		 * The camera of the rendered scene.
		 *
		 * @name TransformControls#camera
		 * @type {Camera}
		 */
		defineProperty( 'camera', camera );
		defineProperty( 'object', undefined );
		defineProperty( 'enabled', true );

		/**
		 * The current transformation axis.
		 *
		 * @name TransformControls#axis
		 * @type {string}
		 */
		defineProperty( 'axis', null );

		/**
		 * The current transformation axis.
		 *
		 * @name TransformControls#mode
		 * @type {('translate'|'rotate'|'scale')}
		 * @default 'translate'
		 */
		defineProperty( 'mode', 'translate' );

		/**
		 * By default, 3D objects are continuously translated. If you set this property to a numeric
		 * value (world units), you can define in which steps the 3D object should be translated.
		 *
		 * @name TransformControls#translationSnap
		 * @type {?number}
		 * @default null
		 */
		defineProperty( 'translationSnap', null );

		/**
		 * By default, 3D objects are continuously rotated. If you set this property to a numeric
		 * value (radians), you can define in which steps the 3D object should be rotated.
		 *
		 * @name TransformControls#rotationSnap
		 * @type {?number}
		 * @default null
		 */
		defineProperty( 'rotationSnap', null );

		/**
		 * By default, 3D objects are continuously scaled. If you set this property to a numeric
		 * value, you can define in which steps the 3D object should be scaled.
		 *
		 * @name TransformControls#scaleSnap
		 * @type {?number}
		 * @default null
		 */
		defineProperty( 'scaleSnap', null );

		/**
		 * Defines in which coordinate space transformations should be performed.
		 *
		 * @name TransformControls#space
		 * @type {('world'|'local')}
		 * @default 'world'
		 */
		defineProperty( 'space', 'world' );

		/**
		 * The size of the helper UI (axes/planes).
		 *
		 * @name TransformControls#size
		 * @type {number}
		 * @default 1
		 */
		defineProperty( 'size', 1 );

		/**
		 * Whether dragging is currently performed or not.
		 *
		 * @name TransformControls#dragging
		 * @type {boolean}
		 * @readonly
		 * @default false
		 */
		defineProperty( 'dragging', false );

		/**
		 * Whether the x-axis helper should be visible or not.
		 *
		 * @name TransformControls#showX
		 * @type {boolean}
		 * @default true
		 */
		defineProperty( 'showX', true );

		/**
		 * Whether the y-axis helper should be visible or not.
		 *
		 * @name TransformControls#showY
		 * @type {boolean}
		 * @default true
		 */
		defineProperty( 'showY', true );

		/**
		 * Whether the z-axis helper should be visible or not.
		 *
		 * @name TransformControls#showZ
		 * @type {boolean}
		 * @default true
		 */
		defineProperty( 'showZ', true );

		/**
		 * The minimum allowed X position during translation.
		 *
		 * @name TransformControls#minX
		 * @type {number}
		 * @default -Infinity
		 */
		defineProperty( 'minX', - Infinity );

		/**
		 * The maximum allowed X position during translation.
		 *
		 * @name TransformControls#maxX
		 * @type {number}
		 * @default Infinity
		 */
		defineProperty( 'maxX', Infinity );

		/**
		 * The minimum allowed y position during translation.
		 *
		 * @name TransformControls#minY
		 * @type {number}
		 * @default -Infinity
		 */
		defineProperty( 'minY', - Infinity );

		/**
		 * The maximum allowed Y position during translation.
		 *
		 * @name TransformControls#maxY
		 * @type {number}
		 * @default Infinity
		 */
		defineProperty( 'maxY', Infinity );

		/**
		 * The minimum allowed z position during translation.
		 *
		 * @name TransformControls#minZ
		 * @type {number}
		 * @default -Infinity
		 */
		defineProperty( 'minZ', - Infinity );

		/**
		 * The maximum allowed Z position during translation.
		 *
		 * @name TransformControls#maxZ
		 * @type {number}
		 * @default Infinity
		 */
		defineProperty( 'maxZ', Infinity );

		// Reusable utility variables

		const worldPosition = new Vector3();
		const worldPositionStart = new Vector3();
		const worldQuaternion = new Quaternion();
		const worldQuaternionStart = new Quaternion();
		const cameraPosition = new Vector3();
		const cameraQuaternion = new Quaternion();
		const pointStart = new Vector3();
		const pointEnd = new Vector3();
		const rotationAxis = new Vector3();
		const rotationAngle = 0;
		const eye = new Vector3();

		// TODO: remove properties unused in plane and gizmo

		defineProperty( 'worldPosition', worldPosition );
		defineProperty( 'worldPositionStart', worldPositionStart );
		defineProperty( 'worldQuaternion', worldQuaternion );
		defineProperty( 'worldQuaternionStart', worldQuaternionStart );
		defineProperty( 'cameraPosition', cameraPosition );
		defineProperty( 'cameraQuaternion', cameraQuaternion );
		defineProperty( 'pointStart', pointStart );
		defineProperty( 'pointEnd', pointEnd );
		defineProperty( 'rotationAxis', rotationAxis );
		defineProperty( 'rotationAngle', rotationAngle );
		defineProperty( 'eye', eye );

		this._offset = new Vector3();
		this._startNorm = new Vector3();
		this._endNorm = new Vector3();
		this._cameraScale = new Vector3();

		this._parentPosition = new Vector3();
		this._parentQuaternion = new Quaternion();
		this._parentQuaternionInv = new Quaternion();
		this._parentScale = new Vector3();

		this._worldScaleStart = new Vector3();
		this._worldQuaternionInv = new Quaternion();
		this._worldScale = new Vector3();

		this._positionStart = new Vector3();
		this._quaternionStart = new Quaternion();
		this._scaleStart = new Vector3();

		this._getPointer = getPointer.bind( this );
		this._onPointerDown = onPointerDown.bind( this );
		this._onPointerHover = onPointerHover.bind( this );
		this._onPointerMove = onPointerMove.bind( this );
		this._onPointerUp = onPointerUp.bind( this );

		if ( domElement !== null ) {

			this.connect( domElement );

		}

	}

	connect( element ) {

		super.connect( element );

		this.domElement.addEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.addEventListener( 'pointermove', this._onPointerHover );
		this.domElement.addEventListener( 'pointerup', this._onPointerUp );

		this.domElement.style.touchAction = 'none'; // disable touch scroll

	}

	disconnect() {

		this.domElement.removeEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.removeEventListener( 'pointermove', this._onPointerHover );
		this.domElement.removeEventListener( 'pointermove', this._onPointerMove );
		this.domElement.removeEventListener( 'pointerup', this._onPointerUp );

		this.domElement.style.touchAction = 'auto';

	}

	/**
	 * Returns the visual representation of the controls. Add the helper to your scene to
	 * visually transform the attached  3D object.
	 *
	 * @return {TransformControlsRoot} The helper.
	 */
	getHelper() {

		return this._root;

	}

	pointerHover( pointer ) {

		if ( this.object === undefined || this.dragging === true ) return;

		if ( pointer !== null ) _raycaster.setFromCamera( pointer, this.camera );

		const intersect = intersectObjectWithRay( this._gizmo.picker[ this.mode ], _raycaster );

		if ( intersect ) {

			this.axis = intersect.object.name;

		} else {

			this.axis = null;

		}

	}

	pointerDown( pointer ) {

		if ( this.object === undefined || this.dragging === true || ( pointer != null && pointer.button !== 0 ) ) return;

		if ( this.axis !== null ) {

			if ( pointer !== null ) _raycaster.setFromCamera( pointer, this.camera );

			const planeIntersect = intersectObjectWithRay( this._plane, _raycaster, true );

			if ( planeIntersect ) {

				this.object.updateMatrixWorld();
				this.object.parent.updateMatrixWorld();

				this._positionStart.copy( this.object.position );
				this._quaternionStart.copy( this.object.quaternion );
				this._scaleStart.copy( this.object.scale );

				this.object.matrixWorld.decompose( this.worldPositionStart, this.worldQuaternionStart, this._worldScaleStart );

				this.pointStart.copy( planeIntersect.point ).sub( this.worldPositionStart );

			}

			this.dragging = true;
			_mouseDownEvent.mode = this.mode;
			this.dispatchEvent( _mouseDownEvent );

		}

	}

	pointerMove( pointer ) {

		const axis = this.axis;
		const mode = this.mode;
		const object = this.object;
		let space = this.space;

		if ( mode === 'scale' ) {

			space = 'local';

		} else if ( axis === 'E' || axis === 'XYZE' || axis === 'XYZ' ) {

			space = 'world';

		}

		if ( object === undefined || axis === null || this.dragging === false || ( pointer !== null && pointer.button !== - 1 ) ) return;

		if ( pointer !== null ) _raycaster.setFromCamera( pointer, this.camera );

		const planeIntersect = intersectObjectWithRay( this._plane, _raycaster, true );

		if ( ! planeIntersect ) return;

		this.pointEnd.copy( planeIntersect.point ).sub( this.worldPositionStart );

		if ( mode === 'translate' ) {

			// Apply translate

			this._offset.copy( this.pointEnd ).sub( this.pointStart );

			if ( space === 'local' && axis !== 'XYZ' ) {

				this._offset.applyQuaternion( this._worldQuaternionInv );

			}

			if ( axis.indexOf( 'X' ) === - 1 ) this._offset.x = 0;
			if ( axis.indexOf( 'Y' ) === - 1 ) this._offset.y = 0;
			if ( axis.indexOf( 'Z' ) === - 1 ) this._offset.z = 0;

			if ( space === 'local' && axis !== 'XYZ' ) {

				this._offset.applyQuaternion( this._quaternionStart ).divide( this._parentScale );

			} else {

				this._offset.applyQuaternion( this._parentQuaternionInv ).divide( this._parentScale );

			}

			object.position.copy( this._offset ).add( this._positionStart );

			// Apply translation snap

			if ( this.translationSnap ) {

				if ( space === 'local' ) {

					object.position.applyQuaternion( _tempQuaternion.copy( this._quaternionStart ).invert() );

					if ( axis.search( 'X' ) !== - 1 ) {

						object.position.x = Math.round( object.position.x / this.translationSnap ) * this.translationSnap;

					}

					if ( axis.search( 'Y' ) !== - 1 ) {

						object.position.y = Math.round( object.position.y / this.translationSnap ) * this.translationSnap;

					}

					if ( axis.search( 'Z' ) !== - 1 ) {

						object.position.z = Math.round( object.position.z / this.translationSnap ) * this.translationSnap;

					}

					object.position.applyQuaternion( this._quaternionStart );

				}

				if ( space === 'world' ) {

					if ( object.parent ) {

						object.position.add( _tempVector.setFromMatrixPosition( object.parent.matrixWorld ) );

					}

					if ( axis.search( 'X' ) !== - 1 ) {

						object.position.x = Math.round( object.position.x / this.translationSnap ) * this.translationSnap;

					}

					if ( axis.search( 'Y' ) !== - 1 ) {

						object.position.y = Math.round( object.position.y / this.translationSnap ) * this.translationSnap;

					}

					if ( axis.search( 'Z' ) !== - 1 ) {

						object.position.z = Math.round( object.position.z / this.translationSnap ) * this.translationSnap;

					}

					if ( object.parent ) {

						object.position.sub( _tempVector.setFromMatrixPosition( object.parent.matrixWorld ) );

					}

				}

			}

			object.position.x = Math.max( this.minX, Math.min( this.maxX, object.position.x ) );
			object.position.y = Math.max( this.minY, Math.min( this.maxY, object.position.y ) );
			object.position.z = Math.max( this.minZ, Math.min( this.maxZ, object.position.z ) );

		} else if ( mode === 'scale' ) {

			if ( axis.search( 'XYZ' ) !== - 1 ) {

				let d = this.pointEnd.length() / this.pointStart.length();

				if ( this.pointEnd.dot( this.pointStart ) < 0 ) d *= - 1;

				_tempVector2.set( d, d, d );

			} else {

				_tempVector.copy( this.pointStart );
				_tempVector2.copy( this.pointEnd );

				_tempVector.applyQuaternion( this._worldQuaternionInv );
				_tempVector2.applyQuaternion( this._worldQuaternionInv );

				_tempVector2.divide( _tempVector );

				if ( axis.search( 'X' ) === - 1 ) {

					_tempVector2.x = 1;

				}

				if ( axis.search( 'Y' ) === - 1 ) {

					_tempVector2.y = 1;

				}

				if ( axis.search( 'Z' ) === - 1 ) {

					_tempVector2.z = 1;

				}

			}

			// Apply scale

			object.scale.copy( this._scaleStart ).multiply( _tempVector2 );

			if ( this.scaleSnap ) {

				if ( axis.search( 'X' ) !== - 1 ) {

					object.scale.x = Math.round( object.scale.x / this.scaleSnap ) * this.scaleSnap || this.scaleSnap;

				}

				if ( axis.search( 'Y' ) !== - 1 ) {

					object.scale.y = Math.round( object.scale.y / this.scaleSnap ) * this.scaleSnap || this.scaleSnap;

				}

				if ( axis.search( 'Z' ) !== - 1 ) {

					object.scale.z = Math.round( object.scale.z / this.scaleSnap ) * this.scaleSnap || this.scaleSnap;

				}

			}

		} else if ( mode === 'rotate' ) {

			this._offset.copy( this.pointEnd ).sub( this.pointStart );

			const ROTATION_SPEED = 20 / this.worldPosition.distanceTo( _tempVector.setFromMatrixPosition( this.camera.matrixWorld ) );

			let _inPlaneRotation = false;

			if ( axis === 'XYZE' ) {

				this.rotationAxis.copy( this._offset ).cross( this.eye ).normalize();
				this.rotationAngle = this._offset.dot( _tempVector.copy( this.rotationAxis ).cross( this.eye ) ) * ROTATION_SPEED;

			} else if ( axis === 'X' || axis === 'Y' || axis === 'Z' ) {

				this.rotationAxis.copy( _unit[ axis ] );

				_tempVector.copy( _unit[ axis ] );

				if ( space === 'local' ) {

					_tempVector.applyQuaternion( this.worldQuaternion );

				}

				_tempVector.cross( this.eye );

				// When _tempVector is 0 after cross with this.eye the vectors are parallel and should use in-plane rotation logic.
				if ( _tempVector.length() === 0 ) {

					_inPlaneRotation = true;

				} else {

					this.rotationAngle = this._offset.dot( _tempVector.normalize() ) * ROTATION_SPEED;

				}


			}

			if ( axis === 'E' || _inPlaneRotation ) {

				this.rotationAxis.copy( this.eye );
				this.rotationAngle = this.pointEnd.angleTo( this.pointStart );

				this._startNorm.copy( this.pointStart ).normalize();
				this._endNorm.copy( this.pointEnd ).normalize();

				this.rotationAngle *= ( this._endNorm.cross( this._startNorm ).dot( this.eye ) < 0 ? 1 : - 1 );

			}

			// Apply rotation snap

			if ( this.rotationSnap ) this.rotationAngle = Math.round( this.rotationAngle / this.rotationSnap ) * this.rotationSnap;

			// Apply rotate
			if ( space === 'local' && axis !== 'E' && axis !== 'XYZE' ) {

				object.quaternion.copy( this._quaternionStart );
				object.quaternion.multiply( _tempQuaternion.setFromAxisAngle( this.rotationAxis, this.rotationAngle ) ).normalize();

			} else {

				this.rotationAxis.applyQuaternion( this._parentQuaternionInv );
				object.quaternion.copy( _tempQuaternion.setFromAxisAngle( this.rotationAxis, this.rotationAngle ) );
				object.quaternion.multiply( this._quaternionStart ).normalize();

			}

		}

		this.dispatchEvent( _changeEvent );
		this.dispatchEvent( _objectChangeEvent );

	}

	pointerUp( pointer ) {

		if ( pointer !== null && pointer.button !== 0 ) return;

		if ( this.dragging && ( this.axis !== null ) ) {

			_mouseUpEvent.mode = this.mode;
			this.dispatchEvent( _mouseUpEvent );

		}

		this.dragging = false;
		this.axis = null;

	}

	dispose() {

		this.disconnect();

		this._root.dispose();

	}

	/**
	 * Sets the 3D object that should be transformed and ensures the controls UI is visible.
	 *
	 * @param {Object3D} object -  The 3D object that should be transformed.
	 * @return {TransformControls} A reference to this controls.
	 */
	attach( object ) {

		this.object = object;
		this._root.visible = true;

		return this;

	}

	/**
	 * Removes the current 3D object from the controls and makes the helper UI invisible.
	 *
	 * @return {TransformControls} A reference to this controls.
	 */
	detach() {

		this.object = undefined;
		this.axis = null;

		this._root.visible = false;

		return this;

	}

	/**
	 * Resets the object's position, rotation and scale to when the current transform began.
	 */
	reset() {

		if ( ! this.enabled ) return;

		if ( this.dragging ) {

			this.object.position.copy( this._positionStart );
			this.object.quaternion.copy( this._quaternionStart );
			this.object.scale.copy( this._scaleStart );

			this.dispatchEvent( _changeEvent );
			this.dispatchEvent( _objectChangeEvent );

			this.pointStart.copy( this.pointEnd );

		}

	}

	/**
	 * Returns the raycaster that is used for user interaction. This object is shared between all
	 * instances of `TransformControls`.
	 *
	 * @returns {Raycaster} The internal raycaster.
	 */
	getRaycaster() {

		return _raycaster;

	}

	/**
	 * Returns the transformation mode.
	 *
	 * @returns {'translate'|'rotate'|'scale'} The transformation mode.
	 */
	getMode() {

		return this.mode;

	}

	/**
	 * Sets the given transformation mode.
	 *
	 * @param {'translate'|'rotate'|'scale'} mode - The transformation mode to set.
	 */
	setMode( mode ) {

		this.mode = mode;

	}

	/**
	 * Sets the translation snap.
	 *
	 * @param {?number} translationSnap - The translation snap to set.
	 */
	setTranslationSnap( translationSnap ) {

		this.translationSnap = translationSnap;

	}

	/**
	 * Sets the rotation snap.
	 *
	 * @param {?number} rotationSnap - The rotation snap to set.
	 */
	setRotationSnap( rotationSnap ) {

		this.rotationSnap = rotationSnap;

	}

	/**
	 * Sets the scale snap.
	 *
	 * @param {?number} scaleSnap - The scale snap to set.
	 */
	setScaleSnap( scaleSnap ) {

		this.scaleSnap = scaleSnap;

	}

	/**
	 * Sets the size of the helper UI.
	 *
	 * @param {number} size - The size to set.
	 */
	setSize( size ) {

		this.size = size;

	}

	/**
	 * Sets the coordinate space in which transformations are applied.
	 *
	 * @param {'world'|'local'} space - The space to set.
	 */
	setSpace( space ) {

		this.space = space;

	}

	/**
	 * Sets the colors of the control's gizmo.
	 *
	 * @param {number|Color|string} xAxis - The x-axis color.
	 * @param {number|Color|string} yAxis - The y-axis color.
	 * @param {number|Color|string} zAxis - The z-axis color.
	 * @param {number|Color|string} active - The color for active elements.
	 */
	setColors( xAxis, yAxis, zAxis, active ) {

		const materialLib = this._gizmo.materialLib;

		materialLib.xAxis.color.set( xAxis );
		materialLib.yAxis.color.set( yAxis );
		materialLib.zAxis.color.set( zAxis );
		materialLib.active.color.set( active );
		materialLib.xAxisTransparent.color.set( xAxis );
		materialLib.yAxisTransparent.color.set( yAxis );
		materialLib.zAxisTransparent.color.set( zAxis );
		materialLib.activeTransparent.color.set( active );

		// update color caches

		if ( materialLib.xAxis._color ) materialLib.xAxis._color.set( xAxis );
		if ( materialLib.yAxis._color ) materialLib.yAxis._color.set( yAxis );
		if ( materialLib.zAxis._color ) materialLib.zAxis._color.set( zAxis );
		if ( materialLib.active._color ) materialLib.active._color.set( active );
		if ( materialLib.xAxisTransparent._color ) materialLib.xAxisTransparent._color.set( xAxis );
		if ( materialLib.yAxisTransparent._color ) materialLib.yAxisTransparent._color.set( yAxis );
		if ( materialLib.zAxisTransparent._color ) materialLib.zAxisTransparent._color.set( zAxis );
		if ( materialLib.activeTransparent._color ) materialLib.activeTransparent._color.set( active );

	}

}
```
</details>

#### Methods

##### `connect(element: any): void`

<details><summary>Code</summary>

```ts
connect( element ) {

		super.connect( element );

		this.domElement.addEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.addEventListener( 'pointermove', this._onPointerHover );
		this.domElement.addEventListener( 'pointerup', this._onPointerUp );

		this.domElement.style.touchAction = 'none'; // disable touch scroll

	}
```
</details>

##### `disconnect(): void`

<details><summary>Code</summary>

```ts
disconnect() {

		this.domElement.removeEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.removeEventListener( 'pointermove', this._onPointerHover );
		this.domElement.removeEventListener( 'pointermove', this._onPointerMove );
		this.domElement.removeEventListener( 'pointerup', this._onPointerUp );

		this.domElement.style.touchAction = 'auto';

	}
```
</details>

##### `getHelper(): TransformControlsRoot`

<details><summary>Code</summary>

```ts
getHelper() {

		return this._root;

	}
```
</details>

##### `pointerHover(pointer: any): void`

<details><summary>Code</summary>

```ts
pointerHover( pointer ) {

		if ( this.object === undefined || this.dragging === true ) return;

		if ( pointer !== null ) _raycaster.setFromCamera( pointer, this.camera );

		const intersect = intersectObjectWithRay( this._gizmo.picker[ this.mode ], _raycaster );

		if ( intersect ) {

			this.axis = intersect.object.name;

		} else {

			this.axis = null;

		}

	}
```
</details>

##### `pointerDown(pointer: any): void`

<details><summary>Code</summary>

```ts
pointerDown( pointer ) {

		if ( this.object === undefined || this.dragging === true || ( pointer != null && pointer.button !== 0 ) ) return;

		if ( this.axis !== null ) {

			if ( pointer !== null ) _raycaster.setFromCamera( pointer, this.camera );

			const planeIntersect = intersectObjectWithRay( this._plane, _raycaster, true );

			if ( planeIntersect ) {

				this.object.updateMatrixWorld();
				this.object.parent.updateMatrixWorld();

				this._positionStart.copy( this.object.position );
				this._quaternionStart.copy( this.object.quaternion );
				this._scaleStart.copy( this.object.scale );

				this.object.matrixWorld.decompose( this.worldPositionStart, this.worldQuaternionStart, this._worldScaleStart );

				this.pointStart.copy( planeIntersect.point ).sub( this.worldPositionStart );

			}

			this.dragging = true;
			_mouseDownEvent.mode = this.mode;
			this.dispatchEvent( _mouseDownEvent );

		}

	}
```
</details>

##### `pointerMove(pointer: any): void`

<details><summary>Code</summary>

```ts
pointerMove( pointer ) {

		const axis = this.axis;
		const mode = this.mode;
		const object = this.object;
		let space = this.space;

		if ( mode === 'scale' ) {

			space = 'local';

		} else if ( axis === 'E' || axis === 'XYZE' || axis === 'XYZ' ) {

			space = 'world';

		}

		if ( object === undefined || axis === null || this.dragging === false || ( pointer !== null && pointer.button !== - 1 ) ) return;

		if ( pointer !== null ) _raycaster.setFromCamera( pointer, this.camera );

		const planeIntersect = intersectObjectWithRay( this._plane, _raycaster, true );

		if ( ! planeIntersect ) return;

		this.pointEnd.copy( planeIntersect.point ).sub( this.worldPositionStart );

		if ( mode === 'translate' ) {

			// Apply translate

			this._offset.copy( this.pointEnd ).sub( this.pointStart );

			if ( space === 'local' && axis !== 'XYZ' ) {

				this._offset.applyQuaternion( this._worldQuaternionInv );

			}

			if ( axis.indexOf( 'X' ) === - 1 ) this._offset.x = 0;
			if ( axis.indexOf( 'Y' ) === - 1 ) this._offset.y = 0;
			if ( axis.indexOf( 'Z' ) === - 1 ) this._offset.z = 0;

			if ( space === 'local' && axis !== 'XYZ' ) {

				this._offset.applyQuaternion( this._quaternionStart ).divide( this._parentScale );

			} else {

				this._offset.applyQuaternion( this._parentQuaternionInv ).divide( this._parentScale );

			}

			object.position.copy( this._offset ).add( this._positionStart );

			// Apply translation snap

			if ( this.translationSnap ) {

				if ( space === 'local' ) {

					object.position.applyQuaternion( _tempQuaternion.copy( this._quaternionStart ).invert() );

					if ( axis.search( 'X' ) !== - 1 ) {

						object.position.x = Math.round( object.position.x / this.translationSnap ) * this.translationSnap;

					}

					if ( axis.search( 'Y' ) !== - 1 ) {

						object.position.y = Math.round( object.position.y / this.translationSnap ) * this.translationSnap;

					}

					if ( axis.search( 'Z' ) !== - 1 ) {

						object.position.z = Math.round( object.position.z / this.translationSnap ) * this.translationSnap;

					}

					object.position.applyQuaternion( this._quaternionStart );

				}

				if ( space === 'world' ) {

					if ( object.parent ) {

						object.position.add( _tempVector.setFromMatrixPosition( object.parent.matrixWorld ) );

					}

					if ( axis.search( 'X' ) !== - 1 ) {

						object.position.x = Math.round( object.position.x / this.translationSnap ) * this.translationSnap;

					}

					if ( axis.search( 'Y' ) !== - 1 ) {

						object.position.y = Math.round( object.position.y / this.translationSnap ) * this.translationSnap;

					}

					if ( axis.search( 'Z' ) !== - 1 ) {

						object.position.z = Math.round( object.position.z / this.translationSnap ) * this.translationSnap;

					}

					if ( object.parent ) {

						object.position.sub( _tempVector.setFromMatrixPosition( object.parent.matrixWorld ) );

					}

				}

			}

			object.position.x = Math.max( this.minX, Math.min( this.maxX, object.position.x ) );
			object.position.y = Math.max( this.minY, Math.min( this.maxY, object.position.y ) );
			object.position.z = Math.max( this.minZ, Math.min( this.maxZ, object.position.z ) );

		} else if ( mode === 'scale' ) {

			if ( axis.search( 'XYZ' ) !== - 1 ) {

				let d = this.pointEnd.length() / this.pointStart.length();

				if ( this.pointEnd.dot( this.pointStart ) < 0 ) d *= - 1;

				_tempVector2.set( d, d, d );

			} else {

				_tempVector.copy( this.pointStart );
				_tempVector2.copy( this.pointEnd );

				_tempVector.applyQuaternion( this._worldQuaternionInv );
				_tempVector2.applyQuaternion( this._worldQuaternionInv );

				_tempVector2.divide( _tempVector );

				if ( axis.search( 'X' ) === - 1 ) {

					_tempVector2.x = 1;

				}

				if ( axis.search( 'Y' ) === - 1 ) {

					_tempVector2.y = 1;

				}

				if ( axis.search( 'Z' ) === - 1 ) {

					_tempVector2.z = 1;

				}

			}

			// Apply scale

			object.scale.copy( this._scaleStart ).multiply( _tempVector2 );

			if ( this.scaleSnap ) {

				if ( axis.search( 'X' ) !== - 1 ) {

					object.scale.x = Math.round( object.scale.x / this.scaleSnap ) * this.scaleSnap || this.scaleSnap;

				}

				if ( axis.search( 'Y' ) !== - 1 ) {

					object.scale.y = Math.round( object.scale.y / this.scaleSnap ) * this.scaleSnap || this.scaleSnap;

				}

				if ( axis.search( 'Z' ) !== - 1 ) {

					object.scale.z = Math.round( object.scale.z / this.scaleSnap ) * this.scaleSnap || this.scaleSnap;

				}

			}

		} else if ( mode === 'rotate' ) {

			this._offset.copy( this.pointEnd ).sub( this.pointStart );

			const ROTATION_SPEED = 20 / this.worldPosition.distanceTo( _tempVector.setFromMatrixPosition( this.camera.matrixWorld ) );

			let _inPlaneRotation = false;

			if ( axis === 'XYZE' ) {

				this.rotationAxis.copy( this._offset ).cross( this.eye ).normalize();
				this.rotationAngle = this._offset.dot( _tempVector.copy( this.rotationAxis ).cross( this.eye ) ) * ROTATION_SPEED;

			} else if ( axis === 'X' || axis === 'Y' || axis === 'Z' ) {

				this.rotationAxis.copy( _unit[ axis ] );

				_tempVector.copy( _unit[ axis ] );

				if ( space === 'local' ) {

					_tempVector.applyQuaternion( this.worldQuaternion );

				}

				_tempVector.cross( this.eye );

				// When _tempVector is 0 after cross with this.eye the vectors are parallel and should use in-plane rotation logic.
				if ( _tempVector.length() === 0 ) {

					_inPlaneRotation = true;

				} else {

					this.rotationAngle = this._offset.dot( _tempVector.normalize() ) * ROTATION_SPEED;

				}


			}

			if ( axis === 'E' || _inPlaneRotation ) {

				this.rotationAxis.copy( this.eye );
				this.rotationAngle = this.pointEnd.angleTo( this.pointStart );

				this._startNorm.copy( this.pointStart ).normalize();
				this._endNorm.copy( this.pointEnd ).normalize();

				this.rotationAngle *= ( this._endNorm.cross( this._startNorm ).dot( this.eye ) < 0 ? 1 : - 1 );

			}

			// Apply rotation snap

			if ( this.rotationSnap ) this.rotationAngle = Math.round( this.rotationAngle / this.rotationSnap ) * this.rotationSnap;

			// Apply rotate
			if ( space === 'local' && axis !== 'E' && axis !== 'XYZE' ) {

				object.quaternion.copy( this._quaternionStart );
				object.quaternion.multiply( _tempQuaternion.setFromAxisAngle( this.rotationAxis, this.rotationAngle ) ).normalize();

			} else {

				this.rotationAxis.applyQuaternion( this._parentQuaternionInv );
				object.quaternion.copy( _tempQuaternion.setFromAxisAngle( this.rotationAxis, this.rotationAngle ) );
				object.quaternion.multiply( this._quaternionStart ).normalize();

			}

		}

		this.dispatchEvent( _changeEvent );
		this.dispatchEvent( _objectChangeEvent );

	}
```
</details>

##### `pointerUp(pointer: any): void`

<details><summary>Code</summary>

```ts
pointerUp( pointer ) {

		if ( pointer !== null && pointer.button !== 0 ) return;

		if ( this.dragging && ( this.axis !== null ) ) {

			_mouseUpEvent.mode = this.mode;
			this.dispatchEvent( _mouseUpEvent );

		}

		this.dragging = false;
		this.axis = null;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.disconnect();

		this._root.dispose();

	}
```
</details>

##### `attach(object: Object3D): TransformControls`

<details><summary>Code</summary>

```ts
attach( object ) {

		this.object = object;
		this._root.visible = true;

		return this;

	}
```
</details>

##### `detach(): TransformControls`

<details><summary>Code</summary>

```ts
detach() {

		this.object = undefined;
		this.axis = null;

		this._root.visible = false;

		return this;

	}
```
</details>

##### `reset(): void`

<details><summary>Code</summary>

```ts
reset() {

		if ( ! this.enabled ) return;

		if ( this.dragging ) {

			this.object.position.copy( this._positionStart );
			this.object.quaternion.copy( this._quaternionStart );
			this.object.scale.copy( this._scaleStart );

			this.dispatchEvent( _changeEvent );
			this.dispatchEvent( _objectChangeEvent );

			this.pointStart.copy( this.pointEnd );

		}

	}
```
</details>

##### `getRaycaster(): Raycaster`

<details><summary>Code</summary>

```ts
getRaycaster() {

		return _raycaster;

	}
```
</details>

##### `getMode(): "translate" | "scale" | "rotate"`

<details><summary>Code</summary>

```ts
getMode() {

		return this.mode;

	}
```
</details>

##### `setMode(mode: "translate" | "scale" | "rotate"): void`

<details><summary>Code</summary>

```ts
setMode( mode ) {

		this.mode = mode;

	}
```
</details>

##### `setTranslationSnap(translationSnap: number): void`

<details><summary>Code</summary>

```ts
setTranslationSnap( translationSnap ) {

		this.translationSnap = translationSnap;

	}
```
</details>

##### `setRotationSnap(rotationSnap: number): void`

<details><summary>Code</summary>

```ts
setRotationSnap( rotationSnap ) {

		this.rotationSnap = rotationSnap;

	}
```
</details>

##### `setScaleSnap(scaleSnap: number): void`

<details><summary>Code</summary>

```ts
setScaleSnap( scaleSnap ) {

		this.scaleSnap = scaleSnap;

	}
```
</details>

##### `setSize(size: number): void`

<details><summary>Code</summary>

```ts
setSize( size ) {

		this.size = size;

	}
```
</details>

##### `setSpace(space: "local" | "world"): void`

<details><summary>Code</summary>

```ts
setSpace( space ) {

		this.space = space;

	}
```
</details>

##### `setColors(xAxis: any, yAxis: any, zAxis: any, active: any): void`

<details><summary>Code</summary>

```ts
setColors( xAxis, yAxis, zAxis, active ) {

		const materialLib = this._gizmo.materialLib;

		materialLib.xAxis.color.set( xAxis );
		materialLib.yAxis.color.set( yAxis );
		materialLib.zAxis.color.set( zAxis );
		materialLib.active.color.set( active );
		materialLib.xAxisTransparent.color.set( xAxis );
		materialLib.yAxisTransparent.color.set( yAxis );
		materialLib.zAxisTransparent.color.set( zAxis );
		materialLib.activeTransparent.color.set( active );

		// update color caches

		if ( materialLib.xAxis._color ) materialLib.xAxis._color.set( xAxis );
		if ( materialLib.yAxis._color ) materialLib.yAxis._color.set( yAxis );
		if ( materialLib.zAxis._color ) materialLib.zAxis._color.set( zAxis );
		if ( materialLib.active._color ) materialLib.active._color.set( active );
		if ( materialLib.xAxisTransparent._color ) materialLib.xAxisTransparent._color.set( xAxis );
		if ( materialLib.yAxisTransparent._color ) materialLib.yAxisTransparent._color.set( yAxis );
		if ( materialLib.zAxisTransparent._color ) materialLib.zAxisTransparent._color.set( zAxis );
		if ( materialLib.activeTransparent._color ) materialLib.activeTransparent._color.set( active );

	}
```
</details>

### `TransformControlsRoot`

<details><summary>Class Code</summary>

```ts
class TransformControlsRoot extends Object3D {

	constructor( controls ) {

		super();

		this.isTransformControlsRoot = true;

		this.controls = controls;
		this.visible = false;

	}

	// updateMatrixWorld updates key transformation variables
	updateMatrixWorld( force ) {

		const controls = this.controls;

		if ( controls.object !== undefined ) {

			controls.object.updateMatrixWorld();

			if ( controls.object.parent === null ) {

				console.error( 'TransformControls: The attached 3D object must be a part of the scene graph.' );

			} else {

				controls.object.parent.matrixWorld.decompose( controls._parentPosition, controls._parentQuaternion, controls._parentScale );

			}

			controls.object.matrixWorld.decompose( controls.worldPosition, controls.worldQuaternion, controls._worldScale );

			controls._parentQuaternionInv.copy( controls._parentQuaternion ).invert();
			controls._worldQuaternionInv.copy( controls.worldQuaternion ).invert();

		}

		controls.camera.updateMatrixWorld();
		controls.camera.matrixWorld.decompose( controls.cameraPosition, controls.cameraQuaternion, controls._cameraScale );

		if ( controls.camera.isOrthographicCamera ) {

			controls.camera.getWorldDirection( controls.eye ).negate();

		} else {

			controls.eye.copy( controls.cameraPosition ).sub( controls.worldPosition ).normalize();

		}

		super.updateMatrixWorld( force );

	}

	dispose() {

		this.traverse( function ( child ) {

			if ( child.geometry ) child.geometry.dispose();
			if ( child.material ) child.material.dispose();

		} );

	}

}
```
</details>

#### Methods

##### `updateMatrixWorld(force: any): void`

<details><summary>Code</summary>

```ts
updateMatrixWorld( force ) {

		const controls = this.controls;

		if ( controls.object !== undefined ) {

			controls.object.updateMatrixWorld();

			if ( controls.object.parent === null ) {

				console.error( 'TransformControls: The attached 3D object must be a part of the scene graph.' );

			} else {

				controls.object.parent.matrixWorld.decompose( controls._parentPosition, controls._parentQuaternion, controls._parentScale );

			}

			controls.object.matrixWorld.decompose( controls.worldPosition, controls.worldQuaternion, controls._worldScale );

			controls._parentQuaternionInv.copy( controls._parentQuaternion ).invert();
			controls._worldQuaternionInv.copy( controls.worldQuaternion ).invert();

		}

		controls.camera.updateMatrixWorld();
		controls.camera.matrixWorld.decompose( controls.cameraPosition, controls.cameraQuaternion, controls._cameraScale );

		if ( controls.camera.isOrthographicCamera ) {

			controls.camera.getWorldDirection( controls.eye ).negate();

		} else {

			controls.eye.copy( controls.cameraPosition ).sub( controls.worldPosition ).normalize();

		}

		super.updateMatrixWorld( force );

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.traverse( function ( child ) {

			if ( child.geometry ) child.geometry.dispose();
			if ( child.material ) child.material.dispose();

		} );

	}
```
</details>

### `TransformControlsGizmo`

<details><summary>Class Code</summary>

```ts
class TransformControlsGizmo extends Object3D {

	constructor() {

		super();

		this.isTransformControlsGizmo = true;

		this.type = 'TransformControlsGizmo';

		// shared materials

		const gizmoMaterial = new MeshBasicMaterial( {
			depthTest: false,
			depthWrite: false,
			fog: false,
			toneMapped: false,
			transparent: true
		} );

		const gizmoLineMaterial = new LineBasicMaterial( {
			depthTest: false,
			depthWrite: false,
			fog: false,
			toneMapped: false,
			transparent: true
		} );

		// Make unique material for each axis/color

		const matInvisible = gizmoMaterial.clone();
		matInvisible.opacity = 0.15;

		const matHelper = gizmoLineMaterial.clone();
		matHelper.opacity = 0.5;

		const matRed = gizmoMaterial.clone();
		matRed.color.setHex( 0xff0000 );

		const matGreen = gizmoMaterial.clone();
		matGreen.color.setHex( 0x00ff00 );

		const matBlue = gizmoMaterial.clone();
		matBlue.color.setHex( 0x0000ff );

		const matRedTransparent = gizmoMaterial.clone();
		matRedTransparent.color.setHex( 0xff0000 );
		matRedTransparent.opacity = 0.5;

		const matGreenTransparent = gizmoMaterial.clone();
		matGreenTransparent.color.setHex( 0x00ff00 );
		matGreenTransparent.opacity = 0.5;

		const matBlueTransparent = gizmoMaterial.clone();
		matBlueTransparent.color.setHex( 0x0000ff );
		matBlueTransparent.opacity = 0.5;

		const matWhiteTransparent = gizmoMaterial.clone();
		matWhiteTransparent.opacity = 0.25;

		const matYellowTransparent = gizmoMaterial.clone();
		matYellowTransparent.color.setHex( 0xffff00 );
		matYellowTransparent.opacity = 0.25;

		const matYellow = gizmoMaterial.clone();
		matYellow.color.setHex( 0xffff00 );

		const matGray = gizmoMaterial.clone();
		matGray.color.setHex( 0x787878 );

		// materials in the below property are configurable via setColors()

		this.materialLib = {
			xAxis: matRed,
			yAxis: matGreen,
			zAxis: matBlue,
			active: matYellow,
			xAxisTransparent: matRedTransparent,
			yAxisTransparent: matGreenTransparent,
			zAxisTransparent: matBlueTransparent,
			activeTransparent: matYellowTransparent
		};

		// reusable geometry

		const arrowGeometry = new CylinderGeometry( 0, 0.04, 0.1, 12 );
		arrowGeometry.translate( 0, 0.05, 0 );

		const scaleHandleGeometry = new BoxGeometry( 0.08, 0.08, 0.08 );
		scaleHandleGeometry.translate( 0, 0.04, 0 );

		const lineGeometry = new BufferGeometry();
		lineGeometry.setAttribute( 'position', new Float32BufferAttribute( [ 0, 0, 0,	1, 0, 0 ], 3 ) );

		const lineGeometry2 = new CylinderGeometry( 0.0075, 0.0075, 0.5, 3 );
		lineGeometry2.translate( 0, 0.25, 0 );

		function CircleGeometry( radius, arc ) {

			const geometry = new TorusGeometry( radius, 0.0075, 3, 64, arc * Math.PI * 2 );
			geometry.rotateY( Math.PI / 2 );
			geometry.rotateX( Math.PI / 2 );
			return geometry;

		}

		// Special geometry for transform helper. If scaled with position vector it spans from [0,0,0] to position

		function TranslateHelperGeometry() {

			const geometry = new BufferGeometry();

			geometry.setAttribute( 'position', new Float32BufferAttribute( [ 0, 0, 0, 1, 1, 1 ], 3 ) );

			return geometry;

		}

		// Gizmo definitions - custom hierarchy definitions for setupGizmo() function

		const gizmoTranslate = {
			X: [
				[ new Mesh( arrowGeometry, matRed ), [ 0.5, 0, 0 ], [ 0, 0, - Math.PI / 2 ]],
				[ new Mesh( arrowGeometry, matRed ), [ - 0.5, 0, 0 ], [ 0, 0, Math.PI / 2 ]],
				[ new Mesh( lineGeometry2, matRed ), [ 0, 0, 0 ], [ 0, 0, - Math.PI / 2 ]]
			],
			Y: [
				[ new Mesh( arrowGeometry, matGreen ), [ 0, 0.5, 0 ]],
				[ new Mesh( arrowGeometry, matGreen ), [ 0, - 0.5, 0 ], [ Math.PI, 0, 0 ]],
				[ new Mesh( lineGeometry2, matGreen ) ]
			],
			Z: [
				[ new Mesh( arrowGeometry, matBlue ), [ 0, 0, 0.5 ], [ Math.PI / 2, 0, 0 ]],
				[ new Mesh( arrowGeometry, matBlue ), [ 0, 0, - 0.5 ], [ - Math.PI / 2, 0, 0 ]],
				[ new Mesh( lineGeometry2, matBlue ), null, [ Math.PI / 2, 0, 0 ]]
			],
			XYZ: [
				[ new Mesh( new OctahedronGeometry( 0.1, 0 ), matWhiteTransparent ), [ 0, 0, 0 ]]
			],
			XY: [
				[ new Mesh( new BoxGeometry( 0.15, 0.15, 0.01 ), matBlueTransparent ), [ 0.15, 0.15, 0 ]]
			],
			YZ: [
				[ new Mesh( new BoxGeometry( 0.15, 0.15, 0.01 ), matRedTransparent ), [ 0, 0.15, 0.15 ], [ 0, Math.PI / 2, 0 ]]
			],
			XZ: [
				[ new Mesh( new BoxGeometry( 0.15, 0.15, 0.01 ), matGreenTransparent ), [ 0.15, 0, 0.15 ], [ - Math.PI / 2, 0, 0 ]]
			]
		};

		const pickerTranslate = {
			X: [
				[ new Mesh( new CylinderGeometry( 0.2, 0, 0.6, 4 ), matInvisible ), [ 0.3, 0, 0 ], [ 0, 0, - Math.PI / 2 ]],
				[ new Mesh( new CylinderGeometry( 0.2, 0, 0.6, 4 ), matInvisible ), [ - 0.3, 0, 0 ], [ 0, 0, Math.PI / 2 ]]
			],
			Y: [
				[ new Mesh( new CylinderGeometry( 0.2, 0, 0.6, 4 ), matInvisible ), [ 0, 0.3, 0 ]],
				[ new Mesh( new CylinderGeometry( 0.2, 0, 0.6, 4 ), matInvisible ), [ 0, - 0.3, 0 ], [ 0, 0, Math.PI ]]
			],
			Z: [
				[ new Mesh( new CylinderGeometry( 0.2, 0, 0.6, 4 ), matInvisible ), [ 0, 0, 0.3 ], [ Math.PI / 2, 0, 0 ]],
				[ new Mesh( new CylinderGeometry( 0.2, 0, 0.6, 4 ), matInvisible ), [ 0, 0, - 0.3 ], [ - Math.PI / 2, 0, 0 ]]
			],
			XYZ: [
				[ new Mesh( new OctahedronGeometry( 0.2, 0 ), matInvisible ) ]
			],
			XY: [
				[ new Mesh( new BoxGeometry( 0.2, 0.2, 0.01 ), matInvisible ), [ 0.15, 0.15, 0 ]]
			],
			YZ: [
				[ new Mesh( new BoxGeometry( 0.2, 0.2, 0.01 ), matInvisible ), [ 0, 0.15, 0.15 ], [ 0, Math.PI / 2, 0 ]]
			],
			XZ: [
				[ new Mesh( new BoxGeometry( 0.2, 0.2, 0.01 ), matInvisible ), [ 0.15, 0, 0.15 ], [ - Math.PI / 2, 0, 0 ]]
			]
		};

		const helperTranslate = {
			START: [
				[ new Mesh( new OctahedronGeometry( 0.01, 2 ), matHelper ), null, null, null, 'helper' ]
			],
			END: [
				[ new Mesh( new OctahedronGeometry( 0.01, 2 ), matHelper ), null, null, null, 'helper' ]
			],
			DELTA: [
				[ new Line( TranslateHelperGeometry(), matHelper ), null, null, null, 'helper' ]
			],
			X: [
				[ new Line( lineGeometry, matHelper ), [ - 1e3, 0, 0 ], null, [ 1e6, 1, 1 ], 'helper' ]
			],
			Y: [
				[ new Line( lineGeometry, matHelper ), [ 0, - 1e3, 0 ], [ 0, 0, Math.PI / 2 ], [ 1e6, 1, 1 ], 'helper' ]
			],
			Z: [
				[ new Line( lineGeometry, matHelper ), [ 0, 0, - 1e3 ], [ 0, - Math.PI / 2, 0 ], [ 1e6, 1, 1 ], 'helper' ]
			]
		};

		const gizmoRotate = {
			XYZE: [
				[ new Mesh( CircleGeometry( 0.5, 1 ), matGray ), null, [ 0, Math.PI / 2, 0 ]]
			],
			X: [
				[ new Mesh( CircleGeometry( 0.5, 0.5 ), matRed ) ]
			],
			Y: [
				[ new Mesh( CircleGeometry( 0.5, 0.5 ), matGreen ), null, [ 0, 0, - Math.PI / 2 ]]
			],
			Z: [
				[ new Mesh( CircleGeometry( 0.5, 0.5 ), matBlue ), null, [ 0, Math.PI / 2, 0 ]]
			],
			E: [
				[ new Mesh( CircleGeometry( 0.75, 1 ), matYellowTransparent ), null, [ 0, Math.PI / 2, 0 ]]
			]
		};

		const helperRotate = {
			AXIS: [
				[ new Line( lineGeometry, matHelper ), [ - 1e3, 0, 0 ], null, [ 1e6, 1, 1 ], 'helper' ]
			]
		};

		const pickerRotate = {
			XYZE: [
				[ new Mesh( new SphereGeometry( 0.25, 10, 8 ), matInvisible ) ]
			],
			X: [
				[ new Mesh( new TorusGeometry( 0.5, 0.1, 4, 24 ), matInvisible ), [ 0, 0, 0 ], [ 0, - Math.PI / 2, - Math.PI / 2 ]],
			],
			Y: [
				[ new Mesh( new TorusGeometry( 0.5, 0.1, 4, 24 ), matInvisible ), [ 0, 0, 0 ], [ Math.PI / 2, 0, 0 ]],
			],
			Z: [
				[ new Mesh( new TorusGeometry( 0.5, 0.1, 4, 24 ), matInvisible ), [ 0, 0, 0 ], [ 0, 0, - Math.PI / 2 ]],
			],
			E: [
				[ new Mesh( new TorusGeometry( 0.75, 0.1, 2, 24 ), matInvisible ) ]
			]
		};

		const gizmoScale = {
			X: [
				[ new Mesh( scaleHandleGeometry, matRed ), [ 0.5, 0, 0 ], [ 0, 0, - Math.PI / 2 ]],
				[ new Mesh( lineGeometry2, matRed ), [ 0, 0, 0 ], [ 0, 0, - Math.PI / 2 ]],
				[ new Mesh( scaleHandleGeometry, matRed ), [ - 0.5, 0, 0 ], [ 0, 0, Math.PI / 2 ]],
			],
			Y: [
				[ new Mesh( scaleHandleGeometry, matGreen ), [ 0, 0.5, 0 ]],
				[ new Mesh( lineGeometry2, matGreen ) ],
				[ new Mesh( scaleHandleGeometry, matGreen ), [ 0, - 0.5, 0 ], [ 0, 0, Math.PI ]],
			],
			Z: [
				[ new Mesh( scaleHandleGeometry, matBlue ), [ 0, 0, 0.5 ], [ Math.PI / 2, 0, 0 ]],
				[ new Mesh( lineGeometry2, matBlue ), [ 0, 0, 0 ], [ Math.PI / 2, 0, 0 ]],
				[ new Mesh( scaleHandleGeometry, matBlue ), [ 0, 0, - 0.5 ], [ - Math.PI / 2, 0, 0 ]]
			],
			XY: [
				[ new Mesh( new BoxGeometry( 0.15, 0.15, 0.01 ), matBlueTransparent ), [ 0.15, 0.15, 0 ]]
			],
			YZ: [
				[ new Mesh( new BoxGeometry( 0.15, 0.15, 0.01 ), matRedTransparent ), [ 0, 0.15, 0.15 ], [ 0, Math.PI / 2, 0 ]]
			],
			XZ: [
				[ new Mesh( new BoxGeometry( 0.15, 0.15, 0.01 ), matGreenTransparent ), [ 0.15, 0, 0.15 ], [ - Math.PI / 2, 0, 0 ]]
			],
			XYZ: [
				[ new Mesh( new BoxGeometry( 0.1, 0.1, 0.1 ), matWhiteTransparent ) ],
			]
		};

		const pickerScale = {
			X: [
				[ new Mesh( new CylinderGeometry( 0.2, 0, 0.6, 4 ), matInvisible ), [ 0.3, 0, 0 ], [ 0, 0, - Math.PI / 2 ]],
				[ new Mesh( new CylinderGeometry( 0.2, 0, 0.6, 4 ), matInvisible ), [ - 0.3, 0, 0 ], [ 0, 0, Math.PI / 2 ]]
			],
			Y: [
				[ new Mesh( new CylinderGeometry( 0.2, 0, 0.6, 4 ), matInvisible ), [ 0, 0.3, 0 ]],
				[ new Mesh( new CylinderGeometry( 0.2, 0, 0.6, 4 ), matInvisible ), [ 0, - 0.3, 0 ], [ 0, 0, Math.PI ]]
			],
			Z: [
				[ new Mesh( new CylinderGeometry( 0.2, 0, 0.6, 4 ), matInvisible ), [ 0, 0, 0.3 ], [ Math.PI / 2, 0, 0 ]],
				[ new Mesh( new CylinderGeometry( 0.2, 0, 0.6, 4 ), matInvisible ), [ 0, 0, - 0.3 ], [ - Math.PI / 2, 0, 0 ]]
			],
			XY: [
				[ new Mesh( new BoxGeometry( 0.2, 0.2, 0.01 ), matInvisible ), [ 0.15, 0.15, 0 ]],
			],
			YZ: [
				[ new Mesh( new BoxGeometry( 0.2, 0.2, 0.01 ), matInvisible ), [ 0, 0.15, 0.15 ], [ 0, Math.PI / 2, 0 ]],
			],
			XZ: [
				[ new Mesh( new BoxGeometry( 0.2, 0.2, 0.01 ), matInvisible ), [ 0.15, 0, 0.15 ], [ - Math.PI / 2, 0, 0 ]],
			],
			XYZ: [
				[ new Mesh( new BoxGeometry( 0.2, 0.2, 0.2 ), matInvisible ), [ 0, 0, 0 ]],
			]
		};

		const helperScale = {
			X: [
				[ new Line( lineGeometry, matHelper ), [ - 1e3, 0, 0 ], null, [ 1e6, 1, 1 ], 'helper' ]
			],
			Y: [
				[ new Line( lineGeometry, matHelper ), [ 0, - 1e3, 0 ], [ 0, 0, Math.PI / 2 ], [ 1e6, 1, 1 ], 'helper' ]
			],
			Z: [
				[ new Line( lineGeometry, matHelper ), [ 0, 0, - 1e3 ], [ 0, - Math.PI / 2, 0 ], [ 1e6, 1, 1 ], 'helper' ]
			]
		};

		// Creates an Object3D with gizmos described in custom hierarchy definition.

		function setupGizmo( gizmoMap ) {

			const gizmo = new Object3D();

			for ( const name in gizmoMap ) {

				for ( let i = gizmoMap[ name ].length; i --; ) {

					const object = gizmoMap[ name ][ i ][ 0 ].clone();
					const position = gizmoMap[ name ][ i ][ 1 ];
					const rotation = gizmoMap[ name ][ i ][ 2 ];
					const scale = gizmoMap[ name ][ i ][ 3 ];
					const tag = gizmoMap[ name ][ i ][ 4 ];

					// name and tag properties are essential for picking and updating logic.
					object.name = name;
					object.tag = tag;

					if ( position ) {

						object.position.set( position[ 0 ], position[ 1 ], position[ 2 ] );

					}

					if ( rotation ) {

						object.rotation.set( rotation[ 0 ], rotation[ 1 ], rotation[ 2 ] );

					}

					if ( scale ) {

						object.scale.set( scale[ 0 ], scale[ 1 ], scale[ 2 ] );

					}

					object.updateMatrix();

					const tempGeometry = object.geometry.clone();
					tempGeometry.applyMatrix4( object.matrix );
					object.geometry = tempGeometry;
					object.renderOrder = Infinity;

					object.position.set( 0, 0, 0 );
					object.rotation.set( 0, 0, 0 );
					object.scale.set( 1, 1, 1 );

					gizmo.add( object );

				}

			}

			return gizmo;

		}

		// Gizmo creation

		this.gizmo = {};
		this.picker = {};
		this.helper = {};

		this.add( this.gizmo[ 'translate' ] = setupGizmo( gizmoTranslate ) );
		this.add( this.gizmo[ 'rotate' ] = setupGizmo( gizmoRotate ) );
		this.add( this.gizmo[ 'scale' ] = setupGizmo( gizmoScale ) );
		this.add( this.picker[ 'translate' ] = setupGizmo( pickerTranslate ) );
		this.add( this.picker[ 'rotate' ] = setupGizmo( pickerRotate ) );
		this.add( this.picker[ 'scale' ] = setupGizmo( pickerScale ) );
		this.add( this.helper[ 'translate' ] = setupGizmo( helperTranslate ) );
		this.add( this.helper[ 'rotate' ] = setupGizmo( helperRotate ) );
		this.add( this.helper[ 'scale' ] = setupGizmo( helperScale ) );

		// Pickers should be hidden always

		this.picker[ 'translate' ].visible = false;
		this.picker[ 'rotate' ].visible = false;
		this.picker[ 'scale' ].visible = false;

	}

	// updateMatrixWorld will update transformations and appearance of individual handles

	updateMatrixWorld( force ) {

		const space = ( this.mode === 'scale' ) ? 'local' : this.space; // scale always oriented to local rotation

		const quaternion = ( space === 'local' ) ? this.worldQuaternion : _identityQuaternion;

		// Show only gizmos for current transform mode

		this.gizmo[ 'translate' ].visible = this.mode === 'translate';
		this.gizmo[ 'rotate' ].visible = this.mode === 'rotate';
		this.gizmo[ 'scale' ].visible = this.mode === 'scale';

		this.helper[ 'translate' ].visible = this.mode === 'translate';
		this.helper[ 'rotate' ].visible = this.mode === 'rotate';
		this.helper[ 'scale' ].visible = this.mode === 'scale';


		let handles = [];
		handles = handles.concat( this.picker[ this.mode ].children );
		handles = handles.concat( this.gizmo[ this.mode ].children );
		handles = handles.concat( this.helper[ this.mode ].children );

		for ( let i = 0; i < handles.length; i ++ ) {

			const handle = handles[ i ];

			// hide aligned to camera

			handle.visible = true;
			handle.rotation.set( 0, 0, 0 );
			handle.position.copy( this.worldPosition );

			let factor;

			if ( this.camera.isOrthographicCamera ) {

				factor = ( this.camera.top - this.camera.bottom ) / this.camera.zoom;

			} else {

				factor = this.worldPosition.distanceTo( this.cameraPosition ) * Math.min( 1.9 * Math.tan( Math.PI * this.camera.fov / 360 ) / this.camera.zoom, 7 );

			}

			handle.scale.set( 1, 1, 1 ).multiplyScalar( factor * this.size / 4 );

			// TODO: simplify helpers and consider decoupling from gizmo

			if ( handle.tag === 'helper' ) {

				handle.visible = false;

				if ( handle.name === 'AXIS' ) {

					handle.visible = !! this.axis;

					if ( this.axis === 'X' ) {

						_tempQuaternion.setFromEuler( _tempEuler.set( 0, 0, 0 ) );
						handle.quaternion.copy( quaternion ).multiply( _tempQuaternion );

						if ( Math.abs( _alignVector.copy( _unitX ).applyQuaternion( quaternion ).dot( this.eye ) ) > 0.9 ) {

							handle.visible = false;

						}

					}

					if ( this.axis === 'Y' ) {

						_tempQuaternion.setFromEuler( _tempEuler.set( 0, 0, Math.PI / 2 ) );
						handle.quaternion.copy( quaternion ).multiply( _tempQuaternion );

						if ( Math.abs( _alignVector.copy( _unitY ).applyQuaternion( quaternion ).dot( this.eye ) ) > 0.9 ) {

							handle.visible = false;

						}

					}

					if ( this.axis === 'Z' ) {

						_tempQuaternion.setFromEuler( _tempEuler.set( 0, Math.PI / 2, 0 ) );
						handle.quaternion.copy( quaternion ).multiply( _tempQuaternion );

						if ( Math.abs( _alignVector.copy( _unitZ ).applyQuaternion( quaternion ).dot( this.eye ) ) > 0.9 ) {

							handle.visible = false;

						}

					}

					if ( this.axis === 'XYZE' ) {

						_tempQuaternion.setFromEuler( _tempEuler.set( 0, Math.PI / 2, 0 ) );
						_alignVector.copy( this.rotationAxis );
						handle.quaternion.setFromRotationMatrix( _lookAtMatrix.lookAt( _zeroVector, _alignVector, _unitY ) );
						handle.quaternion.multiply( _tempQuaternion );
						handle.visible = this.dragging;

					}

					if ( this.axis === 'E' ) {

						handle.visible = false;

					}


				} else if ( handle.name === 'START' ) {

					handle.position.copy( this.worldPositionStart );
					handle.visible = this.dragging;

				} else if ( handle.name === 'END' ) {

					handle.position.copy( this.worldPosition );
					handle.visible = this.dragging;

				} else if ( handle.name === 'DELTA' ) {

					handle.position.copy( this.worldPositionStart );
					handle.quaternion.copy( this.worldQuaternionStart );
					_tempVector.set( 1e-10, 1e-10, 1e-10 ).add( this.worldPositionStart ).sub( this.worldPosition ).multiplyScalar( - 1 );
					_tempVector.applyQuaternion( this.worldQuaternionStart.clone().invert() );
					handle.scale.copy( _tempVector );
					handle.visible = this.dragging;

				} else {

					handle.quaternion.copy( quaternion );

					if ( this.dragging ) {

						handle.position.copy( this.worldPositionStart );

					} else {

						handle.position.copy( this.worldPosition );

					}

					if ( this.axis ) {

						handle.visible = this.axis.search( handle.name ) !== - 1;

					}

				}

				// If updating helper, skip rest of the loop
				continue;

			}

			// Align handles to current local or world rotation

			handle.quaternion.copy( quaternion );

			if ( this.mode === 'translate' || this.mode === 'scale' ) {

				// Hide translate and scale axis facing the camera

				const AXIS_HIDE_THRESHOLD = 0.99;
				const PLANE_HIDE_THRESHOLD = 0.2;

				if ( handle.name === 'X' ) {

					if ( Math.abs( _alignVector.copy( _unitX ).applyQuaternion( quaternion ).dot( this.eye ) ) > AXIS_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

				if ( handle.name === 'Y' ) {

					if ( Math.abs( _alignVector.copy( _unitY ).applyQuaternion( quaternion ).dot( this.eye ) ) > AXIS_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

				if ( handle.name === 'Z' ) {

					if ( Math.abs( _alignVector.copy( _unitZ ).applyQuaternion( quaternion ).dot( this.eye ) ) > AXIS_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

				if ( handle.name === 'XY' ) {

					if ( Math.abs( _alignVector.copy( _unitZ ).applyQuaternion( quaternion ).dot( this.eye ) ) < PLANE_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

				if ( handle.name === 'YZ' ) {

					if ( Math.abs( _alignVector.copy( _unitX ).applyQuaternion( quaternion ).dot( this.eye ) ) < PLANE_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

				if ( handle.name === 'XZ' ) {

					if ( Math.abs( _alignVector.copy( _unitY ).applyQuaternion( quaternion ).dot( this.eye ) ) < PLANE_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

			} else if ( this.mode === 'rotate' ) {

				// Align handles to current local or world rotation

				_tempQuaternion2.copy( quaternion );
				_alignVector.copy( this.eye ).applyQuaternion( _tempQuaternion.copy( quaternion ).invert() );

				if ( handle.name.search( 'E' ) !== - 1 ) {

					handle.quaternion.setFromRotationMatrix( _lookAtMatrix.lookAt( this.eye, _zeroVector, _unitY ) );

				}

				if ( handle.name === 'X' ) {

					_tempQuaternion.setFromAxisAngle( _unitX, Math.atan2( - _alignVector.y, _alignVector.z ) );
					_tempQuaternion.multiplyQuaternions( _tempQuaternion2, _tempQuaternion );
					handle.quaternion.copy( _tempQuaternion );

				}

				if ( handle.name === 'Y' ) {

					_tempQuaternion.setFromAxisAngle( _unitY, Math.atan2( _alignVector.x, _alignVector.z ) );
					_tempQuaternion.multiplyQuaternions( _tempQuaternion2, _tempQuaternion );
					handle.quaternion.copy( _tempQuaternion );

				}

				if ( handle.name === 'Z' ) {

					_tempQuaternion.setFromAxisAngle( _unitZ, Math.atan2( _alignVector.y, _alignVector.x ) );
					_tempQuaternion.multiplyQuaternions( _tempQuaternion2, _tempQuaternion );
					handle.quaternion.copy( _tempQuaternion );

				}

			}

			// Hide disabled axes
			handle.visible = handle.visible && ( handle.name.indexOf( 'X' ) === - 1 || this.showX );
			handle.visible = handle.visible && ( handle.name.indexOf( 'Y' ) === - 1 || this.showY );
			handle.visible = handle.visible && ( handle.name.indexOf( 'Z' ) === - 1 || this.showZ );
			handle.visible = handle.visible && ( handle.name.indexOf( 'E' ) === - 1 || ( this.showX && this.showY && this.showZ ) );

			// highlight selected axis

			handle.material._color = handle.material._color || handle.material.color.clone();
			handle.material._opacity = handle.material._opacity || handle.material.opacity;

			handle.material.color.copy( handle.material._color );
			handle.material.opacity = handle.material._opacity;

			if ( this.enabled && this.axis ) {

				if ( handle.name === this.axis ) {

					handle.material.color.copy( this.materialLib.active.color );
					handle.material.opacity = 1.0;

				} else if ( this.axis.split( '' ).some( function ( a ) {

					return handle.name === a;

				} ) ) {

					handle.material.color.copy( this.materialLib.active.color );
					handle.material.opacity = 1.0;

				}

			}

		}

		super.updateMatrixWorld( force );

	}

}
```
</details>

#### Methods

##### `updateMatrixWorld(force: any): void`

<details><summary>Code</summary>

```ts
updateMatrixWorld( force ) {

		const space = ( this.mode === 'scale' ) ? 'local' : this.space; // scale always oriented to local rotation

		const quaternion = ( space === 'local' ) ? this.worldQuaternion : _identityQuaternion;

		// Show only gizmos for current transform mode

		this.gizmo[ 'translate' ].visible = this.mode === 'translate';
		this.gizmo[ 'rotate' ].visible = this.mode === 'rotate';
		this.gizmo[ 'scale' ].visible = this.mode === 'scale';

		this.helper[ 'translate' ].visible = this.mode === 'translate';
		this.helper[ 'rotate' ].visible = this.mode === 'rotate';
		this.helper[ 'scale' ].visible = this.mode === 'scale';


		let handles = [];
		handles = handles.concat( this.picker[ this.mode ].children );
		handles = handles.concat( this.gizmo[ this.mode ].children );
		handles = handles.concat( this.helper[ this.mode ].children );

		for ( let i = 0; i < handles.length; i ++ ) {

			const handle = handles[ i ];

			// hide aligned to camera

			handle.visible = true;
			handle.rotation.set( 0, 0, 0 );
			handle.position.copy( this.worldPosition );

			let factor;

			if ( this.camera.isOrthographicCamera ) {

				factor = ( this.camera.top - this.camera.bottom ) / this.camera.zoom;

			} else {

				factor = this.worldPosition.distanceTo( this.cameraPosition ) * Math.min( 1.9 * Math.tan( Math.PI * this.camera.fov / 360 ) / this.camera.zoom, 7 );

			}

			handle.scale.set( 1, 1, 1 ).multiplyScalar( factor * this.size / 4 );

			// TODO: simplify helpers and consider decoupling from gizmo

			if ( handle.tag === 'helper' ) {

				handle.visible = false;

				if ( handle.name === 'AXIS' ) {

					handle.visible = !! this.axis;

					if ( this.axis === 'X' ) {

						_tempQuaternion.setFromEuler( _tempEuler.set( 0, 0, 0 ) );
						handle.quaternion.copy( quaternion ).multiply( _tempQuaternion );

						if ( Math.abs( _alignVector.copy( _unitX ).applyQuaternion( quaternion ).dot( this.eye ) ) > 0.9 ) {

							handle.visible = false;

						}

					}

					if ( this.axis === 'Y' ) {

						_tempQuaternion.setFromEuler( _tempEuler.set( 0, 0, Math.PI / 2 ) );
						handle.quaternion.copy( quaternion ).multiply( _tempQuaternion );

						if ( Math.abs( _alignVector.copy( _unitY ).applyQuaternion( quaternion ).dot( this.eye ) ) > 0.9 ) {

							handle.visible = false;

						}

					}

					if ( this.axis === 'Z' ) {

						_tempQuaternion.setFromEuler( _tempEuler.set( 0, Math.PI / 2, 0 ) );
						handle.quaternion.copy( quaternion ).multiply( _tempQuaternion );

						if ( Math.abs( _alignVector.copy( _unitZ ).applyQuaternion( quaternion ).dot( this.eye ) ) > 0.9 ) {

							handle.visible = false;

						}

					}

					if ( this.axis === 'XYZE' ) {

						_tempQuaternion.setFromEuler( _tempEuler.set( 0, Math.PI / 2, 0 ) );
						_alignVector.copy( this.rotationAxis );
						handle.quaternion.setFromRotationMatrix( _lookAtMatrix.lookAt( _zeroVector, _alignVector, _unitY ) );
						handle.quaternion.multiply( _tempQuaternion );
						handle.visible = this.dragging;

					}

					if ( this.axis === 'E' ) {

						handle.visible = false;

					}


				} else if ( handle.name === 'START' ) {

					handle.position.copy( this.worldPositionStart );
					handle.visible = this.dragging;

				} else if ( handle.name === 'END' ) {

					handle.position.copy( this.worldPosition );
					handle.visible = this.dragging;

				} else if ( handle.name === 'DELTA' ) {

					handle.position.copy( this.worldPositionStart );
					handle.quaternion.copy( this.worldQuaternionStart );
					_tempVector.set( 1e-10, 1e-10, 1e-10 ).add( this.worldPositionStart ).sub( this.worldPosition ).multiplyScalar( - 1 );
					_tempVector.applyQuaternion( this.worldQuaternionStart.clone().invert() );
					handle.scale.copy( _tempVector );
					handle.visible = this.dragging;

				} else {

					handle.quaternion.copy( quaternion );

					if ( this.dragging ) {

						handle.position.copy( this.worldPositionStart );

					} else {

						handle.position.copy( this.worldPosition );

					}

					if ( this.axis ) {

						handle.visible = this.axis.search( handle.name ) !== - 1;

					}

				}

				// If updating helper, skip rest of the loop
				continue;

			}

			// Align handles to current local or world rotation

			handle.quaternion.copy( quaternion );

			if ( this.mode === 'translate' || this.mode === 'scale' ) {

				// Hide translate and scale axis facing the camera

				const AXIS_HIDE_THRESHOLD = 0.99;
				const PLANE_HIDE_THRESHOLD = 0.2;

				if ( handle.name === 'X' ) {

					if ( Math.abs( _alignVector.copy( _unitX ).applyQuaternion( quaternion ).dot( this.eye ) ) > AXIS_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

				if ( handle.name === 'Y' ) {

					if ( Math.abs( _alignVector.copy( _unitY ).applyQuaternion( quaternion ).dot( this.eye ) ) > AXIS_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

				if ( handle.name === 'Z' ) {

					if ( Math.abs( _alignVector.copy( _unitZ ).applyQuaternion( quaternion ).dot( this.eye ) ) > AXIS_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

				if ( handle.name === 'XY' ) {

					if ( Math.abs( _alignVector.copy( _unitZ ).applyQuaternion( quaternion ).dot( this.eye ) ) < PLANE_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

				if ( handle.name === 'YZ' ) {

					if ( Math.abs( _alignVector.copy( _unitX ).applyQuaternion( quaternion ).dot( this.eye ) ) < PLANE_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

				if ( handle.name === 'XZ' ) {

					if ( Math.abs( _alignVector.copy( _unitY ).applyQuaternion( quaternion ).dot( this.eye ) ) < PLANE_HIDE_THRESHOLD ) {

						handle.scale.set( 1e-10, 1e-10, 1e-10 );
						handle.visible = false;

					}

				}

			} else if ( this.mode === 'rotate' ) {

				// Align handles to current local or world rotation

				_tempQuaternion2.copy( quaternion );
				_alignVector.copy( this.eye ).applyQuaternion( _tempQuaternion.copy( quaternion ).invert() );

				if ( handle.name.search( 'E' ) !== - 1 ) {

					handle.quaternion.setFromRotationMatrix( _lookAtMatrix.lookAt( this.eye, _zeroVector, _unitY ) );

				}

				if ( handle.name === 'X' ) {

					_tempQuaternion.setFromAxisAngle( _unitX, Math.atan2( - _alignVector.y, _alignVector.z ) );
					_tempQuaternion.multiplyQuaternions( _tempQuaternion2, _tempQuaternion );
					handle.quaternion.copy( _tempQuaternion );

				}

				if ( handle.name === 'Y' ) {

					_tempQuaternion.setFromAxisAngle( _unitY, Math.atan2( _alignVector.x, _alignVector.z ) );
					_tempQuaternion.multiplyQuaternions( _tempQuaternion2, _tempQuaternion );
					handle.quaternion.copy( _tempQuaternion );

				}

				if ( handle.name === 'Z' ) {

					_tempQuaternion.setFromAxisAngle( _unitZ, Math.atan2( _alignVector.y, _alignVector.x ) );
					_tempQuaternion.multiplyQuaternions( _tempQuaternion2, _tempQuaternion );
					handle.quaternion.copy( _tempQuaternion );

				}

			}

			// Hide disabled axes
			handle.visible = handle.visible && ( handle.name.indexOf( 'X' ) === - 1 || this.showX );
			handle.visible = handle.visible && ( handle.name.indexOf( 'Y' ) === - 1 || this.showY );
			handle.visible = handle.visible && ( handle.name.indexOf( 'Z' ) === - 1 || this.showZ );
			handle.visible = handle.visible && ( handle.name.indexOf( 'E' ) === - 1 || ( this.showX && this.showY && this.showZ ) );

			// highlight selected axis

			handle.material._color = handle.material._color || handle.material.color.clone();
			handle.material._opacity = handle.material._opacity || handle.material.opacity;

			handle.material.color.copy( handle.material._color );
			handle.material.opacity = handle.material._opacity;

			if ( this.enabled && this.axis ) {

				if ( handle.name === this.axis ) {

					handle.material.color.copy( this.materialLib.active.color );
					handle.material.opacity = 1.0;

				} else if ( this.axis.split( '' ).some( function ( a ) {

					return handle.name === a;

				} ) ) {

					handle.material.color.copy( this.materialLib.active.color );
					handle.material.opacity = 1.0;

				}

			}

		}

		super.updateMatrixWorld( force );

	}
```
</details>

### `TransformControlsPlane`

<details><summary>Class Code</summary>

```ts
class TransformControlsPlane extends Mesh {

	constructor() {

		super(
			new PlaneGeometry( 100000, 100000, 2, 2 ),
			new MeshBasicMaterial( { visible: false, wireframe: true, side: DoubleSide, transparent: true, opacity: 0.1, toneMapped: false } )
		);

		this.isTransformControlsPlane = true;

		this.type = 'TransformControlsPlane';

	}

	updateMatrixWorld( force ) {

		let space = this.space;

		this.position.copy( this.worldPosition );

		if ( this.mode === 'scale' ) space = 'local'; // scale always oriented to local rotation

		_v1.copy( _unitX ).applyQuaternion( space === 'local' ? this.worldQuaternion : _identityQuaternion );
		_v2.copy( _unitY ).applyQuaternion( space === 'local' ? this.worldQuaternion : _identityQuaternion );
		_v3.copy( _unitZ ).applyQuaternion( space === 'local' ? this.worldQuaternion : _identityQuaternion );

		// Align the plane for current transform mode, axis and space.

		_alignVector.copy( _v2 );

		switch ( this.mode ) {

			case 'translate':
			case 'scale':
				switch ( this.axis ) {

					case 'X':
						_alignVector.copy( this.eye ).cross( _v1 );
						_dirVector.copy( _v1 ).cross( _alignVector );
						break;
					case 'Y':
						_alignVector.copy( this.eye ).cross( _v2 );
						_dirVector.copy( _v2 ).cross( _alignVector );
						break;
					case 'Z':
						_alignVector.copy( this.eye ).cross( _v3 );
						_dirVector.copy( _v3 ).cross( _alignVector );
						break;
					case 'XY':
						_dirVector.copy( _v3 );
						break;
					case 'YZ':
						_dirVector.copy( _v1 );
						break;
					case 'XZ':
						_alignVector.copy( _v3 );
						_dirVector.copy( _v2 );
						break;
					case 'XYZ':
					case 'E':
						_dirVector.set( 0, 0, 0 );
						break;

				}

				break;
			case 'rotate':
			default:
				// special case for rotate
				_dirVector.set( 0, 0, 0 );

		}

		if ( _dirVector.length() === 0 ) {

			// If in rotate mode, make the plane parallel to camera
			this.quaternion.copy( this.cameraQuaternion );

		} else {

			_tempMatrix.lookAt( _tempVector.set( 0, 0, 0 ), _dirVector, _alignVector );

			this.quaternion.setFromRotationMatrix( _tempMatrix );

		}

		super.updateMatrixWorld( force );

	}

}
```
</details>

#### Methods

##### `updateMatrixWorld(force: any): void`

<details><summary>Code</summary>

```ts
updateMatrixWorld( force ) {

		let space = this.space;

		this.position.copy( this.worldPosition );

		if ( this.mode === 'scale' ) space = 'local'; // scale always oriented to local rotation

		_v1.copy( _unitX ).applyQuaternion( space === 'local' ? this.worldQuaternion : _identityQuaternion );
		_v2.copy( _unitY ).applyQuaternion( space === 'local' ? this.worldQuaternion : _identityQuaternion );
		_v3.copy( _unitZ ).applyQuaternion( space === 'local' ? this.worldQuaternion : _identityQuaternion );

		// Align the plane for current transform mode, axis and space.

		_alignVector.copy( _v2 );

		switch ( this.mode ) {

			case 'translate':
			case 'scale':
				switch ( this.axis ) {

					case 'X':
						_alignVector.copy( this.eye ).cross( _v1 );
						_dirVector.copy( _v1 ).cross( _alignVector );
						break;
					case 'Y':
						_alignVector.copy( this.eye ).cross( _v2 );
						_dirVector.copy( _v2 ).cross( _alignVector );
						break;
					case 'Z':
						_alignVector.copy( this.eye ).cross( _v3 );
						_dirVector.copy( _v3 ).cross( _alignVector );
						break;
					case 'XY':
						_dirVector.copy( _v3 );
						break;
					case 'YZ':
						_dirVector.copy( _v1 );
						break;
					case 'XZ':
						_alignVector.copy( _v3 );
						_dirVector.copy( _v2 );
						break;
					case 'XYZ':
					case 'E':
						_dirVector.set( 0, 0, 0 );
						break;

				}

				break;
			case 'rotate':
			default:
				// special case for rotate
				_dirVector.set( 0, 0, 0 );

		}

		if ( _dirVector.length() === 0 ) {

			// If in rotate mode, make the plane parallel to camera
			this.quaternion.copy( this.cameraQuaternion );

		} else {

			_tempMatrix.lookAt( _tempVector.set( 0, 0, 0 ), _dirVector, _alignVector );

			this.quaternion.setFromRotationMatrix( _tempMatrix );

		}

		super.updateMatrixWorld( force );

	}
```
</details>


---