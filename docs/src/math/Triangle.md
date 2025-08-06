[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Triangle.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 22 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 26 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/Triangle.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `./Vector3.js` |
| `Vector4` | `./Vector4.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_v0` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_v1` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_v2` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_v3` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_vab` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_vac` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_vbc` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_vap` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_vbp` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_vcp` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_v40` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `_v41` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `_v42` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `denom` | `number` | let/var | `( dot00 * dot11 - dot01 * dot01 )` | ✗ |
| `invDenom` | `number` | let/var | `1 / denom` | ✗ |
| `u` | `number` | let/var | `( dot11 * dot02 - dot01 * dot12 ) * invDenom` | ✗ |
| `v` | `number` | let/var | `( dot00 * dot12 - dot01 * dot02 ) * invDenom` | ✗ |
| `a` | `Vector3` | let/var | `this.a` | ✗ |
| `b` | `Vector3` | let/var | `this.b` | ✗ |
| `c` | `Vector3` | let/var | `this.c` | ✗ |
| `v` | `any` | let/var | `*not shown*` | ✗ |
| `w` | `any` | let/var | `*not shown*` | ✗ |
| `vc` | `number` | let/var | `d1 * d4 - d3 * d2` | ✗ |
| `vb` | `number` | let/var | `d5 * d2 - d1 * d6` | ✗ |
| `va` | `number` | let/var | `d3 * d6 - d5 * d4` | ✗ |
| `denom` | `number` | let/var | `1 / ( va + vb + vc )` | ✗ |


---

## Functions

### `Triangle.getNormal(a: Vector3, b: Vector3, c: Vector3, target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Computes the normal vector of a triangle.
	 *
	 * @param {Vector3} a - The first corner of the triangle.
	 * @param {Vector3} b - The second corner of the triangle.
	 * @param {Vector3} c - The third corner of the triangle.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The triangle's normal.
	 */
```

**Parameters:**

- **`a`** `Vector3`
- **`b`** `Vector3`
- **`c`** `Vector3`
- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `target.subVectors`
- `_v0.subVectors`
- `target.cross`
- `target.lengthSq`
- `target.multiplyScalar`
- `Math.sqrt`
- `target.set`

<details><summary>Code</summary>

```typescript
static getNormal( a, b, c, target ) {

		target.subVectors( c, b );
		_v0.subVectors( a, b );
		target.cross( _v0 );

		const targetLengthSq = target.lengthSq();
		if ( targetLengthSq > 0 ) {

			return target.multiplyScalar( 1 / Math.sqrt( targetLengthSq ) );

		}

		return target.set( 0, 0, 0 );

	}
```
</details>

### `Triangle.getBarycoord(point: Vector3, a: Vector3, b: Vector3, c: Vector3, target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Computes a barycentric coordinates from the given vector.
	 * Returns `null` if the triangle is degenerate.
	 *
	 * @param {Vector3} point - A point in 3D space.
	 * @param {Vector3} a - The first corner of the triangle.
	 * @param {Vector3} b - The second corner of the triangle.
	 * @param {Vector3} c - The third corner of the triangle.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {?Vector3} The barycentric coordinates for the given point
	 */
```

**Parameters:**

- **`point`** `Vector3`
- **`a`** `Vector3`
- **`b`** `Vector3`
- **`c`** `Vector3`
- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `_v0.subVectors`
- `_v1.subVectors`
- `_v2.subVectors`
- `_v0.dot`
- `_v1.dot`
- `target.set`

**Internal Comments:**
```
// based on: http://www.blackpawn.com/texts/pointinpoly/default.html (x4)
// collinear or singular triangle
// barycentric coordinates must always sum to 1
```

<details><summary>Code</summary>

```typescript
static getBarycoord( point, a, b, c, target ) {

		// based on: http://www.blackpawn.com/texts/pointinpoly/default.html

		_v0.subVectors( c, a );
		_v1.subVectors( b, a );
		_v2.subVectors( point, a );

		const dot00 = _v0.dot( _v0 );
		const dot01 = _v0.dot( _v1 );
		const dot02 = _v0.dot( _v2 );
		const dot11 = _v1.dot( _v1 );
		const dot12 = _v1.dot( _v2 );

		const denom = ( dot00 * dot11 - dot01 * dot01 );

		// collinear or singular triangle
		if ( denom === 0 ) {

			target.set( 0, 0, 0 );
			return null;

		}

		const invDenom = 1 / denom;
		const u = ( dot11 * dot02 - dot01 * dot12 ) * invDenom;
		const v = ( dot00 * dot12 - dot01 * dot02 ) * invDenom;

		// barycentric coordinates must always sum to 1
		return target.set( 1 - u - v, v, u );

	}
```
</details>

### `Triangle.containsPoint(point: Vector3, a: Vector3, b: Vector3, c: Vector3): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given point, when projected onto the plane of the
	 * triangle, lies within the triangle.
	 *
	 * @param {Vector3} point - The point in 3D space to test.
	 * @param {Vector3} a - The first corner of the triangle.
	 * @param {Vector3} b - The second corner of the triangle.
	 * @param {Vector3} c - The third corner of the triangle.
	 * @return {boolean} Whether the given point, when projected onto the plane of the
	 * triangle, lies within the triangle or not.
	 */
```

**Parameters:**

- **`point`** `Vector3`
- **`a`** `Vector3`
- **`b`** `Vector3`
- **`c`** `Vector3`

**Returns:** `boolean`

**Calls:**

- `this.getBarycoord`

**Internal Comments:**
```
// if the triangle is degenerate then we can't contain a point
```

<details><summary>Code</summary>

```typescript
static containsPoint( point, a, b, c ) {

		// if the triangle is degenerate then we can't contain a point
		if ( this.getBarycoord( point, a, b, c, _v3 ) === null ) {

			return false;

		}

		return ( _v3.x >= 0 ) && ( _v3.y >= 0 ) && ( ( _v3.x + _v3.y ) <= 1 );

	}
```
</details>

### `Triangle.getInterpolation(point: Vector3, p1: Vector3, p2: Vector3, p3: Vector3, v1: Vector3, v2: Vector3, v3: Vector3, target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Computes the value barycentrically interpolated for the given point on the
	 * triangle. Returns `null` if the triangle is degenerate.
	 *
	 * @param {Vector3} point - Position of interpolated point.
	 * @param {Vector3} p1 - The first corner of the triangle.
	 * @param {Vector3} p2 - The second corner of the triangle.
	 * @param {Vector3} p3 - The third corner of the triangle.
	 * @param {Vector3} v1 - Value to interpolate of first vertex.
	 * @param {Vector3} v2 - Value to interpolate of second vertex.
	 * @param {Vector3} v3 - Value to interpolate of third vertex.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {?Vector3} The interpolated value.
	 */
```

**Parameters:**

- **`point`** `Vector3`
- **`p1`** `Vector3`
- **`p2`** `Vector3`
- **`p3`** `Vector3`
- **`v1`** `Vector3`
- **`v2`** `Vector3`
- **`v3`** `Vector3`
- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `this.getBarycoord`
- `target.setScalar`
- `target.addScaledVector`

<details><summary>Code</summary>

```typescript
static getInterpolation( point, p1, p2, p3, v1, v2, v3, target ) {

		if ( this.getBarycoord( point, p1, p2, p3, _v3 ) === null ) {

			target.x = 0;
			target.y = 0;
			if ( 'z' in target ) target.z = 0;
			if ( 'w' in target ) target.w = 0;
			return null;

		}

		target.setScalar( 0 );
		target.addScaledVector( v1, _v3.x );
		target.addScaledVector( v2, _v3.y );
		target.addScaledVector( v3, _v3.z );

		return target;

	}
```
</details>

### `Triangle.getInterpolatedAttribute(attr: BufferAttribute, i1: number, i2: number, i3: number, barycoord: Vector3, target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Computes the value barycentrically interpolated for the given attribute and indices.
	 *
	 * @param {BufferAttribute} attr - The attribute to interpolate.
	 * @param {number} i1 - Index of first vertex.
	 * @param {number} i2 - Index of second vertex.
	 * @param {number} i3 - Index of third vertex.
	 * @param {Vector3} barycoord - The barycoordinate value to use to interpolate.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The interpolated attribute value.
	 */
```

**Parameters:**

- **`attr`** `BufferAttribute`
- **`i1`** `number`
- **`i2`** `number`
- **`i3`** `number`
- **`barycoord`** `Vector3`
- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `_v40.setScalar`
- `_v41.setScalar`
- `_v42.setScalar`
- `_v40.fromBufferAttribute`
- `_v41.fromBufferAttribute`
- `_v42.fromBufferAttribute`
- `target.setScalar`
- `target.addScaledVector`

<details><summary>Code</summary>

```typescript
static getInterpolatedAttribute( attr, i1, i2, i3, barycoord, target ) {

		_v40.setScalar( 0 );
		_v41.setScalar( 0 );
		_v42.setScalar( 0 );

		_v40.fromBufferAttribute( attr, i1 );
		_v41.fromBufferAttribute( attr, i2 );
		_v42.fromBufferAttribute( attr, i3 );

		target.setScalar( 0 );
		target.addScaledVector( _v40, barycoord.x );
		target.addScaledVector( _v41, barycoord.y );
		target.addScaledVector( _v42, barycoord.z );

		return target;

	}
```
</details>

### `Triangle.isFrontFacing(a: Vector3, b: Vector3, c: Vector3, direction: Vector3): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the triangle is oriented towards the given direction.
	 *
	 * @param {Vector3} a - The first corner of the triangle.
	 * @param {Vector3} b - The second corner of the triangle.
	 * @param {Vector3} c - The third corner of the triangle.
	 * @param {Vector3} direction - The (normalized) direction vector.
	 * @return {boolean} Whether the triangle is oriented towards the given direction or not.
	 */
```

**Parameters:**

- **`a`** `Vector3`
- **`b`** `Vector3`
- **`c`** `Vector3`
- **`direction`** `Vector3`

**Returns:** `boolean`

**Calls:**

- `_v0.subVectors`
- `_v1.subVectors`
- `_v0.cross( _v1 ).dot`

**Internal Comments:**
```
// strictly front facing
```

<details><summary>Code</summary>

```typescript
static isFrontFacing( a, b, c, direction ) {

		_v0.subVectors( c, b );
		_v1.subVectors( a, b );

		// strictly front facing
		return ( _v0.cross( _v1 ).dot( direction ) < 0 ) ? true : false;

	}
```
</details>

### `Triangle.set(a: Vector3, b: Vector3, c: Vector3): Triangle`

**JSDoc:**
```typescript
/**
	 * Sets the triangle's vertices by copying the given values.
	 *
	 * @param {Vector3} a - The first corner of the triangle.
	 * @param {Vector3} b - The second corner of the triangle.
	 * @param {Vector3} c - The third corner of the triangle.
	 * @return {Triangle} A reference to this triangle.
	 */
```

**Parameters:**

- **`a`** `Vector3`
- **`b`** `Vector3`
- **`c`** `Vector3`

**Returns:** `Triangle`

**Calls:**

- `this.a.copy`
- `this.b.copy`
- `this.c.copy`

<details><summary>Code</summary>

```typescript
set( a, b, c ) {

		this.a.copy( a );
		this.b.copy( b );
		this.c.copy( c );

		return this;

	}
```
</details>

### `Triangle.setFromPointsAndIndices(points: Vector3[], i0: number, i1: number, i2: number): Triangle`

**JSDoc:**
```typescript
/**
	 * Sets the triangle's vertices by copying the given array values.
	 *
	 * @param {Array<Vector3>} points - An array with 3D points.
	 * @param {number} i0 - The array index representing the first corner of the triangle.
	 * @param {number} i1 - The array index representing the second corner of the triangle.
	 * @param {number} i2 - The array index representing the third corner of the triangle.
	 * @return {Triangle} A reference to this triangle.
	 */
```

**Parameters:**

- **`points`** `Vector3[]`
- **`i0`** `number`
- **`i1`** `number`
- **`i2`** `number`

**Returns:** `Triangle`

**Calls:**

- `this.a.copy`
- `this.b.copy`
- `this.c.copy`

<details><summary>Code</summary>

```typescript
setFromPointsAndIndices( points, i0, i1, i2 ) {

		this.a.copy( points[ i0 ] );
		this.b.copy( points[ i1 ] );
		this.c.copy( points[ i2 ] );

		return this;

	}
```
</details>

### `Triangle.setFromAttributeAndIndices(attribute: BufferAttribute, i0: number, i1: number, i2: number): Triangle`

**JSDoc:**
```typescript
/**
	 * Sets the triangle's vertices by copying the given attribute values.
	 *
	 * @param {BufferAttribute} attribute - A buffer attribute with 3D points data.
	 * @param {number} i0 - The attribute index representing the first corner of the triangle.
	 * @param {number} i1 - The attribute index representing the second corner of the triangle.
	 * @param {number} i2 - The attribute index representing the third corner of the triangle.
	 * @return {Triangle} A reference to this triangle.
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`
- **`i0`** `number`
- **`i1`** `number`
- **`i2`** `number`

**Returns:** `Triangle`

**Calls:**

- `this.a.fromBufferAttribute`
- `this.b.fromBufferAttribute`
- `this.c.fromBufferAttribute`

<details><summary>Code</summary>

```typescript
setFromAttributeAndIndices( attribute, i0, i1, i2 ) {

		this.a.fromBufferAttribute( attribute, i0 );
		this.b.fromBufferAttribute( attribute, i1 );
		this.c.fromBufferAttribute( attribute, i2 );

		return this;

	}
```
</details>

### `Triangle.clone(): Triangle`

**JSDoc:**
```typescript
/**
	 * Returns a new triangle with copied values from this instance.
	 *
	 * @return {Triangle} A clone of this instance.
	 */
```

**Returns:** `Triangle`

**Calls:**

- `new this.constructor().copy`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor().copy( this );

	}
```
</details>

### `Triangle.copy(triangle: Triangle): Triangle`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given triangle to this instance.
	 *
	 * @param {Triangle} triangle - The triangle to copy.
	 * @return {Triangle} A reference to this triangle.
	 */
```

**Parameters:**

- **`triangle`** `Triangle`

**Returns:** `Triangle`

**Calls:**

- `this.a.copy`
- `this.b.copy`
- `this.c.copy`

<details><summary>Code</summary>

```typescript
copy( triangle ) {

		this.a.copy( triangle.a );
		this.b.copy( triangle.b );
		this.c.copy( triangle.c );

		return this;

	}
```
</details>

### `Triangle.getArea(): number`

**JSDoc:**
```typescript
/**
	 * Computes the area of the triangle.
	 *
	 * @return {number} The triangle's area.
	 */
```

**Returns:** `number`

**Calls:**

- `_v0.subVectors`
- `_v1.subVectors`
- `_v0.cross( _v1 ).length`

<details><summary>Code</summary>

```typescript
getArea() {

		_v0.subVectors( this.c, this.b );
		_v1.subVectors( this.a, this.b );

		return _v0.cross( _v1 ).length() * 0.5;

	}
```
</details>

### `Triangle.getMidpoint(target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Computes the midpoint of the triangle.
	 *
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The triangle's midpoint.
	 */
```

**Parameters:**

- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `target.addVectors( this.a, this.b ).add( this.c ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getMidpoint( target ) {

		return target.addVectors( this.a, this.b ).add( this.c ).multiplyScalar( 1 / 3 );

	}
```
</details>

### `Triangle.getNormal(target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Computes the normal of the triangle.
	 *
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The triangle's normal.
	 */
```

**Parameters:**

- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Triangle.getNormal`

<details><summary>Code</summary>

```typescript
getNormal( target ) {

		return Triangle.getNormal( this.a, this.b, this.c, target );

	}
```
</details>

### `Triangle.getPlane(target: Plane): Plane`

**JSDoc:**
```typescript
/**
	 * Computes a plane the triangle lies within.
	 *
	 * @param {Plane} target - The target vector that is used to store the method's result.
	 * @return {Plane} The plane the triangle lies within.
	 */
```

**Parameters:**

- **`target`** `Plane`

**Returns:** `Plane`

**Calls:**

- `target.setFromCoplanarPoints`

<details><summary>Code</summary>

```typescript
getPlane( target ) {

		return target.setFromCoplanarPoints( this.a, this.b, this.c );

	}
```
</details>

### `Triangle.getBarycoord(point: Vector3, target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Computes a barycentric coordinates from the given vector.
	 * Returns `null` if the triangle is degenerate.
	 *
	 * @param {Vector3} point - A point in 3D space.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {?Vector3} The barycentric coordinates for the given point
	 */
```

**Parameters:**

- **`point`** `Vector3`
- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Triangle.getBarycoord`

<details><summary>Code</summary>

```typescript
getBarycoord( point, target ) {

		return Triangle.getBarycoord( point, this.a, this.b, this.c, target );

	}
```
</details>

### `Triangle.getInterpolation(point: Vector3, v1: Vector3, v2: Vector3, v3: Vector3, target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Computes the value barycentrically interpolated for the given point on the
	 * triangle. Returns `null` if the triangle is degenerate.
	 *
	 * @param {Vector3} point - Position of interpolated point.
	 * @param {Vector3} v1 - Value to interpolate of first vertex.
	 * @param {Vector3} v2 - Value to interpolate of second vertex.
	 * @param {Vector3} v3 - Value to interpolate of third vertex.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {?Vector3} The interpolated value.
	 */
```

**Parameters:**

- **`point`** `Vector3`
- **`v1`** `Vector3`
- **`v2`** `Vector3`
- **`v3`** `Vector3`
- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Triangle.getInterpolation`

<details><summary>Code</summary>

```typescript
getInterpolation( point, v1, v2, v3, target ) {

		return Triangle.getInterpolation( point, this.a, this.b, this.c, v1, v2, v3, target );

	}
```
</details>

### `Triangle.containsPoint(point: Vector3): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given point, when projected onto the plane of the
	 * triangle, lies within the triangle.
	 *
	 * @param {Vector3} point - The point in 3D space to test.
	 * @return {boolean} Whether the given point, when projected onto the plane of the
	 * triangle, lies within the triangle or not.
	 */
```

**Parameters:**

- **`point`** `Vector3`

**Returns:** `boolean`

**Calls:**

- `Triangle.containsPoint`

<details><summary>Code</summary>

```typescript
containsPoint( point ) {

		return Triangle.containsPoint( point, this.a, this.b, this.c );

	}
```
</details>

### `Triangle.isFrontFacing(direction: Vector3): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the triangle is oriented towards the given direction.
	 *
	 * @param {Vector3} direction - The (normalized) direction vector.
	 * @return {boolean} Whether the triangle is oriented towards the given direction or not.
	 */
```

**Parameters:**

- **`direction`** `Vector3`

**Returns:** `boolean`

**Calls:**

- `Triangle.isFrontFacing`

<details><summary>Code</summary>

```typescript
isFrontFacing( direction ) {

		return Triangle.isFrontFacing( this.a, this.b, this.c, direction );

	}
```
</details>

### `Triangle.intersectsBox(box: Box3): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this triangle intersects with the given box.
	 *
	 * @param {Box3} box - The box to intersect.
	 * @return {boolean} Whether this triangle intersects with the given box or not.
	 */
```

**Parameters:**

- **`box`** `Box3`

**Returns:** `boolean`

**Calls:**

- `box.intersectsTriangle`

<details><summary>Code</summary>

```typescript
intersectsBox( box ) {

		return box.intersectsTriangle( this );

	}
```
</details>

### `Triangle.closestPointToPoint(p: Vector3, target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Returns the closest point on the triangle to the given point.
	 *
	 * @param {Vector3} p - The point to compute the closest point for.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The closest point on the triangle.
	 */
```

**Parameters:**

- **`p`** `Vector3`
- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `_vab.subVectors`
- `_vac.subVectors`
- `_vap.subVectors`
- `_vab.dot`
- `_vac.dot`
- `target.copy`
- `_vbp.subVectors`
- `target.copy( a ).addScaledVector`
- `_vcp.subVectors`
- `_vbc.subVectors`
- `target.copy( b ).addScaledVector`
- `target.copy( a ).addScaledVector( _vab, v ).addScaledVector`

**Internal Comments:**
```
// algorithm thanks to Real-Time Collision Detection by Christer Ericson, (x4)
// published by Morgan Kaufmann Publishers, (c) 2005 Elsevier Inc., (x4)
// under the accompanying license; see chapter 5.1.5 for detailed explanation. (x4)
// basically, we're distinguishing which of the voronoi regions of the triangle (x4)
// the point lies in with the minimum amount of redundant computation. (x4)
// vertex region of A; barycentric coords (1, 0, 0)
// vertex region of B; barycentric coords (0, 1, 0)
// edge region of AB; barycentric coords (1-v, v, 0)
// vertex region of C; barycentric coords (0, 0, 1)
// edge region of AC; barycentric coords (1-w, 0, w)
// edge region of BC; barycentric coords (0, 1-w, w)
// face region (x2)
// u = va * denom (x3)
```

<details><summary>Code</summary>

```typescript
closestPointToPoint( p, target ) {

		const a = this.a, b = this.b, c = this.c;
		let v, w;

		// algorithm thanks to Real-Time Collision Detection by Christer Ericson,
		// published by Morgan Kaufmann Publishers, (c) 2005 Elsevier Inc.,
		// under the accompanying license; see chapter 5.1.5 for detailed explanation.
		// basically, we're distinguishing which of the voronoi regions of the triangle
		// the point lies in with the minimum amount of redundant computation.

		_vab.subVectors( b, a );
		_vac.subVectors( c, a );
		_vap.subVectors( p, a );
		const d1 = _vab.dot( _vap );
		const d2 = _vac.dot( _vap );
		if ( d1 <= 0 && d2 <= 0 ) {

			// vertex region of A; barycentric coords (1, 0, 0)
			return target.copy( a );

		}

		_vbp.subVectors( p, b );
		const d3 = _vab.dot( _vbp );
		const d4 = _vac.dot( _vbp );
		if ( d3 >= 0 && d4 <= d3 ) {

			// vertex region of B; barycentric coords (0, 1, 0)
			return target.copy( b );

		}

		const vc = d1 * d4 - d3 * d2;
		if ( vc <= 0 && d1 >= 0 && d3 <= 0 ) {

			v = d1 / ( d1 - d3 );
			// edge region of AB; barycentric coords (1-v, v, 0)
			return target.copy( a ).addScaledVector( _vab, v );

		}

		_vcp.subVectors( p, c );
		const d5 = _vab.dot( _vcp );
		const d6 = _vac.dot( _vcp );
		if ( d6 >= 0 && d5 <= d6 ) {

			// vertex region of C; barycentric coords (0, 0, 1)
			return target.copy( c );

		}

		const vb = d5 * d2 - d1 * d6;
		if ( vb <= 0 && d2 >= 0 && d6 <= 0 ) {

			w = d2 / ( d2 - d6 );
			// edge region of AC; barycentric coords (1-w, 0, w)
			return target.copy( a ).addScaledVector( _vac, w );

		}

		const va = d3 * d6 - d5 * d4;
		if ( va <= 0 && ( d4 - d3 ) >= 0 && ( d5 - d6 ) >= 0 ) {

			_vbc.subVectors( c, b );
			w = ( d4 - d3 ) / ( ( d4 - d3 ) + ( d5 - d6 ) );
			// edge region of BC; barycentric coords (0, 1-w, w)
			return target.copy( b ).addScaledVector( _vbc, w ); // edge region of BC

		}

		// face region
		const denom = 1 / ( va + vb + vc );
		// u = va * denom
		v = vb * denom;
		w = vc * denom;

		return target.copy( a ).addScaledVector( _vab, v ).addScaledVector( _vac, w );

	}
```
</details>

### `Triangle.equals(triangle: Triangle): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this triangle is equal with the given one.
	 *
	 * @param {Triangle} triangle - The triangle to test for equality.
	 * @return {boolean} Whether this triangle is equal with the given one.
	 */
```

**Parameters:**

- **`triangle`** `Triangle`

**Returns:** `boolean`

**Calls:**

- `triangle.a.equals`
- `triangle.b.equals`
- `triangle.c.equals`

<details><summary>Code</summary>

```typescript
equals( triangle ) {

		return triangle.a.equals( this.a ) && triangle.b.equals( this.b ) && triangle.c.equals( this.c );

	}
```
</details>


---

## Classes

### `Triangle`

<details><summary>Class Code</summary>

```ts
class Triangle {

	/**
	 * Constructs a new triangle.
	 *
	 * @param {Vector3} [a=(0,0,0)] - The first corner of the triangle.
	 * @param {Vector3} [b=(0,0,0)] - The second corner of the triangle.
	 * @param {Vector3} [c=(0,0,0)] - The third corner of the triangle.
	 */
	constructor( a = new Vector3(), b = new Vector3(), c = new Vector3() ) {

		/**
		 * The first corner of the triangle.
		 *
		 * @type {Vector3}
		 */
		this.a = a;

		/**
		 * The second corner of the triangle.
		 *
		 * @type {Vector3}
		 */
		this.b = b;

		/**
		 * The third corner of the triangle.
		 *
		 * @type {Vector3}
		 */
		this.c = c;

	}

	/**
	 * Computes the normal vector of a triangle.
	 *
	 * @param {Vector3} a - The first corner of the triangle.
	 * @param {Vector3} b - The second corner of the triangle.
	 * @param {Vector3} c - The third corner of the triangle.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The triangle's normal.
	 */
	static getNormal( a, b, c, target ) {

		target.subVectors( c, b );
		_v0.subVectors( a, b );
		target.cross( _v0 );

		const targetLengthSq = target.lengthSq();
		if ( targetLengthSq > 0 ) {

			return target.multiplyScalar( 1 / Math.sqrt( targetLengthSq ) );

		}

		return target.set( 0, 0, 0 );

	}

	/**
	 * Computes a barycentric coordinates from the given vector.
	 * Returns `null` if the triangle is degenerate.
	 *
	 * @param {Vector3} point - A point in 3D space.
	 * @param {Vector3} a - The first corner of the triangle.
	 * @param {Vector3} b - The second corner of the triangle.
	 * @param {Vector3} c - The third corner of the triangle.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {?Vector3} The barycentric coordinates for the given point
	 */
	static getBarycoord( point, a, b, c, target ) {

		// based on: http://www.blackpawn.com/texts/pointinpoly/default.html

		_v0.subVectors( c, a );
		_v1.subVectors( b, a );
		_v2.subVectors( point, a );

		const dot00 = _v0.dot( _v0 );
		const dot01 = _v0.dot( _v1 );
		const dot02 = _v0.dot( _v2 );
		const dot11 = _v1.dot( _v1 );
		const dot12 = _v1.dot( _v2 );

		const denom = ( dot00 * dot11 - dot01 * dot01 );

		// collinear or singular triangle
		if ( denom === 0 ) {

			target.set( 0, 0, 0 );
			return null;

		}

		const invDenom = 1 / denom;
		const u = ( dot11 * dot02 - dot01 * dot12 ) * invDenom;
		const v = ( dot00 * dot12 - dot01 * dot02 ) * invDenom;

		// barycentric coordinates must always sum to 1
		return target.set( 1 - u - v, v, u );

	}

	/**
	 * Returns `true` if the given point, when projected onto the plane of the
	 * triangle, lies within the triangle.
	 *
	 * @param {Vector3} point - The point in 3D space to test.
	 * @param {Vector3} a - The first corner of the triangle.
	 * @param {Vector3} b - The second corner of the triangle.
	 * @param {Vector3} c - The third corner of the triangle.
	 * @return {boolean} Whether the given point, when projected onto the plane of the
	 * triangle, lies within the triangle or not.
	 */
	static containsPoint( point, a, b, c ) {

		// if the triangle is degenerate then we can't contain a point
		if ( this.getBarycoord( point, a, b, c, _v3 ) === null ) {

			return false;

		}

		return ( _v3.x >= 0 ) && ( _v3.y >= 0 ) && ( ( _v3.x + _v3.y ) <= 1 );

	}

	/**
	 * Computes the value barycentrically interpolated for the given point on the
	 * triangle. Returns `null` if the triangle is degenerate.
	 *
	 * @param {Vector3} point - Position of interpolated point.
	 * @param {Vector3} p1 - The first corner of the triangle.
	 * @param {Vector3} p2 - The second corner of the triangle.
	 * @param {Vector3} p3 - The third corner of the triangle.
	 * @param {Vector3} v1 - Value to interpolate of first vertex.
	 * @param {Vector3} v2 - Value to interpolate of second vertex.
	 * @param {Vector3} v3 - Value to interpolate of third vertex.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {?Vector3} The interpolated value.
	 */
	static getInterpolation( point, p1, p2, p3, v1, v2, v3, target ) {

		if ( this.getBarycoord( point, p1, p2, p3, _v3 ) === null ) {

			target.x = 0;
			target.y = 0;
			if ( 'z' in target ) target.z = 0;
			if ( 'w' in target ) target.w = 0;
			return null;

		}

		target.setScalar( 0 );
		target.addScaledVector( v1, _v3.x );
		target.addScaledVector( v2, _v3.y );
		target.addScaledVector( v3, _v3.z );

		return target;

	}

	/**
	 * Computes the value barycentrically interpolated for the given attribute and indices.
	 *
	 * @param {BufferAttribute} attr - The attribute to interpolate.
	 * @param {number} i1 - Index of first vertex.
	 * @param {number} i2 - Index of second vertex.
	 * @param {number} i3 - Index of third vertex.
	 * @param {Vector3} barycoord - The barycoordinate value to use to interpolate.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The interpolated attribute value.
	 */
	static getInterpolatedAttribute( attr, i1, i2, i3, barycoord, target ) {

		_v40.setScalar( 0 );
		_v41.setScalar( 0 );
		_v42.setScalar( 0 );

		_v40.fromBufferAttribute( attr, i1 );
		_v41.fromBufferAttribute( attr, i2 );
		_v42.fromBufferAttribute( attr, i3 );

		target.setScalar( 0 );
		target.addScaledVector( _v40, barycoord.x );
		target.addScaledVector( _v41, barycoord.y );
		target.addScaledVector( _v42, barycoord.z );

		return target;

	}

	/**
	 * Returns `true` if the triangle is oriented towards the given direction.
	 *
	 * @param {Vector3} a - The first corner of the triangle.
	 * @param {Vector3} b - The second corner of the triangle.
	 * @param {Vector3} c - The third corner of the triangle.
	 * @param {Vector3} direction - The (normalized) direction vector.
	 * @return {boolean} Whether the triangle is oriented towards the given direction or not.
	 */
	static isFrontFacing( a, b, c, direction ) {

		_v0.subVectors( c, b );
		_v1.subVectors( a, b );

		// strictly front facing
		return ( _v0.cross( _v1 ).dot( direction ) < 0 ) ? true : false;

	}

	/**
	 * Sets the triangle's vertices by copying the given values.
	 *
	 * @param {Vector3} a - The first corner of the triangle.
	 * @param {Vector3} b - The second corner of the triangle.
	 * @param {Vector3} c - The third corner of the triangle.
	 * @return {Triangle} A reference to this triangle.
	 */
	set( a, b, c ) {

		this.a.copy( a );
		this.b.copy( b );
		this.c.copy( c );

		return this;

	}

	/**
	 * Sets the triangle's vertices by copying the given array values.
	 *
	 * @param {Array<Vector3>} points - An array with 3D points.
	 * @param {number} i0 - The array index representing the first corner of the triangle.
	 * @param {number} i1 - The array index representing the second corner of the triangle.
	 * @param {number} i2 - The array index representing the third corner of the triangle.
	 * @return {Triangle} A reference to this triangle.
	 */
	setFromPointsAndIndices( points, i0, i1, i2 ) {

		this.a.copy( points[ i0 ] );
		this.b.copy( points[ i1 ] );
		this.c.copy( points[ i2 ] );

		return this;

	}

	/**
	 * Sets the triangle's vertices by copying the given attribute values.
	 *
	 * @param {BufferAttribute} attribute - A buffer attribute with 3D points data.
	 * @param {number} i0 - The attribute index representing the first corner of the triangle.
	 * @param {number} i1 - The attribute index representing the second corner of the triangle.
	 * @param {number} i2 - The attribute index representing the third corner of the triangle.
	 * @return {Triangle} A reference to this triangle.
	 */
	setFromAttributeAndIndices( attribute, i0, i1, i2 ) {

		this.a.fromBufferAttribute( attribute, i0 );
		this.b.fromBufferAttribute( attribute, i1 );
		this.c.fromBufferAttribute( attribute, i2 );

		return this;

	}

	/**
	 * Returns a new triangle with copied values from this instance.
	 *
	 * @return {Triangle} A clone of this instance.
	 */
	clone() {

		return new this.constructor().copy( this );

	}

	/**
	 * Copies the values of the given triangle to this instance.
	 *
	 * @param {Triangle} triangle - The triangle to copy.
	 * @return {Triangle} A reference to this triangle.
	 */
	copy( triangle ) {

		this.a.copy( triangle.a );
		this.b.copy( triangle.b );
		this.c.copy( triangle.c );

		return this;

	}

	/**
	 * Computes the area of the triangle.
	 *
	 * @return {number} The triangle's area.
	 */
	getArea() {

		_v0.subVectors( this.c, this.b );
		_v1.subVectors( this.a, this.b );

		return _v0.cross( _v1 ).length() * 0.5;

	}

	/**
	 * Computes the midpoint of the triangle.
	 *
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The triangle's midpoint.
	 */
	getMidpoint( target ) {

		return target.addVectors( this.a, this.b ).add( this.c ).multiplyScalar( 1 / 3 );

	}

	/**
	 * Computes the normal of the triangle.
	 *
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The triangle's normal.
	 */
	getNormal( target ) {

		return Triangle.getNormal( this.a, this.b, this.c, target );

	}

	/**
	 * Computes a plane the triangle lies within.
	 *
	 * @param {Plane} target - The target vector that is used to store the method's result.
	 * @return {Plane} The plane the triangle lies within.
	 */
	getPlane( target ) {

		return target.setFromCoplanarPoints( this.a, this.b, this.c );

	}

	/**
	 * Computes a barycentric coordinates from the given vector.
	 * Returns `null` if the triangle is degenerate.
	 *
	 * @param {Vector3} point - A point in 3D space.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {?Vector3} The barycentric coordinates for the given point
	 */
	getBarycoord( point, target ) {

		return Triangle.getBarycoord( point, this.a, this.b, this.c, target );

	}

	/**
	 * Computes the value barycentrically interpolated for the given point on the
	 * triangle. Returns `null` if the triangle is degenerate.
	 *
	 * @param {Vector3} point - Position of interpolated point.
	 * @param {Vector3} v1 - Value to interpolate of first vertex.
	 * @param {Vector3} v2 - Value to interpolate of second vertex.
	 * @param {Vector3} v3 - Value to interpolate of third vertex.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {?Vector3} The interpolated value.
	 */
	getInterpolation( point, v1, v2, v3, target ) {

		return Triangle.getInterpolation( point, this.a, this.b, this.c, v1, v2, v3, target );

	}

	/**
	 * Returns `true` if the given point, when projected onto the plane of the
	 * triangle, lies within the triangle.
	 *
	 * @param {Vector3} point - The point in 3D space to test.
	 * @return {boolean} Whether the given point, when projected onto the plane of the
	 * triangle, lies within the triangle or not.
	 */
	containsPoint( point ) {

		return Triangle.containsPoint( point, this.a, this.b, this.c );

	}

	/**
	 * Returns `true` if the triangle is oriented towards the given direction.
	 *
	 * @param {Vector3} direction - The (normalized) direction vector.
	 * @return {boolean} Whether the triangle is oriented towards the given direction or not.
	 */
	isFrontFacing( direction ) {

		return Triangle.isFrontFacing( this.a, this.b, this.c, direction );

	}

	/**
	 * Returns `true` if this triangle intersects with the given box.
	 *
	 * @param {Box3} box - The box to intersect.
	 * @return {boolean} Whether this triangle intersects with the given box or not.
	 */
	intersectsBox( box ) {

		return box.intersectsTriangle( this );

	}

	/**
	 * Returns the closest point on the triangle to the given point.
	 *
	 * @param {Vector3} p - The point to compute the closest point for.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The closest point on the triangle.
	 */
	closestPointToPoint( p, target ) {

		const a = this.a, b = this.b, c = this.c;
		let v, w;

		// algorithm thanks to Real-Time Collision Detection by Christer Ericson,
		// published by Morgan Kaufmann Publishers, (c) 2005 Elsevier Inc.,
		// under the accompanying license; see chapter 5.1.5 for detailed explanation.
		// basically, we're distinguishing which of the voronoi regions of the triangle
		// the point lies in with the minimum amount of redundant computation.

		_vab.subVectors( b, a );
		_vac.subVectors( c, a );
		_vap.subVectors( p, a );
		const d1 = _vab.dot( _vap );
		const d2 = _vac.dot( _vap );
		if ( d1 <= 0 && d2 <= 0 ) {

			// vertex region of A; barycentric coords (1, 0, 0)
			return target.copy( a );

		}

		_vbp.subVectors( p, b );
		const d3 = _vab.dot( _vbp );
		const d4 = _vac.dot( _vbp );
		if ( d3 >= 0 && d4 <= d3 ) {

			// vertex region of B; barycentric coords (0, 1, 0)
			return target.copy( b );

		}

		const vc = d1 * d4 - d3 * d2;
		if ( vc <= 0 && d1 >= 0 && d3 <= 0 ) {

			v = d1 / ( d1 - d3 );
			// edge region of AB; barycentric coords (1-v, v, 0)
			return target.copy( a ).addScaledVector( _vab, v );

		}

		_vcp.subVectors( p, c );
		const d5 = _vab.dot( _vcp );
		const d6 = _vac.dot( _vcp );
		if ( d6 >= 0 && d5 <= d6 ) {

			// vertex region of C; barycentric coords (0, 0, 1)
			return target.copy( c );

		}

		const vb = d5 * d2 - d1 * d6;
		if ( vb <= 0 && d2 >= 0 && d6 <= 0 ) {

			w = d2 / ( d2 - d6 );
			// edge region of AC; barycentric coords (1-w, 0, w)
			return target.copy( a ).addScaledVector( _vac, w );

		}

		const va = d3 * d6 - d5 * d4;
		if ( va <= 0 && ( d4 - d3 ) >= 0 && ( d5 - d6 ) >= 0 ) {

			_vbc.subVectors( c, b );
			w = ( d4 - d3 ) / ( ( d4 - d3 ) + ( d5 - d6 ) );
			// edge region of BC; barycentric coords (0, 1-w, w)
			return target.copy( b ).addScaledVector( _vbc, w ); // edge region of BC

		}

		// face region
		const denom = 1 / ( va + vb + vc );
		// u = va * denom
		v = vb * denom;
		w = vc * denom;

		return target.copy( a ).addScaledVector( _vab, v ).addScaledVector( _vac, w );

	}

	/**
	 * Returns `true` if this triangle is equal with the given one.
	 *
	 * @param {Triangle} triangle - The triangle to test for equality.
	 * @return {boolean} Whether this triangle is equal with the given one.
	 */
	equals( triangle ) {

		return triangle.a.equals( this.a ) && triangle.b.equals( this.b ) && triangle.c.equals( this.c );

	}

}
```
</details>

#### Methods

##### `getNormal(a: Vector3, b: Vector3, c: Vector3, target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
static getNormal( a, b, c, target ) {

		target.subVectors( c, b );
		_v0.subVectors( a, b );
		target.cross( _v0 );

		const targetLengthSq = target.lengthSq();
		if ( targetLengthSq > 0 ) {

			return target.multiplyScalar( 1 / Math.sqrt( targetLengthSq ) );

		}

		return target.set( 0, 0, 0 );

	}
```
</details>

##### `getBarycoord(point: Vector3, a: Vector3, b: Vector3, c: Vector3, target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
static getBarycoord( point, a, b, c, target ) {

		// based on: http://www.blackpawn.com/texts/pointinpoly/default.html

		_v0.subVectors( c, a );
		_v1.subVectors( b, a );
		_v2.subVectors( point, a );

		const dot00 = _v0.dot( _v0 );
		const dot01 = _v0.dot( _v1 );
		const dot02 = _v0.dot( _v2 );
		const dot11 = _v1.dot( _v1 );
		const dot12 = _v1.dot( _v2 );

		const denom = ( dot00 * dot11 - dot01 * dot01 );

		// collinear or singular triangle
		if ( denom === 0 ) {

			target.set( 0, 0, 0 );
			return null;

		}

		const invDenom = 1 / denom;
		const u = ( dot11 * dot02 - dot01 * dot12 ) * invDenom;
		const v = ( dot00 * dot12 - dot01 * dot02 ) * invDenom;

		// barycentric coordinates must always sum to 1
		return target.set( 1 - u - v, v, u );

	}
```
</details>

##### `containsPoint(point: Vector3, a: Vector3, b: Vector3, c: Vector3): boolean`

<details><summary>Code</summary>

```ts
static containsPoint( point, a, b, c ) {

		// if the triangle is degenerate then we can't contain a point
		if ( this.getBarycoord( point, a, b, c, _v3 ) === null ) {

			return false;

		}

		return ( _v3.x >= 0 ) && ( _v3.y >= 0 ) && ( ( _v3.x + _v3.y ) <= 1 );

	}
```
</details>

##### `getInterpolation(point: Vector3, p1: Vector3, p2: Vector3, p3: Vector3, v1: Vector3, v2: Vector3, v3: Vector3, target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
static getInterpolation( point, p1, p2, p3, v1, v2, v3, target ) {

		if ( this.getBarycoord( point, p1, p2, p3, _v3 ) === null ) {

			target.x = 0;
			target.y = 0;
			if ( 'z' in target ) target.z = 0;
			if ( 'w' in target ) target.w = 0;
			return null;

		}

		target.setScalar( 0 );
		target.addScaledVector( v1, _v3.x );
		target.addScaledVector( v2, _v3.y );
		target.addScaledVector( v3, _v3.z );

		return target;

	}
```
</details>

##### `getInterpolatedAttribute(attr: BufferAttribute, i1: number, i2: number, i3: number, barycoord: Vector3, target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
static getInterpolatedAttribute( attr, i1, i2, i3, barycoord, target ) {

		_v40.setScalar( 0 );
		_v41.setScalar( 0 );
		_v42.setScalar( 0 );

		_v40.fromBufferAttribute( attr, i1 );
		_v41.fromBufferAttribute( attr, i2 );
		_v42.fromBufferAttribute( attr, i3 );

		target.setScalar( 0 );
		target.addScaledVector( _v40, barycoord.x );
		target.addScaledVector( _v41, barycoord.y );
		target.addScaledVector( _v42, barycoord.z );

		return target;

	}
```
</details>

##### `isFrontFacing(a: Vector3, b: Vector3, c: Vector3, direction: Vector3): boolean`

<details><summary>Code</summary>

```ts
static isFrontFacing( a, b, c, direction ) {

		_v0.subVectors( c, b );
		_v1.subVectors( a, b );

		// strictly front facing
		return ( _v0.cross( _v1 ).dot( direction ) < 0 ) ? true : false;

	}
```
</details>

##### `set(a: Vector3, b: Vector3, c: Vector3): Triangle`

<details><summary>Code</summary>

```ts
set( a, b, c ) {

		this.a.copy( a );
		this.b.copy( b );
		this.c.copy( c );

		return this;

	}
```
</details>

##### `setFromPointsAndIndices(points: Vector3[], i0: number, i1: number, i2: number): Triangle`

<details><summary>Code</summary>

```ts
setFromPointsAndIndices( points, i0, i1, i2 ) {

		this.a.copy( points[ i0 ] );
		this.b.copy( points[ i1 ] );
		this.c.copy( points[ i2 ] );

		return this;

	}
```
</details>

##### `setFromAttributeAndIndices(attribute: BufferAttribute, i0: number, i1: number, i2: number): Triangle`

<details><summary>Code</summary>

```ts
setFromAttributeAndIndices( attribute, i0, i1, i2 ) {

		this.a.fromBufferAttribute( attribute, i0 );
		this.b.fromBufferAttribute( attribute, i1 );
		this.c.fromBufferAttribute( attribute, i2 );

		return this;

	}
```
</details>

##### `clone(): Triangle`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor().copy( this );

	}
```
</details>

##### `copy(triangle: Triangle): Triangle`

<details><summary>Code</summary>

```ts
copy( triangle ) {

		this.a.copy( triangle.a );
		this.b.copy( triangle.b );
		this.c.copy( triangle.c );

		return this;

	}
```
</details>

##### `getArea(): number`

<details><summary>Code</summary>

```ts
getArea() {

		_v0.subVectors( this.c, this.b );
		_v1.subVectors( this.a, this.b );

		return _v0.cross( _v1 ).length() * 0.5;

	}
```
</details>

##### `getMidpoint(target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getMidpoint( target ) {

		return target.addVectors( this.a, this.b ).add( this.c ).multiplyScalar( 1 / 3 );

	}
```
</details>

##### `getNormal(target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getNormal( target ) {

		return Triangle.getNormal( this.a, this.b, this.c, target );

	}
```
</details>

##### `getPlane(target: Plane): Plane`

<details><summary>Code</summary>

```ts
getPlane( target ) {

		return target.setFromCoplanarPoints( this.a, this.b, this.c );

	}
```
</details>

##### `getBarycoord(point: Vector3, target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getBarycoord( point, target ) {

		return Triangle.getBarycoord( point, this.a, this.b, this.c, target );

	}
```
</details>

##### `getInterpolation(point: Vector3, v1: Vector3, v2: Vector3, v3: Vector3, target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getInterpolation( point, v1, v2, v3, target ) {

		return Triangle.getInterpolation( point, this.a, this.b, this.c, v1, v2, v3, target );

	}
```
</details>

##### `containsPoint(point: Vector3): boolean`

<details><summary>Code</summary>

```ts
containsPoint( point ) {

		return Triangle.containsPoint( point, this.a, this.b, this.c );

	}
```
</details>

##### `isFrontFacing(direction: Vector3): boolean`

<details><summary>Code</summary>

```ts
isFrontFacing( direction ) {

		return Triangle.isFrontFacing( this.a, this.b, this.c, direction );

	}
```
</details>

##### `intersectsBox(box: Box3): boolean`

<details><summary>Code</summary>

```ts
intersectsBox( box ) {

		return box.intersectsTriangle( this );

	}
```
</details>

##### `closestPointToPoint(p: Vector3, target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
closestPointToPoint( p, target ) {

		const a = this.a, b = this.b, c = this.c;
		let v, w;

		// algorithm thanks to Real-Time Collision Detection by Christer Ericson,
		// published by Morgan Kaufmann Publishers, (c) 2005 Elsevier Inc.,
		// under the accompanying license; see chapter 5.1.5 for detailed explanation.
		// basically, we're distinguishing which of the voronoi regions of the triangle
		// the point lies in with the minimum amount of redundant computation.

		_vab.subVectors( b, a );
		_vac.subVectors( c, a );
		_vap.subVectors( p, a );
		const d1 = _vab.dot( _vap );
		const d2 = _vac.dot( _vap );
		if ( d1 <= 0 && d2 <= 0 ) {

			// vertex region of A; barycentric coords (1, 0, 0)
			return target.copy( a );

		}

		_vbp.subVectors( p, b );
		const d3 = _vab.dot( _vbp );
		const d4 = _vac.dot( _vbp );
		if ( d3 >= 0 && d4 <= d3 ) {

			// vertex region of B; barycentric coords (0, 1, 0)
			return target.copy( b );

		}

		const vc = d1 * d4 - d3 * d2;
		if ( vc <= 0 && d1 >= 0 && d3 <= 0 ) {

			v = d1 / ( d1 - d3 );
			// edge region of AB; barycentric coords (1-v, v, 0)
			return target.copy( a ).addScaledVector( _vab, v );

		}

		_vcp.subVectors( p, c );
		const d5 = _vab.dot( _vcp );
		const d6 = _vac.dot( _vcp );
		if ( d6 >= 0 && d5 <= d6 ) {

			// vertex region of C; barycentric coords (0, 0, 1)
			return target.copy( c );

		}

		const vb = d5 * d2 - d1 * d6;
		if ( vb <= 0 && d2 >= 0 && d6 <= 0 ) {

			w = d2 / ( d2 - d6 );
			// edge region of AC; barycentric coords (1-w, 0, w)
			return target.copy( a ).addScaledVector( _vac, w );

		}

		const va = d3 * d6 - d5 * d4;
		if ( va <= 0 && ( d4 - d3 ) >= 0 && ( d5 - d6 ) >= 0 ) {

			_vbc.subVectors( c, b );
			w = ( d4 - d3 ) / ( ( d4 - d3 ) + ( d5 - d6 ) );
			// edge region of BC; barycentric coords (0, 1-w, w)
			return target.copy( b ).addScaledVector( _vbc, w ); // edge region of BC

		}

		// face region
		const denom = 1 / ( va + vb + vc );
		// u = va * denom
		v = vb * denom;
		w = vc * denom;

		return target.copy( a ).addScaledVector( _vab, v ).addScaledVector( _vac, w );

	}
```
</details>

##### `equals(triangle: Triangle): boolean`

<details><summary>Code</summary>

```ts
equals( triangle ) {

		return triangle.a.equals( this.a ) && triangle.b.equals( this.b ) && triangle.c.equals( this.c );

	}
```
</details>


---