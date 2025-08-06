[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `EdgeSplitModifier.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 21 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/modifiers/EdgeSplitModifier.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferAttribute` | `three` |
| `BufferGeometry` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_A` | `any` | let/var | `new Vector3()` | ✗ |
| `_B` | `any` | let/var | `new Vector3()` | ✗ |
| `_C` | `any` | let/var | `new Vector3()` | ✗ |
| `index` | `any` | let/var | `indexes[ i ]` | ✗ |
| `index` | `any` | let/var | `indexes[ i ]` | ✗ |
| `result` | `{ splitGroup: any[]; currentGroup: an...` | let/var | `{ splitGroup: [], currentGroup: [ firstIndex ] }` | ✗ |
| `groupResults` | `any[]` | let/var | `[]` | ✗ |
| `result` | `{ splitGroup: any[]; currentGroup: an...` | let/var | `groupResults[ 0 ]` | ✗ |
| `hadNormals` | `boolean` | let/var | `false` | ✗ |
| `oldNormals` | `any` | let/var | `null` | ✗ |
| `indexes` | `any` | let/var | `geometry.index.array` | ✗ |
| `positions` | `any` | let/var | `geometry.getAttribute( 'position' ).array` | ✗ |
| `normals` | `any` | let/var | `*not shown*` | ✗ |
| `pointToIndexMap` | `any` | let/var | `*not shown*` | ✗ |
| `splitIndexes` | `any[]` | let/var | `[]` | ✗ |
| `newAttributes` | `{}` | let/var | `{}` | ✗ |
| `oldAttribute` | `any` | let/var | `geometry.attributes[ name ]` | ✗ |
| `newArray` | `any` | let/var | `new oldAttribute.array.constructor( ( indexes.length + splitIndexes.length ) ...` | ✗ |
| `newIndexes` | `Uint32Array<any>` | let/var | `new Uint32Array( indexes.length )` | ✗ |
| `split` | `any` | let/var | `splitIndexes[ i ]` | ✗ |
| `index` | `any` | let/var | `indexes[ split.original ]` | ✗ |


---

## Functions

### `EdgeSplitModifier.modify(geometry: BufferGeometry, cutOffAngle: number, tryKeepNormals: boolean): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Returns a new, modified version of the given geometry by applying an edge-split operation.
	 * Please note that the resulting geometry is always indexed.
	 *
	 * @param {BufferGeometry} geometry - The geometry to modify.
	 * @param {number} cutOffAngle - The cut off angle in radians.
	 * @param {boolean} [tryKeepNormals=true] - Whether to try to keep normals or not.
	 * @return {BufferGeometry} A new, modified geometry.
	 */
```

**Parameters:**

- **`geometry`** `BufferGeometry`
- **`cutOffAngle`** `number`
- **`tryKeepNormals`** `boolean`

**Returns:** `BufferGeometry`

**Calls:**

- `_A.set`
- `_B.set`
- `_C.set`
- `_C.sub`
- `_A.sub`
- `_C.cross( _A ).normalize`
- `Array`
- `pointToIndexMap[ index ].push`
- `_A.set( normals[ 3 * firstIndex ], normals[ 3 * firstIndex + 1 ], normals[ 3 * firstIndex + 2 ] ).normalize`
- `_B.set( normals[ 3 * j ], normals[ 3 * j + 1 ], normals[ 3 * j + 2 ] ).normalize`
- `_B.dot`
- `result.splitGroup.push`
- `result.currentGroup.push`
- `groupResults.push`
- `edgeSplitToGroups`
- `splitIndexes.push`
- `edgeSplit`
- `geometry.clone`
- `geometry.deleteAttribute`
- `BufferGeometryUtils.mergeVertices`
- `geometry.getAttribute`
- `computeNormals`
- `mapPositionsToIndexes`
- `Math.cos`
- `Object.keys`
- `newArray.set`
- `newIndexes.set`
- `Object.values`
- `geometry.setIndex`
- `geometry.setAttribute`
- `geometry.computeVertexNormals`
- `new Array( oldNormals.length / 3 ).fill`

<details><summary>Code</summary>

```typescript
modify( geometry, cutOffAngle, tryKeepNormals = true ) {

		function computeNormals() {

			normals = new Float32Array( indexes.length * 3 );

			for ( let i = 0; i < indexes.length; i += 3 ) {

				let index = indexes[ i ];

				_A.set(
					positions[ 3 * index ],
					positions[ 3 * index + 1 ],
					positions[ 3 * index + 2 ] );

				index = indexes[ i + 1 ];
				_B.set(
					positions[ 3 * index ],
					positions[ 3 * index + 1 ],
					positions[ 3 * index + 2 ] );

				index = indexes[ i + 2 ];
				_C.set(
					positions[ 3 * index ],
					positions[ 3 * index + 1 ],
					positions[ 3 * index + 2 ] );

				_C.sub( _B );
				_A.sub( _B );

				const normal = _C.cross( _A ).normalize();

				for ( let j = 0; j < 3; j ++ ) {

					normals[ 3 * ( i + j ) ] = normal.x;
					normals[ 3 * ( i + j ) + 1 ] = normal.y;
					normals[ 3 * ( i + j ) + 2 ] = normal.z;

				}

			}

		}


		function mapPositionsToIndexes() {

			pointToIndexMap = Array( positions.length / 3 );

			for ( let i = 0; i < indexes.length; i ++ ) {

				const index = indexes[ i ];

				if ( pointToIndexMap[ index ] == null ) {

					pointToIndexMap[ index ] = [];

				}

				pointToIndexMap[ index ].push( i );

			}

		}


		function edgeSplitToGroups( indexes, cutOff, firstIndex ) {

			_A.set( normals[ 3 * firstIndex ], normals[ 3 * firstIndex + 1 ], normals[ 3 * firstIndex + 2 ] ).normalize();

			const result = {
				splitGroup: [],
				currentGroup: [ firstIndex ]
			};

			for ( const j of indexes ) {

				if ( j !== firstIndex ) {

					_B.set( normals[ 3 * j ], normals[ 3 * j + 1 ], normals[ 3 * j + 2 ] ).normalize();

					if ( _B.dot( _A ) < cutOff ) {

						result.splitGroup.push( j );

					} else {

						result.currentGroup.push( j );

					}

				}

			}

			return result;

		}


		function edgeSplit( indexes, cutOff, original = null ) {

			if ( indexes.length === 0 ) return;

			const groupResults = [];

			for ( const index of indexes ) {

				groupResults.push( edgeSplitToGroups( indexes, cutOff, index ) );

			}

			let result = groupResults[ 0 ];

			for ( const groupResult of groupResults ) {

				if ( groupResult.currentGroup.length > result.currentGroup.length ) {

					result = groupResult;

				}

			}


			if ( original != null ) {

				splitIndexes.push( {
					original: original,
					indexes: result.currentGroup
				} );

			}

			if ( result.splitGroup.length ) {

				edgeSplit( result.splitGroup, cutOff, original || result.currentGroup[ 0 ] );

			}

		}

		let hadNormals = false;
		let oldNormals = null;

		if ( geometry.attributes.normal ) {

			hadNormals = true;

			geometry = geometry.clone();

			if ( tryKeepNormals === true && geometry.index !== null ) {

				oldNormals = geometry.attributes.normal.array;

			}

			geometry.deleteAttribute( 'normal' );

		}

		if ( geometry.index == null ) {

			geometry = BufferGeometryUtils.mergeVertices( geometry );

		}

		const indexes = geometry.index.array;
		const positions = geometry.getAttribute( 'position' ).array;

		let normals;
		let pointToIndexMap;

		computeNormals();
		mapPositionsToIndexes();

		const splitIndexes = [];

		for ( const vertexIndexes of pointToIndexMap ) {

			edgeSplit( vertexIndexes, Math.cos( cutOffAngle ) - 0.001 );

		}

		const newAttributes = {};
		for ( const name of Object.keys( geometry.attributes ) ) {

			const oldAttribute = geometry.attributes[ name ];
			const newArray = new oldAttribute.array.constructor( ( indexes.length + splitIndexes.length ) * oldAttribute.itemSize );
			newArray.set( oldAttribute.array );
			newAttributes[ name ] = new BufferAttribute( newArray, oldAttribute.itemSize, oldAttribute.normalized );

		}

		const newIndexes = new Uint32Array( indexes.length );
		newIndexes.set( indexes );

		for ( let i = 0; i < splitIndexes.length; i ++ ) {

			const split = splitIndexes[ i ];
			const index = indexes[ split.original ];

			for ( const attribute of Object.values( newAttributes ) ) {

				for ( let j = 0; j < attribute.itemSize; j ++ ) {

					attribute.array[ ( indexes.length + i ) * attribute.itemSize + j ] =
						attribute.array[ index * attribute.itemSize + j ];

				}

			}

			for ( const j of split.indexes ) {

				newIndexes[ j ] = indexes.length + i;

			}

		}

		geometry = new BufferGeometry();
		geometry.setIndex( new BufferAttribute( newIndexes, 1 ) );

		for ( const name of Object.keys( newAttributes ) ) {

			geometry.setAttribute( name, newAttributes[ name ] );

		}

		if ( hadNormals ) {

			geometry.computeVertexNormals();

			if ( oldNormals !== null ) {

				const changedNormals = new Array( oldNormals.length / 3 ).fill( false );

				for ( const splitData of splitIndexes )
					changedNormals[ splitData.original ] = true;

				for ( let i = 0; i < changedNormals.length; i ++ ) {

					if ( changedNormals[ i ] === false ) {

						for ( let j = 0; j < 3; j ++ )
							geometry.attributes.normal.array[ 3 * i + j ] = oldNormals[ 3 * i + j ];

					}

				}


			}

		}

		return geometry;

	}
```
</details>

### `computeNormals(): void`

**Returns:** `void`

**Calls:**

- `_A.set`
- `_B.set`
- `_C.set`
- `_C.sub`
- `_A.sub`
- `_C.cross( _A ).normalize`

<details><summary>Code</summary>

```typescript
function computeNormals() {

			normals = new Float32Array( indexes.length * 3 );

			for ( let i = 0; i < indexes.length; i += 3 ) {

				let index = indexes[ i ];

				_A.set(
					positions[ 3 * index ],
					positions[ 3 * index + 1 ],
					positions[ 3 * index + 2 ] );

				index = indexes[ i + 1 ];
				_B.set(
					positions[ 3 * index ],
					positions[ 3 * index + 1 ],
					positions[ 3 * index + 2 ] );

				index = indexes[ i + 2 ];
				_C.set(
					positions[ 3 * index ],
					positions[ 3 * index + 1 ],
					positions[ 3 * index + 2 ] );

				_C.sub( _B );
				_A.sub( _B );

				const normal = _C.cross( _A ).normalize();

				for ( let j = 0; j < 3; j ++ ) {

					normals[ 3 * ( i + j ) ] = normal.x;
					normals[ 3 * ( i + j ) + 1 ] = normal.y;
					normals[ 3 * ( i + j ) + 2 ] = normal.z;

				}

			}

		}
```
</details>

### `mapPositionsToIndexes(): void`

**Returns:** `void`

**Calls:**

- `Array`
- `pointToIndexMap[ index ].push`

<details><summary>Code</summary>

```typescript
function mapPositionsToIndexes() {

			pointToIndexMap = Array( positions.length / 3 );

			for ( let i = 0; i < indexes.length; i ++ ) {

				const index = indexes[ i ];

				if ( pointToIndexMap[ index ] == null ) {

					pointToIndexMap[ index ] = [];

				}

				pointToIndexMap[ index ].push( i );

			}

		}
```
</details>

### `edgeSplitToGroups(indexes: any, cutOff: any, firstIndex: any): { splitGroup: any[]; currentGroup: any[]; }`

**Parameters:**

- **`indexes`** `any`
- **`cutOff`** `any`
- **`firstIndex`** `any`

**Returns:** `{ splitGroup: any[]; currentGroup: any[]; }`

**Calls:**

- `_A.set( normals[ 3 * firstIndex ], normals[ 3 * firstIndex + 1 ], normals[ 3 * firstIndex + 2 ] ).normalize`
- `_B.set( normals[ 3 * j ], normals[ 3 * j + 1 ], normals[ 3 * j + 2 ] ).normalize`
- `_B.dot`
- `result.splitGroup.push`
- `result.currentGroup.push`

<details><summary>Code</summary>

```typescript
function edgeSplitToGroups( indexes, cutOff, firstIndex ) {

			_A.set( normals[ 3 * firstIndex ], normals[ 3 * firstIndex + 1 ], normals[ 3 * firstIndex + 2 ] ).normalize();

			const result = {
				splitGroup: [],
				currentGroup: [ firstIndex ]
			};

			for ( const j of indexes ) {

				if ( j !== firstIndex ) {

					_B.set( normals[ 3 * j ], normals[ 3 * j + 1 ], normals[ 3 * j + 2 ] ).normalize();

					if ( _B.dot( _A ) < cutOff ) {

						result.splitGroup.push( j );

					} else {

						result.currentGroup.push( j );

					}

				}

			}

			return result;

		}
```
</details>

### `edgeSplit(indexes: any, cutOff: any, original: any): void`

**Parameters:**

- **`indexes`** `any`
- **`cutOff`** `any`
- **`original`** `any`

**Returns:** `void`

**Calls:**

- `groupResults.push`
- `edgeSplitToGroups`
- `splitIndexes.push`
- `edgeSplit`

<details><summary>Code</summary>

```typescript
function edgeSplit( indexes, cutOff, original = null ) {

			if ( indexes.length === 0 ) return;

			const groupResults = [];

			for ( const index of indexes ) {

				groupResults.push( edgeSplitToGroups( indexes, cutOff, index ) );

			}

			let result = groupResults[ 0 ];

			for ( const groupResult of groupResults ) {

				if ( groupResult.currentGroup.length > result.currentGroup.length ) {

					result = groupResult;

				}

			}


			if ( original != null ) {

				splitIndexes.push( {
					original: original,
					indexes: result.currentGroup
				} );

			}

			if ( result.splitGroup.length ) {

				edgeSplit( result.splitGroup, cutOff, original || result.currentGroup[ 0 ] );

			}

		}
```
</details>


---

## Classes

### `EdgeSplitModifier`

<details><summary>Class Code</summary>

```ts
class EdgeSplitModifier {

	/**
	 * Returns a new, modified version of the given geometry by applying an edge-split operation.
	 * Please note that the resulting geometry is always indexed.
	 *
	 * @param {BufferGeometry} geometry - The geometry to modify.
	 * @param {number} cutOffAngle - The cut off angle in radians.
	 * @param {boolean} [tryKeepNormals=true] - Whether to try to keep normals or not.
	 * @return {BufferGeometry} A new, modified geometry.
	 */
	modify( geometry, cutOffAngle, tryKeepNormals = true ) {

		function computeNormals() {

			normals = new Float32Array( indexes.length * 3 );

			for ( let i = 0; i < indexes.length; i += 3 ) {

				let index = indexes[ i ];

				_A.set(
					positions[ 3 * index ],
					positions[ 3 * index + 1 ],
					positions[ 3 * index + 2 ] );

				index = indexes[ i + 1 ];
				_B.set(
					positions[ 3 * index ],
					positions[ 3 * index + 1 ],
					positions[ 3 * index + 2 ] );

				index = indexes[ i + 2 ];
				_C.set(
					positions[ 3 * index ],
					positions[ 3 * index + 1 ],
					positions[ 3 * index + 2 ] );

				_C.sub( _B );
				_A.sub( _B );

				const normal = _C.cross( _A ).normalize();

				for ( let j = 0; j < 3; j ++ ) {

					normals[ 3 * ( i + j ) ] = normal.x;
					normals[ 3 * ( i + j ) + 1 ] = normal.y;
					normals[ 3 * ( i + j ) + 2 ] = normal.z;

				}

			}

		}


		function mapPositionsToIndexes() {

			pointToIndexMap = Array( positions.length / 3 );

			for ( let i = 0; i < indexes.length; i ++ ) {

				const index = indexes[ i ];

				if ( pointToIndexMap[ index ] == null ) {

					pointToIndexMap[ index ] = [];

				}

				pointToIndexMap[ index ].push( i );

			}

		}


		function edgeSplitToGroups( indexes, cutOff, firstIndex ) {

			_A.set( normals[ 3 * firstIndex ], normals[ 3 * firstIndex + 1 ], normals[ 3 * firstIndex + 2 ] ).normalize();

			const result = {
				splitGroup: [],
				currentGroup: [ firstIndex ]
			};

			for ( const j of indexes ) {

				if ( j !== firstIndex ) {

					_B.set( normals[ 3 * j ], normals[ 3 * j + 1 ], normals[ 3 * j + 2 ] ).normalize();

					if ( _B.dot( _A ) < cutOff ) {

						result.splitGroup.push( j );

					} else {

						result.currentGroup.push( j );

					}

				}

			}

			return result;

		}


		function edgeSplit( indexes, cutOff, original = null ) {

			if ( indexes.length === 0 ) return;

			const groupResults = [];

			for ( const index of indexes ) {

				groupResults.push( edgeSplitToGroups( indexes, cutOff, index ) );

			}

			let result = groupResults[ 0 ];

			for ( const groupResult of groupResults ) {

				if ( groupResult.currentGroup.length > result.currentGroup.length ) {

					result = groupResult;

				}

			}


			if ( original != null ) {

				splitIndexes.push( {
					original: original,
					indexes: result.currentGroup
				} );

			}

			if ( result.splitGroup.length ) {

				edgeSplit( result.splitGroup, cutOff, original || result.currentGroup[ 0 ] );

			}

		}

		let hadNormals = false;
		let oldNormals = null;

		if ( geometry.attributes.normal ) {

			hadNormals = true;

			geometry = geometry.clone();

			if ( tryKeepNormals === true && geometry.index !== null ) {

				oldNormals = geometry.attributes.normal.array;

			}

			geometry.deleteAttribute( 'normal' );

		}

		if ( geometry.index == null ) {

			geometry = BufferGeometryUtils.mergeVertices( geometry );

		}

		const indexes = geometry.index.array;
		const positions = geometry.getAttribute( 'position' ).array;

		let normals;
		let pointToIndexMap;

		computeNormals();
		mapPositionsToIndexes();

		const splitIndexes = [];

		for ( const vertexIndexes of pointToIndexMap ) {

			edgeSplit( vertexIndexes, Math.cos( cutOffAngle ) - 0.001 );

		}

		const newAttributes = {};
		for ( const name of Object.keys( geometry.attributes ) ) {

			const oldAttribute = geometry.attributes[ name ];
			const newArray = new oldAttribute.array.constructor( ( indexes.length + splitIndexes.length ) * oldAttribute.itemSize );
			newArray.set( oldAttribute.array );
			newAttributes[ name ] = new BufferAttribute( newArray, oldAttribute.itemSize, oldAttribute.normalized );

		}

		const newIndexes = new Uint32Array( indexes.length );
		newIndexes.set( indexes );

		for ( let i = 0; i < splitIndexes.length; i ++ ) {

			const split = splitIndexes[ i ];
			const index = indexes[ split.original ];

			for ( const attribute of Object.values( newAttributes ) ) {

				for ( let j = 0; j < attribute.itemSize; j ++ ) {

					attribute.array[ ( indexes.length + i ) * attribute.itemSize + j ] =
						attribute.array[ index * attribute.itemSize + j ];

				}

			}

			for ( const j of split.indexes ) {

				newIndexes[ j ] = indexes.length + i;

			}

		}

		geometry = new BufferGeometry();
		geometry.setIndex( new BufferAttribute( newIndexes, 1 ) );

		for ( const name of Object.keys( newAttributes ) ) {

			geometry.setAttribute( name, newAttributes[ name ] );

		}

		if ( hadNormals ) {

			geometry.computeVertexNormals();

			if ( oldNormals !== null ) {

				const changedNormals = new Array( oldNormals.length / 3 ).fill( false );

				for ( const splitData of splitIndexes )
					changedNormals[ splitData.original ] = true;

				for ( let i = 0; i < changedNormals.length; i ++ ) {

					if ( changedNormals[ i ] === false ) {

						for ( let j = 0; j < 3; j ++ )
							geometry.attributes.normal.array[ 3 * i + j ] = oldNormals[ 3 * i + j ];

					}

				}


			}

		}

		return geometry;

	}

}
```
</details>

#### Methods

##### `modify(geometry: BufferGeometry, cutOffAngle: number, tryKeepNormals: boolean): BufferGeometry`

<details><summary>Code</summary>

```ts
modify( geometry, cutOffAngle, tryKeepNormals = true ) {

		function computeNormals() {

			normals = new Float32Array( indexes.length * 3 );

			for ( let i = 0; i < indexes.length; i += 3 ) {

				let index = indexes[ i ];

				_A.set(
					positions[ 3 * index ],
					positions[ 3 * index + 1 ],
					positions[ 3 * index + 2 ] );

				index = indexes[ i + 1 ];
				_B.set(
					positions[ 3 * index ],
					positions[ 3 * index + 1 ],
					positions[ 3 * index + 2 ] );

				index = indexes[ i + 2 ];
				_C.set(
					positions[ 3 * index ],
					positions[ 3 * index + 1 ],
					positions[ 3 * index + 2 ] );

				_C.sub( _B );
				_A.sub( _B );

				const normal = _C.cross( _A ).normalize();

				for ( let j = 0; j < 3; j ++ ) {

					normals[ 3 * ( i + j ) ] = normal.x;
					normals[ 3 * ( i + j ) + 1 ] = normal.y;
					normals[ 3 * ( i + j ) + 2 ] = normal.z;

				}

			}

		}


		function mapPositionsToIndexes() {

			pointToIndexMap = Array( positions.length / 3 );

			for ( let i = 0; i < indexes.length; i ++ ) {

				const index = indexes[ i ];

				if ( pointToIndexMap[ index ] == null ) {

					pointToIndexMap[ index ] = [];

				}

				pointToIndexMap[ index ].push( i );

			}

		}


		function edgeSplitToGroups( indexes, cutOff, firstIndex ) {

			_A.set( normals[ 3 * firstIndex ], normals[ 3 * firstIndex + 1 ], normals[ 3 * firstIndex + 2 ] ).normalize();

			const result = {
				splitGroup: [],
				currentGroup: [ firstIndex ]
			};

			for ( const j of indexes ) {

				if ( j !== firstIndex ) {

					_B.set( normals[ 3 * j ], normals[ 3 * j + 1 ], normals[ 3 * j + 2 ] ).normalize();

					if ( _B.dot( _A ) < cutOff ) {

						result.splitGroup.push( j );

					} else {

						result.currentGroup.push( j );

					}

				}

			}

			return result;

		}


		function edgeSplit( indexes, cutOff, original = null ) {

			if ( indexes.length === 0 ) return;

			const groupResults = [];

			for ( const index of indexes ) {

				groupResults.push( edgeSplitToGroups( indexes, cutOff, index ) );

			}

			let result = groupResults[ 0 ];

			for ( const groupResult of groupResults ) {

				if ( groupResult.currentGroup.length > result.currentGroup.length ) {

					result = groupResult;

				}

			}


			if ( original != null ) {

				splitIndexes.push( {
					original: original,
					indexes: result.currentGroup
				} );

			}

			if ( result.splitGroup.length ) {

				edgeSplit( result.splitGroup, cutOff, original || result.currentGroup[ 0 ] );

			}

		}

		let hadNormals = false;
		let oldNormals = null;

		if ( geometry.attributes.normal ) {

			hadNormals = true;

			geometry = geometry.clone();

			if ( tryKeepNormals === true && geometry.index !== null ) {

				oldNormals = geometry.attributes.normal.array;

			}

			geometry.deleteAttribute( 'normal' );

		}

		if ( geometry.index == null ) {

			geometry = BufferGeometryUtils.mergeVertices( geometry );

		}

		const indexes = geometry.index.array;
		const positions = geometry.getAttribute( 'position' ).array;

		let normals;
		let pointToIndexMap;

		computeNormals();
		mapPositionsToIndexes();

		const splitIndexes = [];

		for ( const vertexIndexes of pointToIndexMap ) {

			edgeSplit( vertexIndexes, Math.cos( cutOffAngle ) - 0.001 );

		}

		const newAttributes = {};
		for ( const name of Object.keys( geometry.attributes ) ) {

			const oldAttribute = geometry.attributes[ name ];
			const newArray = new oldAttribute.array.constructor( ( indexes.length + splitIndexes.length ) * oldAttribute.itemSize );
			newArray.set( oldAttribute.array );
			newAttributes[ name ] = new BufferAttribute( newArray, oldAttribute.itemSize, oldAttribute.normalized );

		}

		const newIndexes = new Uint32Array( indexes.length );
		newIndexes.set( indexes );

		for ( let i = 0; i < splitIndexes.length; i ++ ) {

			const split = splitIndexes[ i ];
			const index = indexes[ split.original ];

			for ( const attribute of Object.values( newAttributes ) ) {

				for ( let j = 0; j < attribute.itemSize; j ++ ) {

					attribute.array[ ( indexes.length + i ) * attribute.itemSize + j ] =
						attribute.array[ index * attribute.itemSize + j ];

				}

			}

			for ( const j of split.indexes ) {

				newIndexes[ j ] = indexes.length + i;

			}

		}

		geometry = new BufferGeometry();
		geometry.setIndex( new BufferAttribute( newIndexes, 1 ) );

		for ( const name of Object.keys( newAttributes ) ) {

			geometry.setAttribute( name, newAttributes[ name ] );

		}

		if ( hadNormals ) {

			geometry.computeVertexNormals();

			if ( oldNormals !== null ) {

				const changedNormals = new Array( oldNormals.length / 3 ).fill( false );

				for ( const splitData of splitIndexes )
					changedNormals[ splitData.original ] = true;

				for ( let i = 0; i < changedNormals.length; i ++ ) {

					if ( changedNormals[ i ] === false ) {

						for ( let j = 0; j < 3; j ++ )
							geometry.attributes.normal.array[ 3 * i + j ] = oldNormals[ 3 * i + j ];

					}

				}


			}

		}

		return geometry;

	}
```
</details>


---