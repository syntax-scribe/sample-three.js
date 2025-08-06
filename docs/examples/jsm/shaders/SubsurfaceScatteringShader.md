[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SubsurfaceScatteringShader.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/shaders/SubsurfaceScatteringShader.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `three` |
| `ShaderChunk` | `three` |
| `ShaderLib` | `three` |
| `UniformsUtils` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `SubsurfaceScatteringShader` | `ShaderMaterial` | let/var | `{ name: 'SubsurfaceScatteringShader', uniforms: UniformsUtils.merge( [ Shader...` | ✗ |


---

## Functions

### `replaceAll(string: any, find: any, replace: any): any`

**Parameters:**

- **`string`** `any`
- **`find`** `any`
- **`replace`** `any`

**Returns:** `any`

**Calls:**

- `string.split( find ).join`

<details><summary>Code</summary>

```typescript
function replaceAll( string, find, replace ) {

	return string.split( find ).join( replace );

}
```
</details>


---