[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ModelNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/ModelNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Object3DNode` | `./Object3DNode.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `nodeImmutable` | `../tsl/TSLBase.js` |
| `uniform` | `../core/UniformNode.js` |
| `Matrix4` | `../../math/Matrix4.js` |
| `cameraViewMatrix` | `./Camera.js` |
| `Matrix3` | `../../math/Matrix3.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `isHighPrecisionModelViewMatrix` | `any` | let/var | `builder.context.isHighPrecisionModelViewMatrix` | ✗ |


---

## Functions

### `ModelNode.update(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
	 * Extracts the model reference from the frame state and then
	 * updates the uniform value depending on the scope.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
```

**Parameters:**

- **`frame`** `NodeFrame`

**Returns:** `void`

**Calls:**

- `super.update`

<details><summary>Code</summary>

```typescript
update( frame ) {

		this.object3d = frame.object;

		super.update( frame );

	}
```
</details>


---

## Classes

### `ModelNode`

<details><summary>Class Code</summary>

```ts
class ModelNode extends Object3DNode {

	static get type() {

		return 'ModelNode';

	}

	/**
	 * Constructs a new object model node.
	 *
	 * @param {('position'|'viewPosition'|'direction'|'scale'|'worldMatrix')} scope - The node represents a different type of transformation depending on the scope.
	 */
	constructor( scope ) {

		super( scope );

	}

	/**
	 * Extracts the model reference from the frame state and then
	 * updates the uniform value depending on the scope.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
	update( frame ) {

		this.object3d = frame.object;

		super.update( frame );

	}

}
```
</details>

#### Methods

##### `update(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
update( frame ) {

		this.object3d = frame.object;

		super.update( frame );

	}
```
</details>


---