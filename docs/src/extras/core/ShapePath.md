[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ShapePath.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 28 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/extras/core/ShapePath.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `../../math/Color.js` |
| `Path` | `./Path.js` |
| `Shape` | `./Shape.js` |
| `ShapeUtils` | `../ShapeUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `shapes` | `any[]` | let/var | `[]` | ✗ |
| `tmpPath` | `any` | let/var | `inSubpaths[ i ]` | ✗ |
| `tmpShape` | `Shape` | let/var | `new Shape()` | ✗ |
| `polyLen` | `any` | let/var | `inPolygon.length` | ✗ |
| `inside` | `boolean` | let/var | `false` | ✗ |
| `edgeLowPt` | `any` | let/var | `inPolygon[ p ]` | ✗ |
| `edgeHighPt` | `any` | let/var | `inPolygon[ q ]` | ✗ |
| `edgeDx` | `number` | let/var | `edgeHighPt.x - edgeLowPt.x` | ✗ |
| `edgeDy` | `number` | let/var | `edgeHighPt.y - edgeLowPt.y` | ✗ |
| `perpEdge` | `number` | let/var | `edgeDy * ( inPt.x - edgeLowPt.x ) - edgeDx * ( inPt.y - edgeLowPt.y )` | ✗ |
| `isClockWise` | `(pts: Vector2[]) => boolean` | let/var | `ShapeUtils.isClockWise` | ✗ |
| `subPaths` | `Path[]` | let/var | `this.subPaths` | ✗ |
| `solid` | `any` | let/var | `*not shown*` | ✗ |
| `tmpPath` | `any` | let/var | `*not shown*` | ✗ |
| `tmpShape` | `any` | let/var | `*not shown*` | ✗ |
| `shapes` | `any[]` | let/var | `[]` | ✗ |
| `holesFirst` | `boolean` | let/var | `! isClockWise( subPaths[ 0 ].getPoints() )` | ✗ |
| `betterShapeHoles` | `any[]` | let/var | `[]` | ✗ |
| `newShapes` | `any[]` | let/var | `[]` | ✗ |
| `newShapeHoles` | `any[]` | let/var | `[]` | ✗ |
| `mainIdx` | `number` | let/var | `0` | ✗ |
| `tmpPoints` | `any` | let/var | `*not shown*` | ✗ |
| `ambiguous` | `boolean` | let/var | `false` | ✗ |
| `toChange` | `number` | let/var | `0` | ✗ |
| `sho` | `any[]` | let/var | `newShapeHoles[ sIdx ]` | ✗ |
| `ho` | `any` | let/var | `sho[ hIdx ]` | ✗ |
| `hole_unassigned` | `boolean` | let/var | `true` | ✗ |
| `tmpHoles` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `ShapePath.moveTo(x: number, y: number): ShapePath`

**JSDoc:**
```typescript
/**
	 * Creates a new path and moves it current point to the given one.
	 *
	 * @param {number} x - The x coordinate.
	 * @param {number} y - The y coordinate.
	 * @return {ShapePath} A reference to this shape path.
	 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`

**Returns:** `ShapePath`

**Calls:**

- `this.subPaths.push`
- `this.currentPath.moveTo`

<details><summary>Code</summary>

```typescript
moveTo( x, y ) {

		this.currentPath = new Path();
		this.subPaths.push( this.currentPath );
		this.currentPath.moveTo( x, y );

		return this;

	}
```
</details>

### `ShapePath.lineTo(x: number, y: number): ShapePath`

**JSDoc:**
```typescript
/**
	 * Adds an instance of {@link LineCurve} to the path by connecting
	 * the current point with the given one.
	 *
	 * @param {number} x - The x coordinate of the end point.
	 * @param {number} y - The y coordinate of the end point.
	 * @return {ShapePath} A reference to this shape path.
	 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`

**Returns:** `ShapePath`

**Calls:**

- `this.currentPath.lineTo`

<details><summary>Code</summary>

```typescript
lineTo( x, y ) {

		this.currentPath.lineTo( x, y );

		return this;

	}
```
</details>

### `ShapePath.quadraticCurveTo(aCPx: number, aCPy: number, aX: number, aY: number): ShapePath`

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
	 * @return {ShapePath} A reference to this shape path.
	 */
```

**Parameters:**

- **`aCPx`** `number`
- **`aCPy`** `number`
- **`aX`** `number`
- **`aY`** `number`

**Returns:** `ShapePath`

**Calls:**

- `this.currentPath.quadraticCurveTo`

<details><summary>Code</summary>

```typescript
quadraticCurveTo( aCPx, aCPy, aX, aY ) {

		this.currentPath.quadraticCurveTo( aCPx, aCPy, aX, aY );

		return this;

	}
```
</details>

### `ShapePath.bezierCurveTo(aCP1x: number, aCP1y: number, aCP2x: number, aCP2y: number, aX: number, aY: number): ShapePath`

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
	 * @return {ShapePath} A reference to this shape path.
	 */
```

**Parameters:**

- **`aCP1x`** `number`
- **`aCP1y`** `number`
- **`aCP2x`** `number`
- **`aCP2y`** `number`
- **`aX`** `number`
- **`aY`** `number`

**Returns:** `ShapePath`

**Calls:**

- `this.currentPath.bezierCurveTo`

<details><summary>Code</summary>

```typescript
bezierCurveTo( aCP1x, aCP1y, aCP2x, aCP2y, aX, aY ) {

		this.currentPath.bezierCurveTo( aCP1x, aCP1y, aCP2x, aCP2y, aX, aY );

		return this;

	}
```
</details>

### `ShapePath.splineThru(pts: Vector2[]): ShapePath`

**JSDoc:**
```typescript
/**
	 * Adds an instance of {@link SplineCurve} to the path by connecting
	 * the current point with the given list of points.
	 *
	 * @param {Array<Vector2>} pts - An array of points in 2D space.
	 * @return {ShapePath} A reference to this shape path.
	 */
```

**Parameters:**

- **`pts`** `Vector2[]`

**Returns:** `ShapePath`

**Calls:**

- `this.currentPath.splineThru`

<details><summary>Code</summary>

```typescript
splineThru( pts ) {

		this.currentPath.splineThru( pts );

		return this;

	}
```
</details>

### `ShapePath.toShapes(isCCW: boolean): Shape[]`

**JSDoc:**
```typescript
/**
	 * Converts the paths into an array of shapes.
	 *
	 * @param {boolean} isCCW - By default solid shapes are  defined clockwise (CW) and holes are defined counterclockwise (CCW).
	 * If this flag is set to `true`, then those are flipped.
	 * @return {Array<Shape>} An array of shapes.
	 */
```

**Parameters:**

- **`isCCW`** `boolean`

**Returns:** `Shape[]`

**Calls:**

- `shapes.push`
- `Math.abs`
- `isClockWise`
- `subPaths[ 0 ].getPoints`
- `tmpPath.getPoints`
- `newShapeHoles[ mainIdx ].push`
- `toShapesNoHoles`
- `isPointInsidePolygon`
- `betterShapeHoles[ s2Idx ].push`
- `betterShapeHoles[ sIdx ].push`
- `tmpShape.holes.push`

**Internal Comments:**
```
// inPt on polygon contour => immediate success    or (x2)
// toggling of inside/outside at every single! intersection point of an edge (x2)
//  with the horizontal line through inPt, left of inPt (x2)
//  not counting lowerY endpoints of edges and whole edges on that line (x2)
// not parallel
// parallel or collinear
// edge lies on the same horizontal line as inPt
// console.log("Holes first", holesFirst); (x2)
// only Holes? -> probably all Shapes with wrong orientation
//console.log("shape", shapes);
```

<details><summary>Code</summary>

```typescript
toShapes( isCCW ) {

		function toShapesNoHoles( inSubpaths ) {

			const shapes = [];

			for ( let i = 0, l = inSubpaths.length; i < l; i ++ ) {

				const tmpPath = inSubpaths[ i ];

				const tmpShape = new Shape();
				tmpShape.curves = tmpPath.curves;

				shapes.push( tmpShape );

			}

			return shapes;

		}

		function isPointInsidePolygon( inPt, inPolygon ) {

			const polyLen = inPolygon.length;

			// inPt on polygon contour => immediate success    or
			// toggling of inside/outside at every single! intersection point of an edge
			//  with the horizontal line through inPt, left of inPt
			//  not counting lowerY endpoints of edges and whole edges on that line
			let inside = false;
			for ( let p = polyLen - 1, q = 0; q < polyLen; p = q ++ ) {

				let edgeLowPt = inPolygon[ p ];
				let edgeHighPt = inPolygon[ q ];

				let edgeDx = edgeHighPt.x - edgeLowPt.x;
				let edgeDy = edgeHighPt.y - edgeLowPt.y;

				if ( Math.abs( edgeDy ) > Number.EPSILON ) {

					// not parallel
					if ( edgeDy < 0 ) {

						edgeLowPt = inPolygon[ q ]; edgeDx = - edgeDx;
						edgeHighPt = inPolygon[ p ]; edgeDy = - edgeDy;

					}

					if ( ( inPt.y < edgeLowPt.y ) || ( inPt.y > edgeHighPt.y ) ) 		continue;

					if ( inPt.y === edgeLowPt.y ) {

						if ( inPt.x === edgeLowPt.x )		return	true;		// inPt is on contour ?
						// continue;				// no intersection or edgeLowPt => doesn't count !!!

					} else {

						const perpEdge = edgeDy * ( inPt.x - edgeLowPt.x ) - edgeDx * ( inPt.y - edgeLowPt.y );
						if ( perpEdge === 0 )				return	true;		// inPt is on contour ?
						if ( perpEdge < 0 ) 				continue;
						inside = ! inside;		// true intersection left of inPt

					}

				} else {

					// parallel or collinear
					if ( inPt.y !== edgeLowPt.y ) 		continue;			// parallel
					// edge lies on the same horizontal line as inPt
					if ( ( ( edgeHighPt.x <= inPt.x ) && ( inPt.x <= edgeLowPt.x ) ) ||
						 ( ( edgeLowPt.x <= inPt.x ) && ( inPt.x <= edgeHighPt.x ) ) )		return	true;	// inPt: Point on contour !
					// continue;

				}

			}

			return	inside;

		}

		const isClockWise = ShapeUtils.isClockWise;

		const subPaths = this.subPaths;
		if ( subPaths.length === 0 ) return [];

		let solid, tmpPath, tmpShape;
		const shapes = [];

		if ( subPaths.length === 1 ) {

			tmpPath = subPaths[ 0 ];
			tmpShape = new Shape();
			tmpShape.curves = tmpPath.curves;
			shapes.push( tmpShape );
			return shapes;

		}

		let holesFirst = ! isClockWise( subPaths[ 0 ].getPoints() );
		holesFirst = isCCW ? ! holesFirst : holesFirst;

		// console.log("Holes first", holesFirst);

		const betterShapeHoles = [];
		const newShapes = [];
		let newShapeHoles = [];
		let mainIdx = 0;
		let tmpPoints;

		newShapes[ mainIdx ] = undefined;
		newShapeHoles[ mainIdx ] = [];

		for ( let i = 0, l = subPaths.length; i < l; i ++ ) {

			tmpPath = subPaths[ i ];
			tmpPoints = tmpPath.getPoints();
			solid = isClockWise( tmpPoints );
			solid = isCCW ? ! solid : solid;

			if ( solid ) {

				if ( ( ! holesFirst ) && ( newShapes[ mainIdx ] ) )	mainIdx ++;

				newShapes[ mainIdx ] = { s: new Shape(), p: tmpPoints };
				newShapes[ mainIdx ].s.curves = tmpPath.curves;

				if ( holesFirst )	mainIdx ++;
				newShapeHoles[ mainIdx ] = [];

				//console.log('cw', i);

			} else {

				newShapeHoles[ mainIdx ].push( { h: tmpPath, p: tmpPoints[ 0 ] } );

				//console.log('ccw', i);

			}

		}

		// only Holes? -> probably all Shapes with wrong orientation
		if ( ! newShapes[ 0 ] )	return	toShapesNoHoles( subPaths );


		if ( newShapes.length > 1 ) {

			let ambiguous = false;
			let toChange = 0;

			for ( let sIdx = 0, sLen = newShapes.length; sIdx < sLen; sIdx ++ ) {

				betterShapeHoles[ sIdx ] = [];

			}

			for ( let sIdx = 0, sLen = newShapes.length; sIdx < sLen; sIdx ++ ) {

				const sho = newShapeHoles[ sIdx ];

				for ( let hIdx = 0; hIdx < sho.length; hIdx ++ ) {

					const ho = sho[ hIdx ];
					let hole_unassigned = true;

					for ( let s2Idx = 0; s2Idx < newShapes.length; s2Idx ++ ) {

						if ( isPointInsidePolygon( ho.p, newShapes[ s2Idx ].p ) ) {

							if ( sIdx !== s2Idx )	toChange ++;

							if ( hole_unassigned ) {

								hole_unassigned = false;
								betterShapeHoles[ s2Idx ].push( ho );

							} else {

								ambiguous = true;

							}

						}

					}

					if ( hole_unassigned ) {

						betterShapeHoles[ sIdx ].push( ho );

					}

				}

			}

			if ( toChange > 0 && ambiguous === false ) {

				newShapeHoles = betterShapeHoles;

			}

		}

		let tmpHoles;

		for ( let i = 0, il = newShapes.length; i < il; i ++ ) {

			tmpShape = newShapes[ i ].s;
			shapes.push( tmpShape );
			tmpHoles = newShapeHoles[ i ];

			for ( let j = 0, jl = tmpHoles.length; j < jl; j ++ ) {

				tmpShape.holes.push( tmpHoles[ j ].h );

			}

		}

		//console.log("shape", shapes);

		return shapes;

	}
```
</details>

### `toShapesNoHoles(inSubpaths: any): Shape[]`

**Parameters:**

- **`inSubpaths`** `any`

**Returns:** `Shape[]`

**Calls:**

- `shapes.push`

<details><summary>Code</summary>

```typescript
function toShapesNoHoles( inSubpaths ) {

			const shapes = [];

			for ( let i = 0, l = inSubpaths.length; i < l; i ++ ) {

				const tmpPath = inSubpaths[ i ];

				const tmpShape = new Shape();
				tmpShape.curves = tmpPath.curves;

				shapes.push( tmpShape );

			}

			return shapes;

		}
```
</details>

### `isPointInsidePolygon(inPt: any, inPolygon: any): boolean`

**Parameters:**

- **`inPt`** `any`
- **`inPolygon`** `any`

**Returns:** `boolean`

**Calls:**

- `Math.abs`

**Internal Comments:**
```
// inPt on polygon contour => immediate success    or (x2)
// toggling of inside/outside at every single! intersection point of an edge (x2)
//  with the horizontal line through inPt, left of inPt (x2)
//  not counting lowerY endpoints of edges and whole edges on that line (x2)
// not parallel
// parallel or collinear
// edge lies on the same horizontal line as inPt
```

<details><summary>Code</summary>

```typescript
function isPointInsidePolygon( inPt, inPolygon ) {

			const polyLen = inPolygon.length;

			// inPt on polygon contour => immediate success    or
			// toggling of inside/outside at every single! intersection point of an edge
			//  with the horizontal line through inPt, left of inPt
			//  not counting lowerY endpoints of edges and whole edges on that line
			let inside = false;
			for ( let p = polyLen - 1, q = 0; q < polyLen; p = q ++ ) {

				let edgeLowPt = inPolygon[ p ];
				let edgeHighPt = inPolygon[ q ];

				let edgeDx = edgeHighPt.x - edgeLowPt.x;
				let edgeDy = edgeHighPt.y - edgeLowPt.y;

				if ( Math.abs( edgeDy ) > Number.EPSILON ) {

					// not parallel
					if ( edgeDy < 0 ) {

						edgeLowPt = inPolygon[ q ]; edgeDx = - edgeDx;
						edgeHighPt = inPolygon[ p ]; edgeDy = - edgeDy;

					}

					if ( ( inPt.y < edgeLowPt.y ) || ( inPt.y > edgeHighPt.y ) ) 		continue;

					if ( inPt.y === edgeLowPt.y ) {

						if ( inPt.x === edgeLowPt.x )		return	true;		// inPt is on contour ?
						// continue;				// no intersection or edgeLowPt => doesn't count !!!

					} else {

						const perpEdge = edgeDy * ( inPt.x - edgeLowPt.x ) - edgeDx * ( inPt.y - edgeLowPt.y );
						if ( perpEdge === 0 )				return	true;		// inPt is on contour ?
						if ( perpEdge < 0 ) 				continue;
						inside = ! inside;		// true intersection left of inPt

					}

				} else {

					// parallel or collinear
					if ( inPt.y !== edgeLowPt.y ) 		continue;			// parallel
					// edge lies on the same horizontal line as inPt
					if ( ( ( edgeHighPt.x <= inPt.x ) && ( inPt.x <= edgeLowPt.x ) ) ||
						 ( ( edgeLowPt.x <= inPt.x ) && ( inPt.x <= edgeHighPt.x ) ) )		return	true;	// inPt: Point on contour !
					// continue;

				}

			}

			return	inside;

		}
```
</details>


---

## Classes

### `ShapePath`

<details><summary>Class Code</summary>

```ts
class ShapePath {

	/**
	 * Constructs a new shape path.
	 */
	constructor() {

		this.type = 'ShapePath';

		/**
		 * The color of the shape.
		 *
		 * @type {Color}
		 */
		this.color = new Color();

		/**
		 * The paths that have been generated for this shape.
		 *
		 * @type {Array<Path>}
		 * @default null
		 */
		this.subPaths = [];

		/**
		 * The current path that is being generated.
		 *
		 * @type {?Path}
		 * @default null
		 */
		this.currentPath = null;

	}

	/**
	 * Creates a new path and moves it current point to the given one.
	 *
	 * @param {number} x - The x coordinate.
	 * @param {number} y - The y coordinate.
	 * @return {ShapePath} A reference to this shape path.
	 */
	moveTo( x, y ) {

		this.currentPath = new Path();
		this.subPaths.push( this.currentPath );
		this.currentPath.moveTo( x, y );

		return this;

	}

	/**
	 * Adds an instance of {@link LineCurve} to the path by connecting
	 * the current point with the given one.
	 *
	 * @param {number} x - The x coordinate of the end point.
	 * @param {number} y - The y coordinate of the end point.
	 * @return {ShapePath} A reference to this shape path.
	 */
	lineTo( x, y ) {

		this.currentPath.lineTo( x, y );

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
	 * @return {ShapePath} A reference to this shape path.
	 */
	quadraticCurveTo( aCPx, aCPy, aX, aY ) {

		this.currentPath.quadraticCurveTo( aCPx, aCPy, aX, aY );

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
	 * @return {ShapePath} A reference to this shape path.
	 */
	bezierCurveTo( aCP1x, aCP1y, aCP2x, aCP2y, aX, aY ) {

		this.currentPath.bezierCurveTo( aCP1x, aCP1y, aCP2x, aCP2y, aX, aY );

		return this;

	}

	/**
	 * Adds an instance of {@link SplineCurve} to the path by connecting
	 * the current point with the given list of points.
	 *
	 * @param {Array<Vector2>} pts - An array of points in 2D space.
	 * @return {ShapePath} A reference to this shape path.
	 */
	splineThru( pts ) {

		this.currentPath.splineThru( pts );

		return this;

	}

	/**
	 * Converts the paths into an array of shapes.
	 *
	 * @param {boolean} isCCW - By default solid shapes are  defined clockwise (CW) and holes are defined counterclockwise (CCW).
	 * If this flag is set to `true`, then those are flipped.
	 * @return {Array<Shape>} An array of shapes.
	 */
	toShapes( isCCW ) {

		function toShapesNoHoles( inSubpaths ) {

			const shapes = [];

			for ( let i = 0, l = inSubpaths.length; i < l; i ++ ) {

				const tmpPath = inSubpaths[ i ];

				const tmpShape = new Shape();
				tmpShape.curves = tmpPath.curves;

				shapes.push( tmpShape );

			}

			return shapes;

		}

		function isPointInsidePolygon( inPt, inPolygon ) {

			const polyLen = inPolygon.length;

			// inPt on polygon contour => immediate success    or
			// toggling of inside/outside at every single! intersection point of an edge
			//  with the horizontal line through inPt, left of inPt
			//  not counting lowerY endpoints of edges and whole edges on that line
			let inside = false;
			for ( let p = polyLen - 1, q = 0; q < polyLen; p = q ++ ) {

				let edgeLowPt = inPolygon[ p ];
				let edgeHighPt = inPolygon[ q ];

				let edgeDx = edgeHighPt.x - edgeLowPt.x;
				let edgeDy = edgeHighPt.y - edgeLowPt.y;

				if ( Math.abs( edgeDy ) > Number.EPSILON ) {

					// not parallel
					if ( edgeDy < 0 ) {

						edgeLowPt = inPolygon[ q ]; edgeDx = - edgeDx;
						edgeHighPt = inPolygon[ p ]; edgeDy = - edgeDy;

					}

					if ( ( inPt.y < edgeLowPt.y ) || ( inPt.y > edgeHighPt.y ) ) 		continue;

					if ( inPt.y === edgeLowPt.y ) {

						if ( inPt.x === edgeLowPt.x )		return	true;		// inPt is on contour ?
						// continue;				// no intersection or edgeLowPt => doesn't count !!!

					} else {

						const perpEdge = edgeDy * ( inPt.x - edgeLowPt.x ) - edgeDx * ( inPt.y - edgeLowPt.y );
						if ( perpEdge === 0 )				return	true;		// inPt is on contour ?
						if ( perpEdge < 0 ) 				continue;
						inside = ! inside;		// true intersection left of inPt

					}

				} else {

					// parallel or collinear
					if ( inPt.y !== edgeLowPt.y ) 		continue;			// parallel
					// edge lies on the same horizontal line as inPt
					if ( ( ( edgeHighPt.x <= inPt.x ) && ( inPt.x <= edgeLowPt.x ) ) ||
						 ( ( edgeLowPt.x <= inPt.x ) && ( inPt.x <= edgeHighPt.x ) ) )		return	true;	// inPt: Point on contour !
					// continue;

				}

			}

			return	inside;

		}

		const isClockWise = ShapeUtils.isClockWise;

		const subPaths = this.subPaths;
		if ( subPaths.length === 0 ) return [];

		let solid, tmpPath, tmpShape;
		const shapes = [];

		if ( subPaths.length === 1 ) {

			tmpPath = subPaths[ 0 ];
			tmpShape = new Shape();
			tmpShape.curves = tmpPath.curves;
			shapes.push( tmpShape );
			return shapes;

		}

		let holesFirst = ! isClockWise( subPaths[ 0 ].getPoints() );
		holesFirst = isCCW ? ! holesFirst : holesFirst;

		// console.log("Holes first", holesFirst);

		const betterShapeHoles = [];
		const newShapes = [];
		let newShapeHoles = [];
		let mainIdx = 0;
		let tmpPoints;

		newShapes[ mainIdx ] = undefined;
		newShapeHoles[ mainIdx ] = [];

		for ( let i = 0, l = subPaths.length; i < l; i ++ ) {

			tmpPath = subPaths[ i ];
			tmpPoints = tmpPath.getPoints();
			solid = isClockWise( tmpPoints );
			solid = isCCW ? ! solid : solid;

			if ( solid ) {

				if ( ( ! holesFirst ) && ( newShapes[ mainIdx ] ) )	mainIdx ++;

				newShapes[ mainIdx ] = { s: new Shape(), p: tmpPoints };
				newShapes[ mainIdx ].s.curves = tmpPath.curves;

				if ( holesFirst )	mainIdx ++;
				newShapeHoles[ mainIdx ] = [];

				//console.log('cw', i);

			} else {

				newShapeHoles[ mainIdx ].push( { h: tmpPath, p: tmpPoints[ 0 ] } );

				//console.log('ccw', i);

			}

		}

		// only Holes? -> probably all Shapes with wrong orientation
		if ( ! newShapes[ 0 ] )	return	toShapesNoHoles( subPaths );


		if ( newShapes.length > 1 ) {

			let ambiguous = false;
			let toChange = 0;

			for ( let sIdx = 0, sLen = newShapes.length; sIdx < sLen; sIdx ++ ) {

				betterShapeHoles[ sIdx ] = [];

			}

			for ( let sIdx = 0, sLen = newShapes.length; sIdx < sLen; sIdx ++ ) {

				const sho = newShapeHoles[ sIdx ];

				for ( let hIdx = 0; hIdx < sho.length; hIdx ++ ) {

					const ho = sho[ hIdx ];
					let hole_unassigned = true;

					for ( let s2Idx = 0; s2Idx < newShapes.length; s2Idx ++ ) {

						if ( isPointInsidePolygon( ho.p, newShapes[ s2Idx ].p ) ) {

							if ( sIdx !== s2Idx )	toChange ++;

							if ( hole_unassigned ) {

								hole_unassigned = false;
								betterShapeHoles[ s2Idx ].push( ho );

							} else {

								ambiguous = true;

							}

						}

					}

					if ( hole_unassigned ) {

						betterShapeHoles[ sIdx ].push( ho );

					}

				}

			}

			if ( toChange > 0 && ambiguous === false ) {

				newShapeHoles = betterShapeHoles;

			}

		}

		let tmpHoles;

		for ( let i = 0, il = newShapes.length; i < il; i ++ ) {

			tmpShape = newShapes[ i ].s;
			shapes.push( tmpShape );
			tmpHoles = newShapeHoles[ i ];

			for ( let j = 0, jl = tmpHoles.length; j < jl; j ++ ) {

				tmpShape.holes.push( tmpHoles[ j ].h );

			}

		}

		//console.log("shape", shapes);

		return shapes;

	}

}
```
</details>

#### Methods

##### `moveTo(x: number, y: number): ShapePath`

<details><summary>Code</summary>

```ts
moveTo( x, y ) {

		this.currentPath = new Path();
		this.subPaths.push( this.currentPath );
		this.currentPath.moveTo( x, y );

		return this;

	}
```
</details>

##### `lineTo(x: number, y: number): ShapePath`

<details><summary>Code</summary>

```ts
lineTo( x, y ) {

		this.currentPath.lineTo( x, y );

		return this;

	}
```
</details>

##### `quadraticCurveTo(aCPx: number, aCPy: number, aX: number, aY: number): ShapePath`

<details><summary>Code</summary>

```ts
quadraticCurveTo( aCPx, aCPy, aX, aY ) {

		this.currentPath.quadraticCurveTo( aCPx, aCPy, aX, aY );

		return this;

	}
```
</details>

##### `bezierCurveTo(aCP1x: number, aCP1y: number, aCP2x: number, aCP2y: number, aX: number, aY: number): ShapePath`

<details><summary>Code</summary>

```ts
bezierCurveTo( aCP1x, aCP1y, aCP2x, aCP2y, aX, aY ) {

		this.currentPath.bezierCurveTo( aCP1x, aCP1y, aCP2x, aCP2y, aX, aY );

		return this;

	}
```
</details>

##### `splineThru(pts: Vector2[]): ShapePath`

<details><summary>Code</summary>

```ts
splineThru( pts ) {

		this.currentPath.splineThru( pts );

		return this;

	}
```
</details>

##### `toShapes(isCCW: boolean): Shape[]`

<details><summary>Code</summary>

```ts
toShapes( isCCW ) {

		function toShapesNoHoles( inSubpaths ) {

			const shapes = [];

			for ( let i = 0, l = inSubpaths.length; i < l; i ++ ) {

				const tmpPath = inSubpaths[ i ];

				const tmpShape = new Shape();
				tmpShape.curves = tmpPath.curves;

				shapes.push( tmpShape );

			}

			return shapes;

		}

		function isPointInsidePolygon( inPt, inPolygon ) {

			const polyLen = inPolygon.length;

			// inPt on polygon contour => immediate success    or
			// toggling of inside/outside at every single! intersection point of an edge
			//  with the horizontal line through inPt, left of inPt
			//  not counting lowerY endpoints of edges and whole edges on that line
			let inside = false;
			for ( let p = polyLen - 1, q = 0; q < polyLen; p = q ++ ) {

				let edgeLowPt = inPolygon[ p ];
				let edgeHighPt = inPolygon[ q ];

				let edgeDx = edgeHighPt.x - edgeLowPt.x;
				let edgeDy = edgeHighPt.y - edgeLowPt.y;

				if ( Math.abs( edgeDy ) > Number.EPSILON ) {

					// not parallel
					if ( edgeDy < 0 ) {

						edgeLowPt = inPolygon[ q ]; edgeDx = - edgeDx;
						edgeHighPt = inPolygon[ p ]; edgeDy = - edgeDy;

					}

					if ( ( inPt.y < edgeLowPt.y ) || ( inPt.y > edgeHighPt.y ) ) 		continue;

					if ( inPt.y === edgeLowPt.y ) {

						if ( inPt.x === edgeLowPt.x )		return	true;		// inPt is on contour ?
						// continue;				// no intersection or edgeLowPt => doesn't count !!!

					} else {

						const perpEdge = edgeDy * ( inPt.x - edgeLowPt.x ) - edgeDx * ( inPt.y - edgeLowPt.y );
						if ( perpEdge === 0 )				return	true;		// inPt is on contour ?
						if ( perpEdge < 0 ) 				continue;
						inside = ! inside;		// true intersection left of inPt

					}

				} else {

					// parallel or collinear
					if ( inPt.y !== edgeLowPt.y ) 		continue;			// parallel
					// edge lies on the same horizontal line as inPt
					if ( ( ( edgeHighPt.x <= inPt.x ) && ( inPt.x <= edgeLowPt.x ) ) ||
						 ( ( edgeLowPt.x <= inPt.x ) && ( inPt.x <= edgeHighPt.x ) ) )		return	true;	// inPt: Point on contour !
					// continue;

				}

			}

			return	inside;

		}

		const isClockWise = ShapeUtils.isClockWise;

		const subPaths = this.subPaths;
		if ( subPaths.length === 0 ) return [];

		let solid, tmpPath, tmpShape;
		const shapes = [];

		if ( subPaths.length === 1 ) {

			tmpPath = subPaths[ 0 ];
			tmpShape = new Shape();
			tmpShape.curves = tmpPath.curves;
			shapes.push( tmpShape );
			return shapes;

		}

		let holesFirst = ! isClockWise( subPaths[ 0 ].getPoints() );
		holesFirst = isCCW ? ! holesFirst : holesFirst;

		// console.log("Holes first", holesFirst);

		const betterShapeHoles = [];
		const newShapes = [];
		let newShapeHoles = [];
		let mainIdx = 0;
		let tmpPoints;

		newShapes[ mainIdx ] = undefined;
		newShapeHoles[ mainIdx ] = [];

		for ( let i = 0, l = subPaths.length; i < l; i ++ ) {

			tmpPath = subPaths[ i ];
			tmpPoints = tmpPath.getPoints();
			solid = isClockWise( tmpPoints );
			solid = isCCW ? ! solid : solid;

			if ( solid ) {

				if ( ( ! holesFirst ) && ( newShapes[ mainIdx ] ) )	mainIdx ++;

				newShapes[ mainIdx ] = { s: new Shape(), p: tmpPoints };
				newShapes[ mainIdx ].s.curves = tmpPath.curves;

				if ( holesFirst )	mainIdx ++;
				newShapeHoles[ mainIdx ] = [];

				//console.log('cw', i);

			} else {

				newShapeHoles[ mainIdx ].push( { h: tmpPath, p: tmpPoints[ 0 ] } );

				//console.log('ccw', i);

			}

		}

		// only Holes? -> probably all Shapes with wrong orientation
		if ( ! newShapes[ 0 ] )	return	toShapesNoHoles( subPaths );


		if ( newShapes.length > 1 ) {

			let ambiguous = false;
			let toChange = 0;

			for ( let sIdx = 0, sLen = newShapes.length; sIdx < sLen; sIdx ++ ) {

				betterShapeHoles[ sIdx ] = [];

			}

			for ( let sIdx = 0, sLen = newShapes.length; sIdx < sLen; sIdx ++ ) {

				const sho = newShapeHoles[ sIdx ];

				for ( let hIdx = 0; hIdx < sho.length; hIdx ++ ) {

					const ho = sho[ hIdx ];
					let hole_unassigned = true;

					for ( let s2Idx = 0; s2Idx < newShapes.length; s2Idx ++ ) {

						if ( isPointInsidePolygon( ho.p, newShapes[ s2Idx ].p ) ) {

							if ( sIdx !== s2Idx )	toChange ++;

							if ( hole_unassigned ) {

								hole_unassigned = false;
								betterShapeHoles[ s2Idx ].push( ho );

							} else {

								ambiguous = true;

							}

						}

					}

					if ( hole_unassigned ) {

						betterShapeHoles[ sIdx ].push( ho );

					}

				}

			}

			if ( toChange > 0 && ambiguous === false ) {

				newShapeHoles = betterShapeHoles;

			}

		}

		let tmpHoles;

		for ( let i = 0, il = newShapes.length; i < il; i ++ ) {

			tmpShape = newShapes[ i ].s;
			shapes.push( tmpShape );
			tmpHoles = newShapeHoles[ i ];

			for ( let j = 0, jl = tmpHoles.length; j < jl; j ++ ) {

				tmpShape.holes.push( tmpHoles[ j ].h );

			}

		}

		//console.log("shape", shapes);

		return shapes;

	}
```
</details>


---