[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `DirectionalLightNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/lighting/DirectionalLightNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `AnalyticLightNode` | `./AnalyticLightNode.js` |
| `lightTargetDirection` | `../accessors/Lights.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `lightColor` | `Node` | let/var | `this.colorNode` | ✗ |


---

## Functions

### `DirectionalLightNode.setupDirect(): { lightDirection: any; lightColor: Node; }`

**Returns:** `{ lightDirection: any; lightColor: Node; }`

**Calls:**

- `lightTargetDirection (from ../accessors/Lights.js)`

<details><summary>Code</summary>

```typescript
setupDirect() {

		const lightColor = this.colorNode;
		const lightDirection = lightTargetDirection( this.light );

		return { lightDirection, lightColor };

	}
```
</details>


---

## Classes

### `DirectionalLightNode`

<details><summary>Class Code</summary>

```ts
class DirectionalLightNode extends AnalyticLightNode {

	static get type() {

		return 'DirectionalLightNode';

	}

	/**
	 * Constructs a new directional light node.
	 *
	 * @param {?DirectionalLight} [light=null] - The directional light source.
	 */
	constructor( light = null ) {

		super( light );

	}

	setupDirect() {

		const lightColor = this.colorNode;
		const lightDirection = lightTargetDirection( this.light );

		return { lightDirection, lightColor };

	}

}
```
</details>

#### Methods

##### `setupDirect(): { lightDirection: any; lightColor: Node; }`

<details><summary>Code</summary>

```ts
setupDirect() {

		const lightColor = this.colorNode;
		const lightDirection = lightTargetDirection( this.light );

		return { lightDirection, lightColor };

	}
```
</details>


---