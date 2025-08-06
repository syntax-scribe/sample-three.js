[⬅️ Back to Table of Contents](../../index.md)

# 📄 `threejs-custom-buffergeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 12 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/resources/threejs-custom-buffergeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `threejsLessonUtils` | `./threejs-lesson-utils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `loader` | `any` | let/var | `new THREE.TextureLoader()` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshPhongMaterial( { color: 'hsl(300,50%,50%)', side: THREE.DoubleS...` | ✗ |
| `numSegments` | `24` | let/var | `24` | ✗ |
| `positions` | `any[]` | let/var | `[]` | ✗ |
| `uvs` | `any[]` | let/var | `[]` | ✗ |
| `u` | `number` | let/var | `s / numSegments` | ✗ |
| `a` | `number` | let/var | `u * Math.PI * 2` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `ndx` | `number` | let/var | `s * 2` | ✗ |
| `positionNumComponents` | `3` | let/var | `3` | ✗ |
| `uvNumComponents` | `2` | let/var | `2` | ✗ |
| `geometry` | `any` | let/var | `new THREE.BufferGeometry()` | ✗ |


---

## Functions

### `makeMesh(geometry: any): any`

**Parameters:**

- **`geometry`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function makeMesh( geometry ) {

		const material = new THREE.MeshPhongMaterial( {
			color: 'hsl(300,50%,50%)',
			side: THREE.DoubleSide,
			map: texture,
		} );
		return new THREE.Mesh( geometry, material );

	}
```
</details>


---