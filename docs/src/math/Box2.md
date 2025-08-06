[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Box2.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 22 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/Box2.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector2` | `./Vector2.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_vector` | `Vector2` | let/var | `new Vector2()` | ✗ |


---

## Functions

### `Box2.set(min: Vector2, max: Vector2): Box2`

**JSDoc:**
```typescript
/**
	 * Sets the lower and upper boundaries of this box.
	 * Please note that this method only copies the values from the given objects.
	 *
	 * @param {Vector2} min - The lower boundary of the box.
	 * @param {Vector2} max - The upper boundary of the box.
	 * @return {Box2} A reference to this bounding box.
	 */
```

**Parameters:**

- **`min`** `Vector2`
- **`max`** `Vector2`

**Returns:** `Box2`

**Calls:**

- `this.min.copy`
- `this.max.copy`

<details><summary>Code</summary>

```typescript
set( min, max ) {

		this.min.copy( min );
		this.max.copy( max );

		return this;

	}
```
</details>

### `Box2.setFromPoints(points: Vector2[]): Box2`

**JSDoc:**
```typescript
/**
	 * Sets the upper and lower bounds of this box so it encloses the position data
	 * in the given array.
	 *
	 * @param {Array<Vector2>} points - An array holding 2D position data as instances of {@link Vector2}.
	 * @return {Box2} A reference to this bounding box.
	 */
```

**Parameters:**

- **`points`** `Vector2[]`

**Returns:** `Box2`

**Calls:**

- `this.makeEmpty`
- `this.expandByPoint`

<details><summary>Code</summary>

```typescript
setFromPoints( points ) {

		this.makeEmpty();

		for ( let i = 0, il = points.length; i < il; i ++ ) {

			this.expandByPoint( points[ i ] );

		}

		return this;

	}
```
</details>

### `Box2.setFromCenterAndSize(center: Vector2, size: Vector2): Box2`

**JSDoc:**
```typescript
/**
	 * Centers this box on the given center vector and sets this box's width, height and
	 * depth to the given size values.
	 *
	 * @param {Vector2} center - The center of the box.
	 * @param {Vector2} size - The x and y dimensions of the box.
	 * @return {Box2} A reference to this bounding box.
	 */
```

**Parameters:**

- **`center`** `Vector2`
- **`size`** `Vector2`

**Returns:** `Box2`

**Calls:**

- `_vector.copy( size ).multiplyScalar`
- `this.min.copy( center ).sub`
- `this.max.copy( center ).add`

<details><summary>Code</summary>

```typescript
setFromCenterAndSize( center, size ) {

		const halfSize = _vector.copy( size ).multiplyScalar( 0.5 );
		this.min.copy( center ).sub( halfSize );
		this.max.copy( center ).add( halfSize );

		return this;

	}
```
</details>

### `Box2.clone(): Box2`

**JSDoc:**
```typescript
/**
	 * Returns a new box with copied values from this instance.
	 *
	 * @return {Box2} A clone of this instance.
	 */
```

**Returns:** `Box2`

**Calls:**

- `new this.constructor().copy`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor().copy( this );

	}
```
</details>

### `Box2.copy(box: Box2): Box2`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given box to this instance.
	 *
	 * @param {Box2} box - The box to copy.
	 * @return {Box2} A reference to this bounding box.
	 */
```

**Parameters:**

- **`box`** `Box2`

**Returns:** `Box2`

**Calls:**

- `this.min.copy`
- `this.max.copy`

<details><summary>Code</summary>

```typescript
copy( box ) {

		this.min.copy( box.min );
		this.max.copy( box.max );

		return this;

	}
```
</details>

### `Box2.makeEmpty(): Box2`

**JSDoc:**
```typescript
/**
	 * Makes this box empty which means in encloses a zero space in 2D.
	 *
	 * @return {Box2} A reference to this bounding box.
	 */
```

**Returns:** `Box2`

<details><summary>Code</summary>

```typescript
makeEmpty() {

		this.min.x = this.min.y = + Infinity;
		this.max.x = this.max.y = - Infinity;

		return this;

	}
```
</details>

### `Box2.isEmpty(): boolean`

**JSDoc:**
```typescript
/**
	 * Returns true if this box includes zero points within its bounds.
	 * Note that a box with equal lower and upper bounds still includes one
	 * point, the one both bounds share.
	 *
	 * @return {boolean} Whether this box is empty or not.
	 */
```

**Returns:** `boolean`

**Internal Comments:**
```
// this is a more robust check for empty than ( volume <= 0 ) because volume can get positive with two negative axes
```

<details><summary>Code</summary>

```typescript
isEmpty() {

		// this is a more robust check for empty than ( volume <= 0 ) because volume can get positive with two negative axes

		return ( this.max.x < this.min.x ) || ( this.max.y < this.min.y );

	}
```
</details>

### `Box2.getCenter(target: Vector2): Vector2`

**JSDoc:**
```typescript
/**
	 * Returns the center point of this box.
	 *
	 * @param {Vector2} target - The target vector that is used to store the method's result.
	 * @return {Vector2} The center point.
	 */
```

**Parameters:**

- **`target`** `Vector2`

**Returns:** `Vector2`

**Calls:**

- `this.isEmpty`
- `target.set`
- `target.addVectors( this.min, this.max ).multiplyScalar`

<details><summary>Code</summary>

```typescript
getCenter( target ) {

		return this.isEmpty() ? target.set( 0, 0 ) : target.addVectors( this.min, this.max ).multiplyScalar( 0.5 );

	}
```
</details>

### `Box2.getSize(target: Vector2): Vector2`

**JSDoc:**
```typescript
/**
	 * Returns the dimensions of this box.
	 *
	 * @param {Vector2} target - The target vector that is used to store the method's result.
	 * @return {Vector2} The size.
	 */
```

**Parameters:**

- **`target`** `Vector2`

**Returns:** `Vector2`

**Calls:**

- `this.isEmpty`
- `target.set`
- `target.subVectors`

<details><summary>Code</summary>

```typescript
getSize( target ) {

		return this.isEmpty() ? target.set( 0, 0 ) : target.subVectors( this.max, this.min );

	}
```
</details>

### `Box2.expandByPoint(point: Vector2): Box2`

**JSDoc:**
```typescript
/**
	 * Expands the boundaries of this box to include the given point.
	 *
	 * @param {Vector2} point - The point that should be included by the bounding box.
	 * @return {Box2} A reference to this bounding box.
	 */
```

**Parameters:**

- **`point`** `Vector2`

**Returns:** `Box2`

**Calls:**

- `this.min.min`
- `this.max.max`

<details><summary>Code</summary>

```typescript
expandByPoint( point ) {

		this.min.min( point );
		this.max.max( point );

		return this;

	}
```
</details>

### `Box2.expandByVector(vector: Vector2): Box2`

**JSDoc:**
```typescript
/**
	 * Expands this box equilaterally by the given vector. The width of this
	 * box will be expanded by the x component of the vector in both
	 * directions. The height of this box will be expanded by the y component of
	 * the vector in both directions.
	 *
	 * @param {Vector2} vector - The vector that should expand the bounding box.
	 * @return {Box2} A reference to this bounding box.
	 */
```

**Parameters:**

- **`vector`** `Vector2`

**Returns:** `Box2`

**Calls:**

- `this.min.sub`
- `this.max.add`

<details><summary>Code</summary>

```typescript
expandByVector( vector ) {

		this.min.sub( vector );
		this.max.add( vector );

		return this;

	}
```
</details>

### `Box2.expandByScalar(scalar: number): Box2`

**JSDoc:**
```typescript
/**
	 * Expands each dimension of the box by the given scalar. If negative, the
	 * dimensions of the box will be contracted.
	 *
	 * @param {number} scalar - The scalar value that should expand the bounding box.
	 * @return {Box2} A reference to this bounding box.
	 */
```

**Parameters:**

- **`scalar`** `number`

**Returns:** `Box2`

**Calls:**

- `this.min.addScalar`
- `this.max.addScalar`

<details><summary>Code</summary>

```typescript
expandByScalar( scalar ) {

		this.min.addScalar( - scalar );
		this.max.addScalar( scalar );

		return this;

	}
```
</details>

### `Box2.containsPoint(point: Vector2): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given point lies within or on the boundaries of this box.
	 *
	 * @param {Vector2} point - The point to test.
	 * @return {boolean} Whether the bounding box contains the given point or not.
	 */
```

**Parameters:**

- **`point`** `Vector2`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
containsPoint( point ) {

		return point.x >= this.min.x && point.x <= this.max.x &&
			point.y >= this.min.y && point.y <= this.max.y;

	}
```
</details>

### `Box2.containsBox(box: Box2): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this bounding box includes the entirety of the given bounding box.
	 * If this box and the given one are identical, this function also returns `true`.
	 *
	 * @param {Box2} box - The bounding box to test.
	 * @return {boolean} Whether the bounding box contains the given bounding box or not.
	 */
```

**Parameters:**

- **`box`** `Box2`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
containsBox( box ) {

		return this.min.x <= box.min.x && box.max.x <= this.max.x &&
			this.min.y <= box.min.y && box.max.y <= this.max.y;

	}
```
</details>

### `Box2.getParameter(point: Vector2, target: Vector2): Vector2`

**JSDoc:**
```typescript
/**
	 * Returns a point as a proportion of this box's width and height.
	 *
	 * @param {Vector2} point - A point in 2D space.
	 * @param {Vector2} target - The target vector that is used to store the method's result.
	 * @return {Vector2} A point as a proportion of this box's width and height.
	 */
```

**Parameters:**

- **`point`** `Vector2`
- **`target`** `Vector2`

**Returns:** `Vector2`

**Calls:**

- `target.set`

**Internal Comments:**
```
// This can potentially have a divide by zero if the box
// has a size dimension of 0.
```

<details><summary>Code</summary>

```typescript
getParameter( point, target ) {

		// This can potentially have a divide by zero if the box
		// has a size dimension of 0.

		return target.set(
			( point.x - this.min.x ) / ( this.max.x - this.min.x ),
			( point.y - this.min.y ) / ( this.max.y - this.min.y )
		);

	}
```
</details>

### `Box2.intersectsBox(box: Box2): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given bounding box intersects with this bounding box.
	 *
	 * @param {Box2} box - The bounding box to test.
	 * @return {boolean} Whether the given bounding box intersects with this bounding box.
	 */
```

**Parameters:**

- **`box`** `Box2`

**Returns:** `boolean`

**Internal Comments:**
```
// using 4 splitting planes to rule out intersections
```

<details><summary>Code</summary>

```typescript
intersectsBox( box ) {

		// using 4 splitting planes to rule out intersections

		return box.max.x >= this.min.x && box.min.x <= this.max.x &&
			box.max.y >= this.min.y && box.min.y <= this.max.y;

	}
```
</details>

### `Box2.clampPoint(point: Vector2, target: Vector2): Vector2`

**JSDoc:**
```typescript
/**
	 * Clamps the given point within the bounds of this box.
	 *
	 * @param {Vector2} point - The point to clamp.
	 * @param {Vector2} target - The target vector that is used to store the method's result.
	 * @return {Vector2} The clamped point.
	 */
```

**Parameters:**

- **`point`** `Vector2`
- **`target`** `Vector2`

**Returns:** `Vector2`

**Calls:**

- `target.copy( point ).clamp`

<details><summary>Code</summary>

```typescript
clampPoint( point, target ) {

		return target.copy( point ).clamp( this.min, this.max );

	}
```
</details>

### `Box2.distanceToPoint(point: Vector2): number`

**JSDoc:**
```typescript
/**
	 * Returns the euclidean distance from any edge of this box to the specified point. If
	 * the given point lies inside of this box, the distance will be `0`.
	 *
	 * @param {Vector2} point - The point to compute the distance to.
	 * @return {number} The euclidean distance.
	 */
```

**Parameters:**

- **`point`** `Vector2`

**Returns:** `number`

**Calls:**

- `this.clampPoint( point, _vector ).distanceTo`

<details><summary>Code</summary>

```typescript
distanceToPoint( point ) {

		return this.clampPoint( point, _vector ).distanceTo( point );

	}
```
</details>

### `Box2.intersect(box: Box2): Box2`

**JSDoc:**
```typescript
/**
	 * Computes the intersection of this bounding box and the given one, setting the upper
	 * bound of this box to the lesser of the two boxes' upper bounds and the
	 * lower bound of this box to the greater of the two boxes' lower bounds. If
	 * there's no overlap, makes this box empty.
	 *
	 * @param {Box2} box - The bounding box to intersect with.
	 * @return {Box2} A reference to this bounding box.
	 */
```

**Parameters:**

- **`box`** `Box2`

**Returns:** `Box2`

**Calls:**

- `this.min.max`
- `this.max.min`
- `this.isEmpty`
- `this.makeEmpty`

<details><summary>Code</summary>

```typescript
intersect( box ) {

		this.min.max( box.min );
		this.max.min( box.max );

		if ( this.isEmpty() ) this.makeEmpty();

		return this;

	}
```
</details>

### `Box2.union(box: Box2): Box2`

**JSDoc:**
```typescript
/**
	 * Computes the union of this box and another and the given one, setting the upper
	 * bound of this box to the greater of the two boxes' upper bounds and the
	 * lower bound of this box to the lesser of the two boxes' lower bounds.
	 *
	 * @param {Box2} box - The bounding box that will be unioned with this instance.
	 * @return {Box2} A reference to this bounding box.
	 */
```

**Parameters:**

- **`box`** `Box2`

**Returns:** `Box2`

**Calls:**

- `this.min.min`
- `this.max.max`

<details><summary>Code</summary>

```typescript
union( box ) {

		this.min.min( box.min );
		this.max.max( box.max );

		return this;

	}
```
</details>

### `Box2.translate(offset: Vector2): Box2`

**JSDoc:**
```typescript
/**
	 * Adds the given offset to both the upper and lower bounds of this bounding box,
	 * effectively moving it in 2D space.
	 *
	 * @param {Vector2} offset - The offset that should be used to translate the bounding box.
	 * @return {Box2} A reference to this bounding box.
	 */
```

**Parameters:**

- **`offset`** `Vector2`

**Returns:** `Box2`

**Calls:**

- `this.min.add`
- `this.max.add`

<details><summary>Code</summary>

```typescript
translate( offset ) {

		this.min.add( offset );
		this.max.add( offset );

		return this;

	}
```
</details>

### `Box2.equals(box: Box2): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this bounding box is equal with the given one.
	 *
	 * @param {Box2} box - The box to test for equality.
	 * @return {boolean} Whether this bounding box is equal with the given one.
	 */
```

**Parameters:**

- **`box`** `Box2`

**Returns:** `boolean`

**Calls:**

- `box.min.equals`
- `box.max.equals`

<details><summary>Code</summary>

```typescript
equals( box ) {

		return box.min.equals( this.min ) && box.max.equals( this.max );

	}
```
</details>


---

## Classes

### `Box2`

<details><summary>Class Code</summary>

```ts
class Box2 {

	/**
	 * Constructs a new bounding box.
	 *
	 * @param {Vector2} [min=(Infinity,Infinity)] - A vector representing the lower boundary of the box.
	 * @param {Vector2} [max=(-Infinity,-Infinity)] - A vector representing the upper boundary of the box.
	 */
	constructor( min = new Vector2( + Infinity, + Infinity ), max = new Vector2( - Infinity, - Infinity ) ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isBox2 = true;

		/**
		 * The lower boundary of the box.
		 *
		 * @type {Vector2}
		 */
		this.min = min;

		/**
		 * The upper boundary of the box.
		 *
		 * @type {Vector2}
		 */
		this.max = max;

	}

	/**
	 * Sets the lower and upper boundaries of this box.
	 * Please note that this method only copies the values from the given objects.
	 *
	 * @param {Vector2} min - The lower boundary of the box.
	 * @param {Vector2} max - The upper boundary of the box.
	 * @return {Box2} A reference to this bounding box.
	 */
	set( min, max ) {

		this.min.copy( min );
		this.max.copy( max );

		return this;

	}

	/**
	 * Sets the upper and lower bounds of this box so it encloses the position data
	 * in the given array.
	 *
	 * @param {Array<Vector2>} points - An array holding 2D position data as instances of {@link Vector2}.
	 * @return {Box2} A reference to this bounding box.
	 */
	setFromPoints( points ) {

		this.makeEmpty();

		for ( let i = 0, il = points.length; i < il; i ++ ) {

			this.expandByPoint( points[ i ] );

		}

		return this;

	}

	/**
	 * Centers this box on the given center vector and sets this box's width, height and
	 * depth to the given size values.
	 *
	 * @param {Vector2} center - The center of the box.
	 * @param {Vector2} size - The x and y dimensions of the box.
	 * @return {Box2} A reference to this bounding box.
	 */
	setFromCenterAndSize( center, size ) {

		const halfSize = _vector.copy( size ).multiplyScalar( 0.5 );
		this.min.copy( center ).sub( halfSize );
		this.max.copy( center ).add( halfSize );

		return this;

	}

	/**
	 * Returns a new box with copied values from this instance.
	 *
	 * @return {Box2} A clone of this instance.
	 */
	clone() {

		return new this.constructor().copy( this );

	}

	/**
	 * Copies the values of the given box to this instance.
	 *
	 * @param {Box2} box - The box to copy.
	 * @return {Box2} A reference to this bounding box.
	 */
	copy( box ) {

		this.min.copy( box.min );
		this.max.copy( box.max );

		return this;

	}

	/**
	 * Makes this box empty which means in encloses a zero space in 2D.
	 *
	 * @return {Box2} A reference to this bounding box.
	 */
	makeEmpty() {

		this.min.x = this.min.y = + Infinity;
		this.max.x = this.max.y = - Infinity;

		return this;

	}

	/**
	 * Returns true if this box includes zero points within its bounds.
	 * Note that a box with equal lower and upper bounds still includes one
	 * point, the one both bounds share.
	 *
	 * @return {boolean} Whether this box is empty or not.
	 */
	isEmpty() {

		// this is a more robust check for empty than ( volume <= 0 ) because volume can get positive with two negative axes

		return ( this.max.x < this.min.x ) || ( this.max.y < this.min.y );

	}

	/**
	 * Returns the center point of this box.
	 *
	 * @param {Vector2} target - The target vector that is used to store the method's result.
	 * @return {Vector2} The center point.
	 */
	getCenter( target ) {

		return this.isEmpty() ? target.set( 0, 0 ) : target.addVectors( this.min, this.max ).multiplyScalar( 0.5 );

	}

	/**
	 * Returns the dimensions of this box.
	 *
	 * @param {Vector2} target - The target vector that is used to store the method's result.
	 * @return {Vector2} The size.
	 */
	getSize( target ) {

		return this.isEmpty() ? target.set( 0, 0 ) : target.subVectors( this.max, this.min );

	}

	/**
	 * Expands the boundaries of this box to include the given point.
	 *
	 * @param {Vector2} point - The point that should be included by the bounding box.
	 * @return {Box2} A reference to this bounding box.
	 */
	expandByPoint( point ) {

		this.min.min( point );
		this.max.max( point );

		return this;

	}

	/**
	 * Expands this box equilaterally by the given vector. The width of this
	 * box will be expanded by the x component of the vector in both
	 * directions. The height of this box will be expanded by the y component of
	 * the vector in both directions.
	 *
	 * @param {Vector2} vector - The vector that should expand the bounding box.
	 * @return {Box2} A reference to this bounding box.
	 */
	expandByVector( vector ) {

		this.min.sub( vector );
		this.max.add( vector );

		return this;

	}

	/**
	 * Expands each dimension of the box by the given scalar. If negative, the
	 * dimensions of the box will be contracted.
	 *
	 * @param {number} scalar - The scalar value that should expand the bounding box.
	 * @return {Box2} A reference to this bounding box.
	 */
	expandByScalar( scalar ) {

		this.min.addScalar( - scalar );
		this.max.addScalar( scalar );

		return this;

	}

	/**
	 * Returns `true` if the given point lies within or on the boundaries of this box.
	 *
	 * @param {Vector2} point - The point to test.
	 * @return {boolean} Whether the bounding box contains the given point or not.
	 */
	containsPoint( point ) {

		return point.x >= this.min.x && point.x <= this.max.x &&
			point.y >= this.min.y && point.y <= this.max.y;

	}

	/**
	 * Returns `true` if this bounding box includes the entirety of the given bounding box.
	 * If this box and the given one are identical, this function also returns `true`.
	 *
	 * @param {Box2} box - The bounding box to test.
	 * @return {boolean} Whether the bounding box contains the given bounding box or not.
	 */
	containsBox( box ) {

		return this.min.x <= box.min.x && box.max.x <= this.max.x &&
			this.min.y <= box.min.y && box.max.y <= this.max.y;

	}

	/**
	 * Returns a point as a proportion of this box's width and height.
	 *
	 * @param {Vector2} point - A point in 2D space.
	 * @param {Vector2} target - The target vector that is used to store the method's result.
	 * @return {Vector2} A point as a proportion of this box's width and height.
	 */
	getParameter( point, target ) {

		// This can potentially have a divide by zero if the box
		// has a size dimension of 0.

		return target.set(
			( point.x - this.min.x ) / ( this.max.x - this.min.x ),
			( point.y - this.min.y ) / ( this.max.y - this.min.y )
		);

	}

	/**
	 * Returns `true` if the given bounding box intersects with this bounding box.
	 *
	 * @param {Box2} box - The bounding box to test.
	 * @return {boolean} Whether the given bounding box intersects with this bounding box.
	 */
	intersectsBox( box ) {

		// using 4 splitting planes to rule out intersections

		return box.max.x >= this.min.x && box.min.x <= this.max.x &&
			box.max.y >= this.min.y && box.min.y <= this.max.y;

	}

	/**
	 * Clamps the given point within the bounds of this box.
	 *
	 * @param {Vector2} point - The point to clamp.
	 * @param {Vector2} target - The target vector that is used to store the method's result.
	 * @return {Vector2} The clamped point.
	 */
	clampPoint( point, target ) {

		return target.copy( point ).clamp( this.min, this.max );

	}

	/**
	 * Returns the euclidean distance from any edge of this box to the specified point. If
	 * the given point lies inside of this box, the distance will be `0`.
	 *
	 * @param {Vector2} point - The point to compute the distance to.
	 * @return {number} The euclidean distance.
	 */
	distanceToPoint( point ) {

		return this.clampPoint( point, _vector ).distanceTo( point );

	}

	/**
	 * Computes the intersection of this bounding box and the given one, setting the upper
	 * bound of this box to the lesser of the two boxes' upper bounds and the
	 * lower bound of this box to the greater of the two boxes' lower bounds. If
	 * there's no overlap, makes this box empty.
	 *
	 * @param {Box2} box - The bounding box to intersect with.
	 * @return {Box2} A reference to this bounding box.
	 */
	intersect( box ) {

		this.min.max( box.min );
		this.max.min( box.max );

		if ( this.isEmpty() ) this.makeEmpty();

		return this;

	}

	/**
	 * Computes the union of this box and another and the given one, setting the upper
	 * bound of this box to the greater of the two boxes' upper bounds and the
	 * lower bound of this box to the lesser of the two boxes' lower bounds.
	 *
	 * @param {Box2} box - The bounding box that will be unioned with this instance.
	 * @return {Box2} A reference to this bounding box.
	 */
	union( box ) {

		this.min.min( box.min );
		this.max.max( box.max );

		return this;

	}

	/**
	 * Adds the given offset to both the upper and lower bounds of this bounding box,
	 * effectively moving it in 2D space.
	 *
	 * @param {Vector2} offset - The offset that should be used to translate the bounding box.
	 * @return {Box2} A reference to this bounding box.
	 */
	translate( offset ) {

		this.min.add( offset );
		this.max.add( offset );

		return this;

	}

	/**
	 * Returns `true` if this bounding box is equal with the given one.
	 *
	 * @param {Box2} box - The box to test for equality.
	 * @return {boolean} Whether this bounding box is equal with the given one.
	 */
	equals( box ) {

		return box.min.equals( this.min ) && box.max.equals( this.max );

	}

}
```
</details>

#### Methods

##### `set(min: Vector2, max: Vector2): Box2`

<details><summary>Code</summary>

```ts
set( min, max ) {

		this.min.copy( min );
		this.max.copy( max );

		return this;

	}
```
</details>

##### `setFromPoints(points: Vector2[]): Box2`

<details><summary>Code</summary>

```ts
setFromPoints( points ) {

		this.makeEmpty();

		for ( let i = 0, il = points.length; i < il; i ++ ) {

			this.expandByPoint( points[ i ] );

		}

		return this;

	}
```
</details>

##### `setFromCenterAndSize(center: Vector2, size: Vector2): Box2`

<details><summary>Code</summary>

```ts
setFromCenterAndSize( center, size ) {

		const halfSize = _vector.copy( size ).multiplyScalar( 0.5 );
		this.min.copy( center ).sub( halfSize );
		this.max.copy( center ).add( halfSize );

		return this;

	}
```
</details>

##### `clone(): Box2`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor().copy( this );

	}
```
</details>

##### `copy(box: Box2): Box2`

<details><summary>Code</summary>

```ts
copy( box ) {

		this.min.copy( box.min );
		this.max.copy( box.max );

		return this;

	}
```
</details>

##### `makeEmpty(): Box2`

<details><summary>Code</summary>

```ts
makeEmpty() {

		this.min.x = this.min.y = + Infinity;
		this.max.x = this.max.y = - Infinity;

		return this;

	}
```
</details>

##### `isEmpty(): boolean`

<details><summary>Code</summary>

```ts
isEmpty() {

		// this is a more robust check for empty than ( volume <= 0 ) because volume can get positive with two negative axes

		return ( this.max.x < this.min.x ) || ( this.max.y < this.min.y );

	}
```
</details>

##### `getCenter(target: Vector2): Vector2`

<details><summary>Code</summary>

```ts
getCenter( target ) {

		return this.isEmpty() ? target.set( 0, 0 ) : target.addVectors( this.min, this.max ).multiplyScalar( 0.5 );

	}
```
</details>

##### `getSize(target: Vector2): Vector2`

<details><summary>Code</summary>

```ts
getSize( target ) {

		return this.isEmpty() ? target.set( 0, 0 ) : target.subVectors( this.max, this.min );

	}
```
</details>

##### `expandByPoint(point: Vector2): Box2`

<details><summary>Code</summary>

```ts
expandByPoint( point ) {

		this.min.min( point );
		this.max.max( point );

		return this;

	}
```
</details>

##### `expandByVector(vector: Vector2): Box2`

<details><summary>Code</summary>

```ts
expandByVector( vector ) {

		this.min.sub( vector );
		this.max.add( vector );

		return this;

	}
```
</details>

##### `expandByScalar(scalar: number): Box2`

<details><summary>Code</summary>

```ts
expandByScalar( scalar ) {

		this.min.addScalar( - scalar );
		this.max.addScalar( scalar );

		return this;

	}
```
</details>

##### `containsPoint(point: Vector2): boolean`

<details><summary>Code</summary>

```ts
containsPoint( point ) {

		return point.x >= this.min.x && point.x <= this.max.x &&
			point.y >= this.min.y && point.y <= this.max.y;

	}
```
</details>

##### `containsBox(box: Box2): boolean`

<details><summary>Code</summary>

```ts
containsBox( box ) {

		return this.min.x <= box.min.x && box.max.x <= this.max.x &&
			this.min.y <= box.min.y && box.max.y <= this.max.y;

	}
```
</details>

##### `getParameter(point: Vector2, target: Vector2): Vector2`

<details><summary>Code</summary>

```ts
getParameter( point, target ) {

		// This can potentially have a divide by zero if the box
		// has a size dimension of 0.

		return target.set(
			( point.x - this.min.x ) / ( this.max.x - this.min.x ),
			( point.y - this.min.y ) / ( this.max.y - this.min.y )
		);

	}
```
</details>

##### `intersectsBox(box: Box2): boolean`

<details><summary>Code</summary>

```ts
intersectsBox( box ) {

		// using 4 splitting planes to rule out intersections

		return box.max.x >= this.min.x && box.min.x <= this.max.x &&
			box.max.y >= this.min.y && box.min.y <= this.max.y;

	}
```
</details>

##### `clampPoint(point: Vector2, target: Vector2): Vector2`

<details><summary>Code</summary>

```ts
clampPoint( point, target ) {

		return target.copy( point ).clamp( this.min, this.max );

	}
```
</details>

##### `distanceToPoint(point: Vector2): number`

<details><summary>Code</summary>

```ts
distanceToPoint( point ) {

		return this.clampPoint( point, _vector ).distanceTo( point );

	}
```
</details>

##### `intersect(box: Box2): Box2`

<details><summary>Code</summary>

```ts
intersect( box ) {

		this.min.max( box.min );
		this.max.min( box.max );

		if ( this.isEmpty() ) this.makeEmpty();

		return this;

	}
```
</details>

##### `union(box: Box2): Box2`

<details><summary>Code</summary>

```ts
union( box ) {

		this.min.min( box.min );
		this.max.max( box.max );

		return this;

	}
```
</details>

##### `translate(offset: Vector2): Box2`

<details><summary>Code</summary>

```ts
translate( offset ) {

		this.min.add( offset );
		this.max.add( offset );

		return this;

	}
```
</details>

##### `equals(box: Box2): boolean`

<details><summary>Code</summary>

```ts
equals( box ) {

		return box.min.equals( this.min ) && box.max.equals( this.max );

	}
```
</details>


---