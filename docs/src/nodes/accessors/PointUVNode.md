[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `PointUVNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/PointUVNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `nodeImmutable` | `../tsl/TSLBase.js` |


---

## Functions

### `PointUVNode.generate(): string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
generate( /*builder*/ ) {

		return 'vec2( gl_PointCoord.x, 1.0 - gl_PointCoord.y )';

	}
```
</details>


---

## Classes

### `PointUVNode`

<details><summary>Class Code</summary>

```ts
class PointUVNode extends Node {

	static get type() {

		return 'PointUVNode';

	}

	/**
	 * Constructs a new point uv node.
	 */
	constructor() {

		super( 'vec2' );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isPointUVNode = true;

	}

	generate( /*builder*/ ) {

		return 'vec2( gl_PointCoord.x, 1.0 - gl_PointCoord.y )';

	}

}
```
</details>

#### Methods

##### `generate(): string`

<details><summary>Code</summary>

```ts
generate( /*builder*/ ) {

		return 'vec2( gl_PointCoord.x, 1.0 - gl_PointCoord.y )';

	}
```
</details>


---