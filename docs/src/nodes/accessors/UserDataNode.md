[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `UserDataNode.js`

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
📂 **`src/nodes/accessors/UserDataNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ReferenceNode` | `./ReferenceNode.js` |
| `nodeObject` | `../tsl/TSLBase.js` |


---

## Functions

### `UserDataNode.updateReference(state: any): any`

**JSDoc:**
```typescript
/**
	 * Overwritten to make sure {@link ReferenceNode#reference} points to the correct
	 * `userData` field.
	 *
	 * @param {(NodeFrame|NodeBuilder)} state - The current state to evaluate.
	 * @return {Object} A reference to the `userData` field.
	 */
```

**Parameters:**

- **`state`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
updateReference( state ) {

		this.reference = this.userData !== null ? this.userData : state.object.userData;

		return this.reference;

	}
```
</details>

### `userData(name: string, inputType: string, userData: any): UserDataNode`

**Parameters:**

- **`name`** `string`
- **`inputType`** `string`
- **`userData`** `any`

**Returns:** `UserDataNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( name, inputType, userData ) => nodeObject( new UserDataNode( name, inputType, userData ) )
```
</details>


---

## Classes

### `UserDataNode`

<details><summary>Class Code</summary>

```ts
class UserDataNode extends ReferenceNode {

	static get type() {

		return 'UserDataNode';

	}

	/**
	 * Constructs a new user data node.
	 *
	 * @param {string} property - The property name that should be referenced by the node.
	 * @param {string} inputType - The node data type of the reference.
	 * @param {?Object} [userData=null] - A reference to the `userData` object. If not provided, the `userData` property of the 3D object that uses the node material is evaluated.
	 */
	constructor( property, inputType, userData = null ) {

		super( property, inputType, userData );

		/**
		 * A reference to the `userData` object. If not provided, the `userData`
		 * property of the 3D object that uses the node material is evaluated.
		 *
		 * @type {?Object}
		 * @default null
		 */
		this.userData = userData;

	}

	/**
	 * Overwritten to make sure {@link ReferenceNode#reference} points to the correct
	 * `userData` field.
	 *
	 * @param {(NodeFrame|NodeBuilder)} state - The current state to evaluate.
	 * @return {Object} A reference to the `userData` field.
	 */
	updateReference( state ) {

		this.reference = this.userData !== null ? this.userData : state.object.userData;

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

		this.reference = this.userData !== null ? this.userData : state.object.userData;

		return this.reference;

	}
```
</details>


---