[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `UniformGroupNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/UniformGroupNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `./Node.js` |


---

## Functions

### `UniformGroupNode.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		data.name = this.name;
		data.version = this.version;
		data.shared = this.shared;

	}
```
</details>

### `UniformGroupNode.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		this.name = data.name;
		this.version = data.version;
		this.shared = data.shared;

	}
```
</details>

### `uniformGroup(name: string): UniformGroupNode`

**Parameters:**

- **`name`** `string`

**Returns:** `UniformGroupNode`

<details><summary>Code</summary>

```typescript
( name ) => new UniformGroupNode( name )
```
</details>

### `sharedUniformGroup(name: string, order: number): UniformGroupNode`

**Parameters:**

- **`name`** `string`
- **`order`** `number`

**Returns:** `UniformGroupNode`

<details><summary>Code</summary>

```typescript
( name, order = 0 ) => new UniformGroupNode( name, true, order )
```
</details>


---

## Classes

### `UniformGroupNode`

<details><summary>Class Code</summary>

```ts
class UniformGroupNode extends Node {

	static get type() {

		return 'UniformGroupNode';

	}

	/**
	 * Constructs a new uniform group node.
	 *
	 * @param {string} name - The name of the uniform group node.
	 * @param {boolean} [shared=false] - Whether this uniform group node is shared or not.
	 * @param {number} [order=1] - Influences the internal sorting.
	 */
	constructor( name, shared = false, order = 1 ) {

		super( 'string' );

		/**
		 * The name of the uniform group node.
		 *
		 * @type {string}
		 */
		this.name = name;

		/**
		 * Whether this uniform group node is shared or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.shared = shared;

		/**
		 * Influences the internal sorting.
		 * TODO: Add details when this property should be changed.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.order = order;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isUniformGroup = true;

	}

	serialize( data ) {

		super.serialize( data );

		data.name = this.name;
		data.version = this.version;
		data.shared = this.shared;

	}

	deserialize( data ) {

		super.deserialize( data );

		this.name = data.name;
		this.version = data.version;
		this.shared = data.shared;

	}

}
```
</details>

#### Methods

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		data.name = this.name;
		data.version = this.version;
		data.shared = this.shared;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		this.name = data.name;
		this.version = data.version;
		this.shared = data.shared;

	}
```
</details>


---