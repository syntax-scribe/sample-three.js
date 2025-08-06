[⬅️ Back to Table of Contents](../../index.md)

# 📄 `BufferAttribute.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 39 |
| 🧱 Classes | 10 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 9 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/core/BufferAttribute.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `../math/Vector3.js` |
| `Vector2` | `../math/Vector2.js` |
| `denormalize` | `../math/MathUtils.js` |
| `normalize` | `../math/MathUtils.js` |
| `StaticDrawUsage` | `../constants.js` |
| `FloatType` | `../constants.js` |
| `fromHalfFloat` | `../extras/DataUtils.js` |
| `toHalfFloat` | `../extras/DataUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_vector` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `_vector2` | `Vector2` | let/var | `new Vector2()` | ✗ |
| `_id` | `number` | let/var | `0` | ✗ |
| `value` | `TypedArray` | let/var | `this.array[ index * this.itemSize + component ]` | ✗ |
| `x` | `TypedArray` | let/var | `this.array[ index * this.itemSize ]` | ✗ |
| `y` | `TypedArray` | let/var | `this.array[ index * this.itemSize + 1 ]` | ✗ |
| `z` | `TypedArray` | let/var | `this.array[ index * this.itemSize + 2 ]` | ✗ |
| `w` | `TypedArray` | let/var | `this.array[ index * this.itemSize + 3 ]` | ✗ |
| `data` | `{ itemSize: number; type: any; array:...` | let/var | `{ itemSize: this.itemSize, type: this.array.constructor.name, array: Array.fr...` | ✗ |


---

## Functions

### `BufferAttribute.onUploadCallback(): void`

**JSDoc:**
```typescript
/**
	 * A callback function that is executed after the renderer has transferred the attribute
	 * array data to the GPU.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
onUploadCallback() {}
```
</details>

### `BufferAttribute.setUsage(value: any): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the usage of this buffer attribute.
	 *
	 * @param {(StaticDrawUsage|DynamicDrawUsage|StreamDrawUsage|StaticReadUsage|DynamicReadUsage|StreamReadUsage|StaticCopyUsage|DynamicCopyUsage|StreamCopyUsage)} value - The usage to set.
	 * @return {BufferAttribute} A reference to this buffer attribute.
	 */
```

**Parameters:**

- **`value`** `any`

**Returns:** `BufferAttribute`

<details><summary>Code</summary>

```typescript
setUsage( value ) {

		this.usage = value;

		return this;

	}
```
</details>

### `BufferAttribute.addUpdateRange(start: number, count: number): void`

**JSDoc:**
```typescript
/**
	 * Adds a range of data in the data array to be updated on the GPU.
	 *
	 * @param {number} start - Position at which to start update.
	 * @param {number} count - The number of components to update.
	 */
```

**Parameters:**

- **`start`** `number`
- **`count`** `number`

**Returns:** `void`

**Calls:**

- `this.updateRanges.push`

<details><summary>Code</summary>

```typescript
addUpdateRange( start, count ) {

		this.updateRanges.push( { start, count } );

	}
```
</details>

### `BufferAttribute.clearUpdateRanges(): void`

**JSDoc:**
```typescript
/**
	 * Clears the update ranges.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
clearUpdateRanges() {

		this.updateRanges.length = 0;

	}
```
</details>

### `BufferAttribute.copy(source: BufferAttribute): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given buffer attribute to this instance.
	 *
	 * @param {BufferAttribute} source - The buffer attribute to copy.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`source`** `BufferAttribute`

**Returns:** `BufferAttribute`

<details><summary>Code</summary>

```typescript
copy( source ) {

		this.name = source.name;
		this.array = new source.array.constructor( source.array );
		this.itemSize = source.itemSize;
		this.count = source.count;
		this.normalized = source.normalized;

		this.usage = source.usage;
		this.gpuType = source.gpuType;

		return this;

	}
```
</details>

### `BufferAttribute.copyAt(index1: number, attribute: BufferAttribute, index2: number): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Copies a vector from the given buffer attribute to this one. The start
	 * and destination position in the attribute buffers are represented by the
	 * given indices.
	 *
	 * @param {number} index1 - The destination index into this buffer attribute.
	 * @param {BufferAttribute} attribute - The buffer attribute to copy from.
	 * @param {number} index2 - The source index into the given buffer attribute.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`index1`** `number`
- **`attribute`** `BufferAttribute`
- **`index2`** `number`

**Returns:** `BufferAttribute`

<details><summary>Code</summary>

```typescript
copyAt( index1, attribute, index2 ) {

		index1 *= this.itemSize;
		index2 *= attribute.itemSize;

		for ( let i = 0, l = this.itemSize; i < l; i ++ ) {

			this.array[ index1 + i ] = attribute.array[ index2 + i ];

		}

		return this;

	}
```
</details>

### `BufferAttribute.copyArray(array: any): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Copies the given array data into this buffer attribute.
	 *
	 * @param {(TypedArray|Array)} array - The array to copy.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`array`** `any`

**Returns:** `BufferAttribute`

**Calls:**

- `this.array.set`

<details><summary>Code</summary>

```typescript
copyArray( array ) {

		this.array.set( array );

		return this;

	}
```
</details>

### `BufferAttribute.applyMatrix3(m: Matrix3): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Applies the given 3x3 matrix to the given attribute. Works with
	 * item size `2` and `3`.
	 *
	 * @param {Matrix3} m - The matrix to apply.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`m`** `Matrix3`

**Returns:** `BufferAttribute`

**Calls:**

- `_vector2.fromBufferAttribute`
- `_vector2.applyMatrix3`
- `this.setXY`
- `_vector.fromBufferAttribute`
- `_vector.applyMatrix3`
- `this.setXYZ`

<details><summary>Code</summary>

```typescript
applyMatrix3( m ) {

		if ( this.itemSize === 2 ) {

			for ( let i = 0, l = this.count; i < l; i ++ ) {

				_vector2.fromBufferAttribute( this, i );
				_vector2.applyMatrix3( m );

				this.setXY( i, _vector2.x, _vector2.y );

			}

		} else if ( this.itemSize === 3 ) {

			for ( let i = 0, l = this.count; i < l; i ++ ) {

				_vector.fromBufferAttribute( this, i );
				_vector.applyMatrix3( m );

				this.setXYZ( i, _vector.x, _vector.y, _vector.z );

			}

		}

		return this;

	}
```
</details>

### `BufferAttribute.applyMatrix4(m: Matrix4): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Applies the given 4x4 matrix to the given attribute. Only works with
	 * item size `3`.
	 *
	 * @param {Matrix4} m - The matrix to apply.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`m`** `Matrix4`

**Returns:** `BufferAttribute`

**Calls:**

- `_vector.fromBufferAttribute`
- `_vector.applyMatrix4`
- `this.setXYZ`

<details><summary>Code</summary>

```typescript
applyMatrix4( m ) {

		for ( let i = 0, l = this.count; i < l; i ++ ) {

			_vector.fromBufferAttribute( this, i );

			_vector.applyMatrix4( m );

			this.setXYZ( i, _vector.x, _vector.y, _vector.z );

		}

		return this;

	}
```
</details>

### `BufferAttribute.applyNormalMatrix(m: Matrix3): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Applies the given 3x3 normal matrix to the given attribute. Only works with
	 * item size `3`.
	 *
	 * @param {Matrix3} m - The normal matrix to apply.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`m`** `Matrix3`

**Returns:** `BufferAttribute`

**Calls:**

- `_vector.fromBufferAttribute`
- `_vector.applyNormalMatrix`
- `this.setXYZ`

<details><summary>Code</summary>

```typescript
applyNormalMatrix( m ) {

		for ( let i = 0, l = this.count; i < l; i ++ ) {

			_vector.fromBufferAttribute( this, i );

			_vector.applyNormalMatrix( m );

			this.setXYZ( i, _vector.x, _vector.y, _vector.z );

		}

		return this;

	}
```
</details>

### `BufferAttribute.transformDirection(m: Matrix4): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Applies the given 4x4 matrix to the given attribute. Only works with
	 * item size `3` and with direction vectors.
	 *
	 * @param {Matrix4} m - The matrix to apply.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`m`** `Matrix4`

**Returns:** `BufferAttribute`

**Calls:**

- `_vector.fromBufferAttribute`
- `_vector.transformDirection`
- `this.setXYZ`

<details><summary>Code</summary>

```typescript
transformDirection( m ) {

		for ( let i = 0, l = this.count; i < l; i ++ ) {

			_vector.fromBufferAttribute( this, i );

			_vector.transformDirection( m );

			this.setXYZ( i, _vector.x, _vector.y, _vector.z );

		}

		return this;

	}
```
</details>

### `BufferAttribute.set(value: any, offset: number): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the given array data in the buffer attribute.
	 *
	 * @param {(TypedArray|Array)} value - The array data to set.
	 * @param {number} [offset=0] - The offset in this buffer attribute's array.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`value`** `any`
- **`offset`** `number`

**Returns:** `BufferAttribute`

**Calls:**

- `this.array.set`

**Internal Comments:**
```
// Matching BufferAttribute constructor, do not normalize the array. (x5)
```

<details><summary>Code</summary>

```typescript
set( value, offset = 0 ) {

		// Matching BufferAttribute constructor, do not normalize the array.
		this.array.set( value, offset );

		return this;

	}
```
</details>

### `BufferAttribute.getComponent(index: number, component: number): number`

**JSDoc:**
```typescript
/**
	 * Returns the given component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} component - The component index.
	 * @return {number} The returned value.
	 */
```

**Parameters:**

- **`index`** `number`
- **`component`** `number`

**Returns:** `number`

**Calls:**

- `denormalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
getComponent( index, component ) {

		let value = this.array[ index * this.itemSize + component ];

		if ( this.normalized ) value = denormalize( value, this.array );

		return value;

	}
```
</details>

### `BufferAttribute.setComponent(index: number, component: number, value: number): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the given value to the given component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} component - The component index.
	 * @param {number} value - The value to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`index`** `number`
- **`component`** `number`
- **`value`** `number`

**Returns:** `BufferAttribute`

**Calls:**

- `normalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
setComponent( index, component, value ) {

		if ( this.normalized ) value = normalize( value, this.array );

		this.array[ index * this.itemSize + component ] = value;

		return this;

	}
```
</details>

### `BufferAttribute.getX(index: number): number`

**JSDoc:**
```typescript
/**
	 * Returns the x component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @return {number} The x component.
	 */
```

**Parameters:**

- **`index`** `number`

**Returns:** `number`

**Calls:**

- `denormalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
getX( index ) {

		let x = this.array[ index * this.itemSize ];

		if ( this.normalized ) x = denormalize( x, this.array );

		return x;

	}
```
</details>

### `BufferAttribute.setX(index: number, x: number): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the x component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} x - The value to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`index`** `number`
- **`x`** `number`

**Returns:** `BufferAttribute`

**Calls:**

- `normalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
setX( index, x ) {

		if ( this.normalized ) x = normalize( x, this.array );

		this.array[ index * this.itemSize ] = x;

		return this;

	}
```
</details>

### `BufferAttribute.getY(index: number): number`

**JSDoc:**
```typescript
/**
	 * Returns the y component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @return {number} The y component.
	 */
```

**Parameters:**

- **`index`** `number`

**Returns:** `number`

**Calls:**

- `denormalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
getY( index ) {

		let y = this.array[ index * this.itemSize + 1 ];

		if ( this.normalized ) y = denormalize( y, this.array );

		return y;

	}
```
</details>

### `BufferAttribute.setY(index: number, y: number): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the y component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} y - The value to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`index`** `number`
- **`y`** `number`

**Returns:** `BufferAttribute`

**Calls:**

- `normalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
setY( index, y ) {

		if ( this.normalized ) y = normalize( y, this.array );

		this.array[ index * this.itemSize + 1 ] = y;

		return this;

	}
```
</details>

### `BufferAttribute.getZ(index: number): number`

**JSDoc:**
```typescript
/**
	 * Returns the z component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @return {number} The z component.
	 */
```

**Parameters:**

- **`index`** `number`

**Returns:** `number`

**Calls:**

- `denormalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
getZ( index ) {

		let z = this.array[ index * this.itemSize + 2 ];

		if ( this.normalized ) z = denormalize( z, this.array );

		return z;

	}
```
</details>

### `BufferAttribute.setZ(index: number, z: number): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the z component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} z - The value to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`index`** `number`
- **`z`** `number`

**Returns:** `BufferAttribute`

**Calls:**

- `normalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
setZ( index, z ) {

		if ( this.normalized ) z = normalize( z, this.array );

		this.array[ index * this.itemSize + 2 ] = z;

		return this;

	}
```
</details>

### `BufferAttribute.getW(index: number): number`

**JSDoc:**
```typescript
/**
	 * Returns the w component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @return {number} The w component.
	 */
```

**Parameters:**

- **`index`** `number`

**Returns:** `number`

**Calls:**

- `denormalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
getW( index ) {

		let w = this.array[ index * this.itemSize + 3 ];

		if ( this.normalized ) w = denormalize( w, this.array );

		return w;

	}
```
</details>

### `BufferAttribute.setW(index: number, w: number): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the w component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} w - The value to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`index`** `number`
- **`w`** `number`

**Returns:** `BufferAttribute`

**Calls:**

- `normalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
setW( index, w ) {

		if ( this.normalized ) w = normalize( w, this.array );

		this.array[ index * this.itemSize + 3 ] = w;

		return this;

	}
```
</details>

### `BufferAttribute.setXY(index: number, x: number, y: number): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the x and y component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} x - The value for the x component to set.
	 * @param {number} y - The value for the y component to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`index`** `number`
- **`x`** `number`
- **`y`** `number`

**Returns:** `BufferAttribute`

**Calls:**

- `normalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
setXY( index, x, y ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );

		}

		this.array[ index + 0 ] = x;
		this.array[ index + 1 ] = y;

		return this;

	}
```
</details>

### `BufferAttribute.setXYZ(index: number, x: number, y: number, z: number): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the x, y and z component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} x - The value for the x component to set.
	 * @param {number} y - The value for the y component to set.
	 * @param {number} z - The value for the z component to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`index`** `number`
- **`x`** `number`
- **`y`** `number`
- **`z`** `number`

**Returns:** `BufferAttribute`

**Calls:**

- `normalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
setXYZ( index, x, y, z ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );

		}

		this.array[ index + 0 ] = x;
		this.array[ index + 1 ] = y;
		this.array[ index + 2 ] = z;

		return this;

	}
```
</details>

### `BufferAttribute.setXYZW(index: number, x: number, y: number, z: number, w: number): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the x, y, z and w component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} x - The value for the x component to set.
	 * @param {number} y - The value for the y component to set.
	 * @param {number} z - The value for the z component to set.
	 * @param {number} w - The value for the w component to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`index`** `number`
- **`x`** `number`
- **`y`** `number`
- **`z`** `number`
- **`w`** `number`

**Returns:** `BufferAttribute`

**Calls:**

- `normalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
setXYZW( index, x, y, z, w ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );
			w = normalize( w, this.array );

		}

		this.array[ index + 0 ] = x;
		this.array[ index + 1 ] = y;
		this.array[ index + 2 ] = z;
		this.array[ index + 3 ] = w;

		return this;

	}
```
</details>

### `BufferAttribute.onUpload(callback: Function): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the given callback function that is executed after the Renderer has transferred
	 * the attribute array data to the GPU. Can be used to perform clean-up operations after
	 * the upload when attribute data are not needed anymore on the CPU side.
	 *
	 * @param {Function} callback - The `onUpload()` callback.
	 * @return {BufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`callback`** `Function`

**Returns:** `BufferAttribute`

<details><summary>Code</summary>

```typescript
onUpload( callback ) {

		this.onUploadCallback = callback;

		return this;

	}
```
</details>

### `BufferAttribute.clone(): BufferAttribute`

**JSDoc:**
```typescript
/**
	 * Returns a new buffer attribute with copied values from this instance.
	 *
	 * @return {BufferAttribute} A clone of this instance.
	 */
```

**Returns:** `BufferAttribute`

**Calls:**

- `new this.constructor( this.array, this.itemSize ).copy`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor( this.array, this.itemSize ).copy( this );

	}
```
</details>

### `BufferAttribute.toJSON(): any`

**JSDoc:**
```typescript
/**
	 * Serializes the buffer attribute into JSON.
	 *
	 * @return {Object} A JSON object representing the serialized buffer attribute.
	 */
```

**Returns:** `any`

**Calls:**

- `Array.from`

<details><summary>Code</summary>

```typescript
toJSON() {

		const data = {
			itemSize: this.itemSize,
			type: this.array.constructor.name,
			array: Array.from( this.array ),
			normalized: this.normalized
		};

		if ( this.name !== '' ) data.name = this.name;
		if ( this.usage !== StaticDrawUsage ) data.usage = this.usage;

		return data;

	}
```
</details>

### `Float16BufferAttribute.getX(index: any): number`

**Parameters:**

- **`index`** `any`

**Returns:** `number`

**Calls:**

- `fromHalfFloat (from ../extras/DataUtils.js)`
- `denormalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
getX( index ) {

		let x = fromHalfFloat( this.array[ index * this.itemSize ] );

		if ( this.normalized ) x = denormalize( x, this.array );

		return x;

	}
```
</details>

### `Float16BufferAttribute.setX(index: any, x: any): this`

**Parameters:**

- **`index`** `any`
- **`x`** `any`

**Returns:** `this`

**Calls:**

- `normalize (from ../math/MathUtils.js)`
- `toHalfFloat (from ../extras/DataUtils.js)`

<details><summary>Code</summary>

```typescript
setX( index, x ) {

		if ( this.normalized ) x = normalize( x, this.array );

		this.array[ index * this.itemSize ] = toHalfFloat( x );

		return this;

	}
```
</details>

### `Float16BufferAttribute.getY(index: any): number`

**Parameters:**

- **`index`** `any`

**Returns:** `number`

**Calls:**

- `fromHalfFloat (from ../extras/DataUtils.js)`
- `denormalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
getY( index ) {

		let y = fromHalfFloat( this.array[ index * this.itemSize + 1 ] );

		if ( this.normalized ) y = denormalize( y, this.array );

		return y;

	}
```
</details>

### `Float16BufferAttribute.setY(index: any, y: any): this`

**Parameters:**

- **`index`** `any`
- **`y`** `any`

**Returns:** `this`

**Calls:**

- `normalize (from ../math/MathUtils.js)`
- `toHalfFloat (from ../extras/DataUtils.js)`

<details><summary>Code</summary>

```typescript
setY( index, y ) {

		if ( this.normalized ) y = normalize( y, this.array );

		this.array[ index * this.itemSize + 1 ] = toHalfFloat( y );

		return this;

	}
```
</details>

### `Float16BufferAttribute.getZ(index: any): number`

**Parameters:**

- **`index`** `any`

**Returns:** `number`

**Calls:**

- `fromHalfFloat (from ../extras/DataUtils.js)`
- `denormalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
getZ( index ) {

		let z = fromHalfFloat( this.array[ index * this.itemSize + 2 ] );

		if ( this.normalized ) z = denormalize( z, this.array );

		return z;

	}
```
</details>

### `Float16BufferAttribute.setZ(index: any, z: any): this`

**Parameters:**

- **`index`** `any`
- **`z`** `any`

**Returns:** `this`

**Calls:**

- `normalize (from ../math/MathUtils.js)`
- `toHalfFloat (from ../extras/DataUtils.js)`

<details><summary>Code</summary>

```typescript
setZ( index, z ) {

		if ( this.normalized ) z = normalize( z, this.array );

		this.array[ index * this.itemSize + 2 ] = toHalfFloat( z );

		return this;

	}
```
</details>

### `Float16BufferAttribute.getW(index: any): number`

**Parameters:**

- **`index`** `any`

**Returns:** `number`

**Calls:**

- `fromHalfFloat (from ../extras/DataUtils.js)`
- `denormalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
getW( index ) {

		let w = fromHalfFloat( this.array[ index * this.itemSize + 3 ] );

		if ( this.normalized ) w = denormalize( w, this.array );

		return w;

	}
```
</details>

### `Float16BufferAttribute.setW(index: any, w: any): this`

**Parameters:**

- **`index`** `any`
- **`w`** `any`

**Returns:** `this`

**Calls:**

- `normalize (from ../math/MathUtils.js)`
- `toHalfFloat (from ../extras/DataUtils.js)`

<details><summary>Code</summary>

```typescript
setW( index, w ) {

		if ( this.normalized ) w = normalize( w, this.array );

		this.array[ index * this.itemSize + 3 ] = toHalfFloat( w );

		return this;

	}
```
</details>

### `Float16BufferAttribute.setXY(index: any, x: any, y: any): this`

**Parameters:**

- **`index`** `any`
- **`x`** `any`
- **`y`** `any`

**Returns:** `this`

**Calls:**

- `normalize (from ../math/MathUtils.js)`
- `toHalfFloat (from ../extras/DataUtils.js)`

<details><summary>Code</summary>

```typescript
setXY( index, x, y ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );

		}

		this.array[ index + 0 ] = toHalfFloat( x );
		this.array[ index + 1 ] = toHalfFloat( y );

		return this;

	}
```
</details>

### `Float16BufferAttribute.setXYZ(index: any, x: any, y: any, z: any): this`

**Parameters:**

- **`index`** `any`
- **`x`** `any`
- **`y`** `any`
- **`z`** `any`

**Returns:** `this`

**Calls:**

- `normalize (from ../math/MathUtils.js)`
- `toHalfFloat (from ../extras/DataUtils.js)`

<details><summary>Code</summary>

```typescript
setXYZ( index, x, y, z ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );

		}

		this.array[ index + 0 ] = toHalfFloat( x );
		this.array[ index + 1 ] = toHalfFloat( y );
		this.array[ index + 2 ] = toHalfFloat( z );

		return this;

	}
```
</details>

### `Float16BufferAttribute.setXYZW(index: any, x: any, y: any, z: any, w: any): this`

**Parameters:**

- **`index`** `any`
- **`x`** `any`
- **`y`** `any`
- **`z`** `any`
- **`w`** `any`

**Returns:** `this`

**Calls:**

- `normalize (from ../math/MathUtils.js)`
- `toHalfFloat (from ../extras/DataUtils.js)`

<details><summary>Code</summary>

```typescript
setXYZW( index, x, y, z, w ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );
			w = normalize( w, this.array );

		}

		this.array[ index + 0 ] = toHalfFloat( x );
		this.array[ index + 1 ] = toHalfFloat( y );
		this.array[ index + 2 ] = toHalfFloat( z );
		this.array[ index + 3 ] = toHalfFloat( w );

		return this;

	}
```
</details>


---

## Classes

### `BufferAttribute`

<details><summary>Class Code</summary>

```ts
class BufferAttribute {

	/**
	 * Constructs a new buffer attribute.
	 *
	 * @param {TypedArray} array - The array holding the attribute data.
	 * @param {number} itemSize - The item size.
	 * @param {boolean} [normalized=false] - Whether the data are normalized or not.
	 */
	constructor( array, itemSize, normalized = false ) {

		if ( Array.isArray( array ) ) {

			throw new TypeError( 'THREE.BufferAttribute: array should be a Typed Array.' );

		}

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isBufferAttribute = true;

		/**
		 * The ID of the buffer attribute.
		 *
		 * @name BufferAttribute#id
		 * @type {number}
		 * @readonly
		 */
		Object.defineProperty( this, 'id', { value: _id ++ } );

		/**
		 * The name of the buffer attribute.
		 *
		 * @type {string}
		 */
		this.name = '';

		/**
		 * The array holding the attribute data. It should have `itemSize * numVertices`
		 * elements, where `numVertices` is the number of vertices in the associated geometry.
		 *
		 * @type {TypedArray}
		 */
		this.array = array;

		/**
		 * The number of values of the array that should be associated with a particular vertex.
		 * For instance, if this attribute is storing a 3-component vector (such as a position,
		 * normal, or color), then the value should be `3`.
		 *
		 * @type {number}
		 */
		this.itemSize = itemSize;

		/**
		 * Represents the number of items this buffer attribute stores. It is internally computed
		 * by dividing the `array` length by the `itemSize`.
		 *
		 * @type {number}
		 * @readonly
		 */
		this.count = array !== undefined ? array.length / itemSize : 0;

		/**
		 * Applies to integer data only. Indicates how the underlying data in the buffer maps to
		 * the values in the GLSL code. For instance, if `array` is an instance of `UInt16Array`,
		 * and `normalized` is `true`, the values `0 - +65535` in the array data will be mapped to
		 * `0.0f - +1.0f` in the GLSL attribute. If `normalized` is `false`, the values will be converted
		 * to floats unmodified, i.e. `65535` becomes `65535.0f`.
		 *
		 * @type {boolean}
		 */
		this.normalized = normalized;

		/**
		 * Defines the intended usage pattern of the data store for optimization purposes.
		 *
		 * Note: After the initial use of a buffer, its usage cannot be changed. Instead,
		 * instantiate a new one and set the desired usage before the next render.
		 *
		 * @type {(StaticDrawUsage|DynamicDrawUsage|StreamDrawUsage|StaticReadUsage|DynamicReadUsage|StreamReadUsage|StaticCopyUsage|DynamicCopyUsage|StreamCopyUsage)}
		 * @default StaticDrawUsage
		 */
		this.usage = StaticDrawUsage;

		/**
		 * This can be used to only update some components of stored vectors (for example, just the
		 * component related to color). Use the `addUpdateRange()` function to add ranges to this array.
		 *
		 * @type {Array<Object>}
		 */
		this.updateRanges = [];

		/**
		 * Configures the bound GPU type for use in shaders.
		 *
		 * Note: this only has an effect for integer arrays and is not configurable for float arrays.
		 * For lower precision float types, use `Float16BufferAttribute`.
		 *
		 * @type {(FloatType|IntType)}
		 * @default FloatType
		 */
		this.gpuType = FloatType;

		/**
		 * A version number, incremented every time the `needsUpdate` is set to `true`.
		 *
		 * @type {number}
		 */
		this.version = 0;

	}

	/**
	 * A callback function that is executed after the renderer has transferred the attribute
	 * array data to the GPU.
	 */
	onUploadCallback() {}

	/**
	 * Flag to indicate that this attribute has changed and should be re-sent to
	 * the GPU. Set this to `true` when you modify the value of the array.
	 *
	 * @type {number}
	 * @default false
	 * @param {boolean} value
	 */
	set needsUpdate( value ) {

		if ( value === true ) this.version ++;

	}

	/**
	 * Sets the usage of this buffer attribute.
	 *
	 * @param {(StaticDrawUsage|DynamicDrawUsage|StreamDrawUsage|StaticReadUsage|DynamicReadUsage|StreamReadUsage|StaticCopyUsage|DynamicCopyUsage|StreamCopyUsage)} value - The usage to set.
	 * @return {BufferAttribute} A reference to this buffer attribute.
	 */
	setUsage( value ) {

		this.usage = value;

		return this;

	}

	/**
	 * Adds a range of data in the data array to be updated on the GPU.
	 *
	 * @param {number} start - Position at which to start update.
	 * @param {number} count - The number of components to update.
	 */
	addUpdateRange( start, count ) {

		this.updateRanges.push( { start, count } );

	}

	/**
	 * Clears the update ranges.
	 */
	clearUpdateRanges() {

		this.updateRanges.length = 0;

	}

	/**
	 * Copies the values of the given buffer attribute to this instance.
	 *
	 * @param {BufferAttribute} source - The buffer attribute to copy.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	copy( source ) {

		this.name = source.name;
		this.array = new source.array.constructor( source.array );
		this.itemSize = source.itemSize;
		this.count = source.count;
		this.normalized = source.normalized;

		this.usage = source.usage;
		this.gpuType = source.gpuType;

		return this;

	}

	/**
	 * Copies a vector from the given buffer attribute to this one. The start
	 * and destination position in the attribute buffers are represented by the
	 * given indices.
	 *
	 * @param {number} index1 - The destination index into this buffer attribute.
	 * @param {BufferAttribute} attribute - The buffer attribute to copy from.
	 * @param {number} index2 - The source index into the given buffer attribute.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	copyAt( index1, attribute, index2 ) {

		index1 *= this.itemSize;
		index2 *= attribute.itemSize;

		for ( let i = 0, l = this.itemSize; i < l; i ++ ) {

			this.array[ index1 + i ] = attribute.array[ index2 + i ];

		}

		return this;

	}

	/**
	 * Copies the given array data into this buffer attribute.
	 *
	 * @param {(TypedArray|Array)} array - The array to copy.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	copyArray( array ) {

		this.array.set( array );

		return this;

	}

	/**
	 * Applies the given 3x3 matrix to the given attribute. Works with
	 * item size `2` and `3`.
	 *
	 * @param {Matrix3} m - The matrix to apply.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	applyMatrix3( m ) {

		if ( this.itemSize === 2 ) {

			for ( let i = 0, l = this.count; i < l; i ++ ) {

				_vector2.fromBufferAttribute( this, i );
				_vector2.applyMatrix3( m );

				this.setXY( i, _vector2.x, _vector2.y );

			}

		} else if ( this.itemSize === 3 ) {

			for ( let i = 0, l = this.count; i < l; i ++ ) {

				_vector.fromBufferAttribute( this, i );
				_vector.applyMatrix3( m );

				this.setXYZ( i, _vector.x, _vector.y, _vector.z );

			}

		}

		return this;

	}

	/**
	 * Applies the given 4x4 matrix to the given attribute. Only works with
	 * item size `3`.
	 *
	 * @param {Matrix4} m - The matrix to apply.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	applyMatrix4( m ) {

		for ( let i = 0, l = this.count; i < l; i ++ ) {

			_vector.fromBufferAttribute( this, i );

			_vector.applyMatrix4( m );

			this.setXYZ( i, _vector.x, _vector.y, _vector.z );

		}

		return this;

	}

	/**
	 * Applies the given 3x3 normal matrix to the given attribute. Only works with
	 * item size `3`.
	 *
	 * @param {Matrix3} m - The normal matrix to apply.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	applyNormalMatrix( m ) {

		for ( let i = 0, l = this.count; i < l; i ++ ) {

			_vector.fromBufferAttribute( this, i );

			_vector.applyNormalMatrix( m );

			this.setXYZ( i, _vector.x, _vector.y, _vector.z );

		}

		return this;

	}

	/**
	 * Applies the given 4x4 matrix to the given attribute. Only works with
	 * item size `3` and with direction vectors.
	 *
	 * @param {Matrix4} m - The matrix to apply.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	transformDirection( m ) {

		for ( let i = 0, l = this.count; i < l; i ++ ) {

			_vector.fromBufferAttribute( this, i );

			_vector.transformDirection( m );

			this.setXYZ( i, _vector.x, _vector.y, _vector.z );

		}

		return this;

	}

	/**
	 * Sets the given array data in the buffer attribute.
	 *
	 * @param {(TypedArray|Array)} value - The array data to set.
	 * @param {number} [offset=0] - The offset in this buffer attribute's array.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	set( value, offset = 0 ) {

		// Matching BufferAttribute constructor, do not normalize the array.
		this.array.set( value, offset );

		return this;

	}

	/**
	 * Returns the given component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} component - The component index.
	 * @return {number} The returned value.
	 */
	getComponent( index, component ) {

		let value = this.array[ index * this.itemSize + component ];

		if ( this.normalized ) value = denormalize( value, this.array );

		return value;

	}

	/**
	 * Sets the given value to the given component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} component - The component index.
	 * @param {number} value - The value to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	setComponent( index, component, value ) {

		if ( this.normalized ) value = normalize( value, this.array );

		this.array[ index * this.itemSize + component ] = value;

		return this;

	}

	/**
	 * Returns the x component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @return {number} The x component.
	 */
	getX( index ) {

		let x = this.array[ index * this.itemSize ];

		if ( this.normalized ) x = denormalize( x, this.array );

		return x;

	}

	/**
	 * Sets the x component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} x - The value to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	setX( index, x ) {

		if ( this.normalized ) x = normalize( x, this.array );

		this.array[ index * this.itemSize ] = x;

		return this;

	}

	/**
	 * Returns the y component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @return {number} The y component.
	 */
	getY( index ) {

		let y = this.array[ index * this.itemSize + 1 ];

		if ( this.normalized ) y = denormalize( y, this.array );

		return y;

	}

	/**
	 * Sets the y component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} y - The value to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	setY( index, y ) {

		if ( this.normalized ) y = normalize( y, this.array );

		this.array[ index * this.itemSize + 1 ] = y;

		return this;

	}

	/**
	 * Returns the z component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @return {number} The z component.
	 */
	getZ( index ) {

		let z = this.array[ index * this.itemSize + 2 ];

		if ( this.normalized ) z = denormalize( z, this.array );

		return z;

	}

	/**
	 * Sets the z component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} z - The value to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	setZ( index, z ) {

		if ( this.normalized ) z = normalize( z, this.array );

		this.array[ index * this.itemSize + 2 ] = z;

		return this;

	}

	/**
	 * Returns the w component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @return {number} The w component.
	 */
	getW( index ) {

		let w = this.array[ index * this.itemSize + 3 ];

		if ( this.normalized ) w = denormalize( w, this.array );

		return w;

	}

	/**
	 * Sets the w component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} w - The value to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	setW( index, w ) {

		if ( this.normalized ) w = normalize( w, this.array );

		this.array[ index * this.itemSize + 3 ] = w;

		return this;

	}

	/**
	 * Sets the x and y component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} x - The value for the x component to set.
	 * @param {number} y - The value for the y component to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	setXY( index, x, y ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );

		}

		this.array[ index + 0 ] = x;
		this.array[ index + 1 ] = y;

		return this;

	}

	/**
	 * Sets the x, y and z component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} x - The value for the x component to set.
	 * @param {number} y - The value for the y component to set.
	 * @param {number} z - The value for the z component to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	setXYZ( index, x, y, z ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );

		}

		this.array[ index + 0 ] = x;
		this.array[ index + 1 ] = y;
		this.array[ index + 2 ] = z;

		return this;

	}

	/**
	 * Sets the x, y, z and w component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} x - The value for the x component to set.
	 * @param {number} y - The value for the y component to set.
	 * @param {number} z - The value for the z component to set.
	 * @param {number} w - The value for the w component to set.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	setXYZW( index, x, y, z, w ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );
			w = normalize( w, this.array );

		}

		this.array[ index + 0 ] = x;
		this.array[ index + 1 ] = y;
		this.array[ index + 2 ] = z;
		this.array[ index + 3 ] = w;

		return this;

	}

	/**
	 * Sets the given callback function that is executed after the Renderer has transferred
	 * the attribute array data to the GPU. Can be used to perform clean-up operations after
	 * the upload when attribute data are not needed anymore on the CPU side.
	 *
	 * @param {Function} callback - The `onUpload()` callback.
	 * @return {BufferAttribute} A reference to this instance.
	 */
	onUpload( callback ) {

		this.onUploadCallback = callback;

		return this;

	}

	/**
	 * Returns a new buffer attribute with copied values from this instance.
	 *
	 * @return {BufferAttribute} A clone of this instance.
	 */
	clone() {

		return new this.constructor( this.array, this.itemSize ).copy( this );

	}

	/**
	 * Serializes the buffer attribute into JSON.
	 *
	 * @return {Object} A JSON object representing the serialized buffer attribute.
	 */
	toJSON() {

		const data = {
			itemSize: this.itemSize,
			type: this.array.constructor.name,
			array: Array.from( this.array ),
			normalized: this.normalized
		};

		if ( this.name !== '' ) data.name = this.name;
		if ( this.usage !== StaticDrawUsage ) data.usage = this.usage;

		return data;

	}

}
```
</details>

#### Methods

##### `onUploadCallback(): void`

<details><summary>Code</summary>

```ts
onUploadCallback() {}
```
</details>

##### `setUsage(value: any): BufferAttribute`

<details><summary>Code</summary>

```ts
setUsage( value ) {

		this.usage = value;

		return this;

	}
```
</details>

##### `addUpdateRange(start: number, count: number): void`

<details><summary>Code</summary>

```ts
addUpdateRange( start, count ) {

		this.updateRanges.push( { start, count } );

	}
```
</details>

##### `clearUpdateRanges(): void`

<details><summary>Code</summary>

```ts
clearUpdateRanges() {

		this.updateRanges.length = 0;

	}
```
</details>

##### `copy(source: BufferAttribute): BufferAttribute`

<details><summary>Code</summary>

```ts
copy( source ) {

		this.name = source.name;
		this.array = new source.array.constructor( source.array );
		this.itemSize = source.itemSize;
		this.count = source.count;
		this.normalized = source.normalized;

		this.usage = source.usage;
		this.gpuType = source.gpuType;

		return this;

	}
```
</details>

##### `copyAt(index1: number, attribute: BufferAttribute, index2: number): BufferAttribute`

<details><summary>Code</summary>

```ts
copyAt( index1, attribute, index2 ) {

		index1 *= this.itemSize;
		index2 *= attribute.itemSize;

		for ( let i = 0, l = this.itemSize; i < l; i ++ ) {

			this.array[ index1 + i ] = attribute.array[ index2 + i ];

		}

		return this;

	}
```
</details>

##### `copyArray(array: any): BufferAttribute`

<details><summary>Code</summary>

```ts
copyArray( array ) {

		this.array.set( array );

		return this;

	}
```
</details>

##### `applyMatrix3(m: Matrix3): BufferAttribute`

<details><summary>Code</summary>

```ts
applyMatrix3( m ) {

		if ( this.itemSize === 2 ) {

			for ( let i = 0, l = this.count; i < l; i ++ ) {

				_vector2.fromBufferAttribute( this, i );
				_vector2.applyMatrix3( m );

				this.setXY( i, _vector2.x, _vector2.y );

			}

		} else if ( this.itemSize === 3 ) {

			for ( let i = 0, l = this.count; i < l; i ++ ) {

				_vector.fromBufferAttribute( this, i );
				_vector.applyMatrix3( m );

				this.setXYZ( i, _vector.x, _vector.y, _vector.z );

			}

		}

		return this;

	}
```
</details>

##### `applyMatrix4(m: Matrix4): BufferAttribute`

<details><summary>Code</summary>

```ts
applyMatrix4( m ) {

		for ( let i = 0, l = this.count; i < l; i ++ ) {

			_vector.fromBufferAttribute( this, i );

			_vector.applyMatrix4( m );

			this.setXYZ( i, _vector.x, _vector.y, _vector.z );

		}

		return this;

	}
```
</details>

##### `applyNormalMatrix(m: Matrix3): BufferAttribute`

<details><summary>Code</summary>

```ts
applyNormalMatrix( m ) {

		for ( let i = 0, l = this.count; i < l; i ++ ) {

			_vector.fromBufferAttribute( this, i );

			_vector.applyNormalMatrix( m );

			this.setXYZ( i, _vector.x, _vector.y, _vector.z );

		}

		return this;

	}
```
</details>

##### `transformDirection(m: Matrix4): BufferAttribute`

<details><summary>Code</summary>

```ts
transformDirection( m ) {

		for ( let i = 0, l = this.count; i < l; i ++ ) {

			_vector.fromBufferAttribute( this, i );

			_vector.transformDirection( m );

			this.setXYZ( i, _vector.x, _vector.y, _vector.z );

		}

		return this;

	}
```
</details>

##### `set(value: any, offset: number): BufferAttribute`

<details><summary>Code</summary>

```ts
set( value, offset = 0 ) {

		// Matching BufferAttribute constructor, do not normalize the array.
		this.array.set( value, offset );

		return this;

	}
```
</details>

##### `getComponent(index: number, component: number): number`

<details><summary>Code</summary>

```ts
getComponent( index, component ) {

		let value = this.array[ index * this.itemSize + component ];

		if ( this.normalized ) value = denormalize( value, this.array );

		return value;

	}
```
</details>

##### `setComponent(index: number, component: number, value: number): BufferAttribute`

<details><summary>Code</summary>

```ts
setComponent( index, component, value ) {

		if ( this.normalized ) value = normalize( value, this.array );

		this.array[ index * this.itemSize + component ] = value;

		return this;

	}
```
</details>

##### `getX(index: number): number`

<details><summary>Code</summary>

```ts
getX( index ) {

		let x = this.array[ index * this.itemSize ];

		if ( this.normalized ) x = denormalize( x, this.array );

		return x;

	}
```
</details>

##### `setX(index: number, x: number): BufferAttribute`

<details><summary>Code</summary>

```ts
setX( index, x ) {

		if ( this.normalized ) x = normalize( x, this.array );

		this.array[ index * this.itemSize ] = x;

		return this;

	}
```
</details>

##### `getY(index: number): number`

<details><summary>Code</summary>

```ts
getY( index ) {

		let y = this.array[ index * this.itemSize + 1 ];

		if ( this.normalized ) y = denormalize( y, this.array );

		return y;

	}
```
</details>

##### `setY(index: number, y: number): BufferAttribute`

<details><summary>Code</summary>

```ts
setY( index, y ) {

		if ( this.normalized ) y = normalize( y, this.array );

		this.array[ index * this.itemSize + 1 ] = y;

		return this;

	}
```
</details>

##### `getZ(index: number): number`

<details><summary>Code</summary>

```ts
getZ( index ) {

		let z = this.array[ index * this.itemSize + 2 ];

		if ( this.normalized ) z = denormalize( z, this.array );

		return z;

	}
```
</details>

##### `setZ(index: number, z: number): BufferAttribute`

<details><summary>Code</summary>

```ts
setZ( index, z ) {

		if ( this.normalized ) z = normalize( z, this.array );

		this.array[ index * this.itemSize + 2 ] = z;

		return this;

	}
```
</details>

##### `getW(index: number): number`

<details><summary>Code</summary>

```ts
getW( index ) {

		let w = this.array[ index * this.itemSize + 3 ];

		if ( this.normalized ) w = denormalize( w, this.array );

		return w;

	}
```
</details>

##### `setW(index: number, w: number): BufferAttribute`

<details><summary>Code</summary>

```ts
setW( index, w ) {

		if ( this.normalized ) w = normalize( w, this.array );

		this.array[ index * this.itemSize + 3 ] = w;

		return this;

	}
```
</details>

##### `setXY(index: number, x: number, y: number): BufferAttribute`

<details><summary>Code</summary>

```ts
setXY( index, x, y ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );

		}

		this.array[ index + 0 ] = x;
		this.array[ index + 1 ] = y;

		return this;

	}
```
</details>

##### `setXYZ(index: number, x: number, y: number, z: number): BufferAttribute`

<details><summary>Code</summary>

```ts
setXYZ( index, x, y, z ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );

		}

		this.array[ index + 0 ] = x;
		this.array[ index + 1 ] = y;
		this.array[ index + 2 ] = z;

		return this;

	}
```
</details>

##### `setXYZW(index: number, x: number, y: number, z: number, w: number): BufferAttribute`

<details><summary>Code</summary>

```ts
setXYZW( index, x, y, z, w ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );
			w = normalize( w, this.array );

		}

		this.array[ index + 0 ] = x;
		this.array[ index + 1 ] = y;
		this.array[ index + 2 ] = z;
		this.array[ index + 3 ] = w;

		return this;

	}
```
</details>

##### `onUpload(callback: Function): BufferAttribute`

<details><summary>Code</summary>

```ts
onUpload( callback ) {

		this.onUploadCallback = callback;

		return this;

	}
```
</details>

##### `clone(): BufferAttribute`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor( this.array, this.itemSize ).copy( this );

	}
```
</details>

##### `toJSON(): any`

<details><summary>Code</summary>

```ts
toJSON() {

		const data = {
			itemSize: this.itemSize,
			type: this.array.constructor.name,
			array: Array.from( this.array ),
			normalized: this.normalized
		};

		if ( this.name !== '' ) data.name = this.name;
		if ( this.usage !== StaticDrawUsage ) data.usage = this.usage;

		return data;

	}
```
</details>

### `Int8BufferAttribute`

<details><summary>Class Code</summary>

```ts
class Int8BufferAttribute extends BufferAttribute {

	/**
	 * Constructs a new buffer attribute.
	 *
	 * @param {(Array<number>|Int8Array)} array - The array holding the attribute data.
	 * @param {number} itemSize - The item size.
	 * @param {boolean} [normalized=false] - Whether the data are normalized or not.
	 */
	constructor( array, itemSize, normalized ) {

		super( new Int8Array( array ), itemSize, normalized );

	}

}
```
</details>

### `Uint8BufferAttribute`

<details><summary>Class Code</summary>

```ts
class Uint8BufferAttribute extends BufferAttribute {

	/**
	 * Constructs a new buffer attribute.
	 *
	 * @param {(Array<number>|Uint8Array)} array - The array holding the attribute data.
	 * @param {number} itemSize - The item size.
	 * @param {boolean} [normalized=false] - Whether the data are normalized or not.
	 */
	constructor( array, itemSize, normalized ) {

		super( new Uint8Array( array ), itemSize, normalized );

	}

}
```
</details>

### `Uint8ClampedBufferAttribute`

<details><summary>Class Code</summary>

```ts
class Uint8ClampedBufferAttribute extends BufferAttribute {

	/**
	 * Constructs a new buffer attribute.
	 *
	 * @param {(Array<number>|Uint8ClampedArray)} array - The array holding the attribute data.
	 * @param {number} itemSize - The item size.
	 * @param {boolean} [normalized=false] - Whether the data are normalized or not.
	 */
	constructor( array, itemSize, normalized ) {

		super( new Uint8ClampedArray( array ), itemSize, normalized );

	}

}
```
</details>

### `Int16BufferAttribute`

<details><summary>Class Code</summary>

```ts
class Int16BufferAttribute extends BufferAttribute {

	/**
	 * Constructs a new buffer attribute.
	 *
	 * @param {(Array<number>|Int16Array)} array - The array holding the attribute data.
	 * @param {number} itemSize - The item size.
	 * @param {boolean} [normalized=false] - Whether the data are normalized or not.
	 */
	constructor( array, itemSize, normalized ) {

		super( new Int16Array( array ), itemSize, normalized );

	}

}
```
</details>

### `Uint16BufferAttribute`

<details><summary>Class Code</summary>

```ts
class Uint16BufferAttribute extends BufferAttribute {

	/**
	 * Constructs a new buffer attribute.
	 *
	 * @param {(Array<number>|Uint16Array)} array - The array holding the attribute data.
	 * @param {number} itemSize - The item size.
	 * @param {boolean} [normalized=false] - Whether the data are normalized or not.
	 */
	constructor( array, itemSize, normalized ) {

		super( new Uint16Array( array ), itemSize, normalized );

	}

}
```
</details>

### `Int32BufferAttribute`

<details><summary>Class Code</summary>

```ts
class Int32BufferAttribute extends BufferAttribute {

	/**
	 * Constructs a new buffer attribute.
	 *
	 * @param {(Array<number>|Int32Array)} array - The array holding the attribute data.
	 * @param {number} itemSize - The item size.
	 * @param {boolean} [normalized=false] - Whether the data are normalized or not.
	 */
	constructor( array, itemSize, normalized ) {

		super( new Int32Array( array ), itemSize, normalized );

	}

}
```
</details>

### `Uint32BufferAttribute`

<details><summary>Class Code</summary>

```ts
class Uint32BufferAttribute extends BufferAttribute {

	/**
	 * Constructs a new buffer attribute.
	 *
	 * @param {(Array<number>|Uint32Array)} array - The array holding the attribute data.
	 * @param {number} itemSize - The item size.
	 * @param {boolean} [normalized=false] - Whether the data are normalized or not.
	 */
	constructor( array, itemSize, normalized ) {

		super( new Uint32Array( array ), itemSize, normalized );

	}

}
```
</details>

### `Float16BufferAttribute`

<details><summary>Class Code</summary>

```ts
class Float16BufferAttribute extends BufferAttribute {

	/**
	 * Constructs a new buffer attribute.
	 *
	 * @param {(Array<number>|Uint16Array)} array - The array holding the attribute data.
	 * @param {number} itemSize - The item size.
	 * @param {boolean} [normalized=false] - Whether the data are normalized or not.
	 */
	constructor( array, itemSize, normalized ) {

		super( new Uint16Array( array ), itemSize, normalized );

		this.isFloat16BufferAttribute = true;

	}

	getX( index ) {

		let x = fromHalfFloat( this.array[ index * this.itemSize ] );

		if ( this.normalized ) x = denormalize( x, this.array );

		return x;

	}

	setX( index, x ) {

		if ( this.normalized ) x = normalize( x, this.array );

		this.array[ index * this.itemSize ] = toHalfFloat( x );

		return this;

	}

	getY( index ) {

		let y = fromHalfFloat( this.array[ index * this.itemSize + 1 ] );

		if ( this.normalized ) y = denormalize( y, this.array );

		return y;

	}

	setY( index, y ) {

		if ( this.normalized ) y = normalize( y, this.array );

		this.array[ index * this.itemSize + 1 ] = toHalfFloat( y );

		return this;

	}

	getZ( index ) {

		let z = fromHalfFloat( this.array[ index * this.itemSize + 2 ] );

		if ( this.normalized ) z = denormalize( z, this.array );

		return z;

	}

	setZ( index, z ) {

		if ( this.normalized ) z = normalize( z, this.array );

		this.array[ index * this.itemSize + 2 ] = toHalfFloat( z );

		return this;

	}

	getW( index ) {

		let w = fromHalfFloat( this.array[ index * this.itemSize + 3 ] );

		if ( this.normalized ) w = denormalize( w, this.array );

		return w;

	}

	setW( index, w ) {

		if ( this.normalized ) w = normalize( w, this.array );

		this.array[ index * this.itemSize + 3 ] = toHalfFloat( w );

		return this;

	}

	setXY( index, x, y ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );

		}

		this.array[ index + 0 ] = toHalfFloat( x );
		this.array[ index + 1 ] = toHalfFloat( y );

		return this;

	}

	setXYZ( index, x, y, z ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );

		}

		this.array[ index + 0 ] = toHalfFloat( x );
		this.array[ index + 1 ] = toHalfFloat( y );
		this.array[ index + 2 ] = toHalfFloat( z );

		return this;

	}

	setXYZW( index, x, y, z, w ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );
			w = normalize( w, this.array );

		}

		this.array[ index + 0 ] = toHalfFloat( x );
		this.array[ index + 1 ] = toHalfFloat( y );
		this.array[ index + 2 ] = toHalfFloat( z );
		this.array[ index + 3 ] = toHalfFloat( w );

		return this;

	}

}
```
</details>

#### Methods

##### `getX(index: any): number`

<details><summary>Code</summary>

```ts
getX( index ) {

		let x = fromHalfFloat( this.array[ index * this.itemSize ] );

		if ( this.normalized ) x = denormalize( x, this.array );

		return x;

	}
```
</details>

##### `setX(index: any, x: any): this`

<details><summary>Code</summary>

```ts
setX( index, x ) {

		if ( this.normalized ) x = normalize( x, this.array );

		this.array[ index * this.itemSize ] = toHalfFloat( x );

		return this;

	}
```
</details>

##### `getY(index: any): number`

<details><summary>Code</summary>

```ts
getY( index ) {

		let y = fromHalfFloat( this.array[ index * this.itemSize + 1 ] );

		if ( this.normalized ) y = denormalize( y, this.array );

		return y;

	}
```
</details>

##### `setY(index: any, y: any): this`

<details><summary>Code</summary>

```ts
setY( index, y ) {

		if ( this.normalized ) y = normalize( y, this.array );

		this.array[ index * this.itemSize + 1 ] = toHalfFloat( y );

		return this;

	}
```
</details>

##### `getZ(index: any): number`

<details><summary>Code</summary>

```ts
getZ( index ) {

		let z = fromHalfFloat( this.array[ index * this.itemSize + 2 ] );

		if ( this.normalized ) z = denormalize( z, this.array );

		return z;

	}
```
</details>

##### `setZ(index: any, z: any): this`

<details><summary>Code</summary>

```ts
setZ( index, z ) {

		if ( this.normalized ) z = normalize( z, this.array );

		this.array[ index * this.itemSize + 2 ] = toHalfFloat( z );

		return this;

	}
```
</details>

##### `getW(index: any): number`

<details><summary>Code</summary>

```ts
getW( index ) {

		let w = fromHalfFloat( this.array[ index * this.itemSize + 3 ] );

		if ( this.normalized ) w = denormalize( w, this.array );

		return w;

	}
```
</details>

##### `setW(index: any, w: any): this`

<details><summary>Code</summary>

```ts
setW( index, w ) {

		if ( this.normalized ) w = normalize( w, this.array );

		this.array[ index * this.itemSize + 3 ] = toHalfFloat( w );

		return this;

	}
```
</details>

##### `setXY(index: any, x: any, y: any): this`

<details><summary>Code</summary>

```ts
setXY( index, x, y ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );

		}

		this.array[ index + 0 ] = toHalfFloat( x );
		this.array[ index + 1 ] = toHalfFloat( y );

		return this;

	}
```
</details>

##### `setXYZ(index: any, x: any, y: any, z: any): this`

<details><summary>Code</summary>

```ts
setXYZ( index, x, y, z ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );

		}

		this.array[ index + 0 ] = toHalfFloat( x );
		this.array[ index + 1 ] = toHalfFloat( y );
		this.array[ index + 2 ] = toHalfFloat( z );

		return this;

	}
```
</details>

##### `setXYZW(index: any, x: any, y: any, z: any, w: any): this`

<details><summary>Code</summary>

```ts
setXYZW( index, x, y, z, w ) {

		index *= this.itemSize;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );
			w = normalize( w, this.array );

		}

		this.array[ index + 0 ] = toHalfFloat( x );
		this.array[ index + 1 ] = toHalfFloat( y );
		this.array[ index + 2 ] = toHalfFloat( z );
		this.array[ index + 3 ] = toHalfFloat( w );

		return this;

	}
```
</details>

### `Float32BufferAttribute`

<details><summary>Class Code</summary>

```ts
class Float32BufferAttribute extends BufferAttribute {

	/**
	 * Constructs a new buffer attribute.
	 *
	 * @param {(Array<number>|Float32Array)} array - The array holding the attribute data.
	 * @param {number} itemSize - The item size.
	 * @param {boolean} [normalized=false] - Whether the data are normalized or not.
	 */
	constructor( array, itemSize, normalized ) {

		super( new Float32Array( array ), itemSize, normalized );

	}

}
```
</details>


---