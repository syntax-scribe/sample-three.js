[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Menubar.Help.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Menubar.Help.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIPanel` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `title` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `options` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `option` | `UIRow` | let/var | `new UIRow()` | ✗ |


---

## Functions

### `MenubarHelp(editor: any): UIPanel`

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
- `option.setClass`
- `option.setTextContent`
- `option.onClick`
- `window.open`
- `options.add`

**Internal Comments:**
```
// Source code (x2)
/*
	// Icon

	let option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/help/icons' ) );
	option.onClick( function () {

		window.open( 'https://www.flaticon.com/packs/interface-44', '_blank' );

	} );
	options.add( option );
	*/ (x3)
// About (x3)
// Manual (x3)
```

<details><summary>Code</summary>

```typescript
function MenubarHelp( editor ) {

	const strings = editor.strings;

	const container = new UIPanel();
	container.setClass( 'menu' );

	const title = new UIPanel();
	title.setClass( 'title' );
	title.setTextContent( strings.getKey( 'menubar/help' ) );
	container.add( title );

	const options = new UIPanel();
	options.setClass( 'options' );
	container.add( options );

	// Source code

	let option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/help/source_code' ) );
	option.onClick( function () {

		window.open( 'https://github.com/mrdoob/three.js/tree/master/editor', '_blank' );

	} );
	options.add( option );

	/*
	// Icon

	let option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/help/icons' ) );
	option.onClick( function () {

		window.open( 'https://www.flaticon.com/packs/interface-44', '_blank' );

	} );
	options.add( option );
	*/

	// About

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/help/about' ) );
	option.onClick( function () {

		window.open( 'https://threejs.org', '_blank' );

	} );
	options.add( option );

	// Manual

	option = new UIRow();
	option.setClass( 'option' );
	option.setTextContent( strings.getKey( 'menubar/help/manual' ) );
	option.onClick( function () {

		window.open( 'https://github.com/mrdoob/three.js/wiki/Editor-Manual', '_blank' );

	} );
	options.add( option );

	return container;

}
```
</details>


---