[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MeshStandardNodeMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 16 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/nodes/MeshStandardNodeMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeMaterial` | `./NodeMaterial.js` |
| `diffuseColor` | `../../nodes/core/PropertyNode.js` |
| `metalness` | `../../nodes/core/PropertyNode.js` |
| `roughness` | `../../nodes/core/PropertyNode.js` |
| `specularColor` | `../../nodes/core/PropertyNode.js` |
| `specularF90` | `../../nodes/core/PropertyNode.js` |
| `mix` | `../../nodes/math/MathNode.js` |
| `materialRoughness` | `../../nodes/accessors/MaterialNode.js` |
| `materialMetalness` | `../../nodes/accessors/MaterialNode.js` |
| `getRoughness` | `../../nodes/functions/material/getRoughness.js` |
| `PhysicalLightingModel` | `../../nodes/functions/PhysicalLightingModel.js` |
| `EnvironmentNode` | `../../nodes/lighting/EnvironmentNode.js` |
| `float` | `../../nodes/tsl/TSLBase.js` |
| `vec3` | `../../nodes/tsl/TSLBase.js` |
| `vec4` | `../../nodes/tsl/TSLBase.js` |
| `MeshStandardMaterial` | `../MeshStandardMaterial.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_defaultValues` | `MeshStandardMaterial` | let/var | `new MeshStandardMaterial()` | ✗ |
| `metalnessNode` | `any` | let/var | `this.metalnessNode ? float( this.metalnessNode ) : materialMetalness` | ✗ |
| `roughnessNode` | `any` | let/var | `this.roughnessNode ? float( this.roughnessNode ) : materialRoughness` | ✗ |


---

## Functions

### `MeshStandardNodeMaterial.setupEnvironment(builder: NodeBuilder): any`

**JSDoc:**
```typescript
/**
	 * Overwritten since this type of material uses {@link EnvironmentNode}
	 * to implement the PBR (PMREM based) environment mapping. Besides, the
	 * method honors `Scene.environment`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {?EnvironmentNode<vec3>} The environment node.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `any`

**Calls:**

- `super.setupEnvironment`

<details><summary>Code</summary>

```typescript
setupEnvironment( builder ) {

		let envNode = super.setupEnvironment( builder );

		if ( envNode === null && builder.environmentNode ) {

			envNode = builder.environmentNode;

		}

		return envNode ? new EnvironmentNode( envNode ) : null;

	}
```
</details>

### `MeshStandardNodeMaterial.setupLightingModel(): PhysicalLightingModel`

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

		return new PhysicalLightingModel();

	}
```
</details>

### `MeshStandardNodeMaterial.setupSpecular(): void`

**JSDoc:**
```typescript
/**
	 * Setups the specular related node variables.
	 */
```

**Returns:** `void`

**Calls:**

- `mix (from ../../nodes/math/MathNode.js)`
- `vec3 (from ../../nodes/tsl/TSLBase.js)`
- `specularColor.assign`
- `specularF90.assign`

<details><summary>Code</summary>

```typescript
setupSpecular() {

		const specularColorNode = mix( vec3( 0.04 ), diffuseColor.rgb, metalness );

		specularColor.assign( specularColorNode );
		specularF90.assign( 1.0 );

	}
```
</details>

### `MeshStandardNodeMaterial.setupVariants(): void`

**JSDoc:**
```typescript
/**
	 * Setups the standard specific node variables.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Returns:** `void`

**Calls:**

- `float (from ../../nodes/tsl/TSLBase.js)`
- `metalness.assign`
- `getRoughness (from ../../nodes/functions/material/getRoughness.js)`
- `roughness.assign`
- `this.setupSpecular`
- `diffuseColor.assign`
- `vec4 (from ../../nodes/tsl/TSLBase.js)`
- `diffuseColor.rgb.mul`
- `metalnessNode.oneMinus`

**Internal Comments:**
```
// METALNESS (x2)
// ROUGHNESS (x2)
// SPECULAR COLOR (x4)
// DIFFUSE COLOR (x4)
```

<details><summary>Code</summary>

```typescript
setupVariants() {

		// METALNESS

		const metalnessNode = this.metalnessNode ? float( this.metalnessNode ) : materialMetalness;

		metalness.assign( metalnessNode );

		// ROUGHNESS

		let roughnessNode = this.roughnessNode ? float( this.roughnessNode ) : materialRoughness;
		roughnessNode = getRoughness( { roughness: roughnessNode } );

		roughness.assign( roughnessNode );

		// SPECULAR COLOR

		this.setupSpecular();

		// DIFFUSE COLOR

		diffuseColor.assign( vec4( diffuseColor.rgb.mul( metalnessNode.oneMinus() ), diffuseColor.a ) );

	}
```
</details>

### `MeshStandardNodeMaterial.copy(source: any): NodeMaterial`

**Parameters:**

- **`source`** `any`

**Returns:** `NodeMaterial`

**Calls:**

- `super.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		this.emissiveNode = source.emissiveNode;

		this.metalnessNode = source.metalnessNode;
		this.roughnessNode = source.roughnessNode;

		return super.copy( source );

	}
```
</details>


---

## Classes

### `MeshStandardNodeMaterial`

<details><summary>Class Code</summary>

```ts
class MeshStandardNodeMaterial extends NodeMaterial {

	static get type() {

		return 'MeshStandardNodeMaterial';

	}

	/**
	 * Constructs a new mesh standard node material.
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
		this.isMeshStandardNodeMaterial = true;

		/**
		 * Set to `true` because standard materials react on lights.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.lights = true;

		/**
		 * The emissive color of standard materials is by default inferred from the `emissive`,
		 * `emissiveIntensity` and `emissiveMap` properties. This node property allows to
		 * overwrite the default and define the emissive color with a node instead.
		 *
		 * If you don't want to overwrite the emissive color but modify the existing
		 * value instead, use {@link materialEmissive}.
		 *
		 * @type {?Node<vec3>}
		 * @default null
		 */
		this.emissiveNode = null;

		/**
		 * The metalness of standard materials is by default inferred from the `metalness`,
		 * and `metalnessMap` properties. This node property allows to
		 * overwrite the default and define the metalness with a node instead.
		 *
		 * If you don't want to overwrite the metalness but modify the existing
		 * value instead, use {@link materialMetalness}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.metalnessNode = null;

		/**
		 * The roughness of standard materials is by default inferred from the `roughness`,
		 * and `roughnessMap` properties. This node property allows to
		 * overwrite the default and define the roughness with a node instead.
		 *
		 * If you don't want to overwrite the roughness but modify the existing
		 * value instead, use {@link materialRoughness}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.roughnessNode = null;

		this.setDefaultValues( _defaultValues );

		this.setValues( parameters );

	}

	/**
	 * Overwritten since this type of material uses {@link EnvironmentNode}
	 * to implement the PBR (PMREM based) environment mapping. Besides, the
	 * method honors `Scene.environment`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {?EnvironmentNode<vec3>} The environment node.
	 */
	setupEnvironment( builder ) {

		let envNode = super.setupEnvironment( builder );

		if ( envNode === null && builder.environmentNode ) {

			envNode = builder.environmentNode;

		}

		return envNode ? new EnvironmentNode( envNode ) : null;

	}

	/**
	 * Setups the lighting model.
	 *
	 * @return {PhysicalLightingModel} The lighting model.
	 */
	setupLightingModel( /*builder*/ ) {

		return new PhysicalLightingModel();

	}

	/**
	 * Setups the specular related node variables.
	 */
	setupSpecular() {

		const specularColorNode = mix( vec3( 0.04 ), diffuseColor.rgb, metalness );

		specularColor.assign( specularColorNode );
		specularF90.assign( 1.0 );

	}

	/**
	 * Setups the standard specific node variables.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	setupVariants() {

		// METALNESS

		const metalnessNode = this.metalnessNode ? float( this.metalnessNode ) : materialMetalness;

		metalness.assign( metalnessNode );

		// ROUGHNESS

		let roughnessNode = this.roughnessNode ? float( this.roughnessNode ) : materialRoughness;
		roughnessNode = getRoughness( { roughness: roughnessNode } );

		roughness.assign( roughnessNode );

		// SPECULAR COLOR

		this.setupSpecular();

		// DIFFUSE COLOR

		diffuseColor.assign( vec4( diffuseColor.rgb.mul( metalnessNode.oneMinus() ), diffuseColor.a ) );

	}

	copy( source ) {

		this.emissiveNode = source.emissiveNode;

		this.metalnessNode = source.metalnessNode;
		this.roughnessNode = source.roughnessNode;

		return super.copy( source );

	}

}
```
</details>

#### Methods

##### `setupEnvironment(builder: NodeBuilder): any`

<details><summary>Code</summary>

```ts
setupEnvironment( builder ) {

		let envNode = super.setupEnvironment( builder );

		if ( envNode === null && builder.environmentNode ) {

			envNode = builder.environmentNode;

		}

		return envNode ? new EnvironmentNode( envNode ) : null;

	}
```
</details>

##### `setupLightingModel(): PhysicalLightingModel`

<details><summary>Code</summary>

```ts
setupLightingModel( /*builder*/ ) {

		return new PhysicalLightingModel();

	}
```
</details>

##### `setupSpecular(): void`

<details><summary>Code</summary>

```ts
setupSpecular() {

		const specularColorNode = mix( vec3( 0.04 ), diffuseColor.rgb, metalness );

		specularColor.assign( specularColorNode );
		specularF90.assign( 1.0 );

	}
```
</details>

##### `setupVariants(): void`

<details><summary>Code</summary>

```ts
setupVariants() {

		// METALNESS

		const metalnessNode = this.metalnessNode ? float( this.metalnessNode ) : materialMetalness;

		metalness.assign( metalnessNode );

		// ROUGHNESS

		let roughnessNode = this.roughnessNode ? float( this.roughnessNode ) : materialRoughness;
		roughnessNode = getRoughness( { roughness: roughnessNode } );

		roughness.assign( roughnessNode );

		// SPECULAR COLOR

		this.setupSpecular();

		// DIFFUSE COLOR

		diffuseColor.assign( vec4( diffuseColor.rgb.mul( metalnessNode.oneMinus() ), diffuseColor.a ) );

	}
```
</details>

##### `copy(source: any): NodeMaterial`

<details><summary>Code</summary>

```ts
copy( source ) {

		this.emissiveNode = source.emissiveNode;

		this.metalnessNode = source.metalnessNode;
		this.roughnessNode = source.roughnessNode;

		return super.copy( source );

	}
```
</details>


---