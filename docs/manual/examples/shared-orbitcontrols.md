[⬅️ Back to Table of Contents](../../index.md)

# 📄 `shared-orbitcontrols.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 26 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`manual/examples/shared-orbitcontrols.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `OrbitControls` | `https://cdn.skypack.dev/three@0.136.0/examples/jsm/controls/OrbitControls.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `renderer` | `any` | let/var | `new THREE.WebGLRenderer( { antialias: true, canvas } )` | ✗ |
| `fov` | `75` | let/var | `75` | ✗ |
| `aspect` | `2` | let/var | `2` | ✗ |
| `near` | `0.1` | let/var | `0.1` | ✗ |
| `far` | `100` | let/var | `100` | ✗ |
| `camera` | `any` | let/var | `new THREE.PerspectiveCamera( fov, aspect, near, far )` | ✗ |
| `controls` | `any` | let/var | `new OrbitControls( camera, inputElement )` | ✗ |
| `scene` | `any` | let/var | `new THREE.Scene()` | ✗ |
| `color` | `16777215` | let/var | `0xFFFFFF` | ✗ |
| `intensity` | `1` | let/var | `1` | ✗ |
| `light` | `any` | let/var | `new THREE.DirectionalLight( color, intensity )` | ✗ |
| `boxWidth` | `1` | let/var | `1` | ✗ |
| `boxHeight` | `1` | let/var | `1` | ✗ |
| `boxDepth` | `1` | let/var | `1` | ✗ |
| `geometry` | `any` | let/var | `new THREE.BoxGeometry( boxWidth, boxHeight, boxDepth )` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshPhongMaterial( { color, } )` | ✗ |
| `cube` | `any` | let/var | `new THREE.Mesh( geometry, material )` | ✗ |
| `cubes` | `any[]` | let/var | `[ makeInstance( geometry, 0x44aa88, 0 ), makeInstance( geometry, 0x8844aa, - ...` | ✗ |
| `pickPosition` | `{ x: number; y: number; }` | let/var | `{ x: - 2, y: - 2 }` | ✗ |
| `pickHelper` | `PickHelper` | let/var | `new PickHelper()` | ✗ |
| `canvas` | `any` | let/var | `renderer.domElement` | ✗ |
| `width` | `any` | let/var | `inputElement.clientWidth` | ✗ |
| `height` | `any` | let/var | `inputElement.clientHeight` | ✗ |
| `needResize` | `boolean` | let/var | `canvas.width !== width \|\| canvas.height !== height` | ✗ |
| `speed` | `number` | let/var | `1 + ndx * .1` | ✗ |
| `rot` | `number` | let/var | `time * speed` | ✗ |


---

## Functions

### `init(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `controls.target.set`
- `controls.update`
- `light.position.set`
- `scene.add`
- `makeInstance`
- `this.pickedObject.material.emissive.setHex`
- `this.raycaster.setFromCamera`
- `this.raycaster.intersectObjects`
- `this.pickedObject.material.emissive.getHex`
- `clearPickPosition`
- `renderer.setSize`
- `resizeRendererToDisplaySize`
- `camera.updateProjectionMatrix`
- `cubes.forEach`
- `pickHelper.pick`
- `renderer.render`
- `requestAnimationFrame`
- `inputElement.getBoundingClientRect`
- `getCanvasRelativePosition`
- `inputElement.addEventListener`
- `event.preventDefault`
- `setPickPosition`

**Internal Comments:**
```
// restore the color if there is a picked object
// cast a ray through the frustum (x5)
// get the list of objects the ray intersected (x2)
// pick the first object. It's the closest one (x4)
// save its color (x4)
// set its emissive color to flashing red/yellow (x7)
// unlike the mouse which always has a position (x4)
// if the user stops touching the screen we want (x4)
// to stop picking. For now we just pick a value (x4)
// unlikely to pick something (x4)
// prevent the window from scrolling (x4)
```

<details><summary>Code</summary>

```typescript
export function init( data ) { /* eslint-disable-line no-unused-vars */

	const { canvas, inputElement } = data;
	const renderer = new THREE.WebGLRenderer( { antialias: true, canvas } );

	const fov = 75;
	const aspect = 2; // the canvas default
	const near = 0.1;
	const far = 100;
	const camera = new THREE.PerspectiveCamera( fov, aspect, near, far );
	camera.position.z = 4;

	const controls = new OrbitControls( camera, inputElement );
	controls.target.set( 0, 0, 0 );
	controls.update();

	const scene = new THREE.Scene();

	{

		const color = 0xFFFFFF;
		const intensity = 1;
		const light = new THREE.DirectionalLight( color, intensity );
		light.position.set( - 1, 2, 4 );
		scene.add( light );

	}

	const boxWidth = 1;
	const boxHeight = 1;
	const boxDepth = 1;
	const geometry = new THREE.BoxGeometry( boxWidth, boxHeight, boxDepth );

	function makeInstance( geometry, color, x ) {

		const material = new THREE.MeshPhongMaterial( {
			color,
		} );

		const cube = new THREE.Mesh( geometry, material );
		scene.add( cube );

		cube.position.x = x;

		return cube;

	}

	const cubes = [
		makeInstance( geometry, 0x44aa88, 0 ),
		makeInstance( geometry, 0x8844aa, - 2 ),
		makeInstance( geometry, 0xaa8844, 2 ),
	];

	class PickHelper {

		constructor() {

			this.raycaster = new THREE.Raycaster();
			this.pickedObject = null;
			this.pickedObjectSavedColor = 0;

		}
		pick( normalizedPosition, scene, camera, time ) {

			// restore the color if there is a picked object
			if ( this.pickedObject ) {

				this.pickedObject.material.emissive.setHex( this.pickedObjectSavedColor );
				this.pickedObject = undefined;

			}

			// cast a ray through the frustum
			this.raycaster.setFromCamera( normalizedPosition, camera );
			// get the list of objects the ray intersected
			const intersectedObjects = this.raycaster.intersectObjects( scene.children );
			if ( intersectedObjects.length ) {

				// pick the first object. It's the closest one
				this.pickedObject = intersectedObjects[ 0 ].object;
				// save its color
				this.pickedObjectSavedColor = this.pickedObject.material.emissive.getHex();
				// set its emissive color to flashing red/yellow
				this.pickedObject.material.emissive.setHex( ( time * 8 ) % 2 > 1 ? 0xFFFF00 : 0xFF0000 );

			}

		}

	}

	const pickPosition = { x: - 2, y: - 2 };
	const pickHelper = new PickHelper();
	clearPickPosition();

	function resizeRendererToDisplaySize( renderer ) {

		const canvas = renderer.domElement;
		const width = inputElement.clientWidth;
		const height = inputElement.clientHeight;
		const needResize = canvas.width !== width || canvas.height !== height;
		if ( needResize ) {

			renderer.setSize( width, height, false );

		}

		return needResize;

	}

	function render( time ) {

		time *= 0.001;

		if ( resizeRendererToDisplaySize( renderer ) ) {

			camera.aspect = inputElement.clientWidth / inputElement.clientHeight;
			camera.updateProjectionMatrix();

		}

		cubes.forEach( ( cube, ndx ) => {

			const speed = 1 + ndx * .1;
			const rot = time * speed;
			cube.rotation.x = rot;
			cube.rotation.y = rot;

		} );

		pickHelper.pick( pickPosition, scene, camera, time );

		renderer.render( scene, camera );

		requestAnimationFrame( render );

	}

	requestAnimationFrame( render );

	function getCanvasRelativePosition( event ) {

		const rect = inputElement.getBoundingClientRect();
		return {
			x: event.clientX - rect.left,
			y: event.clientY - rect.top,
		};

	}

	function setPickPosition( event ) {

		const pos = getCanvasRelativePosition( event );
		pickPosition.x = ( pos.x / inputElement.clientWidth ) * 2 - 1;
		pickPosition.y = ( pos.y / inputElement.clientHeight ) * - 2 + 1; // note we flip Y

	}

	function clearPickPosition() {

		// unlike the mouse which always has a position
		// if the user stops touching the screen we want
		// to stop picking. For now we just pick a value
		// unlikely to pick something
		pickPosition.x = - 100000;
		pickPosition.y = - 100000;

	}

	inputElement.addEventListener( 'mousemove', setPickPosition );
	inputElement.addEventListener( 'mouseout', clearPickPosition );
	inputElement.addEventListener( 'mouseleave', clearPickPosition );

	inputElement.addEventListener( 'touchstart', ( event ) => {

		// prevent the window from scrolling
		event.preventDefault();
		setPickPosition( event.touches[ 0 ] );

	}, { passive: false } );

	inputElement.addEventListener( 'touchmove', ( event ) => {

		setPickPosition( event.touches[ 0 ] );

	} );

	inputElement.addEventListener( 'touchend', clearPickPosition );

}
```
</details>

### `makeInstance(geometry: any, color: any, x: any): any`

**Parameters:**

- **`geometry`** `any`
- **`color`** `any`
- **`x`** `any`

**Returns:** `any`

**Calls:**

- `scene.add`

<details><summary>Code</summary>

```typescript
function makeInstance( geometry, color, x ) {

		const material = new THREE.MeshPhongMaterial( {
			color,
		} );

		const cube = new THREE.Mesh( geometry, material );
		scene.add( cube );

		cube.position.x = x;

		return cube;

	}
```
</details>

### `PickHelper.pick(normalizedPosition: any, scene: any, camera: any, time: any): void`

**Parameters:**

- **`normalizedPosition`** `any`
- **`scene`** `any`
- **`camera`** `any`
- **`time`** `any`

**Returns:** `void`

**Calls:**

- `this.pickedObject.material.emissive.setHex`
- `this.raycaster.setFromCamera`
- `this.raycaster.intersectObjects`
- `this.pickedObject.material.emissive.getHex`

**Internal Comments:**
```
// restore the color if there is a picked object
// cast a ray through the frustum (x5)
// get the list of objects the ray intersected (x2)
// pick the first object. It's the closest one (x4)
// save its color (x4)
// set its emissive color to flashing red/yellow (x7)
```

<details><summary>Code</summary>

```typescript
pick( normalizedPosition, scene, camera, time ) {

			// restore the color if there is a picked object
			if ( this.pickedObject ) {

				this.pickedObject.material.emissive.setHex( this.pickedObjectSavedColor );
				this.pickedObject = undefined;

			}

			// cast a ray through the frustum
			this.raycaster.setFromCamera( normalizedPosition, camera );
			// get the list of objects the ray intersected
			const intersectedObjects = this.raycaster.intersectObjects( scene.children );
			if ( intersectedObjects.length ) {

				// pick the first object. It's the closest one
				this.pickedObject = intersectedObjects[ 0 ].object;
				// save its color
				this.pickedObjectSavedColor = this.pickedObject.material.emissive.getHex();
				// set its emissive color to flashing red/yellow
				this.pickedObject.material.emissive.setHex( ( time * 8 ) % 2 > 1 ? 0xFFFF00 : 0xFF0000 );

			}

		}
```
</details>

### `resizeRendererToDisplaySize(renderer: any): boolean`

**Parameters:**

- **`renderer`** `any`

**Returns:** `boolean`

**Calls:**

- `renderer.setSize`

<details><summary>Code</summary>

```typescript
function resizeRendererToDisplaySize( renderer ) {

		const canvas = renderer.domElement;
		const width = inputElement.clientWidth;
		const height = inputElement.clientHeight;
		const needResize = canvas.width !== width || canvas.height !== height;
		if ( needResize ) {

			renderer.setSize( width, height, false );

		}

		return needResize;

	}
```
</details>

### `render(time: any): void`

**Parameters:**

- **`time`** `any`

**Returns:** `void`

**Calls:**

- `resizeRendererToDisplaySize`
- `camera.updateProjectionMatrix`
- `cubes.forEach`
- `pickHelper.pick`
- `renderer.render`
- `requestAnimationFrame`

<details><summary>Code</summary>

```typescript
function render( time ) {

		time *= 0.001;

		if ( resizeRendererToDisplaySize( renderer ) ) {

			camera.aspect = inputElement.clientWidth / inputElement.clientHeight;
			camera.updateProjectionMatrix();

		}

		cubes.forEach( ( cube, ndx ) => {

			const speed = 1 + ndx * .1;
			const rot = time * speed;
			cube.rotation.x = rot;
			cube.rotation.y = rot;

		} );

		pickHelper.pick( pickPosition, scene, camera, time );

		renderer.render( scene, camera );

		requestAnimationFrame( render );

	}
```
</details>

### `getCanvasRelativePosition(event: any): { x: number; y: number; }`

**Parameters:**

- **`event`** `any`

**Returns:** `{ x: number; y: number; }`

**Calls:**

- `inputElement.getBoundingClientRect`

<details><summary>Code</summary>

```typescript
function getCanvasRelativePosition( event ) {

		const rect = inputElement.getBoundingClientRect();
		return {
			x: event.clientX - rect.left,
			y: event.clientY - rect.top,
		};

	}
```
</details>

### `setPickPosition(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `getCanvasRelativePosition`

<details><summary>Code</summary>

```typescript
function setPickPosition( event ) {

		const pos = getCanvasRelativePosition( event );
		pickPosition.x = ( pos.x / inputElement.clientWidth ) * 2 - 1;
		pickPosition.y = ( pos.y / inputElement.clientHeight ) * - 2 + 1; // note we flip Y

	}
```
</details>

### `clearPickPosition(): void`

**Returns:** `void`

**Internal Comments:**
```
// unlike the mouse which always has a position (x4)
// if the user stops touching the screen we want (x4)
// to stop picking. For now we just pick a value (x4)
// unlikely to pick something (x4)
```

<details><summary>Code</summary>

```typescript
function clearPickPosition() {

		// unlike the mouse which always has a position
		// if the user stops touching the screen we want
		// to stop picking. For now we just pick a value
		// unlikely to pick something
		pickPosition.x = - 100000;
		pickPosition.y = - 100000;

	}
```
</details>


---

## Classes

### `PickHelper`

<details><summary>Class Code</summary>

```ts
class PickHelper {

		constructor() {

			this.raycaster = new THREE.Raycaster();
			this.pickedObject = null;
			this.pickedObjectSavedColor = 0;

		}
		pick( normalizedPosition, scene, camera, time ) {

			// restore the color if there is a picked object
			if ( this.pickedObject ) {

				this.pickedObject.material.emissive.setHex( this.pickedObjectSavedColor );
				this.pickedObject = undefined;

			}

			// cast a ray through the frustum
			this.raycaster.setFromCamera( normalizedPosition, camera );
			// get the list of objects the ray intersected
			const intersectedObjects = this.raycaster.intersectObjects( scene.children );
			if ( intersectedObjects.length ) {

				// pick the first object. It's the closest one
				this.pickedObject = intersectedObjects[ 0 ].object;
				// save its color
				this.pickedObjectSavedColor = this.pickedObject.material.emissive.getHex();
				// set its emissive color to flashing red/yellow
				this.pickedObject.material.emissive.setHex( ( time * 8 ) % 2 > 1 ? 0xFFFF00 : 0xFF0000 );

			}

		}

	}
```
</details>

#### Methods

##### `pick(normalizedPosition: any, scene: any, camera: any, time: any): void`

<details><summary>Code</summary>

```ts
pick( normalizedPosition, scene, camera, time ) {

			// restore the color if there is a picked object
			if ( this.pickedObject ) {

				this.pickedObject.material.emissive.setHex( this.pickedObjectSavedColor );
				this.pickedObject = undefined;

			}

			// cast a ray through the frustum
			this.raycaster.setFromCamera( normalizedPosition, camera );
			// get the list of objects the ray intersected
			const intersectedObjects = this.raycaster.intersectObjects( scene.children );
			if ( intersectedObjects.length ) {

				// pick the first object. It's the closest one
				this.pickedObject = intersectedObjects[ 0 ].object;
				// save its color
				this.pickedObjectSavedColor = this.pickedObject.material.emissive.getHex();
				// set its emissive color to flashing red/yellow
				this.pickedObject.material.emissive.setHex( ( time * 8 ) % 2 > 1 ? 0xFFFF00 : 0xFF0000 );

			}

		}
```
</details>


---