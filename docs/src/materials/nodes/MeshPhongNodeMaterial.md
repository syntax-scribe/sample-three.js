[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MeshPhongNodeMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/nodes/MeshPhongNodeMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeMaterial` | `./NodeMaterial.js` |
| `shininess` | `../../nodes/core/PropertyNode.js` |
| `specularColor` | `../../nodes/core/PropertyNode.js` |
| `materialShininess` | `../../nodes/accessors/MaterialNode.js` |
| `materialSpecular` | `../../nodes/accessors/MaterialNode.js` |
| `float` | `../../nodes/tsl/TSLBase.js` |
| `BasicEnvironmentNode` | `../../nodes/lighting/BasicEnvironmentNode.js` |
| `PhongLightingModel` | `../../nodes/functions/PhongLightingModel.js` |
| `MeshPhongMaterial` | `../MeshPhongMaterial.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_defaultValues` | `MeshPhongMaterial` | let/var | `new MeshPhongMaterial()` | ✗ |
| `specularNode` | `any` | let/var | `this.specularNode \|\| materialSpecular` | ✗ |


---

## Functions

### `MeshPhongNodeMaterial.setupEnvironment(builder: NodeBuilder): any`

**JSDoc:**
```typescript
/**
	 * Overwritten since this type of material uses {@link BasicEnvironmentNode}
	 * to implement the default environment mapping.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {?BasicEnvironmentNode<vec3>} The environment node.
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

		const envNode = super.setupEnvironment( builder );

		return envNode ? new BasicEnvironmentNode( envNode ) : null;

	}
```
</details>

### `MeshPhongNodeMaterial.setupLightingModel(): PhongLightingModel`

**JSDoc:**
```typescript
/**
	 * Setups the lighting model.
	 *
	 * @return {PhongLightingModel} The lighting model.
	 */
```

**Returns:** `PhongLightingModel`

<details><summary>Code</summary>

```typescript
setupLightingModel( /*builder*/ ) {

		return new PhongLightingModel();

	}
```
</details>

### `MeshPhongNodeMaterial.setupVariants(): void`

**JSDoc:**
```typescript
/**
	 * Setups the phong specific node variables.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Returns:** `void`

**Calls:**

- `( this.shininessNode ? float( this.shininessNode ) : materialShininess ).max`
- `float (from ../../nodes/tsl/TSLBase.js)`
- `shininess.assign`
- `specularColor.assign`

**Internal Comments:**
```
// SHININESS (x2)
// SPECULAR COLOR (x2)
```

<details><summary>Code</summary>

```typescript
setupVariants( /*builder*/ ) {

		// SHININESS

		const shininessNode = ( this.shininessNode ? float( this.shininessNode ) : materialShininess ).max( 1e-4 ); // to prevent pow( 0.0, 0.0 )

		shininess.assign( shininessNode );

		// SPECULAR COLOR

		const specularNode = this.specularNode || materialSpecular;

		specularColor.assign( specularNode );

	}
```
</details>

### `MeshPhongNodeMaterial.copy(source: any): NodeMaterial`

**Parameters:**

- **`source`** `any`

**Returns:** `NodeMaterial`

**Calls:**

- `super.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		this.shininessNode = source.shininessNode;
		this.specularNode = source.specularNode;

		return super.copy( source );

	}
```
</details>


---

## Classes

### `MeshPhongNodeMaterial`

<details><summary>Class Code</summary>

```ts
class MeshPhongNodeMaterial extends NodeMaterial {

	static get type() {

		return 'MeshPhongNodeMaterial';

	}

	/**
	 * Constructs a new mesh lambert node material.
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
		this.isMeshPhongNodeMaterial = true;

		/**
		 * Set to `true` because phong materials react on lights.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.lights = true;

		/**
		 * The shininess of phong materials is by default inferred from the `shininess`
		 * property. This node property allows to overwrite the default
		 * and define the shininess with a node instead.
		 *
		 * If you don't want to overwrite the shininess but modify the existing
		 * value instead, use {@link materialShininess}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.shininessNode = null;

		/**
		 * The specular color of phong materials is by default inferred from the
		 * `specular` property. This node property allows to overwrite the default
		 * and define the specular color with a node instead.
		 *
		 * If you don't want to overwrite the specular color but modify the existing
		 * value instead, use {@link materialSpecular}.
		 *
		 * @type {?Node<vec3>}
		 * @default null
		 */
		this.specularNode = null;

		this.setDefaultValues( _defaultValues );

		this.setValues( parameters );

	}

	/**
	 * Overwritten since this type of material uses {@link BasicEnvironmentNode}
	 * to implement the default environment mapping.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {?BasicEnvironmentNode<vec3>} The environment node.
	 */
	setupEnvironment( builder ) {

		const envNode = super.setupEnvironment( builder );

		return envNode ? new BasicEnvironmentNode( envNode ) : null;

	}

	/**
	 * Setups the lighting model.
	 *
	 * @return {PhongLightingModel} The lighting model.
	 */
	setupLightingModel( /*builder*/ ) {

		return new PhongLightingModel();

	}

	/**
	 * Setups the phong specific node variables.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	setupVariants( /*builder*/ ) {

		// SHININESS

		const shininessNode = ( this.shininessNode ? float( this.shininessNode ) : materialShininess ).max( 1e-4 ); // to prevent pow( 0.0, 0.0 )

		shininess.assign( shininessNode );

		// SPECULAR COLOR

		const specularNode = this.specularNode || materialSpecular;

		specularColor.assign( specularNode );

	}

	copy( source ) {

		this.shininessNode = source.shininessNode;
		this.specularNode = source.specularNode;

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

		const envNode = super.setupEnvironment( builder );

		return envNode ? new BasicEnvironmentNode( envNode ) : null;

	}
```
</details>

##### `setupLightingModel(): PhongLightingModel`

<details><summary>Code</summary>

```ts
setupLightingModel( /*builder*/ ) {

		return new PhongLightingModel();

	}
```
</details>

##### `setupVariants(): void`

<details><summary>Code</summary>

```ts
setupVariants( /*builder*/ ) {

		// SHININESS

		const shininessNode = ( this.shininessNode ? float( this.shininessNode ) : materialShininess ).max( 1e-4 ); // to prevent pow( 0.0, 0.0 )

		shininess.assign( shininessNode );

		// SPECULAR COLOR

		const specularNode = this.specularNode || materialSpecular;

		specularColor.assign( specularNode );

	}
```
</details>

##### `copy(source: any): NodeMaterial`

<details><summary>Code</summary>

```ts
copy( source ) {

		this.shininessNode = source.shininessNode;
		this.specularNode = source.specularNode;

		return super.copy( source );

	}
```
</details>


---