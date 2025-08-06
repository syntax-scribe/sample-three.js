[⬅️ Back to Table of Contents](../../index.md)

# 📄 `SphericalHarmonics3.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 14 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 13 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/SphericalHarmonics3.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `./Vector3.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `x` | `number` | let/var | `normal.x` | ✗ |
| `y` | `number` | let/var | `normal.y` | ✗ |
| `z` | `number` | let/var | `normal.z` | ✗ |
| `coeff` | `Vector3[]` | let/var | `this.coefficients` | ✗ |
| `x` | `number` | let/var | `normal.x` | ✗ |
| `y` | `number` | let/var | `normal.y` | ✗ |
| `z` | `number` | let/var | `normal.z` | ✗ |
| `coeff` | `Vector3[]` | let/var | `this.coefficients` | ✗ |
| `coefficients` | `Vector3[]` | let/var | `this.coefficients` | ✗ |
| `coefficients` | `Vector3[]` | let/var | `this.coefficients` | ✗ |
| `x` | `number` | let/var | `normal.x` | ✗ |
| `y` | `number` | let/var | `normal.y` | ✗ |
| `z` | `number` | let/var | `normal.z` | ✗ |


---

## Functions

### `SphericalHarmonics3.set(coefficients: Vector3[]): SphericalHarmonics3`

**JSDoc:**
```typescript
/**
	 * Sets the given SH coefficients to this instance by copying
	 * the values.
	 *
	 * @param {Array<Vector3>} coefficients - The SH coefficients.
	 * @return {SphericalHarmonics3} A reference to this spherical harmonics.
	 */
```

**Parameters:**

- **`coefficients`** `Vector3[]`

**Returns:** `SphericalHarmonics3`

**Calls:**

- `this.coefficients[ i ].copy`

<details><summary>Code</summary>

```typescript
set( coefficients ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].copy( coefficients[ i ] );

		}

		return this;

	}
```
</details>

### `SphericalHarmonics3.zero(): SphericalHarmonics3`

**JSDoc:**
```typescript
/**
	 * Sets all SH coefficients to `0`.
	 *
	 * @return {SphericalHarmonics3} A reference to this spherical harmonics.
	 */
```

**Returns:** `SphericalHarmonics3`

**Calls:**

- `this.coefficients[ i ].set`

<details><summary>Code</summary>

```typescript
zero() {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].set( 0, 0, 0 );

		}

		return this;

	}
```
</details>

### `SphericalHarmonics3.getAt(normal: Vector3, target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Returns the radiance in the direction of the given normal.
	 *
	 * @param {Vector3} normal - The normal vector (assumed to be unit length)
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The radiance.
	 */
```

**Parameters:**

- **`normal`** `Vector3`
- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `target.copy( coeff[ 0 ] ).multiplyScalar`
- `target.addScaledVector`

**Internal Comments:**
```
// normal is assumed to be unit length (x2)
// band 0 (x6)
// band 1 (x4)
// band 2 (x4)
```

<details><summary>Code</summary>

```typescript
getAt( normal, target ) {

		// normal is assumed to be unit length

		const x = normal.x, y = normal.y, z = normal.z;

		const coeff = this.coefficients;

		// band 0
		target.copy( coeff[ 0 ] ).multiplyScalar( 0.282095 );

		// band 1
		target.addScaledVector( coeff[ 1 ], 0.488603 * y );
		target.addScaledVector( coeff[ 2 ], 0.488603 * z );
		target.addScaledVector( coeff[ 3 ], 0.488603 * x );

		// band 2
		target.addScaledVector( coeff[ 4 ], 1.092548 * ( x * y ) );
		target.addScaledVector( coeff[ 5 ], 1.092548 * ( y * z ) );
		target.addScaledVector( coeff[ 6 ], 0.315392 * ( 3.0 * z * z - 1.0 ) );
		target.addScaledVector( coeff[ 7 ], 1.092548 * ( x * z ) );
		target.addScaledVector( coeff[ 8 ], 0.546274 * ( x * x - y * y ) );

		return target;

	}
```
</details>

### `SphericalHarmonics3.getIrradianceAt(normal: Vector3, target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Returns the irradiance (radiance convolved with cosine lobe) in the
	 * direction of the given normal.
	 *
	 * @param {Vector3} normal - The normal vector (assumed to be unit length)
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The irradiance.
	 */
```

**Parameters:**

- **`normal`** `Vector3`
- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `target.copy( coeff[ 0 ] ).multiplyScalar`
- `target.addScaledVector`

**Internal Comments:**
```
// normal is assumed to be unit length (x2)
// band 0 (x6)
// band 1 (x4)
// band 2 (x4)
```

<details><summary>Code</summary>

```typescript
getIrradianceAt( normal, target ) {

		// normal is assumed to be unit length

		const x = normal.x, y = normal.y, z = normal.z;

		const coeff = this.coefficients;

		// band 0
		target.copy( coeff[ 0 ] ).multiplyScalar( 0.886227 ); // π * 0.282095

		// band 1
		target.addScaledVector( coeff[ 1 ], 2.0 * 0.511664 * y ); // ( 2 * π / 3 ) * 0.488603
		target.addScaledVector( coeff[ 2 ], 2.0 * 0.511664 * z );
		target.addScaledVector( coeff[ 3 ], 2.0 * 0.511664 * x );

		// band 2
		target.addScaledVector( coeff[ 4 ], 2.0 * 0.429043 * x * y ); // ( π / 4 ) * 1.092548
		target.addScaledVector( coeff[ 5 ], 2.0 * 0.429043 * y * z );
		target.addScaledVector( coeff[ 6 ], 0.743125 * z * z - 0.247708 ); // ( π / 4 ) * 0.315392 * 3
		target.addScaledVector( coeff[ 7 ], 2.0 * 0.429043 * x * z );
		target.addScaledVector( coeff[ 8 ], 0.429043 * ( x * x - y * y ) ); // ( π / 4 ) * 0.546274

		return target;

	}
```
</details>

### `SphericalHarmonics3.add(sh: SphericalHarmonics3): SphericalHarmonics3`

**JSDoc:**
```typescript
/**
	 * Adds the given SH to this instance.
	 *
	 * @param {SphericalHarmonics3} sh - The SH to add.
	 * @return {SphericalHarmonics3} A reference to this spherical harmonics.
	 */
```

**Parameters:**

- **`sh`** `SphericalHarmonics3`

**Returns:** `SphericalHarmonics3`

**Calls:**

- `this.coefficients[ i ].add`

<details><summary>Code</summary>

```typescript
add( sh ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].add( sh.coefficients[ i ] );

		}

		return this;

	}
```
</details>

### `SphericalHarmonics3.addScaledSH(sh: SphericalHarmonics3, s: number): SphericalHarmonics3`

**JSDoc:**
```typescript
/**
	 * A convenience method for performing {@link SphericalHarmonics3#add} and
	 * {@link SphericalHarmonics3#scale} at once.
	 *
	 * @param {SphericalHarmonics3} sh - The SH to add.
	 * @param {number} s - The scale factor.
	 * @return {SphericalHarmonics3} A reference to this spherical harmonics.
	 */
```

**Parameters:**

- **`sh`** `SphericalHarmonics3`
- **`s`** `number`

**Returns:** `SphericalHarmonics3`

**Calls:**

- `this.coefficients[ i ].addScaledVector`

<details><summary>Code</summary>

```typescript
addScaledSH( sh, s ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].addScaledVector( sh.coefficients[ i ], s );

		}

		return this;

	}
```
</details>

### `SphericalHarmonics3.scale(s: number): SphericalHarmonics3`

**JSDoc:**
```typescript
/**
	 * Scales this SH by the given scale factor.
	 *
	 * @param {number} s - The scale factor.
	 * @return {SphericalHarmonics3} A reference to this spherical harmonics.
	 */
```

**Parameters:**

- **`s`** `number`

**Returns:** `SphericalHarmonics3`

**Calls:**

- `this.coefficients[ i ].multiplyScalar`

<details><summary>Code</summary>

```typescript
scale( s ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].multiplyScalar( s );

		}

		return this;

	}
```
</details>

### `SphericalHarmonics3.lerp(sh: SphericalHarmonics3, alpha: number): SphericalHarmonics3`

**JSDoc:**
```typescript
/**
	 * Linear interpolates between the given SH and this instance by the given
	 * alpha factor.
	 *
	 * @param {SphericalHarmonics3} sh - The SH to interpolate with.
	 * @param {number} alpha - The alpha factor.
	 * @return {SphericalHarmonics3} A reference to this spherical harmonics.
	 */
```

**Parameters:**

- **`sh`** `SphericalHarmonics3`
- **`alpha`** `number`

**Returns:** `SphericalHarmonics3`

**Calls:**

- `this.coefficients[ i ].lerp`

<details><summary>Code</summary>

```typescript
lerp( sh, alpha ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].lerp( sh.coefficients[ i ], alpha );

		}

		return this;

	}
```
</details>

### `SphericalHarmonics3.equals(sh: SphericalHarmonics3): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this spherical harmonics is equal with the given one.
	 *
	 * @param {SphericalHarmonics3} sh - The spherical harmonics to test for equality.
	 * @return {boolean} Whether this spherical harmonics is equal with the given one.
	 */
```

**Parameters:**

- **`sh`** `SphericalHarmonics3`

**Returns:** `boolean`

**Calls:**

- `this.coefficients[ i ].equals`

<details><summary>Code</summary>

```typescript
equals( sh ) {

		for ( let i = 0; i < 9; i ++ ) {

			if ( ! this.coefficients[ i ].equals( sh.coefficients[ i ] ) ) {

				return false;

			}

		}

		return true;

	}
```
</details>

### `SphericalHarmonics3.copy(sh: SphericalHarmonics3): SphericalHarmonics3`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given spherical harmonics to this instance.
	 *
	 * @param {SphericalHarmonics3} sh - The spherical harmonics to copy.
	 * @return {SphericalHarmonics3} A reference to this spherical harmonics.
	 */
```

**Parameters:**

- **`sh`** `SphericalHarmonics3`

**Returns:** `SphericalHarmonics3`

**Calls:**

- `this.set`

<details><summary>Code</summary>

```typescript
copy( sh ) {

		return this.set( sh.coefficients );

	}
```
</details>

### `SphericalHarmonics3.clone(): SphericalHarmonics3`

**JSDoc:**
```typescript
/**
	 * Returns a new spherical harmonics with copied values from this instance.
	 *
	 * @return {SphericalHarmonics3} A clone of this instance.
	 */
```

**Returns:** `SphericalHarmonics3`

**Calls:**

- `new this.constructor().copy`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor().copy( this );

	}
```
</details>

### `SphericalHarmonics3.fromArray(array: number[], offset: number): SphericalHarmonics3`

**JSDoc:**
```typescript
/**
	 * Sets the SH coefficients of this instance from the given array.
	 *
	 * @param {Array<number>} array - An array holding the SH coefficients.
	 * @param {number} [offset=0] - The array offset where to start copying.
	 * @return {SphericalHarmonics3} A clone of this instance.
	 */
```

**Parameters:**

- **`array`** `number[]`
- **`offset`** `number`

**Returns:** `SphericalHarmonics3`

**Calls:**

- `coefficients[ i ].fromArray`

<details><summary>Code</summary>

```typescript
fromArray( array, offset = 0 ) {

		const coefficients = this.coefficients;

		for ( let i = 0; i < 9; i ++ ) {

			coefficients[ i ].fromArray( array, offset + ( i * 3 ) );

		}

		return this;

	}
```
</details>

### `SphericalHarmonics3.toArray(array: number[], offset: number): number[]`

**JSDoc:**
```typescript
/**
	 * Returns an array with the SH coefficients, or copies them into the provided
	 * array. The coefficients are represented as numbers.
	 *
	 * @param {Array<number>} [array=[]] - The target array.
	 * @param {number} [offset=0] - The array offset where to start copying.
	 * @return {Array<number>} An array with flat SH coefficients.
	 */
```

**Parameters:**

- **`array`** `number[]`
- **`offset`** `number`

**Returns:** `number[]`

**Calls:**

- `coefficients[ i ].toArray`

<details><summary>Code</summary>

```typescript
toArray( array = [], offset = 0 ) {

		const coefficients = this.coefficients;

		for ( let i = 0; i < 9; i ++ ) {

			coefficients[ i ].toArray( array, offset + ( i * 3 ) );

		}

		return array;

	}
```
</details>

### `SphericalHarmonics3.getBasisAt(normal: Vector3, shBasis: number[]): void`

**JSDoc:**
```typescript
/**
	 * Computes the SH basis for the given normal vector.
	 *
	 * @param {Vector3} normal - The normal.
	 * @param {Array<number>} shBasis - The target array holding the SH basis.
	 */
```

**Parameters:**

- **`normal`** `Vector3`
- **`shBasis`** `number[]`

**Returns:** `void`

**Internal Comments:**
```
// normal is assumed to be unit length (x2)
// band 0 (x4)
// band 1 (x4)
// band 2 (x4)
```

<details><summary>Code</summary>

```typescript
static getBasisAt( normal, shBasis ) {

		// normal is assumed to be unit length

		const x = normal.x, y = normal.y, z = normal.z;

		// band 0
		shBasis[ 0 ] = 0.282095;

		// band 1
		shBasis[ 1 ] = 0.488603 * y;
		shBasis[ 2 ] = 0.488603 * z;
		shBasis[ 3 ] = 0.488603 * x;

		// band 2
		shBasis[ 4 ] = 1.092548 * x * y;
		shBasis[ 5 ] = 1.092548 * y * z;
		shBasis[ 6 ] = 0.315392 * ( 3 * z * z - 1 );
		shBasis[ 7 ] = 1.092548 * x * z;
		shBasis[ 8 ] = 0.546274 * ( x * x - y * y );

	}
```
</details>


---

## Classes

### `SphericalHarmonics3`

<details><summary>Class Code</summary>

```ts
class SphericalHarmonics3 {

	/**
	 * Constructs a new spherical harmonics.
	 */
	constructor() {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSphericalHarmonics3 = true;

		/**
		 * An array holding the (9) SH coefficients.
		 *
		 * @type {Array<Vector3>}
		 */
		this.coefficients = [];

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients.push( new Vector3() );

		}

	}

	/**
	 * Sets the given SH coefficients to this instance by copying
	 * the values.
	 *
	 * @param {Array<Vector3>} coefficients - The SH coefficients.
	 * @return {SphericalHarmonics3} A reference to this spherical harmonics.
	 */
	set( coefficients ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].copy( coefficients[ i ] );

		}

		return this;

	}

	/**
	 * Sets all SH coefficients to `0`.
	 *
	 * @return {SphericalHarmonics3} A reference to this spherical harmonics.
	 */
	zero() {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].set( 0, 0, 0 );

		}

		return this;

	}

	/**
	 * Returns the radiance in the direction of the given normal.
	 *
	 * @param {Vector3} normal - The normal vector (assumed to be unit length)
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The radiance.
	 */
	getAt( normal, target ) {

		// normal is assumed to be unit length

		const x = normal.x, y = normal.y, z = normal.z;

		const coeff = this.coefficients;

		// band 0
		target.copy( coeff[ 0 ] ).multiplyScalar( 0.282095 );

		// band 1
		target.addScaledVector( coeff[ 1 ], 0.488603 * y );
		target.addScaledVector( coeff[ 2 ], 0.488603 * z );
		target.addScaledVector( coeff[ 3 ], 0.488603 * x );

		// band 2
		target.addScaledVector( coeff[ 4 ], 1.092548 * ( x * y ) );
		target.addScaledVector( coeff[ 5 ], 1.092548 * ( y * z ) );
		target.addScaledVector( coeff[ 6 ], 0.315392 * ( 3.0 * z * z - 1.0 ) );
		target.addScaledVector( coeff[ 7 ], 1.092548 * ( x * z ) );
		target.addScaledVector( coeff[ 8 ], 0.546274 * ( x * x - y * y ) );

		return target;

	}

	/**
	 * Returns the irradiance (radiance convolved with cosine lobe) in the
	 * direction of the given normal.
	 *
	 * @param {Vector3} normal - The normal vector (assumed to be unit length)
	 * @param {Vector3} target - The target vector that is used to store the method's result.
	 * @return {Vector3} The irradiance.
	 */
	getIrradianceAt( normal, target ) {

		// normal is assumed to be unit length

		const x = normal.x, y = normal.y, z = normal.z;

		const coeff = this.coefficients;

		// band 0
		target.copy( coeff[ 0 ] ).multiplyScalar( 0.886227 ); // π * 0.282095

		// band 1
		target.addScaledVector( coeff[ 1 ], 2.0 * 0.511664 * y ); // ( 2 * π / 3 ) * 0.488603
		target.addScaledVector( coeff[ 2 ], 2.0 * 0.511664 * z );
		target.addScaledVector( coeff[ 3 ], 2.0 * 0.511664 * x );

		// band 2
		target.addScaledVector( coeff[ 4 ], 2.0 * 0.429043 * x * y ); // ( π / 4 ) * 1.092548
		target.addScaledVector( coeff[ 5 ], 2.0 * 0.429043 * y * z );
		target.addScaledVector( coeff[ 6 ], 0.743125 * z * z - 0.247708 ); // ( π / 4 ) * 0.315392 * 3
		target.addScaledVector( coeff[ 7 ], 2.0 * 0.429043 * x * z );
		target.addScaledVector( coeff[ 8 ], 0.429043 * ( x * x - y * y ) ); // ( π / 4 ) * 0.546274

		return target;

	}

	/**
	 * Adds the given SH to this instance.
	 *
	 * @param {SphericalHarmonics3} sh - The SH to add.
	 * @return {SphericalHarmonics3} A reference to this spherical harmonics.
	 */
	add( sh ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].add( sh.coefficients[ i ] );

		}

		return this;

	}

	/**
	 * A convenience method for performing {@link SphericalHarmonics3#add} and
	 * {@link SphericalHarmonics3#scale} at once.
	 *
	 * @param {SphericalHarmonics3} sh - The SH to add.
	 * @param {number} s - The scale factor.
	 * @return {SphericalHarmonics3} A reference to this spherical harmonics.
	 */
	addScaledSH( sh, s ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].addScaledVector( sh.coefficients[ i ], s );

		}

		return this;

	}

	/**
	 * Scales this SH by the given scale factor.
	 *
	 * @param {number} s - The scale factor.
	 * @return {SphericalHarmonics3} A reference to this spherical harmonics.
	 */
	scale( s ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].multiplyScalar( s );

		}

		return this;

	}

	/**
	 * Linear interpolates between the given SH and this instance by the given
	 * alpha factor.
	 *
	 * @param {SphericalHarmonics3} sh - The SH to interpolate with.
	 * @param {number} alpha - The alpha factor.
	 * @return {SphericalHarmonics3} A reference to this spherical harmonics.
	 */
	lerp( sh, alpha ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].lerp( sh.coefficients[ i ], alpha );

		}

		return this;

	}

	/**
	 * Returns `true` if this spherical harmonics is equal with the given one.
	 *
	 * @param {SphericalHarmonics3} sh - The spherical harmonics to test for equality.
	 * @return {boolean} Whether this spherical harmonics is equal with the given one.
	 */
	equals( sh ) {

		for ( let i = 0; i < 9; i ++ ) {

			if ( ! this.coefficients[ i ].equals( sh.coefficients[ i ] ) ) {

				return false;

			}

		}

		return true;

	}

	/**
	 * Copies the values of the given spherical harmonics to this instance.
	 *
	 * @param {SphericalHarmonics3} sh - The spherical harmonics to copy.
	 * @return {SphericalHarmonics3} A reference to this spherical harmonics.
	 */
	copy( sh ) {

		return this.set( sh.coefficients );

	}

	/**
	 * Returns a new spherical harmonics with copied values from this instance.
	 *
	 * @return {SphericalHarmonics3} A clone of this instance.
	 */
	clone() {

		return new this.constructor().copy( this );

	}

	/**
	 * Sets the SH coefficients of this instance from the given array.
	 *
	 * @param {Array<number>} array - An array holding the SH coefficients.
	 * @param {number} [offset=0] - The array offset where to start copying.
	 * @return {SphericalHarmonics3} A clone of this instance.
	 */
	fromArray( array, offset = 0 ) {

		const coefficients = this.coefficients;

		for ( let i = 0; i < 9; i ++ ) {

			coefficients[ i ].fromArray( array, offset + ( i * 3 ) );

		}

		return this;

	}

	/**
	 * Returns an array with the SH coefficients, or copies them into the provided
	 * array. The coefficients are represented as numbers.
	 *
	 * @param {Array<number>} [array=[]] - The target array.
	 * @param {number} [offset=0] - The array offset where to start copying.
	 * @return {Array<number>} An array with flat SH coefficients.
	 */
	toArray( array = [], offset = 0 ) {

		const coefficients = this.coefficients;

		for ( let i = 0; i < 9; i ++ ) {

			coefficients[ i ].toArray( array, offset + ( i * 3 ) );

		}

		return array;

	}

	/**
	 * Computes the SH basis for the given normal vector.
	 *
	 * @param {Vector3} normal - The normal.
	 * @param {Array<number>} shBasis - The target array holding the SH basis.
	 */
	static getBasisAt( normal, shBasis ) {

		// normal is assumed to be unit length

		const x = normal.x, y = normal.y, z = normal.z;

		// band 0
		shBasis[ 0 ] = 0.282095;

		// band 1
		shBasis[ 1 ] = 0.488603 * y;
		shBasis[ 2 ] = 0.488603 * z;
		shBasis[ 3 ] = 0.488603 * x;

		// band 2
		shBasis[ 4 ] = 1.092548 * x * y;
		shBasis[ 5 ] = 1.092548 * y * z;
		shBasis[ 6 ] = 0.315392 * ( 3 * z * z - 1 );
		shBasis[ 7 ] = 1.092548 * x * z;
		shBasis[ 8 ] = 0.546274 * ( x * x - y * y );

	}

}
```
</details>

#### Methods

##### `set(coefficients: Vector3[]): SphericalHarmonics3`

<details><summary>Code</summary>

```ts
set( coefficients ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].copy( coefficients[ i ] );

		}

		return this;

	}
```
</details>

##### `zero(): SphericalHarmonics3`

<details><summary>Code</summary>

```ts
zero() {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].set( 0, 0, 0 );

		}

		return this;

	}
```
</details>

##### `getAt(normal: Vector3, target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getAt( normal, target ) {

		// normal is assumed to be unit length

		const x = normal.x, y = normal.y, z = normal.z;

		const coeff = this.coefficients;

		// band 0
		target.copy( coeff[ 0 ] ).multiplyScalar( 0.282095 );

		// band 1
		target.addScaledVector( coeff[ 1 ], 0.488603 * y );
		target.addScaledVector( coeff[ 2 ], 0.488603 * z );
		target.addScaledVector( coeff[ 3 ], 0.488603 * x );

		// band 2
		target.addScaledVector( coeff[ 4 ], 1.092548 * ( x * y ) );
		target.addScaledVector( coeff[ 5 ], 1.092548 * ( y * z ) );
		target.addScaledVector( coeff[ 6 ], 0.315392 * ( 3.0 * z * z - 1.0 ) );
		target.addScaledVector( coeff[ 7 ], 1.092548 * ( x * z ) );
		target.addScaledVector( coeff[ 8 ], 0.546274 * ( x * x - y * y ) );

		return target;

	}
```
</details>

##### `getIrradianceAt(normal: Vector3, target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getIrradianceAt( normal, target ) {

		// normal is assumed to be unit length

		const x = normal.x, y = normal.y, z = normal.z;

		const coeff = this.coefficients;

		// band 0
		target.copy( coeff[ 0 ] ).multiplyScalar( 0.886227 ); // π * 0.282095

		// band 1
		target.addScaledVector( coeff[ 1 ], 2.0 * 0.511664 * y ); // ( 2 * π / 3 ) * 0.488603
		target.addScaledVector( coeff[ 2 ], 2.0 * 0.511664 * z );
		target.addScaledVector( coeff[ 3 ], 2.0 * 0.511664 * x );

		// band 2
		target.addScaledVector( coeff[ 4 ], 2.0 * 0.429043 * x * y ); // ( π / 4 ) * 1.092548
		target.addScaledVector( coeff[ 5 ], 2.0 * 0.429043 * y * z );
		target.addScaledVector( coeff[ 6 ], 0.743125 * z * z - 0.247708 ); // ( π / 4 ) * 0.315392 * 3
		target.addScaledVector( coeff[ 7 ], 2.0 * 0.429043 * x * z );
		target.addScaledVector( coeff[ 8 ], 0.429043 * ( x * x - y * y ) ); // ( π / 4 ) * 0.546274

		return target;

	}
```
</details>

##### `add(sh: SphericalHarmonics3): SphericalHarmonics3`

<details><summary>Code</summary>

```ts
add( sh ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].add( sh.coefficients[ i ] );

		}

		return this;

	}
```
</details>

##### `addScaledSH(sh: SphericalHarmonics3, s: number): SphericalHarmonics3`

<details><summary>Code</summary>

```ts
addScaledSH( sh, s ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].addScaledVector( sh.coefficients[ i ], s );

		}

		return this;

	}
```
</details>

##### `scale(s: number): SphericalHarmonics3`

<details><summary>Code</summary>

```ts
scale( s ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].multiplyScalar( s );

		}

		return this;

	}
```
</details>

##### `lerp(sh: SphericalHarmonics3, alpha: number): SphericalHarmonics3`

<details><summary>Code</summary>

```ts
lerp( sh, alpha ) {

		for ( let i = 0; i < 9; i ++ ) {

			this.coefficients[ i ].lerp( sh.coefficients[ i ], alpha );

		}

		return this;

	}
```
</details>

##### `equals(sh: SphericalHarmonics3): boolean`

<details><summary>Code</summary>

```ts
equals( sh ) {

		for ( let i = 0; i < 9; i ++ ) {

			if ( ! this.coefficients[ i ].equals( sh.coefficients[ i ] ) ) {

				return false;

			}

		}

		return true;

	}
```
</details>

##### `copy(sh: SphericalHarmonics3): SphericalHarmonics3`

<details><summary>Code</summary>

```ts
copy( sh ) {

		return this.set( sh.coefficients );

	}
```
</details>

##### `clone(): SphericalHarmonics3`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor().copy( this );

	}
```
</details>

##### `fromArray(array: number[], offset: number): SphericalHarmonics3`

<details><summary>Code</summary>

```ts
fromArray( array, offset = 0 ) {

		const coefficients = this.coefficients;

		for ( let i = 0; i < 9; i ++ ) {

			coefficients[ i ].fromArray( array, offset + ( i * 3 ) );

		}

		return this;

	}
```
</details>

##### `toArray(array: number[], offset: number): number[]`

<details><summary>Code</summary>

```ts
toArray( array = [], offset = 0 ) {

		const coefficients = this.coefficients;

		for ( let i = 0; i < 9; i ++ ) {

			coefficients[ i ].toArray( array, offset + ( i * 3 ) );

		}

		return array;

	}
```
</details>

##### `getBasisAt(normal: Vector3, shBasis: number[]): void`

<details><summary>Code</summary>

```ts
static getBasisAt( normal, shBasis ) {

		// normal is assumed to be unit length

		const x = normal.x, y = normal.y, z = normal.z;

		// band 0
		shBasis[ 0 ] = 0.282095;

		// band 1
		shBasis[ 1 ] = 0.488603 * y;
		shBasis[ 2 ] = 0.488603 * z;
		shBasis[ 3 ] = 0.488603 * x;

		// band 2
		shBasis[ 4 ] = 1.092548 * x * y;
		shBasis[ 5 ] = 1.092548 * y * z;
		shBasis[ 6 ] = 0.315392 * ( 3 * z * z - 1 );
		shBasis[ 7 ] = 1.092548 * x * z;
		shBasis[ 8 ] = 0.546274 * ( x * x - y * y );

	}
```
</details>


---