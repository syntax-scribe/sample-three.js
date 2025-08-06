[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Object3D.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 49 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 43 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/core/Object3D.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Quaternion` | `../math/Quaternion.js` |
| `Vector3` | `../math/Vector3.js` |
| `Matrix4` | `../math/Matrix4.js` |
| `EventDispatcher` | `./EventDispatcher.js` |
| `Euler` | `../math/Euler.js` |
| `Layers` | `./Layers.js` |
| `Matrix3` | `../math/Matrix3.js` |
| `generateUUID` | `../math/MathUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_object3DId` | `number` | let/var | `0` | ✗ |
| `_v1` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_q1` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `_m1` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_target` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_position` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_scale` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_quaternion` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `_xAxis` | `Vector3` | let/var | `new Vector3( 1, 0, 0 )` | ✗ |
| `_yAxis` | `Vector3` | let/var | `new Vector3( 0, 1, 0 )` | ✗ |
| `_zAxis` | `Vector3` | let/var | `new Vector3( 0, 0, 1 )` | ✗ |
| `_addedEvent` | `any` | let/var | `{ type: 'added' }` | ✗ |
| `_removedEvent` | `any` | let/var | `{ type: 'removed' }` | ✗ |
| `_childaddedEvent` | `any` | let/var | `{ type: 'childadded', child: null }` | ✗ |
| `_childremovedEvent` | `any` | let/var | `{ type: 'childremoved', child: null }` | ✗ |
| `position` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `rotation` | `Euler` | let/var | `new Euler()` | ✗ |
| `quaternion` | `Quaternion` | let/var | `new Quaternion()` | ✗ |
| `scale` | `Vector3` | let/var | `new Vector3( 1, 1, 1 )` | ✗ |
| `parent` | `Object3D` | let/var | `this.parent` | ✗ |
| `parent` | `Object3D` | let/var | `this.parent` | ✗ |
| `child` | `Object3D` | let/var | `this.children[ i ]` | ✗ |
| `children` | `Object3D[]` | let/var | `this.children` | ✗ |
| `e` | `number[]` | let/var | `this.matrixWorld.elements` | ✗ |
| `children` | `Object3D[]` | let/var | `this.children` | ✗ |
| `children` | `Object3D[]` | let/var | `this.children` | ✗ |
| `parent` | `Object3D` | let/var | `this.parent` | ✗ |
| `children` | `Object3D[]` | let/var | `this.children` | ✗ |
| `child` | `Object3D` | let/var | `children[ i ]` | ✗ |
| `parent` | `Object3D` | let/var | `this.parent` | ✗ |
| `children` | `Object3D[]` | let/var | `this.children` | ✗ |
| `child` | `Object3D` | let/var | `children[ i ]` | ✗ |
| `isRootObject` | `boolean` | let/var | `( meta === undefined \|\| typeof meta === 'string' )` | ✗ |
| `output` | `{ metadata: { version: number; type: ...` | let/var | `{}` | ✗ |
| `object` | `{ uuid: string; type: string; name: s...` | let/var | `{}` | ✗ |
| `parameters` | `any` | let/var | `this.geometry.parameters` | ✗ |
| `shapes` | `any` | let/var | `parameters.shapes` | ✗ |
| `shape` | `any` | let/var | `shapes[ i ]` | ✗ |
| `uuids` | `any[]` | let/var | `[]` | ✗ |
| `animation` | `AnimationClip` | let/var | `this.animations[ i ]` | ✗ |
| `values` | `any[]` | let/var | `[]` | ✗ |
| `data` | `any` | let/var | `cache[ key ]` | ✗ |
| `child` | `Object3D` | let/var | `source.children[ i ]` | ✗ |


---

## Functions

### `Object3D.onBeforeShadow(): void`

**JSDoc:**
```typescript
/**
	 * A callback that is executed immediately before a 3D object is rendered to a shadow map.
	 *
	 * @param {Renderer|WebGLRenderer} renderer - The renderer.
	 * @param {Object3D} object - The 3D object.
	 * @param {Camera} camera - The camera that is used to render the scene.
	 * @param {Camera} shadowCamera - The shadow camera.
	 * @param {BufferGeometry} geometry - The 3D object's geometry.
	 * @param {Material} depthMaterial - The depth material.
	 * @param {Object} group - The geometry group data.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
onBeforeShadow( /* renderer, object, camera, shadowCamera, geometry, depthMaterial, group */ ) {}
```
</details>

### `Object3D.onAfterShadow(): void`

**JSDoc:**
```typescript
/**
	 * A callback that is executed immediately after a 3D object is rendered to a shadow map.
	 *
	 * @param {Renderer|WebGLRenderer} renderer - The renderer.
	 * @param {Object3D} object - The 3D object.
	 * @param {Camera} camera - The camera that is used to render the scene.
	 * @param {Camera} shadowCamera - The shadow camera.
	 * @param {BufferGeometry} geometry - The 3D object's geometry.
	 * @param {Material} depthMaterial - The depth material.
	 * @param {Object} group - The geometry group data.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
onAfterShadow( /* renderer, object, camera, shadowCamera, geometry, depthMaterial, group */ ) {}
```
</details>

### `Object3D.onBeforeRender(): void`

**JSDoc:**
```typescript
/**
	 * A callback that is executed immediately before a 3D object is rendered.
	 *
	 * @param {Renderer|WebGLRenderer} renderer - The renderer.
	 * @param {Object3D} object - The 3D object.
	 * @param {Camera} camera - The camera that is used to render the scene.
	 * @param {BufferGeometry} geometry - The 3D object's geometry.
	 * @param {Material} material - The 3D object's material.
	 * @param {Object} group - The geometry group data.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
onBeforeRender( /* renderer, scene, camera, geometry, material, group */ ) {}
```
</details>

### `Object3D.onAfterRender(): void`

**JSDoc:**
```typescript
/**
	 * A callback that is executed immediately after a 3D object is rendered.
	 *
	 * @param {Renderer|WebGLRenderer} renderer - The renderer.
	 * @param {Object3D} object - The 3D object.
	 * @param {Camera} camera - The camera that is used to render the scene.
	 * @param {BufferGeometry} geometry - The 3D object's geometry.
	 * @param {Material} material - The 3D object's material.
	 * @param {Object} group - The geometry group data.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
onAfterRender( /* renderer, scene, camera, geometry, material, group */ ) {}
```
</details>

### `Object3D.applyMatrix4(matrix: Matrix4): void`

**JSDoc:**
```typescript
/**
	 * Applies the given transformation matrix to the object and updates the object's position,
	 * rotation and scale.
	 *
	 * @param {Matrix4} matrix - The transformation matrix.
	 */
```

**Parameters:**

- **`matrix`** `Matrix4`

**Returns:** `void`

**Calls:**

- `this.updateMatrix`
- `this.matrix.premultiply`
- `this.matrix.decompose`

<details><summary>Code</summary>

```typescript
applyMatrix4( matrix ) {

		if ( this.matrixAutoUpdate ) this.updateMatrix();

		this.matrix.premultiply( matrix );

		this.matrix.decompose( this.position, this.quaternion, this.scale );

	}
```
</details>

### `Object3D.applyQuaternion(q: Quaternion): Object3D`

**JSDoc:**
```typescript
/**
	 * Applies a rotation represented by given the quaternion to the 3D object.
	 *
	 * @param {Quaternion} q - The quaternion.
	 * @return {Object3D} A reference to this instance.
	 */
```

**Parameters:**

- **`q`** `Quaternion`

**Returns:** `Object3D`

**Calls:**

- `this.quaternion.premultiply`

<details><summary>Code</summary>

```typescript
applyQuaternion( q ) {

		this.quaternion.premultiply( q );

		return this;

	}
```
</details>

### `Object3D.setRotationFromAxisAngle(axis: Vector3, angle: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the given rotation represented as an axis/angle couple to the 3D object.
	 *
	 * @param {Vector3} axis - The (normalized) axis vector.
	 * @param {number} angle - The angle in radians.
	 */
```

**Parameters:**

- **`axis`** `Vector3`
- **`angle`** `number`

**Returns:** `void`

**Calls:**

- `this.quaternion.setFromAxisAngle`

**Internal Comments:**
```
// assumes axis is normalized (x5)
```

<details><summary>Code</summary>

```typescript
setRotationFromAxisAngle( axis, angle ) {

		// assumes axis is normalized

		this.quaternion.setFromAxisAngle( axis, angle );

	}
```
</details>

### `Object3D.setRotationFromEuler(euler: Euler): void`

**JSDoc:**
```typescript
/**
	 * Sets the given rotation represented as Euler angles to the 3D object.
	 *
	 * @param {Euler} euler - The Euler angles.
	 */
```

**Parameters:**

- **`euler`** `Euler`

**Returns:** `void`

**Calls:**

- `this.quaternion.setFromEuler`

<details><summary>Code</summary>

```typescript
setRotationFromEuler( euler ) {

		this.quaternion.setFromEuler( euler, true );

	}
```
</details>

### `Object3D.setRotationFromMatrix(m: Matrix4): void`

**JSDoc:**
```typescript
/**
	 * Sets the given rotation represented as rotation matrix to the 3D object.
	 *
	 * @param {Matrix4} m - Although a 4x4 matrix is expected, the upper 3x3 portion must be
	 * a pure rotation matrix (i.e, unscaled).
	 */
```

**Parameters:**

- **`m`** `Matrix4`

**Returns:** `void`

**Calls:**

- `this.quaternion.setFromRotationMatrix`

**Internal Comments:**
```
// assumes the upper 3x3 of m is a pure rotation matrix (i.e, unscaled) (x5)
```

<details><summary>Code</summary>

```typescript
setRotationFromMatrix( m ) {

		// assumes the upper 3x3 of m is a pure rotation matrix (i.e, unscaled)

		this.quaternion.setFromRotationMatrix( m );

	}
```
</details>

### `Object3D.setRotationFromQuaternion(q: Quaternion): void`

**JSDoc:**
```typescript
/**
	 * Sets the given rotation represented as a Quaternion to the 3D object.
	 *
	 * @param {Quaternion} q - The Quaternion
	 */
```

**Parameters:**

- **`q`** `Quaternion`

**Returns:** `void`

**Calls:**

- `this.quaternion.copy`

**Internal Comments:**
```
// assumes q is normalized (x5)
```

<details><summary>Code</summary>

```typescript
setRotationFromQuaternion( q ) {

		// assumes q is normalized

		this.quaternion.copy( q );

	}
```
</details>

### `Object3D.rotateOnAxis(axis: Vector3, angle: number): Object3D`

**JSDoc:**
```typescript
/**
	 * Rotates the 3D object along an axis in local space.
	 *
	 * @param {Vector3} axis - The (normalized) axis vector.
	 * @param {number} angle - The angle in radians.
	 * @return {Object3D} A reference to this instance.
	 */
```

**Parameters:**

- **`axis`** `Vector3`
- **`angle`** `number`

**Returns:** `Object3D`

**Calls:**

- `_q1.setFromAxisAngle`
- `this.quaternion.multiply`

**Internal Comments:**
```
// rotate object on axis in object space (x4)
// axis is assumed to be normalized (x4)
```

<details><summary>Code</summary>

```typescript
rotateOnAxis( axis, angle ) {

		// rotate object on axis in object space
		// axis is assumed to be normalized

		_q1.setFromAxisAngle( axis, angle );

		this.quaternion.multiply( _q1 );

		return this;

	}
```
</details>

### `Object3D.rotateOnWorldAxis(axis: Vector3, angle: number): Object3D`

**JSDoc:**
```typescript
/**
	 * Rotates the 3D object along an axis in world space.
	 *
	 * @param {Vector3} axis - The (normalized) axis vector.
	 * @param {number} angle - The angle in radians.
	 * @return {Object3D} A reference to this instance.
	 */
```

**Parameters:**

- **`axis`** `Vector3`
- **`angle`** `number`

**Returns:** `Object3D`

**Calls:**

- `_q1.setFromAxisAngle`
- `this.quaternion.premultiply`

**Internal Comments:**
```
// rotate object on axis in world space (x4)
// axis is assumed to be normalized (x4)
// method assumes no rotated parent (x4)
```

<details><summary>Code</summary>

```typescript
rotateOnWorldAxis( axis, angle ) {

		// rotate object on axis in world space
		// axis is assumed to be normalized
		// method assumes no rotated parent

		_q1.setFromAxisAngle( axis, angle );

		this.quaternion.premultiply( _q1 );

		return this;

	}
```
</details>

### `Object3D.rotateX(angle: number): Object3D`

**JSDoc:**
```typescript
/**
	 * Rotates the 3D object around its X axis in local space.
	 *
	 * @param {number} angle - The angle in radians.
	 * @return {Object3D} A reference to this instance.
	 */
```

**Parameters:**

- **`angle`** `number`

**Returns:** `Object3D`

**Calls:**

- `this.rotateOnAxis`

<details><summary>Code</summary>

```typescript
rotateX( angle ) {

		return this.rotateOnAxis( _xAxis, angle );

	}
```
</details>

### `Object3D.rotateY(angle: number): Object3D`

**JSDoc:**
```typescript
/**
	 * Rotates the 3D object around its Y axis in local space.
	 *
	 * @param {number} angle - The angle in radians.
	 * @return {Object3D} A reference to this instance.
	 */
```

**Parameters:**

- **`angle`** `number`

**Returns:** `Object3D`

**Calls:**

- `this.rotateOnAxis`

<details><summary>Code</summary>

```typescript
rotateY( angle ) {

		return this.rotateOnAxis( _yAxis, angle );

	}
```
</details>

### `Object3D.rotateZ(angle: number): Object3D`

**JSDoc:**
```typescript
/**
	 * Rotates the 3D object around its Z axis in local space.
	 *
	 * @param {number} angle - The angle in radians.
	 * @return {Object3D} A reference to this instance.
	 */
```

**Parameters:**

- **`angle`** `number`

**Returns:** `Object3D`

**Calls:**

- `this.rotateOnAxis`

<details><summary>Code</summary>

```typescript
rotateZ( angle ) {

		return this.rotateOnAxis( _zAxis, angle );

	}
```
</details>

### `Object3D.translateOnAxis(axis: Vector3, distance: number): Object3D`

**JSDoc:**
```typescript
/**
	 * Translate the 3D object by a distance along the given axis in local space.
	 *
	 * @param {Vector3} axis - The (normalized) axis vector.
	 * @param {number} distance - The distance in world units.
	 * @return {Object3D} A reference to this instance.
	 */
```

**Parameters:**

- **`axis`** `Vector3`
- **`distance`** `number`

**Returns:** `Object3D`

**Calls:**

- `_v1.copy( axis ).applyQuaternion`
- `this.position.add`
- `_v1.multiplyScalar`

**Internal Comments:**
```
// translate object by distance along axis in object space (x6)
// axis is assumed to be normalized (x6)
```

<details><summary>Code</summary>

```typescript
translateOnAxis( axis, distance ) {

		// translate object by distance along axis in object space
		// axis is assumed to be normalized

		_v1.copy( axis ).applyQuaternion( this.quaternion );

		this.position.add( _v1.multiplyScalar( distance ) );

		return this;

	}
```
</details>

### `Object3D.translateX(distance: number): Object3D`

**JSDoc:**
```typescript
/**
	 * Translate the 3D object by a distance along its X-axis in local space.
	 *
	 * @param {number} distance - The distance in world units.
	 * @return {Object3D} A reference to this instance.
	 */
```

**Parameters:**

- **`distance`** `number`

**Returns:** `Object3D`

**Calls:**

- `this.translateOnAxis`

<details><summary>Code</summary>

```typescript
translateX( distance ) {

		return this.translateOnAxis( _xAxis, distance );

	}
```
</details>

### `Object3D.translateY(distance: number): Object3D`

**JSDoc:**
```typescript
/**
	 * Translate the 3D object by a distance along its Y-axis in local space.
	 *
	 * @param {number} distance - The distance in world units.
	 * @return {Object3D} A reference to this instance.
	 */
```

**Parameters:**

- **`distance`** `number`

**Returns:** `Object3D`

**Calls:**

- `this.translateOnAxis`

<details><summary>Code</summary>

```typescript
translateY( distance ) {

		return this.translateOnAxis( _yAxis, distance );

	}
```
</details>

### `Object3D.translateZ(distance: number): Object3D`

**JSDoc:**
```typescript
/**
	 * Translate the 3D object by a distance along its Z-axis in local space.
	 *
	 * @param {number} distance - The distance in world units.
	 * @return {Object3D} A reference to this instance.
	 */
```

**Parameters:**

- **`distance`** `number`

**Returns:** `Object3D`

**Calls:**

- `this.translateOnAxis`

<details><summary>Code</summary>

```typescript
translateZ( distance ) {

		return this.translateOnAxis( _zAxis, distance );

	}
```
</details>

### `Object3D.localToWorld(vector: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Converts the given vector from this 3D object's local space to world space.
	 *
	 * @param {Vector3} vector - The vector to convert.
	 * @return {Vector3} The converted vector.
	 */
```

**Parameters:**

- **`vector`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `this.updateWorldMatrix`
- `vector.applyMatrix4`

<details><summary>Code</summary>

```typescript
localToWorld( vector ) {

		this.updateWorldMatrix( true, false );

		return vector.applyMatrix4( this.matrixWorld );

	}
```
</details>

### `Object3D.worldToLocal(vector: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Converts the given vector from this 3D object's word space to local space.
	 *
	 * @param {Vector3} vector - The vector to convert.
	 * @return {Vector3} The converted vector.
	 */
```

**Parameters:**

- **`vector`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `this.updateWorldMatrix`
- `vector.applyMatrix4`
- `_m1.copy( this.matrixWorld ).invert`

<details><summary>Code</summary>

```typescript
worldToLocal( vector ) {

		this.updateWorldMatrix( true, false );

		return vector.applyMatrix4( _m1.copy( this.matrixWorld ).invert() );

	}
```
</details>

### `Object3D.lookAt(x: number | Vector3, y: number, z: number): void`

**JSDoc:**
```typescript
/**
	 * Rotates the object to face a point in world space.
	 *
	 * This method does not support objects having non-uniformly-scaled parent(s).
	 *
	 * @param {number|Vector3} x - The x coordinate in world space. Alternatively, a vector representing a position in world space
	 * @param {number} [y] - The y coordinate in world space.
	 * @param {number} [z] - The z coordinate in world space.
	 */
```

**Parameters:**

- **`x`** `number | Vector3`
- **`y`** `number`
- **`z`** `number`

**Returns:** `void`

**Calls:**

- `_target.copy`
- `_target.set`
- `this.updateWorldMatrix`
- `_position.setFromMatrixPosition`
- `_m1.lookAt`
- `this.quaternion.setFromRotationMatrix`
- `_m1.extractRotation`
- `_q1.setFromRotationMatrix`
- `this.quaternion.premultiply`
- `_q1.invert`

**Internal Comments:**
```
// This method does not support objects having non-uniformly-scaled parent(s)
```

<details><summary>Code</summary>

```typescript
lookAt( x, y, z ) {

		// This method does not support objects having non-uniformly-scaled parent(s)

		if ( x.isVector3 ) {

			_target.copy( x );

		} else {

			_target.set( x, y, z );

		}

		const parent = this.parent;

		this.updateWorldMatrix( true, false );

		_position.setFromMatrixPosition( this.matrixWorld );

		if ( this.isCamera || this.isLight ) {

			_m1.lookAt( _position, _target, this.up );

		} else {

			_m1.lookAt( _target, _position, this.up );

		}

		this.quaternion.setFromRotationMatrix( _m1 );

		if ( parent ) {

			_m1.extractRotation( parent.matrixWorld );
			_q1.setFromRotationMatrix( _m1 );
			this.quaternion.premultiply( _q1.invert() );

		}

	}
```
</details>

### `Object3D.add(object: Object3D): Object3D`

**JSDoc:**
```typescript
/**
	 * Adds the given 3D object as a child to this 3D object. An arbitrary number of
	 * objects may be added. Any current parent on an object passed in here will be
	 * removed, since an object can have at most one parent.
	 *
	 * @fires Object3D#added
	 * @fires Object3D#childadded
	 * @param {Object3D} object - The 3D object to add.
	 * @return {Object3D} A reference to this instance.
	 */
```

**Parameters:**

- **`object`** `Object3D`

**Returns:** `Object3D`

**Calls:**

- `this.add`
- `console.error`
- `object.removeFromParent`
- `this.children.push`
- `object.dispatchEvent`
- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
add( object ) {

		if ( arguments.length > 1 ) {

			for ( let i = 0; i < arguments.length; i ++ ) {

				this.add( arguments[ i ] );

			}

			return this;

		}

		if ( object === this ) {

			console.error( 'THREE.Object3D.add: object can\'t be added as a child of itself.', object );
			return this;

		}

		if ( object && object.isObject3D ) {

			object.removeFromParent();
			object.parent = this;
			this.children.push( object );

			object.dispatchEvent( _addedEvent );

			_childaddedEvent.child = object;
			this.dispatchEvent( _childaddedEvent );
			_childaddedEvent.child = null;

		} else {

			console.error( 'THREE.Object3D.add: object not an instance of THREE.Object3D.', object );

		}

		return this;

	}
```
</details>

### `Object3D.remove(object: Object3D): Object3D`

**JSDoc:**
```typescript
/**
	 * Removes the given 3D object as child from this 3D object.
	 * An arbitrary number of objects may be removed.
	 *
	 * @fires Object3D#removed
	 * @fires Object3D#childremoved
	 * @param {Object3D} object - The 3D object to remove.
	 * @return {Object3D} A reference to this instance.
	 */
```

**Parameters:**

- **`object`** `Object3D`

**Returns:** `Object3D`

**Calls:**

- `this.remove`
- `this.children.indexOf`
- `this.children.splice`
- `object.dispatchEvent`
- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
remove( object ) {

		if ( arguments.length > 1 ) {

			for ( let i = 0; i < arguments.length; i ++ ) {

				this.remove( arguments[ i ] );

			}

			return this;

		}

		const index = this.children.indexOf( object );

		if ( index !== - 1 ) {

			object.parent = null;
			this.children.splice( index, 1 );

			object.dispatchEvent( _removedEvent );

			_childremovedEvent.child = object;
			this.dispatchEvent( _childremovedEvent );
			_childremovedEvent.child = null;

		}

		return this;

	}
```
</details>

### `Object3D.removeFromParent(): Object3D`

**JSDoc:**
```typescript
/**
	 * Removes this 3D object from its current parent.
	 *
	 * @fires Object3D#removed
	 * @fires Object3D#childremoved
	 * @return {Object3D} A reference to this instance.
	 */
```

**Returns:** `Object3D`

**Calls:**

- `parent.remove`

<details><summary>Code</summary>

```typescript
removeFromParent() {

		const parent = this.parent;

		if ( parent !== null ) {

			parent.remove( this );

		}

		return this;

	}
```
</details>

### `Object3D.clear(): Object3D`

**JSDoc:**
```typescript
/**
	 * Removes all child objects.
	 *
	 * @fires Object3D#removed
	 * @fires Object3D#childremoved
	 * @return {Object3D} A reference to this instance.
	 */
```

**Returns:** `Object3D`

**Calls:**

- `this.remove`

<details><summary>Code</summary>

```typescript
clear() {

		return this.remove( ... this.children );

	}
```
</details>

### `Object3D.attach(object: Object3D): Object3D`

**JSDoc:**
```typescript
/**
	 * Adds the given 3D object as a child of this 3D object, while maintaining the object's world
	 * transform. This method does not support scene graphs having non-uniformly-scaled nodes(s).
	 *
	 * @fires Object3D#added
	 * @fires Object3D#childadded
	 * @param {Object3D} object - The 3D object to attach.
	 * @return {Object3D} A reference to this instance.
	 */
```

**Parameters:**

- **`object`** `Object3D`

**Returns:** `Object3D`

**Calls:**

- `this.updateWorldMatrix`
- `_m1.copy( this.matrixWorld ).invert`
- `object.parent.updateWorldMatrix`
- `_m1.multiply`
- `object.applyMatrix4`
- `object.removeFromParent`
- `this.children.push`
- `object.updateWorldMatrix`
- `object.dispatchEvent`
- `this.dispatchEvent`

**Internal Comments:**
```
// adds object as a child of this, while maintaining the object's world transform (x4)
// Note: This method does not support scene graphs having non-uniformly-scaled nodes(s) (x4)
```

<details><summary>Code</summary>

```typescript
attach( object ) {

		// adds object as a child of this, while maintaining the object's world transform

		// Note: This method does not support scene graphs having non-uniformly-scaled nodes(s)

		this.updateWorldMatrix( true, false );

		_m1.copy( this.matrixWorld ).invert();

		if ( object.parent !== null ) {

			object.parent.updateWorldMatrix( true, false );

			_m1.multiply( object.parent.matrixWorld );

		}

		object.applyMatrix4( _m1 );

		object.removeFromParent();
		object.parent = this;
		this.children.push( object );

		object.updateWorldMatrix( false, true );

		object.dispatchEvent( _addedEvent );

		_childaddedEvent.child = object;
		this.dispatchEvent( _childaddedEvent );
		_childaddedEvent.child = null;

		return this;

	}
```
</details>

### `Object3D.getObjectById(id: number): Object3D`

**JSDoc:**
```typescript
/**
	 * Searches through the 3D object and its children, starting with the 3D object
	 * itself, and returns the first with a matching ID.
	 *
	 * @param {number} id - The id.
	 * @return {Object3D|undefined} The found 3D object. Returns `undefined` if no 3D object has been found.
	 */
```

**Parameters:**

- **`id`** `number`

**Returns:** `Object3D`

**Calls:**

- `this.getObjectByProperty`

<details><summary>Code</summary>

```typescript
getObjectById( id ) {

		return this.getObjectByProperty( 'id', id );

	}
```
</details>

### `Object3D.getObjectByName(name: string): Object3D`

**JSDoc:**
```typescript
/**
	 * Searches through the 3D object and its children, starting with the 3D object
	 * itself, and returns the first with a matching name.
	 *
	 * @param {string} name - The name.
	 * @return {Object3D|undefined} The found 3D object. Returns `undefined` if no 3D object has been found.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `Object3D`

**Calls:**

- `this.getObjectByProperty`

<details><summary>Code</summary>

```typescript
getObjectByName( name ) {

		return this.getObjectByProperty( 'name', name );

	}
```
</details>

### `Object3D.getObjectByProperty(name: string, value: any): Object3D`

**JSDoc:**
```typescript
/**
	 * Searches through the 3D object and its children, starting with the 3D object
	 * itself, and returns the first with a matching property value.
	 *
	 * @param {string} name - The name of the property.
	 * @param {any} value - The value.
	 * @return {Object3D|undefined} The found 3D object. Returns `undefined` if no 3D object has been found.
	 */
```

**Parameters:**

- **`name`** `string`
- **`value`** `any`

**Returns:** `Object3D`

**Calls:**

- `child.getObjectByProperty`

<details><summary>Code</summary>

```typescript
getObjectByProperty( name, value ) {

		if ( this[ name ] === value ) return this;

		for ( let i = 0, l = this.children.length; i < l; i ++ ) {

			const child = this.children[ i ];
			const object = child.getObjectByProperty( name, value );

			if ( object !== undefined ) {

				return object;

			}

		}

		return undefined;

	}
```
</details>

### `Object3D.getObjectsByProperty(name: string, value: any, result: Object3D[]): Object3D[]`

**JSDoc:**
```typescript
/**
	 * Searches through the 3D object and its children, starting with the 3D object
	 * itself, and returns all 3D objects with a matching property value.
	 *
	 * @param {string} name - The name of the property.
	 * @param {any} value - The value.
	 * @param {Array<Object3D>} result - The method stores the result in this array.
	 * @return {Array<Object3D>} The found 3D objects.
	 */
```

**Parameters:**

- **`name`** `string`
- **`value`** `any`
- **`result`** `Object3D[]`

**Returns:** `Object3D[]`

**Calls:**

- `result.push`
- `children[ i ].getObjectsByProperty`

<details><summary>Code</summary>

```typescript
getObjectsByProperty( name, value, result = [] ) {

		if ( this[ name ] === value ) result.push( this );

		const children = this.children;

		for ( let i = 0, l = children.length; i < l; i ++ ) {

			children[ i ].getObjectsByProperty( name, value, result );

		}

		return result;

	}
```
</details>

### `Object3D.getWorldPosition(target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Returns a vector representing the position of the 3D object in world space.
	 *
	 * @param {Vector3} target - The target vector the result is stored to.
	 * @return {Vector3} The 3D object's position in world space.
	 */
```

**Parameters:**

- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `this.updateWorldMatrix`
- `target.setFromMatrixPosition`

<details><summary>Code</summary>

```typescript
getWorldPosition( target ) {

		this.updateWorldMatrix( true, false );

		return target.setFromMatrixPosition( this.matrixWorld );

	}
```
</details>

### `Object3D.getWorldQuaternion(target: Quaternion): Quaternion`

**JSDoc:**
```typescript
/**
	 * Returns a Quaternion representing the position of the 3D object in world space.
	 *
	 * @param {Quaternion} target - The target Quaternion the result is stored to.
	 * @return {Quaternion} The 3D object's rotation in world space.
	 */
```

**Parameters:**

- **`target`** `Quaternion`

**Returns:** `Quaternion`

**Calls:**

- `this.updateWorldMatrix`
- `this.matrixWorld.decompose`

<details><summary>Code</summary>

```typescript
getWorldQuaternion( target ) {

		this.updateWorldMatrix( true, false );

		this.matrixWorld.decompose( _position, target, _scale );

		return target;

	}
```
</details>

### `Object3D.getWorldScale(target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Returns a vector representing the scale of the 3D object in world space.
	 *
	 * @param {Vector3} target - The target vector the result is stored to.
	 * @return {Vector3} The 3D object's scale in world space.
	 */
```

**Parameters:**

- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `this.updateWorldMatrix`
- `this.matrixWorld.decompose`

<details><summary>Code</summary>

```typescript
getWorldScale( target ) {

		this.updateWorldMatrix( true, false );

		this.matrixWorld.decompose( _position, _quaternion, target );

		return target;

	}
```
</details>

### `Object3D.getWorldDirection(target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Returns a vector representing the ("look") direction of the 3D object in world space.
	 *
	 * @param {Vector3} target - The target vector the result is stored to.
	 * @return {Vector3} The 3D object's direction in world space.
	 */
```

**Parameters:**

- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `this.updateWorldMatrix`
- `target.set( e[ 8 ], e[ 9 ], e[ 10 ] ).normalize`

<details><summary>Code</summary>

```typescript
getWorldDirection( target ) {

		this.updateWorldMatrix( true, false );

		const e = this.matrixWorld.elements;

		return target.set( e[ 8 ], e[ 9 ], e[ 10 ] ).normalize();

	}
```
</details>

### `Object3D.raycast(): void`

**JSDoc:**
```typescript
/**
	 * Abstract method to get intersections between a casted ray and this
	 * 3D object. Renderable 3D objects such as {@link Mesh}, {@link Line} or {@link Points}
	 * implement this method in order to use raycasting.
	 *
	 * @abstract
	 * @param {Raycaster} raycaster - The raycaster.
	 * @param {Array<Object>} intersects - An array holding the result of the method.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
raycast( /* raycaster, intersects */ ) {}
```
</details>

### `Object3D.traverse(callback: Function): void`

**JSDoc:**
```typescript
/**
	 * Executes the callback on this 3D object and all descendants.
	 *
	 * Note: Modifying the scene graph inside the callback is discouraged.
	 *
	 * @param {Function} callback - A callback function that allows to process the current 3D object.
	 */
```

**Parameters:**

- **`callback`** `Function`

**Returns:** `void`

**Calls:**

- `callback`
- `children[ i ].traverse`

<details><summary>Code</summary>

```typescript
traverse( callback ) {

		callback( this );

		const children = this.children;

		for ( let i = 0, l = children.length; i < l; i ++ ) {

			children[ i ].traverse( callback );

		}

	}
```
</details>

### `Object3D.traverseVisible(callback: Function): void`

**JSDoc:**
```typescript
/**
	 * Like {@link Object3D#traverse}, but the callback will only be executed for visible 3D objects.
	 * Descendants of invisible 3D objects are not traversed.
	 *
	 * Note: Modifying the scene graph inside the callback is discouraged.
	 *
	 * @param {Function} callback - A callback function that allows to process the current 3D object.
	 */
```

**Parameters:**

- **`callback`** `Function`

**Returns:** `void`

**Calls:**

- `callback`
- `children[ i ].traverseVisible`

<details><summary>Code</summary>

```typescript
traverseVisible( callback ) {

		if ( this.visible === false ) return;

		callback( this );

		const children = this.children;

		for ( let i = 0, l = children.length; i < l; i ++ ) {

			children[ i ].traverseVisible( callback );

		}

	}
```
</details>

### `Object3D.traverseAncestors(callback: Function): void`

**JSDoc:**
```typescript
/**
	 * Like {@link Object3D#traverse}, but the callback will only be executed for all ancestors.
	 *
	 * Note: Modifying the scene graph inside the callback is discouraged.
	 *
	 * @param {Function} callback - A callback function that allows to process the current 3D object.
	 */
```

**Parameters:**

- **`callback`** `Function`

**Returns:** `void`

**Calls:**

- `callback`
- `parent.traverseAncestors`

<details><summary>Code</summary>

```typescript
traverseAncestors( callback ) {

		const parent = this.parent;

		if ( parent !== null ) {

			callback( parent );

			parent.traverseAncestors( callback );

		}

	}
```
</details>

### `Object3D.updateMatrix(): void`

**JSDoc:**
```typescript
/**
	 * Updates the transformation matrix in local space by computing it from the current
	 * position, rotation and scale values.
	 */
```

**Returns:** `void`

**Calls:**

- `this.matrix.compose`

<details><summary>Code</summary>

```typescript
updateMatrix() {

		this.matrix.compose( this.position, this.quaternion, this.scale );

		this.matrixWorldNeedsUpdate = true;

	}
```
</details>

### `Object3D.updateMatrixWorld(force: boolean): void`

**JSDoc:**
```typescript
/**
	 * Updates the transformation matrix in world space of this 3D objects and its descendants.
	 *
	 * To ensure correct results, this method also recomputes the 3D object's transformation matrix in
	 * local space. The computation of the local and world matrix can be controlled with the
	 * {@link Object3D#matrixAutoUpdate} and {@link Object3D#matrixWorldAutoUpdate} flags which are both
	 * `true` by default.  Set these flags to `false` if you need more control over the update matrix process.
	 *
	 * @param {boolean} [force=false] - When set to `true`, a recomputation of world matrices is forced even
	 * when {@link Object3D#matrixWorldAutoUpdate} is set to `false`.
	 */
```

**Parameters:**

- **`force`** `boolean`

**Returns:** `void`

**Calls:**

- `this.updateMatrix`
- `this.matrixWorld.copy`
- `this.matrixWorld.multiplyMatrices`
- `child.updateMatrixWorld`

**Internal Comments:**
```
// make sure descendants are updated if required (x2)
```

<details><summary>Code</summary>

```typescript
updateMatrixWorld( force ) {

		if ( this.matrixAutoUpdate ) this.updateMatrix();

		if ( this.matrixWorldNeedsUpdate || force ) {

			if ( this.matrixWorldAutoUpdate === true ) {

				if ( this.parent === null ) {

					this.matrixWorld.copy( this.matrix );

				} else {

					this.matrixWorld.multiplyMatrices( this.parent.matrixWorld, this.matrix );

				}

			}

			this.matrixWorldNeedsUpdate = false;

			force = true;

		}

		// make sure descendants are updated if required

		const children = this.children;

		for ( let i = 0, l = children.length; i < l; i ++ ) {

			const child = children[ i ];

			child.updateMatrixWorld( force );

		}

	}
```
</details>

### `Object3D.updateWorldMatrix(updateParents: boolean, updateChildren: boolean): void`

**JSDoc:**
```typescript
/**
	 * An alternative version of {@link Object3D#updateMatrixWorld} with more control over the
	 * update of ancestor and descendant nodes.
	 *
	 * @param {boolean} [updateParents=false] Whether ancestor nodes should be updated or not.
	 * @param {boolean} [updateChildren=false] Whether descendant nodes should be updated or not.
	 */
```

**Parameters:**

- **`updateParents`** `boolean`
- **`updateChildren`** `boolean`

**Returns:** `void`

**Calls:**

- `parent.updateWorldMatrix`
- `this.updateMatrix`
- `this.matrixWorld.copy`
- `this.matrixWorld.multiplyMatrices`
- `child.updateWorldMatrix`

**Internal Comments:**
```
// make sure descendants are updated
```

<details><summary>Code</summary>

```typescript
updateWorldMatrix( updateParents, updateChildren ) {

		const parent = this.parent;

		if ( updateParents === true && parent !== null ) {

			parent.updateWorldMatrix( true, false );

		}

		if ( this.matrixAutoUpdate ) this.updateMatrix();

		if ( this.matrixWorldAutoUpdate === true ) {

			if ( this.parent === null ) {

				this.matrixWorld.copy( this.matrix );

			} else {

				this.matrixWorld.multiplyMatrices( this.parent.matrixWorld, this.matrix );

			}

		}

		// make sure descendants are updated

		if ( updateChildren === true ) {

			const children = this.children;

			for ( let i = 0, l = children.length; i < l; i ++ ) {

				const child = children[ i ];

				child.updateWorldMatrix( false, true );

			}

		}

	}
```
</details>

### `Object3D.toJSON(meta: any): any`

**JSDoc:**
```typescript
/**
	 * Serializes the 3D object into JSON.
	 *
	 * @param {?(Object|string)} meta - An optional value holding meta information about the serialization.
	 * @return {Object} A JSON object representing the serialized 3D object.
	 * @see {@link ObjectLoader#parse}
	 */
```

**Parameters:**

- **`meta`** `any`

**Returns:** `any`

**Calls:**

- `Object.keys`
- `this.matrix.toArray`
- `this.up.toArray`
- `this.instanceMatrix.toJSON`
- `this.instanceColor.toJSON`
- `this._geometryInfo.map`
- `info.boundingBox.toJSON`
- `info.boundingSphere.toJSON`
- `this._instanceInfo.map`
- `this._availableInstanceIds.slice`
- `this._availableGeometryIds.slice`
- `this._matricesTexture.toJSON`
- `this._indirectTexture.toJSON`
- `this._colorsTexture.toJSON`
- `this.boundingSphere.toJSON`
- `this.boundingBox.toJSON`
- `element.toJSON`
- `this.background.toJSON`
- `this.environment.toJSON`
- `serialize`
- `Array.isArray`
- `this.bindMatrix.toArray`
- `uuids.push`
- `object.children.push`
- `this.children[ i ].toJSON`
- `object.animations.push`
- `extractFromCache`
- `values.push`

**Internal Comments:**
```
// meta is a string when called from JSON.stringify (x2)
// meta is a hash used to collect geometries, materials.
// not providing it implies that this is the root object
// being serialized.
// initialize meta obj (x3)
// standard Object3D serialization (x2)
// object specific properties
// (x3)
// extract data from the cache hash
// remove metadata on each item
// and return as array
```

<details><summary>Code</summary>

```typescript
toJSON( meta ) {

		// meta is a string when called from JSON.stringify
		const isRootObject = ( meta === undefined || typeof meta === 'string' );

		const output = {};

		// meta is a hash used to collect geometries, materials.
		// not providing it implies that this is the root object
		// being serialized.
		if ( isRootObject ) {

			// initialize meta obj
			meta = {
				geometries: {},
				materials: {},
				textures: {},
				images: {},
				shapes: {},
				skeletons: {},
				animations: {},
				nodes: {}
			};

			output.metadata = {
				version: 4.7,
				type: 'Object',
				generator: 'Object3D.toJSON'
			};

		}

		// standard Object3D serialization

		const object = {};

		object.uuid = this.uuid;
		object.type = this.type;

		if ( this.name !== '' ) object.name = this.name;
		if ( this.castShadow === true ) object.castShadow = true;
		if ( this.receiveShadow === true ) object.receiveShadow = true;
		if ( this.visible === false ) object.visible = false;
		if ( this.frustumCulled === false ) object.frustumCulled = false;
		if ( this.renderOrder !== 0 ) object.renderOrder = this.renderOrder;
		if ( Object.keys( this.userData ).length > 0 ) object.userData = this.userData;

		object.layers = this.layers.mask;
		object.matrix = this.matrix.toArray();
		object.up = this.up.toArray();

		if ( this.matrixAutoUpdate === false ) object.matrixAutoUpdate = false;

		// object specific properties

		if ( this.isInstancedMesh ) {

			object.type = 'InstancedMesh';
			object.count = this.count;
			object.instanceMatrix = this.instanceMatrix.toJSON();
			if ( this.instanceColor !== null ) object.instanceColor = this.instanceColor.toJSON();

		}

		if ( this.isBatchedMesh ) {

			object.type = 'BatchedMesh';
			object.perObjectFrustumCulled = this.perObjectFrustumCulled;
			object.sortObjects = this.sortObjects;

			object.drawRanges = this._drawRanges;
			object.reservedRanges = this._reservedRanges;

			object.geometryInfo = this._geometryInfo.map( info => ( {
				...info,
				boundingBox: info.boundingBox ? info.boundingBox.toJSON() : undefined,
				boundingSphere: info.boundingSphere ? info.boundingSphere.toJSON() : undefined
			} ) );
			object.instanceInfo = this._instanceInfo.map( info => ( { ...info } ) );

			object.availableInstanceIds = this._availableInstanceIds.slice();
			object.availableGeometryIds = this._availableGeometryIds.slice();

			object.nextIndexStart = this._nextIndexStart;
			object.nextVertexStart = this._nextVertexStart;
			object.geometryCount = this._geometryCount;

			object.maxInstanceCount = this._maxInstanceCount;
			object.maxVertexCount = this._maxVertexCount;
			object.maxIndexCount = this._maxIndexCount;

			object.geometryInitialized = this._geometryInitialized;

			object.matricesTexture = this._matricesTexture.toJSON( meta );

			object.indirectTexture = this._indirectTexture.toJSON( meta );

			if ( this._colorsTexture !== null ) {

				object.colorsTexture = this._colorsTexture.toJSON( meta );

			}

			if ( this.boundingSphere !== null ) {

				object.boundingSphere = this.boundingSphere.toJSON();

			}

			if ( this.boundingBox !== null ) {

				object.boundingBox = this.boundingBox.toJSON();

			}

		}

		//

		function serialize( library, element ) {

			if ( library[ element.uuid ] === undefined ) {

				library[ element.uuid ] = element.toJSON( meta );

			}

			return element.uuid;

		}

		if ( this.isScene ) {

			if ( this.background ) {

				if ( this.background.isColor ) {

					object.background = this.background.toJSON();

				} else if ( this.background.isTexture ) {

					object.background = this.background.toJSON( meta ).uuid;

				}

			}

			if ( this.environment && this.environment.isTexture && this.environment.isRenderTargetTexture !== true ) {

				object.environment = this.environment.toJSON( meta ).uuid;

			}

		} else if ( this.isMesh || this.isLine || this.isPoints ) {

			object.geometry = serialize( meta.geometries, this.geometry );

			const parameters = this.geometry.parameters;

			if ( parameters !== undefined && parameters.shapes !== undefined ) {

				const shapes = parameters.shapes;

				if ( Array.isArray( shapes ) ) {

					for ( let i = 0, l = shapes.length; i < l; i ++ ) {

						const shape = shapes[ i ];

						serialize( meta.shapes, shape );

					}

				} else {

					serialize( meta.shapes, shapes );

				}

			}

		}

		if ( this.isSkinnedMesh ) {

			object.bindMode = this.bindMode;
			object.bindMatrix = this.bindMatrix.toArray();

			if ( this.skeleton !== undefined ) {

				serialize( meta.skeletons, this.skeleton );

				object.skeleton = this.skeleton.uuid;

			}

		}

		if ( this.material !== undefined ) {

			if ( Array.isArray( this.material ) ) {

				const uuids = [];

				for ( let i = 0, l = this.material.length; i < l; i ++ ) {

					uuids.push( serialize( meta.materials, this.material[ i ] ) );

				}

				object.material = uuids;

			} else {

				object.material = serialize( meta.materials, this.material );

			}

		}

		//

		if ( this.children.length > 0 ) {

			object.children = [];

			for ( let i = 0; i < this.children.length; i ++ ) {

				object.children.push( this.children[ i ].toJSON( meta ).object );

			}

		}

		//

		if ( this.animations.length > 0 ) {

			object.animations = [];

			for ( let i = 0; i < this.animations.length; i ++ ) {

				const animation = this.animations[ i ];

				object.animations.push( serialize( meta.animations, animation ) );

			}

		}

		if ( isRootObject ) {

			const geometries = extractFromCache( meta.geometries );
			const materials = extractFromCache( meta.materials );
			const textures = extractFromCache( meta.textures );
			const images = extractFromCache( meta.images );
			const shapes = extractFromCache( meta.shapes );
			const skeletons = extractFromCache( meta.skeletons );
			const animations = extractFromCache( meta.animations );
			const nodes = extractFromCache( meta.nodes );

			if ( geometries.length > 0 ) output.geometries = geometries;
			if ( materials.length > 0 ) output.materials = materials;
			if ( textures.length > 0 ) output.textures = textures;
			if ( images.length > 0 ) output.images = images;
			if ( shapes.length > 0 ) output.shapes = shapes;
			if ( skeletons.length > 0 ) output.skeletons = skeletons;
			if ( animations.length > 0 ) output.animations = animations;
			if ( nodes.length > 0 ) output.nodes = nodes;

		}

		output.object = object;

		return output;

		// extract data from the cache hash
		// remove metadata on each item
		// and return as array
		function extractFromCache( cache ) {

			const values = [];
			for ( const key in cache ) {

				const data = cache[ key ];
				delete data.metadata;
				values.push( data );

			}

			return values;

		}

	}
```
</details>

### `Object3D.clone(recursive: boolean): Object3D`

**JSDoc:**
```typescript
/**
	 * Returns a new 3D object with copied values from this instance.
	 *
	 * @param {boolean} [recursive=true] - When set to `true`, descendants of the 3D object are also cloned.
	 * @return {Object3D} A clone of this instance.
	 */
```

**Parameters:**

- **`recursive`** `boolean`

**Returns:** `Object3D`

**Calls:**

- `new this.constructor().copy`

<details><summary>Code</summary>

```typescript
clone( recursive ) {

		return new this.constructor().copy( this, recursive );

	}
```
</details>

### `Object3D.copy(source: Object3D, recursive: boolean): Object3D`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given 3D object to this instance.
	 *
	 * @param {Object3D} source - The 3D object to copy.
	 * @param {boolean} [recursive=true] - When set to `true`, descendants of the 3D object are cloned.
	 * @return {Object3D} A reference to this instance.
	 */
```

**Parameters:**

- **`source`** `Object3D`
- **`recursive`** `boolean`

**Returns:** `Object3D`

**Calls:**

- `this.up.copy`
- `this.position.copy`
- `this.quaternion.copy`
- `this.scale.copy`
- `this.matrix.copy`
- `this.matrixWorld.copy`
- `source.animations.slice`
- `JSON.parse`
- `JSON.stringify`
- `this.add`
- `child.clone`

<details><summary>Code</summary>

```typescript
copy( source, recursive = true ) {

		this.name = source.name;

		this.up.copy( source.up );

		this.position.copy( source.position );
		this.rotation.order = source.rotation.order;
		this.quaternion.copy( source.quaternion );
		this.scale.copy( source.scale );

		this.matrix.copy( source.matrix );
		this.matrixWorld.copy( source.matrixWorld );

		this.matrixAutoUpdate = source.matrixAutoUpdate;

		this.matrixWorldAutoUpdate = source.matrixWorldAutoUpdate;
		this.matrixWorldNeedsUpdate = source.matrixWorldNeedsUpdate;

		this.layers.mask = source.layers.mask;
		this.visible = source.visible;

		this.castShadow = source.castShadow;
		this.receiveShadow = source.receiveShadow;

		this.frustumCulled = source.frustumCulled;
		this.renderOrder = source.renderOrder;

		this.animations = source.animations.slice();

		this.userData = JSON.parse( JSON.stringify( source.userData ) );

		if ( recursive === true ) {

			for ( let i = 0; i < source.children.length; i ++ ) {

				const child = source.children[ i ];
				this.add( child.clone() );

			}

		}

		return this;

	}
```
</details>

### `onRotationChange(): void`

**Returns:** `void`

**Calls:**

- `quaternion.setFromEuler`

<details><summary>Code</summary>

```typescript
function onRotationChange() {

			quaternion.setFromEuler( rotation, false );

		}
```
</details>

### `onQuaternionChange(): void`

**Returns:** `void`

**Calls:**

- `rotation.setFromQuaternion`

<details><summary>Code</summary>

```typescript
function onQuaternionChange() {

			rotation.setFromQuaternion( quaternion, undefined, false );

		}
```
</details>

### `serialize(library: any, element: any): any`

**Parameters:**

- **`library`** `any`
- **`element`** `any`

**Returns:** `any`

**Calls:**

- `element.toJSON`

<details><summary>Code</summary>

```typescript
function serialize( library, element ) {

			if ( library[ element.uuid ] === undefined ) {

				library[ element.uuid ] = element.toJSON( meta );

			}

			return element.uuid;

		}
```
</details>

### `extractFromCache(cache: any): any[]`

**Parameters:**

- **`cache`** `any`

**Returns:** `any[]`

**Calls:**

- `values.push`

<details><summary>Code</summary>

```typescript
function extractFromCache( cache ) {

			const values = [];
			for ( const key in cache ) {

				const data = cache[ key ];
				delete data.metadata;
				values.push( data );

			}

			return values;

		}
```
</details>


---

## Classes

### `Object3D`

<details><summary>Class Code</summary>

```ts
class Object3D extends EventDispatcher {

	/**
	 * Constructs a new 3D object.
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
		this.isObject3D = true;

		/**
		 * The ID of the 3D object.
		 *
		 * @name Object3D#id
		 * @type {number}
		 * @readonly
		 */
		Object.defineProperty( this, 'id', { value: _object3DId ++ } );

		/**
		 * The UUID of the 3D object.
		 *
		 * @type {string}
		 * @readonly
		 */
		this.uuid = generateUUID();

		/**
		 * The name of the 3D object.
		 *
		 * @type {string}
		 */
		this.name = '';

		/**
		 * The type property is used for detecting the object type
		 * in context of serialization/deserialization.
		 *
		 * @type {string}
		 * @readonly
		 */
		this.type = 'Object3D';

		/**
		 * A reference to the parent object.
		 *
		 * @type {?Object3D}
		 * @default null
		 */
		this.parent = null;

		/**
		 * An array holding the child 3D objects of this instance.
		 *
		 * @type {Array<Object3D>}
		 */
		this.children = [];

		/**
		 * Defines the `up` direction of the 3D object which influences
		 * the orientation via methods like {@link Object3D#lookAt}.
		 *
		 * The default values for all 3D objects is defined by `Object3D.DEFAULT_UP`.
		 *
		 * @type {Vector3}
		 */
		this.up = Object3D.DEFAULT_UP.clone();

		const position = new Vector3();
		const rotation = new Euler();
		const quaternion = new Quaternion();
		const scale = new Vector3( 1, 1, 1 );

		function onRotationChange() {

			quaternion.setFromEuler( rotation, false );

		}

		function onQuaternionChange() {

			rotation.setFromQuaternion( quaternion, undefined, false );

		}

		rotation._onChange( onRotationChange );
		quaternion._onChange( onQuaternionChange );

		Object.defineProperties( this, {
			/**
			 * Represents the object's local position.
			 *
			 * @name Object3D#position
			 * @type {Vector3}
			 * @default (0,0,0)
			 */
			position: {
				configurable: true,
				enumerable: true,
				value: position
			},
			/**
			 * Represents the object's local rotation as Euler angles, in radians.
			 *
			 * @name Object3D#rotation
			 * @type {Euler}
			 * @default (0,0,0)
			 */
			rotation: {
				configurable: true,
				enumerable: true,
				value: rotation
			},
			/**
			 * Represents the object's local rotation as Quaternions.
			 *
			 * @name Object3D#quaternion
			 * @type {Quaternion}
			 */
			quaternion: {
				configurable: true,
				enumerable: true,
				value: quaternion
			},
			/**
			 * Represents the object's local scale.
			 *
			 * @name Object3D#scale
			 * @type {Vector3}
			 * @default (1,1,1)
			 */
			scale: {
				configurable: true,
				enumerable: true,
				value: scale
			},
			/**
			 * Represents the object's model-view matrix.
			 *
			 * @name Object3D#modelViewMatrix
			 * @type {Matrix4}
			 */
			modelViewMatrix: {
				value: new Matrix4()
			},
			/**
			 * Represents the object's normal matrix.
			 *
			 * @name Object3D#normalMatrix
			 * @type {Matrix3}
			 */
			normalMatrix: {
				value: new Matrix3()
			}
		} );

		/**
		 * Represents the object's transformation matrix in local space.
		 *
		 * @type {Matrix4}
		 */
		this.matrix = new Matrix4();

		/**
		 * Represents the object's transformation matrix in world space.
		 * If the 3D object has no parent, then it's identical to the local transformation matrix
		 *
		 * @type {Matrix4}
		 */
		this.matrixWorld = new Matrix4();

		/**
		 * When set to `true`, the engine automatically computes the local matrix from position,
		 * rotation and scale every frame.
		 *
		 * The default values for all 3D objects is defined by `Object3D.DEFAULT_MATRIX_AUTO_UPDATE`.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.matrixAutoUpdate = Object3D.DEFAULT_MATRIX_AUTO_UPDATE;

		/**
		 * When set to `true`, the engine automatically computes the world matrix from the current local
		 * matrix and the object's transformation hierarchy.
		 *
		 * The default values for all 3D objects is defined by `Object3D.DEFAULT_MATRIX_WORLD_AUTO_UPDATE`.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.matrixWorldAutoUpdate = Object3D.DEFAULT_MATRIX_WORLD_AUTO_UPDATE; // checked by the renderer

		/**
		 * When set to `true`, it calculates the world matrix in that frame and resets this property
		 * to `false`.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.matrixWorldNeedsUpdate = false;

		/**
		 * The layer membership of the 3D object. The 3D object is only visible if it has
		 * at least one layer in common with the camera in use. This property can also be
		 * used to filter out unwanted objects in ray-intersection tests when using {@link Raycaster}.
		 *
		 * @type {Layers}
		 */
		this.layers = new Layers();

		/**
		 * When set to `true`, the 3D object gets rendered.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.visible = true;

		/**
		 * When set to `true`, the 3D object gets rendered into shadow maps.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.castShadow = false;

		/**
		 * When set to `true`, the 3D object is affected by shadows in the scene.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.receiveShadow = false;

		/**
		 * When set to `true`, the 3D object is honored by view frustum culling.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.frustumCulled = true;

		/**
		 * This value allows the default rendering order of scene graph objects to be
		 * overridden although opaque and transparent objects remain sorted independently.
		 * When this property is set for an instance of {@link Group},all descendants
		 * objects will be sorted and rendered together. Sorting is from lowest to highest
		 * render order.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.renderOrder = 0;

		/**
		 * An array holding the animation clips of the 3D object.
		 *
		 * @type {Array<AnimationClip>}
		 */
		this.animations = [];

		/**
		 * Custom depth material to be used when rendering to the depth map. Can only be used
		 * in context of meshes. When shadow-casting with a {@link DirectionalLight} or {@link SpotLight},
		 * if you are modifying vertex positions in the vertex shader you must specify a custom depth
		 * material for proper shadows.
		 *
		 * Only relevant in context of {@link WebGLRenderer}.
		 *
		 * @type {(Material|undefined)}
		 * @default undefined
		 */
		this.customDepthMaterial = undefined;

		/**
		 * Same as {@link Object3D#customDepthMaterial}, but used with {@link PointLight}.
		 *
		 * Only relevant in context of {@link WebGLRenderer}.
		 *
		 * @type {(Material|undefined)}
		 * @default undefined
		 */
		this.customDistanceMaterial = undefined;

		/**
		 * An object that can be used to store custom data about the 3D object. It
		 * should not hold references to functions as these will not be cloned.
		 *
		 * @type {Object}
		 */
		this.userData = {};

	}

	/**
	 * A callback that is executed immediately before a 3D object is rendered to a shadow map.
	 *
	 * @param {Renderer|WebGLRenderer} renderer - The renderer.
	 * @param {Object3D} object - The 3D object.
	 * @param {Camera} camera - The camera that is used to render the scene.
	 * @param {Camera} shadowCamera - The shadow camera.
	 * @param {BufferGeometry} geometry - The 3D object's geometry.
	 * @param {Material} depthMaterial - The depth material.
	 * @param {Object} group - The geometry group data.
	 */
	onBeforeShadow( /* renderer, object, camera, shadowCamera, geometry, depthMaterial, group */ ) {}

	/**
	 * A callback that is executed immediately after a 3D object is rendered to a shadow map.
	 *
	 * @param {Renderer|WebGLRenderer} renderer - The renderer.
	 * @param {Object3D} object - The 3D object.
	 * @param {Camera} camera - The camera that is used to render the scene.
	 * @param {Camera} shadowCamera - The shadow camera.
	 * @param {BufferGeometry} geometry - The 3D object's geometry.
	 * @param {Material} depthMaterial - The depth material.
	 * @param {Object} group - The geometry group data.
	 */
	onAfterShadow( /* renderer, object, camera, shadowCamera, geometry, depthMaterial, group */ ) {}

	/**
	 * A callback that is executed immediately before a 3D object is rendered.
	 *
	 * @param {Renderer|WebGLRenderer} renderer - The renderer.
	 * @param {Object3D} object - The 3D object.
	 * @param {Camera} camera - The camera that is used to render the scene.
	 * @param {BufferGeometry} geometry - The 3D object's geometry.
	 * @param {Material} material - The 3D object's material.
	 * @param {Object} group - The geometry group data.
	 */
	onBeforeRender( /* renderer, scene, camera, geometry, material, group */ ) {}

	/**
	 * A callback that is executed immediately after a 3D object is rendered.
	 *
	 * @param {Renderer|WebGLRenderer} renderer - The renderer.
	 * @param {Object3D} object - The 3D object.
	 * @param {Camera} camera - The camera that is used to render the scene.
	 * @param {BufferGeometry} geometry - The 3D object's geometry.
	 * @param {Material} material - The 3D object's material.
	 * @param {Object} group - The geometry group data.
	 */
	onAfterRender( /* renderer, scene, camera, geometry, material, group */ ) {}

	/**
	 * Applies the given transformation matrix to the object and updates the object's position,
	 * rotation and scale.
	 *
	 * @param {Matrix4} matrix - The transformation matrix.
	 */
	applyMatrix4( matrix ) {

		if ( this.matrixAutoUpdate ) this.updateMatrix();

		this.matrix.premultiply( matrix );

		this.matrix.decompose( this.position, this.quaternion, this.scale );

	}

	/**
	 * Applies a rotation represented by given the quaternion to the 3D object.
	 *
	 * @param {Quaternion} q - The quaternion.
	 * @return {Object3D} A reference to this instance.
	 */
	applyQuaternion( q ) {

		this.quaternion.premultiply( q );

		return this;

	}

	/**
	 * Sets the given rotation represented as an axis/angle couple to the 3D object.
	 *
	 * @param {Vector3} axis - The (normalized) axis vector.
	 * @param {number} angle - The angle in radians.
	 */
	setRotationFromAxisAngle( axis, angle ) {

		// assumes axis is normalized

		this.quaternion.setFromAxisAngle( axis, angle );

	}

	/**
	 * Sets the given rotation represented as Euler angles to the 3D object.
	 *
	 * @param {Euler} euler - The Euler angles.
	 */
	setRotationFromEuler( euler ) {

		this.quaternion.setFromEuler( euler, true );

	}

	/**
	 * Sets the given rotation represented as rotation matrix to the 3D object.
	 *
	 * @param {Matrix4} m - Although a 4x4 matrix is expected, the upper 3x3 portion must be
	 * a pure rotation matrix (i.e, unscaled).
	 */
	setRotationFromMatrix( m ) {

		// assumes the upper 3x3 of m is a pure rotation matrix (i.e, unscaled)

		this.quaternion.setFromRotationMatrix( m );

	}

	/**
	 * Sets the given rotation represented as a Quaternion to the 3D object.
	 *
	 * @param {Quaternion} q - The Quaternion
	 */
	setRotationFromQuaternion( q ) {

		// assumes q is normalized

		this.quaternion.copy( q );

	}

	/**
	 * Rotates the 3D object along an axis in local space.
	 *
	 * @param {Vector3} axis - The (normalized) axis vector.
	 * @param {number} angle - The angle in radians.
	 * @return {Object3D} A reference to this instance.
	 */
	rotateOnAxis( axis, angle ) {

		// rotate object on axis in object space
		// axis is assumed to be normalized

		_q1.setFromAxisAngle( axis, angle );

		this.quaternion.multiply( _q1 );

		return this;

	}

	/**
	 * Rotates the 3D object along an axis in world space.
	 *
	 * @param {Vector3} axis - The (normalized) axis vector.
	 * @param {number} angle - The angle in radians.
	 * @return {Object3D} A reference to this instance.
	 */
	rotateOnWorldAxis( axis, angle ) {

		// rotate object on axis in world space
		// axis is assumed to be normalized
		// method assumes no rotated parent

		_q1.setFromAxisAngle( axis, angle );

		this.quaternion.premultiply( _q1 );

		return this;

	}

	/**
	 * Rotates the 3D object around its X axis in local space.
	 *
	 * @param {number} angle - The angle in radians.
	 * @return {Object3D} A reference to this instance.
	 */
	rotateX( angle ) {

		return this.rotateOnAxis( _xAxis, angle );

	}

	/**
	 * Rotates the 3D object around its Y axis in local space.
	 *
	 * @param {number} angle - The angle in radians.
	 * @return {Object3D} A reference to this instance.
	 */
	rotateY( angle ) {

		return this.rotateOnAxis( _yAxis, angle );

	}

	/**
	 * Rotates the 3D object around its Z axis in local space.
	 *
	 * @param {number} angle - The angle in radians.
	 * @return {Object3D} A reference to this instance.
	 */
	rotateZ( angle ) {

		return this.rotateOnAxis( _zAxis, angle );

	}

	/**
	 * Translate the 3D object by a distance along the given axis in local space.
	 *
	 * @param {Vector3} axis - The (normalized) axis vector.
	 * @param {number} distance - The distance in world units.
	 * @return {Object3D} A reference to this instance.
	 */
	translateOnAxis( axis, distance ) {

		// translate object by distance along axis in object space
		// axis is assumed to be normalized

		_v1.copy( axis ).applyQuaternion( this.quaternion );

		this.position.add( _v1.multiplyScalar( distance ) );

		return this;

	}

	/**
	 * Translate the 3D object by a distance along its X-axis in local space.
	 *
	 * @param {number} distance - The distance in world units.
	 * @return {Object3D} A reference to this instance.
	 */
	translateX( distance ) {

		return this.translateOnAxis( _xAxis, distance );

	}

	/**
	 * Translate the 3D object by a distance along its Y-axis in local space.
	 *
	 * @param {number} distance - The distance in world units.
	 * @return {Object3D} A reference to this instance.
	 */
	translateY( distance ) {

		return this.translateOnAxis( _yAxis, distance );

	}

	/**
	 * Translate the 3D object by a distance along its Z-axis in local space.
	 *
	 * @param {number} distance - The distance in world units.
	 * @return {Object3D} A reference to this instance.
	 */
	translateZ( distance ) {

		return this.translateOnAxis( _zAxis, distance );

	}

	/**
	 * Converts the given vector from this 3D object's local space to world space.
	 *
	 * @param {Vector3} vector - The vector to convert.
	 * @return {Vector3} The converted vector.
	 */
	localToWorld( vector ) {

		this.updateWorldMatrix( true, false );

		return vector.applyMatrix4( this.matrixWorld );

	}

	/**
	 * Converts the given vector from this 3D object's word space to local space.
	 *
	 * @param {Vector3} vector - The vector to convert.
	 * @return {Vector3} The converted vector.
	 */
	worldToLocal( vector ) {

		this.updateWorldMatrix( true, false );

		return vector.applyMatrix4( _m1.copy( this.matrixWorld ).invert() );

	}

	/**
	 * Rotates the object to face a point in world space.
	 *
	 * This method does not support objects having non-uniformly-scaled parent(s).
	 *
	 * @param {number|Vector3} x - The x coordinate in world space. Alternatively, a vector representing a position in world space
	 * @param {number} [y] - The y coordinate in world space.
	 * @param {number} [z] - The z coordinate in world space.
	 */
	lookAt( x, y, z ) {

		// This method does not support objects having non-uniformly-scaled parent(s)

		if ( x.isVector3 ) {

			_target.copy( x );

		} else {

			_target.set( x, y, z );

		}

		const parent = this.parent;

		this.updateWorldMatrix( true, false );

		_position.setFromMatrixPosition( this.matrixWorld );

		if ( this.isCamera || this.isLight ) {

			_m1.lookAt( _position, _target, this.up );

		} else {

			_m1.lookAt( _target, _position, this.up );

		}

		this.quaternion.setFromRotationMatrix( _m1 );

		if ( parent ) {

			_m1.extractRotation( parent.matrixWorld );
			_q1.setFromRotationMatrix( _m1 );
			this.quaternion.premultiply( _q1.invert() );

		}

	}

	/**
	 * Adds the given 3D object as a child to this 3D object. An arbitrary number of
	 * objects may be added. Any current parent on an object passed in here will be
	 * removed, since an object can have at most one parent.
	 *
	 * @fires Object3D#added
	 * @fires Object3D#childadded
	 * @param {Object3D} object - The 3D object to add.
	 * @return {Object3D} A reference to this instance.
	 */
	add( object ) {

		if ( arguments.length > 1 ) {

			for ( let i = 0; i < arguments.length; i ++ ) {

				this.add( arguments[ i ] );

			}

			return this;

		}

		if ( object === this ) {

			console.error( 'THREE.Object3D.add: object can\'t be added as a child of itself.', object );
			return this;

		}

		if ( object && object.isObject3D ) {

			object.removeFromParent();
			object.parent = this;
			this.children.push( object );

			object.dispatchEvent( _addedEvent );

			_childaddedEvent.child = object;
			this.dispatchEvent( _childaddedEvent );
			_childaddedEvent.child = null;

		} else {

			console.error( 'THREE.Object3D.add: object not an instance of THREE.Object3D.', object );

		}

		return this;

	}

	/**
	 * Removes the given 3D object as child from this 3D object.
	 * An arbitrary number of objects may be removed.
	 *
	 * @fires Object3D#removed
	 * @fires Object3D#childremoved
	 * @param {Object3D} object - The 3D object to remove.
	 * @return {Object3D} A reference to this instance.
	 */
	remove( object ) {

		if ( arguments.length > 1 ) {

			for ( let i = 0; i < arguments.length; i ++ ) {

				this.remove( arguments[ i ] );

			}

			return this;

		}

		const index = this.children.indexOf( object );

		if ( index !== - 1 ) {

			object.parent = null;
			this.children.splice( index, 1 );

			object.dispatchEvent( _removedEvent );

			_childremovedEvent.child = object;
			this.dispatchEvent( _childremovedEvent );
			_childremovedEvent.child = null;

		}

		return this;

	}

	/**
	 * Removes this 3D object from its current parent.
	 *
	 * @fires Object3D#removed
	 * @fires Object3D#childremoved
	 * @return {Object3D} A reference to this instance.
	 */
	removeFromParent() {

		const parent = this.parent;

		if ( parent !== null ) {

			parent.remove( this );

		}

		return this;

	}

	/**
	 * Removes all child objects.
	 *
	 * @fires Object3D#removed
	 * @fires Object3D#childremoved
	 * @return {Object3D} A reference to this instance.
	 */
	clear() {

		return this.remove( ... this.children );

	}

	/**
	 * Adds the given 3D object as a child of this 3D object, while maintaining the object's world
	 * transform. This method does not support scene graphs having non-uniformly-scaled nodes(s).
	 *
	 * @fires Object3D#added
	 * @fires Object3D#childadded
	 * @param {Object3D} object - The 3D object to attach.
	 * @return {Object3D} A reference to this instance.
	 */
	attach( object ) {

		// adds object as a child of this, while maintaining the object's world transform

		// Note: This method does not support scene graphs having non-uniformly-scaled nodes(s)

		this.updateWorldMatrix( true, false );

		_m1.copy( this.matrixWorld ).invert();

		if ( object.parent !== null ) {

			object.parent.updateWorldMatrix( true, false );

			_m1.multiply( object.parent.matrixWorld );

		}

		object.applyMatrix4( _m1 );

		object.removeFromParent();
		object.parent = this;
		this.children.push( object );

		object.updateWorldMatrix( false, true );

		object.dispatchEvent( _addedEvent );

		_childaddedEvent.child = object;
		this.dispatchEvent( _childaddedEvent );
		_childaddedEvent.child = null;

		return this;

	}

	/**
	 * Searches through the 3D object and its children, starting with the 3D object
	 * itself, and returns the first with a matching ID.
	 *
	 * @param {number} id - The id.
	 * @return {Object3D|undefined} The found 3D object. Returns `undefined` if no 3D object has been found.
	 */
	getObjectById( id ) {

		return this.getObjectByProperty( 'id', id );

	}

	/**
	 * Searches through the 3D object and its children, starting with the 3D object
	 * itself, and returns the first with a matching name.
	 *
	 * @param {string} name - The name.
	 * @return {Object3D|undefined} The found 3D object. Returns `undefined` if no 3D object has been found.
	 */
	getObjectByName( name ) {

		return this.getObjectByProperty( 'name', name );

	}

	/**
	 * Searches through the 3D object and its children, starting with the 3D object
	 * itself, and returns the first with a matching property value.
	 *
	 * @param {string} name - The name of the property.
	 * @param {any} value - The value.
	 * @return {Object3D|undefined} The found 3D object. Returns `undefined` if no 3D object has been found.
	 */
	getObjectByProperty( name, value ) {

		if ( this[ name ] === value ) return this;

		for ( let i = 0, l = this.children.length; i < l; i ++ ) {

			const child = this.children[ i ];
			const object = child.getObjectByProperty( name, value );

			if ( object !== undefined ) {

				return object;

			}

		}

		return undefined;

	}

	/**
	 * Searches through the 3D object and its children, starting with the 3D object
	 * itself, and returns all 3D objects with a matching property value.
	 *
	 * @param {string} name - The name of the property.
	 * @param {any} value - The value.
	 * @param {Array<Object3D>} result - The method stores the result in this array.
	 * @return {Array<Object3D>} The found 3D objects.
	 */
	getObjectsByProperty( name, value, result = [] ) {

		if ( this[ name ] === value ) result.push( this );

		const children = this.children;

		for ( let i = 0, l = children.length; i < l; i ++ ) {

			children[ i ].getObjectsByProperty( name, value, result );

		}

		return result;

	}

	/**
	 * Returns a vector representing the position of the 3D object in world space.
	 *
	 * @param {Vector3} target - The target vector the result is stored to.
	 * @return {Vector3} The 3D object's position in world space.
	 */
	getWorldPosition( target ) {

		this.updateWorldMatrix( true, false );

		return target.setFromMatrixPosition( this.matrixWorld );

	}

	/**
	 * Returns a Quaternion representing the position of the 3D object in world space.
	 *
	 * @param {Quaternion} target - The target Quaternion the result is stored to.
	 * @return {Quaternion} The 3D object's rotation in world space.
	 */
	getWorldQuaternion( target ) {

		this.updateWorldMatrix( true, false );

		this.matrixWorld.decompose( _position, target, _scale );

		return target;

	}

	/**
	 * Returns a vector representing the scale of the 3D object in world space.
	 *
	 * @param {Vector3} target - The target vector the result is stored to.
	 * @return {Vector3} The 3D object's scale in world space.
	 */
	getWorldScale( target ) {

		this.updateWorldMatrix( true, false );

		this.matrixWorld.decompose( _position, _quaternion, target );

		return target;

	}

	/**
	 * Returns a vector representing the ("look") direction of the 3D object in world space.
	 *
	 * @param {Vector3} target - The target vector the result is stored to.
	 * @return {Vector3} The 3D object's direction in world space.
	 */
	getWorldDirection( target ) {

		this.updateWorldMatrix( true, false );

		const e = this.matrixWorld.elements;

		return target.set( e[ 8 ], e[ 9 ], e[ 10 ] ).normalize();

	}

	/**
	 * Abstract method to get intersections between a casted ray and this
	 * 3D object. Renderable 3D objects such as {@link Mesh}, {@link Line} or {@link Points}
	 * implement this method in order to use raycasting.
	 *
	 * @abstract
	 * @param {Raycaster} raycaster - The raycaster.
	 * @param {Array<Object>} intersects - An array holding the result of the method.
	 */
	raycast( /* raycaster, intersects */ ) {}

	/**
	 * Executes the callback on this 3D object and all descendants.
	 *
	 * Note: Modifying the scene graph inside the callback is discouraged.
	 *
	 * @param {Function} callback - A callback function that allows to process the current 3D object.
	 */
	traverse( callback ) {

		callback( this );

		const children = this.children;

		for ( let i = 0, l = children.length; i < l; i ++ ) {

			children[ i ].traverse( callback );

		}

	}

	/**
	 * Like {@link Object3D#traverse}, but the callback will only be executed for visible 3D objects.
	 * Descendants of invisible 3D objects are not traversed.
	 *
	 * Note: Modifying the scene graph inside the callback is discouraged.
	 *
	 * @param {Function} callback - A callback function that allows to process the current 3D object.
	 */
	traverseVisible( callback ) {

		if ( this.visible === false ) return;

		callback( this );

		const children = this.children;

		for ( let i = 0, l = children.length; i < l; i ++ ) {

			children[ i ].traverseVisible( callback );

		}

	}

	/**
	 * Like {@link Object3D#traverse}, but the callback will only be executed for all ancestors.
	 *
	 * Note: Modifying the scene graph inside the callback is discouraged.
	 *
	 * @param {Function} callback - A callback function that allows to process the current 3D object.
	 */
	traverseAncestors( callback ) {

		const parent = this.parent;

		if ( parent !== null ) {

			callback( parent );

			parent.traverseAncestors( callback );

		}

	}

	/**
	 * Updates the transformation matrix in local space by computing it from the current
	 * position, rotation and scale values.
	 */
	updateMatrix() {

		this.matrix.compose( this.position, this.quaternion, this.scale );

		this.matrixWorldNeedsUpdate = true;

	}

	/**
	 * Updates the transformation matrix in world space of this 3D objects and its descendants.
	 *
	 * To ensure correct results, this method also recomputes the 3D object's transformation matrix in
	 * local space. The computation of the local and world matrix can be controlled with the
	 * {@link Object3D#matrixAutoUpdate} and {@link Object3D#matrixWorldAutoUpdate} flags which are both
	 * `true` by default.  Set these flags to `false` if you need more control over the update matrix process.
	 *
	 * @param {boolean} [force=false] - When set to `true`, a recomputation of world matrices is forced even
	 * when {@link Object3D#matrixWorldAutoUpdate} is set to `false`.
	 */
	updateMatrixWorld( force ) {

		if ( this.matrixAutoUpdate ) this.updateMatrix();

		if ( this.matrixWorldNeedsUpdate || force ) {

			if ( this.matrixWorldAutoUpdate === true ) {

				if ( this.parent === null ) {

					this.matrixWorld.copy( this.matrix );

				} else {

					this.matrixWorld.multiplyMatrices( this.parent.matrixWorld, this.matrix );

				}

			}

			this.matrixWorldNeedsUpdate = false;

			force = true;

		}

		// make sure descendants are updated if required

		const children = this.children;

		for ( let i = 0, l = children.length; i < l; i ++ ) {

			const child = children[ i ];

			child.updateMatrixWorld( force );

		}

	}

	/**
	 * An alternative version of {@link Object3D#updateMatrixWorld} with more control over the
	 * update of ancestor and descendant nodes.
	 *
	 * @param {boolean} [updateParents=false] Whether ancestor nodes should be updated or not.
	 * @param {boolean} [updateChildren=false] Whether descendant nodes should be updated or not.
	 */
	updateWorldMatrix( updateParents, updateChildren ) {

		const parent = this.parent;

		if ( updateParents === true && parent !== null ) {

			parent.updateWorldMatrix( true, false );

		}

		if ( this.matrixAutoUpdate ) this.updateMatrix();

		if ( this.matrixWorldAutoUpdate === true ) {

			if ( this.parent === null ) {

				this.matrixWorld.copy( this.matrix );

			} else {

				this.matrixWorld.multiplyMatrices( this.parent.matrixWorld, this.matrix );

			}

		}

		// make sure descendants are updated

		if ( updateChildren === true ) {

			const children = this.children;

			for ( let i = 0, l = children.length; i < l; i ++ ) {

				const child = children[ i ];

				child.updateWorldMatrix( false, true );

			}

		}

	}

	/**
	 * Serializes the 3D object into JSON.
	 *
	 * @param {?(Object|string)} meta - An optional value holding meta information about the serialization.
	 * @return {Object} A JSON object representing the serialized 3D object.
	 * @see {@link ObjectLoader#parse}
	 */
	toJSON( meta ) {

		// meta is a string when called from JSON.stringify
		const isRootObject = ( meta === undefined || typeof meta === 'string' );

		const output = {};

		// meta is a hash used to collect geometries, materials.
		// not providing it implies that this is the root object
		// being serialized.
		if ( isRootObject ) {

			// initialize meta obj
			meta = {
				geometries: {},
				materials: {},
				textures: {},
				images: {},
				shapes: {},
				skeletons: {},
				animations: {},
				nodes: {}
			};

			output.metadata = {
				version: 4.7,
				type: 'Object',
				generator: 'Object3D.toJSON'
			};

		}

		// standard Object3D serialization

		const object = {};

		object.uuid = this.uuid;
		object.type = this.type;

		if ( this.name !== '' ) object.name = this.name;
		if ( this.castShadow === true ) object.castShadow = true;
		if ( this.receiveShadow === true ) object.receiveShadow = true;
		if ( this.visible === false ) object.visible = false;
		if ( this.frustumCulled === false ) object.frustumCulled = false;
		if ( this.renderOrder !== 0 ) object.renderOrder = this.renderOrder;
		if ( Object.keys( this.userData ).length > 0 ) object.userData = this.userData;

		object.layers = this.layers.mask;
		object.matrix = this.matrix.toArray();
		object.up = this.up.toArray();

		if ( this.matrixAutoUpdate === false ) object.matrixAutoUpdate = false;

		// object specific properties

		if ( this.isInstancedMesh ) {

			object.type = 'InstancedMesh';
			object.count = this.count;
			object.instanceMatrix = this.instanceMatrix.toJSON();
			if ( this.instanceColor !== null ) object.instanceColor = this.instanceColor.toJSON();

		}

		if ( this.isBatchedMesh ) {

			object.type = 'BatchedMesh';
			object.perObjectFrustumCulled = this.perObjectFrustumCulled;
			object.sortObjects = this.sortObjects;

			object.drawRanges = this._drawRanges;
			object.reservedRanges = this._reservedRanges;

			object.geometryInfo = this._geometryInfo.map( info => ( {
				...info,
				boundingBox: info.boundingBox ? info.boundingBox.toJSON() : undefined,
				boundingSphere: info.boundingSphere ? info.boundingSphere.toJSON() : undefined
			} ) );
			object.instanceInfo = this._instanceInfo.map( info => ( { ...info } ) );

			object.availableInstanceIds = this._availableInstanceIds.slice();
			object.availableGeometryIds = this._availableGeometryIds.slice();

			object.nextIndexStart = this._nextIndexStart;
			object.nextVertexStart = this._nextVertexStart;
			object.geometryCount = this._geometryCount;

			object.maxInstanceCount = this._maxInstanceCount;
			object.maxVertexCount = this._maxVertexCount;
			object.maxIndexCount = this._maxIndexCount;

			object.geometryInitialized = this._geometryInitialized;

			object.matricesTexture = this._matricesTexture.toJSON( meta );

			object.indirectTexture = this._indirectTexture.toJSON( meta );

			if ( this._colorsTexture !== null ) {

				object.colorsTexture = this._colorsTexture.toJSON( meta );

			}

			if ( this.boundingSphere !== null ) {

				object.boundingSphere = this.boundingSphere.toJSON();

			}

			if ( this.boundingBox !== null ) {

				object.boundingBox = this.boundingBox.toJSON();

			}

		}

		//

		function serialize( library, element ) {

			if ( library[ element.uuid ] === undefined ) {

				library[ element.uuid ] = element.toJSON( meta );

			}

			return element.uuid;

		}

		if ( this.isScene ) {

			if ( this.background ) {

				if ( this.background.isColor ) {

					object.background = this.background.toJSON();

				} else if ( this.background.isTexture ) {

					object.background = this.background.toJSON( meta ).uuid;

				}

			}

			if ( this.environment && this.environment.isTexture && this.environment.isRenderTargetTexture !== true ) {

				object.environment = this.environment.toJSON( meta ).uuid;

			}

		} else if ( this.isMesh || this.isLine || this.isPoints ) {

			object.geometry = serialize( meta.geometries, this.geometry );

			const parameters = this.geometry.parameters;

			if ( parameters !== undefined && parameters.shapes !== undefined ) {

				const shapes = parameters.shapes;

				if ( Array.isArray( shapes ) ) {

					for ( let i = 0, l = shapes.length; i < l; i ++ ) {

						const shape = shapes[ i ];

						serialize( meta.shapes, shape );

					}

				} else {

					serialize( meta.shapes, shapes );

				}

			}

		}

		if ( this.isSkinnedMesh ) {

			object.bindMode = this.bindMode;
			object.bindMatrix = this.bindMatrix.toArray();

			if ( this.skeleton !== undefined ) {

				serialize( meta.skeletons, this.skeleton );

				object.skeleton = this.skeleton.uuid;

			}

		}

		if ( this.material !== undefined ) {

			if ( Array.isArray( this.material ) ) {

				const uuids = [];

				for ( let i = 0, l = this.material.length; i < l; i ++ ) {

					uuids.push( serialize( meta.materials, this.material[ i ] ) );

				}

				object.material = uuids;

			} else {

				object.material = serialize( meta.materials, this.material );

			}

		}

		//

		if ( this.children.length > 0 ) {

			object.children = [];

			for ( let i = 0; i < this.children.length; i ++ ) {

				object.children.push( this.children[ i ].toJSON( meta ).object );

			}

		}

		//

		if ( this.animations.length > 0 ) {

			object.animations = [];

			for ( let i = 0; i < this.animations.length; i ++ ) {

				const animation = this.animations[ i ];

				object.animations.push( serialize( meta.animations, animation ) );

			}

		}

		if ( isRootObject ) {

			const geometries = extractFromCache( meta.geometries );
			const materials = extractFromCache( meta.materials );
			const textures = extractFromCache( meta.textures );
			const images = extractFromCache( meta.images );
			const shapes = extractFromCache( meta.shapes );
			const skeletons = extractFromCache( meta.skeletons );
			const animations = extractFromCache( meta.animations );
			const nodes = extractFromCache( meta.nodes );

			if ( geometries.length > 0 ) output.geometries = geometries;
			if ( materials.length > 0 ) output.materials = materials;
			if ( textures.length > 0 ) output.textures = textures;
			if ( images.length > 0 ) output.images = images;
			if ( shapes.length > 0 ) output.shapes = shapes;
			if ( skeletons.length > 0 ) output.skeletons = skeletons;
			if ( animations.length > 0 ) output.animations = animations;
			if ( nodes.length > 0 ) output.nodes = nodes;

		}

		output.object = object;

		return output;

		// extract data from the cache hash
		// remove metadata on each item
		// and return as array
		function extractFromCache( cache ) {

			const values = [];
			for ( const key in cache ) {

				const data = cache[ key ];
				delete data.metadata;
				values.push( data );

			}

			return values;

		}

	}

	/**
	 * Returns a new 3D object with copied values from this instance.
	 *
	 * @param {boolean} [recursive=true] - When set to `true`, descendants of the 3D object are also cloned.
	 * @return {Object3D} A clone of this instance.
	 */
	clone( recursive ) {

		return new this.constructor().copy( this, recursive );

	}

	/**
	 * Copies the values of the given 3D object to this instance.
	 *
	 * @param {Object3D} source - The 3D object to copy.
	 * @param {boolean} [recursive=true] - When set to `true`, descendants of the 3D object are cloned.
	 * @return {Object3D} A reference to this instance.
	 */
	copy( source, recursive = true ) {

		this.name = source.name;

		this.up.copy( source.up );

		this.position.copy( source.position );
		this.rotation.order = source.rotation.order;
		this.quaternion.copy( source.quaternion );
		this.scale.copy( source.scale );

		this.matrix.copy( source.matrix );
		this.matrixWorld.copy( source.matrixWorld );

		this.matrixAutoUpdate = source.matrixAutoUpdate;

		this.matrixWorldAutoUpdate = source.matrixWorldAutoUpdate;
		this.matrixWorldNeedsUpdate = source.matrixWorldNeedsUpdate;

		this.layers.mask = source.layers.mask;
		this.visible = source.visible;

		this.castShadow = source.castShadow;
		this.receiveShadow = source.receiveShadow;

		this.frustumCulled = source.frustumCulled;
		this.renderOrder = source.renderOrder;

		this.animations = source.animations.slice();

		this.userData = JSON.parse( JSON.stringify( source.userData ) );

		if ( recursive === true ) {

			for ( let i = 0; i < source.children.length; i ++ ) {

				const child = source.children[ i ];
				this.add( child.clone() );

			}

		}

		return this;

	}

}
```
</details>

#### Methods

##### `onBeforeShadow(): void`

<details><summary>Code</summary>

```ts
onBeforeShadow( /* renderer, object, camera, shadowCamera, geometry, depthMaterial, group */ ) {}
```
</details>

##### `onAfterShadow(): void`

<details><summary>Code</summary>

```ts
onAfterShadow( /* renderer, object, camera, shadowCamera, geometry, depthMaterial, group */ ) {}
```
</details>

##### `onBeforeRender(): void`

<details><summary>Code</summary>

```ts
onBeforeRender( /* renderer, scene, camera, geometry, material, group */ ) {}
```
</details>

##### `onAfterRender(): void`

<details><summary>Code</summary>

```ts
onAfterRender( /* renderer, scene, camera, geometry, material, group */ ) {}
```
</details>

##### `applyMatrix4(matrix: Matrix4): void`

<details><summary>Code</summary>

```ts
applyMatrix4( matrix ) {

		if ( this.matrixAutoUpdate ) this.updateMatrix();

		this.matrix.premultiply( matrix );

		this.matrix.decompose( this.position, this.quaternion, this.scale );

	}
```
</details>

##### `applyQuaternion(q: Quaternion): Object3D`

<details><summary>Code</summary>

```ts
applyQuaternion( q ) {

		this.quaternion.premultiply( q );

		return this;

	}
```
</details>

##### `setRotationFromAxisAngle(axis: Vector3, angle: number): void`

<details><summary>Code</summary>

```ts
setRotationFromAxisAngle( axis, angle ) {

		// assumes axis is normalized

		this.quaternion.setFromAxisAngle( axis, angle );

	}
```
</details>

##### `setRotationFromEuler(euler: Euler): void`

<details><summary>Code</summary>

```ts
setRotationFromEuler( euler ) {

		this.quaternion.setFromEuler( euler, true );

	}
```
</details>

##### `setRotationFromMatrix(m: Matrix4): void`

<details><summary>Code</summary>

```ts
setRotationFromMatrix( m ) {

		// assumes the upper 3x3 of m is a pure rotation matrix (i.e, unscaled)

		this.quaternion.setFromRotationMatrix( m );

	}
```
</details>

##### `setRotationFromQuaternion(q: Quaternion): void`

<details><summary>Code</summary>

```ts
setRotationFromQuaternion( q ) {

		// assumes q is normalized

		this.quaternion.copy( q );

	}
```
</details>

##### `rotateOnAxis(axis: Vector3, angle: number): Object3D`

<details><summary>Code</summary>

```ts
rotateOnAxis( axis, angle ) {

		// rotate object on axis in object space
		// axis is assumed to be normalized

		_q1.setFromAxisAngle( axis, angle );

		this.quaternion.multiply( _q1 );

		return this;

	}
```
</details>

##### `rotateOnWorldAxis(axis: Vector3, angle: number): Object3D`

<details><summary>Code</summary>

```ts
rotateOnWorldAxis( axis, angle ) {

		// rotate object on axis in world space
		// axis is assumed to be normalized
		// method assumes no rotated parent

		_q1.setFromAxisAngle( axis, angle );

		this.quaternion.premultiply( _q1 );

		return this;

	}
```
</details>

##### `rotateX(angle: number): Object3D`

<details><summary>Code</summary>

```ts
rotateX( angle ) {

		return this.rotateOnAxis( _xAxis, angle );

	}
```
</details>

##### `rotateY(angle: number): Object3D`

<details><summary>Code</summary>

```ts
rotateY( angle ) {

		return this.rotateOnAxis( _yAxis, angle );

	}
```
</details>

##### `rotateZ(angle: number): Object3D`

<details><summary>Code</summary>

```ts
rotateZ( angle ) {

		return this.rotateOnAxis( _zAxis, angle );

	}
```
</details>

##### `translateOnAxis(axis: Vector3, distance: number): Object3D`

<details><summary>Code</summary>

```ts
translateOnAxis( axis, distance ) {

		// translate object by distance along axis in object space
		// axis is assumed to be normalized

		_v1.copy( axis ).applyQuaternion( this.quaternion );

		this.position.add( _v1.multiplyScalar( distance ) );

		return this;

	}
```
</details>

##### `translateX(distance: number): Object3D`

<details><summary>Code</summary>

```ts
translateX( distance ) {

		return this.translateOnAxis( _xAxis, distance );

	}
```
</details>

##### `translateY(distance: number): Object3D`

<details><summary>Code</summary>

```ts
translateY( distance ) {

		return this.translateOnAxis( _yAxis, distance );

	}
```
</details>

##### `translateZ(distance: number): Object3D`

<details><summary>Code</summary>

```ts
translateZ( distance ) {

		return this.translateOnAxis( _zAxis, distance );

	}
```
</details>

##### `localToWorld(vector: Vector3): Vector3`

<details><summary>Code</summary>

```ts
localToWorld( vector ) {

		this.updateWorldMatrix( true, false );

		return vector.applyMatrix4( this.matrixWorld );

	}
```
</details>

##### `worldToLocal(vector: Vector3): Vector3`

<details><summary>Code</summary>

```ts
worldToLocal( vector ) {

		this.updateWorldMatrix( true, false );

		return vector.applyMatrix4( _m1.copy( this.matrixWorld ).invert() );

	}
```
</details>

##### `lookAt(x: number | Vector3, y: number, z: number): void`

<details><summary>Code</summary>

```ts
lookAt( x, y, z ) {

		// This method does not support objects having non-uniformly-scaled parent(s)

		if ( x.isVector3 ) {

			_target.copy( x );

		} else {

			_target.set( x, y, z );

		}

		const parent = this.parent;

		this.updateWorldMatrix( true, false );

		_position.setFromMatrixPosition( this.matrixWorld );

		if ( this.isCamera || this.isLight ) {

			_m1.lookAt( _position, _target, this.up );

		} else {

			_m1.lookAt( _target, _position, this.up );

		}

		this.quaternion.setFromRotationMatrix( _m1 );

		if ( parent ) {

			_m1.extractRotation( parent.matrixWorld );
			_q1.setFromRotationMatrix( _m1 );
			this.quaternion.premultiply( _q1.invert() );

		}

	}
```
</details>

##### `add(object: Object3D): Object3D`

<details><summary>Code</summary>

```ts
add( object ) {

		if ( arguments.length > 1 ) {

			for ( let i = 0; i < arguments.length; i ++ ) {

				this.add( arguments[ i ] );

			}

			return this;

		}

		if ( object === this ) {

			console.error( 'THREE.Object3D.add: object can\'t be added as a child of itself.', object );
			return this;

		}

		if ( object && object.isObject3D ) {

			object.removeFromParent();
			object.parent = this;
			this.children.push( object );

			object.dispatchEvent( _addedEvent );

			_childaddedEvent.child = object;
			this.dispatchEvent( _childaddedEvent );
			_childaddedEvent.child = null;

		} else {

			console.error( 'THREE.Object3D.add: object not an instance of THREE.Object3D.', object );

		}

		return this;

	}
```
</details>

##### `remove(object: Object3D): Object3D`

<details><summary>Code</summary>

```ts
remove( object ) {

		if ( arguments.length > 1 ) {

			for ( let i = 0; i < arguments.length; i ++ ) {

				this.remove( arguments[ i ] );

			}

			return this;

		}

		const index = this.children.indexOf( object );

		if ( index !== - 1 ) {

			object.parent = null;
			this.children.splice( index, 1 );

			object.dispatchEvent( _removedEvent );

			_childremovedEvent.child = object;
			this.dispatchEvent( _childremovedEvent );
			_childremovedEvent.child = null;

		}

		return this;

	}
```
</details>

##### `removeFromParent(): Object3D`

<details><summary>Code</summary>

```ts
removeFromParent() {

		const parent = this.parent;

		if ( parent !== null ) {

			parent.remove( this );

		}

		return this;

	}
```
</details>

##### `clear(): Object3D`

<details><summary>Code</summary>

```ts
clear() {

		return this.remove( ... this.children );

	}
```
</details>

##### `attach(object: Object3D): Object3D`

<details><summary>Code</summary>

```ts
attach( object ) {

		// adds object as a child of this, while maintaining the object's world transform

		// Note: This method does not support scene graphs having non-uniformly-scaled nodes(s)

		this.updateWorldMatrix( true, false );

		_m1.copy( this.matrixWorld ).invert();

		if ( object.parent !== null ) {

			object.parent.updateWorldMatrix( true, false );

			_m1.multiply( object.parent.matrixWorld );

		}

		object.applyMatrix4( _m1 );

		object.removeFromParent();
		object.parent = this;
		this.children.push( object );

		object.updateWorldMatrix( false, true );

		object.dispatchEvent( _addedEvent );

		_childaddedEvent.child = object;
		this.dispatchEvent( _childaddedEvent );
		_childaddedEvent.child = null;

		return this;

	}
```
</details>

##### `getObjectById(id: number): Object3D`

<details><summary>Code</summary>

```ts
getObjectById( id ) {

		return this.getObjectByProperty( 'id', id );

	}
```
</details>

##### `getObjectByName(name: string): Object3D`

<details><summary>Code</summary>

```ts
getObjectByName( name ) {

		return this.getObjectByProperty( 'name', name );

	}
```
</details>

##### `getObjectByProperty(name: string, value: any): Object3D`

<details><summary>Code</summary>

```ts
getObjectByProperty( name, value ) {

		if ( this[ name ] === value ) return this;

		for ( let i = 0, l = this.children.length; i < l; i ++ ) {

			const child = this.children[ i ];
			const object = child.getObjectByProperty( name, value );

			if ( object !== undefined ) {

				return object;

			}

		}

		return undefined;

	}
```
</details>

##### `getObjectsByProperty(name: string, value: any, result: Object3D[]): Object3D[]`

<details><summary>Code</summary>

```ts
getObjectsByProperty( name, value, result = [] ) {

		if ( this[ name ] === value ) result.push( this );

		const children = this.children;

		for ( let i = 0, l = children.length; i < l; i ++ ) {

			children[ i ].getObjectsByProperty( name, value, result );

		}

		return result;

	}
```
</details>

##### `getWorldPosition(target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getWorldPosition( target ) {

		this.updateWorldMatrix( true, false );

		return target.setFromMatrixPosition( this.matrixWorld );

	}
```
</details>

##### `getWorldQuaternion(target: Quaternion): Quaternion`

<details><summary>Code</summary>

```ts
getWorldQuaternion( target ) {

		this.updateWorldMatrix( true, false );

		this.matrixWorld.decompose( _position, target, _scale );

		return target;

	}
```
</details>

##### `getWorldScale(target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getWorldScale( target ) {

		this.updateWorldMatrix( true, false );

		this.matrixWorld.decompose( _position, _quaternion, target );

		return target;

	}
```
</details>

##### `getWorldDirection(target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getWorldDirection( target ) {

		this.updateWorldMatrix( true, false );

		const e = this.matrixWorld.elements;

		return target.set( e[ 8 ], e[ 9 ], e[ 10 ] ).normalize();

	}
```
</details>

##### `raycast(): void`

<details><summary>Code</summary>

```ts
raycast( /* raycaster, intersects */ ) {}
```
</details>

##### `traverse(callback: Function): void`

<details><summary>Code</summary>

```ts
traverse( callback ) {

		callback( this );

		const children = this.children;

		for ( let i = 0, l = children.length; i < l; i ++ ) {

			children[ i ].traverse( callback );

		}

	}
```
</details>

##### `traverseVisible(callback: Function): void`

<details><summary>Code</summary>

```ts
traverseVisible( callback ) {

		if ( this.visible === false ) return;

		callback( this );

		const children = this.children;

		for ( let i = 0, l = children.length; i < l; i ++ ) {

			children[ i ].traverseVisible( callback );

		}

	}
```
</details>

##### `traverseAncestors(callback: Function): void`

<details><summary>Code</summary>

```ts
traverseAncestors( callback ) {

		const parent = this.parent;

		if ( parent !== null ) {

			callback( parent );

			parent.traverseAncestors( callback );

		}

	}
```
</details>

##### `updateMatrix(): void`

<details><summary>Code</summary>

```ts
updateMatrix() {

		this.matrix.compose( this.position, this.quaternion, this.scale );

		this.matrixWorldNeedsUpdate = true;

	}
```
</details>

##### `updateMatrixWorld(force: boolean): void`

<details><summary>Code</summary>

```ts
updateMatrixWorld( force ) {

		if ( this.matrixAutoUpdate ) this.updateMatrix();

		if ( this.matrixWorldNeedsUpdate || force ) {

			if ( this.matrixWorldAutoUpdate === true ) {

				if ( this.parent === null ) {

					this.matrixWorld.copy( this.matrix );

				} else {

					this.matrixWorld.multiplyMatrices( this.parent.matrixWorld, this.matrix );

				}

			}

			this.matrixWorldNeedsUpdate = false;

			force = true;

		}

		// make sure descendants are updated if required

		const children = this.children;

		for ( let i = 0, l = children.length; i < l; i ++ ) {

			const child = children[ i ];

			child.updateMatrixWorld( force );

		}

	}
```
</details>

##### `updateWorldMatrix(updateParents: boolean, updateChildren: boolean): void`

<details><summary>Code</summary>

```ts
updateWorldMatrix( updateParents, updateChildren ) {

		const parent = this.parent;

		if ( updateParents === true && parent !== null ) {

			parent.updateWorldMatrix( true, false );

		}

		if ( this.matrixAutoUpdate ) this.updateMatrix();

		if ( this.matrixWorldAutoUpdate === true ) {

			if ( this.parent === null ) {

				this.matrixWorld.copy( this.matrix );

			} else {

				this.matrixWorld.multiplyMatrices( this.parent.matrixWorld, this.matrix );

			}

		}

		// make sure descendants are updated

		if ( updateChildren === true ) {

			const children = this.children;

			for ( let i = 0, l = children.length; i < l; i ++ ) {

				const child = children[ i ];

				child.updateWorldMatrix( false, true );

			}

		}

	}
```
</details>

##### `toJSON(meta: any): any`

<details><summary>Code</summary>

```ts
toJSON( meta ) {

		// meta is a string when called from JSON.stringify
		const isRootObject = ( meta === undefined || typeof meta === 'string' );

		const output = {};

		// meta is a hash used to collect geometries, materials.
		// not providing it implies that this is the root object
		// being serialized.
		if ( isRootObject ) {

			// initialize meta obj
			meta = {
				geometries: {},
				materials: {},
				textures: {},
				images: {},
				shapes: {},
				skeletons: {},
				animations: {},
				nodes: {}
			};

			output.metadata = {
				version: 4.7,
				type: 'Object',
				generator: 'Object3D.toJSON'
			};

		}

		// standard Object3D serialization

		const object = {};

		object.uuid = this.uuid;
		object.type = this.type;

		if ( this.name !== '' ) object.name = this.name;
		if ( this.castShadow === true ) object.castShadow = true;
		if ( this.receiveShadow === true ) object.receiveShadow = true;
		if ( this.visible === false ) object.visible = false;
		if ( this.frustumCulled === false ) object.frustumCulled = false;
		if ( this.renderOrder !== 0 ) object.renderOrder = this.renderOrder;
		if ( Object.keys( this.userData ).length > 0 ) object.userData = this.userData;

		object.layers = this.layers.mask;
		object.matrix = this.matrix.toArray();
		object.up = this.up.toArray();

		if ( this.matrixAutoUpdate === false ) object.matrixAutoUpdate = false;

		// object specific properties

		if ( this.isInstancedMesh ) {

			object.type = 'InstancedMesh';
			object.count = this.count;
			object.instanceMatrix = this.instanceMatrix.toJSON();
			if ( this.instanceColor !== null ) object.instanceColor = this.instanceColor.toJSON();

		}

		if ( this.isBatchedMesh ) {

			object.type = 'BatchedMesh';
			object.perObjectFrustumCulled = this.perObjectFrustumCulled;
			object.sortObjects = this.sortObjects;

			object.drawRanges = this._drawRanges;
			object.reservedRanges = this._reservedRanges;

			object.geometryInfo = this._geometryInfo.map( info => ( {
				...info,
				boundingBox: info.boundingBox ? info.boundingBox.toJSON() : undefined,
				boundingSphere: info.boundingSphere ? info.boundingSphere.toJSON() : undefined
			} ) );
			object.instanceInfo = this._instanceInfo.map( info => ( { ...info } ) );

			object.availableInstanceIds = this._availableInstanceIds.slice();
			object.availableGeometryIds = this._availableGeometryIds.slice();

			object.nextIndexStart = this._nextIndexStart;
			object.nextVertexStart = this._nextVertexStart;
			object.geometryCount = this._geometryCount;

			object.maxInstanceCount = this._maxInstanceCount;
			object.maxVertexCount = this._maxVertexCount;
			object.maxIndexCount = this._maxIndexCount;

			object.geometryInitialized = this._geometryInitialized;

			object.matricesTexture = this._matricesTexture.toJSON( meta );

			object.indirectTexture = this._indirectTexture.toJSON( meta );

			if ( this._colorsTexture !== null ) {

				object.colorsTexture = this._colorsTexture.toJSON( meta );

			}

			if ( this.boundingSphere !== null ) {

				object.boundingSphere = this.boundingSphere.toJSON();

			}

			if ( this.boundingBox !== null ) {

				object.boundingBox = this.boundingBox.toJSON();

			}

		}

		//

		function serialize( library, element ) {

			if ( library[ element.uuid ] === undefined ) {

				library[ element.uuid ] = element.toJSON( meta );

			}

			return element.uuid;

		}

		if ( this.isScene ) {

			if ( this.background ) {

				if ( this.background.isColor ) {

					object.background = this.background.toJSON();

				} else if ( this.background.isTexture ) {

					object.background = this.background.toJSON( meta ).uuid;

				}

			}

			if ( this.environment && this.environment.isTexture && this.environment.isRenderTargetTexture !== true ) {

				object.environment = this.environment.toJSON( meta ).uuid;

			}

		} else if ( this.isMesh || this.isLine || this.isPoints ) {

			object.geometry = serialize( meta.geometries, this.geometry );

			const parameters = this.geometry.parameters;

			if ( parameters !== undefined && parameters.shapes !== undefined ) {

				const shapes = parameters.shapes;

				if ( Array.isArray( shapes ) ) {

					for ( let i = 0, l = shapes.length; i < l; i ++ ) {

						const shape = shapes[ i ];

						serialize( meta.shapes, shape );

					}

				} else {

					serialize( meta.shapes, shapes );

				}

			}

		}

		if ( this.isSkinnedMesh ) {

			object.bindMode = this.bindMode;
			object.bindMatrix = this.bindMatrix.toArray();

			if ( this.skeleton !== undefined ) {

				serialize( meta.skeletons, this.skeleton );

				object.skeleton = this.skeleton.uuid;

			}

		}

		if ( this.material !== undefined ) {

			if ( Array.isArray( this.material ) ) {

				const uuids = [];

				for ( let i = 0, l = this.material.length; i < l; i ++ ) {

					uuids.push( serialize( meta.materials, this.material[ i ] ) );

				}

				object.material = uuids;

			} else {

				object.material = serialize( meta.materials, this.material );

			}

		}

		//

		if ( this.children.length > 0 ) {

			object.children = [];

			for ( let i = 0; i < this.children.length; i ++ ) {

				object.children.push( this.children[ i ].toJSON( meta ).object );

			}

		}

		//

		if ( this.animations.length > 0 ) {

			object.animations = [];

			for ( let i = 0; i < this.animations.length; i ++ ) {

				const animation = this.animations[ i ];

				object.animations.push( serialize( meta.animations, animation ) );

			}

		}

		if ( isRootObject ) {

			const geometries = extractFromCache( meta.geometries );
			const materials = extractFromCache( meta.materials );
			const textures = extractFromCache( meta.textures );
			const images = extractFromCache( meta.images );
			const shapes = extractFromCache( meta.shapes );
			const skeletons = extractFromCache( meta.skeletons );
			const animations = extractFromCache( meta.animations );
			const nodes = extractFromCache( meta.nodes );

			if ( geometries.length > 0 ) output.geometries = geometries;
			if ( materials.length > 0 ) output.materials = materials;
			if ( textures.length > 0 ) output.textures = textures;
			if ( images.length > 0 ) output.images = images;
			if ( shapes.length > 0 ) output.shapes = shapes;
			if ( skeletons.length > 0 ) output.skeletons = skeletons;
			if ( animations.length > 0 ) output.animations = animations;
			if ( nodes.length > 0 ) output.nodes = nodes;

		}

		output.object = object;

		return output;

		// extract data from the cache hash
		// remove metadata on each item
		// and return as array
		function extractFromCache( cache ) {

			const values = [];
			for ( const key in cache ) {

				const data = cache[ key ];
				delete data.metadata;
				values.push( data );

			}

			return values;

		}

	}
```
</details>

##### `clone(recursive: boolean): Object3D`

<details><summary>Code</summary>

```ts
clone( recursive ) {

		return new this.constructor().copy( this, recursive );

	}
```
</details>

##### `copy(source: Object3D, recursive: boolean): Object3D`

<details><summary>Code</summary>

```ts
copy( source, recursive = true ) {

		this.name = source.name;

		this.up.copy( source.up );

		this.position.copy( source.position );
		this.rotation.order = source.rotation.order;
		this.quaternion.copy( source.quaternion );
		this.scale.copy( source.scale );

		this.matrix.copy( source.matrix );
		this.matrixWorld.copy( source.matrixWorld );

		this.matrixAutoUpdate = source.matrixAutoUpdate;

		this.matrixWorldAutoUpdate = source.matrixWorldAutoUpdate;
		this.matrixWorldNeedsUpdate = source.matrixWorldNeedsUpdate;

		this.layers.mask = source.layers.mask;
		this.visible = source.visible;

		this.castShadow = source.castShadow;
		this.receiveShadow = source.receiveShadow;

		this.frustumCulled = source.frustumCulled;
		this.renderOrder = source.renderOrder;

		this.animations = source.animations.slice();

		this.userData = JSON.parse( JSON.stringify( source.userData ) );

		if ( recursive === true ) {

			for ( let i = 0; i < source.children.length; i ++ ) {

				const child = source.children[ i ];
				this.add( child.clone() );

			}

		}

		return this;

	}
```
</details>


---