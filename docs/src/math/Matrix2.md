[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Matrix2.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/Matrix2.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `te` | `number[]` | let/var | `this.elements` | ✗ |


---

## Functions

### `Matrix2.identity(): Matrix2`

**JSDoc:**
```typescript
/**
	 * Sets this matrix to the 2x2 identity matrix.
	 *
	 * @return {Matrix2} A reference to this matrix.
	 */
```

**Returns:** `Matrix2`

**Calls:**

- `this.set`

<details><summary>Code</summary>

```typescript
identity() {

		this.set(
			1, 0,
			0, 1,
		);

		return this;

	}
```
</details>

### `Matrix2.fromArray(array: number[], offset: number): Matrix2`

**JSDoc:**
```typescript
/**
	 * Sets the elements of the matrix from the given array.
	 *
	 * @param {Array<number>} array - The matrix elements in column-major order.
	 * @param {number} [offset=0] - Index of the first element in the array.
	 * @return {Matrix2} A reference to this matrix.
	 */
```

**Parameters:**

- **`array`** `number[]`
- **`offset`** `number`

**Returns:** `Matrix2`

<details><summary>Code</summary>

```typescript
fromArray( array, offset = 0 ) {

		for ( let i = 0; i < 4; i ++ ) {

			this.elements[ i ] = array[ i + offset ];

		}

		return this;

	}
```
</details>

### `Matrix2.set(n11: number, n12: number, n21: number, n22: number): Matrix2`

**JSDoc:**
```typescript
/**
	 * Sets the elements of the matrix.The arguments are supposed to be
	 * in row-major order.
	 *
	 * @param {number} n11 - 1-1 matrix element.
	 * @param {number} n12 - 1-2 matrix element.
	 * @param {number} n21 - 2-1 matrix element.
	 * @param {number} n22 - 2-2 matrix element.
	 * @return {Matrix2} A reference to this matrix.
	 */
```

**Parameters:**

- **`n11`** `number`
- **`n12`** `number`
- **`n21`** `number`
- **`n22`** `number`

**Returns:** `Matrix2`

<details><summary>Code</summary>

```typescript
set( n11, n12, n21, n22 ) {

		const te = this.elements;

		te[ 0 ] = n11; te[ 2 ] = n12;
		te[ 1 ] = n21; te[ 3 ] = n22;

		return this;

	}
```
</details>


---

## Classes

### `Matrix2`

<details><summary>Class Code</summary>

```ts
export class Matrix2 {

	/**
	 * Constructs a new 2x2 matrix. The arguments are supposed to be
	 * in row-major order. If no arguments are provided, the constructor
	 * initializes the matrix as an identity matrix.
	 *
	 * @param {number} [n11] - 1-1 matrix element.
	 * @param {number} [n12] - 1-2 matrix element.
	 * @param {number} [n21] - 2-1 matrix element.
	 * @param {number} [n22] - 2-2 matrix element.
	 */
	constructor( n11, n12, n21, n22 ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		Matrix2.prototype.isMatrix2 = true;

		/**
		 * A column-major list of matrix values.
		 *
		 * @type {Array<number>}
		 */
		this.elements = [
			1, 0,
			0, 1,
		];

		if ( n11 !== undefined ) {

			this.set( n11, n12, n21, n22 );

		}

	}

	/**
	 * Sets this matrix to the 2x2 identity matrix.
	 *
	 * @return {Matrix2} A reference to this matrix.
	 */
	identity() {

		this.set(
			1, 0,
			0, 1,
		);

		return this;

	}

	/**
	 * Sets the elements of the matrix from the given array.
	 *
	 * @param {Array<number>} array - The matrix elements in column-major order.
	 * @param {number} [offset=0] - Index of the first element in the array.
	 * @return {Matrix2} A reference to this matrix.
	 */
	fromArray( array, offset = 0 ) {

		for ( let i = 0; i < 4; i ++ ) {

			this.elements[ i ] = array[ i + offset ];

		}

		return this;

	}

	/**
	 * Sets the elements of the matrix.The arguments are supposed to be
	 * in row-major order.
	 *
	 * @param {number} n11 - 1-1 matrix element.
	 * @param {number} n12 - 1-2 matrix element.
	 * @param {number} n21 - 2-1 matrix element.
	 * @param {number} n22 - 2-2 matrix element.
	 * @return {Matrix2} A reference to this matrix.
	 */
	set( n11, n12, n21, n22 ) {

		const te = this.elements;

		te[ 0 ] = n11; te[ 2 ] = n12;
		te[ 1 ] = n21; te[ 3 ] = n22;

		return this;

	}

}
```
</details>

#### Methods

##### `identity(): Matrix2`

<details><summary>Code</summary>

```ts
identity() {

		this.set(
			1, 0,
			0, 1,
		);

		return this;

	}
```
</details>

##### `fromArray(array: number[], offset: number): Matrix2`

<details><summary>Code</summary>

```ts
fromArray( array, offset = 0 ) {

		for ( let i = 0; i < 4; i ++ ) {

			this.elements[ i ] = array[ i + offset ];

		}

		return this;

	}
```
</details>

##### `set(n11: number, n12: number, n21: number, n22: number): Matrix2`

<details><summary>Code</summary>

```ts
set( n11, n12, n21, n22 ) {

		const te = this.elements;

		te[ 0 ] = n11; te[ 2 ] = n12;
		te[ 1 ] = n21; te[ 3 ] = n22;

		return this;

	}
```
</details>


---