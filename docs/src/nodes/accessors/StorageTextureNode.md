[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `StorageTextureNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/StorageTextureNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TextureNode` | `./TextureNode.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `NodeAccess` | `../core/constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `snippet` | `any` | let/var | `*not shown*` | ✗ |
| `depthSnippet` | `any` | let/var | `depthNode ? depthNode.build( builder, 'int' ) : null` | ✗ |


---

## Functions

### `StorageTextureNode.getInputType(): string`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation to return a fixed value `'storageTexture'`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getInputType( /*builder*/ ) {

		return 'storageTexture';

	}
```
</details>

### `StorageTextureNode.setup(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `super.setup`
- `builder.getNodeProperties`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		super.setup( builder );

		const properties = builder.getNodeProperties( this );
		properties.storeNode = this.storeNode;

		return properties;

	}
```
</details>

### `StorageTextureNode.setAccess(value: string): StorageTextureNode`

**JSDoc:**
```typescript
/**
	 * Defines the node access.
	 *
	 * @param {string} value - The node access.
	 * @return {StorageTextureNode} A reference to this node.
	 */
```

**Parameters:**

- **`value`** `string`

**Returns:** `StorageTextureNode`

<details><summary>Code</summary>

```typescript
setAccess( value ) {

		this.access = value;
		return this;

	}
```
</details>

### `StorageTextureNode.generate(builder: NodeBuilder, output: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the code snippet of the storage node. If no `storeNode`
	 * is defined, the texture node is generated as normal texture.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {string} output - The current output.
	 * @return {string} The generated code snippet.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`output`** `string`

**Returns:** `string`

**Calls:**

- `this.generateStore`
- `super.generate`

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		let snippet;

		if ( this.storeNode !== null ) {

			snippet = this.generateStore( builder );

		} else {

			snippet = super.generate( builder, output );

		}

		return snippet;

	}
```
</details>

### `StorageTextureNode.toReadWrite(): StorageTextureNode`

**JSDoc:**
```typescript
/**
	 * Convenience method for configuring a read/write node access.
	 *
	 * @return {StorageTextureNode} A reference to this node.
	 */
```

**Returns:** `StorageTextureNode`

**Calls:**

- `this.setAccess`

<details><summary>Code</summary>

```typescript
toReadWrite() {

		return this.setAccess( NodeAccess.READ_WRITE );

	}
```
</details>

### `StorageTextureNode.toReadOnly(): StorageTextureNode`

**JSDoc:**
```typescript
/**
	 * Convenience method for configuring a read-only node access.
	 *
	 * @return {StorageTextureNode} A reference to this node.
	 */
```

**Returns:** `StorageTextureNode`

**Calls:**

- `this.setAccess`

<details><summary>Code</summary>

```typescript
toReadOnly() {

		return this.setAccess( NodeAccess.READ_ONLY );

	}
```
</details>

### `StorageTextureNode.toWriteOnly(): StorageTextureNode`

**JSDoc:**
```typescript
/**
	 * Convenience method for configuring a write-only node access.
	 *
	 * @return {StorageTextureNode} A reference to this node.
	 */
```

**Returns:** `StorageTextureNode`

**Calls:**

- `this.setAccess`

<details><summary>Code</summary>

```typescript
toWriteOnly() {

		return this.setAccess( NodeAccess.WRITE_ONLY );

	}
```
</details>

### `StorageTextureNode.generateStore(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Generates the code snippet of the storage texture node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `builder.getNodeProperties`
- `super.generate`
- `uvNode.build`
- `storeNode.build`
- `depthNode.build`
- `builder.generateTextureStore`
- `builder.addLineFlowCode`

<details><summary>Code</summary>

```typescript
generateStore( builder ) {

		const properties = builder.getNodeProperties( this );

		const { uvNode, storeNode, depthNode } = properties;

		const textureProperty = super.generate( builder, 'property' );
		const uvSnippet = uvNode.build( builder, this.value.is3DTexture === true ? 'uvec3' : 'uvec2' );
		const storeSnippet = storeNode.build( builder, 'vec4' );
		const depthSnippet = depthNode ? depthNode.build( builder, 'int' ) : null;

		const snippet = builder.generateTextureStore( builder, textureProperty, uvSnippet, depthSnippet, storeSnippet );

		builder.addLineFlowCode( snippet, this );

	}
```
</details>

### `StorageTextureNode.clone(): TextureNode`

**Returns:** `TextureNode`

**Calls:**

- `super.clone`

<details><summary>Code</summary>

```typescript
clone() {

		const newNode = super.clone();
		newNode.storeNode = this.storeNode;
		return newNode;

	}
```
</details>

### `textureStore(value: StorageTexture, uvNode: any, storeNode: Node): StorageTextureNode`

**Parameters:**

- **`value`** `StorageTexture`
- **`uvNode`** `any`
- **`storeNode`** `Node`

**Returns:** `StorageTextureNode`

**Calls:**

- `storageTexture`
- `node.toStack`

<details><summary>Code</summary>

```typescript
( value, uvNode, storeNode ) => {

	const node = storageTexture( value, uvNode, storeNode );

	if ( storeNode !== null ) node.toStack();

	return node;

}
```
</details>


---

## Classes

### `StorageTextureNode`

<details><summary>Class Code</summary>

```ts
class StorageTextureNode extends TextureNode {

	static get type() {

		return 'StorageTextureNode';

	}

	/**
	 * Constructs a new storage texture node.
	 *
	 * @param {StorageTexture} value - The storage texture.
	 * @param {Node<vec2|vec3>} uvNode - The uv node.
	 * @param {?Node} [storeNode=null] - The value node that should be stored in the texture.
	 */
	constructor( value, uvNode, storeNode = null ) {

		super( value, uvNode );

		/**
		 * The value node that should be stored in the texture.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.storeNode = storeNode;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isStorageTextureNode = true;

		/**
		 * The access type of the texture node.
		 *
		 * @type {string}
		 * @default 'writeOnly'
		 */
		this.access = NodeAccess.WRITE_ONLY;

	}

	/**
	 * Overwrites the default implementation to return a fixed value `'storageTexture'`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
	getInputType( /*builder*/ ) {

		return 'storageTexture';

	}

	setup( builder ) {

		super.setup( builder );

		const properties = builder.getNodeProperties( this );
		properties.storeNode = this.storeNode;

		return properties;

	}

	/**
	 * Defines the node access.
	 *
	 * @param {string} value - The node access.
	 * @return {StorageTextureNode} A reference to this node.
	 */
	setAccess( value ) {

		this.access = value;
		return this;

	}

	/**
	 * Generates the code snippet of the storage node. If no `storeNode`
	 * is defined, the texture node is generated as normal texture.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {string} output - The current output.
	 * @return {string} The generated code snippet.
	 */
	generate( builder, output ) {

		let snippet;

		if ( this.storeNode !== null ) {

			snippet = this.generateStore( builder );

		} else {

			snippet = super.generate( builder, output );

		}

		return snippet;

	}

	/**
	 * Convenience method for configuring a read/write node access.
	 *
	 * @return {StorageTextureNode} A reference to this node.
	 */
	toReadWrite() {

		return this.setAccess( NodeAccess.READ_WRITE );

	}

	/**
	 * Convenience method for configuring a read-only node access.
	 *
	 * @return {StorageTextureNode} A reference to this node.
	 */
	toReadOnly() {

		return this.setAccess( NodeAccess.READ_ONLY );

	}

	/**
	 * Convenience method for configuring a write-only node access.
	 *
	 * @return {StorageTextureNode} A reference to this node.
	 */
	toWriteOnly() {

		return this.setAccess( NodeAccess.WRITE_ONLY );

	}

	/**
	 * Generates the code snippet of the storage texture node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	generateStore( builder ) {

		const properties = builder.getNodeProperties( this );

		const { uvNode, storeNode, depthNode } = properties;

		const textureProperty = super.generate( builder, 'property' );
		const uvSnippet = uvNode.build( builder, this.value.is3DTexture === true ? 'uvec3' : 'uvec2' );
		const storeSnippet = storeNode.build( builder, 'vec4' );
		const depthSnippet = depthNode ? depthNode.build( builder, 'int' ) : null;

		const snippet = builder.generateTextureStore( builder, textureProperty, uvSnippet, depthSnippet, storeSnippet );

		builder.addLineFlowCode( snippet, this );

	}

	clone() {

		const newNode = super.clone();
		newNode.storeNode = this.storeNode;
		return newNode;

	}

}
```
</details>

#### Methods

##### `getInputType(): string`

<details><summary>Code</summary>

```ts
getInputType( /*builder*/ ) {

		return 'storageTexture';

	}
```
</details>

##### `setup(builder: any): any`

<details><summary>Code</summary>

```ts
setup( builder ) {

		super.setup( builder );

		const properties = builder.getNodeProperties( this );
		properties.storeNode = this.storeNode;

		return properties;

	}
```
</details>

##### `setAccess(value: string): StorageTextureNode`

<details><summary>Code</summary>

```ts
setAccess( value ) {

		this.access = value;
		return this;

	}
```
</details>

##### `generate(builder: NodeBuilder, output: string): string`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		let snippet;

		if ( this.storeNode !== null ) {

			snippet = this.generateStore( builder );

		} else {

			snippet = super.generate( builder, output );

		}

		return snippet;

	}
```
</details>

##### `toReadWrite(): StorageTextureNode`

<details><summary>Code</summary>

```ts
toReadWrite() {

		return this.setAccess( NodeAccess.READ_WRITE );

	}
```
</details>

##### `toReadOnly(): StorageTextureNode`

<details><summary>Code</summary>

```ts
toReadOnly() {

		return this.setAccess( NodeAccess.READ_ONLY );

	}
```
</details>

##### `toWriteOnly(): StorageTextureNode`

<details><summary>Code</summary>

```ts
toWriteOnly() {

		return this.setAccess( NodeAccess.WRITE_ONLY );

	}
```
</details>

##### `generateStore(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
generateStore( builder ) {

		const properties = builder.getNodeProperties( this );

		const { uvNode, storeNode, depthNode } = properties;

		const textureProperty = super.generate( builder, 'property' );
		const uvSnippet = uvNode.build( builder, this.value.is3DTexture === true ? 'uvec3' : 'uvec2' );
		const storeSnippet = storeNode.build( builder, 'vec4' );
		const depthSnippet = depthNode ? depthNode.build( builder, 'int' ) : null;

		const snippet = builder.generateTextureStore( builder, textureProperty, uvSnippet, depthSnippet, storeSnippet );

		builder.addLineFlowCode( snippet, this );

	}
```
</details>

##### `clone(): TextureNode`

<details><summary>Code</summary>

```ts
clone() {

		const newNode = super.clone();
		newNode.storeNode = this.storeNode;
		return newNode;

	}
```
</details>


---