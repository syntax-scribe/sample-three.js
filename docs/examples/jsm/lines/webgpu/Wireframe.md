[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Wireframe.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/lines/webgpu/Wireframe.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `InstancedInterleavedBuffer` | `three/webgpu` |
| `InterleavedBufferAttribute` | `three/webgpu` |
| `Line2NodeMaterial` | `three/webgpu` |
| `Mesh` | `three/webgpu` |
| `Vector3` | `three/webgpu` |
| `LineSegmentsGeometry` | `../../lines/LineSegmentsGeometry.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_start` | `any` | let/var | `new Vector3()` | ✗ |
| `_end` | `any` | let/var | `new Vector3()` | ✗ |
| `geometry` | `any` | let/var | `this.geometry` | ✗ |
| `instanceStart` | `any` | let/var | `geometry.attributes.instanceStart` | ✗ |
| `instanceEnd` | `any` | let/var | `geometry.attributes.instanceEnd` | ✗ |
| `lineDistances` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( 2 * instanceStart.count )` | ✗ |
| `instanceDistanceBuffer` | `any` | let/var | `new InstancedInterleavedBuffer( lineDistances, 2, 1 )` | ✗ |


---

## Functions

### `Wireframe.computeLineDistances(): Wireframe`

**JSDoc:**
```typescript
/**
	 * Computes an array of distance values which are necessary for rendering dashed lines.
	 * For each vertex in the geometry, the method calculates the cumulative length from the
	 * current point to the very beginning of the line.
	 *
	 * @return {Wireframe} A reference to this instance.
	 */
```

**Returns:** `Wireframe`

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


---

## Classes

### `Wireframe`

<details><summary>Class Code</summary>

```ts
class Wireframe extends Mesh {

	/**
	 * Constructs a new wireframe.
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
		this.isWireframe = true;

		this.type = 'Wireframe';

	}

	/**
	 * Computes an array of distance values which are necessary for rendering dashed lines.
	 * For each vertex in the geometry, the method calculates the cumulative length from the
	 * current point to the very beginning of the line.
	 *
	 * @return {Wireframe} A reference to this instance.
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

}
```
</details>

#### Methods

##### `computeLineDistances(): Wireframe`

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


---