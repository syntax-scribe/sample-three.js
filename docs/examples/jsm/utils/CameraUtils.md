[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CameraUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 19 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/utils/CameraUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `MathUtils` | `three` |
| `Quaternion` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_va` | `any` | let/var | `new Vector3()` | ✗ |
| `_vb` | `any` | let/var | `new Vector3()` | ✗ |
| `_vc` | `any` | let/var | `new Vector3()` | ✗ |
| `_vr` | `any` | let/var | `new Vector3()` | ✗ |
| `_vu` | `any` | let/var | `new Vector3()` | ✗ |
| `_vn` | `any` | let/var | `new Vector3()` | ✗ |
| `_vec` | `any` | let/var | `new Vector3()` | ✗ |
| `_quat` | `any` | let/var | `new Quaternion()` | ✗ |
| `pa` | `Vector3` | let/var | `bottomLeftCorner` | ✗ |
| `pb` | `Vector3` | let/var | `bottomRightCorner` | ✗ |
| `pc` | `Vector3` | let/var | `topLeftCorner` | ✗ |
| `pe` | `any` | let/var | `camera.position` | ✗ |
| `n` | `any` | let/var | `camera.near` | ✗ |
| `f` | `any` | let/var | `camera.far` | ✗ |
| `d` | `number` | let/var | `- _va.dot( _vn )` | ✗ |
| `l` | `number` | let/var | `_vr.dot( _va ) * n / d` | ✗ |
| `r` | `number` | let/var | `_vr.dot( _vb ) * n / d` | ✗ |
| `b` | `number` | let/var | `_vu.dot( _va ) * n / d` | ✗ |
| `t` | `number` | let/var | `_vu.dot( _vc ) * n / d` | ✗ |


---

## Functions

### `frameCorners(camera: PerspectiveCamera, bottomLeftCorner: Vector3, bottomRightCorner: Vector3, topLeftCorner: Vector3, estimateViewFrustum: boolean): void`

**JSDoc:**
```typescript
/**
 * Set projection matrix and the orientation of a perspective camera
 * to exactly frame the corners of an arbitrary rectangle.
 * NOTE: This function ignores the standard parameters;
 * do not call `updateProjectionMatrix()` after this.
 *
 * @param {PerspectiveCamera} camera - The camera.
 * @param {Vector3} bottomLeftCorner - The bottom-left corner point.
 * @param {Vector3} bottomRightCorner - The bottom-right corner point.
 * @param {Vector3} topLeftCorner - The top-left corner point.
 * @param {boolean} [estimateViewFrustum=false] - If set to `true`, the function tries to estimate the camera's FOV.
 */
```

**Parameters:**

- **`camera`** `PerspectiveCamera`
- **`bottomLeftCorner`** `Vector3`
- **`bottomRightCorner`** `Vector3`
- **`topLeftCorner`** `Vector3`
- **`estimateViewFrustum`** `boolean`

**Returns:** `void`

**Calls:**

- `_vr.copy( pb ).sub( pa ).normalize`
- `_vu.copy( pc ).sub( pa ).normalize`
- `_vn.crossVectors( _vr, _vu ).normalize`
- `_va.copy( pa ).sub`
- `_vb.copy( pb ).sub`
- `_vc.copy( pc ).sub`
- `_va.dot`
- `_vr.dot`
- `_vu.dot`
- `_quat.setFromUnitVectors`
- `_vec.set`
- `camera.quaternion.setFromUnitVectors( _vec.set( 0, 0, 1 ).applyQuaternion( _quat ), _vn ).multiply`
- `camera.projectionMatrix.set`
- `camera.projectionMatrixInverse.copy( camera.projectionMatrix ).invert`
- `Math.min`
- `Math.atan`
- `_vec.copy( pb ).sub( pa ).length`
- `_vec.copy( pc ).sub( pa ).length`
- `_va.length`

**Internal Comments:**
```
// Set the camera rotation to match the focal plane to the corners' plane (x4)
// Set the off-axis projection matrix to match the corners (x5)
// FoV estimation to fix frustum culling
// Set fieldOfView to a conservative estimate (x4)
// to make frustum tall/wide enough to encompass it (x4)
```

<details><summary>Code</summary>

```typescript
function frameCorners( camera, bottomLeftCorner, bottomRightCorner, topLeftCorner, estimateViewFrustum = false ) {

	const pa = bottomLeftCorner, pb = bottomRightCorner, pc = topLeftCorner;
	const pe = camera.position; // eye position
	const n = camera.near; // distance of near clipping plane
	const f = camera.far; //distance of far clipping plane

	_vr.copy( pb ).sub( pa ).normalize();
	_vu.copy( pc ).sub( pa ).normalize();
	_vn.crossVectors( _vr, _vu ).normalize();

	_va.copy( pa ).sub( pe ); // from pe to pa
	_vb.copy( pb ).sub( pe ); // from pe to pb
	_vc.copy( pc ).sub( pe ); // from pe to pc

	const d = - _va.dot( _vn );	// distance from eye to screen
	const l = _vr.dot( _va ) * n / d; // distance to left screen edge
	const r = _vr.dot( _vb ) * n / d; // distance to right screen edge
	const b = _vu.dot( _va ) * n / d; // distance to bottom screen edge
	const t = _vu.dot( _vc ) * n / d; // distance to top screen edge

	// Set the camera rotation to match the focal plane to the corners' plane
	_quat.setFromUnitVectors( _vec.set( 0, 1, 0 ), _vu );
	camera.quaternion.setFromUnitVectors( _vec.set( 0, 0, 1 ).applyQuaternion( _quat ), _vn ).multiply( _quat );

	// Set the off-axis projection matrix to match the corners
	camera.projectionMatrix.set( 2.0 * n / ( r - l ), 0.0,
		( r + l ) / ( r - l ), 0.0, 0.0,
		2.0 * n / ( t - b ),
		( t + b ) / ( t - b ), 0.0, 0.0, 0.0,
		( f + n ) / ( n - f ),
		2.0 * f * n / ( n - f ), 0.0, 0.0, - 1.0, 0.0 );
	camera.projectionMatrixInverse.copy( camera.projectionMatrix ).invert();

	// FoV estimation to fix frustum culling
	if ( estimateViewFrustum ) {

		// Set fieldOfView to a conservative estimate
		// to make frustum tall/wide enough to encompass it
		camera.fov =
			MathUtils.RAD2DEG / Math.min( 1.0, camera.aspect ) *
			Math.atan( ( _vec.copy( pb ).sub( pa ).length() +
							( _vec.copy( pc ).sub( pa ).length() ) ) / _va.length() );

	}

}
```
</details>


---