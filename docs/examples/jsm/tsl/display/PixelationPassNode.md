[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `PixelationPassNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 12 |
| 🧱 Classes | 2 |
| 📦 Imports | 24 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/PixelationPassNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NearestFilter` | `three/webgpu` |
| `Vector4` | `three/webgpu` |
| `TempNode` | `three/webgpu` |
| `NodeUpdateType` | `three/webgpu` |
| `PassNode` | `three/webgpu` |
| `nodeObject` | `three/tsl` |
| `Fn` | `three/tsl` |
| `float` | `three/tsl` |
| `uv` | `three/tsl` |
| `uniform` | `three/tsl` |
| `convertToTexture` | `three/tsl` |
| `vec2` | `three/tsl` |
| `vec3` | `three/tsl` |
| `clamp` | `three/tsl` |
| `floor` | `three/tsl` |
| `dot` | `three/tsl` |
| `smoothstep` | `three/tsl` |
| `If` | `three/tsl` |
| `sign` | `three/tsl` |
| `step` | `three/tsl` |
| `mrt` | `three/tsl` |
| `output` | `three/tsl` |
| `normalView` | `three/tsl` |
| `property` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `map` | `any` | let/var | `this.textureNode.value` | ✗ |
| `width` | `any` | let/var | `map.image.width` | ✗ |
| `height` | `any` | let/var | `map.image.height` | ✗ |
| `uvNodeTexture` | `any` | let/var | `textureNode.uvNode \|\| uv()` | ✗ |
| `uvNodeDepth` | `any` | let/var | `depthNode.uvNode \|\| uv()` | ✗ |
| `uvNodeNormal` | `any` | let/var | `normalNode.uvNode \|\| uv()` | ✗ |
| `pixelSize` | `any` | let/var | `this.pixelSize.value ? this.pixelSize.value : this.pixelSize` | ✗ |


---

## Functions

### `PixelationNode.updateBefore(): void`

**JSDoc:**
```typescript
/**
	 * This method is used to update uniforms once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
```

**Returns:** `void`

**Calls:**

- `this._resolution.value.set`

<details><summary>Code</summary>

```typescript
updateBefore() {

		const map = this.textureNode.value;

		const width = map.image.width;
		const height = map.image.height;

		this._resolution.value.set( width, height, 1 / width, 1 / height );

	}
```
</details>

### `PixelationNode.setup(): ShaderCallNodeInternal`

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
- `depthNode.sample`
- `uvNodeDepth.add`
- `vec2( x, y ).mul`
- `normalNode.sample( uvNodeNormal.add( vec2( x, y ).mul( this._resolution.zw ) ) ).rgb.normalize`
- `property (from three/tsl)`
- `diff.addAssign`
- `clamp (from three/tsl)`
- `sampleDepth( 1, 0 ).sub`
- `sampleDepth( - 1, 0 ).sub`
- `sampleDepth( 0, 1 ).sub`
- `sampleDepth( 0, - 1 ).sub`
- `floor( smoothstep( 0.01, 0.02, diff ).mul( 2 ) ).div`
- `sampleDepth( x, y ).sub`
- `sampleNormal`
- `vec3 (from three/tsl)`
- `dot (from three/tsl)`
- `normal.sub`
- `smoothstep (from three/tsl)`
- `sign (from three/tsl)`
- `depthDiff.mul( .25 ).add`
- `float( 1.0 ).sub( dot( normal, neighborNormal ) ).mul( depthIndicator ).mul`
- `indicator.addAssign`
- `neighborNormalEdgeIndicator`
- `step (from three/tsl)`
- `Fn (from three/tsl)`
- `sampleTexture`
- `If (from three/tsl)`
- `this.depthEdgeStrength.greaterThan( 0.0 ).or`
- `this.normalEdgeStrength.greaterThan`
- `depth.assign`
- `sampleDepth`
- `normal.assign`
- `this.depthEdgeStrength.greaterThan`
- `dei.assign`
- `depthEdgeIndicator`
- `nei.assign`
- `normalEdgeIndicator`
- `dei.greaterThan( 0 ).select`
- `float( 1.0 ).sub`
- `dei.mul`
- `nei.mul( this.normalEdgeStrength ).add`
- `texel.mul`
- `pixelation`

**Internal Comments:**
```
// Edge pixels should yield to faces who's normals are closer to the bias normal. (x2)
// Only the shallower pixel should detect the normal edge. (x2)
```

<details><summary>Code</summary>

```typescript
setup() {

		const { textureNode, depthNode, normalNode } = this;

		const uvNodeTexture = textureNode.uvNode || uv();
		const uvNodeDepth = depthNode.uvNode || uv();
		const uvNodeNormal = normalNode.uvNode || uv();

		const sampleTexture = () => textureNode.sample( uvNodeTexture );

		const sampleDepth = ( x, y ) => depthNode.sample( uvNodeDepth.add( vec2( x, y ).mul( this._resolution.zw ) ) ).r;

		const sampleNormal = ( x, y ) => normalNode.sample( uvNodeNormal.add( vec2( x, y ).mul( this._resolution.zw ) ) ).rgb.normalize();

		const depthEdgeIndicator = ( depth ) => {

			const diff = property( 'float', 'diff' );
			diff.addAssign( clamp( sampleDepth( 1, 0 ).sub( depth ) ) );
			diff.addAssign( clamp( sampleDepth( - 1, 0 ).sub( depth ) ) );
			diff.addAssign( clamp( sampleDepth( 0, 1 ).sub( depth ) ) );
			diff.addAssign( clamp( sampleDepth( 0, - 1 ).sub( depth ) ) );

			return floor( smoothstep( 0.01, 0.02, diff ).mul( 2 ) ).div( 2 );

		};

		const neighborNormalEdgeIndicator = ( x, y, depth, normal ) => {

			const depthDiff = sampleDepth( x, y ).sub( depth );
			const neighborNormal = sampleNormal( x, y );

			// Edge pixels should yield to faces who's normals are closer to the bias normal.

			const normalEdgeBias = vec3( 1, 1, 1 ); // This should probably be a parameter.
			const normalDiff = dot( normal.sub( neighborNormal ), normalEdgeBias );
			const normalIndicator = clamp( smoothstep( - 0.01, 0.01, normalDiff ), 0.0, 1.0 );

			// Only the shallower pixel should detect the normal edge.

			const depthIndicator = clamp( sign( depthDiff.mul( .25 ).add( .0025 ) ), 0.0, 1.0 );

			return float( 1.0 ).sub( dot( normal, neighborNormal ) ).mul( depthIndicator ).mul( normalIndicator );

		};

		const normalEdgeIndicator = ( depth, normal ) => {

			const indicator = property( 'float', 'indicator' );

			indicator.addAssign( neighborNormalEdgeIndicator( 0, - 1, depth, normal ) );
			indicator.addAssign( neighborNormalEdgeIndicator( 0, 1, depth, normal ) );
			indicator.addAssign( neighborNormalEdgeIndicator( - 1, 0, depth, normal ) );
			indicator.addAssign( neighborNormalEdgeIndicator( 1, 0, depth, normal ) );

			return step( 0.1, indicator );

		};

		const pixelation = Fn( () => {

			const texel = sampleTexture();

			const depth = property( 'float', 'depth' );
			const normal = property( 'vec3', 'normal' );

			If( this.depthEdgeStrength.greaterThan( 0.0 ).or( this.normalEdgeStrength.greaterThan( 0.0 ) ), () => {

				depth.assign( sampleDepth( 0, 0 ) );
				normal.assign( sampleNormal( 0, 0 ) );

			} );

			const dei = property( 'float', 'dei' );

			If( this.depthEdgeStrength.greaterThan( 0.0 ), () => {

				dei.assign( depthEdgeIndicator( depth ) );

			} );

			const nei = property( 'float', 'nei' );

			If( this.normalEdgeStrength.greaterThan( 0.0 ), () => {

				nei.assign( normalEdgeIndicator( depth, normal ) );

			} );

			const strength = dei.greaterThan( 0 ).select( float( 1.0 ).sub( dei.mul( this.depthEdgeStrength ) ), nei.mul( this.normalEdgeStrength ).add( 1 ) );

			return texel.mul( strength );

		} );

		const outputNode = pixelation();

		return outputNode;

	}
```
</details>

### `sampleTexture(): any`

**Returns:** `any`

**Calls:**

- `textureNode.sample`

<details><summary>Code</summary>

```typescript
() => textureNode.sample( uvNodeTexture )
```
</details>

### `sampleDepth(x: any, y: any): any`

**Parameters:**

- **`x`** `any`
- **`y`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
( x, y ) => depthNode.sample( uvNodeDepth.add( vec2( x, y ).mul( this._resolution.zw ) ) ).r
```
</details>

### `sampleNormal(x: any, y: any): any`

**Parameters:**

- **`x`** `any`
- **`y`** `any`

**Returns:** `any`

**Calls:**

- `normalNode.sample( uvNodeNormal.add( vec2( x, y ).mul( this._resolution.zw ) ) ).rgb.normalize`

<details><summary>Code</summary>

```typescript
( x, y ) => normalNode.sample( uvNodeNormal.add( vec2( x, y ).mul( this._resolution.zw ) ) ).rgb.normalize()
```
</details>

### `depthEdgeIndicator(depth: any): any`

**Parameters:**

- **`depth`** `any`

**Returns:** `any`

**Calls:**

- `property (from three/tsl)`
- `diff.addAssign`
- `clamp (from three/tsl)`
- `sampleDepth( 1, 0 ).sub`
- `sampleDepth( - 1, 0 ).sub`
- `sampleDepth( 0, 1 ).sub`
- `sampleDepth( 0, - 1 ).sub`
- `floor( smoothstep( 0.01, 0.02, diff ).mul( 2 ) ).div`

<details><summary>Code</summary>

```typescript
( depth ) => {

			const diff = property( 'float', 'diff' );
			diff.addAssign( clamp( sampleDepth( 1, 0 ).sub( depth ) ) );
			diff.addAssign( clamp( sampleDepth( - 1, 0 ).sub( depth ) ) );
			diff.addAssign( clamp( sampleDepth( 0, 1 ).sub( depth ) ) );
			diff.addAssign( clamp( sampleDepth( 0, - 1 ).sub( depth ) ) );

			return floor( smoothstep( 0.01, 0.02, diff ).mul( 2 ) ).div( 2 );

		}
```
</details>

### `neighborNormalEdgeIndicator(x: any, y: any, depth: any, normal: any): any`

**Parameters:**

- **`x`** `any`
- **`y`** `any`
- **`depth`** `any`
- **`normal`** `any`

**Returns:** `any`

**Calls:**

- `sampleDepth( x, y ).sub`
- `sampleNormal`
- `vec3 (from three/tsl)`
- `dot (from three/tsl)`
- `normal.sub`
- `clamp (from three/tsl)`
- `smoothstep (from three/tsl)`
- `sign (from three/tsl)`
- `depthDiff.mul( .25 ).add`
- `float( 1.0 ).sub( dot( normal, neighborNormal ) ).mul( depthIndicator ).mul`

**Internal Comments:**
```
// Edge pixels should yield to faces who's normals are closer to the bias normal. (x2)
// Only the shallower pixel should detect the normal edge. (x2)
```

<details><summary>Code</summary>

```typescript
( x, y, depth, normal ) => {

			const depthDiff = sampleDepth( x, y ).sub( depth );
			const neighborNormal = sampleNormal( x, y );

			// Edge pixels should yield to faces who's normals are closer to the bias normal.

			const normalEdgeBias = vec3( 1, 1, 1 ); // This should probably be a parameter.
			const normalDiff = dot( normal.sub( neighborNormal ), normalEdgeBias );
			const normalIndicator = clamp( smoothstep( - 0.01, 0.01, normalDiff ), 0.0, 1.0 );

			// Only the shallower pixel should detect the normal edge.

			const depthIndicator = clamp( sign( depthDiff.mul( .25 ).add( .0025 ) ), 0.0, 1.0 );

			return float( 1.0 ).sub( dot( normal, neighborNormal ) ).mul( depthIndicator ).mul( normalIndicator );

		}
```
</details>

### `normalEdgeIndicator(depth: any, normal: any): any`

**Parameters:**

- **`depth`** `any`
- **`normal`** `any`

**Returns:** `any`

**Calls:**

- `property (from three/tsl)`
- `indicator.addAssign`
- `neighborNormalEdgeIndicator`
- `step (from three/tsl)`

<details><summary>Code</summary>

```typescript
( depth, normal ) => {

			const indicator = property( 'float', 'indicator' );

			indicator.addAssign( neighborNormalEdgeIndicator( 0, - 1, depth, normal ) );
			indicator.addAssign( neighborNormalEdgeIndicator( 0, 1, depth, normal ) );
			indicator.addAssign( neighborNormalEdgeIndicator( - 1, 0, depth, normal ) );
			indicator.addAssign( neighborNormalEdgeIndicator( 1, 0, depth, normal ) );

			return step( 0.1, indicator );

		}
```
</details>

### `pixelation(node: any, depthNode: any, normalNode: any, pixelSize: number, normalEdgeStrength: number, depthEdgeStrength: number): any`

**Parameters:**

- **`node`** `any`
- **`depthNode`** `any`
- **`normalNode`** `any`
- **`pixelSize`** `number`
- **`normalEdgeStrength`** `number`
- **`depthEdgeStrength`** `number`

**Returns:** `any`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( node, depthNode, normalNode, pixelSize = 6, normalEdgeStrength = 0.3, depthEdgeStrength = 0.4 ) => nodeObject( new PixelationNode( convertToTexture( node ), convertToTexture( depthNode ), convertToTexture( normalNode ), nodeObject( pixelSize ), nodeObject( normalEdgeStrength ), nodeObject( depthEdgeStrength ) ) )
```
</details>

### `PixelationPassNode.setSize(width: number, height: number): void`

**JSDoc:**
```typescript
/**
	 * Sets the size of the pass.
	 *
	 * @param {number} width - The width of the pass.
	 * @param {number} height - The height of the pass.
	 */
```

**Parameters:**

- **`width`** `number`
- **`height`** `number`

**Returns:** `void`

**Calls:**

- `Math.floor`
- `super.setSize`

<details><summary>Code</summary>

```typescript
setSize( width, height ) {

		const pixelSize = this.pixelSize.value ? this.pixelSize.value : this.pixelSize;

		const adjustedWidth = Math.floor( width / pixelSize );
		const adjustedHeight = Math.floor( height / pixelSize );

		super.setSize( adjustedWidth, adjustedHeight );

	}
```
</details>

### `PixelationPassNode.setup(): PixelationNode`

**JSDoc:**
```typescript
/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {PixelationNode}
	 */
```

**Returns:** `PixelationNode`

**Calls:**

- `super.getTextureNode`
- `pixelation`

<details><summary>Code</summary>

```typescript
setup() {

		const color = super.getTextureNode( 'output' );
		const depth = super.getTextureNode( 'depth' );
		const normal = super.getTextureNode( 'normal' );

		return pixelation( color, depth, normal, this.pixelSize, this.normalEdgeStrength, this.depthEdgeStrength );

	}
```
</details>

### `pixelationPass(scene: Scene, camera: Camera, pixelSize: any, normalEdgeStrength: any, depthEdgeStrength: any): PixelationPassNode`

**Parameters:**

- **`scene`** `Scene`
- **`camera`** `Camera`
- **`pixelSize`** `any`
- **`normalEdgeStrength`** `any`
- **`depthEdgeStrength`** `any`

**Returns:** `PixelationPassNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( scene, camera, pixelSize, normalEdgeStrength, depthEdgeStrength ) => nodeObject( new PixelationPassNode( scene, camera, pixelSize, normalEdgeStrength, depthEdgeStrength ) )
```
</details>


---

## Classes

### `PixelationNode`

<details><summary>Class Code</summary>

```ts
class PixelationNode extends TempNode {

	static get type() {

		return 'PixelationNode';

	}

	/**
	 * Constructs a new pixelation node.
	 *
	 * @param {TextureNode} textureNode - The texture node that represents the beauty pass.
	 * @param {TextureNode} depthNode - The texture that represents the beauty's depth.
	 * @param {TextureNode} normalNode - The texture that represents the beauty's normals.
	 * @param {Node<float>} pixelSize - The pixel size.
	 * @param {Node<float>} normalEdgeStrength - The normal edge strength.
	 * @param {Node<float>} depthEdgeStrength - The depth edge strength.
	 */
	constructor( textureNode, depthNode, normalNode, pixelSize, normalEdgeStrength, depthEdgeStrength ) {

		super( 'vec4' );

		/**
		 * The texture node that represents the beauty pass.
		 *
		 * @type {TextureNode}
		 */
		this.textureNode = textureNode;

		/**
		 * The texture that represents the beauty's depth.
		 *
		 * @type {TextureNode}
		 */
		this.depthNode = depthNode;

		/**
		 * The texture that represents the beauty's normals.
		 *
		 * @type {TextureNode}
		 */
		this.normalNode = normalNode;

		/**
		 * The pixel size.
		 *
		 * @type {Node<float>}
		 */
		this.pixelSize = pixelSize;

		/**
		 * The pixel size.
		 *
		 * @type {Node<float>}
		 */
		this.normalEdgeStrength = normalEdgeStrength;

		/**
		 * The depth edge strength.
		 *
		 * @type {Node<float>}
		 */
		this.depthEdgeStrength = depthEdgeStrength;

		/**
		 * Uniform node that represents the resolution.
		 *
		 * @type {Node<vec4>}
		 */
		this._resolution = uniform( new Vector4() );

		/**
		 * The `updateBeforeType` is set to `NodeUpdateType.FRAME` since the node updates
		 * its internal uniforms once per frame in `updateBefore()`.
		 *
		 * @type {string}
		 * @default 'frame'
		 */
		this.updateBeforeType = NodeUpdateType.FRAME;

	}

	/**
	 * This method is used to update uniforms once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
	updateBefore() {

		const map = this.textureNode.value;

		const width = map.image.width;
		const height = map.image.height;

		this._resolution.value.set( width, height, 1 / width, 1 / height );

	}

	/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {ShaderCallNodeInternal}
	 */
	setup() {

		const { textureNode, depthNode, normalNode } = this;

		const uvNodeTexture = textureNode.uvNode || uv();
		const uvNodeDepth = depthNode.uvNode || uv();
		const uvNodeNormal = normalNode.uvNode || uv();

		const sampleTexture = () => textureNode.sample( uvNodeTexture );

		const sampleDepth = ( x, y ) => depthNode.sample( uvNodeDepth.add( vec2( x, y ).mul( this._resolution.zw ) ) ).r;

		const sampleNormal = ( x, y ) => normalNode.sample( uvNodeNormal.add( vec2( x, y ).mul( this._resolution.zw ) ) ).rgb.normalize();

		const depthEdgeIndicator = ( depth ) => {

			const diff = property( 'float', 'diff' );
			diff.addAssign( clamp( sampleDepth( 1, 0 ).sub( depth ) ) );
			diff.addAssign( clamp( sampleDepth( - 1, 0 ).sub( depth ) ) );
			diff.addAssign( clamp( sampleDepth( 0, 1 ).sub( depth ) ) );
			diff.addAssign( clamp( sampleDepth( 0, - 1 ).sub( depth ) ) );

			return floor( smoothstep( 0.01, 0.02, diff ).mul( 2 ) ).div( 2 );

		};

		const neighborNormalEdgeIndicator = ( x, y, depth, normal ) => {

			const depthDiff = sampleDepth( x, y ).sub( depth );
			const neighborNormal = sampleNormal( x, y );

			// Edge pixels should yield to faces who's normals are closer to the bias normal.

			const normalEdgeBias = vec3( 1, 1, 1 ); // This should probably be a parameter.
			const normalDiff = dot( normal.sub( neighborNormal ), normalEdgeBias );
			const normalIndicator = clamp( smoothstep( - 0.01, 0.01, normalDiff ), 0.0, 1.0 );

			// Only the shallower pixel should detect the normal edge.

			const depthIndicator = clamp( sign( depthDiff.mul( .25 ).add( .0025 ) ), 0.0, 1.0 );

			return float( 1.0 ).sub( dot( normal, neighborNormal ) ).mul( depthIndicator ).mul( normalIndicator );

		};

		const normalEdgeIndicator = ( depth, normal ) => {

			const indicator = property( 'float', 'indicator' );

			indicator.addAssign( neighborNormalEdgeIndicator( 0, - 1, depth, normal ) );
			indicator.addAssign( neighborNormalEdgeIndicator( 0, 1, depth, normal ) );
			indicator.addAssign( neighborNormalEdgeIndicator( - 1, 0, depth, normal ) );
			indicator.addAssign( neighborNormalEdgeIndicator( 1, 0, depth, normal ) );

			return step( 0.1, indicator );

		};

		const pixelation = Fn( () => {

			const texel = sampleTexture();

			const depth = property( 'float', 'depth' );
			const normal = property( 'vec3', 'normal' );

			If( this.depthEdgeStrength.greaterThan( 0.0 ).or( this.normalEdgeStrength.greaterThan( 0.0 ) ), () => {

				depth.assign( sampleDepth( 0, 0 ) );
				normal.assign( sampleNormal( 0, 0 ) );

			} );

			const dei = property( 'float', 'dei' );

			If( this.depthEdgeStrength.greaterThan( 0.0 ), () => {

				dei.assign( depthEdgeIndicator( depth ) );

			} );

			const nei = property( 'float', 'nei' );

			If( this.normalEdgeStrength.greaterThan( 0.0 ), () => {

				nei.assign( normalEdgeIndicator( depth, normal ) );

			} );

			const strength = dei.greaterThan( 0 ).select( float( 1.0 ).sub( dei.mul( this.depthEdgeStrength ) ), nei.mul( this.normalEdgeStrength ).add( 1 ) );

			return texel.mul( strength );

		} );

		const outputNode = pixelation();

		return outputNode;

	}

}
```
</details>

#### Methods

##### `updateBefore(): void`

<details><summary>Code</summary>

```ts
updateBefore() {

		const map = this.textureNode.value;

		const width = map.image.width;
		const height = map.image.height;

		this._resolution.value.set( width, height, 1 / width, 1 / height );

	}
```
</details>

##### `setup(): ShaderCallNodeInternal`

<details><summary>Code</summary>

```ts
setup() {

		const { textureNode, depthNode, normalNode } = this;

		const uvNodeTexture = textureNode.uvNode || uv();
		const uvNodeDepth = depthNode.uvNode || uv();
		const uvNodeNormal = normalNode.uvNode || uv();

		const sampleTexture = () => textureNode.sample( uvNodeTexture );

		const sampleDepth = ( x, y ) => depthNode.sample( uvNodeDepth.add( vec2( x, y ).mul( this._resolution.zw ) ) ).r;

		const sampleNormal = ( x, y ) => normalNode.sample( uvNodeNormal.add( vec2( x, y ).mul( this._resolution.zw ) ) ).rgb.normalize();

		const depthEdgeIndicator = ( depth ) => {

			const diff = property( 'float', 'diff' );
			diff.addAssign( clamp( sampleDepth( 1, 0 ).sub( depth ) ) );
			diff.addAssign( clamp( sampleDepth( - 1, 0 ).sub( depth ) ) );
			diff.addAssign( clamp( sampleDepth( 0, 1 ).sub( depth ) ) );
			diff.addAssign( clamp( sampleDepth( 0, - 1 ).sub( depth ) ) );

			return floor( smoothstep( 0.01, 0.02, diff ).mul( 2 ) ).div( 2 );

		};

		const neighborNormalEdgeIndicator = ( x, y, depth, normal ) => {

			const depthDiff = sampleDepth( x, y ).sub( depth );
			const neighborNormal = sampleNormal( x, y );

			// Edge pixels should yield to faces who's normals are closer to the bias normal.

			const normalEdgeBias = vec3( 1, 1, 1 ); // This should probably be a parameter.
			const normalDiff = dot( normal.sub( neighborNormal ), normalEdgeBias );
			const normalIndicator = clamp( smoothstep( - 0.01, 0.01, normalDiff ), 0.0, 1.0 );

			// Only the shallower pixel should detect the normal edge.

			const depthIndicator = clamp( sign( depthDiff.mul( .25 ).add( .0025 ) ), 0.0, 1.0 );

			return float( 1.0 ).sub( dot( normal, neighborNormal ) ).mul( depthIndicator ).mul( normalIndicator );

		};

		const normalEdgeIndicator = ( depth, normal ) => {

			const indicator = property( 'float', 'indicator' );

			indicator.addAssign( neighborNormalEdgeIndicator( 0, - 1, depth, normal ) );
			indicator.addAssign( neighborNormalEdgeIndicator( 0, 1, depth, normal ) );
			indicator.addAssign( neighborNormalEdgeIndicator( - 1, 0, depth, normal ) );
			indicator.addAssign( neighborNormalEdgeIndicator( 1, 0, depth, normal ) );

			return step( 0.1, indicator );

		};

		const pixelation = Fn( () => {

			const texel = sampleTexture();

			const depth = property( 'float', 'depth' );
			const normal = property( 'vec3', 'normal' );

			If( this.depthEdgeStrength.greaterThan( 0.0 ).or( this.normalEdgeStrength.greaterThan( 0.0 ) ), () => {

				depth.assign( sampleDepth( 0, 0 ) );
				normal.assign( sampleNormal( 0, 0 ) );

			} );

			const dei = property( 'float', 'dei' );

			If( this.depthEdgeStrength.greaterThan( 0.0 ), () => {

				dei.assign( depthEdgeIndicator( depth ) );

			} );

			const nei = property( 'float', 'nei' );

			If( this.normalEdgeStrength.greaterThan( 0.0 ), () => {

				nei.assign( normalEdgeIndicator( depth, normal ) );

			} );

			const strength = dei.greaterThan( 0 ).select( float( 1.0 ).sub( dei.mul( this.depthEdgeStrength ) ), nei.mul( this.normalEdgeStrength ).add( 1 ) );

			return texel.mul( strength );

		} );

		const outputNode = pixelation();

		return outputNode;

	}
```
</details>

### `PixelationPassNode`

<details><summary>Class Code</summary>

```ts
class PixelationPassNode extends PassNode {

	static get type() {

		return 'PixelationPassNode';

	}

	/**
	 * Constructs a new pixelation pass node.
	 *
	 * @param {Scene} scene - The scene to render.
	 * @param {Camera} camera - The camera to render the scene with.
	 * @param {Node<float> | number} [pixelSize=6] - The pixel size.
	 * @param {Node<float> | number} [normalEdgeStrength=0.3] - The normal edge strength.
	 * @param {Node<float> | number} [depthEdgeStrength=0.4] - The depth edge strength.
	 */
	constructor( scene, camera, pixelSize = 6, normalEdgeStrength = 0.3, depthEdgeStrength = 0.4 ) {

		super( PassNode.COLOR, scene, camera, { minFilter: NearestFilter, magFilter: NearestFilter } );

		/**
		 * The pixel size.
		 *
		 * @type {number}
		 * @default 6
		 */
		this.pixelSize = pixelSize;

		/**
		 * The normal edge strength.
		 *
		 * @type {number}
		 * @default 0.3
		 */
		this.normalEdgeStrength = normalEdgeStrength;

		/**
		 * The depth edge strength.
		 *
		 * @type {number}
		 * @default 0.4
		 */
		this.depthEdgeStrength = depthEdgeStrength;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isPixelationPassNode = true;

		this._mrt = mrt( {
			output: output,
			normal: normalView
		} );

	}

	/**
	 * Sets the size of the pass.
	 *
	 * @param {number} width - The width of the pass.
	 * @param {number} height - The height of the pass.
	 */
	setSize( width, height ) {

		const pixelSize = this.pixelSize.value ? this.pixelSize.value : this.pixelSize;

		const adjustedWidth = Math.floor( width / pixelSize );
		const adjustedHeight = Math.floor( height / pixelSize );

		super.setSize( adjustedWidth, adjustedHeight );

	}

	/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {PixelationNode}
	 */
	setup() {

		const color = super.getTextureNode( 'output' );
		const depth = super.getTextureNode( 'depth' );
		const normal = super.getTextureNode( 'normal' );

		return pixelation( color, depth, normal, this.pixelSize, this.normalEdgeStrength, this.depthEdgeStrength );

	}

}
```
</details>

#### Methods

##### `setSize(width: number, height: number): void`

<details><summary>Code</summary>

```ts
setSize( width, height ) {

		const pixelSize = this.pixelSize.value ? this.pixelSize.value : this.pixelSize;

		const adjustedWidth = Math.floor( width / pixelSize );
		const adjustedHeight = Math.floor( height / pixelSize );

		super.setSize( adjustedWidth, adjustedHeight );

	}
```
</details>

##### `setup(): PixelationNode`

<details><summary>Code</summary>

```ts
setup() {

		const color = super.getTextureNode( 'output' );
		const depth = super.getTextureNode( 'depth' );
		const normal = super.getTextureNode( 'normal' );

		return pixelation( color, depth, normal, this.pixelSize, this.normalEdgeStrength, this.depthEdgeStrength );

	}
```
</details>


---