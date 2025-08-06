[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Camera.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/cameras/Camera.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `WebGLCoordinateSystem` | `../constants.js` |
| `Matrix4` | `../math/Matrix4.js` |
| `Object3D` | `../core/Object3D.js` |


---

## Functions

### `Camera.copy(source: any, recursive: any): this`

**Parameters:**

- **`source`** `any`
- **`recursive`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.matrixWorldInverse.copy`
- `this.projectionMatrix.copy`
- `this.projectionMatrixInverse.copy`

<details><summary>Code</summary>

```typescript
copy( source, recursive ) {

		super.copy( source, recursive );

		this.matrixWorldInverse.copy( source.matrixWorldInverse );

		this.projectionMatrix.copy( source.projectionMatrix );
		this.projectionMatrixInverse.copy( source.projectionMatrixInverse );

		this.coordinateSystem = source.coordinateSystem;

		return this;

	}
```
</details>

### `Camera.getWorldDirection(target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Returns a vector representing the ("look") direction of the 3D object in world space.
	 *
	 * This method is overwritten since cameras have a different forward vector compared to other
	 * 3D objects. A camera looks down its local, negative z-axis by default.
	 *
	 * @param {Vector3} target - The target vector the result is stored to.
	 * @return {Vector3} The 3D object's direction in world space.
	 */
```

**Parameters:**

- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `super.getWorldDirection( target ).negate`

<details><summary>Code</summary>

```typescript
getWorldDirection( target ) {

		return super.getWorldDirection( target ).negate();

	}
```
</details>

### `Camera.updateMatrixWorld(force: any): void`

**Parameters:**

- **`force`** `any`

**Returns:** `void`

**Calls:**

- `super.updateMatrixWorld`
- `this.matrixWorldInverse.copy( this.matrixWorld ).invert`

<details><summary>Code</summary>

```typescript
updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		this.matrixWorldInverse.copy( this.matrixWorld ).invert();

	}
```
</details>

### `Camera.updateWorldMatrix(updateParents: any, updateChildren: any): void`

**Parameters:**

- **`updateParents`** `any`
- **`updateChildren`** `any`

**Returns:** `void`

**Calls:**

- `super.updateWorldMatrix`
- `this.matrixWorldInverse.copy( this.matrixWorld ).invert`

<details><summary>Code</summary>

```typescript
updateWorldMatrix( updateParents, updateChildren ) {

		super.updateWorldMatrix( updateParents, updateChildren );

		this.matrixWorldInverse.copy( this.matrixWorld ).invert();

	}
```
</details>

### `Camera.clone(): any`

**Returns:** `any`

**Calls:**

- `new this.constructor().copy`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor().copy( this );

	}
```
</details>


---

## Classes

### `Camera`

<details><summary>Class Code</summary>

```ts
class Camera extends Object3D {

	/**
	 * Constructs a new camera.
	 */
	constructor() {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isCamera = true;

		this.type = 'Camera';

		/**
		 * The inverse of the camera's world matrix.
		 *
		 * @type {Matrix4}
		 */
		this.matrixWorldInverse = new Matrix4();

		/**
		 * The camera's projection matrix.
		 *
		 * @type {Matrix4}
		 */
		this.projectionMatrix = new Matrix4();

		/**
		 * The inverse of the camera's projection matrix.
		 *
		 * @type {Matrix4}
		 */
		this.projectionMatrixInverse = new Matrix4();

		/**
		 * The coordinate system in which the camera is used.
		 *
		 * @type {(WebGLCoordinateSystem|WebGPUCoordinateSystem)}
		 */
		this.coordinateSystem = WebGLCoordinateSystem;

		this._reversedDepth = false;

	}

	/**
	 * The flag that indicates whether the camera uses a reversed depth buffer.
	 *
	 * @type {boolean}
	 * @default false
	 */
	get reversedDepth() {

		return this._reversedDepth;

	}

	copy( source, recursive ) {

		super.copy( source, recursive );

		this.matrixWorldInverse.copy( source.matrixWorldInverse );

		this.projectionMatrix.copy( source.projectionMatrix );
		this.projectionMatrixInverse.copy( source.projectionMatrixInverse );

		this.coordinateSystem = source.coordinateSystem;

		return this;

	}

	/**
	 * Returns a vector representing the ("look") direction of the 3D object in world space.
	 *
	 * This method is overwritten since cameras have a different forward vector compared to other
	 * 3D objects. A camera looks down its local, negative z-axis by default.
	 *
	 * @param {Vector3} target - The target vector the result is stored to.
	 * @return {Vector3} The 3D object's direction in world space.
	 */
	getWorldDirection( target ) {

		return super.getWorldDirection( target ).negate();

	}

	updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		this.matrixWorldInverse.copy( this.matrixWorld ).invert();

	}

	updateWorldMatrix( updateParents, updateChildren ) {

		super.updateWorldMatrix( updateParents, updateChildren );

		this.matrixWorldInverse.copy( this.matrixWorld ).invert();

	}

	clone() {

		return new this.constructor().copy( this );

	}

}
```
</details>

#### Methods

##### `copy(source: any, recursive: any): this`

<details><summary>Code</summary>

```ts
copy( source, recursive ) {

		super.copy( source, recursive );

		this.matrixWorldInverse.copy( source.matrixWorldInverse );

		this.projectionMatrix.copy( source.projectionMatrix );
		this.projectionMatrixInverse.copy( source.projectionMatrixInverse );

		this.coordinateSystem = source.coordinateSystem;

		return this;

	}
```
</details>

##### `getWorldDirection(target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getWorldDirection( target ) {

		return super.getWorldDirection( target ).negate();

	}
```
</details>

##### `updateMatrixWorld(force: any): void`

<details><summary>Code</summary>

```ts
updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		this.matrixWorldInverse.copy( this.matrixWorld ).invert();

	}
```
</details>

##### `updateWorldMatrix(updateParents: any, updateChildren: any): void`

<details><summary>Code</summary>

```ts
updateWorldMatrix( updateParents, updateChildren ) {

		super.updateWorldMatrix( updateParents, updateChildren );

		this.matrixWorldInverse.copy( this.matrixWorld ).invert();

	}
```
</details>

##### `clone(): any`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor().copy( this );

	}
```
</details>


---