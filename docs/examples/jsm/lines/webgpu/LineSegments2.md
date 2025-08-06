[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `LineSegments2.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 13 |
| 📊 Variables & Constants | 51 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/lines/webgpu/LineSegments2.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Box3` | `three/webgpu` |
| `InstancedInterleavedBuffer` | `three/webgpu` |
| `InterleavedBufferAttribute` | `three/webgpu` |
| `Line3` | `three/webgpu` |
| `MathUtils` | `three/webgpu` |
| `Matrix4` | `three/webgpu` |
| `Mesh` | `three/webgpu` |
| `Sphere` | `three/webgpu` |
| `Vector3` | `three/webgpu` |
| `Vector4` | `three/webgpu` |
| `Line2NodeMaterial` | `three/webgpu` |
| `Vector2` | `three/webgpu` |
| `LineSegmentsGeometry` | `../../lines/LineSegmentsGeometry.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_start` | `any` | let/var | `new Vector3()` | ✗ |
| `_end` | `any` | let/var | `new Vector3()` | ✗ |
| `_start4` | `any` | let/var | `new Vector4()` | ✗ |
| `_end4` | `any` | let/var | `new Vector4()` | ✗ |
| `_ssOrigin` | `any` | let/var | `new Vector4()` | ✗ |
| `_ssOrigin3` | `any` | let/var | `new Vector3()` | ✗ |
| `_mvMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `_line` | `any` | let/var | `new Line3()` | ✗ |
| `_closestPoint` | `any` | let/var | `new Vector3()` | ✗ |
| `_box` | `any` | let/var | `new Box3()` | ✗ |
| `_sphere` | `any` | let/var | `new Sphere()` | ✗ |
| `_clipToWorldVector` | `any` | let/var | `new Vector4()` | ✗ |
| `_viewport` | `any` | let/var | `new Vector4()` | ✗ |
| `_ray` | `any` | let/var | `*not shown*` | ✗ |
| `_lineWidth` | `any` | let/var | `*not shown*` | ✗ |
| `matrixWorld` | `any` | let/var | `lineSegments.matrixWorld` | ✗ |
| `geometry` | `any` | let/var | `lineSegments.geometry` | ✗ |
| `instanceStart` | `any` | let/var | `geometry.attributes.instanceStart` | ✗ |
| `instanceEnd` | `any` | let/var | `geometry.attributes.instanceEnd` | ✗ |
| `pointOnLine` | `any` | let/var | `new Vector3()` | ✗ |
| `point` | `any` | let/var | `new Vector3()` | ✗ |
| `isInside` | `boolean` | let/var | `point.distanceTo( pointOnLine ) < _lineWidth * 0.5` | ✗ |
| `projectionMatrix` | `any` | let/var | `camera.projectionMatrix` | ✗ |
| `matrixWorld` | `any` | let/var | `lineSegments.matrixWorld` | ✗ |
| `resolution` | `any` | let/var | `lineSegments._resolution` | ✗ |
| `geometry` | `any` | let/var | `lineSegments.geometry` | ✗ |
| `instanceStart` | `any` | let/var | `geometry.attributes.instanceStart` | ✗ |
| `instanceEnd` | `any` | let/var | `geometry.attributes.instanceEnd` | ✗ |
| `near` | `number` | let/var | `- camera.near` | ✗ |
| `isBehindCameraNear` | `boolean` | let/var | `_start4.z > near && _end4.z > near` | ✗ |
| `deltaDist` | `number` | let/var | `_start4.z - _end4.z` | ✗ |
| `t` | `number` | let/var | `( _start4.z - near ) / deltaDist` | ✗ |
| `deltaDist` | `number` | let/var | `_end4.z - _start4.z` | ✗ |
| `t` | `number` | let/var | `( _end4.z - near ) / deltaDist` | ✗ |
| `isInClipSpace` | `boolean` | let/var | `zPos >= - 1 && zPos <= 1` | ✗ |
| `isInside` | `boolean` | let/var | `_ssOrigin3.distanceTo( _closestPoint ) < _lineWidth * 0.5` | ✗ |
| `pointOnLine` | `any` | let/var | `new Vector3()` | ✗ |
| `point` | `any` | let/var | `new Vector3()` | ✗ |
| `geometry` | `any` | let/var | `this.geometry` | ✗ |
| `instanceStart` | `any` | let/var | `geometry.attributes.instanceStart` | ✗ |
| `instanceEnd` | `any` | let/var | `geometry.attributes.instanceEnd` | ✗ |
| `lineDistances` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( 2 * instanceStart.count )` | ✗ |
| `instanceDistanceBuffer` | `any` | let/var | `new InstancedInterleavedBuffer( lineDistances, 2, 1 )` | ✗ |
| `worldUnits` | `any` | let/var | `this.material.worldUnits` | ✗ |
| `camera` | `any` | let/var | `raycaster.camera` | ✗ |
| `threshold` | `any` | let/var | `( raycaster.params.Line2 !== undefined ) ? raycaster.params.Line2.threshold \...` | ✗ |
| `matrixWorld` | `any` | let/var | `this.matrixWorld` | ✗ |
| `geometry` | `any` | let/var | `this.geometry` | ✗ |
| `material` | `any` | let/var | `this.material` | ✗ |
| `sphereMargin` | `any` | let/var | `*not shown*` | ✗ |
| `boxMargin` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `getWorldSpaceHalfWidth(camera: any, distance: any, resolution: any): number`

**Parameters:**

- **`camera`** `any`
- **`distance`** `any`
- **`resolution`** `any`

**Returns:** `number`

**Calls:**

- `_clipToWorldVector.set( 0, 0, - distance, 1.0 ).applyMatrix4`
- `_clipToWorldVector.multiplyScalar`
- `_clipToWorldVector.applyMatrix4`
- `Math.abs`
- `Math.max`

**Internal Comments:**
```
// transform into clip space, adjust the x and y values by the pixel width offset, then (x6)
// transform back into world space to get world offset. Note clip space is [-1, 1] so full (x6)
// width does not need to be halved. (x6)
```

<details><summary>Code</summary>

```typescript
function getWorldSpaceHalfWidth( camera, distance, resolution ) {

	// transform into clip space, adjust the x and y values by the pixel width offset, then
	// transform back into world space to get world offset. Note clip space is [-1, 1] so full
	// width does not need to be halved.
	_clipToWorldVector.set( 0, 0, - distance, 1.0 ).applyMatrix4( camera.projectionMatrix );
	_clipToWorldVector.multiplyScalar( 1.0 / _clipToWorldVector.w );
	_clipToWorldVector.x = _lineWidth / resolution.width;
	_clipToWorldVector.y = _lineWidth / resolution.height;
	_clipToWorldVector.applyMatrix4( camera.projectionMatrixInverse );
	_clipToWorldVector.multiplyScalar( 1.0 / _clipToWorldVector.w );

	return Math.abs( Math.max( _clipToWorldVector.x, _clipToWorldVector.y ) );

}
```
</details>

### `raycastWorldUnits(lineSegments: any, intersects: any): void`

**Parameters:**

- **`lineSegments`** `any`
- **`intersects`** `any`

**Returns:** `void`

**Calls:**

- `Math.min`
- `_line.start.fromBufferAttribute`
- `_line.end.fromBufferAttribute`
- `_line.applyMatrix4`
- `_ray.distanceSqToSegment`
- `point.distanceTo`
- `intersects.push`
- `_ray.origin.distanceTo`

<details><summary>Code</summary>

```typescript
function raycastWorldUnits( lineSegments, intersects ) {

	const matrixWorld = lineSegments.matrixWorld;
	const geometry = lineSegments.geometry;
	const instanceStart = geometry.attributes.instanceStart;
	const instanceEnd = geometry.attributes.instanceEnd;
	const segmentCount = Math.min( geometry.instanceCount, instanceStart.count );

	for ( let i = 0, l = segmentCount; i < l; i ++ ) {

		_line.start.fromBufferAttribute( instanceStart, i );
		_line.end.fromBufferAttribute( instanceEnd, i );

		_line.applyMatrix4( matrixWorld );

		const pointOnLine = new Vector3();
		const point = new Vector3();

		_ray.distanceSqToSegment( _line.start, _line.end, point, pointOnLine );
		const isInside = point.distanceTo( pointOnLine ) < _lineWidth * 0.5;

		if ( isInside ) {

			intersects.push( {
				point,
				pointOnLine,
				distance: _ray.origin.distanceTo( point ),
				object: lineSegments,
				face: null,
				faceIndex: i,
				uv: null,
				uv1: null,
			} );

		}

	}

}
```
</details>

### `raycastScreenSpace(lineSegments: any, camera: any, intersects: any): void`

**Parameters:**

- **`lineSegments`** `any`
- **`camera`** `any`
- **`intersects`** `any`

**Returns:** `void`

**Calls:**

- `Math.min`
- `_ray.at`
- `_ssOrigin.applyMatrix4`
- `_ssOrigin.multiplyScalar`
- `_ssOrigin3.copy`
- `_mvMatrix.multiplyMatrices`
- `_start4.fromBufferAttribute`
- `_end4.fromBufferAttribute`
- `_start4.applyMatrix4`
- `_end4.applyMatrix4`
- `_start4.lerp`
- `_end4.lerp`
- `_start4.multiplyScalar`
- `_end4.multiplyScalar`
- `_line.start.copy`
- `_line.end.copy`
- `_line.closestPointToPointParameter`
- `_line.at`
- `MathUtils.lerp`
- `_ssOrigin3.distanceTo`
- `_line.start.fromBufferAttribute`
- `_line.end.fromBufferAttribute`
- `_line.start.applyMatrix4`
- `_line.end.applyMatrix4`
- `_ray.distanceSqToSegment`
- `intersects.push`
- `_ray.origin.distanceTo`

**Internal Comments:**
```
// (x4)
// pick a point 1 unit out along the ray to avoid the ray origin (x4)
// sitting at the camera origin which will cause "w" to be 0 when (x4)
// applying the projection matrix. (x4)
// ndc space [ - 1.0, 1.0 ] (x8)
// screen space (x8)
// camera space (x4)
// skip the segment if it's entirely behind the camera (x2)
// trim the segment if it extends behind camera near
// clip space (x4)
// create 2d segment (x5)
// get closest point on ray to segment (x2)
// check if the intersection point is within clip space (x2)
```

<details><summary>Code</summary>

```typescript
function raycastScreenSpace( lineSegments, camera, intersects ) {

	const projectionMatrix = camera.projectionMatrix;
	const matrixWorld = lineSegments.matrixWorld;

	const resolution = lineSegments._resolution;

	const geometry = lineSegments.geometry;
	const instanceStart = geometry.attributes.instanceStart;
	const instanceEnd = geometry.attributes.instanceEnd;
	const segmentCount = Math.min( geometry.instanceCount, instanceStart.count );

	const near = - camera.near;

	//

	// pick a point 1 unit out along the ray to avoid the ray origin
	// sitting at the camera origin which will cause "w" to be 0 when
	// applying the projection matrix.
	_ray.at( 1, _ssOrigin );

	// ndc space [ - 1.0, 1.0 ]
	_ssOrigin.w = 1;
	_ssOrigin.applyMatrix4( camera.matrixWorldInverse );
	_ssOrigin.applyMatrix4( projectionMatrix );
	_ssOrigin.multiplyScalar( 1 / _ssOrigin.w );

	// screen space
	_ssOrigin.x *= resolution.x / 2;
	_ssOrigin.y *= resolution.y / 2;
	_ssOrigin.z = 0;

	_ssOrigin3.copy( _ssOrigin );

	_mvMatrix.multiplyMatrices( camera.matrixWorldInverse, matrixWorld );

	for ( let i = 0, l = segmentCount; i < l; i ++ ) {

		_start4.fromBufferAttribute( instanceStart, i );
		_end4.fromBufferAttribute( instanceEnd, i );

		_start4.w = 1;
		_end4.w = 1;

		// camera space
		_start4.applyMatrix4( _mvMatrix );
		_end4.applyMatrix4( _mvMatrix );

		// skip the segment if it's entirely behind the camera
		const isBehindCameraNear = _start4.z > near && _end4.z > near;
		if ( isBehindCameraNear ) {

			continue;

		}

		// trim the segment if it extends behind camera near
		if ( _start4.z > near ) {

			const deltaDist = _start4.z - _end4.z;
			const t = ( _start4.z - near ) / deltaDist;
			_start4.lerp( _end4, t );

		} else if ( _end4.z > near ) {

			const deltaDist = _end4.z - _start4.z;
			const t = ( _end4.z - near ) / deltaDist;
			_end4.lerp( _start4, t );

		}

		// clip space
		_start4.applyMatrix4( projectionMatrix );
		_end4.applyMatrix4( projectionMatrix );

		// ndc space [ - 1.0, 1.0 ]
		_start4.multiplyScalar( 1 / _start4.w );
		_end4.multiplyScalar( 1 / _end4.w );

		// screen space
		_start4.x *= resolution.x / 2;
		_start4.y *= resolution.y / 2;

		_end4.x *= resolution.x / 2;
		_end4.y *= resolution.y / 2;

		// create 2d segment
		_line.start.copy( _start4 );
		_line.start.z = 0;

		_line.end.copy( _end4 );
		_line.end.z = 0;

		// get closest point on ray to segment
		const param = _line.closestPointToPointParameter( _ssOrigin3, true );
		_line.at( param, _closestPoint );

		// check if the intersection point is within clip space
		const zPos = MathUtils.lerp( _start4.z, _end4.z, param );
		const isInClipSpace = zPos >= - 1 && zPos <= 1;

		const isInside = _ssOrigin3.distanceTo( _closestPoint ) < _lineWidth * 0.5;

		if ( isInClipSpace && isInside ) {

			_line.start.fromBufferAttribute( instanceStart, i );
			_line.end.fromBufferAttribute( instanceEnd, i );

			_line.start.applyMatrix4( matrixWorld );
			_line.end.applyMatrix4( matrixWorld );

			const pointOnLine = new Vector3();
			const point = new Vector3();

			_ray.distanceSqToSegment( _line.start, _line.end, point, pointOnLine );

			intersects.push( {
				point: point,
				pointOnLine: pointOnLine,
				distance: _ray.origin.distanceTo( point ),
				object: lineSegments,
				face: null,
				faceIndex: i,
				uv: null,
				uv1: null,
			} );

		}

	}

}
```
</details>

### `LineSegments2.computeLineDistances(): LineSegments2`

**JSDoc:**
```typescript
/**
	 * Computes an array of distance values which are necessary for rendering dashed lines.
	 * For each vertex in the geometry, the method calculates the cumulative length from the
	 * current point to the very beginning of the line.
	 *
	 * @return {LineSegments2} A reference to this instance.
	 */
```

**Returns:** `LineSegments2`

**Calls:**

- `_start.fromBufferAttribute`
- `_end.fromBufferAttribute`
- `_start.distanceTo`
- `geometry.setAttribute`

**Internal Comments:**
```
// for backwards-compatibility, but could be a method of LineSegmentsGeometry... (x2)
```

<details><summary>Code</summary>

```typescript
computeLineDistances() {

		// for backwards-compatibility, but could be a method of LineSegmentsGeometry...

		const geometry = this.geometry;

		const instanceStart = geometry.attributes.instanceStart;
		const instanceEnd = geometry.attributes.instanceEnd;
		const lineDistances = new Float32Array( 2 * instanceStart.count );

		for ( let i = 0, j = 0, l = instanceStart.count; i < l; i ++, j += 2 ) {

			_start.fromBufferAttribute( instanceStart, i );
			_end.fromBufferAttribute( instanceEnd, i );

			lineDistances[ j ] = ( j === 0 ) ? 0 : lineDistances[ j - 1 ];
			lineDistances[ j + 1 ] = lineDistances[ j ] + _start.distanceTo( _end );

		}

		const instanceDistanceBuffer = new InstancedInterleavedBuffer( lineDistances, 2, 1 ); // d0, d1

		geometry.setAttribute( 'instanceDistanceStart', new InterleavedBufferAttribute( instanceDistanceBuffer, 1, 0 ) ); // d0
		geometry.setAttribute( 'instanceDistanceEnd', new InterleavedBufferAttribute( instanceDistanceBuffer, 1, 1 ) ); // d1

		return this;

	}
```
</details>

### `LineSegments2.onBeforeRender(renderer: any): void`

**Parameters:**

- **`renderer`** `any`

**Returns:** `void`

**Calls:**

- `renderer.getViewport`
- `this._resolution.set`

<details><summary>Code</summary>

```typescript
onBeforeRender( renderer ) {

		renderer.getViewport( _viewport );
		this._resolution.set( _viewport.z, _viewport.w );

	}
```
</details>

### `LineSegments2.raycast(raycaster: Raycaster, intersects: any[]): void`

**JSDoc:**
```typescript
/**
	 * Computes intersection points between a casted ray and this instance.
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
- `geometry.computeBoundingSphere`
- `_sphere.copy( geometry.boundingSphere ).applyMatrix4`
- `Math.max`
- `_sphere.distanceToPoint`
- `getWorldSpaceHalfWidth`
- `_ray.intersectsSphere`
- `geometry.computeBoundingBox`
- `_box.copy( geometry.boundingBox ).applyMatrix4`
- `_box.distanceToPoint`
- `_box.expandByScalar`
- `_ray.intersectsBox`
- `raycastWorldUnits`
- `raycastScreenSpace`

**Internal Comments:**
```
// check if we intersect the sphere bounds
// increase the sphere bounds by the worst case line screen space width (x2)
// check if we intersect the box bounds
// increase the box bounds by the worst case line width (x2)
```

<details><summary>Code</summary>

```typescript
raycast( raycaster, intersects ) {

		const worldUnits = this.material.worldUnits;
		const camera = raycaster.camera;

		if ( camera === null && ! worldUnits ) {

			console.error( 'LineSegments2: "Raycaster.camera" needs to be set in order to raycast against LineSegments2 while worldUnits is set to false.' );

		}

		const threshold = ( raycaster.params.Line2 !== undefined ) ? raycaster.params.Line2.threshold || 0 : 0;

		_ray = raycaster.ray;

		const matrixWorld = this.matrixWorld;
		const geometry = this.geometry;
		const material = this.material;

		_lineWidth = material.linewidth + threshold;

		// check if we intersect the sphere bounds
		if ( geometry.boundingSphere === null ) {

			geometry.computeBoundingSphere();

		}

		_sphere.copy( geometry.boundingSphere ).applyMatrix4( matrixWorld );

		// increase the sphere bounds by the worst case line screen space width
		let sphereMargin;
		if ( worldUnits ) {

			sphereMargin = _lineWidth * 0.5;

		} else {

			const distanceToSphere = Math.max( camera.near, _sphere.distanceToPoint( _ray.origin ) );
			sphereMargin = getWorldSpaceHalfWidth( camera, distanceToSphere, this._resolution );

		}

		_sphere.radius += sphereMargin;

		if ( _ray.intersectsSphere( _sphere ) === false ) {

			return;

		}

		// check if we intersect the box bounds
		if ( geometry.boundingBox === null ) {

			geometry.computeBoundingBox();

		}

		_box.copy( geometry.boundingBox ).applyMatrix4( matrixWorld );

		// increase the box bounds by the worst case line width
		let boxMargin;
		if ( worldUnits ) {

			boxMargin = _lineWidth * 0.5;

		} else {

			const distanceToBox = Math.max( camera.near, _box.distanceToPoint( _ray.origin ) );
			boxMargin = getWorldSpaceHalfWidth( camera, distanceToBox, this._resolution );

		}

		_box.expandByScalar( boxMargin );

		if ( _ray.intersectsBox( _box ) === false ) {

			return;

		}

		if ( worldUnits ) {

			raycastWorldUnits( this, intersects );

		} else {

			raycastScreenSpace( this, camera, intersects );

		}

	}
```
</details>


---

## Classes

### `LineSegments2`

<details><summary>Class Code</summary>

```ts
class LineSegments2 extends Mesh {

	/**
	 * Constructs a new wide line.
	 *
	 * @param {LineSegmentsGeometry} [geometry] - The line geometry.
	 * @param {Line2NodeMaterial} [material] - The line material.
	 */
	constructor( geometry = new LineSegmentsGeometry(), material = new Line2NodeMaterial( { color: Math.random() * 0xffffff } ) ) {

		super( geometry, material );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isLineSegments2 = true;

		this.type = 'LineSegments2';

		this._resolution = new Vector2();

	}

	/**
	 * Computes an array of distance values which are necessary for rendering dashed lines.
	 * For each vertex in the geometry, the method calculates the cumulative length from the
	 * current point to the very beginning of the line.
	 *
	 * @return {LineSegments2} A reference to this instance.
	 */
	computeLineDistances() {

		// for backwards-compatibility, but could be a method of LineSegmentsGeometry...

		const geometry = this.geometry;

		const instanceStart = geometry.attributes.instanceStart;
		const instanceEnd = geometry.attributes.instanceEnd;
		const lineDistances = new Float32Array( 2 * instanceStart.count );

		for ( let i = 0, j = 0, l = instanceStart.count; i < l; i ++, j += 2 ) {

			_start.fromBufferAttribute( instanceStart, i );
			_end.fromBufferAttribute( instanceEnd, i );

			lineDistances[ j ] = ( j === 0 ) ? 0 : lineDistances[ j - 1 ];
			lineDistances[ j + 1 ] = lineDistances[ j ] + _start.distanceTo( _end );

		}

		const instanceDistanceBuffer = new InstancedInterleavedBuffer( lineDistances, 2, 1 ); // d0, d1

		geometry.setAttribute( 'instanceDistanceStart', new InterleavedBufferAttribute( instanceDistanceBuffer, 1, 0 ) ); // d0
		geometry.setAttribute( 'instanceDistanceEnd', new InterleavedBufferAttribute( instanceDistanceBuffer, 1, 1 ) ); // d1

		return this;

	}

	onBeforeRender( renderer ) {

		renderer.getViewport( _viewport );
		this._resolution.set( _viewport.z, _viewport.w );

	}

	/**
	 * Computes intersection points between a casted ray and this instance.
	 *
	 * @param {Raycaster} raycaster - The raycaster.
	 * @param {Array<Object>} intersects - The target array that holds the intersection points.
	 */
	raycast( raycaster, intersects ) {

		const worldUnits = this.material.worldUnits;
		const camera = raycaster.camera;

		if ( camera === null && ! worldUnits ) {

			console.error( 'LineSegments2: "Raycaster.camera" needs to be set in order to raycast against LineSegments2 while worldUnits is set to false.' );

		}

		const threshold = ( raycaster.params.Line2 !== undefined ) ? raycaster.params.Line2.threshold || 0 : 0;

		_ray = raycaster.ray;

		const matrixWorld = this.matrixWorld;
		const geometry = this.geometry;
		const material = this.material;

		_lineWidth = material.linewidth + threshold;

		// check if we intersect the sphere bounds
		if ( geometry.boundingSphere === null ) {

			geometry.computeBoundingSphere();

		}

		_sphere.copy( geometry.boundingSphere ).applyMatrix4( matrixWorld );

		// increase the sphere bounds by the worst case line screen space width
		let sphereMargin;
		if ( worldUnits ) {

			sphereMargin = _lineWidth * 0.5;

		} else {

			const distanceToSphere = Math.max( camera.near, _sphere.distanceToPoint( _ray.origin ) );
			sphereMargin = getWorldSpaceHalfWidth( camera, distanceToSphere, this._resolution );

		}

		_sphere.radius += sphereMargin;

		if ( _ray.intersectsSphere( _sphere ) === false ) {

			return;

		}

		// check if we intersect the box bounds
		if ( geometry.boundingBox === null ) {

			geometry.computeBoundingBox();

		}

		_box.copy( geometry.boundingBox ).applyMatrix4( matrixWorld );

		// increase the box bounds by the worst case line width
		let boxMargin;
		if ( worldUnits ) {

			boxMargin = _lineWidth * 0.5;

		} else {

			const distanceToBox = Math.max( camera.near, _box.distanceToPoint( _ray.origin ) );
			boxMargin = getWorldSpaceHalfWidth( camera, distanceToBox, this._resolution );

		}

		_box.expandByScalar( boxMargin );

		if ( _ray.intersectsBox( _box ) === false ) {

			return;

		}

		if ( worldUnits ) {

			raycastWorldUnits( this, intersects );

		} else {

			raycastScreenSpace( this, camera, intersects );

		}

	}

}
```
</details>

#### Methods

##### `computeLineDistances(): LineSegments2`

<details><summary>Code</summary>

```ts
computeLineDistances() {

		// for backwards-compatibility, but could be a method of LineSegmentsGeometry...

		const geometry = this.geometry;

		const instanceStart = geometry.attributes.instanceStart;
		const instanceEnd = geometry.attributes.instanceEnd;
		const lineDistances = new Float32Array( 2 * instanceStart.count );

		for ( let i = 0, j = 0, l = instanceStart.count; i < l; i ++, j += 2 ) {

			_start.fromBufferAttribute( instanceStart, i );
			_end.fromBufferAttribute( instanceEnd, i );

			lineDistances[ j ] = ( j === 0 ) ? 0 : lineDistances[ j - 1 ];
			lineDistances[ j + 1 ] = lineDistances[ j ] + _start.distanceTo( _end );

		}

		const instanceDistanceBuffer = new InstancedInterleavedBuffer( lineDistances, 2, 1 ); // d0, d1

		geometry.setAttribute( 'instanceDistanceStart', new InterleavedBufferAttribute( instanceDistanceBuffer, 1, 0 ) ); // d0
		geometry.setAttribute( 'instanceDistanceEnd', new InterleavedBufferAttribute( instanceDistanceBuffer, 1, 1 ) ); // d1

		return this;

	}
```
</details>

##### `onBeforeRender(renderer: any): void`

<details><summary>Code</summary>

```ts
onBeforeRender( renderer ) {

		renderer.getViewport( _viewport );
		this._resolution.set( _viewport.z, _viewport.w );

	}
```
</details>

##### `raycast(raycaster: Raycaster, intersects: any[]): void`

<details><summary>Code</summary>

```ts
raycast( raycaster, intersects ) {

		const worldUnits = this.material.worldUnits;
		const camera = raycaster.camera;

		if ( camera === null && ! worldUnits ) {

			console.error( 'LineSegments2: "Raycaster.camera" needs to be set in order to raycast against LineSegments2 while worldUnits is set to false.' );

		}

		const threshold = ( raycaster.params.Line2 !== undefined ) ? raycaster.params.Line2.threshold || 0 : 0;

		_ray = raycaster.ray;

		const matrixWorld = this.matrixWorld;
		const geometry = this.geometry;
		const material = this.material;

		_lineWidth = material.linewidth + threshold;

		// check if we intersect the sphere bounds
		if ( geometry.boundingSphere === null ) {

			geometry.computeBoundingSphere();

		}

		_sphere.copy( geometry.boundingSphere ).applyMatrix4( matrixWorld );

		// increase the sphere bounds by the worst case line screen space width
		let sphereMargin;
		if ( worldUnits ) {

			sphereMargin = _lineWidth * 0.5;

		} else {

			const distanceToSphere = Math.max( camera.near, _sphere.distanceToPoint( _ray.origin ) );
			sphereMargin = getWorldSpaceHalfWidth( camera, distanceToSphere, this._resolution );

		}

		_sphere.radius += sphereMargin;

		if ( _ray.intersectsSphere( _sphere ) === false ) {

			return;

		}

		// check if we intersect the box bounds
		if ( geometry.boundingBox === null ) {

			geometry.computeBoundingBox();

		}

		_box.copy( geometry.boundingBox ).applyMatrix4( matrixWorld );

		// increase the box bounds by the worst case line width
		let boxMargin;
		if ( worldUnits ) {

			boxMargin = _lineWidth * 0.5;

		} else {

			const distanceToBox = Math.max( camera.near, _box.distanceToPoint( _ray.origin ) );
			boxMargin = getWorldSpaceHalfWidth( camera, distanceToBox, this._resolution );

		}

		_box.expandByScalar( boxMargin );

		if ( _ray.intersectsBox( _box ) === false ) {

			return;

		}

		if ( worldUnits ) {

			raycastWorldUnits( this, intersects );

		} else {

			raycastScreenSpace( this, camera, intersects );

		}

	}
```
</details>


---