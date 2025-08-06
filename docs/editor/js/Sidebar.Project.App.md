[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Project.App.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 16 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Project.App.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `zipSync` | `three/addons/libs/fflate.module.js` |
| `strToU8` | `three/addons/libs/fflate.module.js` |
| `UIButton` | `./libs/ui.js` |
| `UICheckbox` | `./libs/ui.js` |
| `UIPanel` | `./libs/ui.js` |
| `UIInput` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `config` | `any` | let/var | `editor.config` | ✗ |
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `save` | `any` | let/var | `editor.utils.save` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `headerRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `titleRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `editableRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `isPlaying` | `boolean` | let/var | `false` | ✗ |
| `playButton` | `UIButton` | let/var | `new UIButton( strings.getKey( 'sidebar/project/app/play' ) )` | ✗ |
| `publishButton` | `UIButton` | let/var | `new UIButton( strings.getKey( 'sidebar/project/app/publish' ) )` | ✗ |
| `toZip` | `{ 'app.json': any; }` | let/var | `{}` | ✗ |
| `blob` | `Blob` | let/var | `new Blob( [ zipped.buffer ], { type: 'application/zip' } )` | ✗ |
| `manager` | `any` | let/var | `new THREE.LoadingManager( function () { const zipped = zipSync( toZip, { leve...` | ✗ |
| `loader` | `any` | let/var | `new THREE.FileLoader( manager )` | ✗ |
| `editButton` | `string` | let/var | `''` | ✗ |


---

## Functions

### `SidebarProjectApp(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.setId`
- `headerRow.add`
- `strings.getKey( 'sidebar/project/app' ).toUpperCase`
- `container.add`
- `new UIInput( config.getKey( 'project/title' ) ).setLeft( '100px' ).setWidth( '150px' ).onChange`
- `config.setKey`
- `this.getValue`
- `titleRow.add`
- `new UIText( strings.getKey( 'sidebar/project/app/title' ) ).setClass`
- `strings.getKey`
- `new UICheckbox( config.getKey( 'project/editable' ) ).setLeft( '100px' ).onChange`
- `editableRow.add`
- `new UIText( strings.getKey( 'sidebar/project/app/editable' ) ).setClass`
- `playButton.setWidth`
- `playButton.setMarginLeft`
- `playButton.setMarginBottom`
- `playButton.onClick`
- `playButton.setTextContent`
- `signals.startPlayer.dispatch`
- `signals.stopPlayer.dispatch`
- `publishButton.setWidth`
- `publishButton.setMarginLeft`
- `publishButton.setMarginBottom`
- `publishButton.onClick`
- `editor.toJSON`
- `JSON.stringify`
- `output.replace`
- `strToU8 (from three/addons/libs/fflate.module.js)`
- `config.getKey`
- `zipSync (from three/addons/libs/fflate.module.js)`
- `save`
- `loader.load`
- `content.replace`
- `[
					'			let button = document.createElement( \'a\' );',
					'			button.href = \'https://threejs.org/editor/#file=\' + location.href.split( \'/\' ).slice( 0, - 1 ).join( \'/\' ) + \'/app.json\';',
					'			button.style.cssText = \'position: absolute; bottom: 20px; right: 20px; padding: 10px 16px; color: #fff; border: 1px solid #fff; border-radius: 20px; text-decoration: none;\';',
					'			button.target = \'_blank\';',
					'			button.textContent = \'EDIT\';',
					'			document.body.appendChild( button );',
				].join`
- `signals.editorCleared.add`
- `title.setValue`

**Internal Comments:**
```
// Title (x2)
// Editable (x2)
// Play/Stop (x2)
// Publish (x2)
// (x4)
// Signals (x5)
```

<details><summary>Code</summary>

```typescript
function SidebarProjectApp( editor ) {

	const config = editor.config;
	const signals = editor.signals;
	const strings = editor.strings;

	const save = editor.utils.save;

	const container = new UIPanel();
	container.setId( 'app' );

	const headerRow = new UIRow();
	headerRow.add( new UIText( strings.getKey( 'sidebar/project/app' ).toUpperCase() ) );
	container.add( headerRow );

	// Title

	const titleRow = new UIRow();
	const title = new UIInput( config.getKey( 'project/title' ) ).setLeft( '100px' ).setWidth( '150px' ).onChange( function () {

		config.setKey( 'project/title', this.getValue() );

	} );

	titleRow.add( new UIText( strings.getKey( 'sidebar/project/app/title' ) ).setClass( 'Label' ) );
	titleRow.add( title );

	container.add( titleRow );

	// Editable

	const editableRow = new UIRow();
	const editable = new UICheckbox( config.getKey( 'project/editable' ) ).setLeft( '100px' ).onChange( function () {

		config.setKey( 'project/editable', this.getValue() );

	} );

	editableRow.add( new UIText( strings.getKey( 'sidebar/project/app/editable' ) ).setClass( 'Label' ) );
	editableRow.add( editable );

	container.add( editableRow );

	// Play/Stop

	let isPlaying = false;

	const playButton = new UIButton( strings.getKey( 'sidebar/project/app/play' ) );
	playButton.setWidth( '170px' );
	playButton.setMarginLeft( '120px' );
	playButton.setMarginBottom( '10px' );
	playButton.onClick( function () {

		if ( isPlaying === false ) {

			isPlaying = true;
			playButton.setTextContent( strings.getKey( 'sidebar/project/app/stop' ) );
			signals.startPlayer.dispatch();

		} else {

			isPlaying = false;
			playButton.setTextContent( strings.getKey( 'sidebar/project/app/play' ) );
			signals.stopPlayer.dispatch();

		}

	} );

	container.add( playButton );

	// Publish

	const publishButton = new UIButton( strings.getKey( 'sidebar/project/app/publish' ) );
	publishButton.setWidth( '170px' );
	publishButton.setMarginLeft( '120px' );
	publishButton.setMarginBottom( '10px' );
	publishButton.onClick( function () {

		const toZip = {};

		//

		let output = editor.toJSON();
		output.metadata.type = 'App';
		delete output.history;

		output = JSON.stringify( output, null, '\t' );
		output = output.replace( /[\n\t]+([\d\.e\-\[\]]+)/g, '$1' );

		toZip[ 'app.json' ] = strToU8( output );

		//

		const title = config.getKey( 'project/title' );

		const manager = new THREE.LoadingManager( function () {

			const zipped = zipSync( toZip, { level: 9 } );

			const blob = new Blob( [ zipped.buffer ], { type: 'application/zip' } );

			save( blob, ( title !== '' ? title : 'untitled' ) + '.zip' );

		} );

		const loader = new THREE.FileLoader( manager );
		loader.load( 'js/libs/app/index.html', function ( content ) {

			content = content.replace( '<!-- title -->', title );

			let editButton = '';

			if ( config.getKey( 'project/editable' ) ) {

				editButton = [
					'			let button = document.createElement( \'a\' );',
					'			button.href = \'https://threejs.org/editor/#file=\' + location.href.split( \'/\' ).slice( 0, - 1 ).join( \'/\' ) + \'/app.json\';',
					'			button.style.cssText = \'position: absolute; bottom: 20px; right: 20px; padding: 10px 16px; color: #fff; border: 1px solid #fff; border-radius: 20px; text-decoration: none;\';',
					'			button.target = \'_blank\';',
					'			button.textContent = \'EDIT\';',
					'			document.body.appendChild( button );',
				].join( '\n' );

			}

			content = content.replace( '\t\t\t/* edit button */', editButton );

			toZip[ 'index.html' ] = strToU8( content );

		} );
		loader.load( 'js/libs/app.js', function ( content ) {

			toZip[ 'js/app.js' ] = strToU8( content );

		} );
		loader.load( '../build/three.core.js', function ( content ) {

			toZip[ 'js/three.core.js' ] = strToU8( content );

		} );
		loader.load( '../build/three.module.js', function ( content ) {

			toZip[ 'js/three.module.js' ] = strToU8( content );

		} );

	} );
	container.add( publishButton );

	// Signals

	signals.editorCleared.add( function () {

		title.setValue( '' );
		config.setKey( 'project/title', '' );

	} );

	return container;

}
```
</details>


---