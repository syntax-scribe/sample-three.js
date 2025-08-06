[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Menubar.Edit.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 12 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Menubar.Edit.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Box3` | `three` |
| `Vector3` | `three` |
| `UIPanel` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |
| `UIHorizontalRule` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `AddObjectCommand` | `./commands/AddObjectCommand.js` |
| `RemoveObjectCommand` | `./commands/RemoveObjectCommand.js` |
| `SetPositionCommand` | `./commands/SetPositionCommand.js` |
| `clone` | `../../examples/jsm/utils/SkeletonUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `title` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `options` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `undo` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `redo` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `history` | `any` | let/var | `editor.history` | ✗ |
| `option` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `object` | `any` | let/var | `editor.selected` | ✗ |
| `newPosition` | `any` | let/var | `new Vector3()` | ✗ |
| `object` | `any` | let/var | `editor.selected` | ✗ |
| `object` | `any` | let/var | `editor.selected` | ✗ |


---

## Functions

### `MenubarEdit(editor: any): UIPanel`

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
- `undo.setClass`
- `undo.setTextContent`
- `undo.add`
- `new UIText( 'CTRL+Z' ).setClass`
- `undo.onClick`
- `editor.undo`
- `options.add`
- `redo.setClass`
- `redo.setTextContent`
- `redo.add`
- `new UIText( 'CTRL+SHIFT+Z' ).setClass`
- `redo.onClick`
- `editor.redo`
- `editor.signals.historyChanged.add`
- `onHistoryChanged`
- `option.setClass`
- `option.setTextContent`
- `option.onClick`
- `new Box3().setFromObject`
- `aabb.getCenter`
- `editor.execute`
- `clone (from ../../examples/jsm/utils/SkeletonUtils.js)`
- `option.add`
- `new UIText( 'DEL' ).setClass`

**Internal Comments:**
```
// Undo (x2)
// Redo (x2)
// --- (x4)
// Center (x2)
// Clone (x3)
// Delete (x3)
```

<details><summary>Code</summary>

```typescript
function MenubarEdit( editor ) {

	const strings = editor.strings;

	const container = new UIPanel();
	container.setClass( 'menu' );

	const title = new UIPanel();
	title.setClass( 'title' );
	title.setTextContent( strings.getKey( 'menubar/edit' ) );
	container.add( title );

	const options = new UIPanel();
	options.setClass( 'options' );
	container.add( options );

	// Undo

	const undo = new UIRow();
	undo.setClass( 'option' );
	undo.setTextContent( strings.getKey( 'menubar/edit/undo' ) );
	undo.add( new UIText( 'CTRL+Z' ).setClass( 'key' ) );
	undo.onClick( function () {

		editor.undo();

	} );
	options.add( undo );

	// Redo

	const redo = new UIRow();
	redo.setClass( 'option' );
	redo.setTextContent( strings.getKey( 'menubar/edit/redo' ) );
	redo.add( new UIText( 'CTRL+SHIFT+Z' ).setClass( 'key' ) );
	redo.onClick( function () {

		editor.redo();

	} );
	options.add( redo );

	function onHistoryChanged() {

		const history = editor.history;

		undo.setClass( 'option' );
		redo.setClass( 'option' );

		if ( history.undos.length == 0 ) {

			undo.setClass( 'inactive' );

		}

		if ( history.redos.length == 0 ) {

			redo.setClass( 'inactive' );

		}

	}

	editor.signals.historyChanged.add( onHistoryChanged );
	onHistoryChanged();

	// ---

	options.add( new UIHorizontalRule() );

	// Center

	let option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/edit/center' ) );
	option.onClick( function () {

		const object = editor.selected;

		if ( object === null || object.parent === null ) return; // avoid centering the camera or scene

		const aabb = new Box3().setFromObject( object );
		const center = aabb.getCenter( new Vector3() );
		const newPosition = new Vector3();

		newPosition.x = object.position.x - center.x;
		newPosition.y = object.position.y - center.y;
		newPosition.z = object.position.z - center.z;

		editor.execute( new SetPositionCommand( editor, object, newPosition ) );

	} );
	options.add( option );

	// Clone

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/edit/clone' ) );
	option.onClick( function () {

		let object = editor.selected;

		if ( object === null || object.parent === null ) return; // avoid cloning the camera or scene

		object = clone( object );

		editor.execute( new AddObjectCommand( editor, object ) );

	} );
	options.add( option );

	// Delete

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/edit/delete' ) );
	option.add( new UIText( 'DEL' ).setClass( 'key' ) );
	option.onClick( function () {

		const object = editor.selected;

		if ( object !== null && object.parent !== null ) {

			editor.execute( new RemoveObjectCommand( editor, object ) );

		}

	} );
	options.add( option );

	return container;

}
```
</details>

### `onHistoryChanged(): void`

**Returns:** `void`

**Calls:**

- `undo.setClass`
- `redo.setClass`

<details><summary>Code</summary>

```typescript
function onHistoryChanged() {

		const history = editor.history;

		undo.setClass( 'option' );
		redo.setClass( 'option' );

		if ( history.undos.length == 0 ) {

			undo.setClass( 'inactive' );

		}

		if ( history.redos.length == 0 ) {

			redo.setClass( 'inactive' );

		}

	}
```
</details>


---