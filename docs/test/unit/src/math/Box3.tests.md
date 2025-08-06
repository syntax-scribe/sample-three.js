[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Box3.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 15 |
| 📊 Variables & Constants | 99 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/math/Box3.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Box3` | `../../../../src/math/Box3.js` |
| `Sphere` | `../../../../src/math/Sphere.js` |
| `Triangle` | `../../../../src/math/Triangle.js` |
| `Plane` | `../../../../src/math/Plane.js` |
| `Vector3` | `../../../../src/math/Vector3.js` |
| `Matrix4` | `../../../../src/math/Matrix4.js` |
| `Mesh` | `../../../../src/objects/Mesh.js` |
| `BufferAttribute` | `../../../../src/core/BufferAttribute.js` |
| `BoxGeometry` | `../../../../src/geometries/BoxGeometry.js` |
| `SphereGeometry` | `../../../../src/geometries/SphereGeometry.js` |
| `negInf3` | `../../utils/math-constants.js` |
| `posInf3` | `../../utils/math-constants.js` |
| `zero3` | `../../utils/math-constants.js` |
| `one3` | `../../utils/math-constants.js` |
| `two3` | `../../utils/math-constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `a` | `Box3` | let/var | `new Box3()` | ✗ |
| `a` | `Box3` | let/var | `new Box3()` | ✗ |
| `b` | `Sphere` | let/var | `new Sphere()` | ✗ |
| `a` | `Box3` | let/var | `new Box3()` | ✗ |
| `a` | `Box3` | let/var | `new Box3()` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `bigger` | `BufferAttribute` | let/var | `new BufferAttribute( new Float32Array( [ - 2, - 2, - 2, 2, 2, 2, 1.5, 1.5, 1....` | ✗ |
| `smaller` | `BufferAttribute` | let/var | `new BufferAttribute( new Float32Array( [ - 0.5, - 0.5, - 0.5, 0.5, 0.5, 0.5, ...` | ✗ |
| `newMin` | `Vector3` | let/var | `new Vector3( - 2, - 2, - 2 )` | ✗ |
| `newMax` | `Vector3` | let/var | `new Vector3( 2, 2, 2 )` | ✗ |
| `a` | `Box3` | let/var | `new Box3()` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `centerA` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `sizeA` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `sizeB` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `newCenter` | `Vector3` | let/var | `one3` | ✗ |
| `newSize` | `Vector3` | let/var | `two3` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `object` | `Mesh` | let/var | `new Mesh( new BoxGeometry( 2, 2, 2 ) )` | ✗ |
| `child` | `Mesh` | let/var | `new Mesh( new BoxGeometry( 1, 1, 1 ) )` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `object` | `Mesh` | let/var | `new Mesh( new SphereGeometry( 1, 32, 32 ) )` | ✗ |
| `child` | `Mesh` | let/var | `new Mesh( new SphereGeometry( 2, 32, 32 ) )` | ✗ |
| `rotatedBox` | `Box3` | let/var | `new Box3( new Vector3( - 2 * Math.SQRT2, - 2 * Math.SQRT2, - 2 ), new Vector3...` | ✗ |
| `rotatedMinBox` | `Box3` | let/var | `new Box3( new Vector3( - 2, - 2, - 2 ), new Vector3( 2, 2, 2 ) )` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `a` | `Box3` | let/var | `new Box3()` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), zero3.clone() )` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), zero3.clone() )` | ✗ |
| `center` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), zero3.clone() )` | ✗ |
| `size` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), zero3.clone() )` | ✗ |
| `center` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `size` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), zero3.clone() )` | ✗ |
| `center` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `size` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), zero3.clone() )` | ✗ |
| `center` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `size` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `bigger` | `Mesh` | let/var | `new Mesh( new BoxGeometry( 2, 2, 2 ) )` | ✗ |
| `smaller` | `Mesh` | let/var | `new Mesh( new BoxGeometry( 0.5, 0.5, 0.5 ) )` | ✗ |
| `child` | `Mesh` | let/var | `new Mesh( new BoxGeometry( 1, 1, 1 ) )` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), zero3.clone() )` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), zero3.clone() )` | ✗ |
| `b` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `c` | `Box3` | let/var | `new Box3( one3.clone().negate(), one3.clone() )` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `b` | `Box3` | let/var | `new Box3( one3.clone().negate(), one3.clone() )` | ✗ |
| `parameter` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), zero3.clone() )` | ✗ |
| `b` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `c` | `Box3` | let/var | `new Box3( one3.clone().negate(), one3.clone() )` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `b` | `Sphere` | let/var | `new Sphere( zero3.clone(), 1 )` | ✗ |
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
| `a` | `Box3` | let/var | `new Box3( one3.clone(), two3.clone() )` | ✗ |
| `b` | `Triangle` | let/var | `new Triangle( new Vector3( 1.5, 1.5, 2.5 ), new Vector3( 2.5, 1.5, 1.5 ), new...` | ✗ |
| `c` | `Triangle` | let/var | `new Triangle( new Vector3( 1.5, 1.5, 3.5 ), new Vector3( 3.5, 1.5, 1.5 ), new...` | ✗ |
| `d` | `Triangle` | let/var | `new Triangle( new Vector3( 1.5, 1.75, 3 ), new Vector3( 3, 1.75, 1.5 ), new V...` | ✗ |
| `e` | `Triangle` | let/var | `new Triangle( new Vector3( 1.5, 1.8, 3 ), new Vector3( 3, 1.8, 1.5 ), new Vec...` | ✗ |
| `f` | `Triangle` | let/var | `new Triangle( new Vector3( 1.5, 2.5, 3 ), new Vector3( 3, 2.5, 1.5 ), new Vec...` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), zero3.clone() )` | ✗ |
| `b` | `Box3` | let/var | `new Box3( one3.clone().negate(), one3.clone() )` | ✗ |
| `point` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), zero3.clone() )` | ✗ |
| `b` | `Box3` | let/var | `new Box3( one3.clone().negate(), one3.clone() )` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), zero3.clone() )` | ✗ |
| `b` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `c` | `Box3` | let/var | `new Box3( one3.clone().negate(), one3.clone() )` | ✗ |
| `sphere` | `Sphere` | let/var | `new Sphere()` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), zero3.clone() )` | ✗ |
| `b` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `c` | `Box3` | let/var | `new Box3( one3.clone().negate(), one3.clone() )` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), zero3.clone() )` | ✗ |
| `b` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `c` | `Box3` | let/var | `new Box3( one3.clone().negate(), one3.clone() )` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), zero3.clone() )` | ✗ |
| `b` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `c` | `Box3` | let/var | `new Box3( one3.clone().negate(), one3.clone() )` | ✗ |
| `d` | `Box3` | let/var | `new Box3( one3.clone().negate(), zero3.clone() )` | ✗ |
| `t1` | `Vector3` | let/var | `new Vector3( 1, - 2, 1 )` | ✗ |
| `a` | `Box3` | let/var | `new Box3( zero3.clone(), zero3.clone() )` | ✗ |
| `b` | `Box3` | let/var | `new Box3( zero3.clone(), one3.clone() )` | ✗ |
| `c` | `Box3` | let/var | `new Box3( one3.clone().negate(), zero3.clone() )` | ✗ |
| `a` | `Box3` | let/var | `new Box3()` | ✗ |
| `b` | `Box3` | let/var | `new Box3()` | ✗ |


---

## Functions

### `compareBox(a: any, b: any, threshold: any): boolean`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`threshold`** `any`

**Returns:** `boolean`

**Calls:**

- `a.min.distanceTo`
- `a.max.distanceTo`

<details><summary>Code</summary>

```typescript
function compareBox( a, b, threshold ) {

	threshold = threshold || 0.0001;
	return ( a.min.distanceTo( b.min ) < threshold &&
	a.max.distanceTo( b.max ) < threshold );

}
```
</details>


---