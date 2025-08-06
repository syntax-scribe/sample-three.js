[⬅️ Back to Table of Contents](../../index.md)

# 📄 `SkinnedMesh.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 18 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/objects/SkinnedMesh.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Mesh` | `./Mesh.js` |
| `Box3` | `../math/Box3.js` |
| `Matrix4` | `../math/Matrix4.js` |
| `Sphere` | `../math/Sphere.js` |
| `Vector3` | `../math/Vector3.js` |
| `Vector4` | `../math/Vector4.js` |
| `Ray` | `../math/Ray.js` |
| `AttachedBindMode` | `../constants.js` |
| `DetachedBindMode` | `../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_basePosition` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_skinIndex` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `_skinWeight` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `_vector3` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_matrix4` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_vertex` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_sphere` | `Sphere` | let/var | `new Sphere()` | ✗ |
| `_inverseMatrix` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_ray` | `Ray` | let/var | `new Ray()` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `material` | `any` | let/var | `this.material` | ✗ |
| `matrixWorld` | `Matrix4` | let/var | `this.matrixWorld` | ✗ |
| `vector` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `skinWeight` | `any` | let/var | `this.geometry.attributes.skinWeight` | ✗ |
| `scale` | `number` | let/var | `1.0 / vector.manhattanLength()` | ✗ |
| `skeleton` | `any` | let/var | `this.skeleton` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |


---

## Functions

### `SkinnedMesh.computeBoundingBox(): void`

**JSDoc:**
```typescript
/**
	 * Computes the bounding box of the skinned mesh, and updates {@link SkinnedMesh#boundingBox}.
	 * The bounding box is not automatically computed by the engine; this method must be called by your app.
	 * If the skinned mesh is animated, the bounding box should be recomputed per frame in order to reflect
	 * the current animation state.
	 */
```

**Returns:** `void`

**Calls:**

- `this.boundingBox.makeEmpty`
- `geometry.getAttribute`
- `this.getVertexPosition`
- `this.boundingBox.expandByPoint`

<details><summary>Code</summary>

```typescript
computeBoundingBox() {

		const geometry = this.geometry;

		if ( this.boundingBox === null ) {

			this.boundingBox = new Box3();

		}

		this.boundingBox.makeEmpty();

		const positionAttribute = geometry.getAttribute( 'position' );

		for ( let i = 0; i < positionAttribute.count; i ++ ) {

			this.getVertexPosition( i, _vertex );
			this.boundingBox.expandByPoint( _vertex );

		}

	}
```
</details>

### `SkinnedMesh.computeBoundingSphere(): void`

**JSDoc:**
```typescript
/**
	 * Computes the bounding sphere of the skinned mesh, and updates {@link SkinnedMesh#boundingSphere}.
	 * The bounding sphere is automatically computed by the engine once when it is needed, e.g., for ray casting
	 * and view frustum culling. If the skinned mesh is animated, the bounding sphere should be recomputed
	 * per frame in order to reflect the current animation state.
	 */
```

**Returns:** `void`

**Calls:**

- `this.boundingSphere.makeEmpty`
- `geometry.getAttribute`
- `this.getVertexPosition`
- `this.boundingSphere.expandByPoint`

<details><summary>Code</summary>

```typescript
computeBoundingSphere() {

		const geometry = this.geometry;

		if ( this.boundingSphere === null ) {

			this.boundingSphere = new Sphere();

		}

		this.boundingSphere.makeEmpty();

		const positionAttribute = geometry.getAttribute( 'position' );

		for ( let i = 0; i < positionAttribute.count; i ++ ) {

			this.getVertexPosition( i, _vertex );
			this.boundingSphere.expandByPoint( _vertex );

		}

	}
```
</details>

### `SkinnedMesh.copy(source: any, recursive: any): this`

**Parameters:**

- **`source`** `any`
- **`recursive`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.bindMatrix.copy`
- `this.bindMatrixInverse.copy`
- `source.boundingBox.clone`
- `source.boundingSphere.clone`

<details><summary>Code</summary>

```typescript
copy( source, recursive ) {

		super.copy( source, recursive );

		this.bindMode = source.bindMode;
		this.bindMatrix.copy( source.bindMatrix );
		this.bindMatrixInverse.copy( source.bindMatrixInverse );

		this.skeleton = source.skeleton;

		if ( source.boundingBox !== null ) this.boundingBox = source.boundingBox.clone();
		if ( source.boundingSphere !== null ) this.boundingSphere = source.boundingSphere.clone();

		return this;

	}
```
</details>

### `SkinnedMesh.raycast(raycaster: any, intersects: any): void`

**Parameters:**

- **`raycaster`** `any`
- **`intersects`** `any`

**Returns:** `void`

**Calls:**

- `this.computeBoundingSphere`
- `_sphere.copy`
- `_sphere.applyMatrix4`
- `raycaster.ray.intersectsSphere`
- `_inverseMatrix.copy( matrixWorld ).invert`
- `_ray.copy( raycaster.ray ).applyMatrix4`
- `_ray.intersectsBox`
- `this._computeIntersections`

**Internal Comments:**
```
// test with bounding sphere in world space
// convert ray to local space of skinned mesh (x6)
// test with bounding box in local space
// test for intersections with geometry (x4)
```

<details><summary>Code</summary>

```typescript
raycast( raycaster, intersects ) {

		const material = this.material;
		const matrixWorld = this.matrixWorld;

		if ( material === undefined ) return;

		// test with bounding sphere in world space

		if ( this.boundingSphere === null ) this.computeBoundingSphere();

		_sphere.copy( this.boundingSphere );
		_sphere.applyMatrix4( matrixWorld );

		if ( raycaster.ray.intersectsSphere( _sphere ) === false ) return;

		// convert ray to local space of skinned mesh

		_inverseMatrix.copy( matrixWorld ).invert();
		_ray.copy( raycaster.ray ).applyMatrix4( _inverseMatrix );

		// test with bounding box in local space

		if ( this.boundingBox !== null ) {

			if ( _ray.intersectsBox( this.boundingBox ) === false ) return;

		}

		// test for intersections with geometry

		this._computeIntersections( raycaster, intersects, _ray );

	}
```
</details>

### `SkinnedMesh.getVertexPosition(index: any, target: any): any`

**Parameters:**

- **`index`** `any`
- **`target`** `any`

**Returns:** `any`

**Calls:**

- `super.getVertexPosition`
- `this.applyBoneTransform`

<details><summary>Code</summary>

```typescript
getVertexPosition( index, target ) {

		super.getVertexPosition( index, target );

		this.applyBoneTransform( index, target );

		return target;

	}
```
</details>

### `SkinnedMesh.bind(skeleton: Skeleton, bindMatrix: Matrix4): void`

**JSDoc:**
```typescript
/**
	 * Binds the given skeleton to the skinned mesh.
	 *
	 * @param {Skeleton} skeleton - The skeleton to bind.
	 * @param {Matrix4} [bindMatrix] - The bind matrix. If no bind matrix is provided,
	 * the skinned mesh's world matrix will be used instead.
	 */
```

**Parameters:**

- **`skeleton`** `Skeleton`
- **`bindMatrix`** `Matrix4`

**Returns:** `void`

**Calls:**

- `this.updateMatrixWorld`
- `this.skeleton.calculateInverses`
- `this.bindMatrix.copy`
- `this.bindMatrixInverse.copy( bindMatrix ).invert`

<details><summary>Code</summary>

```typescript
bind( skeleton, bindMatrix ) {

		this.skeleton = skeleton;

		if ( bindMatrix === undefined ) {

			this.updateMatrixWorld( true );

			this.skeleton.calculateInverses();

			bindMatrix = this.matrixWorld;

		}

		this.bindMatrix.copy( bindMatrix );
		this.bindMatrixInverse.copy( bindMatrix ).invert();

	}
```
</details>

### `SkinnedMesh.pose(): void`

**JSDoc:**
```typescript
/**
	 * This method sets the skinned mesh in the rest pose).
	 */
```

**Returns:** `void`

**Calls:**

- `this.skeleton.pose`

<details><summary>Code</summary>

```typescript
pose() {

		this.skeleton.pose();

	}
```
</details>

### `SkinnedMesh.normalizeSkinWeights(): void`

**JSDoc:**
```typescript
/**
	 * Normalizes the skin weights which are defined as a buffer attribute
	 * in the skinned mesh's geometry.
	 */
```

**Returns:** `void`

**Calls:**

- `vector.fromBufferAttribute`
- `vector.manhattanLength`
- `vector.multiplyScalar`
- `vector.set`
- `skinWeight.setXYZW`

<details><summary>Code</summary>

```typescript
normalizeSkinWeights() {

		const vector = new Vector4();

		const skinWeight = this.geometry.attributes.skinWeight;

		for ( let i = 0, l = skinWeight.count; i < l; i ++ ) {

			vector.fromBufferAttribute( skinWeight, i );

			const scale = 1.0 / vector.manhattanLength();

			if ( scale !== Infinity ) {

				vector.multiplyScalar( scale );

			} else {

				vector.set( 1, 0, 0, 0 ); // do something reasonable

			}

			skinWeight.setXYZW( i, vector.x, vector.y, vector.z, vector.w );

		}

	}
```
</details>

### `SkinnedMesh.updateMatrixWorld(force: any): void`

**Parameters:**

- **`force`** `any`

**Returns:** `void`

**Calls:**

- `super.updateMatrixWorld`
- `this.bindMatrixInverse.copy( this.matrixWorld ).invert`
- `this.bindMatrixInverse.copy( this.bindMatrix ).invert`
- `console.warn`

<details><summary>Code</summary>

```typescript
updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		if ( this.bindMode === AttachedBindMode ) {

			this.bindMatrixInverse.copy( this.matrixWorld ).invert();

		} else if ( this.bindMode === DetachedBindMode ) {

			this.bindMatrixInverse.copy( this.bindMatrix ).invert();

		} else {

			console.warn( 'THREE.SkinnedMesh: Unrecognized bindMode: ' + this.bindMode );

		}

	}
```
</details>

### `SkinnedMesh.applyBoneTransform(index: number, target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Applies the bone transform associated with the given index to the given
	 * vertex position. Returns the updated vector.
	 *
	 * @param {number} index - The vertex index.
	 * @param {Vector3} target - The target object that is used to store the method's result.
	 * the skinned mesh's world matrix will be used instead.
	 * @return {Vector3} The updated vertex position.
	 */
```

**Parameters:**

- **`index`** `number`
- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `_skinIndex.fromBufferAttribute`
- `_skinWeight.fromBufferAttribute`
- `_basePosition.copy( target ).applyMatrix4`
- `target.set`
- `_skinWeight.getComponent`
- `_skinIndex.getComponent`
- `_matrix4.multiplyMatrices`
- `target.addScaledVector`
- `_vector3.copy( _basePosition ).applyMatrix4`
- `target.applyMatrix4`

<details><summary>Code</summary>

```typescript
applyBoneTransform( index, target ) {

		const skeleton = this.skeleton;
		const geometry = this.geometry;

		_skinIndex.fromBufferAttribute( geometry.attributes.skinIndex, index );
		_skinWeight.fromBufferAttribute( geometry.attributes.skinWeight, index );

		_basePosition.copy( target ).applyMatrix4( this.bindMatrix );

		target.set( 0, 0, 0 );

		for ( let i = 0; i < 4; i ++ ) {

			const weight = _skinWeight.getComponent( i );

			if ( weight !== 0 ) {

				const boneIndex = _skinIndex.getComponent( i );

				_matrix4.multiplyMatrices( skeleton.bones[ boneIndex ].matrixWorld, skeleton.boneInverses[ boneIndex ] );

				target.addScaledVector( _vector3.copy( _basePosition ).applyMatrix4( _matrix4 ), weight );

			}

		}

		return target.applyMatrix4( this.bindMatrixInverse );

	}
```
</details>


---

## Classes

### `SkinnedMesh`

<details><summary>Class Code</summary>

```ts
class SkinnedMesh extends Mesh {

	/**
	 * Constructs a new skinned mesh.
	 *
	 * @param {BufferGeometry} [geometry] - The mesh geometry.
	 * @param {Material|Array<Material>} [material] - The mesh material.
	 */
	constructor( geometry, material ) {

		super( geometry, material );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSkinnedMesh = true;

		this.type = 'SkinnedMesh';

		/**
		 * `AttachedBindMode` means the skinned mesh shares the same world space as the skeleton.
		 * This is not true when using `DetachedBindMode` which is useful when sharing a skeleton
		 * across multiple skinned meshes.
		 *
		 * @type {(AttachedBindMode|DetachedBindMode)}
		 * @default AttachedBindMode
		 */
		this.bindMode = AttachedBindMode;

		/**
		 * The base matrix that is used for the bound bone transforms.
		 *
		 * @type {Matrix4}
		 */
		this.bindMatrix = new Matrix4();

		/**
		 * The base matrix that is used for resetting the bound bone transforms.
		 *
		 * @type {Matrix4}
		 */
		this.bindMatrixInverse = new Matrix4();

		/**
		 * The bounding box of the skinned mesh. Can be computed via {@link SkinnedMesh#computeBoundingBox}.
		 *
		 * @type {?Box3}
		 * @default null
		 */
		this.boundingBox = null;

		/**
		 * The bounding sphere of the skinned mesh. Can be computed via {@link SkinnedMesh#computeBoundingSphere}.
		 *
		 * @type {?Sphere}
		 * @default null
		 */
		this.boundingSphere = null;

	}

	/**
	 * Computes the bounding box of the skinned mesh, and updates {@link SkinnedMesh#boundingBox}.
	 * The bounding box is not automatically computed by the engine; this method must be called by your app.
	 * If the skinned mesh is animated, the bounding box should be recomputed per frame in order to reflect
	 * the current animation state.
	 */
	computeBoundingBox() {

		const geometry = this.geometry;

		if ( this.boundingBox === null ) {

			this.boundingBox = new Box3();

		}

		this.boundingBox.makeEmpty();

		const positionAttribute = geometry.getAttribute( 'position' );

		for ( let i = 0; i < positionAttribute.count; i ++ ) {

			this.getVertexPosition( i, _vertex );
			this.boundingBox.expandByPoint( _vertex );

		}

	}

	/**
	 * Computes the bounding sphere of the skinned mesh, and updates {@link SkinnedMesh#boundingSphere}.
	 * The bounding sphere is automatically computed by the engine once when it is needed, e.g., for ray casting
	 * and view frustum culling. If the skinned mesh is animated, the bounding sphere should be recomputed
	 * per frame in order to reflect the current animation state.
	 */
	computeBoundingSphere() {

		const geometry = this.geometry;

		if ( this.boundingSphere === null ) {

			this.boundingSphere = new Sphere();

		}

		this.boundingSphere.makeEmpty();

		const positionAttribute = geometry.getAttribute( 'position' );

		for ( let i = 0; i < positionAttribute.count; i ++ ) {

			this.getVertexPosition( i, _vertex );
			this.boundingSphere.expandByPoint( _vertex );

		}

	}

	copy( source, recursive ) {

		super.copy( source, recursive );

		this.bindMode = source.bindMode;
		this.bindMatrix.copy( source.bindMatrix );
		this.bindMatrixInverse.copy( source.bindMatrixInverse );

		this.skeleton = source.skeleton;

		if ( source.boundingBox !== null ) this.boundingBox = source.boundingBox.clone();
		if ( source.boundingSphere !== null ) this.boundingSphere = source.boundingSphere.clone();

		return this;

	}

	raycast( raycaster, intersects ) {

		const material = this.material;
		const matrixWorld = this.matrixWorld;

		if ( material === undefined ) return;

		// test with bounding sphere in world space

		if ( this.boundingSphere === null ) this.computeBoundingSphere();

		_sphere.copy( this.boundingSphere );
		_sphere.applyMatrix4( matrixWorld );

		if ( raycaster.ray.intersectsSphere( _sphere ) === false ) return;

		// convert ray to local space of skinned mesh

		_inverseMatrix.copy( matrixWorld ).invert();
		_ray.copy( raycaster.ray ).applyMatrix4( _inverseMatrix );

		// test with bounding box in local space

		if ( this.boundingBox !== null ) {

			if ( _ray.intersectsBox( this.boundingBox ) === false ) return;

		}

		// test for intersections with geometry

		this._computeIntersections( raycaster, intersects, _ray );

	}

	getVertexPosition( index, target ) {

		super.getVertexPosition( index, target );

		this.applyBoneTransform( index, target );

		return target;

	}

	/**
	 * Binds the given skeleton to the skinned mesh.
	 *
	 * @param {Skeleton} skeleton - The skeleton to bind.
	 * @param {Matrix4} [bindMatrix] - The bind matrix. If no bind matrix is provided,
	 * the skinned mesh's world matrix will be used instead.
	 */
	bind( skeleton, bindMatrix ) {

		this.skeleton = skeleton;

		if ( bindMatrix === undefined ) {

			this.updateMatrixWorld( true );

			this.skeleton.calculateInverses();

			bindMatrix = this.matrixWorld;

		}

		this.bindMatrix.copy( bindMatrix );
		this.bindMatrixInverse.copy( bindMatrix ).invert();

	}

	/**
	 * This method sets the skinned mesh in the rest pose).
	 */
	pose() {

		this.skeleton.pose();

	}

	/**
	 * Normalizes the skin weights which are defined as a buffer attribute
	 * in the skinned mesh's geometry.
	 */
	normalizeSkinWeights() {

		const vector = new Vector4();

		const skinWeight = this.geometry.attributes.skinWeight;

		for ( let i = 0, l = skinWeight.count; i < l; i ++ ) {

			vector.fromBufferAttribute( skinWeight, i );

			const scale = 1.0 / vector.manhattanLength();

			if ( scale !== Infinity ) {

				vector.multiplyScalar( scale );

			} else {

				vector.set( 1, 0, 0, 0 ); // do something reasonable

			}

			skinWeight.setXYZW( i, vector.x, vector.y, vector.z, vector.w );

		}

	}

	updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		if ( this.bindMode === AttachedBindMode ) {

			this.bindMatrixInverse.copy( this.matrixWorld ).invert();

		} else if ( this.bindMode === DetachedBindMode ) {

			this.bindMatrixInverse.copy( this.bindMatrix ).invert();

		} else {

			console.warn( 'THREE.SkinnedMesh: Unrecognized bindMode: ' + this.bindMode );

		}

	}

	/**
	 * Applies the bone transform associated with the given index to the given
	 * vertex position. Returns the updated vector.
	 *
	 * @param {number} index - The vertex index.
	 * @param {Vector3} target - The target object that is used to store the method's result.
	 * the skinned mesh's world matrix will be used instead.
	 * @return {Vector3} The updated vertex position.
	 */
	applyBoneTransform( index, target ) {

		const skeleton = this.skeleton;
		const geometry = this.geometry;

		_skinIndex.fromBufferAttribute( geometry.attributes.skinIndex, index );
		_skinWeight.fromBufferAttribute( geometry.attributes.skinWeight, index );

		_basePosition.copy( target ).applyMatrix4( this.bindMatrix );

		target.set( 0, 0, 0 );

		for ( let i = 0; i < 4; i ++ ) {

			const weight = _skinWeight.getComponent( i );

			if ( weight !== 0 ) {

				const boneIndex = _skinIndex.getComponent( i );

				_matrix4.multiplyMatrices( skeleton.bones[ boneIndex ].matrixWorld, skeleton.boneInverses[ boneIndex ] );

				target.addScaledVector( _vector3.copy( _basePosition ).applyMatrix4( _matrix4 ), weight );

			}

		}

		return target.applyMatrix4( this.bindMatrixInverse );

	}

}
```
</details>

#### Methods

##### `computeBoundingBox(): void`

<details><summary>Code</summary>

```ts
computeBoundingBox() {

		const geometry = this.geometry;

		if ( this.boundingBox === null ) {

			this.boundingBox = new Box3();

		}

		this.boundingBox.makeEmpty();

		const positionAttribute = geometry.getAttribute( 'position' );

		for ( let i = 0; i < positionAttribute.count; i ++ ) {

			this.getVertexPosition( i, _vertex );
			this.boundingBox.expandByPoint( _vertex );

		}

	}
```
</details>

##### `computeBoundingSphere(): void`

<details><summary>Code</summary>

```ts
computeBoundingSphere() {

		const geometry = this.geometry;

		if ( this.boundingSphere === null ) {

			this.boundingSphere = new Sphere();

		}

		this.boundingSphere.makeEmpty();

		const positionAttribute = geometry.getAttribute( 'position' );

		for ( let i = 0; i < positionAttribute.count; i ++ ) {

			this.getVertexPosition( i, _vertex );
			this.boundingSphere.expandByPoint( _vertex );

		}

	}
```
</details>

##### `copy(source: any, recursive: any): this`

<details><summary>Code</summary>

```ts
copy( source, recursive ) {

		super.copy( source, recursive );

		this.bindMode = source.bindMode;
		this.bindMatrix.copy( source.bindMatrix );
		this.bindMatrixInverse.copy( source.bindMatrixInverse );

		this.skeleton = source.skeleton;

		if ( source.boundingBox !== null ) this.boundingBox = source.boundingBox.clone();
		if ( source.boundingSphere !== null ) this.boundingSphere = source.boundingSphere.clone();

		return this;

	}
```
</details>

##### `raycast(raycaster: any, intersects: any): void`

<details><summary>Code</summary>

```ts
raycast( raycaster, intersects ) {

		const material = this.material;
		const matrixWorld = this.matrixWorld;

		if ( material === undefined ) return;

		// test with bounding sphere in world space

		if ( this.boundingSphere === null ) this.computeBoundingSphere();

		_sphere.copy( this.boundingSphere );
		_sphere.applyMatrix4( matrixWorld );

		if ( raycaster.ray.intersectsSphere( _sphere ) === false ) return;

		// convert ray to local space of skinned mesh

		_inverseMatrix.copy( matrixWorld ).invert();
		_ray.copy( raycaster.ray ).applyMatrix4( _inverseMatrix );

		// test with bounding box in local space

		if ( this.boundingBox !== null ) {

			if ( _ray.intersectsBox( this.boundingBox ) === false ) return;

		}

		// test for intersections with geometry

		this._computeIntersections( raycaster, intersects, _ray );

	}
```
</details>

##### `getVertexPosition(index: any, target: any): any`

<details><summary>Code</summary>

```ts
getVertexPosition( index, target ) {

		super.getVertexPosition( index, target );

		this.applyBoneTransform( index, target );

		return target;

	}
```
</details>

##### `bind(skeleton: Skeleton, bindMatrix: Matrix4): void`

<details><summary>Code</summary>

```ts
bind( skeleton, bindMatrix ) {

		this.skeleton = skeleton;

		if ( bindMatrix === undefined ) {

			this.updateMatrixWorld( true );

			this.skeleton.calculateInverses();

			bindMatrix = this.matrixWorld;

		}

		this.bindMatrix.copy( bindMatrix );
		this.bindMatrixInverse.copy( bindMatrix ).invert();

	}
```
</details>

##### `pose(): void`

<details><summary>Code</summary>

```ts
pose() {

		this.skeleton.pose();

	}
```
</details>

##### `normalizeSkinWeights(): void`

<details><summary>Code</summary>

```ts
normalizeSkinWeights() {

		const vector = new Vector4();

		const skinWeight = this.geometry.attributes.skinWeight;

		for ( let i = 0, l = skinWeight.count; i < l; i ++ ) {

			vector.fromBufferAttribute( skinWeight, i );

			const scale = 1.0 / vector.manhattanLength();

			if ( scale !== Infinity ) {

				vector.multiplyScalar( scale );

			} else {

				vector.set( 1, 0, 0, 0 ); // do something reasonable

			}

			skinWeight.setXYZW( i, vector.x, vector.y, vector.z, vector.w );

		}

	}
```
</details>

##### `updateMatrixWorld(force: any): void`

<details><summary>Code</summary>

```ts
updateMatrixWorld( force ) {

		super.updateMatrixWorld( force );

		if ( this.bindMode === AttachedBindMode ) {

			this.bindMatrixInverse.copy( this.matrixWorld ).invert();

		} else if ( this.bindMode === DetachedBindMode ) {

			this.bindMatrixInverse.copy( this.bindMatrix ).invert();

		} else {

			console.warn( 'THREE.SkinnedMesh: Unrecognized bindMode: ' + this.bindMode );

		}

	}
```
</details>

##### `applyBoneTransform(index: number, target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
applyBoneTransform( index, target ) {

		const skeleton = this.skeleton;
		const geometry = this.geometry;

		_skinIndex.fromBufferAttribute( geometry.attributes.skinIndex, index );
		_skinWeight.fromBufferAttribute( geometry.attributes.skinWeight, index );

		_basePosition.copy( target ).applyMatrix4( this.bindMatrix );

		target.set( 0, 0, 0 );

		for ( let i = 0; i < 4; i ++ ) {

			const weight = _skinWeight.getComponent( i );

			if ( weight !== 0 ) {

				const boneIndex = _skinIndex.getComponent( i );

				_matrix4.multiplyMatrices( skeleton.bones[ boneIndex ].matrixWorld, skeleton.boneInverses[ boneIndex ] );

				target.addScaledVector( _vector3.copy( _basePosition ).applyMatrix4( _matrix4 ), weight );

			}

		}

		return target.applyMatrix4( this.bindMatrixInverse );

	}
```
</details>


---