[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TextureNode.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 33 |
| 🧱 Classes | 1 |
| 📦 Imports | 16 |
| 📊 Variables & Constants | 20 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/accessors/TextureNode.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `uniform` | `../core/UniformNode.js` |
| `UniformNode` | `../core/UniformNode.js` |
| `uv` | `./UV.js` |
| `textureSize` | `./TextureSizeNode.js` |
| `colorSpaceToWorking` | `../display/ColorSpaceNode.js` |
| `expression` | `../code/ExpressionNode.js` |
| `maxMipLevel` | `../utils/MaxMipLevelNode.js` |
| `nodeProxy` | `../tsl/TSLBase.js` |
| `vec3` | `../tsl/TSLBase.js` |
| `nodeObject` | `../tsl/TSLBase.js` |
| `int` | `../tsl/TSLBase.js` |
| `NodeUpdateType` | `../core/constants.js` |
| `IntType` | `../../constants.js` |
| `NearestFilter` | `../../constants.js` |
| `UnsignedIntType` | `../../constants.js` |
| `Texture` | `../../textures/Texture.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `EmptyTexture` | `Texture` | let/var | `new Texture()` | ✗ |
| `texture` | `Texture` | let/var | `this.value` | ✗ |
| `texture` | `Texture` | let/var | `this.value` | ✗ |
| `uvNode` | `any` | let/var | `this.uvNode` | ✗ |
| `levelNode` | `any` | let/var | `this.levelNode` | ✗ |
| `texture` | `Texture` | let/var | `this.value` | ✗ |
| `snippet` | `any` | let/var | `*not shown*` | ✗ |
| `texture` | `Texture` | let/var | `this.value` | ✗ |
| `propertyName` | `any` | let/var | `nodeData.propertyName` | ✗ |
| `levelSnippet` | `any` | let/var | `levelNode ? levelNode.build( builder, 'float' ) : null` | ✗ |
| `biasSnippet` | `any` | let/var | `biasNode ? biasNode.build( builder, 'float' ) : null` | ✗ |
| `depthSnippet` | `any` | let/var | `depthNode ? depthNode.build( builder, 'int' ) : null` | ✗ |
| `compareSnippet` | `any` | let/var | `compareNode ? compareNode.build( builder, 'float' ) : null` | ✗ |
| `gradSnippet` | `any[]` | let/var | `gradNode ? [ gradNode[ 0 ].build( builder, 'vec2' ), gradNode[ 1 ].build( bui...` | ✗ |
| `snippet` | `any` | let/var | `propertyName` | ✗ |
| `map` | `Texture` | let/var | `textureNode.value` | ✗ |
| `texture` | `Texture` | let/var | `this.value` | ✗ |
| `matrixUniform` | `any` | let/var | `this._matrixUniform` | ✗ |
| `newNode` | `any` | let/var | `new this.constructor( this.value, this.uvNode, this.levelNode, this.biasNode )` | ✗ |
| `textureNode` | `any` | let/var | `*not shown*` | ✗ |


---

## Functions

### `TextureNode.getUniformHash(): string`

**JSDoc:**
```typescript
/**
	 * Overwritten since the uniform hash is defined by the texture's UUID.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The uniform hash.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getUniformHash( /*builder*/ ) {

		return this.value.uuid;

	}
```
</details>

### `TextureNode.getNodeType(): string`

**JSDoc:**
```typescript
/**
	 * Overwritten since the node type is inferred from the texture type.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getNodeType( /*builder*/ ) {

		if ( this.value.isDepthTexture === true ) return 'float';

		if ( this.value.type === UnsignedIntType ) {

			return 'uvec4';

		} else if ( this.value.type === IntType ) {

			return 'ivec4';

		}

		return 'vec4';

	}
```
</details>

### `TextureNode.getInputType(): string`

**JSDoc:**
```typescript
/**
	 * Overwrites the default implementation to return a fixed value `'texture'`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getInputType( /*builder*/ ) {

		return 'texture';

	}
```
</details>

### `TextureNode.getDefaultUV(): AttributeNode<vec2>`

**JSDoc:**
```typescript
/**
	 * Returns a default uvs based on the current texture's channel.
	 *
	 * @return {AttributeNode<vec2>} The default uvs.
	 */
```

**Returns:** `AttributeNode<vec2>`

**Calls:**

- `uv (from ./UV.js)`

<details><summary>Code</summary>

```typescript
getDefaultUV() {

		return uv( this.value.channel );

	}
```
</details>

### `TextureNode.updateReference(): Texture`

**JSDoc:**
```typescript
/**
	 * Overwritten to always return the texture reference of the node.
	 *
	 * @param {any} state - This method can be invocated in different contexts so `state` can refer to any object type.
	 * @return {Texture} The texture reference.
	 */
```

**Returns:** `Texture`

<details><summary>Code</summary>

```typescript
updateReference( /*state*/ ) {

		return this.value;

	}
```
</details>

### `TextureNode.getTransformedUV(uvNode: Node): Node`

**JSDoc:**
```typescript
/**
	 * Transforms the given uv node with the texture transformation matrix.
	 *
	 * @param {Node} uvNode - The uv node to transform.
	 * @return {Node} The transformed uv node.
	 */
```

**Parameters:**

- **`uvNode`** `Node`

**Returns:** `Node`

**Calls:**

- `uniform (from ../core/UniformNode.js)`
- `this._matrixUniform.mul`
- `vec3 (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
getTransformedUV( uvNode ) {

		if ( this._matrixUniform === null ) this._matrixUniform = uniform( this.value.matrix );

		return this._matrixUniform.mul( vec3( uvNode, 1 ) ).xy;

	}
```
</details>

### `TextureNode.setUpdateMatrix(value: boolean): TextureNode`

**JSDoc:**
```typescript
/**
	 * Defines whether the uv transformation matrix should automatically be updated or not.
	 *
	 * @param {boolean} value - The update toggle.
	 * @return {TextureNode} A reference to this node.
	 */
```

**Parameters:**

- **`value`** `boolean`

**Returns:** `TextureNode`

<details><summary>Code</summary>

```typescript
setUpdateMatrix( value ) {

		this.updateMatrix = value;
		this.updateType = value ? NodeUpdateType.OBJECT : NodeUpdateType.NONE;

		return this;

	}
```
</details>

### `TextureNode.setupUV(builder: NodeBuilder, uvNode: Node): Node`

**JSDoc:**
```typescript
/**
	 * Setups the uv node. Depending on the backend as well as texture's image and type, it might be necessary
	 * to modify the uv node for correct sampling.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {Node} uvNode - The uv node to setup.
	 * @return {Node} The updated uv node.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`uvNode`** `Node`

**Returns:** `Node`

**Calls:**

- `builder.isFlipY`
- `uvNode.flipY`
- `uvNode.setY`
- `int( textureSize( this, this.levelNode ).y ).sub( uvNode.y ).sub`

<details><summary>Code</summary>

```typescript
setupUV( builder, uvNode ) {

		const texture = this.value;

		if ( builder.isFlipY() && ( ( texture.image instanceof ImageBitmap && texture.flipY === true ) || texture.isRenderTargetTexture === true || texture.isFramebufferTexture === true || texture.isDepthTexture === true ) ) {

			if ( this.sampler ) {

				uvNode = uvNode.flipY();

			} else {

				uvNode = uvNode.setY( int( textureSize( this, this.levelNode ).y ).sub( uvNode.y ).sub( 1 ) );

			}

		}

		return uvNode;

	}
```
</details>

### `TextureNode.setup(builder: NodeBuilder): void`

**JSDoc:**
```typescript
/**
	 * Setups texture node by preparing the internal nodes for code generation.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`

**Returns:** `void`

**Calls:**

- `builder.getNodeProperties`
- `builder.context.getUV`
- `this.getDefaultUV`
- `this.getTransformedUV`
- `this.setupUV`
- `builder.context.getTextureLevel`

**Internal Comments:**
```
// (x10)
```

<details><summary>Code</summary>

```typescript
setup( builder ) {

		const properties = builder.getNodeProperties( this );
		properties.referenceNode = this.referenceNode;

		//

		const texture = this.value;

		if ( ! texture || texture.isTexture !== true ) {

			throw new Error( 'THREE.TSL: `texture( value )` function expects a valid instance of THREE.Texture().' );

		}

		//

		let uvNode = this.uvNode;

		if ( ( uvNode === null || builder.context.forceUVContext === true ) && builder.context.getUV ) {

			uvNode = builder.context.getUV( this, builder );

		}

		if ( ! uvNode ) uvNode = this.getDefaultUV();

		if ( this.updateMatrix === true ) {

			uvNode = this.getTransformedUV( uvNode );

		}

		uvNode = this.setupUV( builder, uvNode );

		//

		let levelNode = this.levelNode;

		if ( levelNode === null && builder.context.getTextureLevel ) {

			levelNode = builder.context.getTextureLevel( this );

		}

		//

		properties.uvNode = uvNode;
		properties.levelNode = levelNode;
		properties.biasNode = this.biasNode;
		properties.compareNode = this.compareNode;
		properties.gradNode = this.gradNode;
		properties.depthNode = this.depthNode;

	}
```
</details>

### `TextureNode.generateUV(builder: NodeBuilder, uvNode: Node): string`

**JSDoc:**
```typescript
/**
	 * Generates the uv code snippet.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {Node} uvNode - The uv node to generate code for.
	 * @return {string} The generated code snippet.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`uvNode`** `Node`

**Returns:** `string`

**Calls:**

- `uvNode.build`

<details><summary>Code</summary>

```typescript
generateUV( builder, uvNode ) {

		return uvNode.build( builder, this.sampler === true ? 'vec2' : 'ivec2' );

	}
```
</details>

### `TextureNode.generateSnippet(builder: NodeBuilder, textureProperty: string, uvSnippet: string, levelSnippet: string, biasSnippet: string, depthSnippet: string, compareSnippet: string, gradSnippet: string[]): string`

**JSDoc:**
```typescript
/**
	 * Generates the snippet for the texture sampling.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {string} textureProperty - The texture property.
	 * @param {string} uvSnippet - The uv snippet.
	 * @param {?string} levelSnippet - The level snippet.
	 * @param {?string} biasSnippet - The bias snippet.
	 * @param {?string} depthSnippet - The depth snippet.
	 * @param {?string} compareSnippet - The compare snippet.
	 * @param {?Array<string>} gradSnippet - The grad snippet.
	 * @return {string} The generated code snippet.
	 */
```

**Parameters:**

- **`builder`** `NodeBuilder`
- **`textureProperty`** `string`
- **`uvSnippet`** `string`
- **`levelSnippet`** `string`
- **`biasSnippet`** `string`
- **`depthSnippet`** `string`
- **`compareSnippet`** `string`
- **`gradSnippet`** `string[]`

**Returns:** `string`

**Calls:**

- `builder.generateTextureLevel`
- `builder.generateTextureBias`
- `builder.generateTextureGrad`
- `builder.generateTextureCompare`
- `builder.generateTextureLoad`
- `builder.generateTexture`

<details><summary>Code</summary>

```typescript
generateSnippet( builder, textureProperty, uvSnippet, levelSnippet, biasSnippet, depthSnippet, compareSnippet, gradSnippet ) {

		const texture = this.value;

		let snippet;

		if ( levelSnippet ) {

			snippet = builder.generateTextureLevel( texture, textureProperty, uvSnippet, levelSnippet, depthSnippet );

		} else if ( biasSnippet ) {

			snippet = builder.generateTextureBias( texture, textureProperty, uvSnippet, biasSnippet, depthSnippet );

		} else if ( gradSnippet ) {

			snippet = builder.generateTextureGrad( texture, textureProperty, uvSnippet, gradSnippet, depthSnippet );

		} else if ( compareSnippet ) {

			snippet = builder.generateTextureCompare( texture, textureProperty, uvSnippet, compareSnippet, depthSnippet );

		} else if ( this.sampler === false ) {

			snippet = builder.generateTextureLoad( texture, textureProperty, uvSnippet, depthSnippet );

		} else {

			snippet = builder.generateTexture( texture, textureProperty, uvSnippet, depthSnippet );

		}

		return snippet;

	}
```
</details>

### `TextureNode.generate(builder: NodeBuilder, output: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the code snippet of the texture node.
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

- `builder.getNodeProperties`
- `super.generate`
- `/^sampler/.test`
- `builder.isReference`
- `builder.getDataFromNode`
- `this.generateUV`
- `levelNode.build`
- `biasNode.build`
- `depthNode.build`
- `compareNode.build`
- `gradNode[ 0 ].build`
- `gradNode[ 1 ].build`
- `builder.getVarFromNode`
- `builder.getPropertyName`
- `this.generateSnippet`
- `builder.addLineFlowCode`
- `this.getNodeType`
- `builder.needsToWorkingColorSpace`
- `colorSpaceToWorking( expression( snippet, nodeType ), texture.colorSpace ).setup( builder ).build`
- `builder.format`

<details><summary>Code</summary>

```typescript
generate( builder, output ) {

		const texture = this.value;

		const properties = builder.getNodeProperties( this );
		const textureProperty = super.generate( builder, 'property' );

		if ( /^sampler/.test( output ) ) {

			return textureProperty + '_sampler';

		} else if ( builder.isReference( output ) ) {

			return textureProperty;

		} else {

			const nodeData = builder.getDataFromNode( this );

			let propertyName = nodeData.propertyName;

			if ( propertyName === undefined ) {

				const { uvNode, levelNode, biasNode, compareNode, depthNode, gradNode } = properties;

				const uvSnippet = this.generateUV( builder, uvNode );
				const levelSnippet = levelNode ? levelNode.build( builder, 'float' ) : null;
				const biasSnippet = biasNode ? biasNode.build( builder, 'float' ) : null;
				const depthSnippet = depthNode ? depthNode.build( builder, 'int' ) : null;
				const compareSnippet = compareNode ? compareNode.build( builder, 'float' ) : null;
				const gradSnippet = gradNode ? [ gradNode[ 0 ].build( builder, 'vec2' ), gradNode[ 1 ].build( builder, 'vec2' ) ] : null;

				const nodeVar = builder.getVarFromNode( this );

				propertyName = builder.getPropertyName( nodeVar );

				const snippet = this.generateSnippet( builder, textureProperty, uvSnippet, levelSnippet, biasSnippet, depthSnippet, compareSnippet, gradSnippet );

				builder.addLineFlowCode( `${propertyName} = ${snippet}`, this );

				nodeData.snippet = snippet;
				nodeData.propertyName = propertyName;

			}

			let snippet = propertyName;
			const nodeType = this.getNodeType( builder );

			if ( builder.needsToWorkingColorSpace( texture ) ) {

				snippet = colorSpaceToWorking( expression( snippet, nodeType ), texture.colorSpace ).setup( builder ).build( builder, nodeType );

			}

			return builder.format( snippet, nodeType, output );

		}

	}
```
</details>

### `TextureNode.setSampler(value: boolean): TextureNode`

**JSDoc:**
```typescript
/**
	 * Sets the sampler value.
	 *
	 * @param {boolean} value - The sampler value to set.
	 * @return {TextureNode} A reference to this texture node.
	 */
```

**Parameters:**

- **`value`** `boolean`

**Returns:** `TextureNode`

<details><summary>Code</summary>

```typescript
setSampler( value ) {

		this.sampler = value;

		return this;

	}
```
</details>

### `TextureNode.getSampler(): boolean`

**JSDoc:**
```typescript
/**
	 * Returns the sampler value.
	 *
	 * @return {boolean} The sampler value.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
getSampler() {

		return this.sampler;

	}
```
</details>

### `TextureNode.uv(uvNode: Node): TextureNode`

**JSDoc:**
```typescript
/**
	 * @function
	 * @deprecated since r172. Use {@link TextureNode#sample} instead.
	 *
	 * @param {Node} uvNode - The uv node.
	 * @return {TextureNode} A texture node representing the texture sample.
	 */
```

**Parameters:**

- **`uvNode`** `Node`

**Returns:** `TextureNode`

**Calls:**

- `console.warn`
- `this.sample`

<details><summary>Code</summary>

```typescript
uv( uvNode ) { // @deprecated, r172

		console.warn( 'THREE.TextureNode: .uv() has been renamed. Use .sample() instead.' );

		return this.sample( uvNode );

	}
```
</details>

### `TextureNode.sample(uvNode: Node): TextureNode`

**JSDoc:**
```typescript
/**
	 * Samples the texture with the given uv node.
	 *
	 * @param {Node} uvNode - The uv node.
	 * @return {TextureNode} A texture node representing the texture sample.
	 */
```

**Parameters:**

- **`uvNode`** `Node`

**Returns:** `TextureNode`

**Calls:**

- `this.clone`
- `nodeObject (from ../tsl/TSLBase.js)`
- `this.getSelf`

<details><summary>Code</summary>

```typescript
sample( uvNode ) {

		const textureNode = this.clone();
		textureNode.uvNode = nodeObject( uvNode );
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}
```
</details>

### `TextureNode.load(uvNode: any): TextureNode`

**JSDoc:**
```typescript
/**
	 * TSL function for creating a texture node that fetches/loads texels without interpolation.
	 *
	 * @param {Node<uvec2>} uvNode - The uv node.
	 * @returns {TextureNode} A texture node representing the texture load.
	 */
```

**Parameters:**

- **`uvNode`** `any`

**Returns:** `TextureNode`

**Calls:**

- `this.sample( uvNode ).setSampler`

<details><summary>Code</summary>

```typescript
load( uvNode ) {

		return this.sample( uvNode ).setSampler( false );

	}
```
</details>

### `TextureNode.blur(amountNode: any): TextureNode`

**JSDoc:**
```typescript
/**
	 * Samples a blurred version of the texture by defining an internal bias.
	 *
	 * @param {Node<float>} amountNode - How blurred the texture should be.
	 * @return {TextureNode} A texture node representing the texture sample.
	 */
```

**Parameters:**

- **`amountNode`** `any`

**Returns:** `TextureNode`

**Calls:**

- `this.clone`
- `nodeObject( amountNode ).mul`
- `maxMipLevel (from ../utils/MaxMipLevelNode.js)`
- `this.getSelf`
- `console.warn`
- `nodeObject (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
blur( amountNode ) {

		const textureNode = this.clone();
		textureNode.biasNode = nodeObject( amountNode ).mul( maxMipLevel( textureNode ) );
		textureNode.referenceNode = this.getSelf();

		const map = textureNode.value;

		if ( textureNode.generateMipmaps === false && ( map && map.generateMipmaps === false || map.minFilter === NearestFilter || map.magFilter === NearestFilter ) ) {

			console.warn( 'THREE.TSL: texture().blur() requires mipmaps and sampling. Use .generateMipmaps=true and .minFilter/.magFilter=THREE.LinearFilter in the Texture.' );

			textureNode.biasNode = null;

		}

		return nodeObject( textureNode );

	}
```
</details>

### `TextureNode.level(levelNode: any): TextureNode`

**JSDoc:**
```typescript
/**
	 * Samples a specific mip of the texture.
	 *
	 * @param {Node<int>} levelNode - The mip level to sample.
	 * @return {TextureNode} A texture node representing the texture sample.
	 */
```

**Parameters:**

- **`levelNode`** `any`

**Returns:** `TextureNode`

**Calls:**

- `this.clone`
- `nodeObject (from ../tsl/TSLBase.js)`
- `this.getSelf`

<details><summary>Code</summary>

```typescript
level( levelNode ) {

		const textureNode = this.clone();
		textureNode.levelNode = nodeObject( levelNode );
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}
```
</details>

### `TextureNode.size(levelNode: any): TextureSizeNode`

**JSDoc:**
```typescript
/**
	 * Returns the texture size of the requested level.
	 *
	 * @param {Node<int>} levelNode - The level to compute the size for.
	 * @return {TextureSizeNode} The texture size.
	 */
```

**Parameters:**

- **`levelNode`** `any`

**Returns:** `TextureSizeNode`

**Calls:**

- `textureSize (from ./TextureSizeNode.js)`

<details><summary>Code</summary>

```typescript
size( levelNode ) {

		return textureSize( this, levelNode );

	}
```
</details>

### `TextureNode.bias(biasNode: any): TextureNode`

**JSDoc:**
```typescript
/**
	 * Samples the texture with the given bias.
	 *
	 * @param {Node<float>} biasNode - The bias node.
	 * @return {TextureNode} A texture node representing the texture sample.
	 */
```

**Parameters:**

- **`biasNode`** `any`

**Returns:** `TextureNode`

**Calls:**

- `this.clone`
- `nodeObject (from ../tsl/TSLBase.js)`
- `this.getSelf`

<details><summary>Code</summary>

```typescript
bias( biasNode ) {

		const textureNode = this.clone();
		textureNode.biasNode = nodeObject( biasNode );
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}
```
</details>

### `TextureNode.compare(compareNode: any): TextureNode`

**JSDoc:**
```typescript
/**
	 * Samples the texture by executing a compare operation.
	 *
	 * @param {Node<float>} compareNode - The node that defines the compare value.
	 * @return {TextureNode} A texture node representing the texture sample.
	 */
```

**Parameters:**

- **`compareNode`** `any`

**Returns:** `TextureNode`

**Calls:**

- `this.clone`
- `nodeObject (from ../tsl/TSLBase.js)`
- `this.getSelf`

<details><summary>Code</summary>

```typescript
compare( compareNode ) {

		const textureNode = this.clone();
		textureNode.compareNode = nodeObject( compareNode );
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}
```
</details>

### `TextureNode.grad(gradNodeX: any, gradNodeY: any): TextureNode`

**JSDoc:**
```typescript
/**
	 * Samples the texture using an explicit gradient.
	 *
	 * @param {Node<vec2>} gradNodeX - The gradX node.
	 * @param {Node<vec2>} gradNodeY - The gradY node.
	 * @return {TextureNode} A texture node representing the texture sample.
	 */
```

**Parameters:**

- **`gradNodeX`** `any`
- **`gradNodeY`** `any`

**Returns:** `TextureNode`

**Calls:**

- `this.clone`
- `nodeObject (from ../tsl/TSLBase.js)`
- `this.getSelf`

<details><summary>Code</summary>

```typescript
grad( gradNodeX, gradNodeY ) {

		const textureNode = this.clone();
		textureNode.gradNode = [ nodeObject( gradNodeX ), nodeObject( gradNodeY ) ];
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}
```
</details>

### `TextureNode.depth(depthNode: any): TextureNode`

**JSDoc:**
```typescript
/**
	 * Samples the texture by defining a depth node.
	 *
	 * @param {Node<int>} depthNode - The depth node.
	 * @return {TextureNode} A texture node representing the texture sample.
	 */
```

**Parameters:**

- **`depthNode`** `any`

**Returns:** `TextureNode`

**Calls:**

- `this.clone`
- `nodeObject (from ../tsl/TSLBase.js)`
- `this.getSelf`

<details><summary>Code</summary>

```typescript
depth( depthNode ) {

		const textureNode = this.clone();
		textureNode.depthNode = nodeObject( depthNode );
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}
```
</details>

### `TextureNode.serialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.serialize`
- `this.value.toJSON`

<details><summary>Code</summary>

```typescript
serialize( data ) {

		super.serialize( data );

		data.value = this.value.toJSON( data.meta ).uuid;
		data.sampler = this.sampler;
		data.updateMatrix = this.updateMatrix;
		data.updateType = this.updateType;

	}
```
</details>

### `TextureNode.deserialize(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `super.deserialize`

<details><summary>Code</summary>

```typescript
deserialize( data ) {

		super.deserialize( data );

		this.value = data.meta.textures[ data.value ];
		this.sampler = data.sampler;
		this.updateMatrix = data.updateMatrix;
		this.updateType = data.updateType;

	}
```
</details>

### `TextureNode.update(): void`

**JSDoc:**
```typescript
/**
	 * The update is used to implement the update of the uv transformation matrix.
	 */
```

**Returns:** `void`

**Calls:**

- `texture.updateMatrix`

<details><summary>Code</summary>

```typescript
update() {

		const texture = this.value;
		const matrixUniform = this._matrixUniform;

		if ( matrixUniform !== null ) matrixUniform.value = texture.matrix;

		if ( texture.matrixAutoUpdate === true ) {

			texture.updateMatrix();

		}

	}
```
</details>

### `TextureNode.clone(): TextureNode`

**JSDoc:**
```typescript
/**
	 * Clones the texture node.
	 *
	 * @return {TextureNode} The cloned texture node.
	 */
```

**Returns:** `TextureNode`

<details><summary>Code</summary>

```typescript
clone() {

		const newNode = new this.constructor( this.value, this.uvNode, this.levelNode, this.biasNode );
		newNode.sampler = this.sampler;
		newNode.depthNode = this.depthNode;
		newNode.compareNode = this.compareNode;
		newNode.gradNode = this.gradNode;

		return newNode;

	}
```
</details>

### `texture(value: Texture | TextureNode, uvNode: any, levelNode: any, biasNode: any): TextureNode`

**Parameters:**

- **`value`** `Texture | TextureNode`
- **`uvNode`** `any`
- **`levelNode`** `any`
- **`biasNode`** `any`

**Returns:** `TextureNode`

**Calls:**

- `nodeObject (from ../tsl/TSLBase.js)`
- `value.clone`
- `value.getSelf`
- `textureBase`

<details><summary>Code</summary>

```typescript
( value = EmptyTexture, uvNode = null, levelNode = null, biasNode = null ) => {

	let textureNode;

	if ( value && value.isTextureNode === true ) {

		textureNode = nodeObject( value.clone() );
		textureNode.referenceNode = value.getSelf(); // Ensure the reference is set to the original node

		if ( uvNode !== null ) textureNode.uvNode = nodeObject( uvNode );
		if ( levelNode !== null ) textureNode.levelNode = nodeObject( levelNode );
		if ( biasNode !== null ) textureNode.biasNode = nodeObject( biasNode );

	} else {

		textureNode = textureBase( value, uvNode, levelNode, biasNode );

	}

	return textureNode;

}
```
</details>

### `uniformTexture(value: Texture): TextureNode`

**Parameters:**

- **`value`** `Texture`

**Returns:** `TextureNode`

**Calls:**

- `texture`

<details><summary>Code</summary>

```typescript
( value = EmptyTexture ) => texture( value )
```
</details>

### `textureLoad(params: any[]): TextureNode`

**Parameters:**

- **`params`** `any[]`

**Returns:** `TextureNode`

**Calls:**

- `texture( ...params ).setSampler`

<details><summary>Code</summary>

```typescript
( ...params ) => texture( ...params ).setSampler( false )
```
</details>

### `sampler(value: Texture | TextureNode): Node`

**Parameters:**

- **`value`** `Texture | TextureNode`

**Returns:** `Node`

**Calls:**

- `( value.isNode === true ? value : texture( value ) ).convert`

<details><summary>Code</summary>

```typescript
( value ) => ( value.isNode === true ? value : texture( value ) ).convert( 'sampler' )
```
</details>

### `samplerComparison(value: Texture | TextureNode): Node`

**Parameters:**

- **`value`** `Texture | TextureNode`

**Returns:** `Node`

**Calls:**

- `( value.isNode === true ? value : texture( value ) ).convert`

<details><summary>Code</summary>

```typescript
( value ) => ( value.isNode === true ? value : texture( value ) ).convert( 'samplerComparison' )
```
</details>


---

## Classes

### `TextureNode`

<details><summary>Class Code</summary>

```ts
class TextureNode extends UniformNode {

	static get type() {

		return 'TextureNode';

	}

	/**
	 * Constructs a new texture node.
	 *
	 * @param {Texture} [value=EmptyTexture] - The texture.
	 * @param {?Node<vec2|vec3>} [uvNode=null] - The uv node.
	 * @param {?Node<int>} [levelNode=null] - The level node.
	 * @param {?Node<float>} [biasNode=null] - The bias node.
	 */
	constructor( value = EmptyTexture, uvNode = null, levelNode = null, biasNode = null ) {

		super( value );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isTextureNode = true;

		/**
		 * Represents the texture coordinates.
		 *
		 * @type {?Node<vec2|vec3>}
		 * @default null
		 */
		this.uvNode = uvNode;

		/**
		 * Represents the mip level that should be selected.
		 *
		 * @type {?Node<int>}
		 * @default null
		 */
		this.levelNode = levelNode;

		/**
		 * Represents the bias to be applied during level-of-detail computation.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.biasNode = biasNode;

		/**
		 * Represents a reference value a texture sample is compared to.
		 *
		 * @type {?Node<float>}
		 * @default null
		 */
		this.compareNode = null;

		/**
		 * When using texture arrays, the depth node defines the layer to select.
		 *
		 * @type {?Node<int>}
		 * @default null
		 */
		this.depthNode = null;

		/**
		 * When defined, a texture is sampled using explicit gradients.
		 *
		 * @type {?Array<Node<vec2>>}
		 * @default null
		 */
		this.gradNode = null;

		/**
		 * Whether texture values should be sampled or fetched.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.sampler = true;

		/**
		 * Whether the uv transformation matrix should be
		 * automatically updated or not. Use `setUpdateMatrix()`
		 * if you want to change the value of the property.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.updateMatrix = false;

		/**
		 * By default the `update()` method is not executed. `setUpdateMatrix()`
		 * sets the value to `frame` when the uv transformation matrix should
		 * automatically be updated.
		 *
		 * @type {string}
		 * @default 'none'
		 */
		this.updateType = NodeUpdateType.NONE;

		/**
		 * The reference node.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.referenceNode = null;

		/**
		 * The texture value is stored in a private property.
		 *
		 * @private
		 * @type {Texture}
		 */
		this._value = value;

		/**
		 * The uniform node that represents the uv transformation matrix.
		 *
		 * @private
		 * @type {?UniformNode<mat3>}
		 */
		this._matrixUniform = null;

		this.setUpdateMatrix( uvNode === null );

	}

	set value( value ) {

		if ( this.referenceNode ) {

			this.referenceNode.value = value;

		} else {

			this._value = value;

		}

	}

	/**
	 * The texture value.
	 *
	 * @type {Texture}
	 */
	get value() {

		return this.referenceNode ? this.referenceNode.value : this._value;

	}

	/**
	 * Overwritten since the uniform hash is defined by the texture's UUID.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The uniform hash.
	 */
	getUniformHash( /*builder*/ ) {

		return this.value.uuid;

	}

	/**
	 * Overwritten since the node type is inferred from the texture type.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The node type.
	 */
	getNodeType( /*builder*/ ) {

		if ( this.value.isDepthTexture === true ) return 'float';

		if ( this.value.type === UnsignedIntType ) {

			return 'uvec4';

		} else if ( this.value.type === IntType ) {

			return 'ivec4';

		}

		return 'vec4';

	}

	/**
	 * Overwrites the default implementation to return a fixed value `'texture'`.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @return {string} The input type.
	 */
	getInputType( /*builder*/ ) {

		return 'texture';

	}

	/**
	 * Returns a default uvs based on the current texture's channel.
	 *
	 * @return {AttributeNode<vec2>} The default uvs.
	 */
	getDefaultUV() {

		return uv( this.value.channel );

	}

	/**
	 * Overwritten to always return the texture reference of the node.
	 *
	 * @param {any} state - This method can be invocated in different contexts so `state` can refer to any object type.
	 * @return {Texture} The texture reference.
	 */
	updateReference( /*state*/ ) {

		return this.value;

	}

	/**
	 * Transforms the given uv node with the texture transformation matrix.
	 *
	 * @param {Node} uvNode - The uv node to transform.
	 * @return {Node} The transformed uv node.
	 */
	getTransformedUV( uvNode ) {

		if ( this._matrixUniform === null ) this._matrixUniform = uniform( this.value.matrix );

		return this._matrixUniform.mul( vec3( uvNode, 1 ) ).xy;

	}

	/**
	 * Defines whether the uv transformation matrix should automatically be updated or not.
	 *
	 * @param {boolean} value - The update toggle.
	 * @return {TextureNode} A reference to this node.
	 */
	setUpdateMatrix( value ) {

		this.updateMatrix = value;
		this.updateType = value ? NodeUpdateType.OBJECT : NodeUpdateType.NONE;

		return this;

	}

	/**
	 * Setups the uv node. Depending on the backend as well as texture's image and type, it might be necessary
	 * to modify the uv node for correct sampling.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {Node} uvNode - The uv node to setup.
	 * @return {Node} The updated uv node.
	 */
	setupUV( builder, uvNode ) {

		const texture = this.value;

		if ( builder.isFlipY() && ( ( texture.image instanceof ImageBitmap && texture.flipY === true ) || texture.isRenderTargetTexture === true || texture.isFramebufferTexture === true || texture.isDepthTexture === true ) ) {

			if ( this.sampler ) {

				uvNode = uvNode.flipY();

			} else {

				uvNode = uvNode.setY( int( textureSize( this, this.levelNode ).y ).sub( uvNode.y ).sub( 1 ) );

			}

		}

		return uvNode;

	}

	/**
	 * Setups texture node by preparing the internal nodes for code generation.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 */
	setup( builder ) {

		const properties = builder.getNodeProperties( this );
		properties.referenceNode = this.referenceNode;

		//

		const texture = this.value;

		if ( ! texture || texture.isTexture !== true ) {

			throw new Error( 'THREE.TSL: `texture( value )` function expects a valid instance of THREE.Texture().' );

		}

		//

		let uvNode = this.uvNode;

		if ( ( uvNode === null || builder.context.forceUVContext === true ) && builder.context.getUV ) {

			uvNode = builder.context.getUV( this, builder );

		}

		if ( ! uvNode ) uvNode = this.getDefaultUV();

		if ( this.updateMatrix === true ) {

			uvNode = this.getTransformedUV( uvNode );

		}

		uvNode = this.setupUV( builder, uvNode );

		//

		let levelNode = this.levelNode;

		if ( levelNode === null && builder.context.getTextureLevel ) {

			levelNode = builder.context.getTextureLevel( this );

		}

		//

		properties.uvNode = uvNode;
		properties.levelNode = levelNode;
		properties.biasNode = this.biasNode;
		properties.compareNode = this.compareNode;
		properties.gradNode = this.gradNode;
		properties.depthNode = this.depthNode;

	}

	/**
	 * Generates the uv code snippet.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {Node} uvNode - The uv node to generate code for.
	 * @return {string} The generated code snippet.
	 */
	generateUV( builder, uvNode ) {

		return uvNode.build( builder, this.sampler === true ? 'vec2' : 'ivec2' );

	}

	/**
	 * Generates the snippet for the texture sampling.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {string} textureProperty - The texture property.
	 * @param {string} uvSnippet - The uv snippet.
	 * @param {?string} levelSnippet - The level snippet.
	 * @param {?string} biasSnippet - The bias snippet.
	 * @param {?string} depthSnippet - The depth snippet.
	 * @param {?string} compareSnippet - The compare snippet.
	 * @param {?Array<string>} gradSnippet - The grad snippet.
	 * @return {string} The generated code snippet.
	 */
	generateSnippet( builder, textureProperty, uvSnippet, levelSnippet, biasSnippet, depthSnippet, compareSnippet, gradSnippet ) {

		const texture = this.value;

		let snippet;

		if ( levelSnippet ) {

			snippet = builder.generateTextureLevel( texture, textureProperty, uvSnippet, levelSnippet, depthSnippet );

		} else if ( biasSnippet ) {

			snippet = builder.generateTextureBias( texture, textureProperty, uvSnippet, biasSnippet, depthSnippet );

		} else if ( gradSnippet ) {

			snippet = builder.generateTextureGrad( texture, textureProperty, uvSnippet, gradSnippet, depthSnippet );

		} else if ( compareSnippet ) {

			snippet = builder.generateTextureCompare( texture, textureProperty, uvSnippet, compareSnippet, depthSnippet );

		} else if ( this.sampler === false ) {

			snippet = builder.generateTextureLoad( texture, textureProperty, uvSnippet, depthSnippet );

		} else {

			snippet = builder.generateTexture( texture, textureProperty, uvSnippet, depthSnippet );

		}

		return snippet;

	}

	/**
	 * Generates the code snippet of the texture node.
	 *
	 * @param {NodeBuilder} builder - The current node builder.
	 * @param {string} output - The current output.
	 * @return {string} The generated code snippet.
	 */
	generate( builder, output ) {

		const texture = this.value;

		const properties = builder.getNodeProperties( this );
		const textureProperty = super.generate( builder, 'property' );

		if ( /^sampler/.test( output ) ) {

			return textureProperty + '_sampler';

		} else if ( builder.isReference( output ) ) {

			return textureProperty;

		} else {

			const nodeData = builder.getDataFromNode( this );

			let propertyName = nodeData.propertyName;

			if ( propertyName === undefined ) {

				const { uvNode, levelNode, biasNode, compareNode, depthNode, gradNode } = properties;

				const uvSnippet = this.generateUV( builder, uvNode );
				const levelSnippet = levelNode ? levelNode.build( builder, 'float' ) : null;
				const biasSnippet = biasNode ? biasNode.build( builder, 'float' ) : null;
				const depthSnippet = depthNode ? depthNode.build( builder, 'int' ) : null;
				const compareSnippet = compareNode ? compareNode.build( builder, 'float' ) : null;
				const gradSnippet = gradNode ? [ gradNode[ 0 ].build( builder, 'vec2' ), gradNode[ 1 ].build( builder, 'vec2' ) ] : null;

				const nodeVar = builder.getVarFromNode( this );

				propertyName = builder.getPropertyName( nodeVar );

				const snippet = this.generateSnippet( builder, textureProperty, uvSnippet, levelSnippet, biasSnippet, depthSnippet, compareSnippet, gradSnippet );

				builder.addLineFlowCode( `${propertyName} = ${snippet}`, this );

				nodeData.snippet = snippet;
				nodeData.propertyName = propertyName;

			}

			let snippet = propertyName;
			const nodeType = this.getNodeType( builder );

			if ( builder.needsToWorkingColorSpace( texture ) ) {

				snippet = colorSpaceToWorking( expression( snippet, nodeType ), texture.colorSpace ).setup( builder ).build( builder, nodeType );

			}

			return builder.format( snippet, nodeType, output );

		}

	}

	/**
	 * Sets the sampler value.
	 *
	 * @param {boolean} value - The sampler value to set.
	 * @return {TextureNode} A reference to this texture node.
	 */
	setSampler( value ) {

		this.sampler = value;

		return this;

	}

	/**
	 * Returns the sampler value.
	 *
	 * @return {boolean} The sampler value.
	 */
	getSampler() {

		return this.sampler;

	}

	// @TODO: Move to TSL

	/**
	 * @function
	 * @deprecated since r172. Use {@link TextureNode#sample} instead.
	 *
	 * @param {Node} uvNode - The uv node.
	 * @return {TextureNode} A texture node representing the texture sample.
	 */
	uv( uvNode ) { // @deprecated, r172

		console.warn( 'THREE.TextureNode: .uv() has been renamed. Use .sample() instead.' );

		return this.sample( uvNode );

	}

	/**
	 * Samples the texture with the given uv node.
	 *
	 * @param {Node} uvNode - The uv node.
	 * @return {TextureNode} A texture node representing the texture sample.
	 */
	sample( uvNode ) {

		const textureNode = this.clone();
		textureNode.uvNode = nodeObject( uvNode );
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}

	/**
	 * TSL function for creating a texture node that fetches/loads texels without interpolation.
	 *
	 * @param {Node<uvec2>} uvNode - The uv node.
	 * @returns {TextureNode} A texture node representing the texture load.
	 */
	load( uvNode ) {

		return this.sample( uvNode ).setSampler( false );

	}

	/**
	 * Samples a blurred version of the texture by defining an internal bias.
	 *
	 * @param {Node<float>} amountNode - How blurred the texture should be.
	 * @return {TextureNode} A texture node representing the texture sample.
	 */
	blur( amountNode ) {

		const textureNode = this.clone();
		textureNode.biasNode = nodeObject( amountNode ).mul( maxMipLevel( textureNode ) );
		textureNode.referenceNode = this.getSelf();

		const map = textureNode.value;

		if ( textureNode.generateMipmaps === false && ( map && map.generateMipmaps === false || map.minFilter === NearestFilter || map.magFilter === NearestFilter ) ) {

			console.warn( 'THREE.TSL: texture().blur() requires mipmaps and sampling. Use .generateMipmaps=true and .minFilter/.magFilter=THREE.LinearFilter in the Texture.' );

			textureNode.biasNode = null;

		}

		return nodeObject( textureNode );

	}

	/**
	 * Samples a specific mip of the texture.
	 *
	 * @param {Node<int>} levelNode - The mip level to sample.
	 * @return {TextureNode} A texture node representing the texture sample.
	 */
	level( levelNode ) {

		const textureNode = this.clone();
		textureNode.levelNode = nodeObject( levelNode );
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}

	/**
	 * Returns the texture size of the requested level.
	 *
	 * @param {Node<int>} levelNode - The level to compute the size for.
	 * @return {TextureSizeNode} The texture size.
	 */
	size( levelNode ) {

		return textureSize( this, levelNode );

	}

	/**
	 * Samples the texture with the given bias.
	 *
	 * @param {Node<float>} biasNode - The bias node.
	 * @return {TextureNode} A texture node representing the texture sample.
	 */
	bias( biasNode ) {

		const textureNode = this.clone();
		textureNode.biasNode = nodeObject( biasNode );
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}

	/**
	 * Samples the texture by executing a compare operation.
	 *
	 * @param {Node<float>} compareNode - The node that defines the compare value.
	 * @return {TextureNode} A texture node representing the texture sample.
	 */
	compare( compareNode ) {

		const textureNode = this.clone();
		textureNode.compareNode = nodeObject( compareNode );
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}

	/**
	 * Samples the texture using an explicit gradient.
	 *
	 * @param {Node<vec2>} gradNodeX - The gradX node.
	 * @param {Node<vec2>} gradNodeY - The gradY node.
	 * @return {TextureNode} A texture node representing the texture sample.
	 */
	grad( gradNodeX, gradNodeY ) {

		const textureNode = this.clone();
		textureNode.gradNode = [ nodeObject( gradNodeX ), nodeObject( gradNodeY ) ];
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}

	/**
	 * Samples the texture by defining a depth node.
	 *
	 * @param {Node<int>} depthNode - The depth node.
	 * @return {TextureNode} A texture node representing the texture sample.
	 */
	depth( depthNode ) {

		const textureNode = this.clone();
		textureNode.depthNode = nodeObject( depthNode );
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}

	// --

	serialize( data ) {

		super.serialize( data );

		data.value = this.value.toJSON( data.meta ).uuid;
		data.sampler = this.sampler;
		data.updateMatrix = this.updateMatrix;
		data.updateType = this.updateType;

	}

	deserialize( data ) {

		super.deserialize( data );

		this.value = data.meta.textures[ data.value ];
		this.sampler = data.sampler;
		this.updateMatrix = data.updateMatrix;
		this.updateType = data.updateType;

	}

	/**
	 * The update is used to implement the update of the uv transformation matrix.
	 */
	update() {

		const texture = this.value;
		const matrixUniform = this._matrixUniform;

		if ( matrixUniform !== null ) matrixUniform.value = texture.matrix;

		if ( texture.matrixAutoUpdate === true ) {

			texture.updateMatrix();

		}

	}

	/**
	 * Clones the texture node.
	 *
	 * @return {TextureNode} The cloned texture node.
	 */
	clone() {

		const newNode = new this.constructor( this.value, this.uvNode, this.levelNode, this.biasNode );
		newNode.sampler = this.sampler;
		newNode.depthNode = this.depthNode;
		newNode.compareNode = this.compareNode;
		newNode.gradNode = this.gradNode;

		return newNode;

	}

}
```
</details>

#### Methods

##### `getUniformHash(): string`

<details><summary>Code</summary>

```ts
getUniformHash( /*builder*/ ) {

		return this.value.uuid;

	}
```
</details>

##### `getNodeType(): string`

<details><summary>Code</summary>

```ts
getNodeType( /*builder*/ ) {

		if ( this.value.isDepthTexture === true ) return 'float';

		if ( this.value.type === UnsignedIntType ) {

			return 'uvec4';

		} else if ( this.value.type === IntType ) {

			return 'ivec4';

		}

		return 'vec4';

	}
```
</details>

##### `getInputType(): string`

<details><summary>Code</summary>

```ts
getInputType( /*builder*/ ) {

		return 'texture';

	}
```
</details>

##### `getDefaultUV(): AttributeNode<vec2>`

<details><summary>Code</summary>

```ts
getDefaultUV() {

		return uv( this.value.channel );

	}
```
</details>

##### `updateReference(): Texture`

<details><summary>Code</summary>

```ts
updateReference( /*state*/ ) {

		return this.value;

	}
```
</details>

##### `getTransformedUV(uvNode: Node): Node`

<details><summary>Code</summary>

```ts
getTransformedUV( uvNode ) {

		if ( this._matrixUniform === null ) this._matrixUniform = uniform( this.value.matrix );

		return this._matrixUniform.mul( vec3( uvNode, 1 ) ).xy;

	}
```
</details>

##### `setUpdateMatrix(value: boolean): TextureNode`

<details><summary>Code</summary>

```ts
setUpdateMatrix( value ) {

		this.updateMatrix = value;
		this.updateType = value ? NodeUpdateType.OBJECT : NodeUpdateType.NONE;

		return this;

	}
```
</details>

##### `setupUV(builder: NodeBuilder, uvNode: Node): Node`

<details><summary>Code</summary>

```ts
setupUV( builder, uvNode ) {

		const texture = this.value;

		if ( builder.isFlipY() && ( ( texture.image instanceof ImageBitmap && texture.flipY === true ) || texture.isRenderTargetTexture === true || texture.isFramebufferTexture === true || texture.isDepthTexture === true ) ) {

			if ( this.sampler ) {

				uvNode = uvNode.flipY();

			} else {

				uvNode = uvNode.setY( int( textureSize( this, this.levelNode ).y ).sub( uvNode.y ).sub( 1 ) );

			}

		}

		return uvNode;

	}
```
</details>

##### `setup(builder: NodeBuilder): void`

<details><summary>Code</summary>

```ts
setup( builder ) {

		const properties = builder.getNodeProperties( this );
		properties.referenceNode = this.referenceNode;

		//

		const texture = this.value;

		if ( ! texture || texture.isTexture !== true ) {

			throw new Error( 'THREE.TSL: `texture( value )` function expects a valid instance of THREE.Texture().' );

		}

		//

		let uvNode = this.uvNode;

		if ( ( uvNode === null || builder.context.forceUVContext === true ) && builder.context.getUV ) {

			uvNode = builder.context.getUV( this, builder );

		}

		if ( ! uvNode ) uvNode = this.getDefaultUV();

		if ( this.updateMatrix === true ) {

			uvNode = this.getTransformedUV( uvNode );

		}

		uvNode = this.setupUV( builder, uvNode );

		//

		let levelNode = this.levelNode;

		if ( levelNode === null && builder.context.getTextureLevel ) {

			levelNode = builder.context.getTextureLevel( this );

		}

		//

		properties.uvNode = uvNode;
		properties.levelNode = levelNode;
		properties.biasNode = this.biasNode;
		properties.compareNode = this.compareNode;
		properties.gradNode = this.gradNode;
		properties.depthNode = this.depthNode;

	}
```
</details>

##### `generateUV(builder: NodeBuilder, uvNode: Node): string`

<details><summary>Code</summary>

```ts
generateUV( builder, uvNode ) {

		return uvNode.build( builder, this.sampler === true ? 'vec2' : 'ivec2' );

	}
```
</details>

##### `generateSnippet(builder: NodeBuilder, textureProperty: string, uvSnippet: string, levelSnippet: string, biasSnippet: string, depthSnippet: string, compareSnippet: string, gradSnippet: string[]): string`

<details><summary>Code</summary>

```ts
generateSnippet( builder, textureProperty, uvSnippet, levelSnippet, biasSnippet, depthSnippet, compareSnippet, gradSnippet ) {

		const texture = this.value;

		let snippet;

		if ( levelSnippet ) {

			snippet = builder.generateTextureLevel( texture, textureProperty, uvSnippet, levelSnippet, depthSnippet );

		} else if ( biasSnippet ) {

			snippet = builder.generateTextureBias( texture, textureProperty, uvSnippet, biasSnippet, depthSnippet );

		} else if ( gradSnippet ) {

			snippet = builder.generateTextureGrad( texture, textureProperty, uvSnippet, gradSnippet, depthSnippet );

		} else if ( compareSnippet ) {

			snippet = builder.generateTextureCompare( texture, textureProperty, uvSnippet, compareSnippet, depthSnippet );

		} else if ( this.sampler === false ) {

			snippet = builder.generateTextureLoad( texture, textureProperty, uvSnippet, depthSnippet );

		} else {

			snippet = builder.generateTexture( texture, textureProperty, uvSnippet, depthSnippet );

		}

		return snippet;

	}
```
</details>

##### `generate(builder: NodeBuilder, output: string): string`

<details><summary>Code</summary>

```ts
generate( builder, output ) {

		const texture = this.value;

		const properties = builder.getNodeProperties( this );
		const textureProperty = super.generate( builder, 'property' );

		if ( /^sampler/.test( output ) ) {

			return textureProperty + '_sampler';

		} else if ( builder.isReference( output ) ) {

			return textureProperty;

		} else {

			const nodeData = builder.getDataFromNode( this );

			let propertyName = nodeData.propertyName;

			if ( propertyName === undefined ) {

				const { uvNode, levelNode, biasNode, compareNode, depthNode, gradNode } = properties;

				const uvSnippet = this.generateUV( builder, uvNode );
				const levelSnippet = levelNode ? levelNode.build( builder, 'float' ) : null;
				const biasSnippet = biasNode ? biasNode.build( builder, 'float' ) : null;
				const depthSnippet = depthNode ? depthNode.build( builder, 'int' ) : null;
				const compareSnippet = compareNode ? compareNode.build( builder, 'float' ) : null;
				const gradSnippet = gradNode ? [ gradNode[ 0 ].build( builder, 'vec2' ), gradNode[ 1 ].build( builder, 'vec2' ) ] : null;

				const nodeVar = builder.getVarFromNode( this );

				propertyName = builder.getPropertyName( nodeVar );

				const snippet = this.generateSnippet( builder, textureProperty, uvSnippet, levelSnippet, biasSnippet, depthSnippet, compareSnippet, gradSnippet );

				builder.addLineFlowCode( `${propertyName} = ${snippet}`, this );

				nodeData.snippet = snippet;
				nodeData.propertyName = propertyName;

			}

			let snippet = propertyName;
			const nodeType = this.getNodeType( builder );

			if ( builder.needsToWorkingColorSpace( texture ) ) {

				snippet = colorSpaceToWorking( expression( snippet, nodeType ), texture.colorSpace ).setup( builder ).build( builder, nodeType );

			}

			return builder.format( snippet, nodeType, output );

		}

	}
```
</details>

##### `setSampler(value: boolean): TextureNode`

<details><summary>Code</summary>

```ts
setSampler( value ) {

		this.sampler = value;

		return this;

	}
```
</details>

##### `getSampler(): boolean`

<details><summary>Code</summary>

```ts
getSampler() {

		return this.sampler;

	}
```
</details>

##### `uv(uvNode: Node): TextureNode`

<details><summary>Code</summary>

```ts
uv( uvNode ) { // @deprecated, r172

		console.warn( 'THREE.TextureNode: .uv() has been renamed. Use .sample() instead.' );

		return this.sample( uvNode );

	}
```
</details>

##### `sample(uvNode: Node): TextureNode`

<details><summary>Code</summary>

```ts
sample( uvNode ) {

		const textureNode = this.clone();
		textureNode.uvNode = nodeObject( uvNode );
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}
```
</details>

##### `load(uvNode: any): TextureNode`

<details><summary>Code</summary>

```ts
load( uvNode ) {

		return this.sample( uvNode ).setSampler( false );

	}
```
</details>

##### `blur(amountNode: any): TextureNode`

<details><summary>Code</summary>

```ts
blur( amountNode ) {

		const textureNode = this.clone();
		textureNode.biasNode = nodeObject( amountNode ).mul( maxMipLevel( textureNode ) );
		textureNode.referenceNode = this.getSelf();

		const map = textureNode.value;

		if ( textureNode.generateMipmaps === false && ( map && map.generateMipmaps === false || map.minFilter === NearestFilter || map.magFilter === NearestFilter ) ) {

			console.warn( 'THREE.TSL: texture().blur() requires mipmaps and sampling. Use .generateMipmaps=true and .minFilter/.magFilter=THREE.LinearFilter in the Texture.' );

			textureNode.biasNode = null;

		}

		return nodeObject( textureNode );

	}
```
</details>

##### `level(levelNode: any): TextureNode`

<details><summary>Code</summary>

```ts
level( levelNode ) {

		const textureNode = this.clone();
		textureNode.levelNode = nodeObject( levelNode );
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}
```
</details>

##### `size(levelNode: any): TextureSizeNode`

<details><summary>Code</summary>

```ts
size( levelNode ) {

		return textureSize( this, levelNode );

	}
```
</details>

##### `bias(biasNode: any): TextureNode`

<details><summary>Code</summary>

```ts
bias( biasNode ) {

		const textureNode = this.clone();
		textureNode.biasNode = nodeObject( biasNode );
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}
```
</details>

##### `compare(compareNode: any): TextureNode`

<details><summary>Code</summary>

```ts
compare( compareNode ) {

		const textureNode = this.clone();
		textureNode.compareNode = nodeObject( compareNode );
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}
```
</details>

##### `grad(gradNodeX: any, gradNodeY: any): TextureNode`

<details><summary>Code</summary>

```ts
grad( gradNodeX, gradNodeY ) {

		const textureNode = this.clone();
		textureNode.gradNode = [ nodeObject( gradNodeX ), nodeObject( gradNodeY ) ];
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}
```
</details>

##### `depth(depthNode: any): TextureNode`

<details><summary>Code</summary>

```ts
depth( depthNode ) {

		const textureNode = this.clone();
		textureNode.depthNode = nodeObject( depthNode );
		textureNode.referenceNode = this.getSelf();

		return nodeObject( textureNode );

	}
```
</details>

##### `serialize(data: any): void`

<details><summary>Code</summary>

```ts
serialize( data ) {

		super.serialize( data );

		data.value = this.value.toJSON( data.meta ).uuid;
		data.sampler = this.sampler;
		data.updateMatrix = this.updateMatrix;
		data.updateType = this.updateType;

	}
```
</details>

##### `deserialize(data: any): void`

<details><summary>Code</summary>

```ts
deserialize( data ) {

		super.deserialize( data );

		this.value = data.meta.textures[ data.value ];
		this.sampler = data.sampler;
		this.updateMatrix = data.updateMatrix;
		this.updateType = data.updateType;

	}
```
</details>

##### `update(): void`

<details><summary>Code</summary>

```ts
update() {

		const texture = this.value;
		const matrixUniform = this._matrixUniform;

		if ( matrixUniform !== null ) matrixUniform.value = texture.matrix;

		if ( texture.matrixAutoUpdate === true ) {

			texture.updateMatrix();

		}

	}
```
</details>

##### `clone(): TextureNode`

<details><summary>Code</summary>

```ts
clone() {

		const newNode = new this.constructor( this.value, this.uvNode, this.levelNode, this.biasNode );
		newNode.sampler = this.sampler;
		newNode.depthNode = this.depthNode;
		newNode.compareNode = this.compareNode;
		newNode.gradNode = this.gradNode;

		return newNode;

	}
```
</details>


---