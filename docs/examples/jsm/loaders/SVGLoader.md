[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SVGLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 53 |
| 🧱 Classes | 1 |
| 📦 Imports | 13 |
| 📊 Variables & Constants | 218 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/SVGLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Box2` | `three` |
| `BufferGeometry` | `three` |
| `FileLoader` | `three` |
| `Float32BufferAttribute` | `three` |
| `Loader` | `three` |
| `Matrix3` | `three` |
| `Path` | `three` |
| `Shape` | `three` |
| `ShapePath` | `three` |
| `ShapeUtils` | `three` |
| `SRGBColorSpace` | `three` |
| `Vector2` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `COLOR_SPACE_SVG` | `any` | let/var | `SRGBColorSpace` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `loader` | `any` | let/var | `new FileLoader( scope.manager )` | ✗ |
| `scope` | `this` | let/var | `this` | ✗ |
| `isDefsNode` | `boolean` | let/var | `false` | ✗ |
| `path` | `any` | let/var | `null` | ✗ |
| `href` | `any` | let/var | `node.getAttributeNS( 'http://www.w3.org/1999/xlink', 'href' ) \|\| ''` | ✗ |
| `childNodes` | `any` | let/var | `node.childNodes` | ✗ |
| `node` | `any` | let/var | `childNodes[ i ]` | ✗ |
| `path` | `any` | let/var | `new ShapePath()` | ✗ |
| `point` | `any` | let/var | `new Vector2()` | ✗ |
| `control` | `any` | let/var | `new Vector2()` | ✗ |
| `firstPoint` | `any` | let/var | `new Vector2()` | ✗ |
| `isFirstPoint` | `boolean` | let/var | `true` | ✗ |
| `doSetFirstPoint` | `boolean` | let/var | `false` | ✗ |
| `command` | `any` | let/var | `commands[ i ]` | ✗ |
| `numbers` | `any` | let/var | `*not shown*` | ✗ |
| `stylesheet` | `any` | let/var | `node.sheet.cssRules[ i ]` | ✗ |
| `dx2` | `number` | let/var | `( start.x - end.x ) / 2.0` | ✗ |
| `dy2` | `number` | let/var | `( start.y - end.y ) / 2.0` | ✗ |
| `x1p` | `number` | let/var | `Math.cos( x_axis_rotation ) * dx2 + Math.sin( x_axis_rotation ) * dy2` | ✗ |
| `y1p` | `number` | let/var | `- Math.sin( x_axis_rotation ) * dx2 + Math.cos( x_axis_rotation ) * dy2` | ✗ |
| `rxs` | `number` | let/var | `rx * rx` | ✗ |
| `rys` | `number` | let/var | `ry * ry` | ✗ |
| `x1ps` | `number` | let/var | `x1p * x1p` | ✗ |
| `y1ps` | `number` | let/var | `y1p * y1p` | ✗ |
| `cr` | `number` | let/var | `x1ps / rxs + y1ps / rys` | ✗ |
| `dq` | `number` | let/var | `( rxs * y1ps + rys * x1ps )` | ✗ |
| `pq` | `number` | let/var | `( rxs * rys - dq ) / dq` | ✗ |
| `cxp` | `number` | let/var | `q * rx * y1p / ry` | ✗ |
| `cyp` | `number` | let/var | `- q * ry * x1p / rx` | ✗ |
| `cx` | `number` | let/var | `Math.cos( x_axis_rotation ) * cxp - Math.sin( x_axis_rotation ) * cyp + ( sta...` | ✗ |
| `cy` | `number` | let/var | `Math.sin( x_axis_rotation ) * cxp + Math.cos( x_axis_rotation ) * cyp + ( sta...` | ✗ |
| `delta` | `number` | let/var | `svgAngle( ( x1p - cxp ) / rx, ( y1p - cyp ) / ry, ( - x1p - cxp ) / rx, ( - y...` | ✗ |
| `dot` | `number` | let/var | `ux * vx + uy * vy` | ✗ |
| `len` | `number` | let/var | `Math.sqrt( ux * ux + uy * uy ) * Math.sqrt( vx * vx + vy * vy )` | ✗ |
| `bci` | `number` | let/var | `1 - 0.551915024494` | ✗ |
| `path` | `any` | let/var | `new ShapePath()` | ✗ |
| `regex` | `RegExp` | let/var | `/([+-]?\d*\.?\d+(?:e[+-]?\d+)?)(?:,\|\s)([+-]?\d*\.?\d+(?:e[+-]?\d+)?)/g` | ✗ |
| `path` | `any` | let/var | `new ShapePath()` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `regex` | `RegExp` | let/var | `/([+-]?\d*\.?\d+(?:e[+-]?\d+)?)(?:,\|\s)([+-]?\d*\.?\d+(?:e[+-]?\d+)?)/g` | ✗ |
| `path` | `any` | let/var | `new ShapePath()` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `subpath` | `any` | let/var | `new Path()` | ✗ |
| `path` | `any` | let/var | `new ShapePath()` | ✗ |
| `subpath` | `any` | let/var | `new Path()` | ✗ |
| `path` | `any` | let/var | `new ShapePath()` | ✗ |
| `path` | `any` | let/var | `new ShapePath()` | ✗ |
| `stylesheetStyles` | `{}` | let/var | `{}` | ✗ |
| `RE` | `{ SEPARATOR: RegExp; WHITESPACE: RegE...` | let/var | `{ SEPARATOR: /[ \t\r\n\,.\-+]/, WHITESPACE: /[ \t\r\n]/, DIGIT: /[\d]/, SIGN:...` | ✗ |
| `SEP` | `0` | let/var | `0` | ✗ |
| `INT` | `1` | let/var | `1` | ✗ |
| `FLOAT` | `2` | let/var | `2` | ✗ |
| `EXP` | `3` | let/var | `3` | ✗ |
| `state` | `number` | let/var | `SEP` | ✗ |
| `seenComma` | `boolean` | let/var | `true` | ✗ |
| `number` | `string` | let/var | `''` | ✗ |
| `exponent` | `string` | let/var | `''` | ✗ |
| `result` | `any[]` | let/var | `[]` | ✗ |
| `error` | `SyntaxError` | let/var | `new SyntaxError( 'Unexpected character "' + current + '" at index ' + i + '.' )` | ✗ |
| `current` | `any` | let/var | `*not shown*` | ✗ |
| `length` | `number` | let/var | `input.length` | ✗ |
| `units` | `string[]` | let/var | `[ 'mm', 'cm', 'in', 'pt', 'pc', 'px' ]` | ✗ |
| `unitConversion` | `{ mm: { mm: number; cm: number; in: n...` | let/var | `{ 'mm': { 'mm': 1, 'cm': 0.1, 'in': 1 / 25.4, 'pt': 72 / 25.4, 'pc': 6 / 25.4...` | ✗ |
| `theUnit` | `string` | let/var | `'px'` | ✗ |
| `u` | `string` | let/var | `units[ i ]` | ✗ |
| `scale` | `any` | let/var | `undefined` | ✗ |
| `transform` | `any` | let/var | `new Matrix3()` | ✗ |
| `currentTransform` | `any` | let/var | `tempTransform0` | ✗ |
| `closeParPos` | `any` | let/var | `transformText.length` | ✗ |
| `tx` | `any` | let/var | `array[ 0 ]` | ✗ |
| `ty` | `number` | let/var | `0` | ✗ |
| `angle` | `number` | let/var | `0` | ✗ |
| `cx` | `number` | let/var | `0` | ✗ |
| `cy` | `number` | let/var | `0` | ✗ |
| `scaleX` | `any` | let/var | `array[ 0 ]` | ✗ |
| `scaleY` | `any` | let/var | `scaleX` | ✗ |
| `a` | `any` | let/var | `curve.xRadius` | ✗ |
| `b` | `any` | let/var | `curve.yRadius` | ✗ |
| `v1` | `any` | let/var | `new Vector3( a * cosTheta, a * sinTheta, 0 )` | ✗ |
| `v2` | `any` | let/var | `new Vector3( - b * sinTheta, b * cosTheta, 0 )` | ✗ |
| `mQe` | `any` | let/var | `mQ.elements` | ✗ |
| `isFullEllipse` | `boolean` | let/var | `( curve.aEndAngle - curve.aStartAngle ) % ( 2 * Math.PI ) < Number.EPSILON` | ✗ |
| `theta` | `number` | let/var | `sx > Number.EPSILON ? Math.atan2( m.elements[ 1 ], m.elements[ 0 ] ) : Math.a...` | ✗ |
| `subPaths` | `any` | let/var | `path.subPaths` | ✗ |
| `subPath` | `any` | let/var | `subPaths[ i ]` | ✗ |
| `curves` | `any` | let/var | `subPath.curves` | ✗ |
| `curve` | `any` | let/var | `curves[ j ]` | ✗ |
| `te` | `any` | let/var | `m.elements` | ✗ |
| `te` | `any` | let/var | `m.elements` | ✗ |
| `basisDot` | `number` | let/var | `te[ 0 ] * te[ 3 ] + te[ 1 ] * te[ 4 ]` | ✗ |
| `te` | `any` | let/var | `m.elements` | ✗ |
| `te` | `any` | let/var | `m.elements` | ✗ |
| `rt1` | `any` | let/var | `*not shown*` | ✗ |
| `rt2` | `any` | let/var | `*not shown*` | ✗ |
| `cs` | `any` | let/var | `*not shown*` | ✗ |
| `sn` | `any` | let/var | `*not shown*` | ✗ |
| `t` | `any` | let/var | `*not shown*` | ✗ |
| `sm` | `any` | let/var | `A + C` | ✗ |
| `df` | `number` | let/var | `A - C` | ✗ |
| `paths` | `any[]` | let/var | `[]` | ✗ |
| `stylesheets` | `{}` | let/var | `{}` | ✗ |
| `transformStack` | `any[]` | let/var | `[]` | ✗ |
| `tempTransform0` | `any` | let/var | `new Matrix3()` | ✗ |
| `tempTransform1` | `any` | let/var | `new Matrix3()` | ✗ |
| `tempTransform2` | `any` | let/var | `new Matrix3()` | ✗ |
| `tempTransform3` | `any` | let/var | `new Matrix3()` | ✗ |
| `tempV2` | `any` | let/var | `new Vector2()` | ✗ |
| `tempV3` | `any` | let/var | `new Vector3()` | ✗ |
| `currentTransform` | `any` | let/var | `new Matrix3()` | ✗ |
| `data` | `{ paths: any[]; xml: HTMLElement; }` | let/var | `{ paths: paths, xml: xml.documentElement }` | ✗ |
| `BIGNUMBER` | `999999999` | let/var | `999999999` | ✗ |
| `IntersectionLocationType` | `{ ORIGIN: number; DESTINATION: number...` | let/var | `{ ORIGIN: 0, DESTINATION: 1, BETWEEN: 2, LEFT: 3, RIGHT: 4, BEHIND: 5, BEYOND...` | ✗ |
| `classifyResult` | `{ loc: number; t: number; }` | let/var | `{ loc: IntersectionLocationType.ORIGIN, t: 0 }` | ✗ |
| `x1` | `any` | let/var | `a0.x` | ✗ |
| `x2` | `any` | let/var | `a1.x` | ✗ |
| `x3` | `any` | let/var | `b0.x` | ✗ |
| `x4` | `any` | let/var | `b1.x` | ✗ |
| `y1` | `any` | let/var | `a0.y` | ✗ |
| `y2` | `any` | let/var | `a1.y` | ✗ |
| `y3` | `any` | let/var | `b0.y` | ✗ |
| `y4` | `any` | let/var | `b1.y` | ✗ |
| `nom1` | `number` | let/var | `( x4 - x3 ) * ( y1 - y3 ) - ( y4 - y3 ) * ( x1 - x3 )` | ✗ |
| `nom2` | `number` | let/var | `( x2 - x1 ) * ( y1 - y3 ) - ( y2 - y1 ) * ( x1 - x3 )` | ✗ |
| `denom` | `number` | let/var | `( y4 - y3 ) * ( x2 - x1 ) - ( x4 - x3 ) * ( y2 - y1 )` | ✗ |
| `t1` | `number` | let/var | `nom1 / denom` | ✗ |
| `t2` | `number` | let/var | `nom2 / denom` | ✗ |
| `point` | `any` | let/var | `( i === 0 ? b0 : b1 )` | ✗ |
| `x` | `number` | let/var | `+ ( ( x1 + classifyResult.t * ( x2 - x1 ) ).toPrecision( 10 ) )` | ✗ |
| `y` | `number` | let/var | `+ ( ( y1 + classifyResult.t * ( y2 - y1 ) ).toPrecision( 10 ) )` | ✗ |
| `point` | `any` | let/var | `( i === 0 ? b0 : b1 )` | ✗ |
| `x` | `number` | let/var | `+ ( ( x1 + t1 * ( x2 - x1 ) ).toPrecision( 10 ) )` | ✗ |
| `y` | `number` | let/var | `+ ( ( y1 + t1 * ( y2 - y1 ) ).toPrecision( 10 ) )` | ✗ |
| `ax` | `number` | let/var | `edgeEnd.x - edgeStart.x` | ✗ |
| `ay` | `number` | let/var | `edgeEnd.y - edgeStart.y` | ✗ |
| `bx` | `number` | let/var | `p.x - edgeStart.x` | ✗ |
| `by` | `number` | let/var | `p.y - edgeStart.y` | ✗ |
| `sa` | `number` | let/var | `ax * by - bx * ay` | ✗ |
| `t` | `any` | let/var | `*not shown*` | ✗ |
| `intersectionsRaw` | `any[]` | let/var | `[]` | ✗ |
| `intersections` | `any[]` | let/var | `[]` | ✗ |
| `path1EdgeStart` | `any` | let/var | `path1[ index - 1 ]` | ✗ |
| `path1EdgeEnd` | `any` | let/var | `path1[ index ]` | ✗ |
| `path2EdgeStart` | `any` | let/var | `path2[ index2 - 1 ]` | ✗ |
| `path2EdgeEnd` | `any` | let/var | `path2[ index2 ]` | ✗ |
| `center` | `any` | let/var | `new Vector2()` | ✗ |
| `allIntersections` | `any[]` | let/var | `[]` | ✗ |
| `centerBoundingBox` | `any` | let/var | `new Vector2()` | ✗ |
| `scanline` | `any[]` | let/var | `[ new Vector2( scanlineMinX, centerBoundingBox.y ), new Vector2( scanlineMaxX...` | ✗ |
| `baseIntersections` | `any[]` | let/var | `[]` | ✗ |
| `otherIntersections` | `any[]` | let/var | `[]` | ✗ |
| `firstXOfPath` | `any` | let/var | `baseIntersections[ 0 ].point.x` | ✗ |
| `stack` | `any[]` | let/var | `[]` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `isHole` | `boolean` | let/var | `stack.length % 2 === 0 ? true : false` | ✗ |
| `isHoleFor` | `any` | let/var | `stack[ stack.length - 2 ]` | ✗ |
| `isHole` | `boolean` | let/var | `true` | ✗ |
| `isHoleFor` | `any` | let/var | `null` | ✗ |
| `lastCWValue` | `any` | let/var | `null` | ✗ |
| `identifier` | `any` | let/var | `stack[ i ]` | ✗ |
| `scanlineMinX` | `number` | let/var | `BIGNUMBER` | ✗ |
| `scanlineMaxX` | `number` | let/var | `- BIGNUMBER` | ✗ |
| `maxY` | `number` | let/var | `- BIGNUMBER` | ✗ |
| `minY` | `number` | let/var | `BIGNUMBER` | ✗ |
| `maxX` | `number` | let/var | `- BIGNUMBER` | ✗ |
| `minX` | `number` | let/var | `BIGNUMBER` | ✗ |
| `p` | `any` | let/var | `points[ i ]` | ✗ |
| `shapesToReturn` | `any[]` | let/var | `[]` | ✗ |
| `amIAHole` | `any` | let/var | `isAHole[ p.identifier ]` | ✗ |
| `shape` | `any` | let/var | `new Shape()` | ✗ |
| `hole` | `any` | let/var | `simplePaths[ h.identifier ]` | ✗ |
| `path` | `any` | let/var | `new Path()` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `uvs` | `any[]` | let/var | `[]` | ✗ |
| `geometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `tempV2_1` | `any` | let/var | `new Vector2()` | ✗ |
| `tempV2_2` | `any` | let/var | `new Vector2()` | ✗ |
| `tempV2_3` | `any` | let/var | `new Vector2()` | ✗ |
| `tempV2_4` | `any` | let/var | `new Vector2()` | ✗ |
| `tempV2_5` | `any` | let/var | `new Vector2()` | ✗ |
| `tempV2_6` | `any` | let/var | `new Vector2()` | ✗ |
| `tempV2_7` | `any` | let/var | `new Vector2()` | ✗ |
| `lastPointL` | `any` | let/var | `new Vector2()` | ✗ |
| `lastPointR` | `any` | let/var | `new Vector2()` | ✗ |
| `point0L` | `any` | let/var | `new Vector2()` | ✗ |
| `point0R` | `any` | let/var | `new Vector2()` | ✗ |
| `currentPointL` | `any` | let/var | `new Vector2()` | ✗ |
| `currentPointR` | `any` | let/var | `new Vector2()` | ✗ |
| `nextPointL` | `any` | let/var | `new Vector2()` | ✗ |
| `nextPointR` | `any` | let/var | `new Vector2()` | ✗ |
| `innerPoint` | `any` | let/var | `new Vector2()` | ✗ |
| `outerPoint` | `any` | let/var | `new Vector2()` | ✗ |
| `numPoints` | `number` | let/var | `points.length` | ✗ |
| `currentPoint` | `any` | let/var | `*not shown*` | ✗ |
| `previousPoint` | `Vector2` | let/var | `points[ 0 ]` | ✗ |
| `nextPoint` | `any` | let/var | `*not shown*` | ✗ |
| `strokeWidth2` | `number` | let/var | `style.strokeWidth / 2` | ✗ |
| `deltaU` | `number` | let/var | `1 / ( numPoints - 1 )` | ✗ |
| `u0` | `number` | let/var | `0` | ✗ |
| `u1` | `any` | let/var | `*not shown*` | ✗ |
| `innerSideModified` | `any` | let/var | `*not shown*` | ✗ |
| `joinIsOnLeftSide` | `any` | let/var | `*not shown*` | ✗ |
| `isMiter` | `any` | let/var | `*not shown*` | ✗ |
| `initialJoinIsOnLeftSide` | `boolean` | let/var | `false` | ✗ |
| `numVertices` | `number` | let/var | `0` | ✗ |
| `currentCoordinate` | `number` | let/var | `vertexOffset * 3` | ✗ |
| `currentCoordinateUV` | `number` | let/var | `vertexOffset * 2` | ✗ |
| `normal1` | `any` | let/var | `tempV2_1` | ✗ |
| `miterSide` | `number` | let/var | `strokeWidth2 / dot` | ✗ |
| `miterFraction` | `number` | let/var | `( strokeWidth2 * style.strokeMiterLimit ) / miterLength2` | ✗ |
| `lastOuter` | `any` | let/var | `outerPoint` | ✗ |
| `lastInner` | `any` | let/var | `innerPoint` | ✗ |
| `angle` | `number` | let/var | `Math.PI` | ✗ |
| `vl` | `number` | let/var | `vertices.length` | ✗ |
| `dupPoints` | `boolean` | let/var | `false` | ✗ |
| `newPoints` | `any[]` | let/var | `[]` | ✗ |


---

## Functions

### `SVGLoader.load(url: string, onLoad: (arg0: { paths: ShapePath[]; xml: string; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded SVG asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({paths:Array<ShapePath>,xml:string})} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: { paths: ShapePath[]; xml: string; }) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `loader.setPath`
- `loader.setRequestHeader`
- `loader.setWithCredentials`
- `loader.load`
- `onLoad`
- `scope.parse`
- `onError`
- `console.error`
- `scope.manager.itemError`

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

### `SVGLoader.parse(text: string): { paths: ShapePath[]; xml: string; }`

**JSDoc:**
```typescript
/**
	 * Parses the given SVG data and returns the resulting data.
	 *
	 * @param {string} text - The raw SVG data as a string.
	 * @return {{paths:Array<ShapePath>,xml:string}} An object holding an array of shape paths and the
	 * SVG XML document.
	 */
```

**Parameters:**

- **`text`** `string`

**Returns:** `{ paths: ShapePath[]; xml: string; }`

**Calls:**

- `getNodeTransform`
- `parseStyle`
- `parseCSSStylesheet`
- `node.hasAttribute`
- `parsePathNode`
- `parseRectNode`
- `parsePolygonNode`
- `parsePolylineNode`
- `parseCircleNode`
- `parseEllipseNode`
- `parseLineNode`
- `node.getAttributeNS`
- `href.substring`
- `node.viewportElement.getElementById`
- `parseNode`
- `console.warn`
- `path.color.setStyle`
- `transformPath`
- `paths.push`
- `transformStack.pop`
- `currentTransform.copy`
- `currentTransform.identity`
- `node.getAttribute`
- `d.match`
- `command.charAt`
- `command.slice( 1 ).trim`
- `parseFloats`
- `path.moveTo`
- `path.lineTo`
- `firstPoint.copy`
- `path.bezierCurveTo`
- `getReflection`
- `path.quadraticCurveTo`
- `point.clone`
- `parseArcCommand`
- `point.copy`
- `path.currentPath.currentPoint.copy`
- `stylesheet.selectorText
					.split( /,/gm )
					.filter( Boolean )
					.map`
- `i.trim`
- `Object.fromEntries`
- `Object.entries( stylesheet.style ).filter`
- `Object.assign`
- `Math.abs`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `Math.max`
- `svgAngle`
- `path.currentPath.absellipse`
- `Math.acos`
- `Math.min`
- `parseFloatWithUnits`
- `node.getAttribute( 'points' ).replace`
- `subpath.absarc`
- `path.subPaths.push`
- `subpath.absellipse`
- `node.getAttribute( 'class' )
					.split( /\s/ )
					.filter( Boolean )
					.map`
- `v.startsWith`
- `adjustFunction`
- `addStyle`
- `result.push`
- `Number`
- `Math.pow`
- `Array.isArray`
- `flags.includes`
- `RE.FLAGS.test`
- `newNumber`
- `RE.WHITESPACE.test`
- `RE.DIGIT.test`
- `RE.SIGN.test`
- `RE.POINT.test`
- `RE.COMMA.test`
- `throwSyntaxError`
- `RE.EXP.test`
- `string.endsWith`
- `string.substring`
- `parseFloat`
- `parseNodeTransform`
- `transform.premultiply`
- `transformStack.push`
- `transform.translate`
- `node.getAttribute( 'transform' ).split`
- `transformsTexts[ tIndex ].trim`
- `transformText.indexOf`
- `transformText.slice`
- `currentTransform.translate`
- `tempTransform1.makeTranslation`
- `tempTransform2.makeRotation`
- `tempTransform3.multiplyMatrices`
- `currentTransform.multiplyMatrices`
- `currentTransform.scale`
- `currentTransform.set`
- `Math.tan`
- `tempV3.set( v2.x, v2.y, 1 ).applyMatrix3`
- `v2.set`
- `v1.applyMatrix3`
- `v2.applyMatrix3`
- `tempTransform0.set`
- `tempTransform1.copy( mF ).invert`
- `tempTransform2.copy( mFInv ).transpose`
- `mFInvT.multiply`
- `eigenDecomposition`
- `Math.atan2`
- `tempTransform1.set`
- `tempTransform2.set`
- `mDsqrt.multiply( mRT ).multiply`
- `new Vector3( Math.cos( phi ), Math.sin( phi ), 0 ).applyMatrix3`
- `transformAngle`
- `isTransformFlipped`
- `getTransformScaleX`
- `getTransformScaleY`
- `transfVec2`
- `tempV2.set`
- `isTransformSkewed`
- `transfEllipseGeneric`
- `transfEllipseNoSkew`
- `new DOMParser().parseFromString`

**Internal Comments:**
```
// Ignore everything in defs except CSS style definitions
// and nested defs, because it is OK by the standard to have
// <style/> there.
// console.log( d ); (x2)
// skip command if start point == end point
// skip command if no displacement
// Reset point to beginning of Path (x4)
// console.log( type, parseFloats( data ), parseFloats( data ).length  ) (x3)
// Remove empty rules (x2)
/**
		 * https://www.w3.org/TR/SVG/implnote.html#ArcImplementationNotes
		 * https://mortoray.com/2017/02/16/rendering-an-svg-elliptical-arc-as-bezier-curves/ Appendix: Endpoint to center arc conversion
		 * From
		 * rx ry x-axis-rotation large-arc-flag sweep-flag x y
		 * To
		 * aX, aY, xRadius, yRadius, aStartAngle, aEndAngle, aClockwise, aRotation
		 */
// draw a line if either of the radii == 0 (x4)
// Ensure radii are positive (x3)
// Compute (x1', y1') (x2)
// Compute (cx', cy') (x2)
// Ensure radii are large enough (x2)
// scale up rx,ry equally so cr == 1 (x2)
// Step 3: Compute (cx, cy) from (cx', cy') (x2)
// Step 4: Compute θ1 and Δθ (x2)
/*
		* According to https://www.w3.org/TR/SVG/shapes.html#RectElementRXAttribute
		* rounded corner should be rendered to elliptical arc, but bezier curve does the job well enough
		*/
// Ellipse arc to Bezier approximation Coefficient (Inversed). See: (x2)
// https://spencermortensen.com/articles/bezier-circle/ (x2)
// top left (x4)
// top right (x4)
// bottom right (x4)
// bottom left (x4)
// back to top left (x4)
// (x8)
// http://www.w3.org/TR/SVG11/implnote.html#PathElementImplementationNotes
// from https://github.com/ppvg/svg-numbers (MIT License)
// Character groups (x2)
// States (x2)
// check for flags
// parse until next number
// eat whitespace
// start new number
// throw on double commas (e.g. "1, , 2")
// parse integer part
// throw on double signs ("-+1"), but not on sign as separator ("-1-2")
// parse decimal part
// throw on double decimal points (e.g. "1..2")
// parse exponent part
// end of number
// add the last number found (if any) (x3)
// Units (x2)
// Conversion: [ fromUnit ][ toUnit ] (-1 means dpi dependent) (x2)
// Conversion scale from  pixels to inches, then to default units (x3)
// Conversion scale to pixels (x3)
// Transforms
// Angle (x3)
// Center x, y (x3)
// Rotate around center (cx, cy) (x4)
// For math description see: (x2)
// https://math.stackexchange.com/questions/4544164 (x2)
// Do not touch angles of a full ellipse because after transformation they
// would converge to a single value effectively removing the whole curve
// Faster shortcut if no skew is applied (x2)
// (e.g, a euclidean transform of a group containing the ellipse) (x2)
// Extract rotation angle from the matrix of form: (x2)
//  | cosθ sx   -sinθ sy | (x2)
//  | sinθ sx    cosθ sy | (x2)
// Remembering that tanθ = sinθ / cosθ; and that (x2)
// `sx`, `sy`, or both might be zero. (x2)
// Transform ellipse center point (x4)
// Transform ellipse shape parameters
// Shortcut for trivial rotations and transformations
// Calculates the eigensystem of a real symmetric 2x2 matrix
//    [ A  B ]
//    [ B  C ]
// in the form
//    [ A  B ]  =  [ cs  -sn ] [ rt1   0  ] [  cs  sn ]
//    [ B  C ]     [ sn   cs ] [  0   rt2 ] [ -sn  cs ]
// where rt1 >= rt2.
// Adapted from: https://www.mpi-hd.mpg.de/personalhomes/globes/3x3/index.html
// -> Algorithms for real symmetric matrices -> Analytical (2x2 symmetric)
// This case needs to be treated separately to avoid div by 0 (x3)
// Calculate eigenvectors
// console.log( paths );
```

<details><summary>Code</summary>

```typescript
parse( text ) {

		const scope = this;

		function parseNode( node, style ) {

			if ( node.nodeType !== 1 ) return;

			const transform = getNodeTransform( node );

			let isDefsNode = false;

			let path = null;

			switch ( node.nodeName ) {

				case 'svg':
					style = parseStyle( node, style );
					break;

				case 'style':
					parseCSSStylesheet( node );
					break;

				case 'g':
					style = parseStyle( node, style );
					break;

				case 'path':
					style = parseStyle( node, style );
					if ( node.hasAttribute( 'd' ) ) path = parsePathNode( node );
					break;

				case 'rect':
					style = parseStyle( node, style );
					path = parseRectNode( node );
					break;

				case 'polygon':
					style = parseStyle( node, style );
					path = parsePolygonNode( node );
					break;

				case 'polyline':
					style = parseStyle( node, style );
					path = parsePolylineNode( node );
					break;

				case 'circle':
					style = parseStyle( node, style );
					path = parseCircleNode( node );
					break;

				case 'ellipse':
					style = parseStyle( node, style );
					path = parseEllipseNode( node );
					break;

				case 'line':
					style = parseStyle( node, style );
					path = parseLineNode( node );
					break;

				case 'defs':
					isDefsNode = true;
					break;

				case 'use':
					style = parseStyle( node, style );

					const href = node.getAttributeNS( 'http://www.w3.org/1999/xlink', 'href' ) || '';
					const usedNodeId = href.substring( 1 );
					const usedNode = node.viewportElement.getElementById( usedNodeId );
					if ( usedNode ) {

						parseNode( usedNode, style );

					} else {

						console.warn( 'SVGLoader: \'use node\' references non-existent node id: ' + usedNodeId );

					}

					break;

				default:
					// console.log( node );

			}

			if ( path ) {

				if ( style.fill !== undefined && style.fill !== 'none' ) {

					path.color.setStyle( style.fill, COLOR_SPACE_SVG );

				}

				transformPath( path, currentTransform );

				paths.push( path );

				path.userData = { node: node, style: style };

			}

			const childNodes = node.childNodes;

			for ( let i = 0; i < childNodes.length; i ++ ) {

				const node = childNodes[ i ];

				if ( isDefsNode && node.nodeName !== 'style' && node.nodeName !== 'defs' ) {

					// Ignore everything in defs except CSS style definitions
					// and nested defs, because it is OK by the standard to have
					// <style/> there.
					continue;

				}

				parseNode( node, style );

			}


			if ( transform ) {

				transformStack.pop();

				if ( transformStack.length > 0 ) {

					currentTransform.copy( transformStack[ transformStack.length - 1 ] );

				} else {

					currentTransform.identity();

				}

			}

		}

		function parsePathNode( node ) {

			const path = new ShapePath();

			const point = new Vector2();
			const control = new Vector2();

			const firstPoint = new Vector2();
			let isFirstPoint = true;
			let doSetFirstPoint = false;

			const d = node.getAttribute( 'd' );

			if ( d === '' || d === 'none' ) return null;

			// console.log( d );

			const commands = d.match( /[a-df-z][^a-df-z]*/ig );

			for ( let i = 0, l = commands.length; i < l; i ++ ) {

				const command = commands[ i ];

				const type = command.charAt( 0 );
				const data = command.slice( 1 ).trim();

				if ( isFirstPoint === true ) {

					doSetFirstPoint = true;
					isFirstPoint = false;

				}

				let numbers;

				switch ( type ) {

					case 'M':
						numbers = parseFloats( data );
						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							point.x = numbers[ j + 0 ];
							point.y = numbers[ j + 1 ];
							control.x = point.x;
							control.y = point.y;

							if ( j === 0 ) {

								path.moveTo( point.x, point.y );

							} else {

								path.lineTo( point.x, point.y );

							}

							if ( j === 0 ) firstPoint.copy( point );

						}

						break;

					case 'H':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j ++ ) {

							point.x = numbers[ j ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'V':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j ++ ) {

							point.y = numbers[ j ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'L':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							point.x = numbers[ j + 0 ];
							point.y = numbers[ j + 1 ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'C':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 6 ) {

							path.bezierCurveTo(
								numbers[ j + 0 ],
								numbers[ j + 1 ],
								numbers[ j + 2 ],
								numbers[ j + 3 ],
								numbers[ j + 4 ],
								numbers[ j + 5 ]
							);
							control.x = numbers[ j + 2 ];
							control.y = numbers[ j + 3 ];
							point.x = numbers[ j + 4 ];
							point.y = numbers[ j + 5 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'S':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 4 ) {

							path.bezierCurveTo(
								getReflection( point.x, control.x ),
								getReflection( point.y, control.y ),
								numbers[ j + 0 ],
								numbers[ j + 1 ],
								numbers[ j + 2 ],
								numbers[ j + 3 ]
							);
							control.x = numbers[ j + 0 ];
							control.y = numbers[ j + 1 ];
							point.x = numbers[ j + 2 ];
							point.y = numbers[ j + 3 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'Q':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 4 ) {

							path.quadraticCurveTo(
								numbers[ j + 0 ],
								numbers[ j + 1 ],
								numbers[ j + 2 ],
								numbers[ j + 3 ]
							);
							control.x = numbers[ j + 0 ];
							control.y = numbers[ j + 1 ];
							point.x = numbers[ j + 2 ];
							point.y = numbers[ j + 3 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'T':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							const rx = getReflection( point.x, control.x );
							const ry = getReflection( point.y, control.y );
							path.quadraticCurveTo(
								rx,
								ry,
								numbers[ j + 0 ],
								numbers[ j + 1 ]
							);
							control.x = rx;
							control.y = ry;
							point.x = numbers[ j + 0 ];
							point.y = numbers[ j + 1 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'A':
						numbers = parseFloats( data, [ 3, 4 ], 7 );

						for ( let j = 0, jl = numbers.length; j < jl; j += 7 ) {

							// skip command if start point == end point
							if ( numbers[ j + 5 ] == point.x && numbers[ j + 6 ] == point.y ) continue;

							const start = point.clone();
							point.x = numbers[ j + 5 ];
							point.y = numbers[ j + 6 ];
							control.x = point.x;
							control.y = point.y;
							parseArcCommand(
								path, numbers[ j ], numbers[ j + 1 ], numbers[ j + 2 ], numbers[ j + 3 ], numbers[ j + 4 ], start, point
							);

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'm':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							point.x += numbers[ j + 0 ];
							point.y += numbers[ j + 1 ];
							control.x = point.x;
							control.y = point.y;

							if ( j === 0 ) {

								path.moveTo( point.x, point.y );

							} else {

								path.lineTo( point.x, point.y );

							}

							if ( j === 0 ) firstPoint.copy( point );

						}

						break;

					case 'h':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j ++ ) {

							point.x += numbers[ j ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'v':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j ++ ) {

							point.y += numbers[ j ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'l':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							point.x += numbers[ j + 0 ];
							point.y += numbers[ j + 1 ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'c':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 6 ) {

							path.bezierCurveTo(
								point.x + numbers[ j + 0 ],
								point.y + numbers[ j + 1 ],
								point.x + numbers[ j + 2 ],
								point.y + numbers[ j + 3 ],
								point.x + numbers[ j + 4 ],
								point.y + numbers[ j + 5 ]
							);
							control.x = point.x + numbers[ j + 2 ];
							control.y = point.y + numbers[ j + 3 ];
							point.x += numbers[ j + 4 ];
							point.y += numbers[ j + 5 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 's':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 4 ) {

							path.bezierCurveTo(
								getReflection( point.x, control.x ),
								getReflection( point.y, control.y ),
								point.x + numbers[ j + 0 ],
								point.y + numbers[ j + 1 ],
								point.x + numbers[ j + 2 ],
								point.y + numbers[ j + 3 ]
							);
							control.x = point.x + numbers[ j + 0 ];
							control.y = point.y + numbers[ j + 1 ];
							point.x += numbers[ j + 2 ];
							point.y += numbers[ j + 3 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'q':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 4 ) {

							path.quadraticCurveTo(
								point.x + numbers[ j + 0 ],
								point.y + numbers[ j + 1 ],
								point.x + numbers[ j + 2 ],
								point.y + numbers[ j + 3 ]
							);
							control.x = point.x + numbers[ j + 0 ];
							control.y = point.y + numbers[ j + 1 ];
							point.x += numbers[ j + 2 ];
							point.y += numbers[ j + 3 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 't':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							const rx = getReflection( point.x, control.x );
							const ry = getReflection( point.y, control.y );
							path.quadraticCurveTo(
								rx,
								ry,
								point.x + numbers[ j + 0 ],
								point.y + numbers[ j + 1 ]
							);
							control.x = rx;
							control.y = ry;
							point.x = point.x + numbers[ j + 0 ];
							point.y = point.y + numbers[ j + 1 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'a':
						numbers = parseFloats( data, [ 3, 4 ], 7 );

						for ( let j = 0, jl = numbers.length; j < jl; j += 7 ) {

							// skip command if no displacement
							if ( numbers[ j + 5 ] == 0 && numbers[ j + 6 ] == 0 ) continue;

							const start = point.clone();
							point.x += numbers[ j + 5 ];
							point.y += numbers[ j + 6 ];
							control.x = point.x;
							control.y = point.y;
							parseArcCommand(
								path, numbers[ j ], numbers[ j + 1 ], numbers[ j + 2 ], numbers[ j + 3 ], numbers[ j + 4 ], start, point
							);

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'Z':
					case 'z':
						path.currentPath.autoClose = true;

						if ( path.currentPath.curves.length > 0 ) {

							// Reset point to beginning of Path
							point.copy( firstPoint );
							path.currentPath.currentPoint.copy( point );
							isFirstPoint = true;

						}

						break;

					default:
						console.warn( command );

				}

				// console.log( type, parseFloats( data ), parseFloats( data ).length  )

				doSetFirstPoint = false;

			}

			return path;

		}

		function parseCSSStylesheet( node ) {

			if ( ! node.sheet || ! node.sheet.cssRules || ! node.sheet.cssRules.length ) return;

			for ( let i = 0; i < node.sheet.cssRules.length; i ++ ) {

				const stylesheet = node.sheet.cssRules[ i ];

				if ( stylesheet.type !== 1 ) continue;

				const selectorList = stylesheet.selectorText
					.split( /,/gm )
					.filter( Boolean )
					.map( i => i.trim() );

				for ( let j = 0; j < selectorList.length; j ++ ) {

					// Remove empty rules
					const definitions = Object.fromEntries(
						Object.entries( stylesheet.style ).filter( ( [ , v ] ) => v !== '' )
					);

					stylesheets[ selectorList[ j ] ] = Object.assign(
						stylesheets[ selectorList[ j ] ] || {},
						definitions
					);

				}

			}

		}

		/**
		 * https://www.w3.org/TR/SVG/implnote.html#ArcImplementationNotes
		 * https://mortoray.com/2017/02/16/rendering-an-svg-elliptical-arc-as-bezier-curves/ Appendix: Endpoint to center arc conversion
		 * From
		 * rx ry x-axis-rotation large-arc-flag sweep-flag x y
		 * To
		 * aX, aY, xRadius, yRadius, aStartAngle, aEndAngle, aClockwise, aRotation
		 */

		function parseArcCommand( path, rx, ry, x_axis_rotation, large_arc_flag, sweep_flag, start, end ) {

			if ( rx == 0 || ry == 0 ) {

				// draw a line if either of the radii == 0
				path.lineTo( end.x, end.y );
				return;

			}

			x_axis_rotation = x_axis_rotation * Math.PI / 180;

			// Ensure radii are positive
			rx = Math.abs( rx );
			ry = Math.abs( ry );

			// Compute (x1', y1')
			const dx2 = ( start.x - end.x ) / 2.0;
			const dy2 = ( start.y - end.y ) / 2.0;
			const x1p = Math.cos( x_axis_rotation ) * dx2 + Math.sin( x_axis_rotation ) * dy2;
			const y1p = - Math.sin( x_axis_rotation ) * dx2 + Math.cos( x_axis_rotation ) * dy2;

			// Compute (cx', cy')
			let rxs = rx * rx;
			let rys = ry * ry;
			const x1ps = x1p * x1p;
			const y1ps = y1p * y1p;

			// Ensure radii are large enough
			const cr = x1ps / rxs + y1ps / rys;

			if ( cr > 1 ) {

				// scale up rx,ry equally so cr == 1
				const s = Math.sqrt( cr );
				rx = s * rx;
				ry = s * ry;
				rxs = rx * rx;
				rys = ry * ry;

			}

			const dq = ( rxs * y1ps + rys * x1ps );
			const pq = ( rxs * rys - dq ) / dq;
			let q = Math.sqrt( Math.max( 0, pq ) );
			if ( large_arc_flag === sweep_flag ) q = - q;
			const cxp = q * rx * y1p / ry;
			const cyp = - q * ry * x1p / rx;

			// Step 3: Compute (cx, cy) from (cx', cy')
			const cx = Math.cos( x_axis_rotation ) * cxp - Math.sin( x_axis_rotation ) * cyp + ( start.x + end.x ) / 2;
			const cy = Math.sin( x_axis_rotation ) * cxp + Math.cos( x_axis_rotation ) * cyp + ( start.y + end.y ) / 2;

			// Step 4: Compute θ1 and Δθ
			const theta = svgAngle( 1, 0, ( x1p - cxp ) / rx, ( y1p - cyp ) / ry );
			const delta = svgAngle( ( x1p - cxp ) / rx, ( y1p - cyp ) / ry, ( - x1p - cxp ) / rx, ( - y1p - cyp ) / ry ) % ( Math.PI * 2 );

			path.currentPath.absellipse( cx, cy, rx, ry, theta, theta + delta, sweep_flag === 0, x_axis_rotation );

		}

		function svgAngle( ux, uy, vx, vy ) {

			const dot = ux * vx + uy * vy;
			const len = Math.sqrt( ux * ux + uy * uy ) * Math.sqrt( vx * vx + vy * vy );
			let ang = Math.acos( Math.max( - 1, Math.min( 1, dot / len ) ) ); // floating point precision, slightly over values appear
			if ( ( ux * vy - uy * vx ) < 0 ) ang = - ang;
			return ang;

		}

		/*
		* According to https://www.w3.org/TR/SVG/shapes.html#RectElementRXAttribute
		* rounded corner should be rendered to elliptical arc, but bezier curve does the job well enough
		*/

		function parseRectNode( node ) {

			const x = parseFloatWithUnits( node.getAttribute( 'x' ) || 0 );
			const y = parseFloatWithUnits( node.getAttribute( 'y' ) || 0 );
			const rx = parseFloatWithUnits( node.getAttribute( 'rx' ) || node.getAttribute( 'ry' ) || 0 );
			const ry = parseFloatWithUnits( node.getAttribute( 'ry' ) || node.getAttribute( 'rx' ) || 0 );
			const w = parseFloatWithUnits( node.getAttribute( 'width' ) );
			const h = parseFloatWithUnits( node.getAttribute( 'height' ) );

			// Ellipse arc to Bezier approximation Coefficient (Inversed). See:
			// https://spencermortensen.com/articles/bezier-circle/
			const bci = 1 - 0.551915024494;

			const path = new ShapePath();

			// top left
			path.moveTo( x + rx, y );

			// top right
			path.lineTo( x + w - rx, y );
			if ( rx !== 0 || ry !== 0 ) {

				path.bezierCurveTo(
					x + w - rx * bci,
					y,
					x + w,
					y + ry * bci,
					x + w,
					y + ry
				);

			}

			// bottom right
			path.lineTo( x + w, y + h - ry );
			if ( rx !== 0 || ry !== 0 ) {

				path.bezierCurveTo(
					x + w,
					y + h - ry * bci,
					x + w - rx * bci,
					y + h,
					x + w - rx,
					y + h
				);

			}

			// bottom left
			path.lineTo( x + rx, y + h );
			if ( rx !== 0 || ry !== 0 ) {

				path.bezierCurveTo(
					x + rx * bci,
					y + h,
					x,
					y + h - ry * bci,
					x,
					y + h - ry
				);

			}

			// back to top left
			path.lineTo( x, y + ry );
			if ( rx !== 0 || ry !== 0 ) {

				path.bezierCurveTo( x, y + ry * bci, x + rx * bci, y, x + rx, y );

			}

			return path;

		}

		function parsePolygonNode( node ) {

			function iterator( match, a, b ) {

				const x = parseFloatWithUnits( a );
				const y = parseFloatWithUnits( b );

				if ( index === 0 ) {

					path.moveTo( x, y );

				} else {

					path.lineTo( x, y );

				}

				index ++;

			}

			const regex = /([+-]?\d*\.?\d+(?:e[+-]?\d+)?)(?:,|\s)([+-]?\d*\.?\d+(?:e[+-]?\d+)?)/g;

			const path = new ShapePath();

			let index = 0;

			node.getAttribute( 'points' ).replace( regex, iterator );

			path.currentPath.autoClose = true;

			return path;

		}

		function parsePolylineNode( node ) {

			function iterator( match, a, b ) {

				const x = parseFloatWithUnits( a );
				const y = parseFloatWithUnits( b );

				if ( index === 0 ) {

					path.moveTo( x, y );

				} else {

					path.lineTo( x, y );

				}

				index ++;

			}

			const regex = /([+-]?\d*\.?\d+(?:e[+-]?\d+)?)(?:,|\s)([+-]?\d*\.?\d+(?:e[+-]?\d+)?)/g;

			const path = new ShapePath();

			let index = 0;

			node.getAttribute( 'points' ).replace( regex, iterator );

			path.currentPath.autoClose = false;

			return path;

		}

		function parseCircleNode( node ) {

			const x = parseFloatWithUnits( node.getAttribute( 'cx' ) || 0 );
			const y = parseFloatWithUnits( node.getAttribute( 'cy' ) || 0 );
			const r = parseFloatWithUnits( node.getAttribute( 'r' ) || 0 );

			const subpath = new Path();
			subpath.absarc( x, y, r, 0, Math.PI * 2 );

			const path = new ShapePath();
			path.subPaths.push( subpath );

			return path;

		}

		function parseEllipseNode( node ) {

			const x = parseFloatWithUnits( node.getAttribute( 'cx' ) || 0 );
			const y = parseFloatWithUnits( node.getAttribute( 'cy' ) || 0 );
			const rx = parseFloatWithUnits( node.getAttribute( 'rx' ) || 0 );
			const ry = parseFloatWithUnits( node.getAttribute( 'ry' ) || 0 );

			const subpath = new Path();
			subpath.absellipse( x, y, rx, ry, 0, Math.PI * 2 );

			const path = new ShapePath();
			path.subPaths.push( subpath );

			return path;

		}

		function parseLineNode( node ) {

			const x1 = parseFloatWithUnits( node.getAttribute( 'x1' ) || 0 );
			const y1 = parseFloatWithUnits( node.getAttribute( 'y1' ) || 0 );
			const x2 = parseFloatWithUnits( node.getAttribute( 'x2' ) || 0 );
			const y2 = parseFloatWithUnits( node.getAttribute( 'y2' ) || 0 );

			const path = new ShapePath();
			path.moveTo( x1, y1 );
			path.lineTo( x2, y2 );
			path.currentPath.autoClose = false;

			return path;

		}

		//

		function parseStyle( node, style ) {

			style = Object.assign( {}, style ); // clone style

			let stylesheetStyles = {};

			if ( node.hasAttribute( 'class' ) ) {

				const classSelectors = node.getAttribute( 'class' )
					.split( /\s/ )
					.filter( Boolean )
					.map( i => i.trim() );

				for ( let i = 0; i < classSelectors.length; i ++ ) {

					stylesheetStyles = Object.assign( stylesheetStyles, stylesheets[ '.' + classSelectors[ i ] ] );

				}

			}

			if ( node.hasAttribute( 'id' ) ) {

				stylesheetStyles = Object.assign( stylesheetStyles, stylesheets[ '#' + node.getAttribute( 'id' ) ] );

			}

			function addStyle( svgName, jsName, adjustFunction ) {

				if ( adjustFunction === undefined ) adjustFunction = function copy( v ) {

					if ( v.startsWith( 'url' ) ) console.warn( 'SVGLoader: url access in attributes is not implemented.' );

					return v;

				};

				if ( node.hasAttribute( svgName ) ) style[ jsName ] = adjustFunction( node.getAttribute( svgName ) );
				if ( stylesheetStyles[ svgName ] ) style[ jsName ] = adjustFunction( stylesheetStyles[ svgName ] );
				if ( node.style && node.style[ svgName ] !== '' ) style[ jsName ] = adjustFunction( node.style[ svgName ] );

			}

			function clamp( v ) {

				return Math.max( 0, Math.min( 1, parseFloatWithUnits( v ) ) );

			}

			function positive( v ) {

				return Math.max( 0, parseFloatWithUnits( v ) );

			}

			addStyle( 'fill', 'fill' );
			addStyle( 'fill-opacity', 'fillOpacity', clamp );
			addStyle( 'fill-rule', 'fillRule' );
			addStyle( 'opacity', 'opacity', clamp );
			addStyle( 'stroke', 'stroke' );
			addStyle( 'stroke-opacity', 'strokeOpacity', clamp );
			addStyle( 'stroke-width', 'strokeWidth', positive );
			addStyle( 'stroke-linejoin', 'strokeLineJoin' );
			addStyle( 'stroke-linecap', 'strokeLineCap' );
			addStyle( 'stroke-miterlimit', 'strokeMiterLimit', positive );
			addStyle( 'visibility', 'visibility' );

			return style;

		}

		// http://www.w3.org/TR/SVG11/implnote.html#PathElementImplementationNotes

		function getReflection( a, b ) {

			return a - ( b - a );

		}

		// from https://github.com/ppvg/svg-numbers (MIT License)

		function parseFloats( input, flags, stride ) {

			if ( typeof input !== 'string' ) {

				throw new TypeError( 'Invalid input: ' + typeof input );

			}

			// Character groups
			const RE = {
				SEPARATOR: /[ \t\r\n\,.\-+]/,
				WHITESPACE: /[ \t\r\n]/,
				DIGIT: /[\d]/,
				SIGN: /[-+]/,
				POINT: /\./,
				COMMA: /,/,
				EXP: /e/i,
				FLAGS: /[01]/
			};

			// States
			const SEP = 0;
			const INT = 1;
			const FLOAT = 2;
			const EXP = 3;

			let state = SEP;
			let seenComma = true;
			let number = '', exponent = '';
			const result = [];

			function throwSyntaxError( current, i, partial ) {

				const error = new SyntaxError( 'Unexpected character "' + current + '" at index ' + i + '.' );
				error.partial = partial;
				throw error;

			}

			function newNumber() {

				if ( number !== '' ) {

					if ( exponent === '' ) result.push( Number( number ) );
					else result.push( Number( number ) * Math.pow( 10, Number( exponent ) ) );

				}

				number = '';
				exponent = '';

			}

			let current;
			const length = input.length;

			for ( let i = 0; i < length; i ++ ) {

				current = input[ i ];

				// check for flags
				if ( Array.isArray( flags ) && flags.includes( result.length % stride ) && RE.FLAGS.test( current ) ) {

					state = INT;
					number = current;
					newNumber();
					continue;

				}

				// parse until next number
				if ( state === SEP ) {

					// eat whitespace
					if ( RE.WHITESPACE.test( current ) ) {

						continue;

					}

					// start new number
					if ( RE.DIGIT.test( current ) || RE.SIGN.test( current ) ) {

						state = INT;
						number = current;
						continue;

					}

					if ( RE.POINT.test( current ) ) {

						state = FLOAT;
						number = current;
						continue;

					}

					// throw on double commas (e.g. "1, , 2")
					if ( RE.COMMA.test( current ) ) {

						if ( seenComma ) {

							throwSyntaxError( current, i, result );

						}

						seenComma = true;

					}

				}

				// parse integer part
				if ( state === INT ) {

					if ( RE.DIGIT.test( current ) ) {

						number += current;
						continue;

					}

					if ( RE.POINT.test( current ) ) {

						number += current;
						state = FLOAT;
						continue;

					}

					if ( RE.EXP.test( current ) ) {

						state = EXP;
						continue;

					}

					// throw on double signs ("-+1"), but not on sign as separator ("-1-2")
					if ( RE.SIGN.test( current )
							&& number.length === 1
							&& RE.SIGN.test( number[ 0 ] ) ) {

						throwSyntaxError( current, i, result );

					}

				}

				// parse decimal part
				if ( state === FLOAT ) {

					if ( RE.DIGIT.test( current ) ) {

						number += current;
						continue;

					}

					if ( RE.EXP.test( current ) ) {

						state = EXP;
						continue;

					}

					// throw on double decimal points (e.g. "1..2")
					if ( RE.POINT.test( current ) && number[ number.length - 1 ] === '.' ) {

						throwSyntaxError( current, i, result );

					}

				}

				// parse exponent part
				if ( state === EXP ) {

					if ( RE.DIGIT.test( current ) ) {

						exponent += current;
						continue;

					}

					if ( RE.SIGN.test( current ) ) {

						if ( exponent === '' ) {

							exponent += current;
							continue;

						}

						if ( exponent.length === 1 && RE.SIGN.test( exponent ) ) {

							throwSyntaxError( current, i, result );

						}

					}

				}


				// end of number
				if ( RE.WHITESPACE.test( current ) ) {

					newNumber();
					state = SEP;
					seenComma = false;

				} else if ( RE.COMMA.test( current ) ) {

					newNumber();
					state = SEP;
					seenComma = true;

				} else if ( RE.SIGN.test( current ) ) {

					newNumber();
					state = INT;
					number = current;

				} else if ( RE.POINT.test( current ) ) {

					newNumber();
					state = FLOAT;
					number = current;

				} else {

					throwSyntaxError( current, i, result );

				}

			}

			// add the last number found (if any)
			newNumber();

			return result;

		}

		// Units

		const units = [ 'mm', 'cm', 'in', 'pt', 'pc', 'px' ];

		// Conversion: [ fromUnit ][ toUnit ] (-1 means dpi dependent)
		const unitConversion = {

			'mm': {
				'mm': 1,
				'cm': 0.1,
				'in': 1 / 25.4,
				'pt': 72 / 25.4,
				'pc': 6 / 25.4,
				'px': - 1
			},
			'cm': {
				'mm': 10,
				'cm': 1,
				'in': 1 / 2.54,
				'pt': 72 / 2.54,
				'pc': 6 / 2.54,
				'px': - 1
			},
			'in': {
				'mm': 25.4,
				'cm': 2.54,
				'in': 1,
				'pt': 72,
				'pc': 6,
				'px': - 1
			},
			'pt': {
				'mm': 25.4 / 72,
				'cm': 2.54 / 72,
				'in': 1 / 72,
				'pt': 1,
				'pc': 6 / 72,
				'px': - 1
			},
			'pc': {
				'mm': 25.4 / 6,
				'cm': 2.54 / 6,
				'in': 1 / 6,
				'pt': 72 / 6,
				'pc': 1,
				'px': - 1
			},
			'px': {
				'px': 1
			}

		};

		function parseFloatWithUnits( string ) {

			let theUnit = 'px';

			if ( typeof string === 'string' || string instanceof String ) {

				for ( let i = 0, n = units.length; i < n; i ++ ) {

					const u = units[ i ];

					if ( string.endsWith( u ) ) {

						theUnit = u;
						string = string.substring( 0, string.length - u.length );
						break;

					}

				}

			}

			let scale = undefined;

			if ( theUnit === 'px' && scope.defaultUnit !== 'px' ) {

				// Conversion scale from  pixels to inches, then to default units

				scale = unitConversion[ 'in' ][ scope.defaultUnit ] / scope.defaultDPI;

			} else {

				scale = unitConversion[ theUnit ][ scope.defaultUnit ];

				if ( scale < 0 ) {

					// Conversion scale to pixels

					scale = unitConversion[ theUnit ][ 'in' ] * scope.defaultDPI;

				}

			}

			return scale * parseFloat( string );

		}

		// Transforms

		function getNodeTransform( node ) {

			if ( ! ( node.hasAttribute( 'transform' ) || ( node.nodeName === 'use' && ( node.hasAttribute( 'x' ) || node.hasAttribute( 'y' ) ) ) ) ) {

				return null;

			}

			const transform = parseNodeTransform( node );

			if ( transformStack.length > 0 ) {

				transform.premultiply( transformStack[ transformStack.length - 1 ] );

			}

			currentTransform.copy( transform );
			transformStack.push( transform );

			return transform;

		}

		function parseNodeTransform( node ) {

			const transform = new Matrix3();
			const currentTransform = tempTransform0;

			if ( node.nodeName === 'use' && ( node.hasAttribute( 'x' ) || node.hasAttribute( 'y' ) ) ) {

				const tx = parseFloatWithUnits( node.getAttribute( 'x' ) );
				const ty = parseFloatWithUnits( node.getAttribute( 'y' ) );

				transform.translate( tx, ty );

			}

			if ( node.hasAttribute( 'transform' ) ) {

				const transformsTexts = node.getAttribute( 'transform' ).split( ')' );

				for ( let tIndex = transformsTexts.length - 1; tIndex >= 0; tIndex -- ) {

					const transformText = transformsTexts[ tIndex ].trim();

					if ( transformText === '' ) continue;

					const openParPos = transformText.indexOf( '(' );
					const closeParPos = transformText.length;

					if ( openParPos > 0 && openParPos < closeParPos ) {

						const transformType = transformText.slice( 0, openParPos );

						const array = parseFloats( transformText.slice( openParPos + 1 ) );

						currentTransform.identity();

						switch ( transformType ) {

							case 'translate':

								if ( array.length >= 1 ) {

									const tx = array[ 0 ];
									let ty = 0;

									if ( array.length >= 2 ) {

										ty = array[ 1 ];

									}

									currentTransform.translate( tx, ty );

								}

								break;

							case 'rotate':

								if ( array.length >= 1 ) {

									let angle = 0;
									let cx = 0;
									let cy = 0;

									// Angle
									angle = array[ 0 ] * Math.PI / 180;

									if ( array.length >= 3 ) {

										// Center x, y
										cx = array[ 1 ];
										cy = array[ 2 ];

									}

									// Rotate around center (cx, cy)
									tempTransform1.makeTranslation( - cx, - cy );
									tempTransform2.makeRotation( angle );
									tempTransform3.multiplyMatrices( tempTransform2, tempTransform1 );
									tempTransform1.makeTranslation( cx, cy );
									currentTransform.multiplyMatrices( tempTransform1, tempTransform3 );

								}

								break;

							case 'scale':

								if ( array.length >= 1 ) {

									const scaleX = array[ 0 ];
									let scaleY = scaleX;

									if ( array.length >= 2 ) {

										scaleY = array[ 1 ];

									}

									currentTransform.scale( scaleX, scaleY );

								}

								break;

							case 'skewX':

								if ( array.length === 1 ) {

									currentTransform.set(
										1, Math.tan( array[ 0 ] * Math.PI / 180 ), 0,
										0, 1, 0,
										0, 0, 1
									);

								}

								break;

							case 'skewY':

								if ( array.length === 1 ) {

									currentTransform.set(
										1, 0, 0,
										Math.tan( array[ 0 ] * Math.PI / 180 ), 1, 0,
										0, 0, 1
									);

								}

								break;

							case 'matrix':

								if ( array.length === 6 ) {

									currentTransform.set(
										array[ 0 ], array[ 2 ], array[ 4 ],
										array[ 1 ], array[ 3 ], array[ 5 ],
										0, 0, 1
									);

								}

								break;

						}

					}

					transform.premultiply( currentTransform );

				}

			}

			return transform;

		}

		function transformPath( path, m ) {

			function transfVec2( v2 ) {

				tempV3.set( v2.x, v2.y, 1 ).applyMatrix3( m );

				v2.set( tempV3.x, tempV3.y );

			}

			function transfEllipseGeneric( curve ) {

				// For math description see:
				// https://math.stackexchange.com/questions/4544164

				const a = curve.xRadius;
				const b = curve.yRadius;

				const cosTheta = Math.cos( curve.aRotation );
				const sinTheta = Math.sin( curve.aRotation );

				const v1 = new Vector3( a * cosTheta, a * sinTheta, 0 );
				const v2 = new Vector3( - b * sinTheta, b * cosTheta, 0 );

				const f1 = v1.applyMatrix3( m );
				const f2 = v2.applyMatrix3( m );

				const mF = tempTransform0.set(
					f1.x, f2.x, 0,
					f1.y, f2.y, 0,
					0, 0, 1,
				);

				const mFInv = tempTransform1.copy( mF ).invert();
				const mFInvT = tempTransform2.copy( mFInv ).transpose();
				const mQ = mFInvT.multiply( mFInv );
				const mQe = mQ.elements;

				const ed = eigenDecomposition( mQe[ 0 ], mQe[ 1 ], mQe[ 4 ] );
				const rt1sqrt = Math.sqrt( ed.rt1 );
				const rt2sqrt = Math.sqrt( ed.rt2 );

				curve.xRadius = 1 / rt1sqrt;
				curve.yRadius = 1 / rt2sqrt;
				curve.aRotation = Math.atan2( ed.sn, ed.cs );

				const isFullEllipse =
					( curve.aEndAngle - curve.aStartAngle ) % ( 2 * Math.PI ) < Number.EPSILON;

				// Do not touch angles of a full ellipse because after transformation they
				// would converge to a single value effectively removing the whole curve

				if ( ! isFullEllipse ) {

					const mDsqrt = tempTransform1.set(
						rt1sqrt, 0, 0,
						0, rt2sqrt, 0,
						0, 0, 1,
					);

					const mRT = tempTransform2.set(
						ed.cs, ed.sn, 0,
						- ed.sn, ed.cs, 0,
						0, 0, 1,
					);

					const mDRF = mDsqrt.multiply( mRT ).multiply( mF );

					const transformAngle = phi => {

						const { x: cosR, y: sinR } =
							new Vector3( Math.cos( phi ), Math.sin( phi ), 0 ).applyMatrix3( mDRF );

						return Math.atan2( sinR, cosR );

					};

					curve.aStartAngle = transformAngle( curve.aStartAngle );
					curve.aEndAngle = transformAngle( curve.aEndAngle );

					if ( isTransformFlipped( m ) ) {

						curve.aClockwise = ! curve.aClockwise;

					}

				}

			}

			function transfEllipseNoSkew( curve ) {

				// Faster shortcut if no skew is applied
				// (e.g, a euclidean transform of a group containing the ellipse)

				const sx = getTransformScaleX( m );
				const sy = getTransformScaleY( m );

				curve.xRadius *= sx;
				curve.yRadius *= sy;

				// Extract rotation angle from the matrix of form:
				//
				//  | cosθ sx   -sinθ sy |
				//  | sinθ sx    cosθ sy |
				//
				// Remembering that tanθ = sinθ / cosθ; and that
				// `sx`, `sy`, or both might be zero.
				const theta =
					sx > Number.EPSILON
						? Math.atan2( m.elements[ 1 ], m.elements[ 0 ] )
						: Math.atan2( - m.elements[ 3 ], m.elements[ 4 ] );

				curve.aRotation += theta;

				if ( isTransformFlipped( m ) ) {

					curve.aStartAngle *= - 1;
					curve.aEndAngle *= - 1;
					curve.aClockwise = ! curve.aClockwise;

				}

			}

			const subPaths = path.subPaths;

			for ( let i = 0, n = subPaths.length; i < n; i ++ ) {

				const subPath = subPaths[ i ];
				const curves = subPath.curves;

				for ( let j = 0; j < curves.length; j ++ ) {

					const curve = curves[ j ];

					if ( curve.isLineCurve ) {

						transfVec2( curve.v1 );
						transfVec2( curve.v2 );

					} else if ( curve.isCubicBezierCurve ) {

						transfVec2( curve.v0 );
						transfVec2( curve.v1 );
						transfVec2( curve.v2 );
						transfVec2( curve.v3 );

					} else if ( curve.isQuadraticBezierCurve ) {

						transfVec2( curve.v0 );
						transfVec2( curve.v1 );
						transfVec2( curve.v2 );

					} else if ( curve.isEllipseCurve ) {

						// Transform ellipse center point

						tempV2.set( curve.aX, curve.aY );
						transfVec2( tempV2 );
						curve.aX = tempV2.x;
						curve.aY = tempV2.y;

						// Transform ellipse shape parameters

						if ( isTransformSkewed( m ) ) {

							transfEllipseGeneric( curve );

						} else {

							transfEllipseNoSkew( curve );

						}

					}

				}

			}

		}

		function isTransformFlipped( m ) {

			const te = m.elements;
			return te[ 0 ] * te[ 4 ] - te[ 1 ] * te[ 3 ] < 0;

		}

		function isTransformSkewed( m ) {

			const te = m.elements;
			const basisDot = te[ 0 ] * te[ 3 ] + te[ 1 ] * te[ 4 ];

			// Shortcut for trivial rotations and transformations
			if ( basisDot === 0 ) return false;

			const sx = getTransformScaleX( m );
			const sy = getTransformScaleY( m );

			return Math.abs( basisDot / ( sx * sy ) ) > Number.EPSILON;

		}

		function getTransformScaleX( m ) {

			const te = m.elements;
			return Math.sqrt( te[ 0 ] * te[ 0 ] + te[ 1 ] * te[ 1 ] );

		}

		function getTransformScaleY( m ) {

			const te = m.elements;
			return Math.sqrt( te[ 3 ] * te[ 3 ] + te[ 4 ] * te[ 4 ] );

		}

		// Calculates the eigensystem of a real symmetric 2x2 matrix
		//    [ A  B ]
		//    [ B  C ]
		// in the form
		//    [ A  B ]  =  [ cs  -sn ] [ rt1   0  ] [  cs  sn ]
		//    [ B  C ]     [ sn   cs ] [  0   rt2 ] [ -sn  cs ]
		// where rt1 >= rt2.
		//
		// Adapted from: https://www.mpi-hd.mpg.de/personalhomes/globes/3x3/index.html
		// -> Algorithms for real symmetric matrices -> Analytical (2x2 symmetric)
		function eigenDecomposition( A, B, C ) {

			let rt1, rt2, cs, sn, t;
			const sm = A + C;
			const df = A - C;
			const rt = Math.sqrt( df * df + 4 * B * B );

			if ( sm > 0 ) {

				rt1 = 0.5 * ( sm + rt );
				t = 1 / rt1;
				rt2 = A * t * C - B * t * B;

			} else if ( sm < 0 ) {

				rt2 = 0.5 * ( sm - rt );

			} else {

				// This case needs to be treated separately to avoid div by 0

				rt1 = 0.5 * rt;
				rt2 = - 0.5 * rt;

			}

			// Calculate eigenvectors

			if ( df > 0 ) {

				cs = df + rt;

			} else {

				cs = df - rt;

			}

			if ( Math.abs( cs ) > 2 * Math.abs( B ) ) {

				t = - 2 * B / cs;
				sn = 1 / Math.sqrt( 1 + t * t );
				cs = t * sn;

			} else if ( Math.abs( B ) === 0 ) {

				cs = 1;
				sn = 0;

			} else {

				t = - 0.5 * cs / B;
				cs = 1 / Math.sqrt( 1 + t * t );
				sn = t * cs;

			}

			if ( df > 0 ) {

				t = cs;
				cs = - sn;
				sn = t;

			}

			return { rt1, rt2, cs, sn };

		}

		//

		const paths = [];
		const stylesheets = {};

		const transformStack = [];

		const tempTransform0 = new Matrix3();
		const tempTransform1 = new Matrix3();
		const tempTransform2 = new Matrix3();
		const tempTransform3 = new Matrix3();
		const tempV2 = new Vector2();
		const tempV3 = new Vector3();

		const currentTransform = new Matrix3();

		const xml = new DOMParser().parseFromString( text, 'image/svg+xml' ); // application/xml

		parseNode( xml.documentElement, {
			fill: '#000',
			fillOpacity: 1,
			strokeOpacity: 1,
			strokeWidth: 1,
			strokeLineJoin: 'miter',
			strokeLineCap: 'butt',
			strokeMiterLimit: 4
		} );

		const data = { paths: paths, xml: xml.documentElement };

		// console.log( paths );
		return data;

	}
```
</details>

### `SVGLoader.createShapes(shapePath: ShapePath): Shape[]`

**JSDoc:**
```typescript
/**
	 * Creates from the given shape path and array of shapes.
	 *
	 * @param {ShapePath} shapePath - The shape path.
	 * @return {Array<Shape>} An array of shapes.
	 */
```

**Parameters:**

- **`shapePath`** `ShapePath`

**Returns:** `Shape[]`

**Calls:**

- `classifyPoint`
- `( x1 + classifyResult.t * ( x2 - x1 ) ).toPrecision`
- `( y1 + classifyResult.t * ( y2 - y1 ) ).toPrecision`
- `( x1 + t1 * ( x2 - x1 ) ).toPrecision`
- `( y1 + t1 * ( y2 - y1 ) ).toPrecision`
- `Math.sqrt`
- `findEdgeIntersection`
- `intersectionsRaw.find`
- `intersectionsRaw.push`
- `intersections.push`
- `boundingBox.getCenter`
- `paths.forEach`
- `path.boundingBox.containsPoint`
- `getIntersections`
- `intersections.forEach`
- `allIntersections.push`
- `allIntersections.sort`
- `simplePath.boundingBox.getCenter`
- `getScanlineIntersections`
- `scanlineIntersections.sort`
- `scanlineIntersections.forEach`
- `baseIntersections.push`
- `otherIntersections.push`
- `stack.pop`
- `stack.push`
- `console.warn`
- `shapePath.subPaths.map`
- `p.getPoints`
- `ShapeUtils.isClockWise`
- `simplePaths.filter`
- `simplePaths.map`
- `isHoleTo`
- `simplePaths.forEach`
- `isAHole.filter`
- `holes.forEach`
- `shape.holes.push`
- `shapesToReturn.push`

**Internal Comments:**
```
//1. lines are parallel or edges don't intersect
//2. lines are colinear
//check if endpoints of edge2 (b0-b1) lies on edge1 (a0-a1)
//find position of this endpoints relatively to edge1
//3. edges intersect
// check if the center of the bounding box is in the bounding box of the paths.
// this is a pruning method to limit the search of intersections in paths that can't envelop of the current path.
// if a path envelops another path. The center of that other path, has to be inside the bounding box of the enveloping path.
// build up the path hierarchy (x2)
// check if path is a hole by counting the amount of paths with alternating rotations it has to cross. (x2)
// check for self intersecting paths (x2)
// TODO (x4)
// check intersecting paths (x2)
// prepare paths for hole detection (x2)
//points.forEach(p => p.y *= -1);
//
// check if path is solid or a hole (x2)
```

<details><summary>Code</summary>

```typescript
static createShapes( shapePath ) {

		const BIGNUMBER = 999999999;

		const IntersectionLocationType = {
			ORIGIN: 0,
			DESTINATION: 1,
			BETWEEN: 2,
			LEFT: 3,
			RIGHT: 4,
			BEHIND: 5,
			BEYOND: 6
		};

		const classifyResult = {
			loc: IntersectionLocationType.ORIGIN,
			t: 0
		};

		function findEdgeIntersection( a0, a1, b0, b1 ) {

			const x1 = a0.x;
			const x2 = a1.x;
			const x3 = b0.x;
			const x4 = b1.x;
			const y1 = a0.y;
			const y2 = a1.y;
			const y3 = b0.y;
			const y4 = b1.y;
			const nom1 = ( x4 - x3 ) * ( y1 - y3 ) - ( y4 - y3 ) * ( x1 - x3 );
			const nom2 = ( x2 - x1 ) * ( y1 - y3 ) - ( y2 - y1 ) * ( x1 - x3 );
			const denom = ( y4 - y3 ) * ( x2 - x1 ) - ( x4 - x3 ) * ( y2 - y1 );
			const t1 = nom1 / denom;
			const t2 = nom2 / denom;

			if ( ( ( denom === 0 ) && ( nom1 !== 0 ) ) || ( t1 <= 0 ) || ( t1 >= 1 ) || ( t2 < 0 ) || ( t2 > 1 ) ) {

				//1. lines are parallel or edges don't intersect

				return null;

			} else if ( ( nom1 === 0 ) && ( denom === 0 ) ) {

				//2. lines are colinear

				//check if endpoints of edge2 (b0-b1) lies on edge1 (a0-a1)
				for ( let i = 0; i < 2; i ++ ) {

					classifyPoint( i === 0 ? b0 : b1, a0, a1 );
					//find position of this endpoints relatively to edge1
					if ( classifyResult.loc == IntersectionLocationType.ORIGIN ) {

						const point = ( i === 0 ? b0 : b1 );
						return { x: point.x, y: point.y, t: classifyResult.t };

					} else if ( classifyResult.loc == IntersectionLocationType.BETWEEN ) {

						const x = + ( ( x1 + classifyResult.t * ( x2 - x1 ) ).toPrecision( 10 ) );
						const y = + ( ( y1 + classifyResult.t * ( y2 - y1 ) ).toPrecision( 10 ) );
						return { x: x, y: y, t: classifyResult.t, };

					}

				}

				return null;

			} else {

				//3. edges intersect

				for ( let i = 0; i < 2; i ++ ) {

					classifyPoint( i === 0 ? b0 : b1, a0, a1 );

					if ( classifyResult.loc == IntersectionLocationType.ORIGIN ) {

						const point = ( i === 0 ? b0 : b1 );
						return { x: point.x, y: point.y, t: classifyResult.t };

					}

				}

				const x = + ( ( x1 + t1 * ( x2 - x1 ) ).toPrecision( 10 ) );
				const y = + ( ( y1 + t1 * ( y2 - y1 ) ).toPrecision( 10 ) );
				return { x: x, y: y, t: t1 };

			}

		}

		function classifyPoint( p, edgeStart, edgeEnd ) {

			const ax = edgeEnd.x - edgeStart.x;
			const ay = edgeEnd.y - edgeStart.y;
			const bx = p.x - edgeStart.x;
			const by = p.y - edgeStart.y;
			const sa = ax * by - bx * ay;

			if ( ( p.x === edgeStart.x ) && ( p.y === edgeStart.y ) ) {

				classifyResult.loc = IntersectionLocationType.ORIGIN;
				classifyResult.t = 0;
				return;

			}

			if ( ( p.x === edgeEnd.x ) && ( p.y === edgeEnd.y ) ) {

				classifyResult.loc = IntersectionLocationType.DESTINATION;
				classifyResult.t = 1;
				return;

			}

			if ( sa < - Number.EPSILON ) {

				classifyResult.loc = IntersectionLocationType.LEFT;
				return;

			}

			if ( sa > Number.EPSILON ) {

				classifyResult.loc = IntersectionLocationType.RIGHT;
				return;


			}

			if ( ( ( ax * bx ) < 0 ) || ( ( ay * by ) < 0 ) ) {

				classifyResult.loc = IntersectionLocationType.BEHIND;
				return;

			}

			if ( ( Math.sqrt( ax * ax + ay * ay ) ) < ( Math.sqrt( bx * bx + by * by ) ) ) {

				classifyResult.loc = IntersectionLocationType.BEYOND;
				return;

			}

			let t;

			if ( ax !== 0 ) {

				t = bx / ax;

			} else {

				t = by / ay;

			}

			classifyResult.loc = IntersectionLocationType.BETWEEN;
			classifyResult.t = t;

		}

		function getIntersections( path1, path2 ) {

			const intersectionsRaw = [];
			const intersections = [];

			for ( let index = 1; index < path1.length; index ++ ) {

				const path1EdgeStart = path1[ index - 1 ];
				const path1EdgeEnd = path1[ index ];

				for ( let index2 = 1; index2 < path2.length; index2 ++ ) {

					const path2EdgeStart = path2[ index2 - 1 ];
					const path2EdgeEnd = path2[ index2 ];

					const intersection = findEdgeIntersection( path1EdgeStart, path1EdgeEnd, path2EdgeStart, path2EdgeEnd );

					if ( intersection !== null && intersectionsRaw.find( i => i.t <= intersection.t + Number.EPSILON && i.t >= intersection.t - Number.EPSILON ) === undefined ) {

						intersectionsRaw.push( intersection );
						intersections.push( new Vector2( intersection.x, intersection.y ) );

					}

				}

			}

			return intersections;

		}

		function getScanlineIntersections( scanline, boundingBox, paths ) {

			const center = new Vector2();
			boundingBox.getCenter( center );

			const allIntersections = [];

			paths.forEach( path => {

				// check if the center of the bounding box is in the bounding box of the paths.
				// this is a pruning method to limit the search of intersections in paths that can't envelop of the current path.
				// if a path envelops another path. The center of that other path, has to be inside the bounding box of the enveloping path.
				if ( path.boundingBox.containsPoint( center ) ) {

					const intersections = getIntersections( scanline, path.points );

					intersections.forEach( p => {

						allIntersections.push( { identifier: path.identifier, isCW: path.isCW, point: p } );

					} );

				}

			} );

			allIntersections.sort( ( i1, i2 ) => {

				return i1.point.x - i2.point.x;

			} );

			return allIntersections;

		}

		function isHoleTo( simplePath, allPaths, scanlineMinX, scanlineMaxX, _fillRule ) {

			if ( _fillRule === null || _fillRule === undefined || _fillRule === '' ) {

				_fillRule = 'nonzero';

			}

			const centerBoundingBox = new Vector2();
			simplePath.boundingBox.getCenter( centerBoundingBox );

			const scanline = [ new Vector2( scanlineMinX, centerBoundingBox.y ), new Vector2( scanlineMaxX, centerBoundingBox.y ) ];

			const scanlineIntersections = getScanlineIntersections( scanline, simplePath.boundingBox, allPaths );

			scanlineIntersections.sort( ( i1, i2 ) => {

				return i1.point.x - i2.point.x;

			} );

			const baseIntersections = [];
			const otherIntersections = [];

			scanlineIntersections.forEach( i => {

				if ( i.identifier === simplePath.identifier ) {

					baseIntersections.push( i );

				} else {

					otherIntersections.push( i );

				}

			} );

			const firstXOfPath = baseIntersections[ 0 ].point.x;

			// build up the path hierarchy
			const stack = [];
			let i = 0;

			while ( i < otherIntersections.length && otherIntersections[ i ].point.x < firstXOfPath ) {

				if ( stack.length > 0 && stack[ stack.length - 1 ] === otherIntersections[ i ].identifier ) {

					stack.pop();

				} else {

					stack.push( otherIntersections[ i ].identifier );

				}

				i ++;

			}

			stack.push( simplePath.identifier );

			if ( _fillRule === 'evenodd' ) {

				const isHole = stack.length % 2 === 0 ? true : false;
				const isHoleFor = stack[ stack.length - 2 ];

				return { identifier: simplePath.identifier, isHole: isHole, for: isHoleFor };

			} else if ( _fillRule === 'nonzero' ) {

				// check if path is a hole by counting the amount of paths with alternating rotations it has to cross.
				let isHole = true;
				let isHoleFor = null;
				let lastCWValue = null;

				for ( let i = 0; i < stack.length; i ++ ) {

					const identifier = stack[ i ];
					if ( isHole ) {

						lastCWValue = allPaths[ identifier ].isCW;
						isHole = false;
						isHoleFor = identifier;

					} else if ( lastCWValue !== allPaths[ identifier ].isCW ) {

						lastCWValue = allPaths[ identifier ].isCW;
						isHole = true;

					}

				}

				return { identifier: simplePath.identifier, isHole: isHole, for: isHoleFor };

			} else {

				console.warn( 'fill-rule: "' + _fillRule + '" is currently not implemented.' );

			}

		}

		// check for self intersecting paths
		// TODO

		// check intersecting paths
		// TODO

		// prepare paths for hole detection
		let scanlineMinX = BIGNUMBER;
		let scanlineMaxX = - BIGNUMBER;

		let simplePaths = shapePath.subPaths.map( p => {

			const points = p.getPoints();
			let maxY = - BIGNUMBER;
			let minY = BIGNUMBER;
			let maxX = - BIGNUMBER;
			let minX = BIGNUMBER;

	      	//points.forEach(p => p.y *= -1);

			for ( let i = 0; i < points.length; i ++ ) {

				const p = points[ i ];

				if ( p.y > maxY ) {

					maxY = p.y;

				}

				if ( p.y < minY ) {

					minY = p.y;

				}

				if ( p.x > maxX ) {

					maxX = p.x;

				}

				if ( p.x < minX ) {

					minX = p.x;

				}

			}

			//
			if ( scanlineMaxX <= maxX ) {

				scanlineMaxX = maxX + 1;

			}

			if ( scanlineMinX >= minX ) {

				scanlineMinX = minX - 1;

			}

			return { curves: p.curves, points: points, isCW: ShapeUtils.isClockWise( points ), identifier: - 1, boundingBox: new Box2( new Vector2( minX, minY ), new Vector2( maxX, maxY ) ) };

		} );

		simplePaths = simplePaths.filter( sp => sp.points.length > 1 );

		for ( let identifier = 0; identifier < simplePaths.length; identifier ++ ) {

			simplePaths[ identifier ].identifier = identifier;

		}

		// check if path is solid or a hole
		const isAHole = simplePaths.map( p => isHoleTo( p, simplePaths, scanlineMinX, scanlineMaxX, ( shapePath.userData ? shapePath.userData.style.fillRule : undefined ) ) );


		const shapesToReturn = [];
		simplePaths.forEach( p => {

			const amIAHole = isAHole[ p.identifier ];

			if ( ! amIAHole.isHole ) {

				const shape = new Shape();
				shape.curves = p.curves;
				const holes = isAHole.filter( h => h.isHole && h.for === p.identifier );
				holes.forEach( h => {

					const hole = simplePaths[ h.identifier ];
					const path = new Path();
					path.curves = hole.curves;
					shape.holes.push( path );

				} );
				shapesToReturn.push( shape );

			}

		} );

		return shapesToReturn;

	}
```
</details>

### `SVGLoader.getStrokeStyle(width: number, color: string, lineJoin: "round" | "bevel" | "miter" | "miter-limit", lineCap: "round" | "butt" | "square", miterLimit: number): any`

**JSDoc:**
```typescript
/**
	 * Returns a stroke style object from the given parameters.
	 *
	 * @param {number} [width=1] - The stroke width.
	 * @param {string} [color='#000'] - The stroke color, as  returned by {@link Color#getStyle}.
	 * @param {'round'|'bevel'|'miter'|'miter-limit'} [lineJoin='miter'] - The line join style.
	 * @param {'round'|'square'|'butt'} [lineCap='butt'] - The line cap style.
	 * @param {number} [miterLimit=4] - Maximum join length, in multiples of the `width` parameter (join is truncated if it exceeds that distance).
	 * @return {Object} The style object.
	 */
```

**Parameters:**

- **`width`** `number`
- **`color`** `string`
- **`lineJoin`** `"round" | "bevel" | "miter" | "miter-limit"`
- **`lineCap`** `"round" | "butt" | "square"`
- **`miterLimit`** `number`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
static getStrokeStyle( width, color, lineJoin, lineCap, miterLimit ) {

		width = width !== undefined ? width : 1;
		color = color !== undefined ? color : '#000';
		lineJoin = lineJoin !== undefined ? lineJoin : 'miter';
		lineCap = lineCap !== undefined ? lineCap : 'butt';
		miterLimit = miterLimit !== undefined ? miterLimit : 4;

		return {
			strokeColor: color,
			strokeWidth: width,
			strokeLineJoin: lineJoin,
			strokeLineCap: lineCap,
			strokeMiterLimit: miterLimit
		};

	}
```
</details>

### `SVGLoader.pointsToStroke(points: Vector2[], style: any, arcDivisions: number, minDistance: number): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Creates a stroke from an array of points.
	 *
	 * @param {Array<Vector2>} points - The points in 2D space. Minimum 2 points. The path can be open or closed (last point equals to first point).
	 * @param {Object} style - Object with SVG properties as returned by `SVGLoader.getStrokeStyle()`, or `SVGLoader.parse()` in the `path.userData.style` object.
	 * @param {number} [arcDivisions=12] - Arc divisions for round joins and endcaps.
	 * @param {number} [minDistance=0.001] - Points closer to this distance will be merged.
	 * @return {?BufferGeometry} The stroke geometry. UV coordinates are generated ('u' along path. 'v' across it, from left to right).
	 * Returns `null` if not geometry was generated.
	 */
```

**Parameters:**

- **`points`** `Vector2[]`
- **`style`** `any`
- **`arcDivisions`** `number`
- **`minDistance`** `number`

**Returns:** `BufferGeometry`

**Calls:**

- `SVGLoader.pointsToStrokeWithBuffers`
- `geometry.setAttribute`

<details><summary>Code</summary>

```typescript
static pointsToStroke( points, style, arcDivisions, minDistance ) {

		const vertices = [];
		const normals = [];
		const uvs = [];

		if ( SVGLoader.pointsToStrokeWithBuffers( points, style, arcDivisions, minDistance, vertices, normals, uvs ) === 0 ) {

			return null;

		}

		const geometry = new BufferGeometry();
		geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
		geometry.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );
		geometry.setAttribute( 'uv', new Float32BufferAttribute( uvs, 2 ) );

		return geometry;

	}
```
</details>

### `SVGLoader.pointsToStrokeWithBuffers(points: Vector2[], style: any, arcDivisions: number, minDistance: number, vertices: number[], normals: number[], uvs: number[], vertexOffset: number): number`

**JSDoc:**
```typescript
/**
	 * Creates a stroke from an array of points.
	 *
	 * @param {Array<Vector2>} points - The points in 2D space. Minimum 2 points.
	 * @param {Object} style - Object with SVG properties as returned by `SVGLoader.getStrokeStyle()`, or `SVGLoader.parse()` in the `path.userData.style` object.
	 * @param {number} [arcDivisions=12] - Arc divisions for round joins and endcaps.
	 * @param {number} [minDistance=0.001] - Points closer to this distance will be merged.
	 * @param {Array<number>} vertices - An array holding vertices.
	 * @param {Array<number>} normals - An array holding normals.
	 * @param {Array<number>} uvs - An array holding uvs.
	 * @param {number} [vertexOffset=0] - The vertex offset.
	 * @return {number} The number of vertices.
	 */
```

**Parameters:**

- **`points`** `Vector2[]`
- **`style`** `any`
- **`arcDivisions`** `number`
- **`minDistance`** `number`
- **`vertices`** `number[]`
- **`normals`** `number[]`
- **`uvs`** `number[]`
- **`vertexOffset`** `number`

**Returns:** `number`

**Calls:**

- `removeDuplicatedPoints`
- `points[ 0 ].equals`
- `getNormal( points[ 0 ], points[ 1 ], tempV2_1 ).multiplyScalar`
- `lastPointL.copy( points[ 0 ] ).sub`
- `lastPointR.copy( points[ 0 ] ).add`
- `point0L.copy`
- `point0R.copy`
- `getNormal`
- `tempV2_3.copy( normal1 ).multiplyScalar`
- `currentPointL.copy( currentPoint ).sub`
- `currentPointR.copy( currentPoint ).add`
- `tempV2_3.copy( tempV2_2 ).multiplyScalar`
- `nextPointL.copy( currentPoint ).sub`
- `nextPointR.copy( currentPoint ).add`
- `tempV2_3.subVectors`
- `normal1.dot`
- `tempV2_3.normalize`
- `Math.abs`
- `tempV2_3.multiplyScalar`
- `tempV2_4.subVectors`
- `tempV2_5.copy( tempV2_4 ).setLength( miterSide ).add`
- `innerPoint.copy( tempV2_5 ).negate`
- `tempV2_5.length`
- `tempV2_4.length`
- `tempV2_4.divideScalar`
- `tempV2_6.subVectors`
- `tempV2_6.length`
- `tempV2_6.divideScalar`
- `tempV2_4.dot`
- `tempV2_6.dot`
- `outerPoint.copy( tempV2_5 ).add`
- `innerPoint.add`
- `nextPointR.copy`
- `currentPointR.copy`
- `nextPointL.copy`
- `currentPointL.copy`
- `makeSegmentTriangles`
- `makeSegmentWithBevelJoin`
- `createSegmentTrianglesWithMiddleSection`
- `makeCircularSector`
- `tempV2_6.subVectors( outerPoint, currentPointL ).multiplyScalar( miterFraction ).add`
- `tempV2_7.subVectors( outerPoint, nextPointL ).multiplyScalar( miterFraction ).add`
- `addVertex`
- `tempV2_6.subVectors( outerPoint, currentPointR ).multiplyScalar( miterFraction ).add`
- `tempV2_7.subVectors( outerPoint, nextPointR ).multiplyScalar( miterFraction ).add`
- `addCapGeometry`
- `lastPointL.copy`
- `lastPointR.copy`
- `lastInner.toArray`
- `lastOuter.toArray`
- `result.subVectors`
- `result.set( - result.y, result.x ).normalize`
- `tempV2_1.copy( p1 ).sub( center ).normalize`
- `tempV2_2.copy( p2 ).sub( center ).normalize`
- `tempV2_1.dot`
- `Math.acos`
- `tempV2_3.copy`
- `tempV2_4.copy( tempV2_3 ).rotateAround`
- `tempV2_1.subVectors`
- `tempV2_2.set`
- `tempV2_3.addVectors( tempV2_1, tempV2_2 ).add`
- `tempV2_4.subVectors( tempV2_2, tempV2_1 ).add`
- `tempV2_3.toArray`
- `tempV2_4.toArray`
- `points[ i ].distanceTo`
- `newPoints.push`

**Internal Comments:**
```
// This function can be called to update existing arrays or buffers. (x2)
// Accepts same parameters as pointsToStroke, plus the buffers and optional offset. (x2)
// Param vertexOffset: Offset vertices to start writing in the buffers (3 elements/vertex for vertices and normals, and 2 elements/vertex for uvs) (x2)
// Returns number of written vertices / normals / uvs pairs (x2)
// if 'vertices' parameter is undefined no triangles will be generated, but the returned vertices count will still be valid (useful to preallocate the buffers) (x2)
// 'normals' and 'uvs' buffers are optional (x2)
// First ensure there are no duplicated points (x3)
// Get initial left and right stroke points (x5)
// Get next point
// Skip duplicated initial point (x3)
// Normal of previous segment in tempV2_1 (x2)
// Normal of next segment in tempV2_2 (x3)
// If path is straight, don't create join
// Compute inner and outer segment intersections (x2)
// Check that previous and next segments doesn't overlap with the innerPoint of intersection
// The segment triangles are generated here if there was overlapping (x3)
// Segment triangles (x6)
// Join triangles
// The join miter length exceeds the miter limit
// Miter-clip join triangles
// Miter join segment triangles
// Optimized segment + join triangles
// Add extra miter join triangles
// The segment triangles are generated here when two consecutive points are collinear (x3)
// The segment triangles are generated here if it is the ending segment (x3)
// Start line endcap (x3)
// Increment loop variables (x3)
// Ending line endcap (x3)
// Modify path first segment vertices to adjust to the segments inner and outer intersections (x2)
// -- End of algorithm
// -- Functions
// param p1, p2: Points in the circle arc. (x8)
// p1 and p2 are in clockwise direction. (x8)
// Optimized segment + bevel triangles
// Path segments triangles (x6)
// Bevel join triangle (x6)
// Bevel join triangle. The segment triangles are done in the main loop
// param center: End point of the path
// param p1, p2: Left and right cap points
// Modify already existing vertices (x2)
// using tempV2_4 to update 3rd vertex if the uv.y of 3rd vertex is 1 (x5)
// Nothing to do here
// Creates a new array if necessary with duplicated points removed. (x2)
// This does not remove duplicated initial and ending points of a closed path. (x2)
```

<details><summary>Code</summary>

```typescript
static pointsToStrokeWithBuffers( points, style, arcDivisions, minDistance, vertices, normals, uvs, vertexOffset ) {

		// This function can be called to update existing arrays or buffers.
		// Accepts same parameters as pointsToStroke, plus the buffers and optional offset.
		// Param vertexOffset: Offset vertices to start writing in the buffers (3 elements/vertex for vertices and normals, and 2 elements/vertex for uvs)
		// Returns number of written vertices / normals / uvs pairs
		// if 'vertices' parameter is undefined no triangles will be generated, but the returned vertices count will still be valid (useful to preallocate the buffers)
		// 'normals' and 'uvs' buffers are optional

		const tempV2_1 = new Vector2();
		const tempV2_2 = new Vector2();
		const tempV2_3 = new Vector2();
		const tempV2_4 = new Vector2();
		const tempV2_5 = new Vector2();
		const tempV2_6 = new Vector2();
		const tempV2_7 = new Vector2();
		const lastPointL = new Vector2();
		const lastPointR = new Vector2();
		const point0L = new Vector2();
		const point0R = new Vector2();
		const currentPointL = new Vector2();
		const currentPointR = new Vector2();
		const nextPointL = new Vector2();
		const nextPointR = new Vector2();
		const innerPoint = new Vector2();
		const outerPoint = new Vector2();

		arcDivisions = arcDivisions !== undefined ? arcDivisions : 12;
		minDistance = minDistance !== undefined ? minDistance : 0.001;
		vertexOffset = vertexOffset !== undefined ? vertexOffset : 0;

		// First ensure there are no duplicated points
		points = removeDuplicatedPoints( points );

		const numPoints = points.length;

		if ( numPoints < 2 ) return 0;

		const isClosed = points[ 0 ].equals( points[ numPoints - 1 ] );

		let currentPoint;
		let previousPoint = points[ 0 ];
		let nextPoint;

		const strokeWidth2 = style.strokeWidth / 2;

		const deltaU = 1 / ( numPoints - 1 );
		let u0 = 0, u1;

		let innerSideModified;
		let joinIsOnLeftSide;
		let isMiter;
		let initialJoinIsOnLeftSide = false;

		let numVertices = 0;
		let currentCoordinate = vertexOffset * 3;
		let currentCoordinateUV = vertexOffset * 2;

		// Get initial left and right stroke points
		getNormal( points[ 0 ], points[ 1 ], tempV2_1 ).multiplyScalar( strokeWidth2 );
		lastPointL.copy( points[ 0 ] ).sub( tempV2_1 );
		lastPointR.copy( points[ 0 ] ).add( tempV2_1 );
		point0L.copy( lastPointL );
		point0R.copy( lastPointR );

		for ( let iPoint = 1; iPoint < numPoints; iPoint ++ ) {

			currentPoint = points[ iPoint ];

			// Get next point
			if ( iPoint === numPoints - 1 ) {

				if ( isClosed ) {

					// Skip duplicated initial point
					nextPoint = points[ 1 ];

				} else nextPoint = undefined;

			} else {

				nextPoint = points[ iPoint + 1 ];

			}

			// Normal of previous segment in tempV2_1
			const normal1 = tempV2_1;
			getNormal( previousPoint, currentPoint, normal1 );

			tempV2_3.copy( normal1 ).multiplyScalar( strokeWidth2 );
			currentPointL.copy( currentPoint ).sub( tempV2_3 );
			currentPointR.copy( currentPoint ).add( tempV2_3 );

			u1 = u0 + deltaU;

			innerSideModified = false;

			if ( nextPoint !== undefined ) {

				// Normal of next segment in tempV2_2
				getNormal( currentPoint, nextPoint, tempV2_2 );

				tempV2_3.copy( tempV2_2 ).multiplyScalar( strokeWidth2 );
				nextPointL.copy( currentPoint ).sub( tempV2_3 );
				nextPointR.copy( currentPoint ).add( tempV2_3 );

				joinIsOnLeftSide = true;
				tempV2_3.subVectors( nextPoint, previousPoint );
				if ( normal1.dot( tempV2_3 ) < 0 ) {

					joinIsOnLeftSide = false;

				}

				if ( iPoint === 1 ) initialJoinIsOnLeftSide = joinIsOnLeftSide;

				tempV2_3.subVectors( nextPoint, currentPoint );
				tempV2_3.normalize();
				const dot = Math.abs( normal1.dot( tempV2_3 ) );

				// If path is straight, don't create join
				if ( dot > Number.EPSILON ) {

					// Compute inner and outer segment intersections
					const miterSide = strokeWidth2 / dot;
					tempV2_3.multiplyScalar( - miterSide );
					tempV2_4.subVectors( currentPoint, previousPoint );
					tempV2_5.copy( tempV2_4 ).setLength( miterSide ).add( tempV2_3 );
					innerPoint.copy( tempV2_5 ).negate();
					const miterLength2 = tempV2_5.length();
					const segmentLengthPrev = tempV2_4.length();
					tempV2_4.divideScalar( segmentLengthPrev );
					tempV2_6.subVectors( nextPoint, currentPoint );
					const segmentLengthNext = tempV2_6.length();
					tempV2_6.divideScalar( segmentLengthNext );
					// Check that previous and next segments doesn't overlap with the innerPoint of intersection
					if ( tempV2_4.dot( innerPoint ) < segmentLengthPrev && tempV2_6.dot( innerPoint ) < segmentLengthNext ) {

						innerSideModified = true;

					}

					outerPoint.copy( tempV2_5 ).add( currentPoint );
					innerPoint.add( currentPoint );

					isMiter = false;

					if ( innerSideModified ) {

						if ( joinIsOnLeftSide ) {

							nextPointR.copy( innerPoint );
							currentPointR.copy( innerPoint );

						} else {

							nextPointL.copy( innerPoint );
							currentPointL.copy( innerPoint );

						}

					} else {

						// The segment triangles are generated here if there was overlapping

						makeSegmentTriangles();

					}

					switch ( style.strokeLineJoin ) {

						case 'bevel':

							makeSegmentWithBevelJoin( joinIsOnLeftSide, innerSideModified, u1 );

							break;

						case 'round':

							// Segment triangles

							createSegmentTrianglesWithMiddleSection( joinIsOnLeftSide, innerSideModified );

							// Join triangles

							if ( joinIsOnLeftSide ) {

								makeCircularSector( currentPoint, currentPointL, nextPointL, u1, 0 );

							} else {

								makeCircularSector( currentPoint, nextPointR, currentPointR, u1, 1 );

							}

							break;

						case 'miter':
						case 'miter-clip':
						default:

							const miterFraction = ( strokeWidth2 * style.strokeMiterLimit ) / miterLength2;

							if ( miterFraction < 1 ) {

								// The join miter length exceeds the miter limit

								if ( style.strokeLineJoin !== 'miter-clip' ) {

									makeSegmentWithBevelJoin( joinIsOnLeftSide, innerSideModified, u1 );
									break;

								} else {

									// Segment triangles

									createSegmentTrianglesWithMiddleSection( joinIsOnLeftSide, innerSideModified );

									// Miter-clip join triangles

									if ( joinIsOnLeftSide ) {

										tempV2_6.subVectors( outerPoint, currentPointL ).multiplyScalar( miterFraction ).add( currentPointL );
										tempV2_7.subVectors( outerPoint, nextPointL ).multiplyScalar( miterFraction ).add( nextPointL );

										addVertex( currentPointL, u1, 0 );
										addVertex( tempV2_6, u1, 0 );
										addVertex( currentPoint, u1, 0.5 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( tempV2_6, u1, 0 );
										addVertex( tempV2_7, u1, 0 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( tempV2_7, u1, 0 );
										addVertex( nextPointL, u1, 0 );

									} else {

										tempV2_6.subVectors( outerPoint, currentPointR ).multiplyScalar( miterFraction ).add( currentPointR );
										tempV2_7.subVectors( outerPoint, nextPointR ).multiplyScalar( miterFraction ).add( nextPointR );

										addVertex( currentPointR, u1, 1 );
										addVertex( tempV2_6, u1, 1 );
										addVertex( currentPoint, u1, 0.5 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( tempV2_6, u1, 1 );
										addVertex( tempV2_7, u1, 1 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( tempV2_7, u1, 1 );
										addVertex( nextPointR, u1, 1 );

									}

								}

							} else {

								// Miter join segment triangles

								if ( innerSideModified ) {

									// Optimized segment + join triangles

									if ( joinIsOnLeftSide ) {

										addVertex( lastPointR, u0, 1 );
										addVertex( lastPointL, u0, 0 );
										addVertex( outerPoint, u1, 0 );

										addVertex( lastPointR, u0, 1 );
										addVertex( outerPoint, u1, 0 );
										addVertex( innerPoint, u1, 1 );

									} else {

										addVertex( lastPointR, u0, 1 );
										addVertex( lastPointL, u0, 0 );
										addVertex( outerPoint, u1, 1 );

										addVertex( lastPointL, u0, 0 );
										addVertex( innerPoint, u1, 0 );
										addVertex( outerPoint, u1, 1 );

									}


									if ( joinIsOnLeftSide ) {

										nextPointL.copy( outerPoint );

									} else {

										nextPointR.copy( outerPoint );

									}


								} else {

									// Add extra miter join triangles

									if ( joinIsOnLeftSide ) {

										addVertex( currentPointL, u1, 0 );
										addVertex( outerPoint, u1, 0 );
										addVertex( currentPoint, u1, 0.5 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( outerPoint, u1, 0 );
										addVertex( nextPointL, u1, 0 );

									} else {

										addVertex( currentPointR, u1, 1 );
										addVertex( outerPoint, u1, 1 );
										addVertex( currentPoint, u1, 0.5 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( outerPoint, u1, 1 );
										addVertex( nextPointR, u1, 1 );

									}

								}

								isMiter = true;

							}

							break;

					}

				} else {

					// The segment triangles are generated here when two consecutive points are collinear

					makeSegmentTriangles();

				}

			} else {

				// The segment triangles are generated here if it is the ending segment

				makeSegmentTriangles();

			}

			if ( ! isClosed && iPoint === numPoints - 1 ) {

				// Start line endcap
				addCapGeometry( points[ 0 ], point0L, point0R, joinIsOnLeftSide, true, u0 );

			}

			// Increment loop variables

			u0 = u1;

			previousPoint = currentPoint;

			lastPointL.copy( nextPointL );
			lastPointR.copy( nextPointR );

		}

		if ( ! isClosed ) {

			// Ending line endcap
			addCapGeometry( currentPoint, currentPointL, currentPointR, joinIsOnLeftSide, false, u1 );

		} else if ( innerSideModified && vertices ) {

			// Modify path first segment vertices to adjust to the segments inner and outer intersections

			let lastOuter = outerPoint;
			let lastInner = innerPoint;

			if ( initialJoinIsOnLeftSide !== joinIsOnLeftSide ) {

				lastOuter = innerPoint;
				lastInner = outerPoint;

			}

			if ( joinIsOnLeftSide ) {

				if ( isMiter || initialJoinIsOnLeftSide ) {

					lastInner.toArray( vertices, 0 * 3 );
					lastInner.toArray( vertices, 3 * 3 );

					if ( isMiter ) {

						lastOuter.toArray( vertices, 1 * 3 );

					}

				}

			} else {

				if ( isMiter || ! initialJoinIsOnLeftSide ) {

					lastInner.toArray( vertices, 1 * 3 );
					lastInner.toArray( vertices, 3 * 3 );

					if ( isMiter ) {

						lastOuter.toArray( vertices, 0 * 3 );

					}

				}

			}

		}

		return numVertices;

		// -- End of algorithm

		// -- Functions

		function getNormal( p1, p2, result ) {

			result.subVectors( p2, p1 );
			return result.set( - result.y, result.x ).normalize();

		}

		function addVertex( position, u, v ) {

			if ( vertices ) {

				vertices[ currentCoordinate ] = position.x;
				vertices[ currentCoordinate + 1 ] = position.y;
				vertices[ currentCoordinate + 2 ] = 0;

				if ( normals ) {

					normals[ currentCoordinate ] = 0;
					normals[ currentCoordinate + 1 ] = 0;
					normals[ currentCoordinate + 2 ] = 1;

				}

				currentCoordinate += 3;

				if ( uvs ) {

					uvs[ currentCoordinateUV ] = u;
					uvs[ currentCoordinateUV + 1 ] = v;

					currentCoordinateUV += 2;

				}

			}

			numVertices += 3;

		}

		function makeCircularSector( center, p1, p2, u, v ) {

			// param p1, p2: Points in the circle arc.
			// p1 and p2 are in clockwise direction.

			tempV2_1.copy( p1 ).sub( center ).normalize();
			tempV2_2.copy( p2 ).sub( center ).normalize();

			let angle = Math.PI;
			const dot = tempV2_1.dot( tempV2_2 );
			if ( Math.abs( dot ) < 1 ) angle = Math.abs( Math.acos( dot ) );

			angle /= arcDivisions;

			tempV2_3.copy( p1 );

			for ( let i = 0, il = arcDivisions - 1; i < il; i ++ ) {

				tempV2_4.copy( tempV2_3 ).rotateAround( center, angle );

				addVertex( tempV2_3, u, v );
				addVertex( tempV2_4, u, v );
				addVertex( center, u, 0.5 );

				tempV2_3.copy( tempV2_4 );

			}

			addVertex( tempV2_4, u, v );
			addVertex( p2, u, v );
			addVertex( center, u, 0.5 );

		}

		function makeSegmentTriangles() {

			addVertex( lastPointR, u0, 1 );
			addVertex( lastPointL, u0, 0 );
			addVertex( currentPointL, u1, 0 );

			addVertex( lastPointR, u0, 1 );
			addVertex( currentPointL, u1, 0 );
			addVertex( currentPointR, u1, 1 );

		}

		function makeSegmentWithBevelJoin( joinIsOnLeftSide, innerSideModified, u ) {

			if ( innerSideModified ) {

				// Optimized segment + bevel triangles

				if ( joinIsOnLeftSide ) {

					// Path segments triangles

					addVertex( lastPointR, u0, 1 );
					addVertex( lastPointL, u0, 0 );
					addVertex( currentPointL, u1, 0 );

					addVertex( lastPointR, u0, 1 );
					addVertex( currentPointL, u1, 0 );
					addVertex( innerPoint, u1, 1 );

					// Bevel join triangle

					addVertex( currentPointL, u, 0 );
					addVertex( nextPointL, u, 0 );
					addVertex( innerPoint, u, 0.5 );

				} else {

					// Path segments triangles

					addVertex( lastPointR, u0, 1 );
					addVertex( lastPointL, u0, 0 );
					addVertex( currentPointR, u1, 1 );

					addVertex( lastPointL, u0, 0 );
					addVertex( innerPoint, u1, 0 );
					addVertex( currentPointR, u1, 1 );

					// Bevel join triangle

					addVertex( currentPointR, u, 1 );
					addVertex( innerPoint, u, 0 );
					addVertex( nextPointR, u, 1 );

				}

			} else {

				// Bevel join triangle. The segment triangles are done in the main loop

				if ( joinIsOnLeftSide ) {

					addVertex( currentPointL, u, 0 );
					addVertex( nextPointL, u, 0 );
					addVertex( currentPoint, u, 0.5 );

				} else {

					addVertex( currentPointR, u, 1 );
					addVertex( nextPointR, u, 0 );
					addVertex( currentPoint, u, 0.5 );

				}

			}

		}

		function createSegmentTrianglesWithMiddleSection( joinIsOnLeftSide, innerSideModified ) {

			if ( innerSideModified ) {

				if ( joinIsOnLeftSide ) {

					addVertex( lastPointR, u0, 1 );
					addVertex( lastPointL, u0, 0 );
					addVertex( currentPointL, u1, 0 );

					addVertex( lastPointR, u0, 1 );
					addVertex( currentPointL, u1, 0 );
					addVertex( innerPoint, u1, 1 );

					addVertex( currentPointL, u0, 0 );
					addVertex( currentPoint, u1, 0.5 );
					addVertex( innerPoint, u1, 1 );

					addVertex( currentPoint, u1, 0.5 );
					addVertex( nextPointL, u0, 0 );
					addVertex( innerPoint, u1, 1 );

				} else {

					addVertex( lastPointR, u0, 1 );
					addVertex( lastPointL, u0, 0 );
					addVertex( currentPointR, u1, 1 );

					addVertex( lastPointL, u0, 0 );
					addVertex( innerPoint, u1, 0 );
					addVertex( currentPointR, u1, 1 );

					addVertex( currentPointR, u0, 1 );
					addVertex( innerPoint, u1, 0 );
					addVertex( currentPoint, u1, 0.5 );

					addVertex( currentPoint, u1, 0.5 );
					addVertex( innerPoint, u1, 0 );
					addVertex( nextPointR, u0, 1 );

				}

			}

		}

		function addCapGeometry( center, p1, p2, joinIsOnLeftSide, start, u ) {

			// param center: End point of the path
			// param p1, p2: Left and right cap points

			switch ( style.strokeLineCap ) {

				case 'round':

					if ( start ) {

						makeCircularSector( center, p2, p1, u, 0.5 );

					} else {

						makeCircularSector( center, p1, p2, u, 0.5 );

					}

					break;

				case 'square':

					if ( start ) {

						tempV2_1.subVectors( p1, center );
						tempV2_2.set( tempV2_1.y, - tempV2_1.x );

						tempV2_3.addVectors( tempV2_1, tempV2_2 ).add( center );
						tempV2_4.subVectors( tempV2_2, tempV2_1 ).add( center );

						// Modify already existing vertices
						if ( joinIsOnLeftSide ) {

							tempV2_3.toArray( vertices, 1 * 3 );
							tempV2_4.toArray( vertices, 0 * 3 );
							tempV2_4.toArray( vertices, 3 * 3 );

						} else {

							tempV2_3.toArray( vertices, 1 * 3 );
							// using tempV2_4 to update 3rd vertex if the uv.y of 3rd vertex is 1
							uvs[ 3 * 2 + 1 ] === 1 ? tempV2_4.toArray( vertices, 3 * 3 ) : tempV2_3.toArray( vertices, 3 * 3 );
							tempV2_4.toArray( vertices, 0 * 3 );

						}

					} else {

						tempV2_1.subVectors( p2, center );
						tempV2_2.set( tempV2_1.y, - tempV2_1.x );

						tempV2_3.addVectors( tempV2_1, tempV2_2 ).add( center );
						tempV2_4.subVectors( tempV2_2, tempV2_1 ).add( center );

						const vl = vertices.length;

						// Modify already existing vertices
						if ( joinIsOnLeftSide ) {

							tempV2_3.toArray( vertices, vl - 1 * 3 );
							tempV2_4.toArray( vertices, vl - 2 * 3 );
							tempV2_4.toArray( vertices, vl - 4 * 3 );

						} else {

							tempV2_4.toArray( vertices, vl - 2 * 3 );
							tempV2_3.toArray( vertices, vl - 1 * 3 );
							tempV2_4.toArray( vertices, vl - 4 * 3 );

						}

					}

					break;

				case 'butt':
				default:

					// Nothing to do here
					break;

			}

		}

		function removeDuplicatedPoints( points ) {

			// Creates a new array if necessary with duplicated points removed.
			// This does not remove duplicated initial and ending points of a closed path.

			let dupPoints = false;
			for ( let i = 1, n = points.length - 1; i < n; i ++ ) {

				if ( points[ i ].distanceTo( points[ i + 1 ] ) < minDistance ) {

					dupPoints = true;
					break;

				}

			}

			if ( ! dupPoints ) return points;

			const newPoints = [];
			newPoints.push( points[ 0 ] );

			for ( let i = 1, n = points.length - 1; i < n; i ++ ) {

				if ( points[ i ].distanceTo( points[ i + 1 ] ) >= minDistance ) {

					newPoints.push( points[ i ] );

				}

			}

			newPoints.push( points[ points.length - 1 ] );

			return newPoints;

		}

	}
```
</details>

### `parseNode(node: any, style: any): void`

**Parameters:**

- **`node`** `any`
- **`style`** `any`

**Returns:** `void`

**Calls:**

- `getNodeTransform`
- `parseStyle`
- `parseCSSStylesheet`
- `node.hasAttribute`
- `parsePathNode`
- `parseRectNode`
- `parsePolygonNode`
- `parsePolylineNode`
- `parseCircleNode`
- `parseEllipseNode`
- `parseLineNode`
- `node.getAttributeNS`
- `href.substring`
- `node.viewportElement.getElementById`
- `parseNode`
- `console.warn`
- `path.color.setStyle`
- `transformPath`
- `paths.push`
- `transformStack.pop`
- `currentTransform.copy`
- `currentTransform.identity`

**Internal Comments:**
```
// Ignore everything in defs except CSS style definitions
// and nested defs, because it is OK by the standard to have
// <style/> there.
```

<details><summary>Code</summary>

```typescript
function parseNode( node, style ) {

			if ( node.nodeType !== 1 ) return;

			const transform = getNodeTransform( node );

			let isDefsNode = false;

			let path = null;

			switch ( node.nodeName ) {

				case 'svg':
					style = parseStyle( node, style );
					break;

				case 'style':
					parseCSSStylesheet( node );
					break;

				case 'g':
					style = parseStyle( node, style );
					break;

				case 'path':
					style = parseStyle( node, style );
					if ( node.hasAttribute( 'd' ) ) path = parsePathNode( node );
					break;

				case 'rect':
					style = parseStyle( node, style );
					path = parseRectNode( node );
					break;

				case 'polygon':
					style = parseStyle( node, style );
					path = parsePolygonNode( node );
					break;

				case 'polyline':
					style = parseStyle( node, style );
					path = parsePolylineNode( node );
					break;

				case 'circle':
					style = parseStyle( node, style );
					path = parseCircleNode( node );
					break;

				case 'ellipse':
					style = parseStyle( node, style );
					path = parseEllipseNode( node );
					break;

				case 'line':
					style = parseStyle( node, style );
					path = parseLineNode( node );
					break;

				case 'defs':
					isDefsNode = true;
					break;

				case 'use':
					style = parseStyle( node, style );

					const href = node.getAttributeNS( 'http://www.w3.org/1999/xlink', 'href' ) || '';
					const usedNodeId = href.substring( 1 );
					const usedNode = node.viewportElement.getElementById( usedNodeId );
					if ( usedNode ) {

						parseNode( usedNode, style );

					} else {

						console.warn( 'SVGLoader: \'use node\' references non-existent node id: ' + usedNodeId );

					}

					break;

				default:
					// console.log( node );

			}

			if ( path ) {

				if ( style.fill !== undefined && style.fill !== 'none' ) {

					path.color.setStyle( style.fill, COLOR_SPACE_SVG );

				}

				transformPath( path, currentTransform );

				paths.push( path );

				path.userData = { node: node, style: style };

			}

			const childNodes = node.childNodes;

			for ( let i = 0; i < childNodes.length; i ++ ) {

				const node = childNodes[ i ];

				if ( isDefsNode && node.nodeName !== 'style' && node.nodeName !== 'defs' ) {

					// Ignore everything in defs except CSS style definitions
					// and nested defs, because it is OK by the standard to have
					// <style/> there.
					continue;

				}

				parseNode( node, style );

			}


			if ( transform ) {

				transformStack.pop();

				if ( transformStack.length > 0 ) {

					currentTransform.copy( transformStack[ transformStack.length - 1 ] );

				} else {

					currentTransform.identity();

				}

			}

		}
```
</details>

### `parsePathNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `node.getAttribute`
- `d.match`
- `command.charAt`
- `command.slice( 1 ).trim`
- `parseFloats`
- `path.moveTo`
- `path.lineTo`
- `firstPoint.copy`
- `path.bezierCurveTo`
- `getReflection`
- `path.quadraticCurveTo`
- `point.clone`
- `parseArcCommand`
- `point.copy`
- `path.currentPath.currentPoint.copy`
- `console.warn`

**Internal Comments:**
```
// console.log( d ); (x2)
// skip command if start point == end point
// skip command if no displacement
// Reset point to beginning of Path (x4)
// console.log( type, parseFloats( data ), parseFloats( data ).length  ) (x3)
```

<details><summary>Code</summary>

```typescript
function parsePathNode( node ) {

			const path = new ShapePath();

			const point = new Vector2();
			const control = new Vector2();

			const firstPoint = new Vector2();
			let isFirstPoint = true;
			let doSetFirstPoint = false;

			const d = node.getAttribute( 'd' );

			if ( d === '' || d === 'none' ) return null;

			// console.log( d );

			const commands = d.match( /[a-df-z][^a-df-z]*/ig );

			for ( let i = 0, l = commands.length; i < l; i ++ ) {

				const command = commands[ i ];

				const type = command.charAt( 0 );
				const data = command.slice( 1 ).trim();

				if ( isFirstPoint === true ) {

					doSetFirstPoint = true;
					isFirstPoint = false;

				}

				let numbers;

				switch ( type ) {

					case 'M':
						numbers = parseFloats( data );
						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							point.x = numbers[ j + 0 ];
							point.y = numbers[ j + 1 ];
							control.x = point.x;
							control.y = point.y;

							if ( j === 0 ) {

								path.moveTo( point.x, point.y );

							} else {

								path.lineTo( point.x, point.y );

							}

							if ( j === 0 ) firstPoint.copy( point );

						}

						break;

					case 'H':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j ++ ) {

							point.x = numbers[ j ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'V':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j ++ ) {

							point.y = numbers[ j ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'L':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							point.x = numbers[ j + 0 ];
							point.y = numbers[ j + 1 ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'C':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 6 ) {

							path.bezierCurveTo(
								numbers[ j + 0 ],
								numbers[ j + 1 ],
								numbers[ j + 2 ],
								numbers[ j + 3 ],
								numbers[ j + 4 ],
								numbers[ j + 5 ]
							);
							control.x = numbers[ j + 2 ];
							control.y = numbers[ j + 3 ];
							point.x = numbers[ j + 4 ];
							point.y = numbers[ j + 5 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'S':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 4 ) {

							path.bezierCurveTo(
								getReflection( point.x, control.x ),
								getReflection( point.y, control.y ),
								numbers[ j + 0 ],
								numbers[ j + 1 ],
								numbers[ j + 2 ],
								numbers[ j + 3 ]
							);
							control.x = numbers[ j + 0 ];
							control.y = numbers[ j + 1 ];
							point.x = numbers[ j + 2 ];
							point.y = numbers[ j + 3 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'Q':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 4 ) {

							path.quadraticCurveTo(
								numbers[ j + 0 ],
								numbers[ j + 1 ],
								numbers[ j + 2 ],
								numbers[ j + 3 ]
							);
							control.x = numbers[ j + 0 ];
							control.y = numbers[ j + 1 ];
							point.x = numbers[ j + 2 ];
							point.y = numbers[ j + 3 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'T':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							const rx = getReflection( point.x, control.x );
							const ry = getReflection( point.y, control.y );
							path.quadraticCurveTo(
								rx,
								ry,
								numbers[ j + 0 ],
								numbers[ j + 1 ]
							);
							control.x = rx;
							control.y = ry;
							point.x = numbers[ j + 0 ];
							point.y = numbers[ j + 1 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'A':
						numbers = parseFloats( data, [ 3, 4 ], 7 );

						for ( let j = 0, jl = numbers.length; j < jl; j += 7 ) {

							// skip command if start point == end point
							if ( numbers[ j + 5 ] == point.x && numbers[ j + 6 ] == point.y ) continue;

							const start = point.clone();
							point.x = numbers[ j + 5 ];
							point.y = numbers[ j + 6 ];
							control.x = point.x;
							control.y = point.y;
							parseArcCommand(
								path, numbers[ j ], numbers[ j + 1 ], numbers[ j + 2 ], numbers[ j + 3 ], numbers[ j + 4 ], start, point
							);

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'm':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							point.x += numbers[ j + 0 ];
							point.y += numbers[ j + 1 ];
							control.x = point.x;
							control.y = point.y;

							if ( j === 0 ) {

								path.moveTo( point.x, point.y );

							} else {

								path.lineTo( point.x, point.y );

							}

							if ( j === 0 ) firstPoint.copy( point );

						}

						break;

					case 'h':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j ++ ) {

							point.x += numbers[ j ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'v':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j ++ ) {

							point.y += numbers[ j ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'l':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							point.x += numbers[ j + 0 ];
							point.y += numbers[ j + 1 ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'c':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 6 ) {

							path.bezierCurveTo(
								point.x + numbers[ j + 0 ],
								point.y + numbers[ j + 1 ],
								point.x + numbers[ j + 2 ],
								point.y + numbers[ j + 3 ],
								point.x + numbers[ j + 4 ],
								point.y + numbers[ j + 5 ]
							);
							control.x = point.x + numbers[ j + 2 ];
							control.y = point.y + numbers[ j + 3 ];
							point.x += numbers[ j + 4 ];
							point.y += numbers[ j + 5 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 's':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 4 ) {

							path.bezierCurveTo(
								getReflection( point.x, control.x ),
								getReflection( point.y, control.y ),
								point.x + numbers[ j + 0 ],
								point.y + numbers[ j + 1 ],
								point.x + numbers[ j + 2 ],
								point.y + numbers[ j + 3 ]
							);
							control.x = point.x + numbers[ j + 0 ];
							control.y = point.y + numbers[ j + 1 ];
							point.x += numbers[ j + 2 ];
							point.y += numbers[ j + 3 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'q':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 4 ) {

							path.quadraticCurveTo(
								point.x + numbers[ j + 0 ],
								point.y + numbers[ j + 1 ],
								point.x + numbers[ j + 2 ],
								point.y + numbers[ j + 3 ]
							);
							control.x = point.x + numbers[ j + 0 ];
							control.y = point.y + numbers[ j + 1 ];
							point.x += numbers[ j + 2 ];
							point.y += numbers[ j + 3 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 't':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							const rx = getReflection( point.x, control.x );
							const ry = getReflection( point.y, control.y );
							path.quadraticCurveTo(
								rx,
								ry,
								point.x + numbers[ j + 0 ],
								point.y + numbers[ j + 1 ]
							);
							control.x = rx;
							control.y = ry;
							point.x = point.x + numbers[ j + 0 ];
							point.y = point.y + numbers[ j + 1 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'a':
						numbers = parseFloats( data, [ 3, 4 ], 7 );

						for ( let j = 0, jl = numbers.length; j < jl; j += 7 ) {

							// skip command if no displacement
							if ( numbers[ j + 5 ] == 0 && numbers[ j + 6 ] == 0 ) continue;

							const start = point.clone();
							point.x += numbers[ j + 5 ];
							point.y += numbers[ j + 6 ];
							control.x = point.x;
							control.y = point.y;
							parseArcCommand(
								path, numbers[ j ], numbers[ j + 1 ], numbers[ j + 2 ], numbers[ j + 3 ], numbers[ j + 4 ], start, point
							);

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'Z':
					case 'z':
						path.currentPath.autoClose = true;

						if ( path.currentPath.curves.length > 0 ) {

							// Reset point to beginning of Path
							point.copy( firstPoint );
							path.currentPath.currentPoint.copy( point );
							isFirstPoint = true;

						}

						break;

					default:
						console.warn( command );

				}

				// console.log( type, parseFloats( data ), parseFloats( data ).length  )

				doSetFirstPoint = false;

			}

			return path;

		}
```
</details>

### `parseCSSStylesheet(node: any): void`

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `stylesheet.selectorText
					.split( /,/gm )
					.filter( Boolean )
					.map`
- `i.trim`
- `Object.fromEntries`
- `Object.entries( stylesheet.style ).filter`
- `Object.assign`

**Internal Comments:**
```
// Remove empty rules (x2)
```

<details><summary>Code</summary>

```typescript
function parseCSSStylesheet( node ) {

			if ( ! node.sheet || ! node.sheet.cssRules || ! node.sheet.cssRules.length ) return;

			for ( let i = 0; i < node.sheet.cssRules.length; i ++ ) {

				const stylesheet = node.sheet.cssRules[ i ];

				if ( stylesheet.type !== 1 ) continue;

				const selectorList = stylesheet.selectorText
					.split( /,/gm )
					.filter( Boolean )
					.map( i => i.trim() );

				for ( let j = 0; j < selectorList.length; j ++ ) {

					// Remove empty rules
					const definitions = Object.fromEntries(
						Object.entries( stylesheet.style ).filter( ( [ , v ] ) => v !== '' )
					);

					stylesheets[ selectorList[ j ] ] = Object.assign(
						stylesheets[ selectorList[ j ] ] || {},
						definitions
					);

				}

			}

		}
```
</details>

### `parseArcCommand(path: any, rx: any, ry: any, x_axis_rotation: any, large_arc_flag: any, sweep_flag: any, start: any, end: any): void`

**JSDoc:**
```typescript
/**
		 * https://www.w3.org/TR/SVG/implnote.html#ArcImplementationNotes
		 * https://mortoray.com/2017/02/16/rendering-an-svg-elliptical-arc-as-bezier-curves/ Appendix: Endpoint to center arc conversion
		 * From
		 * rx ry x-axis-rotation large-arc-flag sweep-flag x y
		 * To
		 * aX, aY, xRadius, yRadius, aStartAngle, aEndAngle, aClockwise, aRotation
		 */
```

**Parameters:**

- **`path`** `any`
- **`rx`** `any`
- **`ry`** `any`
- **`x_axis_rotation`** `any`
- **`large_arc_flag`** `any`
- **`sweep_flag`** `any`
- **`start`** `any`
- **`end`** `any`

**Returns:** `void`

**Calls:**

- `path.lineTo`
- `Math.abs`
- `Math.cos`
- `Math.sin`
- `Math.sqrt`
- `Math.max`
- `svgAngle`
- `path.currentPath.absellipse`

**Internal Comments:**
```
// draw a line if either of the radii == 0 (x4)
// Ensure radii are positive (x3)
// Compute (x1', y1') (x2)
// Compute (cx', cy') (x2)
// Ensure radii are large enough (x2)
// scale up rx,ry equally so cr == 1 (x2)
// Step 3: Compute (cx, cy) from (cx', cy') (x2)
// Step 4: Compute θ1 and Δθ (x2)
```

<details><summary>Code</summary>

```typescript
function parseArcCommand( path, rx, ry, x_axis_rotation, large_arc_flag, sweep_flag, start, end ) {

			if ( rx == 0 || ry == 0 ) {

				// draw a line if either of the radii == 0
				path.lineTo( end.x, end.y );
				return;

			}

			x_axis_rotation = x_axis_rotation * Math.PI / 180;

			// Ensure radii are positive
			rx = Math.abs( rx );
			ry = Math.abs( ry );

			// Compute (x1', y1')
			const dx2 = ( start.x - end.x ) / 2.0;
			const dy2 = ( start.y - end.y ) / 2.0;
			const x1p = Math.cos( x_axis_rotation ) * dx2 + Math.sin( x_axis_rotation ) * dy2;
			const y1p = - Math.sin( x_axis_rotation ) * dx2 + Math.cos( x_axis_rotation ) * dy2;

			// Compute (cx', cy')
			let rxs = rx * rx;
			let rys = ry * ry;
			const x1ps = x1p * x1p;
			const y1ps = y1p * y1p;

			// Ensure radii are large enough
			const cr = x1ps / rxs + y1ps / rys;

			if ( cr > 1 ) {

				// scale up rx,ry equally so cr == 1
				const s = Math.sqrt( cr );
				rx = s * rx;
				ry = s * ry;
				rxs = rx * rx;
				rys = ry * ry;

			}

			const dq = ( rxs * y1ps + rys * x1ps );
			const pq = ( rxs * rys - dq ) / dq;
			let q = Math.sqrt( Math.max( 0, pq ) );
			if ( large_arc_flag === sweep_flag ) q = - q;
			const cxp = q * rx * y1p / ry;
			const cyp = - q * ry * x1p / rx;

			// Step 3: Compute (cx, cy) from (cx', cy')
			const cx = Math.cos( x_axis_rotation ) * cxp - Math.sin( x_axis_rotation ) * cyp + ( start.x + end.x ) / 2;
			const cy = Math.sin( x_axis_rotation ) * cxp + Math.cos( x_axis_rotation ) * cyp + ( start.y + end.y ) / 2;

			// Step 4: Compute θ1 and Δθ
			const theta = svgAngle( 1, 0, ( x1p - cxp ) / rx, ( y1p - cyp ) / ry );
			const delta = svgAngle( ( x1p - cxp ) / rx, ( y1p - cyp ) / ry, ( - x1p - cxp ) / rx, ( - y1p - cyp ) / ry ) % ( Math.PI * 2 );

			path.currentPath.absellipse( cx, cy, rx, ry, theta, theta + delta, sweep_flag === 0, x_axis_rotation );

		}
```
</details>

### `svgAngle(ux: any, uy: any, vx: any, vy: any): number`

**Parameters:**

- **`ux`** `any`
- **`uy`** `any`
- **`vx`** `any`
- **`vy`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`
- `Math.acos`
- `Math.max`
- `Math.min`

<details><summary>Code</summary>

```typescript
function svgAngle( ux, uy, vx, vy ) {

			const dot = ux * vx + uy * vy;
			const len = Math.sqrt( ux * ux + uy * uy ) * Math.sqrt( vx * vx + vy * vy );
			let ang = Math.acos( Math.max( - 1, Math.min( 1, dot / len ) ) ); // floating point precision, slightly over values appear
			if ( ( ux * vy - uy * vx ) < 0 ) ang = - ang;
			return ang;

		}
```
</details>

### `parseRectNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `parseFloatWithUnits`
- `node.getAttribute`
- `path.moveTo`
- `path.lineTo`
- `path.bezierCurveTo`

**Internal Comments:**
```
// Ellipse arc to Bezier approximation Coefficient (Inversed). See: (x2)
// https://spencermortensen.com/articles/bezier-circle/ (x2)
// top left (x4)
// top right (x4)
// bottom right (x4)
// bottom left (x4)
// back to top left (x4)
```

<details><summary>Code</summary>

```typescript
function parseRectNode( node ) {

			const x = parseFloatWithUnits( node.getAttribute( 'x' ) || 0 );
			const y = parseFloatWithUnits( node.getAttribute( 'y' ) || 0 );
			const rx = parseFloatWithUnits( node.getAttribute( 'rx' ) || node.getAttribute( 'ry' ) || 0 );
			const ry = parseFloatWithUnits( node.getAttribute( 'ry' ) || node.getAttribute( 'rx' ) || 0 );
			const w = parseFloatWithUnits( node.getAttribute( 'width' ) );
			const h = parseFloatWithUnits( node.getAttribute( 'height' ) );

			// Ellipse arc to Bezier approximation Coefficient (Inversed). See:
			// https://spencermortensen.com/articles/bezier-circle/
			const bci = 1 - 0.551915024494;

			const path = new ShapePath();

			// top left
			path.moveTo( x + rx, y );

			// top right
			path.lineTo( x + w - rx, y );
			if ( rx !== 0 || ry !== 0 ) {

				path.bezierCurveTo(
					x + w - rx * bci,
					y,
					x + w,
					y + ry * bci,
					x + w,
					y + ry
				);

			}

			// bottom right
			path.lineTo( x + w, y + h - ry );
			if ( rx !== 0 || ry !== 0 ) {

				path.bezierCurveTo(
					x + w,
					y + h - ry * bci,
					x + w - rx * bci,
					y + h,
					x + w - rx,
					y + h
				);

			}

			// bottom left
			path.lineTo( x + rx, y + h );
			if ( rx !== 0 || ry !== 0 ) {

				path.bezierCurveTo(
					x + rx * bci,
					y + h,
					x,
					y + h - ry * bci,
					x,
					y + h - ry
				);

			}

			// back to top left
			path.lineTo( x, y + ry );
			if ( rx !== 0 || ry !== 0 ) {

				path.bezierCurveTo( x, y + ry * bci, x + rx * bci, y, x + rx, y );

			}

			return path;

		}
```
</details>

### `parsePolygonNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `parseFloatWithUnits`
- `path.moveTo`
- `path.lineTo`
- `node.getAttribute( 'points' ).replace`

<details><summary>Code</summary>

```typescript
function parsePolygonNode( node ) {

			function iterator( match, a, b ) {

				const x = parseFloatWithUnits( a );
				const y = parseFloatWithUnits( b );

				if ( index === 0 ) {

					path.moveTo( x, y );

				} else {

					path.lineTo( x, y );

				}

				index ++;

			}

			const regex = /([+-]?\d*\.?\d+(?:e[+-]?\d+)?)(?:,|\s)([+-]?\d*\.?\d+(?:e[+-]?\d+)?)/g;

			const path = new ShapePath();

			let index = 0;

			node.getAttribute( 'points' ).replace( regex, iterator );

			path.currentPath.autoClose = true;

			return path;

		}
```
</details>

### `iterator(match: any, a: any, b: any): void`

**Parameters:**

- **`match`** `any`
- **`a`** `any`
- **`b`** `any`

**Returns:** `void`

**Calls:**

- `parseFloatWithUnits`
- `path.moveTo`
- `path.lineTo`

<details><summary>Code</summary>

```typescript
function iterator( match, a, b ) {

				const x = parseFloatWithUnits( a );
				const y = parseFloatWithUnits( b );

				if ( index === 0 ) {

					path.moveTo( x, y );

				} else {

					path.lineTo( x, y );

				}

				index ++;

			}
```
</details>

### `parsePolylineNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `parseFloatWithUnits`
- `path.moveTo`
- `path.lineTo`
- `node.getAttribute( 'points' ).replace`

<details><summary>Code</summary>

```typescript
function parsePolylineNode( node ) {

			function iterator( match, a, b ) {

				const x = parseFloatWithUnits( a );
				const y = parseFloatWithUnits( b );

				if ( index === 0 ) {

					path.moveTo( x, y );

				} else {

					path.lineTo( x, y );

				}

				index ++;

			}

			const regex = /([+-]?\d*\.?\d+(?:e[+-]?\d+)?)(?:,|\s)([+-]?\d*\.?\d+(?:e[+-]?\d+)?)/g;

			const path = new ShapePath();

			let index = 0;

			node.getAttribute( 'points' ).replace( regex, iterator );

			path.currentPath.autoClose = false;

			return path;

		}
```
</details>

### `iterator(match: any, a: any, b: any): void`

**Parameters:**

- **`match`** `any`
- **`a`** `any`
- **`b`** `any`

**Returns:** `void`

**Calls:**

- `parseFloatWithUnits`
- `path.moveTo`
- `path.lineTo`

<details><summary>Code</summary>

```typescript
function iterator( match, a, b ) {

				const x = parseFloatWithUnits( a );
				const y = parseFloatWithUnits( b );

				if ( index === 0 ) {

					path.moveTo( x, y );

				} else {

					path.lineTo( x, y );

				}

				index ++;

			}
```
</details>

### `parseCircleNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `parseFloatWithUnits`
- `node.getAttribute`
- `subpath.absarc`
- `path.subPaths.push`

<details><summary>Code</summary>

```typescript
function parseCircleNode( node ) {

			const x = parseFloatWithUnits( node.getAttribute( 'cx' ) || 0 );
			const y = parseFloatWithUnits( node.getAttribute( 'cy' ) || 0 );
			const r = parseFloatWithUnits( node.getAttribute( 'r' ) || 0 );

			const subpath = new Path();
			subpath.absarc( x, y, r, 0, Math.PI * 2 );

			const path = new ShapePath();
			path.subPaths.push( subpath );

			return path;

		}
```
</details>

### `parseEllipseNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `parseFloatWithUnits`
- `node.getAttribute`
- `subpath.absellipse`
- `path.subPaths.push`

<details><summary>Code</summary>

```typescript
function parseEllipseNode( node ) {

			const x = parseFloatWithUnits( node.getAttribute( 'cx' ) || 0 );
			const y = parseFloatWithUnits( node.getAttribute( 'cy' ) || 0 );
			const rx = parseFloatWithUnits( node.getAttribute( 'rx' ) || 0 );
			const ry = parseFloatWithUnits( node.getAttribute( 'ry' ) || 0 );

			const subpath = new Path();
			subpath.absellipse( x, y, rx, ry, 0, Math.PI * 2 );

			const path = new ShapePath();
			path.subPaths.push( subpath );

			return path;

		}
```
</details>

### `parseLineNode(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `parseFloatWithUnits`
- `node.getAttribute`
- `path.moveTo`
- `path.lineTo`

<details><summary>Code</summary>

```typescript
function parseLineNode( node ) {

			const x1 = parseFloatWithUnits( node.getAttribute( 'x1' ) || 0 );
			const y1 = parseFloatWithUnits( node.getAttribute( 'y1' ) || 0 );
			const x2 = parseFloatWithUnits( node.getAttribute( 'x2' ) || 0 );
			const y2 = parseFloatWithUnits( node.getAttribute( 'y2' ) || 0 );

			const path = new ShapePath();
			path.moveTo( x1, y1 );
			path.lineTo( x2, y2 );
			path.currentPath.autoClose = false;

			return path;

		}
```
</details>

### `parseStyle(node: any, style: any): any`

**Parameters:**

- **`node`** `any`
- **`style`** `any`

**Returns:** `any`

**Calls:**

- `Object.assign`
- `node.hasAttribute`
- `node.getAttribute( 'class' )
					.split( /\s/ )
					.filter( Boolean )
					.map`
- `i.trim`
- `node.getAttribute`
- `v.startsWith`
- `console.warn`
- `adjustFunction`
- `Math.max`
- `Math.min`
- `parseFloatWithUnits`
- `addStyle`

<details><summary>Code</summary>

```typescript
function parseStyle( node, style ) {

			style = Object.assign( {}, style ); // clone style

			let stylesheetStyles = {};

			if ( node.hasAttribute( 'class' ) ) {

				const classSelectors = node.getAttribute( 'class' )
					.split( /\s/ )
					.filter( Boolean )
					.map( i => i.trim() );

				for ( let i = 0; i < classSelectors.length; i ++ ) {

					stylesheetStyles = Object.assign( stylesheetStyles, stylesheets[ '.' + classSelectors[ i ] ] );

				}

			}

			if ( node.hasAttribute( 'id' ) ) {

				stylesheetStyles = Object.assign( stylesheetStyles, stylesheets[ '#' + node.getAttribute( 'id' ) ] );

			}

			function addStyle( svgName, jsName, adjustFunction ) {

				if ( adjustFunction === undefined ) adjustFunction = function copy( v ) {

					if ( v.startsWith( 'url' ) ) console.warn( 'SVGLoader: url access in attributes is not implemented.' );

					return v;

				};

				if ( node.hasAttribute( svgName ) ) style[ jsName ] = adjustFunction( node.getAttribute( svgName ) );
				if ( stylesheetStyles[ svgName ] ) style[ jsName ] = adjustFunction( stylesheetStyles[ svgName ] );
				if ( node.style && node.style[ svgName ] !== '' ) style[ jsName ] = adjustFunction( node.style[ svgName ] );

			}

			function clamp( v ) {

				return Math.max( 0, Math.min( 1, parseFloatWithUnits( v ) ) );

			}

			function positive( v ) {

				return Math.max( 0, parseFloatWithUnits( v ) );

			}

			addStyle( 'fill', 'fill' );
			addStyle( 'fill-opacity', 'fillOpacity', clamp );
			addStyle( 'fill-rule', 'fillRule' );
			addStyle( 'opacity', 'opacity', clamp );
			addStyle( 'stroke', 'stroke' );
			addStyle( 'stroke-opacity', 'strokeOpacity', clamp );
			addStyle( 'stroke-width', 'strokeWidth', positive );
			addStyle( 'stroke-linejoin', 'strokeLineJoin' );
			addStyle( 'stroke-linecap', 'strokeLineCap' );
			addStyle( 'stroke-miterlimit', 'strokeMiterLimit', positive );
			addStyle( 'visibility', 'visibility' );

			return style;

		}
```
</details>

### `addStyle(svgName: any, jsName: any, adjustFunction: any): void`

**Parameters:**

- **`svgName`** `any`
- **`jsName`** `any`
- **`adjustFunction`** `any`

**Returns:** `void`

**Calls:**

- `v.startsWith`
- `console.warn`
- `node.hasAttribute`
- `adjustFunction`
- `node.getAttribute`

<details><summary>Code</summary>

```typescript
function addStyle( svgName, jsName, adjustFunction ) {

				if ( adjustFunction === undefined ) adjustFunction = function copy( v ) {

					if ( v.startsWith( 'url' ) ) console.warn( 'SVGLoader: url access in attributes is not implemented.' );

					return v;

				};

				if ( node.hasAttribute( svgName ) ) style[ jsName ] = adjustFunction( node.getAttribute( svgName ) );
				if ( stylesheetStyles[ svgName ] ) style[ jsName ] = adjustFunction( stylesheetStyles[ svgName ] );
				if ( node.style && node.style[ svgName ] !== '' ) style[ jsName ] = adjustFunction( node.style[ svgName ] );

			}
```
</details>

### `clamp(v: any): number`

**Parameters:**

- **`v`** `any`

**Returns:** `number`

**Calls:**

- `Math.max`
- `Math.min`
- `parseFloatWithUnits`

<details><summary>Code</summary>

```typescript
function clamp( v ) {

				return Math.max( 0, Math.min( 1, parseFloatWithUnits( v ) ) );

			}
```
</details>

### `positive(v: any): number`

**Parameters:**

- **`v`** `any`

**Returns:** `number`

**Calls:**

- `Math.max`
- `parseFloatWithUnits`

<details><summary>Code</summary>

```typescript
function positive( v ) {

				return Math.max( 0, parseFloatWithUnits( v ) );

			}
```
</details>

### `getReflection(a: any, b: any): number`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function getReflection( a, b ) {

			return a - ( b - a );

		}
```
</details>

### `parseFloats(input: any, flags: any, stride: any): any[]`

**Parameters:**

- **`input`** `any`
- **`flags`** `any`
- **`stride`** `any`

**Returns:** `any[]`

**Calls:**

- `result.push`
- `Number`
- `Math.pow`
- `Array.isArray`
- `flags.includes`
- `RE.FLAGS.test`
- `newNumber`
- `RE.WHITESPACE.test`
- `RE.DIGIT.test`
- `RE.SIGN.test`
- `RE.POINT.test`
- `RE.COMMA.test`
- `throwSyntaxError`
- `RE.EXP.test`

**Internal Comments:**
```
// Character groups (x2)
// States (x2)
// check for flags
// parse until next number
// eat whitespace
// start new number
// throw on double commas (e.g. "1, , 2")
// parse integer part
// throw on double signs ("-+1"), but not on sign as separator ("-1-2")
// parse decimal part
// throw on double decimal points (e.g. "1..2")
// parse exponent part
// end of number
// add the last number found (if any) (x3)
```

<details><summary>Code</summary>

```typescript
function parseFloats( input, flags, stride ) {

			if ( typeof input !== 'string' ) {

				throw new TypeError( 'Invalid input: ' + typeof input );

			}

			// Character groups
			const RE = {
				SEPARATOR: /[ \t\r\n\,.\-+]/,
				WHITESPACE: /[ \t\r\n]/,
				DIGIT: /[\d]/,
				SIGN: /[-+]/,
				POINT: /\./,
				COMMA: /,/,
				EXP: /e/i,
				FLAGS: /[01]/
			};

			// States
			const SEP = 0;
			const INT = 1;
			const FLOAT = 2;
			const EXP = 3;

			let state = SEP;
			let seenComma = true;
			let number = '', exponent = '';
			const result = [];

			function throwSyntaxError( current, i, partial ) {

				const error = new SyntaxError( 'Unexpected character "' + current + '" at index ' + i + '.' );
				error.partial = partial;
				throw error;

			}

			function newNumber() {

				if ( number !== '' ) {

					if ( exponent === '' ) result.push( Number( number ) );
					else result.push( Number( number ) * Math.pow( 10, Number( exponent ) ) );

				}

				number = '';
				exponent = '';

			}

			let current;
			const length = input.length;

			for ( let i = 0; i < length; i ++ ) {

				current = input[ i ];

				// check for flags
				if ( Array.isArray( flags ) && flags.includes( result.length % stride ) && RE.FLAGS.test( current ) ) {

					state = INT;
					number = current;
					newNumber();
					continue;

				}

				// parse until next number
				if ( state === SEP ) {

					// eat whitespace
					if ( RE.WHITESPACE.test( current ) ) {

						continue;

					}

					// start new number
					if ( RE.DIGIT.test( current ) || RE.SIGN.test( current ) ) {

						state = INT;
						number = current;
						continue;

					}

					if ( RE.POINT.test( current ) ) {

						state = FLOAT;
						number = current;
						continue;

					}

					// throw on double commas (e.g. "1, , 2")
					if ( RE.COMMA.test( current ) ) {

						if ( seenComma ) {

							throwSyntaxError( current, i, result );

						}

						seenComma = true;

					}

				}

				// parse integer part
				if ( state === INT ) {

					if ( RE.DIGIT.test( current ) ) {

						number += current;
						continue;

					}

					if ( RE.POINT.test( current ) ) {

						number += current;
						state = FLOAT;
						continue;

					}

					if ( RE.EXP.test( current ) ) {

						state = EXP;
						continue;

					}

					// throw on double signs ("-+1"), but not on sign as separator ("-1-2")
					if ( RE.SIGN.test( current )
							&& number.length === 1
							&& RE.SIGN.test( number[ 0 ] ) ) {

						throwSyntaxError( current, i, result );

					}

				}

				// parse decimal part
				if ( state === FLOAT ) {

					if ( RE.DIGIT.test( current ) ) {

						number += current;
						continue;

					}

					if ( RE.EXP.test( current ) ) {

						state = EXP;
						continue;

					}

					// throw on double decimal points (e.g. "1..2")
					if ( RE.POINT.test( current ) && number[ number.length - 1 ] === '.' ) {

						throwSyntaxError( current, i, result );

					}

				}

				// parse exponent part
				if ( state === EXP ) {

					if ( RE.DIGIT.test( current ) ) {

						exponent += current;
						continue;

					}

					if ( RE.SIGN.test( current ) ) {

						if ( exponent === '' ) {

							exponent += current;
							continue;

						}

						if ( exponent.length === 1 && RE.SIGN.test( exponent ) ) {

							throwSyntaxError( current, i, result );

						}

					}

				}


				// end of number
				if ( RE.WHITESPACE.test( current ) ) {

					newNumber();
					state = SEP;
					seenComma = false;

				} else if ( RE.COMMA.test( current ) ) {

					newNumber();
					state = SEP;
					seenComma = true;

				} else if ( RE.SIGN.test( current ) ) {

					newNumber();
					state = INT;
					number = current;

				} else if ( RE.POINT.test( current ) ) {

					newNumber();
					state = FLOAT;
					number = current;

				} else {

					throwSyntaxError( current, i, result );

				}

			}

			// add the last number found (if any)
			newNumber();

			return result;

		}
```
</details>

### `throwSyntaxError(current: any, i: any, partial: any): void`

**Parameters:**

- **`current`** `any`
- **`i`** `any`
- **`partial`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function throwSyntaxError( current, i, partial ) {

				const error = new SyntaxError( 'Unexpected character "' + current + '" at index ' + i + '.' );
				error.partial = partial;
				throw error;

			}
```
</details>

### `newNumber(): void`

**Returns:** `void`

**Calls:**

- `result.push`
- `Number`
- `Math.pow`

<details><summary>Code</summary>

```typescript
function newNumber() {

				if ( number !== '' ) {

					if ( exponent === '' ) result.push( Number( number ) );
					else result.push( Number( number ) * Math.pow( 10, Number( exponent ) ) );

				}

				number = '';
				exponent = '';

			}
```
</details>

### `parseFloatWithUnits(string: any): number`

**Parameters:**

- **`string`** `any`

**Returns:** `number`

**Calls:**

- `string.endsWith`
- `string.substring`
- `parseFloat`

**Internal Comments:**
```
// Conversion scale from  pixels to inches, then to default units (x3)
// Conversion scale to pixels (x3)
```

<details><summary>Code</summary>

```typescript
function parseFloatWithUnits( string ) {

			let theUnit = 'px';

			if ( typeof string === 'string' || string instanceof String ) {

				for ( let i = 0, n = units.length; i < n; i ++ ) {

					const u = units[ i ];

					if ( string.endsWith( u ) ) {

						theUnit = u;
						string = string.substring( 0, string.length - u.length );
						break;

					}

				}

			}

			let scale = undefined;

			if ( theUnit === 'px' && scope.defaultUnit !== 'px' ) {

				// Conversion scale from  pixels to inches, then to default units

				scale = unitConversion[ 'in' ][ scope.defaultUnit ] / scope.defaultDPI;

			} else {

				scale = unitConversion[ theUnit ][ scope.defaultUnit ];

				if ( scale < 0 ) {

					// Conversion scale to pixels

					scale = unitConversion[ theUnit ][ 'in' ] * scope.defaultDPI;

				}

			}

			return scale * parseFloat( string );

		}
```
</details>

### `getNodeTransform(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `node.hasAttribute`
- `parseNodeTransform`
- `transform.premultiply`
- `currentTransform.copy`
- `transformStack.push`

<details><summary>Code</summary>

```typescript
function getNodeTransform( node ) {

			if ( ! ( node.hasAttribute( 'transform' ) || ( node.nodeName === 'use' && ( node.hasAttribute( 'x' ) || node.hasAttribute( 'y' ) ) ) ) ) {

				return null;

			}

			const transform = parseNodeTransform( node );

			if ( transformStack.length > 0 ) {

				transform.premultiply( transformStack[ transformStack.length - 1 ] );

			}

			currentTransform.copy( transform );
			transformStack.push( transform );

			return transform;

		}
```
</details>

### `parseNodeTransform(node: any): any`

**Parameters:**

- **`node`** `any`

**Returns:** `any`

**Calls:**

- `node.hasAttribute`
- `parseFloatWithUnits`
- `node.getAttribute`
- `transform.translate`
- `node.getAttribute( 'transform' ).split`
- `transformsTexts[ tIndex ].trim`
- `transformText.indexOf`
- `transformText.slice`
- `parseFloats`
- `currentTransform.identity`
- `currentTransform.translate`
- `tempTransform1.makeTranslation`
- `tempTransform2.makeRotation`
- `tempTransform3.multiplyMatrices`
- `currentTransform.multiplyMatrices`
- `currentTransform.scale`
- `currentTransform.set`
- `Math.tan`
- `transform.premultiply`

**Internal Comments:**
```
// Angle (x3)
// Center x, y (x3)
// Rotate around center (cx, cy) (x4)
```

<details><summary>Code</summary>

```typescript
function parseNodeTransform( node ) {

			const transform = new Matrix3();
			const currentTransform = tempTransform0;

			if ( node.nodeName === 'use' && ( node.hasAttribute( 'x' ) || node.hasAttribute( 'y' ) ) ) {

				const tx = parseFloatWithUnits( node.getAttribute( 'x' ) );
				const ty = parseFloatWithUnits( node.getAttribute( 'y' ) );

				transform.translate( tx, ty );

			}

			if ( node.hasAttribute( 'transform' ) ) {

				const transformsTexts = node.getAttribute( 'transform' ).split( ')' );

				for ( let tIndex = transformsTexts.length - 1; tIndex >= 0; tIndex -- ) {

					const transformText = transformsTexts[ tIndex ].trim();

					if ( transformText === '' ) continue;

					const openParPos = transformText.indexOf( '(' );
					const closeParPos = transformText.length;

					if ( openParPos > 0 && openParPos < closeParPos ) {

						const transformType = transformText.slice( 0, openParPos );

						const array = parseFloats( transformText.slice( openParPos + 1 ) );

						currentTransform.identity();

						switch ( transformType ) {

							case 'translate':

								if ( array.length >= 1 ) {

									const tx = array[ 0 ];
									let ty = 0;

									if ( array.length >= 2 ) {

										ty = array[ 1 ];

									}

									currentTransform.translate( tx, ty );

								}

								break;

							case 'rotate':

								if ( array.length >= 1 ) {

									let angle = 0;
									let cx = 0;
									let cy = 0;

									// Angle
									angle = array[ 0 ] * Math.PI / 180;

									if ( array.length >= 3 ) {

										// Center x, y
										cx = array[ 1 ];
										cy = array[ 2 ];

									}

									// Rotate around center (cx, cy)
									tempTransform1.makeTranslation( - cx, - cy );
									tempTransform2.makeRotation( angle );
									tempTransform3.multiplyMatrices( tempTransform2, tempTransform1 );
									tempTransform1.makeTranslation( cx, cy );
									currentTransform.multiplyMatrices( tempTransform1, tempTransform3 );

								}

								break;

							case 'scale':

								if ( array.length >= 1 ) {

									const scaleX = array[ 0 ];
									let scaleY = scaleX;

									if ( array.length >= 2 ) {

										scaleY = array[ 1 ];

									}

									currentTransform.scale( scaleX, scaleY );

								}

								break;

							case 'skewX':

								if ( array.length === 1 ) {

									currentTransform.set(
										1, Math.tan( array[ 0 ] * Math.PI / 180 ), 0,
										0, 1, 0,
										0, 0, 1
									);

								}

								break;

							case 'skewY':

								if ( array.length === 1 ) {

									currentTransform.set(
										1, 0, 0,
										Math.tan( array[ 0 ] * Math.PI / 180 ), 1, 0,
										0, 0, 1
									);

								}

								break;

							case 'matrix':

								if ( array.length === 6 ) {

									currentTransform.set(
										array[ 0 ], array[ 2 ], array[ 4 ],
										array[ 1 ], array[ 3 ], array[ 5 ],
										0, 0, 1
									);

								}

								break;

						}

					}

					transform.premultiply( currentTransform );

				}

			}

			return transform;

		}
```
</details>

### `transformPath(path: any, m: any): void`

**Parameters:**

- **`path`** `any`
- **`m`** `any`

**Returns:** `void`

**Calls:**

- `tempV3.set( v2.x, v2.y, 1 ).applyMatrix3`
- `v2.set`
- `Math.cos`
- `Math.sin`
- `v1.applyMatrix3`
- `v2.applyMatrix3`
- `tempTransform0.set`
- `tempTransform1.copy( mF ).invert`
- `tempTransform2.copy( mFInv ).transpose`
- `mFInvT.multiply`
- `eigenDecomposition`
- `Math.sqrt`
- `Math.atan2`
- `tempTransform1.set`
- `tempTransform2.set`
- `mDsqrt.multiply( mRT ).multiply`
- `new Vector3( Math.cos( phi ), Math.sin( phi ), 0 ).applyMatrix3`
- `transformAngle`
- `isTransformFlipped`
- `getTransformScaleX`
- `getTransformScaleY`
- `transfVec2`
- `tempV2.set`
- `isTransformSkewed`
- `transfEllipseGeneric`
- `transfEllipseNoSkew`

**Internal Comments:**
```
// For math description see: (x2)
// https://math.stackexchange.com/questions/4544164 (x2)
// Do not touch angles of a full ellipse because after transformation they
// would converge to a single value effectively removing the whole curve
// Faster shortcut if no skew is applied (x2)
// (e.g, a euclidean transform of a group containing the ellipse) (x2)
// Extract rotation angle from the matrix of form: (x2)
// (x4)
//  | cosθ sx   -sinθ sy | (x2)
//  | sinθ sx    cosθ sy | (x2)
// Remembering that tanθ = sinθ / cosθ; and that (x2)
// `sx`, `sy`, or both might be zero. (x2)
// Transform ellipse center point (x4)
// Transform ellipse shape parameters
```

<details><summary>Code</summary>

```typescript
function transformPath( path, m ) {

			function transfVec2( v2 ) {

				tempV3.set( v2.x, v2.y, 1 ).applyMatrix3( m );

				v2.set( tempV3.x, tempV3.y );

			}

			function transfEllipseGeneric( curve ) {

				// For math description see:
				// https://math.stackexchange.com/questions/4544164

				const a = curve.xRadius;
				const b = curve.yRadius;

				const cosTheta = Math.cos( curve.aRotation );
				const sinTheta = Math.sin( curve.aRotation );

				const v1 = new Vector3( a * cosTheta, a * sinTheta, 0 );
				const v2 = new Vector3( - b * sinTheta, b * cosTheta, 0 );

				const f1 = v1.applyMatrix3( m );
				const f2 = v2.applyMatrix3( m );

				const mF = tempTransform0.set(
					f1.x, f2.x, 0,
					f1.y, f2.y, 0,
					0, 0, 1,
				);

				const mFInv = tempTransform1.copy( mF ).invert();
				const mFInvT = tempTransform2.copy( mFInv ).transpose();
				const mQ = mFInvT.multiply( mFInv );
				const mQe = mQ.elements;

				const ed = eigenDecomposition( mQe[ 0 ], mQe[ 1 ], mQe[ 4 ] );
				const rt1sqrt = Math.sqrt( ed.rt1 );
				const rt2sqrt = Math.sqrt( ed.rt2 );

				curve.xRadius = 1 / rt1sqrt;
				curve.yRadius = 1 / rt2sqrt;
				curve.aRotation = Math.atan2( ed.sn, ed.cs );

				const isFullEllipse =
					( curve.aEndAngle - curve.aStartAngle ) % ( 2 * Math.PI ) < Number.EPSILON;

				// Do not touch angles of a full ellipse because after transformation they
				// would converge to a single value effectively removing the whole curve

				if ( ! isFullEllipse ) {

					const mDsqrt = tempTransform1.set(
						rt1sqrt, 0, 0,
						0, rt2sqrt, 0,
						0, 0, 1,
					);

					const mRT = tempTransform2.set(
						ed.cs, ed.sn, 0,
						- ed.sn, ed.cs, 0,
						0, 0, 1,
					);

					const mDRF = mDsqrt.multiply( mRT ).multiply( mF );

					const transformAngle = phi => {

						const { x: cosR, y: sinR } =
							new Vector3( Math.cos( phi ), Math.sin( phi ), 0 ).applyMatrix3( mDRF );

						return Math.atan2( sinR, cosR );

					};

					curve.aStartAngle = transformAngle( curve.aStartAngle );
					curve.aEndAngle = transformAngle( curve.aEndAngle );

					if ( isTransformFlipped( m ) ) {

						curve.aClockwise = ! curve.aClockwise;

					}

				}

			}

			function transfEllipseNoSkew( curve ) {

				// Faster shortcut if no skew is applied
				// (e.g, a euclidean transform of a group containing the ellipse)

				const sx = getTransformScaleX( m );
				const sy = getTransformScaleY( m );

				curve.xRadius *= sx;
				curve.yRadius *= sy;

				// Extract rotation angle from the matrix of form:
				//
				//  | cosθ sx   -sinθ sy |
				//  | sinθ sx    cosθ sy |
				//
				// Remembering that tanθ = sinθ / cosθ; and that
				// `sx`, `sy`, or both might be zero.
				const theta =
					sx > Number.EPSILON
						? Math.atan2( m.elements[ 1 ], m.elements[ 0 ] )
						: Math.atan2( - m.elements[ 3 ], m.elements[ 4 ] );

				curve.aRotation += theta;

				if ( isTransformFlipped( m ) ) {

					curve.aStartAngle *= - 1;
					curve.aEndAngle *= - 1;
					curve.aClockwise = ! curve.aClockwise;

				}

			}

			const subPaths = path.subPaths;

			for ( let i = 0, n = subPaths.length; i < n; i ++ ) {

				const subPath = subPaths[ i ];
				const curves = subPath.curves;

				for ( let j = 0; j < curves.length; j ++ ) {

					const curve = curves[ j ];

					if ( curve.isLineCurve ) {

						transfVec2( curve.v1 );
						transfVec2( curve.v2 );

					} else if ( curve.isCubicBezierCurve ) {

						transfVec2( curve.v0 );
						transfVec2( curve.v1 );
						transfVec2( curve.v2 );
						transfVec2( curve.v3 );

					} else if ( curve.isQuadraticBezierCurve ) {

						transfVec2( curve.v0 );
						transfVec2( curve.v1 );
						transfVec2( curve.v2 );

					} else if ( curve.isEllipseCurve ) {

						// Transform ellipse center point

						tempV2.set( curve.aX, curve.aY );
						transfVec2( tempV2 );
						curve.aX = tempV2.x;
						curve.aY = tempV2.y;

						// Transform ellipse shape parameters

						if ( isTransformSkewed( m ) ) {

							transfEllipseGeneric( curve );

						} else {

							transfEllipseNoSkew( curve );

						}

					}

				}

			}

		}
```
</details>

### `transfVec2(v2: any): void`

**Parameters:**

- **`v2`** `any`

**Returns:** `void`

**Calls:**

- `tempV3.set( v2.x, v2.y, 1 ).applyMatrix3`
- `v2.set`

<details><summary>Code</summary>

```typescript
function transfVec2( v2 ) {

				tempV3.set( v2.x, v2.y, 1 ).applyMatrix3( m );

				v2.set( tempV3.x, tempV3.y );

			}
```
</details>

### `transfEllipseGeneric(curve: any): void`

**Parameters:**

- **`curve`** `any`

**Returns:** `void`

**Calls:**

- `Math.cos`
- `Math.sin`
- `v1.applyMatrix3`
- `v2.applyMatrix3`
- `tempTransform0.set`
- `tempTransform1.copy( mF ).invert`
- `tempTransform2.copy( mFInv ).transpose`
- `mFInvT.multiply`
- `eigenDecomposition`
- `Math.sqrt`
- `Math.atan2`
- `tempTransform1.set`
- `tempTransform2.set`
- `mDsqrt.multiply( mRT ).multiply`
- `new Vector3( Math.cos( phi ), Math.sin( phi ), 0 ).applyMatrix3`
- `transformAngle`
- `isTransformFlipped`

**Internal Comments:**
```
// For math description see: (x2)
// https://math.stackexchange.com/questions/4544164 (x2)
// Do not touch angles of a full ellipse because after transformation they
// would converge to a single value effectively removing the whole curve
```

<details><summary>Code</summary>

```typescript
function transfEllipseGeneric( curve ) {

				// For math description see:
				// https://math.stackexchange.com/questions/4544164

				const a = curve.xRadius;
				const b = curve.yRadius;

				const cosTheta = Math.cos( curve.aRotation );
				const sinTheta = Math.sin( curve.aRotation );

				const v1 = new Vector3( a * cosTheta, a * sinTheta, 0 );
				const v2 = new Vector3( - b * sinTheta, b * cosTheta, 0 );

				const f1 = v1.applyMatrix3( m );
				const f2 = v2.applyMatrix3( m );

				const mF = tempTransform0.set(
					f1.x, f2.x, 0,
					f1.y, f2.y, 0,
					0, 0, 1,
				);

				const mFInv = tempTransform1.copy( mF ).invert();
				const mFInvT = tempTransform2.copy( mFInv ).transpose();
				const mQ = mFInvT.multiply( mFInv );
				const mQe = mQ.elements;

				const ed = eigenDecomposition( mQe[ 0 ], mQe[ 1 ], mQe[ 4 ] );
				const rt1sqrt = Math.sqrt( ed.rt1 );
				const rt2sqrt = Math.sqrt( ed.rt2 );

				curve.xRadius = 1 / rt1sqrt;
				curve.yRadius = 1 / rt2sqrt;
				curve.aRotation = Math.atan2( ed.sn, ed.cs );

				const isFullEllipse =
					( curve.aEndAngle - curve.aStartAngle ) % ( 2 * Math.PI ) < Number.EPSILON;

				// Do not touch angles of a full ellipse because after transformation they
				// would converge to a single value effectively removing the whole curve

				if ( ! isFullEllipse ) {

					const mDsqrt = tempTransform1.set(
						rt1sqrt, 0, 0,
						0, rt2sqrt, 0,
						0, 0, 1,
					);

					const mRT = tempTransform2.set(
						ed.cs, ed.sn, 0,
						- ed.sn, ed.cs, 0,
						0, 0, 1,
					);

					const mDRF = mDsqrt.multiply( mRT ).multiply( mF );

					const transformAngle = phi => {

						const { x: cosR, y: sinR } =
							new Vector3( Math.cos( phi ), Math.sin( phi ), 0 ).applyMatrix3( mDRF );

						return Math.atan2( sinR, cosR );

					};

					curve.aStartAngle = transformAngle( curve.aStartAngle );
					curve.aEndAngle = transformAngle( curve.aEndAngle );

					if ( isTransformFlipped( m ) ) {

						curve.aClockwise = ! curve.aClockwise;

					}

				}

			}
```
</details>

### `transformAngle(phi: any): number`

**Parameters:**

- **`phi`** `any`

**Returns:** `number`

**Calls:**

- `new Vector3( Math.cos( phi ), Math.sin( phi ), 0 ).applyMatrix3`
- `Math.cos`
- `Math.sin`
- `Math.atan2`

<details><summary>Code</summary>

```typescript
phi => {

						const { x: cosR, y: sinR } =
							new Vector3( Math.cos( phi ), Math.sin( phi ), 0 ).applyMatrix3( mDRF );

						return Math.atan2( sinR, cosR );

					}
```
</details>

### `transfEllipseNoSkew(curve: any): void`

**Parameters:**

- **`curve`** `any`

**Returns:** `void`

**Calls:**

- `getTransformScaleX`
- `getTransformScaleY`
- `Math.atan2`
- `isTransformFlipped`

**Internal Comments:**
```
// Faster shortcut if no skew is applied (x2)
// (e.g, a euclidean transform of a group containing the ellipse) (x2)
// Extract rotation angle from the matrix of form: (x2)
// (x4)
//  | cosθ sx   -sinθ sy | (x2)
//  | sinθ sx    cosθ sy | (x2)
// Remembering that tanθ = sinθ / cosθ; and that (x2)
// `sx`, `sy`, or both might be zero. (x2)
```

<details><summary>Code</summary>

```typescript
function transfEllipseNoSkew( curve ) {

				// Faster shortcut if no skew is applied
				// (e.g, a euclidean transform of a group containing the ellipse)

				const sx = getTransformScaleX( m );
				const sy = getTransformScaleY( m );

				curve.xRadius *= sx;
				curve.yRadius *= sy;

				// Extract rotation angle from the matrix of form:
				//
				//  | cosθ sx   -sinθ sy |
				//  | sinθ sx    cosθ sy |
				//
				// Remembering that tanθ = sinθ / cosθ; and that
				// `sx`, `sy`, or both might be zero.
				const theta =
					sx > Number.EPSILON
						? Math.atan2( m.elements[ 1 ], m.elements[ 0 ] )
						: Math.atan2( - m.elements[ 3 ], m.elements[ 4 ] );

				curve.aRotation += theta;

				if ( isTransformFlipped( m ) ) {

					curve.aStartAngle *= - 1;
					curve.aEndAngle *= - 1;
					curve.aClockwise = ! curve.aClockwise;

				}

			}
```
</details>

### `isTransformFlipped(m: any): boolean`

**Parameters:**

- **`m`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isTransformFlipped( m ) {

			const te = m.elements;
			return te[ 0 ] * te[ 4 ] - te[ 1 ] * te[ 3 ] < 0;

		}
```
</details>

### `isTransformSkewed(m: any): boolean`

**Parameters:**

- **`m`** `any`

**Returns:** `boolean`

**Calls:**

- `getTransformScaleX`
- `getTransformScaleY`
- `Math.abs`

**Internal Comments:**
```
// Shortcut for trivial rotations and transformations
```

<details><summary>Code</summary>

```typescript
function isTransformSkewed( m ) {

			const te = m.elements;
			const basisDot = te[ 0 ] * te[ 3 ] + te[ 1 ] * te[ 4 ];

			// Shortcut for trivial rotations and transformations
			if ( basisDot === 0 ) return false;

			const sx = getTransformScaleX( m );
			const sy = getTransformScaleY( m );

			return Math.abs( basisDot / ( sx * sy ) ) > Number.EPSILON;

		}
```
</details>

### `getTransformScaleX(m: any): number`

**Parameters:**

- **`m`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function getTransformScaleX( m ) {

			const te = m.elements;
			return Math.sqrt( te[ 0 ] * te[ 0 ] + te[ 1 ] * te[ 1 ] );

		}
```
</details>

### `getTransformScaleY(m: any): number`

**Parameters:**

- **`m`** `any`

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function getTransformScaleY( m ) {

			const te = m.elements;
			return Math.sqrt( te[ 3 ] * te[ 3 ] + te[ 4 ] * te[ 4 ] );

		}
```
</details>

### `eigenDecomposition(A: any, B: any, C: any): { rt1: number; rt2: number; cs: number; sn: number; }`

**Parameters:**

- **`A`** `any`
- **`B`** `any`
- **`C`** `any`

**Returns:** `{ rt1: number; rt2: number; cs: number; sn: number; }`

**Calls:**

- `Math.sqrt`
- `Math.abs`

**Internal Comments:**
```
// This case needs to be treated separately to avoid div by 0 (x3)
// Calculate eigenvectors
```

<details><summary>Code</summary>

```typescript
function eigenDecomposition( A, B, C ) {

			let rt1, rt2, cs, sn, t;
			const sm = A + C;
			const df = A - C;
			const rt = Math.sqrt( df * df + 4 * B * B );

			if ( sm > 0 ) {

				rt1 = 0.5 * ( sm + rt );
				t = 1 / rt1;
				rt2 = A * t * C - B * t * B;

			} else if ( sm < 0 ) {

				rt2 = 0.5 * ( sm - rt );

			} else {

				// This case needs to be treated separately to avoid div by 0

				rt1 = 0.5 * rt;
				rt2 = - 0.5 * rt;

			}

			// Calculate eigenvectors

			if ( df > 0 ) {

				cs = df + rt;

			} else {

				cs = df - rt;

			}

			if ( Math.abs( cs ) > 2 * Math.abs( B ) ) {

				t = - 2 * B / cs;
				sn = 1 / Math.sqrt( 1 + t * t );
				cs = t * sn;

			} else if ( Math.abs( B ) === 0 ) {

				cs = 1;
				sn = 0;

			} else {

				t = - 0.5 * cs / B;
				cs = 1 / Math.sqrt( 1 + t * t );
				sn = t * cs;

			}

			if ( df > 0 ) {

				t = cs;
				cs = - sn;
				sn = t;

			}

			return { rt1, rt2, cs, sn };

		}
```
</details>

### `findEdgeIntersection(a0: any, a1: any, b0: any, b1: any): { x: any; y: any; t: number; }`

**Parameters:**

- **`a0`** `any`
- **`a1`** `any`
- **`b0`** `any`
- **`b1`** `any`

**Returns:** `{ x: any; y: any; t: number; }`

**Calls:**

- `classifyPoint`
- `( x1 + classifyResult.t * ( x2 - x1 ) ).toPrecision`
- `( y1 + classifyResult.t * ( y2 - y1 ) ).toPrecision`
- `( x1 + t1 * ( x2 - x1 ) ).toPrecision`
- `( y1 + t1 * ( y2 - y1 ) ).toPrecision`

**Internal Comments:**
```
//1. lines are parallel or edges don't intersect
//2. lines are colinear
//check if endpoints of edge2 (b0-b1) lies on edge1 (a0-a1)
//find position of this endpoints relatively to edge1
//3. edges intersect
```

<details><summary>Code</summary>

```typescript
function findEdgeIntersection( a0, a1, b0, b1 ) {

			const x1 = a0.x;
			const x2 = a1.x;
			const x3 = b0.x;
			const x4 = b1.x;
			const y1 = a0.y;
			const y2 = a1.y;
			const y3 = b0.y;
			const y4 = b1.y;
			const nom1 = ( x4 - x3 ) * ( y1 - y3 ) - ( y4 - y3 ) * ( x1 - x3 );
			const nom2 = ( x2 - x1 ) * ( y1 - y3 ) - ( y2 - y1 ) * ( x1 - x3 );
			const denom = ( y4 - y3 ) * ( x2 - x1 ) - ( x4 - x3 ) * ( y2 - y1 );
			const t1 = nom1 / denom;
			const t2 = nom2 / denom;

			if ( ( ( denom === 0 ) && ( nom1 !== 0 ) ) || ( t1 <= 0 ) || ( t1 >= 1 ) || ( t2 < 0 ) || ( t2 > 1 ) ) {

				//1. lines are parallel or edges don't intersect

				return null;

			} else if ( ( nom1 === 0 ) && ( denom === 0 ) ) {

				//2. lines are colinear

				//check if endpoints of edge2 (b0-b1) lies on edge1 (a0-a1)
				for ( let i = 0; i < 2; i ++ ) {

					classifyPoint( i === 0 ? b0 : b1, a0, a1 );
					//find position of this endpoints relatively to edge1
					if ( classifyResult.loc == IntersectionLocationType.ORIGIN ) {

						const point = ( i === 0 ? b0 : b1 );
						return { x: point.x, y: point.y, t: classifyResult.t };

					} else if ( classifyResult.loc == IntersectionLocationType.BETWEEN ) {

						const x = + ( ( x1 + classifyResult.t * ( x2 - x1 ) ).toPrecision( 10 ) );
						const y = + ( ( y1 + classifyResult.t * ( y2 - y1 ) ).toPrecision( 10 ) );
						return { x: x, y: y, t: classifyResult.t, };

					}

				}

				return null;

			} else {

				//3. edges intersect

				for ( let i = 0; i < 2; i ++ ) {

					classifyPoint( i === 0 ? b0 : b1, a0, a1 );

					if ( classifyResult.loc == IntersectionLocationType.ORIGIN ) {

						const point = ( i === 0 ? b0 : b1 );
						return { x: point.x, y: point.y, t: classifyResult.t };

					}

				}

				const x = + ( ( x1 + t1 * ( x2 - x1 ) ).toPrecision( 10 ) );
				const y = + ( ( y1 + t1 * ( y2 - y1 ) ).toPrecision( 10 ) );
				return { x: x, y: y, t: t1 };

			}

		}
```
</details>

### `classifyPoint(p: any, edgeStart: any, edgeEnd: any): void`

**Parameters:**

- **`p`** `any`
- **`edgeStart`** `any`
- **`edgeEnd`** `any`

**Returns:** `void`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function classifyPoint( p, edgeStart, edgeEnd ) {

			const ax = edgeEnd.x - edgeStart.x;
			const ay = edgeEnd.y - edgeStart.y;
			const bx = p.x - edgeStart.x;
			const by = p.y - edgeStart.y;
			const sa = ax * by - bx * ay;

			if ( ( p.x === edgeStart.x ) && ( p.y === edgeStart.y ) ) {

				classifyResult.loc = IntersectionLocationType.ORIGIN;
				classifyResult.t = 0;
				return;

			}

			if ( ( p.x === edgeEnd.x ) && ( p.y === edgeEnd.y ) ) {

				classifyResult.loc = IntersectionLocationType.DESTINATION;
				classifyResult.t = 1;
				return;

			}

			if ( sa < - Number.EPSILON ) {

				classifyResult.loc = IntersectionLocationType.LEFT;
				return;

			}

			if ( sa > Number.EPSILON ) {

				classifyResult.loc = IntersectionLocationType.RIGHT;
				return;


			}

			if ( ( ( ax * bx ) < 0 ) || ( ( ay * by ) < 0 ) ) {

				classifyResult.loc = IntersectionLocationType.BEHIND;
				return;

			}

			if ( ( Math.sqrt( ax * ax + ay * ay ) ) < ( Math.sqrt( bx * bx + by * by ) ) ) {

				classifyResult.loc = IntersectionLocationType.BEYOND;
				return;

			}

			let t;

			if ( ax !== 0 ) {

				t = bx / ax;

			} else {

				t = by / ay;

			}

			classifyResult.loc = IntersectionLocationType.BETWEEN;
			classifyResult.t = t;

		}
```
</details>

### `getIntersections(path1: any, path2: any): any[]`

**Parameters:**

- **`path1`** `any`
- **`path2`** `any`

**Returns:** `any[]`

**Calls:**

- `findEdgeIntersection`
- `intersectionsRaw.find`
- `intersectionsRaw.push`
- `intersections.push`

<details><summary>Code</summary>

```typescript
function getIntersections( path1, path2 ) {

			const intersectionsRaw = [];
			const intersections = [];

			for ( let index = 1; index < path1.length; index ++ ) {

				const path1EdgeStart = path1[ index - 1 ];
				const path1EdgeEnd = path1[ index ];

				for ( let index2 = 1; index2 < path2.length; index2 ++ ) {

					const path2EdgeStart = path2[ index2 - 1 ];
					const path2EdgeEnd = path2[ index2 ];

					const intersection = findEdgeIntersection( path1EdgeStart, path1EdgeEnd, path2EdgeStart, path2EdgeEnd );

					if ( intersection !== null && intersectionsRaw.find( i => i.t <= intersection.t + Number.EPSILON && i.t >= intersection.t - Number.EPSILON ) === undefined ) {

						intersectionsRaw.push( intersection );
						intersections.push( new Vector2( intersection.x, intersection.y ) );

					}

				}

			}

			return intersections;

		}
```
</details>

### `getScanlineIntersections(scanline: any, boundingBox: any, paths: any): any[]`

**Parameters:**

- **`scanline`** `any`
- **`boundingBox`** `any`
- **`paths`** `any`

**Returns:** `any[]`

**Calls:**

- `boundingBox.getCenter`
- `paths.forEach`
- `path.boundingBox.containsPoint`
- `getIntersections`
- `intersections.forEach`
- `allIntersections.push`
- `allIntersections.sort`

**Internal Comments:**
```
// check if the center of the bounding box is in the bounding box of the paths.
// this is a pruning method to limit the search of intersections in paths that can't envelop of the current path.
// if a path envelops another path. The center of that other path, has to be inside the bounding box of the enveloping path.
```

<details><summary>Code</summary>

```typescript
function getScanlineIntersections( scanline, boundingBox, paths ) {

			const center = new Vector2();
			boundingBox.getCenter( center );

			const allIntersections = [];

			paths.forEach( path => {

				// check if the center of the bounding box is in the bounding box of the paths.
				// this is a pruning method to limit the search of intersections in paths that can't envelop of the current path.
				// if a path envelops another path. The center of that other path, has to be inside the bounding box of the enveloping path.
				if ( path.boundingBox.containsPoint( center ) ) {

					const intersections = getIntersections( scanline, path.points );

					intersections.forEach( p => {

						allIntersections.push( { identifier: path.identifier, isCW: path.isCW, point: p } );

					} );

				}

			} );

			allIntersections.sort( ( i1, i2 ) => {

				return i1.point.x - i2.point.x;

			} );

			return allIntersections;

		}
```
</details>

### `isHoleTo(simplePath: any, allPaths: any, scanlineMinX: any, scanlineMaxX: any, _fillRule: any): { identifier: any; isHole: boolean; for: any; }`

**Parameters:**

- **`simplePath`** `any`
- **`allPaths`** `any`
- **`scanlineMinX`** `any`
- **`scanlineMaxX`** `any`
- **`_fillRule`** `any`

**Returns:** `{ identifier: any; isHole: boolean; for: any; }`

**Calls:**

- `simplePath.boundingBox.getCenter`
- `getScanlineIntersections`
- `scanlineIntersections.sort`
- `scanlineIntersections.forEach`
- `baseIntersections.push`
- `otherIntersections.push`
- `stack.pop`
- `stack.push`
- `console.warn`

**Internal Comments:**
```
// build up the path hierarchy (x2)
// check if path is a hole by counting the amount of paths with alternating rotations it has to cross. (x2)
```

<details><summary>Code</summary>

```typescript
function isHoleTo( simplePath, allPaths, scanlineMinX, scanlineMaxX, _fillRule ) {

			if ( _fillRule === null || _fillRule === undefined || _fillRule === '' ) {

				_fillRule = 'nonzero';

			}

			const centerBoundingBox = new Vector2();
			simplePath.boundingBox.getCenter( centerBoundingBox );

			const scanline = [ new Vector2( scanlineMinX, centerBoundingBox.y ), new Vector2( scanlineMaxX, centerBoundingBox.y ) ];

			const scanlineIntersections = getScanlineIntersections( scanline, simplePath.boundingBox, allPaths );

			scanlineIntersections.sort( ( i1, i2 ) => {

				return i1.point.x - i2.point.x;

			} );

			const baseIntersections = [];
			const otherIntersections = [];

			scanlineIntersections.forEach( i => {

				if ( i.identifier === simplePath.identifier ) {

					baseIntersections.push( i );

				} else {

					otherIntersections.push( i );

				}

			} );

			const firstXOfPath = baseIntersections[ 0 ].point.x;

			// build up the path hierarchy
			const stack = [];
			let i = 0;

			while ( i < otherIntersections.length && otherIntersections[ i ].point.x < firstXOfPath ) {

				if ( stack.length > 0 && stack[ stack.length - 1 ] === otherIntersections[ i ].identifier ) {

					stack.pop();

				} else {

					stack.push( otherIntersections[ i ].identifier );

				}

				i ++;

			}

			stack.push( simplePath.identifier );

			if ( _fillRule === 'evenodd' ) {

				const isHole = stack.length % 2 === 0 ? true : false;
				const isHoleFor = stack[ stack.length - 2 ];

				return { identifier: simplePath.identifier, isHole: isHole, for: isHoleFor };

			} else if ( _fillRule === 'nonzero' ) {

				// check if path is a hole by counting the amount of paths with alternating rotations it has to cross.
				let isHole = true;
				let isHoleFor = null;
				let lastCWValue = null;

				for ( let i = 0; i < stack.length; i ++ ) {

					const identifier = stack[ i ];
					if ( isHole ) {

						lastCWValue = allPaths[ identifier ].isCW;
						isHole = false;
						isHoleFor = identifier;

					} else if ( lastCWValue !== allPaths[ identifier ].isCW ) {

						lastCWValue = allPaths[ identifier ].isCW;
						isHole = true;

					}

				}

				return { identifier: simplePath.identifier, isHole: isHole, for: isHoleFor };

			} else {

				console.warn( 'fill-rule: "' + _fillRule + '" is currently not implemented.' );

			}

		}
```
</details>

### `getNormal(p1: any, p2: any, result: any): any`

**Parameters:**

- **`p1`** `any`
- **`p2`** `any`
- **`result`** `any`

**Returns:** `any`

**Calls:**

- `result.subVectors`
- `result.set( - result.y, result.x ).normalize`

<details><summary>Code</summary>

```typescript
function getNormal( p1, p2, result ) {

			result.subVectors( p2, p1 );
			return result.set( - result.y, result.x ).normalize();

		}
```
</details>

### `addVertex(position: any, u: any, v: any): void`

**Parameters:**

- **`position`** `any`
- **`u`** `any`
- **`v`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function addVertex( position, u, v ) {

			if ( vertices ) {

				vertices[ currentCoordinate ] = position.x;
				vertices[ currentCoordinate + 1 ] = position.y;
				vertices[ currentCoordinate + 2 ] = 0;

				if ( normals ) {

					normals[ currentCoordinate ] = 0;
					normals[ currentCoordinate + 1 ] = 0;
					normals[ currentCoordinate + 2 ] = 1;

				}

				currentCoordinate += 3;

				if ( uvs ) {

					uvs[ currentCoordinateUV ] = u;
					uvs[ currentCoordinateUV + 1 ] = v;

					currentCoordinateUV += 2;

				}

			}

			numVertices += 3;

		}
```
</details>

### `makeCircularSector(center: any, p1: any, p2: any, u: any, v: any): void`

**Parameters:**

- **`center`** `any`
- **`p1`** `any`
- **`p2`** `any`
- **`u`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `tempV2_1.copy( p1 ).sub( center ).normalize`
- `tempV2_2.copy( p2 ).sub( center ).normalize`
- `tempV2_1.dot`
- `Math.abs`
- `Math.acos`
- `tempV2_3.copy`
- `tempV2_4.copy( tempV2_3 ).rotateAround`
- `addVertex`

**Internal Comments:**
```
// param p1, p2: Points in the circle arc. (x8)
// p1 and p2 are in clockwise direction. (x8)
```

<details><summary>Code</summary>

```typescript
function makeCircularSector( center, p1, p2, u, v ) {

			// param p1, p2: Points in the circle arc.
			// p1 and p2 are in clockwise direction.

			tempV2_1.copy( p1 ).sub( center ).normalize();
			tempV2_2.copy( p2 ).sub( center ).normalize();

			let angle = Math.PI;
			const dot = tempV2_1.dot( tempV2_2 );
			if ( Math.abs( dot ) < 1 ) angle = Math.abs( Math.acos( dot ) );

			angle /= arcDivisions;

			tempV2_3.copy( p1 );

			for ( let i = 0, il = arcDivisions - 1; i < il; i ++ ) {

				tempV2_4.copy( tempV2_3 ).rotateAround( center, angle );

				addVertex( tempV2_3, u, v );
				addVertex( tempV2_4, u, v );
				addVertex( center, u, 0.5 );

				tempV2_3.copy( tempV2_4 );

			}

			addVertex( tempV2_4, u, v );
			addVertex( p2, u, v );
			addVertex( center, u, 0.5 );

		}
```
</details>

### `makeSegmentTriangles(): void`

**Returns:** `void`

**Calls:**

- `addVertex`

<details><summary>Code</summary>

```typescript
function makeSegmentTriangles() {

			addVertex( lastPointR, u0, 1 );
			addVertex( lastPointL, u0, 0 );
			addVertex( currentPointL, u1, 0 );

			addVertex( lastPointR, u0, 1 );
			addVertex( currentPointL, u1, 0 );
			addVertex( currentPointR, u1, 1 );

		}
```
</details>

### `makeSegmentWithBevelJoin(joinIsOnLeftSide: any, innerSideModified: any, u: any): void`

**Parameters:**

- **`joinIsOnLeftSide`** `any`
- **`innerSideModified`** `any`
- **`u`** `any`

**Returns:** `void`

**Calls:**

- `addVertex`

**Internal Comments:**
```
// Optimized segment + bevel triangles
// Path segments triangles (x6)
// Bevel join triangle (x6)
// Bevel join triangle. The segment triangles are done in the main loop
```

<details><summary>Code</summary>

```typescript
function makeSegmentWithBevelJoin( joinIsOnLeftSide, innerSideModified, u ) {

			if ( innerSideModified ) {

				// Optimized segment + bevel triangles

				if ( joinIsOnLeftSide ) {

					// Path segments triangles

					addVertex( lastPointR, u0, 1 );
					addVertex( lastPointL, u0, 0 );
					addVertex( currentPointL, u1, 0 );

					addVertex( lastPointR, u0, 1 );
					addVertex( currentPointL, u1, 0 );
					addVertex( innerPoint, u1, 1 );

					// Bevel join triangle

					addVertex( currentPointL, u, 0 );
					addVertex( nextPointL, u, 0 );
					addVertex( innerPoint, u, 0.5 );

				} else {

					// Path segments triangles

					addVertex( lastPointR, u0, 1 );
					addVertex( lastPointL, u0, 0 );
					addVertex( currentPointR, u1, 1 );

					addVertex( lastPointL, u0, 0 );
					addVertex( innerPoint, u1, 0 );
					addVertex( currentPointR, u1, 1 );

					// Bevel join triangle

					addVertex( currentPointR, u, 1 );
					addVertex( innerPoint, u, 0 );
					addVertex( nextPointR, u, 1 );

				}

			} else {

				// Bevel join triangle. The segment triangles are done in the main loop

				if ( joinIsOnLeftSide ) {

					addVertex( currentPointL, u, 0 );
					addVertex( nextPointL, u, 0 );
					addVertex( currentPoint, u, 0.5 );

				} else {

					addVertex( currentPointR, u, 1 );
					addVertex( nextPointR, u, 0 );
					addVertex( currentPoint, u, 0.5 );

				}

			}

		}
```
</details>

### `createSegmentTrianglesWithMiddleSection(joinIsOnLeftSide: any, innerSideModified: any): void`

**Parameters:**

- **`joinIsOnLeftSide`** `any`
- **`innerSideModified`** `any`

**Returns:** `void`

**Calls:**

- `addVertex`

<details><summary>Code</summary>

```typescript
function createSegmentTrianglesWithMiddleSection( joinIsOnLeftSide, innerSideModified ) {

			if ( innerSideModified ) {

				if ( joinIsOnLeftSide ) {

					addVertex( lastPointR, u0, 1 );
					addVertex( lastPointL, u0, 0 );
					addVertex( currentPointL, u1, 0 );

					addVertex( lastPointR, u0, 1 );
					addVertex( currentPointL, u1, 0 );
					addVertex( innerPoint, u1, 1 );

					addVertex( currentPointL, u0, 0 );
					addVertex( currentPoint, u1, 0.5 );
					addVertex( innerPoint, u1, 1 );

					addVertex( currentPoint, u1, 0.5 );
					addVertex( nextPointL, u0, 0 );
					addVertex( innerPoint, u1, 1 );

				} else {

					addVertex( lastPointR, u0, 1 );
					addVertex( lastPointL, u0, 0 );
					addVertex( currentPointR, u1, 1 );

					addVertex( lastPointL, u0, 0 );
					addVertex( innerPoint, u1, 0 );
					addVertex( currentPointR, u1, 1 );

					addVertex( currentPointR, u0, 1 );
					addVertex( innerPoint, u1, 0 );
					addVertex( currentPoint, u1, 0.5 );

					addVertex( currentPoint, u1, 0.5 );
					addVertex( innerPoint, u1, 0 );
					addVertex( nextPointR, u0, 1 );

				}

			}

		}
```
</details>

### `addCapGeometry(center: any, p1: any, p2: any, joinIsOnLeftSide: any, start: any, u: any): void`

**Parameters:**

- **`center`** `any`
- **`p1`** `any`
- **`p2`** `any`
- **`joinIsOnLeftSide`** `any`
- **`start`** `any`
- **`u`** `any`

**Returns:** `void`

**Calls:**

- `makeCircularSector`
- `tempV2_1.subVectors`
- `tempV2_2.set`
- `tempV2_3.addVectors( tempV2_1, tempV2_2 ).add`
- `tempV2_4.subVectors( tempV2_2, tempV2_1 ).add`
- `tempV2_3.toArray`
- `tempV2_4.toArray`

**Internal Comments:**
```
// param center: End point of the path
// param p1, p2: Left and right cap points
// Modify already existing vertices (x2)
// using tempV2_4 to update 3rd vertex if the uv.y of 3rd vertex is 1 (x5)
// Nothing to do here
```

<details><summary>Code</summary>

```typescript
function addCapGeometry( center, p1, p2, joinIsOnLeftSide, start, u ) {

			// param center: End point of the path
			// param p1, p2: Left and right cap points

			switch ( style.strokeLineCap ) {

				case 'round':

					if ( start ) {

						makeCircularSector( center, p2, p1, u, 0.5 );

					} else {

						makeCircularSector( center, p1, p2, u, 0.5 );

					}

					break;

				case 'square':

					if ( start ) {

						tempV2_1.subVectors( p1, center );
						tempV2_2.set( tempV2_1.y, - tempV2_1.x );

						tempV2_3.addVectors( tempV2_1, tempV2_2 ).add( center );
						tempV2_4.subVectors( tempV2_2, tempV2_1 ).add( center );

						// Modify already existing vertices
						if ( joinIsOnLeftSide ) {

							tempV2_3.toArray( vertices, 1 * 3 );
							tempV2_4.toArray( vertices, 0 * 3 );
							tempV2_4.toArray( vertices, 3 * 3 );

						} else {

							tempV2_3.toArray( vertices, 1 * 3 );
							// using tempV2_4 to update 3rd vertex if the uv.y of 3rd vertex is 1
							uvs[ 3 * 2 + 1 ] === 1 ? tempV2_4.toArray( vertices, 3 * 3 ) : tempV2_3.toArray( vertices, 3 * 3 );
							tempV2_4.toArray( vertices, 0 * 3 );

						}

					} else {

						tempV2_1.subVectors( p2, center );
						tempV2_2.set( tempV2_1.y, - tempV2_1.x );

						tempV2_3.addVectors( tempV2_1, tempV2_2 ).add( center );
						tempV2_4.subVectors( tempV2_2, tempV2_1 ).add( center );

						const vl = vertices.length;

						// Modify already existing vertices
						if ( joinIsOnLeftSide ) {

							tempV2_3.toArray( vertices, vl - 1 * 3 );
							tempV2_4.toArray( vertices, vl - 2 * 3 );
							tempV2_4.toArray( vertices, vl - 4 * 3 );

						} else {

							tempV2_4.toArray( vertices, vl - 2 * 3 );
							tempV2_3.toArray( vertices, vl - 1 * 3 );
							tempV2_4.toArray( vertices, vl - 4 * 3 );

						}

					}

					break;

				case 'butt':
				default:

					// Nothing to do here
					break;

			}

		}
```
</details>

### `removeDuplicatedPoints(points: any): any`

**Parameters:**

- **`points`** `any`

**Returns:** `any`

**Calls:**

- `points[ i ].distanceTo`
- `newPoints.push`

**Internal Comments:**
```
// Creates a new array if necessary with duplicated points removed. (x2)
// This does not remove duplicated initial and ending points of a closed path. (x2)
```

<details><summary>Code</summary>

```typescript
function removeDuplicatedPoints( points ) {

			// Creates a new array if necessary with duplicated points removed.
			// This does not remove duplicated initial and ending points of a closed path.

			let dupPoints = false;
			for ( let i = 1, n = points.length - 1; i < n; i ++ ) {

				if ( points[ i ].distanceTo( points[ i + 1 ] ) < minDistance ) {

					dupPoints = true;
					break;

				}

			}

			if ( ! dupPoints ) return points;

			const newPoints = [];
			newPoints.push( points[ 0 ] );

			for ( let i = 1, n = points.length - 1; i < n; i ++ ) {

				if ( points[ i ].distanceTo( points[ i + 1 ] ) >= minDistance ) {

					newPoints.push( points[ i ] );

				}

			}

			newPoints.push( points[ points.length - 1 ] );

			return newPoints;

		}
```
</details>


---

## Classes

### `SVGLoader`

<details><summary>Class Code</summary>

```ts
class SVGLoader extends Loader {

	/**
	 * Constructs a new SVG loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		/**
		 * Default dots per inch.
		 *
		 * @type {number}
		 * @default 90
		 */
		this.defaultDPI = 90;

		/**
		 * Default unit.
		 *
		 * @type {('mm'|'cm'|'in'|'pt'|'pc'|'px')}
		 * @default 'px'
		 */
		this.defaultUnit = 'px';

	}

	/**
	 * Starts loading from the given URL and passes the loaded SVG asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function({paths:Array<ShapePath>,xml:string})} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}

	/**
	 * Parses the given SVG data and returns the resulting data.
	 *
	 * @param {string} text - The raw SVG data as a string.
	 * @return {{paths:Array<ShapePath>,xml:string}} An object holding an array of shape paths and the
	 * SVG XML document.
	 */
	parse( text ) {

		const scope = this;

		function parseNode( node, style ) {

			if ( node.nodeType !== 1 ) return;

			const transform = getNodeTransform( node );

			let isDefsNode = false;

			let path = null;

			switch ( node.nodeName ) {

				case 'svg':
					style = parseStyle( node, style );
					break;

				case 'style':
					parseCSSStylesheet( node );
					break;

				case 'g':
					style = parseStyle( node, style );
					break;

				case 'path':
					style = parseStyle( node, style );
					if ( node.hasAttribute( 'd' ) ) path = parsePathNode( node );
					break;

				case 'rect':
					style = parseStyle( node, style );
					path = parseRectNode( node );
					break;

				case 'polygon':
					style = parseStyle( node, style );
					path = parsePolygonNode( node );
					break;

				case 'polyline':
					style = parseStyle( node, style );
					path = parsePolylineNode( node );
					break;

				case 'circle':
					style = parseStyle( node, style );
					path = parseCircleNode( node );
					break;

				case 'ellipse':
					style = parseStyle( node, style );
					path = parseEllipseNode( node );
					break;

				case 'line':
					style = parseStyle( node, style );
					path = parseLineNode( node );
					break;

				case 'defs':
					isDefsNode = true;
					break;

				case 'use':
					style = parseStyle( node, style );

					const href = node.getAttributeNS( 'http://www.w3.org/1999/xlink', 'href' ) || '';
					const usedNodeId = href.substring( 1 );
					const usedNode = node.viewportElement.getElementById( usedNodeId );
					if ( usedNode ) {

						parseNode( usedNode, style );

					} else {

						console.warn( 'SVGLoader: \'use node\' references non-existent node id: ' + usedNodeId );

					}

					break;

				default:
					// console.log( node );

			}

			if ( path ) {

				if ( style.fill !== undefined && style.fill !== 'none' ) {

					path.color.setStyle( style.fill, COLOR_SPACE_SVG );

				}

				transformPath( path, currentTransform );

				paths.push( path );

				path.userData = { node: node, style: style };

			}

			const childNodes = node.childNodes;

			for ( let i = 0; i < childNodes.length; i ++ ) {

				const node = childNodes[ i ];

				if ( isDefsNode && node.nodeName !== 'style' && node.nodeName !== 'defs' ) {

					// Ignore everything in defs except CSS style definitions
					// and nested defs, because it is OK by the standard to have
					// <style/> there.
					continue;

				}

				parseNode( node, style );

			}


			if ( transform ) {

				transformStack.pop();

				if ( transformStack.length > 0 ) {

					currentTransform.copy( transformStack[ transformStack.length - 1 ] );

				} else {

					currentTransform.identity();

				}

			}

		}

		function parsePathNode( node ) {

			const path = new ShapePath();

			const point = new Vector2();
			const control = new Vector2();

			const firstPoint = new Vector2();
			let isFirstPoint = true;
			let doSetFirstPoint = false;

			const d = node.getAttribute( 'd' );

			if ( d === '' || d === 'none' ) return null;

			// console.log( d );

			const commands = d.match( /[a-df-z][^a-df-z]*/ig );

			for ( let i = 0, l = commands.length; i < l; i ++ ) {

				const command = commands[ i ];

				const type = command.charAt( 0 );
				const data = command.slice( 1 ).trim();

				if ( isFirstPoint === true ) {

					doSetFirstPoint = true;
					isFirstPoint = false;

				}

				let numbers;

				switch ( type ) {

					case 'M':
						numbers = parseFloats( data );
						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							point.x = numbers[ j + 0 ];
							point.y = numbers[ j + 1 ];
							control.x = point.x;
							control.y = point.y;

							if ( j === 0 ) {

								path.moveTo( point.x, point.y );

							} else {

								path.lineTo( point.x, point.y );

							}

							if ( j === 0 ) firstPoint.copy( point );

						}

						break;

					case 'H':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j ++ ) {

							point.x = numbers[ j ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'V':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j ++ ) {

							point.y = numbers[ j ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'L':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							point.x = numbers[ j + 0 ];
							point.y = numbers[ j + 1 ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'C':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 6 ) {

							path.bezierCurveTo(
								numbers[ j + 0 ],
								numbers[ j + 1 ],
								numbers[ j + 2 ],
								numbers[ j + 3 ],
								numbers[ j + 4 ],
								numbers[ j + 5 ]
							);
							control.x = numbers[ j + 2 ];
							control.y = numbers[ j + 3 ];
							point.x = numbers[ j + 4 ];
							point.y = numbers[ j + 5 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'S':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 4 ) {

							path.bezierCurveTo(
								getReflection( point.x, control.x ),
								getReflection( point.y, control.y ),
								numbers[ j + 0 ],
								numbers[ j + 1 ],
								numbers[ j + 2 ],
								numbers[ j + 3 ]
							);
							control.x = numbers[ j + 0 ];
							control.y = numbers[ j + 1 ];
							point.x = numbers[ j + 2 ];
							point.y = numbers[ j + 3 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'Q':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 4 ) {

							path.quadraticCurveTo(
								numbers[ j + 0 ],
								numbers[ j + 1 ],
								numbers[ j + 2 ],
								numbers[ j + 3 ]
							);
							control.x = numbers[ j + 0 ];
							control.y = numbers[ j + 1 ];
							point.x = numbers[ j + 2 ];
							point.y = numbers[ j + 3 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'T':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							const rx = getReflection( point.x, control.x );
							const ry = getReflection( point.y, control.y );
							path.quadraticCurveTo(
								rx,
								ry,
								numbers[ j + 0 ],
								numbers[ j + 1 ]
							);
							control.x = rx;
							control.y = ry;
							point.x = numbers[ j + 0 ];
							point.y = numbers[ j + 1 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'A':
						numbers = parseFloats( data, [ 3, 4 ], 7 );

						for ( let j = 0, jl = numbers.length; j < jl; j += 7 ) {

							// skip command if start point == end point
							if ( numbers[ j + 5 ] == point.x && numbers[ j + 6 ] == point.y ) continue;

							const start = point.clone();
							point.x = numbers[ j + 5 ];
							point.y = numbers[ j + 6 ];
							control.x = point.x;
							control.y = point.y;
							parseArcCommand(
								path, numbers[ j ], numbers[ j + 1 ], numbers[ j + 2 ], numbers[ j + 3 ], numbers[ j + 4 ], start, point
							);

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'm':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							point.x += numbers[ j + 0 ];
							point.y += numbers[ j + 1 ];
							control.x = point.x;
							control.y = point.y;

							if ( j === 0 ) {

								path.moveTo( point.x, point.y );

							} else {

								path.lineTo( point.x, point.y );

							}

							if ( j === 0 ) firstPoint.copy( point );

						}

						break;

					case 'h':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j ++ ) {

							point.x += numbers[ j ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'v':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j ++ ) {

							point.y += numbers[ j ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'l':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							point.x += numbers[ j + 0 ];
							point.y += numbers[ j + 1 ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'c':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 6 ) {

							path.bezierCurveTo(
								point.x + numbers[ j + 0 ],
								point.y + numbers[ j + 1 ],
								point.x + numbers[ j + 2 ],
								point.y + numbers[ j + 3 ],
								point.x + numbers[ j + 4 ],
								point.y + numbers[ j + 5 ]
							);
							control.x = point.x + numbers[ j + 2 ];
							control.y = point.y + numbers[ j + 3 ];
							point.x += numbers[ j + 4 ];
							point.y += numbers[ j + 5 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 's':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 4 ) {

							path.bezierCurveTo(
								getReflection( point.x, control.x ),
								getReflection( point.y, control.y ),
								point.x + numbers[ j + 0 ],
								point.y + numbers[ j + 1 ],
								point.x + numbers[ j + 2 ],
								point.y + numbers[ j + 3 ]
							);
							control.x = point.x + numbers[ j + 0 ];
							control.y = point.y + numbers[ j + 1 ];
							point.x += numbers[ j + 2 ];
							point.y += numbers[ j + 3 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'q':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 4 ) {

							path.quadraticCurveTo(
								point.x + numbers[ j + 0 ],
								point.y + numbers[ j + 1 ],
								point.x + numbers[ j + 2 ],
								point.y + numbers[ j + 3 ]
							);
							control.x = point.x + numbers[ j + 0 ];
							control.y = point.y + numbers[ j + 1 ];
							point.x += numbers[ j + 2 ];
							point.y += numbers[ j + 3 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 't':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							const rx = getReflection( point.x, control.x );
							const ry = getReflection( point.y, control.y );
							path.quadraticCurveTo(
								rx,
								ry,
								point.x + numbers[ j + 0 ],
								point.y + numbers[ j + 1 ]
							);
							control.x = rx;
							control.y = ry;
							point.x = point.x + numbers[ j + 0 ];
							point.y = point.y + numbers[ j + 1 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'a':
						numbers = parseFloats( data, [ 3, 4 ], 7 );

						for ( let j = 0, jl = numbers.length; j < jl; j += 7 ) {

							// skip command if no displacement
							if ( numbers[ j + 5 ] == 0 && numbers[ j + 6 ] == 0 ) continue;

							const start = point.clone();
							point.x += numbers[ j + 5 ];
							point.y += numbers[ j + 6 ];
							control.x = point.x;
							control.y = point.y;
							parseArcCommand(
								path, numbers[ j ], numbers[ j + 1 ], numbers[ j + 2 ], numbers[ j + 3 ], numbers[ j + 4 ], start, point
							);

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'Z':
					case 'z':
						path.currentPath.autoClose = true;

						if ( path.currentPath.curves.length > 0 ) {

							// Reset point to beginning of Path
							point.copy( firstPoint );
							path.currentPath.currentPoint.copy( point );
							isFirstPoint = true;

						}

						break;

					default:
						console.warn( command );

				}

				// console.log( type, parseFloats( data ), parseFloats( data ).length  )

				doSetFirstPoint = false;

			}

			return path;

		}

		function parseCSSStylesheet( node ) {

			if ( ! node.sheet || ! node.sheet.cssRules || ! node.sheet.cssRules.length ) return;

			for ( let i = 0; i < node.sheet.cssRules.length; i ++ ) {

				const stylesheet = node.sheet.cssRules[ i ];

				if ( stylesheet.type !== 1 ) continue;

				const selectorList = stylesheet.selectorText
					.split( /,/gm )
					.filter( Boolean )
					.map( i => i.trim() );

				for ( let j = 0; j < selectorList.length; j ++ ) {

					// Remove empty rules
					const definitions = Object.fromEntries(
						Object.entries( stylesheet.style ).filter( ( [ , v ] ) => v !== '' )
					);

					stylesheets[ selectorList[ j ] ] = Object.assign(
						stylesheets[ selectorList[ j ] ] || {},
						definitions
					);

				}

			}

		}

		/**
		 * https://www.w3.org/TR/SVG/implnote.html#ArcImplementationNotes
		 * https://mortoray.com/2017/02/16/rendering-an-svg-elliptical-arc-as-bezier-curves/ Appendix: Endpoint to center arc conversion
		 * From
		 * rx ry x-axis-rotation large-arc-flag sweep-flag x y
		 * To
		 * aX, aY, xRadius, yRadius, aStartAngle, aEndAngle, aClockwise, aRotation
		 */

		function parseArcCommand( path, rx, ry, x_axis_rotation, large_arc_flag, sweep_flag, start, end ) {

			if ( rx == 0 || ry == 0 ) {

				// draw a line if either of the radii == 0
				path.lineTo( end.x, end.y );
				return;

			}

			x_axis_rotation = x_axis_rotation * Math.PI / 180;

			// Ensure radii are positive
			rx = Math.abs( rx );
			ry = Math.abs( ry );

			// Compute (x1', y1')
			const dx2 = ( start.x - end.x ) / 2.0;
			const dy2 = ( start.y - end.y ) / 2.0;
			const x1p = Math.cos( x_axis_rotation ) * dx2 + Math.sin( x_axis_rotation ) * dy2;
			const y1p = - Math.sin( x_axis_rotation ) * dx2 + Math.cos( x_axis_rotation ) * dy2;

			// Compute (cx', cy')
			let rxs = rx * rx;
			let rys = ry * ry;
			const x1ps = x1p * x1p;
			const y1ps = y1p * y1p;

			// Ensure radii are large enough
			const cr = x1ps / rxs + y1ps / rys;

			if ( cr > 1 ) {

				// scale up rx,ry equally so cr == 1
				const s = Math.sqrt( cr );
				rx = s * rx;
				ry = s * ry;
				rxs = rx * rx;
				rys = ry * ry;

			}

			const dq = ( rxs * y1ps + rys * x1ps );
			const pq = ( rxs * rys - dq ) / dq;
			let q = Math.sqrt( Math.max( 0, pq ) );
			if ( large_arc_flag === sweep_flag ) q = - q;
			const cxp = q * rx * y1p / ry;
			const cyp = - q * ry * x1p / rx;

			// Step 3: Compute (cx, cy) from (cx', cy')
			const cx = Math.cos( x_axis_rotation ) * cxp - Math.sin( x_axis_rotation ) * cyp + ( start.x + end.x ) / 2;
			const cy = Math.sin( x_axis_rotation ) * cxp + Math.cos( x_axis_rotation ) * cyp + ( start.y + end.y ) / 2;

			// Step 4: Compute θ1 and Δθ
			const theta = svgAngle( 1, 0, ( x1p - cxp ) / rx, ( y1p - cyp ) / ry );
			const delta = svgAngle( ( x1p - cxp ) / rx, ( y1p - cyp ) / ry, ( - x1p - cxp ) / rx, ( - y1p - cyp ) / ry ) % ( Math.PI * 2 );

			path.currentPath.absellipse( cx, cy, rx, ry, theta, theta + delta, sweep_flag === 0, x_axis_rotation );

		}

		function svgAngle( ux, uy, vx, vy ) {

			const dot = ux * vx + uy * vy;
			const len = Math.sqrt( ux * ux + uy * uy ) * Math.sqrt( vx * vx + vy * vy );
			let ang = Math.acos( Math.max( - 1, Math.min( 1, dot / len ) ) ); // floating point precision, slightly over values appear
			if ( ( ux * vy - uy * vx ) < 0 ) ang = - ang;
			return ang;

		}

		/*
		* According to https://www.w3.org/TR/SVG/shapes.html#RectElementRXAttribute
		* rounded corner should be rendered to elliptical arc, but bezier curve does the job well enough
		*/

		function parseRectNode( node ) {

			const x = parseFloatWithUnits( node.getAttribute( 'x' ) || 0 );
			const y = parseFloatWithUnits( node.getAttribute( 'y' ) || 0 );
			const rx = parseFloatWithUnits( node.getAttribute( 'rx' ) || node.getAttribute( 'ry' ) || 0 );
			const ry = parseFloatWithUnits( node.getAttribute( 'ry' ) || node.getAttribute( 'rx' ) || 0 );
			const w = parseFloatWithUnits( node.getAttribute( 'width' ) );
			const h = parseFloatWithUnits( node.getAttribute( 'height' ) );

			// Ellipse arc to Bezier approximation Coefficient (Inversed). See:
			// https://spencermortensen.com/articles/bezier-circle/
			const bci = 1 - 0.551915024494;

			const path = new ShapePath();

			// top left
			path.moveTo( x + rx, y );

			// top right
			path.lineTo( x + w - rx, y );
			if ( rx !== 0 || ry !== 0 ) {

				path.bezierCurveTo(
					x + w - rx * bci,
					y,
					x + w,
					y + ry * bci,
					x + w,
					y + ry
				);

			}

			// bottom right
			path.lineTo( x + w, y + h - ry );
			if ( rx !== 0 || ry !== 0 ) {

				path.bezierCurveTo(
					x + w,
					y + h - ry * bci,
					x + w - rx * bci,
					y + h,
					x + w - rx,
					y + h
				);

			}

			// bottom left
			path.lineTo( x + rx, y + h );
			if ( rx !== 0 || ry !== 0 ) {

				path.bezierCurveTo(
					x + rx * bci,
					y + h,
					x,
					y + h - ry * bci,
					x,
					y + h - ry
				);

			}

			// back to top left
			path.lineTo( x, y + ry );
			if ( rx !== 0 || ry !== 0 ) {

				path.bezierCurveTo( x, y + ry * bci, x + rx * bci, y, x + rx, y );

			}

			return path;

		}

		function parsePolygonNode( node ) {

			function iterator( match, a, b ) {

				const x = parseFloatWithUnits( a );
				const y = parseFloatWithUnits( b );

				if ( index === 0 ) {

					path.moveTo( x, y );

				} else {

					path.lineTo( x, y );

				}

				index ++;

			}

			const regex = /([+-]?\d*\.?\d+(?:e[+-]?\d+)?)(?:,|\s)([+-]?\d*\.?\d+(?:e[+-]?\d+)?)/g;

			const path = new ShapePath();

			let index = 0;

			node.getAttribute( 'points' ).replace( regex, iterator );

			path.currentPath.autoClose = true;

			return path;

		}

		function parsePolylineNode( node ) {

			function iterator( match, a, b ) {

				const x = parseFloatWithUnits( a );
				const y = parseFloatWithUnits( b );

				if ( index === 0 ) {

					path.moveTo( x, y );

				} else {

					path.lineTo( x, y );

				}

				index ++;

			}

			const regex = /([+-]?\d*\.?\d+(?:e[+-]?\d+)?)(?:,|\s)([+-]?\d*\.?\d+(?:e[+-]?\d+)?)/g;

			const path = new ShapePath();

			let index = 0;

			node.getAttribute( 'points' ).replace( regex, iterator );

			path.currentPath.autoClose = false;

			return path;

		}

		function parseCircleNode( node ) {

			const x = parseFloatWithUnits( node.getAttribute( 'cx' ) || 0 );
			const y = parseFloatWithUnits( node.getAttribute( 'cy' ) || 0 );
			const r = parseFloatWithUnits( node.getAttribute( 'r' ) || 0 );

			const subpath = new Path();
			subpath.absarc( x, y, r, 0, Math.PI * 2 );

			const path = new ShapePath();
			path.subPaths.push( subpath );

			return path;

		}

		function parseEllipseNode( node ) {

			const x = parseFloatWithUnits( node.getAttribute( 'cx' ) || 0 );
			const y = parseFloatWithUnits( node.getAttribute( 'cy' ) || 0 );
			const rx = parseFloatWithUnits( node.getAttribute( 'rx' ) || 0 );
			const ry = parseFloatWithUnits( node.getAttribute( 'ry' ) || 0 );

			const subpath = new Path();
			subpath.absellipse( x, y, rx, ry, 0, Math.PI * 2 );

			const path = new ShapePath();
			path.subPaths.push( subpath );

			return path;

		}

		function parseLineNode( node ) {

			const x1 = parseFloatWithUnits( node.getAttribute( 'x1' ) || 0 );
			const y1 = parseFloatWithUnits( node.getAttribute( 'y1' ) || 0 );
			const x2 = parseFloatWithUnits( node.getAttribute( 'x2' ) || 0 );
			const y2 = parseFloatWithUnits( node.getAttribute( 'y2' ) || 0 );

			const path = new ShapePath();
			path.moveTo( x1, y1 );
			path.lineTo( x2, y2 );
			path.currentPath.autoClose = false;

			return path;

		}

		//

		function parseStyle( node, style ) {

			style = Object.assign( {}, style ); // clone style

			let stylesheetStyles = {};

			if ( node.hasAttribute( 'class' ) ) {

				const classSelectors = node.getAttribute( 'class' )
					.split( /\s/ )
					.filter( Boolean )
					.map( i => i.trim() );

				for ( let i = 0; i < classSelectors.length; i ++ ) {

					stylesheetStyles = Object.assign( stylesheetStyles, stylesheets[ '.' + classSelectors[ i ] ] );

				}

			}

			if ( node.hasAttribute( 'id' ) ) {

				stylesheetStyles = Object.assign( stylesheetStyles, stylesheets[ '#' + node.getAttribute( 'id' ) ] );

			}

			function addStyle( svgName, jsName, adjustFunction ) {

				if ( adjustFunction === undefined ) adjustFunction = function copy( v ) {

					if ( v.startsWith( 'url' ) ) console.warn( 'SVGLoader: url access in attributes is not implemented.' );

					return v;

				};

				if ( node.hasAttribute( svgName ) ) style[ jsName ] = adjustFunction( node.getAttribute( svgName ) );
				if ( stylesheetStyles[ svgName ] ) style[ jsName ] = adjustFunction( stylesheetStyles[ svgName ] );
				if ( node.style && node.style[ svgName ] !== '' ) style[ jsName ] = adjustFunction( node.style[ svgName ] );

			}

			function clamp( v ) {

				return Math.max( 0, Math.min( 1, parseFloatWithUnits( v ) ) );

			}

			function positive( v ) {

				return Math.max( 0, parseFloatWithUnits( v ) );

			}

			addStyle( 'fill', 'fill' );
			addStyle( 'fill-opacity', 'fillOpacity', clamp );
			addStyle( 'fill-rule', 'fillRule' );
			addStyle( 'opacity', 'opacity', clamp );
			addStyle( 'stroke', 'stroke' );
			addStyle( 'stroke-opacity', 'strokeOpacity', clamp );
			addStyle( 'stroke-width', 'strokeWidth', positive );
			addStyle( 'stroke-linejoin', 'strokeLineJoin' );
			addStyle( 'stroke-linecap', 'strokeLineCap' );
			addStyle( 'stroke-miterlimit', 'strokeMiterLimit', positive );
			addStyle( 'visibility', 'visibility' );

			return style;

		}

		// http://www.w3.org/TR/SVG11/implnote.html#PathElementImplementationNotes

		function getReflection( a, b ) {

			return a - ( b - a );

		}

		// from https://github.com/ppvg/svg-numbers (MIT License)

		function parseFloats( input, flags, stride ) {

			if ( typeof input !== 'string' ) {

				throw new TypeError( 'Invalid input: ' + typeof input );

			}

			// Character groups
			const RE = {
				SEPARATOR: /[ \t\r\n\,.\-+]/,
				WHITESPACE: /[ \t\r\n]/,
				DIGIT: /[\d]/,
				SIGN: /[-+]/,
				POINT: /\./,
				COMMA: /,/,
				EXP: /e/i,
				FLAGS: /[01]/
			};

			// States
			const SEP = 0;
			const INT = 1;
			const FLOAT = 2;
			const EXP = 3;

			let state = SEP;
			let seenComma = true;
			let number = '', exponent = '';
			const result = [];

			function throwSyntaxError( current, i, partial ) {

				const error = new SyntaxError( 'Unexpected character "' + current + '" at index ' + i + '.' );
				error.partial = partial;
				throw error;

			}

			function newNumber() {

				if ( number !== '' ) {

					if ( exponent === '' ) result.push( Number( number ) );
					else result.push( Number( number ) * Math.pow( 10, Number( exponent ) ) );

				}

				number = '';
				exponent = '';

			}

			let current;
			const length = input.length;

			for ( let i = 0; i < length; i ++ ) {

				current = input[ i ];

				// check for flags
				if ( Array.isArray( flags ) && flags.includes( result.length % stride ) && RE.FLAGS.test( current ) ) {

					state = INT;
					number = current;
					newNumber();
					continue;

				}

				// parse until next number
				if ( state === SEP ) {

					// eat whitespace
					if ( RE.WHITESPACE.test( current ) ) {

						continue;

					}

					// start new number
					if ( RE.DIGIT.test( current ) || RE.SIGN.test( current ) ) {

						state = INT;
						number = current;
						continue;

					}

					if ( RE.POINT.test( current ) ) {

						state = FLOAT;
						number = current;
						continue;

					}

					// throw on double commas (e.g. "1, , 2")
					if ( RE.COMMA.test( current ) ) {

						if ( seenComma ) {

							throwSyntaxError( current, i, result );

						}

						seenComma = true;

					}

				}

				// parse integer part
				if ( state === INT ) {

					if ( RE.DIGIT.test( current ) ) {

						number += current;
						continue;

					}

					if ( RE.POINT.test( current ) ) {

						number += current;
						state = FLOAT;
						continue;

					}

					if ( RE.EXP.test( current ) ) {

						state = EXP;
						continue;

					}

					// throw on double signs ("-+1"), but not on sign as separator ("-1-2")
					if ( RE.SIGN.test( current )
							&& number.length === 1
							&& RE.SIGN.test( number[ 0 ] ) ) {

						throwSyntaxError( current, i, result );

					}

				}

				// parse decimal part
				if ( state === FLOAT ) {

					if ( RE.DIGIT.test( current ) ) {

						number += current;
						continue;

					}

					if ( RE.EXP.test( current ) ) {

						state = EXP;
						continue;

					}

					// throw on double decimal points (e.g. "1..2")
					if ( RE.POINT.test( current ) && number[ number.length - 1 ] === '.' ) {

						throwSyntaxError( current, i, result );

					}

				}

				// parse exponent part
				if ( state === EXP ) {

					if ( RE.DIGIT.test( current ) ) {

						exponent += current;
						continue;

					}

					if ( RE.SIGN.test( current ) ) {

						if ( exponent === '' ) {

							exponent += current;
							continue;

						}

						if ( exponent.length === 1 && RE.SIGN.test( exponent ) ) {

							throwSyntaxError( current, i, result );

						}

					}

				}


				// end of number
				if ( RE.WHITESPACE.test( current ) ) {

					newNumber();
					state = SEP;
					seenComma = false;

				} else if ( RE.COMMA.test( current ) ) {

					newNumber();
					state = SEP;
					seenComma = true;

				} else if ( RE.SIGN.test( current ) ) {

					newNumber();
					state = INT;
					number = current;

				} else if ( RE.POINT.test( current ) ) {

					newNumber();
					state = FLOAT;
					number = current;

				} else {

					throwSyntaxError( current, i, result );

				}

			}

			// add the last number found (if any)
			newNumber();

			return result;

		}

		// Units

		const units = [ 'mm', 'cm', 'in', 'pt', 'pc', 'px' ];

		// Conversion: [ fromUnit ][ toUnit ] (-1 means dpi dependent)
		const unitConversion = {

			'mm': {
				'mm': 1,
				'cm': 0.1,
				'in': 1 / 25.4,
				'pt': 72 / 25.4,
				'pc': 6 / 25.4,
				'px': - 1
			},
			'cm': {
				'mm': 10,
				'cm': 1,
				'in': 1 / 2.54,
				'pt': 72 / 2.54,
				'pc': 6 / 2.54,
				'px': - 1
			},
			'in': {
				'mm': 25.4,
				'cm': 2.54,
				'in': 1,
				'pt': 72,
				'pc': 6,
				'px': - 1
			},
			'pt': {
				'mm': 25.4 / 72,
				'cm': 2.54 / 72,
				'in': 1 / 72,
				'pt': 1,
				'pc': 6 / 72,
				'px': - 1
			},
			'pc': {
				'mm': 25.4 / 6,
				'cm': 2.54 / 6,
				'in': 1 / 6,
				'pt': 72 / 6,
				'pc': 1,
				'px': - 1
			},
			'px': {
				'px': 1
			}

		};

		function parseFloatWithUnits( string ) {

			let theUnit = 'px';

			if ( typeof string === 'string' || string instanceof String ) {

				for ( let i = 0, n = units.length; i < n; i ++ ) {

					const u = units[ i ];

					if ( string.endsWith( u ) ) {

						theUnit = u;
						string = string.substring( 0, string.length - u.length );
						break;

					}

				}

			}

			let scale = undefined;

			if ( theUnit === 'px' && scope.defaultUnit !== 'px' ) {

				// Conversion scale from  pixels to inches, then to default units

				scale = unitConversion[ 'in' ][ scope.defaultUnit ] / scope.defaultDPI;

			} else {

				scale = unitConversion[ theUnit ][ scope.defaultUnit ];

				if ( scale < 0 ) {

					// Conversion scale to pixels

					scale = unitConversion[ theUnit ][ 'in' ] * scope.defaultDPI;

				}

			}

			return scale * parseFloat( string );

		}

		// Transforms

		function getNodeTransform( node ) {

			if ( ! ( node.hasAttribute( 'transform' ) || ( node.nodeName === 'use' && ( node.hasAttribute( 'x' ) || node.hasAttribute( 'y' ) ) ) ) ) {

				return null;

			}

			const transform = parseNodeTransform( node );

			if ( transformStack.length > 0 ) {

				transform.premultiply( transformStack[ transformStack.length - 1 ] );

			}

			currentTransform.copy( transform );
			transformStack.push( transform );

			return transform;

		}

		function parseNodeTransform( node ) {

			const transform = new Matrix3();
			const currentTransform = tempTransform0;

			if ( node.nodeName === 'use' && ( node.hasAttribute( 'x' ) || node.hasAttribute( 'y' ) ) ) {

				const tx = parseFloatWithUnits( node.getAttribute( 'x' ) );
				const ty = parseFloatWithUnits( node.getAttribute( 'y' ) );

				transform.translate( tx, ty );

			}

			if ( node.hasAttribute( 'transform' ) ) {

				const transformsTexts = node.getAttribute( 'transform' ).split( ')' );

				for ( let tIndex = transformsTexts.length - 1; tIndex >= 0; tIndex -- ) {

					const transformText = transformsTexts[ tIndex ].trim();

					if ( transformText === '' ) continue;

					const openParPos = transformText.indexOf( '(' );
					const closeParPos = transformText.length;

					if ( openParPos > 0 && openParPos < closeParPos ) {

						const transformType = transformText.slice( 0, openParPos );

						const array = parseFloats( transformText.slice( openParPos + 1 ) );

						currentTransform.identity();

						switch ( transformType ) {

							case 'translate':

								if ( array.length >= 1 ) {

									const tx = array[ 0 ];
									let ty = 0;

									if ( array.length >= 2 ) {

										ty = array[ 1 ];

									}

									currentTransform.translate( tx, ty );

								}

								break;

							case 'rotate':

								if ( array.length >= 1 ) {

									let angle = 0;
									let cx = 0;
									let cy = 0;

									// Angle
									angle = array[ 0 ] * Math.PI / 180;

									if ( array.length >= 3 ) {

										// Center x, y
										cx = array[ 1 ];
										cy = array[ 2 ];

									}

									// Rotate around center (cx, cy)
									tempTransform1.makeTranslation( - cx, - cy );
									tempTransform2.makeRotation( angle );
									tempTransform3.multiplyMatrices( tempTransform2, tempTransform1 );
									tempTransform1.makeTranslation( cx, cy );
									currentTransform.multiplyMatrices( tempTransform1, tempTransform3 );

								}

								break;

							case 'scale':

								if ( array.length >= 1 ) {

									const scaleX = array[ 0 ];
									let scaleY = scaleX;

									if ( array.length >= 2 ) {

										scaleY = array[ 1 ];

									}

									currentTransform.scale( scaleX, scaleY );

								}

								break;

							case 'skewX':

								if ( array.length === 1 ) {

									currentTransform.set(
										1, Math.tan( array[ 0 ] * Math.PI / 180 ), 0,
										0, 1, 0,
										0, 0, 1
									);

								}

								break;

							case 'skewY':

								if ( array.length === 1 ) {

									currentTransform.set(
										1, 0, 0,
										Math.tan( array[ 0 ] * Math.PI / 180 ), 1, 0,
										0, 0, 1
									);

								}

								break;

							case 'matrix':

								if ( array.length === 6 ) {

									currentTransform.set(
										array[ 0 ], array[ 2 ], array[ 4 ],
										array[ 1 ], array[ 3 ], array[ 5 ],
										0, 0, 1
									);

								}

								break;

						}

					}

					transform.premultiply( currentTransform );

				}

			}

			return transform;

		}

		function transformPath( path, m ) {

			function transfVec2( v2 ) {

				tempV3.set( v2.x, v2.y, 1 ).applyMatrix3( m );

				v2.set( tempV3.x, tempV3.y );

			}

			function transfEllipseGeneric( curve ) {

				// For math description see:
				// https://math.stackexchange.com/questions/4544164

				const a = curve.xRadius;
				const b = curve.yRadius;

				const cosTheta = Math.cos( curve.aRotation );
				const sinTheta = Math.sin( curve.aRotation );

				const v1 = new Vector3( a * cosTheta, a * sinTheta, 0 );
				const v2 = new Vector3( - b * sinTheta, b * cosTheta, 0 );

				const f1 = v1.applyMatrix3( m );
				const f2 = v2.applyMatrix3( m );

				const mF = tempTransform0.set(
					f1.x, f2.x, 0,
					f1.y, f2.y, 0,
					0, 0, 1,
				);

				const mFInv = tempTransform1.copy( mF ).invert();
				const mFInvT = tempTransform2.copy( mFInv ).transpose();
				const mQ = mFInvT.multiply( mFInv );
				const mQe = mQ.elements;

				const ed = eigenDecomposition( mQe[ 0 ], mQe[ 1 ], mQe[ 4 ] );
				const rt1sqrt = Math.sqrt( ed.rt1 );
				const rt2sqrt = Math.sqrt( ed.rt2 );

				curve.xRadius = 1 / rt1sqrt;
				curve.yRadius = 1 / rt2sqrt;
				curve.aRotation = Math.atan2( ed.sn, ed.cs );

				const isFullEllipse =
					( curve.aEndAngle - curve.aStartAngle ) % ( 2 * Math.PI ) < Number.EPSILON;

				// Do not touch angles of a full ellipse because after transformation they
				// would converge to a single value effectively removing the whole curve

				if ( ! isFullEllipse ) {

					const mDsqrt = tempTransform1.set(
						rt1sqrt, 0, 0,
						0, rt2sqrt, 0,
						0, 0, 1,
					);

					const mRT = tempTransform2.set(
						ed.cs, ed.sn, 0,
						- ed.sn, ed.cs, 0,
						0, 0, 1,
					);

					const mDRF = mDsqrt.multiply( mRT ).multiply( mF );

					const transformAngle = phi => {

						const { x: cosR, y: sinR } =
							new Vector3( Math.cos( phi ), Math.sin( phi ), 0 ).applyMatrix3( mDRF );

						return Math.atan2( sinR, cosR );

					};

					curve.aStartAngle = transformAngle( curve.aStartAngle );
					curve.aEndAngle = transformAngle( curve.aEndAngle );

					if ( isTransformFlipped( m ) ) {

						curve.aClockwise = ! curve.aClockwise;

					}

				}

			}

			function transfEllipseNoSkew( curve ) {

				// Faster shortcut if no skew is applied
				// (e.g, a euclidean transform of a group containing the ellipse)

				const sx = getTransformScaleX( m );
				const sy = getTransformScaleY( m );

				curve.xRadius *= sx;
				curve.yRadius *= sy;

				// Extract rotation angle from the matrix of form:
				//
				//  | cosθ sx   -sinθ sy |
				//  | sinθ sx    cosθ sy |
				//
				// Remembering that tanθ = sinθ / cosθ; and that
				// `sx`, `sy`, or both might be zero.
				const theta =
					sx > Number.EPSILON
						? Math.atan2( m.elements[ 1 ], m.elements[ 0 ] )
						: Math.atan2( - m.elements[ 3 ], m.elements[ 4 ] );

				curve.aRotation += theta;

				if ( isTransformFlipped( m ) ) {

					curve.aStartAngle *= - 1;
					curve.aEndAngle *= - 1;
					curve.aClockwise = ! curve.aClockwise;

				}

			}

			const subPaths = path.subPaths;

			for ( let i = 0, n = subPaths.length; i < n; i ++ ) {

				const subPath = subPaths[ i ];
				const curves = subPath.curves;

				for ( let j = 0; j < curves.length; j ++ ) {

					const curve = curves[ j ];

					if ( curve.isLineCurve ) {

						transfVec2( curve.v1 );
						transfVec2( curve.v2 );

					} else if ( curve.isCubicBezierCurve ) {

						transfVec2( curve.v0 );
						transfVec2( curve.v1 );
						transfVec2( curve.v2 );
						transfVec2( curve.v3 );

					} else if ( curve.isQuadraticBezierCurve ) {

						transfVec2( curve.v0 );
						transfVec2( curve.v1 );
						transfVec2( curve.v2 );

					} else if ( curve.isEllipseCurve ) {

						// Transform ellipse center point

						tempV2.set( curve.aX, curve.aY );
						transfVec2( tempV2 );
						curve.aX = tempV2.x;
						curve.aY = tempV2.y;

						// Transform ellipse shape parameters

						if ( isTransformSkewed( m ) ) {

							transfEllipseGeneric( curve );

						} else {

							transfEllipseNoSkew( curve );

						}

					}

				}

			}

		}

		function isTransformFlipped( m ) {

			const te = m.elements;
			return te[ 0 ] * te[ 4 ] - te[ 1 ] * te[ 3 ] < 0;

		}

		function isTransformSkewed( m ) {

			const te = m.elements;
			const basisDot = te[ 0 ] * te[ 3 ] + te[ 1 ] * te[ 4 ];

			// Shortcut for trivial rotations and transformations
			if ( basisDot === 0 ) return false;

			const sx = getTransformScaleX( m );
			const sy = getTransformScaleY( m );

			return Math.abs( basisDot / ( sx * sy ) ) > Number.EPSILON;

		}

		function getTransformScaleX( m ) {

			const te = m.elements;
			return Math.sqrt( te[ 0 ] * te[ 0 ] + te[ 1 ] * te[ 1 ] );

		}

		function getTransformScaleY( m ) {

			const te = m.elements;
			return Math.sqrt( te[ 3 ] * te[ 3 ] + te[ 4 ] * te[ 4 ] );

		}

		// Calculates the eigensystem of a real symmetric 2x2 matrix
		//    [ A  B ]
		//    [ B  C ]
		// in the form
		//    [ A  B ]  =  [ cs  -sn ] [ rt1   0  ] [  cs  sn ]
		//    [ B  C ]     [ sn   cs ] [  0   rt2 ] [ -sn  cs ]
		// where rt1 >= rt2.
		//
		// Adapted from: https://www.mpi-hd.mpg.de/personalhomes/globes/3x3/index.html
		// -> Algorithms for real symmetric matrices -> Analytical (2x2 symmetric)
		function eigenDecomposition( A, B, C ) {

			let rt1, rt2, cs, sn, t;
			const sm = A + C;
			const df = A - C;
			const rt = Math.sqrt( df * df + 4 * B * B );

			if ( sm > 0 ) {

				rt1 = 0.5 * ( sm + rt );
				t = 1 / rt1;
				rt2 = A * t * C - B * t * B;

			} else if ( sm < 0 ) {

				rt2 = 0.5 * ( sm - rt );

			} else {

				// This case needs to be treated separately to avoid div by 0

				rt1 = 0.5 * rt;
				rt2 = - 0.5 * rt;

			}

			// Calculate eigenvectors

			if ( df > 0 ) {

				cs = df + rt;

			} else {

				cs = df - rt;

			}

			if ( Math.abs( cs ) > 2 * Math.abs( B ) ) {

				t = - 2 * B / cs;
				sn = 1 / Math.sqrt( 1 + t * t );
				cs = t * sn;

			} else if ( Math.abs( B ) === 0 ) {

				cs = 1;
				sn = 0;

			} else {

				t = - 0.5 * cs / B;
				cs = 1 / Math.sqrt( 1 + t * t );
				sn = t * cs;

			}

			if ( df > 0 ) {

				t = cs;
				cs = - sn;
				sn = t;

			}

			return { rt1, rt2, cs, sn };

		}

		//

		const paths = [];
		const stylesheets = {};

		const transformStack = [];

		const tempTransform0 = new Matrix3();
		const tempTransform1 = new Matrix3();
		const tempTransform2 = new Matrix3();
		const tempTransform3 = new Matrix3();
		const tempV2 = new Vector2();
		const tempV3 = new Vector3();

		const currentTransform = new Matrix3();

		const xml = new DOMParser().parseFromString( text, 'image/svg+xml' ); // application/xml

		parseNode( xml.documentElement, {
			fill: '#000',
			fillOpacity: 1,
			strokeOpacity: 1,
			strokeWidth: 1,
			strokeLineJoin: 'miter',
			strokeLineCap: 'butt',
			strokeMiterLimit: 4
		} );

		const data = { paths: paths, xml: xml.documentElement };

		// console.log( paths );
		return data;

	}

	/**
	 * Creates from the given shape path and array of shapes.
	 *
	 * @param {ShapePath} shapePath - The shape path.
	 * @return {Array<Shape>} An array of shapes.
	 */
	static createShapes( shapePath ) {

		const BIGNUMBER = 999999999;

		const IntersectionLocationType = {
			ORIGIN: 0,
			DESTINATION: 1,
			BETWEEN: 2,
			LEFT: 3,
			RIGHT: 4,
			BEHIND: 5,
			BEYOND: 6
		};

		const classifyResult = {
			loc: IntersectionLocationType.ORIGIN,
			t: 0
		};

		function findEdgeIntersection( a0, a1, b0, b1 ) {

			const x1 = a0.x;
			const x2 = a1.x;
			const x3 = b0.x;
			const x4 = b1.x;
			const y1 = a0.y;
			const y2 = a1.y;
			const y3 = b0.y;
			const y4 = b1.y;
			const nom1 = ( x4 - x3 ) * ( y1 - y3 ) - ( y4 - y3 ) * ( x1 - x3 );
			const nom2 = ( x2 - x1 ) * ( y1 - y3 ) - ( y2 - y1 ) * ( x1 - x3 );
			const denom = ( y4 - y3 ) * ( x2 - x1 ) - ( x4 - x3 ) * ( y2 - y1 );
			const t1 = nom1 / denom;
			const t2 = nom2 / denom;

			if ( ( ( denom === 0 ) && ( nom1 !== 0 ) ) || ( t1 <= 0 ) || ( t1 >= 1 ) || ( t2 < 0 ) || ( t2 > 1 ) ) {

				//1. lines are parallel or edges don't intersect

				return null;

			} else if ( ( nom1 === 0 ) && ( denom === 0 ) ) {

				//2. lines are colinear

				//check if endpoints of edge2 (b0-b1) lies on edge1 (a0-a1)
				for ( let i = 0; i < 2; i ++ ) {

					classifyPoint( i === 0 ? b0 : b1, a0, a1 );
					//find position of this endpoints relatively to edge1
					if ( classifyResult.loc == IntersectionLocationType.ORIGIN ) {

						const point = ( i === 0 ? b0 : b1 );
						return { x: point.x, y: point.y, t: classifyResult.t };

					} else if ( classifyResult.loc == IntersectionLocationType.BETWEEN ) {

						const x = + ( ( x1 + classifyResult.t * ( x2 - x1 ) ).toPrecision( 10 ) );
						const y = + ( ( y1 + classifyResult.t * ( y2 - y1 ) ).toPrecision( 10 ) );
						return { x: x, y: y, t: classifyResult.t, };

					}

				}

				return null;

			} else {

				//3. edges intersect

				for ( let i = 0; i < 2; i ++ ) {

					classifyPoint( i === 0 ? b0 : b1, a0, a1 );

					if ( classifyResult.loc == IntersectionLocationType.ORIGIN ) {

						const point = ( i === 0 ? b0 : b1 );
						return { x: point.x, y: point.y, t: classifyResult.t };

					}

				}

				const x = + ( ( x1 + t1 * ( x2 - x1 ) ).toPrecision( 10 ) );
				const y = + ( ( y1 + t1 * ( y2 - y1 ) ).toPrecision( 10 ) );
				return { x: x, y: y, t: t1 };

			}

		}

		function classifyPoint( p, edgeStart, edgeEnd ) {

			const ax = edgeEnd.x - edgeStart.x;
			const ay = edgeEnd.y - edgeStart.y;
			const bx = p.x - edgeStart.x;
			const by = p.y - edgeStart.y;
			const sa = ax * by - bx * ay;

			if ( ( p.x === edgeStart.x ) && ( p.y === edgeStart.y ) ) {

				classifyResult.loc = IntersectionLocationType.ORIGIN;
				classifyResult.t = 0;
				return;

			}

			if ( ( p.x === edgeEnd.x ) && ( p.y === edgeEnd.y ) ) {

				classifyResult.loc = IntersectionLocationType.DESTINATION;
				classifyResult.t = 1;
				return;

			}

			if ( sa < - Number.EPSILON ) {

				classifyResult.loc = IntersectionLocationType.LEFT;
				return;

			}

			if ( sa > Number.EPSILON ) {

				classifyResult.loc = IntersectionLocationType.RIGHT;
				return;


			}

			if ( ( ( ax * bx ) < 0 ) || ( ( ay * by ) < 0 ) ) {

				classifyResult.loc = IntersectionLocationType.BEHIND;
				return;

			}

			if ( ( Math.sqrt( ax * ax + ay * ay ) ) < ( Math.sqrt( bx * bx + by * by ) ) ) {

				classifyResult.loc = IntersectionLocationType.BEYOND;
				return;

			}

			let t;

			if ( ax !== 0 ) {

				t = bx / ax;

			} else {

				t = by / ay;

			}

			classifyResult.loc = IntersectionLocationType.BETWEEN;
			classifyResult.t = t;

		}

		function getIntersections( path1, path2 ) {

			const intersectionsRaw = [];
			const intersections = [];

			for ( let index = 1; index < path1.length; index ++ ) {

				const path1EdgeStart = path1[ index - 1 ];
				const path1EdgeEnd = path1[ index ];

				for ( let index2 = 1; index2 < path2.length; index2 ++ ) {

					const path2EdgeStart = path2[ index2 - 1 ];
					const path2EdgeEnd = path2[ index2 ];

					const intersection = findEdgeIntersection( path1EdgeStart, path1EdgeEnd, path2EdgeStart, path2EdgeEnd );

					if ( intersection !== null && intersectionsRaw.find( i => i.t <= intersection.t + Number.EPSILON && i.t >= intersection.t - Number.EPSILON ) === undefined ) {

						intersectionsRaw.push( intersection );
						intersections.push( new Vector2( intersection.x, intersection.y ) );

					}

				}

			}

			return intersections;

		}

		function getScanlineIntersections( scanline, boundingBox, paths ) {

			const center = new Vector2();
			boundingBox.getCenter( center );

			const allIntersections = [];

			paths.forEach( path => {

				// check if the center of the bounding box is in the bounding box of the paths.
				// this is a pruning method to limit the search of intersections in paths that can't envelop of the current path.
				// if a path envelops another path. The center of that other path, has to be inside the bounding box of the enveloping path.
				if ( path.boundingBox.containsPoint( center ) ) {

					const intersections = getIntersections( scanline, path.points );

					intersections.forEach( p => {

						allIntersections.push( { identifier: path.identifier, isCW: path.isCW, point: p } );

					} );

				}

			} );

			allIntersections.sort( ( i1, i2 ) => {

				return i1.point.x - i2.point.x;

			} );

			return allIntersections;

		}

		function isHoleTo( simplePath, allPaths, scanlineMinX, scanlineMaxX, _fillRule ) {

			if ( _fillRule === null || _fillRule === undefined || _fillRule === '' ) {

				_fillRule = 'nonzero';

			}

			const centerBoundingBox = new Vector2();
			simplePath.boundingBox.getCenter( centerBoundingBox );

			const scanline = [ new Vector2( scanlineMinX, centerBoundingBox.y ), new Vector2( scanlineMaxX, centerBoundingBox.y ) ];

			const scanlineIntersections = getScanlineIntersections( scanline, simplePath.boundingBox, allPaths );

			scanlineIntersections.sort( ( i1, i2 ) => {

				return i1.point.x - i2.point.x;

			} );

			const baseIntersections = [];
			const otherIntersections = [];

			scanlineIntersections.forEach( i => {

				if ( i.identifier === simplePath.identifier ) {

					baseIntersections.push( i );

				} else {

					otherIntersections.push( i );

				}

			} );

			const firstXOfPath = baseIntersections[ 0 ].point.x;

			// build up the path hierarchy
			const stack = [];
			let i = 0;

			while ( i < otherIntersections.length && otherIntersections[ i ].point.x < firstXOfPath ) {

				if ( stack.length > 0 && stack[ stack.length - 1 ] === otherIntersections[ i ].identifier ) {

					stack.pop();

				} else {

					stack.push( otherIntersections[ i ].identifier );

				}

				i ++;

			}

			stack.push( simplePath.identifier );

			if ( _fillRule === 'evenodd' ) {

				const isHole = stack.length % 2 === 0 ? true : false;
				const isHoleFor = stack[ stack.length - 2 ];

				return { identifier: simplePath.identifier, isHole: isHole, for: isHoleFor };

			} else if ( _fillRule === 'nonzero' ) {

				// check if path is a hole by counting the amount of paths with alternating rotations it has to cross.
				let isHole = true;
				let isHoleFor = null;
				let lastCWValue = null;

				for ( let i = 0; i < stack.length; i ++ ) {

					const identifier = stack[ i ];
					if ( isHole ) {

						lastCWValue = allPaths[ identifier ].isCW;
						isHole = false;
						isHoleFor = identifier;

					} else if ( lastCWValue !== allPaths[ identifier ].isCW ) {

						lastCWValue = allPaths[ identifier ].isCW;
						isHole = true;

					}

				}

				return { identifier: simplePath.identifier, isHole: isHole, for: isHoleFor };

			} else {

				console.warn( 'fill-rule: "' + _fillRule + '" is currently not implemented.' );

			}

		}

		// check for self intersecting paths
		// TODO

		// check intersecting paths
		// TODO

		// prepare paths for hole detection
		let scanlineMinX = BIGNUMBER;
		let scanlineMaxX = - BIGNUMBER;

		let simplePaths = shapePath.subPaths.map( p => {

			const points = p.getPoints();
			let maxY = - BIGNUMBER;
			let minY = BIGNUMBER;
			let maxX = - BIGNUMBER;
			let minX = BIGNUMBER;

	      	//points.forEach(p => p.y *= -1);

			for ( let i = 0; i < points.length; i ++ ) {

				const p = points[ i ];

				if ( p.y > maxY ) {

					maxY = p.y;

				}

				if ( p.y < minY ) {

					minY = p.y;

				}

				if ( p.x > maxX ) {

					maxX = p.x;

				}

				if ( p.x < minX ) {

					minX = p.x;

				}

			}

			//
			if ( scanlineMaxX <= maxX ) {

				scanlineMaxX = maxX + 1;

			}

			if ( scanlineMinX >= minX ) {

				scanlineMinX = minX - 1;

			}

			return { curves: p.curves, points: points, isCW: ShapeUtils.isClockWise( points ), identifier: - 1, boundingBox: new Box2( new Vector2( minX, minY ), new Vector2( maxX, maxY ) ) };

		} );

		simplePaths = simplePaths.filter( sp => sp.points.length > 1 );

		for ( let identifier = 0; identifier < simplePaths.length; identifier ++ ) {

			simplePaths[ identifier ].identifier = identifier;

		}

		// check if path is solid or a hole
		const isAHole = simplePaths.map( p => isHoleTo( p, simplePaths, scanlineMinX, scanlineMaxX, ( shapePath.userData ? shapePath.userData.style.fillRule : undefined ) ) );


		const shapesToReturn = [];
		simplePaths.forEach( p => {

			const amIAHole = isAHole[ p.identifier ];

			if ( ! amIAHole.isHole ) {

				const shape = new Shape();
				shape.curves = p.curves;
				const holes = isAHole.filter( h => h.isHole && h.for === p.identifier );
				holes.forEach( h => {

					const hole = simplePaths[ h.identifier ];
					const path = new Path();
					path.curves = hole.curves;
					shape.holes.push( path );

				} );
				shapesToReturn.push( shape );

			}

		} );

		return shapesToReturn;

	}

	/**
	 * Returns a stroke style object from the given parameters.
	 *
	 * @param {number} [width=1] - The stroke width.
	 * @param {string} [color='#000'] - The stroke color, as  returned by {@link Color#getStyle}.
	 * @param {'round'|'bevel'|'miter'|'miter-limit'} [lineJoin='miter'] - The line join style.
	 * @param {'round'|'square'|'butt'} [lineCap='butt'] - The line cap style.
	 * @param {number} [miterLimit=4] - Maximum join length, in multiples of the `width` parameter (join is truncated if it exceeds that distance).
	 * @return {Object} The style object.
	 */
	static getStrokeStyle( width, color, lineJoin, lineCap, miterLimit ) {

		width = width !== undefined ? width : 1;
		color = color !== undefined ? color : '#000';
		lineJoin = lineJoin !== undefined ? lineJoin : 'miter';
		lineCap = lineCap !== undefined ? lineCap : 'butt';
		miterLimit = miterLimit !== undefined ? miterLimit : 4;

		return {
			strokeColor: color,
			strokeWidth: width,
			strokeLineJoin: lineJoin,
			strokeLineCap: lineCap,
			strokeMiterLimit: miterLimit
		};

	}

	/**
	 * Creates a stroke from an array of points.
	 *
	 * @param {Array<Vector2>} points - The points in 2D space. Minimum 2 points. The path can be open or closed (last point equals to first point).
	 * @param {Object} style - Object with SVG properties as returned by `SVGLoader.getStrokeStyle()`, or `SVGLoader.parse()` in the `path.userData.style` object.
	 * @param {number} [arcDivisions=12] - Arc divisions for round joins and endcaps.
	 * @param {number} [minDistance=0.001] - Points closer to this distance will be merged.
	 * @return {?BufferGeometry} The stroke geometry. UV coordinates are generated ('u' along path. 'v' across it, from left to right).
	 * Returns `null` if not geometry was generated.
	 */
	static pointsToStroke( points, style, arcDivisions, minDistance ) {

		const vertices = [];
		const normals = [];
		const uvs = [];

		if ( SVGLoader.pointsToStrokeWithBuffers( points, style, arcDivisions, minDistance, vertices, normals, uvs ) === 0 ) {

			return null;

		}

		const geometry = new BufferGeometry();
		geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
		geometry.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );
		geometry.setAttribute( 'uv', new Float32BufferAttribute( uvs, 2 ) );

		return geometry;

	}

	/**
	 * Creates a stroke from an array of points.
	 *
	 * @param {Array<Vector2>} points - The points in 2D space. Minimum 2 points.
	 * @param {Object} style - Object with SVG properties as returned by `SVGLoader.getStrokeStyle()`, or `SVGLoader.parse()` in the `path.userData.style` object.
	 * @param {number} [arcDivisions=12] - Arc divisions for round joins and endcaps.
	 * @param {number} [minDistance=0.001] - Points closer to this distance will be merged.
	 * @param {Array<number>} vertices - An array holding vertices.
	 * @param {Array<number>} normals - An array holding normals.
	 * @param {Array<number>} uvs - An array holding uvs.
	 * @param {number} [vertexOffset=0] - The vertex offset.
	 * @return {number} The number of vertices.
	 */
	static pointsToStrokeWithBuffers( points, style, arcDivisions, minDistance, vertices, normals, uvs, vertexOffset ) {

		// This function can be called to update existing arrays or buffers.
		// Accepts same parameters as pointsToStroke, plus the buffers and optional offset.
		// Param vertexOffset: Offset vertices to start writing in the buffers (3 elements/vertex for vertices and normals, and 2 elements/vertex for uvs)
		// Returns number of written vertices / normals / uvs pairs
		// if 'vertices' parameter is undefined no triangles will be generated, but the returned vertices count will still be valid (useful to preallocate the buffers)
		// 'normals' and 'uvs' buffers are optional

		const tempV2_1 = new Vector2();
		const tempV2_2 = new Vector2();
		const tempV2_3 = new Vector2();
		const tempV2_4 = new Vector2();
		const tempV2_5 = new Vector2();
		const tempV2_6 = new Vector2();
		const tempV2_7 = new Vector2();
		const lastPointL = new Vector2();
		const lastPointR = new Vector2();
		const point0L = new Vector2();
		const point0R = new Vector2();
		const currentPointL = new Vector2();
		const currentPointR = new Vector2();
		const nextPointL = new Vector2();
		const nextPointR = new Vector2();
		const innerPoint = new Vector2();
		const outerPoint = new Vector2();

		arcDivisions = arcDivisions !== undefined ? arcDivisions : 12;
		minDistance = minDistance !== undefined ? minDistance : 0.001;
		vertexOffset = vertexOffset !== undefined ? vertexOffset : 0;

		// First ensure there are no duplicated points
		points = removeDuplicatedPoints( points );

		const numPoints = points.length;

		if ( numPoints < 2 ) return 0;

		const isClosed = points[ 0 ].equals( points[ numPoints - 1 ] );

		let currentPoint;
		let previousPoint = points[ 0 ];
		let nextPoint;

		const strokeWidth2 = style.strokeWidth / 2;

		const deltaU = 1 / ( numPoints - 1 );
		let u0 = 0, u1;

		let innerSideModified;
		let joinIsOnLeftSide;
		let isMiter;
		let initialJoinIsOnLeftSide = false;

		let numVertices = 0;
		let currentCoordinate = vertexOffset * 3;
		let currentCoordinateUV = vertexOffset * 2;

		// Get initial left and right stroke points
		getNormal( points[ 0 ], points[ 1 ], tempV2_1 ).multiplyScalar( strokeWidth2 );
		lastPointL.copy( points[ 0 ] ).sub( tempV2_1 );
		lastPointR.copy( points[ 0 ] ).add( tempV2_1 );
		point0L.copy( lastPointL );
		point0R.copy( lastPointR );

		for ( let iPoint = 1; iPoint < numPoints; iPoint ++ ) {

			currentPoint = points[ iPoint ];

			// Get next point
			if ( iPoint === numPoints - 1 ) {

				if ( isClosed ) {

					// Skip duplicated initial point
					nextPoint = points[ 1 ];

				} else nextPoint = undefined;

			} else {

				nextPoint = points[ iPoint + 1 ];

			}

			// Normal of previous segment in tempV2_1
			const normal1 = tempV2_1;
			getNormal( previousPoint, currentPoint, normal1 );

			tempV2_3.copy( normal1 ).multiplyScalar( strokeWidth2 );
			currentPointL.copy( currentPoint ).sub( tempV2_3 );
			currentPointR.copy( currentPoint ).add( tempV2_3 );

			u1 = u0 + deltaU;

			innerSideModified = false;

			if ( nextPoint !== undefined ) {

				// Normal of next segment in tempV2_2
				getNormal( currentPoint, nextPoint, tempV2_2 );

				tempV2_3.copy( tempV2_2 ).multiplyScalar( strokeWidth2 );
				nextPointL.copy( currentPoint ).sub( tempV2_3 );
				nextPointR.copy( currentPoint ).add( tempV2_3 );

				joinIsOnLeftSide = true;
				tempV2_3.subVectors( nextPoint, previousPoint );
				if ( normal1.dot( tempV2_3 ) < 0 ) {

					joinIsOnLeftSide = false;

				}

				if ( iPoint === 1 ) initialJoinIsOnLeftSide = joinIsOnLeftSide;

				tempV2_3.subVectors( nextPoint, currentPoint );
				tempV2_3.normalize();
				const dot = Math.abs( normal1.dot( tempV2_3 ) );

				// If path is straight, don't create join
				if ( dot > Number.EPSILON ) {

					// Compute inner and outer segment intersections
					const miterSide = strokeWidth2 / dot;
					tempV2_3.multiplyScalar( - miterSide );
					tempV2_4.subVectors( currentPoint, previousPoint );
					tempV2_5.copy( tempV2_4 ).setLength( miterSide ).add( tempV2_3 );
					innerPoint.copy( tempV2_5 ).negate();
					const miterLength2 = tempV2_5.length();
					const segmentLengthPrev = tempV2_4.length();
					tempV2_4.divideScalar( segmentLengthPrev );
					tempV2_6.subVectors( nextPoint, currentPoint );
					const segmentLengthNext = tempV2_6.length();
					tempV2_6.divideScalar( segmentLengthNext );
					// Check that previous and next segments doesn't overlap with the innerPoint of intersection
					if ( tempV2_4.dot( innerPoint ) < segmentLengthPrev && tempV2_6.dot( innerPoint ) < segmentLengthNext ) {

						innerSideModified = true;

					}

					outerPoint.copy( tempV2_5 ).add( currentPoint );
					innerPoint.add( currentPoint );

					isMiter = false;

					if ( innerSideModified ) {

						if ( joinIsOnLeftSide ) {

							nextPointR.copy( innerPoint );
							currentPointR.copy( innerPoint );

						} else {

							nextPointL.copy( innerPoint );
							currentPointL.copy( innerPoint );

						}

					} else {

						// The segment triangles are generated here if there was overlapping

						makeSegmentTriangles();

					}

					switch ( style.strokeLineJoin ) {

						case 'bevel':

							makeSegmentWithBevelJoin( joinIsOnLeftSide, innerSideModified, u1 );

							break;

						case 'round':

							// Segment triangles

							createSegmentTrianglesWithMiddleSection( joinIsOnLeftSide, innerSideModified );

							// Join triangles

							if ( joinIsOnLeftSide ) {

								makeCircularSector( currentPoint, currentPointL, nextPointL, u1, 0 );

							} else {

								makeCircularSector( currentPoint, nextPointR, currentPointR, u1, 1 );

							}

							break;

						case 'miter':
						case 'miter-clip':
						default:

							const miterFraction = ( strokeWidth2 * style.strokeMiterLimit ) / miterLength2;

							if ( miterFraction < 1 ) {

								// The join miter length exceeds the miter limit

								if ( style.strokeLineJoin !== 'miter-clip' ) {

									makeSegmentWithBevelJoin( joinIsOnLeftSide, innerSideModified, u1 );
									break;

								} else {

									// Segment triangles

									createSegmentTrianglesWithMiddleSection( joinIsOnLeftSide, innerSideModified );

									// Miter-clip join triangles

									if ( joinIsOnLeftSide ) {

										tempV2_6.subVectors( outerPoint, currentPointL ).multiplyScalar( miterFraction ).add( currentPointL );
										tempV2_7.subVectors( outerPoint, nextPointL ).multiplyScalar( miterFraction ).add( nextPointL );

										addVertex( currentPointL, u1, 0 );
										addVertex( tempV2_6, u1, 0 );
										addVertex( currentPoint, u1, 0.5 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( tempV2_6, u1, 0 );
										addVertex( tempV2_7, u1, 0 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( tempV2_7, u1, 0 );
										addVertex( nextPointL, u1, 0 );

									} else {

										tempV2_6.subVectors( outerPoint, currentPointR ).multiplyScalar( miterFraction ).add( currentPointR );
										tempV2_7.subVectors( outerPoint, nextPointR ).multiplyScalar( miterFraction ).add( nextPointR );

										addVertex( currentPointR, u1, 1 );
										addVertex( tempV2_6, u1, 1 );
										addVertex( currentPoint, u1, 0.5 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( tempV2_6, u1, 1 );
										addVertex( tempV2_7, u1, 1 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( tempV2_7, u1, 1 );
										addVertex( nextPointR, u1, 1 );

									}

								}

							} else {

								// Miter join segment triangles

								if ( innerSideModified ) {

									// Optimized segment + join triangles

									if ( joinIsOnLeftSide ) {

										addVertex( lastPointR, u0, 1 );
										addVertex( lastPointL, u0, 0 );
										addVertex( outerPoint, u1, 0 );

										addVertex( lastPointR, u0, 1 );
										addVertex( outerPoint, u1, 0 );
										addVertex( innerPoint, u1, 1 );

									} else {

										addVertex( lastPointR, u0, 1 );
										addVertex( lastPointL, u0, 0 );
										addVertex( outerPoint, u1, 1 );

										addVertex( lastPointL, u0, 0 );
										addVertex( innerPoint, u1, 0 );
										addVertex( outerPoint, u1, 1 );

									}


									if ( joinIsOnLeftSide ) {

										nextPointL.copy( outerPoint );

									} else {

										nextPointR.copy( outerPoint );

									}


								} else {

									// Add extra miter join triangles

									if ( joinIsOnLeftSide ) {

										addVertex( currentPointL, u1, 0 );
										addVertex( outerPoint, u1, 0 );
										addVertex( currentPoint, u1, 0.5 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( outerPoint, u1, 0 );
										addVertex( nextPointL, u1, 0 );

									} else {

										addVertex( currentPointR, u1, 1 );
										addVertex( outerPoint, u1, 1 );
										addVertex( currentPoint, u1, 0.5 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( outerPoint, u1, 1 );
										addVertex( nextPointR, u1, 1 );

									}

								}

								isMiter = true;

							}

							break;

					}

				} else {

					// The segment triangles are generated here when two consecutive points are collinear

					makeSegmentTriangles();

				}

			} else {

				// The segment triangles are generated here if it is the ending segment

				makeSegmentTriangles();

			}

			if ( ! isClosed && iPoint === numPoints - 1 ) {

				// Start line endcap
				addCapGeometry( points[ 0 ], point0L, point0R, joinIsOnLeftSide, true, u0 );

			}

			// Increment loop variables

			u0 = u1;

			previousPoint = currentPoint;

			lastPointL.copy( nextPointL );
			lastPointR.copy( nextPointR );

		}

		if ( ! isClosed ) {

			// Ending line endcap
			addCapGeometry( currentPoint, currentPointL, currentPointR, joinIsOnLeftSide, false, u1 );

		} else if ( innerSideModified && vertices ) {

			// Modify path first segment vertices to adjust to the segments inner and outer intersections

			let lastOuter = outerPoint;
			let lastInner = innerPoint;

			if ( initialJoinIsOnLeftSide !== joinIsOnLeftSide ) {

				lastOuter = innerPoint;
				lastInner = outerPoint;

			}

			if ( joinIsOnLeftSide ) {

				if ( isMiter || initialJoinIsOnLeftSide ) {

					lastInner.toArray( vertices, 0 * 3 );
					lastInner.toArray( vertices, 3 * 3 );

					if ( isMiter ) {

						lastOuter.toArray( vertices, 1 * 3 );

					}

				}

			} else {

				if ( isMiter || ! initialJoinIsOnLeftSide ) {

					lastInner.toArray( vertices, 1 * 3 );
					lastInner.toArray( vertices, 3 * 3 );

					if ( isMiter ) {

						lastOuter.toArray( vertices, 0 * 3 );

					}

				}

			}

		}

		return numVertices;

		// -- End of algorithm

		// -- Functions

		function getNormal( p1, p2, result ) {

			result.subVectors( p2, p1 );
			return result.set( - result.y, result.x ).normalize();

		}

		function addVertex( position, u, v ) {

			if ( vertices ) {

				vertices[ currentCoordinate ] = position.x;
				vertices[ currentCoordinate + 1 ] = position.y;
				vertices[ currentCoordinate + 2 ] = 0;

				if ( normals ) {

					normals[ currentCoordinate ] = 0;
					normals[ currentCoordinate + 1 ] = 0;
					normals[ currentCoordinate + 2 ] = 1;

				}

				currentCoordinate += 3;

				if ( uvs ) {

					uvs[ currentCoordinateUV ] = u;
					uvs[ currentCoordinateUV + 1 ] = v;

					currentCoordinateUV += 2;

				}

			}

			numVertices += 3;

		}

		function makeCircularSector( center, p1, p2, u, v ) {

			// param p1, p2: Points in the circle arc.
			// p1 and p2 are in clockwise direction.

			tempV2_1.copy( p1 ).sub( center ).normalize();
			tempV2_2.copy( p2 ).sub( center ).normalize();

			let angle = Math.PI;
			const dot = tempV2_1.dot( tempV2_2 );
			if ( Math.abs( dot ) < 1 ) angle = Math.abs( Math.acos( dot ) );

			angle /= arcDivisions;

			tempV2_3.copy( p1 );

			for ( let i = 0, il = arcDivisions - 1; i < il; i ++ ) {

				tempV2_4.copy( tempV2_3 ).rotateAround( center, angle );

				addVertex( tempV2_3, u, v );
				addVertex( tempV2_4, u, v );
				addVertex( center, u, 0.5 );

				tempV2_3.copy( tempV2_4 );

			}

			addVertex( tempV2_4, u, v );
			addVertex( p2, u, v );
			addVertex( center, u, 0.5 );

		}

		function makeSegmentTriangles() {

			addVertex( lastPointR, u0, 1 );
			addVertex( lastPointL, u0, 0 );
			addVertex( currentPointL, u1, 0 );

			addVertex( lastPointR, u0, 1 );
			addVertex( currentPointL, u1, 0 );
			addVertex( currentPointR, u1, 1 );

		}

		function makeSegmentWithBevelJoin( joinIsOnLeftSide, innerSideModified, u ) {

			if ( innerSideModified ) {

				// Optimized segment + bevel triangles

				if ( joinIsOnLeftSide ) {

					// Path segments triangles

					addVertex( lastPointR, u0, 1 );
					addVertex( lastPointL, u0, 0 );
					addVertex( currentPointL, u1, 0 );

					addVertex( lastPointR, u0, 1 );
					addVertex( currentPointL, u1, 0 );
					addVertex( innerPoint, u1, 1 );

					// Bevel join triangle

					addVertex( currentPointL, u, 0 );
					addVertex( nextPointL, u, 0 );
					addVertex( innerPoint, u, 0.5 );

				} else {

					// Path segments triangles

					addVertex( lastPointR, u0, 1 );
					addVertex( lastPointL, u0, 0 );
					addVertex( currentPointR, u1, 1 );

					addVertex( lastPointL, u0, 0 );
					addVertex( innerPoint, u1, 0 );
					addVertex( currentPointR, u1, 1 );

					// Bevel join triangle

					addVertex( currentPointR, u, 1 );
					addVertex( innerPoint, u, 0 );
					addVertex( nextPointR, u, 1 );

				}

			} else {

				// Bevel join triangle. The segment triangles are done in the main loop

				if ( joinIsOnLeftSide ) {

					addVertex( currentPointL, u, 0 );
					addVertex( nextPointL, u, 0 );
					addVertex( currentPoint, u, 0.5 );

				} else {

					addVertex( currentPointR, u, 1 );
					addVertex( nextPointR, u, 0 );
					addVertex( currentPoint, u, 0.5 );

				}

			}

		}

		function createSegmentTrianglesWithMiddleSection( joinIsOnLeftSide, innerSideModified ) {

			if ( innerSideModified ) {

				if ( joinIsOnLeftSide ) {

					addVertex( lastPointR, u0, 1 );
					addVertex( lastPointL, u0, 0 );
					addVertex( currentPointL, u1, 0 );

					addVertex( lastPointR, u0, 1 );
					addVertex( currentPointL, u1, 0 );
					addVertex( innerPoint, u1, 1 );

					addVertex( currentPointL, u0, 0 );
					addVertex( currentPoint, u1, 0.5 );
					addVertex( innerPoint, u1, 1 );

					addVertex( currentPoint, u1, 0.5 );
					addVertex( nextPointL, u0, 0 );
					addVertex( innerPoint, u1, 1 );

				} else {

					addVertex( lastPointR, u0, 1 );
					addVertex( lastPointL, u0, 0 );
					addVertex( currentPointR, u1, 1 );

					addVertex( lastPointL, u0, 0 );
					addVertex( innerPoint, u1, 0 );
					addVertex( currentPointR, u1, 1 );

					addVertex( currentPointR, u0, 1 );
					addVertex( innerPoint, u1, 0 );
					addVertex( currentPoint, u1, 0.5 );

					addVertex( currentPoint, u1, 0.5 );
					addVertex( innerPoint, u1, 0 );
					addVertex( nextPointR, u0, 1 );

				}

			}

		}

		function addCapGeometry( center, p1, p2, joinIsOnLeftSide, start, u ) {

			// param center: End point of the path
			// param p1, p2: Left and right cap points

			switch ( style.strokeLineCap ) {

				case 'round':

					if ( start ) {

						makeCircularSector( center, p2, p1, u, 0.5 );

					} else {

						makeCircularSector( center, p1, p2, u, 0.5 );

					}

					break;

				case 'square':

					if ( start ) {

						tempV2_1.subVectors( p1, center );
						tempV2_2.set( tempV2_1.y, - tempV2_1.x );

						tempV2_3.addVectors( tempV2_1, tempV2_2 ).add( center );
						tempV2_4.subVectors( tempV2_2, tempV2_1 ).add( center );

						// Modify already existing vertices
						if ( joinIsOnLeftSide ) {

							tempV2_3.toArray( vertices, 1 * 3 );
							tempV2_4.toArray( vertices, 0 * 3 );
							tempV2_4.toArray( vertices, 3 * 3 );

						} else {

							tempV2_3.toArray( vertices, 1 * 3 );
							// using tempV2_4 to update 3rd vertex if the uv.y of 3rd vertex is 1
							uvs[ 3 * 2 + 1 ] === 1 ? tempV2_4.toArray( vertices, 3 * 3 ) : tempV2_3.toArray( vertices, 3 * 3 );
							tempV2_4.toArray( vertices, 0 * 3 );

						}

					} else {

						tempV2_1.subVectors( p2, center );
						tempV2_2.set( tempV2_1.y, - tempV2_1.x );

						tempV2_3.addVectors( tempV2_1, tempV2_2 ).add( center );
						tempV2_4.subVectors( tempV2_2, tempV2_1 ).add( center );

						const vl = vertices.length;

						// Modify already existing vertices
						if ( joinIsOnLeftSide ) {

							tempV2_3.toArray( vertices, vl - 1 * 3 );
							tempV2_4.toArray( vertices, vl - 2 * 3 );
							tempV2_4.toArray( vertices, vl - 4 * 3 );

						} else {

							tempV2_4.toArray( vertices, vl - 2 * 3 );
							tempV2_3.toArray( vertices, vl - 1 * 3 );
							tempV2_4.toArray( vertices, vl - 4 * 3 );

						}

					}

					break;

				case 'butt':
				default:

					// Nothing to do here
					break;

			}

		}

		function removeDuplicatedPoints( points ) {

			// Creates a new array if necessary with duplicated points removed.
			// This does not remove duplicated initial and ending points of a closed path.

			let dupPoints = false;
			for ( let i = 1, n = points.length - 1; i < n; i ++ ) {

				if ( points[ i ].distanceTo( points[ i + 1 ] ) < minDistance ) {

					dupPoints = true;
					break;

				}

			}

			if ( ! dupPoints ) return points;

			const newPoints = [];
			newPoints.push( points[ 0 ] );

			for ( let i = 1, n = points.length - 1; i < n; i ++ ) {

				if ( points[ i ].distanceTo( points[ i + 1 ] ) >= minDistance ) {

					newPoints.push( points[ i ] );

				}

			}

			newPoints.push( points[ points.length - 1 ] );

			return newPoints;

		}

	}


}
```
</details>

#### Methods

##### `load(url: string, onLoad: (arg0: { paths: ShapePath[]; xml: string; }) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const scope = this;

		const loader = new FileLoader( scope.manager );
		loader.setPath( scope.path );
		loader.setRequestHeader( scope.requestHeader );
		loader.setWithCredentials( scope.withCredentials );
		loader.load( url, function ( text ) {

			try {

				onLoad( scope.parse( text ) );

			} catch ( e ) {

				if ( onError ) {

					onError( e );

				} else {

					console.error( e );

				}

				scope.manager.itemError( url );

			}

		}, onProgress, onError );

	}
```
</details>

##### `parse(text: string): { paths: ShapePath[]; xml: string; }`

<details><summary>Code</summary>

```ts
parse( text ) {

		const scope = this;

		function parseNode( node, style ) {

			if ( node.nodeType !== 1 ) return;

			const transform = getNodeTransform( node );

			let isDefsNode = false;

			let path = null;

			switch ( node.nodeName ) {

				case 'svg':
					style = parseStyle( node, style );
					break;

				case 'style':
					parseCSSStylesheet( node );
					break;

				case 'g':
					style = parseStyle( node, style );
					break;

				case 'path':
					style = parseStyle( node, style );
					if ( node.hasAttribute( 'd' ) ) path = parsePathNode( node );
					break;

				case 'rect':
					style = parseStyle( node, style );
					path = parseRectNode( node );
					break;

				case 'polygon':
					style = parseStyle( node, style );
					path = parsePolygonNode( node );
					break;

				case 'polyline':
					style = parseStyle( node, style );
					path = parsePolylineNode( node );
					break;

				case 'circle':
					style = parseStyle( node, style );
					path = parseCircleNode( node );
					break;

				case 'ellipse':
					style = parseStyle( node, style );
					path = parseEllipseNode( node );
					break;

				case 'line':
					style = parseStyle( node, style );
					path = parseLineNode( node );
					break;

				case 'defs':
					isDefsNode = true;
					break;

				case 'use':
					style = parseStyle( node, style );

					const href = node.getAttributeNS( 'http://www.w3.org/1999/xlink', 'href' ) || '';
					const usedNodeId = href.substring( 1 );
					const usedNode = node.viewportElement.getElementById( usedNodeId );
					if ( usedNode ) {

						parseNode( usedNode, style );

					} else {

						console.warn( 'SVGLoader: \'use node\' references non-existent node id: ' + usedNodeId );

					}

					break;

				default:
					// console.log( node );

			}

			if ( path ) {

				if ( style.fill !== undefined && style.fill !== 'none' ) {

					path.color.setStyle( style.fill, COLOR_SPACE_SVG );

				}

				transformPath( path, currentTransform );

				paths.push( path );

				path.userData = { node: node, style: style };

			}

			const childNodes = node.childNodes;

			for ( let i = 0; i < childNodes.length; i ++ ) {

				const node = childNodes[ i ];

				if ( isDefsNode && node.nodeName !== 'style' && node.nodeName !== 'defs' ) {

					// Ignore everything in defs except CSS style definitions
					// and nested defs, because it is OK by the standard to have
					// <style/> there.
					continue;

				}

				parseNode( node, style );

			}


			if ( transform ) {

				transformStack.pop();

				if ( transformStack.length > 0 ) {

					currentTransform.copy( transformStack[ transformStack.length - 1 ] );

				} else {

					currentTransform.identity();

				}

			}

		}

		function parsePathNode( node ) {

			const path = new ShapePath();

			const point = new Vector2();
			const control = new Vector2();

			const firstPoint = new Vector2();
			let isFirstPoint = true;
			let doSetFirstPoint = false;

			const d = node.getAttribute( 'd' );

			if ( d === '' || d === 'none' ) return null;

			// console.log( d );

			const commands = d.match( /[a-df-z][^a-df-z]*/ig );

			for ( let i = 0, l = commands.length; i < l; i ++ ) {

				const command = commands[ i ];

				const type = command.charAt( 0 );
				const data = command.slice( 1 ).trim();

				if ( isFirstPoint === true ) {

					doSetFirstPoint = true;
					isFirstPoint = false;

				}

				let numbers;

				switch ( type ) {

					case 'M':
						numbers = parseFloats( data );
						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							point.x = numbers[ j + 0 ];
							point.y = numbers[ j + 1 ];
							control.x = point.x;
							control.y = point.y;

							if ( j === 0 ) {

								path.moveTo( point.x, point.y );

							} else {

								path.lineTo( point.x, point.y );

							}

							if ( j === 0 ) firstPoint.copy( point );

						}

						break;

					case 'H':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j ++ ) {

							point.x = numbers[ j ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'V':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j ++ ) {

							point.y = numbers[ j ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'L':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							point.x = numbers[ j + 0 ];
							point.y = numbers[ j + 1 ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'C':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 6 ) {

							path.bezierCurveTo(
								numbers[ j + 0 ],
								numbers[ j + 1 ],
								numbers[ j + 2 ],
								numbers[ j + 3 ],
								numbers[ j + 4 ],
								numbers[ j + 5 ]
							);
							control.x = numbers[ j + 2 ];
							control.y = numbers[ j + 3 ];
							point.x = numbers[ j + 4 ];
							point.y = numbers[ j + 5 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'S':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 4 ) {

							path.bezierCurveTo(
								getReflection( point.x, control.x ),
								getReflection( point.y, control.y ),
								numbers[ j + 0 ],
								numbers[ j + 1 ],
								numbers[ j + 2 ],
								numbers[ j + 3 ]
							);
							control.x = numbers[ j + 0 ];
							control.y = numbers[ j + 1 ];
							point.x = numbers[ j + 2 ];
							point.y = numbers[ j + 3 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'Q':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 4 ) {

							path.quadraticCurveTo(
								numbers[ j + 0 ],
								numbers[ j + 1 ],
								numbers[ j + 2 ],
								numbers[ j + 3 ]
							);
							control.x = numbers[ j + 0 ];
							control.y = numbers[ j + 1 ];
							point.x = numbers[ j + 2 ];
							point.y = numbers[ j + 3 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'T':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							const rx = getReflection( point.x, control.x );
							const ry = getReflection( point.y, control.y );
							path.quadraticCurveTo(
								rx,
								ry,
								numbers[ j + 0 ],
								numbers[ j + 1 ]
							);
							control.x = rx;
							control.y = ry;
							point.x = numbers[ j + 0 ];
							point.y = numbers[ j + 1 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'A':
						numbers = parseFloats( data, [ 3, 4 ], 7 );

						for ( let j = 0, jl = numbers.length; j < jl; j += 7 ) {

							// skip command if start point == end point
							if ( numbers[ j + 5 ] == point.x && numbers[ j + 6 ] == point.y ) continue;

							const start = point.clone();
							point.x = numbers[ j + 5 ];
							point.y = numbers[ j + 6 ];
							control.x = point.x;
							control.y = point.y;
							parseArcCommand(
								path, numbers[ j ], numbers[ j + 1 ], numbers[ j + 2 ], numbers[ j + 3 ], numbers[ j + 4 ], start, point
							);

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'm':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							point.x += numbers[ j + 0 ];
							point.y += numbers[ j + 1 ];
							control.x = point.x;
							control.y = point.y;

							if ( j === 0 ) {

								path.moveTo( point.x, point.y );

							} else {

								path.lineTo( point.x, point.y );

							}

							if ( j === 0 ) firstPoint.copy( point );

						}

						break;

					case 'h':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j ++ ) {

							point.x += numbers[ j ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'v':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j ++ ) {

							point.y += numbers[ j ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'l':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							point.x += numbers[ j + 0 ];
							point.y += numbers[ j + 1 ];
							control.x = point.x;
							control.y = point.y;
							path.lineTo( point.x, point.y );

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'c':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 6 ) {

							path.bezierCurveTo(
								point.x + numbers[ j + 0 ],
								point.y + numbers[ j + 1 ],
								point.x + numbers[ j + 2 ],
								point.y + numbers[ j + 3 ],
								point.x + numbers[ j + 4 ],
								point.y + numbers[ j + 5 ]
							);
							control.x = point.x + numbers[ j + 2 ];
							control.y = point.y + numbers[ j + 3 ];
							point.x += numbers[ j + 4 ];
							point.y += numbers[ j + 5 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 's':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 4 ) {

							path.bezierCurveTo(
								getReflection( point.x, control.x ),
								getReflection( point.y, control.y ),
								point.x + numbers[ j + 0 ],
								point.y + numbers[ j + 1 ],
								point.x + numbers[ j + 2 ],
								point.y + numbers[ j + 3 ]
							);
							control.x = point.x + numbers[ j + 0 ];
							control.y = point.y + numbers[ j + 1 ];
							point.x += numbers[ j + 2 ];
							point.y += numbers[ j + 3 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'q':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 4 ) {

							path.quadraticCurveTo(
								point.x + numbers[ j + 0 ],
								point.y + numbers[ j + 1 ],
								point.x + numbers[ j + 2 ],
								point.y + numbers[ j + 3 ]
							);
							control.x = point.x + numbers[ j + 0 ];
							control.y = point.y + numbers[ j + 1 ];
							point.x += numbers[ j + 2 ];
							point.y += numbers[ j + 3 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 't':
						numbers = parseFloats( data );

						for ( let j = 0, jl = numbers.length; j < jl; j += 2 ) {

							const rx = getReflection( point.x, control.x );
							const ry = getReflection( point.y, control.y );
							path.quadraticCurveTo(
								rx,
								ry,
								point.x + numbers[ j + 0 ],
								point.y + numbers[ j + 1 ]
							);
							control.x = rx;
							control.y = ry;
							point.x = point.x + numbers[ j + 0 ];
							point.y = point.y + numbers[ j + 1 ];

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'a':
						numbers = parseFloats( data, [ 3, 4 ], 7 );

						for ( let j = 0, jl = numbers.length; j < jl; j += 7 ) {

							// skip command if no displacement
							if ( numbers[ j + 5 ] == 0 && numbers[ j + 6 ] == 0 ) continue;

							const start = point.clone();
							point.x += numbers[ j + 5 ];
							point.y += numbers[ j + 6 ];
							control.x = point.x;
							control.y = point.y;
							parseArcCommand(
								path, numbers[ j ], numbers[ j + 1 ], numbers[ j + 2 ], numbers[ j + 3 ], numbers[ j + 4 ], start, point
							);

							if ( j === 0 && doSetFirstPoint === true ) firstPoint.copy( point );

						}

						break;

					case 'Z':
					case 'z':
						path.currentPath.autoClose = true;

						if ( path.currentPath.curves.length > 0 ) {

							// Reset point to beginning of Path
							point.copy( firstPoint );
							path.currentPath.currentPoint.copy( point );
							isFirstPoint = true;

						}

						break;

					default:
						console.warn( command );

				}

				// console.log( type, parseFloats( data ), parseFloats( data ).length  )

				doSetFirstPoint = false;

			}

			return path;

		}

		function parseCSSStylesheet( node ) {

			if ( ! node.sheet || ! node.sheet.cssRules || ! node.sheet.cssRules.length ) return;

			for ( let i = 0; i < node.sheet.cssRules.length; i ++ ) {

				const stylesheet = node.sheet.cssRules[ i ];

				if ( stylesheet.type !== 1 ) continue;

				const selectorList = stylesheet.selectorText
					.split( /,/gm )
					.filter( Boolean )
					.map( i => i.trim() );

				for ( let j = 0; j < selectorList.length; j ++ ) {

					// Remove empty rules
					const definitions = Object.fromEntries(
						Object.entries( stylesheet.style ).filter( ( [ , v ] ) => v !== '' )
					);

					stylesheets[ selectorList[ j ] ] = Object.assign(
						stylesheets[ selectorList[ j ] ] || {},
						definitions
					);

				}

			}

		}

		/**
		 * https://www.w3.org/TR/SVG/implnote.html#ArcImplementationNotes
		 * https://mortoray.com/2017/02/16/rendering-an-svg-elliptical-arc-as-bezier-curves/ Appendix: Endpoint to center arc conversion
		 * From
		 * rx ry x-axis-rotation large-arc-flag sweep-flag x y
		 * To
		 * aX, aY, xRadius, yRadius, aStartAngle, aEndAngle, aClockwise, aRotation
		 */

		function parseArcCommand( path, rx, ry, x_axis_rotation, large_arc_flag, sweep_flag, start, end ) {

			if ( rx == 0 || ry == 0 ) {

				// draw a line if either of the radii == 0
				path.lineTo( end.x, end.y );
				return;

			}

			x_axis_rotation = x_axis_rotation * Math.PI / 180;

			// Ensure radii are positive
			rx = Math.abs( rx );
			ry = Math.abs( ry );

			// Compute (x1', y1')
			const dx2 = ( start.x - end.x ) / 2.0;
			const dy2 = ( start.y - end.y ) / 2.0;
			const x1p = Math.cos( x_axis_rotation ) * dx2 + Math.sin( x_axis_rotation ) * dy2;
			const y1p = - Math.sin( x_axis_rotation ) * dx2 + Math.cos( x_axis_rotation ) * dy2;

			// Compute (cx', cy')
			let rxs = rx * rx;
			let rys = ry * ry;
			const x1ps = x1p * x1p;
			const y1ps = y1p * y1p;

			// Ensure radii are large enough
			const cr = x1ps / rxs + y1ps / rys;

			if ( cr > 1 ) {

				// scale up rx,ry equally so cr == 1
				const s = Math.sqrt( cr );
				rx = s * rx;
				ry = s * ry;
				rxs = rx * rx;
				rys = ry * ry;

			}

			const dq = ( rxs * y1ps + rys * x1ps );
			const pq = ( rxs * rys - dq ) / dq;
			let q = Math.sqrt( Math.max( 0, pq ) );
			if ( large_arc_flag === sweep_flag ) q = - q;
			const cxp = q * rx * y1p / ry;
			const cyp = - q * ry * x1p / rx;

			// Step 3: Compute (cx, cy) from (cx', cy')
			const cx = Math.cos( x_axis_rotation ) * cxp - Math.sin( x_axis_rotation ) * cyp + ( start.x + end.x ) / 2;
			const cy = Math.sin( x_axis_rotation ) * cxp + Math.cos( x_axis_rotation ) * cyp + ( start.y + end.y ) / 2;

			// Step 4: Compute θ1 and Δθ
			const theta = svgAngle( 1, 0, ( x1p - cxp ) / rx, ( y1p - cyp ) / ry );
			const delta = svgAngle( ( x1p - cxp ) / rx, ( y1p - cyp ) / ry, ( - x1p - cxp ) / rx, ( - y1p - cyp ) / ry ) % ( Math.PI * 2 );

			path.currentPath.absellipse( cx, cy, rx, ry, theta, theta + delta, sweep_flag === 0, x_axis_rotation );

		}

		function svgAngle( ux, uy, vx, vy ) {

			const dot = ux * vx + uy * vy;
			const len = Math.sqrt( ux * ux + uy * uy ) * Math.sqrt( vx * vx + vy * vy );
			let ang = Math.acos( Math.max( - 1, Math.min( 1, dot / len ) ) ); // floating point precision, slightly over values appear
			if ( ( ux * vy - uy * vx ) < 0 ) ang = - ang;
			return ang;

		}

		/*
		* According to https://www.w3.org/TR/SVG/shapes.html#RectElementRXAttribute
		* rounded corner should be rendered to elliptical arc, but bezier curve does the job well enough
		*/

		function parseRectNode( node ) {

			const x = parseFloatWithUnits( node.getAttribute( 'x' ) || 0 );
			const y = parseFloatWithUnits( node.getAttribute( 'y' ) || 0 );
			const rx = parseFloatWithUnits( node.getAttribute( 'rx' ) || node.getAttribute( 'ry' ) || 0 );
			const ry = parseFloatWithUnits( node.getAttribute( 'ry' ) || node.getAttribute( 'rx' ) || 0 );
			const w = parseFloatWithUnits( node.getAttribute( 'width' ) );
			const h = parseFloatWithUnits( node.getAttribute( 'height' ) );

			// Ellipse arc to Bezier approximation Coefficient (Inversed). See:
			// https://spencermortensen.com/articles/bezier-circle/
			const bci = 1 - 0.551915024494;

			const path = new ShapePath();

			// top left
			path.moveTo( x + rx, y );

			// top right
			path.lineTo( x + w - rx, y );
			if ( rx !== 0 || ry !== 0 ) {

				path.bezierCurveTo(
					x + w - rx * bci,
					y,
					x + w,
					y + ry * bci,
					x + w,
					y + ry
				);

			}

			// bottom right
			path.lineTo( x + w, y + h - ry );
			if ( rx !== 0 || ry !== 0 ) {

				path.bezierCurveTo(
					x + w,
					y + h - ry * bci,
					x + w - rx * bci,
					y + h,
					x + w - rx,
					y + h
				);

			}

			// bottom left
			path.lineTo( x + rx, y + h );
			if ( rx !== 0 || ry !== 0 ) {

				path.bezierCurveTo(
					x + rx * bci,
					y + h,
					x,
					y + h - ry * bci,
					x,
					y + h - ry
				);

			}

			// back to top left
			path.lineTo( x, y + ry );
			if ( rx !== 0 || ry !== 0 ) {

				path.bezierCurveTo( x, y + ry * bci, x + rx * bci, y, x + rx, y );

			}

			return path;

		}

		function parsePolygonNode( node ) {

			function iterator( match, a, b ) {

				const x = parseFloatWithUnits( a );
				const y = parseFloatWithUnits( b );

				if ( index === 0 ) {

					path.moveTo( x, y );

				} else {

					path.lineTo( x, y );

				}

				index ++;

			}

			const regex = /([+-]?\d*\.?\d+(?:e[+-]?\d+)?)(?:,|\s)([+-]?\d*\.?\d+(?:e[+-]?\d+)?)/g;

			const path = new ShapePath();

			let index = 0;

			node.getAttribute( 'points' ).replace( regex, iterator );

			path.currentPath.autoClose = true;

			return path;

		}

		function parsePolylineNode( node ) {

			function iterator( match, a, b ) {

				const x = parseFloatWithUnits( a );
				const y = parseFloatWithUnits( b );

				if ( index === 0 ) {

					path.moveTo( x, y );

				} else {

					path.lineTo( x, y );

				}

				index ++;

			}

			const regex = /([+-]?\d*\.?\d+(?:e[+-]?\d+)?)(?:,|\s)([+-]?\d*\.?\d+(?:e[+-]?\d+)?)/g;

			const path = new ShapePath();

			let index = 0;

			node.getAttribute( 'points' ).replace( regex, iterator );

			path.currentPath.autoClose = false;

			return path;

		}

		function parseCircleNode( node ) {

			const x = parseFloatWithUnits( node.getAttribute( 'cx' ) || 0 );
			const y = parseFloatWithUnits( node.getAttribute( 'cy' ) || 0 );
			const r = parseFloatWithUnits( node.getAttribute( 'r' ) || 0 );

			const subpath = new Path();
			subpath.absarc( x, y, r, 0, Math.PI * 2 );

			const path = new ShapePath();
			path.subPaths.push( subpath );

			return path;

		}

		function parseEllipseNode( node ) {

			const x = parseFloatWithUnits( node.getAttribute( 'cx' ) || 0 );
			const y = parseFloatWithUnits( node.getAttribute( 'cy' ) || 0 );
			const rx = parseFloatWithUnits( node.getAttribute( 'rx' ) || 0 );
			const ry = parseFloatWithUnits( node.getAttribute( 'ry' ) || 0 );

			const subpath = new Path();
			subpath.absellipse( x, y, rx, ry, 0, Math.PI * 2 );

			const path = new ShapePath();
			path.subPaths.push( subpath );

			return path;

		}

		function parseLineNode( node ) {

			const x1 = parseFloatWithUnits( node.getAttribute( 'x1' ) || 0 );
			const y1 = parseFloatWithUnits( node.getAttribute( 'y1' ) || 0 );
			const x2 = parseFloatWithUnits( node.getAttribute( 'x2' ) || 0 );
			const y2 = parseFloatWithUnits( node.getAttribute( 'y2' ) || 0 );

			const path = new ShapePath();
			path.moveTo( x1, y1 );
			path.lineTo( x2, y2 );
			path.currentPath.autoClose = false;

			return path;

		}

		//

		function parseStyle( node, style ) {

			style = Object.assign( {}, style ); // clone style

			let stylesheetStyles = {};

			if ( node.hasAttribute( 'class' ) ) {

				const classSelectors = node.getAttribute( 'class' )
					.split( /\s/ )
					.filter( Boolean )
					.map( i => i.trim() );

				for ( let i = 0; i < classSelectors.length; i ++ ) {

					stylesheetStyles = Object.assign( stylesheetStyles, stylesheets[ '.' + classSelectors[ i ] ] );

				}

			}

			if ( node.hasAttribute( 'id' ) ) {

				stylesheetStyles = Object.assign( stylesheetStyles, stylesheets[ '#' + node.getAttribute( 'id' ) ] );

			}

			function addStyle( svgName, jsName, adjustFunction ) {

				if ( adjustFunction === undefined ) adjustFunction = function copy( v ) {

					if ( v.startsWith( 'url' ) ) console.warn( 'SVGLoader: url access in attributes is not implemented.' );

					return v;

				};

				if ( node.hasAttribute( svgName ) ) style[ jsName ] = adjustFunction( node.getAttribute( svgName ) );
				if ( stylesheetStyles[ svgName ] ) style[ jsName ] = adjustFunction( stylesheetStyles[ svgName ] );
				if ( node.style && node.style[ svgName ] !== '' ) style[ jsName ] = adjustFunction( node.style[ svgName ] );

			}

			function clamp( v ) {

				return Math.max( 0, Math.min( 1, parseFloatWithUnits( v ) ) );

			}

			function positive( v ) {

				return Math.max( 0, parseFloatWithUnits( v ) );

			}

			addStyle( 'fill', 'fill' );
			addStyle( 'fill-opacity', 'fillOpacity', clamp );
			addStyle( 'fill-rule', 'fillRule' );
			addStyle( 'opacity', 'opacity', clamp );
			addStyle( 'stroke', 'stroke' );
			addStyle( 'stroke-opacity', 'strokeOpacity', clamp );
			addStyle( 'stroke-width', 'strokeWidth', positive );
			addStyle( 'stroke-linejoin', 'strokeLineJoin' );
			addStyle( 'stroke-linecap', 'strokeLineCap' );
			addStyle( 'stroke-miterlimit', 'strokeMiterLimit', positive );
			addStyle( 'visibility', 'visibility' );

			return style;

		}

		// http://www.w3.org/TR/SVG11/implnote.html#PathElementImplementationNotes

		function getReflection( a, b ) {

			return a - ( b - a );

		}

		// from https://github.com/ppvg/svg-numbers (MIT License)

		function parseFloats( input, flags, stride ) {

			if ( typeof input !== 'string' ) {

				throw new TypeError( 'Invalid input: ' + typeof input );

			}

			// Character groups
			const RE = {
				SEPARATOR: /[ \t\r\n\,.\-+]/,
				WHITESPACE: /[ \t\r\n]/,
				DIGIT: /[\d]/,
				SIGN: /[-+]/,
				POINT: /\./,
				COMMA: /,/,
				EXP: /e/i,
				FLAGS: /[01]/
			};

			// States
			const SEP = 0;
			const INT = 1;
			const FLOAT = 2;
			const EXP = 3;

			let state = SEP;
			let seenComma = true;
			let number = '', exponent = '';
			const result = [];

			function throwSyntaxError( current, i, partial ) {

				const error = new SyntaxError( 'Unexpected character "' + current + '" at index ' + i + '.' );
				error.partial = partial;
				throw error;

			}

			function newNumber() {

				if ( number !== '' ) {

					if ( exponent === '' ) result.push( Number( number ) );
					else result.push( Number( number ) * Math.pow( 10, Number( exponent ) ) );

				}

				number = '';
				exponent = '';

			}

			let current;
			const length = input.length;

			for ( let i = 0; i < length; i ++ ) {

				current = input[ i ];

				// check for flags
				if ( Array.isArray( flags ) && flags.includes( result.length % stride ) && RE.FLAGS.test( current ) ) {

					state = INT;
					number = current;
					newNumber();
					continue;

				}

				// parse until next number
				if ( state === SEP ) {

					// eat whitespace
					if ( RE.WHITESPACE.test( current ) ) {

						continue;

					}

					// start new number
					if ( RE.DIGIT.test( current ) || RE.SIGN.test( current ) ) {

						state = INT;
						number = current;
						continue;

					}

					if ( RE.POINT.test( current ) ) {

						state = FLOAT;
						number = current;
						continue;

					}

					// throw on double commas (e.g. "1, , 2")
					if ( RE.COMMA.test( current ) ) {

						if ( seenComma ) {

							throwSyntaxError( current, i, result );

						}

						seenComma = true;

					}

				}

				// parse integer part
				if ( state === INT ) {

					if ( RE.DIGIT.test( current ) ) {

						number += current;
						continue;

					}

					if ( RE.POINT.test( current ) ) {

						number += current;
						state = FLOAT;
						continue;

					}

					if ( RE.EXP.test( current ) ) {

						state = EXP;
						continue;

					}

					// throw on double signs ("-+1"), but not on sign as separator ("-1-2")
					if ( RE.SIGN.test( current )
							&& number.length === 1
							&& RE.SIGN.test( number[ 0 ] ) ) {

						throwSyntaxError( current, i, result );

					}

				}

				// parse decimal part
				if ( state === FLOAT ) {

					if ( RE.DIGIT.test( current ) ) {

						number += current;
						continue;

					}

					if ( RE.EXP.test( current ) ) {

						state = EXP;
						continue;

					}

					// throw on double decimal points (e.g. "1..2")
					if ( RE.POINT.test( current ) && number[ number.length - 1 ] === '.' ) {

						throwSyntaxError( current, i, result );

					}

				}

				// parse exponent part
				if ( state === EXP ) {

					if ( RE.DIGIT.test( current ) ) {

						exponent += current;
						continue;

					}

					if ( RE.SIGN.test( current ) ) {

						if ( exponent === '' ) {

							exponent += current;
							continue;

						}

						if ( exponent.length === 1 && RE.SIGN.test( exponent ) ) {

							throwSyntaxError( current, i, result );

						}

					}

				}


				// end of number
				if ( RE.WHITESPACE.test( current ) ) {

					newNumber();
					state = SEP;
					seenComma = false;

				} else if ( RE.COMMA.test( current ) ) {

					newNumber();
					state = SEP;
					seenComma = true;

				} else if ( RE.SIGN.test( current ) ) {

					newNumber();
					state = INT;
					number = current;

				} else if ( RE.POINT.test( current ) ) {

					newNumber();
					state = FLOAT;
					number = current;

				} else {

					throwSyntaxError( current, i, result );

				}

			}

			// add the last number found (if any)
			newNumber();

			return result;

		}

		// Units

		const units = [ 'mm', 'cm', 'in', 'pt', 'pc', 'px' ];

		// Conversion: [ fromUnit ][ toUnit ] (-1 means dpi dependent)
		const unitConversion = {

			'mm': {
				'mm': 1,
				'cm': 0.1,
				'in': 1 / 25.4,
				'pt': 72 / 25.4,
				'pc': 6 / 25.4,
				'px': - 1
			},
			'cm': {
				'mm': 10,
				'cm': 1,
				'in': 1 / 2.54,
				'pt': 72 / 2.54,
				'pc': 6 / 2.54,
				'px': - 1
			},
			'in': {
				'mm': 25.4,
				'cm': 2.54,
				'in': 1,
				'pt': 72,
				'pc': 6,
				'px': - 1
			},
			'pt': {
				'mm': 25.4 / 72,
				'cm': 2.54 / 72,
				'in': 1 / 72,
				'pt': 1,
				'pc': 6 / 72,
				'px': - 1
			},
			'pc': {
				'mm': 25.4 / 6,
				'cm': 2.54 / 6,
				'in': 1 / 6,
				'pt': 72 / 6,
				'pc': 1,
				'px': - 1
			},
			'px': {
				'px': 1
			}

		};

		function parseFloatWithUnits( string ) {

			let theUnit = 'px';

			if ( typeof string === 'string' || string instanceof String ) {

				for ( let i = 0, n = units.length; i < n; i ++ ) {

					const u = units[ i ];

					if ( string.endsWith( u ) ) {

						theUnit = u;
						string = string.substring( 0, string.length - u.length );
						break;

					}

				}

			}

			let scale = undefined;

			if ( theUnit === 'px' && scope.defaultUnit !== 'px' ) {

				// Conversion scale from  pixels to inches, then to default units

				scale = unitConversion[ 'in' ][ scope.defaultUnit ] / scope.defaultDPI;

			} else {

				scale = unitConversion[ theUnit ][ scope.defaultUnit ];

				if ( scale < 0 ) {

					// Conversion scale to pixels

					scale = unitConversion[ theUnit ][ 'in' ] * scope.defaultDPI;

				}

			}

			return scale * parseFloat( string );

		}

		// Transforms

		function getNodeTransform( node ) {

			if ( ! ( node.hasAttribute( 'transform' ) || ( node.nodeName === 'use' && ( node.hasAttribute( 'x' ) || node.hasAttribute( 'y' ) ) ) ) ) {

				return null;

			}

			const transform = parseNodeTransform( node );

			if ( transformStack.length > 0 ) {

				transform.premultiply( transformStack[ transformStack.length - 1 ] );

			}

			currentTransform.copy( transform );
			transformStack.push( transform );

			return transform;

		}

		function parseNodeTransform( node ) {

			const transform = new Matrix3();
			const currentTransform = tempTransform0;

			if ( node.nodeName === 'use' && ( node.hasAttribute( 'x' ) || node.hasAttribute( 'y' ) ) ) {

				const tx = parseFloatWithUnits( node.getAttribute( 'x' ) );
				const ty = parseFloatWithUnits( node.getAttribute( 'y' ) );

				transform.translate( tx, ty );

			}

			if ( node.hasAttribute( 'transform' ) ) {

				const transformsTexts = node.getAttribute( 'transform' ).split( ')' );

				for ( let tIndex = transformsTexts.length - 1; tIndex >= 0; tIndex -- ) {

					const transformText = transformsTexts[ tIndex ].trim();

					if ( transformText === '' ) continue;

					const openParPos = transformText.indexOf( '(' );
					const closeParPos = transformText.length;

					if ( openParPos > 0 && openParPos < closeParPos ) {

						const transformType = transformText.slice( 0, openParPos );

						const array = parseFloats( transformText.slice( openParPos + 1 ) );

						currentTransform.identity();

						switch ( transformType ) {

							case 'translate':

								if ( array.length >= 1 ) {

									const tx = array[ 0 ];
									let ty = 0;

									if ( array.length >= 2 ) {

										ty = array[ 1 ];

									}

									currentTransform.translate( tx, ty );

								}

								break;

							case 'rotate':

								if ( array.length >= 1 ) {

									let angle = 0;
									let cx = 0;
									let cy = 0;

									// Angle
									angle = array[ 0 ] * Math.PI / 180;

									if ( array.length >= 3 ) {

										// Center x, y
										cx = array[ 1 ];
										cy = array[ 2 ];

									}

									// Rotate around center (cx, cy)
									tempTransform1.makeTranslation( - cx, - cy );
									tempTransform2.makeRotation( angle );
									tempTransform3.multiplyMatrices( tempTransform2, tempTransform1 );
									tempTransform1.makeTranslation( cx, cy );
									currentTransform.multiplyMatrices( tempTransform1, tempTransform3 );

								}

								break;

							case 'scale':

								if ( array.length >= 1 ) {

									const scaleX = array[ 0 ];
									let scaleY = scaleX;

									if ( array.length >= 2 ) {

										scaleY = array[ 1 ];

									}

									currentTransform.scale( scaleX, scaleY );

								}

								break;

							case 'skewX':

								if ( array.length === 1 ) {

									currentTransform.set(
										1, Math.tan( array[ 0 ] * Math.PI / 180 ), 0,
										0, 1, 0,
										0, 0, 1
									);

								}

								break;

							case 'skewY':

								if ( array.length === 1 ) {

									currentTransform.set(
										1, 0, 0,
										Math.tan( array[ 0 ] * Math.PI / 180 ), 1, 0,
										0, 0, 1
									);

								}

								break;

							case 'matrix':

								if ( array.length === 6 ) {

									currentTransform.set(
										array[ 0 ], array[ 2 ], array[ 4 ],
										array[ 1 ], array[ 3 ], array[ 5 ],
										0, 0, 1
									);

								}

								break;

						}

					}

					transform.premultiply( currentTransform );

				}

			}

			return transform;

		}

		function transformPath( path, m ) {

			function transfVec2( v2 ) {

				tempV3.set( v2.x, v2.y, 1 ).applyMatrix3( m );

				v2.set( tempV3.x, tempV3.y );

			}

			function transfEllipseGeneric( curve ) {

				// For math description see:
				// https://math.stackexchange.com/questions/4544164

				const a = curve.xRadius;
				const b = curve.yRadius;

				const cosTheta = Math.cos( curve.aRotation );
				const sinTheta = Math.sin( curve.aRotation );

				const v1 = new Vector3( a * cosTheta, a * sinTheta, 0 );
				const v2 = new Vector3( - b * sinTheta, b * cosTheta, 0 );

				const f1 = v1.applyMatrix3( m );
				const f2 = v2.applyMatrix3( m );

				const mF = tempTransform0.set(
					f1.x, f2.x, 0,
					f1.y, f2.y, 0,
					0, 0, 1,
				);

				const mFInv = tempTransform1.copy( mF ).invert();
				const mFInvT = tempTransform2.copy( mFInv ).transpose();
				const mQ = mFInvT.multiply( mFInv );
				const mQe = mQ.elements;

				const ed = eigenDecomposition( mQe[ 0 ], mQe[ 1 ], mQe[ 4 ] );
				const rt1sqrt = Math.sqrt( ed.rt1 );
				const rt2sqrt = Math.sqrt( ed.rt2 );

				curve.xRadius = 1 / rt1sqrt;
				curve.yRadius = 1 / rt2sqrt;
				curve.aRotation = Math.atan2( ed.sn, ed.cs );

				const isFullEllipse =
					( curve.aEndAngle - curve.aStartAngle ) % ( 2 * Math.PI ) < Number.EPSILON;

				// Do not touch angles of a full ellipse because after transformation they
				// would converge to a single value effectively removing the whole curve

				if ( ! isFullEllipse ) {

					const mDsqrt = tempTransform1.set(
						rt1sqrt, 0, 0,
						0, rt2sqrt, 0,
						0, 0, 1,
					);

					const mRT = tempTransform2.set(
						ed.cs, ed.sn, 0,
						- ed.sn, ed.cs, 0,
						0, 0, 1,
					);

					const mDRF = mDsqrt.multiply( mRT ).multiply( mF );

					const transformAngle = phi => {

						const { x: cosR, y: sinR } =
							new Vector3( Math.cos( phi ), Math.sin( phi ), 0 ).applyMatrix3( mDRF );

						return Math.atan2( sinR, cosR );

					};

					curve.aStartAngle = transformAngle( curve.aStartAngle );
					curve.aEndAngle = transformAngle( curve.aEndAngle );

					if ( isTransformFlipped( m ) ) {

						curve.aClockwise = ! curve.aClockwise;

					}

				}

			}

			function transfEllipseNoSkew( curve ) {

				// Faster shortcut if no skew is applied
				// (e.g, a euclidean transform of a group containing the ellipse)

				const sx = getTransformScaleX( m );
				const sy = getTransformScaleY( m );

				curve.xRadius *= sx;
				curve.yRadius *= sy;

				// Extract rotation angle from the matrix of form:
				//
				//  | cosθ sx   -sinθ sy |
				//  | sinθ sx    cosθ sy |
				//
				// Remembering that tanθ = sinθ / cosθ; and that
				// `sx`, `sy`, or both might be zero.
				const theta =
					sx > Number.EPSILON
						? Math.atan2( m.elements[ 1 ], m.elements[ 0 ] )
						: Math.atan2( - m.elements[ 3 ], m.elements[ 4 ] );

				curve.aRotation += theta;

				if ( isTransformFlipped( m ) ) {

					curve.aStartAngle *= - 1;
					curve.aEndAngle *= - 1;
					curve.aClockwise = ! curve.aClockwise;

				}

			}

			const subPaths = path.subPaths;

			for ( let i = 0, n = subPaths.length; i < n; i ++ ) {

				const subPath = subPaths[ i ];
				const curves = subPath.curves;

				for ( let j = 0; j < curves.length; j ++ ) {

					const curve = curves[ j ];

					if ( curve.isLineCurve ) {

						transfVec2( curve.v1 );
						transfVec2( curve.v2 );

					} else if ( curve.isCubicBezierCurve ) {

						transfVec2( curve.v0 );
						transfVec2( curve.v1 );
						transfVec2( curve.v2 );
						transfVec2( curve.v3 );

					} else if ( curve.isQuadraticBezierCurve ) {

						transfVec2( curve.v0 );
						transfVec2( curve.v1 );
						transfVec2( curve.v2 );

					} else if ( curve.isEllipseCurve ) {

						// Transform ellipse center point

						tempV2.set( curve.aX, curve.aY );
						transfVec2( tempV2 );
						curve.aX = tempV2.x;
						curve.aY = tempV2.y;

						// Transform ellipse shape parameters

						if ( isTransformSkewed( m ) ) {

							transfEllipseGeneric( curve );

						} else {

							transfEllipseNoSkew( curve );

						}

					}

				}

			}

		}

		function isTransformFlipped( m ) {

			const te = m.elements;
			return te[ 0 ] * te[ 4 ] - te[ 1 ] * te[ 3 ] < 0;

		}

		function isTransformSkewed( m ) {

			const te = m.elements;
			const basisDot = te[ 0 ] * te[ 3 ] + te[ 1 ] * te[ 4 ];

			// Shortcut for trivial rotations and transformations
			if ( basisDot === 0 ) return false;

			const sx = getTransformScaleX( m );
			const sy = getTransformScaleY( m );

			return Math.abs( basisDot / ( sx * sy ) ) > Number.EPSILON;

		}

		function getTransformScaleX( m ) {

			const te = m.elements;
			return Math.sqrt( te[ 0 ] * te[ 0 ] + te[ 1 ] * te[ 1 ] );

		}

		function getTransformScaleY( m ) {

			const te = m.elements;
			return Math.sqrt( te[ 3 ] * te[ 3 ] + te[ 4 ] * te[ 4 ] );

		}

		// Calculates the eigensystem of a real symmetric 2x2 matrix
		//    [ A  B ]
		//    [ B  C ]
		// in the form
		//    [ A  B ]  =  [ cs  -sn ] [ rt1   0  ] [  cs  sn ]
		//    [ B  C ]     [ sn   cs ] [  0   rt2 ] [ -sn  cs ]
		// where rt1 >= rt2.
		//
		// Adapted from: https://www.mpi-hd.mpg.de/personalhomes/globes/3x3/index.html
		// -> Algorithms for real symmetric matrices -> Analytical (2x2 symmetric)
		function eigenDecomposition( A, B, C ) {

			let rt1, rt2, cs, sn, t;
			const sm = A + C;
			const df = A - C;
			const rt = Math.sqrt( df * df + 4 * B * B );

			if ( sm > 0 ) {

				rt1 = 0.5 * ( sm + rt );
				t = 1 / rt1;
				rt2 = A * t * C - B * t * B;

			} else if ( sm < 0 ) {

				rt2 = 0.5 * ( sm - rt );

			} else {

				// This case needs to be treated separately to avoid div by 0

				rt1 = 0.5 * rt;
				rt2 = - 0.5 * rt;

			}

			// Calculate eigenvectors

			if ( df > 0 ) {

				cs = df + rt;

			} else {

				cs = df - rt;

			}

			if ( Math.abs( cs ) > 2 * Math.abs( B ) ) {

				t = - 2 * B / cs;
				sn = 1 / Math.sqrt( 1 + t * t );
				cs = t * sn;

			} else if ( Math.abs( B ) === 0 ) {

				cs = 1;
				sn = 0;

			} else {

				t = - 0.5 * cs / B;
				cs = 1 / Math.sqrt( 1 + t * t );
				sn = t * cs;

			}

			if ( df > 0 ) {

				t = cs;
				cs = - sn;
				sn = t;

			}

			return { rt1, rt2, cs, sn };

		}

		//

		const paths = [];
		const stylesheets = {};

		const transformStack = [];

		const tempTransform0 = new Matrix3();
		const tempTransform1 = new Matrix3();
		const tempTransform2 = new Matrix3();
		const tempTransform3 = new Matrix3();
		const tempV2 = new Vector2();
		const tempV3 = new Vector3();

		const currentTransform = new Matrix3();

		const xml = new DOMParser().parseFromString( text, 'image/svg+xml' ); // application/xml

		parseNode( xml.documentElement, {
			fill: '#000',
			fillOpacity: 1,
			strokeOpacity: 1,
			strokeWidth: 1,
			strokeLineJoin: 'miter',
			strokeLineCap: 'butt',
			strokeMiterLimit: 4
		} );

		const data = { paths: paths, xml: xml.documentElement };

		// console.log( paths );
		return data;

	}
```
</details>

##### `createShapes(shapePath: ShapePath): Shape[]`

<details><summary>Code</summary>

```ts
static createShapes( shapePath ) {

		const BIGNUMBER = 999999999;

		const IntersectionLocationType = {
			ORIGIN: 0,
			DESTINATION: 1,
			BETWEEN: 2,
			LEFT: 3,
			RIGHT: 4,
			BEHIND: 5,
			BEYOND: 6
		};

		const classifyResult = {
			loc: IntersectionLocationType.ORIGIN,
			t: 0
		};

		function findEdgeIntersection( a0, a1, b0, b1 ) {

			const x1 = a0.x;
			const x2 = a1.x;
			const x3 = b0.x;
			const x4 = b1.x;
			const y1 = a0.y;
			const y2 = a1.y;
			const y3 = b0.y;
			const y4 = b1.y;
			const nom1 = ( x4 - x3 ) * ( y1 - y3 ) - ( y4 - y3 ) * ( x1 - x3 );
			const nom2 = ( x2 - x1 ) * ( y1 - y3 ) - ( y2 - y1 ) * ( x1 - x3 );
			const denom = ( y4 - y3 ) * ( x2 - x1 ) - ( x4 - x3 ) * ( y2 - y1 );
			const t1 = nom1 / denom;
			const t2 = nom2 / denom;

			if ( ( ( denom === 0 ) && ( nom1 !== 0 ) ) || ( t1 <= 0 ) || ( t1 >= 1 ) || ( t2 < 0 ) || ( t2 > 1 ) ) {

				//1. lines are parallel or edges don't intersect

				return null;

			} else if ( ( nom1 === 0 ) && ( denom === 0 ) ) {

				//2. lines are colinear

				//check if endpoints of edge2 (b0-b1) lies on edge1 (a0-a1)
				for ( let i = 0; i < 2; i ++ ) {

					classifyPoint( i === 0 ? b0 : b1, a0, a1 );
					//find position of this endpoints relatively to edge1
					if ( classifyResult.loc == IntersectionLocationType.ORIGIN ) {

						const point = ( i === 0 ? b0 : b1 );
						return { x: point.x, y: point.y, t: classifyResult.t };

					} else if ( classifyResult.loc == IntersectionLocationType.BETWEEN ) {

						const x = + ( ( x1 + classifyResult.t * ( x2 - x1 ) ).toPrecision( 10 ) );
						const y = + ( ( y1 + classifyResult.t * ( y2 - y1 ) ).toPrecision( 10 ) );
						return { x: x, y: y, t: classifyResult.t, };

					}

				}

				return null;

			} else {

				//3. edges intersect

				for ( let i = 0; i < 2; i ++ ) {

					classifyPoint( i === 0 ? b0 : b1, a0, a1 );

					if ( classifyResult.loc == IntersectionLocationType.ORIGIN ) {

						const point = ( i === 0 ? b0 : b1 );
						return { x: point.x, y: point.y, t: classifyResult.t };

					}

				}

				const x = + ( ( x1 + t1 * ( x2 - x1 ) ).toPrecision( 10 ) );
				const y = + ( ( y1 + t1 * ( y2 - y1 ) ).toPrecision( 10 ) );
				return { x: x, y: y, t: t1 };

			}

		}

		function classifyPoint( p, edgeStart, edgeEnd ) {

			const ax = edgeEnd.x - edgeStart.x;
			const ay = edgeEnd.y - edgeStart.y;
			const bx = p.x - edgeStart.x;
			const by = p.y - edgeStart.y;
			const sa = ax * by - bx * ay;

			if ( ( p.x === edgeStart.x ) && ( p.y === edgeStart.y ) ) {

				classifyResult.loc = IntersectionLocationType.ORIGIN;
				classifyResult.t = 0;
				return;

			}

			if ( ( p.x === edgeEnd.x ) && ( p.y === edgeEnd.y ) ) {

				classifyResult.loc = IntersectionLocationType.DESTINATION;
				classifyResult.t = 1;
				return;

			}

			if ( sa < - Number.EPSILON ) {

				classifyResult.loc = IntersectionLocationType.LEFT;
				return;

			}

			if ( sa > Number.EPSILON ) {

				classifyResult.loc = IntersectionLocationType.RIGHT;
				return;


			}

			if ( ( ( ax * bx ) < 0 ) || ( ( ay * by ) < 0 ) ) {

				classifyResult.loc = IntersectionLocationType.BEHIND;
				return;

			}

			if ( ( Math.sqrt( ax * ax + ay * ay ) ) < ( Math.sqrt( bx * bx + by * by ) ) ) {

				classifyResult.loc = IntersectionLocationType.BEYOND;
				return;

			}

			let t;

			if ( ax !== 0 ) {

				t = bx / ax;

			} else {

				t = by / ay;

			}

			classifyResult.loc = IntersectionLocationType.BETWEEN;
			classifyResult.t = t;

		}

		function getIntersections( path1, path2 ) {

			const intersectionsRaw = [];
			const intersections = [];

			for ( let index = 1; index < path1.length; index ++ ) {

				const path1EdgeStart = path1[ index - 1 ];
				const path1EdgeEnd = path1[ index ];

				for ( let index2 = 1; index2 < path2.length; index2 ++ ) {

					const path2EdgeStart = path2[ index2 - 1 ];
					const path2EdgeEnd = path2[ index2 ];

					const intersection = findEdgeIntersection( path1EdgeStart, path1EdgeEnd, path2EdgeStart, path2EdgeEnd );

					if ( intersection !== null && intersectionsRaw.find( i => i.t <= intersection.t + Number.EPSILON && i.t >= intersection.t - Number.EPSILON ) === undefined ) {

						intersectionsRaw.push( intersection );
						intersections.push( new Vector2( intersection.x, intersection.y ) );

					}

				}

			}

			return intersections;

		}

		function getScanlineIntersections( scanline, boundingBox, paths ) {

			const center = new Vector2();
			boundingBox.getCenter( center );

			const allIntersections = [];

			paths.forEach( path => {

				// check if the center of the bounding box is in the bounding box of the paths.
				// this is a pruning method to limit the search of intersections in paths that can't envelop of the current path.
				// if a path envelops another path. The center of that other path, has to be inside the bounding box of the enveloping path.
				if ( path.boundingBox.containsPoint( center ) ) {

					const intersections = getIntersections( scanline, path.points );

					intersections.forEach( p => {

						allIntersections.push( { identifier: path.identifier, isCW: path.isCW, point: p } );

					} );

				}

			} );

			allIntersections.sort( ( i1, i2 ) => {

				return i1.point.x - i2.point.x;

			} );

			return allIntersections;

		}

		function isHoleTo( simplePath, allPaths, scanlineMinX, scanlineMaxX, _fillRule ) {

			if ( _fillRule === null || _fillRule === undefined || _fillRule === '' ) {

				_fillRule = 'nonzero';

			}

			const centerBoundingBox = new Vector2();
			simplePath.boundingBox.getCenter( centerBoundingBox );

			const scanline = [ new Vector2( scanlineMinX, centerBoundingBox.y ), new Vector2( scanlineMaxX, centerBoundingBox.y ) ];

			const scanlineIntersections = getScanlineIntersections( scanline, simplePath.boundingBox, allPaths );

			scanlineIntersections.sort( ( i1, i2 ) => {

				return i1.point.x - i2.point.x;

			} );

			const baseIntersections = [];
			const otherIntersections = [];

			scanlineIntersections.forEach( i => {

				if ( i.identifier === simplePath.identifier ) {

					baseIntersections.push( i );

				} else {

					otherIntersections.push( i );

				}

			} );

			const firstXOfPath = baseIntersections[ 0 ].point.x;

			// build up the path hierarchy
			const stack = [];
			let i = 0;

			while ( i < otherIntersections.length && otherIntersections[ i ].point.x < firstXOfPath ) {

				if ( stack.length > 0 && stack[ stack.length - 1 ] === otherIntersections[ i ].identifier ) {

					stack.pop();

				} else {

					stack.push( otherIntersections[ i ].identifier );

				}

				i ++;

			}

			stack.push( simplePath.identifier );

			if ( _fillRule === 'evenodd' ) {

				const isHole = stack.length % 2 === 0 ? true : false;
				const isHoleFor = stack[ stack.length - 2 ];

				return { identifier: simplePath.identifier, isHole: isHole, for: isHoleFor };

			} else if ( _fillRule === 'nonzero' ) {

				// check if path is a hole by counting the amount of paths with alternating rotations it has to cross.
				let isHole = true;
				let isHoleFor = null;
				let lastCWValue = null;

				for ( let i = 0; i < stack.length; i ++ ) {

					const identifier = stack[ i ];
					if ( isHole ) {

						lastCWValue = allPaths[ identifier ].isCW;
						isHole = false;
						isHoleFor = identifier;

					} else if ( lastCWValue !== allPaths[ identifier ].isCW ) {

						lastCWValue = allPaths[ identifier ].isCW;
						isHole = true;

					}

				}

				return { identifier: simplePath.identifier, isHole: isHole, for: isHoleFor };

			} else {

				console.warn( 'fill-rule: "' + _fillRule + '" is currently not implemented.' );

			}

		}

		// check for self intersecting paths
		// TODO

		// check intersecting paths
		// TODO

		// prepare paths for hole detection
		let scanlineMinX = BIGNUMBER;
		let scanlineMaxX = - BIGNUMBER;

		let simplePaths = shapePath.subPaths.map( p => {

			const points = p.getPoints();
			let maxY = - BIGNUMBER;
			let minY = BIGNUMBER;
			let maxX = - BIGNUMBER;
			let minX = BIGNUMBER;

	      	//points.forEach(p => p.y *= -1);

			for ( let i = 0; i < points.length; i ++ ) {

				const p = points[ i ];

				if ( p.y > maxY ) {

					maxY = p.y;

				}

				if ( p.y < minY ) {

					minY = p.y;

				}

				if ( p.x > maxX ) {

					maxX = p.x;

				}

				if ( p.x < minX ) {

					minX = p.x;

				}

			}

			//
			if ( scanlineMaxX <= maxX ) {

				scanlineMaxX = maxX + 1;

			}

			if ( scanlineMinX >= minX ) {

				scanlineMinX = minX - 1;

			}

			return { curves: p.curves, points: points, isCW: ShapeUtils.isClockWise( points ), identifier: - 1, boundingBox: new Box2( new Vector2( minX, minY ), new Vector2( maxX, maxY ) ) };

		} );

		simplePaths = simplePaths.filter( sp => sp.points.length > 1 );

		for ( let identifier = 0; identifier < simplePaths.length; identifier ++ ) {

			simplePaths[ identifier ].identifier = identifier;

		}

		// check if path is solid or a hole
		const isAHole = simplePaths.map( p => isHoleTo( p, simplePaths, scanlineMinX, scanlineMaxX, ( shapePath.userData ? shapePath.userData.style.fillRule : undefined ) ) );


		const shapesToReturn = [];
		simplePaths.forEach( p => {

			const amIAHole = isAHole[ p.identifier ];

			if ( ! amIAHole.isHole ) {

				const shape = new Shape();
				shape.curves = p.curves;
				const holes = isAHole.filter( h => h.isHole && h.for === p.identifier );
				holes.forEach( h => {

					const hole = simplePaths[ h.identifier ];
					const path = new Path();
					path.curves = hole.curves;
					shape.holes.push( path );

				} );
				shapesToReturn.push( shape );

			}

		} );

		return shapesToReturn;

	}
```
</details>

##### `getStrokeStyle(width: number, color: string, lineJoin: "round" | "bevel" | "miter" | "miter-limit", lineCap: "round" | "butt" | "square", miterLimit: number): any`

<details><summary>Code</summary>

```ts
static getStrokeStyle( width, color, lineJoin, lineCap, miterLimit ) {

		width = width !== undefined ? width : 1;
		color = color !== undefined ? color : '#000';
		lineJoin = lineJoin !== undefined ? lineJoin : 'miter';
		lineCap = lineCap !== undefined ? lineCap : 'butt';
		miterLimit = miterLimit !== undefined ? miterLimit : 4;

		return {
			strokeColor: color,
			strokeWidth: width,
			strokeLineJoin: lineJoin,
			strokeLineCap: lineCap,
			strokeMiterLimit: miterLimit
		};

	}
```
</details>

##### `pointsToStroke(points: Vector2[], style: any, arcDivisions: number, minDistance: number): BufferGeometry`

<details><summary>Code</summary>

```ts
static pointsToStroke( points, style, arcDivisions, minDistance ) {

		const vertices = [];
		const normals = [];
		const uvs = [];

		if ( SVGLoader.pointsToStrokeWithBuffers( points, style, arcDivisions, minDistance, vertices, normals, uvs ) === 0 ) {

			return null;

		}

		const geometry = new BufferGeometry();
		geometry.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );
		geometry.setAttribute( 'normal', new Float32BufferAttribute( normals, 3 ) );
		geometry.setAttribute( 'uv', new Float32BufferAttribute( uvs, 2 ) );

		return geometry;

	}
```
</details>

##### `pointsToStrokeWithBuffers(points: Vector2[], style: any, arcDivisions: number, minDistance: number, vertices: number[], normals: number[], uvs: number[], vertexOffset: number): number`

<details><summary>Code</summary>

```ts
static pointsToStrokeWithBuffers( points, style, arcDivisions, minDistance, vertices, normals, uvs, vertexOffset ) {

		// This function can be called to update existing arrays or buffers.
		// Accepts same parameters as pointsToStroke, plus the buffers and optional offset.
		// Param vertexOffset: Offset vertices to start writing in the buffers (3 elements/vertex for vertices and normals, and 2 elements/vertex for uvs)
		// Returns number of written vertices / normals / uvs pairs
		// if 'vertices' parameter is undefined no triangles will be generated, but the returned vertices count will still be valid (useful to preallocate the buffers)
		// 'normals' and 'uvs' buffers are optional

		const tempV2_1 = new Vector2();
		const tempV2_2 = new Vector2();
		const tempV2_3 = new Vector2();
		const tempV2_4 = new Vector2();
		const tempV2_5 = new Vector2();
		const tempV2_6 = new Vector2();
		const tempV2_7 = new Vector2();
		const lastPointL = new Vector2();
		const lastPointR = new Vector2();
		const point0L = new Vector2();
		const point0R = new Vector2();
		const currentPointL = new Vector2();
		const currentPointR = new Vector2();
		const nextPointL = new Vector2();
		const nextPointR = new Vector2();
		const innerPoint = new Vector2();
		const outerPoint = new Vector2();

		arcDivisions = arcDivisions !== undefined ? arcDivisions : 12;
		minDistance = minDistance !== undefined ? minDistance : 0.001;
		vertexOffset = vertexOffset !== undefined ? vertexOffset : 0;

		// First ensure there are no duplicated points
		points = removeDuplicatedPoints( points );

		const numPoints = points.length;

		if ( numPoints < 2 ) return 0;

		const isClosed = points[ 0 ].equals( points[ numPoints - 1 ] );

		let currentPoint;
		let previousPoint = points[ 0 ];
		let nextPoint;

		const strokeWidth2 = style.strokeWidth / 2;

		const deltaU = 1 / ( numPoints - 1 );
		let u0 = 0, u1;

		let innerSideModified;
		let joinIsOnLeftSide;
		let isMiter;
		let initialJoinIsOnLeftSide = false;

		let numVertices = 0;
		let currentCoordinate = vertexOffset * 3;
		let currentCoordinateUV = vertexOffset * 2;

		// Get initial left and right stroke points
		getNormal( points[ 0 ], points[ 1 ], tempV2_1 ).multiplyScalar( strokeWidth2 );
		lastPointL.copy( points[ 0 ] ).sub( tempV2_1 );
		lastPointR.copy( points[ 0 ] ).add( tempV2_1 );
		point0L.copy( lastPointL );
		point0R.copy( lastPointR );

		for ( let iPoint = 1; iPoint < numPoints; iPoint ++ ) {

			currentPoint = points[ iPoint ];

			// Get next point
			if ( iPoint === numPoints - 1 ) {

				if ( isClosed ) {

					// Skip duplicated initial point
					nextPoint = points[ 1 ];

				} else nextPoint = undefined;

			} else {

				nextPoint = points[ iPoint + 1 ];

			}

			// Normal of previous segment in tempV2_1
			const normal1 = tempV2_1;
			getNormal( previousPoint, currentPoint, normal1 );

			tempV2_3.copy( normal1 ).multiplyScalar( strokeWidth2 );
			currentPointL.copy( currentPoint ).sub( tempV2_3 );
			currentPointR.copy( currentPoint ).add( tempV2_3 );

			u1 = u0 + deltaU;

			innerSideModified = false;

			if ( nextPoint !== undefined ) {

				// Normal of next segment in tempV2_2
				getNormal( currentPoint, nextPoint, tempV2_2 );

				tempV2_3.copy( tempV2_2 ).multiplyScalar( strokeWidth2 );
				nextPointL.copy( currentPoint ).sub( tempV2_3 );
				nextPointR.copy( currentPoint ).add( tempV2_3 );

				joinIsOnLeftSide = true;
				tempV2_3.subVectors( nextPoint, previousPoint );
				if ( normal1.dot( tempV2_3 ) < 0 ) {

					joinIsOnLeftSide = false;

				}

				if ( iPoint === 1 ) initialJoinIsOnLeftSide = joinIsOnLeftSide;

				tempV2_3.subVectors( nextPoint, currentPoint );
				tempV2_3.normalize();
				const dot = Math.abs( normal1.dot( tempV2_3 ) );

				// If path is straight, don't create join
				if ( dot > Number.EPSILON ) {

					// Compute inner and outer segment intersections
					const miterSide = strokeWidth2 / dot;
					tempV2_3.multiplyScalar( - miterSide );
					tempV2_4.subVectors( currentPoint, previousPoint );
					tempV2_5.copy( tempV2_4 ).setLength( miterSide ).add( tempV2_3 );
					innerPoint.copy( tempV2_5 ).negate();
					const miterLength2 = tempV2_5.length();
					const segmentLengthPrev = tempV2_4.length();
					tempV2_4.divideScalar( segmentLengthPrev );
					tempV2_6.subVectors( nextPoint, currentPoint );
					const segmentLengthNext = tempV2_6.length();
					tempV2_6.divideScalar( segmentLengthNext );
					// Check that previous and next segments doesn't overlap with the innerPoint of intersection
					if ( tempV2_4.dot( innerPoint ) < segmentLengthPrev && tempV2_6.dot( innerPoint ) < segmentLengthNext ) {

						innerSideModified = true;

					}

					outerPoint.copy( tempV2_5 ).add( currentPoint );
					innerPoint.add( currentPoint );

					isMiter = false;

					if ( innerSideModified ) {

						if ( joinIsOnLeftSide ) {

							nextPointR.copy( innerPoint );
							currentPointR.copy( innerPoint );

						} else {

							nextPointL.copy( innerPoint );
							currentPointL.copy( innerPoint );

						}

					} else {

						// The segment triangles are generated here if there was overlapping

						makeSegmentTriangles();

					}

					switch ( style.strokeLineJoin ) {

						case 'bevel':

							makeSegmentWithBevelJoin( joinIsOnLeftSide, innerSideModified, u1 );

							break;

						case 'round':

							// Segment triangles

							createSegmentTrianglesWithMiddleSection( joinIsOnLeftSide, innerSideModified );

							// Join triangles

							if ( joinIsOnLeftSide ) {

								makeCircularSector( currentPoint, currentPointL, nextPointL, u1, 0 );

							} else {

								makeCircularSector( currentPoint, nextPointR, currentPointR, u1, 1 );

							}

							break;

						case 'miter':
						case 'miter-clip':
						default:

							const miterFraction = ( strokeWidth2 * style.strokeMiterLimit ) / miterLength2;

							if ( miterFraction < 1 ) {

								// The join miter length exceeds the miter limit

								if ( style.strokeLineJoin !== 'miter-clip' ) {

									makeSegmentWithBevelJoin( joinIsOnLeftSide, innerSideModified, u1 );
									break;

								} else {

									// Segment triangles

									createSegmentTrianglesWithMiddleSection( joinIsOnLeftSide, innerSideModified );

									// Miter-clip join triangles

									if ( joinIsOnLeftSide ) {

										tempV2_6.subVectors( outerPoint, currentPointL ).multiplyScalar( miterFraction ).add( currentPointL );
										tempV2_7.subVectors( outerPoint, nextPointL ).multiplyScalar( miterFraction ).add( nextPointL );

										addVertex( currentPointL, u1, 0 );
										addVertex( tempV2_6, u1, 0 );
										addVertex( currentPoint, u1, 0.5 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( tempV2_6, u1, 0 );
										addVertex( tempV2_7, u1, 0 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( tempV2_7, u1, 0 );
										addVertex( nextPointL, u1, 0 );

									} else {

										tempV2_6.subVectors( outerPoint, currentPointR ).multiplyScalar( miterFraction ).add( currentPointR );
										tempV2_7.subVectors( outerPoint, nextPointR ).multiplyScalar( miterFraction ).add( nextPointR );

										addVertex( currentPointR, u1, 1 );
										addVertex( tempV2_6, u1, 1 );
										addVertex( currentPoint, u1, 0.5 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( tempV2_6, u1, 1 );
										addVertex( tempV2_7, u1, 1 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( tempV2_7, u1, 1 );
										addVertex( nextPointR, u1, 1 );

									}

								}

							} else {

								// Miter join segment triangles

								if ( innerSideModified ) {

									// Optimized segment + join triangles

									if ( joinIsOnLeftSide ) {

										addVertex( lastPointR, u0, 1 );
										addVertex( lastPointL, u0, 0 );
										addVertex( outerPoint, u1, 0 );

										addVertex( lastPointR, u0, 1 );
										addVertex( outerPoint, u1, 0 );
										addVertex( innerPoint, u1, 1 );

									} else {

										addVertex( lastPointR, u0, 1 );
										addVertex( lastPointL, u0, 0 );
										addVertex( outerPoint, u1, 1 );

										addVertex( lastPointL, u0, 0 );
										addVertex( innerPoint, u1, 0 );
										addVertex( outerPoint, u1, 1 );

									}


									if ( joinIsOnLeftSide ) {

										nextPointL.copy( outerPoint );

									} else {

										nextPointR.copy( outerPoint );

									}


								} else {

									// Add extra miter join triangles

									if ( joinIsOnLeftSide ) {

										addVertex( currentPointL, u1, 0 );
										addVertex( outerPoint, u1, 0 );
										addVertex( currentPoint, u1, 0.5 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( outerPoint, u1, 0 );
										addVertex( nextPointL, u1, 0 );

									} else {

										addVertex( currentPointR, u1, 1 );
										addVertex( outerPoint, u1, 1 );
										addVertex( currentPoint, u1, 0.5 );

										addVertex( currentPoint, u1, 0.5 );
										addVertex( outerPoint, u1, 1 );
										addVertex( nextPointR, u1, 1 );

									}

								}

								isMiter = true;

							}

							break;

					}

				} else {

					// The segment triangles are generated here when two consecutive points are collinear

					makeSegmentTriangles();

				}

			} else {

				// The segment triangles are generated here if it is the ending segment

				makeSegmentTriangles();

			}

			if ( ! isClosed && iPoint === numPoints - 1 ) {

				// Start line endcap
				addCapGeometry( points[ 0 ], point0L, point0R, joinIsOnLeftSide, true, u0 );

			}

			// Increment loop variables

			u0 = u1;

			previousPoint = currentPoint;

			lastPointL.copy( nextPointL );
			lastPointR.copy( nextPointR );

		}

		if ( ! isClosed ) {

			// Ending line endcap
			addCapGeometry( currentPoint, currentPointL, currentPointR, joinIsOnLeftSide, false, u1 );

		} else if ( innerSideModified && vertices ) {

			// Modify path first segment vertices to adjust to the segments inner and outer intersections

			let lastOuter = outerPoint;
			let lastInner = innerPoint;

			if ( initialJoinIsOnLeftSide !== joinIsOnLeftSide ) {

				lastOuter = innerPoint;
				lastInner = outerPoint;

			}

			if ( joinIsOnLeftSide ) {

				if ( isMiter || initialJoinIsOnLeftSide ) {

					lastInner.toArray( vertices, 0 * 3 );
					lastInner.toArray( vertices, 3 * 3 );

					if ( isMiter ) {

						lastOuter.toArray( vertices, 1 * 3 );

					}

				}

			} else {

				if ( isMiter || ! initialJoinIsOnLeftSide ) {

					lastInner.toArray( vertices, 1 * 3 );
					lastInner.toArray( vertices, 3 * 3 );

					if ( isMiter ) {

						lastOuter.toArray( vertices, 0 * 3 );

					}

				}

			}

		}

		return numVertices;

		// -- End of algorithm

		// -- Functions

		function getNormal( p1, p2, result ) {

			result.subVectors( p2, p1 );
			return result.set( - result.y, result.x ).normalize();

		}

		function addVertex( position, u, v ) {

			if ( vertices ) {

				vertices[ currentCoordinate ] = position.x;
				vertices[ currentCoordinate + 1 ] = position.y;
				vertices[ currentCoordinate + 2 ] = 0;

				if ( normals ) {

					normals[ currentCoordinate ] = 0;
					normals[ currentCoordinate + 1 ] = 0;
					normals[ currentCoordinate + 2 ] = 1;

				}

				currentCoordinate += 3;

				if ( uvs ) {

					uvs[ currentCoordinateUV ] = u;
					uvs[ currentCoordinateUV + 1 ] = v;

					currentCoordinateUV += 2;

				}

			}

			numVertices += 3;

		}

		function makeCircularSector( center, p1, p2, u, v ) {

			// param p1, p2: Points in the circle arc.
			// p1 and p2 are in clockwise direction.

			tempV2_1.copy( p1 ).sub( center ).normalize();
			tempV2_2.copy( p2 ).sub( center ).normalize();

			let angle = Math.PI;
			const dot = tempV2_1.dot( tempV2_2 );
			if ( Math.abs( dot ) < 1 ) angle = Math.abs( Math.acos( dot ) );

			angle /= arcDivisions;

			tempV2_3.copy( p1 );

			for ( let i = 0, il = arcDivisions - 1; i < il; i ++ ) {

				tempV2_4.copy( tempV2_3 ).rotateAround( center, angle );

				addVertex( tempV2_3, u, v );
				addVertex( tempV2_4, u, v );
				addVertex( center, u, 0.5 );

				tempV2_3.copy( tempV2_4 );

			}

			addVertex( tempV2_4, u, v );
			addVertex( p2, u, v );
			addVertex( center, u, 0.5 );

		}

		function makeSegmentTriangles() {

			addVertex( lastPointR, u0, 1 );
			addVertex( lastPointL, u0, 0 );
			addVertex( currentPointL, u1, 0 );

			addVertex( lastPointR, u0, 1 );
			addVertex( currentPointL, u1, 0 );
			addVertex( currentPointR, u1, 1 );

		}

		function makeSegmentWithBevelJoin( joinIsOnLeftSide, innerSideModified, u ) {

			if ( innerSideModified ) {

				// Optimized segment + bevel triangles

				if ( joinIsOnLeftSide ) {

					// Path segments triangles

					addVertex( lastPointR, u0, 1 );
					addVertex( lastPointL, u0, 0 );
					addVertex( currentPointL, u1, 0 );

					addVertex( lastPointR, u0, 1 );
					addVertex( currentPointL, u1, 0 );
					addVertex( innerPoint, u1, 1 );

					// Bevel join triangle

					addVertex( currentPointL, u, 0 );
					addVertex( nextPointL, u, 0 );
					addVertex( innerPoint, u, 0.5 );

				} else {

					// Path segments triangles

					addVertex( lastPointR, u0, 1 );
					addVertex( lastPointL, u0, 0 );
					addVertex( currentPointR, u1, 1 );

					addVertex( lastPointL, u0, 0 );
					addVertex( innerPoint, u1, 0 );
					addVertex( currentPointR, u1, 1 );

					// Bevel join triangle

					addVertex( currentPointR, u, 1 );
					addVertex( innerPoint, u, 0 );
					addVertex( nextPointR, u, 1 );

				}

			} else {

				// Bevel join triangle. The segment triangles are done in the main loop

				if ( joinIsOnLeftSide ) {

					addVertex( currentPointL, u, 0 );
					addVertex( nextPointL, u, 0 );
					addVertex( currentPoint, u, 0.5 );

				} else {

					addVertex( currentPointR, u, 1 );
					addVertex( nextPointR, u, 0 );
					addVertex( currentPoint, u, 0.5 );

				}

			}

		}

		function createSegmentTrianglesWithMiddleSection( joinIsOnLeftSide, innerSideModified ) {

			if ( innerSideModified ) {

				if ( joinIsOnLeftSide ) {

					addVertex( lastPointR, u0, 1 );
					addVertex( lastPointL, u0, 0 );
					addVertex( currentPointL, u1, 0 );

					addVertex( lastPointR, u0, 1 );
					addVertex( currentPointL, u1, 0 );
					addVertex( innerPoint, u1, 1 );

					addVertex( currentPointL, u0, 0 );
					addVertex( currentPoint, u1, 0.5 );
					addVertex( innerPoint, u1, 1 );

					addVertex( currentPoint, u1, 0.5 );
					addVertex( nextPointL, u0, 0 );
					addVertex( innerPoint, u1, 1 );

				} else {

					addVertex( lastPointR, u0, 1 );
					addVertex( lastPointL, u0, 0 );
					addVertex( currentPointR, u1, 1 );

					addVertex( lastPointL, u0, 0 );
					addVertex( innerPoint, u1, 0 );
					addVertex( currentPointR, u1, 1 );

					addVertex( currentPointR, u0, 1 );
					addVertex( innerPoint, u1, 0 );
					addVertex( currentPoint, u1, 0.5 );

					addVertex( currentPoint, u1, 0.5 );
					addVertex( innerPoint, u1, 0 );
					addVertex( nextPointR, u0, 1 );

				}

			}

		}

		function addCapGeometry( center, p1, p2, joinIsOnLeftSide, start, u ) {

			// param center: End point of the path
			// param p1, p2: Left and right cap points

			switch ( style.strokeLineCap ) {

				case 'round':

					if ( start ) {

						makeCircularSector( center, p2, p1, u, 0.5 );

					} else {

						makeCircularSector( center, p1, p2, u, 0.5 );

					}

					break;

				case 'square':

					if ( start ) {

						tempV2_1.subVectors( p1, center );
						tempV2_2.set( tempV2_1.y, - tempV2_1.x );

						tempV2_3.addVectors( tempV2_1, tempV2_2 ).add( center );
						tempV2_4.subVectors( tempV2_2, tempV2_1 ).add( center );

						// Modify already existing vertices
						if ( joinIsOnLeftSide ) {

							tempV2_3.toArray( vertices, 1 * 3 );
							tempV2_4.toArray( vertices, 0 * 3 );
							tempV2_4.toArray( vertices, 3 * 3 );

						} else {

							tempV2_3.toArray( vertices, 1 * 3 );
							// using tempV2_4 to update 3rd vertex if the uv.y of 3rd vertex is 1
							uvs[ 3 * 2 + 1 ] === 1 ? tempV2_4.toArray( vertices, 3 * 3 ) : tempV2_3.toArray( vertices, 3 * 3 );
							tempV2_4.toArray( vertices, 0 * 3 );

						}

					} else {

						tempV2_1.subVectors( p2, center );
						tempV2_2.set( tempV2_1.y, - tempV2_1.x );

						tempV2_3.addVectors( tempV2_1, tempV2_2 ).add( center );
						tempV2_4.subVectors( tempV2_2, tempV2_1 ).add( center );

						const vl = vertices.length;

						// Modify already existing vertices
						if ( joinIsOnLeftSide ) {

							tempV2_3.toArray( vertices, vl - 1 * 3 );
							tempV2_4.toArray( vertices, vl - 2 * 3 );
							tempV2_4.toArray( vertices, vl - 4 * 3 );

						} else {

							tempV2_4.toArray( vertices, vl - 2 * 3 );
							tempV2_3.toArray( vertices, vl - 1 * 3 );
							tempV2_4.toArray( vertices, vl - 4 * 3 );

						}

					}

					break;

				case 'butt':
				default:

					// Nothing to do here
					break;

			}

		}

		function removeDuplicatedPoints( points ) {

			// Creates a new array if necessary with duplicated points removed.
			// This does not remove duplicated initial and ending points of a closed path.

			let dupPoints = false;
			for ( let i = 1, n = points.length - 1; i < n; i ++ ) {

				if ( points[ i ].distanceTo( points[ i + 1 ] ) < minDistance ) {

					dupPoints = true;
					break;

				}

			}

			if ( ! dupPoints ) return points;

			const newPoints = [];
			newPoints.push( points[ 0 ] );

			for ( let i = 1, n = points.length - 1; i < n; i ++ ) {

				if ( points[ i ].distanceTo( points[ i + 1 ] ) >= minDistance ) {

					newPoints.push( points[ i ] );

				}

			}

			newPoints.push( points[ points.length - 1 ] );

			return newPoints;

		}

	}
```
</details>


---