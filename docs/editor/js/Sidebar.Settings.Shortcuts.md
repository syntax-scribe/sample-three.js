[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Settings.Shortcuts.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Settings.Shortcuts.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIPanel` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIInput` | `./libs/ui.js` |
| `RemoveObjectCommand` | `./commands/RemoveObjectCommand.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `IS_MAC` | `boolean` | let/var | `navigator.platform.toUpperCase().indexOf( 'MAC' ) >= 0` | ✗ |
| `config` | `any` | let/var | `editor.config` | ✗ |
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `headerRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `shortcuts` | `string[]` | let/var | `[ 'translate', 'rotate', 'scale', 'undo', 'focus' ]` | ✗ |
| `configName` | `string` | let/var | `'settings/shortcuts/' + name` | ✗ |
| `shortcutRow` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `object` | `any` | let/var | `editor.selected` | ✗ |
| `parent` | `any` | let/var | `object.parent` | ✗ |


---

## Functions

### `SidebarSettingsShortcuts(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `navigator.platform.toUpperCase().indexOf`
- `key.match`
- `headerRow.add`
- `strings.getKey( 'sidebar/settings/shortcuts' ).toUpperCase`
- `container.add`
- `new UIInput().setWidth( '15px' ).setFontSize`
- `shortcutInput.setTextAlign`
- `shortcutInput.setTextTransform`
- `shortcutInput.onChange`
- `shortcutInput.getValue().toLowerCase`
- `isValidKeyBinding`
- `config.setKey`
- `shortcutInput.dom.addEventListener`
- `shortcutInput.dom.select`
- `shortcutInput.getValue`
- `shortcutInput.setValue`
- `config.getKey`
- `shortcutInput.dom.blur`
- `shortcutRow.add`
- `new UIText( strings.getKey( 'sidebar/settings/shortcuts/' + name ) ).setTextTransform( 'capitalize' ).setClass`
- `createShortcutInput`
- `document.addEventListener`
- `event.key.toLowerCase`
- `event.preventDefault`
- `editor.execute`
- `signals.transformModeChanged.dispatch`
- `editor.redo`
- `editor.undo`
- `editor.focus`

**Internal Comments:**
```
// Automatically highlight when selecting an input field (x5)
// If the value of the input field is invalid, revert the input field (x5)
// to contain the key binding stored in config (x5)
// If a valid key binding character is entered, blur the input field (x5)
// fall-through
```

<details><summary>Code</summary>

```typescript
function SidebarSettingsShortcuts( editor ) {

	const strings = editor.strings;

	const IS_MAC = navigator.platform.toUpperCase().indexOf( 'MAC' ) >= 0;

	function isValidKeyBinding( key ) {

		return key.match( /^[A-Za-z0-9]$/i ); // Can't use z currently due to undo/redo

	}

	const config = editor.config;
	const signals = editor.signals;

	const container = new UIPanel();

	const headerRow = new UIRow();
	headerRow.add( new UIText( strings.getKey( 'sidebar/settings/shortcuts' ).toUpperCase() ) );
	container.add( headerRow );

	const shortcuts = [ 'translate', 'rotate', 'scale', 'undo', 'focus' ];

	function createShortcutInput( name ) {

		const configName = 'settings/shortcuts/' + name;
		const shortcutRow = new UIRow();

		const shortcutInput = new UIInput().setWidth( '15px' ).setFontSize( '12px' );
		shortcutInput.setTextAlign( 'center' );
		shortcutInput.setTextTransform( 'lowercase' );
		shortcutInput.onChange( function () {

			const value = shortcutInput.getValue().toLowerCase();

			if ( isValidKeyBinding( value ) ) {

				config.setKey( configName, value );

			}

		} );

		// Automatically highlight when selecting an input field
		shortcutInput.dom.addEventListener( 'click', function () {

			shortcutInput.dom.select();

		} );

		// If the value of the input field is invalid, revert the input field
		// to contain the key binding stored in config
		shortcutInput.dom.addEventListener( 'blur', function () {

			if ( ! isValidKeyBinding( shortcutInput.getValue() ) ) {

				shortcutInput.setValue( config.getKey( configName ) );

			}

		} );

		// If a valid key binding character is entered, blur the input field
		shortcutInput.dom.addEventListener( 'keyup', function ( event ) {

			if ( isValidKeyBinding( event.key ) ) {

				shortcutInput.dom.blur();

			}

		} );

		if ( config.getKey( configName ) !== undefined ) {

			shortcutInput.setValue( config.getKey( configName ) );

		}

		shortcutInput.dom.maxLength = 1;
		shortcutRow.add( new UIText( strings.getKey( 'sidebar/settings/shortcuts/' + name ) ).setTextTransform( 'capitalize' ).setClass( 'Label' ) );
		shortcutRow.add( shortcutInput );

		container.add( shortcutRow );

	}

	for ( let i = 0; i < shortcuts.length; i ++ ) {

		createShortcutInput( shortcuts[ i ] );

	}

	document.addEventListener( 'keydown', function ( event ) {

		switch ( event.key.toLowerCase() ) {

			case 'backspace':

				event.preventDefault(); // prevent browser back

				// fall-through

			case 'delete':

				const object = editor.selected;

				if ( object === null ) return;

				const parent = object.parent;
				if ( parent !== null ) editor.execute( new RemoveObjectCommand( editor, object ) );

				break;

			case config.getKey( 'settings/shortcuts/translate' ):

				signals.transformModeChanged.dispatch( 'translate' );

				break;

			case config.getKey( 'settings/shortcuts/rotate' ):

				signals.transformModeChanged.dispatch( 'rotate' );

				break;

			case config.getKey( 'settings/shortcuts/scale' ):

				signals.transformModeChanged.dispatch( 'scale' );

				break;

			case config.getKey( 'settings/shortcuts/undo' ):

				if ( IS_MAC ? event.metaKey : event.ctrlKey ) {

					event.preventDefault(); // Prevent browser specific hotkeys

					if ( event.shiftKey ) {

						editor.redo();

					} else {

						editor.undo();

					}

				}

				break;

			case config.getKey( 'settings/shortcuts/focus' ):

				if ( editor.selected !== null ) {

					editor.focus( editor.selected );

				}

				break;

		}

	} );

	return container;

}
```
</details>

### `isValidKeyBinding(key: any): any`

**Parameters:**

- **`key`** `any`

**Returns:** `any`

**Calls:**

- `key.match`

<details><summary>Code</summary>

```typescript
function isValidKeyBinding( key ) {

		return key.match( /^[A-Za-z0-9]$/i ); // Can't use z currently due to undo/redo

	}
```
</details>

### `createShortcutInput(name: any): void`

**Parameters:**

- **`name`** `any`

**Returns:** `void`

**Calls:**

- `new UIInput().setWidth( '15px' ).setFontSize`
- `shortcutInput.setTextAlign`
- `shortcutInput.setTextTransform`
- `shortcutInput.onChange`
- `shortcutInput.getValue().toLowerCase`
- `isValidKeyBinding`
- `config.setKey`
- `shortcutInput.dom.addEventListener`
- `shortcutInput.dom.select`
- `shortcutInput.getValue`
- `shortcutInput.setValue`
- `config.getKey`
- `shortcutInput.dom.blur`
- `shortcutRow.add`
- `new UIText( strings.getKey( 'sidebar/settings/shortcuts/' + name ) ).setTextTransform( 'capitalize' ).setClass`
- `container.add`

**Internal Comments:**
```
// Automatically highlight when selecting an input field (x5)
// If the value of the input field is invalid, revert the input field (x5)
// to contain the key binding stored in config (x5)
// If a valid key binding character is entered, blur the input field (x5)
```

<details><summary>Code</summary>

```typescript
function createShortcutInput( name ) {

		const configName = 'settings/shortcuts/' + name;
		const shortcutRow = new UIRow();

		const shortcutInput = new UIInput().setWidth( '15px' ).setFontSize( '12px' );
		shortcutInput.setTextAlign( 'center' );
		shortcutInput.setTextTransform( 'lowercase' );
		shortcutInput.onChange( function () {

			const value = shortcutInput.getValue().toLowerCase();

			if ( isValidKeyBinding( value ) ) {

				config.setKey( configName, value );

			}

		} );

		// Automatically highlight when selecting an input field
		shortcutInput.dom.addEventListener( 'click', function () {

			shortcutInput.dom.select();

		} );

		// If the value of the input field is invalid, revert the input field
		// to contain the key binding stored in config
		shortcutInput.dom.addEventListener( 'blur', function () {

			if ( ! isValidKeyBinding( shortcutInput.getValue() ) ) {

				shortcutInput.setValue( config.getKey( configName ) );

			}

		} );

		// If a valid key binding character is entered, blur the input field
		shortcutInput.dom.addEventListener( 'keyup', function ( event ) {

			if ( isValidKeyBinding( event.key ) ) {

				shortcutInput.dom.blur();

			}

		} );

		if ( config.getKey( configName ) !== undefined ) {

			shortcutInput.setValue( config.getKey( configName ) );

		}

		shortcutInput.dom.maxLength = 1;
		shortcutRow.add( new UIText( strings.getKey( 'sidebar/settings/shortcuts/' + name ) ).setTextTransform( 'capitalize' ).setClass( 'Label' ) );
		shortcutRow.add( shortcutInput );

		container.add( shortcutRow );

	}
```
</details>


---