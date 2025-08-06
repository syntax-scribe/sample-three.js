[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `UniformsGroup.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 14 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 37 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/UniformsGroup.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UniformBuffer` | `./UniformBuffer.js` |
| `GPU_CHUNK_BYTES` | `./Constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `buffer` | `TypedArray` | let/var | `this._buffer` | ✗ |
| `byteLength` | `number` | let/var | `this.byteLength` | ✗ |
| `bytesPerElement` | `number` | let/var | `this.bytesPerElement` | ✗ |
| `offset` | `number` | let/var | `0` | ✗ |
| `uniform` | `Uniform` | let/var | `this.uniforms[ i ]` | ✗ |
| `boundary` | `any` | let/var | `uniform.boundary` | ✗ |
| `itemSize` | `number` | let/var | `uniform.itemSize * bytesPerElement` | ✗ |
| `chunkOffset` | `number` | let/var | `offset % GPU_CHUNK_BYTES` | ✗ |
| `chunkPadding` | `number` | let/var | `chunkOffset % boundary` | ✗ |
| `chunkStart` | `number` | let/var | `chunkOffset + chunkPadding` | ✗ |
| `updated` | `boolean` | let/var | `false` | ✗ |
| `updated` | `boolean` | let/var | `false` | ✗ |
| `a` | `number[]` | let/var | `this.values` | ✗ |
| `offset` | `any` | let/var | `uniform.offset` | ✗ |
| `updated` | `boolean` | let/var | `false` | ✗ |
| `a` | `number[]` | let/var | `this.values` | ✗ |
| `offset` | `any` | let/var | `uniform.offset` | ✗ |
| `updated` | `boolean` | let/var | `false` | ✗ |
| `a` | `number[]` | let/var | `this.values` | ✗ |
| `offset` | `any` | let/var | `uniform.offset` | ✗ |
| `updated` | `boolean` | let/var | `false` | ✗ |
| `a` | `number[]` | let/var | `this.values` | ✗ |
| `offset` | `any` | let/var | `uniform.offset` | ✗ |
| `updated` | `boolean` | let/var | `false` | ✗ |
| `a` | `number[]` | let/var | `this.values` | ✗ |
| `offset` | `any` | let/var | `uniform.offset` | ✗ |
| `b` | `Float32Array<ArrayBufferLike>` | let/var | `this.buffer` | ✗ |
| `updated` | `boolean` | let/var | `false` | ✗ |
| `a` | `number[]` | let/var | `this.values` | ✗ |
| `e` | `any` | let/var | `uniform.getValue().elements` | ✗ |
| `offset` | `any` | let/var | `uniform.offset` | ✗ |
| `b` | `Float32Array<ArrayBufferLike>` | let/var | `this.buffer` | ✗ |
| `updated` | `boolean` | let/var | `false` | ✗ |
| `a` | `number[]` | let/var | `this.values` | ✗ |
| `e` | `any` | let/var | `uniform.getValue().elements` | ✗ |
| `offset` | `any` | let/var | `uniform.offset` | ✗ |
| `b` | `Float32Array<ArrayBufferLike>` | let/var | `this.buffer` | ✗ |


---

## Functions

### `UniformsGroup.addUniform(uniform: Uniform): UniformsGroup`

**JSDoc:**
```typescript
/**
	 * Adds a uniform to this group.
	 *
	 * @param {Uniform} uniform - The uniform to add.
	 * @return {UniformsGroup} A reference to this group.
	 */
```

**Parameters:**

- **`uniform`** `Uniform`

**Returns:** `UniformsGroup`

**Calls:**

- `this.uniforms.push`

<details><summary>Code</summary>

```typescript
addUniform( uniform ) {

		this.uniforms.push( uniform );

		return this;

	}
```
</details>

### `UniformsGroup.removeUniform(uniform: Uniform): UniformsGroup`

**JSDoc:**
```typescript
/**
	 * Removes a uniform from this group.
	 *
	 * @param {Uniform} uniform - The uniform to remove.
	 * @return {UniformsGroup} A reference to this group.
	 */
```

**Parameters:**

- **`uniform`** `Uniform`

**Returns:** `UniformsGroup`

**Calls:**

- `this.uniforms.indexOf`
- `this.uniforms.splice`

<details><summary>Code</summary>

```typescript
removeUniform( uniform ) {

		const index = this.uniforms.indexOf( uniform );

		if ( index !== - 1 ) {

			this.uniforms.splice( index, 1 );

		}

		return this;

	}
```
</details>

### `UniformsGroup.update(): boolean`

**JSDoc:**
```typescript
/**
	 * Updates this group by updating each uniform object of
	 * the internal uniform list. The uniform objects check if their
	 * values has actually changed so this method only returns
	 * `true` if there is a real value change.
	 *
	 * @return {boolean} Whether the uniforms have been updated and
	 * must be uploaded to the GPU.
	 */
```

**Returns:** `boolean`

**Calls:**

- `this.updateByType`

<details><summary>Code</summary>

```typescript
update() {

		let updated = false;

		for ( const uniform of this.uniforms ) {

			if ( this.updateByType( uniform ) === true ) {

				updated = true;

			}

		}

		return updated;

	}
```
</details>

### `UniformsGroup.updateByType(uniform: Uniform): boolean`

**JSDoc:**
```typescript
/**
	 * Updates a given uniform by calling an update method matching
	 * the uniforms type.
	 *
	 * @param {Uniform} uniform - The uniform to update.
	 * @return {boolean} Whether the uniform has been updated or not.
	 */
```

**Parameters:**

- **`uniform`** `Uniform`

**Returns:** `boolean`

**Calls:**

- `this.updateNumber`
- `this.updateVector2`
- `this.updateVector3`
- `this.updateVector4`
- `this.updateColor`
- `this.updateMatrix3`
- `this.updateMatrix4`
- `console.error`

<details><summary>Code</summary>

```typescript
updateByType( uniform ) {

		if ( uniform.isNumberUniform ) return this.updateNumber( uniform );
		if ( uniform.isVector2Uniform ) return this.updateVector2( uniform );
		if ( uniform.isVector3Uniform ) return this.updateVector3( uniform );
		if ( uniform.isVector4Uniform ) return this.updateVector4( uniform );
		if ( uniform.isColorUniform ) return this.updateColor( uniform );
		if ( uniform.isMatrix3Uniform ) return this.updateMatrix3( uniform );
		if ( uniform.isMatrix4Uniform ) return this.updateMatrix4( uniform );

		console.error( 'THREE.WebGPUUniformsGroup: Unsupported uniform type.', uniform );

	}
```
</details>

### `UniformsGroup.updateNumber(uniform: NumberUniform): boolean`

**JSDoc:**
```typescript
/**
	 * Updates a given Number uniform.
	 *
	 * @param {NumberUniform} uniform - The Number uniform.
	 * @return {boolean} Whether the uniform has been updated or not.
	 */
```

**Parameters:**

- **`uniform`** `NumberUniform`

**Returns:** `boolean`

**Calls:**

- `uniform.getValue`
- `uniform.getType`
- `this._getBufferForType`

<details><summary>Code</summary>

```typescript
updateNumber( uniform ) {

		let updated = false;

		const a = this.values;
		const v = uniform.getValue();
		const offset = uniform.offset;
		const type = uniform.getType();

		if ( a[ offset ] !== v ) {

			const b = this._getBufferForType( type );

			b[ offset ] = a[ offset ] = v;
			updated = true;

		}

		return updated;

	}
```
</details>

### `UniformsGroup.updateVector2(uniform: Vector2Uniform): boolean`

**JSDoc:**
```typescript
/**
	 * Updates a given Vector2 uniform.
	 *
	 * @param {Vector2Uniform} uniform - The Vector2 uniform.
	 * @return {boolean} Whether the uniform has been updated or not.
	 */
```

**Parameters:**

- **`uniform`** `Vector2Uniform`

**Returns:** `boolean`

**Calls:**

- `uniform.getValue`
- `uniform.getType`
- `this._getBufferForType`

<details><summary>Code</summary>

```typescript
updateVector2( uniform ) {

		let updated = false;

		const a = this.values;
		const v = uniform.getValue();
		const offset = uniform.offset;
		const type = uniform.getType();

		if ( a[ offset + 0 ] !== v.x || a[ offset + 1 ] !== v.y ) {

			const b = this._getBufferForType( type );

			b[ offset + 0 ] = a[ offset + 0 ] = v.x;
			b[ offset + 1 ] = a[ offset + 1 ] = v.y;

			updated = true;

		}

		return updated;

	}
```
</details>

### `UniformsGroup.updateVector3(uniform: Vector3Uniform): boolean`

**JSDoc:**
```typescript
/**
	 * Updates a given Vector3 uniform.
	 *
	 * @param {Vector3Uniform} uniform - The Vector3 uniform.
	 * @return {boolean} Whether the uniform has been updated or not.
	 */
```

**Parameters:**

- **`uniform`** `Vector3Uniform`

**Returns:** `boolean`

**Calls:**

- `uniform.getValue`
- `uniform.getType`
- `this._getBufferForType`

<details><summary>Code</summary>

```typescript
updateVector3( uniform ) {

		let updated = false;

		const a = this.values;
		const v = uniform.getValue();
		const offset = uniform.offset;
		const type = uniform.getType();

		if ( a[ offset + 0 ] !== v.x || a[ offset + 1 ] !== v.y || a[ offset + 2 ] !== v.z ) {

			const b = this._getBufferForType( type );

			b[ offset + 0 ] = a[ offset + 0 ] = v.x;
			b[ offset + 1 ] = a[ offset + 1 ] = v.y;
			b[ offset + 2 ] = a[ offset + 2 ] = v.z;

			updated = true;

		}

		return updated;

	}
```
</details>

### `UniformsGroup.updateVector4(uniform: Vector4Uniform): boolean`

**JSDoc:**
```typescript
/**
	 * Updates a given Vector4 uniform.
	 *
	 * @param {Vector4Uniform} uniform - The Vector4 uniform.
	 * @return {boolean} Whether the uniform has been updated or not.
	 */
```

**Parameters:**

- **`uniform`** `Vector4Uniform`

**Returns:** `boolean`

**Calls:**

- `uniform.getValue`
- `uniform.getType`
- `this._getBufferForType`

<details><summary>Code</summary>

```typescript
updateVector4( uniform ) {

		let updated = false;

		const a = this.values;
		const v = uniform.getValue();
		const offset = uniform.offset;
		const type = uniform.getType();

		if ( a[ offset + 0 ] !== v.x || a[ offset + 1 ] !== v.y || a[ offset + 2 ] !== v.z || a[ offset + 4 ] !== v.w ) {

			const b = this._getBufferForType( type );

			b[ offset + 0 ] = a[ offset + 0 ] = v.x;
			b[ offset + 1 ] = a[ offset + 1 ] = v.y;
			b[ offset + 2 ] = a[ offset + 2 ] = v.z;
			b[ offset + 3 ] = a[ offset + 3 ] = v.w;

			updated = true;

		}

		return updated;

	}
```
</details>

### `UniformsGroup.updateColor(uniform: ColorUniform): boolean`

**JSDoc:**
```typescript
/**
	 * Updates a given Color uniform.
	 *
	 * @param {ColorUniform} uniform - The Color uniform.
	 * @return {boolean} Whether the uniform has been updated or not.
	 */
```

**Parameters:**

- **`uniform`** `ColorUniform`

**Returns:** `boolean`

**Calls:**

- `uniform.getValue`

<details><summary>Code</summary>

```typescript
updateColor( uniform ) {

		let updated = false;

		const a = this.values;
		const c = uniform.getValue();
		const offset = uniform.offset;

		if ( a[ offset + 0 ] !== c.r || a[ offset + 1 ] !== c.g || a[ offset + 2 ] !== c.b ) {

			const b = this.buffer;

			b[ offset + 0 ] = a[ offset + 0 ] = c.r;
			b[ offset + 1 ] = a[ offset + 1 ] = c.g;
			b[ offset + 2 ] = a[ offset + 2 ] = c.b;

			updated = true;

		}

		return updated;

	}
```
</details>

### `UniformsGroup.updateMatrix3(uniform: Matrix3Uniform): boolean`

**JSDoc:**
```typescript
/**
	 * Updates a given Matrix3 uniform.
	 *
	 * @param {Matrix3Uniform} uniform - The Matrix3 uniform.
	 * @return {boolean} Whether the uniform has been updated or not.
	 */
```

**Parameters:**

- **`uniform`** `Matrix3Uniform`

**Returns:** `boolean`

**Calls:**

- `uniform.getValue`

<details><summary>Code</summary>

```typescript
updateMatrix3( uniform ) {

		let updated = false;

		const a = this.values;
		const e = uniform.getValue().elements;
		const offset = uniform.offset;

		if ( a[ offset + 0 ] !== e[ 0 ] || a[ offset + 1 ] !== e[ 1 ] || a[ offset + 2 ] !== e[ 2 ] ||
			a[ offset + 4 ] !== e[ 3 ] || a[ offset + 5 ] !== e[ 4 ] || a[ offset + 6 ] !== e[ 5 ] ||
			a[ offset + 8 ] !== e[ 6 ] || a[ offset + 9 ] !== e[ 7 ] || a[ offset + 10 ] !== e[ 8 ] ) {

			const b = this.buffer;

			b[ offset + 0 ] = a[ offset + 0 ] = e[ 0 ];
			b[ offset + 1 ] = a[ offset + 1 ] = e[ 1 ];
			b[ offset + 2 ] = a[ offset + 2 ] = e[ 2 ];
			b[ offset + 4 ] = a[ offset + 4 ] = e[ 3 ];
			b[ offset + 5 ] = a[ offset + 5 ] = e[ 4 ];
			b[ offset + 6 ] = a[ offset + 6 ] = e[ 5 ];
			b[ offset + 8 ] = a[ offset + 8 ] = e[ 6 ];
			b[ offset + 9 ] = a[ offset + 9 ] = e[ 7 ];
			b[ offset + 10 ] = a[ offset + 10 ] = e[ 8 ];

			updated = true;

		}

		return updated;

	}
```
</details>

### `UniformsGroup.updateMatrix4(uniform: Matrix4Uniform): boolean`

**JSDoc:**
```typescript
/**
	 * Updates a given Matrix4 uniform.
	 *
	 * @param {Matrix4Uniform} uniform - The Matrix4 uniform.
	 * @return {boolean} Whether the uniform has been updated or not.
	 */
```

**Parameters:**

- **`uniform`** `Matrix4Uniform`

**Returns:** `boolean`

**Calls:**

- `uniform.getValue`
- `arraysEqual`
- `b.set`
- `setArray`

<details><summary>Code</summary>

```typescript
updateMatrix4( uniform ) {

		let updated = false;

		const a = this.values;
		const e = uniform.getValue().elements;
		const offset = uniform.offset;

		if ( arraysEqual( a, e, offset ) === false ) {

			const b = this.buffer;
			b.set( e, offset );
			setArray( a, e, offset );
			updated = true;

		}

		return updated;

	}
```
</details>

### `UniformsGroup._getBufferForType(type: string): TypedArray`

**JSDoc:**
```typescript
/**
	 * Returns a typed array that matches the given data type.
	 *
	 * @param {string} type - The data type.
	 * @return {TypedArray} The typed array.
	 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `TypedArray`

<details><summary>Code</summary>

```typescript
_getBufferForType( type ) {

		if ( type === 'int' || type === 'ivec2' || type === 'ivec3' || type === 'ivec4' ) return new Int32Array( this.buffer.buffer );
		if ( type === 'uint' || type === 'uvec2' || type === 'uvec3' || type === 'uvec4' ) return new Uint32Array( this.buffer.buffer );
		return this.buffer;

	}
```
</details>

### `setArray(a: TypedArray, b: TypedArray, offset: number): void`

**JSDoc:**
```typescript
/**
 * Sets the values of the second array to the first array.
 *
 * @private
 * @param {TypedArray} a - The first array.
 * @param {TypedArray} b - The second array.
 * @param {number} offset - An index offset for the first array.
 */
```

**Parameters:**

- **`a`** `TypedArray`
- **`b`** `TypedArray`
- **`offset`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function setArray( a, b, offset ) {

	for ( let i = 0, l = b.length; i < l; i ++ ) {

		a[ offset + i ] = b[ i ];

	}

}
```
</details>

### `arraysEqual(a: TypedArray, b: TypedArray, offset: number): boolean`

**JSDoc:**
```typescript
/**
 * Returns `true` if the given arrays are equal.
 *
 * @private
 * @param {TypedArray} a - The first array.
 * @param {TypedArray} b - The second array.
 * @param {number} offset - An index offset for the first array.
 * @return {boolean} Whether the given arrays are equal or not.
 */
```

**Parameters:**

- **`a`** `TypedArray`
- **`b`** `TypedArray`
- **`offset`** `number`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function arraysEqual( a, b, offset ) {

	for ( let i = 0, l = b.length; i < l; i ++ ) {

		if ( a[ offset + i ] !== b[ i ] ) return false;

	}

	return true;

}
```
</details>


---

## Classes

### `UniformsGroup`

<details><summary>Class Code</summary>

```ts
class UniformsGroup extends UniformBuffer {

	/**
	 * Constructs a new uniforms group.
	 *
	 * @param {string} name - The group's name.
	 */
	constructor( name ) {

		super( name );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isUniformsGroup = true;

		/**
		 * An array with the raw uniform values.
		 *
		 * @private
		 * @type {?Array<number>}
		 * @default null
		 */
		this._values = null;

		/**
		 * An array of uniform objects.
		 *
		 * The order of uniforms in this array must match the order of uniforms in the shader.
		 *
		 * @type {Array<Uniform>}
		 */
		this.uniforms = [];

	}

	/**
	 * Adds a uniform to this group.
	 *
	 * @param {Uniform} uniform - The uniform to add.
	 * @return {UniformsGroup} A reference to this group.
	 */
	addUniform( uniform ) {

		this.uniforms.push( uniform );

		return this;

	}

	/**
	 * Removes a uniform from this group.
	 *
	 * @param {Uniform} uniform - The uniform to remove.
	 * @return {UniformsGroup} A reference to this group.
	 */
	removeUniform( uniform ) {

		const index = this.uniforms.indexOf( uniform );

		if ( index !== - 1 ) {

			this.uniforms.splice( index, 1 );

		}

		return this;

	}

	/**
	 * An array with the raw uniform values.
	 *
	 * @type {Array<number>}
	 */
	get values() {

		if ( this._values === null ) {

			this._values = Array.from( this.buffer );

		}

		return this._values;

	}

	/**
	 * A Float32 array buffer with the uniform values.
	 *
	 * @type {Float32Array}
	 */
	get buffer() {

		let buffer = this._buffer;

		if ( buffer === null ) {

			const byteLength = this.byteLength;

			buffer = new Float32Array( new ArrayBuffer( byteLength ) );

			this._buffer = buffer;

		}

		return buffer;

	}

	/**
	 * The byte length of the buffer with correct buffer alignment.
	 *
	 * @type {number}
	 */
	get byteLength() {

		const bytesPerElement = this.bytesPerElement;

		let offset = 0; // global buffer offset in bytes

		for ( let i = 0, l = this.uniforms.length; i < l; i ++ ) {

			const uniform = this.uniforms[ i ];

			const boundary = uniform.boundary;
			const itemSize = uniform.itemSize * bytesPerElement; // size of the uniform in bytes

			const chunkOffset = offset % GPU_CHUNK_BYTES; // offset in the current chunk
			const chunkPadding = chunkOffset % boundary; // required padding to match boundary
			const chunkStart = chunkOffset + chunkPadding; // start position in the current chunk for the data

			offset += chunkPadding;

			// Check for chunk overflow
			if ( chunkStart !== 0 && ( GPU_CHUNK_BYTES - chunkStart ) < itemSize ) {

				// Add padding to the end of the chunk
				offset += ( GPU_CHUNK_BYTES - chunkStart );

			}

			uniform.offset = offset / bytesPerElement;

			offset += itemSize;

		}

		return Math.ceil( offset / GPU_CHUNK_BYTES ) * GPU_CHUNK_BYTES;

	}

	/**
	 * Updates this group by updating each uniform object of
	 * the internal uniform list. The uniform objects check if their
	 * values has actually changed so this method only returns
	 * `true` if there is a real value change.
	 *
	 * @return {boolean} Whether the uniforms have been updated and
	 * must be uploaded to the GPU.
	 */
	update() {

		let updated = false;

		for ( const uniform of this.uniforms ) {

			if ( this.updateByType( uniform ) === true ) {

				updated = true;

			}

		}

		return updated;

	}

	/**
	 * Updates a given uniform by calling an update method matching
	 * the uniforms type.
	 *
	 * @param {Uniform} uniform - The uniform to update.
	 * @return {boolean} Whether the uniform has been updated or not.
	 */
	updateByType( uniform ) {

		if ( uniform.isNumberUniform ) return this.updateNumber( uniform );
		if ( uniform.isVector2Uniform ) return this.updateVector2( uniform );
		if ( uniform.isVector3Uniform ) return this.updateVector3( uniform );
		if ( uniform.isVector4Uniform ) return this.updateVector4( uniform );
		if ( uniform.isColorUniform ) return this.updateColor( uniform );
		if ( uniform.isMatrix3Uniform ) return this.updateMatrix3( uniform );
		if ( uniform.isMatrix4Uniform ) return this.updateMatrix4( uniform );

		console.error( 'THREE.WebGPUUniformsGroup: Unsupported uniform type.', uniform );

	}

	/**
	 * Updates a given Number uniform.
	 *
	 * @param {NumberUniform} uniform - The Number uniform.
	 * @return {boolean} Whether the uniform has been updated or not.
	 */
	updateNumber( uniform ) {

		let updated = false;

		const a = this.values;
		const v = uniform.getValue();
		const offset = uniform.offset;
		const type = uniform.getType();

		if ( a[ offset ] !== v ) {

			const b = this._getBufferForType( type );

			b[ offset ] = a[ offset ] = v;
			updated = true;

		}

		return updated;

	}

	/**
	 * Updates a given Vector2 uniform.
	 *
	 * @param {Vector2Uniform} uniform - The Vector2 uniform.
	 * @return {boolean} Whether the uniform has been updated or not.
	 */
	updateVector2( uniform ) {

		let updated = false;

		const a = this.values;
		const v = uniform.getValue();
		const offset = uniform.offset;
		const type = uniform.getType();

		if ( a[ offset + 0 ] !== v.x || a[ offset + 1 ] !== v.y ) {

			const b = this._getBufferForType( type );

			b[ offset + 0 ] = a[ offset + 0 ] = v.x;
			b[ offset + 1 ] = a[ offset + 1 ] = v.y;

			updated = true;

		}

		return updated;

	}

	/**
	 * Updates a given Vector3 uniform.
	 *
	 * @param {Vector3Uniform} uniform - The Vector3 uniform.
	 * @return {boolean} Whether the uniform has been updated or not.
	 */
	updateVector3( uniform ) {

		let updated = false;

		const a = this.values;
		const v = uniform.getValue();
		const offset = uniform.offset;
		const type = uniform.getType();

		if ( a[ offset + 0 ] !== v.x || a[ offset + 1 ] !== v.y || a[ offset + 2 ] !== v.z ) {

			const b = this._getBufferForType( type );

			b[ offset + 0 ] = a[ offset + 0 ] = v.x;
			b[ offset + 1 ] = a[ offset + 1 ] = v.y;
			b[ offset + 2 ] = a[ offset + 2 ] = v.z;

			updated = true;

		}

		return updated;

	}

	/**
	 * Updates a given Vector4 uniform.
	 *
	 * @param {Vector4Uniform} uniform - The Vector4 uniform.
	 * @return {boolean} Whether the uniform has been updated or not.
	 */
	updateVector4( uniform ) {

		let updated = false;

		const a = this.values;
		const v = uniform.getValue();
		const offset = uniform.offset;
		const type = uniform.getType();

		if ( a[ offset + 0 ] !== v.x || a[ offset + 1 ] !== v.y || a[ offset + 2 ] !== v.z || a[ offset + 4 ] !== v.w ) {

			const b = this._getBufferForType( type );

			b[ offset + 0 ] = a[ offset + 0 ] = v.x;
			b[ offset + 1 ] = a[ offset + 1 ] = v.y;
			b[ offset + 2 ] = a[ offset + 2 ] = v.z;
			b[ offset + 3 ] = a[ offset + 3 ] = v.w;

			updated = true;

		}

		return updated;

	}

	/**
	 * Updates a given Color uniform.
	 *
	 * @param {ColorUniform} uniform - The Color uniform.
	 * @return {boolean} Whether the uniform has been updated or not.
	 */
	updateColor( uniform ) {

		let updated = false;

		const a = this.values;
		const c = uniform.getValue();
		const offset = uniform.offset;

		if ( a[ offset + 0 ] !== c.r || a[ offset + 1 ] !== c.g || a[ offset + 2 ] !== c.b ) {

			const b = this.buffer;

			b[ offset + 0 ] = a[ offset + 0 ] = c.r;
			b[ offset + 1 ] = a[ offset + 1 ] = c.g;
			b[ offset + 2 ] = a[ offset + 2 ] = c.b;

			updated = true;

		}

		return updated;

	}

	/**
	 * Updates a given Matrix3 uniform.
	 *
	 * @param {Matrix3Uniform} uniform - The Matrix3 uniform.
	 * @return {boolean} Whether the uniform has been updated or not.
	 */
	updateMatrix3( uniform ) {

		let updated = false;

		const a = this.values;
		const e = uniform.getValue().elements;
		const offset = uniform.offset;

		if ( a[ offset + 0 ] !== e[ 0 ] || a[ offset + 1 ] !== e[ 1 ] || a[ offset + 2 ] !== e[ 2 ] ||
			a[ offset + 4 ] !== e[ 3 ] || a[ offset + 5 ] !== e[ 4 ] || a[ offset + 6 ] !== e[ 5 ] ||
			a[ offset + 8 ] !== e[ 6 ] || a[ offset + 9 ] !== e[ 7 ] || a[ offset + 10 ] !== e[ 8 ] ) {

			const b = this.buffer;

			b[ offset + 0 ] = a[ offset + 0 ] = e[ 0 ];
			b[ offset + 1 ] = a[ offset + 1 ] = e[ 1 ];
			b[ offset + 2 ] = a[ offset + 2 ] = e[ 2 ];
			b[ offset + 4 ] = a[ offset + 4 ] = e[ 3 ];
			b[ offset + 5 ] = a[ offset + 5 ] = e[ 4 ];
			b[ offset + 6 ] = a[ offset + 6 ] = e[ 5 ];
			b[ offset + 8 ] = a[ offset + 8 ] = e[ 6 ];
			b[ offset + 9 ] = a[ offset + 9 ] = e[ 7 ];
			b[ offset + 10 ] = a[ offset + 10 ] = e[ 8 ];

			updated = true;

		}

		return updated;

	}

	/**
	 * Updates a given Matrix4 uniform.
	 *
	 * @param {Matrix4Uniform} uniform - The Matrix4 uniform.
	 * @return {boolean} Whether the uniform has been updated or not.
	 */
	updateMatrix4( uniform ) {

		let updated = false;

		const a = this.values;
		const e = uniform.getValue().elements;
		const offset = uniform.offset;

		if ( arraysEqual( a, e, offset ) === false ) {

			const b = this.buffer;
			b.set( e, offset );
			setArray( a, e, offset );
			updated = true;

		}

		return updated;

	}

	/**
	 * Returns a typed array that matches the given data type.
	 *
	 * @param {string} type - The data type.
	 * @return {TypedArray} The typed array.
	 */
	_getBufferForType( type ) {

		if ( type === 'int' || type === 'ivec2' || type === 'ivec3' || type === 'ivec4' ) return new Int32Array( this.buffer.buffer );
		if ( type === 'uint' || type === 'uvec2' || type === 'uvec3' || type === 'uvec4' ) return new Uint32Array( this.buffer.buffer );
		return this.buffer;

	}

}
```
</details>

#### Methods

##### `addUniform(uniform: Uniform): UniformsGroup`

<details><summary>Code</summary>

```ts
addUniform( uniform ) {

		this.uniforms.push( uniform );

		return this;

	}
```
</details>

##### `removeUniform(uniform: Uniform): UniformsGroup`

<details><summary>Code</summary>

```ts
removeUniform( uniform ) {

		const index = this.uniforms.indexOf( uniform );

		if ( index !== - 1 ) {

			this.uniforms.splice( index, 1 );

		}

		return this;

	}
```
</details>

##### `update(): boolean`

<details><summary>Code</summary>

```ts
update() {

		let updated = false;

		for ( const uniform of this.uniforms ) {

			if ( this.updateByType( uniform ) === true ) {

				updated = true;

			}

		}

		return updated;

	}
```
</details>

##### `updateByType(uniform: Uniform): boolean`

<details><summary>Code</summary>

```ts
updateByType( uniform ) {

		if ( uniform.isNumberUniform ) return this.updateNumber( uniform );
		if ( uniform.isVector2Uniform ) return this.updateVector2( uniform );
		if ( uniform.isVector3Uniform ) return this.updateVector3( uniform );
		if ( uniform.isVector4Uniform ) return this.updateVector4( uniform );
		if ( uniform.isColorUniform ) return this.updateColor( uniform );
		if ( uniform.isMatrix3Uniform ) return this.updateMatrix3( uniform );
		if ( uniform.isMatrix4Uniform ) return this.updateMatrix4( uniform );

		console.error( 'THREE.WebGPUUniformsGroup: Unsupported uniform type.', uniform );

	}
```
</details>

##### `updateNumber(uniform: NumberUniform): boolean`

<details><summary>Code</summary>

```ts
updateNumber( uniform ) {

		let updated = false;

		const a = this.values;
		const v = uniform.getValue();
		const offset = uniform.offset;
		const type = uniform.getType();

		if ( a[ offset ] !== v ) {

			const b = this._getBufferForType( type );

			b[ offset ] = a[ offset ] = v;
			updated = true;

		}

		return updated;

	}
```
</details>

##### `updateVector2(uniform: Vector2Uniform): boolean`

<details><summary>Code</summary>

```ts
updateVector2( uniform ) {

		let updated = false;

		const a = this.values;
		const v = uniform.getValue();
		const offset = uniform.offset;
		const type = uniform.getType();

		if ( a[ offset + 0 ] !== v.x || a[ offset + 1 ] !== v.y ) {

			const b = this._getBufferForType( type );

			b[ offset + 0 ] = a[ offset + 0 ] = v.x;
			b[ offset + 1 ] = a[ offset + 1 ] = v.y;

			updated = true;

		}

		return updated;

	}
```
</details>

##### `updateVector3(uniform: Vector3Uniform): boolean`

<details><summary>Code</summary>

```ts
updateVector3( uniform ) {

		let updated = false;

		const a = this.values;
		const v = uniform.getValue();
		const offset = uniform.offset;
		const type = uniform.getType();

		if ( a[ offset + 0 ] !== v.x || a[ offset + 1 ] !== v.y || a[ offset + 2 ] !== v.z ) {

			const b = this._getBufferForType( type );

			b[ offset + 0 ] = a[ offset + 0 ] = v.x;
			b[ offset + 1 ] = a[ offset + 1 ] = v.y;
			b[ offset + 2 ] = a[ offset + 2 ] = v.z;

			updated = true;

		}

		return updated;

	}
```
</details>

##### `updateVector4(uniform: Vector4Uniform): boolean`

<details><summary>Code</summary>

```ts
updateVector4( uniform ) {

		let updated = false;

		const a = this.values;
		const v = uniform.getValue();
		const offset = uniform.offset;
		const type = uniform.getType();

		if ( a[ offset + 0 ] !== v.x || a[ offset + 1 ] !== v.y || a[ offset + 2 ] !== v.z || a[ offset + 4 ] !== v.w ) {

			const b = this._getBufferForType( type );

			b[ offset + 0 ] = a[ offset + 0 ] = v.x;
			b[ offset + 1 ] = a[ offset + 1 ] = v.y;
			b[ offset + 2 ] = a[ offset + 2 ] = v.z;
			b[ offset + 3 ] = a[ offset + 3 ] = v.w;

			updated = true;

		}

		return updated;

	}
```
</details>

##### `updateColor(uniform: ColorUniform): boolean`

<details><summary>Code</summary>

```ts
updateColor( uniform ) {

		let updated = false;

		const a = this.values;
		const c = uniform.getValue();
		const offset = uniform.offset;

		if ( a[ offset + 0 ] !== c.r || a[ offset + 1 ] !== c.g || a[ offset + 2 ] !== c.b ) {

			const b = this.buffer;

			b[ offset + 0 ] = a[ offset + 0 ] = c.r;
			b[ offset + 1 ] = a[ offset + 1 ] = c.g;
			b[ offset + 2 ] = a[ offset + 2 ] = c.b;

			updated = true;

		}

		return updated;

	}
```
</details>

##### `updateMatrix3(uniform: Matrix3Uniform): boolean`

<details><summary>Code</summary>

```ts
updateMatrix3( uniform ) {

		let updated = false;

		const a = this.values;
		const e = uniform.getValue().elements;
		const offset = uniform.offset;

		if ( a[ offset + 0 ] !== e[ 0 ] || a[ offset + 1 ] !== e[ 1 ] || a[ offset + 2 ] !== e[ 2 ] ||
			a[ offset + 4 ] !== e[ 3 ] || a[ offset + 5 ] !== e[ 4 ] || a[ offset + 6 ] !== e[ 5 ] ||
			a[ offset + 8 ] !== e[ 6 ] || a[ offset + 9 ] !== e[ 7 ] || a[ offset + 10 ] !== e[ 8 ] ) {

			const b = this.buffer;

			b[ offset + 0 ] = a[ offset + 0 ] = e[ 0 ];
			b[ offset + 1 ] = a[ offset + 1 ] = e[ 1 ];
			b[ offset + 2 ] = a[ offset + 2 ] = e[ 2 ];
			b[ offset + 4 ] = a[ offset + 4 ] = e[ 3 ];
			b[ offset + 5 ] = a[ offset + 5 ] = e[ 4 ];
			b[ offset + 6 ] = a[ offset + 6 ] = e[ 5 ];
			b[ offset + 8 ] = a[ offset + 8 ] = e[ 6 ];
			b[ offset + 9 ] = a[ offset + 9 ] = e[ 7 ];
			b[ offset + 10 ] = a[ offset + 10 ] = e[ 8 ];

			updated = true;

		}

		return updated;

	}
```
</details>

##### `updateMatrix4(uniform: Matrix4Uniform): boolean`

<details><summary>Code</summary>

```ts
updateMatrix4( uniform ) {

		let updated = false;

		const a = this.values;
		const e = uniform.getValue().elements;
		const offset = uniform.offset;

		if ( arraysEqual( a, e, offset ) === false ) {

			const b = this.buffer;
			b.set( e, offset );
			setArray( a, e, offset );
			updated = true;

		}

		return updated;

	}
```
</details>

##### `_getBufferForType(type: string): TypedArray`

<details><summary>Code</summary>

```ts
_getBufferForType( type ) {

		if ( type === 'int' || type === 'ivec2' || type === 'ivec3' || type === 'ivec4' ) return new Int32Array( this.buffer.buffer );
		if ( type === 'uint' || type === 'uvec2' || type === 'uvec3' || type === 'uvec4' ) return new Uint32Array( this.buffer.buffer );
		return this.buffer;

	}
```
</details>


---