[⬅️ Back to Table of Contents](../../index.md)

# 📄 `EdgesGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 18 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/geometries/EdgesGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `../core/BufferGeometry.js` |
| `Float32BufferAttribute` | `../core/BufferAttribute.js` |
| `DEG2RAD` | `../math/MathUtils.js` |
| `Triangle` | `../math/Triangle.js` |
| `Vector3` | `../math/Vector3.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_v0` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_v1` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_normal` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_triangle` | `Triangle` | let/var | `new Triangle()` | ✗ |
| `precisionPoints` | `4` | let/var | `4` | ✗ |
| `indexCount` | `any` | let/var | `indexAttr ? indexAttr.count : positionAttr.count` | ✗ |
| `indexArr` | `number[]` | let/var | `[ 0, 0, 0 ]` | ✗ |
| `vertKeys` | `string[]` | let/var | `[ 'a', 'b', 'c' ]` | ✗ |
| `hashes` | `any[]` | let/var | `new Array( 3 )` | ✗ |
| `edgeData` | `{}` | let/var | `{}` | ✗ |
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `jNext` | `number` | let/var | `( j + 1 ) % 3` | ✗ |
| `vecHash0` | `any` | let/var | `hashes[ j ]` | ✗ |
| `vecHash1` | `any` | let/var | `hashes[ jNext ]` | ✗ |
| `v0` | `any` | let/var | `_triangle[ vertKeys[ j ] ]` | ✗ |
| `v1` | `any` | let/var | `_triangle[ vertKeys[ jNext ] ]` | ✗ |
| `hash` | `string` | let/var | ``${ vecHash0 }_${ vecHash1 }`` | ✗ |
| `reverseHash` | `string` | let/var | ``${ vecHash1 }_${ vecHash0 }`` | ✗ |


---

## Functions

### `EdgesGeometry.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `Object.assign`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.parameters = Object.assign( {}, source.parameters );

		return this;

	}
```
</details>


---

## Classes

### `EdgesGeometry`

<details><summary>Class Code</summary>

```ts
class EdgesGeometry extends BufferGeometry {

	/**
	 * Constructs a new edges geometry.
	 *
	 * @param {?BufferGeometry} [geometry=null] - The geometry.
	 * @param {number} [thresholdAngle=1] - An edge is only rendered if the angle (in degrees)
	 * between the face normals of the adjoining faces exceeds this value.
	 */
	constructor( geometry = null, thresholdAngle = 1 ) {

		super();

		this.type = 'EdgesGeometry';

		/**
		 * Holds the constructor parameters that have been
		 * used to generate the geometry. Any modification
		 * after instantiation does not change the geometry.
		 *
		 * @type {Object}
		 */
		this.parameters = {
			geometry: geometry,
			thresholdAngle: thresholdAngle
		};

		if ( geometry !== null ) {

			const precisionPoints = 4;
			const precision = Math.pow( 10, precisionPoints );
			const thresholdDot = Math.cos( DEG2RAD * thresholdAngle );

			const indexAttr = geometry.getIndex();
			const positionAttr = geometry.getAttribute( 'position' );
			const indexCount = indexAttr ? indexAttr.count : positionAttr.count;

			const indexArr = [ 0, 0, 0 ];
			const vertKeys = [ 'a', 'b', 'c' ];
			const hashes = new Array( 3 );

			const edgeData = {};
			const vertices = [];
			for ( let i = 0; i < indexCount; i += 3 ) {

				if ( indexAttr ) {

					indexArr[ 0 ] = indexAttr.getX( i );
					indexArr[ 1 ] = indexAttr.getX( i + 1 );
					indexArr[ 2 ] = indexAttr.getX( i + 2 );

				} else {

					indexArr[ 0 ] = i;
					indexArr[ 1 ] = i + 1;
					indexArr[ 2 ] = i + 2;

				}

				const { a, b, c } = _triangle;
				a.fromBufferAttribute( positionAttr, indexArr[ 0 ] );
				b.fromBufferAttribute( positionAttr, indexArr[ 1 ] );
				c.fromBufferAttribute( positionAttr, indexArr[ 2 ] );
				_triangle.getNormal( _normal );

				// create hashes for the edge from the vertices
				hashes[ 0 ] = `${ Math.round( a.x * precision ) },${ Math.round( a.y * precision ) },${ Math.round( a.z * precision ) }`;
				hashes[ 1 ] = `${ Math.round( b.x * precision ) },${ Math.round( b.y * precision ) },${ Math.round( b.z * precision ) }`;
				hashes[ 2 ] = `${ Math.round( c.x * precision ) },${ Math.round( c.y * precision ) },${ Math.round( c.z * precision ) }`;

				// skip degenerate triangles
				if ( hashes[ 0 ] === hashes[ 1 ] || hashes[ 1 ] === hashes[ 2 ] || hashes[ 2 ] === hashes[ 0 ] ) {

					continue;

				}

				// iterate over every edge
				for ( let j = 0; j < 3; j ++ ) {

					// get the first and next vertex making up the edge
					const jNext = ( j + 1 ) % 3;
					const vecHash0 = hashes[ j ];
					const vecHash1 = hashes[ jNext ];
					const v0 = _triangle[ vertKeys[ j ] ];
					const v1 = _triangle[ vertKeys[ jNext ] ];

					const hash = `${ vecHash0 }_${ vecHash1 }`;
					const reverseHash = `${ vecHash1 }_${ vecHash0 }`;

					if ( reverseHash in edgeData && edgeData[ reverseHash ] ) {

						// if we found a sibling edge add it into the vertex array if
						// it meets the angle threshold and delete the edge from the map.
						if ( _normal.dot( edgeData[ reverseHash ].normal ) <= thresholdDot ) {

							vertices.push( v0.x, v0.y, v0.z );
							vertices.push( v1.x, v1.y, v1.z );

						}

						edgeData[ reverseHash ] = null;

					} else if ( ! ( hash in edgeData ) ) {

						// if we've already got an edge here then skip adding a new one
						edgeData[ hash ] = {

							index0: indexArr[ j ],
							index1: indexArr[ jNext ],
							normal: _normal.clone(),

						};

					}

				}

			}

			// iterate over all remaining, unmatched edges and add them to the vertex array
			for ( const key in edgeData ) {

				if ( edgeData[ key ] ) {

					const { index0, index1 } = edgeData[ key ];
					_v0.fromBufferAttribute( positionAttr, index0 );
					_v1.fromBufferAttribute( positionAttr, index1 );

					vertices.push( _v0.x, _v0.y, _v0.z );
					vertices.push( _v1.x, _v1.y, _v1.z );

				}

			}

			this.setAttribute( 'position', new Float32BufferAttribute( vertices, 3 ) );

		}

	}

	copy( source ) {

		super.copy( source );

		this.parameters = Object.assign( {}, source.parameters );

		return this;

	}

}
```
</details>

#### Methods

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source );

		this.parameters = Object.assign( {}, source.parameters );

		return this;

	}
```
</details>


---