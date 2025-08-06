[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `DebugEnvironment.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/environments/DebugEnvironment.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BackSide` | `three` |
| `BoxGeometry` | `three` |
| `Mesh` | `three` |
| `MeshLambertMaterial` | `three` |
| `MeshStandardMaterial` | `three` |
| `PointLight` | `three` |
| `Scene` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `geometry` | `any` | let/var | `new BoxGeometry()` | ✗ |
| `roomMaterial` | `any` | let/var | `new MeshStandardMaterial( { metalness: 0, side: BackSide } )` | ✗ |
| `room` | `any` | let/var | `new Mesh( geometry, roomMaterial )` | ✗ |
| `mainLight` | `any` | let/var | `new PointLight( 0xffffff, 50, 0, 2 )` | ✗ |
| `material1` | `any` | let/var | `new MeshLambertMaterial( { color: 0xff0000, emissive: 0xffffff, emissiveInten...` | ✗ |
| `light1` | `any` | let/var | `new Mesh( geometry, material1 )` | ✗ |
| `material2` | `any` | let/var | `new MeshLambertMaterial( { color: 0x00ff00, emissive: 0xffffff, emissiveInten...` | ✗ |
| `light2` | `any` | let/var | `new Mesh( geometry, material2 )` | ✗ |
| `material3` | `any` | let/var | `new MeshLambertMaterial( { color: 0x0000ff, emissive: 0xffffff, emissiveInten...` | ✗ |
| `light3` | `any` | let/var | `new Mesh( geometry, material3 )` | ✗ |
| `resources` | `Set<any>` | let/var | `new Set()` | ✗ |


---

## Functions

### `DebugEnvironment.dispose(): void`

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


---

## Classes

### `DebugEnvironment`

<details><summary>Class Code</summary>

```ts
class DebugEnvironment extends Scene {

	/**
	 * Constructs a new debug environment.
	 */
	constructor() {

		super();

		const geometry = new BoxGeometry();
		geometry.deleteAttribute( 'uv' );
		const roomMaterial = new MeshStandardMaterial( { metalness: 0, side: BackSide } );
		const room = new Mesh( geometry, roomMaterial );
		room.scale.setScalar( 10 );
		this.add( room );

		const mainLight = new PointLight( 0xffffff, 50, 0, 2 );
		this.add( mainLight );

		const material1 = new MeshLambertMaterial( { color: 0xff0000, emissive: 0xffffff, emissiveIntensity: 10 } );

		const light1 = new Mesh( geometry, material1 );
		light1.position.set( - 5, 2, 0 );
		light1.scale.set( 0.1, 1, 1 );
		this.add( light1 );

		const material2 = new MeshLambertMaterial( { color: 0x00ff00, emissive: 0xffffff, emissiveIntensity: 10 } );

		const light2 = new Mesh( geometry, material2 );
		light2.position.set( 0, 5, 0 );
		light2.scale.set( 1, 0.1, 1 );
		this.add( light2 );

		const material3 = new MeshLambertMaterial( { color: 0x0000ff, emissive: 0xffffff, emissiveIntensity: 10 } );

		const light3 = new Mesh( geometry, material3 );
		light3.position.set( 2, 1, 5 );
		light3.scale.set( 1.5, 2, 0.1 );
		this.add( light3 );

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