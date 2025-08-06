[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Gyroscope.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/misc/Gyroscope.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Object3D` | `three` |
| `Quaternion` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_translationObject` | `any` | let/var | `new Vector3()` | ✗ |
| `_quaternionObject` | `any` | let/var | `new Quaternion()` | ✗ |
| `_scaleObject` | `any` | let/var | `new Vector3()` | ✗ |
| `_translationWorld` | `any` | let/var | `new Vector3()` | ✗ |
| `_quaternionWorld` | `any` | let/var | `new Quaternion()` | ✗ |
| `_scaleWorld` | `any` | let/var | `new Vector3()` | ✗ |


---

## Functions

### `Gyroscope.updateMatrixWorld(force: any): void`

**Parameters:**

- **`force`** `any`

**Returns:** `void`

**Calls:**

- `this.updateMatrix`
- `this.matrixWorld.multiplyMatrices`
- `this.matrixWorld.decompose`
- `this.matrix.decompose`
- `this.matrixWorld.compose`
- `this.matrixWorld.copy`
- `this.children[ i ].updateMatrixWorld`

**Internal Comments:**
```
// update matrixWorld
// update children
```

<details><summary>Code</summary>

```typescript
updateMatrixWorld( force ) {

		this.matrixAutoUpdate && this.updateMatrix();

		// update matrixWorld

		if ( this.matrixWorldNeedsUpdate || force ) {

			if ( this.parent !== null ) {

				this.matrixWorld.multiplyMatrices( this.parent.matrixWorld, this.matrix );

				this.matrixWorld.decompose( _translationWorld, _quaternionWorld, _scaleWorld );
				this.matrix.decompose( _translationObject, _quaternionObject, _scaleObject );

				this.matrixWorld.compose( _translationWorld, _quaternionObject, _scaleWorld );


			} else {

				this.matrixWorld.copy( this.matrix );

			}


			this.matrixWorldNeedsUpdate = false;

			force = true;

		}

		// update children

		for ( let i = 0, l = this.children.length; i < l; i ++ ) {

			this.children[ i ].updateMatrixWorld( force );

		}

	}
```
</details>


---

## Classes

### `Gyroscope`

<details><summary>Class Code</summary>

```ts
class Gyroscope extends Object3D {

	/**
	 * Constructs a new gyroscope.
	 */
	constructor() {

		super();

	}

	updateMatrixWorld( force ) {

		this.matrixAutoUpdate && this.updateMatrix();

		// update matrixWorld

		if ( this.matrixWorldNeedsUpdate || force ) {

			if ( this.parent !== null ) {

				this.matrixWorld.multiplyMatrices( this.parent.matrixWorld, this.matrix );

				this.matrixWorld.decompose( _translationWorld, _quaternionWorld, _scaleWorld );
				this.matrix.decompose( _translationObject, _quaternionObject, _scaleObject );

				this.matrixWorld.compose( _translationWorld, _quaternionObject, _scaleWorld );


			} else {

				this.matrixWorld.copy( this.matrix );

			}


			this.matrixWorldNeedsUpdate = false;

			force = true;

		}

		// update children

		for ( let i = 0, l = this.children.length; i < l; i ++ ) {

			this.children[ i ].updateMatrixWorld( force );

		}

	}

}
```
</details>

#### Methods

##### `updateMatrixWorld(force: any): void`

<details><summary>Code</summary>

```ts
updateMatrixWorld( force ) {

		this.matrixAutoUpdate && this.updateMatrix();

		// update matrixWorld

		if ( this.matrixWorldNeedsUpdate || force ) {

			if ( this.parent !== null ) {

				this.matrixWorld.multiplyMatrices( this.parent.matrixWorld, this.matrix );

				this.matrixWorld.decompose( _translationWorld, _quaternionWorld, _scaleWorld );
				this.matrix.decompose( _translationObject, _quaternionObject, _scaleObject );

				this.matrixWorld.compose( _translationWorld, _quaternionObject, _scaleWorld );


			} else {

				this.matrixWorld.copy( this.matrix );

			}


			this.matrixWorldNeedsUpdate = false;

			force = true;

		}

		// update children

		for ( let i = 0, l = this.children.length; i < l; i ++ ) {

			this.children[ i ].updateMatrixWorld( force );

		}

	}
```
</details>


---