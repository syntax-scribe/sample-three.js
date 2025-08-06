[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `RotateNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/utils/RotateNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `../core/TempNode.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `vec4` | `../tsl/TSLBase.js` |
| `mat2` | `../tsl/TSLBase.js` |
| `mat4` | `../tsl/TSLBase.js` |
| `cos` | `../math/MathNode.js` |
| `sin` | `../math/MathNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `rotation` | `Node` | let/var | `rotationNode` | ✗ |


---

## Functions

### `RotateNode.getNodeType(builder: NodeBuilder): string`

**JSDoc:**
```typescript
/**
	 * The type of the {@link RotateNode#positionNode} defines the node's type.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node's type.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `string`

**Calls:**

- `this.positionNode.getNodeType`

<details><summary>Code</summary>

```typescript
getNodeType( builder ) {

		return this.positionNode.getNodeType( builder );

	}
```
</details>

### `RotateNode.setup(builder: any): any`

**Parameters:**

- **`builder`** `any`

**Returns:** `any`

**Calls:**

- `this.getNodeType`
- `rotationNode.cos`
- `rotationNode.sin`
- `mat2 (from ../tsl/TSLBase.js)`
- `sinAngle.negate`
- `rotationMatrix.mul`
- `mat4 (from ../tsl/TSLBase.js)`
- `vec4 (from ../tsl/TSLBase.js)`
- `cos (from ../math/MathNode.js)`
- `sin( rotation.x ).negate`
- `sin (from ../math/MathNode.js)`
- `sin( rotation.y ).negate`
- `sin( rotation.z ).negate`
- `rotationXMatrix.mul( rotationYMatrix ).mul( rotationZMatrix ).mul`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const { rotationNode, positionNode } = this;

		const nodeType = this.getNodeType( builder );

		if ( nodeType === 'vec2' ) {

			const cosAngle = rotationNode.cos();
			const sinAngle = rotationNode.sin();

			const rotationMatrix = mat2(
				cosAngle, sinAngle,
				sinAngle.negate(), cosAngle
			);

			return rotationMatrix.mul( positionNode );

		} else {

			const rotation = rotationNode;
			const rotationXMatrix = mat4( vec4( 1.0, 0.0, 0.0, 0.0 ), vec4( 0.0, cos( rotation.x ), sin( rotation.x ).negate(), 0.0 ), vec4( 0.0, sin( rotation.x ), cos( rotation.x ), 0.0 ), vec4( 0.0, 0.0, 0.0, 1.0 ) );
			const rotationYMatrix = mat4( vec4( cos( rotation.y ), 0.0, sin( rotation.y ), 0.0 ), vec4( 0.0, 1.0, 0.0, 0.0 ), vec4( sin( rotation.y ).negate(), 0.0, cos( rotation.y ), 0.0 ), vec4( 0.0, 0.0, 0.0, 1.0 ) );
			const rotationZMatrix = mat4( vec4( cos( rotation.z ), sin( rotation.z ).negate(), 0.0, 0.0 ), vec4( sin( rotation.z ), cos( rotation.z ), 0.0, 0.0 ), vec4( 0.0, 0.0, 1.0, 0.0 ), vec4( 0.0, 0.0, 0.0, 1.0 ) );

			return rotationXMatrix.mul( rotationYMatrix ).mul( rotationZMatrix ).mul( vec4( positionNode, 1.0 ) ).xyz;

		}

	}
```
</details>


---

## Classes

### `RotateNode`

<details><summary>Class Code</summary>

```ts
class RotateNode extends TempNode {

	static get type() {

		return 'RotateNode';

	}

	/**
	 * Constructs a new rotate node.
	 *
	 * @param {Node} positionNode - The position node.
	 * @param {Node} rotationNode - Represents the rotation that is applied to the position node. Depending
	 * on whether the position data are 2D or 3D, the rotation is expressed a single float value or an Euler value.
	 */
	constructor( positionNode, rotationNode ) {

		super();

		/**
		 * The position node.
		 *
		 * @type {Node}
		 */
		this.positionNode = positionNode;

		/**
		 *  Represents the rotation that is applied to the position node.
		 *  Depending on whether the position data are 2D or 3D, the rotation is expressed a single float value or an Euler value.
		 *
		 * @type {Node}
		 */
		this.rotationNode = rotationNode;

	}

	/**
	 * The type of the {@link RotateNode#positionNode} defines the node's type.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node's type.
	 */
	getNodeType( builder ) {

		return this.positionNode.getNodeType( builder );

	}

	setup( builder ) {

		const { rotationNode, positionNode } = this;

		const nodeType = this.getNodeType( builder );

		if ( nodeType === 'vec2' ) {

			const cosAngle = rotationNode.cos();
			const sinAngle = rotationNode.sin();

			const rotationMatrix = mat2(
				cosAngle, sinAngle,
				sinAngle.negate(), cosAngle
			);

			return rotationMatrix.mul( positionNode );

		} else {

			const rotation = rotationNode;
			const rotationXMatrix = mat4( vec4( 1.0, 0.0, 0.0, 0.0 ), vec4( 0.0, cos( rotation.x ), sin( rotation.x ).negate(), 0.0 ), vec4( 0.0, sin( rotation.x ), cos( rotation.x ), 0.0 ), vec4( 0.0, 0.0, 0.0, 1.0 ) );
			const rotationYMatrix = mat4( vec4( cos( rotation.y ), 0.0, sin( rotation.y ), 0.0 ), vec4( 0.0, 1.0, 0.0, 0.0 ), vec4( sin( rotation.y ).negate(), 0.0, cos( rotation.y ), 0.0 ), vec4( 0.0, 0.0, 0.0, 1.0 ) );
			const rotationZMatrix = mat4( vec4( cos( rotation.z ), sin( rotation.z ).negate(), 0.0, 0.0 ), vec4( sin( rotation.z ), cos( rotation.z ), 0.0, 0.0 ), vec4( 0.0, 0.0, 1.0, 0.0 ), vec4( 0.0, 0.0, 0.0, 1.0 ) );

			return rotationXMatrix.mul( rotationYMatrix ).mul( rotationZMatrix ).mul( vec4( positionNode, 1.0 ) ).xyz;

		}

	}

}
```
</details>

#### Methods

##### `getNodeType(builder: NodeBuilder): string`

<details><summary>Code</summary>

```ts
getNodeType( builder ) {

		return this.positionNode.getNodeType( builder );

	}
```
</details>

##### `setup(builder: any): any`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const { rotationNode, positionNode } = this;

		const nodeType = this.getNodeType( builder );

		if ( nodeType === 'vec2' ) {

			const cosAngle = rotationNode.cos();
			const sinAngle = rotationNode.sin();

			const rotationMatrix = mat2(
				cosAngle, sinAngle,
				sinAngle.negate(), cosAngle
			);

			return rotationMatrix.mul( positionNode );

		} else {

			const rotation = rotationNode;
			const rotationXMatrix = mat4( vec4( 1.0, 0.0, 0.0, 0.0 ), vec4( 0.0, cos( rotation.x ), sin( rotation.x ).negate(), 0.0 ), vec4( 0.0, sin( rotation.x ), cos( rotation.x ), 0.0 ), vec4( 0.0, 0.0, 0.0, 1.0 ) );
			const rotationYMatrix = mat4( vec4( cos( rotation.y ), 0.0, sin( rotation.y ), 0.0 ), vec4( 0.0, 1.0, 0.0, 0.0 ), vec4( sin( rotation.y ).negate(), 0.0, cos( rotation.y ), 0.0 ), vec4( 0.0, 0.0, 0.0, 1.0 ) );
			const rotationZMatrix = mat4( vec4( cos( rotation.z ), sin( rotation.z ).negate(), 0.0, 0.0 ), vec4( sin( rotation.z ), cos( rotation.z ), 0.0, 0.0 ), vec4( 0.0, 0.0, 1.0, 0.0 ), vec4( 0.0, 0.0, 0.0, 1.0 ) );

			return rotationXMatrix.mul( rotationYMatrix ).mul( rotationZMatrix ).mul( vec4( positionNode, 1.0 ) ).xyz;

		}

	}
```
</details>


---