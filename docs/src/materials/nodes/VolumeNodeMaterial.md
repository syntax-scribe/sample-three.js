[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `VolumeNodeMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/nodes/VolumeNodeMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeMaterial` | `./NodeMaterial.js` |
| `VolumetricLightingModel` | `../../nodes/functions/VolumetricLightingModel.js` |
| `BackSide` | `../../constants.js` |


---

## Functions

### `VolumeNodeMaterial.setupLightingModel(): VolumetricLightingModel`

**Returns:** `VolumetricLightingModel`

<details><summary>Code</summary>

```typescript
setupLightingModel() {

		return new VolumetricLightingModel();

	}
```
</details>


---

## Classes

### `VolumeNodeMaterial`

<details><summary>Class Code</summary>

```ts
class VolumeNodeMaterial extends NodeMaterial {

	static get type() {

		return 'VolumeNodeMaterial';

	}

	/**
	 * Constructs a new volume node material.
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
		this.isVolumeNodeMaterial = true;

		/**
		 * Number of steps used for raymarching.
		 *
		 * @type {number}
		 * @default 25
		 */
		this.steps = 25;

		/**
		 * Offsets the distance a ray has been traveled through a volume.
		 * Can be used to implement dithering to reduce banding.
		 *
		 * @type {Node<float>}
		 * @default null
		 */
		this.offsetNode = null;

		/**
		 * Node used for scattering calculations.
		 *
		 * @type {Function|FunctionNode<vec4>}
		 * @default null
		 */
		this.scatteringNode = null;

		this.lights = true;

		this.transparent = true;
		this.side = BackSide;

		this.depthTest = false;
		this.depthWrite = false;

		this.setValues( parameters );

	}

	setupLightingModel() {

		return new VolumetricLightingModel();

	}

}
```
</details>

#### Methods

##### `setupLightingModel(): VolumetricLightingModel`

<details><summary>Code</summary>

```ts
setupLightingModel() {

		return new VolumetricLightingModel();

	}
```
</details>


---