[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `boxBlur.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 12 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/boxBlur.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Fn` | `three/tsl` |
| `vec2` | `three/tsl` |
| `uv` | `three/tsl` |
| `Loop` | `three/tsl` |
| `vec4` | `three/tsl` |
| `premultiplyAlpha` | `three/tsl` |
| `unpremultiplyAlpha` | `three/tsl` |
| `max` | `three/tsl` |
| `int` | `three/tsl` |
| `textureSize` | `three/tsl` |
| `nodeObject` | `three/tsl` |
| `convertToTexture` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `size` | `any` | let/var | `nodeObject( options.size ) \|\| int( 1 )` | ✗ |
| `separation` | `any` | let/var | `nodeObject( options.separation ) \|\| int( 1 )` | ✗ |
| `mask` | `any` | let/var | `options.mask \|\| null` | ✗ |
| `premultipliedAlpha` | `any` | let/var | `options.premultipliedAlpha \|\| false` | ✗ |
| `alpha` | `any` | let/var | `mask.sample( uv ).x` | ✗ |
| `targetUV` | `any` | let/var | `textureNode.uvNode \|\| uv()` | ✗ |


---

## Functions

### `tap(uv: any): any`

**Parameters:**

- **`uv`** `any`

**Returns:** `any`

**Calls:**

- `textureNode.sample`
- `mask.sample`
- `vec4 (from three/tsl)`
- `sample.a.mul`
- `premultiplyAlpha (from three/tsl)`

<details><summary>Code</summary>

```typescript
( uv ) => {

		let sample = textureNode.sample( uv );

		if ( mask !== null ) {

			const alpha = mask.sample( uv ).x;

			sample = vec4( sample.rgb, sample.a.mul( alpha ) );

		}

		return premultipliedAlpha ? premultiplyAlpha( sample ) : sample;

	}
```
</details>


---