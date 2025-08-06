[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `IrradianceNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/IrradianceNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LightingNode` | `./LightingNode.js` |


---

## Functions

### `IrradianceNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `builder.context.irradiance.addAssign`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		builder.context.irradiance.addAssign( this.node );

	}
```
</details>


---

## Classes

### `IrradianceNode`

<details><summary>Class Code</summary>

```ts
class IrradianceNode extends LightingNode {

	static get type() {

		return 'IrradianceNode';

	}

	/**
	 * Constructs a new irradiance node.
	 *
	 * @param {Node<vec3>} node - A node contributing irradiance.
	 */
	constructor( node ) {

		super();

		/**
		 * A node contributing irradiance.
		 *
		 * @type {Node<vec3>}
		 */
		this.node = node;

	}

	setup( builder ) {

		builder.context.irradiance.addAssign( this.node );

	}

}
```
</details>

#### Methods

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		builder.context.irradiance.addAssign( this.node );

	}
```
</details>


---