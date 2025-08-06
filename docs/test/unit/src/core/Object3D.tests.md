[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Object3D.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 📦 Imports | 11 |
| 📊 Variables & Constants | 112 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/core/Object3D.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Object3D` | `../../../../src/core/Object3D.js` |
| `Vector3` | `../../../../src/math/Vector3.js` |
| `Euler` | `../../../../src/math/Euler.js` |
| `Quaternion` | `../../../../src/math/Quaternion.js` |
| `Matrix4` | `../../../../src/math/Matrix4.js` |
| `x` | `../../utils/math-constants.js` |
| `y` | `../../utils/math-constants.js` |
| `z` | `../../utils/math-constants.js` |
| `w` | `../../utils/math-constants.js` |
| `eps` | `../../utils/math-constants.js` |
| `EventDispatcher` | `../../../../src/core/EventDispatcher.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `RadToDeg` | `number` | let/var | `180 / Math.PI` | ✗ |
| `object` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `object` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `object` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `v` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `object` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `object2` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `currentDefaultMatrixAutoUpdate` | `boolean` | let/var | `Object3D.DEFAULT_MATRIX_AUTO_UPDATE` | ✗ |
| `object` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `object2` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `object` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `object2` | `{}` | let/var | `{}` | ✗ |
| `a` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `m` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `expectedPos` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `expectedQuat` | `Quaternion` | let/var | `new Quaternion( 0.5 * Math.sqrt( 2 ), 0, 0, 0.5 * Math.sqrt( 2 ) )` | ✗ |
| `a` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `sqrt` | `number` | let/var | `0.5 * Math.sqrt( 2 )` | ✗ |
| `quat` | `Quaternion` | let/var | `new Quaternion( 0, sqrt, 0, sqrt )` | ✗ |
| `expected` | `Quaternion` | let/var | `new Quaternion( sqrt / 2, sqrt / 2, 0, 0 )` | ✗ |
| `a` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `axis` | `Vector3` | let/var | `new Vector3( 0, 1, 0 )` | ✗ |
| `angle` | `number` | let/var | `Math.PI` | ✗ |
| `expected` | `Euler` | let/var | `new Euler( - Math.PI, 0, - Math.PI )` | ✗ |
| `euler` | `Euler` | let/var | `new Euler()` | ✗ |
| `a` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `rotation` | `Euler` | let/var | `new Euler( ( 45 / RadToDeg ), 0, Math.PI )` | ✗ |
| `euler` | `Euler` | let/var | `new Euler()` | ✗ |
| `a` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `m` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `eye` | `Vector3` | let/var | `new Vector3( 0, 0, 0 )` | ✗ |
| `target` | `Vector3` | let/var | `new Vector3( 0, 1, - 1 )` | ✗ |
| `up` | `Vector3` | let/var | `new Vector3( 0, 1, 0 )` | ✗ |
| `euler` | `Euler` | let/var | `new Euler()` | ✗ |
| `a` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `euler` | `Euler` | let/var | `new Euler()` | ✗ |
| `obj` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `angleInRad` | `1.562` | let/var | `1.562` | ✗ |
| `obj` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `angleInRad` | `-0.346` | let/var | `- 0.346` | ✗ |
| `obj` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `angleInRad` | `1` | let/var | `1` | ✗ |
| `obj` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `obj` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `obj` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `obj` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `v` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `expectedPosition` | `Vector3` | let/var | `new Vector3( 5, - 1, - 4 )` | ✗ |
| `parent` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `child` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `v` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `expectedPosition` | `Vector3` | let/var | `new Vector3( - 1, 0.5, - 1 )` | ✗ |
| `parent` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `child` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `obj` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `a` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `child1` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `child2` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `object` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `oldParent` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `newParent` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `expectedMatrixWorld` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `parent` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `childName` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `childId` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `childNothing` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `parent` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `childName` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `childNothing` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `childName2` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `childName3` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `a` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `b` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `expectedSingle` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `expectedParent` | `Vector3` | let/var | `new Vector3( x, y, 0 )` | ✗ |
| `expectedChild` | `Vector3` | let/var | `new Vector3( x, y, 7 )` | ✗ |
| `position` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `expected` | `Vector3` | let/var | `new Vector3( x, y, z )` | ✗ |
| `a` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `expected` | `Vector3` | let/var | `new Vector3( 0, - 0.5 * Math.sqrt( 2 ), 0.5 * Math.sqrt( 2 ) )` | ✗ |
| `direction` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `b` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `c` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `d` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `a` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `b` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `c` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `d` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `names` | `any[]` | let/var | `[]` | ✗ |
| `expectedNormal` | `string[]` | let/var | `[ 'parent', 'child', 'childchild 1', 'childchild 2' ]` | ✗ |
| `expectedVisible` | `string[]` | let/var | `[ 'parent', 'child', 'childchild 2' ]` | ✗ |
| `expectedAncestors` | `string[]` | let/var | `[ 'child', 'parent' ]` | ✗ |
| `a` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `parent` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `child` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `object` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `parent` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `child` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `m` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `v` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `child` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `childChild` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `gold` | `{ metadata: { version: number; type: ...` | let/var | `{ 'metadata': { 'version': 4.7, 'type': 'Object', 'generator': 'Object3D.toJS...` | ✗ |
| `a` | `any` | let/var | `*not shown*` | ✗ |
| `b` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `a` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `b` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `child` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `childChild` | `Object3D` | let/var | `new Object3D()` | ✗ |


---

## Functions

### `matrixEquals4(a: any, b: any): boolean`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `boolean`

**Calls:**

- `Math.abs`

<details><summary>Code</summary>

```typescript
( a, b ) => {

	for ( let i = 0; i < 16; i ++ ) {

		if ( Math.abs( a.elements[ i ] - b.elements[ i ] ) >= eps ) {

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
function ( a, b, tolerance ) {

			tolerance = tolerance || 0.0001;

			if ( a.order != b.order ) {

				return false;

			}

			return (
				Math.abs( a.x - b.x ) <= tolerance &&
				Math.abs( a.y - b.y ) <= tolerance &&
				Math.abs( a.z - b.z ) <= tolerance
			);

		}
```
</details>


---