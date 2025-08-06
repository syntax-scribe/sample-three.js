[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `UniformNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/UniformNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `InputNode` | `./InputNode.js` |
| `objectGroup` | `./UniformGroupNode.js` |
| `nodeObject` | `../tsl/TSLCore.js` |
| `getConstNodeType` | `../tsl/TSLCore.js` |
| `getValueFromType` | `./NodeUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `snippet` | `any` | let/var | `uniformName` | ✗ |
| `propertyName` | `any` | let/var | `nodeData.propertyName` | ✗ |


---

## Functions

### `UniformNode.setName(name: string): UniformNode`

**JSDoc:**
```typescript
/**
	 * Sets the {@link UniformNode#name} property.
	 *
	 * @param {string} name - The name of the uniform.
	 * @return {UniformNode} A reference to this node.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `UniformNode`

<details><summary>Code</summary>

```typescript
setName( name ) {

		this.name = name;

		return this;

	}
```
</details>

### `UniformNode.label(name: string): UniformNode`

**JSDoc:**
```typescript
/**
	 * Sets the {@link UniformNode#name} property.
	 *
	 * @deprecated
	 * @param {string} name - The name of the uniform.
	 * @return {UniformNode} A reference to this node.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `UniformNode`

**Calls:**

- `console.warn`
- `this.setName`

<details><summary>Code</summary>

```typescript
label( name ) {

		console.warn( 'THREE.TSL: "label()" has been deprecated. Use "setName()" instead.' ); // @deprecated r179

		return this.setName( name );

	}
```
</details>

### `UniformNode.setGroup(group: UniformGroupNode): UniformNode`

**JSDoc:**
```typescript
/**
	 * Sets the {@link UniformNode#groupNode} property.
	 *
	 * @param {UniformGroupNode} group - The uniform group.
	 * @return {UniformNode} A reference to this node.
	 */
```

**Parameters:**

- **`group`** `UniformGroupNode`

**Returns:** `UniformNode`

<details><summary>Code</summary>

```typescript
setGroup( group ) {

		this.groupNode = group;

		return this;

	}
```
</details>

### `UniformNode.getGroup(): UniformGroupNode`

**JSDoc:**
```typescript
/**
	 * Returns the {@link UniformNode#groupNode}.
	 *
	 * @return {UniformGroupNode} The uniform group.
	 */
```

**Returns:** `UniformGroupNode`

<details><summary>Code</summary>

```typescript
getGroup() {

		return this.groupNode;

	}
```
</details>

### `UniformNode.getUniformHash(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * By default, this method returns the result of {@link Node#getHash} but derived
	 * classes might overwrite this method with a different implementation.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The uniform hash.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.getHash`

<details><summary>Code</summary>

```typescript
getUniformHash( builder ) {

		return this.getHash( builder );

	}
```
</details>

### `UniformNode.onUpdate(callback: any, updateType: any): Node`

**Parameters:**

- **`callback`** `any`
- **`updateType`** `any`

**Returns:** `Node`

**Calls:**

- `this.getSelf`
- `callback.bind`
- `super.onUpdate`
- `callback`

<details><summary>Code</summary>

```typescript
onUpdate( callback, updateType ) {

		const self = this.getSelf();

		callback = callback.bind( self );

		return super.onUpdate( ( frame ) => {

			const value = callback( frame, self );

			if ( value !== undefined ) {

				this.value = value;

			}

	 	}, updateType );

	}
```
</details>

### `UniformNode.getInputType(builder: any): string`

**Parameters:**

- **`builder`** `any`

**Returns:** `string`

**Calls:**

- `super.getInputType`

<details><summary>Code</summary>

```typescript
getInputType( builder ) {

		let type = super.getInputType( builder );

		if ( type === 'bool' ) {

			type = 'uint';

		}

		return type;

	}
```
</details>

### `UniformNode.generate(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `this.getNodeType`
- `this.getUniformHash`
- `builder.getNodeFromHash`
- `builder.setHashNode`
- `sharedNode.getInputType`
- `builder.getUniformFromNode`
- `builder.getPropertyName`
- `builder.getDataFromNode`
- `builder.getVarFromNode`
- `builder.format`
- `builder.addLineFlowCode`

**Internal Comments:**
```
// (x2)
// cache to variable (x2)
```

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		const type = this.getNodeType( builder );

		const hash = this.getUniformHash( builder );

		let sharedNode = builder.getNodeFromHash( hash );

		if ( sharedNode === undefined ) {

			builder.setHashNode( this, hash );

			sharedNode = this;

		}

		const sharedNodeType = sharedNode.getInputType( builder );

		const nodeUniform = builder.getUniformFromNode( sharedNode, sharedNodeType, builder.shaderStage, this.name || builder.context.nodeName );
		const uniformName = builder.getPropertyName( nodeUniform );

		if ( builder.context.nodeName !== undefined ) delete builder.context.nodeName;

		//

		let snippet = uniformName;

		if ( type === 'bool' ) {

			// cache to variable

			const nodeData = builder.getDataFromNode( this );

			let propertyName = nodeData.propertyName;

			if ( propertyName === undefined ) {

				const nodeVar = builder.getVarFromNode( this, null, 'bool' );
				propertyName = builder.getPropertyName( nodeVar );

				nodeData.propertyName = propertyName;

				snippet = builder.format( uniformName, sharedNodeType, type );

				builder.addLineFlowCode( `${ propertyName } = ${ snippet }`, this );

			}

			snippet = propertyName;

		}

		return builder.format( snippet, type, output );

	}
```
</details>

### `uniform(value: any, type: string): UniformNode`

**Parameters:**

- **`value`** `any`
- **`type`** `string`

**Returns:** `UniformNode`

**Calls:**

- `getConstNodeType (from ../tsl/TSLCore.js)`
- `getValueFromType (from ./NodeUtils.js)`
- `nodeObject (from ../tsl/TSLCore.js)`

**Internal Comments:**
```
// if the value is a type but no having a value (x3)
// @TODO: get ConstNode from .traverse() in the future (x3)
```

<details><summary>Code</summary>

```typescript
( value, type ) => {

	const nodeType = getConstNodeType( type || value );

	if ( nodeType === value ) {

		// if the value is a type but no having a value

		value = getValueFromType( nodeType );

	}

	// @TODO: get ConstNode from .traverse() in the future
	value = ( value && value.isNode === true ) ? ( value.node && value.node.value ) || value.value : value;

	return nodeObject( new UniformNode( value, nodeType ) );

}
```
</details>


---

## Classes

### `UniformNode`

<details><summary>Class Code</summary>

```ts
class UniformNode extends InputNode {

	static get type() {

		return 'UniformNode';

	}

	/**
	 * Constructs a new uniform node.
	 *
	 * @param {any} value - The value of this node. Usually a JS primitive or three.js object (vector, matrix, color, texture).
	 * @param {?string} nodeType - The node type. If no explicit type is defined, the node tries to derive the type from its value.
	 */
	constructor( value, nodeType = null ) {

		super( value, nodeType );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isUniformNode = true;

		/**
		 * The name or label of the uniform.
		 *
		 * @type {string}
		 * @default ''
		 */
		this.name = '';

		/**
		 * The uniform group of this uniform. By default, uniforms are
		 * managed per object but they might belong to a shared group
		 * which is updated per frame or render call.
		 *
		 * @type {UniformGroupNode}
		 */
		this.groupNode = objectGroup;

	}

	/**
	 * Sets the {@link UniformNode#name} property.
	 *
	 * @param {string} name - The name of the uniform.
	 * @return {UniformNode} A reference to this node.
	 */
	setName( name ) {

		this.name = name;

		return this;

	}

	/**
	 * Sets the {@link UniformNode#name} property.
	 *
	 * @deprecated
	 * @param {string} name - The name of the uniform.
	 * @return {UniformNode} A reference to this node.
	 */
	label( name ) {

		console.warn( 'THREE.TSL: "label()" has been deprecated. Use "setName()" instead.' ); // @deprecated r179

		return this.setName( name );

	}

	/**
	 * Sets the {@link UniformNode#groupNode} property.
	 *
	 * @param {UniformGroupNode} group - The uniform group.
	 * @return {UniformNode} A reference to this node.
	 */
	setGroup( group ) {

		this.groupNode = group;

		return this;

	}

	/**
	 * Returns the {@link UniformNode#groupNode}.
	 *
	 * @return {UniformGroupNode} The uniform group.
	 */
	getGroup() {

		return this.groupNode;

	}

	/**
	 * By default, this method returns the result of {@link Node#getHash} but derived
	 * classes might overwrite this method with a different implementation.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The uniform hash.
	 */
	getUniformHash( builder ) {

		return this.getHash( builder );

	}

	onUpdate( callback, updateType ) {

		const self = this.getSelf();

		callback = callback.bind( self );

		return super.onUpdate( ( frame ) => {

			const value = callback( frame, self );

			if ( value !== undefined ) {

				this.value = value;

			}

	 	}, updateType );

	}

	getInputType( builder ) {

		let type = super.getInputType( builder );

		if ( type === 'bool' ) {

			type = 'uint';

		}

		return type;

	}

	generate( builder, output ) {

		const type = this.getNodeType( builder );

		const hash = this.getUniformHash( builder );

		let sharedNode = builder.getNodeFromHash( hash );

		if ( sharedNode === undefined ) {

			builder.setHashNode( this, hash );

			sharedNode = this;

		}

		const sharedNodeType = sharedNode.getInputType( builder );

		const nodeUniform = builder.getUniformFromNode( sharedNode, sharedNodeType, builder.shaderStage, this.name || builder.context.nodeName );
		const uniformName = builder.getPropertyName( nodeUniform );

		if ( builder.context.nodeName !== undefined ) delete builder.context.nodeName;

		//

		let snippet = uniformName;

		if ( type === 'bool' ) {

			// cache to variable

			const nodeData = builder.getDataFromNode( this );

			let propertyName = nodeData.propertyName;

			if ( propertyName === undefined ) {

				const nodeVar = builder.getVarFromNode( this, null, 'bool' );
				propertyName = builder.getPropertyName( nodeVar );

				nodeData.propertyName = propertyName;

				snippet = builder.format( uniformName, sharedNodeType, type );

				builder.addLineFlowCode( `${ propertyName } = ${ snippet }`, this );

			}

			snippet = propertyName;

		}

		return builder.format( snippet, type, output );

	}

}
```
</details>

#### Methods

##### `setName(name: string): UniformNode`

<details><summary>Code</summary>

```ts
setName( name ) {

		this.name = name;

		return this;

	}
```
</details>

##### `label(name: string): UniformNode`

<details><summary>Code</summary>

```ts
label( name ) {

		console.warn( 'THREE.TSL: "label()" has been deprecated. Use "setName()" instead.' ); // @deprecated r179

		return this.setName( name );

	}
```
</details>

##### `setGroup(group: UniformGroupNode): UniformNode`

<details><summary>Code</summary>

```ts
setGroup( group ) {

		this.groupNode = group;

		return this;

	}
```
</details>

##### `getGroup(): UniformGroupNode`

<details><summary>Code</summary>

```ts
getGroup() {

		return this.groupNode;

	}
```
</details>

##### `getUniformHash(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getUniformHash( builder ) {

		return this.getHash( builder );

	}
```
</details>

##### `onUpdate(callback: any, updateType: any): Node`

<details><summary>Code</summary>

```ts
onUpdate( callback, updateType ) {

		const self = this.getSelf();

		callback = callback.bind( self );

		return super.onUpdate( ( frame ) => {

			const value = callback( frame, self );

			if ( value !== undefined ) {

				this.value = value;

			}

	 	}, updateType );

	}
```
</details>

##### `getInputType(builder: any): string`

<details><summary>Code</summary>

```ts
getInputType( builder ) {

		let type = super.getInputType( builder );

		if ( type === 'bool' ) {

			type = 'uint';

		}

		return type;

	}
```
</details>

##### `generate(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		const type = this.getNodeType( builder );

		const hash = this.getUniformHash( builder );

		let sharedNode = builder.getNodeFromHash( hash );

		if ( sharedNode === undefined ) {

			builder.setHashNode( this, hash );

			sharedNode = this;

		}

		const sharedNodeType = sharedNode.getInputType( builder );

		const nodeUniform = builder.getUniformFromNode( sharedNode, sharedNodeType, builder.shaderStage, this.name || builder.context.nodeName );
		const uniformName = builder.getPropertyName( nodeUniform );

		if ( builder.context.nodeName !== undefined ) delete builder.context.nodeName;

		//

		let snippet = uniformName;

		if ( type === 'bool' ) {

			// cache to variable

			const nodeData = builder.getDataFromNode( this );

			let propertyName = nodeData.propertyName;

			if ( propertyName === undefined ) {

				const nodeVar = builder.getVarFromNode( this, null, 'bool' );
				propertyName = builder.getPropertyName( nodeVar );

				nodeData.propertyName = propertyName;

				snippet = builder.format( uniformName, sharedNodeType, type );

				builder.addLineFlowCode( `${ propertyName } = ${ snippet }`, this );

			}

			snippet = propertyName;

		}

		return builder.format( snippet, type, output );

	}
```
</details>


---