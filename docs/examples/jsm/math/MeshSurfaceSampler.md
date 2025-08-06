[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MeshSurfaceSampler.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 7 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 25 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/math/MeshSurfaceSampler.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Triangle` | `three` |
| `Vector2` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_face` | `any` | let/var | `new Triangle()` | ✗ |
| `_color` | `any` | let/var | `new Vector3()` | ✗ |
| `_uva` | `any` | let/var | `new Vector2()` | ✗ |
| `_uvb` | `any` | let/var | `new Vector2()` | ✗ |
| `_uvc` | `any` | let/var | `new Vector2()` | ✗ |
| `indexAttribute` | `any` | let/var | `this.indexAttribute` | ✗ |
| `positionAttribute` | `any` | let/var | `this.positionAttribute` | ✗ |
| `weightAttribute` | `any` | let/var | `this.weightAttribute` | ✗ |
| `totalFaces` | `number` | let/var | `indexAttribute ? ( indexAttribute.count / 3 ) : ( positionAttribute.count / 3 )` | ✗ |
| `faceWeights` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( totalFaces )` | ✗ |
| `faceWeight` | `number` | let/var | `1` | ✗ |
| `i0` | `number` | let/var | `3 * i` | ✗ |
| `i1` | `number` | let/var | `3 * i + 1` | ✗ |
| `i2` | `number` | let/var | `3 * i + 2` | ✗ |
| `distribution` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( totalFaces )` | ✗ |
| `cumulativeTotal` | `number` | let/var | `0` | ✗ |
| `cumulativeTotal` | `number` | let/var | `this.distribution[ this.distribution.length - 1 ]` | ✗ |
| `dist` | `Float32Array<ArrayBuffer>` | let/var | `this.distribution` | ✗ |
| `start` | `number` | let/var | `0` | ✗ |
| `end` | `number` | let/var | `dist.length - 1` | ✗ |
| `index` | `number` | let/var | `- 1` | ✗ |
| `indexAttribute` | `any` | let/var | `this.indexAttribute` | ✗ |
| `i0` | `number` | let/var | `faceIndex * 3` | ✗ |
| `i1` | `number` | let/var | `faceIndex * 3 + 1` | ✗ |
| `i2` | `number` | let/var | `faceIndex * 3 + 2` | ✗ |


---

## Functions

### `MeshSurfaceSampler.setWeightAttribute(name: string): MeshSurfaceSampler`

**JSDoc:**
```typescript
/**
	 * Specifies a vertex attribute to be used as a weight when sampling from the surface.
	 * Faces with higher weights are more likely to be sampled, and those with weights of
	 * zero will not be sampled at all. For vector attributes, only .x is used in sampling.
	 *
	 * If no weight attribute is selected, sampling is randomly distributed by area.
	 *
	 * @param {string} name - The attribute name.
	 * @return {MeshSurfaceSampler} A reference to this sampler.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `MeshSurfaceSampler`

**Calls:**

- `this.geometry.getAttribute`

<details><summary>Code</summary>

```typescript
setWeightAttribute( name ) {

		this.weightAttribute = name ? this.geometry.getAttribute( name ) : null;

		return this;

	}
```
</details>

### `MeshSurfaceSampler.build(): MeshSurfaceSampler`

**JSDoc:**
```typescript
/**
	 * Processes the input geometry and prepares to return samples. Any configuration of the
	 * geometry or sampler must occur before this method is called. Time complexity is O(n)
	 * for a surface with n faces.
	 *
	 * @return {MeshSurfaceSampler} A reference to this sampler.
	 */
```

**Returns:** `MeshSurfaceSampler`

**Calls:**

- `indexAttribute.getX`
- `weightAttribute.getX`
- `_face.a.fromBufferAttribute`
- `_face.b.fromBufferAttribute`
- `_face.c.fromBufferAttribute`
- `_face.getArea`

**Internal Comments:**
```
// Accumulate weights for each mesh face.
// Store cumulative total face weights in an array, where weight index (x2)
// corresponds to face index. (x2)
```

<details><summary>Code</summary>

```typescript
build() {

		const indexAttribute = this.indexAttribute;
		const positionAttribute = this.positionAttribute;
		const weightAttribute = this.weightAttribute;

		const totalFaces = indexAttribute ? ( indexAttribute.count / 3 ) : ( positionAttribute.count / 3 );
		const faceWeights = new Float32Array( totalFaces );

		// Accumulate weights for each mesh face.

		for ( let i = 0; i < totalFaces; i ++ ) {

			let faceWeight = 1;

			let i0 = 3 * i;
			let i1 = 3 * i + 1;
			let i2 = 3 * i + 2;

			if ( indexAttribute ) {

				i0 = indexAttribute.getX( i0 );
				i1 = indexAttribute.getX( i1 );
				i2 = indexAttribute.getX( i2 );

			}

			if ( weightAttribute ) {

				faceWeight = weightAttribute.getX( i0 )
					+ weightAttribute.getX( i1 )
					+ weightAttribute.getX( i2 );

			}

			_face.a.fromBufferAttribute( positionAttribute, i0 );
			_face.b.fromBufferAttribute( positionAttribute, i1 );
			_face.c.fromBufferAttribute( positionAttribute, i2 );
			faceWeight *= _face.getArea();

			faceWeights[ i ] = faceWeight;

		}

		// Store cumulative total face weights in an array, where weight index
		// corresponds to face index.

		const distribution = new Float32Array( totalFaces );
		let cumulativeTotal = 0;

		for ( let i = 0; i < totalFaces; i ++ ) {

			cumulativeTotal += faceWeights[ i ];
			distribution[ i ] = cumulativeTotal;

		}

		this.distribution = distribution;
		return this;

	}
```
</details>

### `MeshSurfaceSampler.setRandomGenerator(randomFunction: Function): MeshSurfaceSampler`

**JSDoc:**
```typescript
/**
	 * Allows to set a custom random number generator. Default is `Math.random()`.
	 *
	 * @param {Function} randomFunction - A random number generator.
	 * @return {MeshSurfaceSampler} A reference to this sampler.
	 */
```

**Parameters:**

- **`randomFunction`** `Function`

**Returns:** `MeshSurfaceSampler`

<details><summary>Code</summary>

```typescript
setRandomGenerator( randomFunction ) {

		this.randomFunction = randomFunction;
		return this;

	}
```
</details>

### `MeshSurfaceSampler.sample(targetPosition: Vector3, targetNormal: Vector3, targetColor: Color, targetUV: Vector2): MeshSurfaceSampler`

**JSDoc:**
```typescript
/**
	 * Selects a random point on the surface of the input geometry, returning the
	 * position and optionally the normal vector, color and UV Coordinate at that point.
	 * Time complexity is O(log n) for a surface with n faces.
	 *
	 * @param {Vector3} targetPosition - The target object holding the sampled position.
	 * @param {Vector3} targetNormal - The target object holding the sampled normal.
	 * @param {Color} targetColor - The target object holding the sampled color.
	 * @param {Vector2} targetUV -  The target object holding the sampled uv coordinates.
	 * @return {MeshSurfaceSampler} A reference to this sampler.
	 */
```

**Parameters:**

- **`targetPosition`** `Vector3`
- **`targetNormal`** `Vector3`
- **`targetColor`** `Color`
- **`targetUV`** `Vector2`

**Returns:** `MeshSurfaceSampler`

**Calls:**

- `this._sampleFaceIndex`
- `this._sampleFace`

<details><summary>Code</summary>

```typescript
sample( targetPosition, targetNormal, targetColor, targetUV ) {

		const faceIndex = this._sampleFaceIndex();
		return this._sampleFace( faceIndex, targetPosition, targetNormal, targetColor, targetUV );

	}
```
</details>

### `MeshSurfaceSampler._sampleFaceIndex(): number`

**Returns:** `number`

**Calls:**

- `this._binarySearch`
- `this.randomFunction`

<details><summary>Code</summary>

```typescript
_sampleFaceIndex() {

		const cumulativeTotal = this.distribution[ this.distribution.length - 1 ];
		return this._binarySearch( this.randomFunction() * cumulativeTotal );

	}
```
</details>

### `MeshSurfaceSampler._binarySearch(x: any): number`

**Parameters:**

- **`x`** `any`

**Returns:** `number`

**Calls:**

- `Math.ceil`

<details><summary>Code</summary>

```typescript
_binarySearch( x ) {

		const dist = this.distribution;
		let start = 0;
		let end = dist.length - 1;

		let index = - 1;

		while ( start <= end ) {

			const mid = Math.ceil( ( start + end ) / 2 );

			if ( mid === 0 || dist[ mid - 1 ] <= x && dist[ mid ] > x ) {

				index = mid;

				break;

			} else if ( x < dist[ mid ] ) {

				end = mid - 1;

			} else {

				start = mid + 1;

			}

		}

		return index;

	}
```
</details>

### `MeshSurfaceSampler._sampleFace(faceIndex: any, targetPosition: any, targetNormal: any, targetColor: any, targetUV: any): this`

**Parameters:**

- **`faceIndex`** `any`
- **`targetPosition`** `any`
- **`targetNormal`** `any`
- **`targetColor`** `any`
- **`targetUV`** `any`

**Returns:** `this`

**Calls:**

- `this.randomFunction`
- `indexAttribute.getX`
- `_face.a.fromBufferAttribute`
- `_face.b.fromBufferAttribute`
- `_face.c.fromBufferAttribute`
- `targetPosition
			.set( 0, 0, 0 )
			.addScaledVector( _face.a, u )
			.addScaledVector( _face.b, v )
			.addScaledVector`
- `targetNormal.set( 0, 0, 0 ).addScaledVector( _face.a, u ).addScaledVector( _face.b, v ).addScaledVector( _face.c, 1 - ( u + v ) ).normalize`
- `_face.getNormal`
- `_color
				.set( 0, 0, 0 )
				.addScaledVector( _face.a, u )
				.addScaledVector( _face.b, v )
				.addScaledVector`
- `_uva.fromBufferAttribute`
- `_uvb.fromBufferAttribute`
- `_uvc.fromBufferAttribute`
- `targetUV.set( 0, 0 ).addScaledVector( _uva, u ).addScaledVector( _uvb, v ).addScaledVector`

**Internal Comments:**
```
// get the vertex attribute indices (x2)
```

<details><summary>Code</summary>

```typescript
_sampleFace( faceIndex, targetPosition, targetNormal, targetColor, targetUV ) {

		let u = this.randomFunction();
		let v = this.randomFunction();

		if ( u + v > 1 ) {

			u = 1 - u;
			v = 1 - v;

		}

		// get the vertex attribute indices
		const indexAttribute = this.indexAttribute;
		let i0 = faceIndex * 3;
		let i1 = faceIndex * 3 + 1;
		let i2 = faceIndex * 3 + 2;
		if ( indexAttribute ) {

			i0 = indexAttribute.getX( i0 );
			i1 = indexAttribute.getX( i1 );
			i2 = indexAttribute.getX( i2 );

		}

		_face.a.fromBufferAttribute( this.positionAttribute, i0 );
		_face.b.fromBufferAttribute( this.positionAttribute, i1 );
		_face.c.fromBufferAttribute( this.positionAttribute, i2 );

		targetPosition
			.set( 0, 0, 0 )
			.addScaledVector( _face.a, u )
			.addScaledVector( _face.b, v )
			.addScaledVector( _face.c, 1 - ( u + v ) );

		if ( targetNormal !== undefined ) {

			if ( this.normalAttribute !== undefined ) {

				_face.a.fromBufferAttribute( this.normalAttribute, i0 );
				_face.b.fromBufferAttribute( this.normalAttribute, i1 );
				_face.c.fromBufferAttribute( this.normalAttribute, i2 );
				targetNormal.set( 0, 0, 0 ).addScaledVector( _face.a, u ).addScaledVector( _face.b, v ).addScaledVector( _face.c, 1 - ( u + v ) ).normalize();

			} else {

				_face.getNormal( targetNormal );

			}

		}

		if ( targetColor !== undefined && this.colorAttribute !== undefined ) {

			_face.a.fromBufferAttribute( this.colorAttribute, i0 );
			_face.b.fromBufferAttribute( this.colorAttribute, i1 );
			_face.c.fromBufferAttribute( this.colorAttribute, i2 );

			_color
				.set( 0, 0, 0 )
				.addScaledVector( _face.a, u )
				.addScaledVector( _face.b, v )
				.addScaledVector( _face.c, 1 - ( u + v ) );

			targetColor.r = _color.x;
			targetColor.g = _color.y;
			targetColor.b = _color.z;

		}

		if ( targetUV !== undefined && this.uvAttribute !== undefined ) {

			_uva.fromBufferAttribute( this.uvAttribute, i0 );
			_uvb.fromBufferAttribute( this.uvAttribute, i1 );
			_uvc.fromBufferAttribute( this.uvAttribute, i2 );
			targetUV.set( 0, 0 ).addScaledVector( _uva, u ).addScaledVector( _uvb, v ).addScaledVector( _uvc, 1 - ( u + v ) );

		}

		return this;

	}
```
</details>


---

## Classes

### `MeshSurfaceSampler`

<details><summary>Class Code</summary>

```ts
class MeshSurfaceSampler {

	/**
	 * Constructs a mesh surface sampler.
	 *
	 * @param {Mesh} mesh - Surface mesh from which to sample.
	 */
	constructor( mesh ) {

		this.geometry = mesh.geometry;
		this.randomFunction = Math.random;

		this.indexAttribute = this.geometry.index;
		this.positionAttribute = this.geometry.getAttribute( 'position' );
		this.normalAttribute = this.geometry.getAttribute( 'normal' );
		this.colorAttribute = this.geometry.getAttribute( 'color' );
		this.uvAttribute = this.geometry.getAttribute( 'uv' );
		this.weightAttribute = null;

		this.distribution = null;

	}

	/**
	 * Specifies a vertex attribute to be used as a weight when sampling from the surface.
	 * Faces with higher weights are more likely to be sampled, and those with weights of
	 * zero will not be sampled at all. For vector attributes, only .x is used in sampling.
	 *
	 * If no weight attribute is selected, sampling is randomly distributed by area.
	 *
	 * @param {string} name - The attribute name.
	 * @return {MeshSurfaceSampler} A reference to this sampler.
	 */
	setWeightAttribute( name ) {

		this.weightAttribute = name ? this.geometry.getAttribute( name ) : null;

		return this;

	}

	/**
	 * Processes the input geometry and prepares to return samples. Any configuration of the
	 * geometry or sampler must occur before this method is called. Time complexity is O(n)
	 * for a surface with n faces.
	 *
	 * @return {MeshSurfaceSampler} A reference to this sampler.
	 */
	build() {

		const indexAttribute = this.indexAttribute;
		const positionAttribute = this.positionAttribute;
		const weightAttribute = this.weightAttribute;

		const totalFaces = indexAttribute ? ( indexAttribute.count / 3 ) : ( positionAttribute.count / 3 );
		const faceWeights = new Float32Array( totalFaces );

		// Accumulate weights for each mesh face.

		for ( let i = 0; i < totalFaces; i ++ ) {

			let faceWeight = 1;

			let i0 = 3 * i;
			let i1 = 3 * i + 1;
			let i2 = 3 * i + 2;

			if ( indexAttribute ) {

				i0 = indexAttribute.getX( i0 );
				i1 = indexAttribute.getX( i1 );
				i2 = indexAttribute.getX( i2 );

			}

			if ( weightAttribute ) {

				faceWeight = weightAttribute.getX( i0 )
					+ weightAttribute.getX( i1 )
					+ weightAttribute.getX( i2 );

			}

			_face.a.fromBufferAttribute( positionAttribute, i0 );
			_face.b.fromBufferAttribute( positionAttribute, i1 );
			_face.c.fromBufferAttribute( positionAttribute, i2 );
			faceWeight *= _face.getArea();

			faceWeights[ i ] = faceWeight;

		}

		// Store cumulative total face weights in an array, where weight index
		// corresponds to face index.

		const distribution = new Float32Array( totalFaces );
		let cumulativeTotal = 0;

		for ( let i = 0; i < totalFaces; i ++ ) {

			cumulativeTotal += faceWeights[ i ];
			distribution[ i ] = cumulativeTotal;

		}

		this.distribution = distribution;
		return this;

	}

	/**
	 * Allows to set a custom random number generator. Default is `Math.random()`.
	 *
	 * @param {Function} randomFunction - A random number generator.
	 * @return {MeshSurfaceSampler} A reference to this sampler.
	 */
	setRandomGenerator( randomFunction ) {

		this.randomFunction = randomFunction;
		return this;

	}

	/**
	 * Selects a random point on the surface of the input geometry, returning the
	 * position and optionally the normal vector, color and UV Coordinate at that point.
	 * Time complexity is O(log n) for a surface with n faces.
	 *
	 * @param {Vector3} targetPosition - The target object holding the sampled position.
	 * @param {Vector3} targetNormal - The target object holding the sampled normal.
	 * @param {Color} targetColor - The target object holding the sampled color.
	 * @param {Vector2} targetUV -  The target object holding the sampled uv coordinates.
	 * @return {MeshSurfaceSampler} A reference to this sampler.
	 */
	sample( targetPosition, targetNormal, targetColor, targetUV ) {

		const faceIndex = this._sampleFaceIndex();
		return this._sampleFace( faceIndex, targetPosition, targetNormal, targetColor, targetUV );

	}

	// private

	_sampleFaceIndex() {

		const cumulativeTotal = this.distribution[ this.distribution.length - 1 ];
		return this._binarySearch( this.randomFunction() * cumulativeTotal );

	}

	_binarySearch( x ) {

		const dist = this.distribution;
		let start = 0;
		let end = dist.length - 1;

		let index = - 1;

		while ( start <= end ) {

			const mid = Math.ceil( ( start + end ) / 2 );

			if ( mid === 0 || dist[ mid - 1 ] <= x && dist[ mid ] > x ) {

				index = mid;

				break;

			} else if ( x < dist[ mid ] ) {

				end = mid - 1;

			} else {

				start = mid + 1;

			}

		}

		return index;

	}

	_sampleFace( faceIndex, targetPosition, targetNormal, targetColor, targetUV ) {

		let u = this.randomFunction();
		let v = this.randomFunction();

		if ( u + v > 1 ) {

			u = 1 - u;
			v = 1 - v;

		}

		// get the vertex attribute indices
		const indexAttribute = this.indexAttribute;
		let i0 = faceIndex * 3;
		let i1 = faceIndex * 3 + 1;
		let i2 = faceIndex * 3 + 2;
		if ( indexAttribute ) {

			i0 = indexAttribute.getX( i0 );
			i1 = indexAttribute.getX( i1 );
			i2 = indexAttribute.getX( i2 );

		}

		_face.a.fromBufferAttribute( this.positionAttribute, i0 );
		_face.b.fromBufferAttribute( this.positionAttribute, i1 );
		_face.c.fromBufferAttribute( this.positionAttribute, i2 );

		targetPosition
			.set( 0, 0, 0 )
			.addScaledVector( _face.a, u )
			.addScaledVector( _face.b, v )
			.addScaledVector( _face.c, 1 - ( u + v ) );

		if ( targetNormal !== undefined ) {

			if ( this.normalAttribute !== undefined ) {

				_face.a.fromBufferAttribute( this.normalAttribute, i0 );
				_face.b.fromBufferAttribute( this.normalAttribute, i1 );
				_face.c.fromBufferAttribute( this.normalAttribute, i2 );
				targetNormal.set( 0, 0, 0 ).addScaledVector( _face.a, u ).addScaledVector( _face.b, v ).addScaledVector( _face.c, 1 - ( u + v ) ).normalize();

			} else {

				_face.getNormal( targetNormal );

			}

		}

		if ( targetColor !== undefined && this.colorAttribute !== undefined ) {

			_face.a.fromBufferAttribute( this.colorAttribute, i0 );
			_face.b.fromBufferAttribute( this.colorAttribute, i1 );
			_face.c.fromBufferAttribute( this.colorAttribute, i2 );

			_color
				.set( 0, 0, 0 )
				.addScaledVector( _face.a, u )
				.addScaledVector( _face.b, v )
				.addScaledVector( _face.c, 1 - ( u + v ) );

			targetColor.r = _color.x;
			targetColor.g = _color.y;
			targetColor.b = _color.z;

		}

		if ( targetUV !== undefined && this.uvAttribute !== undefined ) {

			_uva.fromBufferAttribute( this.uvAttribute, i0 );
			_uvb.fromBufferAttribute( this.uvAttribute, i1 );
			_uvc.fromBufferAttribute( this.uvAttribute, i2 );
			targetUV.set( 0, 0 ).addScaledVector( _uva, u ).addScaledVector( _uvb, v ).addScaledVector( _uvc, 1 - ( u + v ) );

		}

		return this;

	}

}
```
</details>

#### Methods

##### `setWeightAttribute(name: string): MeshSurfaceSampler`

<details><summary>Code</summary>

```ts
setWeightAttribute( name ) {

		this.weightAttribute = name ? this.geometry.getAttribute( name ) : null;

		return this;

	}
```
</details>

##### `build(): MeshSurfaceSampler`

<details><summary>Code</summary>

```ts
build() {

		const indexAttribute = this.indexAttribute;
		const positionAttribute = this.positionAttribute;
		const weightAttribute = this.weightAttribute;

		const totalFaces = indexAttribute ? ( indexAttribute.count / 3 ) : ( positionAttribute.count / 3 );
		const faceWeights = new Float32Array( totalFaces );

		// Accumulate weights for each mesh face.

		for ( let i = 0; i < totalFaces; i ++ ) {

			let faceWeight = 1;

			let i0 = 3 * i;
			let i1 = 3 * i + 1;
			let i2 = 3 * i + 2;

			if ( indexAttribute ) {

				i0 = indexAttribute.getX( i0 );
				i1 = indexAttribute.getX( i1 );
				i2 = indexAttribute.getX( i2 );

			}

			if ( weightAttribute ) {

				faceWeight = weightAttribute.getX( i0 )
					+ weightAttribute.getX( i1 )
					+ weightAttribute.getX( i2 );

			}

			_face.a.fromBufferAttribute( positionAttribute, i0 );
			_face.b.fromBufferAttribute( positionAttribute, i1 );
			_face.c.fromBufferAttribute( positionAttribute, i2 );
			faceWeight *= _face.getArea();

			faceWeights[ i ] = faceWeight;

		}

		// Store cumulative total face weights in an array, where weight index
		// corresponds to face index.

		const distribution = new Float32Array( totalFaces );
		let cumulativeTotal = 0;

		for ( let i = 0; i < totalFaces; i ++ ) {

			cumulativeTotal += faceWeights[ i ];
			distribution[ i ] = cumulativeTotal;

		}

		this.distribution = distribution;
		return this;

	}
```
</details>

##### `setRandomGenerator(randomFunction: Function): MeshSurfaceSampler`

<details><summary>Code</summary>

```ts
setRandomGenerator( randomFunction ) {

		this.randomFunction = randomFunction;
		return this;

	}
```
</details>

##### `sample(targetPosition: Vector3, targetNormal: Vector3, targetColor: Color, targetUV: Vector2): MeshSurfaceSampler`

<details><summary>Code</summary>

```ts
sample( targetPosition, targetNormal, targetColor, targetUV ) {

		const faceIndex = this._sampleFaceIndex();
		return this._sampleFace( faceIndex, targetPosition, targetNormal, targetColor, targetUV );

	}
```
</details>

##### `_sampleFaceIndex(): number`

<details><summary>Code</summary>

```ts
_sampleFaceIndex() {

		const cumulativeTotal = this.distribution[ this.distribution.length - 1 ];
		return this._binarySearch( this.randomFunction() * cumulativeTotal );

	}
```
</details>

##### `_binarySearch(x: any): number`

<details><summary>Code</summary>

```ts
_binarySearch( x ) {

		const dist = this.distribution;
		let start = 0;
		let end = dist.length - 1;

		let index = - 1;

		while ( start <= end ) {

			const mid = Math.ceil( ( start + end ) / 2 );

			if ( mid === 0 || dist[ mid - 1 ] <= x && dist[ mid ] > x ) {

				index = mid;

				break;

			} else if ( x < dist[ mid ] ) {

				end = mid - 1;

			} else {

				start = mid + 1;

			}

		}

		return index;

	}
```
</details>

##### `_sampleFace(faceIndex: any, targetPosition: any, targetNormal: any, targetColor: any, targetUV: any): this`

<details><summary>Code</summary>

```ts
_sampleFace( faceIndex, targetPosition, targetNormal, targetColor, targetUV ) {

		let u = this.randomFunction();
		let v = this.randomFunction();

		if ( u + v > 1 ) {

			u = 1 - u;
			v = 1 - v;

		}

		// get the vertex attribute indices
		const indexAttribute = this.indexAttribute;
		let i0 = faceIndex * 3;
		let i1 = faceIndex * 3 + 1;
		let i2 = faceIndex * 3 + 2;
		if ( indexAttribute ) {

			i0 = indexAttribute.getX( i0 );
			i1 = indexAttribute.getX( i1 );
			i2 = indexAttribute.getX( i2 );

		}

		_face.a.fromBufferAttribute( this.positionAttribute, i0 );
		_face.b.fromBufferAttribute( this.positionAttribute, i1 );
		_face.c.fromBufferAttribute( this.positionAttribute, i2 );

		targetPosition
			.set( 0, 0, 0 )
			.addScaledVector( _face.a, u )
			.addScaledVector( _face.b, v )
			.addScaledVector( _face.c, 1 - ( u + v ) );

		if ( targetNormal !== undefined ) {

			if ( this.normalAttribute !== undefined ) {

				_face.a.fromBufferAttribute( this.normalAttribute, i0 );
				_face.b.fromBufferAttribute( this.normalAttribute, i1 );
				_face.c.fromBufferAttribute( this.normalAttribute, i2 );
				targetNormal.set( 0, 0, 0 ).addScaledVector( _face.a, u ).addScaledVector( _face.b, v ).addScaledVector( _face.c, 1 - ( u + v ) ).normalize();

			} else {

				_face.getNormal( targetNormal );

			}

		}

		if ( targetColor !== undefined && this.colorAttribute !== undefined ) {

			_face.a.fromBufferAttribute( this.colorAttribute, i0 );
			_face.b.fromBufferAttribute( this.colorAttribute, i1 );
			_face.c.fromBufferAttribute( this.colorAttribute, i2 );

			_color
				.set( 0, 0, 0 )
				.addScaledVector( _face.a, u )
				.addScaledVector( _face.b, v )
				.addScaledVector( _face.c, 1 - ( u + v ) );

			targetColor.r = _color.x;
			targetColor.g = _color.y;
			targetColor.b = _color.z;

		}

		if ( targetUV !== undefined && this.uvAttribute !== undefined ) {

			_uva.fromBufferAttribute( this.uvAttribute, i0 );
			_uvb.fromBufferAttribute( this.uvAttribute, i1 );
			_uvc.fromBufferAttribute( this.uvAttribute, i2 );
			targetUV.set( 0, 0 ).addScaledVector( _uva, u ).addScaledVector( _uvb, v ).addScaledVector( _uvc, 1 - ( u + v ) );

		}

		return this;

	}
```
</details>


---