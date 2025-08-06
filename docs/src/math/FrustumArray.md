[⬅️ Back to Table of Contents](../../index.md)

# 📄 `FrustumArray.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/FrustumArray.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `WebGLCoordinateSystem` | `../constants.js` |
| `Frustum` | `./Frustum.js` |
| `Matrix4` | `./Matrix4.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_projScreenMatrix` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_frustum` | `Frustum` | let/var | `new Frustum()` | ✗ |
| `camera` | `any` | let/var | `cameraArray.cameras[ i ]` | ✗ |
| `camera` | `any` | let/var | `cameraArray.cameras[ i ]` | ✗ |
| `camera` | `any` | let/var | `cameraArray.cameras[ i ]` | ✗ |
| `camera` | `any` | let/var | `cameraArray.cameras[ i ]` | ✗ |
| `camera` | `any` | let/var | `cameraArray.cameras[ i ]` | ✗ |


---

## Functions

### `FrustumArray.intersectsObject(object: Object3D, cameraArray: any): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the 3D object's bounding sphere is intersecting any frustum
	 * from the camera array.
	 *
	 * @param {Object3D} object - The 3D object to test.
	 * @param {Object} cameraArray - An object with a cameras property containing an array of cameras.
	 * @return {boolean} Whether the 3D object is visible in any camera.
	 */
```

**Parameters:**

- **`object`** `Object3D`
- **`cameraArray`** `any`

**Returns:** `boolean`

**Calls:**

- `_projScreenMatrix.multiplyMatrices`
- `_frustum.setFromProjectionMatrix`
- `_frustum.intersectsObject`

<details><summary>Code</summary>

```typescript
intersectsObject( object, cameraArray ) {

		if ( ! cameraArray.isArrayCamera || cameraArray.cameras.length === 0 ) {

			return false;

		}

		for ( let i = 0; i < cameraArray.cameras.length; i ++ ) {

			const camera = cameraArray.cameras[ i ];

			_projScreenMatrix.multiplyMatrices(
				camera.projectionMatrix,
				camera.matrixWorldInverse
			);

			_frustum.setFromProjectionMatrix(
				_projScreenMatrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

			if ( _frustum.intersectsObject( object ) ) {

				return true; // Object is visible in at least one camera

			}

		}

		return false; // Not visible in any camera

	}
```
</details>

### `FrustumArray.intersectsSprite(sprite: Sprite, cameraArray: any): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given sprite is intersecting any frustum
	 * from the camera array.
	 *
	 * @param {Sprite} sprite - The sprite to test.
	 * @param {Object} cameraArray - An object with a cameras property containing an array of cameras.
	 * @return {boolean} Whether the sprite is visible in any camera.
	 */
```

**Parameters:**

- **`sprite`** `Sprite`
- **`cameraArray`** `any`

**Returns:** `boolean`

**Calls:**

- `_projScreenMatrix.multiplyMatrices`
- `_frustum.setFromProjectionMatrix`
- `_frustum.intersectsSprite`

<details><summary>Code</summary>

```typescript
intersectsSprite( sprite, cameraArray ) {

		if ( ! cameraArray || ! cameraArray.cameras || cameraArray.cameras.length === 0 ) {

			return false;

		}

		for ( let i = 0; i < cameraArray.cameras.length; i ++ ) {

			const camera = cameraArray.cameras[ i ];

			_projScreenMatrix.multiplyMatrices(
				camera.projectionMatrix,
				camera.matrixWorldInverse
			);

			_frustum.setFromProjectionMatrix(
				_projScreenMatrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

			if ( _frustum.intersectsSprite( sprite ) ) {

				return true; // Sprite is visible in at least one camera

			}

		}

		return false; // Not visible in any camera

	}
```
</details>

### `FrustumArray.intersectsSphere(sphere: Sphere, cameraArray: any): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given bounding sphere is intersecting any frustum
	 * from the camera array.
	 *
	 * @param {Sphere} sphere - The bounding sphere to test.
	 * @param {Object} cameraArray - An object with a cameras property containing an array of cameras.
	 * @return {boolean} Whether the sphere is visible in any camera.
	 */
```

**Parameters:**

- **`sphere`** `Sphere`
- **`cameraArray`** `any`

**Returns:** `boolean`

**Calls:**

- `_projScreenMatrix.multiplyMatrices`
- `_frustum.setFromProjectionMatrix`
- `_frustum.intersectsSphere`

<details><summary>Code</summary>

```typescript
intersectsSphere( sphere, cameraArray ) {

		if ( ! cameraArray || ! cameraArray.cameras || cameraArray.cameras.length === 0 ) {

			return false;

		}

		for ( let i = 0; i < cameraArray.cameras.length; i ++ ) {

			const camera = cameraArray.cameras[ i ];

			_projScreenMatrix.multiplyMatrices(
				camera.projectionMatrix,
				camera.matrixWorldInverse
			);

			_frustum.setFromProjectionMatrix(
				_projScreenMatrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

			if ( _frustum.intersectsSphere( sphere ) ) {

				return true; // Sphere is visible in at least one camera

			}

		}

		return false; // Not visible in any camera

	}
```
</details>

### `FrustumArray.intersectsBox(box: Box3, cameraArray: any): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given bounding box is intersecting any frustum
	 * from the camera array.
	 *
	 * @param {Box3} box - The bounding box to test.
	 * @param {Object} cameraArray - An object with a cameras property containing an array of cameras.
	 * @return {boolean} Whether the box is visible in any camera.
	 */
```

**Parameters:**

- **`box`** `Box3`
- **`cameraArray`** `any`

**Returns:** `boolean`

**Calls:**

- `_projScreenMatrix.multiplyMatrices`
- `_frustum.setFromProjectionMatrix`
- `_frustum.intersectsBox`

<details><summary>Code</summary>

```typescript
intersectsBox( box, cameraArray ) {

		if ( ! cameraArray || ! cameraArray.cameras || cameraArray.cameras.length === 0 ) {

			return false;

		}

		for ( let i = 0; i < cameraArray.cameras.length; i ++ ) {

			const camera = cameraArray.cameras[ i ];

			_projScreenMatrix.multiplyMatrices(
				camera.projectionMatrix,
				camera.matrixWorldInverse
			);

			_frustum.setFromProjectionMatrix(
				_projScreenMatrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

			if ( _frustum.intersectsBox( box ) ) {

				return true; // Box is visible in at least one camera

			}

		}

		return false; // Not visible in any camera

	}
```
</details>

### `FrustumArray.containsPoint(point: Vector3, cameraArray: any): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given point lies within any frustum
	 * from the camera array.
	 *
	 * @param {Vector3} point - The point to test.
	 * @param {Object} cameraArray - An object with a cameras property containing an array of cameras.
	 * @return {boolean} Whether the point is visible in any camera.
	 */
```

**Parameters:**

- **`point`** `Vector3`
- **`cameraArray`** `any`

**Returns:** `boolean`

**Calls:**

- `_projScreenMatrix.multiplyMatrices`
- `_frustum.setFromProjectionMatrix`
- `_frustum.containsPoint`

<details><summary>Code</summary>

```typescript
containsPoint( point, cameraArray ) {

		if ( ! cameraArray || ! cameraArray.cameras || cameraArray.cameras.length === 0 ) {

			return false;

		}

		for ( let i = 0; i < cameraArray.cameras.length; i ++ ) {

			const camera = cameraArray.cameras[ i ];

			_projScreenMatrix.multiplyMatrices(
				camera.projectionMatrix,
				camera.matrixWorldInverse
			);

			_frustum.setFromProjectionMatrix(
				_projScreenMatrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

			if ( _frustum.containsPoint( point ) ) {

				return true; // Point is visible in at least one camera

			}

		}

		return false; // Not visible in any camera

	}
```
</details>

### `FrustumArray.clone(): FrustumArray`

**JSDoc:**
```typescript
/**
	 * Returns a new frustum array with copied values from this instance.
	 *
	 * @return {FrustumArray} A clone of this instance.
	 */
```

**Returns:** `FrustumArray`

<details><summary>Code</summary>

```typescript
clone() {

		return new FrustumArray();

	}
```
</details>


---

## Classes

### `FrustumArray`

<details><summary>Class Code</summary>

```ts
class FrustumArray {

	/**
	 * Constructs a new frustum array.
	 *
	 */
	constructor() {

		/**
		 * The coordinate system to use.
		 *
		 * @type {WebGLCoordinateSystem|WebGPUCoordinateSystem}
		 * @default WebGLCoordinateSystem
		 */
		this.coordinateSystem = WebGLCoordinateSystem;

	}

	/**
	 * Returns `true` if the 3D object's bounding sphere is intersecting any frustum
	 * from the camera array.
	 *
	 * @param {Object3D} object - The 3D object to test.
	 * @param {Object} cameraArray - An object with a cameras property containing an array of cameras.
	 * @return {boolean} Whether the 3D object is visible in any camera.
	 */
	intersectsObject( object, cameraArray ) {

		if ( ! cameraArray.isArrayCamera || cameraArray.cameras.length === 0 ) {

			return false;

		}

		for ( let i = 0; i < cameraArray.cameras.length; i ++ ) {

			const camera = cameraArray.cameras[ i ];

			_projScreenMatrix.multiplyMatrices(
				camera.projectionMatrix,
				camera.matrixWorldInverse
			);

			_frustum.setFromProjectionMatrix(
				_projScreenMatrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

			if ( _frustum.intersectsObject( object ) ) {

				return true; // Object is visible in at least one camera

			}

		}

		return false; // Not visible in any camera

	}

	/**
	 * Returns `true` if the given sprite is intersecting any frustum
	 * from the camera array.
	 *
	 * @param {Sprite} sprite - The sprite to test.
	 * @param {Object} cameraArray - An object with a cameras property containing an array of cameras.
	 * @return {boolean} Whether the sprite is visible in any camera.
	 */
	intersectsSprite( sprite, cameraArray ) {

		if ( ! cameraArray || ! cameraArray.cameras || cameraArray.cameras.length === 0 ) {

			return false;

		}

		for ( let i = 0; i < cameraArray.cameras.length; i ++ ) {

			const camera = cameraArray.cameras[ i ];

			_projScreenMatrix.multiplyMatrices(
				camera.projectionMatrix,
				camera.matrixWorldInverse
			);

			_frustum.setFromProjectionMatrix(
				_projScreenMatrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

			if ( _frustum.intersectsSprite( sprite ) ) {

				return true; // Sprite is visible in at least one camera

			}

		}

		return false; // Not visible in any camera

	}

	/**
	 * Returns `true` if the given bounding sphere is intersecting any frustum
	 * from the camera array.
	 *
	 * @param {Sphere} sphere - The bounding sphere to test.
	 * @param {Object} cameraArray - An object with a cameras property containing an array of cameras.
	 * @return {boolean} Whether the sphere is visible in any camera.
	 */
	intersectsSphere( sphere, cameraArray ) {

		if ( ! cameraArray || ! cameraArray.cameras || cameraArray.cameras.length === 0 ) {

			return false;

		}

		for ( let i = 0; i < cameraArray.cameras.length; i ++ ) {

			const camera = cameraArray.cameras[ i ];

			_projScreenMatrix.multiplyMatrices(
				camera.projectionMatrix,
				camera.matrixWorldInverse
			);

			_frustum.setFromProjectionMatrix(
				_projScreenMatrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

			if ( _frustum.intersectsSphere( sphere ) ) {

				return true; // Sphere is visible in at least one camera

			}

		}

		return false; // Not visible in any camera

	}

	/**
	 * Returns `true` if the given bounding box is intersecting any frustum
	 * from the camera array.
	 *
	 * @param {Box3} box - The bounding box to test.
	 * @param {Object} cameraArray - An object with a cameras property containing an array of cameras.
	 * @return {boolean} Whether the box is visible in any camera.
	 */
	intersectsBox( box, cameraArray ) {

		if ( ! cameraArray || ! cameraArray.cameras || cameraArray.cameras.length === 0 ) {

			return false;

		}

		for ( let i = 0; i < cameraArray.cameras.length; i ++ ) {

			const camera = cameraArray.cameras[ i ];

			_projScreenMatrix.multiplyMatrices(
				camera.projectionMatrix,
				camera.matrixWorldInverse
			);

			_frustum.setFromProjectionMatrix(
				_projScreenMatrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

			if ( _frustum.intersectsBox( box ) ) {

				return true; // Box is visible in at least one camera

			}

		}

		return false; // Not visible in any camera

	}

	/**
	 * Returns `true` if the given point lies within any frustum
	 * from the camera array.
	 *
	 * @param {Vector3} point - The point to test.
	 * @param {Object} cameraArray - An object with a cameras property containing an array of cameras.
	 * @return {boolean} Whether the point is visible in any camera.
	 */
	containsPoint( point, cameraArray ) {

		if ( ! cameraArray || ! cameraArray.cameras || cameraArray.cameras.length === 0 ) {

			return false;

		}

		for ( let i = 0; i < cameraArray.cameras.length; i ++ ) {

			const camera = cameraArray.cameras[ i ];

			_projScreenMatrix.multiplyMatrices(
				camera.projectionMatrix,
				camera.matrixWorldInverse
			);

			_frustum.setFromProjectionMatrix(
				_projScreenMatrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

			if ( _frustum.containsPoint( point ) ) {

				return true; // Point is visible in at least one camera

			}

		}

		return false; // Not visible in any camera

	}

	/**
	 * Returns a new frustum array with copied values from this instance.
	 *
	 * @return {FrustumArray} A clone of this instance.
	 */
	clone() {

		return new FrustumArray();

	}

}
```
</details>

#### Methods

##### `intersectsObject(object: Object3D, cameraArray: any): boolean`

<details><summary>Code</summary>

```ts
intersectsObject( object, cameraArray ) {

		if ( ! cameraArray.isArrayCamera || cameraArray.cameras.length === 0 ) {

			return false;

		}

		for ( let i = 0; i < cameraArray.cameras.length; i ++ ) {

			const camera = cameraArray.cameras[ i ];

			_projScreenMatrix.multiplyMatrices(
				camera.projectionMatrix,
				camera.matrixWorldInverse
			);

			_frustum.setFromProjectionMatrix(
				_projScreenMatrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

			if ( _frustum.intersectsObject( object ) ) {

				return true; // Object is visible in at least one camera

			}

		}

		return false; // Not visible in any camera

	}
```
</details>

##### `intersectsSprite(sprite: Sprite, cameraArray: any): boolean`

<details><summary>Code</summary>

```ts
intersectsSprite( sprite, cameraArray ) {

		if ( ! cameraArray || ! cameraArray.cameras || cameraArray.cameras.length === 0 ) {

			return false;

		}

		for ( let i = 0; i < cameraArray.cameras.length; i ++ ) {

			const camera = cameraArray.cameras[ i ];

			_projScreenMatrix.multiplyMatrices(
				camera.projectionMatrix,
				camera.matrixWorldInverse
			);

			_frustum.setFromProjectionMatrix(
				_projScreenMatrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

			if ( _frustum.intersectsSprite( sprite ) ) {

				return true; // Sprite is visible in at least one camera

			}

		}

		return false; // Not visible in any camera

	}
```
</details>

##### `intersectsSphere(sphere: Sphere, cameraArray: any): boolean`

<details><summary>Code</summary>

```ts
intersectsSphere( sphere, cameraArray ) {

		if ( ! cameraArray || ! cameraArray.cameras || cameraArray.cameras.length === 0 ) {

			return false;

		}

		for ( let i = 0; i < cameraArray.cameras.length; i ++ ) {

			const camera = cameraArray.cameras[ i ];

			_projScreenMatrix.multiplyMatrices(
				camera.projectionMatrix,
				camera.matrixWorldInverse
			);

			_frustum.setFromProjectionMatrix(
				_projScreenMatrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

			if ( _frustum.intersectsSphere( sphere ) ) {

				return true; // Sphere is visible in at least one camera

			}

		}

		return false; // Not visible in any camera

	}
```
</details>

##### `intersectsBox(box: Box3, cameraArray: any): boolean`

<details><summary>Code</summary>

```ts
intersectsBox( box, cameraArray ) {

		if ( ! cameraArray || ! cameraArray.cameras || cameraArray.cameras.length === 0 ) {

			return false;

		}

		for ( let i = 0; i < cameraArray.cameras.length; i ++ ) {

			const camera = cameraArray.cameras[ i ];

			_projScreenMatrix.multiplyMatrices(
				camera.projectionMatrix,
				camera.matrixWorldInverse
			);

			_frustum.setFromProjectionMatrix(
				_projScreenMatrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

			if ( _frustum.intersectsBox( box ) ) {

				return true; // Box is visible in at least one camera

			}

		}

		return false; // Not visible in any camera

	}
```
</details>

##### `containsPoint(point: Vector3, cameraArray: any): boolean`

<details><summary>Code</summary>

```ts
containsPoint( point, cameraArray ) {

		if ( ! cameraArray || ! cameraArray.cameras || cameraArray.cameras.length === 0 ) {

			return false;

		}

		for ( let i = 0; i < cameraArray.cameras.length; i ++ ) {

			const camera = cameraArray.cameras[ i ];

			_projScreenMatrix.multiplyMatrices(
				camera.projectionMatrix,
				camera.matrixWorldInverse
			);

			_frustum.setFromProjectionMatrix(
				_projScreenMatrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

			if ( _frustum.containsPoint( point ) ) {

				return true; // Point is visible in at least one camera

			}

		}

		return false; // Not visible in any camera

	}
```
</details>

##### `clone(): FrustumArray`

<details><summary>Code</summary>

```ts
clone() {

		return new FrustumArray();

	}
```
</details>


---