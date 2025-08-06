[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CatmullRomCurve3.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 12 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 25 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/extras/curves/CatmullRomCurve3.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `../../math/Vector3.js` |
| `Curve` | `../core/Curve.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `c0` | `number` | let/var | `0` | ✗ |
| `c1` | `number` | let/var | `0` | ✗ |
| `c2` | `number` | let/var | `0` | ✗ |
| `c3` | `number` | let/var | `0` | ✗ |
| `t1` | `number` | let/var | `( x1 - x0 ) / dt0 - ( x2 - x0 ) / ( dt0 + dt1 ) + ( x2 - x1 ) / dt1` | ✗ |
| `t2` | `number` | let/var | `( x2 - x1 ) / dt1 - ( x3 - x1 ) / ( dt1 + dt2 ) + ( x3 - x2 ) / dt2` | ✗ |
| `t2` | `number` | let/var | `t * t` | ✗ |
| `t3` | `number` | let/var | `t2 * t` | ✗ |
| `tmp` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `px` | `any` | let/var | `new CubicPoly()` | ✗ |
| `py` | `any` | let/var | `new CubicPoly()` | ✗ |
| `pz` | `any` | let/var | `new CubicPoly()` | ✗ |
| `point` | `Vector3` | let/var | `optionalTarget` | ✗ |
| `points` | `Vector3[]` | let/var | `this.points` | ✗ |
| `l` | `number` | let/var | `points.length` | ✗ |
| `p` | `number` | let/var | `( l - ( this.closed ? 0 : 1 ) ) * t` | ✗ |
| `weight` | `number` | let/var | `p - intPoint` | ✗ |
| `p0` | `any` | let/var | `*not shown*` | ✗ |
| `p3` | `any` | let/var | `*not shown*` | ✗ |
| `p1` | `Vector3` | let/var | `points[ intPoint % l ]` | ✗ |
| `p2` | `Vector3` | let/var | `points[ ( intPoint + 1 ) % l ]` | ✗ |
| `pow` | `0.5 \| 0.25` | let/var | `this.curveType === 'chordal' ? 0.5 : 0.25` | ✗ |
| `point` | `any` | let/var | `source.points[ i ]` | ✗ |
| `point` | `Vector3` | let/var | `this.points[ i ]` | ✗ |
| `point` | `any` | let/var | `json.points[ i ]` | ✗ |


---

## Functions

### `CubicPoly(): { initCatmullRom: (x0: any, x1: any, x2: any, x3: any, tension: any) => void; initNonuniformCatmullRom: (x0: any, x1: any, x2: any, x3: any, dt0: any, dt1: any, dt2: any) => void; calc: (t: any) => number; }`

**Returns:** `{ initCatmullRom: (x0: any, x1: any, x2: any, x3: any, tension: any) => void; initNonuniformCatmullRom: (x0: any, x1: any, x2: any, x3: any, dt0: any, dt1: any, dt2: any) => void; calc: (t: any) => number; }`

**Calls:**

- `init`

**Internal Comments:**
```
/**
	 * Centripetal CatmullRom Curve - which is useful for avoiding
	* cusps and self-intersections in non-uniform catmull rom curves.
	* http://www.cemyuksel.com/research/catmullrom_param/catmullrom.pdf
	*
	* curve.type accepts centripetal(default), chordal and catmullrom
	* curve.tension is used for catmullrom which defaults to 0.5
	*/ (x2)
/*
	Based on an optimized c++ solution in
	- http://stackoverflow.com/questions/9489736/catmull-rom-curve-with-no-cusps-and-no-self-intersections/
	- http://ideone.com/NoEbVM

	This CubicPoly class could be used for reusing some variables and calculations,
	but for three.js curve use, it could be possible inlined and flatten into a single function call
	which can be placed in CurveUtils.
	*/ (x2)
/*
	 * Compute coefficients for a cubic polynomial
	 *   p(s) = c0 + c1*s + c2*s^2 + c3*s^3
	 * such that
	 *   p(0) = x0, p(1) = x1
	 *  and
	 *   p'(0) = t0, p'(1) = t1.
	 */
// compute tangents when parameterized in [t1,t2] (x2)
// rescale tangents for parametrization in [0,1] (x3)
```

<details><summary>Code</summary>

```typescript
function CubicPoly() {

	/**
	 * Centripetal CatmullRom Curve - which is useful for avoiding
	* cusps and self-intersections in non-uniform catmull rom curves.
	* http://www.cemyuksel.com/research/catmullrom_param/catmullrom.pdf
	*
	* curve.type accepts centripetal(default), chordal and catmullrom
	* curve.tension is used for catmullrom which defaults to 0.5
	*/

	/*
	Based on an optimized c++ solution in
	- http://stackoverflow.com/questions/9489736/catmull-rom-curve-with-no-cusps-and-no-self-intersections/
	- http://ideone.com/NoEbVM

	This CubicPoly class could be used for reusing some variables and calculations,
	but for three.js curve use, it could be possible inlined and flatten into a single function call
	which can be placed in CurveUtils.
	*/

	let c0 = 0, c1 = 0, c2 = 0, c3 = 0;

	/*
	 * Compute coefficients for a cubic polynomial
	 *   p(s) = c0 + c1*s + c2*s^2 + c3*s^3
	 * such that
	 *   p(0) = x0, p(1) = x1
	 *  and
	 *   p'(0) = t0, p'(1) = t1.
	 */
	function init( x0, x1, t0, t1 ) {

		c0 = x0;
		c1 = t0;
		c2 = - 3 * x0 + 3 * x1 - 2 * t0 - t1;
		c3 = 2 * x0 - 2 * x1 + t0 + t1;

	}

	return {

		initCatmullRom: function ( x0, x1, x2, x3, tension ) {

			init( x1, x2, tension * ( x2 - x0 ), tension * ( x3 - x1 ) );

		},

		initNonuniformCatmullRom: function ( x0, x1, x2, x3, dt0, dt1, dt2 ) {

			// compute tangents when parameterized in [t1,t2]
			let t1 = ( x1 - x0 ) / dt0 - ( x2 - x0 ) / ( dt0 + dt1 ) + ( x2 - x1 ) / dt1;
			let t2 = ( x2 - x1 ) / dt1 - ( x3 - x1 ) / ( dt1 + dt2 ) + ( x3 - x2 ) / dt2;

			// rescale tangents for parametrization in [0,1]
			t1 *= dt1;
			t2 *= dt1;

			init( x1, x2, t1, t2 );

		},

		calc: function ( t ) {

			const t2 = t * t;
			const t3 = t2 * t;
			return c0 + c1 * t + c2 * t2 + c3 * t3;

		}

	};

}
```
</details>

### `init(x0: any, x1: any, t0: any, t1: any): void`

**Parameters:**

- **`x0`** `any`
- **`x1`** `any`
- **`t0`** `any`
- **`t1`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function init( x0, x1, t0, t1 ) {

		c0 = x0;
		c1 = t0;
		c2 = - 3 * x0 + 3 * x1 - 2 * t0 - t1;
		c3 = 2 * x0 - 2 * x1 + t0 + t1;

	}
```
</details>

### `initCatmullRom(x0: any, x1: any, x2: any, x3: any, tension: any): void`

**Parameters:**

- **`x0`** `any`
- **`x1`** `any`
- **`x2`** `any`
- **`x3`** `any`
- **`tension`** `any`

**Returns:** `void`

**Calls:**

- `init`

<details><summary>Code</summary>

```typescript
function ( x0, x1, x2, x3, tension ) {

			init( x1, x2, tension * ( x2 - x0 ), tension * ( x3 - x1 ) );

		}
```
</details>

### `initNonuniformCatmullRom(x0: any, x1: any, x2: any, x3: any, dt0: any, dt1: any, dt2: any): void`

**Parameters:**

- **`x0`** `any`
- **`x1`** `any`
- **`x2`** `any`
- **`x3`** `any`
- **`dt0`** `any`
- **`dt1`** `any`
- **`dt2`** `any`

**Returns:** `void`

**Calls:**

- `init`

**Internal Comments:**
```
// compute tangents when parameterized in [t1,t2] (x2)
// rescale tangents for parametrization in [0,1] (x3)
```

<details><summary>Code</summary>

```typescript
function ( x0, x1, x2, x3, dt0, dt1, dt2 ) {

			// compute tangents when parameterized in [t1,t2]
			let t1 = ( x1 - x0 ) / dt0 - ( x2 - x0 ) / ( dt0 + dt1 ) + ( x2 - x1 ) / dt1;
			let t2 = ( x2 - x1 ) / dt1 - ( x3 - x1 ) / ( dt1 + dt2 ) + ( x3 - x2 ) / dt2;

			// rescale tangents for parametrization in [0,1]
			t1 *= dt1;
			t2 *= dt1;

			init( x1, x2, t1, t2 );

		}
```
</details>

### `calc(t: any): number`

**Parameters:**

- **`t`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function ( t ) {

			const t2 = t * t;
			const t3 = t2 * t;
			return c0 + c1 * t + c2 * t2 + c3 * t3;

		}
```
</details>

### `initCatmullRom(x0: any, x1: any, x2: any, x3: any, tension: any): void`

**Parameters:**

- **`x0`** `any`
- **`x1`** `any`
- **`x2`** `any`
- **`x3`** `any`
- **`tension`** `any`

**Returns:** `void`

**Calls:**

- `init`

<details><summary>Code</summary>

```typescript
function ( x0, x1, x2, x3, tension ) {

			init( x1, x2, tension * ( x2 - x0 ), tension * ( x3 - x1 ) );

		}
```
</details>

### `initNonuniformCatmullRom(x0: any, x1: any, x2: any, x3: any, dt0: any, dt1: any, dt2: any): void`

**Parameters:**

- **`x0`** `any`
- **`x1`** `any`
- **`x2`** `any`
- **`x3`** `any`
- **`dt0`** `any`
- **`dt1`** `any`
- **`dt2`** `any`

**Returns:** `void`

**Calls:**

- `init`

**Internal Comments:**
```
// compute tangents when parameterized in [t1,t2] (x2)
// rescale tangents for parametrization in [0,1] (x3)
```

<details><summary>Code</summary>

```typescript
function ( x0, x1, x2, x3, dt0, dt1, dt2 ) {

			// compute tangents when parameterized in [t1,t2]
			let t1 = ( x1 - x0 ) / dt0 - ( x2 - x0 ) / ( dt0 + dt1 ) + ( x2 - x1 ) / dt1;
			let t2 = ( x2 - x1 ) / dt1 - ( x3 - x1 ) / ( dt1 + dt2 ) + ( x3 - x2 ) / dt2;

			// rescale tangents for parametrization in [0,1]
			t1 *= dt1;
			t2 *= dt1;

			init( x1, x2, t1, t2 );

		}
```
</details>

### `calc(t: any): number`

**Parameters:**

- **`t`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function ( t ) {

			const t2 = t * t;
			const t3 = t2 * t;
			return c0 + c1 * t + c2 * t2 + c3 * t3;

		}
```
</details>

### `CatmullRomCurve3.getPoint(t: number, optionalTarget: Vector3): Vector3`

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

- `Math.floor`
- `Math.abs`
- `tmp.subVectors( points[ 0 ], points[ 1 ] ).add`
- `tmp.subVectors( points[ l - 1 ], points[ l - 2 ] ).add`
- `Math.pow`
- `p0.distanceToSquared`
- `p1.distanceToSquared`
- `p2.distanceToSquared`
- `px.initNonuniformCatmullRom`
- `py.initNonuniformCatmullRom`
- `pz.initNonuniformCatmullRom`
- `px.initCatmullRom`
- `py.initCatmullRom`
- `pz.initCatmullRom`
- `point.set`
- `px.calc`
- `py.calc`
- `pz.calc`

**Internal Comments:**
```
// extrapolate first point (x6)
// extrapolate last point (x6)
// init Centripetal / Chordal Catmull-Rom (x2)
// safety check for repeated points
```

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget = new Vector3() ) {

		const point = optionalTarget;

		const points = this.points;
		const l = points.length;

		const p = ( l - ( this.closed ? 0 : 1 ) ) * t;
		let intPoint = Math.floor( p );
		let weight = p - intPoint;

		if ( this.closed ) {

			intPoint += intPoint > 0 ? 0 : ( Math.floor( Math.abs( intPoint ) / l ) + 1 ) * l;

		} else if ( weight === 0 && intPoint === l - 1 ) {

			intPoint = l - 2;
			weight = 1;

		}

		let p0, p3; // 4 points (p1 & p2 defined below)

		if ( this.closed || intPoint > 0 ) {

			p0 = points[ ( intPoint - 1 ) % l ];

		} else {

			// extrapolate first point
			tmp.subVectors( points[ 0 ], points[ 1 ] ).add( points[ 0 ] );
			p0 = tmp;

		}

		const p1 = points[ intPoint % l ];
		const p2 = points[ ( intPoint + 1 ) % l ];

		if ( this.closed || intPoint + 2 < l ) {

			p3 = points[ ( intPoint + 2 ) % l ];

		} else {

			// extrapolate last point
			tmp.subVectors( points[ l - 1 ], points[ l - 2 ] ).add( points[ l - 1 ] );
			p3 = tmp;

		}

		if ( this.curveType === 'centripetal' || this.curveType === 'chordal' ) {

			// init Centripetal / Chordal Catmull-Rom
			const pow = this.curveType === 'chordal' ? 0.5 : 0.25;
			let dt0 = Math.pow( p0.distanceToSquared( p1 ), pow );
			let dt1 = Math.pow( p1.distanceToSquared( p2 ), pow );
			let dt2 = Math.pow( p2.distanceToSquared( p3 ), pow );

			// safety check for repeated points
			if ( dt1 < 1e-4 ) dt1 = 1.0;
			if ( dt0 < 1e-4 ) dt0 = dt1;
			if ( dt2 < 1e-4 ) dt2 = dt1;

			px.initNonuniformCatmullRom( p0.x, p1.x, p2.x, p3.x, dt0, dt1, dt2 );
			py.initNonuniformCatmullRom( p0.y, p1.y, p2.y, p3.y, dt0, dt1, dt2 );
			pz.initNonuniformCatmullRom( p0.z, p1.z, p2.z, p3.z, dt0, dt1, dt2 );

		} else if ( this.curveType === 'catmullrom' ) {

			px.initCatmullRom( p0.x, p1.x, p2.x, p3.x, this.tension );
			py.initCatmullRom( p0.y, p1.y, p2.y, p3.y, this.tension );
			pz.initCatmullRom( p0.z, p1.z, p2.z, p3.z, this.tension );

		}

		point.set(
			px.calc( weight ),
			py.calc( weight ),
			pz.calc( weight )
		);

		return point;

	}
```
</details>

### `CatmullRomCurve3.copy(source: any): this`

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

		this.closed = source.closed;
		this.curveType = source.curveType;
		this.tension = source.tension;

		return this;

	}
```
</details>

### `CatmullRomCurve3.toJSON(): any`

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

		data.closed = this.closed;
		data.curveType = this.curveType;
		data.tension = this.tension;

		return data;

	}
```
</details>

### `CatmullRomCurve3.fromJSON(json: any): this`

**Parameters:**

- **`json`** `any`

**Returns:** `this`

**Calls:**

- `super.fromJSON`
- `this.points.push`
- `new Vector3().fromArray`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		super.fromJSON( json );

		this.points = [];

		for ( let i = 0, l = json.points.length; i < l; i ++ ) {

			const point = json.points[ i ];
			this.points.push( new Vector3().fromArray( point ) );

		}

		this.closed = json.closed;
		this.curveType = json.curveType;
		this.tension = json.tension;

		return this;

	}
```
</details>


---

## Classes

### `CatmullRomCurve3`

<details><summary>Class Code</summary>

```ts
class CatmullRomCurve3 extends Curve {

	/**
	 * Constructs a new Catmull-Rom curve.
	 *
	 * @param {Array<Vector3>} [points] - An array of 3D points defining the curve.
	 * @param {boolean} [closed=false] - Whether the curve is closed or not.
	 * @param {('centripetal'|'chordal'|'catmullrom')} [curveType='centripetal'] - The curve type.
	 * @param {number} [tension=0.5] - Tension of the curve.
	 */
	constructor( points = [], closed = false, curveType = 'centripetal', tension = 0.5 ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isCatmullRomCurve3 = true;

		this.type = 'CatmullRomCurve3';

		/**
		 * An array of 3D points defining the curve.
		 *
		 * @type {Array<Vector3>}
		 */
		this.points = points;

		/**
		 * Whether the curve is closed or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.closed = closed;

		/**
		 * The curve type.
		 *
		 * @type {('centripetal'|'chordal'|'catmullrom')}
		 * @default 'centripetal'
		 */
		this.curveType = curveType;

		/**
		 * Tension of the curve.
		 *
		 * @type {number}
		 * @default 0.5
		 */
		this.tension = tension;

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

		const points = this.points;
		const l = points.length;

		const p = ( l - ( this.closed ? 0 : 1 ) ) * t;
		let intPoint = Math.floor( p );
		let weight = p - intPoint;

		if ( this.closed ) {

			intPoint += intPoint > 0 ? 0 : ( Math.floor( Math.abs( intPoint ) / l ) + 1 ) * l;

		} else if ( weight === 0 && intPoint === l - 1 ) {

			intPoint = l - 2;
			weight = 1;

		}

		let p0, p3; // 4 points (p1 & p2 defined below)

		if ( this.closed || intPoint > 0 ) {

			p0 = points[ ( intPoint - 1 ) % l ];

		} else {

			// extrapolate first point
			tmp.subVectors( points[ 0 ], points[ 1 ] ).add( points[ 0 ] );
			p0 = tmp;

		}

		const p1 = points[ intPoint % l ];
		const p2 = points[ ( intPoint + 1 ) % l ];

		if ( this.closed || intPoint + 2 < l ) {

			p3 = points[ ( intPoint + 2 ) % l ];

		} else {

			// extrapolate last point
			tmp.subVectors( points[ l - 1 ], points[ l - 2 ] ).add( points[ l - 1 ] );
			p3 = tmp;

		}

		if ( this.curveType === 'centripetal' || this.curveType === 'chordal' ) {

			// init Centripetal / Chordal Catmull-Rom
			const pow = this.curveType === 'chordal' ? 0.5 : 0.25;
			let dt0 = Math.pow( p0.distanceToSquared( p1 ), pow );
			let dt1 = Math.pow( p1.distanceToSquared( p2 ), pow );
			let dt2 = Math.pow( p2.distanceToSquared( p3 ), pow );

			// safety check for repeated points
			if ( dt1 < 1e-4 ) dt1 = 1.0;
			if ( dt0 < 1e-4 ) dt0 = dt1;
			if ( dt2 < 1e-4 ) dt2 = dt1;

			px.initNonuniformCatmullRom( p0.x, p1.x, p2.x, p3.x, dt0, dt1, dt2 );
			py.initNonuniformCatmullRom( p0.y, p1.y, p2.y, p3.y, dt0, dt1, dt2 );
			pz.initNonuniformCatmullRom( p0.z, p1.z, p2.z, p3.z, dt0, dt1, dt2 );

		} else if ( this.curveType === 'catmullrom' ) {

			px.initCatmullRom( p0.x, p1.x, p2.x, p3.x, this.tension );
			py.initCatmullRom( p0.y, p1.y, p2.y, p3.y, this.tension );
			pz.initCatmullRom( p0.z, p1.z, p2.z, p3.z, this.tension );

		}

		point.set(
			px.calc( weight ),
			py.calc( weight ),
			pz.calc( weight )
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

		this.closed = source.closed;
		this.curveType = source.curveType;
		this.tension = source.tension;

		return this;

	}

	toJSON() {

		const data = super.toJSON();

		data.points = [];

		for ( let i = 0, l = this.points.length; i < l; i ++ ) {

			const point = this.points[ i ];
			data.points.push( point.toArray() );

		}

		data.closed = this.closed;
		data.curveType = this.curveType;
		data.tension = this.tension;

		return data;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.points = [];

		for ( let i = 0, l = json.points.length; i < l; i ++ ) {

			const point = json.points[ i ];
			this.points.push( new Vector3().fromArray( point ) );

		}

		this.closed = json.closed;
		this.curveType = json.curveType;
		this.tension = json.tension;

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

		const points = this.points;
		const l = points.length;

		const p = ( l - ( this.closed ? 0 : 1 ) ) * t;
		let intPoint = Math.floor( p );
		let weight = p - intPoint;

		if ( this.closed ) {

			intPoint += intPoint > 0 ? 0 : ( Math.floor( Math.abs( intPoint ) / l ) + 1 ) * l;

		} else if ( weight === 0 && intPoint === l - 1 ) {

			intPoint = l - 2;
			weight = 1;

		}

		let p0, p3; // 4 points (p1 & p2 defined below)

		if ( this.closed || intPoint > 0 ) {

			p0 = points[ ( intPoint - 1 ) % l ];

		} else {

			// extrapolate first point
			tmp.subVectors( points[ 0 ], points[ 1 ] ).add( points[ 0 ] );
			p0 = tmp;

		}

		const p1 = points[ intPoint % l ];
		const p2 = points[ ( intPoint + 1 ) % l ];

		if ( this.closed || intPoint + 2 < l ) {

			p3 = points[ ( intPoint + 2 ) % l ];

		} else {

			// extrapolate last point
			tmp.subVectors( points[ l - 1 ], points[ l - 2 ] ).add( points[ l - 1 ] );
			p3 = tmp;

		}

		if ( this.curveType === 'centripetal' || this.curveType === 'chordal' ) {

			// init Centripetal / Chordal Catmull-Rom
			const pow = this.curveType === 'chordal' ? 0.5 : 0.25;
			let dt0 = Math.pow( p0.distanceToSquared( p1 ), pow );
			let dt1 = Math.pow( p1.distanceToSquared( p2 ), pow );
			let dt2 = Math.pow( p2.distanceToSquared( p3 ), pow );

			// safety check for repeated points
			if ( dt1 < 1e-4 ) dt1 = 1.0;
			if ( dt0 < 1e-4 ) dt0 = dt1;
			if ( dt2 < 1e-4 ) dt2 = dt1;

			px.initNonuniformCatmullRom( p0.x, p1.x, p2.x, p3.x, dt0, dt1, dt2 );
			py.initNonuniformCatmullRom( p0.y, p1.y, p2.y, p3.y, dt0, dt1, dt2 );
			pz.initNonuniformCatmullRom( p0.z, p1.z, p2.z, p3.z, dt0, dt1, dt2 );

		} else if ( this.curveType === 'catmullrom' ) {

			px.initCatmullRom( p0.x, p1.x, p2.x, p3.x, this.tension );
			py.initCatmullRom( p0.y, p1.y, p2.y, p3.y, this.tension );
			pz.initCatmullRom( p0.z, p1.z, p2.z, p3.z, this.tension );

		}

		point.set(
			px.calc( weight ),
			py.calc( weight ),
			pz.calc( weight )
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

		this.closed = source.closed;
		this.curveType = source.curveType;
		this.tension = source.tension;

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

		data.closed = this.closed;
		data.curveType = this.curveType;
		data.tension = this.tension;

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
			this.points.push( new Vector3().fromArray( point ) );

		}

		this.closed = json.closed;
		this.curveType = json.curveType;
		this.tension = json.tension;

		return this;

	}
```
</details>


---