[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TSLBase.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🔄 Re-exports | 24 |

## 📚 Table of Contents

- [Re-exports](#re-exports)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/nodes/tsl/TSLBase.js`**

## Re-exports

| Type | Source | Exported Names |
|------|--------|----------------|
| namespace | `./TSLCore.js` | * |
| namespace | `../core/ArrayNode.js` | * |
| namespace | `../core/UniformNode.js` | * |
| namespace | `../core/PropertyNode.js` | * |
| namespace | `../core/AssignNode.js` | * |
| namespace | `../code/FunctionCallNode.js` | * |
| namespace | `../math/OperatorNode.js` | * |
| namespace | `../math/MathNode.js` | * |
| namespace | `../math/ConditionalNode.js` | * |
| namespace | `../core/ContextNode.js` | * |
| namespace | `../core/VarNode.js` | * |
| namespace | `../core/VaryingNode.js` | * |
| namespace | `../display/ColorSpaceNode.js` | * |
| namespace | `../display/ToneMappingNode.js` | * |
| namespace | `../accessors/BufferAttributeNode.js` | * |
| namespace | `../gpgpu/ComputeNode.js` | * |
| namespace | `../core/CacheNode.js` | * |
| namespace | `../core/BypassNode.js` | * |
| namespace | `../utils/RemapNode.js` | * |
| namespace | `../code/ExpressionNode.js` | * |
| namespace | `../utils/Discard.js` | * |
| namespace | `../display/RenderOutputNode.js` | * |
| namespace | `../utils/DebugNode.js` | * |
| namespace | `../core/SubBuildNode.js` | * |


---

## Functions

### `addNodeElement(name: any): void`

**Parameters:**

- **`name`** `any`

**Returns:** `void`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
export function addNodeElement( name/*, nodeElement*/ ) {

	console.warn( 'THREE.TSL: AddNodeElement has been removed in favor of tree-shaking. Trying add', name );

}
```
</details>


---