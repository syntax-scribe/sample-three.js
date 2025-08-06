[⬅️ Back to Table of Contents](../../index.md)

# 📄 `threejs-cameras.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 21 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/resources/threejs-cameras.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `threejsLessonUtils` | `./threejs-lesson-utils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `material` | `any` | let/var | `new THREE.MeshPhongMaterial( { color } )` | ✗ |
| `width` | `8` | let/var | `8` | ✗ |
| `height` | `8` | let/var | `8` | ✗ |
| `depth` | `8` | let/var | `8` | ✗ |
| `radius` | `6` | let/var | `6` | ✗ |
| `height` | `8` | let/var | `8` | ✗ |
| `segments` | `24` | let/var | `24` | ✗ |
| `radiusTop` | `4` | let/var | `4` | ✗ |
| `radiusBottom` | `4` | let/var | `4` | ✗ |
| `height` | `8` | let/var | `8` | ✗ |
| `radialSegments` | `24` | let/var | `24` | ✗ |
| `radius` | `5` | let/var | `5` | ✗ |
| `widthSegments` | `24` | let/var | `24` | ✗ |
| `heightSegments` | `16` | let/var | `16` | ✗ |
| `width` | `8` | let/var | `8` | ✗ |
| `height` | `8` | let/var | `8` | ✗ |
| `depth` | `8` | let/var | `8` | ✗ |
| `geometry` | `any` | let/var | `new THREE.BoxGeometry( width, height, depth )` | ✗ |
| `perspMat` | `any` | let/var | `new THREE.Matrix4()` | ✗ |
| `inMat` | `any` | let/var | `new THREE.Matrix4()` | ✗ |
| `mat` | `any` | let/var | `new THREE.Matrix4()` | ✗ |


---

## Functions

### `addShape(color: any, geometry: any): any`

**Parameters:**

- **`color`** `any`
- **`geometry`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function addShape( color, geometry ) {

		const material = new THREE.MeshPhongMaterial( { color } );
		return new THREE.Mesh( geometry, material );

	}
```
</details>


---