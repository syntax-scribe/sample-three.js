[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LDrawLoader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 50 |
| 🧱 Classes | 5 |
| 📦 Imports | 14 |
| 📊 Variables & Constants | 202 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/loaders/LDrawLoader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferAttribute` | `three` |
| `BufferGeometry` | `three` |
| `Color` | `three` |
| `FileLoader` | `three` |
| `Group` | `three` |
| `LineBasicMaterial` | `three` |
| `LineSegments` | `three` |
| `Loader` | `three` |
| `Matrix4` | `three` |
| `Mesh` | `three` |
| `MeshStandardMaterial` | `three` |
| `SRGBColorSpace` | `three` |
| `Vector3` | `three` |
| `Ray` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `FINISH_TYPE_DEFAULT` | `0` | let/var | `0` | ✗ |
| `FINISH_TYPE_CHROME` | `1` | let/var | `1` | ✗ |
| `FINISH_TYPE_PEARLESCENT` | `2` | let/var | `2` | ✗ |
| `FINISH_TYPE_RUBBER` | `3` | let/var | `3` | ✗ |
| `FINISH_TYPE_MATTE_METALLIC` | `4` | let/var | `4` | ✗ |
| `FINISH_TYPE_METAL` | `5` | let/var | `5` | ✗ |
| `FILE_LOCATION_TRY_PARTS` | `0` | let/var | `0` | ✗ |
| `FILE_LOCATION_TRY_P` | `1` | let/var | `1` | ✗ |
| `FILE_LOCATION_TRY_MODELS` | `2` | let/var | `2` | ✗ |
| `FILE_LOCATION_AS_IS` | `3` | let/var | `3` | ✗ |
| `FILE_LOCATION_TRY_RELATIVE` | `4` | let/var | `4` | ✗ |
| `FILE_LOCATION_TRY_ABSOLUTE` | `5` | let/var | `5` | ✗ |
| `FILE_LOCATION_NOT_FOUND` | `6` | let/var | `6` | ✗ |
| `MAIN_COLOUR_CODE` | `"16"` | let/var | `'16'` | ✗ |
| `MAIN_EDGE_COLOUR_CODE` | `"24"` | let/var | `'24'` | ✗ |
| `COLOR_SPACE_LDRAW` | `any` | let/var | `SRGBColorSpace` | ✗ |
| `_tempVec0` | `any` | let/var | `new Vector3()` | ✗ |
| `_tempVec1` | `any` | let/var | `new Vector3()` | ✗ |
| `face` | `any` | let/var | `faces[ i ]` | ✗ |
| `vertices` | `any` | let/var | `face.vertices` | ✗ |
| `v0` | `any` | let/var | `vertices[ 0 ]` | ✗ |
| `v1` | `any` | let/var | `vertices[ 1 ]` | ✗ |
| `v2` | `any` | let/var | `vertices[ 2 ]` | ✗ |
| `_ray` | `any` | let/var | `new Ray()` | ✗ |
| `hashMultiplier` | `number` | let/var | `( 1 + 1e-10 ) * 1e2` | ✗ |
| `x` | `number` | let/var | `~ ~ ( v.x * hashMultiplier )` | ✗ |
| `y` | `number` | let/var | `~ ~ ( v.y * hashMultiplier )` | ✗ |
| `z` | `number` | let/var | `~ ~ ( v.z * hashMultiplier )` | ✗ |
| `hardEdges` | `Set<any>` | let/var | `new Set()` | ✗ |
| `hardEdgeRays` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `halfEdgeList` | `{}` | let/var | `{}` | ✗ |
| `normals` | `any[]` | let/var | `[]` | ✗ |
| `ls` | `any` | let/var | `lineSegments[ i ]` | ✗ |
| `vertices` | `any` | let/var | `ls.vertices` | ✗ |
| `v0` | `any` | let/var | `vertices[ 0 ]` | ✗ |
| `v1` | `any` | let/var | `vertices[ 1 ]` | ✗ |
| `info` | `{ ray: any; distances: any[]; }` | let/var | `{ ray, distances: [], }` | ✗ |
| `tri` | `any` | let/var | `faces[ i ]` | ✗ |
| `vertices` | `any` | let/var | `tri.vertices` | ✗ |
| `vertCount` | `any` | let/var | `vertices.length` | ✗ |
| `index` | `number` | let/var | `i2` | ✗ |
| `next` | `number` | let/var | `( i2 + 1 ) % vertCount` | ✗ |
| `v0` | `any` | let/var | `vertices[ index ]` | ✗ |
| `v1` | `any` | let/var | `vertices[ next ]` | ✗ |
| `found` | `boolean` | let/var | `false` | ✗ |
| `info` | `{ index: number; tri: any; }` | let/var | `{ index: index, tri: tri }` | ✗ |
| `halfEdge` | `any` | let/var | `null` | ✗ |
| `queue` | `any[]` | let/var | `[ halfEdge ]` | ✗ |
| `tri` | `any` | let/var | `queue.pop().tri` | ✗ |
| `vertices` | `any` | let/var | `tri.vertices` | ✗ |
| `vertNormals` | `any` | let/var | `tri.normals` | ✗ |
| `faceNormal` | `any` | let/var | `tri.faceNormal` | ✗ |
| `vertCount` | `any` | let/var | `vertices.length` | ✗ |
| `index` | `number` | let/var | `i2` | ✗ |
| `next` | `number` | let/var | `( i2 + 1 ) % vertCount` | ✗ |
| `v0` | `any` | let/var | `vertices[ index ]` | ✗ |
| `v1` | `any` | let/var | `vertices[ next ]` | ✗ |
| `otherInfo` | `any` | let/var | `halfEdgeList[ reverseHash ]` | ✗ |
| `otherTri` | `any` | let/var | `otherInfo.tri` | ✗ |
| `otherIndex` | `any` | let/var | `otherInfo.index` | ✗ |
| `otherNormals` | `any` | let/var | `otherTri.normals` | ✗ |
| `otherVertCount` | `any` | let/var | `otherNormals.length` | ✗ |
| `otherFaceNormal` | `any` | let/var | `otherTri.faceNormal` | ✗ |
| `otherNext` | `number` | let/var | `( otherIndex + 1 ) % otherVertCount` | ✗ |
| `sharedNormal1` | `any` | let/var | `vertNormals[ index ] \|\| otherNormals[ otherNext ]` | ✗ |
| `sharedNormal2` | `any` | let/var | `vertNormals[ next ] \|\| otherNormals[ otherIndex ]` | ✗ |
| `pos0` | `number` | let/var | `this.currentCharIndex ++` | ✗ |
| `pos1` | `number` | let/var | `this.currentCharIndex` | ✗ |
| `result` | `{ faces: any; conditionalSegments: an...` | let/var | `{}` | ✗ |
| `triedLowerCase` | `boolean` | let/var | `false` | ✗ |
| `locationState` | `number` | let/var | `FILE_LOCATION_TRY_PARTS` | ✗ |
| `subobjectURL` | `any` | let/var | `fileName` | ✗ |
| `loader` | `any` | let/var | `this.loader` | ✗ |
| `fileLoader` | `any` | let/var | `new FileLoader( loader.manager )` | ✗ |
| `text` | `any` | let/var | `await fileLoader.loadAsync( subobjectURL )` | ✗ |
| `loader` | `any` | let/var | `this.loader` | ✗ |
| `faces` | `any[]` | let/var | `[]` | ✗ |
| `lineSegments` | `any[]` | let/var | `[]` | ✗ |
| `conditionalSegments` | `any[]` | let/var | `[]` | ✗ |
| `subobjects` | `any[]` | let/var | `[]` | ✗ |
| `materials` | `{}` | let/var | `{}` | ✗ |
| `type` | `string` | let/var | `'Model'` | ✗ |
| `category` | `any` | let/var | `null` | ✗ |
| `keywords` | `any` | let/var | `null` | ✗ |
| `author` | `any` | let/var | `null` | ✗ |
| `totalFaces` | `number` | let/var | `0` | ✗ |
| `numLines` | `any` | let/var | `lines.length` | ✗ |
| `parsingEmbeddedFiles` | `boolean` | let/var | `false` | ✗ |
| `currentEmbeddedFileName` | `any` | let/var | `null` | ✗ |
| `currentEmbeddedText` | `any` | let/var | `null` | ✗ |
| `bfcCertified` | `boolean` | let/var | `false` | ✗ |
| `bfcCCW` | `boolean` | let/var | `true` | ✗ |
| `bfcInverted` | `boolean` | let/var | `false` | ✗ |
| `bfcCull` | `boolean` | let/var | `true` | ✗ |
| `startingBuildingStep` | `boolean` | let/var | `false` | ✗ |
| `line` | `any` | let/var | `lines[ lineIndex ]` | ✗ |
| `lp` | `LineParser` | let/var | `new LineParser( line, lineIndex + 1 )` | ✗ |
| `material` | `any` | let/var | `*not shown*` | ✗ |
| `colorCode` | `any` | let/var | `*not shown*` | ✗ |
| `segment` | `any` | let/var | `*not shown*` | ✗ |
| `ccw` | `any` | let/var | `*not shown*` | ✗ |
| `doubleSided` | `any` | let/var | `*not shown*` | ✗ |
| `v0` | `any` | let/var | `*not shown*` | ✗ |
| `v1` | `any` | let/var | `*not shown*` | ✗ |
| `v2` | `any` | let/var | `*not shown*` | ✗ |
| `v3` | `any` | let/var | `*not shown*` | ✗ |
| `c0` | `any` | let/var | `*not shown*` | ✗ |
| `c1` | `any` | let/var | `*not shown*` | ✗ |
| `result` | `any` | let/var | `this._cache[ key ]` | ✗ |
| `isPassthrough` | `boolean` | let/var | `! forEdge && colorCode === MAIN_COLOUR_CODE \|\| forEdge && colorCode === MAI...` | ✗ |
| `loader` | `any` | let/var | `this.loader` | ✗ |
| `parseCache` | `LDrawParsedCache` | let/var | `this.parseCache` | ✗ |
| `faceMaterials` | `Set<any>` | let/var | `new Set()` | ✗ |
| `subobjects` | `any` | let/var | `info.subobjects` | ✗ |
| `promises` | `any[]` | let/var | `[]` | ✗ |
| `subobject` | `any` | let/var | `subobjects[ i ]` | ✗ |
| `group` | `any` | let/var | `new Group()` | ✗ |
| `subobjectInfos` | `any[]` | let/var | `await Promise.all( promises )` | ✗ |
| `subobject` | `any` | let/var | `info.subobjects[ i ]` | ✗ |
| `subobjectInfo` | `any` | let/var | `subobjectInfos[ i ]` | ✗ |
| `subobjectGroup` | `any` | let/var | `subobjectInfo` | ✗ |
| `parentLineSegments` | `any` | let/var | `info.lineSegments` | ✗ |
| `parentConditionalSegments` | `any` | let/var | `info.conditionalSegments` | ✗ |
| `parentFaces` | `any` | let/var | `info.faces` | ✗ |
| `lineSegments` | `any` | let/var | `subobjectInfo.lineSegments` | ✗ |
| `conditionalSegments` | `any` | let/var | `subobjectInfo.conditionalSegments` | ✗ |
| `faces` | `any` | let/var | `subobjectInfo.faces` | ✗ |
| `matrix` | `any` | let/var | `subobject.matrix` | ✗ |
| `inverted` | `any` | let/var | `subobject.inverted` | ✗ |
| `matrixScaleInverted` | `boolean` | let/var | `matrix.determinant() < 0` | ✗ |
| `colorCode` | `any` | let/var | `subobject.colorCode` | ✗ |
| `lineColorCode` | `any` | let/var | `colorCode === MAIN_COLOUR_CODE ? MAIN_EDGE_COLOUR_CODE : colorCode` | ✗ |
| `ls` | `any` | let/var | `lineSegments[ i ]` | ✗ |
| `vertices` | `any` | let/var | `ls.vertices` | ✗ |
| `os` | `any` | let/var | `conditionalSegments[ i ]` | ✗ |
| `vertices` | `any` | let/var | `os.vertices` | ✗ |
| `controlPoints` | `any` | let/var | `os.controlPoints` | ✗ |
| `tri` | `any` | let/var | `faces[ i ]` | ✗ |
| `vertices` | `any` | let/var | `tri.vertices` | ✗ |
| `checkSubSegments` | `boolean` | let/var | `faceMaterials.size > 1` | ✗ |
| `group` | `any` | let/var | `info.group` | ✗ |
| `group` | `any` | let/var | `await this._cache[ key ]` | ✗ |
| `parseCache` | `LDrawParsedCache` | let/var | `this.parseCache` | ✗ |
| `group` | `any` | let/var | `await promise` | ✗ |
| `parseCache` | `LDrawParsedCache` | let/var | `this.parseCache` | ✗ |
| `positions` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( elementSize * totalElements * 3 )` | ✗ |
| `normals` | `Float32Array<ArrayBuffer>` | let/var | `elementSize === 3 ? new Float32Array( elementSize * totalElements * 3 ) : null` | ✗ |
| `materials` | `any[]` | let/var | `[]` | ✗ |
| `quadArray` | `any[]` | let/var | `new Array( 6 )` | ✗ |
| `bufferGeometry` | `any` | let/var | `new BufferGeometry()` | ✗ |
| `prevMaterial` | `any` | let/var | `null` | ✗ |
| `index0` | `number` | let/var | `0` | ✗ |
| `numGroupVerts` | `number` | let/var | `0` | ✗ |
| `offset` | `number` | let/var | `0` | ✗ |
| `elem` | `any` | let/var | `elements[ iElem ]` | ✗ |
| `vertices` | `any` | let/var | `elem.vertices` | ✗ |
| `v` | `any` | let/var | `vertices[ j ]` | ✗ |
| `index` | `number` | let/var | `offset + j * 3` | ✗ |
| `v0` | `any` | let/var | `vertices[ 0 ]` | ✗ |
| `v1` | `any` | let/var | `vertices[ 1 ]` | ✗ |
| `v2` | `any` | let/var | `vertices[ 2 ]` | ✗ |
| `elemNormals` | `any` | let/var | `elem.normals` | ✗ |
| `n` | `any` | let/var | `elem.faceNormal` | ✗ |
| `index` | `number` | let/var | `offset + j * 3` | ✗ |
| `material` | `any` | let/var | `elem.material` | ✗ |
| `object3d` | `any` | let/var | `null` | ✗ |
| `controlArray0` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( elements.length * 3 * 2 )` | ✗ |
| `controlArray1` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( elements.length * 3 * 2 )` | ✗ |
| `directionArray` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( elements.length * 3 * 2 )` | ✗ |
| `os` | `any` | let/var | `elements[ i ]` | ✗ |
| `vertices` | `any` | let/var | `os.vertices` | ✗ |
| `controlPoints` | `any` | let/var | `os.controlPoints` | ✗ |
| `c0` | `any` | let/var | `controlPoints[ 0 ]` | ✗ |
| `c1` | `any` | let/var | `controlPoints[ 1 ]` | ✗ |
| `v0` | `any` | let/var | `vertices[ 0 ]` | ✗ |
| `v1` | `any` | let/var | `vertices[ 1 ]` | ✗ |
| `index` | `number` | let/var | `i * 3 * 2` | ✗ |
| `fileLoader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `text` | `any` | let/var | `await fileLoader.loadAsync( url )` | ✗ |
| `colorLineRegex` | `RegExp` | let/var | `/^0 !COLOUR/` | ✗ |
| `materials` | `any[]` | let/var | `[]` | ✗ |
| `line` | `any` | let/var | `lines[ i ]` | ✗ |
| `fileLoader` | `any` | let/var | `new FileLoader( this.manager )` | ✗ |
| `matLib` | `{}` | let/var | `this.materialLibrary` | ✗ |
| `loader` | `this` | let/var | `this` | ✗ |
| `parentIsPassthrough` | `boolean` | let/var | `parentColorCode === MAIN_COLOUR_CODE` | ✗ |
| `forEdge` | `any` | let/var | `c.isLineSegments \|\| c.isConditionalLine` | ✗ |
| `isPassthrough` | `boolean` | let/var | `! forEdge && colorCode === MAIN_COLOUR_CODE \|\| forEdge && colorCode === MAI...` | ✗ |
| `material` | `any` | let/var | `null` | ✗ |
| `code` | `any` | let/var | `null` | ✗ |
| `fillColor` | `string` | let/var | `'#FF00FF'` | ✗ |
| `edgeColor` | `string` | let/var | `'#FF00FF'` | ✗ |
| `alpha` | `number` | let/var | `1` | ✗ |
| `isTransparent` | `boolean` | let/var | `false` | ✗ |
| `luminance` | `number` | let/var | `0` | ✗ |
| `finishType` | `number` | let/var | `FINISH_TYPE_DEFAULT` | ✗ |
| `edgeMaterial` | `any` | let/var | `null` | ✗ |
| `token` | `any` | let/var | `null` | ✗ |
| `material` | `any` | let/var | `null` | ✗ |
| `conditionalEdgeMaterial` | `any` | let/var | `new this.ConditionalLineMaterial( { fog: true, transparent: isTransparent, de...` | ✗ |
| `lum` | `any` | let/var | `*not shown*` | ✗ |
| `stepNumber` | `number` | let/var | `0` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `processInfoSubobjects` | Promise.all( promises ) | parseCache.ensureDataLoaded( subobject.fileName ).then, this.loadModel( subobject.fileName ).catch, Promise.all |


---

## Functions

### `generateFaceNormals(faces: any): void`

**Parameters:**

- **`faces`** `any`

**Returns:** `void`

**Calls:**

- `_tempVec0.subVectors`
- `_tempVec1.subVectors`
- `new Vector3()
			.crossVectors( _tempVec0, _tempVec1 )
			.normalize`

<details><summary>Code</summary>

```typescript
function generateFaceNormals( faces ) {

	for ( let i = 0, l = faces.length; i < l; i ++ ) {

		const face = faces[ i ];
		const vertices = face.vertices;
		const v0 = vertices[ 0 ];
		const v1 = vertices[ 1 ];
		const v2 = vertices[ 2 ];

		_tempVec0.subVectors( v1, v0 );
		_tempVec1.subVectors( v2, v1 );
		face.faceNormal = new Vector3()
			.crossVectors( _tempVec0, _tempVec1 )
			.normalize();

	}

}
```
</details>

### `smoothNormals(faces: any, lineSegments: any, checkSubSegments: boolean): void`

**Parameters:**

- **`faces`** `any`
- **`lineSegments`** `any`
- **`checkSubSegments`** `boolean`

**Returns:** `void`

**Calls:**

- `hashVertex`
- `targetRay.direction.subVectors( v1, v0 ).normalize`
- `v0.dot`
- `targetRay.origin.copy( v0 ).addScaledVector`
- `hashEdge`
- `hardEdges.add`
- `toNormalizedRay`
- `hashRay`
- `hardEdgeRays.has`
- `hardEdgeRays.set`
- `hardEdgeRays.get`
- `info.ray.direction.dot`
- `info.distances.push`
- `hardEdges.has`
- `ray.direction.dot`
- `queue.pop`
- `Math.abs`
- `otherTri.faceNormal.dot`
- `queue.push`
- `otherNormals[ otherNext ].norm.add`
- `normals.push`
- `sharedNormal1.norm.add`
- `otherNormals[ otherIndex ].norm.add`
- `sharedNormal2.norm.add`
- `normals[ i ].normalize`

**Internal Comments:**
```
// NOTE: 1e2 is pretty coarse but was chosen to quantize the resulting value because (x2)
// it allows edges to be smoothed as expected (see minifig arms). (x2)
// -- (x2)
// And the vector values are initialize multiplied by 1 + 1e-10 to account for floating (x2)
// point errors on vertices along quantization boundaries. Ie after matrix multiplication (x2)
// vertices that should be merged might be set to "1.7" and "1.6999..." meaning they won't (x2)
// get merged. This added epsilon attempts to push these error values to the same quantized (x2)
// value for the sake of hashing. See "AT-ST mini" dishes. See mrdoob/three#23169. (x2)
// converts the two vertices to a ray with a normalized direction and origin of 0, 0, 0 projected
// onto the original line.
// Save the list of hard edges by hash
// only generate the hard edge ray map if we're checking subsegments because it's more expensive to check
// and requires more memory.
// add both ray directions to the map (x2)
// store both segments ends in min, max order in the distances array to check if a face edge is a (x2)
// subsegment later. (x2)
// track the half edges associated with each triangle
// don't add the triangle if the edge is supposed to be hard
// if checking subsegments then check to see if this edge lies on a hard edge ray and whether its within any ray bounds
// return early if the face edge is found to be a subsegment of a line edge meaning the edge will have "hard" normals (x2)
// Iterate until we've tried to connect all faces to share normals
// Stop if there are no more faces left (x2)
// Exhaustively find all connected faces (x2)
// initialize all vertex normals in this triangle (x2)
// Check if any edge is connected to another triangle edge (x2)
// delete this triangle from the list so it won't be found again (x2)
// NOTE: If the angle between faces is > 67.5 degrees then assume it's
// hard edge. There are some cases where the line segments do not line up exactly
// with or span multiple triangle edges (see Lunar Vehicle wheels).
// if this triangle has already been traversed then it won't be in
// the halfEdgeList. If it has not then add it to the queue and delete
// it so it won't be found again.
// share the first normal (x2)
// it's possible to encounter an edge of a triangle that has already been traversed meaning (x3)
// both edges already have different normals defined and shared. To work around this we create (x3)
// a wrapper object so when those edges are merged the normals can be updated everywhere. (x3)
// share the second normal
// The normals of each face have been added up so now we average them by normalizing the vector.
```

<details><summary>Code</summary>

```typescript
function smoothNormals( faces, lineSegments, checkSubSegments = false ) {

	// NOTE: 1e2 is pretty coarse but was chosen to quantize the resulting value because
	// it allows edges to be smoothed as expected (see minifig arms).
	// --
	// And the vector values are initialize multiplied by 1 + 1e-10 to account for floating
	// point errors on vertices along quantization boundaries. Ie after matrix multiplication
	// vertices that should be merged might be set to "1.7" and "1.6999..." meaning they won't
	// get merged. This added epsilon attempts to push these error values to the same quantized
	// value for the sake of hashing. See "AT-ST mini" dishes. See mrdoob/three#23169.

	const hashMultiplier = ( 1 + 1e-10 ) * 1e2;
	function hashVertex( v ) {

		const x = ~ ~ ( v.x * hashMultiplier );
		const y = ~ ~ ( v.y * hashMultiplier );
		const z = ~ ~ ( v.z * hashMultiplier );

		return `${ x },${ y },${ z }`;

	}

	function hashEdge( v0, v1 ) {

		return `${ hashVertex( v0 ) }_${ hashVertex( v1 ) }`;

	}

	// converts the two vertices to a ray with a normalized direction and origin of 0, 0, 0 projected
	// onto the original line.
	function toNormalizedRay( v0, v1, targetRay ) {

		targetRay.direction.subVectors( v1, v0 ).normalize();

		const scalar = v0.dot( targetRay.direction );
		targetRay.origin.copy( v0 ).addScaledVector( targetRay.direction, - scalar );

		return targetRay;

	}

	function hashRay( ray ) {

		return hashEdge( ray.origin, ray.direction );

	}

	const hardEdges = new Set();
	const hardEdgeRays = new Map();
	const halfEdgeList = {};
	const normals = [];

	// Save the list of hard edges by hash
	for ( let i = 0, l = lineSegments.length; i < l; i ++ ) {

		const ls = lineSegments[ i ];
		const vertices = ls.vertices;
		const v0 = vertices[ 0 ];
		const v1 = vertices[ 1 ];
		hardEdges.add( hashEdge( v0, v1 ) );
		hardEdges.add( hashEdge( v1, v0 ) );

		// only generate the hard edge ray map if we're checking subsegments because it's more expensive to check
		// and requires more memory.
		if ( checkSubSegments ) {

			// add both ray directions to the map
			const ray = toNormalizedRay( v0, v1, new Ray() );
			const rh1 = hashRay( ray );
			if ( ! hardEdgeRays.has( rh1 ) ) {

				toNormalizedRay( v1, v0, ray );
				const rh2 = hashRay( ray );

				const info = {
					ray,
					distances: [],
				};

				hardEdgeRays.set( rh1, info );
				hardEdgeRays.set( rh2, info );

			}

			// store both segments ends in min, max order in the distances array to check if a face edge is a
			// subsegment later.
			const info = hardEdgeRays.get( rh1 );
			let d0 = info.ray.direction.dot( v0 );
			let d1 = info.ray.direction.dot( v1 );
			if ( d0 > d1 ) {

				[ d0, d1 ] = [ d1, d0 ];

			}

			info.distances.push( d0, d1 );

		}

	}

	// track the half edges associated with each triangle
	for ( let i = 0, l = faces.length; i < l; i ++ ) {

		const tri = faces[ i ];
		const vertices = tri.vertices;
		const vertCount = vertices.length;
		for ( let i2 = 0; i2 < vertCount; i2 ++ ) {

			const index = i2;
			const next = ( i2 + 1 ) % vertCount;
			const v0 = vertices[ index ];
			const v1 = vertices[ next ];
			const hash = hashEdge( v0, v1 );

			// don't add the triangle if the edge is supposed to be hard
			if ( hardEdges.has( hash ) ) {

				continue;

			}

			// if checking subsegments then check to see if this edge lies on a hard edge ray and whether its within any ray bounds
			if ( checkSubSegments ) {

				toNormalizedRay( v0, v1, _ray );

				const rayHash = hashRay( _ray );
				if ( hardEdgeRays.has( rayHash ) ) {

					const info = hardEdgeRays.get( rayHash );
					const { ray, distances } = info;
					let d0 = ray.direction.dot( v0 );
					let d1 = ray.direction.dot( v1 );

					if ( d0 > d1 ) {

						[ d0, d1 ] = [ d1, d0 ];

					}

					// return early if the face edge is found to be a subsegment of a line edge meaning the edge will have "hard" normals
					let found = false;
					for ( let i = 0, l = distances.length; i < l; i += 2 ) {

						if ( d0 >= distances[ i ] && d1 <= distances[ i + 1 ] ) {

							found = true;
							break;

						}

					}

					if ( found ) {

						continue;

					}

				}

			}

			const info = {
				index: index,
				tri: tri
			};
			halfEdgeList[ hash ] = info;

		}

	}

	// Iterate until we've tried to connect all faces to share normals
	while ( true ) {

		// Stop if there are no more faces left
		let halfEdge = null;
		for ( const key in halfEdgeList ) {

			halfEdge = halfEdgeList[ key ];
			break;

		}

		if ( halfEdge === null ) {

			break;

		}

		// Exhaustively find all connected faces
		const queue = [ halfEdge ];
		while ( queue.length > 0 ) {

			// initialize all vertex normals in this triangle
			const tri = queue.pop().tri;
			const vertices = tri.vertices;
			const vertNormals = tri.normals;
			const faceNormal = tri.faceNormal;

			// Check if any edge is connected to another triangle edge
			const vertCount = vertices.length;
			for ( let i2 = 0; i2 < vertCount; i2 ++ ) {

				const index = i2;
				const next = ( i2 + 1 ) % vertCount;
				const v0 = vertices[ index ];
				const v1 = vertices[ next ];

				// delete this triangle from the list so it won't be found again
				const hash = hashEdge( v0, v1 );
				delete halfEdgeList[ hash ];

				const reverseHash = hashEdge( v1, v0 );
				const otherInfo = halfEdgeList[ reverseHash ];
				if ( otherInfo ) {

					const otherTri = otherInfo.tri;
					const otherIndex = otherInfo.index;
					const otherNormals = otherTri.normals;
					const otherVertCount = otherNormals.length;
					const otherFaceNormal = otherTri.faceNormal;

					// NOTE: If the angle between faces is > 67.5 degrees then assume it's
					// hard edge. There are some cases where the line segments do not line up exactly
					// with or span multiple triangle edges (see Lunar Vehicle wheels).
					if ( Math.abs( otherTri.faceNormal.dot( tri.faceNormal ) ) < 0.25 ) {

						continue;

					}

					// if this triangle has already been traversed then it won't be in
					// the halfEdgeList. If it has not then add it to the queue and delete
					// it so it won't be found again.
					if ( reverseHash in halfEdgeList ) {

						queue.push( otherInfo );
						delete halfEdgeList[ reverseHash ];

					}

					// share the first normal
					const otherNext = ( otherIndex + 1 ) % otherVertCount;
					if (
						vertNormals[ index ] && otherNormals[ otherNext ] &&
						vertNormals[ index ] !== otherNormals[ otherNext ]
					) {

						otherNormals[ otherNext ].norm.add( vertNormals[ index ].norm );
						vertNormals[ index ].norm = otherNormals[ otherNext ].norm;

					}

					let sharedNormal1 = vertNormals[ index ] || otherNormals[ otherNext ];
					if ( sharedNormal1 === null ) {

						// it's possible to encounter an edge of a triangle that has already been traversed meaning
						// both edges already have different normals defined and shared. To work around this we create
						// a wrapper object so when those edges are merged the normals can be updated everywhere.
						sharedNormal1 = { norm: new Vector3() };
						normals.push( sharedNormal1.norm );

					}

					if ( vertNormals[ index ] === null ) {

						vertNormals[ index ] = sharedNormal1;
						sharedNormal1.norm.add( faceNormal );

					}

					if ( otherNormals[ otherNext ] === null ) {

						otherNormals[ otherNext ] = sharedNormal1;
						sharedNormal1.norm.add( otherFaceNormal );

					}

					// share the second normal
					if (
						vertNormals[ next ] && otherNormals[ otherIndex ] &&
						vertNormals[ next ] !== otherNormals[ otherIndex ]
					) {

						otherNormals[ otherIndex ].norm.add( vertNormals[ next ].norm );
						vertNormals[ next ].norm = otherNormals[ otherIndex ].norm;

					}

					let sharedNormal2 = vertNormals[ next ] || otherNormals[ otherIndex ];
					if ( sharedNormal2 === null ) {

						sharedNormal2 = { norm: new Vector3() };
						normals.push( sharedNormal2.norm );

					}

					if ( vertNormals[ next ] === null ) {

						vertNormals[ next ] = sharedNormal2;
						sharedNormal2.norm.add( faceNormal );

					}

					if ( otherNormals[ otherIndex ] === null ) {

						otherNormals[ otherIndex ] = sharedNormal2;
						sharedNormal2.norm.add( otherFaceNormal );

					}

				}

			}

		}

	}

	// The normals of each face have been added up so now we average them by normalizing the vector.
	for ( let i = 0, l = normals.length; i < l; i ++ ) {

		normals[ i ].normalize();

	}

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

		return `${ x },${ y },${ z }`;

	}
```
</details>

### `hashEdge(v0: any, v1: any): string`

**Parameters:**

- **`v0`** `any`
- **`v1`** `any`

**Returns:** `string`

**Calls:**

- `hashVertex`

<details><summary>Code</summary>

```typescript
function hashEdge( v0, v1 ) {

		return `${ hashVertex( v0 ) }_${ hashVertex( v1 ) }`;

	}
```
</details>

### `toNormalizedRay(v0: any, v1: any, targetRay: any): any`

**Parameters:**

- **`v0`** `any`
- **`v1`** `any`
- **`targetRay`** `any`

**Returns:** `any`

**Calls:**

- `targetRay.direction.subVectors( v1, v0 ).normalize`
- `v0.dot`
- `targetRay.origin.copy( v0 ).addScaledVector`

<details><summary>Code</summary>

```typescript
function toNormalizedRay( v0, v1, targetRay ) {

		targetRay.direction.subVectors( v1, v0 ).normalize();

		const scalar = v0.dot( targetRay.direction );
		targetRay.origin.copy( v0 ).addScaledVector( targetRay.direction, - scalar );

		return targetRay;

	}
```
</details>

### `hashRay(ray: any): string`

**Parameters:**

- **`ray`** `any`

**Returns:** `string`

**Calls:**

- `hashEdge`

<details><summary>Code</summary>

```typescript
function hashRay( ray ) {

		return hashEdge( ray.origin, ray.direction );

	}
```
</details>

### `isPartType(type: any): boolean`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function isPartType( type ) {

	return type === 'Part' || type === 'Unofficial_Part';

}
```
</details>

### `isPrimitiveType(type: any): boolean`

**Parameters:**

- **`type`** `any`

**Returns:** `boolean`

**Calls:**

- `/primitive/i.test`

<details><summary>Code</summary>

```typescript
function isPrimitiveType( type ) {

	return /primitive/i.test( type ) || type === 'Subpart';

}
```
</details>

### `LineParser.seekNonSpace(): void`

**Returns:** `void`

**Calls:**

- `this.line.charAt`

<details><summary>Code</summary>

```typescript
seekNonSpace() {

		while ( this.currentCharIndex < this.lineLength ) {

			this.currentChar = this.line.charAt( this.currentCharIndex );

			if ( this.currentChar !== ' ' && this.currentChar !== '\t' ) {

				return;

			}

			this.currentCharIndex ++;

		}

	}
```
</details>

### `LineParser.getToken(): any`

**Returns:** `any`

**Calls:**

- `this.line.charAt`
- `this.seekNonSpace`
- `this.line.substring`

**Internal Comments:**
```
// Seek space
```

<details><summary>Code</summary>

```typescript
getToken() {

		const pos0 = this.currentCharIndex ++;

		// Seek space
		while ( this.currentCharIndex < this.lineLength ) {

			this.currentChar = this.line.charAt( this.currentCharIndex );

			if ( this.currentChar === ' ' || this.currentChar === '\t' ) {

				break;

			}

			this.currentCharIndex ++;

		}

		const pos1 = this.currentCharIndex;

		this.seekNonSpace();

		return this.line.substring( pos0, pos1 );

	}
```
</details>

### `LineParser.getVector(): any`

**Returns:** `any`

**Calls:**

- `parseFloat`
- `this.getToken`

<details><summary>Code</summary>

```typescript
getVector() {

		return new Vector3( parseFloat( this.getToken() ), parseFloat( this.getToken() ), parseFloat( this.getToken() ) );

	}
```
</details>

### `LineParser.getRemainingString(): any`

**Returns:** `any`

**Calls:**

- `this.line.substring`

<details><summary>Code</summary>

```typescript
getRemainingString() {

		return this.line.substring( this.currentCharIndex, this.lineLength );

	}
```
</details>

### `LineParser.isAtTheEnd(): boolean`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
isAtTheEnd() {

		return this.currentCharIndex >= this.lineLength;

	}
```
</details>

### `LineParser.setToEnd(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setToEnd() {

		this.currentCharIndex = this.lineLength;

	}
```
</details>

### `LineParser.getLineNumberString(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getLineNumberString() {

		return this.lineNumber >= 0 ? ' at line ' + this.lineNumber : '';

	}
```
</details>

### `LDrawParsedCache.cloneResult(original: any): { faces: any; conditionalSegments: any; lineSegments: any; type: any; category: any; keywords: any; author: any; subobjects: any; fileName: any; totalFaces: any; startingBuildingStep: any; materials: any; group: any; }`

**Parameters:**

- **`original`** `any`

**Returns:** `{ faces: any; conditionalSegments: any; lineSegments: any; type: any; category: any; keywords: any; author: any; subobjects: any; fileName: any; totalFaces: any; startingBuildingStep: any; materials: any; group: any; }`

**Calls:**

- `original.faces.map`
- `face.vertices.map`
- `v.clone`
- `face.normals.map`
- `original.conditionalSegments.map`
- `face.controlPoints.map`
- `original.lineSegments.map`

**Internal Comments:**
```
// vertices are transformed and normals computed before being converted to geometry (x4)
// so these pieces must be cloned. (x4)
// none if this is subsequently modified (x4)
```

<details><summary>Code</summary>

```typescript
cloneResult( original ) {

		const result = {};

		// vertices are transformed and normals computed before being converted to geometry
		// so these pieces must be cloned.
		result.faces = original.faces.map( face => {

			return {
				colorCode: face.colorCode,
				material: face.material,
				vertices: face.vertices.map( v => v.clone() ),
				normals: face.normals.map( () => null ),
				faceNormal: null
			};

		} );

		result.conditionalSegments = original.conditionalSegments.map( face => {

			return {
				colorCode: face.colorCode,
				material: face.material,
				vertices: face.vertices.map( v => v.clone() ),
				controlPoints: face.controlPoints.map( v => v.clone() )
			};

		} );

		result.lineSegments = original.lineSegments.map( face => {

			return {
				colorCode: face.colorCode,
				material: face.material,
				vertices: face.vertices.map( v => v.clone() )
			};

		} );

		// none if this is subsequently modified
		result.type = original.type;
		result.category = original.category;
		result.keywords = original.keywords;
		result.author = original.author;
		result.subobjects = original.subobjects;
		result.fileName = original.fileName;
		result.totalFaces = original.totalFaces;
		result.startingBuildingStep = original.startingBuildingStep;
		result.materials = original.materials;
		result.group = null;
		return result;

	}
```
</details>

### `LDrawParsedCache.fetchData(fileName: any): Promise<any>`

**Parameters:**

- **`fileName`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `fileName.substring`
- `fileName.lastIndexOf`
- `fileName.toLowerCase`
- `fileLoader.setPath`
- `fileLoader.setRequestHeader`
- `fileLoader.setWithCredentials`
- `fileLoader.loadAsync`

**Internal Comments:**
```
// Try absolute path (x3)
// Next attempt is lower case (x3)
```

<details><summary>Code</summary>

```typescript
async fetchData( fileName ) {

		let triedLowerCase = false;
		let locationState = FILE_LOCATION_TRY_PARTS;
		while ( locationState !== FILE_LOCATION_NOT_FOUND ) {

			let subobjectURL = fileName;
			switch ( locationState ) {

				case FILE_LOCATION_AS_IS:
					locationState = locationState + 1;
					break;

				case FILE_LOCATION_TRY_PARTS:
					subobjectURL = 'parts/' + subobjectURL;
					locationState = locationState + 1;
					break;

				case FILE_LOCATION_TRY_P:
					subobjectURL = 'p/' + subobjectURL;
					locationState = locationState + 1;
					break;

				case FILE_LOCATION_TRY_MODELS:
					subobjectURL = 'models/' + subobjectURL;
					locationState = locationState + 1;
					break;

				case FILE_LOCATION_TRY_RELATIVE:
					subobjectURL = fileName.substring( 0, fileName.lastIndexOf( '/' ) + 1 ) + subobjectURL;
					locationState = locationState + 1;
					break;

				case FILE_LOCATION_TRY_ABSOLUTE:

					if ( triedLowerCase ) {

						// Try absolute path
						locationState = FILE_LOCATION_NOT_FOUND;

					} else {

						// Next attempt is lower case
						fileName = fileName.toLowerCase();
						subobjectURL = fileName;
						triedLowerCase = true;
						locationState = FILE_LOCATION_TRY_PARTS;

					}

					break;

			}

			const loader = this.loader;
			const fileLoader = new FileLoader( loader.manager );
			fileLoader.setPath( loader.partsLibraryPath );
			fileLoader.setRequestHeader( loader.requestHeader );
			fileLoader.setWithCredentials( loader.withCredentials );

			try {

				const text = await fileLoader.loadAsync( subobjectURL );
				return text;

			} catch ( _ ) {

				continue;

			}

		}

		throw new Error( 'LDrawLoader: Subobject "' + fileName + '" could not be loaded.' );

	}
```
</details>

### `LDrawParsedCache.parse(text: any, fileName: any): { faces: { material: any; colorCode: any; faceNormal: any; vertices: any[]; normals: any[]; }[]; conditionalSegments: { material: any; colorCode: any; vertices: any[]; controlPoints: any[]; }[]; lineSegments: { material: any; colorCode: any; vertices: any[]; }[]; ... 9 more ...; group: any; }`

**Parameters:**

- **`text`** `any`
- **`fileName`** `any`

**Returns:** `{ faces: { material: any; colorCode: any; faceNormal: any; vertices: any[]; normals: any[]; }[]; conditionalSegments: { material: any; colorCode: any; vertices: any[]; controlPoints: any[]; }[]; lineSegments: { material: any; colorCode: any; vertices: any[]; }[]; ... 9 more ...; group: any; }`

**Calls:**

- `text.indexOf`
- `text.replace`
- `text.split`
- `line.startsWith`
- `this.setData`
- `line.substring`
- `lp.seekNonSpace`
- `lp.isAtTheEnd`
- `lp.getToken`
- `loader.parseColorMetaDirective`
- `console.warn`
- `lp.getLineNumberString`
- `lp.getRemainingString().split`
- `newKeywords.forEach`
- `keywords.push`
- `keyword.trim`
- `lp.getRemainingString`
- `getLocalMaterial`
- `parseFloat`
- `new Matrix4().set`
- `lp.getRemainingString().trim().replace`
- `fileName.startsWith`
- `subobjects.push`
- `lp.getVector`
- `lineSegments.push`
- `conditionalSegments.push`
- `faces.push`

**Internal Comments:**
```
// final results (x2)
// split into lines
// This is faster than String.split with regex that splits on both (x3)
// Parse all line commands
// Save previous embedded file in the cache (x4)
// New embedded text file (x3)
// Empty line
// Parse the line type (x2)
// Line type 0: Comment or META
// Parse meta directive (x2)
// Start embedded text files parsing (x3)
// Changes to the backface culling state
// Other meta directives are not implemented
// Line type 1: Sub-object file
// Found the subobject path in the preloaded file path map (x3)
// Standardized subfolders
// Line type 2: Line segment
// Line type 5: Conditional Line segment
// Line type 3: Triangle
// Line type 4: Quadrilateral
// specifically place the triangle diagonal in the v0 and v1 slots so we can (x4)
// account for the doubling of vertices later when smoothing normals. (x4)
```

<details><summary>Code</summary>

```typescript
parse( text, fileName = null ) {

		const loader = this.loader;

		// final results
		const faces = [];
		const lineSegments = [];
		const conditionalSegments = [];
		const subobjects = [];
		const materials = {};

		const getLocalMaterial = colorCode => {

			return materials[ colorCode ] || null;

		};

		let type = 'Model';
		let category = null;
		let keywords = null;
		let author = null;
		let totalFaces = 0;

		// split into lines
		if ( text.indexOf( '\r\n' ) !== - 1 ) {

			// This is faster than String.split with regex that splits on both
			text = text.replace( /\r\n/g, '\n' );

		}

		const lines = text.split( '\n' );
		const numLines = lines.length;

		let parsingEmbeddedFiles = false;
		let currentEmbeddedFileName = null;
		let currentEmbeddedText = null;

		let bfcCertified = false;
		let bfcCCW = true;
		let bfcInverted = false;
		let bfcCull = true;

		let startingBuildingStep = false;

		// Parse all line commands
		for ( let lineIndex = 0; lineIndex < numLines; lineIndex ++ ) {

			const line = lines[ lineIndex ];

			if ( line.length === 0 ) continue;

			if ( parsingEmbeddedFiles ) {

				if ( line.startsWith( '0 FILE ' ) ) {

					// Save previous embedded file in the cache
					this.setData( currentEmbeddedFileName, currentEmbeddedText );

					// New embedded text file
					currentEmbeddedFileName = line.substring( 7 );
					currentEmbeddedText = '';

				} else {

					currentEmbeddedText += line + '\n';

				}

				continue;

			}

			const lp = new LineParser( line, lineIndex + 1 );
			lp.seekNonSpace();

			if ( lp.isAtTheEnd() ) {

				// Empty line
				continue;

			}

			// Parse the line type
			const lineType = lp.getToken();

			let material;
			let colorCode;
			let segment;
			let ccw;
			let doubleSided;
			let v0, v1, v2, v3, c0, c1;

			switch ( lineType ) {

				// Line type 0: Comment or META
				case '0':

					// Parse meta directive
					const meta = lp.getToken();

					if ( meta ) {

						switch ( meta ) {

							case '!LDRAW_ORG':

								type = lp.getToken();
								break;

							case '!COLOUR':

								material = loader.parseColorMetaDirective( lp );
								if ( material ) {

									materials[ material.userData.code ] = material;

								}	else {

									console.warn( 'LDrawLoader: Error parsing material' + lp.getLineNumberString() );

								}

								break;

							case '!CATEGORY':

								category = lp.getToken();
								break;

							case '!KEYWORDS':

								const newKeywords = lp.getRemainingString().split( ',' );
								if ( newKeywords.length > 0 ) {

									if ( ! keywords ) {

										keywords = [];

									}

									newKeywords.forEach( function ( keyword ) {

										keywords.push( keyword.trim() );

									} );

								}

								break;

							case 'FILE':

								if ( lineIndex > 0 ) {

									// Start embedded text files parsing
									parsingEmbeddedFiles = true;
									currentEmbeddedFileName = lp.getRemainingString();
									currentEmbeddedText = '';

									bfcCertified = false;
									bfcCCW = true;

								}

								break;

							case 'BFC':

								// Changes to the backface culling state
								while ( ! lp.isAtTheEnd() ) {

									const token = lp.getToken();

									switch ( token ) {

										case 'CERTIFY':
										case 'NOCERTIFY':

											bfcCertified = token === 'CERTIFY';
											bfcCCW = true;

											break;

										case 'CW':
										case 'CCW':

											bfcCCW = token === 'CCW';

											break;

										case 'INVERTNEXT':

											bfcInverted = true;

											break;

										case 'CLIP':
										case 'NOCLIP':

											bfcCull = token === 'CLIP';

											break;

										default:

											console.warn( 'THREE.LDrawLoader: BFC directive "' + token + '" is unknown.' );

											break;

									}

								}

								break;

							case 'STEP':

								startingBuildingStep = true;

								break;

							case 'Author:':

								author = lp.getToken();

								break;

							default:
								// Other meta directives are not implemented
								break;

						}

					}

					break;

					// Line type 1: Sub-object file
				case '1':

					colorCode = lp.getToken();
					material = getLocalMaterial( colorCode );

					const posX = parseFloat( lp.getToken() );
					const posY = parseFloat( lp.getToken() );
					const posZ = parseFloat( lp.getToken() );
					const m0 = parseFloat( lp.getToken() );
					const m1 = parseFloat( lp.getToken() );
					const m2 = parseFloat( lp.getToken() );
					const m3 = parseFloat( lp.getToken() );
					const m4 = parseFloat( lp.getToken() );
					const m5 = parseFloat( lp.getToken() );
					const m6 = parseFloat( lp.getToken() );
					const m7 = parseFloat( lp.getToken() );
					const m8 = parseFloat( lp.getToken() );

					const matrix = new Matrix4().set(
						m0, m1, m2, posX,
						m3, m4, m5, posY,
						m6, m7, m8, posZ,
						0, 0, 0, 1
					);

					let fileName = lp.getRemainingString().trim().replace( /\\/g, '/' );

					if ( loader.fileMap[ fileName ] ) {

						// Found the subobject path in the preloaded file path map
						fileName = loader.fileMap[ fileName ];

					} else {

						// Standardized subfolders
						if ( fileName.startsWith( 's/' ) ) {

							fileName = 'parts/' + fileName;

						} else if ( fileName.startsWith( '48/' ) ) {

							fileName = 'p/' + fileName;

						}

					}

					subobjects.push( {
						material: material,
						colorCode: colorCode,
						matrix: matrix,
						fileName: fileName,
						inverted: bfcInverted,
						startingBuildingStep: startingBuildingStep
					} );

					startingBuildingStep = false;
					bfcInverted = false;

					break;

					// Line type 2: Line segment
				case '2':

					colorCode = lp.getToken();
					material = getLocalMaterial( colorCode );
					v0 = lp.getVector();
					v1 = lp.getVector();

					segment = {
						material: material,
						colorCode: colorCode,
						vertices: [ v0, v1 ],
					};

					lineSegments.push( segment );

					break;

					// Line type 5: Conditional Line segment
				case '5':

					colorCode = lp.getToken();
					material = getLocalMaterial( colorCode );
					v0 = lp.getVector();
					v1 = lp.getVector();
					c0 = lp.getVector();
					c1 = lp.getVector();

					segment = {
						material: material,
						colorCode: colorCode,
						vertices: [ v0, v1 ],
						controlPoints: [ c0, c1 ],
					};

					conditionalSegments.push( segment );

					break;

					// Line type 3: Triangle
				case '3':

					colorCode = lp.getToken();
					material = getLocalMaterial( colorCode );
					ccw = bfcCCW;
					doubleSided = ! bfcCertified || ! bfcCull;

					if ( ccw === true ) {

						v0 = lp.getVector();
						v1 = lp.getVector();
						v2 = lp.getVector();

					} else {

						v2 = lp.getVector();
						v1 = lp.getVector();
						v0 = lp.getVector();

					}

					faces.push( {
						material: material,
						colorCode: colorCode,
						faceNormal: null,
						vertices: [ v0, v1, v2 ],
						normals: [ null, null, null ],
					} );
					totalFaces ++;

					if ( doubleSided === true ) {

						faces.push( {
							material: material,
							colorCode: colorCode,
							faceNormal: null,
							vertices: [ v2, v1, v0 ],
							normals: [ null, null, null ],
						} );
						totalFaces ++;

					}

					break;

					// Line type 4: Quadrilateral
				case '4':

					colorCode = lp.getToken();
					material = getLocalMaterial( colorCode );
					ccw = bfcCCW;
					doubleSided = ! bfcCertified || ! bfcCull;

					if ( ccw === true ) {

						v0 = lp.getVector();
						v1 = lp.getVector();
						v2 = lp.getVector();
						v3 = lp.getVector();

					} else {

						v3 = lp.getVector();
						v2 = lp.getVector();
						v1 = lp.getVector();
						v0 = lp.getVector();

					}

					// specifically place the triangle diagonal in the v0 and v1 slots so we can
					// account for the doubling of vertices later when smoothing normals.
					faces.push( {
						material: material,
						colorCode: colorCode,
						faceNormal: null,
						vertices: [ v0, v1, v2, v3 ],
						normals: [ null, null, null, null ],
					} );
					totalFaces += 2;

					if ( doubleSided === true ) {

						faces.push( {
							material: material,
							colorCode: colorCode,
							faceNormal: null,
							vertices: [ v3, v2, v1, v0 ],
							normals: [ null, null, null, null ],
						} );
						totalFaces += 2;

					}

					break;

				default:
					throw new Error( 'LDrawLoader: Unknown line type "' + lineType + '"' + lp.getLineNumberString() + '.' );

			}

		}

		if ( parsingEmbeddedFiles ) {

			this.setData( currentEmbeddedFileName, currentEmbeddedText );

		}

		return {
			faces,
			conditionalSegments,
			lineSegments,
			type,
			category,
			keywords,
			author,
			subobjects,
			totalFaces,
			startingBuildingStep,
			materials,
			fileName,
			group: null
		};

	}
```
</details>

### `LDrawParsedCache.getData(fileName: any, clone: boolean): any`

**Parameters:**

- **`fileName`** `any`
- **`clone`** `boolean`

**Returns:** `any`

**Calls:**

- `fileName.toLowerCase`
- `this.cloneResult`

<details><summary>Code</summary>

```typescript
getData( fileName, clone = true ) {

		const key = fileName.toLowerCase();
		const result = this._cache[ key ];
		if ( result === null || result instanceof Promise ) {

			return null;

		}

		if ( clone ) {

			return this.cloneResult( result );

		} else {

			return result;

		}

	}
```
</details>

### `LDrawParsedCache.ensureDataLoaded(fileName: any): Promise<void>`

**Parameters:**

- **`fileName`** `any`

**Returns:** `Promise<void>`

**Calls:**

- `fileName.toLowerCase`
- `this.fetchData( fileName ).then`
- `this.parse`

**Internal Comments:**
```
// replace the promise with a copy of the parsed data for immediate processing (x5)
```

<details><summary>Code</summary>

```typescript
async ensureDataLoaded( fileName ) {

		const key = fileName.toLowerCase();
		if ( ! ( key in this._cache ) ) {

			// replace the promise with a copy of the parsed data for immediate processing
			this._cache[ key ] = this.fetchData( fileName ).then( text => {

				const info = this.parse( text, fileName );
				this._cache[ key ] = info;
				return info;

			} );

		}

		await this._cache[ key ];

	}
```
</details>

### `LDrawParsedCache.setData(fileName: any, text: any): void`

**Parameters:**

- **`fileName`** `any`
- **`text`** `any`

**Returns:** `void`

**Calls:**

- `fileName.toLowerCase`
- `this.parse`

<details><summary>Code</summary>

```typescript
setData( fileName, text ) {

		const key = fileName.toLowerCase();
		this._cache[ key ] = this.parse( text, fileName );

	}
```
</details>

### `getLocalMaterial(colorCode: any): any`

**Parameters:**

- **`colorCode`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
colorCode => {

			return materials[ colorCode ] || null;

		}
```
</details>

### `getMaterialFromCode(colorCode: any, parentColorCode: any, materialHierarchy: any, forEdge: any): any`

**Parameters:**

- **`colorCode`** `any`
- **`parentColorCode`** `any`
- **`materialHierarchy`** `any`
- **`forEdge`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getMaterialFromCode( colorCode, parentColorCode, materialHierarchy, forEdge ) {

	const isPassthrough = ! forEdge && colorCode === MAIN_COLOUR_CODE || forEdge && colorCode === MAIN_EDGE_COLOUR_CODE;
	if ( isPassthrough ) {

		colorCode = parentColorCode;

	}

	return materialHierarchy[ colorCode ] || null;

}
```
</details>

### `LDrawPartsGeometryCache.processIntoMesh(info: any): Promise<any>`

**Parameters:**

- **`info`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `parseCache.ensureDataLoaded( subobject.fileName ).then`
- `parseCache.getData`
- `isPrimitiveType`
- `this.loadModel( subobject.fileName ).catch`
- `console.warn`
- `processInfoSubobjects`
- `promises.push`
- `Promise.all`
- `subobject.matrix.decompose`
- `loader.applyMaterialsToMesh`
- `group.add`
- `matrix.determinant`
- `vertices[ 0 ].applyMatrix4`
- `vertices[ 1 ].applyMatrix4`
- `getMaterialFromCode`
- `parentLineSegments.push`
- `controlPoints[ 0 ].applyMatrix4`
- `controlPoints[ 1 ].applyMatrix4`
- `parentConditionalSegments.push`
- `vertices[ i ].applyMatrix4`
- `faceMaterials.add`
- `vertices.reverse`
- `parentFaces.push`
- `generateFaceNormals`
- `smoothNormals`
- `createObject`

**Internal Comments:**
```
// Processes the part subobject information to load child parts and merge geometry onto part (x2)
// piece object. (x2)
// Trigger load of all subobjects. If a subobject isn't a primitive then load it as a separate
// group which lets instruction steps apply correctly.
// the subobject failed to load
// if the subobject was loaded as a separate group then apply the parent scopes materials
// add the subobject group if it has children in case it has both children and primitives
// transform the primitives into the local space of the parent piece and append them to (x2)
// to the parent primitives list. (x2)
// If the scale of the object is negated then the triangle winding order
// needs to be flipped.
// Apply the parent subobjects pass through material code to this object. This is done several times due
// to material scoping.
// Track material use to see if we need to use the normal smooth slow path for hard edges.
// Add the primitive objects and metadata. (x2)
```

<details><summary>Code</summary>

```typescript
async processIntoMesh( info ) {

		const loader = this.loader;
		const parseCache = this.parseCache;
		const faceMaterials = new Set();

		// Processes the part subobject information to load child parts and merge geometry onto part
		// piece object.
		const processInfoSubobjects = async ( info, subobject = null ) => {

			const subobjects = info.subobjects;
			const promises = [];

			// Trigger load of all subobjects. If a subobject isn't a primitive then load it as a separate
			// group which lets instruction steps apply correctly.
			for ( let i = 0, l = subobjects.length; i < l; i ++ ) {

				const subobject = subobjects[ i ];
				const promise = parseCache.ensureDataLoaded( subobject.fileName ).then( () => {

					const subobjectInfo = parseCache.getData( subobject.fileName, false );
					if ( ! isPrimitiveType( subobjectInfo.type ) ) {

						return this.loadModel( subobject.fileName ).catch( error => {

							console.warn( error );
							return null;

						} );

					}

					return processInfoSubobjects( parseCache.getData( subobject.fileName ), subobject );

				} );

				promises.push( promise );

			}

			const group = new Group();
			group.userData.category = info.category;
			group.userData.keywords = info.keywords;
			group.userData.author = info.author;
			group.userData.type = info.type;
			group.userData.fileName = info.fileName;
			info.group = group;

			const subobjectInfos = await Promise.all( promises );
			for ( let i = 0, l = subobjectInfos.length; i < l; i ++ ) {

				const subobject = info.subobjects[ i ];
				const subobjectInfo = subobjectInfos[ i ];

				if ( subobjectInfo === null ) {

					// the subobject failed to load
					continue;

				}

				// if the subobject was loaded as a separate group then apply the parent scopes materials
				if ( subobjectInfo.isGroup ) {

					const subobjectGroup = subobjectInfo;
					subobject.matrix.decompose( subobjectGroup.position, subobjectGroup.quaternion, subobjectGroup.scale );
					subobjectGroup.userData.startingBuildingStep = subobject.startingBuildingStep;
					subobjectGroup.name = subobject.fileName;

					loader.applyMaterialsToMesh( subobjectGroup, subobject.colorCode, info.materials );
					subobjectGroup.userData.colorCode = subobject.colorCode;

					group.add( subobjectGroup );
					continue;

				}

				// add the subobject group if it has children in case it has both children and primitives
				if ( subobjectInfo.group.children.length ) {

					group.add( subobjectInfo.group );

				}

				// transform the primitives into the local space of the parent piece and append them to
				// to the parent primitives list.
				const parentLineSegments = info.lineSegments;
				const parentConditionalSegments = info.conditionalSegments;
				const parentFaces = info.faces;

				const lineSegments = subobjectInfo.lineSegments;
				const conditionalSegments = subobjectInfo.conditionalSegments;

				const faces = subobjectInfo.faces;
				const matrix = subobject.matrix;
				const inverted = subobject.inverted;
				const matrixScaleInverted = matrix.determinant() < 0;
				const colorCode = subobject.colorCode;

				const lineColorCode = colorCode === MAIN_COLOUR_CODE ? MAIN_EDGE_COLOUR_CODE : colorCode;
				for ( let i = 0, l = lineSegments.length; i < l; i ++ ) {

					const ls = lineSegments[ i ];
					const vertices = ls.vertices;
					vertices[ 0 ].applyMatrix4( matrix );
					vertices[ 1 ].applyMatrix4( matrix );
					ls.colorCode = ls.colorCode === MAIN_EDGE_COLOUR_CODE ? lineColorCode : ls.colorCode;
					ls.material = ls.material || getMaterialFromCode( ls.colorCode, ls.colorCode, info.materials, true );

					parentLineSegments.push( ls );

				}

				for ( let i = 0, l = conditionalSegments.length; i < l; i ++ ) {

					const os = conditionalSegments[ i ];
					const vertices = os.vertices;
					const controlPoints = os.controlPoints;
					vertices[ 0 ].applyMatrix4( matrix );
					vertices[ 1 ].applyMatrix4( matrix );
					controlPoints[ 0 ].applyMatrix4( matrix );
					controlPoints[ 1 ].applyMatrix4( matrix );
					os.colorCode = os.colorCode === MAIN_EDGE_COLOUR_CODE ? lineColorCode : os.colorCode;
					os.material = os.material || getMaterialFromCode( os.colorCode, os.colorCode, info.materials, true );

					parentConditionalSegments.push( os );

				}

				for ( let i = 0, l = faces.length; i < l; i ++ ) {

					const tri = faces[ i ];
					const vertices = tri.vertices;
					for ( let i = 0, l = vertices.length; i < l; i ++ ) {

						vertices[ i ].applyMatrix4( matrix );

					}

					tri.colorCode = tri.colorCode === MAIN_COLOUR_CODE ? colorCode : tri.colorCode;
					tri.material = tri.material || getMaterialFromCode( tri.colorCode, colorCode, info.materials, false );
					faceMaterials.add( tri.colorCode );

					// If the scale of the object is negated then the triangle winding order
					// needs to be flipped.
					if ( matrixScaleInverted !== inverted ) {

						vertices.reverse();

					}

					parentFaces.push( tri );

				}

				info.totalFaces += subobjectInfo.totalFaces;

			}

			// Apply the parent subobjects pass through material code to this object. This is done several times due
			// to material scoping.
			if ( subobject ) {

				loader.applyMaterialsToMesh( group, subobject.colorCode, info.materials );
				group.userData.colorCode = subobject.colorCode;

			}

			return info;

		};

		// Track material use to see if we need to use the normal smooth slow path for hard edges.
		for ( let i = 0, l = info.faces; i < l; i ++ ) {

			faceMaterials.add( info.faces[ i ].colorCode );

		}

		await processInfoSubobjects( info );

		if ( loader.smoothNormals ) {

			const checkSubSegments = faceMaterials.size > 1;
			generateFaceNormals( info.faces );
			smoothNormals( info.faces, info.lineSegments, checkSubSegments );

		}

		// Add the primitive objects and metadata.
		const group = info.group;
		if ( info.faces.length > 0 ) {

			group.add( createObject( this.loader, info.faces, 3, false, info.totalFaces ) );

		}

		if ( info.lineSegments.length > 0 ) {

			group.add( createObject( this.loader, info.lineSegments, 2 ) );

		}

		if ( info.conditionalSegments.length > 0 ) {

			group.add( createObject( this.loader, info.conditionalSegments, 2, true ) );

		}

		return group;

	}
```
</details>

### `LDrawPartsGeometryCache.hasCachedModel(fileName: any): boolean`

**Parameters:**

- **`fileName`** `any`

**Returns:** `boolean`

**Calls:**

- `fileName.toLowerCase`

<details><summary>Code</summary>

```typescript
hasCachedModel( fileName ) {

		return fileName !== null && fileName.toLowerCase() in this._cache;

	}
```
</details>

### `LDrawPartsGeometryCache.getCachedModel(fileName: any): Promise<any>`

**Parameters:**

- **`fileName`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `this.hasCachedModel`
- `fileName.toLowerCase`
- `group.clone`

<details><summary>Code</summary>

```typescript
async getCachedModel( fileName ) {

		if ( fileName !== null && this.hasCachedModel( fileName ) ) {

			const key = fileName.toLowerCase();
			const group = await this._cache[ key ];
			return group.clone();

		} else {

			return null;

		}

	}
```
</details>

### `LDrawPartsGeometryCache.loadModel(fileName: any): Promise<any>`

**Parameters:**

- **`fileName`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `fileName.toLowerCase`
- `this.hasCachedModel`
- `this.getCachedModel`
- `parseCache.ensureDataLoaded`
- `parseCache.getData`
- `this.processIntoMesh`
- `isPartType`
- `group.clone`

**Internal Comments:**
```
// Return cached model if available.
// Otherwise parse a new model. (x2)
// Ensure the file data is loaded and pre parsed. (x2)
// Now that the file has loaded it's possible that another part parse has been waiting in parallel
// so check the cache again to see if it's been added since the last async operation so we don't
// do unnecessary work.
// Cache object if it's a part so it can be reused later.
// return a copy (x2)
```

<details><summary>Code</summary>

```typescript
async loadModel( fileName ) {

		const parseCache = this.parseCache;
		const key = fileName.toLowerCase();
		if ( this.hasCachedModel( fileName ) ) {

			// Return cached model if available.
			return this.getCachedModel( fileName );

		} else {

			// Otherwise parse a new model.
			// Ensure the file data is loaded and pre parsed.
			await parseCache.ensureDataLoaded( fileName );

			const info = parseCache.getData( fileName );
			const promise = this.processIntoMesh( info );

			// Now that the file has loaded it's possible that another part parse has been waiting in parallel
			// so check the cache again to see if it's been added since the last async operation so we don't
			// do unnecessary work.
			if ( this.hasCachedModel( fileName ) ) {

				return this.getCachedModel( fileName );

			}

			// Cache object if it's a part so it can be reused later.
			if ( isPartType( info.type ) ) {

				this._cache[ key ] = promise;

			}

			// return a copy
			const group = await promise;
			return group.clone();

		}

	}
```
</details>

### `LDrawPartsGeometryCache.parseModel(text: any): Promise<any>`

**Parameters:**

- **`text`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `parseCache.parse`
- `isPartType`
- `this.hasCachedModel`
- `this.getCachedModel`
- `this.processIntoMesh`

<details><summary>Code</summary>

```typescript
async parseModel( text ) {

		const parseCache = this.parseCache;
		const info = parseCache.parse( text );
		if ( isPartType( info.type ) && this.hasCachedModel( info.fileName ) ) {

			return this.getCachedModel( info.fileName );

		}

		return this.processIntoMesh( info );

	}
```
</details>

### `processInfoSubobjects(info: any, subobject: any): Promise<any>`

**Parameters:**

- **`info`** `any`
- **`subobject`** `any`

**Returns:** `Promise<any>`

**Calls:**

- `parseCache.ensureDataLoaded( subobject.fileName ).then`
- `parseCache.getData`
- `isPrimitiveType`
- `this.loadModel( subobject.fileName ).catch`
- `console.warn`
- `processInfoSubobjects`
- `promises.push`
- `Promise.all`
- `subobject.matrix.decompose`
- `loader.applyMaterialsToMesh`
- `group.add`
- `matrix.determinant`
- `vertices[ 0 ].applyMatrix4`
- `vertices[ 1 ].applyMatrix4`
- `getMaterialFromCode`
- `parentLineSegments.push`
- `controlPoints[ 0 ].applyMatrix4`
- `controlPoints[ 1 ].applyMatrix4`
- `parentConditionalSegments.push`
- `vertices[ i ].applyMatrix4`
- `faceMaterials.add`
- `vertices.reverse`
- `parentFaces.push`

**Internal Comments:**
```
// Trigger load of all subobjects. If a subobject isn't a primitive then load it as a separate
// group which lets instruction steps apply correctly.
// the subobject failed to load
// if the subobject was loaded as a separate group then apply the parent scopes materials
// add the subobject group if it has children in case it has both children and primitives
// transform the primitives into the local space of the parent piece and append them to (x2)
// to the parent primitives list. (x2)
// If the scale of the object is negated then the triangle winding order
// needs to be flipped.
// Apply the parent subobjects pass through material code to this object. This is done several times due
// to material scoping.
```

<details><summary>Code</summary>

```typescript
async ( info, subobject = null ) => {

			const subobjects = info.subobjects;
			const promises = [];

			// Trigger load of all subobjects. If a subobject isn't a primitive then load it as a separate
			// group which lets instruction steps apply correctly.
			for ( let i = 0, l = subobjects.length; i < l; i ++ ) {

				const subobject = subobjects[ i ];
				const promise = parseCache.ensureDataLoaded( subobject.fileName ).then( () => {

					const subobjectInfo = parseCache.getData( subobject.fileName, false );
					if ( ! isPrimitiveType( subobjectInfo.type ) ) {

						return this.loadModel( subobject.fileName ).catch( error => {

							console.warn( error );
							return null;

						} );

					}

					return processInfoSubobjects( parseCache.getData( subobject.fileName ), subobject );

				} );

				promises.push( promise );

			}

			const group = new Group();
			group.userData.category = info.category;
			group.userData.keywords = info.keywords;
			group.userData.author = info.author;
			group.userData.type = info.type;
			group.userData.fileName = info.fileName;
			info.group = group;

			const subobjectInfos = await Promise.all( promises );
			for ( let i = 0, l = subobjectInfos.length; i < l; i ++ ) {

				const subobject = info.subobjects[ i ];
				const subobjectInfo = subobjectInfos[ i ];

				if ( subobjectInfo === null ) {

					// the subobject failed to load
					continue;

				}

				// if the subobject was loaded as a separate group then apply the parent scopes materials
				if ( subobjectInfo.isGroup ) {

					const subobjectGroup = subobjectInfo;
					subobject.matrix.decompose( subobjectGroup.position, subobjectGroup.quaternion, subobjectGroup.scale );
					subobjectGroup.userData.startingBuildingStep = subobject.startingBuildingStep;
					subobjectGroup.name = subobject.fileName;

					loader.applyMaterialsToMesh( subobjectGroup, subobject.colorCode, info.materials );
					subobjectGroup.userData.colorCode = subobject.colorCode;

					group.add( subobjectGroup );
					continue;

				}

				// add the subobject group if it has children in case it has both children and primitives
				if ( subobjectInfo.group.children.length ) {

					group.add( subobjectInfo.group );

				}

				// transform the primitives into the local space of the parent piece and append them to
				// to the parent primitives list.
				const parentLineSegments = info.lineSegments;
				const parentConditionalSegments = info.conditionalSegments;
				const parentFaces = info.faces;

				const lineSegments = subobjectInfo.lineSegments;
				const conditionalSegments = subobjectInfo.conditionalSegments;

				const faces = subobjectInfo.faces;
				const matrix = subobject.matrix;
				const inverted = subobject.inverted;
				const matrixScaleInverted = matrix.determinant() < 0;
				const colorCode = subobject.colorCode;

				const lineColorCode = colorCode === MAIN_COLOUR_CODE ? MAIN_EDGE_COLOUR_CODE : colorCode;
				for ( let i = 0, l = lineSegments.length; i < l; i ++ ) {

					const ls = lineSegments[ i ];
					const vertices = ls.vertices;
					vertices[ 0 ].applyMatrix4( matrix );
					vertices[ 1 ].applyMatrix4( matrix );
					ls.colorCode = ls.colorCode === MAIN_EDGE_COLOUR_CODE ? lineColorCode : ls.colorCode;
					ls.material = ls.material || getMaterialFromCode( ls.colorCode, ls.colorCode, info.materials, true );

					parentLineSegments.push( ls );

				}

				for ( let i = 0, l = conditionalSegments.length; i < l; i ++ ) {

					const os = conditionalSegments[ i ];
					const vertices = os.vertices;
					const controlPoints = os.controlPoints;
					vertices[ 0 ].applyMatrix4( matrix );
					vertices[ 1 ].applyMatrix4( matrix );
					controlPoints[ 0 ].applyMatrix4( matrix );
					controlPoints[ 1 ].applyMatrix4( matrix );
					os.colorCode = os.colorCode === MAIN_EDGE_COLOUR_CODE ? lineColorCode : os.colorCode;
					os.material = os.material || getMaterialFromCode( os.colorCode, os.colorCode, info.materials, true );

					parentConditionalSegments.push( os );

				}

				for ( let i = 0, l = faces.length; i < l; i ++ ) {

					const tri = faces[ i ];
					const vertices = tri.vertices;
					for ( let i = 0, l = vertices.length; i < l; i ++ ) {

						vertices[ i ].applyMatrix4( matrix );

					}

					tri.colorCode = tri.colorCode === MAIN_COLOUR_CODE ? colorCode : tri.colorCode;
					tri.material = tri.material || getMaterialFromCode( tri.colorCode, colorCode, info.materials, false );
					faceMaterials.add( tri.colorCode );

					// If the scale of the object is negated then the triangle winding order
					// needs to be flipped.
					if ( matrixScaleInverted !== inverted ) {

						vertices.reverse();

					}

					parentFaces.push( tri );

				}

				info.totalFaces += subobjectInfo.totalFaces;

			}

			// Apply the parent subobjects pass through material code to this object. This is done several times due
			// to material scoping.
			if ( subobject ) {

				loader.applyMaterialsToMesh( group, subobject.colorCode, info.materials );
				group.userData.colorCode = subobject.colorCode;

			}

			return info;

		}
```
</details>

### `sortByMaterial(a: any, b: any): 1 | 0 | -1`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `1 | 0 | -1`

<details><summary>Code</summary>

```typescript
function sortByMaterial( a, b ) {

	if ( a.colorCode === b.colorCode ) {

		return 0;

	}

	if ( a.colorCode < b.colorCode ) {

		return - 1;

	}

	return 1;

}
```
</details>

### `createObject(loader: any, elements: any, elementSize: any, isConditionalSegments: boolean, totalElements: any): any`

**Parameters:**

- **`loader`** `any`
- **`elements`** `any`
- **`elementSize`** `any`
- **`isConditionalSegments`** `boolean`
- **`totalElements`** `any`

**Returns:** `any`

**Calls:**

- `elements.sort`
- `_tempVec0.subVectors`
- `_tempVec1.subVectors`
- `new Vector3()
					.crossVectors( _tempVec0, _tempVec1 )
					.normalize`
- `bufferGeometry.addGroup`
- `materials.push`
- `loader.edgeMaterialCache.get`
- `loader.conditionalEdgeMaterialCache.get`
- `bufferGeometry.setAttribute`

**Internal Comments:**
```
// Creates a LineSegments (elementSize = 2) or a Mesh (elementSize = 3 ) (x4)
// With per face / segment material, implemented with mesh groups and materials array (x4)
// Sort the faces or line segments by color code to make later the mesh groups (x4)
// create the normals array if this is a set of faces
// use face normal if a vertex normal is not provided (x2)
// If a material has not been made available yet then keep the color code string in the material array (x4)
// to save the spot for the material once a parent scopes materials are being applied to the object. (x4)
```

<details><summary>Code</summary>

```typescript
function createObject( loader, elements, elementSize, isConditionalSegments = false, totalElements = null ) {

	// Creates a LineSegments (elementSize = 2) or a Mesh (elementSize = 3 )
	// With per face / segment material, implemented with mesh groups and materials array

	// Sort the faces or line segments by color code to make later the mesh groups
	elements.sort( sortByMaterial );

	if ( totalElements === null ) {

		totalElements = elements.length;

	}

	const positions = new Float32Array( elementSize * totalElements * 3 );
	const normals = elementSize === 3 ? new Float32Array( elementSize * totalElements * 3 ) : null;
	const materials = [];

	const quadArray = new Array( 6 );
	const bufferGeometry = new BufferGeometry();
	let prevMaterial = null;
	let index0 = 0;
	let numGroupVerts = 0;
	let offset = 0;

	for ( let iElem = 0, nElem = elements.length; iElem < nElem; iElem ++ ) {

		const elem = elements[ iElem ];
		let vertices = elem.vertices;
		if ( vertices.length === 4 ) {

			quadArray[ 0 ] = vertices[ 0 ];
			quadArray[ 1 ] = vertices[ 1 ];
			quadArray[ 2 ] = vertices[ 2 ];
			quadArray[ 3 ] = vertices[ 0 ];
			quadArray[ 4 ] = vertices[ 2 ];
			quadArray[ 5 ] = vertices[ 3 ];
			vertices = quadArray;

		}

		for ( let j = 0, l = vertices.length; j < l; j ++ ) {

			const v = vertices[ j ];
			const index = offset + j * 3;
			positions[ index + 0 ] = v.x;
			positions[ index + 1 ] = v.y;
			positions[ index + 2 ] = v.z;

		}

		// create the normals array if this is a set of faces
		if ( elementSize === 3 ) {

			if ( ! elem.faceNormal ) {

				const v0 = vertices[ 0 ];
				const v1 = vertices[ 1 ];
				const v2 = vertices[ 2 ];
				_tempVec0.subVectors( v1, v0 );
				_tempVec1.subVectors( v2, v1 );
				elem.faceNormal = new Vector3()
					.crossVectors( _tempVec0, _tempVec1 )
					.normalize();

			}

			let elemNormals = elem.normals;
			if ( elemNormals.length === 4 ) {

				quadArray[ 0 ] = elemNormals[ 0 ];
				quadArray[ 1 ] = elemNormals[ 1 ];
				quadArray[ 2 ] = elemNormals[ 2 ];
				quadArray[ 3 ] = elemNormals[ 0 ];
				quadArray[ 4 ] = elemNormals[ 2 ];
				quadArray[ 5 ] = elemNormals[ 3 ];
				elemNormals = quadArray;

			}

			for ( let j = 0, l = elemNormals.length; j < l; j ++ ) {

				// use face normal if a vertex normal is not provided
				let n = elem.faceNormal;
				if ( elemNormals[ j ] ) {

					n = elemNormals[ j ].norm;

				}

				const index = offset + j * 3;
				normals[ index + 0 ] = n.x;
				normals[ index + 1 ] = n.y;
				normals[ index + 2 ] = n.z;

			}

		}

		if ( prevMaterial !== elem.colorCode ) {

			if ( prevMaterial !== null ) {

				bufferGeometry.addGroup( index0, numGroupVerts, materials.length - 1 );

			}

			const material = elem.material;

			if ( material !== null ) {

				if ( elementSize === 3 ) {

					materials.push( material );

				} else if ( elementSize === 2 ) {

					if ( isConditionalSegments ) {

						const edgeMaterial = loader.edgeMaterialCache.get( material );

						materials.push( loader.conditionalEdgeMaterialCache.get( edgeMaterial ) );

					} else {

						materials.push( loader.edgeMaterialCache.get( material ) );

					}

				}

			} else {

				// If a material has not been made available yet then keep the color code string in the material array
				// to save the spot for the material once a parent scopes materials are being applied to the object.
				materials.push( elem.colorCode );

			}

			prevMaterial = elem.colorCode;
			index0 = offset / 3;
			numGroupVerts = vertices.length;

		} else {

			numGroupVerts += vertices.length;

		}

		offset += 3 * vertices.length;

	}

	if ( numGroupVerts > 0 ) {

		bufferGeometry.addGroup( index0, Infinity, materials.length - 1 );

	}

	bufferGeometry.setAttribute( 'position', new BufferAttribute( positions, 3 ) );

	if ( normals !== null ) {

		bufferGeometry.setAttribute( 'normal', new BufferAttribute( normals, 3 ) );

	}

	let object3d = null;

	if ( elementSize === 2 ) {

		if ( isConditionalSegments ) {

			object3d = new ConditionalLineSegments( bufferGeometry, materials.length === 1 ? materials[ 0 ] : materials );

		} else {

			object3d = new LineSegments( bufferGeometry, materials.length === 1 ? materials[ 0 ] : materials );

		}

	} else if ( elementSize === 3 ) {

		object3d = new Mesh( bufferGeometry, materials.length === 1 ? materials[ 0 ] : materials );

	}

	if ( isConditionalSegments ) {

		object3d.isConditionalLine = true;

		const controlArray0 = new Float32Array( elements.length * 3 * 2 );
		const controlArray1 = new Float32Array( elements.length * 3 * 2 );
		const directionArray = new Float32Array( elements.length * 3 * 2 );
		for ( let i = 0, l = elements.length; i < l; i ++ ) {

			const os = elements[ i ];
			const vertices = os.vertices;
			const controlPoints = os.controlPoints;
			const c0 = controlPoints[ 0 ];
			const c1 = controlPoints[ 1 ];
			const v0 = vertices[ 0 ];
			const v1 = vertices[ 1 ];
			const index = i * 3 * 2;
			controlArray0[ index + 0 ] = c0.x;
			controlArray0[ index + 1 ] = c0.y;
			controlArray0[ index + 2 ] = c0.z;
			controlArray0[ index + 3 ] = c0.x;
			controlArray0[ index + 4 ] = c0.y;
			controlArray0[ index + 5 ] = c0.z;

			controlArray1[ index + 0 ] = c1.x;
			controlArray1[ index + 1 ] = c1.y;
			controlArray1[ index + 2 ] = c1.z;
			controlArray1[ index + 3 ] = c1.x;
			controlArray1[ index + 4 ] = c1.y;
			controlArray1[ index + 5 ] = c1.z;

			directionArray[ index + 0 ] = v1.x - v0.x;
			directionArray[ index + 1 ] = v1.y - v0.y;
			directionArray[ index + 2 ] = v1.z - v0.z;
			directionArray[ index + 3 ] = v1.x - v0.x;
			directionArray[ index + 4 ] = v1.y - v0.y;
			directionArray[ index + 5 ] = v1.z - v0.z;

		}

		bufferGeometry.setAttribute( 'control0', new BufferAttribute( controlArray0, 3, false ) );
		bufferGeometry.setAttribute( 'control1', new BufferAttribute( controlArray1, 3, false ) );
		bufferGeometry.setAttribute( 'direction', new BufferAttribute( directionArray, 3, false ) );

	}

	return object3d;

}
```
</details>

### `LDrawLoader.setPartsLibraryPath(path: string): LDrawLoader`

**JSDoc:**
```typescript
/**
	 * This method must be called prior to `load()` unless the model to load does not reference
	 * library parts (usually it will be a model with all its parts packed in a single file).
	 *
	 * @param {string} path - Path to library parts files to load referenced parts from.
	 * This is different from Loader.setPath, which indicates the path to load the main asset from.
	 * @return {LDrawLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`path`** `string`

**Returns:** `LDrawLoader`

<details><summary>Code</summary>

```typescript
setPartsLibraryPath( path ) {

		this.partsLibraryPath = path;
		return this;

	}
```
</details>

### `LDrawLoader.setConditionalLineMaterial(type: any): LDrawLoader`

**JSDoc:**
```typescript
/**
	 * Sets the conditional line material type which depends on the used renderer.
	 * Use {@link LDrawConditionalLineMaterial} when using `WebGLRenderer` and
	 * {@link LDrawConditionalLineNodeMaterial} when using `WebGPURenderer`.
	 *
	 * @param {(LDrawConditionalLineMaterial.constructor|LDrawConditionalLineNodeMaterial.constructor)} type - The conditional line material type.
	 * @return {LDrawLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`type`** `any`

**Returns:** `LDrawLoader`

<details><summary>Code</summary>

```typescript
setConditionalLineMaterial( type ) {

		this.ConditionalLineMaterial = type;
		this.missingConditionalEdgeColorMaterial = new this.ConditionalLineMaterial( { name: Loader.DEFAULT_MATERIAL_NAME, fog: true, color: 0xFF00FF } );
		return this;

	}
```
</details>

### `LDrawLoader.preloadMaterials(url: string): Promise<any>`

**JSDoc:**
```typescript
/**
	 * This async method preloads materials from a single LDraw file. In the official
	 * parts library there is a special file which is loaded always the first (LDConfig.ldr)
	 * and contains all the standard color codes. This method is intended to be used with
	 * not packed files, for example in an editor where materials are preloaded and parts
	 * are loaded on demand.
	 *
	 * @async
	 * @param {string} url - Path of the LDraw materials asset.
	 * @return {Promise} A Promise that resolves when the preload has finished.
	 */
```

**Parameters:**

- **`url`** `string`

**Returns:** `Promise<any>`

**Calls:**

- `fileLoader.setPath`
- `fileLoader.setRequestHeader`
- `fileLoader.setWithCredentials`
- `fileLoader.loadAsync`
- `text.split`
- `colorLineRegex.test`
- `line.replace`
- `this.parseColorMetaDirective`
- `materials.push`
- `this.addMaterials`

<details><summary>Code</summary>

```typescript
async preloadMaterials( url ) {

		const fileLoader = new FileLoader( this.manager );
		fileLoader.setPath( this.path );
		fileLoader.setRequestHeader( this.requestHeader );
		fileLoader.setWithCredentials( this.withCredentials );

		const text = await fileLoader.loadAsync( url );
		const colorLineRegex = /^0 !COLOUR/;
		const lines = text.split( /[\n\r]/g );
		const materials = [];
		for ( let i = 0, l = lines.length; i < l; i ++ ) {

			const line = lines[ i ];
			if ( colorLineRegex.test( line ) ) {

				const directive = line.replace( colorLineRegex, '' );
				const material = this.parseColorMetaDirective( new LineParser( directive ) );
				materials.push( material );

			}

		}

		this.addMaterials( materials );

	}
```
</details>

### `LDrawLoader.load(url: string, onLoad: (arg0: Group) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Starts loading from the given URL and passes the loaded LDraw asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Group)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`url`** `string`
- **`onLoad`** `(arg0: Group) => any`
- **`onProgress`** `onProgressCallback`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `fileLoader.setPath`
- `fileLoader.setRequestHeader`
- `fileLoader.setWithCredentials`
- `fileLoader.load`
- `this.addDefaultMaterials`
- `this.partsCache
				.parseModel( text )
				.then( group => {

					this.applyMaterialsToMesh( group, MAIN_COLOUR_CODE, this.materialLibrary, true );
					this.computeBuildingSteps( group );
					group.userData.fileName = url;
					onLoad( group );

				} )
				.catch`

**Internal Comments:**
```
// Initializes the materials library with default materials (x4)
```

<details><summary>Code</summary>

```typescript
load( url, onLoad, onProgress, onError ) {

		const fileLoader = new FileLoader( this.manager );
		fileLoader.setPath( this.path );
		fileLoader.setRequestHeader( this.requestHeader );
		fileLoader.setWithCredentials( this.withCredentials );
		fileLoader.load( url, text => {

			// Initializes the materials library with default materials
			this.addDefaultMaterials();

			this.partsCache
				.parseModel( text )
				.then( group => {

					this.applyMaterialsToMesh( group, MAIN_COLOUR_CODE, this.materialLibrary, true );
					this.computeBuildingSteps( group );
					group.userData.fileName = url;
					onLoad( group );

				} )
				.catch( onError );

		}, onProgress, onError );

	}
```
</details>

### `LDrawLoader.parse(text: string, onLoad: (arg0: Group) => any, onError: onErrorCallback): void`

**JSDoc:**
```typescript
/**
	 * Parses the given LDraw data and returns the resulting group.
	 *
	 * @param {string} text - The raw VRML data as a string.
	 * @param {function(Group)} onLoad - Executed when the loading/parsing process has been finished.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
```

**Parameters:**

- **`text`** `string`
- **`onLoad`** `(arg0: Group) => any`
- **`onError`** `onErrorCallback`

**Returns:** `void`

**Calls:**

- `this.partsCache
			.parseModel( text )
			.then( group => {

				this.applyMaterialsToMesh( group, MAIN_COLOUR_CODE, this.materialLibrary, true );
				this.computeBuildingSteps( group );
				group.userData.fileName = '';
				onLoad( group );

			} )
			.catch`

<details><summary>Code</summary>

```typescript
parse( text, onLoad, onError ) {

		this.partsCache
			.parseModel( text )
			.then( group => {

				this.applyMaterialsToMesh( group, MAIN_COLOUR_CODE, this.materialLibrary, true );
				this.computeBuildingSteps( group );
				group.userData.fileName = '';
				onLoad( group );

			} )
			.catch( onError );

	}
```
</details>

### `LDrawLoader.setMaterials(materials: Material[]): LDrawLoader`

**JSDoc:**
```typescript
/**
	 * Sets the loader's material library. This method clears existing
	 * material definitions.
	 *
	 * @param {Array<Material>} materials - The materials to set.
	 * @return {LDrawLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`materials`** `Material[]`

**Returns:** `LDrawLoader`

**Calls:**

- `this.clearMaterials`
- `this.addMaterials`

<details><summary>Code</summary>

```typescript
setMaterials( materials ) {

		this.clearMaterials();
		this.addMaterials( materials );

		return this;

	}
```
</details>

### `LDrawLoader.clearMaterials(): LDrawLoader`

**JSDoc:**
```typescript
/**
	 * Clears the loader's material library.
	 *
	 * @return {LDrawLoader} A reference to this loader.
	 */
```

**Returns:** `LDrawLoader`

<details><summary>Code</summary>

```typescript
clearMaterials() {

		this.materialLibrary = {};
		this.materials = [];

		return this;

	}
```
</details>

### `LDrawLoader.addMaterials(materials: Material[]): LDrawLoader`

**JSDoc:**
```typescript
/**
	 * Adds a list of materials to the loader's material library.
	 *
	 * @param {Array<Material>} materials - The materials to add.
	 * @return {LDrawLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`materials`** `Material[]`

**Returns:** `LDrawLoader`

**Calls:**

- `this.addMaterial`

<details><summary>Code</summary>

```typescript
addMaterials( materials ) {

		for ( let i = 0, l = materials.length; i < l; i ++ ) {

			this.addMaterial( materials[ i ] );

		}

		return this;

	}
```
</details>

### `LDrawLoader.addDefaultMaterials(): LDrawLoader`

**JSDoc:**
```typescript
/**
	 * Initializes the loader with default materials.
	 *
	 * @return {LDrawLoader} A reference to this loader.
	 */
```

**Returns:** `LDrawLoader`

**Calls:**

- `this.addMaterial`
- `this.parseColorMetaDirective`

**Internal Comments:**
```
// Add default main triangle and line edge materials (used in pieces that can be colored with a main color) (x4)
```

<details><summary>Code</summary>

```typescript
addDefaultMaterials() {

		// Add default main triangle and line edge materials (used in pieces that can be colored with a main color)
		this.addMaterial( this.parseColorMetaDirective( new LineParser( 'Main_Colour CODE 16 VALUE #FF8080 EDGE #333333' ) ) );
		this.addMaterial( this.parseColorMetaDirective( new LineParser( 'Edge_Colour CODE 24 VALUE #A0A0A0 EDGE #333333' ) ) );

		return this;

	}
```
</details>

### `LDrawLoader.setFileMap(fileMap: { [x: string]: string; }): LDrawLoader`

**JSDoc:**
```typescript
/**
	 * Sets a map which maps referenced library filenames to new filenames.
	 * If a fileMap is not specified (the default), library parts will be accessed by trial and
	 * error in subfolders 'parts', 'p' and 'models'.
	 *
	 * @param {Object<string,string>} fileMap - The file map to set.
	 * @return {LDrawLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`fileMap`** `{ [x: string]: string; }`

**Returns:** `LDrawLoader`

<details><summary>Code</summary>

```typescript
setFileMap( fileMap ) {

		this.fileMap = fileMap;

		return this;

	}
```
</details>

### `LDrawLoader.addMaterial(material: Material): LDrawLoader`

**JSDoc:**
```typescript
/**
	 * Adds a single material to the loader's material library.
	 *
	 * @param {Material} material - The material to add.
	 * @return {LDrawLoader} A reference to this loader.
	 */
```

**Parameters:**

- **`material`** `Material`

**Returns:** `LDrawLoader`

**Calls:**

- `this.materials.push`

**Internal Comments:**
```
// Adds a material to the material library which is on top of the parse scopes stack. And also to the materials array (x2)
```

<details><summary>Code</summary>

```typescript
addMaterial( material ) {

		// Adds a material to the material library which is on top of the parse scopes stack. And also to the materials array

		const matLib = this.materialLibrary;
		if ( ! matLib[ material.userData.code ] ) {

			this.materials.push( material );
			matLib[ material.userData.code ] = material;

		}

		return this;

	}
```
</details>

### `LDrawLoader.getMaterial(colorCode: string): Material`

**JSDoc:**
```typescript
/**
	 * Returns a material for the given color code.
	 *
	 * @param {string} colorCode - The color code.
	 * @return {?Material} The material. Returns `null` if no material has been found.
	 */
```

**Parameters:**

- **`colorCode`** `string`

**Returns:** `Material`

**Calls:**

- `colorCode.startsWith`
- `colorCode.substring`
- `this.parseColorMetaDirective`

**Internal Comments:**
```
// Special 'direct' material value (RGB color) (x2)
```

<details><summary>Code</summary>

```typescript
getMaterial( colorCode ) {

		if ( colorCode.startsWith( '0x2' ) ) {

			// Special 'direct' material value (RGB color)
			const color = colorCode.substring( 3 );

			return this.parseColorMetaDirective( new LineParser( 'Direct_Color_' + color + ' CODE -1 VALUE #' + color + ' EDGE #' + color + '' ) );

		}

		return this.materialLibrary[ colorCode ] || null;

	}
```
</details>

### `LDrawLoader.applyMaterialsToMesh(group: any, parentColorCode: any, materialHierarchy: any, finalMaterialPass: boolean): void`

**Parameters:**

- **`group`** `any`
- **`parentColorCode`** `any`
- **`materialHierarchy`** `any`
- **`finalMaterialPass`** `boolean`

**Returns:** `void`

**Calls:**

- `group.traverse`
- `Array.isArray`
- `getMaterial`
- `loader.getMaterial`
- `console.warn`
- `loader.edgeMaterialCache.get`
- `loader.conditionalEdgeMaterialCache.get`

**Internal Comments:**
```
// find any missing materials as indicated by a color code string and replace it with a material from the current material lib (x2)
// Returns the appropriate material for the object (line or face) given color code. If the code is "pass through"
// (24 for lines, 16 for edges) then the pass through color code is used. If that is also pass through then it's
// simply returned for the subsequent material application.
// if our parent is a passthrough color code and we don't have the current material color available then
// return early.
// see if we can get the final material from the "getMaterial" function which will attempt to (x3)
// parse the "direct" colors (x3)
// otherwise throw a warning if this is final opportunity to set the material (x4)
// And return the 'missing color' material (x3)
```

<details><summary>Code</summary>

```typescript
applyMaterialsToMesh( group, parentColorCode, materialHierarchy, finalMaterialPass = false ) {

		// find any missing materials as indicated by a color code string and replace it with a material from the current material lib
		const loader = this;
		const parentIsPassthrough = parentColorCode === MAIN_COLOUR_CODE;
		group.traverse( c => {

			if ( c.isMesh || c.isLineSegments ) {

				if ( Array.isArray( c.material ) ) {

					for ( let i = 0, l = c.material.length; i < l; i ++ ) {

						if ( ! c.material[ i ].isMaterial ) {

							c.material[ i ] = getMaterial( c, c.material[ i ] );

						}

					}

				} else if ( ! c.material.isMaterial ) {

					c.material = getMaterial( c, c.material );

				}

			}

		} );


		// Returns the appropriate material for the object (line or face) given color code. If the code is "pass through"
		// (24 for lines, 16 for edges) then the pass through color code is used. If that is also pass through then it's
		// simply returned for the subsequent material application.
		function getMaterial( c, colorCode ) {

			// if our parent is a passthrough color code and we don't have the current material color available then
			// return early.
			if ( parentIsPassthrough && ! ( colorCode in materialHierarchy ) && ! finalMaterialPass ) {

				return colorCode;

			}

			const forEdge = c.isLineSegments || c.isConditionalLine;
			const isPassthrough = ! forEdge && colorCode === MAIN_COLOUR_CODE || forEdge && colorCode === MAIN_EDGE_COLOUR_CODE;
			if ( isPassthrough ) {

				colorCode = parentColorCode;

			}

			let material = null;
			if ( colorCode in materialHierarchy ) {

				material = materialHierarchy[ colorCode ];

			} else if ( finalMaterialPass ) {

				// see if we can get the final material from the "getMaterial" function which will attempt to
				// parse the "direct" colors
				material = loader.getMaterial( colorCode );
				if ( material === null ) {

					// otherwise throw a warning if this is final opportunity to set the material
					console.warn( `LDrawLoader: Material properties for code ${ colorCode } not available.` );

					// And return the 'missing color' material
					material = loader.missingColorMaterial;

				}


			} else {

				return colorCode;

			}

			if ( c.isLineSegments ) {

				material = loader.edgeMaterialCache.get( material );

				if ( c.isConditionalLine ) {

					material = loader.conditionalEdgeMaterialCache.get( material );

				}

			}

			return material;

		}

	}
```
</details>

### `LDrawLoader.getMainMaterial(): Material`

**JSDoc:**
```typescript
/**
	 * Returns the Material for the main LDraw color.
	 *
	 * For an already loaded LDraw asset, returns the Material associated with the main color code.
	 * This method can be useful to modify the main material of a model or part that exposes it.
	 *
	 * The main color code is the standard way to color an LDraw part. It is '16' for triangles and
	 * '24' for edges. Usually a complete model will not expose the main color (that is, no part
	 * uses the code '16' at the top level, because they are assigned other specific colors) An LDraw
	 *  part file on the other hand will expose the code '16' to be colored, and can have additional
	 * fixed colors.
	 *
	 * @return {?Material} The material. Returns `null` if no material has been found.
	 */
```

**Returns:** `Material`

**Calls:**

- `this.getMaterial`

<details><summary>Code</summary>

```typescript
getMainMaterial() {

		return this.getMaterial( MAIN_COLOUR_CODE );

	}
```
</details>

### `LDrawLoader.getMainEdgeMaterial(): Material`

**JSDoc:**
```typescript
/**
	 * Returns the material for the edges main LDraw color.
	 *
	 * @return {?Material} The material. Returns `null` if no material has been found.
	 */
```

**Returns:** `Material`

**Calls:**

- `this.getMaterial`
- `this.edgeMaterialCache.get`

<details><summary>Code</summary>

```typescript
getMainEdgeMaterial() {

		const mat = this.getMaterial( MAIN_EDGE_COLOUR_CODE );
		return mat ? this.edgeMaterialCache.get( mat ) : null;

	}
```
</details>

### `LDrawLoader.parseColorMetaDirective(lineParser: any): any`

**Parameters:**

- **`lineParser`** `any`

**Returns:** `any`

**Calls:**

- `lineParser.getToken`
- `lineParser.getLineNumberString`
- `parseLuminance`
- `token.toUpperCase`
- `fillColor.startsWith`
- `fillColor.substring`
- `edgeColor.startsWith`
- `edgeColor.substring`
- `this.getMaterial`
- `this.edgeMaterialCache.get`
- `parseInt`
- `isNaN`
- `Math.max`
- `Math.min`
- `lineParser.setToEnd`
- `material.color.setStyle`
- `material.emissive.setStyle( fillColor, COLOR_SPACE_LDRAW ).multiplyScalar`
- `new Color().setStyle`
- `this.conditionalEdgeMaterialCache.set`
- `this.edgeMaterialCache.set`
- `this.addMaterial`
- `token.startsWith`
- `token.substring`

**Internal Comments:**
```
// Parses a color definition and returns a THREE.Material (x2)
// Triangle and line colors (x2)
// Transparency (x2)
// Self-illumination: (x2)
// Parse tag tokens and their parameters (x2)
// Try to see if edge color is a color code (x3)
// Get the edge material for this triangle material (x3)
// Not implemented (x4)
// Try to imitate pearlescency by making the surface glossy (x3)
// Mirror finish surface (x3)
// Rubber finish (x3)
// Brushed metal finish (x3)
// Average metal finish (x3)
// Should not happen
// This is the material used for edges (x3)
// This is the material used for conditional edges (x2)
// Returns success (x2)
```

<details><summary>Code</summary>

```typescript
parseColorMetaDirective( lineParser ) {

		// Parses a color definition and returns a THREE.Material

		let code = null;

		// Triangle and line colors
		let fillColor = '#FF00FF';
		let edgeColor = '#FF00FF';

		// Transparency
		let alpha = 1;
		let isTransparent = false;
		// Self-illumination:
		let luminance = 0;

		let finishType = FINISH_TYPE_DEFAULT;

		let edgeMaterial = null;

		const name = lineParser.getToken();
		if ( ! name ) {

			throw new Error( 'LDrawLoader: Material name was expected after "!COLOUR tag' + lineParser.getLineNumberString() + '.' );

		}

		// Parse tag tokens and their parameters
		let token = null;
		while ( true ) {

			token = lineParser.getToken();

			if ( ! token ) {

				break;

			}

			if ( ! parseLuminance( token ) ) {

				switch ( token.toUpperCase() ) {

					case 'CODE':

						code = lineParser.getToken();
						break;

					case 'VALUE':

						fillColor = lineParser.getToken();
						if ( fillColor.startsWith( '0x' ) ) {

							fillColor = '#' + fillColor.substring( 2 );

						} else if ( ! fillColor.startsWith( '#' ) ) {

							throw new Error( 'LDrawLoader: Invalid color while parsing material' + lineParser.getLineNumberString() + '.' );

						}

						break;

					case 'EDGE':

						edgeColor = lineParser.getToken();
						if ( edgeColor.startsWith( '0x' ) ) {

							edgeColor = '#' + edgeColor.substring( 2 );

						} else if ( ! edgeColor.startsWith( '#' ) ) {

							// Try to see if edge color is a color code
							edgeMaterial = this.getMaterial( edgeColor );
							if ( ! edgeMaterial ) {

								throw new Error( 'LDrawLoader: Invalid edge color while parsing material' + lineParser.getLineNumberString() + '.' );

							}

							// Get the edge material for this triangle material
							edgeMaterial = this.edgeMaterialCache.get( edgeMaterial );

						}

						break;

					case 'ALPHA':

						alpha = parseInt( lineParser.getToken() );

						if ( isNaN( alpha ) ) {

							throw new Error( 'LDrawLoader: Invalid alpha value in material definition' + lineParser.getLineNumberString() + '.' );

						}

						alpha = Math.max( 0, Math.min( 1, alpha / 255 ) );

						if ( alpha < 1 ) {

							isTransparent = true;

						}

						break;

					case 'LUMINANCE':

						if ( ! parseLuminance( lineParser.getToken() ) ) {

							throw new Error( 'LDrawLoader: Invalid luminance value in material definition' + lineParser.getLineNumberString() + '.' );

						}

						break;

					case 'CHROME':
						finishType = FINISH_TYPE_CHROME;
						break;

					case 'PEARLESCENT':
						finishType = FINISH_TYPE_PEARLESCENT;
						break;

					case 'RUBBER':
						finishType = FINISH_TYPE_RUBBER;
						break;

					case 'MATTE_METALLIC':
						finishType = FINISH_TYPE_MATTE_METALLIC;
						break;

					case 'METAL':
						finishType = FINISH_TYPE_METAL;
						break;

					case 'MATERIAL':
						// Not implemented
						lineParser.setToEnd();
						break;

					default:
						throw new Error( 'LDrawLoader: Unknown token "' + token + '" while parsing material' + lineParser.getLineNumberString() + '.' );

				}

			}

		}

		let material = null;

		switch ( finishType ) {

			case FINISH_TYPE_DEFAULT:

				material = new MeshStandardMaterial( { roughness: 0.3, metalness: 0 } );
				break;

			case FINISH_TYPE_PEARLESCENT:

				// Try to imitate pearlescency by making the surface glossy
				material = new MeshStandardMaterial( { roughness: 0.3, metalness: 0.25 } );
				break;

			case FINISH_TYPE_CHROME:

				// Mirror finish surface
				material = new MeshStandardMaterial( { roughness: 0, metalness: 1 } );
				break;

			case FINISH_TYPE_RUBBER:

				// Rubber finish
				material = new MeshStandardMaterial( { roughness: 0.9, metalness: 0 } );
				break;

			case FINISH_TYPE_MATTE_METALLIC:

				// Brushed metal finish
				material = new MeshStandardMaterial( { roughness: 0.8, metalness: 0.4 } );
				break;

			case FINISH_TYPE_METAL:

				// Average metal finish
				material = new MeshStandardMaterial( { roughness: 0.2, metalness: 0.85 } );
				break;

			default:
				// Should not happen
				break;

		}

		material.color.setStyle( fillColor, COLOR_SPACE_LDRAW );
		material.transparent = isTransparent;
		material.premultipliedAlpha = true;
		material.opacity = alpha;
		material.depthWrite = ! isTransparent;

		material.polygonOffset = true;
		material.polygonOffsetFactor = 1;

		if ( luminance !== 0 ) {

			material.emissive.setStyle( fillColor, COLOR_SPACE_LDRAW ).multiplyScalar( luminance );

		}

		if ( ! edgeMaterial ) {

			// This is the material used for edges
			edgeMaterial = new LineBasicMaterial( {
				color: new Color().setStyle( edgeColor, COLOR_SPACE_LDRAW ),
				transparent: isTransparent,
				opacity: alpha,
				depthWrite: ! isTransparent
			} );
			edgeMaterial.color;
			edgeMaterial.userData.code = code;
			edgeMaterial.name = name + ' - Edge';

			if ( this.ConditionalLineMaterial === null ) {

				throw new Error( 'THREE.LDrawLoader: ConditionalLineMaterial type must be specified via .setConditionalLineMaterial().' );

			}

			// This is the material used for conditional edges
			const conditionalEdgeMaterial = new this.ConditionalLineMaterial( {

				fog: true,
				transparent: isTransparent,
				depthWrite: ! isTransparent,
				color: new Color().setStyle( edgeColor, COLOR_SPACE_LDRAW ),
				opacity: alpha,

			} );
			conditionalEdgeMaterial.userData.code = code;
			conditionalEdgeMaterial.name = name + ' - Conditional Edge';

			this.conditionalEdgeMaterialCache.set( edgeMaterial, conditionalEdgeMaterial );

		}

		material.userData.code = code;
		material.name = name;

		this.edgeMaterialCache.set( material, edgeMaterial );

		this.addMaterial( material );

		return material;

		function parseLuminance( token ) {

			// Returns success

			let lum;

			if ( token.startsWith( 'LUMINANCE' ) ) {

				lum = parseInt( token.substring( 9 ) );

			} else {

				lum = parseInt( token );

			}

			if ( isNaN( lum ) ) {

				return false;

			}

			luminance = Math.max( 0, Math.min( 1, lum / 255 ) );

			return true;

		}

	}
```
</details>

### `LDrawLoader.computeBuildingSteps(model: any): void`

**Parameters:**

- **`model`** `any`

**Returns:** `void`

**Calls:**

- `model.traverse`

**Internal Comments:**
```
// Sets userdata.buildingStep number in Group objects and userData.numBuildingSteps number in the root Group object. (x2)
```

<details><summary>Code</summary>

```typescript
computeBuildingSteps( model ) {

		// Sets userdata.buildingStep number in Group objects and userData.numBuildingSteps number in the root Group object.

		let stepNumber = 0;

		model.traverse( c => {

			if ( c.isGroup ) {

				if ( c.userData.startingBuildingStep ) {

					stepNumber ++;

				}

				c.userData.buildingStep = stepNumber;

			}

		} );

		model.userData.numBuildingSteps = stepNumber + 1;

	}
```
</details>

### `getMaterial(c: any, colorCode: any): any`

**Parameters:**

- **`c`** `any`
- **`colorCode`** `any`

**Returns:** `any`

**Calls:**

- `loader.getMaterial`
- `console.warn`
- `loader.edgeMaterialCache.get`
- `loader.conditionalEdgeMaterialCache.get`

**Internal Comments:**
```
// if our parent is a passthrough color code and we don't have the current material color available then
// return early.
// see if we can get the final material from the "getMaterial" function which will attempt to (x3)
// parse the "direct" colors (x3)
// otherwise throw a warning if this is final opportunity to set the material (x4)
// And return the 'missing color' material (x3)
```

<details><summary>Code</summary>

```typescript
function getMaterial( c, colorCode ) {

			// if our parent is a passthrough color code and we don't have the current material color available then
			// return early.
			if ( parentIsPassthrough && ! ( colorCode in materialHierarchy ) && ! finalMaterialPass ) {

				return colorCode;

			}

			const forEdge = c.isLineSegments || c.isConditionalLine;
			const isPassthrough = ! forEdge && colorCode === MAIN_COLOUR_CODE || forEdge && colorCode === MAIN_EDGE_COLOUR_CODE;
			if ( isPassthrough ) {

				colorCode = parentColorCode;

			}

			let material = null;
			if ( colorCode in materialHierarchy ) {

				material = materialHierarchy[ colorCode ];

			} else if ( finalMaterialPass ) {

				// see if we can get the final material from the "getMaterial" function which will attempt to
				// parse the "direct" colors
				material = loader.getMaterial( colorCode );
				if ( material === null ) {

					// otherwise throw a warning if this is final opportunity to set the material
					console.warn( `LDrawLoader: Material properties for code ${ colorCode } not available.` );

					// And return the 'missing color' material
					material = loader.missingColorMaterial;

				}


			} else {

				return colorCode;

			}

			if ( c.isLineSegments ) {

				material = loader.edgeMaterialCache.get( material );

				if ( c.isConditionalLine ) {

					material = loader.conditionalEdgeMaterialCache.get( material );

				}

			}

			return material;

		}
```
</details>

### `parseLuminance(token: any): boolean`

**Parameters:**

- **`token`** `any`

**Returns:** `boolean`

**Calls:**

- `token.startsWith`
- `parseInt`
- `token.substring`
- `isNaN`
- `Math.max`
- `Math.min`

**Internal Comments:**
```
// Returns success (x2)
```

<details><summary>Code</summary>

```typescript
function parseLuminance( token ) {

			// Returns success

			let lum;

			if ( token.startsWith( 'LUMINANCE' ) ) {

				lum = parseInt( token.substring( 9 ) );

			} else {

				lum = parseInt( token );

			}

			if ( isNaN( lum ) ) {

				return false;

			}

			luminance = Math.max( 0, Math.min( 1, lum / 255 ) );

			return true;

		}
```
</details>


---

## Classes

### `ConditionalLineSegments`

<details><summary>Class Code</summary>

```ts
class ConditionalLineSegments extends LineSegments {

	constructor( geometry, material ) {

		super( geometry, material );
		this.isConditionalLine = true;

	}

}
```
</details>

### `LineParser`

<details><summary>Class Code</summary>

```ts
class LineParser {

	constructor( line, lineNumber ) {

		this.line = line;
		this.lineLength = line.length;
		this.currentCharIndex = 0;
		this.currentChar = ' ';
		this.lineNumber = lineNumber;

	}

	seekNonSpace() {

		while ( this.currentCharIndex < this.lineLength ) {

			this.currentChar = this.line.charAt( this.currentCharIndex );

			if ( this.currentChar !== ' ' && this.currentChar !== '\t' ) {

				return;

			}

			this.currentCharIndex ++;

		}

	}

	getToken() {

		const pos0 = this.currentCharIndex ++;

		// Seek space
		while ( this.currentCharIndex < this.lineLength ) {

			this.currentChar = this.line.charAt( this.currentCharIndex );

			if ( this.currentChar === ' ' || this.currentChar === '\t' ) {

				break;

			}

			this.currentCharIndex ++;

		}

		const pos1 = this.currentCharIndex;

		this.seekNonSpace();

		return this.line.substring( pos0, pos1 );

	}

	getVector() {

		return new Vector3( parseFloat( this.getToken() ), parseFloat( this.getToken() ), parseFloat( this.getToken() ) );

	}

	getRemainingString() {

		return this.line.substring( this.currentCharIndex, this.lineLength );

	}

	isAtTheEnd() {

		return this.currentCharIndex >= this.lineLength;

	}

	setToEnd() {

		this.currentCharIndex = this.lineLength;

	}

	getLineNumberString() {

		return this.lineNumber >= 0 ? ' at line ' + this.lineNumber : '';

	}

}
```
</details>

#### Methods

##### `seekNonSpace(): void`

<details><summary>Code</summary>

```ts
seekNonSpace() {

		while ( this.currentCharIndex < this.lineLength ) {

			this.currentChar = this.line.charAt( this.currentCharIndex );

			if ( this.currentChar !== ' ' && this.currentChar !== '\t' ) {

				return;

			}

			this.currentCharIndex ++;

		}

	}
```
</details>

##### `getToken(): any`

<details><summary>Code</summary>

```ts
getToken() {

		const pos0 = this.currentCharIndex ++;

		// Seek space
		while ( this.currentCharIndex < this.lineLength ) {

			this.currentChar = this.line.charAt( this.currentCharIndex );

			if ( this.currentChar === ' ' || this.currentChar === '\t' ) {

				break;

			}

			this.currentCharIndex ++;

		}

		const pos1 = this.currentCharIndex;

		this.seekNonSpace();

		return this.line.substring( pos0, pos1 );

	}
```
</details>

##### `getVector(): any`

<details><summary>Code</summary>

```ts
getVector() {

		return new Vector3( parseFloat( this.getToken() ), parseFloat( this.getToken() ), parseFloat( this.getToken() ) );

	}
```
</details>

##### `getRemainingString(): any`

<details><summary>Code</summary>

```ts
getRemainingString() {

		return this.line.substring( this.currentCharIndex, this.lineLength );

	}
```
</details>

##### `isAtTheEnd(): boolean`

<details><summary>Code</summary>

```ts
isAtTheEnd() {

		return this.currentCharIndex >= this.lineLength;

	}
```
</details>

##### `setToEnd(): void`

<details><summary>Code</summary>

```ts
setToEnd() {

		this.currentCharIndex = this.lineLength;

	}
```
</details>

##### `getLineNumberString(): string`

<details><summary>Code</summary>

```ts
getLineNumberString() {

		return this.lineNumber >= 0 ? ' at line ' + this.lineNumber : '';

	}
```
</details>

### `LDrawParsedCache`

<details><summary>Class Code</summary>

```ts
class LDrawParsedCache {

	constructor( loader ) {

		this.loader = loader;
		this._cache = {};

	}

	cloneResult( original ) {

		const result = {};

		// vertices are transformed and normals computed before being converted to geometry
		// so these pieces must be cloned.
		result.faces = original.faces.map( face => {

			return {
				colorCode: face.colorCode,
				material: face.material,
				vertices: face.vertices.map( v => v.clone() ),
				normals: face.normals.map( () => null ),
				faceNormal: null
			};

		} );

		result.conditionalSegments = original.conditionalSegments.map( face => {

			return {
				colorCode: face.colorCode,
				material: face.material,
				vertices: face.vertices.map( v => v.clone() ),
				controlPoints: face.controlPoints.map( v => v.clone() )
			};

		} );

		result.lineSegments = original.lineSegments.map( face => {

			return {
				colorCode: face.colorCode,
				material: face.material,
				vertices: face.vertices.map( v => v.clone() )
			};

		} );

		// none if this is subsequently modified
		result.type = original.type;
		result.category = original.category;
		result.keywords = original.keywords;
		result.author = original.author;
		result.subobjects = original.subobjects;
		result.fileName = original.fileName;
		result.totalFaces = original.totalFaces;
		result.startingBuildingStep = original.startingBuildingStep;
		result.materials = original.materials;
		result.group = null;
		return result;

	}

	async fetchData( fileName ) {

		let triedLowerCase = false;
		let locationState = FILE_LOCATION_TRY_PARTS;
		while ( locationState !== FILE_LOCATION_NOT_FOUND ) {

			let subobjectURL = fileName;
			switch ( locationState ) {

				case FILE_LOCATION_AS_IS:
					locationState = locationState + 1;
					break;

				case FILE_LOCATION_TRY_PARTS:
					subobjectURL = 'parts/' + subobjectURL;
					locationState = locationState + 1;
					break;

				case FILE_LOCATION_TRY_P:
					subobjectURL = 'p/' + subobjectURL;
					locationState = locationState + 1;
					break;

				case FILE_LOCATION_TRY_MODELS:
					subobjectURL = 'models/' + subobjectURL;
					locationState = locationState + 1;
					break;

				case FILE_LOCATION_TRY_RELATIVE:
					subobjectURL = fileName.substring( 0, fileName.lastIndexOf( '/' ) + 1 ) + subobjectURL;
					locationState = locationState + 1;
					break;

				case FILE_LOCATION_TRY_ABSOLUTE:

					if ( triedLowerCase ) {

						// Try absolute path
						locationState = FILE_LOCATION_NOT_FOUND;

					} else {

						// Next attempt is lower case
						fileName = fileName.toLowerCase();
						subobjectURL = fileName;
						triedLowerCase = true;
						locationState = FILE_LOCATION_TRY_PARTS;

					}

					break;

			}

			const loader = this.loader;
			const fileLoader = new FileLoader( loader.manager );
			fileLoader.setPath( loader.partsLibraryPath );
			fileLoader.setRequestHeader( loader.requestHeader );
			fileLoader.setWithCredentials( loader.withCredentials );

			try {

				const text = await fileLoader.loadAsync( subobjectURL );
				return text;

			} catch ( _ ) {

				continue;

			}

		}

		throw new Error( 'LDrawLoader: Subobject "' + fileName + '" could not be loaded.' );

	}

	parse( text, fileName = null ) {

		const loader = this.loader;

		// final results
		const faces = [];
		const lineSegments = [];
		const conditionalSegments = [];
		const subobjects = [];
		const materials = {};

		const getLocalMaterial = colorCode => {

			return materials[ colorCode ] || null;

		};

		let type = 'Model';
		let category = null;
		let keywords = null;
		let author = null;
		let totalFaces = 0;

		// split into lines
		if ( text.indexOf( '\r\n' ) !== - 1 ) {

			// This is faster than String.split with regex that splits on both
			text = text.replace( /\r\n/g, '\n' );

		}

		const lines = text.split( '\n' );
		const numLines = lines.length;

		let parsingEmbeddedFiles = false;
		let currentEmbeddedFileName = null;
		let currentEmbeddedText = null;

		let bfcCertified = false;
		let bfcCCW = true;
		let bfcInverted = false;
		let bfcCull = true;

		let startingBuildingStep = false;

		// Parse all line commands
		for ( let lineIndex = 0; lineIndex < numLines; lineIndex ++ ) {

			const line = lines[ lineIndex ];

			if ( line.length === 0 ) continue;

			if ( parsingEmbeddedFiles ) {

				if ( line.startsWith( '0 FILE ' ) ) {

					// Save previous embedded file in the cache
					this.setData( currentEmbeddedFileName, currentEmbeddedText );

					// New embedded text file
					currentEmbeddedFileName = line.substring( 7 );
					currentEmbeddedText = '';

				} else {

					currentEmbeddedText += line + '\n';

				}

				continue;

			}

			const lp = new LineParser( line, lineIndex + 1 );
			lp.seekNonSpace();

			if ( lp.isAtTheEnd() ) {

				// Empty line
				continue;

			}

			// Parse the line type
			const lineType = lp.getToken();

			let material;
			let colorCode;
			let segment;
			let ccw;
			let doubleSided;
			let v0, v1, v2, v3, c0, c1;

			switch ( lineType ) {

				// Line type 0: Comment or META
				case '0':

					// Parse meta directive
					const meta = lp.getToken();

					if ( meta ) {

						switch ( meta ) {

							case '!LDRAW_ORG':

								type = lp.getToken();
								break;

							case '!COLOUR':

								material = loader.parseColorMetaDirective( lp );
								if ( material ) {

									materials[ material.userData.code ] = material;

								}	else {

									console.warn( 'LDrawLoader: Error parsing material' + lp.getLineNumberString() );

								}

								break;

							case '!CATEGORY':

								category = lp.getToken();
								break;

							case '!KEYWORDS':

								const newKeywords = lp.getRemainingString().split( ',' );
								if ( newKeywords.length > 0 ) {

									if ( ! keywords ) {

										keywords = [];

									}

									newKeywords.forEach( function ( keyword ) {

										keywords.push( keyword.trim() );

									} );

								}

								break;

							case 'FILE':

								if ( lineIndex > 0 ) {

									// Start embedded text files parsing
									parsingEmbeddedFiles = true;
									currentEmbeddedFileName = lp.getRemainingString();
									currentEmbeddedText = '';

									bfcCertified = false;
									bfcCCW = true;

								}

								break;

							case 'BFC':

								// Changes to the backface culling state
								while ( ! lp.isAtTheEnd() ) {

									const token = lp.getToken();

									switch ( token ) {

										case 'CERTIFY':
										case 'NOCERTIFY':

											bfcCertified = token === 'CERTIFY';
											bfcCCW = true;

											break;

										case 'CW':
										case 'CCW':

											bfcCCW = token === 'CCW';

											break;

										case 'INVERTNEXT':

											bfcInverted = true;

											break;

										case 'CLIP':
										case 'NOCLIP':

											bfcCull = token === 'CLIP';

											break;

										default:

											console.warn( 'THREE.LDrawLoader: BFC directive "' + token + '" is unknown.' );

											break;

									}

								}

								break;

							case 'STEP':

								startingBuildingStep = true;

								break;

							case 'Author:':

								author = lp.getToken();

								break;

							default:
								// Other meta directives are not implemented
								break;

						}

					}

					break;

					// Line type 1: Sub-object file
				case '1':

					colorCode = lp.getToken();
					material = getLocalMaterial( colorCode );

					const posX = parseFloat( lp.getToken() );
					const posY = parseFloat( lp.getToken() );
					const posZ = parseFloat( lp.getToken() );
					const m0 = parseFloat( lp.getToken() );
					const m1 = parseFloat( lp.getToken() );
					const m2 = parseFloat( lp.getToken() );
					const m3 = parseFloat( lp.getToken() );
					const m4 = parseFloat( lp.getToken() );
					const m5 = parseFloat( lp.getToken() );
					const m6 = parseFloat( lp.getToken() );
					const m7 = parseFloat( lp.getToken() );
					const m8 = parseFloat( lp.getToken() );

					const matrix = new Matrix4().set(
						m0, m1, m2, posX,
						m3, m4, m5, posY,
						m6, m7, m8, posZ,
						0, 0, 0, 1
					);

					let fileName = lp.getRemainingString().trim().replace( /\\/g, '/' );

					if ( loader.fileMap[ fileName ] ) {

						// Found the subobject path in the preloaded file path map
						fileName = loader.fileMap[ fileName ];

					} else {

						// Standardized subfolders
						if ( fileName.startsWith( 's/' ) ) {

							fileName = 'parts/' + fileName;

						} else if ( fileName.startsWith( '48/' ) ) {

							fileName = 'p/' + fileName;

						}

					}

					subobjects.push( {
						material: material,
						colorCode: colorCode,
						matrix: matrix,
						fileName: fileName,
						inverted: bfcInverted,
						startingBuildingStep: startingBuildingStep
					} );

					startingBuildingStep = false;
					bfcInverted = false;

					break;

					// Line type 2: Line segment
				case '2':

					colorCode = lp.getToken();
					material = getLocalMaterial( colorCode );
					v0 = lp.getVector();
					v1 = lp.getVector();

					segment = {
						material: material,
						colorCode: colorCode,
						vertices: [ v0, v1 ],
					};

					lineSegments.push( segment );

					break;

					// Line type 5: Conditional Line segment
				case '5':

					colorCode = lp.getToken();
					material = getLocalMaterial( colorCode );
					v0 = lp.getVector();
					v1 = lp.getVector();
					c0 = lp.getVector();
					c1 = lp.getVector();

					segment = {
						material: material,
						colorCode: colorCode,
						vertices: [ v0, v1 ],
						controlPoints: [ c0, c1 ],
					};

					conditionalSegments.push( segment );

					break;

					// Line type 3: Triangle
				case '3':

					colorCode = lp.getToken();
					material = getLocalMaterial( colorCode );
					ccw = bfcCCW;
					doubleSided = ! bfcCertified || ! bfcCull;

					if ( ccw === true ) {

						v0 = lp.getVector();
						v1 = lp.getVector();
						v2 = lp.getVector();

					} else {

						v2 = lp.getVector();
						v1 = lp.getVector();
						v0 = lp.getVector();

					}

					faces.push( {
						material: material,
						colorCode: colorCode,
						faceNormal: null,
						vertices: [ v0, v1, v2 ],
						normals: [ null, null, null ],
					} );
					totalFaces ++;

					if ( doubleSided === true ) {

						faces.push( {
							material: material,
							colorCode: colorCode,
							faceNormal: null,
							vertices: [ v2, v1, v0 ],
							normals: [ null, null, null ],
						} );
						totalFaces ++;

					}

					break;

					// Line type 4: Quadrilateral
				case '4':

					colorCode = lp.getToken();
					material = getLocalMaterial( colorCode );
					ccw = bfcCCW;
					doubleSided = ! bfcCertified || ! bfcCull;

					if ( ccw === true ) {

						v0 = lp.getVector();
						v1 = lp.getVector();
						v2 = lp.getVector();
						v3 = lp.getVector();

					} else {

						v3 = lp.getVector();
						v2 = lp.getVector();
						v1 = lp.getVector();
						v0 = lp.getVector();

					}

					// specifically place the triangle diagonal in the v0 and v1 slots so we can
					// account for the doubling of vertices later when smoothing normals.
					faces.push( {
						material: material,
						colorCode: colorCode,
						faceNormal: null,
						vertices: [ v0, v1, v2, v3 ],
						normals: [ null, null, null, null ],
					} );
					totalFaces += 2;

					if ( doubleSided === true ) {

						faces.push( {
							material: material,
							colorCode: colorCode,
							faceNormal: null,
							vertices: [ v3, v2, v1, v0 ],
							normals: [ null, null, null, null ],
						} );
						totalFaces += 2;

					}

					break;

				default:
					throw new Error( 'LDrawLoader: Unknown line type "' + lineType + '"' + lp.getLineNumberString() + '.' );

			}

		}

		if ( parsingEmbeddedFiles ) {

			this.setData( currentEmbeddedFileName, currentEmbeddedText );

		}

		return {
			faces,
			conditionalSegments,
			lineSegments,
			type,
			category,
			keywords,
			author,
			subobjects,
			totalFaces,
			startingBuildingStep,
			materials,
			fileName,
			group: null
		};

	}

	// returns an (optionally cloned) instance of the data
	getData( fileName, clone = true ) {

		const key = fileName.toLowerCase();
		const result = this._cache[ key ];
		if ( result === null || result instanceof Promise ) {

			return null;

		}

		if ( clone ) {

			return this.cloneResult( result );

		} else {

			return result;

		}

	}

	// kicks off a fetch and parse of the requested data if it hasn't already been loaded. Returns when
	// the data is ready to use and can be retrieved synchronously with "getData".
	async ensureDataLoaded( fileName ) {

		const key = fileName.toLowerCase();
		if ( ! ( key in this._cache ) ) {

			// replace the promise with a copy of the parsed data for immediate processing
			this._cache[ key ] = this.fetchData( fileName ).then( text => {

				const info = this.parse( text, fileName );
				this._cache[ key ] = info;
				return info;

			} );

		}

		await this._cache[ key ];

	}

	// sets the data in the cache from parsed data
	setData( fileName, text ) {

		const key = fileName.toLowerCase();
		this._cache[ key ] = this.parse( text, fileName );

	}

}
```
</details>

#### Methods

##### `cloneResult(original: any): { faces: any; conditionalSegments: any; lineSegments: any; type: any; category: any; keywords: any; author: any; subobjects: any; fileName: any; totalFaces: any; startingBuildingStep: any; materials: any; group: any; }`

<details><summary>Code</summary>

```ts
cloneResult( original ) {

		const result = {};

		// vertices are transformed and normals computed before being converted to geometry
		// so these pieces must be cloned.
		result.faces = original.faces.map( face => {

			return {
				colorCode: face.colorCode,
				material: face.material,
				vertices: face.vertices.map( v => v.clone() ),
				normals: face.normals.map( () => null ),
				faceNormal: null
			};

		} );

		result.conditionalSegments = original.conditionalSegments.map( face => {

			return {
				colorCode: face.colorCode,
				material: face.material,
				vertices: face.vertices.map( v => v.clone() ),
				controlPoints: face.controlPoints.map( v => v.clone() )
			};

		} );

		result.lineSegments = original.lineSegments.map( face => {

			return {
				colorCode: face.colorCode,
				material: face.material,
				vertices: face.vertices.map( v => v.clone() )
			};

		} );

		// none if this is subsequently modified
		result.type = original.type;
		result.category = original.category;
		result.keywords = original.keywords;
		result.author = original.author;
		result.subobjects = original.subobjects;
		result.fileName = original.fileName;
		result.totalFaces = original.totalFaces;
		result.startingBuildingStep = original.startingBuildingStep;
		result.materials = original.materials;
		result.group = null;
		return result;

	}
```
</details>

##### `fetchData(fileName: any): Promise<any>`

<details><summary>Code</summary>

```ts
async fetchData( fileName ) {

		let triedLowerCase = false;
		let locationState = FILE_LOCATION_TRY_PARTS;
		while ( locationState !== FILE_LOCATION_NOT_FOUND ) {

			let subobjectURL = fileName;
			switch ( locationState ) {

				case FILE_LOCATION_AS_IS:
					locationState = locationState + 1;
					break;

				case FILE_LOCATION_TRY_PARTS:
					subobjectURL = 'parts/' + subobjectURL;
					locationState = locationState + 1;
					break;

				case FILE_LOCATION_TRY_P:
					subobjectURL = 'p/' + subobjectURL;
					locationState = locationState + 1;
					break;

				case FILE_LOCATION_TRY_MODELS:
					subobjectURL = 'models/' + subobjectURL;
					locationState = locationState + 1;
					break;

				case FILE_LOCATION_TRY_RELATIVE:
					subobjectURL = fileName.substring( 0, fileName.lastIndexOf( '/' ) + 1 ) + subobjectURL;
					locationState = locationState + 1;
					break;

				case FILE_LOCATION_TRY_ABSOLUTE:

					if ( triedLowerCase ) {

						// Try absolute path
						locationState = FILE_LOCATION_NOT_FOUND;

					} else {

						// Next attempt is lower case
						fileName = fileName.toLowerCase();
						subobjectURL = fileName;
						triedLowerCase = true;
						locationState = FILE_LOCATION_TRY_PARTS;

					}

					break;

			}

			const loader = this.loader;
			const fileLoader = new FileLoader( loader.manager );
			fileLoader.setPath( loader.partsLibraryPath );
			fileLoader.setRequestHeader( loader.requestHeader );
			fileLoader.setWithCredentials( loader.withCredentials );

			try {

				const text = await fileLoader.loadAsync( subobjectURL );
				return text;

			} catch ( _ ) {

				continue;

			}

		}

		throw new Error( 'LDrawLoader: Subobject "' + fileName + '" could not be loaded.' );

	}
```
</details>

##### `parse(text: any, fileName: any): { faces: { material: any; colorCode: any; faceNormal: any; vertices: any[]; normals: any[]; }[]; conditionalSegments: { material: any; colorCode: any; vertices: any[]; controlPoints: any[]; }[]; lineSegments: { material: any; colorCode: any; vertices: any[]; }[]; ... 9 more ...; group: any; }`

<details><summary>Code</summary>

```ts
parse( text, fileName = null ) {

		const loader = this.loader;

		// final results
		const faces = [];
		const lineSegments = [];
		const conditionalSegments = [];
		const subobjects = [];
		const materials = {};

		const getLocalMaterial = colorCode => {

			return materials[ colorCode ] || null;

		};

		let type = 'Model';
		let category = null;
		let keywords = null;
		let author = null;
		let totalFaces = 0;

		// split into lines
		if ( text.indexOf( '\r\n' ) !== - 1 ) {

			// This is faster than String.split with regex that splits on both
			text = text.replace( /\r\n/g, '\n' );

		}

		const lines = text.split( '\n' );
		const numLines = lines.length;

		let parsingEmbeddedFiles = false;
		let currentEmbeddedFileName = null;
		let currentEmbeddedText = null;

		let bfcCertified = false;
		let bfcCCW = true;
		let bfcInverted = false;
		let bfcCull = true;

		let startingBuildingStep = false;

		// Parse all line commands
		for ( let lineIndex = 0; lineIndex < numLines; lineIndex ++ ) {

			const line = lines[ lineIndex ];

			if ( line.length === 0 ) continue;

			if ( parsingEmbeddedFiles ) {

				if ( line.startsWith( '0 FILE ' ) ) {

					// Save previous embedded file in the cache
					this.setData( currentEmbeddedFileName, currentEmbeddedText );

					// New embedded text file
					currentEmbeddedFileName = line.substring( 7 );
					currentEmbeddedText = '';

				} else {

					currentEmbeddedText += line + '\n';

				}

				continue;

			}

			const lp = new LineParser( line, lineIndex + 1 );
			lp.seekNonSpace();

			if ( lp.isAtTheEnd() ) {

				// Empty line
				continue;

			}

			// Parse the line type
			const lineType = lp.getToken();

			let material;
			let colorCode;
			let segment;
			let ccw;
			let doubleSided;
			let v0, v1, v2, v3, c0, c1;

			switch ( lineType ) {

				// Line type 0: Comment or META
				case '0':

					// Parse meta directive
					const meta = lp.getToken();

					if ( meta ) {

						switch ( meta ) {

							case '!LDRAW_ORG':

								type = lp.getToken();
								break;

							case '!COLOUR':

								material = loader.parseColorMetaDirective( lp );
								if ( material ) {

									materials[ material.userData.code ] = material;

								}	else {

									console.warn( 'LDrawLoader: Error parsing material' + lp.getLineNumberString() );

								}

								break;

							case '!CATEGORY':

								category = lp.getToken();
								break;

							case '!KEYWORDS':

								const newKeywords = lp.getRemainingString().split( ',' );
								if ( newKeywords.length > 0 ) {

									if ( ! keywords ) {

										keywords = [];

									}

									newKeywords.forEach( function ( keyword ) {

										keywords.push( keyword.trim() );

									} );

								}

								break;

							case 'FILE':

								if ( lineIndex > 0 ) {

									// Start embedded text files parsing
									parsingEmbeddedFiles = true;
									currentEmbeddedFileName = lp.getRemainingString();
									currentEmbeddedText = '';

									bfcCertified = false;
									bfcCCW = true;

								}

								break;

							case 'BFC':

								// Changes to the backface culling state
								while ( ! lp.isAtTheEnd() ) {

									const token = lp.getToken();

									switch ( token ) {

										case 'CERTIFY':
										case 'NOCERTIFY':

											bfcCertified = token === 'CERTIFY';
											bfcCCW = true;

											break;

										case 'CW':
										case 'CCW':

											bfcCCW = token === 'CCW';

											break;

										case 'INVERTNEXT':

											bfcInverted = true;

											break;

										case 'CLIP':
										case 'NOCLIP':

											bfcCull = token === 'CLIP';

											break;

										default:

											console.warn( 'THREE.LDrawLoader: BFC directive "' + token + '" is unknown.' );

											break;

									}

								}

								break;

							case 'STEP':

								startingBuildingStep = true;

								break;

							case 'Author:':

								author = lp.getToken();

								break;

							default:
								// Other meta directives are not implemented
								break;

						}

					}

					break;

					// Line type 1: Sub-object file
				case '1':

					colorCode = lp.getToken();
					material = getLocalMaterial( colorCode );

					const posX = parseFloat( lp.getToken() );
					const posY = parseFloat( lp.getToken() );
					const posZ = parseFloat( lp.getToken() );
					const m0 = parseFloat( lp.getToken() );
					const m1 = parseFloat( lp.getToken() );
					const m2 = parseFloat( lp.getToken() );
					const m3 = parseFloat( lp.getToken() );
					const m4 = parseFloat( lp.getToken() );
					const m5 = parseFloat( lp.getToken() );
					const m6 = parseFloat( lp.getToken() );
					const m7 = parseFloat( lp.getToken() );
					const m8 = parseFloat( lp.getToken() );

					const matrix = new Matrix4().set(
						m0, m1, m2, posX,
						m3, m4, m5, posY,
						m6, m7, m8, posZ,
						0, 0, 0, 1
					);

					let fileName = lp.getRemainingString().trim().replace( /\\/g, '/' );

					if ( loader.fileMap[ fileName ] ) {

						// Found the subobject path in the preloaded file path map
						fileName = loader.fileMap[ fileName ];

					} else {

						// Standardized subfolders
						if ( fileName.startsWith( 's/' ) ) {

							fileName = 'parts/' + fileName;

						} else if ( fileName.startsWith( '48/' ) ) {

							fileName = 'p/' + fileName;

						}

					}

					subobjects.push( {
						material: material,
						colorCode: colorCode,
						matrix: matrix,
						fileName: fileName,
						inverted: bfcInverted,
						startingBuildingStep: startingBuildingStep
					} );

					startingBuildingStep = false;
					bfcInverted = false;

					break;

					// Line type 2: Line segment
				case '2':

					colorCode = lp.getToken();
					material = getLocalMaterial( colorCode );
					v0 = lp.getVector();
					v1 = lp.getVector();

					segment = {
						material: material,
						colorCode: colorCode,
						vertices: [ v0, v1 ],
					};

					lineSegments.push( segment );

					break;

					// Line type 5: Conditional Line segment
				case '5':

					colorCode = lp.getToken();
					material = getLocalMaterial( colorCode );
					v0 = lp.getVector();
					v1 = lp.getVector();
					c0 = lp.getVector();
					c1 = lp.getVector();

					segment = {
						material: material,
						colorCode: colorCode,
						vertices: [ v0, v1 ],
						controlPoints: [ c0, c1 ],
					};

					conditionalSegments.push( segment );

					break;

					// Line type 3: Triangle
				case '3':

					colorCode = lp.getToken();
					material = getLocalMaterial( colorCode );
					ccw = bfcCCW;
					doubleSided = ! bfcCertified || ! bfcCull;

					if ( ccw === true ) {

						v0 = lp.getVector();
						v1 = lp.getVector();
						v2 = lp.getVector();

					} else {

						v2 = lp.getVector();
						v1 = lp.getVector();
						v0 = lp.getVector();

					}

					faces.push( {
						material: material,
						colorCode: colorCode,
						faceNormal: null,
						vertices: [ v0, v1, v2 ],
						normals: [ null, null, null ],
					} );
					totalFaces ++;

					if ( doubleSided === true ) {

						faces.push( {
							material: material,
							colorCode: colorCode,
							faceNormal: null,
							vertices: [ v2, v1, v0 ],
							normals: [ null, null, null ],
						} );
						totalFaces ++;

					}

					break;

					// Line type 4: Quadrilateral
				case '4':

					colorCode = lp.getToken();
					material = getLocalMaterial( colorCode );
					ccw = bfcCCW;
					doubleSided = ! bfcCertified || ! bfcCull;

					if ( ccw === true ) {

						v0 = lp.getVector();
						v1 = lp.getVector();
						v2 = lp.getVector();
						v3 = lp.getVector();

					} else {

						v3 = lp.getVector();
						v2 = lp.getVector();
						v1 = lp.getVector();
						v0 = lp.getVector();

					}

					// specifically place the triangle diagonal in the v0 and v1 slots so we can
					// account for the doubling of vertices later when smoothing normals.
					faces.push( {
						material: material,
						colorCode: colorCode,
						faceNormal: null,
						vertices: [ v0, v1, v2, v3 ],
						normals: [ null, null, null, null ],
					} );
					totalFaces += 2;

					if ( doubleSided === true ) {

						faces.push( {
							material: material,
							colorCode: colorCode,
							faceNormal: null,
							vertices: [ v3, v2, v1, v0 ],
							normals: [ null, null, null, null ],
						} );
						totalFaces += 2;

					}

					break;

				default:
					throw new Error( 'LDrawLoader: Unknown line type "' + lineType + '"' + lp.getLineNumberString() + '.' );

			}

		}

		if ( parsingEmbeddedFiles ) {

			this.setData( currentEmbeddedFileName, currentEmbeddedText );

		}

		return {
			faces,
			conditionalSegments,
			lineSegments,
			type,
			category,
			keywords,
			author,
			subobjects,
			totalFaces,
			startingBuildingStep,
			materials,
			fileName,
			group: null
		};

	}
```
</details>

##### `getData(fileName: any, clone: boolean): any`

<details><summary>Code</summary>

```ts
getData( fileName, clone = true ) {

		const key = fileName.toLowerCase();
		const result = this._cache[ key ];
		if ( result === null || result instanceof Promise ) {

			return null;

		}

		if ( clone ) {

			return this.cloneResult( result );

		} else {

			return result;

		}

	}
```
</details>

##### `ensureDataLoaded(fileName: any): Promise<void>`

<details><summary>Code</summary>

```ts
async ensureDataLoaded( fileName ) {

		const key = fileName.toLowerCase();
		if ( ! ( key in this._cache ) ) {

			// replace the promise with a copy of the parsed data for immediate processing
			this._cache[ key ] = this.fetchData( fileName ).then( text => {

				const info = this.parse( text, fileName );
				this._cache[ key ] = info;
				return info;

			} );

		}

		await this._cache[ key ];

	}
```
</details>

##### `setData(fileName: any, text: any): void`

<details><summary>Code</summary>

```ts
setData( fileName, text ) {

		const key = fileName.toLowerCase();
		this._cache[ key ] = this.parse( text, fileName );

	}
```
</details>

### `LDrawPartsGeometryCache`

<details><summary>Class Code</summary>

```ts
class LDrawPartsGeometryCache {

	constructor( loader ) {

		this.loader = loader;
		this.parseCache = new LDrawParsedCache( loader );
		this._cache = {};

	}

	// Convert the given file information into a mesh by processing subobjects.
	async processIntoMesh( info ) {

		const loader = this.loader;
		const parseCache = this.parseCache;
		const faceMaterials = new Set();

		// Processes the part subobject information to load child parts and merge geometry onto part
		// piece object.
		const processInfoSubobjects = async ( info, subobject = null ) => {

			const subobjects = info.subobjects;
			const promises = [];

			// Trigger load of all subobjects. If a subobject isn't a primitive then load it as a separate
			// group which lets instruction steps apply correctly.
			for ( let i = 0, l = subobjects.length; i < l; i ++ ) {

				const subobject = subobjects[ i ];
				const promise = parseCache.ensureDataLoaded( subobject.fileName ).then( () => {

					const subobjectInfo = parseCache.getData( subobject.fileName, false );
					if ( ! isPrimitiveType( subobjectInfo.type ) ) {

						return this.loadModel( subobject.fileName ).catch( error => {

							console.warn( error );
							return null;

						} );

					}

					return processInfoSubobjects( parseCache.getData( subobject.fileName ), subobject );

				} );

				promises.push( promise );

			}

			const group = new Group();
			group.userData.category = info.category;
			group.userData.keywords = info.keywords;
			group.userData.author = info.author;
			group.userData.type = info.type;
			group.userData.fileName = info.fileName;
			info.group = group;

			const subobjectInfos = await Promise.all( promises );
			for ( let i = 0, l = subobjectInfos.length; i < l; i ++ ) {

				const subobject = info.subobjects[ i ];
				const subobjectInfo = subobjectInfos[ i ];

				if ( subobjectInfo === null ) {

					// the subobject failed to load
					continue;

				}

				// if the subobject was loaded as a separate group then apply the parent scopes materials
				if ( subobjectInfo.isGroup ) {

					const subobjectGroup = subobjectInfo;
					subobject.matrix.decompose( subobjectGroup.position, subobjectGroup.quaternion, subobjectGroup.scale );
					subobjectGroup.userData.startingBuildingStep = subobject.startingBuildingStep;
					subobjectGroup.name = subobject.fileName;

					loader.applyMaterialsToMesh( subobjectGroup, subobject.colorCode, info.materials );
					subobjectGroup.userData.colorCode = subobject.colorCode;

					group.add( subobjectGroup );
					continue;

				}

				// add the subobject group if it has children in case it has both children and primitives
				if ( subobjectInfo.group.children.length ) {

					group.add( subobjectInfo.group );

				}

				// transform the primitives into the local space of the parent piece and append them to
				// to the parent primitives list.
				const parentLineSegments = info.lineSegments;
				const parentConditionalSegments = info.conditionalSegments;
				const parentFaces = info.faces;

				const lineSegments = subobjectInfo.lineSegments;
				const conditionalSegments = subobjectInfo.conditionalSegments;

				const faces = subobjectInfo.faces;
				const matrix = subobject.matrix;
				const inverted = subobject.inverted;
				const matrixScaleInverted = matrix.determinant() < 0;
				const colorCode = subobject.colorCode;

				const lineColorCode = colorCode === MAIN_COLOUR_CODE ? MAIN_EDGE_COLOUR_CODE : colorCode;
				for ( let i = 0, l = lineSegments.length; i < l; i ++ ) {

					const ls = lineSegments[ i ];
					const vertices = ls.vertices;
					vertices[ 0 ].applyMatrix4( matrix );
					vertices[ 1 ].applyMatrix4( matrix );
					ls.colorCode = ls.colorCode === MAIN_EDGE_COLOUR_CODE ? lineColorCode : ls.colorCode;
					ls.material = ls.material || getMaterialFromCode( ls.colorCode, ls.colorCode, info.materials, true );

					parentLineSegments.push( ls );

				}

				for ( let i = 0, l = conditionalSegments.length; i < l; i ++ ) {

					const os = conditionalSegments[ i ];
					const vertices = os.vertices;
					const controlPoints = os.controlPoints;
					vertices[ 0 ].applyMatrix4( matrix );
					vertices[ 1 ].applyMatrix4( matrix );
					controlPoints[ 0 ].applyMatrix4( matrix );
					controlPoints[ 1 ].applyMatrix4( matrix );
					os.colorCode = os.colorCode === MAIN_EDGE_COLOUR_CODE ? lineColorCode : os.colorCode;
					os.material = os.material || getMaterialFromCode( os.colorCode, os.colorCode, info.materials, true );

					parentConditionalSegments.push( os );

				}

				for ( let i = 0, l = faces.length; i < l; i ++ ) {

					const tri = faces[ i ];
					const vertices = tri.vertices;
					for ( let i = 0, l = vertices.length; i < l; i ++ ) {

						vertices[ i ].applyMatrix4( matrix );

					}

					tri.colorCode = tri.colorCode === MAIN_COLOUR_CODE ? colorCode : tri.colorCode;
					tri.material = tri.material || getMaterialFromCode( tri.colorCode, colorCode, info.materials, false );
					faceMaterials.add( tri.colorCode );

					// If the scale of the object is negated then the triangle winding order
					// needs to be flipped.
					if ( matrixScaleInverted !== inverted ) {

						vertices.reverse();

					}

					parentFaces.push( tri );

				}

				info.totalFaces += subobjectInfo.totalFaces;

			}

			// Apply the parent subobjects pass through material code to this object. This is done several times due
			// to material scoping.
			if ( subobject ) {

				loader.applyMaterialsToMesh( group, subobject.colorCode, info.materials );
				group.userData.colorCode = subobject.colorCode;

			}

			return info;

		};

		// Track material use to see if we need to use the normal smooth slow path for hard edges.
		for ( let i = 0, l = info.faces; i < l; i ++ ) {

			faceMaterials.add( info.faces[ i ].colorCode );

		}

		await processInfoSubobjects( info );

		if ( loader.smoothNormals ) {

			const checkSubSegments = faceMaterials.size > 1;
			generateFaceNormals( info.faces );
			smoothNormals( info.faces, info.lineSegments, checkSubSegments );

		}

		// Add the primitive objects and metadata.
		const group = info.group;
		if ( info.faces.length > 0 ) {

			group.add( createObject( this.loader, info.faces, 3, false, info.totalFaces ) );

		}

		if ( info.lineSegments.length > 0 ) {

			group.add( createObject( this.loader, info.lineSegments, 2 ) );

		}

		if ( info.conditionalSegments.length > 0 ) {

			group.add( createObject( this.loader, info.conditionalSegments, 2, true ) );

		}

		return group;

	}

	hasCachedModel( fileName ) {

		return fileName !== null && fileName.toLowerCase() in this._cache;

	}

	async getCachedModel( fileName ) {

		if ( fileName !== null && this.hasCachedModel( fileName ) ) {

			const key = fileName.toLowerCase();
			const group = await this._cache[ key ];
			return group.clone();

		} else {

			return null;

		}

	}

	// Loads and parses the model with the given file name. Returns a cached copy if available.
	async loadModel( fileName ) {

		const parseCache = this.parseCache;
		const key = fileName.toLowerCase();
		if ( this.hasCachedModel( fileName ) ) {

			// Return cached model if available.
			return this.getCachedModel( fileName );

		} else {

			// Otherwise parse a new model.
			// Ensure the file data is loaded and pre parsed.
			await parseCache.ensureDataLoaded( fileName );

			const info = parseCache.getData( fileName );
			const promise = this.processIntoMesh( info );

			// Now that the file has loaded it's possible that another part parse has been waiting in parallel
			// so check the cache again to see if it's been added since the last async operation so we don't
			// do unnecessary work.
			if ( this.hasCachedModel( fileName ) ) {

				return this.getCachedModel( fileName );

			}

			// Cache object if it's a part so it can be reused later.
			if ( isPartType( info.type ) ) {

				this._cache[ key ] = promise;

			}

			// return a copy
			const group = await promise;
			return group.clone();

		}

	}

	// parses the given model text into a renderable object. Returns cached copy if available.
	async parseModel( text ) {

		const parseCache = this.parseCache;
		const info = parseCache.parse( text );
		if ( isPartType( info.type ) && this.hasCachedModel( info.fileName ) ) {

			return this.getCachedModel( info.fileName );

		}

		return this.processIntoMesh( info );

	}

}
```
</details>

#### Methods

##### `processIntoMesh(info: any): Promise<any>`

<details><summary>Code</summary>

```ts
async processIntoMesh( info ) {

		const loader = this.loader;
		const parseCache = this.parseCache;
		const faceMaterials = new Set();

		// Processes the part subobject information to load child parts and merge geometry onto part
		// piece object.
		const processInfoSubobjects = async ( info, subobject = null ) => {

			const subobjects = info.subobjects;
			const promises = [];

			// Trigger load of all subobjects. If a subobject isn't a primitive then load it as a separate
			// group which lets instruction steps apply correctly.
			for ( let i = 0, l = subobjects.length; i < l; i ++ ) {

				const subobject = subobjects[ i ];
				const promise = parseCache.ensureDataLoaded( subobject.fileName ).then( () => {

					const subobjectInfo = parseCache.getData( subobject.fileName, false );
					if ( ! isPrimitiveType( subobjectInfo.type ) ) {

						return this.loadModel( subobject.fileName ).catch( error => {

							console.warn( error );
							return null;

						} );

					}

					return processInfoSubobjects( parseCache.getData( subobject.fileName ), subobject );

				} );

				promises.push( promise );

			}

			const group = new Group();
			group.userData.category = info.category;
			group.userData.keywords = info.keywords;
			group.userData.author = info.author;
			group.userData.type = info.type;
			group.userData.fileName = info.fileName;
			info.group = group;

			const subobjectInfos = await Promise.all( promises );
			for ( let i = 0, l = subobjectInfos.length; i < l; i ++ ) {

				const subobject = info.subobjects[ i ];
				const subobjectInfo = subobjectInfos[ i ];

				if ( subobjectInfo === null ) {

					// the subobject failed to load
					continue;

				}

				// if the subobject was loaded as a separate group then apply the parent scopes materials
				if ( subobjectInfo.isGroup ) {

					const subobjectGroup = subobjectInfo;
					subobject.matrix.decompose( subobjectGroup.position, subobjectGroup.quaternion, subobjectGroup.scale );
					subobjectGroup.userData.startingBuildingStep = subobject.startingBuildingStep;
					subobjectGroup.name = subobject.fileName;

					loader.applyMaterialsToMesh( subobjectGroup, subobject.colorCode, info.materials );
					subobjectGroup.userData.colorCode = subobject.colorCode;

					group.add( subobjectGroup );
					continue;

				}

				// add the subobject group if it has children in case it has both children and primitives
				if ( subobjectInfo.group.children.length ) {

					group.add( subobjectInfo.group );

				}

				// transform the primitives into the local space of the parent piece and append them to
				// to the parent primitives list.
				const parentLineSegments = info.lineSegments;
				const parentConditionalSegments = info.conditionalSegments;
				const parentFaces = info.faces;

				const lineSegments = subobjectInfo.lineSegments;
				const conditionalSegments = subobjectInfo.conditionalSegments;

				const faces = subobjectInfo.faces;
				const matrix = subobject.matrix;
				const inverted = subobject.inverted;
				const matrixScaleInverted = matrix.determinant() < 0;
				const colorCode = subobject.colorCode;

				const lineColorCode = colorCode === MAIN_COLOUR_CODE ? MAIN_EDGE_COLOUR_CODE : colorCode;
				for ( let i = 0, l = lineSegments.length; i < l; i ++ ) {

					const ls = lineSegments[ i ];
					const vertices = ls.vertices;
					vertices[ 0 ].applyMatrix4( matrix );
					vertices[ 1 ].applyMatrix4( matrix );
					ls.colorCode = ls.colorCode === MAIN_EDGE_COLOUR_CODE ? lineColorCode : ls.colorCode;
					ls.material = ls.material || getMaterialFromCode( ls.colorCode, ls.colorCode, info.materials, true );

					parentLineSegments.push( ls );

				}

				for ( let i = 0, l = conditionalSegments.length; i < l; i ++ ) {

					const os = conditionalSegments[ i ];
					const vertices = os.vertices;
					const controlPoints = os.controlPoints;
					vertices[ 0 ].applyMatrix4( matrix );
					vertices[ 1 ].applyMatrix4( matrix );
					controlPoints[ 0 ].applyMatrix4( matrix );
					controlPoints[ 1 ].applyMatrix4( matrix );
					os.colorCode = os.colorCode === MAIN_EDGE_COLOUR_CODE ? lineColorCode : os.colorCode;
					os.material = os.material || getMaterialFromCode( os.colorCode, os.colorCode, info.materials, true );

					parentConditionalSegments.push( os );

				}

				for ( let i = 0, l = faces.length; i < l; i ++ ) {

					const tri = faces[ i ];
					const vertices = tri.vertices;
					for ( let i = 0, l = vertices.length; i < l; i ++ ) {

						vertices[ i ].applyMatrix4( matrix );

					}

					tri.colorCode = tri.colorCode === MAIN_COLOUR_CODE ? colorCode : tri.colorCode;
					tri.material = tri.material || getMaterialFromCode( tri.colorCode, colorCode, info.materials, false );
					faceMaterials.add( tri.colorCode );

					// If the scale of the object is negated then the triangle winding order
					// needs to be flipped.
					if ( matrixScaleInverted !== inverted ) {

						vertices.reverse();

					}

					parentFaces.push( tri );

				}

				info.totalFaces += subobjectInfo.totalFaces;

			}

			// Apply the parent subobjects pass through material code to this object. This is done several times due
			// to material scoping.
			if ( subobject ) {

				loader.applyMaterialsToMesh( group, subobject.colorCode, info.materials );
				group.userData.colorCode = subobject.colorCode;

			}

			return info;

		};

		// Track material use to see if we need to use the normal smooth slow path for hard edges.
		for ( let i = 0, l = info.faces; i < l; i ++ ) {

			faceMaterials.add( info.faces[ i ].colorCode );

		}

		await processInfoSubobjects( info );

		if ( loader.smoothNormals ) {

			const checkSubSegments = faceMaterials.size > 1;
			generateFaceNormals( info.faces );
			smoothNormals( info.faces, info.lineSegments, checkSubSegments );

		}

		// Add the primitive objects and metadata.
		const group = info.group;
		if ( info.faces.length > 0 ) {

			group.add( createObject( this.loader, info.faces, 3, false, info.totalFaces ) );

		}

		if ( info.lineSegments.length > 0 ) {

			group.add( createObject( this.loader, info.lineSegments, 2 ) );

		}

		if ( info.conditionalSegments.length > 0 ) {

			group.add( createObject( this.loader, info.conditionalSegments, 2, true ) );

		}

		return group;

	}
```
</details>

##### `hasCachedModel(fileName: any): boolean`

<details><summary>Code</summary>

```ts
hasCachedModel( fileName ) {

		return fileName !== null && fileName.toLowerCase() in this._cache;

	}
```
</details>

##### `getCachedModel(fileName: any): Promise<any>`

<details><summary>Code</summary>

```ts
async getCachedModel( fileName ) {

		if ( fileName !== null && this.hasCachedModel( fileName ) ) {

			const key = fileName.toLowerCase();
			const group = await this._cache[ key ];
			return group.clone();

		} else {

			return null;

		}

	}
```
</details>

##### `loadModel(fileName: any): Promise<any>`

<details><summary>Code</summary>

```ts
async loadModel( fileName ) {

		const parseCache = this.parseCache;
		const key = fileName.toLowerCase();
		if ( this.hasCachedModel( fileName ) ) {

			// Return cached model if available.
			return this.getCachedModel( fileName );

		} else {

			// Otherwise parse a new model.
			// Ensure the file data is loaded and pre parsed.
			await parseCache.ensureDataLoaded( fileName );

			const info = parseCache.getData( fileName );
			const promise = this.processIntoMesh( info );

			// Now that the file has loaded it's possible that another part parse has been waiting in parallel
			// so check the cache again to see if it's been added since the last async operation so we don't
			// do unnecessary work.
			if ( this.hasCachedModel( fileName ) ) {

				return this.getCachedModel( fileName );

			}

			// Cache object if it's a part so it can be reused later.
			if ( isPartType( info.type ) ) {

				this._cache[ key ] = promise;

			}

			// return a copy
			const group = await promise;
			return group.clone();

		}

	}
```
</details>

##### `parseModel(text: any): Promise<any>`

<details><summary>Code</summary>

```ts
async parseModel( text ) {

		const parseCache = this.parseCache;
		const info = parseCache.parse( text );
		if ( isPartType( info.type ) && this.hasCachedModel( info.fileName ) ) {

			return this.getCachedModel( info.fileName );

		}

		return this.processIntoMesh( info );

	}
```
</details>

### `LDrawLoader`

<details><summary>Class Code</summary>

```ts
class LDrawLoader extends Loader {

	/**
	 * Constructs a new LDraw loader.
	 *
	 * @param {LoadingManager} [manager] - The loading manager.
	 */
	constructor( manager ) {

		super( manager );

		// Array of THREE.Material
		this.materials = [];
		this.materialLibrary = {};
		this.edgeMaterialCache = new WeakMap();
		this.conditionalEdgeMaterialCache = new WeakMap();

		// This also allows to handle the embedded text files ("0 FILE" lines)
		this.partsCache = new LDrawPartsGeometryCache( this );

		// This object is a map from file names to paths. It agilizes the paths search. If it is not set then files will be searched by trial and error.
		this.fileMap = {};

		// If this flag is set to true the vertex normals will be smoothed.
		this.smoothNormals = true;

		// The path to load parts from the LDraw parts library from.
		this.partsLibraryPath = '';

		// this material type must be injected via setConditionalLineMaterial()
		this.ConditionalLineMaterial = null;

		// Material assigned to not available colors for meshes and edges
		this.missingColorMaterial = new MeshStandardMaterial( { name: Loader.DEFAULT_MATERIAL_NAME, color: 0xFF00FF, roughness: 0.3, metalness: 0 } );
		this.missingEdgeColorMaterial = new LineBasicMaterial( { name: Loader.DEFAULT_MATERIAL_NAME, color: 0xFF00FF } );
		this.missingConditionalEdgeColorMaterial = null;
		this.edgeMaterialCache.set( this.missingColorMaterial, this.missingEdgeColorMaterial );
		this.conditionalEdgeMaterialCache.set( this.missingEdgeColorMaterial, this.missingConditionalEdgeColorMaterial );

	}

	/**
	 * This method must be called prior to `load()` unless the model to load does not reference
	 * library parts (usually it will be a model with all its parts packed in a single file).
	 *
	 * @param {string} path - Path to library parts files to load referenced parts from.
	 * This is different from Loader.setPath, which indicates the path to load the main asset from.
	 * @return {LDrawLoader} A reference to this loader.
	 */
	setPartsLibraryPath( path ) {

		this.partsLibraryPath = path;
		return this;

	}

	/**
	 * Sets the conditional line material type which depends on the used renderer.
	 * Use {@link LDrawConditionalLineMaterial} when using `WebGLRenderer` and
	 * {@link LDrawConditionalLineNodeMaterial} when using `WebGPURenderer`.
	 *
	 * @param {(LDrawConditionalLineMaterial.constructor|LDrawConditionalLineNodeMaterial.constructor)} type - The conditional line material type.
	 * @return {LDrawLoader} A reference to this loader.
	 */
	setConditionalLineMaterial( type ) {

		this.ConditionalLineMaterial = type;
		this.missingConditionalEdgeColorMaterial = new this.ConditionalLineMaterial( { name: Loader.DEFAULT_MATERIAL_NAME, fog: true, color: 0xFF00FF } );
		return this;

	}

	/**
	 * This async method preloads materials from a single LDraw file. In the official
	 * parts library there is a special file which is loaded always the first (LDConfig.ldr)
	 * and contains all the standard color codes. This method is intended to be used with
	 * not packed files, for example in an editor where materials are preloaded and parts
	 * are loaded on demand.
	 *
	 * @async
	 * @param {string} url - Path of the LDraw materials asset.
	 * @return {Promise} A Promise that resolves when the preload has finished.
	 */
	async preloadMaterials( url ) {

		const fileLoader = new FileLoader( this.manager );
		fileLoader.setPath( this.path );
		fileLoader.setRequestHeader( this.requestHeader );
		fileLoader.setWithCredentials( this.withCredentials );

		const text = await fileLoader.loadAsync( url );
		const colorLineRegex = /^0 !COLOUR/;
		const lines = text.split( /[\n\r]/g );
		const materials = [];
		for ( let i = 0, l = lines.length; i < l; i ++ ) {

			const line = lines[ i ];
			if ( colorLineRegex.test( line ) ) {

				const directive = line.replace( colorLineRegex, '' );
				const material = this.parseColorMetaDirective( new LineParser( directive ) );
				materials.push( material );

			}

		}

		this.addMaterials( materials );

	}

	/**
	 * Starts loading from the given URL and passes the loaded LDraw asset
	 * to the `onLoad()` callback.
	 *
	 * @param {string} url - The path/URL of the file to be loaded. This can also be a data URI.
	 * @param {function(Group)} onLoad - Executed when the loading process has been finished.
	 * @param {onProgressCallback} onProgress - Executed while the loading is in progress.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	load( url, onLoad, onProgress, onError ) {

		const fileLoader = new FileLoader( this.manager );
		fileLoader.setPath( this.path );
		fileLoader.setRequestHeader( this.requestHeader );
		fileLoader.setWithCredentials( this.withCredentials );
		fileLoader.load( url, text => {

			// Initializes the materials library with default materials
			this.addDefaultMaterials();

			this.partsCache
				.parseModel( text )
				.then( group => {

					this.applyMaterialsToMesh( group, MAIN_COLOUR_CODE, this.materialLibrary, true );
					this.computeBuildingSteps( group );
					group.userData.fileName = url;
					onLoad( group );

				} )
				.catch( onError );

		}, onProgress, onError );

	}

	/**
	 * Parses the given LDraw data and returns the resulting group.
	 *
	 * @param {string} text - The raw VRML data as a string.
	 * @param {function(Group)} onLoad - Executed when the loading/parsing process has been finished.
	 * @param {onErrorCallback} onError - Executed when errors occur.
	 */
	parse( text, onLoad, onError ) {

		this.partsCache
			.parseModel( text )
			.then( group => {

				this.applyMaterialsToMesh( group, MAIN_COLOUR_CODE, this.materialLibrary, true );
				this.computeBuildingSteps( group );
				group.userData.fileName = '';
				onLoad( group );

			} )
			.catch( onError );

	}

	/**
	 * Sets the loader's material library. This method clears existing
	 * material definitions.
	 *
	 * @param {Array<Material>} materials - The materials to set.
	 * @return {LDrawLoader} A reference to this loader.
	 */
	setMaterials( materials ) {

		this.clearMaterials();
		this.addMaterials( materials );

		return this;

	}

	/**
	 * Clears the loader's material library.
	 *
	 * @return {LDrawLoader} A reference to this loader.
	 */
	clearMaterials() {

		this.materialLibrary = {};
		this.materials = [];

		return this;

	}

	/**
	 * Adds a list of materials to the loader's material library.
	 *
	 * @param {Array<Material>} materials - The materials to add.
	 * @return {LDrawLoader} A reference to this loader.
	 */
	addMaterials( materials ) {

		for ( let i = 0, l = materials.length; i < l; i ++ ) {

			this.addMaterial( materials[ i ] );

		}

		return this;

	}

	/**
	 * Initializes the loader with default materials.
	 *
	 * @return {LDrawLoader} A reference to this loader.
	 */
	addDefaultMaterials() {

		// Add default main triangle and line edge materials (used in pieces that can be colored with a main color)
		this.addMaterial( this.parseColorMetaDirective( new LineParser( 'Main_Colour CODE 16 VALUE #FF8080 EDGE #333333' ) ) );
		this.addMaterial( this.parseColorMetaDirective( new LineParser( 'Edge_Colour CODE 24 VALUE #A0A0A0 EDGE #333333' ) ) );

		return this;

	}

	/**
	 * Sets a map which maps referenced library filenames to new filenames.
	 * If a fileMap is not specified (the default), library parts will be accessed by trial and
	 * error in subfolders 'parts', 'p' and 'models'.
	 *
	 * @param {Object<string,string>} fileMap - The file map to set.
	 * @return {LDrawLoader} A reference to this loader.
	 */
	setFileMap( fileMap ) {

		this.fileMap = fileMap;

		return this;

	}

	/**
	 * Adds a single material to the loader's material library.
	 *
	 * @param {Material} material - The material to add.
	 * @return {LDrawLoader} A reference to this loader.
	 */
	addMaterial( material ) {

		// Adds a material to the material library which is on top of the parse scopes stack. And also to the materials array

		const matLib = this.materialLibrary;
		if ( ! matLib[ material.userData.code ] ) {

			this.materials.push( material );
			matLib[ material.userData.code ] = material;

		}

		return this;

	}

	/**
	 * Returns a material for the given color code.
	 *
	 * @param {string} colorCode - The color code.
	 * @return {?Material} The material. Returns `null` if no material has been found.
	 */
	getMaterial( colorCode ) {

		if ( colorCode.startsWith( '0x2' ) ) {

			// Special 'direct' material value (RGB color)
			const color = colorCode.substring( 3 );

			return this.parseColorMetaDirective( new LineParser( 'Direct_Color_' + color + ' CODE -1 VALUE #' + color + ' EDGE #' + color + '' ) );

		}

		return this.materialLibrary[ colorCode ] || null;

	}

	// Applies the appropriate materials to a prebuilt hierarchy of geometry. Assumes that color codes are present
	// in the material array if they need to be filled in.
	applyMaterialsToMesh( group, parentColorCode, materialHierarchy, finalMaterialPass = false ) {

		// find any missing materials as indicated by a color code string and replace it with a material from the current material lib
		const loader = this;
		const parentIsPassthrough = parentColorCode === MAIN_COLOUR_CODE;
		group.traverse( c => {

			if ( c.isMesh || c.isLineSegments ) {

				if ( Array.isArray( c.material ) ) {

					for ( let i = 0, l = c.material.length; i < l; i ++ ) {

						if ( ! c.material[ i ].isMaterial ) {

							c.material[ i ] = getMaterial( c, c.material[ i ] );

						}

					}

				} else if ( ! c.material.isMaterial ) {

					c.material = getMaterial( c, c.material );

				}

			}

		} );


		// Returns the appropriate material for the object (line or face) given color code. If the code is "pass through"
		// (24 for lines, 16 for edges) then the pass through color code is used. If that is also pass through then it's
		// simply returned for the subsequent material application.
		function getMaterial( c, colorCode ) {

			// if our parent is a passthrough color code and we don't have the current material color available then
			// return early.
			if ( parentIsPassthrough && ! ( colorCode in materialHierarchy ) && ! finalMaterialPass ) {

				return colorCode;

			}

			const forEdge = c.isLineSegments || c.isConditionalLine;
			const isPassthrough = ! forEdge && colorCode === MAIN_COLOUR_CODE || forEdge && colorCode === MAIN_EDGE_COLOUR_CODE;
			if ( isPassthrough ) {

				colorCode = parentColorCode;

			}

			let material = null;
			if ( colorCode in materialHierarchy ) {

				material = materialHierarchy[ colorCode ];

			} else if ( finalMaterialPass ) {

				// see if we can get the final material from the "getMaterial" function which will attempt to
				// parse the "direct" colors
				material = loader.getMaterial( colorCode );
				if ( material === null ) {

					// otherwise throw a warning if this is final opportunity to set the material
					console.warn( `LDrawLoader: Material properties for code ${ colorCode } not available.` );

					// And return the 'missing color' material
					material = loader.missingColorMaterial;

				}


			} else {

				return colorCode;

			}

			if ( c.isLineSegments ) {

				material = loader.edgeMaterialCache.get( material );

				if ( c.isConditionalLine ) {

					material = loader.conditionalEdgeMaterialCache.get( material );

				}

			}

			return material;

		}

	}

	/**
	 * Returns the Material for the main LDraw color.
	 *
	 * For an already loaded LDraw asset, returns the Material associated with the main color code.
	 * This method can be useful to modify the main material of a model or part that exposes it.
	 *
	 * The main color code is the standard way to color an LDraw part. It is '16' for triangles and
	 * '24' for edges. Usually a complete model will not expose the main color (that is, no part
	 * uses the code '16' at the top level, because they are assigned other specific colors) An LDraw
	 *  part file on the other hand will expose the code '16' to be colored, and can have additional
	 * fixed colors.
	 *
	 * @return {?Material} The material. Returns `null` if no material has been found.
	 */
	getMainMaterial() {

		return this.getMaterial( MAIN_COLOUR_CODE );

	}

	/**
	 * Returns the material for the edges main LDraw color.
	 *
	 * @return {?Material} The material. Returns `null` if no material has been found.
	 */
	getMainEdgeMaterial() {

		const mat = this.getMaterial( MAIN_EDGE_COLOUR_CODE );
		return mat ? this.edgeMaterialCache.get( mat ) : null;

	}

	parseColorMetaDirective( lineParser ) {

		// Parses a color definition and returns a THREE.Material

		let code = null;

		// Triangle and line colors
		let fillColor = '#FF00FF';
		let edgeColor = '#FF00FF';

		// Transparency
		let alpha = 1;
		let isTransparent = false;
		// Self-illumination:
		let luminance = 0;

		let finishType = FINISH_TYPE_DEFAULT;

		let edgeMaterial = null;

		const name = lineParser.getToken();
		if ( ! name ) {

			throw new Error( 'LDrawLoader: Material name was expected after "!COLOUR tag' + lineParser.getLineNumberString() + '.' );

		}

		// Parse tag tokens and their parameters
		let token = null;
		while ( true ) {

			token = lineParser.getToken();

			if ( ! token ) {

				break;

			}

			if ( ! parseLuminance( token ) ) {

				switch ( token.toUpperCase() ) {

					case 'CODE':

						code = lineParser.getToken();
						break;

					case 'VALUE':

						fillColor = lineParser.getToken();
						if ( fillColor.startsWith( '0x' ) ) {

							fillColor = '#' + fillColor.substring( 2 );

						} else if ( ! fillColor.startsWith( '#' ) ) {

							throw new Error( 'LDrawLoader: Invalid color while parsing material' + lineParser.getLineNumberString() + '.' );

						}

						break;

					case 'EDGE':

						edgeColor = lineParser.getToken();
						if ( edgeColor.startsWith( '0x' ) ) {

							edgeColor = '#' + edgeColor.substring( 2 );

						} else if ( ! edgeColor.startsWith( '#' ) ) {

							// Try to see if edge color is a color code
							edgeMaterial = this.getMaterial( edgeColor );
							if ( ! edgeMaterial ) {

								throw new Error( 'LDrawLoader: Invalid edge color while parsing material' + lineParser.getLineNumberString() + '.' );

							}

							// Get the edge material for this triangle material
							edgeMaterial = this.edgeMaterialCache.get( edgeMaterial );

						}

						break;

					case 'ALPHA':

						alpha = parseInt( lineParser.getToken() );

						if ( isNaN( alpha ) ) {

							throw new Error( 'LDrawLoader: Invalid alpha value in material definition' + lineParser.getLineNumberString() + '.' );

						}

						alpha = Math.max( 0, Math.min( 1, alpha / 255 ) );

						if ( alpha < 1 ) {

							isTransparent = true;

						}

						break;

					case 'LUMINANCE':

						if ( ! parseLuminance( lineParser.getToken() ) ) {

							throw new Error( 'LDrawLoader: Invalid luminance value in material definition' + lineParser.getLineNumberString() + '.' );

						}

						break;

					case 'CHROME':
						finishType = FINISH_TYPE_CHROME;
						break;

					case 'PEARLESCENT':
						finishType = FINISH_TYPE_PEARLESCENT;
						break;

					case 'RUBBER':
						finishType = FINISH_TYPE_RUBBER;
						break;

					case 'MATTE_METALLIC':
						finishType = FINISH_TYPE_MATTE_METALLIC;
						break;

					case 'METAL':
						finishType = FINISH_TYPE_METAL;
						break;

					case 'MATERIAL':
						// Not implemented
						lineParser.setToEnd();
						break;

					default:
						throw new Error( 'LDrawLoader: Unknown token "' + token + '" while parsing material' + lineParser.getLineNumberString() + '.' );

				}

			}

		}

		let material = null;

		switch ( finishType ) {

			case FINISH_TYPE_DEFAULT:

				material = new MeshStandardMaterial( { roughness: 0.3, metalness: 0 } );
				break;

			case FINISH_TYPE_PEARLESCENT:

				// Try to imitate pearlescency by making the surface glossy
				material = new MeshStandardMaterial( { roughness: 0.3, metalness: 0.25 } );
				break;

			case FINISH_TYPE_CHROME:

				// Mirror finish surface
				material = new MeshStandardMaterial( { roughness: 0, metalness: 1 } );
				break;

			case FINISH_TYPE_RUBBER:

				// Rubber finish
				material = new MeshStandardMaterial( { roughness: 0.9, metalness: 0 } );
				break;

			case FINISH_TYPE_MATTE_METALLIC:

				// Brushed metal finish
				material = new MeshStandardMaterial( { roughness: 0.8, metalness: 0.4 } );
				break;

			case FINISH_TYPE_METAL:

				// Average metal finish
				material = new MeshStandardMaterial( { roughness: 0.2, metalness: 0.85 } );
				break;

			default:
				// Should not happen
				break;

		}

		material.color.setStyle( fillColor, COLOR_SPACE_LDRAW );
		material.transparent = isTransparent;
		material.premultipliedAlpha = true;
		material.opacity = alpha;
		material.depthWrite = ! isTransparent;

		material.polygonOffset = true;
		material.polygonOffsetFactor = 1;

		if ( luminance !== 0 ) {

			material.emissive.setStyle( fillColor, COLOR_SPACE_LDRAW ).multiplyScalar( luminance );

		}

		if ( ! edgeMaterial ) {

			// This is the material used for edges
			edgeMaterial = new LineBasicMaterial( {
				color: new Color().setStyle( edgeColor, COLOR_SPACE_LDRAW ),
				transparent: isTransparent,
				opacity: alpha,
				depthWrite: ! isTransparent
			} );
			edgeMaterial.color;
			edgeMaterial.userData.code = code;
			edgeMaterial.name = name + ' - Edge';

			if ( this.ConditionalLineMaterial === null ) {

				throw new Error( 'THREE.LDrawLoader: ConditionalLineMaterial type must be specified via .setConditionalLineMaterial().' );

			}

			// This is the material used for conditional edges
			const conditionalEdgeMaterial = new this.ConditionalLineMaterial( {

				fog: true,
				transparent: isTransparent,
				depthWrite: ! isTransparent,
				color: new Color().setStyle( edgeColor, COLOR_SPACE_LDRAW ),
				opacity: alpha,

			} );
			conditionalEdgeMaterial.userData.code = code;
			conditionalEdgeMaterial.name = name + ' - Conditional Edge';

			this.conditionalEdgeMaterialCache.set( edgeMaterial, conditionalEdgeMaterial );

		}

		material.userData.code = code;
		material.name = name;

		this.edgeMaterialCache.set( material, edgeMaterial );

		this.addMaterial( material );

		return material;

		function parseLuminance( token ) {

			// Returns success

			let lum;

			if ( token.startsWith( 'LUMINANCE' ) ) {

				lum = parseInt( token.substring( 9 ) );

			} else {

				lum = parseInt( token );

			}

			if ( isNaN( lum ) ) {

				return false;

			}

			luminance = Math.max( 0, Math.min( 1, lum / 255 ) );

			return true;

		}

	}

	computeBuildingSteps( model ) {

		// Sets userdata.buildingStep number in Group objects and userData.numBuildingSteps number in the root Group object.

		let stepNumber = 0;

		model.traverse( c => {

			if ( c.isGroup ) {

				if ( c.userData.startingBuildingStep ) {

					stepNumber ++;

				}

				c.userData.buildingStep = stepNumber;

			}

		} );

		model.userData.numBuildingSteps = stepNumber + 1;

	}

}
```
</details>

#### Methods

##### `setPartsLibraryPath(path: string): LDrawLoader`

<details><summary>Code</summary>

```ts
setPartsLibraryPath( path ) {

		this.partsLibraryPath = path;
		return this;

	}
```
</details>

##### `setConditionalLineMaterial(type: any): LDrawLoader`

<details><summary>Code</summary>

```ts
setConditionalLineMaterial( type ) {

		this.ConditionalLineMaterial = type;
		this.missingConditionalEdgeColorMaterial = new this.ConditionalLineMaterial( { name: Loader.DEFAULT_MATERIAL_NAME, fog: true, color: 0xFF00FF } );
		return this;

	}
```
</details>

##### `preloadMaterials(url: string): Promise<any>`

<details><summary>Code</summary>

```ts
async preloadMaterials( url ) {

		const fileLoader = new FileLoader( this.manager );
		fileLoader.setPath( this.path );
		fileLoader.setRequestHeader( this.requestHeader );
		fileLoader.setWithCredentials( this.withCredentials );

		const text = await fileLoader.loadAsync( url );
		const colorLineRegex = /^0 !COLOUR/;
		const lines = text.split( /[\n\r]/g );
		const materials = [];
		for ( let i = 0, l = lines.length; i < l; i ++ ) {

			const line = lines[ i ];
			if ( colorLineRegex.test( line ) ) {

				const directive = line.replace( colorLineRegex, '' );
				const material = this.parseColorMetaDirective( new LineParser( directive ) );
				materials.push( material );

			}

		}

		this.addMaterials( materials );

	}
```
</details>

##### `load(url: string, onLoad: (arg0: Group) => any, onProgress: onProgressCallback, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
load( url, onLoad, onProgress, onError ) {

		const fileLoader = new FileLoader( this.manager );
		fileLoader.setPath( this.path );
		fileLoader.setRequestHeader( this.requestHeader );
		fileLoader.setWithCredentials( this.withCredentials );
		fileLoader.load( url, text => {

			// Initializes the materials library with default materials
			this.addDefaultMaterials();

			this.partsCache
				.parseModel( text )
				.then( group => {

					this.applyMaterialsToMesh( group, MAIN_COLOUR_CODE, this.materialLibrary, true );
					this.computeBuildingSteps( group );
					group.userData.fileName = url;
					onLoad( group );

				} )
				.catch( onError );

		}, onProgress, onError );

	}
```
</details>

##### `parse(text: string, onLoad: (arg0: Group) => any, onError: onErrorCallback): void`

<details><summary>Code</summary>

```ts
parse( text, onLoad, onError ) {

		this.partsCache
			.parseModel( text )
			.then( group => {

				this.applyMaterialsToMesh( group, MAIN_COLOUR_CODE, this.materialLibrary, true );
				this.computeBuildingSteps( group );
				group.userData.fileName = '';
				onLoad( group );

			} )
			.catch( onError );

	}
```
</details>

##### `setMaterials(materials: Material[]): LDrawLoader`

<details><summary>Code</summary>

```ts
setMaterials( materials ) {

		this.clearMaterials();
		this.addMaterials( materials );

		return this;

	}
```
</details>

##### `clearMaterials(): LDrawLoader`

<details><summary>Code</summary>

```ts
clearMaterials() {

		this.materialLibrary = {};
		this.materials = [];

		return this;

	}
```
</details>

##### `addMaterials(materials: Material[]): LDrawLoader`

<details><summary>Code</summary>

```ts
addMaterials( materials ) {

		for ( let i = 0, l = materials.length; i < l; i ++ ) {

			this.addMaterial( materials[ i ] );

		}

		return this;

	}
```
</details>

##### `addDefaultMaterials(): LDrawLoader`

<details><summary>Code</summary>

```ts
addDefaultMaterials() {

		// Add default main triangle and line edge materials (used in pieces that can be colored with a main color)
		this.addMaterial( this.parseColorMetaDirective( new LineParser( 'Main_Colour CODE 16 VALUE #FF8080 EDGE #333333' ) ) );
		this.addMaterial( this.parseColorMetaDirective( new LineParser( 'Edge_Colour CODE 24 VALUE #A0A0A0 EDGE #333333' ) ) );

		return this;

	}
```
</details>

##### `setFileMap(fileMap: { [x: string]: string; }): LDrawLoader`

<details><summary>Code</summary>

```ts
setFileMap( fileMap ) {

		this.fileMap = fileMap;

		return this;

	}
```
</details>

##### `addMaterial(material: Material): LDrawLoader`

<details><summary>Code</summary>

```ts
addMaterial( material ) {

		// Adds a material to the material library which is on top of the parse scopes stack. And also to the materials array

		const matLib = this.materialLibrary;
		if ( ! matLib[ material.userData.code ] ) {

			this.materials.push( material );
			matLib[ material.userData.code ] = material;

		}

		return this;

	}
```
</details>

##### `getMaterial(colorCode: string): Material`

<details><summary>Code</summary>

```ts
getMaterial( colorCode ) {

		if ( colorCode.startsWith( '0x2' ) ) {

			// Special 'direct' material value (RGB color)
			const color = colorCode.substring( 3 );

			return this.parseColorMetaDirective( new LineParser( 'Direct_Color_' + color + ' CODE -1 VALUE #' + color + ' EDGE #' + color + '' ) );

		}

		return this.materialLibrary[ colorCode ] || null;

	}
```
</details>

##### `applyMaterialsToMesh(group: any, parentColorCode: any, materialHierarchy: any, finalMaterialPass: boolean): void`

<details><summary>Code</summary>

```ts
applyMaterialsToMesh( group, parentColorCode, materialHierarchy, finalMaterialPass = false ) {

		// find any missing materials as indicated by a color code string and replace it with a material from the current material lib
		const loader = this;
		const parentIsPassthrough = parentColorCode === MAIN_COLOUR_CODE;
		group.traverse( c => {

			if ( c.isMesh || c.isLineSegments ) {

				if ( Array.isArray( c.material ) ) {

					for ( let i = 0, l = c.material.length; i < l; i ++ ) {

						if ( ! c.material[ i ].isMaterial ) {

							c.material[ i ] = getMaterial( c, c.material[ i ] );

						}

					}

				} else if ( ! c.material.isMaterial ) {

					c.material = getMaterial( c, c.material );

				}

			}

		} );


		// Returns the appropriate material for the object (line or face) given color code. If the code is "pass through"
		// (24 for lines, 16 for edges) then the pass through color code is used. If that is also pass through then it's
		// simply returned for the subsequent material application.
		function getMaterial( c, colorCode ) {

			// if our parent is a passthrough color code and we don't have the current material color available then
			// return early.
			if ( parentIsPassthrough && ! ( colorCode in materialHierarchy ) && ! finalMaterialPass ) {

				return colorCode;

			}

			const forEdge = c.isLineSegments || c.isConditionalLine;
			const isPassthrough = ! forEdge && colorCode === MAIN_COLOUR_CODE || forEdge && colorCode === MAIN_EDGE_COLOUR_CODE;
			if ( isPassthrough ) {

				colorCode = parentColorCode;

			}

			let material = null;
			if ( colorCode in materialHierarchy ) {

				material = materialHierarchy[ colorCode ];

			} else if ( finalMaterialPass ) {

				// see if we can get the final material from the "getMaterial" function which will attempt to
				// parse the "direct" colors
				material = loader.getMaterial( colorCode );
				if ( material === null ) {

					// otherwise throw a warning if this is final opportunity to set the material
					console.warn( `LDrawLoader: Material properties for code ${ colorCode } not available.` );

					// And return the 'missing color' material
					material = loader.missingColorMaterial;

				}


			} else {

				return colorCode;

			}

			if ( c.isLineSegments ) {

				material = loader.edgeMaterialCache.get( material );

				if ( c.isConditionalLine ) {

					material = loader.conditionalEdgeMaterialCache.get( material );

				}

			}

			return material;

		}

	}
```
</details>

##### `getMainMaterial(): Material`

<details><summary>Code</summary>

```ts
getMainMaterial() {

		return this.getMaterial( MAIN_COLOUR_CODE );

	}
```
</details>

##### `getMainEdgeMaterial(): Material`

<details><summary>Code</summary>

```ts
getMainEdgeMaterial() {

		const mat = this.getMaterial( MAIN_EDGE_COLOUR_CODE );
		return mat ? this.edgeMaterialCache.get( mat ) : null;

	}
```
</details>

##### `parseColorMetaDirective(lineParser: any): any`

<details><summary>Code</summary>

```ts
parseColorMetaDirective( lineParser ) {

		// Parses a color definition and returns a THREE.Material

		let code = null;

		// Triangle and line colors
		let fillColor = '#FF00FF';
		let edgeColor = '#FF00FF';

		// Transparency
		let alpha = 1;
		let isTransparent = false;
		// Self-illumination:
		let luminance = 0;

		let finishType = FINISH_TYPE_DEFAULT;

		let edgeMaterial = null;

		const name = lineParser.getToken();
		if ( ! name ) {

			throw new Error( 'LDrawLoader: Material name was expected after "!COLOUR tag' + lineParser.getLineNumberString() + '.' );

		}

		// Parse tag tokens and their parameters
		let token = null;
		while ( true ) {

			token = lineParser.getToken();

			if ( ! token ) {

				break;

			}

			if ( ! parseLuminance( token ) ) {

				switch ( token.toUpperCase() ) {

					case 'CODE':

						code = lineParser.getToken();
						break;

					case 'VALUE':

						fillColor = lineParser.getToken();
						if ( fillColor.startsWith( '0x' ) ) {

							fillColor = '#' + fillColor.substring( 2 );

						} else if ( ! fillColor.startsWith( '#' ) ) {

							throw new Error( 'LDrawLoader: Invalid color while parsing material' + lineParser.getLineNumberString() + '.' );

						}

						break;

					case 'EDGE':

						edgeColor = lineParser.getToken();
						if ( edgeColor.startsWith( '0x' ) ) {

							edgeColor = '#' + edgeColor.substring( 2 );

						} else if ( ! edgeColor.startsWith( '#' ) ) {

							// Try to see if edge color is a color code
							edgeMaterial = this.getMaterial( edgeColor );
							if ( ! edgeMaterial ) {

								throw new Error( 'LDrawLoader: Invalid edge color while parsing material' + lineParser.getLineNumberString() + '.' );

							}

							// Get the edge material for this triangle material
							edgeMaterial = this.edgeMaterialCache.get( edgeMaterial );

						}

						break;

					case 'ALPHA':

						alpha = parseInt( lineParser.getToken() );

						if ( isNaN( alpha ) ) {

							throw new Error( 'LDrawLoader: Invalid alpha value in material definition' + lineParser.getLineNumberString() + '.' );

						}

						alpha = Math.max( 0, Math.min( 1, alpha / 255 ) );

						if ( alpha < 1 ) {

							isTransparent = true;

						}

						break;

					case 'LUMINANCE':

						if ( ! parseLuminance( lineParser.getToken() ) ) {

							throw new Error( 'LDrawLoader: Invalid luminance value in material definition' + lineParser.getLineNumberString() + '.' );

						}

						break;

					case 'CHROME':
						finishType = FINISH_TYPE_CHROME;
						break;

					case 'PEARLESCENT':
						finishType = FINISH_TYPE_PEARLESCENT;
						break;

					case 'RUBBER':
						finishType = FINISH_TYPE_RUBBER;
						break;

					case 'MATTE_METALLIC':
						finishType = FINISH_TYPE_MATTE_METALLIC;
						break;

					case 'METAL':
						finishType = FINISH_TYPE_METAL;
						break;

					case 'MATERIAL':
						// Not implemented
						lineParser.setToEnd();
						break;

					default:
						throw new Error( 'LDrawLoader: Unknown token "' + token + '" while parsing material' + lineParser.getLineNumberString() + '.' );

				}

			}

		}

		let material = null;

		switch ( finishType ) {

			case FINISH_TYPE_DEFAULT:

				material = new MeshStandardMaterial( { roughness: 0.3, metalness: 0 } );
				break;

			case FINISH_TYPE_PEARLESCENT:

				// Try to imitate pearlescency by making the surface glossy
				material = new MeshStandardMaterial( { roughness: 0.3, metalness: 0.25 } );
				break;

			case FINISH_TYPE_CHROME:

				// Mirror finish surface
				material = new MeshStandardMaterial( { roughness: 0, metalness: 1 } );
				break;

			case FINISH_TYPE_RUBBER:

				// Rubber finish
				material = new MeshStandardMaterial( { roughness: 0.9, metalness: 0 } );
				break;

			case FINISH_TYPE_MATTE_METALLIC:

				// Brushed metal finish
				material = new MeshStandardMaterial( { roughness: 0.8, metalness: 0.4 } );
				break;

			case FINISH_TYPE_METAL:

				// Average metal finish
				material = new MeshStandardMaterial( { roughness: 0.2, metalness: 0.85 } );
				break;

			default:
				// Should not happen
				break;

		}

		material.color.setStyle( fillColor, COLOR_SPACE_LDRAW );
		material.transparent = isTransparent;
		material.premultipliedAlpha = true;
		material.opacity = alpha;
		material.depthWrite = ! isTransparent;

		material.polygonOffset = true;
		material.polygonOffsetFactor = 1;

		if ( luminance !== 0 ) {

			material.emissive.setStyle( fillColor, COLOR_SPACE_LDRAW ).multiplyScalar( luminance );

		}

		if ( ! edgeMaterial ) {

			// This is the material used for edges
			edgeMaterial = new LineBasicMaterial( {
				color: new Color().setStyle( edgeColor, COLOR_SPACE_LDRAW ),
				transparent: isTransparent,
				opacity: alpha,
				depthWrite: ! isTransparent
			} );
			edgeMaterial.color;
			edgeMaterial.userData.code = code;
			edgeMaterial.name = name + ' - Edge';

			if ( this.ConditionalLineMaterial === null ) {

				throw new Error( 'THREE.LDrawLoader: ConditionalLineMaterial type must be specified via .setConditionalLineMaterial().' );

			}

			// This is the material used for conditional edges
			const conditionalEdgeMaterial = new this.ConditionalLineMaterial( {

				fog: true,
				transparent: isTransparent,
				depthWrite: ! isTransparent,
				color: new Color().setStyle( edgeColor, COLOR_SPACE_LDRAW ),
				opacity: alpha,

			} );
			conditionalEdgeMaterial.userData.code = code;
			conditionalEdgeMaterial.name = name + ' - Conditional Edge';

			this.conditionalEdgeMaterialCache.set( edgeMaterial, conditionalEdgeMaterial );

		}

		material.userData.code = code;
		material.name = name;

		this.edgeMaterialCache.set( material, edgeMaterial );

		this.addMaterial( material );

		return material;

		function parseLuminance( token ) {

			// Returns success

			let lum;

			if ( token.startsWith( 'LUMINANCE' ) ) {

				lum = parseInt( token.substring( 9 ) );

			} else {

				lum = parseInt( token );

			}

			if ( isNaN( lum ) ) {

				return false;

			}

			luminance = Math.max( 0, Math.min( 1, lum / 255 ) );

			return true;

		}

	}
```
</details>

##### `computeBuildingSteps(model: any): void`

<details><summary>Code</summary>

```ts
computeBuildingSteps( model ) {

		// Sets userdata.buildingStep number in Group objects and userData.numBuildingSteps number in the root Group object.

		let stepNumber = 0;

		model.traverse( c => {

			if ( c.isGroup ) {

				if ( c.userData.startingBuildingStep ) {

					stepNumber ++;

				}

				c.userData.buildingStep = stepNumber;

			}

		} );

		model.userData.numBuildingSteps = stepNumber + 1;

	}
```
</details>


---