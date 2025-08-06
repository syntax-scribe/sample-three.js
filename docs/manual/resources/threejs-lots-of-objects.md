[⬅️ Back to Table of Contents](../../index.md)

# 📄 `threejs-lots-of-objects.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 20 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`manual/resources/threejs-lots-of-objects.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `threejsLessonUtils` | `./threejs-lesson-utils.js` |
| `GUI` | `../../examples/jsm/libs/lil-gui.module.min.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `root` | `any` | let/var | `new THREE.Object3D()` | ✗ |
| `size` | `3` | let/var | `3` | ✗ |
| `geometry` | `any` | let/var | `new THREE.BoxGeometry( size, size, size )` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshBasicMaterial( { color: 'red', } )` | ✗ |
| `cube` | `any` | let/var | `new THREE.Mesh( geometry, material )` | ✗ |
| `size` | `10` | let/var | `10` | ✗ |
| `divisions` | `10` | let/var | `10` | ✗ |
| `gridHelper` | `any` | let/var | `new THREE.GridHelper( size, divisions )` | ✗ |
| `size` | `10` | let/var | `10` | ✗ |
| `divisions` | `10` | let/var | `10` | ✗ |
| `gridHelper` | `any` | let/var | `new THREE.GridHelper( size, divisions )` | ✗ |
| `geometry` | `any` | let/var | `new THREE.BoxGeometry( 1, 1, 1 )` | ✗ |
| `lonHelper` | `any` | let/var | `new THREE.Object3D()` | ✗ |
| `latHelper` | `any` | let/var | `new THREE.Object3D()` | ✗ |
| `positionHelper` | `any` | let/var | `new THREE.Object3D()` | ✗ |
| `lonMesh` | `any` | let/var | `new THREE.Mesh( geometry, new THREE.MeshBasicMaterial( { color: 'green' } ) )` | ✗ |
| `latMesh` | `any` | let/var | `new THREE.Mesh( geometry, new THREE.MeshBasicMaterial( { color: 'blue' } ) )` | ✗ |
| `geometry` | `any` | let/var | `new THREE.SphereGeometry( 0.1, 24, 12 )` | ✗ |
| `posMesh` | `any` | let/var | `new THREE.Mesh( geometry, new THREE.MeshBasicMaterial( { color: 'red' } ) )` | ✗ |
| `gui` | `g` | let/var | `new GUI( { autoPlace: false } )` | ✗ |


---

## Functions

### `scaleCube(zOffset: any): { obj3D: any; update: (time: any) => void; }`

**Parameters:**

- **`zOffset`** `any`

**Returns:** `{ obj3D: any; update: (time: any) => void; }`

**Calls:**

- `geometry.applyMatrix4`
- `new THREE.Matrix4().makeTranslation`
- `root.add`
- `cube.add`
- `[[ 0, 0 ], [ 1, 0 ], [ 0, 1 ]].forEach`
- `THREE.MathUtils.lerp`
- `Math.sin`
- `cube.scale.set`

<details><summary>Code</summary>

```typescript
function scaleCube( zOffset ) {

		const root = new THREE.Object3D();

		const size = 3;
		const geometry = new THREE.BoxGeometry( size, size, size );
		geometry.applyMatrix4( new THREE.Matrix4().makeTranslation( 0, 0, zOffset * size ) );
		const material = new THREE.MeshBasicMaterial( {
			color: 'red',
		} );
		const cube = new THREE.Mesh( geometry, material );
		root.add( cube );
		cube.add( new THREE.LineSegments(
			new THREE.EdgesGeometry( geometry ),
			new THREE.LineBasicMaterial( { color: 'white' } ) ) );

		[[ 0, 0 ], [ 1, 0 ], [ 0, 1 ]].forEach( ( rot ) => {

			const size = 10;
			const divisions = 10;
			const gridHelper = new THREE.GridHelper( size, divisions );
			root.add( gridHelper );
			gridHelper.rotation.x = rot[ 0 ] * Math.PI * .5;
			gridHelper.rotation.z = rot[ 1 ] * Math.PI * .5;

		} );

		return {
			obj3D: root,
			update: ( time ) => {

				const s = THREE.MathUtils.lerp( 0.5, 2, Math.sin( time ) * .5 + .5 );
				cube.scale.set( s, s, s );

			},
		};

	}
```
</details>

### `update(time: any): void`

**Parameters:**

- **`time`** `any`

**Returns:** `void`

**Calls:**

- `THREE.MathUtils.lerp`
- `Math.sin`
- `cube.scale.set`

<details><summary>Code</summary>

```typescript
( time ) => {

				const s = THREE.MathUtils.lerp( 0.5, 2, Math.sin( time ) * .5 + .5 );
				cube.scale.set( s, s, s );

			}
```
</details>

### `update(time: any): void`

**Parameters:**

- **`time`** `any`

**Returns:** `void`

**Calls:**

- `THREE.MathUtils.lerp`
- `Math.sin`
- `cube.scale.set`

<details><summary>Code</summary>

```typescript
( time ) => {

				const s = THREE.MathUtils.lerp( 0.5, 2, Math.sin( time ) * .5 + .5 );
				cube.scale.set( s, s, s );

			}
```
</details>


---

## Classes

### `DegRadHelper`

<details><summary>Class Code</summary>

```ts
class DegRadHelper {

		constructor( obj, prop ) {

			this.obj = obj;
			this.prop = prop;

		}
		get value() {

			return THREE.MathUtils.radToDeg( this.obj[ this.prop ] );

		}
		set value( v ) {

			this.obj[ this.prop ] = THREE.MathUtils.degToRad( v );

		}

	}
```
</details>


---