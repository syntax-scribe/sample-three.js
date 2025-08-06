[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Raycaster.tests.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 19 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`test/unit/src/core/Raycaster.tests.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Raycaster` | `../../../../src/core/Raycaster.js` |
| `Vector3` | `../../../../src/math/Vector3.js` |
| `Mesh` | `../../../../src/objects/Mesh.js` |
| `SphereGeometry` | `../../../../src/geometries/SphereGeometry.js` |
| `BufferGeometry` | `../../../../src/core/BufferGeometry.js` |
| `Line` | `../../../../src/objects/Line.js` |
| `Points` | `../../../../src/objects/Points.js` |
| `PerspectiveCamera` | `../../../../src/cameras/PerspectiveCamera.js` |
| `OrthographicCamera` | `../../../../src/cameras/OrthographicCamera.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `objects` | `any[]` | let/var | `[]` | ✗ |
| `object` | `Raycaster` | let/var | `new Raycaster()` | ✗ |
| `origin` | `Vector3` | let/var | `new Vector3( 0, 0, 0 )` | ✗ |
| `direction` | `Vector3` | let/var | `new Vector3( 0, 0, - 1 )` | ✗ |
| `a` | `Raycaster` | let/var | `new Raycaster( origin.clone(), direction.clone() )` | ✗ |
| `raycaster` | `Raycaster` | let/var | `new Raycaster()` | ✗ |
| `rayDirection` | `Vector3` | let/var | `raycaster.ray.direction` | ✗ |
| `camera` | `PerspectiveCamera` | let/var | `new PerspectiveCamera( 90, 1, 1, 1000 )` | ✗ |
| `step` | `0.1` | let/var | `0.1` | ✗ |
| `raycaster` | `Raycaster` | let/var | `new Raycaster()` | ✗ |
| `rayOrigin` | `Vector3` | let/var | `raycaster.ray.origin` | ✗ |
| `rayDirection` | `Vector3` | let/var | `raycaster.ray.direction` | ✗ |
| `camera` | `OrthographicCamera` | let/var | `new OrthographicCamera( - 1, 1, 1, - 1, 0, 1000 )` | ✗ |
| `expectedOrigin` | `Vector3` | let/var | `new Vector3( 0, 0, 0 )` | ✗ |
| `expectedDirection` | `Vector3` | let/var | `new Vector3( 0, 0, - 1 )` | ✗ |
| `points` | `Vector3[]` | let/var | `[ new Vector3( - 2, - 10, - 5 ), new Vector3( - 2, 10, - 5 ) ]` | ✗ |
| `line` | `Line` | let/var | `new Line( geometry, null )` | ✗ |
| `coordinates` | `Vector3[]` | let/var | `[ new Vector3( - 2, 0, - 5 ) ]` | ✗ |
| `points` | `Points` | let/var | `new Points( geometry, null )` | ✗ |


---

## Functions

### `checkRayDirectionAgainstReferenceVector(rayDirection: any, refVector: any, assert: any): void`

**Parameters:**

- **`rayDirection`** `any`
- **`refVector`** `any`
- **`assert`** `any`

**Returns:** `void`

**Calls:**

- `assert.ok`

<details><summary>Code</summary>

```typescript
function checkRayDirectionAgainstReferenceVector( rayDirection, refVector, assert ) {

	assert.ok( refVector.x - rayDirection.x <= Number.EPSILON && refVector.y - rayDirection.y <= Number.EPSILON && refVector.z - rayDirection.z <= Number.EPSILON, 'camera is pointing to' +
		' the same direction as expected' );

}
```
</details>

### `getRaycaster(): Raycaster`

**Returns:** `Raycaster`

<details><summary>Code</summary>

```typescript
function getRaycaster() {

	return new Raycaster(
		new Vector3( 0, 0, 0 ),
		new Vector3( 0, 0, - 1 ),
		1,
		100
	);

}
```
</details>

### `getObjectsToCheck(): Mesh[]`

**Returns:** `Mesh[]`

**Calls:**

- `getSphere`
- `sphere1.position.set`
- `objects.push`
- `sphere11.position.set`
- `sphere1.add`
- `sphere12.position.set`
- `sphere2.position.set`
- `objects[ i ].updateMatrixWorld`

<details><summary>Code</summary>

```typescript
function getObjectsToCheck() {

	const objects = [];

	const sphere1 = getSphere();
	sphere1.position.set( 0, 0, - 10 );
	sphere1.name = 1;
	objects.push( sphere1 );

	const sphere11 = getSphere();
	sphere11.position.set( 0, 0, 1 );
	sphere11.name = 11;
	sphere1.add( sphere11 );

	const sphere12 = getSphere();
	sphere12.position.set( 0, 0, - 1 );
	sphere12.name = 12;
	sphere1.add( sphere12 );

	const sphere2 = getSphere();
	sphere2.position.set( - 5, 0, - 5 );
	sphere2.name = 2;
	objects.push( sphere2 );

	for ( let i = 0; i < objects.length; i ++ ) {

		objects[ i ].updateMatrixWorld();

	}

	return objects;

}
```
</details>

### `getSphere(): Mesh`

**Returns:** `Mesh`

<details><summary>Code</summary>

```typescript
function getSphere() {

	return new Mesh( new SphereGeometry( 1, 100, 100 ) );

}
```
</details>


---