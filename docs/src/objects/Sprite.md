[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Sprite.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 19 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/objects/Sprite.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector2` | `../math/Vector2.js` |
| `Vector3` | `../math/Vector3.js` |
| `Matrix4` | `../math/Matrix4.js` |
| `Triangle` | `../math/Triangle.js` |
| `Object3D` | `../core/Object3D.js` |
| `BufferGeometry` | `../core/BufferGeometry.js` |
| `InterleavedBuffer` | `../core/InterleavedBuffer.js` |
| `InterleavedBufferAttribute` | `../core/InterleavedBufferAttribute.js` |
| `SpriteMaterial` | `../materials/SpriteMaterial.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_geometry` | `any` | let/var | `*not shown*` | ✗ |
| `_intersectPoint` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_worldScale` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_mvPosition` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_alignedPosition` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `_rotatedPosition` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `_viewWorldMatrix` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_vA` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_vB` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_vC` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_uvA` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `_uvB` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `_uvC` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `float32Array` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( [ - 0.5, - 0.5, 0, 0, 0, 0.5, - 0.5, 0, 1, 0, 0.5, 0.5, 0, ...` | ✗ |
| `interleavedBuffer` | `InterleavedBuffer` | let/var | `new InterleavedBuffer( float32Array, 5 )` | ✗ |
| `rotation` | `number` | let/var | `this.material.rotation` | ✗ |
| `sin` | `any` | let/var | `*not shown*` | ✗ |
| `cos` | `any` | let/var | `*not shown*` | ✗ |
| `center` | `Vector2` | let/var | `this.center` | ✗ |


---

## Functions

### `Sprite.raycast(raycaster: Raycaster, intersects: any[]): void`

**JSDoc:**
```typescript
/**
	 * Computes intersection points between a casted ray and this sprite.
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

- `console.error`
- `_worldScale.setFromMatrixScale`
- `_viewWorldMatrix.copy`
- `this.modelViewMatrix.multiplyMatrices`
- `_mvPosition.setFromMatrixPosition`
- `_worldScale.multiplyScalar`
- `Math.cos`
- `Math.sin`
- `transformVertex`
- `_vA.set`
- `_vB.set`
- `_vC.set`
- `_uvA.set`
- `_uvB.set`
- `_uvC.set`
- `raycaster.ray.intersectTriangle`
- `raycaster.ray.origin.distanceTo`
- `intersects.push`
- `_intersectPoint.clone`
- `Triangle.getInterpolation`

**Internal Comments:**
```
// check first triangle (x2)
// check second triangle (x3)
```

<details><summary>Code</summary>

```typescript
raycast( raycaster, intersects ) {

		if ( raycaster.camera === null ) {

			console.error( 'THREE.Sprite: "Raycaster.camera" needs to be set in order to raycast against sprites.' );

		}

		_worldScale.setFromMatrixScale( this.matrixWorld );

		_viewWorldMatrix.copy( raycaster.camera.matrixWorld );
		this.modelViewMatrix.multiplyMatrices( raycaster.camera.matrixWorldInverse, this.matrixWorld );

		_mvPosition.setFromMatrixPosition( this.modelViewMatrix );

		if ( raycaster.camera.isPerspectiveCamera && this.material.sizeAttenuation === false ) {

			_worldScale.multiplyScalar( - _mvPosition.z );

		}

		const rotation = this.material.rotation;
		let sin, cos;

		if ( rotation !== 0 ) {

			cos = Math.cos( rotation );
			sin = Math.sin( rotation );

		}

		const center = this.center;

		transformVertex( _vA.set( - 0.5, - 0.5, 0 ), _mvPosition, center, _worldScale, sin, cos );
		transformVertex( _vB.set( 0.5, - 0.5, 0 ), _mvPosition, center, _worldScale, sin, cos );
		transformVertex( _vC.set( 0.5, 0.5, 0 ), _mvPosition, center, _worldScale, sin, cos );

		_uvA.set( 0, 0 );
		_uvB.set( 1, 0 );
		_uvC.set( 1, 1 );

		// check first triangle
		let intersect = raycaster.ray.intersectTriangle( _vA, _vB, _vC, false, _intersectPoint );

		if ( intersect === null ) {

			// check second triangle
			transformVertex( _vB.set( - 0.5, 0.5, 0 ), _mvPosition, center, _worldScale, sin, cos );
			_uvB.set( 0, 1 );

			intersect = raycaster.ray.intersectTriangle( _vA, _vC, _vB, false, _intersectPoint );
			if ( intersect === null ) {

				return;

			}

		}

		const distance = raycaster.ray.origin.distanceTo( _intersectPoint );

		if ( distance < raycaster.near || distance > raycaster.far ) return;

		intersects.push( {

			distance: distance,
			point: _intersectPoint.clone(),
			uv: Triangle.getInterpolation( _intersectPoint, _vA, _vB, _vC, _uvA, _uvB, _uvC, new Vector2() ),
			face: null,
			object: this

		} );

	}
```
</details>

### `Sprite.copy(source: any, recursive: any): this`

**Parameters:**

- **`source`** `any`
- **`recursive`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.center.copy`

<details><summary>Code</summary>

```typescript
copy( source, recursive ) {

		super.copy( source, recursive );

		if ( source.center !== undefined ) this.center.copy( source.center );

		this.material = source.material;

		return this;

	}
```
</details>

### `transformVertex(vertexPosition: any, mvPosition: any, center: any, scale: any, sin: any, cos: any): void`

**Parameters:**

- **`vertexPosition`** `any`
- **`mvPosition`** `any`
- **`center`** `any`
- **`scale`** `any`
- **`sin`** `any`
- **`cos`** `any`

**Returns:** `void`

**Calls:**

- `_alignedPosition.subVectors( vertexPosition, center ).addScalar( 0.5 ).multiply`
- `_rotatedPosition.copy`
- `vertexPosition.copy`
- `vertexPosition.applyMatrix4`

**Internal Comments:**
```
// compute position in camera space (x8)
// to check if rotation is not zero
// transform to world space (x4)
```

<details><summary>Code</summary>

```typescript
function transformVertex( vertexPosition, mvPosition, center, scale, sin, cos ) {

	// compute position in camera space
	_alignedPosition.subVectors( vertexPosition, center ).addScalar( 0.5 ).multiply( scale );

	// to check if rotation is not zero
	if ( sin !== undefined ) {

		_rotatedPosition.x = ( cos * _alignedPosition.x ) - ( sin * _alignedPosition.y );
		_rotatedPosition.y = ( sin * _alignedPosition.x ) + ( cos * _alignedPosition.y );

	} else {

		_rotatedPosition.copy( _alignedPosition );

	}


	vertexPosition.copy( mvPosition );
	vertexPosition.x += _rotatedPosition.x;
	vertexPosition.y += _rotatedPosition.y;

	// transform to world space
	vertexPosition.applyMatrix4( _viewWorldMatrix );

}
```
</details>


---

## Classes

### `Sprite`

<details><summary>Class Code</summary>

```ts
class Sprite extends Object3D {

	/**
	 * Constructs a new sprite.
	 *
	 * @param {SpriteMaterial} [material] - The sprite material.
	 */
	constructor( material = new SpriteMaterial() ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSprite = true;

		this.type = 'Sprite';

		if ( _geometry === undefined ) {

			_geometry = new BufferGeometry();

			const float32Array = new Float32Array( [
				- 0.5, - 0.5, 0, 0, 0,
				0.5, - 0.5, 0, 1, 0,
				0.5, 0.5, 0, 1, 1,
				- 0.5, 0.5, 0, 0, 1
			] );

			const interleavedBuffer = new InterleavedBuffer( float32Array, 5 );

			_geometry.setIndex( [ 0, 1, 2,	0, 2, 3 ] );
			_geometry.setAttribute( 'position', new InterleavedBufferAttribute( interleavedBuffer, 3, 0, false ) );
			_geometry.setAttribute( 'uv', new InterleavedBufferAttribute( interleavedBuffer, 2, 3, false ) );

		}

		/**
		 * The sprite geometry.
		 *
		 * @type {BufferGeometry}
		 */
		this.geometry = _geometry;

		/**
		 * The sprite material.
		 *
		 * @type {SpriteMaterial}
		 */
		this.material = material;

		/**
		 * The sprite's anchor point, and the point around which the sprite rotates.
		 * A value of `(0.5, 0.5)` corresponds to the midpoint of the sprite. A value
		 * of `(0, 0)` corresponds to the lower left corner of the sprite.
		 *
		 * @type {Vector2}
		 * @default (0.5,0.5)
		 */
		this.center = new Vector2( 0.5, 0.5 );

		/**
		 * The number of instances of this sprite.
		 * Can only be used with {@link WebGPURenderer}.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.count = 1;

	}

	/**
	 * Computes intersection points between a casted ray and this sprite.
	 *
	 * @param {Raycaster} raycaster - The raycaster.
	 * @param {Array<Object>} intersects - The target array that holds the intersection points.
	 */
	raycast( raycaster, intersects ) {

		if ( raycaster.camera === null ) {

			console.error( 'THREE.Sprite: "Raycaster.camera" needs to be set in order to raycast against sprites.' );

		}

		_worldScale.setFromMatrixScale( this.matrixWorld );

		_viewWorldMatrix.copy( raycaster.camera.matrixWorld );
		this.modelViewMatrix.multiplyMatrices( raycaster.camera.matrixWorldInverse, this.matrixWorld );

		_mvPosition.setFromMatrixPosition( this.modelViewMatrix );

		if ( raycaster.camera.isPerspectiveCamera && this.material.sizeAttenuation === false ) {

			_worldScale.multiplyScalar( - _mvPosition.z );

		}

		const rotation = this.material.rotation;
		let sin, cos;

		if ( rotation !== 0 ) {

			cos = Math.cos( rotation );
			sin = Math.sin( rotation );

		}

		const center = this.center;

		transformVertex( _vA.set( - 0.5, - 0.5, 0 ), _mvPosition, center, _worldScale, sin, cos );
		transformVertex( _vB.set( 0.5, - 0.5, 0 ), _mvPosition, center, _worldScale, sin, cos );
		transformVertex( _vC.set( 0.5, 0.5, 0 ), _mvPosition, center, _worldScale, sin, cos );

		_uvA.set( 0, 0 );
		_uvB.set( 1, 0 );
		_uvC.set( 1, 1 );

		// check first triangle
		let intersect = raycaster.ray.intersectTriangle( _vA, _vB, _vC, false, _intersectPoint );

		if ( intersect === null ) {

			// check second triangle
			transformVertex( _vB.set( - 0.5, 0.5, 0 ), _mvPosition, center, _worldScale, sin, cos );
			_uvB.set( 0, 1 );

			intersect = raycaster.ray.intersectTriangle( _vA, _vC, _vB, false, _intersectPoint );
			if ( intersect === null ) {

				return;

			}

		}

		const distance = raycaster.ray.origin.distanceTo( _intersectPoint );

		if ( distance < raycaster.near || distance > raycaster.far ) return;

		intersects.push( {

			distance: distance,
			point: _intersectPoint.clone(),
			uv: Triangle.getInterpolation( _intersectPoint, _vA, _vB, _vC, _uvA, _uvB, _uvC, new Vector2() ),
			face: null,
			object: this

		} );

	}

	copy( source, recursive ) {

		super.copy( source, recursive );

		if ( source.center !== undefined ) this.center.copy( source.center );

		this.material = source.material;

		return this;

	}

}
```
</details>

#### Methods

##### `raycast(raycaster: Raycaster, intersects: any[]): void`

<details><summary>Code</summary>

```ts
raycast( raycaster, intersects ) {

		if ( raycaster.camera === null ) {

			console.error( 'THREE.Sprite: "Raycaster.camera" needs to be set in order to raycast against sprites.' );

		}

		_worldScale.setFromMatrixScale( this.matrixWorld );

		_viewWorldMatrix.copy( raycaster.camera.matrixWorld );
		this.modelViewMatrix.multiplyMatrices( raycaster.camera.matrixWorldInverse, this.matrixWorld );

		_mvPosition.setFromMatrixPosition( this.modelViewMatrix );

		if ( raycaster.camera.isPerspectiveCamera && this.material.sizeAttenuation === false ) {

			_worldScale.multiplyScalar( - _mvPosition.z );

		}

		const rotation = this.material.rotation;
		let sin, cos;

		if ( rotation !== 0 ) {

			cos = Math.cos( rotation );
			sin = Math.sin( rotation );

		}

		const center = this.center;

		transformVertex( _vA.set( - 0.5, - 0.5, 0 ), _mvPosition, center, _worldScale, sin, cos );
		transformVertex( _vB.set( 0.5, - 0.5, 0 ), _mvPosition, center, _worldScale, sin, cos );
		transformVertex( _vC.set( 0.5, 0.5, 0 ), _mvPosition, center, _worldScale, sin, cos );

		_uvA.set( 0, 0 );
		_uvB.set( 1, 0 );
		_uvC.set( 1, 1 );

		// check first triangle
		let intersect = raycaster.ray.intersectTriangle( _vA, _vB, _vC, false, _intersectPoint );

		if ( intersect === null ) {

			// check second triangle
			transformVertex( _vB.set( - 0.5, 0.5, 0 ), _mvPosition, center, _worldScale, sin, cos );
			_uvB.set( 0, 1 );

			intersect = raycaster.ray.intersectTriangle( _vA, _vC, _vB, false, _intersectPoint );
			if ( intersect === null ) {

				return;

			}

		}

		const distance = raycaster.ray.origin.distanceTo( _intersectPoint );

		if ( distance < raycaster.near || distance > raycaster.far ) return;

		intersects.push( {

			distance: distance,
			point: _intersectPoint.clone(),
			uv: Triangle.getInterpolation( _intersectPoint, _vA, _vB, _vC, _uvA, _uvB, _uvC, new Vector2() ),
			face: null,
			object: this

		} );

	}
```
</details>

##### `copy(source: any, recursive: any): this`

<details><summary>Code</summary>

```ts
copy( source, recursive ) {

		super.copy( source, recursive );

		if ( source.center !== undefined ) this.center.copy( source.center );

		this.material = source.material;

		return this;

	}
```
</details>


---