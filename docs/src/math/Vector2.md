[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Vector2.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 51 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/Vector2.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `clamp` | `./MathUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `x` | `number` | let/var | `this.x` | ✗ |
| `y` | `number` | let/var | `this.y` | ✗ |
| `e` | `any` | let/var | `m.elements` | ✗ |
| `angle` | `number` | let/var | `Math.atan2( - this.y, - this.x ) + Math.PI` | ✗ |
| `theta` | `number` | let/var | `this.dot( v ) / denominator` | ✗ |
| `dx` | `number` | let/var | `this.x - v.x` | ✗ |
| `dy` | `number` | let/var | `this.y - v.y` | ✗ |
| `x` | `number` | let/var | `this.x - center.x` | ✗ |
| `y` | `number` | let/var | `this.y - center.y` | ✗ |


---

## Functions

### `Vector2.set(x: number, y: number): Vector2`

**JSDoc:**
```typescript
/**
	 * Sets the vector components.
	 *
	 * @param {number} x - The value of the x component.
	 * @param {number} y - The value of the y component.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
set( x, y ) {

		this.x = x;
		this.y = y;

		return this;

	}
```
</details>

### `Vector2.setScalar(scalar: number): Vector2`

**JSDoc:**
```typescript
/**
	 * Sets the vector components to the same value.
	 *
	 * @param {number} scalar - The value to set for all vector components.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`scalar`** `number`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
setScalar( scalar ) {

		this.x = scalar;
		this.y = scalar;

		return this;

	}
```
</details>

### `Vector2.setX(x: number): Vector2`

**JSDoc:**
```typescript
/**
	 * Sets the vector's x component to the given value
	 *
	 * @param {number} x - The value to set.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`x`** `number`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
setX( x ) {

		this.x = x;

		return this;

	}
```
</details>

### `Vector2.setY(y: number): Vector2`

**JSDoc:**
```typescript
/**
	 * Sets the vector's y component to the given value
	 *
	 * @param {number} y - The value to set.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`y`** `number`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
setY( y ) {

		this.y = y;

		return this;

	}
```
</details>

### `Vector2.setComponent(index: number, value: number): Vector2`

**JSDoc:**
```typescript
/**
	 * Allows to set a vector component with an index.
	 *
	 * @param {number} index - The component index. `0` equals to x, `1` equals to y.
	 * @param {number} value - The value to set.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`index`** `number`
- **`value`** `number`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
setComponent( index, value ) {

		switch ( index ) {

			case 0: this.x = value; break;
			case 1: this.y = value; break;
			default: throw new Error( 'index is out of range: ' + index );

		}

		return this;

	}
```
</details>

### `Vector2.getComponent(index: number): number`

**JSDoc:**
```typescript
/**
	 * Returns the value of the vector component which matches the given index.
	 *
	 * @param {number} index - The component index. `0` equals to x, `1` equals to y.
	 * @return {number} A vector component value.
	 */
```

**Parameters:**

- **`index`** `number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getComponent( index ) {

		switch ( index ) {

			case 0: return this.x;
			case 1: return this.y;
			default: throw new Error( 'index is out of range: ' + index );

		}

	}
```
</details>

### `Vector2.clone(): Vector2`

**JSDoc:**
```typescript
/**
	 * Returns a new vector with copied values from this instance.
	 *
	 * @return {Vector2} A clone of this instance.
	 */
```

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor( this.x, this.y );

	}
```
</details>

### `Vector2.copy(v: Vector2): Vector2`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given vector to this instance.
	 *
	 * @param {Vector2} v - The vector to copy.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector2`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
copy( v ) {

		this.x = v.x;
		this.y = v.y;

		return this;

	}
```
</details>

### `Vector2.add(v: Vector2): Vector2`

**JSDoc:**
```typescript
/**
	 * Adds the given vector to this instance.
	 *
	 * @param {Vector2} v - The vector to add.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector2`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
add( v ) {

		this.x += v.x;
		this.y += v.y;

		return this;

	}
```
</details>

### `Vector2.addScalar(s: number): Vector2`

**JSDoc:**
```typescript
/**
	 * Adds the given scalar value to all components of this instance.
	 *
	 * @param {number} s - The scalar to add.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`s`** `number`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
addScalar( s ) {

		this.x += s;
		this.y += s;

		return this;

	}
```
</details>

### `Vector2.addVectors(a: Vector2, b: Vector2): Vector2`

**JSDoc:**
```typescript
/**
	 * Adds the given vectors and stores the result in this instance.
	 *
	 * @param {Vector2} a - The first vector.
	 * @param {Vector2} b - The second vector.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`a`** `Vector2`
- **`b`** `Vector2`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
addVectors( a, b ) {

		this.x = a.x + b.x;
		this.y = a.y + b.y;

		return this;

	}
```
</details>

### `Vector2.addScaledVector(v: Vector2, s: number): Vector2`

**JSDoc:**
```typescript
/**
	 * Adds the given vector scaled by the given factor to this instance.
	 *
	 * @param {Vector2} v - The vector.
	 * @param {number} s - The factor that scales `v`.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector2`
- **`s`** `number`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
addScaledVector( v, s ) {

		this.x += v.x * s;
		this.y += v.y * s;

		return this;

	}
```
</details>

### `Vector2.sub(v: Vector2): Vector2`

**JSDoc:**
```typescript
/**
	 * Subtracts the given vector from this instance.
	 *
	 * @param {Vector2} v - The vector to subtract.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector2`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
sub( v ) {

		this.x -= v.x;
		this.y -= v.y;

		return this;

	}
```
</details>

### `Vector2.subScalar(s: number): Vector2`

**JSDoc:**
```typescript
/**
	 * Subtracts the given scalar value from all components of this instance.
	 *
	 * @param {number} s - The scalar to subtract.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`s`** `number`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
subScalar( s ) {

		this.x -= s;
		this.y -= s;

		return this;

	}
```
</details>

### `Vector2.subVectors(a: Vector2, b: Vector2): Vector2`

**JSDoc:**
```typescript
/**
	 * Subtracts the given vectors and stores the result in this instance.
	 *
	 * @param {Vector2} a - The first vector.
	 * @param {Vector2} b - The second vector.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`a`** `Vector2`
- **`b`** `Vector2`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
subVectors( a, b ) {

		this.x = a.x - b.x;
		this.y = a.y - b.y;

		return this;

	}
```
</details>

### `Vector2.multiply(v: Vector2): Vector2`

**JSDoc:**
```typescript
/**
	 * Multiplies the given vector with this instance.
	 *
	 * @param {Vector2} v - The vector to multiply.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector2`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
multiply( v ) {

		this.x *= v.x;
		this.y *= v.y;

		return this;

	}
```
</details>

### `Vector2.multiplyScalar(scalar: number): Vector2`

**JSDoc:**
```typescript
/**
	 * Multiplies the given scalar value with all components of this instance.
	 *
	 * @param {number} scalar - The scalar to multiply.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`scalar`** `number`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
multiplyScalar( scalar ) {

		this.x *= scalar;
		this.y *= scalar;

		return this;

	}
```
</details>

### `Vector2.divide(v: Vector2): Vector2`

**JSDoc:**
```typescript
/**
	 * Divides this instance by the given vector.
	 *
	 * @param {Vector2} v - The vector to divide.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector2`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
divide( v ) {

		this.x /= v.x;
		this.y /= v.y;

		return this;

	}
```
</details>

### `Vector2.divideScalar(scalar: number): Vector2`

**JSDoc:**
```typescript
/**
	 * Divides this vector by the given scalar.
	 *
	 * @param {number} scalar - The scalar to divide.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`scalar`** `number`

**Returns:** `Vector2`

**Calls:**

- `this.multiplyScalar`

<details><summary>Code</summary>

```typescript
divideScalar( scalar ) {

		return this.multiplyScalar( 1 / scalar );

	}
```
</details>

### `Vector2.applyMatrix3(m: Matrix3): Vector2`

**JSDoc:**
```typescript
/**
	 * Multiplies this vector (with an implicit 1 as the 3rd component) by
	 * the given 3x3 matrix.
	 *
	 * @param {Matrix3} m - The matrix to apply.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`m`** `Matrix3`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
applyMatrix3( m ) {

		const x = this.x, y = this.y;
		const e = m.elements;

		this.x = e[ 0 ] * x + e[ 3 ] * y + e[ 6 ];
		this.y = e[ 1 ] * x + e[ 4 ] * y + e[ 7 ];

		return this;

	}
```
</details>

### `Vector2.min(v: Vector2): Vector2`

**JSDoc:**
```typescript
/**
	 * If this vector's x or y value is greater than the given vector's x or y
	 * value, replace that value with the corresponding min value.
	 *
	 * @param {Vector2} v - The vector.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector2`

**Returns:** `Vector2`

**Calls:**

- `Math.min`

<details><summary>Code</summary>

```typescript
min( v ) {

		this.x = Math.min( this.x, v.x );
		this.y = Math.min( this.y, v.y );

		return this;

	}
```
</details>

### `Vector2.max(v: Vector2): Vector2`

**JSDoc:**
```typescript
/**
	 * If this vector's x or y value is less than the given vector's x or y
	 * value, replace that value with the corresponding max value.
	 *
	 * @param {Vector2} v - The vector.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector2`

**Returns:** `Vector2`

**Calls:**

- `Math.max`

<details><summary>Code</summary>

```typescript
max( v ) {

		this.x = Math.max( this.x, v.x );
		this.y = Math.max( this.y, v.y );

		return this;

	}
```
</details>

### `Vector2.clamp(min: Vector2, max: Vector2): Vector2`

**JSDoc:**
```typescript
/**
	 * If this vector's x or y value is greater than the max vector's x or y
	 * value, it is replaced by the corresponding value.
	 * If this vector's x or y value is less than the min vector's x or y value,
	 * it is replaced by the corresponding value.
	 *
	 * @param {Vector2} min - The minimum x and y values.
	 * @param {Vector2} max - The maximum x and y values in the desired range.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`min`** `Vector2`
- **`max`** `Vector2`

**Returns:** `Vector2`

**Calls:**

- `clamp (from ./MathUtils.js)`

**Internal Comments:**
```
// assumes min < max, componentwise (x4)
```

<details><summary>Code</summary>

```typescript
clamp( min, max ) {

		// assumes min < max, componentwise

		this.x = clamp( this.x, min.x, max.x );
		this.y = clamp( this.y, min.y, max.y );

		return this;

	}
```
</details>

### `Vector2.clampScalar(minVal: number, maxVal: number): Vector2`

**JSDoc:**
```typescript
/**
	 * If this vector's x or y values are greater than the max value, they are
	 * replaced by the max value.
	 * If this vector's x or y values are less than the min value, they are
	 * replaced by the min value.
	 *
	 * @param {number} minVal - The minimum value the components will be clamped to.
	 * @param {number} maxVal - The maximum value the components will be clamped to.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`minVal`** `number`
- **`maxVal`** `number`

**Returns:** `Vector2`

**Calls:**

- `clamp (from ./MathUtils.js)`

<details><summary>Code</summary>

```typescript
clampScalar( minVal, maxVal ) {

		this.x = clamp( this.x, minVal, maxVal );
		this.y = clamp( this.y, minVal, maxVal );

		return this;

	}
```
</details>

### `Vector2.clampLength(min: number, max: number): Vector2`

**JSDoc:**
```typescript
/**
	 * If this vector's length is greater than the max value, it is replaced by
	 * the max value.
	 * If this vector's length is less than the min value, it is replaced by the
	 * min value.
	 *
	 * @param {number} min - The minimum value the vector length will be clamped to.
	 * @param {number} max - The maximum value the vector length will be clamped to.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`min`** `number`
- **`max`** `number`

**Returns:** `Vector2`

**Calls:**

- `this.length`
- `this.divideScalar( length || 1 ).multiplyScalar`
- `clamp (from ./MathUtils.js)`

<details><summary>Code</summary>

```typescript
clampLength( min, max ) {

		const length = this.length();

		return this.divideScalar( length || 1 ).multiplyScalar( clamp( length, min, max ) );

	}
```
</details>

### `Vector2.floor(): Vector2`

**JSDoc:**
```typescript
/**
	 * The components of this vector are rounded down to the nearest integer value.
	 *
	 * @return {Vector2} A reference to this vector.
	 */
```

**Returns:** `Vector2`

**Calls:**

- `Math.floor`

<details><summary>Code</summary>

```typescript
floor() {

		this.x = Math.floor( this.x );
		this.y = Math.floor( this.y );

		return this;

	}
```
</details>

### `Vector2.ceil(): Vector2`

**JSDoc:**
```typescript
/**
	 * The components of this vector are rounded up to the nearest integer value.
	 *
	 * @return {Vector2} A reference to this vector.
	 */
```

**Returns:** `Vector2`

**Calls:**

- `Math.ceil`

<details><summary>Code</summary>

```typescript
ceil() {

		this.x = Math.ceil( this.x );
		this.y = Math.ceil( this.y );

		return this;

	}
```
</details>

### `Vector2.round(): Vector2`

**JSDoc:**
```typescript
/**
	 * The components of this vector are rounded to the nearest integer value
	 *
	 * @return {Vector2} A reference to this vector.
	 */
```

**Returns:** `Vector2`

**Calls:**

- `Math.round`

<details><summary>Code</summary>

```typescript
round() {

		this.x = Math.round( this.x );
		this.y = Math.round( this.y );

		return this;

	}
```
</details>

### `Vector2.roundToZero(): Vector2`

**JSDoc:**
```typescript
/**
	 * The components of this vector are rounded towards zero (up if negative,
	 * down if positive) to an integer value.
	 *
	 * @return {Vector2} A reference to this vector.
	 */
```

**Returns:** `Vector2`

**Calls:**

- `Math.trunc`

<details><summary>Code</summary>

```typescript
roundToZero() {

		this.x = Math.trunc( this.x );
		this.y = Math.trunc( this.y );

		return this;

	}
```
</details>

### `Vector2.negate(): Vector2`

**JSDoc:**
```typescript
/**
	 * Inverts this vector - i.e. sets x = -x and y = -y.
	 *
	 * @return {Vector2} A reference to this vector.
	 */
```

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
negate() {

		this.x = - this.x;
		this.y = - this.y;

		return this;

	}
```
</details>

### `Vector2.dot(v: Vector2): number`

**JSDoc:**
```typescript
/**
	 * Calculates the dot product of the given vector with this instance.
	 *
	 * @param {Vector2} v - The vector to compute the dot product with.
	 * @return {number} The result of the dot product.
	 */
```

**Parameters:**

- **`v`** `Vector2`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
dot( v ) {

		return this.x * v.x + this.y * v.y;

	}
```
</details>

### `Vector2.cross(v: Vector2): number`

**JSDoc:**
```typescript
/**
	 * Calculates the cross product of the given vector with this instance.
	 *
	 * @param {Vector2} v - The vector to compute the cross product with.
	 * @return {number} The result of the cross product.
	 */
```

**Parameters:**

- **`v`** `Vector2`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
cross( v ) {

		return this.x * v.y - this.y * v.x;

	}
```
</details>

### `Vector2.lengthSq(): number`

**JSDoc:**
```typescript
/**
	 * Computes the square of the Euclidean length (straight-line length) from
	 * (0, 0) to (x, y). If you are comparing the lengths of vectors, you should
	 * compare the length squared instead as it is slightly more efficient to calculate.
	 *
	 * @return {number} The square length of this vector.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
lengthSq() {

		return this.x * this.x + this.y * this.y;

	}
```
</details>

### `Vector2.length(): number`

**JSDoc:**
```typescript
/**
	 * Computes the  Euclidean length (straight-line length) from (0, 0) to (x, y).
	 *
	 * @return {number} The length of this vector.
	 */
```

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
length() {

		return Math.sqrt( this.x * this.x + this.y * this.y );

	}
```
</details>

### `Vector2.manhattanLength(): number`

**JSDoc:**
```typescript
/**
	 * Computes the Manhattan length of this vector.
	 *
	 * @return {number} The length of this vector.
	 */
```

**Returns:** `number`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
manhattanLength() {

		return Math.abs( this.x ) + Math.abs( this.y );

	}
```
</details>

### `Vector2.normalize(): Vector2`

**JSDoc:**
```typescript
/**
	 * Converts this vector to a unit vector - that is, sets it equal to a vector
	 * with the same direction as this one, but with a vector length of `1`.
	 *
	 * @return {Vector2} A reference to this vector.
	 */
```

**Returns:** `Vector2`

**Calls:**

- `this.divideScalar`
- `this.length`

<details><summary>Code</summary>

```typescript
normalize() {

		return this.divideScalar( this.length() || 1 );

	}
```
</details>

### `Vector2.angle(): number`

**JSDoc:**
```typescript
/**
	 * Computes the angle in radians of this vector with respect to the positive x-axis.
	 *
	 * @return {number} The angle in radians.
	 */
```

**Returns:** `number`

**Calls:**

- `Math.atan2`

<details><summary>Code</summary>

```typescript
angle() {

		const angle = Math.atan2( - this.y, - this.x ) + Math.PI;

		return angle;

	}
```
</details>

### `Vector2.angleTo(v: Vector2): number`

**JSDoc:**
```typescript
/**
	 * Returns the angle between the given vector and this instance in radians.
	 *
	 * @param {Vector2} v - The vector to compute the angle with.
	 * @return {number} The angle in radians.
	 */
```

**Parameters:**

- **`v`** `Vector2`

**Returns:** `number`

**Calls:**

- `Math.sqrt`
- `this.lengthSq`
- `v.lengthSq`
- `this.dot`
- `Math.acos`
- `clamp (from ./MathUtils.js)`

**Internal Comments:**
```
// clamp, to handle numerical problems
```

<details><summary>Code</summary>

```typescript
angleTo( v ) {

		const denominator = Math.sqrt( this.lengthSq() * v.lengthSq() );

		if ( denominator === 0 ) return Math.PI / 2;

		const theta = this.dot( v ) / denominator;

		// clamp, to handle numerical problems

		return Math.acos( clamp( theta, - 1, 1 ) );

	}
```
</details>

### `Vector2.distanceTo(v: Vector2): number`

**JSDoc:**
```typescript
/**
	 * Computes the distance from the given vector to this instance.
	 *
	 * @param {Vector2} v - The vector to compute the distance to.
	 * @return {number} The distance.
	 */
```

**Parameters:**

- **`v`** `Vector2`

**Returns:** `number`

**Calls:**

- `Math.sqrt`
- `this.distanceToSquared`

<details><summary>Code</summary>

```typescript
distanceTo( v ) {

		return Math.sqrt( this.distanceToSquared( v ) );

	}
```
</details>

### `Vector2.distanceToSquared(v: Vector2): number`

**JSDoc:**
```typescript
/**
	 * Computes the squared distance from the given vector to this instance.
	 * If you are just comparing the distance with another distance, you should compare
	 * the distance squared instead as it is slightly more efficient to calculate.
	 *
	 * @param {Vector2} v - The vector to compute the squared distance to.
	 * @return {number} The squared distance.
	 */
```

**Parameters:**

- **`v`** `Vector2`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
distanceToSquared( v ) {

		const dx = this.x - v.x, dy = this.y - v.y;
		return dx * dx + dy * dy;

	}
```
</details>

### `Vector2.manhattanDistanceTo(v: Vector2): number`

**JSDoc:**
```typescript
/**
	 * Computes the Manhattan distance from the given vector to this instance.
	 *
	 * @param {Vector2} v - The vector to compute the Manhattan distance to.
	 * @return {number} The Manhattan distance.
	 */
```

**Parameters:**

- **`v`** `Vector2`

**Returns:** `number`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
manhattanDistanceTo( v ) {

		return Math.abs( this.x - v.x ) + Math.abs( this.y - v.y );

	}
```
</details>

### `Vector2.setLength(length: number): Vector2`

**JSDoc:**
```typescript
/**
	 * Sets this vector to a vector with the same direction as this one, but
	 * with the specified length.
	 *
	 * @param {number} length - The new length of this vector.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`length`** `number`

**Returns:** `Vector2`

**Calls:**

- `this.normalize().multiplyScalar`

<details><summary>Code</summary>

```typescript
setLength( length ) {

		return this.normalize().multiplyScalar( length );

	}
```
</details>

### `Vector2.lerp(v: Vector2, alpha: number): Vector2`

**JSDoc:**
```typescript
/**
	 * Linearly interpolates between the given vector and this instance, where
	 * alpha is the percent distance along the line - alpha = 0 will be this
	 * vector, and alpha = 1 will be the given one.
	 *
	 * @param {Vector2} v - The vector to interpolate towards.
	 * @param {number} alpha - The interpolation factor, typically in the closed interval `[0, 1]`.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector2`
- **`alpha`** `number`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
lerp( v, alpha ) {

		this.x += ( v.x - this.x ) * alpha;
		this.y += ( v.y - this.y ) * alpha;

		return this;

	}
```
</details>

### `Vector2.lerpVectors(v1: Vector2, v2: Vector2, alpha: number): Vector2`

**JSDoc:**
```typescript
/**
	 * Linearly interpolates between the given vectors, where alpha is the percent
	 * distance along the line - alpha = 0 will be first vector, and alpha = 1 will
	 * be the second one. The result is stored in this instance.
	 *
	 * @param {Vector2} v1 - The first vector.
	 * @param {Vector2} v2 - The second vector.
	 * @param {number} alpha - The interpolation factor, typically in the closed interval `[0, 1]`.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`v1`** `Vector2`
- **`v2`** `Vector2`
- **`alpha`** `number`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
lerpVectors( v1, v2, alpha ) {

		this.x = v1.x + ( v2.x - v1.x ) * alpha;
		this.y = v1.y + ( v2.y - v1.y ) * alpha;

		return this;

	}
```
</details>

### `Vector2.equals(v: Vector2): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this vector is equal with the given one.
	 *
	 * @param {Vector2} v - The vector to test for equality.
	 * @return {boolean} Whether this vector is equal with the given one.
	 */
```

**Parameters:**

- **`v`** `Vector2`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
equals( v ) {

		return ( ( v.x === this.x ) && ( v.y === this.y ) );

	}
```
</details>

### `Vector2.fromArray(array: number[], offset: number): Vector2`

**JSDoc:**
```typescript
/**
	 * Sets this vector's x value to be `array[ offset ]` and y
	 * value to be `array[ offset + 1 ]`.
	 *
	 * @param {Array<number>} array - An array holding the vector component values.
	 * @param {number} [offset=0] - The offset into the array.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`array`** `number[]`
- **`offset`** `number`

**Returns:** `Vector2`

<details><summary>Code</summary>

```typescript
fromArray( array, offset = 0 ) {

		this.x = array[ offset ];
		this.y = array[ offset + 1 ];

		return this;

	}
```
</details>

### `Vector2.toArray(array: number[], offset: number): number[]`

**JSDoc:**
```typescript
/**
	 * Writes the components of this vector to the given array. If no array is provided,
	 * the method returns a new instance.
	 *
	 * @param {Array<number>} [array=[]] - The target array holding the vector components.
	 * @param {number} [offset=0] - Index of the first element in the array.
	 * @return {Array<number>} The vector components.
	 */
```

**Parameters:**

- **`array`** `number[]`
- **`offset`** `number`

**Returns:** `number[]`

<details><summary>Code</summary>

```typescript
toArray( array = [], offset = 0 ) {

		array[ offset ] = this.x;
		array[ offset + 1 ] = this.y;

		return array;

	}
```
</details>

### `Vector2.fromBufferAttribute(attribute: BufferAttribute, index: number): Vector2`

**JSDoc:**
```typescript
/**
	 * Sets the components of this vector from the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute holding vector data.
	 * @param {number} index - The index into the attribute.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`
- **`index`** `number`

**Returns:** `Vector2`

**Calls:**

- `attribute.getX`
- `attribute.getY`

<details><summary>Code</summary>

```typescript
fromBufferAttribute( attribute, index ) {

		this.x = attribute.getX( index );
		this.y = attribute.getY( index );

		return this;

	}
```
</details>

### `Vector2.rotateAround(center: Vector2, angle: number): Vector2`

**JSDoc:**
```typescript
/**
	 * Rotates this vector around the given center by the given angle.
	 *
	 * @param {Vector2} center - The point around which to rotate.
	 * @param {number} angle - The angle to rotate, in radians.
	 * @return {Vector2} A reference to this vector.
	 */
```

**Parameters:**

- **`center`** `Vector2`
- **`angle`** `number`

**Returns:** `Vector2`

**Calls:**

- `Math.cos`
- `Math.sin`

<details><summary>Code</summary>

```typescript
rotateAround( center, angle ) {

		const c = Math.cos( angle ), s = Math.sin( angle );

		const x = this.x - center.x;
		const y = this.y - center.y;

		this.x = x * c - y * s + center.x;
		this.y = x * s + y * c + center.y;

		return this;

	}
```
</details>

### `Vector2.random(): Vector2`

**JSDoc:**
```typescript
/**
	 * Sets each component of this vector to a pseudo-random value between `0` and
	 * `1`, excluding `1`.
	 *
	 * @return {Vector2} A reference to this vector.
	 */
```

**Returns:** `Vector2`

**Calls:**

- `Math.random`

<details><summary>Code</summary>

```typescript
random() {

		this.x = Math.random();
		this.y = Math.random();

		return this;

	}
```
</details>

### `Vector2.[ Symbol.iterator ](): Generator<number, void, unknown>`

**Returns:** `Generator<number, void, unknown>`

<details><summary>Code</summary>

```typescript
*[ Symbol.iterator ]() {

		yield this.x;
		yield this.y;

	}
```
</details>


---

## Classes

### `Vector2`

<details><summary>Class Code</summary>

```ts
class Vector2 {

	/**
	 * Constructs a new 2D vector.
	 *
	 * @param {number} [x=0] - The x value of this vector.
	 * @param {number} [y=0] - The y value of this vector.
	 */
	constructor( x = 0, y = 0 ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		Vector2.prototype.isVector2 = true;

		/**
		 * The x value of this vector.
		 *
		 * @type {number}
		 */
		this.x = x;

		/**
		 * The y value of this vector.
		 *
		 * @type {number}
		 */
		this.y = y;

	}

	/**
	 * Alias for {@link Vector2#x}.
	 *
	 * @type {number}
	 */
	get width() {

		return this.x;

	}

	set width( value ) {

		this.x = value;

	}

	/**
	 * Alias for {@link Vector2#y}.
	 *
	 * @type {number}
	 */
	get height() {

		return this.y;

	}

	set height( value ) {

		this.y = value;

	}

	/**
	 * Sets the vector components.
	 *
	 * @param {number} x - The value of the x component.
	 * @param {number} y - The value of the y component.
	 * @return {Vector2} A reference to this vector.
	 */
	set( x, y ) {

		this.x = x;
		this.y = y;

		return this;

	}

	/**
	 * Sets the vector components to the same value.
	 *
	 * @param {number} scalar - The value to set for all vector components.
	 * @return {Vector2} A reference to this vector.
	 */
	setScalar( scalar ) {

		this.x = scalar;
		this.y = scalar;

		return this;

	}

	/**
	 * Sets the vector's x component to the given value
	 *
	 * @param {number} x - The value to set.
	 * @return {Vector2} A reference to this vector.
	 */
	setX( x ) {

		this.x = x;

		return this;

	}

	/**
	 * Sets the vector's y component to the given value
	 *
	 * @param {number} y - The value to set.
	 * @return {Vector2} A reference to this vector.
	 */
	setY( y ) {

		this.y = y;

		return this;

	}

	/**
	 * Allows to set a vector component with an index.
	 *
	 * @param {number} index - The component index. `0` equals to x, `1` equals to y.
	 * @param {number} value - The value to set.
	 * @return {Vector2} A reference to this vector.
	 */
	setComponent( index, value ) {

		switch ( index ) {

			case 0: this.x = value; break;
			case 1: this.y = value; break;
			default: throw new Error( 'index is out of range: ' + index );

		}

		return this;

	}

	/**
	 * Returns the value of the vector component which matches the given index.
	 *
	 * @param {number} index - The component index. `0` equals to x, `1` equals to y.
	 * @return {number} A vector component value.
	 */
	getComponent( index ) {

		switch ( index ) {

			case 0: return this.x;
			case 1: return this.y;
			default: throw new Error( 'index is out of range: ' + index );

		}

	}

	/**
	 * Returns a new vector with copied values from this instance.
	 *
	 * @return {Vector2} A clone of this instance.
	 */
	clone() {

		return new this.constructor( this.x, this.y );

	}

	/**
	 * Copies the values of the given vector to this instance.
	 *
	 * @param {Vector2} v - The vector to copy.
	 * @return {Vector2} A reference to this vector.
	 */
	copy( v ) {

		this.x = v.x;
		this.y = v.y;

		return this;

	}

	/**
	 * Adds the given vector to this instance.
	 *
	 * @param {Vector2} v - The vector to add.
	 * @return {Vector2} A reference to this vector.
	 */
	add( v ) {

		this.x += v.x;
		this.y += v.y;

		return this;

	}

	/**
	 * Adds the given scalar value to all components of this instance.
	 *
	 * @param {number} s - The scalar to add.
	 * @return {Vector2} A reference to this vector.
	 */
	addScalar( s ) {

		this.x += s;
		this.y += s;

		return this;

	}

	/**
	 * Adds the given vectors and stores the result in this instance.
	 *
	 * @param {Vector2} a - The first vector.
	 * @param {Vector2} b - The second vector.
	 * @return {Vector2} A reference to this vector.
	 */
	addVectors( a, b ) {

		this.x = a.x + b.x;
		this.y = a.y + b.y;

		return this;

	}

	/**
	 * Adds the given vector scaled by the given factor to this instance.
	 *
	 * @param {Vector2} v - The vector.
	 * @param {number} s - The factor that scales `v`.
	 * @return {Vector2} A reference to this vector.
	 */
	addScaledVector( v, s ) {

		this.x += v.x * s;
		this.y += v.y * s;

		return this;

	}

	/**
	 * Subtracts the given vector from this instance.
	 *
	 * @param {Vector2} v - The vector to subtract.
	 * @return {Vector2} A reference to this vector.
	 */
	sub( v ) {

		this.x -= v.x;
		this.y -= v.y;

		return this;

	}

	/**
	 * Subtracts the given scalar value from all components of this instance.
	 *
	 * @param {number} s - The scalar to subtract.
	 * @return {Vector2} A reference to this vector.
	 */
	subScalar( s ) {

		this.x -= s;
		this.y -= s;

		return this;

	}

	/**
	 * Subtracts the given vectors and stores the result in this instance.
	 *
	 * @param {Vector2} a - The first vector.
	 * @param {Vector2} b - The second vector.
	 * @return {Vector2} A reference to this vector.
	 */
	subVectors( a, b ) {

		this.x = a.x - b.x;
		this.y = a.y - b.y;

		return this;

	}

	/**
	 * Multiplies the given vector with this instance.
	 *
	 * @param {Vector2} v - The vector to multiply.
	 * @return {Vector2} A reference to this vector.
	 */
	multiply( v ) {

		this.x *= v.x;
		this.y *= v.y;

		return this;

	}

	/**
	 * Multiplies the given scalar value with all components of this instance.
	 *
	 * @param {number} scalar - The scalar to multiply.
	 * @return {Vector2} A reference to this vector.
	 */
	multiplyScalar( scalar ) {

		this.x *= scalar;
		this.y *= scalar;

		return this;

	}

	/**
	 * Divides this instance by the given vector.
	 *
	 * @param {Vector2} v - The vector to divide.
	 * @return {Vector2} A reference to this vector.
	 */
	divide( v ) {

		this.x /= v.x;
		this.y /= v.y;

		return this;

	}

	/**
	 * Divides this vector by the given scalar.
	 *
	 * @param {number} scalar - The scalar to divide.
	 * @return {Vector2} A reference to this vector.
	 */
	divideScalar( scalar ) {

		return this.multiplyScalar( 1 / scalar );

	}

	/**
	 * Multiplies this vector (with an implicit 1 as the 3rd component) by
	 * the given 3x3 matrix.
	 *
	 * @param {Matrix3} m - The matrix to apply.
	 * @return {Vector2} A reference to this vector.
	 */
	applyMatrix3( m ) {

		const x = this.x, y = this.y;
		const e = m.elements;

		this.x = e[ 0 ] * x + e[ 3 ] * y + e[ 6 ];
		this.y = e[ 1 ] * x + e[ 4 ] * y + e[ 7 ];

		return this;

	}

	/**
	 * If this vector's x or y value is greater than the given vector's x or y
	 * value, replace that value with the corresponding min value.
	 *
	 * @param {Vector2} v - The vector.
	 * @return {Vector2} A reference to this vector.
	 */
	min( v ) {

		this.x = Math.min( this.x, v.x );
		this.y = Math.min( this.y, v.y );

		return this;

	}

	/**
	 * If this vector's x or y value is less than the given vector's x or y
	 * value, replace that value with the corresponding max value.
	 *
	 * @param {Vector2} v - The vector.
	 * @return {Vector2} A reference to this vector.
	 */
	max( v ) {

		this.x = Math.max( this.x, v.x );
		this.y = Math.max( this.y, v.y );

		return this;

	}

	/**
	 * If this vector's x or y value is greater than the max vector's x or y
	 * value, it is replaced by the corresponding value.
	 * If this vector's x or y value is less than the min vector's x or y value,
	 * it is replaced by the corresponding value.
	 *
	 * @param {Vector2} min - The minimum x and y values.
	 * @param {Vector2} max - The maximum x and y values in the desired range.
	 * @return {Vector2} A reference to this vector.
	 */
	clamp( min, max ) {

		// assumes min < max, componentwise

		this.x = clamp( this.x, min.x, max.x );
		this.y = clamp( this.y, min.y, max.y );

		return this;

	}

	/**
	 * If this vector's x or y values are greater than the max value, they are
	 * replaced by the max value.
	 * If this vector's x or y values are less than the min value, they are
	 * replaced by the min value.
	 *
	 * @param {number} minVal - The minimum value the components will be clamped to.
	 * @param {number} maxVal - The maximum value the components will be clamped to.
	 * @return {Vector2} A reference to this vector.
	 */
	clampScalar( minVal, maxVal ) {

		this.x = clamp( this.x, minVal, maxVal );
		this.y = clamp( this.y, minVal, maxVal );

		return this;

	}

	/**
	 * If this vector's length is greater than the max value, it is replaced by
	 * the max value.
	 * If this vector's length is less than the min value, it is replaced by the
	 * min value.
	 *
	 * @param {number} min - The minimum value the vector length will be clamped to.
	 * @param {number} max - The maximum value the vector length will be clamped to.
	 * @return {Vector2} A reference to this vector.
	 */
	clampLength( min, max ) {

		const length = this.length();

		return this.divideScalar( length || 1 ).multiplyScalar( clamp( length, min, max ) );

	}

	/**
	 * The components of this vector are rounded down to the nearest integer value.
	 *
	 * @return {Vector2} A reference to this vector.
	 */
	floor() {

		this.x = Math.floor( this.x );
		this.y = Math.floor( this.y );

		return this;

	}

	/**
	 * The components of this vector are rounded up to the nearest integer value.
	 *
	 * @return {Vector2} A reference to this vector.
	 */
	ceil() {

		this.x = Math.ceil( this.x );
		this.y = Math.ceil( this.y );

		return this;

	}

	/**
	 * The components of this vector are rounded to the nearest integer value
	 *
	 * @return {Vector2} A reference to this vector.
	 */
	round() {

		this.x = Math.round( this.x );
		this.y = Math.round( this.y );

		return this;

	}

	/**
	 * The components of this vector are rounded towards zero (up if negative,
	 * down if positive) to an integer value.
	 *
	 * @return {Vector2} A reference to this vector.
	 */
	roundToZero() {

		this.x = Math.trunc( this.x );
		this.y = Math.trunc( this.y );

		return this;

	}

	/**
	 * Inverts this vector - i.e. sets x = -x and y = -y.
	 *
	 * @return {Vector2} A reference to this vector.
	 */
	negate() {

		this.x = - this.x;
		this.y = - this.y;

		return this;

	}

	/**
	 * Calculates the dot product of the given vector with this instance.
	 *
	 * @param {Vector2} v - The vector to compute the dot product with.
	 * @return {number} The result of the dot product.
	 */
	dot( v ) {

		return this.x * v.x + this.y * v.y;

	}

	/**
	 * Calculates the cross product of the given vector with this instance.
	 *
	 * @param {Vector2} v - The vector to compute the cross product with.
	 * @return {number} The result of the cross product.
	 */
	cross( v ) {

		return this.x * v.y - this.y * v.x;

	}

	/**
	 * Computes the square of the Euclidean length (straight-line length) from
	 * (0, 0) to (x, y). If you are comparing the lengths of vectors, you should
	 * compare the length squared instead as it is slightly more efficient to calculate.
	 *
	 * @return {number} The square length of this vector.
	 */
	lengthSq() {

		return this.x * this.x + this.y * this.y;

	}

	/**
	 * Computes the  Euclidean length (straight-line length) from (0, 0) to (x, y).
	 *
	 * @return {number} The length of this vector.
	 */
	length() {

		return Math.sqrt( this.x * this.x + this.y * this.y );

	}

	/**
	 * Computes the Manhattan length of this vector.
	 *
	 * @return {number} The length of this vector.
	 */
	manhattanLength() {

		return Math.abs( this.x ) + Math.abs( this.y );

	}

	/**
	 * Converts this vector to a unit vector - that is, sets it equal to a vector
	 * with the same direction as this one, but with a vector length of `1`.
	 *
	 * @return {Vector2} A reference to this vector.
	 */
	normalize() {

		return this.divideScalar( this.length() || 1 );

	}

	/**
	 * Computes the angle in radians of this vector with respect to the positive x-axis.
	 *
	 * @return {number} The angle in radians.
	 */
	angle() {

		const angle = Math.atan2( - this.y, - this.x ) + Math.PI;

		return angle;

	}

	/**
	 * Returns the angle between the given vector and this instance in radians.
	 *
	 * @param {Vector2} v - The vector to compute the angle with.
	 * @return {number} The angle in radians.
	 */
	angleTo( v ) {

		const denominator = Math.sqrt( this.lengthSq() * v.lengthSq() );

		if ( denominator === 0 ) return Math.PI / 2;

		const theta = this.dot( v ) / denominator;

		// clamp, to handle numerical problems

		return Math.acos( clamp( theta, - 1, 1 ) );

	}

	/**
	 * Computes the distance from the given vector to this instance.
	 *
	 * @param {Vector2} v - The vector to compute the distance to.
	 * @return {number} The distance.
	 */
	distanceTo( v ) {

		return Math.sqrt( this.distanceToSquared( v ) );

	}

	/**
	 * Computes the squared distance from the given vector to this instance.
	 * If you are just comparing the distance with another distance, you should compare
	 * the distance squared instead as it is slightly more efficient to calculate.
	 *
	 * @param {Vector2} v - The vector to compute the squared distance to.
	 * @return {number} The squared distance.
	 */
	distanceToSquared( v ) {

		const dx = this.x - v.x, dy = this.y - v.y;
		return dx * dx + dy * dy;

	}

	/**
	 * Computes the Manhattan distance from the given vector to this instance.
	 *
	 * @param {Vector2} v - The vector to compute the Manhattan distance to.
	 * @return {number} The Manhattan distance.
	 */
	manhattanDistanceTo( v ) {

		return Math.abs( this.x - v.x ) + Math.abs( this.y - v.y );

	}

	/**
	 * Sets this vector to a vector with the same direction as this one, but
	 * with the specified length.
	 *
	 * @param {number} length - The new length of this vector.
	 * @return {Vector2} A reference to this vector.
	 */
	setLength( length ) {

		return this.normalize().multiplyScalar( length );

	}

	/**
	 * Linearly interpolates between the given vector and this instance, where
	 * alpha is the percent distance along the line - alpha = 0 will be this
	 * vector, and alpha = 1 will be the given one.
	 *
	 * @param {Vector2} v - The vector to interpolate towards.
	 * @param {number} alpha - The interpolation factor, typically in the closed interval `[0, 1]`.
	 * @return {Vector2} A reference to this vector.
	 */
	lerp( v, alpha ) {

		this.x += ( v.x - this.x ) * alpha;
		this.y += ( v.y - this.y ) * alpha;

		return this;

	}

	/**
	 * Linearly interpolates between the given vectors, where alpha is the percent
	 * distance along the line - alpha = 0 will be first vector, and alpha = 1 will
	 * be the second one. The result is stored in this instance.
	 *
	 * @param {Vector2} v1 - The first vector.
	 * @param {Vector2} v2 - The second vector.
	 * @param {number} alpha - The interpolation factor, typically in the closed interval `[0, 1]`.
	 * @return {Vector2} A reference to this vector.
	 */
	lerpVectors( v1, v2, alpha ) {

		this.x = v1.x + ( v2.x - v1.x ) * alpha;
		this.y = v1.y + ( v2.y - v1.y ) * alpha;

		return this;

	}

	/**
	 * Returns `true` if this vector is equal with the given one.
	 *
	 * @param {Vector2} v - The vector to test for equality.
	 * @return {boolean} Whether this vector is equal with the given one.
	 */
	equals( v ) {

		return ( ( v.x === this.x ) && ( v.y === this.y ) );

	}

	/**
	 * Sets this vector's x value to be `array[ offset ]` and y
	 * value to be `array[ offset + 1 ]`.
	 *
	 * @param {Array<number>} array - An array holding the vector component values.
	 * @param {number} [offset=0] - The offset into the array.
	 * @return {Vector2} A reference to this vector.
	 */
	fromArray( array, offset = 0 ) {

		this.x = array[ offset ];
		this.y = array[ offset + 1 ];

		return this;

	}

	/**
	 * Writes the components of this vector to the given array. If no array is provided,
	 * the method returns a new instance.
	 *
	 * @param {Array<number>} [array=[]] - The target array holding the vector components.
	 * @param {number} [offset=0] - Index of the first element in the array.
	 * @return {Array<number>} The vector components.
	 */
	toArray( array = [], offset = 0 ) {

		array[ offset ] = this.x;
		array[ offset + 1 ] = this.y;

		return array;

	}

	/**
	 * Sets the components of this vector from the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute holding vector data.
	 * @param {number} index - The index into the attribute.
	 * @return {Vector2} A reference to this vector.
	 */
	fromBufferAttribute( attribute, index ) {

		this.x = attribute.getX( index );
		this.y = attribute.getY( index );

		return this;

	}

	/**
	 * Rotates this vector around the given center by the given angle.
	 *
	 * @param {Vector2} center - The point around which to rotate.
	 * @param {number} angle - The angle to rotate, in radians.
	 * @return {Vector2} A reference to this vector.
	 */
	rotateAround( center, angle ) {

		const c = Math.cos( angle ), s = Math.sin( angle );

		const x = this.x - center.x;
		const y = this.y - center.y;

		this.x = x * c - y * s + center.x;
		this.y = x * s + y * c + center.y;

		return this;

	}

	/**
	 * Sets each component of this vector to a pseudo-random value between `0` and
	 * `1`, excluding `1`.
	 *
	 * @return {Vector2} A reference to this vector.
	 */
	random() {

		this.x = Math.random();
		this.y = Math.random();

		return this;

	}

	*[ Symbol.iterator ]() {

		yield this.x;
		yield this.y;

	}

}
```
</details>

#### Methods

##### `set(x: number, y: number): Vector2`

<details><summary>Code</summary>

```ts
set( x, y ) {

		this.x = x;
		this.y = y;

		return this;

	}
```
</details>

##### `setScalar(scalar: number): Vector2`

<details><summary>Code</summary>

```ts
setScalar( scalar ) {

		this.x = scalar;
		this.y = scalar;

		return this;

	}
```
</details>

##### `setX(x: number): Vector2`

<details><summary>Code</summary>

```ts
setX( x ) {

		this.x = x;

		return this;

	}
```
</details>

##### `setY(y: number): Vector2`

<details><summary>Code</summary>

```ts
setY( y ) {

		this.y = y;

		return this;

	}
```
</details>

##### `setComponent(index: number, value: number): Vector2`

<details><summary>Code</summary>

```ts
setComponent( index, value ) {

		switch ( index ) {

			case 0: this.x = value; break;
			case 1: this.y = value; break;
			default: throw new Error( 'index is out of range: ' + index );

		}

		return this;

	}
```
</details>

##### `getComponent(index: number): number`

<details><summary>Code</summary>

```ts
getComponent( index ) {

		switch ( index ) {

			case 0: return this.x;
			case 1: return this.y;
			default: throw new Error( 'index is out of range: ' + index );

		}

	}
```
</details>

##### `clone(): Vector2`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor( this.x, this.y );

	}
```
</details>

##### `copy(v: Vector2): Vector2`

<details><summary>Code</summary>

```ts
copy( v ) {

		this.x = v.x;
		this.y = v.y;

		return this;

	}
```
</details>

##### `add(v: Vector2): Vector2`

<details><summary>Code</summary>

```ts
add( v ) {

		this.x += v.x;
		this.y += v.y;

		return this;

	}
```
</details>

##### `addScalar(s: number): Vector2`

<details><summary>Code</summary>

```ts
addScalar( s ) {

		this.x += s;
		this.y += s;

		return this;

	}
```
</details>

##### `addVectors(a: Vector2, b: Vector2): Vector2`

<details><summary>Code</summary>

```ts
addVectors( a, b ) {

		this.x = a.x + b.x;
		this.y = a.y + b.y;

		return this;

	}
```
</details>

##### `addScaledVector(v: Vector2, s: number): Vector2`

<details><summary>Code</summary>

```ts
addScaledVector( v, s ) {

		this.x += v.x * s;
		this.y += v.y * s;

		return this;

	}
```
</details>

##### `sub(v: Vector2): Vector2`

<details><summary>Code</summary>

```ts
sub( v ) {

		this.x -= v.x;
		this.y -= v.y;

		return this;

	}
```
</details>

##### `subScalar(s: number): Vector2`

<details><summary>Code</summary>

```ts
subScalar( s ) {

		this.x -= s;
		this.y -= s;

		return this;

	}
```
</details>

##### `subVectors(a: Vector2, b: Vector2): Vector2`

<details><summary>Code</summary>

```ts
subVectors( a, b ) {

		this.x = a.x - b.x;
		this.y = a.y - b.y;

		return this;

	}
```
</details>

##### `multiply(v: Vector2): Vector2`

<details><summary>Code</summary>

```ts
multiply( v ) {

		this.x *= v.x;
		this.y *= v.y;

		return this;

	}
```
</details>

##### `multiplyScalar(scalar: number): Vector2`

<details><summary>Code</summary>

```ts
multiplyScalar( scalar ) {

		this.x *= scalar;
		this.y *= scalar;

		return this;

	}
```
</details>

##### `divide(v: Vector2): Vector2`

<details><summary>Code</summary>

```ts
divide( v ) {

		this.x /= v.x;
		this.y /= v.y;

		return this;

	}
```
</details>

##### `divideScalar(scalar: number): Vector2`

<details><summary>Code</summary>

```ts
divideScalar( scalar ) {

		return this.multiplyScalar( 1 / scalar );

	}
```
</details>

##### `applyMatrix3(m: Matrix3): Vector2`

<details><summary>Code</summary>

```ts
applyMatrix3( m ) {

		const x = this.x, y = this.y;
		const e = m.elements;

		this.x = e[ 0 ] * x + e[ 3 ] * y + e[ 6 ];
		this.y = e[ 1 ] * x + e[ 4 ] * y + e[ 7 ];

		return this;

	}
```
</details>

##### `min(v: Vector2): Vector2`

<details><summary>Code</summary>

```ts
min( v ) {

		this.x = Math.min( this.x, v.x );
		this.y = Math.min( this.y, v.y );

		return this;

	}
```
</details>

##### `max(v: Vector2): Vector2`

<details><summary>Code</summary>

```ts
max( v ) {

		this.x = Math.max( this.x, v.x );
		this.y = Math.max( this.y, v.y );

		return this;

	}
```
</details>

##### `clamp(min: Vector2, max: Vector2): Vector2`

<details><summary>Code</summary>

```ts
clamp( min, max ) {

		// assumes min < max, componentwise

		this.x = clamp( this.x, min.x, max.x );
		this.y = clamp( this.y, min.y, max.y );

		return this;

	}
```
</details>

##### `clampScalar(minVal: number, maxVal: number): Vector2`

<details><summary>Code</summary>

```ts
clampScalar( minVal, maxVal ) {

		this.x = clamp( this.x, minVal, maxVal );
		this.y = clamp( this.y, minVal, maxVal );

		return this;

	}
```
</details>

##### `clampLength(min: number, max: number): Vector2`

<details><summary>Code</summary>

```ts
clampLength( min, max ) {

		const length = this.length();

		return this.divideScalar( length || 1 ).multiplyScalar( clamp( length, min, max ) );

	}
```
</details>

##### `floor(): Vector2`

<details><summary>Code</summary>

```ts
floor() {

		this.x = Math.floor( this.x );
		this.y = Math.floor( this.y );

		return this;

	}
```
</details>

##### `ceil(): Vector2`

<details><summary>Code</summary>

```ts
ceil() {

		this.x = Math.ceil( this.x );
		this.y = Math.ceil( this.y );

		return this;

	}
```
</details>

##### `round(): Vector2`

<details><summary>Code</summary>

```ts
round() {

		this.x = Math.round( this.x );
		this.y = Math.round( this.y );

		return this;

	}
```
</details>

##### `roundToZero(): Vector2`

<details><summary>Code</summary>

```ts
roundToZero() {

		this.x = Math.trunc( this.x );
		this.y = Math.trunc( this.y );

		return this;

	}
```
</details>

##### `negate(): Vector2`

<details><summary>Code</summary>

```ts
negate() {

		this.x = - this.x;
		this.y = - this.y;

		return this;

	}
```
</details>

##### `dot(v: Vector2): number`

<details><summary>Code</summary>

```ts
dot( v ) {

		return this.x * v.x + this.y * v.y;

	}
```
</details>

##### `cross(v: Vector2): number`

<details><summary>Code</summary>

```ts
cross( v ) {

		return this.x * v.y - this.y * v.x;

	}
```
</details>

##### `lengthSq(): number`

<details><summary>Code</summary>

```ts
lengthSq() {

		return this.x * this.x + this.y * this.y;

	}
```
</details>

##### `length(): number`

<details><summary>Code</summary>

```ts
length() {

		return Math.sqrt( this.x * this.x + this.y * this.y );

	}
```
</details>

##### `manhattanLength(): number`

<details><summary>Code</summary>

```ts
manhattanLength() {

		return Math.abs( this.x ) + Math.abs( this.y );

	}
```
</details>

##### `normalize(): Vector2`

<details><summary>Code</summary>

```ts
normalize() {

		return this.divideScalar( this.length() || 1 );

	}
```
</details>

##### `angle(): number`

<details><summary>Code</summary>

```ts
angle() {

		const angle = Math.atan2( - this.y, - this.x ) + Math.PI;

		return angle;

	}
```
</details>

##### `angleTo(v: Vector2): number`

<details><summary>Code</summary>

```ts
angleTo( v ) {

		const denominator = Math.sqrt( this.lengthSq() * v.lengthSq() );

		if ( denominator === 0 ) return Math.PI / 2;

		const theta = this.dot( v ) / denominator;

		// clamp, to handle numerical problems

		return Math.acos( clamp( theta, - 1, 1 ) );

	}
```
</details>

##### `distanceTo(v: Vector2): number`

<details><summary>Code</summary>

```ts
distanceTo( v ) {

		return Math.sqrt( this.distanceToSquared( v ) );

	}
```
</details>

##### `distanceToSquared(v: Vector2): number`

<details><summary>Code</summary>

```ts
distanceToSquared( v ) {

		const dx = this.x - v.x, dy = this.y - v.y;
		return dx * dx + dy * dy;

	}
```
</details>

##### `manhattanDistanceTo(v: Vector2): number`

<details><summary>Code</summary>

```ts
manhattanDistanceTo( v ) {

		return Math.abs( this.x - v.x ) + Math.abs( this.y - v.y );

	}
```
</details>

##### `setLength(length: number): Vector2`

<details><summary>Code</summary>

```ts
setLength( length ) {

		return this.normalize().multiplyScalar( length );

	}
```
</details>

##### `lerp(v: Vector2, alpha: number): Vector2`

<details><summary>Code</summary>

```ts
lerp( v, alpha ) {

		this.x += ( v.x - this.x ) * alpha;
		this.y += ( v.y - this.y ) * alpha;

		return this;

	}
```
</details>

##### `lerpVectors(v1: Vector2, v2: Vector2, alpha: number): Vector2`

<details><summary>Code</summary>

```ts
lerpVectors( v1, v2, alpha ) {

		this.x = v1.x + ( v2.x - v1.x ) * alpha;
		this.y = v1.y + ( v2.y - v1.y ) * alpha;

		return this;

	}
```
</details>

##### `equals(v: Vector2): boolean`

<details><summary>Code</summary>

```ts
equals( v ) {

		return ( ( v.x === this.x ) && ( v.y === this.y ) );

	}
```
</details>

##### `fromArray(array: number[], offset: number): Vector2`

<details><summary>Code</summary>

```ts
fromArray( array, offset = 0 ) {

		this.x = array[ offset ];
		this.y = array[ offset + 1 ];

		return this;

	}
```
</details>

##### `toArray(array: number[], offset: number): number[]`

<details><summary>Code</summary>

```ts
toArray( array = [], offset = 0 ) {

		array[ offset ] = this.x;
		array[ offset + 1 ] = this.y;

		return array;

	}
```
</details>

##### `fromBufferAttribute(attribute: BufferAttribute, index: number): Vector2`

<details><summary>Code</summary>

```ts
fromBufferAttribute( attribute, index ) {

		this.x = attribute.getX( index );
		this.y = attribute.getY( index );

		return this;

	}
```
</details>

##### `rotateAround(center: Vector2, angle: number): Vector2`

<details><summary>Code</summary>

```ts
rotateAround( center, angle ) {

		const c = Math.cos( angle ), s = Math.sin( angle );

		const x = this.x - center.x;
		const y = this.y - center.y;

		this.x = x * c - y * s + center.x;
		this.y = x * s + y * c + center.y;

		return this;

	}
```
</details>

##### `random(): Vector2`

<details><summary>Code</summary>

```ts
random() {

		this.x = Math.random();
		this.y = Math.random();

		return this;

	}
```
</details>

##### `[ Symbol.iterator ](): Generator<number, void, unknown>`

<details><summary>Code</summary>

```ts
*[ Symbol.iterator ]() {

		yield this.x;
		yield this.y;

	}
```
</details>


---