[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Plane.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 12 |
| 📊 Variables & Constants | 45 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/math/Plane.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Plane` | `../../../../src/math/Plane.js` |
| `Vector3` | `../../../../src/math/Vector3.js` |
| `Line3` | `../../../../src/math/Line3.js` |
| `Sphere` | `../../../../src/math/Sphere.js` |
| `Box3` | `../../../../src/math/Box3.js` |
| `Matrix4` | `../../../../src/math/Matrix4.js` |
| `x` | `../../utils/math-constants.js` |
| `y` | `../../utils/math-constants.js` |
| `z` | `../../utils/math-constants.js` |
| `w` | `../../utils/math-constants.js` |
| `zero3` | `../../utils/math-constants.js` |
| `one3` | `../../utils/math-constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `a` | `Plane` | let/var | `new Plane()` | ✗ |
| `a` | `Plane` | let/var | `new Plane()` | ✗ |
| `b` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Plane` | let/var | `new Plane()` | ✗ |
| `a` | `Plane` | let/var | `new Plane()` | ✗ |
| `a` | `Plane` | let/var | `new Plane()` | ✗ |
| `v1` | `Vector3` | let/var | `new Vector3( 2.0, 0.5, 0.25 )` | ✗ |
| `v2` | `Vector3` | let/var | `new Vector3( 2.0, - 0.5, 1.25 )` | ✗ |
| `v3` | `Vector3` | let/var | `new Vector3( 2.0, - 3.5, 2.2 )` | ✗ |
| `normal` | `Vector3` | let/var | `new Vector3( 1, 0, 0 )` | ✗ |
| `constant` | `-2` | let/var | `- 2` | ✗ |
| `a` | `Plane` | let/var | `new Plane( new Vector3( 2.0, 0.5, 0.25 ) )` | ✗ |
| `a` | `Plane` | let/var | `new Plane( new Vector3( x, y, z ), w )` | ✗ |
| `a` | `Plane` | let/var | `new Plane( new Vector3( 2, 0, 0 ), 2 )` | ✗ |
| `a` | `Plane` | let/var | `new Plane( new Vector3( 2, 0, 0 ), - 2 )` | ✗ |
| `a` | `Plane` | let/var | `new Plane( new Vector3( 2, 0, 0 ), - 2 )` | ✗ |
| `point` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Plane` | let/var | `new Plane( new Vector3( 1, 0, 0 ), 0 )` | ✗ |
| `b` | `Sphere` | let/var | `new Sphere( new Vector3( 2, 0, 0 ), 1 )` | ✗ |
| `a` | `Plane` | let/var | `new Plane( new Vector3( 1, 0, 0 ), 0 )` | ✗ |
| `point` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Plane` | let/var | `new Plane( new Vector3( 1, 0, 0 ), 0 )` | ✗ |
| `point` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `l1` | `Line3` | let/var | `new Line3( new Vector3( - 10, 0, 0 ), new Vector3( 10, 0, 0 ) )` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `b` | `Plane` | let/var | `new Plane( new Vector3( 0, 1, 0 ), 1 )` | ✗ |
| `c` | `Plane` | let/var | `new Plane( new Vector3( 0, 1, 0 ), 1.25 )` | ✗ |
| `d` | `Plane` | let/var | `new Plane( new Vector3( 0, - 1, 0 ), 1.25 )` | ✗ |
| `e` | `Plane` | let/var | `new Plane( new Vector3( 0, 1, 0 ), 0.25 )` | ✗ |
| `f` | `Plane` | let/var | `new Plane( new Vector3( 0, 1, 0 ), - 0.25 )` | ✗ |
| `g` | `Plane` | let/var | `new Plane( new Vector3( 0, 1, 0 ), - 0.75 )` | ✗ |
| `h` | `Plane` | let/var | `new Plane( new Vector3( 0, 1, 0 ), - 1 )` | ✗ |
| `i` | `Plane` | let/var | `new Plane( new Vector3( 1, 1, 1 ).normalize(), - 1.732 )` | ✗ |
| `j` | `Plane` | let/var | `new Plane( new Vector3( 1, 1, 1 ).normalize(), - 1.733 )` | ✗ |
| `a` | `Sphere` | let/var | `new Sphere( zero3.clone(), 1 )` | ✗ |
| `b` | `Plane` | let/var | `new Plane( new Vector3( 0, 1, 0 ), 1 )` | ✗ |
| `c` | `Plane` | let/var | `new Plane( new Vector3( 0, 1, 0 ), 1.25 )` | ✗ |
| `d` | `Plane` | let/var | `new Plane( new Vector3( 0, - 1, 0 ), 1.25 )` | ✗ |
| `point` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Plane` | let/var | `new Plane( new Vector3( 1, 0, 0 ), 0 )` | ✗ |
| `a` | `Plane` | let/var | `new Plane( new Vector3( 1, 0, 0 ), 0 )` | ✗ |
| `m` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `a` | `Plane` | let/var | `new Plane( new Vector3( 1, 0, 0 ), 0 )` | ✗ |
| `b` | `Plane` | let/var | `new Plane( new Vector3( 1, 0, 0 ), 1 )` | ✗ |
| `c` | `Plane` | let/var | `new Plane( new Vector3( 0, 1, 0 ), 0 )` | ✗ |


---

## Functions

### `comparePlane(a: any, b: any, threshold: any): boolean`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`threshold`** `any`

**Returns:** `boolean`

**Calls:**

- `a.normal.distanceTo`
- `Math.abs`

<details><summary>Code</summary>

```typescript
function comparePlane( a, b, threshold ) {

	threshold = threshold || 0.0001;
	return ( a.normal.distanceTo( b.normal ) < threshold &&
	Math.abs( a.constant - b.constant ) < threshold );

}
```
</details>


---