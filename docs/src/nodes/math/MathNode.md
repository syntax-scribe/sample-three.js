[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MathNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 15 |
| 🧱 Classes | 1 |
| 📦 Imports | 16 |
| 📊 Variables & Constants | 22 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/math/MathNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `../core/TempNode.js` |
| `sub` | `./OperatorNode.js` |
| `mul` | `./OperatorNode.js` |
| `div` | `./OperatorNode.js` |
| `mod` | `./OperatorNode.js` |
| `equal` | `./OperatorNode.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `nodeObject` | `../tsl/TSLCore.js` |
| `nodeProxyIntent` | `../tsl/TSLCore.js` |
| `float` | `../tsl/TSLCore.js` |
| `vec2` | `../tsl/TSLCore.js` |
| `vec3` | `../tsl/TSLCore.js` |
| `vec4` | `../tsl/TSLCore.js` |
| `Fn` | `../tsl/TSLCore.js` |
| `WebGLCoordinateSystem` | `../../constants.js` |
| `WebGPUCoordinateSystem` | `../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `finalOp` | `MathNode` | let/var | `new MathNode( method, aNode, bNode )` | ✗ |
| `bType` | `any` | let/var | `this.bNode ? this.bNode.getNodeType( builder ) : null` | ✗ |
| `cType` | `any` | let/var | `this.cNode ? this.cNode.getNodeType( builder ) : null` | ✗ |
| `aLen` | `any` | let/var | `builder.isMatrix( aType ) ? 0 : builder.getTypeLength( aType )` | ✗ |
| `bLen` | `any` | let/var | `builder.isMatrix( bType ) ? 0 : builder.getTypeLength( bType )` | ✗ |
| `cLen` | `any` | let/var | `builder.isMatrix( cType ) ? 0 : builder.getTypeLength( cType )` | ✗ |
| `method` | `string` | let/var | `this.method` | ✗ |
| `outputNode` | `any` | let/var | `null` | ✗ |
| `tA` | `Node` | let/var | `aNode` | ✗ |
| `tB` | `Node` | let/var | `bNode` | ✗ |
| `mulNode` | `any` | let/var | `mul( tA, tB ).xyz` | ✗ |
| `method` | `string` | let/var | `this.method` | ✗ |
| `a` | `Node` | let/var | `this.aNode` | ✗ |
| `b` | `Node` | let/var | `this.bNode` | ✗ |
| `c` | `Node` | let/var | `this.cNode` | ✗ |
| `coordinateSystem` | `any` | let/var | `builder.renderer.coordinateSystem` | ✗ |
| `params` | `any[]` | let/var | `[]` | ✗ |
| `a` | `12.9898` | let/var | `12.9898` | ✗ |
| `b` | `78.233` | let/var | `78.233` | ✗ |
| `c` | `43758.5453` | let/var | `43758.5453` | ✗ |
| `faceforward` | `any` | let/var | `faceForward` | ✓ |
| `inversesqrt` | `any` | let/var | `inverseSqrt` | ✓ |


---

## Functions

### `MathNode.getInputType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * The input type is inferred from the node types of the input nodes.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.aNode.getNodeType`
- `this.bNode.getNodeType`
- `this.cNode.getNodeType`
- `builder.isMatrix`
- `builder.getTypeLength`

<details><summary>Code</summary>

```typescript
getInputType( builder ) {

		const aType = this.aNode.getNodeType( builder );
		const bType = this.bNode ? this.bNode.getNodeType( builder ) : null;
		const cType = this.cNode ? this.cNode.getNodeType( builder ) : null;

		const aLen = builder.isMatrix( aType ) ? 0 : builder.getTypeLength( aType );
		const bLen = builder.isMatrix( bType ) ? 0 : builder.getTypeLength( bType );
		const cLen = builder.isMatrix( cType ) ? 0 : builder.getTypeLength( cType );

		if ( aLen > bLen && aLen > cLen ) {

			return aType;

		} else if ( bLen > cLen ) {

			return bType;

		} else if ( cLen > aLen ) {

			return cType;

		}

		return aType;

	}
```
</details>

### `MathNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * The selected method as well as the input type determine the node type of this node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `builder.changeComponentType`
- `this.aNode.getNodeType`
- `this.getInputType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		const method = this.method;

		if ( method === MathNode.LENGTH || method === MathNode.DISTANCE || method === MathNode.DOT ) {

			return 'float';

		} else if ( method === MathNode.CROSS ) {

			return 'vec3';

		} else if ( method === MathNode.ALL || method === MathNode.ANY ) {

			return 'bool';

		} else if ( method === MathNode.EQUALS ) {

			return builder.changeComponentType( this.aNode.getNodeType( builder ), 'bool' );

		} else {

			return this.getInputType( builder );

		}

	}
```
</details>

### `MathNode.setup(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `sub (from ./OperatorNode.js)`
- `div (from ./OperatorNode.js)`
- `abs`
- `builder.isMatrix`
- `tA.getNodeType`
- `vec4 (from ../tsl/TSLCore.js)`
- `vec3 (from ../tsl/TSLCore.js)`
- `mul (from ./OperatorNode.js)`
- `normalize`
- `super.setup`

**Internal Comments:**
```
// dir can be either a direction vector or a normal vector (x2)
// upper-left 3x3 of matrix is assumed to be orthogonal (x2)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const { aNode, bNode, method } = this;

		let outputNode = null;

		if ( method === MathNode.ONE_MINUS ) {

			outputNode = sub( 1.0, aNode );

		} else if ( method === MathNode.RECIPROCAL ) {

			outputNode = div( 1.0, aNode );

		} else if ( method === MathNode.DIFFERENCE ) {

			outputNode = abs( sub( aNode, bNode ) );

		} else if ( method === MathNode.TRANSFORM_DIRECTION ) {

			// dir can be either a direction vector or a normal vector
			// upper-left 3x3 of matrix is assumed to be orthogonal

			let tA = aNode;
			let tB = bNode;

			if ( builder.isMatrix( tA.getNodeType( builder ) ) ) {

				tB = vec4( vec3( tB ), 0.0 );

			} else {

				tA = vec4( vec3( tA ), 0.0 );

			}

			const mulNode = mul( tA, tB ).xyz;

			outputNode = normalize( mulNode );

		}

		if ( outputNode !== null ) {

			return outputNode;

		} else {

			return super.setup( builder );

		}

	}
```
</details>

### `MathNode.generate(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `builder.getNodeProperties`
- `super.generate`
- `this.getNodeType`
- `this.getInputType`
- `builder.format`
- `a.build`
- `params.push`
- `b.build`
- `builder.getTypeLength`
- `a.getNodeType`
- `b.getNodeType`
- `c.build`
- `c.getNodeType`
- `console.warn`
- `builder.getMethod`
- `params.join`

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		const properties = builder.getNodeProperties( this );

		if ( properties.outputNode ) {

			return super.generate( builder, output );

		}

		let method = this.method;

		const type = this.getNodeType( builder );
		const inputType = this.getInputType( builder );

		const a = this.aNode;
		const b = this.bNode;
		const c = this.cNode;

		const coordinateSystem = builder.renderer.coordinateSystem;

		if ( method === MathNode.NEGATE ) {

			return builder.format( '( - ' + a.build( builder, inputType ) + ' )', type, output );

		} else {

			const params = [];

			if ( method === MathNode.CROSS ) {

				params.push(
					a.build( builder, type ),
					b.build( builder, type )
				);

			} else if ( coordinateSystem === WebGLCoordinateSystem && method === MathNode.STEP ) {

				params.push(
					a.build( builder, builder.getTypeLength( a.getNodeType( builder ) ) === 1 ? 'float' : inputType ),
					b.build( builder, inputType )
				);

			} else if ( coordinateSystem === WebGLCoordinateSystem && ( method === MathNode.MIN || method === MathNode.MAX ) ) {

				params.push(
					a.build( builder, inputType ),
					b.build( builder, builder.getTypeLength( b.getNodeType( builder ) ) === 1 ? 'float' : inputType )
				);

			} else if ( method === MathNode.REFRACT ) {

				params.push(
					a.build( builder, inputType ),
					b.build( builder, inputType ),
					c.build( builder, 'float' )
				);

			} else if ( method === MathNode.MIX ) {

				params.push(
					a.build( builder, inputType ),
					b.build( builder, inputType ),
					c.build( builder, builder.getTypeLength( c.getNodeType( builder ) ) === 1 ? 'float' : inputType )
				);

			} else {

				if ( coordinateSystem === WebGPUCoordinateSystem && method === MathNode.ATAN && b !== null ) {

					method = 'atan2';

				}

				if ( builder.shaderStage !== 'fragment' && ( method === MathNode.DFDX || method === MathNode.DFDY ) ) {

					console.warn( `THREE.TSL: '${ method }' is not supported in the ${ builder.shaderStage } stage.` );

					method = '/*' + method + '*/';

				}

				params.push( a.build( builder, inputType ) );
				if ( b !== null ) params.push( b.build( builder, inputType ) );
				if ( c !== null ) params.push( c.build( builder, inputType ) );

			}

			return builder.format( `${ builder.getMethod( method, type ) }( ${params.join( ', ' )} )`, type, output );

		}

	}
```
</details>

### `MathNode.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		data.method = this.method;

	}
```
</details>

### `MathNode.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		this.method = data.method;

	}
```
</details>

### `equals(x: number | Node, y: number | Node): any`

**Parameters:**

- **`x`** `number | Node`
- **`y`** `number | Node`

**Returns:** `any`

**Calls:**

- `console.warn`
- `equal (from ./OperatorNode.js)`

<details><summary>Code</summary>

```typescript
( x, y ) => { // @deprecated, r172

	console.warn( 'THREE.TSL: "equals" is deprecated. Use "equal" inside a vector instead, like: "bvec*( equal( ... ) )"' );
	return equal( x, y );

}
```
</details>

### `cbrt(a: number | Node): Node`

**Parameters:**

- **`a`** `number | Node`

**Returns:** `Node`

**Calls:**

- `mul (from ./OperatorNode.js)`

<details><summary>Code</summary>

```typescript
( a ) => mul( sign( a ), pow( abs( a ), 1.0 / 3.0 ) )
```
</details>

### `lengthSq(a: any): any`

**Parameters:**

- **`a`** `any`

**Returns:** `any`

**Calls:**

- `dot`

<details><summary>Code</summary>

```typescript
( a ) => dot( a, a )
```
</details>

### `clamp(value: number | Node, low: number | Node, high: number | Node): Node`

**Parameters:**

- **`value`** `number | Node`
- **`low`** `number | Node`
- **`high`** `number | Node`

**Returns:** `Node`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( value, low = 0, high = 1 ) => nodeObject( new MathNode( MathNode.CLAMP, nodeObject( value ), nodeObject( low ), nodeObject( high ) ) )
```
</details>

### `saturate(value: number | Node): Node`

**Parameters:**

- **`value`** `number | Node`

**Returns:** `Node`

**Calls:**

- `clamp`

<details><summary>Code</summary>

```typescript
( value ) => clamp( value )
```
</details>

### `mixElement(t: number | Node, e1: number | Node, e2: number | Node): Node`

**Parameters:**

- **`t`** `number | Node`
- **`e1`** `number | Node`
- **`e2`** `number | Node`

**Returns:** `Node`

**Calls:**

- `mix`

<details><summary>Code</summary>

```typescript
( t, e1, e2 ) => mix( e1, e2, t )
```
</details>

### `smoothstepElement(x: number | Node, low: number | Node, high: number | Node): Node`

**Parameters:**

- **`x`** `number | Node`
- **`low`** `number | Node`
- **`high`** `number | Node`

**Returns:** `Node`

**Calls:**

- `smoothstep`

<details><summary>Code</summary>

```typescript
( x, low, high ) => smoothstep( low, high, x )
```
</details>

### `stepElement(x: number | Node, edge: number | Node): Node`

**Parameters:**

- **`x`** `number | Node`
- **`edge`** `number | Node`

**Returns:** `Node`

**Calls:**

- `step`

<details><summary>Code</summary>

```typescript
( x, edge ) => step( edge, x )
```
</details>

### `atan2(y: number | Node, x: number | Node): Node`

**Parameters:**

- **`y`** `number | Node`
- **`x`** `number | Node`

**Returns:** `Node`

**Calls:**

- `console.warn`
- `atan`

<details><summary>Code</summary>

```typescript
( y, x ) => { // @deprecated, r172

	console.warn( 'THREE.TSL: "atan2" is overloaded. Use "atan" instead.' );
	return atan( y, x );

}
```
</details>


---

## Classes

### `MathNode`

<details><summary>Class Code</summary>

```ts
class MathNode extends TempNode {

	static get type() {

		return 'MathNode';

	}

	/**
	 * Constructs a new math node.
	 *
	 * @param {string} method - The method name.
	 * @param {Node} aNode - The first input.
	 * @param {?Node} [bNode=null] - The second input.
	 * @param {?Node} [cNode=null] - The third input.
	 */
	constructor( method, aNode, bNode = null, cNode = null ) {

		super();

		// Allow the max() and min() functions to take an arbitrary number of arguments.

		if ( ( method === MathNode.MAX || method === MathNode.MIN ) && arguments.length > 3 ) {

			let finalOp = new MathNode( method, aNode, bNode );

			for ( let i = 2; i < arguments.length - 1; i ++ ) {

				finalOp = new MathNode( method, finalOp, arguments[ i ] );

			}

			aNode = finalOp;
			bNode = arguments[ arguments.length - 1 ];
			cNode = null;

		}

		/**
		 * The method name.
		 *
		 * @type {string}
		 */
		this.method = method;

		/**
		 * The first input.
		 *
		 * @type {Node}
		 */
		this.aNode = aNode;

		/**
		 * The second input.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.bNode = bNode;

		/**
		 * The third input.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.cNode = cNode;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isMathNode = true;

	}

	/**
	 * The input type is inferred from the node types of the input nodes.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
	getInputType( builder ) {

		const aType = this.aNode.getNodeType( builder );
		const bType = this.bNode ? this.bNode.getNodeType( builder ) : null;
		const cType = this.cNode ? this.cNode.getNodeType( builder ) : null;

		const aLen = builder.isMatrix( aType ) ? 0 : builder.getTypeLength( aType );
		const bLen = builder.isMatrix( bType ) ? 0 : builder.getTypeLength( bType );
		const cLen = builder.isMatrix( cType ) ? 0 : builder.getTypeLength( cType );

		if ( aLen > bLen && aLen > cLen ) {

			return aType;

		} else if ( bLen > cLen ) {

			return bType;

		} else if ( cLen > aLen ) {

			return cType;

		}

		return aType;

	}

	/**
	 * The selected method as well as the input type determine the node type of this node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( builder ) {

		const method = this.method;

		if ( method === MathNode.LENGTH || method === MathNode.DISTANCE || method === MathNode.DOT ) {

			return 'float';

		} else if ( method === MathNode.CROSS ) {

			return 'vec3';

		} else if ( method === MathNode.ALL || method === MathNode.ANY ) {

			return 'bool';

		} else if ( method === MathNode.EQUALS ) {

			return builder.changeComponentType( this.aNode.getNodeType( builder ), 'bool' );

		} else {

			return this.getInputType( builder );

		}

	}

	setup( builder ) {

		const { aNode, bNode, method } = this;

		let outputNode = null;

		if ( method === MathNode.ONE_MINUS ) {

			outputNode = sub( 1.0, aNode );

		} else if ( method === MathNode.RECIPROCAL ) {

			outputNode = div( 1.0, aNode );

		} else if ( method === MathNode.DIFFERENCE ) {

			outputNode = abs( sub( aNode, bNode ) );

		} else if ( method === MathNode.TRANSFORM_DIRECTION ) {

			// dir can be either a direction vector or a normal vector
			// upper-left 3x3 of matrix is assumed to be orthogonal

			let tA = aNode;
			let tB = bNode;

			if ( builder.isMatrix( tA.getNodeType( builder ) ) ) {

				tB = vec4( vec3( tB ), 0.0 );

			} else {

				tA = vec4( vec3( tA ), 0.0 );

			}

			const mulNode = mul( tA, tB ).xyz;

			outputNode = normalize( mulNode );

		}

		if ( outputNode !== null ) {

			return outputNode;

		} else {

			return super.setup( builder );

		}

	}

	generate( builder, output ) {

		const properties = builder.getNodeProperties( this );

		if ( properties.outputNode ) {

			return super.generate( builder, output );

		}

		let method = this.method;

		const type = this.getNodeType( builder );
		const inputType = this.getInputType( builder );

		const a = this.aNode;
		const b = this.bNode;
		const c = this.cNode;

		const coordinateSystem = builder.renderer.coordinateSystem;

		if ( method === MathNode.NEGATE ) {

			return builder.format( '( - ' + a.build( builder, inputType ) + ' )', type, output );

		} else {

			const params = [];

			if ( method === MathNode.CROSS ) {

				params.push(
					a.build( builder, type ),
					b.build( builder, type )
				);

			} else if ( coordinateSystem === WebGLCoordinateSystem && method === MathNode.STEP ) {

				params.push(
					a.build( builder, builder.getTypeLength( a.getNodeType( builder ) ) === 1 ? 'float' : inputType ),
					b.build( builder, inputType )
				);

			} else if ( coordinateSystem === WebGLCoordinateSystem && ( method === MathNode.MIN || method === MathNode.MAX ) ) {

				params.push(
					a.build( builder, inputType ),
					b.build( builder, builder.getTypeLength( b.getNodeType( builder ) ) === 1 ? 'float' : inputType )
				);

			} else if ( method === MathNode.REFRACT ) {

				params.push(
					a.build( builder, inputType ),
					b.build( builder, inputType ),
					c.build( builder, 'float' )
				);

			} else if ( method === MathNode.MIX ) {

				params.push(
					a.build( builder, inputType ),
					b.build( builder, inputType ),
					c.build( builder, builder.getTypeLength( c.getNodeType( builder ) ) === 1 ? 'float' : inputType )
				);

			} else {

				if ( coordinateSystem === WebGPUCoordinateSystem && method === MathNode.ATAN && b !== null ) {

					method = 'atan2';

				}

				if ( builder.shaderStage !== 'fragment' && ( method === MathNode.DFDX || method === MathNode.DFDY ) ) {

					console.warn( `THREE.TSL: '${ method }' is not supported in the ${ builder.shaderStage } stage.` );

					method = '/*' + method + '*/';

				}

				params.push( a.build( builder, inputType ) );
				if ( b !== null ) params.push( b.build( builder, inputType ) );
				if ( c !== null ) params.push( c.build( builder, inputType ) );

			}

			return builder.format( `${ builder.getMethod( method, type ) }( ${params.join( ', ' )} )`, type, output );

		}

	}

	serialize( data ) {

		super.serialize( data );

		data.method = this.method;

	}

	deserialize( data ) {

		super.deserialize( data );

		this.method = data.method;

	}

}
```
</details>

#### Methods

##### `getInputType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getInputType( builder ) {

		const aType = this.aNode.getNodeType( builder );
		const bType = this.bNode ? this.bNode.getNodeType( builder ) : null;
		const cType = this.cNode ? this.cNode.getNodeType( builder ) : null;

		const aLen = builder.isMatrix( aType ) ? 0 : builder.getTypeLength( aType );
		const bLen = builder.isMatrix( bType ) ? 0 : builder.getTypeLength( bType );
		const cLen = builder.isMatrix( cType ) ? 0 : builder.getTypeLength( cType );

		if ( aLen > bLen && aLen > cLen ) {

			return aType;

		} else if ( bLen > cLen ) {

			return bType;

		} else if ( cLen > aLen ) {

			return cType;

		}

		return aType;

	}
```
</details>

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		const method = this.method;

		if ( method === MathNode.LENGTH || method === MathNode.DISTANCE || method === MathNode.DOT ) {

			return 'float';

		} else if ( method === MathNode.CROSS ) {

			return 'vec3';

		} else if ( method === MathNode.ALL || method === MathNode.ANY ) {

			return 'bool';

		} else if ( method === MathNode.EQUALS ) {

			return builder.changeComponentType( this.aNode.getNodeType( builder ), 'bool' );

		} else {

			return this.getInputType( builder );

		}

	}
```
</details>

##### `setup(builder: any): any`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const { aNode, bNode, method } = this;

		let outputNode = null;

		if ( method === MathNode.ONE_MINUS ) {

			outputNode = sub( 1.0, aNode );

		} else if ( method === MathNode.RECIPROCAL ) {

			outputNode = div( 1.0, aNode );

		} else if ( method === MathNode.DIFFERENCE ) {

			outputNode = abs( sub( aNode, bNode ) );

		} else if ( method === MathNode.TRANSFORM_DIRECTION ) {

			// dir can be either a direction vector or a normal vector
			// upper-left 3x3 of matrix is assumed to be orthogonal

			let tA = aNode;
			let tB = bNode;

			if ( builder.isMatrix( tA.getNodeType( builder ) ) ) {

				tB = vec4( vec3( tB ), 0.0 );

			} else {

				tA = vec4( vec3( tA ), 0.0 );

			}

			const mulNode = mul( tA, tB ).xyz;

			outputNode = normalize( mulNode );

		}

		if ( outputNode !== null ) {

			return outputNode;

		} else {

			return super.setup( builder );

		}

	}
```
</details>

##### `generate(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		const properties = builder.getNodeProperties( this );

		if ( properties.outputNode ) {

			return super.generate( builder, output );

		}

		let method = this.method;

		const type = this.getNodeType( builder );
		const inputType = this.getInputType( builder );

		const a = this.aNode;
		const b = this.bNode;
		const c = this.cNode;

		const coordinateSystem = builder.renderer.coordinateSystem;

		if ( method === MathNode.NEGATE ) {

			return builder.format( '( - ' + a.build( builder, inputType ) + ' )', type, output );

		} else {

			const params = [];

			if ( method === MathNode.CROSS ) {

				params.push(
					a.build( builder, type ),
					b.build( builder, type )
				);

			} else if ( coordinateSystem === WebGLCoordinateSystem && method === MathNode.STEP ) {

				params.push(
					a.build( builder, builder.getTypeLength( a.getNodeType( builder ) ) === 1 ? 'float' : inputType ),
					b.build( builder, inputType )
				);

			} else if ( coordinateSystem === WebGLCoordinateSystem && ( method === MathNode.MIN || method === MathNode.MAX ) ) {

				params.push(
					a.build( builder, inputType ),
					b.build( builder, builder.getTypeLength( b.getNodeType( builder ) ) === 1 ? 'float' : inputType )
				);

			} else if ( method === MathNode.REFRACT ) {

				params.push(
					a.build( builder, inputType ),
					b.build( builder, inputType ),
					c.build( builder, 'float' )
				);

			} else if ( method === MathNode.MIX ) {

				params.push(
					a.build( builder, inputType ),
					b.build( builder, inputType ),
					c.build( builder, builder.getTypeLength( c.getNodeType( builder ) ) === 1 ? 'float' : inputType )
				);

			} else {

				if ( coordinateSystem === WebGPUCoordinateSystem && method === MathNode.ATAN && b !== null ) {

					method = 'atan2';

				}

				if ( builder.shaderStage !== 'fragment' && ( method === MathNode.DFDX || method === MathNode.DFDY ) ) {

					console.warn( `THREE.TSL: '${ method }' is not supported in the ${ builder.shaderStage } stage.` );

					method = '/*' + method + '*/';

				}

				params.push( a.build( builder, inputType ) );
				if ( b !== null ) params.push( b.build( builder, inputType ) );
				if ( c !== null ) params.push( c.build( builder, inputType ) );

			}

			return builder.format( `${ builder.getMethod( method, type ) }( ${params.join( ', ' )} )`, type, output );

		}

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		data.method = this.method;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		this.method = data.method;

	}
```
</details>


---