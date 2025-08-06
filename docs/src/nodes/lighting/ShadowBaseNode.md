[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ShadowBaseNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/ShadowBaseNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `property` | `../tsl/TSLBase.js` |
| `positionWorld` | `../accessors/Position.js` |


---

## Functions

### `ShadowBaseNode.setupShadowPosition({ context, material }: any): void`

**JSDoc:**
```typescript
/**
	 * Setups the shadow position node which is by default the predefined TSL node object `shadowPositionWorld`.
	 *
	 * @param {NodeBuilder} object - A configuration object that must at least hold a material reference.
	 */
```

**Parameters:**

- **`{ context, material }`** `any`

**Returns:** `void`

**Calls:**

- `shadowPositionWorld.assign`

**Internal Comments:**
```
// Use assign inside an Fn() (x4)
```

<details><summary>Code</summary>

```typescript
setupShadowPosition( { context, material } ) {

		// Use assign inside an Fn()

		shadowPositionWorld.assign( material.receivedShadowPositionNode || context.shadowPositionWorld || positionWorld );

	}
```
</details>


---

## Classes

### `ShadowBaseNode`

<details><summary>Class Code</summary>

```ts
class ShadowBaseNode extends Node {

	static get type() {

		return 'ShadowBaseNode';

	}

	/**
	 * Constructs a new shadow base node.
	 *
	 * @param {Light} light - The shadow casting light.
	 */
	constructor( light ) {

		super();

		/**
		 * The shadow casting light.
		 *
		 * @type {Light}
		 */
		this.light = light;

		/**
		 * Overwritten since shadows are updated by default per render.
		 *
		 * @type {string}
		 * @default 'render'
		 */
		this.updateBeforeType = NodeUpdateType.RENDER;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isShadowBaseNode = true;

	}

	/**
	 * Setups the shadow position node which is by default the predefined TSL node object `shadowPositionWorld`.
	 *
	 * @param {NodeBuilder} object - A configuration object that must at least hold a material reference.
	 */
	setupShadowPosition( { context, material } ) {

		// Use assign inside an Fn()

		shadowPositionWorld.assign( material.receivedShadowPositionNode || context.shadowPositionWorld || positionWorld );

	}

}
```
</details>

#### Methods

##### `setupShadowPosition({ context, material }: any): void`

<details><summary>Code</summary>

```ts
setupShadowPosition( { context, material } ) {

		// Use assign inside an Fn()

		shadowPositionWorld.assign( material.receivedShadowPositionNode || context.shadowPositionWorld || positionWorld );

	}
```
</details>


---