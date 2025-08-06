[⬅️ Back to Table of Contents](../../index.md)

# 📄 `PolarGridHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 13 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/helpers/PolarGridHelper.js`**

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
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `colors` | `any[]` | let/var | `[]` | ✗ |
| `v` | `number` | let/var | `( i / sectors ) * ( Math.PI * 2 )` | ✗ |
| `x` | `number` | let/var | `Math.sin( v ) * radius` | ✗ |
| `z` | `number` | let/var | `Math.cos( v ) * radius` | ✗ |
| `color` | `Color` | let/var | `( i & 1 ) ? color1 : color2` | ✗ |
| `color` | `Color` | let/var | `( i & 1 ) ? color1 : color2` | ✗ |
| `r` | `number` | let/var | `radius - ( radius / rings * i )` | ✗ |
| `v` | `number` | let/var | `( j / divisions ) * ( Math.PI * 2 )` | ✗ |
| `x` | `number` | let/var | `Math.sin( v ) * r` | ✗ |
| `z` | `number` | let/var | `Math.cos( v ) * r` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `material` | `LineBasicMaterial` | let/var | `new LineBasicMaterial( { vertexColors: true, toneMapped: false } )` | ✗ |


---

## Functions

### `PolarGridHelper.dispose(): void`

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

### `PolarGridHelper`

<details><summary>Class Code</summary>

```ts
class PolarGridHelper extends LineSegments {

	/**
	 * Constructs a new polar grid helper.
	 *
	 * @param {number} [radius=10] - The radius of the polar grid. This can be any positive number.
	 * @param {number} [sectors=16] - The number of sectors the grid will be divided into. This can be any positive integer.
	 * @param {number} [rings=16] - The number of rings. This can be any positive integer.
	 * @param {number} [divisions=64] - The number of line segments used for each circle. This can be any positive integer.
	 * @param {number|Color|string} [color1=0x444444] - The first color used for grid elements.
	 * @param {number|Color|string} [color2=0x888888] -  The second color used for grid elements.
	 */
	constructor( radius = 10, sectors = 16, rings = 8, divisions = 64, color1 = 0x444444, color2 = 0x888888 ) {

		color1 = new Color( color1 );
		color2 = new Color( color2 );

		const vertices = [];
		const colors = [];

		// create the sectors

		if ( sectors > 1 ) {

			for ( let i = 0; i < sectors; i ++ ) {

				const v = ( i / sectors ) * ( Math.PI * 2 );

				const x = Math.sin( v ) * radius;
				const z = Math.cos( v ) * radius;

				vertices.push( 0, 0, 0 );
				vertices.push( x, 0, z );

				const color = ( i & 1 ) ? color1 : color2;

				colors.push( color.r, color.g, color.b );
				colors.push( color.r, color.g, color.b );

			}

		}

		// create the rings

		for ( let i = 0; i < rings; i ++ ) {

			const color = ( i & 1 ) ? color1 : color2;

			const r = radius - ( radius / rings * i );

			for ( let j = 0; j < divisions; j ++ ) {

				// first vertex

				let v = ( j / divisions ) * ( Math.PI * 2 );

				let x = Math.sin( v ) * r;
				let z = Math.cos( v ) * r;

				vertices.push( x, 0, z );
				colors.push( color.r, color.g, color.b );

				// second vertex

				v = ( ( j + 1 ) / divisions ) * ( Math.PI * 2 );

				x = Math.sin( v ) * r;
				z = Math.cos( v ) * r;

				vertices.push( x, 0, z );
				colors.push( color.r, color.g, color.b );

			}

		}

		const geometry = new BufferGeometry();
		geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
		geometry.setAttribute( 'color', new Float32BufferAttribute( colors, 3 ) );

		const material = new LineBasicMaterial( { vertexColors: true, toneMapped: false } );

		super( geometry, material );

		this.type = 'PolarGridHelper';

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