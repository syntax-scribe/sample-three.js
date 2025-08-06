[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `FunctionOverloadingNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 10 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/utils/FunctionOverloadingNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `nodeProxy` | `../tsl/TSLCore.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `params` | `Node[]` | let/var | `this.parametersNodes` | ✗ |
| `candidateFnCall` | `ShaderCallNodeInternal` | let/var | `this._candidateFnCall` | ✗ |
| `candidateFn` | `any` | let/var | `null` | ✗ |
| `candidateScore` | `number` | let/var | `- 1` | ✗ |
| `shaderNode` | `any` | let/var | `functionNode.shaderNode` | ✗ |
| `layout` | `any` | let/var | `shaderNode.layout` | ✗ |
| `inputs` | `any` | let/var | `layout.inputs` | ✗ |
| `score` | `number` | let/var | `0` | ✗ |
| `param` | `Node` | let/var | `params[ i ]` | ✗ |
| `input` | `any` | let/var | `inputs[ i ]` | ✗ |


---

## Functions

### `FunctionOverloadingNode.getNodeType(): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node type is inferred from
	 * the function's return type.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getNodeType() {

		return this.functionNodes[ 0 ].shaderNode.layout.type;

	}
```
</details>

### `FunctionOverloadingNode.setup(builder: any): ShaderCallNodeInternal`

**Parameters:**

- **`builder`** `any`

**Returns:** `ShaderCallNodeInternal`

**Calls:**

- `param.getNodeType`
- `candidateFn`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const params = this.parametersNodes;

		let candidateFnCall = this._candidateFnCall;

		if ( candidateFnCall === null ) {

			let candidateFn = null;
			let candidateScore = - 1;

			for ( const functionNode of this.functionNodes ) {

				const shaderNode = functionNode.shaderNode;
				const layout = shaderNode.layout;

				if ( layout === null ) {

					throw new Error( 'FunctionOverloadingNode: FunctionNode must be a layout.' );

				}

				const inputs = layout.inputs;

				if ( params.length === inputs.length ) {

					let score = 0;

					for ( let i = 0; i < params.length; i ++ ) {

						const param = params[ i ];
						const input = inputs[ i ];

						if ( param.getNodeType( builder ) === input.type ) {

							score ++;

						} else {

							score = 0;

						}

					}

					if ( score > candidateScore ) {

						candidateFn = functionNode;
						candidateScore = score;

					}

				}

			}

			this._candidateFnCall = candidateFnCall = candidateFn( ...params );

		}

		return candidateFnCall;

	}
```
</details>

### `overloadingFn(functionNodes: Function[]): FunctionOverloadingNode`

**Parameters:**

- **`functionNodes`** `Function[]`

**Returns:** `FunctionOverloadingNode`

<details><summary>Code</summary>

```typescript
( functionNodes ) => ( ...params ) => overloadingBaseFn( functionNodes, ...params )
```
</details>


---

## Classes

### `FunctionOverloadingNode`

<details><summary>Class Code</summary>

```ts
class FunctionOverloadingNode extends Node {

	static get type() {

		return 'FunctionOverloadingNode';

	}

	/**
	 * Constructs a new function overloading node.
	 *
	 * @param {Array<Function>} functionNodes - Array of `Fn` function definitions.
	 * @param {...Node} parametersNodes - A list of parameter nodes.
	 */
	constructor( functionNodes = [], ...parametersNodes ) {

		super();

		/**
		 * Array of `Fn` function definitions.
		 *
		 * @type {Array<Function>}
		 */
		this.functionNodes = functionNodes;

		/**
		 * A list of parameter nodes.
		 *
		 * @type {Array<Node>}
		 */
		this.parametersNodes = parametersNodes;

		/**
		 * The selected overloaded function call.
		 *
		 * @private
		 * @type {ShaderCallNodeInternal}
		 */
		this._candidateFnCall = null;

		/**
		 * This node is marked as global.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.global = true;

	}

	/**
	 * This method is overwritten since the node type is inferred from
	 * the function's return type.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType() {

		return this.functionNodes[ 0 ].shaderNode.layout.type;

	}

	setup( builder ) {

		const params = this.parametersNodes;

		let candidateFnCall = this._candidateFnCall;

		if ( candidateFnCall === null ) {

			let candidateFn = null;
			let candidateScore = - 1;

			for ( const functionNode of this.functionNodes ) {

				const shaderNode = functionNode.shaderNode;
				const layout = shaderNode.layout;

				if ( layout === null ) {

					throw new Error( 'FunctionOverloadingNode: FunctionNode must be a layout.' );

				}

				const inputs = layout.inputs;

				if ( params.length === inputs.length ) {

					let score = 0;

					for ( let i = 0; i < params.length; i ++ ) {

						const param = params[ i ];
						const input = inputs[ i ];

						if ( param.getNodeType( builder ) === input.type ) {

							score ++;

						} else {

							score = 0;

						}

					}

					if ( score > candidateScore ) {

						candidateFn = functionNode;
						candidateScore = score;

					}

				}

			}

			this._candidateFnCall = candidateFnCall = candidateFn( ...params );

		}

		return candidateFnCall;

	}

}
```
</details>

#### Methods

##### `getNodeType(): string`

<details><summary>Code</summary>

```ts
getNodeType() {

		return this.functionNodes[ 0 ].shaderNode.layout.type;

	}
```
</details>

##### `setup(builder: any): ShaderCallNodeInternal`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const params = this.parametersNodes;

		let candidateFnCall = this._candidateFnCall;

		if ( candidateFnCall === null ) {

			let candidateFn = null;
			let candidateScore = - 1;

			for ( const functionNode of this.functionNodes ) {

				const shaderNode = functionNode.shaderNode;
				const layout = shaderNode.layout;

				if ( layout === null ) {

					throw new Error( 'FunctionOverloadingNode: FunctionNode must be a layout.' );

				}

				const inputs = layout.inputs;

				if ( params.length === inputs.length ) {

					let score = 0;

					for ( let i = 0; i < params.length; i ++ ) {

						const param = params[ i ];
						const input = inputs[ i ];

						if ( param.getNodeType( builder ) === input.type ) {

							score ++;

						} else {

							score = 0;

						}

					}

					if ( score > candidateScore ) {

						candidateFn = functionNode;
						candidateScore = score;

					}

				}

			}

			this._candidateFnCall = candidateFnCall = candidateFn( ...params );

		}

		return candidateFnCall;

	}
```
</details>


---