[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ToneMappingNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/display/ToneMappingNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `../core/TempNode.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `nodeObject` | `../tsl/TSLCore.js` |
| `vec4` | `../tsl/TSLCore.js` |
| `rendererReference` | `../accessors/RendererReferenceNode.js` |
| `NoToneMapping` | `../../constants.js` |
| `hash` | `../core/NodeUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `colorNode` | `any` | let/var | `this.colorNode \|\| builder.context.color` | ✗ |
| `toneMapping` | `number` | let/var | `this.toneMapping` | ✗ |
| `outputNode` | `any` | let/var | `null` | ✗ |


---

## Functions

### `ToneMappingNode.customCacheKey(): number`

**JSDoc:**
```typescript
/**
	 * Overwrites the default `customCacheKey()` implementation by including the tone
	 * mapping type into the cache key.
	 *
	 * @return {number} The hash.
	 */
```

**Returns:** `number`

**Calls:**

- `hash (from ../core/NodeUtils.js)`

<details><summary>Code</summary>

```typescript
customCacheKey() {

		return hash( this.toneMapping );

	}
```
</details>

### `ToneMappingNode.setup(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `builder.renderer.library.getToneMappingFunction`
- `vec4 (from ../tsl/TSLCore.js)`
- `toneMappingFn`
- `console.error`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const colorNode = this.colorNode || builder.context.color;
		const toneMapping = this.toneMapping;

		if ( toneMapping === NoToneMapping ) return colorNode;

		let outputNode = null;

		const toneMappingFn = builder.renderer.library.getToneMappingFunction( toneMapping );

		if ( toneMappingFn !== null ) {

			outputNode = vec4( toneMappingFn( colorNode.rgb, this.exposureNode ), colorNode.a );

		} else {

			console.error( 'ToneMappingNode: Unsupported Tone Mapping configuration.', toneMapping );

			outputNode = colorNode;

		}

		return outputNode;

	}
```
</details>

### `toneMapping(mapping: number, exposure: any, color: any): any`

**Parameters:**

- **`mapping`** `number`
- **`exposure`** `any`
- **`color`** `any`

**Returns:** `any`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( mapping, exposure, color ) => nodeObject( new ToneMappingNode( mapping, nodeObject( exposure ), nodeObject( color ) ) )
```
</details>


---

## Classes

### `ToneMappingNode`

<details><summary>Class Code</summary>

```ts
class ToneMappingNode extends TempNode {

	static get type() {

		return 'ToneMappingNode';

	}

	/**
	 * Constructs a new tone mapping node.
	 *
	 * @param {number} toneMapping - The tone mapping type.
	 * @param {Node} exposureNode - The tone mapping exposure.
	 * @param {Node} [colorNode=null] - The color node to process.
	 */
	constructor( toneMapping, exposureNode = toneMappingExposure, colorNode = null ) {

		super( 'vec3' );

		/**
		 * The tone mapping type.
		 *
		 * @type {number}
		 */
		this.toneMapping = toneMapping;

		/**
		 * The tone mapping exposure.
		 *
		 * @type {Node}
		 * @default null
		 */
		this.exposureNode = exposureNode;

		/**
		 * Represents the color to process.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.colorNode = colorNode;

	}

	/**
	 * Overwrites the default `customCacheKey()` implementation by including the tone
	 * mapping type into the cache key.
	 *
	 * @return {number} The hash.
	 */
	customCacheKey() {

		return hash( this.toneMapping );

	}

	setup( builder ) {

		const colorNode = this.colorNode || builder.context.color;
		const toneMapping = this.toneMapping;

		if ( toneMapping === NoToneMapping ) return colorNode;

		let outputNode = null;

		const toneMappingFn = builder.renderer.library.getToneMappingFunction( toneMapping );

		if ( toneMappingFn !== null ) {

			outputNode = vec4( toneMappingFn( colorNode.rgb, this.exposureNode ), colorNode.a );

		} else {

			console.error( 'ToneMappingNode: Unsupported Tone Mapping configuration.', toneMapping );

			outputNode = colorNode;

		}

		return outputNode;

	}

}
```
</details>

#### Methods

##### `customCacheKey(): number`

<details><summary>Code</summary>

```ts
customCacheKey() {

		return hash( this.toneMapping );

	}
```
</details>

##### `setup(builder: any): any`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const colorNode = this.colorNode || builder.context.color;
		const toneMapping = this.toneMapping;

		if ( toneMapping === NoToneMapping ) return colorNode;

		let outputNode = null;

		const toneMappingFn = builder.renderer.library.getToneMappingFunction( toneMapping );

		if ( toneMappingFn !== null ) {

			outputNode = vec4( toneMappingFn( colorNode.rgb, this.exposureNode ), colorNode.a );

		} else {

			console.error( 'ToneMappingNode: Unsupported Tone Mapping configuration.', toneMapping );

			outputNode = colorNode;

		}

		return outputNode;

	}
```
</details>


---