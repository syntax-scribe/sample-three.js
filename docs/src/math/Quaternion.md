[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Quaternion.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 32 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 64 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/Quaternion.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `clamp` | `./MathUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `x0` | `number` | let/var | `src0[ srcOffset0 + 0 ]` | ✗ |
| `y0` | `number` | let/var | `src0[ srcOffset0 + 1 ]` | ✗ |
| `z0` | `number` | let/var | `src0[ srcOffset0 + 2 ]` | ✗ |
| `w0` | `number` | let/var | `src0[ srcOffset0 + 3 ]` | ✗ |
| `x1` | `number` | let/var | `src1[ srcOffset1 + 0 ]` | ✗ |
| `y1` | `number` | let/var | `src1[ srcOffset1 + 1 ]` | ✗ |
| `z1` | `number` | let/var | `src1[ srcOffset1 + 2 ]` | ✗ |
| `w1` | `number` | let/var | `src1[ srcOffset1 + 3 ]` | ✗ |
| `s` | `number` | let/var | `1 - t` | ✗ |
| `cos` | `number` | let/var | `x0 * x1 + y0 * y1 + z0 * z1 + w0 * w1` | ✗ |
| `dir` | `1 \| -1` | let/var | `( cos >= 0 ? 1 : - 1 )` | ✗ |
| `sqrSin` | `number` | let/var | `1 - cos * cos` | ✗ |
| `tDir` | `number` | let/var | `t * dir` | ✗ |
| `f` | `number` | let/var | `1 / Math.sqrt( x0 * x0 + y0 * y0 + z0 * z0 + w0 * w0 )` | ✗ |
| `x0` | `number` | let/var | `src0[ srcOffset0 ]` | ✗ |
| `y0` | `number` | let/var | `src0[ srcOffset0 + 1 ]` | ✗ |
| `z0` | `number` | let/var | `src0[ srcOffset0 + 2 ]` | ✗ |
| `w0` | `number` | let/var | `src0[ srcOffset0 + 3 ]` | ✗ |
| `x1` | `number` | let/var | `src1[ srcOffset1 ]` | ✗ |
| `y1` | `number` | let/var | `src1[ srcOffset1 + 1 ]` | ✗ |
| `z1` | `number` | let/var | `src1[ srcOffset1 + 2 ]` | ✗ |
| `w1` | `number` | let/var | `src1[ srcOffset1 + 3 ]` | ✗ |
| `x` | `any` | let/var | `euler._x` | ✗ |
| `y` | `any` | let/var | `euler._y` | ✗ |
| `z` | `any` | let/var | `euler._z` | ✗ |
| `order` | `any` | let/var | `euler._order` | ✗ |
| `cos` | `(x: number) => number` | let/var | `Math.cos` | ✗ |
| `sin` | `(x: number) => number` | let/var | `Math.sin` | ✗ |
| `halfAngle` | `number` | let/var | `angle / 2` | ✗ |
| `te` | `any` | let/var | `m.elements` | ✗ |
| `m11` | `any` | let/var | `te[ 0 ]` | ✗ |
| `m12` | `any` | let/var | `te[ 4 ]` | ✗ |
| `m13` | `any` | let/var | `te[ 8 ]` | ✗ |
| `m21` | `any` | let/var | `te[ 1 ]` | ✗ |
| `m22` | `any` | let/var | `te[ 5 ]` | ✗ |
| `m23` | `any` | let/var | `te[ 9 ]` | ✗ |
| `m31` | `any` | let/var | `te[ 2 ]` | ✗ |
| `m32` | `any` | let/var | `te[ 6 ]` | ✗ |
| `m33` | `any` | let/var | `te[ 10 ]` | ✗ |
| `trace` | `any` | let/var | `m11 + m22 + m33` | ✗ |
| `s` | `number` | let/var | `0.5 / Math.sqrt( trace + 1.0 )` | ✗ |
| `s` | `number` | let/var | `2.0 * Math.sqrt( 1.0 + m11 - m22 - m33 )` | ✗ |
| `s` | `number` | let/var | `2.0 * Math.sqrt( 1.0 + m22 - m11 - m33 )` | ✗ |
| `s` | `number` | let/var | `2.0 * Math.sqrt( 1.0 + m33 - m11 - m22 )` | ✗ |
| `r` | `any` | let/var | `vFrom.dot( vTo ) + 1` | ✗ |
| `qax` | `number` | let/var | `a._x` | ✗ |
| `qay` | `number` | let/var | `a._y` | ✗ |
| `qaz` | `number` | let/var | `a._z` | ✗ |
| `qaw` | `number` | let/var | `a._w` | ✗ |
| `qbx` | `number` | let/var | `b._x` | ✗ |
| `qby` | `number` | let/var | `b._y` | ✗ |
| `qbz` | `number` | let/var | `b._z` | ✗ |
| `qbw` | `number` | let/var | `b._w` | ✗ |
| `x` | `number` | let/var | `this._x` | ✗ |
| `y` | `number` | let/var | `this._y` | ✗ |
| `z` | `number` | let/var | `this._z` | ✗ |
| `w` | `number` | let/var | `this._w` | ✗ |
| `cosHalfTheta` | `number` | let/var | `w * qb._w + x * qb._x + y * qb._y + z * qb._z` | ✗ |
| `sqrSinHalfTheta` | `number` | let/var | `1.0 - cosHalfTheta * cosHalfTheta` | ✗ |
| `s` | `number` | let/var | `1 - t` | ✗ |
| `ratioA` | `number` | let/var | `Math.sin( ( 1 - t ) * halfTheta ) / sinHalfTheta` | ✗ |
| `ratioB` | `number` | let/var | `Math.sin( t * halfTheta ) / sinHalfTheta` | ✗ |
| `theta1` | `number` | let/var | `2 * Math.PI * Math.random()` | ✗ |
| `theta2` | `number` | let/var | `2 * Math.PI * Math.random()` | ✗ |


---

## Functions

### `Quaternion.slerpFlat(dst: number[], dstOffset: number, src0: number[], srcOffset0: number, src1: number[], srcOffset1: number, t: number): void`

**JSDoc:**
```typescript
/**
	 * Interpolates between two quaternions via SLERP. This implementation assumes the
	 * quaternion data are managed  in flat arrays.
	 *
	 * @param {Array<number>} dst - The destination array.
	 * @param {number} dstOffset - An offset into the destination array.
	 * @param {Array<number>} src0 - The source array of the first quaternion.
	 * @param {number} srcOffset0 - An offset into the first source array.
	 * @param {Array<number>} src1 -  The source array of the second quaternion.
	 * @param {number} srcOffset1 - An offset into the second source array.
	 * @param {number} t - The interpolation factor in the range `[0,1]`.
	 * @see {@link Quaternion#slerp}
	 */
```

**Parameters:**

- **`dst`** `number[]`
- **`dstOffset`** `number`
- **`src0`** `number[]`
- **`srcOffset0`** `number`
- **`src1`** `number[]`
- **`srcOffset1`** `number`
- **`t`** `number`

**Returns:** `void`

**Calls:**

- `Math.sqrt`
- `Math.atan2`
- `Math.sin`

**Internal Comments:**
```
// fuzz-free, array-based Quaternion SLERP operation (x2)
// Skip the Slerp for tiny steps to avoid numeric problems:
// Normalize in case we just did a lerp:
```

<details><summary>Code</summary>

```typescript
static slerpFlat( dst, dstOffset, src0, srcOffset0, src1, srcOffset1, t ) {

		// fuzz-free, array-based Quaternion SLERP operation

		let x0 = src0[ srcOffset0 + 0 ],
			y0 = src0[ srcOffset0 + 1 ],
			z0 = src0[ srcOffset0 + 2 ],
			w0 = src0[ srcOffset0 + 3 ];

		const x1 = src1[ srcOffset1 + 0 ],
			y1 = src1[ srcOffset1 + 1 ],
			z1 = src1[ srcOffset1 + 2 ],
			w1 = src1[ srcOffset1 + 3 ];

		if ( t === 0 ) {

			dst[ dstOffset + 0 ] = x0;
			dst[ dstOffset + 1 ] = y0;
			dst[ dstOffset + 2 ] = z0;
			dst[ dstOffset + 3 ] = w0;
			return;

		}

		if ( t === 1 ) {

			dst[ dstOffset + 0 ] = x1;
			dst[ dstOffset + 1 ] = y1;
			dst[ dstOffset + 2 ] = z1;
			dst[ dstOffset + 3 ] = w1;
			return;

		}

		if ( w0 !== w1 || x0 !== x1 || y0 !== y1 || z0 !== z1 ) {

			let s = 1 - t;
			const cos = x0 * x1 + y0 * y1 + z0 * z1 + w0 * w1,
				dir = ( cos >= 0 ? 1 : - 1 ),
				sqrSin = 1 - cos * cos;

			// Skip the Slerp for tiny steps to avoid numeric problems:
			if ( sqrSin > Number.EPSILON ) {

				const sin = Math.sqrt( sqrSin ),
					len = Math.atan2( sin, cos * dir );

				s = Math.sin( s * len ) / sin;
				t = Math.sin( t * len ) / sin;

			}

			const tDir = t * dir;

			x0 = x0 * s + x1 * tDir;
			y0 = y0 * s + y1 * tDir;
			z0 = z0 * s + z1 * tDir;
			w0 = w0 * s + w1 * tDir;

			// Normalize in case we just did a lerp:
			if ( s === 1 - t ) {

				const f = 1 / Math.sqrt( x0 * x0 + y0 * y0 + z0 * z0 + w0 * w0 );

				x0 *= f;
				y0 *= f;
				z0 *= f;
				w0 *= f;

			}

		}

		dst[ dstOffset ] = x0;
		dst[ dstOffset + 1 ] = y0;
		dst[ dstOffset + 2 ] = z0;
		dst[ dstOffset + 3 ] = w0;

	}
```
</details>

### `Quaternion.multiplyQuaternionsFlat(dst: number[], dstOffset: number, src0: number[], srcOffset0: number, src1: number[], srcOffset1: number): number[]`

**JSDoc:**
```typescript
/**
	 * Multiplies two quaternions. This implementation assumes the quaternion data are managed
	 * in flat arrays.
	 *
	 * @param {Array<number>} dst - The destination array.
	 * @param {number} dstOffset - An offset into the destination array.
	 * @param {Array<number>} src0 - The source array of the first quaternion.
	 * @param {number} srcOffset0 - An offset into the first source array.
	 * @param {Array<number>} src1 -  The source array of the second quaternion.
	 * @param {number} srcOffset1 - An offset into the second source array.
	 * @return {Array<number>} The destination array.
	 * @see {@link Quaternion#multiplyQuaternions}.
	 */
```

**Parameters:**

- **`dst`** `number[]`
- **`dstOffset`** `number`
- **`src0`** `number[]`
- **`srcOffset0`** `number`
- **`src1`** `number[]`
- **`srcOffset1`** `number`

**Returns:** `number[]`

<details><summary>Code</summary>

```typescript
static multiplyQuaternionsFlat( dst, dstOffset, src0, srcOffset0, src1, srcOffset1 ) {

		const x0 = src0[ srcOffset0 ];
		const y0 = src0[ srcOffset0 + 1 ];
		const z0 = src0[ srcOffset0 + 2 ];
		const w0 = src0[ srcOffset0 + 3 ];

		const x1 = src1[ srcOffset1 ];
		const y1 = src1[ srcOffset1 + 1 ];
		const z1 = src1[ srcOffset1 + 2 ];
		const w1 = src1[ srcOffset1 + 3 ];

		dst[ dstOffset ] = x0 * w1 + w0 * x1 + y0 * z1 - z0 * y1;
		dst[ dstOffset + 1 ] = y0 * w1 + w0 * y1 + z0 * x1 - x0 * z1;
		dst[ dstOffset + 2 ] = z0 * w1 + w0 * z1 + x0 * y1 - y0 * x1;
		dst[ dstOffset + 3 ] = w0 * w1 - x0 * x1 - y0 * y1 - z0 * z1;

		return dst;

	}
```
</details>

### `Quaternion.set(x: number, y: number, z: number, w: number): Quaternion`

**JSDoc:**
```typescript
/**
	 * Sets the quaternion components.
	 *
	 * @param {number} x - The x value of this quaternion.
	 * @param {number} y - The y value of this quaternion.
	 * @param {number} z - The z value of this quaternion.
	 * @param {number} w - The w value of this quaternion.
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`
- **`z`** `number`
- **`w`** `number`

**Returns:** `Quaternion`

**Calls:**

- `this._onChangeCallback`

<details><summary>Code</summary>

```typescript
set( x, y, z, w ) {

		this._x = x;
		this._y = y;
		this._z = z;
		this._w = w;

		this._onChangeCallback();

		return this;

	}
```
</details>

### `Quaternion.clone(): Quaternion`

**JSDoc:**
```typescript
/**
	 * Returns a new quaternion with copied values from this instance.
	 *
	 * @return {Quaternion} A clone of this instance.
	 */
```

**Returns:** `Quaternion`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor( this._x, this._y, this._z, this._w );

	}
```
</details>

### `Quaternion.copy(quaternion: Quaternion): Quaternion`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given quaternion to this instance.
	 *
	 * @param {Quaternion} quaternion - The quaternion to copy.
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Parameters:**

- **`quaternion`** `Quaternion`

**Returns:** `Quaternion`

**Calls:**

- `this._onChangeCallback`

<details><summary>Code</summary>

```typescript
copy( quaternion ) {

		this._x = quaternion.x;
		this._y = quaternion.y;
		this._z = quaternion.z;
		this._w = quaternion.w;

		this._onChangeCallback();

		return this;

	}
```
</details>

### `Quaternion.setFromEuler(euler: Euler, update: boolean): Quaternion`

**JSDoc:**
```typescript
/**
	 * Sets this quaternion from the rotation specified by the given
	 * Euler angles.
	 *
	 * @param {Euler} euler - The Euler angles.
	 * @param {boolean} [update=true] - Whether the internal `onChange` callback should be executed or not.
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Parameters:**

- **`euler`** `Euler`
- **`update`** `boolean`

**Returns:** `Quaternion`

**Calls:**

- `cos`
- `sin`
- `console.warn`
- `this._onChangeCallback`

**Internal Comments:**
```
// http://www.mathworks.com/matlabcentral/fileexchange/ (x2)
// 	20696-function-to-convert-between-dcm-euler-angles-quaternions-and-euler-vectors/ (x2)
//	content/SpinCalc.m (x2)
```

<details><summary>Code</summary>

```typescript
setFromEuler( euler, update = true ) {

		const x = euler._x, y = euler._y, z = euler._z, order = euler._order;

		// http://www.mathworks.com/matlabcentral/fileexchange/
		// 	20696-function-to-convert-between-dcm-euler-angles-quaternions-and-euler-vectors/
		//	content/SpinCalc.m

		const cos = Math.cos;
		const sin = Math.sin;

		const c1 = cos( x / 2 );
		const c2 = cos( y / 2 );
		const c3 = cos( z / 2 );

		const s1 = sin( x / 2 );
		const s2 = sin( y / 2 );
		const s3 = sin( z / 2 );

		switch ( order ) {

			case 'XYZ':
				this._x = s1 * c2 * c3 + c1 * s2 * s3;
				this._y = c1 * s2 * c3 - s1 * c2 * s3;
				this._z = c1 * c2 * s3 + s1 * s2 * c3;
				this._w = c1 * c2 * c3 - s1 * s2 * s3;
				break;

			case 'YXZ':
				this._x = s1 * c2 * c3 + c1 * s2 * s3;
				this._y = c1 * s2 * c3 - s1 * c2 * s3;
				this._z = c1 * c2 * s3 - s1 * s2 * c3;
				this._w = c1 * c2 * c3 + s1 * s2 * s3;
				break;

			case 'ZXY':
				this._x = s1 * c2 * c3 - c1 * s2 * s3;
				this._y = c1 * s2 * c3 + s1 * c2 * s3;
				this._z = c1 * c2 * s3 + s1 * s2 * c3;
				this._w = c1 * c2 * c3 - s1 * s2 * s3;
				break;

			case 'ZYX':
				this._x = s1 * c2 * c3 - c1 * s2 * s3;
				this._y = c1 * s2 * c3 + s1 * c2 * s3;
				this._z = c1 * c2 * s3 - s1 * s2 * c3;
				this._w = c1 * c2 * c3 + s1 * s2 * s3;
				break;

			case 'YZX':
				this._x = s1 * c2 * c3 + c1 * s2 * s3;
				this._y = c1 * s2 * c3 + s1 * c2 * s3;
				this._z = c1 * c2 * s3 - s1 * s2 * c3;
				this._w = c1 * c2 * c3 - s1 * s2 * s3;
				break;

			case 'XZY':
				this._x = s1 * c2 * c3 - c1 * s2 * s3;
				this._y = c1 * s2 * c3 - s1 * c2 * s3;
				this._z = c1 * c2 * s3 + s1 * s2 * c3;
				this._w = c1 * c2 * c3 + s1 * s2 * s3;
				break;

			default:
				console.warn( 'THREE.Quaternion: .setFromEuler() encountered an unknown order: ' + order );

		}

		if ( update === true ) this._onChangeCallback();

		return this;

	}
```
</details>

### `Quaternion.setFromAxisAngle(axis: Vector3, angle: number): Quaternion`

**JSDoc:**
```typescript
/**
	 * Sets this quaternion from the given axis and angle.
	 *
	 * @param {Vector3} axis - The normalized axis.
	 * @param {number} angle - The angle in radians.
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Parameters:**

- **`axis`** `Vector3`
- **`angle`** `number`

**Returns:** `Quaternion`

**Calls:**

- `Math.sin`
- `Math.cos`
- `this._onChangeCallback`

**Internal Comments:**
```
// http://www.euclideanspace.com/maths/geometry/rotations/conversions/angleToQuaternion/index.htm (x2)
```

<details><summary>Code</summary>

```typescript
setFromAxisAngle( axis, angle ) {

		// http://www.euclideanspace.com/maths/geometry/rotations/conversions/angleToQuaternion/index.htm

		const halfAngle = angle / 2, s = Math.sin( halfAngle );

		this._x = axis.x * s;
		this._y = axis.y * s;
		this._z = axis.z * s;
		this._w = Math.cos( halfAngle );

		this._onChangeCallback();

		return this;

	}
```
</details>

### `Quaternion.setFromRotationMatrix(m: Matrix4): Quaternion`

**JSDoc:**
```typescript
/**
	 * Sets this quaternion from the given rotation matrix.
	 *
	 * @param {Matrix4} m - A 4x4 matrix of which the upper 3x3 of matrix is a pure rotation matrix (i.e. unscaled).
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Parameters:**

- **`m`** `Matrix4`

**Returns:** `Quaternion`

**Calls:**

- `Math.sqrt`
- `this._onChangeCallback`

**Internal Comments:**
```
// http://www.euclideanspace.com/maths/geometry/rotations/conversions/matrixToQuaternion/index.htm (x2)
// assumes the upper 3x3 of m is a pure rotation matrix (i.e, unscaled) (x2)
```

<details><summary>Code</summary>

```typescript
setFromRotationMatrix( m ) {

		// http://www.euclideanspace.com/maths/geometry/rotations/conversions/matrixToQuaternion/index.htm

		// assumes the upper 3x3 of m is a pure rotation matrix (i.e, unscaled)

		const te = m.elements,

			m11 = te[ 0 ], m12 = te[ 4 ], m13 = te[ 8 ],
			m21 = te[ 1 ], m22 = te[ 5 ], m23 = te[ 9 ],
			m31 = te[ 2 ], m32 = te[ 6 ], m33 = te[ 10 ],

			trace = m11 + m22 + m33;

		if ( trace > 0 ) {

			const s = 0.5 / Math.sqrt( trace + 1.0 );

			this._w = 0.25 / s;
			this._x = ( m32 - m23 ) * s;
			this._y = ( m13 - m31 ) * s;
			this._z = ( m21 - m12 ) * s;

		} else if ( m11 > m22 && m11 > m33 ) {

			const s = 2.0 * Math.sqrt( 1.0 + m11 - m22 - m33 );

			this._w = ( m32 - m23 ) / s;
			this._x = 0.25 * s;
			this._y = ( m12 + m21 ) / s;
			this._z = ( m13 + m31 ) / s;

		} else if ( m22 > m33 ) {

			const s = 2.0 * Math.sqrt( 1.0 + m22 - m11 - m33 );

			this._w = ( m13 - m31 ) / s;
			this._x = ( m12 + m21 ) / s;
			this._y = 0.25 * s;
			this._z = ( m23 + m32 ) / s;

		} else {

			const s = 2.0 * Math.sqrt( 1.0 + m33 - m11 - m22 );

			this._w = ( m21 - m12 ) / s;
			this._x = ( m13 + m31 ) / s;
			this._y = ( m23 + m32 ) / s;
			this._z = 0.25 * s;

		}

		this._onChangeCallback();

		return this;

	}
```
</details>

### `Quaternion.setFromUnitVectors(vFrom: Vector3, vTo: Vector3): Quaternion`

**JSDoc:**
```typescript
/**
	 * Sets this quaternion to the rotation required to rotate the direction vector
	 * `vFrom` to the direction vector `vTo`.
	 *
	 * @param {Vector3} vFrom - The first (normalized) direction vector.
	 * @param {Vector3} vTo - The second (normalized) direction vector.
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Parameters:**

- **`vFrom`** `Vector3`
- **`vTo`** `Vector3`

**Returns:** `Quaternion`

**Calls:**

- `vFrom.dot`
- `Math.abs`
- `this.normalize`

**Internal Comments:**
```
// assumes direction vectors vFrom and vTo are normalized (x2)
// vFrom and vTo point in opposite directions (x3)
// crossVectors( vFrom, vTo ); // inlined to avoid cyclic dependency on Vector3 (x4)
```

<details><summary>Code</summary>

```typescript
setFromUnitVectors( vFrom, vTo ) {

		// assumes direction vectors vFrom and vTo are normalized

		let r = vFrom.dot( vTo ) + 1;

		if ( r < 1e-8 ) { // the epsilon value has been discussed in #31286

			// vFrom and vTo point in opposite directions

			r = 0;

			if ( Math.abs( vFrom.x ) > Math.abs( vFrom.z ) ) {

				this._x = - vFrom.y;
				this._y = vFrom.x;
				this._z = 0;
				this._w = r;

			} else {

				this._x = 0;
				this._y = - vFrom.z;
				this._z = vFrom.y;
				this._w = r;

			}

		} else {

			// crossVectors( vFrom, vTo ); // inlined to avoid cyclic dependency on Vector3

			this._x = vFrom.y * vTo.z - vFrom.z * vTo.y;
			this._y = vFrom.z * vTo.x - vFrom.x * vTo.z;
			this._z = vFrom.x * vTo.y - vFrom.y * vTo.x;
			this._w = r;

		}

		return this.normalize();

	}
```
</details>

### `Quaternion.angleTo(q: Quaternion): number`

**JSDoc:**
```typescript
/**
	 * Returns the angle between this quaternion and the given one in radians.
	 *
	 * @param {Quaternion} q - The quaternion to compute the angle with.
	 * @return {number} The angle in radians.
	 */
```

**Parameters:**

- **`q`** `Quaternion`

**Returns:** `number`

**Calls:**

- `Math.acos`
- `Math.abs`
- `clamp (from ./MathUtils.js)`
- `this.dot`

<details><summary>Code</summary>

```typescript
angleTo( q ) {

		return 2 * Math.acos( Math.abs( clamp( this.dot( q ), - 1, 1 ) ) );

	}
```
</details>

### `Quaternion.rotateTowards(q: Quaternion, step: number): Quaternion`

**JSDoc:**
```typescript
/**
	 * Rotates this quaternion by a given angular step to the given quaternion.
	 * The method ensures that the final quaternion will not overshoot `q`.
	 *
	 * @param {Quaternion} q - The target quaternion.
	 * @param {number} step - The angular step in radians.
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Parameters:**

- **`q`** `Quaternion`
- **`step`** `number`

**Returns:** `Quaternion`

**Calls:**

- `this.angleTo`
- `Math.min`
- `this.slerp`

<details><summary>Code</summary>

```typescript
rotateTowards( q, step ) {

		const angle = this.angleTo( q );

		if ( angle === 0 ) return this;

		const t = Math.min( 1, step / angle );

		this.slerp( q, t );

		return this;

	}
```
</details>

### `Quaternion.identity(): Quaternion`

**JSDoc:**
```typescript
/**
	 * Sets this quaternion to the identity quaternion; that is, to the
	 * quaternion that represents "no rotation".
	 *
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Returns:** `Quaternion`

**Calls:**

- `this.set`

<details><summary>Code</summary>

```typescript
identity() {

		return this.set( 0, 0, 0, 1 );

	}
```
</details>

### `Quaternion.invert(): Quaternion`

**JSDoc:**
```typescript
/**
	 * Inverts this quaternion via {@link Quaternion#conjugate}. The
	 * quaternion is assumed to have unit length.
	 *
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Returns:** `Quaternion`

**Calls:**

- `this.conjugate`

<details><summary>Code</summary>

```typescript
invert() {

		return this.conjugate();

	}
```
</details>

### `Quaternion.conjugate(): Quaternion`

**JSDoc:**
```typescript
/**
	 * Returns the rotational conjugate of this quaternion. The conjugate of a
	 * quaternion represents the same rotation in the opposite direction about
	 * the rotational axis.
	 *
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Returns:** `Quaternion`

**Calls:**

- `this._onChangeCallback`

<details><summary>Code</summary>

```typescript
conjugate() {

		this._x *= - 1;
		this._y *= - 1;
		this._z *= - 1;

		this._onChangeCallback();

		return this;

	}
```
</details>

### `Quaternion.dot(v: Quaternion): number`

**JSDoc:**
```typescript
/**
	 * Calculates the dot product of this quaternion and the given one.
	 *
	 * @param {Quaternion} v - The quaternion to compute the dot product with.
	 * @return {number} The result of the dot product.
	 */
```

**Parameters:**

- **`v`** `Quaternion`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
dot( v ) {

		return this._x * v._x + this._y * v._y + this._z * v._z + this._w * v._w;

	}
```
</details>

### `Quaternion.lengthSq(): number`

**JSDoc:**
```typescript
/**
	 * Computes the squared Euclidean length (straight-line length) of this quaternion,
	 * considered as a 4 dimensional vector. This can be useful if you are comparing the
	 * lengths of two quaternions, as this is a slightly more efficient calculation than
	 * {@link Quaternion#length}.
	 *
	 * @return {number} The squared Euclidean length.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
lengthSq() {

		return this._x * this._x + this._y * this._y + this._z * this._z + this._w * this._w;

	}
```
</details>

### `Quaternion.length(): number`

**JSDoc:**
```typescript
/**
	 * Computes the Euclidean length (straight-line length) of this quaternion,
	 * considered as a 4 dimensional vector.
	 *
	 * @return {number} The Euclidean length.
	 */
```

**Returns:** `number`

**Calls:**

- `Math.sqrt`

<details><summary>Code</summary>

```typescript
length() {

		return Math.sqrt( this._x * this._x + this._y * this._y + this._z * this._z + this._w * this._w );

	}
```
</details>

### `Quaternion.normalize(): Quaternion`

**JSDoc:**
```typescript
/**
	 * Normalizes this quaternion - that is, calculated the quaternion that performs
	 * the same rotation as this one, but has a length equal to `1`.
	 *
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Returns:** `Quaternion`

**Calls:**

- `this.length`
- `this._onChangeCallback`

<details><summary>Code</summary>

```typescript
normalize() {

		let l = this.length();

		if ( l === 0 ) {

			this._x = 0;
			this._y = 0;
			this._z = 0;
			this._w = 1;

		} else {

			l = 1 / l;

			this._x = this._x * l;
			this._y = this._y * l;
			this._z = this._z * l;
			this._w = this._w * l;

		}

		this._onChangeCallback();

		return this;

	}
```
</details>

### `Quaternion.multiply(q: Quaternion): Quaternion`

**JSDoc:**
```typescript
/**
	 * Multiplies this quaternion by the given one.
	 *
	 * @param {Quaternion} q - The quaternion.
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Parameters:**

- **`q`** `Quaternion`

**Returns:** `Quaternion`

**Calls:**

- `this.multiplyQuaternions`

<details><summary>Code</summary>

```typescript
multiply( q ) {

		return this.multiplyQuaternions( this, q );

	}
```
</details>

### `Quaternion.premultiply(q: Quaternion): Quaternion`

**JSDoc:**
```typescript
/**
	 * Pre-multiplies this quaternion by the given one.
	 *
	 * @param {Quaternion} q - The quaternion.
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Parameters:**

- **`q`** `Quaternion`

**Returns:** `Quaternion`

**Calls:**

- `this.multiplyQuaternions`

<details><summary>Code</summary>

```typescript
premultiply( q ) {

		return this.multiplyQuaternions( q, this );

	}
```
</details>

### `Quaternion.multiplyQuaternions(a: Quaternion, b: Quaternion): Quaternion`

**JSDoc:**
```typescript
/**
	 * Multiplies the given quaternions and stores the result in this instance.
	 *
	 * @param {Quaternion} a - The first quaternion.
	 * @param {Quaternion} b - The second quaternion.
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Parameters:**

- **`a`** `Quaternion`
- **`b`** `Quaternion`

**Returns:** `Quaternion`

**Calls:**

- `this._onChangeCallback`

**Internal Comments:**
```
// from http://www.euclideanspace.com/maths/algebra/realNormedAlgebra/quaternions/code/index.htm (x2)
```

<details><summary>Code</summary>

```typescript
multiplyQuaternions( a, b ) {

		// from http://www.euclideanspace.com/maths/algebra/realNormedAlgebra/quaternions/code/index.htm

		const qax = a._x, qay = a._y, qaz = a._z, qaw = a._w;
		const qbx = b._x, qby = b._y, qbz = b._z, qbw = b._w;

		this._x = qax * qbw + qaw * qbx + qay * qbz - qaz * qby;
		this._y = qay * qbw + qaw * qby + qaz * qbx - qax * qbz;
		this._z = qaz * qbw + qaw * qbz + qax * qby - qay * qbx;
		this._w = qaw * qbw - qax * qbx - qay * qby - qaz * qbz;

		this._onChangeCallback();

		return this;

	}
```
</details>

### `Quaternion.slerp(qb: Quaternion, t: number): Quaternion`

**JSDoc:**
```typescript
/**
	 * Performs a spherical linear interpolation between quaternions.
	 *
	 * @param {Quaternion} qb - The target quaternion.
	 * @param {number} t - The interpolation factor in the closed interval `[0, 1]`.
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Parameters:**

- **`qb`** `Quaternion`
- **`t`** `number`

**Returns:** `Quaternion`

**Calls:**

- `this.copy`
- `this.normalize`
- `Math.sqrt`
- `Math.atan2`
- `Math.sin`
- `this._onChangeCallback`

**Internal Comments:**
```
// http://www.euclideanspace.com/maths/algebra/realNormedAlgebra/quaternions/slerp/ (x2)
```

<details><summary>Code</summary>

```typescript
slerp( qb, t ) {

		if ( t === 0 ) return this;
		if ( t === 1 ) return this.copy( qb );

		const x = this._x, y = this._y, z = this._z, w = this._w;

		// http://www.euclideanspace.com/maths/algebra/realNormedAlgebra/quaternions/slerp/

		let cosHalfTheta = w * qb._w + x * qb._x + y * qb._y + z * qb._z;

		if ( cosHalfTheta < 0 ) {

			this._w = - qb._w;
			this._x = - qb._x;
			this._y = - qb._y;
			this._z = - qb._z;

			cosHalfTheta = - cosHalfTheta;

		} else {

			this.copy( qb );

		}

		if ( cosHalfTheta >= 1.0 ) {

			this._w = w;
			this._x = x;
			this._y = y;
			this._z = z;

			return this;

		}

		const sqrSinHalfTheta = 1.0 - cosHalfTheta * cosHalfTheta;

		if ( sqrSinHalfTheta <= Number.EPSILON ) {

			const s = 1 - t;
			this._w = s * w + t * this._w;
			this._x = s * x + t * this._x;
			this._y = s * y + t * this._y;
			this._z = s * z + t * this._z;

			this.normalize(); // normalize calls _onChangeCallback()

			return this;

		}

		const sinHalfTheta = Math.sqrt( sqrSinHalfTheta );
		const halfTheta = Math.atan2( sinHalfTheta, cosHalfTheta );
		const ratioA = Math.sin( ( 1 - t ) * halfTheta ) / sinHalfTheta,
			ratioB = Math.sin( t * halfTheta ) / sinHalfTheta;

		this._w = ( w * ratioA + this._w * ratioB );
		this._x = ( x * ratioA + this._x * ratioB );
		this._y = ( y * ratioA + this._y * ratioB );
		this._z = ( z * ratioA + this._z * ratioB );

		this._onChangeCallback();

		return this;

	}
```
</details>

### `Quaternion.slerpQuaternions(qa: Quaternion, qb: Quaternion, t: number): Quaternion`

**JSDoc:**
```typescript
/**
	 * Performs a spherical linear interpolation between the given quaternions
	 * and stores the result in this quaternion.
	 *
	 * @param {Quaternion} qa - The source quaternion.
	 * @param {Quaternion} qb - The target quaternion.
	 * @param {number} t - The interpolation factor in the closed interval `[0, 1]`.
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Parameters:**

- **`qa`** `Quaternion`
- **`qb`** `Quaternion`
- **`t`** `number`

**Returns:** `Quaternion`

**Calls:**

- `this.copy( qa ).slerp`

<details><summary>Code</summary>

```typescript
slerpQuaternions( qa, qb, t ) {

		return this.copy( qa ).slerp( qb, t );

	}
```
</details>

### `Quaternion.random(): Quaternion`

**JSDoc:**
```typescript
/**
	 * Sets this quaternion to a uniformly random, normalized quaternion.
	 *
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Returns:** `Quaternion`

**Calls:**

- `Math.random`
- `Math.sqrt`
- `this.set`
- `Math.sin`
- `Math.cos`

**Internal Comments:**
```
// Ken Shoemake (x2)
// Uniform random rotations (x2)
// D. Kirk, editor, Graphics Gems III, pages 124-132. Academic Press, New York, 1992. (x2)
```

<details><summary>Code</summary>

```typescript
random() {

		// Ken Shoemake
		// Uniform random rotations
		// D. Kirk, editor, Graphics Gems III, pages 124-132. Academic Press, New York, 1992.

		const theta1 = 2 * Math.PI * Math.random();
		const theta2 = 2 * Math.PI * Math.random();

		const x0 = Math.random();
		const r1 = Math.sqrt( 1 - x0 );
		const r2 = Math.sqrt( x0 );

		return this.set(
			r1 * Math.sin( theta1 ),
			r1 * Math.cos( theta1 ),
			r2 * Math.sin( theta2 ),
			r2 * Math.cos( theta2 ),
		);

	}
```
</details>

### `Quaternion.equals(quaternion: Quaternion): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this quaternion is equal with the given one.
	 *
	 * @param {Quaternion} quaternion - The quaternion to test for equality.
	 * @return {boolean} Whether this quaternion is equal with the given one.
	 */
```

**Parameters:**

- **`quaternion`** `Quaternion`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
equals( quaternion ) {

		return ( quaternion._x === this._x ) && ( quaternion._y === this._y ) && ( quaternion._z === this._z ) && ( quaternion._w === this._w );

	}
```
</details>

### `Quaternion.fromArray(array: number[], offset: number): Quaternion`

**JSDoc:**
```typescript
/**
	 * Sets this quaternion's components from the given array.
	 *
	 * @param {Array<number>} array - An array holding the quaternion component values.
	 * @param {number} [offset=0] - The offset into the array.
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Parameters:**

- **`array`** `number[]`
- **`offset`** `number`

**Returns:** `Quaternion`

**Calls:**

- `this._onChangeCallback`

<details><summary>Code</summary>

```typescript
fromArray( array, offset = 0 ) {

		this._x = array[ offset ];
		this._y = array[ offset + 1 ];
		this._z = array[ offset + 2 ];
		this._w = array[ offset + 3 ];

		this._onChangeCallback();

		return this;

	}
```
</details>

### `Quaternion.toArray(array: number[], offset: number): number[]`

**JSDoc:**
```typescript
/**
	 * Writes the components of this quaternion to the given array. If no array is provided,
	 * the method returns a new instance.
	 *
	 * @param {Array<number>} [array=[]] - The target array holding the quaternion components.
	 * @param {number} [offset=0] - Index of the first element in the array.
	 * @return {Array<number>} The quaternion components.
	 */
```

**Parameters:**

- **`array`** `number[]`
- **`offset`** `number`

**Returns:** `number[]`

<details><summary>Code</summary>

```typescript
toArray( array = [], offset = 0 ) {

		array[ offset ] = this._x;
		array[ offset + 1 ] = this._y;
		array[ offset + 2 ] = this._z;
		array[ offset + 3 ] = this._w;

		return array;

	}
```
</details>

### `Quaternion.fromBufferAttribute(attribute: BufferAttribute, index: number): Quaternion`

**JSDoc:**
```typescript
/**
	 * Sets the components of this quaternion from the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute holding quaternion data.
	 * @param {number} index - The index into the attribute.
	 * @return {Quaternion} A reference to this quaternion.
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`
- **`index`** `number`

**Returns:** `Quaternion`

**Calls:**

- `attribute.getX`
- `attribute.getY`
- `attribute.getZ`
- `attribute.getW`
- `this._onChangeCallback`

<details><summary>Code</summary>

```typescript
fromBufferAttribute( attribute, index ) {

		this._x = attribute.getX( index );
		this._y = attribute.getY( index );
		this._z = attribute.getZ( index );
		this._w = attribute.getW( index );

		this._onChangeCallback();

		return this;

	}
```
</details>

### `Quaternion.toJSON(): number[]`

**JSDoc:**
```typescript
/**
	 * This methods defines the serialization result of this class. Returns the
	 * numerical elements of this quaternion in an array of format `[x, y, z, w]`.
	 *
	 * @return {Array<number>} The serialized quaternion.
	 */
```

**Returns:** `number[]`

**Calls:**

- `this.toArray`

<details><summary>Code</summary>

```typescript
toJSON() {

		return this.toArray();

	}
```
</details>

### `Quaternion._onChange(callback: any): this`

**Parameters:**

- **`callback`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
_onChange( callback ) {

		this._onChangeCallback = callback;

		return this;

	}
```
</details>

### `Quaternion._onChangeCallback(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
_onChangeCallback() {}
```
</details>

### `Quaternion.[ Symbol.iterator ](): Generator<number, void, unknown>`

**Returns:** `Generator<number, void, unknown>`

<details><summary>Code</summary>

```typescript
*[ Symbol.iterator ]() {

		yield this._x;
		yield this._y;
		yield this._z;
		yield this._w;

	}
```
</details>


---

## Classes

### `Quaternion`

<details><summary>Class Code</summary>

```ts
class Quaternion {

	/**
	 * Constructs a new quaternion.
	 *
	 * @param {number} [x=0] - The x value of this quaternion.
	 * @param {number} [y=0] - The y value of this quaternion.
	 * @param {number} [z=0] - The z value of this quaternion.
	 * @param {number} [w=1] - The w value of this quaternion.
	 */
	constructor( x = 0, y = 0, z = 0, w = 1 ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isQuaternion = true;

		this._x = x;
		this._y = y;
		this._z = z;
		this._w = w;

	}

	/**
	 * Interpolates between two quaternions via SLERP. This implementation assumes the
	 * quaternion data are managed  in flat arrays.
	 *
	 * @param {Array<number>} dst - The destination array.
	 * @param {number} dstOffset - An offset into the destination array.
	 * @param {Array<number>} src0 - The source array of the first quaternion.
	 * @param {number} srcOffset0 - An offset into the first source array.
	 * @param {Array<number>} src1 -  The source array of the second quaternion.
	 * @param {number} srcOffset1 - An offset into the second source array.
	 * @param {number} t - The interpolation factor in the range `[0,1]`.
	 * @see {@link Quaternion#slerp}
	 */
	static slerpFlat( dst, dstOffset, src0, srcOffset0, src1, srcOffset1, t ) {

		// fuzz-free, array-based Quaternion SLERP operation

		let x0 = src0[ srcOffset0 + 0 ],
			y0 = src0[ srcOffset0 + 1 ],
			z0 = src0[ srcOffset0 + 2 ],
			w0 = src0[ srcOffset0 + 3 ];

		const x1 = src1[ srcOffset1 + 0 ],
			y1 = src1[ srcOffset1 + 1 ],
			z1 = src1[ srcOffset1 + 2 ],
			w1 = src1[ srcOffset1 + 3 ];

		if ( t === 0 ) {

			dst[ dstOffset + 0 ] = x0;
			dst[ dstOffset + 1 ] = y0;
			dst[ dstOffset + 2 ] = z0;
			dst[ dstOffset + 3 ] = w0;
			return;

		}

		if ( t === 1 ) {

			dst[ dstOffset + 0 ] = x1;
			dst[ dstOffset + 1 ] = y1;
			dst[ dstOffset + 2 ] = z1;
			dst[ dstOffset + 3 ] = w1;
			return;

		}

		if ( w0 !== w1 || x0 !== x1 || y0 !== y1 || z0 !== z1 ) {

			let s = 1 - t;
			const cos = x0 * x1 + y0 * y1 + z0 * z1 + w0 * w1,
				dir = ( cos >= 0 ? 1 : - 1 ),
				sqrSin = 1 - cos * cos;

			// Skip the Slerp for tiny steps to avoid numeric problems:
			if ( sqrSin > Number.EPSILON ) {

				const sin = Math.sqrt( sqrSin ),
					len = Math.atan2( sin, cos * dir );

				s = Math.sin( s * len ) / sin;
				t = Math.sin( t * len ) / sin;

			}

			const tDir = t * dir;

			x0 = x0 * s + x1 * tDir;
			y0 = y0 * s + y1 * tDir;
			z0 = z0 * s + z1 * tDir;
			w0 = w0 * s + w1 * tDir;

			// Normalize in case we just did a lerp:
			if ( s === 1 - t ) {

				const f = 1 / Math.sqrt( x0 * x0 + y0 * y0 + z0 * z0 + w0 * w0 );

				x0 *= f;
				y0 *= f;
				z0 *= f;
				w0 *= f;

			}

		}

		dst[ dstOffset ] = x0;
		dst[ dstOffset + 1 ] = y0;
		dst[ dstOffset + 2 ] = z0;
		dst[ dstOffset + 3 ] = w0;

	}

	/**
	 * Multiplies two quaternions. This implementation assumes the quaternion data are managed
	 * in flat arrays.
	 *
	 * @param {Array<number>} dst - The destination array.
	 * @param {number} dstOffset - An offset into the destination array.
	 * @param {Array<number>} src0 - The source array of the first quaternion.
	 * @param {number} srcOffset0 - An offset into the first source array.
	 * @param {Array<number>} src1 -  The source array of the second quaternion.
	 * @param {number} srcOffset1 - An offset into the second source array.
	 * @return {Array<number>} The destination array.
	 * @see {@link Quaternion#multiplyQuaternions}.
	 */
	static multiplyQuaternionsFlat( dst, dstOffset, src0, srcOffset0, src1, srcOffset1 ) {

		const x0 = src0[ srcOffset0 ];
		const y0 = src0[ srcOffset0 + 1 ];
		const z0 = src0[ srcOffset0 + 2 ];
		const w0 = src0[ srcOffset0 + 3 ];

		const x1 = src1[ srcOffset1 ];
		const y1 = src1[ srcOffset1 + 1 ];
		const z1 = src1[ srcOffset1 + 2 ];
		const w1 = src1[ srcOffset1 + 3 ];

		dst[ dstOffset ] = x0 * w1 + w0 * x1 + y0 * z1 - z0 * y1;
		dst[ dstOffset + 1 ] = y0 * w1 + w0 * y1 + z0 * x1 - x0 * z1;
		dst[ dstOffset + 2 ] = z0 * w1 + w0 * z1 + x0 * y1 - y0 * x1;
		dst[ dstOffset + 3 ] = w0 * w1 - x0 * x1 - y0 * y1 - z0 * z1;

		return dst;

	}

	/**
	 * The x value of this quaternion.
	 *
	 * @type {number}
	 * @default 0
	 */
	get x() {

		return this._x;

	}

	set x( value ) {

		this._x = value;
		this._onChangeCallback();

	}

	/**
	 * The y value of this quaternion.
	 *
	 * @type {number}
	 * @default 0
	 */
	get y() {

		return this._y;

	}

	set y( value ) {

		this._y = value;
		this._onChangeCallback();

	}

	/**
	 * The z value of this quaternion.
	 *
	 * @type {number}
	 * @default 0
	 */
	get z() {

		return this._z;

	}

	set z( value ) {

		this._z = value;
		this._onChangeCallback();

	}

	/**
	 * The w value of this quaternion.
	 *
	 * @type {number}
	 * @default 1
	 */
	get w() {

		return this._w;

	}

	set w( value ) {

		this._w = value;
		this._onChangeCallback();

	}

	/**
	 * Sets the quaternion components.
	 *
	 * @param {number} x - The x value of this quaternion.
	 * @param {number} y - The y value of this quaternion.
	 * @param {number} z - The z value of this quaternion.
	 * @param {number} w - The w value of this quaternion.
	 * @return {Quaternion} A reference to this quaternion.
	 */
	set( x, y, z, w ) {

		this._x = x;
		this._y = y;
		this._z = z;
		this._w = w;

		this._onChangeCallback();

		return this;

	}

	/**
	 * Returns a new quaternion with copied values from this instance.
	 *
	 * @return {Quaternion} A clone of this instance.
	 */
	clone() {

		return new this.constructor( this._x, this._y, this._z, this._w );

	}

	/**
	 * Copies the values of the given quaternion to this instance.
	 *
	 * @param {Quaternion} quaternion - The quaternion to copy.
	 * @return {Quaternion} A reference to this quaternion.
	 */
	copy( quaternion ) {

		this._x = quaternion.x;
		this._y = quaternion.y;
		this._z = quaternion.z;
		this._w = quaternion.w;

		this._onChangeCallback();

		return this;

	}

	/**
	 * Sets this quaternion from the rotation specified by the given
	 * Euler angles.
	 *
	 * @param {Euler} euler - The Euler angles.
	 * @param {boolean} [update=true] - Whether the internal `onChange` callback should be executed or not.
	 * @return {Quaternion} A reference to this quaternion.
	 */
	setFromEuler( euler, update = true ) {

		const x = euler._x, y = euler._y, z = euler._z, order = euler._order;

		// http://www.mathworks.com/matlabcentral/fileexchange/
		// 	20696-function-to-convert-between-dcm-euler-angles-quaternions-and-euler-vectors/
		//	content/SpinCalc.m

		const cos = Math.cos;
		const sin = Math.sin;

		const c1 = cos( x / 2 );
		const c2 = cos( y / 2 );
		const c3 = cos( z / 2 );

		const s1 = sin( x / 2 );
		const s2 = sin( y / 2 );
		const s3 = sin( z / 2 );

		switch ( order ) {

			case 'XYZ':
				this._x = s1 * c2 * c3 + c1 * s2 * s3;
				this._y = c1 * s2 * c3 - s1 * c2 * s3;
				this._z = c1 * c2 * s3 + s1 * s2 * c3;
				this._w = c1 * c2 * c3 - s1 * s2 * s3;
				break;

			case 'YXZ':
				this._x = s1 * c2 * c3 + c1 * s2 * s3;
				this._y = c1 * s2 * c3 - s1 * c2 * s3;
				this._z = c1 * c2 * s3 - s1 * s2 * c3;
				this._w = c1 * c2 * c3 + s1 * s2 * s3;
				break;

			case 'ZXY':
				this._x = s1 * c2 * c3 - c1 * s2 * s3;
				this._y = c1 * s2 * c3 + s1 * c2 * s3;
				this._z = c1 * c2 * s3 + s1 * s2 * c3;
				this._w = c1 * c2 * c3 - s1 * s2 * s3;
				break;

			case 'ZYX':
				this._x = s1 * c2 * c3 - c1 * s2 * s3;
				this._y = c1 * s2 * c3 + s1 * c2 * s3;
				this._z = c1 * c2 * s3 - s1 * s2 * c3;
				this._w = c1 * c2 * c3 + s1 * s2 * s3;
				break;

			case 'YZX':
				this._x = s1 * c2 * c3 + c1 * s2 * s3;
				this._y = c1 * s2 * c3 + s1 * c2 * s3;
				this._z = c1 * c2 * s3 - s1 * s2 * c3;
				this._w = c1 * c2 * c3 - s1 * s2 * s3;
				break;

			case 'XZY':
				this._x = s1 * c2 * c3 - c1 * s2 * s3;
				this._y = c1 * s2 * c3 - s1 * c2 * s3;
				this._z = c1 * c2 * s3 + s1 * s2 * c3;
				this._w = c1 * c2 * c3 + s1 * s2 * s3;
				break;

			default:
				console.warn( 'THREE.Quaternion: .setFromEuler() encountered an unknown order: ' + order );

		}

		if ( update === true ) this._onChangeCallback();

		return this;

	}

	/**
	 * Sets this quaternion from the given axis and angle.
	 *
	 * @param {Vector3} axis - The normalized axis.
	 * @param {number} angle - The angle in radians.
	 * @return {Quaternion} A reference to this quaternion.
	 */
	setFromAxisAngle( axis, angle ) {

		// http://www.euclideanspace.com/maths/geometry/rotations/conversions/angleToQuaternion/index.htm

		const halfAngle = angle / 2, s = Math.sin( halfAngle );

		this._x = axis.x * s;
		this._y = axis.y * s;
		this._z = axis.z * s;
		this._w = Math.cos( halfAngle );

		this._onChangeCallback();

		return this;

	}

	/**
	 * Sets this quaternion from the given rotation matrix.
	 *
	 * @param {Matrix4} m - A 4x4 matrix of which the upper 3x3 of matrix is a pure rotation matrix (i.e. unscaled).
	 * @return {Quaternion} A reference to this quaternion.
	 */
	setFromRotationMatrix( m ) {

		// http://www.euclideanspace.com/maths/geometry/rotations/conversions/matrixToQuaternion/index.htm

		// assumes the upper 3x3 of m is a pure rotation matrix (i.e, unscaled)

		const te = m.elements,

			m11 = te[ 0 ], m12 = te[ 4 ], m13 = te[ 8 ],
			m21 = te[ 1 ], m22 = te[ 5 ], m23 = te[ 9 ],
			m31 = te[ 2 ], m32 = te[ 6 ], m33 = te[ 10 ],

			trace = m11 + m22 + m33;

		if ( trace > 0 ) {

			const s = 0.5 / Math.sqrt( trace + 1.0 );

			this._w = 0.25 / s;
			this._x = ( m32 - m23 ) * s;
			this._y = ( m13 - m31 ) * s;
			this._z = ( m21 - m12 ) * s;

		} else if ( m11 > m22 && m11 > m33 ) {

			const s = 2.0 * Math.sqrt( 1.0 + m11 - m22 - m33 );

			this._w = ( m32 - m23 ) / s;
			this._x = 0.25 * s;
			this._y = ( m12 + m21 ) / s;
			this._z = ( m13 + m31 ) / s;

		} else if ( m22 > m33 ) {

			const s = 2.0 * Math.sqrt( 1.0 + m22 - m11 - m33 );

			this._w = ( m13 - m31 ) / s;
			this._x = ( m12 + m21 ) / s;
			this._y = 0.25 * s;
			this._z = ( m23 + m32 ) / s;

		} else {

			const s = 2.0 * Math.sqrt( 1.0 + m33 - m11 - m22 );

			this._w = ( m21 - m12 ) / s;
			this._x = ( m13 + m31 ) / s;
			this._y = ( m23 + m32 ) / s;
			this._z = 0.25 * s;

		}

		this._onChangeCallback();

		return this;

	}

	/**
	 * Sets this quaternion to the rotation required to rotate the direction vector
	 * `vFrom` to the direction vector `vTo`.
	 *
	 * @param {Vector3} vFrom - The first (normalized) direction vector.
	 * @param {Vector3} vTo - The second (normalized) direction vector.
	 * @return {Quaternion} A reference to this quaternion.
	 */
	setFromUnitVectors( vFrom, vTo ) {

		// assumes direction vectors vFrom and vTo are normalized

		let r = vFrom.dot( vTo ) + 1;

		if ( r < 1e-8 ) { // the epsilon value has been discussed in #31286

			// vFrom and vTo point in opposite directions

			r = 0;

			if ( Math.abs( vFrom.x ) > Math.abs( vFrom.z ) ) {

				this._x = - vFrom.y;
				this._y = vFrom.x;
				this._z = 0;
				this._w = r;

			} else {

				this._x = 0;
				this._y = - vFrom.z;
				this._z = vFrom.y;
				this._w = r;

			}

		} else {

			// crossVectors( vFrom, vTo ); // inlined to avoid cyclic dependency on Vector3

			this._x = vFrom.y * vTo.z - vFrom.z * vTo.y;
			this._y = vFrom.z * vTo.x - vFrom.x * vTo.z;
			this._z = vFrom.x * vTo.y - vFrom.y * vTo.x;
			this._w = r;

		}

		return this.normalize();

	}

	/**
	 * Returns the angle between this quaternion and the given one in radians.
	 *
	 * @param {Quaternion} q - The quaternion to compute the angle with.
	 * @return {number} The angle in radians.
	 */
	angleTo( q ) {

		return 2 * Math.acos( Math.abs( clamp( this.dot( q ), - 1, 1 ) ) );

	}

	/**
	 * Rotates this quaternion by a given angular step to the given quaternion.
	 * The method ensures that the final quaternion will not overshoot `q`.
	 *
	 * @param {Quaternion} q - The target quaternion.
	 * @param {number} step - The angular step in radians.
	 * @return {Quaternion} A reference to this quaternion.
	 */
	rotateTowards( q, step ) {

		const angle = this.angleTo( q );

		if ( angle === 0 ) return this;

		const t = Math.min( 1, step / angle );

		this.slerp( q, t );

		return this;

	}

	/**
	 * Sets this quaternion to the identity quaternion; that is, to the
	 * quaternion that represents "no rotation".
	 *
	 * @return {Quaternion} A reference to this quaternion.
	 */
	identity() {

		return this.set( 0, 0, 0, 1 );

	}

	/**
	 * Inverts this quaternion via {@link Quaternion#conjugate}. The
	 * quaternion is assumed to have unit length.
	 *
	 * @return {Quaternion} A reference to this quaternion.
	 */
	invert() {

		return this.conjugate();

	}

	/**
	 * Returns the rotational conjugate of this quaternion. The conjugate of a
	 * quaternion represents the same rotation in the opposite direction about
	 * the rotational axis.
	 *
	 * @return {Quaternion} A reference to this quaternion.
	 */
	conjugate() {

		this._x *= - 1;
		this._y *= - 1;
		this._z *= - 1;

		this._onChangeCallback();

		return this;

	}

	/**
	 * Calculates the dot product of this quaternion and the given one.
	 *
	 * @param {Quaternion} v - The quaternion to compute the dot product with.
	 * @return {number} The result of the dot product.
	 */
	dot( v ) {

		return this._x * v._x + this._y * v._y + this._z * v._z + this._w * v._w;

	}

	/**
	 * Computes the squared Euclidean length (straight-line length) of this quaternion,
	 * considered as a 4 dimensional vector. This can be useful if you are comparing the
	 * lengths of two quaternions, as this is a slightly more efficient calculation than
	 * {@link Quaternion#length}.
	 *
	 * @return {number} The squared Euclidean length.
	 */
	lengthSq() {

		return this._x * this._x + this._y * this._y + this._z * this._z + this._w * this._w;

	}

	/**
	 * Computes the Euclidean length (straight-line length) of this quaternion,
	 * considered as a 4 dimensional vector.
	 *
	 * @return {number} The Euclidean length.
	 */
	length() {

		return Math.sqrt( this._x * this._x + this._y * this._y + this._z * this._z + this._w * this._w );

	}

	/**
	 * Normalizes this quaternion - that is, calculated the quaternion that performs
	 * the same rotation as this one, but has a length equal to `1`.
	 *
	 * @return {Quaternion} A reference to this quaternion.
	 */
	normalize() {

		let l = this.length();

		if ( l === 0 ) {

			this._x = 0;
			this._y = 0;
			this._z = 0;
			this._w = 1;

		} else {

			l = 1 / l;

			this._x = this._x * l;
			this._y = this._y * l;
			this._z = this._z * l;
			this._w = this._w * l;

		}

		this._onChangeCallback();

		return this;

	}

	/**
	 * Multiplies this quaternion by the given one.
	 *
	 * @param {Quaternion} q - The quaternion.
	 * @return {Quaternion} A reference to this quaternion.
	 */
	multiply( q ) {

		return this.multiplyQuaternions( this, q );

	}

	/**
	 * Pre-multiplies this quaternion by the given one.
	 *
	 * @param {Quaternion} q - The quaternion.
	 * @return {Quaternion} A reference to this quaternion.
	 */
	premultiply( q ) {

		return this.multiplyQuaternions( q, this );

	}

	/**
	 * Multiplies the given quaternions and stores the result in this instance.
	 *
	 * @param {Quaternion} a - The first quaternion.
	 * @param {Quaternion} b - The second quaternion.
	 * @return {Quaternion} A reference to this quaternion.
	 */
	multiplyQuaternions( a, b ) {

		// from http://www.euclideanspace.com/maths/algebra/realNormedAlgebra/quaternions/code/index.htm

		const qax = a._x, qay = a._y, qaz = a._z, qaw = a._w;
		const qbx = b._x, qby = b._y, qbz = b._z, qbw = b._w;

		this._x = qax * qbw + qaw * qbx + qay * qbz - qaz * qby;
		this._y = qay * qbw + qaw * qby + qaz * qbx - qax * qbz;
		this._z = qaz * qbw + qaw * qbz + qax * qby - qay * qbx;
		this._w = qaw * qbw - qax * qbx - qay * qby - qaz * qbz;

		this._onChangeCallback();

		return this;

	}

	/**
	 * Performs a spherical linear interpolation between quaternions.
	 *
	 * @param {Quaternion} qb - The target quaternion.
	 * @param {number} t - The interpolation factor in the closed interval `[0, 1]`.
	 * @return {Quaternion} A reference to this quaternion.
	 */
	slerp( qb, t ) {

		if ( t === 0 ) return this;
		if ( t === 1 ) return this.copy( qb );

		const x = this._x, y = this._y, z = this._z, w = this._w;

		// http://www.euclideanspace.com/maths/algebra/realNormedAlgebra/quaternions/slerp/

		let cosHalfTheta = w * qb._w + x * qb._x + y * qb._y + z * qb._z;

		if ( cosHalfTheta < 0 ) {

			this._w = - qb._w;
			this._x = - qb._x;
			this._y = - qb._y;
			this._z = - qb._z;

			cosHalfTheta = - cosHalfTheta;

		} else {

			this.copy( qb );

		}

		if ( cosHalfTheta >= 1.0 ) {

			this._w = w;
			this._x = x;
			this._y = y;
			this._z = z;

			return this;

		}

		const sqrSinHalfTheta = 1.0 - cosHalfTheta * cosHalfTheta;

		if ( sqrSinHalfTheta <= Number.EPSILON ) {

			const s = 1 - t;
			this._w = s * w + t * this._w;
			this._x = s * x + t * this._x;
			this._y = s * y + t * this._y;
			this._z = s * z + t * this._z;

			this.normalize(); // normalize calls _onChangeCallback()

			return this;

		}

		const sinHalfTheta = Math.sqrt( sqrSinHalfTheta );
		const halfTheta = Math.atan2( sinHalfTheta, cosHalfTheta );
		const ratioA = Math.sin( ( 1 - t ) * halfTheta ) / sinHalfTheta,
			ratioB = Math.sin( t * halfTheta ) / sinHalfTheta;

		this._w = ( w * ratioA + this._w * ratioB );
		this._x = ( x * ratioA + this._x * ratioB );
		this._y = ( y * ratioA + this._y * ratioB );
		this._z = ( z * ratioA + this._z * ratioB );

		this._onChangeCallback();

		return this;

	}

	/**
	 * Performs a spherical linear interpolation between the given quaternions
	 * and stores the result in this quaternion.
	 *
	 * @param {Quaternion} qa - The source quaternion.
	 * @param {Quaternion} qb - The target quaternion.
	 * @param {number} t - The interpolation factor in the closed interval `[0, 1]`.
	 * @return {Quaternion} A reference to this quaternion.
	 */
	slerpQuaternions( qa, qb, t ) {

		return this.copy( qa ).slerp( qb, t );

	}

	/**
	 * Sets this quaternion to a uniformly random, normalized quaternion.
	 *
	 * @return {Quaternion} A reference to this quaternion.
	 */
	random() {

		// Ken Shoemake
		// Uniform random rotations
		// D. Kirk, editor, Graphics Gems III, pages 124-132. Academic Press, New York, 1992.

		const theta1 = 2 * Math.PI * Math.random();
		const theta2 = 2 * Math.PI * Math.random();

		const x0 = Math.random();
		const r1 = Math.sqrt( 1 - x0 );
		const r2 = Math.sqrt( x0 );

		return this.set(
			r1 * Math.sin( theta1 ),
			r1 * Math.cos( theta1 ),
			r2 * Math.sin( theta2 ),
			r2 * Math.cos( theta2 ),
		);

	}

	/**
	 * Returns `true` if this quaternion is equal with the given one.
	 *
	 * @param {Quaternion} quaternion - The quaternion to test for equality.
	 * @return {boolean} Whether this quaternion is equal with the given one.
	 */
	equals( quaternion ) {

		return ( quaternion._x === this._x ) && ( quaternion._y === this._y ) && ( quaternion._z === this._z ) && ( quaternion._w === this._w );

	}

	/**
	 * Sets this quaternion's components from the given array.
	 *
	 * @param {Array<number>} array - An array holding the quaternion component values.
	 * @param {number} [offset=0] - The offset into the array.
	 * @return {Quaternion} A reference to this quaternion.
	 */
	fromArray( array, offset = 0 ) {

		this._x = array[ offset ];
		this._y = array[ offset + 1 ];
		this._z = array[ offset + 2 ];
		this._w = array[ offset + 3 ];

		this._onChangeCallback();

		return this;

	}

	/**
	 * Writes the components of this quaternion to the given array. If no array is provided,
	 * the method returns a new instance.
	 *
	 * @param {Array<number>} [array=[]] - The target array holding the quaternion components.
	 * @param {number} [offset=0] - Index of the first element in the array.
	 * @return {Array<number>} The quaternion components.
	 */
	toArray( array = [], offset = 0 ) {

		array[ offset ] = this._x;
		array[ offset + 1 ] = this._y;
		array[ offset + 2 ] = this._z;
		array[ offset + 3 ] = this._w;

		return array;

	}

	/**
	 * Sets the components of this quaternion from the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute holding quaternion data.
	 * @param {number} index - The index into the attribute.
	 * @return {Quaternion} A reference to this quaternion.
	 */
	fromBufferAttribute( attribute, index ) {

		this._x = attribute.getX( index );
		this._y = attribute.getY( index );
		this._z = attribute.getZ( index );
		this._w = attribute.getW( index );

		this._onChangeCallback();

		return this;

	}

	/**
	 * This methods defines the serialization result of this class. Returns the
	 * numerical elements of this quaternion in an array of format `[x, y, z, w]`.
	 *
	 * @return {Array<number>} The serialized quaternion.
	 */
	toJSON() {

		return this.toArray();

	}

	_onChange( callback ) {

		this._onChangeCallback = callback;

		return this;

	}

	_onChangeCallback() {}

	*[ Symbol.iterator ]() {

		yield this._x;
		yield this._y;
		yield this._z;
		yield this._w;

	}

}
```
</details>

#### Methods

##### `slerpFlat(dst: number[], dstOffset: number, src0: number[], srcOffset0: number, src1: number[], srcOffset1: number, t: number): void`

<details><summary>Code</summary>

```ts
static slerpFlat( dst, dstOffset, src0, srcOffset0, src1, srcOffset1, t ) {

		// fuzz-free, array-based Quaternion SLERP operation

		let x0 = src0[ srcOffset0 + 0 ],
			y0 = src0[ srcOffset0 + 1 ],
			z0 = src0[ srcOffset0 + 2 ],
			w0 = src0[ srcOffset0 + 3 ];

		const x1 = src1[ srcOffset1 + 0 ],
			y1 = src1[ srcOffset1 + 1 ],
			z1 = src1[ srcOffset1 + 2 ],
			w1 = src1[ srcOffset1 + 3 ];

		if ( t === 0 ) {

			dst[ dstOffset + 0 ] = x0;
			dst[ dstOffset + 1 ] = y0;
			dst[ dstOffset + 2 ] = z0;
			dst[ dstOffset + 3 ] = w0;
			return;

		}

		if ( t === 1 ) {

			dst[ dstOffset + 0 ] = x1;
			dst[ dstOffset + 1 ] = y1;
			dst[ dstOffset + 2 ] = z1;
			dst[ dstOffset + 3 ] = w1;
			return;

		}

		if ( w0 !== w1 || x0 !== x1 || y0 !== y1 || z0 !== z1 ) {

			let s = 1 - t;
			const cos = x0 * x1 + y0 * y1 + z0 * z1 + w0 * w1,
				dir = ( cos >= 0 ? 1 : - 1 ),
				sqrSin = 1 - cos * cos;

			// Skip the Slerp for tiny steps to avoid numeric problems:
			if ( sqrSin > Number.EPSILON ) {

				const sin = Math.sqrt( sqrSin ),
					len = Math.atan2( sin, cos * dir );

				s = Math.sin( s * len ) / sin;
				t = Math.sin( t * len ) / sin;

			}

			const tDir = t * dir;

			x0 = x0 * s + x1 * tDir;
			y0 = y0 * s + y1 * tDir;
			z0 = z0 * s + z1 * tDir;
			w0 = w0 * s + w1 * tDir;

			// Normalize in case we just did a lerp:
			if ( s === 1 - t ) {

				const f = 1 / Math.sqrt( x0 * x0 + y0 * y0 + z0 * z0 + w0 * w0 );

				x0 *= f;
				y0 *= f;
				z0 *= f;
				w0 *= f;

			}

		}

		dst[ dstOffset ] = x0;
		dst[ dstOffset + 1 ] = y0;
		dst[ dstOffset + 2 ] = z0;
		dst[ dstOffset + 3 ] = w0;

	}
```
</details>

##### `multiplyQuaternionsFlat(dst: number[], dstOffset: number, src0: number[], srcOffset0: number, src1: number[], srcOffset1: number): number[]`

<details><summary>Code</summary>

```ts
static multiplyQuaternionsFlat( dst, dstOffset, src0, srcOffset0, src1, srcOffset1 ) {

		const x0 = src0[ srcOffset0 ];
		const y0 = src0[ srcOffset0 + 1 ];
		const z0 = src0[ srcOffset0 + 2 ];
		const w0 = src0[ srcOffset0 + 3 ];

		const x1 = src1[ srcOffset1 ];
		const y1 = src1[ srcOffset1 + 1 ];
		const z1 = src1[ srcOffset1 + 2 ];
		const w1 = src1[ srcOffset1 + 3 ];

		dst[ dstOffset ] = x0 * w1 + w0 * x1 + y0 * z1 - z0 * y1;
		dst[ dstOffset + 1 ] = y0 * w1 + w0 * y1 + z0 * x1 - x0 * z1;
		dst[ dstOffset + 2 ] = z0 * w1 + w0 * z1 + x0 * y1 - y0 * x1;
		dst[ dstOffset + 3 ] = w0 * w1 - x0 * x1 - y0 * y1 - z0 * z1;

		return dst;

	}
```
</details>

##### `set(x: number, y: number, z: number, w: number): Quaternion`

<details><summary>Code</summary>

```ts
set( x, y, z, w ) {

		this._x = x;
		this._y = y;
		this._z = z;
		this._w = w;

		this._onChangeCallback();

		return this;

	}
```
</details>

##### `clone(): Quaternion`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor( this._x, this._y, this._z, this._w );

	}
```
</details>

##### `copy(quaternion: Quaternion): Quaternion`

<details><summary>Code</summary>

```ts
copy( quaternion ) {

		this._x = quaternion.x;
		this._y = quaternion.y;
		this._z = quaternion.z;
		this._w = quaternion.w;

		this._onChangeCallback();

		return this;

	}
```
</details>

##### `setFromEuler(euler: Euler, update: boolean): Quaternion`

<details><summary>Code</summary>

```ts
setFromEuler( euler, update = true ) {

		const x = euler._x, y = euler._y, z = euler._z, order = euler._order;

		// http://www.mathworks.com/matlabcentral/fileexchange/
		// 	20696-function-to-convert-between-dcm-euler-angles-quaternions-and-euler-vectors/
		//	content/SpinCalc.m

		const cos = Math.cos;
		const sin = Math.sin;

		const c1 = cos( x / 2 );
		const c2 = cos( y / 2 );
		const c3 = cos( z / 2 );

		const s1 = sin( x / 2 );
		const s2 = sin( y / 2 );
		const s3 = sin( z / 2 );

		switch ( order ) {

			case 'XYZ':
				this._x = s1 * c2 * c3 + c1 * s2 * s3;
				this._y = c1 * s2 * c3 - s1 * c2 * s3;
				this._z = c1 * c2 * s3 + s1 * s2 * c3;
				this._w = c1 * c2 * c3 - s1 * s2 * s3;
				break;

			case 'YXZ':
				this._x = s1 * c2 * c3 + c1 * s2 * s3;
				this._y = c1 * s2 * c3 - s1 * c2 * s3;
				this._z = c1 * c2 * s3 - s1 * s2 * c3;
				this._w = c1 * c2 * c3 + s1 * s2 * s3;
				break;

			case 'ZXY':
				this._x = s1 * c2 * c3 - c1 * s2 * s3;
				this._y = c1 * s2 * c3 + s1 * c2 * s3;
				this._z = c1 * c2 * s3 + s1 * s2 * c3;
				this._w = c1 * c2 * c3 - s1 * s2 * s3;
				break;

			case 'ZYX':
				this._x = s1 * c2 * c3 - c1 * s2 * s3;
				this._y = c1 * s2 * c3 + s1 * c2 * s3;
				this._z = c1 * c2 * s3 - s1 * s2 * c3;
				this._w = c1 * c2 * c3 + s1 * s2 * s3;
				break;

			case 'YZX':
				this._x = s1 * c2 * c3 + c1 * s2 * s3;
				this._y = c1 * s2 * c3 + s1 * c2 * s3;
				this._z = c1 * c2 * s3 - s1 * s2 * c3;
				this._w = c1 * c2 * c3 - s1 * s2 * s3;
				break;

			case 'XZY':
				this._x = s1 * c2 * c3 - c1 * s2 * s3;
				this._y = c1 * s2 * c3 - s1 * c2 * s3;
				this._z = c1 * c2 * s3 + s1 * s2 * c3;
				this._w = c1 * c2 * c3 + s1 * s2 * s3;
				break;

			default:
				console.warn( 'THREE.Quaternion: .setFromEuler() encountered an unknown order: ' + order );

		}

		if ( update === true ) this._onChangeCallback();

		return this;

	}
```
</details>

##### `setFromAxisAngle(axis: Vector3, angle: number): Quaternion`

<details><summary>Code</summary>

```ts
setFromAxisAngle( axis, angle ) {

		// http://www.euclideanspace.com/maths/geometry/rotations/conversions/angleToQuaternion/index.htm

		const halfAngle = angle / 2, s = Math.sin( halfAngle );

		this._x = axis.x * s;
		this._y = axis.y * s;
		this._z = axis.z * s;
		this._w = Math.cos( halfAngle );

		this._onChangeCallback();

		return this;

	}
```
</details>

##### `setFromRotationMatrix(m: Matrix4): Quaternion`

<details><summary>Code</summary>

```ts
setFromRotationMatrix( m ) {

		// http://www.euclideanspace.com/maths/geometry/rotations/conversions/matrixToQuaternion/index.htm

		// assumes the upper 3x3 of m is a pure rotation matrix (i.e, unscaled)

		const te = m.elements,

			m11 = te[ 0 ], m12 = te[ 4 ], m13 = te[ 8 ],
			m21 = te[ 1 ], m22 = te[ 5 ], m23 = te[ 9 ],
			m31 = te[ 2 ], m32 = te[ 6 ], m33 = te[ 10 ],

			trace = m11 + m22 + m33;

		if ( trace > 0 ) {

			const s = 0.5 / Math.sqrt( trace + 1.0 );

			this._w = 0.25 / s;
			this._x = ( m32 - m23 ) * s;
			this._y = ( m13 - m31 ) * s;
			this._z = ( m21 - m12 ) * s;

		} else if ( m11 > m22 && m11 > m33 ) {

			const s = 2.0 * Math.sqrt( 1.0 + m11 - m22 - m33 );

			this._w = ( m32 - m23 ) / s;
			this._x = 0.25 * s;
			this._y = ( m12 + m21 ) / s;
			this._z = ( m13 + m31 ) / s;

		} else if ( m22 > m33 ) {

			const s = 2.0 * Math.sqrt( 1.0 + m22 - m11 - m33 );

			this._w = ( m13 - m31 ) / s;
			this._x = ( m12 + m21 ) / s;
			this._y = 0.25 * s;
			this._z = ( m23 + m32 ) / s;

		} else {

			const s = 2.0 * Math.sqrt( 1.0 + m33 - m11 - m22 );

			this._w = ( m21 - m12 ) / s;
			this._x = ( m13 + m31 ) / s;
			this._y = ( m23 + m32 ) / s;
			this._z = 0.25 * s;

		}

		this._onChangeCallback();

		return this;

	}
```
</details>

##### `setFromUnitVectors(vFrom: Vector3, vTo: Vector3): Quaternion`

<details><summary>Code</summary>

```ts
setFromUnitVectors( vFrom, vTo ) {

		// assumes direction vectors vFrom and vTo are normalized

		let r = vFrom.dot( vTo ) + 1;

		if ( r < 1e-8 ) { // the epsilon value has been discussed in #31286

			// vFrom and vTo point in opposite directions

			r = 0;

			if ( Math.abs( vFrom.x ) > Math.abs( vFrom.z ) ) {

				this._x = - vFrom.y;
				this._y = vFrom.x;
				this._z = 0;
				this._w = r;

			} else {

				this._x = 0;
				this._y = - vFrom.z;
				this._z = vFrom.y;
				this._w = r;

			}

		} else {

			// crossVectors( vFrom, vTo ); // inlined to avoid cyclic dependency on Vector3

			this._x = vFrom.y * vTo.z - vFrom.z * vTo.y;
			this._y = vFrom.z * vTo.x - vFrom.x * vTo.z;
			this._z = vFrom.x * vTo.y - vFrom.y * vTo.x;
			this._w = r;

		}

		return this.normalize();

	}
```
</details>

##### `angleTo(q: Quaternion): number`

<details><summary>Code</summary>

```ts
angleTo( q ) {

		return 2 * Math.acos( Math.abs( clamp( this.dot( q ), - 1, 1 ) ) );

	}
```
</details>

##### `rotateTowards(q: Quaternion, step: number): Quaternion`

<details><summary>Code</summary>

```ts
rotateTowards( q, step ) {

		const angle = this.angleTo( q );

		if ( angle === 0 ) return this;

		const t = Math.min( 1, step / angle );

		this.slerp( q, t );

		return this;

	}
```
</details>

##### `identity(): Quaternion`

<details><summary>Code</summary>

```ts
identity() {

		return this.set( 0, 0, 0, 1 );

	}
```
</details>

##### `invert(): Quaternion`

<details><summary>Code</summary>

```ts
invert() {

		return this.conjugate();

	}
```
</details>

##### `conjugate(): Quaternion`

<details><summary>Code</summary>

```ts
conjugate() {

		this._x *= - 1;
		this._y *= - 1;
		this._z *= - 1;

		this._onChangeCallback();

		return this;

	}
```
</details>

##### `dot(v: Quaternion): number`

<details><summary>Code</summary>

```ts
dot( v ) {

		return this._x * v._x + this._y * v._y + this._z * v._z + this._w * v._w;

	}
```
</details>

##### `lengthSq(): number`

<details><summary>Code</summary>

```ts
lengthSq() {

		return this._x * this._x + this._y * this._y + this._z * this._z + this._w * this._w;

	}
```
</details>

##### `length(): number`

<details><summary>Code</summary>

```ts
length() {

		return Math.sqrt( this._x * this._x + this._y * this._y + this._z * this._z + this._w * this._w );

	}
```
</details>

##### `normalize(): Quaternion`

<details><summary>Code</summary>

```ts
normalize() {

		let l = this.length();

		if ( l === 0 ) {

			this._x = 0;
			this._y = 0;
			this._z = 0;
			this._w = 1;

		} else {

			l = 1 / l;

			this._x = this._x * l;
			this._y = this._y * l;
			this._z = this._z * l;
			this._w = this._w * l;

		}

		this._onChangeCallback();

		return this;

	}
```
</details>

##### `multiply(q: Quaternion): Quaternion`

<details><summary>Code</summary>

```ts
multiply( q ) {

		return this.multiplyQuaternions( this, q );

	}
```
</details>

##### `premultiply(q: Quaternion): Quaternion`

<details><summary>Code</summary>

```ts
premultiply( q ) {

		return this.multiplyQuaternions( q, this );

	}
```
</details>

##### `multiplyQuaternions(a: Quaternion, b: Quaternion): Quaternion`

<details><summary>Code</summary>

```ts
multiplyQuaternions( a, b ) {

		// from http://www.euclideanspace.com/maths/algebra/realNormedAlgebra/quaternions/code/index.htm

		const qax = a._x, qay = a._y, qaz = a._z, qaw = a._w;
		const qbx = b._x, qby = b._y, qbz = b._z, qbw = b._w;

		this._x = qax * qbw + qaw * qbx + qay * qbz - qaz * qby;
		this._y = qay * qbw + qaw * qby + qaz * qbx - qax * qbz;
		this._z = qaz * qbw + qaw * qbz + qax * qby - qay * qbx;
		this._w = qaw * qbw - qax * qbx - qay * qby - qaz * qbz;

		this._onChangeCallback();

		return this;

	}
```
</details>

##### `slerp(qb: Quaternion, t: number): Quaternion`

<details><summary>Code</summary>

```ts
slerp( qb, t ) {

		if ( t === 0 ) return this;
		if ( t === 1 ) return this.copy( qb );

		const x = this._x, y = this._y, z = this._z, w = this._w;

		// http://www.euclideanspace.com/maths/algebra/realNormedAlgebra/quaternions/slerp/

		let cosHalfTheta = w * qb._w + x * qb._x + y * qb._y + z * qb._z;

		if ( cosHalfTheta < 0 ) {

			this._w = - qb._w;
			this._x = - qb._x;
			this._y = - qb._y;
			this._z = - qb._z;

			cosHalfTheta = - cosHalfTheta;

		} else {

			this.copy( qb );

		}

		if ( cosHalfTheta >= 1.0 ) {

			this._w = w;
			this._x = x;
			this._y = y;
			this._z = z;

			return this;

		}

		const sqrSinHalfTheta = 1.0 - cosHalfTheta * cosHalfTheta;

		if ( sqrSinHalfTheta <= Number.EPSILON ) {

			const s = 1 - t;
			this._w = s * w + t * this._w;
			this._x = s * x + t * this._x;
			this._y = s * y + t * this._y;
			this._z = s * z + t * this._z;

			this.normalize(); // normalize calls _onChangeCallback()

			return this;

		}

		const sinHalfTheta = Math.sqrt( sqrSinHalfTheta );
		const halfTheta = Math.atan2( sinHalfTheta, cosHalfTheta );
		const ratioA = Math.sin( ( 1 - t ) * halfTheta ) / sinHalfTheta,
			ratioB = Math.sin( t * halfTheta ) / sinHalfTheta;

		this._w = ( w * ratioA + this._w * ratioB );
		this._x = ( x * ratioA + this._x * ratioB );
		this._y = ( y * ratioA + this._y * ratioB );
		this._z = ( z * ratioA + this._z * ratioB );

		this._onChangeCallback();

		return this;

	}
```
</details>

##### `slerpQuaternions(qa: Quaternion, qb: Quaternion, t: number): Quaternion`

<details><summary>Code</summary>

```ts
slerpQuaternions( qa, qb, t ) {

		return this.copy( qa ).slerp( qb, t );

	}
```
</details>

##### `random(): Quaternion`

<details><summary>Code</summary>

```ts
random() {

		// Ken Shoemake
		// Uniform random rotations
		// D. Kirk, editor, Graphics Gems III, pages 124-132. Academic Press, New York, 1992.

		const theta1 = 2 * Math.PI * Math.random();
		const theta2 = 2 * Math.PI * Math.random();

		const x0 = Math.random();
		const r1 = Math.sqrt( 1 - x0 );
		const r2 = Math.sqrt( x0 );

		return this.set(
			r1 * Math.sin( theta1 ),
			r1 * Math.cos( theta1 ),
			r2 * Math.sin( theta2 ),
			r2 * Math.cos( theta2 ),
		);

	}
```
</details>

##### `equals(quaternion: Quaternion): boolean`

<details><summary>Code</summary>

```ts
equals( quaternion ) {

		return ( quaternion._x === this._x ) && ( quaternion._y === this._y ) && ( quaternion._z === this._z ) && ( quaternion._w === this._w );

	}
```
</details>

##### `fromArray(array: number[], offset: number): Quaternion`

<details><summary>Code</summary>

```ts
fromArray( array, offset = 0 ) {

		this._x = array[ offset ];
		this._y = array[ offset + 1 ];
		this._z = array[ offset + 2 ];
		this._w = array[ offset + 3 ];

		this._onChangeCallback();

		return this;

	}
```
</details>

##### `toArray(array: number[], offset: number): number[]`

<details><summary>Code</summary>

```ts
toArray( array = [], offset = 0 ) {

		array[ offset ] = this._x;
		array[ offset + 1 ] = this._y;
		array[ offset + 2 ] = this._z;
		array[ offset + 3 ] = this._w;

		return array;

	}
```
</details>

##### `fromBufferAttribute(attribute: BufferAttribute, index: number): Quaternion`

<details><summary>Code</summary>

```ts
fromBufferAttribute( attribute, index ) {

		this._x = attribute.getX( index );
		this._y = attribute.getY( index );
		this._z = attribute.getZ( index );
		this._w = attribute.getW( index );

		this._onChangeCallback();

		return this;

	}
```
</details>

##### `toJSON(): number[]`

<details><summary>Code</summary>

```ts
toJSON() {

		return this.toArray();

	}
```
</details>

##### `_onChange(callback: any): this`

<details><summary>Code</summary>

```ts
_onChange( callback ) {

		this._onChangeCallback = callback;

		return this;

	}
```
</details>

##### `_onChangeCallback(): void`

<details><summary>Code</summary>

```ts
_onChangeCallback() {}
```
</details>

##### `[ Symbol.iterator ](): Generator<number, void, unknown>`

<details><summary>Code</summary>

```ts
*[ Symbol.iterator ]() {

		yield this._x;
		yield this._y;
		yield this._z;
		yield this._w;

	}
```
</details>


---