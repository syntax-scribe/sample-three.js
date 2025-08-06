[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `Lut3DNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/Lut3DNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `three/webgpu` |
| `nodeObject` | `three/tsl` |
| `Fn` | `three/tsl` |
| `float` | `three/tsl` |
| `uniform` | `three/tsl` |
| `vec3` | `three/tsl` |
| `vec4` | `three/tsl` |
| `mix` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `base` | `Node` | let/var | `inputNode` | ✗ |


---

## Functions

### `Lut3DNode.setup(): ShaderCallNodeInternal`

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

- `lutNode.sample`
- `Fn (from three/tsl)`
- `float( 1.0 ).div`
- `float( 0.5 ).div`
- `vec3( halfPixelWidth ).add`
- `base.rgb.mul`
- `float( 1.0 ).sub`
- `vec4 (from three/tsl)`
- `sampleLut`
- `mix (from three/tsl)`
- `lut3D`

**Internal Comments:**
```
// pull the sample in by half a pixel so the sample begins at the center of the edge pixels. (x2)
```

<details><summary>Code</summary>

```typescript
setup() {

		const { inputNode, lutNode } = this;

		const sampleLut = ( uv ) => lutNode.sample( uv );

		const lut3D = Fn( () => {

			const base = inputNode;

			// pull the sample in by half a pixel so the sample begins at the center of the edge pixels.

			const pixelWidth = float( 1.0 ).div( this.size );
			const halfPixelWidth = float( 0.5 ).div( this.size );
			const uvw = vec3( halfPixelWidth ).add( base.rgb.mul( float( 1.0 ).sub( pixelWidth ) ) );

			const lutValue = vec4( sampleLut( uvw ).rgb, base.a );

			return vec4( mix( base, lutValue, this.intensityNode ) );

		} );

		const outputNode = lut3D();

		return outputNode;

	}
```
</details>

### `sampleLut(uv: any): any`

**Parameters:**

- **`uv`** `any`

**Returns:** `any`

**Calls:**

- `lutNode.sample`

<details><summary>Code</summary>

```typescript
( uv ) => lutNode.sample( uv )
```
</details>

### `lut3D(node: Node, lut: TextureNode, size: number, intensity: any): Lut3DNode`

**Parameters:**

- **`node`** `Node`
- **`lut`** `TextureNode`
- **`size`** `number`
- **`intensity`** `any`

**Returns:** `Lut3DNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( node, lut, size, intensity ) => nodeObject( new Lut3DNode( nodeObject( node ), nodeObject( lut ), size, nodeObject( intensity ) ) )
```
</details>


---

## Classes

### `Lut3DNode`

<details><summary>Class Code</summary>

```ts
class Lut3DNode extends TempNode {

	static get type() {

		return 'Lut3DNode';

	}

	/**
	 * Constructs a new LUT node.
	 *
	 * @param {Node} inputNode - The node that represents the input of the effect.
	 * @param {TextureNode} lutNode - A texture node that represents the lookup table.
	 * @param {number} size - The size of the lookup table.
	 * @param {Node<float>} intensityNode - Controls the intensity of the effect.
	 */
	constructor( inputNode, lutNode, size, intensityNode ) {

		super( 'vec4' );

		/**
		 * The node that represents the input of the effect.
		 *
		 * @type {Node}
		 */
		this.inputNode = inputNode;

		/**
		 * A texture node that represents the lookup table.
		 *
		 * @type {TextureNode}
		 */
		this.lutNode = lutNode;

		/**
		 * The size of the lookup table.
		 *
		 * @type {UniformNode<float>}
		 */
		this.size = uniform( size );

		/**
		 * Controls the intensity of the effect.
		 *
		 * @type {Node<float>}
		 */
		this.intensityNode = intensityNode;

	}

	/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {ShaderCallNodeInternal}
	 */
	setup() {

		const { inputNode, lutNode } = this;

		const sampleLut = ( uv ) => lutNode.sample( uv );

		const lut3D = Fn( () => {

			const base = inputNode;

			// pull the sample in by half a pixel so the sample begins at the center of the edge pixels.

			const pixelWidth = float( 1.0 ).div( this.size );
			const halfPixelWidth = float( 0.5 ).div( this.size );
			const uvw = vec3( halfPixelWidth ).add( base.rgb.mul( float( 1.0 ).sub( pixelWidth ) ) );

			const lutValue = vec4( sampleLut( uvw ).rgb, base.a );

			return vec4( mix( base, lutValue, this.intensityNode ) );

		} );

		const outputNode = lut3D();

		return outputNode;

	}

}
```
</details>

#### Methods

##### `setup(): ShaderCallNodeInternal`

<details><summary>Code</summary>

```ts
setup() {

		const { inputNode, lutNode } = this;

		const sampleLut = ( uv ) => lutNode.sample( uv );

		const lut3D = Fn( () => {

			const base = inputNode;

			// pull the sample in by half a pixel so the sample begins at the center of the edge pixels.

			const pixelWidth = float( 1.0 ).div( this.size );
			const halfPixelWidth = float( 0.5 ).div( this.size );
			const uvw = vec3( halfPixelWidth ).add( base.rgb.mul( float( 1.0 ).sub( pixelWidth ) ) );

			const lutValue = vec4( sampleLut( uvw ).rgb, base.a );

			return vec4( mix( base, lutValue, this.intensityNode ) );

		} );

		const outputNode = lut3D();

		return outputNode;

	}
```
</details>


---