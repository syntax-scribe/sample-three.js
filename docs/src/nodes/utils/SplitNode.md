[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SplitNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/utils/SplitNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `vectorComponents` | `../core/constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `vectorLength` | `number` | let/var | `this.components.length` | ✗ |
| `node` | `Node` | let/var | `this.node` | ✗ |
| `snippet` | `any` | let/var | `null` | ✗ |
| `type` | `any` | let/var | `null` | ✗ |


---

## Functions

### `SplitNode.getVectorLength(): number`

**JSDoc:**
```typescript
/**
	 * Returns the vector length which is computed based on the requested components.
	 *
	 * @return {number} The vector length.
	 */
```

**Returns:** `number`

**Calls:**

- `Math.max`
- `vectorComponents.indexOf`

<details><summary>Code</summary>

```typescript
getVectorLength() {

		let vectorLength = this.components.length;

		for ( const c of this.components ) {

			vectorLength = Math.max( vectorComponents.indexOf( c ) + 1, vectorLength );

		}

		return vectorLength;

	}
```
</details>

### `SplitNode.getComponentType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * Returns the component type of the node's type.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The component type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `builder.getComponentType`
- `this.node.getNodeType`

<details><summary>Code</summary>

```typescript
getComponentType( builder ) {

		return builder.getComponentType( this.node.getNodeType( builder ) );

	}
```
</details>

### `SplitNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * This method is overwritten since the node type is inferred from requested components.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `builder.getTypeFromLength`
- `this.getComponentType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return builder.getTypeFromLength( this.components.length, this.getComponentType( builder ) );

	}
```
</details>

### `SplitNode.generate(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `builder.getTypeLength`
- `node.getNodeType`
- `this.getVectorLength`
- `builder.getTypeFromLength`
- `this.getComponentType`
- `node.build`
- `_stringVectorComponents.slice`
- `builder.format`
- `this.getNodeType`

**Internal Comments:**
```
// needed expand the input node (x3)
// unnecessary swizzle (x3)
// ignore .components if .node returns float/integer (x3)
```

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		const node = this.node;
		const nodeTypeLength = builder.getTypeLength( node.getNodeType( builder ) );

		let snippet = null;

		if ( nodeTypeLength > 1 ) {

			let type = null;

			const componentsLength = this.getVectorLength();

			if ( componentsLength >= nodeTypeLength ) {

				// needed expand the input node

				type = builder.getTypeFromLength( this.getVectorLength(), this.getComponentType( builder ) );

			}

			const nodeSnippet = node.build( builder, type );

			if ( this.components.length === nodeTypeLength && this.components === _stringVectorComponents.slice( 0, this.components.length ) ) {

				// unnecessary swizzle

				snippet = builder.format( nodeSnippet, type, output );

			} else {

				snippet = builder.format( `${nodeSnippet}.${this.components}`, this.getNodeType( builder ), output );

			}

		} else {

			// ignore .components if .node returns float/integer

			snippet = node.build( builder, output );

		}

		return snippet;

	}
```
</details>

### `SplitNode.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		data.components = this.components;

	}
```
</details>

### `SplitNode.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		this.components = data.components;

	}
```
</details>


---

## Classes

### `SplitNode`

<details><summary>Class Code</summary>

```ts
class SplitNode extends Node {

	static get type() {

		return 'SplitNode';

	}

	/**
	 * Constructs a new split node.
	 *
	 * @param {Node} node - The node that should be accessed.
	 * @param {string} [components='x'] - The components that should be accessed.
	 */
	constructor( node, components = 'x' ) {

		super();

		/**
		 * The node that should be accessed.
		 *
		 * @type {Node}
		 */
		this.node = node;

		/**
		 * The components that should be accessed.
		 *
		 * @type {string}
		 */
		this.components = components;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSplitNode = true;

	}

	/**
	 * Returns the vector length which is computed based on the requested components.
	 *
	 * @return {number} The vector length.
	 */
	getVectorLength() {

		let vectorLength = this.components.length;

		for ( const c of this.components ) {

			vectorLength = Math.max( vectorComponents.indexOf( c ) + 1, vectorLength );

		}

		return vectorLength;

	}

	/**
	 * Returns the component type of the node's type.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The component type.
	 */
	getComponentType( builder ) {

		return builder.getComponentType( this.node.getNodeType( builder ) );

	}

	/**
	 * This method is overwritten since the node type is inferred from requested components.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( builder ) {

		return builder.getTypeFromLength( this.components.length, this.getComponentType( builder ) );

	}

	generate( builder, output ) {

		const node = this.node;
		const nodeTypeLength = builder.getTypeLength( node.getNodeType( builder ) );

		let snippet = null;

		if ( nodeTypeLength > 1 ) {

			let type = null;

			const componentsLength = this.getVectorLength();

			if ( componentsLength >= nodeTypeLength ) {

				// needed expand the input node

				type = builder.getTypeFromLength( this.getVectorLength(), this.getComponentType( builder ) );

			}

			const nodeSnippet = node.build( builder, type );

			if ( this.components.length === nodeTypeLength && this.components === _stringVectorComponents.slice( 0, this.components.length ) ) {

				// unnecessary swizzle

				snippet = builder.format( nodeSnippet, type, output );

			} else {

				snippet = builder.format( `${nodeSnippet}.${this.components}`, this.getNodeType( builder ), output );

			}

		} else {

			// ignore .components if .node returns float/integer

			snippet = node.build( builder, output );

		}

		return snippet;

	}

	serialize( data ) {

		super.serialize( data );

		data.components = this.components;

	}

	deserialize( data ) {

		super.deserialize( data );

		this.components = data.components;

	}

}
```
</details>

#### Methods

##### `getVectorLength(): number`

<details><summary>Code</summary>

```ts
getVectorLength() {

		let vectorLength = this.components.length;

		for ( const c of this.components ) {

			vectorLength = Math.max( vectorComponents.indexOf( c ) + 1, vectorLength );

		}

		return vectorLength;

	}
```
</details>

##### `getComponentType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getComponentType( builder ) {

		return builder.getComponentType( this.node.getNodeType( builder ) );

	}
```
</details>

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return builder.getTypeFromLength( this.components.length, this.getComponentType( builder ) );

	}
```
</details>

##### `generate(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		const node = this.node;
		const nodeTypeLength = builder.getTypeLength( node.getNodeType( builder ) );

		let snippet = null;

		if ( nodeTypeLength > 1 ) {

			let type = null;

			const componentsLength = this.getVectorLength();

			if ( componentsLength >= nodeTypeLength ) {

				// needed expand the input node

				type = builder.getTypeFromLength( this.getVectorLength(), this.getComponentType( builder ) );

			}

			const nodeSnippet = node.build( builder, type );

			if ( this.components.length === nodeTypeLength && this.components === _stringVectorComponents.slice( 0, this.components.length ) ) {

				// unnecessary swizzle

				snippet = builder.format( nodeSnippet, type, output );

			} else {

				snippet = builder.format( `${nodeSnippet}.${this.components}`, this.getNodeType( builder ), output );

			}

		} else {

			// ignore .components if .node returns float/integer

			snippet = node.build( builder, output );

		}

		return snippet;

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		data.components = this.components;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		this.components = data.components;

	}
```
</details>


---