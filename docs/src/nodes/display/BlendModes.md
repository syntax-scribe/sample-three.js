[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BlendModes.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 📦 Imports | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/nodes/display/BlendModes.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Fn` | `../tsl/TSLBase.js` |
| `If` | `../tsl/TSLBase.js` |
| `vec4` | `../tsl/TSLBase.js` |
| `mix` | `../math/MathNode.js` |
| `min` | `../math/MathNode.js` |
| `step` | `../math/MathNode.js` |


---

## Functions

### `burn(params: any[]): Function`

**Parameters:**

- **`params`** `any[]`

**Returns:** `Function`

**Calls:**

- `console.warn`
- `blendBurn`

<details><summary>Code</summary>

```typescript
( ...params ) => { // @deprecated, r171

	console.warn( 'THREE.TSL: "burn" has been renamed. Use "blendBurn" instead.' );
	return blendBurn( params );

}
```
</details>

### `dodge(params: any[]): Function`

**Parameters:**

- **`params`** `any[]`

**Returns:** `Function`

**Calls:**

- `console.warn`
- `blendDodge`

<details><summary>Code</summary>

```typescript
( ...params ) => { // @deprecated, r171

	console.warn( 'THREE.TSL: "dodge" has been renamed. Use "blendDodge" instead.' );
	return blendDodge( params );

}
```
</details>

### `screen(params: any[]): Function`

**Parameters:**

- **`params`** `any[]`

**Returns:** `Function`

**Calls:**

- `console.warn`
- `blendScreen`

<details><summary>Code</summary>

```typescript
( ...params ) => { // @deprecated, r171

	console.warn( 'THREE.TSL: "screen" has been renamed. Use "blendScreen" instead.' );
	return blendScreen( params );

}
```
</details>

### `overlay(params: any[]): Function`

**Parameters:**

- **`params`** `any[]`

**Returns:** `Function`

**Calls:**

- `console.warn`
- `blendOverlay`

<details><summary>Code</summary>

```typescript
( ...params ) => { // @deprecated, r171

	console.warn( 'THREE.TSL: "overlay" has been renamed. Use "blendOverlay" instead.' );
	return blendOverlay( params );

}
```
</details>


---