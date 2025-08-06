[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `AssignNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/AssignNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `../core/TempNode.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `nodeProxy` | `../tsl/TSLCore.js` |
| `vectorComponents` | `../core/constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `assignDifferentVector` | `boolean` | let/var | `vectorComponents.join( '' ).slice( 0, targetLength ) !== targetNode.components` | ✗ |
| `snippet` | `any` | let/var | `*not shown*` | ✗ |
| `splitNode` | `any` | let/var | `targetNode.node` | ✗ |
| `component` | `any` | let/var | `splitNode.components[ i ]` | ✗ |


---

## Functions

### `AssignNode.hasDependencies(): boolean`

**JSDoc:**
```typescript
/**
	 * Whether this node is used more than once in context of other nodes. This method
	 * is overwritten since it always returns `false` (assigns are unique).
	 *
	 * @return {boolean} A flag that indicates if there is more than one dependency to other nodes. Always `false`.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
hasDependencies() {

		return false;

	}
```
</details>

### `AssignNode.getNodeType(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `this.targetNode.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder, output ) {

		return output !== 'void' ? this.targetNode.getNodeType( builder ) : 'void';

	}
```
</details>

### `AssignNode.needsSplitAssign(builder: NodeBuilder): boolean`

**JSDoc:**
```typescript
/**
	 * Whether a split is required when assigning source to target. This can happen when the component length of
	 * target and source data type does not match.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {boolean} Whether a split is required when assigning source to target.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `boolean`

**Calls:**

- `builder.isAvailable`
- `builder.getTypeLength`
- `targetNode.node.getNodeType`
- `vectorComponents.join( '' ).slice`

<details><summary>Code</summary>

```typescript
needsSplitAssign( builder ) {

		const { targetNode } = this;

		if ( builder.isAvailable( 'swizzleAssign' ) === false && targetNode.isSplitNode && targetNode.components.length > 1 ) {

			const targetLength = builder.getTypeLength( targetNode.node.getNodeType( builder ) );
			const assignDifferentVector = vectorComponents.join( '' ).slice( 0, targetLength ) !== targetNode.components;

			return assignDifferentVector;

		}

		return false;

	}
```
</details>

### `AssignNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `builder.getNodeProperties`
- `targetNode.context`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const { targetNode, sourceNode } = this;

		const targetProperties = builder.getNodeProperties( targetNode );
		targetProperties.assign = true;

		const properties = builder.getNodeProperties( this );
		properties.sourceNode = sourceNode;
		properties.targetNode = targetNode.context( { assign: true } );

	}
```
</details>

### `AssignNode.generate(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `builder.getNodeProperties`
- `this.needsSplitAssign`
- `targetNode.build`
- `targetNode.getNodeType`
- `sourceNode.build`
- `sourceNode.getNodeType`
- `builder.getDataFromNode`
- `builder.getVarFromNode`
- `builder.getPropertyName`
- `builder.addLineFlowCode`
- `splitNode.node.context`
- `splitTargetNode.build`
- `builder.format`

**Internal Comments:**
```
// (x2)
```

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		const { targetNode, sourceNode } = builder.getNodeProperties( this );

		const needsSplitAssign = this.needsSplitAssign( builder );

		const target = targetNode.build( builder );
		const targetType = targetNode.getNodeType( builder );

		const source = sourceNode.build( builder, targetType );
		const sourceType = sourceNode.getNodeType( builder );

		const nodeData = builder.getDataFromNode( this );

		//

		let snippet;

		if ( nodeData.initialized === true ) {

			if ( output !== 'void' ) {

				snippet = target;

			}

		} else if ( needsSplitAssign ) {

			const sourceVar = builder.getVarFromNode( this, null, targetType );
			const sourceProperty = builder.getPropertyName( sourceVar );

			builder.addLineFlowCode( `${ sourceProperty } = ${ source }`, this );

			const splitNode = targetNode.node;
			const splitTargetNode = splitNode.node.context( { assign: true } );

			const targetRoot = splitTargetNode.build( builder );

			for ( let i = 0; i < splitNode.components.length; i ++ ) {

				const component = splitNode.components[ i ];

				builder.addLineFlowCode( `${ targetRoot }.${ component } = ${ sourceProperty }[ ${ i } ]`, this );

			}

			if ( output !== 'void' ) {

				snippet = target;

			}

		} else {

			snippet = `${ target } = ${ source }`;

			if ( output === 'void' || sourceType === 'void' ) {

				builder.addLineFlowCode( snippet, this );

				if ( output !== 'void' ) {

					snippet = target;

				}

			}

		}

		nodeData.initialized = true;

		return builder.format( snippet, targetType, output );

	}
```
</details>


---

## Classes

### `AssignNode`

<details><summary>Class Code</summary>

```ts
class AssignNode extends TempNode {

	static get type() {

		return 'AssignNode';

	}

	/**
	 * Constructs a new assign node.
	 *
	 * @param {Node} targetNode - The target node.
	 * @param {Node} sourceNode - The source type.
	 */
	constructor( targetNode, sourceNode ) {

		super();

		/**
		 * The target node.
		 *
		 * @type {Node}
		 */
		this.targetNode = targetNode;

		/**
		 * The source node.
		 *
		 * @type {Node}
		 */
		this.sourceNode = sourceNode;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isAssignNode = true;

	}

	/**
	 * Whether this node is used more than once in context of other nodes. This method
	 * is overwritten since it always returns `false` (assigns are unique).
	 *
	 * @return {boolean} A flag that indicates if there is more than one dependency to other nodes. Always `false`.
	 */
	hasDependencies() {

		return false;

	}

	getNodeType( builder, output ) {

		return output !== 'void' ? this.targetNode.getNodeType( builder ) : 'void';

	}

	/**
	 * Whether a split is required when assigning source to target. This can happen when the component length of
	 * target and source data type does not match.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {boolean} Whether a split is required when assigning source to target.
	 */
	needsSplitAssign( builder ) {

		const { targetNode } = this;

		if ( builder.isAvailable( 'swizzleAssign' ) === false && targetNode.isSplitNode && targetNode.components.length > 1 ) {

			const targetLength = builder.getTypeLength( targetNode.node.getNodeType( builder ) );
			const assignDifferentVector = vectorComponents.join( '' ).slice( 0, targetLength ) !== targetNode.components;

			return assignDifferentVector;

		}

		return false;

	}

	setup( builder ) {

		const { targetNode, sourceNode } = this;

		const targetProperties = builder.getNodeProperties( targetNode );
		targetProperties.assign = true;

		const properties = builder.getNodeProperties( this );
		properties.sourceNode = sourceNode;
		properties.targetNode = targetNode.context( { assign: true } );

	}

	generate( builder, output ) {

		const { targetNode, sourceNode } = builder.getNodeProperties( this );

		const needsSplitAssign = this.needsSplitAssign( builder );

		const target = targetNode.build( builder );
		const targetType = targetNode.getNodeType( builder );

		const source = sourceNode.build( builder, targetType );
		const sourceType = sourceNode.getNodeType( builder );

		const nodeData = builder.getDataFromNode( this );

		//

		let snippet;

		if ( nodeData.initialized === true ) {

			if ( output !== 'void' ) {

				snippet = target;

			}

		} else if ( needsSplitAssign ) {

			const sourceVar = builder.getVarFromNode( this, null, targetType );
			const sourceProperty = builder.getPropertyName( sourceVar );

			builder.addLineFlowCode( `${ sourceProperty } = ${ source }`, this );

			const splitNode = targetNode.node;
			const splitTargetNode = splitNode.node.context( { assign: true } );

			const targetRoot = splitTargetNode.build( builder );

			for ( let i = 0; i < splitNode.components.length; i ++ ) {

				const component = splitNode.components[ i ];

				builder.addLineFlowCode( `${ targetRoot }.${ component } = ${ sourceProperty }[ ${ i } ]`, this );

			}

			if ( output !== 'void' ) {

				snippet = target;

			}

		} else {

			snippet = `${ target } = ${ source }`;

			if ( output === 'void' || sourceType === 'void' ) {

				builder.addLineFlowCode( snippet, this );

				if ( output !== 'void' ) {

					snippet = target;

				}

			}

		}

		nodeData.initialized = true;

		return builder.format( snippet, targetType, output );

	}

}
```
</details>

#### Methods

##### `hasDependencies(): boolean`

<details><summary>Code</summary>

```ts
hasDependencies() {

		return false;

	}
```
</details>

##### `getNodeType(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
getNodeType( builder, output ) {

		return output !== 'void' ? this.targetNode.getNodeType( builder ) : 'void';

	}
```
</details>

##### `needsSplitAssign(builder: NodeBuilder): boolean`

<details><summary>Code</summary>

```ts
needsSplitAssign( builder ) {

		const { targetNode } = this;

		if ( builder.isAvailable( 'swizzleAssign' ) === false && targetNode.isSplitNode && targetNode.components.length > 1 ) {

			const targetLength = builder.getTypeLength( targetNode.node.getNodeType( builder ) );
			const assignDifferentVector = vectorComponents.join( '' ).slice( 0, targetLength ) !== targetNode.components;

			return assignDifferentVector;

		}

		return false;

	}
```
</details>

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const { targetNode, sourceNode } = this;

		const targetProperties = builder.getNodeProperties( targetNode );
		targetProperties.assign = true;

		const properties = builder.getNodeProperties( this );
		properties.sourceNode = sourceNode;
		properties.targetNode = targetNode.context( { assign: true } );

	}
```
</details>

##### `generate(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		const { targetNode, sourceNode } = builder.getNodeProperties( this );

		const needsSplitAssign = this.needsSplitAssign( builder );

		const target = targetNode.build( builder );
		const targetType = targetNode.getNodeType( builder );

		const source = sourceNode.build( builder, targetType );
		const sourceType = sourceNode.getNodeType( builder );

		const nodeData = builder.getDataFromNode( this );

		//

		let snippet;

		if ( nodeData.initialized === true ) {

			if ( output !== 'void' ) {

				snippet = target;

			}

		} else if ( needsSplitAssign ) {

			const sourceVar = builder.getVarFromNode( this, null, targetType );
			const sourceProperty = builder.getPropertyName( sourceVar );

			builder.addLineFlowCode( `${ sourceProperty } = ${ source }`, this );

			const splitNode = targetNode.node;
			const splitTargetNode = splitNode.node.context( { assign: true } );

			const targetRoot = splitTargetNode.build( builder );

			for ( let i = 0; i < splitNode.components.length; i ++ ) {

				const component = splitNode.components[ i ];

				builder.addLineFlowCode( `${ targetRoot }.${ component } = ${ sourceProperty }[ ${ i } ]`, this );

			}

			if ( output !== 'void' ) {

				snippet = target;

			}

		} else {

			snippet = `${ target } = ${ source }`;

			if ( output === 'void' || sourceType === 'void' ) {

				builder.addLineFlowCode( snippet, this );

				if ( output !== 'void' ) {

					snippet = target;

				}

			}

		}

		nodeData.initialized = true;

		return builder.format( snippet, targetType, output );

	}
```
</details>


---