[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Settings.History.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 14 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Settings.History.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIButton` | `./libs/ui.js` |
| `UIPanel` | `./libs/ui.js` |
| `UIBreak` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `UIBoolean` | `./libs/ui.three.js` |
| `UIOutliner` | `./libs/ui.three.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `config` | `any` | let/var | `editor.config` | ✗ |
| `history` | `any` | let/var | `editor.history` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `persistent` | `UIBoolean` | let/var | `new UIBoolean( config.getKey( 'settings/history' ), strings.getKey( 'sidebar/...` | ✗ |
| `lastUndoCmd` | `any` | let/var | `history.undos[ history.undos.length - 1 ]` | ✗ |
| `lastUndoId` | `any` | let/var | `( lastUndoCmd !== undefined ) ? lastUndoCmd.id : 0` | ✗ |
| `ignoreObjectSelectedSignal` | `boolean` | let/var | `false` | ✗ |
| `outliner` | `UIOutliner` | let/var | `new UIOutliner( editor )` | ✗ |
| `option` | `UIButton` | let/var | `new UIButton( strings.getKey( 'sidebar/history/clear' ) )` | ✗ |
| `options` | `any[]` | let/var | `[]` | ✗ |
| `object` | `any` | let/var | `objects[ i ]` | ✗ |
| `object` | `any` | let/var | `objects[ i ]` | ✗ |


---

## Functions

### `SidebarSettingsHistory(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.add`
- `strings.getKey( 'sidebar/history' ).toUpperCase`
- `config.getKey`
- `strings.getKey`
- `persistent.setPosition( 'absolute' ).setRight`
- `persistent.onChange`
- `this.getValue`
- `config.setKey`
- `alert`
- `editor.history.enableSerialization`
- `signals.historyChanged.dispatch`
- `outliner.onChange`
- `editor.history.goToState`
- `parseInt`
- `outliner.getValue`
- `option.onClick`
- `confirm`
- `editor.history.clear`
- `document.createElement`
- `complex_call_1930`
- `buildOption`
- `options.push`
- `complex_call_2210`
- `outliner.setOptions`
- `refreshUI`
- `signals.editorCleared.add`
- `signals.historyChanged.add`
- `outliner.setValue`

**Internal Comments:**
```
// (x4)
// Clear History (x2)
// events (x5)
```

<details><summary>Code</summary>

```typescript
function SidebarSettingsHistory( editor ) {

	const strings = editor.strings;
	const signals = editor.signals;
	const config = editor.config;
	const history = editor.history;

	const container = new UIPanel();

	container.add( new UIText( strings.getKey( 'sidebar/history' ).toUpperCase() ) );

	//

	const persistent = new UIBoolean( config.getKey( 'settings/history' ), strings.getKey( 'sidebar/history/persistent' ) );
	persistent.setPosition( 'absolute' ).setRight( '8px' );
	persistent.onChange( function () {

		const value = this.getValue();

		config.setKey( 'settings/history', value );

		if ( value ) {

			alert( strings.getKey( 'prompt/history/preserve' ) );

			const lastUndoCmd = history.undos[ history.undos.length - 1 ];
			const lastUndoId = ( lastUndoCmd !== undefined ) ? lastUndoCmd.id : 0;
			editor.history.enableSerialization( lastUndoId );

		} else {

			signals.historyChanged.dispatch();

		}

	} );
	container.add( persistent );

	container.add( new UIBreak(), new UIBreak() );

	let ignoreObjectSelectedSignal = false;

	const outliner = new UIOutliner( editor );
	outliner.onChange( function () {

		ignoreObjectSelectedSignal = true;

		editor.history.goToState( parseInt( outliner.getValue() ) );

		ignoreObjectSelectedSignal = false;

	} );
	container.add( outliner );

	container.add( new UIBreak() );

	// Clear History

	const option = new UIButton( strings.getKey( 'sidebar/history/clear' ) );
	option.onClick( function () {

		if ( confirm( strings.getKey( 'prompt/history/clear' ) ) ) {

			editor.history.clear();

		}

	} );
	container.add( option );

	//

	const refreshUI = function () {

		const options = [];

		function buildOption( object ) {

			const option = document.createElement( 'div' );
			option.value = object.id;

			return option;

		}

		( function addObjects( objects ) {

			for ( let i = 0, l = objects.length; i < l; i ++ ) {

				const object = objects[ i ];

				const option = buildOption( object );
				option.innerHTML = '&nbsp;' + object.name;

				options.push( option );

			}

		} )( history.undos );


		( function addObjects( objects ) {

			for ( let i = objects.length - 1; i >= 0; i -- ) {

				const object = objects[ i ];

				const option = buildOption( object );
				option.innerHTML = '&nbsp;' + object.name;
				option.style.opacity = 0.3;

				options.push( option );

			}

		} )( history.redos );

		outliner.setOptions( options );

	};

	refreshUI();

	// events

	signals.editorCleared.add( refreshUI );

	signals.historyChanged.add( refreshUI );
	signals.historyChanged.add( function ( cmd ) {

		if ( ignoreObjectSelectedSignal === true ) return;

		outliner.setValue( cmd !== undefined ? cmd.id : null );

	} );


	return container;

}
```
</details>

### `refreshUI(): void`

**Returns:** `void`

**Calls:**

- `document.createElement`
- `complex_call_1930`
- `buildOption`
- `options.push`
- `complex_call_2210`
- `outliner.setOptions`

<details><summary>Code</summary>

```typescript
function () {

		const options = [];

		function buildOption( object ) {

			const option = document.createElement( 'div' );
			option.value = object.id;

			return option;

		}

		( function addObjects( objects ) {

			for ( let i = 0, l = objects.length; i < l; i ++ ) {

				const object = objects[ i ];

				const option = buildOption( object );
				option.innerHTML = '&nbsp;' + object.name;

				options.push( option );

			}

		} )( history.undos );


		( function addObjects( objects ) {

			for ( let i = objects.length - 1; i >= 0; i -- ) {

				const object = objects[ i ];

				const option = buildOption( object );
				option.innerHTML = '&nbsp;' + object.name;
				option.style.opacity = 0.3;

				options.push( option );

			}

		} )( history.redos );

		outliner.setOptions( options );

	}
```
</details>

### `buildOption(object: any): HTMLDivElement`

**Parameters:**

- **`object`** `any`

**Returns:** `HTMLDivElement`

**Calls:**

- `document.createElement`

<details><summary>Code</summary>

```typescript
function buildOption( object ) {

			const option = document.createElement( 'div' );
			option.value = object.id;

			return option;

		}
```
</details>


---