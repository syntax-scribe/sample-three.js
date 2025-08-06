[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Fog.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/nodes/fog/Fog.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `positionView` | `../accessors/Position.js` |
| `smoothstep` | `../math/MathNode.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `output` | `../tsl/TSLBase.js` |
| `vec4` | `../tsl/TSLBase.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `viewZ` | `any` | let/var | `*not shown*` | ✗ |
| `getViewZ` | `any` | let/var | `builder.context.getViewZ` | ✗ |


---

## Functions

### `getViewZNode(builder: NodeBuilder): Node`

**JSDoc:**
```typescript
/**
 * Returns a node that represents the `z` coordinate in view space
 * for the current fragment. It's a different representation of the
 * default depth value.
 *
 * This value can be part of a computation that defines how the fog
 * density increases when moving away from the camera.
 *
 * @param {NodeBuilder} builder - The current node builder.
 * @return {Node} The viewZ node.
 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `Node`

**Calls:**

- `getViewZ`
- `( viewZ || positionView.z ).negate`

<details><summary>Code</summary>

```typescript
function getViewZNode( builder ) {

	let viewZ;

	const getViewZ = builder.context.getViewZ;

	if ( getViewZ !== undefined ) {

		viewZ = getViewZ( this );

	}

	return ( viewZ || positionView.z ).negate();

}
```
</details>

### `rangeFog(color: Node, near: Node, far: Node): Function`

**JSDoc:**
```typescript
/**
 * @tsl
 * @function
 * @deprecated since r171. Use `fog( color, rangeFogFactor( near, far ) )` instead.
 *
 * @param {Node} color
 * @param {Node} near
 * @param {Node} far
 * @returns {Function}
 */
```

**Parameters:**

- **`color`** `Node`
- **`near`** `Node`
- **`far`** `Node`

**Returns:** `Function`

**Calls:**

- `console.warn`
- `fog`
- `rangeFogFactor`

<details><summary>Code</summary>

```typescript
export function rangeFog( color, near, far ) { // @deprecated, r171

	console.warn( 'THREE.TSL: "rangeFog( color, near, far )" is deprecated. Use "fog( color, rangeFogFactor( near, far ) )" instead.' );
	return fog( color, rangeFogFactor( near, far ) );

}
```
</details>

### `densityFog(color: Node, density: Node): Function`

**JSDoc:**
```typescript
/**
 * @tsl
 * @function
 * @deprecated since r171. Use `fog( color, densityFogFactor( density ) )` instead.
 *
 * @param {Node} color
 * @param {Node} density
 * @returns {Function}
 */
```

**Parameters:**

- **`color`** `Node`
- **`density`** `Node`

**Returns:** `Function`

**Calls:**

- `console.warn`
- `fog`
- `densityFogFactor`

<details><summary>Code</summary>

```typescript
export function densityFog( color, density ) { // @deprecated, r171

	console.warn( 'THREE.TSL: "densityFog( color, density )" is deprecated. Use "fog( color, densityFogFactor( density ) )" instead.' );
	return fog( color, densityFogFactor( density ) );

}
```
</details>


---