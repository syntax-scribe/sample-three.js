[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Matrix3.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 25 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 58 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/Matrix3.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `te` | `number[]` | let/var | `this.elements` | ✗ |
| `te` | `number[]` | let/var | `this.elements` | ✗ |
| `me` | `number[]` | let/var | `m.elements` | ✗ |
| `me` | `any` | let/var | `m.elements` | ✗ |
| `ae` | `number[]` | let/var | `a.elements` | ✗ |
| `be` | `number[]` | let/var | `b.elements` | ✗ |
| `te` | `number[]` | let/var | `this.elements` | ✗ |
| `a11` | `number` | let/var | `ae[ 0 ]` | ✗ |
| `a12` | `number` | let/var | `ae[ 3 ]` | ✗ |
| `a13` | `number` | let/var | `ae[ 6 ]` | ✗ |
| `a21` | `number` | let/var | `ae[ 1 ]` | ✗ |
| `a22` | `number` | let/var | `ae[ 4 ]` | ✗ |
| `a23` | `number` | let/var | `ae[ 7 ]` | ✗ |
| `a31` | `number` | let/var | `ae[ 2 ]` | ✗ |
| `a32` | `number` | let/var | `ae[ 5 ]` | ✗ |
| `a33` | `number` | let/var | `ae[ 8 ]` | ✗ |
| `b11` | `number` | let/var | `be[ 0 ]` | ✗ |
| `b12` | `number` | let/var | `be[ 3 ]` | ✗ |
| `b13` | `number` | let/var | `be[ 6 ]` | ✗ |
| `b21` | `number` | let/var | `be[ 1 ]` | ✗ |
| `b22` | `number` | let/var | `be[ 4 ]` | ✗ |
| `b23` | `number` | let/var | `be[ 7 ]` | ✗ |
| `b31` | `number` | let/var | `be[ 2 ]` | ✗ |
| `b32` | `number` | let/var | `be[ 5 ]` | ✗ |
| `b33` | `number` | let/var | `be[ 8 ]` | ✗ |
| `te` | `number[]` | let/var | `this.elements` | ✗ |
| `te` | `number[]` | let/var | `this.elements` | ✗ |
| `a` | `number` | let/var | `te[ 0 ]` | ✗ |
| `b` | `number` | let/var | `te[ 1 ]` | ✗ |
| `c` | `number` | let/var | `te[ 2 ]` | ✗ |
| `d` | `number` | let/var | `te[ 3 ]` | ✗ |
| `e` | `number` | let/var | `te[ 4 ]` | ✗ |
| `f` | `number` | let/var | `te[ 5 ]` | ✗ |
| `g` | `number` | let/var | `te[ 6 ]` | ✗ |
| `h` | `number` | let/var | `te[ 7 ]` | ✗ |
| `i` | `number` | let/var | `te[ 8 ]` | ✗ |
| `te` | `number[]` | let/var | `this.elements` | ✗ |
| `n11` | `number` | let/var | `te[ 0 ]` | ✗ |
| `n21` | `number` | let/var | `te[ 1 ]` | ✗ |
| `n31` | `number` | let/var | `te[ 2 ]` | ✗ |
| `n12` | `number` | let/var | `te[ 3 ]` | ✗ |
| `n22` | `number` | let/var | `te[ 4 ]` | ✗ |
| `n32` | `number` | let/var | `te[ 5 ]` | ✗ |
| `n13` | `number` | let/var | `te[ 6 ]` | ✗ |
| `n23` | `number` | let/var | `te[ 7 ]` | ✗ |
| `n33` | `number` | let/var | `te[ 8 ]` | ✗ |
| `t11` | `number` | let/var | `n33 * n22 - n32 * n23` | ✗ |
| `t12` | `number` | let/var | `n32 * n13 - n33 * n12` | ✗ |
| `t13` | `number` | let/var | `n23 * n12 - n22 * n13` | ✗ |
| `det` | `number` | let/var | `n11 * t11 + n21 * t12 + n31 * t13` | ✗ |
| `detInv` | `number` | let/var | `1 / det` | ✗ |
| `tmp` | `any` | let/var | `*not shown*` | ✗ |
| `m` | `number[]` | let/var | `this.elements` | ✗ |
| `m` | `number[]` | let/var | `this.elements` | ✗ |
| `te` | `number[]` | let/var | `this.elements` | ✗ |
| `me` | `number[]` | let/var | `matrix.elements` | ✗ |
| `te` | `number[]` | let/var | `this.elements` | ✗ |
| `_m3` | `Matrix3` | let/var | `new Matrix3()` | ✗ |


---

## Functions

### `Matrix3.set(n11: number, n12: number, n13: number, n21: number, n22: number, n23: number, n31: number, n32: number, n33: number): Matrix3`

**JSDoc:**
```typescript
/**
	 * Sets the elements of the matrix.The arguments are supposed to be
	 * in row-major order.
	 *
	 * @param {number} [n11] - 1-1 matrix element.
	 * @param {number} [n12] - 1-2 matrix element.
	 * @param {number} [n13] - 1-3 matrix element.
	 * @param {number} [n21] - 2-1 matrix element.
	 * @param {number} [n22] - 2-2 matrix element.
	 * @param {number} [n23] - 2-3 matrix element.
	 * @param {number} [n31] - 3-1 matrix element.
	 * @param {number} [n32] - 3-2 matrix element.
	 * @param {number} [n33] - 3-3 matrix element.
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`n11`** `number`
- **`n12`** `number`
- **`n13`** `number`
- **`n21`** `number`
- **`n22`** `number`
- **`n23`** `number`
- **`n31`** `number`
- **`n32`** `number`
- **`n33`** `number`

**Returns:** `Matrix3`

<details><summary>Code</summary>

```typescript
set( n11, n12, n13, n21, n22, n23, n31, n32, n33 ) {

		const te = this.elements;

		te[ 0 ] = n11; te[ 1 ] = n21; te[ 2 ] = n31;
		te[ 3 ] = n12; te[ 4 ] = n22; te[ 5 ] = n32;
		te[ 6 ] = n13; te[ 7 ] = n23; te[ 8 ] = n33;

		return this;

	}
```
</details>

### `Matrix3.identity(): Matrix3`

**JSDoc:**
```typescript
/**
	 * Sets this matrix to the 3x3 identity matrix.
	 *
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Returns:** `Matrix3`

**Calls:**

- `this.set`

<details><summary>Code</summary>

```typescript
identity() {

		this.set(

			1, 0, 0,
			0, 1, 0,
			0, 0, 1

		);

		return this;

	}
```
</details>

### `Matrix3.copy(m: Matrix3): Matrix3`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given matrix to this instance.
	 *
	 * @param {Matrix3} m - The matrix to copy.
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`m`** `Matrix3`

**Returns:** `Matrix3`

<details><summary>Code</summary>

```typescript
copy( m ) {

		const te = this.elements;
		const me = m.elements;

		te[ 0 ] = me[ 0 ]; te[ 1 ] = me[ 1 ]; te[ 2 ] = me[ 2 ];
		te[ 3 ] = me[ 3 ]; te[ 4 ] = me[ 4 ]; te[ 5 ] = me[ 5 ];
		te[ 6 ] = me[ 6 ]; te[ 7 ] = me[ 7 ]; te[ 8 ] = me[ 8 ];

		return this;

	}
```
</details>

### `Matrix3.extractBasis(xAxis: Vector3, yAxis: Vector3, zAxis: Vector3): Matrix3`

**JSDoc:**
```typescript
/**
	 * Extracts the basis of this matrix into the three axis vectors provided.
	 *
	 * @param {Vector3} xAxis - The basis's x axis.
	 * @param {Vector3} yAxis - The basis's y axis.
	 * @param {Vector3} zAxis - The basis's z axis.
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`xAxis`** `Vector3`
- **`yAxis`** `Vector3`
- **`zAxis`** `Vector3`

**Returns:** `Matrix3`

**Calls:**

- `xAxis.setFromMatrix3Column`
- `yAxis.setFromMatrix3Column`
- `zAxis.setFromMatrix3Column`

<details><summary>Code</summary>

```typescript
extractBasis( xAxis, yAxis, zAxis ) {

		xAxis.setFromMatrix3Column( this, 0 );
		yAxis.setFromMatrix3Column( this, 1 );
		zAxis.setFromMatrix3Column( this, 2 );

		return this;

	}
```
</details>

### `Matrix3.setFromMatrix4(m: Matrix4): Matrix3`

**JSDoc:**
```typescript
/**
	 * Set this matrix to the upper 3x3 matrix of the given 4x4 matrix.
	 *
	 * @param {Matrix4} m - The 4x4 matrix.
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`m`** `Matrix4`

**Returns:** `Matrix3`

**Calls:**

- `this.set`

<details><summary>Code</summary>

```typescript
setFromMatrix4( m ) {

		const me = m.elements;

		this.set(

			me[ 0 ], me[ 4 ], me[ 8 ],
			me[ 1 ], me[ 5 ], me[ 9 ],
			me[ 2 ], me[ 6 ], me[ 10 ]

		);

		return this;

	}
```
</details>

### `Matrix3.multiply(m: Matrix3): Matrix3`

**JSDoc:**
```typescript
/**
	 * Post-multiplies this matrix by the given 3x3 matrix.
	 *
	 * @param {Matrix3} m - The matrix to multiply with.
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`m`** `Matrix3`

**Returns:** `Matrix3`

**Calls:**

- `this.multiplyMatrices`

<details><summary>Code</summary>

```typescript
multiply( m ) {

		return this.multiplyMatrices( this, m );

	}
```
</details>

### `Matrix3.premultiply(m: Matrix3): Matrix3`

**JSDoc:**
```typescript
/**
	 * Pre-multiplies this matrix by the given 3x3 matrix.
	 *
	 * @param {Matrix3} m - The matrix to multiply with.
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`m`** `Matrix3`

**Returns:** `Matrix3`

**Calls:**

- `this.multiplyMatrices`

<details><summary>Code</summary>

```typescript
premultiply( m ) {

		return this.multiplyMatrices( m, this );

	}
```
</details>

### `Matrix3.multiplyMatrices(a: Matrix3, b: Matrix3): Matrix3`

**JSDoc:**
```typescript
/**
	 * Multiples the given 3x3 matrices and stores the result
	 * in this matrix.
	 *
	 * @param {Matrix3} a - The first matrix.
	 * @param {Matrix3} b - The second matrix.
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`a`** `Matrix3`
- **`b`** `Matrix3`

**Returns:** `Matrix3`

<details><summary>Code</summary>

```typescript
multiplyMatrices( a, b ) {

		const ae = a.elements;
		const be = b.elements;
		const te = this.elements;

		const a11 = ae[ 0 ], a12 = ae[ 3 ], a13 = ae[ 6 ];
		const a21 = ae[ 1 ], a22 = ae[ 4 ], a23 = ae[ 7 ];
		const a31 = ae[ 2 ], a32 = ae[ 5 ], a33 = ae[ 8 ];

		const b11 = be[ 0 ], b12 = be[ 3 ], b13 = be[ 6 ];
		const b21 = be[ 1 ], b22 = be[ 4 ], b23 = be[ 7 ];
		const b31 = be[ 2 ], b32 = be[ 5 ], b33 = be[ 8 ];

		te[ 0 ] = a11 * b11 + a12 * b21 + a13 * b31;
		te[ 3 ] = a11 * b12 + a12 * b22 + a13 * b32;
		te[ 6 ] = a11 * b13 + a12 * b23 + a13 * b33;

		te[ 1 ] = a21 * b11 + a22 * b21 + a23 * b31;
		te[ 4 ] = a21 * b12 + a22 * b22 + a23 * b32;
		te[ 7 ] = a21 * b13 + a22 * b23 + a23 * b33;

		te[ 2 ] = a31 * b11 + a32 * b21 + a33 * b31;
		te[ 5 ] = a31 * b12 + a32 * b22 + a33 * b32;
		te[ 8 ] = a31 * b13 + a32 * b23 + a33 * b33;

		return this;

	}
```
</details>

### `Matrix3.multiplyScalar(s: number): Matrix3`

**JSDoc:**
```typescript
/**
	 * Multiplies every component of the matrix by the given scalar.
	 *
	 * @param {number} s - The scalar.
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`s`** `number`

**Returns:** `Matrix3`

<details><summary>Code</summary>

```typescript
multiplyScalar( s ) {

		const te = this.elements;

		te[ 0 ] *= s; te[ 3 ] *= s; te[ 6 ] *= s;
		te[ 1 ] *= s; te[ 4 ] *= s; te[ 7 ] *= s;
		te[ 2 ] *= s; te[ 5 ] *= s; te[ 8 ] *= s;

		return this;

	}
```
</details>

### `Matrix3.determinant(): number`

**JSDoc:**
```typescript
/**
	 * Computes and returns the determinant of this matrix.
	 *
	 * @return {number} The determinant.
	 */
```

**Returns:** `number`

<details><summary>Code</summary>

```typescript
determinant() {

		const te = this.elements;

		const a = te[ 0 ], b = te[ 1 ], c = te[ 2 ],
			d = te[ 3 ], e = te[ 4 ], f = te[ 5 ],
			g = te[ 6 ], h = te[ 7 ], i = te[ 8 ];

		return a * e * i - a * f * h - b * d * i + b * f * g + c * d * h - c * e * g;

	}
```
</details>

### `Matrix3.invert(): Matrix3`

**JSDoc:**
```typescript
/**
	 * Inverts this matrix, using the [analytic method]{@link https://en.wikipedia.org/wiki/Invertible_matrix#Analytic_solution}.
	 * You can not invert with a determinant of zero. If you attempt this, the method produces
	 * a zero matrix instead.
	 *
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Returns:** `Matrix3`

**Calls:**

- `this.set`

<details><summary>Code</summary>

```typescript
invert() {

		const te = this.elements,

			n11 = te[ 0 ], n21 = te[ 1 ], n31 = te[ 2 ],
			n12 = te[ 3 ], n22 = te[ 4 ], n32 = te[ 5 ],
			n13 = te[ 6 ], n23 = te[ 7 ], n33 = te[ 8 ],

			t11 = n33 * n22 - n32 * n23,
			t12 = n32 * n13 - n33 * n12,
			t13 = n23 * n12 - n22 * n13,

			det = n11 * t11 + n21 * t12 + n31 * t13;

		if ( det === 0 ) return this.set( 0, 0, 0, 0, 0, 0, 0, 0, 0 );

		const detInv = 1 / det;

		te[ 0 ] = t11 * detInv;
		te[ 1 ] = ( n31 * n23 - n33 * n21 ) * detInv;
		te[ 2 ] = ( n32 * n21 - n31 * n22 ) * detInv;

		te[ 3 ] = t12 * detInv;
		te[ 4 ] = ( n33 * n11 - n31 * n13 ) * detInv;
		te[ 5 ] = ( n31 * n12 - n32 * n11 ) * detInv;

		te[ 6 ] = t13 * detInv;
		te[ 7 ] = ( n21 * n13 - n23 * n11 ) * detInv;
		te[ 8 ] = ( n22 * n11 - n21 * n12 ) * detInv;

		return this;

	}
```
</details>

### `Matrix3.transpose(): Matrix3`

**JSDoc:**
```typescript
/**
	 * Transposes this matrix in place.
	 *
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Returns:** `Matrix3`

<details><summary>Code</summary>

```typescript
transpose() {

		let tmp;
		const m = this.elements;

		tmp = m[ 1 ]; m[ 1 ] = m[ 3 ]; m[ 3 ] = tmp;
		tmp = m[ 2 ]; m[ 2 ] = m[ 6 ]; m[ 6 ] = tmp;
		tmp = m[ 5 ]; m[ 5 ] = m[ 7 ]; m[ 7 ] = tmp;

		return this;

	}
```
</details>

### `Matrix3.getNormalMatrix(matrix4: Matrix4): Matrix3`

**JSDoc:**
```typescript
/**
	 * Computes the normal matrix which is the inverse transpose of the upper
	 * left 3x3 portion of the given 4x4 matrix.
	 *
	 * @param {Matrix4} matrix4 - The 4x4 matrix.
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`matrix4`** `Matrix4`

**Returns:** `Matrix3`

**Calls:**

- `this.setFromMatrix4( matrix4 ).invert().transpose`

<details><summary>Code</summary>

```typescript
getNormalMatrix( matrix4 ) {

		return this.setFromMatrix4( matrix4 ).invert().transpose();

	}
```
</details>

### `Matrix3.transposeIntoArray(r: number[]): Matrix3`

**JSDoc:**
```typescript
/**
	 * Transposes this matrix into the supplied array, and returns itself unchanged.
	 *
	 * @param {Array<number>} r - An array to store the transposed matrix elements.
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`r`** `number[]`

**Returns:** `Matrix3`

<details><summary>Code</summary>

```typescript
transposeIntoArray( r ) {

		const m = this.elements;

		r[ 0 ] = m[ 0 ];
		r[ 1 ] = m[ 3 ];
		r[ 2 ] = m[ 6 ];
		r[ 3 ] = m[ 1 ];
		r[ 4 ] = m[ 4 ];
		r[ 5 ] = m[ 7 ];
		r[ 6 ] = m[ 2 ];
		r[ 7 ] = m[ 5 ];
		r[ 8 ] = m[ 8 ];

		return this;

	}
```
</details>

### `Matrix3.setUvTransform(tx: number, ty: number, sx: number, sy: number, rotation: number, cx: number, cy: number): Matrix3`

**JSDoc:**
```typescript
/**
	 * Sets the UV transform matrix from offset, repeat, rotation, and center.
	 *
	 * @param {number} tx - Offset x.
	 * @param {number} ty - Offset y.
	 * @param {number} sx - Repeat x.
	 * @param {number} sy - Repeat y.
	 * @param {number} rotation - Rotation, in radians. Positive values rotate counterclockwise.
	 * @param {number} cx - Center x of rotation.
	 * @param {number} cy - Center y of rotation
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`tx`** `number`
- **`ty`** `number`
- **`sx`** `number`
- **`sy`** `number`
- **`rotation`** `number`
- **`cx`** `number`
- **`cy`** `number`

**Returns:** `Matrix3`

**Calls:**

- `Math.cos`
- `Math.sin`
- `this.set`

<details><summary>Code</summary>

```typescript
setUvTransform( tx, ty, sx, sy, rotation, cx, cy ) {

		const c = Math.cos( rotation );
		const s = Math.sin( rotation );

		this.set(
			sx * c, sx * s, - sx * ( c * cx + s * cy ) + cx + tx,
			- sy * s, sy * c, - sy * ( - s * cx + c * cy ) + cy + ty,
			0, 0, 1
		);

		return this;

	}
```
</details>

### `Matrix3.scale(sx: number, sy: number): Matrix3`

**JSDoc:**
```typescript
/**
	 * Scales this matrix with the given scalar values.
	 *
	 * @param {number} sx - The amount to scale in the X axis.
	 * @param {number} sy - The amount to scale in the Y axis.
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`sx`** `number`
- **`sy`** `number`

**Returns:** `Matrix3`

**Calls:**

- `this.premultiply`
- `_m3.makeScale`

<details><summary>Code</summary>

```typescript
scale( sx, sy ) {

		this.premultiply( _m3.makeScale( sx, sy ) );

		return this;

	}
```
</details>

### `Matrix3.rotate(theta: number): Matrix3`

**JSDoc:**
```typescript
/**
	 * Rotates this matrix by the given angle.
	 *
	 * @param {number} theta - The rotation in radians.
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`theta`** `number`

**Returns:** `Matrix3`

**Calls:**

- `this.premultiply`
- `_m3.makeRotation`

<details><summary>Code</summary>

```typescript
rotate( theta ) {

		this.premultiply( _m3.makeRotation( - theta ) );

		return this;

	}
```
</details>

### `Matrix3.translate(tx: number, ty: number): Matrix3`

**JSDoc:**
```typescript
/**
	 * Translates this matrix by the given scalar values.
	 *
	 * @param {number} tx - The amount to translate in the X axis.
	 * @param {number} ty - The amount to translate in the Y axis.
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`tx`** `number`
- **`ty`** `number`

**Returns:** `Matrix3`

**Calls:**

- `this.premultiply`
- `_m3.makeTranslation`

<details><summary>Code</summary>

```typescript
translate( tx, ty ) {

		this.premultiply( _m3.makeTranslation( tx, ty ) );

		return this;

	}
```
</details>

### `Matrix3.makeTranslation(x: any, y: number): Matrix3`

**JSDoc:**
```typescript
/**
	 * Sets this matrix as a 2D translation transform.
	 *
	 * @param {number|Vector2} x - The amount to translate in the X axis or alternatively a translation vector.
	 * @param {number} y - The amount to translate in the Y axis.
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`x`** `any`
- **`y`** `number`

**Returns:** `Matrix3`

**Calls:**

- `this.set`

<details><summary>Code</summary>

```typescript
makeTranslation( x, y ) {

		if ( x.isVector2 ) {

			this.set(

				1, 0, x.x,
				0, 1, x.y,
				0, 0, 1

			);

		} else {

			this.set(

				1, 0, x,
				0, 1, y,
				0, 0, 1

			);

		}

		return this;

	}
```
</details>

### `Matrix3.makeRotation(theta: number): Matrix3`

**JSDoc:**
```typescript
/**
	 * Sets this matrix as a 2D rotational transformation.
	 *
	 * @param {number} theta - The rotation in radians.
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`theta`** `number`

**Returns:** `Matrix3`

**Calls:**

- `Math.cos`
- `Math.sin`
- `this.set`

**Internal Comments:**
```
// counterclockwise (x2)
```

<details><summary>Code</summary>

```typescript
makeRotation( theta ) {

		// counterclockwise

		const c = Math.cos( theta );
		const s = Math.sin( theta );

		this.set(

			c, - s, 0,
			s, c, 0,
			0, 0, 1

		);

		return this;

	}
```
</details>

### `Matrix3.makeScale(x: number, y: number): Matrix3`

**JSDoc:**
```typescript
/**
	 * Sets this matrix as a 2D scale transform.
	 *
	 * @param {number} x - The amount to scale in the X axis.
	 * @param {number} y - The amount to scale in the Y axis.
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`

**Returns:** `Matrix3`

**Calls:**

- `this.set`

<details><summary>Code</summary>

```typescript
makeScale( x, y ) {

		this.set(

			x, 0, 0,
			0, y, 0,
			0, 0, 1

		);

		return this;

	}
```
</details>

### `Matrix3.equals(matrix: Matrix3): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this matrix is equal with the given one.
	 *
	 * @param {Matrix3} matrix - The matrix to test for equality.
	 * @return {boolean} Whether this matrix is equal with the given one.
	 */
```

**Parameters:**

- **`matrix`** `Matrix3`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
equals( matrix ) {

		const te = this.elements;
		const me = matrix.elements;

		for ( let i = 0; i < 9; i ++ ) {

			if ( te[ i ] !== me[ i ] ) return false;

		}

		return true;

	}
```
</details>

### `Matrix3.fromArray(array: number[], offset: number): Matrix3`

**JSDoc:**
```typescript
/**
	 * Sets the elements of the matrix from the given array.
	 *
	 * @param {Array<number>} array - The matrix elements in column-major order.
	 * @param {number} [offset=0] - Index of the first element in the array.
	 * @return {Matrix3} A reference to this matrix.
	 */
```

**Parameters:**

- **`array`** `number[]`
- **`offset`** `number`

**Returns:** `Matrix3`

<details><summary>Code</summary>

```typescript
fromArray( array, offset = 0 ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.elements[ i ] = array[ i + offset ];

		}

		return this;

	}
```
</details>

### `Matrix3.toArray(array: number[], offset: number): number[]`

**JSDoc:**
```typescript
/**
	 * Writes the elements of this matrix to the given array. If no array is provided,
	 * the method returns a new instance.
	 *
	 * @param {Array<number>} [array=[]] - The target array holding the matrix elements in column-major order.
	 * @param {number} [offset=0] - Index of the first element in the array.
	 * @return {Array<number>} The matrix elements in column-major order.
	 */
```

**Parameters:**

- **`array`** `number[]`
- **`offset`** `number`

**Returns:** `number[]`

<details><summary>Code</summary>

```typescript
toArray( array = [], offset = 0 ) {

		const te = this.elements;

		array[ offset ] = te[ 0 ];
		array[ offset + 1 ] = te[ 1 ];
		array[ offset + 2 ] = te[ 2 ];

		array[ offset + 3 ] = te[ 3 ];
		array[ offset + 4 ] = te[ 4 ];
		array[ offset + 5 ] = te[ 5 ];

		array[ offset + 6 ] = te[ 6 ];
		array[ offset + 7 ] = te[ 7 ];
		array[ offset + 8 ] = te[ 8 ];

		return array;

	}
```
</details>

### `Matrix3.clone(): Matrix3`

**JSDoc:**
```typescript
/**
	 * Returns a matrix with copied values from this instance.
	 *
	 * @return {Matrix3} A clone of this instance.
	 */
```

**Returns:** `Matrix3`

**Calls:**

- `new this.constructor().fromArray`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor().fromArray( this.elements );

	}
```
</details>


---

## Classes

### `Matrix3`

<details><summary>Class Code</summary>

```ts
class Matrix3 {

	/**
	 * Constructs a new 3x3 matrix. The arguments are supposed to be
	 * in row-major order. If no arguments are provided, the constructor
	 * initializes the matrix as an identity matrix.
	 *
	 * @param {number} [n11] - 1-1 matrix element.
	 * @param {number} [n12] - 1-2 matrix element.
	 * @param {number} [n13] - 1-3 matrix element.
	 * @param {number} [n21] - 2-1 matrix element.
	 * @param {number} [n22] - 2-2 matrix element.
	 * @param {number} [n23] - 2-3 matrix element.
	 * @param {number} [n31] - 3-1 matrix element.
	 * @param {number} [n32] - 3-2 matrix element.
	 * @param {number} [n33] - 3-3 matrix element.
	 */
	constructor( n11, n12, n13, n21, n22, n23, n31, n32, n33 ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		Matrix3.prototype.isMatrix3 = true;

		/**
		 * A column-major list of matrix values.
		 *
		 * @type {Array<number>}
		 */
		this.elements = [

			1, 0, 0,
			0, 1, 0,
			0, 0, 1

		];

		if ( n11 !== undefined ) {

			this.set( n11, n12, n13, n21, n22, n23, n31, n32, n33 );

		}

	}

	/**
	 * Sets the elements of the matrix.The arguments are supposed to be
	 * in row-major order.
	 *
	 * @param {number} [n11] - 1-1 matrix element.
	 * @param {number} [n12] - 1-2 matrix element.
	 * @param {number} [n13] - 1-3 matrix element.
	 * @param {number} [n21] - 2-1 matrix element.
	 * @param {number} [n22] - 2-2 matrix element.
	 * @param {number} [n23] - 2-3 matrix element.
	 * @param {number} [n31] - 3-1 matrix element.
	 * @param {number} [n32] - 3-2 matrix element.
	 * @param {number} [n33] - 3-3 matrix element.
	 * @return {Matrix3} A reference to this matrix.
	 */
	set( n11, n12, n13, n21, n22, n23, n31, n32, n33 ) {

		const te = this.elements;

		te[ 0 ] = n11; te[ 1 ] = n21; te[ 2 ] = n31;
		te[ 3 ] = n12; te[ 4 ] = n22; te[ 5 ] = n32;
		te[ 6 ] = n13; te[ 7 ] = n23; te[ 8 ] = n33;

		return this;

	}

	/**
	 * Sets this matrix to the 3x3 identity matrix.
	 *
	 * @return {Matrix3} A reference to this matrix.
	 */
	identity() {

		this.set(

			1, 0, 0,
			0, 1, 0,
			0, 0, 1

		);

		return this;

	}

	/**
	 * Copies the values of the given matrix to this instance.
	 *
	 * @param {Matrix3} m - The matrix to copy.
	 * @return {Matrix3} A reference to this matrix.
	 */
	copy( m ) {

		const te = this.elements;
		const me = m.elements;

		te[ 0 ] = me[ 0 ]; te[ 1 ] = me[ 1 ]; te[ 2 ] = me[ 2 ];
		te[ 3 ] = me[ 3 ]; te[ 4 ] = me[ 4 ]; te[ 5 ] = me[ 5 ];
		te[ 6 ] = me[ 6 ]; te[ 7 ] = me[ 7 ]; te[ 8 ] = me[ 8 ];

		return this;

	}

	/**
	 * Extracts the basis of this matrix into the three axis vectors provided.
	 *
	 * @param {Vector3} xAxis - The basis's x axis.
	 * @param {Vector3} yAxis - The basis's y axis.
	 * @param {Vector3} zAxis - The basis's z axis.
	 * @return {Matrix3} A reference to this matrix.
	 */
	extractBasis( xAxis, yAxis, zAxis ) {

		xAxis.setFromMatrix3Column( this, 0 );
		yAxis.setFromMatrix3Column( this, 1 );
		zAxis.setFromMatrix3Column( this, 2 );

		return this;

	}

	/**
	 * Set this matrix to the upper 3x3 matrix of the given 4x4 matrix.
	 *
	 * @param {Matrix4} m - The 4x4 matrix.
	 * @return {Matrix3} A reference to this matrix.
	 */
	setFromMatrix4( m ) {

		const me = m.elements;

		this.set(

			me[ 0 ], me[ 4 ], me[ 8 ],
			me[ 1 ], me[ 5 ], me[ 9 ],
			me[ 2 ], me[ 6 ], me[ 10 ]

		);

		return this;

	}

	/**
	 * Post-multiplies this matrix by the given 3x3 matrix.
	 *
	 * @param {Matrix3} m - The matrix to multiply with.
	 * @return {Matrix3} A reference to this matrix.
	 */
	multiply( m ) {

		return this.multiplyMatrices( this, m );

	}

	/**
	 * Pre-multiplies this matrix by the given 3x3 matrix.
	 *
	 * @param {Matrix3} m - The matrix to multiply with.
	 * @return {Matrix3} A reference to this matrix.
	 */
	premultiply( m ) {

		return this.multiplyMatrices( m, this );

	}

	/**
	 * Multiples the given 3x3 matrices and stores the result
	 * in this matrix.
	 *
	 * @param {Matrix3} a - The first matrix.
	 * @param {Matrix3} b - The second matrix.
	 * @return {Matrix3} A reference to this matrix.
	 */
	multiplyMatrices( a, b ) {

		const ae = a.elements;
		const be = b.elements;
		const te = this.elements;

		const a11 = ae[ 0 ], a12 = ae[ 3 ], a13 = ae[ 6 ];
		const a21 = ae[ 1 ], a22 = ae[ 4 ], a23 = ae[ 7 ];
		const a31 = ae[ 2 ], a32 = ae[ 5 ], a33 = ae[ 8 ];

		const b11 = be[ 0 ], b12 = be[ 3 ], b13 = be[ 6 ];
		const b21 = be[ 1 ], b22 = be[ 4 ], b23 = be[ 7 ];
		const b31 = be[ 2 ], b32 = be[ 5 ], b33 = be[ 8 ];

		te[ 0 ] = a11 * b11 + a12 * b21 + a13 * b31;
		te[ 3 ] = a11 * b12 + a12 * b22 + a13 * b32;
		te[ 6 ] = a11 * b13 + a12 * b23 + a13 * b33;

		te[ 1 ] = a21 * b11 + a22 * b21 + a23 * b31;
		te[ 4 ] = a21 * b12 + a22 * b22 + a23 * b32;
		te[ 7 ] = a21 * b13 + a22 * b23 + a23 * b33;

		te[ 2 ] = a31 * b11 + a32 * b21 + a33 * b31;
		te[ 5 ] = a31 * b12 + a32 * b22 + a33 * b32;
		te[ 8 ] = a31 * b13 + a32 * b23 + a33 * b33;

		return this;

	}

	/**
	 * Multiplies every component of the matrix by the given scalar.
	 *
	 * @param {number} s - The scalar.
	 * @return {Matrix3} A reference to this matrix.
	 */
	multiplyScalar( s ) {

		const te = this.elements;

		te[ 0 ] *= s; te[ 3 ] *= s; te[ 6 ] *= s;
		te[ 1 ] *= s; te[ 4 ] *= s; te[ 7 ] *= s;
		te[ 2 ] *= s; te[ 5 ] *= s; te[ 8 ] *= s;

		return this;

	}

	/**
	 * Computes and returns the determinant of this matrix.
	 *
	 * @return {number} The determinant.
	 */
	determinant() {

		const te = this.elements;

		const a = te[ 0 ], b = te[ 1 ], c = te[ 2 ],
			d = te[ 3 ], e = te[ 4 ], f = te[ 5 ],
			g = te[ 6 ], h = te[ 7 ], i = te[ 8 ];

		return a * e * i - a * f * h - b * d * i + b * f * g + c * d * h - c * e * g;

	}

	/**
	 * Inverts this matrix, using the [analytic method]{@link https://en.wikipedia.org/wiki/Invertible_matrix#Analytic_solution}.
	 * You can not invert with a determinant of zero. If you attempt this, the method produces
	 * a zero matrix instead.
	 *
	 * @return {Matrix3} A reference to this matrix.
	 */
	invert() {

		const te = this.elements,

			n11 = te[ 0 ], n21 = te[ 1 ], n31 = te[ 2 ],
			n12 = te[ 3 ], n22 = te[ 4 ], n32 = te[ 5 ],
			n13 = te[ 6 ], n23 = te[ 7 ], n33 = te[ 8 ],

			t11 = n33 * n22 - n32 * n23,
			t12 = n32 * n13 - n33 * n12,
			t13 = n23 * n12 - n22 * n13,

			det = n11 * t11 + n21 * t12 + n31 * t13;

		if ( det === 0 ) return this.set( 0, 0, 0, 0, 0, 0, 0, 0, 0 );

		const detInv = 1 / det;

		te[ 0 ] = t11 * detInv;
		te[ 1 ] = ( n31 * n23 - n33 * n21 ) * detInv;
		te[ 2 ] = ( n32 * n21 - n31 * n22 ) * detInv;

		te[ 3 ] = t12 * detInv;
		te[ 4 ] = ( n33 * n11 - n31 * n13 ) * detInv;
		te[ 5 ] = ( n31 * n12 - n32 * n11 ) * detInv;

		te[ 6 ] = t13 * detInv;
		te[ 7 ] = ( n21 * n13 - n23 * n11 ) * detInv;
		te[ 8 ] = ( n22 * n11 - n21 * n12 ) * detInv;

		return this;

	}

	/**
	 * Transposes this matrix in place.
	 *
	 * @return {Matrix3} A reference to this matrix.
	 */
	transpose() {

		let tmp;
		const m = this.elements;

		tmp = m[ 1 ]; m[ 1 ] = m[ 3 ]; m[ 3 ] = tmp;
		tmp = m[ 2 ]; m[ 2 ] = m[ 6 ]; m[ 6 ] = tmp;
		tmp = m[ 5 ]; m[ 5 ] = m[ 7 ]; m[ 7 ] = tmp;

		return this;

	}

	/**
	 * Computes the normal matrix which is the inverse transpose of the upper
	 * left 3x3 portion of the given 4x4 matrix.
	 *
	 * @param {Matrix4} matrix4 - The 4x4 matrix.
	 * @return {Matrix3} A reference to this matrix.
	 */
	getNormalMatrix( matrix4 ) {

		return this.setFromMatrix4( matrix4 ).invert().transpose();

	}

	/**
	 * Transposes this matrix into the supplied array, and returns itself unchanged.
	 *
	 * @param {Array<number>} r - An array to store the transposed matrix elements.
	 * @return {Matrix3} A reference to this matrix.
	 */
	transposeIntoArray( r ) {

		const m = this.elements;

		r[ 0 ] = m[ 0 ];
		r[ 1 ] = m[ 3 ];
		r[ 2 ] = m[ 6 ];
		r[ 3 ] = m[ 1 ];
		r[ 4 ] = m[ 4 ];
		r[ 5 ] = m[ 7 ];
		r[ 6 ] = m[ 2 ];
		r[ 7 ] = m[ 5 ];
		r[ 8 ] = m[ 8 ];

		return this;

	}

	/**
	 * Sets the UV transform matrix from offset, repeat, rotation, and center.
	 *
	 * @param {number} tx - Offset x.
	 * @param {number} ty - Offset y.
	 * @param {number} sx - Repeat x.
	 * @param {number} sy - Repeat y.
	 * @param {number} rotation - Rotation, in radians. Positive values rotate counterclockwise.
	 * @param {number} cx - Center x of rotation.
	 * @param {number} cy - Center y of rotation
	 * @return {Matrix3} A reference to this matrix.
	 */
	setUvTransform( tx, ty, sx, sy, rotation, cx, cy ) {

		const c = Math.cos( rotation );
		const s = Math.sin( rotation );

		this.set(
			sx * c, sx * s, - sx * ( c * cx + s * cy ) + cx + tx,
			- sy * s, sy * c, - sy * ( - s * cx + c * cy ) + cy + ty,
			0, 0, 1
		);

		return this;

	}

	/**
	 * Scales this matrix with the given scalar values.
	 *
	 * @param {number} sx - The amount to scale in the X axis.
	 * @param {number} sy - The amount to scale in the Y axis.
	 * @return {Matrix3} A reference to this matrix.
	 */
	scale( sx, sy ) {

		this.premultiply( _m3.makeScale( sx, sy ) );

		return this;

	}

	/**
	 * Rotates this matrix by the given angle.
	 *
	 * @param {number} theta - The rotation in radians.
	 * @return {Matrix3} A reference to this matrix.
	 */
	rotate( theta ) {

		this.premultiply( _m3.makeRotation( - theta ) );

		return this;

	}

	/**
	 * Translates this matrix by the given scalar values.
	 *
	 * @param {number} tx - The amount to translate in the X axis.
	 * @param {number} ty - The amount to translate in the Y axis.
	 * @return {Matrix3} A reference to this matrix.
	 */
	translate( tx, ty ) {

		this.premultiply( _m3.makeTranslation( tx, ty ) );

		return this;

	}

	// for 2D Transforms

	/**
	 * Sets this matrix as a 2D translation transform.
	 *
	 * @param {number|Vector2} x - The amount to translate in the X axis or alternatively a translation vector.
	 * @param {number} y - The amount to translate in the Y axis.
	 * @return {Matrix3} A reference to this matrix.
	 */
	makeTranslation( x, y ) {

		if ( x.isVector2 ) {

			this.set(

				1, 0, x.x,
				0, 1, x.y,
				0, 0, 1

			);

		} else {

			this.set(

				1, 0, x,
				0, 1, y,
				0, 0, 1

			);

		}

		return this;

	}

	/**
	 * Sets this matrix as a 2D rotational transformation.
	 *
	 * @param {number} theta - The rotation in radians.
	 * @return {Matrix3} A reference to this matrix.
	 */
	makeRotation( theta ) {

		// counterclockwise

		const c = Math.cos( theta );
		const s = Math.sin( theta );

		this.set(

			c, - s, 0,
			s, c, 0,
			0, 0, 1

		);

		return this;

	}

	/**
	 * Sets this matrix as a 2D scale transform.
	 *
	 * @param {number} x - The amount to scale in the X axis.
	 * @param {number} y - The amount to scale in the Y axis.
	 * @return {Matrix3} A reference to this matrix.
	 */
	makeScale( x, y ) {

		this.set(

			x, 0, 0,
			0, y, 0,
			0, 0, 1

		);

		return this;

	}

	/**
	 * Returns `true` if this matrix is equal with the given one.
	 *
	 * @param {Matrix3} matrix - The matrix to test for equality.
	 * @return {boolean} Whether this matrix is equal with the given one.
	 */
	equals( matrix ) {

		const te = this.elements;
		const me = matrix.elements;

		for ( let i = 0; i < 9; i ++ ) {

			if ( te[ i ] !== me[ i ] ) return false;

		}

		return true;

	}

	/**
	 * Sets the elements of the matrix from the given array.
	 *
	 * @param {Array<number>} array - The matrix elements in column-major order.
	 * @param {number} [offset=0] - Index of the first element in the array.
	 * @return {Matrix3} A reference to this matrix.
	 */
	fromArray( array, offset = 0 ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.elements[ i ] = array[ i + offset ];

		}

		return this;

	}

	/**
	 * Writes the elements of this matrix to the given array. If no array is provided,
	 * the method returns a new instance.
	 *
	 * @param {Array<number>} [array=[]] - The target array holding the matrix elements in column-major order.
	 * @param {number} [offset=0] - Index of the first element in the array.
	 * @return {Array<number>} The matrix elements in column-major order.
	 */
	toArray( array = [], offset = 0 ) {

		const te = this.elements;

		array[ offset ] = te[ 0 ];
		array[ offset + 1 ] = te[ 1 ];
		array[ offset + 2 ] = te[ 2 ];

		array[ offset + 3 ] = te[ 3 ];
		array[ offset + 4 ] = te[ 4 ];
		array[ offset + 5 ] = te[ 5 ];

		array[ offset + 6 ] = te[ 6 ];
		array[ offset + 7 ] = te[ 7 ];
		array[ offset + 8 ] = te[ 8 ];

		return array;

	}

	/**
	 * Returns a matrix with copied values from this instance.
	 *
	 * @return {Matrix3} A clone of this instance.
	 */
	clone() {

		return new this.constructor().fromArray( this.elements );

	}

}
```
</details>

#### Methods

##### `set(n11: number, n12: number, n13: number, n21: number, n22: number, n23: number, n31: number, n32: number, n33: number): Matrix3`

<details><summary>Code</summary>

```ts
set( n11, n12, n13, n21, n22, n23, n31, n32, n33 ) {

		const te = this.elements;

		te[ 0 ] = n11; te[ 1 ] = n21; te[ 2 ] = n31;
		te[ 3 ] = n12; te[ 4 ] = n22; te[ 5 ] = n32;
		te[ 6 ] = n13; te[ 7 ] = n23; te[ 8 ] = n33;

		return this;

	}
```
</details>

##### `identity(): Matrix3`

<details><summary>Code</summary>

```ts
identity() {

		this.set(

			1, 0, 0,
			0, 1, 0,
			0, 0, 1

		);

		return this;

	}
```
</details>

##### `copy(m: Matrix3): Matrix3`

<details><summary>Code</summary>

```ts
copy( m ) {

		const te = this.elements;
		const me = m.elements;

		te[ 0 ] = me[ 0 ]; te[ 1 ] = me[ 1 ]; te[ 2 ] = me[ 2 ];
		te[ 3 ] = me[ 3 ]; te[ 4 ] = me[ 4 ]; te[ 5 ] = me[ 5 ];
		te[ 6 ] = me[ 6 ]; te[ 7 ] = me[ 7 ]; te[ 8 ] = me[ 8 ];

		return this;

	}
```
</details>

##### `extractBasis(xAxis: Vector3, yAxis: Vector3, zAxis: Vector3): Matrix3`

<details><summary>Code</summary>

```ts
extractBasis( xAxis, yAxis, zAxis ) {

		xAxis.setFromMatrix3Column( this, 0 );
		yAxis.setFromMatrix3Column( this, 1 );
		zAxis.setFromMatrix3Column( this, 2 );

		return this;

	}
```
</details>

##### `setFromMatrix4(m: Matrix4): Matrix3`

<details><summary>Code</summary>

```ts
setFromMatrix4( m ) {

		const me = m.elements;

		this.set(

			me[ 0 ], me[ 4 ], me[ 8 ],
			me[ 1 ], me[ 5 ], me[ 9 ],
			me[ 2 ], me[ 6 ], me[ 10 ]

		);

		return this;

	}
```
</details>

##### `multiply(m: Matrix3): Matrix3`

<details><summary>Code</summary>

```ts
multiply( m ) {

		return this.multiplyMatrices( this, m );

	}
```
</details>

##### `premultiply(m: Matrix3): Matrix3`

<details><summary>Code</summary>

```ts
premultiply( m ) {

		return this.multiplyMatrices( m, this );

	}
```
</details>

##### `multiplyMatrices(a: Matrix3, b: Matrix3): Matrix3`

<details><summary>Code</summary>

```ts
multiplyMatrices( a, b ) {

		const ae = a.elements;
		const be = b.elements;
		const te = this.elements;

		const a11 = ae[ 0 ], a12 = ae[ 3 ], a13 = ae[ 6 ];
		const a21 = ae[ 1 ], a22 = ae[ 4 ], a23 = ae[ 7 ];
		const a31 = ae[ 2 ], a32 = ae[ 5 ], a33 = ae[ 8 ];

		const b11 = be[ 0 ], b12 = be[ 3 ], b13 = be[ 6 ];
		const b21 = be[ 1 ], b22 = be[ 4 ], b23 = be[ 7 ];
		const b31 = be[ 2 ], b32 = be[ 5 ], b33 = be[ 8 ];

		te[ 0 ] = a11 * b11 + a12 * b21 + a13 * b31;
		te[ 3 ] = a11 * b12 + a12 * b22 + a13 * b32;
		te[ 6 ] = a11 * b13 + a12 * b23 + a13 * b33;

		te[ 1 ] = a21 * b11 + a22 * b21 + a23 * b31;
		te[ 4 ] = a21 * b12 + a22 * b22 + a23 * b32;
		te[ 7 ] = a21 * b13 + a22 * b23 + a23 * b33;

		te[ 2 ] = a31 * b11 + a32 * b21 + a33 * b31;
		te[ 5 ] = a31 * b12 + a32 * b22 + a33 * b32;
		te[ 8 ] = a31 * b13 + a32 * b23 + a33 * b33;

		return this;

	}
```
</details>

##### `multiplyScalar(s: number): Matrix3`

<details><summary>Code</summary>

```ts
multiplyScalar( s ) {

		const te = this.elements;

		te[ 0 ] *= s; te[ 3 ] *= s; te[ 6 ] *= s;
		te[ 1 ] *= s; te[ 4 ] *= s; te[ 7 ] *= s;
		te[ 2 ] *= s; te[ 5 ] *= s; te[ 8 ] *= s;

		return this;

	}
```
</details>

##### `determinant(): number`

<details><summary>Code</summary>

```ts
determinant() {

		const te = this.elements;

		const a = te[ 0 ], b = te[ 1 ], c = te[ 2 ],
			d = te[ 3 ], e = te[ 4 ], f = te[ 5 ],
			g = te[ 6 ], h = te[ 7 ], i = te[ 8 ];

		return a * e * i - a * f * h - b * d * i + b * f * g + c * d * h - c * e * g;

	}
```
</details>

##### `invert(): Matrix3`

<details><summary>Code</summary>

```ts
invert() {

		const te = this.elements,

			n11 = te[ 0 ], n21 = te[ 1 ], n31 = te[ 2 ],
			n12 = te[ 3 ], n22 = te[ 4 ], n32 = te[ 5 ],
			n13 = te[ 6 ], n23 = te[ 7 ], n33 = te[ 8 ],

			t11 = n33 * n22 - n32 * n23,
			t12 = n32 * n13 - n33 * n12,
			t13 = n23 * n12 - n22 * n13,

			det = n11 * t11 + n21 * t12 + n31 * t13;

		if ( det === 0 ) return this.set( 0, 0, 0, 0, 0, 0, 0, 0, 0 );

		const detInv = 1 / det;

		te[ 0 ] = t11 * detInv;
		te[ 1 ] = ( n31 * n23 - n33 * n21 ) * detInv;
		te[ 2 ] = ( n32 * n21 - n31 * n22 ) * detInv;

		te[ 3 ] = t12 * detInv;
		te[ 4 ] = ( n33 * n11 - n31 * n13 ) * detInv;
		te[ 5 ] = ( n31 * n12 - n32 * n11 ) * detInv;

		te[ 6 ] = t13 * detInv;
		te[ 7 ] = ( n21 * n13 - n23 * n11 ) * detInv;
		te[ 8 ] = ( n22 * n11 - n21 * n12 ) * detInv;

		return this;

	}
```
</details>

##### `transpose(): Matrix3`

<details><summary>Code</summary>

```ts
transpose() {

		let tmp;
		const m = this.elements;

		tmp = m[ 1 ]; m[ 1 ] = m[ 3 ]; m[ 3 ] = tmp;
		tmp = m[ 2 ]; m[ 2 ] = m[ 6 ]; m[ 6 ] = tmp;
		tmp = m[ 5 ]; m[ 5 ] = m[ 7 ]; m[ 7 ] = tmp;

		return this;

	}
```
</details>

##### `getNormalMatrix(matrix4: Matrix4): Matrix3`

<details><summary>Code</summary>

```ts
getNormalMatrix( matrix4 ) {

		return this.setFromMatrix4( matrix4 ).invert().transpose();

	}
```
</details>

##### `transposeIntoArray(r: number[]): Matrix3`

<details><summary>Code</summary>

```ts
transposeIntoArray( r ) {

		const m = this.elements;

		r[ 0 ] = m[ 0 ];
		r[ 1 ] = m[ 3 ];
		r[ 2 ] = m[ 6 ];
		r[ 3 ] = m[ 1 ];
		r[ 4 ] = m[ 4 ];
		r[ 5 ] = m[ 7 ];
		r[ 6 ] = m[ 2 ];
		r[ 7 ] = m[ 5 ];
		r[ 8 ] = m[ 8 ];

		return this;

	}
```
</details>

##### `setUvTransform(tx: number, ty: number, sx: number, sy: number, rotation: number, cx: number, cy: number): Matrix3`

<details><summary>Code</summary>

```ts
setUvTransform( tx, ty, sx, sy, rotation, cx, cy ) {

		const c = Math.cos( rotation );
		const s = Math.sin( rotation );

		this.set(
			sx * c, sx * s, - sx * ( c * cx + s * cy ) + cx + tx,
			- sy * s, sy * c, - sy * ( - s * cx + c * cy ) + cy + ty,
			0, 0, 1
		);

		return this;

	}
```
</details>

##### `scale(sx: number, sy: number): Matrix3`

<details><summary>Code</summary>

```ts
scale( sx, sy ) {

		this.premultiply( _m3.makeScale( sx, sy ) );

		return this;

	}
```
</details>

##### `rotate(theta: number): Matrix3`

<details><summary>Code</summary>

```ts
rotate( theta ) {

		this.premultiply( _m3.makeRotation( - theta ) );

		return this;

	}
```
</details>

##### `translate(tx: number, ty: number): Matrix3`

<details><summary>Code</summary>

```ts
translate( tx, ty ) {

		this.premultiply( _m3.makeTranslation( tx, ty ) );

		return this;

	}
```
</details>

##### `makeTranslation(x: any, y: number): Matrix3`

<details><summary>Code</summary>

```ts
makeTranslation( x, y ) {

		if ( x.isVector2 ) {

			this.set(

				1, 0, x.x,
				0, 1, x.y,
				0, 0, 1

			);

		} else {

			this.set(

				1, 0, x,
				0, 1, y,
				0, 0, 1

			);

		}

		return this;

	}
```
</details>

##### `makeRotation(theta: number): Matrix3`

<details><summary>Code</summary>

```ts
makeRotation( theta ) {

		// counterclockwise

		const c = Math.cos( theta );
		const s = Math.sin( theta );

		this.set(

			c, - s, 0,
			s, c, 0,
			0, 0, 1

		);

		return this;

	}
```
</details>

##### `makeScale(x: number, y: number): Matrix3`

<details><summary>Code</summary>

```ts
makeScale( x, y ) {

		this.set(

			x, 0, 0,
			0, y, 0,
			0, 0, 1

		);

		return this;

	}
```
</details>

##### `equals(matrix: Matrix3): boolean`

<details><summary>Code</summary>

```ts
equals( matrix ) {

		const te = this.elements;
		const me = matrix.elements;

		for ( let i = 0; i < 9; i ++ ) {

			if ( te[ i ] !== me[ i ] ) return false;

		}

		return true;

	}
```
</details>

##### `fromArray(array: number[], offset: number): Matrix3`

<details><summary>Code</summary>

```ts
fromArray( array, offset = 0 ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.elements[ i ] = array[ i + offset ];

		}

		return this;

	}
```
</details>

##### `toArray(array: number[], offset: number): number[]`

<details><summary>Code</summary>

```ts
toArray( array = [], offset = 0 ) {

		const te = this.elements;

		array[ offset ] = te[ 0 ];
		array[ offset + 1 ] = te[ 1 ];
		array[ offset + 2 ] = te[ 2 ];

		array[ offset + 3 ] = te[ 3 ];
		array[ offset + 4 ] = te[ 4 ];
		array[ offset + 5 ] = te[ 5 ];

		array[ offset + 6 ] = te[ 6 ];
		array[ offset + 7 ] = te[ 7 ];
		array[ offset + 8 ] = te[ 8 ];

		return array;

	}
```
</details>

##### `clone(): Matrix3`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor().fromArray( this.elements );

	}
```
</details>


---