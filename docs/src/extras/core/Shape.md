[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Shape.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/extras/core/Shape.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Path` | `./Path.js` |
| `generateUUID` | `../../math/MathUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `holesPts` | `any[]` | let/var | `[]` | ✗ |
| `hole` | `any` | let/var | `source.holes[ i ]` | ✗ |
| `hole` | `Path` | let/var | `this.holes[ i ]` | ✗ |
| `hole` | `any` | let/var | `json.holes[ i ]` | ✗ |


---

## Functions

### `Shape.getPointsHoles(divisions: number): Vector2[][]`

**JSDoc:**
```typescript
/**
	 * Returns an array representing each contour of the holes
	 * as a list of 2D points.
	 *
	 * @param {number} divisions - The fineness of the result.
	 * @return {Array<Array<Vector2>>} The holes as a series of 2D points.
	 */
```

**Parameters:**

- **`divisions`** `number`

**Returns:** `Vector2[][]`

**Calls:**

- `this.holes[ i ].getPoints`

<details><summary>Code</summary>

```typescript
getPointsHoles( divisions ) {

		const holesPts = [];

		for ( let i = 0, l = this.holes.length; i < l; i ++ ) {

			holesPts[ i ] = this.holes[ i ].getPoints( divisions );

		}

		return holesPts;

	}
```
</details>

### `Shape.extractPoints(divisions: number): { shape: Vector2[]; holes: Vector2[][]; }`

**JSDoc:**
```typescript
/**
	 * Returns an object that holds contour data for the shape and its holes as
	 * arrays of 2D points.
	 *
	 * @param {number} divisions - The fineness of the result.
	 * @return {{shape:Array<Vector2>,holes:Array<Array<Vector2>>}} An object with contour data.
	 */
```

**Parameters:**

- **`divisions`** `number`

**Returns:** `{ shape: Vector2[]; holes: Vector2[][]; }`

**Calls:**

- `this.getPoints`
- `this.getPointsHoles`

<details><summary>Code</summary>

```typescript
extractPoints( divisions ) {

		return {

			shape: this.getPoints( divisions ),
			holes: this.getPointsHoles( divisions )

		};

	}
```
</details>

### `Shape.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.holes.push`
- `hole.clone`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.holes = [];

		for ( let i = 0, l = source.holes.length; i < l; i ++ ) {

			const hole = source.holes[ i ];

			this.holes.push( hole.clone() );

		}

		return this;

	}
```
</details>

### `Shape.toJSON(): any`

**Returns:** `any`

**Calls:**

- `super.toJSON`
- `data.holes.push`
- `hole.toJSON`

<details><summary>Code</summary>

```typescript
toJSON() {

		const data = super.toJSON();

		data.uuid = this.uuid;
		data.holes = [];

		for ( let i = 0, l = this.holes.length; i < l; i ++ ) {

			const hole = this.holes[ i ];
			data.holes.push( hole.toJSON() );

		}

		return data;

	}
```
</details>

### `Shape.fromJSON(json: any): this`

**Parameters:**

- **`json`** `any`

**Returns:** `this`

**Calls:**

- `super.fromJSON`
- `this.holes.push`
- `new Path().fromJSON`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		super.fromJSON( json );

		this.uuid = json.uuid;
		this.holes = [];

		for ( let i = 0, l = json.holes.length; i < l; i ++ ) {

			const hole = json.holes[ i ];
			this.holes.push( new Path().fromJSON( hole ) );

		}

		return this;

	}
```
</details>


---

## Classes

### `Shape`

<details><summary>Class Code</summary>

```ts
class Shape extends Path {

	/**
	 * Constructs a new shape.
	 *
	 * @param {Array<Vector2>} [points] - An array of 2D points defining the shape.
	 */
	constructor( points ) {

		super( points );

		/**
		 * The UUID of the shape.
		 *
		 * @type {string}
		 * @readonly
		 */
		this.uuid = generateUUID();

		this.type = 'Shape';

		/**
		 * Defines the holes in the shape. Hole definitions must use the
		 * opposite winding order (CW/CCW) than the outer shape.
		 *
		 * @type {Array<Path>}
		 * @readonly
		 */
		this.holes = [];

	}

	/**
	 * Returns an array representing each contour of the holes
	 * as a list of 2D points.
	 *
	 * @param {number} divisions - The fineness of the result.
	 * @return {Array<Array<Vector2>>} The holes as a series of 2D points.
	 */
	getPointsHoles( divisions ) {

		const holesPts = [];

		for ( let i = 0, l = this.holes.length; i < l; i ++ ) {

			holesPts[ i ] = this.holes[ i ].getPoints( divisions );

		}

		return holesPts;

	}

	// get points of shape and holes (keypoints based on segments parameter)

	/**
	 * Returns an object that holds contour data for the shape and its holes as
	 * arrays of 2D points.
	 *
	 * @param {number} divisions - The fineness of the result.
	 * @return {{shape:Array<Vector2>,holes:Array<Array<Vector2>>}} An object with contour data.
	 */
	extractPoints( divisions ) {

		return {

			shape: this.getPoints( divisions ),
			holes: this.getPointsHoles( divisions )

		};

	}

	copy( source ) {

		super.copy( source );

		this.holes = [];

		for ( let i = 0, l = source.holes.length; i < l; i ++ ) {

			const hole = source.holes[ i ];

			this.holes.push( hole.clone() );

		}

		return this;

	}

	toJSON() {

		const data = super.toJSON();

		data.uuid = this.uuid;
		data.holes = [];

		for ( let i = 0, l = this.holes.length; i < l; i ++ ) {

			const hole = this.holes[ i ];
			data.holes.push( hole.toJSON() );

		}

		return data;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.uuid = json.uuid;
		this.holes = [];

		for ( let i = 0, l = json.holes.length; i < l; i ++ ) {

			const hole = json.holes[ i ];
			this.holes.push( new Path().fromJSON( hole ) );

		}

		return this;

	}

}
```
</details>

#### Methods

##### `getPointsHoles(divisions: number): Vector2[][]`

<details><summary>Code</summary>

```ts
getPointsHoles( divisions ) {

		const holesPts = [];

		for ( let i = 0, l = this.holes.length; i < l; i ++ ) {

			holesPts[ i ] = this.holes[ i ].getPoints( divisions );

		}

		return holesPts;

	}
```
</details>

##### `extractPoints(divisions: number): { shape: Vector2[]; holes: Vector2[][]; }`

<details><summary>Code</summary>

```ts
extractPoints( divisions ) {

		return {

			shape: this.getPoints( divisions ),
			holes: this.getPointsHoles( divisions )

		};

	}
```
</details>

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source );

		this.holes = [];

		for ( let i = 0, l = source.holes.length; i < l; i ++ ) {

			const hole = source.holes[ i ];

			this.holes.push( hole.clone() );

		}

		return this;

	}
```
</details>

##### `toJSON(): any`

<details><summary>Code</summary>

```ts
toJSON() {

		const data = super.toJSON();

		data.uuid = this.uuid;
		data.holes = [];

		for ( let i = 0, l = this.holes.length; i < l; i ++ ) {

			const hole = this.holes[ i ];
			data.holes.push( hole.toJSON() );

		}

		return data;

	}
```
</details>

##### `fromJSON(json: any): this`

<details><summary>Code</summary>

```ts
fromJSON( json ) {

		super.fromJSON( json );

		this.uuid = json.uuid;
		this.holes = [];

		for ( let i = 0, l = json.holes.length; i < l; i ++ ) {

			const hole = json.holes[ i ];
			this.holes.push( new Path().fromJSON( hole ) );

		}

		return this;

	}
```
</details>


---