[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SetNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/utils/SetNode.js`**

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
| `component` | `string` | let/var | `vectorComponents[ i ]` | ✗ |


---

## Functions

### `SetNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node type is inferred from {@link SetNode#sourceNode}.
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

### `SetNode.generate(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `this.getNodeType`
- `builder.getComponentType`
- `targetNode.getNodeType`
- `builder.getTypeFromLength`
- `targetNode.build`
- `sourceNode.build`
- `builder.getTypeLength`
- `snippetValues.push`
- `builder.getType`
- `snippetValues.join`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const { sourceNode, components, targetNode } = this;

		const sourceType = this.getNodeType( builder );

		const componentType = builder.getComponentType( targetNode.getNodeType( builder ) );
		const targetType = builder.getTypeFromLength( components.length, componentType );

		const targetSnippet = targetNode.build( builder, targetType );
		const sourceSnippet = sourceNode.build( builder, sourceType );

		const length = builder.getTypeLength( sourceType );
		const snippetValues = [];

		for ( let i = 0; i < length; i ++ ) {

			const component = vectorComponents[ i ];

			if ( component === components[ 0 ] ) {

				snippetValues.push( targetSnippet );

				i += components.length - 1;

			} else {

				snippetValues.push( sourceSnippet + '.' + component );

			}

		}

		return `${ builder.getType( sourceType ) }( ${ snippetValues.join( ', ' ) } )`;

	}
```
</details>


---

## Classes

### `SetNode`

<details><summary>Class Code</summary>

```ts
class SetNode extends TempNode {

	static get type() {

		return 'SetNode';

	}

	/**
	 * Constructs a new set node.
	 *
	 * @param {Node} sourceNode - The node that should be updated.
	 * @param {string} components - The components that should be updated.
	 * @param {Node} targetNode - The value node.
	 */
	constructor( sourceNode, components, targetNode ) {

		super();

		/**
		 * The node that should be updated.
		 *
		 * @type {Node}
		 */
		this.sourceNode = sourceNode;

		/**
		 * The components that should be updated.
		 *
		 * @type {string}
		 */
		this.components = components;

		/**
		 * The value node.
		 *
		 * @type {Node}
		 */
		this.targetNode = targetNode;

	}

	/**
	 * This method is overwritten since the node type is inferred from {@link SetNode#sourceNode}.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( builder ) {

		return this.sourceNode.getNodeType( builder );

	}

	generate( builder ) {

		const { sourceNode, components, targetNode } = this;

		const sourceType = this.getNodeType( builder );

		const componentType = builder.getComponentType( targetNode.getNodeType( builder ) );
		const targetType = builder.getTypeFromLength( components.length, componentType );

		const targetSnippet = targetNode.build( builder, targetType );
		const sourceSnippet = sourceNode.build( builder, sourceType );

		const length = builder.getTypeLength( sourceType );
		const snippetValues = [];

		for ( let i = 0; i < length; i ++ ) {

			const component = vectorComponents[ i ];

			if ( component === components[ 0 ] ) {

				snippetValues.push( targetSnippet );

				i += components.length - 1;

			} else {

				snippetValues.push( sourceSnippet + '.' + component );

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

		const { sourceNode, components, targetNode } = this;

		const sourceType = this.getNodeType( builder );

		const componentType = builder.getComponentType( targetNode.getNodeType( builder ) );
		const targetType = builder.getTypeFromLength( components.length, componentType );

		const targetSnippet = targetNode.build( builder, targetType );
		const sourceSnippet = sourceNode.build( builder, sourceType );

		const length = builder.getTypeLength( sourceType );
		const snippetValues = [];

		for ( let i = 0; i < length; i ++ ) {

			const component = vectorComponents[ i ];

			if ( component === components[ 0 ] ) {

				snippetValues.push( targetSnippet );

				i += components.length - 1;

			} else {

				snippetValues.push( sourceSnippet + '.' + component );

			}

		}

		return `${ builder.getType( sourceType ) }( ${ snippetValues.join( ', ' ) } )`;

	}
```
</details>


---