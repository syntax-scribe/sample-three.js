[⬅️ Back to Table of Contents](../../index.md)

# 📄 `TextureUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 🧱 Classes | 1 |
| 📦 Imports | 51 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/extras/TextureUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AlphaFormat` | `../constants.js` |
| `RedFormat` | `../constants.js` |
| `RedIntegerFormat` | `../constants.js` |
| `RGFormat` | `../constants.js` |
| `RGIntegerFormat` | `../constants.js` |
| `RGBFormat` | `../constants.js` |
| `RGBAFormat` | `../constants.js` |
| `RGBAIntegerFormat` | `../constants.js` |
| `RGB_S3TC_DXT1_Format` | `../constants.js` |
| `RGBA_S3TC_DXT1_Format` | `../constants.js` |
| `RGBA_S3TC_DXT3_Format` | `../constants.js` |
| `RGBA_S3TC_DXT5_Format` | `../constants.js` |
| `RGB_PVRTC_2BPPV1_Format` | `../constants.js` |
| `RGBA_PVRTC_2BPPV1_Format` | `../constants.js` |
| `RGB_PVRTC_4BPPV1_Format` | `../constants.js` |
| `RGBA_PVRTC_4BPPV1_Format` | `../constants.js` |
| `RGB_ETC1_Format` | `../constants.js` |
| `RGB_ETC2_Format` | `../constants.js` |
| `RGBA_ETC2_EAC_Format` | `../constants.js` |
| `RGBA_ASTC_4x4_Format` | `../constants.js` |
| `RGBA_ASTC_5x4_Format` | `../constants.js` |
| `RGBA_ASTC_5x5_Format` | `../constants.js` |
| `RGBA_ASTC_6x5_Format` | `../constants.js` |
| `RGBA_ASTC_6x6_Format` | `../constants.js` |
| `RGBA_ASTC_8x5_Format` | `../constants.js` |
| `RGBA_ASTC_8x6_Format` | `../constants.js` |
| `RGBA_ASTC_8x8_Format` | `../constants.js` |
| `RGBA_ASTC_10x5_Format` | `../constants.js` |
| `RGBA_ASTC_10x6_Format` | `../constants.js` |
| `RGBA_ASTC_10x8_Format` | `../constants.js` |
| `RGBA_ASTC_10x10_Format` | `../constants.js` |
| `RGBA_ASTC_12x10_Format` | `../constants.js` |
| `RGBA_ASTC_12x12_Format` | `../constants.js` |
| `RGBA_BPTC_Format` | `../constants.js` |
| `RGB_BPTC_SIGNED_Format` | `../constants.js` |
| `RGB_BPTC_UNSIGNED_Format` | `../constants.js` |
| `RED_RGTC1_Format` | `../constants.js` |
| `SIGNED_RED_RGTC1_Format` | `../constants.js` |
| `RED_GREEN_RGTC2_Format` | `../constants.js` |
| `SIGNED_RED_GREEN_RGTC2_Format` | `../constants.js` |
| `UnsignedByteType` | `../constants.js` |
| `ByteType` | `../constants.js` |
| `UnsignedShortType` | `../constants.js` |
| `ShortType` | `../constants.js` |
| `HalfFloatType` | `../constants.js` |
| `UnsignedShort4444Type` | `../constants.js` |
| `UnsignedShort5551Type` | `../constants.js` |
| `UnsignedIntType` | `../constants.js` |
| `IntType` | `../constants.js` |
| `FloatType` | `../constants.js` |
| `UnsignedInt5999Type` | `../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `imageAspect` | `number` | let/var | `( texture.image && texture.image.width ) ? texture.image.width / texture.imag...` | ✗ |
| `imageAspect` | `number` | let/var | `( texture.image && texture.image.width ) ? texture.image.width / texture.imag...` | ✗ |


---

## Functions

### `contain(texture: Texture, aspect: number): Texture`

**JSDoc:**
```typescript
/**
 * Scales the texture as large as possible within its surface without cropping
 * or stretching the texture. The method preserves the original aspect ratio of
 * the texture. Akin to CSS `object-fit: contain`
 *
 * @param {Texture} texture - The texture.
 * @param {number} aspect - The texture's aspect ratio.
 * @return {Texture} The updated texture.
 */
```

**Parameters:**

- **`texture`** `Texture`
- **`aspect`** `number`

**Returns:** `Texture`

<details><summary>Code</summary>

```typescript
function contain( texture, aspect ) {

	const imageAspect = ( texture.image && texture.image.width ) ? texture.image.width / texture.image.height : 1;

	if ( imageAspect > aspect ) {

		texture.repeat.x = 1;
		texture.repeat.y = imageAspect / aspect;

		texture.offset.x = 0;
		texture.offset.y = ( 1 - texture.repeat.y ) / 2;

	} else {

		texture.repeat.x = aspect / imageAspect;
		texture.repeat.y = 1;

		texture.offset.x = ( 1 - texture.repeat.x ) / 2;
		texture.offset.y = 0;

	}

	return texture;

}
```
</details>

### `cover(texture: Texture, aspect: number): Texture`

**JSDoc:**
```typescript
/**
 * Scales the texture to the smallest possible size to fill the surface, leaving
 * no empty space. The method preserves the original aspect ratio of the texture.
 * Akin to CSS `object-fit: cover`.
 *
 * @param {Texture} texture - The texture.
 * @param {number} aspect - The texture's aspect ratio.
 * @return {Texture} The updated texture.
 */
```

**Parameters:**

- **`texture`** `Texture`
- **`aspect`** `number`

**Returns:** `Texture`

<details><summary>Code</summary>

```typescript
function cover( texture, aspect ) {

	const imageAspect = ( texture.image && texture.image.width ) ? texture.image.width / texture.image.height : 1;

	if ( imageAspect > aspect ) {

		texture.repeat.x = aspect / imageAspect;
		texture.repeat.y = 1;

		texture.offset.x = ( 1 - texture.repeat.x ) / 2;
		texture.offset.y = 0;

	} else {

		texture.repeat.x = 1;
		texture.repeat.y = imageAspect / aspect;

		texture.offset.x = 0;
		texture.offset.y = ( 1 - texture.repeat.y ) / 2;

	}

	return texture;

}
```
</details>

### `fill(texture: Texture): Texture`

**JSDoc:**
```typescript
/**
 * Configures the texture to the default transformation. Akin to CSS `object-fit: fill`.
 *
 * @param {Texture} texture - The texture.
 * @return {Texture} The updated texture.
 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `Texture`

<details><summary>Code</summary>

```typescript
function fill( texture ) {

	texture.repeat.x = 1;
	texture.repeat.y = 1;

	texture.offset.x = 0;
	texture.offset.y = 0;

	return texture;

}
```
</details>

### `getByteLength(width: number, height: number, format: number, type: number): number`

**JSDoc:**
```typescript
/**
 * Determines how many bytes must be used to represent the texture.
 *
 * @param {number} width - The width of the texture.
 * @param {number} height - The height of the texture.
 * @param {number} format - The texture's format.
 * @param {number} type - The texture's type.
 * @return {number} The byte length.
 */
```

**Parameters:**

- **`width`** `number`
- **`height`** `number`
- **`format`** `number`
- **`type`** `number`

**Returns:** `number`

**Calls:**

- `getTextureTypeByteLength`
- `Math.floor`
- `Math.max`
- `Math.ceil`

**Internal Comments:**
```
// https://registry.khronos.org/OpenGL-Refpages/es3.0/html/glTexImage2D.xhtml
// https://registry.khronos.org/webgl/extensions/WEBGL_compressed_texture_s3tc_srgb/
// https://registry.khronos.org/webgl/extensions/WEBGL_compressed_texture_pvrtc/
// https://registry.khronos.org/webgl/extensions/WEBGL_compressed_texture_etc/
// https://registry.khronos.org/webgl/extensions/WEBGL_compressed_texture_astc/
// https://registry.khronos.org/webgl/extensions/EXT_texture_compression_bptc/
// https://registry.khronos.org/webgl/extensions/EXT_texture_compression_rgtc/
```

<details><summary>Code</summary>

```typescript
function getByteLength( width, height, format, type ) {

	const typeByteLength = getTextureTypeByteLength( type );

	switch ( format ) {

		// https://registry.khronos.org/OpenGL-Refpages/es3.0/html/glTexImage2D.xhtml
		case AlphaFormat:
			return width * height;
		case RedFormat:
			return ( ( width * height ) / typeByteLength.components ) * typeByteLength.byteLength;
		case RedIntegerFormat:
			return ( ( width * height ) / typeByteLength.components ) * typeByteLength.byteLength;
		case RGFormat:
			return ( ( width * height * 2 ) / typeByteLength.components ) * typeByteLength.byteLength;
		case RGIntegerFormat:
			return ( ( width * height * 2 ) / typeByteLength.components ) * typeByteLength.byteLength;
		case RGBFormat:
			return ( ( width * height * 3 ) / typeByteLength.components ) * typeByteLength.byteLength;
		case RGBAFormat:
			return ( ( width * height * 4 ) / typeByteLength.components ) * typeByteLength.byteLength;
		case RGBAIntegerFormat:
			return ( ( width * height * 4 ) / typeByteLength.components ) * typeByteLength.byteLength;

		// https://registry.khronos.org/webgl/extensions/WEBGL_compressed_texture_s3tc_srgb/
		case RGB_S3TC_DXT1_Format:
		case RGBA_S3TC_DXT1_Format:
			return Math.floor( ( width + 3 ) / 4 ) * Math.floor( ( height + 3 ) / 4 ) * 8;
		case RGBA_S3TC_DXT3_Format:
		case RGBA_S3TC_DXT5_Format:
			return Math.floor( ( width + 3 ) / 4 ) * Math.floor( ( height + 3 ) / 4 ) * 16;

		// https://registry.khronos.org/webgl/extensions/WEBGL_compressed_texture_pvrtc/
		case RGB_PVRTC_2BPPV1_Format:
		case RGBA_PVRTC_2BPPV1_Format:
			return ( Math.max( width, 16 ) * Math.max( height, 8 ) ) / 4;
		case RGB_PVRTC_4BPPV1_Format:
		case RGBA_PVRTC_4BPPV1_Format:
			return ( Math.max( width, 8 ) * Math.max( height, 8 ) ) / 2;

		// https://registry.khronos.org/webgl/extensions/WEBGL_compressed_texture_etc/
		case RGB_ETC1_Format:
		case RGB_ETC2_Format:
			return Math.floor( ( width + 3 ) / 4 ) * Math.floor( ( height + 3 ) / 4 ) * 8;
		case RGBA_ETC2_EAC_Format:
			return Math.floor( ( width + 3 ) / 4 ) * Math.floor( ( height + 3 ) / 4 ) * 16;

		// https://registry.khronos.org/webgl/extensions/WEBGL_compressed_texture_astc/
		case RGBA_ASTC_4x4_Format:
			return Math.floor( ( width + 3 ) / 4 ) * Math.floor( ( height + 3 ) / 4 ) * 16;
		case RGBA_ASTC_5x4_Format:
			return Math.floor( ( width + 4 ) / 5 ) * Math.floor( ( height + 3 ) / 4 ) * 16;
		case RGBA_ASTC_5x5_Format:
			return Math.floor( ( width + 4 ) / 5 ) * Math.floor( ( height + 4 ) / 5 ) * 16;
		case RGBA_ASTC_6x5_Format:
			return Math.floor( ( width + 5 ) / 6 ) * Math.floor( ( height + 4 ) / 5 ) * 16;
		case RGBA_ASTC_6x6_Format:
			return Math.floor( ( width + 5 ) / 6 ) * Math.floor( ( height + 5 ) / 6 ) * 16;
		case RGBA_ASTC_8x5_Format:
			return Math.floor( ( width + 7 ) / 8 ) * Math.floor( ( height + 4 ) / 5 ) * 16;
		case RGBA_ASTC_8x6_Format:
			return Math.floor( ( width + 7 ) / 8 ) * Math.floor( ( height + 5 ) / 6 ) * 16;
		case RGBA_ASTC_8x8_Format:
			return Math.floor( ( width + 7 ) / 8 ) * Math.floor( ( height + 7 ) / 8 ) * 16;
		case RGBA_ASTC_10x5_Format:
			return Math.floor( ( width + 9 ) / 10 ) * Math.floor( ( height + 4 ) / 5 ) * 16;
		case RGBA_ASTC_10x6_Format:
			return Math.floor( ( width + 9 ) / 10 ) * Math.floor( ( height + 5 ) / 6 ) * 16;
		case RGBA_ASTC_10x8_Format:
			return Math.floor( ( width + 9 ) / 10 ) * Math.floor( ( height + 7 ) / 8 ) * 16;
		case RGBA_ASTC_10x10_Format:
			return Math.floor( ( width + 9 ) / 10 ) * Math.floor( ( height + 9 ) / 10 ) * 16;
		case RGBA_ASTC_12x10_Format:
			return Math.floor( ( width + 11 ) / 12 ) * Math.floor( ( height + 9 ) / 10 ) * 16;
		case RGBA_ASTC_12x12_Format:
			return Math.floor( ( width + 11 ) / 12 ) * Math.floor( ( height + 11 ) / 12 ) * 16;

		// https://registry.khronos.org/webgl/extensions/EXT_texture_compression_bptc/
		case RGBA_BPTC_Format:
		case RGB_BPTC_SIGNED_Format:
		case RGB_BPTC_UNSIGNED_Format:
			return Math.ceil( width / 4 ) * Math.ceil( height / 4 ) * 16;

		// https://registry.khronos.org/webgl/extensions/EXT_texture_compression_rgtc/
		case RED_RGTC1_Format:
		case SIGNED_RED_RGTC1_Format:
			return Math.ceil( width / 4 ) * Math.ceil( height / 4 ) * 8;
		case RED_GREEN_RGTC2_Format:
		case SIGNED_RED_GREEN_RGTC2_Format:
			return Math.ceil( width / 4 ) * Math.ceil( height / 4 ) * 16;

	}

	throw new Error(
		`Unable to determine texture byte length for ${format} format.`,
	);

}
```
</details>

### `getTextureTypeByteLength(type: any): { byteLength: number; components: number; }`

**Parameters:**

- **`type`** `any`

**Returns:** `{ byteLength: number; components: number; }`

<details><summary>Code</summary>

```typescript
function getTextureTypeByteLength( type ) {

	switch ( type ) {

		case UnsignedByteType:
		case ByteType:
			return { byteLength: 1, components: 1 };
		case UnsignedShortType:
		case ShortType:
		case HalfFloatType:
			return { byteLength: 2, components: 1 };
		case UnsignedShort4444Type:
		case UnsignedShort5551Type:
			return { byteLength: 2, components: 4 };
		case UnsignedIntType:
		case IntType:
		case FloatType:
			return { byteLength: 4, components: 1 };
		case UnsignedInt5999Type:
			return { byteLength: 4, components: 3 };

	}

	throw new Error( `Unknown texture type ${type}.` );

}
```
</details>

### `TextureUtils.contain(texture: Texture, aspect: number): Texture`

**JSDoc:**
```typescript
/**
	 * Scales the texture as large as possible within its surface without cropping
	 * or stretching the texture. The method preserves the original aspect ratio of
	 * the texture. Akin to CSS `object-fit: contain`
	 *
	 * @param {Texture} texture - The texture.
	 * @param {number} aspect - The texture's aspect ratio.
	 * @return {Texture} The updated texture.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`aspect`** `number`

**Returns:** `Texture`

**Calls:**

- `contain`

<details><summary>Code</summary>

```typescript
static contain( texture, aspect ) {

		return contain( texture, aspect );

	}
```
</details>

### `TextureUtils.cover(texture: Texture, aspect: number): Texture`

**JSDoc:**
```typescript
/**
	 * Scales the texture to the smallest possible size to fill the surface, leaving
	 * no empty space. The method preserves the original aspect ratio of the texture.
	 * Akin to CSS `object-fit: cover`.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {number} aspect - The texture's aspect ratio.
	 * @return {Texture} The updated texture.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`aspect`** `number`

**Returns:** `Texture`

**Calls:**

- `cover`

<details><summary>Code</summary>

```typescript
static cover( texture, aspect ) {

		return cover( texture, aspect );

	}
```
</details>

### `TextureUtils.fill(texture: Texture): Texture`

**JSDoc:**
```typescript
/**
	 * Configures the texture to the default transformation. Akin to CSS `object-fit: fill`.
	 *
	 * @param {Texture} texture - The texture.
	 * @return {Texture} The updated texture.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `Texture`

**Calls:**

- `fill`

<details><summary>Code</summary>

```typescript
static fill( texture ) {

		return fill( texture );

	}
```
</details>

### `TextureUtils.getByteLength(width: number, height: number, format: number, type: number): number`

**JSDoc:**
```typescript
/**
	 * Determines how many bytes must be used to represent the texture.
	 *
	 * @param {number} width - The width of the texture.
	 * @param {number} height - The height of the texture.
	 * @param {number} format - The texture's format.
	 * @param {number} type - The texture's type.
	 * @return {number} The byte length.
	 */
```

**Parameters:**

- **`width`** `number`
- **`height`** `number`
- **`format`** `number`
- **`type`** `number`

**Returns:** `number`

**Calls:**

- `getByteLength`

<details><summary>Code</summary>

```typescript
static getByteLength( width, height, format, type ) {

		return getByteLength( width, height, format, type );

	}
```
</details>


---

## Classes

### `TextureUtils`

<details><summary>Class Code</summary>

```ts
class TextureUtils {

	/**
	 * Scales the texture as large as possible within its surface without cropping
	 * or stretching the texture. The method preserves the original aspect ratio of
	 * the texture. Akin to CSS `object-fit: contain`
	 *
	 * @param {Texture} texture - The texture.
	 * @param {number} aspect - The texture's aspect ratio.
	 * @return {Texture} The updated texture.
	 */
	static contain( texture, aspect ) {

		return contain( texture, aspect );

	}

	/**
	 * Scales the texture to the smallest possible size to fill the surface, leaving
	 * no empty space. The method preserves the original aspect ratio of the texture.
	 * Akin to CSS `object-fit: cover`.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {number} aspect - The texture's aspect ratio.
	 * @return {Texture} The updated texture.
	 */
	static cover( texture, aspect ) {

		return cover( texture, aspect );

	}

	/**
	 * Configures the texture to the default transformation. Akin to CSS `object-fit: fill`.
	 *
	 * @param {Texture} texture - The texture.
	 * @return {Texture} The updated texture.
	 */
	static fill( texture ) {

		return fill( texture );

	}

	/**
	 * Determines how many bytes must be used to represent the texture.
	 *
	 * @param {number} width - The width of the texture.
	 * @param {number} height - The height of the texture.
	 * @param {number} format - The texture's format.
	 * @param {number} type - The texture's type.
	 * @return {number} The byte length.
	 */
	static getByteLength( width, height, format, type ) {

		return getByteLength( width, height, format, type );

	}

}
```
</details>

#### Methods

##### `contain(texture: Texture, aspect: number): Texture`

<details><summary>Code</summary>

```ts
static contain( texture, aspect ) {

		return contain( texture, aspect );

	}
```
</details>

##### `cover(texture: Texture, aspect: number): Texture`

<details><summary>Code</summary>

```ts
static cover( texture, aspect ) {

		return cover( texture, aspect );

	}
```
</details>

##### `fill(texture: Texture): Texture`

<details><summary>Code</summary>

```ts
static fill( texture ) {

		return fill( texture );

	}
```
</details>

##### `getByteLength(width: number, height: number, format: number, type: number): number`

<details><summary>Code</summary>

```ts
static getByteLength( width, height, format, type ) {

		return getByteLength( width, height, format, type );

	}
```
</details>


---