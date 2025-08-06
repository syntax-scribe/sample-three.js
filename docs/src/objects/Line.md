[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Line.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 25 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/objects/Line.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Sphere` | `../math/Sphere.js` |
| `Ray` | `../math/Ray.js` |
| `Matrix4` | `../math/Matrix4.js` |
| `Object3D` | `../core/Object3D.js` |
| `Vector3` | `../math/Vector3.js` |
| `LineBasicMaterial` | `../materials/LineBasicMaterial.js` |
| `BufferGeometry` | `../core/BufferGeometry.js` |
| `Float32BufferAttribute` | `../core/BufferAttribute.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_vStart` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_vEnd` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_inverseMatrix` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_ray` | `Ray` | let/var | `new Ray()` | ✗ |
| `_sphere` | `Sphere` | let/var | `new Sphere()` | ✗ |
| `_intersectPointOnRay` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_intersectPointOnSegment` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `positionAttribute` | `any` | let/var | `geometry.attributes.position` | ✗ |
| `lineDistances` | `number[]` | let/var | `[ 0 ]` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `matrixWorld` | `Matrix4` | let/var | `this.matrixWorld` | ✗ |
| `threshold` | `any` | let/var | `raycaster.params.Line.threshold` | ✗ |
| `drawRange` | `{ start: number; count: number; }` | let/var | `geometry.drawRange` | ✗ |
| `localThreshold` | `number` | let/var | `threshold / ( ( this.scale.x + this.scale.y + this.scale.z ) / 3 )` | ✗ |
| `localThresholdSq` | `number` | let/var | `localThreshold * localThreshold` | ✗ |
| `step` | `1 \| 2` | let/var | `this.isLineSegments ? 2 : 1` | ✗ |
| `index` | `BufferAttribute` | let/var | `geometry.index` | ✗ |
| `attributes` | `{ [x: string]: any; }` | let/var | `geometry.attributes` | ✗ |
| `positionAttribute` | `any` | let/var | `attributes.position` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `morphAttributes` | `any` | let/var | `geometry.morphAttributes` | ✗ |
| `morphAttribute` | `any` | let/var | `morphAttributes[ keys[ 0 ] ]` | ✗ |
| `name` | `any` | let/var | `morphAttribute[ m ].name \|\| String( m )` | ✗ |
| `positionAttribute` | `any` | let/var | `object.geometry.attributes.position` | ✗ |


---

## Functions

### `Line.copy(source: any, recursive: any): this`

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

### `Line.computeLineDistances(): Line`

**JSDoc:**
```typescript
/**
	 * Computes an array of distance values which are necessary for rendering dashed lines.
	 * For each vertex in the geometry, the method calculates the cumulative length from the
	 * current point to the very beginning of the line.
	 *
	 * @return {Line} A reference to this line.
	 */
```

**Returns:** `Line`

**Calls:**

- `_vStart.fromBufferAttribute`
- `_vEnd.fromBufferAttribute`
- `_vStart.distanceTo`
- `geometry.setAttribute`
- `console.warn`

**Internal Comments:**
```
// we assume non-indexed geometry
```

<details><summary>Code</summary>

```typescript
computeLineDistances() {

		const geometry = this.geometry;

		// we assume non-indexed geometry

		if ( geometry.index === null ) {

			const positionAttribute = geometry.attributes.position;
			const lineDistances = [ 0 ];

			for ( let i = 1, l = positionAttribute.count; i < l; i ++ ) {

				_vStart.fromBufferAttribute( positionAttribute, i - 1 );
				_vEnd.fromBufferAttribute( positionAttribute, i );

				lineDistances[ i ] = lineDistances[ i - 1 ];
				lineDistances[ i ] += _vStart.distanceTo( _vEnd );

			}

			geometry.setAttribute( 'lineDistance', new Float32BufferAttribute( lineDistances, 1 ) );

		} else {

			console.warn( 'THREE.Line.computeLineDistances(): Computation only possible with non-indexed BufferGeometry.' );

		}

		return this;

	}
```
</details>

### `Line.raycast(raycaster: Raycaster, intersects: any[]): void`

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
- `raycaster.ray.intersectsSphere`
- `_inverseMatrix.copy( matrixWorld ).invert`
- `_ray.copy( raycaster.ray ).applyMatrix4`
- `Math.max`
- `Math.min`
- `index.getX`
- `checkIntersection`
- `intersects.push`

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
		const threshold = raycaster.params.Line.threshold;
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

		const step = this.isLineSegments ? 2 : 1;

		const index = geometry.index;
		const attributes = geometry.attributes;
		const positionAttribute = attributes.position;

		if ( index !== null ) {

			const start = Math.max( 0, drawRange.start );
			const end = Math.min( index.count, ( drawRange.start + drawRange.count ) );

			for ( let i = start, l = end - 1; i < l; i += step ) {

				const a = index.getX( i );
				const b = index.getX( i + 1 );

				const intersect = checkIntersection( this, raycaster, _ray, localThresholdSq, a, b, i );

				if ( intersect ) {

					intersects.push( intersect );

				}

			}

			if ( this.isLineLoop ) {

				const a = index.getX( end - 1 );
				const b = index.getX( start );

				const intersect = checkIntersection( this, raycaster, _ray, localThresholdSq, a, b, end - 1 );

				if ( intersect ) {

					intersects.push( intersect );

				}

			}

		} else {

			const start = Math.max( 0, drawRange.start );
			const end = Math.min( positionAttribute.count, ( drawRange.start + drawRange.count ) );

			for ( let i = start, l = end - 1; i < l; i += step ) {

				const intersect = checkIntersection( this, raycaster, _ray, localThresholdSq, i, i + 1, i );

				if ( intersect ) {

					intersects.push( intersect );

				}

			}

			if ( this.isLineLoop ) {

				const intersect = checkIntersection( this, raycaster, _ray, localThresholdSq, end - 1, start, end - 1 );

				if ( intersect ) {

					intersects.push( intersect );

				}

			}

		}

	}
```
</details>

### `Line.updateMorphTargets(): void`

**JSDoc:**
```typescript
/**
	 * Sets the values of {@link Line#morphTargetDictionary} and {@link Line#morphTargetInfluences}
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

### `checkIntersection(object: any, raycaster: any, ray: any, thresholdSq: any, a: any, b: any, i: any): { distance: any; point: Vector3; index: any; face: any; faceIndex: any; barycoord: any; object: any; }`

**Parameters:**

- **`object`** `any`
- **`raycaster`** `any`
- **`ray`** `any`
- **`thresholdSq`** `any`
- **`a`** `any`
- **`b`** `any`
- **`i`** `any`

**Returns:** `{ distance: any; point: Vector3; index: any; face: any; faceIndex: any; barycoord: any; object: any; }`

**Calls:**

- `_vStart.fromBufferAttribute`
- `_vEnd.fromBufferAttribute`
- `ray.distanceSqToSegment`
- `_intersectPointOnRay.applyMatrix4`
- `raycaster.ray.origin.distanceTo`
- `_intersectPointOnSegment.clone().applyMatrix4`

**Internal Comments:**
```
// What do we want? intersection point on the ray or on the segment?? (x2)
// point: raycaster.ray.at( distance ), (x2)
```

<details><summary>Code</summary>

```typescript
function checkIntersection( object, raycaster, ray, thresholdSq, a, b, i ) {

	const positionAttribute = object.geometry.attributes.position;

	_vStart.fromBufferAttribute( positionAttribute, a );
	_vEnd.fromBufferAttribute( positionAttribute, b );

	const distSq = ray.distanceSqToSegment( _vStart, _vEnd, _intersectPointOnRay, _intersectPointOnSegment );

	if ( distSq > thresholdSq ) return;

	_intersectPointOnRay.applyMatrix4( object.matrixWorld ); // Move back to world space for distance calculation

	const distance = raycaster.ray.origin.distanceTo( _intersectPointOnRay );

	if ( distance < raycaster.near || distance > raycaster.far ) return;

	return {

		distance: distance,
		// What do we want? intersection point on the ray or on the segment??
		// point: raycaster.ray.at( distance ),
		point: _intersectPointOnSegment.clone().applyMatrix4( object.matrixWorld ),
		index: i,
		face: null,
		faceIndex: null,
		barycoord: null,
		object: object

	};

}
```
</details>


---

## Classes

### `Line`

<details><summary>Class Code</summary>

```ts
class Line extends Object3D {

	/**
	 * Constructs a new line.
	 *
	 * @param {BufferGeometry} [geometry] - The line geometry.
	 * @param {Material|Array<Material>} [material] - The line material.
	 */
	constructor( geometry = new BufferGeometry(), material = new LineBasicMaterial() ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isLine = true;

		this.type = 'Line';

		/**
		 * The line geometry.
		 *
		 * @type {BufferGeometry}
		 */
		this.geometry = geometry;

		/**
		 * The line material.
		 *
		 * @type {Material|Array<Material>}
		 * @default LineBasicMaterial
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
	 * Computes an array of distance values which are necessary for rendering dashed lines.
	 * For each vertex in the geometry, the method calculates the cumulative length from the
	 * current point to the very beginning of the line.
	 *
	 * @return {Line} A reference to this line.
	 */
	computeLineDistances() {

		const geometry = this.geometry;

		// we assume non-indexed geometry

		if ( geometry.index === null ) {

			const positionAttribute = geometry.attributes.position;
			const lineDistances = [ 0 ];

			for ( let i = 1, l = positionAttribute.count; i < l; i ++ ) {

				_vStart.fromBufferAttribute( positionAttribute, i - 1 );
				_vEnd.fromBufferAttribute( positionAttribute, i );

				lineDistances[ i ] = lineDistances[ i - 1 ];
				lineDistances[ i ] += _vStart.distanceTo( _vEnd );

			}

			geometry.setAttribute( 'lineDistance', new Float32BufferAttribute( lineDistances, 1 ) );

		} else {

			console.warn( 'THREE.Line.computeLineDistances(): Computation only possible with non-indexed BufferGeometry.' );

		}

		return this;

	}

	/**
	 * Computes intersection points between a casted ray and this line.
	 *
	 * @param {Raycaster} raycaster - The raycaster.
	 * @param {Array<Object>} intersects - The target array that holds the intersection points.
	 */
	raycast( raycaster, intersects ) {

		const geometry = this.geometry;
		const matrixWorld = this.matrixWorld;
		const threshold = raycaster.params.Line.threshold;
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

		const step = this.isLineSegments ? 2 : 1;

		const index = geometry.index;
		const attributes = geometry.attributes;
		const positionAttribute = attributes.position;

		if ( index !== null ) {

			const start = Math.max( 0, drawRange.start );
			const end = Math.min( index.count, ( drawRange.start + drawRange.count ) );

			for ( let i = start, l = end - 1; i < l; i += step ) {

				const a = index.getX( i );
				const b = index.getX( i + 1 );

				const intersect = checkIntersection( this, raycaster, _ray, localThresholdSq, a, b, i );

				if ( intersect ) {

					intersects.push( intersect );

				}

			}

			if ( this.isLineLoop ) {

				const a = index.getX( end - 1 );
				const b = index.getX( start );

				const intersect = checkIntersection( this, raycaster, _ray, localThresholdSq, a, b, end - 1 );

				if ( intersect ) {

					intersects.push( intersect );

				}

			}

		} else {

			const start = Math.max( 0, drawRange.start );
			const end = Math.min( positionAttribute.count, ( drawRange.start + drawRange.count ) );

			for ( let i = start, l = end - 1; i < l; i += step ) {

				const intersect = checkIntersection( this, raycaster, _ray, localThresholdSq, i, i + 1, i );

				if ( intersect ) {

					intersects.push( intersect );

				}

			}

			if ( this.isLineLoop ) {

				const intersect = checkIntersection( this, raycaster, _ray, localThresholdSq, end - 1, start, end - 1 );

				if ( intersect ) {

					intersects.push( intersect );

				}

			}

		}

	}

	/**
	 * Sets the values of {@link Line#morphTargetDictionary} and {@link Line#morphTargetInfluences}
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

##### `computeLineDistances(): Line`

<details><summary>Code</summary>

```ts
computeLineDistances() {

		const geometry = this.geometry;

		// we assume non-indexed geometry

		if ( geometry.index === null ) {

			const positionAttribute = geometry.attributes.position;
			const lineDistances = [ 0 ];

			for ( let i = 1, l = positionAttribute.count; i < l; i ++ ) {

				_vStart.fromBufferAttribute( positionAttribute, i - 1 );
				_vEnd.fromBufferAttribute( positionAttribute, i );

				lineDistances[ i ] = lineDistances[ i - 1 ];
				lineDistances[ i ] += _vStart.distanceTo( _vEnd );

			}

			geometry.setAttribute( 'lineDistance', new Float32BufferAttribute( lineDistances, 1 ) );

		} else {

			console.warn( 'THREE.Line.computeLineDistances(): Computation only possible with non-indexed BufferGeometry.' );

		}

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
		const threshold = raycaster.params.Line.threshold;
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

		const step = this.isLineSegments ? 2 : 1;

		const index = geometry.index;
		const attributes = geometry.attributes;
		const positionAttribute = attributes.position;

		if ( index !== null ) {

			const start = Math.max( 0, drawRange.start );
			const end = Math.min( index.count, ( drawRange.start + drawRange.count ) );

			for ( let i = start, l = end - 1; i < l; i += step ) {

				const a = index.getX( i );
				const b = index.getX( i + 1 );

				const intersect = checkIntersection( this, raycaster, _ray, localThresholdSq, a, b, i );

				if ( intersect ) {

					intersects.push( intersect );

				}

			}

			if ( this.isLineLoop ) {

				const a = index.getX( end - 1 );
				const b = index.getX( start );

				const intersect = checkIntersection( this, raycaster, _ray, localThresholdSq, a, b, end - 1 );

				if ( intersect ) {

					intersects.push( intersect );

				}

			}

		} else {

			const start = Math.max( 0, drawRange.start );
			const end = Math.min( positionAttribute.count, ( drawRange.start + drawRange.count ) );

			for ( let i = start, l = end - 1; i < l; i += step ) {

				const intersect = checkIntersection( this, raycaster, _ray, localThresholdSq, i, i + 1, i );

				if ( intersect ) {

					intersects.push( intersect );

				}

			}

			if ( this.isLineLoop ) {

				const intersect = checkIntersection( this, raycaster, _ray, localThresholdSq, end - 1, start, end - 1 );

				if ( intersect ) {

					intersects.push( intersect );

				}

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