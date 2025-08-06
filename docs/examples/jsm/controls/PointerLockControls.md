[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PointerLockControls.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 12 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 10 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/controls/PointerLockControls.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Controls` | `three` |
| `Euler` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_euler` | `any` | let/var | `new Euler( 0, 0, 0, 'YXZ' )` | ✗ |
| `_vector` | `any` | let/var | `new Vector3()` | ✗ |
| `_changeEvent` | `any` | let/var | `{ type: 'change' }` | ✗ |
| `_lockEvent` | `any` | let/var | `{ type: 'lock' }` | ✗ |
| `_unlockEvent` | `any` | let/var | `{ type: 'unlock' }` | ✗ |
| `_MOUSE_SENSITIVITY` | `0.002` | let/var | `0.002` | ✗ |
| `_PI_2` | `number` | let/var | `Math.PI / 2` | ✗ |
| `camera` | `any` | let/var | `this.object` | ✗ |
| `camera` | `any` | let/var | `this.object` | ✗ |
| `camera` | `any` | let/var | `this.object` | ✗ |


---

## Functions

### `PointerLockControls.connect(element: any): void`

**Parameters:**

- **`element`** `any`

**Returns:** `void`

**Calls:**

- `super.connect`
- `this.domElement.ownerDocument.addEventListener`

<details><summary>Code</summary>

```typescript
connect( element ) {

		super.connect( element );

		this.domElement.ownerDocument.addEventListener( 'mousemove', this._onMouseMove );
		this.domElement.ownerDocument.addEventListener( 'pointerlockchange', this._onPointerlockChange );
		this.domElement.ownerDocument.addEventListener( 'pointerlockerror', this._onPointerlockError );

	}
```
</details>

### `PointerLockControls.disconnect(): void`

**Returns:** `void`

**Calls:**

- `this.domElement.ownerDocument.removeEventListener`

<details><summary>Code</summary>

```typescript
disconnect() {

		this.domElement.ownerDocument.removeEventListener( 'mousemove', this._onMouseMove );
		this.domElement.ownerDocument.removeEventListener( 'pointerlockchange', this._onPointerlockChange );
		this.domElement.ownerDocument.removeEventListener( 'pointerlockerror', this._onPointerlockError );

	}
```
</details>

### `PointerLockControls.dispose(): void`

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

### `PointerLockControls.getObject(): any`

**Returns:** `any`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
getObject() {

		console.warn( 'THREE.PointerLockControls: getObject() has been deprecated. Use controls.object instead.' ); // @deprecated r169

		return this.object;

	}
```
</details>

### `PointerLockControls.getDirection(v: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Returns the look direction of the camera.
	 *
	 * @param {Vector3} v - The target vector that is used to store the method's result.
	 * @return {Vector3} The normalized direction vector.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `v.set( 0, 0, - 1 ).applyQuaternion`

<details><summary>Code</summary>

```typescript
getDirection( v ) {

		return v.set( 0, 0, - 1 ).applyQuaternion( this.object.quaternion );

	}
```
</details>

### `PointerLockControls.moveForward(distance: number): void`

**JSDoc:**
```typescript
/**
	 * Moves the camera forward parallel to the xz-plane. Assumes camera.up is y-up.
	 *
	 * @param {number} distance - The signed distance.
	 */
```

**Parameters:**

- **`distance`** `number`

**Returns:** `void`

**Calls:**

- `_vector.setFromMatrixColumn`
- `_vector.crossVectors`
- `camera.position.addScaledVector`

**Internal Comments:**
```
// move forward parallel to the xz-plane (x2)
// assumes camera.up is y-up (x2)
```

<details><summary>Code</summary>

```typescript
moveForward( distance ) {

		if ( this.enabled === false ) return;

		// move forward parallel to the xz-plane
		// assumes camera.up is y-up

		const camera = this.object;

		_vector.setFromMatrixColumn( camera.matrix, 0 );

		_vector.crossVectors( camera.up, _vector );

		camera.position.addScaledVector( _vector, distance );

	}
```
</details>

### `PointerLockControls.moveRight(distance: number): void`

**JSDoc:**
```typescript
/**
	 * Moves the camera sidewards parallel to the xz-plane.
	 *
	 * @param {number} distance - The signed distance.
	 */
```

**Parameters:**

- **`distance`** `number`

**Returns:** `void`

**Calls:**

- `_vector.setFromMatrixColumn`
- `camera.position.addScaledVector`

<details><summary>Code</summary>

```typescript
moveRight( distance ) {

		if ( this.enabled === false ) return;

		const camera = this.object;

		_vector.setFromMatrixColumn( camera.matrix, 0 );

		camera.position.addScaledVector( _vector, distance );

	}
```
</details>

### `PointerLockControls.lock(unadjustedMovement: boolean): void`

**JSDoc:**
```typescript
/**
	 * Activates the pointer lock.
	 *
	 * @param {boolean} [unadjustedMovement=false] - Disables OS-level adjustment for mouse acceleration, and accesses raw mouse input instead.
	 * Setting it to true will disable mouse acceleration.
	 */
```

**Parameters:**

- **`unadjustedMovement`** `boolean`

**Returns:** `void`

**Calls:**

- `this.domElement.requestPointerLock`

<details><summary>Code</summary>

```typescript
lock( unadjustedMovement = false ) {

		this.domElement.requestPointerLock( {
			unadjustedMovement
		} );

	}
```
</details>

### `PointerLockControls.unlock(): void`

**JSDoc:**
```typescript
/**
	 * Exits the pointer lock.
	 */
```

**Returns:** `void`

**Calls:**

- `this.domElement.ownerDocument.exitPointerLock`

<details><summary>Code</summary>

```typescript
unlock() {

		this.domElement.ownerDocument.exitPointerLock();

	}
```
</details>

### `onMouseMove(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `_euler.setFromQuaternion`
- `Math.max`
- `Math.min`
- `camera.quaternion.setFromEuler`
- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
function onMouseMove( event ) {

	if ( this.enabled === false || this.isLocked === false ) return;

	const camera = this.object;
	_euler.setFromQuaternion( camera.quaternion );

	_euler.y -= event.movementX * _MOUSE_SENSITIVITY * this.pointerSpeed;
	_euler.x -= event.movementY * _MOUSE_SENSITIVITY * this.pointerSpeed;

	_euler.x = Math.max( _PI_2 - this.maxPolarAngle, Math.min( _PI_2 - this.minPolarAngle, _euler.x ) );

	camera.quaternion.setFromEuler( _euler );

	this.dispatchEvent( _changeEvent );

}
```
</details>

### `onPointerlockChange(): void`

**Returns:** `void`

**Calls:**

- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
function onPointerlockChange() {

	if ( this.domElement.ownerDocument.pointerLockElement === this.domElement ) {

		this.dispatchEvent( _lockEvent );

		this.isLocked = true;

	} else {

		this.dispatchEvent( _unlockEvent );

		this.isLocked = false;

	}

}
```
</details>

### `onPointerlockError(): void`

**Returns:** `void`

**Calls:**

- `console.error`

<details><summary>Code</summary>

```typescript
function onPointerlockError() {

	console.error( 'THREE.PointerLockControls: Unable to use Pointer Lock API' );

}
```
</details>


---

## Classes

### `PointerLockControls`

<details><summary>Class Code</summary>

```ts
class PointerLockControls extends Controls {

	/**
	 * Constructs a new controls instance.
	 *
	 * @param {Camera} camera - The camera that is managed by the controls.
	 * @param {?HTMLDOMElement} domElement - The HTML element used for event listeners.
	 */
	constructor( camera, domElement = null ) {

		super( camera, domElement );

		/**
		 * Whether the controls are locked or not.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default false
		 */
		this.isLocked = false;

		/**
		 * Camera pitch, lower limit. Range is '[0, Math.PI]' in radians.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.minPolarAngle = 0;

		/**
		 * Camera pitch, upper limit. Range is '[0, Math.PI]' in radians.
		 *
		 * @type {number}
		 * @default Math.PI
		 */
		this.maxPolarAngle = Math.PI;

		/**
		 * Multiplier for how much the pointer movement influences the camera rotation.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.pointerSpeed = 1.0;

		// event listeners

		this._onMouseMove = onMouseMove.bind( this );
		this._onPointerlockChange = onPointerlockChange.bind( this );
		this._onPointerlockError = onPointerlockError.bind( this );

		if ( this.domElement !== null ) {

			this.connect( this.domElement );

		}

	}

	connect( element ) {

		super.connect( element );

		this.domElement.ownerDocument.addEventListener( 'mousemove', this._onMouseMove );
		this.domElement.ownerDocument.addEventListener( 'pointerlockchange', this._onPointerlockChange );
		this.domElement.ownerDocument.addEventListener( 'pointerlockerror', this._onPointerlockError );

	}

	disconnect() {

		this.domElement.ownerDocument.removeEventListener( 'mousemove', this._onMouseMove );
		this.domElement.ownerDocument.removeEventListener( 'pointerlockchange', this._onPointerlockChange );
		this.domElement.ownerDocument.removeEventListener( 'pointerlockerror', this._onPointerlockError );

	}

	dispose() {

		this.disconnect();

	}

	getObject() {

		console.warn( 'THREE.PointerLockControls: getObject() has been deprecated. Use controls.object instead.' ); // @deprecated r169

		return this.object;

	}

	/**
	 * Returns the look direction of the camera.
	 *
	 * @param {Vector3} v - The target vector that is used to store the method's result.
	 * @return {Vector3} The normalized direction vector.
	 */
	getDirection( v ) {

		return v.set( 0, 0, - 1 ).applyQuaternion( this.object.quaternion );

	}

	/**
	 * Moves the camera forward parallel to the xz-plane. Assumes camera.up is y-up.
	 *
	 * @param {number} distance - The signed distance.
	 */
	moveForward( distance ) {

		if ( this.enabled === false ) return;

		// move forward parallel to the xz-plane
		// assumes camera.up is y-up

		const camera = this.object;

		_vector.setFromMatrixColumn( camera.matrix, 0 );

		_vector.crossVectors( camera.up, _vector );

		camera.position.addScaledVector( _vector, distance );

	}

	/**
	 * Moves the camera sidewards parallel to the xz-plane.
	 *
	 * @param {number} distance - The signed distance.
	 */
	moveRight( distance ) {

		if ( this.enabled === false ) return;

		const camera = this.object;

		_vector.setFromMatrixColumn( camera.matrix, 0 );

		camera.position.addScaledVector( _vector, distance );

	}

	/**
	 * Activates the pointer lock.
	 *
	 * @param {boolean} [unadjustedMovement=false] - Disables OS-level adjustment for mouse acceleration, and accesses raw mouse input instead.
	 * Setting it to true will disable mouse acceleration.
	 */
	lock( unadjustedMovement = false ) {

		this.domElement.requestPointerLock( {
			unadjustedMovement
		} );

	}

	/**
	 * Exits the pointer lock.
	 */
	unlock() {

		this.domElement.ownerDocument.exitPointerLock();

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

		this.domElement.ownerDocument.addEventListener( 'mousemove', this._onMouseMove );
		this.domElement.ownerDocument.addEventListener( 'pointerlockchange', this._onPointerlockChange );
		this.domElement.ownerDocument.addEventListener( 'pointerlockerror', this._onPointerlockError );

	}
```
</details>

##### `disconnect(): void`

<details><summary>Code</summary>

```ts
disconnect() {

		this.domElement.ownerDocument.removeEventListener( 'mousemove', this._onMouseMove );
		this.domElement.ownerDocument.removeEventListener( 'pointerlockchange', this._onPointerlockChange );
		this.domElement.ownerDocument.removeEventListener( 'pointerlockerror', this._onPointerlockError );

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

##### `getObject(): any`

<details><summary>Code</summary>

```ts
getObject() {

		console.warn( 'THREE.PointerLockControls: getObject() has been deprecated. Use controls.object instead.' ); // @deprecated r169

		return this.object;

	}
```
</details>

##### `getDirection(v: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getDirection( v ) {

		return v.set( 0, 0, - 1 ).applyQuaternion( this.object.quaternion );

	}
```
</details>

##### `moveForward(distance: number): void`

<details><summary>Code</summary>

```ts
moveForward( distance ) {

		if ( this.enabled === false ) return;

		// move forward parallel to the xz-plane
		// assumes camera.up is y-up

		const camera = this.object;

		_vector.setFromMatrixColumn( camera.matrix, 0 );

		_vector.crossVectors( camera.up, _vector );

		camera.position.addScaledVector( _vector, distance );

	}
```
</details>

##### `moveRight(distance: number): void`

<details><summary>Code</summary>

```ts
moveRight( distance ) {

		if ( this.enabled === false ) return;

		const camera = this.object;

		_vector.setFromMatrixColumn( camera.matrix, 0 );

		camera.position.addScaledVector( _vector, distance );

	}
```
</details>

##### `lock(unadjustedMovement: boolean): void`

<details><summary>Code</summary>

```ts
lock( unadjustedMovement = false ) {

		this.domElement.requestPointerLock( {
			unadjustedMovement
		} );

	}
```
</details>

##### `unlock(): void`

<details><summary>Code</summary>

```ts
unlock() {

		this.domElement.ownerDocument.exitPointerLock();

	}
```
</details>


---