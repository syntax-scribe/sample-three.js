[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ScriptableNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 32 |
| 🧱 Classes | 3 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 20 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/code/ScriptableNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `scriptableValue` | `./ScriptableValueNode.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `float` | `../tsl/TSLBase.js` |
| `hashArray` | `../core/NodeUtils.js` |
| `hashString` | `../core/NodeUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `param` | `any` | let/var | `this.parameters[ name ]` | ✗ |
| `value` | `any` | let/var | `param ? param.getValue() : null` | ✗ |
| `ScriptableNodeResources` | `Resources` | let/var | `new Resources()` | ✓ |
| `outputs` | `{}` | let/var | `this._outputs` | ✗ |
| `parameters` | `any` | let/var | `this.parameters` | ✗ |
| `valueNode` | `any` | let/var | `this.parameters[ name ]` | ✗ |
| `method` | `any` | let/var | `object[ name ]` | ✗ |
| `method` | `any` | let/var | `object[ name ]` | ✗ |
| `parameters` | `Parameters` | let/var | `new Parameters( this )` | ✗ |
| `params` | `any[]` | let/var | `[ parameters, this._local, ScriptableNodeResources, refresh, setOutput, THREE...` | ✗ |
| `layout` | `any` | let/var | `this._object.layout` | ✗ |
| `id` | `any` | let/var | `element.id \|\| element.name` | ✗ |
| `valueNode` | `any` | let/var | `this.parameters[ name ]` | ✗ |
| `output` | `any` | let/var | `this.getDefaultOutput().value` | ✗ |
| `parametersProps` | `string[]` | let/var | `[ 'parameters', 'local', 'global', 'refresh', 'setOutput', 'THREE', 'TSL' ]` | ✗ |
| `interfaceProps` | `string[]` | let/var | `[ 'layout', 'init', 'main', 'dispose' ]` | ✗ |
| `declarations` | `string` | let/var | `'var ' + properties + '; var output = {};\n'` | ✗ |
| `returns` | `string` | let/var | `'\nreturn { ...output, ' + properties + ' };'` | ✗ |
| `code` | `string` | let/var | `declarations + this.codeNode.code + returns` | ✗ |
| `values` | `number[]` | let/var | `[ hashString( this.source ), this.getDefaultOutputNode().getCacheKey( force ) ]` | ✗ |


---

## Functions

### `Resources.get(key: any, callback: any, params: any[]): any`

**Parameters:**

- **`key`** `any`
- **`callback`** `any`
- **`params`** `any[]`

**Returns:** `any`

**Calls:**

- `this.has`
- `super.get`
- `callback`
- `this.set`

<details><summary>Code</summary>

```typescript
get( key, callback = null, ...params ) {

		if ( this.has( key ) ) return super.get( key );

		if ( callback !== null ) {

			const value = callback( ...params );
			this.set( key, value );
			return value;

		}

	}
```
</details>

### `Parameters.getInputLayout(id: any): any`

**Parameters:**

- **`id`** `any`

**Returns:** `any`

**Calls:**

- `this.scriptableNode.getInputLayout`

<details><summary>Code</summary>

```typescript
getInputLayout( id ) {

		return this.scriptableNode.getInputLayout( id );

	}
```
</details>

### `Parameters.get(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `param.getValue`

<details><summary>Code</summary>

```typescript
get( name ) {

		const param = this.parameters[ name ];
		const value = param ? param.getValue() : null;

		return value;

	}
```
</details>

### `ScriptableNode.setLocal(name: string, value: any): Resources`

**JSDoc:**
```typescript
/**
	 * Sets the reference of a local script variable.
	 *
	 * @param {string} name - The variable name.
	 * @param {Object} value - The reference to set.
	 * @return {Resources} The resource map
	 */
```

**Parameters:**

- **`name`** `string`
- **`value`** `any`

**Returns:** `Resources`

**Calls:**

- `this._local.set`

<details><summary>Code</summary>

```typescript
setLocal( name, value ) {

		return this._local.set( name, value );

	}
```
</details>

### `ScriptableNode.getLocal(name: string): any`

**JSDoc:**
```typescript
/**
	 * Gets the value of a local script variable.
	 *
	 * @param {string} name - The variable name.
	 * @return {Object} The value.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `any`

**Calls:**

- `this._local.get`

<details><summary>Code</summary>

```typescript
getLocal( name ) {

		return this._local.get( name );

	}
```
</details>

### `ScriptableNode.onRefresh(): void`

**JSDoc:**
```typescript
/**
	 * Event listener for the `refresh` event.
	 */
```

**Returns:** `void`

**Calls:**

- `this._refresh`

<details><summary>Code</summary>

```typescript
onRefresh() {

		this._refresh();

	}
```
</details>

### `ScriptableNode.getInputLayout(id: string): any`

**JSDoc:**
```typescript
/**
	 * Returns an input from the layout with the given id/name.
	 *
	 * @param {string} id - The id/name of the input.
	 * @return {Object} The element entry.
	 */
```

**Parameters:**

- **`id`** `string`

**Returns:** `any`

**Calls:**

- `this.getLayout`

<details><summary>Code</summary>

```typescript
getInputLayout( id ) {

		for ( const element of this.getLayout() ) {

			if ( element.inputType && ( element.id === id || element.name === id ) ) {

				return element;

			}

		}

	}
```
</details>

### `ScriptableNode.getOutputLayout(id: string): any`

**JSDoc:**
```typescript
/**
	 * Returns an output from the layout with the given id/name.
	 *
	 * @param {string} id - The id/name of the output.
	 * @return {Object} The element entry.
	 */
```

**Parameters:**

- **`id`** `string`

**Returns:** `any`

**Calls:**

- `this.getLayout`

<details><summary>Code</summary>

```typescript
getOutputLayout( id ) {

		for ( const element of this.getLayout() ) {

			if ( element.outputType && ( element.id === id || element.name === id ) ) {

				return element;

			}

		}

	}
```
</details>

### `ScriptableNode.setOutput(name: string, value: Node): ScriptableNode`

**JSDoc:**
```typescript
/**
	 * Defines a script output for the given name and value.
	 *
	 * @param {string} name - The name of the output.
	 * @param {Node} value - The node value.
	 * @return {ScriptableNode} A reference to this node.
	 */
```

**Parameters:**

- **`name`** `string`
- **`value`** `Node`

**Returns:** `ScriptableNode`

**Calls:**

- `scriptableValue (from ./ScriptableValueNode.js)`

<details><summary>Code</summary>

```typescript
setOutput( name, value ) {

		const outputs = this._outputs;

		if ( outputs[ name ] === undefined ) {

			outputs[ name ] = scriptableValue( value );

		} else {

			outputs[ name ].value = value;

		}

		return this;

	}
```
</details>

### `ScriptableNode.getOutput(name: string): ScriptableValueNode`

**JSDoc:**
```typescript
/**
	 * Returns a script output for the given name.
	 *
	 * @param {string} name - The name of the output.
	 * @return {ScriptableValueNode} The node value.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `ScriptableValueNode`

<details><summary>Code</summary>

```typescript
getOutput( name ) {

		return this._outputs[ name ];

	}
```
</details>

### `ScriptableNode.getParameter(name: string): ScriptableValueNode`

**JSDoc:**
```typescript
/**
	 * Returns a parameter for the given name
	 *
	 * @param {string} name - The name of the parameter.
	 * @return {ScriptableValueNode} The node value.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `ScriptableValueNode`

<details><summary>Code</summary>

```typescript
getParameter( name ) {

		return this.parameters[ name ];

	}
```
</details>

### `ScriptableNode.setParameter(name: string, value: any): ScriptableNode`

**JSDoc:**
```typescript
/**
	 * Sets a value for the given parameter name.
	 *
	 * @param {string} name - The parameter name.
	 * @param {any} value - The parameter value.
	 * @return {ScriptableNode} A reference to this node.
	 */
```

**Parameters:**

- **`name`** `string`
- **`value`** `any`

**Returns:** `ScriptableNode`

**Calls:**

- `this.deleteParameter`
- `parameters[ name ].getDefaultOutput().events.addEventListener`
- `parameters[ name ].events.addEventListener`
- `scriptableValue (from ./ScriptableValueNode.js)`

<details><summary>Code</summary>

```typescript
setParameter( name, value ) {

		const parameters = this.parameters;

		if ( value && value.isScriptableNode ) {

			this.deleteParameter( name );

			parameters[ name ] = value;
			parameters[ name ].getDefaultOutput().events.addEventListener( 'refresh', this.onRefresh );

		} else if ( value && value.isScriptableValueNode ) {

			this.deleteParameter( name );

			parameters[ name ] = value;
			parameters[ name ].events.addEventListener( 'refresh', this.onRefresh );

		} else if ( parameters[ name ] === undefined ) {

			parameters[ name ] = scriptableValue( value );
			parameters[ name ].events.addEventListener( 'refresh', this.onRefresh );

		} else {

			parameters[ name ].value = value;

		}

		return this;

	}
```
</details>

### `ScriptableNode.getValue(): Node`

**JSDoc:**
```typescript
/**
	 * Returns the value of this node which is the value of
	 * the default output.
	 *
	 * @return {Node} The value.
	 */
```

**Returns:** `Node`

**Calls:**

- `this.getDefaultOutput().getValue`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.getDefaultOutput().getValue();

	}
```
</details>

### `ScriptableNode.deleteParameter(name: string): ScriptableNode`

**JSDoc:**
```typescript
/**
	 * Deletes a parameter from the script.
	 *
	 * @param {string} name - The parameter to remove.
	 * @return {ScriptableNode} A reference to this node.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `ScriptableNode`

**Calls:**

- `valueNode.getDefaultOutput`
- `valueNode.events.removeEventListener`

<details><summary>Code</summary>

```typescript
deleteParameter( name ) {

		let valueNode = this.parameters[ name ];

		if ( valueNode ) {

			if ( valueNode.isScriptableNode ) valueNode = valueNode.getDefaultOutput();

			valueNode.events.removeEventListener( 'refresh', this.onRefresh );

		}

		return this;

	}
```
</details>

### `ScriptableNode.clearParameters(): ScriptableNode`

**JSDoc:**
```typescript
/**
	 * Deletes all parameters from the script.
	 *
	 * @return {ScriptableNode} A reference to this node.
	 */
```

**Returns:** `ScriptableNode`

**Calls:**

- `Object.keys`
- `this.deleteParameter`

<details><summary>Code</summary>

```typescript
clearParameters() {

		for ( const name of Object.keys( this.parameters ) ) {

			this.deleteParameter( name );

		}

		this.needsUpdate = true;

		return this;

	}
```
</details>

### `ScriptableNode.call(name: string, params: any[]): any`

**JSDoc:**
```typescript
/**
	 * Calls a function from the script.
	 *
	 * @param {string} name - The function name.
	 * @param {...any} params - A list of parameters.
	 * @return {any} The result of the function call.
	 */
```

**Parameters:**

- **`name`** `string`
- **`params`** `any[]`

**Returns:** `any`

**Calls:**

- `this.getObject`
- `method`

<details><summary>Code</summary>

```typescript
call( name, ...params ) {

		const object = this.getObject();
		const method = object[ name ];

		if ( typeof method === 'function' ) {

			return method( ...params );

		}

	}
```
</details>

### `ScriptableNode.callAsync(name: string, params: any[]): Promise<any>`

**JSDoc:**
```typescript
/**
	 * Asynchronously calls a function from the script.
	 *
	 * @param {string} name - The function name.
	 * @param {...any} params - A list of parameters.
	 * @return {Promise<any>} The result of the function call.
	 */
```

**Parameters:**

- **`name`** `string`
- **`params`** `any[]`

**Returns:** `Promise<any>`

**Calls:**

- `this.getObject`
- `method`

<details><summary>Code</summary>

```typescript
async callAsync( name, ...params ) {

		const object = this.getObject();
		const method = object[ name ];

		if ( typeof method === 'function' ) {

			return method.constructor.name === 'AsyncFunction' ? await method( ...params ) : method( ...params );

		}

	}
```
</details>

### `ScriptableNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * Overwritten since the node types is inferred from the script's output.
	 *
	 * @param {NodeBuilder} builder - The current node builder
	 * @return {string} The node type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.getDefaultOutputNode().getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return this.getDefaultOutputNode().getNodeType( builder );

	}
```
</details>

### `ScriptableNode.refresh(output: string): void`

**JSDoc:**
```typescript
/**
	 * Refreshes the script node.
	 *
	 * @param {?string} [output=null] - An optional output.
	 */
```

**Parameters:**

- **`output`** `string`

**Returns:** `void`

**Calls:**

- `this.getOutput( output ).refresh`
- `this._refresh`

<details><summary>Code</summary>

```typescript
refresh( output = null ) {

		if ( output !== null ) {

			this.getOutput( output ).refresh();

		} else {

			this._refresh();

		}

	}
```
</details>

### `ScriptableNode.getObject(): any`

**JSDoc:**
```typescript
/**
	 * Returns an object representation of the script.
	 *
	 * @return {Object} The result object.
	 */
```

**Returns:** `any`

**Calls:**

- `this.dispose`
- `this.refresh`
- `this.setOutput`
- `ScriptableNodeResources.get`
- `this.getMethod`
- `method`
- `this._local.clear`
- `Array.isArray`
- `this.getParameter`
- `this.setParameter`
- `this.getOutput`

**Internal Comments:**
```
// (x2)
// default output (x5)
```

<details><summary>Code</summary>

```typescript
getObject() {

		if ( this.needsUpdate ) this.dispose();
		if ( this._object !== null ) return this._object;

		//

		const refresh = () => this.refresh();
		const setOutput = ( id, value ) => this.setOutput( id, value );

		const parameters = new Parameters( this );

		const THREE = ScriptableNodeResources.get( 'THREE' );
		const TSL = ScriptableNodeResources.get( 'TSL' );

		const method = this.getMethod();
		const params = [ parameters, this._local, ScriptableNodeResources, refresh, setOutput, THREE, TSL ];

		this._object = method( ...params );

		const layout = this._object.layout;

		if ( layout ) {

			if ( layout.cache === false ) {

				this._local.clear();

			}

			// default output
			this._output.outputType = layout.outputType || null;

			if ( Array.isArray( layout.elements ) ) {

				for ( const element of layout.elements ) {

					const id = element.id || element.name;

					if ( element.inputType ) {

						if ( this.getParameter( id ) === undefined ) this.setParameter( id, null );

						this.getParameter( id ).inputType = element.inputType;

					}

					if ( element.outputType ) {

						if ( this.getOutput( id ) === undefined ) this.setOutput( id, null );

						this.getOutput( id ).outputType = element.outputType;

					}

				}

			}

		}

		return this._object;

	}
```
</details>

### `ScriptableNode.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`
- `valueNode.getDefaultOutput`
- `valueNode.events.addEventListener`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		for ( const name in this.parameters ) {

			let valueNode = this.parameters[ name ];

			if ( valueNode.isScriptableNode ) valueNode = valueNode.getDefaultOutput();

			valueNode.events.addEventListener( 'refresh', this.onRefresh );

		}

	}
```
</details>

### `ScriptableNode.getLayout(): any`

**JSDoc:**
```typescript
/**
	 * Returns the layout of the script.
	 *
	 * @return {Object} The script's layout.
	 */
```

**Returns:** `any`

**Calls:**

- `this.getObject`

<details><summary>Code</summary>

```typescript
getLayout() {

		return this.getObject().layout;

	}
```
</details>

### `ScriptableNode.getDefaultOutputNode(): Node`

**JSDoc:**
```typescript
/**
	 * Returns default node output of the script.
	 *
	 * @return {Node} The default node output.
	 */
```

**Returns:** `Node`

**Calls:**

- `this.getDefaultOutput`
- `float (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
getDefaultOutputNode() {

		const output = this.getDefaultOutput().value;

		if ( output && output.isNode ) {

			return output;

		}

		return float();

	}
```
</details>

### `ScriptableNode.getDefaultOutput(): ScriptableValueNode`

**JSDoc:**
```typescript
/**
	 * Returns default output of the script.
	 *
	 * @return {ScriptableValueNode} The default output.
	 */
```

**Returns:** `ScriptableValueNode`

**Calls:**

- `this._exec`

<details><summary>Code</summary>

```typescript
getDefaultOutput()	{

		return this._exec()._output;

	}
```
</details>

### `ScriptableNode.getMethod(): Function`

**JSDoc:**
```typescript
/**
	 * Returns a function created from the node's script.
	 *
	 * @return {Function} The function representing the node's code.
	 */
```

**Returns:** `Function`

**Calls:**

- `this.dispose`
- `interfaceProps.join`

**Internal Comments:**
```
// (x6)
```

<details><summary>Code</summary>

```typescript
getMethod() {

		if ( this.needsUpdate ) this.dispose();
		if ( this._method !== null ) return this._method;

		//

		const parametersProps = [ 'parameters', 'local', 'global', 'refresh', 'setOutput', 'THREE', 'TSL' ];
		const interfaceProps = [ 'layout', 'init', 'main', 'dispose' ];

		const properties = interfaceProps.join( ', ' );
		const declarations = 'var ' + properties + '; var output = {};\n';
		const returns = '\nreturn { ...output, ' + properties + ' };';

		const code = declarations + this.codeNode.code + returns;

		//

		this._method = new Function( ...parametersProps, code );

		return this._method;

	}
```
</details>

### `ScriptableNode.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees all internal resources.
	 */
```

**Returns:** `void`

**Calls:**

- `this._object.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		if ( this._method === null ) return;

		if ( this._object && typeof this._object.dispose === 'function' ) {

			this._object.dispose();

		}

		this._method = null;
		this._object = null;
		this._source = null;
		this._value = null;
		this._needsOutputUpdate = true;
		this._output.value = null;
		this._outputs = {};

	}
```
</details>

### `ScriptableNode.setup(): Node`

**Returns:** `Node`

**Calls:**

- `this.getDefaultOutputNode`

<details><summary>Code</summary>

```typescript
setup() {

		return this.getDefaultOutputNode();

	}
```
</details>

### `ScriptableNode.getCacheKey(force: any): number`

**Parameters:**

- **`force`** `any`

**Returns:** `number`

**Calls:**

- `hashString (from ../core/NodeUtils.js)`
- `this.getDefaultOutputNode().getCacheKey`
- `values.push`
- `this.parameters[ param ].getCacheKey`
- `hashArray (from ../core/NodeUtils.js)`

<details><summary>Code</summary>

```typescript
getCacheKey( force ) {

		const values = [ hashString( this.source ), this.getDefaultOutputNode().getCacheKey( force ) ];

		for ( const param in this.parameters ) {

			values.push( this.parameters[ param ].getCacheKey( force ) );

		}

		return hashArray( values );

	}
```
</details>

### `ScriptableNode._exec(): ScriptableNode`

**JSDoc:**
```typescript
/**
	 * Executes the `main` function of the script.
	 *
	 * @private
	 * @return {ScriptableNode} A reference to this node.
	 */
```

**Returns:** `ScriptableNode`

**Calls:**

- `this.call`

<details><summary>Code</summary>

```typescript
_exec()	{

		if ( this.codeNode === null ) return this;

		if ( this._needsOutputUpdate === true ) {

			this._value = this.call( 'main' );

			this._needsOutputUpdate = false;

		}

		this._output.value = this._value;

		return this;

	}
```
</details>

### `ScriptableNode._refresh(): void`

**JSDoc:**
```typescript
/**
	 * Executes the refresh.
	 *
	 * @private
	 */
```

**Returns:** `void`

**Calls:**

- `this._exec`
- `this._output.refresh`

<details><summary>Code</summary>

```typescript
_refresh() {

		this.needsUpdate = true;

		this._exec();

		this._output.refresh();

	}
```
</details>

### `refresh(): void`

**Returns:** `void`

**Calls:**

- `this.refresh`

<details><summary>Code</summary>

```typescript
() => this.refresh()
```
</details>

### `setOutput(id: any, value: any): ScriptableNode`

**Parameters:**

- **`id`** `any`
- **`value`** `any`

**Returns:** `ScriptableNode`

**Calls:**

- `this.setOutput`

<details><summary>Code</summary>

```typescript
( id, value ) => this.setOutput( id, value )
```
</details>


---

## Classes

### `Resources`

<details><summary>Class Code</summary>

```ts
class Resources extends Map {

	get( key, callback = null, ...params ) {

		if ( this.has( key ) ) return super.get( key );

		if ( callback !== null ) {

			const value = callback( ...params );
			this.set( key, value );
			return value;

		}

	}

}
```
</details>

#### Methods

##### `get(key: any, callback: any, params: any[]): any`

<details><summary>Code</summary>

```ts
get( key, callback = null, ...params ) {

		if ( this.has( key ) ) return super.get( key );

		if ( callback !== null ) {

			const value = callback( ...params );
			this.set( key, value );
			return value;

		}

	}
```
</details>

### `Parameters`

<details><summary>Class Code</summary>

```ts
class Parameters {

	constructor( scriptableNode ) {

		this.scriptableNode = scriptableNode;

	}

	get parameters() {

		return this.scriptableNode.parameters;

	}

	get layout() {

		return this.scriptableNode.getLayout();

	}

	getInputLayout( id ) {

		return this.scriptableNode.getInputLayout( id );

	}

	get( name ) {

		const param = this.parameters[ name ];
		const value = param ? param.getValue() : null;

		return value;

	}

}
```
</details>

#### Methods

##### `getInputLayout(id: any): any`

<details><summary>Code</summary>

```ts
getInputLayout( id ) {

		return this.scriptableNode.getInputLayout( id );

	}
```
</details>

##### `get(name: any): any`

<details><summary>Code</summary>

```ts
get( name ) {

		const param = this.parameters[ name ];
		const value = param ? param.getValue() : null;

		return value;

	}
```
</details>

### `ScriptableNode`

<details><summary>Class Code</summary>

```ts
class ScriptableNode extends Node {

	static get type() {

		return 'ScriptableNode';

	}

	/**
	 * Constructs a new scriptable node.
	 *
	 * @param {?CodeNode} [codeNode=null] - The code node.
	 * @param {Object} [parameters={}] - The parameters definition.
	 */
	constructor( codeNode = null, parameters = {} ) {

		super();

		/**
		 * The code node.
		 *
		 * @type {?CodeNode}
		 * @default null
		 */
		this.codeNode = codeNode;

		/**
		 * The parameters definition.
		 *
		 * @type {Object}
		 * @default {}
		 */
		this.parameters = parameters;

		this._local = new Resources();
		this._output = scriptableValue( null );
		this._outputs = {};
		this._source = this.source;
		this._method = null;
		this._object = null;
		this._value = null;
		this._needsOutputUpdate = true;

		this.onRefresh = this.onRefresh.bind( this );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isScriptableNode = true;

	}

	/**
	 * The source code of the scriptable node.
	 *
	 * @type {string}
	 */
	get source() {

		return this.codeNode ? this.codeNode.code : '';

	}

	/**
	 * Sets the reference of a local script variable.
	 *
	 * @param {string} name - The variable name.
	 * @param {Object} value - The reference to set.
	 * @return {Resources} The resource map
	 */
	setLocal( name, value ) {

		return this._local.set( name, value );

	}

	/**
	 * Gets the value of a local script variable.
	 *
	 * @param {string} name - The variable name.
	 * @return {Object} The value.
	 */
	getLocal( name ) {

		return this._local.get( name );

	}

	/**
	 * Event listener for the `refresh` event.
	 */
	onRefresh() {

		this._refresh();

	}

	/**
	 * Returns an input from the layout with the given id/name.
	 *
	 * @param {string} id - The id/name of the input.
	 * @return {Object} The element entry.
	 */
	getInputLayout( id ) {

		for ( const element of this.getLayout() ) {

			if ( element.inputType && ( element.id === id || element.name === id ) ) {

				return element;

			}

		}

	}

	/**
	 * Returns an output from the layout with the given id/name.
	 *
	 * @param {string} id - The id/name of the output.
	 * @return {Object} The element entry.
	 */
	getOutputLayout( id ) {

		for ( const element of this.getLayout() ) {

			if ( element.outputType && ( element.id === id || element.name === id ) ) {

				return element;

			}

		}

	}

	/**
	 * Defines a script output for the given name and value.
	 *
	 * @param {string} name - The name of the output.
	 * @param {Node} value - The node value.
	 * @return {ScriptableNode} A reference to this node.
	 */
	setOutput( name, value ) {

		const outputs = this._outputs;

		if ( outputs[ name ] === undefined ) {

			outputs[ name ] = scriptableValue( value );

		} else {

			outputs[ name ].value = value;

		}

		return this;

	}

	/**
	 * Returns a script output for the given name.
	 *
	 * @param {string} name - The name of the output.
	 * @return {ScriptableValueNode} The node value.
	 */
	getOutput( name ) {

		return this._outputs[ name ];

	}

	/**
	 * Returns a parameter for the given name
	 *
	 * @param {string} name - The name of the parameter.
	 * @return {ScriptableValueNode} The node value.
	 */
	getParameter( name ) {

		return this.parameters[ name ];

	}

	/**
	 * Sets a value for the given parameter name.
	 *
	 * @param {string} name - The parameter name.
	 * @param {any} value - The parameter value.
	 * @return {ScriptableNode} A reference to this node.
	 */
	setParameter( name, value ) {

		const parameters = this.parameters;

		if ( value && value.isScriptableNode ) {

			this.deleteParameter( name );

			parameters[ name ] = value;
			parameters[ name ].getDefaultOutput().events.addEventListener( 'refresh', this.onRefresh );

		} else if ( value && value.isScriptableValueNode ) {

			this.deleteParameter( name );

			parameters[ name ] = value;
			parameters[ name ].events.addEventListener( 'refresh', this.onRefresh );

		} else if ( parameters[ name ] === undefined ) {

			parameters[ name ] = scriptableValue( value );
			parameters[ name ].events.addEventListener( 'refresh', this.onRefresh );

		} else {

			parameters[ name ].value = value;

		}

		return this;

	}

	/**
	 * Returns the value of this node which is the value of
	 * the default output.
	 *
	 * @return {Node} The value.
	 */
	getValue() {

		return this.getDefaultOutput().getValue();

	}

	/**
	 * Deletes a parameter from the script.
	 *
	 * @param {string} name - The parameter to remove.
	 * @return {ScriptableNode} A reference to this node.
	 */
	deleteParameter( name ) {

		let valueNode = this.parameters[ name ];

		if ( valueNode ) {

			if ( valueNode.isScriptableNode ) valueNode = valueNode.getDefaultOutput();

			valueNode.events.removeEventListener( 'refresh', this.onRefresh );

		}

		return this;

	}

	/**
	 * Deletes all parameters from the script.
	 *
	 * @return {ScriptableNode} A reference to this node.
	 */
	clearParameters() {

		for ( const name of Object.keys( this.parameters ) ) {

			this.deleteParameter( name );

		}

		this.needsUpdate = true;

		return this;

	}

	/**
	 * Calls a function from the script.
	 *
	 * @param {string} name - The function name.
	 * @param {...any} params - A list of parameters.
	 * @return {any} The result of the function call.
	 */
	call( name, ...params ) {

		const object = this.getObject();
		const method = object[ name ];

		if ( typeof method === 'function' ) {

			return method( ...params );

		}

	}

	/**
	 * Asynchronously calls a function from the script.
	 *
	 * @param {string} name - The function name.
	 * @param {...any} params - A list of parameters.
	 * @return {Promise<any>} The result of the function call.
	 */
	async callAsync( name, ...params ) {

		const object = this.getObject();
		const method = object[ name ];

		if ( typeof method === 'function' ) {

			return method.constructor.name === 'AsyncFunction' ? await method( ...params ) : method( ...params );

		}

	}

	/**
	 * Overwritten since the node types is inferred from the script's output.
	 *
	 * @param {NodeBuilder} builder - The current node builder
	 * @return {string} The node type.
	 */
	getNodeType( builder ) {

		return this.getDefaultOutputNode().getNodeType( builder );

	}

	/**
	 * Refreshes the script node.
	 *
	 * @param {?string} [output=null] - An optional output.
	 */
	refresh( output = null ) {

		if ( output !== null ) {

			this.getOutput( output ).refresh();

		} else {

			this._refresh();

		}

	}

	/**
	 * Returns an object representation of the script.
	 *
	 * @return {Object} The result object.
	 */
	getObject() {

		if ( this.needsUpdate ) this.dispose();
		if ( this._object !== null ) return this._object;

		//

		const refresh = () => this.refresh();
		const setOutput = ( id, value ) => this.setOutput( id, value );

		const parameters = new Parameters( this );

		const THREE = ScriptableNodeResources.get( 'THREE' );
		const TSL = ScriptableNodeResources.get( 'TSL' );

		const method = this.getMethod();
		const params = [ parameters, this._local, ScriptableNodeResources, refresh, setOutput, THREE, TSL ];

		this._object = method( ...params );

		const layout = this._object.layout;

		if ( layout ) {

			if ( layout.cache === false ) {

				this._local.clear();

			}

			// default output
			this._output.outputType = layout.outputType || null;

			if ( Array.isArray( layout.elements ) ) {

				for ( const element of layout.elements ) {

					const id = element.id || element.name;

					if ( element.inputType ) {

						if ( this.getParameter( id ) === undefined ) this.setParameter( id, null );

						this.getParameter( id ).inputType = element.inputType;

					}

					if ( element.outputType ) {

						if ( this.getOutput( id ) === undefined ) this.setOutput( id, null );

						this.getOutput( id ).outputType = element.outputType;

					}

				}

			}

		}

		return this._object;

	}

	deserialize( data ) {

		super.deserialize( data );

		for ( const name in this.parameters ) {

			let valueNode = this.parameters[ name ];

			if ( valueNode.isScriptableNode ) valueNode = valueNode.getDefaultOutput();

			valueNode.events.addEventListener( 'refresh', this.onRefresh );

		}

	}

	/**
	 * Returns the layout of the script.
	 *
	 * @return {Object} The script's layout.
	 */
	getLayout() {

		return this.getObject().layout;

	}

	/**
	 * Returns default node output of the script.
	 *
	 * @return {Node} The default node output.
	 */
	getDefaultOutputNode() {

		const output = this.getDefaultOutput().value;

		if ( output && output.isNode ) {

			return output;

		}

		return float();

	}

	/**
	 * Returns default output of the script.
	 *
	 * @return {ScriptableValueNode} The default output.
	 */
	getDefaultOutput()	{

		return this._exec()._output;

	}

	/**
	 * Returns a function created from the node's script.
	 *
	 * @return {Function} The function representing the node's code.
	 */
	getMethod() {

		if ( this.needsUpdate ) this.dispose();
		if ( this._method !== null ) return this._method;

		//

		const parametersProps = [ 'parameters', 'local', 'global', 'refresh', 'setOutput', 'THREE', 'TSL' ];
		const interfaceProps = [ 'layout', 'init', 'main', 'dispose' ];

		const properties = interfaceProps.join( ', ' );
		const declarations = 'var ' + properties + '; var output = {};\n';
		const returns = '\nreturn { ...output, ' + properties + ' };';

		const code = declarations + this.codeNode.code + returns;

		//

		this._method = new Function( ...parametersProps, code );

		return this._method;

	}

	/**
	 * Frees all internal resources.
	 */
	dispose() {

		if ( this._method === null ) return;

		if ( this._object && typeof this._object.dispose === 'function' ) {

			this._object.dispose();

		}

		this._method = null;
		this._object = null;
		this._source = null;
		this._value = null;
		this._needsOutputUpdate = true;
		this._output.value = null;
		this._outputs = {};

	}

	setup() {

		return this.getDefaultOutputNode();

	}

	getCacheKey( force ) {

		const values = [ hashString( this.source ), this.getDefaultOutputNode().getCacheKey( force ) ];

		for ( const param in this.parameters ) {

			values.push( this.parameters[ param ].getCacheKey( force ) );

		}

		return hashArray( values );

	}

	set needsUpdate( value ) {

		if ( value === true ) this.dispose();

	}

	get needsUpdate() {

		return this.source !== this._source;

	}

	/**
	 * Executes the `main` function of the script.
	 *
	 * @private
	 * @return {ScriptableNode} A reference to this node.
	 */
	_exec()	{

		if ( this.codeNode === null ) return this;

		if ( this._needsOutputUpdate === true ) {

			this._value = this.call( 'main' );

			this._needsOutputUpdate = false;

		}

		this._output.value = this._value;

		return this;

	}

	/**
	 * Executes the refresh.
	 *
	 * @private
	 */
	_refresh() {

		this.needsUpdate = true;

		this._exec();

		this._output.refresh();

	}

}
```
</details>

#### Methods

##### `setLocal(name: string, value: any): Resources`

<details><summary>Code</summary>

```ts
setLocal( name, value ) {

		return this._local.set( name, value );

	}
```
</details>

##### `getLocal(name: string): any`

<details><summary>Code</summary>

```ts
getLocal( name ) {

		return this._local.get( name );

	}
```
</details>

##### `onRefresh(): void`

<details><summary>Code</summary>

```ts
onRefresh() {

		this._refresh();

	}
```
</details>

##### `getInputLayout(id: string): any`

<details><summary>Code</summary>

```ts
getInputLayout( id ) {

		for ( const element of this.getLayout() ) {

			if ( element.inputType && ( element.id === id || element.name === id ) ) {

				return element;

			}

		}

	}
```
</details>

##### `getOutputLayout(id: string): any`

<details><summary>Code</summary>

```ts
getOutputLayout( id ) {

		for ( const element of this.getLayout() ) {

			if ( element.outputType && ( element.id === id || element.name === id ) ) {

				return element;

			}

		}

	}
```
</details>

##### `setOutput(name: string, value: Node): ScriptableNode`

<details><summary>Code</summary>

```ts
setOutput( name, value ) {

		const outputs = this._outputs;

		if ( outputs[ name ] === undefined ) {

			outputs[ name ] = scriptableValue( value );

		} else {

			outputs[ name ].value = value;

		}

		return this;

	}
```
</details>

##### `getOutput(name: string): ScriptableValueNode`

<details><summary>Code</summary>

```ts
getOutput( name ) {

		return this._outputs[ name ];

	}
```
</details>

##### `getParameter(name: string): ScriptableValueNode`

<details><summary>Code</summary>

```ts
getParameter( name ) {

		return this.parameters[ name ];

	}
```
</details>

##### `setParameter(name: string, value: any): ScriptableNode`

<details><summary>Code</summary>

```ts
setParameter( name, value ) {

		const parameters = this.parameters;

		if ( value && value.isScriptableNode ) {

			this.deleteParameter( name );

			parameters[ name ] = value;
			parameters[ name ].getDefaultOutput().events.addEventListener( 'refresh', this.onRefresh );

		} else if ( value && value.isScriptableValueNode ) {

			this.deleteParameter( name );

			parameters[ name ] = value;
			parameters[ name ].events.addEventListener( 'refresh', this.onRefresh );

		} else if ( parameters[ name ] === undefined ) {

			parameters[ name ] = scriptableValue( value );
			parameters[ name ].events.addEventListener( 'refresh', this.onRefresh );

		} else {

			parameters[ name ].value = value;

		}

		return this;

	}
```
</details>

##### `getValue(): Node`

<details><summary>Code</summary>

```ts
getValue() {

		return this.getDefaultOutput().getValue();

	}
```
</details>

##### `deleteParameter(name: string): ScriptableNode`

<details><summary>Code</summary>

```ts
deleteParameter( name ) {

		let valueNode = this.parameters[ name ];

		if ( valueNode ) {

			if ( valueNode.isScriptableNode ) valueNode = valueNode.getDefaultOutput();

			valueNode.events.removeEventListener( 'refresh', this.onRefresh );

		}

		return this;

	}
```
</details>

##### `clearParameters(): ScriptableNode`

<details><summary>Code</summary>

```ts
clearParameters() {

		for ( const name of Object.keys( this.parameters ) ) {

			this.deleteParameter( name );

		}

		this.needsUpdate = true;

		return this;

	}
```
</details>

##### `call(name: string, params: any[]): any`

<details><summary>Code</summary>

```ts
call( name, ...params ) {

		const object = this.getObject();
		const method = object[ name ];

		if ( typeof method === 'function' ) {

			return method( ...params );

		}

	}
```
</details>

##### `callAsync(name: string, params: any[]): Promise<any>`

<details><summary>Code</summary>

```ts
async callAsync( name, ...params ) {

		const object = this.getObject();
		const method = object[ name ];

		if ( typeof method === 'function' ) {

			return method.constructor.name === 'AsyncFunction' ? await method( ...params ) : method( ...params );

		}

	}
```
</details>

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return this.getDefaultOutputNode().getNodeType( builder );

	}
```
</details>

##### `refresh(output: string): void`

<details><summary>Code</summary>

```ts
refresh( output = null ) {

		if ( output !== null ) {

			this.getOutput( output ).refresh();

		} else {

			this._refresh();

		}

	}
```
</details>

##### `getObject(): any`

<details><summary>Code</summary>

```ts
getObject() {

		if ( this.needsUpdate ) this.dispose();
		if ( this._object !== null ) return this._object;

		//

		const refresh = () => this.refresh();
		const setOutput = ( id, value ) => this.setOutput( id, value );

		const parameters = new Parameters( this );

		const THREE = ScriptableNodeResources.get( 'THREE' );
		const TSL = ScriptableNodeResources.get( 'TSL' );

		const method = this.getMethod();
		const params = [ parameters, this._local, ScriptableNodeResources, refresh, setOutput, THREE, TSL ];

		this._object = method( ...params );

		const layout = this._object.layout;

		if ( layout ) {

			if ( layout.cache === false ) {

				this._local.clear();

			}

			// default output
			this._output.outputType = layout.outputType || null;

			if ( Array.isArray( layout.elements ) ) {

				for ( const element of layout.elements ) {

					const id = element.id || element.name;

					if ( element.inputType ) {

						if ( this.getParameter( id ) === undefined ) this.setParameter( id, null );

						this.getParameter( id ).inputType = element.inputType;

					}

					if ( element.outputType ) {

						if ( this.getOutput( id ) === undefined ) this.setOutput( id, null );

						this.getOutput( id ).outputType = element.outputType;

					}

				}

			}

		}

		return this._object;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		for ( const name in this.parameters ) {

			let valueNode = this.parameters[ name ];

			if ( valueNode.isScriptableNode ) valueNode = valueNode.getDefaultOutput();

			valueNode.events.addEventListener( 'refresh', this.onRefresh );

		}

	}
```
</details>

##### `getLayout(): any`

<details><summary>Code</summary>

```ts
getLayout() {

		return this.getObject().layout;

	}
```
</details>

##### `getDefaultOutputNode(): Node`

<details><summary>Code</summary>

```ts
getDefaultOutputNode() {

		const output = this.getDefaultOutput().value;

		if ( output && output.isNode ) {

			return output;

		}

		return float();

	}
```
</details>

##### `getDefaultOutput(): ScriptableValueNode`

<details><summary>Code</summary>

```ts
getDefaultOutput()	{

		return this._exec()._output;

	}
```
</details>

##### `getMethod(): Function`

<details><summary>Code</summary>

```ts
getMethod() {

		if ( this.needsUpdate ) this.dispose();
		if ( this._method !== null ) return this._method;

		//

		const parametersProps = [ 'parameters', 'local', 'global', 'refresh', 'setOutput', 'THREE', 'TSL' ];
		const interfaceProps = [ 'layout', 'init', 'main', 'dispose' ];

		const properties = interfaceProps.join( ', ' );
		const declarations = 'var ' + properties + '; var output = {};\n';
		const returns = '\nreturn { ...output, ' + properties + ' };';

		const code = declarations + this.codeNode.code + returns;

		//

		this._method = new Function( ...parametersProps, code );

		return this._method;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		if ( this._method === null ) return;

		if ( this._object && typeof this._object.dispose === 'function' ) {

			this._object.dispose();

		}

		this._method = null;
		this._object = null;
		this._source = null;
		this._value = null;
		this._needsOutputUpdate = true;
		this._output.value = null;
		this._outputs = {};

	}
```
</details>

##### `setup(): Node`

<details><summary>Code</summary>

```ts
setup() {

		return this.getDefaultOutputNode();

	}
```
</details>

##### `getCacheKey(force: any): number`

<details><summary>Code</summary>

```ts
getCacheKey( force ) {

		const values = [ hashString( this.source ), this.getDefaultOutputNode().getCacheKey( force ) ];

		for ( const param in this.parameters ) {

			values.push( this.parameters[ param ].getCacheKey( force ) );

		}

		return hashArray( values );

	}
```
</details>

##### `_exec(): ScriptableNode`

<details><summary>Code</summary>

```ts
_exec()	{

		if ( this.codeNode === null ) return this;

		if ( this._needsOutputUpdate === true ) {

			this._value = this.call( 'main' );

			this._needsOutputUpdate = false;

		}

		this._output.value = this._value;

		return this;

	}
```
</details>

##### `_refresh(): void`

<details><summary>Code</summary>

```ts
_refresh() {

		this.needsUpdate = true;

		this._exec();

		this._output.refresh();

	}
```
</details>


---