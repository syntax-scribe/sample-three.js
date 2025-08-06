[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SplineCurve.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/extras/curves/SplineCurve.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Curve` | `../core/Curve.js` |
| `CatmullRom` | `../core/Interpolations.js` |
| `Vector2` | `../../math/Vector2.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `point` | `Vector2` | let/var | `optionalTarget` | ✗ |
| `points` | `Vector2[]` | let/var | `this.points` | ✗ |
| `p` | `number` | let/var | `( points.length - 1 ) * t` | ✗ |
| `weight` | `number` | let/var | `p - intPoint` | ✗ |
| `p0` | `Vector2` | let/var | `points[ intPoint === 0 ? intPoint : intPoint - 1 ]` | ✗ |
| `p1` | `Vector2` | let/var | `points[ intPoint ]` | ✗ |
| `p2` | `Vector2` | let/var | `points[ intPoint > points.length - 2 ? points.length - 1 : intPoint + 1 ]` | ✗ |
| `p3` | `Vector2` | let/var | `points[ intPoint > points.length - 3 ? points.length - 1 : intPoint + 2 ]` | ✗ |
| `point` | `any` | let/var | `source.points[ i ]` | ✗ |
| `point` | `Vector2` | let/var | `this.points[ i ]` | ✗ |
| `point` | `any` | let/var | `json.points[ i ]` | ✗ |


---

## Functions

### `SplineCurve.getPoint(t: number, optionalTarget: Vector2): Vector2`

**JSDoc:**
```typescript
/**
	 * Returns a point on the curve.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector2} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector2} The position on the curve.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector2`

**Returns:** `Vector2`

**Calls:**

- `Math.floor`
- `point.set`
- `CatmullRom (from ../core/Interpolations.js)`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector2() ) {

		const point = optionalTarget;

		const points = this.points;
		const p = ( points.length - 1 ) * t;

		const intPoint = Math.floor( p );
		const weight = p - intPoint;

		const p0 = points[ intPoint === 0 ? intPoint : intPoint - 1 ];
		const p1 = points[ intPoint ];
		const p2 = points[ intPoint > points.length - 2 ? points.length - 1 : intPoint + 1 ];
		const p3 = points[ intPoint > points.length - 3 ? points.length - 1 : intPoint + 2 ];

		point.set(
			CatmullRom( weight, p0.x, p1.x, p2.x, p3.x ),
			CatmullRom( weight, p0.y, p1.y, p2.y, p3.y )
		);

		return point;

	}
```
</details>

### `SplineCurve.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.points.push`
- `point.clone`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.points = [];

		for ( let i = 0, l = source.points.length; i < l; i ++ ) {

			const point = source.points[ i ];

			this.points.push( point.clone() );

		}

		return this;

	}
```
</details>

### `SplineCurve.toJSON(): any`

**Returns:** `any`

**Calls:**

- `super.toJSON`
- `data.points.push`
- `point.toArray`

<details><summary>Code</summary>

```typescript
toJSON() {

		const data = super.toJSON();

		data.points = [];

		for ( let i = 0, l = this.points.length; i < l; i ++ ) {

			const point = this.points[ i ];
			data.points.push( point.toArray() );

		}

		return data;

	}
```
</details>

### `SplineCurve.fromJSON(json: any): this`

**Parameters:**

- **`json`** `any`

**Returns:** `this`

**Calls:**

- `super.fromJSON`
- `this.points.push`
- `new Vector2().fromArray`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		super.fromJSON( json );

		this.points = [];

		for ( let i = 0, l = json.points.length; i < l; i ++ ) {

			const point = json.points[ i ];
			this.points.push( new Vector2().fromArray( point ) );

		}

		return this;

	}
```
</details>


---

## Classes

### `SplineCurve`

<details><summary>Class Code</summary>

```ts
class SplineCurve extends Curve {

	/**
	 * Constructs a new 2D spline curve.
	 *
	 * @param {Array<Vector2>} [points] -  An array of 2D points defining the curve.
	 */
	constructor( points = [] ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSplineCurve = true;

		this.type = 'SplineCurve';

		/**
		 * An array of 2D points defining the curve.
		 *
		 * @type {Array<Vector2>}
		 */
		this.points = points;

	}

	/**
	 * Returns a point on the curve.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector2} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector2} The position on the curve.
	 */
	getPoint( t, optionalTarget = new Vector2() ) {

		const point = optionalTarget;

		const points = this.points;
		const p = ( points.length - 1 ) * t;

		const intPoint = Math.floor( p );
		const weight = p - intPoint;

		const p0 = points[ intPoint === 0 ? intPoint : intPoint - 1 ];
		const p1 = points[ intPoint ];
		const p2 = points[ intPoint > points.length - 2 ? points.length - 1 : intPoint + 1 ];
		const p3 = points[ intPoint > points.length - 3 ? points.length - 1 : intPoint + 2 ];

		point.set(
			CatmullRom( weight, p0.x, p1.x, p2.x, p3.x ),
			CatmullRom( weight, p0.y, p1.y, p2.y, p3.y )
		);

		return point;

	}

	copy( source ) {

		super.copy( source );

		this.points = [];

		for ( let i = 0, l = source.points.length; i < l; i ++ ) {

			const point = source.points[ i ];

			this.points.push( point.clone() );

		}

		return this;

	}

	toJSON() {

		const data = super.toJSON();

		data.points = [];

		for ( let i = 0, l = this.points.length; i < l; i ++ ) {

			const point = this.points[ i ];
			data.points.push( point.toArray() );

		}

		return data;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.points = [];

		for ( let i = 0, l = json.points.length; i < l; i ++ ) {

			const point = json.points[ i ];
			this.points.push( new Vector2().fromArray( point ) );

		}

		return this;

	}

}
```
</details>

#### Methods

##### `getPoint(t: number, optionalTarget: Vector2): Vector2`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector2() ) {

		const point = optionalTarget;

		const points = this.points;
		const p = ( points.length - 1 ) * t;

		const intPoint = Math.floor( p );
		const weight = p - intPoint;

		const p0 = points[ intPoint === 0 ? intPoint : intPoint - 1 ];
		const p1 = points[ intPoint ];
		const p2 = points[ intPoint > points.length - 2 ? points.length - 1 : intPoint + 1 ];
		const p3 = points[ intPoint > points.length - 3 ? points.length - 1 : intPoint + 2 ];

		point.set(
			CatmullRom( weight, p0.x, p1.x, p2.x, p3.x ),
			CatmullRom( weight, p0.y, p1.y, p2.y, p3.y )
		);

		return point;

	}
```
</details>

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source );

		this.points = [];

		for ( let i = 0, l = source.points.length; i < l; i ++ ) {

			const point = source.points[ i ];

			this.points.push( point.clone() );

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

		data.points = [];

		for ( let i = 0, l = this.points.length; i < l; i ++ ) {

			const point = this.points[ i ];
			data.points.push( point.toArray() );

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

		this.points = [];

		for ( let i = 0, l = json.points.length; i < l; i ++ ) {

			const point = json.points[ i ];
			this.points.push( new Vector2().fromArray( point ) );

		}

		return this;

	}
```
</details>


---