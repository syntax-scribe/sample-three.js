[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Menubar.Status.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Menubar.Status.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIPanel` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `UIBoolean` | `./libs/ui.three.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `autosave` | `UIBoolean` | let/var | `new UIBoolean( editor.config.getKey( 'autosave' ), strings.getKey( 'menubar/s...` | ✗ |
| `version` | `UIText` | let/var | `new UIText( 'r' + THREE.REVISION )` | ✗ |


---

## Functions

### `MenubarStatus(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.setClass`
- `editor.config.getKey`
- `strings.getKey`
- `autosave.text.setColor`
- `autosave.onChange`
- `this.getValue`
- `editor.config.setKey`
- `editor.signals.sceneGraphChanged.dispatch`
- `container.add`
- `editor.signals.savingStarted.add`
- `autosave.text.setTextDecoration`
- `editor.signals.savingFinished.add`
- `version.setClass`
- `version.setOpacity`

<details><summary>Code</summary>

```typescript
function MenubarStatus( editor ) {

	const strings = editor.strings;

	const container = new UIPanel();
	container.setClass( 'menu right' );

	const autosave = new UIBoolean( editor.config.getKey( 'autosave' ), strings.getKey( 'menubar/status/autosave' ) );
	autosave.text.setColor( '#888' );
	autosave.onChange( function () {

		const value = this.getValue();

		editor.config.setKey( 'autosave', value );

		if ( value === true ) {

			editor.signals.sceneGraphChanged.dispatch();

		}

	} );
	container.add( autosave );

	editor.signals.savingStarted.add( function () {

		autosave.text.setTextDecoration( 'underline' );

	} );

	editor.signals.savingFinished.add( function () {

		autosave.text.setTextDecoration( 'none' );

	} );

	const version = new UIText( 'r' + THREE.REVISION );
	version.setClass( 'title' );
	version.setOpacity( 0.5 );
	container.add( version );

	return container;

}
```
</details>


---