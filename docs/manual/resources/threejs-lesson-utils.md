[⬅️ Back to Table of Contents](../../index.md)

# 📄 `threejs-lesson-utils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 32 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/resources/threejs-lesson-utils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `OrbitControls` | `../../examples/jsm/controls/OrbitControls.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `renderer` | `any` | let/var | `new THREE.WebGLRenderer( { canvas, alpha: true, antialias: true, powerPrefere...` | ✗ |
| `canvas` | `any` | let/var | `renderer.domElement` | ✗ |
| `width` | `number` | let/var | `canvas.clientWidth * this.pixelRatio \| 0` | ✗ |
| `height` | `number` | let/var | `canvas.clientHeight * this.pixelRatio \| 0` | ✗ |
| `needResize` | `boolean` | let/var | `canvas.width !== width \|\| canvas.height !== height` | ✗ |
| `clearColor` | `any` | let/var | `new THREE.Color( '#000' )` | ✗ |
| `needsUpdate` | `boolean` | let/var | `true` | ✗ |
| `rafRequestId` | `any` | let/var | `*not shown*` | ✗ |
| `rafRunning` | `any` | let/var | `*not shown*` | ✗ |
| `transform` | `string` | let/var | ``translateY(${window.scrollY}px)`` | ✗ |
| `name` | `any` | let/var | `elem.dataset.diagram` | ✗ |
| `info` | `any` | let/var | `diagrams[ name ]` | ✗ |
| `scene` | `any` | let/var | `new THREE.Scene()` | ✗ |
| `targetFOVDeg` | `number` | let/var | `60` | ✗ |
| `aspect` | `1` | let/var | `1` | ✗ |
| `near` | `0.1` | let/var | `0.1` | ✗ |
| `far` | `50` | let/var | `50` | ✗ |
| `camera` | `any` | let/var | `new THREE.PerspectiveCamera( targetFOVDeg, aspect, near, far )` | ✗ |
| `root` | `any` | let/var | `new THREE.Object3D()` | ✗ |
| `renderInfo` | `{ pixelRatio: any; camera: any; scene...` | let/var | `{ pixelRatio: this.pixelRatio, camera, scene, root, renderer: this.renderer, ...` | ✗ |
| `promise` | `Promise<any>` | let/var | `( obj3D instanceof Promise ) ? obj3D : Promise.resolve( obj3D )` | ✗ |
| `updateFunctions` | `any[]` | let/var | `[]` | ✗ |
| `resizeFunctions` | `any[]` | let/var | `[]` | ✗ |
| `settings` | `{ lights: boolean; trackball: boolean...` | let/var | `{ lights: true, trackball: true, // resize(renderInfo) { // }, // update(time...` | ✗ |
| `info` | `any` | let/var | `result instanceof THREE.Object3D ? { obj3D: result, } : result` | ✗ |
| `controls` | `OrbitControls` | let/var | `new OrbitControls( camera, elem )` | ✗ |
| `light` | `any` | let/var | `new THREE.DirectionalLight( 0xffffff, 1 )` | ✗ |
| `oldWidth` | `number` | let/var | `- 1` | ✗ |
| `oldHeight` | `number` | let/var | `- 1` | ✗ |
| `aspect` | `number` | let/var | `renderInfo.width / renderInfo.height` | ✗ |
| `fovDeg` | `any` | let/var | `aspect >= 1 ? targetFOVDeg : THREE.MathUtils.radToDeg( 2 * Math.atan( Math.ta...` | ✗ |
| `threejsLessonUtils` | `{ _afterPrettifyFuncs: any[]; init(op...` | let/var | `{ _afterPrettifyFuncs: [], init( options = { threejsOptions: {} } ) { if ( th...` | ✓ |


---

## Functions

### `resizeRendererToDisplaySize(renderer: any): boolean`

**Parameters:**

- **`renderer`** `any`

**Returns:** `boolean`

**Calls:**

- `renderer.setSize`

<details><summary>Code</summary>

```typescript
( renderer ) => {

			const canvas = renderer.domElement;
			const width = canvas.clientWidth * this.pixelRatio | 0;
			const height = canvas.clientHeight * this.pixelRatio | 0;
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
- `renderer.setScissorTest`
- `renderer.setClearColor`
- `renderer.clear`
- `this.elementsOnScreen.forEach`
- `this.elemToRenderFuncMap.get`
- `fn`
- `startRAFLoop`

**Internal Comments:**
```
// only update if we drew last time
// so the browser will not recomposite the page
// of nothing is being drawn.
// maybe there is another way. Originally I used `position: fixed` (x2)
// but the problem is if we can't render as fast as the browser (x2)
// scrolls then our shapes lag. 1 or 2 frames of lag isn't too (x2)
// horrible but iOS would often been 1/2 a second or worse. (x2)
// By doing it this way the canvas will scroll which means the (x2)
// worse that happens is part of the shapes scrolling on don't (x2)
// get drawn for a few frames but the shapes that are on the screen (x2)
// scroll perfectly. (x2)
// (x2)
// I'm using `transform` on the voodoo that it doesn't affect (x2)
// layout as much as `top` since AFAIK setting `top` is in (x2)
// the flow but `transform` is not though thinking about it (x2)
// the given we're `position: absolute` maybe there's no difference? (x2)
```

<details><summary>Code</summary>

```typescript
( time ) => {

			rafRequestId = undefined;
			time *= 0.001;

			const resized = resizeRendererToDisplaySize( renderer );

			// only update if we drew last time
			// so the browser will not recomposite the page
			// of nothing is being drawn.
			if ( needsUpdate ) {

				needsUpdate = false;

				renderer.setScissorTest( false );
				renderer.setClearColor( clearColor, 0 );
				renderer.clear( true, true );
				renderer.setScissorTest( true );

			}

			this.elementsOnScreen.forEach( elem => {

				const fn = this.elemToRenderFuncMap.get( elem );
				const wasRendered = fn( renderer, time, resized );
				needsUpdate = needsUpdate || wasRendered;

			} );

			if ( needsUpdate ) {

				// maybe there is another way. Originally I used `position: fixed`
				// but the problem is if we can't render as fast as the browser
				// scrolls then our shapes lag. 1 or 2 frames of lag isn't too
				// horrible but iOS would often been 1/2 a second or worse.
				// By doing it this way the canvas will scroll which means the
				// worse that happens is part of the shapes scrolling on don't
				// get drawn for a few frames but the shapes that are on the screen
				// scroll perfectly.
				//
				// I'm using `transform` on the voodoo that it doesn't affect
				// layout as much as `top` since AFAIK setting `top` is in
				// the flow but `transform` is not though thinking about it
				// the given we're `position: absolute` maybe there's no difference?
				const transform = `translateY(${window.scrollY}px)`;
				renderer.domElement.style.transform = transform;

			}

			if ( rafRunning ) {

				startRAFLoop();

			}

		}
```
</details>

### `startRAFLoop(): void`

**Returns:** `void`

**Calls:**

- `requestAnimationFrame`

<details><summary>Code</summary>

```typescript
function startRAFLoop() {

			rafRunning = true;
			if ( ! rafRequestId ) {

				rafRequestId = requestAnimationFrame( render );

			}

		}
```
</details>

### `render(renderer: any, time: any): boolean`

**Parameters:**

- **`renderer`** `any`
- **`time`** `any`

**Returns:** `boolean`

**Calls:**

- `elem.getBoundingClientRect`
- `resizeFunctions.forEach`
- `fn`
- `updateFunctions.forEach`
- `THREE.MathUtils.radToDeg`
- `Math.atan`
- `Math.tan`
- `THREE.MathUtils.degToRad`
- `camera.updateProjectionMatrix`
- `renderer.setViewport`
- `renderer.setScissor`
- `settings.render`

<details><summary>Code</summary>

```typescript
( renderer, time ) => {

			root.rotation.x = time * .1;
			root.rotation.y = time * .11;

			const rect = elem.getBoundingClientRect();
			if ( rect.bottom < 0 || rect.top > renderer.domElement.clientHeight ||
          rect.right < 0 || rect.left > renderer.domElement.clientWidth ) {

				return false;

			}

			renderInfo.width = rect.width * this.pixelRatio;
			renderInfo.height = rect.height * this.pixelRatio;
			renderInfo.left = rect.left * this.pixelRatio;
			renderInfo.bottom = ( renderer.domElement.clientHeight - rect.bottom ) * this.pixelRatio;

			if ( renderInfo.width !== oldWidth || renderInfo.height !== oldHeight ) {

				oldWidth = renderInfo.width;
				oldHeight = renderInfo.height;
				resizeFunctions.forEach( fn => fn( renderInfo ) );

			}

			updateFunctions.forEach( fn => fn( time, renderInfo ) );

			const aspect = renderInfo.width / renderInfo.height;
			const fovDeg = aspect >= 1
				? targetFOVDeg
				: THREE.MathUtils.radToDeg( 2 * Math.atan( Math.tan( THREE.MathUtils.degToRad( targetFOVDeg ) * .5 ) / aspect ) );

			camera.fov = fovDeg;
			camera.aspect = aspect;
			camera.updateProjectionMatrix();

			renderer.setViewport( renderInfo.left, renderInfo.bottom, renderInfo.width, renderInfo.height );
			renderer.setScissor( renderInfo.left, renderInfo.bottom, renderInfo.width, renderInfo.height );

			settings.render( renderInfo );

			return true;

		}
```
</details>

### `init(options: { threejsOptions: {}; }): void`

**Parameters:**

- **`options`** `{ threejsOptions: {}; }`

**Returns:** `void`

**Calls:**

- `document.createElement`
- `document.body.appendChild`
- `renderer.setSize`
- `resizeRendererToDisplaySize`
- `renderer.setScissorTest`
- `renderer.setClearColor`
- `renderer.clear`
- `this.elementsOnScreen.forEach`
- `this.elemToRenderFuncMap.get`
- `fn`
- `startRAFLoop`
- `requestAnimationFrame`
- `entries.forEach`
- `this.elementsOnScreen.add`
- `this.elementsOnScreen.delete`

**Internal Comments:**
```
// only update if we drew last time
// so the browser will not recomposite the page
// of nothing is being drawn.
// maybe there is another way. Originally I used `position: fixed` (x2)
// but the problem is if we can't render as fast as the browser (x2)
// scrolls then our shapes lag. 1 or 2 frames of lag isn't too (x2)
// horrible but iOS would often been 1/2 a second or worse. (x2)
// By doing it this way the canvas will scroll which means the (x2)
// worse that happens is part of the shapes scrolling on don't (x2)
// get drawn for a few frames but the shapes that are on the screen (x2)
// scroll perfectly. (x2)
// (x2)
// I'm using `transform` on the voodoo that it doesn't affect (x2)
// layout as much as `top` since AFAIK setting `top` is in (x2)
// the flow but `transform` is not though thinking about it (x2)
// the given we're `position: absolute` maybe there's no difference? (x2)
```

<details><summary>Code</summary>

```typescript
init( options = { threejsOptions: {} } ) {

		if ( this.renderer ) {

			return;

		}

		const canvas = document.createElement( 'canvas' );
		canvas.id = 'c';
		document.body.appendChild( canvas );
		const renderer = new THREE.WebGLRenderer( {
			canvas,
			alpha: true,
			antialias: true,
			powerPreference: 'low-power',
			...options.threejsOptions,
		} );
		this.pixelRatio = window.devicePixelRatio;

		this.renderer = renderer;
		this.elemToRenderFuncMap = new Map();

		const resizeRendererToDisplaySize = ( renderer ) => {

			const canvas = renderer.domElement;
			const width = canvas.clientWidth * this.pixelRatio | 0;
			const height = canvas.clientHeight * this.pixelRatio | 0;
			const needResize = canvas.width !== width || canvas.height !== height;
			if ( needResize ) {

				renderer.setSize( width, height, false );

			}

			return needResize;

		};

		const clearColor = new THREE.Color( '#000' );
		let needsUpdate = true;
		let rafRequestId;
		let rafRunning;

		const render = ( time ) => {

			rafRequestId = undefined;
			time *= 0.001;

			const resized = resizeRendererToDisplaySize( renderer );

			// only update if we drew last time
			// so the browser will not recomposite the page
			// of nothing is being drawn.
			if ( needsUpdate ) {

				needsUpdate = false;

				renderer.setScissorTest( false );
				renderer.setClearColor( clearColor, 0 );
				renderer.clear( true, true );
				renderer.setScissorTest( true );

			}

			this.elementsOnScreen.forEach( elem => {

				const fn = this.elemToRenderFuncMap.get( elem );
				const wasRendered = fn( renderer, time, resized );
				needsUpdate = needsUpdate || wasRendered;

			} );

			if ( needsUpdate ) {

				// maybe there is another way. Originally I used `position: fixed`
				// but the problem is if we can't render as fast as the browser
				// scrolls then our shapes lag. 1 or 2 frames of lag isn't too
				// horrible but iOS would often been 1/2 a second or worse.
				// By doing it this way the canvas will scroll which means the
				// worse that happens is part of the shapes scrolling on don't
				// get drawn for a few frames but the shapes that are on the screen
				// scroll perfectly.
				//
				// I'm using `transform` on the voodoo that it doesn't affect
				// layout as much as `top` since AFAIK setting `top` is in
				// the flow but `transform` is not though thinking about it
				// the given we're `position: absolute` maybe there's no difference?
				const transform = `translateY(${window.scrollY}px)`;
				renderer.domElement.style.transform = transform;

			}

			if ( rafRunning ) {

				startRAFLoop();

			}

		};

		function startRAFLoop() {

			rafRunning = true;
			if ( ! rafRequestId ) {

				rafRequestId = requestAnimationFrame( render );

			}

		}

		this.elementsOnScreen = new Set();
		this.intersectionObserver = new IntersectionObserver( ( entries ) => {

			entries.forEach( entry => {

				if ( entry.isIntersecting ) {

					this.elementsOnScreen.add( entry.target );

				} else {

					this.elementsOnScreen.delete( entry.target );

				}
				// Each entry describes an intersection change for one observed
				// target element:
				//   entry.boundingClientRect
				//   entry.intersectionRatio
				//   entry.intersectionRect
				//   entry.isIntersecting
				//   entry.rootBounds
				//   entry.target
				//   entry.time

			} );
			if ( this.elementsOnScreen.size > 0 ) {

				startRAFLoop();

			} else {

				rafRunning = false;

			}

		} );


	}
```
</details>

### `addDiagrams(diagrams: any): void`

**Parameters:**

- **`diagrams`** `any`

**Returns:** `void`

**Calls:**

- `[ ...document.querySelectorAll( '[data-diagram]' ) ].forEach`
- `document.querySelectorAll`
- `this.addDiagram`

<details><summary>Code</summary>

```typescript
addDiagrams( diagrams ) {

		[ ...document.querySelectorAll( '[data-diagram]' ) ].forEach( ( elem ) => {

			const name = elem.dataset.diagram;
			const info = diagrams[ name ];
			if ( ! info ) {

				throw new Error( `no diagram: ${name}` );

			}

			this.addDiagram( elem, info );

		} );

	}
```
</details>

### `addDiagram(elem: any, info: any): void`

**Parameters:**

- **`elem`** `any`
- **`info`** `any`

**Returns:** `void`

**Calls:**

- `this.init`
- `scene.add`
- `info.create`
- `Promise.resolve`
- `renderInfo.renderer.render`
- `promise.then`
- `root.add`
- `updateFunctions.push`
- `resizeFunctions.push`
- `Object.assign`
- `elem.removeAttribute`
- `controls.update.bind`
- `camera.add`
- `light.position.set`
- `elem.getBoundingClientRect`
- `resizeFunctions.forEach`
- `fn`
- `updateFunctions.forEach`
- `THREE.MathUtils.radToDeg`
- `Math.atan`
- `Math.tan`
- `THREE.MathUtils.degToRad`
- `camera.updateProjectionMatrix`
- `renderer.setViewport`
- `renderer.setScissor`
- `settings.render`
- `this.intersectionObserver.observe`
- `this.elemToRenderFuncMap.set`

**Internal Comments:**
```
// resize(renderInfo) { (x2)
// }, (x4)
// update(time, renderInfo) { (x2)
//resizeFunctions.push(controls.handleResize.bind(controls)); (x4)
// add the lights as children of the camera.
// this is because TrackballControls move the camera.
// We really want to rotate the object itself but there's no
// controls for that so we fake it by putting all the lights
// on the camera so they move with it.
```

<details><summary>Code</summary>

```typescript
addDiagram( elem, info ) {

		this.init();

		const scene = new THREE.Scene();
		let targetFOVDeg = 60;
		const aspect = 1;
		const near = 0.1;
		const far = 50;
		let camera = new THREE.PerspectiveCamera( targetFOVDeg, aspect, near, far );
		camera.position.z = 15;
		scene.add( camera );

		const root = new THREE.Object3D();
		scene.add( root );

		const renderInfo = {
			pixelRatio: this.pixelRatio,
			camera,
			scene,
			root,
			renderer: this.renderer,
			elem,
		};

		const obj3D = info.create( { scene, camera, renderInfo } );
		const promise = ( obj3D instanceof Promise ) ? obj3D : Promise.resolve( obj3D );

		const updateFunctions = [];
		const resizeFunctions = [];

		const settings = {
			lights: true,
			trackball: true,
			// resize(renderInfo) {
			// },
			// update(time, renderInfo) {
			// },
			render( renderInfo ) {

				renderInfo.renderer.render( renderInfo.scene, renderInfo.camera );

			},
		};

		promise.then( ( result ) => {

			const info = result instanceof THREE.Object3D ? {
				obj3D: result,
			} : result;
			if ( info.obj3D ) {

				root.add( info.obj3D );

			}

			if ( info.update ) {

				updateFunctions.push( info.update );

			}

			if ( info.resize ) {

				resizeFunctions.push( info.resize );

			}

			if ( info.camera ) {

				camera = info.camera;
				renderInfo.camera = camera;

			}

			Object.assign( settings, info );
			targetFOVDeg = camera.fov;

			if ( settings.trackball !== false ) {

				const controls = new OrbitControls( camera, elem );
				controls.rotateSpeed = 1 / 6;
				controls.enableZoom = false;
				controls.enablePan = false;
				elem.removeAttribute( 'tabIndex' );
				//resizeFunctions.push(controls.handleResize.bind(controls));
				updateFunctions.push( controls.update.bind( controls ) );

			}

			// add the lights as children of the camera.
			// this is because TrackballControls move the camera.
			// We really want to rotate the object itself but there's no
			// controls for that so we fake it by putting all the lights
			// on the camera so they move with it.
			if ( settings.lights !== false ) {

				camera.add( new THREE.HemisphereLight( 0xaaaaaa, 0x444444, .5 ) );
				const light = new THREE.DirectionalLight( 0xffffff, 1 );
				light.position.set( - 1, 2, 4 - 15 );
				camera.add( light );

			}

		} );

		let oldWidth = - 1;
		let oldHeight = - 1;

		const render = ( renderer, time ) => {

			root.rotation.x = time * .1;
			root.rotation.y = time * .11;

			const rect = elem.getBoundingClientRect();
			if ( rect.bottom < 0 || rect.top > renderer.domElement.clientHeight ||
          rect.right < 0 || rect.left > renderer.domElement.clientWidth ) {

				return false;

			}

			renderInfo.width = rect.width * this.pixelRatio;
			renderInfo.height = rect.height * this.pixelRatio;
			renderInfo.left = rect.left * this.pixelRatio;
			renderInfo.bottom = ( renderer.domElement.clientHeight - rect.bottom ) * this.pixelRatio;

			if ( renderInfo.width !== oldWidth || renderInfo.height !== oldHeight ) {

				oldWidth = renderInfo.width;
				oldHeight = renderInfo.height;
				resizeFunctions.forEach( fn => fn( renderInfo ) );

			}

			updateFunctions.forEach( fn => fn( time, renderInfo ) );

			const aspect = renderInfo.width / renderInfo.height;
			const fovDeg = aspect >= 1
				? targetFOVDeg
				: THREE.MathUtils.radToDeg( 2 * Math.atan( Math.tan( THREE.MathUtils.degToRad( targetFOVDeg ) * .5 ) / aspect ) );

			camera.fov = fovDeg;
			camera.aspect = aspect;
			camera.updateProjectionMatrix();

			renderer.setViewport( renderInfo.left, renderInfo.bottom, renderInfo.width, renderInfo.height );
			renderer.setScissor( renderInfo.left, renderInfo.bottom, renderInfo.width, renderInfo.height );

			settings.render( renderInfo );

			return true;

		};

		this.intersectionObserver.observe( elem );
		this.elemToRenderFuncMap.set( elem, render );

	}
```
</details>

### `onAfterPrettify(fn: any): void`

**Parameters:**

- **`fn`** `any`

**Returns:** `void`

**Calls:**

- `this._afterPrettifyFuncs.push`

<details><summary>Code</summary>

```typescript
onAfterPrettify( fn ) {

		this._afterPrettifyFuncs.push( fn );

	}
```
</details>

### `afterPrettify(): void`

**Returns:** `void`

**Calls:**

- `this._afterPrettifyFuncs.forEach`
- `fn`

<details><summary>Code</summary>

```typescript
afterPrettify() {

		this._afterPrettifyFuncs.forEach( ( fn ) => {

			fn();

		} );

	}
```
</details>


---