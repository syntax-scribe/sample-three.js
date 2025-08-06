[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RemapNode.js`

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
📂 **`src/nodes/utils/RemapNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `float` | `../tsl/TSLCore.js` |
| `addMethodChaining` | `../tsl/TSLCore.js` |
| `nodeProxy` | `../tsl/TSLCore.js` |


---

## Functions

### `RemapNode.setup(): any`

**Returns:** `any`

**Calls:**

- `node.sub( inLowNode ).div`
- `inHighNode.sub`
- `t.clamp`
- `t.mul( outHighNode.sub( outLowNode ) ).add`

<details><summary>Code</summary>

```typescript
setup() {

		const { node, inLowNode, inHighNode, outLowNode, outHighNode, doClamp } = this;

		let t = node.sub( inLowNode ).div( inHighNode.sub( inLowNode ) );

		if ( doClamp === true ) t = t.clamp();

		return t.mul( outHighNode.sub( outLowNode ) ).add( outLowNode );

	}
```
</details>


---

## Classes

### `RemapNode`

<details><summary>Class Code</summary>

```ts
class RemapNode extends Node {

	static get type() {

		return 'RemapNode';

	}

	/**
	 * Constructs a new remap node.
	 *
	 * @param {Node} node - The node that should be remapped.
	 * @param {Node} inLowNode - The source or current lower bound of the range.
	 * @param {Node} inHighNode - The source or current upper bound of the range.
	 * @param {Node} [outLowNode=float(0)] - The target lower bound of the range.
	 * @param {Node} [outHighNode=float(1)] - The target upper bound of the range.
	 */
	constructor( node, inLowNode, inHighNode, outLowNode = float( 0 ), outHighNode = float( 1 ) ) {

		super();

		/**
		 * The node that should be remapped.
		 *
		 * @type {Node}
		 */
		this.node = node;

		/**
		 * The source or current lower bound of the range.
		 *
		 * @type {Node}
		 */
		this.inLowNode = inLowNode;

		/**
		 * The source or current upper bound of the range.
		 *
		 * @type {Node}
		 */
		this.inHighNode = inHighNode;

		/**
		 * The target lower bound of the range.
		 *
		 * @type {Node}
		 * @default float(0)
		 */
		this.outLowNode = outLowNode;

		/**
		 * The target upper bound of the range.
		 *
		 * @type {Node}
		 * @default float(1)
		 */
		this.outHighNode = outHighNode;

		/**
		 * Whether the node value should be clamped before
		 * remapping it to the target range.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.doClamp = true;

	}

	setup() {

		const { node, inLowNode, inHighNode, outLowNode, outHighNode, doClamp } = this;

		let t = node.sub( inLowNode ).div( inHighNode.sub( inLowNode ) );

		if ( doClamp === true ) t = t.clamp();

		return t.mul( outHighNode.sub( outLowNode ) ).add( outLowNode );

	}

}
```
</details>

#### Methods

##### `setup(): any`

<details><summary>Code</summary>

```ts
setup() {

		const { node, inLowNode, inHighNode, outLowNode, outHighNode, doClamp } = this;

		let t = node.sub( inLowNode ).div( inHighNode.sub( inLowNode ) );

		if ( doClamp === true ) t = t.clamp();

		return t.mul( outHighNode.sub( outLowNode ) ).add( outLowNode );

	}
```
</details>


---