[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `JoinNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/utils/JoinNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `../core/TempNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `nodes` | `Node[]` | let/var | `this.nodes` | ✗ |
| `snippetValues` | `any[]` | let/var | `[]` | ✗ |
| `length` | `number` | let/var | `0` | ✗ |
| `inputSnippet` | `any` | let/var | `*not shown*` | ✗ |
| `snippet` | `string` | let/var | ``${ builder.getType( type ) }( ${ snippetValues.join( ', ' ) } )`` | ✗ |


---

## Functions

### `JoinNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node type must be inferred from the
	 * joined data length if not explicitly defined.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `builder.getVectorType`
- `builder.getTypeFromLength`
- `this.nodes.reduce`
- `builder.getTypeLength`
- `cur.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		if ( this.nodeType !== null ) {

			return builder.getVectorType( this.nodeType );

		}

		return builder.getTypeFromLength( this.nodes.reduce( ( count, cur ) => count + builder.getTypeLength( cur.getNodeType( builder ) ), 0 ) );

	}
```
</details>

### `JoinNode.generate(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `this.getNodeType`
- `builder.getTypeLength`
- `builder.getComponentType`
- `console.error`
- `input.getNodeType`
- `builder.getTypeFromLength`
- `input.build`
- `builder.format`
- `snippetValues.push`
- `builder.getType`
- `snippetValues.join`

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		const type = this.getNodeType( builder );
		const maxLength = builder.getTypeLength( type );

		const nodes = this.nodes;

		const primitiveType = builder.getComponentType( type );

		const snippetValues = [];

		let length = 0;

		for ( const input of nodes ) {

			if ( length >= maxLength ) {

				console.error( `THREE.TSL: Length of parameters exceeds maximum length of function '${ type }()' type.` );
				break;

			}

			let inputType = input.getNodeType( builder );
			let inputTypeLength = builder.getTypeLength( inputType );
			let inputSnippet;

			if ( length + inputTypeLength > maxLength ) {

				console.error( `THREE.TSL: Length of '${ type }()' data exceeds maximum length of output type.` );

				inputTypeLength = maxLength - length;
				inputType = builder.getTypeFromLength( inputTypeLength );

			}

			length += inputTypeLength;
			inputSnippet = input.build( builder, inputType );

			const inputPrimitiveType = builder.getComponentType( inputType );

			if ( inputPrimitiveType !== primitiveType ) {

				inputSnippet = builder.format( inputSnippet, inputPrimitiveType, primitiveType );

			}

			snippetValues.push( inputSnippet );

		}

		const snippet = `${ builder.getType( type ) }( ${ snippetValues.join( ', ' ) } )`;

		return builder.format( snippet, type, output );

	}
```
</details>


---

## Classes

### `JoinNode`

<details><summary>Class Code</summary>

```ts
class JoinNode extends TempNode {

	static get type() {

		return 'JoinNode';

	}

	/**
	 * Constructs a new join node.
	 *
	 * @param {Array<Node>} nodes - An array of nodes that should be joined.
	 * @param {?string} [nodeType=null] - The node type.
	 */
	constructor( nodes = [], nodeType = null ) {

		super( nodeType );

		/**
		 * An array of nodes that should be joined.
		 *
		 * @type {Array<Node>}
		 */
		this.nodes = nodes;

	}

	/**
	 * This method is overwritten since the node type must be inferred from the
	 * joined data length if not explicitly defined.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( builder ) {

		if ( this.nodeType !== null ) {

			return builder.getVectorType( this.nodeType );

		}

		return builder.getTypeFromLength( this.nodes.reduce( ( count, cur ) => count + builder.getTypeLength( cur.getNodeType( builder ) ), 0 ) );

	}

	generate( builder, output ) {

		const type = this.getNodeType( builder );
		const maxLength = builder.getTypeLength( type );

		const nodes = this.nodes;

		const primitiveType = builder.getComponentType( type );

		const snippetValues = [];

		let length = 0;

		for ( const input of nodes ) {

			if ( length >= maxLength ) {

				console.error( `THREE.TSL: Length of parameters exceeds maximum length of function '${ type }()' type.` );
				break;

			}

			let inputType = input.getNodeType( builder );
			let inputTypeLength = builder.getTypeLength( inputType );
			let inputSnippet;

			if ( length + inputTypeLength > maxLength ) {

				console.error( `THREE.TSL: Length of '${ type }()' data exceeds maximum length of output type.` );

				inputTypeLength = maxLength - length;
				inputType = builder.getTypeFromLength( inputTypeLength );

			}

			length += inputTypeLength;
			inputSnippet = input.build( builder, inputType );

			const inputPrimitiveType = builder.getComponentType( inputType );

			if ( inputPrimitiveType !== primitiveType ) {

				inputSnippet = builder.format( inputSnippet, inputPrimitiveType, primitiveType );

			}

			snippetValues.push( inputSnippet );

		}

		const snippet = `${ builder.getType( type ) }( ${ snippetValues.join( ', ' ) } )`;

		return builder.format( snippet, type, output );

	}

}
```
</details>

#### Methods

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		if ( this.nodeType !== null ) {

			return builder.getVectorType( this.nodeType );

		}

		return builder.getTypeFromLength( this.nodes.reduce( ( count, cur ) => count + builder.getTypeLength( cur.getNodeType( builder ) ), 0 ) );

	}
```
</details>

##### `generate(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		const type = this.getNodeType( builder );
		const maxLength = builder.getTypeLength( type );

		const nodes = this.nodes;

		const primitiveType = builder.getComponentType( type );

		const snippetValues = [];

		let length = 0;

		for ( const input of nodes ) {

			if ( length >= maxLength ) {

				console.error( `THREE.TSL: Length of parameters exceeds maximum length of function '${ type }()' type.` );
				break;

			}

			let inputType = input.getNodeType( builder );
			let inputTypeLength = builder.getTypeLength( inputType );
			let inputSnippet;

			if ( length + inputTypeLength > maxLength ) {

				console.error( `THREE.TSL: Length of '${ type }()' data exceeds maximum length of output type.` );

				inputTypeLength = maxLength - length;
				inputType = builder.getTypeFromLength( inputTypeLength );

			}

			length += inputTypeLength;
			inputSnippet = input.build( builder, inputType );

			const inputPrimitiveType = builder.getComponentType( inputType );

			if ( inputPrimitiveType !== primitiveType ) {

				inputSnippet = builder.format( inputSnippet, inputPrimitiveType, primitiveType );

			}

			snippetValues.push( inputSnippet );

		}

		const snippet = `${ builder.getType( type ) }( ${ snippetValues.join( ', ' ) } )`;

		return builder.format( snippet, type, output );

	}
```
</details>


---