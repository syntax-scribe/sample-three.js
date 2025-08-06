[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TiledLighting.js`

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
📂 **`examples/jsm/lighting/TiledLighting.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Lighting` | `three/webgpu` |
| `tiledLights` | `../tsl/lighting/TiledLightsNode.js` |


---

## Functions

### `TiledLighting.createNode(lights: Light[]): TiledLightsNode`

**JSDoc:**
```typescript
/**
	 * Creates a new tiled lights node for the given array of lights.
	 *
	 * This method is called internally by the renderer and must be overwritten by
	 * all custom lighting implementations.
	 *
	 * @param {Array<Light>} lights - The render object.
	 * @return {TiledLightsNode} The tiled lights node.
	 */
```

**Parameters:**

- **`lights`** `Light[]`

**Returns:** `TiledLightsNode`

**Calls:**

- `tiledLights().setLights`

<details><summary>Code</summary>

```typescript
createNode( lights = [] ) {

		return tiledLights().setLights( lights );

	}
```
</details>


---

## Classes

### `TiledLighting`

<details><summary>Class Code</summary>

```ts
export class TiledLighting extends Lighting {

	/**
	 * Constructs a new lighting system.
	 */
	constructor() {

		super();

	}

	/**
	 * Creates a new tiled lights node for the given array of lights.
	 *
	 * This method is called internally by the renderer and must be overwritten by
	 * all custom lighting implementations.
	 *
	 * @param {Array<Light>} lights - The render object.
	 * @return {TiledLightsNode} The tiled lights node.
	 */
	createNode( lights = [] ) {

		return tiledLights().setLights( lights );

	}

}
```
</details>

#### Methods

##### `createNode(lights: Light[]): TiledLightsNode`

<details><summary>Code</summary>

```ts
createNode( lights = [] ) {

		return tiledLights().setLights( lights );

	}
```
</details>


---