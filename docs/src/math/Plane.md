[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Plane.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 19 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/Plane.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Matrix3` | `./Matrix3.js` |
| `Vector3` | `./Vector3.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_vector1` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_vector2` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_normalMatrix` | `Matrix3` | let/var | `new Matrix3()` | ✗ |
| `inverseNormalLength` | `number` | let/var | `1.0 / this.normal.length()` | ✗ |
| `t` | `number` | let/var | `- ( line.start.dot( this.normal ) + this.constant ) / denominator` | ✗ |
| `normalMatrix` | `any` | let/var | `optionalNormalMatrix \|\| _normalMatrix.getNormalMatrix( matrix )` | ✗ |


---

## Functions

### `Plane.set(normal: Vector3, constant: number): Plane`

**JSDoc:**
```typescript
/**
	 * Sets the plane components by copying the given values.
	 *
	 * @param {Vector3} normal - The normal.
	 * @param {number} constant - The constant.
	 * @return {Plane} A reference to this plane.
	 */
```

**Parameters:**

- **`normal`** `Vector3`
- **`constant`** `number`

**Returns:** `Plane`

**Calls:**

- `this.normal.copy`

<details><summary>Code</summary>

```typescript
set( normal, constant ) {

		this.normal.copy( normal );
		this.constant = constant;

		return this;

	}
```
</details>

### `Plane.setComponents(x: number, y: number, z: number, w: number): Plane`

**JSDoc:**
```typescript
/**
	 * Sets the plane components by defining `x`, `y`, `z` as the
	 * plane normal and `w` as the constant.
	 *
	 * @param {number} x - The value for the normal's x component.
	 * @param {number} y - The value for the normal's y component.
	 * @param {number} z - The value for the normal's z component.
	 * @param {number} w - The constant value.
	 * @return {Plane} A reference to this plane.
	 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`
- **`z`** `number`
- **`w`** `number`

**Returns:** `Plane`

**Calls:**

- `this.normal.set`

<details><summary>Code</summary>

```typescript
setComponents( x, y, z, w ) {

		this.normal.set( x, y, z );
		this.constant = w;

		return this;

	}
```
</details>

### `Plane.setFromNormalAndCoplanarPoint(normal: Vector3, point: Vector3): Plane`

**JSDoc:**
```typescript
/**
	 * Sets the plane from the given normal and coplanar point (that is a point
	 * that lies onto the plane).
	 *
	 * @param {Vector3} normal - The normal.
	 * @param {Vector3} point - A coplanar point.
	 * @return {Plane} A reference to this plane.
	 */
```

**Parameters:**

- **`normal`** `Vector3`
- **`point`** `Vector3`

**Returns:** `Plane`

**Calls:**

- `this.normal.copy`
- `point.dot`

<details><summary>Code</summary>

```typescript
setFromNormalAndCoplanarPoint( normal, point ) {

		this.normal.copy( normal );
		this.constant = - point.dot( this.normal );

		return this;

	}
```
</details>

### `Plane.setFromCoplanarPoints(a: Vector3, b: Vector3, c: Vector3): Plane`

**JSDoc:**
```typescript
/**
	 * Sets the plane from three coplanar points. The winding order is
	 * assumed to be counter-clockwise, and determines the direction of
	 * the plane normal.
	 *
	 * @param {Vector3} a - The first coplanar point.
	 * @param {Vector3} b - The second coplanar point.
	 * @param {Vector3} c - The third coplanar point.
	 * @return {Plane} A reference to this plane.
	 */
```

**Parameters:**

- **`a`** `Vector3`
- **`b`** `Vector3`
- **`c`** `Vector3`

**Returns:** `Plane`

**Calls:**

- `_vector1.subVectors( c, b ).cross( _vector2.subVectors( a, b ) ).normalize`
- `this.setFromNormalAndCoplanarPoint`

**Internal Comments:**
```
// Q: should an error be thrown if normal is zero (e.g. degenerate plane)? (x4)
```

<details><summary>Code</summary>

```typescript
setFromCoplanarPoints( a, b, c ) {

		const normal = _vector1.subVectors( c, b ).cross( _vector2.subVectors( a, b ) ).normalize();

		// Q: should an error be thrown if normal is zero (e.g. degenerate plane)?

		this.setFromNormalAndCoplanarPoint( normal, a );

		return this;

	}
```
</details>

### `Plane.copy(plane: Plane): Plane`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given plane to this instance.
	 *
	 * @param {Plane} plane - The plane to copy.
	 * @return {Plane} A reference to this plane.
	 */
```

**Parameters:**

- **`plane`** `Plane`

**Returns:** `Plane`

**Calls:**

- `this.normal.copy`

<details><summary>Code</summary>

```typescript
copy( plane ) {

		this.normal.copy( plane.normal );
		this.constant = plane.constant;

		return this;

	}
```
</details>

### `Plane.normalize(): Plane`

**JSDoc:**
```typescript
/**
	 * Normalizes the plane normal and adjusts the constant accordingly.
	 *
	 * @return {Plane} A reference to this plane.
	 */
```

**Returns:** `Plane`

**Calls:**

- `this.normal.length`
- `this.normal.multiplyScalar`

**Internal Comments:**
```
// Note: will lead to a divide by zero if the plane is invalid. (x2)
```

<details><summary>Code</summary>

```typescript
normalize() {

		// Note: will lead to a divide by zero if the plane is invalid.

		const inverseNormalLength = 1.0 / this.normal.length();
		this.normal.multiplyScalar( inverseNormalLength );
		this.constant *= inverseNormalLength;

		return this;

	}
```
</details>

### `Plane.negate(): Plane`

**JSDoc:**
```typescript
/**
	 * Negates both the plane normal and the constant.
	 *
	 * @return {Plane} A reference to this plane.
	 */
```

**Returns:** `Plane`

**Calls:**

- `this.normal.negate`

<details><summary>Code</summary>

```typescript
negate() {

		this.constant *= - 1;
		this.normal.negate();

		return this;

	}
```
</details>

### `Plane.distanceToPoint(point: Vector3): number`

**JSDoc:**
```typescript
/**
	 * Returns the signed distance from the given point to this plane.
	 *
	 * @param {Vector3} point - The point to compute the distance for.
	 * @return {number} The signed distance.
	 */
```

**Parameters:**

- **`point`** `Vector3`

**Returns:** `number`

**Calls:**

- `this.normal.dot`

<details><summary>Code</summary>

```typescript
distanceToPoint( point ) {

		return this.normal.dot( point ) + this.constant;

	}
```
</details>

### `Plane.distanceToSphere(sphere: Sphere): number`

**JSDoc:**
```typescript
/**
	 * Returns the signed distance from the given sphere to this plane.
	 *
	 * @param {Sphere} sphere - The sphere to compute the distance for.
	 * @return {number} The signed distance.
	 */
```

**Parameters:**

- **`sphere`** `Sphere`

**Returns:** `number`

**Calls:**

- `this.distanceToPoint`

<details><summary>Code</summary>

```typescript
distanceToSphere( sphere ) {

		return this.distanceToPoint( sphere.center ) - sphere.radius;

	}
```
</details>

### `Plane.projectPoint(point: Vector3, target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Projects a the given point onto the plane.
	 *
	 * @param {Vector3} point - The point to project.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The projected point on the plane.
	 */
```

**Parameters:**

- **`point`** `Vector3`
- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `target.copy( point ).addScaledVector`
- `this.distanceToPoint`

<details><summary>Code</summary>

```typescript
projectPoint( point, target ) {

		return target.copy( point ).addScaledVector( this.normal, - this.distanceToPoint( point ) );

	}
```
</details>

### `Plane.intersectLine(line: Line3, target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Returns the intersection point of the passed line and the plane. Returns
	 * `null` if the line does not intersect. Returns the line's starting point if
	 * the line is coplanar with the plane.
	 *
	 * @param {Line3} line - The line to compute the intersection for.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {?Vector3} The intersection point.
	 */
```

**Parameters:**

- **`line`** `Line3`
- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `line.delta`
- `this.normal.dot`
- `this.distanceToPoint`
- `target.copy`
- `line.start.dot`
- `target.copy( line.start ).addScaledVector`

**Internal Comments:**
```
// line is coplanar, return origin
// Unsure if this is the correct method to handle this case.
```

<details><summary>Code</summary>

```typescript
intersectLine( line, target ) {

		const direction = line.delta( _vector1 );

		const denominator = this.normal.dot( direction );

		if ( denominator === 0 ) {

			// line is coplanar, return origin
			if ( this.distanceToPoint( line.start ) === 0 ) {

				return target.copy( line.start );

			}

			// Unsure if this is the correct method to handle this case.
			return null;

		}

		const t = - ( line.start.dot( this.normal ) + this.constant ) / denominator;

		if ( t < 0 || t > 1 ) {

			return null;

		}

		return target.copy( line.start ).addScaledVector( direction, t );

	}
```
</details>

### `Plane.intersectsLine(line: Line3): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given line segment intersects with (passes through) the plane.
	 *
	 * @param {Line3} line - The line to test.
	 * @return {boolean} Whether the given line segment intersects with the plane or not.
	 */
```

**Parameters:**

- **`line`** `Line3`

**Returns:** `boolean`

**Calls:**

- `this.distanceToPoint`

**Internal Comments:**
```
// Note: this tests if a line intersects the plane, not whether it (or its end-points) are coplanar with it. (x2)
```

<details><summary>Code</summary>

```typescript
intersectsLine( line ) {

		// Note: this tests if a line intersects the plane, not whether it (or its end-points) are coplanar with it.

		const startSign = this.distanceToPoint( line.start );
		const endSign = this.distanceToPoint( line.end );

		return ( startSign < 0 && endSign > 0 ) || ( endSign < 0 && startSign > 0 );

	}
```
</details>

### `Plane.intersectsBox(box: Box3): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given bounding box intersects with the plane.
	 *
	 * @param {Box3} box - The bounding box to test.
	 * @return {boolean} Whether the given bounding box intersects with the plane or not.
	 */
```

**Parameters:**

- **`box`** `Box3`

**Returns:** `boolean`

**Calls:**

- `box.intersectsPlane`

<details><summary>Code</summary>

```typescript
intersectsBox( box ) {

		return box.intersectsPlane( this );

	}
```
</details>

### `Plane.intersectsSphere(sphere: Sphere): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given bounding sphere intersects with the plane.
	 *
	 * @param {Sphere} sphere - The bounding sphere to test.
	 * @return {boolean} Whether the given bounding sphere intersects with the plane or not.
	 */
```

**Parameters:**

- **`sphere`** `Sphere`

**Returns:** `boolean`

**Calls:**

- `sphere.intersectsPlane`

<details><summary>Code</summary>

```typescript
intersectsSphere( sphere ) {

		return sphere.intersectsPlane( this );

	}
```
</details>

### `Plane.coplanarPoint(target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Returns a coplanar vector to the plane, by calculating the
	 * projection of the normal at the origin onto the plane.
	 *
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The coplanar point.
	 */
```

**Parameters:**

- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `target.copy( this.normal ).multiplyScalar`

<details><summary>Code</summary>

```typescript
coplanarPoint( target ) {

		return target.copy( this.normal ).multiplyScalar( - this.constant );

	}
```
</details>

### `Plane.applyMatrix4(matrix: Matrix4, optionalNormalMatrix: Matrix4): Plane`

**JSDoc:**
```typescript
/**
	 * Apply a 4x4 matrix to the plane. The matrix must be an affine, homogeneous transform.
	 *
	 * The optional normal matrix can be pre-computed like so:
	 * ```js
	 * const optionalNormalMatrix = new THREE.Matrix3().getNormalMatrix( matrix );
	 * ```
	 *
	 * @param {Matrix4} matrix - The transformation matrix.
	 * @param {Matrix4} [optionalNormalMatrix] - A pre-computed normal matrix.
	 * @return {Plane} A reference to this plane.
	 */
```

**Parameters:**

- **`matrix`** `Matrix4`
- **`optionalNormalMatrix`** `Matrix4`

**Returns:** `Plane`

**Calls:**

- `_normalMatrix.getNormalMatrix`
- `this.coplanarPoint( _vector1 ).applyMatrix4`
- `this.normal.applyMatrix3( normalMatrix ).normalize`
- `referencePoint.dot`

<details><summary>Code</summary>

```typescript
applyMatrix4( matrix, optionalNormalMatrix ) {

		const normalMatrix = optionalNormalMatrix || _normalMatrix.getNormalMatrix( matrix );

		const referencePoint = this.coplanarPoint( _vector1 ).applyMatrix4( matrix );

		const normal = this.normal.applyMatrix3( normalMatrix ).normalize();

		this.constant = - referencePoint.dot( normal );

		return this;

	}
```
</details>

### `Plane.translate(offset: Vector3): Plane`

**JSDoc:**
```typescript
/**
	 * Translates the plane by the distance defined by the given offset vector.
	 * Note that this only affects the plane constant and will not affect the normal vector.
	 *
	 * @param {Vector3} offset - The offset vector.
	 * @return {Plane} A reference to this plane.
	 */
```

**Parameters:**

- **`offset`** `Vector3`

**Returns:** `Plane`

**Calls:**

- `offset.dot`

<details><summary>Code</summary>

```typescript
translate( offset ) {

		this.constant -= offset.dot( this.normal );

		return this;

	}
```
</details>

### `Plane.equals(plane: Plane): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this plane is equal with the given one.
	 *
	 * @param {Plane} plane - The plane to test for equality.
	 * @return {boolean} Whether this plane is equal with the given one.
	 */
```

**Parameters:**

- **`plane`** `Plane`

**Returns:** `boolean`

**Calls:**

- `plane.normal.equals`

<details><summary>Code</summary>

```typescript
equals( plane ) {

		return plane.normal.equals( this.normal ) && ( plane.constant === this.constant );

	}
```
</details>

### `Plane.clone(): Plane`

**JSDoc:**
```typescript
/**
	 * Returns a new plane with copied values from this instance.
	 *
	 * @return {Plane} A clone of this instance.
	 */
```

**Returns:** `Plane`

**Calls:**

- `new this.constructor().copy`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor().copy( this );

	}
```
</details>


---

## Classes

### `Plane`

<details><summary>Class Code</summary>

```ts
class Plane {

	/**
	 * Constructs a new plane.
	 *
	 * @param {Vector3} [normal=(1,0,0)] - A unit length vector defining the normal of the plane.
	 * @param {number} [constant=0] - The signed distance from the origin to the plane.
	 */
	constructor( normal = new Vector3( 1, 0, 0 ), constant = 0 ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isPlane = true;

		/**
		 * A unit length vector defining the normal of the plane.
		 *
		 * @type {Vector3}
		 */
		this.normal = normal;

		/**
		 * The signed distance from the origin to the plane.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.constant = constant;

	}

	/**
	 * Sets the plane components by copying the given values.
	 *
	 * @param {Vector3} normal - The normal.
	 * @param {number} constant - The constant.
	 * @return {Plane} A reference to this plane.
	 */
	set( normal, constant ) {

		this.normal.copy( normal );
		this.constant = constant;

		return this;

	}

	/**
	 * Sets the plane components by defining `x`, `y`, `z` as the
	 * plane normal and `w` as the constant.
	 *
	 * @param {number} x - The value for the normal's x component.
	 * @param {number} y - The value for the normal's y component.
	 * @param {number} z - The value for the normal's z component.
	 * @param {number} w - The constant value.
	 * @return {Plane} A reference to this plane.
	 */
	setComponents( x, y, z, w ) {

		this.normal.set( x, y, z );
		this.constant = w;

		return this;

	}

	/**
	 * Sets the plane from the given normal and coplanar point (that is a point
	 * that lies onto the plane).
	 *
	 * @param {Vector3} normal - The normal.
	 * @param {Vector3} point - A coplanar point.
	 * @return {Plane} A reference to this plane.
	 */
	setFromNormalAndCoplanarPoint( normal, point ) {

		this.normal.copy( normal );
		this.constant = - point.dot( this.normal );

		return this;

	}

	/**
	 * Sets the plane from three coplanar points. The winding order is
	 * assumed to be counter-clockwise, and determines the direction of
	 * the plane normal.
	 *
	 * @param {Vector3} a - The first coplanar point.
	 * @param {Vector3} b - The second coplanar point.
	 * @param {Vector3} c - The third coplanar point.
	 * @return {Plane} A reference to this plane.
	 */
	setFromCoplanarPoints( a, b, c ) {

		const normal = _vector1.subVectors( c, b ).cross( _vector2.subVectors( a, b ) ).normalize();

		// Q: should an error be thrown if normal is zero (e.g. degenerate plane)?

		this.setFromNormalAndCoplanarPoint( normal, a );

		return this;

	}

	/**
	 * Copies the values of the given plane to this instance.
	 *
	 * @param {Plane} plane - The plane to copy.
	 * @return {Plane} A reference to this plane.
	 */
	copy( plane ) {

		this.normal.copy( plane.normal );
		this.constant = plane.constant;

		return this;

	}

	/**
	 * Normalizes the plane normal and adjusts the constant accordingly.
	 *
	 * @return {Plane} A reference to this plane.
	 */
	normalize() {

		// Note: will lead to a divide by zero if the plane is invalid.

		const inverseNormalLength = 1.0 / this.normal.length();
		this.normal.multiplyScalar( inverseNormalLength );
		this.constant *= inverseNormalLength;

		return this;

	}

	/**
	 * Negates both the plane normal and the constant.
	 *
	 * @return {Plane} A reference to this plane.
	 */
	negate() {

		this.constant *= - 1;
		this.normal.negate();

		return this;

	}

	/**
	 * Returns the signed distance from the given point to this plane.
	 *
	 * @param {Vector3} point - The point to compute the distance for.
	 * @return {number} The signed distance.
	 */
	distanceToPoint( point ) {

		return this.normal.dot( point ) + this.constant;

	}

	/**
	 * Returns the signed distance from the given sphere to this plane.
	 *
	 * @param {Sphere} sphere - The sphere to compute the distance for.
	 * @return {number} The signed distance.
	 */
	distanceToSphere( sphere ) {

		return this.distanceToPoint( sphere.center ) - sphere.radius;

	}

	/**
	 * Projects a the given point onto the plane.
	 *
	 * @param {Vector3} point - The point to project.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The projected point on the plane.
	 */
	projectPoint( point, target ) {

		return target.copy( point ).addScaledVector( this.normal, - this.distanceToPoint( point ) );

	}

	/**
	 * Returns the intersection point of the passed line and the plane. Returns
	 * `null` if the line does not intersect. Returns the line's starting point if
	 * the line is coplanar with the plane.
	 *
	 * @param {Line3} line - The line to compute the intersection for.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {?Vector3} The intersection point.
	 */
	intersectLine( line, target ) {

		const direction = line.delta( _vector1 );

		const denominator = this.normal.dot( direction );

		if ( denominator === 0 ) {

			// line is coplanar, return origin
			if ( this.distanceToPoint( line.start ) === 0 ) {

				return target.copy( line.start );

			}

			// Unsure if this is the correct method to handle this case.
			return null;

		}

		const t = - ( line.start.dot( this.normal ) + this.constant ) / denominator;

		if ( t < 0 || t > 1 ) {

			return null;

		}

		return target.copy( line.start ).addScaledVector( direction, t );

	}

	/**
	 * Returns `true` if the given line segment intersects with (passes through) the plane.
	 *
	 * @param {Line3} line - The line to test.
	 * @return {boolean} Whether the given line segment intersects with the plane or not.
	 */
	intersectsLine( line ) {

		// Note: this tests if a line intersects the plane, not whether it (or its end-points) are coplanar with it.

		const startSign = this.distanceToPoint( line.start );
		const endSign = this.distanceToPoint( line.end );

		return ( startSign < 0 && endSign > 0 ) || ( endSign < 0 && startSign > 0 );

	}

	/**
	 * Returns `true` if the given bounding box intersects with the plane.
	 *
	 * @param {Box3} box - The bounding box to test.
	 * @return {boolean} Whether the given bounding box intersects with the plane or not.
	 */
	intersectsBox( box ) {

		return box.intersectsPlane( this );

	}

	/**
	 * Returns `true` if the given bounding sphere intersects with the plane.
	 *
	 * @param {Sphere} sphere - The bounding sphere to test.
	 * @return {boolean} Whether the given bounding sphere intersects with the plane or not.
	 */
	intersectsSphere( sphere ) {

		return sphere.intersectsPlane( this );

	}

	/**
	 * Returns a coplanar vector to the plane, by calculating the
	 * projection of the normal at the origin onto the plane.
	 *
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The coplanar point.
	 */
	coplanarPoint( target ) {

		return target.copy( this.normal ).multiplyScalar( - this.constant );

	}

	/**
	 * Apply a 4x4 matrix to the plane. The matrix must be an affine, homogeneous transform.
	 *
	 * The optional normal matrix can be pre-computed like so:
	 * ```js
	 * const optionalNormalMatrix = new THREE.Matrix3().getNormalMatrix( matrix );
	 * ```
	 *
	 * @param {Matrix4} matrix - The transformation matrix.
	 * @param {Matrix4} [optionalNormalMatrix] - A pre-computed normal matrix.
	 * @return {Plane} A reference to this plane.
	 */
	applyMatrix4( matrix, optionalNormalMatrix ) {

		const normalMatrix = optionalNormalMatrix || _normalMatrix.getNormalMatrix( matrix );

		const referencePoint = this.coplanarPoint( _vector1 ).applyMatrix4( matrix );

		const normal = this.normal.applyMatrix3( normalMatrix ).normalize();

		this.constant = - referencePoint.dot( normal );

		return this;

	}

	/**
	 * Translates the plane by the distance defined by the given offset vector.
	 * Note that this only affects the plane constant and will not affect the normal vector.
	 *
	 * @param {Vector3} offset - The offset vector.
	 * @return {Plane} A reference to this plane.
	 */
	translate( offset ) {

		this.constant -= offset.dot( this.normal );

		return this;

	}

	/**
	 * Returns `true` if this plane is equal with the given one.
	 *
	 * @param {Plane} plane - The plane to test for equality.
	 * @return {boolean} Whether this plane is equal with the given one.
	 */
	equals( plane ) {

		return plane.normal.equals( this.normal ) && ( plane.constant === this.constant );

	}

	/**
	 * Returns a new plane with copied values from this instance.
	 *
	 * @return {Plane} A clone of this instance.
	 */
	clone() {

		return new this.constructor().copy( this );

	}

}
```
</details>

#### Methods

##### `set(normal: Vector3, constant: number): Plane`

<details><summary>Code</summary>

```ts
set( normal, constant ) {

		this.normal.copy( normal );
		this.constant = constant;

		return this;

	}
```
</details>

##### `setComponents(x: number, y: number, z: number, w: number): Plane`

<details><summary>Code</summary>

```ts
setComponents( x, y, z, w ) {

		this.normal.set( x, y, z );
		this.constant = w;

		return this;

	}
```
</details>

##### `setFromNormalAndCoplanarPoint(normal: Vector3, point: Vector3): Plane`

<details><summary>Code</summary>

```ts
setFromNormalAndCoplanarPoint( normal, point ) {

		this.normal.copy( normal );
		this.constant = - point.dot( this.normal );

		return this;

	}
```
</details>

##### `setFromCoplanarPoints(a: Vector3, b: Vector3, c: Vector3): Plane`

<details><summary>Code</summary>

```ts
setFromCoplanarPoints( a, b, c ) {

		const normal = _vector1.subVectors( c, b ).cross( _vector2.subVectors( a, b ) ).normalize();

		// Q: should an error be thrown if normal is zero (e.g. degenerate plane)?

		this.setFromNormalAndCoplanarPoint( normal, a );

		return this;

	}
```
</details>

##### `copy(plane: Plane): Plane`

<details><summary>Code</summary>

```ts
copy( plane ) {

		this.normal.copy( plane.normal );
		this.constant = plane.constant;

		return this;

	}
```
</details>

##### `normalize(): Plane`

<details><summary>Code</summary>

```ts
normalize() {

		// Note: will lead to a divide by zero if the plane is invalid.

		const inverseNormalLength = 1.0 / this.normal.length();
		this.normal.multiplyScalar( inverseNormalLength );
		this.constant *= inverseNormalLength;

		return this;

	}
```
</details>

##### `negate(): Plane`

<details><summary>Code</summary>

```ts
negate() {

		this.constant *= - 1;
		this.normal.negate();

		return this;

	}
```
</details>

##### `distanceToPoint(point: Vector3): number`

<details><summary>Code</summary>

```ts
distanceToPoint( point ) {

		return this.normal.dot( point ) + this.constant;

	}
```
</details>

##### `distanceToSphere(sphere: Sphere): number`

<details><summary>Code</summary>

```ts
distanceToSphere( sphere ) {

		return this.distanceToPoint( sphere.center ) - sphere.radius;

	}
```
</details>

##### `projectPoint(point: Vector3, target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
projectPoint( point, target ) {

		return target.copy( point ).addScaledVector( this.normal, - this.distanceToPoint( point ) );

	}
```
</details>

##### `intersectLine(line: Line3, target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
intersectLine( line, target ) {

		const direction = line.delta( _vector1 );

		const denominator = this.normal.dot( direction );

		if ( denominator === 0 ) {

			// line is coplanar, return origin
			if ( this.distanceToPoint( line.start ) === 0 ) {

				return target.copy( line.start );

			}

			// Unsure if this is the correct method to handle this case.
			return null;

		}

		const t = - ( line.start.dot( this.normal ) + this.constant ) / denominator;

		if ( t < 0 || t > 1 ) {

			return null;

		}

		return target.copy( line.start ).addScaledVector( direction, t );

	}
```
</details>

##### `intersectsLine(line: Line3): boolean`

<details><summary>Code</summary>

```ts
intersectsLine( line ) {

		// Note: this tests if a line intersects the plane, not whether it (or its end-points) are coplanar with it.

		const startSign = this.distanceToPoint( line.start );
		const endSign = this.distanceToPoint( line.end );

		return ( startSign < 0 && endSign > 0 ) || ( endSign < 0 && startSign > 0 );

	}
```
</details>

##### `intersectsBox(box: Box3): boolean`

<details><summary>Code</summary>

```ts
intersectsBox( box ) {

		return box.intersectsPlane( this );

	}
```
</details>

##### `intersectsSphere(sphere: Sphere): boolean`

<details><summary>Code</summary>

```ts
intersectsSphere( sphere ) {

		return sphere.intersectsPlane( this );

	}
```
</details>

##### `coplanarPoint(target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
coplanarPoint( target ) {

		return target.copy( this.normal ).multiplyScalar( - this.constant );

	}
```
</details>

##### `applyMatrix4(matrix: Matrix4, optionalNormalMatrix: Matrix4): Plane`

<details><summary>Code</summary>

```ts
applyMatrix4( matrix, optionalNormalMatrix ) {

		const normalMatrix = optionalNormalMatrix || _normalMatrix.getNormalMatrix( matrix );

		const referencePoint = this.coplanarPoint( _vector1 ).applyMatrix4( matrix );

		const normal = this.normal.applyMatrix3( normalMatrix ).normalize();

		this.constant = - referencePoint.dot( normal );

		return this;

	}
```
</details>

##### `translate(offset: Vector3): Plane`

<details><summary>Code</summary>

```ts
translate( offset ) {

		this.constant -= offset.dot( this.normal );

		return this;

	}
```
</details>

##### `equals(plane: Plane): boolean`

<details><summary>Code</summary>

```ts
equals( plane ) {

		return plane.normal.equals( this.normal ) && ( plane.constant === this.constant );

	}
```
</details>

##### `clone(): Plane`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor().copy( this );

	}
```
</details>


---