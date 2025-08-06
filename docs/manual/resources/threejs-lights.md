[⬅️ Back to Table of Contents](../../index.md)

# 📄 `threejs-lights.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 26 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/resources/threejs-lights.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `OrbitControls` | `../../examples/jsm/controls/OrbitControls.js` |
| `threejsLessonUtils` | `./threejs-lesson-utils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `data` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( [ 0x88, 0x88, 0x88, 0xFF, 0xCC, 0xCC, 0xCC, 0xFF, 0xCC, 0xCC,...` | ✗ |
| `width` | `2` | let/var | `2` | ✗ |
| `height` | `2` | let/var | `2` | ✗ |
| `texture` | `any` | let/var | `new THREE.DataTexture( data, width, height )` | ✗ |
| `cubeSize` | `4` | let/var | `4` | ✗ |
| `cubeGeo` | `any` | let/var | `new THREE.BoxGeometry( cubeSize, cubeSize, cubeSize )` | ✗ |
| `cubeMat` | `any` | let/var | `new THREE.MeshPhongMaterial( { color: '#8AC' } )` | ✗ |
| `sphereRadius` | `3` | let/var | `3` | ✗ |
| `sphereWidthDivisions` | `32` | let/var | `32` | ✗ |
| `sphereHeightDivisions` | `16` | let/var | `16` | ✗ |
| `sphereGeo` | `any` | let/var | `new THREE.SphereGeometry( sphereRadius, sphereWidthDivisions, sphereHeightDiv...` | ✗ |
| `sphereMat` | `any` | let/var | `new THREE.MeshPhongMaterial( { color: '#CA8' } )` | ✗ |
| `planeSize` | `40` | let/var | `40` | ✗ |
| `planeGeo` | `any` | let/var | `new THREE.PlaneGeometry( planeSize, planeSize )` | ✗ |
| `planeMat` | `any` | let/var | `new THREE.MeshPhongMaterial( { map: makeCheckerTexture( planeSize ), side: TH...` | ✗ |
| `controls` | `OrbitControls` | let/var | `new OrbitControls( camera, elem )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( cubeGeo, cubeMat )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( sphereGeo, sphereMat )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( planeGeo, planeMat )` | ✗ |
| `light` | `any` | let/var | `new THREE.DirectionalLight( 0xFFFFFF, 1 )` | ✗ |
| `light` | `any` | let/var | `new THREE.AmbientLight( 0xFFFFFF, .6 )` | ✗ |
| `light` | `any` | let/var | `new THREE.DirectionalLight( 0xFFFFFF, 1 )` | ✗ |
| `skyColor` | `11657727` | let/var | `0xB1E1FF` | ✗ |
| `groundColor` | `12155424` | let/var | `0xB97A20` | ✗ |
| `intensity` | `0.6` | let/var | `.6` | ✗ |
| `light` | `any` | let/var | `new THREE.HemisphereLight( skyColor, groundColor, intensity )` | ✗ |


---

## Functions

### `makeCheckerTexture(repeats: any): any`

**Parameters:**

- **`repeats`** `any`

**Returns:** `any`

**Calls:**

- `texture.repeat.set`

<details><summary>Code</summary>

```typescript
function makeCheckerTexture( repeats ) {

		const data = new Uint8Array( [
			0x88, 0x88, 0x88, 0xFF, 0xCC, 0xCC, 0xCC, 0xFF,
			0xCC, 0xCC, 0xCC, 0xFF, 0x88, 0x88, 0x88, 0xFF
		] );
		const width = 2;
		const height = 2;
		const texture = new THREE.DataTexture( data, width, height );
		texture.needsUpdate = true;
		texture.wrapS = THREE.RepeatWrapping;
		texture.wrapT = THREE.RepeatWrapping;
		texture.repeat.set( repeats / 2, repeats / 2 );
		return texture;

	}
```
</details>


---