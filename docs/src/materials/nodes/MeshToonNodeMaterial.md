[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MeshToonNodeMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/nodes/MeshToonNodeMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeMaterial` | `./NodeMaterial.js` |
| `ToonLightingModel` | `../../nodes/functions/ToonLightingModel.js` |
| `MeshToonMaterial` | `../MeshToonMaterial.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_defaultValues` | `MeshToonMaterial` | let/var | `new MeshToonMaterial()` | ✗ |


---

## Functions

### `MeshToonNodeMaterial.setupLightingModel(): ToonLightingModel`

**JSDoc:**
```typescript
/**
	 * Setups the lighting model.
	 *
	 * @return {ToonLightingModel} The lighting model.
	 */
```

**Returns:** `ToonLightingModel`

<details><summary>Code</summary>

```typescript
setupLightingModel( /*builder*/ ) {

		return new ToonLightingModel();

	}
```
</details>


---

## Classes

### `MeshToonNodeMaterial`

<details><summary>Class Code</summary>

```ts
class MeshToonNodeMaterial extends NodeMaterial {

	static get type() {

		return 'MeshToonNodeMaterial';

	}

	/**
	 * Constructs a new mesh toon node material.
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
		this.isMeshToonNodeMaterial = true;

		/**
		 * Set to `true` because toon materials react on lights.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.lights = true;

		this.setDefaultValues( _defaultValues );

		this.setValues( parameters );

	}

	/**
	 * Setups the lighting model.
	 *
	 * @return {ToonLightingModel} The lighting model.
	 */
	setupLightingModel( /*builder*/ ) {

		return new ToonLightingModel();

	}

}
```
</details>

#### Methods

##### `setupLightingModel(): ToonLightingModel`

<details><summary>Code</summary>

```ts
setupLightingModel( /*builder*/ ) {

		return new ToonLightingModel();

	}
```
</details>


---