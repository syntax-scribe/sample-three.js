[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WorkgroupInfoNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 🧱 Classes | 2 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/gpgpu/WorkgroupInfoNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ArrayElementNode` | `../utils/ArrayElementNode.js` |
| `nodeObject` | `../tsl/TSLCore.js` |
| `Node` | `../core/Node.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `snippet` | `any` | let/var | `*not shown*` | ✗ |
| `isAssignContext` | `any` | let/var | `builder.context.assign` | ✗ |
| `name` | `string` | let/var | `( this.name !== '' ) ? this.name : `${this.scope}Array_${this.id}`` | ✗ |


---

## Functions

### `WorkgroupInfoElementNode.generate(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `super.generate`
- `this.getNodeType`
- `builder.format`

**Internal Comments:**
```
// TODO: Possibly activate clip distance index on index access rather than from clipping context
```

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		let snippet;

		const isAssignContext = builder.context.assign;
		snippet = super.generate( builder );

		if ( isAssignContext !== true ) {

			const type = this.getNodeType( builder );

			snippet = builder.format( snippet, type, output );

		}

		// TODO: Possibly activate clip distance index on index access rather than from clipping context

		return snippet;

	}
```
</details>

### `WorkgroupInfoNode.setName(name: string): WorkgroupInfoNode`

**JSDoc:**
```typescript
/**
	 * Sets the name of this node.
	 *
	 * @param {string} name - The name to set.
	 * @return {WorkgroupInfoNode} A reference to this node.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `WorkgroupInfoNode`

<details><summary>Code</summary>

```typescript
setName( name ) {

		this.name = name;

		return this;

	}
```
</details>

### `WorkgroupInfoNode.label(name: string): WorkgroupInfoNode`

**JSDoc:**
```typescript
/**
	 * Sets the name/label of this node.
	 *
	 * @deprecated
	 * @param {string} name - The name to set.
	 * @return {WorkgroupInfoNode} A reference to this node.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `WorkgroupInfoNode`

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

### `WorkgroupInfoNode.setScope(scope: string): WorkgroupInfoNode`

**JSDoc:**
```typescript
/**
	 * Sets the scope of this node.
	 *
	 * @param {string} scope - The scope to set.
	 * @return {WorkgroupInfoNode} A reference to this node.
	 */
```

**Parameters:**

- **`scope`** `string`

**Returns:** `WorkgroupInfoNode`

<details><summary>Code</summary>

```typescript
setScope( scope ) {

		this.scope = scope;

		return this;

	}
```
</details>

### `WorkgroupInfoNode.getElementType(): string`

**JSDoc:**
```typescript
/**
	 * The data type of the array buffer.
	 *
	 * @return {string} The element type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getElementType() {

		return this.elementType;

	}
```
</details>

### `WorkgroupInfoNode.getInputType(): string`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation since the input type
	 * is inferred from the scope.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getInputType( /*builder*/ ) {

		return `${this.scope}Array`;

	}
```
</details>

### `WorkgroupInfoNode.element(indexNode: IndexNode): WorkgroupInfoElementNode`

**JSDoc:**
```typescript
/**
	 * This method can be used to access elements via an index node.
	 *
	 * @param {IndexNode} indexNode - indexNode.
	 * @return {WorkgroupInfoElementNode} A reference to an element.
	 */
```

**Parameters:**

- **`indexNode`** `IndexNode`

**Returns:** `WorkgroupInfoElementNode`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
element( indexNode ) {

		return nodeObject( new WorkgroupInfoElementNode( this, indexNode ) );

	}
```
</details>

### `WorkgroupInfoNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.getScopedArray`
- `this.scope.toLowerCase`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const name = ( this.name !== '' ) ? this.name : `${this.scope}Array_${this.id}`;

		return builder.getScopedArray( name, this.scope.toLowerCase(), this.bufferType, this.bufferCount );

	}
```
</details>

### `workgroupArray(type: string, count: number): WorkgroupInfoNode`

**Parameters:**

- **`type`** `string`
- **`count`** `number`

**Returns:** `WorkgroupInfoNode`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( type, count ) => nodeObject( new WorkgroupInfoNode( 'Workgroup', type, count ) )
```
</details>


---

## Classes

### `WorkgroupInfoElementNode`

<details><summary>Class Code</summary>

```ts
class WorkgroupInfoElementNode extends ArrayElementNode {

	/**
	 * Constructs a new workgroup info element node.
	 *
	 * @param {Node} workgroupInfoNode - The workgroup info node.
	 * @param {Node} indexNode - The index node that defines the element access.
	 */
	constructor( workgroupInfoNode, indexNode ) {

		super( workgroupInfoNode, indexNode );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isWorkgroupInfoElementNode = true;

	}

	generate( builder, output ) {

		let snippet;

		const isAssignContext = builder.context.assign;
		snippet = super.generate( builder );

		if ( isAssignContext !== true ) {

			const type = this.getNodeType( builder );

			snippet = builder.format( snippet, type, output );

		}

		// TODO: Possibly activate clip distance index on index access rather than from clipping context

		return snippet;

	}

}
```
</details>

#### Methods

##### `generate(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		let snippet;

		const isAssignContext = builder.context.assign;
		snippet = super.generate( builder );

		if ( isAssignContext !== true ) {

			const type = this.getNodeType( builder );

			snippet = builder.format( snippet, type, output );

		}

		// TODO: Possibly activate clip distance index on index access rather than from clipping context

		return snippet;

	}
```
</details>

### `WorkgroupInfoNode`

<details><summary>Class Code</summary>

```ts
class WorkgroupInfoNode extends Node {

	/**
	 * Constructs a new buffer scoped to type scope.
	 *
	 * @param {string} scope - TODO.
	 * @param {string} bufferType - The data type of a 'workgroup' scoped buffer element.
	 * @param {number} [bufferCount=0] - The number of elements in the buffer.
	 */
	constructor( scope, bufferType, bufferCount = 0 ) {

		super( bufferType );

		/**
		 * The buffer type.
		 *
		 * @type {string}
		 */
		this.bufferType = bufferType;

		/**
		 * The buffer count.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.bufferCount = bufferCount;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isWorkgroupInfoNode = true;

		/**
		 * The data type of the array buffer.
		 *
		 * @type {string}
		 */
		this.elementType = bufferType;

		/**
		 * TODO.
		 *
		 * @type {string}
		 */
		this.scope = scope;

		/**
		 * The name of the workgroup scoped buffer.
		 *
		 * @type {string}
		 * @default ''
		 */
		this.name = '';

	}

	/**
	 * Sets the name of this node.
	 *
	 * @param {string} name - The name to set.
	 * @return {WorkgroupInfoNode} A reference to this node.
	 */
	setName( name ) {

		this.name = name;

		return this;

	}

	/**
	 * Sets the name/label of this node.
	 *
	 * @deprecated
	 * @param {string} name - The name to set.
	 * @return {WorkgroupInfoNode} A reference to this node.
	 */
	label( name ) {

		console.warn( 'THREE.TSL: "label()" has been deprecated. Use "setName()" instead.' ); // @deprecated r179

		return this.setName( name );

	}

	/**
	 * Sets the scope of this node.
	 *
	 * @param {string} scope - The scope to set.
	 * @return {WorkgroupInfoNode} A reference to this node.
	 */
	setScope( scope ) {

		this.scope = scope;

		return this;

	}


	/**
	 * The data type of the array buffer.
	 *
	 * @return {string} The element type.
	 */
	getElementType() {

		return this.elementType;

	}

	/**
	 * Overwrites the default implementation since the input type
	 * is inferred from the scope.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
	getInputType( /*builder*/ ) {

		return `${this.scope}Array`;

	}

	/**
	 * This method can be used to access elements via an index node.
	 *
	 * @param {IndexNode} indexNode - indexNode.
	 * @return {WorkgroupInfoElementNode} A reference to an element.
	 */
	element( indexNode ) {

		return nodeObject( new WorkgroupInfoElementNode( this, indexNode ) );

	}

	generate( builder ) {

		const name = ( this.name !== '' ) ? this.name : `${this.scope}Array_${this.id}`;

		return builder.getScopedArray( name, this.scope.toLowerCase(), this.bufferType, this.bufferCount );

	}

}
```
</details>

#### Methods

##### `setName(name: string): WorkgroupInfoNode`

<details><summary>Code</summary>

```ts
setName( name ) {

		this.name = name;

		return this;

	}
```
</details>

##### `label(name: string): WorkgroupInfoNode`

<details><summary>Code</summary>

```ts
label( name ) {

		console.warn( 'THREE.TSL: "label()" has been deprecated. Use "setName()" instead.' ); // @deprecated r179

		return this.setName( name );

	}
```
</details>

##### `setScope(scope: string): WorkgroupInfoNode`

<details><summary>Code</summary>

```ts
setScope( scope ) {

		this.scope = scope;

		return this;

	}
```
</details>

##### `getElementType(): string`

<details><summary>Code</summary>

```ts
getElementType() {

		return this.elementType;

	}
```
</details>

##### `getInputType(): string`

<details><summary>Code</summary>

```ts
getInputType( /*builder*/ ) {

		return `${this.scope}Array`;

	}
```
</details>

##### `element(indexNode: IndexNode): WorkgroupInfoElementNode`

<details><summary>Code</summary>

```ts
element( indexNode ) {

		return nodeObject( new WorkgroupInfoElementNode( this, indexNode ) );

	}
```
</details>

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const name = ( this.name !== '' ) ? this.name : `${this.scope}Array_${this.id}`;

		return builder.getScopedArray( name, this.scope.toLowerCase(), this.bufferType, this.bufferCount );

	}
```
</details>


---