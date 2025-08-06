[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MRTNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/MRTNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `OutputStructNode` | `./OutputStructNode.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `vec4` | `../tsl/TSLBase.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `outputs` | `{ [x: string]: Node; }` | let/var | `{ ...this.outputNodes, ...mrtNode.outputNodes }` | ✗ |
| `outputNodes` | `{ [x: string]: Node; }` | let/var | `this.outputNodes` | ✗ |
| `members` | `any[]` | let/var | `[]` | ✗ |
| `textures` | `any` | let/var | `mrt.textures` | ✗ |


---

## Functions

### `getTextureIndex(textures: Texture[], name: string): number`

**JSDoc:**
```typescript
/**
 * Returns the MRT texture index for the given name.
 *
 * @param {Array<Texture>} textures - The textures of a MRT-configured render target.
 * @param {string} name - The name of the MRT texture which index is requested.
 * @return {number} The texture index.
 */
```

**Parameters:**

- **`textures`** `Texture[]`
- **`name`** `string`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
export function getTextureIndex( textures, name ) {

	for ( let i = 0; i < textures.length; i ++ ) {

		if ( textures[ i ].name === name ) {

			return i;

		}

	}

	return - 1;

}
```
</details>

### `MRTNode.has(name: string): NodeBuilder`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the MRT node has an output with the given name.
	 *
	 * @param {string} name - The name of the output.
	 * @return {NodeBuilder} Whether the MRT node has an output for the given name or not.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `NodeBuilder`

<details><summary>Code</summary>

```typescript
has( name ) {

		return this.outputNodes[ name ] !== undefined;

	}
```
</details>

### `MRTNode.get(name: string): Node`

**JSDoc:**
```typescript
/**
	 * Returns the output node for the given name.
	 *
	 * @param {string} name - The name of the output.
	 * @return {Node} The output node.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `Node`

<details><summary>Code</summary>

```typescript
get( name ) {

		return this.outputNodes[ name ];

	}
```
</details>

### `MRTNode.merge(mrtNode: MRTNode): MRTNode`

**JSDoc:**
```typescript
/**
	 * Merges the outputs of the given MRT node with the outputs of this node.
	 *
	 * @param {MRTNode} mrtNode - The MRT to merge.
	 * @return {MRTNode} A new MRT node with merged outputs..
	 */
```

**Parameters:**

- **`mrtNode`** `MRTNode`

**Returns:** `MRTNode`

**Calls:**

- `mrt`

<details><summary>Code</summary>

```typescript
merge( mrtNode ) {

		const outputs = { ...this.outputNodes, ...mrtNode.outputNodes };

		return mrt( outputs );

	}
```
</details>

### `MRTNode.setup(builder: any): Node`

**Parameters:**

- **`builder`** `any`

**Returns:** `Node`

**Calls:**

- `builder.renderer.getRenderTarget`
- `getTextureIndex`
- `vec4 (from ../tsl/TSLBase.js)`
- `super.setup`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const outputNodes = this.outputNodes;
		const mrt = builder.renderer.getRenderTarget();

		const members = [];

		const textures = mrt.textures;

		for ( const name in outputNodes ) {

			const index = getTextureIndex( textures, name );

			members[ index ] = vec4( outputNodes[ name ] );

		}

		this.members = members;

		return super.setup( builder );

	}
```
</details>


---

## Classes

### `MRTNode`

<details><summary>Class Code</summary>

```ts
class MRTNode extends OutputStructNode {

	static get type() {

		return 'MRTNode';

	}

	/**
	 * Constructs a new output struct node.
	 *
	 * @param {Object<string, Node>} outputNodes - The MRT outputs.
	 */
	constructor( outputNodes ) {

		super();

		/**
		 * A dictionary representing the MRT outputs. The key
		 * is the name of the output, the value the node which produces
		 * the output result.
		 *
		 * @type {Object<string, Node>}
		 */
		this.outputNodes = outputNodes;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isMRTNode = true;

	}

	/**
	 * Returns `true` if the MRT node has an output with the given name.
	 *
	 * @param {string} name - The name of the output.
	 * @return {NodeBuilder} Whether the MRT node has an output for the given name or not.
	 */
	has( name ) {

		return this.outputNodes[ name ] !== undefined;

	}

	/**
	 * Returns the output node for the given name.
	 *
	 * @param {string} name - The name of the output.
	 * @return {Node} The output node.
	 */
	get( name ) {

		return this.outputNodes[ name ];

	}

	/**
	 * Merges the outputs of the given MRT node with the outputs of this node.
	 *
	 * @param {MRTNode} mrtNode - The MRT to merge.
	 * @return {MRTNode} A new MRT node with merged outputs..
	 */
	merge( mrtNode ) {

		const outputs = { ...this.outputNodes, ...mrtNode.outputNodes };

		return mrt( outputs );

	}

	setup( builder ) {

		const outputNodes = this.outputNodes;
		const mrt = builder.renderer.getRenderTarget();

		const members = [];

		const textures = mrt.textures;

		for ( const name in outputNodes ) {

			const index = getTextureIndex( textures, name );

			members[ index ] = vec4( outputNodes[ name ] );

		}

		this.members = members;

		return super.setup( builder );

	}

}
```
</details>

#### Methods

##### `has(name: string): NodeBuilder`

<details><summary>Code</summary>

```ts
has( name ) {

		return this.outputNodes[ name ] !== undefined;

	}
```
</details>

##### `get(name: string): Node`

<details><summary>Code</summary>

```ts
get( name ) {

		return this.outputNodes[ name ];

	}
```
</details>

##### `merge(mrtNode: MRTNode): MRTNode`

<details><summary>Code</summary>

```ts
merge( mrtNode ) {

		const outputs = { ...this.outputNodes, ...mrtNode.outputNodes };

		return mrt( outputs );

	}
```
</details>

##### `setup(builder: any): Node`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const outputNodes = this.outputNodes;
		const mrt = builder.renderer.getRenderTarget();

		const members = [];

		const textures = mrt.textures;

		for ( const name in outputNodes ) {

			const index = getTextureIndex( textures, name );

			members[ index ] = vec4( outputNodes[ name ] );

		}

		this.members = members;

		return super.setup( builder );

	}
```
</details>


---