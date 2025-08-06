[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BasicEnvironmentNode.js`

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
📂 **`src/nodes/lighting/BasicEnvironmentNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LightingNode` | `./LightingNode.js` |
| `cubeMapNode` | `../utils/CubeMapNode.js` |


---

## Functions

### `BasicEnvironmentNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `cubeMapNode (from ../utils/CubeMapNode.js)`

**Internal Comments:**
```
// environment property is used in the finish() method of BasicLightingModel (x5)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		// environment property is used in the finish() method of BasicLightingModel

		builder.context.environment = cubeMapNode( this.envNode );

	}
```
</details>


---

## Classes

### `BasicEnvironmentNode`

<details><summary>Class Code</summary>

```ts
class BasicEnvironmentNode extends LightingNode {

	static get type() {

		return 'BasicEnvironmentNode';

	}

	/**
	 * Constructs a new basic environment node.
	 *
	 * @param {Node} [envNode=null] - A node representing the environment.
	 */
	constructor( envNode = null ) {

		super();

		/**
		 * A node representing the environment.
		 *
		 * @type {Node}
		 * @default null
		 */
		this.envNode = envNode;

	}

	setup( builder ) {

		// environment property is used in the finish() method of BasicLightingModel

		builder.context.environment = cubeMapNode( this.envNode );

	}

}
```
</details>

#### Methods

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		// environment property is used in the finish() method of BasicLightingModel

		builder.context.environment = cubeMapNode( this.envNode );

	}
```
</details>


---