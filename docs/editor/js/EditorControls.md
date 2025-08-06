[⬅️ Back to Table of Contents](../../index.md)

# 📄 `EditorControls.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 16 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 27 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/EditorControls.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `vector` | `any` | let/var | `new THREE.Vector3()` | ✗ |
| `delta` | `any` | let/var | `new THREE.Vector3()` | ✗ |
| `box` | `any` | let/var | `new THREE.Box3()` | ✗ |
| `STATE` | `{ NONE: number; ROTATE: number; ZOOM:...` | let/var | `{ NONE: - 1, ROTATE: 0, ZOOM: 1, PAN: 2 }` | ✗ |
| `state` | `number` | let/var | `STATE.NONE` | ✗ |
| `center` | `any` | let/var | `this.center` | ✗ |
| `normalMatrix` | `any` | let/var | `new THREE.Matrix3()` | ✗ |
| `pointer` | `any` | let/var | `new THREE.Vector2()` | ✗ |
| `pointerOld` | `any` | let/var | `new THREE.Vector2()` | ✗ |
| `spherical` | `any` | let/var | `new THREE.Spherical()` | ✗ |
| `sphere` | `any` | let/var | `new THREE.Sphere()` | ✗ |
| `pointers` | `any[]` | let/var | `[]` | ✗ |
| `pointerPositions` | `{}` | let/var | `{}` | ✗ |
| `domElement` | `any` | let/var | `null` | ✗ |
| `changeEvent` | `{ type: string; }` | let/var | `{ type: 'change' }` | ✗ |
| `distance` | `any` | let/var | `*not shown*` | ✗ |
| `pointerId` | `any` | let/var | `pointers[ 0 ]` | ✗ |
| `position` | `any` | let/var | `pointerPositions[ pointerId ]` | ✗ |
| `movementX` | `number` | let/var | `pointer.x - pointerOld.x` | ✗ |
| `movementY` | `number` | let/var | `pointer.y - pointerOld.y` | ✗ |
| `touches` | `any[]` | let/var | `[ new THREE.Vector3(), new THREE.Vector3(), new THREE.Vector3() ]` | ✗ |
| `prevTouches` | `any[]` | let/var | `[ new THREE.Vector3(), new THREE.Vector3(), new THREE.Vector3() ]` | ✗ |
| `prevDistance` | `any` | let/var | `null` | ✗ |
| `closest` | `any` | let/var | `touches[ 0 ]` | ✗ |
| `position` | `any` | let/var | `pointerPositions[ event.pointerId ]` | ✗ |
| `pointerId` | `any` | let/var | `( event.pointerId === pointers[ 0 ] ) ? pointers[ 1 ] : pointers[ 0 ]` | ✗ |


---

## Functions

### `onPointerDown(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `domElement.setPointerCapture`
- `domElement.ownerDocument.addEventListener`
- `isTrackingPointer`
- `addPointer`
- `onTouchStart`
- `onMouseDown`

**Internal Comments:**
```
// (x4)
```

<details><summary>Code</summary>

```typescript
function onPointerDown( event ) {

			if ( scope.enabled === false ) return;

			if ( pointers.length === 0 ) {

				domElement.setPointerCapture( event.pointerId );

				domElement.ownerDocument.addEventListener( 'pointermove', onPointerMove );
				domElement.ownerDocument.addEventListener( 'pointerup', onPointerUp );

			}

			//

			if ( isTrackingPointer( event ) ) return;

			//

			addPointer( event );

			if ( event.pointerType === 'touch' ) {

				onTouchStart( event );

			} else {

				onMouseDown( event );

			}

		}
```
</details>

### `onPointerMove(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `onTouchMove`
- `onMouseMove`

<details><summary>Code</summary>

```typescript
function onPointerMove( event ) {

			if ( scope.enabled === false ) return;

			if ( event.pointerType === 'touch' ) {

				onTouchMove( event );

			} else {

				onMouseMove( event );

			}

		}
```
</details>

### `onPointerUp(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `removePointer`
- `domElement.releasePointerCapture`
- `domElement.ownerDocument.removeEventListener`
- `onTouchStart`

**Internal Comments:**
```
// minimal placeholder event - allows state correction on pointer-up (x3)
```

<details><summary>Code</summary>

```typescript
function onPointerUp( event ) {

			removePointer( event );

			switch ( pointers.length ) {

				case 0:

					domElement.releasePointerCapture( event.pointerId );

					domElement.ownerDocument.removeEventListener( 'pointermove', onPointerMove );
					domElement.ownerDocument.removeEventListener( 'pointerup', onPointerUp );

					break;

				case 1:

					var pointerId = pointers[ 0 ];
					var position = pointerPositions[ pointerId ];

					// minimal placeholder event - allows state correction on pointer-up
					onTouchStart( { pointerId: pointerId, pageX: position.x, pageY: position.y } );

					break;

			}

		}
```
</details>

### `onMouseDown(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `pointerOld.set`

<details><summary>Code</summary>

```typescript
function onMouseDown( event ) {

			if ( event.button === 0 ) {

				state = STATE.ROTATE;

			} else if ( event.button === 1 ) {

				state = STATE.ZOOM;

			} else if ( event.button === 2 ) {

				state = STATE.PAN;

			}

			pointerOld.set( event.clientX, event.clientY );

		}
```
</details>

### `onMouseMove(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `pointer.set`
- `scope.rotate`
- `delta.set`
- `scope.zoom`
- `scope.pan`
- `pointerOld.set`

<details><summary>Code</summary>

```typescript
function onMouseMove( event ) {

			pointer.set( event.clientX, event.clientY );

			var movementX = pointer.x - pointerOld.x;
			var movementY = pointer.y - pointerOld.y;

			if ( state === STATE.ROTATE ) {

				scope.rotate( delta.set( - movementX, - movementY, 0 ) );

			} else if ( state === STATE.ZOOM ) {

				scope.zoom( delta.set( 0, 0, movementY ) );

			} else if ( state === STATE.PAN ) {

				scope.pan( delta.set( - movementX, movementY, 0 ) );

			}

			pointerOld.set( event.clientX, event.clientY );

		}
```
</details>

### `onMouseUp(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function onMouseUp() {

			state = STATE.NONE;

		}
```
</details>

### `onMouseWheel(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `event.preventDefault`
- `scope.zoom`
- `delta.set`

**Internal Comments:**
```
// Normalize deltaY due to https://bugzilla.mozilla.org/show_bug.cgi?id=1392460 (x4)
```

<details><summary>Code</summary>

```typescript
function onMouseWheel( event ) {

			if ( scope.enabled === false ) return;

			event.preventDefault();

			// Normalize deltaY due to https://bugzilla.mozilla.org/show_bug.cgi?id=1392460
			scope.zoom( delta.set( 0, 0, event.deltaY > 0 ? 1 : - 1 ) );

		}
```
</details>

### `contextmenu(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `event.preventDefault`

<details><summary>Code</summary>

```typescript
function contextmenu( event ) {

			event.preventDefault();

		}
```
</details>

### `onTouchStart(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `trackPointer`
- `touches[ 0 ].set( event.pageX, event.pageY, 0 ).divideScalar`
- `touches[ 1 ].set( event.pageX, event.pageY, 0 ).divideScalar`
- `getSecondPointerPosition`
- `touches[ 1 ].set( position.x, position.y, 0 ).divideScalar`
- `touches[ 0 ].distanceTo`
- `prevTouches[ 0 ].copy`
- `prevTouches[ 1 ].copy`

<details><summary>Code</summary>

```typescript
function onTouchStart( event ) {

			trackPointer( event );

			switch ( pointers.length ) {

				case 1:
					touches[ 0 ].set( event.pageX, event.pageY, 0 ).divideScalar( window.devicePixelRatio );
					touches[ 1 ].set( event.pageX, event.pageY, 0 ).divideScalar( window.devicePixelRatio );
					break;

				case 2:

					var position = getSecondPointerPosition( event );

					touches[ 0 ].set( event.pageX, event.pageY, 0 ).divideScalar( window.devicePixelRatio );
					touches[ 1 ].set( position.x, position.y, 0 ).divideScalar( window.devicePixelRatio );
					prevDistance = touches[ 0 ].distanceTo( touches[ 1 ] );
					break;

			}

			prevTouches[ 0 ].copy( touches[ 0 ] );
			prevTouches[ 1 ].copy( touches[ 1 ] );

		}
```
</details>

### `onTouchMove(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `trackPointer`
- `closest.distanceTo`
- `touch2.distanceTo`
- `touches[ 0 ].set( event.pageX, event.pageY, 0 ).divideScalar`
- `touches[ 1 ].set( event.pageX, event.pageY, 0 ).divideScalar`
- `scope.rotate`
- `touches[ 0 ].sub( getClosest( touches[ 0 ], prevTouches ) ).multiplyScalar`
- `getSecondPointerPosition`
- `touches[ 1 ].set( position.x, position.y, 0 ).divideScalar`
- `touches[ 0 ].distanceTo`
- `scope.zoom`
- `delta.set`
- `touches[ 0 ].clone().sub`
- `getClosest`
- `touches[ 1 ].clone().sub`
- `scope.pan`
- `offset0.add`
- `prevTouches[ 0 ].copy`
- `prevTouches[ 1 ].copy`

<details><summary>Code</summary>

```typescript
function onTouchMove( event ) {

			trackPointer( event );

			function getClosest( touch, touches ) {

				var closest = touches[ 0 ];

				for ( var touch2 of touches ) {

					if ( closest.distanceTo( touch ) > touch2.distanceTo( touch ) ) closest = touch2;

				}

				return closest;

			}

			switch ( pointers.length ) {

				case 1:
					touches[ 0 ].set( event.pageX, event.pageY, 0 ).divideScalar( window.devicePixelRatio );
					touches[ 1 ].set( event.pageX, event.pageY, 0 ).divideScalar( window.devicePixelRatio );
					scope.rotate( touches[ 0 ].sub( getClosest( touches[ 0 ], prevTouches ) ).multiplyScalar( - 1 ) );
					break;

				case 2:

					var position = getSecondPointerPosition( event );

					touches[ 0 ].set( event.pageX, event.pageY, 0 ).divideScalar( window.devicePixelRatio );
					touches[ 1 ].set( position.x, position.y, 0 ).divideScalar( window.devicePixelRatio );
					var distance = touches[ 0 ].distanceTo( touches[ 1 ] );
					scope.zoom( delta.set( 0, 0, prevDistance - distance ) );
					prevDistance = distance;


					var offset0 = touches[ 0 ].clone().sub( getClosest( touches[ 0 ], prevTouches ) );
					var offset1 = touches[ 1 ].clone().sub( getClosest( touches[ 1 ], prevTouches ) );
					offset0.x = - offset0.x;
					offset1.x = - offset1.x;

					scope.pan( offset0.add( offset1 ) );

					break;

			}

			prevTouches[ 0 ].copy( touches[ 0 ] );
			prevTouches[ 1 ].copy( touches[ 1 ] );

		}
```
</details>

### `getClosest(touch: any, touches: any): any`

**Parameters:**

- **`touch`** `any`
- **`touches`** `any`

**Returns:** `any`

**Calls:**

- `closest.distanceTo`
- `touch2.distanceTo`

<details><summary>Code</summary>

```typescript
function getClosest( touch, touches ) {

				var closest = touches[ 0 ];

				for ( var touch2 of touches ) {

					if ( closest.distanceTo( touch ) > touch2.distanceTo( touch ) ) closest = touch2;

				}

				return closest;

			}
```
</details>

### `addPointer(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `pointers.push`

<details><summary>Code</summary>

```typescript
function addPointer( event ) {

			pointers.push( event.pointerId );

		}
```
</details>

### `removePointer(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `pointers.splice`

<details><summary>Code</summary>

```typescript
function removePointer( event ) {

			delete pointerPositions[ event.pointerId ];

			for ( var i = 0; i < pointers.length; i ++ ) {

				if ( pointers[ i ] == event.pointerId ) {

					pointers.splice( i, 1 );
					return;

				}

			}

		}
```
</details>

### `isTrackingPointer(event: any): boolean`

**Parameters:**

- **`event`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isTrackingPointer( event ) {

			for ( var i = 0; i < pointers.length; i ++ ) {

				if ( pointers[ i ] == event.pointerId ) return true;

			}

			return false;

		}
```
</details>

### `trackPointer(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `position.set`

<details><summary>Code</summary>

```typescript
function trackPointer( event ) {

			var position = pointerPositions[ event.pointerId ];

			if ( position === undefined ) {

				position = new THREE.Vector2();
				pointerPositions[ event.pointerId ] = position;

			}

			position.set( event.pageX, event.pageY );

		}
```
</details>

### `getSecondPointerPosition(event: any): any`

**Parameters:**

- **`event`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getSecondPointerPosition( event ) {

			var pointerId = ( event.pointerId === pointers[ 0 ] ) ? pointers[ 1 ] : pointers[ 0 ];

			return pointerPositions[ pointerId ];

		}
```
</details>


---

## Classes

### `EditorControls`

<details><summary>Class Code</summary>

```ts
class EditorControls extends THREE.EventDispatcher {

	constructor( object ) {

		super();

		// API

		this.enabled = true;
		this.center = new THREE.Vector3();
		this.panSpeed = 0.002;
		this.zoomSpeed = 0.1;
		this.rotationSpeed = 0.005;

		// internals

		var scope = this;
		var vector = new THREE.Vector3();
		var delta = new THREE.Vector3();
		var box = new THREE.Box3();

		var STATE = { NONE: - 1, ROTATE: 0, ZOOM: 1, PAN: 2 };
		var state = STATE.NONE;

		var center = this.center;
		var normalMatrix = new THREE.Matrix3();
		var pointer = new THREE.Vector2();
		var pointerOld = new THREE.Vector2();
		var spherical = new THREE.Spherical();
		var sphere = new THREE.Sphere();

		var pointers = [];
		var pointerPositions = {};

		var domElement = null;

		// events

		var changeEvent = { type: 'change' };

		this.focus = function ( target ) {

			var distance;

			box.setFromObject( target );

			if ( box.isEmpty() === false ) {

				box.getCenter( center );
				distance = box.getBoundingSphere( sphere ).radius;

			} else {

				// Focusing on an Group, AmbientLight, etc

				center.setFromMatrixPosition( target.matrixWorld );
				distance = 0.1;

			}

			delta.set( 0, 0, 1 );
			delta.applyQuaternion( object.quaternion );
			delta.multiplyScalar( distance * 4 );

			object.position.copy( center ).add( delta );

			scope.dispatchEvent( changeEvent );

		};

		this.pan = function ( delta ) {

			var distance = object.position.distanceTo( center );

			delta.multiplyScalar( distance * scope.panSpeed );
			delta.applyMatrix3( normalMatrix.getNormalMatrix( object.matrix ) );

			object.position.add( delta );
			center.add( delta );

			scope.dispatchEvent( changeEvent );

		};

		this.zoom = function ( delta ) {

			var distance = object.position.distanceTo( center );

			delta.multiplyScalar( distance * scope.zoomSpeed );

			if ( delta.length() > distance ) return;

			delta.applyMatrix3( normalMatrix.getNormalMatrix( object.matrix ) );

			object.position.add( delta );

			scope.dispatchEvent( changeEvent );

		};

		this.rotate = function ( delta ) {

			vector.copy( object.position ).sub( center );

			spherical.setFromVector3( vector );

			spherical.theta += delta.x * scope.rotationSpeed;
			spherical.phi += delta.y * scope.rotationSpeed;

			spherical.makeSafe();

			vector.setFromSpherical( spherical );

			object.position.copy( center ).add( vector );

			object.lookAt( center );

			scope.dispatchEvent( changeEvent );

		};

		//

		function onPointerDown( event ) {

			if ( scope.enabled === false ) return;

			if ( pointers.length === 0 ) {

				domElement.setPointerCapture( event.pointerId );

				domElement.ownerDocument.addEventListener( 'pointermove', onPointerMove );
				domElement.ownerDocument.addEventListener( 'pointerup', onPointerUp );

			}

			//

			if ( isTrackingPointer( event ) ) return;

			//

			addPointer( event );

			if ( event.pointerType === 'touch' ) {

				onTouchStart( event );

			} else {

				onMouseDown( event );

			}

		}

		function onPointerMove( event ) {

			if ( scope.enabled === false ) return;

			if ( event.pointerType === 'touch' ) {

				onTouchMove( event );

			} else {

				onMouseMove( event );

			}

		}

		function onPointerUp( event ) {

			removePointer( event );

			switch ( pointers.length ) {

				case 0:

					domElement.releasePointerCapture( event.pointerId );

					domElement.ownerDocument.removeEventListener( 'pointermove', onPointerMove );
					domElement.ownerDocument.removeEventListener( 'pointerup', onPointerUp );

					break;

				case 1:

					var pointerId = pointers[ 0 ];
					var position = pointerPositions[ pointerId ];

					// minimal placeholder event - allows state correction on pointer-up
					onTouchStart( { pointerId: pointerId, pageX: position.x, pageY: position.y } );

					break;

			}

		}

		// mouse

		function onMouseDown( event ) {

			if ( event.button === 0 ) {

				state = STATE.ROTATE;

			} else if ( event.button === 1 ) {

				state = STATE.ZOOM;

			} else if ( event.button === 2 ) {

				state = STATE.PAN;

			}

			pointerOld.set( event.clientX, event.clientY );

		}

		function onMouseMove( event ) {

			pointer.set( event.clientX, event.clientY );

			var movementX = pointer.x - pointerOld.x;
			var movementY = pointer.y - pointerOld.y;

			if ( state === STATE.ROTATE ) {

				scope.rotate( delta.set( - movementX, - movementY, 0 ) );

			} else if ( state === STATE.ZOOM ) {

				scope.zoom( delta.set( 0, 0, movementY ) );

			} else if ( state === STATE.PAN ) {

				scope.pan( delta.set( - movementX, movementY, 0 ) );

			}

			pointerOld.set( event.clientX, event.clientY );

		}

		function onMouseUp() {

			state = STATE.NONE;

		}

		function onMouseWheel( event ) {

			if ( scope.enabled === false ) return;

			event.preventDefault();

			// Normalize deltaY due to https://bugzilla.mozilla.org/show_bug.cgi?id=1392460
			scope.zoom( delta.set( 0, 0, event.deltaY > 0 ? 1 : - 1 ) );

		}

		function contextmenu( event ) {

			event.preventDefault();

		}

		this.connect = function ( element ) {

			if ( domElement !== null ) this.disconnect();

			domElement = element;

			domElement.addEventListener( 'contextmenu', contextmenu );
			domElement.addEventListener( 'dblclick', onMouseUp );
			domElement.addEventListener( 'wheel', onMouseWheel, { passive: false } );

			domElement.addEventListener( 'pointerdown', onPointerDown );

		};

		this.disconnect = function () {

			domElement.removeEventListener( 'contextmenu', contextmenu );
			domElement.removeEventListener( 'dblclick', onMouseUp );
			domElement.removeEventListener( 'wheel', onMouseWheel );

			domElement.removeEventListener( 'pointerdown', onPointerDown );

			domElement = null;

		};

		// touch

		var touches = [ new THREE.Vector3(), new THREE.Vector3(), new THREE.Vector3() ];
		var prevTouches = [ new THREE.Vector3(), new THREE.Vector3(), new THREE.Vector3() ];

		var prevDistance = null;

		function onTouchStart( event ) {

			trackPointer( event );

			switch ( pointers.length ) {

				case 1:
					touches[ 0 ].set( event.pageX, event.pageY, 0 ).divideScalar( window.devicePixelRatio );
					touches[ 1 ].set( event.pageX, event.pageY, 0 ).divideScalar( window.devicePixelRatio );
					break;

				case 2:

					var position = getSecondPointerPosition( event );

					touches[ 0 ].set( event.pageX, event.pageY, 0 ).divideScalar( window.devicePixelRatio );
					touches[ 1 ].set( position.x, position.y, 0 ).divideScalar( window.devicePixelRatio );
					prevDistance = touches[ 0 ].distanceTo( touches[ 1 ] );
					break;

			}

			prevTouches[ 0 ].copy( touches[ 0 ] );
			prevTouches[ 1 ].copy( touches[ 1 ] );

		}


		function onTouchMove( event ) {

			trackPointer( event );

			function getClosest( touch, touches ) {

				var closest = touches[ 0 ];

				for ( var touch2 of touches ) {

					if ( closest.distanceTo( touch ) > touch2.distanceTo( touch ) ) closest = touch2;

				}

				return closest;

			}

			switch ( pointers.length ) {

				case 1:
					touches[ 0 ].set( event.pageX, event.pageY, 0 ).divideScalar( window.devicePixelRatio );
					touches[ 1 ].set( event.pageX, event.pageY, 0 ).divideScalar( window.devicePixelRatio );
					scope.rotate( touches[ 0 ].sub( getClosest( touches[ 0 ], prevTouches ) ).multiplyScalar( - 1 ) );
					break;

				case 2:

					var position = getSecondPointerPosition( event );

					touches[ 0 ].set( event.pageX, event.pageY, 0 ).divideScalar( window.devicePixelRatio );
					touches[ 1 ].set( position.x, position.y, 0 ).divideScalar( window.devicePixelRatio );
					var distance = touches[ 0 ].distanceTo( touches[ 1 ] );
					scope.zoom( delta.set( 0, 0, prevDistance - distance ) );
					prevDistance = distance;


					var offset0 = touches[ 0 ].clone().sub( getClosest( touches[ 0 ], prevTouches ) );
					var offset1 = touches[ 1 ].clone().sub( getClosest( touches[ 1 ], prevTouches ) );
					offset0.x = - offset0.x;
					offset1.x = - offset1.x;

					scope.pan( offset0.add( offset1 ) );

					break;

			}

			prevTouches[ 0 ].copy( touches[ 0 ] );
			prevTouches[ 1 ].copy( touches[ 1 ] );

		}

		function addPointer( event ) {

			pointers.push( event.pointerId );

		}

		function removePointer( event ) {

			delete pointerPositions[ event.pointerId ];

			for ( var i = 0; i < pointers.length; i ++ ) {

				if ( pointers[ i ] == event.pointerId ) {

					pointers.splice( i, 1 );
					return;

				}

			}

		}

		function isTrackingPointer( event ) {

			for ( var i = 0; i < pointers.length; i ++ ) {

				if ( pointers[ i ] == event.pointerId ) return true;

			}

			return false;

		}

		function trackPointer( event ) {

			var position = pointerPositions[ event.pointerId ];

			if ( position === undefined ) {

				position = new THREE.Vector2();
				pointerPositions[ event.pointerId ] = position;

			}

			position.set( event.pageX, event.pageY );

		}

		function getSecondPointerPosition( event ) {

			var pointerId = ( event.pointerId === pointers[ 0 ] ) ? pointers[ 1 ] : pointers[ 0 ];

			return pointerPositions[ pointerId ];

		}

	}

}
```
</details>


---