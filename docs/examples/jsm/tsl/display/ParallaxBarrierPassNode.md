[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `ParallaxBarrierPassNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/ParallaxBarrierPassNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeMaterial` | `three/webgpu` |
| `nodeObject` | `three/tsl` |
| `Fn` | `three/tsl` |
| `vec4` | `three/tsl` |
| `uv` | `three/tsl` |
| `If` | `three/tsl` |
| `mod` | `three/tsl` |
| `screenCoordinate` | `three/tsl` |
| `StereoCompositePassNode` | `./StereoCompositePassNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `material` | `any` | let/var | `this._material \|\| ( this._material = new NodeMaterial() )` | ✗ |


---

## Functions

### `ParallaxBarrierPassNode.setup(builder: NodeBuilder): PassTextureNode`

**JSDoc:**
```typescript
/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {PassTextureNode}
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `PassTextureNode`

**Calls:**

- `uv (from three/tsl)`
- `Fn (from three/tsl)`
- `vec4().toVar`
- `If( mod( screenCoordinate.y, 2 ).greaterThan( 1 ), () => {

				color.assign( this._mapLeft.sample( uvNode ) );

			} ).Else`
- `color.assign`
- `this._mapRight.sample`
- `parallaxBarrier().context`
- `builder.getSharedContext`
- `super.setup`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const uvNode = uv();

		const parallaxBarrier = Fn( () => {

			const color = vec4().toVar();

			If( mod( screenCoordinate.y, 2 ).greaterThan( 1 ), () => {

				color.assign( this._mapLeft.sample( uvNode ) );

			} ).Else( () => {

				color.assign( this._mapRight.sample( uvNode ) );

			} );

			return color;

		} );

		const material = this._material || ( this._material = new NodeMaterial() );
		material.fragmentNode = parallaxBarrier().context( builder.getSharedContext() );
		material.needsUpdate = true;

		return super.setup( builder );

	}
```
</details>

### `parallaxBarrierPass(scene: Scene, camera: Camera): ParallaxBarrierPassNode`

**Parameters:**

- **`scene`** `Scene`
- **`camera`** `Camera`

**Returns:** `ParallaxBarrierPassNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( scene, camera ) => nodeObject( new ParallaxBarrierPassNode( scene, camera ) )
```
</details>


---

## Classes

### `ParallaxBarrierPassNode`

<details><summary>Class Code</summary>

```ts
class ParallaxBarrierPassNode extends StereoCompositePassNode {

	static get type() {

		return 'ParallaxBarrierPassNode';

	}

	/**
	 * Constructs a new parallax barrier pass node.
	 *
	 * @param {Scene} scene - The scene to render.
	 * @param {Camera} camera - The camera to render the scene with.
	 */
	constructor( scene, camera ) {

		super( scene, camera );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isParallaxBarrierPassNode = true;

	}

	/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {PassTextureNode}
	 */
	setup( builder ) {

		const uvNode = uv();

		const parallaxBarrier = Fn( () => {

			const color = vec4().toVar();

			If( mod( screenCoordinate.y, 2 ).greaterThan( 1 ), () => {

				color.assign( this._mapLeft.sample( uvNode ) );

			} ).Else( () => {

				color.assign( this._mapRight.sample( uvNode ) );

			} );

			return color;

		} );

		const material = this._material || ( this._material = new NodeMaterial() );
		material.fragmentNode = parallaxBarrier().context( builder.getSharedContext() );
		material.needsUpdate = true;

		return super.setup( builder );

	}

}
```
</details>

#### Methods

##### `setup(builder: NodeBuilder): PassTextureNode`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const uvNode = uv();

		const parallaxBarrier = Fn( () => {

			const color = vec4().toVar();

			If( mod( screenCoordinate.y, 2 ).greaterThan( 1 ), () => {

				color.assign( this._mapLeft.sample( uvNode ) );

			} ).Else( () => {

				color.assign( this._mapRight.sample( uvNode ) );

			} );

			return color;

		} );

		const material = this._material || ( this._material = new NodeMaterial() );
		material.fragmentNode = parallaxBarrier().context( builder.getSharedContext() );
		material.needsUpdate = true;

		return super.setup( builder );

	}
```
</details>


---