[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sphere.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 20 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/Sphere.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Box3` | `./Box3.js` |
| `Vector3` | `./Vector3.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_box` | `Box3` | let/var | `new Box3()` | ✗ |
| `_v1` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_v2` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `center` | `Vector3` | let/var | `this.center` | ✗ |
| `maxRadiusSq` | `number` | let/var | `0` | ✗ |
| `radiusSum` | `number` | let/var | `this.radius + sphere.radius` | ✗ |
| `delta` | `number` | let/var | `( length - this.radius ) * 0.5` | ✗ |


---

## Functions

### `Sphere.set(center: Vector3, radius: number): Sphere`

**JSDoc:**
```typescript
/**
	 * Sets the sphere's components by copying the given values.
	 *
	 * @param {Vector3} center - The center.
	 * @param {number} radius - The radius.
	 * @return {Sphere} A reference to this sphere.
	 */
```

**Parameters:**

- **`center`** `Vector3`
- **`radius`** `number`

**Returns:** `Sphere`

**Calls:**

- `this.center.copy`

<details><summary>Code</summary>

```typescript
set( center, radius ) {

		this.center.copy( center );
		this.radius = radius;

		return this;

	}
```
</details>

### `Sphere.setFromPoints(points: Vector3[], optionalCenter: Vector3): Sphere`

**JSDoc:**
```typescript
/**
	 * Computes the minimum bounding sphere for list of points.
	 * If the optional center point is given, it is used as the sphere's
	 * center. Otherwise, the center of the axis-aligned bounding box
	 * encompassing the points is calculated.
	 *
	 * @param {Array<Vector3>} points - A list of points in 3D space.
	 * @param {Vector3} [optionalCenter] - The center of the sphere.
	 * @return {Sphere} A reference to this sphere.
	 */
```

**Parameters:**

- **`points`** `Vector3[]`
- **`optionalCenter`** `Vector3`

**Returns:** `Sphere`

**Calls:**

- `center.copy`
- `_box.setFromPoints( points ).getCenter`
- `Math.max`
- `center.distanceToSquared`
- `Math.sqrt`

<details><summary>Code</summary>

```typescript
setFromPoints( points, optionalCenter ) {

		const center = this.center;

		if ( optionalCenter !== undefined ) {

			center.copy( optionalCenter );

		} else {

			_box.setFromPoints( points ).getCenter( center );

		}

		let maxRadiusSq = 0;

		for ( let i = 0, il = points.length; i < il; i ++ ) {

			maxRadiusSq = Math.max( maxRadiusSq, center.distanceToSquared( points[ i ] ) );

		}

		this.radius = Math.sqrt( maxRadiusSq );

		return this;

	}
```
</details>

### `Sphere.copy(sphere: Sphere): Sphere`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given sphere to this instance.
	 *
	 * @param {Sphere} sphere - The sphere to copy.
	 * @return {Sphere} A reference to this sphere.
	 */
```

**Parameters:**

- **`sphere`** `Sphere`

**Returns:** `Sphere`

**Calls:**

- `this.center.copy`

<details><summary>Code</summary>

```typescript
copy( sphere ) {

		this.center.copy( sphere.center );
		this.radius = sphere.radius;

		return this;

	}
```
</details>

### `Sphere.isEmpty(): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the sphere is empty (the radius set to a negative number).
	 *
	 * Spheres with a radius of `0` contain only their center point and are not
	 * considered to be empty.
	 *
	 * @return {boolean} Whether this sphere is empty or not.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
isEmpty() {

		return ( this.radius < 0 );

	}
```
</details>

### `Sphere.makeEmpty(): Sphere`

**JSDoc:**
```typescript
/**
	 * Makes this sphere empty which means in encloses a zero space in 3D.
	 *
	 * @return {Sphere} A reference to this sphere.
	 */
```

**Returns:** `Sphere`

**Calls:**

- `this.center.set`

<details><summary>Code</summary>

```typescript
makeEmpty() {

		this.center.set( 0, 0, 0 );
		this.radius = - 1;

		return this;

	}
```
</details>

### `Sphere.containsPoint(point: Vector3): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this sphere contains the given point inclusive of
	 * the surface of the sphere.
	 *
	 * @param {Vector3} point - The point to check.
	 * @return {boolean} Whether this sphere contains the given point or not.
	 */
```

**Parameters:**

- **`point`** `Vector3`

**Returns:** `boolean`

**Calls:**

- `point.distanceToSquared`

<details><summary>Code</summary>

```typescript
containsPoint( point ) {

		return ( point.distanceToSquared( this.center ) <= ( this.radius * this.radius ) );

	}
```
</details>

### `Sphere.distanceToPoint(point: Vector3): number`

**JSDoc:**
```typescript
/**
	 * Returns the closest distance from the boundary of the sphere to the
	 * given point. If the sphere contains the point, the distance will
	 * be negative.
	 *
	 * @param {Vector3} point - The point to compute the distance to.
	 * @return {number} The distance to the point.
	 */
```

**Parameters:**

- **`point`** `Vector3`

**Returns:** `number`

**Calls:**

- `point.distanceTo`

<details><summary>Code</summary>

```typescript
distanceToPoint( point ) {

		return ( point.distanceTo( this.center ) - this.radius );

	}
```
</details>

### `Sphere.intersectsSphere(sphere: Sphere): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this sphere intersects with the given one.
	 *
	 * @param {Sphere} sphere - The sphere to test.
	 * @return {boolean} Whether this sphere intersects with the given one or not.
	 */
```

**Parameters:**

- **`sphere`** `Sphere`

**Returns:** `boolean`

**Calls:**

- `sphere.center.distanceToSquared`

<details><summary>Code</summary>

```typescript
intersectsSphere( sphere ) {

		const radiusSum = this.radius + sphere.radius;

		return sphere.center.distanceToSquared( this.center ) <= ( radiusSum * radiusSum );

	}
```
</details>

### `Sphere.intersectsBox(box: Box3): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this sphere intersects with the given box.
	 *
	 * @param {Box3} box - The box to test.
	 * @return {boolean} Whether this sphere intersects with the given box or not.
	 */
```

**Parameters:**

- **`box`** `Box3`

**Returns:** `boolean`

**Calls:**

- `box.intersectsSphere`

<details><summary>Code</summary>

```typescript
intersectsBox( box ) {

		return box.intersectsSphere( this );

	}
```
</details>

### `Sphere.intersectsPlane(plane: Plane): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this sphere intersects with the given plane.
	 *
	 * @param {Plane} plane - The plane to test.
	 * @return {boolean} Whether this sphere intersects with the given plane or not.
	 */
```

**Parameters:**

- **`plane`** `Plane`

**Returns:** `boolean`

**Calls:**

- `Math.abs`
- `plane.distanceToPoint`

<details><summary>Code</summary>

```typescript
intersectsPlane( plane ) {

		return Math.abs( plane.distanceToPoint( this.center ) ) <= this.radius;

	}
```
</details>

### `Sphere.clampPoint(point: Vector3, target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Clamps a point within the sphere. If the point is outside the sphere, it
	 * will clamp it to the closest point on the edge of the sphere. Points
	 * already inside the sphere will not be affected.
	 *
	 * @param {Vector3} point - The plane to clamp.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The clamped point.
	 */
```

**Parameters:**

- **`point`** `Vector3`
- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `this.center.distanceToSquared`
- `target.copy`
- `target.sub( this.center ).normalize`
- `target.multiplyScalar( this.radius ).add`

<details><summary>Code</summary>

```typescript
clampPoint( point, target ) {

		const deltaLengthSq = this.center.distanceToSquared( point );

		target.copy( point );

		if ( deltaLengthSq > ( this.radius * this.radius ) ) {

			target.sub( this.center ).normalize();
			target.multiplyScalar( this.radius ).add( this.center );

		}

		return target;

	}
```
</details>

### `Sphere.getBoundingBox(target: Box3): Box3`

**JSDoc:**
```typescript
/**
	 * Returns a bounding box that encloses this sphere.
	 *
	 * @param {Box3} target - The target box that is used to store the method's result.
	 * @return {Box3} The bounding box that encloses this sphere.
	 */
```

**Parameters:**

- **`target`** `Box3`

**Returns:** `Box3`

**Calls:**

- `this.isEmpty`
- `target.makeEmpty`
- `target.set`
- `target.expandByScalar`

**Internal Comments:**
```
// Empty sphere produces empty bounding box (x4)
```

<details><summary>Code</summary>

```typescript
getBoundingBox( target ) {

		if ( this.isEmpty() ) {

			// Empty sphere produces empty bounding box
			target.makeEmpty();
			return target;

		}

		target.set( this.center, this.center );
		target.expandByScalar( this.radius );

		return target;

	}
```
</details>

### `Sphere.applyMatrix4(matrix: Matrix4): Sphere`

**JSDoc:**
```typescript
/**
	 * Transforms this sphere with the given 4x4 transformation matrix.
	 *
	 * @param {Matrix4} matrix - The transformation matrix.
	 * @return {Sphere} A reference to this sphere.
	 */
```

**Parameters:**

- **`matrix`** `Matrix4`

**Returns:** `Sphere`

**Calls:**

- `this.center.applyMatrix4`
- `matrix.getMaxScaleOnAxis`

<details><summary>Code</summary>

```typescript
applyMatrix4( matrix ) {

		this.center.applyMatrix4( matrix );
		this.radius = this.radius * matrix.getMaxScaleOnAxis();

		return this;

	}
```
</details>

### `Sphere.translate(offset: Vector3): Sphere`

**JSDoc:**
```typescript
/**
	 * Translates the sphere's center by the given offset.
	 *
	 * @param {Vector3} offset - The offset.
	 * @return {Sphere} A reference to this sphere.
	 */
```

**Parameters:**

- **`offset`** `Vector3`

**Returns:** `Sphere`

**Calls:**

- `this.center.add`

<details><summary>Code</summary>

```typescript
translate( offset ) {

		this.center.add( offset );

		return this;

	}
```
</details>

### `Sphere.expandByPoint(point: Vector3): Sphere`

**JSDoc:**
```typescript
/**
	 * Expands the boundaries of this sphere to include the given point.
	 *
	 * @param {Vector3} point - The point to include.
	 * @return {Sphere} A reference to this sphere.
	 */
```

**Parameters:**

- **`point`** `Vector3`

**Returns:** `Sphere`

**Calls:**

- `this.isEmpty`
- `this.center.copy`
- `_v1.subVectors`
- `_v1.lengthSq`
- `Math.sqrt`
- `this.center.addScaledVector`

**Internal Comments:**
```
// calculate the minimal sphere (x2)
```

<details><summary>Code</summary>

```typescript
expandByPoint( point ) {

		if ( this.isEmpty() ) {

			this.center.copy( point );

			this.radius = 0;

			return this;

		}

		_v1.subVectors( point, this.center );

		const lengthSq = _v1.lengthSq();

		if ( lengthSq > ( this.radius * this.radius ) ) {

			// calculate the minimal sphere

			const length = Math.sqrt( lengthSq );

			const delta = ( length - this.radius ) * 0.5;

			this.center.addScaledVector( _v1, delta / length );

			this.radius += delta;

		}

		return this;

	}
```
</details>

### `Sphere.union(sphere: Sphere): Sphere`

**JSDoc:**
```typescript
/**
	 * Expands this sphere to enclose both the original sphere and the given sphere.
	 *
	 * @param {Sphere} sphere - The sphere to include.
	 * @return {Sphere} A reference to this sphere.
	 */
```

**Parameters:**

- **`sphere`** `Sphere`

**Returns:** `Sphere`

**Calls:**

- `sphere.isEmpty`
- `this.isEmpty`
- `this.copy`
- `this.center.equals`
- `Math.max`
- `_v2.subVectors( sphere.center, this.center ).setLength`
- `this.expandByPoint`
- `_v1.copy( sphere.center ).add`
- `_v1.copy( sphere.center ).sub`

<details><summary>Code</summary>

```typescript
union( sphere ) {

		if ( sphere.isEmpty() ) {

			return this;

		}

		if ( this.isEmpty() ) {

			this.copy( sphere );

			return this;

		}

		if ( this.center.equals( sphere.center ) === true ) {

			 this.radius = Math.max( this.radius, sphere.radius );

		} else {

			_v2.subVectors( sphere.center, this.center ).setLength( sphere.radius );

			this.expandByPoint( _v1.copy( sphere.center ).add( _v2 ) );

			this.expandByPoint( _v1.copy( sphere.center ).sub( _v2 ) );

		}

		return this;

	}
```
</details>

### `Sphere.equals(sphere: Sphere): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this sphere is equal with the given one.
	 *
	 * @param {Sphere} sphere - The sphere to test for equality.
	 * @return {boolean} Whether this bounding sphere is equal with the given one.
	 */
```

**Parameters:**

- **`sphere`** `Sphere`

**Returns:** `boolean`

**Calls:**

- `sphere.center.equals`

<details><summary>Code</summary>

```typescript
equals( sphere ) {

		return sphere.center.equals( this.center ) && ( sphere.radius === this.radius );

	}
```
</details>

### `Sphere.clone(): Sphere`

**JSDoc:**
```typescript
/**
	 * Returns a new sphere with copied values from this instance.
	 *
	 * @return {Sphere} A clone of this instance.
	 */
```

**Returns:** `Sphere`

**Calls:**

- `new this.constructor().copy`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor().copy( this );

	}
```
</details>

### `Sphere.toJSON(): any`

**JSDoc:**
```typescript
/**
	 * Returns a serialized structure of the bounding sphere.
	 *
	 * @return {Object} Serialized structure with fields representing the object state.
	 */
```

**Returns:** `any`

**Calls:**

- `this.center.toArray`

<details><summary>Code</summary>

```typescript
toJSON() {

		return {
			radius: this.radius,
			center: this.center.toArray()
		};

	}
```
</details>

### `Sphere.fromJSON(json: any): Box3`

**JSDoc:**
```typescript
/**
	 * Returns a serialized structure of the bounding sphere.
	 *
	 * @param {Object} json - The serialized json to set the sphere from.
	 * @return {Box3} A reference to this bounding sphere.
	 */
```

**Parameters:**

- **`json`** `any`

**Returns:** `Box3`

**Calls:**

- `this.center.fromArray`

<details><summary>Code</summary>

```typescript
fromJSON( json ) {

		this.radius = json.radius;
		this.center.fromArray( json.center );
		return this;

	}
```
</details>


---

## Classes

### `Sphere`

<details><summary>Class Code</summary>

```ts
class Sphere {

	/**
	 * Constructs a new sphere.
	 *
	 * @param {Vector3} [center=(0,0,0)] - The center of the sphere
	 * @param {number} [radius=-1] - The radius of the sphere.
	 */
	constructor( center = new Vector3(), radius = - 1 ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSphere = true;

		/**
		 * The center of the sphere
		 *
		 * @type {Vector3}
		 */
		this.center = center;

		/**
		 * The radius of the sphere.
		 *
		 * @type {number}
		 */
		this.radius = radius;

	}

	/**
	 * Sets the sphere's components by copying the given values.
	 *
	 * @param {Vector3} center - The center.
	 * @param {number} radius - The radius.
	 * @return {Sphere} A reference to this sphere.
	 */
	set( center, radius ) {

		this.center.copy( center );
		this.radius = radius;

		return this;

	}

	/**
	 * Computes the minimum bounding sphere for list of points.
	 * If the optional center point is given, it is used as the sphere's
	 * center. Otherwise, the center of the axis-aligned bounding box
	 * encompassing the points is calculated.
	 *
	 * @param {Array<Vector3>} points - A list of points in 3D space.
	 * @param {Vector3} [optionalCenter] - The center of the sphere.
	 * @return {Sphere} A reference to this sphere.
	 */
	setFromPoints( points, optionalCenter ) {

		const center = this.center;

		if ( optionalCenter !== undefined ) {

			center.copy( optionalCenter );

		} else {

			_box.setFromPoints( points ).getCenter( center );

		}

		let maxRadiusSq = 0;

		for ( let i = 0, il = points.length; i < il; i ++ ) {

			maxRadiusSq = Math.max( maxRadiusSq, center.distanceToSquared( points[ i ] ) );

		}

		this.radius = Math.sqrt( maxRadiusSq );

		return this;

	}

	/**
	 * Copies the values of the given sphere to this instance.
	 *
	 * @param {Sphere} sphere - The sphere to copy.
	 * @return {Sphere} A reference to this sphere.
	 */
	copy( sphere ) {

		this.center.copy( sphere.center );
		this.radius = sphere.radius;

		return this;

	}

	/**
	 * Returns `true` if the sphere is empty (the radius set to a negative number).
	 *
	 * Spheres with a radius of `0` contain only their center point and are not
	 * considered to be empty.
	 *
	 * @return {boolean} Whether this sphere is empty or not.
	 */
	isEmpty() {

		return ( this.radius < 0 );

	}

	/**
	 * Makes this sphere empty which means in encloses a zero space in 3D.
	 *
	 * @return {Sphere} A reference to this sphere.
	 */
	makeEmpty() {

		this.center.set( 0, 0, 0 );
		this.radius = - 1;

		return this;

	}

	/**
	 * Returns `true` if this sphere contains the given point inclusive of
	 * the surface of the sphere.
	 *
	 * @param {Vector3} point - The point to check.
	 * @return {boolean} Whether this sphere contains the given point or not.
	 */
	containsPoint( point ) {

		return ( point.distanceToSquared( this.center ) <= ( this.radius * this.radius ) );

	}

	/**
	 * Returns the closest distance from the boundary of the sphere to the
	 * given point. If the sphere contains the point, the distance will
	 * be negative.
	 *
	 * @param {Vector3} point - The point to compute the distance to.
	 * @return {number} The distance to the point.
	 */
	distanceToPoint( point ) {

		return ( point.distanceTo( this.center ) - this.radius );

	}

	/**
	 * Returns `true` if this sphere intersects with the given one.
	 *
	 * @param {Sphere} sphere - The sphere to test.
	 * @return {boolean} Whether this sphere intersects with the given one or not.
	 */
	intersectsSphere( sphere ) {

		const radiusSum = this.radius + sphere.radius;

		return sphere.center.distanceToSquared( this.center ) <= ( radiusSum * radiusSum );

	}

	/**
	 * Returns `true` if this sphere intersects with the given box.
	 *
	 * @param {Box3} box - The box to test.
	 * @return {boolean} Whether this sphere intersects with the given box or not.
	 */
	intersectsBox( box ) {

		return box.intersectsSphere( this );

	}

	/**
	 * Returns `true` if this sphere intersects with the given plane.
	 *
	 * @param {Plane} plane - The plane to test.
	 * @return {boolean} Whether this sphere intersects with the given plane or not.
	 */
	intersectsPlane( plane ) {

		return Math.abs( plane.distanceToPoint( this.center ) ) <= this.radius;

	}

	/**
	 * Clamps a point within the sphere. If the point is outside the sphere, it
	 * will clamp it to the closest point on the edge of the sphere. Points
	 * already inside the sphere will not be affected.
	 *
	 * @param {Vector3} point - The plane to clamp.
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The clamped point.
	 */
	clampPoint( point, target ) {

		const deltaLengthSq = this.center.distanceToSquared( point );

		target.copy( point );

		if ( deltaLengthSq > ( this.radius * this.radius ) ) {

			target.sub( this.center ).normalize();
			target.multiplyScalar( this.radius ).add( this.center );

		}

		return target;

	}

	/**
	 * Returns a bounding box that encloses this sphere.
	 *
	 * @param {Box3} target - The target box that is used to store the method's result.
	 * @return {Box3} The bounding box that encloses this sphere.
	 */
	getBoundingBox( target ) {

		if ( this.isEmpty() ) {

			// Empty sphere produces empty bounding box
			target.makeEmpty();
			return target;

		}

		target.set( this.center, this.center );
		target.expandByScalar( this.radius );

		return target;

	}

	/**
	 * Transforms this sphere with the given 4x4 transformation matrix.
	 *
	 * @param {Matrix4} matrix - The transformation matrix.
	 * @return {Sphere} A reference to this sphere.
	 */
	applyMatrix4( matrix ) {

		this.center.applyMatrix4( matrix );
		this.radius = this.radius * matrix.getMaxScaleOnAxis();

		return this;

	}

	/**
	 * Translates the sphere's center by the given offset.
	 *
	 * @param {Vector3} offset - The offset.
	 * @return {Sphere} A reference to this sphere.
	 */
	translate( offset ) {

		this.center.add( offset );

		return this;

	}

	/**
	 * Expands the boundaries of this sphere to include the given point.
	 *
	 * @param {Vector3} point - The point to include.
	 * @return {Sphere} A reference to this sphere.
	 */
	expandByPoint( point ) {

		if ( this.isEmpty() ) {

			this.center.copy( point );

			this.radius = 0;

			return this;

		}

		_v1.subVectors( point, this.center );

		const lengthSq = _v1.lengthSq();

		if ( lengthSq > ( this.radius * this.radius ) ) {

			// calculate the minimal sphere

			const length = Math.sqrt( lengthSq );

			const delta = ( length - this.radius ) * 0.5;

			this.center.addScaledVector( _v1, delta / length );

			this.radius += delta;

		}

		return this;

	}

	/**
	 * Expands this sphere to enclose both the original sphere and the given sphere.
	 *
	 * @param {Sphere} sphere - The sphere to include.
	 * @return {Sphere} A reference to this sphere.
	 */
	union( sphere ) {

		if ( sphere.isEmpty() ) {

			return this;

		}

		if ( this.isEmpty() ) {

			this.copy( sphere );

			return this;

		}

		if ( this.center.equals( sphere.center ) === true ) {

			 this.radius = Math.max( this.radius, sphere.radius );

		} else {

			_v2.subVectors( sphere.center, this.center ).setLength( sphere.radius );

			this.expandByPoint( _v1.copy( sphere.center ).add( _v2 ) );

			this.expandByPoint( _v1.copy( sphere.center ).sub( _v2 ) );

		}

		return this;

	}

	/**
	 * Returns `true` if this sphere is equal with the given one.
	 *
	 * @param {Sphere} sphere - The sphere to test for equality.
	 * @return {boolean} Whether this bounding sphere is equal with the given one.
	 */
	equals( sphere ) {

		return sphere.center.equals( this.center ) && ( sphere.radius === this.radius );

	}

	/**
	 * Returns a new sphere with copied values from this instance.
	 *
	 * @return {Sphere} A clone of this instance.
	 */
	clone() {

		return new this.constructor().copy( this );

	}

	/**
	 * Returns a serialized structure of the bounding sphere.
	 *
	 * @return {Object} Serialized structure with fields representing the object state.
	 */
	toJSON() {

		return {
			radius: this.radius,
			center: this.center.toArray()
		};

	}

	/**
	 * Returns a serialized structure of the bounding sphere.
	 *
	 * @param {Object} json - The serialized json to set the sphere from.
	 * @return {Box3} A reference to this bounding sphere.
	 */
	fromJSON( json ) {

		this.radius = json.radius;
		this.center.fromArray( json.center );
		return this;

	}

}
```
</details>

#### Methods

##### `set(center: Vector3, radius: number): Sphere`

<details><summary>Code</summary>

```ts
set( center, radius ) {

		this.center.copy( center );
		this.radius = radius;

		return this;

	}
```
</details>

##### `setFromPoints(points: Vector3[], optionalCenter: Vector3): Sphere`

<details><summary>Code</summary>

```ts
setFromPoints( points, optionalCenter ) {

		const center = this.center;

		if ( optionalCenter !== undefined ) {

			center.copy( optionalCenter );

		} else {

			_box.setFromPoints( points ).getCenter( center );

		}

		let maxRadiusSq = 0;

		for ( let i = 0, il = points.length; i < il; i ++ ) {

			maxRadiusSq = Math.max( maxRadiusSq, center.distanceToSquared( points[ i ] ) );

		}

		this.radius = Math.sqrt( maxRadiusSq );

		return this;

	}
```
</details>

##### `copy(sphere: Sphere): Sphere`

<details><summary>Code</summary>

```ts
copy( sphere ) {

		this.center.copy( sphere.center );
		this.radius = sphere.radius;

		return this;

	}
```
</details>

##### `isEmpty(): boolean`

<details><summary>Code</summary>

```ts
isEmpty() {

		return ( this.radius < 0 );

	}
```
</details>

##### `makeEmpty(): Sphere`

<details><summary>Code</summary>

```ts
makeEmpty() {

		this.center.set( 0, 0, 0 );
		this.radius = - 1;

		return this;

	}
```
</details>

##### `containsPoint(point: Vector3): boolean`

<details><summary>Code</summary>

```ts
containsPoint( point ) {

		return ( point.distanceToSquared( this.center ) <= ( this.radius * this.radius ) );

	}
```
</details>

##### `distanceToPoint(point: Vector3): number`

<details><summary>Code</summary>

```ts
distanceToPoint( point ) {

		return ( point.distanceTo( this.center ) - this.radius );

	}
```
</details>

##### `intersectsSphere(sphere: Sphere): boolean`

<details><summary>Code</summary>

```ts
intersectsSphere( sphere ) {

		const radiusSum = this.radius + sphere.radius;

		return sphere.center.distanceToSquared( this.center ) <= ( radiusSum * radiusSum );

	}
```
</details>

##### `intersectsBox(box: Box3): boolean`

<details><summary>Code</summary>

```ts
intersectsBox( box ) {

		return box.intersectsSphere( this );

	}
```
</details>

##### `intersectsPlane(plane: Plane): boolean`

<details><summary>Code</summary>

```ts
intersectsPlane( plane ) {

		return Math.abs( plane.distanceToPoint( this.center ) ) <= this.radius;

	}
```
</details>

##### `clampPoint(point: Vector3, target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
clampPoint( point, target ) {

		const deltaLengthSq = this.center.distanceToSquared( point );

		target.copy( point );

		if ( deltaLengthSq > ( this.radius * this.radius ) ) {

			target.sub( this.center ).normalize();
			target.multiplyScalar( this.radius ).add( this.center );

		}

		return target;

	}
```
</details>

##### `getBoundingBox(target: Box3): Box3`

<details><summary>Code</summary>

```ts
getBoundingBox( target ) {

		if ( this.isEmpty() ) {

			// Empty sphere produces empty bounding box
			target.makeEmpty();
			return target;

		}

		target.set( this.center, this.center );
		target.expandByScalar( this.radius );

		return target;

	}
```
</details>

##### `applyMatrix4(matrix: Matrix4): Sphere`

<details><summary>Code</summary>

```ts
applyMatrix4( matrix ) {

		this.center.applyMatrix4( matrix );
		this.radius = this.radius * matrix.getMaxScaleOnAxis();

		return this;

	}
```
</details>

##### `translate(offset: Vector3): Sphere`

<details><summary>Code</summary>

```ts
translate( offset ) {

		this.center.add( offset );

		return this;

	}
```
</details>

##### `expandByPoint(point: Vector3): Sphere`

<details><summary>Code</summary>

```ts
expandByPoint( point ) {

		if ( this.isEmpty() ) {

			this.center.copy( point );

			this.radius = 0;

			return this;

		}

		_v1.subVectors( point, this.center );

		const lengthSq = _v1.lengthSq();

		if ( lengthSq > ( this.radius * this.radius ) ) {

			// calculate the minimal sphere

			const length = Math.sqrt( lengthSq );

			const delta = ( length - this.radius ) * 0.5;

			this.center.addScaledVector( _v1, delta / length );

			this.radius += delta;

		}

		return this;

	}
```
</details>

##### `union(sphere: Sphere): Sphere`

<details><summary>Code</summary>

```ts
union( sphere ) {

		if ( sphere.isEmpty() ) {

			return this;

		}

		if ( this.isEmpty() ) {

			this.copy( sphere );

			return this;

		}

		if ( this.center.equals( sphere.center ) === true ) {

			 this.radius = Math.max( this.radius, sphere.radius );

		} else {

			_v2.subVectors( sphere.center, this.center ).setLength( sphere.radius );

			this.expandByPoint( _v1.copy( sphere.center ).add( _v2 ) );

			this.expandByPoint( _v1.copy( sphere.center ).sub( _v2 ) );

		}

		return this;

	}
```
</details>

##### `equals(sphere: Sphere): boolean`

<details><summary>Code</summary>

```ts
equals( sphere ) {

		return sphere.center.equals( this.center ) && ( sphere.radius === this.radius );

	}
```
</details>

##### `clone(): Sphere`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor().copy( this );

	}
```
</details>

##### `toJSON(): any`

<details><summary>Code</summary>

```ts
toJSON() {

		return {
			radius: this.radius,
			center: this.center.toArray()
		};

	}
```
</details>

##### `fromJSON(json: any): Box3`

<details><summary>Code</summary>

```ts
fromJSON( json ) {

		this.radius = json.radius;
		this.center.fromArray( json.center );
		return this;

	}
```
</details>


---