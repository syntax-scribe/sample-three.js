[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `SobelOperatorNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 14 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/SobelOperatorNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector2` | `three/webgpu` |
| `TempNode` | `three/webgpu` |
| `NodeUpdateType` | `three/webgpu` |
| `nodeObject` | `three/tsl` |
| `Fn` | `three/tsl` |
| `uv` | `three/tsl` |
| `uniform` | `three/tsl` |
| `convertToTexture` | `three/tsl` |
| `vec2` | `three/tsl` |
| `vec3` | `three/tsl` |
| `vec4` | `three/tsl` |
| `mat3` | `three/tsl` |
| `luminance` | `three/tsl` |
| `add` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `map` | `any` | let/var | `this.textureNode.value` | ✗ |
| `uvNode` | `any` | let/var | `textureNode.uvNode \|\| uv()` | ✗ |
| `texel` | `UniformNode<vec2>` | let/var | `this._invSize` | ✗ |


---

## Functions

### `SobelOperatorNode.updateBefore(): void`

**JSDoc:**
```typescript
/**
	 * This method is used to update the effect's uniforms once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
```

**Returns:** `void`

**Calls:**

- `this._invSize.value.set`

<details><summary>Code</summary>

```typescript
updateBefore( /* frame */ ) {

		const map = this.textureNode.value;

		this._invSize.value.set( 1 / map.image.width, 1 / map.image.height );

	}
```
</details>

### `SobelOperatorNode.setup(): ShaderCallNodeInternal`

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
- `mat3 (from three/tsl)`
- `luminance (from three/tsl)`
- `sampleTexture`
- `uvNode.add`
- `texel.mul`
- `vec2 (from three/tsl)`
- `add (from three/tsl)`
- `Gx[ 0 ][ 0 ].mul`
- `Gx[ 1 ][ 0 ].mul`
- `Gx[ 2 ][ 0 ].mul`
- `Gx[ 0 ][ 1 ].mul`
- `Gx[ 1 ][ 1 ].mul`
- `Gx[ 2 ][ 1 ].mul`
- `Gx[ 0 ][ 2 ].mul`
- `Gx[ 1 ][ 2 ].mul`
- `Gx[ 2 ][ 2 ].mul`
- `Gy[ 0 ][ 0 ].mul`
- `Gy[ 1 ][ 0 ].mul`
- `Gy[ 2 ][ 0 ].mul`
- `Gy[ 0 ][ 1 ].mul`
- `Gy[ 1 ][ 1 ].mul`
- `Gy[ 2 ][ 1 ].mul`
- `Gy[ 0 ][ 2 ].mul`
- `Gy[ 1 ][ 2 ].mul`
- `Gy[ 2 ][ 2 ].mul`
- `valueGx.mul( valueGx ).add( valueGy.mul( valueGy ) ).sqrt`
- `vec4 (from three/tsl)`
- `vec3 (from three/tsl)`
- `sobel`

**Internal Comments:**
```
// Sobel Edge Detection (see https://youtu.be/uihBwtPIBxM) (x2)
// kernel definition (in glsl matrices are filled in column-major order) (x2)
// fetch the 3x3 neighbourhood of a fragment (x2)
// first column (x2)
// second column (x2)
// third column (x2)
// gradient value in x direction (x2)
// gradient value in y direction (x2)
// magnitude of the total gradient (x2)
```

<details><summary>Code</summary>

```typescript
setup( /* builder */ ) {

		const { textureNode } = this;

		const uvNode = textureNode.uvNode || uv();

		const sampleTexture = ( uv ) => textureNode.sample( uv );

		const sobel = Fn( () => {

			// Sobel Edge Detection (see https://youtu.be/uihBwtPIBxM)

			const texel = this._invSize;

			// kernel definition (in glsl matrices are filled in column-major order)

			const Gx = mat3( - 1, - 2, - 1, 0, 0, 0, 1, 2, 1 ); // x direction kernel
			const Gy = mat3( - 1, 0, 1, - 2, 0, 2, - 1, 0, 1 ); // y direction kernel

			// fetch the 3x3 neighbourhood of a fragment

			// first column

			const tx0y0 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( - 1, - 1 ) ) ) ).xyz );
			const tx0y1 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( - 1, 0 ) ) ) ).xyz );
			const tx0y2 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( - 1, 1 ) ) ) ).xyz );

			// second column

			const tx1y0 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 0, - 1 ) ) ) ).xyz );
			const tx1y1 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 0, 0 ) ) ) ).xyz );
			const tx1y2 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 0, 1 ) ) ) ).xyz );

			// third column

			const tx2y0 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 1, - 1 ) ) ) ).xyz );
			const tx2y1 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 1, 0 ) ) ) ).xyz );
			const tx2y2 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 1, 1 ) ) ) ).xyz );

			// gradient value in x direction

			const valueGx = add(
				Gx[ 0 ][ 0 ].mul( tx0y0 ),
				Gx[ 1 ][ 0 ].mul( tx1y0 ),
				Gx[ 2 ][ 0 ].mul( tx2y0 ),
				Gx[ 0 ][ 1 ].mul( tx0y1 ),
				Gx[ 1 ][ 1 ].mul( tx1y1 ),
				Gx[ 2 ][ 1 ].mul( tx2y1 ),
				Gx[ 0 ][ 2 ].mul( tx0y2 ),
				Gx[ 1 ][ 2 ].mul( tx1y2 ),
				Gx[ 2 ][ 2 ].mul( tx2y2 )
			);


			// gradient value in y direction

			const valueGy = add(
				Gy[ 0 ][ 0 ].mul( tx0y0 ),
				Gy[ 1 ][ 0 ].mul( tx1y0 ),
				Gy[ 2 ][ 0 ].mul( tx2y0 ),
				Gy[ 0 ][ 1 ].mul( tx0y1 ),
				Gy[ 1 ][ 1 ].mul( tx1y1 ),
				Gy[ 2 ][ 1 ].mul( tx2y1 ),
				Gy[ 0 ][ 2 ].mul( tx0y2 ),
				Gy[ 1 ][ 2 ].mul( tx1y2 ),
				Gy[ 2 ][ 2 ].mul( tx2y2 )
			);

			// magnitude of the total gradient

			const G = valueGx.mul( valueGx ).add( valueGy.mul( valueGy ) ).sqrt();

			return vec4( vec3( G ), 1 );

		} );

		const outputNode = sobel();

		return outputNode;

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

### `sobel(node: any): SobelOperatorNode`

**Parameters:**

- **`node`** `any`

**Returns:** `SobelOperatorNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( node ) => nodeObject( new SobelOperatorNode( convertToTexture( node ) ) )
```
</details>


---

## Classes

### `SobelOperatorNode`

<details><summary>Class Code</summary>

```ts
class SobelOperatorNode extends TempNode {

	static get type() {

		return 'SobelOperatorNode';

	}

	/**
	 * Constructs a new sobel operator node.
	 *
	 * @param {TextureNode} textureNode - The texture node that represents the input of the effect.
	 */
	constructor( textureNode ) {

		super( 'vec4' );

		/**
		 * The texture node that represents the input of the effect.
		 *
		 * @type {TextureNode}
		 */
		this.textureNode = textureNode;

		/**
		 * The `updateBeforeType` is set to `NodeUpdateType.FRAME` since the node updates
		 * its internal uniforms once per frame in `updateBefore()`.
		 *
		 * @type {string}
		 * @default 'frame'
		 */
		this.updateBeforeType = NodeUpdateType.FRAME;

		/**
		 * A uniform node holding the inverse resolution value.
		 *
		 * @private
		 * @type {UniformNode<vec2>}
		 */
		this._invSize = uniform( new Vector2() );

	}

	/**
	 * This method is used to update the effect's uniforms once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
	updateBefore( /* frame */ ) {

		const map = this.textureNode.value;

		this._invSize.value.set( 1 / map.image.width, 1 / map.image.height );

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

		const sobel = Fn( () => {

			// Sobel Edge Detection (see https://youtu.be/uihBwtPIBxM)

			const texel = this._invSize;

			// kernel definition (in glsl matrices are filled in column-major order)

			const Gx = mat3( - 1, - 2, - 1, 0, 0, 0, 1, 2, 1 ); // x direction kernel
			const Gy = mat3( - 1, 0, 1, - 2, 0, 2, - 1, 0, 1 ); // y direction kernel

			// fetch the 3x3 neighbourhood of a fragment

			// first column

			const tx0y0 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( - 1, - 1 ) ) ) ).xyz );
			const tx0y1 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( - 1, 0 ) ) ) ).xyz );
			const tx0y2 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( - 1, 1 ) ) ) ).xyz );

			// second column

			const tx1y0 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 0, - 1 ) ) ) ).xyz );
			const tx1y1 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 0, 0 ) ) ) ).xyz );
			const tx1y2 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 0, 1 ) ) ) ).xyz );

			// third column

			const tx2y0 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 1, - 1 ) ) ) ).xyz );
			const tx2y1 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 1, 0 ) ) ) ).xyz );
			const tx2y2 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 1, 1 ) ) ) ).xyz );

			// gradient value in x direction

			const valueGx = add(
				Gx[ 0 ][ 0 ].mul( tx0y0 ),
				Gx[ 1 ][ 0 ].mul( tx1y0 ),
				Gx[ 2 ][ 0 ].mul( tx2y0 ),
				Gx[ 0 ][ 1 ].mul( tx0y1 ),
				Gx[ 1 ][ 1 ].mul( tx1y1 ),
				Gx[ 2 ][ 1 ].mul( tx2y1 ),
				Gx[ 0 ][ 2 ].mul( tx0y2 ),
				Gx[ 1 ][ 2 ].mul( tx1y2 ),
				Gx[ 2 ][ 2 ].mul( tx2y2 )
			);


			// gradient value in y direction

			const valueGy = add(
				Gy[ 0 ][ 0 ].mul( tx0y0 ),
				Gy[ 1 ][ 0 ].mul( tx1y0 ),
				Gy[ 2 ][ 0 ].mul( tx2y0 ),
				Gy[ 0 ][ 1 ].mul( tx0y1 ),
				Gy[ 1 ][ 1 ].mul( tx1y1 ),
				Gy[ 2 ][ 1 ].mul( tx2y1 ),
				Gy[ 0 ][ 2 ].mul( tx0y2 ),
				Gy[ 1 ][ 2 ].mul( tx1y2 ),
				Gy[ 2 ][ 2 ].mul( tx2y2 )
			);

			// magnitude of the total gradient

			const G = valueGx.mul( valueGx ).add( valueGy.mul( valueGy ) ).sqrt();

			return vec4( vec3( G ), 1 );

		} );

		const outputNode = sobel();

		return outputNode;

	}

}
```
</details>

#### Methods

##### `updateBefore(): void`

<details><summary>Code</summary>

```ts
updateBefore( /* frame */ ) {

		const map = this.textureNode.value;

		this._invSize.value.set( 1 / map.image.width, 1 / map.image.height );

	}
```
</details>

##### `setup(): ShaderCallNodeInternal`

<details><summary>Code</summary>

```ts
setup( /* builder */ ) {

		const { textureNode } = this;

		const uvNode = textureNode.uvNode || uv();

		const sampleTexture = ( uv ) => textureNode.sample( uv );

		const sobel = Fn( () => {

			// Sobel Edge Detection (see https://youtu.be/uihBwtPIBxM)

			const texel = this._invSize;

			// kernel definition (in glsl matrices are filled in column-major order)

			const Gx = mat3( - 1, - 2, - 1, 0, 0, 0, 1, 2, 1 ); // x direction kernel
			const Gy = mat3( - 1, 0, 1, - 2, 0, 2, - 1, 0, 1 ); // y direction kernel

			// fetch the 3x3 neighbourhood of a fragment

			// first column

			const tx0y0 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( - 1, - 1 ) ) ) ).xyz );
			const tx0y1 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( - 1, 0 ) ) ) ).xyz );
			const tx0y2 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( - 1, 1 ) ) ) ).xyz );

			// second column

			const tx1y0 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 0, - 1 ) ) ) ).xyz );
			const tx1y1 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 0, 0 ) ) ) ).xyz );
			const tx1y2 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 0, 1 ) ) ) ).xyz );

			// third column

			const tx2y0 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 1, - 1 ) ) ) ).xyz );
			const tx2y1 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 1, 0 ) ) ) ).xyz );
			const tx2y2 = luminance( sampleTexture( uvNode.add( texel.mul( vec2( 1, 1 ) ) ) ).xyz );

			// gradient value in x direction

			const valueGx = add(
				Gx[ 0 ][ 0 ].mul( tx0y0 ),
				Gx[ 1 ][ 0 ].mul( tx1y0 ),
				Gx[ 2 ][ 0 ].mul( tx2y0 ),
				Gx[ 0 ][ 1 ].mul( tx0y1 ),
				Gx[ 1 ][ 1 ].mul( tx1y1 ),
				Gx[ 2 ][ 1 ].mul( tx2y1 ),
				Gx[ 0 ][ 2 ].mul( tx0y2 ),
				Gx[ 1 ][ 2 ].mul( tx1y2 ),
				Gx[ 2 ][ 2 ].mul( tx2y2 )
			);


			// gradient value in y direction

			const valueGy = add(
				Gy[ 0 ][ 0 ].mul( tx0y0 ),
				Gy[ 1 ][ 0 ].mul( tx1y0 ),
				Gy[ 2 ][ 0 ].mul( tx2y0 ),
				Gy[ 0 ][ 1 ].mul( tx0y1 ),
				Gy[ 1 ][ 1 ].mul( tx1y1 ),
				Gy[ 2 ][ 1 ].mul( tx2y1 ),
				Gy[ 0 ][ 2 ].mul( tx0y2 ),
				Gy[ 1 ][ 2 ].mul( tx1y2 ),
				Gy[ 2 ][ 2 ].mul( tx2y2 )
			);

			// magnitude of the total gradient

			const G = valueGx.mul( valueGx ).add( valueGy.mul( valueGy ) ).sqrt();

			return vec4( vec3( G ), 1 );

		} );

		const outputNode = sobel();

		return outputNode;

	}
```
</details>


---