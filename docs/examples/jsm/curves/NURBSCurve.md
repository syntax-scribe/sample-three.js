[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NURBSCurve.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/curves/NURBSCurve.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Curve` | `three` |
| `Vector3` | `three` |
| `Vector4` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `knotsLength` | `number` | let/var | `knots ? knots.length - 1 : 0` | ✗ |
| `pointsLength` | `number` | let/var | `controlPoints ? controlPoints.length : 0` | ✗ |
| `point` | `any` | let/var | `controlPoints[ i ]` | ✗ |
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `u` | `number` | let/var | `this.knots[ this.startKnot ] + t * ( this.knots[ this.endKnot ] - this.knots[...` | ✗ |
| `tangent` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `u` | `number` | let/var | `this.knots[ 0 ] + t * ( this.knots[ this.knots.length - 1 ] - this.knots[ 0 ] )` | ✗ |


---

## Functions

### `NURBSCurve.getPoint(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 3D space for the given interpolation factor.
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

- `NURBSUtils.calcBSplinePoint`
- `hpoint.divideScalar`
- `point.set`

**Internal Comments:**
```
// following results in (wx, wy, wz, w) homogeneous point (x2)
// project to 3D space: (wx, wy, wz, w) -> (x, y, z, 1) (x4)
```

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const u = this.knots[ this.startKnot ] + t * ( this.knots[ this.endKnot ] - this.knots[ this.startKnot ] ); // linear mapping t->u

		// following results in (wx, wy, wz, w) homogeneous point
		const hpoint = NURBSUtils.calcBSplinePoint( this.degree, this.knots, this.controlPoints, u );

		if ( hpoint.w !== 1.0 ) {

			// project to 3D space: (wx, wy, wz, w) -> (x, y, z, 1)
			hpoint.divideScalar( hpoint.w );

		}

		return point.set( hpoint.x, hpoint.y, hpoint.z );

	}
```
</details>

### `NURBSCurve.getTangent(t: number, optionalTarget: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Returns a unit vector tangent for the given interpolation factor.
	 *
	 * @param {number} t - The interpolation factor.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The tangent vector.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `NURBSUtils.calcNURBSDerivatives`
- `tangent.copy( ders[ 1 ] ).normalize`

<details><summary>Code</summary>

```typescript
getTangent( t, optionalTarget = new Vector3() ) {

		const tangent = optionalTarget;

		const u = this.knots[ 0 ] + t * ( this.knots[ this.knots.length - 1 ] - this.knots[ 0 ] );
		const ders = NURBSUtils.calcNURBSDerivatives( this.degree, this.knots, this.controlPoints, u, 1 );
		tangent.copy( ders[ 1 ] ).normalize();

		return tangent;

	}
```
</details>

### `NURBSCurve.toJSON(): any`

**Returns:** `any`

**Calls:**

- `super.toJSON`
- `this.controlPoints.map`
- `p.toArray`

<details><summary>Code</summary>

```typescript
toJSON() {

		const data = super.toJSON();

		data.degree = this.degree;
		data.knots = [ ...this.knots ];
		data.controlPoints = this.controlPoints.map( p => p.toArray() );
		data.startKnot = this.startKnot;
		data.endKnot = this.endKnot;

		return data;

	}
```
</details>

### `NURBSCurve.fromJSON(json: any): this`

**Parameters:**

- **`json`** `any`

**Returns:** `this`

**Calls:**

- `super.fromJSON`
- `json.controlPoints.map`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		super.fromJSON( json );

		this.degree = json.degree;
		this.knots = [ ...json.knots ];
		this.controlPoints = json.controlPoints.map( p => new Vector4( p[ 0 ], p[ 1 ], p[ 2 ], p[ 3 ] ) );
		this.startKnot = json.startKnot;
		this.endKnot = json.endKnot;

		return this;

	}
```
</details>


---

## Classes

### `NURBSCurve`

<details><summary>Class Code</summary>

```ts
class NURBSCurve extends Curve {

	/**
	 * Constructs a new NURBS curve.
	 *
	 * @param {number} degree - The NURBS degree.
	 * @param {Array<number>} knots - The knots as a flat array of numbers.
	 * @param {Array<Vector2|Vector3|Vector4>} controlPoints - An array holding control points.
	 * @param {number} [startKnot] - Index of the start knot into the `knots` array.
	 * @param {number} [endKnot] - Index of the end knot into the `knots` array.
	 */
	constructor( degree, knots, controlPoints, startKnot, endKnot ) {

		super();

		const knotsLength = knots ? knots.length - 1 : 0;
		const pointsLength = controlPoints ? controlPoints.length : 0;

		/**
		 * The NURBS degree.
		 *
		 * @type {number}
		 */
		this.degree = degree;

		/**
		 * The knots as a flat array of numbers.
		 *
		 * @type {Array<number>}
		 */
		this.knots = knots;

		/**
		 * An array of control points.
		 *
		 * @type {Array<Vector4>}
		 */
		this.controlPoints = [];

		/**
		 * Index of the start knot into the `knots` array.
		 *
		 * @type {number}
		 */
		this.startKnot = startKnot || 0;

		/**
		 * Index of the end knot into the `knots` array.
		 *
		 * @type {number}
		 */
		this.endKnot = endKnot || knotsLength;

		for ( let i = 0; i < pointsLength; ++ i ) {

			// ensure Vector4 for control points
			const point = controlPoints[ i ];
			this.controlPoints[ i ] = new Vector4( point.x, point.y, point.z, point.w );

		}

	}

	/**
	 * This method returns a vector in 3D space for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The position on the curve.
	 */
	getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const u = this.knots[ this.startKnot ] + t * ( this.knots[ this.endKnot ] - this.knots[ this.startKnot ] ); // linear mapping t->u

		// following results in (wx, wy, wz, w) homogeneous point
		const hpoint = NURBSUtils.calcBSplinePoint( this.degree, this.knots, this.controlPoints, u );

		if ( hpoint.w !== 1.0 ) {

			// project to 3D space: (wx, wy, wz, w) -> (x, y, z, 1)
			hpoint.divideScalar( hpoint.w );

		}

		return point.set( hpoint.x, hpoint.y, hpoint.z );

	}

	/**
	 * Returns a unit vector tangent for the given interpolation factor.
	 *
	 * @param {number} t - The interpolation factor.
	 * @param {Vector3} [optionalTarget] - The optional target vector the result is written to.
	 * @return {Vector3} The tangent vector.
	 */
	getTangent( t, optionalTarget = new Vector3() ) {

		const tangent = optionalTarget;

		const u = this.knots[ 0 ] + t * ( this.knots[ this.knots.length - 1 ] - this.knots[ 0 ] );
		const ders = NURBSUtils.calcNURBSDerivatives( this.degree, this.knots, this.controlPoints, u, 1 );
		tangent.copy( ders[ 1 ] ).normalize();

		return tangent;

	}

	toJSON() {

		const data = super.toJSON();

		data.degree = this.degree;
		data.knots = [ ...this.knots ];
		data.controlPoints = this.controlPoints.map( p => p.toArray() );
		data.startKnot = this.startKnot;
		data.endKnot = this.endKnot;

		return data;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.degree = json.degree;
		this.knots = [ ...json.knots ];
		this.controlPoints = json.controlPoints.map( p => new Vector4( p[ 0 ], p[ 1 ], p[ 2 ], p[ 3 ] ) );
		this.startKnot = json.startKnot;
		this.endKnot = json.endKnot;

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

		const u = this.knots[ this.startKnot ] + t * ( this.knots[ this.endKnot ] - this.knots[ this.startKnot ] ); // linear mapping t->u

		// following results in (wx, wy, wz, w) homogeneous point
		const hpoint = NURBSUtils.calcBSplinePoint( this.degree, this.knots, this.controlPoints, u );

		if ( hpoint.w !== 1.0 ) {

			// project to 3D space: (wx, wy, wz, w) -> (x, y, z, 1)
			hpoint.divideScalar( hpoint.w );

		}

		return point.set( hpoint.x, hpoint.y, hpoint.z );

	}
```
</details>

##### `getTangent(t: number, optionalTarget: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getTangent( t, optionalTarget = new Vector3() ) {

		const tangent = optionalTarget;

		const u = this.knots[ 0 ] + t * ( this.knots[ this.knots.length - 1 ] - this.knots[ 0 ] );
		const ders = NURBSUtils.calcNURBSDerivatives( this.degree, this.knots, this.controlPoints, u, 1 );
		tangent.copy( ders[ 1 ] ).normalize();

		return tangent;

	}
```
</details>

##### `toJSON(): any`

<details><summary>Code</summary>

```ts
toJSON() {

		const data = super.toJSON();

		data.degree = this.degree;
		data.knots = [ ...this.knots ];
		data.controlPoints = this.controlPoints.map( p => p.toArray() );
		data.startKnot = this.startKnot;
		data.endKnot = this.endKnot;

		return data;

	}
```
</details>

##### `fromJSON(json: any): this`

<details><summary>Code</summary>

```ts
fromJSON( json ) {

		super.fromJSON( json );

		this.degree = json.degree;
		this.knots = [ ...json.knots ];
		this.controlPoints = json.controlPoints.map( p => new Vector4( p[ 0 ], p[ 1 ], p[ 2 ], p[ 3 ] ) );
		this.startKnot = json.startKnot;
		this.endKnot = json.endKnot;

		return this;

	}
```
</details>


---