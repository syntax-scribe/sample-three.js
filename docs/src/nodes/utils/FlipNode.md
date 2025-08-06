[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `FlipNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/utils/FlipNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `../core/TempNode.js` |
| `vectorComponents` | `../core/constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `snippetValues` | `any[]` | let/var | `[]` | ✗ |
| `componentIndex` | `number` | let/var | `0` | ✗ |
| `component` | `string` | let/var | `vectorComponents[ i ]` | ✗ |


---

## Functions

### `FlipNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node type is inferred from the source node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.sourceNode.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return this.sourceNode.getNodeType( builder );

	}
```
</details>

### `FlipNode.generate(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `this.getNodeType`
- `sourceNode.build`
- `builder.getVarFromNode`
- `builder.getPropertyName`
- `builder.addLineFlowCode`
- `builder.getTypeLength`
- `snippetValues.push`
- `builder.getType`
- `snippetValues.join`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const { components, sourceNode } = this;

		const sourceType = this.getNodeType( builder );
		const sourceSnippet = sourceNode.build( builder );

		const sourceCache = builder.getVarFromNode( this );
		const sourceProperty = builder.getPropertyName( sourceCache );

		builder.addLineFlowCode( sourceProperty + ' = ' + sourceSnippet, this );

		const length = builder.getTypeLength( sourceType );
		const snippetValues = [];

		let componentIndex = 0;

		for ( let i = 0; i < length; i ++ ) {

			const component = vectorComponents[ i ];

			if ( component === components[ componentIndex ] ) {

				snippetValues.push( '1.0 - ' + ( sourceProperty + '.' + component ) );

				componentIndex ++;

			} else {

				snippetValues.push( sourceProperty + '.' + component );

			}

		}

		return `${ builder.getType( sourceType ) }( ${ snippetValues.join( ', ' ) } )`;

	}
```
</details>


---

## Classes

### `FlipNode`

<details><summary>Class Code</summary>

```ts
class FlipNode extends TempNode {

	static get type() {

		return 'FlipNode';

	}

	/**
	 * Constructs a new flip node.
	 *
	 * @param {Node} sourceNode - The node which component(s) should be flipped.
	 * @param {string} components - The components that should be flipped e.g. `'x'` or `'xy'`.
	 */
	constructor( sourceNode, components ) {

		super();

		/**
		 * The node which component(s) should be flipped.
		 *
		 * @type {Node}
		 */
		this.sourceNode = sourceNode;

		/**
		 * The components that should be flipped e.g. `'x'` or `'xy'`.
		 *
		 * @type {string}
		 */
		this.components = components;

	}

	/**
	 * This method is overwritten since the node type is inferred from the source node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( builder ) {

		return this.sourceNode.getNodeType( builder );

	}

	generate( builder ) {

		const { components, sourceNode } = this;

		const sourceType = this.getNodeType( builder );
		const sourceSnippet = sourceNode.build( builder );

		const sourceCache = builder.getVarFromNode( this );
		const sourceProperty = builder.getPropertyName( sourceCache );

		builder.addLineFlowCode( sourceProperty + ' = ' + sourceSnippet, this );

		const length = builder.getTypeLength( sourceType );
		const snippetValues = [];

		let componentIndex = 0;

		for ( let i = 0; i < length; i ++ ) {

			const component = vectorComponents[ i ];

			if ( component === components[ componentIndex ] ) {

				snippetValues.push( '1.0 - ' + ( sourceProperty + '.' + component ) );

				componentIndex ++;

			} else {

				snippetValues.push( sourceProperty + '.' + component );

			}

		}

		return `${ builder.getType( sourceType ) }( ${ snippetValues.join( ', ' ) } )`;

	}

}
```
</details>

#### Methods

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return this.sourceNode.getNodeType( builder );

	}
```
</details>

##### `generate(builder: any): string`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const { components, sourceNode } = this;

		const sourceType = this.getNodeType( builder );
		const sourceSnippet = sourceNode.build( builder );

		const sourceCache = builder.getVarFromNode( this );
		const sourceProperty = builder.getPropertyName( sourceCache );

		builder.addLineFlowCode( sourceProperty + ' = ' + sourceSnippet, this );

		const length = builder.getTypeLength( sourceType );
		const snippetValues = [];

		let componentIndex = 0;

		for ( let i = 0; i < length; i ++ ) {

			const component = vectorComponents[ i ];

			if ( component === components[ componentIndex ] ) {

				snippetValues.push( '1.0 - ' + ( sourceProperty + '.' + component ) );

				componentIndex ++;

			} else {

				snippetValues.push( sourceProperty + '.' + component );

			}

		}

		return `${ builder.getType( sourceType ) }( ${ snippetValues.join( ', ' ) } )`;

	}
```
</details>


---