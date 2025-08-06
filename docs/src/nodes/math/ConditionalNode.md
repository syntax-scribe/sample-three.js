[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ConditionalNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/math/ConditionalNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `property` | `../core/PropertyNode.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `nodeProxy` | `../tsl/TSLCore.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `elseNode` | `any` | let/var | `this.elseNode ? this.elseNode.cache() : null` | ✗ |
| `currentNodeBlock` | `any` | let/var | `builder.context.nodeBlock` | ✗ |
| `isUniformFlow` | `any` | let/var | `builder.context.uniformFlow` | ✗ |
| `functionNode` | `any` | let/var | `builder.currentFunctionNode` | ✗ |
| `needsOutput` | `boolean` | let/var | `output !== 'void'` | ✗ |
| `nodeProperty` | `string \| Node` | let/var | `needsOutput ? property( type ).build( builder ) : ''` | ✗ |
| `isUniformFlow` | `any` | let/var | `builder.context.uniformFlow` | ✗ |


---

## Functions

### `ConditionalNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node type is inferred from the if/else
	 * nodes.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `builder.getNodeProperties`
- `builder.flowBuildStage`
- `this.getNodeType`
- `ifNode.getNodeType`
- `elseNode.getNodeType`
- `builder.getTypeLength`

**Internal Comments:**
```
// fallback setup (x4)
```

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		const { ifNode, elseNode } = builder.getNodeProperties( this );

		if ( ifNode === undefined ) {

			// fallback setup

			builder.flowBuildStage( this, 'setup' );

			return this.getNodeType( builder );

		}

		const ifType = ifNode.getNodeType( builder );

		if ( elseNode !== null ) {

			const elseType = elseNode.getNodeType( builder );

			if ( builder.getTypeLength( elseType ) > builder.getTypeLength( ifType ) ) {

				return elseType;

			}

		}

		return ifType;

	}
```
</details>

### `ConditionalNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `this.condNode.cache`
- `this.ifNode.cache`
- `this.elseNode.cache`
- `builder.getDataFromNode`
- `builder.getNodeProperties`
- `ifNode.context`
- `elseNode.context`

**Internal Comments:**
```
// (x4)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const condNode = this.condNode.cache();
		const ifNode = this.ifNode.cache();
		const elseNode = this.elseNode ? this.elseNode.cache() : null;

		//

		const currentNodeBlock = builder.context.nodeBlock;

		builder.getDataFromNode( ifNode ).parentNodeBlock = currentNodeBlock;
		if ( elseNode !== null ) builder.getDataFromNode( elseNode ).parentNodeBlock = currentNodeBlock;

		//

		const isUniformFlow = builder.context.uniformFlow;

		const properties = builder.getNodeProperties( this );
		properties.condNode = condNode;
		properties.ifNode = isUniformFlow ? ifNode : ifNode.context( { nodeBlock: ifNode } );
		properties.elseNode = elseNode ? ( isUniformFlow ? elseNode : elseNode.context( { nodeBlock: elseNode } ) ) : null;

	}
```
</details>

### `ConditionalNode.generate(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `this.getNodeType`
- `builder.getDataFromNode`
- `builder.getNodeProperties`
- `property( type ).build`
- `condNode.build`
- `ifNode.build`
- `elseNode.build`
- `builder.getTernary`
- `builder.format`
- `builder.addFlowCode( `\n${ builder.tab }if ( ${ nodeSnippet } ) {\n\n` ).addFlowTab`
- `console.warn`
- `builder.removeFlowTab().addFlowCode`
- `builder.addFlowCode( ' else {\n\n' ).addFlowTab`
- `builder.addFlowCode`

**Internal Comments:**
```
// TODO: If node property already exists return something else
```

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		const type = this.getNodeType( builder );

		const nodeData = builder.getDataFromNode( this );

		if ( nodeData.nodeProperty !== undefined ) {

			return nodeData.nodeProperty;

		}

		const { condNode, ifNode, elseNode } = builder.getNodeProperties( this );

		const functionNode = builder.currentFunctionNode;
		const needsOutput = output !== 'void';
		const nodeProperty = needsOutput ? property( type ).build( builder ) : '';

		nodeData.nodeProperty = nodeProperty;

		const nodeSnippet = condNode.build( builder, 'bool' );
		const isUniformFlow = builder.context.uniformFlow;

		if ( isUniformFlow && elseNode !== null ) {

			const ifSnippet = ifNode.build( builder, type );
			const elseSnippet = elseNode.build( builder, type );

			const mathSnippet = builder.getTernary( nodeSnippet, ifSnippet, elseSnippet );

			// TODO: If node property already exists return something else

			return builder.format( mathSnippet, type, output );

		}

		builder.addFlowCode( `\n${ builder.tab }if ( ${ nodeSnippet } ) {\n\n` ).addFlowTab();

		let ifSnippet = ifNode.build( builder, type );

		if ( ifSnippet ) {

			if ( needsOutput ) {

				ifSnippet = nodeProperty + ' = ' + ifSnippet + ';';

			} else {

				ifSnippet = 'return ' + ifSnippet + ';';

				if ( functionNode === null ) {

					console.warn( 'THREE.TSL: Return statement used in an inline \'Fn()\'. Define a layout struct to allow return values.' );

					ifSnippet = '// ' + ifSnippet;

				}

			}

		}

		builder.removeFlowTab().addFlowCode( builder.tab + '\t' + ifSnippet + '\n\n' + builder.tab + '}' );

		if ( elseNode !== null ) {

			builder.addFlowCode( ' else {\n\n' ).addFlowTab();

			let elseSnippet = elseNode.build( builder, type );

			if ( elseSnippet ) {

				if ( needsOutput ) {

					elseSnippet = nodeProperty + ' = ' + elseSnippet + ';';

				} else {

					elseSnippet = 'return ' + elseSnippet + ';';

					if ( functionNode === null ) {

						console.warn( 'THREE.TSL: Return statement used in an inline \'Fn()\'. Define a layout struct to allow return values.' );

						elseSnippet = '// ' + elseSnippet;

					}

				}

			}

			builder.removeFlowTab().addFlowCode( builder.tab + '\t' + elseSnippet + '\n\n' + builder.tab + '}\n\n' );

		} else {

			builder.addFlowCode( '\n\n' );

		}

		return builder.format( nodeProperty, type, output );

	}
```
</details>


---

## Classes

### `ConditionalNode`

<details><summary>Class Code</summary>

```ts
class ConditionalNode extends Node {

	static get type() {

		return 'ConditionalNode';

	}

	/**
	 * Constructs a new conditional node.
	 *
	 * @param {Node} condNode - The node that defines the condition.
	 * @param {Node} ifNode - The node that is evaluate when the condition ends up `true`.
	 * @param {?Node} [elseNode=null] - The node that is evaluate when the condition ends up `false`.
	 */
	constructor( condNode, ifNode, elseNode = null ) {

		super();

		/**
		 * The node that defines the condition.
		 *
		 * @type {Node}
		 */
		this.condNode = condNode;

		/**
		 * The node that is evaluate when the condition ends up `true`.
		 *
		 * @type {Node}
		 */
		this.ifNode = ifNode;

		/**
		 * The node that is evaluate when the condition ends up `false`.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.elseNode = elseNode;

	}

	/**
	 * This method is overwritten since the node type is inferred from the if/else
	 * nodes.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( builder ) {

		const { ifNode, elseNode } = builder.getNodeProperties( this );

		if ( ifNode === undefined ) {

			// fallback setup

			builder.flowBuildStage( this, 'setup' );

			return this.getNodeType( builder );

		}

		const ifType = ifNode.getNodeType( builder );

		if ( elseNode !== null ) {

			const elseType = elseNode.getNodeType( builder );

			if ( builder.getTypeLength( elseType ) > builder.getTypeLength( ifType ) ) {

				return elseType;

			}

		}

		return ifType;

	}

	setup( builder ) {

		const condNode = this.condNode.cache();
		const ifNode = this.ifNode.cache();
		const elseNode = this.elseNode ? this.elseNode.cache() : null;

		//

		const currentNodeBlock = builder.context.nodeBlock;

		builder.getDataFromNode( ifNode ).parentNodeBlock = currentNodeBlock;
		if ( elseNode !== null ) builder.getDataFromNode( elseNode ).parentNodeBlock = currentNodeBlock;

		//

		const isUniformFlow = builder.context.uniformFlow;

		const properties = builder.getNodeProperties( this );
		properties.condNode = condNode;
		properties.ifNode = isUniformFlow ? ifNode : ifNode.context( { nodeBlock: ifNode } );
		properties.elseNode = elseNode ? ( isUniformFlow ? elseNode : elseNode.context( { nodeBlock: elseNode } ) ) : null;

	}

	generate( builder, output ) {

		const type = this.getNodeType( builder );

		const nodeData = builder.getDataFromNode( this );

		if ( nodeData.nodeProperty !== undefined ) {

			return nodeData.nodeProperty;

		}

		const { condNode, ifNode, elseNode } = builder.getNodeProperties( this );

		const functionNode = builder.currentFunctionNode;
		const needsOutput = output !== 'void';
		const nodeProperty = needsOutput ? property( type ).build( builder ) : '';

		nodeData.nodeProperty = nodeProperty;

		const nodeSnippet = condNode.build( builder, 'bool' );
		const isUniformFlow = builder.context.uniformFlow;

		if ( isUniformFlow && elseNode !== null ) {

			const ifSnippet = ifNode.build( builder, type );
			const elseSnippet = elseNode.build( builder, type );

			const mathSnippet = builder.getTernary( nodeSnippet, ifSnippet, elseSnippet );

			// TODO: If node property already exists return something else

			return builder.format( mathSnippet, type, output );

		}

		builder.addFlowCode( `\n${ builder.tab }if ( ${ nodeSnippet } ) {\n\n` ).addFlowTab();

		let ifSnippet = ifNode.build( builder, type );

		if ( ifSnippet ) {

			if ( needsOutput ) {

				ifSnippet = nodeProperty + ' = ' + ifSnippet + ';';

			} else {

				ifSnippet = 'return ' + ifSnippet + ';';

				if ( functionNode === null ) {

					console.warn( 'THREE.TSL: Return statement used in an inline \'Fn()\'. Define a layout struct to allow return values.' );

					ifSnippet = '// ' + ifSnippet;

				}

			}

		}

		builder.removeFlowTab().addFlowCode( builder.tab + '\t' + ifSnippet + '\n\n' + builder.tab + '}' );

		if ( elseNode !== null ) {

			builder.addFlowCode( ' else {\n\n' ).addFlowTab();

			let elseSnippet = elseNode.build( builder, type );

			if ( elseSnippet ) {

				if ( needsOutput ) {

					elseSnippet = nodeProperty + ' = ' + elseSnippet + ';';

				} else {

					elseSnippet = 'return ' + elseSnippet + ';';

					if ( functionNode === null ) {

						console.warn( 'THREE.TSL: Return statement used in an inline \'Fn()\'. Define a layout struct to allow return values.' );

						elseSnippet = '// ' + elseSnippet;

					}

				}

			}

			builder.removeFlowTab().addFlowCode( builder.tab + '\t' + elseSnippet + '\n\n' + builder.tab + '}\n\n' );

		} else {

			builder.addFlowCode( '\n\n' );

		}

		return builder.format( nodeProperty, type, output );

	}

}
```
</details>

#### Methods

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		const { ifNode, elseNode } = builder.getNodeProperties( this );

		if ( ifNode === undefined ) {

			// fallback setup

			builder.flowBuildStage( this, 'setup' );

			return this.getNodeType( builder );

		}

		const ifType = ifNode.getNodeType( builder );

		if ( elseNode !== null ) {

			const elseType = elseNode.getNodeType( builder );

			if ( builder.getTypeLength( elseType ) > builder.getTypeLength( ifType ) ) {

				return elseType;

			}

		}

		return ifType;

	}
```
</details>

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const condNode = this.condNode.cache();
		const ifNode = this.ifNode.cache();
		const elseNode = this.elseNode ? this.elseNode.cache() : null;

		//

		const currentNodeBlock = builder.context.nodeBlock;

		builder.getDataFromNode( ifNode ).parentNodeBlock = currentNodeBlock;
		if ( elseNode !== null ) builder.getDataFromNode( elseNode ).parentNodeBlock = currentNodeBlock;

		//

		const isUniformFlow = builder.context.uniformFlow;

		const properties = builder.getNodeProperties( this );
		properties.condNode = condNode;
		properties.ifNode = isUniformFlow ? ifNode : ifNode.context( { nodeBlock: ifNode } );
		properties.elseNode = elseNode ? ( isUniformFlow ? elseNode : elseNode.context( { nodeBlock: elseNode } ) ) : null;

	}
```
</details>

##### `generate(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		const type = this.getNodeType( builder );

		const nodeData = builder.getDataFromNode( this );

		if ( nodeData.nodeProperty !== undefined ) {

			return nodeData.nodeProperty;

		}

		const { condNode, ifNode, elseNode } = builder.getNodeProperties( this );

		const functionNode = builder.currentFunctionNode;
		const needsOutput = output !== 'void';
		const nodeProperty = needsOutput ? property( type ).build( builder ) : '';

		nodeData.nodeProperty = nodeProperty;

		const nodeSnippet = condNode.build( builder, 'bool' );
		const isUniformFlow = builder.context.uniformFlow;

		if ( isUniformFlow && elseNode !== null ) {

			const ifSnippet = ifNode.build( builder, type );
			const elseSnippet = elseNode.build( builder, type );

			const mathSnippet = builder.getTernary( nodeSnippet, ifSnippet, elseSnippet );

			// TODO: If node property already exists return something else

			return builder.format( mathSnippet, type, output );

		}

		builder.addFlowCode( `\n${ builder.tab }if ( ${ nodeSnippet } ) {\n\n` ).addFlowTab();

		let ifSnippet = ifNode.build( builder, type );

		if ( ifSnippet ) {

			if ( needsOutput ) {

				ifSnippet = nodeProperty + ' = ' + ifSnippet + ';';

			} else {

				ifSnippet = 'return ' + ifSnippet + ';';

				if ( functionNode === null ) {

					console.warn( 'THREE.TSL: Return statement used in an inline \'Fn()\'. Define a layout struct to allow return values.' );

					ifSnippet = '// ' + ifSnippet;

				}

			}

		}

		builder.removeFlowTab().addFlowCode( builder.tab + '\t' + ifSnippet + '\n\n' + builder.tab + '}' );

		if ( elseNode !== null ) {

			builder.addFlowCode( ' else {\n\n' ).addFlowTab();

			let elseSnippet = elseNode.build( builder, type );

			if ( elseSnippet ) {

				if ( needsOutput ) {

					elseSnippet = nodeProperty + ' = ' + elseSnippet + ';';

				} else {

					elseSnippet = 'return ' + elseSnippet + ';';

					if ( functionNode === null ) {

						console.warn( 'THREE.TSL: Return statement used in an inline \'Fn()\'. Define a layout struct to allow return values.' );

						elseSnippet = '// ' + elseSnippet;

					}

				}

			}

			builder.removeFlowTab().addFlowCode( builder.tab + '\t' + elseSnippet + '\n\n' + builder.tab + '}\n\n' );

		} else {

			builder.addFlowCode( '\n\n' );

		}

		return builder.format( nodeProperty, type, output );

	}
```
</details>


---