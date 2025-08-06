[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `RGBShiftNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/RGBShiftNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `three/webgpu` |
| `nodeObject` | `three/tsl` |
| `Fn` | `three/tsl` |
| `uv` | `three/tsl` |
| `uniform` | `three/tsl` |
| `vec2` | `three/tsl` |
| `sin` | `three/tsl` |
| `cos` | `three/tsl` |
| `vec4` | `three/tsl` |
| `convertToTexture` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `uvNode` | `any` | let/var | `textureNode.uvNode \|\| uv()` | ✗ |


---

## Functions

### `RGBShiftNode.setup(): ShaderCallNodeInternal`

**JSDoc:**
```typescript
/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {ShaderCallNodeInternal}
	 */
```

**Returns:** `ShaderCallNodeInternal`

**Calls:**

- `uv (from three/tsl)`
- `textureNode.sample`
- `Fn (from three/tsl)`
- `vec2( cos( this.angle ), sin( this.angle ) ).mul`
- `sampleTexture`
- `uvNode.add`
- `uvNode.sub`
- `vec4 (from three/tsl)`
- `rgbShift`

<details><summary>Code</summary>

```typescript
setup( /* builder */ ) {

		const { textureNode } = this;

		const uvNode = textureNode.uvNode || uv();

		const sampleTexture = ( uv ) => textureNode.sample( uv );

		const rgbShift = Fn( () => {

			const offset = vec2( cos( this.angle ), sin( this.angle ) ).mul( this.amount );
			const cr = sampleTexture( uvNode.add( offset ) );
			const cga = sampleTexture( uvNode );
			const cb = sampleTexture( uvNode.sub( offset ) );

			return vec4( cr.r, cga.g, cb.b, cga.a );

		} );

		return rgbShift();

	}
```
</details>

### `sampleTexture(uv: any): any`

**Parameters:**

- **`uv`** `any`

**Returns:** `any`

**Calls:**

- `textureNode.sample`

<details><summary>Code</summary>

```typescript
( uv ) => textureNode.sample( uv )
```
</details>

### `rgbShift(node: any, amount: number, angle: number): RGBShiftNode`

**Parameters:**

- **`node`** `any`
- **`amount`** `number`
- **`angle`** `number`

**Returns:** `RGBShiftNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( node, amount, angle ) => nodeObject( new RGBShiftNode( convertToTexture( node ), amount, angle ) )
```
</details>


---

## Classes

### `RGBShiftNode`

<details><summary>Class Code</summary>

```ts
class RGBShiftNode extends TempNode {

	static get type() {

		return 'RGBShiftNode';

	}

	/**
	 * Constructs a new RGB shift node.
	 *
	 * @param {TextureNode} textureNode - The texture node that represents the input of the effect.
	 * @param {number} [amount=0.005] - The amount of the RGB shift.
	 * @param {number} [angle=0] - Defines the orientation in which colors are shifted.
	 */
	constructor( textureNode, amount = 0.005, angle = 0 ) {

		super( 'vec4' );

		/**
		 * The texture node that represents the input of the effect.
		 *
		 * @type {TextureNode}
		 */
		this.textureNode = textureNode;

		/**
		 * The amount of the RGB shift.
		 *
		 * @type {UniformNode<float>}
		 */
		this.amount = uniform( amount );

		/**
		 * Defines in which direction colors are shifted.
		 *
		 * @type {UniformNode<float>}
		 */
		this.angle = uniform( angle );

	}

	/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {ShaderCallNodeInternal}
	 */
	setup( /* builder */ ) {

		const { textureNode } = this;

		const uvNode = textureNode.uvNode || uv();

		const sampleTexture = ( uv ) => textureNode.sample( uv );

		const rgbShift = Fn( () => {

			const offset = vec2( cos( this.angle ), sin( this.angle ) ).mul( this.amount );
			const cr = sampleTexture( uvNode.add( offset ) );
			const cga = sampleTexture( uvNode );
			const cb = sampleTexture( uvNode.sub( offset ) );

			return vec4( cr.r, cga.g, cb.b, cga.a );

		} );

		return rgbShift();

	}

}
```
</details>

#### Methods

##### `setup(): ShaderCallNodeInternal`

<details><summary>Code</summary>

```ts
setup( /* builder */ ) {

		const { textureNode } = this;

		const uvNode = textureNode.uvNode || uv();

		const sampleTexture = ( uv ) => textureNode.sample( uv );

		const rgbShift = Fn( () => {

			const offset = vec2( cos( this.angle ), sin( this.angle ) ).mul( this.amount );
			const cr = sampleTexture( uvNode.add( offset ) );
			const cga = sampleTexture( uvNode );
			const cb = sampleTexture( uvNode.sub( offset ) );

			return vec4( cr.r, cga.g, cb.b, cga.a );

		} );

		return rgbShift();

	}
```
</details>


---