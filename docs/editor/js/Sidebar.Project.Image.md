[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Project.Image.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 21 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Project.Image.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIBreak` | `./libs/ui.js` |
| `UIButton` | `./libs/ui.js` |
| `UIInteger` | `./libs/ui.js` |
| `UIPanel` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UISelect` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `ViewportPathtracer` | `./Viewport.Pathtracer.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `shadingRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `pathTracerMinSamples` | `3` | let/var | `3` | ✗ |
| `pathTracerMaxSamples` | `65536` | let/var | `65536` | ✗ |
| `samplesRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `resolutionRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `renderButton` | `UIButton` | let/var | `new UIButton( strings.getKey( 'sidebar/project/render' ) )` | ✗ |
| `isMaterialsValid` | `boolean` | let/var | `true` | ✗ |
| `materials` | `any` | let/var | `Array.isArray( object.material ) ? object.material : [ object.material ]` | ✗ |
| `material` | `any` | let/var | `materials[ i ]` | ✗ |
| `project` | `any` | let/var | `json.project` | ✗ |
| `loader` | `any` | let/var | `new THREE.ObjectLoader()` | ✗ |
| `renderer` | `any` | let/var | `new THREE.WebGLRenderer( { antialias: true } )` | ✗ |
| `width` | `number` | let/var | `imageWidth.getValue() / window.devicePixelRatio` | ✗ |
| `height` | `number` | let/var | `imageHeight.getValue() / window.devicePixelRatio` | ✗ |
| `left` | `number` | let/var | `( screen.width - width ) / 2` | ✗ |
| `top` | `number` | let/var | `( screen.height - height ) / 2` | ✗ |
| `canvas` | `any` | let/var | `renderer.domElement` | ✗ |
| `pathTracer` | `any` | let/var | `new ViewportPathtracer( renderer )` | ✗ |
| `samples` | `number` | let/var | `Math.floor( pathTracer.getSamples() ) + 1` | ✗ |


---

## Functions

### `SidebarProjectImage(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.setId`
- `container.add`
- `new UIText( strings.getKey( 'sidebar/project/image' ) ).setTextTransform`
- `strings.getKey`
- `shadingRow.add`
- `new UIText( strings.getKey( 'sidebar/project/shading' ) ).setClass`
- `new UISelect().setOptions( {
		'solid': 'SOLID',
		'realistic': 'REALISTIC'
	} ).setWidth( '170px' ).onChange( refreshShadingRow ).setValue`
- `new UIInteger( 16 ).setRange`
- `samplesRow.add`
- `new UIText( strings.getKey( 'sidebar/project/image/samples' ) ).setClass`
- `samplesRow.setHidden`
- `shadingTypeSelect.getValue`
- `refreshShadingRow`
- `resolutionRow.add`
- `new UIText( strings.getKey( 'sidebar/project/resolution' ) ).setClass`
- `new UIInteger( 1024 ).setTextAlign( 'center' ).setWidth`
- `new UIText( '×' ).setTextAlign( 'center' ).setFontSize( '12px' ).setWidth`
- `renderButton.setWidth`
- `renderButton.setMarginLeft`
- `renderButton.onClick`
- `editor.scene.traverseVisible`
- `Array.isArray`
- `alert`
- `editor.toJSON`
- `loader.parse`
- `imageWidth.getValue`
- `imageHeight.getValue`
- `camera.updateProjectionMatrix`
- `camera.updateMatrixWorld`
- `renderer.setSize`
- `window.open`
- `document.createElement`
- `output.document.head.appendChild`
- `output.document.body.appendChild`
- `renderer.render`
- `renderer.dispose`
- `pathTracer.init`
- `pathTracer.setSize`
- `Math.max`
- `Math.min`
- `samplesNumber.getValue`
- `Math.floor`
- `pathTracer.getSamples`
- `requestAnimationFrame`
- `pathTracer.update`
- `animate`

**Internal Comments:**
```
// Image (x4)
// Shading (x2)
// Resolution (x2)
// Render (x2)
// (x6)
// popup (x2)
```

<details><summary>Code</summary>

```typescript
function SidebarProjectImage( editor ) {

	const strings = editor.strings;

	const container = new UIPanel();
	container.setId( 'render' );

	// Image

	container.add( new UIText( strings.getKey( 'sidebar/project/image' ) ).setTextTransform( 'uppercase' ) );
	container.add( new UIBreak(), new UIBreak() );

	// Shading

	const shadingRow = new UIRow();
	container.add( shadingRow );

	shadingRow.add( new UIText( strings.getKey( 'sidebar/project/shading' ) ).setClass( 'Label' ) );

	const shadingTypeSelect = new UISelect().setOptions( {
		'solid': 'SOLID',
		'realistic': 'REALISTIC'
	} ).setWidth( '170px' ).onChange( refreshShadingRow ).setValue( 'solid' );
	shadingRow.add( shadingTypeSelect );

	const pathTracerMinSamples = 3;
	const pathTracerMaxSamples = 65536;
	const samplesNumber = new UIInteger( 16 ).setRange( pathTracerMinSamples, pathTracerMaxSamples );

	const samplesRow = new UIRow();
	samplesRow.add( new UIText( strings.getKey( 'sidebar/project/image/samples' ) ).setClass( 'Label' ) );
	samplesRow.add( samplesNumber );

	container.add( samplesRow );

	function refreshShadingRow() {

		samplesRow.setHidden( shadingTypeSelect.getValue() !== 'realistic' );

	}

	refreshShadingRow();

	// Resolution

	const resolutionRow = new UIRow();
	container.add( resolutionRow );

	resolutionRow.add( new UIText( strings.getKey( 'sidebar/project/resolution' ) ).setClass( 'Label' ) );

	const imageWidth = new UIInteger( 1024 ).setTextAlign( 'center' ).setWidth( '28px' );
	resolutionRow.add( imageWidth );

	resolutionRow.add( new UIText( '×' ).setTextAlign( 'center' ).setFontSize( '12px' ).setWidth( '12px' ) );

	const imageHeight = new UIInteger( 1024 ).setTextAlign( 'center' ).setWidth( '28px' );
	resolutionRow.add( imageHeight );

	// Render

	const renderButton = new UIButton( strings.getKey( 'sidebar/project/render' ) );
	renderButton.setWidth( '170px' );
	renderButton.setMarginLeft( '120px' );
	renderButton.onClick( async () => {

		if ( shadingTypeSelect.getValue() === 'realistic' ) {

			let isMaterialsValid = true;

			editor.scene.traverseVisible( ( object ) => {

				if ( object.isMesh ) {

					const materials = Array.isArray( object.material ) ? object.material : [ object.material ];

					for ( let i = 0; i < materials.length; i ++ ) {

						const material = materials[ i ];

						if ( ! material.isMeshStandardMaterial ) {

							isMaterialsValid = false;
							return;

						}

					}

				}

			} );

			if ( isMaterialsValid === false ) {

				alert( strings.getKey( 'prompt/rendering/realistic/unsupportedMaterial' ) );
				return;

			}

		}

		//

		const json = editor.toJSON();
		const project = json.project;

		//

		const loader = new THREE.ObjectLoader();

		const camera = loader.parse( json.camera );
		camera.aspect = imageWidth.getValue() / imageHeight.getValue();
		camera.updateProjectionMatrix();
		camera.updateMatrixWorld();

		const scene = loader.parse( json.scene );

		const renderer = new THREE.WebGLRenderer( { antialias: true } );
		renderer.setSize( imageWidth.getValue(), imageHeight.getValue() );

		if ( project.shadows !== undefined ) renderer.shadowMap.enabled = project.shadows;
		if ( project.shadowType !== undefined ) renderer.shadowMap.type = project.shadowType;
		if ( project.toneMapping !== undefined ) renderer.toneMapping = project.toneMapping;
		if ( project.toneMappingExposure !== undefined ) renderer.toneMappingExposure = project.toneMappingExposure;

		// popup

		const width = imageWidth.getValue() / window.devicePixelRatio;
		const height = imageHeight.getValue() / window.devicePixelRatio;

		const left = ( screen.width - width ) / 2;
		const top = ( screen.height - height ) / 2;

		const output = window.open( '', '_blank', `location=no,left=${left},top=${top},width=${width},height=${height}` );

		const meta = document.createElement( 'meta' );
		meta.name = 'viewport';
		meta.content = 'width=device-width, user-scalable=no, minimum-scale=1.0, maximum-scale=1.0';
		output.document.head.appendChild( meta );

		output.document.body.style.background = '#000';
		output.document.body.style.margin = '0px';
		output.document.body.style.overflow = 'hidden';

		const canvas = renderer.domElement;
		canvas.style.width = width + 'px';
		canvas.style.height = height + 'px';
		output.document.body.appendChild( canvas );

		//

		switch ( shadingTypeSelect.getValue() ) {

			case 'solid':

				renderer.render( scene, camera );
				renderer.dispose();

				break;

			case 'realistic':

				const status = document.createElement( 'div' );
				status.style.position = 'absolute';
				status.style.top = '10px';
				status.style.left = '10px';
				status.style.color = 'white';
				status.style.fontFamily = 'system-ui';
				status.style.fontSize = '12px';
				output.document.body.appendChild( status );

				const pathTracer = new ViewportPathtracer( renderer );
				pathTracer.init( scene, camera );
				pathTracer.setSize( imageWidth.getValue(), imageHeight.getValue() );

				const maxSamples = Math.max( pathTracerMinSamples, Math.min( pathTracerMaxSamples, samplesNumber.getValue() ) );

				function animate() {

					if ( output.closed === true ) return;

					const samples = Math.floor( pathTracer.getSamples() ) + 1;

					if ( samples < maxSamples ) {

						requestAnimationFrame( animate );

					}

					pathTracer.update();

					const progress = Math.floor( samples / maxSamples * 100 );

					status.textContent = `${ samples } / ${ maxSamples } ( ${ progress }% )`;

					if ( progress === 100 ) {

						status.textContent += ' ✓';

					}

				}

				animate();

				break;

		}

	} );
	container.add( renderButton );

	//

	return container;

}
```
</details>

### `refreshShadingRow(): void`

**Returns:** `void`

**Calls:**

- `samplesRow.setHidden`
- `shadingTypeSelect.getValue`

<details><summary>Code</summary>

```typescript
function refreshShadingRow() {

		samplesRow.setHidden( shadingTypeSelect.getValue() !== 'realistic' );

	}
```
</details>

### `animate(): void`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `pathTracer.getSamples`
- `requestAnimationFrame`
- `pathTracer.update`

<details><summary>Code</summary>

```typescript
function animate() {

					if ( output.closed === true ) return;

					const samples = Math.floor( pathTracer.getSamples() ) + 1;

					if ( samples < maxSamples ) {

						requestAnimationFrame( animate );

					}

					pathTracer.update();

					const progress = Math.floor( samples / maxSamples * 100 );

					status.textContent = `${ samples } / ${ maxSamples } ( ${ progress }% )`;

					if ( progress === 100 ) {

						status.textContent += ' ✓';

					}

				}
```
</details>


---