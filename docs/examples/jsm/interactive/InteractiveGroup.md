[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `InteractiveGroup.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/interactive/InteractiveGroup.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Group` | `three` |
| `Raycaster` | `three` |
| `Vector2` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_pointer` | `any` | let/var | `new Vector2()` | ✗ |
| `_event` | `{ type: string; data: any; }` | let/var | `{ type: '', data: _pointer }` | ✗ |
| `_events` | `{ move: string; select: string; selec...` | let/var | `{ 'move': 'mousemove', 'select': 'click', 'selectstart': 'mousedown', 'select...` | ✗ |
| `_raycaster` | `any` | let/var | `new Raycaster()` | ✗ |
| `intersection` | `any` | let/var | `intersects[ 0 ]` | ✗ |
| `object` | `any` | let/var | `intersection.object` | ✗ |
| `uv` | `any` | let/var | `intersection.uv` | ✗ |
| `controller` | `any` | let/var | `event.target` | ✗ |
| `intersection` | `any` | let/var | `intersections[ 0 ]` | ✗ |
| `object` | `any` | let/var | `intersection.object` | ✗ |
| `uv` | `any` | let/var | `intersection.uv` | ✗ |


---

## Functions

### `InteractiveGroup.onPointerEvent(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `event.stopPropagation`
- `this.element.getBoundingClientRect`
- `this.raycaster.setFromCamera`
- `this.raycaster.intersectObjects`
- `_event.data.set`
- `object.dispatchEvent`

<details><summary>Code</summary>

```typescript
onPointerEvent( event ) {

		event.stopPropagation();

		const rect = this.element.getBoundingClientRect();

		_pointer.x = ( event.clientX - rect.left ) / rect.width * 2 - 1;
		_pointer.y = - ( event.clientY - rect.top ) / rect.height * 2 + 1;

		this.raycaster.setFromCamera( _pointer, this.camera );

		const intersects = this.raycaster.intersectObjects( this.children, false );

		if ( intersects.length > 0 ) {

			const intersection = intersects[ 0 ];

			const object = intersection.object;
			const uv = intersection.uv;

			_event.type = event.type;
			_event.data.set( uv.x, 1 - uv.y );

			object.dispatchEvent( _event );

		}

	}
```
</details>

### `InteractiveGroup.onXRControllerEvent(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `_raycaster.setFromXRController`
- `_raycaster.intersectObjects`
- `_event.data.set`
- `object.dispatchEvent`

<details><summary>Code</summary>

```typescript
onXRControllerEvent( event ) {

		const controller = event.target;

		_raycaster.setFromXRController( controller );

		const intersections = _raycaster.intersectObjects( this.children, false );

		if ( intersections.length > 0 ) {

			const intersection = intersections[ 0 ];

			const object = intersection.object;
			const uv = intersection.uv;

			_event.type = _events[ event.type ];
			_event.data.set( uv.x, 1 - uv.y );

			object.dispatchEvent( _event );

		}

	}
```
</details>

### `InteractiveGroup.listenToPointerEvents(renderer: any, camera: Camera): void`

**JSDoc:**
```typescript
/**
	 * Calling this method makes sure the interactive group listens to Pointer and Mouse events.
	 * The target is the `domElement` of the given renderer. The camera is required for the internal
	 * raycasting so 3D objects can be detected based on the events.
	 *
	 * @param {(WebGPURenderer|WebGLRenderer)} renderer - The renderer.
	 * @param {Camera} camera - The camera.
	 */
```

**Parameters:**

- **`renderer`** `any`
- **`camera`** `Camera`

**Returns:** `void`

**Calls:**

- `this.element.addEventListener`

<details><summary>Code</summary>

```typescript
listenToPointerEvents( renderer, camera ) {

		this.camera = camera;
		this.element = renderer.domElement;

		this.element.addEventListener( 'pointerdown', this._onPointerEvent );
		this.element.addEventListener( 'pointerup', this._onPointerEvent );
		this.element.addEventListener( 'pointermove', this._onPointerEvent );
		this.element.addEventListener( 'mousedown', this._onPointerEvent );
		this.element.addEventListener( 'mouseup', this._onPointerEvent );
		this.element.addEventListener( 'mousemove', this._onPointerEvent );
		this.element.addEventListener( 'click', this._onPointerEvent );

	}
```
</details>

### `InteractiveGroup.disconnectionPointerEvents(): void`

**JSDoc:**
```typescript
/**
	 * Disconnects this interactive group from all Pointer and Mouse Events.
	 */
```

**Returns:** `void`

**Calls:**

- `this.element.removeEventListener`

<details><summary>Code</summary>

```typescript
disconnectionPointerEvents() {

		if ( this.element !== null ) {

			this.element.removeEventListener( 'pointerdown', this._onPointerEvent );
			this.element.removeEventListener( 'pointerup', this._onPointerEvent );
			this.element.removeEventListener( 'pointermove', this._onPointerEvent );
			this.element.removeEventListener( 'mousedown', this._onPointerEvent );
			this.element.removeEventListener( 'mouseup', this._onPointerEvent );
			this.element.removeEventListener( 'mousemove', this._onPointerEvent );
			this.element.removeEventListener( 'click', this._onPointerEvent );

		}

	}
```
</details>

### `InteractiveGroup.listenToXRControllerEvents(controller: Group): void`

**JSDoc:**
```typescript
/**
	 * Calling this method makes sure the interactive group listens to events of
	 * the given XR controller.
	 *
	 * @param {Group} controller - The XR controller.
	 */
```

**Parameters:**

- **`controller`** `Group`

**Returns:** `void`

**Calls:**

- `this.controllers.push`
- `controller.addEventListener`

<details><summary>Code</summary>

```typescript
listenToXRControllerEvents( controller ) {

		this.controllers.push( controller );
		controller.addEventListener( 'move', this._onXRControllerEvent );
		controller.addEventListener( 'select', this._onXRControllerEvent );
		controller.addEventListener( 'selectstart', this._onXRControllerEvent );
		controller.addEventListener( 'selectend', this._onXRControllerEvent );

	}
```
</details>

### `InteractiveGroup.disconnectXrControllerEvents(): void`

**JSDoc:**
```typescript
/**
	 * Disconnects this interactive group from all XR controllers.
	 */
```

**Returns:** `void`

**Calls:**

- `controller.removeEventListener`

<details><summary>Code</summary>

```typescript
disconnectXrControllerEvents() {

		for ( const controller of this.controllers ) {

			controller.removeEventListener( 'move', this._onXRControllerEvent );
			controller.removeEventListener( 'select', this._onXRControllerEvent );
			controller.removeEventListener( 'selectstart', this._onXRControllerEvent );
			controller.removeEventListener( 'selectend', this._onXRControllerEvent );

		}

	}
```
</details>

### `InteractiveGroup.disconnect(): void`

**JSDoc:**
```typescript
/**
	 * Disconnects this interactive group from the DOM and all XR controllers.
	 */
```

**Returns:** `void`

**Calls:**

- `this.disconnectionPointerEvents`
- `this.disconnectXrControllerEvents`

<details><summary>Code</summary>

```typescript
disconnect() {

		this.disconnectionPointerEvents();
		this.disconnectXrControllerEvents();

		this.camera = null;
		this.element = null;

		this.controllers = [];

	}
```
</details>


---

## Classes

### `InteractiveGroup`

<details><summary>Class Code</summary>

```ts
class InteractiveGroup extends Group {

	constructor() {

		super();

		/**
		 * The internal raycaster.
		 *
		 * @type {Raycaster}
		 */
		this.raycaster = new Raycaster();

		/**
		 * The internal raycaster.
		 *
		 * @type {?HTMLDOMElement}
		 * @default null
		 */
		this.element = null;

		/**
		 * The camera used for raycasting.
		 *
		 * @type {?Camera}
		 * @default null
		 */
		this.camera = null;

		/**
		 * An array of XR controllers.
		 *
		 * @type {Array<Group>}
		 */
		this.controllers = [];

		this._onPointerEvent = this.onPointerEvent.bind( this );
		this._onXRControllerEvent = this.onXRControllerEvent.bind( this );

	}

	onPointerEvent( event ) {

		event.stopPropagation();

		const rect = this.element.getBoundingClientRect();

		_pointer.x = ( event.clientX - rect.left ) / rect.width * 2 - 1;
		_pointer.y = - ( event.clientY - rect.top ) / rect.height * 2 + 1;

		this.raycaster.setFromCamera( _pointer, this.camera );

		const intersects = this.raycaster.intersectObjects( this.children, false );

		if ( intersects.length > 0 ) {

			const intersection = intersects[ 0 ];

			const object = intersection.object;
			const uv = intersection.uv;

			_event.type = event.type;
			_event.data.set( uv.x, 1 - uv.y );

			object.dispatchEvent( _event );

		}

	}

	onXRControllerEvent( event ) {

		const controller = event.target;

		_raycaster.setFromXRController( controller );

		const intersections = _raycaster.intersectObjects( this.children, false );

		if ( intersections.length > 0 ) {

			const intersection = intersections[ 0 ];

			const object = intersection.object;
			const uv = intersection.uv;

			_event.type = _events[ event.type ];
			_event.data.set( uv.x, 1 - uv.y );

			object.dispatchEvent( _event );

		}

	}

	/**
	 * Calling this method makes sure the interactive group listens to Pointer and Mouse events.
	 * The target is the `domElement` of the given renderer. The camera is required for the internal
	 * raycasting so 3D objects can be detected based on the events.
	 *
	 * @param {(WebGPURenderer|WebGLRenderer)} renderer - The renderer.
	 * @param {Camera} camera - The camera.
	 */
	listenToPointerEvents( renderer, camera ) {

		this.camera = camera;
		this.element = renderer.domElement;

		this.element.addEventListener( 'pointerdown', this._onPointerEvent );
		this.element.addEventListener( 'pointerup', this._onPointerEvent );
		this.element.addEventListener( 'pointermove', this._onPointerEvent );
		this.element.addEventListener( 'mousedown', this._onPointerEvent );
		this.element.addEventListener( 'mouseup', this._onPointerEvent );
		this.element.addEventListener( 'mousemove', this._onPointerEvent );
		this.element.addEventListener( 'click', this._onPointerEvent );

	}

	/**
	 * Disconnects this interactive group from all Pointer and Mouse Events.
	 */
	disconnectionPointerEvents() {

		if ( this.element !== null ) {

			this.element.removeEventListener( 'pointerdown', this._onPointerEvent );
			this.element.removeEventListener( 'pointerup', this._onPointerEvent );
			this.element.removeEventListener( 'pointermove', this._onPointerEvent );
			this.element.removeEventListener( 'mousedown', this._onPointerEvent );
			this.element.removeEventListener( 'mouseup', this._onPointerEvent );
			this.element.removeEventListener( 'mousemove', this._onPointerEvent );
			this.element.removeEventListener( 'click', this._onPointerEvent );

		}

	}

	/**
	 * Calling this method makes sure the interactive group listens to events of
	 * the given XR controller.
	 *
	 * @param {Group} controller - The XR controller.
	 */
	listenToXRControllerEvents( controller ) {

		this.controllers.push( controller );
		controller.addEventListener( 'move', this._onXRControllerEvent );
		controller.addEventListener( 'select', this._onXRControllerEvent );
		controller.addEventListener( 'selectstart', this._onXRControllerEvent );
		controller.addEventListener( 'selectend', this._onXRControllerEvent );

	}

	/**
	 * Disconnects this interactive group from all XR controllers.
	 */
	disconnectXrControllerEvents() {

		for ( const controller of this.controllers ) {

			controller.removeEventListener( 'move', this._onXRControllerEvent );
			controller.removeEventListener( 'select', this._onXRControllerEvent );
			controller.removeEventListener( 'selectstart', this._onXRControllerEvent );
			controller.removeEventListener( 'selectend', this._onXRControllerEvent );

		}

	}

	/**
	 * Disconnects this interactive group from the DOM and all XR controllers.
	 */
	disconnect() {

		this.disconnectionPointerEvents();
		this.disconnectXrControllerEvents();

		this.camera = null;
		this.element = null;

		this.controllers = [];

	}

}
```
</details>

#### Methods

##### `onPointerEvent(event: any): void`

<details><summary>Code</summary>

```ts
onPointerEvent( event ) {

		event.stopPropagation();

		const rect = this.element.getBoundingClientRect();

		_pointer.x = ( event.clientX - rect.left ) / rect.width * 2 - 1;
		_pointer.y = - ( event.clientY - rect.top ) / rect.height * 2 + 1;

		this.raycaster.setFromCamera( _pointer, this.camera );

		const intersects = this.raycaster.intersectObjects( this.children, false );

		if ( intersects.length > 0 ) {

			const intersection = intersects[ 0 ];

			const object = intersection.object;
			const uv = intersection.uv;

			_event.type = event.type;
			_event.data.set( uv.x, 1 - uv.y );

			object.dispatchEvent( _event );

		}

	}
```
</details>

##### `onXRControllerEvent(event: any): void`

<details><summary>Code</summary>

```ts
onXRControllerEvent( event ) {

		const controller = event.target;

		_raycaster.setFromXRController( controller );

		const intersections = _raycaster.intersectObjects( this.children, false );

		if ( intersections.length > 0 ) {

			const intersection = intersections[ 0 ];

			const object = intersection.object;
			const uv = intersection.uv;

			_event.type = _events[ event.type ];
			_event.data.set( uv.x, 1 - uv.y );

			object.dispatchEvent( _event );

		}

	}
```
</details>

##### `listenToPointerEvents(renderer: any, camera: Camera): void`

<details><summary>Code</summary>

```ts
listenToPointerEvents( renderer, camera ) {

		this.camera = camera;
		this.element = renderer.domElement;

		this.element.addEventListener( 'pointerdown', this._onPointerEvent );
		this.element.addEventListener( 'pointerup', this._onPointerEvent );
		this.element.addEventListener( 'pointermove', this._onPointerEvent );
		this.element.addEventListener( 'mousedown', this._onPointerEvent );
		this.element.addEventListener( 'mouseup', this._onPointerEvent );
		this.element.addEventListener( 'mousemove', this._onPointerEvent );
		this.element.addEventListener( 'click', this._onPointerEvent );

	}
```
</details>

##### `disconnectionPointerEvents(): void`

<details><summary>Code</summary>

```ts
disconnectionPointerEvents() {

		if ( this.element !== null ) {

			this.element.removeEventListener( 'pointerdown', this._onPointerEvent );
			this.element.removeEventListener( 'pointerup', this._onPointerEvent );
			this.element.removeEventListener( 'pointermove', this._onPointerEvent );
			this.element.removeEventListener( 'mousedown', this._onPointerEvent );
			this.element.removeEventListener( 'mouseup', this._onPointerEvent );
			this.element.removeEventListener( 'mousemove', this._onPointerEvent );
			this.element.removeEventListener( 'click', this._onPointerEvent );

		}

	}
```
</details>

##### `listenToXRControllerEvents(controller: Group): void`

<details><summary>Code</summary>

```ts
listenToXRControllerEvents( controller ) {

		this.controllers.push( controller );
		controller.addEventListener( 'move', this._onXRControllerEvent );
		controller.addEventListener( 'select', this._onXRControllerEvent );
		controller.addEventListener( 'selectstart', this._onXRControllerEvent );
		controller.addEventListener( 'selectend', this._onXRControllerEvent );

	}
```
</details>

##### `disconnectXrControllerEvents(): void`

<details><summary>Code</summary>

```ts
disconnectXrControllerEvents() {

		for ( const controller of this.controllers ) {

			controller.removeEventListener( 'move', this._onXRControllerEvent );
			controller.removeEventListener( 'select', this._onXRControllerEvent );
			controller.removeEventListener( 'selectstart', this._onXRControllerEvent );
			controller.removeEventListener( 'selectend', this._onXRControllerEvent );

		}

	}
```
</details>

##### `disconnect(): void`

<details><summary>Code</summary>

```ts
disconnect() {

		this.disconnectionPointerEvents();
		this.disconnectXrControllerEvents();

		this.camera = null;
		this.element = null;

		this.controllers = [];

	}
```
</details>


---