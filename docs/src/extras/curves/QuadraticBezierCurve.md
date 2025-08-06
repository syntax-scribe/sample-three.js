[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `QuadraticBezierCurve.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/extras/curves/QuadraticBezierCurve.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Curve` | `../core/Curve.js` |
| `QuadraticBezier` | `../core/Interpolations.js` |
| `Vector2` | `../../math/Vector2.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `point` | `Vector2` | let/var | `optionalTarget` | ✗ |
| `v0` | `Vector2` | let/var | `this.v0` | ✗ |
| `v1` | `Vector2` | let/var | `this.v1` | ✗ |
| `v2` | `Vector2` | let/var | `this.v2` | ✗ |


---

## Functions

### `QuadraticBezierCurve.getPoint(t: number, optionalTarget: Vector2): Vector2`

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

- `point.set`
- `QuadraticBezier (from ../core/Interpolations.js)`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector2() ) {

		const point = optionalTarget;

		const v0 = this.v0, v1 = this.v1, v2 = this.v2;

		point.set(
			QuadraticBezier( t, v0.x, v1.x, v2.x ),
			QuadraticBezier( t, v0.y, v1.y, v2.y )
		);

		return point;

	}
```
</details>

### `QuadraticBezierCurve.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.v0.copy`
- `this.v1.copy`
- `this.v2.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.v0.copy( source.v0 );
		this.v1.copy( source.v1 );
		this.v2.copy( source.v2 );

		return this;

	}
```
</details>

### `QuadraticBezierCurve.toJSON(): any`

**Returns:** `any`

**Calls:**

- `super.toJSON`
- `this.v0.toArray`
- `this.v1.toArray`
- `this.v2.toArray`

<details><summary>Code</summary>

```typescript
toJSON() {

		const data = super.toJSON();

		data.v0 = this.v0.toArray();
		data.v1 = this.v1.toArray();
		data.v2 = this.v2.toArray();

		return data;

	}
```
</details>

### `QuadraticBezierCurve.fromJSON(json: any): this`

**Parameters:**

- **`json`** `any`

**Returns:** `this`

**Calls:**

- `super.fromJSON`
- `this.v0.fromArray`
- `this.v1.fromArray`
- `this.v2.fromArray`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		super.fromJSON( json );

		this.v0.fromArray( json.v0 );
		this.v1.fromArray( json.v1 );
		this.v2.fromArray( json.v2 );

		return this;

	}
```
</details>


---

## Classes

### `QuadraticBezierCurve`

<details><summary>Class Code</summary>

```ts
class QuadraticBezierCurve extends Curve {

	/**
	 * Constructs a new Quadratic Bezier curve.
	 *
	 * @param {Vector2} [v0] - The start point.
	 * @param {Vector2} [v1] - The control point.
	 * @param {Vector2} [v2] - The end point.
	 */
	constructor( v0 = new Vector2(), v1 = new Vector2(), v2 = new Vector2() ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isQuadraticBezierCurve = true;

		this.type = 'QuadraticBezierCurve';

		/**
		 * The start point.
		 *
		 * @type {Vector2}
		 */
		this.v0 = v0;

		/**
		 * The control point.
		 *
		 * @type {Vector2}
		 */
		this.v1 = v1;

		/**
		 * The end point.
		 *
		 * @type {Vector2}
		 */
		this.v2 = v2;

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

		const v0 = this.v0, v1 = this.v1, v2 = this.v2;

		point.set(
			QuadraticBezier( t, v0.x, v1.x, v2.x ),
			QuadraticBezier( t, v0.y, v1.y, v2.y )
		);

		return point;

	}

	copy( source ) {

		super.copy( source );

		this.v0.copy( source.v0 );
		this.v1.copy( source.v1 );
		this.v2.copy( source.v2 );

		return this;

	}

	toJSON() {

		const data = super.toJSON();

		data.v0 = this.v0.toArray();
		data.v1 = this.v1.toArray();
		data.v2 = this.v2.toArray();

		return data;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.v0.fromArray( json.v0 );
		this.v1.fromArray( json.v1 );
		this.v2.fromArray( json.v2 );

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

		const v0 = this.v0, v1 = this.v1, v2 = this.v2;

		point.set(
			QuadraticBezier( t, v0.x, v1.x, v2.x ),
			QuadraticBezier( t, v0.y, v1.y, v2.y )
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

		this.v0.copy( source.v0 );
		this.v1.copy( source.v1 );
		this.v2.copy( source.v2 );

		return this;

	}
```
</details>

##### `toJSON(): any`

<details><summary>Code</summary>

```ts
toJSON() {

		const data = super.toJSON();

		data.v0 = this.v0.toArray();
		data.v1 = this.v1.toArray();
		data.v2 = this.v2.toArray();

		return data;

	}
```
</details>

##### `fromJSON(json: any): this`

<details><summary>Code</summary>

```ts
fromJSON( json ) {

		super.fromJSON( json );

		this.v0.fromArray( json.v0 );
		this.v1.fromArray( json.v1 );
		this.v2.fromArray( json.v2 );

		return this;

	}
```
</details>


---