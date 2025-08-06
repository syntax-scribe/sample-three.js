[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BoxLineGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 10 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/geometries/BoxLineGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `three` |
| `Float32BufferAttribute` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `widthHalf` | `number` | let/var | `width / 2` | ✗ |
| `heightHalf` | `number` | let/var | `height / 2` | ✗ |
| `depthHalf` | `number` | let/var | `depth / 2` | ✗ |
| `segmentWidth` | `number` | let/var | `width / widthSegments` | ✗ |
| `segmentHeight` | `number` | let/var | `height / heightSegments` | ✗ |
| `segmentDepth` | `number` | let/var | `depth / depthSegments` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `x` | `number` | let/var | `- widthHalf` | ✗ |
| `y` | `number` | let/var | `- heightHalf` | ✗ |
| `z` | `number` | let/var | `- depthHalf` | ✗ |


---

## Classes

### `BoxLineGeometry`

<details><summary>Class Code</summary>

```ts
class BoxLineGeometry extends BufferGeometry {

	/**
	 * Constructs a new box line geometry.
	 *
	 * @param {number} [width=1] - The width. That is, the length of the edges parallel to the X axis.
	 * @param {number} [height=1] - The height. That is, the length of the edges parallel to the Y axis.
	 * @param {number} [depth=1] - The depth. That is, the length of the edges parallel to the Z axis.
	 * @param {number} [widthSegments=1] - Number of segmented rectangular sections along the width of the sides.
	 * @param {number} [heightSegments=1] - Number of segmented rectangular sections along the height of the sides.
	 * @param {number} [depthSegments=1] - Number of segmented rectangular sections along the depth of the sides.
	 */
	constructor( width = 1, height = 1, depth = 1, widthSegments = 1, heightSegments = 1, depthSegments = 1 ) {

		super();

		widthSegments = Math.floor( widthSegments );
		heightSegments = Math.floor( heightSegments );
		depthSegments = Math.floor( depthSegments );

		const widthHalf = width / 2;
		const heightHalf = height / 2;
		const depthHalf = depth / 2;

		const segmentWidth = width / widthSegments;
		const segmentHeight = height / heightSegments;
		const segmentDepth = depth / depthSegments;

		const vertices = [];

		let x = - widthHalf;
		let y = - heightHalf;
		let z = - depthHalf;

		for ( let i = 0; i <= widthSegments; i ++ ) {

			vertices.push( x, - heightHalf, - depthHalf, x, heightHalf, - depthHalf );
			vertices.push( x, heightHalf, - depthHalf, x, heightHalf, depthHalf );
			vertices.push( x, heightHalf, depthHalf, x, - heightHalf, depthHalf );
			vertices.push( x, - heightHalf, depthHalf, x, - heightHalf, - depthHalf );

			x += segmentWidth;

		}

		for ( let i = 0; i <= heightSegments; i ++ ) {

			vertices.push( - widthHalf, y, - depthHalf, widthHalf, y, - depthHalf );
			vertices.push( widthHalf, y, - depthHalf, widthHalf, y, depthHalf );
			vertices.push( widthHalf, y, depthHalf, - widthHalf, y, depthHalf );
			vertices.push( - widthHalf, y, depthHalf, - widthHalf, y, - depthHalf );

			y += segmentHeight;

		}

		for ( let i = 0; i <= depthSegments; i ++ ) {

			vertices.push( - widthHalf, - heightHalf, z, - widthHalf, heightHalf, z );
			vertices.push( - widthHalf, heightHalf, z, widthHalf, heightHalf, z );
			vertices.push( widthHalf, heightHalf, z, widthHalf, - heightHalf, z );
			vertices.push( widthHalf, - heightHalf, z, - widthHalf, - heightHalf, z );

			z += segmentDepth;

		}

		this.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );

	}

}
```
</details>


---