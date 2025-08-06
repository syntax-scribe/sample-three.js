[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Script.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 10 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Script.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIPanel` | `./libs/ui.js` |
| `UIBreak` | `./libs/ui.js` |
| `UIButton` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIInput` | `./libs/ui.js` |
| `AddScriptCommand` | `./commands/AddScriptCommand.js` |
| `SetScriptValueCommand` | `./commands/SetScriptValueCommand.js` |
| `RemoveScriptCommand` | `./commands/RemoveScriptCommand.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `scriptsContainer` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `newScript` | `UIButton` | let/var | `new UIButton( strings.getKey( 'sidebar/script/new' ) )` | ✗ |
| `script` | `{ name: string; source: string; }` | let/var | `{ name: '', source: 'function update( event ) {}' }` | ✗ |
| `object` | `any` | let/var | `editor.selected` | ✗ |
| `scripts` | `any` | let/var | `editor.scripts[ object.uuid ]` | ✗ |
| `edit` | `UIButton` | let/var | `new UIButton( strings.getKey( 'sidebar/script/edit' ) )` | ✗ |
| `remove` | `UIButton` | let/var | `new UIButton( strings.getKey( 'sidebar/script/remove' ) )` | ✗ |


---

## Functions

### `SidebarScript(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.setBorderTop`
- `container.setPaddingTop`
- `container.setDisplay`
- `container.add`
- `strings.getKey`
- `newScript.onClick`
- `editor.execute`
- `scriptsContainer.clear`
- `scriptsContainer.setDisplay`
- `complex_call_1408`
- `new UIInput( script.name ).setWidth( '130px' ).setFontSize`
- `name.onChange`
- `this.getValue`
- `scriptsContainer.add`
- `edit.setMarginLeft`
- `edit.onClick`
- `signals.editScript.dispatch`
- `remove.setMarginLeft`
- `remove.onClick`
- `confirm`
- `signals.objectSelected.add`
- `update`
- `signals.scriptAdded.add`
- `signals.scriptRemoved.add`
- `signals.scriptChanged.add`

**Internal Comments:**
```
// (x3)
/*
	let loadScript = new UI.Button( 'Load' );
	loadScript.setMarginLeft( '4px' );
	container.add( loadScript );
	*/
// signals (x5)
```

<details><summary>Code</summary>

```typescript
function SidebarScript( editor ) {

	const strings = editor.strings;

	const signals = editor.signals;

	const container = new UIPanel();
	container.setBorderTop( '0' );
	container.setPaddingTop( '20px' );
	container.setDisplay( 'none' );

	//

	const scriptsContainer = new UIRow();
	container.add( scriptsContainer );

	const newScript = new UIButton( strings.getKey( 'sidebar/script/new' ) );
	newScript.onClick( function () {

		const script = { name: '', source: 'function update( event ) {}' };
		editor.execute( new AddScriptCommand( editor, editor.selected, script ) );

	} );
	container.add( newScript );

	/*
	let loadScript = new UI.Button( 'Load' );
	loadScript.setMarginLeft( '4px' );
	container.add( loadScript );
	*/

	//

	function update() {

		scriptsContainer.clear();
		scriptsContainer.setDisplay( 'none' );

		const object = editor.selected;

		if ( object === null ) {

			return;

		}

		const scripts = editor.scripts[ object.uuid ];

		if ( scripts !== undefined && scripts.length > 0 ) {

			scriptsContainer.setDisplay( 'block' );

			for ( let i = 0; i < scripts.length; i ++ ) {

				( function ( object, script ) {

					const name = new UIInput( script.name ).setWidth( '130px' ).setFontSize( '12px' );
					name.onChange( function () {

						editor.execute( new SetScriptValueCommand( editor, editor.selected, script, 'name', this.getValue() ) );

					} );
					scriptsContainer.add( name );

					const edit = new UIButton( strings.getKey( 'sidebar/script/edit' ) );
					edit.setMarginLeft( '4px' );
					edit.onClick( function () {

						signals.editScript.dispatch( object, script );

					} );
					scriptsContainer.add( edit );

					const remove = new UIButton( strings.getKey( 'sidebar/script/remove' ) );
					remove.setMarginLeft( '4px' );
					remove.onClick( function () {

						if ( confirm( strings.getKey( 'prompt/script/remove' ) ) ) {

							editor.execute( new RemoveScriptCommand( editor, editor.selected, script ) );

						}

					} );
					scriptsContainer.add( remove );

					scriptsContainer.add( new UIBreak() );

				} )( object, scripts[ i ] );

			}

		}

	}

	// signals

	signals.objectSelected.add( function ( object ) {

		if ( object !== null && editor.camera !== object ) {

			container.setDisplay( 'block' );

			update();

		} else {

			container.setDisplay( 'none' );

		}

	} );

	signals.scriptAdded.add( update );
	signals.scriptRemoved.add( update );
	signals.scriptChanged.add( update );

	return container;

}
```
</details>

### `update(): void`

**Returns:** `void`

**Calls:**

- `scriptsContainer.clear`
- `scriptsContainer.setDisplay`
- `complex_call_1408`
- `new UIInput( script.name ).setWidth( '130px' ).setFontSize`
- `name.onChange`
- `editor.execute`
- `this.getValue`
- `scriptsContainer.add`
- `strings.getKey`
- `edit.setMarginLeft`
- `edit.onClick`
- `signals.editScript.dispatch`
- `remove.setMarginLeft`
- `remove.onClick`
- `confirm`

<details><summary>Code</summary>

```typescript
function update() {

		scriptsContainer.clear();
		scriptsContainer.setDisplay( 'none' );

		const object = editor.selected;

		if ( object === null ) {

			return;

		}

		const scripts = editor.scripts[ object.uuid ];

		if ( scripts !== undefined && scripts.length > 0 ) {

			scriptsContainer.setDisplay( 'block' );

			for ( let i = 0; i < scripts.length; i ++ ) {

				( function ( object, script ) {

					const name = new UIInput( script.name ).setWidth( '130px' ).setFontSize( '12px' );
					name.onChange( function () {

						editor.execute( new SetScriptValueCommand( editor, editor.selected, script, 'name', this.getValue() ) );

					} );
					scriptsContainer.add( name );

					const edit = new UIButton( strings.getKey( 'sidebar/script/edit' ) );
					edit.setMarginLeft( '4px' );
					edit.onClick( function () {

						signals.editScript.dispatch( object, script );

					} );
					scriptsContainer.add( edit );

					const remove = new UIButton( strings.getKey( 'sidebar/script/remove' ) );
					remove.setMarginLeft( '4px' );
					remove.onClick( function () {

						if ( confirm( strings.getKey( 'prompt/script/remove' ) ) ) {

							editor.execute( new RemoveScriptCommand( editor, editor.selected, script ) );

						}

					} );
					scriptsContainer.add( remove );

					scriptsContainer.add( new UIBreak() );

				} )( object, scripts[ i ] );

			}

		}

	}
```
</details>


---