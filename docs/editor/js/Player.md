[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Player.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`editor/js/Player.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UIPanel` | `./libs/ui.js` |
| `APP` | `./libs/app.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `container` | `UIPanel` | let/var | `new UIPanel()` | ✗ |
| `player` | `Player` | let/var | `new APP.Player()` | ✗ |


---

## Functions

### `Player(editor: any): UIPanel`

**Parameters:**

- **`editor`** `any`

**Returns:** `UIPanel`

**Calls:**

- `container.setId`
- `container.setPosition`
- `container.setDisplay`
- `container.dom.appendChild`
- `window.addEventListener`
- `player.setSize`
- `signals.windowResize.add`
- `signals.startPlayer.add`
- `player.load`
- `editor.toJSON`
- `player.play`
- `signals.stopPlayer.add`
- `player.stop`
- `player.dispose`

**Internal Comments:**
```
// (x2)
```

<details><summary>Code</summary>

```typescript
function Player( editor ) {

	const signals = editor.signals;

	const container = new UIPanel();
	container.setId( 'player' );
	container.setPosition( 'absolute' );
	container.setDisplay( 'none' );

	//

	const player = new APP.Player();
	container.dom.appendChild( player.dom );

	window.addEventListener( 'resize', function () {

		player.setSize( container.dom.clientWidth, container.dom.clientHeight );

	} );

	signals.windowResize.add( function () {

		player.setSize( container.dom.clientWidth, container.dom.clientHeight );

	} );

	signals.startPlayer.add( function () {

		container.setDisplay( '' );

		player.load( editor.toJSON() );
		player.setSize( container.dom.clientWidth, container.dom.clientHeight );
		player.play();

	} );

	signals.stopPlayer.add( function () {

		container.setDisplay( 'none' );

		player.stop();
		player.dispose();

	} );

	return container;

}
```
</details>


---