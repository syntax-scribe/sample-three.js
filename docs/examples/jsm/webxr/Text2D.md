[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Text2D.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/webxr/Text2D.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DoubleSide` | `three` |
| `Mesh` | `three` |
| `MeshBasicMaterial` | `three` |
| `PlaneGeometry` | `three` |
| `Texture` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `metrics` | `any` | let/var | `null` | ✗ |
| `textHeight` | `100` | let/var | `100` | ✗ |
| `textWidth` | `number` | let/var | `metrics.width` | ✗ |
| `texture` | `any` | let/var | `new Texture( canvas )` | ✗ |
| `material` | `any` | let/var | `new MeshBasicMaterial( { color: 0xffffff, side: DoubleSide, map: texture, tra...` | ✗ |
| `geometry` | `any` | let/var | `new PlaneGeometry( ( height * textWidth ) / textHeight, height )` | ✗ |
| `plane` | `any` | let/var | `new Mesh( geometry, material )` | ✗ |


---

## Functions

### `createText(message: string, height: number): Mesh`

**JSDoc:**
```typescript
/**
 * A helper function for creating a simple plane mesh
 * that can be used as a text label. The mesh's material
 * holds a canvas texture that displays the given message.
 *
 * @param {string} message - The message to display.
 * @param {number} height - The labels height.
 * @return {Mesh} The plane mesh representing a text label.
 */
```

**Parameters:**

- **`message`** `string`
- **`height`** `number`

**Returns:** `Mesh`

**Calls:**

- `document.createElement`
- `canvas.getContext`
- `context.measureText`
- `context.fillText`

<details><summary>Code</summary>

```typescript
function createText( message, height ) {

	const canvas = document.createElement( 'canvas' );
	const context = canvas.getContext( '2d' );
	let metrics = null;
	const textHeight = 100;
	context.font = 'normal ' + textHeight + 'px Arial';
	metrics = context.measureText( message );
	const textWidth = metrics.width;
	canvas.width = textWidth;
	canvas.height = textHeight;
	context.font = 'normal ' + textHeight + 'px Arial';
	context.textAlign = 'center';
	context.textBaseline = 'middle';
	context.fillStyle = '#ffffff';
	context.fillText( message, textWidth / 2, textHeight / 2 );

	const texture = new Texture( canvas );
	texture.needsUpdate = true;

	const material = new MeshBasicMaterial( {
		color: 0xffffff,
		side: DoubleSide,
		map: texture,
		transparent: true,
	} );
	const geometry = new PlaneGeometry(
		( height * textWidth ) / textHeight,
		height
	);
	const plane = new Mesh( geometry, material );
	return plane;

}
```
</details>


---