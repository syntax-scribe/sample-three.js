[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `QuadraticBezierCurve3.js`

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
📂 **`src/extras/curves/QuadraticBezierCurve3.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Curve` | `../core/Curve.js` |
| `QuadraticBezier` | `../core/Interpolations.js` |
| `Vector3` | `../../math/Vector3.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `v0` | `Vector3` | let/var | `this.v0` | ✗ |
| `v1` | `Vector3` | let/var | `this.v1` | ✗ |
| `v2` | `Vector3` | let/var | `this.v2` | ✗ |


---

## Functions

### `QuadraticBezierCurve3.getPoint(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Returns a point on the curve.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `point.set`
- `QuadraticBezier (from ../core/Interpolations.js)`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const v0 = this.v0, v1 = this.v1, v2 = this.v2;

		point.set(
			QuadraticBezier( t, v0.x, v1.x, v2.x ),
			QuadraticBezier( t, v0.y, v1.y, v2.y ),
			QuadraticBezier( t, v0.z, v1.z, v2.z )
		);

		return point;

	}
```
</details>

### `QuadraticBezierCurve3.copy(source: any): this`

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

### `QuadraticBezierCurve3.toJSON(): any`

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

### `QuadraticBezierCurve3.fromJSON(json: any): this`

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

### `QuadraticBezierCurve3`

<details><summary>Class Code</summary>

```ts
class QuadraticBezierCurve3 extends Curve {

	/**
	 * Constructs a new Quadratic Bezier curve.
	 *
	 * @param {Vector3} [v0] - The start point.
	 * @param {Vector3} [v1] - The control point.
	 * @param {Vector3} [v2] - The end point.
	 */
	constructor( v0 = new Vector3(), v1 = new Vector3(), v2 = new Vector3() ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isQuadraticBezierCurve3 = true;

		this.type = 'QuadraticBezierCurve3';

		/**
		 * The start point.
		 *
		 * @type {Vector3}
		 */
		this.v0 = v0;

		/**
		 * The control point.
		 *
		 * @type {Vector3}
		 */
		this.v1 = v1;

		/**
		 * The end point.
		 *
		 * @type {Vector3}
		 */
		this.v2 = v2;

	}

	/**
	 * Returns a point on the curve.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
	getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const v0 = this.v0, v1 = this.v1, v2 = this.v2;

		point.set(
			QuadraticBezier( t, v0.x, v1.x, v2.x ),
			QuadraticBezier( t, v0.y, v1.y, v2.y ),
			QuadraticBezier( t, v0.z, v1.z, v2.z )
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

##### `getPoint(t: number, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const v0 = this.v0, v1 = this.v1, v2 = this.v2;

		point.set(
			QuadraticBezier( t, v0.x, v1.x, v2.x ),
			QuadraticBezier( t, v0.y, v1.y, v2.y ),
			QuadraticBezier( t, v0.z, v1.z, v2.z )
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