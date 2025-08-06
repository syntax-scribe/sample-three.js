[⬅️ Back to Table of Contents](../../index.md)

# 📄 `BatchedMesh.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 41 |
| 🧱 Classes | 2 |
| 📦 Imports | 16 |
| 📊 Variables & Constants | 119 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/objects/BatchedMesh.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferAttribute` | `../core/BufferAttribute.js` |
| `BufferGeometry` | `../core/BufferGeometry.js` |
| `DataTexture` | `../textures/DataTexture.js` |
| `FloatType` | `../constants.js` |
| `RedIntegerFormat` | `../constants.js` |
| `UnsignedIntType` | `../constants.js` |
| `RGBAFormat` | `../constants.js` |
| `Matrix4` | `../math/Matrix4.js` |
| `Mesh` | `./Mesh.js` |
| `ColorManagement` | `../math/ColorManagement.js` |
| `Box3` | `../math/Box3.js` |
| `Sphere` | `../math/Sphere.js` |
| `Frustum` | `../math/Frustum.js` |
| `Vector3` | `../math/Vector3.js` |
| `Color` | `../math/Color.js` |
| `FrustumArray` | `../math/FrustumArray.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `pool` | `any[]` | let/var | `this.pool` | ✗ |
| `list` | `any[]` | let/var | `this.list` | ✗ |
| `item` | `any` | let/var | `pool[ this.index ]` | ✗ |
| `_matrix` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_whiteColor` | `Color` | let/var | `new Color( 1, 1, 1 )` | ✗ |
| `_frustum` | `Frustum` | let/var | `new Frustum()` | ✗ |
| `_frustumArray` | `FrustumArray` | let/var | `new FrustumArray()` | ✗ |
| `_box` | `Box3` | let/var | `new Box3()` | ✗ |
| `_sphere` | `Sphere` | let/var | `new Sphere()` | ✗ |
| `_vector` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_forward` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_temp` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_renderList` | `MultiDrawRenderList` | let/var | `new MultiDrawRenderList()` | ✗ |
| `_mesh` | `Mesh` | let/var | `new Mesh()` | ✗ |
| `_batchIntersects` | `any[]` | let/var | `[]` | ✗ |
| `itemSize` | `any` | let/var | `target.itemSize` | ✗ |
| `vertexCount` | `any` | let/var | `src.count` | ✗ |
| `matricesArray` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( size * size * 4 )` | ✗ |
| `matricesTexture` | `DataTexture` | let/var | `new DataTexture( matricesArray, size, size, RGBAFormat, FloatType )` | ✗ |
| `indirectArray` | `Uint32Array<ArrayBuffer>` | let/var | `new Uint32Array( size * size )` | ✗ |
| `indirectTexture` | `DataTexture` | let/var | `new DataTexture( indirectArray, size, size, RedIntegerFormat, UnsignedIntType )` | ✗ |
| `colorsTexture` | `DataTexture` | let/var | `new DataTexture( colorsArray, size, size, RGBAFormat, FloatType )` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `maxVertexCount` | `number` | let/var | `this._maxVertexCount` | ✗ |
| `maxIndexCount` | `number` | let/var | `this._maxIndexCount` | ✗ |
| `dstArray` | `any` | let/var | `new array.constructor( maxVertexCount * itemSize )` | ✗ |
| `dstAttribute` | `BufferAttribute` | let/var | `new BufferAttribute( dstArray, itemSize, normalized )` | ✗ |
| `indexArray` | `Uint32Array<ArrayBuffer> \| Uint16Arr...` | let/var | `maxVertexCount > 65535 ? new Uint32Array( maxIndexCount ) : new Uint16Array( ...` | ✗ |
| `batchGeometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `instanceInfo` | `any[]` | let/var | `this._instanceInfo` | ✗ |
| `geometryInfoList` | `any[]` | let/var | `this._geometryInfo` | ✗ |
| `boundingBox` | `Box3` | let/var | `this.boundingBox` | ✗ |
| `instanceInfo` | `any[]` | let/var | `this._instanceInfo` | ✗ |
| `geometryId` | `any` | let/var | `instanceInfo[ i ].geometryIndex` | ✗ |
| `boundingSphere` | `Sphere` | let/var | `this.boundingSphere` | ✗ |
| `instanceInfo` | `any[]` | let/var | `this._instanceInfo` | ✗ |
| `geometryId` | `any` | let/var | `instanceInfo[ i ].geometryIndex` | ✗ |
| `atCapacity` | `boolean` | let/var | `this._instanceInfo.length >= this.maxInstanceCount` | ✗ |
| `instanceInfo` | `{ visible: boolean; active: boolean; ...` | let/var | `{ visible: true, active: true, geometryIndex: geometryId, }` | ✗ |
| `drawId` | `any` | let/var | `null` | ✗ |
| `matricesTexture` | `any` | let/var | `this._matricesTexture` | ✗ |
| `colorsTexture` | `any` | let/var | `this._colorsTexture` | ✗ |
| `geometryInfo` | `{ vertexStart: number; vertexCount: n...` | let/var | `{ // geometry information vertexStart: - 1, vertexCount: - 1, reservedVertexC...` | ✗ |
| `geometryInfoList` | `any[]` | let/var | `this._geometryInfo` | ✗ |
| `hasIndex` | `boolean` | let/var | `index !== null` | ✗ |
| `geometryId` | `any` | let/var | `*not shown*` | ✗ |
| `batchGeometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `hasIndex` | `boolean` | let/var | `batchGeometry.getIndex() !== null` | ✗ |
| `geometryInfo` | `any` | let/var | `this._geometryInfo[ geometryId ]` | ✗ |
| `vertexStart` | `any` | let/var | `geometryInfo.vertexStart` | ✗ |
| `reservedVertexCount` | `any` | let/var | `geometryInfo.reservedVertexCount` | ✗ |
| `itemSize` | `any` | let/var | `srcAttribute.itemSize` | ✗ |
| `index` | `any` | let/var | `vertexStart + i` | ✗ |
| `indexStart` | `any` | let/var | `geometryInfo.indexStart` | ✗ |
| `reservedIndexCount` | `any` | let/var | `geometryInfo.reservedIndexCount` | ✗ |
| `geometryInfoList` | `any[]` | let/var | `this._geometryInfo` | ✗ |
| `instanceInfo` | `any[]` | let/var | `this._instanceInfo` | ✗ |
| `nextVertexStart` | `number` | let/var | `0` | ✗ |
| `nextIndexStart` | `number` | let/var | `0` | ✗ |
| `geometryInfoList` | `any[]` | let/var | `this._geometryInfo` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `index` | `number` | let/var | `indices[ i ]` | ✗ |
| `geometryInfo` | `any` | let/var | `geometryInfoList[ index ]` | ✗ |
| `index` | `BufferAttribute` | let/var | `geometry.index` | ✗ |
| `array` | `TypedArray` | let/var | `index.array` | ✗ |
| `elementDelta` | `number` | let/var | `nextVertexStart - vertexStart` | ✗ |
| `attributes` | `{ [x: string]: any; }` | let/var | `geometry.attributes` | ✗ |
| `attribute` | `any` | let/var | `attributes[ key ]` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `geometryInfo` | `any` | let/var | `this._geometryInfo[ geometryId ]` | ✗ |
| `box` | `Box3` | let/var | `new Box3()` | ✗ |
| `index` | `BufferAttribute` | let/var | `geometry.index` | ✗ |
| `position` | `any` | let/var | `geometry.attributes.position` | ✗ |
| `iv` | `any` | let/var | `i` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `geometryInfo` | `any` | let/var | `this._geometryInfo[ geometryId ]` | ✗ |
| `sphere` | `Sphere` | let/var | `new Sphere()` | ✗ |
| `index` | `BufferAttribute` | let/var | `geometry.index` | ✗ |
| `position` | `any` | let/var | `geometry.attributes.position` | ✗ |
| `maxRadiusSq` | `number` | let/var | `0` | ✗ |
| `iv` | `any` | let/var | `i` | ✗ |
| `matricesTexture` | `any` | let/var | `this._matricesTexture` | ✗ |
| `matricesArray` | `any` | let/var | `this._matricesTexture.image.data` | ✗ |
| `geometryInfo` | `any` | let/var | `this._geometryInfo[ geometryId ]` | ✗ |
| `availableInstanceIds` | `any[]` | let/var | `this._availableInstanceIds` | ✗ |
| `instanceInfo` | `any[]` | let/var | `this._instanceInfo` | ✗ |
| `multiDrawCounts` | `Int32Array<ArrayBuffer>` | let/var | `new Int32Array( maxInstanceCount )` | ✗ |
| `multiDrawStarts` | `Int32Array<ArrayBuffer>` | let/var | `new Int32Array( maxInstanceCount )` | ✗ |
| `indirectTexture` | `any` | let/var | `this._indirectTexture` | ✗ |
| `matricesTexture` | `any` | let/var | `this._matricesTexture` | ✗ |
| `colorsTexture` | `any` | let/var | `this._colorsTexture` | ✗ |
| `oldGeometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `geometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `instanceInfo` | `any[]` | let/var | `this._instanceInfo` | ✗ |
| `geometryInfoList` | `any[]` | let/var | `this._geometryInfo` | ✗ |
| `matrixWorld` | `Matrix4` | let/var | `this.matrixWorld` | ✗ |
| `batchGeometry` | `BufferGeometry` | let/var | `this.geometry` | ✗ |
| `geometryId` | `any` | let/var | `instanceInfo[ i ].geometryIndex` | ✗ |
| `geometryInfo` | `any` | let/var | `geometryInfoList[ geometryId ]` | ✗ |
| `intersect` | `any` | let/var | `_batchIntersects[ j ]` | ✗ |
| `bytesPerElement` | `any` | let/var | `index === null ? 1 : index.array.BYTES_PER_ELEMENT` | ✗ |
| `instanceInfo` | `any[]` | let/var | `this._instanceInfo` | ✗ |
| `multiDrawStarts` | `Int32Array<ArrayBuffer>` | let/var | `this._multiDrawStarts` | ✗ |
| `multiDrawCounts` | `Int32Array<ArrayBuffer>` | let/var | `this._multiDrawCounts` | ✗ |
| `geometryInfoList` | `any[]` | let/var | `this._geometryInfo` | ✗ |
| `perObjectFrustumCulled` | `boolean` | let/var | `this.perObjectFrustumCulled` | ✗ |
| `indirectTexture` | `any` | let/var | `this._indirectTexture` | ✗ |
| `indirectArray` | `any` | let/var | `indirectTexture.image.data` | ✗ |
| `frustum` | `Frustum \| FrustumArray` | let/var | `camera.isArrayCamera ? _frustumArray : _frustum` | ✗ |
| `multiDrawCount` | `number` | let/var | `0` | ✗ |
| `geometryId` | `any` | let/var | `instanceInfo[ i ].geometryIndex` | ✗ |
| `culled` | `boolean` | let/var | `false` | ✗ |
| `geometryInfo` | `any` | let/var | `geometryInfoList[ geometryId ]` | ✗ |
| `list` | `any[]` | let/var | `_renderList.list` | ✗ |
| `customSort` | `Function` | let/var | `this.customSort` | ✗ |
| `item` | `any` | let/var | `list[ i ]` | ✗ |
| `geometryId` | `any` | let/var | `instanceInfo[ i ].geometryIndex` | ✗ |
| `culled` | `boolean` | let/var | `false` | ✗ |
| `geometryInfo` | `any` | let/var | `geometryInfoList[ geometryId ]` | ✗ |


---

## Functions

### `ascIdSort(a: any, b: any): number`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function ascIdSort( a, b ) {

	return a - b;

}
```
</details>

### `sortOpaque(a: any, b: any): number`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function sortOpaque( a, b ) {

	return a.z - b.z;

}
```
</details>

### `sortTransparent(a: any, b: any): number`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
function sortTransparent( a, b ) {

	return b.z - a.z;

}
```
</details>

### `MultiDrawRenderList.push(start: any, count: any, z: any, index: any): void`

**Parameters:**

- **`start`** `any`
- **`count`** `any`
- **`z`** `any`
- **`index`** `any`

**Returns:** `void`

**Calls:**

- `pool.push`
- `list.push`

<details><summary>Code</summary>

```typescript
push( start, count, z, index ) {

		const pool = this.pool;
		const list = this.list;
		if ( this.index >= pool.length ) {

			pool.push( {

				start: - 1,
				count: - 1,
				z: - 1,
				index: - 1,

			} );

		}

		const item = pool[ this.index ];
		list.push( item );
		this.index ++;

		item.start = start;
		item.count = count;
		item.z = z;
		item.index = index;

	}
```
</details>

### `MultiDrawRenderList.reset(): void`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
reset() {

		this.list.length = 0;
		this.index = 0;

	}
```
</details>

### `copyAttributeData(src: any, target: any, targetOffset: number): void`

**Parameters:**

- **`src`** `any`
- **`target`** `any`
- **`targetOffset`** `number`

**Returns:** `void`

**Calls:**

- `target.setComponent`
- `src.getComponent`
- `target.array.set`

**Internal Comments:**
```
// use the component getters and setters if the array data cannot (x2)
// be copied directly (x2)
// faster copy approach using typed array set function (x5)
```

<details><summary>Code</summary>

```typescript
function copyAttributeData( src, target, targetOffset = 0 ) {

	const itemSize = target.itemSize;
	if ( src.isInterleavedBufferAttribute || src.array.constructor !== target.array.constructor ) {

		// use the component getters and setters if the array data cannot
		// be copied directly
		const vertexCount = src.count;
		for ( let i = 0; i < vertexCount; i ++ ) {

			for ( let c = 0; c < itemSize; c ++ ) {

				target.setComponent( i + targetOffset, c, src.getComponent( i, c ) );

			}

		}

	} else {

		// faster copy approach using typed array set function
		target.array.set( src.array, targetOffset * itemSize );

	}

	target.needsUpdate = true;

}
```
</details>

### `copyArrayContents(src: any, target: any): void`

**Parameters:**

- **`src`** `any`
- **`target`** `any`

**Returns:** `void`

**Calls:**

- `Math.min`
- `target.set`

**Internal Comments:**
```
// if arrays are of a different type (eg due to index size increasing) then data must be per-element copied (x2)
// if the arrays use the same data layout we can use a fast block copy (x2)
```

<details><summary>Code</summary>

```typescript
function copyArrayContents( src, target ) {

	if ( src.constructor !== target.constructor ) {

		// if arrays are of a different type (eg due to index size increasing) then data must be per-element copied
		const len = Math.min( src.length, target.length );
		for ( let i = 0; i < len; i ++ ) {

			target[ i ] = src[ i ];

		}

	} else {

		// if the arrays use the same data layout we can use a fast block copy
		const len = Math.min( src.length, target.length );
		target.set( new src.constructor( src.buffer, 0, len ) );

	}

}
```
</details>

### `BatchedMesh._initMatricesTexture(): void`

**Returns:** `void`

**Calls:**

- `Math.sqrt`
- `Math.ceil`
- `Math.max`

**Internal Comments:**
```
// layout (1 matrix = 4 pixels) (x2)
//      RGBA RGBA RGBA RGBA (=> column1, column2, column3, column4) (x2)
//  with  8x8  pixel texture max   16 matrices * 4 pixels =  (8 * 8) (x2)
//       16x16 pixel texture max   64 matrices * 4 pixels = (16 * 16) (x2)
//       32x32 pixel texture max  256 matrices * 4 pixels = (32 * 32) (x2)
//       64x64 pixel texture max 1024 matrices * 4 pixels = (64 * 64) (x2)
```

<details><summary>Code</summary>

```typescript
_initMatricesTexture() {

		// layout (1 matrix = 4 pixels)
		//      RGBA RGBA RGBA RGBA (=> column1, column2, column3, column4)
		//  with  8x8  pixel texture max   16 matrices * 4 pixels =  (8 * 8)
		//       16x16 pixel texture max   64 matrices * 4 pixels = (16 * 16)
		//       32x32 pixel texture max  256 matrices * 4 pixels = (32 * 32)
		//       64x64 pixel texture max 1024 matrices * 4 pixels = (64 * 64)

		let size = Math.sqrt( this._maxInstanceCount * 4 ); // 4 pixels needed for 1 matrix
		size = Math.ceil( size / 4 ) * 4;
		size = Math.max( size, 4 );

		const matricesArray = new Float32Array( size * size * 4 ); // 4 floats per RGBA pixel
		const matricesTexture = new DataTexture( matricesArray, size, size, RGBAFormat, FloatType );

		this._matricesTexture = matricesTexture;

	}
```
</details>

### `BatchedMesh._initIndirectTexture(): void`

**Returns:** `void`

**Calls:**

- `Math.sqrt`
- `Math.ceil`

<details><summary>Code</summary>

```typescript
_initIndirectTexture() {

		let size = Math.sqrt( this._maxInstanceCount );
		size = Math.ceil( size );

		const indirectArray = new Uint32Array( size * size );
		const indirectTexture = new DataTexture( indirectArray, size, size, RedIntegerFormat, UnsignedIntType );

		this._indirectTexture = indirectTexture;

	}
```
</details>

### `BatchedMesh._initColorsTexture(): void`

**Returns:** `void`

**Calls:**

- `Math.sqrt`
- `Math.ceil`
- `new Float32Array( size * size * 4 ).fill`

**Internal Comments:**
```
// 4 floats per RGBA pixel initialized to white (x2)
```

<details><summary>Code</summary>

```typescript
_initColorsTexture() {

		let size = Math.sqrt( this._maxInstanceCount );
		size = Math.ceil( size );

		// 4 floats per RGBA pixel initialized to white
		const colorsArray = new Float32Array( size * size * 4 ).fill( 1 );
		const colorsTexture = new DataTexture( colorsArray, size, size, RGBAFormat, FloatType );
		colorsTexture.colorSpace = ColorManagement.workingColorSpace;

		this._colorsTexture = colorsTexture;

	}
```
</details>

### `BatchedMesh._initializeGeometry(reference: any): void`

**Parameters:**

- **`reference`** `any`

**Returns:** `void`

**Calls:**

- `reference.getAttribute`
- `geometry.setAttribute`
- `reference.getIndex`
- `geometry.setIndex`

**Internal Comments:**
```
// Reserve last u16 index for primitive restart. (x2)
```

<details><summary>Code</summary>

```typescript
_initializeGeometry( reference ) {

		const geometry = this.geometry;
		const maxVertexCount = this._maxVertexCount;
		const maxIndexCount = this._maxIndexCount;
		if ( this._geometryInitialized === false ) {

			for ( const attributeName in reference.attributes ) {

				const srcAttribute = reference.getAttribute( attributeName );
				const { array, itemSize, normalized } = srcAttribute;

				const dstArray = new array.constructor( maxVertexCount * itemSize );
				const dstAttribute = new BufferAttribute( dstArray, itemSize, normalized );

				geometry.setAttribute( attributeName, dstAttribute );

			}

			if ( reference.getIndex() !== null ) {

				// Reserve last u16 index for primitive restart.
				const indexArray = maxVertexCount > 65535
					? new Uint32Array( maxIndexCount )
					: new Uint16Array( maxIndexCount );

				geometry.setIndex( new BufferAttribute( indexArray, 1 ) );

			}

			this._geometryInitialized = true;

		}

	}
```
</details>

### `BatchedMesh._validateGeometry(geometry: any): void`

**Parameters:**

- **`geometry`** `any`

**Returns:** `void`

**Calls:**

- `Boolean`
- `geometry.getIndex`
- `batchGeometry.getIndex`
- `geometry.hasAttribute`
- `geometry.getAttribute`
- `batchGeometry.getAttribute`

**Internal Comments:**
```
// check to ensure the geometries are using consistent attributes and indices (x2)
```

<details><summary>Code</summary>

```typescript
_validateGeometry( geometry ) {

		// check to ensure the geometries are using consistent attributes and indices
		const batchGeometry = this.geometry;
		if ( Boolean( geometry.getIndex() ) !== Boolean( batchGeometry.getIndex() ) ) {

			throw new Error( 'THREE.BatchedMesh: All geometries must consistently have "index".' );

		}

		for ( const attributeName in batchGeometry.attributes ) {

			if ( ! geometry.hasAttribute( attributeName ) ) {

				throw new Error( `THREE.BatchedMesh: Added geometry missing "${ attributeName }". All geometries must have consistent attributes.` );

			}

			const srcAttribute = geometry.getAttribute( attributeName );
			const dstAttribute = batchGeometry.getAttribute( attributeName );
			if ( srcAttribute.itemSize !== dstAttribute.itemSize || srcAttribute.normalized !== dstAttribute.normalized ) {

				throw new Error( 'THREE.BatchedMesh: All attributes must have a consistent itemSize and normalized value.' );

			}

		}

	}
```
</details>

### `BatchedMesh.validateInstanceId(instanceId: number): void`

**JSDoc:**
```typescript
/**
	 * Validates the instance defined by the given ID.
	 *
	 * @param {number} instanceId - The instance to validate.
	 */
```

**Parameters:**

- **`instanceId`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
validateInstanceId( instanceId ) {

		const instanceInfo = this._instanceInfo;
		if ( instanceId < 0 || instanceId >= instanceInfo.length || instanceInfo[ instanceId ].active === false ) {

			throw new Error( `THREE.BatchedMesh: Invalid instanceId ${instanceId}. Instance is either out of range or has been deleted.` );

		}

	}
```
</details>

### `BatchedMesh.validateGeometryId(geometryId: number): void`

**JSDoc:**
```typescript
/**
	 * Validates the geometry defined by the given ID.
	 *
	 * @param {number} geometryId - The geometry to validate.
	 */
```

**Parameters:**

- **`geometryId`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
validateGeometryId( geometryId ) {

		const geometryInfoList = this._geometryInfo;
		if ( geometryId < 0 || geometryId >= geometryInfoList.length || geometryInfoList[ geometryId ].active === false ) {

			throw new Error( `THREE.BatchedMesh: Invalid geometryId ${geometryId}. Geometry is either out of range or has been deleted.` );

		}

	}
```
</details>

### `BatchedMesh.setCustomSort(func: Function): BatchedMesh`

**JSDoc:**
```typescript
/**
	 * Takes a sort a function that is run before render. The function takes a list of instances to
	 * sort and a camera. The objects in the list include a "z" field to perform a depth-ordered sort with.
	 *
	 * @param {Function} func - The custom sort function.
	 * @return {BatchedMesh} A reference to this batched mesh.
	 */
```

**Parameters:**

- **`func`** `Function`

**Returns:** `BatchedMesh`

<details><summary>Code</summary>

```typescript
setCustomSort( func ) {

		this.customSort = func;
		return this;

	}
```
</details>

### `BatchedMesh.computeBoundingBox(): void`

**JSDoc:**
```typescript
/**
	 * Computes the bounding box, updating {@link BatchedMesh#boundingBox}.
	 * Bounding boxes aren't computed by default. They need to be explicitly computed,
	 * otherwise they are `null`.
	 */
```

**Returns:** `void`

**Calls:**

- `boundingBox.makeEmpty`
- `this.getMatrixAt`
- `this.getBoundingBoxAt( geometryId, _box ).applyMatrix4`
- `boundingBox.union`

<details><summary>Code</summary>

```typescript
computeBoundingBox() {

		if ( this.boundingBox === null ) {

			this.boundingBox = new Box3();

		}

		const boundingBox = this.boundingBox;
		const instanceInfo = this._instanceInfo;

		boundingBox.makeEmpty();
		for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

			if ( instanceInfo[ i ].active === false ) continue;

			const geometryId = instanceInfo[ i ].geometryIndex;
			this.getMatrixAt( i, _matrix );
			this.getBoundingBoxAt( geometryId, _box ).applyMatrix4( _matrix );
			boundingBox.union( _box );

		}

	}
```
</details>

### `BatchedMesh.computeBoundingSphere(): void`

**JSDoc:**
```typescript
/**
	 * Computes the bounding sphere, updating {@link BatchedMesh#boundingSphere}.
	 * Bounding spheres aren't computed by default. They need to be explicitly computed,
	 * otherwise they are `null`.
	 */
```

**Returns:** `void`

**Calls:**

- `boundingSphere.makeEmpty`
- `this.getMatrixAt`
- `this.getBoundingSphereAt( geometryId, _sphere ).applyMatrix4`
- `boundingSphere.union`

<details><summary>Code</summary>

```typescript
computeBoundingSphere() {

		if ( this.boundingSphere === null ) {

			this.boundingSphere = new Sphere();

		}

		const boundingSphere = this.boundingSphere;
		const instanceInfo = this._instanceInfo;

		boundingSphere.makeEmpty();
		for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

			if ( instanceInfo[ i ].active === false ) continue;

			const geometryId = instanceInfo[ i ].geometryIndex;
			this.getMatrixAt( i, _matrix );
			this.getBoundingSphereAt( geometryId, _sphere ).applyMatrix4( _matrix );
			boundingSphere.union( _sphere );

		}

	}
```
</details>

### `BatchedMesh.addInstance(geometryId: number): number`

**JSDoc:**
```typescript
/**
	 * Adds a new instance to the batch using the geometry of the given ID and returns
	 * a new id referring to the new instance to be used by other functions.
	 *
	 * @param {number} geometryId - The ID of a previously added geometry via {@link BatchedMesh#addGeometry}.
	 * @return {number} The instance ID.
	 */
```

**Parameters:**

- **`geometryId`** `number`

**Returns:** `number`

**Calls:**

- `this._availableInstanceIds.sort`
- `this._availableInstanceIds.shift`
- `this._instanceInfo.push`
- `_matrix.identity().toArray`
- `_whiteColor.toArray`

**Internal Comments:**
```
// ensure we're not over geometry
// Prioritize using previously freed instance ids
```

<details><summary>Code</summary>

```typescript
addInstance( geometryId ) {

		const atCapacity = this._instanceInfo.length >= this.maxInstanceCount;

		// ensure we're not over geometry
		if ( atCapacity && this._availableInstanceIds.length === 0 ) {

			throw new Error( 'THREE.BatchedMesh: Maximum item count reached.' );

		}

		const instanceInfo = {
			visible: true,
			active: true,
			geometryIndex: geometryId,
		};

		let drawId = null;

		// Prioritize using previously freed instance ids
		if ( this._availableInstanceIds.length > 0 ) {

			this._availableInstanceIds.sort( ascIdSort );

			drawId = this._availableInstanceIds.shift();
			this._instanceInfo[ drawId ] = instanceInfo;

		} else {

			drawId = this._instanceInfo.length;
			this._instanceInfo.push( instanceInfo );

		}

		const matricesTexture = this._matricesTexture;
		_matrix.identity().toArray( matricesTexture.image.data, drawId * 16 );
		matricesTexture.needsUpdate = true;

		const colorsTexture = this._colorsTexture;
		if ( colorsTexture ) {

			_whiteColor.toArray( colorsTexture.image.data, drawId * 4 );
			colorsTexture.needsUpdate = true;

		}

		this._visibilityChanged = true;
		return drawId;

	}
```
</details>

### `BatchedMesh.addGeometry(geometry: BufferGeometry, reservedVertexCount: number, reservedIndexCount: number): number`

**JSDoc:**
```typescript
/**
	 * Adds the given geometry to the batch and returns the associated
	 * geometry id referring to it to be used in other functions.
	 *
	 * @param {BufferGeometry} geometry - The geometry to add.
	 * @param {number} [reservedVertexCount=-1] - Optional parameter specifying the amount of
	 * vertex buffer space to reserve for the added geometry. This is necessary if it is planned
	 * to set a new geometry at this index at a later time that is larger than the original geometry.
	 * Defaults to the length of the given geometry vertex buffer.
	 * @param {number} [reservedIndexCount=-1] - Optional parameter specifying the amount of index
	 * buffer space to reserve for the added geometry. This is necessary if it is planned to set a
	 * new geometry at this index at a later time that is larger than the original geometry. Defaults to
	 * the length of the given geometry index buffer.
	 * @return {number} The geometry ID.
	 */
```

**Parameters:**

- **`geometry`** `BufferGeometry`
- **`reservedVertexCount`** `number`
- **`reservedIndexCount`** `number`

**Returns:** `number`

**Calls:**

- `this._initializeGeometry`
- `this._validateGeometry`
- `geometry.getAttribute`
- `geometry.getIndex`
- `this._availableGeometryIds.sort`
- `this._availableGeometryIds.shift`
- `geometryInfoList.push`
- `this.setGeometryAt`

**Internal Comments:**
```
// geometry information (x2)
// draw range information (x2)
// state (x2)
// update id (x2)
// update the geometry (x4)
// increment the next geometry position (x4)
```

<details><summary>Code</summary>

```typescript
addGeometry( geometry, reservedVertexCount = - 1, reservedIndexCount = - 1 ) {

		this._initializeGeometry( geometry );

		this._validateGeometry( geometry );

		const geometryInfo = {
			// geometry information
			vertexStart: - 1,
			vertexCount: - 1,
			reservedVertexCount: - 1,

			indexStart: - 1,
			indexCount: - 1,
			reservedIndexCount: - 1,

			// draw range information
			start: - 1,
			count: - 1,

			// state
			boundingBox: null,
			boundingSphere: null,
			active: true,
		};

		const geometryInfoList = this._geometryInfo;
		geometryInfo.vertexStart = this._nextVertexStart;
		geometryInfo.reservedVertexCount = reservedVertexCount === - 1 ? geometry.getAttribute( 'position' ).count : reservedVertexCount;

		const index = geometry.getIndex();
		const hasIndex = index !== null;
		if ( hasIndex ) {

			geometryInfo.indexStart = this._nextIndexStart;
			geometryInfo.reservedIndexCount = reservedIndexCount === - 1 ? index.count : reservedIndexCount;

		}

		if (
			geometryInfo.indexStart !== - 1 &&
			geometryInfo.indexStart + geometryInfo.reservedIndexCount > this._maxIndexCount ||
			geometryInfo.vertexStart + geometryInfo.reservedVertexCount > this._maxVertexCount
		) {

			throw new Error( 'THREE.BatchedMesh: Reserved space request exceeds the maximum buffer size.' );

		}

		// update id
		let geometryId;
		if ( this._availableGeometryIds.length > 0 ) {

			this._availableGeometryIds.sort( ascIdSort );

			geometryId = this._availableGeometryIds.shift();
			geometryInfoList[ geometryId ] = geometryInfo;


		} else {

			geometryId = this._geometryCount;
			this._geometryCount ++;
			geometryInfoList.push( geometryInfo );

		}

		// update the geometry
		this.setGeometryAt( geometryId, geometry );

		// increment the next geometry position
		this._nextIndexStart = geometryInfo.indexStart + geometryInfo.reservedIndexCount;
		this._nextVertexStart = geometryInfo.vertexStart + geometryInfo.reservedVertexCount;

		return geometryId;

	}
```
</details>

### `BatchedMesh.setGeometryAt(geometryId: number, geometry: BufferGeometry): number`

**JSDoc:**
```typescript
/**
	 * Replaces the geometry at the given ID with the provided geometry. Throws an error if there
	 * is not enough space reserved for geometry. Calling this will change all instances that are
	 * rendering that geometry.
	 *
	 * @param {number} geometryId - The ID of the geometry that should be replaced with the given geometry.
	 * @param {BufferGeometry} geometry - The new geometry.
	 * @return {number} The geometry ID.
	 */
```

**Parameters:**

- **`geometryId`** `number`
- **`geometry`** `BufferGeometry`

**Returns:** `number`

**Calls:**

- `this._validateGeometry`
- `batchGeometry.getIndex`
- `geometry.getIndex`
- `geometry.getAttribute`
- `batchGeometry.getAttribute`
- `copyAttributeData`
- `dstAttribute.setComponent`
- `dstAttribute.addUpdateRange`
- `dstIndex.setX`
- `srcIndex.getX`
- `dstIndex.addUpdateRange`
- `geometry.boundingBox.clone`
- `geometry.boundingSphere.clone`

**Internal Comments:**
```
// copy geometry buffer data over (x2)
// copy attribute data (x2)
// fill the rest in with zeroes (x3)
// copy index
// copy index data over
// update the draw range (x4)
// store the bounding boxes (x4)
```

<details><summary>Code</summary>

```typescript
setGeometryAt( geometryId, geometry ) {

		if ( geometryId >= this._geometryCount ) {

			throw new Error( 'THREE.BatchedMesh: Maximum geometry count reached.' );

		}

		this._validateGeometry( geometry );

		const batchGeometry = this.geometry;
		const hasIndex = batchGeometry.getIndex() !== null;
		const dstIndex = batchGeometry.getIndex();
		const srcIndex = geometry.getIndex();
		const geometryInfo = this._geometryInfo[ geometryId ];
		if (
			hasIndex &&
			srcIndex.count > geometryInfo.reservedIndexCount ||
			geometry.attributes.position.count > geometryInfo.reservedVertexCount
		) {

			throw new Error( 'THREE.BatchedMesh: Reserved space not large enough for provided geometry.' );

		}

		// copy geometry buffer data over
		const vertexStart = geometryInfo.vertexStart;
		const reservedVertexCount = geometryInfo.reservedVertexCount;
		geometryInfo.vertexCount = geometry.getAttribute( 'position' ).count;

		for ( const attributeName in batchGeometry.attributes ) {

			// copy attribute data
			const srcAttribute = geometry.getAttribute( attributeName );
			const dstAttribute = batchGeometry.getAttribute( attributeName );
			copyAttributeData( srcAttribute, dstAttribute, vertexStart );

			// fill the rest in with zeroes
			const itemSize = srcAttribute.itemSize;
			for ( let i = srcAttribute.count, l = reservedVertexCount; i < l; i ++ ) {

				const index = vertexStart + i;
				for ( let c = 0; c < itemSize; c ++ ) {

					dstAttribute.setComponent( index, c, 0 );

				}

			}

			dstAttribute.needsUpdate = true;
			dstAttribute.addUpdateRange( vertexStart * itemSize, reservedVertexCount * itemSize );

		}

		// copy index
		if ( hasIndex ) {

			const indexStart = geometryInfo.indexStart;
			const reservedIndexCount = geometryInfo.reservedIndexCount;
			geometryInfo.indexCount = geometry.getIndex().count;

			// copy index data over
			for ( let i = 0; i < srcIndex.count; i ++ ) {

				dstIndex.setX( indexStart + i, vertexStart + srcIndex.getX( i ) );

			}

			// fill the rest in with zeroes
			for ( let i = srcIndex.count, l = reservedIndexCount; i < l; i ++ ) {

				dstIndex.setX( indexStart + i, vertexStart );

			}

			dstIndex.needsUpdate = true;
			dstIndex.addUpdateRange( indexStart, geometryInfo.reservedIndexCount );

		}

		// update the draw range
		geometryInfo.start = hasIndex ? geometryInfo.indexStart : geometryInfo.vertexStart;
		geometryInfo.count = hasIndex ? geometryInfo.indexCount : geometryInfo.vertexCount;

		// store the bounding boxes
		geometryInfo.boundingBox = null;
		if ( geometry.boundingBox !== null ) {

			geometryInfo.boundingBox = geometry.boundingBox.clone();

		}

		geometryInfo.boundingSphere = null;
		if ( geometry.boundingSphere !== null ) {

			geometryInfo.boundingSphere = geometry.boundingSphere.clone();

		}

		this._visibilityChanged = true;
		return geometryId;

	}
```
</details>

### `BatchedMesh.deleteGeometry(geometryId: number): BatchedMesh`

**JSDoc:**
```typescript
/**
	 * Deletes the geometry defined by the given ID from this batch. Any instances referencing
	 * this geometry will also be removed as a side effect.
	 *
	 * @param {number} geometryId - The ID of the geometry to remove from the batch.
	 * @return {BatchedMesh} A reference to this batched mesh.
	 */
```

**Parameters:**

- **`geometryId`** `number`

**Returns:** `BatchedMesh`

**Calls:**

- `this.deleteInstance`
- `this._availableGeometryIds.push`

**Internal Comments:**
```
// delete any instances associated with this geometry (x2)
```

<details><summary>Code</summary>

```typescript
deleteGeometry( geometryId ) {

		const geometryInfoList = this._geometryInfo;
		if ( geometryId >= geometryInfoList.length || geometryInfoList[ geometryId ].active === false ) {

			return this;

		}

		// delete any instances associated with this geometry
		const instanceInfo = this._instanceInfo;
		for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

			if ( instanceInfo[ i ].active && instanceInfo[ i ].geometryIndex === geometryId ) {

				this.deleteInstance( i );

			}

		}

		geometryInfoList[ geometryId ].active = false;
		this._availableGeometryIds.push( geometryId );
		this._visibilityChanged = true;

		return this;

	}
```
</details>

### `BatchedMesh.deleteInstance(instanceId: number): BatchedMesh`

**JSDoc:**
```typescript
/**
	 * Deletes an existing instance from the batch using the given ID.
	 *
	 * @param {number} instanceId - The ID of the instance to remove from the batch.
	 * @return {BatchedMesh} A reference to this batched mesh.
	 */
```

**Parameters:**

- **`instanceId`** `number`

**Returns:** `BatchedMesh`

**Calls:**

- `this.validateInstanceId`
- `this._availableInstanceIds.push`

<details><summary>Code</summary>

```typescript
deleteInstance( instanceId ) {

		this.validateInstanceId( instanceId );

		this._instanceInfo[ instanceId ].active = false;
		this._availableInstanceIds.push( instanceId );
		this._visibilityChanged = true;

		return this;

	}
```
</details>

### `BatchedMesh.optimize(): BatchedMesh`

**JSDoc:**
```typescript
/**
	 * Repacks the sub geometries in [name] to remove any unused space remaining from
	 * previously deleted geometry, freeing up space to add new geometry.
	 *
	 * @param {number} instanceId - The ID of the instance to remove from the batch.
	 * @return {BatchedMesh} A reference to this batched mesh.
	 */
```

**Returns:** `BatchedMesh`

**Calls:**

- `geometryInfoList
			.map( ( e, i ) => i )
			.sort`
- `index.array.copyWithin`
- `index.addUpdateRange`
- `array.copyWithin`
- `attribute.addUpdateRange`

**Internal Comments:**
```
// track the next indices to copy data to (x2)
// Iterate over all geometry ranges in order sorted from earliest in the geometry buffer to latest (x2)
// in the geometry buffer. Because draw range objects can be reused there is no guarantee of their order. (x2)
// if a geometry range is inactive then don't copy anything (x2)
// if a geometry contains an index buffer then shift it, as well
// shift the index pointers based on how the vertex data will shift (x2)
// adjusting the index must happen first so the original vertex start value is available (x2)
// if a geometry needs to be moved then copy attribute data to overwrite unused space
// step the next geometry points to the shifted position (x4)
```

<details><summary>Code</summary>

```typescript
optimize() {

		// track the next indices to copy data to
		let nextVertexStart = 0;
		let nextIndexStart = 0;

		// Iterate over all geometry ranges in order sorted from earliest in the geometry buffer to latest
		// in the geometry buffer. Because draw range objects can be reused there is no guarantee of their order.
		const geometryInfoList = this._geometryInfo;
		const indices = geometryInfoList
			.map( ( e, i ) => i )
			.sort( ( a, b ) => {

				return geometryInfoList[ a ].vertexStart - geometryInfoList[ b ].vertexStart;

			} );

		const geometry = this.geometry;
		for ( let i = 0, l = geometryInfoList.length; i < l; i ++ ) {

			// if a geometry range is inactive then don't copy anything
			const index = indices[ i ];
			const geometryInfo = geometryInfoList[ index ];
			if ( geometryInfo.active === false ) {

				continue;

			}

			// if a geometry contains an index buffer then shift it, as well
			if ( geometry.index !== null ) {

				if ( geometryInfo.indexStart !== nextIndexStart ) {

					const { indexStart, vertexStart, reservedIndexCount } = geometryInfo;
					const index = geometry.index;
					const array = index.array;

					// shift the index pointers based on how the vertex data will shift
					// adjusting the index must happen first so the original vertex start value is available
					const elementDelta = nextVertexStart - vertexStart;
					for ( let j = indexStart; j < indexStart + reservedIndexCount; j ++ ) {

						array[ j ] = array[ j ] + elementDelta;

					}

					index.array.copyWithin( nextIndexStart, indexStart, indexStart + reservedIndexCount );
					index.addUpdateRange( nextIndexStart, reservedIndexCount );

					geometryInfo.indexStart = nextIndexStart;

				}

				nextIndexStart += geometryInfo.reservedIndexCount;

			}

			// if a geometry needs to be moved then copy attribute data to overwrite unused space
			if ( geometryInfo.vertexStart !== nextVertexStart ) {

				const { vertexStart, reservedVertexCount } = geometryInfo;
				const attributes = geometry.attributes;
				for ( const key in attributes ) {

					const attribute = attributes[ key ];
					const { array, itemSize } = attribute;
					array.copyWithin( nextVertexStart * itemSize, vertexStart * itemSize, ( vertexStart + reservedVertexCount ) * itemSize );
					attribute.addUpdateRange( nextVertexStart * itemSize, reservedVertexCount * itemSize );

				}

				geometryInfo.vertexStart = nextVertexStart;

			}

			nextVertexStart += geometryInfo.reservedVertexCount;
			geometryInfo.start = geometry.index ? geometryInfo.indexStart : geometryInfo.vertexStart;

			// step the next geometry points to the shifted position
			this._nextIndexStart = geometry.index ? geometryInfo.indexStart + geometryInfo.reservedIndexCount : 0;
			this._nextVertexStart = geometryInfo.vertexStart + geometryInfo.reservedVertexCount;

		}

		return this;

	}
```
</details>

### `BatchedMesh.getBoundingBoxAt(geometryId: number, target: Box3): Box3`

**JSDoc:**
```typescript
/**
	 * Returns the bounding box for the given geometry.
	 *
	 * @param {number} geometryId - The ID of the geometry to return the bounding box for.
	 * @param {Box3} target - The target object that is used to store the method's result.
	 * @return {Box3|null} The geometry's bounding box. Returns `null` if no geometry has been found for the given ID.
	 */
```

**Parameters:**

- **`geometryId`** `number`
- **`target`** `Box3`

**Returns:** `Box3`

**Calls:**

- `index.getX`
- `box.expandByPoint`
- `_vector.fromBufferAttribute`
- `target.copy`

**Internal Comments:**
```
// compute bounding box (x2)
```

<details><summary>Code</summary>

```typescript
getBoundingBoxAt( geometryId, target ) {

		if ( geometryId >= this._geometryCount ) {

			return null;

		}

		// compute bounding box
		const geometry = this.geometry;
		const geometryInfo = this._geometryInfo[ geometryId ];
		if ( geometryInfo.boundingBox === null ) {

			const box = new Box3();
			const index = geometry.index;
			const position = geometry.attributes.position;
			for ( let i = geometryInfo.start, l = geometryInfo.start + geometryInfo.count; i < l; i ++ ) {

				let iv = i;
				if ( index ) {

					iv = index.getX( iv );

				}

				box.expandByPoint( _vector.fromBufferAttribute( position, iv ) );

			}

			geometryInfo.boundingBox = box;

		}

		target.copy( geometryInfo.boundingBox );
		return target;

	}
```
</details>

### `BatchedMesh.getBoundingSphereAt(geometryId: number, target: Sphere): Sphere`

**JSDoc:**
```typescript
/**
	 * Returns the bounding sphere for the given geometry.
	 *
	 * @param {number} geometryId - The ID of the geometry to return the bounding sphere for.
	 * @param {Sphere} target - The target object that is used to store the method's result.
	 * @return {Sphere|null} The geometry's bounding sphere. Returns `null` if no geometry has been found for the given ID.
	 */
```

**Parameters:**

- **`geometryId`** `number`
- **`target`** `Sphere`

**Returns:** `Sphere`

**Calls:**

- `this.getBoundingBoxAt`
- `_box.getCenter`
- `index.getX`
- `_vector.fromBufferAttribute`
- `Math.max`
- `sphere.center.distanceToSquared`
- `Math.sqrt`
- `target.copy`

**Internal Comments:**
```
// compute bounding sphere (x2)
```

<details><summary>Code</summary>

```typescript
getBoundingSphereAt( geometryId, target ) {

		if ( geometryId >= this._geometryCount ) {

			return null;

		}

		// compute bounding sphere
		const geometry = this.geometry;
		const geometryInfo = this._geometryInfo[ geometryId ];
		if ( geometryInfo.boundingSphere === null ) {

			const sphere = new Sphere();
			this.getBoundingBoxAt( geometryId, _box );
			_box.getCenter( sphere.center );

			const index = geometry.index;
			const position = geometry.attributes.position;

			let maxRadiusSq = 0;
			for ( let i = geometryInfo.start, l = geometryInfo.start + geometryInfo.count; i < l; i ++ ) {

				let iv = i;
				if ( index ) {

					iv = index.getX( iv );

				}

				_vector.fromBufferAttribute( position, iv );
				maxRadiusSq = Math.max( maxRadiusSq, sphere.center.distanceToSquared( _vector ) );

			}

			sphere.radius = Math.sqrt( maxRadiusSq );
			geometryInfo.boundingSphere = sphere;

		}

		target.copy( geometryInfo.boundingSphere );
		return target;

	}
```
</details>

### `BatchedMesh.setMatrixAt(instanceId: number, matrix: Matrix4): BatchedMesh`

**JSDoc:**
```typescript
/**
	 * Sets the given local transformation matrix to the defined instance.
	 * Negatively scaled matrices are not supported.
	 *
	 * @param {number} instanceId - The ID of an instance to set the matrix of.
	 * @param {Matrix4} matrix - A 4x4 matrix representing the local transformation of a single instance.
	 * @return {BatchedMesh} A reference to this batched mesh.
	 */
```

**Parameters:**

- **`instanceId`** `number`
- **`matrix`** `Matrix4`

**Returns:** `BatchedMesh`

**Calls:**

- `this.validateInstanceId`
- `matrix.toArray`

<details><summary>Code</summary>

```typescript
setMatrixAt( instanceId, matrix ) {

		this.validateInstanceId( instanceId );

		const matricesTexture = this._matricesTexture;
		const matricesArray = this._matricesTexture.image.data;
		matrix.toArray( matricesArray, instanceId * 16 );
		matricesTexture.needsUpdate = true;

		return this;

	}
```
</details>

### `BatchedMesh.getMatrixAt(instanceId: number, matrix: Matrix4): Matrix4`

**JSDoc:**
```typescript
/**
	 * Returns the local transformation matrix of the defined instance.
	 *
	 * @param {number} instanceId - The ID of an instance to get the matrix of.
	 * @param {Matrix4} matrix - The target object that is used to store the method's result.
	 * @return {Matrix4} The instance's local transformation matrix.
	 */
```

**Parameters:**

- **`instanceId`** `number`
- **`matrix`** `Matrix4`

**Returns:** `Matrix4`

**Calls:**

- `this.validateInstanceId`
- `matrix.fromArray`

<details><summary>Code</summary>

```typescript
getMatrixAt( instanceId, matrix ) {

		this.validateInstanceId( instanceId );
		return matrix.fromArray( this._matricesTexture.image.data, instanceId * 16 );

	}
```
</details>

### `BatchedMesh.setColorAt(instanceId: number, color: Color): BatchedMesh`

**JSDoc:**
```typescript
/**
	 * Sets the given color to the defined instance.
	 *
	 * @param {number} instanceId - The ID of an instance to set the color of.
	 * @param {Color} color - The color to set the instance to.
	 * @return {BatchedMesh} A reference to this batched mesh.
	 */
```

**Parameters:**

- **`instanceId`** `number`
- **`color`** `Color`

**Returns:** `BatchedMesh`

**Calls:**

- `this.validateInstanceId`
- `this._initColorsTexture`
- `color.toArray`

<details><summary>Code</summary>

```typescript
setColorAt( instanceId, color ) {

		this.validateInstanceId( instanceId );

		if ( this._colorsTexture === null ) {

			this._initColorsTexture();

		}

		color.toArray( this._colorsTexture.image.data, instanceId * 4 );
		this._colorsTexture.needsUpdate = true;

		return this;

	}
```
</details>

### `BatchedMesh.getColorAt(instanceId: number, color: Color): Color`

**JSDoc:**
```typescript
/**
	 * Returns the color of the defined instance.
	 *
	 * @param {number} instanceId - The ID of an instance to get the color of.
	 * @param {Color} color - The target object that is used to store the method's result.
	 * @return {Color} The instance's color.
	 */
```

**Parameters:**

- **`instanceId`** `number`
- **`color`** `Color`

**Returns:** `Color`

**Calls:**

- `this.validateInstanceId`
- `color.fromArray`

<details><summary>Code</summary>

```typescript
getColorAt( instanceId, color ) {

		this.validateInstanceId( instanceId );
		return color.fromArray( this._colorsTexture.image.data, instanceId * 4 );

	}
```
</details>

### `BatchedMesh.setVisibleAt(instanceId: number, visible: boolean): BatchedMesh`

**JSDoc:**
```typescript
/**
	 * Sets the visibility of the instance.
	 *
	 * @param {number} instanceId - The id of the instance to set the visibility of.
	 * @param {boolean} visible - Whether the instance is visible or not.
	 * @return {BatchedMesh} A reference to this batched mesh.
	 */
```

**Parameters:**

- **`instanceId`** `number`
- **`visible`** `boolean`

**Returns:** `BatchedMesh`

**Calls:**

- `this.validateInstanceId`

<details><summary>Code</summary>

```typescript
setVisibleAt( instanceId, visible ) {

		this.validateInstanceId( instanceId );

		if ( this._instanceInfo[ instanceId ].visible === visible ) {

			return this;

		}

		this._instanceInfo[ instanceId ].visible = visible;
		this._visibilityChanged = true;

		return this;

	}
```
</details>

### `BatchedMesh.getVisibleAt(instanceId: number): boolean`

**JSDoc:**
```typescript
/**
	 * Returns the visibility state of the defined instance.
	 *
	 * @param {number} instanceId - The ID of an instance to get the visibility state of.
	 * @return {boolean} Whether the instance is visible or not.
	 */
```

**Parameters:**

- **`instanceId`** `number`

**Returns:** `boolean`

**Calls:**

- `this.validateInstanceId`

<details><summary>Code</summary>

```typescript
getVisibleAt( instanceId ) {

		this.validateInstanceId( instanceId );

		return this._instanceInfo[ instanceId ].visible;

	}
```
</details>

### `BatchedMesh.setGeometryIdAt(instanceId: number, geometryId: number): BatchedMesh`

**JSDoc:**
```typescript
/**
	 * Sets the geometry ID of the instance at the given index.
	 *
	 * @param {number} instanceId - The ID of the instance to set the geometry ID of.
	 * @param {number} geometryId - The geometry ID to be use by the instance.
	 * @return {BatchedMesh} A reference to this batched mesh.
	 */
```

**Parameters:**

- **`instanceId`** `number`
- **`geometryId`** `number`

**Returns:** `BatchedMesh`

**Calls:**

- `this.validateInstanceId`
- `this.validateGeometryId`

<details><summary>Code</summary>

```typescript
setGeometryIdAt( instanceId, geometryId ) {

		this.validateInstanceId( instanceId );
		this.validateGeometryId( geometryId );

		this._instanceInfo[ instanceId ].geometryIndex = geometryId;

		return this;

	}
```
</details>

### `BatchedMesh.getGeometryIdAt(instanceId: number): number`

**JSDoc:**
```typescript
/**
	 * Returns the geometry ID of the defined instance.
	 *
	 * @param {number} instanceId - The ID of an instance to get the geometry ID of.
	 * @return {number} The instance's geometry ID.
	 */
```

**Parameters:**

- **`instanceId`** `number`

**Returns:** `number`

**Calls:**

- `this.validateInstanceId`

<details><summary>Code</summary>

```typescript
getGeometryIdAt( instanceId ) {

		this.validateInstanceId( instanceId );

		return this._instanceInfo[ instanceId ].geometryIndex;

	}
```
</details>

### `BatchedMesh.getGeometryRangeAt(geometryId: number, target: any): { vertexStart: number; vertexCount: number; reservedVertexCount: number; indexStart: number; indexCount: number; reservedIndexCount: number; start: number; count: number; }`

**JSDoc:**
```typescript
/**
	 * Get the range representing the subset of triangles related to the attached geometry,
	 * indicating the starting offset and count, or `null` if invalid.
	 *
	 * @param {number} geometryId - The id of the geometry to get the range of.
	 * @param {Object} [target] - The target object that is used to store the method's result.
	 * @return {{
	 * 	vertexStart:number,vertexCount:number,reservedVertexCount:number,
	 * 	indexStart:number,indexCount:number,reservedIndexCount:number,
	 * 	start:number,count:number
	 * }} The result object with range data.
	 */
```

**Parameters:**

- **`geometryId`** `number`
- **`target`** `any`

**Returns:** `{ vertexStart: number; vertexCount: number; reservedVertexCount: number; indexStart: number; indexCount: number; reservedIndexCount: number; start: number; count: number; }`

**Calls:**

- `this.validateGeometryId`

<details><summary>Code</summary>

```typescript
getGeometryRangeAt( geometryId, target = {} ) {

		this.validateGeometryId( geometryId );

		const geometryInfo = this._geometryInfo[ geometryId ];
		target.vertexStart = geometryInfo.vertexStart;
		target.vertexCount = geometryInfo.vertexCount;
		target.reservedVertexCount = geometryInfo.reservedVertexCount;

		target.indexStart = geometryInfo.indexStart;
		target.indexCount = geometryInfo.indexCount;
		target.reservedIndexCount = geometryInfo.reservedIndexCount;

		target.start = geometryInfo.start;
		target.count = geometryInfo.count;

		return target;

	}
```
</details>

### `BatchedMesh.setInstanceCount(maxInstanceCount: number): void`

**JSDoc:**
```typescript
/**
	 * Resizes the necessary buffers to support the provided number of instances.
	 * If the provided arguments shrink the number of instances but there are not enough
	 * unused Ids at the end of the list then an error is thrown.
	 *
	 * @param {number} maxInstanceCount - The max number of individual instances that can be added and rendered by the batch.
	*/
```

**Parameters:**

- **`maxInstanceCount`** `number`

**Returns:** `void`

**Calls:**

- `availableInstanceIds.sort`
- `instanceInfo.pop`
- `availableInstanceIds.pop`
- `copyArrayContents`
- `indirectTexture.dispose`
- `this._initIndirectTexture`
- `matricesTexture.dispose`
- `this._initMatricesTexture`
- `colorsTexture.dispose`
- `this._initColorsTexture`

**Internal Comments:**
```
// shrink the available instances as much as possible (x2)
// throw an error if it can't be shrunk to the desired size
// copy the multi draw counts (x2)
// update texture data for instance sampling (x2)
```

<details><summary>Code</summary>

```typescript
setInstanceCount( maxInstanceCount ) {

		// shrink the available instances as much as possible
		const availableInstanceIds = this._availableInstanceIds;
		const instanceInfo = this._instanceInfo;
		availableInstanceIds.sort( ascIdSort );
		while ( availableInstanceIds[ availableInstanceIds.length - 1 ] === instanceInfo.length - 1 ) {

			instanceInfo.pop();
			availableInstanceIds.pop();

		}

		// throw an error if it can't be shrunk to the desired size
		if ( maxInstanceCount < instanceInfo.length ) {

			throw new Error( `BatchedMesh: Instance ids outside the range ${ maxInstanceCount } are being used. Cannot shrink instance count.` );

		}

		// copy the multi draw counts
		const multiDrawCounts = new Int32Array( maxInstanceCount );
		const multiDrawStarts = new Int32Array( maxInstanceCount );
		copyArrayContents( this._multiDrawCounts, multiDrawCounts );
		copyArrayContents( this._multiDrawStarts, multiDrawStarts );

		this._multiDrawCounts = multiDrawCounts;
		this._multiDrawStarts = multiDrawStarts;
		this._maxInstanceCount = maxInstanceCount;

		// update texture data for instance sampling
		const indirectTexture = this._indirectTexture;
		const matricesTexture = this._matricesTexture;
		const colorsTexture = this._colorsTexture;

		indirectTexture.dispose();
		this._initIndirectTexture();
		copyArrayContents( indirectTexture.image.data, this._indirectTexture.image.data );

		matricesTexture.dispose();
		this._initMatricesTexture();
		copyArrayContents( matricesTexture.image.data, this._matricesTexture.image.data );

		if ( colorsTexture ) {

			colorsTexture.dispose();
			this._initColorsTexture();
			copyArrayContents( colorsTexture.image.data, this._colorsTexture.image.data );

		}

	}
```
</details>

### `BatchedMesh.setGeometrySize(maxVertexCount: number, maxIndexCount: number): void`

**JSDoc:**
```typescript
/**
	 * Resizes the available space in the batch's vertex and index buffer attributes to the provided sizes.
	 * If the provided arguments shrink the geometry buffers but there is not enough unused space at the
	 * end of the geometry attributes then an error is thrown.
	 *
	 * @param {number} maxVertexCount - The maximum number of vertices to be used by all unique geometries to resize to.
	 * @param {number} maxIndexCount - The maximum number of indices to be used by all unique geometries to resize to.
	*/
```

**Parameters:**

- **`maxVertexCount`** `number`
- **`maxIndexCount`** `number`

**Returns:** `void`

**Calls:**

- `[ ...this._geometryInfo ].filter`
- `Math.max`
- `validRanges.map`
- `oldGeometry.dispose`
- `this._initializeGeometry`
- `copyArrayContents`

**Internal Comments:**
```
// Check if we can shrink to the requested vertex attribute size (x2)
// Check if we can shrink to the requested index attribute size
// (x2)
// dispose of the previous geometry (x2)
// recreate the geometry needed based on the previous variant (x4)
// copy data from the previous geometry (x2)
```

<details><summary>Code</summary>

```typescript
setGeometrySize( maxVertexCount, maxIndexCount ) {

		// Check if we can shrink to the requested vertex attribute size
		const validRanges = [ ...this._geometryInfo ].filter( info => info.active );
		const requiredVertexLength = Math.max( ...validRanges.map( range => range.vertexStart + range.reservedVertexCount ) );
		if ( requiredVertexLength > maxVertexCount ) {

			throw new Error( `BatchedMesh: Geometry vertex values are being used outside the range ${ maxIndexCount }. Cannot shrink further.` );

		}

		// Check if we can shrink to the requested index attribute size
		if ( this.geometry.index ) {

			const requiredIndexLength = Math.max( ...validRanges.map( range => range.indexStart + range.reservedIndexCount ) );
			if ( requiredIndexLength > maxIndexCount ) {

				throw new Error( `BatchedMesh: Geometry index values are being used outside the range ${ maxIndexCount }. Cannot shrink further.` );

			}

		}

		//

		// dispose of the previous geometry
		const oldGeometry = this.geometry;
		oldGeometry.dispose();

		// recreate the geometry needed based on the previous variant
		this._maxVertexCount = maxVertexCount;
		this._maxIndexCount = maxIndexCount;

		if ( this._geometryInitialized ) {

			this._geometryInitialized = false;
			this.geometry = new BufferGeometry();
			this._initializeGeometry( oldGeometry );

		}

		// copy data from the previous geometry
		const geometry = this.geometry;
		if ( oldGeometry.index ) {

			copyArrayContents( oldGeometry.index.array, geometry.index.array );

		}

		for ( const key in oldGeometry.attributes ) {

			copyArrayContents( oldGeometry.attributes[ key ].array, geometry.attributes[ key ].array );

		}

	}
```
</details>

### `BatchedMesh.raycast(raycaster: any, intersects: any): void`

**Parameters:**

- **`raycaster`** `any`
- **`intersects`** `any`

**Returns:** `void`

**Calls:**

- `_mesh.geometry.setDrawRange`
- `this.getMatrixAt( i, _mesh.matrixWorld ).premultiply`
- `this.getBoundingBoxAt`
- `this.getBoundingSphereAt`
- `_mesh.raycast`
- `intersects.push`

**Internal Comments:**
```
// iterate over each geometry (x4)
// get the intersects (x6)
// add batch id to the intersects
```

<details><summary>Code</summary>

```typescript
raycast( raycaster, intersects ) {

		const instanceInfo = this._instanceInfo;
		const geometryInfoList = this._geometryInfo;
		const matrixWorld = this.matrixWorld;
		const batchGeometry = this.geometry;

		// iterate over each geometry
		_mesh.material = this.material;
		_mesh.geometry.index = batchGeometry.index;
		_mesh.geometry.attributes = batchGeometry.attributes;
		if ( _mesh.geometry.boundingBox === null ) {

			_mesh.geometry.boundingBox = new Box3();

		}

		if ( _mesh.geometry.boundingSphere === null ) {

			_mesh.geometry.boundingSphere = new Sphere();

		}

		for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

			if ( ! instanceInfo[ i ].visible || ! instanceInfo[ i ].active ) {

				continue;

			}

			const geometryId = instanceInfo[ i ].geometryIndex;
			const geometryInfo = geometryInfoList[ geometryId ];
			_mesh.geometry.setDrawRange( geometryInfo.start, geometryInfo.count );

			// get the intersects
			this.getMatrixAt( i, _mesh.matrixWorld ).premultiply( matrixWorld );
			this.getBoundingBoxAt( geometryId, _mesh.geometry.boundingBox );
			this.getBoundingSphereAt( geometryId, _mesh.geometry.boundingSphere );
			_mesh.raycast( raycaster, _batchIntersects );

			// add batch id to the intersects
			for ( let j = 0, l = _batchIntersects.length; j < l; j ++ ) {

				const intersect = _batchIntersects[ j ];
				intersect.object = this;
				intersect.batchId = i;
				intersects.push( intersect );

			}

			_batchIntersects.length = 0;

		}

		_mesh.material = null;
		_mesh.geometry.index = null;
		_mesh.geometry.attributes = {};
		_mesh.geometry.setDrawRange( 0, Infinity );

	}
```
</details>

### `BatchedMesh.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `source.geometry.clone`
- `source.boundingBox.clone`
- `source.boundingSphere.clone`
- `source._geometryInfo.map`
- `info.boundingBox.clone`
- `info.boundingSphere.clone`
- `source._instanceInfo.map`
- `source._availableInstanceIds.slice`
- `source._availableGeometryIds.slice`
- `source._multiDrawCounts.slice`
- `source._multiDrawStarts.slice`
- `source._indirectTexture.clone`
- `this._indirectTexture.image.data.slice`
- `source._matricesTexture.clone`
- `this._matricesTexture.image.data.slice`
- `source._colorsTexture.clone`
- `this._colorsTexture.image.data.slice`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.geometry = source.geometry.clone();
		this.perObjectFrustumCulled = source.perObjectFrustumCulled;
		this.sortObjects = source.sortObjects;
		this.boundingBox = source.boundingBox !== null ? source.boundingBox.clone() : null;
		this.boundingSphere = source.boundingSphere !== null ? source.boundingSphere.clone() : null;

		this._geometryInfo = source._geometryInfo.map( info => ( {
			...info,

			boundingBox: info.boundingBox !== null ? info.boundingBox.clone() : null,
			boundingSphere: info.boundingSphere !== null ? info.boundingSphere.clone() : null,
		} ) );
		this._instanceInfo = source._instanceInfo.map( info => ( { ...info } ) );

		this._availableInstanceIds = source._availableInstanceIds.slice();
		this._availableGeometryIds = source._availableGeometryIds.slice();

		this._nextIndexStart = source._nextIndexStart;
		this._nextVertexStart = source._nextVertexStart;
		this._geometryCount = source._geometryCount;

		this._maxInstanceCount = source._maxInstanceCount;
		this._maxVertexCount = source._maxVertexCount;
		this._maxIndexCount = source._maxIndexCount;

		this._geometryInitialized = source._geometryInitialized;
		this._multiDrawCounts = source._multiDrawCounts.slice();
		this._multiDrawStarts = source._multiDrawStarts.slice();

		this._indirectTexture = source._indirectTexture.clone();
		this._indirectTexture.image.data = this._indirectTexture.image.data.slice();

		this._matricesTexture = source._matricesTexture.clone();
		this._matricesTexture.image.data = this._matricesTexture.image.data.slice();

		if ( this._colorsTexture !== null ) {

			this._colorsTexture = source._colorsTexture.clone();
			this._colorsTexture.image.data = this._colorsTexture.image.data.slice();

		}

		return this;

	}
```
</details>

### `BatchedMesh.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.geometry.dispose`
- `this._matricesTexture.dispose`
- `this._indirectTexture.dispose`
- `this._colorsTexture.dispose`

**Internal Comments:**
```
// Assuming the geometry is not shared with other meshes (x5)
```

<details><summary>Code</summary>

```typescript
dispose() {

		// Assuming the geometry is not shared with other meshes
		this.geometry.dispose();

		this._matricesTexture.dispose();
		this._matricesTexture = null;

		this._indirectTexture.dispose();
		this._indirectTexture = null;

		if ( this._colorsTexture !== null ) {

			this._colorsTexture.dispose();
			this._colorsTexture = null;

		}

	}
```
</details>

### `BatchedMesh.onBeforeRender(renderer: any, scene: any, camera: any, geometry: any, material: any): void`

**Parameters:**

- **`renderer`** `any`
- **`scene`** `any`
- **`camera`** `any`
- **`geometry`** `any`
- **`material`** `any`

**Returns:** `void`

**Calls:**

- `geometry.getIndex`
- `_matrix
				.multiplyMatrices( camera.projectionMatrix, camera.matrixWorldInverse )
				.multiply`
- `_frustum.setFromProjectionMatrix`
- `_matrix.copy( this.matrixWorld ).invert`
- `_vector.setFromMatrixPosition( camera.matrixWorld ).applyMatrix4`
- `_forward.set( 0, 0, - 1 ).transformDirection( camera.matrixWorld ).transformDirection`
- `this.getMatrixAt`
- `this.getBoundingSphereAt( geometryId, _sphere ).applyMatrix4`
- `frustum.intersectsSphere`
- `_temp.subVectors( _sphere.center, _vector ).dot`
- `_renderList.push`
- `list.sort`
- `customSort.call`
- `_renderList.reset`

**Internal Comments:**
```
// if visibility has not changed and frustum culling and object sorting is not required
// then skip iterating over all items
// the indexed version of the multi draw function requires specifying the start (x2)
// offset in bytes. (x2)
// prepare the frustum in the local frame
// get the camera position in the local frame (x6)
// get the bounds in world space (x8)
// determine whether the batched geometry is within the frustum (x4)
// get the distance from camera used for sorting (x2)
// Sort the draw ranges and prep for rendering (x2)
```

<details><summary>Code</summary>

```typescript
onBeforeRender( renderer, scene, camera, geometry, material/*, _group*/ ) {

		// if visibility has not changed and frustum culling and object sorting is not required
		// then skip iterating over all items
		if ( ! this._visibilityChanged && ! this.perObjectFrustumCulled && ! this.sortObjects ) {

			return;

		}

		// the indexed version of the multi draw function requires specifying the start
		// offset in bytes.
		const index = geometry.getIndex();
		const bytesPerElement = index === null ? 1 : index.array.BYTES_PER_ELEMENT;

		const instanceInfo = this._instanceInfo;
		const multiDrawStarts = this._multiDrawStarts;
		const multiDrawCounts = this._multiDrawCounts;
		const geometryInfoList = this._geometryInfo;
		const perObjectFrustumCulled = this.perObjectFrustumCulled;
		const indirectTexture = this._indirectTexture;
		const indirectArray = indirectTexture.image.data;

		const frustum = camera.isArrayCamera ? _frustumArray : _frustum;
		// prepare the frustum in the local frame
		if ( perObjectFrustumCulled && ! camera.isArrayCamera ) {

			_matrix
				.multiplyMatrices( camera.projectionMatrix, camera.matrixWorldInverse )
				.multiply( this.matrixWorld );

			_frustum.setFromProjectionMatrix(
				_matrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

		}

		let multiDrawCount = 0;
		if ( this.sortObjects ) {

			// get the camera position in the local frame
			_matrix.copy( this.matrixWorld ).invert();
			_vector.setFromMatrixPosition( camera.matrixWorld ).applyMatrix4( _matrix );
			_forward.set( 0, 0, - 1 ).transformDirection( camera.matrixWorld ).transformDirection( _matrix );

			for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

				if ( instanceInfo[ i ].visible && instanceInfo[ i ].active ) {

					const geometryId = instanceInfo[ i ].geometryIndex;

					// get the bounds in world space
					this.getMatrixAt( i, _matrix );
					this.getBoundingSphereAt( geometryId, _sphere ).applyMatrix4( _matrix );

					// determine whether the batched geometry is within the frustum
					let culled = false;
					if ( perObjectFrustumCulled ) {

						culled = ! frustum.intersectsSphere( _sphere, camera );

					}

					if ( ! culled ) {

						// get the distance from camera used for sorting
						const geometryInfo = geometryInfoList[ geometryId ];
						const z = _temp.subVectors( _sphere.center, _vector ).dot( _forward );
						_renderList.push( geometryInfo.start, geometryInfo.count, z, i );

					}

				}

			}

			// Sort the draw ranges and prep for rendering
			const list = _renderList.list;
			const customSort = this.customSort;
			if ( customSort === null ) {

				list.sort( material.transparent ? sortTransparent : sortOpaque );

			} else {

				customSort.call( this, list, camera );

			}

			for ( let i = 0, l = list.length; i < l; i ++ ) {

				const item = list[ i ];
				multiDrawStarts[ multiDrawCount ] = item.start * bytesPerElement;
				multiDrawCounts[ multiDrawCount ] = item.count;
				indirectArray[ multiDrawCount ] = item.index;
				multiDrawCount ++;

			}

			_renderList.reset();

		} else {

			for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

				if ( instanceInfo[ i ].visible && instanceInfo[ i ].active ) {

					const geometryId = instanceInfo[ i ].geometryIndex;

					// determine whether the batched geometry is within the frustum
					let culled = false;
					if ( perObjectFrustumCulled ) {

						// get the bounds in world space
						this.getMatrixAt( i, _matrix );
						this.getBoundingSphereAt( geometryId, _sphere ).applyMatrix4( _matrix );
						culled = ! frustum.intersectsSphere( _sphere, camera );

					}

					if ( ! culled ) {

						const geometryInfo = geometryInfoList[ geometryId ];
						multiDrawStarts[ multiDrawCount ] = geometryInfo.start * bytesPerElement;
						multiDrawCounts[ multiDrawCount ] = geometryInfo.count;
						indirectArray[ multiDrawCount ] = i;
						multiDrawCount ++;

					}

				}

			}

		}

		indirectTexture.needsUpdate = true;
		this._multiDrawCount = multiDrawCount;
		this._visibilityChanged = false;

	}
```
</details>

### `BatchedMesh.onBeforeShadow(renderer: any, object: any, camera: any, shadowCamera: any, geometry: any, depthMaterial: any): void`

**Parameters:**

- **`renderer`** `any`
- **`object`** `any`
- **`camera`** `any`
- **`shadowCamera`** `any`
- **`geometry`** `any`
- **`depthMaterial`** `any`

**Returns:** `void`

**Calls:**

- `this.onBeforeRender`

<details><summary>Code</summary>

```typescript
onBeforeShadow( renderer, object, camera, shadowCamera, geometry, depthMaterial/* , group */ ) {

		this.onBeforeRender( renderer, null, shadowCamera, geometry, depthMaterial );

	}
```
</details>


---

## Classes

### `MultiDrawRenderList`

<details><summary>Class Code</summary>

```ts
class MultiDrawRenderList {

	constructor() {

		this.index = 0;
		this.pool = [];
		this.list = [];

	}

	push( start, count, z, index ) {

		const pool = this.pool;
		const list = this.list;
		if ( this.index >= pool.length ) {

			pool.push( {

				start: - 1,
				count: - 1,
				z: - 1,
				index: - 1,

			} );

		}

		const item = pool[ this.index ];
		list.push( item );
		this.index ++;

		item.start = start;
		item.count = count;
		item.z = z;
		item.index = index;

	}

	reset() {

		this.list.length = 0;
		this.index = 0;

	}

}
```
</details>

#### Methods

##### `push(start: any, count: any, z: any, index: any): void`

<details><summary>Code</summary>

```ts
push( start, count, z, index ) {

		const pool = this.pool;
		const list = this.list;
		if ( this.index >= pool.length ) {

			pool.push( {

				start: - 1,
				count: - 1,
				z: - 1,
				index: - 1,

			} );

		}

		const item = pool[ this.index ];
		list.push( item );
		this.index ++;

		item.start = start;
		item.count = count;
		item.z = z;
		item.index = index;

	}
```
</details>

##### `reset(): void`

<details><summary>Code</summary>

```ts
reset() {

		this.list.length = 0;
		this.index = 0;

	}
```
</details>

### `BatchedMesh`

<details><summary>Class Code</summary>

```ts
class BatchedMesh extends Mesh {

	/**
	 * Constructs a new batched mesh.
	 *
	 * @param {number} maxInstanceCount - The maximum number of individual instances planned to be added and rendered.
	 * @param {number} maxVertexCount - The maximum number of vertices to be used by all unique geometries.
	 * @param {number} [maxIndexCount=maxVertexCount*2] - The maximum number of indices to be used by all unique geometries
	 * @param {Material|Array<Material>} [material] - The mesh material.
	 */
	constructor( maxInstanceCount, maxVertexCount, maxIndexCount = maxVertexCount * 2, material ) {

		super( new BufferGeometry(), material );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isBatchedMesh = true;

		/**
		 * When set ot `true`, the individual objects of a batch are frustum culled.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.perObjectFrustumCulled = true;

		/**
		 * When set to `true`, the individual objects of a batch are sorted to improve overdraw-related artifacts.
		 * If the material is marked as "transparent" objects are rendered back to front and if not then they are
		 * rendered front to back.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.sortObjects = true;

		/**
		 * The bounding box of the batched mesh. Can be computed via {@link BatchedMesh#computeBoundingBox}.
		 *
		 * @type {?Box3}
		 * @default null
		 */
		this.boundingBox = null;

		/**
		 * The bounding sphere of the batched mesh. Can be computed via {@link BatchedMesh#computeBoundingSphere}.
		 *
		 * @type {?Sphere}
		 * @default null
		 */
		this.boundingSphere = null;

		/**
		 * Takes a sort a function that is run before render. The function takes a list of instances to
		 * sort and a camera. The objects in the list include a "z" field to perform a depth-ordered
		 * sort with.
		 *
		 * @type {?Function}
		 * @default null
		 */
		this.customSort = null;

		// stores visible, active, and geometry id per instance and reserved buffer ranges for geometries
		this._instanceInfo = [];
		this._geometryInfo = [];

		// instance, geometry ids that have been set as inactive, and are available to be overwritten
		this._availableInstanceIds = [];
		this._availableGeometryIds = [];

		// used to track where the next point is that geometry should be inserted
		this._nextIndexStart = 0;
		this._nextVertexStart = 0;
		this._geometryCount = 0;

		// flags
		this._visibilityChanged = true;
		this._geometryInitialized = false;

		// cached user options
		this._maxInstanceCount = maxInstanceCount;
		this._maxVertexCount = maxVertexCount;
		this._maxIndexCount = maxIndexCount;

		// buffers for multi draw
		this._multiDrawCounts = new Int32Array( maxInstanceCount );
		this._multiDrawStarts = new Int32Array( maxInstanceCount );
		this._multiDrawCount = 0;
		this._multiDrawInstances = null;

		// Local matrix per geometry by using data texture
		this._matricesTexture = null;
		this._indirectTexture = null;
		this._colorsTexture = null;

		this._initMatricesTexture();
		this._initIndirectTexture();

	}

	/**
	 * The maximum number of individual instances that can be stored in the batch.
	 *
	 * @type {number}
	 * @readonly
	 */
	get maxInstanceCount() {

		return this._maxInstanceCount;

	}

	/**
	 * The instance count.
	 *
	 * @type {number}
	 * @readonly
	 */
	get instanceCount() {

		return this._instanceInfo.length - this._availableInstanceIds.length;

	}

	/**
	 * The number of unused vertices.
	 *
	 * @type {number}
	 * @readonly
	 */
	get unusedVertexCount() {

		return this._maxVertexCount - this._nextVertexStart;

	}

	/**
	 * The number of unused indices.
	 *
	 * @type {number}
	 * @readonly
	 */
	get unusedIndexCount() {

		return this._maxIndexCount - this._nextIndexStart;

	}

	_initMatricesTexture() {

		// layout (1 matrix = 4 pixels)
		//      RGBA RGBA RGBA RGBA (=> column1, column2, column3, column4)
		//  with  8x8  pixel texture max   16 matrices * 4 pixels =  (8 * 8)
		//       16x16 pixel texture max   64 matrices * 4 pixels = (16 * 16)
		//       32x32 pixel texture max  256 matrices * 4 pixels = (32 * 32)
		//       64x64 pixel texture max 1024 matrices * 4 pixels = (64 * 64)

		let size = Math.sqrt( this._maxInstanceCount * 4 ); // 4 pixels needed for 1 matrix
		size = Math.ceil( size / 4 ) * 4;
		size = Math.max( size, 4 );

		const matricesArray = new Float32Array( size * size * 4 ); // 4 floats per RGBA pixel
		const matricesTexture = new DataTexture( matricesArray, size, size, RGBAFormat, FloatType );

		this._matricesTexture = matricesTexture;

	}

	_initIndirectTexture() {

		let size = Math.sqrt( this._maxInstanceCount );
		size = Math.ceil( size );

		const indirectArray = new Uint32Array( size * size );
		const indirectTexture = new DataTexture( indirectArray, size, size, RedIntegerFormat, UnsignedIntType );

		this._indirectTexture = indirectTexture;

	}

	_initColorsTexture() {

		let size = Math.sqrt( this._maxInstanceCount );
		size = Math.ceil( size );

		// 4 floats per RGBA pixel initialized to white
		const colorsArray = new Float32Array( size * size * 4 ).fill( 1 );
		const colorsTexture = new DataTexture( colorsArray, size, size, RGBAFormat, FloatType );
		colorsTexture.colorSpace = ColorManagement.workingColorSpace;

		this._colorsTexture = colorsTexture;

	}

	_initializeGeometry( reference ) {

		const geometry = this.geometry;
		const maxVertexCount = this._maxVertexCount;
		const maxIndexCount = this._maxIndexCount;
		if ( this._geometryInitialized === false ) {

			for ( const attributeName in reference.attributes ) {

				const srcAttribute = reference.getAttribute( attributeName );
				const { array, itemSize, normalized } = srcAttribute;

				const dstArray = new array.constructor( maxVertexCount * itemSize );
				const dstAttribute = new BufferAttribute( dstArray, itemSize, normalized );

				geometry.setAttribute( attributeName, dstAttribute );

			}

			if ( reference.getIndex() !== null ) {

				// Reserve last u16 index for primitive restart.
				const indexArray = maxVertexCount > 65535
					? new Uint32Array( maxIndexCount )
					: new Uint16Array( maxIndexCount );

				geometry.setIndex( new BufferAttribute( indexArray, 1 ) );

			}

			this._geometryInitialized = true;

		}

	}

	// Make sure the geometry is compatible with the existing combined geometry attributes
	_validateGeometry( geometry ) {

		// check to ensure the geometries are using consistent attributes and indices
		const batchGeometry = this.geometry;
		if ( Boolean( geometry.getIndex() ) !== Boolean( batchGeometry.getIndex() ) ) {

			throw new Error( 'THREE.BatchedMesh: All geometries must consistently have "index".' );

		}

		for ( const attributeName in batchGeometry.attributes ) {

			if ( ! geometry.hasAttribute( attributeName ) ) {

				throw new Error( `THREE.BatchedMesh: Added geometry missing "${ attributeName }". All geometries must have consistent attributes.` );

			}

			const srcAttribute = geometry.getAttribute( attributeName );
			const dstAttribute = batchGeometry.getAttribute( attributeName );
			if ( srcAttribute.itemSize !== dstAttribute.itemSize || srcAttribute.normalized !== dstAttribute.normalized ) {

				throw new Error( 'THREE.BatchedMesh: All attributes must have a consistent itemSize and normalized value.' );

			}

		}

	}

	/**
	 * Validates the instance defined by the given ID.
	 *
	 * @param {number} instanceId - The instance to validate.
	 */
	validateInstanceId( instanceId ) {

		const instanceInfo = this._instanceInfo;
		if ( instanceId < 0 || instanceId >= instanceInfo.length || instanceInfo[ instanceId ].active === false ) {

			throw new Error( `THREE.BatchedMesh: Invalid instanceId ${instanceId}. Instance is either out of range or has been deleted.` );

		}

	}

	/**
	 * Validates the geometry defined by the given ID.
	 *
	 * @param {number} geometryId - The geometry to validate.
	 */
	validateGeometryId( geometryId ) {

		const geometryInfoList = this._geometryInfo;
		if ( geometryId < 0 || geometryId >= geometryInfoList.length || geometryInfoList[ geometryId ].active === false ) {

			throw new Error( `THREE.BatchedMesh: Invalid geometryId ${geometryId}. Geometry is either out of range or has been deleted.` );

		}

	}

	/**
	 * Takes a sort a function that is run before render. The function takes a list of instances to
	 * sort and a camera. The objects in the list include a "z" field to perform a depth-ordered sort with.
	 *
	 * @param {Function} func - The custom sort function.
	 * @return {BatchedMesh} A reference to this batched mesh.
	 */
	setCustomSort( func ) {

		this.customSort = func;
		return this;

	}

	/**
	 * Computes the bounding box, updating {@link BatchedMesh#boundingBox}.
	 * Bounding boxes aren't computed by default. They need to be explicitly computed,
	 * otherwise they are `null`.
	 */
	computeBoundingBox() {

		if ( this.boundingBox === null ) {

			this.boundingBox = new Box3();

		}

		const boundingBox = this.boundingBox;
		const instanceInfo = this._instanceInfo;

		boundingBox.makeEmpty();
		for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

			if ( instanceInfo[ i ].active === false ) continue;

			const geometryId = instanceInfo[ i ].geometryIndex;
			this.getMatrixAt( i, _matrix );
			this.getBoundingBoxAt( geometryId, _box ).applyMatrix4( _matrix );
			boundingBox.union( _box );

		}

	}

	/**
	 * Computes the bounding sphere, updating {@link BatchedMesh#boundingSphere}.
	 * Bounding spheres aren't computed by default. They need to be explicitly computed,
	 * otherwise they are `null`.
	 */
	computeBoundingSphere() {

		if ( this.boundingSphere === null ) {

			this.boundingSphere = new Sphere();

		}

		const boundingSphere = this.boundingSphere;
		const instanceInfo = this._instanceInfo;

		boundingSphere.makeEmpty();
		for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

			if ( instanceInfo[ i ].active === false ) continue;

			const geometryId = instanceInfo[ i ].geometryIndex;
			this.getMatrixAt( i, _matrix );
			this.getBoundingSphereAt( geometryId, _sphere ).applyMatrix4( _matrix );
			boundingSphere.union( _sphere );

		}

	}

	/**
	 * Adds a new instance to the batch using the geometry of the given ID and returns
	 * a new id referring to the new instance to be used by other functions.
	 *
	 * @param {number} geometryId - The ID of a previously added geometry via {@link BatchedMesh#addGeometry}.
	 * @return {number} The instance ID.
	 */
	addInstance( geometryId ) {

		const atCapacity = this._instanceInfo.length >= this.maxInstanceCount;

		// ensure we're not over geometry
		if ( atCapacity && this._availableInstanceIds.length === 0 ) {

			throw new Error( 'THREE.BatchedMesh: Maximum item count reached.' );

		}

		const instanceInfo = {
			visible: true,
			active: true,
			geometryIndex: geometryId,
		};

		let drawId = null;

		// Prioritize using previously freed instance ids
		if ( this._availableInstanceIds.length > 0 ) {

			this._availableInstanceIds.sort( ascIdSort );

			drawId = this._availableInstanceIds.shift();
			this._instanceInfo[ drawId ] = instanceInfo;

		} else {

			drawId = this._instanceInfo.length;
			this._instanceInfo.push( instanceInfo );

		}

		const matricesTexture = this._matricesTexture;
		_matrix.identity().toArray( matricesTexture.image.data, drawId * 16 );
		matricesTexture.needsUpdate = true;

		const colorsTexture = this._colorsTexture;
		if ( colorsTexture ) {

			_whiteColor.toArray( colorsTexture.image.data, drawId * 4 );
			colorsTexture.needsUpdate = true;

		}

		this._visibilityChanged = true;
		return drawId;

	}

	/**
	 * Adds the given geometry to the batch and returns the associated
	 * geometry id referring to it to be used in other functions.
	 *
	 * @param {BufferGeometry} geometry - The geometry to add.
	 * @param {number} [reservedVertexCount=-1] - Optional parameter specifying the amount of
	 * vertex buffer space to reserve for the added geometry. This is necessary if it is planned
	 * to set a new geometry at this index at a later time that is larger than the original geometry.
	 * Defaults to the length of the given geometry vertex buffer.
	 * @param {number} [reservedIndexCount=-1] - Optional parameter specifying the amount of index
	 * buffer space to reserve for the added geometry. This is necessary if it is planned to set a
	 * new geometry at this index at a later time that is larger than the original geometry. Defaults to
	 * the length of the given geometry index buffer.
	 * @return {number} The geometry ID.
	 */
	addGeometry( geometry, reservedVertexCount = - 1, reservedIndexCount = - 1 ) {

		this._initializeGeometry( geometry );

		this._validateGeometry( geometry );

		const geometryInfo = {
			// geometry information
			vertexStart: - 1,
			vertexCount: - 1,
			reservedVertexCount: - 1,

			indexStart: - 1,
			indexCount: - 1,
			reservedIndexCount: - 1,

			// draw range information
			start: - 1,
			count: - 1,

			// state
			boundingBox: null,
			boundingSphere: null,
			active: true,
		};

		const geometryInfoList = this._geometryInfo;
		geometryInfo.vertexStart = this._nextVertexStart;
		geometryInfo.reservedVertexCount = reservedVertexCount === - 1 ? geometry.getAttribute( 'position' ).count : reservedVertexCount;

		const index = geometry.getIndex();
		const hasIndex = index !== null;
		if ( hasIndex ) {

			geometryInfo.indexStart = this._nextIndexStart;
			geometryInfo.reservedIndexCount = reservedIndexCount === - 1 ? index.count : reservedIndexCount;

		}

		if (
			geometryInfo.indexStart !== - 1 &&
			geometryInfo.indexStart + geometryInfo.reservedIndexCount > this._maxIndexCount ||
			geometryInfo.vertexStart + geometryInfo.reservedVertexCount > this._maxVertexCount
		) {

			throw new Error( 'THREE.BatchedMesh: Reserved space request exceeds the maximum buffer size.' );

		}

		// update id
		let geometryId;
		if ( this._availableGeometryIds.length > 0 ) {

			this._availableGeometryIds.sort( ascIdSort );

			geometryId = this._availableGeometryIds.shift();
			geometryInfoList[ geometryId ] = geometryInfo;


		} else {

			geometryId = this._geometryCount;
			this._geometryCount ++;
			geometryInfoList.push( geometryInfo );

		}

		// update the geometry
		this.setGeometryAt( geometryId, geometry );

		// increment the next geometry position
		this._nextIndexStart = geometryInfo.indexStart + geometryInfo.reservedIndexCount;
		this._nextVertexStart = geometryInfo.vertexStart + geometryInfo.reservedVertexCount;

		return geometryId;

	}

	/**
	 * Replaces the geometry at the given ID with the provided geometry. Throws an error if there
	 * is not enough space reserved for geometry. Calling this will change all instances that are
	 * rendering that geometry.
	 *
	 * @param {number} geometryId - The ID of the geometry that should be replaced with the given geometry.
	 * @param {BufferGeometry} geometry - The new geometry.
	 * @return {number} The geometry ID.
	 */
	setGeometryAt( geometryId, geometry ) {

		if ( geometryId >= this._geometryCount ) {

			throw new Error( 'THREE.BatchedMesh: Maximum geometry count reached.' );

		}

		this._validateGeometry( geometry );

		const batchGeometry = this.geometry;
		const hasIndex = batchGeometry.getIndex() !== null;
		const dstIndex = batchGeometry.getIndex();
		const srcIndex = geometry.getIndex();
		const geometryInfo = this._geometryInfo[ geometryId ];
		if (
			hasIndex &&
			srcIndex.count > geometryInfo.reservedIndexCount ||
			geometry.attributes.position.count > geometryInfo.reservedVertexCount
		) {

			throw new Error( 'THREE.BatchedMesh: Reserved space not large enough for provided geometry.' );

		}

		// copy geometry buffer data over
		const vertexStart = geometryInfo.vertexStart;
		const reservedVertexCount = geometryInfo.reservedVertexCount;
		geometryInfo.vertexCount = geometry.getAttribute( 'position' ).count;

		for ( const attributeName in batchGeometry.attributes ) {

			// copy attribute data
			const srcAttribute = geometry.getAttribute( attributeName );
			const dstAttribute = batchGeometry.getAttribute( attributeName );
			copyAttributeData( srcAttribute, dstAttribute, vertexStart );

			// fill the rest in with zeroes
			const itemSize = srcAttribute.itemSize;
			for ( let i = srcAttribute.count, l = reservedVertexCount; i < l; i ++ ) {

				const index = vertexStart + i;
				for ( let c = 0; c < itemSize; c ++ ) {

					dstAttribute.setComponent( index, c, 0 );

				}

			}

			dstAttribute.needsUpdate = true;
			dstAttribute.addUpdateRange( vertexStart * itemSize, reservedVertexCount * itemSize );

		}

		// copy index
		if ( hasIndex ) {

			const indexStart = geometryInfo.indexStart;
			const reservedIndexCount = geometryInfo.reservedIndexCount;
			geometryInfo.indexCount = geometry.getIndex().count;

			// copy index data over
			for ( let i = 0; i < srcIndex.count; i ++ ) {

				dstIndex.setX( indexStart + i, vertexStart + srcIndex.getX( i ) );

			}

			// fill the rest in with zeroes
			for ( let i = srcIndex.count, l = reservedIndexCount; i < l; i ++ ) {

				dstIndex.setX( indexStart + i, vertexStart );

			}

			dstIndex.needsUpdate = true;
			dstIndex.addUpdateRange( indexStart, geometryInfo.reservedIndexCount );

		}

		// update the draw range
		geometryInfo.start = hasIndex ? geometryInfo.indexStart : geometryInfo.vertexStart;
		geometryInfo.count = hasIndex ? geometryInfo.indexCount : geometryInfo.vertexCount;

		// store the bounding boxes
		geometryInfo.boundingBox = null;
		if ( geometry.boundingBox !== null ) {

			geometryInfo.boundingBox = geometry.boundingBox.clone();

		}

		geometryInfo.boundingSphere = null;
		if ( geometry.boundingSphere !== null ) {

			geometryInfo.boundingSphere = geometry.boundingSphere.clone();

		}

		this._visibilityChanged = true;
		return geometryId;

	}

	/**
	 * Deletes the geometry defined by the given ID from this batch. Any instances referencing
	 * this geometry will also be removed as a side effect.
	 *
	 * @param {number} geometryId - The ID of the geometry to remove from the batch.
	 * @return {BatchedMesh} A reference to this batched mesh.
	 */
	deleteGeometry( geometryId ) {

		const geometryInfoList = this._geometryInfo;
		if ( geometryId >= geometryInfoList.length || geometryInfoList[ geometryId ].active === false ) {

			return this;

		}

		// delete any instances associated with this geometry
		const instanceInfo = this._instanceInfo;
		for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

			if ( instanceInfo[ i ].active && instanceInfo[ i ].geometryIndex === geometryId ) {

				this.deleteInstance( i );

			}

		}

		geometryInfoList[ geometryId ].active = false;
		this._availableGeometryIds.push( geometryId );
		this._visibilityChanged = true;

		return this;

	}

	/**
	 * Deletes an existing instance from the batch using the given ID.
	 *
	 * @param {number} instanceId - The ID of the instance to remove from the batch.
	 * @return {BatchedMesh} A reference to this batched mesh.
	 */
	deleteInstance( instanceId ) {

		this.validateInstanceId( instanceId );

		this._instanceInfo[ instanceId ].active = false;
		this._availableInstanceIds.push( instanceId );
		this._visibilityChanged = true;

		return this;

	}

	/**
	 * Repacks the sub geometries in [name] to remove any unused space remaining from
	 * previously deleted geometry, freeing up space to add new geometry.
	 *
	 * @param {number} instanceId - The ID of the instance to remove from the batch.
	 * @return {BatchedMesh} A reference to this batched mesh.
	 */
	optimize() {

		// track the next indices to copy data to
		let nextVertexStart = 0;
		let nextIndexStart = 0;

		// Iterate over all geometry ranges in order sorted from earliest in the geometry buffer to latest
		// in the geometry buffer. Because draw range objects can be reused there is no guarantee of their order.
		const geometryInfoList = this._geometryInfo;
		const indices = geometryInfoList
			.map( ( e, i ) => i )
			.sort( ( a, b ) => {

				return geometryInfoList[ a ].vertexStart - geometryInfoList[ b ].vertexStart;

			} );

		const geometry = this.geometry;
		for ( let i = 0, l = geometryInfoList.length; i < l; i ++ ) {

			// if a geometry range is inactive then don't copy anything
			const index = indices[ i ];
			const geometryInfo = geometryInfoList[ index ];
			if ( geometryInfo.active === false ) {

				continue;

			}

			// if a geometry contains an index buffer then shift it, as well
			if ( geometry.index !== null ) {

				if ( geometryInfo.indexStart !== nextIndexStart ) {

					const { indexStart, vertexStart, reservedIndexCount } = geometryInfo;
					const index = geometry.index;
					const array = index.array;

					// shift the index pointers based on how the vertex data will shift
					// adjusting the index must happen first so the original vertex start value is available
					const elementDelta = nextVertexStart - vertexStart;
					for ( let j = indexStart; j < indexStart + reservedIndexCount; j ++ ) {

						array[ j ] = array[ j ] + elementDelta;

					}

					index.array.copyWithin( nextIndexStart, indexStart, indexStart + reservedIndexCount );
					index.addUpdateRange( nextIndexStart, reservedIndexCount );

					geometryInfo.indexStart = nextIndexStart;

				}

				nextIndexStart += geometryInfo.reservedIndexCount;

			}

			// if a geometry needs to be moved then copy attribute data to overwrite unused space
			if ( geometryInfo.vertexStart !== nextVertexStart ) {

				const { vertexStart, reservedVertexCount } = geometryInfo;
				const attributes = geometry.attributes;
				for ( const key in attributes ) {

					const attribute = attributes[ key ];
					const { array, itemSize } = attribute;
					array.copyWithin( nextVertexStart * itemSize, vertexStart * itemSize, ( vertexStart + reservedVertexCount ) * itemSize );
					attribute.addUpdateRange( nextVertexStart * itemSize, reservedVertexCount * itemSize );

				}

				geometryInfo.vertexStart = nextVertexStart;

			}

			nextVertexStart += geometryInfo.reservedVertexCount;
			geometryInfo.start = geometry.index ? geometryInfo.indexStart : geometryInfo.vertexStart;

			// step the next geometry points to the shifted position
			this._nextIndexStart = geometry.index ? geometryInfo.indexStart + geometryInfo.reservedIndexCount : 0;
			this._nextVertexStart = geometryInfo.vertexStart + geometryInfo.reservedVertexCount;

		}

		return this;

	}

	/**
	 * Returns the bounding box for the given geometry.
	 *
	 * @param {number} geometryId - The ID of the geometry to return the bounding box for.
	 * @param {Box3} target - The target object that is used to store the method's result.
	 * @return {Box3|null} The geometry's bounding box. Returns `null` if no geometry has been found for the given ID.
	 */
	getBoundingBoxAt( geometryId, target ) {

		if ( geometryId >= this._geometryCount ) {

			return null;

		}

		// compute bounding box
		const geometry = this.geometry;
		const geometryInfo = this._geometryInfo[ geometryId ];
		if ( geometryInfo.boundingBox === null ) {

			const box = new Box3();
			const index = geometry.index;
			const position = geometry.attributes.position;
			for ( let i = geometryInfo.start, l = geometryInfo.start + geometryInfo.count; i < l; i ++ ) {

				let iv = i;
				if ( index ) {

					iv = index.getX( iv );

				}

				box.expandByPoint( _vector.fromBufferAttribute( position, iv ) );

			}

			geometryInfo.boundingBox = box;

		}

		target.copy( geometryInfo.boundingBox );
		return target;

	}

	/**
	 * Returns the bounding sphere for the given geometry.
	 *
	 * @param {number} geometryId - The ID of the geometry to return the bounding sphere for.
	 * @param {Sphere} target - The target object that is used to store the method's result.
	 * @return {Sphere|null} The geometry's bounding sphere. Returns `null` if no geometry has been found for the given ID.
	 */
	getBoundingSphereAt( geometryId, target ) {

		if ( geometryId >= this._geometryCount ) {

			return null;

		}

		// compute bounding sphere
		const geometry = this.geometry;
		const geometryInfo = this._geometryInfo[ geometryId ];
		if ( geometryInfo.boundingSphere === null ) {

			const sphere = new Sphere();
			this.getBoundingBoxAt( geometryId, _box );
			_box.getCenter( sphere.center );

			const index = geometry.index;
			const position = geometry.attributes.position;

			let maxRadiusSq = 0;
			for ( let i = geometryInfo.start, l = geometryInfo.start + geometryInfo.count; i < l; i ++ ) {

				let iv = i;
				if ( index ) {

					iv = index.getX( iv );

				}

				_vector.fromBufferAttribute( position, iv );
				maxRadiusSq = Math.max( maxRadiusSq, sphere.center.distanceToSquared( _vector ) );

			}

			sphere.radius = Math.sqrt( maxRadiusSq );
			geometryInfo.boundingSphere = sphere;

		}

		target.copy( geometryInfo.boundingSphere );
		return target;

	}

	/**
	 * Sets the given local transformation matrix to the defined instance.
	 * Negatively scaled matrices are not supported.
	 *
	 * @param {number} instanceId - The ID of an instance to set the matrix of.
	 * @param {Matrix4} matrix - A 4x4 matrix representing the local transformation of a single instance.
	 * @return {BatchedMesh} A reference to this batched mesh.
	 */
	setMatrixAt( instanceId, matrix ) {

		this.validateInstanceId( instanceId );

		const matricesTexture = this._matricesTexture;
		const matricesArray = this._matricesTexture.image.data;
		matrix.toArray( matricesArray, instanceId * 16 );
		matricesTexture.needsUpdate = true;

		return this;

	}

	/**
	 * Returns the local transformation matrix of the defined instance.
	 *
	 * @param {number} instanceId - The ID of an instance to get the matrix of.
	 * @param {Matrix4} matrix - The target object that is used to store the method's result.
	 * @return {Matrix4} The instance's local transformation matrix.
	 */
	getMatrixAt( instanceId, matrix ) {

		this.validateInstanceId( instanceId );
		return matrix.fromArray( this._matricesTexture.image.data, instanceId * 16 );

	}

	/**
	 * Sets the given color to the defined instance.
	 *
	 * @param {number} instanceId - The ID of an instance to set the color of.
	 * @param {Color} color - The color to set the instance to.
	 * @return {BatchedMesh} A reference to this batched mesh.
	 */
	setColorAt( instanceId, color ) {

		this.validateInstanceId( instanceId );

		if ( this._colorsTexture === null ) {

			this._initColorsTexture();

		}

		color.toArray( this._colorsTexture.image.data, instanceId * 4 );
		this._colorsTexture.needsUpdate = true;

		return this;

	}

	/**
	 * Returns the color of the defined instance.
	 *
	 * @param {number} instanceId - The ID of an instance to get the color of.
	 * @param {Color} color - The target object that is used to store the method's result.
	 * @return {Color} The instance's color.
	 */
	getColorAt( instanceId, color ) {

		this.validateInstanceId( instanceId );
		return color.fromArray( this._colorsTexture.image.data, instanceId * 4 );

	}

	/**
	 * Sets the visibility of the instance.
	 *
	 * @param {number} instanceId - The id of the instance to set the visibility of.
	 * @param {boolean} visible - Whether the instance is visible or not.
	 * @return {BatchedMesh} A reference to this batched mesh.
	 */
	setVisibleAt( instanceId, visible ) {

		this.validateInstanceId( instanceId );

		if ( this._instanceInfo[ instanceId ].visible === visible ) {

			return this;

		}

		this._instanceInfo[ instanceId ].visible = visible;
		this._visibilityChanged = true;

		return this;

	}

	/**
	 * Returns the visibility state of the defined instance.
	 *
	 * @param {number} instanceId - The ID of an instance to get the visibility state of.
	 * @return {boolean} Whether the instance is visible or not.
	 */
	getVisibleAt( instanceId ) {

		this.validateInstanceId( instanceId );

		return this._instanceInfo[ instanceId ].visible;

	}

	/**
	 * Sets the geometry ID of the instance at the given index.
	 *
	 * @param {number} instanceId - The ID of the instance to set the geometry ID of.
	 * @param {number} geometryId - The geometry ID to be use by the instance.
	 * @return {BatchedMesh} A reference to this batched mesh.
	 */
	setGeometryIdAt( instanceId, geometryId ) {

		this.validateInstanceId( instanceId );
		this.validateGeometryId( geometryId );

		this._instanceInfo[ instanceId ].geometryIndex = geometryId;

		return this;

	}

	/**
	 * Returns the geometry ID of the defined instance.
	 *
	 * @param {number} instanceId - The ID of an instance to get the geometry ID of.
	 * @return {number} The instance's geometry ID.
	 */
	getGeometryIdAt( instanceId ) {

		this.validateInstanceId( instanceId );

		return this._instanceInfo[ instanceId ].geometryIndex;

	}

	/**
	 * Get the range representing the subset of triangles related to the attached geometry,
	 * indicating the starting offset and count, or `null` if invalid.
	 *
	 * @param {number} geometryId - The id of the geometry to get the range of.
	 * @param {Object} [target] - The target object that is used to store the method's result.
	 * @return {{
	 * 	vertexStart:number,vertexCount:number,reservedVertexCount:number,
	 * 	indexStart:number,indexCount:number,reservedIndexCount:number,
	 * 	start:number,count:number
	 * }} The result object with range data.
	 */
	getGeometryRangeAt( geometryId, target = {} ) {

		this.validateGeometryId( geometryId );

		const geometryInfo = this._geometryInfo[ geometryId ];
		target.vertexStart = geometryInfo.vertexStart;
		target.vertexCount = geometryInfo.vertexCount;
		target.reservedVertexCount = geometryInfo.reservedVertexCount;

		target.indexStart = geometryInfo.indexStart;
		target.indexCount = geometryInfo.indexCount;
		target.reservedIndexCount = geometryInfo.reservedIndexCount;

		target.start = geometryInfo.start;
		target.count = geometryInfo.count;

		return target;

	}

	/**
	 * Resizes the necessary buffers to support the provided number of instances.
	 * If the provided arguments shrink the number of instances but there are not enough
	 * unused Ids at the end of the list then an error is thrown.
	 *
	 * @param {number} maxInstanceCount - The max number of individual instances that can be added and rendered by the batch.
	*/
	setInstanceCount( maxInstanceCount ) {

		// shrink the available instances as much as possible
		const availableInstanceIds = this._availableInstanceIds;
		const instanceInfo = this._instanceInfo;
		availableInstanceIds.sort( ascIdSort );
		while ( availableInstanceIds[ availableInstanceIds.length - 1 ] === instanceInfo.length - 1 ) {

			instanceInfo.pop();
			availableInstanceIds.pop();

		}

		// throw an error if it can't be shrunk to the desired size
		if ( maxInstanceCount < instanceInfo.length ) {

			throw new Error( `BatchedMesh: Instance ids outside the range ${ maxInstanceCount } are being used. Cannot shrink instance count.` );

		}

		// copy the multi draw counts
		const multiDrawCounts = new Int32Array( maxInstanceCount );
		const multiDrawStarts = new Int32Array( maxInstanceCount );
		copyArrayContents( this._multiDrawCounts, multiDrawCounts );
		copyArrayContents( this._multiDrawStarts, multiDrawStarts );

		this._multiDrawCounts = multiDrawCounts;
		this._multiDrawStarts = multiDrawStarts;
		this._maxInstanceCount = maxInstanceCount;

		// update texture data for instance sampling
		const indirectTexture = this._indirectTexture;
		const matricesTexture = this._matricesTexture;
		const colorsTexture = this._colorsTexture;

		indirectTexture.dispose();
		this._initIndirectTexture();
		copyArrayContents( indirectTexture.image.data, this._indirectTexture.image.data );

		matricesTexture.dispose();
		this._initMatricesTexture();
		copyArrayContents( matricesTexture.image.data, this._matricesTexture.image.data );

		if ( colorsTexture ) {

			colorsTexture.dispose();
			this._initColorsTexture();
			copyArrayContents( colorsTexture.image.data, this._colorsTexture.image.data );

		}

	}

	/**
	 * Resizes the available space in the batch's vertex and index buffer attributes to the provided sizes.
	 * If the provided arguments shrink the geometry buffers but there is not enough unused space at the
	 * end of the geometry attributes then an error is thrown.
	 *
	 * @param {number} maxVertexCount - The maximum number of vertices to be used by all unique geometries to resize to.
	 * @param {number} maxIndexCount - The maximum number of indices to be used by all unique geometries to resize to.
	*/
	setGeometrySize( maxVertexCount, maxIndexCount ) {

		// Check if we can shrink to the requested vertex attribute size
		const validRanges = [ ...this._geometryInfo ].filter( info => info.active );
		const requiredVertexLength = Math.max( ...validRanges.map( range => range.vertexStart + range.reservedVertexCount ) );
		if ( requiredVertexLength > maxVertexCount ) {

			throw new Error( `BatchedMesh: Geometry vertex values are being used outside the range ${ maxIndexCount }. Cannot shrink further.` );

		}

		// Check if we can shrink to the requested index attribute size
		if ( this.geometry.index ) {

			const requiredIndexLength = Math.max( ...validRanges.map( range => range.indexStart + range.reservedIndexCount ) );
			if ( requiredIndexLength > maxIndexCount ) {

				throw new Error( `BatchedMesh: Geometry index values are being used outside the range ${ maxIndexCount }. Cannot shrink further.` );

			}

		}

		//

		// dispose of the previous geometry
		const oldGeometry = this.geometry;
		oldGeometry.dispose();

		// recreate the geometry needed based on the previous variant
		this._maxVertexCount = maxVertexCount;
		this._maxIndexCount = maxIndexCount;

		if ( this._geometryInitialized ) {

			this._geometryInitialized = false;
			this.geometry = new BufferGeometry();
			this._initializeGeometry( oldGeometry );

		}

		// copy data from the previous geometry
		const geometry = this.geometry;
		if ( oldGeometry.index ) {

			copyArrayContents( oldGeometry.index.array, geometry.index.array );

		}

		for ( const key in oldGeometry.attributes ) {

			copyArrayContents( oldGeometry.attributes[ key ].array, geometry.attributes[ key ].array );

		}

	}

	raycast( raycaster, intersects ) {

		const instanceInfo = this._instanceInfo;
		const geometryInfoList = this._geometryInfo;
		const matrixWorld = this.matrixWorld;
		const batchGeometry = this.geometry;

		// iterate over each geometry
		_mesh.material = this.material;
		_mesh.geometry.index = batchGeometry.index;
		_mesh.geometry.attributes = batchGeometry.attributes;
		if ( _mesh.geometry.boundingBox === null ) {

			_mesh.geometry.boundingBox = new Box3();

		}

		if ( _mesh.geometry.boundingSphere === null ) {

			_mesh.geometry.boundingSphere = new Sphere();

		}

		for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

			if ( ! instanceInfo[ i ].visible || ! instanceInfo[ i ].active ) {

				continue;

			}

			const geometryId = instanceInfo[ i ].geometryIndex;
			const geometryInfo = geometryInfoList[ geometryId ];
			_mesh.geometry.setDrawRange( geometryInfo.start, geometryInfo.count );

			// get the intersects
			this.getMatrixAt( i, _mesh.matrixWorld ).premultiply( matrixWorld );
			this.getBoundingBoxAt( geometryId, _mesh.geometry.boundingBox );
			this.getBoundingSphereAt( geometryId, _mesh.geometry.boundingSphere );
			_mesh.raycast( raycaster, _batchIntersects );

			// add batch id to the intersects
			for ( let j = 0, l = _batchIntersects.length; j < l; j ++ ) {

				const intersect = _batchIntersects[ j ];
				intersect.object = this;
				intersect.batchId = i;
				intersects.push( intersect );

			}

			_batchIntersects.length = 0;

		}

		_mesh.material = null;
		_mesh.geometry.index = null;
		_mesh.geometry.attributes = {};
		_mesh.geometry.setDrawRange( 0, Infinity );

	}

	copy( source ) {

		super.copy( source );

		this.geometry = source.geometry.clone();
		this.perObjectFrustumCulled = source.perObjectFrustumCulled;
		this.sortObjects = source.sortObjects;
		this.boundingBox = source.boundingBox !== null ? source.boundingBox.clone() : null;
		this.boundingSphere = source.boundingSphere !== null ? source.boundingSphere.clone() : null;

		this._geometryInfo = source._geometryInfo.map( info => ( {
			...info,

			boundingBox: info.boundingBox !== null ? info.boundingBox.clone() : null,
			boundingSphere: info.boundingSphere !== null ? info.boundingSphere.clone() : null,
		} ) );
		this._instanceInfo = source._instanceInfo.map( info => ( { ...info } ) );

		this._availableInstanceIds = source._availableInstanceIds.slice();
		this._availableGeometryIds = source._availableGeometryIds.slice();

		this._nextIndexStart = source._nextIndexStart;
		this._nextVertexStart = source._nextVertexStart;
		this._geometryCount = source._geometryCount;

		this._maxInstanceCount = source._maxInstanceCount;
		this._maxVertexCount = source._maxVertexCount;
		this._maxIndexCount = source._maxIndexCount;

		this._geometryInitialized = source._geometryInitialized;
		this._multiDrawCounts = source._multiDrawCounts.slice();
		this._multiDrawStarts = source._multiDrawStarts.slice();

		this._indirectTexture = source._indirectTexture.clone();
		this._indirectTexture.image.data = this._indirectTexture.image.data.slice();

		this._matricesTexture = source._matricesTexture.clone();
		this._matricesTexture.image.data = this._matricesTexture.image.data.slice();

		if ( this._colorsTexture !== null ) {

			this._colorsTexture = source._colorsTexture.clone();
			this._colorsTexture.image.data = this._colorsTexture.image.data.slice();

		}

		return this;

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		// Assuming the geometry is not shared with other meshes
		this.geometry.dispose();

		this._matricesTexture.dispose();
		this._matricesTexture = null;

		this._indirectTexture.dispose();
		this._indirectTexture = null;

		if ( this._colorsTexture !== null ) {

			this._colorsTexture.dispose();
			this._colorsTexture = null;

		}

	}

	onBeforeRender( renderer, scene, camera, geometry, material/*, _group*/ ) {

		// if visibility has not changed and frustum culling and object sorting is not required
		// then skip iterating over all items
		if ( ! this._visibilityChanged && ! this.perObjectFrustumCulled && ! this.sortObjects ) {

			return;

		}

		// the indexed version of the multi draw function requires specifying the start
		// offset in bytes.
		const index = geometry.getIndex();
		const bytesPerElement = index === null ? 1 : index.array.BYTES_PER_ELEMENT;

		const instanceInfo = this._instanceInfo;
		const multiDrawStarts = this._multiDrawStarts;
		const multiDrawCounts = this._multiDrawCounts;
		const geometryInfoList = this._geometryInfo;
		const perObjectFrustumCulled = this.perObjectFrustumCulled;
		const indirectTexture = this._indirectTexture;
		const indirectArray = indirectTexture.image.data;

		const frustum = camera.isArrayCamera ? _frustumArray : _frustum;
		// prepare the frustum in the local frame
		if ( perObjectFrustumCulled && ! camera.isArrayCamera ) {

			_matrix
				.multiplyMatrices( camera.projectionMatrix, camera.matrixWorldInverse )
				.multiply( this.matrixWorld );

			_frustum.setFromProjectionMatrix(
				_matrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

		}

		let multiDrawCount = 0;
		if ( this.sortObjects ) {

			// get the camera position in the local frame
			_matrix.copy( this.matrixWorld ).invert();
			_vector.setFromMatrixPosition( camera.matrixWorld ).applyMatrix4( _matrix );
			_forward.set( 0, 0, - 1 ).transformDirection( camera.matrixWorld ).transformDirection( _matrix );

			for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

				if ( instanceInfo[ i ].visible && instanceInfo[ i ].active ) {

					const geometryId = instanceInfo[ i ].geometryIndex;

					// get the bounds in world space
					this.getMatrixAt( i, _matrix );
					this.getBoundingSphereAt( geometryId, _sphere ).applyMatrix4( _matrix );

					// determine whether the batched geometry is within the frustum
					let culled = false;
					if ( perObjectFrustumCulled ) {

						culled = ! frustum.intersectsSphere( _sphere, camera );

					}

					if ( ! culled ) {

						// get the distance from camera used for sorting
						const geometryInfo = geometryInfoList[ geometryId ];
						const z = _temp.subVectors( _sphere.center, _vector ).dot( _forward );
						_renderList.push( geometryInfo.start, geometryInfo.count, z, i );

					}

				}

			}

			// Sort the draw ranges and prep for rendering
			const list = _renderList.list;
			const customSort = this.customSort;
			if ( customSort === null ) {

				list.sort( material.transparent ? sortTransparent : sortOpaque );

			} else {

				customSort.call( this, list, camera );

			}

			for ( let i = 0, l = list.length; i < l; i ++ ) {

				const item = list[ i ];
				multiDrawStarts[ multiDrawCount ] = item.start * bytesPerElement;
				multiDrawCounts[ multiDrawCount ] = item.count;
				indirectArray[ multiDrawCount ] = item.index;
				multiDrawCount ++;

			}

			_renderList.reset();

		} else {

			for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

				if ( instanceInfo[ i ].visible && instanceInfo[ i ].active ) {

					const geometryId = instanceInfo[ i ].geometryIndex;

					// determine whether the batched geometry is within the frustum
					let culled = false;
					if ( perObjectFrustumCulled ) {

						// get the bounds in world space
						this.getMatrixAt( i, _matrix );
						this.getBoundingSphereAt( geometryId, _sphere ).applyMatrix4( _matrix );
						culled = ! frustum.intersectsSphere( _sphere, camera );

					}

					if ( ! culled ) {

						const geometryInfo = geometryInfoList[ geometryId ];
						multiDrawStarts[ multiDrawCount ] = geometryInfo.start * bytesPerElement;
						multiDrawCounts[ multiDrawCount ] = geometryInfo.count;
						indirectArray[ multiDrawCount ] = i;
						multiDrawCount ++;

					}

				}

			}

		}

		indirectTexture.needsUpdate = true;
		this._multiDrawCount = multiDrawCount;
		this._visibilityChanged = false;

	}

	onBeforeShadow( renderer, object, camera, shadowCamera, geometry, depthMaterial/* , group */ ) {

		this.onBeforeRender( renderer, null, shadowCamera, geometry, depthMaterial );

	}

}
```
</details>

#### Methods

##### `_initMatricesTexture(): void`

<details><summary>Code</summary>

```ts
_initMatricesTexture() {

		// layout (1 matrix = 4 pixels)
		//      RGBA RGBA RGBA RGBA (=> column1, column2, column3, column4)
		//  with  8x8  pixel texture max   16 matrices * 4 pixels =  (8 * 8)
		//       16x16 pixel texture max   64 matrices * 4 pixels = (16 * 16)
		//       32x32 pixel texture max  256 matrices * 4 pixels = (32 * 32)
		//       64x64 pixel texture max 1024 matrices * 4 pixels = (64 * 64)

		let size = Math.sqrt( this._maxInstanceCount * 4 ); // 4 pixels needed for 1 matrix
		size = Math.ceil( size / 4 ) * 4;
		size = Math.max( size, 4 );

		const matricesArray = new Float32Array( size * size * 4 ); // 4 floats per RGBA pixel
		const matricesTexture = new DataTexture( matricesArray, size, size, RGBAFormat, FloatType );

		this._matricesTexture = matricesTexture;

	}
```
</details>

##### `_initIndirectTexture(): void`

<details><summary>Code</summary>

```ts
_initIndirectTexture() {

		let size = Math.sqrt( this._maxInstanceCount );
		size = Math.ceil( size );

		const indirectArray = new Uint32Array( size * size );
		const indirectTexture = new DataTexture( indirectArray, size, size, RedIntegerFormat, UnsignedIntType );

		this._indirectTexture = indirectTexture;

	}
```
</details>

##### `_initColorsTexture(): void`

<details><summary>Code</summary>

```ts
_initColorsTexture() {

		let size = Math.sqrt( this._maxInstanceCount );
		size = Math.ceil( size );

		// 4 floats per RGBA pixel initialized to white
		const colorsArray = new Float32Array( size * size * 4 ).fill( 1 );
		const colorsTexture = new DataTexture( colorsArray, size, size, RGBAFormat, FloatType );
		colorsTexture.colorSpace = ColorManagement.workingColorSpace;

		this._colorsTexture = colorsTexture;

	}
```
</details>

##### `_initializeGeometry(reference: any): void`

<details><summary>Code</summary>

```ts
_initializeGeometry( reference ) {

		const geometry = this.geometry;
		const maxVertexCount = this._maxVertexCount;
		const maxIndexCount = this._maxIndexCount;
		if ( this._geometryInitialized === false ) {

			for ( const attributeName in reference.attributes ) {

				const srcAttribute = reference.getAttribute( attributeName );
				const { array, itemSize, normalized } = srcAttribute;

				const dstArray = new array.constructor( maxVertexCount * itemSize );
				const dstAttribute = new BufferAttribute( dstArray, itemSize, normalized );

				geometry.setAttribute( attributeName, dstAttribute );

			}

			if ( reference.getIndex() !== null ) {

				// Reserve last u16 index for primitive restart.
				const indexArray = maxVertexCount > 65535
					? new Uint32Array( maxIndexCount )
					: new Uint16Array( maxIndexCount );

				geometry.setIndex( new BufferAttribute( indexArray, 1 ) );

			}

			this._geometryInitialized = true;

		}

	}
```
</details>

##### `_validateGeometry(geometry: any): void`

<details><summary>Code</summary>

```ts
_validateGeometry( geometry ) {

		// check to ensure the geometries are using consistent attributes and indices
		const batchGeometry = this.geometry;
		if ( Boolean( geometry.getIndex() ) !== Boolean( batchGeometry.getIndex() ) ) {

			throw new Error( 'THREE.BatchedMesh: All geometries must consistently have "index".' );

		}

		for ( const attributeName in batchGeometry.attributes ) {

			if ( ! geometry.hasAttribute( attributeName ) ) {

				throw new Error( `THREE.BatchedMesh: Added geometry missing "${ attributeName }". All geometries must have consistent attributes.` );

			}

			const srcAttribute = geometry.getAttribute( attributeName );
			const dstAttribute = batchGeometry.getAttribute( attributeName );
			if ( srcAttribute.itemSize !== dstAttribute.itemSize || srcAttribute.normalized !== dstAttribute.normalized ) {

				throw new Error( 'THREE.BatchedMesh: All attributes must have a consistent itemSize and normalized value.' );

			}

		}

	}
```
</details>

##### `validateInstanceId(instanceId: number): void`

<details><summary>Code</summary>

```ts
validateInstanceId( instanceId ) {

		const instanceInfo = this._instanceInfo;
		if ( instanceId < 0 || instanceId >= instanceInfo.length || instanceInfo[ instanceId ].active === false ) {

			throw new Error( `THREE.BatchedMesh: Invalid instanceId ${instanceId}. Instance is either out of range or has been deleted.` );

		}

	}
```
</details>

##### `validateGeometryId(geometryId: number): void`

<details><summary>Code</summary>

```ts
validateGeometryId( geometryId ) {

		const geometryInfoList = this._geometryInfo;
		if ( geometryId < 0 || geometryId >= geometryInfoList.length || geometryInfoList[ geometryId ].active === false ) {

			throw new Error( `THREE.BatchedMesh: Invalid geometryId ${geometryId}. Geometry is either out of range or has been deleted.` );

		}

	}
```
</details>

##### `setCustomSort(func: Function): BatchedMesh`

<details><summary>Code</summary>

```ts
setCustomSort( func ) {

		this.customSort = func;
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

		const boundingBox = this.boundingBox;
		const instanceInfo = this._instanceInfo;

		boundingBox.makeEmpty();
		for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

			if ( instanceInfo[ i ].active === false ) continue;

			const geometryId = instanceInfo[ i ].geometryIndex;
			this.getMatrixAt( i, _matrix );
			this.getBoundingBoxAt( geometryId, _box ).applyMatrix4( _matrix );
			boundingBox.union( _box );

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

		const boundingSphere = this.boundingSphere;
		const instanceInfo = this._instanceInfo;

		boundingSphere.makeEmpty();
		for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

			if ( instanceInfo[ i ].active === false ) continue;

			const geometryId = instanceInfo[ i ].geometryIndex;
			this.getMatrixAt( i, _matrix );
			this.getBoundingSphereAt( geometryId, _sphere ).applyMatrix4( _matrix );
			boundingSphere.union( _sphere );

		}

	}
```
</details>

##### `addInstance(geometryId: number): number`

<details><summary>Code</summary>

```ts
addInstance( geometryId ) {

		const atCapacity = this._instanceInfo.length >= this.maxInstanceCount;

		// ensure we're not over geometry
		if ( atCapacity && this._availableInstanceIds.length === 0 ) {

			throw new Error( 'THREE.BatchedMesh: Maximum item count reached.' );

		}

		const instanceInfo = {
			visible: true,
			active: true,
			geometryIndex: geometryId,
		};

		let drawId = null;

		// Prioritize using previously freed instance ids
		if ( this._availableInstanceIds.length > 0 ) {

			this._availableInstanceIds.sort( ascIdSort );

			drawId = this._availableInstanceIds.shift();
			this._instanceInfo[ drawId ] = instanceInfo;

		} else {

			drawId = this._instanceInfo.length;
			this._instanceInfo.push( instanceInfo );

		}

		const matricesTexture = this._matricesTexture;
		_matrix.identity().toArray( matricesTexture.image.data, drawId * 16 );
		matricesTexture.needsUpdate = true;

		const colorsTexture = this._colorsTexture;
		if ( colorsTexture ) {

			_whiteColor.toArray( colorsTexture.image.data, drawId * 4 );
			colorsTexture.needsUpdate = true;

		}

		this._visibilityChanged = true;
		return drawId;

	}
```
</details>

##### `addGeometry(geometry: BufferGeometry, reservedVertexCount: number, reservedIndexCount: number): number`

<details><summary>Code</summary>

```ts
addGeometry( geometry, reservedVertexCount = - 1, reservedIndexCount = - 1 ) {

		this._initializeGeometry( geometry );

		this._validateGeometry( geometry );

		const geometryInfo = {
			// geometry information
			vertexStart: - 1,
			vertexCount: - 1,
			reservedVertexCount: - 1,

			indexStart: - 1,
			indexCount: - 1,
			reservedIndexCount: - 1,

			// draw range information
			start: - 1,
			count: - 1,

			// state
			boundingBox: null,
			boundingSphere: null,
			active: true,
		};

		const geometryInfoList = this._geometryInfo;
		geometryInfo.vertexStart = this._nextVertexStart;
		geometryInfo.reservedVertexCount = reservedVertexCount === - 1 ? geometry.getAttribute( 'position' ).count : reservedVertexCount;

		const index = geometry.getIndex();
		const hasIndex = index !== null;
		if ( hasIndex ) {

			geometryInfo.indexStart = this._nextIndexStart;
			geometryInfo.reservedIndexCount = reservedIndexCount === - 1 ? index.count : reservedIndexCount;

		}

		if (
			geometryInfo.indexStart !== - 1 &&
			geometryInfo.indexStart + geometryInfo.reservedIndexCount > this._maxIndexCount ||
			geometryInfo.vertexStart + geometryInfo.reservedVertexCount > this._maxVertexCount
		) {

			throw new Error( 'THREE.BatchedMesh: Reserved space request exceeds the maximum buffer size.' );

		}

		// update id
		let geometryId;
		if ( this._availableGeometryIds.length > 0 ) {

			this._availableGeometryIds.sort( ascIdSort );

			geometryId = this._availableGeometryIds.shift();
			geometryInfoList[ geometryId ] = geometryInfo;


		} else {

			geometryId = this._geometryCount;
			this._geometryCount ++;
			geometryInfoList.push( geometryInfo );

		}

		// update the geometry
		this.setGeometryAt( geometryId, geometry );

		// increment the next geometry position
		this._nextIndexStart = geometryInfo.indexStart + geometryInfo.reservedIndexCount;
		this._nextVertexStart = geometryInfo.vertexStart + geometryInfo.reservedVertexCount;

		return geometryId;

	}
```
</details>

##### `setGeometryAt(geometryId: number, geometry: BufferGeometry): number`

<details><summary>Code</summary>

```ts
setGeometryAt( geometryId, geometry ) {

		if ( geometryId >= this._geometryCount ) {

			throw new Error( 'THREE.BatchedMesh: Maximum geometry count reached.' );

		}

		this._validateGeometry( geometry );

		const batchGeometry = this.geometry;
		const hasIndex = batchGeometry.getIndex() !== null;
		const dstIndex = batchGeometry.getIndex();
		const srcIndex = geometry.getIndex();
		const geometryInfo = this._geometryInfo[ geometryId ];
		if (
			hasIndex &&
			srcIndex.count > geometryInfo.reservedIndexCount ||
			geometry.attributes.position.count > geometryInfo.reservedVertexCount
		) {

			throw new Error( 'THREE.BatchedMesh: Reserved space not large enough for provided geometry.' );

		}

		// copy geometry buffer data over
		const vertexStart = geometryInfo.vertexStart;
		const reservedVertexCount = geometryInfo.reservedVertexCount;
		geometryInfo.vertexCount = geometry.getAttribute( 'position' ).count;

		for ( const attributeName in batchGeometry.attributes ) {

			// copy attribute data
			const srcAttribute = geometry.getAttribute( attributeName );
			const dstAttribute = batchGeometry.getAttribute( attributeName );
			copyAttributeData( srcAttribute, dstAttribute, vertexStart );

			// fill the rest in with zeroes
			const itemSize = srcAttribute.itemSize;
			for ( let i = srcAttribute.count, l = reservedVertexCount; i < l; i ++ ) {

				const index = vertexStart + i;
				for ( let c = 0; c < itemSize; c ++ ) {

					dstAttribute.setComponent( index, c, 0 );

				}

			}

			dstAttribute.needsUpdate = true;
			dstAttribute.addUpdateRange( vertexStart * itemSize, reservedVertexCount * itemSize );

		}

		// copy index
		if ( hasIndex ) {

			const indexStart = geometryInfo.indexStart;
			const reservedIndexCount = geometryInfo.reservedIndexCount;
			geometryInfo.indexCount = geometry.getIndex().count;

			// copy index data over
			for ( let i = 0; i < srcIndex.count; i ++ ) {

				dstIndex.setX( indexStart + i, vertexStart + srcIndex.getX( i ) );

			}

			// fill the rest in with zeroes
			for ( let i = srcIndex.count, l = reservedIndexCount; i < l; i ++ ) {

				dstIndex.setX( indexStart + i, vertexStart );

			}

			dstIndex.needsUpdate = true;
			dstIndex.addUpdateRange( indexStart, geometryInfo.reservedIndexCount );

		}

		// update the draw range
		geometryInfo.start = hasIndex ? geometryInfo.indexStart : geometryInfo.vertexStart;
		geometryInfo.count = hasIndex ? geometryInfo.indexCount : geometryInfo.vertexCount;

		// store the bounding boxes
		geometryInfo.boundingBox = null;
		if ( geometry.boundingBox !== null ) {

			geometryInfo.boundingBox = geometry.boundingBox.clone();

		}

		geometryInfo.boundingSphere = null;
		if ( geometry.boundingSphere !== null ) {

			geometryInfo.boundingSphere = geometry.boundingSphere.clone();

		}

		this._visibilityChanged = true;
		return geometryId;

	}
```
</details>

##### `deleteGeometry(geometryId: number): BatchedMesh`

<details><summary>Code</summary>

```ts
deleteGeometry( geometryId ) {

		const geometryInfoList = this._geometryInfo;
		if ( geometryId >= geometryInfoList.length || geometryInfoList[ geometryId ].active === false ) {

			return this;

		}

		// delete any instances associated with this geometry
		const instanceInfo = this._instanceInfo;
		for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

			if ( instanceInfo[ i ].active && instanceInfo[ i ].geometryIndex === geometryId ) {

				this.deleteInstance( i );

			}

		}

		geometryInfoList[ geometryId ].active = false;
		this._availableGeometryIds.push( geometryId );
		this._visibilityChanged = true;

		return this;

	}
```
</details>

##### `deleteInstance(instanceId: number): BatchedMesh`

<details><summary>Code</summary>

```ts
deleteInstance( instanceId ) {

		this.validateInstanceId( instanceId );

		this._instanceInfo[ instanceId ].active = false;
		this._availableInstanceIds.push( instanceId );
		this._visibilityChanged = true;

		return this;

	}
```
</details>

##### `optimize(): BatchedMesh`

<details><summary>Code</summary>

```ts
optimize() {

		// track the next indices to copy data to
		let nextVertexStart = 0;
		let nextIndexStart = 0;

		// Iterate over all geometry ranges in order sorted from earliest in the geometry buffer to latest
		// in the geometry buffer. Because draw range objects can be reused there is no guarantee of their order.
		const geometryInfoList = this._geometryInfo;
		const indices = geometryInfoList
			.map( ( e, i ) => i )
			.sort( ( a, b ) => {

				return geometryInfoList[ a ].vertexStart - geometryInfoList[ b ].vertexStart;

			} );

		const geometry = this.geometry;
		for ( let i = 0, l = geometryInfoList.length; i < l; i ++ ) {

			// if a geometry range is inactive then don't copy anything
			const index = indices[ i ];
			const geometryInfo = geometryInfoList[ index ];
			if ( geometryInfo.active === false ) {

				continue;

			}

			// if a geometry contains an index buffer then shift it, as well
			if ( geometry.index !== null ) {

				if ( geometryInfo.indexStart !== nextIndexStart ) {

					const { indexStart, vertexStart, reservedIndexCount } = geometryInfo;
					const index = geometry.index;
					const array = index.array;

					// shift the index pointers based on how the vertex data will shift
					// adjusting the index must happen first so the original vertex start value is available
					const elementDelta = nextVertexStart - vertexStart;
					for ( let j = indexStart; j < indexStart + reservedIndexCount; j ++ ) {

						array[ j ] = array[ j ] + elementDelta;

					}

					index.array.copyWithin( nextIndexStart, indexStart, indexStart + reservedIndexCount );
					index.addUpdateRange( nextIndexStart, reservedIndexCount );

					geometryInfo.indexStart = nextIndexStart;

				}

				nextIndexStart += geometryInfo.reservedIndexCount;

			}

			// if a geometry needs to be moved then copy attribute data to overwrite unused space
			if ( geometryInfo.vertexStart !== nextVertexStart ) {

				const { vertexStart, reservedVertexCount } = geometryInfo;
				const attributes = geometry.attributes;
				for ( const key in attributes ) {

					const attribute = attributes[ key ];
					const { array, itemSize } = attribute;
					array.copyWithin( nextVertexStart * itemSize, vertexStart * itemSize, ( vertexStart + reservedVertexCount ) * itemSize );
					attribute.addUpdateRange( nextVertexStart * itemSize, reservedVertexCount * itemSize );

				}

				geometryInfo.vertexStart = nextVertexStart;

			}

			nextVertexStart += geometryInfo.reservedVertexCount;
			geometryInfo.start = geometry.index ? geometryInfo.indexStart : geometryInfo.vertexStart;

			// step the next geometry points to the shifted position
			this._nextIndexStart = geometry.index ? geometryInfo.indexStart + geometryInfo.reservedIndexCount : 0;
			this._nextVertexStart = geometryInfo.vertexStart + geometryInfo.reservedVertexCount;

		}

		return this;

	}
```
</details>

##### `getBoundingBoxAt(geometryId: number, target: Box3): Box3`

<details><summary>Code</summary>

```ts
getBoundingBoxAt( geometryId, target ) {

		if ( geometryId >= this._geometryCount ) {

			return null;

		}

		// compute bounding box
		const geometry = this.geometry;
		const geometryInfo = this._geometryInfo[ geometryId ];
		if ( geometryInfo.boundingBox === null ) {

			const box = new Box3();
			const index = geometry.index;
			const position = geometry.attributes.position;
			for ( let i = geometryInfo.start, l = geometryInfo.start + geometryInfo.count; i < l; i ++ ) {

				let iv = i;
				if ( index ) {

					iv = index.getX( iv );

				}

				box.expandByPoint( _vector.fromBufferAttribute( position, iv ) );

			}

			geometryInfo.boundingBox = box;

		}

		target.copy( geometryInfo.boundingBox );
		return target;

	}
```
</details>

##### `getBoundingSphereAt(geometryId: number, target: Sphere): Sphere`

<details><summary>Code</summary>

```ts
getBoundingSphereAt( geometryId, target ) {

		if ( geometryId >= this._geometryCount ) {

			return null;

		}

		// compute bounding sphere
		const geometry = this.geometry;
		const geometryInfo = this._geometryInfo[ geometryId ];
		if ( geometryInfo.boundingSphere === null ) {

			const sphere = new Sphere();
			this.getBoundingBoxAt( geometryId, _box );
			_box.getCenter( sphere.center );

			const index = geometry.index;
			const position = geometry.attributes.position;

			let maxRadiusSq = 0;
			for ( let i = geometryInfo.start, l = geometryInfo.start + geometryInfo.count; i < l; i ++ ) {

				let iv = i;
				if ( index ) {

					iv = index.getX( iv );

				}

				_vector.fromBufferAttribute( position, iv );
				maxRadiusSq = Math.max( maxRadiusSq, sphere.center.distanceToSquared( _vector ) );

			}

			sphere.radius = Math.sqrt( maxRadiusSq );
			geometryInfo.boundingSphere = sphere;

		}

		target.copy( geometryInfo.boundingSphere );
		return target;

	}
```
</details>

##### `setMatrixAt(instanceId: number, matrix: Matrix4): BatchedMesh`

<details><summary>Code</summary>

```ts
setMatrixAt( instanceId, matrix ) {

		this.validateInstanceId( instanceId );

		const matricesTexture = this._matricesTexture;
		const matricesArray = this._matricesTexture.image.data;
		matrix.toArray( matricesArray, instanceId * 16 );
		matricesTexture.needsUpdate = true;

		return this;

	}
```
</details>

##### `getMatrixAt(instanceId: number, matrix: Matrix4): Matrix4`

<details><summary>Code</summary>

```ts
getMatrixAt( instanceId, matrix ) {

		this.validateInstanceId( instanceId );
		return matrix.fromArray( this._matricesTexture.image.data, instanceId * 16 );

	}
```
</details>

##### `setColorAt(instanceId: number, color: Color): BatchedMesh`

<details><summary>Code</summary>

```ts
setColorAt( instanceId, color ) {

		this.validateInstanceId( instanceId );

		if ( this._colorsTexture === null ) {

			this._initColorsTexture();

		}

		color.toArray( this._colorsTexture.image.data, instanceId * 4 );
		this._colorsTexture.needsUpdate = true;

		return this;

	}
```
</details>

##### `getColorAt(instanceId: number, color: Color): Color`

<details><summary>Code</summary>

```ts
getColorAt( instanceId, color ) {

		this.validateInstanceId( instanceId );
		return color.fromArray( this._colorsTexture.image.data, instanceId * 4 );

	}
```
</details>

##### `setVisibleAt(instanceId: number, visible: boolean): BatchedMesh`

<details><summary>Code</summary>

```ts
setVisibleAt( instanceId, visible ) {

		this.validateInstanceId( instanceId );

		if ( this._instanceInfo[ instanceId ].visible === visible ) {

			return this;

		}

		this._instanceInfo[ instanceId ].visible = visible;
		this._visibilityChanged = true;

		return this;

	}
```
</details>

##### `getVisibleAt(instanceId: number): boolean`

<details><summary>Code</summary>

```ts
getVisibleAt( instanceId ) {

		this.validateInstanceId( instanceId );

		return this._instanceInfo[ instanceId ].visible;

	}
```
</details>

##### `setGeometryIdAt(instanceId: number, geometryId: number): BatchedMesh`

<details><summary>Code</summary>

```ts
setGeometryIdAt( instanceId, geometryId ) {

		this.validateInstanceId( instanceId );
		this.validateGeometryId( geometryId );

		this._instanceInfo[ instanceId ].geometryIndex = geometryId;

		return this;

	}
```
</details>

##### `getGeometryIdAt(instanceId: number): number`

<details><summary>Code</summary>

```ts
getGeometryIdAt( instanceId ) {

		this.validateInstanceId( instanceId );

		return this._instanceInfo[ instanceId ].geometryIndex;

	}
```
</details>

##### `getGeometryRangeAt(geometryId: number, target: any): { vertexStart: number; vertexCount: number; reservedVertexCount: number; indexStart: number; indexCount: number; reservedIndexCount: number; start: number; count: number; }`

<details><summary>Code</summary>

```ts
getGeometryRangeAt( geometryId, target = {} ) {

		this.validateGeometryId( geometryId );

		const geometryInfo = this._geometryInfo[ geometryId ];
		target.vertexStart = geometryInfo.vertexStart;
		target.vertexCount = geometryInfo.vertexCount;
		target.reservedVertexCount = geometryInfo.reservedVertexCount;

		target.indexStart = geometryInfo.indexStart;
		target.indexCount = geometryInfo.indexCount;
		target.reservedIndexCount = geometryInfo.reservedIndexCount;

		target.start = geometryInfo.start;
		target.count = geometryInfo.count;

		return target;

	}
```
</details>

##### `setInstanceCount(maxInstanceCount: number): void`

<details><summary>Code</summary>

```ts
setInstanceCount( maxInstanceCount ) {

		// shrink the available instances as much as possible
		const availableInstanceIds = this._availableInstanceIds;
		const instanceInfo = this._instanceInfo;
		availableInstanceIds.sort( ascIdSort );
		while ( availableInstanceIds[ availableInstanceIds.length - 1 ] === instanceInfo.length - 1 ) {

			instanceInfo.pop();
			availableInstanceIds.pop();

		}

		// throw an error if it can't be shrunk to the desired size
		if ( maxInstanceCount < instanceInfo.length ) {

			throw new Error( `BatchedMesh: Instance ids outside the range ${ maxInstanceCount } are being used. Cannot shrink instance count.` );

		}

		// copy the multi draw counts
		const multiDrawCounts = new Int32Array( maxInstanceCount );
		const multiDrawStarts = new Int32Array( maxInstanceCount );
		copyArrayContents( this._multiDrawCounts, multiDrawCounts );
		copyArrayContents( this._multiDrawStarts, multiDrawStarts );

		this._multiDrawCounts = multiDrawCounts;
		this._multiDrawStarts = multiDrawStarts;
		this._maxInstanceCount = maxInstanceCount;

		// update texture data for instance sampling
		const indirectTexture = this._indirectTexture;
		const matricesTexture = this._matricesTexture;
		const colorsTexture = this._colorsTexture;

		indirectTexture.dispose();
		this._initIndirectTexture();
		copyArrayContents( indirectTexture.image.data, this._indirectTexture.image.data );

		matricesTexture.dispose();
		this._initMatricesTexture();
		copyArrayContents( matricesTexture.image.data, this._matricesTexture.image.data );

		if ( colorsTexture ) {

			colorsTexture.dispose();
			this._initColorsTexture();
			copyArrayContents( colorsTexture.image.data, this._colorsTexture.image.data );

		}

	}
```
</details>

##### `setGeometrySize(maxVertexCount: number, maxIndexCount: number): void`

<details><summary>Code</summary>

```ts
setGeometrySize( maxVertexCount, maxIndexCount ) {

		// Check if we can shrink to the requested vertex attribute size
		const validRanges = [ ...this._geometryInfo ].filter( info => info.active );
		const requiredVertexLength = Math.max( ...validRanges.map( range => range.vertexStart + range.reservedVertexCount ) );
		if ( requiredVertexLength > maxVertexCount ) {

			throw new Error( `BatchedMesh: Geometry vertex values are being used outside the range ${ maxIndexCount }. Cannot shrink further.` );

		}

		// Check if we can shrink to the requested index attribute size
		if ( this.geometry.index ) {

			const requiredIndexLength = Math.max( ...validRanges.map( range => range.indexStart + range.reservedIndexCount ) );
			if ( requiredIndexLength > maxIndexCount ) {

				throw new Error( `BatchedMesh: Geometry index values are being used outside the range ${ maxIndexCount }. Cannot shrink further.` );

			}

		}

		//

		// dispose of the previous geometry
		const oldGeometry = this.geometry;
		oldGeometry.dispose();

		// recreate the geometry needed based on the previous variant
		this._maxVertexCount = maxVertexCount;
		this._maxIndexCount = maxIndexCount;

		if ( this._geometryInitialized ) {

			this._geometryInitialized = false;
			this.geometry = new BufferGeometry();
			this._initializeGeometry( oldGeometry );

		}

		// copy data from the previous geometry
		const geometry = this.geometry;
		if ( oldGeometry.index ) {

			copyArrayContents( oldGeometry.index.array, geometry.index.array );

		}

		for ( const key in oldGeometry.attributes ) {

			copyArrayContents( oldGeometry.attributes[ key ].array, geometry.attributes[ key ].array );

		}

	}
```
</details>

##### `raycast(raycaster: any, intersects: any): void`

<details><summary>Code</summary>

```ts
raycast( raycaster, intersects ) {

		const instanceInfo = this._instanceInfo;
		const geometryInfoList = this._geometryInfo;
		const matrixWorld = this.matrixWorld;
		const batchGeometry = this.geometry;

		// iterate over each geometry
		_mesh.material = this.material;
		_mesh.geometry.index = batchGeometry.index;
		_mesh.geometry.attributes = batchGeometry.attributes;
		if ( _mesh.geometry.boundingBox === null ) {

			_mesh.geometry.boundingBox = new Box3();

		}

		if ( _mesh.geometry.boundingSphere === null ) {

			_mesh.geometry.boundingSphere = new Sphere();

		}

		for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

			if ( ! instanceInfo[ i ].visible || ! instanceInfo[ i ].active ) {

				continue;

			}

			const geometryId = instanceInfo[ i ].geometryIndex;
			const geometryInfo = geometryInfoList[ geometryId ];
			_mesh.geometry.setDrawRange( geometryInfo.start, geometryInfo.count );

			// get the intersects
			this.getMatrixAt( i, _mesh.matrixWorld ).premultiply( matrixWorld );
			this.getBoundingBoxAt( geometryId, _mesh.geometry.boundingBox );
			this.getBoundingSphereAt( geometryId, _mesh.geometry.boundingSphere );
			_mesh.raycast( raycaster, _batchIntersects );

			// add batch id to the intersects
			for ( let j = 0, l = _batchIntersects.length; j < l; j ++ ) {

				const intersect = _batchIntersects[ j ];
				intersect.object = this;
				intersect.batchId = i;
				intersects.push( intersect );

			}

			_batchIntersects.length = 0;

		}

		_mesh.material = null;
		_mesh.geometry.index = null;
		_mesh.geometry.attributes = {};
		_mesh.geometry.setDrawRange( 0, Infinity );

	}
```
</details>

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source );

		this.geometry = source.geometry.clone();
		this.perObjectFrustumCulled = source.perObjectFrustumCulled;
		this.sortObjects = source.sortObjects;
		this.boundingBox = source.boundingBox !== null ? source.boundingBox.clone() : null;
		this.boundingSphere = source.boundingSphere !== null ? source.boundingSphere.clone() : null;

		this._geometryInfo = source._geometryInfo.map( info => ( {
			...info,

			boundingBox: info.boundingBox !== null ? info.boundingBox.clone() : null,
			boundingSphere: info.boundingSphere !== null ? info.boundingSphere.clone() : null,
		} ) );
		this._instanceInfo = source._instanceInfo.map( info => ( { ...info } ) );

		this._availableInstanceIds = source._availableInstanceIds.slice();
		this._availableGeometryIds = source._availableGeometryIds.slice();

		this._nextIndexStart = source._nextIndexStart;
		this._nextVertexStart = source._nextVertexStart;
		this._geometryCount = source._geometryCount;

		this._maxInstanceCount = source._maxInstanceCount;
		this._maxVertexCount = source._maxVertexCount;
		this._maxIndexCount = source._maxIndexCount;

		this._geometryInitialized = source._geometryInitialized;
		this._multiDrawCounts = source._multiDrawCounts.slice();
		this._multiDrawStarts = source._multiDrawStarts.slice();

		this._indirectTexture = source._indirectTexture.clone();
		this._indirectTexture.image.data = this._indirectTexture.image.data.slice();

		this._matricesTexture = source._matricesTexture.clone();
		this._matricesTexture.image.data = this._matricesTexture.image.data.slice();

		if ( this._colorsTexture !== null ) {

			this._colorsTexture = source._colorsTexture.clone();
			this._colorsTexture.image.data = this._colorsTexture.image.data.slice();

		}

		return this;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		// Assuming the geometry is not shared with other meshes
		this.geometry.dispose();

		this._matricesTexture.dispose();
		this._matricesTexture = null;

		this._indirectTexture.dispose();
		this._indirectTexture = null;

		if ( this._colorsTexture !== null ) {

			this._colorsTexture.dispose();
			this._colorsTexture = null;

		}

	}
```
</details>

##### `onBeforeRender(renderer: any, scene: any, camera: any, geometry: any, material: any): void`

<details><summary>Code</summary>

```ts
onBeforeRender( renderer, scene, camera, geometry, material/*, _group*/ ) {

		// if visibility has not changed and frustum culling and object sorting is not required
		// then skip iterating over all items
		if ( ! this._visibilityChanged && ! this.perObjectFrustumCulled && ! this.sortObjects ) {

			return;

		}

		// the indexed version of the multi draw function requires specifying the start
		// offset in bytes.
		const index = geometry.getIndex();
		const bytesPerElement = index === null ? 1 : index.array.BYTES_PER_ELEMENT;

		const instanceInfo = this._instanceInfo;
		const multiDrawStarts = this._multiDrawStarts;
		const multiDrawCounts = this._multiDrawCounts;
		const geometryInfoList = this._geometryInfo;
		const perObjectFrustumCulled = this.perObjectFrustumCulled;
		const indirectTexture = this._indirectTexture;
		const indirectArray = indirectTexture.image.data;

		const frustum = camera.isArrayCamera ? _frustumArray : _frustum;
		// prepare the frustum in the local frame
		if ( perObjectFrustumCulled && ! camera.isArrayCamera ) {

			_matrix
				.multiplyMatrices( camera.projectionMatrix, camera.matrixWorldInverse )
				.multiply( this.matrixWorld );

			_frustum.setFromProjectionMatrix(
				_matrix,
				camera.coordinateSystem,
				camera.reversedDepth
			);

		}

		let multiDrawCount = 0;
		if ( this.sortObjects ) {

			// get the camera position in the local frame
			_matrix.copy( this.matrixWorld ).invert();
			_vector.setFromMatrixPosition( camera.matrixWorld ).applyMatrix4( _matrix );
			_forward.set( 0, 0, - 1 ).transformDirection( camera.matrixWorld ).transformDirection( _matrix );

			for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

				if ( instanceInfo[ i ].visible && instanceInfo[ i ].active ) {

					const geometryId = instanceInfo[ i ].geometryIndex;

					// get the bounds in world space
					this.getMatrixAt( i, _matrix );
					this.getBoundingSphereAt( geometryId, _sphere ).applyMatrix4( _matrix );

					// determine whether the batched geometry is within the frustum
					let culled = false;
					if ( perObjectFrustumCulled ) {

						culled = ! frustum.intersectsSphere( _sphere, camera );

					}

					if ( ! culled ) {

						// get the distance from camera used for sorting
						const geometryInfo = geometryInfoList[ geometryId ];
						const z = _temp.subVectors( _sphere.center, _vector ).dot( _forward );
						_renderList.push( geometryInfo.start, geometryInfo.count, z, i );

					}

				}

			}

			// Sort the draw ranges and prep for rendering
			const list = _renderList.list;
			const customSort = this.customSort;
			if ( customSort === null ) {

				list.sort( material.transparent ? sortTransparent : sortOpaque );

			} else {

				customSort.call( this, list, camera );

			}

			for ( let i = 0, l = list.length; i < l; i ++ ) {

				const item = list[ i ];
				multiDrawStarts[ multiDrawCount ] = item.start * bytesPerElement;
				multiDrawCounts[ multiDrawCount ] = item.count;
				indirectArray[ multiDrawCount ] = item.index;
				multiDrawCount ++;

			}

			_renderList.reset();

		} else {

			for ( let i = 0, l = instanceInfo.length; i < l; i ++ ) {

				if ( instanceInfo[ i ].visible && instanceInfo[ i ].active ) {

					const geometryId = instanceInfo[ i ].geometryIndex;

					// determine whether the batched geometry is within the frustum
					let culled = false;
					if ( perObjectFrustumCulled ) {

						// get the bounds in world space
						this.getMatrixAt( i, _matrix );
						this.getBoundingSphereAt( geometryId, _sphere ).applyMatrix4( _matrix );
						culled = ! frustum.intersectsSphere( _sphere, camera );

					}

					if ( ! culled ) {

						const geometryInfo = geometryInfoList[ geometryId ];
						multiDrawStarts[ multiDrawCount ] = geometryInfo.start * bytesPerElement;
						multiDrawCounts[ multiDrawCount ] = geometryInfo.count;
						indirectArray[ multiDrawCount ] = i;
						multiDrawCount ++;

					}

				}

			}

		}

		indirectTexture.needsUpdate = true;
		this._multiDrawCount = multiDrawCount;
		this._visibilityChanged = false;

	}
```
</details>

##### `onBeforeShadow(renderer: any, object: any, camera: any, shadowCamera: any, geometry: any, depthMaterial: any): void`

<details><summary>Code</summary>

```ts
onBeforeShadow( renderer, object, camera, shadowCamera, geometry, depthMaterial/* , group */ ) {

		this.onBeforeRender( renderer, null, shadowCamera, geometry, depthMaterial );

	}
```
</details>


---