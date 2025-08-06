[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLExtensions.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLExtensions.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `warnOnce` | `../../utils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `extensions` | `{}` | let/var | `{}` | ✗ |
| `extension` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `WebGLExtensions(gl: any): { has: (name: any) => boolean; init: () => void; get: (name: any) => any; }`

**Parameters:**

- **`gl`** `any`

**Returns:** `{ has: (name: any) => boolean; init: () => void; get: (name: any) => any; }`

**Calls:**

- `gl.getExtension`
- `getExtension`
- `warnOnce (from ../../utils.js)`

<details><summary>Code</summary>

```typescript
function WebGLExtensions( gl ) {

	const extensions = {};

	function getExtension( name ) {

		if ( extensions[ name ] !== undefined ) {

			return extensions[ name ];

		}

		let extension;

		switch ( name ) {

			case 'WEBGL_depth_texture':
				extension = gl.getExtension( 'WEBGL_depth_texture' ) || gl.getExtension( 'MOZ_WEBGL_depth_texture' ) || gl.getExtension( 'WEBKIT_WEBGL_depth_texture' );
				break;

			case 'EXT_texture_filter_anisotropic':
				extension = gl.getExtension( 'EXT_texture_filter_anisotropic' ) || gl.getExtension( 'MOZ_EXT_texture_filter_anisotropic' ) || gl.getExtension( 'WEBKIT_EXT_texture_filter_anisotropic' );
				break;

			case 'WEBGL_compressed_texture_s3tc':
				extension = gl.getExtension( 'WEBGL_compressed_texture_s3tc' ) || gl.getExtension( 'MOZ_WEBGL_compressed_texture_s3tc' ) || gl.getExtension( 'WEBKIT_WEBGL_compressed_texture_s3tc' );
				break;

			case 'WEBGL_compressed_texture_pvrtc':
				extension = gl.getExtension( 'WEBGL_compressed_texture_pvrtc' ) || gl.getExtension( 'WEBKIT_WEBGL_compressed_texture_pvrtc' );
				break;

			default:
				extension = gl.getExtension( name );

		}

		extensions[ name ] = extension;

		return extension;

	}

	return {

		has: function ( name ) {

			return getExtension( name ) !== null;

		},

		init: function () {

			getExtension( 'EXT_color_buffer_float' );
			getExtension( 'WEBGL_clip_cull_distance' );
			getExtension( 'OES_texture_float_linear' );
			getExtension( 'EXT_color_buffer_half_float' );
			getExtension( 'WEBGL_multisampled_render_to_texture' );
			getExtension( 'WEBGL_render_shared_exponent' );

		},

		get: function ( name ) {

			const extension = getExtension( name );

			if ( extension === null ) {

				warnOnce( 'THREE.WebGLRenderer: ' + name + ' extension not supported.' );

			}

			return extension;

		}

	};

}
```
</details>

### `getExtension(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `gl.getExtension`

<details><summary>Code</summary>

```typescript
function getExtension( name ) {

		if ( extensions[ name ] !== undefined ) {

			return extensions[ name ];

		}

		let extension;

		switch ( name ) {

			case 'WEBGL_depth_texture':
				extension = gl.getExtension( 'WEBGL_depth_texture' ) || gl.getExtension( 'MOZ_WEBGL_depth_texture' ) || gl.getExtension( 'WEBKIT_WEBGL_depth_texture' );
				break;

			case 'EXT_texture_filter_anisotropic':
				extension = gl.getExtension( 'EXT_texture_filter_anisotropic' ) || gl.getExtension( 'MOZ_EXT_texture_filter_anisotropic' ) || gl.getExtension( 'WEBKIT_EXT_texture_filter_anisotropic' );
				break;

			case 'WEBGL_compressed_texture_s3tc':
				extension = gl.getExtension( 'WEBGL_compressed_texture_s3tc' ) || gl.getExtension( 'MOZ_WEBGL_compressed_texture_s3tc' ) || gl.getExtension( 'WEBKIT_WEBGL_compressed_texture_s3tc' );
				break;

			case 'WEBGL_compressed_texture_pvrtc':
				extension = gl.getExtension( 'WEBGL_compressed_texture_pvrtc' ) || gl.getExtension( 'WEBKIT_WEBGL_compressed_texture_pvrtc' );
				break;

			default:
				extension = gl.getExtension( name );

		}

		extensions[ name ] = extension;

		return extension;

	}
```
</details>

### `has(name: any): boolean`

**Parameters:**

- **`name`** `any`

**Returns:** `boolean`

**Calls:**

- `getExtension`

<details><summary>Code</summary>

```typescript
function ( name ) {

			return getExtension( name ) !== null;

		}
```
</details>

### `init(): void`

**Returns:** `void`

**Calls:**

- `getExtension`

<details><summary>Code</summary>

```typescript
function () {

			getExtension( 'EXT_color_buffer_float' );
			getExtension( 'WEBGL_clip_cull_distance' );
			getExtension( 'OES_texture_float_linear' );
			getExtension( 'EXT_color_buffer_half_float' );
			getExtension( 'WEBGL_multisampled_render_to_texture' );
			getExtension( 'WEBGL_render_shared_exponent' );

		}
```
</details>

### `get(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `getExtension`
- `warnOnce (from ../../utils.js)`

<details><summary>Code</summary>

```typescript
function ( name ) {

			const extension = getExtension( name );

			if ( extension === null ) {

				warnOnce( 'THREE.WebGLRenderer: ' + name + ' extension not supported.' );

			}

			return extension;

		}
```
</details>

### `has(name: any): boolean`

**Parameters:**

- **`name`** `any`

**Returns:** `boolean`

**Calls:**

- `getExtension`

<details><summary>Code</summary>

```typescript
function ( name ) {

			return getExtension( name ) !== null;

		}
```
</details>

### `init(): void`

**Returns:** `void`

**Calls:**

- `getExtension`

<details><summary>Code</summary>

```typescript
function () {

			getExtension( 'EXT_color_buffer_float' );
			getExtension( 'WEBGL_clip_cull_distance' );
			getExtension( 'OES_texture_float_linear' );
			getExtension( 'EXT_color_buffer_half_float' );
			getExtension( 'WEBGL_multisampled_render_to_texture' );
			getExtension( 'WEBGL_render_shared_exponent' );

		}
```
</details>

### `get(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `getExtension`
- `warnOnce (from ../../utils.js)`

<details><summary>Code</summary>

```typescript
function ( name ) {

			const extension = getExtension( name );

			if ( extension === null ) {

				warnOnce( 'THREE.WebGLRenderer: ' + name + ' extension not supported.' );

			}

			return extension;

		}
```
</details>


---