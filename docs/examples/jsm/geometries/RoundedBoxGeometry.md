[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RoundedBoxGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 15 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/geometries/RoundedBoxGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BoxGeometry` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_tempNormal` | `any` | let/var | `new Vector3()` | ✗ |
| `totArcLength` | `number` | let/var | `2 * Math.PI * radius / 4` | ✗ |
| `halfArc` | `number` | let/var | `Math.PI / 4` | ✗ |
| `arcUvRatio` | `number` | let/var | `0.5 * totArcLength / ( totArcLength + centerLength )` | ✗ |
| `arcAngleRatio` | `number` | let/var | `1.0 - ( _tempNormal.angleTo( faceDirVector ) / halfArc )` | ✗ |
| `lenUv` | `number` | let/var | `centerLength / ( totArcLength + centerLength )` | ✗ |
| `totalSegments` | `number` | let/var | `segments * 2 + 1` | ✗ |
| `position` | `any` | let/var | `new Vector3()` | ✗ |
| `normal` | `any` | let/var | `new Vector3()` | ✗ |
| `positions` | `any` | let/var | `this.attributes.position.array` | ✗ |
| `normals` | `any` | let/var | `this.attributes.normal.array` | ✗ |
| `uvs` | `any` | let/var | `this.attributes.uv.array` | ✗ |
| `faceTris` | `number` | let/var | `positions.length / 6` | ✗ |
| `faceDirVector` | `any` | let/var | `new Vector3()` | ✗ |
| `halfSegmentSize` | `number` | let/var | `0.5 / totalSegments` | ✗ |


---

## Functions

### `getUv(faceDirVector: any, normal: any, uvAxis: any, projectionAxis: any, radius: any, sideLength: any): number`

**Parameters:**

- **`faceDirVector`** `any`
- **`normal`** `any`
- **`uvAxis`** `any`
- **`projectionAxis`** `any`
- **`radius`** `any`
- **`sideLength`** `any`

**Returns:** `number`

**Calls:**

- `Math.max`
- `_tempNormal.copy`
- `_tempNormal.normalize`
- `_tempNormal.angleTo`
- `Math.sign`

**Internal Comments:**
```
// length of the planes between the arcs on each axis (x2)
// Get the vector projected onto the Y plane (x4)
// total amount of UV space alloted to a single arc (x2)
// the distance along one arc the point is at (x2)
// total amount of UV space alloted to the plane between the arcs (x2)
```

<details><summary>Code</summary>

```typescript
function getUv( faceDirVector, normal, uvAxis, projectionAxis, radius, sideLength ) {

	const totArcLength = 2 * Math.PI * radius / 4;

	// length of the planes between the arcs on each axis
	const centerLength = Math.max( sideLength - 2 * radius, 0 );
	const halfArc = Math.PI / 4;

	// Get the vector projected onto the Y plane
	_tempNormal.copy( normal );
	_tempNormal[ projectionAxis ] = 0;
	_tempNormal.normalize();

	// total amount of UV space alloted to a single arc
	const arcUvRatio = 0.5 * totArcLength / ( totArcLength + centerLength );

	// the distance along one arc the point is at
	const arcAngleRatio = 1.0 - ( _tempNormal.angleTo( faceDirVector ) / halfArc );

	if ( Math.sign( _tempNormal[ uvAxis ] ) === 1 ) {

		return arcAngleRatio * arcUvRatio;

	} else {

		// total amount of UV space alloted to the plane between the arcs
		const lenUv = centerLength / ( totArcLength + centerLength );
		return lenUv + arcUvRatio + arcUvRatio * ( 1.0 - arcAngleRatio );

	}

}
```
</details>

### `RoundedBoxGeometry.fromJSON(data: any): RoundedBoxGeometry`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @returns {RoundedBoxGeometry} A new instance.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `RoundedBoxGeometry`

<details><summary>Code</summary>

```typescript
static fromJSON( data ) {

		return new RoundedBoxGeometry(
			data.width,
			data.height,
			data.depth,
			data.segments,
			data.radius
		);

	}
```
</details>


---

## Classes

### `RoundedBoxGeometry`

<details><summary>Class Code</summary>

```ts
class RoundedBoxGeometry extends BoxGeometry {

	/**
	 * Constructs a new rounded box geometry.
	 *
	 * @param {number} [width=1] - The width. That is, the length of the edges parallel to the X axis.
	 * @param {number} [height=1] - The height. That is, the length of the edges parallel to the Y axis.
	 * @param {number} [depth=1] - The depth. That is, the length of the edges parallel to the Z axis.
	 * @param {number} [segments=2] - Number of segments that form the rounded corners.
	 * @param {number} [radius=0.1] - The radius of the rounded corners.
	 */
	constructor( width = 1, height = 1, depth = 1, segments = 2, radius = 0.1 ) {

		// calculate total segments needed &
		// ensure it's odd so that we have a plane connecting the rounded corners
		const totalSegments = segments * 2 + 1;

		// ensure radius isn't bigger than shortest side
		radius = Math.min( width / 2, height / 2, depth / 2, radius );

		// start with a unit box geometry, its vertices will be modified to form the rounded box
		super( 1, 1, 1, totalSegments, totalSegments, totalSegments );

		this.type = 'RoundedBoxGeometry';

		/**
		 * Holds the constructor parameters that have been
		 * used to generate the geometry. Any modification
		 * after instantiation does not change the geometry.
		 *
		 * @type {Object}
		 */
		this.parameters = {
			width: width,
			height: height,
			depth: depth,
			segments: segments,
			radius: radius,
		};

		// if totalSegments is 1, no rounding is needed - return regular box
		if ( totalSegments === 1 ) return;

		const geometry2 = this.toNonIndexed();

		this.index = null;
		this.attributes.position = geometry2.attributes.position;
		this.attributes.normal = geometry2.attributes.normal;
		this.attributes.uv = geometry2.attributes.uv;

		//

		const position = new Vector3();
		const normal = new Vector3();

		const box = new Vector3( width, height, depth ).divideScalar( 2 ).subScalar( radius );

		const positions = this.attributes.position.array;
		const normals = this.attributes.normal.array;
		const uvs = this.attributes.uv.array;

		const faceTris = positions.length / 6;
		const faceDirVector = new Vector3();
		const halfSegmentSize = 0.5 / totalSegments;

		for ( let i = 0, j = 0; i < positions.length; i += 3, j += 2 ) {

			position.fromArray( positions, i );
			normal.copy( position );
			normal.x -= Math.sign( normal.x ) * halfSegmentSize;
			normal.y -= Math.sign( normal.y ) * halfSegmentSize;
			normal.z -= Math.sign( normal.z ) * halfSegmentSize;
			normal.normalize();

			positions[ i + 0 ] = box.x * Math.sign( position.x ) + normal.x * radius;
			positions[ i + 1 ] = box.y * Math.sign( position.y ) + normal.y * radius;
			positions[ i + 2 ] = box.z * Math.sign( position.z ) + normal.z * radius;

			normals[ i + 0 ] = normal.x;
			normals[ i + 1 ] = normal.y;
			normals[ i + 2 ] = normal.z;

			const side = Math.floor( i / faceTris );

			switch ( side ) {

				case 0: // right

					// generate UVs along Z then Y
					faceDirVector.set( 1, 0, 0 );
					uvs[ j + 0 ] = getUv( faceDirVector, normal, 'z', 'y', radius, depth );
					uvs[ j + 1 ] = 1.0 - getUv( faceDirVector, normal, 'y', 'z', radius, height );
					break;

				case 1: // left

					// generate UVs along Z then Y
					faceDirVector.set( - 1, 0, 0 );
					uvs[ j + 0 ] = 1.0 - getUv( faceDirVector, normal, 'z', 'y', radius, depth );
					uvs[ j + 1 ] = 1.0 - getUv( faceDirVector, normal, 'y', 'z', radius, height );
					break;

				case 2: // top

					// generate UVs along X then Z
					faceDirVector.set( 0, 1, 0 );
					uvs[ j + 0 ] = 1.0 - getUv( faceDirVector, normal, 'x', 'z', radius, width );
					uvs[ j + 1 ] = getUv( faceDirVector, normal, 'z', 'x', radius, depth );
					break;

				case 3: // bottom

					// generate UVs along X then Z
					faceDirVector.set( 0, - 1, 0 );
					uvs[ j + 0 ] = 1.0 - getUv( faceDirVector, normal, 'x', 'z', radius, width );
					uvs[ j + 1 ] = 1.0 - getUv( faceDirVector, normal, 'z', 'x', radius, depth );
					break;

				case 4: // front

					// generate UVs along X then Y
					faceDirVector.set( 0, 0, 1 );
					uvs[ j + 0 ] = 1.0 - getUv( faceDirVector, normal, 'x', 'y', radius, width );
					uvs[ j + 1 ] = 1.0 - getUv( faceDirVector, normal, 'y', 'x', radius, height );
					break;

				case 5: // back

					// generate UVs along X then Y
					faceDirVector.set( 0, 0, - 1 );
					uvs[ j + 0 ] = getUv( faceDirVector, normal, 'x', 'y', radius, width );
					uvs[ j + 1 ] = 1.0 - getUv( faceDirVector, normal, 'y', 'x', radius, height );
					break;

			}

		}

	}

	/**
	 * Factory method for creating an instance of this class from the given
	 * JSON object.
	 *
	 * @param {Object} data - A JSON object representing the serialized geometry.
	 * @returns {RoundedBoxGeometry} A new instance.
	 */
	static fromJSON( data ) {

		return new RoundedBoxGeometry(
			data.width,
			data.height,
			data.depth,
			data.segments,
			data.radius
		);

	}


}
```
</details>

#### Methods

##### `fromJSON(data: any): RoundedBoxGeometry`

<details><summary>Code</summary>

```ts
static fromJSON( data ) {

		return new RoundedBoxGeometry(
			data.width,
			data.height,
			data.depth,
			data.segments,
			data.radius
		);

	}
```
</details>


---