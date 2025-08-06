[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ShadowMaskModel.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/functions/ShadowMaskModel.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LightingModel` | `../core/LightingModel.js` |
| `diffuseColor` | `../core/PropertyNode.js` |
| `float` | `../tsl/TSLBase.js` |


---

## Functions

### `ShadowMaskModel.direct({ lightNode }: any): void`

**JSDoc:**
```typescript
/**
	 * Only used to save the shadow mask.
	 *
	 * @param {Object} input - The input data.
	 */
```

**Parameters:**

- **`{ lightNode }`** `any`

**Returns:** `void`

**Calls:**

- `this.shadowNode.mulAssign`

<details><summary>Code</summary>

```typescript
direct( { lightNode } ) {

		if ( lightNode.shadowNode !== null ) {

			this.shadowNode.mulAssign( lightNode.shadowNode );

		}

	}
```
</details>

### `ShadowMaskModel.finish({ context }: any): void`

**JSDoc:**
```typescript
/**
	 * Uses the shadow mask to produce the final color.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`{ context }`** `any`

**Returns:** `void`

**Calls:**

- `diffuseColor.a.mulAssign`
- `this.shadowNode.oneMinus`
- `context.outgoingLight.rgb.assign`

<details><summary>Code</summary>

```typescript
finish( { context } ) {

		diffuseColor.a.mulAssign( this.shadowNode.oneMinus() );

		context.outgoingLight.rgb.assign( diffuseColor.rgb ); // TODO: Optimize LightsNode to avoid this assignment

	}
```
</details>


---

## Classes

### `ShadowMaskModel`

<details><summary>Class Code</summary>

```ts
class ShadowMaskModel extends LightingModel {

	/**
	 * Constructs a new shadow mask model.
	 */
	constructor() {

		super();

		/**
		 * The shadow mask node.
		 *
		 * @type {Node}
		 */
		this.shadowNode = float( 1 ).toVar( 'shadowMask' );

	}

	/**
	 * Only used to save the shadow mask.
	 *
	 * @param {Object} input - The input data.
	 */
	direct( { lightNode } ) {

		if ( lightNode.shadowNode !== null ) {

			this.shadowNode.mulAssign( lightNode.shadowNode );

		}

	}

	/**
	 * Uses the shadow mask to produce the final color.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	finish( { context } ) {

		diffuseColor.a.mulAssign( this.shadowNode.oneMinus() );

		context.outgoingLight.rgb.assign( diffuseColor.rgb ); // TODO: Optimize LightsNode to avoid this assignment

	}

}
```
</details>

#### Methods

##### `direct({ lightNode }: any): void`

<details><summary>Code</summary>

```ts
direct( { lightNode } ) {

		if ( lightNode.shadowNode !== null ) {

			this.shadowNode.mulAssign( lightNode.shadowNode );

		}

	}
```
</details>

##### `finish({ context }: any): void`

<details><summary>Code</summary>

```ts
finish( { context } ) {

		diffuseColor.a.mulAssign( this.shadowNode.oneMinus() );

		context.outgoingLight.rgb.assign( diffuseColor.rgb ); // TODO: Optimize LightsNode to avoid this assignment

	}
```
</details>


---