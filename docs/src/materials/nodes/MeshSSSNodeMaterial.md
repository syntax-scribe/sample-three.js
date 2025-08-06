[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MeshSSSNodeMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 2 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/nodes/MeshSSSNodeMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `MeshPhysicalNodeMaterial` | `./MeshPhysicalNodeMaterial.js` |
| `PhysicalLightingModel` | `../../nodes/functions/PhysicalLightingModel.js` |
| `normalView` | `../../nodes/accessors/Normal.js` |
| `positionViewDirection` | `../../nodes/accessors/Position.js` |
| `float` | `../../nodes/tsl/TSLBase.js` |
| `vec3` | `../../nodes/tsl/TSLBase.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `material` | `any` | let/var | `builder.material` | ✗ |


---

## Functions

### `SSSLightingModel.direct({ lightDirection, lightColor, reflectedLight }: any, builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Extends the default implementation with a SSS term.
	 *
	 * Reference: [Approximating Translucency for a Fast, Cheap and Convincing Subsurface Scattering Look]{@link https://colinbarrebrisebois.com/2011/03/07/gdc-2011-approximating-translucency-for-a-fast-cheap-and-convincing-subsurface-scattering-look/}
	 *
	 * @param {Object} input - The input data.
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`{ lightDirection, lightColor, reflectedLight }`** `any`
- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `lightDirection.add( normalView.mul( thicknessDistortionNode ) ).normalize`
- `float (from ../../nodes/tsl/TSLBase.js)`
- `positionViewDirection.dot( scatteringHalf.negate() ).saturate().pow( thicknessPowerNode ).mul`
- `vec3 (from ../../nodes/tsl/TSLBase.js)`
- `scatteringDot.add( thicknessAmbientNode ).mul`
- `reflectedLight.directDiffuse.addAssign`
- `scatteringIllu.mul`
- `thicknessAttenuationNode.mul`
- `super.direct`

<details><summary>Code</summary>

```typescript
direct( { lightDirection, lightColor, reflectedLight }, builder ) {

		if ( this.useSSS === true ) {

			const material = builder.material;

			const { thicknessColorNode, thicknessDistortionNode, thicknessAmbientNode, thicknessAttenuationNode, thicknessPowerNode, thicknessScaleNode } = material;

			const scatteringHalf = lightDirection.add( normalView.mul( thicknessDistortionNode ) ).normalize();
			const scatteringDot = float( positionViewDirection.dot( scatteringHalf.negate() ).saturate().pow( thicknessPowerNode ).mul( thicknessScaleNode ) );
			const scatteringIllu = vec3( scatteringDot.add( thicknessAmbientNode ).mul( thicknessColorNode ) );

			reflectedLight.directDiffuse.addAssign( scatteringIllu.mul( thicknessAttenuationNode.mul( lightColor ) ) );

		}

		super.direct( { lightDirection, lightColor, reflectedLight }, builder );

	}
```
</details>

### `MeshSSSNodeMaterial.setupLightingModel(): SSSLightingModel`

**JSDoc:**
```typescript
/**
	 * Setups the lighting model.
	 *
	 * @return {SSSLightingModel} The lighting model.
	 */
```

**Returns:** `SSSLightingModel`

<details><summary>Code</summary>

```typescript
setupLightingModel( /*builder*/ ) {

		return new SSSLightingModel( this.useClearcoat, this.useSheen, this.useIridescence, this.useAnisotropy, this.useTransmission, this.useDispersion, this.useSSS );

	}
```
</details>

### `MeshSSSNodeMaterial.copy(source: any): NodeMaterial`

**Parameters:**

- **`source`** `any`

**Returns:** `NodeMaterial`

**Calls:**

- `super.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		this.thicknessColorNode = source.thicknessColorNode;
		this.thicknessDistortionNode = source.thicknessDistortionNode;
		this.thicknessAmbientNode = source.thicknessAmbientNode;
		this.thicknessAttenuationNode = source.thicknessAttenuationNode;
		this.thicknessPowerNode = source.thicknessPowerNode;
		this.thicknessScaleNode = source.thicknessScaleNode;

		return super.copy( source );

	}
```
</details>


---

## Classes

### `SSSLightingModel`

<details><summary>Class Code</summary>

```ts
class SSSLightingModel extends PhysicalLightingModel {

	/**
	 * Constructs a new physical lighting model.
	 *
	 * @param {boolean} [clearcoat=false] - Whether clearcoat is supported or not.
	 * @param {boolean} [sheen=false] - Whether sheen is supported or not.
	 * @param {boolean} [iridescence=false] - Whether iridescence is supported or not.
	 * @param {boolean} [anisotropy=false] - Whether anisotropy is supported or not.
	 * @param {boolean} [transmission=false] - Whether transmission is supported or not.
	 * @param {boolean} [dispersion=false] - Whether dispersion is supported or not.
	 * @param {boolean} [sss=false] - Whether SSS is supported or not.
	 */
	constructor( clearcoat = false, sheen = false, iridescence = false, anisotropy = false, transmission = false, dispersion = false, sss = false ) {

		super( clearcoat, sheen, iridescence, anisotropy, transmission, dispersion );

		/**
		 * Whether the lighting model should use SSS or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.useSSS = sss;

	}

	/**
	 * Extends the default implementation with a SSS term.
	 *
	 * Reference: [Approximating Translucency for a Fast, Cheap and Convincing Subsurface Scattering Look]{@link https://colinbarrebrisebois.com/2011/03/07/gdc-2011-approximating-translucency-for-a-fast-cheap-and-convincing-subsurface-scattering-look/}
	 *
	 * @param {Object} input - The input data.
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	direct( { lightDirection, lightColor, reflectedLight }, builder ) {

		if ( this.useSSS === true ) {

			const material = builder.material;

			const { thicknessColorNode, thicknessDistortionNode, thicknessAmbientNode, thicknessAttenuationNode, thicknessPowerNode, thicknessScaleNode } = material;

			const scatteringHalf = lightDirection.add( normalView.mul( thicknessDistortionNode ) ).normalize();
			const scatteringDot = float( positionViewDirection.dot( scatteringHalf.negate() ).saturate().pow( thicknessPowerNode ).mul( thicknessScaleNode ) );
			const scatteringIllu = vec3( scatteringDot.add( thicknessAmbientNode ).mul( thicknessColorNode ) );

			reflectedLight.directDiffuse.addAssign( scatteringIllu.mul( thicknessAttenuationNode.mul( lightColor ) ) );

		}

		super.direct( { lightDirection, lightColor, reflectedLight }, builder );

	}

}
```
</details>

#### Methods

##### `direct({ lightDirection, lightColor, reflectedLight }: any, builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
direct( { lightDirection, lightColor, reflectedLight }, builder ) {

		if ( this.useSSS === true ) {

			const material = builder.material;

			const { thicknessColorNode, thicknessDistortionNode, thicknessAmbientNode, thicknessAttenuationNode, thicknessPowerNode, thicknessScaleNode } = material;

			const scatteringHalf = lightDirection.add( normalView.mul( thicknessDistortionNode ) ).normalize();
			const scatteringDot = float( positionViewDirection.dot( scatteringHalf.negate() ).saturate().pow( thicknessPowerNode ).mul( thicknessScaleNode ) );
			const scatteringIllu = vec3( scatteringDot.add( thicknessAmbientNode ).mul( thicknessColorNode ) );

			reflectedLight.directDiffuse.addAssign( scatteringIllu.mul( thicknessAttenuationNode.mul( lightColor ) ) );

		}

		super.direct( { lightDirection, lightColor, reflectedLight }, builder );

	}
```
</details>

### `MeshSSSNodeMaterial`

<details><summary>Class Code</summary>

```ts
class MeshSSSNodeMaterial extends MeshPhysicalNodeMaterial {

	static get type() {

		return 'MeshSSSNodeMaterial';

	}

	/**
	 * Constructs a new mesh SSS node material.
	 *
	 * @param {Object} [parameters] - The configuration parameter.
	 */
	constructor( parameters ) {

		super( parameters );

		/**
		 * Represents the thickness color.
		 *
		 * @type {?Node<vec3>}
		 * @default null
		 */
		this.thicknessColorNode = null;

		/**
		 * Represents the distortion factor.
		 *
		 * @type {?Node<float>}
		 */
		this.thicknessDistortionNode = float( 0.1 );

		/**
		 * Represents the thickness ambient factor.
		 *
		 * @type {?Node<float>}
		 */
		this.thicknessAmbientNode = float( 0.0 );

		/**
		 * Represents the thickness attenuation.
		 *
		 * @type {?Node<float>}
		 */
		this.thicknessAttenuationNode = float( .1 );

		/**
		 * Represents the thickness power.
		 *
		 * @type {?Node<float>}
		 */
		this.thicknessPowerNode = float( 2.0 );

		/**
		 * Represents the thickness scale.
		 *
		 * @type {?Node<float>}
		 */
		this.thicknessScaleNode = float( 10.0 );

	}

	/**
	 * Whether the lighting model should use SSS or not.
	 *
	 * @type {boolean}
	 * @default true
	 */
	get useSSS() {

		return this.thicknessColorNode !== null;

	}

	/**
	 * Setups the lighting model.
	 *
	 * @return {SSSLightingModel} The lighting model.
	 */
	setupLightingModel( /*builder*/ ) {

		return new SSSLightingModel( this.useClearcoat, this.useSheen, this.useIridescence, this.useAnisotropy, this.useTransmission, this.useDispersion, this.useSSS );

	}

	copy( source ) {

		this.thicknessColorNode = source.thicknessColorNode;
		this.thicknessDistortionNode = source.thicknessDistortionNode;
		this.thicknessAmbientNode = source.thicknessAmbientNode;
		this.thicknessAttenuationNode = source.thicknessAttenuationNode;
		this.thicknessPowerNode = source.thicknessPowerNode;
		this.thicknessScaleNode = source.thicknessScaleNode;

		return super.copy( source );

	}

}
```
</details>

#### Methods

##### `setupLightingModel(): SSSLightingModel`

<details><summary>Code</summary>

```ts
setupLightingModel( /*builder*/ ) {

		return new SSSLightingModel( this.useClearcoat, this.useSheen, this.useIridescence, this.useAnisotropy, this.useTransmission, this.useDispersion, this.useSSS );

	}
```
</details>

##### `copy(source: any): NodeMaterial`

<details><summary>Code</summary>

```ts
copy( source ) {

		this.thicknessColorNode = source.thicknessColorNode;
		this.thicknessDistortionNode = source.thicknessDistortionNode;
		this.thicknessAmbientNode = source.thicknessAmbientNode;
		this.thicknessAttenuationNode = source.thicknessAttenuationNode;
		this.thicknessPowerNode = source.thicknessPowerNode;
		this.thicknessScaleNode = source.thicknessScaleNode;

		return super.copy( source );

	}
```
</details>


---