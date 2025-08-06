[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Curve.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 15 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 29 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/extras/core/Curve.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `clamp` | `../../math/MathUtils.js` |
| `Vector2` | `../../math/Vector2.js` |
| `Vector3` | `../../math/Vector3.js` |
| `Matrix4` | `../../math/Matrix4.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `points` | `any[]` | let/var | `[]` | ✗ |
| `points` | `any[]` | let/var | `[]` | ✗ |
| `cache` | `any[]` | let/var | `[]` | ✗ |
| `current` | `any` | let/var | `*not shown*` | ✗ |
| `sum` | `number` | let/var | `0` | ✗ |
| `i` | `number` | let/var | `0` | ✗ |
| `il` | `number` | let/var | `arcLengths.length` | ✗ |
| `targetArcLength` | `any` | let/var | `*not shown*` | ✗ |
| `low` | `number` | let/var | `0` | ✗ |
| `high` | `number` | let/var | `il - 1` | ✗ |
| `comparison` | `any` | let/var | `*not shown*` | ✗ |
| `lengthBefore` | `number` | let/var | `arcLengths[ i ]` | ✗ |
| `lengthAfter` | `number` | let/var | `arcLengths[ i + 1 ]` | ✗ |
| `segmentLength` | `number` | let/var | `lengthAfter - lengthBefore` | ✗ |
| `segmentFraction` | `number` | let/var | `( targetArcLength - lengthBefore ) / segmentLength` | ✗ |
| `t` | `number` | let/var | `( i + segmentFraction ) / ( il - 1 )` | ✗ |
| `delta` | `0.0001` | let/var | `0.0001` | ✗ |
| `t1` | `number` | let/var | `t - delta` | ✗ |
| `t2` | `number` | let/var | `t + delta` | ✗ |
| `tangent` | `Vector2 \| Vector3` | let/var | `optionalTarget \|\| ( ( pt1.isVector2 ) ? new Vector2() : new Vector3() )` | ✗ |
| `normal` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `tangents` | `any[]` | let/var | `[]` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `binormals` | `any[]` | let/var | `[]` | ✗ |
| `vec` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `mat` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `u` | `number` | let/var | `i / segments` | ✗ |
| `min` | `number` | let/var | `Number.MAX_VALUE` | ✗ |
| `data` | `{ metadata: { version: number; type: ...` | let/var | `{ metadata: { version: 4.7, type: 'Curve', generator: 'Curve.toJSON' } }` | ✗ |


---

## Functions

### `Curve.getPoint(): Vector2 | Vector3`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 2D or 3D space (depending on the curve definition)
	 * for the given interpolation factor.
	 *
	 * @abstract
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {(Vector2|Vector3)} [optionalTarget] - The optional target vector the result is written to.
	 * @return {(Vector2|Vector3)} The position on the curve. It can be a 2D or 3D vector depending on the curve definition.
	 */
```

**Returns:** `Vector2 | Vector3`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
getPoint( /* t, optionalTarget */ ) {

		console.warn( 'THREE.Curve: .getPoint() not implemented.' );

	}
```
</details>

### `Curve.getPointAt(u: number, optionalTarget: Vector2 | Vector3): Vector2 | Vector3`

**JSDoc:**
```typescript
/**
	 * This method returns a vector in 2D or 3D space (depending on the curve definition)
	 * for the given interpolation factor. Unlike {@link Curve#getPoint}, this method honors the length
	 * of the curve which equidistant samples.
	 *
	 * @param {number} u - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {(Vector2|Vector3)} [optionalTarget] - The optional target vector the result is written to.
	 * @return {(Vector2|Vector3)} The position on the curve. It can be a 2D or 3D vector depending on the curve definition.
	 */
```

**Parameters:**

- **`u`** `number`
- **`optionalTarget`** `Vector2 | Vector3`

**Returns:** `Vector2 | Vector3`

**Calls:**

- `this.getUtoTmapping`
- `this.getPoint`

<details><summary>Code</summary>

```typescript
getPointAt( u, optionalTarget ) {

		const t = this.getUtoTmapping( u );
		return this.getPoint( t, optionalTarget );

	}
```
</details>

### `Curve.getPoints(divisions: number): (Vector2 | Vector3)[]`

**JSDoc:**
```typescript
/**
	 * This method samples the curve via {@link Curve#getPoint} and returns an array of points representing
	 * the curve shape.
	 *
	 * @param {number} [divisions=5] - The number of divisions.
	 * @return {Array<(Vector2|Vector3)>} An array holding the sampled curve values. The number of points is `divisions + 1`.
	 */
```

**Parameters:**

- **`divisions`** `number`

**Returns:** `(Vector2 | Vector3)[]`

**Calls:**

- `points.push`
- `this.getPoint`

<details><summary>Code</summary>

```typescript
getPoints( divisions = 5 ) {

		const points = [];

		for ( let d = 0; d <= divisions; d ++ ) {

			points.push( this.getPoint( d / divisions ) );

		}

		return points;

	}
```
</details>

### `Curve.getSpacedPoints(divisions: number): (Vector2 | Vector3)[]`

**JSDoc:**
```typescript
/**
	 * This method samples the curve via {@link Curve#getPointAt} and returns an array of points representing
	 * the curve shape. Unlike {@link Curve#getPoints}, this method returns equi-spaced points across the entire
	 * curve.
	 *
	 * @param {number} [divisions=5] - The number of divisions.
	 * @return {Array<(Vector2|Vector3)>} An array holding the sampled curve values. The number of points is `divisions + 1`.
	 */
```

**Parameters:**

- **`divisions`** `number`

**Returns:** `(Vector2 | Vector3)[]`

**Calls:**

- `points.push`
- `this.getPointAt`

<details><summary>Code</summary>

```typescript
getSpacedPoints( divisions = 5 ) {

		const points = [];

		for ( let d = 0; d <= divisions; d ++ ) {

			points.push( this.getPointAt( d / divisions ) );

		}

		return points;

	}
```
</details>

### `Curve.getLength(): number`

**JSDoc:**
```typescript
/**
	 * Returns the total arc length of the curve.
	 *
	 * @return {number} The length of the curve.
	 */
```

**Returns:** `number`

**Calls:**

- `this.getLengths`

<details><summary>Code</summary>

```typescript
getLength() {

		const lengths = this.getLengths();
		return lengths[ lengths.length - 1 ];

	}
```
</details>

### `Curve.getLengths(divisions: number): number[]`

**JSDoc:**
```typescript
/**
	 * Returns an array of cumulative segment lengths of the curve.
	 *
	 * @param {number} [divisions=this.arcLengthDivisions] - The number of divisions.
	 * @return {Array<number>} An array holding the cumulative segment lengths.
	 */
```

**Parameters:**

- **`divisions`** `number`

**Returns:** `number[]`

**Calls:**

- `this.getPoint`
- `cache.push`
- `current.distanceTo`

<details><summary>Code</summary>

```typescript
getLengths( divisions = this.arcLengthDivisions ) {

		if ( this.cacheArcLengths &&
			( this.cacheArcLengths.length === divisions + 1 ) &&
			! this.needsUpdate ) {

			return this.cacheArcLengths;

		}

		this.needsUpdate = false;

		const cache = [];
		let current, last = this.getPoint( 0 );
		let sum = 0;

		cache.push( 0 );

		for ( let p = 1; p <= divisions; p ++ ) {

			current = this.getPoint( p / divisions );
			sum += current.distanceTo( last );
			cache.push( sum );
			last = current;

		}

		this.cacheArcLengths = cache;

		return cache; // { sums: cache, sum: sum }; Sum is in the last element.

	}
```
</details>

### `Curve.updateArcLengths(): void`

**JSDoc:**
```typescript
/**
	 * Update the cumulative segment distance cache. The method must be called
	 * every time curve parameters are changed. If an updated curve is part of a
	 * composed curve like {@link CurvePath}, this method must be called on the
	 * composed curve, too.
	 */
```

**Returns:** `void`

**Calls:**

- `this.getLengths`

<details><summary>Code</summary>

```typescript
updateArcLengths() {

		this.needsUpdate = true;
		this.getLengths();

	}
```
</details>

### `Curve.getUtoTmapping(u: number, distance: number): number`

**JSDoc:**
```typescript
/**
	 * Given an interpolation factor in the range `[0,1]`, this method returns an updated
	 * interpolation factor in the same range that can be ued to sample equidistant points
	 * from a curve.
	 *
	 * @param {number} u - The interpolation factor.
	 * @param {?number} distance - An optional distance on the curve.
	 * @return {number} The updated interpolation factor.
	 */
```

**Parameters:**

- **`u`** `number`
- **`distance`** `number`

**Returns:** `number`

**Calls:**

- `this.getLengths`
- `Math.floor`

**Internal Comments:**
```
// binary search for the index with largest value smaller than target u distance (x2)
// we could get finer grain at lengths, or use simple interpolation between two points (x2)
// determine where we are between the 'before' and 'after' points (x2)
// add that fractional amount to t (x2)
```

<details><summary>Code</summary>

```typescript
getUtoTmapping( u, distance = null ) {

		const arcLengths = this.getLengths();

		let i = 0;
		const il = arcLengths.length;

		let targetArcLength; // The targeted u distance value to get

		if ( distance ) {

			targetArcLength = distance;

		} else {

			targetArcLength = u * arcLengths[ il - 1 ];

		}

		// binary search for the index with largest value smaller than target u distance

		let low = 0, high = il - 1, comparison;

		while ( low <= high ) {

			i = Math.floor( low + ( high - low ) / 2 ); // less likely to overflow, though probably not issue here, JS doesn't really have integers, all numbers are floats

			comparison = arcLengths[ i ] - targetArcLength;

			if ( comparison < 0 ) {

				low = i + 1;

			} else if ( comparison > 0 ) {

				high = i - 1;

			} else {

				high = i;
				break;

				// DONE

			}

		}

		i = high;

		if ( arcLengths[ i ] === targetArcLength ) {

			return i / ( il - 1 );

		}

		// we could get finer grain at lengths, or use simple interpolation between two points

		const lengthBefore = arcLengths[ i ];
		const lengthAfter = arcLengths[ i + 1 ];

		const segmentLength = lengthAfter - lengthBefore;

		// determine where we are between the 'before' and 'after' points

		const segmentFraction = ( targetArcLength - lengthBefore ) / segmentLength;

		// add that fractional amount to t

		const t = ( i + segmentFraction ) / ( il - 1 );

		return t;

	}
```
</details>

### `Curve.getTangent(t: number, optionalTarget: Vector2 | Vector3): Vector2 | Vector3`

**JSDoc:**
```typescript
/**
	 * Returns a unit vector tangent for the given interpolation factor.
	 * If the derived curve does not implement its tangent derivation,
	 * two points a small delta apart will be used to find its gradient
	 * which seems to give a reasonable approximation.
	 *
	 * @param {number} t - The interpolation factor.
	 * @param {(Vector2|Vector3)} [optionalTarget] - The optional target vector the result is written to.
	 * @return {(Vector2|Vector3)} The tangent vector.
	 */
```

**Parameters:**

- **`t`** `number`
- **`optionalTarget`** `Vector2 | Vector3`

**Returns:** `Vector2 | Vector3`

**Calls:**

- `this.getPoint`
- `tangent.copy( pt2 ).sub( pt1 ).normalize`

**Internal Comments:**
```
// Capping in case of danger
```

<details><summary>Code</summary>

```typescript
getTangent( t, optionalTarget ) {

		const delta = 0.0001;
		let t1 = t - delta;
		let t2 = t + delta;

		// Capping in case of danger

		if ( t1 < 0 ) t1 = 0;
		if ( t2 > 1 ) t2 = 1;

		const pt1 = this.getPoint( t1 );
		const pt2 = this.getPoint( t2 );

		const tangent = optionalTarget || ( ( pt1.isVector2 ) ? new Vector2() : new Vector3() );

		tangent.copy( pt2 ).sub( pt1 ).normalize();

		return tangent;

	}
```
</details>

### `Curve.getTangentAt(u: number, optionalTarget: Vector2 | Vector3): Vector2 | Vector3`

**JSDoc:**
```typescript
/**
	 * Same as {@link Curve#getTangent} but with equidistant samples.
	 *
	 * @param {number} u - The interpolation factor.
	 * @param {(Vector2|Vector3)} [optionalTarget] - The optional target vector the result is written to.
	 * @return {(Vector2|Vector3)} The tangent vector.
	 * @see {@link Curve#getPointAt}
	 */
```

**Parameters:**

- **`u`** `number`
- **`optionalTarget`** `Vector2 | Vector3`

**Returns:** `Vector2 | Vector3`

**Calls:**

- `this.getUtoTmapping`
- `this.getTangent`

<details><summary>Code</summary>

```typescript
getTangentAt( u, optionalTarget ) {

		const t = this.getUtoTmapping( u );
		return this.getTangent( t, optionalTarget );

	}
```
</details>

### `Curve.computeFrenetFrames(segments: number, closed: boolean): { tangents: Vector3[]; normals: Vector3[]; binormals: Vector3[]; }`

**JSDoc:**
```typescript
/**
	 * Generates the Frenet Frames. Requires a curve definition in 3D space. Used
	 * in geometries like {@link TubeGeometry} or {@link ExtrudeGeometry}.
	 *
	 * @param {number} segments - The number of segments.
	 * @param {boolean} [closed=false] - Whether the curve is closed or not.
	 * @return {{tangents: Array<Vector3>, normals: Array<Vector3>, binormals: Array<Vector3>}} The Frenet Frames.
	 */
```

**Parameters:**

- **`segments`** `number`
- **`closed`** `boolean`

**Returns:** `{ tangents: Vector3[]; normals: Vector3[]; binormals: Vector3[]; }`

**Calls:**

- `this.getTangentAt`
- `Math.abs`
- `normal.set`
- `vec.crossVectors( tangents[ 0 ], normal ).normalize`
- `normals[ 0 ].crossVectors`
- `binormals[ 0 ].crossVectors`
- `normals[ i - 1 ].clone`
- `binormals[ i - 1 ].clone`
- `vec.crossVectors`
- `vec.length`
- `vec.normalize`
- `Math.acos`
- `clamp (from ../../math/MathUtils.js)`
- `tangents[ i - 1 ].dot`
- `normals[ i ].applyMatrix4`
- `mat.makeRotationAxis`
- `binormals[ i ].crossVectors`
- `normals[ 0 ].dot`
- `tangents[ 0 ].dot`

**Internal Comments:**
```
// see http://www.cs.indiana.edu/pub/techreports/TR425.pdf (x2)
// compute the tangent vectors for each segment on the curve
// select an initial normal vector perpendicular to the first tangent vector, (x4)
// and in the direction of the minimum tangent xyz component (x4)
// compute the slowly-varying normal and binormal vectors for each segment on the curve
// if the curve is closed, postprocess the vectors so the first and last normal vectors are the same
// twist a little... (x5)
```

<details><summary>Code</summary>

```typescript
computeFrenetFrames( segments, closed = false ) {

		// see http://www.cs.indiana.edu/pub/techreports/TR425.pdf

		const normal = new Vector3();

		const tangents = [];
		const normals = [];
		const binormals = [];

		const vec = new Vector3();
		const mat = new Matrix4();

		// compute the tangent vectors for each segment on the curve

		for ( let i = 0; i <= segments; i ++ ) {

			const u = i / segments;

			tangents[ i ] = this.getTangentAt( u, new Vector3() );

		}

		// select an initial normal vector perpendicular to the first tangent vector,
		// and in the direction of the minimum tangent xyz component

		normals[ 0 ] = new Vector3();
		binormals[ 0 ] = new Vector3();
		let min = Number.MAX_VALUE;
		const tx = Math.abs( tangents[ 0 ].x );
		const ty = Math.abs( tangents[ 0 ].y );
		const tz = Math.abs( tangents[ 0 ].z );

		if ( tx <= min ) {

			min = tx;
			normal.set( 1, 0, 0 );

		}

		if ( ty <= min ) {

			min = ty;
			normal.set( 0, 1, 0 );

		}

		if ( tz <= min ) {

			normal.set( 0, 0, 1 );

		}

		vec.crossVectors( tangents[ 0 ], normal ).normalize();

		normals[ 0 ].crossVectors( tangents[ 0 ], vec );
		binormals[ 0 ].crossVectors( tangents[ 0 ], normals[ 0 ] );


		// compute the slowly-varying normal and binormal vectors for each segment on the curve

		for ( let i = 1; i <= segments; i ++ ) {

			normals[ i ] = normals[ i - 1 ].clone();

			binormals[ i ] = binormals[ i - 1 ].clone();

			vec.crossVectors( tangents[ i - 1 ], tangents[ i ] );

			if ( vec.length() > Number.EPSILON ) {

				vec.normalize();

				const theta = Math.acos( clamp( tangents[ i - 1 ].dot( tangents[ i ] ), - 1, 1 ) ); // clamp for floating pt errors

				normals[ i ].applyMatrix4( mat.makeRotationAxis( vec, theta ) );

			}

			binormals[ i ].crossVectors( tangents[ i ], normals[ i ] );

		}

		// if the curve is closed, postprocess the vectors so the first and last normal vectors are the same

		if ( closed === true ) {

			let theta = Math.acos( clamp( normals[ 0 ].dot( normals[ segments ] ), - 1, 1 ) );
			theta /= segments;

			if ( tangents[ 0 ].dot( vec.crossVectors( normals[ 0 ], normals[ segments ] ) ) > 0 ) {

				theta = - theta;

			}

			for ( let i = 1; i <= segments; i ++ ) {

				// twist a little...
				normals[ i ].applyMatrix4( mat.makeRotationAxis( tangents[ i ], theta * i ) );
				binormals[ i ].crossVectors( tangents[ i ], normals[ i ] );

			}

		}

		return {
			tangents: tangents,
			normals: normals,
			binormals: binormals
		};

	}
```
</details>

### `Curve.clone(): Curve`

**JSDoc:**
```typescript
/**
	 * Returns a new curve with copied values from this instance.
	 *
	 * @return {Curve} A clone of this instance.
	 */
```

**Returns:** `Curve`

**Calls:**

- `new this.constructor().copy`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor().copy( this );

	}
```
</details>

### `Curve.copy(source: Curve): Curve`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given curve to this instance.
	 *
	 * @param {Curve} source - The curve to copy.
	 * @return {Curve} A reference to this curve.
	 */
```

**Parameters:**

- **`source`** `Curve`

**Returns:** `Curve`

<details><summary>Code</summary>

```typescript
copy( source ) {

		this.arcLengthDivisions = source.arcLengthDivisions;

		return this;

	}
```
</details>

### `Curve.toJSON(): any`

**JSDoc:**
```typescript
/**
	 * Serializes the curve into JSON.
	 *
	 * @return {Object} A JSON object representing the serialized curve.
	 * @see {@link ObjectLoader#parse}
	 */
```

**Returns:** `any`

<details><summary>Code</summary>

```typescript
toJSON() {

		const data = {
			metadata: {
				version: 4.7,
				type: 'Curve',
				generator: 'Curve.toJSON'
			}
		};

		data.arcLengthDivisions = this.arcLengthDivisions;
		data.type = this.type;

		return data;

	}
```
</details>

### `Curve.fromJSON(json: any): Curve`

**JSDoc:**
```typescript
/**
	 * Deserializes the curve from the given JSON.
	 *
	 * @param {Object} json - The JSON holding the serialized curve.
	 * @return {Curve} A reference to this curve.
	 */
```

**Parameters:**

- **`json`** `any`

**Returns:** `Curve`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		this.arcLengthDivisions = json.arcLengthDivisions;

		return this;

	}
```
</details>


---

## Classes

### `Curve`

<details><summary>Class Code</summary>

```ts
class Curve {

	/**
	 * Constructs a new curve.
	 */
	constructor() {

		/**
		 * The type property is used for detecting the object type
		 * in context of serialization/deserialization.
		 *
		 * @type {string}
		 * @readonly
		 */
		this.type = 'Curve';

		/**
		 * This value determines the amount of divisions when calculating the
		 * cumulative segment lengths of a curve via {@link Curve#getLengths}. To ensure
		 * precision when using methods like {@link Curve#getSpacedPoints}, it is
		 * recommended to increase the value of this property if the curve is very large.
		 *
		 * @type {number}
		 * @default 200
		 */
		this.arcLengthDivisions = 200;

		/**
		 * Must be set to `true` if the curve parameters have changed.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.needsUpdate = false;

		/**
		 * An internal cache that holds precomputed curve length values.
		 *
		 * @private
		 * @type {?Array<number>}
		 * @default null
		 */
		this.cacheArcLengths = null;

	}

	/**
	 * This method returns a vector in 2D or 3D space (depending on the curve definition)
	 * for the given interpolation factor.
	 *
	 * @abstract
	 * @param {number} t - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {(Vector2|Vector3)} [optionalTarget] - The optional target vector the result is written to.
	 * @return {(Vector2|Vector3)} The position on the curve. It can be a 2D or 3D vector depending on the curve definition.
	 */
	getPoint( /* t, optionalTarget */ ) {

		console.warn( 'THREE.Curve: .getPoint() not implemented.' );

	}

	/**
	 * This method returns a vector in 2D or 3D space (depending on the curve definition)
	 * for the given interpolation factor. Unlike {@link Curve#getPoint}, this method honors the length
	 * of the curve which equidistant samples.
	 *
	 * @param {number} u - A interpolation factor representing a position on the curve. Must be in the range `[0,1]`.
	 * @param {(Vector2|Vector3)} [optionalTarget] - The optional target vector the result is written to.
	 * @return {(Vector2|Vector3)} The position on the curve. It can be a 2D or 3D vector depending on the curve definition.
	 */
	getPointAt( u, optionalTarget ) {

		const t = this.getUtoTmapping( u );
		return this.getPoint( t, optionalTarget );

	}

	/**
	 * This method samples the curve via {@link Curve#getPoint} and returns an array of points representing
	 * the curve shape.
	 *
	 * @param {number} [divisions=5] - The number of divisions.
	 * @return {Array<(Vector2|Vector3)>} An array holding the sampled curve values. The number of points is `divisions + 1`.
	 */
	getPoints( divisions = 5 ) {

		const points = [];

		for ( let d = 0; d <= divisions; d ++ ) {

			points.push( this.getPoint( d / divisions ) );

		}

		return points;

	}

	// Get sequence of points using getPointAt( u )

	/**
	 * This method samples the curve via {@link Curve#getPointAt} and returns an array of points representing
	 * the curve shape. Unlike {@link Curve#getPoints}, this method returns equi-spaced points across the entire
	 * curve.
	 *
	 * @param {number} [divisions=5] - The number of divisions.
	 * @return {Array<(Vector2|Vector3)>} An array holding the sampled curve values. The number of points is `divisions + 1`.
	 */
	getSpacedPoints( divisions = 5 ) {

		const points = [];

		for ( let d = 0; d <= divisions; d ++ ) {

			points.push( this.getPointAt( d / divisions ) );

		}

		return points;

	}

	/**
	 * Returns the total arc length of the curve.
	 *
	 * @return {number} The length of the curve.
	 */
	getLength() {

		const lengths = this.getLengths();
		return lengths[ lengths.length - 1 ];

	}

	/**
	 * Returns an array of cumulative segment lengths of the curve.
	 *
	 * @param {number} [divisions=this.arcLengthDivisions] - The number of divisions.
	 * @return {Array<number>} An array holding the cumulative segment lengths.
	 */
	getLengths( divisions = this.arcLengthDivisions ) {

		if ( this.cacheArcLengths &&
			( this.cacheArcLengths.length === divisions + 1 ) &&
			! this.needsUpdate ) {

			return this.cacheArcLengths;

		}

		this.needsUpdate = false;

		const cache = [];
		let current, last = this.getPoint( 0 );
		let sum = 0;

		cache.push( 0 );

		for ( let p = 1; p <= divisions; p ++ ) {

			current = this.getPoint( p / divisions );
			sum += current.distanceTo( last );
			cache.push( sum );
			last = current;

		}

		this.cacheArcLengths = cache;

		return cache; // { sums: cache, sum: sum }; Sum is in the last element.

	}

	/**
	 * Update the cumulative segment distance cache. The method must be called
	 * every time curve parameters are changed. If an updated curve is part of a
	 * composed curve like {@link CurvePath}, this method must be called on the
	 * composed curve, too.
	 */
	updateArcLengths() {

		this.needsUpdate = true;
		this.getLengths();

	}

	/**
	 * Given an interpolation factor in the range `[0,1]`, this method returns an updated
	 * interpolation factor in the same range that can be ued to sample equidistant points
	 * from a curve.
	 *
	 * @param {number} u - The interpolation factor.
	 * @param {?number} distance - An optional distance on the curve.
	 * @return {number} The updated interpolation factor.
	 */
	getUtoTmapping( u, distance = null ) {

		const arcLengths = this.getLengths();

		let i = 0;
		const il = arcLengths.length;

		let targetArcLength; // The targeted u distance value to get

		if ( distance ) {

			targetArcLength = distance;

		} else {

			targetArcLength = u * arcLengths[ il - 1 ];

		}

		// binary search for the index with largest value smaller than target u distance

		let low = 0, high = il - 1, comparison;

		while ( low <= high ) {

			i = Math.floor( low + ( high - low ) / 2 ); // less likely to overflow, though probably not issue here, JS doesn't really have integers, all numbers are floats

			comparison = arcLengths[ i ] - targetArcLength;

			if ( comparison < 0 ) {

				low = i + 1;

			} else if ( comparison > 0 ) {

				high = i - 1;

			} else {

				high = i;
				break;

				// DONE

			}

		}

		i = high;

		if ( arcLengths[ i ] === targetArcLength ) {

			return i / ( il - 1 );

		}

		// we could get finer grain at lengths, or use simple interpolation between two points

		const lengthBefore = arcLengths[ i ];
		const lengthAfter = arcLengths[ i + 1 ];

		const segmentLength = lengthAfter - lengthBefore;

		// determine where we are between the 'before' and 'after' points

		const segmentFraction = ( targetArcLength - lengthBefore ) / segmentLength;

		// add that fractional amount to t

		const t = ( i + segmentFraction ) / ( il - 1 );

		return t;

	}

	/**
	 * Returns a unit vector tangent for the given interpolation factor.
	 * If the derived curve does not implement its tangent derivation,
	 * two points a small delta apart will be used to find its gradient
	 * which seems to give a reasonable approximation.
	 *
	 * @param {number} t - The interpolation factor.
	 * @param {(Vector2|Vector3)} [optionalTarget] - The optional target vector the result is written to.
	 * @return {(Vector2|Vector3)} The tangent vector.
	 */
	getTangent( t, optionalTarget ) {

		const delta = 0.0001;
		let t1 = t - delta;
		let t2 = t + delta;

		// Capping in case of danger

		if ( t1 < 0 ) t1 = 0;
		if ( t2 > 1 ) t2 = 1;

		const pt1 = this.getPoint( t1 );
		const pt2 = this.getPoint( t2 );

		const tangent = optionalTarget || ( ( pt1.isVector2 ) ? new Vector2() : new Vector3() );

		tangent.copy( pt2 ).sub( pt1 ).normalize();

		return tangent;

	}

	/**
	 * Same as {@link Curve#getTangent} but with equidistant samples.
	 *
	 * @param {number} u - The interpolation factor.
	 * @param {(Vector2|Vector3)} [optionalTarget] - The optional target vector the result is written to.
	 * @return {(Vector2|Vector3)} The tangent vector.
	 * @see {@link Curve#getPointAt}
	 */
	getTangentAt( u, optionalTarget ) {

		const t = this.getUtoTmapping( u );
		return this.getTangent( t, optionalTarget );

	}

	/**
	 * Generates the Frenet Frames. Requires a curve definition in 3D space. Used
	 * in geometries like {@link TubeGeometry} or {@link ExtrudeGeometry}.
	 *
	 * @param {number} segments - The number of segments.
	 * @param {boolean} [closed=false] - Whether the curve is closed or not.
	 * @return {{tangents: Array<Vector3>, normals: Array<Vector3>, binormals: Array<Vector3>}} The Frenet Frames.
	 */
	computeFrenetFrames( segments, closed = false ) {

		// see http://www.cs.indiana.edu/pub/techreports/TR425.pdf

		const normal = new Vector3();

		const tangents = [];
		const normals = [];
		const binormals = [];

		const vec = new Vector3();
		const mat = new Matrix4();

		// compute the tangent vectors for each segment on the curve

		for ( let i = 0; i <= segments; i ++ ) {

			const u = i / segments;

			tangents[ i ] = this.getTangentAt( u, new Vector3() );

		}

		// select an initial normal vector perpendicular to the first tangent vector,
		// and in the direction of the minimum tangent xyz component

		normals[ 0 ] = new Vector3();
		binormals[ 0 ] = new Vector3();
		let min = Number.MAX_VALUE;
		const tx = Math.abs( tangents[ 0 ].x );
		const ty = Math.abs( tangents[ 0 ].y );
		const tz = Math.abs( tangents[ 0 ].z );

		if ( tx <= min ) {

			min = tx;
			normal.set( 1, 0, 0 );

		}

		if ( ty <= min ) {

			min = ty;
			normal.set( 0, 1, 0 );

		}

		if ( tz <= min ) {

			normal.set( 0, 0, 1 );

		}

		vec.crossVectors( tangents[ 0 ], normal ).normalize();

		normals[ 0 ].crossVectors( tangents[ 0 ], vec );
		binormals[ 0 ].crossVectors( tangents[ 0 ], normals[ 0 ] );


		// compute the slowly-varying normal and binormal vectors for each segment on the curve

		for ( let i = 1; i <= segments; i ++ ) {

			normals[ i ] = normals[ i - 1 ].clone();

			binormals[ i ] = binormals[ i - 1 ].clone();

			vec.crossVectors( tangents[ i - 1 ], tangents[ i ] );

			if ( vec.length() > Number.EPSILON ) {

				vec.normalize();

				const theta = Math.acos( clamp( tangents[ i - 1 ].dot( tangents[ i ] ), - 1, 1 ) ); // clamp for floating pt errors

				normals[ i ].applyMatrix4( mat.makeRotationAxis( vec, theta ) );

			}

			binormals[ i ].crossVectors( tangents[ i ], normals[ i ] );

		}

		// if the curve is closed, postprocess the vectors so the first and last normal vectors are the same

		if ( closed === true ) {

			let theta = Math.acos( clamp( normals[ 0 ].dot( normals[ segments ] ), - 1, 1 ) );
			theta /= segments;

			if ( tangents[ 0 ].dot( vec.crossVectors( normals[ 0 ], normals[ segments ] ) ) > 0 ) {

				theta = - theta;

			}

			for ( let i = 1; i <= segments; i ++ ) {

				// twist a little...
				normals[ i ].applyMatrix4( mat.makeRotationAxis( tangents[ i ], theta * i ) );
				binormals[ i ].crossVectors( tangents[ i ], normals[ i ] );

			}

		}

		return {
			tangents: tangents,
			normals: normals,
			binormals: binormals
		};

	}

	/**
	 * Returns a new curve with copied values from this instance.
	 *
	 * @return {Curve} A clone of this instance.
	 */
	clone() {

		return new this.constructor().copy( this );

	}

	/**
	 * Copies the values of the given curve to this instance.
	 *
	 * @param {Curve} source - The curve to copy.
	 * @return {Curve} A reference to this curve.
	 */
	copy( source ) {

		this.arcLengthDivisions = source.arcLengthDivisions;

		return this;

	}

	/**
	 * Serializes the curve into JSON.
	 *
	 * @return {Object} A JSON object representing the serialized curve.
	 * @see {@link ObjectLoader#parse}
	 */
	toJSON() {

		const data = {
			metadata: {
				version: 4.7,
				type: 'Curve',
				generator: 'Curve.toJSON'
			}
		};

		data.arcLengthDivisions = this.arcLengthDivisions;
		data.type = this.type;

		return data;

	}

	/**
	 * Deserializes the curve from the given JSON.
	 *
	 * @param {Object} json - The JSON holding the serialized curve.
	 * @return {Curve} A reference to this curve.
	 */
	fromJSON( json ) {

		this.arcLengthDivisions = json.arcLengthDivisions;

		return this;

	}

}
```
</details>

#### Methods

##### `getPoint(): Vector2 | Vector3`

<details><summary>Code</summary>

```ts
getPoint( /* t, optionalTarget */ ) {

		console.warn( 'THREE.Curve: .getPoint() not implemented.' );

	}
```
</details>

##### `getPointAt(u: number, optionalTarget: Vector2 | Vector3): Vector2 | Vector3`

<details><summary>Code</summary>

```ts
getPointAt( u, optionalTarget ) {

		const t = this.getUtoTmapping( u );
		return this.getPoint( t, optionalTarget );

	}
```
</details>

##### `getPoints(divisions: number): (Vector2 | Vector3)[]`

<details><summary>Code</summary>

```ts
getPoints( divisions = 5 ) {

		const points = [];

		for ( let d = 0; d <= divisions; d ++ ) {

			points.push( this.getPoint( d / divisions ) );

		}

		return points;

	}
```
</details>

##### `getSpacedPoints(divisions: number): (Vector2 | Vector3)[]`

<details><summary>Code</summary>

```ts
getSpacedPoints( divisions = 5 ) {

		const points = [];

		for ( let d = 0; d <= divisions; d ++ ) {

			points.push( this.getPointAt( d / divisions ) );

		}

		return points;

	}
```
</details>

##### `getLength(): number`

<details><summary>Code</summary>

```ts
getLength() {

		const lengths = this.getLengths();
		return lengths[ lengths.length - 1 ];

	}
```
</details>

##### `getLengths(divisions: number): number[]`

<details><summary>Code</summary>

```ts
getLengths( divisions = this.arcLengthDivisions ) {

		if ( this.cacheArcLengths &&
			( this.cacheArcLengths.length === divisions + 1 ) &&
			! this.needsUpdate ) {

			return this.cacheArcLengths;

		}

		this.needsUpdate = false;

		const cache = [];
		let current, last = this.getPoint( 0 );
		let sum = 0;

		cache.push( 0 );

		for ( let p = 1; p <= divisions; p ++ ) {

			current = this.getPoint( p / divisions );
			sum += current.distanceTo( last );
			cache.push( sum );
			last = current;

		}

		this.cacheArcLengths = cache;

		return cache; // { sums: cache, sum: sum }; Sum is in the last element.

	}
```
</details>

##### `updateArcLengths(): void`

<details><summary>Code</summary>

```ts
updateArcLengths() {

		this.needsUpdate = true;
		this.getLengths();

	}
```
</details>

##### `getUtoTmapping(u: number, distance: number): number`

<details><summary>Code</summary>

```ts
getUtoTmapping( u, distance = null ) {

		const arcLengths = this.getLengths();

		let i = 0;
		const il = arcLengths.length;

		let targetArcLength; // The targeted u distance value to get

		if ( distance ) {

			targetArcLength = distance;

		} else {

			targetArcLength = u * arcLengths[ il - 1 ];

		}

		// binary search for the index with largest value smaller than target u distance

		let low = 0, high = il - 1, comparison;

		while ( low <= high ) {

			i = Math.floor( low + ( high - low ) / 2 ); // less likely to overflow, though probably not issue here, JS doesn't really have integers, all numbers are floats

			comparison = arcLengths[ i ] - targetArcLength;

			if ( comparison < 0 ) {

				low = i + 1;

			} else if ( comparison > 0 ) {

				high = i - 1;

			} else {

				high = i;
				break;

				// DONE

			}

		}

		i = high;

		if ( arcLengths[ i ] === targetArcLength ) {

			return i / ( il - 1 );

		}

		// we could get finer grain at lengths, or use simple interpolation between two points

		const lengthBefore = arcLengths[ i ];
		const lengthAfter = arcLengths[ i + 1 ];

		const segmentLength = lengthAfter - lengthBefore;

		// determine where we are between the 'before' and 'after' points

		const segmentFraction = ( targetArcLength - lengthBefore ) / segmentLength;

		// add that fractional amount to t

		const t = ( i + segmentFraction ) / ( il - 1 );

		return t;

	}
```
</details>

##### `getTangent(t: number, optionalTarget: Vector2 | Vector3): Vector2 | Vector3`

<details><summary>Code</summary>

```ts
getTangent( t, optionalTarget ) {

		const delta = 0.0001;
		let t1 = t - delta;
		let t2 = t + delta;

		// Capping in case of danger

		if ( t1 < 0 ) t1 = 0;
		if ( t2 > 1 ) t2 = 1;

		const pt1 = this.getPoint( t1 );
		const pt2 = this.getPoint( t2 );

		const tangent = optionalTarget || ( ( pt1.isVector2 ) ? new Vector2() : new Vector3() );

		tangent.copy( pt2 ).sub( pt1 ).normalize();

		return tangent;

	}
```
</details>

##### `getTangentAt(u: number, optionalTarget: Vector2 | Vector3): Vector2 | Vector3`

<details><summary>Code</summary>

```ts
getTangentAt( u, optionalTarget ) {

		const t = this.getUtoTmapping( u );
		return this.getTangent( t, optionalTarget );

	}
```
</details>

##### `computeFrenetFrames(segments: number, closed: boolean): { tangents: Vector3[]; normals: Vector3[]; binormals: Vector3[]; }`

<details><summary>Code</summary>

```ts
computeFrenetFrames( segments, closed = false ) {

		// see http://www.cs.indiana.edu/pub/techreports/TR425.pdf

		const normal = new Vector3();

		const tangents = [];
		const normals = [];
		const binormals = [];

		const vec = new Vector3();
		const mat = new Matrix4();

		// compute the tangent vectors for each segment on the curve

		for ( let i = 0; i <= segments; i ++ ) {

			const u = i / segments;

			tangents[ i ] = this.getTangentAt( u, new Vector3() );

		}

		// select an initial normal vector perpendicular to the first tangent vector,
		// and in the direction of the minimum tangent xyz component

		normals[ 0 ] = new Vector3();
		binormals[ 0 ] = new Vector3();
		let min = Number.MAX_VALUE;
		const tx = Math.abs( tangents[ 0 ].x );
		const ty = Math.abs( tangents[ 0 ].y );
		const tz = Math.abs( tangents[ 0 ].z );

		if ( tx <= min ) {

			min = tx;
			normal.set( 1, 0, 0 );

		}

		if ( ty <= min ) {

			min = ty;
			normal.set( 0, 1, 0 );

		}

		if ( tz <= min ) {

			normal.set( 0, 0, 1 );

		}

		vec.crossVectors( tangents[ 0 ], normal ).normalize();

		normals[ 0 ].crossVectors( tangents[ 0 ], vec );
		binormals[ 0 ].crossVectors( tangents[ 0 ], normals[ 0 ] );


		// compute the slowly-varying normal and binormal vectors for each segment on the curve

		for ( let i = 1; i <= segments; i ++ ) {

			normals[ i ] = normals[ i - 1 ].clone();

			binormals[ i ] = binormals[ i - 1 ].clone();

			vec.crossVectors( tangents[ i - 1 ], tangents[ i ] );

			if ( vec.length() > Number.EPSILON ) {

				vec.normalize();

				const theta = Math.acos( clamp( tangents[ i - 1 ].dot( tangents[ i ] ), - 1, 1 ) ); // clamp for floating pt errors

				normals[ i ].applyMatrix4( mat.makeRotationAxis( vec, theta ) );

			}

			binormals[ i ].crossVectors( tangents[ i ], normals[ i ] );

		}

		// if the curve is closed, postprocess the vectors so the first and last normal vectors are the same

		if ( closed === true ) {

			let theta = Math.acos( clamp( normals[ 0 ].dot( normals[ segments ] ), - 1, 1 ) );
			theta /= segments;

			if ( tangents[ 0 ].dot( vec.crossVectors( normals[ 0 ], normals[ segments ] ) ) > 0 ) {

				theta = - theta;

			}

			for ( let i = 1; i <= segments; i ++ ) {

				// twist a little...
				normals[ i ].applyMatrix4( mat.makeRotationAxis( tangents[ i ], theta * i ) );
				binormals[ i ].crossVectors( tangents[ i ], normals[ i ] );

			}

		}

		return {
			tangents: tangents,
			normals: normals,
			binormals: binormals
		};

	}
```
</details>

##### `clone(): Curve`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor().copy( this );

	}
```
</details>

##### `copy(source: Curve): Curve`

<details><summary>Code</summary>

```ts
copy( source ) {

		this.arcLengthDivisions = source.arcLengthDivisions;

		return this;

	}
```
</details>

##### `toJSON(): any`

<details><summary>Code</summary>

```ts
toJSON() {

		const data = {
			metadata: {
				version: 4.7,
				type: 'Curve',
				generator: 'Curve.toJSON'
			}
		};

		data.arcLengthDivisions = this.arcLengthDivisions;
		data.type = this.type;

		return data;

	}
```
</details>

##### `fromJSON(json: any): Curve`

<details><summary>Code</summary>

```ts
fromJSON( json ) {

		this.arcLengthDivisions = json.arcLengthDivisions;

		return this;

	}
```
</details>


---