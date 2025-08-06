[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RendererReferenceNode.js`

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
📂 **`src/nodes/accessors/RendererReferenceNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ReferenceBaseNode` | `./ReferenceBaseNode.js` |
| `nodeObject` | `../tsl/TSLCore.js` |
| `renderGroup` | `../core/UniformGroupNode.js` |


---

## Functions

### `RendererReferenceNode.updateReference(state: any): any`

**JSDoc:**
```typescript
/**
	 * Updates the reference based on the given state. The state is only evaluated
	 * {@link RendererReferenceNode#renderer} is not set.
	 *
	 * @param {(NodeFrame|NodeBuilder)} state - The current state.
	 * @return {Object} The updated reference.
	 */
```

**Parameters:**

- **`state`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
updateReference( state ) {

		this.reference = this.renderer !== null ? this.renderer : state.renderer;

		return this.reference;

	}
```
</details>

### `rendererReference(name: string, type: string, renderer: Renderer): RendererReferenceNode`

**Parameters:**

- **`name`** `string`
- **`type`** `string`
- **`renderer`** `Renderer`

**Returns:** `RendererReferenceNode`

**Calls:**

- `nodeObject (from ../tsl/TSLCore.js)`

<details><summary>Code</summary>

```typescript
( name, type, renderer = null ) => nodeObject( new RendererReferenceNode( name, type, renderer ) )
```
</details>


---

## Classes

### `RendererReferenceNode`

<details><summary>Class Code</summary>

```ts
class RendererReferenceNode extends ReferenceBaseNode {

	static get type() {

		return 'RendererReferenceNode';

	}

	/**
	 * Constructs a new renderer reference node.
	 *
	 * @param {string} property - The name of the property the node refers to.
	 * @param {string} inputType - The uniform type that should be used to represent the property value.
	 * @param {?Renderer} [renderer=null] - The renderer the property belongs to. When no renderer is set,
	 * the node refers to the renderer of the current state.
	 */
	constructor( property, inputType, renderer = null ) {

		super( property, inputType, renderer );

		/**
		 * The renderer the property belongs to. When no renderer is set,
		 * the node refers to the renderer of the current state.
		 *
		 * @type {?Renderer}
		 * @default null
		 */
		this.renderer = renderer;

		this.setGroup( renderGroup );

	}

	/**
	 * Updates the reference based on the given state. The state is only evaluated
	 * {@link RendererReferenceNode#renderer} is not set.
	 *
	 * @param {(NodeFrame|NodeBuilder)} state - The current state.
	 * @return {Object} The updated reference.
	 */
	updateReference( state ) {

		this.reference = this.renderer !== null ? this.renderer : state.renderer;

		return this.reference;

	}

}
```
</details>

#### Methods

##### `updateReference(state: any): any`

<details><summary>Code</summary>

```ts
updateReference( state ) {

		this.reference = this.renderer !== null ? this.renderer : state.renderer;

		return this.reference;

	}
```
</details>


---