[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `ChromaticAberrationNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/ChromaticAberrationNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector2` | `three/webgpu` |
| `TempNode` | `three/webgpu` |
| `nodeObject` | `three/tsl` |
| `Fn` | `three/tsl` |
| `uniform` | `three/tsl` |
| `convertToTexture` | `three/tsl` |
| `float` | `three/tsl` |
| `vec4` | `three/tsl` |
| `uv` | `three/tsl` |
| `NodeUpdateType` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `map` | `any` | let/var | `this.textureNode.value` | ✗ |
| `textureNode` | `texture` | let/var | `this.textureNode` | ✗ |
| `uvNode` | `any` | let/var | `textureNode.uvNode \|\| uv()` | ✗ |
| `r` | `any` | let/var | `textureNode.sample( finalRedUV ).r` | ✗ |
| `g` | `any` | let/var | `textureNode.sample( finalGreenUV ).g` | ✗ |
| `b` | `any` | let/var | `textureNode.sample( finalBlueUV ).b` | ✗ |
| `a` | `any` | let/var | `textureNode.sample( uv ).a` | ✗ |


---

## Functions

### `ChromaticAberrationNode.updateBefore(): void`

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

### `ChromaticAberrationNode.setup(): ShaderCallNodeInternal`

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
- `Fn( ( [ uv, strength, center, scale ] ) => {

			// Calculate distance from center
			const offset = uv.sub( center );
			const distance = offset.length();

			// Create stepped scaling zones based on distance
			// Each channel gets different scaling steps
			const redScale = float( 1.0 ).add( scale.mul( 0.02 ).mul( strength ) ); // Red channel scaled outward
			const greenScale = float( 1.0 ); // Green stays at original scale
			const blueScale = float( 1.0 ).sub( scale.mul( 0.02 ).mul( strength ) ); // Blue channel scaled inward

			// Create radial distortion based on distance from center
			const aberrationStrength = strength.mul( distance );

			// Calculate scaled UV coordinates for each channel
			const redUV = center.add( offset.mul( redScale ) );
			const greenUV = center.add( offset.mul( greenScale ) );
			const blueUV = center.add( offset.mul( blueScale ) );

			// Apply additional chromatic offset based on aberration strength
			const rOffset = offset.mul( aberrationStrength ).mul( float( 0.01 ) );
			const gOffset = offset.mul( aberrationStrength ).mul( float( 0.0 ) );
			const bOffset = offset.mul( aberrationStrength ).mul( float( - 0.01 ) );

			// Final UV coordinates combining scale and chromatic aberration
			const finalRedUV = redUV.add( rOffset );
			const finalGreenUV = greenUV.add( gOffset );
			const finalBlueUV = blueUV.add( bOffset );

			// Sample texture for each channel
			const r = textureNode.sample( finalRedUV ).r;
			const g = textureNode.sample( finalGreenUV ).g;
			const b = textureNode.sample( finalBlueUV ).b;

			// Get original alpha
			const a = textureNode.sample( uv ).a;

			return vec4( r, g, b, a );

		} ).setLayout`
- `Fn (from three/tsl)`
- `ApplyChromaticAberration`
- `chromaticAberrationFn`

**Internal Comments:**
```
// Calculate distance from center (x2)
// Create stepped scaling zones based on distance (x2)
// Each channel gets different scaling steps (x2)
// Create radial distortion based on distance from center (x2)
// Calculate scaled UV coordinates for each channel (x2)
// Apply additional chromatic offset based on aberration strength (x2)
// Final UV coordinates combining scale and chromatic aberration (x2)
// Sample texture for each channel (x2)
// Get original alpha (x2)
```

<details><summary>Code</summary>

```typescript
setup( /* builder */ ) {

		const textureNode = this.textureNode;
		const uvNode = textureNode.uvNode || uv();

		const ApplyChromaticAberration = Fn( ( [ uv, strength, center, scale ] ) => {

			// Calculate distance from center
			const offset = uv.sub( center );
			const distance = offset.length();

			// Create stepped scaling zones based on distance
			// Each channel gets different scaling steps
			const redScale = float( 1.0 ).add( scale.mul( 0.02 ).mul( strength ) ); // Red channel scaled outward
			const greenScale = float( 1.0 ); // Green stays at original scale
			const blueScale = float( 1.0 ).sub( scale.mul( 0.02 ).mul( strength ) ); // Blue channel scaled inward

			// Create radial distortion based on distance from center
			const aberrationStrength = strength.mul( distance );

			// Calculate scaled UV coordinates for each channel
			const redUV = center.add( offset.mul( redScale ) );
			const greenUV = center.add( offset.mul( greenScale ) );
			const blueUV = center.add( offset.mul( blueScale ) );

			// Apply additional chromatic offset based on aberration strength
			const rOffset = offset.mul( aberrationStrength ).mul( float( 0.01 ) );
			const gOffset = offset.mul( aberrationStrength ).mul( float( 0.0 ) );
			const bOffset = offset.mul( aberrationStrength ).mul( float( - 0.01 ) );

			// Final UV coordinates combining scale and chromatic aberration
			const finalRedUV = redUV.add( rOffset );
			const finalGreenUV = greenUV.add( gOffset );
			const finalBlueUV = blueUV.add( bOffset );

			// Sample texture for each channel
			const r = textureNode.sample( finalRedUV ).r;
			const g = textureNode.sample( finalGreenUV ).g;
			const b = textureNode.sample( finalBlueUV ).b;

			// Get original alpha
			const a = textureNode.sample( uv ).a;

			return vec4( r, g, b, a );

		} ).setLayout( {
			name: 'ChromaticAberrationShader',
			type: 'vec4',
			inputs: [
				{ name: 'uv', type: 'vec2' },
				{ name: 'strength', type: 'float' },
				{ name: 'center', type: 'vec2' },
				{ name: 'scale', type: 'float' },
				{ name: 'invSize', type: 'vec2' }
			]
		} );

		const chromaticAberrationFn = Fn( () => {

			return ApplyChromaticAberration(
				uvNode,
				this.strengthNode,
				this.centerNode,
				this.scaleNode,
				this._invSize
			);

		} );

		const outputNode = chromaticAberrationFn();

		return outputNode;

	}
```
</details>

### `chromaticAberration(node: any, strength: number | Node, center: any, scale: number | Node): ChromaticAberrationNode`

**Parameters:**

- **`node`** `any`
- **`strength`** `number | Node`
- **`center`** `any`
- **`scale`** `number | Node`

**Returns:** `ChromaticAberrationNode`

**Calls:**

- `nodeObject (from three/tsl)`
- `convertToTexture (from three/tsl)`

<details><summary>Code</summary>

```typescript
( node, strength = 1.0, center = null, scale = 1.1 ) => {

	return nodeObject(
		new ChromaticAberrationNode(
			convertToTexture( node ),
			nodeObject( strength ),
			nodeObject( center ),
			nodeObject( scale )
		)
	);
}
```
</details>


---

## Classes

### `ChromaticAberrationNode`

<details><summary>Class Code</summary>

```ts
class ChromaticAberrationNode extends TempNode {

	static get type() {

		return 'ChromaticAberrationNode';

	}

	/**
	 * Constructs a new chromatic aberration node.
	 *
	 * @param {TextureNode} textureNode - The texture node that represents the input of the effect.
	 * @param {Node} strengthNode - The strength of the chromatic aberration effect as a node.
	 * @param {Node} centerNode - The center point of the effect as a node.
	 * @param {Node} scaleNode - The scale factor for stepped scaling from center as a node.
	 */
	constructor( textureNode, strengthNode, centerNode, scaleNode ) {

		super( 'vec4' );

		/**
		 * The texture node that represents the input of the effect.
		 *
		 * @type {texture}
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
		 * A node holding the strength of the effect.
		 *
		 * @type {Node}
		 */
		this.strengthNode = strengthNode;

		/**
		 * A node holding the center point of the effect.
		 *
		 * @type {Node}
		 */
		this.centerNode = centerNode;

		/**
		 * A node holding the scale factor for stepped scaling.
		 *
		 * @type {Node}
		 */
		this.scaleNode = scaleNode;

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

		const textureNode = this.textureNode;
		const uvNode = textureNode.uvNode || uv();

		const ApplyChromaticAberration = Fn( ( [ uv, strength, center, scale ] ) => {

			// Calculate distance from center
			const offset = uv.sub( center );
			const distance = offset.length();

			// Create stepped scaling zones based on distance
			// Each channel gets different scaling steps
			const redScale = float( 1.0 ).add( scale.mul( 0.02 ).mul( strength ) ); // Red channel scaled outward
			const greenScale = float( 1.0 ); // Green stays at original scale
			const blueScale = float( 1.0 ).sub( scale.mul( 0.02 ).mul( strength ) ); // Blue channel scaled inward

			// Create radial distortion based on distance from center
			const aberrationStrength = strength.mul( distance );

			// Calculate scaled UV coordinates for each channel
			const redUV = center.add( offset.mul( redScale ) );
			const greenUV = center.add( offset.mul( greenScale ) );
			const blueUV = center.add( offset.mul( blueScale ) );

			// Apply additional chromatic offset based on aberration strength
			const rOffset = offset.mul( aberrationStrength ).mul( float( 0.01 ) );
			const gOffset = offset.mul( aberrationStrength ).mul( float( 0.0 ) );
			const bOffset = offset.mul( aberrationStrength ).mul( float( - 0.01 ) );

			// Final UV coordinates combining scale and chromatic aberration
			const finalRedUV = redUV.add( rOffset );
			const finalGreenUV = greenUV.add( gOffset );
			const finalBlueUV = blueUV.add( bOffset );

			// Sample texture for each channel
			const r = textureNode.sample( finalRedUV ).r;
			const g = textureNode.sample( finalGreenUV ).g;
			const b = textureNode.sample( finalBlueUV ).b;

			// Get original alpha
			const a = textureNode.sample( uv ).a;

			return vec4( r, g, b, a );

		} ).setLayout( {
			name: 'ChromaticAberrationShader',
			type: 'vec4',
			inputs: [
				{ name: 'uv', type: 'vec2' },
				{ name: 'strength', type: 'float' },
				{ name: 'center', type: 'vec2' },
				{ name: 'scale', type: 'float' },
				{ name: 'invSize', type: 'vec2' }
			]
		} );

		const chromaticAberrationFn = Fn( () => {

			return ApplyChromaticAberration(
				uvNode,
				this.strengthNode,
				this.centerNode,
				this.scaleNode,
				this._invSize
			);

		} );

		const outputNode = chromaticAberrationFn();

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

		const textureNode = this.textureNode;
		const uvNode = textureNode.uvNode || uv();

		const ApplyChromaticAberration = Fn( ( [ uv, strength, center, scale ] ) => {

			// Calculate distance from center
			const offset = uv.sub( center );
			const distance = offset.length();

			// Create stepped scaling zones based on distance
			// Each channel gets different scaling steps
			const redScale = float( 1.0 ).add( scale.mul( 0.02 ).mul( strength ) ); // Red channel scaled outward
			const greenScale = float( 1.0 ); // Green stays at original scale
			const blueScale = float( 1.0 ).sub( scale.mul( 0.02 ).mul( strength ) ); // Blue channel scaled inward

			// Create radial distortion based on distance from center
			const aberrationStrength = strength.mul( distance );

			// Calculate scaled UV coordinates for each channel
			const redUV = center.add( offset.mul( redScale ) );
			const greenUV = center.add( offset.mul( greenScale ) );
			const blueUV = center.add( offset.mul( blueScale ) );

			// Apply additional chromatic offset based on aberration strength
			const rOffset = offset.mul( aberrationStrength ).mul( float( 0.01 ) );
			const gOffset = offset.mul( aberrationStrength ).mul( float( 0.0 ) );
			const bOffset = offset.mul( aberrationStrength ).mul( float( - 0.01 ) );

			// Final UV coordinates combining scale and chromatic aberration
			const finalRedUV = redUV.add( rOffset );
			const finalGreenUV = greenUV.add( gOffset );
			const finalBlueUV = blueUV.add( bOffset );

			// Sample texture for each channel
			const r = textureNode.sample( finalRedUV ).r;
			const g = textureNode.sample( finalGreenUV ).g;
			const b = textureNode.sample( finalBlueUV ).b;

			// Get original alpha
			const a = textureNode.sample( uv ).a;

			return vec4( r, g, b, a );

		} ).setLayout( {
			name: 'ChromaticAberrationShader',
			type: 'vec4',
			inputs: [
				{ name: 'uv', type: 'vec2' },
				{ name: 'strength', type: 'float' },
				{ name: 'center', type: 'vec2' },
				{ name: 'scale', type: 'float' },
				{ name: 'invSize', type: 'vec2' }
			]
		} );

		const chromaticAberrationFn = Fn( () => {

			return ApplyChromaticAberration(
				uvNode,
				this.strengthNode,
				this.centerNode,
				this.scaleNode,
				this._invSize
			);

		} );

		const outputNode = chromaticAberrationFn();

		return outputNode;

	}
```
</details>


---