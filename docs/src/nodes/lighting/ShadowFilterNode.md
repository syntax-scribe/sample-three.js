[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ShadowFilterNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 📦 Imports | 18 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/nodes/lighting/ShadowFilterNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `float` | `../tsl/TSLBase.js` |
| `vec2` | `../tsl/TSLBase.js` |
| `vec4` | `../tsl/TSLBase.js` |
| `If` | `../tsl/TSLBase.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `reference` | `../accessors/ReferenceNode.js` |
| `texture` | `../accessors/TextureNode.js` |
| `mix` | `../math/MathNode.js` |
| `fract` | `../math/MathNode.js` |
| `step` | `../math/MathNode.js` |
| `max` | `../math/MathNode.js` |
| `clamp` | `../math/MathNode.js` |
| `add` | `../math/OperatorNode.js` |
| `sub` | `../math/OperatorNode.js` |
| `renderGroup` | `../core/UniformGroupNode.js` |
| `NodeMaterial` | `../../materials/nodes/NodeMaterial.js` |
| `objectPosition` | `../accessors/Object3DNode.js` |
| `positionWorld` | `../accessors/Position.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `shadowMaterialLib` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `dx` | `any` | let/var | `texelSize.x` | ✗ |
| `dy` | `any` | let/var | `texelSize.y` | ✗ |
| `uv` | `any` | let/var | `shadowCoord.xy` | ✗ |
| `camera` | `any` | let/var | `light.shadow.camera` | ✗ |
| `depthNode` | `void` | let/var | `light.isPointLight ? linearShadowDistance( light ) : null` | ✗ |


---

## Functions

### `depthCompare(uv: any, compare: any): TextureNode`

**Parameters:**

- **`uv`** `any`
- **`compare`** `any`

**Returns:** `TextureNode`

**Calls:**

- `texture (from ../accessors/TextureNode.js)`
- `depth.depth`
- `depth.compare`

<details><summary>Code</summary>

```typescript
( uv, compare ) => {

		let depth = texture( depthTexture, uv );

		if ( depthTexture.isArrayTexture ) {

			depth = depth.depth( depthLayer );

		}

		return depth.compare( compare );

	}
```
</details>

### `depthCompare(uv: any, compare: any): TextureNode`

**Parameters:**

- **`uv`** `any`
- **`compare`** `any`

**Returns:** `TextureNode`

**Calls:**

- `texture (from ../accessors/TextureNode.js)`
- `depth.depth`
- `depth.compare`

<details><summary>Code</summary>

```typescript
( uv, compare ) => {

		let depth = texture( depthTexture, uv );

		if ( depthTexture.isArrayTexture ) {

			depth = depth.depth( depthLayer );

		}

		return depth.compare( compare );

	}
```
</details>

### `linearShadowDistance(light: any): void`

**Parameters:**

- **`light`** `any`

**Returns:** `void`

**Calls:**

- `reference( 'near', 'float', camera ).setGroup`
- `reference( 'far', 'float', camera ).setGroup`
- `objectPosition (from ../accessors/Object3DNode.js)`
- `linearDistance`

<details><summary>Code</summary>

```typescript
( light ) => {

	const camera = light.shadow.camera;

	const nearDistance = reference( 'near', 'float', camera ).setGroup( renderGroup );
	const farDistance = reference( 'far', 'float', camera ).setGroup( renderGroup );

	const referencePosition = objectPosition( light );

	return linearDistance( referencePosition, nearDistance, farDistance );

}
```
</details>

### `getShadowMaterial(light: Light): NodeMaterial`

**Parameters:**

- **`light`** `Light`

**Returns:** `NodeMaterial`

**Calls:**

- `shadowMaterialLib.get`
- `linearShadowDistance`
- `vec4 (from ../tsl/TSLBase.js)`
- `shadowMaterialLib.set`

<details><summary>Code</summary>

```typescript
( light ) => {

	let material = shadowMaterialLib.get( light );

	if ( material === undefined ) {

		const depthNode = light.isPointLight ? linearShadowDistance( light ) : null;

		material = new NodeMaterial();
		material.colorNode = vec4( 0, 0, 0, 1 );
		material.depthNode = depthNode;
		material.isShadowPassMaterial = true; // Use to avoid other overrideMaterial override material.colorNode unintentionally when using material.shadowNode
		material.name = 'ShadowMaterial';
		material.fog = false;

		shadowMaterialLib.set( light, material );

	}

	return material;

}
```
</details>


---