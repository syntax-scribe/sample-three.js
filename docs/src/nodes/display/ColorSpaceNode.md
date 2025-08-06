[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ColorSpaceNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/display/ColorSpaceNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `../core/TempNode.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `mat3` | `../tsl/TSLCore.js` |
| `nodeObject` | `../tsl/TSLCore.js` |
| `vec4` | `../tsl/TSLCore.js` |
| `SRGBTransfer` | `../../constants.js` |
| `ColorManagement` | `../../math/ColorManagement.js` |
| `sRGBTransferEOTF` | `./ColorSpaceFunctions.js` |
| `sRGBTransferOETF` | `./ColorSpaceFunctions.js` |
| `Matrix3` | `../../math/Matrix3.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `WORKING_COLOR_SPACE` | `"WorkingColorSpace"` | let/var | `'WorkingColorSpace'` | ✗ |
| `OUTPUT_COLOR_SPACE` | `"OutputColorSpace"` | let/var | `'OutputColorSpace'` | ✗ |
| `outputNode` | `Node` | let/var | `colorNode` | ✗ |


---

## Functions

### `ColorSpaceNode.resolveColorSpace(builder: NodeBuilder, colorSpace: string): string`

**JSDoc:**
```typescript
/**
	 * This method resolves the constants `WORKING_COLOR_SPACE` and
	 * `OUTPUT_COLOR_SPACE` based on the current configuration of the
	 * color management and renderer.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {string} colorSpace - The color space to resolve.
	 * @return {string} The resolved color space.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`colorSpace`** `string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
resolveColorSpace( builder, colorSpace ) {

		if ( colorSpace === WORKING_COLOR_SPACE ) {

			return ColorManagement.workingColorSpace;

		} else if ( colorSpace === OUTPUT_COLOR_SPACE ) {

			return builder.context.outputColorSpace || builder.renderer.outputColorSpace;

		}

		return colorSpace;

	}
```
</details>

### `ColorSpaceNode.setup(builder: any): Node`

**Parameters:**

- **`builder`** `any`

**Returns:** `Node`

**Calls:**

- `this.resolveColorSpace`
- `ColorManagement.getTransfer`
- `vec4 (from ../tsl/TSLCore.js)`
- `sRGBTransferEOTF (from ./ColorSpaceFunctions.js)`
- `ColorManagement.getPrimaries`
- `mat3( ColorManagement._getMatrix( new Matrix3(), source, target ) ).mul`
- `sRGBTransferOETF (from ./ColorSpaceFunctions.js)`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const { colorNode } = this;

		const source = this.resolveColorSpace( builder, this.source );
		const target = this.resolveColorSpace( builder, this.target );

		let outputNode = colorNode;

		if ( ColorManagement.enabled === false || source === target || ! source || ! target ) {

			return outputNode;

		}

		if ( ColorManagement.getTransfer( source ) === SRGBTransfer ) {

			outputNode = vec4( sRGBTransferEOTF( outputNode.rgb ), outputNode.a );

		}

		if ( ColorManagement.getPrimaries( source ) !== ColorManagement.getPrimaries( target ) ) {

			outputNode = vec4(
				mat3( ColorManagement._getMatrix( new Matrix3(), source, target ) ).mul( outputNode.rgb ),
				outputNode.a
			);

		}

		if ( ColorManagement.getTransfer( target ) === SRGBTransfer ) {

			outputNode = vec4( sRGBTransferOETF( outputNode.rgb ), outputNode.a );

		}

		return outputNode;

	}
```
</details>

### `workingToColorSpace(node: Node, targetColorSpace: string): ColorSpaceNode`

**Parameters:**

- **`node`** `Node`
- **`targetColorSpace`** `string`

**Returns:** `ColorSpaceNode`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( node, targetColorSpace ) => nodeObject( new ColorSpaceNode( nodeObject( node ), WORKING_COLOR_SPACE, targetColorSpace ) )
```
</details>

### `colorSpaceToWorking(node: Node, sourceColorSpace: string): ColorSpaceNode`

**Parameters:**

- **`node`** `Node`
- **`sourceColorSpace`** `string`

**Returns:** `ColorSpaceNode`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( node, sourceColorSpace ) => nodeObject( new ColorSpaceNode( nodeObject( node ), sourceColorSpace, WORKING_COLOR_SPACE ) )
```
</details>

### `convertColorSpace(node: Node, sourceColorSpace: string, targetColorSpace: string): ColorSpaceNode`

**Parameters:**

- **`node`** `Node`
- **`sourceColorSpace`** `string`
- **`targetColorSpace`** `string`

**Returns:** `ColorSpaceNode`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( node, sourceColorSpace, targetColorSpace ) => nodeObject( new ColorSpaceNode( nodeObject( node ), sourceColorSpace, targetColorSpace ) )
```
</details>


---

## Classes

### `ColorSpaceNode`

<details><summary>Class Code</summary>

```ts
class ColorSpaceNode extends TempNode {

	static get type() {

		return 'ColorSpaceNode';

	}

	/**
	 * Constructs a new color space node.
	 *
	 * @param {Node} colorNode - Represents the color to convert.
	 * @param {string} source - The source color space.
	 * @param {string} target - The target color space.
	 */
	constructor( colorNode, source, target ) {

		super( 'vec4' );

		/**
		 * Represents the color to convert.
		 *
		 * @type {Node}
		 */
		this.colorNode = colorNode;

		/**
		 * The source color space.
		 *
		 * @type {string}
		 */
		this.source = source;

		/**
		 * The target color space.
		 *
		 * @type {string}
		 */
		this.target = target;

	}

	/**
	 * This method resolves the constants `WORKING_COLOR_SPACE` and
	 * `OUTPUT_COLOR_SPACE` based on the current configuration of the
	 * color management and renderer.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {string} colorSpace - The color space to resolve.
	 * @return {string} The resolved color space.
	 */
	resolveColorSpace( builder, colorSpace ) {

		if ( colorSpace === WORKING_COLOR_SPACE ) {

			return ColorManagement.workingColorSpace;

		} else if ( colorSpace === OUTPUT_COLOR_SPACE ) {

			return builder.context.outputColorSpace || builder.renderer.outputColorSpace;

		}

		return colorSpace;

	}

	setup( builder ) {

		const { colorNode } = this;

		const source = this.resolveColorSpace( builder, this.source );
		const target = this.resolveColorSpace( builder, this.target );

		let outputNode = colorNode;

		if ( ColorManagement.enabled === false || source === target || ! source || ! target ) {

			return outputNode;

		}

		if ( ColorManagement.getTransfer( source ) === SRGBTransfer ) {

			outputNode = vec4( sRGBTransferEOTF( outputNode.rgb ), outputNode.a );

		}

		if ( ColorManagement.getPrimaries( source ) !== ColorManagement.getPrimaries( target ) ) {

			outputNode = vec4(
				mat3( ColorManagement._getMatrix( new Matrix3(), source, target ) ).mul( outputNode.rgb ),
				outputNode.a
			);

		}

		if ( ColorManagement.getTransfer( target ) === SRGBTransfer ) {

			outputNode = vec4( sRGBTransferOETF( outputNode.rgb ), outputNode.a );

		}

		return outputNode;

	}

}
```
</details>

#### Methods

##### `resolveColorSpace(builder: NodeBuilder, colorSpace: string): string`

<details><summary>Code</summary>

```ts
resolveColorSpace( builder, colorSpace ) {

		if ( colorSpace === WORKING_COLOR_SPACE ) {

			return ColorManagement.workingColorSpace;

		} else if ( colorSpace === OUTPUT_COLOR_SPACE ) {

			return builder.context.outputColorSpace || builder.renderer.outputColorSpace;

		}

		return colorSpace;

	}
```
</details>

##### `setup(builder: any): Node`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const { colorNode } = this;

		const source = this.resolveColorSpace( builder, this.source );
		const target = this.resolveColorSpace( builder, this.target );

		let outputNode = colorNode;

		if ( ColorManagement.enabled === false || source === target || ! source || ! target ) {

			return outputNode;

		}

		if ( ColorManagement.getTransfer( source ) === SRGBTransfer ) {

			outputNode = vec4( sRGBTransferEOTF( outputNode.rgb ), outputNode.a );

		}

		if ( ColorManagement.getPrimaries( source ) !== ColorManagement.getPrimaries( target ) ) {

			outputNode = vec4(
				mat3( ColorManagement._getMatrix( new Matrix3(), source, target ) ).mul( outputNode.rgb ),
				outputNode.a
			);

		}

		if ( ColorManagement.getTransfer( target ) === SRGBTransfer ) {

			outputNode = vec4( sRGBTransferOETF( outputNode.rgb ), outputNode.a );

		}

		return outputNode;

	}
```
</details>


---