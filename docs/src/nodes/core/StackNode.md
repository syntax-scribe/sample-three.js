[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `StackNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 11 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 12 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/StackNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `./Node.js` |
| `select` | `../math/ConditionalNode.js` |
| `ShaderNode` | `../tsl/TSLBase.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `getCurrentStack` | `../tsl/TSLBase.js` |
| `setCurrentStack` | `../tsl/TSLBase.js` |
| `nodeObject` | `../tsl/TSLBase.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `methodNode` | `any` | let/var | `new ShaderNode( method )` | ✗ |
| `methodNode` | `any` | let/var | `new ShaderNode( method )` | ✗ |
| `caseNodes` | `any[]` | let/var | `[]` | ✗ |
| `method` | `any` | let/var | `params[ params.length - 1 ]` | ✗ |
| `methodNode` | `any` | let/var | `new ShaderNode( method )` | ✗ |
| `caseNode` | `any` | let/var | `caseNodes[ 0 ]` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `previousBuildStack` | `any` | let/var | `builder.currentStack` | ✗ |
| `buildStage` | `any` | let/var | `builder.buildStage` | ✗ |
| `stages` | `any` | let/var | `builder.getDataFromNode( node, 'any' ).stages` | ✗ |
| `parents` | `any` | let/var | `stages && stages[ builder.shaderStage ]` | ✗ |
| `result` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `StackNode.getNodeType(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `this.outputNode.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return this.hasOutput ? this.outputNode.getNodeType( builder ) : 'void';

	}
```
</details>

### `StackNode.getMemberType(builder: any, name: any): string`

**Parameters:**

- **`builder`** `any`
- **`name`** `any`

**Returns:** `string`

**Calls:**

- `this.outputNode.getMemberType`

<details><summary>Code</summary>

```typescript
getMemberType( builder, name ) {

		return this.hasOutput ? this.outputNode.getMemberType( builder, name ) : 'void';

	}
```
</details>

### `StackNode.add(node: Node): StackNode`

**JSDoc:**
```typescript
/**
	 * Adds a node to this stack.
	 *
	 * @param {Node} node - The node to add.
	 * @return {StackNode} A reference to this stack node.
	 */
```

**Parameters:**

- **`node`** `Node`

**Returns:** `StackNode`

**Calls:**

- `console.error`
- `this.nodes.push`

<details><summary>Code</summary>

```typescript
add( node ) {

		if ( node.isNode !== true ) {

			console.error( 'THREE.TSL: Invalid node added to stack.' );
			return this;

		}

		this.nodes.push( node );

		return this;

	}
```
</details>

### `StackNode.If(boolNode: Node, method: Function): StackNode`

**JSDoc:**
```typescript
/**
	 * Represent an `if` statement in TSL.
	 *
	 * @param {Node} boolNode - Represents the condition.
	 * @param {Function} method - TSL code which is executed if the condition evaluates to `true`.
	 * @return {StackNode} A reference to this stack node.
	 */
```

**Parameters:**

- **`boolNode`** `Node`
- **`method`** `Function`

**Returns:** `StackNode`

**Calls:**

- `select (from ../math/ConditionalNode.js)`
- `this.add`

<details><summary>Code</summary>

```typescript
If( boolNode, method ) {

		const methodNode = new ShaderNode( method );
		this._currentCond = select( boolNode, methodNode );

		return this.add( this._currentCond );

	}
```
</details>

### `StackNode.ElseIf(boolNode: Node, method: Function): StackNode`

**JSDoc:**
```typescript
/**
	 * Represent an `elseif` statement in TSL.
	 *
	 * @param {Node} boolNode - Represents the condition.
	 * @param {Function} method - TSL code which is executed if the condition evaluates to `true`.
	 * @return {StackNode} A reference to this stack node.
	 */
```

**Parameters:**

- **`boolNode`** `Node`
- **`method`** `Function`

**Returns:** `StackNode`

**Calls:**

- `select (from ../math/ConditionalNode.js)`

<details><summary>Code</summary>

```typescript
ElseIf( boolNode, method ) {

		const methodNode = new ShaderNode( method );
		const ifNode = select( boolNode, methodNode );

		this._currentCond.elseNode = ifNode;
		this._currentCond = ifNode;

		return this;

	}
```
</details>

### `StackNode.Else(method: Function): StackNode`

**JSDoc:**
```typescript
/**
	 * Represent an `else` statement in TSL.
	 *
	 * @param {Function} method - TSL code which is executed in the `else` case.
	 * @return {StackNode} A reference to this stack node.
	 */
```

**Parameters:**

- **`method`** `Function`

**Returns:** `StackNode`

<details><summary>Code</summary>

```typescript
Else( method ) {

		this._currentCond.elseNode = new ShaderNode( method );

		return this;

	}
```
</details>

### `StackNode.Switch(expression: any): StackNode`

**JSDoc:**
```typescript
/**
	 * Represents a `switch` statement in TSL.
	 *
	 * @param {any} expression - Represents the expression.
	 * @param {Function} method - TSL code which is executed if the condition evaluates to `true`.
	 * @return {StackNode} A reference to this stack node.
	 */
```

**Parameters:**

- **`expression`** `any`

**Returns:** `StackNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
Switch( expression ) {

		this._expressionNode = nodeObject( expression );

		return this;

	}
```
</details>

### `StackNode.Case(params: any[]): StackNode`

**JSDoc:**
```typescript
/**
	 * Represents a `case` statement in TSL. The TSL version accepts an arbitrary numbers of values.
	 * The last parameter must be the callback method that should be executed in the `true` case.
	 *
	 * @param {...any} params - The values of the `Case()` statement as well as the callback method.
	 * @return {StackNode} A reference to this stack node.
	 */
```

**Parameters:**

- **`params`** `any[]`

**Returns:** `StackNode`

**Calls:**

- `caseNodes.push`
- `this._expressionNode.equal`
- `nodeObject (from ../tsl/TSLBase.js)`
- `console.error`
- `caseNode.or`
- `select (from ../math/ConditionalNode.js)`
- `this.add`

**Internal Comments:**
```
// extract case nodes from the parameter list
// extract method (x2)
// chain multiple cases when using Case( 1, 2, 3, () => {} ) (x2)
// build condition (x2)
```

<details><summary>Code</summary>

```typescript
Case( ...params ) {

		const caseNodes = [];

		// extract case nodes from the parameter list

		if ( params.length >= 2 ) {

			for ( let i = 0; i < params.length - 1; i ++ ) {

				caseNodes.push( this._expressionNode.equal( nodeObject( params[ i ] ) ) );

			}

		} else {

			console.error( 'THREE.TSL: Invalid parameter length. Case() requires at least two parameters.' );

		}

		// extract method

		const method = params[ params.length - 1 ];
		const methodNode = new ShaderNode( method );

		// chain multiple cases when using Case( 1, 2, 3, () => {} )

		let caseNode = caseNodes[ 0 ];

		for ( let i = 1; i < caseNodes.length; i ++ ) {

			caseNode = caseNode.or( caseNodes[ i ] );

		}

		// build condition

		const condNode = select( caseNode, methodNode );

		if ( this._currentCond === null ) {

			this._currentCond = condNode;

			return this.add( this._currentCond );

		} else {

			this._currentCond.elseNode = condNode;
			this._currentCond = condNode;

			return this;

		}

	}
```
</details>

### `StackNode.Default(method: Function): StackNode`

**JSDoc:**
```typescript
/**
	 * Represents the default code block of a Switch/Case statement.
	 *
	 * @param {Function} method - TSL code which is executed in the `else` case.
	 * @return {StackNode} A reference to this stack node.
	 */
```

**Parameters:**

- **`method`** `Function`

**Returns:** `StackNode`

**Calls:**

- `this.Else`

<details><summary>Code</summary>

```typescript
Default( method ) {

		this.Else( method );

		return this;

	}
```
</details>

### `StackNode.setup(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.getNodeProperties`
- `this.getChildren`

**Internal Comments:**
```
// return a outputNode if exists or null
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const nodeProperties = builder.getNodeProperties( this );

		let index = 0;

		for ( const childNode of this.getChildren() ) {

			if ( childNode.isVarNode && childNode.intent === true ) {

				const properties = builder.getNodeProperties( childNode );

				if ( properties.assign !== true ) {

					continue;

				}

			}

			nodeProperties[ 'node' + index ++ ] = childNode;

		}

		// return a outputNode if exists or null

		return nodeProperties.outputNode || null;

	}
```
</details>

### `StackNode.build(builder: any, params: any[]): string | Node`

**Parameters:**

- **`builder`** `any`
- **`params`** `any[]`

**Returns:** `string | Node`

**Calls:**

- `getCurrentStack (from ../tsl/TSLBase.js)`
- `setCurrentStack (from ../tsl/TSLBase.js)`
- `builder.getNodeProperties`
- `node.build`
- `builder.getDataFromNode`
- `this.outputNode.build`
- `super.build`

**Internal Comments:**
```
// (x2)
```

<details><summary>Code</summary>

```typescript
build( builder, ...params ) {

		const previousBuildStack = builder.currentStack;
		const previousStack = getCurrentStack();

		setCurrentStack( this );

		builder.currentStack = this;

		const buildStage = builder.buildStage;

		for ( const node of this.nodes ) {

			if ( node.isVarNode && node.intent === true ) {

				const properties = builder.getNodeProperties( node );

				if ( properties.assign !== true ) {

					continue;

				}

			}

			if ( buildStage === 'setup' ) {

				node.build( builder );

			} else if ( buildStage === 'analyze' ) {

				node.build( builder, this );

			} else if ( buildStage === 'generate' ) {

				const stages = builder.getDataFromNode( node, 'any' ).stages;
				const parents = stages && stages[ builder.shaderStage ];

				if ( node.isVarNode && parents && parents.length === 1 && parents[ 0 ] && parents[ 0 ].isStackNode ) {

					continue; // skip var nodes that are only used in .toVarying()

				}

				node.build( builder, 'void' );

			}

		}

		//

		let result;

		if ( this.hasOutput ) {

			result = this.outputNode.build( builder, ...params );

		} else {

			result = super.build( builder, ...params );

		}

		setCurrentStack( previousStack );

		builder.currentStack = previousBuildStack;

		return result;

	}
```
</details>


---

## Classes

### `StackNode`

<details><summary>Class Code</summary>

```ts
class StackNode extends Node {

	static get type() {

		return 'StackNode';

	}

	/**
	 * Constructs a new stack node.
	 *
	 * @param {?StackNode} [parent=null] - The parent stack node.
	 */
	constructor( parent = null ) {

		super();

		/**
		 * List of nodes.
		 *
		 * @type {Array<Node>}
		 */
		this.nodes = [];

		/**
		 * The output node.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.outputNode = null;

		/**
		 * The parent stack node.
		 *
		 * @type {?StackNode}
		 * @default null
		 */
		this.parent = parent;

		/**
		 * The current conditional node.
		 *
		 * @private
		 * @type {ConditionalNode}
		 * @default null
		 */
		this._currentCond = null;

		/**
		 * The expression node. Only
		 * relevant for Switch/Case.
		 *
		 * @private
		 * @type {Node}
		 * @default null
		 */
		this._expressionNode = null;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isStackNode = true;

	}

	getNodeType( builder ) {

		return this.hasOutput ? this.outputNode.getNodeType( builder ) : 'void';

	}

	getMemberType( builder, name ) {

		return this.hasOutput ? this.outputNode.getMemberType( builder, name ) : 'void';

	}

	/**
	 * Adds a node to this stack.
	 *
	 * @param {Node} node - The node to add.
	 * @return {StackNode} A reference to this stack node.
	 */
	add( node ) {

		if ( node.isNode !== true ) {

			console.error( 'THREE.TSL: Invalid node added to stack.' );
			return this;

		}

		this.nodes.push( node );

		return this;

	}

	/**
	 * Represent an `if` statement in TSL.
	 *
	 * @param {Node} boolNode - Represents the condition.
	 * @param {Function} method - TSL code which is executed if the condition evaluates to `true`.
	 * @return {StackNode} A reference to this stack node.
	 */
	If( boolNode, method ) {

		const methodNode = new ShaderNode( method );
		this._currentCond = select( boolNode, methodNode );

		return this.add( this._currentCond );

	}

	/**
	 * Represent an `elseif` statement in TSL.
	 *
	 * @param {Node} boolNode - Represents the condition.
	 * @param {Function} method - TSL code which is executed if the condition evaluates to `true`.
	 * @return {StackNode} A reference to this stack node.
	 */
	ElseIf( boolNode, method ) {

		const methodNode = new ShaderNode( method );
		const ifNode = select( boolNode, methodNode );

		this._currentCond.elseNode = ifNode;
		this._currentCond = ifNode;

		return this;

	}

	/**
	 * Represent an `else` statement in TSL.
	 *
	 * @param {Function} method - TSL code which is executed in the `else` case.
	 * @return {StackNode} A reference to this stack node.
	 */
	Else( method ) {

		this._currentCond.elseNode = new ShaderNode( method );

		return this;

	}

	/**
	 * Represents a `switch` statement in TSL.
	 *
	 * @param {any} expression - Represents the expression.
	 * @param {Function} method - TSL code which is executed if the condition evaluates to `true`.
	 * @return {StackNode} A reference to this stack node.
	 */
	Switch( expression ) {

		this._expressionNode = nodeObject( expression );

		return this;

	}

	/**
	 * Represents a `case` statement in TSL. The TSL version accepts an arbitrary numbers of values.
	 * The last parameter must be the callback method that should be executed in the `true` case.
	 *
	 * @param {...any} params - The values of the `Case()` statement as well as the callback method.
	 * @return {StackNode} A reference to this stack node.
	 */
	Case( ...params ) {

		const caseNodes = [];

		// extract case nodes from the parameter list

		if ( params.length >= 2 ) {

			for ( let i = 0; i < params.length - 1; i ++ ) {

				caseNodes.push( this._expressionNode.equal( nodeObject( params[ i ] ) ) );

			}

		} else {

			console.error( 'THREE.TSL: Invalid parameter length. Case() requires at least two parameters.' );

		}

		// extract method

		const method = params[ params.length - 1 ];
		const methodNode = new ShaderNode( method );

		// chain multiple cases when using Case( 1, 2, 3, () => {} )

		let caseNode = caseNodes[ 0 ];

		for ( let i = 1; i < caseNodes.length; i ++ ) {

			caseNode = caseNode.or( caseNodes[ i ] );

		}

		// build condition

		const condNode = select( caseNode, methodNode );

		if ( this._currentCond === null ) {

			this._currentCond = condNode;

			return this.add( this._currentCond );

		} else {

			this._currentCond.elseNode = condNode;
			this._currentCond = condNode;

			return this;

		}

	}

	/**
	 * Represents the default code block of a Switch/Case statement.
	 *
	 * @param {Function} method - TSL code which is executed in the `else` case.
	 * @return {StackNode} A reference to this stack node.
	 */
	Default( method ) {

		this.Else( method );

		return this;

	}

	setup( builder ) {

		const nodeProperties = builder.getNodeProperties( this );

		let index = 0;

		for ( const childNode of this.getChildren() ) {

			if ( childNode.isVarNode && childNode.intent === true ) {

				const properties = builder.getNodeProperties( childNode );

				if ( properties.assign !== true ) {

					continue;

				}

			}

			nodeProperties[ 'node' + index ++ ] = childNode;

		}

		// return a outputNode if exists or null

		return nodeProperties.outputNode || null;

	}

	get hasOutput() {

		return this.outputNode && this.outputNode.isNode;

	}

	build( builder, ...params ) {

		const previousBuildStack = builder.currentStack;
		const previousStack = getCurrentStack();

		setCurrentStack( this );

		builder.currentStack = this;

		const buildStage = builder.buildStage;

		for ( const node of this.nodes ) {

			if ( node.isVarNode && node.intent === true ) {

				const properties = builder.getNodeProperties( node );

				if ( properties.assign !== true ) {

					continue;

				}

			}

			if ( buildStage === 'setup' ) {

				node.build( builder );

			} else if ( buildStage === 'analyze' ) {

				node.build( builder, this );

			} else if ( buildStage === 'generate' ) {

				const stages = builder.getDataFromNode( node, 'any' ).stages;
				const parents = stages && stages[ builder.shaderStage ];

				if ( node.isVarNode && parents && parents.length === 1 && parents[ 0 ] && parents[ 0 ].isStackNode ) {

					continue; // skip var nodes that are only used in .toVarying()

				}

				node.build( builder, 'void' );

			}

		}

		//

		let result;

		if ( this.hasOutput ) {

			result = this.outputNode.build( builder, ...params );

		} else {

			result = super.build( builder, ...params );

		}

		setCurrentStack( previousStack );

		builder.currentStack = previousBuildStack;

		return result;

	}

}
```
</details>

#### Methods

##### `getNodeType(builder: any): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return this.hasOutput ? this.outputNode.getNodeType( builder ) : 'void';

	}
```
</details>

##### `getMemberType(builder: any, name: any): string`

<details><summary>Code</summary>

```ts
getMemberType( builder, name ) {

		return this.hasOutput ? this.outputNode.getMemberType( builder, name ) : 'void';

	}
```
</details>

##### `add(node: Node): StackNode`

<details><summary>Code</summary>

```ts
add( node ) {

		if ( node.isNode !== true ) {

			console.error( 'THREE.TSL: Invalid node added to stack.' );
			return this;

		}

		this.nodes.push( node );

		return this;

	}
```
</details>

##### `If(boolNode: Node, method: Function): StackNode`

<details><summary>Code</summary>

```ts
If( boolNode, method ) {

		const methodNode = new ShaderNode( method );
		this._currentCond = select( boolNode, methodNode );

		return this.add( this._currentCond );

	}
```
</details>

##### `ElseIf(boolNode: Node, method: Function): StackNode`

<details><summary>Code</summary>

```ts
ElseIf( boolNode, method ) {

		const methodNode = new ShaderNode( method );
		const ifNode = select( boolNode, methodNode );

		this._currentCond.elseNode = ifNode;
		this._currentCond = ifNode;

		return this;

	}
```
</details>

##### `Else(method: Function): StackNode`

<details><summary>Code</summary>

```ts
Else( method ) {

		this._currentCond.elseNode = new ShaderNode( method );

		return this;

	}
```
</details>

##### `Switch(expression: any): StackNode`

<details><summary>Code</summary>

```ts
Switch( expression ) {

		this._expressionNode = nodeObject( expression );

		return this;

	}
```
</details>

##### `Case(params: any[]): StackNode`

<details><summary>Code</summary>

```ts
Case( ...params ) {

		const caseNodes = [];

		// extract case nodes from the parameter list

		if ( params.length >= 2 ) {

			for ( let i = 0; i < params.length - 1; i ++ ) {

				caseNodes.push( this._expressionNode.equal( nodeObject( params[ i ] ) ) );

			}

		} else {

			console.error( 'THREE.TSL: Invalid parameter length. Case() requires at least two parameters.' );

		}

		// extract method

		const method = params[ params.length - 1 ];
		const methodNode = new ShaderNode( method );

		// chain multiple cases when using Case( 1, 2, 3, () => {} )

		let caseNode = caseNodes[ 0 ];

		for ( let i = 1; i < caseNodes.length; i ++ ) {

			caseNode = caseNode.or( caseNodes[ i ] );

		}

		// build condition

		const condNode = select( caseNode, methodNode );

		if ( this._currentCond === null ) {

			this._currentCond = condNode;

			return this.add( this._currentCond );

		} else {

			this._currentCond.elseNode = condNode;
			this._currentCond = condNode;

			return this;

		}

	}
```
</details>

##### `Default(method: Function): StackNode`

<details><summary>Code</summary>

```ts
Default( method ) {

		this.Else( method );

		return this;

	}
```
</details>

##### `setup(builder: any): any`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const nodeProperties = builder.getNodeProperties( this );

		let index = 0;

		for ( const childNode of this.getChildren() ) {

			if ( childNode.isVarNode && childNode.intent === true ) {

				const properties = builder.getNodeProperties( childNode );

				if ( properties.assign !== true ) {

					continue;

				}

			}

			nodeProperties[ 'node' + index ++ ] = childNode;

		}

		// return a outputNode if exists or null

		return nodeProperties.outputNode || null;

	}
```
</details>

##### `build(builder: any, params: any[]): string | Node`

<details><summary>Code</summary>

```ts
build( builder, ...params ) {

		const previousBuildStack = builder.currentStack;
		const previousStack = getCurrentStack();

		setCurrentStack( this );

		builder.currentStack = this;

		const buildStage = builder.buildStage;

		for ( const node of this.nodes ) {

			if ( node.isVarNode && node.intent === true ) {

				const properties = builder.getNodeProperties( node );

				if ( properties.assign !== true ) {

					continue;

				}

			}

			if ( buildStage === 'setup' ) {

				node.build( builder );

			} else if ( buildStage === 'analyze' ) {

				node.build( builder, this );

			} else if ( buildStage === 'generate' ) {

				const stages = builder.getDataFromNode( node, 'any' ).stages;
				const parents = stages && stages[ builder.shaderStage ];

				if ( node.isVarNode && parents && parents.length === 1 && parents[ 0 ] && parents[ 0 ].isStackNode ) {

					continue; // skip var nodes that are only used in .toVarying()

				}

				node.build( builder, 'void' );

			}

		}

		//

		let result;

		if ( this.hasOutput ) {

			result = this.outputNode.build( builder, ...params );

		} else {

			result = super.build( builder, ...params );

		}

		setCurrentStack( previousStack );

		builder.currentStack = previousBuildStack;

		return result;

	}
```
</details>


---