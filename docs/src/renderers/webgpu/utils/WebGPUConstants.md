[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `WebGPUConstants.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 📊 Variables & Constants | 24 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)

## 🛠️ File Location:
📂 **`src/renderers/webgpu/utils/WebGPUConstants.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `GPUPrimitiveTopology` | `{ PointList: string; LineList: string...` | let/var | `{ PointList: 'point-list', LineList: 'line-list', LineStrip: 'line-strip', Tr...` | ✓ |
| `GPUCompareFunction` | `{ Never: string; Less: string; Equal:...` | let/var | `{ Never: 'never', Less: 'less', Equal: 'equal', LessEqual: 'less-equal', Grea...` | ✓ |
| `GPUStoreOp` | `{ Store: string; Discard: string; }` | let/var | `{ Store: 'store', Discard: 'discard' }` | ✓ |
| `GPULoadOp` | `{ Load: string; Clear: string; }` | let/var | `{ Load: 'load', Clear: 'clear' }` | ✓ |
| `GPUFrontFace` | `{ CCW: string; CW: string; }` | let/var | `{ CCW: 'ccw', CW: 'cw' }` | ✓ |
| `GPUCullMode` | `{ None: string; Front: string; Back: ...` | let/var | `{ None: 'none', Front: 'front', Back: 'back' }` | ✓ |
| `GPUIndexFormat` | `{ Uint16: string; Uint32: string; }` | let/var | `{ Uint16: 'uint16', Uint32: 'uint32' }` | ✓ |
| `GPUVertexFormat` | `{ Uint8x2: string; Uint8x4: string; S...` | let/var | `{ Uint8x2: 'uint8x2', Uint8x4: 'uint8x4', Sint8x2: 'sint8x2', Sint8x4: 'sint8...` | ✓ |
| `GPUTextureFormat` | `{ R8Unorm: string; R8Snorm: string; R...` | let/var | `{ // 8-bit formats R8Unorm: 'r8unorm', R8Snorm: 'r8snorm', R8Uint: 'r8uint', ...` | ✓ |
| `GPUAddressMode` | `{ ClampToEdge: string; Repeat: string...` | let/var | `{ ClampToEdge: 'clamp-to-edge', Repeat: 'repeat', MirrorRepeat: 'mirror-repea...` | ✓ |
| `GPUFilterMode` | `{ Linear: string; Nearest: string; }` | let/var | `{ Linear: 'linear', Nearest: 'nearest' }` | ✓ |
| `GPUBlendFactor` | `{ Zero: string; One: string; Src: str...` | let/var | `{ Zero: 'zero', One: 'one', Src: 'src', OneMinusSrc: 'one-minus-src', SrcAlph...` | ✓ |
| `GPUBlendOperation` | `{ Add: string; Subtract: string; Reve...` | let/var | `{ Add: 'add', Subtract: 'subtract', ReverseSubtract: 'reverse-subtract', Min:...` | ✓ |
| `GPUColorWriteFlags` | `{ None: number; Red: number; Green: n...` | let/var | `{ None: 0, Red: 0x1, Green: 0x2, Blue: 0x4, Alpha: 0x8, All: 0xF }` | ✓ |
| `GPUStencilOperation` | `{ Keep: string; Zero: string; Replace...` | let/var | `{ Keep: 'keep', Zero: 'zero', Replace: 'replace', Invert: 'invert', Increment...` | ✓ |
| `GPUBufferBindingType` | `{ Uniform: string; Storage: string; R...` | let/var | `{ Uniform: 'uniform', Storage: 'storage', ReadOnlyStorage: 'read-only-storage' }` | ✓ |
| `GPUStorageTextureAccess` | `{ WriteOnly: string; ReadOnly: string...` | let/var | `{ WriteOnly: 'write-only', ReadOnly: 'read-only', ReadWrite: 'read-write', }` | ✓ |
| `GPUSamplerBindingType` | `{ Filtering: string; NonFiltering: st...` | let/var | `{ Filtering: 'filtering', NonFiltering: 'non-filtering', Comparison: 'compari...` | ✓ |
| `GPUTextureSampleType` | `{ Float: string; UnfilterableFloat: s...` | let/var | `{ Float: 'float', UnfilterableFloat: 'unfilterable-float', Depth: 'depth', SI...` | ✓ |
| `GPUTextureDimension` | `{ OneD: string; TwoD: string; ThreeD:...` | let/var | `{ OneD: '1d', TwoD: '2d', ThreeD: '3d' }` | ✓ |
| `GPUTextureViewDimension` | `{ OneD: string; TwoD: string; TwoDArr...` | let/var | `{ OneD: '1d', TwoD: '2d', TwoDArray: '2d-array', Cube: 'cube', CubeArray: 'cu...` | ✓ |
| `GPUTextureAspect` | `{ All: string; StencilOnly: string; D...` | let/var | `{ All: 'all', StencilOnly: 'stencil-only', DepthOnly: 'depth-only' }` | ✓ |
| `GPUInputStepMode` | `{ Vertex: string; Instance: string; }` | let/var | `{ Vertex: 'vertex', Instance: 'instance' }` | ✓ |
| `GPUFeatureName` | `{ CoreFeaturesAndLimits: string; Dept...` | let/var | `{ CoreFeaturesAndLimits: 'core-features-and-limits', DepthClipControl: 'depth...` | ✓ |


---