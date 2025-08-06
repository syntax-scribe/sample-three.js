[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `constants.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 📊 Variables & Constants | 8 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)

## 🛠️ File Location:
📂 **`src/nodes/core/constants.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `NodeShaderStage` | `{ VERTEX: string; FRAGMENT: string; }` | let/var | `{ VERTEX: 'vertex', FRAGMENT: 'fragment' }` | ✓ |
| `NodeUpdateType` | `{ NONE: string; FRAME: string; RENDER...` | let/var | `{ NONE: 'none', FRAME: 'frame', RENDER: 'render', OBJECT: 'object' }` | ✓ |
| `NodeType` | `{ BOOLEAN: string; INTEGER: string; F...` | let/var | `{ BOOLEAN: 'bool', INTEGER: 'int', FLOAT: 'float', VECTOR2: 'vec2', VECTOR3: ...` | ✓ |
| `NodeAccess` | `{ READ_ONLY: string; WRITE_ONLY: stri...` | let/var | `{ READ_ONLY: 'readOnly', WRITE_ONLY: 'writeOnly', READ_WRITE: 'readWrite', }` | ✓ |
| `defaultShaderStages` | `string[]` | let/var | `[ 'fragment', 'vertex' ]` | ✓ |
| `defaultBuildStages` | `string[]` | let/var | `[ 'setup', 'analyze', 'generate' ]` | ✓ |
| `shaderStages` | `string[]` | let/var | `[ ...defaultShaderStages, 'compute' ]` | ✓ |
| `vectorComponents` | `string[]` | let/var | `[ 'x', 'y', 'z', 'w' ]` | ✓ |


---