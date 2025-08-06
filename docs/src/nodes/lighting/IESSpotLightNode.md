[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `IESSpotLightNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/IESSpotLightNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `SpotLightNode` | `./SpotLightNode.js` |
| `texture` | `../accessors/TextureNode.js` |
| `vec2` | `../tsl/TSLBase.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `iesMap` | `any` | let/var | `this.light.iesMap` | ✗ |
| `spotAttenuation` | `any` | let/var | `null` | ✗ |


---

## Functions

### `IESSpotLightNode.getSpotAttenuation(builder: NodeBuilder, angleCosine: any): any`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation to compute an IES conform spot attenuation.
	 *
	 * @param {NodeBuilder} builder - The node builder.
	 * @param {Node<float>} angleCosine - The angle to compute the spot attenuation for.
	 * @return {Node<float>} The spot attenuation.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`angleCosine`** `any`

**Returns:** `any`

**Calls:**

- `angleCosine.acos().mul`
- `texture (from ../accessors/TextureNode.js)`
- `vec2 (from ../tsl/TSLBase.js)`
- `super.getSpotAttenuation`

<details><summary>Code</summary>

```typescript
getSpotAttenuation( builder, angleCosine ) {

		const iesMap = this.light.iesMap;

		let spotAttenuation = null;

		if ( iesMap && iesMap.isTexture === true ) {

			const angle = angleCosine.acos().mul( 1.0 / Math.PI );

			spotAttenuation = texture( iesMap, vec2( angle, 0 ), 0 ).r;

		} else {

			spotAttenuation = super.getSpotAttenuation( angleCosine );

		}

		return spotAttenuation;

	}
```
</details>


---

## Classes

### `IESSpotLightNode`

<details><summary>Class Code</summary>

```ts
class IESSpotLightNode extends SpotLightNode {

	static get type() {

		return 'IESSpotLightNode';

	}

	/**
	 * Overwrites the default implementation to compute an IES conform spot attenuation.
	 *
	 * @param {NodeBuilder} builder - The node builder.
	 * @param {Node<float>} angleCosine - The angle to compute the spot attenuation for.
	 * @return {Node<float>} The spot attenuation.
	 */
	getSpotAttenuation( builder, angleCosine ) {

		const iesMap = this.light.iesMap;

		let spotAttenuation = null;

		if ( iesMap && iesMap.isTexture === true ) {

			const angle = angleCosine.acos().mul( 1.0 / Math.PI );

			spotAttenuation = texture( iesMap, vec2( angle, 0 ), 0 ).r;

		} else {

			spotAttenuation = super.getSpotAttenuation( angleCosine );

		}

		return spotAttenuation;

	}

}
```
</details>

#### Methods

##### `getSpotAttenuation(builder: NodeBuilder, angleCosine: any): any`

<details><summary>Code</summary>

```ts
getSpotAttenuation( builder, angleCosine ) {

		const iesMap = this.light.iesMap;

		let spotAttenuation = null;

		if ( iesMap && iesMap.isTexture === true ) {

			const angle = angleCosine.acos().mul( 1.0 / Math.PI );

			spotAttenuation = texture( iesMap, vec2( angle, 0 ), 0 ).r;

		} else {

			spotAttenuation = super.getSpotAttenuation( angleCosine );

		}

		return spotAttenuation;

	}
```
</details>


---