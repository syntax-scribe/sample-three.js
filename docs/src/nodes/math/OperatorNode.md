[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `OperatorNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 12 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/math/OperatorNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `WebGLCoordinateSystem` | `../../constants.js` |
| `TempNode` | `../core/TempNode.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `Fn` | `../tsl/TSLCore.js` |
| `int` | `../tsl/TSLCore.js` |
| `nodeProxyIntent` | `../tsl/TSLCore.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_vectorOperators` | `{ '==': string; '!=': string; '<': st...` | let/var | `{ '==': 'equal', '!=': 'notEqual', '<': 'lessThan', '>': 'greaterThan', '<=':...` | ✗ |
| `finalOp` | `OperatorNode` | let/var | `new OperatorNode( op, aNode, bNode )` | ✗ |
| `op` | `string` | let/var | `this.op` | ✗ |
| `aNode` | `Node` | let/var | `this.aNode` | ✗ |
| `bNode` | `Node` | let/var | `this.bNode` | ✗ |
| `typeB` | `any` | let/var | `bNode ? bNode.getNodeType( builder ) : null` | ✗ |
| `op` | `string` | let/var | `this.op` | ✗ |
| `typeA` | `any` | let/var | `null` | ✗ |
| `typeB` | `any` | let/var | `null` | ✗ |
| `b` | `any` | let/var | `bNode ? bNode.build( builder, typeB ) : null` | ✗ |
| `isGLSL` | `boolean` | let/var | `builder.renderer.coordinateSystem === WebGLCoordinateSystem` | ✗ |
| `snippet` | `string` | let/var | ``( ${ a } ${ op } ${ b } )`` | ✗ |


---

## Functions

### `OperatorNode.getOperatorMethod(builder: NodeBuilder, output: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the operator method name.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {string} output - The output type.
	 * @returns {string} The operator method name.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`output`** `string`

**Returns:** `string`

**Calls:**

- `builder.getMethod`

<details><summary>Code</summary>

```typescript
getOperatorMethod( builder, output ) {

		return builder.getMethod( _vectorOperators[ this.op ], output );

	}
```
</details>

### `OperatorNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node type is inferred from the operator
	 * and the input node types.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `aNode.getNodeType`
- `bNode.getNodeType`
- `builder.getIntegerType`
- `Math.max`
- `builder.getTypeLength`
- `builder.isMatrix`
- `builder.isVector`
- `builder.getVectorFromMatrix`

**Internal Comments:**
```
// Handle matrix operations
// Handle non-matrix cases
// anytype x anytype: use the greater length vector
```

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		const op = this.op;

		const aNode = this.aNode;
		const bNode = this.bNode;

		const typeA = aNode.getNodeType( builder );
		const typeB = bNode ? bNode.getNodeType( builder ) : null;

		if ( typeA === 'void' || typeB === 'void' ) {

			return 'void';

		} else if ( op === '%' ) {

			return typeA;

		} else if ( op === '~' || op === '&' || op === '|' || op === '^' || op === '>>' || op === '<<' ) {

			return builder.getIntegerType( typeA );

		} else if ( op === '!' || op === '&&' || op === '||' || op === '^^' ) {

			return 'bool';

		} else if ( op === '==' || op === '!=' || op === '<' || op === '>' || op === '<=' || op === '>=' ) {

			const typeLength = Math.max( builder.getTypeLength( typeA ), builder.getTypeLength( typeB ) );

			return typeLength > 1 ? `bvec${ typeLength }` : 'bool';

		} else {

			// Handle matrix operations

			if ( builder.isMatrix( typeA ) ) {

				if ( typeB === 'float' ) {

					return typeA; // matrix * scalar = matrix

				} else if ( builder.isVector( typeB ) ) {

					return builder.getVectorFromMatrix( typeA ); // matrix * vector

				} else if ( builder.isMatrix( typeB ) ) {

					return typeA; // matrix * matrix

				}

			} else if ( builder.isMatrix( typeB ) ) {

				if ( typeA === 'float' ) {

					return typeB; // scalar * matrix = matrix

				} else if ( builder.isVector( typeA ) ) {

					return builder.getVectorFromMatrix( typeB ); // vector * matrix

				}

			}

			// Handle non-matrix cases

			if ( builder.getTypeLength( typeB ) > builder.getTypeLength( typeA ) ) {

				// anytype x anytype: use the greater length vector

				return typeB;

			}

			return typeA;

		}

	}
```
</details>

### `OperatorNode.generate(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `this.getNodeType`
- `aNode.getNodeType`
- `bNode.getNodeType`
- `builder.isVector`
- `builder.changeComponentType`
- `builder.isInteger`
- `builder.isMatrix`
- `builder.getVectorFromMatrix`
- `aNode.build`
- `bNode.build`
- `builder.getFunctionOperator`
- `builder.format`
- `this.getOperatorMethod`

**Internal Comments:**
```
// Keep matrix type for typeA, but ensure typeB stays float (x3)
// matrix x vector (x3)
// Keep matrix type for typeB, but ensure typeA stays float (x3)
// vector x matrix (x3)
// anytype x anytype (x3)
// WGSL
// Handle matrix operations
```

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		const op = this.op;

		const { aNode, bNode } = this;

		const type = this.getNodeType( builder );

		let typeA = null;
		let typeB = null;

		if ( type !== 'void' ) {

			typeA = aNode.getNodeType( builder );
			typeB = bNode ? bNode.getNodeType( builder ) : null;

			if ( op === '<' || op === '>' || op === '<=' || op === '>=' || op === '==' || op === '!=' ) {

				if ( builder.isVector( typeA ) ) {

					typeB = typeA;

				} else if ( builder.isVector( typeB ) ) {

					typeA = typeB;

				} else if ( typeA !== typeB ) {

					typeA = typeB = 'float';

				}

			} else if ( op === '>>' || op === '<<' ) {

				typeA = type;
				typeB = builder.changeComponentType( typeB, 'uint' );

			} else if ( op === '%' ) {

				typeA = type;
				typeB = builder.isInteger( typeA ) && builder.isInteger( typeB ) ? typeB : typeA;

			} else if ( builder.isMatrix( typeA ) ) {

				if ( typeB === 'float' ) {

					// Keep matrix type for typeA, but ensure typeB stays float

					typeB = 'float';

				} else if ( builder.isVector( typeB ) ) {

					// matrix x vector
					typeB = builder.getVectorFromMatrix( typeA );

				} else if ( builder.isMatrix( typeB ) ) {

					// matrix x matrix - keep both types

				} else {

					typeA = typeB = type;

				}

			} else if ( builder.isMatrix( typeB ) ) {

				if ( typeA === 'float' ) {

					// Keep matrix type for typeB, but ensure typeA stays float

					typeA = 'float';

				} else if ( builder.isVector( typeA ) ) {

					// vector x matrix

					typeA = builder.getVectorFromMatrix( typeB );

				} else {

					typeA = typeB = type;

				}

			} else {

				// anytype x anytype

				typeA = typeB = type;

			}

		} else {

			typeA = typeB = type;

		}

		const a = aNode.build( builder, typeA );
		const b = bNode ? bNode.build( builder, typeB ) : null;

		const fnOpSnippet = builder.getFunctionOperator( op );

		if ( output !== 'void' ) {

			const isGLSL = builder.renderer.coordinateSystem === WebGLCoordinateSystem;

			if ( op === '==' || op === '!=' || op === '<' || op === '>' || op === '<=' || op === '>=' ) {

				if ( isGLSL ) {

					if ( builder.isVector( typeA ) ) {

						return builder.format( `${ this.getOperatorMethod( builder, output ) }( ${ a }, ${ b } )`, type, output );

					} else {

						return builder.format( `( ${ a } ${ op } ${ b } )`, type, output );

					}

				} else {

					// WGSL

					return builder.format( `( ${ a } ${ op } ${ b } )`, type, output );

				}

			} else if ( op === '%' ) {

				if ( builder.isInteger( typeB ) ) {

					return builder.format( `( ${ a } % ${ b } )`, type, output );

				} else {

					return builder.format( `${ this.getOperatorMethod( builder, type ) }( ${ a }, ${ b } )`, type, output );

				}

			} else if ( op === '!' || op === '~' ) {

				return builder.format( `(${op}${a})`, typeA, output );

			} else if ( fnOpSnippet ) {

				return builder.format( `${ fnOpSnippet }( ${ a }, ${ b } )`, type, output );

			} else {

				// Handle matrix operations

				if ( builder.isMatrix( typeA ) && typeB === 'float' ) {

					return builder.format( `( ${ b } ${ op } ${ a } )`, type, output );

				} else if ( typeA === 'float' && builder.isMatrix( typeB ) ) {

					return builder.format( `${ a } ${ op } ${ b }`, type, output );

				} else {

					let snippet = `( ${ a } ${ op } ${ b } )`;

					if ( ! isGLSL && type === 'bool' && builder.isVector( typeA ) && builder.isVector( typeB ) ) {

						snippet = `all${ snippet }`;

					}

					return builder.format( snippet, type, output );

				}

			}

		} else if ( typeA !== 'void' ) {

			if ( fnOpSnippet ) {

				return builder.format( `${ fnOpSnippet }( ${ a }, ${ b } )`, type, output );

			} else {

				if ( builder.isMatrix( typeA ) && typeB === 'float' ) {

					return builder.format( `${ b } ${ op } ${ a }`, type, output );

				} else {

					return builder.format( `${ a } ${ op } ${ b }`, type, output );

				}

			}

		}

	}
```
</details>

### `OperatorNode.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		data.op = this.op;

	}
```
</details>

### `OperatorNode.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		this.op = data.op;

	}
```
</details>

### `modInt(a: Node, b: Node): OperatorNode`

**Parameters:**

- **`a`** `Node`
- **`b`** `Node`

**Returns:** `OperatorNode`

**Calls:**

- `console.warn`
- `mod`
- `int (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( a, b ) => { // @deprecated, r175

	console.warn( 'THREE.TSL: "modInt()" is deprecated. Use "mod( int( ... ) )" instead.' );
	return mod( int( a ), int( b ) );

}
```
</details>


---

## Classes

### `OperatorNode`

<details><summary>Class Code</summary>

```ts
class OperatorNode extends TempNode {

	static get type() {

		return 'OperatorNode';

	}

	/**
	 * Constructs a new operator node.
	 *
	 * @param {string} op - The operator.
	 * @param {Node} aNode - The first input.
	 * @param {Node} bNode - The second input.
	 * @param {...Node} params - Additional input parameters.
	 */
	constructor( op, aNode, bNode, ...params ) {

		super();

		if ( params.length > 0 ) {

			let finalOp = new OperatorNode( op, aNode, bNode );

			for ( let i = 0; i < params.length - 1; i ++ ) {

				finalOp = new OperatorNode( op, finalOp, params[ i ] );

			}

			aNode = finalOp;
			bNode = params[ params.length - 1 ];

		}

		/**
		 * The operator.
		 *
		 * @type {string}
		 */
		this.op = op;

		/**
		 * The first input.
		 *
		 * @type {Node}
		 */
		this.aNode = aNode;

		/**
		 * The second input.
		 *
		 * @type {Node}
		 */
		this.bNode = bNode;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isOperatorNode = true;

	}

	/**
	 * Returns the operator method name.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {string} output - The output type.
	 * @returns {string} The operator method name.
	 */
	getOperatorMethod( builder, output ) {

		return builder.getMethod( _vectorOperators[ this.op ], output );

	}

	/**
	 * This method is overwritten since the node type is inferred from the operator
	 * and the input node types.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( builder ) {

		const op = this.op;

		const aNode = this.aNode;
		const bNode = this.bNode;

		const typeA = aNode.getNodeType( builder );
		const typeB = bNode ? bNode.getNodeType( builder ) : null;

		if ( typeA === 'void' || typeB === 'void' ) {

			return 'void';

		} else if ( op === '%' ) {

			return typeA;

		} else if ( op === '~' || op === '&' || op === '|' || op === '^' || op === '>>' || op === '<<' ) {

			return builder.getIntegerType( typeA );

		} else if ( op === '!' || op === '&&' || op === '||' || op === '^^' ) {

			return 'bool';

		} else if ( op === '==' || op === '!=' || op === '<' || op === '>' || op === '<=' || op === '>=' ) {

			const typeLength = Math.max( builder.getTypeLength( typeA ), builder.getTypeLength( typeB ) );

			return typeLength > 1 ? `bvec${ typeLength }` : 'bool';

		} else {

			// Handle matrix operations

			if ( builder.isMatrix( typeA ) ) {

				if ( typeB === 'float' ) {

					return typeA; // matrix * scalar = matrix

				} else if ( builder.isVector( typeB ) ) {

					return builder.getVectorFromMatrix( typeA ); // matrix * vector

				} else if ( builder.isMatrix( typeB ) ) {

					return typeA; // matrix * matrix

				}

			} else if ( builder.isMatrix( typeB ) ) {

				if ( typeA === 'float' ) {

					return typeB; // scalar * matrix = matrix

				} else if ( builder.isVector( typeA ) ) {

					return builder.getVectorFromMatrix( typeB ); // vector * matrix

				}

			}

			// Handle non-matrix cases

			if ( builder.getTypeLength( typeB ) > builder.getTypeLength( typeA ) ) {

				// anytype x anytype: use the greater length vector

				return typeB;

			}

			return typeA;

		}

	}

	generate( builder, output ) {

		const op = this.op;

		const { aNode, bNode } = this;

		const type = this.getNodeType( builder );

		let typeA = null;
		let typeB = null;

		if ( type !== 'void' ) {

			typeA = aNode.getNodeType( builder );
			typeB = bNode ? bNode.getNodeType( builder ) : null;

			if ( op === '<' || op === '>' || op === '<=' || op === '>=' || op === '==' || op === '!=' ) {

				if ( builder.isVector( typeA ) ) {

					typeB = typeA;

				} else if ( builder.isVector( typeB ) ) {

					typeA = typeB;

				} else if ( typeA !== typeB ) {

					typeA = typeB = 'float';

				}

			} else if ( op === '>>' || op === '<<' ) {

				typeA = type;
				typeB = builder.changeComponentType( typeB, 'uint' );

			} else if ( op === '%' ) {

				typeA = type;
				typeB = builder.isInteger( typeA ) && builder.isInteger( typeB ) ? typeB : typeA;

			} else if ( builder.isMatrix( typeA ) ) {

				if ( typeB === 'float' ) {

					// Keep matrix type for typeA, but ensure typeB stays float

					typeB = 'float';

				} else if ( builder.isVector( typeB ) ) {

					// matrix x vector
					typeB = builder.getVectorFromMatrix( typeA );

				} else if ( builder.isMatrix( typeB ) ) {

					// matrix x matrix - keep both types

				} else {

					typeA = typeB = type;

				}

			} else if ( builder.isMatrix( typeB ) ) {

				if ( typeA === 'float' ) {

					// Keep matrix type for typeB, but ensure typeA stays float

					typeA = 'float';

				} else if ( builder.isVector( typeA ) ) {

					// vector x matrix

					typeA = builder.getVectorFromMatrix( typeB );

				} else {

					typeA = typeB = type;

				}

			} else {

				// anytype x anytype

				typeA = typeB = type;

			}

		} else {

			typeA = typeB = type;

		}

		const a = aNode.build( builder, typeA );
		const b = bNode ? bNode.build( builder, typeB ) : null;

		const fnOpSnippet = builder.getFunctionOperator( op );

		if ( output !== 'void' ) {

			const isGLSL = builder.renderer.coordinateSystem === WebGLCoordinateSystem;

			if ( op === '==' || op === '!=' || op === '<' || op === '>' || op === '<=' || op === '>=' ) {

				if ( isGLSL ) {

					if ( builder.isVector( typeA ) ) {

						return builder.format( `${ this.getOperatorMethod( builder, output ) }( ${ a }, ${ b } )`, type, output );

					} else {

						return builder.format( `( ${ a } ${ op } ${ b } )`, type, output );

					}

				} else {

					// WGSL

					return builder.format( `( ${ a } ${ op } ${ b } )`, type, output );

				}

			} else if ( op === '%' ) {

				if ( builder.isInteger( typeB ) ) {

					return builder.format( `( ${ a } % ${ b } )`, type, output );

				} else {

					return builder.format( `${ this.getOperatorMethod( builder, type ) }( ${ a }, ${ b } )`, type, output );

				}

			} else if ( op === '!' || op === '~' ) {

				return builder.format( `(${op}${a})`, typeA, output );

			} else if ( fnOpSnippet ) {

				return builder.format( `${ fnOpSnippet }( ${ a }, ${ b } )`, type, output );

			} else {

				// Handle matrix operations

				if ( builder.isMatrix( typeA ) && typeB === 'float' ) {

					return builder.format( `( ${ b } ${ op } ${ a } )`, type, output );

				} else if ( typeA === 'float' && builder.isMatrix( typeB ) ) {

					return builder.format( `${ a } ${ op } ${ b }`, type, output );

				} else {

					let snippet = `( ${ a } ${ op } ${ b } )`;

					if ( ! isGLSL && type === 'bool' && builder.isVector( typeA ) && builder.isVector( typeB ) ) {

						snippet = `all${ snippet }`;

					}

					return builder.format( snippet, type, output );

				}

			}

		} else if ( typeA !== 'void' ) {

			if ( fnOpSnippet ) {

				return builder.format( `${ fnOpSnippet }( ${ a }, ${ b } )`, type, output );

			} else {

				if ( builder.isMatrix( typeA ) && typeB === 'float' ) {

					return builder.format( `${ b } ${ op } ${ a }`, type, output );

				} else {

					return builder.format( `${ a } ${ op } ${ b }`, type, output );

				}

			}

		}

	}

	serialize( data ) {

		super.serialize( data );

		data.op = this.op;

	}

	deserialize( data ) {

		super.deserialize( data );

		this.op = data.op;

	}

}
```
</details>

#### Methods

##### `getOperatorMethod(builder: NodeBuilder, output: string): string`

<details><summary>Code</summary>

```ts
getOperatorMethod( builder, output ) {

		return builder.getMethod( _vectorOperators[ this.op ], output );

	}
```
</details>

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		const op = this.op;

		const aNode = this.aNode;
		const bNode = this.bNode;

		const typeA = aNode.getNodeType( builder );
		const typeB = bNode ? bNode.getNodeType( builder ) : null;

		if ( typeA === 'void' || typeB === 'void' ) {

			return 'void';

		} else if ( op === '%' ) {

			return typeA;

		} else if ( op === '~' || op === '&' || op === '|' || op === '^' || op === '>>' || op === '<<' ) {

			return builder.getIntegerType( typeA );

		} else if ( op === '!' || op === '&&' || op === '||' || op === '^^' ) {

			return 'bool';

		} else if ( op === '==' || op === '!=' || op === '<' || op === '>' || op === '<=' || op === '>=' ) {

			const typeLength = Math.max( builder.getTypeLength( typeA ), builder.getTypeLength( typeB ) );

			return typeLength > 1 ? `bvec${ typeLength }` : 'bool';

		} else {

			// Handle matrix operations

			if ( builder.isMatrix( typeA ) ) {

				if ( typeB === 'float' ) {

					return typeA; // matrix * scalar = matrix

				} else if ( builder.isVector( typeB ) ) {

					return builder.getVectorFromMatrix( typeA ); // matrix * vector

				} else if ( builder.isMatrix( typeB ) ) {

					return typeA; // matrix * matrix

				}

			} else if ( builder.isMatrix( typeB ) ) {

				if ( typeA === 'float' ) {

					return typeB; // scalar * matrix = matrix

				} else if ( builder.isVector( typeA ) ) {

					return builder.getVectorFromMatrix( typeB ); // vector * matrix

				}

			}

			// Handle non-matrix cases

			if ( builder.getTypeLength( typeB ) > builder.getTypeLength( typeA ) ) {

				// anytype x anytype: use the greater length vector

				return typeB;

			}

			return typeA;

		}

	}
```
</details>

##### `generate(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		const op = this.op;

		const { aNode, bNode } = this;

		const type = this.getNodeType( builder );

		let typeA = null;
		let typeB = null;

		if ( type !== 'void' ) {

			typeA = aNode.getNodeType( builder );
			typeB = bNode ? bNode.getNodeType( builder ) : null;

			if ( op === '<' || op === '>' || op === '<=' || op === '>=' || op === '==' || op === '!=' ) {

				if ( builder.isVector( typeA ) ) {

					typeB = typeA;

				} else if ( builder.isVector( typeB ) ) {

					typeA = typeB;

				} else if ( typeA !== typeB ) {

					typeA = typeB = 'float';

				}

			} else if ( op === '>>' || op === '<<' ) {

				typeA = type;
				typeB = builder.changeComponentType( typeB, 'uint' );

			} else if ( op === '%' ) {

				typeA = type;
				typeB = builder.isInteger( typeA ) && builder.isInteger( typeB ) ? typeB : typeA;

			} else if ( builder.isMatrix( typeA ) ) {

				if ( typeB === 'float' ) {

					// Keep matrix type for typeA, but ensure typeB stays float

					typeB = 'float';

				} else if ( builder.isVector( typeB ) ) {

					// matrix x vector
					typeB = builder.getVectorFromMatrix( typeA );

				} else if ( builder.isMatrix( typeB ) ) {

					// matrix x matrix - keep both types

				} else {

					typeA = typeB = type;

				}

			} else if ( builder.isMatrix( typeB ) ) {

				if ( typeA === 'float' ) {

					// Keep matrix type for typeB, but ensure typeA stays float

					typeA = 'float';

				} else if ( builder.isVector( typeA ) ) {

					// vector x matrix

					typeA = builder.getVectorFromMatrix( typeB );

				} else {

					typeA = typeB = type;

				}

			} else {

				// anytype x anytype

				typeA = typeB = type;

			}

		} else {

			typeA = typeB = type;

		}

		const a = aNode.build( builder, typeA );
		const b = bNode ? bNode.build( builder, typeB ) : null;

		const fnOpSnippet = builder.getFunctionOperator( op );

		if ( output !== 'void' ) {

			const isGLSL = builder.renderer.coordinateSystem === WebGLCoordinateSystem;

			if ( op === '==' || op === '!=' || op === '<' || op === '>' || op === '<=' || op === '>=' ) {

				if ( isGLSL ) {

					if ( builder.isVector( typeA ) ) {

						return builder.format( `${ this.getOperatorMethod( builder, output ) }( ${ a }, ${ b } )`, type, output );

					} else {

						return builder.format( `( ${ a } ${ op } ${ b } )`, type, output );

					}

				} else {

					// WGSL

					return builder.format( `( ${ a } ${ op } ${ b } )`, type, output );

				}

			} else if ( op === '%' ) {

				if ( builder.isInteger( typeB ) ) {

					return builder.format( `( ${ a } % ${ b } )`, type, output );

				} else {

					return builder.format( `${ this.getOperatorMethod( builder, type ) }( ${ a }, ${ b } )`, type, output );

				}

			} else if ( op === '!' || op === '~' ) {

				return builder.format( `(${op}${a})`, typeA, output );

			} else if ( fnOpSnippet ) {

				return builder.format( `${ fnOpSnippet }( ${ a }, ${ b } )`, type, output );

			} else {

				// Handle matrix operations

				if ( builder.isMatrix( typeA ) && typeB === 'float' ) {

					return builder.format( `( ${ b } ${ op } ${ a } )`, type, output );

				} else if ( typeA === 'float' && builder.isMatrix( typeB ) ) {

					return builder.format( `${ a } ${ op } ${ b }`, type, output );

				} else {

					let snippet = `( ${ a } ${ op } ${ b } )`;

					if ( ! isGLSL && type === 'bool' && builder.isVector( typeA ) && builder.isVector( typeB ) ) {

						snippet = `all${ snippet }`;

					}

					return builder.format( snippet, type, output );

				}

			}

		} else if ( typeA !== 'void' ) {

			if ( fnOpSnippet ) {

				return builder.format( `${ fnOpSnippet }( ${ a }, ${ b } )`, type, output );

			} else {

				if ( builder.isMatrix( typeA ) && typeB === 'float' ) {

					return builder.format( `${ b } ${ op } ${ a }`, type, output );

				} else {

					return builder.format( `${ a } ${ op } ${ b }`, type, output );

				}

			}

		}

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		data.op = this.op;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		this.op = data.op;

	}
```
</details>


---