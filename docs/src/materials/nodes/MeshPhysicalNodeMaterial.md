[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MeshPhysicalNodeMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 52 |
| 📊 Variables & Constants | 14 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/nodes/MeshPhysicalNodeMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `clearcoat` | `../../nodes/core/PropertyNode.js` |
| `clearcoatRoughness` | `../../nodes/core/PropertyNode.js` |
| `sheen` | `../../nodes/core/PropertyNode.js` |
| `sheenRoughness` | `../../nodes/core/PropertyNode.js` |
| `iridescence` | `../../nodes/core/PropertyNode.js` |
| `iridescenceIOR` | `../../nodes/core/PropertyNode.js` |
| `iridescenceThickness` | `../../nodes/core/PropertyNode.js` |
| `specularColor` | `../../nodes/core/PropertyNode.js` |
| `specularF90` | `../../nodes/core/PropertyNode.js` |
| `diffuseColor` | `../../nodes/core/PropertyNode.js` |
| `metalness` | `../../nodes/core/PropertyNode.js` |
| `roughness` | `../../nodes/core/PropertyNode.js` |
| `anisotropy` | `../../nodes/core/PropertyNode.js` |
| `alphaT` | `../../nodes/core/PropertyNode.js` |
| `anisotropyT` | `../../nodes/core/PropertyNode.js` |
| `anisotropyB` | `../../nodes/core/PropertyNode.js` |
| `ior` | `../../nodes/core/PropertyNode.js` |
| `transmission` | `../../nodes/core/PropertyNode.js` |
| `thickness` | `../../nodes/core/PropertyNode.js` |
| `attenuationDistance` | `../../nodes/core/PropertyNode.js` |
| `attenuationColor` | `../../nodes/core/PropertyNode.js` |
| `dispersion` | `../../nodes/core/PropertyNode.js` |
| `materialClearcoat` | `../../nodes/accessors/MaterialNode.js` |
| `materialClearcoatRoughness` | `../../nodes/accessors/MaterialNode.js` |
| `materialClearcoatNormal` | `../../nodes/accessors/MaterialNode.js` |
| `materialSheen` | `../../nodes/accessors/MaterialNode.js` |
| `materialSheenRoughness` | `../../nodes/accessors/MaterialNode.js` |
| `materialIridescence` | `../../nodes/accessors/MaterialNode.js` |
| `materialIridescenceIOR` | `../../nodes/accessors/MaterialNode.js` |
| `materialIridescenceThickness` | `../../nodes/accessors/MaterialNode.js` |
| `materialSpecularIntensity` | `../../nodes/accessors/MaterialNode.js` |
| `materialSpecularColor` | `../../nodes/accessors/MaterialNode.js` |
| `materialAnisotropy` | `../../nodes/accessors/MaterialNode.js` |
| `materialIOR` | `../../nodes/accessors/MaterialNode.js` |
| `materialTransmission` | `../../nodes/accessors/MaterialNode.js` |
| `materialThickness` | `../../nodes/accessors/MaterialNode.js` |
| `materialAttenuationDistance` | `../../nodes/accessors/MaterialNode.js` |
| `materialAttenuationColor` | `../../nodes/accessors/MaterialNode.js` |
| `materialDispersion` | `../../nodes/accessors/MaterialNode.js` |
| `float` | `../../nodes/tsl/TSLBase.js` |
| `vec2` | `../../nodes/tsl/TSLBase.js` |
| `vec3` | `../../nodes/tsl/TSLBase.js` |
| `If` | `../../nodes/tsl/TSLBase.js` |
| `getRoughness` | `../../nodes/functions/material/getRoughness.js` |
| `TBNViewMatrix` | `../../nodes/accessors/AccessorsUtils.js` |
| `PhysicalLightingModel` | `../../nodes/functions/PhysicalLightingModel.js` |
| `MeshStandardNodeMaterial` | `./MeshStandardNodeMaterial.js` |
| `mix` | `../../nodes/math/MathNode.js` |
| `pow2` | `../../nodes/math/MathNode.js` |
| `min` | `../../nodes/math/MathNode.js` |
| `subBuild` | `../../nodes/core/SubBuildNode.js` |
| `MeshPhysicalMaterial` | `../MeshPhysicalMaterial.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_defaultValues` | `MeshPhysicalMaterial` | let/var | `new MeshPhysicalMaterial()` | ✗ |
| `iorNode` | `any` | let/var | `this.iorNode ? float( this.iorNode ) : materialIOR` | ✗ |
| `clearcoatNode` | `any` | let/var | `this.clearcoatNode ? float( this.clearcoatNode ) : materialClearcoat` | ✗ |
| `clearcoatRoughnessNode` | `any` | let/var | `this.clearcoatRoughnessNode ? float( this.clearcoatRoughnessNode ) : material...` | ✗ |
| `sheenNode` | `any` | let/var | `this.sheenNode ? vec3( this.sheenNode ) : materialSheen` | ✗ |
| `sheenRoughnessNode` | `any` | let/var | `this.sheenRoughnessNode ? float( this.sheenRoughnessNode ) : materialSheenRou...` | ✗ |
| `iridescenceNode` | `any` | let/var | `this.iridescenceNode ? float( this.iridescenceNode ) : materialIridescence` | ✗ |
| `iridescenceIORNode` | `any` | let/var | `this.iridescenceIORNode ? float( this.iridescenceIORNode ) : materialIridesce...` | ✗ |
| `iridescenceThicknessNode` | `any` | let/var | `this.iridescenceThicknessNode ? float( this.iridescenceThicknessNode ) : mate...` | ✗ |
| `transmissionNode` | `any` | let/var | `this.transmissionNode ? float( this.transmissionNode ) : materialTransmission` | ✗ |
| `thicknessNode` | `any` | let/var | `this.thicknessNode ? float( this.thicknessNode ) : materialThickness` | ✗ |
| `attenuationDistanceNode` | `any` | let/var | `this.attenuationDistanceNode ? float( this.attenuationDistanceNode ) : materi...` | ✗ |
| `attenuationColorNode` | `any` | let/var | `this.attenuationColorNode ? vec3( this.attenuationColorNode ) : materialAtten...` | ✗ |
| `dispersionNode` | `any` | let/var | `this.dispersionNode ? float( this.dispersionNode ) : materialDispersion` | ✗ |


---

## Functions

### `MeshPhysicalNodeMaterial.setupSpecular(): void`

**JSDoc:**
```typescript
/**
	 * Setups the specular related node variables.
	 */
```

**Returns:** `void`

**Calls:**

- `float (from ../../nodes/tsl/TSLBase.js)`
- `ior.assign`
- `specularColor.assign`
- `mix (from ../../nodes/math/MathNode.js)`
- `min( pow2( ior.sub( 1.0 ).div( ior.add( 1.0 ) ) ).mul( materialSpecularColor ), vec3( 1.0 ) ).mul`
- `specularF90.assign`

<details><summary>Code</summary>

```typescript
setupSpecular() {

		const iorNode = this.iorNode ? float( this.iorNode ) : materialIOR;

		ior.assign( iorNode );
		specularColor.assign( mix( min( pow2( ior.sub( 1.0 ).div( ior.add( 1.0 ) ) ).mul( materialSpecularColor ), vec3( 1.0 ) ).mul( materialSpecularIntensity ), diffuseColor.rgb, metalness ) );
		specularF90.assign( mix( materialSpecularIntensity, 1.0, metalness ) );

	}
```
</details>

### `MeshPhysicalNodeMaterial.setupLightingModel(): PhysicalLightingModel`

**JSDoc:**
```typescript
/**
	 * Setups the lighting model.
	 *
	 * @return {PhysicalLightingModel} The lighting model.
	 */
```

**Returns:** `PhysicalLightingModel`

<details><summary>Code</summary>

```typescript
setupLightingModel( /*builder*/ ) {

		return new PhysicalLightingModel( this.useClearcoat, this.useSheen, this.useIridescence, this.useAnisotropy, this.useTransmission, this.useDispersion );

	}
```
</details>

### `MeshPhysicalNodeMaterial.setupVariants(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Setups the physical specific node variables.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `super.setupVariants`
- `float (from ../../nodes/tsl/TSLBase.js)`
- `clearcoat.assign`
- `clearcoatRoughness.assign`
- `getRoughness (from ../../nodes/functions/material/getRoughness.js)`
- `vec3 (from ../../nodes/tsl/TSLBase.js)`
- `sheen.assign`
- `sheenRoughness.assign`
- `iridescence.assign`
- `iridescenceIOR.assign`
- `iridescenceThickness.assign`
- `( this.anisotropyNode ? vec2( this.anisotropyNode ) : materialAnisotropy ).toVar`
- `vec2 (from ../../nodes/tsl/TSLBase.js)`
- `anisotropy.assign`
- `anisotropyV.length`
- `If( anisotropy.equal( 0.0 ), () => {

				anisotropyV.assign( vec2( 1.0, 0.0 ) );

			} ).Else`
- `anisotropyV.divAssign`
- `anisotropy.saturate`
- `alphaT.assign`
- `anisotropy.pow2().mix`
- `roughness.pow2`
- `anisotropyT.assign`
- `TBNViewMatrix[ 0 ].mul( anisotropyV.x ).add`
- `TBNViewMatrix[ 1 ].mul`
- `anisotropyB.assign`
- `TBNViewMatrix[ 1 ].mul( anisotropyV.x ).sub`
- `TBNViewMatrix[ 0 ].mul`
- `transmission.assign`
- `thickness.assign`
- `attenuationDistance.assign`
- `attenuationColor.assign`
- `dispersion.assign`

**Internal Comments:**
```
// CLEARCOAT
// SHEEN
// IRIDESCENCE
// ANISOTROPY
// Roughness along the anisotropy bitangent is the material roughness, while the tangent roughness increases with anisotropy. (x4)
// TRANSMISSION
```

<details><summary>Code</summary>

```typescript
setupVariants( builder ) {

		super.setupVariants( builder );

		// CLEARCOAT

		if ( this.useClearcoat ) {

			const clearcoatNode = this.clearcoatNode ? float( this.clearcoatNode ) : materialClearcoat;
			const clearcoatRoughnessNode = this.clearcoatRoughnessNode ? float( this.clearcoatRoughnessNode ) : materialClearcoatRoughness;

			clearcoat.assign( clearcoatNode );
			clearcoatRoughness.assign( getRoughness( { roughness: clearcoatRoughnessNode } ) );

		}

		// SHEEN

		if ( this.useSheen ) {

			const sheenNode = this.sheenNode ? vec3( this.sheenNode ) : materialSheen;
			const sheenRoughnessNode = this.sheenRoughnessNode ? float( this.sheenRoughnessNode ) : materialSheenRoughness;

			sheen.assign( sheenNode );
			sheenRoughness.assign( sheenRoughnessNode );

		}

		// IRIDESCENCE

		if ( this.useIridescence ) {

			const iridescenceNode = this.iridescenceNode ? float( this.iridescenceNode ) : materialIridescence;
			const iridescenceIORNode = this.iridescenceIORNode ? float( this.iridescenceIORNode ) : materialIridescenceIOR;
			const iridescenceThicknessNode = this.iridescenceThicknessNode ? float( this.iridescenceThicknessNode ) : materialIridescenceThickness;

			iridescence.assign( iridescenceNode );
			iridescenceIOR.assign( iridescenceIORNode );
			iridescenceThickness.assign( iridescenceThicknessNode );

		}

		// ANISOTROPY

		if ( this.useAnisotropy ) {

			const anisotropyV = ( this.anisotropyNode ? vec2( this.anisotropyNode ) : materialAnisotropy ).toVar();

			anisotropy.assign( anisotropyV.length() );

			If( anisotropy.equal( 0.0 ), () => {

				anisotropyV.assign( vec2( 1.0, 0.0 ) );

			} ).Else( () => {

				anisotropyV.divAssign( vec2( anisotropy ) );
				anisotropy.assign( anisotropy.saturate() );

			} );

			// Roughness along the anisotropy bitangent is the material roughness, while the tangent roughness increases with anisotropy.
			alphaT.assign( anisotropy.pow2().mix( roughness.pow2(), 1.0 ) );

			anisotropyT.assign( TBNViewMatrix[ 0 ].mul( anisotropyV.x ).add( TBNViewMatrix[ 1 ].mul( anisotropyV.y ) ) );
			anisotropyB.assign( TBNViewMatrix[ 1 ].mul( anisotropyV.x ).sub( TBNViewMatrix[ 0 ].mul( anisotropyV.y ) ) );

		}

		// TRANSMISSION

		if ( this.useTransmission ) {

			const transmissionNode = this.transmissionNode ? float( this.transmissionNode ) : materialTransmission;
			const thicknessNode = this.thicknessNode ? float( this.thicknessNode ) : materialThickness;
			const attenuationDistanceNode = this.attenuationDistanceNode ? float( this.attenuationDistanceNode ) : materialAttenuationDistance;
			const attenuationColorNode = this.attenuationColorNode ? vec3( this.attenuationColorNode ) : materialAttenuationColor;

			transmission.assign( transmissionNode );
			thickness.assign( thicknessNode );
			attenuationDistance.assign( attenuationDistanceNode );
			attenuationColor.assign( attenuationColorNode );

			if ( this.useDispersion ) {

				const dispersionNode = this.dispersionNode ? float( this.dispersionNode ) : materialDispersion;

				dispersion.assign( dispersionNode );

			}

		}

	}
```
</details>

### `MeshPhysicalNodeMaterial.setupClearcoatNormal(): any`

**JSDoc:**
```typescript
/**
	 * Setups the clearcoat normal node.
	 *
	 * @return {Node<vec3>} The clearcoat normal.
	 */
```

**Returns:** `any`

**Calls:**

- `vec3 (from ../../nodes/tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
setupClearcoatNormal() {

		return this.clearcoatNormalNode ? vec3( this.clearcoatNormalNode ) : materialClearcoatNormal;

	}
```
</details>

### `MeshPhysicalNodeMaterial.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `subBuild (from ../../nodes/core/SubBuildNode.js)`
- `this.setupClearcoatNormal`
- `super.setup`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		builder.context.setupClearcoatNormal = () => subBuild( this.setupClearcoatNormal( builder ), 'NORMAL', 'vec3' );

		super.setup( builder );

	}
```
</details>

### `MeshPhysicalNodeMaterial.copy(source: any): NodeMaterial`

**Parameters:**

- **`source`** `any`

**Returns:** `NodeMaterial`

**Calls:**

- `super.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		this.clearcoatNode = source.clearcoatNode;
		this.clearcoatRoughnessNode = source.clearcoatRoughnessNode;
		this.clearcoatNormalNode = source.clearcoatNormalNode;

		this.sheenNode = source.sheenNode;
		this.sheenRoughnessNode = source.sheenRoughnessNode;

		this.iridescenceNode = source.iridescenceNode;
		this.iridescenceIORNode = source.iridescenceIORNode;
		this.iridescenceThicknessNode = source.iridescenceThicknessNode;

		this.specularIntensityNode = source.specularIntensityNode;
		this.specularColorNode = source.specularColorNode;

		this.transmissionNode = source.transmissionNode;
		this.thicknessNode = source.thicknessNode;
		this.attenuationDistanceNode = source.attenuationDistanceNode;
		this.attenuationColorNode = source.attenuationColorNode;
		this.dispersionNode = source.dispersionNode;

		this.anisotropyNode = source.anisotropyNode;

		return super.copy( source );

	}
```
</details>


---

## Classes

### `MeshPhysicalNodeMaterial`

<details><summary>Class Code</summary>

```ts
class MeshPhysicalNodeMaterial extends MeshStandardNodeMaterial {

	static get type() {

		return 'MeshPhysicalNodeMaterial';

	}

	/**
	 * Constructs a new mesh physical node material.
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
		this.isMeshPhysicalNodeMaterial = true;

		/**
		 * The clearcoat of physical materials is by default inferred from the `clearcoat`
		 * and `clearcoatMap` properties. This node property allows to overwrite the default
		 * and define the clearcoat with a node instead.
		 *
		 * If you don't want to overwrite the clearcoat but modify the existing
		 * value instead, use {@link materialClearcoat}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.clearcoatNode = null;

		/**
		 * The clearcoat roughness of physical materials is by default inferred from the `clearcoatRoughness`
		 * and `clearcoatRoughnessMap` properties. This node property allows to overwrite the default
		 * and define the clearcoat roughness with a node instead.
		 *
		 * If you don't want to overwrite the clearcoat roughness but modify the existing
		 * value instead, use {@link materialClearcoatRoughness}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.clearcoatRoughnessNode = null;

		/**
		 * The clearcoat normal of physical materials is by default inferred from the `clearcoatNormalMap`
		 * property. This node property allows to overwrite the default
		 * and define the clearcoat normal with a node instead.
		 *
		 * If you don't want to overwrite the clearcoat normal but modify the existing
		 * value instead, use {@link materialClearcoatNormal}.
		 *
		 * @type {?Node<vec3>}
		 * @default null
		 */
		this.clearcoatNormalNode = null;

		/**
		 * The sheen of physical materials is by default inferred from the `sheen`, `sheenColor`
		 * and `sheenColorMap` properties. This node property allows to overwrite the default
		 * and define the sheen with a node instead.
		 *
		 * If you don't want to overwrite the sheen but modify the existing
		 * value instead, use {@link materialSheen}.
		 *
		 * @type {?Node<vec3>}
		 * @default null
		 */
		this.sheenNode = null;

		/**
		 * The sheen roughness of physical materials is by default inferred from the `sheenRoughness` and
		 * `sheenRoughnessMap` properties. This node property allows to overwrite the default
		 * and define the sheen roughness with a node instead.
		 *
		 * If you don't want to overwrite the sheen roughness but modify the existing
		 * value instead, use {@link materialSheenRoughness}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.sheenRoughnessNode = null;

		/**
		 * The iridescence of physical materials is by default inferred from the `iridescence`
		 * property. This node property allows to overwrite the default
		 * and define the iridescence with a node instead.
		 *
		 * If you don't want to overwrite the iridescence but modify the existing
		 * value instead, use {@link materialIridescence}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.iridescenceNode = null;

		/**
		 * The iridescence IOR of physical materials is by default inferred from the `iridescenceIOR`
		 * property. This node property allows to overwrite the default
		 * and define the iridescence IOR with a node instead.
		 *
		 * If you don't want to overwrite the iridescence IOR but modify the existing
		 * value instead, use {@link materialIridescenceIOR}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.iridescenceIORNode = null;

		/**
		 * The iridescence thickness of physical materials is by default inferred from the `iridescenceThicknessRange`
		 * and `iridescenceThicknessMap` properties. This node property allows to overwrite the default
		 * and define the iridescence thickness with a node instead.
		 *
		 * If you don't want to overwrite the iridescence thickness but modify the existing
		 * value instead, use {@link materialIridescenceThickness}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.iridescenceThicknessNode = null;

		/**
		 * The specular intensity of physical materials is by default inferred from the `specularIntensity`
		 * and `specularIntensityMap` properties. This node property allows to overwrite the default
		 * and define the specular intensity with a node instead.
		 *
		 * If you don't want to overwrite the specular intensity but modify the existing
		 * value instead, use {@link materialSpecularIntensity}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.specularIntensityNode = null;

		/**
		 * The specular color of physical materials is by default inferred from the `specularColor`
		 * and `specularColorMap` properties. This node property allows to overwrite the default
		 * and define the specular color with a node instead.
		 *
		 * If you don't want to overwrite the specular color but modify the existing
		 * value instead, use {@link materialSpecularColor}.
		 *
		 * @type {?Node<vec3>}
		 * @default null
		 */
		this.specularColorNode = null;

		/**
		 * The ior of physical materials is by default inferred from the `ior`
		 * property. This node property allows to overwrite the default
		 * and define the ior with a node instead.
		 *
		 * If you don't want to overwrite the ior but modify the existing
		 * value instead, use {@link materialIOR}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.iorNode = null;

		/**
		 * The transmission of physical materials is by default inferred from the `transmission` and
		 * `transmissionMap` properties. This node property allows to overwrite the default
		 * and define the transmission with a node instead.
		 *
		 * If you don't want to overwrite the transmission but modify the existing
		 * value instead, use {@link materialTransmission}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.transmissionNode = null;

		/**
		 * The thickness of physical materials is by default inferred from the `thickness` and
		 * `thicknessMap` properties. This node property allows to overwrite the default
		 * and define the thickness with a node instead.
		 *
		 * If you don't want to overwrite the thickness but modify the existing
		 * value instead, use {@link materialThickness}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.thicknessNode = null;

		/**
		 * The attenuation distance of physical materials is by default inferred from the
		 * `attenuationDistance` property. This node property allows to overwrite the default
		 * and define the attenuation distance with a node instead.
		 *
		 * If you don't want to overwrite the attenuation distance but modify the existing
		 * value instead, use {@link materialAttenuationDistance}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.attenuationDistanceNode = null;

		/**
		 * The attenuation color of physical materials is by default inferred from the
		 * `attenuationColor` property. This node property allows to overwrite the default
		 * and define the attenuation color with a node instead.
		 *
		 * If you don't want to overwrite the attenuation color but modify the existing
		 * value instead, use {@link materialAttenuationColor}.
		 *
		 * @type {?Node<vec3>}
		 * @default null
		 */
		this.attenuationColorNode = null;

		/**
		 * The dispersion of physical materials is by default inferred from the
		 * `dispersion` property. This node property allows to overwrite the default
		 * and define the dispersion with a node instead.
		 *
		 * If you don't want to overwrite the dispersion but modify the existing
		 * value instead, use {@link materialDispersion}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.dispersionNode = null;

		/**
		 * The anisotropy of physical materials is by default inferred from the
		 * `anisotropy` property. This node property allows to overwrite the default
		 * and define the anisotropy with a node instead.
		 *
		 * If you don't want to overwrite the anisotropy but modify the existing
		 * value instead, use {@link materialAnisotropy}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.anisotropyNode = null;

		this.setDefaultValues( _defaultValues );

		this.setValues( parameters );

	}

	/**
	 * Whether the lighting model should use clearcoat or not.
	 *
	 * @type {boolean}
	 * @default true
	 */
	get useClearcoat() {

		return this.clearcoat > 0 || this.clearcoatNode !== null;

	}

	/**
	 * Whether the lighting model should use iridescence or not.
	 *
	 * @type {boolean}
	 * @default true
	 */
	get useIridescence() {

		return this.iridescence > 0 || this.iridescenceNode !== null;

	}

	/**
	 * Whether the lighting model should use sheen or not.
	 *
	 * @type {boolean}
	 * @default true
	 */
	get useSheen() {

		return this.sheen > 0 || this.sheenNode !== null;

	}

	/**
	 * Whether the lighting model should use anisotropy or not.
	 *
	 * @type {boolean}
	 * @default true
	 */
	get useAnisotropy() {

		return this.anisotropy > 0 || this.anisotropyNode !== null;

	}

	/**
	 * Whether the lighting model should use transmission or not.
	 *
	 * @type {boolean}
	 * @default true
	 */
	get useTransmission() {

		return this.transmission > 0 || this.transmissionNode !== null;

	}

	/**
	 * Whether the lighting model should use dispersion or not.
	 *
	 * @type {boolean}
	 * @default true
	 */
	get useDispersion() {

		return this.dispersion > 0 || this.dispersionNode !== null;

	}

	/**
	 * Setups the specular related node variables.
	 */
	setupSpecular() {

		const iorNode = this.iorNode ? float( this.iorNode ) : materialIOR;

		ior.assign( iorNode );
		specularColor.assign( mix( min( pow2( ior.sub( 1.0 ).div( ior.add( 1.0 ) ) ).mul( materialSpecularColor ), vec3( 1.0 ) ).mul( materialSpecularIntensity ), diffuseColor.rgb, metalness ) );
		specularF90.assign( mix( materialSpecularIntensity, 1.0, metalness ) );

	}

	/**
	 * Setups the lighting model.
	 *
	 * @return {PhysicalLightingModel} The lighting model.
	 */
	setupLightingModel( /*builder*/ ) {

		return new PhysicalLightingModel( this.useClearcoat, this.useSheen, this.useIridescence, this.useAnisotropy, this.useTransmission, this.useDispersion );

	}

	/**
	 * Setups the physical specific node variables.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	setupVariants( builder ) {

		super.setupVariants( builder );

		// CLEARCOAT

		if ( this.useClearcoat ) {

			const clearcoatNode = this.clearcoatNode ? float( this.clearcoatNode ) : materialClearcoat;
			const clearcoatRoughnessNode = this.clearcoatRoughnessNode ? float( this.clearcoatRoughnessNode ) : materialClearcoatRoughness;

			clearcoat.assign( clearcoatNode );
			clearcoatRoughness.assign( getRoughness( { roughness: clearcoatRoughnessNode } ) );

		}

		// SHEEN

		if ( this.useSheen ) {

			const sheenNode = this.sheenNode ? vec3( this.sheenNode ) : materialSheen;
			const sheenRoughnessNode = this.sheenRoughnessNode ? float( this.sheenRoughnessNode ) : materialSheenRoughness;

			sheen.assign( sheenNode );
			sheenRoughness.assign( sheenRoughnessNode );

		}

		// IRIDESCENCE

		if ( this.useIridescence ) {

			const iridescenceNode = this.iridescenceNode ? float( this.iridescenceNode ) : materialIridescence;
			const iridescenceIORNode = this.iridescenceIORNode ? float( this.iridescenceIORNode ) : materialIridescenceIOR;
			const iridescenceThicknessNode = this.iridescenceThicknessNode ? float( this.iridescenceThicknessNode ) : materialIridescenceThickness;

			iridescence.assign( iridescenceNode );
			iridescenceIOR.assign( iridescenceIORNode );
			iridescenceThickness.assign( iridescenceThicknessNode );

		}

		// ANISOTROPY

		if ( this.useAnisotropy ) {

			const anisotropyV = ( this.anisotropyNode ? vec2( this.anisotropyNode ) : materialAnisotropy ).toVar();

			anisotropy.assign( anisotropyV.length() );

			If( anisotropy.equal( 0.0 ), () => {

				anisotropyV.assign( vec2( 1.0, 0.0 ) );

			} ).Else( () => {

				anisotropyV.divAssign( vec2( anisotropy ) );
				anisotropy.assign( anisotropy.saturate() );

			} );

			// Roughness along the anisotropy bitangent is the material roughness, while the tangent roughness increases with anisotropy.
			alphaT.assign( anisotropy.pow2().mix( roughness.pow2(), 1.0 ) );

			anisotropyT.assign( TBNViewMatrix[ 0 ].mul( anisotropyV.x ).add( TBNViewMatrix[ 1 ].mul( anisotropyV.y ) ) );
			anisotropyB.assign( TBNViewMatrix[ 1 ].mul( anisotropyV.x ).sub( TBNViewMatrix[ 0 ].mul( anisotropyV.y ) ) );

		}

		// TRANSMISSION

		if ( this.useTransmission ) {

			const transmissionNode = this.transmissionNode ? float( this.transmissionNode ) : materialTransmission;
			const thicknessNode = this.thicknessNode ? float( this.thicknessNode ) : materialThickness;
			const attenuationDistanceNode = this.attenuationDistanceNode ? float( this.attenuationDistanceNode ) : materialAttenuationDistance;
			const attenuationColorNode = this.attenuationColorNode ? vec3( this.attenuationColorNode ) : materialAttenuationColor;

			transmission.assign( transmissionNode );
			thickness.assign( thicknessNode );
			attenuationDistance.assign( attenuationDistanceNode );
			attenuationColor.assign( attenuationColorNode );

			if ( this.useDispersion ) {

				const dispersionNode = this.dispersionNode ? float( this.dispersionNode ) : materialDispersion;

				dispersion.assign( dispersionNode );

			}

		}

	}

	/**
	 * Setups the clearcoat normal node.
	 *
	 * @return {Node<vec3>} The clearcoat normal.
	 */
	setupClearcoatNormal() {

		return this.clearcoatNormalNode ? vec3( this.clearcoatNormalNode ) : materialClearcoatNormal;

	}

	setup( builder ) {

		builder.context.setupClearcoatNormal = () => subBuild( this.setupClearcoatNormal( builder ), 'NORMAL', 'vec3' );

		super.setup( builder );

	}

	copy( source ) {

		this.clearcoatNode = source.clearcoatNode;
		this.clearcoatRoughnessNode = source.clearcoatRoughnessNode;
		this.clearcoatNormalNode = source.clearcoatNormalNode;

		this.sheenNode = source.sheenNode;
		this.sheenRoughnessNode = source.sheenRoughnessNode;

		this.iridescenceNode = source.iridescenceNode;
		this.iridescenceIORNode = source.iridescenceIORNode;
		this.iridescenceThicknessNode = source.iridescenceThicknessNode;

		this.specularIntensityNode = source.specularIntensityNode;
		this.specularColorNode = source.specularColorNode;

		this.transmissionNode = source.transmissionNode;
		this.thicknessNode = source.thicknessNode;
		this.attenuationDistanceNode = source.attenuationDistanceNode;
		this.attenuationColorNode = source.attenuationColorNode;
		this.dispersionNode = source.dispersionNode;

		this.anisotropyNode = source.anisotropyNode;

		return super.copy( source );

	}

}
```
</details>

#### Methods

##### `setupSpecular(): void`

<details><summary>Code</summary>

```ts
setupSpecular() {

		const iorNode = this.iorNode ? float( this.iorNode ) : materialIOR;

		ior.assign( iorNode );
		specularColor.assign( mix( min( pow2( ior.sub( 1.0 ).div( ior.add( 1.0 ) ) ).mul( materialSpecularColor ), vec3( 1.0 ) ).mul( materialSpecularIntensity ), diffuseColor.rgb, metalness ) );
		specularF90.assign( mix( materialSpecularIntensity, 1.0, metalness ) );

	}
```
</details>

##### `setupLightingModel(): PhysicalLightingModel`

<details><summary>Code</summary>

```ts
setupLightingModel( /*builder*/ ) {

		return new PhysicalLightingModel( this.useClearcoat, this.useSheen, this.useIridescence, this.useAnisotropy, this.useTransmission, this.useDispersion );

	}
```
</details>

##### `setupVariants(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
setupVariants( builder ) {

		super.setupVariants( builder );

		// CLEARCOAT

		if ( this.useClearcoat ) {

			const clearcoatNode = this.clearcoatNode ? float( this.clearcoatNode ) : materialClearcoat;
			const clearcoatRoughnessNode = this.clearcoatRoughnessNode ? float( this.clearcoatRoughnessNode ) : materialClearcoatRoughness;

			clearcoat.assign( clearcoatNode );
			clearcoatRoughness.assign( getRoughness( { roughness: clearcoatRoughnessNode } ) );

		}

		// SHEEN

		if ( this.useSheen ) {

			const sheenNode = this.sheenNode ? vec3( this.sheenNode ) : materialSheen;
			const sheenRoughnessNode = this.sheenRoughnessNode ? float( this.sheenRoughnessNode ) : materialSheenRoughness;

			sheen.assign( sheenNode );
			sheenRoughness.assign( sheenRoughnessNode );

		}

		// IRIDESCENCE

		if ( this.useIridescence ) {

			const iridescenceNode = this.iridescenceNode ? float( this.iridescenceNode ) : materialIridescence;
			const iridescenceIORNode = this.iridescenceIORNode ? float( this.iridescenceIORNode ) : materialIridescenceIOR;
			const iridescenceThicknessNode = this.iridescenceThicknessNode ? float( this.iridescenceThicknessNode ) : materialIridescenceThickness;

			iridescence.assign( iridescenceNode );
			iridescenceIOR.assign( iridescenceIORNode );
			iridescenceThickness.assign( iridescenceThicknessNode );

		}

		// ANISOTROPY

		if ( this.useAnisotropy ) {

			const anisotropyV = ( this.anisotropyNode ? vec2( this.anisotropyNode ) : materialAnisotropy ).toVar();

			anisotropy.assign( anisotropyV.length() );

			If( anisotropy.equal( 0.0 ), () => {

				anisotropyV.assign( vec2( 1.0, 0.0 ) );

			} ).Else( () => {

				anisotropyV.divAssign( vec2( anisotropy ) );
				anisotropy.assign( anisotropy.saturate() );

			} );

			// Roughness along the anisotropy bitangent is the material roughness, while the tangent roughness increases with anisotropy.
			alphaT.assign( anisotropy.pow2().mix( roughness.pow2(), 1.0 ) );

			anisotropyT.assign( TBNViewMatrix[ 0 ].mul( anisotropyV.x ).add( TBNViewMatrix[ 1 ].mul( anisotropyV.y ) ) );
			anisotropyB.assign( TBNViewMatrix[ 1 ].mul( anisotropyV.x ).sub( TBNViewMatrix[ 0 ].mul( anisotropyV.y ) ) );

		}

		// TRANSMISSION

		if ( this.useTransmission ) {

			const transmissionNode = this.transmissionNode ? float( this.transmissionNode ) : materialTransmission;
			const thicknessNode = this.thicknessNode ? float( this.thicknessNode ) : materialThickness;
			const attenuationDistanceNode = this.attenuationDistanceNode ? float( this.attenuationDistanceNode ) : materialAttenuationDistance;
			const attenuationColorNode = this.attenuationColorNode ? vec3( this.attenuationColorNode ) : materialAttenuationColor;

			transmission.assign( transmissionNode );
			thickness.assign( thicknessNode );
			attenuationDistance.assign( attenuationDistanceNode );
			attenuationColor.assign( attenuationColorNode );

			if ( this.useDispersion ) {

				const dispersionNode = this.dispersionNode ? float( this.dispersionNode ) : materialDispersion;

				dispersion.assign( dispersionNode );

			}

		}

	}
```
</details>

##### `setupClearcoatNormal(): any`

<details><summary>Code</summary>

```ts
setupClearcoatNormal() {

		return this.clearcoatNormalNode ? vec3( this.clearcoatNormalNode ) : materialClearcoatNormal;

	}
```
</details>

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		builder.context.setupClearcoatNormal = () => subBuild( this.setupClearcoatNormal( builder ), 'NORMAL', 'vec3' );

		super.setup( builder );

	}
```
</details>

##### `copy(source: any): NodeMaterial`

<details><summary>Code</summary>

```ts
copy( source ) {

		this.clearcoatNode = source.clearcoatNode;
		this.clearcoatRoughnessNode = source.clearcoatRoughnessNode;
		this.clearcoatNormalNode = source.clearcoatNormalNode;

		this.sheenNode = source.sheenNode;
		this.sheenRoughnessNode = source.sheenRoughnessNode;

		this.iridescenceNode = source.iridescenceNode;
		this.iridescenceIORNode = source.iridescenceIORNode;
		this.iridescenceThicknessNode = source.iridescenceThicknessNode;

		this.specularIntensityNode = source.specularIntensityNode;
		this.specularColorNode = source.specularColorNode;

		this.transmissionNode = source.transmissionNode;
		this.thicknessNode = source.thicknessNode;
		this.attenuationDistanceNode = source.attenuationDistanceNode;
		this.attenuationColorNode = source.attenuationColorNode;
		this.dispersionNode = source.dispersionNode;

		this.anisotropyNode = source.anisotropyNode;

		return super.copy( source );

	}
```
</details>


---