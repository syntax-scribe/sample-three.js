[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Menubar.View.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 8 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Menubar.View.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIHorizontalRule` | `./libs/ui.js` |
| `UIPanel` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `title` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `options` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `states` | `{ gridHelper: boolean; cameraHelpers:...` | let/var | `{ gridHelper: true, cameraHelpers: true, lightHelpers: true, skeletonHelpers:...` | ✗ |
| `option` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `option` | `UIRow` | let/var | `new UIRow()` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| promise-chain | `MenubarView` | *none* | navigator.xr.isSessionSupported( 'immersive-ar' ).then, navigator.xr.isSessionSupported( 'immersive-vr' ).then |


---

## Functions

### `MenubarView(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.setClass`
- `title.setClass`
- `title.setTextContent`
- `strings.getKey`
- `container.add`
- `options.setClass`
- `new UIRow().addClass( 'option' ).addClass( 'toggle' ).setTextContent( strings.getKey( 'menubar/view/gridHelper' ) ).onClick( function () {

		states.gridHelper = ! states.gridHelper;

		this.toggleClass( 'toggle-on', states.gridHelper );

		signals.showHelpersChanged.dispatch( states );

	} ).toggleClass`
- `options.add`
- `new UIRow().addClass( 'option' ).addClass( 'toggle' ).setTextContent( strings.getKey( 'menubar/view/cameraHelpers' ) ).onClick( function () {

		states.cameraHelpers = ! states.cameraHelpers;

		this.toggleClass( 'toggle-on', states.cameraHelpers );

		signals.showHelpersChanged.dispatch( states );

	} ).toggleClass`
- `new UIRow().addClass( 'option' ).addClass( 'toggle' ).setTextContent( strings.getKey( 'menubar/view/lightHelpers' ) ).onClick( function () {

		states.lightHelpers = ! states.lightHelpers;

		this.toggleClass( 'toggle-on', states.lightHelpers );

		signals.showHelpersChanged.dispatch( states );

	} ).toggleClass`
- `new UIRow().addClass( 'option' ).addClass( 'toggle' ).setTextContent( strings.getKey( 'menubar/view/skeletonHelpers' ) ).onClick( function () {

		states.skeletonHelpers = ! states.skeletonHelpers;

		this.toggleClass( 'toggle-on', states.skeletonHelpers );

		signals.showHelpersChanged.dispatch( states );

	} ).toggleClass`
- `signals.helperAdded.add`
- `signals.showHelpersChanged.dispatch`
- `option.setClass`
- `option.setTextContent`
- `option.onClick`
- `document.documentElement.requestFullscreen`
- `document.exitFullscreen`
- `document.documentElement.webkitRequestFullscreen`
- `document.webkitExitFullscreen`
- `signals.offerXR.dispatch`
- `navigator.xr.isSessionSupported( 'immersive-ar' )
				.then`
- `signals.enterXR.dispatch`
- `navigator.xr.isSessionSupported( 'immersive-vr' )
							.then`

**Internal Comments:**
```
// Helpers (x2)
// Grid Helper (x2)
// Camera Helpers (x3)
// Light Helpers (x3)
// Skeleton Helpers (x3)
// new helpers are visible by default, the global visibility state (x5)
// of helpers is managed in this component. every time a helper is added, (x5)
// we request a viewport updated by firing the showHelpersChanged signal. (x5)
// (x5)
// Fullscreen (x3)
// Safari
// XR (Work in progress)
```

<details><summary>Code</summary>

```typescript
function MenubarView( editor ) {

	const signals = editor.signals;
	const strings = editor.strings;

	const container = new UIPanel();
	container.setClass( 'menu' );

	const title = new UIPanel();
	title.setClass( 'title' );
	title.setTextContent( strings.getKey( 'menubar/view' ) );
	container.add( title );

	const options = new UIPanel();
	options.setClass( 'options' );
	container.add( options );

	// Helpers

	const states = {

		gridHelper: true,
		cameraHelpers: true,
		lightHelpers: true,
		skeletonHelpers: true

	};

	// Grid Helper

	let option = new UIRow().addClass( 'option' ).addClass( 'toggle' ).setTextContent( strings.getKey( 'menubar/view/gridHelper' ) ).onClick( function () {

		states.gridHelper = ! states.gridHelper;

		this.toggleClass( 'toggle-on', states.gridHelper );

		signals.showHelpersChanged.dispatch( states );

	} ).toggleClass( 'toggle-on', states.gridHelper );

	options.add( option );

	// Camera Helpers

	option = new UIRow().addClass( 'option' ).addClass( 'toggle' ).setTextContent( strings.getKey( 'menubar/view/cameraHelpers' ) ).onClick( function () {

		states.cameraHelpers = ! states.cameraHelpers;

		this.toggleClass( 'toggle-on', states.cameraHelpers );

		signals.showHelpersChanged.dispatch( states );

	} ).toggleClass( 'toggle-on', states.cameraHelpers );

	options.add( option );

	// Light Helpers

	option = new UIRow().addClass( 'option' ).addClass( 'toggle' ).setTextContent( strings.getKey( 'menubar/view/lightHelpers' ) ).onClick( function () {

		states.lightHelpers = ! states.lightHelpers;

		this.toggleClass( 'toggle-on', states.lightHelpers );

		signals.showHelpersChanged.dispatch( states );

	} ).toggleClass( 'toggle-on', states.lightHelpers );

	options.add( option );

	// Skeleton Helpers

	option = new UIRow().addClass( 'option' ).addClass( 'toggle' ).setTextContent( strings.getKey( 'menubar/view/skeletonHelpers' ) ).onClick( function () {

		states.skeletonHelpers = ! states.skeletonHelpers;

		this.toggleClass( 'toggle-on', states.skeletonHelpers );

		signals.showHelpersChanged.dispatch( states );

	} ).toggleClass( 'toggle-on', states.skeletonHelpers );

	options.add( option );

	// new helpers are visible by default, the global visibility state
	// of helpers is managed in this component. every time a helper is added,
	// we request a viewport updated by firing the showHelpersChanged signal.

	signals.helperAdded.add( function () {

		signals.showHelpersChanged.dispatch( states );

	} );

	//

	options.add( new UIHorizontalRule() );

	// Fullscreen

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/view/fullscreen' ) );
	option.onClick( function () {

		if ( document.fullscreenElement === null ) {

			document.documentElement.requestFullscreen();

		} else if ( document.exitFullscreen ) {

			document.exitFullscreen();

		}

		// Safari

		if ( document.webkitFullscreenElement === null ) {

			document.documentElement.webkitRequestFullscreen();

		} else if ( document.webkitExitFullscreen ) {

			document.webkitExitFullscreen();

		}

	} );
	options.add( option );

	// XR (Work in progress)

	if ( 'xr' in navigator ) {

		if ( 'offerSession' in navigator.xr ) {

			signals.offerXR.dispatch( 'immersive-ar' );

		} else {

			navigator.xr.isSessionSupported( 'immersive-ar' )
				.then( function ( supported ) {

					if ( supported ) {

						const option = new UIRow();
						option.setClass( 'option' );
						option.setTextContent( 'AR' );
						option.onClick( function () {

							signals.enterXR.dispatch( 'immersive-ar' );

						} );
						options.add( option );

					} else {

						navigator.xr.isSessionSupported( 'immersive-vr' )
							.then( function ( supported ) {

								if ( supported ) {

									const option = new UIRow();
									option.setClass( 'option' );
									option.setTextContent( 'VR' );
									option.onClick( function () {

										signals.enterXR.dispatch( 'immersive-vr' );

									} );
									options.add( option );

								}

							} );

					}

				} );

		}

	}

	//

	return container;

}
```
</details>


---