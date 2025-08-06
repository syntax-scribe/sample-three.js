[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `FlakesTexture.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/textures/FlakesTexture.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `x` | `number` | let/var | `Math.random() * width` | ✗ |
| `y` | `number` | let/var | `Math.random() * height` | ✗ |
| `r` | `number` | let/var | `Math.random() * 3 + 3` | ✗ |
| `nx` | `number` | let/var | `Math.random() * 2 - 1` | ✗ |
| `ny` | `number` | let/var | `Math.random() * 2 - 1` | ✗ |
| `nz` | `number` | let/var | `1.5` | ✗ |


---

## Classes

### `FlakesTexture`

<details><summary>Class Code</summary>

```ts
class FlakesTexture {

	/**
	 * Generates a new flakes texture image. The result is a canvas
	 * that can be used as an input for {@link CanvasTexture}.
	 *
	 * @param {number} [width=512] - The width of the image.
	 * @param {number} [height=512] - The height of the image.
	 * @return {HTMLCanvasElement} The generated image.
	 */
	constructor( width = 512, height = 512 ) {

		const canvas = document.createElement( 'canvas' );
		canvas.width = width;
		canvas.height = height;

		const context = canvas.getContext( '2d' );
		context.fillStyle = 'rgb(127,127,255)';
		context.fillRect( 0, 0, width, height );

		for ( let i = 0; i < 4000; i ++ ) {

			const x = Math.random() * width;
			const y = Math.random() * height;
			const r = Math.random() * 3 + 3;

			let nx = Math.random() * 2 - 1;
			let ny = Math.random() * 2 - 1;
			let nz = 1.5;

			const l = Math.sqrt( nx * nx + ny * ny + nz * nz );

			nx /= l; ny /= l; nz /= l;

			context.fillStyle = 'rgb(' + ( nx * 127 + 127 ) + ',' + ( ny * 127 + 127 ) + ',' + ( nz * 255 ) + ')';
			context.beginPath();
			context.arc( x, y, r, 0, Math.PI * 2 );
			context.fill();

		}

		return canvas;

	}

}
```
</details>


---