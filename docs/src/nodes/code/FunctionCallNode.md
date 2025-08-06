[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `FunctionCallNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/code/FunctionCallNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `../core/TempNode.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `nodeArray` | `../tsl/TSLCore.js` |
| `nodeObject` | `../tsl/TSLCore.js` |
| `nodeObjects` | `../tsl/TSLCore.js` |
| `float` | `../tsl/TSLCore.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `params` | `any[]` | let/var | `[]` | ✗ |
| `functionNode` | `FunctionNode` | let/var | `this.functionNode` | ✗ |
| `parameters` | `{ [x: string]: Node; }` | let/var | `this.parameters` | ✗ |
| `type` | `any` | let/var | `inputNode.type` | ✗ |
| `pointer` | `boolean` | let/var | `type === 'pointer'` | ✗ |
| `output` | `any` | let/var | `*not shown*` | ✗ |
| `node` | `Node` | let/var | `parameters[ inputNode.name ]` | ✗ |


---

## Functions

### `FunctionCallNode.setParameters(parameters: { [x: string]: Node; }): FunctionCallNode`

**JSDoc:**
```typescript
/**
	 * Sets the parameters of the function call node.
	 *
	 * @param {Object<string, Node>} parameters - The parameters to set.
	 * @return {FunctionCallNode} A reference to this node.
	 */
```

**Parameters:**

- **`parameters`** `{ [x: string]: Node; }`

**Returns:** `FunctionCallNode`

<details><summary>Code</summary>

```typescript
setParameters( parameters ) {

		this.parameters = parameters;

		return this;

	}
```
</details>

### `FunctionCallNode.getParameters(): { [x: string]: Node; }`

**JSDoc:**
```typescript
/**
	 * Returns the parameters of the function call node.
	 *
	 * @return {Object<string, Node>} The parameters of this node.
	 */
```

**Returns:** `{ [x: string]: Node; }`

<details><summary>Code</summary>

```typescript
getParameters() {

		return this.parameters;

	}
```
</details>

### `FunctionCallNode.getNodeType(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this.functionNode.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return this.functionNode.getNodeType( builder );

	}
```
</details>

### `FunctionCallNode.generate(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `functionNode.getInputs`
- `node.build`
- `Array.isArray`
- `console.error`
- `parameters.push`
- `float (from ../tsl/TSLCore.js)`
- `params.push`
- `generateInput`
- `functionNode.build`
- `params.join`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const params = [];

		const functionNode = this.functionNode;

		const inputs = functionNode.getInputs( builder );
		const parameters = this.parameters;

		const generateInput = ( node, inputNode ) => {

			const type = inputNode.type;
			const pointer = type === 'pointer';

			let output;

			if ( pointer ) output = '&' + node.build( builder );
			else output = node.build( builder, type );

			return output;

		};

		if ( Array.isArray( parameters ) ) {

			if ( parameters.length > inputs.length ) {

				console.error( 'THREE.TSL: The number of provided parameters exceeds the expected number of inputs in \'Fn()\'.' );

				parameters.length = inputs.length;

			} else if ( parameters.length < inputs.length ) {

				console.error( 'THREE.TSL: The number of provided parameters is less than the expected number of inputs in \'Fn()\'.' );

				while ( parameters.length < inputs.length ) {

					parameters.push( float( 0 ) );

				}

			}

			for ( let i = 0; i < parameters.length; i ++ ) {

				params.push( generateInput( parameters[ i ], inputs[ i ] ) );

			}

		} else {

			for ( const inputNode of inputs ) {

				const node = parameters[ inputNode.name ];

				if ( node !== undefined ) {

					params.push( generateInput( node, inputNode ) );

				} else {

					console.error( `THREE.TSL: Input '${ inputNode.name }' not found in \'Fn()\'.` );

					params.push( generateInput( float( 0 ), inputNode ) );

				}

			}

		}

		const functionName = functionNode.build( builder, 'property' );

		return `${ functionName }( ${ params.join( ', ' ) } )`;

	}
```
</details>

### `generateInput(node: any, inputNode: any): any`

**Parameters:**

- **`node`** `any`
- **`inputNode`** `any`

**Returns:** `any`

**Calls:**

- `node.build`

<details><summary>Code</summary>

```typescript
( node, inputNode ) => {

			const type = inputNode.type;
			const pointer = type === 'pointer';

			let output;

			if ( pointer ) output = '&' + node.build( builder );
			else output = node.build( builder, type );

			return output;

		}
```
</details>

### `call(func: any, params: any[]): any`

**Parameters:**

- **`func`** `any`
- **`params`** `any[]`

**Returns:** `any`

**Calls:**

- `nodeArray (from ../tsl/TSLCore.js)`
- `nodeObjects (from ../tsl/TSLCore.js)`
- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( func, ...params ) => {

	params = params.length > 1 || ( params[ 0 ] && params[ 0 ].isNode === true ) ? nodeArray( params ) : nodeObjects( params[ 0 ] );

	return nodeObject( new FunctionCallNode( nodeObject( func ), params ) );

}
```
</details>


---

## Classes

### `FunctionCallNode`

<details><summary>Class Code</summary>

```ts
class FunctionCallNode extends TempNode {

	static get type() {

		return 'FunctionCallNode';

	}

	/**
	 * Constructs a new function call node.
	 *
	 * @param {?FunctionNode} functionNode - The function node.
	 * @param {Object<string, Node>} [parameters={}] - The parameters for the function call.
	 */
	constructor( functionNode = null, parameters = {} ) {

		super();

		/**
		 * The function node.
		 *
		 * @type {?FunctionNode}
		 * @default null
		 */
		this.functionNode = functionNode;

		/**
		 * The parameters of the function call.
		 *
		 * @type {Object<string, Node>}
		 * @default {}
		 */
		this.parameters = parameters;

	}

	/**
	 * Sets the parameters of the function call node.
	 *
	 * @param {Object<string, Node>} parameters - The parameters to set.
	 * @return {FunctionCallNode} A reference to this node.
	 */
	setParameters( parameters ) {

		this.parameters = parameters;

		return this;

	}

	/**
	 * Returns the parameters of the function call node.
	 *
	 * @return {Object<string, Node>} The parameters of this node.
	 */
	getParameters() {

		return this.parameters;

	}

	getNodeType( builder ) {

		return this.functionNode.getNodeType( builder );

	}

	generate( builder ) {

		const params = [];

		const functionNode = this.functionNode;

		const inputs = functionNode.getInputs( builder );
		const parameters = this.parameters;

		const generateInput = ( node, inputNode ) => {

			const type = inputNode.type;
			const pointer = type === 'pointer';

			let output;

			if ( pointer ) output = '&' + node.build( builder );
			else output = node.build( builder, type );

			return output;

		};

		if ( Array.isArray( parameters ) ) {

			if ( parameters.length > inputs.length ) {

				console.error( 'THREE.TSL: The number of provided parameters exceeds the expected number of inputs in \'Fn()\'.' );

				parameters.length = inputs.length;

			} else if ( parameters.length < inputs.length ) {

				console.error( 'THREE.TSL: The number of provided parameters is less than the expected number of inputs in \'Fn()\'.' );

				while ( parameters.length < inputs.length ) {

					parameters.push( float( 0 ) );

				}

			}

			for ( let i = 0; i < parameters.length; i ++ ) {

				params.push( generateInput( parameters[ i ], inputs[ i ] ) );

			}

		} else {

			for ( const inputNode of inputs ) {

				const node = parameters[ inputNode.name ];

				if ( node !== undefined ) {

					params.push( generateInput( node, inputNode ) );

				} else {

					console.error( `THREE.TSL: Input '${ inputNode.name }' not found in \'Fn()\'.` );

					params.push( generateInput( float( 0 ), inputNode ) );

				}

			}

		}

		const functionName = functionNode.build( builder, 'property' );

		return `${ functionName }( ${ params.join( ', ' ) } )`;

	}

}
```
</details>

#### Methods

##### `setParameters(parameters: { [x: string]: Node; }): FunctionCallNode`

<details><summary>Code</summary>

```ts
setParameters( parameters ) {

		this.parameters = parameters;

		return this;

	}
```
</details>

##### `getParameters(): { [x: string]: Node; }`

<details><summary>Code</summary>

```ts
getParameters() {

		return this.parameters;

	}
```
</details>

##### `getNodeType(builder: any): any`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return this.functionNode.getNodeType( builder );

	}
```
</details>

##### `generate(builder: any): string`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const params = [];

		const functionNode = this.functionNode;

		const inputs = functionNode.getInputs( builder );
		const parameters = this.parameters;

		const generateInput = ( node, inputNode ) => {

			const type = inputNode.type;
			const pointer = type === 'pointer';

			let output;

			if ( pointer ) output = '&' + node.build( builder );
			else output = node.build( builder, type );

			return output;

		};

		if ( Array.isArray( parameters ) ) {

			if ( parameters.length > inputs.length ) {

				console.error( 'THREE.TSL: The number of provided parameters exceeds the expected number of inputs in \'Fn()\'.' );

				parameters.length = inputs.length;

			} else if ( parameters.length < inputs.length ) {

				console.error( 'THREE.TSL: The number of provided parameters is less than the expected number of inputs in \'Fn()\'.' );

				while ( parameters.length < inputs.length ) {

					parameters.push( float( 0 ) );

				}

			}

			for ( let i = 0; i < parameters.length; i ++ ) {

				params.push( generateInput( parameters[ i ], inputs[ i ] ) );

			}

		} else {

			for ( const inputNode of inputs ) {

				const node = parameters[ inputNode.name ];

				if ( node !== undefined ) {

					params.push( generateInput( node, inputNode ) );

				} else {

					console.error( `THREE.TSL: Input '${ inputNode.name }' not found in \'Fn()\'.` );

					params.push( generateInput( float( 0 ), inputNode ) );

				}

			}

		}

		const functionName = functionNode.build( builder, 'property' );

		return `${ functionName }( ${ params.join( ', ' ) } )`;

	}
```
</details>


---