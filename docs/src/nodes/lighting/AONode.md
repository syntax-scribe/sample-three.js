[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `AONode.js`

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
📂 **`src/nodes/lighting/AONode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LightingNode` | `./LightingNode.js` |


---

## Functions

### `AONode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `builder.context.ambientOcclusion.mulAssign`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		builder.context.ambientOcclusion.mulAssign( this.aoNode );

	}
```
</details>


---

## Classes

### `AONode`

<details><summary>Class Code</summary>

```ts
class AONode extends LightingNode {

	static get type() {

		return 'AONode';

	}

	/**
	 * Constructs a new AO node.
	 *
	 * @param {?Node<float>} [aoNode=null] - The ambient occlusion node.
	 */
	constructor( aoNode = null ) {

		super();

		/**
		 * The ambient occlusion node.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.aoNode = aoNode;

	}

	setup( builder ) {

		builder.context.ambientOcclusion.mulAssign( this.aoNode );

	}

}
```
</details>

#### Methods

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		builder.context.ambientOcclusion.mulAssign( this.aoNode );

	}
```
</details>


---