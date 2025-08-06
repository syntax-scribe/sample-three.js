[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLUniforms.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 51 |
| 🧱 Classes | 4 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 62 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLUniforms.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `CubeTexture` | `../../textures/CubeTexture.js` |
| `Texture` | `../../textures/Texture.js` |
| `DataArrayTexture` | `../../textures/DataArrayTexture.js` |
| `Data3DTexture` | `../../textures/Data3DTexture.js` |
| `DepthTexture` | `../../textures/DepthTexture.js` |
| `LessEqualCompare` | `../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `emptyTexture` | `Texture` | let/var | `new Texture()` | ✗ |
| `emptyShadowTexture` | `DepthTexture` | let/var | `new DepthTexture( 1, 1 )` | ✗ |
| `emptyArrayTexture` | `DataArrayTexture` | let/var | `new DataArrayTexture()` | ✗ |
| `empty3dTexture` | `Data3DTexture` | let/var | `new Data3DTexture()` | ✗ |
| `emptyCubeTexture` | `CubeTexture` | let/var | `new CubeTexture()` | ✗ |
| `arrayCacheF32` | `any[]` | let/var | `[]` | ✗ |
| `arrayCacheI32` | `any[]` | let/var | `[]` | ✗ |
| `mat4array` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( 16 )` | ✗ |
| `mat3array` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( 9 )` | ✗ |
| `mat2array` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( 4 )` | ✗ |
| `firstElem` | `any` | let/var | `array[ 0 ]` | ✗ |
| `n` | `number` | let/var | `nBlocks * blockSize` | ✗ |
| `r` | `any` | let/var | `arrayCacheF32[ n ]` | ✗ |
| `r` | `any` | let/var | `arrayCacheI32[ n ]` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `elements` | `any` | let/var | `v.elements` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `elements` | `any` | let/var | `v.elements` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `elements` | `any` | let/var | `v.elements` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `emptyTexture2D` | `any` | let/var | `*not shown*` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `n` | `any` | let/var | `v.length` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `n` | `any` | let/var | `v.length` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `n` | `any` | let/var | `v.length` | ✗ |
| `cache` | `any` | let/var | `this.cache` | ✗ |
| `n` | `any` | let/var | `v.length` | ✗ |
| `seq` | `any[]` | let/var | `this.seq` | ✗ |
| `u` | `any` | let/var | `seq[ i ]` | ✗ |
| `RePathPart` | `RegExp` | let/var | `/(\w+)(\])?(\[\|\.)?/g` | ✗ |
| `path` | `any` | let/var | `activeInfo.name` | ✗ |
| `pathLength` | `any` | let/var | `path.length` | ✗ |
| `matchEnd` | `number` | let/var | `RePathPart.lastIndex` | ✗ |
| `id` | `string` | let/var | `match[ 1 ]` | ✗ |
| `idIsIndex` | `boolean` | let/var | `match[ 2 ] === ']'` | ✗ |
| `subscript` | `string` | let/var | `match[ 3 ]` | ✗ |
| `map` | `any` | let/var | `container.map` | ✗ |
| `next` | `any` | let/var | `map[ id ]` | ✗ |
| `u` | `any` | let/var | `this.map[ name ]` | ✗ |
| `v` | `any` | let/var | `object[ name ]` | ✗ |
| `u` | `any` | let/var | `seq[ i ]` | ✗ |
| `v` | `any` | let/var | `values[ u.id ]` | ✗ |
| `r` | `any[]` | let/var | `[]` | ✗ |
| `u` | `any` | let/var | `seq[ i ]` | ✗ |


---

## Functions

### `flatten(array: any, nBlocks: any, blockSize: any): any`

**Parameters:**

- **`array`** `any`
- **`nBlocks`** `any`
- **`blockSize`** `any`

**Returns:** `any`

**Calls:**

- `firstElem.toArray`
- `array[ i ].toArray`

**Internal Comments:**
```
// unoptimized: ! isNaN( firstElem ) (x2)
// see http://jacksondunstan.com/articles/983 (x2)
```

<details><summary>Code</summary>

```typescript
function flatten( array, nBlocks, blockSize ) {

	const firstElem = array[ 0 ];

	if ( firstElem <= 0 || firstElem > 0 ) return array;
	// unoptimized: ! isNaN( firstElem )
	// see http://jacksondunstan.com/articles/983

	const n = nBlocks * blockSize;
	let r = arrayCacheF32[ n ];

	if ( r === undefined ) {

		r = new Float32Array( n );
		arrayCacheF32[ n ] = r;

	}

	if ( nBlocks !== 0 ) {

		firstElem.toArray( r, 0 );

		for ( let i = 1, offset = 0; i !== nBlocks; ++ i ) {

			offset += blockSize;
			array[ i ].toArray( r, offset );

		}

	}

	return r;

}
```
</details>

### `arraysEqual(a: any, b: any): boolean`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function arraysEqual( a, b ) {

	if ( a.length !== b.length ) return false;

	for ( let i = 0, l = a.length; i < l; i ++ ) {

		if ( a[ i ] !== b[ i ] ) return false;

	}

	return true;

}
```
</details>

### `copyArray(a: any, b: any): void`

**Parameters:**

- **`a`** `any`
- **`b`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function copyArray( a, b ) {

	for ( let i = 0, l = b.length; i < l; i ++ ) {

		a[ i ] = b[ i ];

	}

}
```
</details>

### `allocTexUnits(textures: any, n: any): any`

**Parameters:**

- **`textures`** `any`
- **`n`** `any`

**Returns:** `any`

**Calls:**

- `textures.allocateTextureUnit`

<details><summary>Code</summary>

```typescript
function allocTexUnits( textures, n ) {

	let r = arrayCacheI32[ n ];

	if ( r === undefined ) {

		r = new Int32Array( n );
		arrayCacheI32[ n ] = r;

	}

	for ( let i = 0; i !== n; ++ i ) {

		r[ i ] = textures.allocateTextureUnit();

	}

	return r;

}
```
</details>

### `setValueV1f(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform1f`

<details><summary>Code</summary>

```typescript
function setValueV1f( gl, v ) {

	const cache = this.cache;

	if ( cache[ 0 ] === v ) return;

	gl.uniform1f( this.addr, v );

	cache[ 0 ] = v;

}
```
</details>

### `setValueV2f(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform2f`
- `arraysEqual`
- `gl.uniform2fv`
- `copyArray`

<details><summary>Code</summary>

```typescript
function setValueV2f( gl, v ) {

	const cache = this.cache;

	if ( v.x !== undefined ) {

		if ( cache[ 0 ] !== v.x || cache[ 1 ] !== v.y ) {

			gl.uniform2f( this.addr, v.x, v.y );

			cache[ 0 ] = v.x;
			cache[ 1 ] = v.y;

		}

	} else {

		if ( arraysEqual( cache, v ) ) return;

		gl.uniform2fv( this.addr, v );

		copyArray( cache, v );

	}

}
```
</details>

### `setValueV3f(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform3f`
- `arraysEqual`
- `gl.uniform3fv`
- `copyArray`

<details><summary>Code</summary>

```typescript
function setValueV3f( gl, v ) {

	const cache = this.cache;

	if ( v.x !== undefined ) {

		if ( cache[ 0 ] !== v.x || cache[ 1 ] !== v.y || cache[ 2 ] !== v.z ) {

			gl.uniform3f( this.addr, v.x, v.y, v.z );

			cache[ 0 ] = v.x;
			cache[ 1 ] = v.y;
			cache[ 2 ] = v.z;

		}

	} else if ( v.r !== undefined ) {

		if ( cache[ 0 ] !== v.r || cache[ 1 ] !== v.g || cache[ 2 ] !== v.b ) {

			gl.uniform3f( this.addr, v.r, v.g, v.b );

			cache[ 0 ] = v.r;
			cache[ 1 ] = v.g;
			cache[ 2 ] = v.b;

		}

	} else {

		if ( arraysEqual( cache, v ) ) return;

		gl.uniform3fv( this.addr, v );

		copyArray( cache, v );

	}

}
```
</details>

### `setValueV4f(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform4f`
- `arraysEqual`
- `gl.uniform4fv`
- `copyArray`

<details><summary>Code</summary>

```typescript
function setValueV4f( gl, v ) {

	const cache = this.cache;

	if ( v.x !== undefined ) {

		if ( cache[ 0 ] !== v.x || cache[ 1 ] !== v.y || cache[ 2 ] !== v.z || cache[ 3 ] !== v.w ) {

			gl.uniform4f( this.addr, v.x, v.y, v.z, v.w );

			cache[ 0 ] = v.x;
			cache[ 1 ] = v.y;
			cache[ 2 ] = v.z;
			cache[ 3 ] = v.w;

		}

	} else {

		if ( arraysEqual( cache, v ) ) return;

		gl.uniform4fv( this.addr, v );

		copyArray( cache, v );

	}

}
```
</details>

### `setValueM2(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `arraysEqual`
- `gl.uniformMatrix2fv`
- `copyArray`
- `mat2array.set`

<details><summary>Code</summary>

```typescript
function setValueM2( gl, v ) {

	const cache = this.cache;
	const elements = v.elements;

	if ( elements === undefined ) {

		if ( arraysEqual( cache, v ) ) return;

		gl.uniformMatrix2fv( this.addr, false, v );

		copyArray( cache, v );

	} else {

		if ( arraysEqual( cache, elements ) ) return;

		mat2array.set( elements );

		gl.uniformMatrix2fv( this.addr, false, mat2array );

		copyArray( cache, elements );

	}

}
```
</details>

### `setValueM3(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `arraysEqual`
- `gl.uniformMatrix3fv`
- `copyArray`
- `mat3array.set`

<details><summary>Code</summary>

```typescript
function setValueM3( gl, v ) {

	const cache = this.cache;
	const elements = v.elements;

	if ( elements === undefined ) {

		if ( arraysEqual( cache, v ) ) return;

		gl.uniformMatrix3fv( this.addr, false, v );

		copyArray( cache, v );

	} else {

		if ( arraysEqual( cache, elements ) ) return;

		mat3array.set( elements );

		gl.uniformMatrix3fv( this.addr, false, mat3array );

		copyArray( cache, elements );

	}

}
```
</details>

### `setValueM4(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `arraysEqual`
- `gl.uniformMatrix4fv`
- `copyArray`
- `mat4array.set`

<details><summary>Code</summary>

```typescript
function setValueM4( gl, v ) {

	const cache = this.cache;
	const elements = v.elements;

	if ( elements === undefined ) {

		if ( arraysEqual( cache, v ) ) return;

		gl.uniformMatrix4fv( this.addr, false, v );

		copyArray( cache, v );

	} else {

		if ( arraysEqual( cache, elements ) ) return;

		mat4array.set( elements );

		gl.uniformMatrix4fv( this.addr, false, mat4array );

		copyArray( cache, elements );

	}

}
```
</details>

### `setValueV1i(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform1i`

<details><summary>Code</summary>

```typescript
function setValueV1i( gl, v ) {

	const cache = this.cache;

	if ( cache[ 0 ] === v ) return;

	gl.uniform1i( this.addr, v );

	cache[ 0 ] = v;

}
```
</details>

### `setValueV2i(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform2i`
- `arraysEqual`
- `gl.uniform2iv`
- `copyArray`

<details><summary>Code</summary>

```typescript
function setValueV2i( gl, v ) {

	const cache = this.cache;

	if ( v.x !== undefined ) {

		if ( cache[ 0 ] !== v.x || cache[ 1 ] !== v.y ) {

			gl.uniform2i( this.addr, v.x, v.y );

			cache[ 0 ] = v.x;
			cache[ 1 ] = v.y;

		}

	} else {

		if ( arraysEqual( cache, v ) ) return;

		gl.uniform2iv( this.addr, v );

		copyArray( cache, v );

	}

}
```
</details>

### `setValueV3i(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform3i`
- `arraysEqual`
- `gl.uniform3iv`
- `copyArray`

<details><summary>Code</summary>

```typescript
function setValueV3i( gl, v ) {

	const cache = this.cache;

	if ( v.x !== undefined ) {

		if ( cache[ 0 ] !== v.x || cache[ 1 ] !== v.y || cache[ 2 ] !== v.z ) {

			gl.uniform3i( this.addr, v.x, v.y, v.z );

			cache[ 0 ] = v.x;
			cache[ 1 ] = v.y;
			cache[ 2 ] = v.z;

		}

	} else {

		if ( arraysEqual( cache, v ) ) return;

		gl.uniform3iv( this.addr, v );

		copyArray( cache, v );

	}

}
```
</details>

### `setValueV4i(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform4i`
- `arraysEqual`
- `gl.uniform4iv`
- `copyArray`

<details><summary>Code</summary>

```typescript
function setValueV4i( gl, v ) {

	const cache = this.cache;

	if ( v.x !== undefined ) {

		if ( cache[ 0 ] !== v.x || cache[ 1 ] !== v.y || cache[ 2 ] !== v.z || cache[ 3 ] !== v.w ) {

			gl.uniform4i( this.addr, v.x, v.y, v.z, v.w );

			cache[ 0 ] = v.x;
			cache[ 1 ] = v.y;
			cache[ 2 ] = v.z;
			cache[ 3 ] = v.w;

		}

	} else {

		if ( arraysEqual( cache, v ) ) return;

		gl.uniform4iv( this.addr, v );

		copyArray( cache, v );

	}

}
```
</details>

### `setValueV1ui(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform1ui`

<details><summary>Code</summary>

```typescript
function setValueV1ui( gl, v ) {

	const cache = this.cache;

	if ( cache[ 0 ] === v ) return;

	gl.uniform1ui( this.addr, v );

	cache[ 0 ] = v;

}
```
</details>

### `setValueV2ui(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform2ui`
- `arraysEqual`
- `gl.uniform2uiv`
- `copyArray`

<details><summary>Code</summary>

```typescript
function setValueV2ui( gl, v ) {

	const cache = this.cache;

	if ( v.x !== undefined ) {

		if ( cache[ 0 ] !== v.x || cache[ 1 ] !== v.y ) {

			gl.uniform2ui( this.addr, v.x, v.y );

			cache[ 0 ] = v.x;
			cache[ 1 ] = v.y;

		}

	} else {

		if ( arraysEqual( cache, v ) ) return;

		gl.uniform2uiv( this.addr, v );

		copyArray( cache, v );

	}

}
```
</details>

### `setValueV3ui(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform3ui`
- `arraysEqual`
- `gl.uniform3uiv`
- `copyArray`

<details><summary>Code</summary>

```typescript
function setValueV3ui( gl, v ) {

	const cache = this.cache;

	if ( v.x !== undefined ) {

		if ( cache[ 0 ] !== v.x || cache[ 1 ] !== v.y || cache[ 2 ] !== v.z ) {

			gl.uniform3ui( this.addr, v.x, v.y, v.z );

			cache[ 0 ] = v.x;
			cache[ 1 ] = v.y;
			cache[ 2 ] = v.z;

		}

	} else {

		if ( arraysEqual( cache, v ) ) return;

		gl.uniform3uiv( this.addr, v );

		copyArray( cache, v );

	}

}
```
</details>

### `setValueV4ui(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform4ui`
- `arraysEqual`
- `gl.uniform4uiv`
- `copyArray`

<details><summary>Code</summary>

```typescript
function setValueV4ui( gl, v ) {

	const cache = this.cache;

	if ( v.x !== undefined ) {

		if ( cache[ 0 ] !== v.x || cache[ 1 ] !== v.y || cache[ 2 ] !== v.z || cache[ 3 ] !== v.w ) {

			gl.uniform4ui( this.addr, v.x, v.y, v.z, v.w );

			cache[ 0 ] = v.x;
			cache[ 1 ] = v.y;
			cache[ 2 ] = v.z;
			cache[ 3 ] = v.w;

		}

	} else {

		if ( arraysEqual( cache, v ) ) return;

		gl.uniform4uiv( this.addr, v );

		copyArray( cache, v );

	}

}
```
</details>

### `setValueT1(gl: any, v: any, textures: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`
- **`textures`** `any`

**Returns:** `void`

**Calls:**

- `textures.allocateTextureUnit`
- `gl.uniform1i`
- `textures.setTexture2D`

<details><summary>Code</summary>

```typescript
function setValueT1( gl, v, textures ) {

	const cache = this.cache;
	const unit = textures.allocateTextureUnit();

	if ( cache[ 0 ] !== unit ) {

		gl.uniform1i( this.addr, unit );
		cache[ 0 ] = unit;

	}

	let emptyTexture2D;

	if ( this.type === gl.SAMPLER_2D_SHADOW ) {

		emptyShadowTexture.compareFunction = LessEqualCompare; // #28670
		emptyTexture2D = emptyShadowTexture;

	} else {

		emptyTexture2D = emptyTexture;

	}

	textures.setTexture2D( v || emptyTexture2D, unit );

}
```
</details>

### `setValueT3D1(gl: any, v: any, textures: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`
- **`textures`** `any`

**Returns:** `void`

**Calls:**

- `textures.allocateTextureUnit`
- `gl.uniform1i`
- `textures.setTexture3D`

<details><summary>Code</summary>

```typescript
function setValueT3D1( gl, v, textures ) {

	const cache = this.cache;
	const unit = textures.allocateTextureUnit();

	if ( cache[ 0 ] !== unit ) {

		gl.uniform1i( this.addr, unit );
		cache[ 0 ] = unit;

	}

	textures.setTexture3D( v || empty3dTexture, unit );

}
```
</details>

### `setValueT6(gl: any, v: any, textures: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`
- **`textures`** `any`

**Returns:** `void`

**Calls:**

- `textures.allocateTextureUnit`
- `gl.uniform1i`
- `textures.setTextureCube`

<details><summary>Code</summary>

```typescript
function setValueT6( gl, v, textures ) {

	const cache = this.cache;
	const unit = textures.allocateTextureUnit();

	if ( cache[ 0 ] !== unit ) {

		gl.uniform1i( this.addr, unit );
		cache[ 0 ] = unit;

	}

	textures.setTextureCube( v || emptyCubeTexture, unit );

}
```
</details>

### `setValueT2DArray1(gl: any, v: any, textures: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`
- **`textures`** `any`

**Returns:** `void`

**Calls:**

- `textures.allocateTextureUnit`
- `gl.uniform1i`
- `textures.setTexture2DArray`

<details><summary>Code</summary>

```typescript
function setValueT2DArray1( gl, v, textures ) {

	const cache = this.cache;
	const unit = textures.allocateTextureUnit();

	if ( cache[ 0 ] !== unit ) {

		gl.uniform1i( this.addr, unit );
		cache[ 0 ] = unit;

	}

	textures.setTexture2DArray( v || emptyArrayTexture, unit );

}
```
</details>

### `getSingularSetter(type: any): (gl: any, v: any, textures: any) => void`

**Parameters:**

- **`type`** `any`

**Returns:** `(gl: any, v: any, textures: any) => void`

<details><summary>Code</summary>

```typescript
function getSingularSetter( type ) {

	switch ( type ) {

		case 0x1406: return setValueV1f; // FLOAT
		case 0x8b50: return setValueV2f; // _VEC2
		case 0x8b51: return setValueV3f; // _VEC3
		case 0x8b52: return setValueV4f; // _VEC4

		case 0x8b5a: return setValueM2; // _MAT2
		case 0x8b5b: return setValueM3; // _MAT3
		case 0x8b5c: return setValueM4; // _MAT4

		case 0x1404: case 0x8b56: return setValueV1i; // INT, BOOL
		case 0x8b53: case 0x8b57: return setValueV2i; // _VEC2
		case 0x8b54: case 0x8b58: return setValueV3i; // _VEC3
		case 0x8b55: case 0x8b59: return setValueV4i; // _VEC4

		case 0x1405: return setValueV1ui; // UINT
		case 0x8dc6: return setValueV2ui; // _VEC2
		case 0x8dc7: return setValueV3ui; // _VEC3
		case 0x8dc8: return setValueV4ui; // _VEC4

		case 0x8b5e: // SAMPLER_2D
		case 0x8d66: // SAMPLER_EXTERNAL_OES
		case 0x8dca: // INT_SAMPLER_2D
		case 0x8dd2: // UNSIGNED_INT_SAMPLER_2D
		case 0x8b62: // SAMPLER_2D_SHADOW
			return setValueT1;

		case 0x8b5f: // SAMPLER_3D
		case 0x8dcb: // INT_SAMPLER_3D
		case 0x8dd3: // UNSIGNED_INT_SAMPLER_3D
			return setValueT3D1;

		case 0x8b60: // SAMPLER_CUBE
		case 0x8dcc: // INT_SAMPLER_CUBE
		case 0x8dd4: // UNSIGNED_INT_SAMPLER_CUBE
		case 0x8dc5: // SAMPLER_CUBE_SHADOW
			return setValueT6;

		case 0x8dc1: // SAMPLER_2D_ARRAY
		case 0x8dcf: // INT_SAMPLER_2D_ARRAY
		case 0x8dd7: // UNSIGNED_INT_SAMPLER_2D_ARRAY
		case 0x8dc4: // SAMPLER_2D_ARRAY_SHADOW
			return setValueT2DArray1;

	}

}
```
</details>

### `setValueV1fArray(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform1fv`

<details><summary>Code</summary>

```typescript
function setValueV1fArray( gl, v ) {

	gl.uniform1fv( this.addr, v );

}
```
</details>

### `setValueV2fArray(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `flatten`
- `gl.uniform2fv`

<details><summary>Code</summary>

```typescript
function setValueV2fArray( gl, v ) {

	const data = flatten( v, this.size, 2 );

	gl.uniform2fv( this.addr, data );

}
```
</details>

### `setValueV3fArray(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `flatten`
- `gl.uniform3fv`

<details><summary>Code</summary>

```typescript
function setValueV3fArray( gl, v ) {

	const data = flatten( v, this.size, 3 );

	gl.uniform3fv( this.addr, data );

}
```
</details>

### `setValueV4fArray(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `flatten`
- `gl.uniform4fv`

<details><summary>Code</summary>

```typescript
function setValueV4fArray( gl, v ) {

	const data = flatten( v, this.size, 4 );

	gl.uniform4fv( this.addr, data );

}
```
</details>

### `setValueM2Array(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `flatten`
- `gl.uniformMatrix2fv`

<details><summary>Code</summary>

```typescript
function setValueM2Array( gl, v ) {

	const data = flatten( v, this.size, 4 );

	gl.uniformMatrix2fv( this.addr, false, data );

}
```
</details>

### `setValueM3Array(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `flatten`
- `gl.uniformMatrix3fv`

<details><summary>Code</summary>

```typescript
function setValueM3Array( gl, v ) {

	const data = flatten( v, this.size, 9 );

	gl.uniformMatrix3fv( this.addr, false, data );

}
```
</details>

### `setValueM4Array(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `flatten`
- `gl.uniformMatrix4fv`

<details><summary>Code</summary>

```typescript
function setValueM4Array( gl, v ) {

	const data = flatten( v, this.size, 16 );

	gl.uniformMatrix4fv( this.addr, false, data );

}
```
</details>

### `setValueV1iArray(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform1iv`

<details><summary>Code</summary>

```typescript
function setValueV1iArray( gl, v ) {

	gl.uniform1iv( this.addr, v );

}
```
</details>

### `setValueV2iArray(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform2iv`

<details><summary>Code</summary>

```typescript
function setValueV2iArray( gl, v ) {

	gl.uniform2iv( this.addr, v );

}
```
</details>

### `setValueV3iArray(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform3iv`

<details><summary>Code</summary>

```typescript
function setValueV3iArray( gl, v ) {

	gl.uniform3iv( this.addr, v );

}
```
</details>

### `setValueV4iArray(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform4iv`

<details><summary>Code</summary>

```typescript
function setValueV4iArray( gl, v ) {

	gl.uniform4iv( this.addr, v );

}
```
</details>

### `setValueV1uiArray(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform1uiv`

<details><summary>Code</summary>

```typescript
function setValueV1uiArray( gl, v ) {

	gl.uniform1uiv( this.addr, v );

}
```
</details>

### `setValueV2uiArray(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform2uiv`

<details><summary>Code</summary>

```typescript
function setValueV2uiArray( gl, v ) {

	gl.uniform2uiv( this.addr, v );

}
```
</details>

### `setValueV3uiArray(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform3uiv`

<details><summary>Code</summary>

```typescript
function setValueV3uiArray( gl, v ) {

	gl.uniform3uiv( this.addr, v );

}
```
</details>

### `setValueV4uiArray(gl: any, v: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`

**Returns:** `void`

**Calls:**

- `gl.uniform4uiv`

<details><summary>Code</summary>

```typescript
function setValueV4uiArray( gl, v ) {

	gl.uniform4uiv( this.addr, v );

}
```
</details>

### `setValueT1Array(gl: any, v: any, textures: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`
- **`textures`** `any`

**Returns:** `void`

**Calls:**

- `allocTexUnits`
- `arraysEqual`
- `gl.uniform1iv`
- `copyArray`
- `textures.setTexture2D`

<details><summary>Code</summary>

```typescript
function setValueT1Array( gl, v, textures ) {

	const cache = this.cache;

	const n = v.length;

	const units = allocTexUnits( textures, n );

	if ( ! arraysEqual( cache, units ) ) {

		gl.uniform1iv( this.addr, units );

		copyArray( cache, units );

	}

	for ( let i = 0; i !== n; ++ i ) {

		textures.setTexture2D( v[ i ] || emptyTexture, units[ i ] );

	}

}
```
</details>

### `setValueT3DArray(gl: any, v: any, textures: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`
- **`textures`** `any`

**Returns:** `void`

**Calls:**

- `allocTexUnits`
- `arraysEqual`
- `gl.uniform1iv`
- `copyArray`
- `textures.setTexture3D`

<details><summary>Code</summary>

```typescript
function setValueT3DArray( gl, v, textures ) {

	const cache = this.cache;

	const n = v.length;

	const units = allocTexUnits( textures, n );

	if ( ! arraysEqual( cache, units ) ) {

		gl.uniform1iv( this.addr, units );

		copyArray( cache, units );

	}

	for ( let i = 0; i !== n; ++ i ) {

		textures.setTexture3D( v[ i ] || empty3dTexture, units[ i ] );

	}

}
```
</details>

### `setValueT6Array(gl: any, v: any, textures: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`
- **`textures`** `any`

**Returns:** `void`

**Calls:**

- `allocTexUnits`
- `arraysEqual`
- `gl.uniform1iv`
- `copyArray`
- `textures.setTextureCube`

<details><summary>Code</summary>

```typescript
function setValueT6Array( gl, v, textures ) {

	const cache = this.cache;

	const n = v.length;

	const units = allocTexUnits( textures, n );

	if ( ! arraysEqual( cache, units ) ) {

		gl.uniform1iv( this.addr, units );

		copyArray( cache, units );

	}

	for ( let i = 0; i !== n; ++ i ) {

		textures.setTextureCube( v[ i ] || emptyCubeTexture, units[ i ] );

	}

}
```
</details>

### `setValueT2DArrayArray(gl: any, v: any, textures: any): void`

**Parameters:**

- **`gl`** `any`
- **`v`** `any`
- **`textures`** `any`

**Returns:** `void`

**Calls:**

- `allocTexUnits`
- `arraysEqual`
- `gl.uniform1iv`
- `copyArray`
- `textures.setTexture2DArray`

<details><summary>Code</summary>

```typescript
function setValueT2DArrayArray( gl, v, textures ) {

	const cache = this.cache;

	const n = v.length;

	const units = allocTexUnits( textures, n );

	if ( ! arraysEqual( cache, units ) ) {

		gl.uniform1iv( this.addr, units );

		copyArray( cache, units );

	}

	for ( let i = 0; i !== n; ++ i ) {

		textures.setTexture2DArray( v[ i ] || emptyArrayTexture, units[ i ] );

	}

}
```
</details>

### `getPureArraySetter(type: any): (gl: any, v: any, textures: any) => void`

**Parameters:**

- **`type`** `any`

**Returns:** `(gl: any, v: any, textures: any) => void`

<details><summary>Code</summary>

```typescript
function getPureArraySetter( type ) {

	switch ( type ) {

		case 0x1406: return setValueV1fArray; // FLOAT
		case 0x8b50: return setValueV2fArray; // _VEC2
		case 0x8b51: return setValueV3fArray; // _VEC3
		case 0x8b52: return setValueV4fArray; // _VEC4

		case 0x8b5a: return setValueM2Array; // _MAT2
		case 0x8b5b: return setValueM3Array; // _MAT3
		case 0x8b5c: return setValueM4Array; // _MAT4

		case 0x1404: case 0x8b56: return setValueV1iArray; // INT, BOOL
		case 0x8b53: case 0x8b57: return setValueV2iArray; // _VEC2
		case 0x8b54: case 0x8b58: return setValueV3iArray; // _VEC3
		case 0x8b55: case 0x8b59: return setValueV4iArray; // _VEC4

		case 0x1405: return setValueV1uiArray; // UINT
		case 0x8dc6: return setValueV2uiArray; // _VEC2
		case 0x8dc7: return setValueV3uiArray; // _VEC3
		case 0x8dc8: return setValueV4uiArray; // _VEC4

		case 0x8b5e: // SAMPLER_2D
		case 0x8d66: // SAMPLER_EXTERNAL_OES
		case 0x8dca: // INT_SAMPLER_2D
		case 0x8dd2: // UNSIGNED_INT_SAMPLER_2D
		case 0x8b62: // SAMPLER_2D_SHADOW
			return setValueT1Array;

		case 0x8b5f: // SAMPLER_3D
		case 0x8dcb: // INT_SAMPLER_3D
		case 0x8dd3: // UNSIGNED_INT_SAMPLER_3D
			return setValueT3DArray;

		case 0x8b60: // SAMPLER_CUBE
		case 0x8dcc: // INT_SAMPLER_CUBE
		case 0x8dd4: // UNSIGNED_INT_SAMPLER_CUBE
		case 0x8dc5: // SAMPLER_CUBE_SHADOW
			return setValueT6Array;

		case 0x8dc1: // SAMPLER_2D_ARRAY
		case 0x8dcf: // INT_SAMPLER_2D_ARRAY
		case 0x8dd7: // UNSIGNED_INT_SAMPLER_2D_ARRAY
		case 0x8dc4: // SAMPLER_2D_ARRAY_SHADOW
			return setValueT2DArrayArray;

	}

}
```
</details>

### `StructuredUniform.setValue(gl: any, value: any, textures: any): void`

**Parameters:**

- **`gl`** `any`
- **`value`** `any`
- **`textures`** `any`

**Returns:** `void`

**Calls:**

- `u.setValue`

<details><summary>Code</summary>

```typescript
setValue( gl, value, textures ) {

		const seq = this.seq;

		for ( let i = 0, n = seq.length; i !== n; ++ i ) {

			const u = seq[ i ];
			u.setValue( gl, value[ u.id ], textures );

		}

	}
```
</details>

### `addUniform(container: any, uniformObject: any): void`

**Parameters:**

- **`container`** `any`
- **`uniformObject`** `any`

**Returns:** `void`

**Calls:**

- `container.seq.push`

<details><summary>Code</summary>

```typescript
function addUniform( container, uniformObject ) {

	container.seq.push( uniformObject );
	container.map[ uniformObject.id ] = uniformObject;

}
```
</details>

### `parseUniform(activeInfo: any, addr: any, container: any): void`

**Parameters:**

- **`activeInfo`** `any`
- **`addr`** `any`
- **`container`** `any`

**Returns:** `void`

**Calls:**

- `RePathPart.exec`
- `addUniform`

**Internal Comments:**
```
// reset RegExp object, because of the early exit of a previous run (x4)
// bare name or "pure" bottom-level array "[0]" suffix (x3)
// step into inner node / create it in case it doesn't exist (x2)
```

<details><summary>Code</summary>

```typescript
function parseUniform( activeInfo, addr, container ) {

	const path = activeInfo.name,
		pathLength = path.length;

	// reset RegExp object, because of the early exit of a previous run
	RePathPart.lastIndex = 0;

	while ( true ) {

		const match = RePathPart.exec( path ),
			matchEnd = RePathPart.lastIndex;

		let id = match[ 1 ];
		const idIsIndex = match[ 2 ] === ']',
			subscript = match[ 3 ];

		if ( idIsIndex ) id = id | 0; // convert to integer

		if ( subscript === undefined || subscript === '[' && matchEnd + 2 === pathLength ) {

			// bare name or "pure" bottom-level array "[0]" suffix

			addUniform( container, subscript === undefined ?
				new SingleUniform( id, activeInfo, addr ) :
				new PureArrayUniform( id, activeInfo, addr ) );

			break;

		} else {

			// step into inner node / create it in case it doesn't exist

			const map = container.map;
			let next = map[ id ];

			if ( next === undefined ) {

				next = new StructuredUniform( id );
				addUniform( container, next );

			}

			container = next;

		}

	}

}
```
</details>

### `WebGLUniforms.setValue(gl: any, name: any, value: any, textures: any): void`

**Parameters:**

- **`gl`** `any`
- **`name`** `any`
- **`value`** `any`
- **`textures`** `any`

**Returns:** `void`

**Calls:**

- `u.setValue`

<details><summary>Code</summary>

```typescript
setValue( gl, name, value, textures ) {

		const u = this.map[ name ];

		if ( u !== undefined ) u.setValue( gl, value, textures );

	}
```
</details>

### `WebGLUniforms.setOptional(gl: any, object: any, name: any): void`

**Parameters:**

- **`gl`** `any`
- **`object`** `any`
- **`name`** `any`

**Returns:** `void`

**Calls:**

- `this.setValue`

<details><summary>Code</summary>

```typescript
setOptional( gl, object, name ) {

		const v = object[ name ];

		if ( v !== undefined ) this.setValue( gl, name, v );

	}
```
</details>

### `WebGLUniforms.upload(gl: any, seq: any, values: any, textures: any): void`

**Parameters:**

- **`gl`** `any`
- **`seq`** `any`
- **`values`** `any`
- **`textures`** `any`

**Returns:** `void`

**Calls:**

- `u.setValue`

**Internal Comments:**
```
// note: always updating when .needsUpdate is undefined (x4)
```

<details><summary>Code</summary>

```typescript
static upload( gl, seq, values, textures ) {

		for ( let i = 0, n = seq.length; i !== n; ++ i ) {

			const u = seq[ i ],
				v = values[ u.id ];

			if ( v.needsUpdate !== false ) {

				// note: always updating when .needsUpdate is undefined
				u.setValue( gl, v.value, textures );

			}

		}

	}
```
</details>

### `WebGLUniforms.seqWithValue(seq: any, values: any): any[]`

**Parameters:**

- **`seq`** `any`
- **`values`** `any`

**Returns:** `any[]`

**Calls:**

- `r.push`

<details><summary>Code</summary>

```typescript
static seqWithValue( seq, values ) {

		const r = [];

		for ( let i = 0, n = seq.length; i !== n; ++ i ) {

			const u = seq[ i ];
			if ( u.id in values ) r.push( u );

		}

		return r;

	}
```
</details>


---

## Classes

### `SingleUniform`

<details><summary>Class Code</summary>

```ts
class SingleUniform {

	constructor( id, activeInfo, addr ) {

		this.id = id;
		this.addr = addr;
		this.cache = [];
		this.type = activeInfo.type;
		this.setValue = getSingularSetter( activeInfo.type );

		// this.path = activeInfo.name; // DEBUG

	}

}
```
</details>

### `PureArrayUniform`

<details><summary>Class Code</summary>

```ts
class PureArrayUniform {

	constructor( id, activeInfo, addr ) {

		this.id = id;
		this.addr = addr;
		this.cache = [];
		this.type = activeInfo.type;
		this.size = activeInfo.size;
		this.setValue = getPureArraySetter( activeInfo.type );

		// this.path = activeInfo.name; // DEBUG

	}

}
```
</details>

### `StructuredUniform`

<details><summary>Class Code</summary>

```ts
class StructuredUniform {

	constructor( id ) {

		this.id = id;

		this.seq = [];
		this.map = {};

	}

	setValue( gl, value, textures ) {

		const seq = this.seq;

		for ( let i = 0, n = seq.length; i !== n; ++ i ) {

			const u = seq[ i ];
			u.setValue( gl, value[ u.id ], textures );

		}

	}

}
```
</details>

#### Methods

##### `setValue(gl: any, value: any, textures: any): void`

<details><summary>Code</summary>

```ts
setValue( gl, value, textures ) {

		const seq = this.seq;

		for ( let i = 0, n = seq.length; i !== n; ++ i ) {

			const u = seq[ i ];
			u.setValue( gl, value[ u.id ], textures );

		}

	}
```
</details>

### `WebGLUniforms`

<details><summary>Class Code</summary>

```ts
class WebGLUniforms {

	constructor( gl, program ) {

		this.seq = [];
		this.map = {};

		const n = gl.getProgramParameter( program, gl.ACTIVE_UNIFORMS );

		for ( let i = 0; i < n; ++ i ) {

			const info = gl.getActiveUniform( program, i ),
				addr = gl.getUniformLocation( program, info.name );

			parseUniform( info, addr, this );

		}

	}

	setValue( gl, name, value, textures ) {

		const u = this.map[ name ];

		if ( u !== undefined ) u.setValue( gl, value, textures );

	}

	setOptional( gl, object, name ) {

		const v = object[ name ];

		if ( v !== undefined ) this.setValue( gl, name, v );

	}

	static upload( gl, seq, values, textures ) {

		for ( let i = 0, n = seq.length; i !== n; ++ i ) {

			const u = seq[ i ],
				v = values[ u.id ];

			if ( v.needsUpdate !== false ) {

				// note: always updating when .needsUpdate is undefined
				u.setValue( gl, v.value, textures );

			}

		}

	}

	static seqWithValue( seq, values ) {

		const r = [];

		for ( let i = 0, n = seq.length; i !== n; ++ i ) {

			const u = seq[ i ];
			if ( u.id in values ) r.push( u );

		}

		return r;

	}

}
```
</details>

#### Methods

##### `setValue(gl: any, name: any, value: any, textures: any): void`

<details><summary>Code</summary>

```ts
setValue( gl, name, value, textures ) {

		const u = this.map[ name ];

		if ( u !== undefined ) u.setValue( gl, value, textures );

	}
```
</details>

##### `setOptional(gl: any, object: any, name: any): void`

<details><summary>Code</summary>

```ts
setOptional( gl, object, name ) {

		const v = object[ name ];

		if ( v !== undefined ) this.setValue( gl, name, v );

	}
```
</details>

##### `upload(gl: any, seq: any, values: any, textures: any): void`

<details><summary>Code</summary>

```ts
static upload( gl, seq, values, textures ) {

		for ( let i = 0, n = seq.length; i !== n; ++ i ) {

			const u = seq[ i ],
				v = values[ u.id ];

			if ( v.needsUpdate !== false ) {

				// note: always updating when .needsUpdate is undefined
				u.setValue( gl, v.value, textures );

			}

		}

	}
```
</details>

##### `seqWithValue(seq: any, values: any): any[]`

<details><summary>Code</summary>

```ts
static seqWithValue( seq, values ) {

		const r = [];

		for ( let i = 0, n = seq.length; i !== n; ++ i ) {

			const u = seq[ i ];
			if ( u.id in values ) r.push( u );

		}

		return r;

	}
```
</details>


---