[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `SkinningNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 🧱 Classes | 1 |
| 📦 Imports | 17 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/SkinningNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Node` | `../core/Node.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `nodeObject` | `../tsl/TSLBase.js` |
| `attribute` | `../core/AttributeNode.js` |
| `reference` | `./ReferenceNode.js` |
| `referenceBuffer` | `./ReferenceNode.js` |
| `add` | `../math/OperatorNode.js` |
| `normalLocal` | `./Normal.js` |
| `positionLocal` | `./Position.js` |
| `positionPrevious` | `./Position.js` |
| `tangentLocal` | `./Tangent.js` |
| `uniform` | `../core/UniformNode.js` |
| `buffer` | `./BufferNode.js` |
| `getDataFromObject` | `../core/NodeUtils.js` |
| `storage` | `./StorageBufferNode.js` |
| `InstancedBufferAttribute` | `../../core/InstancedBufferAttribute.js` |
| `instanceIndex` | `../core/IndexNode.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_frameId` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `skinnedMesh` | `any` | let/var | `builder.object` | ✗ |
| `skeleton` | `any` | let/var | `frame.object && frame.object.skeleton ? frame.object.skeleton : this.skinnedM...` | ✗ |
| `node` | `SkinningNode` | let/var | `new SkinningNode( skinnedMesh )` | ✗ |


---

## Functions

### `SkinningNode.getSkinnedPosition(boneMatrices: Node, position: any): any`

**JSDoc:**
```typescript
/**
	 * Transforms the given vertex position via skinning.
	 *
	 * @param {Node} [boneMatrices=this.boneMatricesNode] - The bone matrices
	 * @param {Node<vec3>} [position=this.positionNode] - The vertex position in local space.
	 * @return {Node<vec3>} The transformed vertex position.
	 */
```

**Parameters:**

- **`boneMatrices`** `Node`
- **`position`** `any`

**Returns:** `any`

**Calls:**

- `boneMatrices.element`
- `bindMatrixNode.mul`
- `add (from ../math/OperatorNode.js)`
- `boneMatX.mul( skinWeightNode.x ).mul`
- `boneMatY.mul( skinWeightNode.y ).mul`
- `boneMatZ.mul( skinWeightNode.z ).mul`
- `boneMatW.mul( skinWeightNode.w ).mul`
- `bindMatrixInverseNode.mul`

**Internal Comments:**
```
// POSITION (x2)
```

<details><summary>Code</summary>

```typescript
getSkinnedPosition( boneMatrices = this.boneMatricesNode, position = this.positionNode ) {

		const { skinIndexNode, skinWeightNode, bindMatrixNode, bindMatrixInverseNode } = this;

		const boneMatX = boneMatrices.element( skinIndexNode.x );
		const boneMatY = boneMatrices.element( skinIndexNode.y );
		const boneMatZ = boneMatrices.element( skinIndexNode.z );
		const boneMatW = boneMatrices.element( skinIndexNode.w );

		// POSITION

		const skinVertex = bindMatrixNode.mul( position );

		const skinned = add(
			boneMatX.mul( skinWeightNode.x ).mul( skinVertex ),
			boneMatY.mul( skinWeightNode.y ).mul( skinVertex ),
			boneMatZ.mul( skinWeightNode.z ).mul( skinVertex ),
			boneMatW.mul( skinWeightNode.w ).mul( skinVertex )
		);

		return bindMatrixInverseNode.mul( skinned ).xyz;

	}
```
</details>

### `SkinningNode.getSkinnedNormal(boneMatrices: Node, normal: any): any`

**JSDoc:**
```typescript
/**
	 * Transforms the given vertex normal via skinning.
	 *
	 * @param {Node} [boneMatrices=this.boneMatricesNode] - The bone matrices
	 * @param {Node<vec3>} [normal=normalLocal] - The vertex normal in local space.
	 * @return {Node<vec3>} The transformed vertex normal.
	 */
```

**Parameters:**

- **`boneMatrices`** `Node`
- **`normal`** `any`

**Returns:** `any`

**Calls:**

- `boneMatrices.element`
- `add (from ../math/OperatorNode.js)`
- `skinWeightNode.x.mul`
- `skinWeightNode.y.mul`
- `skinWeightNode.z.mul`
- `skinWeightNode.w.mul`
- `bindMatrixInverseNode.mul( skinMatrix ).mul`
- `skinMatrix.transformDirection`

**Internal Comments:**
```
// NORMAL (x2)
```

<details><summary>Code</summary>

```typescript
getSkinnedNormal( boneMatrices = this.boneMatricesNode, normal = normalLocal ) {

		const { skinIndexNode, skinWeightNode, bindMatrixNode, bindMatrixInverseNode } = this;

		const boneMatX = boneMatrices.element( skinIndexNode.x );
		const boneMatY = boneMatrices.element( skinIndexNode.y );
		const boneMatZ = boneMatrices.element( skinIndexNode.z );
		const boneMatW = boneMatrices.element( skinIndexNode.w );

		// NORMAL

		let skinMatrix = add(
			skinWeightNode.x.mul( boneMatX ),
			skinWeightNode.y.mul( boneMatY ),
			skinWeightNode.z.mul( boneMatZ ),
			skinWeightNode.w.mul( boneMatW )
		);

		skinMatrix = bindMatrixInverseNode.mul( skinMatrix ).mul( bindMatrixNode );

		return skinMatrix.transformDirection( normal ).xyz;

	}
```
</details>

### `SkinningNode.getPreviousSkinnedPosition(builder: NodeBuilder): any`

**JSDoc:**
```typescript
/**
	 * Computes the transformed/skinned vertex position of the previous frame.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Node<vec3>} The skinned position from the previous frame.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `any`

**Calls:**

- `referenceBuffer (from ./ReferenceNode.js)`
- `this.getSkinnedPosition`

<details><summary>Code</summary>

```typescript
getPreviousSkinnedPosition( builder ) {

		const skinnedMesh = builder.object;

		if ( this.previousBoneMatricesNode === null ) {

			skinnedMesh.skeleton.previousBoneMatrices = new Float32Array( skinnedMesh.skeleton.boneMatrices );

			this.previousBoneMatricesNode = referenceBuffer( 'skeleton.previousBoneMatrices', 'mat4', skinnedMesh.skeleton.bones.length );

		}

		return this.getSkinnedPosition( this.previousBoneMatricesNode, positionPrevious );

	}
```
</details>

### `SkinningNode.needsPreviousBoneMatrices(builder: NodeBuilder): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if bone matrices from the previous frame are required. Relevant
	 * when computing motion vectors with {@link VelocityNode}.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {boolean} Whether bone matrices from the previous frame are required or not.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `boolean`

**Calls:**

- `builder.renderer.getMRT`
- `mrt.has`
- `getDataFromObject (from ../core/NodeUtils.js)`

<details><summary>Code</summary>

```typescript
needsPreviousBoneMatrices( builder ) {

		const mrt = builder.renderer.getMRT();

		return ( mrt && mrt.has( 'velocity' ) ) || getDataFromObject( builder.object ).useVelocity === true;

	}
```
</details>

### `SkinningNode.setup(builder: NodeBuilder): any`

**JSDoc:**
```typescript
/**
	 * Setups the skinning node by assigning the transformed vertex data to predefined node variables.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Node<vec3>} The transformed vertex position.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `any`

**Calls:**

- `this.needsPreviousBoneMatrices`
- `positionPrevious.assign`
- `this.getPreviousSkinnedPosition`
- `this.getSkinnedPosition`
- `this.toPositionNode.assign`
- `builder.hasGeometryAttribute`
- `this.getSkinnedNormal`
- `normalLocal.assign`
- `tangentLocal.assign`

**Internal Comments:**
```
//
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		if ( this.needsPreviousBoneMatrices( builder ) ) {

			positionPrevious.assign( this.getPreviousSkinnedPosition( builder ) );

		}

		const skinPosition = this.getSkinnedPosition();

		if ( this.toPositionNode ) this.toPositionNode.assign( skinPosition );

		//

		if ( builder.hasGeometryAttribute( 'normal' ) ) {

			const skinNormal = this.getSkinnedNormal();

			normalLocal.assign( skinNormal );

			if ( builder.hasGeometryAttribute( 'tangent' ) ) {

				tangentLocal.assign( skinNormal );

			}

		}

		return skinPosition;

	}
```
</details>

### `SkinningNode.generate(builder: NodeBuilder, output: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the code snippet of the skinning node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {string} output - The current output.
	 * @return {string} The generated code snippet.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`output`** `string`

**Returns:** `string`

**Calls:**

- `super.generate`

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		if ( output !== 'void' ) {

			return super.generate( builder, output );

		}

	}
```
</details>

### `SkinningNode.update(frame: NodeFrame): void`

**JSDoc:**
```typescript
/**
	 * Updates the state of the skinned mesh by updating the skeleton once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
```

**Parameters:**

- **`frame`** `NodeFrame`

**Returns:** `void`

**Calls:**

- `_frameId.get`
- `_frameId.set`
- `skeleton.previousBoneMatrices.set`
- `skeleton.update`

<details><summary>Code</summary>

```typescript
update( frame ) {

		const skeleton = frame.object && frame.object.skeleton ? frame.object.skeleton : this.skinnedMesh.skeleton;

		if ( _frameId.get( skeleton ) === frame.frameId ) return;

		_frameId.set( skeleton, frame.frameId );

		if ( this.previousBoneMatricesNode !== null ) skeleton.previousBoneMatrices.set( skeleton.boneMatrices );

		skeleton.update();

	}
```
</details>

### `skinning(skinnedMesh: SkinnedMesh): SkinningNode`

**Parameters:**

- **`skinnedMesh`** `SkinnedMesh`

**Returns:** `SkinningNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( skinnedMesh ) => nodeObject( new SkinningNode( skinnedMesh ) )
```
</details>

### `computeSkinning(skinnedMesh: SkinnedMesh, toPosition: any): SkinningNode`

**Parameters:**

- **`skinnedMesh`** `SkinnedMesh`
- **`toPosition`** `any`

**Returns:** `SkinningNode`

**Calls:**

- `storage( new InstancedBufferAttribute( skinnedMesh.geometry.getAttribute( 'position' ).array, 3 ), 'vec3' ).setPBO( true ).toReadOnly().element( instanceIndex ).toVar`
- `storage( new InstancedBufferAttribute( new Uint32Array( skinnedMesh.geometry.getAttribute( 'skinIndex' ).array ), 4 ), 'uvec4' ).setPBO( true ).toReadOnly().element( instanceIndex ).toVar`
- `storage( new InstancedBufferAttribute( skinnedMesh.geometry.getAttribute( 'skinWeight' ).array, 4 ), 'vec4' ).setPBO( true ).toReadOnly().element( instanceIndex ).toVar`
- `uniform (from ../core/UniformNode.js)`
- `buffer (from ./BufferNode.js)`
- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
( skinnedMesh, toPosition = null ) => {

	const node = new SkinningNode( skinnedMesh );
	node.positionNode = storage( new InstancedBufferAttribute( skinnedMesh.geometry.getAttribute( 'position' ).array, 3 ), 'vec3' ).setPBO( true ).toReadOnly().element( instanceIndex ).toVar();
	node.skinIndexNode = storage( new InstancedBufferAttribute( new Uint32Array( skinnedMesh.geometry.getAttribute( 'skinIndex' ).array ), 4 ), 'uvec4' ).setPBO( true ).toReadOnly().element( instanceIndex ).toVar();
	node.skinWeightNode = storage( new InstancedBufferAttribute( skinnedMesh.geometry.getAttribute( 'skinWeight' ).array, 4 ), 'vec4' ).setPBO( true ).toReadOnly().element( instanceIndex ).toVar();
	node.bindMatrixNode = uniform( skinnedMesh.bindMatrix, 'mat4' );
	node.bindMatrixInverseNode = uniform( skinnedMesh.bindMatrixInverse, 'mat4' );
	node.boneMatricesNode = buffer( skinnedMesh.skeleton.boneMatrices, 'mat4', skinnedMesh.skeleton.bones.length );
	node.toPositionNode = toPosition;

	return nodeObject( node );

}
```
</details>


---

## Classes

### `SkinningNode`

<details><summary>Class Code</summary>

```ts
class SkinningNode extends Node {

	static get type() {

		return 'SkinningNode';

	}

	/**
	 * Constructs a new skinning node.
	 *
	 * @param {SkinnedMesh} skinnedMesh - The skinned mesh.
	 */
	constructor( skinnedMesh ) {

		super( 'void' );

		/**
		 * The skinned mesh.
		 *
		 * @type {SkinnedMesh}
		 */
		this.skinnedMesh = skinnedMesh;

		/**
		 * The update type overwritten since skinning nodes are updated per object.
		 *
		 * @type {string}
		 */
		this.updateType = NodeUpdateType.OBJECT;

		//

		/**
		 * The skin index attribute.
		 *
		 * @type {AttributeNode}
		 */
		this.skinIndexNode = attribute( 'skinIndex', 'uvec4' );

		/**
		 * The skin weight attribute.
		 *
		 * @type {AttributeNode}
		 */
		this.skinWeightNode = attribute( 'skinWeight', 'vec4' );

		/**
		 * The bind matrix node.
		 *
		 * @type {Node<mat4>}
		 */
		this.bindMatrixNode = reference( 'bindMatrix', 'mat4' );

		/**
		 * The bind matrix inverse node.
		 *
		 * @type {Node<mat4>}
		 */
		this.bindMatrixInverseNode = reference( 'bindMatrixInverse', 'mat4' );

		/**
		 * The bind matrices as a uniform buffer node.
		 *
		 * @type {Node}
		 */
		this.boneMatricesNode = referenceBuffer( 'skeleton.boneMatrices', 'mat4', skinnedMesh.skeleton.bones.length );

		/**
		 * The current vertex position in local space.
		 *
		 * @type {Node<vec3>}
		 */
		this.positionNode = positionLocal;

		/**
		 * The result of vertex position in local space.
		 *
		 * @type {Node<vec3>}
		 */
		this.toPositionNode = positionLocal;

		/**
		 * The previous bind matrices as a uniform buffer node.
		 * Required for computing motion vectors.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.previousBoneMatricesNode = null;

	}

	/**
	 * Transforms the given vertex position via skinning.
	 *
	 * @param {Node} [boneMatrices=this.boneMatricesNode] - The bone matrices
	 * @param {Node<vec3>} [position=this.positionNode] - The vertex position in local space.
	 * @return {Node<vec3>} The transformed vertex position.
	 */
	getSkinnedPosition( boneMatrices = this.boneMatricesNode, position = this.positionNode ) {

		const { skinIndexNode, skinWeightNode, bindMatrixNode, bindMatrixInverseNode } = this;

		const boneMatX = boneMatrices.element( skinIndexNode.x );
		const boneMatY = boneMatrices.element( skinIndexNode.y );
		const boneMatZ = boneMatrices.element( skinIndexNode.z );
		const boneMatW = boneMatrices.element( skinIndexNode.w );

		// POSITION

		const skinVertex = bindMatrixNode.mul( position );

		const skinned = add(
			boneMatX.mul( skinWeightNode.x ).mul( skinVertex ),
			boneMatY.mul( skinWeightNode.y ).mul( skinVertex ),
			boneMatZ.mul( skinWeightNode.z ).mul( skinVertex ),
			boneMatW.mul( skinWeightNode.w ).mul( skinVertex )
		);

		return bindMatrixInverseNode.mul( skinned ).xyz;

	}

	/**
	 * Transforms the given vertex normal via skinning.
	 *
	 * @param {Node} [boneMatrices=this.boneMatricesNode] - The bone matrices
	 * @param {Node<vec3>} [normal=normalLocal] - The vertex normal in local space.
	 * @return {Node<vec3>} The transformed vertex normal.
	 */
	getSkinnedNormal( boneMatrices = this.boneMatricesNode, normal = normalLocal ) {

		const { skinIndexNode, skinWeightNode, bindMatrixNode, bindMatrixInverseNode } = this;

		const boneMatX = boneMatrices.element( skinIndexNode.x );
		const boneMatY = boneMatrices.element( skinIndexNode.y );
		const boneMatZ = boneMatrices.element( skinIndexNode.z );
		const boneMatW = boneMatrices.element( skinIndexNode.w );

		// NORMAL

		let skinMatrix = add(
			skinWeightNode.x.mul( boneMatX ),
			skinWeightNode.y.mul( boneMatY ),
			skinWeightNode.z.mul( boneMatZ ),
			skinWeightNode.w.mul( boneMatW )
		);

		skinMatrix = bindMatrixInverseNode.mul( skinMatrix ).mul( bindMatrixNode );

		return skinMatrix.transformDirection( normal ).xyz;

	}

	/**
	 * Computes the transformed/skinned vertex position of the previous frame.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Node<vec3>} The skinned position from the previous frame.
	 */
	getPreviousSkinnedPosition( builder ) {

		const skinnedMesh = builder.object;

		if ( this.previousBoneMatricesNode === null ) {

			skinnedMesh.skeleton.previousBoneMatrices = new Float32Array( skinnedMesh.skeleton.boneMatrices );

			this.previousBoneMatricesNode = referenceBuffer( 'skeleton.previousBoneMatrices', 'mat4', skinnedMesh.skeleton.bones.length );

		}

		return this.getSkinnedPosition( this.previousBoneMatricesNode, positionPrevious );

	}

	/**
	 * Returns `true` if bone matrices from the previous frame are required. Relevant
	 * when computing motion vectors with {@link VelocityNode}.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {boolean} Whether bone matrices from the previous frame are required or not.
	 */
	needsPreviousBoneMatrices( builder ) {

		const mrt = builder.renderer.getMRT();

		return ( mrt && mrt.has( 'velocity' ) ) || getDataFromObject( builder.object ).useVelocity === true;

	}

	/**
	 * Setups the skinning node by assigning the transformed vertex data to predefined node variables.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {Node<vec3>} The transformed vertex position.
	 */
	setup( builder ) {

		if ( this.needsPreviousBoneMatrices( builder ) ) {

			positionPrevious.assign( this.getPreviousSkinnedPosition( builder ) );

		}

		const skinPosition = this.getSkinnedPosition();

		if ( this.toPositionNode ) this.toPositionNode.assign( skinPosition );

		//

		if ( builder.hasGeometryAttribute( 'normal' ) ) {

			const skinNormal = this.getSkinnedNormal();

			normalLocal.assign( skinNormal );

			if ( builder.hasGeometryAttribute( 'tangent' ) ) {

				tangentLocal.assign( skinNormal );

			}

		}

		return skinPosition;

	}

	/**
	 * Generates the code snippet of the skinning node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {string} output - The current output.
	 * @return {string} The generated code snippet.
	 */
	generate( builder, output ) {

		if ( output !== 'void' ) {

			return super.generate( builder, output );

		}

	}

	/**
	 * Updates the state of the skinned mesh by updating the skeleton once per frame.
	 *
	 * @param {NodeFrame} frame - The current node frame.
	 */
	update( frame ) {

		const skeleton = frame.object && frame.object.skeleton ? frame.object.skeleton : this.skinnedMesh.skeleton;

		if ( _frameId.get( skeleton ) === frame.frameId ) return;

		_frameId.set( skeleton, frame.frameId );

		if ( this.previousBoneMatricesNode !== null ) skeleton.previousBoneMatrices.set( skeleton.boneMatrices );

		skeleton.update();

	}

}
```
</details>

#### Methods

##### `getSkinnedPosition(boneMatrices: Node, position: any): any`

<details><summary>Code</summary>

```ts
getSkinnedPosition( boneMatrices = this.boneMatricesNode, position = this.positionNode ) {

		const { skinIndexNode, skinWeightNode, bindMatrixNode, bindMatrixInverseNode } = this;

		const boneMatX = boneMatrices.element( skinIndexNode.x );
		const boneMatY = boneMatrices.element( skinIndexNode.y );
		const boneMatZ = boneMatrices.element( skinIndexNode.z );
		const boneMatW = boneMatrices.element( skinIndexNode.w );

		// POSITION

		const skinVertex = bindMatrixNode.mul( position );

		const skinned = add(
			boneMatX.mul( skinWeightNode.x ).mul( skinVertex ),
			boneMatY.mul( skinWeightNode.y ).mul( skinVertex ),
			boneMatZ.mul( skinWeightNode.z ).mul( skinVertex ),
			boneMatW.mul( skinWeightNode.w ).mul( skinVertex )
		);

		return bindMatrixInverseNode.mul( skinned ).xyz;

	}
```
</details>

##### `getSkinnedNormal(boneMatrices: Node, normal: any): any`

<details><summary>Code</summary>

```ts
getSkinnedNormal( boneMatrices = this.boneMatricesNode, normal = normalLocal ) {

		const { skinIndexNode, skinWeightNode, bindMatrixNode, bindMatrixInverseNode } = this;

		const boneMatX = boneMatrices.element( skinIndexNode.x );
		const boneMatY = boneMatrices.element( skinIndexNode.y );
		const boneMatZ = boneMatrices.element( skinIndexNode.z );
		const boneMatW = boneMatrices.element( skinIndexNode.w );

		// NORMAL

		let skinMatrix = add(
			skinWeightNode.x.mul( boneMatX ),
			skinWeightNode.y.mul( boneMatY ),
			skinWeightNode.z.mul( boneMatZ ),
			skinWeightNode.w.mul( boneMatW )
		);

		skinMatrix = bindMatrixInverseNode.mul( skinMatrix ).mul( bindMatrixNode );

		return skinMatrix.transformDirection( normal ).xyz;

	}
```
</details>

##### `getPreviousSkinnedPosition(builder: NodeBuilder): any`

<details><summary>Code</summary>

```ts
getPreviousSkinnedPosition( builder ) {

		const skinnedMesh = builder.object;

		if ( this.previousBoneMatricesNode === null ) {

			skinnedMesh.skeleton.previousBoneMatrices = new Float32Array( skinnedMesh.skeleton.boneMatrices );

			this.previousBoneMatricesNode = referenceBuffer( 'skeleton.previousBoneMatrices', 'mat4', skinnedMesh.skeleton.bones.length );

		}

		return this.getSkinnedPosition( this.previousBoneMatricesNode, positionPrevious );

	}
```
</details>

##### `needsPreviousBoneMatrices(builder: NodeBuilder): boolean`

<details><summary>Code</summary>

```ts
needsPreviousBoneMatrices( builder ) {

		const mrt = builder.renderer.getMRT();

		return ( mrt && mrt.has( 'velocity' ) ) || getDataFromObject( builder.object ).useVelocity === true;

	}
```
</details>

##### `setup(builder: NodeBuilder): any`

<details><summary>Code</summary>

```ts
setup( builder ) {

		if ( this.needsPreviousBoneMatrices( builder ) ) {

			positionPrevious.assign( this.getPreviousSkinnedPosition( builder ) );

		}

		const skinPosition = this.getSkinnedPosition();

		if ( this.toPositionNode ) this.toPositionNode.assign( skinPosition );

		//

		if ( builder.hasGeometryAttribute( 'normal' ) ) {

			const skinNormal = this.getSkinnedNormal();

			normalLocal.assign( skinNormal );

			if ( builder.hasGeometryAttribute( 'tangent' ) ) {

				tangentLocal.assign( skinNormal );

			}

		}

		return skinPosition;

	}
```
</details>

##### `generate(builder: NodeBuilder, output: string): string`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		if ( output !== 'void' ) {

			return super.generate( builder, output );

		}

	}
```
</details>

##### `update(frame: NodeFrame): void`

<details><summary>Code</summary>

```ts
update( frame ) {

		const skeleton = frame.object && frame.object.skeleton ? frame.object.skeleton : this.skinnedMesh.skeleton;

		if ( _frameId.get( skeleton ) === frame.frameId ) return;

		_frameId.set( skeleton, frame.frameId );

		if ( this.previousBoneMatricesNode !== null ) skeleton.previousBoneMatrices.set( skeleton.boneMatrices );

		skeleton.update();

	}
```
</details>


---