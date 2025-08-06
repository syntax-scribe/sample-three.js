[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `DragControls.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 15 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 22 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/controls/DragControls.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Controls` | `three` |
| `Matrix4` | `three` |
| `Plane` | `three` |
| `Raycaster` | `three` |
| `Vector2` | `three` |
| `Vector3` | `three` |
| `MOUSE` | `three` |
| `TOUCH` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_plane` | `any` | let/var | `new Plane()` | ✗ |
| `_pointer` | `any` | let/var | `new Vector2()` | ✗ |
| `_offset` | `any` | let/var | `new Vector3()` | ✗ |
| `_diff` | `any` | let/var | `new Vector2()` | ✗ |
| `_previousPointer` | `any` | let/var | `new Vector2()` | ✗ |
| `_intersection` | `any` | let/var | `new Vector3()` | ✗ |
| `_worldPosition` | `any` | let/var | `new Vector3()` | ✗ |
| `_inverseMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `_up` | `any` | let/var | `new Vector3()` | ✗ |
| `_right` | `any` | let/var | `new Vector3()` | ✗ |
| `_selected` | `any` | let/var | `null` | ✗ |
| `_hovered` | `any` | let/var | `null` | ✗ |
| `_intersections` | `any[]` | let/var | `[]` | ✗ |
| `STATE` | `{ NONE: number; PAN: number; ROTATE: ...` | let/var | `{ NONE: - 1, PAN: 0, ROTATE: 1 }` | ✗ |
| `action` | `any` | let/var | `*not shown*` | ✗ |
| `camera` | `any` | let/var | `this.object` | ✗ |
| `domElement` | `any` | let/var | `this.domElement` | ✗ |
| `raycaster` | `any` | let/var | `this.raycaster` | ✗ |
| `object` | `any` | let/var | `_intersections[ 0 ].object` | ✗ |
| `camera` | `any` | let/var | `this.object` | ✗ |
| `domElement` | `any` | let/var | `this.domElement` | ✗ |
| `raycaster` | `any` | let/var | `this.raycaster` | ✗ |


---

## Functions

### `DragControls.connect(element: any): void`

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

		this.domElement.addEventListener( 'pointermove', this._onPointerMove );
		this.domElement.addEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.addEventListener( 'pointerup', this._onPointerCancel );
		this.domElement.addEventListener( 'pointerleave', this._onPointerCancel );
		this.domElement.addEventListener( 'contextmenu', this._onContextMenu );

		this.domElement.style.touchAction = 'none'; // disable touch scroll

	}
```
</details>

### `DragControls.disconnect(): void`

**Returns:** `void`

**Calls:**

- `this.domElement.removeEventListener`

<details><summary>Code</summary>

```typescript
disconnect() {

		this.domElement.removeEventListener( 'pointermove', this._onPointerMove );
		this.domElement.removeEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.removeEventListener( 'pointerup', this._onPointerCancel );
		this.domElement.removeEventListener( 'pointerleave', this._onPointerCancel );
		this.domElement.removeEventListener( 'contextmenu', this._onContextMenu );

		this.domElement.style.touchAction = 'auto';
		this.domElement.style.cursor = '';

	}
```
</details>

### `DragControls.dispose(): void`

**Returns:** `void`

**Calls:**

- `this.disconnect`

<details><summary>Code</summary>

```typescript
dispose() {

		this.disconnect();

	}
```
</details>

### `DragControls._updatePointer(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `this.domElement.getBoundingClientRect`

<details><summary>Code</summary>

```typescript
_updatePointer( event ) {

		const rect = this.domElement.getBoundingClientRect();

		_pointer.x = ( event.clientX - rect.left ) / rect.width * 2 - 1;
		_pointer.y = - ( event.clientY - rect.top ) / rect.height * 2 + 1;

	}
```
</details>

### `DragControls._updateState(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Internal Comments:**
```
// determine action (x2)
// determine state
```

<details><summary>Code</summary>

```typescript
_updateState( event ) {

		// determine action

		let action;

		if ( event.pointerType === 'touch' ) {

			action = this.touches.ONE;

		} else {

			switch ( event.button ) {

				case 0:

					action = this.mouseButtons.LEFT;
					break;

				case 1:

					action = this.mouseButtons.MIDDLE;
					break;

				case 2:

					action = this.mouseButtons.RIGHT;
					break;

				default:

					action = null;

			}

		}

		// determine state

		switch ( action ) {

			case MOUSE.PAN:
			case TOUCH.PAN:

				this.state = STATE.PAN;

				break;

			case MOUSE.ROTATE:
			case TOUCH.ROTATE:

				this.state = STATE.ROTATE;

				break;

			default:

				this.state = STATE.NONE;

		}

	}
```
</details>

### `DragControls.getRaycaster(): Raycaster`

**Returns:** `Raycaster`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
getRaycaster() {

		console.warn( 'THREE.DragControls: getRaycaster() has been deprecated. Use controls.raycaster instead.' ); // @deprecated r169

		return this.raycaster;

	}
```
</details>

### `DragControls.setObjects(objects: any): void`

**Parameters:**

- **`objects`** `any`

**Returns:** `void`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
setObjects( objects ) {

		console.warn( 'THREE.DragControls: setObjects() has been deprecated. Use controls.objects instead.' ); // @deprecated r169

		this.objects = objects;

	}
```
</details>

### `DragControls.getObjects(): Object3D[]`

**Returns:** `Object3D[]`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
getObjects() {

		console.warn( 'THREE.DragControls: getObjects() has been deprecated. Use controls.objects instead.' ); // @deprecated r169

		return this.objects;

	}
```
</details>

### `DragControls.activate(): void`

**Returns:** `void`

**Calls:**

- `console.warn`
- `this.connect`

<details><summary>Code</summary>

```typescript
activate() {

		console.warn( 'THREE.DragControls: activate() has been renamed to connect().' ); // @deprecated r169
		this.connect();

	}
```
</details>

### `DragControls.deactivate(): void`

**Returns:** `void`

**Calls:**

- `console.warn`
- `this.disconnect`

<details><summary>Code</summary>

```typescript
deactivate() {

		console.warn( 'THREE.DragControls: deactivate() has been renamed to disconnect().' ); // @deprecated r169
		this.disconnect();

	}
```
</details>

### `onPointerMove(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `this._updatePointer`
- `raycaster.setFromCamera`
- `raycaster.ray.intersectPlane`
- `_selected.position.copy`
- `_intersection.sub( _offset ).applyMatrix4`
- `_diff.subVectors( _pointer, _previousPointer ).multiplyScalar`
- `_selected.rotateOnWorldAxis`
- `_right.normalize`
- `this.dispatchEvent`
- `_previousPointer.copy`
- `raycaster.intersectObjects`
- `_plane.setFromNormalAndCoplanarPoint`
- `camera.getWorldDirection`
- `_worldPosition.setFromMatrixPosition`

**Internal Comments:**
```
// hover support
```

<details><summary>Code</summary>

```typescript
function onPointerMove( event ) {

	const camera = this.object;
	const domElement = this.domElement;
	const raycaster = this.raycaster;

	if ( this.enabled === false ) return;

	this._updatePointer( event );

	raycaster.setFromCamera( _pointer, camera );

	if ( _selected ) {

		if ( this.state === STATE.PAN ) {

			if ( raycaster.ray.intersectPlane( _plane, _intersection ) ) {

				_selected.position.copy( _intersection.sub( _offset ).applyMatrix4( _inverseMatrix ) );

			}

		} else if ( this.state === STATE.ROTATE ) {

			_diff.subVectors( _pointer, _previousPointer ).multiplyScalar( this.rotateSpeed );
			_selected.rotateOnWorldAxis( _up, _diff.x );
			_selected.rotateOnWorldAxis( _right.normalize(), - _diff.y );

		}

		this.dispatchEvent( { type: 'drag', object: _selected } );

		_previousPointer.copy( _pointer );

	} else {

		// hover support

		if ( event.pointerType === 'mouse' || event.pointerType === 'pen' ) {

			_intersections.length = 0;

			raycaster.setFromCamera( _pointer, camera );
			raycaster.intersectObjects( this.objects, this.recursive, _intersections );

			if ( _intersections.length > 0 ) {

				const object = _intersections[ 0 ].object;

				_plane.setFromNormalAndCoplanarPoint( camera.getWorldDirection( _plane.normal ), _worldPosition.setFromMatrixPosition( object.matrixWorld ) );

				if ( _hovered !== object && _hovered !== null ) {

					this.dispatchEvent( { type: 'hoveroff', object: _hovered } );

					domElement.style.cursor = 'auto';
					_hovered = null;

				}

				if ( _hovered !== object ) {

					this.dispatchEvent( { type: 'hoveron', object: object } );

					domElement.style.cursor = 'pointer';
					_hovered = object;

				}

			} else {

				if ( _hovered !== null ) {

					this.dispatchEvent( { type: 'hoveroff', object: _hovered } );

					domElement.style.cursor = 'auto';
					_hovered = null;

				}

			}

		}

	}

	_previousPointer.copy( _pointer );

}
```
</details>

### `onPointerDown(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `this._updatePointer`
- `this._updateState`
- `raycaster.setFromCamera`
- `raycaster.intersectObjects`
- `findGroup`
- `_plane.setFromNormalAndCoplanarPoint`
- `camera.getWorldDirection`
- `_worldPosition.setFromMatrixPosition`
- `raycaster.ray.intersectPlane`
- `_inverseMatrix.copy( _selected.parent.matrixWorld ).invert`
- `_offset.copy( _intersection ).sub`
- `_up.set( 0, 1, 0 ).applyQuaternion( camera.quaternion ).normalize`
- `_right.set( 1, 0, 0 ).applyQuaternion( camera.quaternion ).normalize`
- `this.dispatchEvent`
- `_previousPointer.copy`

**Internal Comments:**
```
// look for the outermost group in the object's upper hierarchy (x3)
// the controls only support Y+ up (x8)
```

<details><summary>Code</summary>

```typescript
function onPointerDown( event ) {

	const camera = this.object;
	const domElement = this.domElement;
	const raycaster = this.raycaster;

	if ( this.enabled === false ) return;

	this._updatePointer( event );
	this._updateState( event );

	_intersections.length = 0;

	raycaster.setFromCamera( _pointer, camera );
	raycaster.intersectObjects( this.objects, this.recursive, _intersections );

	if ( _intersections.length > 0 ) {

		if ( this.transformGroup === true ) {

			// look for the outermost group in the object's upper hierarchy

			_selected = findGroup( _intersections[ 0 ].object );

		} else {

			_selected = _intersections[ 0 ].object;

		}

		_plane.setFromNormalAndCoplanarPoint( camera.getWorldDirection( _plane.normal ), _worldPosition.setFromMatrixPosition( _selected.matrixWorld ) );

		if ( raycaster.ray.intersectPlane( _plane, _intersection ) ) {

			if ( this.state === STATE.PAN ) {

				_inverseMatrix.copy( _selected.parent.matrixWorld ).invert();
				_offset.copy( _intersection ).sub( _worldPosition.setFromMatrixPosition( _selected.matrixWorld ) );

			} else if ( this.state === STATE.ROTATE ) {

				// the controls only support Y+ up
				_up.set( 0, 1, 0 ).applyQuaternion( camera.quaternion ).normalize();
				_right.set( 1, 0, 0 ).applyQuaternion( camera.quaternion ).normalize();

			}

		}

		domElement.style.cursor = 'move';

		this.dispatchEvent( { type: 'dragstart', object: _selected } );

	}

	_previousPointer.copy( _pointer );

}
```
</details>

### `onPointerCancel(): void`

**Returns:** `void`

**Calls:**

- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
function onPointerCancel() {

	if ( this.enabled === false ) return;

	if ( _selected ) {

		this.dispatchEvent( { type: 'dragend', object: _selected } );

		_selected = null;

	}

	this.domElement.style.cursor = _hovered ? 'pointer' : 'auto';

	this.state = STATE.NONE;

}
```
</details>

### `onContextMenu(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `event.preventDefault`

<details><summary>Code</summary>

```typescript
function onContextMenu( event ) {

	if ( this.enabled === false ) return;

	event.preventDefault();

}
```
</details>

### `findGroup(obj: any, group: any): any`

**Parameters:**

- **`obj`** `any`
- **`group`** `any`

**Returns:** `any`

**Calls:**

- `findGroup`

<details><summary>Code</summary>

```typescript
function findGroup( obj, group = null ) {

	if ( obj.isGroup ) group = obj;

	if ( obj.parent === null ) return group;

	return findGroup( obj.parent, group );

}
```
</details>


---

## Classes

### `DragControls`

<details><summary>Class Code</summary>

```ts
class DragControls extends Controls {

	/**
	 * Constructs a new controls instance.
	 *
	 * @param {Array<Object3D>} objects - An array of draggable 3D objects.
	 * @param {Camera} camera - The camera of the rendered scene.
	 * @param {?HTMLDOMElement} [domElement=null] - The HTML DOM element used for event listeners.
	 */
	constructor( objects, camera, domElement = null ) {

		super( camera, domElement );

		/**
		 * An array of draggable 3D objects.
		 *
		 * @type {Array<Object3D>}
		 */
		this.objects = objects;

		/**
		 * Whether children of draggable objects can be dragged independently from their parent.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.recursive = true;

		/**
		 * This option only works if the `objects` array contains a single draggable  group object.
		 * If set to `true`, the controls does not transform individual objects but the entire group.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.transformGroup = false;

		/**
		 * The speed at which the object will rotate when dragged in `rotate` mode.
		 * The higher the number the faster the rotation.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.rotateSpeed = 1;

		/**
		 * The raycaster used for detecting 3D objects.
		 *
		 * @type {Raycaster}
		 */
		this.raycaster = new Raycaster();

		// interaction

		this.mouseButtons = { LEFT: MOUSE.PAN, MIDDLE: MOUSE.PAN, RIGHT: MOUSE.ROTATE };
		this.touches = { ONE: TOUCH.PAN };

		// event listeners

		this._onPointerMove = onPointerMove.bind( this );
		this._onPointerDown = onPointerDown.bind( this );
		this._onPointerCancel = onPointerCancel.bind( this );
		this._onContextMenu = onContextMenu.bind( this );

		//

		if ( domElement !== null ) {

			this.connect( domElement );

		}

	}

	connect( element ) {

		super.connect( element );

		this.domElement.addEventListener( 'pointermove', this._onPointerMove );
		this.domElement.addEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.addEventListener( 'pointerup', this._onPointerCancel );
		this.domElement.addEventListener( 'pointerleave', this._onPointerCancel );
		this.domElement.addEventListener( 'contextmenu', this._onContextMenu );

		this.domElement.style.touchAction = 'none'; // disable touch scroll

	}

	disconnect() {

		this.domElement.removeEventListener( 'pointermove', this._onPointerMove );
		this.domElement.removeEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.removeEventListener( 'pointerup', this._onPointerCancel );
		this.domElement.removeEventListener( 'pointerleave', this._onPointerCancel );
		this.domElement.removeEventListener( 'contextmenu', this._onContextMenu );

		this.domElement.style.touchAction = 'auto';
		this.domElement.style.cursor = '';

	}

	dispose() {

		this.disconnect();

	}

	_updatePointer( event ) {

		const rect = this.domElement.getBoundingClientRect();

		_pointer.x = ( event.clientX - rect.left ) / rect.width * 2 - 1;
		_pointer.y = - ( event.clientY - rect.top ) / rect.height * 2 + 1;

	}

	_updateState( event ) {

		// determine action

		let action;

		if ( event.pointerType === 'touch' ) {

			action = this.touches.ONE;

		} else {

			switch ( event.button ) {

				case 0:

					action = this.mouseButtons.LEFT;
					break;

				case 1:

					action = this.mouseButtons.MIDDLE;
					break;

				case 2:

					action = this.mouseButtons.RIGHT;
					break;

				default:

					action = null;

			}

		}

		// determine state

		switch ( action ) {

			case MOUSE.PAN:
			case TOUCH.PAN:

				this.state = STATE.PAN;

				break;

			case MOUSE.ROTATE:
			case TOUCH.ROTATE:

				this.state = STATE.ROTATE;

				break;

			default:

				this.state = STATE.NONE;

		}

	}

	getRaycaster() {

		console.warn( 'THREE.DragControls: getRaycaster() has been deprecated. Use controls.raycaster instead.' ); // @deprecated r169

		return this.raycaster;

	}

	setObjects( objects ) {

		console.warn( 'THREE.DragControls: setObjects() has been deprecated. Use controls.objects instead.' ); // @deprecated r169

		this.objects = objects;

	}

	getObjects() {

		console.warn( 'THREE.DragControls: getObjects() has been deprecated. Use controls.objects instead.' ); // @deprecated r169

		return this.objects;

	}

	activate() {

		console.warn( 'THREE.DragControls: activate() has been renamed to connect().' ); // @deprecated r169
		this.connect();

	}

	deactivate() {

		console.warn( 'THREE.DragControls: deactivate() has been renamed to disconnect().' ); // @deprecated r169
		this.disconnect();

	}

	set mode( value ) {

		console.warn( 'THREE.DragControls: The .mode property has been removed. Define the type of transformation via the .mouseButtons or .touches properties.' ); // @deprecated r169

	}

	get mode() {

		console.warn( 'THREE.DragControls: The .mode property has been removed. Define the type of transformation via the .mouseButtons or .touches properties.' ); // @deprecated r169

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

		this.domElement.addEventListener( 'pointermove', this._onPointerMove );
		this.domElement.addEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.addEventListener( 'pointerup', this._onPointerCancel );
		this.domElement.addEventListener( 'pointerleave', this._onPointerCancel );
		this.domElement.addEventListener( 'contextmenu', this._onContextMenu );

		this.domElement.style.touchAction = 'none'; // disable touch scroll

	}
```
</details>

##### `disconnect(): void`

<details><summary>Code</summary>

```ts
disconnect() {

		this.domElement.removeEventListener( 'pointermove', this._onPointerMove );
		this.domElement.removeEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.removeEventListener( 'pointerup', this._onPointerCancel );
		this.domElement.removeEventListener( 'pointerleave', this._onPointerCancel );
		this.domElement.removeEventListener( 'contextmenu', this._onContextMenu );

		this.domElement.style.touchAction = 'auto';
		this.domElement.style.cursor = '';

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.disconnect();

	}
```
</details>

##### `_updatePointer(event: any): void`

<details><summary>Code</summary>

```ts
_updatePointer( event ) {

		const rect = this.domElement.getBoundingClientRect();

		_pointer.x = ( event.clientX - rect.left ) / rect.width * 2 - 1;
		_pointer.y = - ( event.clientY - rect.top ) / rect.height * 2 + 1;

	}
```
</details>

##### `_updateState(event: any): void`

<details><summary>Code</summary>

```ts
_updateState( event ) {

		// determine action

		let action;

		if ( event.pointerType === 'touch' ) {

			action = this.touches.ONE;

		} else {

			switch ( event.button ) {

				case 0:

					action = this.mouseButtons.LEFT;
					break;

				case 1:

					action = this.mouseButtons.MIDDLE;
					break;

				case 2:

					action = this.mouseButtons.RIGHT;
					break;

				default:

					action = null;

			}

		}

		// determine state

		switch ( action ) {

			case MOUSE.PAN:
			case TOUCH.PAN:

				this.state = STATE.PAN;

				break;

			case MOUSE.ROTATE:
			case TOUCH.ROTATE:

				this.state = STATE.ROTATE;

				break;

			default:

				this.state = STATE.NONE;

		}

	}
```
</details>

##### `getRaycaster(): Raycaster`

<details><summary>Code</summary>

```ts
getRaycaster() {

		console.warn( 'THREE.DragControls: getRaycaster() has been deprecated. Use controls.raycaster instead.' ); // @deprecated r169

		return this.raycaster;

	}
```
</details>

##### `setObjects(objects: any): void`

<details><summary>Code</summary>

```ts
setObjects( objects ) {

		console.warn( 'THREE.DragControls: setObjects() has been deprecated. Use controls.objects instead.' ); // @deprecated r169

		this.objects = objects;

	}
```
</details>

##### `getObjects(): Object3D[]`

<details><summary>Code</summary>

```ts
getObjects() {

		console.warn( 'THREE.DragControls: getObjects() has been deprecated. Use controls.objects instead.' ); // @deprecated r169

		return this.objects;

	}
```
</details>

##### `activate(): void`

<details><summary>Code</summary>

```ts
activate() {

		console.warn( 'THREE.DragControls: activate() has been renamed to connect().' ); // @deprecated r169
		this.connect();

	}
```
</details>

##### `deactivate(): void`

<details><summary>Code</summary>

```ts
deactivate() {

		console.warn( 'THREE.DragControls: deactivate() has been renamed to disconnect().' ); // @deprecated r169
		this.disconnect();

	}
```
</details>


---