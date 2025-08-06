[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `PerspectiveCamera.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/cameras/PerspectiveCamera.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `PerspectiveCamera` | `../../../../src/cameras/PerspectiveCamera.js` |
| `Matrix4` | `../../../../src/math/Matrix4.js` |
| `Camera` | `../../../../src/cameras/Camera.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `object` | `PerspectiveCamera` | let/var | `new PerspectiveCamera()` | ✗ |
| `object` | `PerspectiveCamera` | let/var | `new PerspectiveCamera()` | ✗ |
| `object` | `PerspectiveCamera` | let/var | `new PerspectiveCamera()` | ✗ |
| `object` | `PerspectiveCamera` | let/var | `new PerspectiveCamera()` | ✗ |
| `cam` | `PerspectiveCamera` | let/var | `new PerspectiveCamera( 75, 16 / 9, 0.1, 300.0 )` | ✗ |
| `m` | `Matrix4` | let/var | `cam.projectionMatrix` | ✗ |
| `near` | `1` | let/var | `1` | ✗ |
| `far` | `3` | let/var | `3` | ✗ |
| `aspect` | `number` | let/var | `16 / 9` | ✗ |
| `fov` | `90` | let/var | `90` | ✗ |
| `cam` | `PerspectiveCamera` | let/var | `new PerspectiveCamera( fov, aspect, near, far )` | ✗ |


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
function ( a, b, tolerance ) {

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


---