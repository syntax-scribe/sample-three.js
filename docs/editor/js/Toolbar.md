[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Toolbar.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Toolbar.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIPanel` | `./libs/ui.js` |
| `UIButton` | `./libs/ui.js` |
| `UICheckbox` | `./libs/ui.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `translate` | `UIButton` | let/var | `new UIButton()` | ✗ |
| `rotate` | `UIButton` | let/var | `new UIButton()` | ✗ |
| `scale` | `UIButton` | let/var | `new UIButton()` | ✗ |
| `local` | `UICheckbox` | let/var | `new UICheckbox( false )` | ✗ |


---

## Functions

### `Toolbar(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.setId`
- `document.createElement`
- `strings.getKey`
- `translate.dom.appendChild`
- `translate.onClick`
- `signals.transformModeChanged.dispatch`
- `container.add`
- `rotate.dom.appendChild`
- `rotate.onClick`
- `scale.dom.appendChild`
- `scale.onClick`
- `local.onChange`
- `signals.spaceChanged.dispatch`
- `this.getValue`
- `signals.transformModeChanged.add`
- `translate.dom.classList.remove`
- `rotate.dom.classList.remove`
- `scale.dom.classList.remove`
- `translate.dom.classList.add`
- `rotate.dom.classList.add`
- `scale.dom.classList.add`

**Internal Comments:**
```
// translate / rotate / scale (x2)
// (x5)
```

<details><summary>Code</summary>

```typescript
function Toolbar( editor ) {

	const signals = editor.signals;
	const strings = editor.strings;

	const container = new UIPanel();
	container.setId( 'toolbar' );

	// translate / rotate / scale

	const translateIcon = document.createElement( 'img' );
	translateIcon.title = strings.getKey( 'toolbar/translate' );
	translateIcon.src = 'images/translate.svg';

	const translate = new UIButton();
	translate.dom.className = 'Button selected';
	translate.dom.appendChild( translateIcon );
	translate.onClick( function () {

		signals.transformModeChanged.dispatch( 'translate' );

	} );
	container.add( translate );

	const rotateIcon = document.createElement( 'img' );
	rotateIcon.title = strings.getKey( 'toolbar/rotate' );
	rotateIcon.src = 'images/rotate.svg';

	const rotate = new UIButton();
	rotate.dom.appendChild( rotateIcon );
	rotate.onClick( function () {

		signals.transformModeChanged.dispatch( 'rotate' );

	} );
	container.add( rotate );

	const scaleIcon = document.createElement( 'img' );
	scaleIcon.title = strings.getKey( 'toolbar/scale' );
	scaleIcon.src = 'images/scale.svg';

	const scale = new UIButton();
	scale.dom.appendChild( scaleIcon );
	scale.onClick( function () {

		signals.transformModeChanged.dispatch( 'scale' );

	} );
	container.add( scale );

	const local = new UICheckbox( false );
	local.dom.title = strings.getKey( 'toolbar/local' );
	local.onChange( function () {

		signals.spaceChanged.dispatch( this.getValue() === true ? 'local' : 'world' );

	} );
	container.add( local );

	//

	signals.transformModeChanged.add( function ( mode ) {

		translate.dom.classList.remove( 'selected' );
		rotate.dom.classList.remove( 'selected' );
		scale.dom.classList.remove( 'selected' );

		switch ( mode ) {

			case 'translate': translate.dom.classList.add( 'selected' ); break;
			case 'rotate': rotate.dom.classList.add( 'selected' ); break;
			case 'scale': scale.dom.classList.add( 'selected' ); break;

		}

	} );

	return container;

}
```
</details>


---