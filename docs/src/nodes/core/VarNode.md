[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `VarNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 11 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/VarNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `./Node.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `getCurrentStack` | `../tsl/TSLCore.js` |
| `nodeProxy` | `../tsl/TSLCore.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `builder` | `any` | let/var | `params[ 0 ]` | ✗ |
| `isWebGPUBackend` | `boolean` | let/var | `renderer.backend.isWebGPUBackend === true` | ✗ |
| `isDeterministic` | `boolean` | let/var | `false` | ✗ |
| `shouldTreatAsReadOnly` | `boolean` | let/var | `false` | ✗ |
| `declarationPrefix` | `any` | let/var | `propertyName` | ✗ |


---

## Functions

### `VarNode.setIntent(value: boolean): VarNode`

**JSDoc:**
```typescript
/**
	 * Sets the intent flag for this node.
	 *
	 * This flag is used to indicate that this node is used for intent
	 * and should not be built directly. Instead, it is used to indicate that
	 * the node should be treated as a variable intent.
	 *
	 * It's useful for assigning variables without needing creating a new variable node.
	 *
	 * @param {boolean} value - The value to set for the intent flag.
	 * @returns {VarNode} This node.
	 */
```

**Parameters:**

- **`value`** `boolean`

**Returns:** `VarNode`

<details><summary>Code</summary>

```typescript
setIntent( value ) {

		this.intent = value;

		return this;

	}
```
</details>

### `VarNode.getIntent(): boolean`

**JSDoc:**
```typescript
/**
	 * Returns the intent flag of this node.
	 *
	 * @return {boolean} The intent flag.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
getIntent() {

		return this.intent;

	}
```
</details>

### `VarNode.getMemberType(builder: any, name: any): string`

**Parameters:**

- **`builder`** `any`
- **`name`** `any`

**Returns:** `string`

**Calls:**

- `this.node.getMemberType`

<details><summary>Code</summary>

```typescript
getMemberType( builder, name ) {

		return this.node.getMemberType( builder, name );

	}
```
</details>

### `VarNode.getElementType(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `this.node.getElementType`

<details><summary>Code</summary>

```typescript
getElementType( builder ) {

		return this.node.getElementType( builder );

	}
```
</details>

### `VarNode.getNodeType(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `this.node.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return this.node.getNodeType( builder );

	}
```
</details>

### `VarNode.getArrayCount(builder: any): number`

**Parameters:**

- **`builder`** `any`

**Returns:** `number`

**Calls:**

- `this.node.getArrayCount`

<details><summary>Code</summary>

```typescript
getArrayCount( builder ) {

		return this.node.getArrayCount( builder );

	}
```
</details>

### `VarNode.build(params: any[]): string | Node`

**Parameters:**

- **`params`** `any[]`

**Returns:** `string | Node`

**Calls:**

- `builder.getNodeProperties`
- `this.node.build`
- `super.build`

<details><summary>Code</summary>

```typescript
build( ...params ) {

		if ( this.intent === true ) {

			const builder = params[ 0 ];
			const properties = builder.getNodeProperties( this );

			if ( properties.assign !== true ) {

				return this.node.build( ...params );

			}

		}

		return super.build( ...params );

	}
```
</details>

### `VarNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.isDeterministic`
- `builder.getVectorType`
- `this.getNodeType`
- `node.build`
- `builder.getVarFromNode`
- `builder.getPropertyName`
- `node.getArrayCount`
- `builder.getVar`
- `builder.addLineFlowCode`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const { node, name, readOnly } = this;
		const { renderer } = builder;

		const isWebGPUBackend = renderer.backend.isWebGPUBackend === true;

		let isDeterministic = false;
		let shouldTreatAsReadOnly = false;

		if ( readOnly ) {

			isDeterministic = builder.isDeterministic( node );

			shouldTreatAsReadOnly = isWebGPUBackend ? readOnly : isDeterministic;

		}

		const vectorType = builder.getVectorType( this.getNodeType( builder ) );
		const snippet = node.build( builder, vectorType );

		const nodeVar = builder.getVarFromNode( this, name, vectorType, undefined, shouldTreatAsReadOnly );

		const propertyName = builder.getPropertyName( nodeVar );

		let declarationPrefix = propertyName;

		if ( shouldTreatAsReadOnly ) {

			if ( isWebGPUBackend ) {

				declarationPrefix = isDeterministic
					? `const ${ propertyName }`
					: `let ${ propertyName }`;

			} else {

				const count = node.getArrayCount( builder );

				declarationPrefix = `const ${ builder.getVar( nodeVar.type, propertyName, count ) }`;

			}

		}

		builder.addLineFlowCode( `${ declarationPrefix } = ${ snippet }`, this );

		return propertyName;

	}
```
</details>

### `Var(node: Node, name: string): VarNode`

**Parameters:**

- **`node`** `Node`
- **`name`** `string`

**Returns:** `VarNode`

**Calls:**

- `createVar( node, name ).toStack`

<details><summary>Code</summary>

```typescript
( node, name = null ) => createVar( node, name ).toStack()
```
</details>

### `Const(node: Node, name: string): VarNode`

**Parameters:**

- **`node`** `Node`
- **`name`** `string`

**Returns:** `VarNode`

**Calls:**

- `createVar( node, name, true ).toStack`

<details><summary>Code</summary>

```typescript
( node, name = null ) => createVar( node, name, true ).toStack()
```
</details>

### `VarIntent(node: Node): VarNode`

**Parameters:**

- **`node`** `Node`

**Returns:** `VarNode`

**Calls:**

- `getCurrentStack (from ../tsl/TSLCore.js)`
- `createVar( node ).setIntent( true ).toStack`

<details><summary>Code</summary>

```typescript
( node ) => {

	if ( getCurrentStack() === null ) {

		return node;

	}

	return createVar( node ).setIntent( true ).toStack();

}
```
</details>


---

## Classes

### `VarNode`

<details><summary>Class Code</summary>

```ts
class VarNode extends Node {

	static get type() {

		return 'VarNode';

	}

	/**
	 * Constructs a new variable node.
	 *
	 * @param {Node} node - The node for which a variable should be created.
	 * @param {?string} [name=null] - The name of the variable in the shader.
	 * @param {boolean} [readOnly=false] - The read-only flag.
	 */
	constructor( node, name = null, readOnly = false ) {

		super();

		/**
		 * The node for which a variable should be created.
		 *
		 * @type {Node}
		 */
		this.node = node;

		/**
		 * The name of the variable in the shader. If no name is defined,
		 * the node system auto-generates one.
		 *
		 * @type {?string}
		 * @default null
		 */
		this.name = name;

		/**
		 * `VarNode` sets this property to `true` by default.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.global = true;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isVarNode = true;

		/**
		 *
		 * The read-only flag.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.readOnly = readOnly;

		/**
		 *
		 * Add this flag to the node system to indicate that this node require parents.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.parents = true;

		/**
		 * This flag is used to indicate that this node is used for intent.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.intent = false;

	}

	/**
	 * Sets the intent flag for this node.
	 *
	 * This flag is used to indicate that this node is used for intent
	 * and should not be built directly. Instead, it is used to indicate that
	 * the node should be treated as a variable intent.
	 *
	 * It's useful for assigning variables without needing creating a new variable node.
	 *
	 * @param {boolean} value - The value to set for the intent flag.
	 * @returns {VarNode} This node.
	 */
	setIntent( value ) {

		this.intent = value;

		return this;

	}

	/**
	 * Returns the intent flag of this node.
	 *
	 * @return {boolean} The intent flag.
	 */
	getIntent() {

		return this.intent;

	}

	getMemberType( builder, name ) {

		return this.node.getMemberType( builder, name );

	}

	getElementType( builder ) {

		return this.node.getElementType( builder );

	}

	getNodeType( builder ) {

		return this.node.getNodeType( builder );

	}

	getArrayCount( builder ) {

		return this.node.getArrayCount( builder );

	}

	build( ...params ) {

		if ( this.intent === true ) {

			const builder = params[ 0 ];
			const properties = builder.getNodeProperties( this );

			if ( properties.assign !== true ) {

				return this.node.build( ...params );

			}

		}

		return super.build( ...params );

	}

	generate( builder ) {

		const { node, name, readOnly } = this;
		const { renderer } = builder;

		const isWebGPUBackend = renderer.backend.isWebGPUBackend === true;

		let isDeterministic = false;
		let shouldTreatAsReadOnly = false;

		if ( readOnly ) {

			isDeterministic = builder.isDeterministic( node );

			shouldTreatAsReadOnly = isWebGPUBackend ? readOnly : isDeterministic;

		}

		const vectorType = builder.getVectorType( this.getNodeType( builder ) );
		const snippet = node.build( builder, vectorType );

		const nodeVar = builder.getVarFromNode( this, name, vectorType, undefined, shouldTreatAsReadOnly );

		const propertyName = builder.getPropertyName( nodeVar );

		let declarationPrefix = propertyName;

		if ( shouldTreatAsReadOnly ) {

			if ( isWebGPUBackend ) {

				declarationPrefix = isDeterministic
					? `const ${ propertyName }`
					: `let ${ propertyName }`;

			} else {

				const count = node.getArrayCount( builder );

				declarationPrefix = `const ${ builder.getVar( nodeVar.type, propertyName, count ) }`;

			}

		}

		builder.addLineFlowCode( `${ declarationPrefix } = ${ snippet }`, this );

		return propertyName;

	}

}
```
</details>

#### Methods

##### `setIntent(value: boolean): VarNode`

<details><summary>Code</summary>

```ts
setIntent( value ) {

		this.intent = value;

		return this;

	}
```
</details>

##### `getIntent(): boolean`

<details><summary>Code</summary>

```ts
getIntent() {

		return this.intent;

	}
```
</details>

##### `getMemberType(builder: any, name: any): string`

<details><summary>Code</summary>

```ts
getMemberType( builder, name ) {

		return this.node.getMemberType( builder, name );

	}
```
</details>

##### `getElementType(builder: any): string`

<details><summary>Code</summary>

```ts
getElementType( builder ) {

		return this.node.getElementType( builder );

	}
```
</details>

##### `getNodeType(builder: any): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return this.node.getNodeType( builder );

	}
```
</details>

##### `getArrayCount(builder: any): number`

<details><summary>Code</summary>

```ts
getArrayCount( builder ) {

		return this.node.getArrayCount( builder );

	}
```
</details>

##### `build(params: any[]): string | Node`

<details><summary>Code</summary>

```ts
build( ...params ) {

		if ( this.intent === true ) {

			const builder = params[ 0 ];
			const properties = builder.getNodeProperties( this );

			if ( properties.assign !== true ) {

				return this.node.build( ...params );

			}

		}

		return super.build( ...params );

	}
```
</details>

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const { node, name, readOnly } = this;
		const { renderer } = builder;

		const isWebGPUBackend = renderer.backend.isWebGPUBackend === true;

		let isDeterministic = false;
		let shouldTreatAsReadOnly = false;

		if ( readOnly ) {

			isDeterministic = builder.isDeterministic( node );

			shouldTreatAsReadOnly = isWebGPUBackend ? readOnly : isDeterministic;

		}

		const vectorType = builder.getVectorType( this.getNodeType( builder ) );
		const snippet = node.build( builder, vectorType );

		const nodeVar = builder.getVarFromNode( this, name, vectorType, undefined, shouldTreatAsReadOnly );

		const propertyName = builder.getPropertyName( nodeVar );

		let declarationPrefix = propertyName;

		if ( shouldTreatAsReadOnly ) {

			if ( isWebGPUBackend ) {

				declarationPrefix = isDeterministic
					? `const ${ propertyName }`
					: `let ${ propertyName }`;

			} else {

				const count = node.getArrayCount( builder );

				declarationPrefix = `const ${ builder.getVar( nodeVar.type, propertyName, count ) }`;

			}

		}

		builder.addLineFlowCode( `${ declarationPrefix } = ${ snippet }`, this );

		return propertyName;

	}
```
</details>


---