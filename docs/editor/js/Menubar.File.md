[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Menubar.File.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 29 |
| ⚡ Async/Await Patterns | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Menubar.File.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIPanel` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIHorizontalRule` | `./libs/ui.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `saveArrayBuffer` | `any` | let/var | `editor.utils.saveArrayBuffer` | ✗ |
| `saveString` | `any` | let/var | `editor.utils.saveString` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `title` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `options` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `examples` | `{ title: string; file: string; }[]` | let/var | `[ { title: 'menubar/file/new/Arkanoid', file: 'arkanoid.app.json' }, { title:...` | ✗ |
| `loader` | `any` | let/var | `new THREE.FileLoader()` | ✗ |
| `example` | `{ title: string; file: string; }` | let/var | `examples[ i ]` | ✗ |
| `option` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `file` | `File` | let/var | `openProjectInput.files[ 0 ]` | ✗ |
| `blob` | `Blob` | let/var | `new Blob( [ JSON.stringify( json ) ], { type: 'application/json' } )` | ✗ |
| `object` | `any` | let/var | `editor.selected` | ✗ |
| `exporter` | `any` | let/var | `new DRACOExporter()` | ✗ |
| `options` | `{ decodeSpeed: number; encodeSpeed: n...` | let/var | `{ decodeSpeed: 5, encodeSpeed: 5, encoderMethod: DRACOExporter.MESH_EDGEBREAK...` | ✗ |
| `scene` | `any` | let/var | `editor.scene` | ✗ |
| `optimizedAnimations` | `any[]` | let/var | `[]` | ✗ |
| `exporter` | `any` | let/var | `new GLTFExporter()` | ✗ |
| `scene` | `any` | let/var | `editor.scene` | ✗ |
| `optimizedAnimations` | `any[]` | let/var | `[]` | ✗ |
| `exporter` | `any` | let/var | `new GLTFExporter()` | ✗ |
| `object` | `any` | let/var | `editor.selected` | ✗ |
| `exporter` | `any` | let/var | `new OBJExporter()` | ✗ |
| `exporter` | `any` | let/var | `new PLYExporter()` | ✗ |
| `exporter` | `any` | let/var | `new PLYExporter()` | ✗ |
| `exporter` | `any` | let/var | `new STLExporter()` | ✗ |
| `exporter` | `any` | let/var | `new STLExporter()` | ✗ |
| `exporter` | `any` | let/var | `new USDZExporter()` | ✗ |
| `animations` | `any[]` | let/var | `[]` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| await-expression | `MenubarFile` | file.text(), editor.fromJSON( json ), import( 'three/addons/exporters/DRACOExporter.js' ), import( 'three/addons/exporters/GLTFExporter.js' ), import( 'three/addons/exporters/GLTFExporter.js' ), import( 'three/addons/exporters/OBJExporter.js' ), import( 'three/addons/exporters/PLYExporter.js' ), import( 'three/addons/exporters/PLYExporter.js' ), import( 'three/addons/exporters/STLExporter.js' ), import( 'three/addons/exporters/STLExporter.js' ), import( 'three/addons/exporters/USDZExporter.js' ), exporter.parseAsync( editor.scene ) | *none* |
| async-function | `onEditorCleared` | editor.fromJSON( json ) | *none* |


---

## Functions

### `MenubarFile(editor: any): UIPanel`

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
- `new UIRow().setTextContent( strings.getKey( 'menubar/file/new' ) ).addClass( 'option' ).addClass`
- `newProjectSubmenuTitle.onMouseOver`
- `this.dom.getBoundingClientRect`
- `getComputedStyle`
- `newProjectSubmenu.setLeft`
- `newProjectSubmenu.setTop`
- `parseFloat`
- `newProjectSubmenu.setDisplay`
- `newProjectSubmenuTitle.onMouseOut`
- `options.add`
- `new UIPanel().setPosition( 'fixed' ).addClass( 'options' ).setDisplay`
- `newProjectSubmenuTitle.add`
- `new UIRow().setTextContent( strings.getKey( 'menubar/file/new/empty' ) ).setClass`
- `option.onClick`
- `confirm`
- `editor.clear`
- `newProjectSubmenu.add`
- `complex_call_2152`
- `option.setClass`
- `option.setTextContent`
- `loader.load`
- `editor.fromJSON`
- `JSON.parse`
- `document.createElement`
- `document.body.appendChild`
- `openProjectInput.addEventListener`
- `file.text`
- `editor.signals.editorCleared.remove`
- `editor.signals.editorCleared.add`
- `alert`
- `console.error`
- `form.reset`
- `openProjectForm.appendChild`
- `new UIRow()
		.addClass( 'option' )
		.setTextContent( strings.getKey( 'menubar/file/open' ) )
		.onClick`
- `openProjectInput.click`
- `new UIRow()
		.addClass( 'option' )
		.setTextContent( strings.getKey( 'menubar/file/save' ) )
		.onClick`
- `editor.toJSON`
- `JSON.stringify`
- `editor.utils.save`
- `fileInput.addEventListener`
- `editor.loader.loadFiles`
- `form.appendChild`
- `fileInput.click`
- `new UIRow().setTextContent( strings.getKey( 'menubar/file/export' ) ).addClass( 'option' ).addClass`
- `fileExportSubmenuTitle.onMouseOver`
- `fileExportSubmenu.setLeft`
- `fileExportSubmenu.setTop`
- `fileExportSubmenu.setDisplay`
- `fileExportSubmenuTitle.onMouseOut`
- `fileExportSubmenuTitle.add`
- `complex_call_5989`
- `object.geometry.hasAttribute`
- `exporter.parse`
- `saveArrayBuffer`
- `fileExportSubmenu.add`
- `getAnimations`
- `optimizedAnimations.push`
- `animation.clone().optimize`
- `complex_call_6939`
- `complex_call_7631`
- `saveString`
- `complex_call_8258`
- `complex_call_8626`
- `complex_call_9055`
- `complex_call_9499`
- `complex_call_9883`
- `complex_call_10282`
- `exporter.parseAsync`
- `scene.traverse`
- `animations.push`

**Internal Comments:**
```
// New Project (x2)
// New Project / Empty (x2)
// (x9)
// New Project / ... (x2)
// Open (x2)
// Save (x3)
// Import (x2)
// Export (x2)
// Export DRC (x3)
// TODO: Change to DRACOExporter's parse( geometry, onParse )? (x2)
// Export GLB (x3)
// Export GLTF (x3)
// Export OBJ (x3)
// Export PLY (ASCII) (x3)
// Export PLY (BINARY) (x3)
// Export STL (ASCII) (x3)
// Export STL (BINARY) (x3)
// Export USDZ (x3)
```

<details><summary>Code</summary>

```typescript
function MenubarFile( editor ) {

	const strings = editor.strings;

	const saveArrayBuffer = editor.utils.saveArrayBuffer;
	const saveString = editor.utils.saveString;

	const container = new UIPanel();
	container.setClass( 'menu' );

	const title = new UIPanel();
	title.setClass( 'title' );
	title.setTextContent( strings.getKey( 'menubar/file' ) );
	container.add( title );

	const options = new UIPanel();
	options.setClass( 'options' );
	container.add( options );

	// New Project

	const newProjectSubmenuTitle = new UIRow().setTextContent( strings.getKey( 'menubar/file/new' ) ).addClass( 'option' ).addClass( 'submenu-title' );
	newProjectSubmenuTitle.onMouseOver( function () {

		const { top, right } = this.dom.getBoundingClientRect();
		const { paddingTop } = getComputedStyle( this.dom );
		newProjectSubmenu.setLeft( right + 'px' );
		newProjectSubmenu.setTop( top - parseFloat( paddingTop ) + 'px' );
		newProjectSubmenu.setDisplay( 'block' );

	} );
	newProjectSubmenuTitle.onMouseOut( function () {

		newProjectSubmenu.setDisplay( 'none' );

	} );
	options.add( newProjectSubmenuTitle );

	const newProjectSubmenu = new UIPanel().setPosition( 'fixed' ).addClass( 'options' ).setDisplay( 'none' );
	newProjectSubmenuTitle.add( newProjectSubmenu );

	// New Project / Empty

	let option = new UIRow().setTextContent( strings.getKey( 'menubar/file/new/empty' ) ).setClass( 'option' );
	option.onClick( function () {

		if ( confirm( strings.getKey( 'prompt/file/open' ) ) ) {

			editor.clear();

		}

	} );
	newProjectSubmenu.add( option );

	//

	newProjectSubmenu.add( new UIHorizontalRule() );

	// New Project / ...

	const examples = [
		{ title: 'menubar/file/new/Arkanoid', file: 'arkanoid.app.json' },
		{ title: 'menubar/file/new/Camera', file: 'camera.app.json' },
		{ title: 'menubar/file/new/Particles', file: 'particles.app.json' },
		{ title: 'menubar/file/new/Pong', file: 'pong.app.json' },
		{ title: 'menubar/file/new/Shaders', file: 'shaders.app.json' }
	];

	const loader = new THREE.FileLoader();

	for ( let i = 0; i < examples.length; i ++ ) {

		( function ( i ) {

			const example = examples[ i ];

			const option = new UIRow();
			option.setClass( 'option' );
			option.setTextContent( strings.getKey( example.title ) );
			option.onClick( function () {

				if ( confirm( strings.getKey( 'prompt/file/open' ) ) ) {

					loader.load( 'examples/' + example.file, function ( text ) {

						editor.clear();
						editor.fromJSON( JSON.parse( text ) );

					} );

				}

			} );
			newProjectSubmenu.add( option );

		} )( i );

	}

	// Open

	const openProjectForm = document.createElement( 'form' );
	openProjectForm.style.display = 'none';
	document.body.appendChild( openProjectForm );

	const openProjectInput = document.createElement( 'input' );
	openProjectInput.multiple = false;
	openProjectInput.type = 'file';
	openProjectInput.accept = '.json';
	openProjectInput.addEventListener( 'change', async function () {

		const file = openProjectInput.files[ 0 ];

		if ( file === undefined ) return;

		try {

			const json = JSON.parse( await file.text() );

			async function onEditorCleared() {

				await editor.fromJSON( json );

				editor.signals.editorCleared.remove( onEditorCleared );

			}

			editor.signals.editorCleared.add( onEditorCleared );

			editor.clear();

		} catch ( e ) {

			alert( strings.getKey( 'prompt/file/failedToOpenProject' ) );
			console.error( e );

		} finally {

			form.reset();

		}

	} );

	openProjectForm.appendChild( openProjectInput );

	option = new UIRow()
		.addClass( 'option' )
		.setTextContent( strings.getKey( 'menubar/file/open' ) )
		.onClick( function () {

			if ( confirm( strings.getKey( 'prompt/file/open' ) ) ) {

				openProjectInput.click();

			}

		} );

	options.add( option );

	// Save

	option = new UIRow()
		.addClass( 'option' )
		.setTextContent( strings.getKey( 'menubar/file/save' ) )
		.onClick( function () {

			const json = editor.toJSON();
			const blob = new Blob( [ JSON.stringify( json ) ], { type: 'application/json' } );
			editor.utils.save( blob, 'project.json' );

		} );

	options.add( option );

	//

	options.add( new UIHorizontalRule() );

	// Import

	const form = document.createElement( 'form' );
	form.style.display = 'none';
	document.body.appendChild( form );

	const fileInput = document.createElement( 'input' );
	fileInput.multiple = true;
	fileInput.type = 'file';
	fileInput.addEventListener( 'change', function () {

		editor.loader.loadFiles( fileInput.files );
		form.reset();

	} );
	form.appendChild( fileInput );

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/file/import' ) );
	option.onClick( function () {

		fileInput.click();

	} );
	options.add( option );

	// Export

	const fileExportSubmenuTitle = new UIRow().setTextContent( strings.getKey( 'menubar/file/export' ) ).addClass( 'option' ).addClass( 'submenu-title' );
	fileExportSubmenuTitle.onMouseOver( function () {

		const { top, right } = this.dom.getBoundingClientRect();
		const { paddingTop } = getComputedStyle( this.dom );
		fileExportSubmenu.setLeft( right + 'px' );
		fileExportSubmenu.setTop( top - parseFloat( paddingTop ) + 'px' );
		fileExportSubmenu.setDisplay( 'block' );

	} );
	fileExportSubmenuTitle.onMouseOut( function () {

		fileExportSubmenu.setDisplay( 'none' );

	} );
	options.add( fileExportSubmenuTitle );

	const fileExportSubmenu = new UIPanel().setPosition( 'fixed' ).addClass( 'options' ).setDisplay( 'none' );
	fileExportSubmenuTitle.add( fileExportSubmenu );

	// Export DRC

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( 'DRC' );
	option.onClick( async function () {

		const object = editor.selected;

		if ( object === null || object.isMesh === undefined ) {

			alert( strings.getKey( 'prompt/file/export/noMeshSelected' ) );
			return;

		}

		const { DRACOExporter } = await import( 'three/addons/exporters/DRACOExporter.js' );

		const exporter = new DRACOExporter();

		const options = {
			decodeSpeed: 5,
			encodeSpeed: 5,
			encoderMethod: DRACOExporter.MESH_EDGEBREAKER_ENCODING,
			quantization: [ 16, 8, 8, 8, 8 ],
			exportUvs: true,
			exportNormals: true,
			exportColor: object.geometry.hasAttribute( 'color' )
		};

		// TODO: Change to DRACOExporter's parse( geometry, onParse )?
		const result = exporter.parse( object, options );
		saveArrayBuffer( result, 'model.drc' );

	} );
	fileExportSubmenu.add( option );

	// Export GLB

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( 'GLB' );
	option.onClick( async function () {

		const scene = editor.scene;
		const animations = getAnimations( scene );

		const optimizedAnimations = [];

		for ( const animation of animations ) {

			optimizedAnimations.push( animation.clone().optimize() );

		}

		const { GLTFExporter } = await import( 'three/addons/exporters/GLTFExporter.js' );

		const exporter = new GLTFExporter();

		exporter.parse( scene, function ( result ) {

			saveArrayBuffer( result, 'scene.glb' );

		}, undefined, { binary: true, animations: optimizedAnimations } );

	} );
	fileExportSubmenu.add( option );

	// Export GLTF

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( 'GLTF' );
	option.onClick( async function () {

		const scene = editor.scene;
		const animations = getAnimations( scene );

		const optimizedAnimations = [];

		for ( const animation of animations ) {

			optimizedAnimations.push( animation.clone().optimize() );

		}

		const { GLTFExporter } = await import( 'three/addons/exporters/GLTFExporter.js' );

		const exporter = new GLTFExporter();

		exporter.parse( scene, function ( result ) {

			saveString( JSON.stringify( result, null, 2 ), 'scene.gltf' );

		}, undefined, { animations: optimizedAnimations } );


	} );
	fileExportSubmenu.add( option );

	// Export OBJ

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( 'OBJ' );
	option.onClick( async function () {

		const object = editor.selected;

		if ( object === null ) {

			alert( strings.getKey( 'prompt/file/export/noObjectSelected' ) );
			return;

		}

		const { OBJExporter } = await import( 'three/addons/exporters/OBJExporter.js' );

		const exporter = new OBJExporter();

		saveString( exporter.parse( object ), 'model.obj' );

	} );
	fileExportSubmenu.add( option );

	// Export PLY (ASCII)

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( 'PLY' );
	option.onClick( async function () {

		const { PLYExporter } = await import( 'three/addons/exporters/PLYExporter.js' );

		const exporter = new PLYExporter();

		exporter.parse( editor.scene, function ( result ) {

			saveArrayBuffer( result, 'model.ply' );

		} );

	} );
	fileExportSubmenu.add( option );

	// Export PLY (BINARY)

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( 'PLY (BINARY)' );
	option.onClick( async function () {

		const { PLYExporter } = await import( 'three/addons/exporters/PLYExporter.js' );

		const exporter = new PLYExporter();

		exporter.parse( editor.scene, function ( result ) {

			saveArrayBuffer( result, 'model-binary.ply' );

		}, { binary: true } );

	} );
	fileExportSubmenu.add( option );

	// Export STL (ASCII)

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( 'STL' );
	option.onClick( async function () {

		const { STLExporter } = await import( 'three/addons/exporters/STLExporter.js' );

		const exporter = new STLExporter();

		saveString( exporter.parse( editor.scene ), 'model.stl' );

	} );
	fileExportSubmenu.add( option );

	// Export STL (BINARY)

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( 'STL (BINARY)' );
	option.onClick( async function () {

		const { STLExporter } = await import( 'three/addons/exporters/STLExporter.js' );

		const exporter = new STLExporter();

		saveArrayBuffer( exporter.parse( editor.scene, { binary: true } ), 'model-binary.stl' );

	} );
	fileExportSubmenu.add( option );

	// Export USDZ

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( 'USDZ' );
	option.onClick( async function () {

		const { USDZExporter } = await import( 'three/addons/exporters/USDZExporter.js' );

		const exporter = new USDZExporter();

		saveArrayBuffer( await exporter.parseAsync( editor.scene ), 'model.usdz' );

	} );
	fileExportSubmenu.add( option );

	//

	function getAnimations( scene ) {

		const animations = [];

		scene.traverse( function ( object ) {

			animations.push( ... object.animations );

		} );

		return animations;

	}

	return container;

}
```
</details>

### `onEditorCleared(): Promise<void>`

**Returns:** `Promise<void>`

**Calls:**

- `editor.fromJSON`
- `editor.signals.editorCleared.remove`

<details><summary>Code</summary>

```typescript
async function onEditorCleared() {

				await editor.fromJSON( json );

				editor.signals.editorCleared.remove( onEditorCleared );

			}
```
</details>

### `getAnimations(scene: any): any[]`

**Parameters:**

- **`scene`** `any`

**Returns:** `any[]`

**Calls:**

- `scene.traverse`
- `animations.push`

<details><summary>Code</summary>

```typescript
function getAnimations( scene ) {

		const animations = [];

		scene.traverse( function ( object ) {

			animations.push( ... object.animations );

		} );

		return animations;

	}
```
</details>


---