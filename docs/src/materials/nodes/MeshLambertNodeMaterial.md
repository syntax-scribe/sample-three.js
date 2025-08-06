[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MeshLambertNodeMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/nodes/MeshLambertNodeMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeMaterial` | `./NodeMaterial.js` |
| `BasicEnvironmentNode` | `../../nodes/lighting/BasicEnvironmentNode.js` |
| `PhongLightingModel` | `../../nodes/functions/PhongLightingModel.js` |
| `MeshLambertMaterial` | `../MeshLambertMaterial.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_defaultValues` | `MeshLambertMaterial` | let/var | `new MeshLambertMaterial()` | ✗ |


---

## Functions

### `MeshLambertNodeMaterial.setupEnvironment(builder: NodeBuilder): any`

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

### `MeshLambertNodeMaterial.setupLightingModel(): PhongLightingModel`

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

		return new PhongLightingModel( false ); // ( specular ) -> force lambert

	}
```
</details>


---

## Classes

### `MeshLambertNodeMaterial`

<details><summary>Class Code</summary>

```ts
class MeshLambertNodeMaterial extends NodeMaterial {

	static get type() {

		return 'MeshLambertNodeMaterial';

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
		this.isMeshLambertNodeMaterial = true;

		/**
		 * Set to `true` because lambert materials react on lights.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.lights = true;

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

		return new PhongLightingModel( false ); // ( specular ) -> force lambert

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

		return new PhongLightingModel( false ); // ( specular ) -> force lambert

	}
```
</details>


---