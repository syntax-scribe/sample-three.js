[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `StorageArrayElementNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/utils/StorageArrayElementNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `nodeProxy` | `../tsl/TSLBase.js` |
| `ArrayElementNode` | `./ArrayElementNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `structTypeNode` | `any` | let/var | `this.storageBufferNode.structTypeNode` | ✗ |
| `snippet` | `any` | let/var | `*not shown*` | ✗ |
| `isAssignContext` | `any` | let/var | `builder.context.assign` | ✗ |


---

## Functions

### `StorageArrayElementNode.getMemberType(builder: any, name: any): any`

**Parameters:**

- **`builder`** `any`
- **`name`** `any`

**Returns:** `any`

**Calls:**

- `structTypeNode.getMemberType`

<details><summary>Code</summary>

```typescript
getMemberType( builder, name ) {

		const structTypeNode = this.storageBufferNode.structTypeNode;

		if ( structTypeNode ) {

			return structTypeNode.getMemberType( builder, name );

		}

		return 'void';

	}
```
</details>

### `StorageArrayElementNode.setup(builder: any): Node`

**Parameters:**

- **`builder`** `any`

**Returns:** `Node`

**Calls:**

- `builder.isAvailable`
- `builder.setupPBO`
- `super.setup`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		if ( builder.isAvailable( 'storageBuffer' ) === false ) {

			if ( this.node.isPBO === true ) {

				builder.setupPBO( this.node );

			}

		}

		return super.setup( builder );

	}
```
</details>

### `StorageArrayElementNode.generate(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `builder.isAvailable`
- `builder.generatePBO`
- `this.node.build`
- `super.generate`
- `this.getNodeType`
- `builder.format`

**Internal Comments:**
```
//
```

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		let snippet;

		const isAssignContext = builder.context.assign;

		//

		if ( builder.isAvailable( 'storageBuffer' ) === false ) {

			if ( this.node.isPBO === true && isAssignContext !== true && ( this.node.value.isInstancedBufferAttribute || builder.shaderStage !== 'compute' ) ) {

				snippet = builder.generatePBO( this );

			} else {

				snippet = this.node.build( builder );

			}

		} else {

			snippet = super.generate( builder );

		}

		if ( isAssignContext !== true ) {

			const type = this.getNodeType( builder );

			snippet = builder.format( snippet, type, output );

		}

		return snippet;

	}
```
</details>


---

## Classes

### `StorageArrayElementNode`

<details><summary>Class Code</summary>

```ts
class StorageArrayElementNode extends ArrayElementNode {

	static get type() {

		return 'StorageArrayElementNode';

	}

	/**
	 * Constructs storage buffer element node.
	 *
	 * @param {StorageBufferNode} storageBufferNode - The storage buffer node.
	 * @param {Node} indexNode - The index node that defines the element access.
	 */
	constructor( storageBufferNode, indexNode ) {

		super( storageBufferNode, indexNode );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isStorageArrayElementNode = true;

	}

	/**
	 * The storage buffer node.
	 *
	 * @param {Node} value
	 * @type {StorageBufferNode}
	 */
	set storageBufferNode( value ) {

		this.node = value;

	}

	get storageBufferNode() {

		return this.node;

	}

	getMemberType( builder, name ) {

		const structTypeNode = this.storageBufferNode.structTypeNode;

		if ( structTypeNode ) {

			return structTypeNode.getMemberType( builder, name );

		}

		return 'void';

	}

	setup( builder ) {

		if ( builder.isAvailable( 'storageBuffer' ) === false ) {

			if ( this.node.isPBO === true ) {

				builder.setupPBO( this.node );

			}

		}

		return super.setup( builder );

	}

	generate( builder, output ) {

		let snippet;

		const isAssignContext = builder.context.assign;

		//

		if ( builder.isAvailable( 'storageBuffer' ) === false ) {

			if ( this.node.isPBO === true && isAssignContext !== true && ( this.node.value.isInstancedBufferAttribute || builder.shaderStage !== 'compute' ) ) {

				snippet = builder.generatePBO( this );

			} else {

				snippet = this.node.build( builder );

			}

		} else {

			snippet = super.generate( builder );

		}

		if ( isAssignContext !== true ) {

			const type = this.getNodeType( builder );

			snippet = builder.format( snippet, type, output );

		}

		return snippet;

	}

}
```
</details>

#### Methods

##### `getMemberType(builder: any, name: any): any`

<details><summary>Code</summary>

```ts
getMemberType( builder, name ) {

		const structTypeNode = this.storageBufferNode.structTypeNode;

		if ( structTypeNode ) {

			return structTypeNode.getMemberType( builder, name );

		}

		return 'void';

	}
```
</details>

##### `setup(builder: any): Node`

<details><summary>Code</summary>

```ts
setup( builder ) {

		if ( builder.isAvailable( 'storageBuffer' ) === false ) {

			if ( this.node.isPBO === true ) {

				builder.setupPBO( this.node );

			}

		}

		return super.setup( builder );

	}
```
</details>

##### `generate(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		let snippet;

		const isAssignContext = builder.context.assign;

		//

		if ( builder.isAvailable( 'storageBuffer' ) === false ) {

			if ( this.node.isPBO === true && isAssignContext !== true && ( this.node.value.isInstancedBufferAttribute || builder.shaderStage !== 'compute' ) ) {

				snippet = builder.generatePBO( this );

			} else {

				snippet = this.node.build( builder );

			}

		} else {

			snippet = super.generate( builder );

		}

		if ( isAssignContext !== true ) {

			const type = this.getNodeType( builder );

			snippet = builder.format( snippet, type, output );

		}

		return snippet;

	}
```
</details>


---