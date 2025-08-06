[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ViewportSharedTextureNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/display/ViewportSharedTextureNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ViewportTextureNode` | `./ViewportTextureNode.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `screenUV` | `./ScreenNode.js` |
| `FramebufferTexture` | `../../textures/FramebufferTexture.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_sharedFramebuffer` | `any` | let/var | `null` | ✗ |


---

## Functions

### `ViewportSharedTextureNode.updateReference(): this`

**Returns:** `this`

<details><summary>Code</summary>

```typescript
updateReference() {

		return this;

	}
```
</details>


---

## Classes

### `ViewportSharedTextureNode`

<details><summary>Class Code</summary>

```ts
class ViewportSharedTextureNode extends ViewportTextureNode {

	static get type() {

		return 'ViewportSharedTextureNode';

	}

	/**
	 * Constructs a new viewport shared texture node.
	 *
	 * @param {Node} [uvNode=screenUV] - The uv node.
	 * @param {?Node} [levelNode=null] - The level node.
	 */
	constructor( uvNode = screenUV, levelNode = null ) {

		if ( _sharedFramebuffer === null ) {

			_sharedFramebuffer = new FramebufferTexture();

		}

		super( uvNode, levelNode, _sharedFramebuffer );

	}

	updateReference() {

		return this;

	}

}
```
</details>

#### Methods

##### `updateReference(): this`

<details><summary>Code</summary>

```ts
updateReference() {

		return this;

	}
```
</details>


---