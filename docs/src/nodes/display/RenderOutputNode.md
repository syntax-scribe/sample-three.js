[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RenderOutputNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/display/RenderOutputNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `../core/TempNode.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `nodeObject` | `../tsl/TSLCore.js` |
| `NoColorSpace` | `../../constants.js` |
| `NoToneMapping` | `../../constants.js` |
| `ColorManagement` | `../../math/ColorManagement.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `outputNode` | `any` | let/var | `this.colorNode \|\| context.color` | ✗ |
| `toneMapping` | `any` | let/var | `( this.toneMapping !== null ? this.toneMapping : context.toneMapping ) \|\| N...` | ✗ |
| `outputColorSpace` | `any` | let/var | `( this.outputColorSpace !== null ? this.outputColorSpace : context.outputColo...` | ✗ |


---

## Functions

### `RenderOutputNode.setup({ context }: any): any`

**Parameters:**

- **`{ context }`** `any`

**Returns:** `any`

**Calls:**

- `outputNode.toneMapping`
- `outputNode.workingToColorSpace`

**Internal Comments:**
```
// tone mapping (x2)
// working to output color space
```

<details><summary>Code</summary>

```typescript
setup( { context } ) {

		let outputNode = this.colorNode || context.color;

		// tone mapping

		const toneMapping = ( this.toneMapping !== null ? this.toneMapping : context.toneMapping ) || NoToneMapping;
		const outputColorSpace = ( this.outputColorSpace !== null ? this.outputColorSpace : context.outputColorSpace ) || NoColorSpace;

		if ( toneMapping !== NoToneMapping ) {

			outputNode = outputNode.toneMapping( toneMapping );

		}

		// working to output color space

		if ( outputColorSpace !== NoColorSpace && outputColorSpace !== ColorManagement.workingColorSpace ) {

			outputNode = outputNode.workingToColorSpace( outputColorSpace );

		}

		return outputNode;

	}
```
</details>

### `renderOutput(color: Node, toneMapping: number, outputColorSpace: string): RenderOutputNode`

**Parameters:**

- **`color`** `Node`
- **`toneMapping`** `number`
- **`outputColorSpace`** `string`

**Returns:** `RenderOutputNode`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( color, toneMapping = null, outputColorSpace = null ) => nodeObject( new RenderOutputNode( nodeObject( color ), toneMapping, outputColorSpace ) )
```
</details>


---

## Classes

### `RenderOutputNode`

<details><summary>Class Code</summary>

```ts
class RenderOutputNode extends TempNode {

	static get type() {

		return 'RenderOutputNode';

	}

	/**
	 * Constructs a new render output node.
	 *
	 * @param {Node} colorNode - The color node to process.
	 * @param {?number} toneMapping - The tone mapping type.
	 * @param {?string} outputColorSpace - The output color space.
	 */
	constructor( colorNode, toneMapping, outputColorSpace ) {

		super( 'vec4' );

		/**
		 * The color node to process.
		 *
		 * @type {Node}
		 */
		this.colorNode = colorNode;

		/**
		 * The tone mapping type.
		 *
		 * @type {?number}
		 */
		this.toneMapping = toneMapping;

		/**
		 * The output color space.
		 *
		 * @type {?string}
		 */
		this.outputColorSpace = outputColorSpace;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isRenderOutputNode = true;

	}

	setup( { context } ) {

		let outputNode = this.colorNode || context.color;

		// tone mapping

		const toneMapping = ( this.toneMapping !== null ? this.toneMapping : context.toneMapping ) || NoToneMapping;
		const outputColorSpace = ( this.outputColorSpace !== null ? this.outputColorSpace : context.outputColorSpace ) || NoColorSpace;

		if ( toneMapping !== NoToneMapping ) {

			outputNode = outputNode.toneMapping( toneMapping );

		}

		// working to output color space

		if ( outputColorSpace !== NoColorSpace && outputColorSpace !== ColorManagement.workingColorSpace ) {

			outputNode = outputNode.workingToColorSpace( outputColorSpace );

		}

		return outputNode;

	}

}
```
</details>

#### Methods

##### `setup({ context }: any): any`

<details><summary>Code</summary>

```ts
setup( { context } ) {

		let outputNode = this.colorNode || context.color;

		// tone mapping

		const toneMapping = ( this.toneMapping !== null ? this.toneMapping : context.toneMapping ) || NoToneMapping;
		const outputColorSpace = ( this.outputColorSpace !== null ? this.outputColorSpace : context.outputColorSpace ) || NoColorSpace;

		if ( toneMapping !== NoToneMapping ) {

			outputNode = outputNode.toneMapping( toneMapping );

		}

		// working to output color space

		if ( outputColorSpace !== NoColorSpace && outputColorSpace !== ColorManagement.workingColorSpace ) {

			outputNode = outputNode.workingToColorSpace( outputColorSpace );

		}

		return outputNode;

	}
```
</details>


---