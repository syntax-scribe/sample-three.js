[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sidebar.Object.Animation.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Sidebar.Object.Animation.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIBreak` | `./libs/ui.js` |
| `UIButton` | `./libs/ui.js` |
| `UIDiv` | `./libs/ui.js` |
| `UIText` | `./libs/ui.js` |
| `UINumber` | `./libs/ui.js` |
| `UIRow` | `./libs/ui.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `strings` | `any` | let/var | `editor.strings` | ✗ |
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `mixer` | `any` | let/var | `editor.mixer` | ✗ |
| `container` | `UIRow` | let/var | `new UIRow()` | ✗ |
| `button` | `UIButton` | let/var | `new UIButton( getButtonText( action ) )` | ✗ |
| `animations` | `any` | let/var | `object.animations` | ✗ |
| `container` | `UIDiv` | let/var | `new UIDiv()` | ✗ |
| `animationsList` | `UIDiv` | let/var | `new UIDiv()` | ✗ |
| `mixerTimeScaleRow` | `UIRow` | let/var | `new UIRow()` | ✗ |


---

## Functions

### `SidebarObjectAnimation(editor: any): UIDiv`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIDiv`

**Calls:**

- `action.isRunning`
- `strings.getKey`
- `mixer.clipAction`
- `new UIText( animation.name ).setWidth`
- `container.add`
- `getButtonText`
- `button.onClick`
- `action.stop`
- `action.play`
- `button.setTextContent`
- `signals.objectSelected.add`
- `animationsList.clear`
- `animationsList.add`
- `container.setDisplay`
- `signals.objectRemoved.add`
- `mixer.uncacheRoot`
- `container.setMarginTop`
- `new UIText( strings.getKey( 'sidebar/animations' ) ).setTextTransform`
- `new UINumber( 1 ).setWidth( '60px' ).setRange`
- `mixerTimeScaleNumber.onChange`
- `mixerTimeScaleNumber.getValue`
- `mixerTimeScaleRow.add`
- `new UIText( strings.getKey( 'sidebar/animations/timescale' ) ).setClass`

<details><summary>Code</summary>

```typescript
function SidebarObjectAnimation( editor ) {

	const strings = editor.strings;
	const signals = editor.signals;
	const mixer = editor.mixer;

	function getButtonText( action ) {

		return action.isRunning()
			? strings.getKey( 'sidebar/animations/stop' )
			: strings.getKey( 'sidebar/animations/play' );

	}

	function Animation( animation, object ) {

		const action = mixer.clipAction( animation, object );

		const container = new UIRow();

		const name = new UIText( animation.name ).setWidth( '200px' );
		container.add( name );

		const button = new UIButton( getButtonText( action ) );
		button.onClick( function () {

			action.isRunning() ? action.stop() : action.play();
			button.setTextContent( getButtonText( action ) );

		} );

		container.add( button );

		return container;

	}

	signals.objectSelected.add( function ( object ) {

		if ( object !== null && object.animations.length > 0 ) {

			animationsList.clear();

			const animations = object.animations;

			for ( const animation of animations ) {

				animationsList.add( new Animation( animation, object ) );

			}

			container.setDisplay( '' );

		} else {

			container.setDisplay( 'none' );

		}

	} );

	signals.objectRemoved.add( function ( object ) {

		if ( object !== null && object.animations.length > 0 ) {

			mixer.uncacheRoot( object );

		}

	} );

	const container = new UIDiv();
	container.setMarginTop( '20px' );
	container.setDisplay( 'none' );

	container.add( new UIText( strings.getKey( 'sidebar/animations' ) ).setTextTransform( 'uppercase' ) );
	container.add( new UIBreak() );
	container.add( new UIBreak() );

	const animationsList = new UIDiv();
	container.add( animationsList );

	const mixerTimeScaleRow = new UIRow();
	const mixerTimeScaleNumber = new UINumber( 1 ).setWidth( '60px' ).setRange( - 10, 10 );
	mixerTimeScaleNumber.onChange( function () {

		mixer.timeScale = mixerTimeScaleNumber.getValue();

	} );

	mixerTimeScaleRow.add( new UIText( strings.getKey( 'sidebar/animations/timescale' ) ).setClass( 'Label' ) );
	mixerTimeScaleRow.add( mixerTimeScaleNumber );

	container.add( mixerTimeScaleRow );

	return container;

}
```
</details>

### `getButtonText(action: any): any`

**Parameters:**

- **`action`** `any`

**Returns:** `any`

**Calls:**

- `action.isRunning`
- `strings.getKey`

<details><summary>Code</summary>

```typescript
function getButtonText( action ) {

		return action.isRunning()
			? strings.getKey( 'sidebar/animations/stop' )
			: strings.getKey( 'sidebar/animations/play' );

	}
```
</details>

### `Animation(animation: any, object: any): UIRow`

**Parameters:**

- **`animation`** `any`
- **`object`** `any`

**Returns:** `UIRow`

**Calls:**

- `mixer.clipAction`
- `new UIText( animation.name ).setWidth`
- `container.add`
- `getButtonText`
- `button.onClick`
- `action.isRunning`
- `action.stop`
- `action.play`
- `button.setTextContent`

<details><summary>Code</summary>

```typescript
function Animation( animation, object ) {

		const action = mixer.clipAction( animation, object );

		const container = new UIRow();

		const name = new UIText( animation.name ).setWidth( '200px' );
		container.add( name );

		const button = new UIButton( getButtonText( action ) );
		button.onClick( function () {

			action.isRunning() ? action.stop() : action.play();
			button.setTextContent( getButtonText( action ) );

		} );

		container.add( button );

		return container;

	}
```
</details>


---