[⬅️ Back to Table of Contents](../../index.md)

# 📄 `OctahedronGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/geometries/OctahedronGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `PolyhedronGeometry` | `./PolyhedronGeometry.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `vertices` | `number[]` | let/var | `[ 1, 0, 0, - 1, 0, 0, 0, 1, 0, 0, - 1, 0, 0, 0, 1, 0, 0, - 1 ]` | ✗ |
| `indices` | `number[]` | let/var | `[ 0, 2, 4, 0, 4, 3, 0, 3, 5, 0, 5, 2, 1, 2, 5, 1, 5, 3, 1, 3, 4, 1, 4, 2 ]` | ✗ |


---

## Functions

### `OctahedronGeometry.fromJSON(data: any): OctahedronGeometry`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @return {OctahedronGeometry} A new instance.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `OctahedronGeometry`

<details><summary>Code</summary>

```typescript
static fromJSON( data ) {

		return new OctahedronGeometry( data.radius, data.detail );

	}
```
</details>


---

## Classes

### `OctahedronGeometry`

<details><summary>Class Code</summary>

```ts
class OctahedronGeometry extends PolyhedronGeometry {

	/**
	 * Constructs a new octahedron geometry.
	 *
	 * @param {number} [radius=1] - Radius of the octahedron.
	 * @param {number} [detail=0] - Setting this to a value greater than `0` adds vertices making it no longer a octahedron.
	 */
	constructor( radius = 1, detail = 0 ) {

		const vertices = [
			1, 0, 0, 	- 1, 0, 0,	0, 1, 0,
			0, - 1, 0, 	0, 0, 1,	0, 0, - 1
		];

		const indices = [
			0, 2, 4,	0, 4, 3,	0, 3, 5,
			0, 5, 2,	1, 2, 5,	1, 5, 3,
			1, 3, 4,	1, 4, 2
		];

		super( vertices, indices, radius, detail );

		this.type = 'OctahedronGeometry';

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
	 * @return {OctahedronGeometry} A new instance.
	 */
	static fromJSON( data ) {

		return new OctahedronGeometry( data.radius, data.detail );

	}

}
```
</details>

#### Methods

##### `fromJSON(data: any): OctahedronGeometry`

<details><summary>Code</summary>

```ts
static fromJSON( data ) {

		return new OctahedronGeometry( data.radius, data.detail );

	}
```
</details>


---