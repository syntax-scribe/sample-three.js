[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SpriteSheetUVNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/utils/SpriteSheetUVNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `uv` | `../accessors/UV.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `float` | `../tsl/TSLBase.js` |
| `vec2` | `../tsl/TSLBase.js` |


---

## Functions

### `SpriteSheetUVNode.setup(): any`

**Returns:** `any`

**Calls:**

- `frameNode.mod( width.mul( height ) ).floor`
- `frameNum.mod`
- `height.sub`
- `frameNum.add( 1 ).div( width ).ceil`
- `countNode.reciprocal`
- `vec2 (from ../tsl/TSLBase.js)`
- `uvNode.add( uvFrameOffset ).mul`

<details><summary>Code</summary>

```typescript
setup() {

		const { frameNode, uvNode, countNode } = this;

		const { width, height } = countNode;

		const frameNum = frameNode.mod( width.mul( height ) ).floor();

		const column = frameNum.mod( width );
		const row = height.sub( frameNum.add( 1 ).div( width ).ceil() );

		const scale = countNode.reciprocal();
		const uvFrameOffset = vec2( column, row );

		return uvNode.add( uvFrameOffset ).mul( scale );

	}
```
</details>


---

## Classes

### `SpriteSheetUVNode`

<details><summary>Class Code</summary>

```ts
class SpriteSheetUVNode extends Node {

	static get type() {

		return 'SpriteSheetUVNode';

	}

	/**
	 * Constructs a new sprite sheet uv node.
	 *
	 * @param {Node<vec2>} countNode - The node that defines the number of sprites in the x and y direction (e.g 6x6).
	 * @param {Node<vec2>} [uvNode=uv()] - The uv node.
	 * @param {Node<float>} [frameNode=float()] - The node that defines the current frame/sprite.
	 */
	constructor( countNode, uvNode = uv(), frameNode = float( 0 ) ) {

		super( 'vec2' );

		/**
		 * The node that defines the number of sprites in the x and y direction (e.g 6x6).
		 *
		 * @type {Node<vec2>}
		 */
		this.countNode = countNode;

		/**
		 * The uv node.
		 *
		 * @type {Node<vec2>}
		 */
		this.uvNode = uvNode;

		/**
		 * The node that defines the current frame/sprite.
		 *
		 * @type {Node<float>}
		 */
		this.frameNode = frameNode;

	}

	setup() {

		const { frameNode, uvNode, countNode } = this;

		const { width, height } = countNode;

		const frameNum = frameNode.mod( width.mul( height ) ).floor();

		const column = frameNum.mod( width );
		const row = height.sub( frameNum.add( 1 ).div( width ).ceil() );

		const scale = countNode.reciprocal();
		const uvFrameOffset = vec2( column, row );

		return uvNode.add( uvFrameOffset ).mul( scale );

	}

}
```
</details>

#### Methods

##### `setup(): any`

<details><summary>Code</summary>

```ts
setup() {

		const { frameNode, uvNode, countNode } = this;

		const { width, height } = countNode;

		const frameNum = frameNode.mod( width.mul( height ) ).floor();

		const column = frameNum.mod( width );
		const row = height.sub( frameNum.add( 1 ).div( width ).ceil() );

		const scale = countNode.reciprocal();
		const uvFrameOffset = vec2( column, row );

		return uvNode.add( uvFrameOffset ).mul( scale );

	}
```
</details>


---