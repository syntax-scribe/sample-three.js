[⬅️ Back to Table of Contents](../../index.md)

# 📄 `InterleavedBufferAttribute.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 18 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 10 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/core/InterleavedBufferAttribute.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector3` | `../math/Vector3.js` |
| `BufferAttribute` | `./BufferAttribute.js` |
| `denormalize` | `../math/MathUtils.js` |
| `normalize` | `../math/MathUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_vector` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `value` | `TypedArray` | let/var | `this.array[ index * this.data.stride + this.offset + component ]` | ✗ |
| `x` | `any` | let/var | `this.data.array[ index * this.data.stride + this.offset ]` | ✗ |
| `y` | `any` | let/var | `this.data.array[ index * this.data.stride + this.offset + 1 ]` | ✗ |
| `z` | `any` | let/var | `this.data.array[ index * this.data.stride + this.offset + 2 ]` | ✗ |
| `w` | `any` | let/var | `this.data.array[ index * this.data.stride + this.offset + 3 ]` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `index` | `number` | let/var | `i * this.data.stride + this.offset` | ✗ |
| `array` | `any[]` | let/var | `[]` | ✗ |
| `index` | `number` | let/var | `i * this.data.stride + this.offset` | ✗ |


---

## Functions

### `InterleavedBufferAttribute.applyMatrix4(m: Matrix4): InterleavedBufferAttribute`

**JSDoc:**
```typescript
/**
	 * Applies the given 4x4 matrix to the given attribute. Only works with
	 * item size `3`.
	 *
	 * @param {Matrix4} m - The matrix to apply.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`m`** `Matrix4`

**Returns:** `InterleavedBufferAttribute`

**Calls:**

- `_vector.fromBufferAttribute`
- `_vector.applyMatrix4`
- `this.setXYZ`

<details><summary>Code</summary>

```typescript
applyMatrix4( m ) {

		for ( let i = 0, l = this.data.count; i < l; i ++ ) {

			_vector.fromBufferAttribute( this, i );

			_vector.applyMatrix4( m );

			this.setXYZ( i, _vector.x, _vector.y, _vector.z );

		}

		return this;

	}
```
</details>

### `InterleavedBufferAttribute.applyNormalMatrix(m: Matrix3): InterleavedBufferAttribute`

**JSDoc:**
```typescript
/**
	 * Applies the given 3x3 normal matrix to the given attribute. Only works with
	 * item size `3`.
	 *
	 * @param {Matrix3} m - The normal matrix to apply.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`m`** `Matrix3`

**Returns:** `InterleavedBufferAttribute`

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

### `InterleavedBufferAttribute.transformDirection(m: Matrix4): InterleavedBufferAttribute`

**JSDoc:**
```typescript
/**
	 * Applies the given 4x4 matrix to the given attribute. Only works with
	 * item size `3` and with direction vectors.
	 *
	 * @param {Matrix4} m - The matrix to apply.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`m`** `Matrix4`

**Returns:** `InterleavedBufferAttribute`

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

### `InterleavedBufferAttribute.getComponent(index: number, component: number): number`

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

		let value = this.array[ index * this.data.stride + this.offset + component ];

		if ( this.normalized ) value = denormalize( value, this.array );

		return value;

	}
```
</details>

### `InterleavedBufferAttribute.setComponent(index: number, component: number, value: number): InterleavedBufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the given value to the given component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} component - The component index.
	 * @param {number} value - The value to set.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`index`** `number`
- **`component`** `number`
- **`value`** `number`

**Returns:** `InterleavedBufferAttribute`

**Calls:**

- `normalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
setComponent( index, component, value ) {

		if ( this.normalized ) value = normalize( value, this.array );

		this.data.array[ index * this.data.stride + this.offset + component ] = value;

		return this;

	}
```
</details>

### `InterleavedBufferAttribute.setX(index: number, x: number): InterleavedBufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the x component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} x - The value to set.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`index`** `number`
- **`x`** `number`

**Returns:** `InterleavedBufferAttribute`

**Calls:**

- `normalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
setX( index, x ) {

		if ( this.normalized ) x = normalize( x, this.array );

		this.data.array[ index * this.data.stride + this.offset ] = x;

		return this;

	}
```
</details>

### `InterleavedBufferAttribute.setY(index: number, y: number): InterleavedBufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the y component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} y - The value to set.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`index`** `number`
- **`y`** `number`

**Returns:** `InterleavedBufferAttribute`

**Calls:**

- `normalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
setY( index, y ) {

		if ( this.normalized ) y = normalize( y, this.array );

		this.data.array[ index * this.data.stride + this.offset + 1 ] = y;

		return this;

	}
```
</details>

### `InterleavedBufferAttribute.setZ(index: number, z: number): InterleavedBufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the z component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} z - The value to set.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`index`** `number`
- **`z`** `number`

**Returns:** `InterleavedBufferAttribute`

**Calls:**

- `normalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
setZ( index, z ) {

		if ( this.normalized ) z = normalize( z, this.array );

		this.data.array[ index * this.data.stride + this.offset + 2 ] = z;

		return this;

	}
```
</details>

### `InterleavedBufferAttribute.setW(index: number, w: number): InterleavedBufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the w component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} w - The value to set.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`index`** `number`
- **`w`** `number`

**Returns:** `InterleavedBufferAttribute`

**Calls:**

- `normalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
setW( index, w ) {

		if ( this.normalized ) w = normalize( w, this.array );

		this.data.array[ index * this.data.stride + this.offset + 3 ] = w;

		return this;

	}
```
</details>

### `InterleavedBufferAttribute.getX(index: number): number`

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

		let x = this.data.array[ index * this.data.stride + this.offset ];

		if ( this.normalized ) x = denormalize( x, this.array );

		return x;

	}
```
</details>

### `InterleavedBufferAttribute.getY(index: number): number`

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

		let y = this.data.array[ index * this.data.stride + this.offset + 1 ];

		if ( this.normalized ) y = denormalize( y, this.array );

		return y;

	}
```
</details>

### `InterleavedBufferAttribute.getZ(index: number): number`

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

		let z = this.data.array[ index * this.data.stride + this.offset + 2 ];

		if ( this.normalized ) z = denormalize( z, this.array );

		return z;

	}
```
</details>

### `InterleavedBufferAttribute.getW(index: number): number`

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

		let w = this.data.array[ index * this.data.stride + this.offset + 3 ];

		if ( this.normalized ) w = denormalize( w, this.array );

		return w;

	}
```
</details>

### `InterleavedBufferAttribute.setXY(index: number, x: number, y: number): InterleavedBufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the x and y component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} x - The value for the x component to set.
	 * @param {number} y - The value for the y component to set.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`index`** `number`
- **`x`** `number`
- **`y`** `number`

**Returns:** `InterleavedBufferAttribute`

**Calls:**

- `normalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
setXY( index, x, y ) {

		index = index * this.data.stride + this.offset;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );

		}

		this.data.array[ index + 0 ] = x;
		this.data.array[ index + 1 ] = y;

		return this;

	}
```
</details>

### `InterleavedBufferAttribute.setXYZ(index: number, x: number, y: number, z: number): InterleavedBufferAttribute`

**JSDoc:**
```typescript
/**
	 * Sets the x, y and z component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} x - The value for the x component to set.
	 * @param {number} y - The value for the y component to set.
	 * @param {number} z - The value for the z component to set.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`index`** `number`
- **`x`** `number`
- **`y`** `number`
- **`z`** `number`

**Returns:** `InterleavedBufferAttribute`

**Calls:**

- `normalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
setXYZ( index, x, y, z ) {

		index = index * this.data.stride + this.offset;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );

		}

		this.data.array[ index + 0 ] = x;
		this.data.array[ index + 1 ] = y;
		this.data.array[ index + 2 ] = z;

		return this;

	}
```
</details>

### `InterleavedBufferAttribute.setXYZW(index: number, x: number, y: number, z: number, w: number): InterleavedBufferAttribute`

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
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
```

**Parameters:**

- **`index`** `number`
- **`x`** `number`
- **`y`** `number`
- **`z`** `number`
- **`w`** `number`

**Returns:** `InterleavedBufferAttribute`

**Calls:**

- `normalize (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
setXYZW( index, x, y, z, w ) {

		index = index * this.data.stride + this.offset;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );
			w = normalize( w, this.array );

		}

		this.data.array[ index + 0 ] = x;
		this.data.array[ index + 1 ] = y;
		this.data.array[ index + 2 ] = z;
		this.data.array[ index + 3 ] = w;

		return this;

	}
```
</details>

### `InterleavedBufferAttribute.clone(data: any): BufferAttribute | InterleavedBufferAttribute`

**JSDoc:**
```typescript
/**
	 * Returns a new buffer attribute with copied values from this instance.
	 *
	 * If no parameter is provided, cloning an interleaved buffer attribute will de-interleave buffer data.
	 *
	 * @param {Object} [data] - An object with interleaved buffers that allows to retain the interleaved property.
	 * @return {BufferAttribute|InterleavedBufferAttribute} A clone of this instance.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `BufferAttribute | InterleavedBufferAttribute`

**Calls:**

- `console.log`
- `array.push`
- `this.data.clone`

<details><summary>Code</summary>

```typescript
clone( data ) {

		if ( data === undefined ) {

			console.log( 'THREE.InterleavedBufferAttribute.clone(): Cloning an interleaved buffer attribute will de-interleave buffer data.' );

			const array = [];

			for ( let i = 0; i < this.count; i ++ ) {

				const index = i * this.data.stride + this.offset;

				for ( let j = 0; j < this.itemSize; j ++ ) {

					array.push( this.data.array[ index + j ] );

				}

			}

			return new BufferAttribute( new this.array.constructor( array ), this.itemSize, this.normalized );

		} else {

			if ( data.interleavedBuffers === undefined ) {

				data.interleavedBuffers = {};

			}

			if ( data.interleavedBuffers[ this.data.uuid ] === undefined ) {

				data.interleavedBuffers[ this.data.uuid ] = this.data.clone( data );

			}

			return new InterleavedBufferAttribute( data.interleavedBuffers[ this.data.uuid ], this.itemSize, this.offset, this.normalized );

		}

	}
```
</details>

### `InterleavedBufferAttribute.toJSON(data: any): any`

**JSDoc:**
```typescript
/**
	 * Serializes the buffer attribute into JSON.
	 *
	 * If no parameter is provided, cloning an interleaved buffer attribute will de-interleave buffer data.
	 *
	 * @param {Object} [data] - An optional value holding meta information about the serialization.
	 * @return {Object} A JSON object representing the serialized buffer attribute.
	 */
```

**Parameters:**

- **`data`** `any`

**Returns:** `any`

**Calls:**

- `console.log`
- `array.push`
- `this.data.toJSON`

**Internal Comments:**
```
// de-interleave data and save it as an ordinary buffer attribute for now
// save as true interleaved attribute
```

<details><summary>Code</summary>

```typescript
toJSON( data ) {

		if ( data === undefined ) {

			console.log( 'THREE.InterleavedBufferAttribute.toJSON(): Serializing an interleaved buffer attribute will de-interleave buffer data.' );

			const array = [];

			for ( let i = 0; i < this.count; i ++ ) {

				const index = i * this.data.stride + this.offset;

				for ( let j = 0; j < this.itemSize; j ++ ) {

					array.push( this.data.array[ index + j ] );

				}

			}

			// de-interleave data and save it as an ordinary buffer attribute for now

			return {
				itemSize: this.itemSize,
				type: this.array.constructor.name,
				array: array,
				normalized: this.normalized
			};

		} else {

			// save as true interleaved attribute

			if ( data.interleavedBuffers === undefined ) {

				data.interleavedBuffers = {};

			}

			if ( data.interleavedBuffers[ this.data.uuid ] === undefined ) {

				data.interleavedBuffers[ this.data.uuid ] = this.data.toJSON( data );

			}

			return {
				isInterleavedBufferAttribute: true,
				itemSize: this.itemSize,
				data: this.data.uuid,
				offset: this.offset,
				normalized: this.normalized
			};

		}

	}
```
</details>


---

## Classes

### `InterleavedBufferAttribute`

<details><summary>Class Code</summary>

```ts
class InterleavedBufferAttribute {

	/**
	 * Constructs a new interleaved buffer attribute.
	 *
	 * @param {InterleavedBuffer} interleavedBuffer - The buffer holding the interleaved data.
	 * @param {number} itemSize - The item size.
	 * @param {number} offset - The attribute offset into the buffer.
	 * @param {boolean} [normalized=false] - Whether the data are normalized or not.
	 */
	constructor( interleavedBuffer, itemSize, offset, normalized = false ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isInterleavedBufferAttribute = true;

		/**
		 * The name of the buffer attribute.
		 *
		 * @type {string}
		 */
		this.name = '';

		/**
		 * The buffer holding the interleaved data.
		 *
		 * @type {InterleavedBuffer}
		 */
		this.data = interleavedBuffer;

		/**
		 * The item size, see {@link BufferAttribute#itemSize}.
		 *
		 * @type {number}
		 */
		this.itemSize = itemSize;

		/**
		 * The attribute offset into the buffer.
		 *
		 * @type {number}
		 */
		this.offset = offset;

		/**
		 * Whether the data are normalized or not, see {@link BufferAttribute#normalized}
		 *
		 * @type {InterleavedBuffer}
		 */
		this.normalized = normalized;

	}

	/**
	 * The item count of this buffer attribute.
	 *
	 * @type {number}
	 * @readonly
	 */
	get count() {

		return this.data.count;

	}

	/**
	 * The array holding the interleaved buffer attribute data.
	 *
	 * @type {TypedArray}
	 */
	get array() {

		return this.data.array;

	}

	/**
	 * Flag to indicate that this attribute has changed and should be re-sent to
	 * the GPU. Set this to `true` when you modify the value of the array.
	 *
	 * @type {number}
	 * @default false
	 * @param {boolean} value
	 */
	set needsUpdate( value ) {

		this.data.needsUpdate = value;

	}

	/**
	 * Applies the given 4x4 matrix to the given attribute. Only works with
	 * item size `3`.
	 *
	 * @param {Matrix4} m - The matrix to apply.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
	applyMatrix4( m ) {

		for ( let i = 0, l = this.data.count; i < l; i ++ ) {

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
	 * @return {InterleavedBufferAttribute} A reference to this instance.
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
	 * @return {InterleavedBufferAttribute} A reference to this instance.
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
	 * Returns the given component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} component - The component index.
	 * @return {number} The returned value.
	 */
	getComponent( index, component ) {

		let value = this.array[ index * this.data.stride + this.offset + component ];

		if ( this.normalized ) value = denormalize( value, this.array );

		return value;

	}

	/**
	 * Sets the given value to the given component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} component - The component index.
	 * @param {number} value - The value to set.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
	setComponent( index, component, value ) {

		if ( this.normalized ) value = normalize( value, this.array );

		this.data.array[ index * this.data.stride + this.offset + component ] = value;

		return this;

	}

	/**
	 * Sets the x component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} x - The value to set.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
	setX( index, x ) {

		if ( this.normalized ) x = normalize( x, this.array );

		this.data.array[ index * this.data.stride + this.offset ] = x;

		return this;

	}

	/**
	 * Sets the y component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} y - The value to set.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
	setY( index, y ) {

		if ( this.normalized ) y = normalize( y, this.array );

		this.data.array[ index * this.data.stride + this.offset + 1 ] = y;

		return this;

	}

	/**
	 * Sets the z component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} z - The value to set.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
	setZ( index, z ) {

		if ( this.normalized ) z = normalize( z, this.array );

		this.data.array[ index * this.data.stride + this.offset + 2 ] = z;

		return this;

	}

	/**
	 * Sets the w component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} w - The value to set.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
	setW( index, w ) {

		if ( this.normalized ) w = normalize( w, this.array );

		this.data.array[ index * this.data.stride + this.offset + 3 ] = w;

		return this;

	}

	/**
	 * Returns the x component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @return {number} The x component.
	 */
	getX( index ) {

		let x = this.data.array[ index * this.data.stride + this.offset ];

		if ( this.normalized ) x = denormalize( x, this.array );

		return x;

	}

	/**
	 * Returns the y component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @return {number} The y component.
	 */
	getY( index ) {

		let y = this.data.array[ index * this.data.stride + this.offset + 1 ];

		if ( this.normalized ) y = denormalize( y, this.array );

		return y;

	}

	/**
	 * Returns the z component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @return {number} The z component.
	 */
	getZ( index ) {

		let z = this.data.array[ index * this.data.stride + this.offset + 2 ];

		if ( this.normalized ) z = denormalize( z, this.array );

		return z;

	}

	/**
	 * Returns the w component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @return {number} The w component.
	 */
	getW( index ) {

		let w = this.data.array[ index * this.data.stride + this.offset + 3 ];

		if ( this.normalized ) w = denormalize( w, this.array );

		return w;

	}

	/**
	 * Sets the x and y component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} x - The value for the x component to set.
	 * @param {number} y - The value for the y component to set.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
	setXY( index, x, y ) {

		index = index * this.data.stride + this.offset;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );

		}

		this.data.array[ index + 0 ] = x;
		this.data.array[ index + 1 ] = y;

		return this;

	}

	/**
	 * Sets the x, y and z component of the vector at the given index.
	 *
	 * @param {number} index - The index into the buffer attribute.
	 * @param {number} x - The value for the x component to set.
	 * @param {number} y - The value for the y component to set.
	 * @param {number} z - The value for the z component to set.
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
	setXYZ( index, x, y, z ) {

		index = index * this.data.stride + this.offset;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );

		}

		this.data.array[ index + 0 ] = x;
		this.data.array[ index + 1 ] = y;
		this.data.array[ index + 2 ] = z;

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
	 * @return {InterleavedBufferAttribute} A reference to this instance.
	 */
	setXYZW( index, x, y, z, w ) {

		index = index * this.data.stride + this.offset;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );
			w = normalize( w, this.array );

		}

		this.data.array[ index + 0 ] = x;
		this.data.array[ index + 1 ] = y;
		this.data.array[ index + 2 ] = z;
		this.data.array[ index + 3 ] = w;

		return this;

	}

	/**
	 * Returns a new buffer attribute with copied values from this instance.
	 *
	 * If no parameter is provided, cloning an interleaved buffer attribute will de-interleave buffer data.
	 *
	 * @param {Object} [data] - An object with interleaved buffers that allows to retain the interleaved property.
	 * @return {BufferAttribute|InterleavedBufferAttribute} A clone of this instance.
	 */
	clone( data ) {

		if ( data === undefined ) {

			console.log( 'THREE.InterleavedBufferAttribute.clone(): Cloning an interleaved buffer attribute will de-interleave buffer data.' );

			const array = [];

			for ( let i = 0; i < this.count; i ++ ) {

				const index = i * this.data.stride + this.offset;

				for ( let j = 0; j < this.itemSize; j ++ ) {

					array.push( this.data.array[ index + j ] );

				}

			}

			return new BufferAttribute( new this.array.constructor( array ), this.itemSize, this.normalized );

		} else {

			if ( data.interleavedBuffers === undefined ) {

				data.interleavedBuffers = {};

			}

			if ( data.interleavedBuffers[ this.data.uuid ] === undefined ) {

				data.interleavedBuffers[ this.data.uuid ] = this.data.clone( data );

			}

			return new InterleavedBufferAttribute( data.interleavedBuffers[ this.data.uuid ], this.itemSize, this.offset, this.normalized );

		}

	}

	/**
	 * Serializes the buffer attribute into JSON.
	 *
	 * If no parameter is provided, cloning an interleaved buffer attribute will de-interleave buffer data.
	 *
	 * @param {Object} [data] - An optional value holding meta information about the serialization.
	 * @return {Object} A JSON object representing the serialized buffer attribute.
	 */
	toJSON( data ) {

		if ( data === undefined ) {

			console.log( 'THREE.InterleavedBufferAttribute.toJSON(): Serializing an interleaved buffer attribute will de-interleave buffer data.' );

			const array = [];

			for ( let i = 0; i < this.count; i ++ ) {

				const index = i * this.data.stride + this.offset;

				for ( let j = 0; j < this.itemSize; j ++ ) {

					array.push( this.data.array[ index + j ] );

				}

			}

			// de-interleave data and save it as an ordinary buffer attribute for now

			return {
				itemSize: this.itemSize,
				type: this.array.constructor.name,
				array: array,
				normalized: this.normalized
			};

		} else {

			// save as true interleaved attribute

			if ( data.interleavedBuffers === undefined ) {

				data.interleavedBuffers = {};

			}

			if ( data.interleavedBuffers[ this.data.uuid ] === undefined ) {

				data.interleavedBuffers[ this.data.uuid ] = this.data.toJSON( data );

			}

			return {
				isInterleavedBufferAttribute: true,
				itemSize: this.itemSize,
				data: this.data.uuid,
				offset: this.offset,
				normalized: this.normalized
			};

		}

	}

}
```
</details>

#### Methods

##### `applyMatrix4(m: Matrix4): InterleavedBufferAttribute`

<details><summary>Code</summary>

```ts
applyMatrix4( m ) {

		for ( let i = 0, l = this.data.count; i < l; i ++ ) {

			_vector.fromBufferAttribute( this, i );

			_vector.applyMatrix4( m );

			this.setXYZ( i, _vector.x, _vector.y, _vector.z );

		}

		return this;

	}
```
</details>

##### `applyNormalMatrix(m: Matrix3): InterleavedBufferAttribute`

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

##### `transformDirection(m: Matrix4): InterleavedBufferAttribute`

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

##### `getComponent(index: number, component: number): number`

<details><summary>Code</summary>

```ts
getComponent( index, component ) {

		let value = this.array[ index * this.data.stride + this.offset + component ];

		if ( this.normalized ) value = denormalize( value, this.array );

		return value;

	}
```
</details>

##### `setComponent(index: number, component: number, value: number): InterleavedBufferAttribute`

<details><summary>Code</summary>

```ts
setComponent( index, component, value ) {

		if ( this.normalized ) value = normalize( value, this.array );

		this.data.array[ index * this.data.stride + this.offset + component ] = value;

		return this;

	}
```
</details>

##### `setX(index: number, x: number): InterleavedBufferAttribute`

<details><summary>Code</summary>

```ts
setX( index, x ) {

		if ( this.normalized ) x = normalize( x, this.array );

		this.data.array[ index * this.data.stride + this.offset ] = x;

		return this;

	}
```
</details>

##### `setY(index: number, y: number): InterleavedBufferAttribute`

<details><summary>Code</summary>

```ts
setY( index, y ) {

		if ( this.normalized ) y = normalize( y, this.array );

		this.data.array[ index * this.data.stride + this.offset + 1 ] = y;

		return this;

	}
```
</details>

##### `setZ(index: number, z: number): InterleavedBufferAttribute`

<details><summary>Code</summary>

```ts
setZ( index, z ) {

		if ( this.normalized ) z = normalize( z, this.array );

		this.data.array[ index * this.data.stride + this.offset + 2 ] = z;

		return this;

	}
```
</details>

##### `setW(index: number, w: number): InterleavedBufferAttribute`

<details><summary>Code</summary>

```ts
setW( index, w ) {

		if ( this.normalized ) w = normalize( w, this.array );

		this.data.array[ index * this.data.stride + this.offset + 3 ] = w;

		return this;

	}
```
</details>

##### `getX(index: number): number`

<details><summary>Code</summary>

```ts
getX( index ) {

		let x = this.data.array[ index * this.data.stride + this.offset ];

		if ( this.normalized ) x = denormalize( x, this.array );

		return x;

	}
```
</details>

##### `getY(index: number): number`

<details><summary>Code</summary>

```ts
getY( index ) {

		let y = this.data.array[ index * this.data.stride + this.offset + 1 ];

		if ( this.normalized ) y = denormalize( y, this.array );

		return y;

	}
```
</details>

##### `getZ(index: number): number`

<details><summary>Code</summary>

```ts
getZ( index ) {

		let z = this.data.array[ index * this.data.stride + this.offset + 2 ];

		if ( this.normalized ) z = denormalize( z, this.array );

		return z;

	}
```
</details>

##### `getW(index: number): number`

<details><summary>Code</summary>

```ts
getW( index ) {

		let w = this.data.array[ index * this.data.stride + this.offset + 3 ];

		if ( this.normalized ) w = denormalize( w, this.array );

		return w;

	}
```
</details>

##### `setXY(index: number, x: number, y: number): InterleavedBufferAttribute`

<details><summary>Code</summary>

```ts
setXY( index, x, y ) {

		index = index * this.data.stride + this.offset;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );

		}

		this.data.array[ index + 0 ] = x;
		this.data.array[ index + 1 ] = y;

		return this;

	}
```
</details>

##### `setXYZ(index: number, x: number, y: number, z: number): InterleavedBufferAttribute`

<details><summary>Code</summary>

```ts
setXYZ( index, x, y, z ) {

		index = index * this.data.stride + this.offset;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );

		}

		this.data.array[ index + 0 ] = x;
		this.data.array[ index + 1 ] = y;
		this.data.array[ index + 2 ] = z;

		return this;

	}
```
</details>

##### `setXYZW(index: number, x: number, y: number, z: number, w: number): InterleavedBufferAttribute`

<details><summary>Code</summary>

```ts
setXYZW( index, x, y, z, w ) {

		index = index * this.data.stride + this.offset;

		if ( this.normalized ) {

			x = normalize( x, this.array );
			y = normalize( y, this.array );
			z = normalize( z, this.array );
			w = normalize( w, this.array );

		}

		this.data.array[ index + 0 ] = x;
		this.data.array[ index + 1 ] = y;
		this.data.array[ index + 2 ] = z;
		this.data.array[ index + 3 ] = w;

		return this;

	}
```
</details>

##### `clone(data: any): BufferAttribute | InterleavedBufferAttribute`

<details><summary>Code</summary>

```ts
clone( data ) {

		if ( data === undefined ) {

			console.log( 'THREE.InterleavedBufferAttribute.clone(): Cloning an interleaved buffer attribute will de-interleave buffer data.' );

			const array = [];

			for ( let i = 0; i < this.count; i ++ ) {

				const index = i * this.data.stride + this.offset;

				for ( let j = 0; j < this.itemSize; j ++ ) {

					array.push( this.data.array[ index + j ] );

				}

			}

			return new BufferAttribute( new this.array.constructor( array ), this.itemSize, this.normalized );

		} else {

			if ( data.interleavedBuffers === undefined ) {

				data.interleavedBuffers = {};

			}

			if ( data.interleavedBuffers[ this.data.uuid ] === undefined ) {

				data.interleavedBuffers[ this.data.uuid ] = this.data.clone( data );

			}

			return new InterleavedBufferAttribute( data.interleavedBuffers[ this.data.uuid ], this.itemSize, this.offset, this.normalized );

		}

	}
```
</details>

##### `toJSON(data: any): any`

<details><summary>Code</summary>

```ts
toJSON( data ) {

		if ( data === undefined ) {

			console.log( 'THREE.InterleavedBufferAttribute.toJSON(): Serializing an interleaved buffer attribute will de-interleave buffer data.' );

			const array = [];

			for ( let i = 0; i < this.count; i ++ ) {

				const index = i * this.data.stride + this.offset;

				for ( let j = 0; j < this.itemSize; j ++ ) {

					array.push( this.data.array[ index + j ] );

				}

			}

			// de-interleave data and save it as an ordinary buffer attribute for now

			return {
				itemSize: this.itemSize,
				type: this.array.constructor.name,
				array: array,
				normalized: this.normalized
			};

		} else {

			// save as true interleaved attribute

			if ( data.interleavedBuffers === undefined ) {

				data.interleavedBuffers = {};

			}

			if ( data.interleavedBuffers[ this.data.uuid ] === undefined ) {

				data.interleavedBuffers[ this.data.uuid ] = this.data.toJSON( data );

			}

			return {
				isInterleavedBufferAttribute: true,
				itemSize: this.itemSize,
				data: this.data.uuid,
				offset: this.offset,
				normalized: this.normalized
			};

		}

	}
```
</details>


---