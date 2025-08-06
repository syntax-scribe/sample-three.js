[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CurvePath.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 11 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 17 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/extras/core/CurvePath.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Curve` | `./Curve.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `lineType` | `"LineCurve" \| "LineCurve3"` | let/var | `( startPoint.isVector2 === true ) ? 'LineCurve' : 'LineCurve3'` | ✗ |
| `d` | `number` | let/var | `t * this.getLength()` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `diff` | `number` | let/var | `curveLengths[ i ] - d` | ✗ |
| `curve` | `Curve` | let/var | `this.curves[ i ]` | ✗ |
| `u` | `number` | let/var | `segmentLength === 0 ? 0 : 1 - diff / segmentLength` | ✗ |
| `lengths` | `any[]` | let/var | `[]` | ✗ |
| `sums` | `number` | let/var | `0` | ✗ |
| `points` | `any[]` | let/var | `[]` | ✗ |
| `points` | `any[]` | let/var | `[]` | ✗ |
| `last` | `any` | let/var | `*not shown*` | ✗ |
| `curve` | `Curve` | let/var | `curves[ i ]` | ✗ |
| `resolution` | `number` | let/var | `curve.isEllipseCurve ? divisions * 2 : ( curve.isLineCurve \|\| curve.isLineC...` | ✗ |
| `point` | `Vector2 \| Vector3` | let/var | `pts[ j ]` | ✗ |
| `curve` | `any` | let/var | `source.curves[ i ]` | ✗ |
| `curve` | `Curve` | let/var | `this.curves[ i ]` | ✗ |
| `curve` | `any` | let/var | `json.curves[ i ]` | ✗ |


---

## Functions

### `CurvePath.add(curve: Curve): void`

**JSDoc:**
```typescript
/**
	 * Adds a curve to this curve path.
	 *
	 * @param {Curve} curve - The curve to add.
	 */
```

**Parameters:**

- **`curve`** `Curve`

**Returns:** `void`

**Calls:**

- `this.curves.push`

<details><summary>Code</summary>

```typescript
add( curve ) {

		this.curves.push( curve );

	}
```
</details>

### `CurvePath.closePath(): CurvePath`

**JSDoc:**
```typescript
/**
	 * Adds a line curve to close the path.
	 *
	 * @return {CurvePath} A reference to this curve path.
	 */
```

**Returns:** `CurvePath`

**Calls:**

- `this.curves[ 0 ].getPoint`
- `this.curves[ this.curves.length - 1 ].getPoint`
- `startPoint.equals`
- `this.curves.push`

**Internal Comments:**
```
// Add a line curve if start and end of lines are not connected (x2)
```

<details><summary>Code</summary>

```typescript
closePath() {

		// Add a line curve if start and end of lines are not connected
		const startPoint = this.curves[ 0 ].getPoint( 0 );
		const endPoint = this.curves[ this.curves.length - 1 ].getPoint( 1 );

		if ( ! startPoint.equals( endPoint ) ) {

			const lineType = ( startPoint.isVector2 === true ) ? 'LineCurve' : 'LineCurve3';
			this.curves.push( new Curves[ lineType ]( endPoint, startPoint ) );

		}

		return this;

	}
```
</details>

### `CurvePath.getPoint(t: number, optionalTarget: any): any`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 2D or 3D space (depending on the curve definitions)
	 * for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {(Vector2|Vector3)} [optionalTarget] - The optional target vector the result is written to.
	 * @return {?(Vector2|Vector3)} The position on the curve. It can be a 2D or 3D vector depending on the curve definition.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `any`

**Returns:** `any`

**Calls:**

- `this.getLength`
- `this.getCurveLengths`
- `curve.getLength`
- `curve.getPointAt`

**Internal Comments:**
```
// To get accurate point with reference to (x2)
// entire path distance at time t, (x2)
// following has to be done: (x2)
// 1. Length of each sub path have to be known (x2)
// 2. Locate and identify type of curve (x2)
// 3. Get t for the curve (x2)
// 4. Return curve.getPointAt(t') (x2)
// To think about boundaries points.
```

<details><summary>Code</summary>

```typescript
getPoint( t, optionalTarget ) {

		// To get accurate point with reference to
		// entire path distance at time t,
		// following has to be done:

		// 1. Length of each sub path have to be known
		// 2. Locate and identify type of curve
		// 3. Get t for the curve
		// 4. Return curve.getPointAt(t')

		const d = t * this.getLength();
		const curveLengths = this.getCurveLengths();
		let i = 0;

		// To think about boundaries points.

		while ( i < curveLengths.length ) {

			if ( curveLengths[ i ] >= d ) {

				const diff = curveLengths[ i ] - d;
				const curve = this.curves[ i ];

				const segmentLength = curve.getLength();
				const u = segmentLength === 0 ? 0 : 1 - diff / segmentLength;

				return curve.getPointAt( u, optionalTarget );

			}

			i ++;

		}

		return null;

		// loop where sum != 0, sum > d , sum+1 <d

	}
```
</details>

### `CurvePath.getLength(): number`

**Returns:** `number`

**Calls:**

- `this.getCurveLengths`

**Internal Comments:**
```
// We cannot use the default THREE.Curve getPoint() with getLength() because in (x2)
// THREE.Curve, getLength() depends on getPoint() but in THREE.CurvePath (x2)
// getPoint() depends on getLength (x2)
```

<details><summary>Code</summary>

```typescript
getLength() {

		// We cannot use the default THREE.Curve getPoint() with getLength() because in
		// THREE.Curve, getLength() depends on getPoint() but in THREE.CurvePath
		// getPoint() depends on getLength

		const lens = this.getCurveLengths();
		return lens[ lens.length - 1 ];

	}
```
</details>

### `CurvePath.updateArcLengths(): void`

**Returns:** `void`

**Calls:**

- `this.getCurveLengths`

**Internal Comments:**
```
// cacheLengths must be recalculated. (x4)
```

<details><summary>Code</summary>

```typescript
updateArcLengths() {

		// cacheLengths must be recalculated.

		this.needsUpdate = true;
		this.cacheLengths = null;
		this.getCurveLengths();

	}
```
</details>

### `CurvePath.getCurveLengths(): number[]`

**JSDoc:**
```typescript
/**
	 * Returns list of cumulative curve lengths of the defined curves.
	 *
	 * @return {Array<number>} The curve lengths.
	 */
```

**Returns:** `number[]`

**Calls:**

- `this.curves[ i ].getLength`
- `lengths.push`

**Internal Comments:**
```
// Compute lengths and cache them
// We cannot overwrite getLengths() because UtoT mapping uses it.
// We use cache values if curves and cache array are same length
// Get length of sub-curve (x2)
// Push sums into cached array (x2)
```

<details><summary>Code</summary>

```typescript
getCurveLengths() {

		// Compute lengths and cache them
		// We cannot overwrite getLengths() because UtoT mapping uses it.
		// We use cache values if curves and cache array are same length

		if ( this.cacheLengths && this.cacheLengths.length === this.curves.length ) {

			return this.cacheLengths;

		}

		// Get length of sub-curve
		// Push sums into cached array

		const lengths = [];
		let sums = 0;

		for ( let i = 0, l = this.curves.length; i < l; i ++ ) {

			sums += this.curves[ i ].getLength();
			lengths.push( sums );

		}

		this.cacheLengths = lengths;

		return lengths;

	}
```
</details>

### `CurvePath.getSpacedPoints(divisions: number): any[]`

**Parameters:**

- **`divisions`** `number`

**Returns:** `any[]`

**Calls:**

- `points.push`
- `this.getPoint`

<details><summary>Code</summary>

```typescript
getSpacedPoints( divisions = 40 ) {

		const points = [];

		for ( let i = 0; i <= divisions; i ++ ) {

			points.push( this.getPoint( i / divisions ) );

		}

		if ( this.autoClose ) {

			points.push( points[ 0 ] );

		}

		return points;

	}
```
</details>

### `CurvePath.getPoints(divisions: number): (Vector2 | Vector3)[]`

**Parameters:**

- **`divisions`** `number`

**Returns:** `(Vector2 | Vector3)[]`

**Calls:**

- `curve.getPoints`
- `last.equals`
- `points.push`
- `points[ points.length - 1 ].equals`

<details><summary>Code</summary>

```typescript
getPoints( divisions = 12 ) {

		const points = [];
		let last;

		for ( let i = 0, curves = this.curves; i < curves.length; i ++ ) {

			const curve = curves[ i ];
			const resolution = curve.isEllipseCurve ? divisions * 2
				: ( curve.isLineCurve || curve.isLineCurve3 ) ? 1
					: curve.isSplineCurve ? divisions * curve.points.length
						: divisions;

			const pts = curve.getPoints( resolution );

			for ( let j = 0; j < pts.length; j ++ ) {

				const point = pts[ j ];

				if ( last && last.equals( point ) ) continue; // ensures no consecutive points are duplicates

				points.push( point );
				last = point;

			}

		}

		if ( this.autoClose && points.length > 1 && ! points[ points.length - 1 ].equals( points[ 0 ] ) ) {

			points.push( points[ 0 ] );

		}

		return points;

	}
```
</details>

### `CurvePath.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.curves.push`
- `curve.clone`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.curves = [];

		for ( let i = 0, l = source.curves.length; i < l; i ++ ) {

			const curve = source.curves[ i ];

			this.curves.push( curve.clone() );

		}

		this.autoClose = source.autoClose;

		return this;

	}
```
</details>

### `CurvePath.toJSON(): any`

**Returns:** `any`

**Calls:**

- `super.toJSON`
- `data.curves.push`
- `curve.toJSON`

<details><summary>Code</summary>

```typescript
toJSON() {

		const data = super.toJSON();

		data.autoClose = this.autoClose;
		data.curves = [];

		for ( let i = 0, l = this.curves.length; i < l; i ++ ) {

			const curve = this.curves[ i ];
			data.curves.push( curve.toJSON() );

		}

		return data;

	}
```
</details>

### `CurvePath.fromJSON(json: any): this`

**Parameters:**

- **`json`** `any`

**Returns:** `this`

**Calls:**

- `super.fromJSON`
- `this.curves.push`
- `new Curves[ curve.type ]().fromJSON`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		super.fromJSON( json );

		this.autoClose = json.autoClose;
		this.curves = [];

		for ( let i = 0, l = json.curves.length; i < l; i ++ ) {

			const curve = json.curves[ i ];
			this.curves.push( new Curves[ curve.type ]().fromJSON( curve ) );

		}

		return this;

	}
```
</details>


---

## Classes

### `CurvePath`

<details><summary>Class Code</summary>

```ts
class CurvePath extends Curve {

	/**
	 * Constructs a new curve path.
	 */
	constructor() {

		super();

		this.type = 'CurvePath';

		/**
		 * An array of curves defining the
		 * path.
		 *
		 * @type {Array<Curve>}
		 */
		this.curves = [];

		/**
		 * Whether the path should automatically be closed
		 * by a line curve.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.autoClose = false;

	}

	/**
	 * Adds a curve to this curve path.
	 *
	 * @param {Curve} curve - The curve to add.
	 */
	add( curve ) {

		this.curves.push( curve );

	}

	/**
	 * Adds a line curve to close the path.
	 *
	 * @return {CurvePath} A reference to this curve path.
	 */
	closePath() {

		// Add a line curve if start and end of lines are not connected
		const startPoint = this.curves[ 0 ].getPoint( 0 );
		const endPoint = this.curves[ this.curves.length - 1 ].getPoint( 1 );

		if ( ! startPoint.equals( endPoint ) ) {

			const lineType = ( startPoint.isVector2 === true ) ? 'LineCurve' : 'LineCurve3';
			this.curves.push( new Curves[ lineType ]( endPoint, startPoint ) );

		}

		return this;

	}

	/**
	 * This method returns a vector in 2D or 3D space (depending on the curve definitions)
	 * for the given interpolation factor.
	 *
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {(Vector2|Vector3)} [optionalTarget] - The optional target vector the result is written to.
	 * @return {?(Vector2|Vector3)} The position on the curve. It can be a 2D or 3D vector depending on the curve definition.
	 */
	getPoint( t, optionalTarget ) {

		// To get accurate point with reference to
		// entire path distance at time t,
		// following has to be done:

		// 1. Length of each sub path have to be known
		// 2. Locate and identify type of curve
		// 3. Get t for the curve
		// 4. Return curve.getPointAt(t')

		const d = t * this.getLength();
		const curveLengths = this.getCurveLengths();
		let i = 0;

		// To think about boundaries points.

		while ( i < curveLengths.length ) {

			if ( curveLengths[ i ] >= d ) {

				const diff = curveLengths[ i ] - d;
				const curve = this.curves[ i ];

				const segmentLength = curve.getLength();
				const u = segmentLength === 0 ? 0 : 1 - diff / segmentLength;

				return curve.getPointAt( u, optionalTarget );

			}

			i ++;

		}

		return null;

		// loop where sum != 0, sum > d , sum+1 <d

	}

	getLength() {

		// We cannot use the default THREE.Curve getPoint() with getLength() because in
		// THREE.Curve, getLength() depends on getPoint() but in THREE.CurvePath
		// getPoint() depends on getLength

		const lens = this.getCurveLengths();
		return lens[ lens.length - 1 ];

	}

	updateArcLengths() {

		// cacheLengths must be recalculated.

		this.needsUpdate = true;
		this.cacheLengths = null;
		this.getCurveLengths();

	}

	/**
	 * Returns list of cumulative curve lengths of the defined curves.
	 *
	 * @return {Array<number>} The curve lengths.
	 */
	getCurveLengths() {

		// Compute lengths and cache them
		// We cannot overwrite getLengths() because UtoT mapping uses it.
		// We use cache values if curves and cache array are same length

		if ( this.cacheLengths && this.cacheLengths.length === this.curves.length ) {

			return this.cacheLengths;

		}

		// Get length of sub-curve
		// Push sums into cached array

		const lengths = [];
		let sums = 0;

		for ( let i = 0, l = this.curves.length; i < l; i ++ ) {

			sums += this.curves[ i ].getLength();
			lengths.push( sums );

		}

		this.cacheLengths = lengths;

		return lengths;

	}

	getSpacedPoints( divisions = 40 ) {

		const points = [];

		for ( let i = 0; i <= divisions; i ++ ) {

			points.push( this.getPoint( i / divisions ) );

		}

		if ( this.autoClose ) {

			points.push( points[ 0 ] );

		}

		return points;

	}

	getPoints( divisions = 12 ) {

		const points = [];
		let last;

		for ( let i = 0, curves = this.curves; i < curves.length; i ++ ) {

			const curve = curves[ i ];
			const resolution = curve.isEllipseCurve ? divisions * 2
				: ( curve.isLineCurve || curve.isLineCurve3 ) ? 1
					: curve.isSplineCurve ? divisions * curve.points.length
						: divisions;

			const pts = curve.getPoints( resolution );

			for ( let j = 0; j < pts.length; j ++ ) {

				const point = pts[ j ];

				if ( last && last.equals( point ) ) continue; // ensures no consecutive points are duplicates

				points.push( point );
				last = point;

			}

		}

		if ( this.autoClose && points.length > 1 && ! points[ points.length - 1 ].equals( points[ 0 ] ) ) {

			points.push( points[ 0 ] );

		}

		return points;

	}

	copy( source ) {

		super.copy( source );

		this.curves = [];

		for ( let i = 0, l = source.curves.length; i < l; i ++ ) {

			const curve = source.curves[ i ];

			this.curves.push( curve.clone() );

		}

		this.autoClose = source.autoClose;

		return this;

	}

	toJSON() {

		const data = super.toJSON();

		data.autoClose = this.autoClose;
		data.curves = [];

		for ( let i = 0, l = this.curves.length; i < l; i ++ ) {

			const curve = this.curves[ i ];
			data.curves.push( curve.toJSON() );

		}

		return data;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.autoClose = json.autoClose;
		this.curves = [];

		for ( let i = 0, l = json.curves.length; i < l; i ++ ) {

			const curve = json.curves[ i ];
			this.curves.push( new Curves[ curve.type ]().fromJSON( curve ) );

		}

		return this;

	}

}
```
</details>

#### Methods

##### `add(curve: Curve): void`

<details><summary>Code</summary>

```ts
add( curve ) {

		this.curves.push( curve );

	}
```
</details>

##### `closePath(): CurvePath`

<details><summary>Code</summary>

```ts
closePath() {

		// Add a line curve if start and end of lines are not connected
		const startPoint = this.curves[ 0 ].getPoint( 0 );
		const endPoint = this.curves[ this.curves.length - 1 ].getPoint( 1 );

		if ( ! startPoint.equals( endPoint ) ) {

			const lineType = ( startPoint.isVector2 === true ) ? 'LineCurve' : 'LineCurve3';
			this.curves.push( new Curves[ lineType ]( endPoint, startPoint ) );

		}

		return this;

	}
```
</details>

##### `getPoint(t: number, optionalTarget: any): any`

<details><summary>Code</summary>

```ts
getPoint( t, optionalTarget ) {

		// To get accurate point with reference to
		// entire path distance at time t,
		// following has to be done:

		// 1. Length of each sub path have to be known
		// 2. Locate and identify type of curve
		// 3. Get t for the curve
		// 4. Return curve.getPointAt(t')

		const d = t * this.getLength();
		const curveLengths = this.getCurveLengths();
		let i = 0;

		// To think about boundaries points.

		while ( i < curveLengths.length ) {

			if ( curveLengths[ i ] >= d ) {

				const diff = curveLengths[ i ] - d;
				const curve = this.curves[ i ];

				const segmentLength = curve.getLength();
				const u = segmentLength === 0 ? 0 : 1 - diff / segmentLength;

				return curve.getPointAt( u, optionalTarget );

			}

			i ++;

		}

		return null;

		// loop where sum != 0, sum > d , sum+1 <d

	}
```
</details>

##### `getLength(): number`

<details><summary>Code</summary>

```ts
getLength() {

		// We cannot use the default THREE.Curve getPoint() with getLength() because in
		// THREE.Curve, getLength() depends on getPoint() but in THREE.CurvePath
		// getPoint() depends on getLength

		const lens = this.getCurveLengths();
		return lens[ lens.length - 1 ];

	}
```
</details>

##### `updateArcLengths(): void`

<details><summary>Code</summary>

```ts
updateArcLengths() {

		// cacheLengths must be recalculated.

		this.needsUpdate = true;
		this.cacheLengths = null;
		this.getCurveLengths();

	}
```
</details>

##### `getCurveLengths(): number[]`

<details><summary>Code</summary>

```ts
getCurveLengths() {

		// Compute lengths and cache them
		// We cannot overwrite getLengths() because UtoT mapping uses it.
		// We use cache values if curves and cache array are same length

		if ( this.cacheLengths && this.cacheLengths.length === this.curves.length ) {

			return this.cacheLengths;

		}

		// Get length of sub-curve
		// Push sums into cached array

		const lengths = [];
		let sums = 0;

		for ( let i = 0, l = this.curves.length; i < l; i ++ ) {

			sums += this.curves[ i ].getLength();
			lengths.push( sums );

		}

		this.cacheLengths = lengths;

		return lengths;

	}
```
</details>

##### `getSpacedPoints(divisions: number): any[]`

<details><summary>Code</summary>

```ts
getSpacedPoints( divisions = 40 ) {

		const points = [];

		for ( let i = 0; i <= divisions; i ++ ) {

			points.push( this.getPoint( i / divisions ) );

		}

		if ( this.autoClose ) {

			points.push( points[ 0 ] );

		}

		return points;

	}
```
</details>

##### `getPoints(divisions: number): (Vector2 | Vector3)[]`

<details><summary>Code</summary>

```ts
getPoints( divisions = 12 ) {

		const points = [];
		let last;

		for ( let i = 0, curves = this.curves; i < curves.length; i ++ ) {

			const curve = curves[ i ];
			const resolution = curve.isEllipseCurve ? divisions * 2
				: ( curve.isLineCurve || curve.isLineCurve3 ) ? 1
					: curve.isSplineCurve ? divisions * curve.points.length
						: divisions;

			const pts = curve.getPoints( resolution );

			for ( let j = 0; j < pts.length; j ++ ) {

				const point = pts[ j ];

				if ( last && last.equals( point ) ) continue; // ensures no consecutive points are duplicates

				points.push( point );
				last = point;

			}

		}

		if ( this.autoClose && points.length > 1 && ! points[ points.length - 1 ].equals( points[ 0 ] ) ) {

			points.push( points[ 0 ] );

		}

		return points;

	}
```
</details>

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source );

		this.curves = [];

		for ( let i = 0, l = source.curves.length; i < l; i ++ ) {

			const curve = source.curves[ i ];

			this.curves.push( curve.clone() );

		}

		this.autoClose = source.autoClose;

		return this;

	}
```
</details>

##### `toJSON(): any`

<details><summary>Code</summary>

```ts
toJSON() {

		const data = super.toJSON();

		data.autoClose = this.autoClose;
		data.curves = [];

		for ( let i = 0, l = this.curves.length; i < l; i ++ ) {

			const curve = this.curves[ i ];
			data.curves.push( curve.toJSON() );

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

		this.autoClose = json.autoClose;
		this.curves = [];

		for ( let i = 0, l = json.curves.length; i < l; i ++ ) {

			const curve = json.curves[ i ];
			this.curves.push( new Curves[ curve.type ]().fromJSON( curve ) );

		}

		return this;

	}
```
</details>


---