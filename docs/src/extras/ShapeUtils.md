[⬅️ Back to Table of Contents](../../index.md)

# 📄 `ShapeUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/extras/ShapeUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Earcut` | `./Earcut.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `n` | `number` | let/var | `contour.length` | ✗ |
| `a` | `number` | let/var | `0.0` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `holeIndices` | `any[]` | let/var | `[]` | ✗ |
| `faces` | `any[]` | let/var | `[]` | ✗ |
| `holeIndex` | `number` | let/var | `contour.length` | ✗ |
| `l` | `any` | let/var | `points.length` | ✗ |


---

## Functions

### `ShapeUtils.area(contour: Vector2[]): number`

**JSDoc:**
```typescript
/**
	 * Calculate area of a ( 2D ) contour polygon.
	 *
	 * @param {Array<Vector2>} contour - An array of 2D points.
	 * @return {number} The area.
	 */
```

**Parameters:**

- **`contour`** `Vector2[]`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
static area( contour ) {

		const n = contour.length;
		let a = 0.0;

		for ( let p = n - 1, q = 0; q < n; p = q ++ ) {

			a += contour[ p ].x * contour[ q ].y - contour[ q ].x * contour[ p ].y;

		}

		return a * 0.5;

	}
```
</details>

### `ShapeUtils.isClockWise(pts: Vector2[]): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given contour uses a clockwise winding order.
	 *
	 * @param {Array<Vector2>} pts - An array of 2D points defining a polygon.
	 * @return {boolean} Whether the given contour uses a clockwise winding order or not.
	 */
```

**Parameters:**

- **`pts`** `Vector2[]`

**Returns:** `boolean`

**Calls:**

- `ShapeUtils.area`

<details><summary>Code</summary>

```typescript
static isClockWise( pts ) {

		return ShapeUtils.area( pts ) < 0;

	}
```
</details>

### `ShapeUtils.triangulateShape(contour: Vector2[], holes: Vector2[][]): number[][]`

**JSDoc:**
```typescript
/**
	 * Triangulates the given shape definition.
	 *
	 * @param {Array<Vector2>} contour - An array of 2D points defining the contour.
	 * @param {Array<Array<Vector2>>} holes - An array that holds arrays of 2D points defining the holes.
	 * @return {Array<Array<number>>} An array that holds for each face definition an array with three indices.
	 */
```

**Parameters:**

- **`contour`** `Vector2[]`
- **`holes`** `Vector2[][]`

**Returns:** `number[][]`

**Calls:**

- `removeDupEndPts`
- `addContour`
- `holes.forEach`
- `holeIndices.push`
- `Earcut.triangulate`
- `faces.push`
- `triangles.slice`

**Internal Comments:**
```
// (x5)
```

<details><summary>Code</summary>

```typescript
static triangulateShape( contour, holes ) {

		const vertices = []; // flat array of vertices like [ x0,y0, x1,y1, x2,y2, ... ]
		const holeIndices = []; // array of hole indices
		const faces = []; // final array of vertex indices like [ [ a,b,d ], [ b,c,d ] ]

		removeDupEndPts( contour );
		addContour( vertices, contour );

		//

		let holeIndex = contour.length;

		holes.forEach( removeDupEndPts );

		for ( let i = 0; i < holes.length; i ++ ) {

			holeIndices.push( holeIndex );
			holeIndex += holes[ i ].length;
			addContour( vertices, holes[ i ] );

		}

		//

		const triangles = Earcut.triangulate( vertices, holeIndices );

		//

		for ( let i = 0; i < triangles.length; i += 3 ) {

			faces.push( triangles.slice( i, i + 3 ) );

		}

		return faces;

	}
```
</details>

### `removeDupEndPts(points: any): void`

**Parameters:**

- **`points`** `any`

**Returns:** `void`

**Calls:**

- `points[ l - 1 ].equals`
- `points.pop`

<details><summary>Code</summary>

```typescript
function removeDupEndPts( points ) {

	const l = points.length;

	if ( l > 2 && points[ l - 1 ].equals( points[ 0 ] ) ) {

		points.pop();

	}

}
```
</details>

### `addContour(vertices: any, contour: any): void`

**Parameters:**

- **`vertices`** `any`
- **`contour`** `any`

**Returns:** `void`

**Calls:**

- `vertices.push`

<details><summary>Code</summary>

```typescript
function addContour( vertices, contour ) {

	for ( let i = 0; i < contour.length; i ++ ) {

		vertices.push( contour[ i ].x );
		vertices.push( contour[ i ].y );

	}

}
```
</details>


---

## Classes

### `ShapeUtils`

<details><summary>Class Code</summary>

```ts
class ShapeUtils {

	/**
	 * Calculate area of a ( 2D ) contour polygon.
	 *
	 * @param {Array<Vector2>} contour - An array of 2D points.
	 * @return {number} The area.
	 */
	static area( contour ) {

		const n = contour.length;
		let a = 0.0;

		for ( let p = n - 1, q = 0; q < n; p = q ++ ) {

			a += contour[ p ].x * contour[ q ].y - contour[ q ].x * contour[ p ].y;

		}

		return a * 0.5;

	}

	/**
	 * Returns `true` if the given contour uses a clockwise winding order.
	 *
	 * @param {Array<Vector2>} pts - An array of 2D points defining a polygon.
	 * @return {boolean} Whether the given contour uses a clockwise winding order or not.
	 */
	static isClockWise( pts ) {

		return ShapeUtils.area( pts ) < 0;

	}

	/**
	 * Triangulates the given shape definition.
	 *
	 * @param {Array<Vector2>} contour - An array of 2D points defining the contour.
	 * @param {Array<Array<Vector2>>} holes - An array that holds arrays of 2D points defining the holes.
	 * @return {Array<Array<number>>} An array that holds for each face definition an array with three indices.
	 */
	static triangulateShape( contour, holes ) {

		const vertices = []; // flat array of vertices like [ x0,y0, x1,y1, x2,y2, ... ]
		const holeIndices = []; // array of hole indices
		const faces = []; // final array of vertex indices like [ [ a,b,d ], [ b,c,d ] ]

		removeDupEndPts( contour );
		addContour( vertices, contour );

		//

		let holeIndex = contour.length;

		holes.forEach( removeDupEndPts );

		for ( let i = 0; i < holes.length; i ++ ) {

			holeIndices.push( holeIndex );
			holeIndex += holes[ i ].length;
			addContour( vertices, holes[ i ] );

		}

		//

		const triangles = Earcut.triangulate( vertices, holeIndices );

		//

		for ( let i = 0; i < triangles.length; i += 3 ) {

			faces.push( triangles.slice( i, i + 3 ) );

		}

		return faces;

	}

}
```
</details>

#### Methods

##### `area(contour: Vector2[]): number`

<details><summary>Code</summary>

```ts
static area( contour ) {

		const n = contour.length;
		let a = 0.0;

		for ( let p = n - 1, q = 0; q < n; p = q ++ ) {

			a += contour[ p ].x * contour[ q ].y - contour[ q ].x * contour[ p ].y;

		}

		return a * 0.5;

	}
```
</details>

##### `isClockWise(pts: Vector2[]): boolean`

<details><summary>Code</summary>

```ts
static isClockWise( pts ) {

		return ShapeUtils.area( pts ) < 0;

	}
```
</details>

##### `triangulateShape(contour: Vector2[], holes: Vector2[][]): number[][]`

<details><summary>Code</summary>

```ts
static triangulateShape( contour, holes ) {

		const vertices = []; // flat array of vertices like [ x0,y0, x1,y1, x2,y2, ... ]
		const holeIndices = []; // array of hole indices
		const faces = []; // final array of vertex indices like [ [ a,b,d ], [ b,c,d ] ]

		removeDupEndPts( contour );
		addContour( vertices, contour );

		//

		let holeIndex = contour.length;

		holes.forEach( removeDupEndPts );

		for ( let i = 0; i < holes.length; i ++ ) {

			holeIndices.push( holeIndex );
			holeIndex += holes[ i ].length;
			addContour( vertices, holes[ i ] );

		}

		//

		const triangles = Earcut.triangulate( vertices, holeIndices );

		//

		for ( let i = 0; i < triangles.length; i += 3 ) {

			faces.push( triangles.slice( i, i + 3 ) );

		}

		return faces;

	}
```
</details>


---