[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MeshNormalNodeMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/nodes/MeshNormalNodeMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeMaterial` | `./NodeMaterial.js` |
| `diffuseColor` | `../../nodes/core/PropertyNode.js` |
| `directionToColor` | `../../nodes/utils/Packing.js` |
| `materialOpacity` | `../../nodes/accessors/MaterialNode.js` |
| `normalView` | `../../nodes/accessors/Normal.js` |
| `colorSpaceToWorking` | `../../nodes/display/ColorSpaceNode.js` |
| `float` | `../../nodes/tsl/TSLBase.js` |
| `vec4` | `../../nodes/tsl/TSLBase.js` |
| `SRGBColorSpace` | `../../constants.js` |
| `MeshNormalMaterial` | `../MeshNormalMaterial.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_defaultValues` | `MeshNormalMaterial` | let/var | `new MeshNormalMaterial()` | ✗ |
| `opacityNode` | `any` | let/var | `this.opacityNode ? float( this.opacityNode ) : materialOpacity` | ✗ |


---

## Functions

### `MeshNormalNodeMaterial.setupDiffuseColor(): void`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation by computing the diffuse color
	 * based on the normal data.
	 */
```

**Returns:** `void`

**Calls:**

- `float (from ../../nodes/tsl/TSLBase.js)`
- `diffuseColor.assign`
- `colorSpaceToWorking (from ../../nodes/display/ColorSpaceNode.js)`
- `vec4 (from ../../nodes/tsl/TSLBase.js)`
- `directionToColor (from ../../nodes/utils/Packing.js)`

**Internal Comments:**
```
// By convention, a normal packed to RGB is in sRGB color space. Convert it to working color space. (x4)
```

<details><summary>Code</summary>

```typescript
setupDiffuseColor() {

		const opacityNode = this.opacityNode ? float( this.opacityNode ) : materialOpacity;

		// By convention, a normal packed to RGB is in sRGB color space. Convert it to working color space.

		diffuseColor.assign( colorSpaceToWorking( vec4( directionToColor( normalView ), opacityNode ), SRGBColorSpace ) );

	}
```
</details>


---

## Classes

### `MeshNormalNodeMaterial`

<details><summary>Class Code</summary>

```ts
class MeshNormalNodeMaterial extends NodeMaterial {

	static get type() {

		return 'MeshNormalNodeMaterial';

	}

	/**
	 * Constructs a new mesh normal node material.
	 *
	 * @param {Object} [parameters] - The configuration parameter.
	 */
	constructor( parameters ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isMeshNormalNodeMaterial = true;

		this.setDefaultValues( _defaultValues );

		this.setValues( parameters );

	}

	/**
	 * Overwrites the default implementation by computing the diffuse color
	 * based on the normal data.
	 */
	setupDiffuseColor() {

		const opacityNode = this.opacityNode ? float( this.opacityNode ) : materialOpacity;

		// By convention, a normal packed to RGB is in sRGB color space. Convert it to working color space.

		diffuseColor.assign( colorSpaceToWorking( vec4( directionToColor( normalView ), opacityNode ), SRGBColorSpace ) );

	}

}
```
</details>

#### Methods

##### `setupDiffuseColor(): void`

<details><summary>Code</summary>

```ts
setupDiffuseColor() {

		const opacityNode = this.opacityNode ? float( this.opacityNode ) : materialOpacity;

		// By convention, a normal packed to RGB is in sRGB color space. Convert it to working color space.

		diffuseColor.assign( colorSpaceToWorking( vec4( directionToColor( normalView ), opacityNode ), SRGBColorSpace ) );

	}
```
</details>


---