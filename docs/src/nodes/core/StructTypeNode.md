[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `StructTypeNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 8 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/StructTypeNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `./Node.js` |
| `getByteBoundaryFromType` | `./NodeUtils.js` |
| `getMemoryLengthFromType` | `./NodeUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `GPU_CHUNK_BYTES` | `8` | let/var | `8` | ✗ |
| `BYTES_PER_ELEMENT` | `number` | let/var | `Float32Array.BYTES_PER_ELEMENT` | ✗ |
| `offset` | `number` | let/var | `0` | ✗ |
| `type` | `string` | let/var | `member.type` | ✗ |
| `itemSize` | `number` | let/var | `getMemoryLengthFromType( type ) * BYTES_PER_ELEMENT` | ✗ |
| `chunkOffset` | `number` | let/var | `offset % GPU_CHUNK_BYTES` | ✗ |
| `chunkPadding` | `number` | let/var | `chunkOffset % boundary` | ✗ |
| `chunkStart` | `number` | let/var | `chunkOffset + chunkPadding` | ✗ |


---

## Functions

### `getMembersLayout(members: { [x: string]: any; }): { name: string; type: string; atomic: boolean; }[]`

**JSDoc:**
```typescript
/**
 * Generates a layout for struct members.
 * This function takes an object representing struct members and returns an array of member layouts.
 * Each member layout includes the member's name, type, and whether it is atomic.
 *
 * @param {Object.<string, string|Object>} members - An object where keys are member names and values are either types (as strings) or objects with type and atomic properties.
 * @returns {Array.<{name: string, type: string, atomic: boolean}>} An array of member layouts.
 */
```

**Parameters:**

- **`members`** `{ [x: string]: any; }`

**Returns:** `{ name: string; type: string; atomic: boolean; }[]`

**Calls:**

- `Object.entries( members ).map`

<details><summary>Code</summary>

```typescript
function getMembersLayout( members ) {

	return Object.entries( members ).map( ( [ name, value ] ) => {

		if ( typeof value === 'string' ) {

			return { name, type: value, atomic: false };

		}

		return { name, type: value.type, atomic: value.atomic || false };

	} );

}
```
</details>

### `StructTypeNode.getLength(): number`

**JSDoc:**
```typescript
/**
	 * Returns the length of the struct.
	 * The length is calculated by summing the lengths of the struct's members.
	 *
	 * @returns {number} The length of the struct.
	 */
```

**Returns:** `number`

**Calls:**

- `getMemoryLengthFromType (from ./NodeUtils.js)`
- `getByteBoundaryFromType (from ./NodeUtils.js)`
- `Math.ceil`

**Internal Comments:**
```
// Check for chunk overflow
// Add padding to the end of the chunk (x3)
```

<details><summary>Code</summary>

```typescript
getLength() {

		const GPU_CHUNK_BYTES = 8;
		const BYTES_PER_ELEMENT = Float32Array.BYTES_PER_ELEMENT;

		let offset = 0; // global buffer offset in bytes

		for ( const member of this.membersLayout ) {

			const type = member.type;

			const itemSize = getMemoryLengthFromType( type ) * BYTES_PER_ELEMENT;
			const boundary = getByteBoundaryFromType( type );

			const chunkOffset = offset % GPU_CHUNK_BYTES; // offset in the current chunk
			const chunkPadding = chunkOffset % boundary; // required padding to match boundary
			const chunkStart = chunkOffset + chunkPadding; // start position in the current chunk for the data

			offset += chunkPadding;

			// Check for chunk overflow
			if ( chunkStart !== 0 && ( GPU_CHUNK_BYTES - chunkStart ) < itemSize ) {

				// Add padding to the end of the chunk
				offset += ( GPU_CHUNK_BYTES - chunkStart );

			}

			offset += itemSize;

		}

		return ( Math.ceil( offset / GPU_CHUNK_BYTES ) * GPU_CHUNK_BYTES ) / BYTES_PER_ELEMENT;

	}
```
</details>

### `StructTypeNode.getMemberType(builder: any, name: any): string`

**Parameters:**

- **`builder`** `any`
- **`name`** `any`

**Returns:** `string`

**Calls:**

- `this.membersLayout.find`

<details><summary>Code</summary>

```typescript
getMemberType( builder, name ) {

		const member = this.membersLayout.find( m => m.name === name );

		return member ? member.type : 'void';

	}
```
</details>

### `StructTypeNode.getNodeType(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.getStructTypeFromNode`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		const structType = builder.getStructTypeFromNode( this, this.membersLayout, this.name );

		return structType.name;

	}
```
</details>

### `StructTypeNode.setup(builder: any): void`

**Parameters:**

- **`builder`** `any`

**Returns:** `void`

**Calls:**

- `builder.addInclude`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		builder.addInclude( this );

	}
```
</details>

### `StructTypeNode.generate(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this.getNodeType`

<details><summary>Code</summary>

```typescript
generate( builder ) {

		return this.getNodeType( builder );

	}
```
</details>


---

## Classes

### `StructTypeNode`

<details><summary>Class Code</summary>

```ts
class StructTypeNode extends Node {

	static get type() {

		return 'StructTypeNode';

	}

	/**
	 * Creates an instance of StructTypeNode.
	 *
	 * @param {Object} membersLayout - The layout of the members for the struct.
	 * @param {?string} [name=null] - The optional name of the struct.
	 */
	constructor( membersLayout, name = null ) {

		super( 'struct' );

		/**
		 * The layout of the members for the struct
		 *
		 * @type {Array.<{name: string, type: string, atomic: boolean}>}
		 */
		this.membersLayout = getMembersLayout( membersLayout );

		/**
		 * The name of the struct.
		 *
		 * @type {?string}
		 * @default null
		 */
		this.name = name;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isStructLayoutNode = true;

	}

	/**
	 * Returns the length of the struct.
	 * The length is calculated by summing the lengths of the struct's members.
	 *
	 * @returns {number} The length of the struct.
	 */
	getLength() {

		const GPU_CHUNK_BYTES = 8;
		const BYTES_PER_ELEMENT = Float32Array.BYTES_PER_ELEMENT;

		let offset = 0; // global buffer offset in bytes

		for ( const member of this.membersLayout ) {

			const type = member.type;

			const itemSize = getMemoryLengthFromType( type ) * BYTES_PER_ELEMENT;
			const boundary = getByteBoundaryFromType( type );

			const chunkOffset = offset % GPU_CHUNK_BYTES; // offset in the current chunk
			const chunkPadding = chunkOffset % boundary; // required padding to match boundary
			const chunkStart = chunkOffset + chunkPadding; // start position in the current chunk for the data

			offset += chunkPadding;

			// Check for chunk overflow
			if ( chunkStart !== 0 && ( GPU_CHUNK_BYTES - chunkStart ) < itemSize ) {

				// Add padding to the end of the chunk
				offset += ( GPU_CHUNK_BYTES - chunkStart );

			}

			offset += itemSize;

		}

		return ( Math.ceil( offset / GPU_CHUNK_BYTES ) * GPU_CHUNK_BYTES ) / BYTES_PER_ELEMENT;

	}

	getMemberType( builder, name ) {

		const member = this.membersLayout.find( m => m.name === name );

		return member ? member.type : 'void';

	}

	getNodeType( builder ) {

		const structType = builder.getStructTypeFromNode( this, this.membersLayout, this.name );

		return structType.name;

	}

	setup( builder ) {

		builder.addInclude( this );

	}

	generate( builder ) {

		return this.getNodeType( builder );

	}

}
```
</details>

#### Methods

##### `getLength(): number`

<details><summary>Code</summary>

```ts
getLength() {

		const GPU_CHUNK_BYTES = 8;
		const BYTES_PER_ELEMENT = Float32Array.BYTES_PER_ELEMENT;

		let offset = 0; // global buffer offset in bytes

		for ( const member of this.membersLayout ) {

			const type = member.type;

			const itemSize = getMemoryLengthFromType( type ) * BYTES_PER_ELEMENT;
			const boundary = getByteBoundaryFromType( type );

			const chunkOffset = offset % GPU_CHUNK_BYTES; // offset in the current chunk
			const chunkPadding = chunkOffset % boundary; // required padding to match boundary
			const chunkStart = chunkOffset + chunkPadding; // start position in the current chunk for the data

			offset += chunkPadding;

			// Check for chunk overflow
			if ( chunkStart !== 0 && ( GPU_CHUNK_BYTES - chunkStart ) < itemSize ) {

				// Add padding to the end of the chunk
				offset += ( GPU_CHUNK_BYTES - chunkStart );

			}

			offset += itemSize;

		}

		return ( Math.ceil( offset / GPU_CHUNK_BYTES ) * GPU_CHUNK_BYTES ) / BYTES_PER_ELEMENT;

	}
```
</details>

##### `getMemberType(builder: any, name: any): string`

<details><summary>Code</summary>

```ts
getMemberType( builder, name ) {

		const member = this.membersLayout.find( m => m.name === name );

		return member ? member.type : 'void';

	}
```
</details>

##### `getNodeType(builder: any): any`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		const structType = builder.getStructTypeFromNode( this, this.membersLayout, this.name );

		return structType.name;

	}
```
</details>

##### `setup(builder: any): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		builder.addInclude( this );

	}
```
</details>

##### `generate(builder: any): any`

<details><summary>Code</summary>

```ts
generate( builder ) {

		return this.getNodeType( builder );

	}
```
</details>


---