[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LineSegmentsGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 18 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/lines/LineSegmentsGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Box3` | `three` |
| `Float32BufferAttribute` | `three` |
| `InstancedBufferGeometry` | `three` |
| `InstancedInterleavedBuffer` | `three` |
| `InterleavedBufferAttribute` | `three` |
| `Sphere` | `three` |
| `Vector3` | `three` |
| `WireframeGeometry` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_box` | `any` | let/var | `new Box3()` | ✗ |
| `_vector` | `any` | let/var | `new Vector3()` | ✗ |
| `positions` | `number[]` | let/var | `[ - 1, 2, 0, 1, 2, 0, - 1, 1, 0, 1, 1, 0, - 1, 0, 0, 1, 0, 0, - 1, - 1, 0, 1,...` | ✗ |
| `uvs` | `number[]` | let/var | `[ - 1, 2, 1, 2, - 1, 1, 1, 1, - 1, - 1, 1, - 1, - 1, - 2, 1, - 2 ]` | ✗ |
| `index` | `number[]` | let/var | `[ 0, 2, 1, 2, 3, 1, 2, 4, 3, 4, 5, 3, 4, 6, 5, 6, 7, 5 ]` | ✗ |
| `start` | `any` | let/var | `this.attributes.instanceStart` | ✗ |
| `end` | `any` | let/var | `this.attributes.instanceEnd` | ✗ |
| `lineSegments` | `any` | let/var | `*not shown*` | ✗ |
| `instanceBuffer` | `any` | let/var | `new InstancedInterleavedBuffer( lineSegments, 6, 1 )` | ✗ |
| `colors` | `any` | let/var | `*not shown*` | ✗ |
| `instanceColorBuffer` | `any` | let/var | `new InstancedInterleavedBuffer( colors, 6, 1 )` | ✗ |
| `geometry` | `any` | let/var | `lineSegments.geometry` | ✗ |
| `start` | `any` | let/var | `this.attributes.instanceStart` | ✗ |
| `end` | `any` | let/var | `this.attributes.instanceEnd` | ✗ |
| `start` | `any` | let/var | `this.attributes.instanceStart` | ✗ |
| `end` | `any` | let/var | `this.attributes.instanceEnd` | ✗ |
| `center` | `any` | let/var | `this.boundingSphere.center` | ✗ |
| `maxRadiusSq` | `number` | let/var | `0` | ✗ |


---

## Functions

### `LineSegmentsGeometry.applyMatrix4(matrix: Matrix4): LineSegmentsGeometry`

**JSDoc:**
```typescript
/**
	 * Applies the given 4x4 transformation matrix to the geometry.
	 *
	 * @param {Matrix4} matrix - The matrix to apply.
	 * @return {LineSegmentsGeometry} A reference to this instance.
	 */
```

**Parameters:**

- **`matrix`** `Matrix4`

**Returns:** `LineSegmentsGeometry`

**Calls:**

- `start.applyMatrix4`
- `end.applyMatrix4`
- `this.computeBoundingBox`
- `this.computeBoundingSphere`

<details><summary>Code</summary>

```typescript
applyMatrix4( matrix ) {

		const start = this.attributes.instanceStart;
		const end = this.attributes.instanceEnd;

		if ( start !== undefined ) {

			start.applyMatrix4( matrix );

			end.applyMatrix4( matrix );

			start.needsUpdate = true;

		}

		if ( this.boundingBox !== null ) {

			this.computeBoundingBox();

		}

		if ( this.boundingSphere !== null ) {

			this.computeBoundingSphere();

		}

		return this;

	}
```
</details>

### `LineSegmentsGeometry.setPositions(array: number[] | Float32Array<ArrayBufferLike>): LineSegmentsGeometry`

**JSDoc:**
```typescript
/**
	 * Sets the given line positions for this geometry. The length must be a multiple of six since
	 * each line segment is defined by a start end vertex in the pattern `(xyz xyz)`.
	 *
	 * @param {Float32Array|Array<number>} array - The position data to set.
	 * @return {LineSegmentsGeometry} A reference to this geometry.
	 */
```

**Parameters:**

- **`array`** `number[] | Float32Array<ArrayBufferLike>`

**Returns:** `LineSegmentsGeometry`

**Calls:**

- `Array.isArray`
- `this.setAttribute`
- `this.computeBoundingBox`
- `this.computeBoundingSphere`

**Internal Comments:**
```
// (x4)
```

<details><summary>Code</summary>

```typescript
setPositions( array ) {

		let lineSegments;

		if ( array instanceof Float32Array ) {

			lineSegments = array;

		} else if ( Array.isArray( array ) ) {

			lineSegments = new Float32Array( array );

		}

		const instanceBuffer = new InstancedInterleavedBuffer( lineSegments, 6, 1 ); // xyz, xyz

		this.setAttribute( 'instanceStart', new InterleavedBufferAttribute( instanceBuffer, 3, 0 ) ); // xyz
		this.setAttribute( 'instanceEnd', new InterleavedBufferAttribute( instanceBuffer, 3, 3 ) ); // xyz

		this.instanceCount = this.attributes.instanceStart.count;

		//

		this.computeBoundingBox();
		this.computeBoundingSphere();

		return this;

	}
```
</details>

### `LineSegmentsGeometry.setColors(array: number[] | Float32Array<ArrayBufferLike>): LineSegmentsGeometry`

**JSDoc:**
```typescript
/**
	 * Sets the given line colors for this geometry. The length must be a multiple of six since
	 * each line segment is defined by a start end color in the pattern `(rgb rgb)`.
	 *
	 * @param {Float32Array|Array<number>} array - The position data to set.
	 * @return {LineSegmentsGeometry} A reference to this geometry.
	 */
```

**Parameters:**

- **`array`** `number[] | Float32Array<ArrayBufferLike>`

**Returns:** `LineSegmentsGeometry`

**Calls:**

- `Array.isArray`
- `this.setAttribute`

<details><summary>Code</summary>

```typescript
setColors( array ) {

		let colors;

		if ( array instanceof Float32Array ) {

			colors = array;

		} else if ( Array.isArray( array ) ) {

			colors = new Float32Array( array );

		}

		const instanceColorBuffer = new InstancedInterleavedBuffer( colors, 6, 1 ); // rgb, rgb

		this.setAttribute( 'instanceColorStart', new InterleavedBufferAttribute( instanceColorBuffer, 3, 0 ) ); // rgb
		this.setAttribute( 'instanceColorEnd', new InterleavedBufferAttribute( instanceColorBuffer, 3, 3 ) ); // rgb

		return this;

	}
```
</details>

### `LineSegmentsGeometry.fromWireframeGeometry(geometry: WireframeGeometry): LineSegmentsGeometry`

**JSDoc:**
```typescript
/**
	 * Setups this line segments geometry from the given wireframe geometry.
	 *
	 * @param {WireframeGeometry} geometry - The geometry that should be used as a data source for this geometry.
	 * @return {LineSegmentsGeometry} A reference to this geometry.
	 */
```

**Parameters:**

- **`geometry`** `WireframeGeometry`

**Returns:** `LineSegmentsGeometry`

**Calls:**

- `this.setPositions`

<details><summary>Code</summary>

```typescript
fromWireframeGeometry( geometry ) {

		this.setPositions( geometry.attributes.position.array );

		return this;

	}
```
</details>

### `LineSegmentsGeometry.fromEdgesGeometry(geometry: EdgesGeometry): LineSegmentsGeometry`

**JSDoc:**
```typescript
/**
	 * Setups this line segments geometry from the given edges geometry.
	 *
	 * @param {EdgesGeometry} geometry - The geometry that should be used as a data source for this geometry.
	 * @return {LineSegmentsGeometry} A reference to this geometry.
	 */
```

**Parameters:**

- **`geometry`** `EdgesGeometry`

**Returns:** `LineSegmentsGeometry`

**Calls:**

- `this.setPositions`

<details><summary>Code</summary>

```typescript
fromEdgesGeometry( geometry ) {

		this.setPositions( geometry.attributes.position.array );

		return this;

	}
```
</details>

### `LineSegmentsGeometry.fromMesh(mesh: Mesh): LineSegmentsGeometry`

**JSDoc:**
```typescript
/**
	 * Setups this line segments geometry from the given mesh.
	 *
	 * @param {Mesh} mesh - The mesh geometry that should be used as a data source for this geometry.
	 * @return {LineSegmentsGeometry} A reference to this geometry.
	 */
```

**Parameters:**

- **`mesh`** `Mesh`

**Returns:** `LineSegmentsGeometry`

**Calls:**

- `this.fromWireframeGeometry`

**Internal Comments:**
```
// set colors, maybe
```

<details><summary>Code</summary>

```typescript
fromMesh( mesh ) {

		this.fromWireframeGeometry( new WireframeGeometry( mesh.geometry ) );

		// set colors, maybe

		return this;

	}
```
</details>

### `LineSegmentsGeometry.fromLineSegments(lineSegments: LineSegments): LineSegmentsGeometry`

**JSDoc:**
```typescript
/**
	 * Setups this line segments geometry from the given line segments.
	 *
	 * @param {LineSegments} lineSegments - The line segments that should be used as a data source for this geometry.
	 * Assumes the source geometry is not using indices.
	 * @return {LineSegmentsGeometry} A reference to this geometry.
	 */
```

**Parameters:**

- **`lineSegments`** `LineSegments`

**Returns:** `LineSegmentsGeometry`

**Calls:**

- `this.setPositions`

**Internal Comments:**
```
// set colors, maybe
```

<details><summary>Code</summary>

```typescript
fromLineSegments( lineSegments ) {

		const geometry = lineSegments.geometry;

		this.setPositions( geometry.attributes.position.array ); // assumes non-indexed

		// set colors, maybe

		return this;

	}
```
</details>

### `LineSegmentsGeometry.computeBoundingBox(): void`

**Returns:** `void`

**Calls:**

- `this.boundingBox.setFromBufferAttribute`
- `_box.setFromBufferAttribute`
- `this.boundingBox.union`

<details><summary>Code</summary>

```typescript
computeBoundingBox() {

		if ( this.boundingBox === null ) {

			this.boundingBox = new Box3();

		}

		const start = this.attributes.instanceStart;
		const end = this.attributes.instanceEnd;

		if ( start !== undefined && end !== undefined ) {

			this.boundingBox.setFromBufferAttribute( start );

			_box.setFromBufferAttribute( end );

			this.boundingBox.union( _box );

		}

	}
```
</details>

### `LineSegmentsGeometry.computeBoundingSphere(): void`

**Returns:** `void`

**Calls:**

- `this.computeBoundingBox`
- `this.boundingBox.getCenter`
- `_vector.fromBufferAttribute`
- `Math.max`
- `center.distanceToSquared`
- `Math.sqrt`
- `isNaN`
- `console.error`

<details><summary>Code</summary>

```typescript
computeBoundingSphere() {

		if ( this.boundingSphere === null ) {

			this.boundingSphere = new Sphere();

		}

		if ( this.boundingBox === null ) {

			this.computeBoundingBox();

		}

		const start = this.attributes.instanceStart;
		const end = this.attributes.instanceEnd;

		if ( start !== undefined && end !== undefined ) {

			const center = this.boundingSphere.center;

			this.boundingBox.getCenter( center );

			let maxRadiusSq = 0;

			for ( let i = 0, il = start.count; i < il; i ++ ) {

				_vector.fromBufferAttribute( start, i );
				maxRadiusSq = Math.max( maxRadiusSq, center.distanceToSquared( _vector ) );

				_vector.fromBufferAttribute( end, i );
				maxRadiusSq = Math.max( maxRadiusSq, center.distanceToSquared( _vector ) );

			}

			this.boundingSphere.radius = Math.sqrt( maxRadiusSq );

			if ( isNaN( this.boundingSphere.radius ) ) {

				console.error( 'THREE.LineSegmentsGeometry.computeBoundingSphere(): Computed radius is NaN. The instanced position data is likely to have NaN values.', this );

			}

		}

	}
```
</details>

### `LineSegmentsGeometry.toJSON(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
toJSON() {

		// todo

	}
```
</details>


---

## Classes

### `LineSegmentsGeometry`

<details><summary>Class Code</summary>

```ts
class LineSegmentsGeometry extends InstancedBufferGeometry {

	/**
	 * Constructs a new line segments geometry.
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
		this.isLineSegmentsGeometry = true;

		this.type = 'LineSegmentsGeometry';

		const positions = [ - 1, 2, 0, 1, 2, 0, - 1, 1, 0, 1, 1, 0, - 1, 0, 0, 1, 0, 0, - 1, - 1, 0, 1, - 1, 0 ];
		const uvs = [ - 1, 2, 1, 2, - 1, 1, 1, 1, - 1, - 1, 1, - 1, - 1, - 2, 1, - 2 ];
		const index = [ 0, 2, 1, 2, 3, 1, 2, 4, 3, 4, 5, 3, 4, 6, 5, 6, 7, 5 ];

		this.setIndex( index );
		this.setAttribute( 'position', new Float32BufferAttribute( positions, 3 ) );
		this.setAttribute( 'uv', new Float32BufferAttribute( uvs, 2 ) );

	}

	/**
	 * Applies the given 4x4 transformation matrix to the geometry.
	 *
	 * @param {Matrix4} matrix - The matrix to apply.
	 * @return {LineSegmentsGeometry} A reference to this instance.
	 */
	applyMatrix4( matrix ) {

		const start = this.attributes.instanceStart;
		const end = this.attributes.instanceEnd;

		if ( start !== undefined ) {

			start.applyMatrix4( matrix );

			end.applyMatrix4( matrix );

			start.needsUpdate = true;

		}

		if ( this.boundingBox !== null ) {

			this.computeBoundingBox();

		}

		if ( this.boundingSphere !== null ) {

			this.computeBoundingSphere();

		}

		return this;

	}

	/**
	 * Sets the given line positions for this geometry. The length must be a multiple of six since
	 * each line segment is defined by a start end vertex in the pattern `(xyz xyz)`.
	 *
	 * @param {Float32Array|Array<number>} array - The position data to set.
	 * @return {LineSegmentsGeometry} A reference to this geometry.
	 */
	setPositions( array ) {

		let lineSegments;

		if ( array instanceof Float32Array ) {

			lineSegments = array;

		} else if ( Array.isArray( array ) ) {

			lineSegments = new Float32Array( array );

		}

		const instanceBuffer = new InstancedInterleavedBuffer( lineSegments, 6, 1 ); // xyz, xyz

		this.setAttribute( 'instanceStart', new InterleavedBufferAttribute( instanceBuffer, 3, 0 ) ); // xyz
		this.setAttribute( 'instanceEnd', new InterleavedBufferAttribute( instanceBuffer, 3, 3 ) ); // xyz

		this.instanceCount = this.attributes.instanceStart.count;

		//

		this.computeBoundingBox();
		this.computeBoundingSphere();

		return this;

	}

	/**
	 * Sets the given line colors for this geometry. The length must be a multiple of six since
	 * each line segment is defined by a start end color in the pattern `(rgb rgb)`.
	 *
	 * @param {Float32Array|Array<number>} array - The position data to set.
	 * @return {LineSegmentsGeometry} A reference to this geometry.
	 */
	setColors( array ) {

		let colors;

		if ( array instanceof Float32Array ) {

			colors = array;

		} else if ( Array.isArray( array ) ) {

			colors = new Float32Array( array );

		}

		const instanceColorBuffer = new InstancedInterleavedBuffer( colors, 6, 1 ); // rgb, rgb

		this.setAttribute( 'instanceColorStart', new InterleavedBufferAttribute( instanceColorBuffer, 3, 0 ) ); // rgb
		this.setAttribute( 'instanceColorEnd', new InterleavedBufferAttribute( instanceColorBuffer, 3, 3 ) ); // rgb

		return this;

	}

	/**
	 * Setups this line segments geometry from the given wireframe geometry.
	 *
	 * @param {WireframeGeometry} geometry - The geometry that should be used as a data source for this geometry.
	 * @return {LineSegmentsGeometry} A reference to this geometry.
	 */
	fromWireframeGeometry( geometry ) {

		this.setPositions( geometry.attributes.position.array );

		return this;

	}

	/**
	 * Setups this line segments geometry from the given edges geometry.
	 *
	 * @param {EdgesGeometry} geometry - The geometry that should be used as a data source for this geometry.
	 * @return {LineSegmentsGeometry} A reference to this geometry.
	 */
	fromEdgesGeometry( geometry ) {

		this.setPositions( geometry.attributes.position.array );

		return this;

	}

	/**
	 * Setups this line segments geometry from the given mesh.
	 *
	 * @param {Mesh} mesh - The mesh geometry that should be used as a data source for this geometry.
	 * @return {LineSegmentsGeometry} A reference to this geometry.
	 */
	fromMesh( mesh ) {

		this.fromWireframeGeometry( new WireframeGeometry( mesh.geometry ) );

		// set colors, maybe

		return this;

	}

	/**
	 * Setups this line segments geometry from the given line segments.
	 *
	 * @param {LineSegments} lineSegments - The line segments that should be used as a data source for this geometry.
	 * Assumes the source geometry is not using indices.
	 * @return {LineSegmentsGeometry} A reference to this geometry.
	 */
	fromLineSegments( lineSegments ) {

		const geometry = lineSegments.geometry;

		this.setPositions( geometry.attributes.position.array ); // assumes non-indexed

		// set colors, maybe

		return this;

	}

	computeBoundingBox() {

		if ( this.boundingBox === null ) {

			this.boundingBox = new Box3();

		}

		const start = this.attributes.instanceStart;
		const end = this.attributes.instanceEnd;

		if ( start !== undefined && end !== undefined ) {

			this.boundingBox.setFromBufferAttribute( start );

			_box.setFromBufferAttribute( end );

			this.boundingBox.union( _box );

		}

	}

	computeBoundingSphere() {

		if ( this.boundingSphere === null ) {

			this.boundingSphere = new Sphere();

		}

		if ( this.boundingBox === null ) {

			this.computeBoundingBox();

		}

		const start = this.attributes.instanceStart;
		const end = this.attributes.instanceEnd;

		if ( start !== undefined && end !== undefined ) {

			const center = this.boundingSphere.center;

			this.boundingBox.getCenter( center );

			let maxRadiusSq = 0;

			for ( let i = 0, il = start.count; i < il; i ++ ) {

				_vector.fromBufferAttribute( start, i );
				maxRadiusSq = Math.max( maxRadiusSq, center.distanceToSquared( _vector ) );

				_vector.fromBufferAttribute( end, i );
				maxRadiusSq = Math.max( maxRadiusSq, center.distanceToSquared( _vector ) );

			}

			this.boundingSphere.radius = Math.sqrt( maxRadiusSq );

			if ( isNaN( this.boundingSphere.radius ) ) {

				console.error( 'THREE.LineSegmentsGeometry.computeBoundingSphere(): Computed radius is NaN. The instanced position data is likely to have NaN values.', this );

			}

		}

	}

	toJSON() {

		// todo

	}

}
```
</details>

#### Methods

##### `applyMatrix4(matrix: Matrix4): LineSegmentsGeometry`

<details><summary>Code</summary>

```ts
applyMatrix4( matrix ) {

		const start = this.attributes.instanceStart;
		const end = this.attributes.instanceEnd;

		if ( start !== undefined ) {

			start.applyMatrix4( matrix );

			end.applyMatrix4( matrix );

			start.needsUpdate = true;

		}

		if ( this.boundingBox !== null ) {

			this.computeBoundingBox();

		}

		if ( this.boundingSphere !== null ) {

			this.computeBoundingSphere();

		}

		return this;

	}
```
</details>

##### `setPositions(array: number[] | Float32Array<ArrayBufferLike>): LineSegmentsGeometry`

<details><summary>Code</summary>

```ts
setPositions( array ) {

		let lineSegments;

		if ( array instanceof Float32Array ) {

			lineSegments = array;

		} else if ( Array.isArray( array ) ) {

			lineSegments = new Float32Array( array );

		}

		const instanceBuffer = new InstancedInterleavedBuffer( lineSegments, 6, 1 ); // xyz, xyz

		this.setAttribute( 'instanceStart', new InterleavedBufferAttribute( instanceBuffer, 3, 0 ) ); // xyz
		this.setAttribute( 'instanceEnd', new InterleavedBufferAttribute( instanceBuffer, 3, 3 ) ); // xyz

		this.instanceCount = this.attributes.instanceStart.count;

		//

		this.computeBoundingBox();
		this.computeBoundingSphere();

		return this;

	}
```
</details>

##### `setColors(array: number[] | Float32Array<ArrayBufferLike>): LineSegmentsGeometry`

<details><summary>Code</summary>

```ts
setColors( array ) {

		let colors;

		if ( array instanceof Float32Array ) {

			colors = array;

		} else if ( Array.isArray( array ) ) {

			colors = new Float32Array( array );

		}

		const instanceColorBuffer = new InstancedInterleavedBuffer( colors, 6, 1 ); // rgb, rgb

		this.setAttribute( 'instanceColorStart', new InterleavedBufferAttribute( instanceColorBuffer, 3, 0 ) ); // rgb
		this.setAttribute( 'instanceColorEnd', new InterleavedBufferAttribute( instanceColorBuffer, 3, 3 ) ); // rgb

		return this;

	}
```
</details>

##### `fromWireframeGeometry(geometry: WireframeGeometry): LineSegmentsGeometry`

<details><summary>Code</summary>

```ts
fromWireframeGeometry( geometry ) {

		this.setPositions( geometry.attributes.position.array );

		return this;

	}
```
</details>

##### `fromEdgesGeometry(geometry: EdgesGeometry): LineSegmentsGeometry`

<details><summary>Code</summary>

```ts
fromEdgesGeometry( geometry ) {

		this.setPositions( geometry.attributes.position.array );

		return this;

	}
```
</details>

##### `fromMesh(mesh: Mesh): LineSegmentsGeometry`

<details><summary>Code</summary>

```ts
fromMesh( mesh ) {

		this.fromWireframeGeometry( new WireframeGeometry( mesh.geometry ) );

		// set colors, maybe

		return this;

	}
```
</details>

##### `fromLineSegments(lineSegments: LineSegments): LineSegmentsGeometry`

<details><summary>Code</summary>

```ts
fromLineSegments( lineSegments ) {

		const geometry = lineSegments.geometry;

		this.setPositions( geometry.attributes.position.array ); // assumes non-indexed

		// set colors, maybe

		return this;

	}
```
</details>

##### `computeBoundingBox(): void`

<details><summary>Code</summary>

```ts
computeBoundingBox() {

		if ( this.boundingBox === null ) {

			this.boundingBox = new Box3();

		}

		const start = this.attributes.instanceStart;
		const end = this.attributes.instanceEnd;

		if ( start !== undefined && end !== undefined ) {

			this.boundingBox.setFromBufferAttribute( start );

			_box.setFromBufferAttribute( end );

			this.boundingBox.union( _box );

		}

	}
```
</details>

##### `computeBoundingSphere(): void`

<details><summary>Code</summary>

```ts
computeBoundingSphere() {

		if ( this.boundingSphere === null ) {

			this.boundingSphere = new Sphere();

		}

		if ( this.boundingBox === null ) {

			this.computeBoundingBox();

		}

		const start = this.attributes.instanceStart;
		const end = this.attributes.instanceEnd;

		if ( start !== undefined && end !== undefined ) {

			const center = this.boundingSphere.center;

			this.boundingBox.getCenter( center );

			let maxRadiusSq = 0;

			for ( let i = 0, il = start.count; i < il; i ++ ) {

				_vector.fromBufferAttribute( start, i );
				maxRadiusSq = Math.max( maxRadiusSq, center.distanceToSquared( _vector ) );

				_vector.fromBufferAttribute( end, i );
				maxRadiusSq = Math.max( maxRadiusSq, center.distanceToSquared( _vector ) );

			}

			this.boundingSphere.radius = Math.sqrt( maxRadiusSq );

			if ( isNaN( this.boundingSphere.radius ) ) {

				console.error( 'THREE.LineSegmentsGeometry.computeBoundingSphere(): Computed radius is NaN. The instanced position data is likely to have NaN values.', this );

			}

		}

	}
```
</details>

##### `toJSON(): void`

<details><summary>Code</summary>

```ts
toJSON() {

		// todo

	}
```
</details>


---