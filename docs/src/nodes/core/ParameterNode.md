[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ParameterNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/ParameterNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `nodeObject` | `../tsl/TSLBase.js` |
| `PropertyNode` | `./PropertyNode.js` |


---

## Functions

### `ParameterNode.getHash(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getHash() {

		return this.uuid;

	}
```
</details>

### `ParameterNode.generate(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
generate() {

		return this.name;

	}
```
</details>

### `parameter(type: string, name: string): ParameterNode`

**Parameters:**

- **`type`** `string`
- **`name`** `string`

**Returns:** `ParameterNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( type, name ) => nodeObject( new ParameterNode( type, name ) )
```
</details>


---

## Classes

### `ParameterNode`

<details><summary>Class Code</summary>

```ts
class ParameterNode extends PropertyNode {

	static get type() {

		return 'ParameterNode';

	}

	/**
	 * Constructs a new parameter node.
	 *
	 * @param {string} nodeType - The type of the node.
	 * @param {?string} [name=null] - The name of the parameter in the shader.
	 */
	constructor( nodeType, name = null ) {

		super( nodeType, name );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isParameterNode = true;

	}

	getHash() {

		return this.uuid;

	}

	generate() {

		return this.name;

	}

}
```
</details>

#### Methods

##### `getHash(): string`

<details><summary>Code</summary>

```ts
getHash() {

		return this.uuid;

	}
```
</details>

##### `generate(): string`

<details><summary>Code</summary>

```ts
generate() {

		return this.name;

	}
```
</details>


---