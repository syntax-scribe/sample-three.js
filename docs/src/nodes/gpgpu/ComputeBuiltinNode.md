[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ComputeBuiltinNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/gpgpu/ComputeBuiltinNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `nodeObject` | `../tsl/TSLBase.js` |


---

## Functions

### `ComputeBuiltinNode.getHash(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since hash is derived from the built-in name.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The hash.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.getBuiltinName`

<details><summary>Code</summary>

```typescript
getHash( builder ) {

		return this.getBuiltinName( builder );

	}
```
</details>

### `ComputeBuiltinNode.getNodeType(): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node type is simply derived from `nodeType`..
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getNodeType( /*builder*/ ) {

		return this.nodeType;

	}
```
</details>

### `ComputeBuiltinNode.setBuiltinName(builtinName: string): ComputeBuiltinNode`

**JSDoc:**
```typescript
/**
	 * Sets the builtin name.
	 *
	 * @param {string} builtinName - The built-in name.
	 * @return {ComputeBuiltinNode} A reference to this node.
	 */
```

**Parameters:**

- **`builtinName`** `string`

**Returns:** `ComputeBuiltinNode`

<details><summary>Code</summary>

```typescript
setBuiltinName( builtinName ) {

		this._builtinName = builtinName;

		return this;

	}
```
</details>

### `ComputeBuiltinNode.getBuiltinName(): string`

**JSDoc:**
```typescript
/**
	 * Returns the builtin name.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The builtin name.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getBuiltinName( /*builder*/ ) {

		return this._builtinName;

	}
```
</details>

### `ComputeBuiltinNode.hasBuiltin(builder: NodeBuilder): boolean`

**JSDoc:**
```typescript
/**
	 * Whether the current node builder has the builtin or not.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {boolean} Whether the builder has the builtin or not.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `boolean`

**Calls:**

- `builder.hasBuiltin`

<details><summary>Code</summary>

```typescript
hasBuiltin( builder ) {

		return builder.hasBuiltin( this._builtinName );

	}
```
</details>

### `ComputeBuiltinNode.generate(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `this.getBuiltinName`
- `this.getNodeType`
- `builder.format`
- `console.warn`
- `builder.generateConst`

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		const builtinName = this.getBuiltinName( builder );
		const nodeType = this.getNodeType( builder );

		if ( builder.shaderStage === 'compute' ) {

			return builder.format( builtinName, nodeType, output );

		} else {

			console.warn( `ComputeBuiltinNode: Compute built-in value ${builtinName} can not be accessed in the ${builder.shaderStage} stage` );
			return builder.generateConst( nodeType );

		}

	}
```
</details>

### `ComputeBuiltinNode.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		data.global = this.global;
		data._builtinName = this._builtinName;

	}
```
</details>

### `ComputeBuiltinNode.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		this.global = data.global;
		this._builtinName = data._builtinName;

	}
```
</details>

### `computeBuiltin(name: string, nodeType: string): ComputeBuiltinNode`

**Parameters:**

- **`name`** `string`
- **`nodeType`** `string`

**Returns:** `ComputeBuiltinNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( name, nodeType ) => nodeObject( new ComputeBuiltinNode( name, nodeType ) )
```
</details>


---

## Classes

### `ComputeBuiltinNode`

<details><summary>Class Code</summary>

```ts
class ComputeBuiltinNode extends Node {

	static get type() {

		return 'ComputeBuiltinNode';

	}

	/**
	 * Constructs a new compute builtin node.
	 *
	 * @param {string} builtinName - The built-in name.
	 * @param {string} nodeType - The node type.
	 */
	constructor( builtinName, nodeType ) {

		super( nodeType );

		/**
		 * The built-in name.
		 *
		 * @private
		 * @type {string}
		 */
		this._builtinName = builtinName;

	}

	/**
	 * This method is overwritten since hash is derived from the built-in name.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The hash.
	 */
	getHash( builder ) {

		return this.getBuiltinName( builder );

	}

	/**
	 * This method is overwritten since the node type is simply derived from `nodeType`..
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( /*builder*/ ) {

		return this.nodeType;

	}

	/**
	 * Sets the builtin name.
	 *
	 * @param {string} builtinName - The built-in name.
	 * @return {ComputeBuiltinNode} A reference to this node.
	 */
	setBuiltinName( builtinName ) {

		this._builtinName = builtinName;

		return this;

	}

	/**
	 * Returns the builtin name.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The builtin name.
	 */
	getBuiltinName( /*builder*/ ) {

		return this._builtinName;

	}

	/**
	 * Whether the current node builder has the builtin or not.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {boolean} Whether the builder has the builtin or not.
	 */
	hasBuiltin( builder ) {

		return builder.hasBuiltin( this._builtinName );

	}

	generate( builder, output ) {

		const builtinName = this.getBuiltinName( builder );
		const nodeType = this.getNodeType( builder );

		if ( builder.shaderStage === 'compute' ) {

			return builder.format( builtinName, nodeType, output );

		} else {

			console.warn( `ComputeBuiltinNode: Compute built-in value ${builtinName} can not be accessed in the ${builder.shaderStage} stage` );
			return builder.generateConst( nodeType );

		}

	}

	serialize( data ) {

		super.serialize( data );

		data.global = this.global;
		data._builtinName = this._builtinName;

	}

	deserialize( data ) {

		super.deserialize( data );

		this.global = data.global;
		this._builtinName = data._builtinName;

	}

}
```
</details>

#### Methods

##### `getHash(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getHash( builder ) {

		return this.getBuiltinName( builder );

	}
```
</details>

##### `getNodeType(): string`

<details><summary>Code</summary>

```ts
getNodeType( /*builder*/ ) {

		return this.nodeType;

	}
```
</details>

##### `setBuiltinName(builtinName: string): ComputeBuiltinNode`

<details><summary>Code</summary>

```ts
setBuiltinName( builtinName ) {

		this._builtinName = builtinName;

		return this;

	}
```
</details>

##### `getBuiltinName(): string`

<details><summary>Code</summary>

```ts
getBuiltinName( /*builder*/ ) {

		return this._builtinName;

	}
```
</details>

##### `hasBuiltin(builder: NodeBuilder): boolean`

<details><summary>Code</summary>

```ts
hasBuiltin( builder ) {

		return builder.hasBuiltin( this._builtinName );

	}
```
</details>

##### `generate(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		const builtinName = this.getBuiltinName( builder );
		const nodeType = this.getNodeType( builder );

		if ( builder.shaderStage === 'compute' ) {

			return builder.format( builtinName, nodeType, output );

		} else {

			console.warn( `ComputeBuiltinNode: Compute built-in value ${builtinName} can not be accessed in the ${builder.shaderStage} stage` );
			return builder.generateConst( nodeType );

		}

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		data.global = this.global;
		data._builtinName = this._builtinName;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		this.global = data.global;
		this._builtinName = data._builtinName;

	}
```
</details>


---