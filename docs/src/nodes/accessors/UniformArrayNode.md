[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `UniformArrayNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 8 |
| 🧱 Classes | 2 |
| 📦 Imports | 5 |
| 📊 Variables & Constants | 18 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/UniformArrayNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `nodeObject` | `../tsl/TSLBase.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `getValueType` | `../core/NodeUtils.js` |
| `ArrayElementNode` | `../utils/ArrayElementNode.js` |
| `BufferNode` | `./BufferNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `elementType` | `string` | let/var | `this.elementType` | ✗ |
| `paddedType` | `string` | let/var | `'vec4'` | ✗ |
| `elementType` | `string` | let/var | `this.elementType` | ✗ |
| `index` | `number` | let/var | `i * 4` | ✗ |
| `index` | `number` | let/var | `i * 4` | ✗ |
| `vector` | `any` | let/var | `array[ i ]` | ✗ |
| `index` | `number` | let/var | `i * 4` | ✗ |
| `matrix` | `any` | let/var | `array[ i ]` | ✗ |
| `index` | `number` | let/var | `i * 16` | ✗ |
| `matrix` | `any` | let/var | `array[ i ]` | ✗ |
| `index` | `number` | let/var | `i * 16` | ✗ |
| `matrix` | `any` | let/var | `array[ i ]` | ✗ |
| `index` | `number` | let/var | `i * 4` | ✗ |
| `vector` | `any` | let/var | `array[ i ]` | ✗ |
| `length` | `number` | let/var | `this.array.length` | ✗ |
| `elementType` | `string` | let/var | `this.elementType` | ✗ |
| `arrayType` | `Float32ArrayConstructor` | let/var | `Float32Array` | ✗ |
| `paddedType` | `string` | let/var | `this.paddedType` | ✗ |


---

## Functions

### `UniformArrayElementNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `super.generate`
- `this.getNodeType`
- `this.node.getPaddedType`
- `builder.format`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		const snippet = super.generate( builder );
		const type = this.getNodeType();
		const paddedType = this.node.getPaddedType();

		return builder.format( snippet, paddedType, type );

	}
```
</details>

### `UniformArrayNode.getNodeType(): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node type is inferred from the
	 * {@link UniformArrayNode#paddedType}.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getNodeType( /*builder*/ ) {

		return this.paddedType;

	}
```
</details>

### `UniformArrayNode.getElementType(): string`

**JSDoc:**
```typescript
/**
	 * The data type of the array elements.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
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

### `UniformArrayNode.getPaddedType(): string`

**JSDoc:**
```typescript
/**
	 * Returns the padded type based on the element type.
	 *
	 * @return {string} The padded type.
	 */
```

**Returns:** `string`

**Calls:**

- `/mat/.test`
- `elementType.charAt`

<details><summary>Code</summary>

```typescript
getPaddedType() {

		const elementType = this.elementType;

		let paddedType = 'vec4';

		if ( elementType === 'mat2' ) {

			paddedType = 'mat2';

		} else if ( /mat/.test( elementType ) === true ) {

			paddedType = 'mat4';

		} else if ( elementType.charAt( 0 ) === 'i' ) {

			paddedType = 'ivec4';

		} else if ( elementType.charAt( 0 ) === 'u' ) {

			paddedType = 'uvec4';

		}

		return paddedType;

	}
```
</details>

### `UniformArrayNode.update(): void`

**JSDoc:**
```typescript
/**
	 * The update makes sure to correctly transfer the data from the (complex) objects
	 * in the array to the internal, correctly padded value buffer.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
update( /*frame*/ ) {

		const { array, value } = this;

		const elementType = this.elementType;

		if ( elementType === 'float' || elementType === 'int' || elementType === 'uint' ) {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 4;

				value[ index ] = array[ i ];

			}

		} else if ( elementType === 'color' ) {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 4;
				const vector = array[ i ];

				value[ index ] = vector.r;
				value[ index + 1 ] = vector.g;
				value[ index + 2 ] = vector.b || 0;
				//value[ index + 3 ] = vector.a || 0;

			}

		} else if ( elementType === 'mat2' ) {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 4;
				const matrix = array[ i ];

				value[ index ] = matrix.elements[ 0 ];
				value[ index + 1 ] = matrix.elements[ 1 ];
				value[ index + 2 ] = matrix.elements[ 2 ];
				value[ index + 3 ] = matrix.elements[ 3 ];

			}

		} else if ( elementType === 'mat3' ) {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 16;
				const matrix = array[ i ];

				value[ index ] = matrix.elements[ 0 ];
				value[ index + 1 ] = matrix.elements[ 1 ];
				value[ index + 2 ] = matrix.elements[ 2 ];

				value[ index + 4 ] = matrix.elements[ 3 ];
				value[ index + 5 ] = matrix.elements[ 4 ];
				value[ index + 6 ] = matrix.elements[ 5 ];

				value[ index + 8 ] = matrix.elements[ 6 ];
				value[ index + 9 ] = matrix.elements[ 7 ];
				value[ index + 10 ] = matrix.elements[ 8 ];

				value[ index + 15 ] = 1;

			}

		} else if ( elementType === 'mat4' ) {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 16;
				const matrix = array[ i ];

				for ( let i = 0; i < matrix.elements.length; i ++ ) {

					value[ index + i ] = matrix.elements[ i ];

				}

			}

		} else {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 4;
				const vector = array[ i ];

				value[ index ] = vector.x;
				value[ index + 1 ] = vector.y;
				value[ index + 2 ] = vector.z || 0;
				value[ index + 3 ] = vector.w || 0;

			}

		}

	}
```
</details>

### `UniformArrayNode.setup(builder: NodeBuilder): null`

**JSDoc:**
```typescript
/**
	 * Implement the value buffer creation based on the array data.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @return {null}
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `null`

**Calls:**

- `builder.getTypeLength`
- `elementType.charAt`
- `super.setup`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const length = this.array.length;
		const elementType = this.elementType;

		let arrayType = Float32Array;

		const paddedType = this.paddedType;
		const paddedElementLength = builder.getTypeLength( paddedType );

		if ( elementType.charAt( 0 ) === 'i' ) arrayType = Int32Array;
		if ( elementType.charAt( 0 ) === 'u' ) arrayType = Uint32Array;

		this.value = new arrayType( length * paddedElementLength );
		this.bufferCount = length;
		this.bufferType = paddedType;

		return super.setup( builder );

	}
```
</details>

### `UniformArrayNode.element(indexNode: IndexNode): UniformArrayElementNode`

**JSDoc:**
```typescript
/**
	 * Overwrites the default `element()` method to provide element access
	 * based on {@link UniformArrayNode}.
	 *
	 * @param {IndexNode} indexNode - The index node.
	 * @return {UniformArrayElementNode}
	 */
```

**Parameters:**

- **`indexNode`** `IndexNode`

**Returns:** `UniformArrayElementNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
element( indexNode ) {

		return nodeObject( new UniformArrayElementNode( this, nodeObject( indexNode ) ) );

	}
```
</details>

### `uniformArray(values: any[], nodeType: string): UniformArrayNode`

**Parameters:**

- **`values`** `any[]`
- **`nodeType`** `string`

**Returns:** `UniformArrayNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( values, nodeType ) => nodeObject( new UniformArrayNode( values, nodeType ) )
```
</details>


---

## Classes

### `UniformArrayElementNode`

<details><summary>Class Code</summary>

```ts
class UniformArrayElementNode extends ArrayElementNode {

	static get type() {

		return 'UniformArrayElementNode';

	}

	/**
	 * Constructs a new buffer node.
	 *
	 * @param {UniformArrayNode} uniformArrayNode - The uniform array node to access.
	 * @param {IndexNode} indexNode - The index data that define the position of the accessed element in the array.
	 */
	constructor( uniformArrayNode, indexNode ) {

		super( uniformArrayNode, indexNode );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isArrayBufferElementNode = true;

	}

	generate( builder ) {

		const snippet = super.generate( builder );
		const type = this.getNodeType();
		const paddedType = this.node.getPaddedType();

		return builder.format( snippet, paddedType, type );

	}

}
```
</details>

#### Methods

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		const snippet = super.generate( builder );
		const type = this.getNodeType();
		const paddedType = this.node.getPaddedType();

		return builder.format( snippet, paddedType, type );

	}
```
</details>

### `UniformArrayNode`

<details><summary>Class Code</summary>

```ts
class UniformArrayNode extends BufferNode {

	static get type() {

		return 'UniformArrayNode';

	}

	/**
	 * Constructs a new uniform array node.
	 *
	 * @param {Array<any>} value - Array holding the buffer data.
	 * @param {?string} [elementType=null] - The data type of a buffer element.
	 */
	constructor( value, elementType = null ) {

		super( null );

		/**
		 * Array holding the buffer data. Unlike {@link BufferNode}, the array can
		 * hold number primitives as well as three.js objects like vectors, matrices
		 * or colors.
		 *
		 * @type {Array<any>}
		 */
		this.array = value;

		/**
		 * The data type of an array element.
		 *
		 * @type {string}
		 */
		this.elementType = elementType === null ? getValueType( value[ 0 ] ) : elementType;

		/**
		 * The padded type. Uniform buffers must conform to a certain buffer layout
		 * so a separate type is computed to ensure correct buffer size.
		 *
		 * @type {string}
		 */
		this.paddedType = this.getPaddedType();

		/**
		 * Overwritten since uniform array nodes are updated per render.
		 *
		 * @type {string}
		 * @default 'render'
		 */
		this.updateType = NodeUpdateType.RENDER;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isArrayBufferNode = true;

	}

	/**
	 * This method is overwritten since the node type is inferred from the
	 * {@link UniformArrayNode#paddedType}.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( /*builder*/ ) {

		return this.paddedType;

	}

	/**
	 * The data type of the array elements.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The element type.
	 */
	getElementType() {

		return this.elementType;

	}

	/**
	 * Returns the padded type based on the element type.
	 *
	 * @return {string} The padded type.
	 */
	getPaddedType() {

		const elementType = this.elementType;

		let paddedType = 'vec4';

		if ( elementType === 'mat2' ) {

			paddedType = 'mat2';

		} else if ( /mat/.test( elementType ) === true ) {

			paddedType = 'mat4';

		} else if ( elementType.charAt( 0 ) === 'i' ) {

			paddedType = 'ivec4';

		} else if ( elementType.charAt( 0 ) === 'u' ) {

			paddedType = 'uvec4';

		}

		return paddedType;

	}

	/**
	 * The update makes sure to correctly transfer the data from the (complex) objects
	 * in the array to the internal, correctly padded value buffer.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
	update( /*frame*/ ) {

		const { array, value } = this;

		const elementType = this.elementType;

		if ( elementType === 'float' || elementType === 'int' || elementType === 'uint' ) {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 4;

				value[ index ] = array[ i ];

			}

		} else if ( elementType === 'color' ) {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 4;
				const vector = array[ i ];

				value[ index ] = vector.r;
				value[ index + 1 ] = vector.g;
				value[ index + 2 ] = vector.b || 0;
				//value[ index + 3 ] = vector.a || 0;

			}

		} else if ( elementType === 'mat2' ) {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 4;
				const matrix = array[ i ];

				value[ index ] = matrix.elements[ 0 ];
				value[ index + 1 ] = matrix.elements[ 1 ];
				value[ index + 2 ] = matrix.elements[ 2 ];
				value[ index + 3 ] = matrix.elements[ 3 ];

			}

		} else if ( elementType === 'mat3' ) {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 16;
				const matrix = array[ i ];

				value[ index ] = matrix.elements[ 0 ];
				value[ index + 1 ] = matrix.elements[ 1 ];
				value[ index + 2 ] = matrix.elements[ 2 ];

				value[ index + 4 ] = matrix.elements[ 3 ];
				value[ index + 5 ] = matrix.elements[ 4 ];
				value[ index + 6 ] = matrix.elements[ 5 ];

				value[ index + 8 ] = matrix.elements[ 6 ];
				value[ index + 9 ] = matrix.elements[ 7 ];
				value[ index + 10 ] = matrix.elements[ 8 ];

				value[ index + 15 ] = 1;

			}

		} else if ( elementType === 'mat4' ) {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 16;
				const matrix = array[ i ];

				for ( let i = 0; i < matrix.elements.length; i ++ ) {

					value[ index + i ] = matrix.elements[ i ];

				}

			}

		} else {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 4;
				const vector = array[ i ];

				value[ index ] = vector.x;
				value[ index + 1 ] = vector.y;
				value[ index + 2 ] = vector.z || 0;
				value[ index + 3 ] = vector.w || 0;

			}

		}

	}

	/**
	 * Implement the value buffer creation based on the array data.
	 *
	 * @param {NodeBuilder} builder - A reference to the current node builder.
	 * @return {null}
	 */
	setup( builder ) {

		const length = this.array.length;
		const elementType = this.elementType;

		let arrayType = Float32Array;

		const paddedType = this.paddedType;
		const paddedElementLength = builder.getTypeLength( paddedType );

		if ( elementType.charAt( 0 ) === 'i' ) arrayType = Int32Array;
		if ( elementType.charAt( 0 ) === 'u' ) arrayType = Uint32Array;

		this.value = new arrayType( length * paddedElementLength );
		this.bufferCount = length;
		this.bufferType = paddedType;

		return super.setup( builder );

	}

	/**
	 * Overwrites the default `element()` method to provide element access
	 * based on {@link UniformArrayNode}.
	 *
	 * @param {IndexNode} indexNode - The index node.
	 * @return {UniformArrayElementNode}
	 */
	element( indexNode ) {

		return nodeObject( new UniformArrayElementNode( this, nodeObject( indexNode ) ) );

	}

}
```
</details>

#### Methods

##### `getNodeType(): string`

<details><summary>Code</summary>

```ts
getNodeType( /*builder*/ ) {

		return this.paddedType;

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

##### `getPaddedType(): string`

<details><summary>Code</summary>

```ts
getPaddedType() {

		const elementType = this.elementType;

		let paddedType = 'vec4';

		if ( elementType === 'mat2' ) {

			paddedType = 'mat2';

		} else if ( /mat/.test( elementType ) === true ) {

			paddedType = 'mat4';

		} else if ( elementType.charAt( 0 ) === 'i' ) {

			paddedType = 'ivec4';

		} else if ( elementType.charAt( 0 ) === 'u' ) {

			paddedType = 'uvec4';

		}

		return paddedType;

	}
```
</details>

##### `update(): void`

<details><summary>Code</summary>

```ts
update( /*frame*/ ) {

		const { array, value } = this;

		const elementType = this.elementType;

		if ( elementType === 'float' || elementType === 'int' || elementType === 'uint' ) {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 4;

				value[ index ] = array[ i ];

			}

		} else if ( elementType === 'color' ) {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 4;
				const vector = array[ i ];

				value[ index ] = vector.r;
				value[ index + 1 ] = vector.g;
				value[ index + 2 ] = vector.b || 0;
				//value[ index + 3 ] = vector.a || 0;

			}

		} else if ( elementType === 'mat2' ) {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 4;
				const matrix = array[ i ];

				value[ index ] = matrix.elements[ 0 ];
				value[ index + 1 ] = matrix.elements[ 1 ];
				value[ index + 2 ] = matrix.elements[ 2 ];
				value[ index + 3 ] = matrix.elements[ 3 ];

			}

		} else if ( elementType === 'mat3' ) {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 16;
				const matrix = array[ i ];

				value[ index ] = matrix.elements[ 0 ];
				value[ index + 1 ] = matrix.elements[ 1 ];
				value[ index + 2 ] = matrix.elements[ 2 ];

				value[ index + 4 ] = matrix.elements[ 3 ];
				value[ index + 5 ] = matrix.elements[ 4 ];
				value[ index + 6 ] = matrix.elements[ 5 ];

				value[ index + 8 ] = matrix.elements[ 6 ];
				value[ index + 9 ] = matrix.elements[ 7 ];
				value[ index + 10 ] = matrix.elements[ 8 ];

				value[ index + 15 ] = 1;

			}

		} else if ( elementType === 'mat4' ) {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 16;
				const matrix = array[ i ];

				for ( let i = 0; i < matrix.elements.length; i ++ ) {

					value[ index + i ] = matrix.elements[ i ];

				}

			}

		} else {

			for ( let i = 0; i < array.length; i ++ ) {

				const index = i * 4;
				const vector = array[ i ];

				value[ index ] = vector.x;
				value[ index + 1 ] = vector.y;
				value[ index + 2 ] = vector.z || 0;
				value[ index + 3 ] = vector.w || 0;

			}

		}

	}
```
</details>

##### `setup(builder: NodeBuilder): null`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const length = this.array.length;
		const elementType = this.elementType;

		let arrayType = Float32Array;

		const paddedType = this.paddedType;
		const paddedElementLength = builder.getTypeLength( paddedType );

		if ( elementType.charAt( 0 ) === 'i' ) arrayType = Int32Array;
		if ( elementType.charAt( 0 ) === 'u' ) arrayType = Uint32Array;

		this.value = new arrayType( length * paddedElementLength );
		this.bufferCount = length;
		this.bufferType = paddedType;

		return super.setup( builder );

	}
```
</details>

##### `element(indexNode: IndexNode): UniformArrayElementNode`

<details><summary>Code</summary>

```ts
element( indexNode ) {

		return nodeObject( new UniformArrayElementNode( this, nodeObject( indexNode ) ) );

	}
```
</details>


---