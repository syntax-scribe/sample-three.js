[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `AtomicFunctionNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 13 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/gpgpu/AtomicFunctionNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `expression` | `../code/ExpressionNode.js` |
| `nodeProxy` | `../tsl/TSLCore.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `parents` | `any` | let/var | `properties.parents` | ✗ |
| `method` | `string` | let/var | `this.method` | ✗ |
| `a` | `Node` | let/var | `this.pointerNode` | ✗ |
| `b` | `Node` | let/var | `this.valueNode` | ✗ |
| `params` | `any[]` | let/var | `[]` | ✗ |
| `methodSnippet` | `string` | let/var | ``${ builder.getMethod( method, type ) }( ${ params.join( ', ' ) } )`` | ✗ |
| `isVoid` | `boolean` | let/var | `parents ? ( parents.length === 1 && parents[ 0 ].isStackNode === true ) : false` | ✗ |


---

## Functions

### `AtomicFunctionNode.getInputType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation to return the type of
	 * the pointer node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.pointerNode.getNodeType`

<details><summary>Code</summary>

```typescript
getInputType( builder ) {

		return this.pointerNode.getNodeType( builder );

	}
```
</details>

### `AtomicFunctionNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * Overwritten since the node type is inferred from the input type.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.getInputType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return this.getInputType( builder );

	}
```
</details>

### `AtomicFunctionNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.getNodeProperties`
- `this.getNodeType`
- `this.getInputType`
- `params.push`
- `a.build`
- `b.build`
- `builder.getMethod`
- `params.join`
- `builder.addLineFlowCode`
- `expression( methodSnippet, type ).toConst`
- `properties.constNode.build`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const properties = builder.getNodeProperties( this );
		const parents = properties.parents;

		const method = this.method;

		const type = this.getNodeType( builder );
		const inputType = this.getInputType( builder );

		const a = this.pointerNode;
		const b = this.valueNode;

		const params = [];

		params.push( `&${ a.build( builder, inputType ) }` );

		if ( b !== null ) {

			params.push( b.build( builder, inputType ) );


		}

		const methodSnippet = `${ builder.getMethod( method, type ) }( ${ params.join( ', ' ) } )`;
		const isVoid = parents ? ( parents.length === 1 && parents[ 0 ].isStackNode === true ) : false;

		if ( isVoid ) {

			builder.addLineFlowCode( methodSnippet, this );

		} else {

			if ( properties.constNode === undefined ) {

				properties.constNode = expression( methodSnippet, type ).toConst();

			}

			return properties.constNode.build( builder );

		}

	}
```
</details>

### `atomicFunc(method: string, pointerNode: Node, valueNode: Node): AtomicFunctionNode`

**Parameters:**

- **`method`** `string`
- **`pointerNode`** `Node`
- **`valueNode`** `Node`

**Returns:** `AtomicFunctionNode`

**Calls:**

- `atomicNode( method, pointerNode, valueNode ).toStack`

<details><summary>Code</summary>

```typescript
( method, pointerNode, valueNode ) => {

	return atomicNode( method, pointerNode, valueNode ).toStack();

}
```
</details>

### `atomicLoad(pointerNode: Node): AtomicFunctionNode`

**Parameters:**

- **`pointerNode`** `Node`

**Returns:** `AtomicFunctionNode`

**Calls:**

- `atomicFunc`

<details><summary>Code</summary>

```typescript
( pointerNode ) => atomicFunc( AtomicFunctionNode.ATOMIC_LOAD, pointerNode, null )
```
</details>

### `atomicStore(pointerNode: Node, valueNode: Node): AtomicFunctionNode`

**Parameters:**

- **`pointerNode`** `Node`
- **`valueNode`** `Node`

**Returns:** `AtomicFunctionNode`

**Calls:**

- `atomicFunc`

<details><summary>Code</summary>

```typescript
( pointerNode, valueNode ) => atomicFunc( AtomicFunctionNode.ATOMIC_STORE, pointerNode, valueNode )
```
</details>

### `atomicAdd(pointerNode: Node, valueNode: Node): AtomicFunctionNode`

**Parameters:**

- **`pointerNode`** `Node`
- **`valueNode`** `Node`

**Returns:** `AtomicFunctionNode`

**Calls:**

- `atomicFunc`

<details><summary>Code</summary>

```typescript
( pointerNode, valueNode ) => atomicFunc( AtomicFunctionNode.ATOMIC_ADD, pointerNode, valueNode )
```
</details>

### `atomicSub(pointerNode: Node, valueNode: Node): AtomicFunctionNode`

**Parameters:**

- **`pointerNode`** `Node`
- **`valueNode`** `Node`

**Returns:** `AtomicFunctionNode`

**Calls:**

- `atomicFunc`

<details><summary>Code</summary>

```typescript
( pointerNode, valueNode ) => atomicFunc( AtomicFunctionNode.ATOMIC_SUB, pointerNode, valueNode )
```
</details>

### `atomicMax(pointerNode: Node, valueNode: Node): AtomicFunctionNode`

**Parameters:**

- **`pointerNode`** `Node`
- **`valueNode`** `Node`

**Returns:** `AtomicFunctionNode`

**Calls:**

- `atomicFunc`

<details><summary>Code</summary>

```typescript
( pointerNode, valueNode ) => atomicFunc( AtomicFunctionNode.ATOMIC_MAX, pointerNode, valueNode )
```
</details>

### `atomicMin(pointerNode: Node, valueNode: Node): AtomicFunctionNode`

**Parameters:**

- **`pointerNode`** `Node`
- **`valueNode`** `Node`

**Returns:** `AtomicFunctionNode`

**Calls:**

- `atomicFunc`

<details><summary>Code</summary>

```typescript
( pointerNode, valueNode ) => atomicFunc( AtomicFunctionNode.ATOMIC_MIN, pointerNode, valueNode )
```
</details>

### `atomicAnd(pointerNode: Node, valueNode: Node): AtomicFunctionNode`

**Parameters:**

- **`pointerNode`** `Node`
- **`valueNode`** `Node`

**Returns:** `AtomicFunctionNode`

**Calls:**

- `atomicFunc`

<details><summary>Code</summary>

```typescript
( pointerNode, valueNode ) => atomicFunc( AtomicFunctionNode.ATOMIC_AND, pointerNode, valueNode )
```
</details>

### `atomicOr(pointerNode: Node, valueNode: Node): AtomicFunctionNode`

**Parameters:**

- **`pointerNode`** `Node`
- **`valueNode`** `Node`

**Returns:** `AtomicFunctionNode`

**Calls:**

- `atomicFunc`

<details><summary>Code</summary>

```typescript
( pointerNode, valueNode ) => atomicFunc( AtomicFunctionNode.ATOMIC_OR, pointerNode, valueNode )
```
</details>

### `atomicXor(pointerNode: Node, valueNode: Node): AtomicFunctionNode`

**Parameters:**

- **`pointerNode`** `Node`
- **`valueNode`** `Node`

**Returns:** `AtomicFunctionNode`

**Calls:**

- `atomicFunc`

<details><summary>Code</summary>

```typescript
( pointerNode, valueNode ) => atomicFunc( AtomicFunctionNode.ATOMIC_XOR, pointerNode, valueNode )
```
</details>


---

## Classes

### `AtomicFunctionNode`

<details><summary>Class Code</summary>

```ts
class AtomicFunctionNode extends Node {

	static get type() {

		return 'AtomicFunctionNode';

	}

	/**
	 * Constructs a new atomic function node.
	 *
	 * @param {string} method - The signature of the atomic function to construct.
	 * @param {Node} pointerNode - An atomic variable or element of an atomic buffer.
	 * @param {Node} valueNode - The value that mutates the atomic variable.
	 */
	constructor( method, pointerNode, valueNode ) {

		super( 'uint' );

		/**
		 * The signature of the atomic function to construct.
		 *
		 * @type {string}
		 */
		this.method = method;

		/**
		 * An atomic variable or element of an atomic buffer.
		 *
		 * @type {Node}
		 */
		this.pointerNode = pointerNode;

		/**
		 * A value that modifies the atomic variable.
		 *
		 * @type {Node}
		 */
		this.valueNode = valueNode;

		/**
		 * Creates a list of the parents for this node for detecting if the node needs to return a value.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.parents = true;

	}

	/**
	 * Overwrites the default implementation to return the type of
	 * the pointer node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
	getInputType( builder ) {

		return this.pointerNode.getNodeType( builder );

	}

	/**
	 * Overwritten since the node type is inferred from the input type.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( builder ) {

		return this.getInputType( builder );

	}

	generate( builder ) {

		const properties = builder.getNodeProperties( this );
		const parents = properties.parents;

		const method = this.method;

		const type = this.getNodeType( builder );
		const inputType = this.getInputType( builder );

		const a = this.pointerNode;
		const b = this.valueNode;

		const params = [];

		params.push( `&${ a.build( builder, inputType ) }` );

		if ( b !== null ) {

			params.push( b.build( builder, inputType ) );


		}

		const methodSnippet = `${ builder.getMethod( method, type ) }( ${ params.join( ', ' ) } )`;
		const isVoid = parents ? ( parents.length === 1 && parents[ 0 ].isStackNode === true ) : false;

		if ( isVoid ) {

			builder.addLineFlowCode( methodSnippet, this );

		} else {

			if ( properties.constNode === undefined ) {

				properties.constNode = expression( methodSnippet, type ).toConst();

			}

			return properties.constNode.build( builder );

		}

	}

}
```
</details>

#### Methods

##### `getInputType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getInputType( builder ) {

		return this.pointerNode.getNodeType( builder );

	}
```
</details>

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return this.getInputType( builder );

	}
```
</details>

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const properties = builder.getNodeProperties( this );
		const parents = properties.parents;

		const method = this.method;

		const type = this.getNodeType( builder );
		const inputType = this.getInputType( builder );

		const a = this.pointerNode;
		const b = this.valueNode;

		const params = [];

		params.push( `&${ a.build( builder, inputType ) }` );

		if ( b !== null ) {

			params.push( b.build( builder, inputType ) );


		}

		const methodSnippet = `${ builder.getMethod( method, type ) }( ${ params.join( ', ' ) } )`;
		const isVoid = parents ? ( parents.length === 1 && parents[ 0 ].isStackNode === true ) : false;

		if ( isVoid ) {

			builder.addLineFlowCode( methodSnippet, this );

		} else {

			if ( properties.constNode === undefined ) {

				properties.constNode = expression( methodSnippet, type ).toConst();

			}

			return properties.constNode.build( builder );

		}

	}
```
</details>


---