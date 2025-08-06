[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BasicLightMapNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/BasicLightMapNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LightingNode` | `./LightingNode.js` |
| `float` | `../tsl/TSLBase.js` |


---

## Functions

### `BasicLightMapNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `float (from ../tsl/TSLBase.js)`
- `this.lightMapNode.mul`

**Internal Comments:**
```
// irradianceLightMap property is used in the indirectDiffuse() method of BasicLightingModel (x2)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		// irradianceLightMap property is used in the indirectDiffuse() method of BasicLightingModel

		const RECIPROCAL_PI = float( 1 / Math.PI );

		builder.context.irradianceLightMap = this.lightMapNode.mul( RECIPROCAL_PI );

	}
```
</details>


---

## Classes

### `BasicLightMapNode`

<details><summary>Class Code</summary>

```ts
class BasicLightMapNode extends LightingNode {

	static get type() {

		return 'BasicLightMapNode';

	}

	/**
	 * Constructs a new basic light map node.
	 *
	 * @param {?Node<vec3>} [lightMapNode=null] - The light map node.
	 */
	constructor( lightMapNode = null ) {

		super();

		/**
		 * The light map node.
		 *
		 * @type {?Node<vec3>}
		 */
		this.lightMapNode = lightMapNode;

	}

	setup( builder ) {

		// irradianceLightMap property is used in the indirectDiffuse() method of BasicLightingModel

		const RECIPROCAL_PI = float( 1 / Math.PI );

		builder.context.irradianceLightMap = this.lightMapNode.mul( RECIPROCAL_PI );

	}

}
```
</details>

#### Methods

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		// irradianceLightMap property is used in the indirectDiffuse() method of BasicLightingModel

		const RECIPROCAL_PI = float( 1 / Math.PI );

		builder.context.irradianceLightMap = this.lightMapNode.mul( RECIPROCAL_PI );

	}
```
</details>


---