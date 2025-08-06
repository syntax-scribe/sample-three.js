[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Vector3.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 74 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 40 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/Vector3.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `clamp` | `./MathUtils.js` |
| `Quaternion` | `./Quaternion.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `x` | `number` | let/var | `this.x` | ✗ |
| `y` | `number` | let/var | `this.y` | ✗ |
| `z` | `number` | let/var | `this.z` | ✗ |
| `e` | `any` | let/var | `m.elements` | ✗ |
| `x` | `number` | let/var | `this.x` | ✗ |
| `y` | `number` | let/var | `this.y` | ✗ |
| `z` | `number` | let/var | `this.z` | ✗ |
| `e` | `any` | let/var | `m.elements` | ✗ |
| `w` | `number` | let/var | `1 / ( e[ 3 ] * x + e[ 7 ] * y + e[ 11 ] * z + e[ 15 ] )` | ✗ |
| `vx` | `number` | let/var | `this.x` | ✗ |
| `vy` | `number` | let/var | `this.y` | ✗ |
| `vz` | `number` | let/var | `this.z` | ✗ |
| `qx` | `number` | let/var | `q.x` | ✗ |
| `qy` | `number` | let/var | `q.y` | ✗ |
| `qz` | `number` | let/var | `q.z` | ✗ |
| `qw` | `number` | let/var | `q.w` | ✗ |
| `tx` | `number` | let/var | `2 * ( qy * vz - qz * vy )` | ✗ |
| `ty` | `number` | let/var | `2 * ( qz * vx - qx * vz )` | ✗ |
| `tz` | `number` | let/var | `2 * ( qx * vy - qy * vx )` | ✗ |
| `x` | `number` | let/var | `this.x` | ✗ |
| `y` | `number` | let/var | `this.y` | ✗ |
| `z` | `number` | let/var | `this.z` | ✗ |
| `e` | `any` | let/var | `m.elements` | ✗ |
| `ax` | `number` | let/var | `a.x` | ✗ |
| `ay` | `number` | let/var | `a.y` | ✗ |
| `az` | `number` | let/var | `a.z` | ✗ |
| `bx` | `number` | let/var | `b.x` | ✗ |
| `by` | `number` | let/var | `b.y` | ✗ |
| `bz` | `number` | let/var | `b.z` | ✗ |
| `scalar` | `number` | let/var | `v.dot( this ) / denominator` | ✗ |
| `theta` | `number` | let/var | `this.dot( v ) / denominator` | ✗ |
| `dx` | `number` | let/var | `this.x - v.x` | ✗ |
| `dy` | `number` | let/var | `this.y - v.y` | ✗ |
| `dz` | `number` | let/var | `this.z - v.z` | ✗ |
| `sinPhiRadius` | `number` | let/var | `Math.sin( phi ) * radius` | ✗ |
| `e` | `any` | let/var | `m.elements` | ✗ |
| `theta` | `number` | let/var | `Math.random() * Math.PI * 2` | ✗ |
| `u` | `number` | let/var | `Math.random() * 2 - 1` | ✗ |
| `_vector` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_quaternion` | `Quaternion` | let/var | `new Quaternion()` | ✗ |


---

## Functions

### `Vector3.set(x: number, y: number, z: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets the vector components.
	 *
	 * @param {number} x - The value of the x component.
	 * @param {number} y - The value of the y component.
	 * @param {number} z - The value of the z component.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`
- **`z`** `number`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
set( x, y, z ) {

		if ( z === undefined ) z = this.z; // sprite.scale.set(x,y)

		this.x = x;
		this.y = y;
		this.z = z;

		return this;

	}
```
</details>

### `Vector3.setScalar(scalar: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets the vector components to the same value.
	 *
	 * @param {number} scalar - The value to set for all vector components.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`scalar`** `number`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
setScalar( scalar ) {

		this.x = scalar;
		this.y = scalar;
		this.z = scalar;

		return this;

	}
```
</details>

### `Vector3.setX(x: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets the vector's x component to the given value
	 *
	 * @param {number} x - The value to set.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`x`** `number`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
setX( x ) {

		this.x = x;

		return this;

	}
```
</details>

### `Vector3.setY(y: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets the vector's y component to the given value
	 *
	 * @param {number} y - The value to set.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`y`** `number`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
setY( y ) {

		this.y = y;

		return this;

	}
```
</details>

### `Vector3.setZ(z: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets the vector's z component to the given value
	 *
	 * @param {number} z - The value to set.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`z`** `number`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
setZ( z ) {

		this.z = z;

		return this;

	}
```
</details>

### `Vector3.setComponent(index: number, value: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Allows to set a vector component with an index.
	 *
	 * @param {number} index - The component index. `0` equals to x, `1` equals to y, `2` equals to z.
	 * @param {number} value - The value to set.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`index`** `number`
- **`value`** `number`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
setComponent( index, value ) {

		switch ( index ) {

			case 0: this.x = value; break;
			case 1: this.y = value; break;
			case 2: this.z = value; break;
			default: throw new Error( 'index is out of range: ' + index );

		}

		return this;

	}
```
</details>

### `Vector3.getComponent(index: number): number`

**JSDoc:**
```typescript
/**
	 * Returns the value of the vector component which matches the given index.
	 *
	 * @param {number} index - The component index. `0` equals to x, `1` equals to y, `2` equals to z.
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
			case 2: return this.z;
			default: throw new Error( 'index is out of range: ' + index );

		}

	}
```
</details>

### `Vector3.clone(): Vector3`

**JSDoc:**
```typescript
/**
	 * Returns a new vector with copied values from this instance.
	 *
	 * @return {Vector3} A clone of this instance.
	 */
```

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor( this.x, this.y, this.z );

	}
```
</details>

### `Vector3.copy(v: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given vector to this instance.
	 *
	 * @param {Vector3} v - The vector to copy.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
copy( v ) {

		this.x = v.x;
		this.y = v.y;
		this.z = v.z;

		return this;

	}
```
</details>

### `Vector3.add(v: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Adds the given vector to this instance.
	 *
	 * @param {Vector3} v - The vector to add.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
add( v ) {

		this.x += v.x;
		this.y += v.y;
		this.z += v.z;

		return this;

	}
```
</details>

### `Vector3.addScalar(s: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Adds the given scalar value to all components of this instance.
	 *
	 * @param {number} s - The scalar to add.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`s`** `number`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
addScalar( s ) {

		this.x += s;
		this.y += s;
		this.z += s;

		return this;

	}
```
</details>

### `Vector3.addVectors(a: Vector3, b: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Adds the given vectors and stores the result in this instance.
	 *
	 * @param {Vector3} a - The first vector.
	 * @param {Vector3} b - The second vector.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`a`** `Vector3`
- **`b`** `Vector3`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
addVectors( a, b ) {

		this.x = a.x + b.x;
		this.y = a.y + b.y;
		this.z = a.z + b.z;

		return this;

	}
```
</details>

### `Vector3.addScaledVector(v: any, s: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Adds the given vector scaled by the given factor to this instance.
	 *
	 * @param {Vector3|Vector4} v - The vector.
	 * @param {number} s - The factor that scales `v`.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `any`
- **`s`** `number`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
addScaledVector( v, s ) {

		this.x += v.x * s;
		this.y += v.y * s;
		this.z += v.z * s;

		return this;

	}
```
</details>

### `Vector3.sub(v: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Subtracts the given vector from this instance.
	 *
	 * @param {Vector3} v - The vector to subtract.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
sub( v ) {

		this.x -= v.x;
		this.y -= v.y;
		this.z -= v.z;

		return this;

	}
```
</details>

### `Vector3.subScalar(s: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Subtracts the given scalar value from all components of this instance.
	 *
	 * @param {number} s - The scalar to subtract.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`s`** `number`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
subScalar( s ) {

		this.x -= s;
		this.y -= s;
		this.z -= s;

		return this;

	}
```
</details>

### `Vector3.subVectors(a: Vector3, b: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Subtracts the given vectors and stores the result in this instance.
	 *
	 * @param {Vector3} a - The first vector.
	 * @param {Vector3} b - The second vector.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`a`** `Vector3`
- **`b`** `Vector3`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
subVectors( a, b ) {

		this.x = a.x - b.x;
		this.y = a.y - b.y;
		this.z = a.z - b.z;

		return this;

	}
```
</details>

### `Vector3.multiply(v: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Multiplies the given vector with this instance.
	 *
	 * @param {Vector3} v - The vector to multiply.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
multiply( v ) {

		this.x *= v.x;
		this.y *= v.y;
		this.z *= v.z;

		return this;

	}
```
</details>

### `Vector3.multiplyScalar(scalar: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Multiplies the given scalar value with all components of this instance.
	 *
	 * @param {number} scalar - The scalar to multiply.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`scalar`** `number`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
multiplyScalar( scalar ) {

		this.x *= scalar;
		this.y *= scalar;
		this.z *= scalar;

		return this;

	}
```
</details>

### `Vector3.multiplyVectors(a: Vector3, b: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Multiplies the given vectors and stores the result in this instance.
	 *
	 * @param {Vector3} a - The first vector.
	 * @param {Vector3} b - The second vector.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`a`** `Vector3`
- **`b`** `Vector3`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
multiplyVectors( a, b ) {

		this.x = a.x * b.x;
		this.y = a.y * b.y;
		this.z = a.z * b.z;

		return this;

	}
```
</details>

### `Vector3.applyEuler(euler: Euler): Vector3`

**JSDoc:**
```typescript
/**
	 * Applies the given Euler rotation to this vector.
	 *
	 * @param {Euler} euler - The Euler angles.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`euler`** `Euler`

**Returns:** `Vector3`

**Calls:**

- `this.applyQuaternion`
- `_quaternion.setFromEuler`

<details><summary>Code</summary>

```typescript
applyEuler( euler ) {

		return this.applyQuaternion( _quaternion.setFromEuler( euler ) );

	}
```
</details>

### `Vector3.applyAxisAngle(axis: Vector3, angle: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Applies a rotation specified by an axis and an angle to this vector.
	 *
	 * @param {Vector3} axis - A normalized vector representing the rotation axis.
	 * @param {number} angle - The angle in radians.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`axis`** `Vector3`
- **`angle`** `number`

**Returns:** `Vector3`

**Calls:**

- `this.applyQuaternion`
- `_quaternion.setFromAxisAngle`

<details><summary>Code</summary>

```typescript
applyAxisAngle( axis, angle ) {

		return this.applyQuaternion( _quaternion.setFromAxisAngle( axis, angle ) );

	}
```
</details>

### `Vector3.applyMatrix3(m: Matrix3): Vector3`

**JSDoc:**
```typescript
/**
	 * Multiplies this vector with the given 3x3 matrix.
	 *
	 * @param {Matrix3} m - The 3x3 matrix.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`m`** `Matrix3`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
applyMatrix3( m ) {

		const x = this.x, y = this.y, z = this.z;
		const e = m.elements;

		this.x = e[ 0 ] * x + e[ 3 ] * y + e[ 6 ] * z;
		this.y = e[ 1 ] * x + e[ 4 ] * y + e[ 7 ] * z;
		this.z = e[ 2 ] * x + e[ 5 ] * y + e[ 8 ] * z;

		return this;

	}
```
</details>

### `Vector3.applyNormalMatrix(m: Matrix3): Vector3`

**JSDoc:**
```typescript
/**
	 * Multiplies this vector by the given normal matrix and normalizes
	 * the result.
	 *
	 * @param {Matrix3} m - The normal matrix.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`m`** `Matrix3`

**Returns:** `Vector3`

**Calls:**

- `this.applyMatrix3( m ).normalize`

<details><summary>Code</summary>

```typescript
applyNormalMatrix( m ) {

		return this.applyMatrix3( m ).normalize();

	}
```
</details>

### `Vector3.applyMatrix4(m: Matrix4): Vector3`

**JSDoc:**
```typescript
/**
	 * Multiplies this vector (with an implicit 1 in the 4th dimension) by m, and
	 * divides by perspective.
	 *
	 * @param {Matrix4} m - The matrix to apply.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`m`** `Matrix4`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
applyMatrix4( m ) {

		const x = this.x, y = this.y, z = this.z;
		const e = m.elements;

		const w = 1 / ( e[ 3 ] * x + e[ 7 ] * y + e[ 11 ] * z + e[ 15 ] );

		this.x = ( e[ 0 ] * x + e[ 4 ] * y + e[ 8 ] * z + e[ 12 ] ) * w;
		this.y = ( e[ 1 ] * x + e[ 5 ] * y + e[ 9 ] * z + e[ 13 ] ) * w;
		this.z = ( e[ 2 ] * x + e[ 6 ] * y + e[ 10 ] * z + e[ 14 ] ) * w;

		return this;

	}
```
</details>

### `Vector3.applyQuaternion(q: Quaternion): Vector3`

**JSDoc:**
```typescript
/**
	 * Applies the given Quaternion to this vector.
	 *
	 * @param {Quaternion} q - The Quaternion.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`q`** `Quaternion`

**Returns:** `Vector3`

**Internal Comments:**
```
// quaternion q is assumed to have unit length (x2)
// t = 2 * cross( q.xyz, v ); (x2)
// v + q.w * t + cross( q.xyz, t ); (x4)
```

<details><summary>Code</summary>

```typescript
applyQuaternion( q ) {

		// quaternion q is assumed to have unit length

		const vx = this.x, vy = this.y, vz = this.z;
		const qx = q.x, qy = q.y, qz = q.z, qw = q.w;

		// t = 2 * cross( q.xyz, v );
		const tx = 2 * ( qy * vz - qz * vy );
		const ty = 2 * ( qz * vx - qx * vz );
		const tz = 2 * ( qx * vy - qy * vx );

		// v + q.w * t + cross( q.xyz, t );
		this.x = vx + qw * tx + qy * tz - qz * ty;
		this.y = vy + qw * ty + qz * tx - qx * tz;
		this.z = vz + qw * tz + qx * ty - qy * tx;

		return this;

	}
```
</details>

### `Vector3.project(camera: Camera): Vector3`

**JSDoc:**
```typescript
/**
	 * Projects this vector from world space into the camera's normalized
	 * device coordinate (NDC) space.
	 *
	 * @param {Camera} camera - The camera.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`camera`** `Camera`

**Returns:** `Vector3`

**Calls:**

- `this.applyMatrix4( camera.matrixWorldInverse ).applyMatrix4`

<details><summary>Code</summary>

```typescript
project( camera ) {

		return this.applyMatrix4( camera.matrixWorldInverse ).applyMatrix4( camera.projectionMatrix );

	}
```
</details>

### `Vector3.unproject(camera: Camera): Vector3`

**JSDoc:**
```typescript
/**
	 * Unprojects this vector from the camera's normalized device coordinate (NDC)
	 * space into world space.
	 *
	 * @param {Camera} camera - The camera.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`camera`** `Camera`

**Returns:** `Vector3`

**Calls:**

- `this.applyMatrix4( camera.projectionMatrixInverse ).applyMatrix4`

<details><summary>Code</summary>

```typescript
unproject( camera ) {

		return this.applyMatrix4( camera.projectionMatrixInverse ).applyMatrix4( camera.matrixWorld );

	}
```
</details>

### `Vector3.transformDirection(m: Matrix4): Vector3`

**JSDoc:**
```typescript
/**
	 * Transforms the direction of this vector by a matrix (the upper left 3 x 3
	 * subset of the given 4x4 matrix and then normalizes the result.
	 *
	 * @param {Matrix4} m - The matrix.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`m`** `Matrix4`

**Returns:** `Vector3`

**Calls:**

- `this.normalize`

**Internal Comments:**
```
// input: THREE.Matrix4 affine matrix (x2)
// vector interpreted as a direction (x2)
```

<details><summary>Code</summary>

```typescript
transformDirection( m ) {

		// input: THREE.Matrix4 affine matrix
		// vector interpreted as a direction

		const x = this.x, y = this.y, z = this.z;
		const e = m.elements;

		this.x = e[ 0 ] * x + e[ 4 ] * y + e[ 8 ] * z;
		this.y = e[ 1 ] * x + e[ 5 ] * y + e[ 9 ] * z;
		this.z = e[ 2 ] * x + e[ 6 ] * y + e[ 10 ] * z;

		return this.normalize();

	}
```
</details>

### `Vector3.divide(v: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Divides this instance by the given vector.
	 *
	 * @param {Vector3} v - The vector to divide.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
divide( v ) {

		this.x /= v.x;
		this.y /= v.y;
		this.z /= v.z;

		return this;

	}
```
</details>

### `Vector3.divideScalar(scalar: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Divides this vector by the given scalar.
	 *
	 * @param {number} scalar - The scalar to divide.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`scalar`** `number`

**Returns:** `Vector3`

**Calls:**

- `this.multiplyScalar`

<details><summary>Code</summary>

```typescript
divideScalar( scalar ) {

		return this.multiplyScalar( 1 / scalar );

	}
```
</details>

### `Vector3.min(v: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * If this vector's x, y or z value is greater than the given vector's x, y or z
	 * value, replace that value with the corresponding min value.
	 *
	 * @param {Vector3} v - The vector.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Math.min`

<details><summary>Code</summary>

```typescript
min( v ) {

		this.x = Math.min( this.x, v.x );
		this.y = Math.min( this.y, v.y );
		this.z = Math.min( this.z, v.z );

		return this;

	}
```
</details>

### `Vector3.max(v: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * If this vector's x, y or z value is less than the given vector's x, y or z
	 * value, replace that value with the corresponding max value.
	 *
	 * @param {Vector3} v - The vector.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `Math.max`

<details><summary>Code</summary>

```typescript
max( v ) {

		this.x = Math.max( this.x, v.x );
		this.y = Math.max( this.y, v.y );
		this.z = Math.max( this.z, v.z );

		return this;

	}
```
</details>

### `Vector3.clamp(min: Vector3, max: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * If this vector's x, y or z value is greater than the max vector's x, y or z
	 * value, it is replaced by the corresponding value.
	 * If this vector's x, y or z value is less than the min vector's x, y or z value,
	 * it is replaced by the corresponding value.
	 *
	 * @param {Vector3} min - The minimum x, y and z values.
	 * @param {Vector3} max - The maximum x, y and z values in the desired range.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`min`** `Vector3`
- **`max`** `Vector3`

**Returns:** `Vector3`

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
		this.z = clamp( this.z, min.z, max.z );

		return this;

	}
```
</details>

### `Vector3.clampScalar(minVal: number, maxVal: number): Vector3`

**JSDoc:**
```typescript
/**
	 * If this vector's x, y or z values are greater than the max value, they are
	 * replaced by the max value.
	 * If this vector's x, y or z values are less than the min value, they are
	 * replaced by the min value.
	 *
	 * @param {number} minVal - The minimum value the components will be clamped to.
	 * @param {number} maxVal - The maximum value the components will be clamped to.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`minVal`** `number`
- **`maxVal`** `number`

**Returns:** `Vector3`

**Calls:**

- `clamp (from ./MathUtils.js)`

<details><summary>Code</summary>

```typescript
clampScalar( minVal, maxVal ) {

		this.x = clamp( this.x, minVal, maxVal );
		this.y = clamp( this.y, minVal, maxVal );
		this.z = clamp( this.z, minVal, maxVal );

		return this;

	}
```
</details>

### `Vector3.clampLength(min: number, max: number): Vector3`

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
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`min`** `number`
- **`max`** `number`

**Returns:** `Vector3`

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

### `Vector3.floor(): Vector3`

**JSDoc:**
```typescript
/**
	 * The components of this vector are rounded down to the nearest integer value.
	 *
	 * @return {Vector3} A reference to this vector.
	 */
```

**Returns:** `Vector3`

**Calls:**

- `Math.floor`

<details><summary>Code</summary>

```typescript
floor() {

		this.x = Math.floor( this.x );
		this.y = Math.floor( this.y );
		this.z = Math.floor( this.z );

		return this;

	}
```
</details>

### `Vector3.ceil(): Vector3`

**JSDoc:**
```typescript
/**
	 * The components of this vector are rounded up to the nearest integer value.
	 *
	 * @return {Vector3} A reference to this vector.
	 */
```

**Returns:** `Vector3`

**Calls:**

- `Math.ceil`

<details><summary>Code</summary>

```typescript
ceil() {

		this.x = Math.ceil( this.x );
		this.y = Math.ceil( this.y );
		this.z = Math.ceil( this.z );

		return this;

	}
```
</details>

### `Vector3.round(): Vector3`

**JSDoc:**
```typescript
/**
	 * The components of this vector are rounded to the nearest integer value
	 *
	 * @return {Vector3} A reference to this vector.
	 */
```

**Returns:** `Vector3`

**Calls:**

- `Math.round`

<details><summary>Code</summary>

```typescript
round() {

		this.x = Math.round( this.x );
		this.y = Math.round( this.y );
		this.z = Math.round( this.z );

		return this;

	}
```
</details>

### `Vector3.roundToZero(): Vector3`

**JSDoc:**
```typescript
/**
	 * The components of this vector are rounded towards zero (up if negative,
	 * down if positive) to an integer value.
	 *
	 * @return {Vector3} A reference to this vector.
	 */
```

**Returns:** `Vector3`

**Calls:**

- `Math.trunc`

<details><summary>Code</summary>

```typescript
roundToZero() {

		this.x = Math.trunc( this.x );
		this.y = Math.trunc( this.y );
		this.z = Math.trunc( this.z );

		return this;

	}
```
</details>

### `Vector3.negate(): Vector3`

**JSDoc:**
```typescript
/**
	 * Inverts this vector - i.e. sets x = -x, y = -y and z = -z.
	 *
	 * @return {Vector3} A reference to this vector.
	 */
```

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
negate() {

		this.x = - this.x;
		this.y = - this.y;
		this.z = - this.z;

		return this;

	}
```
</details>

### `Vector3.dot(v: Vector3): number`

**JSDoc:**
```typescript
/**
	 * Calculates the dot product of the given vector with this instance.
	 *
	 * @param {Vector3} v - The vector to compute the dot product with.
	 * @return {number} The result of the dot product.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
dot( v ) {

		return this.x * v.x + this.y * v.y + this.z * v.z;

	}
```
</details>

### `Vector3.lengthSq(): number`

**JSDoc:**
```typescript
/**
	 * Computes the square of the Euclidean length (straight-line length) from
	 * (0, 0, 0) to (x, y, z). If you are comparing the lengths of vectors, you should
	 * compare the length squared instead as it is slightly more efficient to calculate.
	 *
	 * @return {number} The square length of this vector.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
lengthSq() {

		return this.x * this.x + this.y * this.y + this.z * this.z;

	}
```
</details>

### `Vector3.length(): number`

**JSDoc:**
```typescript
/**
	 * Computes the  Euclidean length (straight-line length) from (0, 0, 0) to (x, y, z).
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

		return Math.sqrt( this.x * this.x + this.y * this.y + this.z * this.z );

	}
```
</details>

### `Vector3.manhattanLength(): number`

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

		return Math.abs( this.x ) + Math.abs( this.y ) + Math.abs( this.z );

	}
```
</details>

### `Vector3.normalize(): Vector3`

**JSDoc:**
```typescript
/**
	 * Converts this vector to a unit vector - that is, sets it equal to a vector
	 * with the same direction as this one, but with a vector length of `1`.
	 *
	 * @return {Vector3} A reference to this vector.
	 */
```

**Returns:** `Vector3`

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

### `Vector3.setLength(length: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets this vector to a vector with the same direction as this one, but
	 * with the specified length.
	 *
	 * @param {number} length - The new length of this vector.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`length`** `number`

**Returns:** `Vector3`

**Calls:**

- `this.normalize().multiplyScalar`

<details><summary>Code</summary>

```typescript
setLength( length ) {

		return this.normalize().multiplyScalar( length );

	}
```
</details>

### `Vector3.lerp(v: Vector3, alpha: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Linearly interpolates between the given vector and this instance, where
	 * alpha is the percent distance along the line - alpha = 0 will be this
	 * vector, and alpha = 1 will be the given one.
	 *
	 * @param {Vector3} v - The vector to interpolate towards.
	 * @param {number} alpha - The interpolation factor, typically in the closed interval `[0, 1]`.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector3`
- **`alpha`** `number`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
lerp( v, alpha ) {

		this.x += ( v.x - this.x ) * alpha;
		this.y += ( v.y - this.y ) * alpha;
		this.z += ( v.z - this.z ) * alpha;

		return this;

	}
```
</details>

### `Vector3.lerpVectors(v1: Vector3, v2: Vector3, alpha: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Linearly interpolates between the given vectors, where alpha is the percent
	 * distance along the line - alpha = 0 will be first vector, and alpha = 1 will
	 * be the second one. The result is stored in this instance.
	 *
	 * @param {Vector3} v1 - The first vector.
	 * @param {Vector3} v2 - The second vector.
	 * @param {number} alpha - The interpolation factor, typically in the closed interval `[0, 1]`.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`v1`** `Vector3`
- **`v2`** `Vector3`
- **`alpha`** `number`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
lerpVectors( v1, v2, alpha ) {

		this.x = v1.x + ( v2.x - v1.x ) * alpha;
		this.y = v1.y + ( v2.y - v1.y ) * alpha;
		this.z = v1.z + ( v2.z - v1.z ) * alpha;

		return this;

	}
```
</details>

### `Vector3.cross(v: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Calculates the cross product of the given vector with this instance.
	 *
	 * @param {Vector3} v - The vector to compute the cross product with.
	 * @return {Vector3} The result of the cross product.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `this.crossVectors`

<details><summary>Code</summary>

```typescript
cross( v ) {

		return this.crossVectors( this, v );

	}
```
</details>

### `Vector3.crossVectors(a: Vector3, b: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Calculates the cross product of the given vectors and stores the result
	 * in this instance.
	 *
	 * @param {Vector3} a - The first vector.
	 * @param {Vector3} b - The second vector.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`a`** `Vector3`
- **`b`** `Vector3`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
crossVectors( a, b ) {

		const ax = a.x, ay = a.y, az = a.z;
		const bx = b.x, by = b.y, bz = b.z;

		this.x = ay * bz - az * by;
		this.y = az * bx - ax * bz;
		this.z = ax * by - ay * bx;

		return this;

	}
```
</details>

### `Vector3.projectOnVector(v: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Projects this vector onto the given one.
	 *
	 * @param {Vector3} v - The vector to project to.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `v.lengthSq`
- `this.set`
- `v.dot`
- `this.copy( v ).multiplyScalar`

<details><summary>Code</summary>

```typescript
projectOnVector( v ) {

		const denominator = v.lengthSq();

		if ( denominator === 0 ) return this.set( 0, 0, 0 );

		const scalar = v.dot( this ) / denominator;

		return this.copy( v ).multiplyScalar( scalar );

	}
```
</details>

### `Vector3.projectOnPlane(planeNormal: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Projects this vector onto a plane by subtracting this
	 * vector projected onto the plane's normal from this vector.
	 *
	 * @param {Vector3} planeNormal - The plane normal.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`planeNormal`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `_vector.copy( this ).projectOnVector`
- `this.sub`

<details><summary>Code</summary>

```typescript
projectOnPlane( planeNormal ) {

		_vector.copy( this ).projectOnVector( planeNormal );

		return this.sub( _vector );

	}
```
</details>

### `Vector3.reflect(normal: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Reflects this vector off a plane orthogonal to the given normal vector.
	 *
	 * @param {Vector3} normal - The (normalized) normal vector.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`normal`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `this.sub`
- `_vector.copy( normal ).multiplyScalar`
- `this.dot`

<details><summary>Code</summary>

```typescript
reflect( normal ) {

		return this.sub( _vector.copy( normal ).multiplyScalar( 2 * this.dot( normal ) ) );

	}
```
</details>

### `Vector3.angleTo(v: Vector3): number`

**JSDoc:**
```typescript
/**
	 * Returns the angle between the given vector and this instance in radians.
	 *
	 * @param {Vector3} v - The vector to compute the angle with.
	 * @return {number} The angle in radians.
	 */
```

**Parameters:**

- **`v`** `Vector3`

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

### `Vector3.distanceTo(v: Vector3): number`

**JSDoc:**
```typescript
/**
	 * Computes the distance from the given vector to this instance.
	 *
	 * @param {Vector3} v - The vector to compute the distance to.
	 * @return {number} The distance.
	 */
```

**Parameters:**

- **`v`** `Vector3`

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

### `Vector3.distanceToSquared(v: Vector3): number`

**JSDoc:**
```typescript
/**
	 * Computes the squared distance from the given vector to this instance.
	 * If you are just comparing the distance with another distance, you should compare
	 * the distance squared instead as it is slightly more efficient to calculate.
	 *
	 * @param {Vector3} v - The vector to compute the squared distance to.
	 * @return {number} The squared distance.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
distanceToSquared( v ) {

		const dx = this.x - v.x, dy = this.y - v.y, dz = this.z - v.z;

		return dx * dx + dy * dy + dz * dz;

	}
```
</details>

### `Vector3.manhattanDistanceTo(v: Vector3): number`

**JSDoc:**
```typescript
/**
	 * Computes the Manhattan distance from the given vector to this instance.
	 *
	 * @param {Vector3} v - The vector to compute the Manhattan distance to.
	 * @return {number} The Manhattan distance.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `number`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
manhattanDistanceTo( v ) {

		return Math.abs( this.x - v.x ) + Math.abs( this.y - v.y ) + Math.abs( this.z - v.z );

	}
```
</details>

### `Vector3.setFromSpherical(s: Spherical): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets the vector components from the given spherical coordinates.
	 *
	 * @param {Spherical} s - The spherical coordinates.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`s`** `Spherical`

**Returns:** `Vector3`

**Calls:**

- `this.setFromSphericalCoords`

<details><summary>Code</summary>

```typescript
setFromSpherical( s ) {

		return this.setFromSphericalCoords( s.radius, s.phi, s.theta );

	}
```
</details>

### `Vector3.setFromSphericalCoords(radius: number, phi: number, theta: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets the vector components from the given spherical coordinates.
	 *
	 * @param {number} radius - The radius.
	 * @param {number} phi - The phi angle in radians.
	 * @param {number} theta - The theta angle in radians.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`radius`** `number`
- **`phi`** `number`
- **`theta`** `number`

**Returns:** `Vector3`

**Calls:**

- `Math.sin`
- `Math.cos`

<details><summary>Code</summary>

```typescript
setFromSphericalCoords( radius, phi, theta ) {

		const sinPhiRadius = Math.sin( phi ) * radius;

		this.x = sinPhiRadius * Math.sin( theta );
		this.y = Math.cos( phi ) * radius;
		this.z = sinPhiRadius * Math.cos( theta );

		return this;

	}
```
</details>

### `Vector3.setFromCylindrical(c: Cylindrical): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets the vector components from the given cylindrical coordinates.
	 *
	 * @param {Cylindrical} c - The cylindrical coordinates.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`c`** `Cylindrical`

**Returns:** `Vector3`

**Calls:**

- `this.setFromCylindricalCoords`

<details><summary>Code</summary>

```typescript
setFromCylindrical( c ) {

		return this.setFromCylindricalCoords( c.radius, c.theta, c.y );

	}
```
</details>

### `Vector3.setFromCylindricalCoords(radius: number, theta: number, y: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets the vector components from the given cylindrical coordinates.
	 *
	 * @param {number} radius - The radius.
	 * @param {number} theta - The theta angle in radians.
	 * @param {number} y - The y value.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`radius`** `number`
- **`theta`** `number`
- **`y`** `number`

**Returns:** `Vector3`

**Calls:**

- `Math.sin`
- `Math.cos`

<details><summary>Code</summary>

```typescript
setFromCylindricalCoords( radius, theta, y ) {

		this.x = radius * Math.sin( theta );
		this.y = y;
		this.z = radius * Math.cos( theta );

		return this;

	}
```
</details>

### `Vector3.setFromMatrixPosition(m: Matrix4): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets the vector components to the position elements of the
	 * given transformation matrix.
	 *
	 * @param {Matrix4} m - The 4x4 matrix.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`m`** `Matrix4`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
setFromMatrixPosition( m ) {

		const e = m.elements;

		this.x = e[ 12 ];
		this.y = e[ 13 ];
		this.z = e[ 14 ];

		return this;

	}
```
</details>

### `Vector3.setFromMatrixScale(m: Matrix4): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets the vector components to the scale elements of the
	 * given transformation matrix.
	 *
	 * @param {Matrix4} m - The 4x4 matrix.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`m`** `Matrix4`

**Returns:** `Vector3`

**Calls:**

- `this.setFromMatrixColumn( m, 0 ).length`
- `this.setFromMatrixColumn( m, 1 ).length`
- `this.setFromMatrixColumn( m, 2 ).length`

<details><summary>Code</summary>

```typescript
setFromMatrixScale( m ) {

		const sx = this.setFromMatrixColumn( m, 0 ).length();
		const sy = this.setFromMatrixColumn( m, 1 ).length();
		const sz = this.setFromMatrixColumn( m, 2 ).length();

		this.x = sx;
		this.y = sy;
		this.z = sz;

		return this;

	}
```
</details>

### `Vector3.setFromMatrixColumn(m: Matrix4, index: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets the vector components from the specified matrix column.
	 *
	 * @param {Matrix4} m - The 4x4 matrix.
	 * @param {number} index - The column index.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`m`** `Matrix4`
- **`index`** `number`

**Returns:** `Vector3`

**Calls:**

- `this.fromArray`

<details><summary>Code</summary>

```typescript
setFromMatrixColumn( m, index ) {

		return this.fromArray( m.elements, index * 4 );

	}
```
</details>

### `Vector3.setFromMatrix3Column(m: Matrix3, index: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets the vector components from the specified matrix column.
	 *
	 * @param {Matrix3} m - The 3x3 matrix.
	 * @param {number} index - The column index.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`m`** `Matrix3`
- **`index`** `number`

**Returns:** `Vector3`

**Calls:**

- `this.fromArray`

<details><summary>Code</summary>

```typescript
setFromMatrix3Column( m, index ) {

		return this.fromArray( m.elements, index * 3 );

	}
```
</details>

### `Vector3.setFromEuler(e: Euler): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets the vector components from the given Euler angles.
	 *
	 * @param {Euler} e - The Euler angles to set.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`e`** `Euler`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
setFromEuler( e ) {

		this.x = e._x;
		this.y = e._y;
		this.z = e._z;

		return this;

	}
```
</details>

### `Vector3.setFromColor(c: Color): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets the vector components from the RGB components of the
	 * given color.
	 *
	 * @param {Color} c - The color to set.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`c`** `Color`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
setFromColor( c ) {

		this.x = c.r;
		this.y = c.g;
		this.z = c.b;

		return this;

	}
```
</details>

### `Vector3.equals(v: Vector3): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this vector is equal with the given one.
	 *
	 * @param {Vector3} v - The vector to test for equality.
	 * @return {boolean} Whether this vector is equal with the given one.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
equals( v ) {

		return ( ( v.x === this.x ) && ( v.y === this.y ) && ( v.z === this.z ) );

	}
```
</details>

### `Vector3.fromArray(array: number[], offset: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets this vector's x value to be `array[ offset ]`, y value to be `array[ offset + 1 ]`
	 * and z value to be `array[ offset + 2 ]`.
	 *
	 * @param {Array<number>} array - An array holding the vector component values.
	 * @param {number} [offset=0] - The offset into the array.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`array`** `number[]`
- **`offset`** `number`

**Returns:** `Vector3`

<details><summary>Code</summary>

```typescript
fromArray( array, offset = 0 ) {

		this.x = array[ offset ];
		this.y = array[ offset + 1 ];
		this.z = array[ offset + 2 ];

		return this;

	}
```
</details>

### `Vector3.toArray(array: number[], offset: number): number[]`

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
		array[ offset + 2 ] = this.z;

		return array;

	}
```
</details>

### `Vector3.fromBufferAttribute(attribute: BufferAttribute, index: number): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets the components of this vector from the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute holding vector data.
	 * @param {number} index - The index into the attribute.
	 * @return {Vector3} A reference to this vector.
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`
- **`index`** `number`

**Returns:** `Vector3`

**Calls:**

- `attribute.getX`
- `attribute.getY`
- `attribute.getZ`

<details><summary>Code</summary>

```typescript
fromBufferAttribute( attribute, index ) {

		this.x = attribute.getX( index );
		this.y = attribute.getY( index );
		this.z = attribute.getZ( index );

		return this;

	}
```
</details>

### `Vector3.random(): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets each component of this vector to a pseudo-random value between `0` and
	 * `1`, excluding `1`.
	 *
	 * @return {Vector3} A reference to this vector.
	 */
```

**Returns:** `Vector3`

**Calls:**

- `Math.random`

<details><summary>Code</summary>

```typescript
random() {

		this.x = Math.random();
		this.y = Math.random();
		this.z = Math.random();

		return this;

	}
```
</details>

### `Vector3.randomDirection(): Vector3`

**JSDoc:**
```typescript
/**
	 * Sets this vector to a uniformly random point on a unit sphere.
	 *
	 * @return {Vector3} A reference to this vector.
	 */
```

**Returns:** `Vector3`

**Calls:**

- `Math.random`
- `Math.sqrt`
- `Math.cos`
- `Math.sin`

**Internal Comments:**
```
// https://mathworld.wolfram.com/SpherePointPicking.html (x2)
```

<details><summary>Code</summary>

```typescript
randomDirection() {

		// https://mathworld.wolfram.com/SpherePointPicking.html

		const theta = Math.random() * Math.PI * 2;
		const u = Math.random() * 2 - 1;
		const c = Math.sqrt( 1 - u * u );

		this.x = c * Math.cos( theta );
		this.y = u;
		this.z = c * Math.sin( theta );

		return this;

	}
```
</details>

### `Vector3.[ Symbol.iterator ](): Generator<number, void, unknown>`

**Returns:** `Generator<number, void, unknown>`

<details><summary>Code</summary>

```typescript
*[ Symbol.iterator ]() {

		yield this.x;
		yield this.y;
		yield this.z;

	}
```
</details>


---

## Classes

### `Vector3`

<details><summary>Class Code</summary>

```ts
class Vector3 {

	/**
	 * Constructs a new 3D vector.
	 *
	 * @param {number} [x=0] - The x value of this vector.
	 * @param {number} [y=0] - The y value of this vector.
	 * @param {number} [z=0] - The z value of this vector.
	 */
	constructor( x = 0, y = 0, z = 0 ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		Vector3.prototype.isVector3 = true;

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

		/**
		 * The z value of this vector.
		 *
		 * @type {number}
		 */
		this.z = z;

	}

	/**
	 * Sets the vector components.
	 *
	 * @param {number} x - The value of the x component.
	 * @param {number} y - The value of the y component.
	 * @param {number} z - The value of the z component.
	 * @return {Vector3} A reference to this vector.
	 */
	set( x, y, z ) {

		if ( z === undefined ) z = this.z; // sprite.scale.set(x,y)

		this.x = x;
		this.y = y;
		this.z = z;

		return this;

	}

	/**
	 * Sets the vector components to the same value.
	 *
	 * @param {number} scalar - The value to set for all vector components.
	 * @return {Vector3} A reference to this vector.
	 */
	setScalar( scalar ) {

		this.x = scalar;
		this.y = scalar;
		this.z = scalar;

		return this;

	}

	/**
	 * Sets the vector's x component to the given value
	 *
	 * @param {number} x - The value to set.
	 * @return {Vector3} A reference to this vector.
	 */
	setX( x ) {

		this.x = x;

		return this;

	}

	/**
	 * Sets the vector's y component to the given value
	 *
	 * @param {number} y - The value to set.
	 * @return {Vector3} A reference to this vector.
	 */
	setY( y ) {

		this.y = y;

		return this;

	}

	/**
	 * Sets the vector's z component to the given value
	 *
	 * @param {number} z - The value to set.
	 * @return {Vector3} A reference to this vector.
	 */
	setZ( z ) {

		this.z = z;

		return this;

	}

	/**
	 * Allows to set a vector component with an index.
	 *
	 * @param {number} index - The component index. `0` equals to x, `1` equals to y, `2` equals to z.
	 * @param {number} value - The value to set.
	 * @return {Vector3} A reference to this vector.
	 */
	setComponent( index, value ) {

		switch ( index ) {

			case 0: this.x = value; break;
			case 1: this.y = value; break;
			case 2: this.z = value; break;
			default: throw new Error( 'index is out of range: ' + index );

		}

		return this;

	}

	/**
	 * Returns the value of the vector component which matches the given index.
	 *
	 * @param {number} index - The component index. `0` equals to x, `1` equals to y, `2` equals to z.
	 * @return {number} A vector component value.
	 */
	getComponent( index ) {

		switch ( index ) {

			case 0: return this.x;
			case 1: return this.y;
			case 2: return this.z;
			default: throw new Error( 'index is out of range: ' + index );

		}

	}

	/**
	 * Returns a new vector with copied values from this instance.
	 *
	 * @return {Vector3} A clone of this instance.
	 */
	clone() {

		return new this.constructor( this.x, this.y, this.z );

	}

	/**
	 * Copies the values of the given vector to this instance.
	 *
	 * @param {Vector3} v - The vector to copy.
	 * @return {Vector3} A reference to this vector.
	 */
	copy( v ) {

		this.x = v.x;
		this.y = v.y;
		this.z = v.z;

		return this;

	}

	/**
	 * Adds the given vector to this instance.
	 *
	 * @param {Vector3} v - The vector to add.
	 * @return {Vector3} A reference to this vector.
	 */
	add( v ) {

		this.x += v.x;
		this.y += v.y;
		this.z += v.z;

		return this;

	}

	/**
	 * Adds the given scalar value to all components of this instance.
	 *
	 * @param {number} s - The scalar to add.
	 * @return {Vector3} A reference to this vector.
	 */
	addScalar( s ) {

		this.x += s;
		this.y += s;
		this.z += s;

		return this;

	}

	/**
	 * Adds the given vectors and stores the result in this instance.
	 *
	 * @param {Vector3} a - The first vector.
	 * @param {Vector3} b - The second vector.
	 * @return {Vector3} A reference to this vector.
	 */
	addVectors( a, b ) {

		this.x = a.x + b.x;
		this.y = a.y + b.y;
		this.z = a.z + b.z;

		return this;

	}

	/**
	 * Adds the given vector scaled by the given factor to this instance.
	 *
	 * @param {Vector3|Vector4} v - The vector.
	 * @param {number} s - The factor that scales `v`.
	 * @return {Vector3} A reference to this vector.
	 */
	addScaledVector( v, s ) {

		this.x += v.x * s;
		this.y += v.y * s;
		this.z += v.z * s;

		return this;

	}

	/**
	 * Subtracts the given vector from this instance.
	 *
	 * @param {Vector3} v - The vector to subtract.
	 * @return {Vector3} A reference to this vector.
	 */
	sub( v ) {

		this.x -= v.x;
		this.y -= v.y;
		this.z -= v.z;

		return this;

	}

	/**
	 * Subtracts the given scalar value from all components of this instance.
	 *
	 * @param {number} s - The scalar to subtract.
	 * @return {Vector3} A reference to this vector.
	 */
	subScalar( s ) {

		this.x -= s;
		this.y -= s;
		this.z -= s;

		return this;

	}

	/**
	 * Subtracts the given vectors and stores the result in this instance.
	 *
	 * @param {Vector3} a - The first vector.
	 * @param {Vector3} b - The second vector.
	 * @return {Vector3} A reference to this vector.
	 */
	subVectors( a, b ) {

		this.x = a.x - b.x;
		this.y = a.y - b.y;
		this.z = a.z - b.z;

		return this;

	}

	/**
	 * Multiplies the given vector with this instance.
	 *
	 * @param {Vector3} v - The vector to multiply.
	 * @return {Vector3} A reference to this vector.
	 */
	multiply( v ) {

		this.x *= v.x;
		this.y *= v.y;
		this.z *= v.z;

		return this;

	}

	/**
	 * Multiplies the given scalar value with all components of this instance.
	 *
	 * @param {number} scalar - The scalar to multiply.
	 * @return {Vector3} A reference to this vector.
	 */
	multiplyScalar( scalar ) {

		this.x *= scalar;
		this.y *= scalar;
		this.z *= scalar;

		return this;

	}

	/**
	 * Multiplies the given vectors and stores the result in this instance.
	 *
	 * @param {Vector3} a - The first vector.
	 * @param {Vector3} b - The second vector.
	 * @return {Vector3} A reference to this vector.
	 */
	multiplyVectors( a, b ) {

		this.x = a.x * b.x;
		this.y = a.y * b.y;
		this.z = a.z * b.z;

		return this;

	}

	/**
	 * Applies the given Euler rotation to this vector.
	 *
	 * @param {Euler} euler - The Euler angles.
	 * @return {Vector3} A reference to this vector.
	 */
	applyEuler( euler ) {

		return this.applyQuaternion( _quaternion.setFromEuler( euler ) );

	}

	/**
	 * Applies a rotation specified by an axis and an angle to this vector.
	 *
	 * @param {Vector3} axis - A normalized vector representing the rotation axis.
	 * @param {number} angle - The angle in radians.
	 * @return {Vector3} A reference to this vector.
	 */
	applyAxisAngle( axis, angle ) {

		return this.applyQuaternion( _quaternion.setFromAxisAngle( axis, angle ) );

	}

	/**
	 * Multiplies this vector with the given 3x3 matrix.
	 *
	 * @param {Matrix3} m - The 3x3 matrix.
	 * @return {Vector3} A reference to this vector.
	 */
	applyMatrix3( m ) {

		const x = this.x, y = this.y, z = this.z;
		const e = m.elements;

		this.x = e[ 0 ] * x + e[ 3 ] * y + e[ 6 ] * z;
		this.y = e[ 1 ] * x + e[ 4 ] * y + e[ 7 ] * z;
		this.z = e[ 2 ] * x + e[ 5 ] * y + e[ 8 ] * z;

		return this;

	}

	/**
	 * Multiplies this vector by the given normal matrix and normalizes
	 * the result.
	 *
	 * @param {Matrix3} m - The normal matrix.
	 * @return {Vector3} A reference to this vector.
	 */
	applyNormalMatrix( m ) {

		return this.applyMatrix3( m ).normalize();

	}

	/**
	 * Multiplies this vector (with an implicit 1 in the 4th dimension) by m, and
	 * divides by perspective.
	 *
	 * @param {Matrix4} m - The matrix to apply.
	 * @return {Vector3} A reference to this vector.
	 */
	applyMatrix4( m ) {

		const x = this.x, y = this.y, z = this.z;
		const e = m.elements;

		const w = 1 / ( e[ 3 ] * x + e[ 7 ] * y + e[ 11 ] * z + e[ 15 ] );

		this.x = ( e[ 0 ] * x + e[ 4 ] * y + e[ 8 ] * z + e[ 12 ] ) * w;
		this.y = ( e[ 1 ] * x + e[ 5 ] * y + e[ 9 ] * z + e[ 13 ] ) * w;
		this.z = ( e[ 2 ] * x + e[ 6 ] * y + e[ 10 ] * z + e[ 14 ] ) * w;

		return this;

	}

	/**
	 * Applies the given Quaternion to this vector.
	 *
	 * @param {Quaternion} q - The Quaternion.
	 * @return {Vector3} A reference to this vector.
	 */
	applyQuaternion( q ) {

		// quaternion q is assumed to have unit length

		const vx = this.x, vy = this.y, vz = this.z;
		const qx = q.x, qy = q.y, qz = q.z, qw = q.w;

		// t = 2 * cross( q.xyz, v );
		const tx = 2 * ( qy * vz - qz * vy );
		const ty = 2 * ( qz * vx - qx * vz );
		const tz = 2 * ( qx * vy - qy * vx );

		// v + q.w * t + cross( q.xyz, t );
		this.x = vx + qw * tx + qy * tz - qz * ty;
		this.y = vy + qw * ty + qz * tx - qx * tz;
		this.z = vz + qw * tz + qx * ty - qy * tx;

		return this;

	}

	/**
	 * Projects this vector from world space into the camera's normalized
	 * device coordinate (NDC) space.
	 *
	 * @param {Camera} camera - The camera.
	 * @return {Vector3} A reference to this vector.
	 */
	project( camera ) {

		return this.applyMatrix4( camera.matrixWorldInverse ).applyMatrix4( camera.projectionMatrix );

	}

	/**
	 * Unprojects this vector from the camera's normalized device coordinate (NDC)
	 * space into world space.
	 *
	 * @param {Camera} camera - The camera.
	 * @return {Vector3} A reference to this vector.
	 */
	unproject( camera ) {

		return this.applyMatrix4( camera.projectionMatrixInverse ).applyMatrix4( camera.matrixWorld );

	}

	/**
	 * Transforms the direction of this vector by a matrix (the upper left 3 x 3
	 * subset of the given 4x4 matrix and then normalizes the result.
	 *
	 * @param {Matrix4} m - The matrix.
	 * @return {Vector3} A reference to this vector.
	 */
	transformDirection( m ) {

		// input: THREE.Matrix4 affine matrix
		// vector interpreted as a direction

		const x = this.x, y = this.y, z = this.z;
		const e = m.elements;

		this.x = e[ 0 ] * x + e[ 4 ] * y + e[ 8 ] * z;
		this.y = e[ 1 ] * x + e[ 5 ] * y + e[ 9 ] * z;
		this.z = e[ 2 ] * x + e[ 6 ] * y + e[ 10 ] * z;

		return this.normalize();

	}

	/**
	 * Divides this instance by the given vector.
	 *
	 * @param {Vector3} v - The vector to divide.
	 * @return {Vector3} A reference to this vector.
	 */
	divide( v ) {

		this.x /= v.x;
		this.y /= v.y;
		this.z /= v.z;

		return this;

	}

	/**
	 * Divides this vector by the given scalar.
	 *
	 * @param {number} scalar - The scalar to divide.
	 * @return {Vector3} A reference to this vector.
	 */
	divideScalar( scalar ) {

		return this.multiplyScalar( 1 / scalar );

	}

	/**
	 * If this vector's x, y or z value is greater than the given vector's x, y or z
	 * value, replace that value with the corresponding min value.
	 *
	 * @param {Vector3} v - The vector.
	 * @return {Vector3} A reference to this vector.
	 */
	min( v ) {

		this.x = Math.min( this.x, v.x );
		this.y = Math.min( this.y, v.y );
		this.z = Math.min( this.z, v.z );

		return this;

	}

	/**
	 * If this vector's x, y or z value is less than the given vector's x, y or z
	 * value, replace that value with the corresponding max value.
	 *
	 * @param {Vector3} v - The vector.
	 * @return {Vector3} A reference to this vector.
	 */
	max( v ) {

		this.x = Math.max( this.x, v.x );
		this.y = Math.max( this.y, v.y );
		this.z = Math.max( this.z, v.z );

		return this;

	}

	/**
	 * If this vector's x, y or z value is greater than the max vector's x, y or z
	 * value, it is replaced by the corresponding value.
	 * If this vector's x, y or z value is less than the min vector's x, y or z value,
	 * it is replaced by the corresponding value.
	 *
	 * @param {Vector3} min - The minimum x, y and z values.
	 * @param {Vector3} max - The maximum x, y and z values in the desired range.
	 * @return {Vector3} A reference to this vector.
	 */
	clamp( min, max ) {

		// assumes min < max, componentwise

		this.x = clamp( this.x, min.x, max.x );
		this.y = clamp( this.y, min.y, max.y );
		this.z = clamp( this.z, min.z, max.z );

		return this;

	}

	/**
	 * If this vector's x, y or z values are greater than the max value, they are
	 * replaced by the max value.
	 * If this vector's x, y or z values are less than the min value, they are
	 * replaced by the min value.
	 *
	 * @param {number} minVal - The minimum value the components will be clamped to.
	 * @param {number} maxVal - The maximum value the components will be clamped to.
	 * @return {Vector3} A reference to this vector.
	 */
	clampScalar( minVal, maxVal ) {

		this.x = clamp( this.x, minVal, maxVal );
		this.y = clamp( this.y, minVal, maxVal );
		this.z = clamp( this.z, minVal, maxVal );

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
	 * @return {Vector3} A reference to this vector.
	 */
	clampLength( min, max ) {

		const length = this.length();

		return this.divideScalar( length || 1 ).multiplyScalar( clamp( length, min, max ) );

	}

	/**
	 * The components of this vector are rounded down to the nearest integer value.
	 *
	 * @return {Vector3} A reference to this vector.
	 */
	floor() {

		this.x = Math.floor( this.x );
		this.y = Math.floor( this.y );
		this.z = Math.floor( this.z );

		return this;

	}

	/**
	 * The components of this vector are rounded up to the nearest integer value.
	 *
	 * @return {Vector3} A reference to this vector.
	 */
	ceil() {

		this.x = Math.ceil( this.x );
		this.y = Math.ceil( this.y );
		this.z = Math.ceil( this.z );

		return this;

	}

	/**
	 * The components of this vector are rounded to the nearest integer value
	 *
	 * @return {Vector3} A reference to this vector.
	 */
	round() {

		this.x = Math.round( this.x );
		this.y = Math.round( this.y );
		this.z = Math.round( this.z );

		return this;

	}

	/**
	 * The components of this vector are rounded towards zero (up if negative,
	 * down if positive) to an integer value.
	 *
	 * @return {Vector3} A reference to this vector.
	 */
	roundToZero() {

		this.x = Math.trunc( this.x );
		this.y = Math.trunc( this.y );
		this.z = Math.trunc( this.z );

		return this;

	}

	/**
	 * Inverts this vector - i.e. sets x = -x, y = -y and z = -z.
	 *
	 * @return {Vector3} A reference to this vector.
	 */
	negate() {

		this.x = - this.x;
		this.y = - this.y;
		this.z = - this.z;

		return this;

	}

	/**
	 * Calculates the dot product of the given vector with this instance.
	 *
	 * @param {Vector3} v - The vector to compute the dot product with.
	 * @return {number} The result of the dot product.
	 */
	dot( v ) {

		return this.x * v.x + this.y * v.y + this.z * v.z;

	}

	// TODO lengthSquared?

	/**
	 * Computes the square of the Euclidean length (straight-line length) from
	 * (0, 0, 0) to (x, y, z). If you are comparing the lengths of vectors, you should
	 * compare the length squared instead as it is slightly more efficient to calculate.
	 *
	 * @return {number} The square length of this vector.
	 */
	lengthSq() {

		return this.x * this.x + this.y * this.y + this.z * this.z;

	}

	/**
	 * Computes the  Euclidean length (straight-line length) from (0, 0, 0) to (x, y, z).
	 *
	 * @return {number} The length of this vector.
	 */
	length() {

		return Math.sqrt( this.x * this.x + this.y * this.y + this.z * this.z );

	}

	/**
	 * Computes the Manhattan length of this vector.
	 *
	 * @return {number} The length of this vector.
	 */
	manhattanLength() {

		return Math.abs( this.x ) + Math.abs( this.y ) + Math.abs( this.z );

	}

	/**
	 * Converts this vector to a unit vector - that is, sets it equal to a vector
	 * with the same direction as this one, but with a vector length of `1`.
	 *
	 * @return {Vector3} A reference to this vector.
	 */
	normalize() {

		return this.divideScalar( this.length() || 1 );

	}

	/**
	 * Sets this vector to a vector with the same direction as this one, but
	 * with the specified length.
	 *
	 * @param {number} length - The new length of this vector.
	 * @return {Vector3} A reference to this vector.
	 */
	setLength( length ) {

		return this.normalize().multiplyScalar( length );

	}

	/**
	 * Linearly interpolates between the given vector and this instance, where
	 * alpha is the percent distance along the line - alpha = 0 will be this
	 * vector, and alpha = 1 will be the given one.
	 *
	 * @param {Vector3} v - The vector to interpolate towards.
	 * @param {number} alpha - The interpolation factor, typically in the closed interval `[0, 1]`.
	 * @return {Vector3} A reference to this vector.
	 */
	lerp( v, alpha ) {

		this.x += ( v.x - this.x ) * alpha;
		this.y += ( v.y - this.y ) * alpha;
		this.z += ( v.z - this.z ) * alpha;

		return this;

	}

	/**
	 * Linearly interpolates between the given vectors, where alpha is the percent
	 * distance along the line - alpha = 0 will be first vector, and alpha = 1 will
	 * be the second one. The result is stored in this instance.
	 *
	 * @param {Vector3} v1 - The first vector.
	 * @param {Vector3} v2 - The second vector.
	 * @param {number} alpha - The interpolation factor, typically in the closed interval `[0, 1]`.
	 * @return {Vector3} A reference to this vector.
	 */
	lerpVectors( v1, v2, alpha ) {

		this.x = v1.x + ( v2.x - v1.x ) * alpha;
		this.y = v1.y + ( v2.y - v1.y ) * alpha;
		this.z = v1.z + ( v2.z - v1.z ) * alpha;

		return this;

	}

	/**
	 * Calculates the cross product of the given vector with this instance.
	 *
	 * @param {Vector3} v - The vector to compute the cross product with.
	 * @return {Vector3} The result of the cross product.
	 */
	cross( v ) {

		return this.crossVectors( this, v );

	}

	/**
	 * Calculates the cross product of the given vectors and stores the result
	 * in this instance.
	 *
	 * @param {Vector3} a - The first vector.
	 * @param {Vector3} b - The second vector.
	 * @return {Vector3} A reference to this vector.
	 */
	crossVectors( a, b ) {

		const ax = a.x, ay = a.y, az = a.z;
		const bx = b.x, by = b.y, bz = b.z;

		this.x = ay * bz - az * by;
		this.y = az * bx - ax * bz;
		this.z = ax * by - ay * bx;

		return this;

	}

	/**
	 * Projects this vector onto the given one.
	 *
	 * @param {Vector3} v - The vector to project to.
	 * @return {Vector3} A reference to this vector.
	 */
	projectOnVector( v ) {

		const denominator = v.lengthSq();

		if ( denominator === 0 ) return this.set( 0, 0, 0 );

		const scalar = v.dot( this ) / denominator;

		return this.copy( v ).multiplyScalar( scalar );

	}

	/**
	 * Projects this vector onto a plane by subtracting this
	 * vector projected onto the plane's normal from this vector.
	 *
	 * @param {Vector3} planeNormal - The plane normal.
	 * @return {Vector3} A reference to this vector.
	 */
	projectOnPlane( planeNormal ) {

		_vector.copy( this ).projectOnVector( planeNormal );

		return this.sub( _vector );

	}

	/**
	 * Reflects this vector off a plane orthogonal to the given normal vector.
	 *
	 * @param {Vector3} normal - The (normalized) normal vector.
	 * @return {Vector3} A reference to this vector.
	 */
	reflect( normal ) {

		return this.sub( _vector.copy( normal ).multiplyScalar( 2 * this.dot( normal ) ) );

	}
	/**
	 * Returns the angle between the given vector and this instance in radians.
	 *
	 * @param {Vector3} v - The vector to compute the angle with.
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
	 * @param {Vector3} v - The vector to compute the distance to.
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
	 * @param {Vector3} v - The vector to compute the squared distance to.
	 * @return {number} The squared distance.
	 */
	distanceToSquared( v ) {

		const dx = this.x - v.x, dy = this.y - v.y, dz = this.z - v.z;

		return dx * dx + dy * dy + dz * dz;

	}

	/**
	 * Computes the Manhattan distance from the given vector to this instance.
	 *
	 * @param {Vector3} v - The vector to compute the Manhattan distance to.
	 * @return {number} The Manhattan distance.
	 */
	manhattanDistanceTo( v ) {

		return Math.abs( this.x - v.x ) + Math.abs( this.y - v.y ) + Math.abs( this.z - v.z );

	}

	/**
	 * Sets the vector components from the given spherical coordinates.
	 *
	 * @param {Spherical} s - The spherical coordinates.
	 * @return {Vector3} A reference to this vector.
	 */
	setFromSpherical( s ) {

		return this.setFromSphericalCoords( s.radius, s.phi, s.theta );

	}

	/**
	 * Sets the vector components from the given spherical coordinates.
	 *
	 * @param {number} radius - The radius.
	 * @param {number} phi - The phi angle in radians.
	 * @param {number} theta - The theta angle in radians.
	 * @return {Vector3} A reference to this vector.
	 */
	setFromSphericalCoords( radius, phi, theta ) {

		const sinPhiRadius = Math.sin( phi ) * radius;

		this.x = sinPhiRadius * Math.sin( theta );
		this.y = Math.cos( phi ) * radius;
		this.z = sinPhiRadius * Math.cos( theta );

		return this;

	}

	/**
	 * Sets the vector components from the given cylindrical coordinates.
	 *
	 * @param {Cylindrical} c - The cylindrical coordinates.
	 * @return {Vector3} A reference to this vector.
	 */
	setFromCylindrical( c ) {

		return this.setFromCylindricalCoords( c.radius, c.theta, c.y );

	}

	/**
	 * Sets the vector components from the given cylindrical coordinates.
	 *
	 * @param {number} radius - The radius.
	 * @param {number} theta - The theta angle in radians.
	 * @param {number} y - The y value.
	 * @return {Vector3} A reference to this vector.
	 */
	setFromCylindricalCoords( radius, theta, y ) {

		this.x = radius * Math.sin( theta );
		this.y = y;
		this.z = radius * Math.cos( theta );

		return this;

	}

	/**
	 * Sets the vector components to the position elements of the
	 * given transformation matrix.
	 *
	 * @param {Matrix4} m - The 4x4 matrix.
	 * @return {Vector3} A reference to this vector.
	 */
	setFromMatrixPosition( m ) {

		const e = m.elements;

		this.x = e[ 12 ];
		this.y = e[ 13 ];
		this.z = e[ 14 ];

		return this;

	}

	/**
	 * Sets the vector components to the scale elements of the
	 * given transformation matrix.
	 *
	 * @param {Matrix4} m - The 4x4 matrix.
	 * @return {Vector3} A reference to this vector.
	 */
	setFromMatrixScale( m ) {

		const sx = this.setFromMatrixColumn( m, 0 ).length();
		const sy = this.setFromMatrixColumn( m, 1 ).length();
		const sz = this.setFromMatrixColumn( m, 2 ).length();

		this.x = sx;
		this.y = sy;
		this.z = sz;

		return this;

	}

	/**
	 * Sets the vector components from the specified matrix column.
	 *
	 * @param {Matrix4} m - The 4x4 matrix.
	 * @param {number} index - The column index.
	 * @return {Vector3} A reference to this vector.
	 */
	setFromMatrixColumn( m, index ) {

		return this.fromArray( m.elements, index * 4 );

	}

	/**
	 * Sets the vector components from the specified matrix column.
	 *
	 * @param {Matrix3} m - The 3x3 matrix.
	 * @param {number} index - The column index.
	 * @return {Vector3} A reference to this vector.
	 */
	setFromMatrix3Column( m, index ) {

		return this.fromArray( m.elements, index * 3 );

	}

	/**
	 * Sets the vector components from the given Euler angles.
	 *
	 * @param {Euler} e - The Euler angles to set.
	 * @return {Vector3} A reference to this vector.
	 */
	setFromEuler( e ) {

		this.x = e._x;
		this.y = e._y;
		this.z = e._z;

		return this;

	}

	/**
	 * Sets the vector components from the RGB components of the
	 * given color.
	 *
	 * @param {Color} c - The color to set.
	 * @return {Vector3} A reference to this vector.
	 */
	setFromColor( c ) {

		this.x = c.r;
		this.y = c.g;
		this.z = c.b;

		return this;

	}

	/**
	 * Returns `true` if this vector is equal with the given one.
	 *
	 * @param {Vector3} v - The vector to test for equality.
	 * @return {boolean} Whether this vector is equal with the given one.
	 */
	equals( v ) {

		return ( ( v.x === this.x ) && ( v.y === this.y ) && ( v.z === this.z ) );

	}

	/**
	 * Sets this vector's x value to be `array[ offset ]`, y value to be `array[ offset + 1 ]`
	 * and z value to be `array[ offset + 2 ]`.
	 *
	 * @param {Array<number>} array - An array holding the vector component values.
	 * @param {number} [offset=0] - The offset into the array.
	 * @return {Vector3} A reference to this vector.
	 */
	fromArray( array, offset = 0 ) {

		this.x = array[ offset ];
		this.y = array[ offset + 1 ];
		this.z = array[ offset + 2 ];

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
		array[ offset + 2 ] = this.z;

		return array;

	}

	/**
	 * Sets the components of this vector from the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute holding vector data.
	 * @param {number} index - The index into the attribute.
	 * @return {Vector3} A reference to this vector.
	 */
	fromBufferAttribute( attribute, index ) {

		this.x = attribute.getX( index );
		this.y = attribute.getY( index );
		this.z = attribute.getZ( index );

		return this;

	}

	/**
	 * Sets each component of this vector to a pseudo-random value between `0` and
	 * `1`, excluding `1`.
	 *
	 * @return {Vector3} A reference to this vector.
	 */
	random() {

		this.x = Math.random();
		this.y = Math.random();
		this.z = Math.random();

		return this;

	}

	/**
	 * Sets this vector to a uniformly random point on a unit sphere.
	 *
	 * @return {Vector3} A reference to this vector.
	 */
	randomDirection() {

		// https://mathworld.wolfram.com/SpherePointPicking.html

		const theta = Math.random() * Math.PI * 2;
		const u = Math.random() * 2 - 1;
		const c = Math.sqrt( 1 - u * u );

		this.x = c * Math.cos( theta );
		this.y = u;
		this.z = c * Math.sin( theta );

		return this;

	}

	*[ Symbol.iterator ]() {

		yield this.x;
		yield this.y;
		yield this.z;

	}

}
```
</details>

#### Methods

##### `set(x: number, y: number, z: number): Vector3`

<details><summary>Code</summary>

```ts
set( x, y, z ) {

		if ( z === undefined ) z = this.z; // sprite.scale.set(x,y)

		this.x = x;
		this.y = y;
		this.z = z;

		return this;

	}
```
</details>

##### `setScalar(scalar: number): Vector3`

<details><summary>Code</summary>

```ts
setScalar( scalar ) {

		this.x = scalar;
		this.y = scalar;
		this.z = scalar;

		return this;

	}
```
</details>

##### `setX(x: number): Vector3`

<details><summary>Code</summary>

```ts
setX( x ) {

		this.x = x;

		return this;

	}
```
</details>

##### `setY(y: number): Vector3`

<details><summary>Code</summary>

```ts
setY( y ) {

		this.y = y;

		return this;

	}
```
</details>

##### `setZ(z: number): Vector3`

<details><summary>Code</summary>

```ts
setZ( z ) {

		this.z = z;

		return this;

	}
```
</details>

##### `setComponent(index: number, value: number): Vector3`

<details><summary>Code</summary>

```ts
setComponent( index, value ) {

		switch ( index ) {

			case 0: this.x = value; break;
			case 1: this.y = value; break;
			case 2: this.z = value; break;
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
			case 2: return this.z;
			default: throw new Error( 'index is out of range: ' + index );

		}

	}
```
</details>

##### `clone(): Vector3`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor( this.x, this.y, this.z );

	}
```
</details>

##### `copy(v: Vector3): Vector3`

<details><summary>Code</summary>

```ts
copy( v ) {

		this.x = v.x;
		this.y = v.y;
		this.z = v.z;

		return this;

	}
```
</details>

##### `add(v: Vector3): Vector3`

<details><summary>Code</summary>

```ts
add( v ) {

		this.x += v.x;
		this.y += v.y;
		this.z += v.z;

		return this;

	}
```
</details>

##### `addScalar(s: number): Vector3`

<details><summary>Code</summary>

```ts
addScalar( s ) {

		this.x += s;
		this.y += s;
		this.z += s;

		return this;

	}
```
</details>

##### `addVectors(a: Vector3, b: Vector3): Vector3`

<details><summary>Code</summary>

```ts
addVectors( a, b ) {

		this.x = a.x + b.x;
		this.y = a.y + b.y;
		this.z = a.z + b.z;

		return this;

	}
```
</details>

##### `addScaledVector(v: any, s: number): Vector3`

<details><summary>Code</summary>

```ts
addScaledVector( v, s ) {

		this.x += v.x * s;
		this.y += v.y * s;
		this.z += v.z * s;

		return this;

	}
```
</details>

##### `sub(v: Vector3): Vector3`

<details><summary>Code</summary>

```ts
sub( v ) {

		this.x -= v.x;
		this.y -= v.y;
		this.z -= v.z;

		return this;

	}
```
</details>

##### `subScalar(s: number): Vector3`

<details><summary>Code</summary>

```ts
subScalar( s ) {

		this.x -= s;
		this.y -= s;
		this.z -= s;

		return this;

	}
```
</details>

##### `subVectors(a: Vector3, b: Vector3): Vector3`

<details><summary>Code</summary>

```ts
subVectors( a, b ) {

		this.x = a.x - b.x;
		this.y = a.y - b.y;
		this.z = a.z - b.z;

		return this;

	}
```
</details>

##### `multiply(v: Vector3): Vector3`

<details><summary>Code</summary>

```ts
multiply( v ) {

		this.x *= v.x;
		this.y *= v.y;
		this.z *= v.z;

		return this;

	}
```
</details>

##### `multiplyScalar(scalar: number): Vector3`

<details><summary>Code</summary>

```ts
multiplyScalar( scalar ) {

		this.x *= scalar;
		this.y *= scalar;
		this.z *= scalar;

		return this;

	}
```
</details>

##### `multiplyVectors(a: Vector3, b: Vector3): Vector3`

<details><summary>Code</summary>

```ts
multiplyVectors( a, b ) {

		this.x = a.x * b.x;
		this.y = a.y * b.y;
		this.z = a.z * b.z;

		return this;

	}
```
</details>

##### `applyEuler(euler: Euler): Vector3`

<details><summary>Code</summary>

```ts
applyEuler( euler ) {

		return this.applyQuaternion( _quaternion.setFromEuler( euler ) );

	}
```
</details>

##### `applyAxisAngle(axis: Vector3, angle: number): Vector3`

<details><summary>Code</summary>

```ts
applyAxisAngle( axis, angle ) {

		return this.applyQuaternion( _quaternion.setFromAxisAngle( axis, angle ) );

	}
```
</details>

##### `applyMatrix3(m: Matrix3): Vector3`

<details><summary>Code</summary>

```ts
applyMatrix3( m ) {

		const x = this.x, y = this.y, z = this.z;
		const e = m.elements;

		this.x = e[ 0 ] * x + e[ 3 ] * y + e[ 6 ] * z;
		this.y = e[ 1 ] * x + e[ 4 ] * y + e[ 7 ] * z;
		this.z = e[ 2 ] * x + e[ 5 ] * y + e[ 8 ] * z;

		return this;

	}
```
</details>

##### `applyNormalMatrix(m: Matrix3): Vector3`

<details><summary>Code</summary>

```ts
applyNormalMatrix( m ) {

		return this.applyMatrix3( m ).normalize();

	}
```
</details>

##### `applyMatrix4(m: Matrix4): Vector3`

<details><summary>Code</summary>

```ts
applyMatrix4( m ) {

		const x = this.x, y = this.y, z = this.z;
		const e = m.elements;

		const w = 1 / ( e[ 3 ] * x + e[ 7 ] * y + e[ 11 ] * z + e[ 15 ] );

		this.x = ( e[ 0 ] * x + e[ 4 ] * y + e[ 8 ] * z + e[ 12 ] ) * w;
		this.y = ( e[ 1 ] * x + e[ 5 ] * y + e[ 9 ] * z + e[ 13 ] ) * w;
		this.z = ( e[ 2 ] * x + e[ 6 ] * y + e[ 10 ] * z + e[ 14 ] ) * w;

		return this;

	}
```
</details>

##### `applyQuaternion(q: Quaternion): Vector3`

<details><summary>Code</summary>

```ts
applyQuaternion( q ) {

		// quaternion q is assumed to have unit length

		const vx = this.x, vy = this.y, vz = this.z;
		const qx = q.x, qy = q.y, qz = q.z, qw = q.w;

		// t = 2 * cross( q.xyz, v );
		const tx = 2 * ( qy * vz - qz * vy );
		const ty = 2 * ( qz * vx - qx * vz );
		const tz = 2 * ( qx * vy - qy * vx );

		// v + q.w * t + cross( q.xyz, t );
		this.x = vx + qw * tx + qy * tz - qz * ty;
		this.y = vy + qw * ty + qz * tx - qx * tz;
		this.z = vz + qw * tz + qx * ty - qy * tx;

		return this;

	}
```
</details>

##### `project(camera: Camera): Vector3`

<details><summary>Code</summary>

```ts
project( camera ) {

		return this.applyMatrix4( camera.matrixWorldInverse ).applyMatrix4( camera.projectionMatrix );

	}
```
</details>

##### `unproject(camera: Camera): Vector3`

<details><summary>Code</summary>

```ts
unproject( camera ) {

		return this.applyMatrix4( camera.projectionMatrixInverse ).applyMatrix4( camera.matrixWorld );

	}
```
</details>

##### `transformDirection(m: Matrix4): Vector3`

<details><summary>Code</summary>

```ts
transformDirection( m ) {

		// input: THREE.Matrix4 affine matrix
		// vector interpreted as a direction

		const x = this.x, y = this.y, z = this.z;
		const e = m.elements;

		this.x = e[ 0 ] * x + e[ 4 ] * y + e[ 8 ] * z;
		this.y = e[ 1 ] * x + e[ 5 ] * y + e[ 9 ] * z;
		this.z = e[ 2 ] * x + e[ 6 ] * y + e[ 10 ] * z;

		return this.normalize();

	}
```
</details>

##### `divide(v: Vector3): Vector3`

<details><summary>Code</summary>

```ts
divide( v ) {

		this.x /= v.x;
		this.y /= v.y;
		this.z /= v.z;

		return this;

	}
```
</details>

##### `divideScalar(scalar: number): Vector3`

<details><summary>Code</summary>

```ts
divideScalar( scalar ) {

		return this.multiplyScalar( 1 / scalar );

	}
```
</details>

##### `min(v: Vector3): Vector3`

<details><summary>Code</summary>

```ts
min( v ) {

		this.x = Math.min( this.x, v.x );
		this.y = Math.min( this.y, v.y );
		this.z = Math.min( this.z, v.z );

		return this;

	}
```
</details>

##### `max(v: Vector3): Vector3`

<details><summary>Code</summary>

```ts
max( v ) {

		this.x = Math.max( this.x, v.x );
		this.y = Math.max( this.y, v.y );
		this.z = Math.max( this.z, v.z );

		return this;

	}
```
</details>

##### `clamp(min: Vector3, max: Vector3): Vector3`

<details><summary>Code</summary>

```ts
clamp( min, max ) {

		// assumes min < max, componentwise

		this.x = clamp( this.x, min.x, max.x );
		this.y = clamp( this.y, min.y, max.y );
		this.z = clamp( this.z, min.z, max.z );

		return this;

	}
```
</details>

##### `clampScalar(minVal: number, maxVal: number): Vector3`

<details><summary>Code</summary>

```ts
clampScalar( minVal, maxVal ) {

		this.x = clamp( this.x, minVal, maxVal );
		this.y = clamp( this.y, minVal, maxVal );
		this.z = clamp( this.z, minVal, maxVal );

		return this;

	}
```
</details>

##### `clampLength(min: number, max: number): Vector3`

<details><summary>Code</summary>

```ts
clampLength( min, max ) {

		const length = this.length();

		return this.divideScalar( length || 1 ).multiplyScalar( clamp( length, min, max ) );

	}
```
</details>

##### `floor(): Vector3`

<details><summary>Code</summary>

```ts
floor() {

		this.x = Math.floor( this.x );
		this.y = Math.floor( this.y );
		this.z = Math.floor( this.z );

		return this;

	}
```
</details>

##### `ceil(): Vector3`

<details><summary>Code</summary>

```ts
ceil() {

		this.x = Math.ceil( this.x );
		this.y = Math.ceil( this.y );
		this.z = Math.ceil( this.z );

		return this;

	}
```
</details>

##### `round(): Vector3`

<details><summary>Code</summary>

```ts
round() {

		this.x = Math.round( this.x );
		this.y = Math.round( this.y );
		this.z = Math.round( this.z );

		return this;

	}
```
</details>

##### `roundToZero(): Vector3`

<details><summary>Code</summary>

```ts
roundToZero() {

		this.x = Math.trunc( this.x );
		this.y = Math.trunc( this.y );
		this.z = Math.trunc( this.z );

		return this;

	}
```
</details>

##### `negate(): Vector3`

<details><summary>Code</summary>

```ts
negate() {

		this.x = - this.x;
		this.y = - this.y;
		this.z = - this.z;

		return this;

	}
```
</details>

##### `dot(v: Vector3): number`

<details><summary>Code</summary>

```ts
dot( v ) {

		return this.x * v.x + this.y * v.y + this.z * v.z;

	}
```
</details>

##### `lengthSq(): number`

<details><summary>Code</summary>

```ts
lengthSq() {

		return this.x * this.x + this.y * this.y + this.z * this.z;

	}
```
</details>

##### `length(): number`

<details><summary>Code</summary>

```ts
length() {

		return Math.sqrt( this.x * this.x + this.y * this.y + this.z * this.z );

	}
```
</details>

##### `manhattanLength(): number`

<details><summary>Code</summary>

```ts
manhattanLength() {

		return Math.abs( this.x ) + Math.abs( this.y ) + Math.abs( this.z );

	}
```
</details>

##### `normalize(): Vector3`

<details><summary>Code</summary>

```ts
normalize() {

		return this.divideScalar( this.length() || 1 );

	}
```
</details>

##### `setLength(length: number): Vector3`

<details><summary>Code</summary>

```ts
setLength( length ) {

		return this.normalize().multiplyScalar( length );

	}
```
</details>

##### `lerp(v: Vector3, alpha: number): Vector3`

<details><summary>Code</summary>

```ts
lerp( v, alpha ) {

		this.x += ( v.x - this.x ) * alpha;
		this.y += ( v.y - this.y ) * alpha;
		this.z += ( v.z - this.z ) * alpha;

		return this;

	}
```
</details>

##### `lerpVectors(v1: Vector3, v2: Vector3, alpha: number): Vector3`

<details><summary>Code</summary>

```ts
lerpVectors( v1, v2, alpha ) {

		this.x = v1.x + ( v2.x - v1.x ) * alpha;
		this.y = v1.y + ( v2.y - v1.y ) * alpha;
		this.z = v1.z + ( v2.z - v1.z ) * alpha;

		return this;

	}
```
</details>

##### `cross(v: Vector3): Vector3`

<details><summary>Code</summary>

```ts
cross( v ) {

		return this.crossVectors( this, v );

	}
```
</details>

##### `crossVectors(a: Vector3, b: Vector3): Vector3`

<details><summary>Code</summary>

```ts
crossVectors( a, b ) {

		const ax = a.x, ay = a.y, az = a.z;
		const bx = b.x, by = b.y, bz = b.z;

		this.x = ay * bz - az * by;
		this.y = az * bx - ax * bz;
		this.z = ax * by - ay * bx;

		return this;

	}
```
</details>

##### `projectOnVector(v: Vector3): Vector3`

<details><summary>Code</summary>

```ts
projectOnVector( v ) {

		const denominator = v.lengthSq();

		if ( denominator === 0 ) return this.set( 0, 0, 0 );

		const scalar = v.dot( this ) / denominator;

		return this.copy( v ).multiplyScalar( scalar );

	}
```
</details>

##### `projectOnPlane(planeNormal: Vector3): Vector3`

<details><summary>Code</summary>

```ts
projectOnPlane( planeNormal ) {

		_vector.copy( this ).projectOnVector( planeNormal );

		return this.sub( _vector );

	}
```
</details>

##### `reflect(normal: Vector3): Vector3`

<details><summary>Code</summary>

```ts
reflect( normal ) {

		return this.sub( _vector.copy( normal ).multiplyScalar( 2 * this.dot( normal ) ) );

	}
```
</details>

##### `angleTo(v: Vector3): number`

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

##### `distanceTo(v: Vector3): number`

<details><summary>Code</summary>

```ts
distanceTo( v ) {

		return Math.sqrt( this.distanceToSquared( v ) );

	}
```
</details>

##### `distanceToSquared(v: Vector3): number`

<details><summary>Code</summary>

```ts
distanceToSquared( v ) {

		const dx = this.x - v.x, dy = this.y - v.y, dz = this.z - v.z;

		return dx * dx + dy * dy + dz * dz;

	}
```
</details>

##### `manhattanDistanceTo(v: Vector3): number`

<details><summary>Code</summary>

```ts
manhattanDistanceTo( v ) {

		return Math.abs( this.x - v.x ) + Math.abs( this.y - v.y ) + Math.abs( this.z - v.z );

	}
```
</details>

##### `setFromSpherical(s: Spherical): Vector3`

<details><summary>Code</summary>

```ts
setFromSpherical( s ) {

		return this.setFromSphericalCoords( s.radius, s.phi, s.theta );

	}
```
</details>

##### `setFromSphericalCoords(radius: number, phi: number, theta: number): Vector3`

<details><summary>Code</summary>

```ts
setFromSphericalCoords( radius, phi, theta ) {

		const sinPhiRadius = Math.sin( phi ) * radius;

		this.x = sinPhiRadius * Math.sin( theta );
		this.y = Math.cos( phi ) * radius;
		this.z = sinPhiRadius * Math.cos( theta );

		return this;

	}
```
</details>

##### `setFromCylindrical(c: Cylindrical): Vector3`

<details><summary>Code</summary>

```ts
setFromCylindrical( c ) {

		return this.setFromCylindricalCoords( c.radius, c.theta, c.y );

	}
```
</details>

##### `setFromCylindricalCoords(radius: number, theta: number, y: number): Vector3`

<details><summary>Code</summary>

```ts
setFromCylindricalCoords( radius, theta, y ) {

		this.x = radius * Math.sin( theta );
		this.y = y;
		this.z = radius * Math.cos( theta );

		return this;

	}
```
</details>

##### `setFromMatrixPosition(m: Matrix4): Vector3`

<details><summary>Code</summary>

```ts
setFromMatrixPosition( m ) {

		const e = m.elements;

		this.x = e[ 12 ];
		this.y = e[ 13 ];
		this.z = e[ 14 ];

		return this;

	}
```
</details>

##### `setFromMatrixScale(m: Matrix4): Vector3`

<details><summary>Code</summary>

```ts
setFromMatrixScale( m ) {

		const sx = this.setFromMatrixColumn( m, 0 ).length();
		const sy = this.setFromMatrixColumn( m, 1 ).length();
		const sz = this.setFromMatrixColumn( m, 2 ).length();

		this.x = sx;
		this.y = sy;
		this.z = sz;

		return this;

	}
```
</details>

##### `setFromMatrixColumn(m: Matrix4, index: number): Vector3`

<details><summary>Code</summary>

```ts
setFromMatrixColumn( m, index ) {

		return this.fromArray( m.elements, index * 4 );

	}
```
</details>

##### `setFromMatrix3Column(m: Matrix3, index: number): Vector3`

<details><summary>Code</summary>

```ts
setFromMatrix3Column( m, index ) {

		return this.fromArray( m.elements, index * 3 );

	}
```
</details>

##### `setFromEuler(e: Euler): Vector3`

<details><summary>Code</summary>

```ts
setFromEuler( e ) {

		this.x = e._x;
		this.y = e._y;
		this.z = e._z;

		return this;

	}
```
</details>

##### `setFromColor(c: Color): Vector3`

<details><summary>Code</summary>

```ts
setFromColor( c ) {

		this.x = c.r;
		this.y = c.g;
		this.z = c.b;

		return this;

	}
```
</details>

##### `equals(v: Vector3): boolean`

<details><summary>Code</summary>

```ts
equals( v ) {

		return ( ( v.x === this.x ) && ( v.y === this.y ) && ( v.z === this.z ) );

	}
```
</details>

##### `fromArray(array: number[], offset: number): Vector3`

<details><summary>Code</summary>

```ts
fromArray( array, offset = 0 ) {

		this.x = array[ offset ];
		this.y = array[ offset + 1 ];
		this.z = array[ offset + 2 ];

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
		array[ offset + 2 ] = this.z;

		return array;

	}
```
</details>

##### `fromBufferAttribute(attribute: BufferAttribute, index: number): Vector3`

<details><summary>Code</summary>

```ts
fromBufferAttribute( attribute, index ) {

		this.x = attribute.getX( index );
		this.y = attribute.getY( index );
		this.z = attribute.getZ( index );

		return this;

	}
```
</details>

##### `random(): Vector3`

<details><summary>Code</summary>

```ts
random() {

		this.x = Math.random();
		this.y = Math.random();
		this.z = Math.random();

		return this;

	}
```
</details>

##### `randomDirection(): Vector3`

<details><summary>Code</summary>

```ts
randomDirection() {

		// https://mathworld.wolfram.com/SpherePointPicking.html

		const theta = Math.random() * Math.PI * 2;
		const u = Math.random() * 2 - 1;
		const c = Math.sqrt( 1 - u * u );

		this.x = c * Math.cos( theta );
		this.y = u;
		this.z = c * Math.sin( theta );

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
		yield this.z;

	}
```
</details>


---