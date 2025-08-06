[⬅️ Back to Table of Contents](../../index.md)

# 📄 `WireframeGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 15 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/geometries/WireframeGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `../core/BufferGeometry.js` |
| `Float32BufferAttribute` | `../core/BufferAttribute.js` |
| `Vector3` | `../math/Vector3.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `vertices` | `any[]` | let/var | `[]` | ✗ |
| `edges` | `Set<any>` | let/var | `new Set()` | ✗ |
| `start` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `end` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `position` | `any` | let/var | `geometry.attributes.position` | ✗ |
| `indices` | `BufferAttribute` | let/var | `geometry.index` | ✗ |
| `groups` | `any[]` | let/var | `geometry.groups` | ✗ |
| `group` | `any` | let/var | `groups[ o ]` | ✗ |
| `groupStart` | `any` | let/var | `group.start` | ✗ |
| `groupCount` | `any` | let/var | `group.count` | ✗ |
| `position` | `any` | let/var | `geometry.attributes.position` | ✗ |
| `index1` | `number` | let/var | `3 * i + j` | ✗ |
| `index2` | `number` | let/var | `3 * i + ( ( j + 1 ) % 3 )` | ✗ |
| `hash1` | `string` | let/var | ``${start.x},${start.y},${start.z}-${end.x},${end.y},${end.z}`` | ✗ |
| `hash2` | `string` | let/var | ``${end.x},${end.y},${end.z}-${start.x},${start.y},${start.z}`` | ✗ |


---

## Functions

### `WireframeGeometry.copy(source: any): this`

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

### `isUniqueEdge(start: any, end: any, edges: any): boolean`

**Parameters:**

- **`start`** `any`
- **`end`** `any`
- **`edges`** `any`

**Returns:** `boolean`

**Calls:**

- `edges.has`
- `edges.add`

<details><summary>Code</summary>

```typescript
function isUniqueEdge( start, end, edges ) {

	const hash1 = `${start.x},${start.y},${start.z}-${end.x},${end.y},${end.z}`;
	const hash2 = `${end.x},${end.y},${end.z}-${start.x},${start.y},${start.z}`; // coincident edge

	if ( edges.has( hash1 ) === true || edges.has( hash2 ) === true ) {

		return false;

	} else {

		edges.add( hash1 );
		edges.add( hash2 );
		return true;

	}

}
```
</details>


---

## Classes

### `WireframeGeometry`

<details><summary>Class Code</summary>

```ts
class WireframeGeometry extends BufferGeometry {

	/**
	 * Constructs a new wireframe geometry.
	 *
	 * @param {?BufferGeometry} [geometry=null] - The geometry.
	 */
	constructor( geometry = null ) {

		super();

		this.type = 'WireframeGeometry';

		/**
		 * Holds the constructor parameters that have been
		 * used to generate the geometry. Any modification
		 * after instantiation does not change the geometry.
		 *
		 * @type {Object}
		 */
		this.parameters = {
			geometry: geometry
		};

		if ( geometry !== null ) {

			// buffer

			const vertices = [];
			const edges = new Set();

			// helper variables

			const start = new Vector3();
			const end = new Vector3();

			if ( geometry.index !== null ) {

				// indexed BufferGeometry

				const position = geometry.attributes.position;
				const indices = geometry.index;
				let groups = geometry.groups;

				if ( groups.length === 0 ) {

					groups = [ { start: 0, count: indices.count, materialIndex: 0 } ];

				}

				// create a data structure that contains all edges without duplicates

				for ( let o = 0, ol = groups.length; o < ol; ++ o ) {

					const group = groups[ o ];

					const groupStart = group.start;
					const groupCount = group.count;

					for ( let i = groupStart, l = ( groupStart + groupCount ); i < l; i += 3 ) {

						for ( let j = 0; j < 3; j ++ ) {

							const index1 = indices.getX( i + j );
							const index2 = indices.getX( i + ( j + 1 ) % 3 );

							start.fromBufferAttribute( position, index1 );
							end.fromBufferAttribute( position, index2 );

							if ( isUniqueEdge( start, end, edges ) === true ) {

								vertices.push( start.x, start.y, start.z );
								vertices.push( end.x, end.y, end.z );

							}

						}

					}

				}

			} else {

				// non-indexed BufferGeometry

				const position = geometry.attributes.position;

				for ( let i = 0, l = ( position.count / 3 ); i < l; i ++ ) {

					for ( let j = 0; j < 3; j ++ ) {

						// three edges per triangle, an edge is represented as (index1, index2)
						// e.g. the first triangle has the following edges: (0,1),(1,2),(2,0)

						const index1 = 3 * i + j;
						const index2 = 3 * i + ( ( j + 1 ) % 3 );

						start.fromBufferAttribute( position, index1 );
						end.fromBufferAttribute( position, index2 );

						if ( isUniqueEdge( start, end, edges ) === true ) {

							vertices.push( start.x, start.y, start.z );
							vertices.push( end.x, end.y, end.z );

						}

					}

				}

			}

			// build geometry

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