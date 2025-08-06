[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Viewport.ViewHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/Viewport.ViewHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIPanel` | `./libs/ui.js` |
| `ViewHelperBase` | `three/addons/helpers/ViewHelper.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `panel` | `UIPanel` | let/var | `new UIPanel()` | ✗ |


---

## Classes

### `ViewHelper`

<details><summary>Class Code</summary>

```ts
class ViewHelper extends ViewHelperBase {

	constructor( editorCamera, container ) {

		super( editorCamera, container.dom );

		const panel = new UIPanel();
		panel.setId( 'viewHelper' );
		panel.setPosition( 'absolute' );
		panel.setRight( '0px' );
		panel.setBottom( '0px' );
		panel.setHeight( '128px' );
		panel.setWidth( '128px' );

		panel.dom.addEventListener( 'pointerup', ( event ) => {

			event.stopPropagation();

			this.handleClick( event );

		} );

		panel.dom.addEventListener( 'pointerdown', function ( event ) {

			event.stopPropagation();

		} );

		container.add( panel );

	}

}
```
</details>


---