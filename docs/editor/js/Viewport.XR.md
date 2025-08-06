[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Viewport.XR.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 15 |
| ⚡ Async/Await Patterns | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/Viewport.XR.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `HTMLMesh` | `three/addons/interactive/HTMLMesh.js` |
| `InteractiveGroup` | `three/addons/interactive/InteractiveGroup.js` |
| `XRControllerModelFactory` | `three/addons/webxr/XRControllerModelFactory.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `selector` | `any` | let/var | `editor.selector` | ✗ |
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `controllers` | `any` | let/var | `null` | ✗ |
| `group` | `any` | let/var | `null` | ✗ |
| `renderer` | `any` | let/var | `null` | ✗ |
| `camera` | `any` | let/var | `new THREE.PerspectiveCamera()` | ✗ |
| `geometry` | `any` | let/var | `new THREE.BufferGeometry()` | ✗ |
| `line` | `any` | let/var | `new THREE.Line( geometry )` | ✗ |
| `raycaster` | `any` | let/var | `new THREE.Raycaster()` | ✗ |
| `controller` | `any` | let/var | `event.target` | ✗ |
| `intersect` | `any` | let/var | `intersects[ 0 ]` | ✗ |
| `controller` | `any` | let/var | `event.target` | ✗ |
| `controllerModelFactory` | `any` | let/var | `new XRControllerModelFactory()` | ✗ |
| `mesh` | `any` | let/var | `new HTMLMesh( sidebar )` | ✗ |
| `sessionInit` | `{ optionalFeatures: string[]; }` | let/var | `{ optionalFeatures: [ 'local-floor' ] }` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `onSessionStarted` | renderer.xr.setSession( session ) | *none* |
| async-function | `onSessionEnded` | *none* | *none* |


---

## Functions

### `onSessionStarted(session: any): Promise<void>`

**Parameters:**

- **`session`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `camera.copy`
- `document.getElementById`
- `geometry.setAttribute`
- `controller1.add`
- `controller2.add`
- `raycaster.setFromXRController`
- `selector.getIntersects`
- `signals.intersectionsDetected.dispatch`
- `controls.getRaycaster().setFromXRController`
- `controls.pointerDown`
- `controls.pointerUp`
- `controls.pointerHover`
- `controls.pointerMove`
- `renderer.xr.getController`
- `controller1.addEventListener`
- `controllers.add`
- `controller2.addEventListener`
- `renderer.xr.getControllerGrip`
- `controllerGrip1.add`
- `controllerModelFactory.createControllerModel`
- `controllerGrip2.add`
- `mesh.position.set`
- `group.add`
- `group.listenToXRControllerEvents`
- `editor.sceneHelpers.add`
- `renderer.xr.addEventListener`
- `renderer.xr.setSession`

**Internal Comments:**
```
// (x3)
// Ignore menu clicks (x2)
// menu (x3)
```

<details><summary>Code</summary>

```typescript
async ( session ) => {

			camera.copy( editor.camera );

			const sidebar = document.getElementById( 'sidebar' );
			sidebar.style.width = '350px';
			sidebar.style.height = '700px';

			//

			if ( controllers === null ) {

				const geometry = new THREE.BufferGeometry();
				geometry.setAttribute( 'position', new THREE.Float32BufferAttribute( [ 0, 0, 0, 0, 0, - 5 ], 3 ) );

				const line = new THREE.Line( geometry );

				const raycaster = new THREE.Raycaster();

				function onSelect( event ) {

					const controller = event.target;

					controller1.userData.active = false;
					controller2.userData.active = false;

					if ( controller === controller1 ) {

						controller1.userData.active = true;
						controller1.add( line );

					}

					if ( controller === controller2 ) {

						controller2.userData.active = true;
						controller2.add( line );

					}

					raycaster.setFromXRController( controller );

					const intersects = selector.getIntersects( raycaster );

					if ( intersects.length > 0 ) {

						// Ignore menu clicks

						const intersect = intersects[ 0 ];
						if ( intersect.object === group.children[ 0 ] ) return;

					}

					signals.intersectionsDetected.dispatch( intersects );

				}

				function onControllerEvent( event ) {

					const controller = event.target;

					if ( controller.userData.active === false ) return;

					controls.getRaycaster().setFromXRController( controller );

					switch ( event.type ) {

						case 'selectstart':
							controls.pointerDown( null );
							break;

						case 'selectend':
							controls.pointerUp( null );
							break;

						case 'move':
							controls.pointerHover( null );
							controls.pointerMove( null );
							break;

					}

				}

				controllers = new THREE.Group();

				const controller1 = renderer.xr.getController( 0 );
				controller1.addEventListener( 'select', onSelect );
				controller1.addEventListener( 'selectstart', onControllerEvent );
				controller1.addEventListener( 'selectend', onControllerEvent );
				controller1.addEventListener( 'move', onControllerEvent );
				controller1.userData.active = false;
				controllers.add( controller1 );

				const controller2 = renderer.xr.getController( 1 );
				controller2.addEventListener( 'select', onSelect );
				controller2.addEventListener( 'selectstart', onControllerEvent );
				controller2.addEventListener( 'selectend', onControllerEvent );
				controller2.addEventListener( 'move', onControllerEvent );
				controller2.userData.active = true;
				controllers.add( controller2 );

				//

				const controllerModelFactory = new XRControllerModelFactory();

				const controllerGrip1 = renderer.xr.getControllerGrip( 0 );
				controllerGrip1.add( controllerModelFactory.createControllerModel( controllerGrip1 ) );
				controllers.add( controllerGrip1 );

				const controllerGrip2 = renderer.xr.getControllerGrip( 1 );
				controllerGrip2.add( controllerModelFactory.createControllerModel( controllerGrip2 ) );
				controllers.add( controllerGrip2 );

				// menu

				group = new InteractiveGroup();

				const mesh = new HTMLMesh( sidebar );
				mesh.name = 'picker'; // Make Selector be aware of the menu
				mesh.position.set( 0.5, 1.0, - 0.5 );
				mesh.rotation.y = - 0.5;
				group.add( mesh );

				group.listenToXRControllerEvents( controller1 );
				group.listenToXRControllerEvents( controller2 );

			}

			editor.sceneHelpers.add( group );
			editor.sceneHelpers.add( controllers );

			renderer.xr.enabled = true;
			renderer.xr.addEventListener( 'sessionend', onSessionEnded );

			await renderer.xr.setSession( session );

		}
```
</details>

### `onSelect(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `controller1.add`
- `controller2.add`
- `raycaster.setFromXRController`
- `selector.getIntersects`
- `signals.intersectionsDetected.dispatch`

**Internal Comments:**
```
// Ignore menu clicks (x2)
```

<details><summary>Code</summary>

```typescript
function onSelect( event ) {

					const controller = event.target;

					controller1.userData.active = false;
					controller2.userData.active = false;

					if ( controller === controller1 ) {

						controller1.userData.active = true;
						controller1.add( line );

					}

					if ( controller === controller2 ) {

						controller2.userData.active = true;
						controller2.add( line );

					}

					raycaster.setFromXRController( controller );

					const intersects = selector.getIntersects( raycaster );

					if ( intersects.length > 0 ) {

						// Ignore menu clicks

						const intersect = intersects[ 0 ];
						if ( intersect.object === group.children[ 0 ] ) return;

					}

					signals.intersectionsDetected.dispatch( intersects );

				}
```
</details>

### `onControllerEvent(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `controls.getRaycaster().setFromXRController`
- `controls.pointerDown`
- `controls.pointerUp`
- `controls.pointerHover`
- `controls.pointerMove`

<details><summary>Code</summary>

```typescript
function onControllerEvent( event ) {

					const controller = event.target;

					if ( controller.userData.active === false ) return;

					controls.getRaycaster().setFromXRController( controller );

					switch ( event.type ) {

						case 'selectstart':
							controls.pointerDown( null );
							break;

						case 'selectend':
							controls.pointerUp( null );
							break;

						case 'move':
							controls.pointerHover( null );
							controls.pointerMove( null );
							break;

					}

				}
```
</details>

### `onSessionEnded(): Promise<void>`

**Returns:** `Promise<void>`

**Calls:**

- `editor.sceneHelpers.remove`
- `document.getElementById`
- `renderer.xr.removeEventListener`
- `editor.camera.copy`
- `signals.windowResize.dispatch`
- `signals.leaveXR.dispatch`

<details><summary>Code</summary>

```typescript
async () => {

			editor.sceneHelpers.remove( group );
			editor.sceneHelpers.remove( controllers );

			const sidebar = document.getElementById( 'sidebar' );
			sidebar.style.width = '';
			sidebar.style.height = '';

			renderer.xr.removeEventListener( 'sessionend', onSessionEnded );
			renderer.xr.enabled = false;

			editor.camera.copy( camera );

			signals.windowResize.dispatch();
			signals.leaveXR.dispatch();

		}
```
</details>


---

## Classes

### `XR`

<details><summary>Class Code</summary>

```ts
class XR {

	constructor( editor, controls ) {

		const selector = editor.selector;
		const signals = editor.signals;

		let controllers = null;
		let group = null;
		let renderer = null;

		const camera = new THREE.PerspectiveCamera();

		const onSessionStarted = async ( session ) => {

			camera.copy( editor.camera );

			const sidebar = document.getElementById( 'sidebar' );
			sidebar.style.width = '350px';
			sidebar.style.height = '700px';

			//

			if ( controllers === null ) {

				const geometry = new THREE.BufferGeometry();
				geometry.setAttribute( 'position', new THREE.Float32BufferAttribute( [ 0, 0, 0, 0, 0, - 5 ], 3 ) );

				const line = new THREE.Line( geometry );

				const raycaster = new THREE.Raycaster();

				function onSelect( event ) {

					const controller = event.target;

					controller1.userData.active = false;
					controller2.userData.active = false;

					if ( controller === controller1 ) {

						controller1.userData.active = true;
						controller1.add( line );

					}

					if ( controller === controller2 ) {

						controller2.userData.active = true;
						controller2.add( line );

					}

					raycaster.setFromXRController( controller );

					const intersects = selector.getIntersects( raycaster );

					if ( intersects.length > 0 ) {

						// Ignore menu clicks

						const intersect = intersects[ 0 ];
						if ( intersect.object === group.children[ 0 ] ) return;

					}

					signals.intersectionsDetected.dispatch( intersects );

				}

				function onControllerEvent( event ) {

					const controller = event.target;

					if ( controller.userData.active === false ) return;

					controls.getRaycaster().setFromXRController( controller );

					switch ( event.type ) {

						case 'selectstart':
							controls.pointerDown( null );
							break;

						case 'selectend':
							controls.pointerUp( null );
							break;

						case 'move':
							controls.pointerHover( null );
							controls.pointerMove( null );
							break;

					}

				}

				controllers = new THREE.Group();

				const controller1 = renderer.xr.getController( 0 );
				controller1.addEventListener( 'select', onSelect );
				controller1.addEventListener( 'selectstart', onControllerEvent );
				controller1.addEventListener( 'selectend', onControllerEvent );
				controller1.addEventListener( 'move', onControllerEvent );
				controller1.userData.active = false;
				controllers.add( controller1 );

				const controller2 = renderer.xr.getController( 1 );
				controller2.addEventListener( 'select', onSelect );
				controller2.addEventListener( 'selectstart', onControllerEvent );
				controller2.addEventListener( 'selectend', onControllerEvent );
				controller2.addEventListener( 'move', onControllerEvent );
				controller2.userData.active = true;
				controllers.add( controller2 );

				//

				const controllerModelFactory = new XRControllerModelFactory();

				const controllerGrip1 = renderer.xr.getControllerGrip( 0 );
				controllerGrip1.add( controllerModelFactory.createControllerModel( controllerGrip1 ) );
				controllers.add( controllerGrip1 );

				const controllerGrip2 = renderer.xr.getControllerGrip( 1 );
				controllerGrip2.add( controllerModelFactory.createControllerModel( controllerGrip2 ) );
				controllers.add( controllerGrip2 );

				// menu

				group = new InteractiveGroup();

				const mesh = new HTMLMesh( sidebar );
				mesh.name = 'picker'; // Make Selector be aware of the menu
				mesh.position.set( 0.5, 1.0, - 0.5 );
				mesh.rotation.y = - 0.5;
				group.add( mesh );

				group.listenToXRControllerEvents( controller1 );
				group.listenToXRControllerEvents( controller2 );

			}

			editor.sceneHelpers.add( group );
			editor.sceneHelpers.add( controllers );

			renderer.xr.enabled = true;
			renderer.xr.addEventListener( 'sessionend', onSessionEnded );

			await renderer.xr.setSession( session );

		};

		const onSessionEnded = async () => {

			editor.sceneHelpers.remove( group );
			editor.sceneHelpers.remove( controllers );

			const sidebar = document.getElementById( 'sidebar' );
			sidebar.style.width = '';
			sidebar.style.height = '';

			renderer.xr.removeEventListener( 'sessionend', onSessionEnded );
			renderer.xr.enabled = false;

			editor.camera.copy( camera );

			signals.windowResize.dispatch();
			signals.leaveXR.dispatch();

		};

		// signals

		const sessionInit = { optionalFeatures: [ 'local-floor' ] };

		signals.enterXR.add( ( mode ) => {

			if ( 'xr' in navigator ) {

				navigator.xr.requestSession( mode, sessionInit )
					.then( onSessionStarted );

			}

		} );

		signals.offerXR.add( function ( mode ) {

			if ( 'xr' in navigator ) {

				navigator.xr.offerSession( mode, sessionInit )
					.then( onSessionStarted );

				signals.leaveXR.add( function () {

					navigator.xr.offerSession( mode, sessionInit )
						.then( onSessionStarted );

				} );

			}

		} );

		signals.rendererCreated.add( ( value ) => {

			renderer = value;

		} );

	}

}
```
</details>


---