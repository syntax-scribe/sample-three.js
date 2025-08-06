[⬅️ Back to Table of Contents](../../index.md)

# 📄 `DodecahedronGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/geometries/DodecahedronGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `PolyhedronGeometry` | `./PolyhedronGeometry.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `t` | `number` | let/var | `( 1 + Math.sqrt( 5 ) ) / 2` | ✗ |
| `r` | `number` | let/var | `1 / t` | ✗ |
| `vertices` | `number[]` | let/var | `[ // (±1, ±1, ±1) - 1, - 1, - 1, - 1, - 1, 1, - 1, 1, - 1, - 1, 1, 1, 1, - 1,...` | ✗ |
| `indices` | `number[]` | let/var | `[ 3, 11, 7, 3, 7, 15, 3, 15, 13, 7, 19, 17, 7, 17, 6, 7, 6, 15, 17, 4, 8, 17,...` | ✗ |


---

## Functions

### `DodecahedronGeometry.fromJSON(data: any): DodecahedronGeometry`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @return {DodecahedronGeometry} A new instance.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `DodecahedronGeometry`

<details><summary>Code</summary>

```typescript
static fromJSON( data ) {

		return new DodecahedronGeometry( data.radius, data.detail );

	}
```
</details>


---

## Classes

### `DodecahedronGeometry`

<details><summary>Class Code</summary>

```ts
class DodecahedronGeometry extends PolyhedronGeometry {

	/**
	 * Constructs a new dodecahedron geometry.
	 *
	 * @param {number} [radius=1] - Radius of the dodecahedron.
	 * @param {number} [detail=0] - Setting this to a value greater than `0` adds vertices making it no longer a dodecahedron.
	 */
	constructor( radius = 1, detail = 0 ) {

		const t = ( 1 + Math.sqrt( 5 ) ) / 2;
		const r = 1 / t;

		const vertices = [

			// (±1, ±1, ±1)
			- 1, - 1, - 1,	- 1, - 1, 1,
			- 1, 1, - 1, - 1, 1, 1,
			1, - 1, - 1, 1, - 1, 1,
			1, 1, - 1, 1, 1, 1,

			// (0, ±1/φ, ±φ)
			0, - r, - t, 0, - r, t,
			0, r, - t, 0, r, t,

			// (±1/φ, ±φ, 0)
			- r, - t, 0, - r, t, 0,
			r, - t, 0, r, t, 0,

			// (±φ, 0, ±1/φ)
			- t, 0, - r, t, 0, - r,
			- t, 0, r, t, 0, r
		];

		const indices = [
			3, 11, 7, 	3, 7, 15, 	3, 15, 13,
			7, 19, 17, 	7, 17, 6, 	7, 6, 15,
			17, 4, 8, 	17, 8, 10, 	17, 10, 6,
			8, 0, 16, 	8, 16, 2, 	8, 2, 10,
			0, 12, 1, 	0, 1, 18, 	0, 18, 16,
			6, 10, 2, 	6, 2, 13, 	6, 13, 15,
			2, 16, 18, 	2, 18, 3, 	2, 3, 13,
			18, 1, 9, 	18, 9, 11, 	18, 11, 3,
			4, 14, 12, 	4, 12, 0, 	4, 0, 8,
			11, 9, 5, 	11, 5, 19, 	11, 19, 7,
			19, 5, 14, 	19, 14, 4, 	19, 4, 17,
			1, 12, 14, 	1, 14, 5, 	1, 5, 9
		];

		super( vertices, indices, radius, detail );

		this.type = 'DodecahedronGeometry';

		/**
		 * Holds the constructor parameters that have been
		 * used to generate the geometry. Any modification
		 * after instantiation does not change the geometry.
		 *
		 * @type {Object}
		 */
		this.parameters = {
			radius: radius,
			detail: detail
		};

	}

	/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @return {DodecahedronGeometry} A new instance.
	 */
	static fromJSON( data ) {

		return new DodecahedronGeometry( data.radius, data.detail );

	}

}
```
</details>

#### Methods

##### `fromJSON(data: any): DodecahedronGeometry`

<details><summary>Code</summary>

```ts
static fromJSON( data ) {

		return new DodecahedronGeometry( data.radius, data.detail );

	}
```
</details>


---