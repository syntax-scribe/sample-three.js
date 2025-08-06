[⬅️ Back to Table of Contents](../../index.md)

# 📄 `GridHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 8 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/helpers/GridHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LineSegments` | `../objects/LineSegments.js` |
| `LineBasicMaterial` | `../materials/LineBasicMaterial.js` |
| `Float32BufferAttribute` | `../core/BufferAttribute.js` |
| `BufferGeometry` | `../core/BufferGeometry.js` |
| `Color` | `../math/Color.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `center` | `number` | let/var | `divisions / 2` | ✗ |
| `step` | `number` | let/var | `size / divisions` | ✗ |
| `halfSize` | `number` | let/var | `size / 2` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `colors` | `any[]` | let/var | `[]` | ✗ |
| `color` | `Color` | let/var | `i === center ? color1 : color2` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `material` | `LineBasicMaterial` | let/var | `new LineBasicMaterial( { vertexColors: true, toneMapped: false } )` | ✗ |


---

## Functions

### `GridHelper.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.geometry.dispose`
- `this.material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}
```
</details>


---

## Classes

### `GridHelper`

<details><summary>Class Code</summary>

```ts
class GridHelper extends LineSegments {

	/**
	 * Constructs a new grid helper.
	 *
	 * @param {number} [size=10] - The size of the grid.
	 * @param {number} [divisions=10] - The number of divisions across the grid.
	 * @param {number|Color|string} [color1=0x444444] - The color of the center line.
	 * @param {number|Color|string} [color2=0x888888] - The color of the lines of the grid.
	 */
	constructor( size = 10, divisions = 10, color1 = 0x444444, color2 = 0x888888 ) {

		color1 = new Color( color1 );
		color2 = new Color( color2 );

		const center = divisions / 2;
		const step = size / divisions;
		const halfSize = size / 2;

		const vertices = [], colors = [];

		for ( let i = 0, j = 0, k = - halfSize; i <= divisions; i ++, k += step ) {

			vertices.push( - halfSize, 0, k, halfSize, 0, k );
			vertices.push( k, 0, - halfSize, k, 0, halfSize );

			const color = i === center ? color1 : color2;

			color.toArray( colors, j ); j += 3;
			color.toArray( colors, j ); j += 3;
			color.toArray( colors, j ); j += 3;
			color.toArray( colors, j ); j += 3;

		}

		const geometry = new BufferGeometry();
		geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
		geometry.setAttribute( 'color', new Float32BufferAttribute( colors, 3 ) );

		const material = new LineBasicMaterial( { vertexColors: true, toneMapped: false } );

		super( geometry, material );

		this.type = 'GridHelper';

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}

}
```
</details>

#### Methods

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}
```
</details>


---