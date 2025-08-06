[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LineDashedNodeMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 11 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/nodes/LineDashedNodeMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeMaterial` | `./NodeMaterial.js` |
| `attribute` | `../../nodes/core/AttributeNode.js` |
| `materialLineDashOffset` | `../../nodes/accessors/MaterialNode.js` |
| `materialLineDashSize` | `../../nodes/accessors/MaterialNode.js` |
| `materialLineGapSize` | `../../nodes/accessors/MaterialNode.js` |
| `materialLineScale` | `../../nodes/accessors/MaterialNode.js` |
| `dashSize` | `../../nodes/core/PropertyNode.js` |
| `gapSize` | `../../nodes/core/PropertyNode.js` |
| `varying` | `../../nodes/tsl/TSLBase.js` |
| `float` | `../../nodes/tsl/TSLBase.js` |
| `LineDashedMaterial` | `../LineDashedMaterial.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_defaultValues` | `LineDashedMaterial` | let/var | `new LineDashedMaterial()` | ✗ |
| `offsetNode` | `any` | let/var | `this.offsetNode ? float( this.offsetNode ) : materialLineDashOffset` | ✗ |
| `dashScaleNode` | `any` | let/var | `this.dashScaleNode ? float( this.dashScaleNode ) : materialLineScale` | ✗ |
| `dashSizeNode` | `any` | let/var | `this.dashSizeNode ? float( this.dashSizeNode ) : materialLineDashSize` | ✗ |
| `gapSizeNode` | `any` | let/var | `this.gapSizeNode ? float( this.gapSizeNode ) : materialLineGapSize` | ✗ |
| `vLineDistanceOffset` | `any` | let/var | `offsetNode ? vLineDistance.add( offsetNode ) : vLineDistance` | ✗ |


---

## Functions

### `LineDashedNodeMaterial.setupVariants(): void`

**JSDoc:**
```typescript
/**
	 * Setups the dash specific node variables.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Returns:** `void`

**Calls:**

- `float (from ../../nodes/tsl/TSLBase.js)`
- `dashSize.assign`
- `gapSize.assign`
- `varying (from ../../nodes/tsl/TSLBase.js)`
- `attribute( 'lineDistance' ).mul`
- `vLineDistance.add`
- `vLineDistanceOffset.mod( dashSize.add( gapSize ) ).greaterThan( dashSize ).discard`

<details><summary>Code</summary>

```typescript
setupVariants( /* builder */ ) {

		const offsetNode = this.offsetNode ? float( this.offsetNode ) : materialLineDashOffset;
		const dashScaleNode = this.dashScaleNode ? float( this.dashScaleNode ) : materialLineScale;
		const dashSizeNode = this.dashSizeNode ? float( this.dashSizeNode ) : materialLineDashSize;
		const gapSizeNode = this.gapSizeNode ? float( this.gapSizeNode ) : materialLineGapSize;

		dashSize.assign( dashSizeNode );
		gapSize.assign( gapSizeNode );

		const vLineDistance = varying( attribute( 'lineDistance' ).mul( dashScaleNode ) );
		const vLineDistanceOffset = offsetNode ? vLineDistance.add( offsetNode ) : vLineDistance;

		vLineDistanceOffset.mod( dashSize.add( gapSize ) ).greaterThan( dashSize ).discard();

	}
```
</details>


---

## Classes

### `LineDashedNodeMaterial`

<details><summary>Class Code</summary>

```ts
class LineDashedNodeMaterial extends NodeMaterial {

	static get type() {

		return 'LineDashedNodeMaterial';

	}

	/**
	 * Constructs a new line dashed node material.
	 *
	 * @param {Object} [parameters] - The configuration parameter.
	 */
	constructor( parameters ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isLineDashedNodeMaterial = true;

		this.setDefaultValues( _defaultValues );

		/**
		 * The dash offset.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.dashOffset = 0;

		/**
		 * The offset of dash materials is by default inferred from the `dashOffset`
		 * property. This node property allows to overwrite the default
		 * and define the offset with a node instead.
		 *
		 * If you don't want to overwrite the offset but modify the existing
		 * value instead, use {@link materialLineDashOffset}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.offsetNode = null;

		/**
		 * The scale of dash materials is by default inferred from the `scale`
		 * property. This node property allows to overwrite the default
		 * and define the scale with a node instead.
		 *
		 * If you don't want to overwrite the scale but modify the existing
		 * value instead, use {@link materialLineScale}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.dashScaleNode = null;

		/**
		 * The dash size of dash materials is by default inferred from the `dashSize`
		 * property. This node property allows to overwrite the default
		 * and define the dash size with a node instead.
		 *
		 * If you don't want to overwrite the dash size but modify the existing
		 * value instead, use {@link materialLineDashSize}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.dashSizeNode = null;

		/**
		 * The gap size of dash materials is by default inferred from the `gapSize`
		 * property. This node property allows to overwrite the default
		 * and define the gap size with a node instead.
		 *
		 * If you don't want to overwrite the gap size but modify the existing
		 * value instead, use {@link materialLineGapSize}.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.gapSizeNode = null;

		this.setValues( parameters );

	}

	/**
	 * Setups the dash specific node variables.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	setupVariants( /* builder */ ) {

		const offsetNode = this.offsetNode ? float( this.offsetNode ) : materialLineDashOffset;
		const dashScaleNode = this.dashScaleNode ? float( this.dashScaleNode ) : materialLineScale;
		const dashSizeNode = this.dashSizeNode ? float( this.dashSizeNode ) : materialLineDashSize;
		const gapSizeNode = this.gapSizeNode ? float( this.gapSizeNode ) : materialLineGapSize;

		dashSize.assign( dashSizeNode );
		gapSize.assign( gapSizeNode );

		const vLineDistance = varying( attribute( 'lineDistance' ).mul( dashScaleNode ) );
		const vLineDistanceOffset = offsetNode ? vLineDistance.add( offsetNode ) : vLineDistance;

		vLineDistanceOffset.mod( dashSize.add( gapSize ) ).greaterThan( dashSize ).discard();

	}

}
```
</details>

#### Methods

##### `setupVariants(): void`

<details><summary>Code</summary>

```ts
setupVariants( /* builder */ ) {

		const offsetNode = this.offsetNode ? float( this.offsetNode ) : materialLineDashOffset;
		const dashScaleNode = this.dashScaleNode ? float( this.dashScaleNode ) : materialLineScale;
		const dashSizeNode = this.dashSizeNode ? float( this.dashSizeNode ) : materialLineDashSize;
		const gapSizeNode = this.gapSizeNode ? float( this.gapSizeNode ) : materialLineGapSize;

		dashSize.assign( dashSizeNode );
		gapSize.assign( gapSizeNode );

		const vLineDistance = varying( attribute( 'lineDistance' ).mul( dashScaleNode ) );
		const vLineDistanceOffset = offsetNode ? vLineDistance.add( offsetNode ) : vLineDistance;

		vLineDistanceOffset.mod( dashSize.add( gapSize ) ).greaterThan( dashSize ).discard();

	}
```
</details>


---