[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `backgroundCube.glsl.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)

## 🛠️ File Location:
📂 **`src/renderers/shaders/ShaderLib/backgroundCube.glsl.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `vertex` | `"\nvarying vec3 vWorldDirection;\n\n#...` | let/var | `` varying vec3 vWorldDirection; #include <common> void main() { vWorldDirecti...` | ✓ |
| `fragment` | `"\n\n#ifdef ENVMAP_TYPE_CUBE\n\n\tuni...` | let/var | `` #ifdef ENVMAP_TYPE_CUBE uniform samplerCube envMap; #elif defined( ENVMAP_T...` | ✓ |


---