[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BumpMapNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 10 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/display/BumpMapNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `../core/TempNode.js` |
| `uv` | `../accessors/UV.js` |
| `normalView` | `../accessors/Normal.js` |
| `positionView` | `../accessors/Position.js` |
| `faceDirection` | `./FrontFacingNode.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `float` | `../tsl/TSLBase.js` |
| `vec2` | `../tsl/TSLBase.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `vN` | `any` | let/var | `surf_norm` | ✗ |
| `bumpScale` | `any` | let/var | `this.scaleNode !== null ? this.scaleNode : 1` | ✗ |


---

## Functions

### `sampleTexture(callback: any): any`

**Parameters:**

- **`callback`** `any`

**Returns:** `any`

**Calls:**

- `textureNode.cache().context`

<details><summary>Code</summary>

```typescript
( callback ) => textureNode.cache().context( { getUV: ( texNode ) => callback( texNode.uvNode || uv() ), forceUVContext: true } )
```
</details>

### `getUV(texNode: any): any`

**Parameters:**

- **`texNode`** `any`

**Returns:** `any`

**Calls:**

- `callback`

<details><summary>Code</summary>

```typescript
( texNode ) => callback( texNode.uvNode || uv() )
```
</details>

### `getUV(texNode: any): any`

**Parameters:**

- **`texNode`** `any`

**Returns:** `any`

**Calls:**

- `callback`

<details><summary>Code</summary>

```typescript
( texNode ) => callback( texNode.uvNode || uv() )
```
</details>

### `getUV(texNode: any): any`

**Parameters:**

- **`texNode`** `any`

**Returns:** `any`

**Calls:**

- `callback`

<details><summary>Code</summary>

```typescript
( texNode ) => callback( texNode.uvNode || uv() )
```
</details>

### `getUV(texNode: any): any`

**Parameters:**

- **`texNode`** `any`

**Returns:** `any`

**Calls:**

- `callback`

<details><summary>Code</summary>

```typescript
( texNode ) => callback( texNode.uvNode || uv() )
```
</details>

### `getUV(texNode: any): any`

**Parameters:**

- **`texNode`** `any`

**Returns:** `any`

**Calls:**

- `callback`

<details><summary>Code</summary>

```typescript
( texNode ) => callback( texNode.uvNode || uv() )
```
</details>

### `getUV(texNode: any): any`

**Parameters:**

- **`texNode`** `any`

**Returns:** `any`

**Calls:**

- `callback`

<details><summary>Code</summary>

```typescript
( texNode ) => callback( texNode.uvNode || uv() )
```
</details>

### `getUV(texNode: any): any`

**Parameters:**

- **`texNode`** `any`

**Returns:** `any`

**Calls:**

- `callback`

<details><summary>Code</summary>

```typescript
( texNode ) => callback( texNode.uvNode || uv() )
```
</details>

### `getUV(texNode: any): any`

**Parameters:**

- **`texNode`** `any`

**Returns:** `any`

**Calls:**

- `callback`

<details><summary>Code</summary>

```typescript
( texNode ) => callback( texNode.uvNode || uv() )
```
</details>

### `BumpMapNode.setup(): void`

**Returns:** `void`

**Calls:**

- `dHdxy_fwd`
- `perturbNormalArb`

<details><summary>Code</summary>

```typescript
setup() {

		const bumpScale = this.scaleNode !== null ? this.scaleNode : 1;
		const dHdxy = dHdxy_fwd( { textureNode: this.textureNode, bumpScale } );

		return perturbNormalArb( {
			surf_pos: positionView,
			surf_norm: normalView,
			dHdxy
		} );

	}
```
</details>


---

## Classes

### `BumpMapNode`

<details><summary>Class Code</summary>

```ts
class BumpMapNode extends TempNode {

	static get type() {

		return 'BumpMapNode';

	}

	/**
	 * Constructs a new bump map node.
	 *
	 * @param {Node<float>} textureNode - Represents the bump map data.
	 * @param {?Node<float>} [scaleNode=null] - Controls the intensity of the bump effect.
	 */
	constructor( textureNode, scaleNode = null ) {

		super( 'vec3' );

		/**
		 * Represents the bump map data.
		 *
		 * @type {Node<float>}
		 */
		this.textureNode = textureNode;

		/**
		 * Controls the intensity of the bump effect.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.scaleNode = scaleNode;

	}

	setup() {

		const bumpScale = this.scaleNode !== null ? this.scaleNode : 1;
		const dHdxy = dHdxy_fwd( { textureNode: this.textureNode, bumpScale } );

		return perturbNormalArb( {
			surf_pos: positionView,
			surf_norm: normalView,
			dHdxy
		} );

	}

}
```
</details>

#### Methods

##### `setup(): void`

<details><summary>Code</summary>

```ts
setup() {

		const bumpScale = this.scaleNode !== null ? this.scaleNode : 1;
		const dHdxy = dHdxy_fwd( { textureNode: this.textureNode, bumpScale } );

		return perturbNormalArb( {
			surf_pos: positionView,
			surf_norm: normalView,
			dHdxy
		} );

	}
```
</details>


---