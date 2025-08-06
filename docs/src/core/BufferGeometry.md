[⬅️ Back to Table of Contents](../../index.md)

# 📄 `BufferGeometry.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 34 |
| 🧱 Classes | 1 |
| 📦 Imports | 14 |
| 📊 Variables & Constants | 101 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/core/BufferGeometry.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `../math/Vector3.js` |
| `Vector2` | `../math/Vector2.js` |
| `Box3` | `../math/Box3.js` |
| `EventDispatcher` | `./EventDispatcher.js` |
| `BufferAttribute` | `./BufferAttribute.js` |
| `Float32BufferAttribute` | `./BufferAttribute.js` |
| `Uint16BufferAttribute` | `./BufferAttribute.js` |
| `Uint32BufferAttribute` | `./BufferAttribute.js` |
| `Sphere` | `../math/Sphere.js` |
| `Object3D` | `./Object3D.js` |
| `Matrix4` | `../math/Matrix4.js` |
| `Matrix3` | `../math/Matrix3.js` |
| `generateUUID` | `../math/MathUtils.js` |
| `arrayNeedsUint32` | `../utils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_id` | `number` | let/var | `0` | ✗ |
| `_m1` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `_obj` | `Object3D` | let/var | `new Object3D()` | ✗ |
| `_offset` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_box` | `Box3` | let/var | `new Box3()` | ✗ |
| `_boxMorphTargets` | `Box3` | let/var | `new Box3()` | ✗ |
| `_vector` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `position` | `any` | let/var | `this.attributes.position` | ✗ |
| `normal` | `any` | let/var | `this.attributes.normal` | ✗ |
| `tangent` | `any` | let/var | `this.attributes.tangent` | ✗ |
| `position` | `any[]` | let/var | `[]` | ✗ |
| `point` | `Vector2 \| Vector3` | let/var | `points[ i ]` | ✗ |
| `point` | `Vector2 \| Vector3` | let/var | `points[ i ]` | ✗ |
| `position` | `any` | let/var | `this.attributes.position` | ✗ |
| `morphAttributesPosition` | `any` | let/var | `this.morphAttributes.position` | ✗ |
| `morphAttribute` | `any` | let/var | `morphAttributesPosition[ i ]` | ✗ |
| `position` | `any` | let/var | `this.attributes.position` | ✗ |
| `morphAttributesPosition` | `any` | let/var | `this.morphAttributes.position` | ✗ |
| `center` | `Vector3` | let/var | `this.boundingSphere.center` | ✗ |
| `morphAttribute` | `any` | let/var | `morphAttributesPosition[ i ]` | ✗ |
| `maxRadiusSq` | `number` | let/var | `0` | ✗ |
| `morphAttribute` | `any` | let/var | `morphAttributesPosition[ i ]` | ✗ |
| `morphTargetsRelative` | `boolean` | let/var | `this.morphTargetsRelative` | ✗ |
| `index` | `BufferAttribute` | let/var | `this.index` | ✗ |
| `attributes` | `{ [x: string]: any; }` | let/var | `this.attributes` | ✗ |
| `positionAttribute` | `any` | let/var | `attributes.position` | ✗ |
| `normalAttribute` | `any` | let/var | `attributes.normal` | ✗ |
| `uvAttribute` | `any` | let/var | `attributes.uv` | ✗ |
| `tan1` | `any[]` | let/var | `[]` | ✗ |
| `tan2` | `any[]` | let/var | `[]` | ✗ |
| `vA` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `vB` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `vC` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `uvA` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `uvB` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `uvC` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `sdir` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `tdir` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `r` | `number` | let/var | `1.0 / ( uvB.x * uvC.y - uvC.x * uvB.y )` | ✗ |
| `groups` | `any[]` | let/var | `this.groups` | ✗ |
| `group` | `any` | let/var | `groups[ i ]` | ✗ |
| `start` | `any` | let/var | `group.start` | ✗ |
| `count` | `any` | let/var | `group.count` | ✗ |
| `tmp` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `tmp2` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `n` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `n2` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `t` | `any` | let/var | `tan1[ v ]` | ✗ |
| `w` | `1 \| -1` | let/var | `( test < 0.0 ) ? - 1.0 : 1.0` | ✗ |
| `group` | `any` | let/var | `groups[ i ]` | ✗ |
| `start` | `any` | let/var | `group.start` | ✗ |
| `count` | `any` | let/var | `group.count` | ✗ |
| `index` | `BufferAttribute` | let/var | `this.index` | ✗ |
| `pA` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `pB` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `pC` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `nA` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `nB` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `nC` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `cb` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `ab` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `normals` | `any` | let/var | `this.attributes.normal` | ✗ |
| `array` | `any` | let/var | `attribute.array` | ✗ |
| `itemSize` | `any` | let/var | `attribute.itemSize` | ✗ |
| `normalized` | `any` | let/var | `attribute.normalized` | ✗ |
| `array2` | `any` | let/var | `new array.constructor( indices.length * itemSize )` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `index2` | `number` | let/var | `0` | ✗ |
| `geometry2` | `BufferGeometry` | let/var | `new BufferGeometry()` | ✗ |
| `indices` | `TypedArray` | let/var | `this.index.array` | ✗ |
| `attributes` | `{ [x: string]: any; }` | let/var | `this.attributes` | ✗ |
| `attribute` | `any` | let/var | `attributes[ name ]` | ✗ |
| `morphAttributes` | `any` | let/var | `this.morphAttributes` | ✗ |
| `morphArray` | `any[]` | let/var | `[]` | ✗ |
| `morphAttribute` | `any` | let/var | `morphAttributes[ name ]` | ✗ |
| `attribute` | `any` | let/var | `morphAttribute[ i ]` | ✗ |
| `groups` | `any[]` | let/var | `this.groups` | ✗ |
| `group` | `any` | let/var | `groups[ i ]` | ✗ |
| `data` | `{ metadata: { version: number; type: ...` | let/var | `{ metadata: { version: 4.7, type: 'BufferGeometry', generator: 'BufferGeometr...` | ✗ |
| `parameters` | `any` | let/var | `this.parameters` | ✗ |
| `index` | `BufferAttribute` | let/var | `this.index` | ✗ |
| `attributes` | `{ [x: string]: any; }` | let/var | `this.attributes` | ✗ |
| `attribute` | `any` | let/var | `attributes[ key ]` | ✗ |
| `morphAttributes` | `{}` | let/var | `{}` | ✗ |
| `hasMorphAttributes` | `boolean` | let/var | `false` | ✗ |
| `attributeArray` | `any` | let/var | `this.morphAttributes[ key ]` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `attribute` | `any` | let/var | `attributeArray[ i ]` | ✗ |
| `groups` | `any[]` | let/var | `this.groups` | ✗ |
| `boundingSphere` | `Sphere` | let/var | `this.boundingSphere` | ✗ |
| `data` | `{}` | let/var | `{}` | ✗ |
| `index` | `BufferAttribute` | let/var | `source.index` | ✗ |
| `attributes` | `{ [x: string]: any; }` | let/var | `source.attributes` | ✗ |
| `attribute` | `any` | let/var | `attributes[ name ]` | ✗ |
| `morphAttributes` | `any` | let/var | `source.morphAttributes` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `morphAttribute` | `any` | let/var | `morphAttributes[ name ]` | ✗ |
| `groups` | `any[]` | let/var | `source.groups` | ✗ |
| `group` | `any` | let/var | `groups[ i ]` | ✗ |
| `boundingBox` | `Box3` | let/var | `source.boundingBox` | ✗ |
| `boundingSphere` | `Sphere` | let/var | `source.boundingSphere` | ✗ |


---

## Functions

### `BufferGeometry.getIndex(): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Returns the index of this geometry.
	 *
	 * @return {?BufferAttribute} The index. Returns `null` if no index is defined.
	 */
```

**Returns:** `BufferAttribute`

<details><summary>Code</summary>

```typescript
getIndex() {

		return this.index;

	}
```
</details>

### `BufferGeometry.setIndex(index: number[] | BufferAttribute): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Sets the given index to this geometry.
	 *
	 * @param {Array<number>|BufferAttribute} index - The index to set.
	 * @return {BufferGeometry} A reference to this instance.
	 */
```

**Parameters:**

- **`index`** `number[] | BufferAttribute`

**Returns:** `BufferGeometry`

**Calls:**

- `Array.isArray`
- `arrayNeedsUint32 (from ../utils.js)`

<details><summary>Code</summary>

```typescript
setIndex( index ) {

		if ( Array.isArray( index ) ) {

			this.index = new ( arrayNeedsUint32( index ) ? Uint32BufferAttribute : Uint16BufferAttribute )( index, 1 );

		} else {

			this.index = index;

		}

		return this;

	}
```
</details>

### `BufferGeometry.setIndirect(indirect: BufferAttribute): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Sets the given indirect attribute to this geometry.
	 *
	 * @param {BufferAttribute} indirect - The attribute holding indirect draw calls.
	 * @return {BufferGeometry} A reference to this instance.
	 */
```

**Parameters:**

- **`indirect`** `BufferAttribute`

**Returns:** `BufferGeometry`

<details><summary>Code</summary>

```typescript
setIndirect( indirect ) {

		this.indirect = indirect;

		return this;

	}
```
</details>

### `BufferGeometry.getIndirect(): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Returns the indirect attribute of this geometry.
	 *
	 * @return {?BufferAttribute} The indirect attribute. Returns `null` if no indirect attribute is defined.
	 */
```

**Returns:** `BufferAttribute`

<details><summary>Code</summary>

```typescript
getIndirect() {

		return this.indirect;

	}
```
</details>

### `BufferGeometry.getAttribute(name: string): any`

**JSDoc:**
```typescript
/**
	 * Returns the buffer attribute for the given name.
	 *
	 * @param {string} name - The attribute name.
	 * @return {BufferAttribute|InterleavedBufferAttribute|undefined} The buffer attribute.
	 * Returns `undefined` if not attribute has been found.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getAttribute( name ) {

		return this.attributes[ name ];

	}
```
</details>

### `BufferGeometry.setAttribute(name: string, attribute: any): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Sets the given attribute for the given name.
	 *
	 * @param {string} name - The attribute name.
	 * @param {BufferAttribute|InterleavedBufferAttribute} attribute - The attribute to set.
	 * @return {BufferGeometry} A reference to this instance.
	 */
```

**Parameters:**

- **`name`** `string`
- **`attribute`** `any`

**Returns:** `BufferGeometry`

<details><summary>Code</summary>

```typescript
setAttribute( name, attribute ) {

		this.attributes[ name ] = attribute;

		return this;

	}
```
</details>

### `BufferGeometry.deleteAttribute(name: string): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Deletes the attribute for the given name.
	 *
	 * @param {string} name - The attribute name to delete.
	 * @return {BufferGeometry} A reference to this instance.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `BufferGeometry`

<details><summary>Code</summary>

```typescript
deleteAttribute( name ) {

		delete this.attributes[ name ];

		return this;

	}
```
</details>

### `BufferGeometry.hasAttribute(name: string): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this geometry has an attribute for the given name.
	 *
	 * @param {string} name - The attribute name.
	 * @return {boolean} Whether this geometry has an attribute for the given name or not.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
hasAttribute( name ) {

		return this.attributes[ name ] !== undefined;

	}
```
</details>

### `BufferGeometry.addGroup(start: number, count: number, materialIndex: number): void`

**JSDoc:**
```typescript
/**
	 * Adds a group to this geometry.
	 *
	 * @param {number} start - The first element in this draw call. That is the first
	 * vertex for non-indexed geometry, otherwise the first triangle index.
	 * @param {number} count - Specifies how many vertices (or indices) are part of this group.
	 * @param {number} [materialIndex=0] - The material array index to use.
	 */
```

**Parameters:**

- **`start`** `number`
- **`count`** `number`
- **`materialIndex`** `number`

**Returns:** `void`

**Calls:**

- `this.groups.push`

<details><summary>Code</summary>

```typescript
addGroup( start, count, materialIndex = 0 ) {

		this.groups.push( {

			start: start,
			count: count,
			materialIndex: materialIndex

		} );

	}
```
</details>

### `BufferGeometry.clearGroups(): void`

**JSDoc:**
```typescript
/**
	 * Clears all groups.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
clearGroups() {

		this.groups = [];

	}
```
</details>

### `BufferGeometry.setDrawRange(start: number, count: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the draw range for this geometry.
	 *
	 * @param {number} start - The first vertex for non-indexed geometry, otherwise the first triangle index.
	 * @param {number} count - For non-indexed BufferGeometry, `count` is the number of vertices to render.
	 * For indexed BufferGeometry, `count` is the number of indices to render.
	 */
```

**Parameters:**

- **`start`** `number`
- **`count`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setDrawRange( start, count ) {

		this.drawRange.start = start;
		this.drawRange.count = count;

	}
```
</details>

### `BufferGeometry.applyMatrix4(matrix: Matrix4): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Applies the given 4x4 transformation matrix to the geometry.
	 *
	 * @param {Matrix4} matrix - The matrix to apply.
	 * @return {BufferGeometry} A reference to this instance.
	 */
```

**Parameters:**

- **`matrix`** `Matrix4`

**Returns:** `BufferGeometry`

**Calls:**

- `position.applyMatrix4`
- `new Matrix3().getNormalMatrix`
- `normal.applyNormalMatrix`
- `tangent.transformDirection`
- `this.computeBoundingBox`
- `this.computeBoundingSphere`

<details><summary>Code</summary>

```typescript
applyMatrix4( matrix ) {

		const position = this.attributes.position;

		if ( position !== undefined ) {

			position.applyMatrix4( matrix );

			position.needsUpdate = true;

		}

		const normal = this.attributes.normal;

		if ( normal !== undefined ) {

			const normalMatrix = new Matrix3().getNormalMatrix( matrix );

			normal.applyNormalMatrix( normalMatrix );

			normal.needsUpdate = true;

		}

		const tangent = this.attributes.tangent;

		if ( tangent !== undefined ) {

			tangent.transformDirection( matrix );

			tangent.needsUpdate = true;

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

### `BufferGeometry.applyQuaternion(q: Quaternion): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Applies the rotation represented by the Quaternion to the geometry.
	 *
	 * @param {Quaternion} q - The Quaternion to apply.
	 * @return {BufferGeometry} A reference to this instance.
	 */
```

**Parameters:**

- **`q`** `Quaternion`

**Returns:** `BufferGeometry`

**Calls:**

- `_m1.makeRotationFromQuaternion`
- `this.applyMatrix4`

<details><summary>Code</summary>

```typescript
applyQuaternion( q ) {

		_m1.makeRotationFromQuaternion( q );

		this.applyMatrix4( _m1 );

		return this;

	}
```
</details>

### `BufferGeometry.rotateX(angle: number): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Rotates the geometry about the X axis. This is typically done as a one time
	 * operation, and not during a loop. Use {@link Object3D#rotation} for typical
	 * real-time mesh rotation.
	 *
	 * @param {number} angle - The angle in radians.
	 * @return {BufferGeometry} A reference to this instance.
	 */
```

**Parameters:**

- **`angle`** `number`

**Returns:** `BufferGeometry`

**Calls:**

- `_m1.makeRotationX`
- `this.applyMatrix4`

**Internal Comments:**
```
// rotate geometry around world x-axis (x4)
```

<details><summary>Code</summary>

```typescript
rotateX( angle ) {

		// rotate geometry around world x-axis

		_m1.makeRotationX( angle );

		this.applyMatrix4( _m1 );

		return this;

	}
```
</details>

### `BufferGeometry.rotateY(angle: number): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Rotates the geometry about the Y axis. This is typically done as a one time
	 * operation, and not during a loop. Use {@link Object3D#rotation} for typical
	 * real-time mesh rotation.
	 *
	 * @param {number} angle - The angle in radians.
	 * @return {BufferGeometry} A reference to this instance.
	 */
```

**Parameters:**

- **`angle`** `number`

**Returns:** `BufferGeometry`

**Calls:**

- `_m1.makeRotationY`
- `this.applyMatrix4`

**Internal Comments:**
```
// rotate geometry around world y-axis (x4)
```

<details><summary>Code</summary>

```typescript
rotateY( angle ) {

		// rotate geometry around world y-axis

		_m1.makeRotationY( angle );

		this.applyMatrix4( _m1 );

		return this;

	}
```
</details>

### `BufferGeometry.rotateZ(angle: number): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Rotates the geometry about the Z axis. This is typically done as a one time
	 * operation, and not during a loop. Use {@link Object3D#rotation} for typical
	 * real-time mesh rotation.
	 *
	 * @param {number} angle - The angle in radians.
	 * @return {BufferGeometry} A reference to this instance.
	 */
```

**Parameters:**

- **`angle`** `number`

**Returns:** `BufferGeometry`

**Calls:**

- `_m1.makeRotationZ`
- `this.applyMatrix4`

**Internal Comments:**
```
// rotate geometry around world z-axis (x4)
```

<details><summary>Code</summary>

```typescript
rotateZ( angle ) {

		// rotate geometry around world z-axis

		_m1.makeRotationZ( angle );

		this.applyMatrix4( _m1 );

		return this;

	}
```
</details>

### `BufferGeometry.translate(x: number, y: number, z: number): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Translates the geometry. This is typically done as a one time
	 * operation, and not during a loop. Use {@link Object3D#position} for typical
	 * real-time mesh rotation.
	 *
	 * @param {number} x - The x offset.
	 * @param {number} y - The y offset.
	 * @param {number} z - The z offset.
	 * @return {BufferGeometry} A reference to this instance.
	 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`
- **`z`** `number`

**Returns:** `BufferGeometry`

**Calls:**

- `_m1.makeTranslation`
- `this.applyMatrix4`

**Internal Comments:**
```
// translate geometry (x4)
```

<details><summary>Code</summary>

```typescript
translate( x, y, z ) {

		// translate geometry

		_m1.makeTranslation( x, y, z );

		this.applyMatrix4( _m1 );

		return this;

	}
```
</details>

### `BufferGeometry.scale(x: number, y: number, z: number): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Scales the geometry. This is typically done as a one time
	 * operation, and not during a loop. Use {@link Object3D#scale} for typical
	 * real-time mesh rotation.
	 *
	 * @param {number} x - The x scale.
	 * @param {number} y - The y scale.
	 * @param {number} z - The z scale.
	 * @return {BufferGeometry} A reference to this instance.
	 */
```

**Parameters:**

- **`x`** `number`
- **`y`** `number`
- **`z`** `number`

**Returns:** `BufferGeometry`

**Calls:**

- `_m1.makeScale`
- `this.applyMatrix4`

**Internal Comments:**
```
// scale geometry (x4)
```

<details><summary>Code</summary>

```typescript
scale( x, y, z ) {

		// scale geometry

		_m1.makeScale( x, y, z );

		this.applyMatrix4( _m1 );

		return this;

	}
```
</details>

### `BufferGeometry.lookAt(vector: Vector3): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Rotates the geometry to face a point in 3D space. This is typically done as a one time
	 * operation, and not during a loop. Use {@link Object3D#lookAt} for typical
	 * real-time mesh rotation.
	 *
	 * @param {Vector3} vector - The target point.
	 * @return {BufferGeometry} A reference to this instance.
	 */
```

**Parameters:**

- **`vector`** `Vector3`

**Returns:** `BufferGeometry`

**Calls:**

- `_obj.lookAt`
- `_obj.updateMatrix`
- `this.applyMatrix4`

<details><summary>Code</summary>

```typescript
lookAt( vector ) {

		_obj.lookAt( vector );

		_obj.updateMatrix();

		this.applyMatrix4( _obj.matrix );

		return this;

	}
```
</details>

### `BufferGeometry.center(): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Center the geometry based on its bounding box.
	 *
	 * @return {BufferGeometry} A reference to this instance.
	 */
```

**Returns:** `BufferGeometry`

**Calls:**

- `this.computeBoundingBox`
- `this.boundingBox.getCenter( _offset ).negate`
- `this.translate`

<details><summary>Code</summary>

```typescript
center() {

		this.computeBoundingBox();

		this.boundingBox.getCenter( _offset ).negate();

		this.translate( _offset.x, _offset.y, _offset.z );

		return this;

	}
```
</details>

### `BufferGeometry.setFromPoints(points: Vector3[] | Vector2[]): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Defines a geometry by creating a `position` attribute based on the given array of points. The array
	 * can hold 2D or 3D vectors. When using two-dimensional data, the `z` coordinate for all vertices is
	 * set to `0`.
	 *
	 * If the method is used with an existing `position` attribute, the vertex data are overwritten with the
	 * data from the array. The length of the array must match the vertex count.
	 *
	 * @param {Array<Vector2>|Array<Vector3>} points - The points.
	 * @return {BufferGeometry} A reference to this instance.
	 */
```

**Parameters:**

- **`points`** `Vector3[] | Vector2[]`

**Returns:** `BufferGeometry`

**Calls:**

- `this.getAttribute`
- `position.push`
- `this.setAttribute`
- `Math.min`
- `positionAttribute.setXYZ`
- `console.warn`

<details><summary>Code</summary>

```typescript
setFromPoints( points ) {

		const positionAttribute = this.getAttribute( 'position' );

		if ( positionAttribute === undefined ) {

			const position = [];

			for ( let i = 0, l = points.length; i < l; i ++ ) {

				const point = points[ i ];
				position.push( point.x, point.y, point.z || 0 );

			}

			this.setAttribute( 'position', new Float32BufferAttribute( position, 3 ) );

		} else {

			const l = Math.min( points.length, positionAttribute.count ); // make sure data do not exceed buffer size

			for ( let i = 0; i < l; i ++ ) {

				const point = points[ i ];
				positionAttribute.setXYZ( i, point.x, point.y, point.z || 0 );

			}

			if ( points.length > positionAttribute.count ) {

				console.warn( 'THREE.BufferGeometry: Buffer size too small for points data. Use .dispose() and create a new geometry.' );

			}

			positionAttribute.needsUpdate = true;

		}

		return this;

	}
```
</details>

### `BufferGeometry.computeBoundingBox(): void`

**JSDoc:**
```typescript
/**
	 * Computes the bounding box of the geometry, and updates the `boundingBox` member.
	 * The bounding box is not computed by the engine; it must be computed by your app.
	 * You may need to recompute the bounding box if the geometry vertices are modified.
	 */
```

**Returns:** `void`

**Calls:**

- `console.error`
- `this.boundingBox.set`
- `this.boundingBox.setFromBufferAttribute`
- `_box.setFromBufferAttribute`
- `_vector.addVectors`
- `this.boundingBox.expandByPoint`
- `this.boundingBox.makeEmpty`
- `isNaN`

**Internal Comments:**
```
// process morph attributes if present
```

<details><summary>Code</summary>

```typescript
computeBoundingBox() {

		if ( this.boundingBox === null ) {

			this.boundingBox = new Box3();

		}

		const position = this.attributes.position;
		const morphAttributesPosition = this.morphAttributes.position;

		if ( position && position.isGLBufferAttribute ) {

			console.error( 'THREE.BufferGeometry.computeBoundingBox(): GLBufferAttribute requires a manual bounding box.', this );

			this.boundingBox.set(
				new Vector3( - Infinity, - Infinity, - Infinity ),
				new Vector3( + Infinity, + Infinity, + Infinity )
			);

			return;

		}

		if ( position !== undefined ) {

			this.boundingBox.setFromBufferAttribute( position );

			// process morph attributes if present

			if ( morphAttributesPosition ) {

				for ( let i = 0, il = morphAttributesPosition.length; i < il; i ++ ) {

					const morphAttribute = morphAttributesPosition[ i ];
					_box.setFromBufferAttribute( morphAttribute );

					if ( this.morphTargetsRelative ) {

						_vector.addVectors( this.boundingBox.min, _box.min );
						this.boundingBox.expandByPoint( _vector );

						_vector.addVectors( this.boundingBox.max, _box.max );
						this.boundingBox.expandByPoint( _vector );

					} else {

						this.boundingBox.expandByPoint( _box.min );
						this.boundingBox.expandByPoint( _box.max );

					}

				}

			}

		} else {

			this.boundingBox.makeEmpty();

		}

		if ( isNaN( this.boundingBox.min.x ) || isNaN( this.boundingBox.min.y ) || isNaN( this.boundingBox.min.z ) ) {

			console.error( 'THREE.BufferGeometry.computeBoundingBox(): Computed min/max have NaN values. The "position" attribute is likely to have NaN values.', this );

		}

	}
```
</details>

### `BufferGeometry.computeBoundingSphere(): void`

**JSDoc:**
```typescript
/**
	 * Computes the bounding sphere of the geometry, and updates the `boundingSphere` member.
	 * The engine automatically computes the bounding sphere when it is needed, e.g., for ray casting or view frustum culling.
	 * You may need to recompute the bounding sphere if the geometry vertices are modified.
	 */
```

**Returns:** `void`

**Calls:**

- `console.error`
- `this.boundingSphere.set`
- `_box.setFromBufferAttribute`
- `_boxMorphTargets.setFromBufferAttribute`
- `_vector.addVectors`
- `_box.expandByPoint`
- `_box.getCenter`
- `_vector.fromBufferAttribute`
- `Math.max`
- `center.distanceToSquared`
- `_offset.fromBufferAttribute`
- `_vector.add`
- `Math.sqrt`
- `isNaN`

**Internal Comments:**
```
// first, find the center of the bounding sphere (x2)
// process morph attributes if present (x2)
// second, try to find a boundingSphere with a radius smaller than the (x2)
// boundingSphere of the boundingBox: sqrt(3) smaller in the best case (x2)
```

<details><summary>Code</summary>

```typescript
computeBoundingSphere() {

		if ( this.boundingSphere === null ) {

			this.boundingSphere = new Sphere();

		}

		const position = this.attributes.position;
		const morphAttributesPosition = this.morphAttributes.position;

		if ( position && position.isGLBufferAttribute ) {

			console.error( 'THREE.BufferGeometry.computeBoundingSphere(): GLBufferAttribute requires a manual bounding sphere.', this );

			this.boundingSphere.set( new Vector3(), Infinity );

			return;

		}

		if ( position ) {

			// first, find the center of the bounding sphere

			const center = this.boundingSphere.center;

			_box.setFromBufferAttribute( position );

			// process morph attributes if present

			if ( morphAttributesPosition ) {

				for ( let i = 0, il = morphAttributesPosition.length; i < il; i ++ ) {

					const morphAttribute = morphAttributesPosition[ i ];
					_boxMorphTargets.setFromBufferAttribute( morphAttribute );

					if ( this.morphTargetsRelative ) {

						_vector.addVectors( _box.min, _boxMorphTargets.min );
						_box.expandByPoint( _vector );

						_vector.addVectors( _box.max, _boxMorphTargets.max );
						_box.expandByPoint( _vector );

					} else {

						_box.expandByPoint( _boxMorphTargets.min );
						_box.expandByPoint( _boxMorphTargets.max );

					}

				}

			}

			_box.getCenter( center );

			// second, try to find a boundingSphere with a radius smaller than the
			// boundingSphere of the boundingBox: sqrt(3) smaller in the best case

			let maxRadiusSq = 0;

			for ( let i = 0, il = position.count; i < il; i ++ ) {

				_vector.fromBufferAttribute( position, i );

				maxRadiusSq = Math.max( maxRadiusSq, center.distanceToSquared( _vector ) );

			}

			// process morph attributes if present

			if ( morphAttributesPosition ) {

				for ( let i = 0, il = morphAttributesPosition.length; i < il; i ++ ) {

					const morphAttribute = morphAttributesPosition[ i ];
					const morphTargetsRelative = this.morphTargetsRelative;

					for ( let j = 0, jl = morphAttribute.count; j < jl; j ++ ) {

						_vector.fromBufferAttribute( morphAttribute, j );

						if ( morphTargetsRelative ) {

							_offset.fromBufferAttribute( position, j );
							_vector.add( _offset );

						}

						maxRadiusSq = Math.max( maxRadiusSq, center.distanceToSquared( _vector ) );

					}

				}

			}

			this.boundingSphere.radius = Math.sqrt( maxRadiusSq );

			if ( isNaN( this.boundingSphere.radius ) ) {

				console.error( 'THREE.BufferGeometry.computeBoundingSphere(): Computed radius is NaN. The "position" attribute is likely to have NaN values.', this );

			}

		}

	}
```
</details>

### `BufferGeometry.computeTangents(): void`

**JSDoc:**
```typescript
/**
	 * Calculates and adds a tangent attribute to this geometry.
	 *
	 * The computation is only supported for indexed geometries and if position, normal, and uv attributes
	 * are defined. When using a tangent space normal map, prefer the MikkTSpace algorithm provided by
	 * {@link BufferGeometryUtils#computeMikkTSpaceTangents} instead.
	 */
```

**Returns:** `void`

**Calls:**

- `console.error`
- `this.hasAttribute`
- `this.setAttribute`
- `this.getAttribute`
- `vA.fromBufferAttribute`
- `vB.fromBufferAttribute`
- `vC.fromBufferAttribute`
- `uvA.fromBufferAttribute`
- `uvB.fromBufferAttribute`
- `uvC.fromBufferAttribute`
- `vB.sub`
- `vC.sub`
- `uvB.sub`
- `uvC.sub`
- `isFinite`
- `sdir.copy( vB ).multiplyScalar( uvC.y ).addScaledVector( vC, - uvB.y ).multiplyScalar`
- `tdir.copy( vC ).multiplyScalar( uvB.x ).addScaledVector( vB, - uvC.x ).multiplyScalar`
- `tan1[ a ].add`
- `tan1[ b ].add`
- `tan1[ c ].add`
- `tan2[ a ].add`
- `tan2[ b ].add`
- `tan2[ c ].add`
- `handleTriangle`
- `index.getX`
- `n.fromBufferAttribute`
- `n2.copy`
- `tmp.copy`
- `tmp.sub( n.multiplyScalar( n.dot( t ) ) ).normalize`
- `tmp2.crossVectors`
- `tmp2.dot`
- `tangentAttribute.setXYZW`
- `handleVertex`

**Internal Comments:**
```
// based on http://www.terathon.com/code/tangent.html
// (per vertex tangents)
// silently ignore degenerate uv triangles having coincident or colinear vertices
// Gram-Schmidt orthogonalize (x4)
// Calculate handedness (x4)
```

<details><summary>Code</summary>

```typescript
computeTangents() {

		const index = this.index;
		const attributes = this.attributes;

		// based on http://www.terathon.com/code/tangent.html
		// (per vertex tangents)

		if ( index === null ||
			 attributes.position === undefined ||
			 attributes.normal === undefined ||
			 attributes.uv === undefined ) {

			console.error( 'THREE.BufferGeometry: .computeTangents() failed. Missing required attributes (index, position, normal or uv)' );
			return;

		}

		const positionAttribute = attributes.position;
		const normalAttribute = attributes.normal;
		const uvAttribute = attributes.uv;

		if ( this.hasAttribute( 'tangent' ) === false ) {

			this.setAttribute( 'tangent', new BufferAttribute( new Float32Array( 4 * positionAttribute.count ), 4 ) );

		}

		const tangentAttribute = this.getAttribute( 'tangent' );

		const tan1 = [], tan2 = [];

		for ( let i = 0; i < positionAttribute.count; i ++ ) {

			tan1[ i ] = new Vector3();
			tan2[ i ] = new Vector3();

		}

		const vA = new Vector3(),
			vB = new Vector3(),
			vC = new Vector3(),

			uvA = new Vector2(),
			uvB = new Vector2(),
			uvC = new Vector2(),

			sdir = new Vector3(),
			tdir = new Vector3();

		function handleTriangle( a, b, c ) {

			vA.fromBufferAttribute( positionAttribute, a );
			vB.fromBufferAttribute( positionAttribute, b );
			vC.fromBufferAttribute( positionAttribute, c );

			uvA.fromBufferAttribute( uvAttribute, a );
			uvB.fromBufferAttribute( uvAttribute, b );
			uvC.fromBufferAttribute( uvAttribute, c );

			vB.sub( vA );
			vC.sub( vA );

			uvB.sub( uvA );
			uvC.sub( uvA );

			const r = 1.0 / ( uvB.x * uvC.y - uvC.x * uvB.y );

			// silently ignore degenerate uv triangles having coincident or colinear vertices

			if ( ! isFinite( r ) ) return;

			sdir.copy( vB ).multiplyScalar( uvC.y ).addScaledVector( vC, - uvB.y ).multiplyScalar( r );
			tdir.copy( vC ).multiplyScalar( uvB.x ).addScaledVector( vB, - uvC.x ).multiplyScalar( r );

			tan1[ a ].add( sdir );
			tan1[ b ].add( sdir );
			tan1[ c ].add( sdir );

			tan2[ a ].add( tdir );
			tan2[ b ].add( tdir );
			tan2[ c ].add( tdir );

		}

		let groups = this.groups;

		if ( groups.length === 0 ) {

			groups = [ {
				start: 0,
				count: index.count
			} ];

		}

		for ( let i = 0, il = groups.length; i < il; ++ i ) {

			const group = groups[ i ];

			const start = group.start;
			const count = group.count;

			for ( let j = start, jl = start + count; j < jl; j += 3 ) {

				handleTriangle(
					index.getX( j + 0 ),
					index.getX( j + 1 ),
					index.getX( j + 2 )
				);

			}

		}

		const tmp = new Vector3(), tmp2 = new Vector3();
		const n = new Vector3(), n2 = new Vector3();

		function handleVertex( v ) {

			n.fromBufferAttribute( normalAttribute, v );
			n2.copy( n );

			const t = tan1[ v ];

			// Gram-Schmidt orthogonalize

			tmp.copy( t );
			tmp.sub( n.multiplyScalar( n.dot( t ) ) ).normalize();

			// Calculate handedness

			tmp2.crossVectors( n2, t );
			const test = tmp2.dot( tan2[ v ] );
			const w = ( test < 0.0 ) ? - 1.0 : 1.0;

			tangentAttribute.setXYZW( v, tmp.x, tmp.y, tmp.z, w );

		}

		for ( let i = 0, il = groups.length; i < il; ++ i ) {

			const group = groups[ i ];

			const start = group.start;
			const count = group.count;

			for ( let j = start, jl = start + count; j < jl; j += 3 ) {

				handleVertex( index.getX( j + 0 ) );
				handleVertex( index.getX( j + 1 ) );
				handleVertex( index.getX( j + 2 ) );

			}

		}

	}
```
</details>

### `BufferGeometry.computeVertexNormals(): void`

**JSDoc:**
```typescript
/**
	 * Computes vertex normals for the given vertex data. For indexed geometries, the method sets
	 * each vertex normal to be the average of the face normals of the faces that share that vertex.
	 * For non-indexed geometries, vertices are not shared, and the method sets each vertex normal
	 * to be the same as the face normal.
	 */
```

**Returns:** `void`

**Calls:**

- `this.getAttribute`
- `this.setAttribute`
- `normalAttribute.setXYZ`
- `index.getX`
- `pA.fromBufferAttribute`
- `pB.fromBufferAttribute`
- `pC.fromBufferAttribute`
- `cb.subVectors`
- `ab.subVectors`
- `cb.cross`
- `nA.fromBufferAttribute`
- `nB.fromBufferAttribute`
- `nC.fromBufferAttribute`
- `nA.add`
- `nB.add`
- `nC.add`
- `this.normalizeNormals`

**Internal Comments:**
```
// reset existing normals to zero
// indexed elements
// non-indexed elements (unconnected triangle soup)
```

<details><summary>Code</summary>

```typescript
computeVertexNormals() {

		const index = this.index;
		const positionAttribute = this.getAttribute( 'position' );

		if ( positionAttribute !== undefined ) {

			let normalAttribute = this.getAttribute( 'normal' );

			if ( normalAttribute === undefined ) {

				normalAttribute = new BufferAttribute( new Float32Array( positionAttribute.count * 3 ), 3 );
				this.setAttribute( 'normal', normalAttribute );

			} else {

				// reset existing normals to zero

				for ( let i = 0, il = normalAttribute.count; i < il; i ++ ) {

					normalAttribute.setXYZ( i, 0, 0, 0 );

				}

			}

			const pA = new Vector3(), pB = new Vector3(), pC = new Vector3();
			const nA = new Vector3(), nB = new Vector3(), nC = new Vector3();
			const cb = new Vector3(), ab = new Vector3();

			// indexed elements

			if ( index ) {

				for ( let i = 0, il = index.count; i < il; i += 3 ) {

					const vA = index.getX( i + 0 );
					const vB = index.getX( i + 1 );
					const vC = index.getX( i + 2 );

					pA.fromBufferAttribute( positionAttribute, vA );
					pB.fromBufferAttribute( positionAttribute, vB );
					pC.fromBufferAttribute( positionAttribute, vC );

					cb.subVectors( pC, pB );
					ab.subVectors( pA, pB );
					cb.cross( ab );

					nA.fromBufferAttribute( normalAttribute, vA );
					nB.fromBufferAttribute( normalAttribute, vB );
					nC.fromBufferAttribute( normalAttribute, vC );

					nA.add( cb );
					nB.add( cb );
					nC.add( cb );

					normalAttribute.setXYZ( vA, nA.x, nA.y, nA.z );
					normalAttribute.setXYZ( vB, nB.x, nB.y, nB.z );
					normalAttribute.setXYZ( vC, nC.x, nC.y, nC.z );

				}

			} else {

				// non-indexed elements (unconnected triangle soup)

				for ( let i = 0, il = positionAttribute.count; i < il; i += 3 ) {

					pA.fromBufferAttribute( positionAttribute, i + 0 );
					pB.fromBufferAttribute( positionAttribute, i + 1 );
					pC.fromBufferAttribute( positionAttribute, i + 2 );

					cb.subVectors( pC, pB );
					ab.subVectors( pA, pB );
					cb.cross( ab );

					normalAttribute.setXYZ( i + 0, cb.x, cb.y, cb.z );
					normalAttribute.setXYZ( i + 1, cb.x, cb.y, cb.z );
					normalAttribute.setXYZ( i + 2, cb.x, cb.y, cb.z );

				}

			}

			this.normalizeNormals();

			normalAttribute.needsUpdate = true;

		}

	}
```
</details>

### `BufferGeometry.normalizeNormals(): void`

**JSDoc:**
```typescript
/**
	 * Ensures every normal vector in a geometry will have a magnitude of `1`. This will
	 * correct lighting on the geometry surfaces.
	 */
```

**Returns:** `void`

**Calls:**

- `_vector.fromBufferAttribute`
- `_vector.normalize`
- `normals.setXYZ`

<details><summary>Code</summary>

```typescript
normalizeNormals() {

		const normals = this.attributes.normal;

		for ( let i = 0, il = normals.count; i < il; i ++ ) {

			_vector.fromBufferAttribute( normals, i );

			_vector.normalize();

			normals.setXYZ( i, _vector.x, _vector.y, _vector.z );

		}

	}
```
</details>

### `BufferGeometry.toNonIndexed(): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Return a new non-index version of this indexed geometry. If the geometry
	 * is already non-indexed, the method is a NOOP.
	 *
	 * @return {BufferGeometry} The non-indexed version of this indexed geometry.
	 */
```

**Returns:** `BufferGeometry`

**Calls:**

- `console.warn`
- `convertBufferAttribute`
- `geometry2.setAttribute`
- `morphArray.push`
- `geometry2.addGroup`

**Internal Comments:**
```
//
// attributes
// morph attributes (x2)
// groups (x2)
```

<details><summary>Code</summary>

```typescript
toNonIndexed() {

		function convertBufferAttribute( attribute, indices ) {

			const array = attribute.array;
			const itemSize = attribute.itemSize;
			const normalized = attribute.normalized;

			const array2 = new array.constructor( indices.length * itemSize );

			let index = 0, index2 = 0;

			for ( let i = 0, l = indices.length; i < l; i ++ ) {

				if ( attribute.isInterleavedBufferAttribute ) {

					index = indices[ i ] * attribute.data.stride + attribute.offset;

				} else {

					index = indices[ i ] * itemSize;

				}

				for ( let j = 0; j < itemSize; j ++ ) {

					array2[ index2 ++ ] = array[ index ++ ];

				}

			}

			return new BufferAttribute( array2, itemSize, normalized );

		}

		//

		if ( this.index === null ) {

			console.warn( 'THREE.BufferGeometry.toNonIndexed(): BufferGeometry is already non-indexed.' );
			return this;

		}

		const geometry2 = new BufferGeometry();

		const indices = this.index.array;
		const attributes = this.attributes;

		// attributes

		for ( const name in attributes ) {

			const attribute = attributes[ name ];

			const newAttribute = convertBufferAttribute( attribute, indices );

			geometry2.setAttribute( name, newAttribute );

		}

		// morph attributes

		const morphAttributes = this.morphAttributes;

		for ( const name in morphAttributes ) {

			const morphArray = [];
			const morphAttribute = morphAttributes[ name ]; // morphAttribute: array of Float32BufferAttributes

			for ( let i = 0, il = morphAttribute.length; i < il; i ++ ) {

				const attribute = morphAttribute[ i ];

				const newAttribute = convertBufferAttribute( attribute, indices );

				morphArray.push( newAttribute );

			}

			geometry2.morphAttributes[ name ] = morphArray;

		}

		geometry2.morphTargetsRelative = this.morphTargetsRelative;

		// groups

		const groups = this.groups;

		for ( let i = 0, l = groups.length; i < l; i ++ ) {

			const group = groups[ i ];
			geometry2.addGroup( group.start, group.count, group.materialIndex );

		}

		return geometry2;

	}
```
</details>

### `BufferGeometry.toJSON(): any`

**JSDoc:**
```typescript
/**
	 * Serializes the geometry into JSON.
	 *
	 * @return {Object} A JSON object representing the serialized geometry.
	 */
```

**Returns:** `any`

**Calls:**

- `Object.keys`
- `Array.prototype.slice.call`
- `attribute.toJSON`
- `array.push`
- `JSON.parse`
- `JSON.stringify`
- `boundingSphere.toJSON`

**Internal Comments:**
```
// standard BufferGeometry serialization (x4)
// for simplicity the code assumes attributes are not shared across geometries, see #15811 (x4)
```

<details><summary>Code</summary>

```typescript
toJSON() {

		const data = {
			metadata: {
				version: 4.7,
				type: 'BufferGeometry',
				generator: 'BufferGeometry.toJSON'
			}
		};

		// standard BufferGeometry serialization

		data.uuid = this.uuid;
		data.type = this.type;
		if ( this.name !== '' ) data.name = this.name;
		if ( Object.keys( this.userData ).length > 0 ) data.userData = this.userData;

		if ( this.parameters !== undefined ) {

			const parameters = this.parameters;

			for ( const key in parameters ) {

				if ( parameters[ key ] !== undefined ) data[ key ] = parameters[ key ];

			}

			return data;

		}

		// for simplicity the code assumes attributes are not shared across geometries, see #15811

		data.data = { attributes: {} };

		const index = this.index;

		if ( index !== null ) {

			data.data.index = {
				type: index.array.constructor.name,
				array: Array.prototype.slice.call( index.array )
			};

		}

		const attributes = this.attributes;

		for ( const key in attributes ) {

			const attribute = attributes[ key ];

			data.data.attributes[ key ] = attribute.toJSON( data.data );

		}

		const morphAttributes = {};
		let hasMorphAttributes = false;

		for ( const key in this.morphAttributes ) {

			const attributeArray = this.morphAttributes[ key ];

			const array = [];

			for ( let i = 0, il = attributeArray.length; i < il; i ++ ) {

				const attribute = attributeArray[ i ];

				array.push( attribute.toJSON( data.data ) );

			}

			if ( array.length > 0 ) {

				morphAttributes[ key ] = array;

				hasMorphAttributes = true;

			}

		}

		if ( hasMorphAttributes ) {

			data.data.morphAttributes = morphAttributes;
			data.data.morphTargetsRelative = this.morphTargetsRelative;

		}

		const groups = this.groups;

		if ( groups.length > 0 ) {

			data.data.groups = JSON.parse( JSON.stringify( groups ) );

		}

		const boundingSphere = this.boundingSphere;

		if ( boundingSphere !== null ) {

			data.data.boundingSphere = boundingSphere.toJSON();

		}

		return data;

	}
```
</details>

### `BufferGeometry.clone(): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Returns a new geometry with copied values from this instance.
	 *
	 * @return {BufferGeometry} A clone of this instance.
	 */
```

**Returns:** `BufferGeometry`

**Calls:**

- `new this.constructor().copy`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor().copy( this );

	}
```
</details>

### `BufferGeometry.copy(source: BufferGeometry): BufferGeometry`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given geometry to this instance.
	 *
	 * @param {BufferGeometry} source - The geometry to copy.
	 * @return {BufferGeometry} A reference to this instance.
	 */
```

**Parameters:**

- **`source`** `BufferGeometry`

**Returns:** `BufferGeometry`

**Calls:**

- `this.setIndex`
- `index.clone`
- `this.setAttribute`
- `attribute.clone`
- `array.push`
- `morphAttribute[ i ].clone`
- `this.addGroup`
- `boundingBox.clone`
- `boundingSphere.clone`

**Internal Comments:**
```
// reset (x4)
// used for storing cloned, shared data (x2)
// name (x4)
// index (x2)
// attributes (x2)
// morph attributes (x2)
// groups (x2)
// bounding box (x2)
// bounding sphere (x2)
// draw range (x5)
// user data (x4)
```

<details><summary>Code</summary>

```typescript
copy( source ) {

		// reset

		this.index = null;
		this.attributes = {};
		this.morphAttributes = {};
		this.groups = [];
		this.boundingBox = null;
		this.boundingSphere = null;

		// used for storing cloned, shared data

		const data = {};

		// name

		this.name = source.name;

		// index

		const index = source.index;

		if ( index !== null ) {

			this.setIndex( index.clone() );

		}

		// attributes

		const attributes = source.attributes;

		for ( const name in attributes ) {

			const attribute = attributes[ name ];
			this.setAttribute( name, attribute.clone( data ) );

		}

		// morph attributes

		const morphAttributes = source.morphAttributes;

		for ( const name in morphAttributes ) {

			const array = [];
			const morphAttribute = morphAttributes[ name ]; // morphAttribute: array of Float32BufferAttributes

			for ( let i = 0, l = morphAttribute.length; i < l; i ++ ) {

				array.push( morphAttribute[ i ].clone( data ) );

			}

			this.morphAttributes[ name ] = array;

		}

		this.morphTargetsRelative = source.morphTargetsRelative;

		// groups

		const groups = source.groups;

		for ( let i = 0, l = groups.length; i < l; i ++ ) {

			const group = groups[ i ];
			this.addGroup( group.start, group.count, group.materialIndex );

		}

		// bounding box

		const boundingBox = source.boundingBox;

		if ( boundingBox !== null ) {

			this.boundingBox = boundingBox.clone();

		}

		// bounding sphere

		const boundingSphere = source.boundingSphere;

		if ( boundingSphere !== null ) {

			this.boundingSphere = boundingSphere.clone();

		}

		// draw range

		this.drawRange.start = source.drawRange.start;
		this.drawRange.count = source.drawRange.count;

		// user data

		this.userData = source.userData;

		return this;

	}
```
</details>

### `BufferGeometry.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 *
	 * @fires BufferGeometry#dispose
	 */
```

**Returns:** `void`

**Calls:**

- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
dispose() {

		this.dispatchEvent( { type: 'dispose' } );

	}
```
</details>

### `handleTriangle(a: any, b: any, c: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`
- **`c`** `any`

**Returns:** `void`

**Calls:**

- `vA.fromBufferAttribute`
- `vB.fromBufferAttribute`
- `vC.fromBufferAttribute`
- `uvA.fromBufferAttribute`
- `uvB.fromBufferAttribute`
- `uvC.fromBufferAttribute`
- `vB.sub`
- `vC.sub`
- `uvB.sub`
- `uvC.sub`
- `isFinite`
- `sdir.copy( vB ).multiplyScalar( uvC.y ).addScaledVector( vC, - uvB.y ).multiplyScalar`
- `tdir.copy( vC ).multiplyScalar( uvB.x ).addScaledVector( vB, - uvC.x ).multiplyScalar`
- `tan1[ a ].add`
- `tan1[ b ].add`
- `tan1[ c ].add`
- `tan2[ a ].add`
- `tan2[ b ].add`
- `tan2[ c ].add`

**Internal Comments:**
```
// silently ignore degenerate uv triangles having coincident or colinear vertices
```

<details><summary>Code</summary>

```typescript
function handleTriangle( a, b, c ) {

			vA.fromBufferAttribute( positionAttribute, a );
			vB.fromBufferAttribute( positionAttribute, b );
			vC.fromBufferAttribute( positionAttribute, c );

			uvA.fromBufferAttribute( uvAttribute, a );
			uvB.fromBufferAttribute( uvAttribute, b );
			uvC.fromBufferAttribute( uvAttribute, c );

			vB.sub( vA );
			vC.sub( vA );

			uvB.sub( uvA );
			uvC.sub( uvA );

			const r = 1.0 / ( uvB.x * uvC.y - uvC.x * uvB.y );

			// silently ignore degenerate uv triangles having coincident or colinear vertices

			if ( ! isFinite( r ) ) return;

			sdir.copy( vB ).multiplyScalar( uvC.y ).addScaledVector( vC, - uvB.y ).multiplyScalar( r );
			tdir.copy( vC ).multiplyScalar( uvB.x ).addScaledVector( vB, - uvC.x ).multiplyScalar( r );

			tan1[ a ].add( sdir );
			tan1[ b ].add( sdir );
			tan1[ c ].add( sdir );

			tan2[ a ].add( tdir );
			tan2[ b ].add( tdir );
			tan2[ c ].add( tdir );

		}
```
</details>

### `handleVertex(v: any): void`

**Parameters:**

- **`v`** `any`

**Returns:** `void`

**Calls:**

- `n.fromBufferAttribute`
- `n2.copy`
- `tmp.copy`
- `tmp.sub( n.multiplyScalar( n.dot( t ) ) ).normalize`
- `tmp2.crossVectors`
- `tmp2.dot`
- `tangentAttribute.setXYZW`

**Internal Comments:**
```
// Gram-Schmidt orthogonalize (x4)
// Calculate handedness (x4)
```

<details><summary>Code</summary>

```typescript
function handleVertex( v ) {

			n.fromBufferAttribute( normalAttribute, v );
			n2.copy( n );

			const t = tan1[ v ];

			// Gram-Schmidt orthogonalize

			tmp.copy( t );
			tmp.sub( n.multiplyScalar( n.dot( t ) ) ).normalize();

			// Calculate handedness

			tmp2.crossVectors( n2, t );
			const test = tmp2.dot( tan2[ v ] );
			const w = ( test < 0.0 ) ? - 1.0 : 1.0;

			tangentAttribute.setXYZW( v, tmp.x, tmp.y, tmp.z, w );

		}
```
</details>

### `convertBufferAttribute(attribute: any, indices: any): BufferAttribute`

**Parameters:**

- **`attribute`** `any`
- **`indices`** `any`

**Returns:** `BufferAttribute`

<details><summary>Code</summary>

```typescript
function convertBufferAttribute( attribute, indices ) {

			const array = attribute.array;
			const itemSize = attribute.itemSize;
			const normalized = attribute.normalized;

			const array2 = new array.constructor( indices.length * itemSize );

			let index = 0, index2 = 0;

			for ( let i = 0, l = indices.length; i < l; i ++ ) {

				if ( attribute.isInterleavedBufferAttribute ) {

					index = indices[ i ] * attribute.data.stride + attribute.offset;

				} else {

					index = indices[ i ] * itemSize;

				}

				for ( let j = 0; j < itemSize; j ++ ) {

					array2[ index2 ++ ] = array[ index ++ ];

				}

			}

			return new BufferAttribute( array2, itemSize, normalized );

		}
```
</details>


---

## Classes

### `BufferGeometry`

<details><summary>Class Code</summary>

```ts
class BufferGeometry extends EventDispatcher {

	/**
	 * Constructs a new geometry.
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
		this.isBufferGeometry = true;

		/**
		 * The ID of the geometry.
		 *
		 * @name BufferGeometry#id
		 * @type {number}
		 * @readonly
		 */
		Object.defineProperty( this, 'id', { value: _id ++ } );

		/**
		 * The UUID of the geometry.
		 *
		 * @type {string}
		 * @readonly
		 */
		this.uuid = generateUUID();

		/**
		 * The name of the geometry.
		 *
		 * @type {string}
		 */
		this.name = '';
		this.type = 'BufferGeometry';

		/**
		 * Allows for vertices to be re-used across multiple triangles; this is
		 * called using "indexed triangles". Each triangle is associated with the
		 * indices of three vertices. This attribute therefore stores the index of
		 * each vertex for each triangular face. If this attribute is not set, the
		 * renderer assumes that each three contiguous positions represent a single triangle.
		 *
		 * @type {?BufferAttribute}
		 * @default null
		 */
		this.index = null;

		/**
		 * A (storage) buffer attribute which was generated with a compute shader and
		 * now defines indirect draw calls.
		 *
		 * Can only be used with {@link WebGPURenderer} and a WebGPU backend.
		 *
		 * @type {?BufferAttribute}
		 * @default null
		 */
		this.indirect = null;

		/**
		 * This dictionary has as id the name of the attribute to be set and as value
		 * the buffer attribute to set it to. Rather than accessing this property directly,
		 * use `setAttribute()` and `getAttribute()` to access attributes of this geometry.
		 *
		 * @type {Object<string,(BufferAttribute|InterleavedBufferAttribute)>}
		 */
		this.attributes = {};

		/**
		 * This dictionary holds the morph targets of the geometry.
		 *
		 * Note: Once the geometry has been rendered, the morph attribute data cannot
		 * be changed. You will have to call `dispose()?, and create a new geometry instance.
		 *
		 * @type {Object}
		 */
		this.morphAttributes = {};

		/**
		 * Used to control the morph target behavior; when set to `true`, the morph
		 * target data is treated as relative offsets, rather than as absolute
		 * positions/normals.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.morphTargetsRelative = false;

		/**
		 * Split the geometry into groups, each of which will be rendered in a
		 * separate draw call. This allows an array of materials to be used with the geometry.
		 *
		 * Use `addGroup()` and `clearGroups()` to edit groups, rather than modifying this array directly.
		 *
		 * Every vertex and index must belong to exactly one group — groups must not share vertices or
		 * indices, and must not leave vertices or indices unused.
		 *
		 * @type {Array<Object>}
		 */
		this.groups = [];

		/**
		 * Bounding box for the geometry which can be calculated with `computeBoundingBox()`.
		 *
		 * @type {Box3}
		 * @default null
		 */
		this.boundingBox = null;

		/**
		 * Bounding sphere for the geometry which can be calculated with `computeBoundingSphere()`.
		 *
		 * @type {Sphere}
		 * @default null
		 */
		this.boundingSphere = null;

		/**
		 * Determines the part of the geometry to render. This should not be set directly,
		 * instead use `setDrawRange()`.
		 *
		 * @type {{start:number,count:number}}
		 */
		this.drawRange = { start: 0, count: Infinity };

		/**
		 * An object that can be used to store custom data about the geometry.
		 * It should not hold references to functions as these will not be cloned.
		 *
		 * @type {Object}
		 */
		this.userData = {};

	}

	/**
	 * Returns the index of this geometry.
	 *
	 * @return {?BufferAttribute} The index. Returns `null` if no index is defined.
	 */
	getIndex() {

		return this.index;

	}

	/**
	 * Sets the given index to this geometry.
	 *
	 * @param {Array<number>|BufferAttribute} index - The index to set.
	 * @return {BufferGeometry} A reference to this instance.
	 */
	setIndex( index ) {

		if ( Array.isArray( index ) ) {

			this.index = new ( arrayNeedsUint32( index ) ? Uint32BufferAttribute : Uint16BufferAttribute )( index, 1 );

		} else {

			this.index = index;

		}

		return this;

	}

	/**
	 * Sets the given indirect attribute to this geometry.
	 *
	 * @param {BufferAttribute} indirect - The attribute holding indirect draw calls.
	 * @return {BufferGeometry} A reference to this instance.
	 */
	setIndirect( indirect ) {

		this.indirect = indirect;

		return this;

	}

	/**
	 * Returns the indirect attribute of this geometry.
	 *
	 * @return {?BufferAttribute} The indirect attribute. Returns `null` if no indirect attribute is defined.
	 */
	getIndirect() {

		return this.indirect;

	}

	/**
	 * Returns the buffer attribute for the given name.
	 *
	 * @param {string} name - The attribute name.
	 * @return {BufferAttribute|InterleavedBufferAttribute|undefined} The buffer attribute.
	 * Returns `undefined` if not attribute has been found.
	 */
	getAttribute( name ) {

		return this.attributes[ name ];

	}

	/**
	 * Sets the given attribute for the given name.
	 *
	 * @param {string} name - The attribute name.
	 * @param {BufferAttribute|InterleavedBufferAttribute} attribute - The attribute to set.
	 * @return {BufferGeometry} A reference to this instance.
	 */
	setAttribute( name, attribute ) {

		this.attributes[ name ] = attribute;

		return this;

	}

	/**
	 * Deletes the attribute for the given name.
	 *
	 * @param {string} name - The attribute name to delete.
	 * @return {BufferGeometry} A reference to this instance.
	 */
	deleteAttribute( name ) {

		delete this.attributes[ name ];

		return this;

	}

	/**
	 * Returns `true` if this geometry has an attribute for the given name.
	 *
	 * @param {string} name - The attribute name.
	 * @return {boolean} Whether this geometry has an attribute for the given name or not.
	 */
	hasAttribute( name ) {

		return this.attributes[ name ] !== undefined;

	}

	/**
	 * Adds a group to this geometry.
	 *
	 * @param {number} start - The first element in this draw call. That is the first
	 * vertex for non-indexed geometry, otherwise the first triangle index.
	 * @param {number} count - Specifies how many vertices (or indices) are part of this group.
	 * @param {number} [materialIndex=0] - The material array index to use.
	 */
	addGroup( start, count, materialIndex = 0 ) {

		this.groups.push( {

			start: start,
			count: count,
			materialIndex: materialIndex

		} );

	}

	/**
	 * Clears all groups.
	 */
	clearGroups() {

		this.groups = [];

	}

	/**
	 * Sets the draw range for this geometry.
	 *
	 * @param {number} start - The first vertex for non-indexed geometry, otherwise the first triangle index.
	 * @param {number} count - For non-indexed BufferGeometry, `count` is the number of vertices to render.
	 * For indexed BufferGeometry, `count` is the number of indices to render.
	 */
	setDrawRange( start, count ) {

		this.drawRange.start = start;
		this.drawRange.count = count;

	}

	/**
	 * Applies the given 4x4 transformation matrix to the geometry.
	 *
	 * @param {Matrix4} matrix - The matrix to apply.
	 * @return {BufferGeometry} A reference to this instance.
	 */
	applyMatrix4( matrix ) {

		const position = this.attributes.position;

		if ( position !== undefined ) {

			position.applyMatrix4( matrix );

			position.needsUpdate = true;

		}

		const normal = this.attributes.normal;

		if ( normal !== undefined ) {

			const normalMatrix = new Matrix3().getNormalMatrix( matrix );

			normal.applyNormalMatrix( normalMatrix );

			normal.needsUpdate = true;

		}

		const tangent = this.attributes.tangent;

		if ( tangent !== undefined ) {

			tangent.transformDirection( matrix );

			tangent.needsUpdate = true;

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
	 * Applies the rotation represented by the Quaternion to the geometry.
	 *
	 * @param {Quaternion} q - The Quaternion to apply.
	 * @return {BufferGeometry} A reference to this instance.
	 */
	applyQuaternion( q ) {

		_m1.makeRotationFromQuaternion( q );

		this.applyMatrix4( _m1 );

		return this;

	}

	/**
	 * Rotates the geometry about the X axis. This is typically done as a one time
	 * operation, and not during a loop. Use {@link Object3D#rotation} for typical
	 * real-time mesh rotation.
	 *
	 * @param {number} angle - The angle in radians.
	 * @return {BufferGeometry} A reference to this instance.
	 */
	rotateX( angle ) {

		// rotate geometry around world x-axis

		_m1.makeRotationX( angle );

		this.applyMatrix4( _m1 );

		return this;

	}

	/**
	 * Rotates the geometry about the Y axis. This is typically done as a one time
	 * operation, and not during a loop. Use {@link Object3D#rotation} for typical
	 * real-time mesh rotation.
	 *
	 * @param {number} angle - The angle in radians.
	 * @return {BufferGeometry} A reference to this instance.
	 */
	rotateY( angle ) {

		// rotate geometry around world y-axis

		_m1.makeRotationY( angle );

		this.applyMatrix4( _m1 );

		return this;

	}

	/**
	 * Rotates the geometry about the Z axis. This is typically done as a one time
	 * operation, and not during a loop. Use {@link Object3D#rotation} for typical
	 * real-time mesh rotation.
	 *
	 * @param {number} angle - The angle in radians.
	 * @return {BufferGeometry} A reference to this instance.
	 */
	rotateZ( angle ) {

		// rotate geometry around world z-axis

		_m1.makeRotationZ( angle );

		this.applyMatrix4( _m1 );

		return this;

	}

	/**
	 * Translates the geometry. This is typically done as a one time
	 * operation, and not during a loop. Use {@link Object3D#position} for typical
	 * real-time mesh rotation.
	 *
	 * @param {number} x - The x offset.
	 * @param {number} y - The y offset.
	 * @param {number} z - The z offset.
	 * @return {BufferGeometry} A reference to this instance.
	 */
	translate( x, y, z ) {

		// translate geometry

		_m1.makeTranslation( x, y, z );

		this.applyMatrix4( _m1 );

		return this;

	}

	/**
	 * Scales the geometry. This is typically done as a one time
	 * operation, and not during a loop. Use {@link Object3D#scale} for typical
	 * real-time mesh rotation.
	 *
	 * @param {number} x - The x scale.
	 * @param {number} y - The y scale.
	 * @param {number} z - The z scale.
	 * @return {BufferGeometry} A reference to this instance.
	 */
	scale( x, y, z ) {

		// scale geometry

		_m1.makeScale( x, y, z );

		this.applyMatrix4( _m1 );

		return this;

	}

	/**
	 * Rotates the geometry to face a point in 3D space. This is typically done as a one time
	 * operation, and not during a loop. Use {@link Object3D#lookAt} for typical
	 * real-time mesh rotation.
	 *
	 * @param {Vector3} vector - The target point.
	 * @return {BufferGeometry} A reference to this instance.
	 */
	lookAt( vector ) {

		_obj.lookAt( vector );

		_obj.updateMatrix();

		this.applyMatrix4( _obj.matrix );

		return this;

	}

	/**
	 * Center the geometry based on its bounding box.
	 *
	 * @return {BufferGeometry} A reference to this instance.
	 */
	center() {

		this.computeBoundingBox();

		this.boundingBox.getCenter( _offset ).negate();

		this.translate( _offset.x, _offset.y, _offset.z );

		return this;

	}

	/**
	 * Defines a geometry by creating a `position` attribute based on the given array of points. The array
	 * can hold 2D or 3D vectors. When using two-dimensional data, the `z` coordinate for all vertices is
	 * set to `0`.
	 *
	 * If the method is used with an existing `position` attribute, the vertex data are overwritten with the
	 * data from the array. The length of the array must match the vertex count.
	 *
	 * @param {Array<Vector2>|Array<Vector3>} points - The points.
	 * @return {BufferGeometry} A reference to this instance.
	 */
	setFromPoints( points ) {

		const positionAttribute = this.getAttribute( 'position' );

		if ( positionAttribute === undefined ) {

			const position = [];

			for ( let i = 0, l = points.length; i < l; i ++ ) {

				const point = points[ i ];
				position.push( point.x, point.y, point.z || 0 );

			}

			this.setAttribute( 'position', new Float32BufferAttribute( position, 3 ) );

		} else {

			const l = Math.min( points.length, positionAttribute.count ); // make sure data do not exceed buffer size

			for ( let i = 0; i < l; i ++ ) {

				const point = points[ i ];
				positionAttribute.setXYZ( i, point.x, point.y, point.z || 0 );

			}

			if ( points.length > positionAttribute.count ) {

				console.warn( 'THREE.BufferGeometry: Buffer size too small for points data. Use .dispose() and create a new geometry.' );

			}

			positionAttribute.needsUpdate = true;

		}

		return this;

	}

	/**
	 * Computes the bounding box of the geometry, and updates the `boundingBox` member.
	 * The bounding box is not computed by the engine; it must be computed by your app.
	 * You may need to recompute the bounding box if the geometry vertices are modified.
	 */
	computeBoundingBox() {

		if ( this.boundingBox === null ) {

			this.boundingBox = new Box3();

		}

		const position = this.attributes.position;
		const morphAttributesPosition = this.morphAttributes.position;

		if ( position && position.isGLBufferAttribute ) {

			console.error( 'THREE.BufferGeometry.computeBoundingBox(): GLBufferAttribute requires a manual bounding box.', this );

			this.boundingBox.set(
				new Vector3( - Infinity, - Infinity, - Infinity ),
				new Vector3( + Infinity, + Infinity, + Infinity )
			);

			return;

		}

		if ( position !== undefined ) {

			this.boundingBox.setFromBufferAttribute( position );

			// process morph attributes if present

			if ( morphAttributesPosition ) {

				for ( let i = 0, il = morphAttributesPosition.length; i < il; i ++ ) {

					const morphAttribute = morphAttributesPosition[ i ];
					_box.setFromBufferAttribute( morphAttribute );

					if ( this.morphTargetsRelative ) {

						_vector.addVectors( this.boundingBox.min, _box.min );
						this.boundingBox.expandByPoint( _vector );

						_vector.addVectors( this.boundingBox.max, _box.max );
						this.boundingBox.expandByPoint( _vector );

					} else {

						this.boundingBox.expandByPoint( _box.min );
						this.boundingBox.expandByPoint( _box.max );

					}

				}

			}

		} else {

			this.boundingBox.makeEmpty();

		}

		if ( isNaN( this.boundingBox.min.x ) || isNaN( this.boundingBox.min.y ) || isNaN( this.boundingBox.min.z ) ) {

			console.error( 'THREE.BufferGeometry.computeBoundingBox(): Computed min/max have NaN values. The "position" attribute is likely to have NaN values.', this );

		}

	}

	/**
	 * Computes the bounding sphere of the geometry, and updates the `boundingSphere` member.
	 * The engine automatically computes the bounding sphere when it is needed, e.g., for ray casting or view frustum culling.
	 * You may need to recompute the bounding sphere if the geometry vertices are modified.
	 */
	computeBoundingSphere() {

		if ( this.boundingSphere === null ) {

			this.boundingSphere = new Sphere();

		}

		const position = this.attributes.position;
		const morphAttributesPosition = this.morphAttributes.position;

		if ( position && position.isGLBufferAttribute ) {

			console.error( 'THREE.BufferGeometry.computeBoundingSphere(): GLBufferAttribute requires a manual bounding sphere.', this );

			this.boundingSphere.set( new Vector3(), Infinity );

			return;

		}

		if ( position ) {

			// first, find the center of the bounding sphere

			const center = this.boundingSphere.center;

			_box.setFromBufferAttribute( position );

			// process morph attributes if present

			if ( morphAttributesPosition ) {

				for ( let i = 0, il = morphAttributesPosition.length; i < il; i ++ ) {

					const morphAttribute = morphAttributesPosition[ i ];
					_boxMorphTargets.setFromBufferAttribute( morphAttribute );

					if ( this.morphTargetsRelative ) {

						_vector.addVectors( _box.min, _boxMorphTargets.min );
						_box.expandByPoint( _vector );

						_vector.addVectors( _box.max, _boxMorphTargets.max );
						_box.expandByPoint( _vector );

					} else {

						_box.expandByPoint( _boxMorphTargets.min );
						_box.expandByPoint( _boxMorphTargets.max );

					}

				}

			}

			_box.getCenter( center );

			// second, try to find a boundingSphere with a radius smaller than the
			// boundingSphere of the boundingBox: sqrt(3) smaller in the best case

			let maxRadiusSq = 0;

			for ( let i = 0, il = position.count; i < il; i ++ ) {

				_vector.fromBufferAttribute( position, i );

				maxRadiusSq = Math.max( maxRadiusSq, center.distanceToSquared( _vector ) );

			}

			// process morph attributes if present

			if ( morphAttributesPosition ) {

				for ( let i = 0, il = morphAttributesPosition.length; i < il; i ++ ) {

					const morphAttribute = morphAttributesPosition[ i ];
					const morphTargetsRelative = this.morphTargetsRelative;

					for ( let j = 0, jl = morphAttribute.count; j < jl; j ++ ) {

						_vector.fromBufferAttribute( morphAttribute, j );

						if ( morphTargetsRelative ) {

							_offset.fromBufferAttribute( position, j );
							_vector.add( _offset );

						}

						maxRadiusSq = Math.max( maxRadiusSq, center.distanceToSquared( _vector ) );

					}

				}

			}

			this.boundingSphere.radius = Math.sqrt( maxRadiusSq );

			if ( isNaN( this.boundingSphere.radius ) ) {

				console.error( 'THREE.BufferGeometry.computeBoundingSphere(): Computed radius is NaN. The "position" attribute is likely to have NaN values.', this );

			}

		}

	}

	/**
	 * Calculates and adds a tangent attribute to this geometry.
	 *
	 * The computation is only supported for indexed geometries and if position, normal, and uv attributes
	 * are defined. When using a tangent space normal map, prefer the MikkTSpace algorithm provided by
	 * {@link BufferGeometryUtils#computeMikkTSpaceTangents} instead.
	 */
	computeTangents() {

		const index = this.index;
		const attributes = this.attributes;

		// based on http://www.terathon.com/code/tangent.html
		// (per vertex tangents)

		if ( index === null ||
			 attributes.position === undefined ||
			 attributes.normal === undefined ||
			 attributes.uv === undefined ) {

			console.error( 'THREE.BufferGeometry: .computeTangents() failed. Missing required attributes (index, position, normal or uv)' );
			return;

		}

		const positionAttribute = attributes.position;
		const normalAttribute = attributes.normal;
		const uvAttribute = attributes.uv;

		if ( this.hasAttribute( 'tangent' ) === false ) {

			this.setAttribute( 'tangent', new BufferAttribute( new Float32Array( 4 * positionAttribute.count ), 4 ) );

		}

		const tangentAttribute = this.getAttribute( 'tangent' );

		const tan1 = [], tan2 = [];

		for ( let i = 0; i < positionAttribute.count; i ++ ) {

			tan1[ i ] = new Vector3();
			tan2[ i ] = new Vector3();

		}

		const vA = new Vector3(),
			vB = new Vector3(),
			vC = new Vector3(),

			uvA = new Vector2(),
			uvB = new Vector2(),
			uvC = new Vector2(),

			sdir = new Vector3(),
			tdir = new Vector3();

		function handleTriangle( a, b, c ) {

			vA.fromBufferAttribute( positionAttribute, a );
			vB.fromBufferAttribute( positionAttribute, b );
			vC.fromBufferAttribute( positionAttribute, c );

			uvA.fromBufferAttribute( uvAttribute, a );
			uvB.fromBufferAttribute( uvAttribute, b );
			uvC.fromBufferAttribute( uvAttribute, c );

			vB.sub( vA );
			vC.sub( vA );

			uvB.sub( uvA );
			uvC.sub( uvA );

			const r = 1.0 / ( uvB.x * uvC.y - uvC.x * uvB.y );

			// silently ignore degenerate uv triangles having coincident or colinear vertices

			if ( ! isFinite( r ) ) return;

			sdir.copy( vB ).multiplyScalar( uvC.y ).addScaledVector( vC, - uvB.y ).multiplyScalar( r );
			tdir.copy( vC ).multiplyScalar( uvB.x ).addScaledVector( vB, - uvC.x ).multiplyScalar( r );

			tan1[ a ].add( sdir );
			tan1[ b ].add( sdir );
			tan1[ c ].add( sdir );

			tan2[ a ].add( tdir );
			tan2[ b ].add( tdir );
			tan2[ c ].add( tdir );

		}

		let groups = this.groups;

		if ( groups.length === 0 ) {

			groups = [ {
				start: 0,
				count: index.count
			} ];

		}

		for ( let i = 0, il = groups.length; i < il; ++ i ) {

			const group = groups[ i ];

			const start = group.start;
			const count = group.count;

			for ( let j = start, jl = start + count; j < jl; j += 3 ) {

				handleTriangle(
					index.getX( j + 0 ),
					index.getX( j + 1 ),
					index.getX( j + 2 )
				);

			}

		}

		const tmp = new Vector3(), tmp2 = new Vector3();
		const n = new Vector3(), n2 = new Vector3();

		function handleVertex( v ) {

			n.fromBufferAttribute( normalAttribute, v );
			n2.copy( n );

			const t = tan1[ v ];

			// Gram-Schmidt orthogonalize

			tmp.copy( t );
			tmp.sub( n.multiplyScalar( n.dot( t ) ) ).normalize();

			// Calculate handedness

			tmp2.crossVectors( n2, t );
			const test = tmp2.dot( tan2[ v ] );
			const w = ( test < 0.0 ) ? - 1.0 : 1.0;

			tangentAttribute.setXYZW( v, tmp.x, tmp.y, tmp.z, w );

		}

		for ( let i = 0, il = groups.length; i < il; ++ i ) {

			const group = groups[ i ];

			const start = group.start;
			const count = group.count;

			for ( let j = start, jl = start + count; j < jl; j += 3 ) {

				handleVertex( index.getX( j + 0 ) );
				handleVertex( index.getX( j + 1 ) );
				handleVertex( index.getX( j + 2 ) );

			}

		}

	}

	/**
	 * Computes vertex normals for the given vertex data. For indexed geometries, the method sets
	 * each vertex normal to be the average of the face normals of the faces that share that vertex.
	 * For non-indexed geometries, vertices are not shared, and the method sets each vertex normal
	 * to be the same as the face normal.
	 */
	computeVertexNormals() {

		const index = this.index;
		const positionAttribute = this.getAttribute( 'position' );

		if ( positionAttribute !== undefined ) {

			let normalAttribute = this.getAttribute( 'normal' );

			if ( normalAttribute === undefined ) {

				normalAttribute = new BufferAttribute( new Float32Array( positionAttribute.count * 3 ), 3 );
				this.setAttribute( 'normal', normalAttribute );

			} else {

				// reset existing normals to zero

				for ( let i = 0, il = normalAttribute.count; i < il; i ++ ) {

					normalAttribute.setXYZ( i, 0, 0, 0 );

				}

			}

			const pA = new Vector3(), pB = new Vector3(), pC = new Vector3();
			const nA = new Vector3(), nB = new Vector3(), nC = new Vector3();
			const cb = new Vector3(), ab = new Vector3();

			// indexed elements

			if ( index ) {

				for ( let i = 0, il = index.count; i < il; i += 3 ) {

					const vA = index.getX( i + 0 );
					const vB = index.getX( i + 1 );
					const vC = index.getX( i + 2 );

					pA.fromBufferAttribute( positionAttribute, vA );
					pB.fromBufferAttribute( positionAttribute, vB );
					pC.fromBufferAttribute( positionAttribute, vC );

					cb.subVectors( pC, pB );
					ab.subVectors( pA, pB );
					cb.cross( ab );

					nA.fromBufferAttribute( normalAttribute, vA );
					nB.fromBufferAttribute( normalAttribute, vB );
					nC.fromBufferAttribute( normalAttribute, vC );

					nA.add( cb );
					nB.add( cb );
					nC.add( cb );

					normalAttribute.setXYZ( vA, nA.x, nA.y, nA.z );
					normalAttribute.setXYZ( vB, nB.x, nB.y, nB.z );
					normalAttribute.setXYZ( vC, nC.x, nC.y, nC.z );

				}

			} else {

				// non-indexed elements (unconnected triangle soup)

				for ( let i = 0, il = positionAttribute.count; i < il; i += 3 ) {

					pA.fromBufferAttribute( positionAttribute, i + 0 );
					pB.fromBufferAttribute( positionAttribute, i + 1 );
					pC.fromBufferAttribute( positionAttribute, i + 2 );

					cb.subVectors( pC, pB );
					ab.subVectors( pA, pB );
					cb.cross( ab );

					normalAttribute.setXYZ( i + 0, cb.x, cb.y, cb.z );
					normalAttribute.setXYZ( i + 1, cb.x, cb.y, cb.z );
					normalAttribute.setXYZ( i + 2, cb.x, cb.y, cb.z );

				}

			}

			this.normalizeNormals();

			normalAttribute.needsUpdate = true;

		}

	}

	/**
	 * Ensures every normal vector in a geometry will have a magnitude of `1`. This will
	 * correct lighting on the geometry surfaces.
	 */
	normalizeNormals() {

		const normals = this.attributes.normal;

		for ( let i = 0, il = normals.count; i < il; i ++ ) {

			_vector.fromBufferAttribute( normals, i );

			_vector.normalize();

			normals.setXYZ( i, _vector.x, _vector.y, _vector.z );

		}

	}

	/**
	 * Return a new non-index version of this indexed geometry. If the geometry
	 * is already non-indexed, the method is a NOOP.
	 *
	 * @return {BufferGeometry} The non-indexed version of this indexed geometry.
	 */
	toNonIndexed() {

		function convertBufferAttribute( attribute, indices ) {

			const array = attribute.array;
			const itemSize = attribute.itemSize;
			const normalized = attribute.normalized;

			const array2 = new array.constructor( indices.length * itemSize );

			let index = 0, index2 = 0;

			for ( let i = 0, l = indices.length; i < l; i ++ ) {

				if ( attribute.isInterleavedBufferAttribute ) {

					index = indices[ i ] * attribute.data.stride + attribute.offset;

				} else {

					index = indices[ i ] * itemSize;

				}

				for ( let j = 0; j < itemSize; j ++ ) {

					array2[ index2 ++ ] = array[ index ++ ];

				}

			}

			return new BufferAttribute( array2, itemSize, normalized );

		}

		//

		if ( this.index === null ) {

			console.warn( 'THREE.BufferGeometry.toNonIndexed(): BufferGeometry is already non-indexed.' );
			return this;

		}

		const geometry2 = new BufferGeometry();

		const indices = this.index.array;
		const attributes = this.attributes;

		// attributes

		for ( const name in attributes ) {

			const attribute = attributes[ name ];

			const newAttribute = convertBufferAttribute( attribute, indices );

			geometry2.setAttribute( name, newAttribute );

		}

		// morph attributes

		const morphAttributes = this.morphAttributes;

		for ( const name in morphAttributes ) {

			const morphArray = [];
			const morphAttribute = morphAttributes[ name ]; // morphAttribute: array of Float32BufferAttributes

			for ( let i = 0, il = morphAttribute.length; i < il; i ++ ) {

				const attribute = morphAttribute[ i ];

				const newAttribute = convertBufferAttribute( attribute, indices );

				morphArray.push( newAttribute );

			}

			geometry2.morphAttributes[ name ] = morphArray;

		}

		geometry2.morphTargetsRelative = this.morphTargetsRelative;

		// groups

		const groups = this.groups;

		for ( let i = 0, l = groups.length; i < l; i ++ ) {

			const group = groups[ i ];
			geometry2.addGroup( group.start, group.count, group.materialIndex );

		}

		return geometry2;

	}

	/**
	 * Serializes the geometry into JSON.
	 *
	 * @return {Object} A JSON object representing the serialized geometry.
	 */
	toJSON() {

		const data = {
			metadata: {
				version: 4.7,
				type: 'BufferGeometry',
				generator: 'BufferGeometry.toJSON'
			}
		};

		// standard BufferGeometry serialization

		data.uuid = this.uuid;
		data.type = this.type;
		if ( this.name !== '' ) data.name = this.name;
		if ( Object.keys( this.userData ).length > 0 ) data.userData = this.userData;

		if ( this.parameters !== undefined ) {

			const parameters = this.parameters;

			for ( const key in parameters ) {

				if ( parameters[ key ] !== undefined ) data[ key ] = parameters[ key ];

			}

			return data;

		}

		// for simplicity the code assumes attributes are not shared across geometries, see #15811

		data.data = { attributes: {} };

		const index = this.index;

		if ( index !== null ) {

			data.data.index = {
				type: index.array.constructor.name,
				array: Array.prototype.slice.call( index.array )
			};

		}

		const attributes = this.attributes;

		for ( const key in attributes ) {

			const attribute = attributes[ key ];

			data.data.attributes[ key ] = attribute.toJSON( data.data );

		}

		const morphAttributes = {};
		let hasMorphAttributes = false;

		for ( const key in this.morphAttributes ) {

			const attributeArray = this.morphAttributes[ key ];

			const array = [];

			for ( let i = 0, il = attributeArray.length; i < il; i ++ ) {

				const attribute = attributeArray[ i ];

				array.push( attribute.toJSON( data.data ) );

			}

			if ( array.length > 0 ) {

				morphAttributes[ key ] = array;

				hasMorphAttributes = true;

			}

		}

		if ( hasMorphAttributes ) {

			data.data.morphAttributes = morphAttributes;
			data.data.morphTargetsRelative = this.morphTargetsRelative;

		}

		const groups = this.groups;

		if ( groups.length > 0 ) {

			data.data.groups = JSON.parse( JSON.stringify( groups ) );

		}

		const boundingSphere = this.boundingSphere;

		if ( boundingSphere !== null ) {

			data.data.boundingSphere = boundingSphere.toJSON();

		}

		return data;

	}

	/**
	 * Returns a new geometry with copied values from this instance.
	 *
	 * @return {BufferGeometry} A clone of this instance.
	 */
	clone() {

		return new this.constructor().copy( this );

	}

	/**
	 * Copies the values of the given geometry to this instance.
	 *
	 * @param {BufferGeometry} source - The geometry to copy.
	 * @return {BufferGeometry} A reference to this instance.
	 */
	copy( source ) {

		// reset

		this.index = null;
		this.attributes = {};
		this.morphAttributes = {};
		this.groups = [];
		this.boundingBox = null;
		this.boundingSphere = null;

		// used for storing cloned, shared data

		const data = {};

		// name

		this.name = source.name;

		// index

		const index = source.index;

		if ( index !== null ) {

			this.setIndex( index.clone() );

		}

		// attributes

		const attributes = source.attributes;

		for ( const name in attributes ) {

			const attribute = attributes[ name ];
			this.setAttribute( name, attribute.clone( data ) );

		}

		// morph attributes

		const morphAttributes = source.morphAttributes;

		for ( const name in morphAttributes ) {

			const array = [];
			const morphAttribute = morphAttributes[ name ]; // morphAttribute: array of Float32BufferAttributes

			for ( let i = 0, l = morphAttribute.length; i < l; i ++ ) {

				array.push( morphAttribute[ i ].clone( data ) );

			}

			this.morphAttributes[ name ] = array;

		}

		this.morphTargetsRelative = source.morphTargetsRelative;

		// groups

		const groups = source.groups;

		for ( let i = 0, l = groups.length; i < l; i ++ ) {

			const group = groups[ i ];
			this.addGroup( group.start, group.count, group.materialIndex );

		}

		// bounding box

		const boundingBox = source.boundingBox;

		if ( boundingBox !== null ) {

			this.boundingBox = boundingBox.clone();

		}

		// bounding sphere

		const boundingSphere = source.boundingSphere;

		if ( boundingSphere !== null ) {

			this.boundingSphere = boundingSphere.clone();

		}

		// draw range

		this.drawRange.start = source.drawRange.start;
		this.drawRange.count = source.drawRange.count;

		// user data

		this.userData = source.userData;

		return this;

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 *
	 * @fires BufferGeometry#dispose
	 */
	dispose() {

		this.dispatchEvent( { type: 'dispose' } );

	}

}
```
</details>

#### Methods

##### `getIndex(): BufferAttribute`

<details><summary>Code</summary>

```ts
getIndex() {

		return this.index;

	}
```
</details>

##### `setIndex(index: number[] | BufferAttribute): BufferGeometry`

<details><summary>Code</summary>

```ts
setIndex( index ) {

		if ( Array.isArray( index ) ) {

			this.index = new ( arrayNeedsUint32( index ) ? Uint32BufferAttribute : Uint16BufferAttribute )( index, 1 );

		} else {

			this.index = index;

		}

		return this;

	}
```
</details>

##### `setIndirect(indirect: BufferAttribute): BufferGeometry`

<details><summary>Code</summary>

```ts
setIndirect( indirect ) {

		this.indirect = indirect;

		return this;

	}
```
</details>

##### `getIndirect(): BufferAttribute`

<details><summary>Code</summary>

```ts
getIndirect() {

		return this.indirect;

	}
```
</details>

##### `getAttribute(name: string): any`

<details><summary>Code</summary>

```ts
getAttribute( name ) {

		return this.attributes[ name ];

	}
```
</details>

##### `setAttribute(name: string, attribute: any): BufferGeometry`

<details><summary>Code</summary>

```ts
setAttribute( name, attribute ) {

		this.attributes[ name ] = attribute;

		return this;

	}
```
</details>

##### `deleteAttribute(name: string): BufferGeometry`

<details><summary>Code</summary>

```ts
deleteAttribute( name ) {

		delete this.attributes[ name ];

		return this;

	}
```
</details>

##### `hasAttribute(name: string): boolean`

<details><summary>Code</summary>

```ts
hasAttribute( name ) {

		return this.attributes[ name ] !== undefined;

	}
```
</details>

##### `addGroup(start: number, count: number, materialIndex: number): void`

<details><summary>Code</summary>

```ts
addGroup( start, count, materialIndex = 0 ) {

		this.groups.push( {

			start: start,
			count: count,
			materialIndex: materialIndex

		} );

	}
```
</details>

##### `clearGroups(): void`

<details><summary>Code</summary>

```ts
clearGroups() {

		this.groups = [];

	}
```
</details>

##### `setDrawRange(start: number, count: number): void`

<details><summary>Code</summary>

```ts
setDrawRange( start, count ) {

		this.drawRange.start = start;
		this.drawRange.count = count;

	}
```
</details>

##### `applyMatrix4(matrix: Matrix4): BufferGeometry`

<details><summary>Code</summary>

```ts
applyMatrix4( matrix ) {

		const position = this.attributes.position;

		if ( position !== undefined ) {

			position.applyMatrix4( matrix );

			position.needsUpdate = true;

		}

		const normal = this.attributes.normal;

		if ( normal !== undefined ) {

			const normalMatrix = new Matrix3().getNormalMatrix( matrix );

			normal.applyNormalMatrix( normalMatrix );

			normal.needsUpdate = true;

		}

		const tangent = this.attributes.tangent;

		if ( tangent !== undefined ) {

			tangent.transformDirection( matrix );

			tangent.needsUpdate = true;

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

##### `applyQuaternion(q: Quaternion): BufferGeometry`

<details><summary>Code</summary>

```ts
applyQuaternion( q ) {

		_m1.makeRotationFromQuaternion( q );

		this.applyMatrix4( _m1 );

		return this;

	}
```
</details>

##### `rotateX(angle: number): BufferGeometry`

<details><summary>Code</summary>

```ts
rotateX( angle ) {

		// rotate geometry around world x-axis

		_m1.makeRotationX( angle );

		this.applyMatrix4( _m1 );

		return this;

	}
```
</details>

##### `rotateY(angle: number): BufferGeometry`

<details><summary>Code</summary>

```ts
rotateY( angle ) {

		// rotate geometry around world y-axis

		_m1.makeRotationY( angle );

		this.applyMatrix4( _m1 );

		return this;

	}
```
</details>

##### `rotateZ(angle: number): BufferGeometry`

<details><summary>Code</summary>

```ts
rotateZ( angle ) {

		// rotate geometry around world z-axis

		_m1.makeRotationZ( angle );

		this.applyMatrix4( _m1 );

		return this;

	}
```
</details>

##### `translate(x: number, y: number, z: number): BufferGeometry`

<details><summary>Code</summary>

```ts
translate( x, y, z ) {

		// translate geometry

		_m1.makeTranslation( x, y, z );

		this.applyMatrix4( _m1 );

		return this;

	}
```
</details>

##### `scale(x: number, y: number, z: number): BufferGeometry`

<details><summary>Code</summary>

```ts
scale( x, y, z ) {

		// scale geometry

		_m1.makeScale( x, y, z );

		this.applyMatrix4( _m1 );

		return this;

	}
```
</details>

##### `lookAt(vector: Vector3): BufferGeometry`

<details><summary>Code</summary>

```ts
lookAt( vector ) {

		_obj.lookAt( vector );

		_obj.updateMatrix();

		this.applyMatrix4( _obj.matrix );

		return this;

	}
```
</details>

##### `center(): BufferGeometry`

<details><summary>Code</summary>

```ts
center() {

		this.computeBoundingBox();

		this.boundingBox.getCenter( _offset ).negate();

		this.translate( _offset.x, _offset.y, _offset.z );

		return this;

	}
```
</details>

##### `setFromPoints(points: Vector3[] | Vector2[]): BufferGeometry`

<details><summary>Code</summary>

```ts
setFromPoints( points ) {

		const positionAttribute = this.getAttribute( 'position' );

		if ( positionAttribute === undefined ) {

			const position = [];

			for ( let i = 0, l = points.length; i < l; i ++ ) {

				const point = points[ i ];
				position.push( point.x, point.y, point.z || 0 );

			}

			this.setAttribute( 'position', new Float32BufferAttribute( position, 3 ) );

		} else {

			const l = Math.min( points.length, positionAttribute.count ); // make sure data do not exceed buffer size

			for ( let i = 0; i < l; i ++ ) {

				const point = points[ i ];
				positionAttribute.setXYZ( i, point.x, point.y, point.z || 0 );

			}

			if ( points.length > positionAttribute.count ) {

				console.warn( 'THREE.BufferGeometry: Buffer size too small for points data. Use .dispose() and create a new geometry.' );

			}

			positionAttribute.needsUpdate = true;

		}

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

		const position = this.attributes.position;
		const morphAttributesPosition = this.morphAttributes.position;

		if ( position && position.isGLBufferAttribute ) {

			console.error( 'THREE.BufferGeometry.computeBoundingBox(): GLBufferAttribute requires a manual bounding box.', this );

			this.boundingBox.set(
				new Vector3( - Infinity, - Infinity, - Infinity ),
				new Vector3( + Infinity, + Infinity, + Infinity )
			);

			return;

		}

		if ( position !== undefined ) {

			this.boundingBox.setFromBufferAttribute( position );

			// process morph attributes if present

			if ( morphAttributesPosition ) {

				for ( let i = 0, il = morphAttributesPosition.length; i < il; i ++ ) {

					const morphAttribute = morphAttributesPosition[ i ];
					_box.setFromBufferAttribute( morphAttribute );

					if ( this.morphTargetsRelative ) {

						_vector.addVectors( this.boundingBox.min, _box.min );
						this.boundingBox.expandByPoint( _vector );

						_vector.addVectors( this.boundingBox.max, _box.max );
						this.boundingBox.expandByPoint( _vector );

					} else {

						this.boundingBox.expandByPoint( _box.min );
						this.boundingBox.expandByPoint( _box.max );

					}

				}

			}

		} else {

			this.boundingBox.makeEmpty();

		}

		if ( isNaN( this.boundingBox.min.x ) || isNaN( this.boundingBox.min.y ) || isNaN( this.boundingBox.min.z ) ) {

			console.error( 'THREE.BufferGeometry.computeBoundingBox(): Computed min/max have NaN values. The "position" attribute is likely to have NaN values.', this );

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

		const position = this.attributes.position;
		const morphAttributesPosition = this.morphAttributes.position;

		if ( position && position.isGLBufferAttribute ) {

			console.error( 'THREE.BufferGeometry.computeBoundingSphere(): GLBufferAttribute requires a manual bounding sphere.', this );

			this.boundingSphere.set( new Vector3(), Infinity );

			return;

		}

		if ( position ) {

			// first, find the center of the bounding sphere

			const center = this.boundingSphere.center;

			_box.setFromBufferAttribute( position );

			// process morph attributes if present

			if ( morphAttributesPosition ) {

				for ( let i = 0, il = morphAttributesPosition.length; i < il; i ++ ) {

					const morphAttribute = morphAttributesPosition[ i ];
					_boxMorphTargets.setFromBufferAttribute( morphAttribute );

					if ( this.morphTargetsRelative ) {

						_vector.addVectors( _box.min, _boxMorphTargets.min );
						_box.expandByPoint( _vector );

						_vector.addVectors( _box.max, _boxMorphTargets.max );
						_box.expandByPoint( _vector );

					} else {

						_box.expandByPoint( _boxMorphTargets.min );
						_box.expandByPoint( _boxMorphTargets.max );

					}

				}

			}

			_box.getCenter( center );

			// second, try to find a boundingSphere with a radius smaller than the
			// boundingSphere of the boundingBox: sqrt(3) smaller in the best case

			let maxRadiusSq = 0;

			for ( let i = 0, il = position.count; i < il; i ++ ) {

				_vector.fromBufferAttribute( position, i );

				maxRadiusSq = Math.max( maxRadiusSq, center.distanceToSquared( _vector ) );

			}

			// process morph attributes if present

			if ( morphAttributesPosition ) {

				for ( let i = 0, il = morphAttributesPosition.length; i < il; i ++ ) {

					const morphAttribute = morphAttributesPosition[ i ];
					const morphTargetsRelative = this.morphTargetsRelative;

					for ( let j = 0, jl = morphAttribute.count; j < jl; j ++ ) {

						_vector.fromBufferAttribute( morphAttribute, j );

						if ( morphTargetsRelative ) {

							_offset.fromBufferAttribute( position, j );
							_vector.add( _offset );

						}

						maxRadiusSq = Math.max( maxRadiusSq, center.distanceToSquared( _vector ) );

					}

				}

			}

			this.boundingSphere.radius = Math.sqrt( maxRadiusSq );

			if ( isNaN( this.boundingSphere.radius ) ) {

				console.error( 'THREE.BufferGeometry.computeBoundingSphere(): Computed radius is NaN. The "position" attribute is likely to have NaN values.', this );

			}

		}

	}
```
</details>

##### `computeTangents(): void`

<details><summary>Code</summary>

```ts
computeTangents() {

		const index = this.index;
		const attributes = this.attributes;

		// based on http://www.terathon.com/code/tangent.html
		// (per vertex tangents)

		if ( index === null ||
			 attributes.position === undefined ||
			 attributes.normal === undefined ||
			 attributes.uv === undefined ) {

			console.error( 'THREE.BufferGeometry: .computeTangents() failed. Missing required attributes (index, position, normal or uv)' );
			return;

		}

		const positionAttribute = attributes.position;
		const normalAttribute = attributes.normal;
		const uvAttribute = attributes.uv;

		if ( this.hasAttribute( 'tangent' ) === false ) {

			this.setAttribute( 'tangent', new BufferAttribute( new Float32Array( 4 * positionAttribute.count ), 4 ) );

		}

		const tangentAttribute = this.getAttribute( 'tangent' );

		const tan1 = [], tan2 = [];

		for ( let i = 0; i < positionAttribute.count; i ++ ) {

			tan1[ i ] = new Vector3();
			tan2[ i ] = new Vector3();

		}

		const vA = new Vector3(),
			vB = new Vector3(),
			vC = new Vector3(),

			uvA = new Vector2(),
			uvB = new Vector2(),
			uvC = new Vector2(),

			sdir = new Vector3(),
			tdir = new Vector3();

		function handleTriangle( a, b, c ) {

			vA.fromBufferAttribute( positionAttribute, a );
			vB.fromBufferAttribute( positionAttribute, b );
			vC.fromBufferAttribute( positionAttribute, c );

			uvA.fromBufferAttribute( uvAttribute, a );
			uvB.fromBufferAttribute( uvAttribute, b );
			uvC.fromBufferAttribute( uvAttribute, c );

			vB.sub( vA );
			vC.sub( vA );

			uvB.sub( uvA );
			uvC.sub( uvA );

			const r = 1.0 / ( uvB.x * uvC.y - uvC.x * uvB.y );

			// silently ignore degenerate uv triangles having coincident or colinear vertices

			if ( ! isFinite( r ) ) return;

			sdir.copy( vB ).multiplyScalar( uvC.y ).addScaledVector( vC, - uvB.y ).multiplyScalar( r );
			tdir.copy( vC ).multiplyScalar( uvB.x ).addScaledVector( vB, - uvC.x ).multiplyScalar( r );

			tan1[ a ].add( sdir );
			tan1[ b ].add( sdir );
			tan1[ c ].add( sdir );

			tan2[ a ].add( tdir );
			tan2[ b ].add( tdir );
			tan2[ c ].add( tdir );

		}

		let groups = this.groups;

		if ( groups.length === 0 ) {

			groups = [ {
				start: 0,
				count: index.count
			} ];

		}

		for ( let i = 0, il = groups.length; i < il; ++ i ) {

			const group = groups[ i ];

			const start = group.start;
			const count = group.count;

			for ( let j = start, jl = start + count; j < jl; j += 3 ) {

				handleTriangle(
					index.getX( j + 0 ),
					index.getX( j + 1 ),
					index.getX( j + 2 )
				);

			}

		}

		const tmp = new Vector3(), tmp2 = new Vector3();
		const n = new Vector3(), n2 = new Vector3();

		function handleVertex( v ) {

			n.fromBufferAttribute( normalAttribute, v );
			n2.copy( n );

			const t = tan1[ v ];

			// Gram-Schmidt orthogonalize

			tmp.copy( t );
			tmp.sub( n.multiplyScalar( n.dot( t ) ) ).normalize();

			// Calculate handedness

			tmp2.crossVectors( n2, t );
			const test = tmp2.dot( tan2[ v ] );
			const w = ( test < 0.0 ) ? - 1.0 : 1.0;

			tangentAttribute.setXYZW( v, tmp.x, tmp.y, tmp.z, w );

		}

		for ( let i = 0, il = groups.length; i < il; ++ i ) {

			const group = groups[ i ];

			const start = group.start;
			const count = group.count;

			for ( let j = start, jl = start + count; j < jl; j += 3 ) {

				handleVertex( index.getX( j + 0 ) );
				handleVertex( index.getX( j + 1 ) );
				handleVertex( index.getX( j + 2 ) );

			}

		}

	}
```
</details>

##### `computeVertexNormals(): void`

<details><summary>Code</summary>

```ts
computeVertexNormals() {

		const index = this.index;
		const positionAttribute = this.getAttribute( 'position' );

		if ( positionAttribute !== undefined ) {

			let normalAttribute = this.getAttribute( 'normal' );

			if ( normalAttribute === undefined ) {

				normalAttribute = new BufferAttribute( new Float32Array( positionAttribute.count * 3 ), 3 );
				this.setAttribute( 'normal', normalAttribute );

			} else {

				// reset existing normals to zero

				for ( let i = 0, il = normalAttribute.count; i < il; i ++ ) {

					normalAttribute.setXYZ( i, 0, 0, 0 );

				}

			}

			const pA = new Vector3(), pB = new Vector3(), pC = new Vector3();
			const nA = new Vector3(), nB = new Vector3(), nC = new Vector3();
			const cb = new Vector3(), ab = new Vector3();

			// indexed elements

			if ( index ) {

				for ( let i = 0, il = index.count; i < il; i += 3 ) {

					const vA = index.getX( i + 0 );
					const vB = index.getX( i + 1 );
					const vC = index.getX( i + 2 );

					pA.fromBufferAttribute( positionAttribute, vA );
					pB.fromBufferAttribute( positionAttribute, vB );
					pC.fromBufferAttribute( positionAttribute, vC );

					cb.subVectors( pC, pB );
					ab.subVectors( pA, pB );
					cb.cross( ab );

					nA.fromBufferAttribute( normalAttribute, vA );
					nB.fromBufferAttribute( normalAttribute, vB );
					nC.fromBufferAttribute( normalAttribute, vC );

					nA.add( cb );
					nB.add( cb );
					nC.add( cb );

					normalAttribute.setXYZ( vA, nA.x, nA.y, nA.z );
					normalAttribute.setXYZ( vB, nB.x, nB.y, nB.z );
					normalAttribute.setXYZ( vC, nC.x, nC.y, nC.z );

				}

			} else {

				// non-indexed elements (unconnected triangle soup)

				for ( let i = 0, il = positionAttribute.count; i < il; i += 3 ) {

					pA.fromBufferAttribute( positionAttribute, i + 0 );
					pB.fromBufferAttribute( positionAttribute, i + 1 );
					pC.fromBufferAttribute( positionAttribute, i + 2 );

					cb.subVectors( pC, pB );
					ab.subVectors( pA, pB );
					cb.cross( ab );

					normalAttribute.setXYZ( i + 0, cb.x, cb.y, cb.z );
					normalAttribute.setXYZ( i + 1, cb.x, cb.y, cb.z );
					normalAttribute.setXYZ( i + 2, cb.x, cb.y, cb.z );

				}

			}

			this.normalizeNormals();

			normalAttribute.needsUpdate = true;

		}

	}
```
</details>

##### `normalizeNormals(): void`

<details><summary>Code</summary>

```ts
normalizeNormals() {

		const normals = this.attributes.normal;

		for ( let i = 0, il = normals.count; i < il; i ++ ) {

			_vector.fromBufferAttribute( normals, i );

			_vector.normalize();

			normals.setXYZ( i, _vector.x, _vector.y, _vector.z );

		}

	}
```
</details>

##### `toNonIndexed(): BufferGeometry`

<details><summary>Code</summary>

```ts
toNonIndexed() {

		function convertBufferAttribute( attribute, indices ) {

			const array = attribute.array;
			const itemSize = attribute.itemSize;
			const normalized = attribute.normalized;

			const array2 = new array.constructor( indices.length * itemSize );

			let index = 0, index2 = 0;

			for ( let i = 0, l = indices.length; i < l; i ++ ) {

				if ( attribute.isInterleavedBufferAttribute ) {

					index = indices[ i ] * attribute.data.stride + attribute.offset;

				} else {

					index = indices[ i ] * itemSize;

				}

				for ( let j = 0; j < itemSize; j ++ ) {

					array2[ index2 ++ ] = array[ index ++ ];

				}

			}

			return new BufferAttribute( array2, itemSize, normalized );

		}

		//

		if ( this.index === null ) {

			console.warn( 'THREE.BufferGeometry.toNonIndexed(): BufferGeometry is already non-indexed.' );
			return this;

		}

		const geometry2 = new BufferGeometry();

		const indices = this.index.array;
		const attributes = this.attributes;

		// attributes

		for ( const name in attributes ) {

			const attribute = attributes[ name ];

			const newAttribute = convertBufferAttribute( attribute, indices );

			geometry2.setAttribute( name, newAttribute );

		}

		// morph attributes

		const morphAttributes = this.morphAttributes;

		for ( const name in morphAttributes ) {

			const morphArray = [];
			const morphAttribute = morphAttributes[ name ]; // morphAttribute: array of Float32BufferAttributes

			for ( let i = 0, il = morphAttribute.length; i < il; i ++ ) {

				const attribute = morphAttribute[ i ];

				const newAttribute = convertBufferAttribute( attribute, indices );

				morphArray.push( newAttribute );

			}

			geometry2.morphAttributes[ name ] = morphArray;

		}

		geometry2.morphTargetsRelative = this.morphTargetsRelative;

		// groups

		const groups = this.groups;

		for ( let i = 0, l = groups.length; i < l; i ++ ) {

			const group = groups[ i ];
			geometry2.addGroup( group.start, group.count, group.materialIndex );

		}

		return geometry2;

	}
```
</details>

##### `toJSON(): any`

<details><summary>Code</summary>

```ts
toJSON() {

		const data = {
			metadata: {
				version: 4.7,
				type: 'BufferGeometry',
				generator: 'BufferGeometry.toJSON'
			}
		};

		// standard BufferGeometry serialization

		data.uuid = this.uuid;
		data.type = this.type;
		if ( this.name !== '' ) data.name = this.name;
		if ( Object.keys( this.userData ).length > 0 ) data.userData = this.userData;

		if ( this.parameters !== undefined ) {

			const parameters = this.parameters;

			for ( const key in parameters ) {

				if ( parameters[ key ] !== undefined ) data[ key ] = parameters[ key ];

			}

			return data;

		}

		// for simplicity the code assumes attributes are not shared across geometries, see #15811

		data.data = { attributes: {} };

		const index = this.index;

		if ( index !== null ) {

			data.data.index = {
				type: index.array.constructor.name,
				array: Array.prototype.slice.call( index.array )
			};

		}

		const attributes = this.attributes;

		for ( const key in attributes ) {

			const attribute = attributes[ key ];

			data.data.attributes[ key ] = attribute.toJSON( data.data );

		}

		const morphAttributes = {};
		let hasMorphAttributes = false;

		for ( const key in this.morphAttributes ) {

			const attributeArray = this.morphAttributes[ key ];

			const array = [];

			for ( let i = 0, il = attributeArray.length; i < il; i ++ ) {

				const attribute = attributeArray[ i ];

				array.push( attribute.toJSON( data.data ) );

			}

			if ( array.length > 0 ) {

				morphAttributes[ key ] = array;

				hasMorphAttributes = true;

			}

		}

		if ( hasMorphAttributes ) {

			data.data.morphAttributes = morphAttributes;
			data.data.morphTargetsRelative = this.morphTargetsRelative;

		}

		const groups = this.groups;

		if ( groups.length > 0 ) {

			data.data.groups = JSON.parse( JSON.stringify( groups ) );

		}

		const boundingSphere = this.boundingSphere;

		if ( boundingSphere !== null ) {

			data.data.boundingSphere = boundingSphere.toJSON();

		}

		return data;

	}
```
</details>

##### `clone(): BufferGeometry`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor().copy( this );

	}
```
</details>

##### `copy(source: BufferGeometry): BufferGeometry`

<details><summary>Code</summary>

```ts
copy( source ) {

		// reset

		this.index = null;
		this.attributes = {};
		this.morphAttributes = {};
		this.groups = [];
		this.boundingBox = null;
		this.boundingSphere = null;

		// used for storing cloned, shared data

		const data = {};

		// name

		this.name = source.name;

		// index

		const index = source.index;

		if ( index !== null ) {

			this.setIndex( index.clone() );

		}

		// attributes

		const attributes = source.attributes;

		for ( const name in attributes ) {

			const attribute = attributes[ name ];
			this.setAttribute( name, attribute.clone( data ) );

		}

		// morph attributes

		const morphAttributes = source.morphAttributes;

		for ( const name in morphAttributes ) {

			const array = [];
			const morphAttribute = morphAttributes[ name ]; // morphAttribute: array of Float32BufferAttributes

			for ( let i = 0, l = morphAttribute.length; i < l; i ++ ) {

				array.push( morphAttribute[ i ].clone( data ) );

			}

			this.morphAttributes[ name ] = array;

		}

		this.morphTargetsRelative = source.morphTargetsRelative;

		// groups

		const groups = source.groups;

		for ( let i = 0, l = groups.length; i < l; i ++ ) {

			const group = groups[ i ];
			this.addGroup( group.start, group.count, group.materialIndex );

		}

		// bounding box

		const boundingBox = source.boundingBox;

		if ( boundingBox !== null ) {

			this.boundingBox = boundingBox.clone();

		}

		// bounding sphere

		const boundingSphere = source.boundingSphere;

		if ( boundingSphere !== null ) {

			this.boundingSphere = boundingSphere.clone();

		}

		// draw range

		this.drawRange.start = source.drawRange.start;
		this.drawRange.count = source.drawRange.count;

		// user data

		this.userData = source.userData;

		return this;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.dispatchEvent( { type: 'dispose' } );

	}
```
</details>


---