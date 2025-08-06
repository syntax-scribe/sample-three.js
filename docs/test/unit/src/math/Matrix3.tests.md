[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Matrix3.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 28 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/math/Matrix3.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Matrix3` | `../../../../src/math/Matrix3.js` |
| `Matrix4` | `../../../../src/math/Matrix4.js` |
| `Vector2` | `../../../../src/math/Vector2.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `result` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `re` | `number[]` | let/var | `result.elements` | ✗ |
| `me` | `any` | let/var | `m3.elements` | ✗ |
| `a` | `Matrix3` | let/var | `new Matrix3()` | ✗ |
| `c` | `Matrix3` | let/var | `new Matrix3( 0, 1, 2, 3, 4, 5, 6, 7, 8 )` | ✗ |
| `a` | `Matrix3` | let/var | `new Matrix3()` | ✗ |
| `b` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `b` | `Matrix3` | let/var | `new Matrix3()` | ✗ |
| `a` | `Matrix3` | let/var | `new Matrix3()` | ✗ |
| `b` | `Matrix3` | let/var | `new Matrix3()` | ✗ |
| `expectedMultiply` | `number[]` | let/var | `[ 446, 1343, 2491, 486, 1457, 2701, 520, 1569, 2925 ]` | ✗ |
| `expectedPremultiply` | `number[]` | let/var | `[ 904, 1182, 1556, 1131, 1489, 1967, 1399, 1845, 2435 ]` | ✗ |
| `ans` | `Matrix3` | let/var | `new Matrix3()` | ✗ |
| `a` | `Matrix3` | let/var | `new Matrix3()` | ✗ |
| `identity4` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `b` | `Matrix3` | let/var | `new Matrix3()` | ✗ |
| `testMatrices` | `Matrix4[]` | let/var | `[ new Matrix4().makeRotationX( 0.3 ), new Matrix4().makeRotationX( - 0.3 ), n...` | ✗ |
| `m` | `Matrix4` | let/var | `testMatrices[ i ]` | ✗ |
| `a` | `Matrix3` | let/var | `new Matrix3()` | ✗ |
| `a` | `Matrix3` | let/var | `new Matrix3()` | ✗ |
| `b` | `any[]` | let/var | `[]` | ✗ |
| `b` | `Matrix3` | let/var | `new Matrix3()` | ✗ |
| `params` | `{ centerX: number; centerY: number; o...` | let/var | `{ centerX: 0.5, centerY: 0.5, offsetX: 0, offsetY: 0, repeatX: 0.25, repeatY:...` | ✗ |
| `a` | `Matrix3` | let/var | `new Matrix3()` | ✗ |
| `b` | `Vector2` | let/var | `new Vector2( 1, 2 )` | ✗ |
| `b` | `Matrix3` | let/var | `new Matrix3()` | ✗ |
| `noOffset` | `number[]` | let/var | `[ 1, 4, 7, 2, 5, 8, 3, 6, 9 ]` | ✗ |
| `withOffset` | `number[]` | let/var | `[ undefined, 1, 4, 7, 2, 5, 8, 3, 6, 9 ]` | ✗ |


---

## Functions

### `matrixEquals3(b: any, a: any, tolerance: any): boolean`

**Parameters:**

- **`b`** `any`
- **`a`** `any`
- **`tolerance`** `any`

**Returns:** `boolean`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
function matrixEquals3( b, a, tolerance ) {

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

### `toMatrix4(m3: any): Matrix4`

**Parameters:**

- **`m3`** `any`

**Returns:** `Matrix4`

<details><summary>Code</summary>

```typescript
function toMatrix4( m3 ) {

	const result = new Matrix4();
	const re = result.elements;
	const me = m3.elements;
	re[ 0 ] = me[ 0 ];
	re[ 1 ] = me[ 1 ];
	re[ 2 ] = me[ 2 ];
	re[ 4 ] = me[ 3 ];
	re[ 5 ] = me[ 4 ];
	re[ 6 ] = me[ 5 ];
	re[ 8 ] = me[ 6 ];
	re[ 9 ] = me[ 7 ];
	re[ 10 ] = me[ 8 ];

	return result;

}
```
</details>


---