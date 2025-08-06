[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Earcut.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/extras/Earcut.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `earcut` | `./lib/earcut.js` |


---

## Functions

### `Earcut.triangulate(data: number[], holeIndices: number[], dim: number): number[]`

**JSDoc:**
```typescript
/**
	 * Triangulates the given shape definition by returning an array of triangles.
	 *
	 * @param {Array<number>} data - An array with 2D points.
	 * @param {Array<number>} holeIndices - An array with indices defining holes.
	 * @param {number} [dim=2] - The number of coordinates per vertex in the input array.
	 * @return {Array<number>} An array representing the triangulated faces. Each face is defined by three consecutive numbers
	 * representing vertex indices.
	 */
```

**Parameters:**

- **`data`** `number[]`
- **`holeIndices`** `number[]`
- **`dim`** `number`

**Returns:** `number[]`

**Calls:**

- `earcut (from ./lib/earcut.js)`

<details><summary>Code</summary>

```typescript
static triangulate( data, holeIndices, dim = 2 ) {

		return earcut( data, holeIndices, dim );

	}
```
</details>


---

## Classes

### `Earcut`

<details><summary>Class Code</summary>

```ts
class Earcut {

	/**
	 * Triangulates the given shape definition by returning an array of triangles.
	 *
	 * @param {Array<number>} data - An array with 2D points.
	 * @param {Array<number>} holeIndices - An array with indices defining holes.
	 * @param {number} [dim=2] - The number of coordinates per vertex in the input array.
	 * @return {Array<number>} An array representing the triangulated faces. Each face is defined by three consecutive numbers
	 * representing vertex indices.
	 */
	static triangulate( data, holeIndices, dim = 2 ) {

		return earcut( data, holeIndices, dim );

	}

}
```
</details>

#### Methods

##### `triangulate(data: number[], holeIndices: number[], dim: number): number[]`

<details><summary>Code</summary>

```ts
static triangulate( data, holeIndices, dim = 2 ) {

		return earcut( data, holeIndices, dim );

	}
```
</details>


---