[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ComputeNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 11 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/gpgpu/ComputeNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `nodeObject` | `../tsl/TSLCore.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `outputComputeNode` | `any` | let/var | `properties.outputComputeNode` | ✗ |
| `val` | `number` | let/var | `workgroupSize[ i ]` | ✗ |


---

## Functions

### `ComputeNode.setCount(count: any): this`

**Parameters:**

- **`count`** `any`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
setCount( count ) {

		this.count = count;

		return this;

	}
```
</details>

### `ComputeNode.getCount(): number`

**Returns:** `number`

<details><summary>Code</summary>

```typescript
getCount() {

		return this.count;

	}
```
</details>

### `ComputeNode.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Executes the `dispose` event for this node.
	 */
```

**Returns:** `void`

**Calls:**

- `this.dispatchEvent`

<details><summary>Code</summary>

```typescript
dispose() {

		this.dispatchEvent( { type: 'dispose' } );

	}
```
</details>

### `ComputeNode.setName(name: string): ComputeNode`

**JSDoc:**
```typescript
/**
	 * Sets the {@link ComputeNode#name} property.
	 *
	 * @param {string} name - The name of the uniform.
	 * @return {ComputeNode} A reference to this node.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `ComputeNode`

<details><summary>Code</summary>

```typescript
setName( name ) {

		this.name = name;

		return this;

	}
```
</details>

### `ComputeNode.label(name: string): ComputeNode`

**JSDoc:**
```typescript
/**
	 * Sets the {@link ComputeNode#name} property.
	 *
	 * @deprecated
	 * @param {string} name - The name of the uniform.
	 * @return {ComputeNode} A reference to this node.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `ComputeNode`

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

### `ComputeNode.onInit(callback: Function): ComputeNode`

**JSDoc:**
```typescript
/**
	 * TODO
	 *
	 * @param {Function} callback - TODO.
	 * @return {ComputeNode} A reference to this node.
	 */
```

**Parameters:**

- **`callback`** `Function`

**Returns:** `ComputeNode`

<details><summary>Code</summary>

```typescript
onInit( callback ) {

		this.onInitFunction = callback;

		return this;

	}
```
</details>

### `ComputeNode.updateBefore({ renderer }: any): void`

**JSDoc:**
```typescript
/**
	 * The method execute the compute for this node.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
```

**Parameters:**

- **`{ renderer }`** `any`

**Returns:** `void`

**Calls:**

- `renderer.compute`

<details><summary>Code</summary>

```typescript
updateBefore( { renderer } ) {

		renderer.compute( this );

	}
```
</details>

### `ComputeNode.setup(builder: any): string | Node`

**Parameters:**

- **`builder`** `any`

**Returns:** `string | Node`

**Calls:**

- `this.computeNode.build`
- `builder.getNodeProperties`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const result = this.computeNode.build( builder );

		if ( result ) {

			const properties = builder.getNodeProperties( this );
			properties.outputComputeNode = result.outputNode;

			result.outputNode = null;

		}

		return result;

	}
```
</details>

### `ComputeNode.generate(builder: any, output: any): any`

**Parameters:**

- **`builder`** `any`
- **`output`** `any`

**Returns:** `any`

**Calls:**

- `this.computeNode.build`
- `builder.addLineFlowCode`
- `builder.getNodeProperties`
- `outputComputeNode.build`

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		const { shaderStage } = builder;

		if ( shaderStage === 'compute' ) {

			const snippet = this.computeNode.build( builder, 'void' );

			if ( snippet !== '' ) {

				builder.addLineFlowCode( snippet, this );

			}

		} else {

			const properties = builder.getNodeProperties( this );
			const outputComputeNode = properties.outputComputeNode;

			if ( outputComputeNode ) {

				return outputComputeNode.build( builder, output );

			}

		}

	}
```
</details>

### `computeKernel(node: Node, workgroupSize: number[]): AtomicFunctionNode`

**Parameters:**

- **`node`** `Node`
- **`workgroupSize`** `number[]`

**Returns:** `AtomicFunctionNode`

**Calls:**

- `console.error`
- `Number.isInteger`
- `workgroupSize.push`
- `nodeObject (from ../tsl/TSLCore.js)`

**Internal Comments:**
```
// Implicit fill-up to [ x, y, z ] with 1s, just like WGSL treats @workgroup_size when fewer dimensions are specified
//
```

<details><summary>Code</summary>

```typescript
( node, workgroupSize = [ 64 ] ) => {

	if ( workgroupSize.length === 0 || workgroupSize.length > 3 ) {

		console.error( 'THREE.TSL: compute() workgroupSize must have 1, 2, or 3 elements' );

	}

	for ( let i = 0; i < workgroupSize.length; i ++ ) {

		const val = workgroupSize[ i ];

		if ( typeof val !== 'number' || val <= 0 || ! Number.isInteger( val ) ) {

			console.error( `THREE.TSL: compute() workgroupSize element at index [ ${ i } ] must be a positive integer` );

		}

	}

	// Implicit fill-up to [ x, y, z ] with 1s, just like WGSL treats @workgroup_size when fewer dimensions are specified

	while ( workgroupSize.length < 3 ) workgroupSize.push( 1 );

	//

	return nodeObject( new ComputeNode( nodeObject( node ), workgroupSize ) );

}
```
</details>

### `compute(node: Node, count: number, workgroupSize: number[]): AtomicFunctionNode`

**Parameters:**

- **`node`** `Node`
- **`count`** `number`
- **`workgroupSize`** `number[]`

**Returns:** `AtomicFunctionNode`

**Calls:**

- `computeKernel( node, workgroupSize ).setCount`

<details><summary>Code</summary>

```typescript
( node, count, workgroupSize ) => computeKernel( node, workgroupSize ).setCount( count )
```
</details>


---

## Classes

### `ComputeNode`

<details><summary>Class Code</summary>

```ts
class ComputeNode extends Node {

	static get type() {

		return 'ComputeNode';

	}

	/**
	 * Constructs a new compute node.
	 *
	 * @param {Node} computeNode - TODO
	 * @param {Array<number>} workgroupSize - TODO.
	 */
	constructor( computeNode, workgroupSize ) {

		super( 'void' );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isComputeNode = true;

		/**
		 * TODO
		 *
		 * @type {Node}
		 */
		this.computeNode = computeNode;


		/**
		 * TODO
		 *
		 * @type {Array<number>}
		 * @default [ 64 ]
		 */
		this.workgroupSize = workgroupSize;

		/**
		 * TODO
		 *
		 * @type {number}
		 */
		this.count = null;

		/**
		 * TODO
		 *
		 * @type {number}
		 */
		this.version = 1;

		/**
		 * The name or label of the uniform.
		 *
		 * @type {string}
		 * @default ''
		 */
		this.name = '';

		/**
		 * The `updateBeforeType` is set to `NodeUpdateType.OBJECT` since {@link ComputeNode#updateBefore}
		 * is executed once per object by default.
		 *
		 * @type {string}
		 * @default 'object'
		 */
		this.updateBeforeType = NodeUpdateType.OBJECT;

		/**
		 * TODO
		 *
		 * @type {?Function}
		 */
		this.onInitFunction = null;

	}

	setCount( count ) {

		this.count = count;

		return this;

	}

	getCount() {

		return this.count;

	}

	/**
	 * Executes the `dispose` event for this node.
	 */
	dispose() {

		this.dispatchEvent( { type: 'dispose' } );

	}

	/**
	 * Sets the {@link ComputeNode#name} property.
	 *
	 * @param {string} name - The name of the uniform.
	 * @return {ComputeNode} A reference to this node.
	 */
	setName( name ) {

		this.name = name;

		return this;

	}

	/**
	 * Sets the {@link ComputeNode#name} property.
	 *
	 * @deprecated
	 * @param {string} name - The name of the uniform.
	 * @return {ComputeNode} A reference to this node.
	 */
	label( name ) {

		console.warn( 'THREE.TSL: "label()" has been deprecated. Use "setName()" instead.' ); // @deprecated r179

		return this.setName( name );

	}

	/**
	 * TODO
	 *
	 * @param {Function} callback - TODO.
	 * @return {ComputeNode} A reference to this node.
	 */
	onInit( callback ) {

		this.onInitFunction = callback;

		return this;

	}

	/**
	 * The method execute the compute for this node.
	 *
	 * @param {NodeFrame} frame - A reference to the current node frame.
	 */
	updateBefore( { renderer } ) {

		renderer.compute( this );

	}

	setup( builder ) {

		const result = this.computeNode.build( builder );

		if ( result ) {

			const properties = builder.getNodeProperties( this );
			properties.outputComputeNode = result.outputNode;

			result.outputNode = null;

		}

		return result;

	}

	generate( builder, output ) {

		const { shaderStage } = builder;

		if ( shaderStage === 'compute' ) {

			const snippet = this.computeNode.build( builder, 'void' );

			if ( snippet !== '' ) {

				builder.addLineFlowCode( snippet, this );

			}

		} else {

			const properties = builder.getNodeProperties( this );
			const outputComputeNode = properties.outputComputeNode;

			if ( outputComputeNode ) {

				return outputComputeNode.build( builder, output );

			}

		}

	}

}
```
</details>

#### Methods

##### `setCount(count: any): this`

<details><summary>Code</summary>

```ts
setCount( count ) {

		this.count = count;

		return this;

	}
```
</details>

##### `getCount(): number`

<details><summary>Code</summary>

```ts
getCount() {

		return this.count;

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.dispatchEvent( { type: 'dispose' } );

	}
```
</details>

##### `setName(name: string): ComputeNode`

<details><summary>Code</summary>

```ts
setName( name ) {

		this.name = name;

		return this;

	}
```
</details>

##### `label(name: string): ComputeNode`

<details><summary>Code</summary>

```ts
label( name ) {

		console.warn( 'THREE.TSL: "label()" has been deprecated. Use "setName()" instead.' ); // @deprecated r179

		return this.setName( name );

	}
```
</details>

##### `onInit(callback: Function): ComputeNode`

<details><summary>Code</summary>

```ts
onInit( callback ) {

		this.onInitFunction = callback;

		return this;

	}
```
</details>

##### `updateBefore({ renderer }: any): void`

<details><summary>Code</summary>

```ts
updateBefore( { renderer } ) {

		renderer.compute( this );

	}
```
</details>

##### `setup(builder: any): string | Node`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const result = this.computeNode.build( builder );

		if ( result ) {

			const properties = builder.getNodeProperties( this );
			properties.outputComputeNode = result.outputNode;

			result.outputNode = null;

		}

		return result;

	}
```
</details>

##### `generate(builder: any, output: any): any`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		const { shaderStage } = builder;

		if ( shaderStage === 'compute' ) {

			const snippet = this.computeNode.build( builder, 'void' );

			if ( snippet !== '' ) {

				builder.addLineFlowCode( snippet, this );

			}

		} else {

			const properties = builder.getNodeProperties( this );
			const outputComputeNode = properties.outputComputeNode;

			if ( outputComputeNode ) {

				return outputComputeNode.build( builder, output );

			}

		}

	}
```
</details>


---