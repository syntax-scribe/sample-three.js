[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Points.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 18 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/objects/Points.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Sphere` | `../math/Sphere.js` |
| `Ray` | `../math/Ray.js` |
| `Matrix4` | `../math/Matrix4.js` |
| `Object3D` | `../core/Object3D.js` |
| `Vector3` | `../math/Vector3.js` |
| `PointsMaterial` | `../materials/PointsMaterial.js` |
| `BufferGeometry` | `../core/BufferGeometry.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_inverseMatrix` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_ray` | `Ray` | let/var | `new Ray()` | ✗ |
| `_sphere` | `Sphere` | let/var | `new Sphere()` | ✗ |
| `_position` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `matrixWorld` | `Matrix4` | let/var | `this.matrixWorld` | ✗ |
| `threshold` | `any` | let/var | `raycaster.params.Points.threshold` | ✗ |
| `drawRange` | `{ start: number; count: number; }` | let/var | `geometry.drawRange` | ✗ |
| `localThreshold` | `number` | let/var | `threshold / ( ( this.scale.x + this.scale.y + this.scale.z ) / 3 )` | ✗ |
| `localThresholdSq` | `number` | let/var | `localThreshold * localThreshold` | ✗ |
| `index` | `BufferAttribute` | let/var | `geometry.index` | ✗ |
| `attributes` | `{ [x: string]: any; }` | let/var | `geometry.attributes` | ✗ |
| `positionAttribute` | `any` | let/var | `attributes.position` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `morphAttributes` | `any` | let/var | `geometry.morphAttributes` | ✗ |
| `morphAttribute` | `any` | let/var | `morphAttributes[ keys[ 0 ] ]` | ✗ |
| `name` | `any` | let/var | `morphAttribute[ m ].name \|\| String( m )` | ✗ |
| `intersectPoint` | `Vector3` | let/var | `new Vector3()` | ✗ |


---

## Functions

### `Points.copy(source: any, recursive: any): this`

**Parameters:**

- **`source`** `any`
- **`recursive`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `Array.isArray`
- `source.material.slice`

<details><summary>Code</summary>

```typescript
copy( source, recursive ) {

		super.copy( source, recursive );

		this.material = Array.isArray( source.material ) ? source.material.slice() : source.material;
		this.geometry = source.geometry;

		return this;

	}
```
</details>

### `Points.raycast(raycaster: Raycaster, intersects: any[]): void`

**JSDoc:**
```typescript
/**
	 * Computes intersection points between a casted ray and this point cloud.
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
- `raycaster.ray.intersectsSphere`
- `_inverseMatrix.copy( matrixWorld ).invert`
- `_ray.copy( raycaster.ray ).applyMatrix4`
- `Math.max`
- `Math.min`
- `index.getX`
- `_position.fromBufferAttribute`
- `testPoint`

**Internal Comments:**
```
// Checking boundingSphere distance to ray
// (x6)
```

<details><summary>Code</summary>

```typescript
raycast( raycaster, intersects ) {

		const geometry = this.geometry;
		const matrixWorld = this.matrixWorld;
		const threshold = raycaster.params.Points.threshold;
		const drawRange = geometry.drawRange;

		// Checking boundingSphere distance to ray

		if ( geometry.boundingSphere === null ) geometry.computeBoundingSphere();

		_sphere.copy( geometry.boundingSphere );
		_sphere.applyMatrix4( matrixWorld );
		_sphere.radius += threshold;

		if ( raycaster.ray.intersectsSphere( _sphere ) === false ) return;

		//

		_inverseMatrix.copy( matrixWorld ).invert();
		_ray.copy( raycaster.ray ).applyMatrix4( _inverseMatrix );

		const localThreshold = threshold / ( ( this.scale.x + this.scale.y + this.scale.z ) / 3 );
		const localThresholdSq = localThreshold * localThreshold;

		const index = geometry.index;
		const attributes = geometry.attributes;
		const positionAttribute = attributes.position;

		if ( index !== null ) {

			const start = Math.max( 0, drawRange.start );
			const end = Math.min( index.count, ( drawRange.start + drawRange.count ) );

			for ( let i = start, il = end; i < il; i ++ ) {

				const a = index.getX( i );

				_position.fromBufferAttribute( positionAttribute, a );

				testPoint( _position, a, localThresholdSq, matrixWorld, raycaster, intersects, this );

			}

		} else {

			const start = Math.max( 0, drawRange.start );
			const end = Math.min( positionAttribute.count, ( drawRange.start + drawRange.count ) );

			for ( let i = start, l = end; i < l; i ++ ) {

				_position.fromBufferAttribute( positionAttribute, i );

				testPoint( _position, i, localThresholdSq, matrixWorld, raycaster, intersects, this );

			}

		}

	}
```
</details>

### `Points.updateMorphTargets(): void`

**JSDoc:**
```typescript
/**
	 * Sets the values of {@link Points#morphTargetDictionary} and {@link Points#morphTargetInfluences}
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

### `testPoint(point: any, index: any, localThresholdSq: any, matrixWorld: any, raycaster: any, intersects: any, object: any): void`

**Parameters:**

- **`point`** `any`
- **`index`** `any`
- **`localThresholdSq`** `any`
- **`matrixWorld`** `any`
- **`raycaster`** `any`
- **`intersects`** `any`
- **`object`** `any`

**Returns:** `void`

**Calls:**

- `_ray.distanceSqToPoint`
- `_ray.closestPointToPoint`
- `intersectPoint.applyMatrix4`
- `raycaster.ray.origin.distanceTo`
- `intersects.push`
- `Math.sqrt`

<details><summary>Code</summary>

```typescript
function testPoint( point, index, localThresholdSq, matrixWorld, raycaster, intersects, object ) {

	const rayPointDistanceSq = _ray.distanceSqToPoint( point );

	if ( rayPointDistanceSq < localThresholdSq ) {

		const intersectPoint = new Vector3();

		_ray.closestPointToPoint( point, intersectPoint );
		intersectPoint.applyMatrix4( matrixWorld );

		const distance = raycaster.ray.origin.distanceTo( intersectPoint );

		if ( distance < raycaster.near || distance > raycaster.far ) return;

		intersects.push( {

			distance: distance,
			distanceToRay: Math.sqrt( rayPointDistanceSq ),
			point: intersectPoint,
			index: index,
			face: null,
			faceIndex: null,
			barycoord: null,
			object: object

		} );

	}

}
```
</details>


---

## Classes

### `Points`

<details><summary>Class Code</summary>

```ts
class Points extends Object3D {

	/**
	 * Constructs a new point cloud.
	 *
	 * @param {BufferGeometry} [geometry] - The points geometry.
	 * @param {Material|Array<Material>} [material] - The points material.
	 */
	constructor( geometry = new BufferGeometry(), material = new PointsMaterial() ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isPoints = true;

		this.type = 'Points';

		/**
		 * The points geometry.
		 *
		 * @type {BufferGeometry}
		 */
		this.geometry = geometry;

		/**
		 * The line material.
		 *
		 * @type {Material|Array<Material>}
		 * @default PointsMaterial
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

		this.updateMorphTargets();

	}

	copy( source, recursive ) {

		super.copy( source, recursive );

		this.material = Array.isArray( source.material ) ? source.material.slice() : source.material;
		this.geometry = source.geometry;

		return this;

	}

	/**
	 * Computes intersection points between a casted ray and this point cloud.
	 *
	 * @param {Raycaster} raycaster - The raycaster.
	 * @param {Array<Object>} intersects - The target array that holds the intersection points.
	 */
	raycast( raycaster, intersects ) {

		const geometry = this.geometry;
		const matrixWorld = this.matrixWorld;
		const threshold = raycaster.params.Points.threshold;
		const drawRange = geometry.drawRange;

		// Checking boundingSphere distance to ray

		if ( geometry.boundingSphere === null ) geometry.computeBoundingSphere();

		_sphere.copy( geometry.boundingSphere );
		_sphere.applyMatrix4( matrixWorld );
		_sphere.radius += threshold;

		if ( raycaster.ray.intersectsSphere( _sphere ) === false ) return;

		//

		_inverseMatrix.copy( matrixWorld ).invert();
		_ray.copy( raycaster.ray ).applyMatrix4( _inverseMatrix );

		const localThreshold = threshold / ( ( this.scale.x + this.scale.y + this.scale.z ) / 3 );
		const localThresholdSq = localThreshold * localThreshold;

		const index = geometry.index;
		const attributes = geometry.attributes;
		const positionAttribute = attributes.position;

		if ( index !== null ) {

			const start = Math.max( 0, drawRange.start );
			const end = Math.min( index.count, ( drawRange.start + drawRange.count ) );

			for ( let i = start, il = end; i < il; i ++ ) {

				const a = index.getX( i );

				_position.fromBufferAttribute( positionAttribute, a );

				testPoint( _position, a, localThresholdSq, matrixWorld, raycaster, intersects, this );

			}

		} else {

			const start = Math.max( 0, drawRange.start );
			const end = Math.min( positionAttribute.count, ( drawRange.start + drawRange.count ) );

			for ( let i = start, l = end; i < l; i ++ ) {

				_position.fromBufferAttribute( positionAttribute, i );

				testPoint( _position, i, localThresholdSq, matrixWorld, raycaster, intersects, this );

			}

		}

	}

	/**
	 * Sets the values of {@link Points#morphTargetDictionary} and {@link Points#morphTargetInfluences}
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

}
```
</details>

#### Methods

##### `copy(source: any, recursive: any): this`

<details><summary>Code</summary>

```ts
copy( source, recursive ) {

		super.copy( source, recursive );

		this.material = Array.isArray( source.material ) ? source.material.slice() : source.material;
		this.geometry = source.geometry;

		return this;

	}
```
</details>

##### `raycast(raycaster: Raycaster, intersects: any[]): void`

<details><summary>Code</summary>

```ts
raycast( raycaster, intersects ) {

		const geometry = this.geometry;
		const matrixWorld = this.matrixWorld;
		const threshold = raycaster.params.Points.threshold;
		const drawRange = geometry.drawRange;

		// Checking boundingSphere distance to ray

		if ( geometry.boundingSphere === null ) geometry.computeBoundingSphere();

		_sphere.copy( geometry.boundingSphere );
		_sphere.applyMatrix4( matrixWorld );
		_sphere.radius += threshold;

		if ( raycaster.ray.intersectsSphere( _sphere ) === false ) return;

		//

		_inverseMatrix.copy( matrixWorld ).invert();
		_ray.copy( raycaster.ray ).applyMatrix4( _inverseMatrix );

		const localThreshold = threshold / ( ( this.scale.x + this.scale.y + this.scale.z ) / 3 );
		const localThresholdSq = localThreshold * localThreshold;

		const index = geometry.index;
		const attributes = geometry.attributes;
		const positionAttribute = attributes.position;

		if ( index !== null ) {

			const start = Math.max( 0, drawRange.start );
			const end = Math.min( index.count, ( drawRange.start + drawRange.count ) );

			for ( let i = start, il = end; i < il; i ++ ) {

				const a = index.getX( i );

				_position.fromBufferAttribute( positionAttribute, a );

				testPoint( _position, a, localThresholdSq, matrixWorld, raycaster, intersects, this );

			}

		} else {

			const start = Math.max( 0, drawRange.start );
			const end = Math.min( positionAttribute.count, ( drawRange.start + drawRange.count ) );

			for ( let i = start, l = end; i < l; i ++ ) {

				_position.fromBufferAttribute( positionAttribute, i );

				testPoint( _position, i, localThresholdSq, matrixWorld, raycaster, intersects, this );

			}

		}

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


---