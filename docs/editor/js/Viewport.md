[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Viewport.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 17 |
| 📦 Imports | 12 |
| 📊 Variables & Constants | 45 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Viewport.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TransformControls` | `three/addons/controls/TransformControls.js` |
| `UIPanel` | `./libs/ui.js` |
| `EditorControls` | `./EditorControls.js` |
| `ViewportControls` | `./Viewport.Controls.js` |
| `ViewportInfo` | `./Viewport.Info.js` |
| `ViewHelper` | `./Viewport.ViewHelper.js` |
| `XR` | `./Viewport.XR.js` |
| `SetPositionCommand` | `./commands/SetPositionCommand.js` |
| `SetRotationCommand` | `./commands/SetRotationCommand.js` |
| `SetScaleCommand` | `./commands/SetScaleCommand.js` |
| `RoomEnvironment` | `three/addons/environments/RoomEnvironment.js` |
| `ViewportPathtracer` | `./Viewport.Pathtracer.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `selector` | `any` | let/var | `editor.selector` | ✗ |
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `renderer` | `any` | let/var | `null` | ✗ |
| `pmremGenerator` | `any` | let/var | `null` | ✗ |
| `pathtracer` | `any` | let/var | `null` | ✗ |
| `camera` | `any` | let/var | `editor.camera` | ✗ |
| `scene` | `any` | let/var | `editor.scene` | ✗ |
| `sceneHelpers` | `any` | let/var | `editor.sceneHelpers` | ✗ |
| `GRID_COLORS_LIGHT` | `number[]` | let/var | `[ 0x999999, 0x777777 ]` | ✗ |
| `GRID_COLORS_DARK` | `number[]` | let/var | `[ 0x555555, 0x888888 ]` | ✗ |
| `grid` | `any` | let/var | `new THREE.Group()` | ✗ |
| `grid1` | `any` | let/var | `new THREE.GridHelper( 30, 30 )` | ✗ |
| `grid2` | `any` | let/var | `new THREE.GridHelper( 30, 6 )` | ✗ |
| `viewHelper` | `ViewHelper` | let/var | `new ViewHelper( camera, container )` | ✗ |
| `box` | `any` | let/var | `new THREE.Box3()` | ✗ |
| `selectionBox` | `any` | let/var | `new THREE.Box3Helper( box )` | ✗ |
| `objectPositionOnDown` | `any` | let/var | `null` | ✗ |
| `objectRotationOnDown` | `any` | let/var | `null` | ✗ |
| `objectScaleOnDown` | `any` | let/var | `null` | ✗ |
| `transformControls` | `any` | let/var | `new TransformControls( camera )` | ✗ |
| `object` | `any` | let/var | `transformControls.object` | ✗ |
| `object` | `any` | let/var | `transformControls.object` | ✗ |
| `xr` | `XR` | let/var | `new XR( editor, transformControls )` | ✗ |
| `camera` | `any` | let/var | `editor.cameras[ uuid ]` | ✗ |
| `aspect` | `number` | let/var | `container.dom.offsetWidth / container.dom.offsetHeight` | ✗ |
| `cameraHelper` | `any` | let/var | `editor.helpers[ camera.id ]` | ✗ |
| `onDownPosition` | `any` | let/var | `new THREE.Vector2()` | ✗ |
| `onUpPosition` | `any` | let/var | `new THREE.Vector2()` | ✗ |
| `onDoubleClickPosition` | `any` | let/var | `new THREE.Vector2()` | ✗ |
| `touch` | `any` | let/var | `event.changedTouches[ 0 ]` | ✗ |
| `touch` | `any` | let/var | `event.changedTouches[ 0 ]` | ✗ |
| `intersect` | `any` | let/var | `intersects[ 0 ]` | ✗ |
| `controls` | `EditorControls` | let/var | `new EditorControls( camera )` | ✗ |
| `helper` | `any` | let/var | `editor.helpers[ object.id ]` | ✗ |
| `useBackgroundAsEnvironment` | `boolean` | let/var | `false` | ✗ |
| `viewportCamera` | `any` | let/var | `editor.viewportCamera` | ✗ |
| `viewportShading` | `any` | let/var | `editor.viewportShading` | ✗ |
| `prevActionsInUse` | `number` | let/var | `0` | ✗ |
| `clock` | `any` | let/var | `new THREE.Clock()` | ✗ |
| `mixer` | `any` | let/var | `editor.mixer` | ✗ |
| `needsUpdate` | `boolean` | let/var | `false` | ✗ |
| `actions` | `any` | let/var | `mixer.stats.actions` | ✗ |
| `startTime` | `number` | let/var | `0` | ✗ |
| `endTime` | `number` | let/var | `0` | ✗ |


---

## Functions

### `Viewport(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.setId`
- `container.setPosition`
- `container.add`
- `grid1.material.color.setHex`
- `grid.add`
- `grid2.material.color.setHex`
- `sceneHelpers.add`
- `transformControls.addEventListener`
- `render`
- `signals.objectChanged.dispatch`
- `object.position.clone`
- `object.rotation.clone`
- `object.scale.clone`
- `transformControls.getMode`
- `objectPositionOnDown.equals`
- `editor.execute`
- `objectRotationOnDown.equals`
- `objectScaleOnDown.equals`
- `transformControls.getHelper`
- `camera.updateProjectionMatrix`
- `cameraHelper.update`
- `dom.getBoundingClientRect`
- `onDownPosition.distanceTo`
- `selector.getPointerIntersects`
- `signals.intersectionsDetected.dispatch`
- `getMousePosition`
- `onDownPosition.fromArray`
- `document.addEventListener`
- `onUpPosition.fromArray`
- `handleClick`
- `document.removeEventListener`
- `onDoubleClickPosition.fromArray`
- `signals.objectFocused.dispatch`
- `container.dom.addEventListener`
- `controls.addEventListener`
- `signals.cameraChanged.dispatch`
- `signals.refreshSidebarObject3D.dispatch`
- `signals.editorCleared.add`
- `controls.center.set`
- `pathtracer.reset`
- `initPT`
- `signals.transformModeChanged.add`
- `transformControls.setMode`
- `signals.snapChanged.add`
- `transformControls.setTranslationSnap`
- `signals.spaceChanged.add`
- `transformControls.setSpace`
- `signals.rendererUpdated.add`
- `scene.traverse`
- `signals.rendererCreated.add`
- `renderer.setAnimationLoop`
- `renderer.dispose`
- `pmremGenerator.dispose`
- `container.dom.removeChild`
- `controls.connect`
- `transformControls.connect`
- `renderer.setClearColor`
- `window.matchMedia`
- `mediaQuery.addEventListener`
- `updateGridColors`
- `renderer.setPixelRatio`
- `renderer.setSize`
- `pmremGenerator.compileEquirectangularShader`
- `container.dom.appendChild`
- `signals.rendererDetectKTX2Support.add`
- `ktx2Loader.detectSupport`
- `signals.sceneGraphChanged.add`
- `signals.cameraChanged.add`
- `signals.objectSelected.add`
- `transformControls.detach`
- `box.setFromObject`
- `box.isEmpty`
- `transformControls.attach`
- `signals.objectFocused.add`
- `controls.focus`
- `signals.geometryChanged.add`
- `signals.objectChanged.add`
- `object.updateProjectionMatrix`
- `helper.update`
- `signals.objectRemoved.add`
- `signals.materialChanged.add`
- `updatePTMaterials`
- `signals.sceneBackgroundChanged.add`
- `updatePTBackground`
- `signals.sceneEnvironmentChanged.add`
- `pmremGenerator.fromScene`
- `updatePTEnvironment`
- `signals.sceneFogChanged.add`
- `signals.sceneFogSettingsChanged.add`
- `scene.fog.color.setHex`
- `signals.viewportCameraChanged.add`
- `updateAspectRatio`
- `signals.viewportShadingChanged.add`
- `pathtracer.init`
- `signals.windowResize.add`
- `pathtracer.setSize`
- `signals.showHelpersChanged.add`
- `sceneHelpers.traverse`
- `signals.cameraResetted.add`
- `clock.getDelta`
- `mixer.update`
- `editor.selected.updateWorldMatrix`
- `selectionBox.box.setFromObject`
- `viewHelper.update`
- `updatePT`
- `pathtracer.setBackground`
- `pathtracer.setEnvironment`
- `pathtracer.updateMaterials`
- `pathtracer.update`
- `editor.signals.pathTracerUpdated.dispatch`
- `pathtracer.getSamples`
- `performance.now`
- `renderer.setViewport`
- `renderer.render`
- `viewHelper.render`
- `editor.signals.sceneRendered.dispatch`

**Internal Comments:**
```
// (x13)
// helpers (x2)
// events
// event.preventDefault();
// controls need to be added *after* main logic, (x2)
// otherwise controls.enabled doesn't work. (x2)
// signals (x5)
// background (x5)
// environment (x2)
// fog (x5)
// disable EditorControls when setting a user camera (x4)
// animations (x2)
// Animations (x2)
// View Helper
```

<details><summary>Code</summary>

```typescript
function Viewport( editor ) {

	const selector = editor.selector;
	const signals = editor.signals;

	const container = new UIPanel();
	container.setId( 'viewport' );
	container.setPosition( 'absolute' );

	container.add( new ViewportControls( editor ) );
	container.add( new ViewportInfo( editor ) );

	//

	let renderer = null;
	let pmremGenerator = null;
	let pathtracer = null;

	const camera = editor.camera;
	const scene = editor.scene;
	const sceneHelpers = editor.sceneHelpers;

	// helpers

	const GRID_COLORS_LIGHT = [ 0x999999, 0x777777 ];
	const GRID_COLORS_DARK = [ 0x555555, 0x888888 ];

	const grid = new THREE.Group();

	const grid1 = new THREE.GridHelper( 30, 30 );
	grid1.material.color.setHex( GRID_COLORS_LIGHT[ 0 ] );
	grid1.material.vertexColors = false;
	grid.add( grid1 );

	const grid2 = new THREE.GridHelper( 30, 6 );
	grid2.material.color.setHex( GRID_COLORS_LIGHT[ 1 ] );
	grid2.material.vertexColors = false;
	grid.add( grid2 );

	const viewHelper = new ViewHelper( camera, container );

	//

	const box = new THREE.Box3();

	const selectionBox = new THREE.Box3Helper( box );
	selectionBox.material.depthTest = false;
	selectionBox.material.transparent = true;
	selectionBox.visible = false;
	sceneHelpers.add( selectionBox );

	let objectPositionOnDown = null;
	let objectRotationOnDown = null;
	let objectScaleOnDown = null;

	const transformControls = new TransformControls( camera );
	transformControls.addEventListener( 'axis-changed', function () {

		if ( editor.viewportShading !== 'realistic' ) render();

	} );
	transformControls.addEventListener( 'objectChange', function () {

		signals.objectChanged.dispatch( transformControls.object );

	} );
	transformControls.addEventListener( 'mouseDown', function () {

		const object = transformControls.object;

		objectPositionOnDown = object.position.clone();
		objectRotationOnDown = object.rotation.clone();
		objectScaleOnDown = object.scale.clone();

		controls.enabled = false;

	} );
	transformControls.addEventListener( 'mouseUp', function () {

		const object = transformControls.object;

		if ( object !== undefined ) {

			switch ( transformControls.getMode() ) {

				case 'translate':

					if ( ! objectPositionOnDown.equals( object.position ) ) {

						editor.execute( new SetPositionCommand( editor, object, object.position, objectPositionOnDown ) );

					}

					break;

				case 'rotate':

					if ( ! objectRotationOnDown.equals( object.rotation ) ) {

						editor.execute( new SetRotationCommand( editor, object, object.rotation, objectRotationOnDown ) );

					}

					break;

				case 'scale':

					if ( ! objectScaleOnDown.equals( object.scale ) ) {

						editor.execute( new SetScaleCommand( editor, object, object.scale, objectScaleOnDown ) );

					}

					break;

			}

		}

		controls.enabled = true;

	} );

	sceneHelpers.add( transformControls.getHelper() );

	//

	const xr = new XR( editor, transformControls ); // eslint-disable-line no-unused-vars

	// events

	function updateAspectRatio() {

		for ( const uuid in editor.cameras ) {

			const camera = editor.cameras[ uuid ];

			const aspect = container.dom.offsetWidth / container.dom.offsetHeight;

			if ( camera.isPerspectiveCamera ) {

				camera.aspect = aspect;

			} else {

				camera.left = - aspect;
				camera.right = aspect;

			}

			camera.updateProjectionMatrix();

			const cameraHelper = editor.helpers[ camera.id ];
			if ( cameraHelper ) cameraHelper.update();

		}

	}

	const onDownPosition = new THREE.Vector2();
	const onUpPosition = new THREE.Vector2();
	const onDoubleClickPosition = new THREE.Vector2();

	function getMousePosition( dom, x, y ) {

		const rect = dom.getBoundingClientRect();
		return [ ( x - rect.left ) / rect.width, ( y - rect.top ) / rect.height ];

	}

	function handleClick() {

		if ( onDownPosition.distanceTo( onUpPosition ) === 0 ) {

			const intersects = selector.getPointerIntersects( onUpPosition, camera );
			signals.intersectionsDetected.dispatch( intersects );

			render();

		}

	}

	function onMouseDown( event ) {

		// event.preventDefault();

		if ( event.target !== renderer.domElement ) return;

		const array = getMousePosition( container.dom, event.clientX, event.clientY );
		onDownPosition.fromArray( array );

		document.addEventListener( 'mouseup', onMouseUp );

	}

	function onMouseUp( event ) {

		const array = getMousePosition( container.dom, event.clientX, event.clientY );
		onUpPosition.fromArray( array );

		handleClick();

		document.removeEventListener( 'mouseup', onMouseUp );

	}

	function onTouchStart( event ) {

		const touch = event.changedTouches[ 0 ];

		const array = getMousePosition( container.dom, touch.clientX, touch.clientY );
		onDownPosition.fromArray( array );

		document.addEventListener( 'touchend', onTouchEnd );

	}

	function onTouchEnd( event ) {

		const touch = event.changedTouches[ 0 ];

		const array = getMousePosition( container.dom, touch.clientX, touch.clientY );
		onUpPosition.fromArray( array );

		handleClick();

		document.removeEventListener( 'touchend', onTouchEnd );

	}

	function onDoubleClick( event ) {

		const array = getMousePosition( container.dom, event.clientX, event.clientY );
		onDoubleClickPosition.fromArray( array );

		const intersects = selector.getPointerIntersects( onDoubleClickPosition, camera );

		if ( intersects.length > 0 ) {

			const intersect = intersects[ 0 ];

			signals.objectFocused.dispatch( intersect.object );

		}

	}

	container.dom.addEventListener( 'mousedown', onMouseDown );
	container.dom.addEventListener( 'touchstart', onTouchStart, { passive: false } );
	container.dom.addEventListener( 'dblclick', onDoubleClick );

	// controls need to be added *after* main logic,
	// otherwise controls.enabled doesn't work.

	const controls = new EditorControls( camera );
	controls.addEventListener( 'change', function () {

		signals.cameraChanged.dispatch( camera );
		signals.refreshSidebarObject3D.dispatch( camera );

	} );
	viewHelper.center = controls.center;

	// signals

	signals.editorCleared.add( function () {

		controls.center.set( 0, 0, 0 );
		pathtracer.reset();

		initPT();
		render();

	} );

	signals.transformModeChanged.add( function ( mode ) {

		transformControls.setMode( mode );

		render();

	} );

	signals.snapChanged.add( function ( dist ) {

		transformControls.setTranslationSnap( dist );

	} );

	signals.spaceChanged.add( function ( space ) {

		transformControls.setSpace( space );

		render();

	} );

	signals.rendererUpdated.add( function () {

		scene.traverse( function ( child ) {

			if ( child.material !== undefined ) {

				child.material.needsUpdate = true;

			}

		} );

		render();

	} );

	signals.rendererCreated.add( function ( newRenderer ) {

		if ( renderer !== null ) {

			renderer.setAnimationLoop( null );
			renderer.dispose();
			pmremGenerator.dispose();

			container.dom.removeChild( renderer.domElement );

		}

		controls.connect( newRenderer.domElement );
		transformControls.connect( newRenderer.domElement );

		renderer = newRenderer;

		renderer.setAnimationLoop( animate );
		renderer.setClearColor( 0xaaaaaa );

		if ( window.matchMedia ) {

			const mediaQuery = window.matchMedia( '(prefers-color-scheme: dark)' );
			mediaQuery.addEventListener( 'change', function ( event ) {

				renderer.setClearColor( event.matches ? 0x333333 : 0xaaaaaa );
				updateGridColors( grid1, grid2, event.matches ? GRID_COLORS_DARK : GRID_COLORS_LIGHT );

				render();

			} );

			renderer.setClearColor( mediaQuery.matches ? 0x333333 : 0xaaaaaa );
			updateGridColors( grid1, grid2, mediaQuery.matches ? GRID_COLORS_DARK : GRID_COLORS_LIGHT );

		}

		renderer.setPixelRatio( window.devicePixelRatio );
		renderer.setSize( container.dom.offsetWidth, container.dom.offsetHeight );

		pmremGenerator = new THREE.PMREMGenerator( renderer );
		pmremGenerator.compileEquirectangularShader();

		pathtracer = new ViewportPathtracer( renderer );

		container.dom.appendChild( renderer.domElement );

		render();

	} );

	signals.rendererDetectKTX2Support.add( function ( ktx2Loader ) {

		ktx2Loader.detectSupport( renderer );

	} );

	signals.sceneGraphChanged.add( function () {

		initPT();
		render();

	} );

	signals.cameraChanged.add( function () {

		pathtracer.reset();

		render();

	} );

	signals.objectSelected.add( function ( object ) {

		selectionBox.visible = false;
		transformControls.detach();

		if ( object !== null && object !== scene && object !== camera ) {

			box.setFromObject( object, true );

			if ( box.isEmpty() === false ) {

				selectionBox.visible = true;

			}

			transformControls.attach( object );

		}

		render();

	} );

	signals.objectFocused.add( function ( object ) {

		controls.focus( object );

	} );

	signals.geometryChanged.add( function ( object ) {

		if ( object !== undefined ) {

			box.setFromObject( object, true );

		}

		initPT();
		render();

	} );

	signals.objectChanged.add( function ( object ) {

		if ( editor.selected === object ) {

			box.setFromObject( object, true );

		}

		if ( object.isPerspectiveCamera ) {

			object.updateProjectionMatrix();

		}

		const helper = editor.helpers[ object.id ];

		if ( helper !== undefined && helper.isSkeletonHelper !== true ) {

			helper.update();

		}

		initPT();
		render();

	} );

	signals.objectRemoved.add( function ( object ) {

		controls.enabled = true; // see #14180

		if ( object === transformControls.object ) {

			transformControls.detach();

		}

	} );

	signals.materialChanged.add( function () {

		updatePTMaterials();
		render();

	} );

	// background

	signals.sceneBackgroundChanged.add( function ( backgroundType, backgroundColor, backgroundTexture, backgroundEquirectangularTexture, backgroundColorSpace, backgroundBlurriness, backgroundIntensity, backgroundRotation ) {

		scene.background = null;

		switch ( backgroundType ) {

			case 'Color':

				scene.background = new THREE.Color( backgroundColor );

				break;

			case 'Texture':

				if ( backgroundTexture ) {

					backgroundTexture.colorSpace = backgroundColorSpace;
					backgroundTexture.needsUpdate = true;

					scene.background = backgroundTexture;

				}

				break;

			case 'Equirectangular':

				if ( backgroundEquirectangularTexture ) {

					backgroundEquirectangularTexture.mapping = THREE.EquirectangularReflectionMapping;
					backgroundEquirectangularTexture.colorSpace = backgroundColorSpace;
					backgroundEquirectangularTexture.needsUpdate = true;

					scene.background = backgroundEquirectangularTexture;
					scene.backgroundBlurriness = backgroundBlurriness;
					scene.backgroundIntensity = backgroundIntensity;
					scene.backgroundRotation.y = backgroundRotation * THREE.MathUtils.DEG2RAD;

					if ( useBackgroundAsEnvironment ) {

						scene.environment = scene.background;
						scene.environmentRotation.y = backgroundRotation * THREE.MathUtils.DEG2RAD;

					}


				}

				break;

		}

		updatePTBackground();
		render();

	} );

	// environment

	let useBackgroundAsEnvironment = false;

	signals.sceneEnvironmentChanged.add( function ( environmentType, environmentEquirectangularTexture ) {

		scene.environment = null;

		useBackgroundAsEnvironment = false;

		switch ( environmentType ) {


			case 'Background':

				useBackgroundAsEnvironment = true;

				if ( scene.background !== null && scene.background.isTexture ) {

					scene.environment = scene.background;
					scene.environment.mapping = THREE.EquirectangularReflectionMapping;
					scene.environmentRotation.y = scene.backgroundRotation.y;

				}

				break;

			case 'Equirectangular':

				if ( environmentEquirectangularTexture ) {

					scene.environment = environmentEquirectangularTexture;
					scene.environment.mapping = THREE.EquirectangularReflectionMapping;

				}

				break;

			case 'Room':

				scene.environment = pmremGenerator.fromScene( new RoomEnvironment(), 0.04 ).texture;

				break;

		}

		updatePTEnvironment();
		render();

	} );

	// fog

	signals.sceneFogChanged.add( function ( fogType, fogColor, fogNear, fogFar, fogDensity ) {

		switch ( fogType ) {

			case 'None':
				scene.fog = null;
				break;
			case 'Fog':
				scene.fog = new THREE.Fog( fogColor, fogNear, fogFar );
				break;
			case 'FogExp2':
				scene.fog = new THREE.FogExp2( fogColor, fogDensity );
				break;

		}

		render();

	} );

	signals.sceneFogSettingsChanged.add( function ( fogType, fogColor, fogNear, fogFar, fogDensity ) {

		switch ( fogType ) {

			case 'Fog':
				scene.fog.color.setHex( fogColor );
				scene.fog.near = fogNear;
				scene.fog.far = fogFar;
				break;
			case 'FogExp2':
				scene.fog.color.setHex( fogColor );
				scene.fog.density = fogDensity;
				break;

		}

		render();

	} );

	signals.viewportCameraChanged.add( function () {

		const viewportCamera = editor.viewportCamera;

		if ( viewportCamera.isPerspectiveCamera || viewportCamera.isOrthographicCamera ) {

			updateAspectRatio();

		}

		// disable EditorControls when setting a user camera

		controls.enabled = ( viewportCamera === editor.camera );

		initPT();
		render();

	} );

	signals.viewportShadingChanged.add( function () {

		const viewportShading = editor.viewportShading;

		switch ( viewportShading ) {

			case 'realistic':
				pathtracer.init( scene, editor.viewportCamera );
				break;

			case 'solid':
				scene.overrideMaterial = null;
				break;

			case 'normals':
				scene.overrideMaterial = new THREE.MeshNormalMaterial();
				break;

			case 'wireframe':
				scene.overrideMaterial = new THREE.MeshBasicMaterial( { color: 0x000000, wireframe: true } );
				break;

		}

		render();

	} );

	//

	signals.windowResize.add( function () {

		updateAspectRatio();

		renderer.setSize( container.dom.offsetWidth, container.dom.offsetHeight );
		pathtracer.setSize( container.dom.offsetWidth, container.dom.offsetHeight );

		render();

	} );

	signals.showHelpersChanged.add( function ( appearanceStates ) {

		grid.visible = appearanceStates.gridHelper;

		sceneHelpers.traverse( function ( object ) {

			switch ( object.type ) {

				case 'CameraHelper':

				{

					object.visible = appearanceStates.cameraHelpers;
					break;

				}

				case 'PointLightHelper':
				case 'DirectionalLightHelper':
				case 'SpotLightHelper':
				case 'HemisphereLightHelper':

				{

					object.visible = appearanceStates.lightHelpers;
					break;

				}

				case 'SkeletonHelper':

				{

					object.visible = appearanceStates.skeletonHelpers;
					break;

				}

				default:

				{

					// not a helper, skip.

				}

			}

		} );


		render();

	} );

	signals.cameraResetted.add( updateAspectRatio );

	// animations

	let prevActionsInUse = 0;

	const clock = new THREE.Clock(); // only used for animations

	function animate() {

		const mixer = editor.mixer;
		const delta = clock.getDelta();

		let needsUpdate = false;

		// Animations

		const actions = mixer.stats.actions;

		if ( actions.inUse > 0 || prevActionsInUse > 0 ) {

			prevActionsInUse = actions.inUse;

			mixer.update( delta );
			needsUpdate = true;

			if ( editor.selected !== null ) {

				editor.selected.updateWorldMatrix( false, true ); // avoid frame late effect for certain skinned meshes (e.g. Michelle.glb)
				selectionBox.box.setFromObject( editor.selected, true ); // selection box should reflect current animation state

			}

		}

		// View Helper

		if ( viewHelper.animating === true ) {

			viewHelper.update( delta );
			needsUpdate = true;

		}

		if ( renderer.xr.isPresenting === true ) {

			needsUpdate = true;

		}

		if ( needsUpdate === true ) render();

		updatePT();

	}

	function initPT() {

		if ( editor.viewportShading === 'realistic' ) {

			pathtracer.init( scene, editor.viewportCamera );

		}

	}

	function updatePTBackground() {

		if ( editor.viewportShading === 'realistic' ) {

			pathtracer.setBackground( scene.background, scene.backgroundBlurriness );

		}

	}

	function updatePTEnvironment() {

		if ( editor.viewportShading === 'realistic' ) {

			pathtracer.setEnvironment( scene.environment );

		}

	}

	function updatePTMaterials() {

		if ( editor.viewportShading === 'realistic' ) {

			pathtracer.updateMaterials();

		}

	}

	function updatePT() {

		if ( editor.viewportShading === 'realistic' ) {

			pathtracer.update();
			editor.signals.pathTracerUpdated.dispatch( pathtracer.getSamples() );

		}

	}

	//

	let startTime = 0;
	let endTime = 0;

	function render() {

		startTime = performance.now();

		renderer.setViewport( 0, 0, container.dom.offsetWidth, container.dom.offsetHeight );
		renderer.render( scene, editor.viewportCamera );

		if ( camera === editor.viewportCamera ) {

			renderer.autoClear = false;
			if ( grid.visible === true ) renderer.render( grid, camera );
			if ( sceneHelpers.visible === true ) renderer.render( sceneHelpers, camera );
			if ( renderer.xr.isPresenting !== true ) viewHelper.render( renderer );
			renderer.autoClear = true;

		}

		endTime = performance.now();
		editor.signals.sceneRendered.dispatch( endTime - startTime );

	}

	return container;

}
```
</details>

### `updateAspectRatio(): void`

**Returns:** `void`

**Calls:**

- `camera.updateProjectionMatrix`
- `cameraHelper.update`

<details><summary>Code</summary>

```typescript
function updateAspectRatio() {

		for ( const uuid in editor.cameras ) {

			const camera = editor.cameras[ uuid ];

			const aspect = container.dom.offsetWidth / container.dom.offsetHeight;

			if ( camera.isPerspectiveCamera ) {

				camera.aspect = aspect;

			} else {

				camera.left = - aspect;
				camera.right = aspect;

			}

			camera.updateProjectionMatrix();

			const cameraHelper = editor.helpers[ camera.id ];
			if ( cameraHelper ) cameraHelper.update();

		}

	}
```
</details>

### `getMousePosition(dom: any, x: any, y: any): number[]`

**Parameters:**

- **`dom`** `any`
- **`x`** `any`
- **`y`** `any`

**Returns:** `number[]`

**Calls:**

- `dom.getBoundingClientRect`

<details><summary>Code</summary>

```typescript
function getMousePosition( dom, x, y ) {

		const rect = dom.getBoundingClientRect();
		return [ ( x - rect.left ) / rect.width, ( y - rect.top ) / rect.height ];

	}
```
</details>

### `handleClick(): void`

**Returns:** `void`

**Calls:**

- `onDownPosition.distanceTo`
- `selector.getPointerIntersects`
- `signals.intersectionsDetected.dispatch`
- `render`

<details><summary>Code</summary>

```typescript
function handleClick() {

		if ( onDownPosition.distanceTo( onUpPosition ) === 0 ) {

			const intersects = selector.getPointerIntersects( onUpPosition, camera );
			signals.intersectionsDetected.dispatch( intersects );

			render();

		}

	}
```
</details>

### `onMouseDown(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `getMousePosition`
- `onDownPosition.fromArray`
- `document.addEventListener`

**Internal Comments:**
```
// event.preventDefault();
```

<details><summary>Code</summary>

```typescript
function onMouseDown( event ) {

		// event.preventDefault();

		if ( event.target !== renderer.domElement ) return;

		const array = getMousePosition( container.dom, event.clientX, event.clientY );
		onDownPosition.fromArray( array );

		document.addEventListener( 'mouseup', onMouseUp );

	}
```
</details>

### `onMouseUp(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `getMousePosition`
- `onUpPosition.fromArray`
- `handleClick`
- `document.removeEventListener`

<details><summary>Code</summary>

```typescript
function onMouseUp( event ) {

		const array = getMousePosition( container.dom, event.clientX, event.clientY );
		onUpPosition.fromArray( array );

		handleClick();

		document.removeEventListener( 'mouseup', onMouseUp );

	}
```
</details>

### `onTouchStart(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `getMousePosition`
- `onDownPosition.fromArray`
- `document.addEventListener`

<details><summary>Code</summary>

```typescript
function onTouchStart( event ) {

		const touch = event.changedTouches[ 0 ];

		const array = getMousePosition( container.dom, touch.clientX, touch.clientY );
		onDownPosition.fromArray( array );

		document.addEventListener( 'touchend', onTouchEnd );

	}
```
</details>

### `onTouchEnd(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `getMousePosition`
- `onUpPosition.fromArray`
- `handleClick`
- `document.removeEventListener`

<details><summary>Code</summary>

```typescript
function onTouchEnd( event ) {

		const touch = event.changedTouches[ 0 ];

		const array = getMousePosition( container.dom, touch.clientX, touch.clientY );
		onUpPosition.fromArray( array );

		handleClick();

		document.removeEventListener( 'touchend', onTouchEnd );

	}
```
</details>

### `onDoubleClick(event: any): void`

**Parameters:**

- **`event`** `any`

**Returns:** `void`

**Calls:**

- `getMousePosition`
- `onDoubleClickPosition.fromArray`
- `selector.getPointerIntersects`
- `signals.objectFocused.dispatch`

<details><summary>Code</summary>

```typescript
function onDoubleClick( event ) {

		const array = getMousePosition( container.dom, event.clientX, event.clientY );
		onDoubleClickPosition.fromArray( array );

		const intersects = selector.getPointerIntersects( onDoubleClickPosition, camera );

		if ( intersects.length > 0 ) {

			const intersect = intersects[ 0 ];

			signals.objectFocused.dispatch( intersect.object );

		}

	}
```
</details>

### `animate(): void`

**Returns:** `void`

**Calls:**

- `clock.getDelta`
- `mixer.update`
- `editor.selected.updateWorldMatrix`
- `selectionBox.box.setFromObject`
- `viewHelper.update`
- `render`
- `updatePT`

**Internal Comments:**
```
// Animations (x2)
// View Helper
```

<details><summary>Code</summary>

```typescript
function animate() {

		const mixer = editor.mixer;
		const delta = clock.getDelta();

		let needsUpdate = false;

		// Animations

		const actions = mixer.stats.actions;

		if ( actions.inUse > 0 || prevActionsInUse > 0 ) {

			prevActionsInUse = actions.inUse;

			mixer.update( delta );
			needsUpdate = true;

			if ( editor.selected !== null ) {

				editor.selected.updateWorldMatrix( false, true ); // avoid frame late effect for certain skinned meshes (e.g. Michelle.glb)
				selectionBox.box.setFromObject( editor.selected, true ); // selection box should reflect current animation state

			}

		}

		// View Helper

		if ( viewHelper.animating === true ) {

			viewHelper.update( delta );
			needsUpdate = true;

		}

		if ( renderer.xr.isPresenting === true ) {

			needsUpdate = true;

		}

		if ( needsUpdate === true ) render();

		updatePT();

	}
```
</details>

### `initPT(): void`

**Returns:** `void`

**Calls:**

- `pathtracer.init`

<details><summary>Code</summary>

```typescript
function initPT() {

		if ( editor.viewportShading === 'realistic' ) {

			pathtracer.init( scene, editor.viewportCamera );

		}

	}
```
</details>

### `updatePTBackground(): void`

**Returns:** `void`

**Calls:**

- `pathtracer.setBackground`

<details><summary>Code</summary>

```typescript
function updatePTBackground() {

		if ( editor.viewportShading === 'realistic' ) {

			pathtracer.setBackground( scene.background, scene.backgroundBlurriness );

		}

	}
```
</details>

### `updatePTEnvironment(): void`

**Returns:** `void`

**Calls:**

- `pathtracer.setEnvironment`

<details><summary>Code</summary>

```typescript
function updatePTEnvironment() {

		if ( editor.viewportShading === 'realistic' ) {

			pathtracer.setEnvironment( scene.environment );

		}

	}
```
</details>

### `updatePTMaterials(): void`

**Returns:** `void`

**Calls:**

- `pathtracer.updateMaterials`

<details><summary>Code</summary>

```typescript
function updatePTMaterials() {

		if ( editor.viewportShading === 'realistic' ) {

			pathtracer.updateMaterials();

		}

	}
```
</details>

### `updatePT(): void`

**Returns:** `void`

**Calls:**

- `pathtracer.update`
- `editor.signals.pathTracerUpdated.dispatch`
- `pathtracer.getSamples`

<details><summary>Code</summary>

```typescript
function updatePT() {

		if ( editor.viewportShading === 'realistic' ) {

			pathtracer.update();
			editor.signals.pathTracerUpdated.dispatch( pathtracer.getSamples() );

		}

	}
```
</details>

### `render(): void`

**Returns:** `void`

**Calls:**

- `performance.now`
- `renderer.setViewport`
- `renderer.render`
- `viewHelper.render`
- `editor.signals.sceneRendered.dispatch`

<details><summary>Code</summary>

```typescript
function render() {

		startTime = performance.now();

		renderer.setViewport( 0, 0, container.dom.offsetWidth, container.dom.offsetHeight );
		renderer.render( scene, editor.viewportCamera );

		if ( camera === editor.viewportCamera ) {

			renderer.autoClear = false;
			if ( grid.visible === true ) renderer.render( grid, camera );
			if ( sceneHelpers.visible === true ) renderer.render( sceneHelpers, camera );
			if ( renderer.xr.isPresenting !== true ) viewHelper.render( renderer );
			renderer.autoClear = true;

		}

		endTime = performance.now();
		editor.signals.sceneRendered.dispatch( endTime - startTime );

	}
```
</details>

### `updateGridColors(grid1: any, grid2: any, colors: any): void`

**Parameters:**

- **`grid1`** `any`
- **`grid2`** `any`
- **`colors`** `any`

**Returns:** `void`

**Calls:**

- `grid1.material.color.setHex`
- `grid2.material.color.setHex`

<details><summary>Code</summary>

```typescript
function updateGridColors( grid1, grid2, colors ) {

	grid1.material.color.setHex( colors[ 0 ] );
	grid2.material.color.setHex( colors[ 1 ] );

}
```
</details>


---