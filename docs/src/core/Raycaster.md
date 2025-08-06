[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Raycaster.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/core/Raycaster.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Matrix4` | `../math/Matrix4.js` |
| `Ray` | `../math/Ray.js` |
| `Layers` | `./Layers.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_matrix` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `propagate` | `boolean` | let/var | `true` | ✗ |
| `children` | `any` | let/var | `object.children` | ✗ |


---

## Functions

### `Raycaster.set(origin: Vector3, direction: Vector3): void`

**JSDoc:**
```typescript
/**
	 * Updates the ray with a new origin and direction by copying the values from the arguments.
	 *
	 * @param {Vector3} origin - The origin vector where the ray casts from.
	 * @param {Vector3} direction - The (normalized) direction vector that gives direction to the ray.
	 */
```

**Parameters:**

- **`origin`** `Vector3`
- **`direction`** `Vector3`

**Returns:** `void`

**Calls:**

- `this.ray.set`

**Internal Comments:**
```
// direction is assumed to be normalized (for accurate distance calculations) (x5)
```

<details><summary>Code</summary>

```typescript
set( origin, direction ) {

		// direction is assumed to be normalized (for accurate distance calculations)

		this.ray.set( origin, direction );

	}
```
</details>

### `Raycaster.setFromCamera(coords: Vector2, camera: Camera): void`

**JSDoc:**
```typescript
/**
	 * Uses the given coordinates and camera to compute a new origin and direction for the internal ray.
	 *
	 * @param {Vector2} coords - 2D coordinates of the mouse, in normalized device coordinates (NDC).
	 * X and Y components should be between `-1` and `1`.
	 * @param {Camera} camera - The camera from which the ray should originate.
	 */
```

**Parameters:**

- **`coords`** `Vector2`
- **`camera`** `Camera`

**Returns:** `void`

**Calls:**

- `this.ray.origin.setFromMatrixPosition`
- `this.ray.direction.set( coords.x, coords.y, 0.5 ).unproject( camera ).sub( this.ray.origin ).normalize`
- `this.ray.origin.set( coords.x, coords.y, ( camera.near + camera.far ) / ( camera.near - camera.far ) ).unproject`
- `this.ray.direction.set( 0, 0, - 1 ).transformDirection`
- `console.error`

<details><summary>Code</summary>

```typescript
setFromCamera( coords, camera ) {

		if ( camera.isPerspectiveCamera ) {

			this.ray.origin.setFromMatrixPosition( camera.matrixWorld );
			this.ray.direction.set( coords.x, coords.y, 0.5 ).unproject( camera ).sub( this.ray.origin ).normalize();
			this.camera = camera;

		} else if ( camera.isOrthographicCamera ) {

			this.ray.origin.set( coords.x, coords.y, ( camera.near + camera.far ) / ( camera.near - camera.far ) ).unproject( camera ); // set origin in plane of camera
			this.ray.direction.set( 0, 0, - 1 ).transformDirection( camera.matrixWorld );
			this.camera = camera;

		} else {

			console.error( 'THREE.Raycaster: Unsupported camera type: ' + camera.type );

		}

	}
```
</details>

### `Raycaster.setFromXRController(controller: WebXRController): Raycaster`

**JSDoc:**
```typescript
/**
	 * Uses the given WebXR controller to compute a new origin and direction for the internal ray.
	 *
	 * @param {WebXRController} controller - The controller to copy the position and direction from.
	 * @return {Raycaster} A reference to this raycaster.
	 */
```

**Parameters:**

- **`controller`** `WebXRController`

**Returns:** `Raycaster`

**Calls:**

- `_matrix.identity().extractRotation`
- `this.ray.origin.setFromMatrixPosition`
- `this.ray.direction.set( 0, 0, - 1 ).applyMatrix4`

<details><summary>Code</summary>

```typescript
setFromXRController( controller ) {

		_matrix.identity().extractRotation( controller.matrixWorld );

		this.ray.origin.setFromMatrixPosition( controller.matrixWorld );
		this.ray.direction.set( 0, 0, - 1 ).applyMatrix4( _matrix );

		return this;

	}
```
</details>

### `Raycaster.intersectObject(object: Object3D, recursive: boolean, intersects: any[]): Raycaster[]`

**JSDoc:**
```typescript
/**
	 * Checks all intersection between the ray and the object with or without the
	 * descendants. Intersections are returned sorted by distance, closest first.
	 *
	 * `Raycaster` delegates to the `raycast()` method of the passed 3D object, when
	 * evaluating whether the ray intersects the object or not. This allows meshes to respond
	 * differently to ray casting than lines or points.
	 *
	 * Note that for meshes, faces must be pointed towards the origin of the ray in order
	 * to be detected; intersections of the ray passing through the back of a face will not
	 * be detected. To raycast against both faces of an object, you'll want to set  {@link Material#side}
	 * to `THREE.DoubleSide`.
	 *
	 * @param {Object3D} object - The 3D object to check for intersection with the ray.
	 * @param {boolean} [recursive=true] - If set to `true`, it also checks all descendants.
	 * Otherwise it only checks intersection with the object.
	 * @param {Array<Raycaster~Intersection>} [intersects=[]] The target array that holds the result of the method.
	 * @return {Array<Raycaster~Intersection>} An array holding the intersection points.
	 */
```

**Parameters:**

- **`object`** `Object3D`
- **`recursive`** `boolean`
- **`intersects`** `any[]`

**Returns:** `Raycaster[]`

**Calls:**

- `intersect`
- `intersects.sort`

<details><summary>Code</summary>

```typescript
intersectObject( object, recursive = true, intersects = [] ) {

		intersect( object, this, intersects, recursive );

		intersects.sort( ascSort );

		return intersects;

	}
```
</details>

### `Raycaster.intersectObjects(objects: Object3D[], recursive: boolean, intersects: any[]): Raycaster[]`

**JSDoc:**
```typescript
/**
	 * Checks all intersection between the ray and the objects with or without
	 * the descendants. Intersections are returned sorted by distance, closest first.
	 *
	 * @param {Array<Object3D>} objects - The 3D objects to check for intersection with the ray.
	 * @param {boolean} [recursive=true] - If set to `true`, it also checks all descendants.
	 * Otherwise it only checks intersection with the object.
	 * @param {Array<Raycaster~Intersection>} [intersects=[]] The target array that holds the result of the method.
	 * @return {Array<Raycaster~Intersection>} An array holding the intersection points.
	 */
```

**Parameters:**

- **`objects`** `Object3D[]`
- **`recursive`** `boolean`
- **`intersects`** `any[]`

**Returns:** `Raycaster[]`

**Calls:**

- `intersect`
- `intersects.sort`

<details><summary>Code</summary>

```typescript
intersectObjects( objects, recursive = true, intersects = [] ) {

		for ( let i = 0, l = objects.length; i < l; i ++ ) {

			intersect( objects[ i ], this, intersects, recursive );

		}

		intersects.sort( ascSort );

		return intersects;

	}
```
</details>

### `ascSort(a: any, b: any): number`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function ascSort( a, b ) {

	return a.distance - b.distance;

}
```
</details>

### `intersect(object: any, raycaster: any, intersects: any, recursive: any): void`

**Parameters:**

- **`object`** `any`
- **`raycaster`** `any`
- **`intersects`** `any`
- **`recursive`** `any`

**Returns:** `void`

**Calls:**

- `object.layers.test`
- `object.raycast`
- `intersect`

<details><summary>Code</summary>

```typescript
function intersect( object, raycaster, intersects, recursive ) {

	let propagate = true;

	if ( object.layers.test( raycaster.layers ) ) {

		const result = object.raycast( raycaster, intersects );

		if ( result === false ) propagate = false;

	}

	if ( propagate === true && recursive === true ) {

		const children = object.children;

		for ( let i = 0, l = children.length; i < l; i ++ ) {

			intersect( children[ i ], raycaster, intersects, true );

		}

	}

}
```
</details>


---

## Classes

### `Raycaster`

<details><summary>Class Code</summary>

```ts
class Raycaster {

	/**
	 * Constructs a new raycaster.
	 *
	 * @param {Vector3} origin - The origin vector where the ray casts from.
	 * @param {Vector3} direction - The (normalized) direction vector that gives direction to the ray.
	 * @param {number} [near=0] - All results returned are further away than near. Near can't be negative.
	 * @param {number} [far=Infinity] - All results returned are closer than far. Far can't be lower than near.
	 */
	constructor( origin, direction, near = 0, far = Infinity ) {

		/**
		 * The ray used for raycasting.
		 *
		 * @type {Ray}
		 */
		this.ray = new Ray( origin, direction );

		/**
		 * All results returned are further away than near. Near can't be negative.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.near = near;

		/**
		 * All results returned are further away than near. Near can't be negative.
		 *
		 * @type {number}
		 * @default Infinity
		 */
		this.far = far;

		/**
		 * The camera to use when raycasting against view-dependent objects such as
		 * billboarded objects like sprites. This field can be set manually or
		 * is set when calling `setFromCamera()`.
		 *
		 * @type {?Camera}
		 * @default null
		 */
		this.camera = null;

		/**
		 * Allows to selectively ignore 3D objects when performing intersection tests.
		 * The following code example ensures that only 3D objects on layer `1` will be
		 * honored by raycaster.
		 * ```js
		 * raycaster.layers.set( 1 );
		 * object.layers.enable( 1 );
		 * ```
		 *
		 * @type {Layers}
		 */
		this.layers = new Layers();


		/**
		 * A parameter object that configures the raycasting. It has the structure:
		 *
		 * ```
		 * {
		 * 	Mesh: {},
		 * 	Line: { threshold: 1 },
		 * 	LOD: {},
		 * 	Points: { threshold: 1 },
		 * 	Sprite: {}
		 * }
		 * ```
		 * Where `threshold` is the precision of the raycaster when intersecting objects, in world units.
		 *
		 * @type {Object}
		 */
		this.params = {
			Mesh: {},
			Line: { threshold: 1 },
			LOD: {},
			Points: { threshold: 1 },
			Sprite: {}
		};

	}

	/**
	 * Updates the ray with a new origin and direction by copying the values from the arguments.
	 *
	 * @param {Vector3} origin - The origin vector where the ray casts from.
	 * @param {Vector3} direction - The (normalized) direction vector that gives direction to the ray.
	 */
	set( origin, direction ) {

		// direction is assumed to be normalized (for accurate distance calculations)

		this.ray.set( origin, direction );

	}

	/**
	 * Uses the given coordinates and camera to compute a new origin and direction for the internal ray.
	 *
	 * @param {Vector2} coords - 2D coordinates of the mouse, in normalized device coordinates (NDC).
	 * X and Y components should be between `-1` and `1`.
	 * @param {Camera} camera - The camera from which the ray should originate.
	 */
	setFromCamera( coords, camera ) {

		if ( camera.isPerspectiveCamera ) {

			this.ray.origin.setFromMatrixPosition( camera.matrixWorld );
			this.ray.direction.set( coords.x, coords.y, 0.5 ).unproject( camera ).sub( this.ray.origin ).normalize();
			this.camera = camera;

		} else if ( camera.isOrthographicCamera ) {

			this.ray.origin.set( coords.x, coords.y, ( camera.near + camera.far ) / ( camera.near - camera.far ) ).unproject( camera ); // set origin in plane of camera
			this.ray.direction.set( 0, 0, - 1 ).transformDirection( camera.matrixWorld );
			this.camera = camera;

		} else {

			console.error( 'THREE.Raycaster: Unsupported camera type: ' + camera.type );

		}

	}

	/**
	 * Uses the given WebXR controller to compute a new origin and direction for the internal ray.
	 *
	 * @param {WebXRController} controller - The controller to copy the position and direction from.
	 * @return {Raycaster} A reference to this raycaster.
	 */
	setFromXRController( controller ) {

		_matrix.identity().extractRotation( controller.matrixWorld );

		this.ray.origin.setFromMatrixPosition( controller.matrixWorld );
		this.ray.direction.set( 0, 0, - 1 ).applyMatrix4( _matrix );

		return this;

	}

	/**
	 * The intersection point of a raycaster intersection test.
	 * @typedef {Object} Raycaster~Intersection
	 * @property {number} distance - The distance from the ray's origin to the intersection point.
	 * @property {number} distanceToRay -  Some 3D objects e.g. {@link Points} provide the distance of the
	 * intersection to the nearest point on the ray. For other objects it will be `undefined`.
	 * @property {Vector3} point - The intersection point, in world coordinates.
	 * @property {Object} face - The face that has been intersected.
	 * @property {number} faceIndex - The face index.
	 * @property {Object3D} object - The 3D object that has been intersected.
	 * @property {Vector2} uv - U,V coordinates at point of intersection.
	 * @property {Vector2} uv1 - Second set of U,V coordinates at point of intersection.
	 * @property {Vector3} uv1 - Interpolated normal vector at point of intersection.
	 * @property {number} instanceId - The index number of the instance where the ray
	 * intersects the {@link InstancedMesh}.
	 */

	/**
	 * Checks all intersection between the ray and the object with or without the
	 * descendants. Intersections are returned sorted by distance, closest first.
	 *
	 * `Raycaster` delegates to the `raycast()` method of the passed 3D object, when
	 * evaluating whether the ray intersects the object or not. This allows meshes to respond
	 * differently to ray casting than lines or points.
	 *
	 * Note that for meshes, faces must be pointed towards the origin of the ray in order
	 * to be detected; intersections of the ray passing through the back of a face will not
	 * be detected. To raycast against both faces of an object, you'll want to set  {@link Material#side}
	 * to `THREE.DoubleSide`.
	 *
	 * @param {Object3D} object - The 3D object to check for intersection with the ray.
	 * @param {boolean} [recursive=true] - If set to `true`, it also checks all descendants.
	 * Otherwise it only checks intersection with the object.
	 * @param {Array<Raycaster~Intersection>} [intersects=[]] The target array that holds the result of the method.
	 * @return {Array<Raycaster~Intersection>} An array holding the intersection points.
	 */
	intersectObject( object, recursive = true, intersects = [] ) {

		intersect( object, this, intersects, recursive );

		intersects.sort( ascSort );

		return intersects;

	}

	/**
	 * Checks all intersection between the ray and the objects with or without
	 * the descendants. Intersections are returned sorted by distance, closest first.
	 *
	 * @param {Array<Object3D>} objects - The 3D objects to check for intersection with the ray.
	 * @param {boolean} [recursive=true] - If set to `true`, it also checks all descendants.
	 * Otherwise it only checks intersection with the object.
	 * @param {Array<Raycaster~Intersection>} [intersects=[]] The target array that holds the result of the method.
	 * @return {Array<Raycaster~Intersection>} An array holding the intersection points.
	 */
	intersectObjects( objects, recursive = true, intersects = [] ) {

		for ( let i = 0, l = objects.length; i < l; i ++ ) {

			intersect( objects[ i ], this, intersects, recursive );

		}

		intersects.sort( ascSort );

		return intersects;

	}

}
```
</details>

#### Methods

##### `set(origin: Vector3, direction: Vector3): void`

<details><summary>Code</summary>

```ts
set( origin, direction ) {

		// direction is assumed to be normalized (for accurate distance calculations)

		this.ray.set( origin, direction );

	}
```
</details>

##### `setFromCamera(coords: Vector2, camera: Camera): void`

<details><summary>Code</summary>

```ts
setFromCamera( coords, camera ) {

		if ( camera.isPerspectiveCamera ) {

			this.ray.origin.setFromMatrixPosition( camera.matrixWorld );
			this.ray.direction.set( coords.x, coords.y, 0.5 ).unproject( camera ).sub( this.ray.origin ).normalize();
			this.camera = camera;

		} else if ( camera.isOrthographicCamera ) {

			this.ray.origin.set( coords.x, coords.y, ( camera.near + camera.far ) / ( camera.near - camera.far ) ).unproject( camera ); // set origin in plane of camera
			this.ray.direction.set( 0, 0, - 1 ).transformDirection( camera.matrixWorld );
			this.camera = camera;

		} else {

			console.error( 'THREE.Raycaster: Unsupported camera type: ' + camera.type );

		}

	}
```
</details>

##### `setFromXRController(controller: WebXRController): Raycaster`

<details><summary>Code</summary>

```ts
setFromXRController( controller ) {

		_matrix.identity().extractRotation( controller.matrixWorld );

		this.ray.origin.setFromMatrixPosition( controller.matrixWorld );
		this.ray.direction.set( 0, 0, - 1 ).applyMatrix4( _matrix );

		return this;

	}
```
</details>

##### `intersectObject(object: Object3D, recursive: boolean, intersects: any[]): Raycaster[]`

<details><summary>Code</summary>

```ts
intersectObject( object, recursive = true, intersects = [] ) {

		intersect( object, this, intersects, recursive );

		intersects.sort( ascSort );

		return intersects;

	}
```
</details>

##### `intersectObjects(objects: Object3D[], recursive: boolean, intersects: any[]): Raycaster[]`

<details><summary>Code</summary>

```ts
intersectObjects( objects, recursive = true, intersects = [] ) {

		for ( let i = 0, l = objects.length; i < l; i ++ ) {

			intersect( objects[ i ], this, intersects, recursive );

		}

		intersects.sort( ascSort );

		return intersects;

	}
```
</details>


---