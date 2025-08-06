[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Project.Renderer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Project.Renderer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UINumber` | `./libs/ui.js` |
| `UIPanel` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UISelect` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `UIBoolean` | `./libs/ui.three.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `config` | `any` | let/var | `editor.config` | ✗ |
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `currentRenderer` | `any` | let/var | `null` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `antialiasRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `shadowsRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `toneMappingRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `toneMappingExposure` | `UINumber` | let/var | `new UINumber( config.getKey( 'project/renderer/toneMappingExposure' ) )` | ✗ |


---

## Functions

### `SidebarProjectRenderer(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.setBorderTop`
- `container.add`
- `antialiasRow.add`
- `new UIText( strings.getKey( 'sidebar/project/antialias' ) ).setClass`
- `strings.getKey`
- `new UIBoolean( config.getKey( 'project/renderer/antialias' ) ).onChange`
- `config.getKey`
- `shadowsRow.add`
- `new UIText( strings.getKey( 'sidebar/project/shadows' ) ).setClass`
- `new UIBoolean( config.getKey( 'project/renderer/shadows' ) ).onChange`
- `new UISelect().setOptions( {
		0: 'Basic',
		1: 'PCF',
		2: 'PCF Soft',
		//	3: 'VSM'
	} ).setWidth( '125px' ).onChange`
- `shadowTypeSelect.setValue`
- `shadowsBoolean.getValue`
- `parseFloat`
- `shadowTypeSelect.getValue`
- `signals.rendererUpdated.dispatch`
- `toneMappingRow.add`
- `new UIText( strings.getKey( 'sidebar/project/toneMapping' ) ).setClass`
- `new UISelect().setOptions( {
		0: 'No',
		1: 'Linear',
		2: 'Reinhard',
		3: 'Cineon',
		4: 'ACESFilmic',
		6: 'AgX',
		7: 'Neutral'
	} ).setWidth( '120px' ).onChange`
- `toneMappingSelect.setValue`
- `toneMappingExposure.setDisplay`
- `toneMappingSelect.getValue`
- `toneMappingExposure.setWidth( '30px' ).setMarginLeft`
- `toneMappingExposure.setRange`
- `toneMappingExposure.onChange`
- `toneMappingExposure.getValue`
- `antialiasBoolean.getValue`
- `signals.rendererCreated.dispatch`
- `createRenderer`
- `signals.editorCleared.add`
- `shadowsBoolean.setValue`
- `toneMappingExposure.setValue`
- `signals.rendererUpdated.add`
- `config.setKey`

**Internal Comments:**
```
// Antialias (x2)
// Shadows (x2)
// Tonemapping (x2)
//
// Signals (x5)
```

<details><summary>Code</summary>

```typescript
function SidebarProjectRenderer( editor ) {

	const config = editor.config;
	const signals = editor.signals;
	const strings = editor.strings;

	let currentRenderer = null;

	const container = new UIPanel();
	container.setBorderTop( '0px' );

	// Antialias

	const antialiasRow = new UIRow();
	container.add( antialiasRow );

	antialiasRow.add( new UIText( strings.getKey( 'sidebar/project/antialias' ) ).setClass( 'Label' ) );

	const antialiasBoolean = new UIBoolean( config.getKey( 'project/renderer/antialias' ) ).onChange( createRenderer );
	antialiasRow.add( antialiasBoolean );

	// Shadows

	const shadowsRow = new UIRow();
	container.add( shadowsRow );

	shadowsRow.add( new UIText( strings.getKey( 'sidebar/project/shadows' ) ).setClass( 'Label' ) );

	const shadowsBoolean = new UIBoolean( config.getKey( 'project/renderer/shadows' ) ).onChange( updateShadows );
	shadowsRow.add( shadowsBoolean );

	const shadowTypeSelect = new UISelect().setOptions( {
		0: 'Basic',
		1: 'PCF',
		2: 'PCF Soft',
		//	3: 'VSM'
	} ).setWidth( '125px' ).onChange( updateShadows );
	shadowTypeSelect.setValue( config.getKey( 'project/renderer/shadowType' ) );
	shadowsRow.add( shadowTypeSelect );

	function updateShadows() {

		currentRenderer.shadowMap.enabled = shadowsBoolean.getValue();
		currentRenderer.shadowMap.type = parseFloat( shadowTypeSelect.getValue() );

		signals.rendererUpdated.dispatch();

	}

	// Tonemapping

	const toneMappingRow = new UIRow();
	container.add( toneMappingRow );

	toneMappingRow.add( new UIText( strings.getKey( 'sidebar/project/toneMapping' ) ).setClass( 'Label' ) );

	const toneMappingSelect = new UISelect().setOptions( {
		0: 'No',
		1: 'Linear',
		2: 'Reinhard',
		3: 'Cineon',
		4: 'ACESFilmic',
		6: 'AgX',
		7: 'Neutral'
	} ).setWidth( '120px' ).onChange( updateToneMapping );
	toneMappingSelect.setValue( config.getKey( 'project/renderer/toneMapping' ) );
	toneMappingRow.add( toneMappingSelect );

	const toneMappingExposure = new UINumber( config.getKey( 'project/renderer/toneMappingExposure' ) );
	toneMappingExposure.setDisplay( toneMappingSelect.getValue() === '0' ? 'none' : '' );
	toneMappingExposure.setWidth( '30px' ).setMarginLeft( '10px' );
	toneMappingExposure.setRange( 0, 10 );
	toneMappingExposure.onChange( updateToneMapping );
	toneMappingRow.add( toneMappingExposure );

	function updateToneMapping() {

		toneMappingExposure.setDisplay( toneMappingSelect.getValue() === '0' ? 'none' : '' );

		currentRenderer.toneMapping = parseFloat( toneMappingSelect.getValue() );
		currentRenderer.toneMappingExposure = toneMappingExposure.getValue();
		signals.rendererUpdated.dispatch();

	}

	//

	function createRenderer() {

		currentRenderer = new THREE.WebGLRenderer( { antialias: antialiasBoolean.getValue() } );
		currentRenderer.shadowMap.enabled = shadowsBoolean.getValue();
		currentRenderer.shadowMap.type = parseFloat( shadowTypeSelect.getValue() );
		currentRenderer.toneMapping = parseFloat( toneMappingSelect.getValue() );
		currentRenderer.toneMappingExposure = toneMappingExposure.getValue();

		signals.rendererCreated.dispatch( currentRenderer );
		signals.rendererUpdated.dispatch();

	}

	createRenderer();


	// Signals

	signals.editorCleared.add( function () {

		currentRenderer.shadowMap.enabled = true;
		currentRenderer.shadowMap.type = THREE.PCFShadowMap;
		currentRenderer.toneMapping = THREE.NoToneMapping;
		currentRenderer.toneMappingExposure = 1;

		shadowsBoolean.setValue( currentRenderer.shadowMap.enabled );
		shadowTypeSelect.setValue( currentRenderer.shadowMap.type );
		toneMappingSelect.setValue( currentRenderer.toneMapping );
		toneMappingExposure.setValue( currentRenderer.toneMappingExposure );
		toneMappingExposure.setDisplay( currentRenderer.toneMapping === 0 ? 'none' : '' );

		signals.rendererUpdated.dispatch();

	} );

	signals.rendererUpdated.add( function () {

		config.setKey(
			'project/renderer/antialias', antialiasBoolean.getValue(),
			'project/renderer/shadows', shadowsBoolean.getValue(),
			'project/renderer/shadowType', parseFloat( shadowTypeSelect.getValue() ),
			'project/renderer/toneMapping', parseFloat( toneMappingSelect.getValue() ),
			'project/renderer/toneMappingExposure', toneMappingExposure.getValue()
		);

	} );

	return container;

}
```
</details>

### `updateShadows(): void`

**Returns:** `void`

**Calls:**

- `shadowsBoolean.getValue`
- `parseFloat`
- `shadowTypeSelect.getValue`
- `signals.rendererUpdated.dispatch`

<details><summary>Code</summary>

```typescript
function updateShadows() {

		currentRenderer.shadowMap.enabled = shadowsBoolean.getValue();
		currentRenderer.shadowMap.type = parseFloat( shadowTypeSelect.getValue() );

		signals.rendererUpdated.dispatch();

	}
```
</details>

### `updateToneMapping(): void`

**Returns:** `void`

**Calls:**

- `toneMappingExposure.setDisplay`
- `toneMappingSelect.getValue`
- `parseFloat`
- `toneMappingExposure.getValue`
- `signals.rendererUpdated.dispatch`

<details><summary>Code</summary>

```typescript
function updateToneMapping() {

		toneMappingExposure.setDisplay( toneMappingSelect.getValue() === '0' ? 'none' : '' );

		currentRenderer.toneMapping = parseFloat( toneMappingSelect.getValue() );
		currentRenderer.toneMappingExposure = toneMappingExposure.getValue();
		signals.rendererUpdated.dispatch();

	}
```
</details>

### `createRenderer(): void`

**Returns:** `void`

**Calls:**

- `antialiasBoolean.getValue`
- `shadowsBoolean.getValue`
- `parseFloat`
- `shadowTypeSelect.getValue`
- `toneMappingSelect.getValue`
- `toneMappingExposure.getValue`
- `signals.rendererCreated.dispatch`
- `signals.rendererUpdated.dispatch`

<details><summary>Code</summary>

```typescript
function createRenderer() {

		currentRenderer = new THREE.WebGLRenderer( { antialias: antialiasBoolean.getValue() } );
		currentRenderer.shadowMap.enabled = shadowsBoolean.getValue();
		currentRenderer.shadowMap.type = parseFloat( shadowTypeSelect.getValue() );
		currentRenderer.toneMapping = parseFloat( toneMappingSelect.getValue() );
		currentRenderer.toneMappingExposure = toneMappingExposure.getValue();

		signals.rendererCreated.dispatch( currentRenderer );
		signals.rendererUpdated.dispatch();

	}
```
</details>


---