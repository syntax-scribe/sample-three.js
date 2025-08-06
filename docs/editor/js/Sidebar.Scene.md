[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Scene.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 15 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 25 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Scene.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIPanel` | `./libs/ui.js` |
| `UIBreak` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIColor` | `./libs/ui.js` |
| `UISelect` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `UINumber` | `./libs/ui.js` |
| `UIOutliner` | `./libs/ui.three.js` |
| `UITexture` | `./libs/ui.three.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `nodeStates` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `html` | `string` | let/var | ``<span class="type ${ getObjectType( object ) }"></span> ${ escapeHTML( objec...` | ✗ |
| `geometry` | `any` | let/var | `object.geometry` | ✗ |
| `material` | `any` | let/var | `object.material` | ✗ |
| `ignoreObjectSelectedSignal` | `boolean` | let/var | `false` | ✗ |
| `outliner` | `UIOutliner` | let/var | `new UIOutliner( editor )` | ✗ |
| `backgroundRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `backgroundColorSpaceRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `backgroundEquirectRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `environmentRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `fogTypeRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `fogPropertiesRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `camera` | `any` | let/var | `editor.camera` | ✗ |
| `scene` | `any` | let/var | `editor.scene` | ✗ |
| `options` | `any[]` | let/var | `[]` | ✗ |
| `object` | `any` | let/var | `objects[ i ]` | ✗ |
| `options` | `any[]` | let/var | `outliner.options` | ✗ |
| `option` | `any` | let/var | `options[ i ]` | ✗ |
| `openerHTML` | `any` | let/var | `openerElement ? openerElement.outerHTML : ''` | ✗ |
| `needsRefresh` | `boolean` | let/var | `false` | ✗ |
| `parent` | `any` | let/var | `object.parent` | ✗ |


---

## Functions

### `SidebarScene(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.setBorderTop`
- `container.setPaddingTop`
- `document.createElement`
- `buildHTML`
- `nodeStates.has`
- `nodeStates.get`
- `opener.classList.add`
- `opener.addEventListener`
- `nodeStates.set`
- `refreshUI`
- `option.insertBefore`
- `Array.isArray`
- `array.push`
- `array.join`
- `html
			.replace( /&/g, '&amp;' )
			.replace( /"/g, '&quot;' )
			.replace( /'/g, '&#39;' )
			.replace( /</g, '&lt;' )
			.replace`
- `getObjectType`
- `escapeHTML`
- `getMaterialName`
- `getScript`
- `outliner.setId`
- `outliner.onChange`
- `editor.selectById`
- `parseInt`
- `outliner.getValue`
- `outliner.onDblClick`
- `editor.focusById`
- `container.add`
- `new UISelect().setOptions( {

		'None': '',
		'Color': 'Color',
		'Texture': 'Texture',
		'Equirectangular': 'Equirect'

	} ).setWidth`
- `backgroundType.onChange`
- `onBackgroundChanged`
- `refreshBackgroundUI`
- `backgroundRow.add`
- `new UIText( strings.getKey( 'sidebar/scene/background' ) ).setClass`
- `strings.getKey`
- `new UIColor().setValue( '#000000' ).setMarginLeft( '8px' ).onInput`
- `new UITexture( editor ).setMarginLeft( '8px' ).onChange`
- `backgroundTexture.setDisplay`
- `backgroundEquirectangularTexture.setDisplay`
- `backgroundColorSpaceRow.setDisplay`
- `backgroundColorSpaceRow.setMarginLeft`
- `new UISelect().setOptions( {

		[ THREE.NoColorSpace ]: 'No Color Space',
		[ THREE.LinearSRGBColorSpace ]: 'srgb-linear',
		[ THREE.SRGBColorSpace ]: 'srgb',

	} ).setWidth`
- `backgroundColorSpace.setValue`
- `backgroundColorSpace.onChange`
- `backgroundColorSpaceRow.add`
- `backgroundEquirectRow.setDisplay`
- `backgroundEquirectRow.setMarginLeft`
- `new UINumber( 0 ).setWidth( '40px' ).setRange( 0, 1 ).onChange`
- `backgroundEquirectRow.add`
- `new UINumber( 1 ).setWidth( '40px' ).setRange( 0, Infinity ).onChange`
- `new UINumber( 0 ).setWidth( '40px' ).setRange( - 180, 180 ).setStep( 10 ).setNudge( 0.1 ).setUnit( '°' ).onChange`
- `signals.sceneBackgroundChanged.dispatch`
- `backgroundType.getValue`
- `backgroundColor.getHexValue`
- `backgroundTexture.getValue`
- `backgroundEquirectangularTexture.getValue`
- `backgroundColorSpace.getValue`
- `backgroundBlurriness.getValue`
- `backgroundIntensity.getValue`
- `backgroundRotation.getValue`
- `backgroundType.setWidth`
- `backgroundColor.setDisplay`
- `new UISelect().setOptions( {

		'None': '',
		'Background': 'Background',
		'Equirectangular': 'Equirect',
		'Room': 'Room'

	} ).setWidth`
- `environmentType.setValue`
- `environmentType.onChange`
- `onEnvironmentChanged`
- `refreshEnvironmentUI`
- `environmentRow.add`
- `new UIText( strings.getKey( 'sidebar/scene/environment' ) ).setClass`
- `environmentEquirectangularTexture.setDisplay`
- `signals.sceneEnvironmentChanged.dispatch`
- `environmentType.getValue`
- `environmentEquirectangularTexture.getValue`
- `environmentType.setWidth`
- `signals.sceneFogChanged.dispatch`
- `fogType.getValue`
- `fogColor.getHexValue`
- `fogNear.getValue`
- `fogFar.getValue`
- `fogDensity.getValue`
- `signals.sceneFogSettingsChanged.dispatch`
- `new UISelect().setOptions( {

		'None': '',
		'Fog': 'Linear',
		'FogExp2': 'Exponential'

	} ).setWidth`
- `fogType.onChange`
- `onFogChanged`
- `refreshFogUI`
- `fogTypeRow.add`
- `new UIText( strings.getKey( 'sidebar/scene/fog' ) ).setClass`
- `fogPropertiesRow.setDisplay`
- `fogPropertiesRow.setMarginLeft`
- `new UIColor().setValue`
- `fogColor.onInput`
- `fogPropertiesRow.add`
- `new UINumber( 0.1 ).setWidth( '40px' ).setRange( 0, Infinity ).onChange`
- `new UINumber( 50 ).setWidth( '40px' ).setRange( 0, Infinity ).onChange`
- `new UINumber( 0.05 ).setWidth( '40px' ).setRange( 0, 0.1 ).setStep( 0.001 ).setPrecision( 3 ).onChange`
- `options.push`
- `buildOption`
- `complex_call_9519`
- `addObjects`
- `outliner.setOptions`
- `outliner.setValue`
- `backgroundType.setValue`
- `backgroundColor.setHexValue`
- `scene.background.getHex`
- `backgroundEquirectangularTexture.setValue`
- `backgroundBlurriness.setValue`
- `backgroundIntensity.setValue`
- `backgroundTexture.setValue`
- `environmentEquirectangularTexture.setValue`
- `fogColor.setHexValue`
- `scene.fog.color.getHex`
- `fogType.setValue`
- `fogNear.setValue`
- `fogFar.setValue`
- `fogDensity.setValue`
- `fogNear.setDisplay`
- `fogFar.setDisplay`
- `fogDensity.setDisplay`
- `signals.editorCleared.add`
- `signals.sceneGraphChanged.add`
- `signals.refreshSidebarEnvironment.add`
- `signals.objectChanged.add`
- `option.querySelector`
- `signals.scriptAdded.add`
- `signals.objectChanged.dispatch`
- `signals.scriptRemoved.add`
- `signals.objectSelected.add`
- `signals.sceneBackgroundChanged.add`

**Internal Comments:**
```
// outliner (x2)
// opener
// background (x2)
// environment (x2)
// fog
// fog color (x2)
// fog near (x2)
// fog far (x2)
// fog density (x2)
//
// events (x5)
```

<details><summary>Code</summary>

```typescript
function SidebarScene( editor ) {

	const signals = editor.signals;
	const strings = editor.strings;

	const container = new UIPanel();
	container.setBorderTop( '0' );
	container.setPaddingTop( '20px' );

	// outliner

	const nodeStates = new WeakMap();

	function buildOption( object, draggable ) {

		const option = document.createElement( 'div' );
		option.draggable = draggable;
		option.innerHTML = buildHTML( object );
		option.value = object.id;

		// opener

		if ( nodeStates.has( object ) ) {

			const state = nodeStates.get( object );

			const opener = document.createElement( 'span' );
			opener.classList.add( 'opener' );

			if ( object.children.length > 0 ) {

				opener.classList.add( state ? 'open' : 'closed' );

			}

			opener.addEventListener( 'click', function () {

				nodeStates.set( object, nodeStates.get( object ) === false ); // toggle
				refreshUI();

			} );

			option.insertBefore( opener, option.firstChild );

		}

		return option;

	}

	function getMaterialName( material ) {

		if ( Array.isArray( material ) ) {

			const array = [];

			for ( let i = 0; i < material.length; i ++ ) {

				array.push( material[ i ].name );

			}

			return array.join( ',' );

		}

		return material.name;

	}

	function escapeHTML( html ) {

		return html
			.replace( /&/g, '&amp;' )
			.replace( /"/g, '&quot;' )
			.replace( /'/g, '&#39;' )
			.replace( /</g, '&lt;' )
			.replace( />/g, '&gt;' );

	}

	function getObjectType( object ) {

		if ( object.isScene ) return 'Scene';
		if ( object.isCamera ) return 'Camera';
		if ( object.isLight ) return 'Light';
		if ( object.isMesh ) return 'Mesh';
		if ( object.isLine ) return 'Line';
		if ( object.isPoints ) return 'Points';

		return 'Object3D';

	}

	function buildHTML( object ) {

		let html = `<span class="type ${ getObjectType( object ) }"></span> ${ escapeHTML( object.name ) }`;

		if ( object.isMesh ) {

			const geometry = object.geometry;
			const material = object.material;

			html += ` <span class="type Geometry"></span> ${ escapeHTML( geometry.name ) }`;
			html += ` <span class="type Material"></span> ${ escapeHTML( getMaterialName( material ) ) }`;

		}

		html += getScript( object.uuid );

		return html;

	}

	function getScript( uuid ) {

		if ( editor.scripts[ uuid ] === undefined ) return '';

		if ( editor.scripts[ uuid ].length === 0 ) return '';

		return ' <span class="type Script"></span>';

	}

	let ignoreObjectSelectedSignal = false;

	const outliner = new UIOutliner( editor );
	outliner.setId( 'outliner' );
	outliner.onChange( function () {

		ignoreObjectSelectedSignal = true;

		editor.selectById( parseInt( outliner.getValue() ) );

		ignoreObjectSelectedSignal = false;

	} );
	outliner.onDblClick( function () {

		editor.focusById( parseInt( outliner.getValue() ) );

	} );
	container.add( outliner );
	container.add( new UIBreak() );

	// background

	const backgroundRow = new UIRow();

	const backgroundType = new UISelect().setOptions( {

		'None': '',
		'Color': 'Color',
		'Texture': 'Texture',
		'Equirectangular': 'Equirect'

	} ).setWidth( '150px' );
	backgroundType.onChange( function () {

		onBackgroundChanged();
		refreshBackgroundUI();

	} );

	backgroundRow.add( new UIText( strings.getKey( 'sidebar/scene/background' ) ).setClass( 'Label' ) );
	backgroundRow.add( backgroundType );

	const backgroundColor = new UIColor().setValue( '#000000' ).setMarginLeft( '8px' ).onInput( onBackgroundChanged );
	backgroundRow.add( backgroundColor );

	const backgroundTexture = new UITexture( editor ).setMarginLeft( '8px' ).onChange( onBackgroundChanged );
	backgroundTexture.setDisplay( 'none' );
	backgroundRow.add( backgroundTexture );

	const backgroundEquirectangularTexture = new UITexture( editor ).setMarginLeft( '8px' ).onChange( onBackgroundChanged );
	backgroundEquirectangularTexture.setDisplay( 'none' );
	backgroundRow.add( backgroundEquirectangularTexture );

	const backgroundColorSpaceRow = new UIRow();
	backgroundColorSpaceRow.setDisplay( 'none' );
	backgroundColorSpaceRow.setMarginLeft( '120px' );

	const backgroundColorSpace = new UISelect().setOptions( {

		[ THREE.NoColorSpace ]: 'No Color Space',
		[ THREE.LinearSRGBColorSpace ]: 'srgb-linear',
		[ THREE.SRGBColorSpace ]: 'srgb',

	} ).setWidth( '150px' );
	backgroundColorSpace.setValue( THREE.NoColorSpace );
	backgroundColorSpace.onChange( onBackgroundChanged );
	backgroundColorSpaceRow.add( backgroundColorSpace );

	container.add( backgroundRow );
	container.add( backgroundColorSpaceRow );

	const backgroundEquirectRow = new UIRow();
	backgroundEquirectRow.setDisplay( 'none' );
	backgroundEquirectRow.setMarginLeft( '120px' );

	const backgroundBlurriness = new UINumber( 0 ).setWidth( '40px' ).setRange( 0, 1 ).onChange( onBackgroundChanged );
	backgroundEquirectRow.add( backgroundBlurriness );

	const backgroundIntensity = new UINumber( 1 ).setWidth( '40px' ).setRange( 0, Infinity ).onChange( onBackgroundChanged );
	backgroundEquirectRow.add( backgroundIntensity );

	const backgroundRotation = new UINumber( 0 ).setWidth( '40px' ).setRange( - 180, 180 ).setStep( 10 ).setNudge( 0.1 ).setUnit( '°' ).onChange( onBackgroundChanged );
	backgroundEquirectRow.add( backgroundRotation );

	container.add( backgroundEquirectRow );

	function onBackgroundChanged() {

		signals.sceneBackgroundChanged.dispatch(
			backgroundType.getValue(),
			backgroundColor.getHexValue(),
			backgroundTexture.getValue(),
			backgroundEquirectangularTexture.getValue(),
			backgroundColorSpace.getValue(),
			backgroundBlurriness.getValue(),
			backgroundIntensity.getValue(),
			backgroundRotation.getValue()
		);

	}

	function refreshBackgroundUI() {

		const type = backgroundType.getValue();

		backgroundType.setWidth( type === 'None' ? '150px' : '110px' );
		backgroundColor.setDisplay( type === 'Color' ? '' : 'none' );
		backgroundTexture.setDisplay( type === 'Texture' ? '' : 'none' );
		backgroundEquirectangularTexture.setDisplay( type === 'Equirectangular' ? '' : 'none' );
		backgroundEquirectRow.setDisplay( type === 'Equirectangular' ? '' : 'none' );

		if ( type === 'Texture' || type === 'Equirectangular' ) {

			backgroundColorSpaceRow.setDisplay( '' );

		} else {

			backgroundColorSpaceRow.setDisplay( 'none' );

		}

	}

	// environment

	const environmentRow = new UIRow();

	const environmentType = new UISelect().setOptions( {

		'None': '',
		'Background': 'Background',
		'Equirectangular': 'Equirect',
		'Room': 'Room'

	} ).setWidth( '150px' );
	environmentType.setValue( 'None' );
	environmentType.onChange( function () {

		onEnvironmentChanged();
		refreshEnvironmentUI();

	} );

	environmentRow.add( new UIText( strings.getKey( 'sidebar/scene/environment' ) ).setClass( 'Label' ) );
	environmentRow.add( environmentType );

	const environmentEquirectangularTexture = new UITexture( editor ).setMarginLeft( '8px' ).onChange( onEnvironmentChanged );
	environmentEquirectangularTexture.setDisplay( 'none' );
	environmentRow.add( environmentEquirectangularTexture );

	container.add( environmentRow );

	function onEnvironmentChanged() {

		signals.sceneEnvironmentChanged.dispatch(
			environmentType.getValue(),
			environmentEquirectangularTexture.getValue()
		);

	}

	function refreshEnvironmentUI() {

		const type = environmentType.getValue();

		environmentType.setWidth( type !== 'Equirectangular' ? '150px' : '110px' );
		environmentEquirectangularTexture.setDisplay( type === 'Equirectangular' ? '' : 'none' );

	}

	// fog

	function onFogChanged() {

		signals.sceneFogChanged.dispatch(
			fogType.getValue(),
			fogColor.getHexValue(),
			fogNear.getValue(),
			fogFar.getValue(),
			fogDensity.getValue()
		);

	}

	function onFogSettingsChanged() {

		signals.sceneFogSettingsChanged.dispatch(
			fogType.getValue(),
			fogColor.getHexValue(),
			fogNear.getValue(),
			fogFar.getValue(),
			fogDensity.getValue()
		);

	}

	const fogTypeRow = new UIRow();
	const fogType = new UISelect().setOptions( {

		'None': '',
		'Fog': 'Linear',
		'FogExp2': 'Exponential'

	} ).setWidth( '150px' );
	fogType.onChange( function () {

		onFogChanged();
		refreshFogUI();

	} );

	fogTypeRow.add( new UIText( strings.getKey( 'sidebar/scene/fog' ) ).setClass( 'Label' ) );
	fogTypeRow.add( fogType );

	container.add( fogTypeRow );

	// fog color

	const fogPropertiesRow = new UIRow();
	fogPropertiesRow.setDisplay( 'none' );
	fogPropertiesRow.setMarginLeft( '120px' );
	container.add( fogPropertiesRow );

	const fogColor = new UIColor().setValue( '#aaaaaa' );
	fogColor.onInput( onFogSettingsChanged );
	fogPropertiesRow.add( fogColor );

	// fog near

	const fogNear = new UINumber( 0.1 ).setWidth( '40px' ).setRange( 0, Infinity ).onChange( onFogSettingsChanged );
	fogPropertiesRow.add( fogNear );

	// fog far

	const fogFar = new UINumber( 50 ).setWidth( '40px' ).setRange( 0, Infinity ).onChange( onFogSettingsChanged );
	fogPropertiesRow.add( fogFar );

	// fog density

	const fogDensity = new UINumber( 0.05 ).setWidth( '40px' ).setRange( 0, 0.1 ).setStep( 0.001 ).setPrecision( 3 ).onChange( onFogSettingsChanged );
	fogPropertiesRow.add( fogDensity );

	//

	function refreshUI() {

		const camera = editor.camera;
		const scene = editor.scene;

		const options = [];

		options.push( buildOption( camera, false ) );
		options.push( buildOption( scene, false ) );

		( function addObjects( objects, pad ) {

			for ( let i = 0, l = objects.length; i < l; i ++ ) {

				const object = objects[ i ];

				if ( nodeStates.has( object ) === false ) {

					nodeStates.set( object, false );

				}

				const option = buildOption( object, true );
				option.style.paddingLeft = ( pad * 18 ) + 'px';
				options.push( option );

				if ( nodeStates.get( object ) === true ) {

					addObjects( object.children, pad + 1 );

				}

			}

		} )( scene.children, 0 );

		outliner.setOptions( options );

		if ( editor.selected !== null ) {

			outliner.setValue( editor.selected.id );

		}

		if ( scene.background ) {

			if ( scene.background.isColor ) {

				backgroundType.setValue( 'Color' );
				backgroundColor.setHexValue( scene.background.getHex() );

			} else if ( scene.background.isTexture ) {

				if ( scene.background.mapping === THREE.EquirectangularReflectionMapping ) {

					backgroundType.setValue( 'Equirectangular' );
					backgroundEquirectangularTexture.setValue( scene.background );
					backgroundBlurriness.setValue( scene.backgroundBlurriness );
					backgroundIntensity.setValue( scene.backgroundIntensity );

				} else {

					backgroundType.setValue( 'Texture' );
					backgroundTexture.setValue( scene.background );

				}

				backgroundColorSpace.setValue( scene.background.colorSpace );

			}

		} else {

			backgroundType.setValue( 'None' );
			backgroundTexture.setValue( null );
			backgroundEquirectangularTexture.setValue( null );
			backgroundColorSpace.setValue( THREE.NoColorSpace );

		}

		if ( scene.environment ) {

			if ( scene.background && scene.background.isTexture && scene.background.uuid === scene.environment.uuid ) {

				environmentType.setValue( 'Background' );

			} else if ( scene.environment.mapping === THREE.EquirectangularReflectionMapping ) {

				environmentType.setValue( 'Equirectangular' );
				environmentEquirectangularTexture.setValue( scene.environment );

			} else if ( scene.environment.isRenderTargetTexture === true ) {

				environmentType.setValue( 'Room' );

			}

		} else {

			environmentType.setValue( 'None' );
			environmentEquirectangularTexture.setValue( null );

		}

		if ( scene.fog ) {

			fogColor.setHexValue( scene.fog.color.getHex() );

			if ( scene.fog.isFog ) {

				fogType.setValue( 'Fog' );
				fogNear.setValue( scene.fog.near );
				fogFar.setValue( scene.fog.far );

			} else if ( scene.fog.isFogExp2 ) {

				fogType.setValue( 'FogExp2' );
				fogDensity.setValue( scene.fog.density );

			}

		} else {

			fogType.setValue( 'None' );

		}

		refreshBackgroundUI();
		refreshEnvironmentUI();
		refreshFogUI();

	}

	function refreshFogUI() {

		const type = fogType.getValue();

		fogPropertiesRow.setDisplay( type === 'None' ? 'none' : '' );
		fogNear.setDisplay( type === 'Fog' ? '' : 'none' );
		fogFar.setDisplay( type === 'Fog' ? '' : 'none' );
		fogDensity.setDisplay( type === 'FogExp2' ? '' : 'none' );

	}

	refreshUI();

	// events

	signals.editorCleared.add( refreshUI );

	signals.sceneGraphChanged.add( refreshUI );

	signals.refreshSidebarEnvironment.add( refreshUI );

	signals.objectChanged.add( function ( object ) {

		const options = outliner.options;

		for ( let i = 0; i < options.length; i ++ ) {

			const option = options[ i ];

			if ( option.value === object.id ) {

				const openerElement = option.querySelector( ':scope > .opener' );

				const openerHTML = openerElement ? openerElement.outerHTML : '';

				option.innerHTML = openerHTML + buildHTML( object );

				return;

			}

		}

	} );

	signals.scriptAdded.add( function () {

		if ( editor.selected !== null ) signals.objectChanged.dispatch( editor.selected );

	} );

	signals.scriptRemoved.add( function () {

		if ( editor.selected !== null ) signals.objectChanged.dispatch( editor.selected );

	} );


	signals.objectSelected.add( function ( object ) {

		if ( ignoreObjectSelectedSignal === true ) return;

		if ( object !== null && object.parent !== null ) {

			let needsRefresh = false;
			let parent = object.parent;

			while ( parent !== editor.scene ) {

				if ( nodeStates.get( parent ) !== true ) {

					nodeStates.set( parent, true );
					needsRefresh = true;

				}

				parent = parent.parent;

			}

			if ( needsRefresh ) refreshUI();

			outliner.setValue( object.id );

		} else {

			outliner.setValue( null );

		}

	} );

	signals.sceneBackgroundChanged.add( function () {

		if ( environmentType.getValue() === 'Background' ) {

			onEnvironmentChanged();
			refreshEnvironmentUI();

		}

	} );

	return container;

}
```
</details>

### `buildOption(object: any, draggable: any): HTMLDivElement`

**Parameters:**

- **`object`** `any`
- **`draggable`** `any`

**Returns:** `HTMLDivElement`

**Calls:**

- `document.createElement`
- `buildHTML`
- `nodeStates.has`
- `nodeStates.get`
- `opener.classList.add`
- `opener.addEventListener`
- `nodeStates.set`
- `refreshUI`
- `option.insertBefore`

**Internal Comments:**
```
// opener
```

<details><summary>Code</summary>

```typescript
function buildOption( object, draggable ) {

		const option = document.createElement( 'div' );
		option.draggable = draggable;
		option.innerHTML = buildHTML( object );
		option.value = object.id;

		// opener

		if ( nodeStates.has( object ) ) {

			const state = nodeStates.get( object );

			const opener = document.createElement( 'span' );
			opener.classList.add( 'opener' );

			if ( object.children.length > 0 ) {

				opener.classList.add( state ? 'open' : 'closed' );

			}

			opener.addEventListener( 'click', function () {

				nodeStates.set( object, nodeStates.get( object ) === false ); // toggle
				refreshUI();

			} );

			option.insertBefore( opener, option.firstChild );

		}

		return option;

	}
```
</details>

### `getMaterialName(material: any): any`

**Parameters:**

- **`material`** `any`

**Returns:** `any`

**Calls:**

- `Array.isArray`
- `array.push`
- `array.join`

<details><summary>Code</summary>

```typescript
function getMaterialName( material ) {

		if ( Array.isArray( material ) ) {

			const array = [];

			for ( let i = 0; i < material.length; i ++ ) {

				array.push( material[ i ].name );

			}

			return array.join( ',' );

		}

		return material.name;

	}
```
</details>

### `escapeHTML(html: any): any`

**Parameters:**

- **`html`** `any`

**Returns:** `any`

**Calls:**

- `html
			.replace( /&/g, '&amp;' )
			.replace( /"/g, '&quot;' )
			.replace( /'/g, '&#39;' )
			.replace( /</g, '&lt;' )
			.replace`

<details><summary>Code</summary>

```typescript
function escapeHTML( html ) {

		return html
			.replace( /&/g, '&amp;' )
			.replace( /"/g, '&quot;' )
			.replace( /'/g, '&#39;' )
			.replace( /</g, '&lt;' )
			.replace( />/g, '&gt;' );

	}
```
</details>

### `getObjectType(object: any): "Line" | "Light" | "Camera" | "Points" | "Mesh" | "Scene" | "Object3D"`

**Parameters:**

- **`object`** `any`

**Returns:** `"Line" | "Light" | "Camera" | "Points" | "Mesh" | "Scene" | "Object3D"`

<details><summary>Code</summary>

```typescript
function getObjectType( object ) {

		if ( object.isScene ) return 'Scene';
		if ( object.isCamera ) return 'Camera';
		if ( object.isLight ) return 'Light';
		if ( object.isMesh ) return 'Mesh';
		if ( object.isLine ) return 'Line';
		if ( object.isPoints ) return 'Points';

		return 'Object3D';

	}
```
</details>

### `buildHTML(object: any): string`

**Parameters:**

- **`object`** `any`

**Returns:** `string`

**Calls:**

- `getObjectType`
- `escapeHTML`
- `getMaterialName`
- `getScript`

<details><summary>Code</summary>

```typescript
function buildHTML( object ) {

		let html = `<span class="type ${ getObjectType( object ) }"></span> ${ escapeHTML( object.name ) }`;

		if ( object.isMesh ) {

			const geometry = object.geometry;
			const material = object.material;

			html += ` <span class="type Geometry"></span> ${ escapeHTML( geometry.name ) }`;
			html += ` <span class="type Material"></span> ${ escapeHTML( getMaterialName( material ) ) }`;

		}

		html += getScript( object.uuid );

		return html;

	}
```
</details>

### `getScript(uuid: any): "" | " <span class=\"type Script\"></span>"`

**Parameters:**

- **`uuid`** `any`

**Returns:** `"" | " <span class=\"type Script\"></span>"`

<details><summary>Code</summary>

```typescript
function getScript( uuid ) {

		if ( editor.scripts[ uuid ] === undefined ) return '';

		if ( editor.scripts[ uuid ].length === 0 ) return '';

		return ' <span class="type Script"></span>';

	}
```
</details>

### `onBackgroundChanged(): void`

**Returns:** `void`

**Calls:**

- `signals.sceneBackgroundChanged.dispatch`
- `backgroundType.getValue`
- `backgroundColor.getHexValue`
- `backgroundTexture.getValue`
- `backgroundEquirectangularTexture.getValue`
- `backgroundColorSpace.getValue`
- `backgroundBlurriness.getValue`
- `backgroundIntensity.getValue`
- `backgroundRotation.getValue`

<details><summary>Code</summary>

```typescript
function onBackgroundChanged() {

		signals.sceneBackgroundChanged.dispatch(
			backgroundType.getValue(),
			backgroundColor.getHexValue(),
			backgroundTexture.getValue(),
			backgroundEquirectangularTexture.getValue(),
			backgroundColorSpace.getValue(),
			backgroundBlurriness.getValue(),
			backgroundIntensity.getValue(),
			backgroundRotation.getValue()
		);

	}
```
</details>

### `refreshBackgroundUI(): void`

**Returns:** `void`

**Calls:**

- `backgroundType.getValue`
- `backgroundType.setWidth`
- `backgroundColor.setDisplay`
- `backgroundTexture.setDisplay`
- `backgroundEquirectangularTexture.setDisplay`
- `backgroundEquirectRow.setDisplay`
- `backgroundColorSpaceRow.setDisplay`

<details><summary>Code</summary>

```typescript
function refreshBackgroundUI() {

		const type = backgroundType.getValue();

		backgroundType.setWidth( type === 'None' ? '150px' : '110px' );
		backgroundColor.setDisplay( type === 'Color' ? '' : 'none' );
		backgroundTexture.setDisplay( type === 'Texture' ? '' : 'none' );
		backgroundEquirectangularTexture.setDisplay( type === 'Equirectangular' ? '' : 'none' );
		backgroundEquirectRow.setDisplay( type === 'Equirectangular' ? '' : 'none' );

		if ( type === 'Texture' || type === 'Equirectangular' ) {

			backgroundColorSpaceRow.setDisplay( '' );

		} else {

			backgroundColorSpaceRow.setDisplay( 'none' );

		}

	}
```
</details>

### `onEnvironmentChanged(): void`

**Returns:** `void`

**Calls:**

- `signals.sceneEnvironmentChanged.dispatch`
- `environmentType.getValue`
- `environmentEquirectangularTexture.getValue`

<details><summary>Code</summary>

```typescript
function onEnvironmentChanged() {

		signals.sceneEnvironmentChanged.dispatch(
			environmentType.getValue(),
			environmentEquirectangularTexture.getValue()
		);

	}
```
</details>

### `refreshEnvironmentUI(): void`

**Returns:** `void`

**Calls:**

- `environmentType.getValue`
- `environmentType.setWidth`
- `environmentEquirectangularTexture.setDisplay`

<details><summary>Code</summary>

```typescript
function refreshEnvironmentUI() {

		const type = environmentType.getValue();

		environmentType.setWidth( type !== 'Equirectangular' ? '150px' : '110px' );
		environmentEquirectangularTexture.setDisplay( type === 'Equirectangular' ? '' : 'none' );

	}
```
</details>

### `onFogChanged(): void`

**Returns:** `void`

**Calls:**

- `signals.sceneFogChanged.dispatch`
- `fogType.getValue`
- `fogColor.getHexValue`
- `fogNear.getValue`
- `fogFar.getValue`
- `fogDensity.getValue`

<details><summary>Code</summary>

```typescript
function onFogChanged() {

		signals.sceneFogChanged.dispatch(
			fogType.getValue(),
			fogColor.getHexValue(),
			fogNear.getValue(),
			fogFar.getValue(),
			fogDensity.getValue()
		);

	}
```
</details>

### `onFogSettingsChanged(): void`

**Returns:** `void`

**Calls:**

- `signals.sceneFogSettingsChanged.dispatch`
- `fogType.getValue`
- `fogColor.getHexValue`
- `fogNear.getValue`
- `fogFar.getValue`
- `fogDensity.getValue`

<details><summary>Code</summary>

```typescript
function onFogSettingsChanged() {

		signals.sceneFogSettingsChanged.dispatch(
			fogType.getValue(),
			fogColor.getHexValue(),
			fogNear.getValue(),
			fogFar.getValue(),
			fogDensity.getValue()
		);

	}
```
</details>

### `refreshUI(): void`

**Returns:** `void`

**Calls:**

- `options.push`
- `buildOption`
- `complex_call_9519`
- `nodeStates.has`
- `nodeStates.set`
- `nodeStates.get`
- `addObjects`
- `outliner.setOptions`
- `outliner.setValue`
- `backgroundType.setValue`
- `backgroundColor.setHexValue`
- `scene.background.getHex`
- `backgroundEquirectangularTexture.setValue`
- `backgroundBlurriness.setValue`
- `backgroundIntensity.setValue`
- `backgroundTexture.setValue`
- `backgroundColorSpace.setValue`
- `environmentType.setValue`
- `environmentEquirectangularTexture.setValue`
- `fogColor.setHexValue`
- `scene.fog.color.getHex`
- `fogType.setValue`
- `fogNear.setValue`
- `fogFar.setValue`
- `fogDensity.setValue`
- `refreshBackgroundUI`
- `refreshEnvironmentUI`
- `refreshFogUI`

<details><summary>Code</summary>

```typescript
function refreshUI() {

		const camera = editor.camera;
		const scene = editor.scene;

		const options = [];

		options.push( buildOption( camera, false ) );
		options.push( buildOption( scene, false ) );

		( function addObjects( objects, pad ) {

			for ( let i = 0, l = objects.length; i < l; i ++ ) {

				const object = objects[ i ];

				if ( nodeStates.has( object ) === false ) {

					nodeStates.set( object, false );

				}

				const option = buildOption( object, true );
				option.style.paddingLeft = ( pad * 18 ) + 'px';
				options.push( option );

				if ( nodeStates.get( object ) === true ) {

					addObjects( object.children, pad + 1 );

				}

			}

		} )( scene.children, 0 );

		outliner.setOptions( options );

		if ( editor.selected !== null ) {

			outliner.setValue( editor.selected.id );

		}

		if ( scene.background ) {

			if ( scene.background.isColor ) {

				backgroundType.setValue( 'Color' );
				backgroundColor.setHexValue( scene.background.getHex() );

			} else if ( scene.background.isTexture ) {

				if ( scene.background.mapping === THREE.EquirectangularReflectionMapping ) {

					backgroundType.setValue( 'Equirectangular' );
					backgroundEquirectangularTexture.setValue( scene.background );
					backgroundBlurriness.setValue( scene.backgroundBlurriness );
					backgroundIntensity.setValue( scene.backgroundIntensity );

				} else {

					backgroundType.setValue( 'Texture' );
					backgroundTexture.setValue( scene.background );

				}

				backgroundColorSpace.setValue( scene.background.colorSpace );

			}

		} else {

			backgroundType.setValue( 'None' );
			backgroundTexture.setValue( null );
			backgroundEquirectangularTexture.setValue( null );
			backgroundColorSpace.setValue( THREE.NoColorSpace );

		}

		if ( scene.environment ) {

			if ( scene.background && scene.background.isTexture && scene.background.uuid === scene.environment.uuid ) {

				environmentType.setValue( 'Background' );

			} else if ( scene.environment.mapping === THREE.EquirectangularReflectionMapping ) {

				environmentType.setValue( 'Equirectangular' );
				environmentEquirectangularTexture.setValue( scene.environment );

			} else if ( scene.environment.isRenderTargetTexture === true ) {

				environmentType.setValue( 'Room' );

			}

		} else {

			environmentType.setValue( 'None' );
			environmentEquirectangularTexture.setValue( null );

		}

		if ( scene.fog ) {

			fogColor.setHexValue( scene.fog.color.getHex() );

			if ( scene.fog.isFog ) {

				fogType.setValue( 'Fog' );
				fogNear.setValue( scene.fog.near );
				fogFar.setValue( scene.fog.far );

			} else if ( scene.fog.isFogExp2 ) {

				fogType.setValue( 'FogExp2' );
				fogDensity.setValue( scene.fog.density );

			}

		} else {

			fogType.setValue( 'None' );

		}

		refreshBackgroundUI();
		refreshEnvironmentUI();
		refreshFogUI();

	}
```
</details>

### `refreshFogUI(): void`

**Returns:** `void`

**Calls:**

- `fogType.getValue`
- `fogPropertiesRow.setDisplay`
- `fogNear.setDisplay`
- `fogFar.setDisplay`
- `fogDensity.setDisplay`

<details><summary>Code</summary>

```typescript
function refreshFogUI() {

		const type = fogType.getValue();

		fogPropertiesRow.setDisplay( type === 'None' ? 'none' : '' );
		fogNear.setDisplay( type === 'Fog' ? '' : 'none' );
		fogFar.setDisplay( type === 'Fog' ? '' : 'none' );
		fogDensity.setDisplay( type === 'FogExp2' ? '' : 'none' );

	}
```
</details>


---