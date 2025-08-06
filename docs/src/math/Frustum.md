[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Frustum.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 30 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/Frustum.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `WebGLCoordinateSystem` | `../constants.js` |
| `WebGPUCoordinateSystem` | `../constants.js` |
| `Vector2` | `./Vector2.js` |
| `Vector3` | `./Vector3.js` |
| `Sphere` | `./Sphere.js` |
| `Plane` | `./Plane.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_sphere` | `Sphere` | let/var | `new Sphere()` | ✗ |
| `_defaultSpriteCenter` | `Vector2` | let/var | `new Vector2( 0.5, 0.5 )` | ✗ |
| `_vector` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `planes` | `Plane[]` | let/var | `this.planes` | ✗ |
| `planes` | `Plane[]` | let/var | `this.planes` | ✗ |
| `planes` | `Plane[]` | let/var | `this.planes` | ✗ |
| `me` | `any` | let/var | `m.elements` | ✗ |
| `me0` | `any` | let/var | `me[ 0 ]` | ✗ |
| `me1` | `any` | let/var | `me[ 1 ]` | ✗ |
| `me2` | `any` | let/var | `me[ 2 ]` | ✗ |
| `me3` | `any` | let/var | `me[ 3 ]` | ✗ |
| `me4` | `any` | let/var | `me[ 4 ]` | ✗ |
| `me5` | `any` | let/var | `me[ 5 ]` | ✗ |
| `me6` | `any` | let/var | `me[ 6 ]` | ✗ |
| `me7` | `any` | let/var | `me[ 7 ]` | ✗ |
| `me8` | `any` | let/var | `me[ 8 ]` | ✗ |
| `me9` | `any` | let/var | `me[ 9 ]` | ✗ |
| `me10` | `any` | let/var | `me[ 10 ]` | ✗ |
| `me11` | `any` | let/var | `me[ 11 ]` | ✗ |
| `me12` | `any` | let/var | `me[ 12 ]` | ✗ |
| `me13` | `any` | let/var | `me[ 13 ]` | ✗ |
| `me14` | `any` | let/var | `me[ 14 ]` | ✗ |
| `me15` | `any` | let/var | `me[ 15 ]` | ✗ |
| `geometry` | `any` | let/var | `object.geometry` | ✗ |
| `planes` | `Plane[]` | let/var | `this.planes` | ✗ |
| `center` | `Vector3` | let/var | `sphere.center` | ✗ |
| `negRadius` | `number` | let/var | `- sphere.radius` | ✗ |
| `planes` | `Plane[]` | let/var | `this.planes` | ✗ |
| `plane` | `Plane` | let/var | `planes[ i ]` | ✗ |
| `planes` | `Plane[]` | let/var | `this.planes` | ✗ |


---

## Functions

### `Frustum.set(p0: Plane, p1: Plane, p2: Plane, p3: Plane, p4: Plane, p5: Plane): Frustum`

**JSDoc:**
```typescript
/**
	 * Sets the frustum planes by copying the given planes.
	 *
	 * @param {Plane} [p0] - The first plane that encloses the frustum.
	 * @param {Plane} [p1] - The second plane that encloses the frustum.
	 * @param {Plane} [p2] - The third plane that encloses the frustum.
	 * @param {Plane} [p3] - The fourth plane that encloses the frustum.
	 * @param {Plane} [p4] - The fifth plane that encloses the frustum.
	 * @param {Plane} [p5] - The sixth plane that encloses the frustum.
	 * @return {Frustum} A reference to this frustum.
	 */
```

**Parameters:**

- **`p0`** `Plane`
- **`p1`** `Plane`
- **`p2`** `Plane`
- **`p3`** `Plane`
- **`p4`** `Plane`
- **`p5`** `Plane`

**Returns:** `Frustum`

**Calls:**

- `planes[ 0 ].copy`
- `planes[ 1 ].copy`
- `planes[ 2 ].copy`
- `planes[ 3 ].copy`
- `planes[ 4 ].copy`
- `planes[ 5 ].copy`

<details><summary>Code</summary>

```typescript
set( p0, p1, p2, p3, p4, p5 ) {

		const planes = this.planes;

		planes[ 0 ].copy( p0 );
		planes[ 1 ].copy( p1 );
		planes[ 2 ].copy( p2 );
		planes[ 3 ].copy( p3 );
		planes[ 4 ].copy( p4 );
		planes[ 5 ].copy( p5 );

		return this;

	}
```
</details>

### `Frustum.copy(frustum: Frustum): Frustum`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given frustum to this instance.
	 *
	 * @param {Frustum} frustum - The frustum to copy.
	 * @return {Frustum} A reference to this frustum.
	 */
```

**Parameters:**

- **`frustum`** `Frustum`

**Returns:** `Frustum`

**Calls:**

- `planes[ i ].copy`

<details><summary>Code</summary>

```typescript
copy( frustum ) {

		const planes = this.planes;

		for ( let i = 0; i < 6; i ++ ) {

			planes[ i ].copy( frustum.planes[ i ] );

		}

		return this;

	}
```
</details>

### `Frustum.setFromProjectionMatrix(m: Matrix4, coordinateSystem: number, reversedDepth: boolean): Frustum`

**JSDoc:**
```typescript
/**
	 * Sets the frustum planes from the given projection matrix.
	 *
	 * @param {Matrix4} m - The projection matrix.
	 * @param {(WebGLCoordinateSystem|WebGPUCoordinateSystem)} coordinateSystem - The coordinate system.
	 * @param {boolean} [reversedDepth=false] - Whether to use a reversed depth.
	 * @return {Frustum} A reference to this frustum.
	 */
```

**Parameters:**

- **`m`** `Matrix4`
- **`coordinateSystem`** `number`
- **`reversedDepth`** `boolean`

**Returns:** `Frustum`

**Calls:**

- `planes[ 0 ].setComponents( me3 - me0, me7 - me4, me11 - me8, me15 - me12 ).normalize`
- `planes[ 1 ].setComponents( me3 + me0, me7 + me4, me11 + me8, me15 + me12 ).normalize`
- `planes[ 2 ].setComponents( me3 + me1, me7 + me5, me11 + me9, me15 + me13 ).normalize`
- `planes[ 3 ].setComponents( me3 - me1, me7 - me5, me11 - me9, me15 - me13 ).normalize`
- `planes[ 4 ].setComponents( me2, me6, me10, me14 ).normalize`
- `planes[ 5 ].setComponents( me3 - me2, me7 - me6, me11 - me10, me15 - me14 ).normalize`
- `planes[ 4 ].setComponents( me3 - me2, me7 - me6, me11 - me10, me15 - me14 ).normalize`
- `planes[ 5 ].setComponents( me3 + me2, me7 + me6, me11 + me10, me15 + me14 ).normalize`
- `planes[ 5 ].setComponents( me2, me6, me10, me14 ).normalize`

<details><summary>Code</summary>

```typescript
setFromProjectionMatrix( m, coordinateSystem = WebGLCoordinateSystem, reversedDepth = false ) {

		const planes = this.planes;
		const me = m.elements;
		const me0 = me[ 0 ], me1 = me[ 1 ], me2 = me[ 2 ], me3 = me[ 3 ];
		const me4 = me[ 4 ], me5 = me[ 5 ], me6 = me[ 6 ], me7 = me[ 7 ];
		const me8 = me[ 8 ], me9 = me[ 9 ], me10 = me[ 10 ], me11 = me[ 11 ];
		const me12 = me[ 12 ], me13 = me[ 13 ], me14 = me[ 14 ], me15 = me[ 15 ];

		planes[ 0 ].setComponents( me3 - me0, me7 - me4, me11 - me8, me15 - me12 ).normalize();
		planes[ 1 ].setComponents( me3 + me0, me7 + me4, me11 + me8, me15 + me12 ).normalize();
		planes[ 2 ].setComponents( me3 + me1, me7 + me5, me11 + me9, me15 + me13 ).normalize();
		planes[ 3 ].setComponents( me3 - me1, me7 - me5, me11 - me9, me15 - me13 ).normalize();

		if ( reversedDepth ) {

			planes[ 4 ].setComponents( me2, me6, me10, me14 ).normalize(); // far
			planes[ 5 ].setComponents( me3 - me2, me7 - me6, me11 - me10, me15 - me14 ).normalize(); // near

		} else {

			planes[ 4 ].setComponents( me3 - me2, me7 - me6, me11 - me10, me15 - me14 ).normalize(); // far

			if ( coordinateSystem === WebGLCoordinateSystem ) {

				planes[ 5 ].setComponents( me3 + me2, me7 + me6, me11 + me10, me15 + me14 ).normalize(); // near

			} else if ( coordinateSystem === WebGPUCoordinateSystem ) {

				planes[ 5 ].setComponents( me2, me6, me10, me14 ).normalize(); // near

			} else {

				throw new Error( 'THREE.Frustum.setFromProjectionMatrix(): Invalid coordinate system: ' + coordinateSystem );

			}

		}

		return this;

	}
```
</details>

### `Frustum.intersectsObject(object: Object3D): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the 3D object's bounding sphere is intersecting this frustum.
	 *
	 * Note that the 3D object must have a geometry so that the bounding sphere can be calculated.
	 *
	 * @param {Object3D} object - The 3D object to test.
	 * @return {boolean} Whether the 3D object's bounding sphere is intersecting this frustum or not.
	 */
```

**Parameters:**

- **`object`** `Object3D`

**Returns:** `boolean`

**Calls:**

- `object.computeBoundingSphere`
- `_sphere.copy( object.boundingSphere ).applyMatrix4`
- `geometry.computeBoundingSphere`
- `_sphere.copy( geometry.boundingSphere ).applyMatrix4`
- `this.intersectsSphere`

<details><summary>Code</summary>

```typescript
intersectsObject( object ) {

		if ( object.boundingSphere !== undefined ) {

			if ( object.boundingSphere === null ) object.computeBoundingSphere();

			_sphere.copy( object.boundingSphere ).applyMatrix4( object.matrixWorld );

		} else {

			const geometry = object.geometry;

			if ( geometry.boundingSphere === null ) geometry.computeBoundingSphere();

			_sphere.copy( geometry.boundingSphere ).applyMatrix4( object.matrixWorld );

		}

		return this.intersectsSphere( _sphere );

	}
```
</details>

### `Frustum.intersectsSprite(sprite: Sprite): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given sprite is intersecting this frustum.
	 *
	 * @param {Sprite} sprite - The sprite to test.
	 * @return {boolean} Whether the sprite is intersecting this frustum or not.
	 */
```

**Parameters:**

- **`sprite`** `Sprite`

**Returns:** `boolean`

**Calls:**

- `_sphere.center.set`
- `_defaultSpriteCenter.distanceTo`
- `_sphere.applyMatrix4`
- `this.intersectsSphere`

<details><summary>Code</summary>

```typescript
intersectsSprite( sprite ) {

		_sphere.center.set( 0, 0, 0 );

		const offset = _defaultSpriteCenter.distanceTo( sprite.center );

		_sphere.radius = 0.7071067811865476 + offset;
		_sphere.applyMatrix4( sprite.matrixWorld );

		return this.intersectsSphere( _sphere );

	}
```
</details>

### `Frustum.intersectsSphere(sphere: Sphere): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given bounding sphere is intersecting this frustum.
	 *
	 * @param {Sphere} sphere - The bounding sphere to test.
	 * @return {boolean} Whether the bounding sphere is intersecting this frustum or not.
	 */
```

**Parameters:**

- **`sphere`** `Sphere`

**Returns:** `boolean`

**Calls:**

- `planes[ i ].distanceToPoint`

<details><summary>Code</summary>

```typescript
intersectsSphere( sphere ) {

		const planes = this.planes;
		const center = sphere.center;
		const negRadius = - sphere.radius;

		for ( let i = 0; i < 6; i ++ ) {

			const distance = planes[ i ].distanceToPoint( center );

			if ( distance < negRadius ) {

				return false;

			}

		}

		return true;

	}
```
</details>

### `Frustum.intersectsBox(box: Box3): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given bounding box is intersecting this frustum.
	 *
	 * @param {Box3} box - The bounding box to test.
	 * @return {boolean} Whether the bounding box is intersecting this frustum or not.
	 */
```

**Parameters:**

- **`box`** `Box3`

**Returns:** `boolean`

**Calls:**

- `plane.distanceToPoint`

**Internal Comments:**
```
// corner at max distance (x4)
```

<details><summary>Code</summary>

```typescript
intersectsBox( box ) {

		const planes = this.planes;

		for ( let i = 0; i < 6; i ++ ) {

			const plane = planes[ i ];

			// corner at max distance

			_vector.x = plane.normal.x > 0 ? box.max.x : box.min.x;
			_vector.y = plane.normal.y > 0 ? box.max.y : box.min.y;
			_vector.z = plane.normal.z > 0 ? box.max.z : box.min.z;

			if ( plane.distanceToPoint( _vector ) < 0 ) {

				return false;

			}

		}

		return true;

	}
```
</details>

### `Frustum.containsPoint(point: Vector3): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given point lies within the frustum.
	 *
	 * @param {Vector3} point - The point to test.
	 * @return {boolean} Whether the point lies within this frustum or not.
	 */
```

**Parameters:**

- **`point`** `Vector3`

**Returns:** `boolean`

**Calls:**

- `planes[ i ].distanceToPoint`

<details><summary>Code</summary>

```typescript
containsPoint( point ) {

		const planes = this.planes;

		for ( let i = 0; i < 6; i ++ ) {

			if ( planes[ i ].distanceToPoint( point ) < 0 ) {

				return false;

			}

		}

		return true;

	}
```
</details>

### `Frustum.clone(): Frustum`

**JSDoc:**
```typescript
/**
	 * Returns a new frustum with copied values from this instance.
	 *
	 * @return {Frustum} A clone of this instance.
	 */
```

**Returns:** `Frustum`

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

### `Frustum`

<details><summary>Class Code</summary>

```ts
class Frustum {

	/**
	 * Constructs a new frustum.
	 *
	 * @param {Plane} [p0] - The first plane that encloses the frustum.
	 * @param {Plane} [p1] - The second plane that encloses the frustum.
	 * @param {Plane} [p2] - The third plane that encloses the frustum.
	 * @param {Plane} [p3] - The fourth plane that encloses the frustum.
	 * @param {Plane} [p4] - The fifth plane that encloses the frustum.
	 * @param {Plane} [p5] - The sixth plane that encloses the frustum.
	 */
	constructor( p0 = new Plane(), p1 = new Plane(), p2 = new Plane(), p3 = new Plane(), p4 = new Plane(), p5 = new Plane() ) {

		/**
		 * This array holds the planes that enclose the frustum.
		 *
		 * @type {Array<Plane>}
		 */
		this.planes = [ p0, p1, p2, p3, p4, p5 ];

	}

	/**
	 * Sets the frustum planes by copying the given planes.
	 *
	 * @param {Plane} [p0] - The first plane that encloses the frustum.
	 * @param {Plane} [p1] - The second plane that encloses the frustum.
	 * @param {Plane} [p2] - The third plane that encloses the frustum.
	 * @param {Plane} [p3] - The fourth plane that encloses the frustum.
	 * @param {Plane} [p4] - The fifth plane that encloses the frustum.
	 * @param {Plane} [p5] - The sixth plane that encloses the frustum.
	 * @return {Frustum} A reference to this frustum.
	 */
	set( p0, p1, p2, p3, p4, p5 ) {

		const planes = this.planes;

		planes[ 0 ].copy( p0 );
		planes[ 1 ].copy( p1 );
		planes[ 2 ].copy( p2 );
		planes[ 3 ].copy( p3 );
		planes[ 4 ].copy( p4 );
		planes[ 5 ].copy( p5 );

		return this;

	}

	/**
	 * Copies the values of the given frustum to this instance.
	 *
	 * @param {Frustum} frustum - The frustum to copy.
	 * @return {Frustum} A reference to this frustum.
	 */
	copy( frustum ) {

		const planes = this.planes;

		for ( let i = 0; i < 6; i ++ ) {

			planes[ i ].copy( frustum.planes[ i ] );

		}

		return this;

	}

	/**
	 * Sets the frustum planes from the given projection matrix.
	 *
	 * @param {Matrix4} m - The projection matrix.
	 * @param {(WebGLCoordinateSystem|WebGPUCoordinateSystem)} coordinateSystem - The coordinate system.
	 * @param {boolean} [reversedDepth=false] - Whether to use a reversed depth.
	 * @return {Frustum} A reference to this frustum.
	 */
	setFromProjectionMatrix( m, coordinateSystem = WebGLCoordinateSystem, reversedDepth = false ) {

		const planes = this.planes;
		const me = m.elements;
		const me0 = me[ 0 ], me1 = me[ 1 ], me2 = me[ 2 ], me3 = me[ 3 ];
		const me4 = me[ 4 ], me5 = me[ 5 ], me6 = me[ 6 ], me7 = me[ 7 ];
		const me8 = me[ 8 ], me9 = me[ 9 ], me10 = me[ 10 ], me11 = me[ 11 ];
		const me12 = me[ 12 ], me13 = me[ 13 ], me14 = me[ 14 ], me15 = me[ 15 ];

		planes[ 0 ].setComponents( me3 - me0, me7 - me4, me11 - me8, me15 - me12 ).normalize();
		planes[ 1 ].setComponents( me3 + me0, me7 + me4, me11 + me8, me15 + me12 ).normalize();
		planes[ 2 ].setComponents( me3 + me1, me7 + me5, me11 + me9, me15 + me13 ).normalize();
		planes[ 3 ].setComponents( me3 - me1, me7 - me5, me11 - me9, me15 - me13 ).normalize();

		if ( reversedDepth ) {

			planes[ 4 ].setComponents( me2, me6, me10, me14 ).normalize(); // far
			planes[ 5 ].setComponents( me3 - me2, me7 - me6, me11 - me10, me15 - me14 ).normalize(); // near

		} else {

			planes[ 4 ].setComponents( me3 - me2, me7 - me6, me11 - me10, me15 - me14 ).normalize(); // far

			if ( coordinateSystem === WebGLCoordinateSystem ) {

				planes[ 5 ].setComponents( me3 + me2, me7 + me6, me11 + me10, me15 + me14 ).normalize(); // near

			} else if ( coordinateSystem === WebGPUCoordinateSystem ) {

				planes[ 5 ].setComponents( me2, me6, me10, me14 ).normalize(); // near

			} else {

				throw new Error( 'THREE.Frustum.setFromProjectionMatrix(): Invalid coordinate system: ' + coordinateSystem );

			}

		}

		return this;

	}

	/**
	 * Returns `true` if the 3D object's bounding sphere is intersecting this frustum.
	 *
	 * Note that the 3D object must have a geometry so that the bounding sphere can be calculated.
	 *
	 * @param {Object3D} object - The 3D object to test.
	 * @return {boolean} Whether the 3D object's bounding sphere is intersecting this frustum or not.
	 */
	intersectsObject( object ) {

		if ( object.boundingSphere !== undefined ) {

			if ( object.boundingSphere === null ) object.computeBoundingSphere();

			_sphere.copy( object.boundingSphere ).applyMatrix4( object.matrixWorld );

		} else {

			const geometry = object.geometry;

			if ( geometry.boundingSphere === null ) geometry.computeBoundingSphere();

			_sphere.copy( geometry.boundingSphere ).applyMatrix4( object.matrixWorld );

		}

		return this.intersectsSphere( _sphere );

	}

	/**
	 * Returns `true` if the given sprite is intersecting this frustum.
	 *
	 * @param {Sprite} sprite - The sprite to test.
	 * @return {boolean} Whether the sprite is intersecting this frustum or not.
	 */
	intersectsSprite( sprite ) {

		_sphere.center.set( 0, 0, 0 );

		const offset = _defaultSpriteCenter.distanceTo( sprite.center );

		_sphere.radius = 0.7071067811865476 + offset;
		_sphere.applyMatrix4( sprite.matrixWorld );

		return this.intersectsSphere( _sphere );

	}

	/**
	 * Returns `true` if the given bounding sphere is intersecting this frustum.
	 *
	 * @param {Sphere} sphere - The bounding sphere to test.
	 * @return {boolean} Whether the bounding sphere is intersecting this frustum or not.
	 */
	intersectsSphere( sphere ) {

		const planes = this.planes;
		const center = sphere.center;
		const negRadius = - sphere.radius;

		for ( let i = 0; i < 6; i ++ ) {

			const distance = planes[ i ].distanceToPoint( center );

			if ( distance < negRadius ) {

				return false;

			}

		}

		return true;

	}

	/**
	 * Returns `true` if the given bounding box is intersecting this frustum.
	 *
	 * @param {Box3} box - The bounding box to test.
	 * @return {boolean} Whether the bounding box is intersecting this frustum or not.
	 */
	intersectsBox( box ) {

		const planes = this.planes;

		for ( let i = 0; i < 6; i ++ ) {

			const plane = planes[ i ];

			// corner at max distance

			_vector.x = plane.normal.x > 0 ? box.max.x : box.min.x;
			_vector.y = plane.normal.y > 0 ? box.max.y : box.min.y;
			_vector.z = plane.normal.z > 0 ? box.max.z : box.min.z;

			if ( plane.distanceToPoint( _vector ) < 0 ) {

				return false;

			}

		}

		return true;

	}

	/**
	 * Returns `true` if the given point lies within the frustum.
	 *
	 * @param {Vector3} point - The point to test.
	 * @return {boolean} Whether the point lies within this frustum or not.
	 */
	containsPoint( point ) {

		const planes = this.planes;

		for ( let i = 0; i < 6; i ++ ) {

			if ( planes[ i ].distanceToPoint( point ) < 0 ) {

				return false;

			}

		}

		return true;

	}

	/**
	 * Returns a new frustum with copied values from this instance.
	 *
	 * @return {Frustum} A clone of this instance.
	 */
	clone() {

		return new this.constructor().copy( this );

	}

}
```
</details>

#### Methods

##### `set(p0: Plane, p1: Plane, p2: Plane, p3: Plane, p4: Plane, p5: Plane): Frustum`

<details><summary>Code</summary>

```ts
set( p0, p1, p2, p3, p4, p5 ) {

		const planes = this.planes;

		planes[ 0 ].copy( p0 );
		planes[ 1 ].copy( p1 );
		planes[ 2 ].copy( p2 );
		planes[ 3 ].copy( p3 );
		planes[ 4 ].copy( p4 );
		planes[ 5 ].copy( p5 );

		return this;

	}
```
</details>

##### `copy(frustum: Frustum): Frustum`

<details><summary>Code</summary>

```ts
copy( frustum ) {

		const planes = this.planes;

		for ( let i = 0; i < 6; i ++ ) {

			planes[ i ].copy( frustum.planes[ i ] );

		}

		return this;

	}
```
</details>

##### `setFromProjectionMatrix(m: Matrix4, coordinateSystem: number, reversedDepth: boolean): Frustum`

<details><summary>Code</summary>

```ts
setFromProjectionMatrix( m, coordinateSystem = WebGLCoordinateSystem, reversedDepth = false ) {

		const planes = this.planes;
		const me = m.elements;
		const me0 = me[ 0 ], me1 = me[ 1 ], me2 = me[ 2 ], me3 = me[ 3 ];
		const me4 = me[ 4 ], me5 = me[ 5 ], me6 = me[ 6 ], me7 = me[ 7 ];
		const me8 = me[ 8 ], me9 = me[ 9 ], me10 = me[ 10 ], me11 = me[ 11 ];
		const me12 = me[ 12 ], me13 = me[ 13 ], me14 = me[ 14 ], me15 = me[ 15 ];

		planes[ 0 ].setComponents( me3 - me0, me7 - me4, me11 - me8, me15 - me12 ).normalize();
		planes[ 1 ].setComponents( me3 + me0, me7 + me4, me11 + me8, me15 + me12 ).normalize();
		planes[ 2 ].setComponents( me3 + me1, me7 + me5, me11 + me9, me15 + me13 ).normalize();
		planes[ 3 ].setComponents( me3 - me1, me7 - me5, me11 - me9, me15 - me13 ).normalize();

		if ( reversedDepth ) {

			planes[ 4 ].setComponents( me2, me6, me10, me14 ).normalize(); // far
			planes[ 5 ].setComponents( me3 - me2, me7 - me6, me11 - me10, me15 - me14 ).normalize(); // near

		} else {

			planes[ 4 ].setComponents( me3 - me2, me7 - me6, me11 - me10, me15 - me14 ).normalize(); // far

			if ( coordinateSystem === WebGLCoordinateSystem ) {

				planes[ 5 ].setComponents( me3 + me2, me7 + me6, me11 + me10, me15 + me14 ).normalize(); // near

			} else if ( coordinateSystem === WebGPUCoordinateSystem ) {

				planes[ 5 ].setComponents( me2, me6, me10, me14 ).normalize(); // near

			} else {

				throw new Error( 'THREE.Frustum.setFromProjectionMatrix(): Invalid coordinate system: ' + coordinateSystem );

			}

		}

		return this;

	}
```
</details>

##### `intersectsObject(object: Object3D): boolean`

<details><summary>Code</summary>

```ts
intersectsObject( object ) {

		if ( object.boundingSphere !== undefined ) {

			if ( object.boundingSphere === null ) object.computeBoundingSphere();

			_sphere.copy( object.boundingSphere ).applyMatrix4( object.matrixWorld );

		} else {

			const geometry = object.geometry;

			if ( geometry.boundingSphere === null ) geometry.computeBoundingSphere();

			_sphere.copy( geometry.boundingSphere ).applyMatrix4( object.matrixWorld );

		}

		return this.intersectsSphere( _sphere );

	}
```
</details>

##### `intersectsSprite(sprite: Sprite): boolean`

<details><summary>Code</summary>

```ts
intersectsSprite( sprite ) {

		_sphere.center.set( 0, 0, 0 );

		const offset = _defaultSpriteCenter.distanceTo( sprite.center );

		_sphere.radius = 0.7071067811865476 + offset;
		_sphere.applyMatrix4( sprite.matrixWorld );

		return this.intersectsSphere( _sphere );

	}
```
</details>

##### `intersectsSphere(sphere: Sphere): boolean`

<details><summary>Code</summary>

```ts
intersectsSphere( sphere ) {

		const planes = this.planes;
		const center = sphere.center;
		const negRadius = - sphere.radius;

		for ( let i = 0; i < 6; i ++ ) {

			const distance = planes[ i ].distanceToPoint( center );

			if ( distance < negRadius ) {

				return false;

			}

		}

		return true;

	}
```
</details>

##### `intersectsBox(box: Box3): boolean`

<details><summary>Code</summary>

```ts
intersectsBox( box ) {

		const planes = this.planes;

		for ( let i = 0; i < 6; i ++ ) {

			const plane = planes[ i ];

			// corner at max distance

			_vector.x = plane.normal.x > 0 ? box.max.x : box.min.x;
			_vector.y = plane.normal.y > 0 ? box.max.y : box.min.y;
			_vector.z = plane.normal.z > 0 ? box.max.z : box.min.z;

			if ( plane.distanceToPoint( _vector ) < 0 ) {

				return false;

			}

		}

		return true;

	}
```
</details>

##### `containsPoint(point: Vector3): boolean`

<details><summary>Code</summary>

```ts
containsPoint( point ) {

		const planes = this.planes;

		for ( let i = 0; i < 6; i ++ ) {

			if ( planes[ i ].distanceToPoint( point ) < 0 ) {

				return false;

			}

		}

		return true;

	}
```
</details>

##### `clone(): Frustum`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor().copy( this );

	}
```
</details>


---