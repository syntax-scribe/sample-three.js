[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `StorageBufferNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 15 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/StorageBufferNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferNode` | `./BufferNode.js` |
| `bufferAttribute` | `./BufferAttributeNode.js` |
| `nodeObject` | `../tsl/TSLBase.js` |
| `varying` | `../tsl/TSLBase.js` |
| `storageElement` | `../utils/StorageArrayElementNode.js` |
| `NodeAccess` | `../core/constants.js` |
| `getTypeFromLength` | `../core/NodeUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `nodeType` | `any` | let/var | `*not shown*` | ✗ |
| `structTypeNode` | `any` | let/var | `null` | ✗ |


---

## Functions

### `StorageBufferNode.getHash(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the buffer data might be shared
	 * and thus the hash should be shared as well.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The hash.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `builder.globalCache.getData`
- `builder.globalCache.setData`

<details><summary>Code</summary>

```typescript
getHash( builder ) {

		if ( this.bufferCount === 0 ) {

			let bufferData = builder.globalCache.getData( this.value );

			if ( bufferData === undefined ) {

				bufferData = {
					node: this
				};

				builder.globalCache.setData( this.value, bufferData );

			}

			return bufferData.node.uuid;

		}

		return this.uuid;

	}
```
</details>

### `StorageBufferNode.getInputType(): string`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation to return a fixed value `'indirectStorageBuffer'` or `'storageBuffer'`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getInputType( /*builder*/ ) {

		return this.value.isIndirectStorageBufferAttribute ? 'indirectStorageBuffer' : 'storageBuffer';

	}
```
</details>

### `StorageBufferNode.element(indexNode: IndexNode): StorageArrayElementNode`

**JSDoc:**
```typescript
/**
	 * Enables element access with the given index node.
	 *
	 * @param {IndexNode} indexNode - The index node.
	 * @return {StorageArrayElementNode} A node representing the element access.
	 */
```

**Parameters:**

- **`indexNode`** `IndexNode`

**Returns:** `StorageArrayElementNode`

**Calls:**

- `storageElement (from ../utils/StorageArrayElementNode.js)`

<details><summary>Code</summary>

```typescript
element( indexNode ) {

		return storageElement( this, indexNode );

	}
```
</details>

### `StorageBufferNode.setPBO(value: boolean): StorageBufferNode`

**JSDoc:**
```typescript
/**
	 * Defines whether this node is a PBO or not. Only relevant for WebGL.
	 *
	 * @param {boolean} value - The value so set.
	 * @return {StorageBufferNode} A reference to this node.
	 */
```

**Parameters:**

- **`value`** `boolean`

**Returns:** `StorageBufferNode`

<details><summary>Code</summary>

```typescript
setPBO( value ) {

		this.isPBO = value;

		return this;

	}
```
</details>

### `StorageBufferNode.getPBO(): boolean`

**JSDoc:**
```typescript
/**
	 * Returns the `isPBO` value.
	 *
	 * @return {boolean} Whether the node represents a PBO or not.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
getPBO() {

		return this.isPBO;

	}
```
</details>

### `StorageBufferNode.setAccess(value: string): StorageBufferNode`

**JSDoc:**
```typescript
/**
	 * Defines the node access.
	 *
	 * @param {string} value - The node access.
	 * @return {StorageBufferNode} A reference to this node.
	 */
```

**Parameters:**

- **`value`** `string`

**Returns:** `StorageBufferNode`

<details><summary>Code</summary>

```typescript
setAccess( value ) {

		this.access = value;

		return this;

	}
```
</details>

### `StorageBufferNode.toReadOnly(): StorageBufferNode`

**JSDoc:**
```typescript
/**
	 * Convenience method for configuring a read-only node access.
	 *
	 * @return {StorageBufferNode} A reference to this node.
	 */
```

**Returns:** `StorageBufferNode`

**Calls:**

- `this.setAccess`

<details><summary>Code</summary>

```typescript
toReadOnly() {

		return this.setAccess( NodeAccess.READ_ONLY );

	}
```
</details>

### `StorageBufferNode.setAtomic(value: boolean): StorageBufferNode`

**JSDoc:**
```typescript
/**
	 * Defines whether the node is atomic or not.
	 *
	 * @param {boolean} value - The atomic flag.
	 * @return {StorageBufferNode} A reference to this node.
	 */
```

**Parameters:**

- **`value`** `boolean`

**Returns:** `StorageBufferNode`

<details><summary>Code</summary>

```typescript
setAtomic( value ) {

		this.isAtomic = value;

		return this;

	}
```
</details>

### `StorageBufferNode.toAtomic(): StorageBufferNode`

**JSDoc:**
```typescript
/**
	 * Convenience method for making this node atomic.
	 *
	 * @return {StorageBufferNode} A reference to this node.
	 */
```

**Returns:** `StorageBufferNode`

**Calls:**

- `this.setAtomic`

<details><summary>Code</summary>

```typescript
toAtomic() {

		return this.setAtomic( true );

	}
```
</details>

### `StorageBufferNode.getAttributeData(): { attribute: BufferAttributeNode; varying: VaryingNode; }`

**JSDoc:**
```typescript
/**
	 * Returns attribute data for this storage buffer node.
	 *
	 * @return {{attribute: BufferAttributeNode, varying: VaryingNode}} The attribute data.
	 */
```

**Returns:** `{ attribute: BufferAttributeNode; varying: VaryingNode; }`

**Calls:**

- `bufferAttribute (from ./BufferAttributeNode.js)`
- `varying (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
getAttributeData() {

		if ( this._attribute === null ) {

			this._attribute = bufferAttribute( this.value );
			this._varying = varying( this._attribute );

		}

		return {
			attribute: this._attribute,
			varying: this._varying
		};

	}
```
</details>

### `StorageBufferNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node type from the availability of storage buffers
	 * and the attribute data.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.structTypeNode.getNodeType`
- `builder.isAvailable`
- `super.getNodeType`
- `this.getAttributeData`
- `attribute.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		if ( this.structTypeNode !== null ) {

			return this.structTypeNode.getNodeType( builder );

		}

		if ( builder.isAvailable( 'storageBuffer' ) || builder.isAvailable( 'indirectStorageBuffer' ) ) {

			return super.getNodeType( builder );

		}

		const { attribute } = this.getAttributeData();

		return attribute.getNodeType( builder );

	}
```
</details>

### `StorageBufferNode.getMemberType(builder: NodeBuilder, name: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the type of a member of the struct.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {string} name - The name of the member.
	 * @return {string} The type of the member.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`name`** `string`

**Returns:** `string`

**Calls:**

- `this.structTypeNode.getMemberType`

<details><summary>Code</summary>

```typescript
getMemberType( builder, name ) {

		if ( this.structTypeNode !== null ) {

			return this.structTypeNode.getMemberType( builder, name );

		}

		return 'void';

	}
```
</details>

### `StorageBufferNode.generate(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * Generates the code snippet of the storage buffer node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The generated code snippet.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.structTypeNode.build`
- `builder.isAvailable`
- `super.generate`
- `this.getAttributeData`
- `varying.build`
- `builder.registerTransform`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		if ( this.structTypeNode !== null ) this.structTypeNode.build( builder );

		if ( builder.isAvailable( 'storageBuffer' ) || builder.isAvailable( 'indirectStorageBuffer' ) ) {

			return super.generate( builder );

		}

		const { attribute, varying } = this.getAttributeData();

		const output = varying.build( builder );

		builder.registerTransform( output, attribute );

		return output;

	}
```
</details>

### `storage(value: any, type: any, count: number): StorageBufferNode`

**Parameters:**

- **`value`** `any`
- **`type`** `any`
- **`count`** `number`

**Returns:** `StorageBufferNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( value, type = null, count = 0 ) => nodeObject( new StorageBufferNode( value, type, count ) )
```
</details>

### `storageObject(value: any, type: string, count: number): StorageBufferNode`

**Parameters:**

- **`value`** `any`
- **`type`** `string`
- **`count`** `number`

**Returns:** `StorageBufferNode`

**Calls:**

- `console.warn`
- `storage( value, type, count ).setPBO`

<details><summary>Code</summary>

```typescript
( value, type, count ) => { // @deprecated, r171

	console.warn( 'THREE.TSL: "storageObject()" is deprecated. Use "storage().setPBO( true )" instead.' );

	return storage( value, type, count ).setPBO( true );

}
```
</details>


---

## Classes

### `StorageBufferNode`

<details><summary>Class Code</summary>

```ts
class StorageBufferNode extends BufferNode {

	static get type() {

		return 'StorageBufferNode';

	}

	/**
	 * Constructs a new storage buffer node.
	 *
	 * @param {StorageBufferAttribute|StorageInstancedBufferAttribute|BufferAttribute} value - The buffer data.
	 * @param {?(string|Struct)} [bufferType=null] - The buffer type (e.g. `'vec3'`).
	 * @param {number} [bufferCount=0] - The buffer count.
	 */
	constructor( value, bufferType = null, bufferCount = 0 ) {

		let nodeType, structTypeNode = null;

		if ( bufferType && bufferType.isStruct ) {

			nodeType = 'struct';
			structTypeNode = bufferType.layout;

			if ( value.isStorageBufferAttribute || value.isStorageInstancedBufferAttribute ) {

				bufferCount = value.count;

			}

		} else if ( bufferType === null && ( value.isStorageBufferAttribute || value.isStorageInstancedBufferAttribute ) ) {

			nodeType = getTypeFromLength( value.itemSize );
			bufferCount = value.count;

		} else {

			nodeType = bufferType;

		}

		super( value, nodeType, bufferCount );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isStorageBufferNode = true;


		/**
		 * The buffer struct type.
		 *
		 * @type {?StructTypeNode}
		 * @default null
		 */
		this.structTypeNode = structTypeNode;

		/**
		 * The access type of the texture node.
		 *
		 * @type {string}
		 * @default 'readWrite'
		 */
		this.access = NodeAccess.READ_WRITE;

		/**
		 * Whether the node is atomic or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.isAtomic = false;

		/**
		 * Whether the node represents a PBO or not.
		 * Only relevant for WebGL.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.isPBO = false;

		/**
		 * A reference to the internal buffer attribute node.
		 *
		 * @type {?BufferAttributeNode}
		 * @default null
		 */
		this._attribute = null;

		/**
		 * A reference to the internal varying node.
		 *
		 * @type {?VaryingNode}
		 * @default null
		 */
		this._varying = null;

		/**
		 * `StorageBufferNode` sets this property to `true` by default.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.global = true;

		if ( value.isStorageBufferAttribute !== true && value.isStorageInstancedBufferAttribute !== true ) {

			// TODO: Improve it, possibly adding a new property to the BufferAttribute to identify it as a storage buffer read-only attribute in Renderer

			if ( value.isInstancedBufferAttribute ) value.isStorageInstancedBufferAttribute = true;
			else value.isStorageBufferAttribute = true;

		}

	}

	/**
	 * This method is overwritten since the buffer data might be shared
	 * and thus the hash should be shared as well.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The hash.
	 */
	getHash( builder ) {

		if ( this.bufferCount === 0 ) {

			let bufferData = builder.globalCache.getData( this.value );

			if ( bufferData === undefined ) {

				bufferData = {
					node: this
				};

				builder.globalCache.setData( this.value, bufferData );

			}

			return bufferData.node.uuid;

		}

		return this.uuid;

	}

	/**
	 * Overwrites the default implementation to return a fixed value `'indirectStorageBuffer'` or `'storageBuffer'`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
	getInputType( /*builder*/ ) {

		return this.value.isIndirectStorageBufferAttribute ? 'indirectStorageBuffer' : 'storageBuffer';

	}

	/**
	 * Enables element access with the given index node.
	 *
	 * @param {IndexNode} indexNode - The index node.
	 * @return {StorageArrayElementNode} A node representing the element access.
	 */
	element( indexNode ) {

		return storageElement( this, indexNode );

	}

	/**
	 * Defines whether this node is a PBO or not. Only relevant for WebGL.
	 *
	 * @param {boolean} value - The value so set.
	 * @return {StorageBufferNode} A reference to this node.
	 */
	setPBO( value ) {

		this.isPBO = value;

		return this;

	}

	/**
	 * Returns the `isPBO` value.
	 *
	 * @return {boolean} Whether the node represents a PBO or not.
	 */
	getPBO() {

		return this.isPBO;

	}

	/**
	 * Defines the node access.
	 *
	 * @param {string} value - The node access.
	 * @return {StorageBufferNode} A reference to this node.
	 */
	setAccess( value ) {

		this.access = value;

		return this;

	}

	/**
	 * Convenience method for configuring a read-only node access.
	 *
	 * @return {StorageBufferNode} A reference to this node.
	 */
	toReadOnly() {

		return this.setAccess( NodeAccess.READ_ONLY );

	}

	/**
	 * Defines whether the node is atomic or not.
	 *
	 * @param {boolean} value - The atomic flag.
	 * @return {StorageBufferNode} A reference to this node.
	 */
	setAtomic( value ) {

		this.isAtomic = value;

		return this;

	}

	/**
	 * Convenience method for making this node atomic.
	 *
	 * @return {StorageBufferNode} A reference to this node.
	 */
	toAtomic() {

		return this.setAtomic( true );

	}

	/**
	 * Returns attribute data for this storage buffer node.
	 *
	 * @return {{attribute: BufferAttributeNode, varying: VaryingNode}} The attribute data.
	 */
	getAttributeData() {

		if ( this._attribute === null ) {

			this._attribute = bufferAttribute( this.value );
			this._varying = varying( this._attribute );

		}

		return {
			attribute: this._attribute,
			varying: this._varying
		};

	}

	/**
	 * This method is overwritten since the node type from the availability of storage buffers
	 * and the attribute data.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( builder ) {

		if ( this.structTypeNode !== null ) {

			return this.structTypeNode.getNodeType( builder );

		}

		if ( builder.isAvailable( 'storageBuffer' ) || builder.isAvailable( 'indirectStorageBuffer' ) ) {

			return super.getNodeType( builder );

		}

		const { attribute } = this.getAttributeData();

		return attribute.getNodeType( builder );

	}

	/**
	 * Returns the type of a member of the struct.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {string} name - The name of the member.
	 * @return {string} The type of the member.
	 */
	getMemberType( builder, name ) {

		if ( this.structTypeNode !== null ) {

			return this.structTypeNode.getMemberType( builder, name );

		}

		return 'void';

	}

	/**
	 * Generates the code snippet of the storage buffer node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The generated code snippet.
	 */
	generate( builder ) {

		if ( this.structTypeNode !== null ) this.structTypeNode.build( builder );

		if ( builder.isAvailable( 'storageBuffer' ) || builder.isAvailable( 'indirectStorageBuffer' ) ) {

			return super.generate( builder );

		}

		const { attribute, varying } = this.getAttributeData();

		const output = varying.build( builder );

		builder.registerTransform( output, attribute );

		return output;

	}

}
```
</details>

#### Methods

##### `getHash(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getHash( builder ) {

		if ( this.bufferCount === 0 ) {

			let bufferData = builder.globalCache.getData( this.value );

			if ( bufferData === undefined ) {

				bufferData = {
					node: this
				};

				builder.globalCache.setData( this.value, bufferData );

			}

			return bufferData.node.uuid;

		}

		return this.uuid;

	}
```
</details>

##### `getInputType(): string`

<details><summary>Code</summary>

```ts
getInputType( /*builder*/ ) {

		return this.value.isIndirectStorageBufferAttribute ? 'indirectStorageBuffer' : 'storageBuffer';

	}
```
</details>

##### `element(indexNode: IndexNode): StorageArrayElementNode`

<details><summary>Code</summary>

```ts
element( indexNode ) {

		return storageElement( this, indexNode );

	}
```
</details>

##### `setPBO(value: boolean): StorageBufferNode`

<details><summary>Code</summary>

```ts
setPBO( value ) {

		this.isPBO = value;

		return this;

	}
```
</details>

##### `getPBO(): boolean`

<details><summary>Code</summary>

```ts
getPBO() {

		return this.isPBO;

	}
```
</details>

##### `setAccess(value: string): StorageBufferNode`

<details><summary>Code</summary>

```ts
setAccess( value ) {

		this.access = value;

		return this;

	}
```
</details>

##### `toReadOnly(): StorageBufferNode`

<details><summary>Code</summary>

```ts
toReadOnly() {

		return this.setAccess( NodeAccess.READ_ONLY );

	}
```
</details>

##### `setAtomic(value: boolean): StorageBufferNode`

<details><summary>Code</summary>

```ts
setAtomic( value ) {

		this.isAtomic = value;

		return this;

	}
```
</details>

##### `toAtomic(): StorageBufferNode`

<details><summary>Code</summary>

```ts
toAtomic() {

		return this.setAtomic( true );

	}
```
</details>

##### `getAttributeData(): { attribute: BufferAttributeNode; varying: VaryingNode; }`

<details><summary>Code</summary>

```ts
getAttributeData() {

		if ( this._attribute === null ) {

			this._attribute = bufferAttribute( this.value );
			this._varying = varying( this._attribute );

		}

		return {
			attribute: this._attribute,
			varying: this._varying
		};

	}
```
</details>

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		if ( this.structTypeNode !== null ) {

			return this.structTypeNode.getNodeType( builder );

		}

		if ( builder.isAvailable( 'storageBuffer' ) || builder.isAvailable( 'indirectStorageBuffer' ) ) {

			return super.getNodeType( builder );

		}

		const { attribute } = this.getAttributeData();

		return attribute.getNodeType( builder );

	}
```
</details>

##### `getMemberType(builder: NodeBuilder, name: string): string`

<details><summary>Code</summary>

```ts
getMemberType( builder, name ) {

		if ( this.structTypeNode !== null ) {

			return this.structTypeNode.getMemberType( builder, name );

		}

		return 'void';

	}
```
</details>

##### `generate(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
generate( builder ) {

		if ( this.structTypeNode !== null ) this.structTypeNode.build( builder );

		if ( builder.isAvailable( 'storageBuffer' ) || builder.isAvailable( 'indirectStorageBuffer' ) ) {

			return super.generate( builder );

		}

		const { attribute, varying } = this.getAttributeData();

		const output = varying.build( builder );

		builder.registerTransform( output, attribute );

		return output;

	}
```
</details>


---