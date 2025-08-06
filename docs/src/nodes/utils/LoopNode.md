[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LoopNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 23 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/utils/LoopNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `expression` | `../code/ExpressionNode.js` |
| `nodeObject` | `../tsl/TSLBase.js` |
| `nodeArray` | `../tsl/TSLBase.js` |
| `Fn` | `../tsl/TSLBase.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `inputs` | `{}` | let/var | `{}` | ✗ |
| `param` | `any` | let/var | `this.params[ i ]` | ✗ |
| `name` | `any` | let/var | `( param.isNode !== true && param.name ) \|\| this.getVarName( i )` | ✗ |
| `type` | `any` | let/var | `( param.isNode !== true && param.type ) \|\| 'int'` | ✗ |
| `baseParam` | `any` | let/var | `this.params[ 0 ]` | ✗ |
| `params` | `any[]` | let/var | `this.params` | ✗ |
| `stackNode` | `any` | let/var | `properties.stackNode` | ✗ |
| `param` | `any` | let/var | `params[ i ]` | ✗ |
| `isWhile` | `boolean` | let/var | `false` | ✗ |
| `start` | `any` | let/var | `null` | ✗ |
| `end` | `any` | let/var | `null` | ✗ |
| `name` | `any` | let/var | `null` | ✗ |
| `type` | `any` | let/var | `null` | ✗ |
| `condition` | `any` | let/var | `null` | ✗ |
| `update` | `any` | let/var | `null` | ✗ |
| `loopSnippet` | `any` | let/var | `*not shown*` | ✗ |
| `internalParam` | `{ start: any; end: any; condition: an...` | let/var | `{ start, end, condition }` | ✗ |
| `startSnippet` | `any` | let/var | `internalParam.start` | ✗ |
| `endSnippet` | `any` | let/var | `internalParam.end` | ✗ |
| `updateSnippet` | `any` | let/var | `*not shown*` | ✗ |
| `declarationSnippet` | `string` | let/var | `builder.getVar( type, name ) + ' = ' + startSnippet` | ✗ |
| `conditionalSnippet` | `string` | let/var | `name + ' ' + condition + ' ' + endSnippet` | ✗ |
| `returnsSnippet` | `any` | let/var | `properties.returnsNode ? properties.returnsNode.build( builder ) : ''` | ✗ |


---

## Functions

### `LoopNode.getVarName(index: number): string`

**JSDoc:**
```typescript
/**
	 * Returns a loop variable name based on an index. The pattern is
	 * `0` = `i`, `1`= `j`, `2`= `k` and so on.
	 *
	 * @param {number} index - The index.
	 * @return {string} The loop variable name.
	 */
```

**Parameters:**

- **`index`** `number`

**Returns:** `string`

**Calls:**

- `String.fromCharCode`
- `'i'.charCodeAt`

<details><summary>Code</summary>

```typescript
getVarName( index ) {

		return String.fromCharCode( 'i'.charCodeAt( 0 ) + index );

	}
```
</details>

### `LoopNode.getProperties(builder: NodeBuilder): any`

**JSDoc:**
```typescript
/**
	 * Returns properties about this node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Object} The node properties.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `any`

**Calls:**

- `builder.getNodeProperties`
- `this.getVarName`
- `expression (from ../code/ExpressionNode.js)`
- `builder.addStack`
- `complex_call_2411`
- `complex_call_2648`
- `builder.removeStack`

**Internal Comments:**
```
// (x2)
```

<details><summary>Code</summary>

```typescript
getProperties( builder ) {

		const properties = builder.getNodeProperties( this );

		if ( properties.stackNode !== undefined ) return properties;

		//

		const inputs = {};

		for ( let i = 0, l = this.params.length - 1; i < l; i ++ ) {

			const param = this.params[ i ];

			const name = ( param.isNode !== true && param.name ) || this.getVarName( i );
			const type = ( param.isNode !== true && param.type ) || 'int';

			inputs[ name ] = expression( name, type );

		}

		const stack = builder.addStack(); // TODO: cache() it

		properties.returnsNode = this.params[ this.params.length - 1 ]( inputs, builder );
		properties.stackNode = stack;

		const baseParam = this.params[ 0 ];

		if ( baseParam.isNode !== true && typeof baseParam.update === 'function' ) {

			properties.updateNode = Fn( this.params[ 0 ].update )( inputs );

		}

		builder.removeStack();

		return properties;

	}
```
</details>

### `LoopNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node type is inferred based on the loop configuration.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.getProperties`
- `returnsNode.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		const { returnsNode } = this.getProperties( builder );

		return returnsNode ? returnsNode.getNodeType( builder ) : 'void';

	}
```
</details>

### `LoopNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `this.getProperties`

**Internal Comments:**
```
// setup properties (x4)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		// setup properties

		this.getProperties( builder );

	}
```
</details>

### `LoopNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this.getProperties`
- `param.getNodeType`
- `param.build`
- `this.getVarName`
- `builder.generateConst`
- `start.build`
- `end.build`
- `Number`
- `condition.includes`
- `builder.flowStagesNode`
- `flow.code.replace`
- `deltaOperator`
- `update.build`
- `console.error`
- `builder.getVar`
- `builder.addFlowCode( ( i === 0 ? '\n' : '' ) + builder.tab + loopSnippet + ' {\n\n' ).addFlowTab`
- `stackNode.build`
- `properties.returnsNode.build`
- `builder.removeFlowTab().addFlowCode`
- `builder.addFlowCode( ( i === 0 ? '' : builder.tab ) + '}\n\n' ).removeFlowTab`
- `builder.addFlowTab`

**Internal Comments:**
```
// (x2)
```

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const properties = this.getProperties( builder );

		const params = this.params;
		const stackNode = properties.stackNode;

		for ( let i = 0, l = params.length - 1; i < l; i ++ ) {

			const param = params[ i ];

			let isWhile = false, start = null, end = null, name = null, type = null, condition = null, update = null;

			if ( param.isNode ) {

				if ( param.getNodeType( builder ) === 'bool' ) {

					isWhile = true;
					type = 'bool';
					end = param.build( builder, type );

				} else {

					type = 'int';
					name = this.getVarName( i );
					start = '0';
					end = param.build( builder, type );
					condition = '<';

				}

			} else {

				type = param.type || 'int';
				name = param.name || this.getVarName( i );
				start = param.start;
				end = param.end;
				condition = param.condition;
				update = param.update;

				if ( typeof start === 'number' ) start = builder.generateConst( type, start );
				else if ( start && start.isNode ) start = start.build( builder, type );

				if ( typeof end === 'number' ) end = builder.generateConst( type, end );
				else if ( end && end.isNode ) end = end.build( builder, type );

				if ( start !== undefined && end === undefined ) {

					start = start + ' - 1';
					end = '0';
					condition = '>=';

				} else if ( end !== undefined && start === undefined ) {

					start = '0';
					condition = '<';

				}

				if ( condition === undefined ) {

					if ( Number( start ) > Number( end ) ) {

						condition = '>=';

					} else {

						condition = '<';

					}

				}

			}

			let loopSnippet;

			if ( isWhile ) {

				loopSnippet = `while ( ${ end } )`;

			} else {

				const internalParam = { start, end, condition };

				//

				const startSnippet = internalParam.start;
				const endSnippet = internalParam.end;

				let updateSnippet;

				const deltaOperator = () => condition.includes( '<' ) ? '+=' : '-=';

				if ( update !== undefined && update !== null ) {

					switch ( typeof update ) {

						case 'function':

							const flow = builder.flowStagesNode( properties.updateNode, 'void' );
							const snippet = flow.code.replace( /\t|;/g, '' );

							updateSnippet = snippet;

							break;

						case 'number':

							updateSnippet = name + ' ' + deltaOperator() + ' ' + builder.generateConst( type, update );

							break;

						case 'string':

							updateSnippet = name + ' ' + update;

							break;

						default:

							if ( update.isNode ) {

								updateSnippet = name + ' ' + deltaOperator() + ' ' + update.build( builder );

							} else {

								console.error( 'THREE.TSL: \'Loop( { update: ... } )\' is not a function, string or number.' );

								updateSnippet = 'break /* invalid update */';

							}

					}

				} else {

					if ( type === 'int' || type === 'uint' ) {

						update = condition.includes( '<' ) ? '++' : '--';

					} else {

						update = deltaOperator() + ' 1.';

					}

					updateSnippet = name + ' ' + update;

				}

				const declarationSnippet = builder.getVar( type, name ) + ' = ' + startSnippet;
				const conditionalSnippet = name + ' ' + condition + ' ' + endSnippet;

				loopSnippet = `for ( ${ declarationSnippet }; ${ conditionalSnippet }; ${ updateSnippet } )`;

			}

			builder.addFlowCode( ( i === 0 ? '\n' : '' ) + builder.tab + loopSnippet + ' {\n\n' ).addFlowTab();

		}

		const stackSnippet = stackNode.build( builder, 'void' );

		const returnsSnippet = properties.returnsNode ? properties.returnsNode.build( builder ) : '';

		builder.removeFlowTab().addFlowCode( '\n' + builder.tab + stackSnippet );

		for ( let i = 0, l = this.params.length - 1; i < l; i ++ ) {

			builder.addFlowCode( ( i === 0 ? '' : builder.tab ) + '}\n\n' ).removeFlowTab();

		}

		builder.addFlowTab();

		return returnsSnippet;

	}
```
</details>

### `deltaOperator(): "+=" | "-="`

**Returns:** `"+=" | "-="`

<details><summary>Code</summary>

```typescript
() => condition.includes( '<' ) ? '+=' : '-='
```
</details>

### `Loop(params: any[]): LoopNode`

**Parameters:**

- **`params`** `any[]`

**Returns:** `LoopNode`

**Calls:**

- `nodeObject( new LoopNode( nodeArray( params, 'int' ) ) ).toStack`

<details><summary>Code</summary>

```typescript
( ...params ) => nodeObject( new LoopNode( nodeArray( params, 'int' ) ) ).toStack()
```
</details>

### `Continue(): ExpressionNode`

**Returns:** `ExpressionNode`

**Calls:**

- `expression( 'continue' ).toStack`

<details><summary>Code</summary>

```typescript
() => expression( 'continue' ).toStack()
```
</details>

### `Break(): ExpressionNode`

**Returns:** `ExpressionNode`

**Calls:**

- `expression( 'break' ).toStack`

<details><summary>Code</summary>

```typescript
() => expression( 'break' ).toStack()
```
</details>


---

## Classes

### `LoopNode`

<details><summary>Class Code</summary>

```ts
class LoopNode extends Node {

	static get type() {

		return 'LoopNode';

	}

	/**
	 * Constructs a new loop node.
	 *
	 * @param {Array<any>} params - Depending on the loop type, array holds different parameterization values for the loop.
	 */
	constructor( params = [] ) {

		super();

		this.params = params;

	}

	/**
	 * Returns a loop variable name based on an index. The pattern is
	 * `0` = `i`, `1`= `j`, `2`= `k` and so on.
	 *
	 * @param {number} index - The index.
	 * @return {string} The loop variable name.
	 */
	getVarName( index ) {

		return String.fromCharCode( 'i'.charCodeAt( 0 ) + index );

	}

	/**
	 * Returns properties about this node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Object} The node properties.
	 */
	getProperties( builder ) {

		const properties = builder.getNodeProperties( this );

		if ( properties.stackNode !== undefined ) return properties;

		//

		const inputs = {};

		for ( let i = 0, l = this.params.length - 1; i < l; i ++ ) {

			const param = this.params[ i ];

			const name = ( param.isNode !== true && param.name ) || this.getVarName( i );
			const type = ( param.isNode !== true && param.type ) || 'int';

			inputs[ name ] = expression( name, type );

		}

		const stack = builder.addStack(); // TODO: cache() it

		properties.returnsNode = this.params[ this.params.length - 1 ]( inputs, builder );
		properties.stackNode = stack;

		const baseParam = this.params[ 0 ];

		if ( baseParam.isNode !== true && typeof baseParam.update === 'function' ) {

			properties.updateNode = Fn( this.params[ 0 ].update )( inputs );

		}

		builder.removeStack();

		return properties;

	}

	/**
	 * This method is overwritten since the node type is inferred based on the loop configuration.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( builder ) {

		const { returnsNode } = this.getProperties( builder );

		return returnsNode ? returnsNode.getNodeType( builder ) : 'void';

	}

	setup( builder ) {

		// setup properties

		this.getProperties( builder );

	}

	generate( builder ) {

		const properties = this.getProperties( builder );

		const params = this.params;
		const stackNode = properties.stackNode;

		for ( let i = 0, l = params.length - 1; i < l; i ++ ) {

			const param = params[ i ];

			let isWhile = false, start = null, end = null, name = null, type = null, condition = null, update = null;

			if ( param.isNode ) {

				if ( param.getNodeType( builder ) === 'bool' ) {

					isWhile = true;
					type = 'bool';
					end = param.build( builder, type );

				} else {

					type = 'int';
					name = this.getVarName( i );
					start = '0';
					end = param.build( builder, type );
					condition = '<';

				}

			} else {

				type = param.type || 'int';
				name = param.name || this.getVarName( i );
				start = param.start;
				end = param.end;
				condition = param.condition;
				update = param.update;

				if ( typeof start === 'number' ) start = builder.generateConst( type, start );
				else if ( start && start.isNode ) start = start.build( builder, type );

				if ( typeof end === 'number' ) end = builder.generateConst( type, end );
				else if ( end && end.isNode ) end = end.build( builder, type );

				if ( start !== undefined && end === undefined ) {

					start = start + ' - 1';
					end = '0';
					condition = '>=';

				} else if ( end !== undefined && start === undefined ) {

					start = '0';
					condition = '<';

				}

				if ( condition === undefined ) {

					if ( Number( start ) > Number( end ) ) {

						condition = '>=';

					} else {

						condition = '<';

					}

				}

			}

			let loopSnippet;

			if ( isWhile ) {

				loopSnippet = `while ( ${ end } )`;

			} else {

				const internalParam = { start, end, condition };

				//

				const startSnippet = internalParam.start;
				const endSnippet = internalParam.end;

				let updateSnippet;

				const deltaOperator = () => condition.includes( '<' ) ? '+=' : '-=';

				if ( update !== undefined && update !== null ) {

					switch ( typeof update ) {

						case 'function':

							const flow = builder.flowStagesNode( properties.updateNode, 'void' );
							const snippet = flow.code.replace( /\t|;/g, '' );

							updateSnippet = snippet;

							break;

						case 'number':

							updateSnippet = name + ' ' + deltaOperator() + ' ' + builder.generateConst( type, update );

							break;

						case 'string':

							updateSnippet = name + ' ' + update;

							break;

						default:

							if ( update.isNode ) {

								updateSnippet = name + ' ' + deltaOperator() + ' ' + update.build( builder );

							} else {

								console.error( 'THREE.TSL: \'Loop( { update: ... } )\' is not a function, string or number.' );

								updateSnippet = 'break /* invalid update */';

							}

					}

				} else {

					if ( type === 'int' || type === 'uint' ) {

						update = condition.includes( '<' ) ? '++' : '--';

					} else {

						update = deltaOperator() + ' 1.';

					}

					updateSnippet = name + ' ' + update;

				}

				const declarationSnippet = builder.getVar( type, name ) + ' = ' + startSnippet;
				const conditionalSnippet = name + ' ' + condition + ' ' + endSnippet;

				loopSnippet = `for ( ${ declarationSnippet }; ${ conditionalSnippet }; ${ updateSnippet } )`;

			}

			builder.addFlowCode( ( i === 0 ? '\n' : '' ) + builder.tab + loopSnippet + ' {\n\n' ).addFlowTab();

		}

		const stackSnippet = stackNode.build( builder, 'void' );

		const returnsSnippet = properties.returnsNode ? properties.returnsNode.build( builder ) : '';

		builder.removeFlowTab().addFlowCode( '\n' + builder.tab + stackSnippet );

		for ( let i = 0, l = this.params.length - 1; i < l; i ++ ) {

			builder.addFlowCode( ( i === 0 ? '' : builder.tab ) + '}\n\n' ).removeFlowTab();

		}

		builder.addFlowTab();

		return returnsSnippet;

	}

}
```
</details>

#### Methods

##### `getVarName(index: number): string`

<details><summary>Code</summary>

```ts
getVarName( index ) {

		return String.fromCharCode( 'i'.charCodeAt( 0 ) + index );

	}
```
</details>

##### `getProperties(builder: NodeBuilder): any`

<details><summary>Code</summary>

```ts
getProperties( builder ) {

		const properties = builder.getNodeProperties( this );

		if ( properties.stackNode !== undefined ) return properties;

		//

		const inputs = {};

		for ( let i = 0, l = this.params.length - 1; i < l; i ++ ) {

			const param = this.params[ i ];

			const name = ( param.isNode !== true && param.name ) || this.getVarName( i );
			const type = ( param.isNode !== true && param.type ) || 'int';

			inputs[ name ] = expression( name, type );

		}

		const stack = builder.addStack(); // TODO: cache() it

		properties.returnsNode = this.params[ this.params.length - 1 ]( inputs, builder );
		properties.stackNode = stack;

		const baseParam = this.params[ 0 ];

		if ( baseParam.isNode !== true && typeof baseParam.update === 'function' ) {

			properties.updateNode = Fn( this.params[ 0 ].update )( inputs );

		}

		builder.removeStack();

		return properties;

	}
```
</details>

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		const { returnsNode } = this.getProperties( builder );

		return returnsNode ? returnsNode.getNodeType( builder ) : 'void';

	}
```
</details>

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		// setup properties

		this.getProperties( builder );

	}
```
</details>

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const properties = this.getProperties( builder );

		const params = this.params;
		const stackNode = properties.stackNode;

		for ( let i = 0, l = params.length - 1; i < l; i ++ ) {

			const param = params[ i ];

			let isWhile = false, start = null, end = null, name = null, type = null, condition = null, update = null;

			if ( param.isNode ) {

				if ( param.getNodeType( builder ) === 'bool' ) {

					isWhile = true;
					type = 'bool';
					end = param.build( builder, type );

				} else {

					type = 'int';
					name = this.getVarName( i );
					start = '0';
					end = param.build( builder, type );
					condition = '<';

				}

			} else {

				type = param.type || 'int';
				name = param.name || this.getVarName( i );
				start = param.start;
				end = param.end;
				condition = param.condition;
				update = param.update;

				if ( typeof start === 'number' ) start = builder.generateConst( type, start );
				else if ( start && start.isNode ) start = start.build( builder, type );

				if ( typeof end === 'number' ) end = builder.generateConst( type, end );
				else if ( end && end.isNode ) end = end.build( builder, type );

				if ( start !== undefined && end === undefined ) {

					start = start + ' - 1';
					end = '0';
					condition = '>=';

				} else if ( end !== undefined && start === undefined ) {

					start = '0';
					condition = '<';

				}

				if ( condition === undefined ) {

					if ( Number( start ) > Number( end ) ) {

						condition = '>=';

					} else {

						condition = '<';

					}

				}

			}

			let loopSnippet;

			if ( isWhile ) {

				loopSnippet = `while ( ${ end } )`;

			} else {

				const internalParam = { start, end, condition };

				//

				const startSnippet = internalParam.start;
				const endSnippet = internalParam.end;

				let updateSnippet;

				const deltaOperator = () => condition.includes( '<' ) ? '+=' : '-=';

				if ( update !== undefined && update !== null ) {

					switch ( typeof update ) {

						case 'function':

							const flow = builder.flowStagesNode( properties.updateNode, 'void' );
							const snippet = flow.code.replace( /\t|;/g, '' );

							updateSnippet = snippet;

							break;

						case 'number':

							updateSnippet = name + ' ' + deltaOperator() + ' ' + builder.generateConst( type, update );

							break;

						case 'string':

							updateSnippet = name + ' ' + update;

							break;

						default:

							if ( update.isNode ) {

								updateSnippet = name + ' ' + deltaOperator() + ' ' + update.build( builder );

							} else {

								console.error( 'THREE.TSL: \'Loop( { update: ... } )\' is not a function, string or number.' );

								updateSnippet = 'break /* invalid update */';

							}

					}

				} else {

					if ( type === 'int' || type === 'uint' ) {

						update = condition.includes( '<' ) ? '++' : '--';

					} else {

						update = deltaOperator() + ' 1.';

					}

					updateSnippet = name + ' ' + update;

				}

				const declarationSnippet = builder.getVar( type, name ) + ' = ' + startSnippet;
				const conditionalSnippet = name + ' ' + condition + ' ' + endSnippet;

				loopSnippet = `for ( ${ declarationSnippet }; ${ conditionalSnippet }; ${ updateSnippet } )`;

			}

			builder.addFlowCode( ( i === 0 ? '\n' : '' ) + builder.tab + loopSnippet + ' {\n\n' ).addFlowTab();

		}

		const stackSnippet = stackNode.build( builder, 'void' );

		const returnsSnippet = properties.returnsNode ? properties.returnsNode.build( builder ) : '';

		builder.removeFlowTab().addFlowCode( '\n' + builder.tab + stackSnippet );

		for ( let i = 0, l = this.params.length - 1; i < l; i ++ ) {

			builder.addFlowCode( ( i === 0 ? '' : builder.tab ) + '}\n\n' ).removeFlowTab();

		}

		builder.addFlowTab();

		return returnsSnippet;

	}
```
</details>


---