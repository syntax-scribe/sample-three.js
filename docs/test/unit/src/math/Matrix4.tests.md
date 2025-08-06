[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Matrix4.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 50 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/math/Matrix4.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Matrix3` | `../../../../src/math/Matrix3.js` |
| `Matrix4` | `../../../../src/math/Matrix4.js` |
| `Vector3` | `../../../../src/math/Vector3.js` |
| `Euler` | `../../../../src/math/Euler.js` |
| `Quaternion` | `../../../../src/math/Quaternion.js` |
| `eps` | `../../utils/math-constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `diff` | `number` | let/var | `Math.abs( a.x - b.x ) + Math.abs( a.y - b.y ) + Math.abs( a.z - b.z )` | ✗ |
| `a` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `c` | `Matrix4` | let/var | `new Matrix4( 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15 )` | ✗ |
| `a` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `b` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `a` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `b` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `identityBasis` | `Vector3[]` | let/var | `[ new Vector3( 1, 0, 0 ), new Vector3( 0, 1, 0 ), new Vector3( 0, 0, 1 ) ]` | ✗ |
| `identity` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `testBases` | `Vector3[][]` | let/var | `[[ new Vector3( 0, 1, 0 ), new Vector3( - 1, 0, 0 ), new Vector3( 0, 0, 1 ) ]]` | ✗ |
| `testBasis` | `Vector3[]` | let/var | `testBases[ i ]` | ✗ |
| `outBasis` | `Vector3[]` | let/var | `[ new Vector3(), new Vector3(), new Vector3() ]` | ✗ |
| `testValues` | `Euler[]` | let/var | `[ new Euler( 0, 0, 0, 'XYZ' ), new Euler( 1, 0, 0, 'XYZ' ), new Euler( 0, 1, ...` | ✗ |
| `v` | `Euler` | let/var | `testValues[ i ]` | ✗ |
| `a` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `eye` | `Vector3` | let/var | `new Vector3( 0, 0, 0 )` | ✗ |
| `target` | `Vector3` | let/var | `new Vector3( 0, 1, - 1 )` | ✗ |
| `up` | `Vector3` | let/var | `new Vector3( 0, 1, 0 )` | ✗ |
| `ans` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `a` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `a` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( - 1, - 2, - 3 )` | ✗ |
| `identity` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `a` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `testMatrices` | `Matrix4[]` | let/var | `[ new Matrix4().makeRotationX( 0.3 ), new Matrix4().makeRotationX( - 0.3 ), n...` | ✗ |
| `m` | `Matrix4` | let/var | `testMatrices[ i ]` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( 2, 3, 4 )` | ✗ |
| `a` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3( 2, 3, 4 )` | ✗ |
| `a` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `b` | `number` | let/var | `Math.sqrt( 3 ) / 2` | ✗ |
| `a` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `b` | `number` | let/var | `Math.sqrt( 3 ) / 2` | ✗ |
| `a` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `b` | `number` | let/var | `Math.sqrt( 3 ) / 2` | ✗ |
| `a` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `a` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `tValues` | `Vector3[]` | let/var | `[ new Vector3(), new Vector3( 3, 0, 0 ), new Vector3( 0, 4, 0 ), new Vector3(...` | ✗ |
| `sValues` | `Vector3[]` | let/var | `[ new Vector3( 1, 1, 1 ), new Vector3( 2, 2, 2 ), new Vector3( 1, - 1, 1 ), n...` | ✗ |
| `rValues` | `Quaternion[]` | let/var | `[ new Quaternion(), new Quaternion().setFromEuler( new Euler( 1, 1, 0 ) ), ne...` | ✗ |
| `t` | `Vector3` | let/var | `tValues[ ti ]` | ✗ |
| `s` | `Vector3` | let/var | `sValues[ si ]` | ✗ |
| `r` | `Quaternion` | let/var | `rValues[ ri ]` | ✗ |
| `t2` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `r2` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `s2` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `noOffset` | `number[]` | let/var | `[ 1, 5, 9, 13, 2, 6, 10, 14, 3, 7, 11, 15, 4, 8, 12, 16 ]` | ✗ |
| `withOffset` | `number[]` | let/var | `[ undefined, 1, 5, 9, 13, 2, 6, 10, 14, 3, 7, 11, 15, 4, 8, 12, 16 ]` | ✗ |


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

### `eulerEquals(a: any, b: any, tolerance: any): boolean`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`tolerance`** `any`

**Returns:** `boolean`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
function eulerEquals( a, b, tolerance ) {

	tolerance = tolerance || 0.0001;
	const diff = Math.abs( a.x - b.x ) + Math.abs( a.y - b.y ) + Math.abs( a.z - b.z );
	return ( diff < tolerance );

}
```
</details>


---