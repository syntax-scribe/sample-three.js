[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `MorphNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 20 |
| 📊 Variables & Constants | 28 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/MorphNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `float` | `../tsl/TSLBase.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `ivec2` | `../tsl/TSLBase.js` |
| `int` | `../tsl/TSLBase.js` |
| `If` | `../tsl/TSLBase.js` |
| `uniform` | `../core/UniformNode.js` |
| `reference` | `./ReferenceNode.js` |
| `positionLocal` | `./Position.js` |
| `normalLocal` | `./Normal.js` |
| `textureLoad` | `./TextureNode.js` |
| `instanceIndex` | `../core/IndexNode.js` |
| `vertexIndex` | `../core/IndexNode.js` |
| `Loop` | `../utils/LoopNode.js` |
| `DataArrayTexture` | `../../textures/DataArrayTexture.js` |
| `Vector2` | `../../math/Vector2.js` |
| `Vector4` | `../../math/Vector4.js` |
| `FloatType` | `../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_morphTextures` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `_morphVec4` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `bufferAttrib` | `any` | let/var | `textureLoad( bufferMap, ivec2( x, y ) ).depth( depth ).xyz` | ✗ |
| `hasMorphPosition` | `boolean` | let/var | `geometry.morphAttributes.position !== undefined` | ✗ |
| `hasMorphNormals` | `boolean` | let/var | `geometry.morphAttributes.normal !== undefined` | ✗ |
| `hasMorphColors` | `boolean` | let/var | `geometry.morphAttributes.color !== undefined` | ✗ |
| `morphAttribute` | `any` | let/var | `geometry.morphAttributes.position \|\| geometry.morphAttributes.normal \|\| g...` | ✗ |
| `morphTargetsCount` | `any` | let/var | `( morphAttribute !== undefined ) ? morphAttribute.length : 0` | ✗ |
| `morphTargets` | `any` | let/var | `geometry.morphAttributes.position \|\| []` | ✗ |
| `morphNormals` | `any` | let/var | `geometry.morphAttributes.normal \|\| []` | ✗ |
| `morphColors` | `any` | let/var | `geometry.morphAttributes.color \|\| []` | ✗ |
| `vertexDataCount` | `number` | let/var | `0` | ✗ |
| `width` | `number` | let/var | `geometry.attributes.position.count * vertexDataCount` | ✗ |
| `height` | `number` | let/var | `1` | ✗ |
| `maxTextureSize` | `4096` | let/var | `4096` | ✗ |
| `buffer` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( width * height * 4 * morphTargetsCount )` | ✗ |
| `bufferTexture` | `DataArrayTexture` | let/var | `new DataArrayTexture( buffer, width, height, morphTargetsCount )` | ✗ |
| `vertexDataStride` | `number` | let/var | `vertexDataCount * 4` | ✗ |
| `morphTarget` | `any` | let/var | `morphTargets[ i ]` | ✗ |
| `morphNormal` | `any` | let/var | `morphNormals[ i ]` | ✗ |
| `morphColor` | `any` | let/var | `morphColors[ i ]` | ✗ |
| `offset` | `number` | let/var | `width * height * 4 * i` | ✗ |
| `stride` | `number` | let/var | `j * vertexDataStride` | ✗ |
| `hasMorphPosition` | `boolean` | let/var | `geometry.morphAttributes.position !== undefined` | ✗ |
| `hasMorphNormals` | `boolean` | let/var | `geometry.hasAttribute( 'normal' ) && geometry.morphAttributes.normal !== unde...` | ✗ |
| `morphAttribute` | `any` | let/var | `geometry.morphAttributes.position \|\| geometry.morphAttributes.normal \|\| g...` | ✗ |
| `morphTargetsCount` | `any` | let/var | `( morphAttribute !== undefined ) ? morphAttribute.length : 0` | ✗ |
| `morphBaseInfluence` | `UniformNode<any>` | let/var | `this.morphBaseInfluence` | ✗ |


---

## Functions

### `getEntry(geometry: any): any`

**Parameters:**

- **`geometry`** `any`

**Returns:** `any`

**Calls:**

- `_morphTextures.get`
- `entry.texture.dispose`
- `Math.ceil`
- `_morphVec4.fromBufferAttribute`
- `_morphTextures.set`
- `bufferTexture.dispose`
- `_morphTextures.delete`
- `geometry.removeEventListener`
- `geometry.addEventListener`

**Internal Comments:**
```
// instead of using attributes, the WebGL 2 code path encodes morph targets (x2)
// into an array of data textures. Each layer represents a single morph target. (x2)
// fill buffer (x2)
```

<details><summary>Code</summary>

```typescript
function getEntry( geometry ) {

	const hasMorphPosition = geometry.morphAttributes.position !== undefined;
	const hasMorphNormals = geometry.morphAttributes.normal !== undefined;
	const hasMorphColors = geometry.morphAttributes.color !== undefined;

	// instead of using attributes, the WebGL 2 code path encodes morph targets
	// into an array of data textures. Each layer represents a single morph target.

	const morphAttribute = geometry.morphAttributes.position || geometry.morphAttributes.normal || geometry.morphAttributes.color;
	const morphTargetsCount = ( morphAttribute !== undefined ) ? morphAttribute.length : 0;

	let entry = _morphTextures.get( geometry );

	if ( entry === undefined || entry.count !== morphTargetsCount ) {

		if ( entry !== undefined ) entry.texture.dispose();

		const morphTargets = geometry.morphAttributes.position || [];
		const morphNormals = geometry.morphAttributes.normal || [];
		const morphColors = geometry.morphAttributes.color || [];

		let vertexDataCount = 0;

		if ( hasMorphPosition === true ) vertexDataCount = 1;
		if ( hasMorphNormals === true ) vertexDataCount = 2;
		if ( hasMorphColors === true ) vertexDataCount = 3;

		let width = geometry.attributes.position.count * vertexDataCount;
		let height = 1;

		const maxTextureSize = 4096; // @TODO: Use 'capabilities.maxTextureSize'

		if ( width > maxTextureSize ) {

			height = Math.ceil( width / maxTextureSize );
			width = maxTextureSize;

		}

		const buffer = new Float32Array( width * height * 4 * morphTargetsCount );

		const bufferTexture = new DataArrayTexture( buffer, width, height, morphTargetsCount );
		bufferTexture.type = FloatType;
		bufferTexture.needsUpdate = true;

		// fill buffer

		const vertexDataStride = vertexDataCount * 4;

		for ( let i = 0; i < morphTargetsCount; i ++ ) {

			const morphTarget = morphTargets[ i ];
			const morphNormal = morphNormals[ i ];
			const morphColor = morphColors[ i ];

			const offset = width * height * 4 * i;

			for ( let j = 0; j < morphTarget.count; j ++ ) {

				const stride = j * vertexDataStride;

				if ( hasMorphPosition === true ) {

					_morphVec4.fromBufferAttribute( morphTarget, j );

					buffer[ offset + stride + 0 ] = _morphVec4.x;
					buffer[ offset + stride + 1 ] = _morphVec4.y;
					buffer[ offset + stride + 2 ] = _morphVec4.z;
					buffer[ offset + stride + 3 ] = 0;

				}

				if ( hasMorphNormals === true ) {

					_morphVec4.fromBufferAttribute( morphNormal, j );

					buffer[ offset + stride + 4 ] = _morphVec4.x;
					buffer[ offset + stride + 5 ] = _morphVec4.y;
					buffer[ offset + stride + 6 ] = _morphVec4.z;
					buffer[ offset + stride + 7 ] = 0;

				}

				if ( hasMorphColors === true ) {

					_morphVec4.fromBufferAttribute( morphColor, j );

					buffer[ offset + stride + 8 ] = _morphVec4.x;
					buffer[ offset + stride + 9 ] = _morphVec4.y;
					buffer[ offset + stride + 10 ] = _morphVec4.z;
					buffer[ offset + stride + 11 ] = ( morphColor.itemSize === 4 ) ? _morphVec4.w : 1;

				}

			}

		}

		entry = {
			count: morphTargetsCount,
			texture: bufferTexture,
			stride: vertexDataCount,
			size: new Vector2( width, height )
		};

		_morphTextures.set( geometry, entry );

		function disposeTexture() {

			bufferTexture.dispose();

			_morphTextures.delete( geometry );

			geometry.removeEventListener( 'dispose', disposeTexture );

		}

		geometry.addEventListener( 'dispose', disposeTexture );

	}

	return entry;

}
```
</details>

### `disposeTexture(): void`

**Returns:** `void`

**Calls:**

- `bufferTexture.dispose`
- `_morphTextures.delete`
- `geometry.removeEventListener`

<details><summary>Code</summary>

```typescript
function disposeTexture() {

			bufferTexture.dispose();

			_morphTextures.delete( geometry );

			geometry.removeEventListener( 'dispose', disposeTexture );

		}
```
</details>

### `MorphNode.setup(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Setups the morph node by assigning the transformed vertex data to predefined node variables.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `geometry.hasAttribute`
- `getEntry`
- `positionLocal.mulAssign`
- `normalLocal.mulAssign`
- `int (from ../tsl/TSLBase.js)`
- `Loop (from ../utils/LoopNode.js)`
- `float( 0 ).toVar`
- `influence.assign`
- `textureLoad (from ./TextureNode.js)`
- `ivec2 (from ../tsl/TSLBase.js)`
- `int( i ).add`
- `reference( 'morphTargetInfluences', 'float' ).element( i ).toVar`
- `If (from ../tsl/TSLBase.js)`
- `influence.notEqual`
- `positionLocal.addAssign`
- `getMorph`
- `normalLocal.addAssign`

**Internal Comments:**
```
// nodes (x2)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const { geometry } = builder;

		const hasMorphPosition = geometry.morphAttributes.position !== undefined;
		const hasMorphNormals = geometry.hasAttribute( 'normal' ) && geometry.morphAttributes.normal !== undefined;

		const morphAttribute = geometry.morphAttributes.position || geometry.morphAttributes.normal || geometry.morphAttributes.color;
		const morphTargetsCount = ( morphAttribute !== undefined ) ? morphAttribute.length : 0;

		// nodes

		const { texture: bufferMap, stride, size } = getEntry( geometry );

		if ( hasMorphPosition === true ) positionLocal.mulAssign( this.morphBaseInfluence );
		if ( hasMorphNormals === true ) normalLocal.mulAssign( this.morphBaseInfluence );

		const width = int( size.width );

		Loop( morphTargetsCount, ( { i } ) => {

			const influence = float( 0 ).toVar();

			if ( this.mesh.count > 1 && ( this.mesh.morphTexture !== null && this.mesh.morphTexture !== undefined ) ) {

				influence.assign( textureLoad( this.mesh.morphTexture, ivec2( int( i ).add( 1 ), int( instanceIndex ) ) ).r );

			} else {

				influence.assign( reference( 'morphTargetInfluences', 'float' ).element( i ).toVar() );

			}

			If( influence.notEqual( 0 ), () => {

				if ( hasMorphPosition === true ) {

					positionLocal.addAssign( getMorph( {
						bufferMap,
						influence,
						stride,
						width,
						depth: i,
						offset: int( 0 )
					} ) );

				}

				if ( hasMorphNormals === true ) {

					normalLocal.addAssign( getMorph( {
						bufferMap,
						influence,
						stride,
						width,
						depth: i,
						offset: int( 1 )
					} ) );

				}

			} );

		} );

	}
```
</details>

### `MorphNode.update(): void`

**JSDoc:**
```typescript
/**
	 * Updates the state of the morphed mesh by updating the base influence.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
```

**Returns:** `void`

**Calls:**

- `this.mesh.morphTargetInfluences.reduce`

<details><summary>Code</summary>

```typescript
update( /*frame*/ ) {

		const morphBaseInfluence = this.morphBaseInfluence;

		if ( this.mesh.geometry.morphTargetsRelative ) {

			morphBaseInfluence.value = 1;

		} else {

			morphBaseInfluence.value = 1 - this.mesh.morphTargetInfluences.reduce( ( a, b ) => a + b, 0 );

		}

	}
```
</details>


---

## Classes

### `MorphNode`

<details><summary>Class Code</summary>

```ts
class MorphNode extends Node {

	static get type() {

		return 'MorphNode';

	}

	/**
	 * Constructs a new morph node.
	 *
	 * @param {Mesh} mesh - The mesh holding the morph targets.
	 */
	constructor( mesh ) {

		super( 'void' );

		/**
		 * The mesh holding the morph targets.
		 *
		 * @type {Mesh}
		 */
		this.mesh = mesh;

		/**
		 * A uniform node which represents the morph base influence value.
		 *
		 * @type {UniformNode<float>}
		 */
		this.morphBaseInfluence = uniform( 1 );

		/**
		 * The update type overwritten since morph nodes are updated per object.
		 *
		 * @type {string}
		 */
		this.updateType = NodeUpdateType.OBJECT;

	}

	/**
	 * Setups the morph node by assigning the transformed vertex data to predefined node variables.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	setup( builder ) {

		const { geometry } = builder;

		const hasMorphPosition = geometry.morphAttributes.position !== undefined;
		const hasMorphNormals = geometry.hasAttribute( 'normal' ) && geometry.morphAttributes.normal !== undefined;

		const morphAttribute = geometry.morphAttributes.position || geometry.morphAttributes.normal || geometry.morphAttributes.color;
		const morphTargetsCount = ( morphAttribute !== undefined ) ? morphAttribute.length : 0;

		// nodes

		const { texture: bufferMap, stride, size } = getEntry( geometry );

		if ( hasMorphPosition === true ) positionLocal.mulAssign( this.morphBaseInfluence );
		if ( hasMorphNormals === true ) normalLocal.mulAssign( this.morphBaseInfluence );

		const width = int( size.width );

		Loop( morphTargetsCount, ( { i } ) => {

			const influence = float( 0 ).toVar();

			if ( this.mesh.count > 1 && ( this.mesh.morphTexture !== null && this.mesh.morphTexture !== undefined ) ) {

				influence.assign( textureLoad( this.mesh.morphTexture, ivec2( int( i ).add( 1 ), int( instanceIndex ) ) ).r );

			} else {

				influence.assign( reference( 'morphTargetInfluences', 'float' ).element( i ).toVar() );

			}

			If( influence.notEqual( 0 ), () => {

				if ( hasMorphPosition === true ) {

					positionLocal.addAssign( getMorph( {
						bufferMap,
						influence,
						stride,
						width,
						depth: i,
						offset: int( 0 )
					} ) );

				}

				if ( hasMorphNormals === true ) {

					normalLocal.addAssign( getMorph( {
						bufferMap,
						influence,
						stride,
						width,
						depth: i,
						offset: int( 1 )
					} ) );

				}

			} );

		} );

	}

	/**
	 * Updates the state of the morphed mesh by updating the base influence.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
	update( /*frame*/ ) {

		const morphBaseInfluence = this.morphBaseInfluence;

		if ( this.mesh.geometry.morphTargetsRelative ) {

			morphBaseInfluence.value = 1;

		} else {

			morphBaseInfluence.value = 1 - this.mesh.morphTargetInfluences.reduce( ( a, b ) => a + b, 0 );

		}

	}

}
```
</details>

#### Methods

##### `setup(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const { geometry } = builder;

		const hasMorphPosition = geometry.morphAttributes.position !== undefined;
		const hasMorphNormals = geometry.hasAttribute( 'normal' ) && geometry.morphAttributes.normal !== undefined;

		const morphAttribute = geometry.morphAttributes.position || geometry.morphAttributes.normal || geometry.morphAttributes.color;
		const morphTargetsCount = ( morphAttribute !== undefined ) ? morphAttribute.length : 0;

		// nodes

		const { texture: bufferMap, stride, size } = getEntry( geometry );

		if ( hasMorphPosition === true ) positionLocal.mulAssign( this.morphBaseInfluence );
		if ( hasMorphNormals === true ) normalLocal.mulAssign( this.morphBaseInfluence );

		const width = int( size.width );

		Loop( morphTargetsCount, ( { i } ) => {

			const influence = float( 0 ).toVar();

			if ( this.mesh.count > 1 && ( this.mesh.morphTexture !== null && this.mesh.morphTexture !== undefined ) ) {

				influence.assign( textureLoad( this.mesh.morphTexture, ivec2( int( i ).add( 1 ), int( instanceIndex ) ) ).r );

			} else {

				influence.assign( reference( 'morphTargetInfluences', 'float' ).element( i ).toVar() );

			}

			If( influence.notEqual( 0 ), () => {

				if ( hasMorphPosition === true ) {

					positionLocal.addAssign( getMorph( {
						bufferMap,
						influence,
						stride,
						width,
						depth: i,
						offset: int( 0 )
					} ) );

				}

				if ( hasMorphNormals === true ) {

					normalLocal.addAssign( getMorph( {
						bufferMap,
						influence,
						stride,
						width,
						depth: i,
						offset: int( 1 )
					} ) );

				}

			} );

		} );

	}
```
</details>

##### `update(): void`

<details><summary>Code</summary>

```ts
update( /*frame*/ ) {

		const morphBaseInfluence = this.morphBaseInfluence;

		if ( this.mesh.geometry.morphTargetsRelative ) {

			morphBaseInfluence.value = 1;

		} else {

			morphBaseInfluence.value = 1 - this.mesh.morphTargetInfluences.reduce( ( a, b ) => a + b, 0 );

		}

	}
```
</details>


---