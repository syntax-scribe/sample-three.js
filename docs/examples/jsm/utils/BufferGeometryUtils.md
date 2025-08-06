[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BufferGeometryUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 16 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 150 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/utils/BufferGeometryUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferAttribute` | `three` |
| `BufferGeometry` | `three` |
| `Float32BufferAttribute` | `three` |
| `InstancedBufferAttribute` | `three` |
| `InterleavedBuffer` | `three` |
| `InterleavedBufferAttribute` | `three` |
| `TriangleFanDrawMode` | `three` |
| `TriangleStripDrawMode` | `three` |
| `TrianglesDrawMode` | `three` |
| `Vector3` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `dstArray` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( attribute.count * attribute.itemSize )` | ✗ |
| `_geometry` | `any` | let/var | `geometry.index ? geometry.toNonIndexed() : geometry` | ✗ |
| `isIndexed` | `boolean` | let/var | `geometries[ 0 ].index !== null` | ✗ |
| `attributesUsed` | `Set<string>` | let/var | `new Set( Object.keys( geometries[ 0 ].attributes ) )` | ✗ |
| `morphAttributesUsed` | `Set<string>` | let/var | `new Set( Object.keys( geometries[ 0 ].morphAttributes ) )` | ✗ |
| `attributes` | `{}` | let/var | `{}` | ✗ |
| `morphAttributes` | `{}` | let/var | `{}` | ✗ |
| `morphTargetsRelative` | `any` | let/var | `geometries[ 0 ].morphTargetsRelative` | ✗ |
| `mergedGeometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `offset` | `number` | let/var | `0` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `geometries[ i ]` | ✗ |
| `attributesCount` | `number` | let/var | `0` | ✗ |
| `count` | `any` | let/var | `*not shown*` | ✗ |
| `indexOffset` | `number` | let/var | `0` | ✗ |
| `mergedIndex` | `any[]` | let/var | `[]` | ✗ |
| `index` | `any` | let/var | `geometries[ i ].index` | ✗ |
| `numMorphTargets` | `any` | let/var | `morphAttributes[ name ][ 0 ].length` | ✗ |
| `morphAttributesToMerge` | `any[]` | let/var | `[]` | ✗ |
| `TypedArray` | `any` | let/var | `*not shown*` | ✗ |
| `itemSize` | `any` | let/var | `*not shown*` | ✗ |
| `normalized` | `any` | let/var | `*not shown*` | ✗ |
| `gpuType` | `number` | let/var | `- 1` | ✗ |
| `arrayLength` | `number` | let/var | `0` | ✗ |
| `attribute` | `BufferAttribute` | let/var | `attributes[ i ]` | ✗ |
| `array` | `any` | let/var | `new TypedArray( arrayLength )` | ✗ |
| `result` | `any` | let/var | `new BufferAttribute( array, itemSize, normalized )` | ✗ |
| `offset` | `number` | let/var | `0` | ✗ |
| `attribute` | `BufferAttribute` | let/var | `attributes[ i ]` | ✗ |
| `tupleOffset` | `number` | let/var | `offset / itemSize` | ✗ |
| `TypedArray` | `any` | let/var | `*not shown*` | ✗ |
| `arrayLength` | `number` | let/var | `0` | ✗ |
| `stride` | `number` | let/var | `0` | ✗ |
| `attribute` | `BufferAttribute` | let/var | `attributes[ i ]` | ✗ |
| `interleavedBuffer` | `any` | let/var | `new InterleavedBuffer( new TypedArray( arrayLength ), stride )` | ✗ |
| `offset` | `number` | let/var | `0` | ✗ |
| `res` | `any[]` | let/var | `[]` | ✗ |
| `getters` | `string[]` | let/var | `[ 'getX', 'getY', 'getZ', 'getW' ]` | ✗ |
| `setters` | `string[]` | let/var | `[ 'setX', 'setY', 'setZ', 'setW' ]` | ✗ |
| `attribute` | `BufferAttribute` | let/var | `attributes[ j ]` | ✗ |
| `itemSize` | `any` | let/var | `attribute.itemSize` | ✗ |
| `count` | `any` | let/var | `attribute.count` | ✗ |
| `iba` | `any` | let/var | `new InterleavedBufferAttribute( interleavedBuffer, itemSize, offset, attribut...` | ✗ |
| `cons` | `any` | let/var | `attribute.data.array.constructor` | ✗ |
| `count` | `any` | let/var | `attribute.count` | ✗ |
| `itemSize` | `any` | let/var | `attribute.itemSize` | ✗ |
| `normalized` | `any` | let/var | `attribute.normalized` | ✗ |
| `array` | `any` | let/var | `new cons( count * itemSize )` | ✗ |
| `newAttribute` | `any` | let/var | `*not shown*` | ✗ |
| `attributes` | `any` | let/var | `geometry.attributes` | ✗ |
| `morphTargets` | `any` | let/var | `geometry.morphTargets` | ✗ |
| `attrMap` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `attr` | `any` | let/var | `attributes[ key ]` | ✗ |
| `attr` | `any` | let/var | `morphTargets[ key ]` | ✗ |
| `mem` | `number` | let/var | `0` | ✗ |
| `hashToIndex` | `{}` | let/var | `{}` | ✗ |
| `vertexCount` | `any` | let/var | `indices ? indices.count : positions.count` | ✗ |
| `nextIndex` | `number` | let/var | `0` | ✗ |
| `tmpAttributes` | `{}` | let/var | `{}` | ✗ |
| `tmpMorphAttributes` | `{}` | let/var | `{}` | ✗ |
| `newIndices` | `any[]` | let/var | `[]` | ✗ |
| `getters` | `string[]` | let/var | `[ 'getX', 'getY', 'getZ', 'getW' ]` | ✗ |
| `setters` | `string[]` | let/var | `[ 'setX', 'setY', 'setZ', 'setW' ]` | ✗ |
| `name` | `string` | let/var | `attributeNames[ i ]` | ✗ |
| `attr` | `any` | let/var | `geometry.attributes[ name ]` | ✗ |
| `morphAttributes` | `any` | let/var | `geometry.morphAttributes[ name ]` | ✗ |
| `array` | `any` | let/var | `new morphAttr.array.constructor( morphAttr.count * morphAttr.itemSize )` | ✗ |
| `halfTolerance` | `number` | let/var | `tolerance * 0.5` | ✗ |
| `hashAdditive` | `number` | let/var | `halfTolerance * hashMultiplier` | ✗ |
| `index` | `any` | let/var | `indices ? indices.getX( i ) : i` | ✗ |
| `hash` | `string` | let/var | `''` | ✗ |
| `name` | `string` | let/var | `attributeNames[ j ]` | ✗ |
| `itemSize` | `any` | let/var | `attribute.itemSize` | ✗ |
| `name` | `string` | let/var | `attributeNames[ j ]` | ✗ |
| `morphAttributes` | `any` | let/var | `geometry.morphAttributes[ name ]` | ✗ |
| `itemSize` | `any` | let/var | `attribute.itemSize` | ✗ |
| `newArray` | `any` | let/var | `tmpAttributes[ name ]` | ✗ |
| `newMorphArrays` | `any` | let/var | `tmpMorphAttributes[ name ]` | ✗ |
| `getterFunc` | `string` | let/var | `getters[ k ]` | ✗ |
| `setterFunc` | `string` | let/var | `setters[ k ]` | ✗ |
| `tmpAttribute` | `any` | let/var | `tmpAttributes[ name ]` | ✗ |
| `tmpMorphAttribute` | `any` | let/var | `tmpMorphAttributes[ name ][ j ]` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `numberOfTriangles` | `number` | let/var | `index.count - 2` | ✗ |
| `newIndices` | `any[]` | let/var | `[]` | ✗ |
| `_vA` | `any` | let/var | `new Vector3()` | ✗ |
| `_vB` | `any` | let/var | `new Vector3()` | ✗ |
| `_vC` | `any` | let/var | `new Vector3()` | ✗ |
| `_tempA` | `any` | let/var | `new Vector3()` | ✗ |
| `_tempB` | `any` | let/var | `new Vector3()` | ✗ |
| `_tempC` | `any` | let/var | `new Vector3()` | ✗ |
| `_morphA` | `any` | let/var | `new Vector3()` | ✗ |
| `_morphB` | `any` | let/var | `new Vector3()` | ✗ |
| `_morphC` | `any` | let/var | `new Vector3()` | ✗ |
| `morphInfluences` | `any` | let/var | `object.morphTargetInfluences` | ✗ |
| `influence` | `any` | let/var | `morphInfluences[ i ]` | ✗ |
| `morph` | `any` | let/var | `morphAttribute[ i ]` | ✗ |
| `geometry` | `any` | let/var | `object.geometry` | ✗ |
| `material` | `any` | let/var | `object.material` | ✗ |
| `a` | `any` | let/var | `*not shown*` | ✗ |
| `b` | `any` | let/var | `*not shown*` | ✗ |
| `c` | `any` | let/var | `*not shown*` | ✗ |
| `index` | `any` | let/var | `geometry.index` | ✗ |
| `positionAttribute` | `any` | let/var | `geometry.attributes.position` | ✗ |
| `morphPosition` | `any` | let/var | `geometry.morphAttributes.position` | ✗ |
| `morphTargetsRelative` | `any` | let/var | `geometry.morphTargetsRelative` | ✗ |
| `normalAttribute` | `any` | let/var | `geometry.attributes.normal` | ✗ |
| `morphNormal` | `any` | let/var | `geometry.morphAttributes.position` | ✗ |
| `groups` | `any` | let/var | `geometry.groups` | ✗ |
| `drawRange` | `any` | let/var | `geometry.drawRange` | ✗ |
| `i` | `any` | let/var | `*not shown*` | ✗ |
| `j` | `any` | let/var | `*not shown*` | ✗ |
| `il` | `any` | let/var | `*not shown*` | ✗ |
| `jl` | `any` | let/var | `*not shown*` | ✗ |
| `group` | `any` | let/var | `*not shown*` | ✗ |
| `start` | `any` | let/var | `*not shown*` | ✗ |
| `end` | `any` | let/var | `*not shown*` | ✗ |
| `modifiedPosition` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( positionAttribute.count * positionAttribute.itemSize )` | ✗ |
| `modifiedNormal` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( normalAttribute.count * normalAttribute.itemSize )` | ✗ |
| `morphedPositionAttribute` | `any` | let/var | `new Float32BufferAttribute( modifiedPosition, 3 )` | ✗ |
| `morphedNormalAttribute` | `any` | let/var | `new Float32BufferAttribute( modifiedNormal, 3 )` | ✗ |
| `groups` | `any` | let/var | `geometry.groups` | ✗ |
| `indices` | `any[]` | let/var | `[]` | ✗ |
| `newIndices` | `any[]` | let/var | `[]` | ✗ |
| `group` | `any` | let/var | `groups[ i ]` | ✗ |
| `groupStart` | `any` | let/var | `group.start` | ✗ |
| `groupLength` | `any` | let/var | `groupStart + group.count` | ✗ |
| `start` | `number` | let/var | `0` | ✗ |
| `group` | `any` | let/var | `groups[ i ]` | ✗ |
| `currentGroup` | `any` | let/var | `groups[ 0 ]` | ✗ |
| `group` | `any` | let/var | `groups[ i ]` | ✗ |
| `hashMultiplier` | `number` | let/var | `( 1 + 1e-10 ) * 1e2` | ✗ |
| `verts` | `any[]` | let/var | `[ new Vector3(), new Vector3(), new Vector3() ]` | ✗ |
| `tempVec1` | `any` | let/var | `new Vector3()` | ✗ |
| `tempVec2` | `any` | let/var | `new Vector3()` | ✗ |
| `tempNorm` | `any` | let/var | `new Vector3()` | ✗ |
| `tempNorm2` | `any` | let/var | `new Vector3()` | ✗ |
| `x` | `number` | let/var | `~ ~ ( v.x * hashMultiplier )` | ✗ |
| `y` | `number` | let/var | `~ ~ ( v.y * hashMultiplier )` | ✗ |
| `z` | `number` | let/var | `~ ~ ( v.z * hashMultiplier )` | ✗ |
| `resultGeometry` | `any` | let/var | `geometry.index ? geometry.toNonIndexed() : geometry` | ✗ |
| `posAttr` | `any` | let/var | `resultGeometry.attributes.position` | ✗ |
| `vertexMap` | `{}` | let/var | `{}` | ✗ |
| `i3` | `number` | let/var | `3 * i` | ✗ |
| `vert` | `any` | let/var | `verts[ n ]` | ✗ |
| `normalArray` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( posAttr.count * 3 )` | ✗ |
| `normAttr` | `any` | let/var | `new BufferAttribute( normalArray, 3, false )` | ✗ |
| `i3` | `number` | let/var | `3 * i` | ✗ |
| `vert` | `any` | let/var | `verts[ n ]` | ✗ |
| `otherNormals` | `any` | let/var | `vertexMap[ hash ]` | ✗ |
| `otherNorm` | `any` | let/var | `otherNormals[ k ]` | ✗ |


---

## Functions

### `computeMikkTSpaceTangents(geometry: BufferGeometry, MikkTSpace: any, negateSign: boolean): BufferGeometry`

**JSDoc:**
```typescript
/**
 * Computes vertex tangents using the MikkTSpace algorithm. MikkTSpace generates the same tangents consistently,
 * and is used in most modelling tools and normal map bakers. Use MikkTSpace for materials with normal maps,
 * because inconsistent tangents may lead to subtle visual issues in the normal map, particularly around mirrored
 * UV seams.
 *
 * In comparison to this method, {@link BufferGeometry#computeTangents} (a custom algorithm) generates tangents that
 * probably will not match the tangents in other software. The custom algorithm is sufficient for general use with a
 * custom material, and may be faster than MikkTSpace.
 *
 * Returns the original BufferGeometry. Indexed geometries will be de-indexed. Requires position, normal, and uv attributes.
 *
 * @param {BufferGeometry} geometry - The geometry to compute tangents for.
 * @param {Object} MikkTSpace - Instance of `examples/jsm/libs/mikktspace.module.js`, or `mikktspace` npm package.
 * Await `MikkTSpace.ready` before use.
 * @param {boolean} [negateSign=true] - Whether to negate the sign component (.w) of each tangent.
 * Required for normal map conventions in some formats, including glTF.
 * @return {BufferGeometry} The updated geometry.
 */
```

**Parameters:**

- **`geometry`** `BufferGeometry`
- **`MikkTSpace`** `any`
- **`negateSign`** `boolean`

**Returns:** `BufferGeometry`

**Calls:**

- `geometry.hasAttribute`
- `attribute.getX`
- `attribute.getY`
- `attribute.getZ`
- `geometry.toNonIndexed`
- `MikkTSpace.generateTangents`
- `getAttributeArray`
- `_geometry.setAttribute`
- `geometry.copy`

**Internal Comments:**
```
// MikkTSpace algorithm requires non-indexed input. (x2)
// Compute vertex tangents. (x2)
// Texture coordinate convention of glTF differs from the apparent
// default of the MikkTSpace library; .w component must be flipped.
// (x4)
```

<details><summary>Code</summary>

```typescript
function computeMikkTSpaceTangents( geometry, MikkTSpace, negateSign = true ) {

	if ( ! MikkTSpace || ! MikkTSpace.isReady ) {

		throw new Error( 'BufferGeometryUtils: Initialized MikkTSpace library required.' );

	}

	if ( ! geometry.hasAttribute( 'position' ) || ! geometry.hasAttribute( 'normal' ) || ! geometry.hasAttribute( 'uv' ) ) {

		throw new Error( 'BufferGeometryUtils: Tangents require "position", "normal", and "uv" attributes.' );

	}

	function getAttributeArray( attribute ) {

		if ( attribute.normalized || attribute.isInterleavedBufferAttribute ) {

			const dstArray = new Float32Array( attribute.count * attribute.itemSize );

			for ( let i = 0, j = 0; i < attribute.count; i ++ ) {

				dstArray[ j ++ ] = attribute.getX( i );
				dstArray[ j ++ ] = attribute.getY( i );

				if ( attribute.itemSize > 2 ) {

					dstArray[ j ++ ] = attribute.getZ( i );

				}

			}

			return dstArray;

		}

		if ( attribute.array instanceof Float32Array ) {

			return attribute.array;

		}

		return new Float32Array( attribute.array );

	}

	// MikkTSpace algorithm requires non-indexed input.

	const _geometry = geometry.index ? geometry.toNonIndexed() : geometry;

	// Compute vertex tangents.

	const tangents = MikkTSpace.generateTangents(

		getAttributeArray( _geometry.attributes.position ),
		getAttributeArray( _geometry.attributes.normal ),
		getAttributeArray( _geometry.attributes.uv )

	);

	// Texture coordinate convention of glTF differs from the apparent
	// default of the MikkTSpace library; .w component must be flipped.

	if ( negateSign ) {

		for ( let i = 3; i < tangents.length; i += 4 ) {

			tangents[ i ] *= - 1;

		}

	}

	//

	_geometry.setAttribute( 'tangent', new BufferAttribute( tangents, 4 ) );

	if ( geometry !== _geometry ) {

		geometry.copy( _geometry );

	}

	return geometry;

}
```
</details>

### `getAttributeArray(attribute: any): any`

**Parameters:**

- **`attribute`** `any`

**Returns:** `any`

**Calls:**

- `attribute.getX`
- `attribute.getY`
- `attribute.getZ`

<details><summary>Code</summary>

```typescript
function getAttributeArray( attribute ) {

		if ( attribute.normalized || attribute.isInterleavedBufferAttribute ) {

			const dstArray = new Float32Array( attribute.count * attribute.itemSize );

			for ( let i = 0, j = 0; i < attribute.count; i ++ ) {

				dstArray[ j ++ ] = attribute.getX( i );
				dstArray[ j ++ ] = attribute.getY( i );

				if ( attribute.itemSize > 2 ) {

					dstArray[ j ++ ] = attribute.getZ( i );

				}

			}

			return dstArray;

		}

		if ( attribute.array instanceof Float32Array ) {

			return attribute.array;

		}

		return new Float32Array( attribute.array );

	}
```
</details>

### `mergeGeometries(geometries: BufferGeometry[], useGroups: boolean): BufferGeometry`

**JSDoc:**
```typescript
/**
 * Merges a set of geometries into a single instance. All geometries must have compatible attributes.
 *
 * @param {Array<BufferGeometry>} geometries - The geometries to merge.
 * @param {boolean} [useGroups=false] - Whether to use groups or not.
 * @return {?BufferGeometry} The merged geometry. Returns `null` if the merge does not succeed.
 */
```

**Parameters:**

- **`geometries`** `BufferGeometry[]`
- **`useGroups`** `boolean`

**Returns:** `BufferGeometry`

**Calls:**

- `Object.keys`
- `console.error`
- `attributesUsed.has`
- `attributes[ name ].push`
- `morphAttributesUsed.has`
- `morphAttributes[ name ].push`
- `mergedGeometry.addGroup`
- `mergedIndex.push`
- `index.getX`
- `mergedGeometry.setIndex`
- `mergeAttributes`
- `mergedGeometry.setAttribute`
- `morphAttributesToMerge.push`
- `mergedGeometry.morphAttributes[ name ].push`

**Internal Comments:**
```
// ensure that all geometries are indexed, or none
// gather attributes, exit early if they're different
// ensure geometries have the same number of attributes
// gather morph attributes, exit early if they're different
// merge indices
// merge attributes
// merge morph attributes
```

<details><summary>Code</summary>

```typescript
function mergeGeometries( geometries, useGroups = false ) {

	const isIndexed = geometries[ 0 ].index !== null;

	const attributesUsed = new Set( Object.keys( geometries[ 0 ].attributes ) );
	const morphAttributesUsed = new Set( Object.keys( geometries[ 0 ].morphAttributes ) );

	const attributes = {};
	const morphAttributes = {};

	const morphTargetsRelative = geometries[ 0 ].morphTargetsRelative;

	const mergedGeometry = new BufferGeometry();

	let offset = 0;

	for ( let i = 0; i < geometries.length; ++ i ) {

		const geometry = geometries[ i ];
		let attributesCount = 0;

		// ensure that all geometries are indexed, or none

		if ( isIndexed !== ( geometry.index !== null ) ) {

			console.error( 'THREE.BufferGeometryUtils: .mergeGeometries() failed with geometry at index ' + i + '. All geometries must have compatible attributes; make sure index attribute exists among all geometries, or in none of them.' );
			return null;

		}

		// gather attributes, exit early if they're different

		for ( const name in geometry.attributes ) {

			if ( ! attributesUsed.has( name ) ) {

				console.error( 'THREE.BufferGeometryUtils: .mergeGeometries() failed with geometry at index ' + i + '. All geometries must have compatible attributes; make sure "' + name + '" attribute exists among all geometries, or in none of them.' );
				return null;

			}

			if ( attributes[ name ] === undefined ) attributes[ name ] = [];

			attributes[ name ].push( geometry.attributes[ name ] );

			attributesCount ++;

		}

		// ensure geometries have the same number of attributes

		if ( attributesCount !== attributesUsed.size ) {

			console.error( 'THREE.BufferGeometryUtils: .mergeGeometries() failed with geometry at index ' + i + '. Make sure all geometries have the same number of attributes.' );
			return null;

		}

		// gather morph attributes, exit early if they're different

		if ( morphTargetsRelative !== geometry.morphTargetsRelative ) {

			console.error( 'THREE.BufferGeometryUtils: .mergeGeometries() failed with geometry at index ' + i + '. .morphTargetsRelative must be consistent throughout all geometries.' );
			return null;

		}

		for ( const name in geometry.morphAttributes ) {

			if ( ! morphAttributesUsed.has( name ) ) {

				console.error( 'THREE.BufferGeometryUtils: .mergeGeometries() failed with geometry at index ' + i + '.  .morphAttributes must be consistent throughout all geometries.' );
				return null;

			}

			if ( morphAttributes[ name ] === undefined ) morphAttributes[ name ] = [];

			morphAttributes[ name ].push( geometry.morphAttributes[ name ] );

		}

		if ( useGroups ) {

			let count;

			if ( isIndexed ) {

				count = geometry.index.count;

			} else if ( geometry.attributes.position !== undefined ) {

				count = geometry.attributes.position.count;

			} else {

				console.error( 'THREE.BufferGeometryUtils: .mergeGeometries() failed with geometry at index ' + i + '. The geometry must have either an index or a position attribute' );
				return null;

			}

			mergedGeometry.addGroup( offset, count, i );

			offset += count;

		}

	}

	// merge indices

	if ( isIndexed ) {

		let indexOffset = 0;
		const mergedIndex = [];

		for ( let i = 0; i < geometries.length; ++ i ) {

			const index = geometries[ i ].index;

			for ( let j = 0; j < index.count; ++ j ) {

				mergedIndex.push( index.getX( j ) + indexOffset );

			}

			indexOffset += geometries[ i ].attributes.position.count;

		}

		mergedGeometry.setIndex( mergedIndex );

	}

	// merge attributes

	for ( const name in attributes ) {

		const mergedAttribute = mergeAttributes( attributes[ name ] );

		if ( ! mergedAttribute ) {

			console.error( 'THREE.BufferGeometryUtils: .mergeGeometries() failed while trying to merge the ' + name + ' attribute.' );
			return null;

		}

		mergedGeometry.setAttribute( name, mergedAttribute );

	}

	// merge morph attributes

	for ( const name in morphAttributes ) {

		const numMorphTargets = morphAttributes[ name ][ 0 ].length;

		if ( numMorphTargets === 0 ) break;

		mergedGeometry.morphAttributes = mergedGeometry.morphAttributes || {};
		mergedGeometry.morphAttributes[ name ] = [];

		for ( let i = 0; i < numMorphTargets; ++ i ) {

			const morphAttributesToMerge = [];

			for ( let j = 0; j < morphAttributes[ name ].length; ++ j ) {

				morphAttributesToMerge.push( morphAttributes[ name ][ j ][ i ] );

			}

			const mergedMorphAttribute = mergeAttributes( morphAttributesToMerge );

			if ( ! mergedMorphAttribute ) {

				console.error( 'THREE.BufferGeometryUtils: .mergeGeometries() failed while trying to merge the ' + name + ' morphAttribute.' );
				return null;

			}

			mergedGeometry.morphAttributes[ name ].push( mergedMorphAttribute );

		}

	}

	return mergedGeometry;

}
```
</details>

### `mergeAttributes(attributes: BufferAttribute[]): BufferAttribute`

**JSDoc:**
```typescript
/**
 * Merges a set of attributes into a single instance. All attributes must have compatible properties and types.
 * Instances of {@link InterleavedBufferAttribute} are not supported.
 *
 * @param {Array<BufferAttribute>} attributes - The attributes to merge.
 * @return {?BufferAttribute} The merged attribute. Returns `null` if the merge does not succeed.
 */
```

**Parameters:**

- **`attributes`** `BufferAttribute[]`

**Returns:** `BufferAttribute`

**Calls:**

- `console.error`
- `attribute.getComponent`
- `result.setComponent`
- `array.set`

<details><summary>Code</summary>

```typescript
function mergeAttributes( attributes ) {

	let TypedArray;
	let itemSize;
	let normalized;
	let gpuType = - 1;
	let arrayLength = 0;

	for ( let i = 0; i < attributes.length; ++ i ) {

		const attribute = attributes[ i ];

		if ( TypedArray === undefined ) TypedArray = attribute.array.constructor;
		if ( TypedArray !== attribute.array.constructor ) {

			console.error( 'THREE.BufferGeometryUtils: .mergeAttributes() failed. BufferAttribute.array must be of consistent array types across matching attributes.' );
			return null;

		}

		if ( itemSize === undefined ) itemSize = attribute.itemSize;
		if ( itemSize !== attribute.itemSize ) {

			console.error( 'THREE.BufferGeometryUtils: .mergeAttributes() failed. BufferAttribute.itemSize must be consistent across matching attributes.' );
			return null;

		}

		if ( normalized === undefined ) normalized = attribute.normalized;
		if ( normalized !== attribute.normalized ) {

			console.error( 'THREE.BufferGeometryUtils: .mergeAttributes() failed. BufferAttribute.normalized must be consistent across matching attributes.' );
			return null;

		}

		if ( gpuType === - 1 ) gpuType = attribute.gpuType;
		if ( gpuType !== attribute.gpuType ) {

			console.error( 'THREE.BufferGeometryUtils: .mergeAttributes() failed. BufferAttribute.gpuType must be consistent across matching attributes.' );
			return null;

		}

		arrayLength += attribute.count * itemSize;

	}

	const array = new TypedArray( arrayLength );
	const result = new BufferAttribute( array, itemSize, normalized );
	let offset = 0;

	for ( let i = 0; i < attributes.length; ++ i ) {

		const attribute = attributes[ i ];
		if ( attribute.isInterleavedBufferAttribute ) {

			const tupleOffset = offset / itemSize;
			for ( let j = 0, l = attribute.count; j < l; j ++ ) {

				for ( let c = 0; c < itemSize; c ++ ) {

					const value = attribute.getComponent( j, c );
					result.setComponent( j + tupleOffset, c, value );

				}

			}

		} else {

			array.set( attribute.array, offset );

		}

		offset += attribute.count * itemSize;

	}

	if ( gpuType !== undefined ) {

		result.gpuType = gpuType;

	}

	return result;

}
```
</details>

### `deepCloneAttribute(attribute: BufferAttribute): BufferAttribute`

**JSDoc:**
```typescript
/**
 * Performs a deep clone of the given buffer attribute.
 *
 * @param {BufferAttribute} attribute - The attribute to clone.
 * @return {BufferAttribute} The cloned attribute.
 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`

**Returns:** `BufferAttribute`

**Calls:**

- `deinterleaveAttribute`
- `new InstancedBufferAttribute().copy`
- `new BufferAttribute().copy`

<details><summary>Code</summary>

```typescript
function deepCloneAttribute( attribute ) {

	if ( attribute.isInstancedInterleavedBufferAttribute || attribute.isInterleavedBufferAttribute ) {

		return deinterleaveAttribute( attribute );

	}

	if ( attribute.isInstancedBufferAttribute ) {

		return new InstancedBufferAttribute().copy( attribute );

	}

	return new BufferAttribute().copy( attribute );

}
```
</details>

### `interleaveAttributes(attributes: BufferAttribute[]): InterleavedBufferAttribute[]`

**JSDoc:**
```typescript
/**
 * Interleaves a set of attributes and returns a new array of corresponding attributes that share a
 * single {@link InterleavedBuffer} instance. All attributes must have compatible types.
 *
 * @param {Array<BufferAttribute>} attributes - The attributes to interleave.
 * @return {Array<InterleavedBufferAttribute>} An array of interleaved attributes. If interleave does not succeed, the method returns `null`.
 */
```

**Parameters:**

- **`attributes`** `BufferAttribute[]`

**Returns:** `InterleavedBufferAttribute[]`

**Calls:**

- `console.error`
- `res.push`
- `complex_call_13531`
- `complex_call_13555`

**Internal Comments:**
```
// Interleaves the provided attributes into an InterleavedBuffer and returns (x2)
// a set of InterleavedBufferAttributes for each attribute (x2)
// calculate the length and type of the interleavedBuffer
// Create the set of buffer attributes (x2)
// Move the data for each attribute into the new interleavedBuffer
// at the appropriate offset
```

<details><summary>Code</summary>

```typescript
function interleaveAttributes( attributes ) {

	// Interleaves the provided attributes into an InterleavedBuffer and returns
	// a set of InterleavedBufferAttributes for each attribute
	let TypedArray;
	let arrayLength = 0;
	let stride = 0;

	// calculate the length and type of the interleavedBuffer
	for ( let i = 0, l = attributes.length; i < l; ++ i ) {

		const attribute = attributes[ i ];

		if ( TypedArray === undefined ) TypedArray = attribute.array.constructor;
		if ( TypedArray !== attribute.array.constructor ) {

			console.error( 'AttributeBuffers of different types cannot be interleaved' );
			return null;

		}

		arrayLength += attribute.array.length;
		stride += attribute.itemSize;

	}

	// Create the set of buffer attributes
	const interleavedBuffer = new InterleavedBuffer( new TypedArray( arrayLength ), stride );
	let offset = 0;
	const res = [];
	const getters = [ 'getX', 'getY', 'getZ', 'getW' ];
	const setters = [ 'setX', 'setY', 'setZ', 'setW' ];

	for ( let j = 0, l = attributes.length; j < l; j ++ ) {

		const attribute = attributes[ j ];
		const itemSize = attribute.itemSize;
		const count = attribute.count;
		const iba = new InterleavedBufferAttribute( interleavedBuffer, itemSize, offset, attribute.normalized );
		res.push( iba );

		offset += itemSize;

		// Move the data for each attribute into the new interleavedBuffer
		// at the appropriate offset
		for ( let c = 0; c < count; c ++ ) {

			for ( let k = 0; k < itemSize; k ++ ) {

				iba[ setters[ k ] ]( c, attribute[ getters[ k ] ]( c ) );

			}

		}

	}

	return res;

}
```
</details>

### `deinterleaveAttribute(attribute: InterleavedBufferAttribute): BufferAttribute`

**JSDoc:**
```typescript
/**
 * Returns a new, non-interleaved version of the given attribute.
 *
 * @param {InterleavedBufferAttribute} attribute - The interleaved attribute.
 * @return {BufferAttribute} The non-interleaved attribute.
 */
```

**Parameters:**

- **`attribute`** `InterleavedBufferAttribute`

**Returns:** `BufferAttribute`

**Calls:**

- `newAttribute.setX`
- `attribute.getX`
- `newAttribute.setY`
- `attribute.getY`
- `newAttribute.setZ`
- `attribute.getZ`
- `newAttribute.setW`
- `attribute.getW`

<details><summary>Code</summary>

```typescript
function deinterleaveAttribute( attribute ) {

	const cons = attribute.data.array.constructor;
	const count = attribute.count;
	const itemSize = attribute.itemSize;
	const normalized = attribute.normalized;

	const array = new cons( count * itemSize );
	let newAttribute;
	if ( attribute.isInstancedInterleavedBufferAttribute ) {

		newAttribute = new InstancedBufferAttribute( array, itemSize, normalized, attribute.meshPerAttribute );

	} else {

		newAttribute = new BufferAttribute( array, itemSize, normalized );

	}

	for ( let i = 0; i < count; i ++ ) {

		newAttribute.setX( i, attribute.getX( i ) );

		if ( itemSize >= 2 ) {

			newAttribute.setY( i, attribute.getY( i ) );

		}

		if ( itemSize >= 3 ) {

			newAttribute.setZ( i, attribute.getZ( i ) );

		}

		if ( itemSize >= 4 ) {

			newAttribute.setW( i, attribute.getW( i ) );

		}

	}

	return newAttribute;

}
```
</details>

### `deinterleaveGeometry(geometry: BufferGeometry): void`

**JSDoc:**
```typescript
/**
 * Deinterleaves all attributes on the given geometry.
 *
 * @param {BufferGeometry} geometry - The geometry to deinterleave.
 */
```

**Parameters:**

- **`geometry`** `BufferGeometry`

**Returns:** `void`

**Calls:**

- `attrMap.has`
- `attrMap.set`
- `deinterleaveAttribute`
- `attrMap.get`

<details><summary>Code</summary>

```typescript
function deinterleaveGeometry( geometry ) {

	const attributes = geometry.attributes;
	const morphTargets = geometry.morphTargets;
	const attrMap = new Map();

	for ( const key in attributes ) {

		const attr = attributes[ key ];
		if ( attr.isInterleavedBufferAttribute ) {

			if ( ! attrMap.has( attr ) ) {

				attrMap.set( attr, deinterleaveAttribute( attr ) );

			}

			attributes[ key ] = attrMap.get( attr );

		}

	}

	for ( const key in morphTargets ) {

		const attr = morphTargets[ key ];
		if ( attr.isInterleavedBufferAttribute ) {

			if ( ! attrMap.has( attr ) ) {

				attrMap.set( attr, deinterleaveAttribute( attr ) );

			}

			morphTargets[ key ] = attrMap.get( attr );

		}

	}

}
```
</details>

### `estimateBytesUsed(geometry: BufferGeometry): number`

**JSDoc:**
```typescript
/**
 * Returns the amount of bytes used by all attributes to represent the geometry.
 *
 * @param {BufferGeometry} geometry - The geometry.
 * @return {number} The estimate bytes used.
 */
```

**Parameters:**

- **`geometry`** `BufferGeometry`

**Returns:** `number`

**Calls:**

- `geometry.getAttribute`
- `geometry.getIndex`

**Internal Comments:**
```
// Return the estimated memory used by this geometry in bytes (x2)
// Calculate using itemSize, count, and BYTES_PER_ELEMENT to account (x2)
// for InterleavedBufferAttributes. (x2)
```

<details><summary>Code</summary>

```typescript
function estimateBytesUsed( geometry ) {

	// Return the estimated memory used by this geometry in bytes
	// Calculate using itemSize, count, and BYTES_PER_ELEMENT to account
	// for InterleavedBufferAttributes.
	let mem = 0;
	for ( const name in geometry.attributes ) {

		const attr = geometry.getAttribute( name );
		mem += attr.count * attr.itemSize * attr.array.BYTES_PER_ELEMENT;

	}

	const indices = geometry.getIndex();
	mem += indices ? indices.count * indices.itemSize * indices.array.BYTES_PER_ELEMENT : 0;
	return mem;

}
```
</details>

### `mergeVertices(geometry: BufferGeometry, tolerance: number): BufferGeometry`

**JSDoc:**
```typescript
/**
 * Returns a new geometry with vertices for which all similar vertex attributes (within tolerance) are merged.
 *
 * @param {BufferGeometry} geometry - The geometry to merge vertices for.
 * @param {number} [tolerance=1e-4] - The tolerance value.
 * @return {BufferGeometry} - The new geometry with merged vertices.
 */
```

**Parameters:**

- **`geometry`** `BufferGeometry`
- **`tolerance`** `number`

**Returns:** `BufferGeometry`

**Calls:**

- `Math.max`
- `geometry.getIndex`
- `geometry.getAttribute`
- `Object.keys`
- `morphAttributes.forEach`
- `Math.log10`
- `Math.pow`
- `indices.getX`
- `complex_call_18956`
- `newIndices.push`
- `complex_call_19759`
- `complex_call_19794`
- `complex_call_19939`
- `complex_call_19985`
- `geometry.clone`
- `result.setAttribute`
- `tmpAttribute.array.slice`
- `tmpMorphAttribute.array.slice`
- `result.setIndex`

**Internal Comments:**
```
// Generate an index buffer if the geometry doesn't have one, or optimize it (x2)
// if it's already available. (x2)
// next value for triangle indices (x2)
// attributes and new attribute arrays (x2)
// Initialize the arrays, allocating space conservatively. Extra
// space will be trimmed in the last step.
// convert the error tolerance to an amount of decimal places to truncate to (x2)
// Generate a hash for the vertex attributes at the current index 'i' (x2)
// double tilde truncates the decimal value (x3)
// Add another reference to the vertex if it's already
// used by another index
// copy data to the new index in the temporary attributes
// generate result BufferGeometry (x2)
// indices (x4)
```

<details><summary>Code</summary>

```typescript
function mergeVertices( geometry, tolerance = 1e-4 ) {

	tolerance = Math.max( tolerance, Number.EPSILON );

	// Generate an index buffer if the geometry doesn't have one, or optimize it
	// if it's already available.
	const hashToIndex = {};
	const indices = geometry.getIndex();
	const positions = geometry.getAttribute( 'position' );
	const vertexCount = indices ? indices.count : positions.count;

	// next value for triangle indices
	let nextIndex = 0;

	// attributes and new attribute arrays
	const attributeNames = Object.keys( geometry.attributes );
	const tmpAttributes = {};
	const tmpMorphAttributes = {};
	const newIndices = [];
	const getters = [ 'getX', 'getY', 'getZ', 'getW' ];
	const setters = [ 'setX', 'setY', 'setZ', 'setW' ];

	// Initialize the arrays, allocating space conservatively. Extra
	// space will be trimmed in the last step.
	for ( let i = 0, l = attributeNames.length; i < l; i ++ ) {

		const name = attributeNames[ i ];
		const attr = geometry.attributes[ name ];

		tmpAttributes[ name ] = new attr.constructor(
			new attr.array.constructor( attr.count * attr.itemSize ),
			attr.itemSize,
			attr.normalized
		);

		const morphAttributes = geometry.morphAttributes[ name ];
		if ( morphAttributes ) {

			if ( ! tmpMorphAttributes[ name ] ) tmpMorphAttributes[ name ] = [];
			morphAttributes.forEach( ( morphAttr, i ) => {

				const array = new morphAttr.array.constructor( morphAttr.count * morphAttr.itemSize );
				tmpMorphAttributes[ name ][ i ] = new morphAttr.constructor( array, morphAttr.itemSize, morphAttr.normalized );

			} );

		}

	}

	// convert the error tolerance to an amount of decimal places to truncate to
	const halfTolerance = tolerance * 0.5;
	const exponent = Math.log10( 1 / tolerance );
	const hashMultiplier = Math.pow( 10, exponent );
	const hashAdditive = halfTolerance * hashMultiplier;
	for ( let i = 0; i < vertexCount; i ++ ) {

		const index = indices ? indices.getX( i ) : i;

		// Generate a hash for the vertex attributes at the current index 'i'
		let hash = '';
		for ( let j = 0, l = attributeNames.length; j < l; j ++ ) {

			const name = attributeNames[ j ];
			const attribute = geometry.getAttribute( name );
			const itemSize = attribute.itemSize;

			for ( let k = 0; k < itemSize; k ++ ) {

				// double tilde truncates the decimal value
				hash += `${ ~ ~ ( attribute[ getters[ k ] ]( index ) * hashMultiplier + hashAdditive ) },`;

			}

		}

		// Add another reference to the vertex if it's already
		// used by another index
		if ( hash in hashToIndex ) {

			newIndices.push( hashToIndex[ hash ] );

		} else {

			// copy data to the new index in the temporary attributes
			for ( let j = 0, l = attributeNames.length; j < l; j ++ ) {

				const name = attributeNames[ j ];
				const attribute = geometry.getAttribute( name );
				const morphAttributes = geometry.morphAttributes[ name ];
				const itemSize = attribute.itemSize;
				const newArray = tmpAttributes[ name ];
				const newMorphArrays = tmpMorphAttributes[ name ];

				for ( let k = 0; k < itemSize; k ++ ) {

					const getterFunc = getters[ k ];
					const setterFunc = setters[ k ];
					newArray[ setterFunc ]( nextIndex, attribute[ getterFunc ]( index ) );

					if ( morphAttributes ) {

						for ( let m = 0, ml = morphAttributes.length; m < ml; m ++ ) {

							newMorphArrays[ m ][ setterFunc ]( nextIndex, morphAttributes[ m ][ getterFunc ]( index ) );

						}

					}

				}

			}

			hashToIndex[ hash ] = nextIndex;
			newIndices.push( nextIndex );
			nextIndex ++;

		}

	}

	// generate result BufferGeometry
	const result = geometry.clone();
	for ( const name in geometry.attributes ) {

		const tmpAttribute = tmpAttributes[ name ];

		result.setAttribute( name, new tmpAttribute.constructor(
			tmpAttribute.array.slice( 0, nextIndex * tmpAttribute.itemSize ),
			tmpAttribute.itemSize,
			tmpAttribute.normalized,
		) );

		if ( ! ( name in tmpMorphAttributes ) ) continue;

		for ( let j = 0; j < tmpMorphAttributes[ name ].length; j ++ ) {

			const tmpMorphAttribute = tmpMorphAttributes[ name ][ j ];

			result.morphAttributes[ name ][ j ] = new tmpMorphAttribute.constructor(
				tmpMorphAttribute.array.slice( 0, nextIndex * tmpMorphAttribute.itemSize ),
				tmpMorphAttribute.itemSize,
				tmpMorphAttribute.normalized,
			);

		}

	}

	// indices

	result.setIndex( newIndices );

	return result;

}
```
</details>

### `toTrianglesDrawMode(geometry: BufferGeometry, drawMode: number): BufferGeometry`

**JSDoc:**
```typescript
/**
 * Returns a new indexed geometry based on `TrianglesDrawMode` draw mode.
 * This mode corresponds to the `gl.TRIANGLES` primitive in WebGL.
 *
 * @param {BufferGeometry} geometry - The geometry to convert.
 * @param {number} drawMode - The current draw mode.
 * @return {BufferGeometry} The new geometry using `TrianglesDrawMode`.
 */
```

**Parameters:**

- **`geometry`** `BufferGeometry`
- **`drawMode`** `number`

**Returns:** `BufferGeometry`

**Calls:**

- `console.warn`
- `geometry.getIndex`
- `geometry.getAttribute`
- `indices.push`
- `geometry.setIndex`
- `console.error`
- `newIndices.push`
- `index.getX`
- `geometry.clone`
- `newGeometry.setIndex`
- `newGeometry.clearGroups`

**Internal Comments:**
```
// generate index if not present
// (x2)
// gl.TRIANGLE_FAN
// gl.TRIANGLE_STRIP
// build final geometry (x2)
```

<details><summary>Code</summary>

```typescript
function toTrianglesDrawMode( geometry, drawMode ) {

	if ( drawMode === TrianglesDrawMode ) {

		console.warn( 'THREE.BufferGeometryUtils.toTrianglesDrawMode(): Geometry already defined as triangles.' );
		return geometry;

	}

	if ( drawMode === TriangleFanDrawMode || drawMode === TriangleStripDrawMode ) {

		let index = geometry.getIndex();

		// generate index if not present

		if ( index === null ) {

			const indices = [];

			const position = geometry.getAttribute( 'position' );

			if ( position !== undefined ) {

				for ( let i = 0; i < position.count; i ++ ) {

					indices.push( i );

				}

				geometry.setIndex( indices );
				index = geometry.getIndex();

			} else {

				console.error( 'THREE.BufferGeometryUtils.toTrianglesDrawMode(): Undefined position attribute. Processing not possible.' );
				return geometry;

			}

		}

		//

		const numberOfTriangles = index.count - 2;
		const newIndices = [];

		if ( drawMode === TriangleFanDrawMode ) {

			// gl.TRIANGLE_FAN

			for ( let i = 1; i <= numberOfTriangles; i ++ ) {

				newIndices.push( index.getX( 0 ) );
				newIndices.push( index.getX( i ) );
				newIndices.push( index.getX( i + 1 ) );

			}

		} else {

			// gl.TRIANGLE_STRIP

			for ( let i = 0; i < numberOfTriangles; i ++ ) {

				if ( i % 2 === 0 ) {

					newIndices.push( index.getX( i ) );
					newIndices.push( index.getX( i + 1 ) );
					newIndices.push( index.getX( i + 2 ) );

				} else {

					newIndices.push( index.getX( i + 2 ) );
					newIndices.push( index.getX( i + 1 ) );
					newIndices.push( index.getX( i ) );

				}

			}

		}

		if ( ( newIndices.length / 3 ) !== numberOfTriangles ) {

			console.error( 'THREE.BufferGeometryUtils.toTrianglesDrawMode(): Unable to generate correct amount of triangles.' );

		}

		// build final geometry

		const newGeometry = geometry.clone();
		newGeometry.setIndex( newIndices );
		newGeometry.clearGroups();

		return newGeometry;

	} else {

		console.error( 'THREE.BufferGeometryUtils.toTrianglesDrawMode(): Unknown draw mode:', drawMode );
		return geometry;

	}

}
```
</details>

### `computeMorphedAttributes(object: any): any`

**JSDoc:**
```typescript
/**
 * Calculates the morphed attributes of a morphed/skinned BufferGeometry.
 *
 * Helpful for Raytracing or Decals (i.e. a `DecalGeometry` applied to a morphed Object with a `BufferGeometry`
 * will use the original `BufferGeometry`, not the morphed/skinned one, generating an incorrect result.
 * Using this function to create a shadow `Object3`D the `DecalGeometry` can be correctly generated).
 *
 * @param {Mesh|Line|Points} object - The 3D object to compute morph attributes for.
 * @return {Object} An object with original position/normal attributes and morphed ones.
 */
```

**Parameters:**

- **`object`** `any`

**Returns:** `any`

**Calls:**

- `_vA.fromBufferAttribute`
- `_vB.fromBufferAttribute`
- `_vC.fromBufferAttribute`
- `_morphA.set`
- `_morphB.set`
- `_morphC.set`
- `_tempA.fromBufferAttribute`
- `_tempB.fromBufferAttribute`
- `_tempC.fromBufferAttribute`
- `_morphA.addScaledVector`
- `_morphB.addScaledVector`
- `_morphC.addScaledVector`
- `_tempA.sub`
- `_tempB.sub`
- `_tempC.sub`
- `_vA.add`
- `_vB.add`
- `_vC.add`
- `object.applyBoneTransform`
- `Array.isArray`
- `Math.max`
- `Math.min`
- `index.getX`
- `_calculateMorphedAttributeData`

**Internal Comments:**
```
// indexed buffer geometry
// non-indexed buffer geometry
```

<details><summary>Code</summary>

```typescript
function computeMorphedAttributes( object ) {

	const _vA = new Vector3();
	const _vB = new Vector3();
	const _vC = new Vector3();

	const _tempA = new Vector3();
	const _tempB = new Vector3();
	const _tempC = new Vector3();

	const _morphA = new Vector3();
	const _morphB = new Vector3();
	const _morphC = new Vector3();

	function _calculateMorphedAttributeData(
		object,
		attribute,
		morphAttribute,
		morphTargetsRelative,
		a,
		b,
		c,
		modifiedAttributeArray
	) {

		_vA.fromBufferAttribute( attribute, a );
		_vB.fromBufferAttribute( attribute, b );
		_vC.fromBufferAttribute( attribute, c );

		const morphInfluences = object.morphTargetInfluences;

		if ( morphAttribute && morphInfluences ) {

			_morphA.set( 0, 0, 0 );
			_morphB.set( 0, 0, 0 );
			_morphC.set( 0, 0, 0 );

			for ( let i = 0, il = morphAttribute.length; i < il; i ++ ) {

				const influence = morphInfluences[ i ];
				const morph = morphAttribute[ i ];

				if ( influence === 0 ) continue;

				_tempA.fromBufferAttribute( morph, a );
				_tempB.fromBufferAttribute( morph, b );
				_tempC.fromBufferAttribute( morph, c );

				if ( morphTargetsRelative ) {

					_morphA.addScaledVector( _tempA, influence );
					_morphB.addScaledVector( _tempB, influence );
					_morphC.addScaledVector( _tempC, influence );

				} else {

					_morphA.addScaledVector( _tempA.sub( _vA ), influence );
					_morphB.addScaledVector( _tempB.sub( _vB ), influence );
					_morphC.addScaledVector( _tempC.sub( _vC ), influence );

				}

			}

			_vA.add( _morphA );
			_vB.add( _morphB );
			_vC.add( _morphC );

		}

		if ( object.isSkinnedMesh ) {

			object.applyBoneTransform( a, _vA );
			object.applyBoneTransform( b, _vB );
			object.applyBoneTransform( c, _vC );

		}

		modifiedAttributeArray[ a * 3 + 0 ] = _vA.x;
		modifiedAttributeArray[ a * 3 + 1 ] = _vA.y;
		modifiedAttributeArray[ a * 3 + 2 ] = _vA.z;
		modifiedAttributeArray[ b * 3 + 0 ] = _vB.x;
		modifiedAttributeArray[ b * 3 + 1 ] = _vB.y;
		modifiedAttributeArray[ b * 3 + 2 ] = _vB.z;
		modifiedAttributeArray[ c * 3 + 0 ] = _vC.x;
		modifiedAttributeArray[ c * 3 + 1 ] = _vC.y;
		modifiedAttributeArray[ c * 3 + 2 ] = _vC.z;

	}

	const geometry = object.geometry;
	const material = object.material;

	let a, b, c;
	const index = geometry.index;
	const positionAttribute = geometry.attributes.position;
	const morphPosition = geometry.morphAttributes.position;
	const morphTargetsRelative = geometry.morphTargetsRelative;
	const normalAttribute = geometry.attributes.normal;
	const morphNormal = geometry.morphAttributes.position;

	const groups = geometry.groups;
	const drawRange = geometry.drawRange;
	let i, j, il, jl;
	let group;
	let start, end;

	const modifiedPosition = new Float32Array( positionAttribute.count * positionAttribute.itemSize );
	const modifiedNormal = new Float32Array( normalAttribute.count * normalAttribute.itemSize );

	if ( index !== null ) {

		// indexed buffer geometry

		if ( Array.isArray( material ) ) {

			for ( i = 0, il = groups.length; i < il; i ++ ) {

				group = groups[ i ];

				start = Math.max( group.start, drawRange.start );
				end = Math.min( ( group.start + group.count ), ( drawRange.start + drawRange.count ) );

				for ( j = start, jl = end; j < jl; j += 3 ) {

					a = index.getX( j );
					b = index.getX( j + 1 );
					c = index.getX( j + 2 );

					_calculateMorphedAttributeData(
						object,
						positionAttribute,
						morphPosition,
						morphTargetsRelative,
						a, b, c,
						modifiedPosition
					);

					_calculateMorphedAttributeData(
						object,
						normalAttribute,
						morphNormal,
						morphTargetsRelative,
						a, b, c,
						modifiedNormal
					);

				}

			}

		} else {

			start = Math.max( 0, drawRange.start );
			end = Math.min( index.count, ( drawRange.start + drawRange.count ) );

			for ( i = start, il = end; i < il; i += 3 ) {

				a = index.getX( i );
				b = index.getX( i + 1 );
				c = index.getX( i + 2 );

				_calculateMorphedAttributeData(
					object,
					positionAttribute,
					morphPosition,
					morphTargetsRelative,
					a, b, c,
					modifiedPosition
				);

				_calculateMorphedAttributeData(
					object,
					normalAttribute,
					morphNormal,
					morphTargetsRelative,
					a, b, c,
					modifiedNormal
				);

			}

		}

	} else {

		// non-indexed buffer geometry

		if ( Array.isArray( material ) ) {

			for ( i = 0, il = groups.length; i < il; i ++ ) {

				group = groups[ i ];

				start = Math.max( group.start, drawRange.start );
				end = Math.min( ( group.start + group.count ), ( drawRange.start + drawRange.count ) );

				for ( j = start, jl = end; j < jl; j += 3 ) {

					a = j;
					b = j + 1;
					c = j + 2;

					_calculateMorphedAttributeData(
						object,
						positionAttribute,
						morphPosition,
						morphTargetsRelative,
						a, b, c,
						modifiedPosition
					);

					_calculateMorphedAttributeData(
						object,
						normalAttribute,
						morphNormal,
						morphTargetsRelative,
						a, b, c,
						modifiedNormal
					);

				}

			}

		} else {

			start = Math.max( 0, drawRange.start );
			end = Math.min( positionAttribute.count, ( drawRange.start + drawRange.count ) );

			for ( i = start, il = end; i < il; i += 3 ) {

				a = i;
				b = i + 1;
				c = i + 2;

				_calculateMorphedAttributeData(
					object,
					positionAttribute,
					morphPosition,
					morphTargetsRelative,
					a, b, c,
					modifiedPosition
				);

				_calculateMorphedAttributeData(
					object,
					normalAttribute,
					morphNormal,
					morphTargetsRelative,
					a, b, c,
					modifiedNormal
				);

			}

		}

	}

	const morphedPositionAttribute = new Float32BufferAttribute( modifiedPosition, 3 );
	const morphedNormalAttribute = new Float32BufferAttribute( modifiedNormal, 3 );

	return {

		positionAttribute: positionAttribute,
		normalAttribute: normalAttribute,
		morphedPositionAttribute: morphedPositionAttribute,
		morphedNormalAttribute: morphedNormalAttribute

	};

}
```
</details>

### `_calculateMorphedAttributeData(object: any, attribute: any, morphAttribute: any, morphTargetsRelative: any, a: any, b: any, c: any, modifiedAttributeArray: any): void`

**Parameters:**

- **`object`** `any`
- **`attribute`** `any`
- **`morphAttribute`** `any`
- **`morphTargetsRelative`** `any`
- **`a`** `any`
- **`b`** `any`
- **`c`** `any`
- **`modifiedAttributeArray`** `any`

**Returns:** `void`

**Calls:**

- `_vA.fromBufferAttribute`
- `_vB.fromBufferAttribute`
- `_vC.fromBufferAttribute`
- `_morphA.set`
- `_morphB.set`
- `_morphC.set`
- `_tempA.fromBufferAttribute`
- `_tempB.fromBufferAttribute`
- `_tempC.fromBufferAttribute`
- `_morphA.addScaledVector`
- `_morphB.addScaledVector`
- `_morphC.addScaledVector`
- `_tempA.sub`
- `_tempB.sub`
- `_tempC.sub`
- `_vA.add`
- `_vB.add`
- `_vC.add`
- `object.applyBoneTransform`

<details><summary>Code</summary>

```typescript
function _calculateMorphedAttributeData(
		object,
		attribute,
		morphAttribute,
		morphTargetsRelative,
		a,
		b,
		c,
		modifiedAttributeArray
	) {

		_vA.fromBufferAttribute( attribute, a );
		_vB.fromBufferAttribute( attribute, b );
		_vC.fromBufferAttribute( attribute, c );

		const morphInfluences = object.morphTargetInfluences;

		if ( morphAttribute && morphInfluences ) {

			_morphA.set( 0, 0, 0 );
			_morphB.set( 0, 0, 0 );
			_morphC.set( 0, 0, 0 );

			for ( let i = 0, il = morphAttribute.length; i < il; i ++ ) {

				const influence = morphInfluences[ i ];
				const morph = morphAttribute[ i ];

				if ( influence === 0 ) continue;

				_tempA.fromBufferAttribute( morph, a );
				_tempB.fromBufferAttribute( morph, b );
				_tempC.fromBufferAttribute( morph, c );

				if ( morphTargetsRelative ) {

					_morphA.addScaledVector( _tempA, influence );
					_morphB.addScaledVector( _tempB, influence );
					_morphC.addScaledVector( _tempC, influence );

				} else {

					_morphA.addScaledVector( _tempA.sub( _vA ), influence );
					_morphB.addScaledVector( _tempB.sub( _vB ), influence );
					_morphC.addScaledVector( _tempC.sub( _vC ), influence );

				}

			}

			_vA.add( _morphA );
			_vB.add( _morphB );
			_vC.add( _morphC );

		}

		if ( object.isSkinnedMesh ) {

			object.applyBoneTransform( a, _vA );
			object.applyBoneTransform( b, _vB );
			object.applyBoneTransform( c, _vC );

		}

		modifiedAttributeArray[ a * 3 + 0 ] = _vA.x;
		modifiedAttributeArray[ a * 3 + 1 ] = _vA.y;
		modifiedAttributeArray[ a * 3 + 2 ] = _vA.z;
		modifiedAttributeArray[ b * 3 + 0 ] = _vB.x;
		modifiedAttributeArray[ b * 3 + 1 ] = _vB.y;
		modifiedAttributeArray[ b * 3 + 2 ] = _vB.z;
		modifiedAttributeArray[ c * 3 + 0 ] = _vC.x;
		modifiedAttributeArray[ c * 3 + 1 ] = _vC.y;
		modifiedAttributeArray[ c * 3 + 2 ] = _vC.z;

	}
```
</details>

### `mergeGroups(geometry: BufferGeometry): BufferGeometry`

**JSDoc:**
```typescript
/**
 * Merges the {@link BufferGeometry#groups} for the given geometry.
 *
 * @param {BufferGeometry} geometry - The geometry to modify.
 * @return {BufferGeometry} - The updated geometry
 */
```

**Parameters:**

- **`geometry`** `BufferGeometry`

**Returns:** `BufferGeometry`

**Calls:**

- `console.warn`
- `groups.sort`
- `geometry.getIndex`
- `geometry.getAttribute`
- `indices.push`
- `geometry.setIndex`
- `newIndices.push`
- `index.getX`
- `geometry.dispose`
- `geometry.groups.push`

**Internal Comments:**
```
// sort groups by material index (x3)
// create index for non-indexed geometries
// sort index (x2)
// update groups indices (x2)
// merge groups (x2)
```

<details><summary>Code</summary>

```typescript
function mergeGroups( geometry ) {

	if ( geometry.groups.length === 0 ) {

		console.warn( 'THREE.BufferGeometryUtils.mergeGroups(): No groups are defined. Nothing to merge.' );
		return geometry;

	}

	let groups = geometry.groups;

	// sort groups by material index

	groups = groups.sort( ( a, b ) => {

		if ( a.materialIndex !== b.materialIndex ) return a.materialIndex - b.materialIndex;

		return a.start - b.start;

	} );

	// create index for non-indexed geometries

	if ( geometry.getIndex() === null ) {

		const positionAttribute = geometry.getAttribute( 'position' );
		const indices = [];

		for ( let i = 0; i < positionAttribute.count; i += 3 ) {

			indices.push( i, i + 1, i + 2 );

		}

		geometry.setIndex( indices );

	}

	// sort index

	const index = geometry.getIndex();

	const newIndices = [];

	for ( let i = 0; i < groups.length; i ++ ) {

		const group = groups[ i ];

		const groupStart = group.start;
		const groupLength = groupStart + group.count;

		for ( let j = groupStart; j < groupLength; j ++ ) {

			newIndices.push( index.getX( j ) );

		}

	}

	geometry.dispose(); // Required to force buffer recreation
	geometry.setIndex( newIndices );

	// update groups indices

	let start = 0;

	for ( let i = 0; i < groups.length; i ++ ) {

		const group = groups[ i ];

		group.start = start;
		start += group.count;

	}

	// merge groups

	let currentGroup = groups[ 0 ];

	geometry.groups = [ currentGroup ];

	for ( let i = 1; i < groups.length; i ++ ) {

		const group = groups[ i ];

		if ( currentGroup.materialIndex === group.materialIndex ) {

			currentGroup.count += group.count;

		} else {

			currentGroup = group;
			geometry.groups.push( currentGroup );

		}

	}

	return geometry;

}
```
</details>

### `toCreasedNormals(geometry: BufferGeometry, creaseAngle: number): BufferGeometry`

**JSDoc:**
```typescript
/**
 * Modifies the supplied geometry if it is non-indexed, otherwise creates a new,
 * non-indexed geometry. Returns the geometry with smooth normals everywhere except
 * faces that meet at an angle greater than the crease angle.
 *
 * @param {BufferGeometry} geometry - The geometry to modify.
 * @param {number} [creaseAngle=Math.PI/3] - The crease angle in radians.
 * @return {BufferGeometry} - The updated geometry
 */
```

**Parameters:**

- **`geometry`** `BufferGeometry`
- **`creaseAngle`** `number`

**Returns:** `BufferGeometry`

**Calls:**

- `Math.cos`
- `geometry.toNonIndexed`
- `verts[ 0 ].fromBufferAttribute`
- `verts[ 1 ].fromBufferAttribute`
- `verts[ 2 ].fromBufferAttribute`
- `tempVec1.subVectors`
- `tempVec2.subVectors`
- `new Vector3().crossVectors( tempVec1, tempVec2 ).normalize`
- `hashVertex`
- `vertexMap[ hash ].push`
- `tempNorm.crossVectors( tempVec1, tempVec2 ).normalize`
- `tempNorm2.set`
- `tempNorm.dot`
- `tempNorm2.add`
- `tempNorm2.normalize`
- `normAttr.setXYZ`
- `resultGeometry.setAttribute`

**Internal Comments:**
```
// reusable vectors (x2)
// hashes a vector
// BufferGeometry.toNonIndexed() warns if the geometry is non-indexed (x2)
// and returns the original geometry (x2)
// find all the normals shared by commonly located vertices
// add the normal to the map for all vertices (x2)
// average normals from all vertices that share a common location if they are within the (x2)
// provided crease threshold (x2)
// get the face normal for this vertex (x2)
// average all normals that meet the threshold and set the normal value
```

<details><summary>Code</summary>

```typescript
function toCreasedNormals( geometry, creaseAngle = Math.PI / 3 /* 60 degrees */ ) {

	const creaseDot = Math.cos( creaseAngle );
	const hashMultiplier = ( 1 + 1e-10 ) * 1e2;

	// reusable vectors
	const verts = [ new Vector3(), new Vector3(), new Vector3() ];
	const tempVec1 = new Vector3();
	const tempVec2 = new Vector3();
	const tempNorm = new Vector3();
	const tempNorm2 = new Vector3();

	// hashes a vector
	function hashVertex( v ) {

		const x = ~ ~ ( v.x * hashMultiplier );
		const y = ~ ~ ( v.y * hashMultiplier );
		const z = ~ ~ ( v.z * hashMultiplier );
		return `${x},${y},${z}`;

	}

	// BufferGeometry.toNonIndexed() warns if the geometry is non-indexed
	// and returns the original geometry
	const resultGeometry = geometry.index ? geometry.toNonIndexed() : geometry;
	const posAttr = resultGeometry.attributes.position;
	const vertexMap = {};

	// find all the normals shared by commonly located vertices
	for ( let i = 0, l = posAttr.count / 3; i < l; i ++ ) {

		const i3 = 3 * i;
		const a = verts[ 0 ].fromBufferAttribute( posAttr, i3 + 0 );
		const b = verts[ 1 ].fromBufferAttribute( posAttr, i3 + 1 );
		const c = verts[ 2 ].fromBufferAttribute( posAttr, i3 + 2 );

		tempVec1.subVectors( c, b );
		tempVec2.subVectors( a, b );

		// add the normal to the map for all vertices
		const normal = new Vector3().crossVectors( tempVec1, tempVec2 ).normalize();
		for ( let n = 0; n < 3; n ++ ) {

			const vert = verts[ n ];
			const hash = hashVertex( vert );
			if ( ! ( hash in vertexMap ) ) {

				vertexMap[ hash ] = [];

			}

			vertexMap[ hash ].push( normal );

		}

	}

	// average normals from all vertices that share a common location if they are within the
	// provided crease threshold
	const normalArray = new Float32Array( posAttr.count * 3 );
	const normAttr = new BufferAttribute( normalArray, 3, false );
	for ( let i = 0, l = posAttr.count / 3; i < l; i ++ ) {

		// get the face normal for this vertex
		const i3 = 3 * i;
		const a = verts[ 0 ].fromBufferAttribute( posAttr, i3 + 0 );
		const b = verts[ 1 ].fromBufferAttribute( posAttr, i3 + 1 );
		const c = verts[ 2 ].fromBufferAttribute( posAttr, i3 + 2 );

		tempVec1.subVectors( c, b );
		tempVec2.subVectors( a, b );

		tempNorm.crossVectors( tempVec1, tempVec2 ).normalize();

		// average all normals that meet the threshold and set the normal value
		for ( let n = 0; n < 3; n ++ ) {

			const vert = verts[ n ];
			const hash = hashVertex( vert );
			const otherNormals = vertexMap[ hash ];
			tempNorm2.set( 0, 0, 0 );

			for ( let k = 0, lk = otherNormals.length; k < lk; k ++ ) {

				const otherNorm = otherNormals[ k ];
				if ( tempNorm.dot( otherNorm ) > creaseDot ) {

					tempNorm2.add( otherNorm );

				}

			}

			tempNorm2.normalize();
			normAttr.setXYZ( i3 + n, tempNorm2.x, tempNorm2.y, tempNorm2.z );

		}

	}

	resultGeometry.setAttribute( 'normal', normAttr );
	return resultGeometry;

}
```
</details>

### `hashVertex(v: any): string`

**Parameters:**

- **`v`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function hashVertex( v ) {

		const x = ~ ~ ( v.x * hashMultiplier );
		const y = ~ ~ ( v.y * hashMultiplier );
		const z = ~ ~ ( v.z * hashMultiplier );
		return `${x},${y},${z}`;

	}
```
</details>


---