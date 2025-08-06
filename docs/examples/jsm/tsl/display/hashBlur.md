[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `hashBlur.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 14 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/hashBlur.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `float` | `three/tsl` |
| `Fn` | `three/tsl` |
| `vec2` | `three/tsl` |
| `uv` | `three/tsl` |
| `sin` | `three/tsl` |
| `rand` | `three/tsl` |
| `degrees` | `three/tsl` |
| `cos` | `three/tsl` |
| `Loop` | `three/tsl` |
| `vec4` | `three/tsl` |
| `premultiplyAlpha` | `three/tsl` |
| `unpremultiplyAlpha` | `three/tsl` |
| `convertToTexture` | `three/tsl` |
| `nodeObject` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `repeats` | `any` | let/var | `nodeObject( options.size ) \|\| float( 45 )` | ✗ |
| `mask` | `any` | let/var | `options.mask \|\| null` | ✗ |
| `premultipliedAlpha` | `any` | let/var | `options.premultipliedAlpha \|\| false` | ✗ |
| `alpha` | `any` | let/var | `mask.sample( uv ).x` | ✗ |
| `targetUV` | `any` | let/var | `textureNode.uvNode \|\| uv()` | ✗ |


---

## Functions

### `draw(uv: any): any`

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