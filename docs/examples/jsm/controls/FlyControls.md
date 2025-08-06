[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `FlyControls.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 14 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/controls/FlyControls.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Controls` | `three` |
| `Quaternion` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_changeEvent` | `any` | let/var | `{ type: 'change' }` | ✗ |
| `_EPS` | `0.000001` | let/var | `0.000001` | ✗ |
| `_tmpQuaternion` | `any` | let/var | `new Quaternion()` | ✗ |
| `object` | `any` | let/var | `this.object` | ✗ |
| `moveMult` | `number` | let/var | `delta * this.movementSpeed` | ✗ |
| `rotMult` | `number` | let/var | `delta * this.rollSpeed` | ✗ |
| `forward` | `1 \| 0` | let/var | `( this._moveState.forward \|\| ( this.autoForward && ! this._moveState.back )...` | ✗ |
| `halfWidth` | `number` | let/var | `container.size[ 0 ] / 2` | ✗ |
| `halfHeight` | `number` | let/var | `container.size[ 1 ] / 2` | ✗ |


---

## Functions

### `FlyControls.connect(element: any): void`

**Parameters:**

- **`element`** `any`

**Returns:** `void`

**Calls:**

- `super.connect`
- `window.addEventListener`
- `this.domElement.addEventListener`

<details><summary>Code</summary>

```typescript
connect( element ) {

		super.connect( element );

		window.addEventListener( 'keydown', this._onKeyDown );
		window.addEventListener( 'keyup', this._onKeyUp );

		this.domElement.addEventListener( 'pointermove', this._onPointerMove );
		this.domElement.addEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.addEventListener( 'pointerup', this._onPointerUp );
		this.domElement.addEventListener( 'pointercancel', this._onPointerCancel );
		this.domElement.addEventListener( 'contextmenu', this._onContextMenu );

	}
```
</details>

### `FlyControls.disconnect(): void`

**Returns:** `void`

**Calls:**

- `window.removeEventListener`
- `this.domElement.removeEventListener`

<details><summary>Code</summary>

```typescript
disconnect() {

		window.removeEventListener( 'keydown', this._onKeyDown );
		window.removeEventListener( 'keyup', this._onKeyUp );

		this.domElement.removeEventListener( 'pointermove', this._onPointerMove );
		this.domElement.removeEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.removeEventListener( 'pointerup', this._onPointerUp );
		this.domElement.removeEventListener( 'pointercancel', this._onPointerCancel );
		this.domElement.removeEventListener( 'contextmenu', this._onContextMenu );

	}
```
</details>

### `FlyControls.dispose(): void`

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

### `FlyControls.update(delta: any): void`

**Parameters:**

- **`delta`** `any`

**Returns:** `void`

**Calls:**

- `object.translateX`
- `object.translateY`
- `object.translateZ`
- `_tmpQuaternion.set( this._rotationVector.x * rotMult, this._rotationVector.y * rotMult, this._rotationVector.z * rotMult, 1 ).normalize`
- `object.quaternion.multiply`
- `this._lastPosition.distanceToSquared`
- `this._lastQuaternion.dot`
- `this.dispatchEvent`
- `this._lastQuaternion.copy`
- `this._lastPosition.copy`

<details><summary>Code</summary>

```typescript
update( delta ) {

		if ( this.enabled === false ) return;

		const object = this.object;

		const moveMult = delta * this.movementSpeed;
		const rotMult = delta * this.rollSpeed;

		object.translateX( this._moveVector.x * moveMult );
		object.translateY( this._moveVector.y * moveMult );
		object.translateZ( this._moveVector.z * moveMult );

		_tmpQuaternion.set( this._rotationVector.x * rotMult, this._rotationVector.y * rotMult, this._rotationVector.z * rotMult, 1 ).normalize();
		object.quaternion.multiply( _tmpQuaternion );

		if (
			this._lastPosition.distanceToSquared( object.position ) > _EPS ||
			8 * ( 1 - this._lastQuaternion.dot( object.quaternion ) ) > _EPS
		) {

			this.dispatchEvent( _changeEvent );
			this._lastQuaternion.copy( object.quaternion );
			this._lastPosition.copy( object.position );

		}

	}
```
</details>

### `FlyControls._updateMovementVector(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_updateMovementVector() {

		const forward = ( this._moveState.forward || ( this.autoForward && ! this._moveState.back ) ) ? 1 : 0;

		this._moveVector.x = ( - this._moveState.left + this._moveState.right );
		this._moveVector.y = ( - this._moveState.down + this._moveState.up );
		this._moveVector.z = ( - forward + this._moveState.back );

		//console.log( 'move:', [ this._moveVector.x, this._moveVector.y, this._moveVector.z ] );

	}
```
</details>

### `FlyControls._updateRotationVector(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_updateRotationVector() {

		this._rotationVector.x = ( - this._moveState.pitchDown + this._moveState.pitchUp );
		this._rotationVector.y = ( - this._moveState.yawRight + this._moveState.yawLeft );
		this._rotationVector.z = ( - this._moveState.rollRight + this._moveState.rollLeft );

		//console.log( 'rotate:', [ this._rotationVector.x, this._rotationVector.y, this._rotationVector.z ] );

	}
```
</details>

### `FlyControls._getContainerDimensions(): { size: any[]; offset: any[]; }`

**Returns:** `{ size: any[]; offset: any[]; }`

<details><summary>Code</summary>

```typescript
_getContainerDimensions() {

		if ( this.domElement != document ) {

			return {
				size: [ this.domElement.offsetWidth, this.domElement.offsetHeight ],
				offset: [ this.domElement.offsetLeft, this.domElement.offsetTop ]
			};

		} else {

			return {
				size: [ window.innerWidth, window.innerHeight ],
				offset: [ 0, 0 ]
			};

		}

	}
```
</details>

### `onKeyDown(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `this._updateMovementVector`
- `this._updateRotationVector`

<details><summary>Code</summary>

```typescript
function onKeyDown( event ) {

	if ( event.altKey || this.enabled === false ) {

		return;

	}

	switch ( event.code ) {

		case 'ShiftLeft':
		case 'ShiftRight': this.movementSpeedMultiplier = .1; break;

		case 'KeyW': this._moveState.forward = 1; break;
		case 'KeyS': this._moveState.back = 1; break;

		case 'KeyA': this._moveState.left = 1; break;
		case 'KeyD': this._moveState.right = 1; break;

		case 'KeyR': this._moveState.up = 1; break;
		case 'KeyF': this._moveState.down = 1; break;

		case 'ArrowUp': this._moveState.pitchUp = 1; break;
		case 'ArrowDown': this._moveState.pitchDown = 1; break;

		case 'ArrowLeft': this._moveState.yawLeft = 1; break;
		case 'ArrowRight': this._moveState.yawRight = 1; break;

		case 'KeyQ': this._moveState.rollLeft = 1; break;
		case 'KeyE': this._moveState.rollRight = 1; break;

	}

	this._updateMovementVector();
	this._updateRotationVector();

}
```
</details>

### `onKeyUp(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `this._updateMovementVector`
- `this._updateRotationVector`

<details><summary>Code</summary>

```typescript
function onKeyUp( event ) {

	if ( this.enabled === false ) return;

	switch ( event.code ) {

		case 'ShiftLeft':
		case 'ShiftRight': this.movementSpeedMultiplier = 1; break;

		case 'KeyW': this._moveState.forward = 0; break;
		case 'KeyS': this._moveState.back = 0; break;

		case 'KeyA': this._moveState.left = 0; break;
		case 'KeyD': this._moveState.right = 0; break;

		case 'KeyR': this._moveState.up = 0; break;
		case 'KeyF': this._moveState.down = 0; break;

		case 'ArrowUp': this._moveState.pitchUp = 0; break;
		case 'ArrowDown': this._moveState.pitchDown = 0; break;

		case 'ArrowLeft': this._moveState.yawLeft = 0; break;
		case 'ArrowRight': this._moveState.yawRight = 0; break;

		case 'KeyQ': this._moveState.rollLeft = 0; break;
		case 'KeyE': this._moveState.rollRight = 0; break;

	}

	this._updateMovementVector();
	this._updateRotationVector();

}
```
</details>

### `onPointerDown(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `this._updateMovementVector`

<details><summary>Code</summary>

```typescript
function onPointerDown( event ) {

	if ( this.enabled === false ) return;

	if ( this.dragToLook ) {

		this._status ++;

	} else {

		switch ( event.button ) {

			case 0: this._moveState.forward = 1; break;
			case 2: this._moveState.back = 1; break;

		}

		this._updateMovementVector();

	}

}
```
</details>

### `onPointerMove(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `this._getContainerDimensions`
- `this._updateRotationVector`

<details><summary>Code</summary>

```typescript
function onPointerMove( event ) {

	if ( this.enabled === false ) return;

	if ( ! this.dragToLook || this._status > 0 ) {

		const container = this._getContainerDimensions();
		const halfWidth = container.size[ 0 ] / 2;
		const halfHeight = container.size[ 1 ] / 2;

		this._moveState.yawLeft = - ( ( event.pageX - container.offset[ 0 ] ) - halfWidth ) / halfWidth;
		this._moveState.pitchDown = ( ( event.pageY - container.offset[ 1 ] ) - halfHeight ) / halfHeight;

		this._updateRotationVector();

	}

}
```
</details>

### `onPointerUp(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `this._updateMovementVector`
- `this._updateRotationVector`

<details><summary>Code</summary>

```typescript
function onPointerUp( event ) {

	if ( this.enabled === false ) return;

	if ( this.dragToLook ) {

		this._status --;

		this._moveState.yawLeft = this._moveState.pitchDown = 0;

	} else {

		switch ( event.button ) {

			case 0: this._moveState.forward = 0; break;
			case 2: this._moveState.back = 0; break;

		}

		this._updateMovementVector();

	}

	this._updateRotationVector();

}
```
</details>

### `onPointerCancel(): void`

**Returns:** `void`

**Calls:**

- `this._updateMovementVector`
- `this._updateRotationVector`

<details><summary>Code</summary>

```typescript
function onPointerCancel() {

	if ( this.enabled === false ) return;

	if ( this.dragToLook ) {

		this._status = 0;

		this._moveState.yawLeft = this._moveState.pitchDown = 0;

	} else {

		this._moveState.forward = 0;
		this._moveState.back = 0;

		this._updateMovementVector();

	}

	this._updateRotationVector();

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


---

## Classes

### `FlyControls`

<details><summary>Class Code</summary>

```ts
class FlyControls extends Controls {

	/**
	 * Constructs a new controls instance.
	 *
	 * @param {Object3D} object - The object that is managed by the controls.
	 * @param {?HTMLDOMElement} domElement - The HTML element used for event listeners.
	 */
	constructor( object, domElement = null ) {

		super( object, domElement );

		/**
		 * The movement speed.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.movementSpeed = 1.0;

		/**
		 * The rotation speed.
		 *
		 * @type {number}
		 * @default 0.005
		 */
		this.rollSpeed = 0.005;

		/**
		 * If set to `true`, you can only look around by performing a drag interaction.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.dragToLook = false;

		/**
		 * If set to `true`, the camera automatically moves forward (and does not stop) when initially translated.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.autoForward = false;

		// internals

		this._moveState = { up: 0, down: 0, left: 0, right: 0, forward: 0, back: 0, pitchUp: 0, pitchDown: 0, yawLeft: 0, yawRight: 0, rollLeft: 0, rollRight: 0 };
		this._moveVector = new Vector3( 0, 0, 0 );
		this._rotationVector = new Vector3( 0, 0, 0 );
		this._lastQuaternion = new Quaternion();
		this._lastPosition = new Vector3();
		this._status = 0;

		// event listeners

		this._onKeyDown = onKeyDown.bind( this );
		this._onKeyUp = onKeyUp.bind( this );
		this._onPointerMove = onPointerMove.bind( this );
		this._onPointerDown = onPointerDown.bind( this );
		this._onPointerUp = onPointerUp.bind( this );
		this._onPointerCancel = onPointerCancel.bind( this );
		this._onContextMenu = onContextMenu.bind( this );

		//

		if ( domElement !== null ) {

			this.connect( domElement );

		}

	}

	connect( element ) {

		super.connect( element );

		window.addEventListener( 'keydown', this._onKeyDown );
		window.addEventListener( 'keyup', this._onKeyUp );

		this.domElement.addEventListener( 'pointermove', this._onPointerMove );
		this.domElement.addEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.addEventListener( 'pointerup', this._onPointerUp );
		this.domElement.addEventListener( 'pointercancel', this._onPointerCancel );
		this.domElement.addEventListener( 'contextmenu', this._onContextMenu );

	}

	disconnect() {

		window.removeEventListener( 'keydown', this._onKeyDown );
		window.removeEventListener( 'keyup', this._onKeyUp );

		this.domElement.removeEventListener( 'pointermove', this._onPointerMove );
		this.domElement.removeEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.removeEventListener( 'pointerup', this._onPointerUp );
		this.domElement.removeEventListener( 'pointercancel', this._onPointerCancel );
		this.domElement.removeEventListener( 'contextmenu', this._onContextMenu );

	}

	dispose() {

		this.disconnect();

	}

	update( delta ) {

		if ( this.enabled === false ) return;

		const object = this.object;

		const moveMult = delta * this.movementSpeed;
		const rotMult = delta * this.rollSpeed;

		object.translateX( this._moveVector.x * moveMult );
		object.translateY( this._moveVector.y * moveMult );
		object.translateZ( this._moveVector.z * moveMult );

		_tmpQuaternion.set( this._rotationVector.x * rotMult, this._rotationVector.y * rotMult, this._rotationVector.z * rotMult, 1 ).normalize();
		object.quaternion.multiply( _tmpQuaternion );

		if (
			this._lastPosition.distanceToSquared( object.position ) > _EPS ||
			8 * ( 1 - this._lastQuaternion.dot( object.quaternion ) ) > _EPS
		) {

			this.dispatchEvent( _changeEvent );
			this._lastQuaternion.copy( object.quaternion );
			this._lastPosition.copy( object.position );

		}

	}

	// private

	_updateMovementVector() {

		const forward = ( this._moveState.forward || ( this.autoForward && ! this._moveState.back ) ) ? 1 : 0;

		this._moveVector.x = ( - this._moveState.left + this._moveState.right );
		this._moveVector.y = ( - this._moveState.down + this._moveState.up );
		this._moveVector.z = ( - forward + this._moveState.back );

		//console.log( 'move:', [ this._moveVector.x, this._moveVector.y, this._moveVector.z ] );

	}

	_updateRotationVector() {

		this._rotationVector.x = ( - this._moveState.pitchDown + this._moveState.pitchUp );
		this._rotationVector.y = ( - this._moveState.yawRight + this._moveState.yawLeft );
		this._rotationVector.z = ( - this._moveState.rollRight + this._moveState.rollLeft );

		//console.log( 'rotate:', [ this._rotationVector.x, this._rotationVector.y, this._rotationVector.z ] );

	}

	_getContainerDimensions() {

		if ( this.domElement != document ) {

			return {
				size: [ this.domElement.offsetWidth, this.domElement.offsetHeight ],
				offset: [ this.domElement.offsetLeft, this.domElement.offsetTop ]
			};

		} else {

			return {
				size: [ window.innerWidth, window.innerHeight ],
				offset: [ 0, 0 ]
			};

		}

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

		window.addEventListener( 'keydown', this._onKeyDown );
		window.addEventListener( 'keyup', this._onKeyUp );

		this.domElement.addEventListener( 'pointermove', this._onPointerMove );
		this.domElement.addEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.addEventListener( 'pointerup', this._onPointerUp );
		this.domElement.addEventListener( 'pointercancel', this._onPointerCancel );
		this.domElement.addEventListener( 'contextmenu', this._onContextMenu );

	}
```
</details>

##### `disconnect(): void`

<details><summary>Code</summary>

```ts
disconnect() {

		window.removeEventListener( 'keydown', this._onKeyDown );
		window.removeEventListener( 'keyup', this._onKeyUp );

		this.domElement.removeEventListener( 'pointermove', this._onPointerMove );
		this.domElement.removeEventListener( 'pointerdown', this._onPointerDown );
		this.domElement.removeEventListener( 'pointerup', this._onPointerUp );
		this.domElement.removeEventListener( 'pointercancel', this._onPointerCancel );
		this.domElement.removeEventListener( 'contextmenu', this._onContextMenu );

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

##### `update(delta: any): void`

<details><summary>Code</summary>

```ts
update( delta ) {

		if ( this.enabled === false ) return;

		const object = this.object;

		const moveMult = delta * this.movementSpeed;
		const rotMult = delta * this.rollSpeed;

		object.translateX( this._moveVector.x * moveMult );
		object.translateY( this._moveVector.y * moveMult );
		object.translateZ( this._moveVector.z * moveMult );

		_tmpQuaternion.set( this._rotationVector.x * rotMult, this._rotationVector.y * rotMult, this._rotationVector.z * rotMult, 1 ).normalize();
		object.quaternion.multiply( _tmpQuaternion );

		if (
			this._lastPosition.distanceToSquared( object.position ) > _EPS ||
			8 * ( 1 - this._lastQuaternion.dot( object.quaternion ) ) > _EPS
		) {

			this.dispatchEvent( _changeEvent );
			this._lastQuaternion.copy( object.quaternion );
			this._lastPosition.copy( object.position );

		}

	}
```
</details>

##### `_updateMovementVector(): void`

<details><summary>Code</summary>

```ts
_updateMovementVector() {

		const forward = ( this._moveState.forward || ( this.autoForward && ! this._moveState.back ) ) ? 1 : 0;

		this._moveVector.x = ( - this._moveState.left + this._moveState.right );
		this._moveVector.y = ( - this._moveState.down + this._moveState.up );
		this._moveVector.z = ( - forward + this._moveState.back );

		//console.log( 'move:', [ this._moveVector.x, this._moveVector.y, this._moveVector.z ] );

	}
```
</details>

##### `_updateRotationVector(): void`

<details><summary>Code</summary>

```ts
_updateRotationVector() {

		this._rotationVector.x = ( - this._moveState.pitchDown + this._moveState.pitchUp );
		this._rotationVector.y = ( - this._moveState.yawRight + this._moveState.yawLeft );
		this._rotationVector.z = ( - this._moveState.rollRight + this._moveState.rollLeft );

		//console.log( 'rotate:', [ this._rotationVector.x, this._rotationVector.y, this._rotationVector.z ] );

	}
```
</details>

##### `_getContainerDimensions(): { size: any[]; offset: any[]; }`

<details><summary>Code</summary>

```ts
_getContainerDimensions() {

		if ( this.domElement != document ) {

			return {
				size: [ this.domElement.offsetWidth, this.domElement.offsetHeight ],
				offset: [ this.domElement.offsetLeft, this.domElement.offsetTop ]
			};

		} else {

			return {
				size: [ window.innerWidth, window.innerHeight ],
				offset: [ 0, 0 ]
			};

		}

	}
```
</details>


---