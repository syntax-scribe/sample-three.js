[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `DenoiseNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 🧱 Classes | 1 |
| 📦 Imports | 34 |
| 📊 Variables & Constants | 10 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/tsl/display/DenoiseNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DataTexture` | `three/webgpu` |
| `RepeatWrapping` | `three/webgpu` |
| `Vector2` | `three/webgpu` |
| `Vector3` | `three/webgpu` |
| `TempNode` | `three/webgpu` |
| `texture` | `three/tsl` |
| `getNormalFromDepth` | `three/tsl` |
| `getViewPosition` | `three/tsl` |
| `convertToTexture` | `three/tsl` |
| `nodeObject` | `three/tsl` |
| `Fn` | `three/tsl` |
| `float` | `three/tsl` |
| `NodeUpdateType` | `three/tsl` |
| `uv` | `three/tsl` |
| `uniform` | `three/tsl` |
| `Loop` | `three/tsl` |
| `luminance` | `three/tsl` |
| `vec2` | `three/tsl` |
| `vec3` | `three/tsl` |
| `vec4` | `three/tsl` |
| `uniformArray` | `three/tsl` |
| `int` | `three/tsl` |
| `dot` | `three/tsl` |
| `max` | `three/tsl` |
| `pow` | `three/tsl` |
| `abs` | `three/tsl` |
| `If` | `three/tsl` |
| `textureSize` | `three/tsl` |
| `sin` | `three/tsl` |
| `cos` | `three/tsl` |
| `mat2` | `three/tsl` |
| `PI` | `three/tsl` |
| `property` | `three/tsl` |
| `SimplexNoise` | `../../math/SimplexNoise.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `map` | `any` | let/var | `this.textureNode.value` | ✗ |
| `neighborColor` | `any` | let/var | `texel.rgb` | ✗ |
| `samples` | `any[]` | let/var | `[]` | ✗ |
| `angle` | `number` | let/var | `2 * Math.PI * numRings * i / numSamples` | ✗ |
| `simplex` | `SimplexNoise` | let/var | `new SimplexNoise()` | ✗ |
| `arraySize` | `number` | let/var | `size * size * 4` | ✗ |
| `data` | `Uint8Array<ArrayBuffer>` | let/var | `new Uint8Array( arraySize )` | ✗ |
| `x` | `number` | let/var | `i` | ✗ |
| `y` | `number` | let/var | `j` | ✗ |
| `noiseTexture` | `any` | let/var | `new DataTexture( data, size, size )` | ✗ |


---

## Functions

### `DenoiseNode.updateBefore(): void`

**JSDoc:**
```typescript
/**
	 * This method is used to update internal uniforms once per frame.
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

		this._resolution.value.set( map.image.width, map.image.height );

	}
```
</details>

### `DenoiseNode.setup(): ShaderCallNodeInternal`

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
- `this.textureNode.sample`
- `this.depthNode.sample`
- `this.normalNode.sample( uv ).rgb.normalize`
- `getNormalFromDepth (from three/tsl)`
- `this.noiseNode.sample`
- `Fn (from three/tsl)`
- `sampleTexture( sampleUv ).toVar`
- `sampleDepth( sampleUv ).toVar`
- `sampleNormal( sampleUv ).toVar`
- `getViewPosition( sampleUv, depth, this._cameraProjectionMatrixInverse ).toVar`
- `dot( viewNormal, normal ).toVar`
- `pow( max( normalDiff, 0 ), this.normalPhi ).toVar`
- `abs( luminance( neighborColor ).sub( luminance( center ) ) ).toVar`
- `max( float( 1.0 ).sub( lumaDiff.div( this.lumaPhi ) ), 0 ).toVar`
- `abs( dot( viewPosition.sub( viewPos ), viewNormal ) ).toVar`
- `max (from three/tsl)`
- `float( 1.0 ).sub`
- `depthDiff.div`
- `lumaSimilarity.mul( depthSimilarity ).mul`
- `vec4 (from three/tsl)`
- `neighborColor.mul`
- `sampleDepth( uvNode ).toVar`
- `sampleNormal( uvNode ).toVar`
- `sampleTexture( uvNode ).toVar`
- `property (from three/tsl)`
- `If( depth.greaterThanEqual( 1.0 ).or( dot( viewNormal, viewNormal ).equal( 0.0 ) ), () => {

				result.assign( texel );

			} ).Else`
- `vec3 (from three/tsl)`
- `getViewPosition( uvNode, depth, this._cameraProjectionMatrixInverse ).toConst`
- `textureSize (from three/tsl)`
- `vec2 (from three/tsl)`
- `uvNode.y.oneMinus`
- `noiseUv.mul`
- `this._resolution.div`
- `sampleNoise( noiseUv ).toVar`
- `sin (from three/tsl)`
- `noiseTexel.element`
- `this.index.mod( 4 ).mul( 2 ).mul`
- `cos (from three/tsl)`
- `mat2 (from three/tsl)`
- `noiseVec.y.negate`
- `float( 1.0 ).toVar`
- `vec3( texel.rgb ).toVar`
- `Loop (from three/tsl)`
- `int (from three/tsl)`
- `this._sampleVectors.element`
- `rotationMatrix.mul( sampleDir.xy.mul( float( 1.0 ).add( sampleDir.z.mul( this.radius.sub( 1 ) ) ) ) ).div`
- `uvNode.add`
- `denoiseSample`
- `denoised.addAssign`
- `totalWeight.addAssign`
- `If (from three/tsl)`
- `totalWeight.greaterThan`
- `float (from three/tsl)`
- `denoised.divAssign`
- `result.assign`
- `denoise`
- `output`

<details><summary>Code</summary>

```typescript
setup( /* builder */ ) {

		const uvNode = uv();

		const sampleTexture = ( uv ) => this.textureNode.sample( uv );
		const sampleDepth = ( uv ) => this.depthNode.sample( uv ).x;
		const sampleNormal = ( uv ) => ( this.normalNode !== null ) ? this.normalNode.sample( uv ).rgb.normalize() : getNormalFromDepth( uv, this.depthNode.value, this._cameraProjectionMatrixInverse );
		const sampleNoise = ( uv ) => this.noiseNode.sample( uv );

		const denoiseSample = Fn( ( [ center, viewNormal, viewPosition, sampleUv ] ) => {

			const texel = sampleTexture( sampleUv ).toVar();
			const depth = sampleDepth( sampleUv ).toVar();
			const normal = sampleNormal( sampleUv ).toVar();
			const neighborColor = texel.rgb;
			const viewPos = getViewPosition( sampleUv, depth, this._cameraProjectionMatrixInverse ).toVar();

			const normalDiff = dot( viewNormal, normal ).toVar();
			const normalSimilarity = pow( max( normalDiff, 0 ), this.normalPhi ).toVar();
			const lumaDiff = abs( luminance( neighborColor ).sub( luminance( center ) ) ).toVar();
			const lumaSimilarity = max( float( 1.0 ).sub( lumaDiff.div( this.lumaPhi ) ), 0 ).toVar();
			const depthDiff = abs( dot( viewPosition.sub( viewPos ), viewNormal ) ).toVar();
			const depthSimilarity = max( float( 1.0 ).sub( depthDiff.div( this.depthPhi ) ), 0 );
			const w = lumaSimilarity.mul( depthSimilarity ).mul( normalSimilarity );

			return vec4( neighborColor.mul( w ), w );

		} );

		const denoise = Fn( ( [ uvNode ] ) => {

			const depth = sampleDepth( uvNode ).toVar();
			const viewNormal = sampleNormal( uvNode ).toVar();

			const texel = sampleTexture( uvNode ).toVar();
			const result = property( 'vec4' );

			If( depth.greaterThanEqual( 1.0 ).or( dot( viewNormal, viewNormal ).equal( 0.0 ) ), () => {

				result.assign( texel );

			} ).Else( () => {

				const center = vec3( texel.rgb );

				const viewPosition = getViewPosition( uvNode, depth, this._cameraProjectionMatrixInverse ).toConst();

				const noiseResolution = textureSize( this.noiseNode, 0 );
				let noiseUv = vec2( uvNode.x, uvNode.y.oneMinus() );
				noiseUv = noiseUv.mul( this._resolution.div( noiseResolution ) );
				const noiseTexel = sampleNoise( noiseUv ).toVar();

				const x = sin( noiseTexel.element( this.index.mod( 4 ).mul( 2 ).mul( PI ) ) );
				const y = cos( noiseTexel.element( this.index.mod( 4 ).mul( 2 ).mul( PI ) ) );

				const noiseVec = vec2( x, y );
				const rotationMatrix = mat2( noiseVec.x, noiseVec.y.negate(), noiseVec.x, noiseVec.y );

				const totalWeight = float( 1.0 ).toVar();
				const denoised = vec3( texel.rgb ).toVar();

				Loop( { start: int( 0 ), end: int( 16 ), type: 'int', condition: '<' }, ( { i } ) => {

					const sampleDir = this._sampleVectors.element( i );
					const offset = rotationMatrix.mul( sampleDir.xy.mul( float( 1.0 ).add( sampleDir.z.mul( this.radius.sub( 1 ) ) ) ) ).div( this._resolution );
					const sampleUv = uvNode.add( offset );

					const sampleResult = denoiseSample( center, viewNormal, viewPosition, sampleUv );

					denoised.addAssign( sampleResult.xyz );
					totalWeight.addAssign( sampleResult.w );

				} );

				If( totalWeight.greaterThan( float( 0 ) ), () => {

					denoised.divAssign( totalWeight );

				} );

				result.assign( vec4( denoised, texel.a ) );

			} );

			return result;

		}/*, { uv: 'vec2', return: 'vec4' }*/ );

		const output = Fn( () => {

			return denoise( uvNode );

		} );

		const outputNode = output();

		return outputNode;

	}
```
</details>

### `sampleTexture(uv: any): any`

**Parameters:**

- **`uv`** `any`

**Returns:** `any`

**Calls:**

- `this.textureNode.sample`

<details><summary>Code</summary>

```typescript
( uv ) => this.textureNode.sample( uv )
```
</details>

### `sampleDepth(uv: any): any`

**Parameters:**

- **`uv`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
( uv ) => this.depthNode.sample( uv ).x
```
</details>

### `sampleNormal(uv: any): any`

**Parameters:**

- **`uv`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
( uv ) => ( this.normalNode !== null ) ? this.normalNode.sample( uv ).rgb.normalize() : getNormalFromDepth( uv, this.depthNode.value, this._cameraProjectionMatrixInverse )
```
</details>

### `sampleNoise(uv: any): any`

**Parameters:**

- **`uv`** `any`

**Returns:** `any`

**Calls:**

- `this.noiseNode.sample`

<details><summary>Code</summary>

```typescript
( uv ) => this.noiseNode.sample( uv )
```
</details>

### `generateDenoiseSamples(numSamples: number, numRings: number, radiusExponent: number): Vector3[]`

**JSDoc:**
```typescript
/**
 * Generates denoise samples based on the given parameters.
 *
 * @param {number} numSamples - The number of samples.
 * @param {number} numRings - The number of rings.
 * @param {number} radiusExponent - The radius exponent.
 * @return {Array<Vector3>} The denoise samples.
 */
```

**Parameters:**

- **`numSamples`** `number`
- **`numRings`** `number`
- **`radiusExponent`** `number`

**Returns:** `Vector3[]`

**Calls:**

- `Math.pow`
- `samples.push`
- `Math.cos`
- `Math.sin`

<details><summary>Code</summary>

```typescript
function generateDenoiseSamples( numSamples, numRings, radiusExponent ) {

	const samples = [];

	for ( let i = 0; i < numSamples; i ++ ) {

		const angle = 2 * Math.PI * numRings * i / numSamples;
		const radius = Math.pow( i / ( numSamples - 1 ), radiusExponent );
		samples.push( new Vector3( Math.cos( angle ), Math.sin( angle ), radius ) );

	}

	return samples;

}
```
</details>

### `generateDefaultNoise(size: number): DataTexture`

**JSDoc:**
```typescript
/**
 * Generates a default noise texture for the given size.
 *
 * @param {number} [size=64] - The texture size.
 * @return {DataTexture} The generated noise texture.
 */
```

**Parameters:**

- **`size`** `number`

**Returns:** `DataTexture`

**Calls:**

- `simplex.noise`

<details><summary>Code</summary>

```typescript
function generateDefaultNoise( size = 64 ) {

	const simplex = new SimplexNoise();

	const arraySize = size * size * 4;
	const data = new Uint8Array( arraySize );

	for ( let i = 0; i < size; i ++ ) {

		for ( let j = 0; j < size; j ++ ) {

			const x = i;
			const y = j;

			data[ ( i * size + j ) * 4 ] = ( simplex.noise( x, y ) * 0.5 + 0.5 ) * 255;
			data[ ( i * size + j ) * 4 + 1 ] = ( simplex.noise( x + size, y ) * 0.5 + 0.5 ) * 255;
			data[ ( i * size + j ) * 4 + 2 ] = ( simplex.noise( x, y + size ) * 0.5 + 0.5 ) * 255;
			data[ ( i * size + j ) * 4 + 3 ] = ( simplex.noise( x + size, y + size ) * 0.5 + 0.5 ) * 255;

		}

	}

	const noiseTexture = new DataTexture( data, size, size );
	noiseTexture.wrapS = RepeatWrapping;
	noiseTexture.wrapT = RepeatWrapping;
	noiseTexture.needsUpdate = true;

	return noiseTexture;

}
```
</details>

### `denoise(node: Node, depthNode: any, normalNode: any, camera: Camera): DenoiseNode`

**Parameters:**

- **`node`** `Node`
- **`depthNode`** `any`
- **`normalNode`** `any`
- **`camera`** `Camera`

**Returns:** `DenoiseNode`

**Calls:**

- `nodeObject (from three/tsl)`

<details><summary>Code</summary>

```typescript
( node, depthNode, normalNode, camera ) => nodeObject( new DenoiseNode( convertToTexture( node ), nodeObject( depthNode ), nodeObject( normalNode ), camera ) )
```
</details>


---

## Classes

### `DenoiseNode`

<details><summary>Class Code</summary>

```ts
class DenoiseNode extends TempNode {

	static get type() {

		return 'DenoiseNode';

	}

	/**
	 * Constructs a new denoise node.
	 *
	 * @param {TextureNode} textureNode - The texture node that represents the input of the effect (e.g. AO).
	 * @param {Node<float>} depthNode - A node that represents the scene's depth.
	 * @param {?Node<vec3>} normalNode - A node that represents the scene's normals.
	 * @param {Camera} camera - The camera the scene is rendered with.
	 */
	constructor( textureNode, depthNode, normalNode, camera ) {

		super( 'vec4' );

		/**
		 * The texture node that represents the input of the effect (e.g. AO).
		 *
		 * @type {TextureNode}
		 */
		this.textureNode = textureNode;

		/**
		 * A node that represents the scene's depth.
		 *
		 * @type {Node<float>}
		 */
		this.depthNode = depthNode;

		/**
		 * A node that represents the scene's normals. If no normals are passed to the
		 * constructor (because MRT is not available), normals can be automatically
		 * reconstructed from depth values in the shader.
		 *
		 * @type {?Node<vec3>}
		 */
		this.normalNode = normalNode;

		/**
		 * The node represents the internal noise texture.
		 *
		 * @type {TextureNode}
		 */
		this.noiseNode = texture( generateDefaultNoise() );

		/**
		 * The luma Phi value.
		 *
		 * @type {UniformNode<float>}
		 */
		this.lumaPhi = uniform( 5 );

		/**
		 * The depth Phi value.
		 *
		 * @type {UniformNode<float>}
		 */
		this.depthPhi = uniform( 5 );

		/**
		 * The normal Phi value.
		 *
		 * @type {UniformNode<float>}
		 */
		this.normalPhi = uniform( 5 );

		/**
		 * The radius.
		 *
		 * @type {UniformNode<float>}
		 */
		this.radius = uniform( 5 );

		/**
		 * The index.
		 *
		 * @type {UniformNode<float>}
		 */
		this.index = uniform( 0 );

		/**
		 * The `updateBeforeType` is set to `NodeUpdateType.FRAME` since the node updates
		 * its internal uniforms once per frame in `updateBefore()`.
		 *
		 * @type {string}
		 * @default 'frame'
		 */
		this.updateBeforeType = NodeUpdateType.FRAME;

		/**
		 * The resolution of the effect.
		 *
		 * @private
		 * @type {UniformNode<vec2>}
		 */
		this._resolution = uniform( new Vector2() );

		/**
		 * An array of sample vectors.
		 *
		 * @private
		 * @type {UniformArrayNode<vec3>}
		 */
		this._sampleVectors = uniformArray( generateDenoiseSamples( 16, 2, 1 ) );

		/**
		 * Represents the inverse projection matrix of the scene's camera.
		 *
		 * @private
		 * @type {UniformNode<mat4>}
		 */
		this._cameraProjectionMatrixInverse = uniform( camera.projectionMatrixInverse );

	}

	/**
	 * This method is used to update internal uniforms once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
	updateBefore() {

		const map = this.textureNode.value;

		this._resolution.value.set( map.image.width, map.image.height );

	}

	/**
	 * This method is used to setup the effect's TSL code.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {ShaderCallNodeInternal}
	 */
	setup( /* builder */ ) {

		const uvNode = uv();

		const sampleTexture = ( uv ) => this.textureNode.sample( uv );
		const sampleDepth = ( uv ) => this.depthNode.sample( uv ).x;
		const sampleNormal = ( uv ) => ( this.normalNode !== null ) ? this.normalNode.sample( uv ).rgb.normalize() : getNormalFromDepth( uv, this.depthNode.value, this._cameraProjectionMatrixInverse );
		const sampleNoise = ( uv ) => this.noiseNode.sample( uv );

		const denoiseSample = Fn( ( [ center, viewNormal, viewPosition, sampleUv ] ) => {

			const texel = sampleTexture( sampleUv ).toVar();
			const depth = sampleDepth( sampleUv ).toVar();
			const normal = sampleNormal( sampleUv ).toVar();
			const neighborColor = texel.rgb;
			const viewPos = getViewPosition( sampleUv, depth, this._cameraProjectionMatrixInverse ).toVar();

			const normalDiff = dot( viewNormal, normal ).toVar();
			const normalSimilarity = pow( max( normalDiff, 0 ), this.normalPhi ).toVar();
			const lumaDiff = abs( luminance( neighborColor ).sub( luminance( center ) ) ).toVar();
			const lumaSimilarity = max( float( 1.0 ).sub( lumaDiff.div( this.lumaPhi ) ), 0 ).toVar();
			const depthDiff = abs( dot( viewPosition.sub( viewPos ), viewNormal ) ).toVar();
			const depthSimilarity = max( float( 1.0 ).sub( depthDiff.div( this.depthPhi ) ), 0 );
			const w = lumaSimilarity.mul( depthSimilarity ).mul( normalSimilarity );

			return vec4( neighborColor.mul( w ), w );

		} );

		const denoise = Fn( ( [ uvNode ] ) => {

			const depth = sampleDepth( uvNode ).toVar();
			const viewNormal = sampleNormal( uvNode ).toVar();

			const texel = sampleTexture( uvNode ).toVar();
			const result = property( 'vec4' );

			If( depth.greaterThanEqual( 1.0 ).or( dot( viewNormal, viewNormal ).equal( 0.0 ) ), () => {

				result.assign( texel );

			} ).Else( () => {

				const center = vec3( texel.rgb );

				const viewPosition = getViewPosition( uvNode, depth, this._cameraProjectionMatrixInverse ).toConst();

				const noiseResolution = textureSize( this.noiseNode, 0 );
				let noiseUv = vec2( uvNode.x, uvNode.y.oneMinus() );
				noiseUv = noiseUv.mul( this._resolution.div( noiseResolution ) );
				const noiseTexel = sampleNoise( noiseUv ).toVar();

				const x = sin( noiseTexel.element( this.index.mod( 4 ).mul( 2 ).mul( PI ) ) );
				const y = cos( noiseTexel.element( this.index.mod( 4 ).mul( 2 ).mul( PI ) ) );

				const noiseVec = vec2( x, y );
				const rotationMatrix = mat2( noiseVec.x, noiseVec.y.negate(), noiseVec.x, noiseVec.y );

				const totalWeight = float( 1.0 ).toVar();
				const denoised = vec3( texel.rgb ).toVar();

				Loop( { start: int( 0 ), end: int( 16 ), type: 'int', condition: '<' }, ( { i } ) => {

					const sampleDir = this._sampleVectors.element( i );
					const offset = rotationMatrix.mul( sampleDir.xy.mul( float( 1.0 ).add( sampleDir.z.mul( this.radius.sub( 1 ) ) ) ) ).div( this._resolution );
					const sampleUv = uvNode.add( offset );

					const sampleResult = denoiseSample( center, viewNormal, viewPosition, sampleUv );

					denoised.addAssign( sampleResult.xyz );
					totalWeight.addAssign( sampleResult.w );

				} );

				If( totalWeight.greaterThan( float( 0 ) ), () => {

					denoised.divAssign( totalWeight );

				} );

				result.assign( vec4( denoised, texel.a ) );

			} );

			return result;

		}/*, { uv: 'vec2', return: 'vec4' }*/ );

		const output = Fn( () => {

			return denoise( uvNode );

		} );

		const outputNode = output();

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

		this._resolution.value.set( map.image.width, map.image.height );

	}
```
</details>

##### `setup(): ShaderCallNodeInternal`

<details><summary>Code</summary>

```ts
setup( /* builder */ ) {

		const uvNode = uv();

		const sampleTexture = ( uv ) => this.textureNode.sample( uv );
		const sampleDepth = ( uv ) => this.depthNode.sample( uv ).x;
		const sampleNormal = ( uv ) => ( this.normalNode !== null ) ? this.normalNode.sample( uv ).rgb.normalize() : getNormalFromDepth( uv, this.depthNode.value, this._cameraProjectionMatrixInverse );
		const sampleNoise = ( uv ) => this.noiseNode.sample( uv );

		const denoiseSample = Fn( ( [ center, viewNormal, viewPosition, sampleUv ] ) => {

			const texel = sampleTexture( sampleUv ).toVar();
			const depth = sampleDepth( sampleUv ).toVar();
			const normal = sampleNormal( sampleUv ).toVar();
			const neighborColor = texel.rgb;
			const viewPos = getViewPosition( sampleUv, depth, this._cameraProjectionMatrixInverse ).toVar();

			const normalDiff = dot( viewNormal, normal ).toVar();
			const normalSimilarity = pow( max( normalDiff, 0 ), this.normalPhi ).toVar();
			const lumaDiff = abs( luminance( neighborColor ).sub( luminance( center ) ) ).toVar();
			const lumaSimilarity = max( float( 1.0 ).sub( lumaDiff.div( this.lumaPhi ) ), 0 ).toVar();
			const depthDiff = abs( dot( viewPosition.sub( viewPos ), viewNormal ) ).toVar();
			const depthSimilarity = max( float( 1.0 ).sub( depthDiff.div( this.depthPhi ) ), 0 );
			const w = lumaSimilarity.mul( depthSimilarity ).mul( normalSimilarity );

			return vec4( neighborColor.mul( w ), w );

		} );

		const denoise = Fn( ( [ uvNode ] ) => {

			const depth = sampleDepth( uvNode ).toVar();
			const viewNormal = sampleNormal( uvNode ).toVar();

			const texel = sampleTexture( uvNode ).toVar();
			const result = property( 'vec4' );

			If( depth.greaterThanEqual( 1.0 ).or( dot( viewNormal, viewNormal ).equal( 0.0 ) ), () => {

				result.assign( texel );

			} ).Else( () => {

				const center = vec3( texel.rgb );

				const viewPosition = getViewPosition( uvNode, depth, this._cameraProjectionMatrixInverse ).toConst();

				const noiseResolution = textureSize( this.noiseNode, 0 );
				let noiseUv = vec2( uvNode.x, uvNode.y.oneMinus() );
				noiseUv = noiseUv.mul( this._resolution.div( noiseResolution ) );
				const noiseTexel = sampleNoise( noiseUv ).toVar();

				const x = sin( noiseTexel.element( this.index.mod( 4 ).mul( 2 ).mul( PI ) ) );
				const y = cos( noiseTexel.element( this.index.mod( 4 ).mul( 2 ).mul( PI ) ) );

				const noiseVec = vec2( x, y );
				const rotationMatrix = mat2( noiseVec.x, noiseVec.y.negate(), noiseVec.x, noiseVec.y );

				const totalWeight = float( 1.0 ).toVar();
				const denoised = vec3( texel.rgb ).toVar();

				Loop( { start: int( 0 ), end: int( 16 ), type: 'int', condition: '<' }, ( { i } ) => {

					const sampleDir = this._sampleVectors.element( i );
					const offset = rotationMatrix.mul( sampleDir.xy.mul( float( 1.0 ).add( sampleDir.z.mul( this.radius.sub( 1 ) ) ) ) ).div( this._resolution );
					const sampleUv = uvNode.add( offset );

					const sampleResult = denoiseSample( center, viewNormal, viewPosition, sampleUv );

					denoised.addAssign( sampleResult.xyz );
					totalWeight.addAssign( sampleResult.w );

				} );

				If( totalWeight.greaterThan( float( 0 ) ), () => {

					denoised.divAssign( totalWeight );

				} );

				result.assign( vec4( denoised, texel.a ) );

			} );

			return result;

		}/*, { uv: 'vec2', return: 'vec4' }*/ );

		const output = Fn( () => {

			return denoise( uvNode );

		} );

		const outputNode = output();

		return outputNode;

	}
```
</details>


---