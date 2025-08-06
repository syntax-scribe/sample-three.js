[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TempNode.js`

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
📂 **`src/nodes/core/TempNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `./Node.js` |


---

## Functions

### `TempNode.hasDependencies(builder: NodeBuilder): boolean`

**JSDoc:**
```typescript
/**
	 * Whether this node is used more than once in context of other nodes.
	 *
	 * @param {NodeBuilder} builder - The node builder.
	 * @return {boolean} A flag that indicates if there is more than one dependency to other nodes.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `boolean`

**Calls:**

- `builder.getDataFromNode`

<details><summary>Code</summary>

```typescript
hasDependencies( builder ) {

		return builder.getDataFromNode( this ).usageCount > 1;

	}
```
</details>

### `TempNode.build(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `builder.getBuildStage`
- `builder.getVectorType`
- `this.getNodeType`
- `builder.getDataFromNode`
- `builder.format`
- `this.hasDependencies`
- `super.build`
- `builder.getVarFromNode`
- `builder.getPropertyName`
- `builder.addLineFlowCode`

<details><summary>Code</summary>

```typescript
build( builder, output ) {

		const buildStage = builder.getBuildStage();

		if ( buildStage === 'generate' ) {

			const type = builder.getVectorType( this.getNodeType( builder, output ) );
			const nodeData = builder.getDataFromNode( this );

			if ( nodeData.propertyName !== undefined ) {

				return builder.format( nodeData.propertyName, type, output );

			} else if ( type !== 'void' && output !== 'void' && this.hasDependencies( builder ) ) {

				const snippet = super.build( builder, type );

				const nodeVar = builder.getVarFromNode( this, null, type );
				const propertyName = builder.getPropertyName( nodeVar );

				builder.addLineFlowCode( `${ propertyName } = ${ snippet }`, this );

				nodeData.snippet = snippet;
				nodeData.propertyName = propertyName;

				return builder.format( nodeData.propertyName, type, output );

			}

		}

		return super.build( builder, output );

	}
```
</details>


---

## Classes

### `TempNode`

<details><summary>Class Code</summary>

```ts
class TempNode extends Node {

	static get type() {

		return 'TempNode';

	}

	/**
	 * Constructs a temp node.
	 *
	 * @param {?string} nodeType - The node type.
	 */
	constructor( nodeType = null ) {

		super( nodeType );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isTempNode = true;

	}

	/**
	 * Whether this node is used more than once in context of other nodes.
	 *
	 * @param {NodeBuilder} builder - The node builder.
	 * @return {boolean} A flag that indicates if there is more than one dependency to other nodes.
	 */
	hasDependencies( builder ) {

		return builder.getDataFromNode( this ).usageCount > 1;

	}

	build( builder, output ) {

		const buildStage = builder.getBuildStage();

		if ( buildStage === 'generate' ) {

			const type = builder.getVectorType( this.getNodeType( builder, output ) );
			const nodeData = builder.getDataFromNode( this );

			if ( nodeData.propertyName !== undefined ) {

				return builder.format( nodeData.propertyName, type, output );

			} else if ( type !== 'void' && output !== 'void' && this.hasDependencies( builder ) ) {

				const snippet = super.build( builder, type );

				const nodeVar = builder.getVarFromNode( this, null, type );
				const propertyName = builder.getPropertyName( nodeVar );

				builder.addLineFlowCode( `${ propertyName } = ${ snippet }`, this );

				nodeData.snippet = snippet;
				nodeData.propertyName = propertyName;

				return builder.format( nodeData.propertyName, type, output );

			}

		}

		return super.build( builder, output );

	}

}
```
</details>

#### Methods

##### `hasDependencies(builder: NodeBuilder): boolean`

<details><summary>Code</summary>

```ts
hasDependencies( builder ) {

		return builder.getDataFromNode( this ).usageCount > 1;

	}
```
</details>

##### `build(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
build( builder, output ) {

		const buildStage = builder.getBuildStage();

		if ( buildStage === 'generate' ) {

			const type = builder.getVectorType( this.getNodeType( builder, output ) );
			const nodeData = builder.getDataFromNode( this );

			if ( nodeData.propertyName !== undefined ) {

				return builder.format( nodeData.propertyName, type, output );

			} else if ( type !== 'void' && output !== 'void' && this.hasDependencies( builder ) ) {

				const snippet = super.build( builder, type );

				const nodeVar = builder.getVarFromNode( this, null, type );
				const propertyName = builder.getPropertyName( nodeVar );

				builder.addLineFlowCode( `${ propertyName } = ${ snippet }`, this );

				nodeData.snippet = snippet;
				nodeData.propertyName = propertyName;

				return builder.format( nodeData.propertyName, type, output );

			}

		}

		return super.build( builder, output );

	}
```
</details>


---