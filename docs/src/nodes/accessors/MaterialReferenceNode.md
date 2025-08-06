[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MaterialReferenceNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/MaterialReferenceNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ReferenceNode` | `./ReferenceNode.js` |
| `nodeObject` | `../tsl/TSLBase.js` |


---

## Functions

### `MaterialReferenceNode.updateReference(state: any): any`

**JSDoc:**
```typescript
/**
	 * Updates the reference based on the given state. The state is only evaluated
	 * {@link MaterialReferenceNode#material} is not set.
	 *
	 * @param {(NodeFrame|NodeBuilder)} state - The current state.
	 * @return {Object} The updated reference.
	 */
```

**Parameters:**

- **`state`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
updateReference( state ) {

		this.reference = this.material !== null ? this.material : state.material;

		return this.reference;

	}
```
</details>

### `materialReference(name: string, type: string, material: Material): MaterialReferenceNode`

**Parameters:**

- **`name`** `string`
- **`type`** `string`
- **`material`** `Material`

**Returns:** `MaterialReferenceNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( name, type, material = null ) => nodeObject( new MaterialReferenceNode( name, type, material ) )
```
</details>


---

## Classes

### `MaterialReferenceNode`

<details><summary>Class Code</summary>

```ts
class MaterialReferenceNode extends ReferenceNode {

	static get type() {

		return 'MaterialReferenceNode';

	}

	/**
	 * Constructs a new material reference node.
	 *
	 * @param {string} property - The name of the property the node refers to.
	 * @param {string} inputType - The uniform type that should be used to represent the property value.
	 * @param {?Material} [material=null] - The material the property belongs to. When no material is set,
	 * the node refers to the material of the current rendered object.
	 */
	constructor( property, inputType, material = null ) {

		super( property, inputType, material );

		/**
		 * The material the property belongs to. When no material is set,
		 * the node refers to the material of the current rendered object.
		 *
		 * @type {?Material}
		 * @default null
		 */
		this.material = material;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isMaterialReferenceNode = true;

	}

	/**
	 * Updates the reference based on the given state. The state is only evaluated
	 * {@link MaterialReferenceNode#material} is not set.
	 *
	 * @param {(NodeFrame|NodeBuilder)} state - The current state.
	 * @return {Object} The updated reference.
	 */
	updateReference( state ) {

		this.reference = this.material !== null ? this.material : state.material;

		return this.reference;

	}

}
```
</details>

#### Methods

##### `updateReference(state: any): any`

<details><summary>Code</summary>

```ts
updateReference( state ) {

		this.reference = this.material !== null ? this.material : state.material;

		return this.reference;

	}
```
</details>


---