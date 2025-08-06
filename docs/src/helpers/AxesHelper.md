[⬅️ Back to Table of Contents](../../index.md)

# 📄 `AxesHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/helpers/AxesHelper.js`**

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
| `vertices` | `number[]` | let/var | `[ 0, 0, 0, size, 0, 0, 0, 0, 0, 0, size, 0, 0, 0, 0, 0, 0, size ]` | ✗ |
| `colors` | `number[]` | let/var | `[ 1, 0, 0, 1, 0.6, 0, 0, 1, 0, 0.6, 1, 0, 0, 0, 1, 0, 0.6, 1 ]` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `material` | `LineBasicMaterial` | let/var | `new LineBasicMaterial( { vertexColors: true, toneMapped: false } )` | ✗ |
| `color` | `Color` | let/var | `new Color()` | ✗ |
| `array` | `any` | let/var | `this.geometry.attributes.color.array` | ✗ |


---

## Functions

### `AxesHelper.setColors(xAxisColor: string | number | Color, yAxisColor: string | number | Color, zAxisColor: string | number | Color): AxesHelper`

**JSDoc:**
```typescript
/**
	 * Defines the colors of the axes helper.
	 *
	 * @param {number|Color|string} xAxisColor - The color for the x axis.
	 * @param {number|Color|string} yAxisColor - The color for the y axis.
	 * @param {number|Color|string} zAxisColor - The color for the z axis.
	 * @return {AxesHelper} A reference to this axes helper.
	 */
```

**Parameters:**

- **`xAxisColor`** `string | number | Color`
- **`yAxisColor`** `string | number | Color`
- **`zAxisColor`** `string | number | Color`

**Returns:** `AxesHelper`

**Calls:**

- `color.set`
- `color.toArray`

<details><summary>Code</summary>

```typescript
setColors( xAxisColor, yAxisColor, zAxisColor ) {

		const color = new Color();
		const array = this.geometry.attributes.color.array;

		color.set( xAxisColor );
		color.toArray( array, 0 );
		color.toArray( array, 3 );

		color.set( yAxisColor );
		color.toArray( array, 6 );
		color.toArray( array, 9 );

		color.set( zAxisColor );
		color.toArray( array, 12 );
		color.toArray( array, 15 );

		this.geometry.attributes.color.needsUpdate = true;

		return this;

	}
```
</details>

### `AxesHelper.dispose(): void`

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

### `AxesHelper`

<details><summary>Class Code</summary>

```ts
class AxesHelper extends LineSegments {

	/**
	 * Constructs a new axes helper.
	 *
	 * @param {number} [size=1] - Size of the lines representing the axes.
	 */
	constructor( size = 1 ) {

		const vertices = [
			0, 0, 0,	size, 0, 0,
			0, 0, 0,	0, size, 0,
			0, 0, 0,	0, 0, size
		];

		const colors = [
			1, 0, 0,	1, 0.6, 0,
			0, 1, 0,	0.6, 1, 0,
			0, 0, 1,	0, 0.6, 1
		];

		const geometry = new BufferGeometry();
		geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
		geometry.setAttribute( 'color', new Float32BufferAttribute( colors, 3 ) );

		const material = new LineBasicMaterial( { vertexColors: true, toneMapped: false } );

		super( geometry, material );

		this.type = 'AxesHelper';

	}

	/**
	 * Defines the colors of the axes helper.
	 *
	 * @param {number|Color|string} xAxisColor - The color for the x axis.
	 * @param {number|Color|string} yAxisColor - The color for the y axis.
	 * @param {number|Color|string} zAxisColor - The color for the z axis.
	 * @return {AxesHelper} A reference to this axes helper.
	 */
	setColors( xAxisColor, yAxisColor, zAxisColor ) {

		const color = new Color();
		const array = this.geometry.attributes.color.array;

		color.set( xAxisColor );
		color.toArray( array, 0 );
		color.toArray( array, 3 );

		color.set( yAxisColor );
		color.toArray( array, 6 );
		color.toArray( array, 9 );

		color.set( zAxisColor );
		color.toArray( array, 12 );
		color.toArray( array, 15 );

		this.geometry.attributes.color.needsUpdate = true;

		return this;

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

##### `setColors(xAxisColor: string | number | Color, yAxisColor: string | number | Color, zAxisColor: string | number | Color): AxesHelper`

<details><summary>Code</summary>

```ts
setColors( xAxisColor, yAxisColor, zAxisColor ) {

		const color = new Color();
		const array = this.geometry.attributes.color.array;

		color.set( xAxisColor );
		color.toArray( array, 0 );
		color.toArray( array, 3 );

		color.set( yAxisColor );
		color.toArray( array, 6 );
		color.toArray( array, 9 );

		color.set( zAxisColor );
		color.toArray( array, 12 );
		color.toArray( array, 15 );

		this.geometry.attributes.color.needsUpdate = true;

		return this;

	}
```
</details>

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