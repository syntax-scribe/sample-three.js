[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `threejs-utils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/examples/resources/threejs-utils.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `width` | `number` | let/var | `canvas.clientWidth * multiplier \| 0` | ✗ |
| `height` | `number` | let/var | `canvas.clientHeight * multiplier \| 0` | ✗ |


---

## Functions

### `resizeCanvasToDisplaySize(canvas: HTMLCanvasElement, multiplier: number): boolean`

**JSDoc:**
```typescript
/**
   * Resize a canvas to match the size its displayed.
   * @param {HTMLCanvasElement} canvas The canvas to resize.
   * @param {number} [multiplier] amount to multiply by.
   *    Pass in window.devicePixelRatio for native pixels.
   * @return {boolean} true if the canvas was resized.
   * @memberOf module:webgl-utils
   */
```

**Parameters:**

- **`canvas`** `HTMLCanvasElement`
- **`multiplier`** `number`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function resizeCanvasToDisplaySize( canvas, multiplier ) {

		multiplier = multiplier || 1;
		const width = canvas.clientWidth * multiplier | 0;
		const height = canvas.clientHeight * multiplier | 0;
		if ( canvas.width !== width || canvas.height !== height ) {

			canvas.width = width;
			canvas.height = height;
			return true;

		}

		return false;

	}
```
</details>


---