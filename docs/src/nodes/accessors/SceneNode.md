[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SceneNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 6 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/SceneNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `UVMapping` | `../../constants.js` |
| `Euler` | `../../math/Euler.js` |
| `Matrix4` | `../../math/Matrix4.js` |
| `Node` | `../core/Node.js` |
| `renderGroup` | `../core/UniformGroupNode.js` |
| `nodeImmutable` | `../tsl/TSLBase.js` |
| `uniform` | `../tsl/TSLBase.js` |
| `reference` | `./ReferenceNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_e1` | `Euler` | let/var | `new Euler()` | ✗ |
| `_m1` | `Matrix4` | let/var | `new Matrix4()` | ✗ |
| `scope` | `"backgroundBlurriness" \| "background...` | let/var | `this.scope` | ✗ |
| `scene` | `any` | let/var | `this.scene !== null ? this.scene : builder.scene` | ✗ |
| `output` | `any` | let/var | `*not shown*` | ✗ |
| `background` | `any` | let/var | `scene.background` | ✗ |


---

## Functions

### `SceneNode.setup(builder: NodeBuilder): Node`

**JSDoc:**
```typescript
/**
	 * Depending on the scope, the method returns a different type of node that represents
	 * the respective scene property.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Node} The output node.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `Node`

**Calls:**

- `reference (from ./ReferenceNode.js)`
- `uniform( 'mat4' ).setName( 'backgroundRotation' ).setGroup( renderGroup ).onRenderUpdate`
- `_e1.copy`
- `_m1.makeRotationFromEuler`
- `_m1.identity`
- `console.error`

**Internal Comments:**
```
// accommodate left-handed frame (x4)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const scope = this.scope;
		const scene = this.scene !== null ? this.scene : builder.scene;

		let output;

		if ( scope === SceneNode.BACKGROUND_BLURRINESS ) {

			output = reference( 'backgroundBlurriness', 'float', scene );

		} else if ( scope === SceneNode.BACKGROUND_INTENSITY ) {

			output = reference( 'backgroundIntensity', 'float', scene );

		} else if ( scope === SceneNode.BACKGROUND_ROTATION ) {

			output = uniform( 'mat4' ).setName( 'backgroundRotation' ).setGroup( renderGroup ).onRenderUpdate( () => {

				const background = scene.background;

				if ( background !== null && background.isTexture && background.mapping !== UVMapping ) {

					_e1.copy( scene.backgroundRotation );

					// accommodate left-handed frame
					_e1.x *= - 1; _e1.y *= - 1; _e1.z *= - 1;

					_m1.makeRotationFromEuler( _e1 );

				} else {

					_m1.identity();

				}

				return _m1;

			} );

		} else {

			console.error( 'THREE.SceneNode: Unknown scope:', scope );

		}

		return output;

	}
```
</details>


---

## Classes

### `SceneNode`

<details><summary>Class Code</summary>

```ts
class SceneNode extends Node {

	static get type() {

		return 'SceneNode';

	}

	/**
	 * Constructs a new scene node.
	 *
	 * @param {('backgroundBlurriness'|'backgroundIntensity'|'backgroundRotation')} scope - The scope defines the type of scene property that is accessed.
	 * @param {?Scene} [scene=null] - A reference to the scene.
	 */
	constructor( scope = SceneNode.BACKGROUND_BLURRINESS, scene = null ) {

		super();

		/**
		 * The scope defines the type of scene property that is accessed.
		 *
		 * @type {('backgroundBlurriness'|'backgroundIntensity'|'backgroundRotation')}
		 */
		this.scope = scope;

		/**
		 * A reference to the scene that is going to be accessed.
		 *
		 * @type {?Scene}
		 * @default null
		 */
		this.scene = scene;

	}

	/**
	 * Depending on the scope, the method returns a different type of node that represents
	 * the respective scene property.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Node} The output node.
	 */
	setup( builder ) {

		const scope = this.scope;
		const scene = this.scene !== null ? this.scene : builder.scene;

		let output;

		if ( scope === SceneNode.BACKGROUND_BLURRINESS ) {

			output = reference( 'backgroundBlurriness', 'float', scene );

		} else if ( scope === SceneNode.BACKGROUND_INTENSITY ) {

			output = reference( 'backgroundIntensity', 'float', scene );

		} else if ( scope === SceneNode.BACKGROUND_ROTATION ) {

			output = uniform( 'mat4' ).setName( 'backgroundRotation' ).setGroup( renderGroup ).onRenderUpdate( () => {

				const background = scene.background;

				if ( background !== null && background.isTexture && background.mapping !== UVMapping ) {

					_e1.copy( scene.backgroundRotation );

					// accommodate left-handed frame
					_e1.x *= - 1; _e1.y *= - 1; _e1.z *= - 1;

					_m1.makeRotationFromEuler( _e1 );

				} else {

					_m1.identity();

				}

				return _m1;

			} );

		} else {

			console.error( 'THREE.SceneNode: Unknown scope:', scope );

		}

		return output;

	}

}
```
</details>

#### Methods

##### `setup(builder: NodeBuilder): Node`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const scope = this.scope;
		const scene = this.scene !== null ? this.scene : builder.scene;

		let output;

		if ( scope === SceneNode.BACKGROUND_BLURRINESS ) {

			output = reference( 'backgroundBlurriness', 'float', scene );

		} else if ( scope === SceneNode.BACKGROUND_INTENSITY ) {

			output = reference( 'backgroundIntensity', 'float', scene );

		} else if ( scope === SceneNode.BACKGROUND_ROTATION ) {

			output = uniform( 'mat4' ).setName( 'backgroundRotation' ).setGroup( renderGroup ).onRenderUpdate( () => {

				const background = scene.background;

				if ( background !== null && background.isTexture && background.mapping !== UVMapping ) {

					_e1.copy( scene.backgroundRotation );

					// accommodate left-handed frame
					_e1.x *= - 1; _e1.y *= - 1; _e1.z *= - 1;

					_m1.makeRotationFromEuler( _e1 );

				} else {

					_m1.identity();

				}

				return _m1;

			} );

		} else {

			console.error( 'THREE.SceneNode: Unknown scope:', scope );

		}

		return output;

	}
```
</details>


---