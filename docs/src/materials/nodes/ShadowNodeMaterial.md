[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ShadowNodeMaterial.js`

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
📂 **`src/materials/nodes/ShadowNodeMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeMaterial` | `./NodeMaterial.js` |
| `ShadowMaskModel` | `../../nodes/functions/ShadowMaskModel.js` |
| `ShadowMaterial` | `../ShadowMaterial.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_defaultValues` | `ShadowMaterial` | let/var | `new ShadowMaterial()` | ✗ |


---

## Functions

### `ShadowNodeMaterial.setupLightingModel(): ShadowMaskModel`

**JSDoc:**
```typescript
/**
	 * Setups the lighting model.
	 *
	 * @return {ShadowMaskModel} The lighting model.
	 */
```

**Returns:** `ShadowMaskModel`

<details><summary>Code</summary>

```typescript
setupLightingModel( /*builder*/ ) {

		return new ShadowMaskModel();

	}
```
</details>


---

## Classes

### `ShadowNodeMaterial`

<details><summary>Class Code</summary>

```ts
class ShadowNodeMaterial extends NodeMaterial {

	static get type() {

		return 'ShadowNodeMaterial';

	}

	/**
	 * Constructs a new shadow node material.
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
		this.isShadowNodeMaterial = true;

		/**
		 * Set to `true` because so it's possible to implement
		 * the shadow mask effect.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.lights = true;

		/**
		 * Overwritten since shadow materials are transparent
		 * by default.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.transparent = true;

		this.setDefaultValues( _defaultValues );

		this.setValues( parameters );

	}

	/**
	 * Setups the lighting model.
	 *
	 * @return {ShadowMaskModel} The lighting model.
	 */
	setupLightingModel( /*builder*/ ) {

		return new ShadowMaskModel();

	}

}
```
</details>

#### Methods

##### `setupLightingModel(): ShadowMaskModel`

<details><summary>Code</summary>

```ts
setupLightingModel( /*builder*/ ) {

		return new ShadowMaskModel();

	}
```
</details>


---