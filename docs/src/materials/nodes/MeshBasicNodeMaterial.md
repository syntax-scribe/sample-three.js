[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MeshBasicNodeMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/nodes/MeshBasicNodeMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeMaterial` | `./NodeMaterial.js` |
| `materialLightMap` | `../../nodes/accessors/MaterialNode.js` |
| `BasicEnvironmentNode` | `../../nodes/lighting/BasicEnvironmentNode.js` |
| `BasicLightMapNode` | `../../nodes/lighting/BasicLightMapNode.js` |
| `BasicLightingModel` | `../../nodes/functions/BasicLightingModel.js` |
| `normalViewGeometry` | `../../nodes/accessors/Normal.js` |
| `diffuseColor` | `../../nodes/core/PropertyNode.js` |
| `directionToFaceDirection` | `../../nodes/display/FrontFacingNode.js` |
| `MeshBasicMaterial` | `../MeshBasicMaterial.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_defaultValues` | `MeshBasicMaterial` | let/var | `new MeshBasicMaterial()` | ✗ |
| `node` | `any` | let/var | `null` | ✗ |


---

## Functions

### `MeshBasicNodeMaterial.setupNormal(): any`

**JSDoc:**
```typescript
/**
	 * Basic materials are not affected by normal and bump maps so we
	 * return by default {@link normalViewGeometry}.
	 *
	 * @return {Node<vec3>} The normal node.
	 */
```

**Returns:** `any`

**Calls:**

- `directionToFaceDirection (from ../../nodes/display/FrontFacingNode.js)`

<details><summary>Code</summary>

```typescript
setupNormal() {

		return directionToFaceDirection( normalViewGeometry ); // see #28839

	}
```
</details>

### `MeshBasicNodeMaterial.setupEnvironment(builder: NodeBuilder): any`

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

### `MeshBasicNodeMaterial.setupLightMap(builder: NodeBuilder): any`

**JSDoc:**
```typescript
/**
	 * This method must be overwritten since light maps are evaluated
	 * with a special scaling factor for basic materials.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {?BasicLightMapNode<vec3>} The light map node.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
setupLightMap( builder ) {

		let node = null;

		if ( builder.material.lightMap ) {

			node = new BasicLightMapNode( materialLightMap );

		}

		return node;

	}
```
</details>

### `MeshBasicNodeMaterial.setupOutgoingLight(): any`

**JSDoc:**
```typescript
/**
	 * The material overwrites this method because `lights` is set to `true` but
	 * we still want to return the diffuse color as the outgoing light.
	 *
	 * @return {Node<vec3>} The outgoing light node.
	 */
```

**Returns:** `any`

<details><summary>Code</summary>

```typescript
setupOutgoingLight() {

		return diffuseColor.rgb;

	}
```
</details>

### `MeshBasicNodeMaterial.setupLightingModel(): BasicLightingModel`

**JSDoc:**
```typescript
/**
	 * Setups the lighting model.
	 *
	 * @return {BasicLightingModel} The lighting model.
	 */
```

**Returns:** `BasicLightingModel`

<details><summary>Code</summary>

```typescript
setupLightingModel() {

		return new BasicLightingModel();

	}
```
</details>


---

## Classes

### `MeshBasicNodeMaterial`

<details><summary>Class Code</summary>

```ts
class MeshBasicNodeMaterial extends NodeMaterial {

	static get type() {

		return 'MeshBasicNodeMaterial';

	}

	/**
	 * Constructs a new mesh basic node material.
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
		this.isMeshBasicNodeMaterial = true;

		/**
		 * Although the basic material is by definition unlit, we set
		 * this property to `true` since we use a lighting model to compute
		 * the outgoing light of the fragment shader.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.lights = true;

		this.setDefaultValues( _defaultValues );

		this.setValues( parameters );

	}

	/**
	 * Basic materials are not affected by normal and bump maps so we
	 * return by default {@link normalViewGeometry}.
	 *
	 * @return {Node<vec3>} The normal node.
	 */
	setupNormal() {

		return directionToFaceDirection( normalViewGeometry ); // see #28839

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
	 * This method must be overwritten since light maps are evaluated
	 * with a special scaling factor for basic materials.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {?BasicLightMapNode<vec3>} The light map node.
	 */
	setupLightMap( builder ) {

		let node = null;

		if ( builder.material.lightMap ) {

			node = new BasicLightMapNode( materialLightMap );

		}

		return node;

	}

	/**
	 * The material overwrites this method because `lights` is set to `true` but
	 * we still want to return the diffuse color as the outgoing light.
	 *
	 * @return {Node<vec3>} The outgoing light node.
	 */
	setupOutgoingLight() {

		return diffuseColor.rgb;

	}

	/**
	 * Setups the lighting model.
	 *
	 * @return {BasicLightingModel} The lighting model.
	 */
	setupLightingModel() {

		return new BasicLightingModel();

	}

}
```
</details>

#### Methods

##### `setupNormal(): any`

<details><summary>Code</summary>

```ts
setupNormal() {

		return directionToFaceDirection( normalViewGeometry ); // see #28839

	}
```
</details>

##### `setupEnvironment(builder: NodeBuilder): any`

<details><summary>Code</summary>

```ts
setupEnvironment( builder ) {

		const envNode = super.setupEnvironment( builder );

		return envNode ? new BasicEnvironmentNode( envNode ) : null;

	}
```
</details>

##### `setupLightMap(builder: NodeBuilder): any`

<details><summary>Code</summary>

```ts
setupLightMap( builder ) {

		let node = null;

		if ( builder.material.lightMap ) {

			node = new BasicLightMapNode( materialLightMap );

		}

		return node;

	}
```
</details>

##### `setupOutgoingLight(): any`

<details><summary>Code</summary>

```ts
setupOutgoingLight() {

		return diffuseColor.rgb;

	}
```
</details>

##### `setupLightingModel(): BasicLightingModel`

<details><summary>Code</summary>

```ts
setupLightingModel() {

		return new BasicLightingModel();

	}
```
</details>


---