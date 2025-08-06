[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Path.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 13 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/extras/core/Path.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector2` | `../../math/Vector2.js` |
| `CurvePath` | `./CurvePath.js` |
| `EllipseCurve` | `../curves/EllipseCurve.js` |
| `SplineCurve` | `../curves/SplineCurve.js` |
| `CubicBezierCurve` | `../curves/CubicBezierCurve.js` |
| `QuadraticBezierCurve` | `../curves/QuadraticBezierCurve.js` |
| `LineCurve` | `../curves/LineCurve.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `curve` | `LineCurve` | let/var | `new LineCurve( this.currentPoint.clone(), new Vector2( x, y ) )` | ✗ |
| `curve` | `QuadraticBezierCurve` | let/var | `new QuadraticBezierCurve( this.currentPoint.clone(), new Vector2( aCPx, aCPy ...` | ✗ |
| `curve` | `CubicBezierCurve` | let/var | `new CubicBezierCurve( this.currentPoint.clone(), new Vector2( aCP1x, aCP1y ),...` | ✗ |
| `curve` | `SplineCurve` | let/var | `new SplineCurve( npts )` | ✗ |
| `x0` | `number` | let/var | `this.currentPoint.x` | ✗ |
| `y0` | `number` | let/var | `this.currentPoint.y` | ✗ |
| `x0` | `number` | let/var | `this.currentPoint.x` | ✗ |
| `y0` | `number` | let/var | `this.currentPoint.y` | ✗ |
| `curve` | `EllipseCurve` | let/var | `new EllipseCurve( aX, aY, xRadius, yRadius, aStartAngle, aEndAngle, aClockwis...` | ✗ |


---

## Functions

### `Path.setFromPoints(points: Vector2[]): Path`

**JSDoc:**
```typescript
/**
	 * Creates a path from the given list of points. The points are added
	 * to the path as instances of {@link LineCurve}.
	 *
	 * @param {Array<Vector2>} points - An array of 2D points.
	 * @return {Path} A reference to this path.
	 */
```

**Parameters:**

- **`points`** `Vector2[]`

**Returns:** `Path`

**Calls:**

- `this.moveTo`
- `this.lineTo`

<details><summary>Code</summary>

```typescript
setFromPoints( points ) {

		this.moveTo( points[ 0 ].x, points[ 0 ].y );

		for ( let i = 1, l = points.length; i < l; i ++ ) {

			this.lineTo( points[ i ].x, points[ i ].y );

		}

		return this;

	}
```
</details>

### `Path.moveTo(x: number, y: number): Path`

**JSDoc:**
```typescript
/**
	 * Moves {@link Path#currentPoint} to the given point.
	 *
	 * @param {number} x - The x coordinate.
	 * @param {number} y - The y coordinate.
	 * @return {Path} A reference to this path.
	 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`

**Returns:** `Path`

**Calls:**

- `this.currentPoint.set`

<details><summary>Code</summary>

```typescript
moveTo( x, y ) {

		this.currentPoint.set( x, y ); // TODO consider referencing vectors instead of copying?

		return this;

	}
```
</details>

### `Path.lineTo(x: number, y: number): Path`

**JSDoc:**
```typescript
/**
	 * Adds an instance of {@link LineCurve} to the path by connecting
	 * the current point with the given one.
	 *
	 * @param {number} x - The x coordinate of the end point.
	 * @param {number} y - The y coordinate of the end point.
	 * @return {Path} A reference to this path.
	 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`

**Returns:** `Path`

**Calls:**

- `this.currentPoint.clone`
- `this.curves.push`
- `this.currentPoint.set`

<details><summary>Code</summary>

```typescript
lineTo( x, y ) {

		const curve = new LineCurve( this.currentPoint.clone(), new Vector2( x, y ) );
		this.curves.push( curve );

		this.currentPoint.set( x, y );

		return this;

	}
```
</details>

### `Path.quadraticCurveTo(aCPx: number, aCPy: number, aX: number, aY: number): Path`

**JSDoc:**
```typescript
/**
	 * Adds an instance of {@link QuadraticBezierCurve} to the path by connecting
	 * the current point with the given one.
	 *
	 * @param {number} aCPx - The x coordinate of the control point.
	 * @param {number} aCPy - The y coordinate of the control point.
	 * @param {number} aX - The x coordinate of the end point.
	 * @param {number} aY - The y coordinate of the end point.
	 * @return {Path} A reference to this path.
	 */
```

**Parameters:**

- **`aCPx`** `number`
- **`aCPy`** `number`
- **`aX`** `number`
- **`aY`** `number`

**Returns:** `Path`

**Calls:**

- `this.currentPoint.clone`
- `this.curves.push`
- `this.currentPoint.set`

<details><summary>Code</summary>

```typescript
quadraticCurveTo( aCPx, aCPy, aX, aY ) {

		const curve = new QuadraticBezierCurve(
			this.currentPoint.clone(),
			new Vector2( aCPx, aCPy ),
			new Vector2( aX, aY )
		);

		this.curves.push( curve );

		this.currentPoint.set( aX, aY );

		return this;

	}
```
</details>

### `Path.bezierCurveTo(aCP1x: number, aCP1y: number, aCP2x: number, aCP2y: number, aX: number, aY: number): Path`

**JSDoc:**
```typescript
/**
	 * Adds an instance of {@link CubicBezierCurve} to the path by connecting
	 * the current point with the given one.
	 *
	 * @param {number} aCP1x - The x coordinate of the first control point.
	 * @param {number} aCP1y - The y coordinate of the first control point.
	 * @param {number} aCP2x - The x coordinate of the second control point.
	 * @param {number} aCP2y - The y coordinate of the second control point.
	 * @param {number} aX - The x coordinate of the end point.
	 * @param {number} aY - The y coordinate of the end point.
	 * @return {Path} A reference to this path.
	 */
```

**Parameters:**

- **`aCP1x`** `number`
- **`aCP1y`** `number`
- **`aCP2x`** `number`
- **`aCP2y`** `number`
- **`aX`** `number`
- **`aY`** `number`

**Returns:** `Path`

**Calls:**

- `this.currentPoint.clone`
- `this.curves.push`
- `this.currentPoint.set`

<details><summary>Code</summary>

```typescript
bezierCurveTo( aCP1x, aCP1y, aCP2x, aCP2y, aX, aY ) {

		const curve = new CubicBezierCurve(
			this.currentPoint.clone(),
			new Vector2( aCP1x, aCP1y ),
			new Vector2( aCP2x, aCP2y ),
			new Vector2( aX, aY )
		);

		this.curves.push( curve );

		this.currentPoint.set( aX, aY );

		return this;

	}
```
</details>

### `Path.splineThru(pts: Vector2[]): Path`

**JSDoc:**
```typescript
/**
	 * Adds an instance of {@link SplineCurve} to the path by connecting
	 * the current point with the given list of points.
	 *
	 * @param {Array<Vector2>} pts - An array of points in 2D space.
	 * @return {Path} A reference to this path.
	 */
```

**Parameters:**

- **`pts`** `Vector2[]`

**Returns:** `Path`

**Calls:**

- `[ this.currentPoint.clone() ].concat`
- `this.currentPoint.clone`
- `this.curves.push`
- `this.currentPoint.copy`

<details><summary>Code</summary>

```typescript
splineThru( pts ) {

		const npts = [ this.currentPoint.clone() ].concat( pts );

		const curve = new SplineCurve( npts );
		this.curves.push( curve );

		this.currentPoint.copy( pts[ pts.length - 1 ] );

		return this;

	}
```
</details>

### `Path.arc(aX: number, aY: number, aRadius: number, aStartAngle: number, aEndAngle: number, aClockwise: boolean): Path`

**JSDoc:**
```typescript
/**
	 * Adds an arc as an instance of {@link EllipseCurve} to the path, positioned relative
	 * to the current point.
	 *
	 * @param {number} [aX=0] - The x coordinate of the center of the arc offsetted from the previous curve.
	 * @param {number} [aY=0] - The y coordinate of the center of the arc offsetted from the previous curve.
	 * @param {number} [aRadius=1] - The radius of the arc.
	 * @param {number} [aStartAngle=0] - The start angle in radians.
	 * @param {number} [aEndAngle=Math.PI*2] - The end angle in radians.
	 * @param {boolean} [aClockwise=false] - Whether to sweep the arc clockwise or not.
	 * @return {Path} A reference to this path.
	 */
```

**Parameters:**

- **`aX`** `number`
- **`aY`** `number`
- **`aRadius`** `number`
- **`aStartAngle`** `number`
- **`aEndAngle`** `number`
- **`aClockwise`** `boolean`

**Returns:** `Path`

**Calls:**

- `this.absarc`

<details><summary>Code</summary>

```typescript
arc( aX, aY, aRadius, aStartAngle, aEndAngle, aClockwise ) {

		const x0 = this.currentPoint.x;
		const y0 = this.currentPoint.y;

		this.absarc( aX + x0, aY + y0, aRadius,
			aStartAngle, aEndAngle, aClockwise );

		return this;

	}
```
</details>

### `Path.absarc(aX: number, aY: number, aRadius: number, aStartAngle: number, aEndAngle: number, aClockwise: boolean): Path`

**JSDoc:**
```typescript
/**
	 * Adds an absolutely positioned arc as an instance of {@link EllipseCurve} to the path.
	 *
	 * @param {number} [aX=0] - The x coordinate of the center of the arc.
	 * @param {number} [aY=0] - The y coordinate of the center of the arc.
	 * @param {number} [aRadius=1] - The radius of the arc.
	 * @param {number} [aStartAngle=0] - The start angle in radians.
	 * @param {number} [aEndAngle=Math.PI*2] - The end angle in radians.
	 * @param {boolean} [aClockwise=false] - Whether to sweep the arc clockwise or not.
	 * @return {Path} A reference to this path.
	 */
```

**Parameters:**

- **`aX`** `number`
- **`aY`** `number`
- **`aRadius`** `number`
- **`aStartAngle`** `number`
- **`aEndAngle`** `number`
- **`aClockwise`** `boolean`

**Returns:** `Path`

**Calls:**

- `this.absellipse`

<details><summary>Code</summary>

```typescript
absarc( aX, aY, aRadius, aStartAngle, aEndAngle, aClockwise ) {

		this.absellipse( aX, aY, aRadius, aRadius, aStartAngle, aEndAngle, aClockwise );

		return this;

	}
```
</details>

### `Path.ellipse(aX: number, aY: number, xRadius: number, yRadius: number, aStartAngle: number, aEndAngle: number, aClockwise: boolean, aRotation: number): Path`

**JSDoc:**
```typescript
/**
	 * Adds an ellipse as an instance of {@link EllipseCurve} to the path, positioned relative
	 * to the current point
	 *
	 * @param {number} [aX=0] - The x coordinate of the center of the ellipse offsetted from the previous curve.
	 * @param {number} [aY=0] - The y coordinate of the center of the ellipse offsetted from the previous curve.
	 * @param {number} [xRadius=1] - The radius of the ellipse in the x axis.
	 * @param {number} [yRadius=1] - The radius of the ellipse in the y axis.
	 * @param {number} [aStartAngle=0] - The start angle in radians.
	 * @param {number} [aEndAngle=Math.PI*2] - The end angle in radians.
	 * @param {boolean} [aClockwise=false] - Whether to sweep the ellipse clockwise or not.
	 * @param {number} [aRotation=0] - The rotation angle of the ellipse in radians, counterclockwise from the positive X axis.
	 * @return {Path} A reference to this path.
	 */
```

**Parameters:**

- **`aX`** `number`
- **`aY`** `number`
- **`xRadius`** `number`
- **`yRadius`** `number`
- **`aStartAngle`** `number`
- **`aEndAngle`** `number`
- **`aClockwise`** `boolean`
- **`aRotation`** `number`

**Returns:** `Path`

**Calls:**

- `this.absellipse`

<details><summary>Code</summary>

```typescript
ellipse( aX, aY, xRadius, yRadius, aStartAngle, aEndAngle, aClockwise, aRotation ) {

		const x0 = this.currentPoint.x;
		const y0 = this.currentPoint.y;

		this.absellipse( aX + x0, aY + y0, xRadius, yRadius, aStartAngle, aEndAngle, aClockwise, aRotation );

		return this;

	}
```
</details>

### `Path.absellipse(aX: number, aY: number, xRadius: number, yRadius: number, aStartAngle: number, aEndAngle: number, aClockwise: boolean, aRotation: number): Path`

**JSDoc:**
```typescript
/**
	 * Adds an absolutely positioned ellipse as an instance of {@link EllipseCurve} to the path.
	 *
	 * @param {number} [aX=0] - The x coordinate of the absolute center of the ellipse.
	 * @param {number} [aY=0] - The y coordinate of the absolute center of the ellipse.
	 * @param {number} [xRadius=1] - The radius of the ellipse in the x axis.
	 * @param {number} [yRadius=1] - The radius of the ellipse in the y axis.
	 * @param {number} [aStartAngle=0] - The start angle in radians.
	 * @param {number} [aEndAngle=Math.PI*2] - The end angle in radians.
	 * @param {boolean} [aClockwise=false] - Whether to sweep the ellipse clockwise or not.
	 * @param {number} [aRotation=0] - The rotation angle of the ellipse in radians, counterclockwise from the positive X axis.
	 * @return {Path} A reference to this path.
	 */
```

**Parameters:**

- **`aX`** `number`
- **`aY`** `number`
- **`xRadius`** `number`
- **`yRadius`** `number`
- **`aStartAngle`** `number`
- **`aEndAngle`** `number`
- **`aClockwise`** `boolean`
- **`aRotation`** `number`

**Returns:** `Path`

**Calls:**

- `curve.getPoint`
- `firstPoint.equals`
- `this.lineTo`
- `this.curves.push`
- `this.currentPoint.copy`

**Internal Comments:**
```
// if a previous curve is present, attempt to join (x2)
```

<details><summary>Code</summary>

```typescript
absellipse( aX, aY, xRadius, yRadius, aStartAngle, aEndAngle, aClockwise, aRotation ) {

		const curve = new EllipseCurve( aX, aY, xRadius, yRadius, aStartAngle, aEndAngle, aClockwise, aRotation );

		if ( this.curves.length > 0 ) {

			// if a previous curve is present, attempt to join
			const firstPoint = curve.getPoint( 0 );

			if ( ! firstPoint.equals( this.currentPoint ) ) {

				this.lineTo( firstPoint.x, firstPoint.y );

			}

		}

		this.curves.push( curve );

		const lastPoint = curve.getPoint( 1 );
		this.currentPoint.copy( lastPoint );

		return this;

	}
```
</details>

### `Path.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.currentPoint.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.currentPoint.copy( source.currentPoint );

		return this;

	}
```
</details>

### `Path.toJSON(): any`

**Returns:** `any`

**Calls:**

- `super.toJSON`
- `this.currentPoint.toArray`

<details><summary>Code</summary>

```typescript
toJSON() {

		const data = super.toJSON();

		data.currentPoint = this.currentPoint.toArray();

		return data;

	}
```
</details>

### `Path.fromJSON(json: any): this`

**Parameters:**

- **`json`** `any`

**Returns:** `this`

**Calls:**

- `super.fromJSON`
- `this.currentPoint.fromArray`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		super.fromJSON( json );

		this.currentPoint.fromArray( json.currentPoint );

		return this;

	}
```
</details>


---

## Classes

### `Path`

<details><summary>Class Code</summary>

```ts
class Path extends CurvePath {

	/**
	 * Constructs a new path.
	 *
	 * @param {Array<Vector2>} [points] - An array of 2D points defining the path.
	 */
	constructor( points ) {

		super();

		this.type = 'Path';

		/**
		 * The current offset of the path. Any new curve added will start here.
		 *
		 * @type {Vector2}
		 */
		this.currentPoint = new Vector2();

		if ( points ) {

			this.setFromPoints( points );

		}

	}

	/**
	 * Creates a path from the given list of points. The points are added
	 * to the path as instances of {@link LineCurve}.
	 *
	 * @param {Array<Vector2>} points - An array of 2D points.
	 * @return {Path} A reference to this path.
	 */
	setFromPoints( points ) {

		this.moveTo( points[ 0 ].x, points[ 0 ].y );

		for ( let i = 1, l = points.length; i < l; i ++ ) {

			this.lineTo( points[ i ].x, points[ i ].y );

		}

		return this;

	}

	/**
	 * Moves {@link Path#currentPoint} to the given point.
	 *
	 * @param {number} x - The x coordinate.
	 * @param {number} y - The y coordinate.
	 * @return {Path} A reference to this path.
	 */
	moveTo( x, y ) {

		this.currentPoint.set( x, y ); // TODO consider referencing vectors instead of copying?

		return this;

	}

	/**
	 * Adds an instance of {@link LineCurve} to the path by connecting
	 * the current point with the given one.
	 *
	 * @param {number} x - The x coordinate of the end point.
	 * @param {number} y - The y coordinate of the end point.
	 * @return {Path} A reference to this path.
	 */
	lineTo( x, y ) {

		const curve = new LineCurve( this.currentPoint.clone(), new Vector2( x, y ) );
		this.curves.push( curve );

		this.currentPoint.set( x, y );

		return this;

	}

	/**
	 * Adds an instance of {@link QuadraticBezierCurve} to the path by connecting
	 * the current point with the given one.
	 *
	 * @param {number} aCPx - The x coordinate of the control point.
	 * @param {number} aCPy - The y coordinate of the control point.
	 * @param {number} aX - The x coordinate of the end point.
	 * @param {number} aY - The y coordinate of the end point.
	 * @return {Path} A reference to this path.
	 */
	quadraticCurveTo( aCPx, aCPy, aX, aY ) {

		const curve = new QuadraticBezierCurve(
			this.currentPoint.clone(),
			new Vector2( aCPx, aCPy ),
			new Vector2( aX, aY )
		);

		this.curves.push( curve );

		this.currentPoint.set( aX, aY );

		return this;

	}

	/**
	 * Adds an instance of {@link CubicBezierCurve} to the path by connecting
	 * the current point with the given one.
	 *
	 * @param {number} aCP1x - The x coordinate of the first control point.
	 * @param {number} aCP1y - The y coordinate of the first control point.
	 * @param {number} aCP2x - The x coordinate of the second control point.
	 * @param {number} aCP2y - The y coordinate of the second control point.
	 * @param {number} aX - The x coordinate of the end point.
	 * @param {number} aY - The y coordinate of the end point.
	 * @return {Path} A reference to this path.
	 */
	bezierCurveTo( aCP1x, aCP1y, aCP2x, aCP2y, aX, aY ) {

		const curve = new CubicBezierCurve(
			this.currentPoint.clone(),
			new Vector2( aCP1x, aCP1y ),
			new Vector2( aCP2x, aCP2y ),
			new Vector2( aX, aY )
		);

		this.curves.push( curve );

		this.currentPoint.set( aX, aY );

		return this;

	}

	/**
	 * Adds an instance of {@link SplineCurve} to the path by connecting
	 * the current point with the given list of points.
	 *
	 * @param {Array<Vector2>} pts - An array of points in 2D space.
	 * @return {Path} A reference to this path.
	 */
	splineThru( pts ) {

		const npts = [ this.currentPoint.clone() ].concat( pts );

		const curve = new SplineCurve( npts );
		this.curves.push( curve );

		this.currentPoint.copy( pts[ pts.length - 1 ] );

		return this;

	}

	/**
	 * Adds an arc as an instance of {@link EllipseCurve} to the path, positioned relative
	 * to the current point.
	 *
	 * @param {number} [aX=0] - The x coordinate of the center of the arc offsetted from the previous curve.
	 * @param {number} [aY=0] - The y coordinate of the center of the arc offsetted from the previous curve.
	 * @param {number} [aRadius=1] - The radius of the arc.
	 * @param {number} [aStartAngle=0] - The start angle in radians.
	 * @param {number} [aEndAngle=Math.PI*2] - The end angle in radians.
	 * @param {boolean} [aClockwise=false] - Whether to sweep the arc clockwise or not.
	 * @return {Path} A reference to this path.
	 */
	arc( aX, aY, aRadius, aStartAngle, aEndAngle, aClockwise ) {

		const x0 = this.currentPoint.x;
		const y0 = this.currentPoint.y;

		this.absarc( aX + x0, aY + y0, aRadius,
			aStartAngle, aEndAngle, aClockwise );

		return this;

	}

	/**
	 * Adds an absolutely positioned arc as an instance of {@link EllipseCurve} to the path.
	 *
	 * @param {number} [aX=0] - The x coordinate of the center of the arc.
	 * @param {number} [aY=0] - The y coordinate of the center of the arc.
	 * @param {number} [aRadius=1] - The radius of the arc.
	 * @param {number} [aStartAngle=0] - The start angle in radians.
	 * @param {number} [aEndAngle=Math.PI*2] - The end angle in radians.
	 * @param {boolean} [aClockwise=false] - Whether to sweep the arc clockwise or not.
	 * @return {Path} A reference to this path.
	 */
	absarc( aX, aY, aRadius, aStartAngle, aEndAngle, aClockwise ) {

		this.absellipse( aX, aY, aRadius, aRadius, aStartAngle, aEndAngle, aClockwise );

		return this;

	}

	/**
	 * Adds an ellipse as an instance of {@link EllipseCurve} to the path, positioned relative
	 * to the current point
	 *
	 * @param {number} [aX=0] - The x coordinate of the center of the ellipse offsetted from the previous curve.
	 * @param {number} [aY=0] - The y coordinate of the center of the ellipse offsetted from the previous curve.
	 * @param {number} [xRadius=1] - The radius of the ellipse in the x axis.
	 * @param {number} [yRadius=1] - The radius of the ellipse in the y axis.
	 * @param {number} [aStartAngle=0] - The start angle in radians.
	 * @param {number} [aEndAngle=Math.PI*2] - The end angle in radians.
	 * @param {boolean} [aClockwise=false] - Whether to sweep the ellipse clockwise or not.
	 * @param {number} [aRotation=0] - The rotation angle of the ellipse in radians, counterclockwise from the positive X axis.
	 * @return {Path} A reference to this path.
	 */
	ellipse( aX, aY, xRadius, yRadius, aStartAngle, aEndAngle, aClockwise, aRotation ) {

		const x0 = this.currentPoint.x;
		const y0 = this.currentPoint.y;

		this.absellipse( aX + x0, aY + y0, xRadius, yRadius, aStartAngle, aEndAngle, aClockwise, aRotation );

		return this;

	}

	/**
	 * Adds an absolutely positioned ellipse as an instance of {@link EllipseCurve} to the path.
	 *
	 * @param {number} [aX=0] - The x coordinate of the absolute center of the ellipse.
	 * @param {number} [aY=0] - The y coordinate of the absolute center of the ellipse.
	 * @param {number} [xRadius=1] - The radius of the ellipse in the x axis.
	 * @param {number} [yRadius=1] - The radius of the ellipse in the y axis.
	 * @param {number} [aStartAngle=0] - The start angle in radians.
	 * @param {number} [aEndAngle=Math.PI*2] - The end angle in radians.
	 * @param {boolean} [aClockwise=false] - Whether to sweep the ellipse clockwise or not.
	 * @param {number} [aRotation=0] - The rotation angle of the ellipse in radians, counterclockwise from the positive X axis.
	 * @return {Path} A reference to this path.
	 */
	absellipse( aX, aY, xRadius, yRadius, aStartAngle, aEndAngle, aClockwise, aRotation ) {

		const curve = new EllipseCurve( aX, aY, xRadius, yRadius, aStartAngle, aEndAngle, aClockwise, aRotation );

		if ( this.curves.length > 0 ) {

			// if a previous curve is present, attempt to join
			const firstPoint = curve.getPoint( 0 );

			if ( ! firstPoint.equals( this.currentPoint ) ) {

				this.lineTo( firstPoint.x, firstPoint.y );

			}

		}

		this.curves.push( curve );

		const lastPoint = curve.getPoint( 1 );
		this.currentPoint.copy( lastPoint );

		return this;

	}

	copy( source ) {

		super.copy( source );

		this.currentPoint.copy( source.currentPoint );

		return this;

	}

	toJSON() {

		const data = super.toJSON();

		data.currentPoint = this.currentPoint.toArray();

		return data;

	}

	fromJSON( json ) {

		super.fromJSON( json );

		this.currentPoint.fromArray( json.currentPoint );

		return this;

	}

}
```
</details>

#### Methods

##### `setFromPoints(points: Vector2[]): Path`

<details><summary>Code</summary>

```ts
setFromPoints( points ) {

		this.moveTo( points[ 0 ].x, points[ 0 ].y );

		for ( let i = 1, l = points.length; i < l; i ++ ) {

			this.lineTo( points[ i ].x, points[ i ].y );

		}

		return this;

	}
```
</details>

##### `moveTo(x: number, y: number): Path`

<details><summary>Code</summary>

```ts
moveTo( x, y ) {

		this.currentPoint.set( x, y ); // TODO consider referencing vectors instead of copying?

		return this;

	}
```
</details>

##### `lineTo(x: number, y: number): Path`

<details><summary>Code</summary>

```ts
lineTo( x, y ) {

		const curve = new LineCurve( this.currentPoint.clone(), new Vector2( x, y ) );
		this.curves.push( curve );

		this.currentPoint.set( x, y );

		return this;

	}
```
</details>

##### `quadraticCurveTo(aCPx: number, aCPy: number, aX: number, aY: number): Path`

<details><summary>Code</summary>

```ts
quadraticCurveTo( aCPx, aCPy, aX, aY ) {

		const curve = new QuadraticBezierCurve(
			this.currentPoint.clone(),
			new Vector2( aCPx, aCPy ),
			new Vector2( aX, aY )
		);

		this.curves.push( curve );

		this.currentPoint.set( aX, aY );

		return this;

	}
```
</details>

##### `bezierCurveTo(aCP1x: number, aCP1y: number, aCP2x: number, aCP2y: number, aX: number, aY: number): Path`

<details><summary>Code</summary>

```ts
bezierCurveTo( aCP1x, aCP1y, aCP2x, aCP2y, aX, aY ) {

		const curve = new CubicBezierCurve(
			this.currentPoint.clone(),
			new Vector2( aCP1x, aCP1y ),
			new Vector2( aCP2x, aCP2y ),
			new Vector2( aX, aY )
		);

		this.curves.push( curve );

		this.currentPoint.set( aX, aY );

		return this;

	}
```
</details>

##### `splineThru(pts: Vector2[]): Path`

<details><summary>Code</summary>

```ts
splineThru( pts ) {

		const npts = [ this.currentPoint.clone() ].concat( pts );

		const curve = new SplineCurve( npts );
		this.curves.push( curve );

		this.currentPoint.copy( pts[ pts.length - 1 ] );

		return this;

	}
```
</details>

##### `arc(aX: number, aY: number, aRadius: number, aStartAngle: number, aEndAngle: number, aClockwise: boolean): Path`

<details><summary>Code</summary>

```ts
arc( aX, aY, aRadius, aStartAngle, aEndAngle, aClockwise ) {

		const x0 = this.currentPoint.x;
		const y0 = this.currentPoint.y;

		this.absarc( aX + x0, aY + y0, aRadius,
			aStartAngle, aEndAngle, aClockwise );

		return this;

	}
```
</details>

##### `absarc(aX: number, aY: number, aRadius: number, aStartAngle: number, aEndAngle: number, aClockwise: boolean): Path`

<details><summary>Code</summary>

```ts
absarc( aX, aY, aRadius, aStartAngle, aEndAngle, aClockwise ) {

		this.absellipse( aX, aY, aRadius, aRadius, aStartAngle, aEndAngle, aClockwise );

		return this;

	}
```
</details>

##### `ellipse(aX: number, aY: number, xRadius: number, yRadius: number, aStartAngle: number, aEndAngle: number, aClockwise: boolean, aRotation: number): Path`

<details><summary>Code</summary>

```ts
ellipse( aX, aY, xRadius, yRadius, aStartAngle, aEndAngle, aClockwise, aRotation ) {

		const x0 = this.currentPoint.x;
		const y0 = this.currentPoint.y;

		this.absellipse( aX + x0, aY + y0, xRadius, yRadius, aStartAngle, aEndAngle, aClockwise, aRotation );

		return this;

	}
```
</details>

##### `absellipse(aX: number, aY: number, xRadius: number, yRadius: number, aStartAngle: number, aEndAngle: number, aClockwise: boolean, aRotation: number): Path`

<details><summary>Code</summary>

```ts
absellipse( aX, aY, xRadius, yRadius, aStartAngle, aEndAngle, aClockwise, aRotation ) {

		const curve = new EllipseCurve( aX, aY, xRadius, yRadius, aStartAngle, aEndAngle, aClockwise, aRotation );

		if ( this.curves.length > 0 ) {

			// if a previous curve is present, attempt to join
			const firstPoint = curve.getPoint( 0 );

			if ( ! firstPoint.equals( this.currentPoint ) ) {

				this.lineTo( firstPoint.x, firstPoint.y );

			}

		}

		this.curves.push( curve );

		const lastPoint = curve.getPoint( 1 );
		this.currentPoint.copy( lastPoint );

		return this;

	}
```
</details>

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source );

		this.currentPoint.copy( source.currentPoint );

		return this;

	}
```
</details>

##### `toJSON(): any`

<details><summary>Code</summary>

```ts
toJSON() {

		const data = super.toJSON();

		data.currentPoint = this.currentPoint.toArray();

		return data;

	}
```
</details>

##### `fromJSON(json: any): this`

<details><summary>Code</summary>

```ts
fromJSON( json ) {

		super.fromJSON( json );

		this.currentPoint.fromArray( json.currentPoint );

		return this;

	}
```
</details>


---