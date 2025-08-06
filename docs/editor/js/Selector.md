[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Selector.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`editor/js/Selector.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `mouse` | `any` | let/var | `new THREE.Vector2()` | ✗ |
| `raycaster` | `any` | let/var | `new THREE.Raycaster()` | ✗ |
| `signals` | `any` | let/var | `editor.signals` | ✗ |
| `object` | `any` | let/var | `intersects[ 0 ].object` | ✗ |
| `objects` | `any[]` | let/var | `[]` | ✗ |
| `uuid` | `any` | let/var | `null` | ✗ |


---

## Functions

### `Selector.getIntersects(raycaster: any): any`

**Parameters:**

- **`raycaster`** `any`

**Returns:** `any`

**Calls:**

- `this.editor.scene.traverseVisible`
- `objects.push`
- `this.editor.sceneHelpers.traverseVisible`
- `raycaster.intersectObjects`

<details><summary>Code</summary>

```typescript
getIntersects( raycaster ) {

		const objects = [];

		this.editor.scene.traverseVisible( function ( child ) {

			objects.push( child );

		} );

		this.editor.sceneHelpers.traverseVisible( function ( child ) {

			if ( child.name === 'picker' ) objects.push( child );

		} );

		return raycaster.intersectObjects( objects, false );

	}
```
</details>

### `Selector.getPointerIntersects(point: any, camera: any): any`

**Parameters:**

- **`point`** `any`
- **`camera`** `any`

**Returns:** `any`

**Calls:**

- `mouse.set`
- `raycaster.setFromCamera`
- `this.getIntersects`

<details><summary>Code</summary>

```typescript
getPointerIntersects( point, camera ) {

		mouse.set( ( point.x * 2 ) - 1, - ( point.y * 2 ) + 1 );

		raycaster.setFromCamera( mouse, camera );

		return this.getIntersects( raycaster );

	}
```
</details>

### `Selector.select(object: any): void`

**Parameters:**

- **`object`** `any`

**Returns:** `void`

**Calls:**

- `this.editor.config.setKey`
- `this.signals.objectSelected.dispatch`

<details><summary>Code</summary>

```typescript
select( object ) {

		if ( this.editor.selected === object ) return;

		let uuid = null;

		if ( object !== null ) {

			uuid = object.uuid;

		}

		this.editor.selected = object;
		this.editor.config.setKey( 'selected', uuid );

		this.signals.objectSelected.dispatch( object );

	}
```
</details>

### `Selector.deselect(): void`

**Returns:** `void`

**Calls:**

- `this.select`

<details><summary>Code</summary>

```typescript
deselect() {

		this.select( null );

	}
```
</details>


---

## Classes

### `Selector`

<details><summary>Class Code</summary>

```ts
class Selector {

	constructor( editor ) {

		const signals = editor.signals;

		this.editor = editor;
		this.signals = signals;

		// signals

		signals.intersectionsDetected.add( ( intersects ) => {

			if ( intersects.length > 0 ) {

				const object = intersects[ 0 ].object;

				if ( object.userData.object !== undefined ) {

					// helper

					this.select( object.userData.object );

				} else {

					this.select( object );

				}

			} else {

				this.select( null );

			}

		} );

	}

	getIntersects( raycaster ) {

		const objects = [];

		this.editor.scene.traverseVisible( function ( child ) {

			objects.push( child );

		} );

		this.editor.sceneHelpers.traverseVisible( function ( child ) {

			if ( child.name === 'picker' ) objects.push( child );

		} );

		return raycaster.intersectObjects( objects, false );

	}

	getPointerIntersects( point, camera ) {

		mouse.set( ( point.x * 2 ) - 1, - ( point.y * 2 ) + 1 );

		raycaster.setFromCamera( mouse, camera );

		return this.getIntersects( raycaster );

	}

	select( object ) {

		if ( this.editor.selected === object ) return;

		let uuid = null;

		if ( object !== null ) {

			uuid = object.uuid;

		}

		this.editor.selected = object;
		this.editor.config.setKey( 'selected', uuid );

		this.signals.objectSelected.dispatch( object );

	}

	deselect() {

		this.select( null );

	}

}
```
</details>

#### Methods

##### `getIntersects(raycaster: any): any`

<details><summary>Code</summary>

```ts
getIntersects( raycaster ) {

		const objects = [];

		this.editor.scene.traverseVisible( function ( child ) {

			objects.push( child );

		} );

		this.editor.sceneHelpers.traverseVisible( function ( child ) {

			if ( child.name === 'picker' ) objects.push( child );

		} );

		return raycaster.intersectObjects( objects, false );

	}
```
</details>

##### `getPointerIntersects(point: any, camera: any): any`

<details><summary>Code</summary>

```ts
getPointerIntersects( point, camera ) {

		mouse.set( ( point.x * 2 ) - 1, - ( point.y * 2 ) + 1 );

		raycaster.setFromCamera( mouse, camera );

		return this.getIntersects( raycaster );

	}
```
</details>

##### `select(object: any): void`

<details><summary>Code</summary>

```ts
select( object ) {

		if ( this.editor.selected === object ) return;

		let uuid = null;

		if ( object !== null ) {

			uuid = object.uuid;

		}

		this.editor.selected = object;
		this.editor.config.setKey( 'selected', uuid );

		this.signals.objectSelected.dispatch( object );

	}
```
</details>

##### `deselect(): void`

<details><summary>Code</summary>

```ts
deselect() {

		this.select( null );

	}
```
</details>


---