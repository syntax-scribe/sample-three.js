[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ReferenceBaseNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 13 |
| 🧱 Classes | 2 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/ReferenceBaseNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `uniform` | `../core/UniformNode.js` |
| `nodeObject` | `../tsl/TSLCore.js` |
| `ArrayElementNode` | `../utils/ArrayElementNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
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

### `ReferenceBaseNode.setGroup(group: UniformGroupNode): ReferenceBaseNode`

**JSDoc:**
```typescript
/**
	 * Sets the uniform group for this reference node.
	 *
	 * @param {UniformGroupNode} group - The uniform group to set.
	 * @return {ReferenceBaseNode} A reference to this node.
	 */
```

**Parameters:**

- **`group`** `UniformGroupNode`

**Returns:** `ReferenceBaseNode`

<details><summary>Code</summary>

```typescript
setGroup( group ) {

		this.group = group;

		return this;

	}
```
</details>

### `ReferenceBaseNode.element(indexNode: IndexNode): ReferenceElementNode`

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

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
element( indexNode ) {

		return nodeObject( new ReferenceElementNode( this, nodeObject( indexNode ) ) );

	}
```
</details>

### `ReferenceBaseNode.setNodeType(uniformType: string): void`

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

- `uniform( null, uniformType ).getSelf`
- `node.setGroup`

<details><summary>Code</summary>

```typescript
setNodeType( uniformType ) {

		const node = uniform( null, uniformType ).getSelf();

		if ( this.group !== null ) {

			node.setGroup( this.group );

		}

		this.node = node;

	}
```
</details>

### `ReferenceBaseNode.getNodeType(builder: NodeBuilder): string`

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

### `ReferenceBaseNode.getValueFromReference(object: any): any`

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

### `ReferenceBaseNode.updateReference(state: any): any`

**JSDoc:**
```typescript
/**
	 * Allows to update the reference based on the given state. The state is only
	 * evaluated {@link ReferenceBaseNode#object} is not set.
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

### `ReferenceBaseNode.setup(): UniformNode`

**JSDoc:**
```typescript
/**
	 * The output of the reference node is the internal uniform node.
	 *
	 * @return {UniformNode} The output node.
	 */
```

**Returns:** `UniformNode`

**Calls:**

- `this.updateValue`

<details><summary>Code</summary>

```typescript
setup() {

		this.updateValue();

		return this.node;

	}
```
</details>

### `ReferenceBaseNode.update(): void`

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

### `ReferenceBaseNode.updateValue(): void`

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

### `reference(name: string, type: string, object: any): ReferenceBaseNode`

**Parameters:**

- **`name`** `string`
- **`type`** `string`
- **`object`** `any`

**Returns:** `ReferenceBaseNode`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( name, type, object ) => nodeObject( new ReferenceBaseNode( name, type, object ) )
```
</details>

### `referenceBuffer(name: string, type: string, count: number, object: any): ReferenceBaseNode`

**Parameters:**

- **`name`** `string`
- **`type`** `string`
- **`count`** `number`
- **`object`** `any`

**Returns:** `ReferenceBaseNode`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( name, type, count, object ) => nodeObject( new ReferenceBaseNode( name, type, object, count ) )
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
	 * @param {ReferenceBaseNode} referenceNode - The reference node.
	 * @param {Node} indexNode - The index node that defines the element access.
	 */
	constructor( referenceNode, indexNode ) {

		super( referenceNode, indexNode );

		/**
		 * Similar to {@link ReferenceBaseNode#reference}, an additional
		 * property references to the current node.
		 *
		 * @type {?ReferenceBaseNode}
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

### `ReferenceBaseNode`

<details><summary>Class Code</summary>

```ts
class ReferenceBaseNode extends Node {

	static get type() {

		return 'ReferenceBaseNode';

	}

	/**
	 * Constructs a new reference base node.
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
		 * Overwritten since reference nodes are updated per object.
		 *
		 * @type {string}
		 * @default 'object'
		 */
		this.updateType = NodeUpdateType.OBJECT;

	}

	/**
	 * Sets the uniform group for this reference node.
	 *
	 * @param {UniformGroupNode} group - The uniform group to set.
	 * @return {ReferenceBaseNode} A reference to this node.
	 */
	setGroup( group ) {

		this.group = group;

		return this;

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
	 * Sets the node type which automatically defines the internal
	 * uniform type.
	 *
	 * @param {string} uniformType - The type to set.
	 */
	setNodeType( uniformType ) {

		const node = uniform( null, uniformType ).getSelf();

		if ( this.group !== null ) {

			node.setGroup( this.group );

		}

		this.node = node;

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
	 * evaluated {@link ReferenceBaseNode#object} is not set.
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
	 * @return {UniformNode} The output node.
	 */
	setup() {

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

##### `setGroup(group: UniformGroupNode): ReferenceBaseNode`

<details><summary>Code</summary>

```ts
setGroup( group ) {

		this.group = group;

		return this;

	}
```
</details>

##### `element(indexNode: IndexNode): ReferenceElementNode`

<details><summary>Code</summary>

```ts
element( indexNode ) {

		return nodeObject( new ReferenceElementNode( this, nodeObject( indexNode ) ) );

	}
```
</details>

##### `setNodeType(uniformType: string): void`

<details><summary>Code</summary>

```ts
setNodeType( uniformType ) {

		const node = uniform( null, uniformType ).getSelf();

		if ( this.group !== null ) {

			node.setGroup( this.group );

		}

		this.node = node;

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
setup() {

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