[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `UniformsUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/shaders/UniformsUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ColorManagement` | `../../math/ColorManagement.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `dst` | `{}` | let/var | `{}` | ✗ |
| `property` | `any` | let/var | `src[ u ][ p ]` | ✗ |
| `merged` | `{}` | let/var | `{}` | ✗ |
| `dst` | `any[]` | let/var | `[]` | ✗ |
| `UniformsUtils` | `{ clone: (src: any) => {}; merge: (un...` | let/var | `{ clone: cloneUniforms, merge: mergeUniforms }` | ✗ |


---

## Functions

### `cloneUniforms(src: any): {}`

**Parameters:**

- **`src`** `any`

**Returns:** `{}`

**Calls:**

- `console.warn`
- `property.clone`
- `Array.isArray`
- `property.slice`

<details><summary>Code</summary>

```typescript
export function cloneUniforms( src ) {

	const dst = {};

	for ( const u in src ) {

		dst[ u ] = {};

		for ( const p in src[ u ] ) {

			const property = src[ u ][ p ];

			if ( property && ( property.isColor ||
				property.isMatrix3 || property.isMatrix4 ||
				property.isVector2 || property.isVector3 || property.isVector4 ||
				property.isTexture || property.isQuaternion ) ) {

				if ( property.isRenderTargetTexture ) {

					console.warn( 'UniformsUtils: Textures of render targets cannot be cloned via cloneUniforms() or mergeUniforms().' );
					dst[ u ][ p ] = null;

				} else {

					dst[ u ][ p ] = property.clone();

				}

			} else if ( Array.isArray( property ) ) {

				dst[ u ][ p ] = property.slice();

			} else {

				dst[ u ][ p ] = property;

			}

		}

	}

	return dst;

}
```
</details>

### `mergeUniforms(uniforms: any): {}`

**Parameters:**

- **`uniforms`** `any`

**Returns:** `{}`

**Calls:**

- `cloneUniforms`

<details><summary>Code</summary>

```typescript
export function mergeUniforms( uniforms ) {

	const merged = {};

	for ( let u = 0; u < uniforms.length; u ++ ) {

		const tmp = cloneUniforms( uniforms[ u ] );

		for ( const p in tmp ) {

			merged[ p ] = tmp[ p ];

		}

	}

	return merged;

}
```
</details>

### `cloneUniformsGroups(src: any): any[]`

**Parameters:**

- **`src`** `any`

**Returns:** `any[]`

**Calls:**

- `dst.push`
- `src[ u ].clone`

<details><summary>Code</summary>

```typescript
export function cloneUniformsGroups( src ) {

	const dst = [];

	for ( let u = 0; u < src.length; u ++ ) {

		dst.push( src[ u ].clone() );

	}

	return dst;

}
```
</details>

### `getUnlitUniformColorSpace(renderer: any): any`

**Parameters:**

- **`renderer`** `any`

**Returns:** `any`

**Calls:**

- `renderer.getRenderTarget`

**Internal Comments:**
```
// https://github.com/mrdoob/three.js/pull/23937#issuecomment-1111067398
// https://github.com/mrdoob/three.js/issues/27868
```

<details><summary>Code</summary>

```typescript
export function getUnlitUniformColorSpace( renderer ) {

	const currentRenderTarget = renderer.getRenderTarget();

	if ( currentRenderTarget === null ) {

		// https://github.com/mrdoob/three.js/pull/23937#issuecomment-1111067398
		return renderer.outputColorSpace;

	}

	// https://github.com/mrdoob/three.js/issues/27868
	if ( currentRenderTarget.isXRRenderTarget === true ) {

		return currentRenderTarget.texture.colorSpace;

	}

	return ColorManagement.workingColorSpace;

}
```
</details>


---