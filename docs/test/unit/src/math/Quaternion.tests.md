[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Quaternion.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 13 |
| 📦 Imports | 11 |
| 📊 Variables & Constants | 73 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/math/Quaternion.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `Quaternion` | `../../../../src/math/Quaternion.js` |
| `Vector3` | `../../../../src/math/Vector3.js` |
| `Vector4` | `../../../../src/math/Vector4.js` |
| `Euler` | `../../../../src/math/Euler.js` |
| `Matrix4` | `../../../../src/math/Matrix4.js` |
| `x` | `../../utils/math-constants.js` |
| `y` | `../../utils/math-constants.js` |
| `z` | `../../utils/math-constants.js` |
| `w` | `../../utils/math-constants.js` |
| `eps` | `../../utils/math-constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `orders` | `string[]` | let/var | `[ 'XYZ', 'YXZ', 'ZXY', 'ZYX', 'YZX', 'XZY' ]` | ✗ |
| `eulerAngles` | `Euler` | let/var | `new Euler( 0.1, - 0.3, 0.25 )` | ✗ |
| `result` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `result` | `number[]` | let/var | `[ 0, 0, 0, 0 ]` | ✗ |
| `result` | `any` | let/var | `*not shown*` | ✗ |
| `a` | `number[]` | let/var | `[ 0.6753410084407496, 0.4087830051091744, 0.32856700410659473, 0.518512006480...` | ✗ |
| `b` | `number[]` | let/var | `[ 0.6602792107657797, 0.43647413932562285, 0.35119011210236006, 0.50018715966...` | ✗ |
| `maxNormError` | `number` | let/var | `0` | ✗ |
| `D` | `number` | let/var | `Math.SQRT1_2` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `b` | `boolean` | let/var | `false` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `b` | `boolean` | let/var | `false` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `b` | `boolean` | let/var | `false` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `b` | `boolean` | let/var | `false` | ✗ |
| `object` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion( x, y, z, w )` | ✗ |
| `angles` | `Vector3[]` | let/var | `[ new Vector3( 1, 0, 0 ), new Vector3( 0, 1, 0 ), new Vector3( 0, 0, 1 ) ]` | ✗ |
| `newAngle` | `Vector3` | let/var | `new Vector3( eulers2.x, eulers2.y, eulers2.z )` | ✗ |
| `zero` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `expected` | `Vector4` | let/var | `new Vector4( 0.8581163303210332, 0.19069251784911848, - 0.2860387767736777, 0...` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( 1, 0, 0 )` | ✗ |
| `c` | `Vector3` | let/var | `new Vector3( 0, 1, 0 )` | ✗ |
| `expected` | `Quaternion` | let/var | `new Quaternion( 0, 0, Math.sqrt( 2 ) / 2, Math.sqrt( 2 ) / 2 )` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `c` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `halfPI` | `number` | let/var | `Math.PI * 0.5` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion( x, y, z, w )` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `b` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion( x, y, z, w )` | ✗ |
| `angles` | `Euler[]` | let/var | `[ new Euler( 1, 0, 0 ), new Euler( 0, 1, 0 ), new Euler( 0, 0, 1 ) ]` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion( x, y, z, w )` | ✗ |
| `b` | `Quaternion` | let/var | `new Quaternion( 2 * x, - y, - 2 * z, w )` | ✗ |
| `expected` | `Quaternion` | let/var | `new Quaternion( 42, - 32, - 2, 58 )` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion( x, y, z, w )` | ✗ |
| `b` | `Quaternion` | let/var | `new Quaternion( - x, - y, - z, - w )` | ✗ |
| `D` | `number` | let/var | `Math.SQRT1_2` | ✗ |
| `e` | `Quaternion` | let/var | `new Quaternion( 1, 0, 0, 0 )` | ✗ |
| `f` | `Quaternion` | let/var | `new Quaternion( 0, 0, 1, 0 )` | ✗ |
| `expected` | `Quaternion` | let/var | `new Quaternion( D, 0, D, 0 )` | ✗ |
| `g` | `Quaternion` | let/var | `new Quaternion( 0, D, 0, D )` | ✗ |
| `h` | `Quaternion` | let/var | `new Quaternion( 0, - D, 0, D )` | ✗ |
| `e` | `Quaternion` | let/var | `new Quaternion( 1, 0, 0, 0 )` | ✗ |
| `f` | `Quaternion` | let/var | `new Quaternion( 0, 0, 1, 0 )` | ✗ |
| `expected` | `Quaternion` | let/var | `new Quaternion( Math.SQRT1_2, 0, Math.SQRT1_2, 0 )` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `identity` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion( x, y, z, w )` | ✗ |
| `b` | `Quaternion` | let/var | `new Quaternion( - x, - y, - z, - w )` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion( x, y, z, w )` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `attribute` | `BufferAttribute` | let/var | `new BufferAttribute( new Float32Array( [ 0, 0, 0, 1, .7, 0, 0, .7, 0, .7, 0, ...` | ✗ |
| `b` | `boolean` | let/var | `false` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion( 11, 12, 13, 1 )` | ✗ |
| `b` | `boolean` | let/var | `false` | ✗ |
| `a` | `Quaternion` | let/var | `new Quaternion( 11, 12, 13, 1 )` | ✗ |
| `angles` | `Euler[]` | let/var | `[ new Euler( 1, 0, 0 ), new Euler( 0, 1, 0 ), new Euler( 0, 0, 1 ) ]` | ✗ |
| `v0` | `Vector3` | let/var | `new Vector3( 1, 0, 0 )` | ✗ |
| `q` | `Quaternion` | let/var | `new Quaternion( 0, 0.5, 0.7, 1 )` | ✗ |
| `q` | `Quaternion` | let/var | `new Quaternion( 0, 0.5, 0.7, 1 )` | ✗ |
| `array` | `number[]` | let/var | `[ ...q ]` | ✗ |


---

## Functions

### `qSub(a: any, b: any): Quaternion`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `Quaternion`

**Calls:**

- `result.copy`

<details><summary>Code</summary>

```typescript
function qSub( a, b ) {

	const result = new Quaternion();
	result.copy( a );

	result.x -= b.x;
	result.y -= b.y;
	result.z -= b.z;
	result.w -= b.w;

	return result;

}
```
</details>

### `doSlerpObject(aArr: any, bArr: any, t: any): { equals: (x: any, y: any, z: any, w: any, maxError: any) => boolean; length: number; dotA: number; dotB: number; }`

**Parameters:**

- **`aArr`** `any`
- **`bArr`** `any`
- **`t`** `any`

**Returns:** `{ equals: (x: any, y: any, z: any, w: any, maxError: any) => boolean; length: number; dotA: number; dotB: number; }`

**Calls:**

- `new Quaternion().fromArray`
- `c.slerp`
- `Math.abs`
- `c.length`
- `c.dot`

<details><summary>Code</summary>

```typescript
function doSlerpObject( aArr, bArr, t ) {

	const a = new Quaternion().fromArray( aArr ),
		b = new Quaternion().fromArray( bArr ),
		c = new Quaternion().fromArray( aArr );

	c.slerp( b, t );

	return {

		equals: function ( x, y, z, w, maxError ) {

			if ( maxError === undefined ) maxError = Number.EPSILON;

			return Math.abs( x - c.x ) <= maxError &&
				Math.abs( y - c.y ) <= maxError &&
				Math.abs( z - c.z ) <= maxError &&
				Math.abs( w - c.w ) <= maxError;

		},

		length: c.length(),

		dotA: c.dot( a ),
		dotB: c.dot( b )

	};

}
```
</details>

### `equals(x: any, y: any, z: any, w: any, maxError: any): boolean`

**Parameters:**

- **`x`** `any`
- **`y`** `any`
- **`z`** `any`
- **`w`** `any`
- **`maxError`** `any`

**Returns:** `boolean`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
function ( x, y, z, w, maxError ) {

			if ( maxError === undefined ) maxError = Number.EPSILON;

			return Math.abs( x - c.x ) <= maxError &&
				Math.abs( y - c.y ) <= maxError &&
				Math.abs( z - c.z ) <= maxError &&
				Math.abs( w - c.w ) <= maxError;

		}
```
</details>

### `equals(x: any, y: any, z: any, w: any, maxError: any): boolean`

**Parameters:**

- **`x`** `any`
- **`y`** `any`
- **`z`** `any`
- **`w`** `any`
- **`maxError`** `any`

**Returns:** `boolean`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
function ( x, y, z, w, maxError ) {

			if ( maxError === undefined ) maxError = Number.EPSILON;

			return Math.abs( x - c.x ) <= maxError &&
				Math.abs( y - c.y ) <= maxError &&
				Math.abs( z - c.z ) <= maxError &&
				Math.abs( w - c.w ) <= maxError;

		}
```
</details>

### `doSlerpArray(a: any, b: any, t: any): { equals: (x: any, y: any, z: any, w: any, maxError: any) => boolean; length: number; dotA: number; dotB: number; }`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`t`** `any`

**Returns:** `{ equals: (x: any, y: any, z: any, w: any, maxError: any) => boolean; length: number; dotA: number; dotB: number; }`

**Calls:**

- `Quaternion.slerpFlat`
- `Math.abs`
- `Math.sqrt`
- `arrDot`

<details><summary>Code</summary>

```typescript
function doSlerpArray( a, b, t ) {

	const result = [ 0, 0, 0, 0 ];

	Quaternion.slerpFlat( result, 0, a, 0, b, 0, t );

	function arrDot( a, b ) {

		return a[ 0 ] * b[ 0 ] + a[ 1 ] * b[ 1 ] +
			a[ 2 ] * b[ 2 ] + a[ 3 ] * b[ 3 ];

	}

	return {

		equals: function ( x, y, z, w, maxError ) {

			if ( maxError === undefined ) maxError = Number.EPSILON;

			return Math.abs( x - result[ 0 ] ) <= maxError &&
				Math.abs( y - result[ 1 ] ) <= maxError &&
				Math.abs( z - result[ 2 ] ) <= maxError &&
				Math.abs( w - result[ 3 ] ) <= maxError;

		},

		length: Math.sqrt( arrDot( result, result ) ),

		dotA: arrDot( result, a ),
		dotB: arrDot( result, b )

	};

}
```
</details>

### `arrDot(a: any, b: any): number`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function arrDot( a, b ) {

		return a[ 0 ] * b[ 0 ] + a[ 1 ] * b[ 1 ] +
			a[ 2 ] * b[ 2 ] + a[ 3 ] * b[ 3 ];

	}
```
</details>

### `equals(x: any, y: any, z: any, w: any, maxError: any): boolean`

**Parameters:**

- **`x`** `any`
- **`y`** `any`
- **`z`** `any`
- **`w`** `any`
- **`maxError`** `any`

**Returns:** `boolean`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
function ( x, y, z, w, maxError ) {

			if ( maxError === undefined ) maxError = Number.EPSILON;

			return Math.abs( x - result[ 0 ] ) <= maxError &&
				Math.abs( y - result[ 1 ] ) <= maxError &&
				Math.abs( z - result[ 2 ] ) <= maxError &&
				Math.abs( w - result[ 3 ] ) <= maxError;

		}
```
</details>

### `equals(x: any, y: any, z: any, w: any, maxError: any): boolean`

**Parameters:**

- **`x`** `any`
- **`y`** `any`
- **`z`** `any`
- **`w`** `any`
- **`maxError`** `any`

**Returns:** `boolean`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
function ( x, y, z, w, maxError ) {

			if ( maxError === undefined ) maxError = Number.EPSILON;

			return Math.abs( x - result[ 0 ] ) <= maxError &&
				Math.abs( y - result[ 1 ] ) <= maxError &&
				Math.abs( z - result[ 2 ] ) <= maxError &&
				Math.abs( w - result[ 3 ] ) <= maxError;

		}
```
</details>

### `slerpTestSkeleton(doSlerp: any, maxError: any, assert: any): void`

**Parameters:**

- **`doSlerp`** `any`
- **`maxError`** `any`
- **`assert`** `any`

**Returns:** `void`

**Calls:**

- `Math.abs`
- `Math.max`
- `doSlerp`
- `assert.ok`
- `result.equals`
- `isNormal`

<details><summary>Code</summary>

```typescript
function slerpTestSkeleton( doSlerp, maxError, assert ) {

	let result;

	const a = [
		0.6753410084407496,
		0.4087830051091744,
		0.32856700410659473,
		0.5185120064806223
	];

	const b = [
		0.6602792107657797,
		0.43647413932562285,
		0.35119011210236006,
		0.5001871596632682
	];

	let maxNormError = 0;

	function isNormal( result ) {

		const normError = Math.abs( 1 - result.length );
		maxNormError = Math.max( maxNormError, normError );
		return normError <= maxError;

	}

	result = doSlerp( a, b, 0 );
	assert.ok( result.equals(
		a[ 0 ], a[ 1 ], a[ 2 ], a[ 3 ], 0 ), 'Exactly A @ t = 0' );

	result = doSlerp( a, b, 1 );
	assert.ok( result.equals(
		b[ 0 ], b[ 1 ], b[ 2 ], b[ 3 ], 0 ), 'Exactly B @ t = 1' );

	result = doSlerp( a, b, 0.5 );
	assert.ok( Math.abs( result.dotA - result.dotB ) <= Number.EPSILON, 'Symmetry at 0.5' );
	assert.ok( isNormal( result ), 'Approximately normal (at 0.5)' );

	result = doSlerp( a, b, 0.25 );
	assert.ok( result.dotA > result.dotB, 'Interpolating at 0.25' );
	assert.ok( isNormal( result ), 'Approximately normal (at 0.25)' );

	result = doSlerp( a, b, 0.75 );
	assert.ok( result.dotA < result.dotB, 'Interpolating at 0.75' );
	assert.ok( isNormal( result ), 'Approximately normal (at 0.75)' );

	const D = Math.SQRT1_2;

	result = doSlerp( [ 1, 0, 0, 0 ], [ 0, 0, 1, 0 ], 0.5 );
	assert.ok( result.equals( D, 0, D, 0 ), 'X/Z diagonal from axes' );
	assert.ok( isNormal( result ), 'Approximately normal (X/Z diagonal)' );

	result = doSlerp( [ 0, D, 0, D ], [ 0, - D, 0, D ], 0.5 );
	assert.ok( result.equals( 0, 0, 0, 1 ), 'W-Unit from diagonals' );
	assert.ok( isNormal( result ), 'Approximately normal (W-Unit)' );

}
```
</details>

### `isNormal(result: any): boolean`

**Parameters:**

- **`result`** `any`

**Returns:** `boolean`

**Calls:**

- `Math.abs`
- `Math.max`

<details><summary>Code</summary>

```typescript
function isNormal( result ) {

		const normError = Math.abs( 1 - result.length );
		maxNormError = Math.max( maxNormError, normError );
		return normError <= maxError;

	}
```
</details>

### `changeEulerOrder(euler: any, order: any): Euler`

**Parameters:**

- **`euler`** `any`
- **`order`** `any`

**Returns:** `Euler`

<details><summary>Code</summary>

```typescript
function changeEulerOrder( euler, order ) {

	return new Euler( euler.x, euler.y, euler.z, order );

}
```
</details>

### `f(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

				b = true;

			}
```
</details>

### `f(): void`

**Returns:** `void`

**Calls:**

- `assert.ok`

<details><summary>Code</summary>

```typescript
function () {

				b = true;
				assert.ok( a === this, 'Passed!' );

			}
```
</details>


---