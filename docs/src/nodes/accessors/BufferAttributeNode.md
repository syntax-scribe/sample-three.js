[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BufferAttributeNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 11 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/BufferAttributeNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `InputNode` | `../core/InputNode.js` |
| `nodeObject` | `../tsl/TSLCore.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `varying` | `../core/VaryingNode.js` |
| `InterleavedBufferAttribute` | `../../core/InterleavedBufferAttribute.js` |
| `InterleavedBuffer` | `../../core/InterleavedBuffer.js` |
| `StaticDrawUsage` | `../../constants.js` |
| `DynamicDrawUsage` | `../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `array` | `any` | let/var | `this.value` | ✗ |
| `stride` | `any` | let/var | `this.bufferStride \|\| itemSize` | ✗ |
| `offset` | `number` | let/var | `this.bufferOffset` | ✗ |
| `buffer` | `any` | let/var | `array.isInterleavedBuffer === true ? array : new InterleavedBuffer( array, st...` | ✗ |
| `bufferAttribute` | `InterleavedBufferAttribute` | let/var | `new InterleavedBufferAttribute( buffer, itemSize, offset )` | ✗ |
| `output` | `any` | let/var | `null` | ✗ |


---

## Functions

### `BufferAttributeNode.getHash(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the attribute data might be shared
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

		if ( this.bufferStride === 0 && this.bufferOffset === 0 ) {

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

### `BufferAttributeNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node type is inferred from
	 * the buffer attribute.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `builder.getTypeFromAttribute`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		if ( this.bufferType === null ) {

			this.bufferType = builder.getTypeFromAttribute( this.attribute );

		}

		return this.bufferType;

	}
```
</details>

### `BufferAttributeNode.setup(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Depending on which value was passed to the node, `setup()` behaves
	 * differently. If no instance of `BufferAttribute` was passed, the method
	 * creates an internal attribute and configures it respectively.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `this.getNodeType`
- `builder.getTypeLength`
- `buffer.setUsage`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		if ( this.attribute !== null ) return;

		const type = this.getNodeType( builder );
		const array = this.value;
		const itemSize = builder.getTypeLength( type );
		const stride = this.bufferStride || itemSize;
		const offset = this.bufferOffset;

		const buffer = array.isInterleavedBuffer === true ? array : new InterleavedBuffer( array, stride );
		const bufferAttribute = new InterleavedBufferAttribute( buffer, itemSize, offset );

		buffer.setUsage( this.usage );

		this.attribute = bufferAttribute;
		this.attribute.isInstancedBufferAttribute = this.instanced; // @TODO: Add a possible: InstancedInterleavedBufferAttribute

	}
```
</details>

### `BufferAttributeNode.generate(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * Generates the code snippet of the buffer attribute node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The generated code snippet.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.getNodeType`
- `builder.getBufferAttributeFromNode`
- `builder.getPropertyName`
- `varying (from ../core/VaryingNode.js)`
- `nodeVarying.build`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const nodeType = this.getNodeType( builder );

		const nodeAttribute = builder.getBufferAttributeFromNode( this, nodeType );
		const propertyName = builder.getPropertyName( nodeAttribute );

		let output = null;

		if ( builder.shaderStage === 'vertex' || builder.shaderStage === 'compute' ) {

			this.name = propertyName;

			output = propertyName;

		} else {

			const nodeVarying = varying( this );

			output = nodeVarying.build( builder, nodeType );

		}

		return output;

	}
```
</details>

### `BufferAttributeNode.getInputType(): string`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation to return a fixed value `'bufferAttribute'`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getInputType( /*builder*/ ) {

		return 'bufferAttribute';

	}
```
</details>

### `BufferAttributeNode.setUsage(value: number): BufferAttributeNode`

**JSDoc:**
```typescript
/**
	 * Sets the `usage` property to the given value.
	 *
	 * @param {number} value - The usage to set.
	 * @return {BufferAttributeNode} A reference to this node.
	 */
```

**Parameters:**

- **`value`** `number`

**Returns:** `BufferAttributeNode`

<details><summary>Code</summary>

```typescript
setUsage( value ) {

		this.usage = value;

		if ( this.attribute && this.attribute.isBufferAttribute === true ) {

			this.attribute.usage = value;

		}

		return this;

	}
```
</details>

### `BufferAttributeNode.setInstanced(value: boolean): BufferAttributeNode`

**JSDoc:**
```typescript
/**
	 * Sets the `instanced` property to the given value.
	 *
	 * @param {boolean} value - The value to set.
	 * @return {BufferAttributeNode} A reference to this node.
	 */
```

**Parameters:**

- **`value`** `boolean`

**Returns:** `BufferAttributeNode`

<details><summary>Code</summary>

```typescript
setInstanced( value ) {

		this.instanced = value;

		return this;

	}
```
</details>

### `bufferAttribute(array: any, type: string, stride: number, offset: number): BufferAttributeNode`

**Parameters:**

- **`array`** `any`
- **`type`** `string`
- **`stride`** `number`
- **`offset`** `number`

**Returns:** `BufferAttributeNode`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( array, type = null, stride = 0, offset = 0 ) => nodeObject( new BufferAttributeNode( array, type, stride, offset ) )
```
</details>

### `dynamicBufferAttribute(array: any, type: string, stride: number, offset: number): BufferAttributeNode`

**Parameters:**

- **`array`** `any`
- **`type`** `string`
- **`stride`** `number`
- **`offset`** `number`

**Returns:** `BufferAttributeNode`

**Calls:**

- `bufferAttribute( array, type, stride, offset ).setUsage`

<details><summary>Code</summary>

```typescript
( array, type = null, stride = 0, offset = 0 ) => bufferAttribute( array, type, stride, offset ).setUsage( DynamicDrawUsage )
```
</details>

### `instancedBufferAttribute(array: any, type: string, stride: number, offset: number): BufferAttributeNode`

**Parameters:**

- **`array`** `any`
- **`type`** `string`
- **`stride`** `number`
- **`offset`** `number`

**Returns:** `BufferAttributeNode`

**Calls:**

- `bufferAttribute( array, type, stride, offset ).setInstanced`

<details><summary>Code</summary>

```typescript
( array, type = null, stride = 0, offset = 0 ) => bufferAttribute( array, type, stride, offset ).setInstanced( true )
```
</details>

### `instancedDynamicBufferAttribute(array: any, type: string, stride: number, offset: number): BufferAttributeNode`

**Parameters:**

- **`array`** `any`
- **`type`** `string`
- **`stride`** `number`
- **`offset`** `number`

**Returns:** `BufferAttributeNode`

**Calls:**

- `dynamicBufferAttribute( array, type, stride, offset ).setInstanced`

<details><summary>Code</summary>

```typescript
( array, type = null, stride = 0, offset = 0 ) => dynamicBufferAttribute( array, type, stride, offset ).setInstanced( true )
```
</details>


---

## Classes

### `BufferAttributeNode`

<details><summary>Class Code</summary>

```ts
class BufferAttributeNode extends InputNode {

	static get type() {

		return 'BufferAttributeNode';

	}

	/**
	 * Constructs a new buffer attribute node.
	 *
	 * @param {BufferAttribute|InterleavedBuffer|TypedArray} value - The attribute data.
	 * @param {?string} [bufferType=null] - The buffer type (e.g. `'vec3'`).
	 * @param {number} [bufferStride=0] - The buffer stride.
	 * @param {number} [bufferOffset=0] - The buffer offset.
	 */
	constructor( value, bufferType = null, bufferStride = 0, bufferOffset = 0 ) {

		super( value, bufferType );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isBufferNode = true;

		/**
		 * The buffer type (e.g. `'vec3'`).
		 *
		 * @type {?string}
		 * @default null
		 */
		this.bufferType = bufferType;

		/**
		 * The buffer stride.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.bufferStride = bufferStride;

		/**
		 * The buffer offset.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.bufferOffset = bufferOffset;

		/**
		 * The usage property. Set this to `THREE.DynamicDrawUsage` via `.setUsage()`,
		 * if you are planning to update the attribute data per frame.
		 *
		 * @type {number}
		 * @default StaticDrawUsage
		 */
		this.usage = StaticDrawUsage;

		/**
		 * Whether the attribute is instanced or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.instanced = false;

		/**
		 * A reference to the buffer attribute.
		 *
		 * @type {?BufferAttribute}
		 * @default null
		 */
		this.attribute = null;

		/**
		 * `BufferAttributeNode` sets this property to `true` by default.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.global = true;

		if ( value && value.isBufferAttribute === true ) {

			this.attribute = value;
			this.usage = value.usage;
			this.instanced = value.isInstancedBufferAttribute;

		}

	}

	/**
	 * This method is overwritten since the attribute data might be shared
	 * and thus the hash should be shared as well.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The hash.
	 */
	getHash( builder ) {

		if ( this.bufferStride === 0 && this.bufferOffset === 0 ) {

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
	 * This method is overwritten since the node type is inferred from
	 * the buffer attribute.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( builder ) {

		if ( this.bufferType === null ) {

			this.bufferType = builder.getTypeFromAttribute( this.attribute );

		}

		return this.bufferType;

	}

	/**
	 * Depending on which value was passed to the node, `setup()` behaves
	 * differently. If no instance of `BufferAttribute` was passed, the method
	 * creates an internal attribute and configures it respectively.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	setup( builder ) {

		if ( this.attribute !== null ) return;

		const type = this.getNodeType( builder );
		const array = this.value;
		const itemSize = builder.getTypeLength( type );
		const stride = this.bufferStride || itemSize;
		const offset = this.bufferOffset;

		const buffer = array.isInterleavedBuffer === true ? array : new InterleavedBuffer( array, stride );
		const bufferAttribute = new InterleavedBufferAttribute( buffer, itemSize, offset );

		buffer.setUsage( this.usage );

		this.attribute = bufferAttribute;
		this.attribute.isInstancedBufferAttribute = this.instanced; // @TODO: Add a possible: InstancedInterleavedBufferAttribute

	}

	/**
	 * Generates the code snippet of the buffer attribute node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The generated code snippet.
	 */
	generate( builder ) {

		const nodeType = this.getNodeType( builder );

		const nodeAttribute = builder.getBufferAttributeFromNode( this, nodeType );
		const propertyName = builder.getPropertyName( nodeAttribute );

		let output = null;

		if ( builder.shaderStage === 'vertex' || builder.shaderStage === 'compute' ) {

			this.name = propertyName;

			output = propertyName;

		} else {

			const nodeVarying = varying( this );

			output = nodeVarying.build( builder, nodeType );

		}

		return output;

	}

	/**
	 * Overwrites the default implementation to return a fixed value `'bufferAttribute'`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
	getInputType( /*builder*/ ) {

		return 'bufferAttribute';

	}

	/**
	 * Sets the `usage` property to the given value.
	 *
	 * @param {number} value - The usage to set.
	 * @return {BufferAttributeNode} A reference to this node.
	 */
	setUsage( value ) {

		this.usage = value;

		if ( this.attribute && this.attribute.isBufferAttribute === true ) {

			this.attribute.usage = value;

		}

		return this;

	}

	/**
	 * Sets the `instanced` property to the given value.
	 *
	 * @param {boolean} value - The value to set.
	 * @return {BufferAttributeNode} A reference to this node.
	 */
	setInstanced( value ) {

		this.instanced = value;

		return this;

	}

}
```
</details>

#### Methods

##### `getHash(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getHash( builder ) {

		if ( this.bufferStride === 0 && this.bufferOffset === 0 ) {

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

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		if ( this.bufferType === null ) {

			this.bufferType = builder.getTypeFromAttribute( this.attribute );

		}

		return this.bufferType;

	}
```
</details>

##### `setup(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		if ( this.attribute !== null ) return;

		const type = this.getNodeType( builder );
		const array = this.value;
		const itemSize = builder.getTypeLength( type );
		const stride = this.bufferStride || itemSize;
		const offset = this.bufferOffset;

		const buffer = array.isInterleavedBuffer === true ? array : new InterleavedBuffer( array, stride );
		const bufferAttribute = new InterleavedBufferAttribute( buffer, itemSize, offset );

		buffer.setUsage( this.usage );

		this.attribute = bufferAttribute;
		this.attribute.isInstancedBufferAttribute = this.instanced; // @TODO: Add a possible: InstancedInterleavedBufferAttribute

	}
```
</details>

##### `generate(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const nodeType = this.getNodeType( builder );

		const nodeAttribute = builder.getBufferAttributeFromNode( this, nodeType );
		const propertyName = builder.getPropertyName( nodeAttribute );

		let output = null;

		if ( builder.shaderStage === 'vertex' || builder.shaderStage === 'compute' ) {

			this.name = propertyName;

			output = propertyName;

		} else {

			const nodeVarying = varying( this );

			output = nodeVarying.build( builder, nodeType );

		}

		return output;

	}
```
</details>

##### `getInputType(): string`

<details><summary>Code</summary>

```ts
getInputType( /*builder*/ ) {

		return 'bufferAttribute';

	}
```
</details>

##### `setUsage(value: number): BufferAttributeNode`

<details><summary>Code</summary>

```ts
setUsage( value ) {

		this.usage = value;

		if ( this.attribute && this.attribute.isBufferAttribute === true ) {

			this.attribute.usage = value;

		}

		return this;

	}
```
</details>

##### `setInstanced(value: boolean): BufferAttributeNode`

<details><summary>Code</summary>

```ts
setInstanced( value ) {

		this.instanced = value;

		return this;

	}
```
</details>


---