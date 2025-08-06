[⬅️ Back to Table of Contents](../../index.md)

# 📄 `ExtrudeGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 28 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 120 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/geometries/ExtrudeGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `../core/BufferGeometry.js` |
| `Float32BufferAttribute` | `../core/BufferAttribute.js` |
| `Vector2` | `../math/Vector2.js` |
| `Vector3` | `../math/Vector3.js` |
| `Shape` | `../extras/core/Shape.js` |
| `ShapeUtils` | `../extras/ShapeUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `verticesArray` | `any[]` | let/var | `[]` | ✗ |
| `uvArray` | `any[]` | let/var | `[]` | ✗ |
| `shape` | `Shape` | let/var | `shapes[ i ]` | ✗ |
| `placeholder` | `any[]` | let/var | `[]` | ✗ |
| `curveSegments` | `any` | let/var | `options.curveSegments !== undefined ? options.curveSegments : 12` | ✗ |
| `steps` | `any` | let/var | `options.steps !== undefined ? options.steps : 1` | ✗ |
| `depth` | `any` | let/var | `options.depth !== undefined ? options.depth : 1` | ✗ |
| `bevelEnabled` | `any` | let/var | `options.bevelEnabled !== undefined ? options.bevelEnabled : true` | ✗ |
| `bevelThickness` | `any` | let/var | `options.bevelThickness !== undefined ? options.bevelThickness : 0.2` | ✗ |
| `bevelSize` | `any` | let/var | `options.bevelSize !== undefined ? options.bevelSize : bevelThickness - 0.1` | ✗ |
| `bevelOffset` | `any` | let/var | `options.bevelOffset !== undefined ? options.bevelOffset : 0` | ✗ |
| `bevelSegments` | `any` | let/var | `options.bevelSegments !== undefined ? options.bevelSegments : 3` | ✗ |
| `extrudePath` | `any` | let/var | `options.extrudePath` | ✗ |
| `uvgen` | `any` | let/var | `options.UVGenerator !== undefined ? options.UVGenerator : WorldUVGenerator` | ✗ |
| `extrudePts` | `any` | let/var | `*not shown*` | ✗ |
| `extrudeByPath` | `boolean` | let/var | `false` | ✗ |
| `splineTube` | `any` | let/var | `*not shown*` | ✗ |
| `binormal` | `any` | let/var | `*not shown*` | ✗ |
| `normal` | `any` | let/var | `*not shown*` | ✗ |
| `position2` | `any` | let/var | `*not shown*` | ✗ |
| `vertices` | `any` | let/var | `shapePoints.shape` | ✗ |
| `holes` | `any` | let/var | `shapePoints.holes` | ✗ |
| `reverse` | `boolean` | let/var | `! ShapeUtils.isClockWise( vertices )` | ✗ |
| `ahole` | `any` | let/var | `holes[ h ]` | ✗ |
| `THRESHOLD` | `1e-10` | let/var | `1e-10` | ✗ |
| `THRESHOLD_SQ` | `number` | let/var | `THRESHOLD * THRESHOLD` | ✗ |
| `prevPos` | `Vector2` | let/var | `points[ 0 ]` | ✗ |
| `currentIndex` | `number` | let/var | `i % points.length` | ✗ |
| `currentPos` | `Vector2` | let/var | `points[ currentIndex ]` | ✗ |
| `dx` | `number` | let/var | `currentPos.x - prevPos.x` | ✗ |
| `dy` | `number` | let/var | `currentPos.y - prevPos.y` | ✗ |
| `distSq` | `number` | let/var | `dx * dx + dy * dy` | ✗ |
| `thresholdSqScaled` | `number` | let/var | `THRESHOLD_SQ * scalingFactorSqrt * scalingFactorSqrt` | ✗ |
| `numHoles` | `any` | let/var | `holes.length` | ✗ |
| `contour` | `any` | let/var | `vertices` | ✗ |
| `ahole` | `any` | let/var | `holes[ h ]` | ✗ |
| `vlen` | `any` | let/var | `vertices.length` | ✗ |
| `v_trans_x` | `any` | let/var | `*not shown*` | ✗ |
| `v_trans_y` | `any` | let/var | `*not shown*` | ✗ |
| `shrink_by` | `any` | let/var | `*not shown*` | ✗ |
| `v_prev_x` | `number` | let/var | `inPt.x - inPrev.x` | ✗ |
| `v_prev_y` | `number` | let/var | `inPt.y - inPrev.y` | ✗ |
| `v_next_x` | `number` | let/var | `inNext.x - inPt.x` | ✗ |
| `v_next_y` | `number` | let/var | `inNext.y - inPt.y` | ✗ |
| `v_prev_lensq` | `number` | let/var | `( v_prev_x * v_prev_x + v_prev_y * v_prev_y )` | ✗ |
| `collinear0` | `number` | let/var | `( v_prev_x * v_next_y - v_prev_y * v_next_x )` | ✗ |
| `ptPrevShift_x` | `number` | let/var | `( inPrev.x - v_prev_y / v_prev_len )` | ✗ |
| `ptPrevShift_y` | `any` | let/var | `( inPrev.y + v_prev_x / v_prev_len )` | ✗ |
| `ptNextShift_x` | `number` | let/var | `( inNext.x - v_next_y / v_next_len )` | ✗ |
| `ptNextShift_y` | `any` | let/var | `( inNext.y + v_next_x / v_next_len )` | ✗ |
| `sf` | `number` | let/var | `( ( ptNextShift_x - ptPrevShift_x ) * v_next_y - ( ptNextShift_y - ptPrevShif...` | ✗ |
| `v_trans_lensq` | `number` | let/var | `( v_trans_x * v_trans_x + v_trans_y * v_trans_y )` | ✗ |
| `direction_eq` | `boolean` | let/var | `false` | ✗ |
| `contourMovements` | `any[]` | let/var | `[]` | ✗ |
| `holesMovements` | `any[]` | let/var | `[]` | ✗ |
| `oneHoleMovements` | `any` | let/var | `*not shown*` | ✗ |
| `ahole` | `any` | let/var | `holes[ h ]` | ✗ |
| `faces` | `any` | let/var | `*not shown*` | ✗ |
| `contractedContourVertices` | `any[]` | let/var | `[]` | ✗ |
| `expandedHoleVertices` | `any[]` | let/var | `[]` | ✗ |
| `t` | `number` | let/var | `b / bevelSegments` | ✗ |
| `z` | `number` | let/var | `bevelThickness * Math.cos( t * Math.PI / 2 )` | ✗ |
| `bs` | `any` | let/var | `bevelSize * Math.sin( t * Math.PI / 2 ) + bevelOffset` | ✗ |
| `ahole` | `any` | let/var | `holes[ h ]` | ✗ |
| `oneHoleVertices` | `any[]` | let/var | `[]` | ✗ |
| `flen` | `number` | let/var | `faces.length` | ✗ |
| `bs` | `any` | let/var | `bevelSize + bevelOffset` | ✗ |
| `vert` | `any` | let/var | `bevelEnabled ? scalePt2( vertices[ i ], verticesMovements[ i ], bs ) : vertic...` | ✗ |
| `vert` | `any` | let/var | `bevelEnabled ? scalePt2( vertices[ i ], verticesMovements[ i ], bs ) : vertic...` | ✗ |
| `t` | `number` | let/var | `b / bevelSegments` | ✗ |
| `z` | `number` | let/var | `bevelThickness * Math.cos( t * Math.PI / 2 )` | ✗ |
| `bs` | `any` | let/var | `bevelSize * Math.sin( t * Math.PI / 2 ) + bevelOffset` | ✗ |
| `ahole` | `any` | let/var | `holes[ h ]` | ✗ |
| `start` | `number` | let/var | `verticesArray.length / 3` | ✗ |
| `layer` | `number` | let/var | `0` | ✗ |
| `offset` | `number` | let/var | `vlen * layer` | ✗ |
| `face` | `any` | let/var | `faces[ i ]` | ✗ |
| `face` | `any` | let/var | `faces[ i ]` | ✗ |
| `face` | `any` | let/var | `faces[ i ]` | ✗ |
| `face` | `any` | let/var | `faces[ i ]` | ✗ |
| `start` | `number` | let/var | `verticesArray.length / 3` | ✗ |
| `layeroffset` | `number` | let/var | `0` | ✗ |
| `ahole` | `any` | let/var | `holes[ h ]` | ✗ |
| `i` | `any` | let/var | `contour.length` | ✗ |
| `j` | `any` | let/var | `i` | ✗ |
| `k` | `number` | let/var | `i - 1` | ✗ |
| `slen1` | `number` | let/var | `vlen * s` | ✗ |
| `slen2` | `number` | let/var | `vlen * ( s + 1 )` | ✗ |
| `a` | `any` | let/var | `layeroffset + j + slen1` | ✗ |
| `b` | `any` | let/var | `layeroffset + k + slen1` | ✗ |
| `c` | `any` | let/var | `layeroffset + k + slen2` | ✗ |
| `d` | `any` | let/var | `layeroffset + j + slen2` | ✗ |
| `nextIndex` | `number` | let/var | `verticesArray.length / 3` | ✗ |
| `nextIndex` | `number` | let/var | `verticesArray.length / 3` | ✗ |
| `shapes` | `any` | let/var | `this.parameters.shapes` | ✗ |
| `options` | `any` | let/var | `this.parameters.options` | ✗ |
| `geometryShapes` | `any[]` | let/var | `[]` | ✗ |
| `shape` | `Shape` | let/var | `shapes[ data.shapes[ j ] ]` | ✗ |
| `extrudePath` | `any` | let/var | `data.options.extrudePath` | ✗ |
| `a_x` | `any` | let/var | `vertices[ indexA * 3 ]` | ✗ |
| `a_y` | `any` | let/var | `vertices[ indexA * 3 + 1 ]` | ✗ |
| `b_x` | `any` | let/var | `vertices[ indexB * 3 ]` | ✗ |
| `b_y` | `any` | let/var | `vertices[ indexB * 3 + 1 ]` | ✗ |
| `c_x` | `any` | let/var | `vertices[ indexC * 3 ]` | ✗ |
| `c_y` | `any` | let/var | `vertices[ indexC * 3 + 1 ]` | ✗ |
| `a_x` | `any` | let/var | `vertices[ indexA * 3 ]` | ✗ |
| `a_y` | `any` | let/var | `vertices[ indexA * 3 + 1 ]` | ✗ |
| `a_z` | `any` | let/var | `vertices[ indexA * 3 + 2 ]` | ✗ |
| `b_x` | `any` | let/var | `vertices[ indexB * 3 ]` | ✗ |
| `b_y` | `any` | let/var | `vertices[ indexB * 3 + 1 ]` | ✗ |
| `b_z` | `any` | let/var | `vertices[ indexB * 3 + 2 ]` | ✗ |
| `c_x` | `any` | let/var | `vertices[ indexC * 3 ]` | ✗ |
| `c_y` | `any` | let/var | `vertices[ indexC * 3 + 1 ]` | ✗ |
| `c_z` | `any` | let/var | `vertices[ indexC * 3 + 2 ]` | ✗ |
| `d_x` | `any` | let/var | `vertices[ indexD * 3 ]` | ✗ |
| `d_y` | `any` | let/var | `vertices[ indexD * 3 + 1 ]` | ✗ |
| `d_z` | `any` | let/var | `vertices[ indexD * 3 + 2 ]` | ✗ |
| `WorldUVGenerator` | `{ generateTopUV: (geometry: any, vert...` | let/var | `{ generateTopUV: function ( geometry, vertices, indexA, indexB, indexC ) { co...` | ✗ |
| `shape` | `any` | let/var | `shapes[ i ]` | ✗ |


---

## Functions

### `ExtrudeGeometry.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `Object.assign`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.parameters = Object.assign( {}, source.parameters );

		return this;

	}
```
</details>

### `ExtrudeGeometry.toJSON(): any`

**Returns:** `any`

**Calls:**

- `super.toJSON`
- `toJSON`

<details><summary>Code</summary>

```typescript
toJSON() {

		const data = super.toJSON();

		const shapes = this.parameters.shapes;
		const options = this.parameters.options;

		return toJSON( shapes, options, data );

	}
```
</details>

### `ExtrudeGeometry.fromJSON(data: any, shapes: Shape[]): ExtrudeGeometry`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @param {Array<Shape>} shapes - An array of shapes.
	 * @return {ExtrudeGeometry} A new instance.
	 */
```

**Parameters:**

- **`data`** `any`
- **`shapes`** `Shape[]`

**Returns:** `ExtrudeGeometry`

**Calls:**

- `geometryShapes.push`
- `new Curves[ extrudePath.type ]().fromJSON`

<details><summary>Code</summary>

```typescript
static fromJSON( data, shapes ) {

		const geometryShapes = [];

		for ( let j = 0, jl = data.shapes.length; j < jl; j ++ ) {

			const shape = shapes[ data.shapes[ j ] ];

			geometryShapes.push( shape );

		}

		const extrudePath = data.options.extrudePath;

		if ( extrudePath !== undefined ) {

			data.options.extrudePath = new Curves[ extrudePath.type ]().fromJSON( extrudePath );

		}

		return new ExtrudeGeometry( geometryShapes, data.options );

	}
```
</details>

### `addShape(shape: any): void`

**Parameters:**

- **`shape`** `any`

**Returns:** `void`

**Calls:**

- `extrudePath.getSpacedPoints`
- `extrudePath.computeFrenetFrames`
- `shape.extractPoints`
- `ShapeUtils.isClockWise`
- `vertices.reverse`
- `ahole.reverse`
- `Math.max`
- `Math.abs`
- `points.splice`
- `mergeOverlappingPoints`
- `holes.forEach`
- `vertices.concat`
- `console.error`
- `pt.clone().addScaledVector`
- `Math.sqrt`
- `Math.sign`
- `getBevelVec`
- `contourMovements.concat`
- `holesMovements.push`
- `verticesMovements.concat`
- `ShapeUtils.triangulateShape`
- `Math.cos`
- `Math.sin`
- `scalePt2`
- `v`
- `contractedContourVertices.push`
- `oneHoleVertices.push`
- `expandedHoleVertices.push`
- `normal.copy( splineTube.normals[ 0 ] ).multiplyScalar`
- `binormal.copy( splineTube.binormals[ 0 ] ).multiplyScalar`
- `position2.copy( extrudePts[ 0 ] ).add( normal ).add`
- `normal.copy( splineTube.normals[ s ] ).multiplyScalar`
- `binormal.copy( splineTube.binormals[ s ] ).multiplyScalar`
- `position2.copy( extrudePts[ s ] ).add( normal ).add`
- `buildLidFaces`
- `buildSideFaces`
- `f3`
- `scope.addGroup`
- `sidewalls`
- `f4`
- `placeholder.push`
- `addVertex`
- `uvgen.generateTopUV`
- `addUV`
- `uvgen.generateSideWallUV`
- `verticesArray.push`
- `uvArray.push`

**Internal Comments:**
```
// options (x2)
// (x4)
// SETUP TNB variables (x3)
// TODO1 - have a .isClosed in spline? (x3)
// console.log(splineTube, 'splineTube', splineTube.normals.length, 'steps', steps, 'extrudePts', extrudePts.length); (x3)
// Safeguards if bevels are not enabled
// Variables initialization (x2)
// Maybe we should also check if holes are in the opposite direction, just to be safe ...
/**Merges index-adjacent points that are within a threshold distance of each other. Array is modified in-place. Threshold distance is empirical, and scaled based on the magnitude of point coordinates.
			 * @param {Array<Vector2>} points
			*/
/* Vertices */ (x2)
// Find directions for point movement
// computes for inPt the corresponding point inPt' on a new contour (x2)
//   shifted by 1 unit (length of normalized vector) to the left (x2)
// if we walk along contour clockwise, this new contour is outside the old one (x2)
// inPt' is the intersection of the two lines parallel to the two (x2)
//  adjacent edges of inPt at a distance of 1 unit on the left side. (x2)
// good reading for geometry algorithms (here: line-line intersection) (x2)
// http://geomalgorithms.com/a05-_intersect-1.html (x2)
// check for collinear edges (x2)
// not collinear (x2)
// length of vectors for normalizing (x2)
// shift adjacent points by unit vectors to the left (x2)
// scaling factor for v_prev to intersection point (x2)
// vector from inPt to intersection point (x3)
// Don't normalize!, otherwise sharp corners become ugly (x2)
//  but prevent crazy spikes (x2)
// handle special case of collinear edges (x2)
// console.log("Warning: lines are a straight sequence"); (x3)
// console.log("Warning: lines are a straight spike"); (x3)
//  (j)---(i)---(k) (x8)
// console.log('i,j,k', i, j , k) (x4)
// Loop bevelSegments, 1 for the front, 1 for the back
//for ( b = bevelSegments; b > 0; b -- ) { (x2)
// contract shape (x2)
// expand holes (x2)
// Back facing vertices
// v( vert.x, vert.y + extrudePts[ 0 ].y, extrudePts[ 0 ].x ); (x6)
// Add stepped vertices...
// Including front facing vertices
// v( vert.x, vert.y + extrudePts[ s - 1 ].y, extrudePts[ s - 1 ].x ); (x6)
// Add bevel segments planes
//for ( b = 1; b <= bevelSegments; b ++ ) {
/* Faces */ (x3)
// Top and bottom faces (x3)
// Sides faces (x3)
/////  Internal functions
// Bottom faces (x2)
// Top faces (x2)
// Create faces for the z-sides of the shape
//, true (x3)
//console.log('b', i,j, i-1, k,vertices.length);
```

<details><summary>Code</summary>

```typescript
function addShape( shape ) {

			const placeholder = [];

			// options

			const curveSegments = options.curveSegments !== undefined ? options.curveSegments : 12;
			const steps = options.steps !== undefined ? options.steps : 1;
			const depth = options.depth !== undefined ? options.depth : 1;

			let bevelEnabled = options.bevelEnabled !== undefined ? options.bevelEnabled : true;
			let bevelThickness = options.bevelThickness !== undefined ? options.bevelThickness : 0.2;
			let bevelSize = options.bevelSize !== undefined ? options.bevelSize : bevelThickness - 0.1;
			let bevelOffset = options.bevelOffset !== undefined ? options.bevelOffset : 0;
			let bevelSegments = options.bevelSegments !== undefined ? options.bevelSegments : 3;

			const extrudePath = options.extrudePath;

			const uvgen = options.UVGenerator !== undefined ? options.UVGenerator : WorldUVGenerator;

			//

			let extrudePts, extrudeByPath = false;
			let splineTube, binormal, normal, position2;

			if ( extrudePath ) {

				extrudePts = extrudePath.getSpacedPoints( steps );

				extrudeByPath = true;
				bevelEnabled = false; // bevels not supported for path extrusion

				// SETUP TNB variables

				// TODO1 - have a .isClosed in spline?

				splineTube = extrudePath.computeFrenetFrames( steps, false );

				// console.log(splineTube, 'splineTube', splineTube.normals.length, 'steps', steps, 'extrudePts', extrudePts.length);

				binormal = new Vector3();
				normal = new Vector3();
				position2 = new Vector3();

			}

			// Safeguards if bevels are not enabled

			if ( ! bevelEnabled ) {

				bevelSegments = 0;
				bevelThickness = 0;
				bevelSize = 0;
				bevelOffset = 0;

			}

			// Variables initialization

			const shapePoints = shape.extractPoints( curveSegments );

			let vertices = shapePoints.shape;
			const holes = shapePoints.holes;

			const reverse = ! ShapeUtils.isClockWise( vertices );

			if ( reverse ) {

				vertices = vertices.reverse();

				// Maybe we should also check if holes are in the opposite direction, just to be safe ...

				for ( let h = 0, hl = holes.length; h < hl; h ++ ) {

					const ahole = holes[ h ];

					if ( ShapeUtils.isClockWise( ahole ) ) {

						holes[ h ] = ahole.reverse();

					}

				}

			}

			/**Merges index-adjacent points that are within a threshold distance of each other. Array is modified in-place. Threshold distance is empirical, and scaled based on the magnitude of point coordinates.
			 * @param {Array<Vector2>} points
			*/
			function mergeOverlappingPoints( points ) {

				const THRESHOLD = 1e-10;
				const THRESHOLD_SQ = THRESHOLD * THRESHOLD;
				let prevPos = points[ 0 ];
				for ( let i = 1; i <= points.length; i ++ ) {

					const currentIndex = i % points.length;
					const currentPos = points[ currentIndex ];
					const dx = currentPos.x - prevPos.x;
					const dy = currentPos.y - prevPos.y;
					const distSq = dx * dx + dy * dy;

					const scalingFactorSqrt = Math.max(
						Math.abs( currentPos.x ),
						Math.abs( currentPos.y ),
						Math.abs( prevPos.x ),
						Math.abs( prevPos.y )
					);
					const thresholdSqScaled = THRESHOLD_SQ * scalingFactorSqrt * scalingFactorSqrt;
					if ( distSq <= thresholdSqScaled ) {

						points.splice( currentIndex, 1 );
						i --;
						continue;

					}

					prevPos = currentPos;

				}

			}

			mergeOverlappingPoints( vertices );
			holes.forEach( mergeOverlappingPoints );

			const numHoles = holes.length;

			/* Vertices */

			const contour = vertices; // vertices has all points but contour has only points of circumference

			for ( let h = 0; h < numHoles; h ++ ) {

				const ahole = holes[ h ];

				vertices = vertices.concat( ahole );

			}


			function scalePt2( pt, vec, size ) {

				if ( ! vec ) console.error( 'THREE.ExtrudeGeometry: vec does not exist' );

				return pt.clone().addScaledVector( vec, size );

			}

			const vlen = vertices.length;


			// Find directions for point movement


			function getBevelVec( inPt, inPrev, inNext ) {

				// computes for inPt the corresponding point inPt' on a new contour
				//   shifted by 1 unit (length of normalized vector) to the left
				// if we walk along contour clockwise, this new contour is outside the old one
				//
				// inPt' is the intersection of the two lines parallel to the two
				//  adjacent edges of inPt at a distance of 1 unit on the left side.

				let v_trans_x, v_trans_y, shrink_by; // resulting translation vector for inPt

				// good reading for geometry algorithms (here: line-line intersection)
				// http://geomalgorithms.com/a05-_intersect-1.html

				const v_prev_x = inPt.x - inPrev.x,
					v_prev_y = inPt.y - inPrev.y;
				const v_next_x = inNext.x - inPt.x,
					v_next_y = inNext.y - inPt.y;

				const v_prev_lensq = ( v_prev_x * v_prev_x + v_prev_y * v_prev_y );

				// check for collinear edges
				const collinear0 = ( v_prev_x * v_next_y - v_prev_y * v_next_x );

				if ( Math.abs( collinear0 ) > Number.EPSILON ) {

					// not collinear

					// length of vectors for normalizing

					const v_prev_len = Math.sqrt( v_prev_lensq );
					const v_next_len = Math.sqrt( v_next_x * v_next_x + v_next_y * v_next_y );

					// shift adjacent points by unit vectors to the left

					const ptPrevShift_x = ( inPrev.x - v_prev_y / v_prev_len );
					const ptPrevShift_y = ( inPrev.y + v_prev_x / v_prev_len );

					const ptNextShift_x = ( inNext.x - v_next_y / v_next_len );
					const ptNextShift_y = ( inNext.y + v_next_x / v_next_len );

					// scaling factor for v_prev to intersection point

					const sf = ( ( ptNextShift_x - ptPrevShift_x ) * v_next_y -
							( ptNextShift_y - ptPrevShift_y ) * v_next_x ) /
						( v_prev_x * v_next_y - v_prev_y * v_next_x );

					// vector from inPt to intersection point

					v_trans_x = ( ptPrevShift_x + v_prev_x * sf - inPt.x );
					v_trans_y = ( ptPrevShift_y + v_prev_y * sf - inPt.y );

					// Don't normalize!, otherwise sharp corners become ugly
					//  but prevent crazy spikes
					const v_trans_lensq = ( v_trans_x * v_trans_x + v_trans_y * v_trans_y );
					if ( v_trans_lensq <= 2 ) {

						return new Vector2( v_trans_x, v_trans_y );

					} else {

						shrink_by = Math.sqrt( v_trans_lensq / 2 );

					}

				} else {

					// handle special case of collinear edges

					let direction_eq = false; // assumes: opposite

					if ( v_prev_x > Number.EPSILON ) {

						if ( v_next_x > Number.EPSILON ) {

							direction_eq = true;

						}

					} else {

						if ( v_prev_x < - Number.EPSILON ) {

							if ( v_next_x < - Number.EPSILON ) {

								direction_eq = true;

							}

						} else {

							if ( Math.sign( v_prev_y ) === Math.sign( v_next_y ) ) {

								direction_eq = true;

							}

						}

					}

					if ( direction_eq ) {

						// console.log("Warning: lines are a straight sequence");
						v_trans_x = - v_prev_y;
						v_trans_y = v_prev_x;
						shrink_by = Math.sqrt( v_prev_lensq );

					} else {

						// console.log("Warning: lines are a straight spike");
						v_trans_x = v_prev_x;
						v_trans_y = v_prev_y;
						shrink_by = Math.sqrt( v_prev_lensq / 2 );

					}

				}

				return new Vector2( v_trans_x / shrink_by, v_trans_y / shrink_by );

			}


			const contourMovements = [];

			for ( let i = 0, il = contour.length, j = il - 1, k = i + 1; i < il; i ++, j ++, k ++ ) {

				if ( j === il ) j = 0;
				if ( k === il ) k = 0;

				//  (j)---(i)---(k)
				// console.log('i,j,k', i, j , k)

				contourMovements[ i ] = getBevelVec( contour[ i ], contour[ j ], contour[ k ] );

			}

			const holesMovements = [];
			let oneHoleMovements, verticesMovements = contourMovements.concat();

			for ( let h = 0, hl = numHoles; h < hl; h ++ ) {

				const ahole = holes[ h ];

				oneHoleMovements = [];

				for ( let i = 0, il = ahole.length, j = il - 1, k = i + 1; i < il; i ++, j ++, k ++ ) {

					if ( j === il ) j = 0;
					if ( k === il ) k = 0;

					//  (j)---(i)---(k)
					oneHoleMovements[ i ] = getBevelVec( ahole[ i ], ahole[ j ], ahole[ k ] );

				}

				holesMovements.push( oneHoleMovements );
				verticesMovements = verticesMovements.concat( oneHoleMovements );

			}

			let faces;

			if ( bevelSegments === 0 ) {

				faces = ShapeUtils.triangulateShape( contour, holes );

			} else {

				const contractedContourVertices = [];
				const expandedHoleVertices = [];

				// Loop bevelSegments, 1 for the front, 1 for the back

				for ( let b = 0; b < bevelSegments; b ++ ) {

					//for ( b = bevelSegments; b > 0; b -- ) {

					const t = b / bevelSegments;
					const z = bevelThickness * Math.cos( t * Math.PI / 2 );
					const bs = bevelSize * Math.sin( t * Math.PI / 2 ) + bevelOffset;

					// contract shape

					for ( let i = 0, il = contour.length; i < il; i ++ ) {

						const vert = scalePt2( contour[ i ], contourMovements[ i ], bs );

						v( vert.x, vert.y, - z );
						if ( t === 0 ) contractedContourVertices.push( vert );

					}

					// expand holes

					for ( let h = 0, hl = numHoles; h < hl; h ++ ) {

						const ahole = holes[ h ];
						oneHoleMovements = holesMovements[ h ];
						const oneHoleVertices = [];
						for ( let i = 0, il = ahole.length; i < il; i ++ ) {

							const vert = scalePt2( ahole[ i ], oneHoleMovements[ i ], bs );

							v( vert.x, vert.y, - z );
							if ( t === 0 ) oneHoleVertices.push( vert );

						}

						if ( t === 0 ) expandedHoleVertices.push( oneHoleVertices );

					}

				}

				faces = ShapeUtils.triangulateShape( contractedContourVertices, expandedHoleVertices );

			}

			const flen = faces.length;

			const bs = bevelSize + bevelOffset;

			// Back facing vertices

			for ( let i = 0; i < vlen; i ++ ) {

				const vert = bevelEnabled ? scalePt2( vertices[ i ], verticesMovements[ i ], bs ) : vertices[ i ];

				if ( ! extrudeByPath ) {

					v( vert.x, vert.y, 0 );

				} else {

					// v( vert.x, vert.y + extrudePts[ 0 ].y, extrudePts[ 0 ].x );

					normal.copy( splineTube.normals[ 0 ] ).multiplyScalar( vert.x );
					binormal.copy( splineTube.binormals[ 0 ] ).multiplyScalar( vert.y );

					position2.copy( extrudePts[ 0 ] ).add( normal ).add( binormal );

					v( position2.x, position2.y, position2.z );

				}

			}

			// Add stepped vertices...
			// Including front facing vertices

			for ( let s = 1; s <= steps; s ++ ) {

				for ( let i = 0; i < vlen; i ++ ) {

					const vert = bevelEnabled ? scalePt2( vertices[ i ], verticesMovements[ i ], bs ) : vertices[ i ];

					if ( ! extrudeByPath ) {

						v( vert.x, vert.y, depth / steps * s );

					} else {

						// v( vert.x, vert.y + extrudePts[ s - 1 ].y, extrudePts[ s - 1 ].x );

						normal.copy( splineTube.normals[ s ] ).multiplyScalar( vert.x );
						binormal.copy( splineTube.binormals[ s ] ).multiplyScalar( vert.y );

						position2.copy( extrudePts[ s ] ).add( normal ).add( binormal );

						v( position2.x, position2.y, position2.z );

					}

				}

			}


			// Add bevel segments planes

			//for ( b = 1; b <= bevelSegments; b ++ ) {
			for ( let b = bevelSegments - 1; b >= 0; b -- ) {

				const t = b / bevelSegments;
				const z = bevelThickness * Math.cos( t * Math.PI / 2 );
				const bs = bevelSize * Math.sin( t * Math.PI / 2 ) + bevelOffset;

				// contract shape

				for ( let i = 0, il = contour.length; i < il; i ++ ) {

					const vert = scalePt2( contour[ i ], contourMovements[ i ], bs );
					v( vert.x, vert.y, depth + z );

				}

				// expand holes

				for ( let h = 0, hl = holes.length; h < hl; h ++ ) {

					const ahole = holes[ h ];
					oneHoleMovements = holesMovements[ h ];

					for ( let i = 0, il = ahole.length; i < il; i ++ ) {

						const vert = scalePt2( ahole[ i ], oneHoleMovements[ i ], bs );

						if ( ! extrudeByPath ) {

							v( vert.x, vert.y, depth + z );

						} else {

							v( vert.x, vert.y + extrudePts[ steps - 1 ].y, extrudePts[ steps - 1 ].x + z );

						}

					}

				}

			}

			/* Faces */

			// Top and bottom faces

			buildLidFaces();

			// Sides faces

			buildSideFaces();


			/////  Internal functions

			function buildLidFaces() {

				const start = verticesArray.length / 3;

				if ( bevelEnabled ) {

					let layer = 0; // steps + 1
					let offset = vlen * layer;

					// Bottom faces

					for ( let i = 0; i < flen; i ++ ) {

						const face = faces[ i ];
						f3( face[ 2 ] + offset, face[ 1 ] + offset, face[ 0 ] + offset );

					}

					layer = steps + bevelSegments * 2;
					offset = vlen * layer;

					// Top faces

					for ( let i = 0; i < flen; i ++ ) {

						const face = faces[ i ];
						f3( face[ 0 ] + offset, face[ 1 ] + offset, face[ 2 ] + offset );

					}

				} else {

					// Bottom faces

					for ( let i = 0; i < flen; i ++ ) {

						const face = faces[ i ];
						f3( face[ 2 ], face[ 1 ], face[ 0 ] );

					}

					// Top faces

					for ( let i = 0; i < flen; i ++ ) {

						const face = faces[ i ];
						f3( face[ 0 ] + vlen * steps, face[ 1 ] + vlen * steps, face[ 2 ] + vlen * steps );

					}

				}

				scope.addGroup( start, verticesArray.length / 3 - start, 0 );

			}

			// Create faces for the z-sides of the shape

			function buildSideFaces() {

				const start = verticesArray.length / 3;
				let layeroffset = 0;
				sidewalls( contour, layeroffset );
				layeroffset += contour.length;

				for ( let h = 0, hl = holes.length; h < hl; h ++ ) {

					const ahole = holes[ h ];
					sidewalls( ahole, layeroffset );

					//, true
					layeroffset += ahole.length;

				}


				scope.addGroup( start, verticesArray.length / 3 - start, 1 );


			}

			function sidewalls( contour, layeroffset ) {

				let i = contour.length;

				while ( -- i >= 0 ) {

					const j = i;
					let k = i - 1;
					if ( k < 0 ) k = contour.length - 1;

					//console.log('b', i,j, i-1, k,vertices.length);

					for ( let s = 0, sl = ( steps + bevelSegments * 2 ); s < sl; s ++ ) {

						const slen1 = vlen * s;
						const slen2 = vlen * ( s + 1 );

						const a = layeroffset + j + slen1,
							b = layeroffset + k + slen1,
							c = layeroffset + k + slen2,
							d = layeroffset + j + slen2;

						f4( a, b, c, d );

					}

				}

			}

			function v( x, y, z ) {

				placeholder.push( x );
				placeholder.push( y );
				placeholder.push( z );

			}


			function f3( a, b, c ) {

				addVertex( a );
				addVertex( b );
				addVertex( c );

				const nextIndex = verticesArray.length / 3;
				const uvs = uvgen.generateTopUV( scope, verticesArray, nextIndex - 3, nextIndex - 2, nextIndex - 1 );

				addUV( uvs[ 0 ] );
				addUV( uvs[ 1 ] );
				addUV( uvs[ 2 ] );

			}

			function f4( a, b, c, d ) {

				addVertex( a );
				addVertex( b );
				addVertex( d );

				addVertex( b );
				addVertex( c );
				addVertex( d );


				const nextIndex = verticesArray.length / 3;
				const uvs = uvgen.generateSideWallUV( scope, verticesArray, nextIndex - 6, nextIndex - 3, nextIndex - 2, nextIndex - 1 );

				addUV( uvs[ 0 ] );
				addUV( uvs[ 1 ] );
				addUV( uvs[ 3 ] );

				addUV( uvs[ 1 ] );
				addUV( uvs[ 2 ] );
				addUV( uvs[ 3 ] );

			}

			function addVertex( index ) {

				verticesArray.push( placeholder[ index * 3 + 0 ] );
				verticesArray.push( placeholder[ index * 3 + 1 ] );
				verticesArray.push( placeholder[ index * 3 + 2 ] );

			}


			function addUV( vector2 ) {

				uvArray.push( vector2.x );
				uvArray.push( vector2.y );

			}

		}
```
</details>

### `mergeOverlappingPoints(points: Vector2[]): void`

**JSDoc:**
```typescript
/**Merges index-adjacent points that are within a threshold distance of each other. Array is modified in-place. Threshold distance is empirical, and scaled based on the magnitude of point coordinates.
			 * @param {Array<Vector2>} points
			*/
```

**Parameters:**

- **`points`** `Vector2[]`

**Returns:** `void`

**Calls:**

- `Math.max`
- `Math.abs`
- `points.splice`

<details><summary>Code</summary>

```typescript
function mergeOverlappingPoints( points ) {

				const THRESHOLD = 1e-10;
				const THRESHOLD_SQ = THRESHOLD * THRESHOLD;
				let prevPos = points[ 0 ];
				for ( let i = 1; i <= points.length; i ++ ) {

					const currentIndex = i % points.length;
					const currentPos = points[ currentIndex ];
					const dx = currentPos.x - prevPos.x;
					const dy = currentPos.y - prevPos.y;
					const distSq = dx * dx + dy * dy;

					const scalingFactorSqrt = Math.max(
						Math.abs( currentPos.x ),
						Math.abs( currentPos.y ),
						Math.abs( prevPos.x ),
						Math.abs( prevPos.y )
					);
					const thresholdSqScaled = THRESHOLD_SQ * scalingFactorSqrt * scalingFactorSqrt;
					if ( distSq <= thresholdSqScaled ) {

						points.splice( currentIndex, 1 );
						i --;
						continue;

					}

					prevPos = currentPos;

				}

			}
```
</details>

### `scalePt2(pt: any, vec: any, size: any): any`

**Parameters:**

- **`pt`** `any`
- **`vec`** `any`
- **`size`** `any`

**Returns:** `any`

**Calls:**

- `console.error`
- `pt.clone().addScaledVector`

<details><summary>Code</summary>

```typescript
function scalePt2( pt, vec, size ) {

				if ( ! vec ) console.error( 'THREE.ExtrudeGeometry: vec does not exist' );

				return pt.clone().addScaledVector( vec, size );

			}
```
</details>

### `getBevelVec(inPt: any, inPrev: any, inNext: any): Vector2`

**Parameters:**

- **`inPt`** `any`
- **`inPrev`** `any`
- **`inNext`** `any`

**Returns:** `Vector2`

**Calls:**

- `Math.abs`
- `Math.sqrt`
- `Math.sign`

**Internal Comments:**
```
// computes for inPt the corresponding point inPt' on a new contour (x2)
//   shifted by 1 unit (length of normalized vector) to the left (x2)
// if we walk along contour clockwise, this new contour is outside the old one (x2)
// (x2)
// inPt' is the intersection of the two lines parallel to the two (x2)
//  adjacent edges of inPt at a distance of 1 unit on the left side. (x2)
// good reading for geometry algorithms (here: line-line intersection) (x2)
// http://geomalgorithms.com/a05-_intersect-1.html (x2)
// check for collinear edges (x2)
// not collinear (x2)
// length of vectors for normalizing (x2)
// shift adjacent points by unit vectors to the left (x2)
// scaling factor for v_prev to intersection point (x2)
// vector from inPt to intersection point (x3)
// Don't normalize!, otherwise sharp corners become ugly (x2)
//  but prevent crazy spikes (x2)
// handle special case of collinear edges (x2)
// console.log("Warning: lines are a straight sequence"); (x3)
// console.log("Warning: lines are a straight spike"); (x3)
```

<details><summary>Code</summary>

```typescript
function getBevelVec( inPt, inPrev, inNext ) {

				// computes for inPt the corresponding point inPt' on a new contour
				//   shifted by 1 unit (length of normalized vector) to the left
				// if we walk along contour clockwise, this new contour is outside the old one
				//
				// inPt' is the intersection of the two lines parallel to the two
				//  adjacent edges of inPt at a distance of 1 unit on the left side.

				let v_trans_x, v_trans_y, shrink_by; // resulting translation vector for inPt

				// good reading for geometry algorithms (here: line-line intersection)
				// http://geomalgorithms.com/a05-_intersect-1.html

				const v_prev_x = inPt.x - inPrev.x,
					v_prev_y = inPt.y - inPrev.y;
				const v_next_x = inNext.x - inPt.x,
					v_next_y = inNext.y - inPt.y;

				const v_prev_lensq = ( v_prev_x * v_prev_x + v_prev_y * v_prev_y );

				// check for collinear edges
				const collinear0 = ( v_prev_x * v_next_y - v_prev_y * v_next_x );

				if ( Math.abs( collinear0 ) > Number.EPSILON ) {

					// not collinear

					// length of vectors for normalizing

					const v_prev_len = Math.sqrt( v_prev_lensq );
					const v_next_len = Math.sqrt( v_next_x * v_next_x + v_next_y * v_next_y );

					// shift adjacent points by unit vectors to the left

					const ptPrevShift_x = ( inPrev.x - v_prev_y / v_prev_len );
					const ptPrevShift_y = ( inPrev.y + v_prev_x / v_prev_len );

					const ptNextShift_x = ( inNext.x - v_next_y / v_next_len );
					const ptNextShift_y = ( inNext.y + v_next_x / v_next_len );

					// scaling factor for v_prev to intersection point

					const sf = ( ( ptNextShift_x - ptPrevShift_x ) * v_next_y -
							( ptNextShift_y - ptPrevShift_y ) * v_next_x ) /
						( v_prev_x * v_next_y - v_prev_y * v_next_x );

					// vector from inPt to intersection point

					v_trans_x = ( ptPrevShift_x + v_prev_x * sf - inPt.x );
					v_trans_y = ( ptPrevShift_y + v_prev_y * sf - inPt.y );

					// Don't normalize!, otherwise sharp corners become ugly
					//  but prevent crazy spikes
					const v_trans_lensq = ( v_trans_x * v_trans_x + v_trans_y * v_trans_y );
					if ( v_trans_lensq <= 2 ) {

						return new Vector2( v_trans_x, v_trans_y );

					} else {

						shrink_by = Math.sqrt( v_trans_lensq / 2 );

					}

				} else {

					// handle special case of collinear edges

					let direction_eq = false; // assumes: opposite

					if ( v_prev_x > Number.EPSILON ) {

						if ( v_next_x > Number.EPSILON ) {

							direction_eq = true;

						}

					} else {

						if ( v_prev_x < - Number.EPSILON ) {

							if ( v_next_x < - Number.EPSILON ) {

								direction_eq = true;

							}

						} else {

							if ( Math.sign( v_prev_y ) === Math.sign( v_next_y ) ) {

								direction_eq = true;

							}

						}

					}

					if ( direction_eq ) {

						// console.log("Warning: lines are a straight sequence");
						v_trans_x = - v_prev_y;
						v_trans_y = v_prev_x;
						shrink_by = Math.sqrt( v_prev_lensq );

					} else {

						// console.log("Warning: lines are a straight spike");
						v_trans_x = v_prev_x;
						v_trans_y = v_prev_y;
						shrink_by = Math.sqrt( v_prev_lensq / 2 );

					}

				}

				return new Vector2( v_trans_x / shrink_by, v_trans_y / shrink_by );

			}
```
</details>

### `buildLidFaces(): void`

**Returns:** `void`

**Calls:**

- `f3`
- `scope.addGroup`

**Internal Comments:**
```
// Bottom faces (x2)
// Top faces (x2)
```

<details><summary>Code</summary>

```typescript
function buildLidFaces() {

				const start = verticesArray.length / 3;

				if ( bevelEnabled ) {

					let layer = 0; // steps + 1
					let offset = vlen * layer;

					// Bottom faces

					for ( let i = 0; i < flen; i ++ ) {

						const face = faces[ i ];
						f3( face[ 2 ] + offset, face[ 1 ] + offset, face[ 0 ] + offset );

					}

					layer = steps + bevelSegments * 2;
					offset = vlen * layer;

					// Top faces

					for ( let i = 0; i < flen; i ++ ) {

						const face = faces[ i ];
						f3( face[ 0 ] + offset, face[ 1 ] + offset, face[ 2 ] + offset );

					}

				} else {

					// Bottom faces

					for ( let i = 0; i < flen; i ++ ) {

						const face = faces[ i ];
						f3( face[ 2 ], face[ 1 ], face[ 0 ] );

					}

					// Top faces

					for ( let i = 0; i < flen; i ++ ) {

						const face = faces[ i ];
						f3( face[ 0 ] + vlen * steps, face[ 1 ] + vlen * steps, face[ 2 ] + vlen * steps );

					}

				}

				scope.addGroup( start, verticesArray.length / 3 - start, 0 );

			}
```
</details>

### `buildSideFaces(): void`

**Returns:** `void`

**Calls:**

- `sidewalls`
- `scope.addGroup`

**Internal Comments:**
```
//, true (x3)
```

<details><summary>Code</summary>

```typescript
function buildSideFaces() {

				const start = verticesArray.length / 3;
				let layeroffset = 0;
				sidewalls( contour, layeroffset );
				layeroffset += contour.length;

				for ( let h = 0, hl = holes.length; h < hl; h ++ ) {

					const ahole = holes[ h ];
					sidewalls( ahole, layeroffset );

					//, true
					layeroffset += ahole.length;

				}


				scope.addGroup( start, verticesArray.length / 3 - start, 1 );


			}
```
</details>

### `sidewalls(contour: any, layeroffset: any): void`

**Parameters:**

- **`contour`** `any`
- **`layeroffset`** `any`

**Returns:** `void`

**Calls:**

- `f4`

**Internal Comments:**
```
//console.log('b', i,j, i-1, k,vertices.length);
```

<details><summary>Code</summary>

```typescript
function sidewalls( contour, layeroffset ) {

				let i = contour.length;

				while ( -- i >= 0 ) {

					const j = i;
					let k = i - 1;
					if ( k < 0 ) k = contour.length - 1;

					//console.log('b', i,j, i-1, k,vertices.length);

					for ( let s = 0, sl = ( steps + bevelSegments * 2 ); s < sl; s ++ ) {

						const slen1 = vlen * s;
						const slen2 = vlen * ( s + 1 );

						const a = layeroffset + j + slen1,
							b = layeroffset + k + slen1,
							c = layeroffset + k + slen2,
							d = layeroffset + j + slen2;

						f4( a, b, c, d );

					}

				}

			}
```
</details>

### `v(x: any, y: any, z: any): void`

**Parameters:**

- **`x`** `any`
- **`y`** `any`
- **`z`** `any`

**Returns:** `void`

**Calls:**

- `placeholder.push`

<details><summary>Code</summary>

```typescript
function v( x, y, z ) {

				placeholder.push( x );
				placeholder.push( y );
				placeholder.push( z );

			}
```
</details>

### `f3(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `addVertex`
- `uvgen.generateTopUV`
- `addUV`

<details><summary>Code</summary>

```typescript
function f3( a, b, c ) {

				addVertex( a );
				addVertex( b );
				addVertex( c );

				const nextIndex = verticesArray.length / 3;
				const uvs = uvgen.generateTopUV( scope, verticesArray, nextIndex - 3, nextIndex - 2, nextIndex - 1 );

				addUV( uvs[ 0 ] );
				addUV( uvs[ 1 ] );
				addUV( uvs[ 2 ] );

			}
```
</details>

### `f4(a: any, b: any, c: any, d: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`
- **`d`** `any`

**Returns:** `void`

**Calls:**

- `addVertex`
- `uvgen.generateSideWallUV`
- `addUV`

<details><summary>Code</summary>

```typescript
function f4( a, b, c, d ) {

				addVertex( a );
				addVertex( b );
				addVertex( d );

				addVertex( b );
				addVertex( c );
				addVertex( d );


				const nextIndex = verticesArray.length / 3;
				const uvs = uvgen.generateSideWallUV( scope, verticesArray, nextIndex - 6, nextIndex - 3, nextIndex - 2, nextIndex - 1 );

				addUV( uvs[ 0 ] );
				addUV( uvs[ 1 ] );
				addUV( uvs[ 3 ] );

				addUV( uvs[ 1 ] );
				addUV( uvs[ 2 ] );
				addUV( uvs[ 3 ] );

			}
```
</details>

### `addVertex(index: any): void`

**Parameters:**

- **`index`** `any`

**Returns:** `void`

**Calls:**

- `verticesArray.push`

<details><summary>Code</summary>

```typescript
function addVertex( index ) {

				verticesArray.push( placeholder[ index * 3 + 0 ] );
				verticesArray.push( placeholder[ index * 3 + 1 ] );
				verticesArray.push( placeholder[ index * 3 + 2 ] );

			}
```
</details>

### `addUV(vector2: any): void`

**Parameters:**

- **`vector2`** `any`

**Returns:** `void`

**Calls:**

- `uvArray.push`

<details><summary>Code</summary>

```typescript
function addUV( vector2 ) {

				uvArray.push( vector2.x );
				uvArray.push( vector2.y );

			}
```
</details>

### `generateTopUV(geometry: any, vertices: any, indexA: any, indexB: any, indexC: any): Vector2[]`

**Parameters:**

- **`geometry`** `any`
- **`vertices`** `any`
- **`indexA`** `any`
- **`indexB`** `any`
- **`indexC`** `any`

**Returns:** `Vector2[]`

<details><summary>Code</summary>

```typescript
function ( geometry, vertices, indexA, indexB, indexC ) {

		const a_x = vertices[ indexA * 3 ];
		const a_y = vertices[ indexA * 3 + 1 ];
		const b_x = vertices[ indexB * 3 ];
		const b_y = vertices[ indexB * 3 + 1 ];
		const c_x = vertices[ indexC * 3 ];
		const c_y = vertices[ indexC * 3 + 1 ];

		return [
			new Vector2( a_x, a_y ),
			new Vector2( b_x, b_y ),
			new Vector2( c_x, c_y )
		];

	}
```
</details>

### `generateSideWallUV(geometry: any, vertices: any, indexA: any, indexB: any, indexC: any, indexD: any): Vector2[]`

**Parameters:**

- **`geometry`** `any`
- **`vertices`** `any`
- **`indexA`** `any`
- **`indexB`** `any`
- **`indexC`** `any`
- **`indexD`** `any`

**Returns:** `Vector2[]`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
function ( geometry, vertices, indexA, indexB, indexC, indexD ) {

		const a_x = vertices[ indexA * 3 ];
		const a_y = vertices[ indexA * 3 + 1 ];
		const a_z = vertices[ indexA * 3 + 2 ];
		const b_x = vertices[ indexB * 3 ];
		const b_y = vertices[ indexB * 3 + 1 ];
		const b_z = vertices[ indexB * 3 + 2 ];
		const c_x = vertices[ indexC * 3 ];
		const c_y = vertices[ indexC * 3 + 1 ];
		const c_z = vertices[ indexC * 3 + 2 ];
		const d_x = vertices[ indexD * 3 ];
		const d_y = vertices[ indexD * 3 + 1 ];
		const d_z = vertices[ indexD * 3 + 2 ];

		if ( Math.abs( a_y - b_y ) < Math.abs( a_x - b_x ) ) {

			return [
				new Vector2( a_x, 1 - a_z ),
				new Vector2( b_x, 1 - b_z ),
				new Vector2( c_x, 1 - c_z ),
				new Vector2( d_x, 1 - d_z )
			];

		} else {

			return [
				new Vector2( a_y, 1 - a_z ),
				new Vector2( b_y, 1 - b_z ),
				new Vector2( c_y, 1 - c_z ),
				new Vector2( d_y, 1 - d_z )
			];

		}

	}
```
</details>

### `generateTopUV(geometry: any, vertices: any, indexA: any, indexB: any, indexC: any): Vector2[]`

**Parameters:**

- **`geometry`** `any`
- **`vertices`** `any`
- **`indexA`** `any`
- **`indexB`** `any`
- **`indexC`** `any`

**Returns:** `Vector2[]`

<details><summary>Code</summary>

```typescript
function ( geometry, vertices, indexA, indexB, indexC ) {

		const a_x = vertices[ indexA * 3 ];
		const a_y = vertices[ indexA * 3 + 1 ];
		const b_x = vertices[ indexB * 3 ];
		const b_y = vertices[ indexB * 3 + 1 ];
		const c_x = vertices[ indexC * 3 ];
		const c_y = vertices[ indexC * 3 + 1 ];

		return [
			new Vector2( a_x, a_y ),
			new Vector2( b_x, b_y ),
			new Vector2( c_x, c_y )
		];

	}
```
</details>

### `generateSideWallUV(geometry: any, vertices: any, indexA: any, indexB: any, indexC: any, indexD: any): Vector2[]`

**Parameters:**

- **`geometry`** `any`
- **`vertices`** `any`
- **`indexA`** `any`
- **`indexB`** `any`
- **`indexC`** `any`
- **`indexD`** `any`

**Returns:** `Vector2[]`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
function ( geometry, vertices, indexA, indexB, indexC, indexD ) {

		const a_x = vertices[ indexA * 3 ];
		const a_y = vertices[ indexA * 3 + 1 ];
		const a_z = vertices[ indexA * 3 + 2 ];
		const b_x = vertices[ indexB * 3 ];
		const b_y = vertices[ indexB * 3 + 1 ];
		const b_z = vertices[ indexB * 3 + 2 ];
		const c_x = vertices[ indexC * 3 ];
		const c_y = vertices[ indexC * 3 + 1 ];
		const c_z = vertices[ indexC * 3 + 2 ];
		const d_x = vertices[ indexD * 3 ];
		const d_y = vertices[ indexD * 3 + 1 ];
		const d_z = vertices[ indexD * 3 + 2 ];

		if ( Math.abs( a_y - b_y ) < Math.abs( a_x - b_x ) ) {

			return [
				new Vector2( a_x, 1 - a_z ),
				new Vector2( b_x, 1 - b_z ),
				new Vector2( c_x, 1 - c_z ),
				new Vector2( d_x, 1 - d_z )
			];

		} else {

			return [
				new Vector2( a_y, 1 - a_z ),
				new Vector2( b_y, 1 - b_z ),
				new Vector2( c_y, 1 - c_z ),
				new Vector2( d_y, 1 - d_z )
			];

		}

	}
```
</details>

### `generateTopUV(geometry: any, vertices: any, indexA: any, indexB: any, indexC: any): Vector2[]`

**Parameters:**

- **`geometry`** `any`
- **`vertices`** `any`
- **`indexA`** `any`
- **`indexB`** `any`
- **`indexC`** `any`

**Returns:** `Vector2[]`

<details><summary>Code</summary>

```typescript
function ( geometry, vertices, indexA, indexB, indexC ) {

		const a_x = vertices[ indexA * 3 ];
		const a_y = vertices[ indexA * 3 + 1 ];
		const b_x = vertices[ indexB * 3 ];
		const b_y = vertices[ indexB * 3 + 1 ];
		const c_x = vertices[ indexC * 3 ];
		const c_y = vertices[ indexC * 3 + 1 ];

		return [
			new Vector2( a_x, a_y ),
			new Vector2( b_x, b_y ),
			new Vector2( c_x, c_y )
		];

	}
```
</details>

### `generateSideWallUV(geometry: any, vertices: any, indexA: any, indexB: any, indexC: any, indexD: any): Vector2[]`

**Parameters:**

- **`geometry`** `any`
- **`vertices`** `any`
- **`indexA`** `any`
- **`indexB`** `any`
- **`indexC`** `any`
- **`indexD`** `any`

**Returns:** `Vector2[]`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
function ( geometry, vertices, indexA, indexB, indexC, indexD ) {

		const a_x = vertices[ indexA * 3 ];
		const a_y = vertices[ indexA * 3 + 1 ];
		const a_z = vertices[ indexA * 3 + 2 ];
		const b_x = vertices[ indexB * 3 ];
		const b_y = vertices[ indexB * 3 + 1 ];
		const b_z = vertices[ indexB * 3 + 2 ];
		const c_x = vertices[ indexC * 3 ];
		const c_y = vertices[ indexC * 3 + 1 ];
		const c_z = vertices[ indexC * 3 + 2 ];
		const d_x = vertices[ indexD * 3 ];
		const d_y = vertices[ indexD * 3 + 1 ];
		const d_z = vertices[ indexD * 3 + 2 ];

		if ( Math.abs( a_y - b_y ) < Math.abs( a_x - b_x ) ) {

			return [
				new Vector2( a_x, 1 - a_z ),
				new Vector2( b_x, 1 - b_z ),
				new Vector2( c_x, 1 - c_z ),
				new Vector2( d_x, 1 - d_z )
			];

		} else {

			return [
				new Vector2( a_y, 1 - a_z ),
				new Vector2( b_y, 1 - b_z ),
				new Vector2( c_y, 1 - c_z ),
				new Vector2( d_y, 1 - d_z )
			];

		}

	}
```
</details>

### `generateTopUV(geometry: any, vertices: any, indexA: any, indexB: any, indexC: any): Vector2[]`

**Parameters:**

- **`geometry`** `any`
- **`vertices`** `any`
- **`indexA`** `any`
- **`indexB`** `any`
- **`indexC`** `any`

**Returns:** `Vector2[]`

<details><summary>Code</summary>

```typescript
function ( geometry, vertices, indexA, indexB, indexC ) {

		const a_x = vertices[ indexA * 3 ];
		const a_y = vertices[ indexA * 3 + 1 ];
		const b_x = vertices[ indexB * 3 ];
		const b_y = vertices[ indexB * 3 + 1 ];
		const c_x = vertices[ indexC * 3 ];
		const c_y = vertices[ indexC * 3 + 1 ];

		return [
			new Vector2( a_x, a_y ),
			new Vector2( b_x, b_y ),
			new Vector2( c_x, c_y )
		];

	}
```
</details>

### `generateSideWallUV(geometry: any, vertices: any, indexA: any, indexB: any, indexC: any, indexD: any): Vector2[]`

**Parameters:**

- **`geometry`** `any`
- **`vertices`** `any`
- **`indexA`** `any`
- **`indexB`** `any`
- **`indexC`** `any`
- **`indexD`** `any`

**Returns:** `Vector2[]`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
function ( geometry, vertices, indexA, indexB, indexC, indexD ) {

		const a_x = vertices[ indexA * 3 ];
		const a_y = vertices[ indexA * 3 + 1 ];
		const a_z = vertices[ indexA * 3 + 2 ];
		const b_x = vertices[ indexB * 3 ];
		const b_y = vertices[ indexB * 3 + 1 ];
		const b_z = vertices[ indexB * 3 + 2 ];
		const c_x = vertices[ indexC * 3 ];
		const c_y = vertices[ indexC * 3 + 1 ];
		const c_z = vertices[ indexC * 3 + 2 ];
		const d_x = vertices[ indexD * 3 ];
		const d_y = vertices[ indexD * 3 + 1 ];
		const d_z = vertices[ indexD * 3 + 2 ];

		if ( Math.abs( a_y - b_y ) < Math.abs( a_x - b_x ) ) {

			return [
				new Vector2( a_x, 1 - a_z ),
				new Vector2( b_x, 1 - b_z ),
				new Vector2( c_x, 1 - c_z ),
				new Vector2( d_x, 1 - d_z )
			];

		} else {

			return [
				new Vector2( a_y, 1 - a_z ),
				new Vector2( b_y, 1 - b_z ),
				new Vector2( c_y, 1 - c_z ),
				new Vector2( d_y, 1 - d_z )
			];

		}

	}
```
</details>

### `generateTopUV(geometry: any, vertices: any, indexA: any, indexB: any, indexC: any): Vector2[]`

**Parameters:**

- **`geometry`** `any`
- **`vertices`** `any`
- **`indexA`** `any`
- **`indexB`** `any`
- **`indexC`** `any`

**Returns:** `Vector2[]`

<details><summary>Code</summary>

```typescript
function ( geometry, vertices, indexA, indexB, indexC ) {

		const a_x = vertices[ indexA * 3 ];
		const a_y = vertices[ indexA * 3 + 1 ];
		const b_x = vertices[ indexB * 3 ];
		const b_y = vertices[ indexB * 3 + 1 ];
		const c_x = vertices[ indexC * 3 ];
		const c_y = vertices[ indexC * 3 + 1 ];

		return [
			new Vector2( a_x, a_y ),
			new Vector2( b_x, b_y ),
			new Vector2( c_x, c_y )
		];

	}
```
</details>

### `generateSideWallUV(geometry: any, vertices: any, indexA: any, indexB: any, indexC: any, indexD: any): Vector2[]`

**Parameters:**

- **`geometry`** `any`
- **`vertices`** `any`
- **`indexA`** `any`
- **`indexB`** `any`
- **`indexC`** `any`
- **`indexD`** `any`

**Returns:** `Vector2[]`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
function ( geometry, vertices, indexA, indexB, indexC, indexD ) {

		const a_x = vertices[ indexA * 3 ];
		const a_y = vertices[ indexA * 3 + 1 ];
		const a_z = vertices[ indexA * 3 + 2 ];
		const b_x = vertices[ indexB * 3 ];
		const b_y = vertices[ indexB * 3 + 1 ];
		const b_z = vertices[ indexB * 3 + 2 ];
		const c_x = vertices[ indexC * 3 ];
		const c_y = vertices[ indexC * 3 + 1 ];
		const c_z = vertices[ indexC * 3 + 2 ];
		const d_x = vertices[ indexD * 3 ];
		const d_y = vertices[ indexD * 3 + 1 ];
		const d_z = vertices[ indexD * 3 + 2 ];

		if ( Math.abs( a_y - b_y ) < Math.abs( a_x - b_x ) ) {

			return [
				new Vector2( a_x, 1 - a_z ),
				new Vector2( b_x, 1 - b_z ),
				new Vector2( c_x, 1 - c_z ),
				new Vector2( d_x, 1 - d_z )
			];

		} else {

			return [
				new Vector2( a_y, 1 - a_z ),
				new Vector2( b_y, 1 - b_z ),
				new Vector2( c_y, 1 - c_z ),
				new Vector2( d_y, 1 - d_z )
			];

		}

	}
```
</details>

### `generateTopUV(geometry: any, vertices: any, indexA: any, indexB: any, indexC: any): Vector2[]`

**Parameters:**

- **`geometry`** `any`
- **`vertices`** `any`
- **`indexA`** `any`
- **`indexB`** `any`
- **`indexC`** `any`

**Returns:** `Vector2[]`

<details><summary>Code</summary>

```typescript
function ( geometry, vertices, indexA, indexB, indexC ) {

		const a_x = vertices[ indexA * 3 ];
		const a_y = vertices[ indexA * 3 + 1 ];
		const b_x = vertices[ indexB * 3 ];
		const b_y = vertices[ indexB * 3 + 1 ];
		const c_x = vertices[ indexC * 3 ];
		const c_y = vertices[ indexC * 3 + 1 ];

		return [
			new Vector2( a_x, a_y ),
			new Vector2( b_x, b_y ),
			new Vector2( c_x, c_y )
		];

	}
```
</details>

### `generateSideWallUV(geometry: any, vertices: any, indexA: any, indexB: any, indexC: any, indexD: any): Vector2[]`

**Parameters:**

- **`geometry`** `any`
- **`vertices`** `any`
- **`indexA`** `any`
- **`indexB`** `any`
- **`indexC`** `any`
- **`indexD`** `any`

**Returns:** `Vector2[]`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
function ( geometry, vertices, indexA, indexB, indexC, indexD ) {

		const a_x = vertices[ indexA * 3 ];
		const a_y = vertices[ indexA * 3 + 1 ];
		const a_z = vertices[ indexA * 3 + 2 ];
		const b_x = vertices[ indexB * 3 ];
		const b_y = vertices[ indexB * 3 + 1 ];
		const b_z = vertices[ indexB * 3 + 2 ];
		const c_x = vertices[ indexC * 3 ];
		const c_y = vertices[ indexC * 3 + 1 ];
		const c_z = vertices[ indexC * 3 + 2 ];
		const d_x = vertices[ indexD * 3 ];
		const d_y = vertices[ indexD * 3 + 1 ];
		const d_z = vertices[ indexD * 3 + 2 ];

		if ( Math.abs( a_y - b_y ) < Math.abs( a_x - b_x ) ) {

			return [
				new Vector2( a_x, 1 - a_z ),
				new Vector2( b_x, 1 - b_z ),
				new Vector2( c_x, 1 - c_z ),
				new Vector2( d_x, 1 - d_z )
			];

		} else {

			return [
				new Vector2( a_y, 1 - a_z ),
				new Vector2( b_y, 1 - b_z ),
				new Vector2( c_y, 1 - c_z ),
				new Vector2( d_y, 1 - d_z )
			];

		}

	}
```
</details>

### `toJSON(shapes: any, options: any, data: any): any`

**Parameters:**

- **`shapes`** `any`
- **`options`** `any`
- **`data`** `any`

**Returns:** `any`

**Calls:**

- `Array.isArray`
- `data.shapes.push`
- `Object.assign`
- `options.extrudePath.toJSON`

<details><summary>Code</summary>

```typescript
function toJSON( shapes, options, data ) {

	data.shapes = [];

	if ( Array.isArray( shapes ) ) {

		for ( let i = 0, l = shapes.length; i < l; i ++ ) {

			const shape = shapes[ i ];

			data.shapes.push( shape.uuid );

		}

	} else {

		data.shapes.push( shapes.uuid );

	}

	data.options = Object.assign( {}, options );

	if ( options.extrudePath !== undefined ) data.options.extrudePath = options.extrudePath.toJSON();

	return data;

}
```
</details>


---

## Classes

### `ExtrudeGeometry`

<details><summary>Class Code</summary>

```ts
class ExtrudeGeometry extends BufferGeometry {

	/**
	 * Constructs a new extrude geometry.
	 *
	 * @param {Shape|Array<Shape>} [shapes] - A shape or an array of shapes.
	 * @param {ExtrudeGeometry~Options} [options] - The extrude settings.
	 */
	constructor( shapes = new Shape( [ new Vector2( 0.5, 0.5 ), new Vector2( - 0.5, 0.5 ), new Vector2( - 0.5, - 0.5 ), new Vector2( 0.5, - 0.5 ) ] ), options = {} ) {

		super();

		this.type = 'ExtrudeGeometry';

		/**
		 * Holds the constructor parameters that have been
		 * used to generate the geometry. Any modification
		 * after instantiation does not change the geometry.
		 *
		 * @type {Object}
		 */
		this.parameters = {
			shapes: shapes,
			options: options
		};

		shapes = Array.isArray( shapes ) ? shapes : [ shapes ];

		const scope = this;

		const verticesArray = [];
		const uvArray = [];

		for ( let i = 0, l = shapes.length; i < l; i ++ ) {

			const shape = shapes[ i ];
			addShape( shape );

		}

		// build geometry

		this.setAttribute( 'position', new Float32BufferAttribute( verticesArray, 3 ) );
		this.setAttribute( 'uv', new Float32BufferAttribute( uvArray, 2 ) );

		this.computeVertexNormals();

		// functions

		function addShape( shape ) {

			const placeholder = [];

			// options

			const curveSegments = options.curveSegments !== undefined ? options.curveSegments : 12;
			const steps = options.steps !== undefined ? options.steps : 1;
			const depth = options.depth !== undefined ? options.depth : 1;

			let bevelEnabled = options.bevelEnabled !== undefined ? options.bevelEnabled : true;
			let bevelThickness = options.bevelThickness !== undefined ? options.bevelThickness : 0.2;
			let bevelSize = options.bevelSize !== undefined ? options.bevelSize : bevelThickness - 0.1;
			let bevelOffset = options.bevelOffset !== undefined ? options.bevelOffset : 0;
			let bevelSegments = options.bevelSegments !== undefined ? options.bevelSegments : 3;

			const extrudePath = options.extrudePath;

			const uvgen = options.UVGenerator !== undefined ? options.UVGenerator : WorldUVGenerator;

			//

			let extrudePts, extrudeByPath = false;
			let splineTube, binormal, normal, position2;

			if ( extrudePath ) {

				extrudePts = extrudePath.getSpacedPoints( steps );

				extrudeByPath = true;
				bevelEnabled = false; // bevels not supported for path extrusion

				// SETUP TNB variables

				// TODO1 - have a .isClosed in spline?

				splineTube = extrudePath.computeFrenetFrames( steps, false );

				// console.log(splineTube, 'splineTube', splineTube.normals.length, 'steps', steps, 'extrudePts', extrudePts.length);

				binormal = new Vector3();
				normal = new Vector3();
				position2 = new Vector3();

			}

			// Safeguards if bevels are not enabled

			if ( ! bevelEnabled ) {

				bevelSegments = 0;
				bevelThickness = 0;
				bevelSize = 0;
				bevelOffset = 0;

			}

			// Variables initialization

			const shapePoints = shape.extractPoints( curveSegments );

			let vertices = shapePoints.shape;
			const holes = shapePoints.holes;

			const reverse = ! ShapeUtils.isClockWise( vertices );

			if ( reverse ) {

				vertices = vertices.reverse();

				// Maybe we should also check if holes are in the opposite direction, just to be safe ...

				for ( let h = 0, hl = holes.length; h < hl; h ++ ) {

					const ahole = holes[ h ];

					if ( ShapeUtils.isClockWise( ahole ) ) {

						holes[ h ] = ahole.reverse();

					}

				}

			}

			/**Merges index-adjacent points that are within a threshold distance of each other. Array is modified in-place. Threshold distance is empirical, and scaled based on the magnitude of point coordinates.
			 * @param {Array<Vector2>} points
			*/
			function mergeOverlappingPoints( points ) {

				const THRESHOLD = 1e-10;
				const THRESHOLD_SQ = THRESHOLD * THRESHOLD;
				let prevPos = points[ 0 ];
				for ( let i = 1; i <= points.length; i ++ ) {

					const currentIndex = i % points.length;
					const currentPos = points[ currentIndex ];
					const dx = currentPos.x - prevPos.x;
					const dy = currentPos.y - prevPos.y;
					const distSq = dx * dx + dy * dy;

					const scalingFactorSqrt = Math.max(
						Math.abs( currentPos.x ),
						Math.abs( currentPos.y ),
						Math.abs( prevPos.x ),
						Math.abs( prevPos.y )
					);
					const thresholdSqScaled = THRESHOLD_SQ * scalingFactorSqrt * scalingFactorSqrt;
					if ( distSq <= thresholdSqScaled ) {

						points.splice( currentIndex, 1 );
						i --;
						continue;

					}

					prevPos = currentPos;

				}

			}

			mergeOverlappingPoints( vertices );
			holes.forEach( mergeOverlappingPoints );

			const numHoles = holes.length;

			/* Vertices */

			const contour = vertices; // vertices has all points but contour has only points of circumference

			for ( let h = 0; h < numHoles; h ++ ) {

				const ahole = holes[ h ];

				vertices = vertices.concat( ahole );

			}


			function scalePt2( pt, vec, size ) {

				if ( ! vec ) console.error( 'THREE.ExtrudeGeometry: vec does not exist' );

				return pt.clone().addScaledVector( vec, size );

			}

			const vlen = vertices.length;


			// Find directions for point movement


			function getBevelVec( inPt, inPrev, inNext ) {

				// computes for inPt the corresponding point inPt' on a new contour
				//   shifted by 1 unit (length of normalized vector) to the left
				// if we walk along contour clockwise, this new contour is outside the old one
				//
				// inPt' is the intersection of the two lines parallel to the two
				//  adjacent edges of inPt at a distance of 1 unit on the left side.

				let v_trans_x, v_trans_y, shrink_by; // resulting translation vector for inPt

				// good reading for geometry algorithms (here: line-line intersection)
				// http://geomalgorithms.com/a05-_intersect-1.html

				const v_prev_x = inPt.x - inPrev.x,
					v_prev_y = inPt.y - inPrev.y;
				const v_next_x = inNext.x - inPt.x,
					v_next_y = inNext.y - inPt.y;

				const v_prev_lensq = ( v_prev_x * v_prev_x + v_prev_y * v_prev_y );

				// check for collinear edges
				const collinear0 = ( v_prev_x * v_next_y - v_prev_y * v_next_x );

				if ( Math.abs( collinear0 ) > Number.EPSILON ) {

					// not collinear

					// length of vectors for normalizing

					const v_prev_len = Math.sqrt( v_prev_lensq );
					const v_next_len = Math.sqrt( v_next_x * v_next_x + v_next_y * v_next_y );

					// shift adjacent points by unit vectors to the left

					const ptPrevShift_x = ( inPrev.x - v_prev_y / v_prev_len );
					const ptPrevShift_y = ( inPrev.y + v_prev_x / v_prev_len );

					const ptNextShift_x = ( inNext.x - v_next_y / v_next_len );
					const ptNextShift_y = ( inNext.y + v_next_x / v_next_len );

					// scaling factor for v_prev to intersection point

					const sf = ( ( ptNextShift_x - ptPrevShift_x ) * v_next_y -
							( ptNextShift_y - ptPrevShift_y ) * v_next_x ) /
						( v_prev_x * v_next_y - v_prev_y * v_next_x );

					// vector from inPt to intersection point

					v_trans_x = ( ptPrevShift_x + v_prev_x * sf - inPt.x );
					v_trans_y = ( ptPrevShift_y + v_prev_y * sf - inPt.y );

					// Don't normalize!, otherwise sharp corners become ugly
					//  but prevent crazy spikes
					const v_trans_lensq = ( v_trans_x * v_trans_x + v_trans_y * v_trans_y );
					if ( v_trans_lensq <= 2 ) {

						return new Vector2( v_trans_x, v_trans_y );

					} else {

						shrink_by = Math.sqrt( v_trans_lensq / 2 );

					}

				} else {

					// handle special case of collinear edges

					let direction_eq = false; // assumes: opposite

					if ( v_prev_x > Number.EPSILON ) {

						if ( v_next_x > Number.EPSILON ) {

							direction_eq = true;

						}

					} else {

						if ( v_prev_x < - Number.EPSILON ) {

							if ( v_next_x < - Number.EPSILON ) {

								direction_eq = true;

							}

						} else {

							if ( Math.sign( v_prev_y ) === Math.sign( v_next_y ) ) {

								direction_eq = true;

							}

						}

					}

					if ( direction_eq ) {

						// console.log("Warning: lines are a straight sequence");
						v_trans_x = - v_prev_y;
						v_trans_y = v_prev_x;
						shrink_by = Math.sqrt( v_prev_lensq );

					} else {

						// console.log("Warning: lines are a straight spike");
						v_trans_x = v_prev_x;
						v_trans_y = v_prev_y;
						shrink_by = Math.sqrt( v_prev_lensq / 2 );

					}

				}

				return new Vector2( v_trans_x / shrink_by, v_trans_y / shrink_by );

			}


			const contourMovements = [];

			for ( let i = 0, il = contour.length, j = il - 1, k = i + 1; i < il; i ++, j ++, k ++ ) {

				if ( j === il ) j = 0;
				if ( k === il ) k = 0;

				//  (j)---(i)---(k)
				// console.log('i,j,k', i, j , k)

				contourMovements[ i ] = getBevelVec( contour[ i ], contour[ j ], contour[ k ] );

			}

			const holesMovements = [];
			let oneHoleMovements, verticesMovements = contourMovements.concat();

			for ( let h = 0, hl = numHoles; h < hl; h ++ ) {

				const ahole = holes[ h ];

				oneHoleMovements = [];

				for ( let i = 0, il = ahole.length, j = il - 1, k = i + 1; i < il; i ++, j ++, k ++ ) {

					if ( j === il ) j = 0;
					if ( k === il ) k = 0;

					//  (j)---(i)---(k)
					oneHoleMovements[ i ] = getBevelVec( ahole[ i ], ahole[ j ], ahole[ k ] );

				}

				holesMovements.push( oneHoleMovements );
				verticesMovements = verticesMovements.concat( oneHoleMovements );

			}

			let faces;

			if ( bevelSegments === 0 ) {

				faces = ShapeUtils.triangulateShape( contour, holes );

			} else {

				const contractedContourVertices = [];
				const expandedHoleVertices = [];

				// Loop bevelSegments, 1 for the front, 1 for the back

				for ( let b = 0; b < bevelSegments; b ++ ) {

					//for ( b = bevelSegments; b > 0; b -- ) {

					const t = b / bevelSegments;
					const z = bevelThickness * Math.cos( t * Math.PI / 2 );
					const bs = bevelSize * Math.sin( t * Math.PI / 2 ) + bevelOffset;

					// contract shape

					for ( let i = 0, il = contour.length; i < il; i ++ ) {

						const vert = scalePt2( contour[ i ], contourMovements[ i ], bs );

						v( vert.x, vert.y, - z );
						if ( t === 0 ) contractedContourVertices.push( vert );

					}

					// expand holes

					for ( let h = 0, hl = numHoles; h < hl; h ++ ) {

						const ahole = holes[ h ];
						oneHoleMovements = holesMovements[ h ];
						const oneHoleVertices = [];
						for ( let i = 0, il = ahole.length; i < il; i ++ ) {

							const vert = scalePt2( ahole[ i ], oneHoleMovements[ i ], bs );

							v( vert.x, vert.y, - z );
							if ( t === 0 ) oneHoleVertices.push( vert );

						}

						if ( t === 0 ) expandedHoleVertices.push( oneHoleVertices );

					}

				}

				faces = ShapeUtils.triangulateShape( contractedContourVertices, expandedHoleVertices );

			}

			const flen = faces.length;

			const bs = bevelSize + bevelOffset;

			// Back facing vertices

			for ( let i = 0; i < vlen; i ++ ) {

				const vert = bevelEnabled ? scalePt2( vertices[ i ], verticesMovements[ i ], bs ) : vertices[ i ];

				if ( ! extrudeByPath ) {

					v( vert.x, vert.y, 0 );

				} else {

					// v( vert.x, vert.y + extrudePts[ 0 ].y, extrudePts[ 0 ].x );

					normal.copy( splineTube.normals[ 0 ] ).multiplyScalar( vert.x );
					binormal.copy( splineTube.binormals[ 0 ] ).multiplyScalar( vert.y );

					position2.copy( extrudePts[ 0 ] ).add( normal ).add( binormal );

					v( position2.x, position2.y, position2.z );

				}

			}

			// Add stepped vertices...
			// Including front facing vertices

			for ( let s = 1; s <= steps; s ++ ) {

				for ( let i = 0; i < vlen; i ++ ) {

					const vert = bevelEnabled ? scalePt2( vertices[ i ], verticesMovements[ i ], bs ) : vertices[ i ];

					if ( ! extrudeByPath ) {

						v( vert.x, vert.y, depth / steps * s );

					} else {

						// v( vert.x, vert.y + extrudePts[ s - 1 ].y, extrudePts[ s - 1 ].x );

						normal.copy( splineTube.normals[ s ] ).multiplyScalar( vert.x );
						binormal.copy( splineTube.binormals[ s ] ).multiplyScalar( vert.y );

						position2.copy( extrudePts[ s ] ).add( normal ).add( binormal );

						v( position2.x, position2.y, position2.z );

					}

				}

			}


			// Add bevel segments planes

			//for ( b = 1; b <= bevelSegments; b ++ ) {
			for ( let b = bevelSegments - 1; b >= 0; b -- ) {

				const t = b / bevelSegments;
				const z = bevelThickness * Math.cos( t * Math.PI / 2 );
				const bs = bevelSize * Math.sin( t * Math.PI / 2 ) + bevelOffset;

				// contract shape

				for ( let i = 0, il = contour.length; i < il; i ++ ) {

					const vert = scalePt2( contour[ i ], contourMovements[ i ], bs );
					v( vert.x, vert.y, depth + z );

				}

				// expand holes

				for ( let h = 0, hl = holes.length; h < hl; h ++ ) {

					const ahole = holes[ h ];
					oneHoleMovements = holesMovements[ h ];

					for ( let i = 0, il = ahole.length; i < il; i ++ ) {

						const vert = scalePt2( ahole[ i ], oneHoleMovements[ i ], bs );

						if ( ! extrudeByPath ) {

							v( vert.x, vert.y, depth + z );

						} else {

							v( vert.x, vert.y + extrudePts[ steps - 1 ].y, extrudePts[ steps - 1 ].x + z );

						}

					}

				}

			}

			/* Faces */

			// Top and bottom faces

			buildLidFaces();

			// Sides faces

			buildSideFaces();


			/////  Internal functions

			function buildLidFaces() {

				const start = verticesArray.length / 3;

				if ( bevelEnabled ) {

					let layer = 0; // steps + 1
					let offset = vlen * layer;

					// Bottom faces

					for ( let i = 0; i < flen; i ++ ) {

						const face = faces[ i ];
						f3( face[ 2 ] + offset, face[ 1 ] + offset, face[ 0 ] + offset );

					}

					layer = steps + bevelSegments * 2;
					offset = vlen * layer;

					// Top faces

					for ( let i = 0; i < flen; i ++ ) {

						const face = faces[ i ];
						f3( face[ 0 ] + offset, face[ 1 ] + offset, face[ 2 ] + offset );

					}

				} else {

					// Bottom faces

					for ( let i = 0; i < flen; i ++ ) {

						const face = faces[ i ];
						f3( face[ 2 ], face[ 1 ], face[ 0 ] );

					}

					// Top faces

					for ( let i = 0; i < flen; i ++ ) {

						const face = faces[ i ];
						f3( face[ 0 ] + vlen * steps, face[ 1 ] + vlen * steps, face[ 2 ] + vlen * steps );

					}

				}

				scope.addGroup( start, verticesArray.length / 3 - start, 0 );

			}

			// Create faces for the z-sides of the shape

			function buildSideFaces() {

				const start = verticesArray.length / 3;
				let layeroffset = 0;
				sidewalls( contour, layeroffset );
				layeroffset += contour.length;

				for ( let h = 0, hl = holes.length; h < hl; h ++ ) {

					const ahole = holes[ h ];
					sidewalls( ahole, layeroffset );

					//, true
					layeroffset += ahole.length;

				}


				scope.addGroup( start, verticesArray.length / 3 - start, 1 );


			}

			function sidewalls( contour, layeroffset ) {

				let i = contour.length;

				while ( -- i >= 0 ) {

					const j = i;
					let k = i - 1;
					if ( k < 0 ) k = contour.length - 1;

					//console.log('b', i,j, i-1, k,vertices.length);

					for ( let s = 0, sl = ( steps + bevelSegments * 2 ); s < sl; s ++ ) {

						const slen1 = vlen * s;
						const slen2 = vlen * ( s + 1 );

						const a = layeroffset + j + slen1,
							b = layeroffset + k + slen1,
							c = layeroffset + k + slen2,
							d = layeroffset + j + slen2;

						f4( a, b, c, d );

					}

				}

			}

			function v( x, y, z ) {

				placeholder.push( x );
				placeholder.push( y );
				placeholder.push( z );

			}


			function f3( a, b, c ) {

				addVertex( a );
				addVertex( b );
				addVertex( c );

				const nextIndex = verticesArray.length / 3;
				const uvs = uvgen.generateTopUV( scope, verticesArray, nextIndex - 3, nextIndex - 2, nextIndex - 1 );

				addUV( uvs[ 0 ] );
				addUV( uvs[ 1 ] );
				addUV( uvs[ 2 ] );

			}

			function f4( a, b, c, d ) {

				addVertex( a );
				addVertex( b );
				addVertex( d );

				addVertex( b );
				addVertex( c );
				addVertex( d );


				const nextIndex = verticesArray.length / 3;
				const uvs = uvgen.generateSideWallUV( scope, verticesArray, nextIndex - 6, nextIndex - 3, nextIndex - 2, nextIndex - 1 );

				addUV( uvs[ 0 ] );
				addUV( uvs[ 1 ] );
				addUV( uvs[ 3 ] );

				addUV( uvs[ 1 ] );
				addUV( uvs[ 2 ] );
				addUV( uvs[ 3 ] );

			}

			function addVertex( index ) {

				verticesArray.push( placeholder[ index * 3 + 0 ] );
				verticesArray.push( placeholder[ index * 3 + 1 ] );
				verticesArray.push( placeholder[ index * 3 + 2 ] );

			}


			function addUV( vector2 ) {

				uvArray.push( vector2.x );
				uvArray.push( vector2.y );

			}

		}

	}

	copy( source ) {

		super.copy( source );

		this.parameters = Object.assign( {}, source.parameters );

		return this;

	}

	toJSON() {

		const data = super.toJSON();

		const shapes = this.parameters.shapes;
		const options = this.parameters.options;

		return toJSON( shapes, options, data );

	}

	/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @param {Array<Shape>} shapes - An array of shapes.
	 * @return {ExtrudeGeometry} A new instance.
	 */
	static fromJSON( data, shapes ) {

		const geometryShapes = [];

		for ( let j = 0, jl = data.shapes.length; j < jl; j ++ ) {

			const shape = shapes[ data.shapes[ j ] ];

			geometryShapes.push( shape );

		}

		const extrudePath = data.options.extrudePath;

		if ( extrudePath !== undefined ) {

			data.options.extrudePath = new Curves[ extrudePath.type ]().fromJSON( extrudePath );

		}

		return new ExtrudeGeometry( geometryShapes, data.options );

	}

}
```
</details>

#### Methods

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source );

		this.parameters = Object.assign( {}, source.parameters );

		return this;

	}
```
</details>

##### `toJSON(): any`

<details><summary>Code</summary>

```ts
toJSON() {

		const data = super.toJSON();

		const shapes = this.parameters.shapes;
		const options = this.parameters.options;

		return toJSON( shapes, options, data );

	}
```
</details>

##### `fromJSON(data: any, shapes: Shape[]): ExtrudeGeometry`

<details><summary>Code</summary>

```ts
static fromJSON( data, shapes ) {

		const geometryShapes = [];

		for ( let j = 0, jl = data.shapes.length; j < jl; j ++ ) {

			const shape = shapes[ data.shapes[ j ] ];

			geometryShapes.push( shape );

		}

		const extrudePath = data.options.extrudePath;

		if ( extrudePath !== undefined ) {

			data.options.extrudePath = new Curves[ extrudePath.type ]().fromJSON( extrudePath );

		}

		return new ExtrudeGeometry( geometryShapes, data.options );

	}
```
</details>


---