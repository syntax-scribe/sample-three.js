[⬅️ Back to Table of Contents](../../index.md)

# 📄 `IcosahedronGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/geometries/IcosahedronGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `PolyhedronGeometry` | `./PolyhedronGeometry.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `t` | `number` | let/var | `( 1 + Math.sqrt( 5 ) ) / 2` | ✗ |
| `vertices` | `number[]` | let/var | `[ - 1, t, 0, 1, t, 0, - 1, - t, 0, 1, - t, 0, 0, - 1, t, 0, 1, t, 0, - 1, - t...` | ✗ |
| `indices` | `number[]` | let/var | `[ 0, 11, 5, 0, 5, 1, 0, 1, 7, 0, 7, 10, 0, 10, 11, 1, 5, 9, 5, 11, 4, 11, 10,...` | ✗ |


---

## Functions

### `IcosahedronGeometry.fromJSON(data: any): IcosahedronGeometry`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @return {IcosahedronGeometry} A new instance.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `IcosahedronGeometry`

<details><summary>Code</summary>

```typescript
static fromJSON( data ) {

		return new IcosahedronGeometry( data.radius, data.detail );

	}
```
</details>


---

## Classes

### `IcosahedronGeometry`

<details><summary>Class Code</summary>

```ts
class IcosahedronGeometry extends PolyhedronGeometry {

	/**
	 * Constructs a new icosahedron geometry.
	 *
	 * @param {number} [radius=1] - Radius of the icosahedron.
	 * @param {number} [detail=0] - Setting this to a value greater than `0` adds vertices making it no longer a icosahedron.
	 */
	constructor( radius = 1, detail = 0 ) {

		const t = ( 1 + Math.sqrt( 5 ) ) / 2;

		const vertices = [
			- 1, t, 0, 	1, t, 0, 	- 1, - t, 0, 	1, - t, 0,
			0, - 1, t, 	0, 1, t,	0, - 1, - t, 	0, 1, - t,
			t, 0, - 1, 	t, 0, 1, 	- t, 0, - 1, 	- t, 0, 1
		];

		const indices = [
			0, 11, 5, 	0, 5, 1, 	0, 1, 7, 	0, 7, 10, 	0, 10, 11,
			1, 5, 9, 	5, 11, 4,	11, 10, 2,	10, 7, 6,	7, 1, 8,
			3, 9, 4, 	3, 4, 2,	3, 2, 6,	3, 6, 8,	3, 8, 9,
			4, 9, 5, 	2, 4, 11,	6, 2, 10,	8, 6, 7,	9, 8, 1
		];

		super( vertices, indices, radius, detail );

		this.type = 'IcosahedronGeometry';

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
	 * @return {IcosahedronGeometry} A new instance.
	 */
	static fromJSON( data ) {

		return new IcosahedronGeometry( data.radius, data.detail );

	}

}
```
</details>

#### Methods

##### `fromJSON(data: any): IcosahedronGeometry`

<details><summary>Code</summary>

```ts
static fromJSON( data ) {

		return new IcosahedronGeometry( data.radius, data.detail );

	}
```
</details>


---