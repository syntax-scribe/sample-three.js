[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ReferenceNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 15 |
| 🧱 Classes | 2 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/ReferenceNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `uniform` | `../core/UniformNode.js` |
| `texture` | `./TextureNode.js` |
| `cubeTexture` | `./CubeTextureNode.js` |
| `buffer` | `./BufferNode.js` |
| `nodeObject` | `../tsl/TSLBase.js` |
| `uniformArray` | `./UniformArrayNode.js` |
| `ArrayElementNode` | `../utils/ArrayElementNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `node` | `any` | let/var | `null` | ✗ |
| `value` | `any` | let/var | `object[ properties[ 0 ] ]` | ✗ |


---

## Functions

### `ReferenceElementNode.getNodeType(): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node type is inferred from
	 * the uniform type of the reference node.
	 *
	 * @return {string} The node type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getNodeType() {

		return this.referenceNode.uniformType;

	}
```
</details>

### `ReferenceElementNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `super.generate`
- `this.referenceNode.getNodeType`
- `this.getNodeType`
- `builder.format`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const snippet = super.generate( builder );
		const arrayType = this.referenceNode.getNodeType();
		const elementType = this.getNodeType();

		return builder.format( snippet, arrayType, elementType );

	}
```
</details>

### `ReferenceNode.element(indexNode: IndexNode): ReferenceElementNode`

**JSDoc:**
```typescript
/**
	 * When the referred property is array-like, this method can be used
	 * to access elements via an index node.
	 *
	 * @param {IndexNode} indexNode - indexNode.
	 * @return {ReferenceElementNode} A reference to an element.
	 */
```

**Parameters:**

- **`indexNode`** `IndexNode`

**Returns:** `ReferenceElementNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
element( indexNode ) {

		return nodeObject( new ReferenceElementNode( this, nodeObject( indexNode ) ) );

	}
```
</details>

### `ReferenceNode.setGroup(group: UniformGroupNode): ReferenceNode`

**JSDoc:**
```typescript
/**
	 * Sets the uniform group for this reference node.
	 *
	 * @param {UniformGroupNode} group - The uniform group to set.
	 * @return {ReferenceNode} A reference to this node.
	 */
```

**Parameters:**

- **`group`** `UniformGroupNode`

**Returns:** `ReferenceNode`

<details><summary>Code</summary>

```typescript
setGroup( group ) {

		this.group = group;

		return this;

	}
```
</details>

### `ReferenceNode.setName(name: string): ReferenceNode`

**JSDoc:**
```typescript
/**
	 * Sets the name for the internal uniform.
	 *
	 * @param {string} name - The label to set.
	 * @return {ReferenceNode} A reference to this node.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `ReferenceNode`

<details><summary>Code</summary>

```typescript
setName( name ) {

		this.name = name;

		return this;

	}
```
</details>

### `ReferenceNode.label(name: string): ReferenceNode`

**JSDoc:**
```typescript
/**
	 * Sets the label for the internal uniform.
	 *
	 * @deprecated
	 * @param {string} name - The label to set.
	 * @return {ReferenceNode} A reference to this node.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `ReferenceNode`

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

### `ReferenceNode.setNodeType(uniformType: string): void`

**JSDoc:**
```typescript
/**
	 * Sets the node type which automatically defines the internal
	 * uniform type.
	 *
	 * @param {string} uniformType - The type to set.
	 */
```

**Parameters:**

- **`uniformType`** `string`

**Returns:** `void`

**Calls:**

- `buffer (from ./BufferNode.js)`
- `Array.isArray`
- `this.getValueFromReference`
- `uniformArray (from ./UniformArrayNode.js)`
- `texture (from ./TextureNode.js)`
- `cubeTexture (from ./CubeTextureNode.js)`
- `uniform (from ../core/UniformNode.js)`
- `node.setGroup`
- `node.setName`
- `node.getSelf`

<details><summary>Code</summary>

```typescript
setNodeType( uniformType ) {

		let node = null;

		if ( this.count !== null ) {

			node = buffer( null, uniformType, this.count );

		} else if ( Array.isArray( this.getValueFromReference() ) ) {

			node = uniformArray( null, uniformType );

		} else if ( uniformType === 'texture' ) {

			node = texture( null );

		} else if ( uniformType === 'cubeTexture' ) {

			node = cubeTexture( null );

		} else {

			node = uniform( null, uniformType );

		}

		if ( this.group !== null ) {

			node.setGroup( this.group );

		}

		if ( this.name !== null ) node.setName( this.name );

		this.node = node.getSelf();

	}
```
</details>

### `ReferenceNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node type is inferred from
	 * the type of the reference node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.updateReference`
- `this.updateValue`
- `this.node.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		if ( this.node === null ) {

			this.updateReference( builder );
			this.updateValue();

		}

		return this.node.getNodeType( builder );

	}
```
</details>

### `ReferenceNode.getValueFromReference(object: any): any`

**JSDoc:**
```typescript
/**
	 * Returns the property value from the given referred object.
	 *
	 * @param {Object} [object=this.reference] - The object to retrieve the property value from.
	 * @return {any} The value.
	 */
```

**Parameters:**

- **`object`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getValueFromReference( object = this.reference ) {

		const { properties } = this;

		let value = object[ properties[ 0 ] ];

		for ( let i = 1; i < properties.length; i ++ ) {

			value = value[ properties[ i ] ];

		}

		return value;

	}
```
</details>

### `ReferenceNode.updateReference(state: any): any`

**JSDoc:**
```typescript
/**
	 * Allows to update the reference based on the given state. The state is only
	 * evaluated {@link ReferenceNode#object} is not set.
	 *
	 * @param {(NodeFrame|NodeBuilder)} state - The current state.
	 * @return {Object} The updated reference.
	 */
```

**Parameters:**

- **`state`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
updateReference( state ) {

		this.reference = this.object !== null ? this.object : state.object;

		return this.reference;

	}
```
</details>

### `ReferenceNode.setup(): UniformNode`

**JSDoc:**
```typescript
/**
	 * The output of the reference node is the internal uniform node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {UniformNode} The output node.
	 */
```

**Returns:** `UniformNode`

**Calls:**

- `this.updateValue`

<details><summary>Code</summary>

```typescript
setup( /* builder */ ) {

		this.updateValue();

		return this.node;

	}
```
</details>

### `ReferenceNode.update(): void`

**JSDoc:**
```typescript
/**
	 * Overwritten to update the internal uniform value.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
```

**Returns:** `void`

**Calls:**

- `this.updateValue`

<details><summary>Code</summary>

```typescript
update( /*frame*/ ) {

		this.updateValue();

	}
```
</details>

### `ReferenceNode.updateValue(): void`

**JSDoc:**
```typescript
/**
	 * Retrieves the value from the referred object property and uses it
	 * to updated the internal uniform.
	 */
```

**Returns:** `void`

**Calls:**

- `this.setNodeType`
- `this.getValueFromReference`
- `Array.isArray`

<details><summary>Code</summary>

```typescript
updateValue() {

		if ( this.node === null ) this.setNodeType( this.uniformType );

		const value = this.getValueFromReference();

		if ( Array.isArray( value ) ) {

			this.node.array = value;

		} else {

			this.node.value = value;

		}

	}
```
</details>

### `reference(name: string, type: string, object: any): ReferenceNode`

**Parameters:**

- **`name`** `string`
- **`type`** `string`
- **`object`** `any`

**Returns:** `ReferenceNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( name, type, object ) => nodeObject( new ReferenceNode( name, type, object ) )
```
</details>

### `referenceBuffer(name: string, type: string, count: number, object: any): ReferenceNode`

**Parameters:**

- **`name`** `string`
- **`type`** `string`
- **`count`** `number`
- **`object`** `any`

**Returns:** `ReferenceNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( name, type, count, object ) => nodeObject( new ReferenceNode( name, type, object, count ) )
```
</details>


---

## Classes

### `ReferenceElementNode`

<details><summary>Class Code</summary>

```ts
class ReferenceElementNode extends ArrayElementNode {

	static get type() {

		return 'ReferenceElementNode';

	}

	/**
	 * Constructs a new reference element node.
	 *
	 * @param {?ReferenceNode} referenceNode - The reference node.
	 * @param {Node} indexNode - The index node that defines the element access.
	 */
	constructor( referenceNode, indexNode ) {

		super( referenceNode, indexNode );

		/**
		 * Similar to {@link ReferenceNode#reference}, an additional
		 * property references to the current node.
		 *
		 * @type {?ReferenceNode}
		 * @default null
		 */
		this.referenceNode = referenceNode;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isReferenceElementNode = true;

	}

	/**
	 * This method is overwritten since the node type is inferred from
	 * the uniform type of the reference node.
	 *
	 * @return {string} The node type.
	 */
	getNodeType() {

		return this.referenceNode.uniformType;

	}

	generate( builder ) {

		const snippet = super.generate( builder );
		const arrayType = this.referenceNode.getNodeType();
		const elementType = this.getNodeType();

		return builder.format( snippet, arrayType, elementType );

	}

}
```
</details>

#### Methods

##### `getNodeType(): string`

<details><summary>Code</summary>

```ts
getNodeType() {

		return this.referenceNode.uniformType;

	}
```
</details>

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const snippet = super.generate( builder );
		const arrayType = this.referenceNode.getNodeType();
		const elementType = this.getNodeType();

		return builder.format( snippet, arrayType, elementType );

	}
```
</details>

### `ReferenceNode`

<details><summary>Class Code</summary>

```ts
class ReferenceNode extends Node {

	static get type() {

		return 'ReferenceNode';

	}

	/**
	 * Constructs a new reference node.
	 *
	 * @param {string} property - The name of the property the node refers to.
	 * @param {string} uniformType - The uniform type that should be used to represent the property value.
	 * @param {?Object} [object=null] - The object the property belongs to.
	 * @param {?number} [count=null] - When the linked property is an array-like, this parameter defines its length.
	 */
	constructor( property, uniformType, object = null, count = null ) {

		super();

		/**
		 * The name of the property the node refers to.
		 *
		 * @type {string}
		 */
		this.property = property;

		/**
		 * The uniform type that should be used to represent the property value.
		 *
		 * @type {string}
		 */
		this.uniformType = uniformType;

		/**
		 * The object the property belongs to.
		 *
		 * @type {?Object}
		 * @default null
		 */
		this.object = object;

		/**
		 * When the linked property is an array, this parameter defines its length.
		 *
		 * @type {?number}
		 * @default null
		 */
		this.count = count;

		/**
		 * The property name might have dots so nested properties can be referred.
		 * The hierarchy of the names is stored inside this array.
		 *
		 * @type {Array<string>}
		 */
		this.properties = property.split( '.' );

		/**
		 * Points to the current referred object. This property exists next to {@link ReferenceNode#object}
		 * since the final reference might be updated from calling code.
		 *
		 * @type {?Object}
		 * @default null
		 */
		this.reference = object;

		/**
		 * The uniform node that holds the value of the reference node.
		 *
		 * @type {UniformNode}
		 * @default null
		 */
		this.node = null;

		/**
		 * The uniform group of the internal uniform.
		 *
		 * @type {UniformGroupNode}
		 * @default null
		 */
		this.group = null;

		/**
		 * An optional label of the internal uniform node.
		 *
		 * @type {?string}
		 * @default null
		 */
		this.name = null;

		/**
		 * Overwritten since reference nodes are updated per object.
		 *
		 * @type {string}
		 * @default 'object'
		 */
		this.updateType = NodeUpdateType.OBJECT;

	}

	/**
	 * When the referred property is array-like, this method can be used
	 * to access elements via an index node.
	 *
	 * @param {IndexNode} indexNode - indexNode.
	 * @return {ReferenceElementNode} A reference to an element.
	 */
	element( indexNode ) {

		return nodeObject( new ReferenceElementNode( this, nodeObject( indexNode ) ) );

	}

	/**
	 * Sets the uniform group for this reference node.
	 *
	 * @param {UniformGroupNode} group - The uniform group to set.
	 * @return {ReferenceNode} A reference to this node.
	 */
	setGroup( group ) {

		this.group = group;

		return this;

	}

	/**
	 * Sets the name for the internal uniform.
	 *
	 * @param {string} name - The label to set.
	 * @return {ReferenceNode} A reference to this node.
	 */
	setName( name ) {

		this.name = name;

		return this;

	}

	/**
	 * Sets the label for the internal uniform.
	 *
	 * @deprecated
	 * @param {string} name - The label to set.
	 * @return {ReferenceNode} A reference to this node.
	 */
	label( name ) {

		console.warn( 'THREE.TSL: "label()" has been deprecated. Use "setName()" instead.' ); // @deprecated r179

		return this.setName( name );

	}

	/**
	 * Sets the node type which automatically defines the internal
	 * uniform type.
	 *
	 * @param {string} uniformType - The type to set.
	 */
	setNodeType( uniformType ) {

		let node = null;

		if ( this.count !== null ) {

			node = buffer( null, uniformType, this.count );

		} else if ( Array.isArray( this.getValueFromReference() ) ) {

			node = uniformArray( null, uniformType );

		} else if ( uniformType === 'texture' ) {

			node = texture( null );

		} else if ( uniformType === 'cubeTexture' ) {

			node = cubeTexture( null );

		} else {

			node = uniform( null, uniformType );

		}

		if ( this.group !== null ) {

			node.setGroup( this.group );

		}

		if ( this.name !== null ) node.setName( this.name );

		this.node = node.getSelf();

	}

	/**
	 * This method is overwritten since the node type is inferred from
	 * the type of the reference node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( builder ) {

		if ( this.node === null ) {

			this.updateReference( builder );
			this.updateValue();

		}

		return this.node.getNodeType( builder );

	}

	/**
	 * Returns the property value from the given referred object.
	 *
	 * @param {Object} [object=this.reference] - The object to retrieve the property value from.
	 * @return {any} The value.
	 */
	getValueFromReference( object = this.reference ) {

		const { properties } = this;

		let value = object[ properties[ 0 ] ];

		for ( let i = 1; i < properties.length; i ++ ) {

			value = value[ properties[ i ] ];

		}

		return value;

	}

	/**
	 * Allows to update the reference based on the given state. The state is only
	 * evaluated {@link ReferenceNode#object} is not set.
	 *
	 * @param {(NodeFrame|NodeBuilder)} state - The current state.
	 * @return {Object} The updated reference.
	 */
	updateReference( state ) {

		this.reference = this.object !== null ? this.object : state.object;

		return this.reference;

	}

	/**
	 * The output of the reference node is the internal uniform node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {UniformNode} The output node.
	 */
	setup( /* builder */ ) {

		this.updateValue();

		return this.node;

	}

	/**
	 * Overwritten to update the internal uniform value.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
	update( /*frame*/ ) {

		this.updateValue();

	}

	/**
	 * Retrieves the value from the referred object property and uses it
	 * to updated the internal uniform.
	 */
	updateValue() {

		if ( this.node === null ) this.setNodeType( this.uniformType );

		const value = this.getValueFromReference();

		if ( Array.isArray( value ) ) {

			this.node.array = value;

		} else {

			this.node.value = value;

		}

	}

}
```
</details>

#### Methods

##### `element(indexNode: IndexNode): ReferenceElementNode`

<details><summary>Code</summary>

```ts
element( indexNode ) {

		return nodeObject( new ReferenceElementNode( this, nodeObject( indexNode ) ) );

	}
```
</details>

##### `setGroup(group: UniformGroupNode): ReferenceNode`

<details><summary>Code</summary>

```ts
setGroup( group ) {

		this.group = group;

		return this;

	}
```
</details>

##### `setName(name: string): ReferenceNode`

<details><summary>Code</summary>

```ts
setName( name ) {

		this.name = name;

		return this;

	}
```
</details>

##### `label(name: string): ReferenceNode`

<details><summary>Code</summary>

```ts
label( name ) {

		console.warn( 'THREE.TSL: "label()" has been deprecated. Use "setName()" instead.' ); // @deprecated r179

		return this.setName( name );

	}
```
</details>

##### `setNodeType(uniformType: string): void`

<details><summary>Code</summary>

```ts
setNodeType( uniformType ) {

		let node = null;

		if ( this.count !== null ) {

			node = buffer( null, uniformType, this.count );

		} else if ( Array.isArray( this.getValueFromReference() ) ) {

			node = uniformArray( null, uniformType );

		} else if ( uniformType === 'texture' ) {

			node = texture( null );

		} else if ( uniformType === 'cubeTexture' ) {

			node = cubeTexture( null );

		} else {

			node = uniform( null, uniformType );

		}

		if ( this.group !== null ) {

			node.setGroup( this.group );

		}

		if ( this.name !== null ) node.setName( this.name );

		this.node = node.getSelf();

	}
```
</details>

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		if ( this.node === null ) {

			this.updateReference( builder );
			this.updateValue();

		}

		return this.node.getNodeType( builder );

	}
```
</details>

##### `getValueFromReference(object: any): any`

<details><summary>Code</summary>

```ts
getValueFromReference( object = this.reference ) {

		const { properties } = this;

		let value = object[ properties[ 0 ] ];

		for ( let i = 1; i < properties.length; i ++ ) {

			value = value[ properties[ i ] ];

		}

		return value;

	}
```
</details>

##### `updateReference(state: any): any`

<details><summary>Code</summary>

```ts
updateReference( state ) {

		this.reference = this.object !== null ? this.object : state.object;

		return this.reference;

	}
```
</details>

##### `setup(): UniformNode`

<details><summary>Code</summary>

```ts
setup( /* builder */ ) {

		this.updateValue();

		return this.node;

	}
```
</details>

##### `update(): void`

<details><summary>Code</summary>

```ts
update( /*frame*/ ) {

		this.updateValue();

	}
```
</details>

##### `updateValue(): void`

<details><summary>Code</summary>

```ts
updateValue() {

		if ( this.node === null ) this.setNodeType( this.uniformType );

		const value = this.getValueFromReference();

		if ( Array.isArray( value ) ) {

			this.node.array = value;

		} else {

			this.node.value = value;

		}

	}
```
</details>


---