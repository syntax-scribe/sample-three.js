[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `TransitionNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 12 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/TransitionNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `TempNode` | `three/webgpu` |
| `nodeObject` | `three/tsl` |
| `Fn` | `three/tsl` |
| `float` | `three/tsl` |
| `uv` | `three/tsl` |
| `convertToTexture` | `three/tsl` |
| `vec4` | `three/tsl` |
| `If` | `three/tsl` |
| `int` | `three/tsl` |
| `clamp` | `three/tsl` |
| `sub` | `three/tsl` |
| `mix` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `uvNodeTexture` | `any` | let/var | `textureNode.uvNode \|\| uv()` | ✗ |


---

## Functions

### `TransitionNode.setup(): ShaderCallNodeInternal`

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
- `sampleTexture`
- `vec4().toVar`
- `If( useTextureNode.equal( int( 1 ) ), () => {

				const transitionTexel = sampleTexture( mixTextureNode );
				const r = mixRatioNode.mul( thresholdNode.mul( 2.0 ).add( 1.0 ) ).sub( thresholdNode );
				const mixf = clamp( sub( transitionTexel.r, r ).mul( float( 1.0 ).div( thresholdNode ) ), 0.0, 1.0 );

				color.assign( mix( texelOne, texelTwo, mixf ) );

			} ).Else`
- `color.assign`
- `mix (from three/tsl)`
- `transition`

<details><summary>Code</summary>

```typescript
setup() {

		const { textureNodeA, textureNodeB, mixTextureNode, mixRatioNode, thresholdNode, useTextureNode } = this;

		const sampleTexture = ( textureNode ) => {

			const uvNodeTexture = textureNode.uvNode || uv();
			return textureNode.sample( uvNodeTexture );

		};

		const transition = Fn( () => {

			const texelOne = sampleTexture( textureNodeA );
			const texelTwo = sampleTexture( textureNodeB );

			const color = vec4().toVar();

			If( useTextureNode.equal( int( 1 ) ), () => {

				const transitionTexel = sampleTexture( mixTextureNode );
				const r = mixRatioNode.mul( thresholdNode.mul( 2.0 ).add( 1.0 ) ).sub( thresholdNode );
				const mixf = clamp( sub( transitionTexel.r, r ).mul( float( 1.0 ).div( thresholdNode ) ), 0.0, 1.0 );

				color.assign( mix( texelOne, texelTwo, mixf ) );

			} ).Else( () => {

				color.assign( mix( texelTwo, texelOne, mixRatioNode ) );

			} );

			return color;

		} );

		const outputNode = transition();

		return outputNode;

	}
```
</details>

### `sampleTexture(textureNode: any): any`

**Parameters:**

- **`textureNode`** `any`

**Returns:** `any`

**Calls:**

- `uv (from three/tsl)`
- `textureNode.sample`

<details><summary>Code</summary>

```typescript
( textureNode ) => {

			const uvNodeTexture = textureNode.uvNode || uv();
			return textureNode.sample( uvNodeTexture );

		}
```
</details>

### `transition(nodeA: any, nodeB: any, mixTextureNode: any, mixRatio: any, threshold: any, useTexture: any): TransitionNode`

**Parameters:**

- **`nodeA`** `any`
- **`nodeB`** `any`
- **`mixTextureNode`** `any`
- **`mixRatio`** `any`
- **`threshold`** `any`
- **`useTexture`** `any`

**Returns:** `TransitionNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( nodeA, nodeB, mixTextureNode, mixRatio, threshold, useTexture ) => nodeObject( new TransitionNode( convertToTexture( nodeA ), convertToTexture( nodeB ), convertToTexture( mixTextureNode ), nodeObject( mixRatio ), nodeObject( threshold ), nodeObject( useTexture ) ) )
```
</details>


---

## Classes

### `TransitionNode`

<details><summary>Class Code</summary>

```ts
class TransitionNode extends TempNode {

	static get type() {

		return 'TransitionNode';

	}

	/**
	 * Constructs a new transition node.
	 *
	 * @param {TextureNode} textureNodeA - A texture node that represents the beauty pass of the first scene.
	 * @param {TextureNode} textureNodeB - A texture node that represents the beauty pass of the second scene.
	 * @param {TextureNode} mixTextureNode - A texture node that defines how the transition effect should look like.
	 * @param {Node<float>} mixRatioNode - The interpolation factor that controls the mix.
	 * @param {Node<float>} thresholdNode - Can be used to tweak the linear interpolation.
	 * @param {Node<float>} useTextureNode - Whether `mixTextureNode` should influence the transition or not.
	 */
	constructor( textureNodeA, textureNodeB, mixTextureNode, mixRatioNode, thresholdNode, useTextureNode ) {

		super( 'vec4' );

		/**
		 * A texture node that represents the beauty pass of the first scene.
		 *
		 * @type {TextureNode}
		 */
		this.textureNodeA = textureNodeA;

		/**
		 * A texture node that represents the beauty pass of the second scene.
		 *
		 * @type {TextureNode}
		 */
		this.textureNodeB = textureNodeB;

		/**
		 * A texture that defines how the transition effect should look like.
		 *
		 * @type {TextureNode}
		 */
		this.mixTextureNode = mixTextureNode;

		/**
		 * The interpolation factor that controls the mix.
		 *
		 * @type {Node<float>}
		 */
		this.mixRatioNode = mixRatioNode;

		/**
		 * Can be used to tweak the linear interpolation.
		 *
		 * @type {Node<float>}
		 */
		this.thresholdNode = thresholdNode;

		/**
		 * Whether `mixTextureNode` should influence the transition or not.
		 *
		 * @type {Node<float>}
		 */
		this.useTextureNode = useTextureNode;

	}

	/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {ShaderCallNodeInternal}
	 */
	setup() {

		const { textureNodeA, textureNodeB, mixTextureNode, mixRatioNode, thresholdNode, useTextureNode } = this;

		const sampleTexture = ( textureNode ) => {

			const uvNodeTexture = textureNode.uvNode || uv();
			return textureNode.sample( uvNodeTexture );

		};

		const transition = Fn( () => {

			const texelOne = sampleTexture( textureNodeA );
			const texelTwo = sampleTexture( textureNodeB );

			const color = vec4().toVar();

			If( useTextureNode.equal( int( 1 ) ), () => {

				const transitionTexel = sampleTexture( mixTextureNode );
				const r = mixRatioNode.mul( thresholdNode.mul( 2.0 ).add( 1.0 ) ).sub( thresholdNode );
				const mixf = clamp( sub( transitionTexel.r, r ).mul( float( 1.0 ).div( thresholdNode ) ), 0.0, 1.0 );

				color.assign( mix( texelOne, texelTwo, mixf ) );

			} ).Else( () => {

				color.assign( mix( texelTwo, texelOne, mixRatioNode ) );

			} );

			return color;

		} );

		const outputNode = transition();

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

		const { textureNodeA, textureNodeB, mixTextureNode, mixRatioNode, thresholdNode, useTextureNode } = this;

		const sampleTexture = ( textureNode ) => {

			const uvNodeTexture = textureNode.uvNode || uv();
			return textureNode.sample( uvNodeTexture );

		};

		const transition = Fn( () => {

			const texelOne = sampleTexture( textureNodeA );
			const texelTwo = sampleTexture( textureNodeB );

			const color = vec4().toVar();

			If( useTextureNode.equal( int( 1 ) ), () => {

				const transitionTexel = sampleTexture( mixTextureNode );
				const r = mixRatioNode.mul( thresholdNode.mul( 2.0 ).add( 1.0 ) ).sub( thresholdNode );
				const mixf = clamp( sub( transitionTexel.r, r ).mul( float( 1.0 ).div( thresholdNode ) ), 0.0, 1.0 );

				color.assign( mix( texelOne, texelTwo, mixf ) );

			} ).Else( () => {

				color.assign( mix( texelTwo, texelOne, mixRatioNode ) );

			} );

			return color;

		} );

		const outputNode = transition();

		return outputNode;

	}
```
</details>


---