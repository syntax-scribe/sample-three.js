[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Mesh.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 11 |
| 📊 Variables & Constants | 48 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/objects/Mesh.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `../math/Vector3.js` |
| `Vector2` | `../math/Vector2.js` |
| `Sphere` | `../math/Sphere.js` |
| `Ray` | `../math/Ray.js` |
| `Matrix4` | `../math/Matrix4.js` |
| `Object3D` | `../core/Object3D.js` |
| `Triangle` | `../math/Triangle.js` |
| `BackSide` | `../constants.js` |
| `FrontSide` | `../constants.js` |
| `MeshBasicMaterial` | `../materials/MeshBasicMaterial.js` |
| `BufferGeometry` | `../core/BufferGeometry.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_inverseMatrix` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_ray` | `Ray` | let/var | `new Ray()` | ✗ |
| `_sphere` | `Sphere` | let/var | `new Sphere()` | ✗ |
| `_sphereHitAt` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_vA` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_vB` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_vC` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_tempA` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_morphA` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_intersectionPoint` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_intersectionPointWorld` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `morphAttributes` | `any` | let/var | `geometry.morphAttributes` | ✗ |
| `morphAttribute` | `any` | let/var | `morphAttributes[ keys[ 0 ] ]` | ✗ |
| `name` | `any` | let/var | `morphAttribute[ m ].name \|\| String( m )` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `position` | `any` | let/var | `geometry.attributes.position` | ✗ |
| `morphPosition` | `any` | let/var | `geometry.morphAttributes.position` | ✗ |
| `morphTargetsRelative` | `boolean` | let/var | `geometry.morphTargetsRelative` | ✗ |
| `morphInfluences` | `number[]` | let/var | `this.morphTargetInfluences` | ✗ |
| `influence` | `number` | let/var | `morphInfluences[ i ]` | ✗ |
| `morphAttribute` | `any` | let/var | `morphPosition[ i ]` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `material` | `any` | let/var | `this.material` | ✗ |
| `matrixWorld` | `Matrix4` | let/var | `this.matrixWorld` | ✗ |
| `intersection` | `any` | let/var | `*not shown*` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `material` | `any` | let/var | `this.material` | ✗ |
| `index` | `BufferAttribute` | let/var | `geometry.index` | ✗ |
| `position` | `any` | let/var | `geometry.attributes.position` | ✗ |
| `uv` | `any` | let/var | `geometry.attributes.uv` | ✗ |
| `uv1` | `any` | let/var | `geometry.attributes.uv1` | ✗ |
| `normal` | `any` | let/var | `geometry.attributes.normal` | ✗ |
| `groups` | `any[]` | let/var | `geometry.groups` | ✗ |
| `drawRange` | `{ start: number; count: number; }` | let/var | `geometry.drawRange` | ✗ |
| `group` | `any` | let/var | `groups[ i ]` | ✗ |
| `groupMaterial` | `any` | let/var | `material[ group.materialIndex ]` | ✗ |
| `group` | `any` | let/var | `groups[ i ]` | ✗ |
| `groupMaterial` | `any` | let/var | `material[ group.materialIndex ]` | ✗ |
| `a` | `number` | let/var | `j` | ✗ |
| `b` | `number` | let/var | `j + 1` | ✗ |
| `c` | `number` | let/var | `j + 2` | ✗ |
| `a` | `number` | let/var | `i` | ✗ |
| `b` | `number` | let/var | `i + 1` | ✗ |
| `c` | `number` | let/var | `i + 2` | ✗ |
| `intersect` | `any` | let/var | `*not shown*` | ✗ |
| `barycoord` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `face` | `{ a: any; b: any; c: any; normal: Vec...` | let/var | `{ a: a, b: b, c: c, normal: new Vector3(), materialIndex: 0 }` | ✗ |


---

## Functions

### `Mesh.copy(source: any, recursive: any): this`

**Parameters:**

- **`source`** `any`
- **`recursive`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `source.morphTargetInfluences.slice`
- `Object.assign`
- `Array.isArray`
- `source.material.slice`

<details><summary>Code</summary>

```typescript
copy( source, recursive ) {

		super.copy( source, recursive );

		if ( source.morphTargetInfluences !== undefined ) {

			this.morphTargetInfluences = source.morphTargetInfluences.slice();

		}

		if ( source.morphTargetDictionary !== undefined ) {

			this.morphTargetDictionary = Object.assign( {}, source.morphTargetDictionary );

		}

		this.material = Array.isArray( source.material ) ? source.material.slice() : source.material;
		this.geometry = source.geometry;

		return this;

	}
```
</details>

### `Mesh.updateMorphTargets(): void`

**JSDoc:**
```typescript
/**
	 * Sets the values of {@link Mesh#morphTargetDictionary} and {@link Mesh#morphTargetInfluences}
	 * to make sure existing morph targets can influence this 3D object.
	 */
```

**Returns:** `void`

**Calls:**

- `Object.keys`
- `String`
- `this.morphTargetInfluences.push`

<details><summary>Code</summary>

```typescript
updateMorphTargets() {

		const geometry = this.geometry;

		const morphAttributes = geometry.morphAttributes;
		const keys = Object.keys( morphAttributes );

		if ( keys.length > 0 ) {

			const morphAttribute = morphAttributes[ keys[ 0 ] ];

			if ( morphAttribute !== undefined ) {

				this.morphTargetInfluences = [];
				this.morphTargetDictionary = {};

				for ( let m = 0, ml = morphAttribute.length; m < ml; m ++ ) {

					const name = morphAttribute[ m ].name || String( m );

					this.morphTargetInfluences.push( 0 );
					this.morphTargetDictionary[ name ] = m;

				}

			}

		}

	}
```
</details>

### `Mesh.getVertexPosition(index: number, target: Vector3): Vector3`

**JSDoc:**
```typescript
/**
	 * Returns the local-space position of the vertex at the given index, taking into
	 * account the current animation state of both morph targets and skinning.
	 *
	 * @param {number} index - The vertex index.
	 * @param {Vector3} target - The target object that is used to store the method's result.
	 * @return {Vector3} The vertex position in local space.
	 */
```

**Parameters:**

- **`index`** `number`
- **`target`** `Vector3`

**Returns:** `Vector3`

**Calls:**

- `target.fromBufferAttribute`
- `_morphA.set`
- `_tempA.fromBufferAttribute`
- `_morphA.addScaledVector`
- `_tempA.sub`
- `target.add`

<details><summary>Code</summary>

```typescript
getVertexPosition( index, target ) {

		const geometry = this.geometry;
		const position = geometry.attributes.position;
		const morphPosition = geometry.morphAttributes.position;
		const morphTargetsRelative = geometry.morphTargetsRelative;

		target.fromBufferAttribute( position, index );

		const morphInfluences = this.morphTargetInfluences;

		if ( morphPosition && morphInfluences ) {

			_morphA.set( 0, 0, 0 );

			for ( let i = 0, il = morphPosition.length; i < il; i ++ ) {

				const influence = morphInfluences[ i ];
				const morphAttribute = morphPosition[ i ];

				if ( influence === 0 ) continue;

				_tempA.fromBufferAttribute( morphAttribute, index );

				if ( morphTargetsRelative ) {

					_morphA.addScaledVector( _tempA, influence );

				} else {

					_morphA.addScaledVector( _tempA.sub( target ), influence );

				}

			}

			target.add( _morphA );

		}

		return target;

	}
```
</details>

### `Mesh.raycast(raycaster: Raycaster, intersects: any[]): void`

**JSDoc:**
```typescript
/**
	 * Computes intersection points between a casted ray and this line.
	 *
	 * @param {Raycaster} raycaster - The raycaster.
	 * @param {Array<Object>} intersects - The target array that holds the intersection points.
	 */
```

**Parameters:**

- **`raycaster`** `Raycaster`
- **`intersects`** `any[]`

**Returns:** `void`

**Calls:**

- `geometry.computeBoundingSphere`
- `_sphere.copy`
- `_sphere.applyMatrix4`
- `_ray.copy( raycaster.ray ).recast`
- `_sphere.containsPoint`
- `_ray.intersectSphere`
- `_ray.origin.distanceToSquared`
- `_inverseMatrix.copy( matrixWorld ).invert`
- `_ray.copy( raycaster.ray ).applyMatrix4`
- `_ray.intersectsBox`
- `this._computeIntersections`

**Internal Comments:**
```
// test with bounding sphere in world space
// check distance from ray origin to bounding sphere (x6)
// convert ray to local space of mesh (x6)
// test with bounding box in local space
// test for intersections with geometry (x4)
```

<details><summary>Code</summary>

```typescript
raycast( raycaster, intersects ) {

		const geometry = this.geometry;
		const material = this.material;
		const matrixWorld = this.matrixWorld;

		if ( material === undefined ) return;

		// test with bounding sphere in world space

		if ( geometry.boundingSphere === null ) geometry.computeBoundingSphere();

		_sphere.copy( geometry.boundingSphere );
		_sphere.applyMatrix4( matrixWorld );

		// check distance from ray origin to bounding sphere

		_ray.copy( raycaster.ray ).recast( raycaster.near );

		if ( _sphere.containsPoint( _ray.origin ) === false ) {

			if ( _ray.intersectSphere( _sphere, _sphereHitAt ) === null ) return;

			if ( _ray.origin.distanceToSquared( _sphereHitAt ) > ( raycaster.far - raycaster.near ) ** 2 ) return;

		}

		// convert ray to local space of mesh

		_inverseMatrix.copy( matrixWorld ).invert();
		_ray.copy( raycaster.ray ).applyMatrix4( _inverseMatrix );

		// test with bounding box in local space

		if ( geometry.boundingBox !== null ) {

			if ( _ray.intersectsBox( geometry.boundingBox ) === false ) return;

		}

		// test for intersections with geometry

		this._computeIntersections( raycaster, intersects, _ray );

	}
```
</details>

### `Mesh._computeIntersections(raycaster: any, intersects: any, rayLocalSpace: any): void`

**Parameters:**

- **`raycaster`** `any`
- **`intersects`** `any`
- **`rayLocalSpace`** `any`

**Returns:** `void`

**Calls:**

- `Array.isArray`
- `Math.max`
- `Math.min`
- `index.getX`
- `checkGeometryIntersection`
- `Math.floor`
- `intersects.push`

**Internal Comments:**
```
// indexed buffer geometry
// non-indexed buffer geometry
```

<details><summary>Code</summary>

```typescript
_computeIntersections( raycaster, intersects, rayLocalSpace ) {

		let intersection;

		const geometry = this.geometry;
		const material = this.material;

		const index = geometry.index;
		const position = geometry.attributes.position;
		const uv = geometry.attributes.uv;
		const uv1 = geometry.attributes.uv1;
		const normal = geometry.attributes.normal;
		const groups = geometry.groups;
		const drawRange = geometry.drawRange;

		if ( index !== null ) {

			// indexed buffer geometry

			if ( Array.isArray( material ) ) {

				for ( let i = 0, il = groups.length; i < il; i ++ ) {

					const group = groups[ i ];
					const groupMaterial = material[ group.materialIndex ];

					const start = Math.max( group.start, drawRange.start );
					const end = Math.min( index.count, Math.min( ( group.start + group.count ), ( drawRange.start + drawRange.count ) ) );

					for ( let j = start, jl = end; j < jl; j += 3 ) {

						const a = index.getX( j );
						const b = index.getX( j + 1 );
						const c = index.getX( j + 2 );

						intersection = checkGeometryIntersection( this, groupMaterial, raycaster, rayLocalSpace, uv, uv1, normal, a, b, c );

						if ( intersection ) {

							intersection.faceIndex = Math.floor( j / 3 ); // triangle number in indexed buffer semantics
							intersection.face.materialIndex = group.materialIndex;
							intersects.push( intersection );

						}

					}

				}

			} else {

				const start = Math.max( 0, drawRange.start );
				const end = Math.min( index.count, ( drawRange.start + drawRange.count ) );

				for ( let i = start, il = end; i < il; i += 3 ) {

					const a = index.getX( i );
					const b = index.getX( i + 1 );
					const c = index.getX( i + 2 );

					intersection = checkGeometryIntersection( this, material, raycaster, rayLocalSpace, uv, uv1, normal, a, b, c );

					if ( intersection ) {

						intersection.faceIndex = Math.floor( i / 3 ); // triangle number in indexed buffer semantics
						intersects.push( intersection );

					}

				}

			}

		} else if ( position !== undefined ) {

			// non-indexed buffer geometry

			if ( Array.isArray( material ) ) {

				for ( let i = 0, il = groups.length; i < il; i ++ ) {

					const group = groups[ i ];
					const groupMaterial = material[ group.materialIndex ];

					const start = Math.max( group.start, drawRange.start );
					const end = Math.min( position.count, Math.min( ( group.start + group.count ), ( drawRange.start + drawRange.count ) ) );

					for ( let j = start, jl = end; j < jl; j += 3 ) {

						const a = j;
						const b = j + 1;
						const c = j + 2;

						intersection = checkGeometryIntersection( this, groupMaterial, raycaster, rayLocalSpace, uv, uv1, normal, a, b, c );

						if ( intersection ) {

							intersection.faceIndex = Math.floor( j / 3 ); // triangle number in non-indexed buffer semantics
							intersection.face.materialIndex = group.materialIndex;
							intersects.push( intersection );

						}

					}

				}

			} else {

				const start = Math.max( 0, drawRange.start );
				const end = Math.min( position.count, ( drawRange.start + drawRange.count ) );

				for ( let i = start, il = end; i < il; i += 3 ) {

					const a = i;
					const b = i + 1;
					const c = i + 2;

					intersection = checkGeometryIntersection( this, material, raycaster, rayLocalSpace, uv, uv1, normal, a, b, c );

					if ( intersection ) {

						intersection.faceIndex = Math.floor( i / 3 ); // triangle number in non-indexed buffer semantics
						intersects.push( intersection );

					}

				}

			}

		}

	}
```
</details>

### `checkIntersection(object: any, material: any, raycaster: any, ray: any, pA: any, pB: any, pC: any, point: any): { distance: any; point: Vector3; object: any; }`

**Parameters:**

- **`object`** `any`
- **`material`** `any`
- **`raycaster`** `any`
- **`ray`** `any`
- **`pA`** `any`
- **`pB`** `any`
- **`pC`** `any`
- **`point`** `any`

**Returns:** `{ distance: any; point: Vector3; object: any; }`

**Calls:**

- `ray.intersectTriangle`
- `_intersectionPointWorld.copy`
- `_intersectionPointWorld.applyMatrix4`
- `raycaster.ray.origin.distanceTo`
- `_intersectionPointWorld.clone`

<details><summary>Code</summary>

```typescript
function checkIntersection( object, material, raycaster, ray, pA, pB, pC, point ) {

	let intersect;

	if ( material.side === BackSide ) {

		intersect = ray.intersectTriangle( pC, pB, pA, true, point );

	} else {

		intersect = ray.intersectTriangle( pA, pB, pC, ( material.side === FrontSide ), point );

	}

	if ( intersect === null ) return null;

	_intersectionPointWorld.copy( point );
	_intersectionPointWorld.applyMatrix4( object.matrixWorld );

	const distance = raycaster.ray.origin.distanceTo( _intersectionPointWorld );

	if ( distance < raycaster.near || distance > raycaster.far ) return null;

	return {
		distance: distance,
		point: _intersectionPointWorld.clone(),
		object: object
	};

}
```
</details>

### `checkGeometryIntersection(object: any, material: any, raycaster: any, ray: any, uv: any, uv1: any, normal: any, a: any, b: any, c: any): { distance: any; point: Vector3; object: any; }`

**Parameters:**

- **`object`** `any`
- **`material`** `any`
- **`raycaster`** `any`
- **`ray`** `any`
- **`uv`** `any`
- **`uv1`** `any`
- **`normal`** `any`
- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `{ distance: any; point: Vector3; object: any; }`

**Calls:**

- `object.getVertexPosition`
- `checkIntersection`
- `Triangle.getBarycoord`
- `Triangle.getInterpolatedAttribute`
- `intersection.normal.dot`
- `intersection.normal.multiplyScalar`
- `Triangle.getNormal`

<details><summary>Code</summary>

```typescript
function checkGeometryIntersection( object, material, raycaster, ray, uv, uv1, normal, a, b, c ) {

	object.getVertexPosition( a, _vA );
	object.getVertexPosition( b, _vB );
	object.getVertexPosition( c, _vC );

	const intersection = checkIntersection( object, material, raycaster, ray, _vA, _vB, _vC, _intersectionPoint );

	if ( intersection ) {

		const barycoord = new Vector3();
		Triangle.getBarycoord( _intersectionPoint, _vA, _vB, _vC, barycoord );

		if ( uv ) {

			intersection.uv = Triangle.getInterpolatedAttribute( uv, a, b, c, barycoord, new Vector2() );

		}

		if ( uv1 ) {

			intersection.uv1 = Triangle.getInterpolatedAttribute( uv1, a, b, c, barycoord, new Vector2() );

		}

		if ( normal ) {

			intersection.normal = Triangle.getInterpolatedAttribute( normal, a, b, c, barycoord, new Vector3() );

			if ( intersection.normal.dot( ray.direction ) > 0 ) {

				intersection.normal.multiplyScalar( - 1 );

			}

		}

		const face = {
			a: a,
			b: b,
			c: c,
			normal: new Vector3(),
			materialIndex: 0
		};

		Triangle.getNormal( _vA, _vB, _vC, face.normal );

		intersection.face = face;
		intersection.barycoord = barycoord;

	}

	return intersection;

}
```
</details>


---

## Classes

### `Mesh`

<details><summary>Class Code</summary>

```ts
class Mesh extends Object3D {

	/**
	 * Constructs a new mesh.
	 *
	 * @param {BufferGeometry} [geometry] - The mesh geometry.
	 * @param {Material|Array<Material>} [material] - The mesh material.
	 */
	constructor( geometry = new BufferGeometry(), material = new MeshBasicMaterial() ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isMesh = true;

		this.type = 'Mesh';

		/**
		 * The mesh geometry.
		 *
		 * @type {BufferGeometry}
		 */
		this.geometry = geometry;

		/**
		 * The mesh material.
		 *
		 * @type {Material|Array<Material>}
		 * @default MeshBasicMaterial
		 */
		this.material = material;

		/**
		 * A dictionary representing the morph targets in the geometry. The key is the
		 * morph targets name, the value its attribute index. This member is `undefined`
		 * by default and only set when morph targets are detected in the geometry.
		 *
		 * @type {Object<String,number>|undefined}
		 * @default undefined
		 */
		this.morphTargetDictionary = undefined;

		/**
		 * An array of weights typically in the range `[0,1]` that specify how much of the morph
		 * is applied. This member is `undefined` by default and only set when morph targets are
		 * detected in the geometry.
		 *
		 * @type {Array<number>|undefined}
		 * @default undefined
		 */
		this.morphTargetInfluences = undefined;

		/**
		 * The number of instances of this mesh.
		 * Can only be used with {@link WebGPURenderer}.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.count = 1;

		this.updateMorphTargets();

	}

	copy( source, recursive ) {

		super.copy( source, recursive );

		if ( source.morphTargetInfluences !== undefined ) {

			this.morphTargetInfluences = source.morphTargetInfluences.slice();

		}

		if ( source.morphTargetDictionary !== undefined ) {

			this.morphTargetDictionary = Object.assign( {}, source.morphTargetDictionary );

		}

		this.material = Array.isArray( source.material ) ? source.material.slice() : source.material;
		this.geometry = source.geometry;

		return this;

	}

	/**
	 * Sets the values of {@link Mesh#morphTargetDictionary} and {@link Mesh#morphTargetInfluences}
	 * to make sure existing morph targets can influence this 3D object.
	 */
	updateMorphTargets() {

		const geometry = this.geometry;

		const morphAttributes = geometry.morphAttributes;
		const keys = Object.keys( morphAttributes );

		if ( keys.length > 0 ) {

			const morphAttribute = morphAttributes[ keys[ 0 ] ];

			if ( morphAttribute !== undefined ) {

				this.morphTargetInfluences = [];
				this.morphTargetDictionary = {};

				for ( let m = 0, ml = morphAttribute.length; m < ml; m ++ ) {

					const name = morphAttribute[ m ].name || String( m );

					this.morphTargetInfluences.push( 0 );
					this.morphTargetDictionary[ name ] = m;

				}

			}

		}

	}

	/**
	 * Returns the local-space position of the vertex at the given index, taking into
	 * account the current animation state of both morph targets and skinning.
	 *
	 * @param {number} index - The vertex index.
	 * @param {Vector3} target - The target object that is used to store the method's result.
	 * @return {Vector3} The vertex position in local space.
	 */
	getVertexPosition( index, target ) {

		const geometry = this.geometry;
		const position = geometry.attributes.position;
		const morphPosition = geometry.morphAttributes.position;
		const morphTargetsRelative = geometry.morphTargetsRelative;

		target.fromBufferAttribute( position, index );

		const morphInfluences = this.morphTargetInfluences;

		if ( morphPosition && morphInfluences ) {

			_morphA.set( 0, 0, 0 );

			for ( let i = 0, il = morphPosition.length; i < il; i ++ ) {

				const influence = morphInfluences[ i ];
				const morphAttribute = morphPosition[ i ];

				if ( influence === 0 ) continue;

				_tempA.fromBufferAttribute( morphAttribute, index );

				if ( morphTargetsRelative ) {

					_morphA.addScaledVector( _tempA, influence );

				} else {

					_morphA.addScaledVector( _tempA.sub( target ), influence );

				}

			}

			target.add( _morphA );

		}

		return target;

	}

	/**
	 * Computes intersection points between a casted ray and this line.
	 *
	 * @param {Raycaster} raycaster - The raycaster.
	 * @param {Array<Object>} intersects - The target array that holds the intersection points.
	 */
	raycast( raycaster, intersects ) {

		const geometry = this.geometry;
		const material = this.material;
		const matrixWorld = this.matrixWorld;

		if ( material === undefined ) return;

		// test with bounding sphere in world space

		if ( geometry.boundingSphere === null ) geometry.computeBoundingSphere();

		_sphere.copy( geometry.boundingSphere );
		_sphere.applyMatrix4( matrixWorld );

		// check distance from ray origin to bounding sphere

		_ray.copy( raycaster.ray ).recast( raycaster.near );

		if ( _sphere.containsPoint( _ray.origin ) === false ) {

			if ( _ray.intersectSphere( _sphere, _sphereHitAt ) === null ) return;

			if ( _ray.origin.distanceToSquared( _sphereHitAt ) > ( raycaster.far - raycaster.near ) ** 2 ) return;

		}

		// convert ray to local space of mesh

		_inverseMatrix.copy( matrixWorld ).invert();
		_ray.copy( raycaster.ray ).applyMatrix4( _inverseMatrix );

		// test with bounding box in local space

		if ( geometry.boundingBox !== null ) {

			if ( _ray.intersectsBox( geometry.boundingBox ) === false ) return;

		}

		// test for intersections with geometry

		this._computeIntersections( raycaster, intersects, _ray );

	}

	_computeIntersections( raycaster, intersects, rayLocalSpace ) {

		let intersection;

		const geometry = this.geometry;
		const material = this.material;

		const index = geometry.index;
		const position = geometry.attributes.position;
		const uv = geometry.attributes.uv;
		const uv1 = geometry.attributes.uv1;
		const normal = geometry.attributes.normal;
		const groups = geometry.groups;
		const drawRange = geometry.drawRange;

		if ( index !== null ) {

			// indexed buffer geometry

			if ( Array.isArray( material ) ) {

				for ( let i = 0, il = groups.length; i < il; i ++ ) {

					const group = groups[ i ];
					const groupMaterial = material[ group.materialIndex ];

					const start = Math.max( group.start, drawRange.start );
					const end = Math.min( index.count, Math.min( ( group.start + group.count ), ( drawRange.start + drawRange.count ) ) );

					for ( let j = start, jl = end; j < jl; j += 3 ) {

						const a = index.getX( j );
						const b = index.getX( j + 1 );
						const c = index.getX( j + 2 );

						intersection = checkGeometryIntersection( this, groupMaterial, raycaster, rayLocalSpace, uv, uv1, normal, a, b, c );

						if ( intersection ) {

							intersection.faceIndex = Math.floor( j / 3 ); // triangle number in indexed buffer semantics
							intersection.face.materialIndex = group.materialIndex;
							intersects.push( intersection );

						}

					}

				}

			} else {

				const start = Math.max( 0, drawRange.start );
				const end = Math.min( index.count, ( drawRange.start + drawRange.count ) );

				for ( let i = start, il = end; i < il; i += 3 ) {

					const a = index.getX( i );
					const b = index.getX( i + 1 );
					const c = index.getX( i + 2 );

					intersection = checkGeometryIntersection( this, material, raycaster, rayLocalSpace, uv, uv1, normal, a, b, c );

					if ( intersection ) {

						intersection.faceIndex = Math.floor( i / 3 ); // triangle number in indexed buffer semantics
						intersects.push( intersection );

					}

				}

			}

		} else if ( position !== undefined ) {

			// non-indexed buffer geometry

			if ( Array.isArray( material ) ) {

				for ( let i = 0, il = groups.length; i < il; i ++ ) {

					const group = groups[ i ];
					const groupMaterial = material[ group.materialIndex ];

					const start = Math.max( group.start, drawRange.start );
					const end = Math.min( position.count, Math.min( ( group.start + group.count ), ( drawRange.start + drawRange.count ) ) );

					for ( let j = start, jl = end; j < jl; j += 3 ) {

						const a = j;
						const b = j + 1;
						const c = j + 2;

						intersection = checkGeometryIntersection( this, groupMaterial, raycaster, rayLocalSpace, uv, uv1, normal, a, b, c );

						if ( intersection ) {

							intersection.faceIndex = Math.floor( j / 3 ); // triangle number in non-indexed buffer semantics
							intersection.face.materialIndex = group.materialIndex;
							intersects.push( intersection );

						}

					}

				}

			} else {

				const start = Math.max( 0, drawRange.start );
				const end = Math.min( position.count, ( drawRange.start + drawRange.count ) );

				for ( let i = start, il = end; i < il; i += 3 ) {

					const a = i;
					const b = i + 1;
					const c = i + 2;

					intersection = checkGeometryIntersection( this, material, raycaster, rayLocalSpace, uv, uv1, normal, a, b, c );

					if ( intersection ) {

						intersection.faceIndex = Math.floor( i / 3 ); // triangle number in non-indexed buffer semantics
						intersects.push( intersection );

					}

				}

			}

		}

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

		if ( source.morphTargetInfluences !== undefined ) {

			this.morphTargetInfluences = source.morphTargetInfluences.slice();

		}

		if ( source.morphTargetDictionary !== undefined ) {

			this.morphTargetDictionary = Object.assign( {}, source.morphTargetDictionary );

		}

		this.material = Array.isArray( source.material ) ? source.material.slice() : source.material;
		this.geometry = source.geometry;

		return this;

	}
```
</details>

##### `updateMorphTargets(): void`

<details><summary>Code</summary>

```ts
updateMorphTargets() {

		const geometry = this.geometry;

		const morphAttributes = geometry.morphAttributes;
		const keys = Object.keys( morphAttributes );

		if ( keys.length > 0 ) {

			const morphAttribute = morphAttributes[ keys[ 0 ] ];

			if ( morphAttribute !== undefined ) {

				this.morphTargetInfluences = [];
				this.morphTargetDictionary = {};

				for ( let m = 0, ml = morphAttribute.length; m < ml; m ++ ) {

					const name = morphAttribute[ m ].name || String( m );

					this.morphTargetInfluences.push( 0 );
					this.morphTargetDictionary[ name ] = m;

				}

			}

		}

	}
```
</details>

##### `getVertexPosition(index: number, target: Vector3): Vector3`

<details><summary>Code</summary>

```ts
getVertexPosition( index, target ) {

		const geometry = this.geometry;
		const position = geometry.attributes.position;
		const morphPosition = geometry.morphAttributes.position;
		const morphTargetsRelative = geometry.morphTargetsRelative;

		target.fromBufferAttribute( position, index );

		const morphInfluences = this.morphTargetInfluences;

		if ( morphPosition && morphInfluences ) {

			_morphA.set( 0, 0, 0 );

			for ( let i = 0, il = morphPosition.length; i < il; i ++ ) {

				const influence = morphInfluences[ i ];
				const morphAttribute = morphPosition[ i ];

				if ( influence === 0 ) continue;

				_tempA.fromBufferAttribute( morphAttribute, index );

				if ( morphTargetsRelative ) {

					_morphA.addScaledVector( _tempA, influence );

				} else {

					_morphA.addScaledVector( _tempA.sub( target ), influence );

				}

			}

			target.add( _morphA );

		}

		return target;

	}
```
</details>

##### `raycast(raycaster: Raycaster, intersects: any[]): void`

<details><summary>Code</summary>

```ts
raycast( raycaster, intersects ) {

		const geometry = this.geometry;
		const material = this.material;
		const matrixWorld = this.matrixWorld;

		if ( material === undefined ) return;

		// test with bounding sphere in world space

		if ( geometry.boundingSphere === null ) geometry.computeBoundingSphere();

		_sphere.copy( geometry.boundingSphere );
		_sphere.applyMatrix4( matrixWorld );

		// check distance from ray origin to bounding sphere

		_ray.copy( raycaster.ray ).recast( raycaster.near );

		if ( _sphere.containsPoint( _ray.origin ) === false ) {

			if ( _ray.intersectSphere( _sphere, _sphereHitAt ) === null ) return;

			if ( _ray.origin.distanceToSquared( _sphereHitAt ) > ( raycaster.far - raycaster.near ) ** 2 ) return;

		}

		// convert ray to local space of mesh

		_inverseMatrix.copy( matrixWorld ).invert();
		_ray.copy( raycaster.ray ).applyMatrix4( _inverseMatrix );

		// test with bounding box in local space

		if ( geometry.boundingBox !== null ) {

			if ( _ray.intersectsBox( geometry.boundingBox ) === false ) return;

		}

		// test for intersections with geometry

		this._computeIntersections( raycaster, intersects, _ray );

	}
```
</details>

##### `_computeIntersections(raycaster: any, intersects: any, rayLocalSpace: any): void`

<details><summary>Code</summary>

```ts
_computeIntersections( raycaster, intersects, rayLocalSpace ) {

		let intersection;

		const geometry = this.geometry;
		const material = this.material;

		const index = geometry.index;
		const position = geometry.attributes.position;
		const uv = geometry.attributes.uv;
		const uv1 = geometry.attributes.uv1;
		const normal = geometry.attributes.normal;
		const groups = geometry.groups;
		const drawRange = geometry.drawRange;

		if ( index !== null ) {

			// indexed buffer geometry

			if ( Array.isArray( material ) ) {

				for ( let i = 0, il = groups.length; i < il; i ++ ) {

					const group = groups[ i ];
					const groupMaterial = material[ group.materialIndex ];

					const start = Math.max( group.start, drawRange.start );
					const end = Math.min( index.count, Math.min( ( group.start + group.count ), ( drawRange.start + drawRange.count ) ) );

					for ( let j = start, jl = end; j < jl; j += 3 ) {

						const a = index.getX( j );
						const b = index.getX( j + 1 );
						const c = index.getX( j + 2 );

						intersection = checkGeometryIntersection( this, groupMaterial, raycaster, rayLocalSpace, uv, uv1, normal, a, b, c );

						if ( intersection ) {

							intersection.faceIndex = Math.floor( j / 3 ); // triangle number in indexed buffer semantics
							intersection.face.materialIndex = group.materialIndex;
							intersects.push( intersection );

						}

					}

				}

			} else {

				const start = Math.max( 0, drawRange.start );
				const end = Math.min( index.count, ( drawRange.start + drawRange.count ) );

				for ( let i = start, il = end; i < il; i += 3 ) {

					const a = index.getX( i );
					const b = index.getX( i + 1 );
					const c = index.getX( i + 2 );

					intersection = checkGeometryIntersection( this, material, raycaster, rayLocalSpace, uv, uv1, normal, a, b, c );

					if ( intersection ) {

						intersection.faceIndex = Math.floor( i / 3 ); // triangle number in indexed buffer semantics
						intersects.push( intersection );

					}

				}

			}

		} else if ( position !== undefined ) {

			// non-indexed buffer geometry

			if ( Array.isArray( material ) ) {

				for ( let i = 0, il = groups.length; i < il; i ++ ) {

					const group = groups[ i ];
					const groupMaterial = material[ group.materialIndex ];

					const start = Math.max( group.start, drawRange.start );
					const end = Math.min( position.count, Math.min( ( group.start + group.count ), ( drawRange.start + drawRange.count ) ) );

					for ( let j = start, jl = end; j < jl; j += 3 ) {

						const a = j;
						const b = j + 1;
						const c = j + 2;

						intersection = checkGeometryIntersection( this, groupMaterial, raycaster, rayLocalSpace, uv, uv1, normal, a, b, c );

						if ( intersection ) {

							intersection.faceIndex = Math.floor( j / 3 ); // triangle number in non-indexed buffer semantics
							intersection.face.materialIndex = group.materialIndex;
							intersects.push( intersection );

						}

					}

				}

			} else {

				const start = Math.max( 0, drawRange.start );
				const end = Math.min( position.count, ( drawRange.start + drawRange.count ) );

				for ( let i = start, il = end; i < il; i += 3 ) {

					const a = i;
					const b = i + 1;
					const c = i + 2;

					intersection = checkGeometryIntersection( this, material, raycaster, rayLocalSpace, uv, uv1, normal, a, b, c );

					if ( intersection ) {

						intersection.faceIndex = Math.floor( i / 3 ); // triangle number in non-indexed buffer semantics
						intersects.push( intersection );

					}

				}

			}

		}

	}
```
</details>


---