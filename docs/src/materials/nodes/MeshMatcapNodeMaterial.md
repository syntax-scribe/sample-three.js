[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MeshMatcapNodeMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/nodes/MeshMatcapNodeMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeMaterial` | `./NodeMaterial.js` |
| `materialReference` | `../../nodes/accessors/MaterialReferenceNode.js` |
| `diffuseColor` | `../../nodes/core/PropertyNode.js` |
| `vec3` | `../../nodes/tsl/TSLBase.js` |
| `mix` | `../../nodes/math/MathNode.js` |
| `matcapUV` | `../../nodes/utils/MatcapUV.js` |
| `MeshMatcapMaterial` | `../MeshMatcapMaterial.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_defaultValues` | `MeshMatcapMaterial` | let/var | `new MeshMatcapMaterial()` | ✗ |
| `uv` | `any` | let/var | `matcapUV` | ✗ |
| `matcapColor` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `MeshMatcapNodeMaterial.setupVariants(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Setups the matcap specific node variables.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `materialReference( 'matcap', 'texture' ).context`
- `vec3 (from ../../nodes/tsl/TSLBase.js)`
- `mix (from ../../nodes/math/MathNode.js)`
- `diffuseColor.rgb.mulAssign`

<details><summary>Code</summary>

```typescript
setupVariants( builder ) {

		const uv = matcapUV;

		let matcapColor;

		if ( builder.material.matcap ) {

			matcapColor = materialReference( 'matcap', 'texture' ).context( { getUV: () => uv } );

		} else {

			matcapColor = vec3( mix( 0.2, 0.8, uv.y ) ); // default if matcap is missing

		}

		diffuseColor.rgb.mulAssign( matcapColor.rgb );

	}
```
</details>

### `getUV(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => uv
```
</details>

### `getUV(): any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
() => uv
```
</details>


---

## Classes

### `MeshMatcapNodeMaterial`

<details><summary>Class Code</summary>

```ts
class MeshMatcapNodeMaterial extends NodeMaterial {

	static get type() {

		return 'MeshMatcapNodeMaterial';

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
		this.isMeshMatcapNodeMaterial = true;

		this.setDefaultValues( _defaultValues );

		this.setValues( parameters );

	}

	/**
	 * Setups the matcap specific node variables.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	setupVariants( builder ) {

		const uv = matcapUV;

		let matcapColor;

		if ( builder.material.matcap ) {

			matcapColor = materialReference( 'matcap', 'texture' ).context( { getUV: () => uv } );

		} else {

			matcapColor = vec3( mix( 0.2, 0.8, uv.y ) ); // default if matcap is missing

		}

		diffuseColor.rgb.mulAssign( matcapColor.rgb );

	}

}
```
</details>

#### Methods

##### `setupVariants(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
setupVariants( builder ) {

		const uv = matcapUV;

		let matcapColor;

		if ( builder.material.matcap ) {

			matcapColor = materialReference( 'matcap', 'texture' ).context( { getUV: () => uv } );

		} else {

			matcapColor = vec3( mix( 0.2, 0.8, uv.y ) ); // default if matcap is missing

		}

		diffuseColor.rgb.mulAssign( matcapColor.rgb );

	}
```
</details>


---