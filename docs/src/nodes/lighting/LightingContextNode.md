[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LightingContextNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/LightingContextNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ContextNode` | `../core/ContextNode.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `float` | `../tsl/TSLBase.js` |
| `vec3` | `../tsl/TSLBase.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `reflectedLight` | `{ directDiffuse: any; directSpecular:...` | let/var | `{ directDiffuse, directSpecular, indirectDiffuse, indirectSpecular }` | ✗ |
| `context` | `{ radiance: any; irradiance: any; ibl...` | let/var | `{ radiance: vec3().toVar( 'radiance' ), irradiance: vec3().toVar( 'irradiance...` | ✗ |


---

## Functions

### `LightingContextNode.getContext(): { radiance: any; irradiance: any; iblIrradiance: any; ambientOcclusion: any; reflectedLight: { directDiffuse: any; directSpecular: any; indirectDiffuse: any; indirectSpecular: any; }; backdrop: any; backdropAlpha: any; }`

**JSDoc:**
```typescript
/**
	 * Returns a lighting context object.
	 *
	 * @return {{
	 * radiance: Node<vec3>,
	 * irradiance: Node<vec3>,
	 * iblIrradiance: Node<vec3>,
	 * ambientOcclusion: Node<float>,
	 * reflectedLight: {directDiffuse: Node<vec3>, directSpecular: Node<vec3>, indirectDiffuse: Node<vec3>, indirectSpecular: Node<vec3>},
	 * backdrop: Node<vec3>,
	 * backdropAlpha: Node<float>
	 * }} The lighting context object.
	 */
```

**Returns:** `{ radiance: any; irradiance: any; iblIrradiance: any; ambientOcclusion: any; reflectedLight: { directDiffuse: any; directSpecular: any; indirectDiffuse: any; indirectSpecular: any; }; backdrop: any; backdropAlpha: any; }`

**Calls:**

- `vec3().toVar`
- `float( 1 ).toVar`

<details><summary>Code</summary>

```typescript
getContext() {

		const { backdropNode, backdropAlphaNode } = this;

		const directDiffuse = vec3().toVar( 'directDiffuse' ),
			directSpecular = vec3().toVar( 'directSpecular' ),
			indirectDiffuse = vec3().toVar( 'indirectDiffuse' ),
			indirectSpecular = vec3().toVar( 'indirectSpecular' );

		const reflectedLight = {
			directDiffuse,
			directSpecular,
			indirectDiffuse,
			indirectSpecular
		};

		const context = {
			radiance: vec3().toVar( 'radiance' ),
			irradiance: vec3().toVar( 'irradiance' ),
			iblIrradiance: vec3().toVar( 'iblIrradiance' ),
			ambientOcclusion: float( 1 ).toVar( 'ambientOcclusion' ),
			reflectedLight,
			backdrop: backdropNode,
			backdropAlpha: backdropAlphaNode
		};

		return context;

	}
```
</details>

### `LightingContextNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `this.getContext`
- `super.setup`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		this.value = this._value || ( this._value = this.getContext() );
		this.value.lightingModel = this.lightingModel || builder.context.lightingModel;

		return super.setup( builder );

	}
```
</details>


---

## Classes

### `LightingContextNode`

<details><summary>Class Code</summary>

```ts
class LightingContextNode extends ContextNode {

	static get type() {

		return 'LightingContextNode';

	}

	/**
	 * Constructs a new lighting context node.
	 *
	 * @param {LightsNode} lightsNode - The lights node.
	 * @param {?LightingModel} [lightingModel=null] - The current lighting model.
	 * @param {?Node<vec3>} [backdropNode=null] - A backdrop node.
	 * @param {?Node<float>} [backdropAlphaNode=null] - A backdrop alpha node.
	 */
	constructor( lightsNode, lightingModel = null, backdropNode = null, backdropAlphaNode = null ) {

		super( lightsNode );

		/**
		 * The current lighting model.
		 *
		 * @type {?LightingModel}
		 * @default null
		 */
		this.lightingModel = lightingModel;

		/**
		 * A backdrop node.
		 *
		 * @type {?Node<vec3>}
		 * @default null
		 */
		this.backdropNode = backdropNode;

		/**
		 * A backdrop alpha node.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.backdropAlphaNode = backdropAlphaNode;

		this._value = null;

	}

	/**
	 * Returns a lighting context object.
	 *
	 * @return {{
	 * radiance: Node<vec3>,
	 * irradiance: Node<vec3>,
	 * iblIrradiance: Node<vec3>,
	 * ambientOcclusion: Node<float>,
	 * reflectedLight: {directDiffuse: Node<vec3>, directSpecular: Node<vec3>, indirectDiffuse: Node<vec3>, indirectSpecular: Node<vec3>},
	 * backdrop: Node<vec3>,
	 * backdropAlpha: Node<float>
	 * }} The lighting context object.
	 */
	getContext() {

		const { backdropNode, backdropAlphaNode } = this;

		const directDiffuse = vec3().toVar( 'directDiffuse' ),
			directSpecular = vec3().toVar( 'directSpecular' ),
			indirectDiffuse = vec3().toVar( 'indirectDiffuse' ),
			indirectSpecular = vec3().toVar( 'indirectSpecular' );

		const reflectedLight = {
			directDiffuse,
			directSpecular,
			indirectDiffuse,
			indirectSpecular
		};

		const context = {
			radiance: vec3().toVar( 'radiance' ),
			irradiance: vec3().toVar( 'irradiance' ),
			iblIrradiance: vec3().toVar( 'iblIrradiance' ),
			ambientOcclusion: float( 1 ).toVar( 'ambientOcclusion' ),
			reflectedLight,
			backdrop: backdropNode,
			backdropAlpha: backdropAlphaNode
		};

		return context;

	}

	setup( builder ) {

		this.value = this._value || ( this._value = this.getContext() );
		this.value.lightingModel = this.lightingModel || builder.context.lightingModel;

		return super.setup( builder );

	}

}
```
</details>

#### Methods

##### `getContext(): { radiance: any; irradiance: any; iblIrradiance: any; ambientOcclusion: any; reflectedLight: { directDiffuse: any; directSpecular: any; indirectDiffuse: any; indirectSpecular: any; }; backdrop: any; backdropAlpha: any; }`

<details><summary>Code</summary>

```ts
getContext() {

		const { backdropNode, backdropAlphaNode } = this;

		const directDiffuse = vec3().toVar( 'directDiffuse' ),
			directSpecular = vec3().toVar( 'directSpecular' ),
			indirectDiffuse = vec3().toVar( 'indirectDiffuse' ),
			indirectSpecular = vec3().toVar( 'indirectSpecular' );

		const reflectedLight = {
			directDiffuse,
			directSpecular,
			indirectDiffuse,
			indirectSpecular
		};

		const context = {
			radiance: vec3().toVar( 'radiance' ),
			irradiance: vec3().toVar( 'irradiance' ),
			iblIrradiance: vec3().toVar( 'iblIrradiance' ),
			ambientOcclusion: float( 1 ).toVar( 'ambientOcclusion' ),
			reflectedLight,
			backdrop: backdropNode,
			backdropAlpha: backdropAlphaNode
		};

		return context;

	}
```
</details>

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		this.value = this._value || ( this._value = this.getContext() );
		this.value.lightingModel = this.lightingModel || builder.context.lightingModel;

		return super.setup( builder );

	}
```
</details>


---