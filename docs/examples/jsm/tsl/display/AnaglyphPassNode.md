[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `AnaglyphPassNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/AnaglyphPassNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Matrix3` | `three/webgpu` |
| `NodeMaterial` | `three/webgpu` |
| `clamp` | `three/tsl` |
| `nodeObject` | `three/tsl` |
| `Fn` | `three/tsl` |
| `vec4` | `three/tsl` |
| `uv` | `three/tsl` |
| `uniform` | `three/tsl` |
| `max` | `three/tsl` |
| `StereoCompositePassNode` | `./StereoCompositePassNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `material` | `any` | let/var | `this._material \|\| ( this._material = new NodeMaterial() )` | ✗ |


---

## Functions

### `AnaglyphPassNode.setup(builder: NodeBuilder): PassTextureNode`

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
- `this._mapLeft.sample`
- `this._mapRight.sample`
- `clamp (from three/tsl)`
- `this._colorMatrixLeft.mul( colorL.rgb ).add`
- `this._colorMatrixRight.mul`
- `vec4 (from three/tsl)`
- `max (from three/tsl)`
- `anaglyph().context`
- `builder.getSharedContext`
- `super.setup`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const uvNode = uv();

		const anaglyph = Fn( () => {

			const colorL = this._mapLeft.sample( uvNode );
			const colorR = this._mapRight.sample( uvNode );

			const color = clamp( this._colorMatrixLeft.mul( colorL.rgb ).add( this._colorMatrixRight.mul( colorR.rgb ) ) );

			return vec4( color.rgb, max( colorL.a, colorR.a ) );

		} );

		const material = this._material || ( this._material = new NodeMaterial() );
		material.fragmentNode = anaglyph().context( builder.getSharedContext() );
		material.name = 'Anaglyph';
		material.needsUpdate = true;

		return super.setup( builder );

	}
```
</details>

### `anaglyphPass(scene: Scene, camera: Camera): AnaglyphPassNode`

**Parameters:**

- **`scene`** `Scene`
- **`camera`** `Camera`

**Returns:** `AnaglyphPassNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( scene, camera ) => nodeObject( new AnaglyphPassNode( scene, camera ) )
```
</details>


---

## Classes

### `AnaglyphPassNode`

<details><summary>Class Code</summary>

```ts
class AnaglyphPassNode extends StereoCompositePassNode {

	static get type() {

		return 'AnaglyphPassNode';

	}

	/**
	 * Constructs a new anaglyph pass node.
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
		this.isAnaglyphPassNode = true;

		// Dubois matrices from https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.7.6968&rep=rep1&type=pdf#page=4

		/**
		 * Color matrix node for the left eye.
		 *
		 * @type {UniformNode<mat3>}
		 */
		this._colorMatrixLeft = uniform( new Matrix3().fromArray( [
			0.456100, - 0.0400822, - 0.0152161,
			0.500484, - 0.0378246, - 0.0205971,
			0.176381, - 0.0157589, - 0.00546856
		] ) );

		/**
		 * Color matrix node for the right eye.
		 *
		 * @type {UniformNode<mat3>}
		 */
		this._colorMatrixRight = uniform( new Matrix3().fromArray( [
			- 0.0434706, 0.378476, - 0.0721527,
			- 0.0879388, 0.73364, - 0.112961,
			- 0.00155529, - 0.0184503, 1.2264
		] ) );

	}

	/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {PassTextureNode}
	 */
	setup( builder ) {

		const uvNode = uv();

		const anaglyph = Fn( () => {

			const colorL = this._mapLeft.sample( uvNode );
			const colorR = this._mapRight.sample( uvNode );

			const color = clamp( this._colorMatrixLeft.mul( colorL.rgb ).add( this._colorMatrixRight.mul( colorR.rgb ) ) );

			return vec4( color.rgb, max( colorL.a, colorR.a ) );

		} );

		const material = this._material || ( this._material = new NodeMaterial() );
		material.fragmentNode = anaglyph().context( builder.getSharedContext() );
		material.name = 'Anaglyph';
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

		const anaglyph = Fn( () => {

			const colorL = this._mapLeft.sample( uvNode );
			const colorR = this._mapRight.sample( uvNode );

			const color = clamp( this._colorMatrixLeft.mul( colorL.rgb ).add( this._colorMatrixRight.mul( colorR.rgb ) ) );

			return vec4( color.rgb, max( colorL.a, colorR.a ) );

		} );

		const material = this._material || ( this._material = new NodeMaterial() );
		material.fragmentNode = anaglyph().context( builder.getSharedContext() );
		material.name = 'Anaglyph';
		material.needsUpdate = true;

		return super.setup( builder );

	}
```
</details>


---