[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `BatchNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 17 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/BatchNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `normalLocal` | `./Normal.js` |
| `positionLocal` | `./Position.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `vec3` | `../tsl/TSLBase.js` |
| `mat3` | `../tsl/TSLBase.js` |
| `mat4` | `../tsl/TSLBase.js` |
| `int` | `../tsl/TSLBase.js` |
| `ivec2` | `../tsl/TSLBase.js` |
| `float` | `../tsl/TSLBase.js` |
| `Fn` | `../tsl/TSLBase.js` |
| `textureLoad` | `./TextureNode.js` |
| `textureSize` | `./TextureSizeNode.js` |
| `tangentLocal` | `./Tangent.js` |
| `instanceIndex` | `../core/IndexNode.js` |
| `drawIndex` | `../core/IndexNode.js` |
| `varyingProperty` | `../core/PropertyNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `matricesTexture` | `any` | let/var | `this.batchMesh._matricesTexture` | ✗ |
| `colorsTexture` | `any` | let/var | `this.batchMesh._colorsTexture` | ✗ |
| `j` | `any` | let/var | `id` | ✗ |
| `batchingNormal` | `any` | let/var | `bm.mul( transformedNormal ).xyz` | ✗ |


---

## Functions

### `BatchNode.setup(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Setups the internal buffers and nodes and assigns the transformed vertex data
	 * to predefined node variables for accumulation. That follows the same patterns
	 * like with morph and skinning nodes.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `builder.getDrawIndex`
- `Fn( ( [ id ] ) => {

			const size = int( textureSize( textureLoad( this.batchMesh._indirectTexture ), 0 ).x );
			const x = int( id ).mod( size );
			const y = int( id ).div( size );
			return textureLoad( this.batchMesh._indirectTexture, ivec2( x, y ) ).x;

		} ).setLayout`
- `getIndirectIndex`
- `int (from ../tsl/TSLBase.js)`
- `textureSize (from ./TextureSizeNode.js)`
- `textureLoad (from ./TextureNode.js)`
- `float( indirectId ).mul( 4 ).toInt().toVar`
- `j.mod`
- `j.div`
- `mat4 (from ../tsl/TSLBase.js)`
- `ivec2 (from ../tsl/TSLBase.js)`
- `x.add`
- `Fn( ( [ id ] ) => {

				const size = int( textureSize( textureLoad( colorsTexture ), 0 ).x );
				const j = id;
				const x = j.mod( size );
				const y = j.div( size );
				return textureLoad( colorsTexture, ivec2( x, y ) ).rgb;

			} ).setLayout`
- `getBatchingColor`
- `varyingProperty( 'vec3', 'vBatchColor' ).assign`
- `mat3 (from ../tsl/TSLBase.js)`
- `positionLocal.assign`
- `batchingMatrix.mul`
- `normalLocal.div`
- `vec3 (from ../tsl/TSLBase.js)`
- `bm[ 0 ].dot`
- `bm[ 1 ].dot`
- `bm[ 2 ].dot`
- `bm.mul`
- `normalLocal.assign`
- `builder.hasGeometryAttribute`
- `tangentLocal.mulAssign`

<details><summary>Code</summary>

```typescript
setup( builder ) {

		if ( this.batchingIdNode === null ) {

			if ( builder.getDrawIndex() === null ) {

				this.batchingIdNode = instanceIndex;

			} else {

				this.batchingIdNode = drawIndex;

			}

		}

		const getIndirectIndex = Fn( ( [ id ] ) => {

			const size = int( textureSize( textureLoad( this.batchMesh._indirectTexture ), 0 ).x );
			const x = int( id ).mod( size );
			const y = int( id ).div( size );
			return textureLoad( this.batchMesh._indirectTexture, ivec2( x, y ) ).x;

		} ).setLayout( {
			name: 'getIndirectIndex',
			type: 'uint',
			inputs: [
				{ name: 'id', type: 'int' }
			]
		} );

		const indirectId = getIndirectIndex( int( this.batchingIdNode ) );

		const matricesTexture = this.batchMesh._matricesTexture;

		const size = int( textureSize( textureLoad( matricesTexture ), 0 ).x );
		const j = float( indirectId ).mul( 4 ).toInt().toVar();

		const x = j.mod( size );
		const y = j.div( size );
		const batchingMatrix = mat4(
			textureLoad( matricesTexture, ivec2( x, y ) ),
			textureLoad( matricesTexture, ivec2( x.add( 1 ), y ) ),
			textureLoad( matricesTexture, ivec2( x.add( 2 ), y ) ),
			textureLoad( matricesTexture, ivec2( x.add( 3 ), y ) )
		);


		const colorsTexture = this.batchMesh._colorsTexture;

		if ( colorsTexture !== null ) {

			const getBatchingColor = Fn( ( [ id ] ) => {

				const size = int( textureSize( textureLoad( colorsTexture ), 0 ).x );
				const j = id;
				const x = j.mod( size );
				const y = j.div( size );
				return textureLoad( colorsTexture, ivec2( x, y ) ).rgb;

			} ).setLayout( {
				name: 'getBatchingColor',
				type: 'vec3',
				inputs: [
					{ name: 'id', type: 'int' }
				]
			} );

			const color = getBatchingColor( indirectId );

			varyingProperty( 'vec3', 'vBatchColor' ).assign( color );

		}

		const bm = mat3( batchingMatrix );

		positionLocal.assign( batchingMatrix.mul( positionLocal ) );

		const transformedNormal = normalLocal.div( vec3( bm[ 0 ].dot( bm[ 0 ] ), bm[ 1 ].dot( bm[ 1 ] ), bm[ 2 ].dot( bm[ 2 ] ) ) );

		const batchingNormal = bm.mul( transformedNormal ).xyz;

		normalLocal.assign( batchingNormal );

		if ( builder.hasGeometryAttribute( 'tangent' ) ) {

			tangentLocal.mulAssign( bm );

		}

	}
```
</details>


---

## Classes

### `BatchNode`

<details><summary>Class Code</summary>

```ts
class BatchNode extends Node {

	static get type() {

		return 'BatchNode';

	}

	/**
	 * Constructs a new batch node.
	 *
	 * @param {BatchedMesh} batchMesh - A reference to batched mesh.
	 */
	constructor( batchMesh ) {

		super( 'void' );

		/**
		 * A reference to batched mesh.
		 *
		 * @type {BatchedMesh}
		 */
		this.batchMesh = batchMesh;

		/**
		 * The batching index node.
		 *
		 * @type {?IndexNode}
		 * @default null
		 */
		this.batchingIdNode = null;

	}

	/**
	 * Setups the internal buffers and nodes and assigns the transformed vertex data
	 * to predefined node variables for accumulation. That follows the same patterns
	 * like with morph and skinning nodes.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	setup( builder ) {

		if ( this.batchingIdNode === null ) {

			if ( builder.getDrawIndex() === null ) {

				this.batchingIdNode = instanceIndex;

			} else {

				this.batchingIdNode = drawIndex;

			}

		}

		const getIndirectIndex = Fn( ( [ id ] ) => {

			const size = int( textureSize( textureLoad( this.batchMesh._indirectTexture ), 0 ).x );
			const x = int( id ).mod( size );
			const y = int( id ).div( size );
			return textureLoad( this.batchMesh._indirectTexture, ivec2( x, y ) ).x;

		} ).setLayout( {
			name: 'getIndirectIndex',
			type: 'uint',
			inputs: [
				{ name: 'id', type: 'int' }
			]
		} );

		const indirectId = getIndirectIndex( int( this.batchingIdNode ) );

		const matricesTexture = this.batchMesh._matricesTexture;

		const size = int( textureSize( textureLoad( matricesTexture ), 0 ).x );
		const j = float( indirectId ).mul( 4 ).toInt().toVar();

		const x = j.mod( size );
		const y = j.div( size );
		const batchingMatrix = mat4(
			textureLoad( matricesTexture, ivec2( x, y ) ),
			textureLoad( matricesTexture, ivec2( x.add( 1 ), y ) ),
			textureLoad( matricesTexture, ivec2( x.add( 2 ), y ) ),
			textureLoad( matricesTexture, ivec2( x.add( 3 ), y ) )
		);


		const colorsTexture = this.batchMesh._colorsTexture;

		if ( colorsTexture !== null ) {

			const getBatchingColor = Fn( ( [ id ] ) => {

				const size = int( textureSize( textureLoad( colorsTexture ), 0 ).x );
				const j = id;
				const x = j.mod( size );
				const y = j.div( size );
				return textureLoad( colorsTexture, ivec2( x, y ) ).rgb;

			} ).setLayout( {
				name: 'getBatchingColor',
				type: 'vec3',
				inputs: [
					{ name: 'id', type: 'int' }
				]
			} );

			const color = getBatchingColor( indirectId );

			varyingProperty( 'vec3', 'vBatchColor' ).assign( color );

		}

		const bm = mat3( batchingMatrix );

		positionLocal.assign( batchingMatrix.mul( positionLocal ) );

		const transformedNormal = normalLocal.div( vec3( bm[ 0 ].dot( bm[ 0 ] ), bm[ 1 ].dot( bm[ 1 ] ), bm[ 2 ].dot( bm[ 2 ] ) ) );

		const batchingNormal = bm.mul( transformedNormal ).xyz;

		normalLocal.assign( batchingNormal );

		if ( builder.hasGeometryAttribute( 'tangent' ) ) {

			tangentLocal.mulAssign( bm );

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

		if ( this.batchingIdNode === null ) {

			if ( builder.getDrawIndex() === null ) {

				this.batchingIdNode = instanceIndex;

			} else {

				this.batchingIdNode = drawIndex;

			}

		}

		const getIndirectIndex = Fn( ( [ id ] ) => {

			const size = int( textureSize( textureLoad( this.batchMesh._indirectTexture ), 0 ).x );
			const x = int( id ).mod( size );
			const y = int( id ).div( size );
			return textureLoad( this.batchMesh._indirectTexture, ivec2( x, y ) ).x;

		} ).setLayout( {
			name: 'getIndirectIndex',
			type: 'uint',
			inputs: [
				{ name: 'id', type: 'int' }
			]
		} );

		const indirectId = getIndirectIndex( int( this.batchingIdNode ) );

		const matricesTexture = this.batchMesh._matricesTexture;

		const size = int( textureSize( textureLoad( matricesTexture ), 0 ).x );
		const j = float( indirectId ).mul( 4 ).toInt().toVar();

		const x = j.mod( size );
		const y = j.div( size );
		const batchingMatrix = mat4(
			textureLoad( matricesTexture, ivec2( x, y ) ),
			textureLoad( matricesTexture, ivec2( x.add( 1 ), y ) ),
			textureLoad( matricesTexture, ivec2( x.add( 2 ), y ) ),
			textureLoad( matricesTexture, ivec2( x.add( 3 ), y ) )
		);


		const colorsTexture = this.batchMesh._colorsTexture;

		if ( colorsTexture !== null ) {

			const getBatchingColor = Fn( ( [ id ] ) => {

				const size = int( textureSize( textureLoad( colorsTexture ), 0 ).x );
				const j = id;
				const x = j.mod( size );
				const y = j.div( size );
				return textureLoad( colorsTexture, ivec2( x, y ) ).rgb;

			} ).setLayout( {
				name: 'getBatchingColor',
				type: 'vec3',
				inputs: [
					{ name: 'id', type: 'int' }
				]
			} );

			const color = getBatchingColor( indirectId );

			varyingProperty( 'vec3', 'vBatchColor' ).assign( color );

		}

		const bm = mat3( batchingMatrix );

		positionLocal.assign( batchingMatrix.mul( positionLocal ) );

		const transformedNormal = normalLocal.div( vec3( bm[ 0 ].dot( bm[ 0 ] ), bm[ 1 ].dot( bm[ 1 ] ), bm[ 2 ].dot( bm[ 2 ] ) ) );

		const batchingNormal = bm.mul( transformedNormal ).xyz;

		normalLocal.assign( batchingNormal );

		if ( builder.hasGeometryAttribute( 'tangent' ) ) {

			tangentLocal.mulAssign( bm );

		}

	}
```
</details>


---