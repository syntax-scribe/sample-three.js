[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Viewport.Controls.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 8 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Viewport.Controls.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIPanel` | `./libs/ui.js` |
| `UISelect` | `./libs/ui.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `cameraSelect` | `UISelect` | let/var | `new UISelect()` | ✗ |
| `shadingSelect` | `UISelect` | let/var | `new UISelect()` | ✗ |
| `options` | `{}` | let/var | `{}` | ✗ |
| `cameras` | `any` | let/var | `editor.cameras` | ✗ |
| `camera` | `any` | let/var | `cameras[ key ]` | ✗ |
| `selectedCamera` | `any` | let/var | `( editor.viewportCamera.uuid in options ) ? editor.viewportCamera : editor.ca...` | ✗ |


---

## Functions

### `ViewportControls(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.setPosition`
- `container.setRight`
- `container.setTop`
- `container.setColor`
- `cameraSelect.setMarginLeft`
- `cameraSelect.setMarginRight`
- `cameraSelect.onChange`
- `editor.setViewportCamera`
- `this.getValue`
- `container.add`
- `signals.cameraAdded.add`
- `signals.cameraRemoved.add`
- `signals.objectChanged.add`
- `update`
- `shadingSelect.setOptions`
- `shadingSelect.setValue`
- `shadingSelect.onChange`
- `editor.setViewportShading`
- `signals.editorCleared.add`
- `shadingSelect.getValue`
- `signals.cameraResetted.add`
- `cameraSelect.setOptions`
- `cameraSelect.setValue`

**Internal Comments:**
```
// camera (x2)
// shading (x2)
//
```

<details><summary>Code</summary>

```typescript
function ViewportControls( editor ) {

	const signals = editor.signals;

	const container = new UIPanel();
	container.setPosition( 'absolute' );
	container.setRight( '10px' );
	container.setTop( '10px' );
	container.setColor( '#ffffff' );

	// camera

	const cameraSelect = new UISelect();
	cameraSelect.setMarginLeft( '10px' );
	cameraSelect.setMarginRight( '10px' );
	cameraSelect.onChange( function () {

		editor.setViewportCamera( this.getValue() );

	} );
	container.add( cameraSelect );

	signals.cameraAdded.add( update );
	signals.cameraRemoved.add( update );
	signals.objectChanged.add( function ( object ) {

		if ( object.isCamera ) {

			update();

		}

	} );

	// shading

	const shadingSelect = new UISelect();
	shadingSelect.setOptions( { 'realistic': 'realistic', 'solid': 'solid', 'normals': 'normals', 'wireframe': 'wireframe' } );
	shadingSelect.setValue( 'solid' );
	shadingSelect.onChange( function () {

		editor.setViewportShading( this.getValue() );

	} );
	container.add( shadingSelect );

	signals.editorCleared.add( function () {

		editor.setViewportCamera( editor.camera.uuid );

		shadingSelect.setValue( 'solid' );
		editor.setViewportShading( shadingSelect.getValue() );

	} );

	signals.cameraResetted.add( update );

	update();

	//

	function update() {

		const options = {};

		const cameras = editor.cameras;

		for ( const key in cameras ) {

			const camera = cameras[ key ];
			options[ camera.uuid ] = camera.name;

		}

		cameraSelect.setOptions( options );

		const selectedCamera = ( editor.viewportCamera.uuid in options )
			? editor.viewportCamera
			: editor.camera;

		cameraSelect.setValue( selectedCamera.uuid );
		editor.setViewportCamera( selectedCamera.uuid );

	}

	return container;

}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `cameraSelect.setOptions`
- `cameraSelect.setValue`
- `editor.setViewportCamera`

<details><summary>Code</summary>

```typescript
function update() {

		const options = {};

		const cameras = editor.cameras;

		for ( const key in cameras ) {

			const camera = cameras[ key ];
			options[ camera.uuid ] = camera.name;

		}

		cameraSelect.setOptions( options );

		const selectedCamera = ( editor.viewportCamera.uuid in options )
			? editor.viewportCamera
			: editor.camera;

		cameraSelect.setValue( selectedCamera.uuid );
		editor.setViewportCamera( selectedCamera.uuid );

	}
```
</details>


---