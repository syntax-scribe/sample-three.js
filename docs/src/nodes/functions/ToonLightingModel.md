[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ToonLightingModel.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 🧱 Classes | 1 |
| 📦 Imports | 11 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/functions/ToonLightingModel.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LightingModel` | `../core/LightingModel.js` |
| `BRDF_Lambert` | `./BSDF/BRDF_Lambert.js` |
| `diffuseColor` | `../core/PropertyNode.js` |
| `normalGeometry` | `../accessors/Normal.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `float` | `../tsl/TSLBase.js` |
| `vec2` | `../tsl/TSLBase.js` |
| `vec3` | `../tsl/TSLBase.js` |
| `mix` | `../math/MathNode.js` |
| `smoothstep` | `../math/MathNode.js` |
| `materialReference` | `../accessors/MaterialReferenceNode.js` |


---

## Functions

### `getUV(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => coord
```
</details>

### `getUV(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => coord
```
</details>

### `getUV(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => coord
```
</details>

### `getUV(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => coord
```
</details>

### `getUV(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => coord
```
</details>

### `getUV(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => coord
```
</details>

### `getUV(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => coord
```
</details>

### `getUV(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => coord
```
</details>

### `ToonLightingModel.direct({ lightDirection, lightColor, reflectedLight }: any, builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Implements the direct lighting. Instead of using a conventional smooth irradiance, the irradiance is
	 * reduced to a small number of discrete shades to create a comic-like, flat look.
	 *
	 * @param {Object} lightData - The light data.
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`{ lightDirection, lightColor, reflectedLight }`** `any`
- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `getGradientIrradiance( { normal: normalGeometry, lightDirection, builder } ).mul`
- `reflectedLight.directDiffuse.addAssign`
- `irradiance.mul`
- `BRDF_Lambert (from ./BSDF/BRDF_Lambert.js)`

<details><summary>Code</summary>

```typescript
direct( { lightDirection, lightColor, reflectedLight }, builder ) {

		const irradiance = getGradientIrradiance( { normal: normalGeometry, lightDirection, builder } ).mul( lightColor );

		reflectedLight.directDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor: diffuseColor.rgb } ) ) );

	}
```
</details>

### `ToonLightingModel.indirect(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Implements the indirect lighting.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `reflectedLight.indirectDiffuse.addAssign`
- `irradiance.mul`
- `BRDF_Lambert (from ./BSDF/BRDF_Lambert.js)`
- `reflectedLight.indirectDiffuse.mulAssign`

<details><summary>Code</summary>

```typescript
indirect( builder ) {

		const { ambientOcclusion, irradiance, reflectedLight } = builder.context;

		reflectedLight.indirectDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor } ) ) );

		reflectedLight.indirectDiffuse.mulAssign( ambientOcclusion );

	}
```
</details>


---

## Classes

### `ToonLightingModel`

<details><summary>Class Code</summary>

```ts
class ToonLightingModel extends LightingModel {

	/**
	 * Implements the direct lighting. Instead of using a conventional smooth irradiance, the irradiance is
	 * reduced to a small number of discrete shades to create a comic-like, flat look.
	 *
	 * @param {Object} lightData - The light data.
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	direct( { lightDirection, lightColor, reflectedLight }, builder ) {

		const irradiance = getGradientIrradiance( { normal: normalGeometry, lightDirection, builder } ).mul( lightColor );

		reflectedLight.directDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor: diffuseColor.rgb } ) ) );

	}

	/**
	 * Implements the indirect lighting.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	indirect( builder ) {

		const { ambientOcclusion, irradiance, reflectedLight } = builder.context;

		reflectedLight.indirectDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor } ) ) );

		reflectedLight.indirectDiffuse.mulAssign( ambientOcclusion );

	}

}
```
</details>

#### Methods

##### `direct({ lightDirection, lightColor, reflectedLight }: any, builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
direct( { lightDirection, lightColor, reflectedLight }, builder ) {

		const irradiance = getGradientIrradiance( { normal: normalGeometry, lightDirection, builder } ).mul( lightColor );

		reflectedLight.directDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor: diffuseColor.rgb } ) ) );

	}
```
</details>

##### `indirect(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
indirect( builder ) {

		const { ambientOcclusion, irradiance, reflectedLight } = builder.context;

		reflectedLight.indirectDiffuse.addAssign( irradiance.mul( BRDF_Lambert( { diffuseColor } ) ) );

		reflectedLight.indirectDiffuse.mulAssign( ambientOcclusion );

	}
```
</details>


---