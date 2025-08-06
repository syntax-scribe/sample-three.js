[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ViewportDepthTextureNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/display/ViewportDepthTextureNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `ViewportTextureNode` | `./ViewportTextureNode.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `screenUV` | `./ScreenNode.js` |
| `DepthTexture` | `../../textures/DepthTexture.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `sharedDepthbuffer` | `any` | let/var | `null` | ✗ |


---

## Classes

### `ViewportDepthTextureNode`

<details><summary>Class Code</summary>

```ts
class ViewportDepthTextureNode extends ViewportTextureNode {

	static get type() {

		return 'ViewportDepthTextureNode';

	}

	/**
	 * Constructs a new viewport depth texture node.
	 *
	 * @param {Node} [uvNode=screenUV] - The uv node.
	 * @param {?Node} [levelNode=null] - The level node.
	 */
	constructor( uvNode = screenUV, levelNode = null ) {

		if ( sharedDepthbuffer === null ) {

			sharedDepthbuffer = new DepthTexture();

		}

		super( uvNode, levelNode, sharedDepthbuffer );

	}

}
```
</details>


---