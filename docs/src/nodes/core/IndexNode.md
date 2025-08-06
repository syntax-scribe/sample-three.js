[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `IndexNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/IndexNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `./Node.js` |
| `nodeImmutable` | `../tsl/TSLBase.js` |
| `varying` | `../tsl/TSLBase.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `string` | let/var | `this.scope` | ✗ |
| `propertyName` | `any` | let/var | `*not shown*` | ✗ |
| `output` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `IndexNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this.getNodeType`
- `builder.getVertexIndex`
- `builder.getInstanceIndex`
- `builder.getDrawIndex`
- `builder.getInvocationLocalIndex`
- `builder.getInvocationSubgroupIndex`
- `builder.getSubgroupIndex`
- `varying (from ../tsl/TSLBase.js)`
- `nodeVarying.build`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const nodeType = this.getNodeType( builder );
		const scope = this.scope;

		let propertyName;

		if ( scope === IndexNode.VERTEX ) {

			propertyName = builder.getVertexIndex();

		} else if ( scope === IndexNode.INSTANCE ) {

			propertyName = builder.getInstanceIndex();

		} else if ( scope === IndexNode.DRAW ) {

			propertyName = builder.getDrawIndex();

		} else if ( scope === IndexNode.INVOCATION_LOCAL ) {

			propertyName = builder.getInvocationLocalIndex();

		} else if ( scope === IndexNode.INVOCATION_SUBGROUP ) {

			propertyName = builder.getInvocationSubgroupIndex();

		} else if ( scope === IndexNode.SUBGROUP ) {

			propertyName = builder.getSubgroupIndex();

		} else {

			throw new Error( 'THREE.IndexNode: Unknown scope: ' + scope );

		}

		let output;

		if ( builder.shaderStage === 'vertex' || builder.shaderStage === 'compute' ) {

			output = propertyName;

		} else {

			const nodeVarying = varying( this );

			output = nodeVarying.build( builder, nodeType );

		}

		return output;

	}
```
</details>


---

## Classes

### `IndexNode`

<details><summary>Class Code</summary>

```ts
class IndexNode extends Node {

	static get type() {

		return 'IndexNode';

	}

	/**
	 * Constructs a new index node.
	 *
	 * @param {('vertex'|'instance'|'subgroup'|'invocationLocal'|'invocationSubgroup'|'draw')} scope - The scope of the index node.
	 */
	constructor( scope ) {

		super( 'uint' );

		/**
		 * The scope of the index node.
		 *
		 * @type {string}
		 */
		this.scope = scope;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isIndexNode = true;

	}

	generate( builder ) {

		const nodeType = this.getNodeType( builder );
		const scope = this.scope;

		let propertyName;

		if ( scope === IndexNode.VERTEX ) {

			propertyName = builder.getVertexIndex();

		} else if ( scope === IndexNode.INSTANCE ) {

			propertyName = builder.getInstanceIndex();

		} else if ( scope === IndexNode.DRAW ) {

			propertyName = builder.getDrawIndex();

		} else if ( scope === IndexNode.INVOCATION_LOCAL ) {

			propertyName = builder.getInvocationLocalIndex();

		} else if ( scope === IndexNode.INVOCATION_SUBGROUP ) {

			propertyName = builder.getInvocationSubgroupIndex();

		} else if ( scope === IndexNode.SUBGROUP ) {

			propertyName = builder.getSubgroupIndex();

		} else {

			throw new Error( 'THREE.IndexNode: Unknown scope: ' + scope );

		}

		let output;

		if ( builder.shaderStage === 'vertex' || builder.shaderStage === 'compute' ) {

			output = propertyName;

		} else {

			const nodeVarying = varying( this );

			output = nodeVarying.build( builder, nodeType );

		}

		return output;

	}

}
```
</details>

#### Methods

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const nodeType = this.getNodeType( builder );
		const scope = this.scope;

		let propertyName;

		if ( scope === IndexNode.VERTEX ) {

			propertyName = builder.getVertexIndex();

		} else if ( scope === IndexNode.INSTANCE ) {

			propertyName = builder.getInstanceIndex();

		} else if ( scope === IndexNode.DRAW ) {

			propertyName = builder.getDrawIndex();

		} else if ( scope === IndexNode.INVOCATION_LOCAL ) {

			propertyName = builder.getInvocationLocalIndex();

		} else if ( scope === IndexNode.INVOCATION_SUBGROUP ) {

			propertyName = builder.getInvocationSubgroupIndex();

		} else if ( scope === IndexNode.SUBGROUP ) {

			propertyName = builder.getSubgroupIndex();

		} else {

			throw new Error( 'THREE.IndexNode: Unknown scope: ' + scope );

		}

		let output;

		if ( builder.shaderStage === 'vertex' || builder.shaderStage === 'compute' ) {

			output = propertyName;

		} else {

			const nodeVarying = varying( this );

			output = nodeVarying.build( builder, nodeType );

		}

		return output;

	}
```
</details>


---