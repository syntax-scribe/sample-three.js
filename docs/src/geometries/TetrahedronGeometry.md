[⬅️ Back to Table of Contents](../../index.md)

# 📄 `TetrahedronGeometry.js`

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
📂 **`src/geometries/TetrahedronGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `PolyhedronGeometry` | `./PolyhedronGeometry.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `vertices` | `number[]` | let/var | `[ 1, 1, 1, - 1, - 1, 1, - 1, 1, - 1, 1, - 1, - 1 ]` | ✗ |
| `indices` | `number[]` | let/var | `[ 2, 1, 0, 0, 3, 2, 1, 3, 0, 2, 3, 1 ]` | ✗ |


---

## Functions

### `TetrahedronGeometry.fromJSON(data: any): TetrahedronGeometry`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @return {TetrahedronGeometry} A new instance.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `TetrahedronGeometry`

<details><summary>Code</summary>

```typescript
static fromJSON( data ) {

		return new TetrahedronGeometry( data.radius, data.detail );

	}
```
</details>


---

## Classes

### `TetrahedronGeometry`

<details><summary>Class Code</summary>

```ts
class TetrahedronGeometry extends PolyhedronGeometry {

	/**
	 * Constructs a new tetrahedron geometry.
	 *
	 * @param {number} [radius=1] - Radius of the tetrahedron.
	 * @param {number} [detail=0] - Setting this to a value greater than `0` adds vertices making it no longer a tetrahedron.
	 */
	constructor( radius = 1, detail = 0 ) {

		const vertices = [
			1, 1, 1, 	- 1, - 1, 1, 	- 1, 1, - 1, 	1, - 1, - 1
		];

		const indices = [
			2, 1, 0, 	0, 3, 2,	1, 3, 0,	2, 3, 1
		];

		super( vertices, indices, radius, detail );

		this.type = 'TetrahedronGeometry';

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
	 * @return {TetrahedronGeometry} A new instance.
	 */
	static fromJSON( data ) {

		return new TetrahedronGeometry( data.radius, data.detail );

	}

}
```
</details>

#### Methods

##### `fromJSON(data: any): TetrahedronGeometry`

<details><summary>Code</summary>

```ts
static fromJSON( data ) {

		return new TetrahedronGeometry( data.radius, data.detail );

	}
```
</details>


---