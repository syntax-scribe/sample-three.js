[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Lighting.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/Lighting.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LightsNode` | `../../nodes/Nodes.js` |
| `ChainMap` | `./ChainMap.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_defaultLights` | `LightsNode` | let/var | `new LightsNode()` | ✗ |
| `_chainKeys` | `any[]` | let/var | `[]` | ✗ |


---

## Functions

### `Lighting.createNode(lights: Light[]): LightsNode`

**JSDoc:**
```typescript
/**
	 * Creates a new lights node for the given array of lights.
	 *
	 * @param {Array<Light>} lights - The render object.
	 * @return {LightsNode} The lights node.
	 */
```

**Parameters:**

- **`lights`** `Light[]`

**Returns:** `LightsNode`

**Calls:**

- `new LightsNode().setLights`

<details><summary>Code</summary>

```typescript
createNode( lights = [] ) {

		return new LightsNode().setLights( lights );

	}
```
</details>

### `Lighting.getNode(scene: Scene, camera: Camera): LightsNode`

**JSDoc:**
```typescript
/**
	 * Returns a lights node for the given scene and camera.
	 *
	 * @param {Scene} scene - The scene.
	 * @param {Camera} camera - The camera.
	 * @return {LightsNode} The lights node.
	 */
```

**Parameters:**

- **`scene`** `Scene`
- **`camera`** `Camera`

**Returns:** `LightsNode`

**Calls:**

- `this.get`
- `this.createNode`
- `this.set`

**Internal Comments:**
```
// ignore post-processing
```

<details><summary>Code</summary>

```typescript
getNode( scene, camera ) {

		// ignore post-processing

		if ( scene.isQuadMesh ) return _defaultLights;

		_chainKeys[ 0 ] = scene;
		_chainKeys[ 1 ] = camera;

		let node = this.get( _chainKeys );

		if ( node === undefined ) {

			node = this.createNode();
			this.set( _chainKeys, node );

		}

		_chainKeys.length = 0;

		return node;

	}
```
</details>


---

## Classes

### `Lighting`

<details><summary>Class Code</summary>

```ts
class Lighting extends ChainMap {

	/**
	 * Constructs a lighting management component.
	 */
	constructor() {

		super();

	}

	/**
	 * Creates a new lights node for the given array of lights.
	 *
	 * @param {Array<Light>} lights - The render object.
	 * @return {LightsNode} The lights node.
	 */
	createNode( lights = [] ) {

		return new LightsNode().setLights( lights );

	}

	/**
	 * Returns a lights node for the given scene and camera.
	 *
	 * @param {Scene} scene - The scene.
	 * @param {Camera} camera - The camera.
	 * @return {LightsNode} The lights node.
	 */
	getNode( scene, camera ) {

		// ignore post-processing

		if ( scene.isQuadMesh ) return _defaultLights;

		_chainKeys[ 0 ] = scene;
		_chainKeys[ 1 ] = camera;

		let node = this.get( _chainKeys );

		if ( node === undefined ) {

			node = this.createNode();
			this.set( _chainKeys, node );

		}

		_chainKeys.length = 0;

		return node;

	}

}
```
</details>

#### Methods

##### `createNode(lights: Light[]): LightsNode`

<details><summary>Code</summary>

```ts
createNode( lights = [] ) {

		return new LightsNode().setLights( lights );

	}
```
</details>

##### `getNode(scene: Scene, camera: Camera): LightsNode`

<details><summary>Code</summary>

```ts
getNode( scene, camera ) {

		// ignore post-processing

		if ( scene.isQuadMesh ) return _defaultLights;

		_chainKeys[ 0 ] = scene;
		_chainKeys[ 1 ] = camera;

		let node = this.get( _chainKeys );

		if ( node === undefined ) {

			node = this.createNode();
			this.set( _chainKeys, node );

		}

		_chainKeys.length = 0;

		return node;

	}
```
</details>


---