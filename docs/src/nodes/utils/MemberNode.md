[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MemberNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/utils/MemberNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |


---

## Functions

### `MemberNode.getNodeType(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `this.node.getMemberType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return this.node.getMemberType( builder, this.property );

	}
```
</details>

### `MemberNode.generate(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `this.node.build`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const propertyName = this.node.build( builder );

		return propertyName + '.' + this.property;

	}
```
</details>


---

## Classes

### `MemberNode`

<details><summary>Class Code</summary>

```ts
class MemberNode extends Node {

	static get type() {

		return 'MemberNode';

	}

	/**
	 * Constructs an array element node.
	 *
	 * @param {Node} node - The array-like node.
	 * @param {string} property - The property name.
	 */
	constructor( node, property ) {

		super();

		/**
		 * The array-like node.
		 *
		 * @type {Node}
		 */
		this.node = node;

		/**
		 * The property name.
		 *
		 * @type {Node}
		 */
		this.property = property;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isMemberNode = true;

	}

	getNodeType( builder ) {

		return this.node.getMemberType( builder, this.property );

	}

	generate( builder ) {

		const propertyName = this.node.build( builder );

		return propertyName + '.' + this.property;

	}

}
```
</details>

#### Methods

##### `getNodeType(builder: any): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return this.node.getMemberType( builder, this.property );

	}
```
</details>

##### `generate(builder: any): string`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const propertyName = this.node.build( builder );

		return propertyName + '.' + this.property;

	}
```
</details>


---