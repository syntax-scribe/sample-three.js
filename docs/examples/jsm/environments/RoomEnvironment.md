[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RoomEnvironment.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 15 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/environments/RoomEnvironment.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BackSide` | `three` |
| `BoxGeometry` | `three` |
| `InstancedMesh` | `three` |
| `Mesh` | `three` |
| `MeshLambertMaterial` | `three` |
| `MeshStandardMaterial` | `three` |
| `PointLight` | `three` |
| `Scene` | `three` |
| `Object3D` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `geometry` | `any` | let/var | `new BoxGeometry()` | ✗ |
| `roomMaterial` | `any` | let/var | `new MeshStandardMaterial( { side: BackSide } )` | ✗ |
| `boxMaterial` | `any` | let/var | `new MeshStandardMaterial()` | ✗ |
| `mainLight` | `any` | let/var | `new PointLight( 0xffffff, 900, 28, 2 )` | ✗ |
| `room` | `any` | let/var | `new Mesh( geometry, roomMaterial )` | ✗ |
| `boxes` | `any` | let/var | `new InstancedMesh( geometry, boxMaterial, 6 )` | ✗ |
| `transform` | `any` | let/var | `new Object3D()` | ✗ |
| `light1` | `any` | let/var | `new Mesh( geometry, createAreaLightMaterial( 50 ) )` | ✗ |
| `light2` | `any` | let/var | `new Mesh( geometry, createAreaLightMaterial( 50 ) )` | ✗ |
| `light3` | `any` | let/var | `new Mesh( geometry, createAreaLightMaterial( 17 ) )` | ✗ |
| `light4` | `any` | let/var | `new Mesh( geometry, createAreaLightMaterial( 43 ) )` | ✗ |
| `light5` | `any` | let/var | `new Mesh( geometry, createAreaLightMaterial( 20 ) )` | ✗ |
| `light6` | `any` | let/var | `new Mesh( geometry, createAreaLightMaterial( 100 ) )` | ✗ |
| `resources` | `Set<any>` | let/var | `new Set()` | ✗ |
| `material` | `any` | let/var | `new MeshLambertMaterial( { color: 0x000000, emissive: 0xffffff, emissiveInten...` | ✗ |


---

## Functions

### `RoomEnvironment.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees internal resources. This method should be called
	 * when the environment is no longer required.
	 */
```

**Returns:** `void`

**Calls:**

- `this.traverse`
- `resources.add`
- `resource.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		const resources = new Set();

		this.traverse( ( object ) => {

			if ( object.isMesh ) {

				resources.add( object.geometry );
				resources.add( object.material );

			}

		} );

		for ( const resource of resources ) {

			resource.dispose();

		}

	}
```
</details>

### `createAreaLightMaterial(intensity: any): any`

**Parameters:**

- **`intensity`** `any`

**Returns:** `any`

**Internal Comments:**
```
// create an emissive-only material. see #31348 (x2)
```

<details><summary>Code</summary>

```typescript
function createAreaLightMaterial( intensity ) {

	// create an emissive-only material. see #31348
	const material = new MeshLambertMaterial( {
		color: 0x000000,
		emissive: 0xffffff,
		emissiveIntensity: intensity
	} );

	return material;

}
```
</details>


---

## Classes

### `RoomEnvironment`

<details><summary>Class Code</summary>

```ts
class RoomEnvironment extends Scene {

	constructor() {

		super();

		const geometry = new BoxGeometry();
		geometry.deleteAttribute( 'uv' );

		const roomMaterial = new MeshStandardMaterial( { side: BackSide } );
		const boxMaterial = new MeshStandardMaterial();

		const mainLight = new PointLight( 0xffffff, 900, 28, 2 );
		mainLight.position.set( 0.418, 16.199, 0.300 );
		this.add( mainLight );

		const room = new Mesh( geometry, roomMaterial );
		room.position.set( - 0.757, 13.219, 0.717 );
		room.scale.set( 31.713, 28.305, 28.591 );
		this.add( room );

		const boxes = new InstancedMesh( geometry, boxMaterial, 6 );
		const transform = new Object3D();

		// box1
		transform.position.set( - 10.906, 2.009, 1.846 );
		transform.rotation.set( 0, - 0.195, 0 );
		transform.scale.set( 2.328, 7.905, 4.651 );
		transform.updateMatrix();
		boxes.setMatrixAt( 0, transform.matrix );

		// box2
		transform.position.set( - 5.607, - 0.754, - 0.758 );
		transform.rotation.set( 0, 0.994, 0 );
		transform.scale.set( 1.970, 1.534, 3.955 );
		transform.updateMatrix();
		boxes.setMatrixAt( 1, transform.matrix );

		// box3
		transform.position.set( 6.167, 0.857, 7.803 );
		transform.rotation.set( 0, 0.561, 0 );
		transform.scale.set( 3.927, 6.285, 3.687 );
		transform.updateMatrix();
		boxes.setMatrixAt( 2, transform.matrix );

		// box4
		transform.position.set( - 2.017, 0.018, 6.124 );
		transform.rotation.set( 0, 0.333, 0 );
		transform.scale.set( 2.002, 4.566, 2.064 );
		transform.updateMatrix();
		boxes.setMatrixAt( 3, transform.matrix );

		// box5
		transform.position.set( 2.291, - 0.756, - 2.621 );
		transform.rotation.set( 0, - 0.286, 0 );
		transform.scale.set( 1.546, 1.552, 1.496 );
		transform.updateMatrix();
		boxes.setMatrixAt( 4, transform.matrix );

		// box6
		transform.position.set( - 2.193, - 0.369, - 5.547 );
		transform.rotation.set( 0, 0.516, 0 );
		transform.scale.set( 3.875, 3.487, 2.986 );
		transform.updateMatrix();
		boxes.setMatrixAt( 5, transform.matrix );

		this.add( boxes );


		// -x right
		const light1 = new Mesh( geometry, createAreaLightMaterial( 50 ) );
		light1.position.set( - 16.116, 14.37, 8.208 );
		light1.scale.set( 0.1, 2.428, 2.739 );
		this.add( light1 );

		// -x left
		const light2 = new Mesh( geometry, createAreaLightMaterial( 50 ) );
		light2.position.set( - 16.109, 18.021, - 8.207 );
		light2.scale.set( 0.1, 2.425, 2.751 );
		this.add( light2 );

		// +x
		const light3 = new Mesh( geometry, createAreaLightMaterial( 17 ) );
		light3.position.set( 14.904, 12.198, - 1.832 );
		light3.scale.set( 0.15, 4.265, 6.331 );
		this.add( light3 );

		// +z
		const light4 = new Mesh( geometry, createAreaLightMaterial( 43 ) );
		light4.position.set( - 0.462, 8.89, 14.520 );
		light4.scale.set( 4.38, 5.441, 0.088 );
		this.add( light4 );

		// -z
		const light5 = new Mesh( geometry, createAreaLightMaterial( 20 ) );
		light5.position.set( 3.235, 11.486, - 12.541 );
		light5.scale.set( 2.5, 2.0, 0.1 );
		this.add( light5 );

		// +y
		const light6 = new Mesh( geometry, createAreaLightMaterial( 100 ) );
		light6.position.set( 0.0, 20.0, 0.0 );
		light6.scale.set( 1.0, 0.1, 1.0 );
		this.add( light6 );

	}

	/**
	 * Frees internal resources. This method should be called
	 * when the environment is no longer required.
	 */
	dispose() {

		const resources = new Set();

		this.traverse( ( object ) => {

			if ( object.isMesh ) {

				resources.add( object.geometry );
				resources.add( object.material );

			}

		} );

		for ( const resource of resources ) {

			resource.dispose();

		}

	}

}
```
</details>

#### Methods

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		const resources = new Set();

		this.traverse( ( object ) => {

			if ( object.isMesh ) {

				resources.add( object.geometry );
				resources.add( object.material );

			}

		} );

		for ( const resource of resources ) {

			resource.dispose();

		}

	}
```
</details>


---