[⬅️ Back to Table of Contents](../../index.md)

# 📄 `PlaneGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 16 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/geometries/PlaneGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `../core/BufferGeometry.js` |
| `Float32BufferAttribute` | `../core/BufferAttribute.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `width_half` | `number` | let/var | `width / 2` | ✗ |
| `height_half` | `number` | let/var | `height / 2` | ✗ |
| `gridX1` | `number` | let/var | `gridX + 1` | ✗ |
| `gridY1` | `number` | let/var | `gridY + 1` | ✗ |
| `segment_width` | `number` | let/var | `width / gridX` | ✗ |
| `segment_height` | `number` | let/var | `height / gridY` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `uvs` | `any[]` | let/var | `[]` | ✗ |
| `y` | `number` | let/var | `iy * segment_height - height_half` | ✗ |
| `x` | `number` | let/var | `ix * segment_width - width_half` | ✗ |
| `a` | `number` | let/var | `ix + gridX1 * iy` | ✗ |
| `b` | `number` | let/var | `ix + gridX1 * ( iy + 1 )` | ✗ |
| `c` | `number` | let/var | `( ix + 1 ) + gridX1 * ( iy + 1 )` | ✗ |
| `d` | `number` | let/var | `( ix + 1 ) + gridX1 * iy` | ✗ |


---

## Functions

### `PlaneGeometry.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `Object.assign`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.parameters = Object.assign( {}, source.parameters );

		return this;

	}
```
</details>

### `PlaneGeometry.fromJSON(data: any): PlaneGeometry`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @return {PlaneGeometry} A new instance.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `PlaneGeometry`

<details><summary>Code</summary>

```typescript
static fromJSON( data ) {

		return new PlaneGeometry( data.width, data.height, data.widthSegments, data.heightSegments );

	}
```
</details>


---

## Classes

### `PlaneGeometry`

<details><summary>Class Code</summary>

```ts
class PlaneGeometry extends BufferGeometry {

	/**
	 * Constructs a new plane geometry.
	 *
	 * @param {number} [width=1] - The width along the X axis.
	 * @param {number} [height=1] - The height along the Y axis
	 * @param {number} [widthSegments=1] - The number of segments along the X axis.
	 * @param {number} [heightSegments=1] - The number of segments along the Y axis.
	 */
	constructor( width = 1, height = 1, widthSegments = 1, heightSegments = 1 ) {

		super();

		this.type = 'PlaneGeometry';

		/**
		 * Holds the constructor parameters that have been
		 * used to generate the geometry. Any modification
		 * after instantiation does not change the geometry.
		 *
		 * @type {Object}
		 */
		this.parameters = {
			width: width,
			height: height,
			widthSegments: widthSegments,
			heightSegments: heightSegments
		};

		const width_half = width / 2;
		const height_half = height / 2;

		const gridX = Math.floor( widthSegments );
		const gridY = Math.floor( heightSegments );

		const gridX1 = gridX + 1;
		const gridY1 = gridY + 1;

		const segment_width = width / gridX;
		const segment_height = height / gridY;

		//

		const indices = [];
		const vertices = [];
		const normals = [];
		const uvs = [];

		for ( let iy = 0; iy < gridY1; iy ++ ) {

			const y = iy * segment_height - height_half;

			for ( let ix = 0; ix < gridX1; ix ++ ) {

				const x = ix * segment_width - width_half;

				vertices.push( x, - y, 0 );

				normals.push( 0, 0, 1 );

				uvs.push( ix / gridX );
				uvs.push( 1 - ( iy / gridY ) );

			}

		}

		for ( let iy = 0; iy < gridY; iy ++ ) {

			for ( let ix = 0; ix < gridX; ix ++ ) {

				const a = ix + gridX1 * iy;
				const b = ix + gridX1 * ( iy + 1 );
				const c = ( ix + 1 ) + gridX1 * ( iy + 1 );
				const d = ( ix + 1 ) + gridX1 * iy;

				indices.push( a, b, d );
				indices.push( b, c, d );

			}

		}

		this.setIndex( indices );
		this.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
		this.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );
		this.setAttribute( 'uv', new Float32BufferAttribute( uvs, 2 ) );

	}

	copy( source ) {

		super.copy( source );

		this.parameters = Object.assign( {}, source.parameters );

		return this;

	}

	/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @return {PlaneGeometry} A new instance.
	 */
	static fromJSON( data ) {

		return new PlaneGeometry( data.width, data.height, data.widthSegments, data.heightSegments );

	}

}
```
</details>

#### Methods

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source );

		this.parameters = Object.assign( {}, source.parameters );

		return this;

	}
```
</details>

##### `fromJSON(data: any): PlaneGeometry`

<details><summary>Code</summary>

```ts
static fromJSON( data ) {

		return new PlaneGeometry( data.width, data.height, data.widthSegments, data.heightSegments );

	}
```
</details>


---