[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Euler.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 33 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/math/Euler.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Euler` | `../../../../src/math/Euler.js` |
| `Matrix4` | `../../../../src/math/Matrix4.js` |
| `Quaternion` | `../../../../src/math/Quaternion.js` |
| `Vector3` | `../../../../src/math/Vector3.js` |
| `x` | `../../utils/math-constants.js` |
| `y` | `../../utils/math-constants.js` |
| `z` | `../../utils/math-constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `eulerZero` | `Euler` | let/var | `new Euler( 0, 0, 0, 'XYZ' )` | ✗ |
| `eulerAxyz` | `Euler` | let/var | `new Euler( 1, 0, 0, 'XYZ' )` | ✗ |
| `eulerAzyx` | `Euler` | let/var | `new Euler( 0, 1, 0, 'ZYX' )` | ✗ |
| `diff` | `number` | let/var | `Math.abs( a.x - b.x ) + Math.abs( a.y - b.y ) + Math.abs( a.z - b.z ) + Math....` | ✗ |
| `a` | `Euler` | let/var | `new Euler()` | ✗ |
| `a` | `Euler` | let/var | `new Euler()` | ✗ |
| `b` | `boolean` | let/var | `false` | ✗ |
| `a` | `Euler` | let/var | `new Euler()` | ✗ |
| `b` | `boolean` | let/var | `false` | ✗ |
| `a` | `Euler` | let/var | `new Euler()` | ✗ |
| `b` | `boolean` | let/var | `false` | ✗ |
| `a` | `Euler` | let/var | `new Euler()` | ✗ |
| `b` | `boolean` | let/var | `false` | ✗ |
| `a` | `Euler` | let/var | `new Euler()` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `testValues` | `Euler[]` | let/var | `[ eulerZero, eulerAxyz, eulerAzyx ]` | ✗ |
| `v` | `Euler` | let/var | `testValues[ i ]` | ✗ |
| `testValues` | `Euler[]` | let/var | `[ eulerZero, eulerAxyz, eulerAzyx ]` | ✗ |
| `v` | `Euler` | let/var | `testValues[ i ]` | ✗ |
| `testValues` | `Euler[]` | let/var | `[ eulerZero, eulerAxyz, eulerAzyx ]` | ✗ |
| `v` | `Euler` | let/var | `testValues[ i ]` | ✗ |
| `a` | `Euler` | let/var | `new Euler()` | ✗ |
| `a` | `Euler` | let/var | `new Euler( 1, 2, 3, 'ZXY' )` | ✗ |
| `b` | `Euler` | let/var | `new Euler( 4, 5, 6, 'XZY' )` | ✗ |
| `order` | `"YXZ"` | let/var | `'YXZ'` | ✗ |
| `a` | `Euler` | let/var | `new Euler( x, y, z, order )` | ✗ |
| `a` | `Euler` | let/var | `new Euler()` | ✗ |
| `array` | `number[]` | let/var | `[ x, y, z ]` | ✗ |
| `a` | `Euler` | let/var | `new Euler( 11, 12, 13, 'XYZ' )` | ✗ |
| `b` | `boolean` | let/var | `false` | ✗ |
| `a` | `Euler` | let/var | `new Euler( 11, 12, 13, 'XYZ' )` | ✗ |
| `e` | `Euler` | let/var | `new Euler( 0.5, 0.75, 1, 'YZX' )` | ✗ |
| `array` | `(string \| number)[]` | let/var | `[ ...e ]` | ✗ |


---

## Functions

### `matrixEquals4(a: any, b: any, tolerance: any): boolean`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`tolerance`** `any`

**Returns:** `boolean`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
function matrixEquals4( a, b, tolerance ) {

	tolerance = tolerance || 0.0001;
	if ( a.elements.length != b.elements.length ) {

		return false;

	}

	for ( let i = 0, il = a.elements.length; i < il; i ++ ) {

		const delta = Math.abs( a.elements[ i ] - b.elements[ i ] );
		if ( delta > tolerance ) {

			return false;

		}

	}

	return true;

}
```
</details>

### `quatEquals(a: any, b: any, tolerance: any): boolean`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`tolerance`** `any`

**Returns:** `boolean`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
function quatEquals( a, b, tolerance ) {

	tolerance = tolerance || 0.0001;
	const diff = Math.abs( a.x - b.x ) + Math.abs( a.y - b.y ) + Math.abs( a.z - b.z ) + Math.abs( a.w - b.w );

	return ( diff < tolerance );

}
```
</details>

### `cbSucceed(): void`

**Returns:** `void`

**Calls:**

- `assert.ok`
- `assert.step`

<details><summary>Code</summary>

```typescript
function () {

				assert.ok( true );
				assert.step( 'onChange called' );

			}
```
</details>

### `cbFail(): void`

**Returns:** `void`

**Calls:**

- `assert.ok`

<details><summary>Code</summary>

```typescript
function () {

				assert.ok( false );

			}
```
</details>

### `cb(): void`

**Returns:** `void`

**Calls:**

- `assert.step`

<details><summary>Code</summary>

```typescript
function () {

				assert.step( 'onChange called' );

			}
```
</details>

### `f(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function () {

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