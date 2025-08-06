[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `FunctionNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/code/FunctionNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `CodeNode` | `./CodeNode.js` |
| `nodeObject` | `../tsl/TSLBase.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `nodeFunction` | `any` | let/var | `nodeData.nodeFunction` | ✗ |
| `name` | `any` | let/var | `nodeFunction.name` | ✗ |
| `type` | `any` | let/var | `nodeFunction.type` | ✗ |
| `include` | `any` | let/var | `includes[ i ]` | ✗ |


---

## Functions

### `FunctionNode.getNodeType(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this.getNodeFunction`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return this.getNodeFunction( builder ).type;

	}
```
</details>

### `FunctionNode.getInputs(builder: NodeBuilder): NodeFunctionInput[]`

**JSDoc:**
```typescript
/**
	 * Returns the inputs of this function node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Array<NodeFunctionInput>} The inputs.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `NodeFunctionInput[]`

**Calls:**

- `this.getNodeFunction`

<details><summary>Code</summary>

```typescript
getInputs( builder ) {

		return this.getNodeFunction( builder ).inputs;

	}
```
</details>

### `FunctionNode.getNodeFunction(builder: NodeBuilder): NodeFunction`

**JSDoc:**
```typescript
/**
	 * Returns the node function for this function node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {NodeFunction} The node function.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `NodeFunction`

**Calls:**

- `builder.getDataFromNode`
- `builder.parser.parseFunction`

<details><summary>Code</summary>

```typescript
getNodeFunction( builder ) {

		const nodeData = builder.getDataFromNode( this );

		let nodeFunction = nodeData.nodeFunction;

		if ( nodeFunction === undefined ) {

			nodeFunction = builder.parser.parseFunction( this.code );

			nodeData.nodeFunction = nodeFunction;

		}

		return nodeFunction;

	}
```
</details>

### `FunctionNode.generate(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `super.generate`
- `this.getNodeFunction`
- `builder.getCodeFromNode`
- `builder.getPropertyName`
- `this.getNodeFunction( builder ).getCode`
- `builder.format`

**Internal Comments:**
```
// use a custom property name (x4)
```

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		super.generate( builder );

		const nodeFunction = this.getNodeFunction( builder );

		const name = nodeFunction.name;
		const type = nodeFunction.type;

		const nodeCode = builder.getCodeFromNode( this, type );

		if ( name !== '' ) {

			// use a custom property name

			nodeCode.name = name;

		}

		const propertyName = builder.getPropertyName( nodeCode );

		const code = this.getNodeFunction( builder ).getCode( propertyName );

		nodeCode.code = code + '\n';

		if ( output === 'property' ) {

			return propertyName;

		} else {

			return builder.format( `${ propertyName }()`, type, output );

		}

	}
```
</details>

### `nativeFn(code: any, includes: any[], language: string): { (...params: any[]): any; functionNode: any; }`

**Parameters:**

- **`code`** `any`
- **`includes`** `any[]`
- **`language`** `string`

**Returns:** `{ (...params: any[]): any; functionNode: any; }`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`
- `functionNode.call`

**Internal Comments:**
```
// TSL Function: glslFn, wgslFn
```

<details><summary>Code</summary>

```typescript
( code, includes = [], language = '' ) => {

	for ( let i = 0; i < includes.length; i ++ ) {

		const include = includes[ i ];

		// TSL Function: glslFn, wgslFn

		if ( typeof include === 'function' ) {

			includes[ i ] = include.functionNode;

		}

	}

	const functionNode = nodeObject( new FunctionNode( code, includes, language ) );

	const fn = ( ...params ) => functionNode.call( ...params );
	fn.functionNode = functionNode;

	return fn;

}
```
</details>

### `fn(params: any[]): any`

**Parameters:**

- **`params`** `any[]`

**Returns:** `any`

**Calls:**

- `functionNode.call`

<details><summary>Code</summary>

```typescript
( ...params ) => functionNode.call( ...params )
```
</details>

### `glslFn(code: any, includes: any): { (...params: any[]): any; functionNode: any; }`

**Parameters:**

- **`code`** `any`
- **`includes`** `any`

**Returns:** `{ (...params: any[]): any; functionNode: any; }`

**Calls:**

- `nativeFn`

<details><summary>Code</summary>

```typescript
( code, includes ) => nativeFn( code, includes, 'glsl' )
```
</details>

### `wgslFn(code: any, includes: any): { (...params: any[]): any; functionNode: any; }`

**Parameters:**

- **`code`** `any`
- **`includes`** `any`

**Returns:** `{ (...params: any[]): any; functionNode: any; }`

**Calls:**

- `nativeFn`

<details><summary>Code</summary>

```typescript
( code, includes ) => nativeFn( code, includes, 'wgsl' )
```
</details>


---

## Classes

### `FunctionNode`

<details><summary>Class Code</summary>

```ts
class FunctionNode extends CodeNode {

	static get type() {

		return 'FunctionNode';

	}

	/**
	 * Constructs a new function node.
	 *
	 * @param {string} [code=''] - The native code.
	 * @param {Array<Node>} [includes=[]] - An array of includes.
	 * @param {('js'|'wgsl'|'glsl')} [language=''] - The used language.
	 */
	constructor( code = '', includes = [], language = '' ) {

		super( code, includes, language );

	}

	getNodeType( builder ) {

		return this.getNodeFunction( builder ).type;

	}

	/**
	 * Returns the inputs of this function node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Array<NodeFunctionInput>} The inputs.
	 */
	getInputs( builder ) {

		return this.getNodeFunction( builder ).inputs;

	}

	/**
	 * Returns the node function for this function node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {NodeFunction} The node function.
	 */
	getNodeFunction( builder ) {

		const nodeData = builder.getDataFromNode( this );

		let nodeFunction = nodeData.nodeFunction;

		if ( nodeFunction === undefined ) {

			nodeFunction = builder.parser.parseFunction( this.code );

			nodeData.nodeFunction = nodeFunction;

		}

		return nodeFunction;

	}

	generate( builder, output ) {

		super.generate( builder );

		const nodeFunction = this.getNodeFunction( builder );

		const name = nodeFunction.name;
		const type = nodeFunction.type;

		const nodeCode = builder.getCodeFromNode( this, type );

		if ( name !== '' ) {

			// use a custom property name

			nodeCode.name = name;

		}

		const propertyName = builder.getPropertyName( nodeCode );

		const code = this.getNodeFunction( builder ).getCode( propertyName );

		nodeCode.code = code + '\n';

		if ( output === 'property' ) {

			return propertyName;

		} else {

			return builder.format( `${ propertyName }()`, type, output );

		}

	}

}
```
</details>

#### Methods

##### `getNodeType(builder: any): any`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return this.getNodeFunction( builder ).type;

	}
```
</details>

##### `getInputs(builder: NodeBuilder): NodeFunctionInput[]`

<details><summary>Code</summary>

```ts
getInputs( builder ) {

		return this.getNodeFunction( builder ).inputs;

	}
```
</details>

##### `getNodeFunction(builder: NodeBuilder): NodeFunction`

<details><summary>Code</summary>

```ts
getNodeFunction( builder ) {

		const nodeData = builder.getDataFromNode( this );

		let nodeFunction = nodeData.nodeFunction;

		if ( nodeFunction === undefined ) {

			nodeFunction = builder.parser.parseFunction( this.code );

			nodeData.nodeFunction = nodeFunction;

		}

		return nodeFunction;

	}
```
</details>

##### `generate(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		super.generate( builder );

		const nodeFunction = this.getNodeFunction( builder );

		const name = nodeFunction.name;
		const type = nodeFunction.type;

		const nodeCode = builder.getCodeFromNode( this, type );

		if ( name !== '' ) {

			// use a custom property name

			nodeCode.name = name;

		}

		const propertyName = builder.getPropertyName( nodeCode );

		const code = this.getNodeFunction( builder ).getCode( propertyName );

		nodeCode.code = code + '\n';

		if ( output === 'property' ) {

			return propertyName;

		} else {

			return builder.format( `${ propertyName }()`, type, output );

		}

	}
```
</details>


---