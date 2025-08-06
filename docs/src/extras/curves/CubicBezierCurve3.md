[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CubicBezierCurve3.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/extras/curves/CubicBezierCurve3.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Curve` | `../core/Curve.js` |
| `CubicBezier` | `../core/Interpolations.js` |
| `Vector3` | `../../math/Vector3.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `v0` | `Vector3` | let/var | `this.v0` | ✗ |
| `v1` | `Vector3` | let/var | `this.v1` | ✗ |
| `v2` | `Vector3` | let/var | `this.v2` | ✗ |
| `v3` | `Vector3` | let/var | `this.v3` | ✗ |


---

## Functions

### `CubicBezierCurve3.getPoint(t: number, optionalTarget: Vector3): Vector3`

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
- `CubicBezier (from ../core/Interpolations.js)`

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const v0 = this.v0, v1 = this.v1, v2 = this.v2, v3 = this.v3;

		point.set(
			CubicBezier( t, v0.x, v1.x, v2.x, v3.x ),
			CubicBezier( t, v0.y, v1.y, v2.y, v3.y ),
			CubicBezier( t, v0.z, v1.z, v2.z, v3.z )
		);

		return point;

	}
```
</details>

### `CubicBezierCurve3.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.v0.copy`
- `this.v1.copy`
- `this.v2.copy`
- `this.v3.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.v0.copy( source.v0 );
		this.v1.copy( source.v1 );
		this.v2.copy( source.v2 );
		this.v3.copy( source.v3 );

		return this;

	}
```
</details>

### `CubicBezierCurve3.toJSON(): any`

**Returns:** `any`

**Calls:**

- `super.toJSON`
- `this.v0.toArray`
- `this.v1.toArray`
- `this.v2.toArray`
- `this.v3.toArray`

<details><summary>Code</summary>

```typescript
toJSON() {

		const data = super.toJSON();

		data.v0 = this.v0.toArray();
		data.v1 = this.v1.toArray();
		data.v2 = this.v2.toArray();
		data.v3 = this.v3.toArray();

		return data;

	}
```
</details>

### `CubicBezierCurve3.fromJSON(json: any): this`

**Parameters:**

- **`json`** `any`

**Returns:** `this`

**Calls:**

- `super.fromJSON`
- `this.v0.fromArray`
- `this.v1.fromArray`
- `this.v2.fromArray`
- `this.v3.fromArray`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		super.fromJSON( json );

		this.v0.fromArray( json.v0 );
		this.v1.fromArray( json.v1 );
		this.v2.fromArray( json.v2 );
		this.v3.fromArray( json.v3 );

		return this;

	}
```
</details>


---

## Classes

### `CubicBezierCurve3`

<details><summary>Class Code</summary>

```ts
class CubicBezierCurve3 extends Curve {

	/**
	 * Constructs a new Cubic Bezier curve.
	 *
	 * @param {Vector3} [v0] - The start point.
	 * @param {Vector3} [v1] - The first control point.
	 * @param {Vector3} [v2] - The second control point.
	 * @param {Vector3} [v3] - The end point.
	 */
	constructor( v0 = new Vector3(), v1 = new Vector3(), v2 = new Vector3(), v3 = new Vector3() ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isCubicBezierCurve3 = true;

		this.type = 'CubicBezierCurve3';

		/**
		 * The start point.
		 *
		 * @type {Vector3}
		 */
		this.v0 = v0;

		/**
		 * The first control point.
		 *
		 * @type {Vector3}
		 */
		this.v1 = v1;

		/**
		 * The second control point.
		 *
		 * @type {Vector3}
		 */
		this.v2 = v2;

		/**
		 * The end point.
		 *
		 * @type {Vector3}
		 */
		this.v3 = v3;

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

		const v0 = this.v0, v1 = this.v1, v2 = this.v2, v3 = this.v3;

		point.set(
			CubicBezier( t, v0.x, v1.x, v2.x, v3.x ),
			CubicBezier( t, v0.y, v1.y, v2.y, v3.y ),
			CubicBezier( t, v0.z, v1.z, v2.z, v3.z )
		);

		return point;

	}

	copy( source ) {

		super.copy( source );

		this.v0.copy( source.v0 );
		this.v1.copy( source.v1 );
		this.v2.copy( source.v2 );
		this.v3.copy( source.v3 );

		return this;

	}

	toJSON() {

		const data = super.toJSON();

		data.v0 = this.v0.toArray();
		data.v1 = this.v1.toArray();
		data.v2 = this.v2.toArray();
		data.v3 = this.v3.toArray();

		return data;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.v0.fromArray( json.v0 );
		this.v1.fromArray( json.v1 );
		this.v2.fromArray( json.v2 );
		this.v3.fromArray( json.v3 );

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

		const v0 = this.v0, v1 = this.v1, v2 = this.v2, v3 = this.v3;

		point.set(
			CubicBezier( t, v0.x, v1.x, v2.x, v3.x ),
			CubicBezier( t, v0.y, v1.y, v2.y, v3.y ),
			CubicBezier( t, v0.z, v1.z, v2.z, v3.z )
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
		this.v3.copy( source.v3 );

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
		data.v3 = this.v3.toArray();

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
		this.v3.fromArray( json.v3 );

		return this;

	}
```
</details>


---