[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `NodeBuilder.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 126 |
| 🧱 Classes | 1 |
| 📦 Imports | 41 |
| 📊 Variables & Constants | 84 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/nodes/core/NodeBuilder.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeUniform` | `./NodeUniform.js` |
| `NodeAttribute` | `./NodeAttribute.js` |
| `NodeVarying` | `./NodeVarying.js` |
| `NodeVar` | `./NodeVar.js` |
| `NodeCode` | `./NodeCode.js` |
| `NodeCache` | `./NodeCache.js` |
| `ParameterNode` | `./ParameterNode.js` |
| `StructType` | `./StructType.js` |
| `FunctionNode` | `../code/FunctionNode.js` |
| `NodeMaterial` | `../../materials/nodes/NodeMaterial.js` |
| `getTypeFromLength` | `./NodeUtils.js` |
| `NodeUpdateType` | `./constants.js` |
| `defaultBuildStages` | `./constants.js` |
| `shaderStages` | `./constants.js` |
| `NumberNodeUniform` | `../../renderers/common/nodes/NodeUniform.js` |
| `Vector2NodeUniform` | `../../renderers/common/nodes/NodeUniform.js` |
| `Vector3NodeUniform` | `../../renderers/common/nodes/NodeUniform.js` |
| `Vector4NodeUniform` | `../../renderers/common/nodes/NodeUniform.js` |
| `ColorNodeUniform` | `../../renderers/common/nodes/NodeUniform.js` |
| `Matrix2NodeUniform` | `../../renderers/common/nodes/NodeUniform.js` |
| `Matrix3NodeUniform` | `../../renderers/common/nodes/NodeUniform.js` |
| `Matrix4NodeUniform` | `../../renderers/common/nodes/NodeUniform.js` |
| `stack` | `./StackNode.js` |
| `getCurrentStack` | `../tsl/TSLBase.js` |
| `setCurrentStack` | `../tsl/TSLBase.js` |
| `CubeRenderTarget` | `../../renderers/common/CubeRenderTarget.js` |
| `ChainMap` | `../../renderers/common/ChainMap.js` |
| `BindGroup` | `../../renderers/common/BindGroup.js` |
| `REVISION` | `../../constants.js` |
| `IntType` | `../../constants.js` |
| `UnsignedIntType` | `../../constants.js` |
| `LinearFilter` | `../../constants.js` |
| `LinearMipmapNearestFilter` | `../../constants.js` |
| `NearestMipmapLinearFilter` | `../../constants.js` |
| `LinearMipmapLinearFilter` | `../../constants.js` |
| `RenderTarget` | `../../core/RenderTarget.js` |
| `Color` | `../../math/Color.js` |
| `Vector2` | `../../math/Vector2.js` |
| `Vector3` | `../../math/Vector3.js` |
| `Vector4` | `../../math/Vector4.js` |
| `Float16BufferAttribute` | `../../core/BufferAttribute.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `rendererCache` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `typeFromArray` | `Map<Int8ArrayConstructor, string>` | let/var | `new Map( [ [ Int8Array, 'int' ], [ Int16Array, 'int' ], [ Int32Array, 'int' ]...` | ✗ |
| `bindingsArray` | `any[]` | let/var | `[]` | ✗ |
| `sharedGroup` | `boolean` | let/var | `true` | ✗ |
| `bindGroup` | `any` | let/var | `*not shown*` | ✗ |
| `bindings` | `any` | let/var | `this.bindings[ shaderStage ]` | ✗ |
| `bindGroup` | `any` | let/var | `bindings[ groupName ]` | ✗ |
| `bindingsGroups` | `BindGroup[]` | let/var | `this.bindGroups` | ✗ |
| `groups` | `{}` | let/var | `{}` | ✗ |
| `bindings` | `any` | let/var | `this.bindings` | ✗ |
| `uniforms` | `any` | let/var | `bindings[ shaderStage ][ groupName ]` | ✗ |
| `groupUniforms` | `any` | let/var | `groups[ groupName ] \|\| ( groups[ groupName ] = [] )` | ✗ |
| `group` | `any` | let/var | `groups[ groupName ]` | ✗ |
| `bindingGroup` | `BindGroup` | let/var | `bindingsGroups[ i ]` | ✗ |
| `context` | `any` | let/var | `{ ...this.context }` | ✗ |
| `snippet` | `string` | let/var | `this.generateArrayDeclaration( type, count ) + '( '` | ✗ |
| `value` | `Node` | let/var | `values ? values[ i ] : null` | ✗ |
| `snippets` | `any[]` | let/var | `[]` | ✗ |
| `attributes` | `NodeAttribute[]` | let/var | `this.attributes` | ✗ |
| `attribute` | `NodeAttribute` | let/var | `new NodeAttribute( name, type )` | ✗ |
| `type` | `any` | let/var | `texture.type` | ✗ |
| `prefix` | `string` | let/var | `componentType === 'float' ? '' : componentType[ 0 ]` | ✗ |
| `dataAttribute` | `BufferAttribute` | let/var | `attribute` | ✗ |
| `array` | `any` | let/var | `dataAttribute.array` | ✗ |
| `itemSize` | `any` | let/var | `attribute.itemSize` | ✗ |
| `normalized` | `any` | let/var | `attribute.normalized` | ✗ |
| `arrayType` | `any` | let/var | `*not shown*` | ✗ |
| `lastStack` | `StackNode` | let/var | `this.stack` | ✗ |
| `data` | `any` | let/var | `nodeData[ shaderStage ]` | ✗ |
| `subBuilds` | `any` | let/var | `nodeData.any ? nodeData.any.subBuilds : null` | ✗ |
| `bufferAttribute` | `any` | let/var | `nodeData.bufferAttribute` | ✗ |
| `index` | `number` | let/var | `this.uniforms.index ++` | ✗ |
| `structType` | `any` | let/var | `nodeData.structType` | ✗ |
| `index` | `number` | let/var | `this.structs.index ++` | ✗ |
| `nodeUniform` | `any` | let/var | `nodeData.uniform` | ✗ |
| `index` | `number` | let/var | `this.uniforms.index ++` | ✗ |
| `nodeVar` | `any` | let/var | `nodeData[ subBuildVariable ]` | ✗ |
| `idNS` | `"_const" \| "_var"` | let/var | `readOnly ? '_const' : '_var'` | ✗ |
| `vars` | `number \| NodeVar[]` | let/var | `this.vars[ shaderStage ] \|\| ( this.vars[ shaderStage ] = [] )` | ✗ |
| `id` | `number \| NodeVar[]` | let/var | `this.vars[ idNS ] \|\| ( this.vars[ idNS ] = 0 )` | ✗ |
| `nodeVarying` | `any` | let/var | `nodeData[ subBuildVarying ]` | ✗ |
| `varyings` | `NodeVarying[]` | let/var | `this.varyings` | ✗ |
| `index` | `number` | let/var | `varyings.length` | ✗ |
| `shaderStage` | `"compute" \| "vertex" \| "fragment" \...` | let/var | `this.shaderStage` | ✗ |
| `declarations` | `any` | let/var | `this.declarations[ shaderStage ] \|\| ( this.declarations[ shaderStage ] = {} )` | ✗ |
| `index` | `number` | let/var | `1` | ✗ |
| `name` | `string` | let/var | `property` | ✗ |
| `nodeCode` | `any` | let/var | `nodeData.code` | ✗ |
| `codes` | `NodeCode[]` | let/var | `this.codes[ shaderStage ] \|\| ( this.codes[ shaderStage ] = [] )` | ✗ |
| `index` | `number` | let/var | `codes.length` | ✗ |
| `needsFlowCode` | `boolean` | let/var | `true` | ✗ |
| `nodeBlockHierarchy` | `Node` | let/var | `nodeBlock` | ✗ |
| `flowCodes` | `any` | let/var | `nodeData.flowCodes \|\| ( nodeData.flowCodes = [] )` | ✗ |
| `codeBlock` | `any` | let/var | `nodeData.flowCodeBlock \|\| ( nodeData.flowCodeBlock = new WeakMap() )` | ✗ |
| `fn` | `FunctionNode` | let/var | `new FunctionNode()` | ✗ |
| `previous` | `FunctionNode` | let/var | `this.currentFunctionNode` | ✗ |
| `layout` | `any` | let/var | `shaderNode.layout` | ✗ |
| `index` | `number` | let/var | `0` | ✗ |
| `inputs` | `{ [Symbol.iterator](): { next: () => ...` | let/var | `{ [ Symbol.iterator ]() { let index = 0; const values = Object.values( this )...` | ✗ |
| `previousFlow` | `{ code: string; }` | let/var | `this.flow` | ✗ |
| `previousVars` | `{ [x: string]: number \| NodeVar[]; }` | let/var | `this.vars` | ✗ |
| `previousDeclarations` | `any` | let/var | `this.declarations` | ✗ |
| `previousCache` | `NodeCache` | let/var | `this.cache` | ✗ |
| `previousBuildStage` | `"setup" \| "generate" \| "analyze"` | let/var | `this.buildStage` | ✗ |
| `previousStack` | `StackNode` | let/var | `this.stack` | ✗ |
| `flow` | `{ code: string; }` | let/var | `{ code: '' }` | ✗ |
| `previousFlow` | `{ code: string; }` | let/var | `this.flow` | ✗ |
| `flow` | `{ code: string; }` | let/var | `{ code: '' }` | ✗ |
| `previousTab` | `string` | let/var | `this.tab` | ✗ |
| `previousCache` | `NodeCache` | let/var | `this.cache` | ✗ |
| `previousShaderStage` | `"compute" \| "vertex" \| "fragment" \...` | let/var | `this.shaderStage` | ✗ |
| `previousContext` | `any` | let/var | `this.context` | ✗ |
| `context` | `any` | let/var | `{ ...this.context }` | ✗ |
| `result` | `any` | let/var | `null` | ✗ |
| `snippet` | `string` | let/var | `''` | ✗ |
| `vars` | `number \| NodeVar[]` | let/var | `this.vars[ shaderStage ]` | ✗ |
| `codes` | `NodeCode[]` | let/var | `this.codes[ shaderStage ]` | ✗ |
| `code` | `string` | let/var | `''` | ✗ |
| `subBuilds` | `any` | let/var | `*not shown*` | ✗ |
| `subBuildLayers` | `SubBuildNode[]` | let/var | `this.subBuildLayers` | ✗ |
| `subBuild` | `any` | let/var | `subBuilds[ i ]` | ✗ |
| `subBuild` | `any` | let/var | `*not shown*` | ✗ |
| `result` | `any` | let/var | `*not shown*` | ✗ |
| `flowNodes` | `Node[]` | let/var | `this.flowNodes[ shaderStage ]` | ✗ |


---

## Functions

### `toFloat(value: any): string`

**Parameters:**

- **`value`** `any`

**Returns:** `string`

**Calls:**

- `/e/g.test`
- `String( value ).replace`
- `Number`

<details><summary>Code</summary>

```typescript
( value ) => {

	if ( /e/g.test( value ) ) {

		return String( value ).replace( /\+/g, '' );

	} else {

		value = Number( value );

		return value + ( value % 1 ? '' : '.0' );

	}

}
```
</details>

### `NodeBuilder.getBindGroupsCache(): ChainMap`

**JSDoc:**
```typescript
/**
	 * Returns the bind groups of the current renderer.
	 *
	 * @return {ChainMap} The cache.
	 */
```

**Returns:** `ChainMap`

**Calls:**

- `rendererCache.get`
- `rendererCache.set`

<details><summary>Code</summary>

```typescript
getBindGroupsCache() {

		let bindGroupsCache = rendererCache.get( this.renderer );

		if ( bindGroupsCache === undefined ) {

			bindGroupsCache = new ChainMap();

			rendererCache.set( this.renderer, bindGroupsCache );

		}

		return bindGroupsCache;

	}
```
</details>

### `NodeBuilder.createRenderTarget(width: number, height: number, options: any): RenderTarget`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of {@link RenderTarget} with the given
	 * dimensions and options.
	 *
	 * @param {number} width - The width of the render target.
	 * @param {number} height - The height of the render target.
	 * @param {Object} options - The options of the render target.
	 * @return {RenderTarget} The render target.
	 */
```

**Parameters:**

- **`width`** `number`
- **`height`** `number`
- **`options`** `any`

**Returns:** `RenderTarget`

<details><summary>Code</summary>

```typescript
createRenderTarget( width, height, options ) {

		return new RenderTarget( width, height, options );

	}
```
</details>

### `NodeBuilder.createCubeRenderTarget(size: number, options: any): CubeRenderTarget`

**JSDoc:**
```typescript
/**
	 * Factory method for creating an instance of {@link CubeRenderTarget} with the given
	 * dimensions and options.
	 *
	 * @param {number} size - The size of the cube render target.
	 * @param {Object} options - The options of the cube render target.
	 * @return {CubeRenderTarget} The cube render target.
	 */
```

**Parameters:**

- **`size`** `number`
- **`options`** `any`

**Returns:** `CubeRenderTarget`

<details><summary>Code</summary>

```typescript
createCubeRenderTarget( size, options ) {

		return new CubeRenderTarget( size, options );

	}
```
</details>

### `NodeBuilder.includes(node: Node): boolean`

**JSDoc:**
```typescript
/**
	 * Whether the given node is included in the internal array of nodes or not.
	 *
	 * @param {Node} node - The node to test.
	 * @return {boolean} Whether the given node is included in the internal array of nodes or not.
	 */
```

**Parameters:**

- **`node`** `Node`

**Returns:** `boolean`

**Calls:**

- `this.nodes.includes`

<details><summary>Code</summary>

```typescript
includes( node ) {

		return this.nodes.includes( node );

	}
```
</details>

### `NodeBuilder.getOutputStructName(): string`

**JSDoc:**
```typescript
/**
	 * Returns the output struct name which is required by
	 * {@link OutputStructNode}.
	 *
	 * @abstract
	 * @return {string} The name of the output struct.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getOutputStructName() {}
```
</details>

### `NodeBuilder._getBindGroup(groupName: string, bindings: NodeUniformsGroup[]): BindGroup`

**JSDoc:**
```typescript
/**
	 * Returns a bind group for the given group name and binding.
	 *
	 * @private
	 * @param {string} groupName - The group name.
	 * @param {Array<NodeUniformsGroup>} bindings - List of bindings.
	 * @return {BindGroup} The bind group
	 */
```

**Parameters:**

- **`groupName`** `string`
- **`bindings`** `NodeUniformsGroup[]`

**Returns:** `BindGroup`

**Calls:**

- `this.getBindGroupsCache`
- `bindingsArray.push`
- `bindGroupsCache.get`
- `bindGroupsCache.set`

**Internal Comments:**
```
// (x4)
```

<details><summary>Code</summary>

```typescript
_getBindGroup( groupName, bindings ) {

		const bindGroupsCache = this.getBindGroupsCache();

		//

		const bindingsArray = [];

		let sharedGroup = true;

		for ( const binding of bindings ) {

			bindingsArray.push( binding );

			sharedGroup = sharedGroup && binding.groupNode.shared !== true;

		}

		//

		let bindGroup;

		if ( sharedGroup ) {

			bindGroup = bindGroupsCache.get( bindingsArray );

			if ( bindGroup === undefined ) {

				bindGroup = new BindGroup( groupName, bindingsArray, this.bindingsIndexes[ groupName ].group, bindingsArray );

				bindGroupsCache.set( bindingsArray, bindGroup );

			}

		} else {

			bindGroup = new BindGroup( groupName, bindingsArray, this.bindingsIndexes[ groupName ].group, bindingsArray );

		}

		return bindGroup;

	}
```
</details>

### `NodeBuilder.getBindGroupArray(groupName: string, shaderStage: "compute" | "vertex" | "fragment" | "any"): NodeUniformsGroup[]`

**JSDoc:**
```typescript
/**
	 * Returns an array of node uniform groups for the given group name and shader stage.
	 *
	 * @param {string} groupName - The group name.
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @return {Array<NodeUniformsGroup>} The array of node uniform groups.
	 */
```

**Parameters:**

- **`groupName`** `string`
- **`shaderStage`** `"compute" | "vertex" | "fragment" | "any"`

**Returns:** `NodeUniformsGroup[]`

**Calls:**

- `Object.keys`

<details><summary>Code</summary>

```typescript
getBindGroupArray( groupName, shaderStage ) {

		const bindings = this.bindings[ shaderStage ];

		let bindGroup = bindings[ groupName ];

		if ( bindGroup === undefined ) {

			if ( this.bindingsIndexes[ groupName ] === undefined ) {

				this.bindingsIndexes[ groupName ] = { binding: 0, group: Object.keys( this.bindingsIndexes ).length };

			}

			bindings[ groupName ] = bindGroup = [];

		}

		return bindGroup;

	}
```
</details>

### `NodeBuilder.getBindings(): BindGroup[]`

**JSDoc:**
```typescript
/**
	 * Returns a list bindings of all shader stages separated by groups.
	 *
	 * @return {Array<BindGroup>} The list of bindings.
	 */
```

**Returns:** `BindGroup[]`

**Calls:**

- `groupUniforms.push`
- `this._getBindGroup`
- `bindingsGroups.push`

<details><summary>Code</summary>

```typescript
getBindings() {

		let bindingsGroups = this.bindGroups;

		if ( bindingsGroups === null ) {

			const groups = {};
			const bindings = this.bindings;

			for ( const shaderStage of shaderStages ) {

				for ( const groupName in bindings[ shaderStage ] ) {

					const uniforms = bindings[ shaderStage ][ groupName ];

					const groupUniforms = groups[ groupName ] || ( groups[ groupName ] = [] );
					groupUniforms.push( ...uniforms );

				}

			}

			bindingsGroups = [];

			for ( const groupName in groups ) {

				const group = groups[ groupName ];

				const bindingsGroup = this._getBindGroup( groupName, group );

				bindingsGroups.push( bindingsGroup );

			}

			this.bindGroups = bindingsGroups;

		}

		return bindingsGroups;

	}
```
</details>

### `NodeBuilder.sortBindingGroups(): void`

**JSDoc:**
```typescript
/**
	 * Sorts the bind groups and updates {@link NodeBuilder#bindingsIndexes}.
	 */
```

**Returns:** `void`

**Calls:**

- `this.getBindings`
- `bindingsGroups.sort`

<details><summary>Code</summary>

```typescript
sortBindingGroups() {

		const bindingsGroups = this.getBindings();

		bindingsGroups.sort( ( a, b ) => ( a.bindings[ 0 ].groupNode.order - b.bindings[ 0 ].groupNode.order ) );

		for ( let i = 0; i < bindingsGroups.length; i ++ ) {

			const bindingGroup = bindingsGroups[ i ];
			this.bindingsIndexes[ bindingGroup.name ].group = i;

			bindingGroup.index = i;

		}

	}
```
</details>

### `NodeBuilder.setHashNode(node: Node, hash: number): void`

**JSDoc:**
```typescript
/**
	 * The builder maintains each node in a hash-based dictionary.
	 * This method sets the given node (value) with the given hash (key) into this dictionary.
	 *
	 * @param {Node} node - The node to add.
	 * @param {number} hash - The hash of the node.
	 */
```

**Parameters:**

- **`node`** `Node`
- **`hash`** `number`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setHashNode( node, hash ) {

		this.hashNodes[ hash ] = node;

	}
```
</details>

### `NodeBuilder.addNode(node: Node): void`

**JSDoc:**
```typescript
/**
	 * Adds a node to this builder.
	 *
	 * @param {Node} node - The node to add.
	 */
```

**Parameters:**

- **`node`** `Node`

**Returns:** `void`

**Calls:**

- `this.nodes.includes`
- `this.nodes.push`
- `this.setHashNode`
- `node.getHash`

<details><summary>Code</summary>

```typescript
addNode( node ) {

		if ( this.nodes.includes( node ) === false ) {

			this.nodes.push( node );

			this.setHashNode( node, node.getHash( this ) );

		}

	}
```
</details>

### `NodeBuilder.addSequentialNode(node: Node): void`

**JSDoc:**
```typescript
/**
	 * It is used to add Nodes that will be used as FRAME and RENDER events,
	 * and need to follow a certain sequence in the calls to work correctly.
	 * This function should be called after 'setup()' in the 'build()' process to ensure that the child nodes are processed first.
	 *
	 * @param {Node} node - The node to add.
	 */
```

**Parameters:**

- **`node`** `Node`

**Returns:** `void`

**Calls:**

- `this.sequentialNodes.includes`
- `this.sequentialNodes.push`

<details><summary>Code</summary>

```typescript
addSequentialNode( node ) {

		if ( this.sequentialNodes.includes( node ) === false ) {

			this.sequentialNodes.push( node );

		}

	}
```
</details>

### `NodeBuilder.buildUpdateNodes(): void`

**JSDoc:**
```typescript
/**
	 * Checks the update types of nodes
	 */
```

**Returns:** `void`

**Calls:**

- `node.getUpdateType`
- `this.updateNodes.push`
- `node.getSelf`
- `node.getUpdateBeforeType`
- `node.getUpdateAfterType`
- `this.updateBeforeNodes.push`
- `this.updateAfterNodes.push`

<details><summary>Code</summary>

```typescript
buildUpdateNodes() {

		for ( const node of this.nodes ) {

			const updateType = node.getUpdateType();

			if ( updateType !== NodeUpdateType.NONE ) {

				this.updateNodes.push( node.getSelf() );

			}

		}

		for ( const node of this.sequentialNodes ) {

			const updateBeforeType = node.getUpdateBeforeType();
			const updateAfterType = node.getUpdateAfterType();

			if ( updateBeforeType !== NodeUpdateType.NONE ) {

				this.updateBeforeNodes.push( node.getSelf() );

			}

			if ( updateAfterType !== NodeUpdateType.NONE ) {

				this.updateAfterNodes.push( node.getSelf() );

			}

		}

	}
```
</details>

### `NodeBuilder.isFilteredTexture(texture: Texture): boolean`

**JSDoc:**
```typescript
/**
	 * Whether the given texture is filtered or not.
	 *
	 * @param {Texture} texture - The texture to check.
	 * @return {boolean} Whether the given texture is filtered or not.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
isFilteredTexture( texture ) {

		return ( texture.magFilter === LinearFilter || texture.magFilter === LinearMipmapNearestFilter || texture.magFilter === NearestMipmapLinearFilter || texture.magFilter === LinearMipmapLinearFilter ||
			texture.minFilter === LinearFilter || texture.minFilter === LinearMipmapNearestFilter || texture.minFilter === NearestMipmapLinearFilter || texture.minFilter === LinearMipmapLinearFilter );

	}
```
</details>

### `NodeBuilder.addChain(node: Node): void`

**JSDoc:**
```typescript
/**
	 * Adds the given node to the internal node chain.
	 * This is used to check recursive calls in node-graph.
	 *
	 * @param {Node} node - The node to add.
	 */
```

**Parameters:**

- **`node`** `Node`

**Returns:** `void`

**Calls:**

- `this.chaining.push`

**Internal Comments:**
```
/*
		if ( this.chaining.indexOf( node ) !== - 1 ) {

			console.warn( 'Recursive node: ', node );

		}
		*/ (x5)
```

<details><summary>Code</summary>

```typescript
addChain( node ) {

		/*
		if ( this.chaining.indexOf( node ) !== - 1 ) {

			console.warn( 'Recursive node: ', node );

		}
		*/

		this.chaining.push( node );

	}
```
</details>

### `NodeBuilder.removeChain(node: Node): void`

**JSDoc:**
```typescript
/**
	 * Removes the given node from the internal node chain.
	 *
	 * @param {Node} node - The node to remove.
	 */
```

**Parameters:**

- **`node`** `Node`

**Returns:** `void`

**Calls:**

- `this.chaining.pop`

<details><summary>Code</summary>

```typescript
removeChain( node ) {

		const lastChain = this.chaining.pop();

		if ( lastChain !== node ) {

			throw new Error( 'NodeBuilder: Invalid node chaining!' );

		}

	}
```
</details>

### `NodeBuilder.getMethod(method: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the native shader method name for a given generic name. E.g.
	 * the method name `textureDimensions` matches the WGSL name but must be
	 * resolved to `textureSize` in GLSL.
	 *
	 * @abstract
	 * @param {string} method - The method name to resolve.
	 * @return {string} The resolved method name.
	 */
```

**Parameters:**

- **`method`** `string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getMethod( method ) {

		return method;

	}
```
</details>

### `NodeBuilder.getTernary(): string`

**JSDoc:**
```typescript
/**
	 * Returns the native snippet for a ternary operation. E.g. GLSL would output
	 * a ternary op as `cond ? x : y` whereas WGSL would output it as `select(y, x, cond)`
	 *
	 * @abstract
	 * @param {string} condSnippet - The condition determining which expression gets resolved.
	 * @param {string} ifSnippet - The expression to resolve to if the condition is true.
	 * @param {string} elseSnippet - The expression to resolve to if the condition is false.
	 * @return {string} The resolved method name.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getTernary( /* condSnippet, ifSnippet, elseSnippet*/ ) {

		return null;

	}
```
</details>

### `NodeBuilder.getNodeFromHash(hash: number): Node`

**JSDoc:**
```typescript
/**
	 * Returns a node for the given hash, see {@link NodeBuilder#setHashNode}.
	 *
	 * @param {number} hash - The hash of the node.
	 * @return {Node} The found node.
	 */
```

**Parameters:**

- **`hash`** `number`

**Returns:** `Node`

<details><summary>Code</summary>

```typescript
getNodeFromHash( hash ) {

		return this.hashNodes[ hash ];

	}
```
</details>

### `NodeBuilder.addFlow(shaderStage: "compute" | "vertex" | "fragment", node: Node): Node`

**JSDoc:**
```typescript
/**
	 * Adds the Node to a target flow so that it can generate code in the 'generate' process.
	 *
	 * @param {('vertex'|'fragment'|'compute')} shaderStage - The shader stage.
	 * @param {Node} node - The node to add.
	 * @return {Node} The node.
	 */
```

**Parameters:**

- **`shaderStage`** `"compute" | "vertex" | "fragment"`
- **`node`** `Node`

**Returns:** `Node`

**Calls:**

- `this.flowNodes[ shaderStage ].push`

<details><summary>Code</summary>

```typescript
addFlow( shaderStage, node ) {

		this.flowNodes[ shaderStage ].push( node );

		return node;

	}
```
</details>

### `NodeBuilder.setContext(context: any): void`

**JSDoc:**
```typescript
/**
	 * Sets builder's context.
	 *
	 * @param {Object} context - The context to set.
	 */
```

**Parameters:**

- **`context`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setContext( context ) {

		this.context = context;

	}
```
</details>

### `NodeBuilder.getContext(): any`

**JSDoc:**
```typescript
/**
	 * Returns the builder's current context.
	 *
	 * @return {Object} The builder's current context.
	 */
```

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getContext() {

		return this.context;

	}
```
</details>

### `NodeBuilder.getSharedContext(): any`

**JSDoc:**
```typescript
/**
	 * Gets a context used in shader construction that can be shared across different materials.
	 * This is necessary since the renderer cache can reuse shaders generated in one material and use them in another.
	 *
	 * @return {Object} The builder's current context without material.
	 */
```

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getSharedContext() {

		const context = { ...this.context };

		delete context.material;

		return this.context;

	}
```
</details>

### `NodeBuilder.setCache(cache: NodeCache): void`

**JSDoc:**
```typescript
/**
	 * Sets builder's cache.
	 *
	 * @param {NodeCache} cache - The cache to set.
	 */
```

**Parameters:**

- **`cache`** `NodeCache`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setCache( cache ) {

		this.cache = cache;

	}
```
</details>

### `NodeBuilder.getCache(): NodeCache`

**JSDoc:**
```typescript
/**
	 * Returns the builder's current cache.
	 *
	 * @return {NodeCache} The builder's current cache.
	 */
```

**Returns:** `NodeCache`

<details><summary>Code</summary>

```typescript
getCache() {

		return this.cache;

	}
```
</details>

### `NodeBuilder.getCacheFromNode(node: Node, parent: boolean): NodeCache`

**JSDoc:**
```typescript
/**
	 * Returns a cache for the given node.
	 *
	 * @param {Node} node - The node.
	 * @param {boolean} [parent=true] - Whether this node refers to a shared parent cache or not.
	 * @return {NodeCache} The cache.
	 */
```

**Parameters:**

- **`node`** `Node`
- **`parent`** `boolean`

**Returns:** `NodeCache`

**Calls:**

- `this.getDataFromNode`
- `this.getCache`

<details><summary>Code</summary>

```typescript
getCacheFromNode( node, parent = true ) {

		const data = this.getDataFromNode( node );
		if ( data.cache === undefined ) data.cache = new NodeCache( parent ? this.getCache() : null );

		return data.cache;

	}
```
</details>

### `NodeBuilder.isAvailable(): boolean`

**JSDoc:**
```typescript
/**
	 * Whether the requested feature is available or not.
	 *
	 * @abstract
	 * @param {string} name - The requested feature.
	 * @return {boolean} Whether the requested feature is supported or not.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
isAvailable( /*name*/ ) {

		return false;

	}
```
</details>

### `NodeBuilder.getVertexIndex(): string`

**JSDoc:**
```typescript
/**
	 * Returns the vertexIndex input variable as a native shader string.
	 *
	 * @abstract
	 * @return {string} The instanceIndex shader string.
	 */
```

**Returns:** `string`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
getVertexIndex() {

		console.warn( 'Abstract function.' );

	}
```
</details>

### `NodeBuilder.getInstanceIndex(): string`

**JSDoc:**
```typescript
/**
	 * Returns the instanceIndex input variable as a native shader string.
	 *
	 * @abstract
	 * @return {string} The instanceIndex shader string.
	 */
```

**Returns:** `string`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
getInstanceIndex() {

		console.warn( 'Abstract function.' );

	}
```
</details>

### `NodeBuilder.getDrawIndex(): string`

**JSDoc:**
```typescript
/**
	 * Returns the drawIndex input variable as a native shader string.
	 * Only relevant for WebGL and its `WEBGL_multi_draw` extension.
	 *
	 * @abstract
	 * @return {?string} The drawIndex shader string.
	 */
```

**Returns:** `string`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
getDrawIndex() {

		console.warn( 'Abstract function.' );

	}
```
</details>

### `NodeBuilder.getFrontFacing(): string`

**JSDoc:**
```typescript
/**
	 * Returns the frontFacing input variable as a native shader string.
	 *
	 * @abstract
	 * @return {string} The frontFacing shader string.
	 */
```

**Returns:** `string`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
getFrontFacing() {

		console.warn( 'Abstract function.' );

	}
```
</details>

### `NodeBuilder.getFragCoord(): string`

**JSDoc:**
```typescript
/**
	 * Returns the fragCoord input variable as a native shader string.
	 *
	 * @abstract
	 * @return {string} The fragCoord shader string.
	 */
```

**Returns:** `string`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
getFragCoord() {

		console.warn( 'Abstract function.' );

	}
```
</details>

### `NodeBuilder.isFlipY(): boolean`

**JSDoc:**
```typescript
/**
	 * Whether to flip texture data along its vertical axis or not. WebGL needs
	 * this method evaluate to `true`, WebGPU to `false`.
	 *
	 * @abstract
	 * @return {boolean} Whether to flip texture data along its vertical axis or not.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
isFlipY() {

		return false;

	}
```
</details>

### `NodeBuilder.increaseUsage(node: Node): number`

**JSDoc:**
```typescript
/**
	 * Calling this method increases the usage count for the given node by one.
	 *
	 * @param {Node} node - The node to increase the usage count for.
	 * @return {number} The updated usage count.
	 */
```

**Parameters:**

- **`node`** `Node`

**Returns:** `number`

**Calls:**

- `this.getDataFromNode`

<details><summary>Code</summary>

```typescript
increaseUsage( node ) {

		const nodeData = this.getDataFromNode( node );
		nodeData.usageCount = nodeData.usageCount === undefined ? 1 : nodeData.usageCount + 1;

		return nodeData.usageCount;

	}
```
</details>

### `NodeBuilder.generateTexture(): string`

**JSDoc:**
```typescript
/**
	 * Generates a texture sample shader string for the given texture data.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The texture property name.
	 * @param {string} uvSnippet - Snippet defining the texture coordinates.
	 * @return {string} The generated shader string.
	 */
```

**Returns:** `string`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
generateTexture( /* texture, textureProperty, uvSnippet */ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

### `NodeBuilder.generateTextureLod(): string`

**JSDoc:**
```typescript
/**
	 * Generates a texture LOD shader string for the given texture data.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The texture property name.
	 * @param {string} uvSnippet - Snippet defining the texture coordinates.
	 * @param {?string} depthSnippet - Snippet defining the 0-based texture array index to sample.
	 * @param {string} levelSnippet - Snippet defining the mip level.
	 * @return {string} The generated shader string.
	 */
```

**Returns:** `string`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
generateTextureLod( /* texture, textureProperty, uvSnippet, depthSnippet, levelSnippet */ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

### `NodeBuilder.generateArrayDeclaration(type: string, count: number): string`

**JSDoc:**
```typescript
/**
	 * Generates the array declaration string.
	 *
	 * @param {string} type - The type.
	 * @param {?number} [count] - The count.
	 * @return {string} The generated value as a shader string.
	 */
```

**Parameters:**

- **`type`** `string`
- **`count`** `number`

**Returns:** `string`

**Calls:**

- `this.getType`

<details><summary>Code</summary>

```typescript
generateArrayDeclaration( type, count ) {

		return this.getType( type ) + '[ ' + count + ' ]';

	}
```
</details>

### `NodeBuilder.generateArray(type: string, count: number, values: Node[]): string`

**JSDoc:**
```typescript
/**
	 * Generates the array shader string for the given type and value.
	 *
	 * @param {string} type - The type.
	 * @param {?number} [count] - The count.
	 * @param {?Array<Node>} [values=null] - The default values.
	 * @return {string} The generated value as a shader string.
	 */
```

**Parameters:**

- **`type`** `string`
- **`count`** `number`
- **`values`** `Node[]`

**Returns:** `string`

**Calls:**

- `this.generateArrayDeclaration`
- `value.build`
- `this.generateConst`

<details><summary>Code</summary>

```typescript
generateArray( type, count, values = null ) {

		let snippet = this.generateArrayDeclaration( type, count ) + '( ';

		for ( let i = 0; i < count; i ++ ) {

			const value = values ? values[ i ] : null;

			if ( value !== null ) {

				snippet += value.build( this, type );

			} else {

				snippet += this.generateConst( type );

			}

			if ( i < count - 1 ) snippet += ', ';

		}

		snippet += ' )';

		return snippet;

	}
```
</details>

### `NodeBuilder.generateStruct(type: string, membersLayout: any[], values: Node[]): string`

**JSDoc:**
```typescript
/**
	 * Generates the struct shader string.
	 *
	 * @param {string} type - The type.
	 * @param {Array<Object>} [membersLayout] - The count.
	 * @param {?Array<Node>} [values=null] - The default values.
	 * @return {string} The generated value as a shader string.
	 */
```

**Parameters:**

- **`type`** `string`
- **`membersLayout`** `any[]`
- **`values`** `Node[]`

**Returns:** `string`

**Calls:**

- `snippets.push`
- `values[ name ].build`
- `this.generateConst`
- `snippets.join`

<details><summary>Code</summary>

```typescript
generateStruct( type, membersLayout, values = null ) {

		const snippets = [];

		for ( const member of membersLayout ) {

			const { name, type } = member;

			if ( values && values[ name ] && values[ name ].isNode ) {

				snippets.push( values[ name ].build( this, type ) );

			} else {

				snippets.push( this.generateConst( type ) );

			}

		}

		return type + '( ' + snippets.join( ', ' ) + ' )';

	}
```
</details>

### `NodeBuilder.generateConst(type: string, value: any): string`

**JSDoc:**
```typescript
/**
	 * Generates the shader string for the given type and value.
	 *
	 * @param {string} type - The type.
	 * @param {?any} [value=null] - The value.
	 * @return {string} The generated value as a shader string.
	 */
```

**Parameters:**

- **`type`** `string`
- **`value`** `any`

**Returns:** `string`

**Calls:**

- `toFloat`
- `Math.round`
- `this.getType`
- `this.getTypeLength`
- `this.getComponentType`
- `this.generateConst`
- `generateConst`
- `value.elements.map( generateConst ).join`

<details><summary>Code</summary>

```typescript
generateConst( type, value = null ) {

		if ( value === null ) {

			if ( type === 'float' || type === 'int' || type === 'uint' ) value = 0;
			else if ( type === 'bool' ) value = false;
			else if ( type === 'color' ) value = new Color();
			else if ( type === 'vec2' ) value = new Vector2();
			else if ( type === 'vec3' ) value = new Vector3();
			else if ( type === 'vec4' ) value = new Vector4();

		}

		if ( type === 'float' ) return toFloat( value );
		if ( type === 'int' ) return `${ Math.round( value ) }`;
		if ( type === 'uint' ) return value >= 0 ? `${ Math.round( value ) }u` : '0u';
		if ( type === 'bool' ) return value ? 'true' : 'false';
		if ( type === 'color' ) return `${ this.getType( 'vec3' ) }( ${ toFloat( value.r ) }, ${ toFloat( value.g ) }, ${ toFloat( value.b ) } )`;

		const typeLength = this.getTypeLength( type );

		const componentType = this.getComponentType( type );

		const generateConst = value => this.generateConst( componentType, value );

		if ( typeLength === 2 ) {

			return `${ this.getType( type ) }( ${ generateConst( value.x ) }, ${ generateConst( value.y ) } )`;

		} else if ( typeLength === 3 ) {

			return `${ this.getType( type ) }( ${ generateConst( value.x ) }, ${ generateConst( value.y ) }, ${ generateConst( value.z ) } )`;

		} else if ( typeLength === 4 && type !== 'mat2' ) {

			return `${ this.getType( type ) }( ${ generateConst( value.x ) }, ${ generateConst( value.y ) }, ${ generateConst( value.z ) }, ${ generateConst( value.w ) } )`;

		} else if ( typeLength >= 4 && value && ( value.isMatrix2 || value.isMatrix3 || value.isMatrix4 ) ) {

			return `${ this.getType( type ) }( ${ value.elements.map( generateConst ).join( ', ' ) } )`;

		} else if ( typeLength > 4 ) {

			return `${ this.getType( type ) }()`;

		}

		throw new Error( `NodeBuilder: Type '${type}' not found in generate constant attempt.` );

	}
```
</details>

### `NodeBuilder.getType(type: string): string`

**JSDoc:**
```typescript
/**
	 * It might be necessary to convert certain data types to different ones
	 * so this method can be used to hide the conversion.
	 *
	 * @param {string} type - The type.
	 * @return {string} The updated type.
	 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getType( type ) {

		if ( type === 'color' ) return 'vec3';

		return type;

	}
```
</details>

### `NodeBuilder.hasGeometryAttribute(name: string): boolean`

**JSDoc:**
```typescript
/**
	 * Whether the given attribute name is defined in the geometry or not.
	 *
	 * @param {string} name - The attribute name.
	 * @return {boolean} Whether the given attribute name is defined in the geometry.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `boolean`

**Calls:**

- `this.geometry.getAttribute`

<details><summary>Code</summary>

```typescript
hasGeometryAttribute( name ) {

		return this.geometry && this.geometry.getAttribute( name ) !== undefined;

	}
```
</details>

### `NodeBuilder.getAttribute(name: string, type: string): NodeAttribute`

**JSDoc:**
```typescript
/**
	 * Returns a node attribute for the given name and type.
	 *
	 * @param {string} name - The attribute's name.
	 * @param {string} type - The attribute's type.
	 * @return {NodeAttribute} The node attribute.
	 */
```

**Parameters:**

- **`name`** `string`
- **`type`** `string`

**Returns:** `NodeAttribute`

**Calls:**

- `this.registerDeclaration`
- `attributes.push`

**Internal Comments:**
```
// find attribute
// create a new if no exist (x2)
```

<details><summary>Code</summary>

```typescript
getAttribute( name, type ) {

		const attributes = this.attributes;

		// find attribute

		for ( const attribute of attributes ) {

			if ( attribute.name === name ) {

				return attribute;

			}

		}

		// create a new if no exist

		const attribute = new NodeAttribute( name, type );

		this.registerDeclaration( attribute );

		attributes.push( attribute );

		return attribute;

	}
```
</details>

### `NodeBuilder.getPropertyName(node: Node): string`

**JSDoc:**
```typescript
/**
	 * Returns for the given node and shader stage the property name for the shader.
	 *
	 * @param {Node} node - The node.
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @return {string} The property name.
	 */
```

**Parameters:**

- **`node`** `Node`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getPropertyName( node/*, shaderStage*/ ) {

		return node.name;

	}
```
</details>

### `NodeBuilder.isVector(type: string): boolean`

**JSDoc:**
```typescript
/**
	 * Whether the given type is a vector type or not.
	 *
	 * @param {string} type - The type to check.
	 * @return {boolean} Whether the given type is a vector type or not.
	 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `boolean`

**Calls:**

- `/vec\d/.test`

<details><summary>Code</summary>

```typescript
isVector( type ) {

		return /vec\d/.test( type );

	}
```
</details>

### `NodeBuilder.isMatrix(type: string): boolean`

**JSDoc:**
```typescript
/**
	 * Whether the given type is a matrix type or not.
	 *
	 * @param {string} type - The type to check.
	 * @return {boolean} Whether the given type is a matrix type or not.
	 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `boolean`

**Calls:**

- `/mat\d/.test`

<details><summary>Code</summary>

```typescript
isMatrix( type ) {

		return /mat\d/.test( type );

	}
```
</details>

### `NodeBuilder.isReference(type: string): boolean`

**JSDoc:**
```typescript
/**
	 * Whether the given type is a reference type or not.
	 *
	 * @param {string} type - The type to check.
	 * @return {boolean} Whether the given type is a reference type or not.
	 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
isReference( type ) {

		return type === 'void' || type === 'property' || type === 'sampler' || type === 'samplerComparison' || type === 'texture' || type === 'cubeTexture' || type === 'storageTexture' || type === 'depthTexture' || type === 'texture3D';

	}
```
</details>

### `NodeBuilder.needsToWorkingColorSpace(): boolean`

**JSDoc:**
```typescript
/**
	 * Checks if the given texture requires a manual conversion to the working color space.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture to check.
	 * @return {boolean} Whether the given texture requires a conversion to working color space or not.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
needsToWorkingColorSpace( /*texture*/ ) {

		return false;

	}
```
</details>

### `NodeBuilder.getComponentTypeFromTexture(texture: Texture): string`

**JSDoc:**
```typescript
/**
	 * Returns the component type of a given texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @return {string} The component type.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getComponentTypeFromTexture( texture ) {

		const type = texture.type;

		if ( texture.isDataTexture ) {

			if ( type === IntType ) return 'int';
			if ( type === UnsignedIntType ) return 'uint';

		}

		return 'float';

	}
```
</details>

### `NodeBuilder.getElementType(type: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the element type for a given type.
	 *
	 * @param {string} type - The type.
	 * @return {string} The element type.
	 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `string`

**Calls:**

- `this.getComponentType`

<details><summary>Code</summary>

```typescript
getElementType( type ) {

		if ( type === 'mat2' ) return 'vec2';
		if ( type === 'mat3' ) return 'vec3';
		if ( type === 'mat4' ) return 'vec4';

		return this.getComponentType( type );

	}
```
</details>

### `NodeBuilder.getComponentType(type: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the component type for a given type.
	 *
	 * @param {string} type - The type.
	 * @return {string} The component type.
	 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `string`

**Calls:**

- `this.getVectorType`
- `/(b|i|u|)(vec|mat)([2-4])/.exec`

<details><summary>Code</summary>

```typescript
getComponentType( type ) {

		type = this.getVectorType( type );

		if ( type === 'float' || type === 'bool' || type === 'int' || type === 'uint' ) return type;

		const componentType = /(b|i|u|)(vec|mat)([2-4])/.exec( type );

		if ( componentType === null ) return null;

		if ( componentType[ 1 ] === 'b' ) return 'bool';
		if ( componentType[ 1 ] === 'i' ) return 'int';
		if ( componentType[ 1 ] === 'u' ) return 'uint';

		return 'float';

	}
```
</details>

### `NodeBuilder.getVectorType(type: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the vector type for a given type.
	 *
	 * @param {string} type - The type.
	 * @return {string} The vector type.
	 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getVectorType( type ) {

		if ( type === 'color' ) return 'vec3';
		if ( type === 'texture' || type === 'cubeTexture' || type === 'storageTexture' || type === 'texture3D' ) return 'vec4';

		return type;

	}
```
</details>

### `NodeBuilder.getTypeFromLength(length: number, componentType: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the data type for the given the length and component type.
	 *
	 * @param {number} length - The length.
	 * @param {string} [componentType='float'] - The component type.
	 * @return {string} The type.
	 */
```

**Parameters:**

- **`length`** `number`
- **`componentType`** `string`

**Returns:** `string`

**Calls:**

- `getTypeFromLength (from ./NodeUtils.js)`
- `/mat2/.test`
- `baseType.replace`

**Internal Comments:**
```
// fix edge case for mat2x2 being same size as vec4
```

<details><summary>Code</summary>

```typescript
getTypeFromLength( length, componentType = 'float' ) {

		if ( length === 1 ) return componentType;

		let baseType = getTypeFromLength( length );
		const prefix = componentType === 'float' ? '' : componentType[ 0 ];

		// fix edge case for mat2x2 being same size as vec4
		if ( /mat2/.test( componentType ) === true ) {

			baseType = baseType.replace( 'vec', 'mat' );

		}

		return prefix + baseType;

	}
```
</details>

### `NodeBuilder.getTypeFromArray(array: TypedArray): string`

**JSDoc:**
```typescript
/**
	 * Returns the type for a given typed array.
	 *
	 * @param {TypedArray} array - The typed array.
	 * @return {string} The type.
	 */
```

**Parameters:**

- **`array`** `TypedArray`

**Returns:** `string`

**Calls:**

- `typeFromArray.get`

<details><summary>Code</summary>

```typescript
getTypeFromArray( array ) {

		return typeFromArray.get( array.constructor );

	}
```
</details>

### `NodeBuilder.isInteger(type: string): boolean`

**JSDoc:**
```typescript
/**
	 * Returns the type is an integer type.
	 *
	 * @param {string} type - The type.
	 * @return {boolean} Whether the type is an integer type or not.
	 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `boolean`

**Calls:**

- `/int|uint|(i|u)vec/.test`

<details><summary>Code</summary>

```typescript
isInteger( type ) {

		return /int|uint|(i|u)vec/.test( type );

	}
```
</details>

### `NodeBuilder.getTypeFromAttribute(attribute: BufferAttribute): string`

**JSDoc:**
```typescript
/**
	 * Returns the type for a given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 * @return {string} The type.
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`

**Returns:** `string`

**Calls:**

- `this.getTypeFromArray`
- `this.getTypeFromLength`

<details><summary>Code</summary>

```typescript
getTypeFromAttribute( attribute ) {

		let dataAttribute = attribute;

		if ( attribute.isInterleavedBufferAttribute ) dataAttribute = attribute.data;

		const array = dataAttribute.array;
		const itemSize = attribute.itemSize;
		const normalized = attribute.normalized;

		let arrayType;

		if ( ! ( attribute instanceof Float16BufferAttribute ) && normalized !== true ) {

			arrayType = this.getTypeFromArray( array );

		}

		return this.getTypeFromLength( itemSize, arrayType );

	}
```
</details>

### `NodeBuilder.getTypeLength(type: string): number`

**JSDoc:**
```typescript
/**
	 * Returns the length for the given data type.
	 *
	 * @param {string} type - The data type.
	 * @return {number} The length.
	 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `number`

**Calls:**

- `this.getVectorType`
- `/vec([2-4])/.exec`
- `Number`
- `/mat2/.test`
- `/mat3/.test`
- `/mat4/.test`

<details><summary>Code</summary>

```typescript
getTypeLength( type ) {

		const vecType = this.getVectorType( type );
		const vecNum = /vec([2-4])/.exec( vecType );

		if ( vecNum !== null ) return Number( vecNum[ 1 ] );
		if ( vecType === 'float' || vecType === 'bool' || vecType === 'int' || vecType === 'uint' ) return 1;
		if ( /mat2/.test( type ) === true ) return 4;
		if ( /mat3/.test( type ) === true ) return 9;
		if ( /mat4/.test( type ) === true ) return 16;

		return 0;

	}
```
</details>

### `NodeBuilder.getVectorFromMatrix(type: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the vector type for a given matrix type.
	 *
	 * @param {string} type - The matrix type.
	 * @return {string} The vector type.
	 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `string`

**Calls:**

- `type.replace`

<details><summary>Code</summary>

```typescript
getVectorFromMatrix( type ) {

		return type.replace( 'mat', 'vec' );

	}
```
</details>

### `NodeBuilder.changeComponentType(type: string, newComponentType: string): string`

**JSDoc:**
```typescript
/**
	 * For a given type this method changes the component type to the
	 * given value. E.g. `vec4` should be changed to the new component type
	 * `uint` which results in `uvec4`.
	 *
	 * @param {string} type - The type.
	 * @param {string} newComponentType - The new component type.
	 * @return {string} The new type.
	 */
```

**Parameters:**

- **`type`** `string`
- **`newComponentType`** `string`

**Returns:** `string`

**Calls:**

- `this.getTypeFromLength`
- `this.getTypeLength`

<details><summary>Code</summary>

```typescript
changeComponentType( type, newComponentType ) {

		return this.getTypeFromLength( this.getTypeLength( type ), newComponentType );

	}
```
</details>

### `NodeBuilder.getIntegerType(type: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the integer type pendant for the given type.
	 *
	 * @param {string} type - The type.
	 * @return {string} The integer type.
	 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `string`

**Calls:**

- `this.getComponentType`
- `this.changeComponentType`

<details><summary>Code</summary>

```typescript
getIntegerType( type ) {

		const componentType = this.getComponentType( type );

		if ( componentType === 'int' || componentType === 'uint' ) return type;

		return this.changeComponentType( type, 'int' );

	}
```
</details>

### `NodeBuilder.addStack(): StackNode`

**JSDoc:**
```typescript
/**
	 * Adds a stack node to the internal stack.
	 *
	 * @return {StackNode} The added stack node.
	 */
```

**Returns:** `StackNode`

**Calls:**

- `stack (from ./StackNode.js)`
- `this.stacks.push`
- `getCurrentStack (from ../tsl/TSLBase.js)`
- `setCurrentStack (from ../tsl/TSLBase.js)`

<details><summary>Code</summary>

```typescript
addStack() {

		this.stack = stack( this.stack );

		this.stacks.push( getCurrentStack() || this.stack );
		setCurrentStack( this.stack );

		return this.stack;

	}
```
</details>

### `NodeBuilder.removeStack(): StackNode`

**JSDoc:**
```typescript
/**
	 * Removes the last stack node from the internal stack.
	 *
	 * @return {StackNode} The removed stack node.
	 */
```

**Returns:** `StackNode`

**Calls:**

- `setCurrentStack (from ../tsl/TSLBase.js)`
- `this.stacks.pop`

<details><summary>Code</summary>

```typescript
removeStack() {

		const lastStack = this.stack;
		this.stack = lastStack.parent;

		setCurrentStack( this.stacks.pop() );

		return lastStack;

	}
```
</details>

### `NodeBuilder.getDataFromNode(node: Node, shaderStage: "compute" | "vertex" | "fragment" | "any", cache: NodeCache): any`

**JSDoc:**
```typescript
/**
	 * The builder maintains (cached) data for each node during the building process. This method
	 * can be used to get these data for a specific shader stage and cache.
	 *
	 * @param {Node} node - The node to get the data for.
	 * @param {('vertex'|'fragment'|'compute'|'any')} [shaderStage=this.shaderStage] - The shader stage.
	 * @param {?NodeCache} cache - An optional cache.
	 * @return {Object} The node data.
	 */
```

**Parameters:**

- **`node`** `Node`
- **`shaderStage`** `"compute" | "vertex" | "fragment" | "any"`
- **`cache`** `NodeCache`

**Returns:** `any`

**Calls:**

- `node.isGlobal`
- `cache.getData`
- `cache.setData`
- `this.getClosestSubBuild`

**Internal Comments:**
```
// (x2)
```

<details><summary>Code</summary>

```typescript
getDataFromNode( node, shaderStage = this.shaderStage, cache = null ) {

		cache = cache === null ? ( node.isGlobal( this ) ? this.globalCache : this.cache ) : cache;

		let nodeData = cache.getData( node );

		if ( nodeData === undefined ) {

			nodeData = {};

			cache.setData( node, nodeData );

		}

		if ( nodeData[ shaderStage ] === undefined ) nodeData[ shaderStage ] = {};

		//

		let data = nodeData[ shaderStage ];

		const subBuilds = nodeData.any ? nodeData.any.subBuilds : null;
		const subBuild = this.getClosestSubBuild( subBuilds );

		if ( subBuild ) {

			if ( data.subBuildsCache === undefined ) data.subBuildsCache = {};

			data = data.subBuildsCache[ subBuild ] || ( data.subBuildsCache[ subBuild ] = {} );
			data.subBuilds = subBuilds;

		}

		return data;

	}
```
</details>

### `NodeBuilder.getNodeProperties(node: Node, shaderStage: "compute" | "vertex" | "fragment" | "any"): any`

**JSDoc:**
```typescript
/**
	 * Returns the properties for the given node and shader stage.
	 *
	 * @param {Node} node - The node to get the properties for.
	 * @param {('vertex'|'fragment'|'compute'|'any')} [shaderStage='any'] - The shader stage.
	 * @return {Object} The node properties.
	 */
```

**Parameters:**

- **`node`** `Node`
- **`shaderStage`** `"compute" | "vertex" | "fragment" | "any"`

**Returns:** `any`

**Calls:**

- `this.getDataFromNode`

<details><summary>Code</summary>

```typescript
getNodeProperties( node, shaderStage = 'any' ) {

		const nodeData = this.getDataFromNode( node, shaderStage );

		return nodeData.properties || ( nodeData.properties = { outputNode: null } );

	}
```
</details>

### `NodeBuilder.getBufferAttributeFromNode(node: BufferAttributeNode, type: string): NodeAttribute`

**JSDoc:**
```typescript
/**
	 * Returns an instance of {@link NodeAttribute} for the given buffer attribute node.
	 *
	 * @param {BufferAttributeNode} node - The buffer attribute node.
	 * @param {string} type - The node type.
	 * @return {NodeAttribute} The node attribute.
	 */
```

**Parameters:**

- **`node`** `BufferAttributeNode`
- **`type`** `string`

**Returns:** `NodeAttribute`

**Calls:**

- `this.getDataFromNode`
- `this.bufferAttributes.push`

<details><summary>Code</summary>

```typescript
getBufferAttributeFromNode( node, type ) {

		const nodeData = this.getDataFromNode( node );

		let bufferAttribute = nodeData.bufferAttribute;

		if ( bufferAttribute === undefined ) {

			const index = this.uniforms.index ++;

			bufferAttribute = new NodeAttribute( 'nodeAttribute' + index, type, node );

			this.bufferAttributes.push( bufferAttribute );

			nodeData.bufferAttribute = bufferAttribute;

		}

		return bufferAttribute;

	}
```
</details>

### `NodeBuilder.getStructTypeFromNode(node: OutputStructNode, membersLayout: any[], name: string, shaderStage: "compute" | "vertex" | "fragment" | "any"): StructType`

**JSDoc:**
```typescript
/**
	 * Returns an instance of {@link StructType} for the given output struct node.
	 *
	 * @param {OutputStructNode} node - The output struct node.
	 * @param {Array<Object>} membersLayout - The output struct types.
	 * @param {?string} [name=null] - The name of the struct.
	 * @param {('vertex'|'fragment'|'compute'|'any')} [shaderStage=this.shaderStage] - The shader stage.
	 * @return {StructType} The struct type attribute.
	 */
```

**Parameters:**

- **`node`** `OutputStructNode`
- **`membersLayout`** `any[]`
- **`name`** `string`
- **`shaderStage`** `"compute" | "vertex" | "fragment" | "any"`

**Returns:** `StructType`

**Calls:**

- `this.getDataFromNode`
- `this.structs[ shaderStage ].push`

<details><summary>Code</summary>

```typescript
getStructTypeFromNode( node, membersLayout, name = null, shaderStage = this.shaderStage ) {

		const nodeData = this.getDataFromNode( node, shaderStage, this.globalCache );

		let structType = nodeData.structType;

		if ( structType === undefined ) {

			const index = this.structs.index ++;

			if ( name === null ) name = 'StructType' + index;

			structType = new StructType( name, membersLayout );

			this.structs[ shaderStage ].push( structType );

			nodeData.structType = structType;

		}

		return structType;

	}
```
</details>

### `NodeBuilder.getOutputStructTypeFromNode(node: OutputStructNode, membersLayout: any[]): StructType`

**JSDoc:**
```typescript
/**
	 * Returns an instance of {@link StructType} for the given output struct node.
	 *
	 * @param {OutputStructNode} node - The output struct node.
	 * @param {Array<Object>} membersLayout - The output struct types.
	 * @return {StructType} The struct type attribute.
	 */
```

**Parameters:**

- **`node`** `OutputStructNode`
- **`membersLayout`** `any[]`

**Returns:** `StructType`

**Calls:**

- `this.getStructTypeFromNode`

<details><summary>Code</summary>

```typescript
getOutputStructTypeFromNode( node, membersLayout ) {

		const structType = this.getStructTypeFromNode( node, membersLayout, 'OutputType', 'fragment' );
		structType.output = true;

		return structType;

	}
```
</details>

### `NodeBuilder.getUniformFromNode(node: UniformNode, type: string, shaderStage: "compute" | "vertex" | "fragment" | "any", name: string): NodeUniform`

**JSDoc:**
```typescript
/**
	 * Returns an instance of {@link NodeUniform} for the given uniform node.
	 *
	 * @param {UniformNode} node - The uniform node.
	 * @param {string} type - The uniform type.
	 * @param {('vertex'|'fragment'|'compute'|'any')} [shaderStage=this.shaderStage] - The shader stage.
	 * @param {?string} name - The name of the uniform.
	 * @return {NodeUniform} The node uniform.
	 */
```

**Parameters:**

- **`node`** `UniformNode`
- **`type`** `string`
- **`shaderStage`** `"compute" | "vertex" | "fragment" | "any"`
- **`name`** `string`

**Returns:** `NodeUniform`

**Calls:**

- `this.getDataFromNode`
- `this.uniforms[ shaderStage ].push`
- `this.registerDeclaration`

<details><summary>Code</summary>

```typescript
getUniformFromNode( node, type, shaderStage = this.shaderStage, name = null ) {

		const nodeData = this.getDataFromNode( node, shaderStage, this.globalCache );

		let nodeUniform = nodeData.uniform;

		if ( nodeUniform === undefined ) {

			const index = this.uniforms.index ++;

			nodeUniform = new NodeUniform( name || ( 'nodeUniform' + index ), type, node );

			this.uniforms[ shaderStage ].push( nodeUniform );

			this.registerDeclaration( nodeUniform );

			nodeData.uniform = nodeUniform;

		}

		return nodeUniform;

	}
```
</details>

### `NodeBuilder.getVarFromNode(node: VarNode, name: string, type: string, shaderStage: "compute" | "vertex" | "fragment" | "any", readOnly: boolean): NodeVar`

**JSDoc:**
```typescript
/**
	 * Returns an instance of {@link NodeVar} for the given variable node.
	 *
	 * @param {VarNode} node - The variable node.
	 * @param {?string} name - The variable's name.
	 * @param {string} [type=node.getNodeType( this )] - The variable's type.
	 * @param {('vertex'|'fragment'|'compute'|'any')} [shaderStage=this.shaderStage] - The shader stage.
	 * @param {boolean} [readOnly=false] - Whether the variable is read-only or not.
	 *
	 * @return {NodeVar} The node variable.
	 */
```

**Parameters:**

- **`node`** `VarNode`
- **`name`** `string`
- **`type`** `string`
- **`shaderStage`** `"compute" | "vertex" | "fragment" | "any"`
- **`readOnly`** `boolean`

**Returns:** `NodeVar`

**Calls:**

- `this.getDataFromNode`
- `this.getSubBuildProperty`
- `node.getArrayCount`
- `vars.push`
- `this.registerDeclaration`

**Internal Comments:**
```
// (x3)
```

<details><summary>Code</summary>

```typescript
getVarFromNode( node, name = null, type = node.getNodeType( this ), shaderStage = this.shaderStage, readOnly = false ) {

		const nodeData = this.getDataFromNode( node, shaderStage );
		const subBuildVariable = this.getSubBuildProperty( 'variable', nodeData.subBuilds );

		let nodeVar = nodeData[ subBuildVariable ];

		if ( nodeVar === undefined ) {

			const idNS = readOnly ? '_const' : '_var';

			const vars = this.vars[ shaderStage ] || ( this.vars[ shaderStage ] = [] );
			const id = this.vars[ idNS ] || ( this.vars[ idNS ] = 0 );

			if ( name === null ) {

				name = ( readOnly ? 'nodeConst' : 'nodeVar' ) + id;

				this.vars[ idNS ] ++;

			}

			//

			if ( subBuildVariable !== 'variable' ) {

				name = this.getSubBuildProperty( name, nodeData.subBuilds );

			}

			//

			const count = node.getArrayCount( this );

			nodeVar = new NodeVar( name, type, readOnly, count );

			if ( ! readOnly ) {

				vars.push( nodeVar );

			}

			this.registerDeclaration( nodeVar );

			nodeData[ subBuildVariable ] = nodeVar;

		}

		return nodeVar;

	}
```
</details>

### `NodeBuilder.isDeterministic(node: Node): boolean`

**JSDoc:**
```typescript
/**
	 * Returns whether a Node or its flow is deterministic, useful for use in `const`.
	 *
	 * @param {Node} node - The varying node.
	 * @return {boolean} Returns true if deterministic.
	 */
```

**Parameters:**

- **`node`** `Node`

**Returns:** `boolean`

**Calls:**

- `this.isDeterministic`

<details><summary>Code</summary>

```typescript
isDeterministic( node ) {

		if ( node.isMathNode ) {

			return this.isDeterministic( node.aNode ) &&
				( node.bNode ? this.isDeterministic( node.bNode ) : true ) &&
				( node.cNode ? this.isDeterministic( node.cNode ) : true );

		} else if ( node.isOperatorNode ) {

			return this.isDeterministic( node.aNode ) &&
				( node.bNode ? this.isDeterministic( node.bNode ) : true );

		} else if ( node.isArrayNode ) {

			if ( node.values !== null ) {

				for ( const n of node.values ) {

					if ( ! this.isDeterministic( n ) ) {

						return false;

					}

				}

			}

			return true;

		} else if ( node.isConstNode ) {

			return true;

		}

		return false;

	}
```
</details>

### `NodeBuilder.getVaryingFromNode(node: any, name: string, type: string, interpolationType: string, interpolationSampling: string): NodeVar`

**JSDoc:**
```typescript
/**
	 * Returns an instance of {@link NodeVarying} for the given varying node.
	 *
	 * @param {(VaryingNode|PropertyNode)} node - The varying node.
	 * @param {?string} name - The varying's name.
	 * @param {string} [type=node.getNodeType( this )] - The varying's type.
	 * @param {?string} interpolationType - The interpolation type of the varying.
	 * @param {?string} interpolationSampling - The interpolation sampling type of the varying.
	 * @return {NodeVar} The node varying.
	 */
```

**Parameters:**

- **`node`** `any`
- **`name`** `string`
- **`type`** `string`
- **`interpolationType`** `string`
- **`interpolationSampling`** `string`

**Returns:** `NodeVar`

**Calls:**

- `this.getDataFromNode`
- `this.getSubBuildProperty`
- `varyings.push`
- `this.registerDeclaration`

**Internal Comments:**
```
// (x4)
```

<details><summary>Code</summary>

```typescript
getVaryingFromNode( node, name = null, type = node.getNodeType( this ), interpolationType = null, interpolationSampling = null ) {

		const nodeData = this.getDataFromNode( node, 'any' );
		const subBuildVarying = this.getSubBuildProperty( 'varying', nodeData.subBuilds );

		let nodeVarying = nodeData[ subBuildVarying ];

		if ( nodeVarying === undefined ) {

			const varyings = this.varyings;
			const index = varyings.length;

			if ( name === null ) name = 'nodeVarying' + index;

			//

			if ( subBuildVarying !== 'varying' ) {

				name = this.getSubBuildProperty( name, nodeData.subBuilds );

			}

			//

			nodeVarying = new NodeVarying( name, type, interpolationType, interpolationSampling );

			varyings.push( nodeVarying );

			this.registerDeclaration( nodeVarying );

			nodeData[ subBuildVarying ] = nodeVarying;

		}

		return nodeVarying;

	}
```
</details>

### `NodeBuilder.registerDeclaration(node: any): void`

**JSDoc:**
```typescript
/**
	 * Registers a node declaration in the current shader stage.
	 *
	 * @param {Object} node - The node to be registered.
	 */
```

**Parameters:**

- **`node`** `any`

**Returns:** `void`

**Calls:**

- `this.getPropertyName`
- `console.warn`

**Internal Comments:**
```
// Automatically renames the property if the name is already in use.
```

<details><summary>Code</summary>

```typescript
registerDeclaration( node ) {

		const shaderStage = this.shaderStage;
		const declarations = this.declarations[ shaderStage ] || ( this.declarations[ shaderStage ] = {} );

		const property = this.getPropertyName( node );

		let index = 1;
		let name = property;

		// Automatically renames the property if the name is already in use.

		while ( declarations[ name ] !== undefined ) {

			name = property + '_' + index ++;

		}

		if ( index > 1 ) {

			node.name = name;

			console.warn( `THREE.TSL: Declaration name '${ property }' of '${ node.type }' already in use. Renamed to '${ name }'.` );

		}

		declarations[ name ] = node;

	}
```
</details>

### `NodeBuilder.getCodeFromNode(node: CodeNode, type: string, shaderStage: "compute" | "vertex" | "fragment" | "any"): NodeCode`

**JSDoc:**
```typescript
/**
	 * Returns an instance of {@link NodeCode} for the given code node.
	 *
	 * @param {CodeNode} node - The code node.
	 * @param {string} type - The node type.
	 * @param {('vertex'|'fragment'|'compute'|'any')} [shaderStage=this.shaderStage] - The shader stage.
	 * @return {NodeCode} The node code.
	 */
```

**Parameters:**

- **`node`** `CodeNode`
- **`type`** `string`
- **`shaderStage`** `"compute" | "vertex" | "fragment" | "any"`

**Returns:** `NodeCode`

**Calls:**

- `this.getDataFromNode`
- `codes.push`

<details><summary>Code</summary>

```typescript
getCodeFromNode( node, type, shaderStage = this.shaderStage ) {

		const nodeData = this.getDataFromNode( node );

		let nodeCode = nodeData.code;

		if ( nodeCode === undefined ) {

			const codes = this.codes[ shaderStage ] || ( this.codes[ shaderStage ] = [] );
			const index = codes.length;

			nodeCode = new NodeCode( 'nodeCode' + index, type );

			codes.push( nodeCode );

			nodeData.code = nodeCode;

		}

		return nodeCode;

	}
```
</details>

### `NodeBuilder.addFlowCodeHierarchy(node: Node, nodeBlock: Node): void`

**JSDoc:**
```typescript
/**
	 * Adds a code flow based on the code-block hierarchy.

	 * This is used so that code-blocks like If,Else create their variables locally if the Node
	 * is only used inside one of these conditionals in the current shader stage.
	 *
	 * @param {Node} node - The node to add.
	 * @param {Node} nodeBlock - Node-based code-block. Usually 'ConditionalNode'.
	 */
```

**Parameters:**

- **`node`** `Node`
- **`nodeBlock`** `Node`

**Returns:** `void`

**Calls:**

- `this.getDataFromNode`
- `flowCodeBlock.get`
- `this.addLineFlowCode`

<details><summary>Code</summary>

```typescript
addFlowCodeHierarchy( node, nodeBlock ) {

		const { flowCodes, flowCodeBlock } = this.getDataFromNode( node );

		let needsFlowCode = true;
		let nodeBlockHierarchy = nodeBlock;

		while ( nodeBlockHierarchy ) {

			if ( flowCodeBlock.get( nodeBlockHierarchy ) === true ) {

				needsFlowCode = false;
				break;

			}

			nodeBlockHierarchy = this.getDataFromNode( nodeBlockHierarchy ).parentNodeBlock;

		}

		if ( needsFlowCode ) {

			for ( const flowCode of flowCodes ) {

				this.addLineFlowCode( flowCode );

			}

		}

	}
```
</details>

### `NodeBuilder.addLineFlowCodeBlock(node: Node, code: string, nodeBlock: Node): void`

**JSDoc:**
```typescript
/**
	 * Add a inline-code to the current flow code-block.
	 *
	 * @param {Node} node - The node to add.
	 * @param {string} code - The code to add.
	 * @param {Node} nodeBlock - Current ConditionalNode
	 */
```

**Parameters:**

- **`node`** `Node`
- **`code`** `string`
- **`nodeBlock`** `Node`

**Returns:** `void`

**Calls:**

- `this.getDataFromNode`
- `flowCodes.push`
- `codeBlock.set`

<details><summary>Code</summary>

```typescript
addLineFlowCodeBlock( node, code, nodeBlock ) {

		const nodeData = this.getDataFromNode( node );
		const flowCodes = nodeData.flowCodes || ( nodeData.flowCodes = [] );
		const codeBlock = nodeData.flowCodeBlock || ( nodeData.flowCodeBlock = new WeakMap() );

		flowCodes.push( code );
		codeBlock.set( nodeBlock, true );

	}
```
</details>

### `NodeBuilder.addLineFlowCode(code: string, node: Node): NodeBuilder`

**JSDoc:**
```typescript
/**
	 * Add a inline-code to the current flow.
	 *
	 * @param {string} code - The code to add.
	 * @param {?Node} [node= null] - Optional Node, can help the system understand if the Node is part of a code-block.
	 * @return {NodeBuilder} A reference to this node builder.
	 */
```

**Parameters:**

- **`code`** `string`
- **`node`** `Node`

**Returns:** `NodeBuilder`

**Calls:**

- `this.addLineFlowCodeBlock`
- `/;\s*$/.test`

<details><summary>Code</summary>

```typescript
addLineFlowCode( code, node = null ) {

		if ( code === '' ) return this;

		if ( node !== null && this.context.nodeBlock ) {

			this.addLineFlowCodeBlock( node, code, this.context.nodeBlock );

		}

		code = this.tab + code;

		if ( ! /;\s*$/.test( code ) ) {

			code = code + ';\n';

		}

		this.flow.code += code;

		return this;

	}
```
</details>

### `NodeBuilder.addFlowCode(code: string): NodeBuilder`

**JSDoc:**
```typescript
/**
	 * Adds a code to the current code flow.
	 *
	 * @param {string} code - Shader code.
	 * @return {NodeBuilder} A reference to this node builder.
	 */
```

**Parameters:**

- **`code`** `string`

**Returns:** `NodeBuilder`

<details><summary>Code</summary>

```typescript
addFlowCode( code ) {

		this.flow.code += code;

		return this;

	}
```
</details>

### `NodeBuilder.addFlowTab(): NodeBuilder`

**JSDoc:**
```typescript
/**
	 * Add tab in the code that will be generated so that other snippets respect the current tabulation.
	 * Typically used in codes with If,Else.
	 *
	 * @return {NodeBuilder} A reference to this node builder.
	 */
```

**Returns:** `NodeBuilder`

<details><summary>Code</summary>

```typescript
addFlowTab() {

		this.tab += '\t';

		return this;

	}
```
</details>

### `NodeBuilder.removeFlowTab(): NodeBuilder`

**JSDoc:**
```typescript
/**
	 * Removes a tab.
	 *
	 * @return {NodeBuilder} A reference to this node builder.
	 */
```

**Returns:** `NodeBuilder`

**Calls:**

- `this.tab.slice`

<details><summary>Code</summary>

```typescript
removeFlowTab() {

		this.tab = this.tab.slice( 0, - 1 );

		return this;

	}
```
</details>

### `NodeBuilder.getFlowData(node: Node): any`

**JSDoc:**
```typescript
/**
	 * Gets the current flow data based on a Node.
	 *
	 * @param {Node} node - Node that the flow was started.
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @return {Object} The flow data.
	 */
```

**Parameters:**

- **`node`** `Node`

**Returns:** `any`

**Calls:**

- `this.flowsData.get`

<details><summary>Code</summary>

```typescript
getFlowData( node/*, shaderStage*/ ) {

		return this.flowsData.get( node );

	}
```
</details>

### `NodeBuilder.flowNode(node: Node): any`

**JSDoc:**
```typescript
/**
	 * Executes the node flow based on a root node to generate the final shader code.
	 *
	 * @param {Node} node - The node to execute.
	 * @return {Object} The code flow.
	 */
```

**Parameters:**

- **`node`** `Node`

**Returns:** `any`

**Calls:**

- `node.getNodeType`
- `this.flowChildNode`
- `this.flowsData.set`

<details><summary>Code</summary>

```typescript
flowNode( node ) {

		const output = node.getNodeType( this );

		const flowData = this.flowChildNode( node, output );

		this.flowsData.set( node, flowData );

		return flowData;

	}
```
</details>

### `NodeBuilder.addInclude(node: Node): void`

**JSDoc:**
```typescript
/**
	 * Includes a node in the current function node.
	 *
	 * @param {Node} node - The node to include.
	 * @returns {void}
	 */
```

**Parameters:**

- **`node`** `Node`

**Returns:** `void`

**Calls:**

- `this.currentFunctionNode.includes.push`

<details><summary>Code</summary>

```typescript
addInclude( node ) {

		if ( this.currentFunctionNode !== null ) {

			this.currentFunctionNode.includes.push( node );

		}

	}
```
</details>

### `NodeBuilder.buildFunctionNode(shaderNode: ShaderNodeInternal): FunctionNode`

**JSDoc:**
```typescript
/**
	 * Returns the native shader operator name for a given generic name.
	 * It is a similar type of method like {@link NodeBuilder#getMethod}.
	 *
	 * @param {ShaderNodeInternal} shaderNode - The shader node to build the function node with.
	 * @return {FunctionNode} The build function node.
	 */
```

**Parameters:**

- **`shaderNode`** `ShaderNodeInternal`

**Returns:** `FunctionNode`

**Calls:**

- `this.buildFunctionCode`

<details><summary>Code</summary>

```typescript
buildFunctionNode( shaderNode ) {

		const fn = new FunctionNode();

		const previous = this.currentFunctionNode;

		this.currentFunctionNode = fn;

		fn.code = this.buildFunctionCode( shaderNode );

		this.currentFunctionNode = previous;

		return fn;

	}
```
</details>

### `NodeBuilder.flowShaderNode(shaderNode: ShaderNodeInternal): any`

**JSDoc:**
```typescript
/**
	 * Generates a code flow based on a TSL function: Fn().
	 *
	 * @param {ShaderNodeInternal} shaderNode - A function code will be generated based on the input.
	 * @return {Object}
	 */
```

**Parameters:**

- **`shaderNode`** `ShaderNodeInternal`

**Returns:** `any`

**Calls:**

- `Object.values`
- `shaderNode.call`
- `this.flowStagesNode`

**Internal Comments:**
```
// (x4)
```

<details><summary>Code</summary>

```typescript
flowShaderNode( shaderNode ) {

		const layout = shaderNode.layout;

		const inputs = {
			[ Symbol.iterator ]() {

				let index = 0;
				const values = Object.values( this );
				return {
					next: () => ( {
						value: values[ index ],
						done: index ++ >= values.length
					} )
				};

			}
		};

		for ( const input of layout.inputs ) {

			inputs[ input.name ] = new ParameterNode( input.type, input.name );

		}

		//

		shaderNode.layout = null;

		const callNode = shaderNode.call( inputs );
		const flowData = this.flowStagesNode( callNode, layout.type );

		shaderNode.layout = layout;

		return flowData;

	}
```
</details>

### `NodeBuilder.flowBuildStage(node: Node, buildStage: string, output: string | Node): string | Node`

**JSDoc:**
```typescript
/**
	 * Executes the node in a specific build stage.
	 *
	 * @param {Node} node - The node to execute.
	 * @param {string} buildStage - The build stage to execute the node in.
	 * @param {Node|string|null} output - Expected output type. For example 'vec3'.
	 * @return {Node|string|null} The result of the node build.
	 */
```

**Parameters:**

- **`node`** `Node`
- **`buildStage`** `string`
- **`output`** `string | Node`

**Returns:** `string | Node`

**Calls:**

- `this.getBuildStage`
- `this.setBuildStage`
- `node.build`

<details><summary>Code</summary>

```typescript
flowBuildStage( node, buildStage, output = null ) {

		const previousBuildStage = this.getBuildStage();

		this.setBuildStage( buildStage );

		const result = node.build( this, output );

		this.setBuildStage( previousBuildStage );

		return result;

	}
```
</details>

### `NodeBuilder.flowStagesNode(node: Node, output: string): any`

**JSDoc:**
```typescript
/**
	 * Runs the node flow through all the steps of creation, 'setup', 'analyze', 'generate'.
	 *
	 * @param {Node} node - The node to execute.
	 * @param {?string} output - Expected output type. For example 'vec3'.
	 * @return {Object}
	 */
```

**Parameters:**

- **`node`** `Node`
- **`output`** `string`

**Returns:** `any`

**Calls:**

- `stack (from ./StackNode.js)`
- `this.setBuildStage`
- `node.build`
- `this.getVars`

<details><summary>Code</summary>

```typescript
flowStagesNode( node, output = null ) {

		const previousFlow = this.flow;
		const previousVars = this.vars;
		const previousDeclarations = this.declarations;
		const previousCache = this.cache;
		const previousBuildStage = this.buildStage;
		const previousStack = this.stack;

		const flow = {
			code: ''
		};

		this.flow = flow;
		this.vars = {};
		this.declarations = {};
		this.cache = new NodeCache();
		this.stack = stack();

		for ( const buildStage of defaultBuildStages ) {

			this.setBuildStage( buildStage );

			flow.result = node.build( this, output );

		}

		flow.vars = this.getVars( this.shaderStage );

		this.flow = previousFlow;
		this.vars = previousVars;
		this.declarations = previousDeclarations;
		this.cache = previousCache;
		this.stack = previousStack;

		this.setBuildStage( previousBuildStage );

		return flow;

	}
```
</details>

### `NodeBuilder.getFunctionOperator(): string`

**JSDoc:**
```typescript
/**
	 * Returns the native shader operator name for a given generic name.
	 * It is a similar type of method like {@link NodeBuilder#getMethod}.
	 *
	 * @abstract
	 * @param {string} op - The operator name to resolve.
	 * @return {?string} The resolved operator name.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getFunctionOperator( /* op */ ) {

		return null;

	}
```
</details>

### `NodeBuilder.buildFunctionCode(): string`

**JSDoc:**
```typescript
/**
	 * Builds the given shader node.
	 *
	 * @abstract
	 * @param {ShaderNodeInternal} shaderNode - The shader node.
	 * @return {string} The function code.
	 */
```

**Returns:** `string`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
buildFunctionCode( /* shaderNode */ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

### `NodeBuilder.flowChildNode(node: Node, output: string): any`

**JSDoc:**
```typescript
/**
	 * Generates a code flow based on a child Node.
	 *
	 * @param {Node} node - The node to execute.
	 * @param {?string} output - Expected output type. For example 'vec3'.
	 * @return {Object} The code flow.
	 */
```

**Parameters:**

- **`node`** `Node`
- **`output`** `string`

**Returns:** `any`

**Calls:**

- `node.build`

<details><summary>Code</summary>

```typescript
flowChildNode( node, output = null ) {

		const previousFlow = this.flow;

		const flow = {
			code: ''
		};

		this.flow = flow;

		flow.result = node.build( this, output );

		this.flow = previousFlow;

		return flow;

	}
```
</details>

### `NodeBuilder.flowNodeFromShaderStage(shaderStage: "compute" | "vertex" | "fragment" | "any", node: Node, output: string, propertyName: string): any`

**JSDoc:**
```typescript
/**
	 * Executes a flow of code in a different stage.
	 *
	 * Some nodes like `varying()` have the ability to compute code in vertex-stage and
	 * return the value in fragment-stage even if it is being executed in an input fragment.
	 *
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @param {Node} node - The node to execute.
	 * @param {?string} output - Expected output type. For example 'vec3'.
	 * @param {?string} propertyName - The property name to assign the result.
	 * @return {Object|Node|null} The code flow or node.build() result.
	 */
```

**Parameters:**

- **`shaderStage`** `"compute" | "vertex" | "fragment" | "any"`
- **`node`** `Node`
- **`output`** `string`
- **`propertyName`** `string`

**Returns:** `any`

**Calls:**

- `this.setShaderStage`
- `this.flowChildNode`
- `node.build`

<details><summary>Code</summary>

```typescript
flowNodeFromShaderStage( shaderStage, node, output = null, propertyName = null ) {

		const previousTab = this.tab;
		const previousCache = this.cache;
		const previousShaderStage = this.shaderStage;
		const previousContext = this.context;

		this.setShaderStage( shaderStage );

		const context = { ...this.context };
		delete context.nodeBlock;

		this.cache = this.globalCache;
		this.tab = '\t';
		this.context = context;

		let result = null;

		if ( this.buildStage === 'generate' ) {

			const flowData = this.flowChildNode( node, output );

			if ( propertyName !== null ) {

				flowData.code += `${ this.tab + propertyName } = ${ flowData.result };\n`;

			}

			this.flowCode[ shaderStage ] = this.flowCode[ shaderStage ] + flowData.code;

			result = flowData;

		} else {

			result = node.build( this );

		}

		this.setShaderStage( previousShaderStage );

		this.cache = previousCache;
		this.tab = previousTab;
		this.context = previousContext;

		return result;

	}
```
</details>

### `NodeBuilder.getAttributesArray(): NodeAttribute[]`

**JSDoc:**
```typescript
/**
	 * Returns an array holding all node attributes of this node builder.
	 *
	 * @return {Array<NodeAttribute>} The node attributes of this builder.
	 */
```

**Returns:** `NodeAttribute[]`

**Calls:**

- `this.attributes.concat`

<details><summary>Code</summary>

```typescript
getAttributesArray() {

		return this.attributes.concat( this.bufferAttributes );

	}
```
</details>

### `NodeBuilder.getAttributes(): string`

**JSDoc:**
```typescript
/**
	 * Returns the attribute definitions as a shader string for the given shader stage.
	 *
	 * @abstract
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @return {string} The attribute code section.
	 */
```

**Returns:** `string`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
getAttributes( /*shaderStage*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

### `NodeBuilder.getVaryings(): string`

**JSDoc:**
```typescript
/**
	 * Returns the varying definitions as a shader string for the given shader stage.
	 *
	 * @abstract
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @return {string} The varying code section.
	 */
```

**Returns:** `string`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
getVaryings( /*shaderStage*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

### `NodeBuilder.getVar(type: string, name: string, count: number): string`

**JSDoc:**
```typescript
/**
	 * Returns a single variable definition as a shader string for the given variable type and name.
	 *
	 * @param {string} type - The variable's type.
	 * @param {string} name - The variable's name.
	 * @param {?number} [count=null] - The array length.
	 * @return {string} The shader string.
	 */
```

**Parameters:**

- **`type`** `string`
- **`name`** `string`
- **`count`** `number`

**Returns:** `string`

**Calls:**

- `this.generateArrayDeclaration`
- `this.getType`

<details><summary>Code</summary>

```typescript
getVar( type, name, count = null ) {

		return `${ count !== null ? this.generateArrayDeclaration( type, count ) : this.getType( type ) } ${ name }`;

	}
```
</details>

### `NodeBuilder.getVars(shaderStage: "compute" | "vertex" | "fragment" | "any"): string`

**JSDoc:**
```typescript
/**
	 * Returns the variable definitions as a shader string for the given shader stage.
	 *
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @return {string} The variable code section.
	 */
```

**Parameters:**

- **`shaderStage`** `"compute" | "vertex" | "fragment" | "any"`

**Returns:** `string`

**Calls:**

- `this.getVar`

<details><summary>Code</summary>

```typescript
getVars( shaderStage ) {

		let snippet = '';

		const vars = this.vars[ shaderStage ];

		if ( vars !== undefined ) {

			for ( const variable of vars ) {

				snippet += `${ this.getVar( variable.type, variable.name ) }; `;

			}

		}

		return snippet;

	}
```
</details>

### `NodeBuilder.getUniforms(): string`

**JSDoc:**
```typescript
/**
	 * Returns the uniform definitions as a shader string for the given shader stage.
	 *
	 * @abstract
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @return {string} The uniform code section.
	 */
```

**Returns:** `string`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
getUniforms( /*shaderStage*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

### `NodeBuilder.getCodes(shaderStage: "compute" | "vertex" | "fragment" | "any"): string`

**JSDoc:**
```typescript
/**
	 * Returns the native code definitions as a shader string for the given shader stage.
	 *
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @return {string} The native code section.
	 */
```

**Parameters:**

- **`shaderStage`** `"compute" | "vertex" | "fragment" | "any"`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getCodes( shaderStage ) {

		const codes = this.codes[ shaderStage ];

		let code = '';

		if ( codes !== undefined ) {

			for ( const nodeCode of codes ) {

				code += nodeCode.code + '\n';

			}

		}

		return code;

	}
```
</details>

### `NodeBuilder.getHash(): string`

**JSDoc:**
```typescript
/**
	 * Returns the hash of this node builder.
	 *
	 * @return {string} The hash.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getHash() {

		return this.vertexShader + this.fragmentShader + this.computeShader;

	}
```
</details>

### `NodeBuilder.setShaderStage(shaderStage: "compute" | "vertex" | "fragment" | "any"): void`

**JSDoc:**
```typescript
/**
	 * Sets the current shader stage.
	 *
	 * @param {?('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage to set.
	 */
```

**Parameters:**

- **`shaderStage`** `"compute" | "vertex" | "fragment" | "any"`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setShaderStage( shaderStage ) {

		this.shaderStage = shaderStage;

	}
```
</details>

### `NodeBuilder.getShaderStage(): "compute" | "vertex" | "fragment" | "any"`

**JSDoc:**
```typescript
/**
	 * Returns the current shader stage.
	 *
	 * @return {?('vertex'|'fragment'|'compute'|'any')} The current shader stage.
	 */
```

**Returns:** `"compute" | "vertex" | "fragment" | "any"`

<details><summary>Code</summary>

```typescript
getShaderStage() {

		return this.shaderStage;

	}
```
</details>

### `NodeBuilder.setBuildStage(buildStage: "setup" | "generate" | "analyze"): void`

**JSDoc:**
```typescript
/**
	 * Sets the current build stage.
	 *
	 * @param {?('setup'|'analyze'|'generate')} buildStage - The build stage to set.
	 */
```

**Parameters:**

- **`buildStage`** `"setup" | "generate" | "analyze"`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setBuildStage( buildStage ) {

		this.buildStage = buildStage;

	}
```
</details>

### `NodeBuilder.getBuildStage(): "setup" | "generate" | "analyze"`

**JSDoc:**
```typescript
/**
	 * Returns the current build stage.
	 *
	 * @return {?('setup'|'analyze'|'generate')} The current build stage.
	 */
```

**Returns:** `"setup" | "generate" | "analyze"`

<details><summary>Code</summary>

```typescript
getBuildStage() {

		return this.buildStage;

	}
```
</details>

### `NodeBuilder.buildCode(): void`

**JSDoc:**
```typescript
/**
	 * Controls the code build of the shader stages.
	 *
	 * @abstract
	 */
```

**Returns:** `void`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
buildCode() {

		console.warn( 'Abstract function.' );

	}
```
</details>

### `NodeBuilder.addSubBuild(subBuild: SubBuildNode): void`

**JSDoc:**
```typescript
/**
	 * Adds a sub-build layer to the node builder.
	 *
	 * @param {SubBuildNode} subBuild - The sub-build layer to add.
	 */
```

**Parameters:**

- **`subBuild`** `SubBuildNode`

**Returns:** `void`

**Calls:**

- `this.subBuildLayers.push`

<details><summary>Code</summary>

```typescript
addSubBuild( subBuild ) {

		this.subBuildLayers.push( subBuild );

	}
```
</details>

### `NodeBuilder.removeSubBuild(): SubBuildNode`

**JSDoc:**
```typescript
/**
	 * Removes the last sub-build layer from the node builder.
	 *
	 * @return {SubBuildNode} The removed sub-build layer.
	 */
```

**Returns:** `SubBuildNode`

**Calls:**

- `this.subBuildLayers.pop`

<details><summary>Code</summary>

```typescript
removeSubBuild() {

		return this.subBuildLayers.pop();

	}
```
</details>

### `NodeBuilder.getClosestSubBuild(data: any[] | Node | Set<any>): string`

**JSDoc:**
```typescript
/**
	 * Returns the closest sub-build layer for the given data.
	 *
	 * @param {Node|Set|Array} data - The data to get the closest sub-build layer from.
	 * @return {?string} The closest sub-build name or null if none found.
	 */
```

**Parameters:**

- **`data`** `any[] | Node | Set<any>`

**Returns:** `string`

**Calls:**

- `this.getDataFromNode`
- `subBuildLayers.includes`

<details><summary>Code</summary>

```typescript
getClosestSubBuild( data ) {

		let subBuilds;

		if ( data && data.isNode ) {

			if ( data.isShaderCallNodeInternal ) {

				subBuilds = data.shaderNode.subBuilds;

			} else if ( data.isStackNode ) {

				subBuilds = [ data.subBuild ];

			} else {

				subBuilds = this.getDataFromNode( data, 'any' ).subBuilds;

			}

		} else if ( data instanceof Set ) {

			subBuilds = [ ...data ];

		} else {

			subBuilds = data;

		}

		if ( ! subBuilds ) return null;

		const subBuildLayers = this.subBuildLayers;

		for ( let i = subBuilds.length - 1; i >= 0; i -- ) {

			const subBuild = subBuilds[ i ];

			if ( subBuildLayers.includes( subBuild ) ) {

				return subBuild;

			}

		}

		return null;

	}
```
</details>

### `NodeBuilder.getSubBuildOutput(node: Node): string`

**JSDoc:**
```typescript
/**
	 * Returns the output node of a sub-build layer.
	 *
	 * @param {Node} node - The node to get the output from.
	 * @return {string} The output node name.
	 */
```

**Parameters:**

- **`node`** `Node`

**Returns:** `string`

**Calls:**

- `this.getSubBuildProperty`

<details><summary>Code</summary>

```typescript
getSubBuildOutput( node ) {

		return this.getSubBuildProperty( 'outputNode', node );

	}
```
</details>

### `NodeBuilder.getSubBuildProperty(property: string, node: Node): string`

**JSDoc:**
```typescript
/**
	 * Returns the sub-build property name for the given property and node.
	 *
	 * @param {string} [property=''] - The property name.
	 * @param {?Node} [node=null] - The node to get the sub-build from.
	 * @return {string} The sub-build property name.
	 */
```

**Parameters:**

- **`property`** `string`
- **`node`** `Node`

**Returns:** `string`

**Calls:**

- `this.getClosestSubBuild`

<details><summary>Code</summary>

```typescript
getSubBuildProperty( property = '', node = null ) {

		let subBuild;

		if ( node !== null ) {

			subBuild = this.getClosestSubBuild( node );

		} else {

			subBuild = this.subBuildFn;

		}

		let result;

		if ( subBuild ) {

			result = property ? ( subBuild + '_' + property ) : subBuild;

		} else {

			result = property;

		}

		return result;

	}
```
</details>

### `NodeBuilder.build(): NodeBuilder`

**JSDoc:**
```typescript
/**
	 * Central build method which controls the build for the given object.
	 *
	 * @return {NodeBuilder} A reference to this node builder.
	 */
```

**Returns:** `NodeBuilder`

**Calls:**

- `renderer.library.fromMaterial`
- `console.error`
- `nodeMaterial.build`
- `this.addFlow`
- `this.setBuildStage`
- `this.flowNodeFromShaderStage`
- `this.setShaderStage`
- `this.flowNode`
- `node.build`
- `this.buildCode`
- `this.buildUpdateNodes`

**Internal Comments:**
```
// setup() -> stage 1: create possible new nodes and/or return an output reference node
// analyze()   -> stage 2: analyze nodes to possible optimization and validation
// generate()  -> stage 3: generate shader
// stage 4: build code for a specific output (x4)
```

<details><summary>Code</summary>

```typescript
build() {

		const { object, material, renderer } = this;

		if ( material !== null ) {

			let nodeMaterial = renderer.library.fromMaterial( material );

			if ( nodeMaterial === null ) {

				console.error( `NodeMaterial: Material "${ material.type }" is not compatible.` );

				nodeMaterial = new NodeMaterial();

			}

			nodeMaterial.build( this );

		} else {

			this.addFlow( 'compute', object );

		}

		// setup() -> stage 1: create possible new nodes and/or return an output reference node
		// analyze()   -> stage 2: analyze nodes to possible optimization and validation
		// generate()  -> stage 3: generate shader

		for ( const buildStage of defaultBuildStages ) {

			this.setBuildStage( buildStage );

			if ( this.context.vertex && this.context.vertex.isNode ) {

				this.flowNodeFromShaderStage( 'vertex', this.context.vertex );

			}

			for ( const shaderStage of shaderStages ) {

				this.setShaderStage( shaderStage );

				const flowNodes = this.flowNodes[ shaderStage ];

				for ( const node of flowNodes ) {

					if ( buildStage === 'generate' ) {

						this.flowNode( node );

					} else {

						node.build( this );

					}

				}

			}

		}

		this.setBuildStage( null );
		this.setShaderStage( null );

		// stage 4: build code for a specific output

		this.buildCode();
		this.buildUpdateNodes();

		return this;

	}
```
</details>

### `NodeBuilder.getNodeUniform(uniformNode: NodeUniform, type: string): Uniform`

**JSDoc:**
```typescript
/**
	 * Returns a uniform representation which is later used for UBO generation and rendering.
	 *
	 * @param {NodeUniform} uniformNode - The uniform node.
	 * @param {string} type - The requested type.
	 * @return {Uniform} The uniform.
	 */
```

**Parameters:**

- **`uniformNode`** `NodeUniform`
- **`type`** `string`

**Returns:** `Uniform`

<details><summary>Code</summary>

```typescript
getNodeUniform( uniformNode, type ) {

		if ( type === 'float' || type === 'int' || type === 'uint' ) return new NumberNodeUniform( uniformNode );
		if ( type === 'vec2' || type === 'ivec2' || type === 'uvec2' ) return new Vector2NodeUniform( uniformNode );
		if ( type === 'vec3' || type === 'ivec3' || type === 'uvec3' ) return new Vector3NodeUniform( uniformNode );
		if ( type === 'vec4' || type === 'ivec4' || type === 'uvec4' ) return new Vector4NodeUniform( uniformNode );
		if ( type === 'color' ) return new ColorNodeUniform( uniformNode );
		if ( type === 'mat2' ) return new Matrix2NodeUniform( uniformNode );
		if ( type === 'mat3' ) return new Matrix3NodeUniform( uniformNode );
		if ( type === 'mat4' ) return new Matrix4NodeUniform( uniformNode );

		throw new Error( `Uniform "${type}" not declared.` );

	}
```
</details>

### `NodeBuilder.format(snippet: string, fromType: string, toType: string): string`

**JSDoc:**
```typescript
/**
	 * Formats the given shader snippet from a given type into another one. E.g.
	 * this method might be used to convert a simple float string `"1.0"` into a
	 * `vec3` representation: `"vec3<f32>( 1.0 )"`.
	 *
	 * @param {string} snippet - The shader snippet.
	 * @param {string} fromType - The source type.
	 * @param {string} toType - The target type.
	 * @return {string} The updated shader string.
	 */
```

**Parameters:**

- **`snippet`** `string`
- **`fromType`** `string`
- **`toType`** `string`

**Returns:** `string`

**Calls:**

- `this.getVectorType`
- `this.isReference`
- `this.getTypeLength`
- `this.getType`
- `'xyz'.slice`
- `this.format`
- `this.getTypeFromLength`
- `this.getComponentType`

**Internal Comments:**
```
// @TODO: ignore for now (x2)
// convert a number value to vector type, e.g: (x3)
// vec3( 1u ) -> vec3( float( 1u ) ) (x3)
```

<details><summary>Code</summary>

```typescript
format( snippet, fromType, toType ) {

		fromType = this.getVectorType( fromType );
		toType = this.getVectorType( toType );

		if ( fromType === toType || toType === null || this.isReference( toType ) ) {

			return snippet;

		}

		const fromTypeLength = this.getTypeLength( fromType );
		const toTypeLength = this.getTypeLength( toType );

		if ( fromTypeLength === 16 && toTypeLength === 9 ) {

			return `${ this.getType( toType ) }( ${ snippet }[ 0 ].xyz, ${ snippet }[ 1 ].xyz, ${ snippet }[ 2 ].xyz )`;

		}

		if ( fromTypeLength === 9 && toTypeLength === 4 ) {

			return `${ this.getType( toType ) }( ${ snippet }[ 0 ].xy, ${ snippet }[ 1 ].xy )`;

		}


		if ( fromTypeLength > 4 ) { // fromType is matrix-like

			// @TODO: ignore for now

			return snippet;

		}

		if ( toTypeLength > 4 || toTypeLength === 0 ) { // toType is matrix-like or unknown

			// @TODO: ignore for now

			return snippet;

		}

		if ( fromTypeLength === toTypeLength ) {

			return `${ this.getType( toType ) }( ${ snippet } )`;

		}

		if ( fromTypeLength > toTypeLength ) {

			snippet = toType === 'bool' ? `all( ${ snippet } )` : `${ snippet }.${ 'xyz'.slice( 0, toTypeLength ) }`;

			return this.format( snippet, this.getTypeFromLength( toTypeLength, this.getComponentType( fromType ) ), toType );

		}

		if ( toTypeLength === 4 && fromTypeLength > 1 ) { // toType is vec4-like

			return `${ this.getType( toType ) }( ${ this.format( snippet, fromType, 'vec3' ) }, 1.0 )`;

		}

		if ( fromTypeLength === 2 ) { // fromType is vec2-like and toType is vec3-like

			return `${ this.getType( toType ) }( ${ this.format( snippet, fromType, 'vec2' ) }, 0.0 )`;

		}

		if ( fromTypeLength === 1 && toTypeLength > 1 && fromType !== this.getComponentType( toType ) ) { // fromType is float-like

			// convert a number value to vector type, e.g:
			// vec3( 1u ) -> vec3( float( 1u ) )

			snippet = `${ this.getType( this.getComponentType( toType ) ) }( ${ snippet } )`;

		}

		return `${ this.getType( toType ) }( ${ snippet } )`; // fromType is float-like

	}
```
</details>

### `NodeBuilder.getSignature(): string`

**JSDoc:**
```typescript
/**
	 * Returns a signature with the engine's current revision.
	 *
	 * @return {string} The signature.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getSignature() {

		return `// Three.js r${ REVISION } - Node System\n`;

	}
```
</details>

### `generateConst(value: any): string`

**Parameters:**

- **`value`** `any`

**Returns:** `string`

**Calls:**

- `this.generateConst`

<details><summary>Code</summary>

```typescript
value => this.generateConst( componentType, value )
```
</details>

### `next(): { value: any; done: boolean; }`

**Returns:** `{ value: any; done: boolean; }`

<details><summary>Code</summary>

```typescript
() => ( {
						value: values[ index ],
						done: index ++ >= values.length
					} )
```
</details>

### `next(): { value: any; done: boolean; }`

**Returns:** `{ value: any; done: boolean; }`

<details><summary>Code</summary>

```typescript
() => ( {
						value: values[ index ],
						done: index ++ >= values.length
					} )
```
</details>

### `next(): { value: any; done: boolean; }`

**Returns:** `{ value: any; done: boolean; }`

<details><summary>Code</summary>

```typescript
() => ( {
						value: values[ index ],
						done: index ++ >= values.length
					} )
```
</details>

### `next(): { value: any; done: boolean; }`

**Returns:** `{ value: any; done: boolean; }`

<details><summary>Code</summary>

```typescript
() => ( {
						value: values[ index ],
						done: index ++ >= values.length
					} )
```
</details>

### `next(): { value: any; done: boolean; }`

**Returns:** `{ value: any; done: boolean; }`

<details><summary>Code</summary>

```typescript
() => ( {
						value: values[ index ],
						done: index ++ >= values.length
					} )
```
</details>

### `next(): { value: any; done: boolean; }`

**Returns:** `{ value: any; done: boolean; }`

<details><summary>Code</summary>

```typescript
() => ( {
						value: values[ index ],
						done: index ++ >= values.length
					} )
```
</details>

### `next(): { value: any; done: boolean; }`

**Returns:** `{ value: any; done: boolean; }`

<details><summary>Code</summary>

```typescript
() => ( {
						value: values[ index ],
						done: index ++ >= values.length
					} )
```
</details>

### `next(): { value: any; done: boolean; }`

**Returns:** `{ value: any; done: boolean; }`

<details><summary>Code</summary>

```typescript
() => ( {
						value: values[ index ],
						done: index ++ >= values.length
					} )
```
</details>

### `next(): { value: any; done: boolean; }`

**Returns:** `{ value: any; done: boolean; }`

<details><summary>Code</summary>

```typescript
() => ( {
						value: values[ index ],
						done: index ++ >= values.length
					} )
```
</details>

### `next(): { value: any; done: boolean; }`

**Returns:** `{ value: any; done: boolean; }`

<details><summary>Code</summary>

```typescript
() => ( {
						value: values[ index ],
						done: index ++ >= values.length
					} )
```
</details>

### `next(): { value: any; done: boolean; }`

**Returns:** `{ value: any; done: boolean; }`

<details><summary>Code</summary>

```typescript
() => ( {
						value: values[ index ],
						done: index ++ >= values.length
					} )
```
</details>

### `next(): { value: any; done: boolean; }`

**Returns:** `{ value: any; done: boolean; }`

<details><summary>Code</summary>

```typescript
() => ( {
						value: values[ index ],
						done: index ++ >= values.length
					} )
```
</details>


---

## Classes

### `NodeBuilder`

<details><summary>Class Code</summary>

```ts
class NodeBuilder {

	/**
	 * Constructs a new node builder.
	 *
	 * @param {Object3D} object - The 3D object.
	 * @param {Renderer} renderer - The current renderer.
	 * @param {NodeParser} parser - A reference to a node parser.
	 */
	constructor( object, renderer, parser ) {

		/**
		 * The 3D object.
		 *
		 * @type {Object3D}
		 */
		this.object = object;

		/**
		 * The material of the 3D object.
		 *
		 * @type {?Material}
		 */
		this.material = ( object && object.material ) || null;

		/**
		 * The geometry of the 3D object.
		 *
		 * @type {?BufferGeometry}
		 */
		this.geometry = ( object && object.geometry ) || null;

		/**
		 * The current renderer.
		 *
		 * @type {Renderer}
		 */
		this.renderer = renderer;

		/**
		 * A reference to a node parser.
		 *
		 * @type {NodeParser}
		 */
		this.parser = parser;

		/**
		 * The scene the 3D object belongs to.
		 *
		 * @type {?Scene}
		 * @default null
		 */
		this.scene = null;

		/**
		 * The camera the 3D object is rendered with.
		 *
		 * @type {?Camera}
		 * @default null
		 */
		this.camera = null;

		/**
		 * A list of all nodes the builder is processing
		 * for this 3D object.
		 *
		 * @type {Array<Node>}
		 */
		this.nodes = [];

		/**
		 * A list of all sequential nodes.
		 *
		 * @type {Array<Node>}
		 */
		this.sequentialNodes = [];

		/**
		 * A list of all nodes which {@link Node#update} method should be executed.
		 *
		 * @type {Array<Node>}
		 */
		this.updateNodes = [];

		/**
		 * A list of all nodes which {@link Node#updateBefore} method should be executed.
		 *
		 * @type {Array<Node>}
		 */
		this.updateBeforeNodes = [];

		/**
		 * A list of all nodes which {@link Node#updateAfter} method should be executed.
		 *
		 * @type {Array<Node>}
		 */
		this.updateAfterNodes = [];

		/**
		 * A dictionary that assigns each node to a unique hash.
		 *
		 * @type {Object<number,Node>}
		 */
		this.hashNodes = {};

		/**
		 * A reference to a node material observer.
		 *
		 * @type {?NodeMaterialObserver}
		 * @default null
		 */
		this.observer = null;

		/**
		 * A reference to the current lights node.
		 *
		 * @type {?LightsNode}
		 * @default null
		 */
		this.lightsNode = null;

		/**
		 * A reference to the current environment node.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.environmentNode = null;

		/**
		 * A reference to the current fog node.
		 *
		 * @type {?Node}
		 * @default null
		 */
		this.fogNode = null;

		/**
		 * The current clipping context.
		 *
		 * @type {?ClippingContext}
		 */
		this.clippingContext = null;

		/**
		 * The generated vertex shader.
		 *
		 * @type {?string}
		 */
		this.vertexShader = null;

		/**
		 * The generated fragment shader.
		 *
		 * @type {?string}
		 */
		this.fragmentShader = null;

		/**
		 * The generated compute shader.
		 *
		 * @type {?string}
		 */
		this.computeShader = null;

		/**
		 * Nodes used in the primary flow of code generation.
		 *
		 * @type {Object<string,Array<Node>>}
		 */
		this.flowNodes = { vertex: [], fragment: [], compute: [] };

		/**
		 * Nodes code from `.flowNodes`.
		 *
		 * @type {Object<string,string>}
		 */
		this.flowCode = { vertex: '', fragment: '', compute: '' };

		/**
		 * This dictionary holds the node uniforms of the builder.
		 * The uniforms are maintained in an array for each shader stage.
		 *
		 * @type {Object}
		 */
		this.uniforms = { vertex: [], fragment: [], compute: [], index: 0 };

		/**
		 * This dictionary holds the output structs of the builder.
		 * The structs are maintained in an array for each shader stage.
		 *
		 * @type {Object}
		 */
		this.structs = { vertex: [], fragment: [], compute: [], index: 0 };

		/**
		 * This dictionary holds the bindings for each shader stage.
		 *
		 * @type {Object}
		 */
		this.bindings = { vertex: {}, fragment: {}, compute: {} };

		/**
		 * This dictionary maintains the binding indices per bind group.
		 *
		 * @type {Object}
		 */
		this.bindingsIndexes = {};

		/**
		 * Reference to the array of bind groups.
		 *
		 * @type {?Array<BindGroup>}
		 */
		this.bindGroups = null;

		/**
		 * This array holds the node attributes of this builder
		 * created via {@link AttributeNode}.
		 *
		 * @type {Array<NodeAttribute>}
		 */
		this.attributes = [];

		/**
		 * This array holds the node attributes of this builder
		 * created via {@link BufferAttributeNode}.
		 *
		 * @type {Array<NodeAttribute>}
		 */
		this.bufferAttributes = [];

		/**
		 * This array holds the node varyings of this builder.
		 *
		 * @type {Array<NodeVarying>}
		 */
		this.varyings = [];

		/**
		 * This dictionary holds the (native) node codes of this builder.
		 * The codes are maintained in an array for each shader stage.
		 *
		 * @type {Object<string,Array<NodeCode>>}
		 */
		this.codes = {};

		/**
		 * This dictionary holds the node variables of this builder.
		 * The variables are maintained in an array for each shader stage.
		 * This dictionary is also used to count the number of variables
		 * according to their type (const, vars).
		 *
		 * @type {Object<string,Array<NodeVar>|number>}
		 */
		this.vars = {};

		/**
		 * This dictionary holds the declarations for each shader stage.
		 *
		 * @type {Object}
		 */
		this.declarations = {};

		/**
		 * Current code flow.
		 * All code generated in this stack will be stored in `.flow`.
		 *
		 * @type {{code: string}}
		 */
		this.flow = { code: '' };

		/**
		 * A chain of nodes.
		 * Used to check recursive calls in node-graph.
		 *
		 * @type {Array<Node>}
		 */
		this.chaining = [];

		/**
		 * The current stack.
		 * This reflects the current process in the code block hierarchy,
		 * it is useful to know if the current process is inside a conditional for example.
		 *
		 * @type {StackNode}
		 */
		this.stack = stack();

		/**
		 * List of stack nodes.
		 * The current stack hierarchy is stored in an array.
		 *
		 * @type {Array<StackNode>}
		 */
		this.stacks = [];

		/**
		 * A tab value. Used for shader string generation.
		 *
		 * @type {string}
		 * @default '\t'
		 */
		this.tab = '\t';

		/**
		 * Reference to the current function node.
		 *
		 * @type {?FunctionNode}
		 * @default null
		 */
		this.currentFunctionNode = null;

		/**
		 * The builder's context.
		 *
		 * @type {Object}
		 */
		this.context = {
			material: this.material
		};

		/**
		 * The builder's cache.
		 *
		 * @type {NodeCache}
		 */
		this.cache = new NodeCache();

		/**
		 * Since the {@link NodeBuilder#cache} might be temporarily
		 * overwritten by other caches, this member retains the reference
		 * to the builder's own cache.
		 *
		 * @type {NodeCache}
		 * @default this.cache
		 */
		this.globalCache = this.cache;

		this.flowsData = new WeakMap();

		/**
		 * The current shader stage.
		 *
		 * @type {?('vertex'|'fragment'|'compute'|'any')}
		 */
		this.shaderStage = null;

		/**
		 * The current build stage.
		 *
		 * @type {?('setup'|'analyze'|'generate')}
		 */
		this.buildStage = null;

		/**
		 * The sub-build layers.
		 *
		 * @type {Array<SubBuildNode>}
		 * @default []
		 */
		this.subBuildLayers = [];

		/**
		 * The current stack of nodes.
		 *
		 * @type {?StackNode}
		 * @default null
		 */
		this.currentStack = null;

		/**
		 * The current sub-build TSL function(Fn).
		 *
		 * @type {?string}
		 * @default null
		 */
		this.subBuildFn = null;

	}

	/**
	 * Returns the bind groups of the current renderer.
	 *
	 * @return {ChainMap} The cache.
	 */
	getBindGroupsCache() {

		let bindGroupsCache = rendererCache.get( this.renderer );

		if ( bindGroupsCache === undefined ) {

			bindGroupsCache = new ChainMap();

			rendererCache.set( this.renderer, bindGroupsCache );

		}

		return bindGroupsCache;

	}

	/**
	 * Factory method for creating an instance of {@link RenderTarget} with the given
	 * dimensions and options.
	 *
	 * @param {number} width - The width of the render target.
	 * @param {number} height - The height of the render target.
	 * @param {Object} options - The options of the render target.
	 * @return {RenderTarget} The render target.
	 */
	createRenderTarget( width, height, options ) {

		return new RenderTarget( width, height, options );

	}

	/**
	 * Factory method for creating an instance of {@link CubeRenderTarget} with the given
	 * dimensions and options.
	 *
	 * @param {number} size - The size of the cube render target.
	 * @param {Object} options - The options of the cube render target.
	 * @return {CubeRenderTarget} The cube render target.
	 */
	createCubeRenderTarget( size, options ) {

		return new CubeRenderTarget( size, options );

	}

	/**
	 * Whether the given node is included in the internal array of nodes or not.
	 *
	 * @param {Node} node - The node to test.
	 * @return {boolean} Whether the given node is included in the internal array of nodes or not.
	 */
	includes( node ) {

		return this.nodes.includes( node );

	}

	/**
	 * Returns the output struct name which is required by
	 * {@link OutputStructNode}.
	 *
	 * @abstract
	 * @return {string} The name of the output struct.
	 */
	getOutputStructName() {}

	/**
	 * Returns a bind group for the given group name and binding.
	 *
	 * @private
	 * @param {string} groupName - The group name.
	 * @param {Array<NodeUniformsGroup>} bindings - List of bindings.
	 * @return {BindGroup} The bind group
	 */
	_getBindGroup( groupName, bindings ) {

		const bindGroupsCache = this.getBindGroupsCache();

		//

		const bindingsArray = [];

		let sharedGroup = true;

		for ( const binding of bindings ) {

			bindingsArray.push( binding );

			sharedGroup = sharedGroup && binding.groupNode.shared !== true;

		}

		//

		let bindGroup;

		if ( sharedGroup ) {

			bindGroup = bindGroupsCache.get( bindingsArray );

			if ( bindGroup === undefined ) {

				bindGroup = new BindGroup( groupName, bindingsArray, this.bindingsIndexes[ groupName ].group, bindingsArray );

				bindGroupsCache.set( bindingsArray, bindGroup );

			}

		} else {

			bindGroup = new BindGroup( groupName, bindingsArray, this.bindingsIndexes[ groupName ].group, bindingsArray );

		}

		return bindGroup;

	}

	/**
	 * Returns an array of node uniform groups for the given group name and shader stage.
	 *
	 * @param {string} groupName - The group name.
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @return {Array<NodeUniformsGroup>} The array of node uniform groups.
	 */
	getBindGroupArray( groupName, shaderStage ) {

		const bindings = this.bindings[ shaderStage ];

		let bindGroup = bindings[ groupName ];

		if ( bindGroup === undefined ) {

			if ( this.bindingsIndexes[ groupName ] === undefined ) {

				this.bindingsIndexes[ groupName ] = { binding: 0, group: Object.keys( this.bindingsIndexes ).length };

			}

			bindings[ groupName ] = bindGroup = [];

		}

		return bindGroup;

	}

	/**
	 * Returns a list bindings of all shader stages separated by groups.
	 *
	 * @return {Array<BindGroup>} The list of bindings.
	 */
	getBindings() {

		let bindingsGroups = this.bindGroups;

		if ( bindingsGroups === null ) {

			const groups = {};
			const bindings = this.bindings;

			for ( const shaderStage of shaderStages ) {

				for ( const groupName in bindings[ shaderStage ] ) {

					const uniforms = bindings[ shaderStage ][ groupName ];

					const groupUniforms = groups[ groupName ] || ( groups[ groupName ] = [] );
					groupUniforms.push( ...uniforms );

				}

			}

			bindingsGroups = [];

			for ( const groupName in groups ) {

				const group = groups[ groupName ];

				const bindingsGroup = this._getBindGroup( groupName, group );

				bindingsGroups.push( bindingsGroup );

			}

			this.bindGroups = bindingsGroups;

		}

		return bindingsGroups;

	}

	/**
	 * Sorts the bind groups and updates {@link NodeBuilder#bindingsIndexes}.
	 */
	sortBindingGroups() {

		const bindingsGroups = this.getBindings();

		bindingsGroups.sort( ( a, b ) => ( a.bindings[ 0 ].groupNode.order - b.bindings[ 0 ].groupNode.order ) );

		for ( let i = 0; i < bindingsGroups.length; i ++ ) {

			const bindingGroup = bindingsGroups[ i ];
			this.bindingsIndexes[ bindingGroup.name ].group = i;

			bindingGroup.index = i;

		}

	}

	/**
	 * The builder maintains each node in a hash-based dictionary.
	 * This method sets the given node (value) with the given hash (key) into this dictionary.
	 *
	 * @param {Node} node - The node to add.
	 * @param {number} hash - The hash of the node.
	 */
	setHashNode( node, hash ) {

		this.hashNodes[ hash ] = node;

	}

	/**
	 * Adds a node to this builder.
	 *
	 * @param {Node} node - The node to add.
	 */
	addNode( node ) {

		if ( this.nodes.includes( node ) === false ) {

			this.nodes.push( node );

			this.setHashNode( node, node.getHash( this ) );

		}

	}

	/**
	 * It is used to add Nodes that will be used as FRAME and RENDER events,
	 * and need to follow a certain sequence in the calls to work correctly.
	 * This function should be called after 'setup()' in the 'build()' process to ensure that the child nodes are processed first.
	 *
	 * @param {Node} node - The node to add.
	 */
	addSequentialNode( node ) {

		if ( this.sequentialNodes.includes( node ) === false ) {

			this.sequentialNodes.push( node );

		}

	}

	/**
	 * Checks the update types of nodes
	 */
	buildUpdateNodes() {

		for ( const node of this.nodes ) {

			const updateType = node.getUpdateType();

			if ( updateType !== NodeUpdateType.NONE ) {

				this.updateNodes.push( node.getSelf() );

			}

		}

		for ( const node of this.sequentialNodes ) {

			const updateBeforeType = node.getUpdateBeforeType();
			const updateAfterType = node.getUpdateAfterType();

			if ( updateBeforeType !== NodeUpdateType.NONE ) {

				this.updateBeforeNodes.push( node.getSelf() );

			}

			if ( updateAfterType !== NodeUpdateType.NONE ) {

				this.updateAfterNodes.push( node.getSelf() );

			}

		}

	}

	/**
	 * A reference the current node which is the
	 * last node in the chain of nodes.
	 *
	 * @type {Node}
	 */
	get currentNode() {

		return this.chaining[ this.chaining.length - 1 ];

	}

	/**
	 * Whether the given texture is filtered or not.
	 *
	 * @param {Texture} texture - The texture to check.
	 * @return {boolean} Whether the given texture is filtered or not.
	 */
	isFilteredTexture( texture ) {

		return ( texture.magFilter === LinearFilter || texture.magFilter === LinearMipmapNearestFilter || texture.magFilter === NearestMipmapLinearFilter || texture.magFilter === LinearMipmapLinearFilter ||
			texture.minFilter === LinearFilter || texture.minFilter === LinearMipmapNearestFilter || texture.minFilter === NearestMipmapLinearFilter || texture.minFilter === LinearMipmapLinearFilter );

	}

	/**
	 * Adds the given node to the internal node chain.
	 * This is used to check recursive calls in node-graph.
	 *
	 * @param {Node} node - The node to add.
	 */
	addChain( node ) {

		/*
		if ( this.chaining.indexOf( node ) !== - 1 ) {

			console.warn( 'Recursive node: ', node );

		}
		*/

		this.chaining.push( node );

	}

	/**
	 * Removes the given node from the internal node chain.
	 *
	 * @param {Node} node - The node to remove.
	 */
	removeChain( node ) {

		const lastChain = this.chaining.pop();

		if ( lastChain !== node ) {

			throw new Error( 'NodeBuilder: Invalid node chaining!' );

		}

	}

	/**
	 * Returns the native shader method name for a given generic name. E.g.
	 * the method name `textureDimensions` matches the WGSL name but must be
	 * resolved to `textureSize` in GLSL.
	 *
	 * @abstract
	 * @param {string} method - The method name to resolve.
	 * @return {string} The resolved method name.
	 */
	getMethod( method ) {

		return method;

	}

	/**
	 * Returns the native snippet for a ternary operation. E.g. GLSL would output
	 * a ternary op as `cond ? x : y` whereas WGSL would output it as `select(y, x, cond)`
	 *
	 * @abstract
	 * @param {string} condSnippet - The condition determining which expression gets resolved.
	 * @param {string} ifSnippet - The expression to resolve to if the condition is true.
	 * @param {string} elseSnippet - The expression to resolve to if the condition is false.
	 * @return {string} The resolved method name.
	 */
	getTernary( /* condSnippet, ifSnippet, elseSnippet*/ ) {

		return null;

	}

	/**
	 * Returns a node for the given hash, see {@link NodeBuilder#setHashNode}.
	 *
	 * @param {number} hash - The hash of the node.
	 * @return {Node} The found node.
	 */
	getNodeFromHash( hash ) {

		return this.hashNodes[ hash ];

	}

	/**
	 * Adds the Node to a target flow so that it can generate code in the 'generate' process.
	 *
	 * @param {('vertex'|'fragment'|'compute')} shaderStage - The shader stage.
	 * @param {Node} node - The node to add.
	 * @return {Node} The node.
	 */
	addFlow( shaderStage, node ) {

		this.flowNodes[ shaderStage ].push( node );

		return node;

	}

	/**
	 * Sets builder's context.
	 *
	 * @param {Object} context - The context to set.
	 */
	setContext( context ) {

		this.context = context;

	}

	/**
	 * Returns the builder's current context.
	 *
	 * @return {Object} The builder's current context.
	 */
	getContext() {

		return this.context;

	}

	/**
	 * Gets a context used in shader construction that can be shared across different materials.
	 * This is necessary since the renderer cache can reuse shaders generated in one material and use them in another.
	 *
	 * @return {Object} The builder's current context without material.
	 */
	getSharedContext() {

		const context = { ...this.context };

		delete context.material;

		return this.context;

	}

	/**
	 * Sets builder's cache.
	 *
	 * @param {NodeCache} cache - The cache to set.
	 */
	setCache( cache ) {

		this.cache = cache;

	}

	/**
	 * Returns the builder's current cache.
	 *
	 * @return {NodeCache} The builder's current cache.
	 */
	getCache() {

		return this.cache;

	}

	/**
	 * Returns a cache for the given node.
	 *
	 * @param {Node} node - The node.
	 * @param {boolean} [parent=true] - Whether this node refers to a shared parent cache or not.
	 * @return {NodeCache} The cache.
	 */
	getCacheFromNode( node, parent = true ) {

		const data = this.getDataFromNode( node );
		if ( data.cache === undefined ) data.cache = new NodeCache( parent ? this.getCache() : null );

		return data.cache;

	}

	/**
	 * Whether the requested feature is available or not.
	 *
	 * @abstract
	 * @param {string} name - The requested feature.
	 * @return {boolean} Whether the requested feature is supported or not.
	 */
	isAvailable( /*name*/ ) {

		return false;

	}

	/**
	 * Returns the vertexIndex input variable as a native shader string.
	 *
	 * @abstract
	 * @return {string} The instanceIndex shader string.
	 */
	getVertexIndex() {

		console.warn( 'Abstract function.' );

	}

	/**
	 * Returns the instanceIndex input variable as a native shader string.
	 *
	 * @abstract
	 * @return {string} The instanceIndex shader string.
	 */
	getInstanceIndex() {

		console.warn( 'Abstract function.' );

	}

	/**
	 * Returns the drawIndex input variable as a native shader string.
	 * Only relevant for WebGL and its `WEBGL_multi_draw` extension.
	 *
	 * @abstract
	 * @return {?string} The drawIndex shader string.
	 */
	getDrawIndex() {

		console.warn( 'Abstract function.' );

	}

	/**
	 * Returns the frontFacing input variable as a native shader string.
	 *
	 * @abstract
	 * @return {string} The frontFacing shader string.
	 */
	getFrontFacing() {

		console.warn( 'Abstract function.' );

	}

	/**
	 * Returns the fragCoord input variable as a native shader string.
	 *
	 * @abstract
	 * @return {string} The fragCoord shader string.
	 */
	getFragCoord() {

		console.warn( 'Abstract function.' );

	}

	/**
	 * Whether to flip texture data along its vertical axis or not. WebGL needs
	 * this method evaluate to `true`, WebGPU to `false`.
	 *
	 * @abstract
	 * @return {boolean} Whether to flip texture data along its vertical axis or not.
	 */
	isFlipY() {

		return false;

	}

	/**
	 * Calling this method increases the usage count for the given node by one.
	 *
	 * @param {Node} node - The node to increase the usage count for.
	 * @return {number} The updated usage count.
	 */
	increaseUsage( node ) {

		const nodeData = this.getDataFromNode( node );
		nodeData.usageCount = nodeData.usageCount === undefined ? 1 : nodeData.usageCount + 1;

		return nodeData.usageCount;

	}

	/**
	 * Generates a texture sample shader string for the given texture data.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The texture property name.
	 * @param {string} uvSnippet - Snippet defining the texture coordinates.
	 * @return {string} The generated shader string.
	 */
	generateTexture( /* texture, textureProperty, uvSnippet */ ) {

		console.warn( 'Abstract function.' );

	}

	/**
	 * Generates a texture LOD shader string for the given texture data.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The texture property name.
	 * @param {string} uvSnippet - Snippet defining the texture coordinates.
	 * @param {?string} depthSnippet - Snippet defining the 0-based texture array index to sample.
	 * @param {string} levelSnippet - Snippet defining the mip level.
	 * @return {string} The generated shader string.
	 */
	generateTextureLod( /* texture, textureProperty, uvSnippet, depthSnippet, levelSnippet */ ) {

		console.warn( 'Abstract function.' );

	}

	/**
	 * Generates the array declaration string.
	 *
	 * @param {string} type - The type.
	 * @param {?number} [count] - The count.
	 * @return {string} The generated value as a shader string.
	 */
	generateArrayDeclaration( type, count ) {

		return this.getType( type ) + '[ ' + count + ' ]';

	}

	/**
	 * Generates the array shader string for the given type and value.
	 *
	 * @param {string} type - The type.
	 * @param {?number} [count] - The count.
	 * @param {?Array<Node>} [values=null] - The default values.
	 * @return {string} The generated value as a shader string.
	 */
	generateArray( type, count, values = null ) {

		let snippet = this.generateArrayDeclaration( type, count ) + '( ';

		for ( let i = 0; i < count; i ++ ) {

			const value = values ? values[ i ] : null;

			if ( value !== null ) {

				snippet += value.build( this, type );

			} else {

				snippet += this.generateConst( type );

			}

			if ( i < count - 1 ) snippet += ', ';

		}

		snippet += ' )';

		return snippet;

	}

	/**
	 * Generates the struct shader string.
	 *
	 * @param {string} type - The type.
	 * @param {Array<Object>} [membersLayout] - The count.
	 * @param {?Array<Node>} [values=null] - The default values.
	 * @return {string} The generated value as a shader string.
	 */
	generateStruct( type, membersLayout, values = null ) {

		const snippets = [];

		for ( const member of membersLayout ) {

			const { name, type } = member;

			if ( values && values[ name ] && values[ name ].isNode ) {

				snippets.push( values[ name ].build( this, type ) );

			} else {

				snippets.push( this.generateConst( type ) );

			}

		}

		return type + '( ' + snippets.join( ', ' ) + ' )';

	}

	/**
	 * Generates the shader string for the given type and value.
	 *
	 * @param {string} type - The type.
	 * @param {?any} [value=null] - The value.
	 * @return {string} The generated value as a shader string.
	 */
	generateConst( type, value = null ) {

		if ( value === null ) {

			if ( type === 'float' || type === 'int' || type === 'uint' ) value = 0;
			else if ( type === 'bool' ) value = false;
			else if ( type === 'color' ) value = new Color();
			else if ( type === 'vec2' ) value = new Vector2();
			else if ( type === 'vec3' ) value = new Vector3();
			else if ( type === 'vec4' ) value = new Vector4();

		}

		if ( type === 'float' ) return toFloat( value );
		if ( type === 'int' ) return `${ Math.round( value ) }`;
		if ( type === 'uint' ) return value >= 0 ? `${ Math.round( value ) }u` : '0u';
		if ( type === 'bool' ) return value ? 'true' : 'false';
		if ( type === 'color' ) return `${ this.getType( 'vec3' ) }( ${ toFloat( value.r ) }, ${ toFloat( value.g ) }, ${ toFloat( value.b ) } )`;

		const typeLength = this.getTypeLength( type );

		const componentType = this.getComponentType( type );

		const generateConst = value => this.generateConst( componentType, value );

		if ( typeLength === 2 ) {

			return `${ this.getType( type ) }( ${ generateConst( value.x ) }, ${ generateConst( value.y ) } )`;

		} else if ( typeLength === 3 ) {

			return `${ this.getType( type ) }( ${ generateConst( value.x ) }, ${ generateConst( value.y ) }, ${ generateConst( value.z ) } )`;

		} else if ( typeLength === 4 && type !== 'mat2' ) {

			return `${ this.getType( type ) }( ${ generateConst( value.x ) }, ${ generateConst( value.y ) }, ${ generateConst( value.z ) }, ${ generateConst( value.w ) } )`;

		} else if ( typeLength >= 4 && value && ( value.isMatrix2 || value.isMatrix3 || value.isMatrix4 ) ) {

			return `${ this.getType( type ) }( ${ value.elements.map( generateConst ).join( ', ' ) } )`;

		} else if ( typeLength > 4 ) {

			return `${ this.getType( type ) }()`;

		}

		throw new Error( `NodeBuilder: Type '${type}' not found in generate constant attempt.` );

	}

	/**
	 * It might be necessary to convert certain data types to different ones
	 * so this method can be used to hide the conversion.
	 *
	 * @param {string} type - The type.
	 * @return {string} The updated type.
	 */
	getType( type ) {

		if ( type === 'color' ) return 'vec3';

		return type;

	}

	/**
	 * Whether the given attribute name is defined in the geometry or not.
	 *
	 * @param {string} name - The attribute name.
	 * @return {boolean} Whether the given attribute name is defined in the geometry.
	 */
	hasGeometryAttribute( name ) {

		return this.geometry && this.geometry.getAttribute( name ) !== undefined;

	}

	/**
	 * Returns a node attribute for the given name and type.
	 *
	 * @param {string} name - The attribute's name.
	 * @param {string} type - The attribute's type.
	 * @return {NodeAttribute} The node attribute.
	 */
	getAttribute( name, type ) {

		const attributes = this.attributes;

		// find attribute

		for ( const attribute of attributes ) {

			if ( attribute.name === name ) {

				return attribute;

			}

		}

		// create a new if no exist

		const attribute = new NodeAttribute( name, type );

		this.registerDeclaration( attribute );

		attributes.push( attribute );

		return attribute;

	}

	/**
	 * Returns for the given node and shader stage the property name for the shader.
	 *
	 * @param {Node} node - The node.
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @return {string} The property name.
	 */
	getPropertyName( node/*, shaderStage*/ ) {

		return node.name;

	}

	/**
	 * Whether the given type is a vector type or not.
	 *
	 * @param {string} type - The type to check.
	 * @return {boolean} Whether the given type is a vector type or not.
	 */
	isVector( type ) {

		return /vec\d/.test( type );

	}

	/**
	 * Whether the given type is a matrix type or not.
	 *
	 * @param {string} type - The type to check.
	 * @return {boolean} Whether the given type is a matrix type or not.
	 */
	isMatrix( type ) {

		return /mat\d/.test( type );

	}

	/**
	 * Whether the given type is a reference type or not.
	 *
	 * @param {string} type - The type to check.
	 * @return {boolean} Whether the given type is a reference type or not.
	 */
	isReference( type ) {

		return type === 'void' || type === 'property' || type === 'sampler' || type === 'samplerComparison' || type === 'texture' || type === 'cubeTexture' || type === 'storageTexture' || type === 'depthTexture' || type === 'texture3D';

	}

	/**
	 * Checks if the given texture requires a manual conversion to the working color space.
	 *
	 * @abstract
	 * @param {Texture} texture - The texture to check.
	 * @return {boolean} Whether the given texture requires a conversion to working color space or not.
	 */
	needsToWorkingColorSpace( /*texture*/ ) {

		return false;

	}

	/**
	 * Returns the component type of a given texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @return {string} The component type.
	 */
	getComponentTypeFromTexture( texture ) {

		const type = texture.type;

		if ( texture.isDataTexture ) {

			if ( type === IntType ) return 'int';
			if ( type === UnsignedIntType ) return 'uint';

		}

		return 'float';

	}

	/**
	 * Returns the element type for a given type.
	 *
	 * @param {string} type - The type.
	 * @return {string} The element type.
	 */
	getElementType( type ) {

		if ( type === 'mat2' ) return 'vec2';
		if ( type === 'mat3' ) return 'vec3';
		if ( type === 'mat4' ) return 'vec4';

		return this.getComponentType( type );

	}

	/**
	 * Returns the component type for a given type.
	 *
	 * @param {string} type - The type.
	 * @return {string} The component type.
	 */
	getComponentType( type ) {

		type = this.getVectorType( type );

		if ( type === 'float' || type === 'bool' || type === 'int' || type === 'uint' ) return type;

		const componentType = /(b|i|u|)(vec|mat)([2-4])/.exec( type );

		if ( componentType === null ) return null;

		if ( componentType[ 1 ] === 'b' ) return 'bool';
		if ( componentType[ 1 ] === 'i' ) return 'int';
		if ( componentType[ 1 ] === 'u' ) return 'uint';

		return 'float';

	}

	/**
	 * Returns the vector type for a given type.
	 *
	 * @param {string} type - The type.
	 * @return {string} The vector type.
	 */
	getVectorType( type ) {

		if ( type === 'color' ) return 'vec3';
		if ( type === 'texture' || type === 'cubeTexture' || type === 'storageTexture' || type === 'texture3D' ) return 'vec4';

		return type;

	}

	/**
	 * Returns the data type for the given the length and component type.
	 *
	 * @param {number} length - The length.
	 * @param {string} [componentType='float'] - The component type.
	 * @return {string} The type.
	 */
	getTypeFromLength( length, componentType = 'float' ) {

		if ( length === 1 ) return componentType;

		let baseType = getTypeFromLength( length );
		const prefix = componentType === 'float' ? '' : componentType[ 0 ];

		// fix edge case for mat2x2 being same size as vec4
		if ( /mat2/.test( componentType ) === true ) {

			baseType = baseType.replace( 'vec', 'mat' );

		}

		return prefix + baseType;

	}

	/**
	 * Returns the type for a given typed array.
	 *
	 * @param {TypedArray} array - The typed array.
	 * @return {string} The type.
	 */
	getTypeFromArray( array ) {

		return typeFromArray.get( array.constructor );

	}

	/**
	 * Returns the type is an integer type.
	 *
	 * @param {string} type - The type.
	 * @return {boolean} Whether the type is an integer type or not.
	 */
	isInteger( type ) {

		return /int|uint|(i|u)vec/.test( type );

	}

	/**
	 * Returns the type for a given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 * @return {string} The type.
	 */
	getTypeFromAttribute( attribute ) {

		let dataAttribute = attribute;

		if ( attribute.isInterleavedBufferAttribute ) dataAttribute = attribute.data;

		const array = dataAttribute.array;
		const itemSize = attribute.itemSize;
		const normalized = attribute.normalized;

		let arrayType;

		if ( ! ( attribute instanceof Float16BufferAttribute ) && normalized !== true ) {

			arrayType = this.getTypeFromArray( array );

		}

		return this.getTypeFromLength( itemSize, arrayType );

	}

	/**
	 * Returns the length for the given data type.
	 *
	 * @param {string} type - The data type.
	 * @return {number} The length.
	 */
	getTypeLength( type ) {

		const vecType = this.getVectorType( type );
		const vecNum = /vec([2-4])/.exec( vecType );

		if ( vecNum !== null ) return Number( vecNum[ 1 ] );
		if ( vecType === 'float' || vecType === 'bool' || vecType === 'int' || vecType === 'uint' ) return 1;
		if ( /mat2/.test( type ) === true ) return 4;
		if ( /mat3/.test( type ) === true ) return 9;
		if ( /mat4/.test( type ) === true ) return 16;

		return 0;

	}

	/**
	 * Returns the vector type for a given matrix type.
	 *
	 * @param {string} type - The matrix type.
	 * @return {string} The vector type.
	 */
	getVectorFromMatrix( type ) {

		return type.replace( 'mat', 'vec' );

	}

	/**
	 * For a given type this method changes the component type to the
	 * given value. E.g. `vec4` should be changed to the new component type
	 * `uint` which results in `uvec4`.
	 *
	 * @param {string} type - The type.
	 * @param {string} newComponentType - The new component type.
	 * @return {string} The new type.
	 */
	changeComponentType( type, newComponentType ) {

		return this.getTypeFromLength( this.getTypeLength( type ), newComponentType );

	}

	/**
	 * Returns the integer type pendant for the given type.
	 *
	 * @param {string} type - The type.
	 * @return {string} The integer type.
	 */
	getIntegerType( type ) {

		const componentType = this.getComponentType( type );

		if ( componentType === 'int' || componentType === 'uint' ) return type;

		return this.changeComponentType( type, 'int' );

	}

	/**
	 * Adds a stack node to the internal stack.
	 *
	 * @return {StackNode} The added stack node.
	 */
	addStack() {

		this.stack = stack( this.stack );

		this.stacks.push( getCurrentStack() || this.stack );
		setCurrentStack( this.stack );

		return this.stack;

	}

	/**
	 * Removes the last stack node from the internal stack.
	 *
	 * @return {StackNode} The removed stack node.
	 */
	removeStack() {

		const lastStack = this.stack;
		this.stack = lastStack.parent;

		setCurrentStack( this.stacks.pop() );

		return lastStack;

	}

	/**
	 * The builder maintains (cached) data for each node during the building process. This method
	 * can be used to get these data for a specific shader stage and cache.
	 *
	 * @param {Node} node - The node to get the data for.
	 * @param {('vertex'|'fragment'|'compute'|'any')} [shaderStage=this.shaderStage] - The shader stage.
	 * @param {?NodeCache} cache - An optional cache.
	 * @return {Object} The node data.
	 */
	getDataFromNode( node, shaderStage = this.shaderStage, cache = null ) {

		cache = cache === null ? ( node.isGlobal( this ) ? this.globalCache : this.cache ) : cache;

		let nodeData = cache.getData( node );

		if ( nodeData === undefined ) {

			nodeData = {};

			cache.setData( node, nodeData );

		}

		if ( nodeData[ shaderStage ] === undefined ) nodeData[ shaderStage ] = {};

		//

		let data = nodeData[ shaderStage ];

		const subBuilds = nodeData.any ? nodeData.any.subBuilds : null;
		const subBuild = this.getClosestSubBuild( subBuilds );

		if ( subBuild ) {

			if ( data.subBuildsCache === undefined ) data.subBuildsCache = {};

			data = data.subBuildsCache[ subBuild ] || ( data.subBuildsCache[ subBuild ] = {} );
			data.subBuilds = subBuilds;

		}

		return data;

	}

	/**
	 * Returns the properties for the given node and shader stage.
	 *
	 * @param {Node} node - The node to get the properties for.
	 * @param {('vertex'|'fragment'|'compute'|'any')} [shaderStage='any'] - The shader stage.
	 * @return {Object} The node properties.
	 */
	getNodeProperties( node, shaderStage = 'any' ) {

		const nodeData = this.getDataFromNode( node, shaderStage );

		return nodeData.properties || ( nodeData.properties = { outputNode: null } );

	}

	/**
	 * Returns an instance of {@link NodeAttribute} for the given buffer attribute node.
	 *
	 * @param {BufferAttributeNode} node - The buffer attribute node.
	 * @param {string} type - The node type.
	 * @return {NodeAttribute} The node attribute.
	 */
	getBufferAttributeFromNode( node, type ) {

		const nodeData = this.getDataFromNode( node );

		let bufferAttribute = nodeData.bufferAttribute;

		if ( bufferAttribute === undefined ) {

			const index = this.uniforms.index ++;

			bufferAttribute = new NodeAttribute( 'nodeAttribute' + index, type, node );

			this.bufferAttributes.push( bufferAttribute );

			nodeData.bufferAttribute = bufferAttribute;

		}

		return bufferAttribute;

	}

	/**
	 * Returns an instance of {@link StructType} for the given output struct node.
	 *
	 * @param {OutputStructNode} node - The output struct node.
	 * @param {Array<Object>} membersLayout - The output struct types.
	 * @param {?string} [name=null] - The name of the struct.
	 * @param {('vertex'|'fragment'|'compute'|'any')} [shaderStage=this.shaderStage] - The shader stage.
	 * @return {StructType} The struct type attribute.
	 */
	getStructTypeFromNode( node, membersLayout, name = null, shaderStage = this.shaderStage ) {

		const nodeData = this.getDataFromNode( node, shaderStage, this.globalCache );

		let structType = nodeData.structType;

		if ( structType === undefined ) {

			const index = this.structs.index ++;

			if ( name === null ) name = 'StructType' + index;

			structType = new StructType( name, membersLayout );

			this.structs[ shaderStage ].push( structType );

			nodeData.structType = structType;

		}

		return structType;

	}

	/**
	 * Returns an instance of {@link StructType} for the given output struct node.
	 *
	 * @param {OutputStructNode} node - The output struct node.
	 * @param {Array<Object>} membersLayout - The output struct types.
	 * @return {StructType} The struct type attribute.
	 */
	getOutputStructTypeFromNode( node, membersLayout ) {

		const structType = this.getStructTypeFromNode( node, membersLayout, 'OutputType', 'fragment' );
		structType.output = true;

		return structType;

	}

	/**
	 * Returns an instance of {@link NodeUniform} for the given uniform node.
	 *
	 * @param {UniformNode} node - The uniform node.
	 * @param {string} type - The uniform type.
	 * @param {('vertex'|'fragment'|'compute'|'any')} [shaderStage=this.shaderStage] - The shader stage.
	 * @param {?string} name - The name of the uniform.
	 * @return {NodeUniform} The node uniform.
	 */
	getUniformFromNode( node, type, shaderStage = this.shaderStage, name = null ) {

		const nodeData = this.getDataFromNode( node, shaderStage, this.globalCache );

		let nodeUniform = nodeData.uniform;

		if ( nodeUniform === undefined ) {

			const index = this.uniforms.index ++;

			nodeUniform = new NodeUniform( name || ( 'nodeUniform' + index ), type, node );

			this.uniforms[ shaderStage ].push( nodeUniform );

			this.registerDeclaration( nodeUniform );

			nodeData.uniform = nodeUniform;

		}

		return nodeUniform;

	}

	/**
	 * Returns an instance of {@link NodeVar} for the given variable node.
	 *
	 * @param {VarNode} node - The variable node.
	 * @param {?string} name - The variable's name.
	 * @param {string} [type=node.getNodeType( this )] - The variable's type.
	 * @param {('vertex'|'fragment'|'compute'|'any')} [shaderStage=this.shaderStage] - The shader stage.
	 * @param {boolean} [readOnly=false] - Whether the variable is read-only or not.
	 *
	 * @return {NodeVar} The node variable.
	 */
	getVarFromNode( node, name = null, type = node.getNodeType( this ), shaderStage = this.shaderStage, readOnly = false ) {

		const nodeData = this.getDataFromNode( node, shaderStage );
		const subBuildVariable = this.getSubBuildProperty( 'variable', nodeData.subBuilds );

		let nodeVar = nodeData[ subBuildVariable ];

		if ( nodeVar === undefined ) {

			const idNS = readOnly ? '_const' : '_var';

			const vars = this.vars[ shaderStage ] || ( this.vars[ shaderStage ] = [] );
			const id = this.vars[ idNS ] || ( this.vars[ idNS ] = 0 );

			if ( name === null ) {

				name = ( readOnly ? 'nodeConst' : 'nodeVar' ) + id;

				this.vars[ idNS ] ++;

			}

			//

			if ( subBuildVariable !== 'variable' ) {

				name = this.getSubBuildProperty( name, nodeData.subBuilds );

			}

			//

			const count = node.getArrayCount( this );

			nodeVar = new NodeVar( name, type, readOnly, count );

			if ( ! readOnly ) {

				vars.push( nodeVar );

			}

			this.registerDeclaration( nodeVar );

			nodeData[ subBuildVariable ] = nodeVar;

		}

		return nodeVar;

	}

	/**
	 * Returns whether a Node or its flow is deterministic, useful for use in `const`.
	 *
	 * @param {Node} node - The varying node.
	 * @return {boolean} Returns true if deterministic.
	 */
	isDeterministic( node ) {

		if ( node.isMathNode ) {

			return this.isDeterministic( node.aNode ) &&
				( node.bNode ? this.isDeterministic( node.bNode ) : true ) &&
				( node.cNode ? this.isDeterministic( node.cNode ) : true );

		} else if ( node.isOperatorNode ) {

			return this.isDeterministic( node.aNode ) &&
				( node.bNode ? this.isDeterministic( node.bNode ) : true );

		} else if ( node.isArrayNode ) {

			if ( node.values !== null ) {

				for ( const n of node.values ) {

					if ( ! this.isDeterministic( n ) ) {

						return false;

					}

				}

			}

			return true;

		} else if ( node.isConstNode ) {

			return true;

		}

		return false;

	}

	/**
	 * Returns an instance of {@link NodeVarying} for the given varying node.
	 *
	 * @param {(VaryingNode|PropertyNode)} node - The varying node.
	 * @param {?string} name - The varying's name.
	 * @param {string} [type=node.getNodeType( this )] - The varying's type.
	 * @param {?string} interpolationType - The interpolation type of the varying.
	 * @param {?string} interpolationSampling - The interpolation sampling type of the varying.
	 * @return {NodeVar} The node varying.
	 */
	getVaryingFromNode( node, name = null, type = node.getNodeType( this ), interpolationType = null, interpolationSampling = null ) {

		const nodeData = this.getDataFromNode( node, 'any' );
		const subBuildVarying = this.getSubBuildProperty( 'varying', nodeData.subBuilds );

		let nodeVarying = nodeData[ subBuildVarying ];

		if ( nodeVarying === undefined ) {

			const varyings = this.varyings;
			const index = varyings.length;

			if ( name === null ) name = 'nodeVarying' + index;

			//

			if ( subBuildVarying !== 'varying' ) {

				name = this.getSubBuildProperty( name, nodeData.subBuilds );

			}

			//

			nodeVarying = new NodeVarying( name, type, interpolationType, interpolationSampling );

			varyings.push( nodeVarying );

			this.registerDeclaration( nodeVarying );

			nodeData[ subBuildVarying ] = nodeVarying;

		}

		return nodeVarying;

	}

	/**
	 * Registers a node declaration in the current shader stage.
	 *
	 * @param {Object} node - The node to be registered.
	 */
	registerDeclaration( node ) {

		const shaderStage = this.shaderStage;
		const declarations = this.declarations[ shaderStage ] || ( this.declarations[ shaderStage ] = {} );

		const property = this.getPropertyName( node );

		let index = 1;
		let name = property;

		// Automatically renames the property if the name is already in use.

		while ( declarations[ name ] !== undefined ) {

			name = property + '_' + index ++;

		}

		if ( index > 1 ) {

			node.name = name;

			console.warn( `THREE.TSL: Declaration name '${ property }' of '${ node.type }' already in use. Renamed to '${ name }'.` );

		}

		declarations[ name ] = node;

	}

	/**
	 * Returns an instance of {@link NodeCode} for the given code node.
	 *
	 * @param {CodeNode} node - The code node.
	 * @param {string} type - The node type.
	 * @param {('vertex'|'fragment'|'compute'|'any')} [shaderStage=this.shaderStage] - The shader stage.
	 * @return {NodeCode} The node code.
	 */
	getCodeFromNode( node, type, shaderStage = this.shaderStage ) {

		const nodeData = this.getDataFromNode( node );

		let nodeCode = nodeData.code;

		if ( nodeCode === undefined ) {

			const codes = this.codes[ shaderStage ] || ( this.codes[ shaderStage ] = [] );
			const index = codes.length;

			nodeCode = new NodeCode( 'nodeCode' + index, type );

			codes.push( nodeCode );

			nodeData.code = nodeCode;

		}

		return nodeCode;

	}

	/**
	 * Adds a code flow based on the code-block hierarchy.

	 * This is used so that code-blocks like If,Else create their variables locally if the Node
	 * is only used inside one of these conditionals in the current shader stage.
	 *
	 * @param {Node} node - The node to add.
	 * @param {Node} nodeBlock - Node-based code-block. Usually 'ConditionalNode'.
	 */
	addFlowCodeHierarchy( node, nodeBlock ) {

		const { flowCodes, flowCodeBlock } = this.getDataFromNode( node );

		let needsFlowCode = true;
		let nodeBlockHierarchy = nodeBlock;

		while ( nodeBlockHierarchy ) {

			if ( flowCodeBlock.get( nodeBlockHierarchy ) === true ) {

				needsFlowCode = false;
				break;

			}

			nodeBlockHierarchy = this.getDataFromNode( nodeBlockHierarchy ).parentNodeBlock;

		}

		if ( needsFlowCode ) {

			for ( const flowCode of flowCodes ) {

				this.addLineFlowCode( flowCode );

			}

		}

	}

	/**
	 * Add a inline-code to the current flow code-block.
	 *
	 * @param {Node} node - The node to add.
	 * @param {string} code - The code to add.
	 * @param {Node} nodeBlock - Current ConditionalNode
	 */
	addLineFlowCodeBlock( node, code, nodeBlock ) {

		const nodeData = this.getDataFromNode( node );
		const flowCodes = nodeData.flowCodes || ( nodeData.flowCodes = [] );
		const codeBlock = nodeData.flowCodeBlock || ( nodeData.flowCodeBlock = new WeakMap() );

		flowCodes.push( code );
		codeBlock.set( nodeBlock, true );

	}

	/**
	 * Add a inline-code to the current flow.
	 *
	 * @param {string} code - The code to add.
	 * @param {?Node} [node= null] - Optional Node, can help the system understand if the Node is part of a code-block.
	 * @return {NodeBuilder} A reference to this node builder.
	 */
	addLineFlowCode( code, node = null ) {

		if ( code === '' ) return this;

		if ( node !== null && this.context.nodeBlock ) {

			this.addLineFlowCodeBlock( node, code, this.context.nodeBlock );

		}

		code = this.tab + code;

		if ( ! /;\s*$/.test( code ) ) {

			code = code + ';\n';

		}

		this.flow.code += code;

		return this;

	}

	/**
	 * Adds a code to the current code flow.
	 *
	 * @param {string} code - Shader code.
	 * @return {NodeBuilder} A reference to this node builder.
	 */
	addFlowCode( code ) {

		this.flow.code += code;

		return this;

	}

	/**
	 * Add tab in the code that will be generated so that other snippets respect the current tabulation.
	 * Typically used in codes with If,Else.
	 *
	 * @return {NodeBuilder} A reference to this node builder.
	 */
	addFlowTab() {

		this.tab += '\t';

		return this;

	}

	/**
	 * Removes a tab.
	 *
	 * @return {NodeBuilder} A reference to this node builder.
	 */
	removeFlowTab() {

		this.tab = this.tab.slice( 0, - 1 );

		return this;

	}

	/**
	 * Gets the current flow data based on a Node.
	 *
	 * @param {Node} node - Node that the flow was started.
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @return {Object} The flow data.
	 */
	getFlowData( node/*, shaderStage*/ ) {

		return this.flowsData.get( node );

	}

	/**
	 * Executes the node flow based on a root node to generate the final shader code.
	 *
	 * @param {Node} node - The node to execute.
	 * @return {Object} The code flow.
	 */
	flowNode( node ) {

		const output = node.getNodeType( this );

		const flowData = this.flowChildNode( node, output );

		this.flowsData.set( node, flowData );

		return flowData;

	}

	/**
	 * Includes a node in the current function node.
	 *
	 * @param {Node} node - The node to include.
	 * @returns {void}
	 */
	addInclude( node ) {

		if ( this.currentFunctionNode !== null ) {

			this.currentFunctionNode.includes.push( node );

		}

	}

	/**
	 * Returns the native shader operator name for a given generic name.
	 * It is a similar type of method like {@link NodeBuilder#getMethod}.
	 *
	 * @param {ShaderNodeInternal} shaderNode - The shader node to build the function node with.
	 * @return {FunctionNode} The build function node.
	 */
	buildFunctionNode( shaderNode ) {

		const fn = new FunctionNode();

		const previous = this.currentFunctionNode;

		this.currentFunctionNode = fn;

		fn.code = this.buildFunctionCode( shaderNode );

		this.currentFunctionNode = previous;

		return fn;

	}

	/**
	 * Generates a code flow based on a TSL function: Fn().
	 *
	 * @param {ShaderNodeInternal} shaderNode - A function code will be generated based on the input.
	 * @return {Object}
	 */
	flowShaderNode( shaderNode ) {

		const layout = shaderNode.layout;

		const inputs = {
			[ Symbol.iterator ]() {

				let index = 0;
				const values = Object.values( this );
				return {
					next: () => ( {
						value: values[ index ],
						done: index ++ >= values.length
					} )
				};

			}
		};

		for ( const input of layout.inputs ) {

			inputs[ input.name ] = new ParameterNode( input.type, input.name );

		}

		//

		shaderNode.layout = null;

		const callNode = shaderNode.call( inputs );
		const flowData = this.flowStagesNode( callNode, layout.type );

		shaderNode.layout = layout;

		return flowData;

	}

	/**
	 * Executes the node in a specific build stage.
	 *
	 * @param {Node} node - The node to execute.
	 * @param {string} buildStage - The build stage to execute the node in.
	 * @param {Node|string|null} output - Expected output type. For example 'vec3'.
	 * @return {Node|string|null} The result of the node build.
	 */
	flowBuildStage( node, buildStage, output = null ) {

		const previousBuildStage = this.getBuildStage();

		this.setBuildStage( buildStage );

		const result = node.build( this, output );

		this.setBuildStage( previousBuildStage );

		return result;

	}

	/**
	 * Runs the node flow through all the steps of creation, 'setup', 'analyze', 'generate'.
	 *
	 * @param {Node} node - The node to execute.
	 * @param {?string} output - Expected output type. For example 'vec3'.
	 * @return {Object}
	 */
	flowStagesNode( node, output = null ) {

		const previousFlow = this.flow;
		const previousVars = this.vars;
		const previousDeclarations = this.declarations;
		const previousCache = this.cache;
		const previousBuildStage = this.buildStage;
		const previousStack = this.stack;

		const flow = {
			code: ''
		};

		this.flow = flow;
		this.vars = {};
		this.declarations = {};
		this.cache = new NodeCache();
		this.stack = stack();

		for ( const buildStage of defaultBuildStages ) {

			this.setBuildStage( buildStage );

			flow.result = node.build( this, output );

		}

		flow.vars = this.getVars( this.shaderStage );

		this.flow = previousFlow;
		this.vars = previousVars;
		this.declarations = previousDeclarations;
		this.cache = previousCache;
		this.stack = previousStack;

		this.setBuildStage( previousBuildStage );

		return flow;

	}

	/**
	 * Returns the native shader operator name for a given generic name.
	 * It is a similar type of method like {@link NodeBuilder#getMethod}.
	 *
	 * @abstract
	 * @param {string} op - The operator name to resolve.
	 * @return {?string} The resolved operator name.
	 */
	getFunctionOperator( /* op */ ) {

		return null;

	}

	/**
	 * Builds the given shader node.
	 *
	 * @abstract
	 * @param {ShaderNodeInternal} shaderNode - The shader node.
	 * @return {string} The function code.
	 */
	buildFunctionCode( /* shaderNode */ ) {

		console.warn( 'Abstract function.' );

	}

	/**
	 * Generates a code flow based on a child Node.
	 *
	 * @param {Node} node - The node to execute.
	 * @param {?string} output - Expected output type. For example 'vec3'.
	 * @return {Object} The code flow.
	 */
	flowChildNode( node, output = null ) {

		const previousFlow = this.flow;

		const flow = {
			code: ''
		};

		this.flow = flow;

		flow.result = node.build( this, output );

		this.flow = previousFlow;

		return flow;

	}

	/**
	 * Executes a flow of code in a different stage.
	 *
	 * Some nodes like `varying()` have the ability to compute code in vertex-stage and
	 * return the value in fragment-stage even if it is being executed in an input fragment.
	 *
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @param {Node} node - The node to execute.
	 * @param {?string} output - Expected output type. For example 'vec3'.
	 * @param {?string} propertyName - The property name to assign the result.
	 * @return {Object|Node|null} The code flow or node.build() result.
	 */
	flowNodeFromShaderStage( shaderStage, node, output = null, propertyName = null ) {

		const previousTab = this.tab;
		const previousCache = this.cache;
		const previousShaderStage = this.shaderStage;
		const previousContext = this.context;

		this.setShaderStage( shaderStage );

		const context = { ...this.context };
		delete context.nodeBlock;

		this.cache = this.globalCache;
		this.tab = '\t';
		this.context = context;

		let result = null;

		if ( this.buildStage === 'generate' ) {

			const flowData = this.flowChildNode( node, output );

			if ( propertyName !== null ) {

				flowData.code += `${ this.tab + propertyName } = ${ flowData.result };\n`;

			}

			this.flowCode[ shaderStage ] = this.flowCode[ shaderStage ] + flowData.code;

			result = flowData;

		} else {

			result = node.build( this );

		}

		this.setShaderStage( previousShaderStage );

		this.cache = previousCache;
		this.tab = previousTab;
		this.context = previousContext;

		return result;

	}

	/**
	 * Returns an array holding all node attributes of this node builder.
	 *
	 * @return {Array<NodeAttribute>} The node attributes of this builder.
	 */
	getAttributesArray() {

		return this.attributes.concat( this.bufferAttributes );

	}

	/**
	 * Returns the attribute definitions as a shader string for the given shader stage.
	 *
	 * @abstract
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @return {string} The attribute code section.
	 */
	getAttributes( /*shaderStage*/ ) {

		console.warn( 'Abstract function.' );

	}

	/**
	 * Returns the varying definitions as a shader string for the given shader stage.
	 *
	 * @abstract
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @return {string} The varying code section.
	 */
	getVaryings( /*shaderStage*/ ) {

		console.warn( 'Abstract function.' );

	}

	/**
	 * Returns a single variable definition as a shader string for the given variable type and name.
	 *
	 * @param {string} type - The variable's type.
	 * @param {string} name - The variable's name.
	 * @param {?number} [count=null] - The array length.
	 * @return {string} The shader string.
	 */
	getVar( type, name, count = null ) {

		return `${ count !== null ? this.generateArrayDeclaration( type, count ) : this.getType( type ) } ${ name }`;

	}

	/**
	 * Returns the variable definitions as a shader string for the given shader stage.
	 *
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @return {string} The variable code section.
	 */
	getVars( shaderStage ) {

		let snippet = '';

		const vars = this.vars[ shaderStage ];

		if ( vars !== undefined ) {

			for ( const variable of vars ) {

				snippet += `${ this.getVar( variable.type, variable.name ) }; `;

			}

		}

		return snippet;

	}

	/**
	 * Returns the uniform definitions as a shader string for the given shader stage.
	 *
	 * @abstract
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @return {string} The uniform code section.
	 */
	getUniforms( /*shaderStage*/ ) {

		console.warn( 'Abstract function.' );

	}

	/**
	 * Returns the native code definitions as a shader string for the given shader stage.
	 *
	 * @param {('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage.
	 * @return {string} The native code section.
	 */
	getCodes( shaderStage ) {

		const codes = this.codes[ shaderStage ];

		let code = '';

		if ( codes !== undefined ) {

			for ( const nodeCode of codes ) {

				code += nodeCode.code + '\n';

			}

		}

		return code;

	}

	/**
	 * Returns the hash of this node builder.
	 *
	 * @return {string} The hash.
	 */
	getHash() {

		return this.vertexShader + this.fragmentShader + this.computeShader;

	}

	/**
	 * Sets the current shader stage.
	 *
	 * @param {?('vertex'|'fragment'|'compute'|'any')} shaderStage - The shader stage to set.
	 */
	setShaderStage( shaderStage ) {

		this.shaderStage = shaderStage;

	}

	/**
	 * Returns the current shader stage.
	 *
	 * @return {?('vertex'|'fragment'|'compute'|'any')} The current shader stage.
	 */
	getShaderStage() {

		return this.shaderStage;

	}

	/**
	 * Sets the current build stage.
	 *
	 * @param {?('setup'|'analyze'|'generate')} buildStage - The build stage to set.
	 */
	setBuildStage( buildStage ) {

		this.buildStage = buildStage;

	}

	/**
	 * Returns the current build stage.
	 *
	 * @return {?('setup'|'analyze'|'generate')} The current build stage.
	 */
	getBuildStage() {

		return this.buildStage;

	}

	/**
	 * Controls the code build of the shader stages.
	 *
	 * @abstract
	 */
	buildCode() {

		console.warn( 'Abstract function.' );

	}

	/**
	 * Returns the current sub-build layer.
	 *
	 * @return {SubBuildNode} The current sub-build layers.
	 */
	get subBuild() {

		return this.subBuildLayers[ this.subBuildLayers.length - 1 ] || null;

	}

	/**
	 * Adds a sub-build layer to the node builder.
	 *
	 * @param {SubBuildNode} subBuild - The sub-build layer to add.
	 */
	addSubBuild( subBuild ) {

		this.subBuildLayers.push( subBuild );

	}

	/**
	 * Removes the last sub-build layer from the node builder.
	 *
	 * @return {SubBuildNode} The removed sub-build layer.
	 */
	removeSubBuild() {

		return this.subBuildLayers.pop();

	}

	/**
	 * Returns the closest sub-build layer for the given data.
	 *
	 * @param {Node|Set|Array} data - The data to get the closest sub-build layer from.
	 * @return {?string} The closest sub-build name or null if none found.
	 */
	getClosestSubBuild( data ) {

		let subBuilds;

		if ( data && data.isNode ) {

			if ( data.isShaderCallNodeInternal ) {

				subBuilds = data.shaderNode.subBuilds;

			} else if ( data.isStackNode ) {

				subBuilds = [ data.subBuild ];

			} else {

				subBuilds = this.getDataFromNode( data, 'any' ).subBuilds;

			}

		} else if ( data instanceof Set ) {

			subBuilds = [ ...data ];

		} else {

			subBuilds = data;

		}

		if ( ! subBuilds ) return null;

		const subBuildLayers = this.subBuildLayers;

		for ( let i = subBuilds.length - 1; i >= 0; i -- ) {

			const subBuild = subBuilds[ i ];

			if ( subBuildLayers.includes( subBuild ) ) {

				return subBuild;

			}

		}

		return null;

	}


	/**
	 * Returns the output node of a sub-build layer.
	 *
	 * @param {Node} node - The node to get the output from.
	 * @return {string} The output node name.
	 */
	getSubBuildOutput( node ) {

		return this.getSubBuildProperty( 'outputNode', node );

	}

	/**
	 * Returns the sub-build property name for the given property and node.
	 *
	 * @param {string} [property=''] - The property name.
	 * @param {?Node} [node=null] - The node to get the sub-build from.
	 * @return {string} The sub-build property name.
	 */
	getSubBuildProperty( property = '', node = null ) {

		let subBuild;

		if ( node !== null ) {

			subBuild = this.getClosestSubBuild( node );

		} else {

			subBuild = this.subBuildFn;

		}

		let result;

		if ( subBuild ) {

			result = property ? ( subBuild + '_' + property ) : subBuild;

		} else {

			result = property;

		}

		return result;

	}

	/**
	 * Central build method which controls the build for the given object.
	 *
	 * @return {NodeBuilder} A reference to this node builder.
	 */
	build() {

		const { object, material, renderer } = this;

		if ( material !== null ) {

			let nodeMaterial = renderer.library.fromMaterial( material );

			if ( nodeMaterial === null ) {

				console.error( `NodeMaterial: Material "${ material.type }" is not compatible.` );

				nodeMaterial = new NodeMaterial();

			}

			nodeMaterial.build( this );

		} else {

			this.addFlow( 'compute', object );

		}

		// setup() -> stage 1: create possible new nodes and/or return an output reference node
		// analyze()   -> stage 2: analyze nodes to possible optimization and validation
		// generate()  -> stage 3: generate shader

		for ( const buildStage of defaultBuildStages ) {

			this.setBuildStage( buildStage );

			if ( this.context.vertex && this.context.vertex.isNode ) {

				this.flowNodeFromShaderStage( 'vertex', this.context.vertex );

			}

			for ( const shaderStage of shaderStages ) {

				this.setShaderStage( shaderStage );

				const flowNodes = this.flowNodes[ shaderStage ];

				for ( const node of flowNodes ) {

					if ( buildStage === 'generate' ) {

						this.flowNode( node );

					} else {

						node.build( this );

					}

				}

			}

		}

		this.setBuildStage( null );
		this.setShaderStage( null );

		// stage 4: build code for a specific output

		this.buildCode();
		this.buildUpdateNodes();

		return this;

	}

	/**
	 * Returns a uniform representation which is later used for UBO generation and rendering.
	 *
	 * @param {NodeUniform} uniformNode - The uniform node.
	 * @param {string} type - The requested type.
	 * @return {Uniform} The uniform.
	 */
	getNodeUniform( uniformNode, type ) {

		if ( type === 'float' || type === 'int' || type === 'uint' ) return new NumberNodeUniform( uniformNode );
		if ( type === 'vec2' || type === 'ivec2' || type === 'uvec2' ) return new Vector2NodeUniform( uniformNode );
		if ( type === 'vec3' || type === 'ivec3' || type === 'uvec3' ) return new Vector3NodeUniform( uniformNode );
		if ( type === 'vec4' || type === 'ivec4' || type === 'uvec4' ) return new Vector4NodeUniform( uniformNode );
		if ( type === 'color' ) return new ColorNodeUniform( uniformNode );
		if ( type === 'mat2' ) return new Matrix2NodeUniform( uniformNode );
		if ( type === 'mat3' ) return new Matrix3NodeUniform( uniformNode );
		if ( type === 'mat4' ) return new Matrix4NodeUniform( uniformNode );

		throw new Error( `Uniform "${type}" not declared.` );

	}

	/**
	 * Formats the given shader snippet from a given type into another one. E.g.
	 * this method might be used to convert a simple float string `"1.0"` into a
	 * `vec3` representation: `"vec3<f32>( 1.0 )"`.
	 *
	 * @param {string} snippet - The shader snippet.
	 * @param {string} fromType - The source type.
	 * @param {string} toType - The target type.
	 * @return {string} The updated shader string.
	 */
	format( snippet, fromType, toType ) {

		fromType = this.getVectorType( fromType );
		toType = this.getVectorType( toType );

		if ( fromType === toType || toType === null || this.isReference( toType ) ) {

			return snippet;

		}

		const fromTypeLength = this.getTypeLength( fromType );
		const toTypeLength = this.getTypeLength( toType );

		if ( fromTypeLength === 16 && toTypeLength === 9 ) {

			return `${ this.getType( toType ) }( ${ snippet }[ 0 ].xyz, ${ snippet }[ 1 ].xyz, ${ snippet }[ 2 ].xyz )`;

		}

		if ( fromTypeLength === 9 && toTypeLength === 4 ) {

			return `${ this.getType( toType ) }( ${ snippet }[ 0 ].xy, ${ snippet }[ 1 ].xy )`;

		}


		if ( fromTypeLength > 4 ) { // fromType is matrix-like

			// @TODO: ignore for now

			return snippet;

		}

		if ( toTypeLength > 4 || toTypeLength === 0 ) { // toType is matrix-like or unknown

			// @TODO: ignore for now

			return snippet;

		}

		if ( fromTypeLength === toTypeLength ) {

			return `${ this.getType( toType ) }( ${ snippet } )`;

		}

		if ( fromTypeLength > toTypeLength ) {

			snippet = toType === 'bool' ? `all( ${ snippet } )` : `${ snippet }.${ 'xyz'.slice( 0, toTypeLength ) }`;

			return this.format( snippet, this.getTypeFromLength( toTypeLength, this.getComponentType( fromType ) ), toType );

		}

		if ( toTypeLength === 4 && fromTypeLength > 1 ) { // toType is vec4-like

			return `${ this.getType( toType ) }( ${ this.format( snippet, fromType, 'vec3' ) }, 1.0 )`;

		}

		if ( fromTypeLength === 2 ) { // fromType is vec2-like and toType is vec3-like

			return `${ this.getType( toType ) }( ${ this.format( snippet, fromType, 'vec2' ) }, 0.0 )`;

		}

		if ( fromTypeLength === 1 && toTypeLength > 1 && fromType !== this.getComponentType( toType ) ) { // fromType is float-like

			// convert a number value to vector type, e.g:
			// vec3( 1u ) -> vec3( float( 1u ) )

			snippet = `${ this.getType( this.getComponentType( toType ) ) }( ${ snippet } )`;

		}

		return `${ this.getType( toType ) }( ${ snippet } )`; // fromType is float-like

	}

	/**
	 * Returns a signature with the engine's current revision.
	 *
	 * @return {string} The signature.
	 */
	getSignature() {

		return `// Three.js r${ REVISION } - Node System\n`;

	}

}
```
</details>

#### Methods

##### `getBindGroupsCache(): ChainMap`

<details><summary>Code</summary>

```ts
getBindGroupsCache() {

		let bindGroupsCache = rendererCache.get( this.renderer );

		if ( bindGroupsCache === undefined ) {

			bindGroupsCache = new ChainMap();

			rendererCache.set( this.renderer, bindGroupsCache );

		}

		return bindGroupsCache;

	}
```
</details>

##### `createRenderTarget(width: number, height: number, options: any): RenderTarget`

<details><summary>Code</summary>

```ts
createRenderTarget( width, height, options ) {

		return new RenderTarget( width, height, options );

	}
```
</details>

##### `createCubeRenderTarget(size: number, options: any): CubeRenderTarget`

<details><summary>Code</summary>

```ts
createCubeRenderTarget( size, options ) {

		return new CubeRenderTarget( size, options );

	}
```
</details>

##### `includes(node: Node): boolean`

<details><summary>Code</summary>

```ts
includes( node ) {

		return this.nodes.includes( node );

	}
```
</details>

##### `getOutputStructName(): string`

<details><summary>Code</summary>

```ts
getOutputStructName() {}
```
</details>

##### `_getBindGroup(groupName: string, bindings: NodeUniformsGroup[]): BindGroup`

<details><summary>Code</summary>

```ts
_getBindGroup( groupName, bindings ) {

		const bindGroupsCache = this.getBindGroupsCache();

		//

		const bindingsArray = [];

		let sharedGroup = true;

		for ( const binding of bindings ) {

			bindingsArray.push( binding );

			sharedGroup = sharedGroup && binding.groupNode.shared !== true;

		}

		//

		let bindGroup;

		if ( sharedGroup ) {

			bindGroup = bindGroupsCache.get( bindingsArray );

			if ( bindGroup === undefined ) {

				bindGroup = new BindGroup( groupName, bindingsArray, this.bindingsIndexes[ groupName ].group, bindingsArray );

				bindGroupsCache.set( bindingsArray, bindGroup );

			}

		} else {

			bindGroup = new BindGroup( groupName, bindingsArray, this.bindingsIndexes[ groupName ].group, bindingsArray );

		}

		return bindGroup;

	}
```
</details>

##### `getBindGroupArray(groupName: string, shaderStage: "compute" | "vertex" | "fragment" | "any"): NodeUniformsGroup[]`

<details><summary>Code</summary>

```ts
getBindGroupArray( groupName, shaderStage ) {

		const bindings = this.bindings[ shaderStage ];

		let bindGroup = bindings[ groupName ];

		if ( bindGroup === undefined ) {

			if ( this.bindingsIndexes[ groupName ] === undefined ) {

				this.bindingsIndexes[ groupName ] = { binding: 0, group: Object.keys( this.bindingsIndexes ).length };

			}

			bindings[ groupName ] = bindGroup = [];

		}

		return bindGroup;

	}
```
</details>

##### `getBindings(): BindGroup[]`

<details><summary>Code</summary>

```ts
getBindings() {

		let bindingsGroups = this.bindGroups;

		if ( bindingsGroups === null ) {

			const groups = {};
			const bindings = this.bindings;

			for ( const shaderStage of shaderStages ) {

				for ( const groupName in bindings[ shaderStage ] ) {

					const uniforms = bindings[ shaderStage ][ groupName ];

					const groupUniforms = groups[ groupName ] || ( groups[ groupName ] = [] );
					groupUniforms.push( ...uniforms );

				}

			}

			bindingsGroups = [];

			for ( const groupName in groups ) {

				const group = groups[ groupName ];

				const bindingsGroup = this._getBindGroup( groupName, group );

				bindingsGroups.push( bindingsGroup );

			}

			this.bindGroups = bindingsGroups;

		}

		return bindingsGroups;

	}
```
</details>

##### `sortBindingGroups(): void`

<details><summary>Code</summary>

```ts
sortBindingGroups() {

		const bindingsGroups = this.getBindings();

		bindingsGroups.sort( ( a, b ) => ( a.bindings[ 0 ].groupNode.order - b.bindings[ 0 ].groupNode.order ) );

		for ( let i = 0; i < bindingsGroups.length; i ++ ) {

			const bindingGroup = bindingsGroups[ i ];
			this.bindingsIndexes[ bindingGroup.name ].group = i;

			bindingGroup.index = i;

		}

	}
```
</details>

##### `setHashNode(node: Node, hash: number): void`

<details><summary>Code</summary>

```ts
setHashNode( node, hash ) {

		this.hashNodes[ hash ] = node;

	}
```
</details>

##### `addNode(node: Node): void`

<details><summary>Code</summary>

```ts
addNode( node ) {

		if ( this.nodes.includes( node ) === false ) {

			this.nodes.push( node );

			this.setHashNode( node, node.getHash( this ) );

		}

	}
```
</details>

##### `addSequentialNode(node: Node): void`

<details><summary>Code</summary>

```ts
addSequentialNode( node ) {

		if ( this.sequentialNodes.includes( node ) === false ) {

			this.sequentialNodes.push( node );

		}

	}
```
</details>

##### `buildUpdateNodes(): void`

<details><summary>Code</summary>

```ts
buildUpdateNodes() {

		for ( const node of this.nodes ) {

			const updateType = node.getUpdateType();

			if ( updateType !== NodeUpdateType.NONE ) {

				this.updateNodes.push( node.getSelf() );

			}

		}

		for ( const node of this.sequentialNodes ) {

			const updateBeforeType = node.getUpdateBeforeType();
			const updateAfterType = node.getUpdateAfterType();

			if ( updateBeforeType !== NodeUpdateType.NONE ) {

				this.updateBeforeNodes.push( node.getSelf() );

			}

			if ( updateAfterType !== NodeUpdateType.NONE ) {

				this.updateAfterNodes.push( node.getSelf() );

			}

		}

	}
```
</details>

##### `isFilteredTexture(texture: Texture): boolean`

<details><summary>Code</summary>

```ts
isFilteredTexture( texture ) {

		return ( texture.magFilter === LinearFilter || texture.magFilter === LinearMipmapNearestFilter || texture.magFilter === NearestMipmapLinearFilter || texture.magFilter === LinearMipmapLinearFilter ||
			texture.minFilter === LinearFilter || texture.minFilter === LinearMipmapNearestFilter || texture.minFilter === NearestMipmapLinearFilter || texture.minFilter === LinearMipmapLinearFilter );

	}
```
</details>

##### `addChain(node: Node): void`

<details><summary>Code</summary>

```ts
addChain( node ) {

		/*
		if ( this.chaining.indexOf( node ) !== - 1 ) {

			console.warn( 'Recursive node: ', node );

		}
		*/

		this.chaining.push( node );

	}
```
</details>

##### `removeChain(node: Node): void`

<details><summary>Code</summary>

```ts
removeChain( node ) {

		const lastChain = this.chaining.pop();

		if ( lastChain !== node ) {

			throw new Error( 'NodeBuilder: Invalid node chaining!' );

		}

	}
```
</details>

##### `getMethod(method: string): string`

<details><summary>Code</summary>

```ts
getMethod( method ) {

		return method;

	}
```
</details>

##### `getTernary(): string`

<details><summary>Code</summary>

```ts
getTernary( /* condSnippet, ifSnippet, elseSnippet*/ ) {

		return null;

	}
```
</details>

##### `getNodeFromHash(hash: number): Node`

<details><summary>Code</summary>

```ts
getNodeFromHash( hash ) {

		return this.hashNodes[ hash ];

	}
```
</details>

##### `addFlow(shaderStage: "compute" | "vertex" | "fragment", node: Node): Node`

<details><summary>Code</summary>

```ts
addFlow( shaderStage, node ) {

		this.flowNodes[ shaderStage ].push( node );

		return node;

	}
```
</details>

##### `setContext(context: any): void`

<details><summary>Code</summary>

```ts
setContext( context ) {

		this.context = context;

	}
```
</details>

##### `getContext(): any`

<details><summary>Code</summary>

```ts
getContext() {

		return this.context;

	}
```
</details>

##### `getSharedContext(): any`

<details><summary>Code</summary>

```ts
getSharedContext() {

		const context = { ...this.context };

		delete context.material;

		return this.context;

	}
```
</details>

##### `setCache(cache: NodeCache): void`

<details><summary>Code</summary>

```ts
setCache( cache ) {

		this.cache = cache;

	}
```
</details>

##### `getCache(): NodeCache`

<details><summary>Code</summary>

```ts
getCache() {

		return this.cache;

	}
```
</details>

##### `getCacheFromNode(node: Node, parent: boolean): NodeCache`

<details><summary>Code</summary>

```ts
getCacheFromNode( node, parent = true ) {

		const data = this.getDataFromNode( node );
		if ( data.cache === undefined ) data.cache = new NodeCache( parent ? this.getCache() : null );

		return data.cache;

	}
```
</details>

##### `isAvailable(): boolean`

<details><summary>Code</summary>

```ts
isAvailable( /*name*/ ) {

		return false;

	}
```
</details>

##### `getVertexIndex(): string`

<details><summary>Code</summary>

```ts
getVertexIndex() {

		console.warn( 'Abstract function.' );

	}
```
</details>

##### `getInstanceIndex(): string`

<details><summary>Code</summary>

```ts
getInstanceIndex() {

		console.warn( 'Abstract function.' );

	}
```
</details>

##### `getDrawIndex(): string`

<details><summary>Code</summary>

```ts
getDrawIndex() {

		console.warn( 'Abstract function.' );

	}
```
</details>

##### `getFrontFacing(): string`

<details><summary>Code</summary>

```ts
getFrontFacing() {

		console.warn( 'Abstract function.' );

	}
```
</details>

##### `getFragCoord(): string`

<details><summary>Code</summary>

```ts
getFragCoord() {

		console.warn( 'Abstract function.' );

	}
```
</details>

##### `isFlipY(): boolean`

<details><summary>Code</summary>

```ts
isFlipY() {

		return false;

	}
```
</details>

##### `increaseUsage(node: Node): number`

<details><summary>Code</summary>

```ts
increaseUsage( node ) {

		const nodeData = this.getDataFromNode( node );
		nodeData.usageCount = nodeData.usageCount === undefined ? 1 : nodeData.usageCount + 1;

		return nodeData.usageCount;

	}
```
</details>

##### `generateTexture(): string`

<details><summary>Code</summary>

```ts
generateTexture( /* texture, textureProperty, uvSnippet */ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

##### `generateTextureLod(): string`

<details><summary>Code</summary>

```ts
generateTextureLod( /* texture, textureProperty, uvSnippet, depthSnippet, levelSnippet */ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

##### `generateArrayDeclaration(type: string, count: number): string`

<details><summary>Code</summary>

```ts
generateArrayDeclaration( type, count ) {

		return this.getType( type ) + '[ ' + count + ' ]';

	}
```
</details>

##### `generateArray(type: string, count: number, values: Node[]): string`

<details><summary>Code</summary>

```ts
generateArray( type, count, values = null ) {

		let snippet = this.generateArrayDeclaration( type, count ) + '( ';

		for ( let i = 0; i < count; i ++ ) {

			const value = values ? values[ i ] : null;

			if ( value !== null ) {

				snippet += value.build( this, type );

			} else {

				snippet += this.generateConst( type );

			}

			if ( i < count - 1 ) snippet += ', ';

		}

		snippet += ' )';

		return snippet;

	}
```
</details>

##### `generateStruct(type: string, membersLayout: any[], values: Node[]): string`

<details><summary>Code</summary>

```ts
generateStruct( type, membersLayout, values = null ) {

		const snippets = [];

		for ( const member of membersLayout ) {

			const { name, type } = member;

			if ( values && values[ name ] && values[ name ].isNode ) {

				snippets.push( values[ name ].build( this, type ) );

			} else {

				snippets.push( this.generateConst( type ) );

			}

		}

		return type + '( ' + snippets.join( ', ' ) + ' )';

	}
```
</details>

##### `generateConst(type: string, value: any): string`

<details><summary>Code</summary>

```ts
generateConst( type, value = null ) {

		if ( value === null ) {

			if ( type === 'float' || type === 'int' || type === 'uint' ) value = 0;
			else if ( type === 'bool' ) value = false;
			else if ( type === 'color' ) value = new Color();
			else if ( type === 'vec2' ) value = new Vector2();
			else if ( type === 'vec3' ) value = new Vector3();
			else if ( type === 'vec4' ) value = new Vector4();

		}

		if ( type === 'float' ) return toFloat( value );
		if ( type === 'int' ) return `${ Math.round( value ) }`;
		if ( type === 'uint' ) return value >= 0 ? `${ Math.round( value ) }u` : '0u';
		if ( type === 'bool' ) return value ? 'true' : 'false';
		if ( type === 'color' ) return `${ this.getType( 'vec3' ) }( ${ toFloat( value.r ) }, ${ toFloat( value.g ) }, ${ toFloat( value.b ) } )`;

		const typeLength = this.getTypeLength( type );

		const componentType = this.getComponentType( type );

		const generateConst = value => this.generateConst( componentType, value );

		if ( typeLength === 2 ) {

			return `${ this.getType( type ) }( ${ generateConst( value.x ) }, ${ generateConst( value.y ) } )`;

		} else if ( typeLength === 3 ) {

			return `${ this.getType( type ) }( ${ generateConst( value.x ) }, ${ generateConst( value.y ) }, ${ generateConst( value.z ) } )`;

		} else if ( typeLength === 4 && type !== 'mat2' ) {

			return `${ this.getType( type ) }( ${ generateConst( value.x ) }, ${ generateConst( value.y ) }, ${ generateConst( value.z ) }, ${ generateConst( value.w ) } )`;

		} else if ( typeLength >= 4 && value && ( value.isMatrix2 || value.isMatrix3 || value.isMatrix4 ) ) {

			return `${ this.getType( type ) }( ${ value.elements.map( generateConst ).join( ', ' ) } )`;

		} else if ( typeLength > 4 ) {

			return `${ this.getType( type ) }()`;

		}

		throw new Error( `NodeBuilder: Type '${type}' not found in generate constant attempt.` );

	}
```
</details>

##### `getType(type: string): string`

<details><summary>Code</summary>

```ts
getType( type ) {

		if ( type === 'color' ) return 'vec3';

		return type;

	}
```
</details>

##### `hasGeometryAttribute(name: string): boolean`

<details><summary>Code</summary>

```ts
hasGeometryAttribute( name ) {

		return this.geometry && this.geometry.getAttribute( name ) !== undefined;

	}
```
</details>

##### `getAttribute(name: string, type: string): NodeAttribute`

<details><summary>Code</summary>

```ts
getAttribute( name, type ) {

		const attributes = this.attributes;

		// find attribute

		for ( const attribute of attributes ) {

			if ( attribute.name === name ) {

				return attribute;

			}

		}

		// create a new if no exist

		const attribute = new NodeAttribute( name, type );

		this.registerDeclaration( attribute );

		attributes.push( attribute );

		return attribute;

	}
```
</details>

##### `getPropertyName(node: Node): string`

<details><summary>Code</summary>

```ts
getPropertyName( node/*, shaderStage*/ ) {

		return node.name;

	}
```
</details>

##### `isVector(type: string): boolean`

<details><summary>Code</summary>

```ts
isVector( type ) {

		return /vec\d/.test( type );

	}
```
</details>

##### `isMatrix(type: string): boolean`

<details><summary>Code</summary>

```ts
isMatrix( type ) {

		return /mat\d/.test( type );

	}
```
</details>

##### `isReference(type: string): boolean`

<details><summary>Code</summary>

```ts
isReference( type ) {

		return type === 'void' || type === 'property' || type === 'sampler' || type === 'samplerComparison' || type === 'texture' || type === 'cubeTexture' || type === 'storageTexture' || type === 'depthTexture' || type === 'texture3D';

	}
```
</details>

##### `needsToWorkingColorSpace(): boolean`

<details><summary>Code</summary>

```ts
needsToWorkingColorSpace( /*texture*/ ) {

		return false;

	}
```
</details>

##### `getComponentTypeFromTexture(texture: Texture): string`

<details><summary>Code</summary>

```ts
getComponentTypeFromTexture( texture ) {

		const type = texture.type;

		if ( texture.isDataTexture ) {

			if ( type === IntType ) return 'int';
			if ( type === UnsignedIntType ) return 'uint';

		}

		return 'float';

	}
```
</details>

##### `getElementType(type: string): string`

<details><summary>Code</summary>

```ts
getElementType( type ) {

		if ( type === 'mat2' ) return 'vec2';
		if ( type === 'mat3' ) return 'vec3';
		if ( type === 'mat4' ) return 'vec4';

		return this.getComponentType( type );

	}
```
</details>

##### `getComponentType(type: string): string`

<details><summary>Code</summary>

```ts
getComponentType( type ) {

		type = this.getVectorType( type );

		if ( type === 'float' || type === 'bool' || type === 'int' || type === 'uint' ) return type;

		const componentType = /(b|i|u|)(vec|mat)([2-4])/.exec( type );

		if ( componentType === null ) return null;

		if ( componentType[ 1 ] === 'b' ) return 'bool';
		if ( componentType[ 1 ] === 'i' ) return 'int';
		if ( componentType[ 1 ] === 'u' ) return 'uint';

		return 'float';

	}
```
</details>

##### `getVectorType(type: string): string`

<details><summary>Code</summary>

```ts
getVectorType( type ) {

		if ( type === 'color' ) return 'vec3';
		if ( type === 'texture' || type === 'cubeTexture' || type === 'storageTexture' || type === 'texture3D' ) return 'vec4';

		return type;

	}
```
</details>

##### `getTypeFromLength(length: number, componentType: string): string`

<details><summary>Code</summary>

```ts
getTypeFromLength( length, componentType = 'float' ) {

		if ( length === 1 ) return componentType;

		let baseType = getTypeFromLength( length );
		const prefix = componentType === 'float' ? '' : componentType[ 0 ];

		// fix edge case for mat2x2 being same size as vec4
		if ( /mat2/.test( componentType ) === true ) {

			baseType = baseType.replace( 'vec', 'mat' );

		}

		return prefix + baseType;

	}
```
</details>

##### `getTypeFromArray(array: TypedArray): string`

<details><summary>Code</summary>

```ts
getTypeFromArray( array ) {

		return typeFromArray.get( array.constructor );

	}
```
</details>

##### `isInteger(type: string): boolean`

<details><summary>Code</summary>

```ts
isInteger( type ) {

		return /int|uint|(i|u)vec/.test( type );

	}
```
</details>

##### `getTypeFromAttribute(attribute: BufferAttribute): string`

<details><summary>Code</summary>

```ts
getTypeFromAttribute( attribute ) {

		let dataAttribute = attribute;

		if ( attribute.isInterleavedBufferAttribute ) dataAttribute = attribute.data;

		const array = dataAttribute.array;
		const itemSize = attribute.itemSize;
		const normalized = attribute.normalized;

		let arrayType;

		if ( ! ( attribute instanceof Float16BufferAttribute ) && normalized !== true ) {

			arrayType = this.getTypeFromArray( array );

		}

		return this.getTypeFromLength( itemSize, arrayType );

	}
```
</details>

##### `getTypeLength(type: string): number`

<details><summary>Code</summary>

```ts
getTypeLength( type ) {

		const vecType = this.getVectorType( type );
		const vecNum = /vec([2-4])/.exec( vecType );

		if ( vecNum !== null ) return Number( vecNum[ 1 ] );
		if ( vecType === 'float' || vecType === 'bool' || vecType === 'int' || vecType === 'uint' ) return 1;
		if ( /mat2/.test( type ) === true ) return 4;
		if ( /mat3/.test( type ) === true ) return 9;
		if ( /mat4/.test( type ) === true ) return 16;

		return 0;

	}
```
</details>

##### `getVectorFromMatrix(type: string): string`

<details><summary>Code</summary>

```ts
getVectorFromMatrix( type ) {

		return type.replace( 'mat', 'vec' );

	}
```
</details>

##### `changeComponentType(type: string, newComponentType: string): string`

<details><summary>Code</summary>

```ts
changeComponentType( type, newComponentType ) {

		return this.getTypeFromLength( this.getTypeLength( type ), newComponentType );

	}
```
</details>

##### `getIntegerType(type: string): string`

<details><summary>Code</summary>

```ts
getIntegerType( type ) {

		const componentType = this.getComponentType( type );

		if ( componentType === 'int' || componentType === 'uint' ) return type;

		return this.changeComponentType( type, 'int' );

	}
```
</details>

##### `addStack(): StackNode`

<details><summary>Code</summary>

```ts
addStack() {

		this.stack = stack( this.stack );

		this.stacks.push( getCurrentStack() || this.stack );
		setCurrentStack( this.stack );

		return this.stack;

	}
```
</details>

##### `removeStack(): StackNode`

<details><summary>Code</summary>

```ts
removeStack() {

		const lastStack = this.stack;
		this.stack = lastStack.parent;

		setCurrentStack( this.stacks.pop() );

		return lastStack;

	}
```
</details>

##### `getDataFromNode(node: Node, shaderStage: "compute" | "vertex" | "fragment" | "any", cache: NodeCache): any`

<details><summary>Code</summary>

```ts
getDataFromNode( node, shaderStage = this.shaderStage, cache = null ) {

		cache = cache === null ? ( node.isGlobal( this ) ? this.globalCache : this.cache ) : cache;

		let nodeData = cache.getData( node );

		if ( nodeData === undefined ) {

			nodeData = {};

			cache.setData( node, nodeData );

		}

		if ( nodeData[ shaderStage ] === undefined ) nodeData[ shaderStage ] = {};

		//

		let data = nodeData[ shaderStage ];

		const subBuilds = nodeData.any ? nodeData.any.subBuilds : null;
		const subBuild = this.getClosestSubBuild( subBuilds );

		if ( subBuild ) {

			if ( data.subBuildsCache === undefined ) data.subBuildsCache = {};

			data = data.subBuildsCache[ subBuild ] || ( data.subBuildsCache[ subBuild ] = {} );
			data.subBuilds = subBuilds;

		}

		return data;

	}
```
</details>

##### `getNodeProperties(node: Node, shaderStage: "compute" | "vertex" | "fragment" | "any"): any`

<details><summary>Code</summary>

```ts
getNodeProperties( node, shaderStage = 'any' ) {

		const nodeData = this.getDataFromNode( node, shaderStage );

		return nodeData.properties || ( nodeData.properties = { outputNode: null } );

	}
```
</details>

##### `getBufferAttributeFromNode(node: BufferAttributeNode, type: string): NodeAttribute`

<details><summary>Code</summary>

```ts
getBufferAttributeFromNode( node, type ) {

		const nodeData = this.getDataFromNode( node );

		let bufferAttribute = nodeData.bufferAttribute;

		if ( bufferAttribute === undefined ) {

			const index = this.uniforms.index ++;

			bufferAttribute = new NodeAttribute( 'nodeAttribute' + index, type, node );

			this.bufferAttributes.push( bufferAttribute );

			nodeData.bufferAttribute = bufferAttribute;

		}

		return bufferAttribute;

	}
```
</details>

##### `getStructTypeFromNode(node: OutputStructNode, membersLayout: any[], name: string, shaderStage: "compute" | "vertex" | "fragment" | "any"): StructType`

<details><summary>Code</summary>

```ts
getStructTypeFromNode( node, membersLayout, name = null, shaderStage = this.shaderStage ) {

		const nodeData = this.getDataFromNode( node, shaderStage, this.globalCache );

		let structType = nodeData.structType;

		if ( structType === undefined ) {

			const index = this.structs.index ++;

			if ( name === null ) name = 'StructType' + index;

			structType = new StructType( name, membersLayout );

			this.structs[ shaderStage ].push( structType );

			nodeData.structType = structType;

		}

		return structType;

	}
```
</details>

##### `getOutputStructTypeFromNode(node: OutputStructNode, membersLayout: any[]): StructType`

<details><summary>Code</summary>

```ts
getOutputStructTypeFromNode( node, membersLayout ) {

		const structType = this.getStructTypeFromNode( node, membersLayout, 'OutputType', 'fragment' );
		structType.output = true;

		return structType;

	}
```
</details>

##### `getUniformFromNode(node: UniformNode, type: string, shaderStage: "compute" | "vertex" | "fragment" | "any", name: string): NodeUniform`

<details><summary>Code</summary>

```ts
getUniformFromNode( node, type, shaderStage = this.shaderStage, name = null ) {

		const nodeData = this.getDataFromNode( node, shaderStage, this.globalCache );

		let nodeUniform = nodeData.uniform;

		if ( nodeUniform === undefined ) {

			const index = this.uniforms.index ++;

			nodeUniform = new NodeUniform( name || ( 'nodeUniform' + index ), type, node );

			this.uniforms[ shaderStage ].push( nodeUniform );

			this.registerDeclaration( nodeUniform );

			nodeData.uniform = nodeUniform;

		}

		return nodeUniform;

	}
```
</details>

##### `getVarFromNode(node: VarNode, name: string, type: string, shaderStage: "compute" | "vertex" | "fragment" | "any", readOnly: boolean): NodeVar`

<details><summary>Code</summary>

```ts
getVarFromNode( node, name = null, type = node.getNodeType( this ), shaderStage = this.shaderStage, readOnly = false ) {

		const nodeData = this.getDataFromNode( node, shaderStage );
		const subBuildVariable = this.getSubBuildProperty( 'variable', nodeData.subBuilds );

		let nodeVar = nodeData[ subBuildVariable ];

		if ( nodeVar === undefined ) {

			const idNS = readOnly ? '_const' : '_var';

			const vars = this.vars[ shaderStage ] || ( this.vars[ shaderStage ] = [] );
			const id = this.vars[ idNS ] || ( this.vars[ idNS ] = 0 );

			if ( name === null ) {

				name = ( readOnly ? 'nodeConst' : 'nodeVar' ) + id;

				this.vars[ idNS ] ++;

			}

			//

			if ( subBuildVariable !== 'variable' ) {

				name = this.getSubBuildProperty( name, nodeData.subBuilds );

			}

			//

			const count = node.getArrayCount( this );

			nodeVar = new NodeVar( name, type, readOnly, count );

			if ( ! readOnly ) {

				vars.push( nodeVar );

			}

			this.registerDeclaration( nodeVar );

			nodeData[ subBuildVariable ] = nodeVar;

		}

		return nodeVar;

	}
```
</details>

##### `isDeterministic(node: Node): boolean`

<details><summary>Code</summary>

```ts
isDeterministic( node ) {

		if ( node.isMathNode ) {

			return this.isDeterministic( node.aNode ) &&
				( node.bNode ? this.isDeterministic( node.bNode ) : true ) &&
				( node.cNode ? this.isDeterministic( node.cNode ) : true );

		} else if ( node.isOperatorNode ) {

			return this.isDeterministic( node.aNode ) &&
				( node.bNode ? this.isDeterministic( node.bNode ) : true );

		} else if ( node.isArrayNode ) {

			if ( node.values !== null ) {

				for ( const n of node.values ) {

					if ( ! this.isDeterministic( n ) ) {

						return false;

					}

				}

			}

			return true;

		} else if ( node.isConstNode ) {

			return true;

		}

		return false;

	}
```
</details>

##### `getVaryingFromNode(node: any, name: string, type: string, interpolationType: string, interpolationSampling: string): NodeVar`

<details><summary>Code</summary>

```ts
getVaryingFromNode( node, name = null, type = node.getNodeType( this ), interpolationType = null, interpolationSampling = null ) {

		const nodeData = this.getDataFromNode( node, 'any' );
		const subBuildVarying = this.getSubBuildProperty( 'varying', nodeData.subBuilds );

		let nodeVarying = nodeData[ subBuildVarying ];

		if ( nodeVarying === undefined ) {

			const varyings = this.varyings;
			const index = varyings.length;

			if ( name === null ) name = 'nodeVarying' + index;

			//

			if ( subBuildVarying !== 'varying' ) {

				name = this.getSubBuildProperty( name, nodeData.subBuilds );

			}

			//

			nodeVarying = new NodeVarying( name, type, interpolationType, interpolationSampling );

			varyings.push( nodeVarying );

			this.registerDeclaration( nodeVarying );

			nodeData[ subBuildVarying ] = nodeVarying;

		}

		return nodeVarying;

	}
```
</details>

##### `registerDeclaration(node: any): void`

<details><summary>Code</summary>

```ts
registerDeclaration( node ) {

		const shaderStage = this.shaderStage;
		const declarations = this.declarations[ shaderStage ] || ( this.declarations[ shaderStage ] = {} );

		const property = this.getPropertyName( node );

		let index = 1;
		let name = property;

		// Automatically renames the property if the name is already in use.

		while ( declarations[ name ] !== undefined ) {

			name = property + '_' + index ++;

		}

		if ( index > 1 ) {

			node.name = name;

			console.warn( `THREE.TSL: Declaration name '${ property }' of '${ node.type }' already in use. Renamed to '${ name }'.` );

		}

		declarations[ name ] = node;

	}
```
</details>

##### `getCodeFromNode(node: CodeNode, type: string, shaderStage: "compute" | "vertex" | "fragment" | "any"): NodeCode`

<details><summary>Code</summary>

```ts
getCodeFromNode( node, type, shaderStage = this.shaderStage ) {

		const nodeData = this.getDataFromNode( node );

		let nodeCode = nodeData.code;

		if ( nodeCode === undefined ) {

			const codes = this.codes[ shaderStage ] || ( this.codes[ shaderStage ] = [] );
			const index = codes.length;

			nodeCode = new NodeCode( 'nodeCode' + index, type );

			codes.push( nodeCode );

			nodeData.code = nodeCode;

		}

		return nodeCode;

	}
```
</details>

##### `addFlowCodeHierarchy(node: Node, nodeBlock: Node): void`

<details><summary>Code</summary>

```ts
addFlowCodeHierarchy( node, nodeBlock ) {

		const { flowCodes, flowCodeBlock } = this.getDataFromNode( node );

		let needsFlowCode = true;
		let nodeBlockHierarchy = nodeBlock;

		while ( nodeBlockHierarchy ) {

			if ( flowCodeBlock.get( nodeBlockHierarchy ) === true ) {

				needsFlowCode = false;
				break;

			}

			nodeBlockHierarchy = this.getDataFromNode( nodeBlockHierarchy ).parentNodeBlock;

		}

		if ( needsFlowCode ) {

			for ( const flowCode of flowCodes ) {

				this.addLineFlowCode( flowCode );

			}

		}

	}
```
</details>

##### `addLineFlowCodeBlock(node: Node, code: string, nodeBlock: Node): void`

<details><summary>Code</summary>

```ts
addLineFlowCodeBlock( node, code, nodeBlock ) {

		const nodeData = this.getDataFromNode( node );
		const flowCodes = nodeData.flowCodes || ( nodeData.flowCodes = [] );
		const codeBlock = nodeData.flowCodeBlock || ( nodeData.flowCodeBlock = new WeakMap() );

		flowCodes.push( code );
		codeBlock.set( nodeBlock, true );

	}
```
</details>

##### `addLineFlowCode(code: string, node: Node): NodeBuilder`

<details><summary>Code</summary>

```ts
addLineFlowCode( code, node = null ) {

		if ( code === '' ) return this;

		if ( node !== null && this.context.nodeBlock ) {

			this.addLineFlowCodeBlock( node, code, this.context.nodeBlock );

		}

		code = this.tab + code;

		if ( ! /;\s*$/.test( code ) ) {

			code = code + ';\n';

		}

		this.flow.code += code;

		return this;

	}
```
</details>

##### `addFlowCode(code: string): NodeBuilder`

<details><summary>Code</summary>

```ts
addFlowCode( code ) {

		this.flow.code += code;

		return this;

	}
```
</details>

##### `addFlowTab(): NodeBuilder`

<details><summary>Code</summary>

```ts
addFlowTab() {

		this.tab += '\t';

		return this;

	}
```
</details>

##### `removeFlowTab(): NodeBuilder`

<details><summary>Code</summary>

```ts
removeFlowTab() {

		this.tab = this.tab.slice( 0, - 1 );

		return this;

	}
```
</details>

##### `getFlowData(node: Node): any`

<details><summary>Code</summary>

```ts
getFlowData( node/*, shaderStage*/ ) {

		return this.flowsData.get( node );

	}
```
</details>

##### `flowNode(node: Node): any`

<details><summary>Code</summary>

```ts
flowNode( node ) {

		const output = node.getNodeType( this );

		const flowData = this.flowChildNode( node, output );

		this.flowsData.set( node, flowData );

		return flowData;

	}
```
</details>

##### `addInclude(node: Node): void`

<details><summary>Code</summary>

```ts
addInclude( node ) {

		if ( this.currentFunctionNode !== null ) {

			this.currentFunctionNode.includes.push( node );

		}

	}
```
</details>

##### `buildFunctionNode(shaderNode: ShaderNodeInternal): FunctionNode`

<details><summary>Code</summary>

```ts
buildFunctionNode( shaderNode ) {

		const fn = new FunctionNode();

		const previous = this.currentFunctionNode;

		this.currentFunctionNode = fn;

		fn.code = this.buildFunctionCode( shaderNode );

		this.currentFunctionNode = previous;

		return fn;

	}
```
</details>

##### `flowShaderNode(shaderNode: ShaderNodeInternal): any`

<details><summary>Code</summary>

```ts
flowShaderNode( shaderNode ) {

		const layout = shaderNode.layout;

		const inputs = {
			[ Symbol.iterator ]() {

				let index = 0;
				const values = Object.values( this );
				return {
					next: () => ( {
						value: values[ index ],
						done: index ++ >= values.length
					} )
				};

			}
		};

		for ( const input of layout.inputs ) {

			inputs[ input.name ] = new ParameterNode( input.type, input.name );

		}

		//

		shaderNode.layout = null;

		const callNode = shaderNode.call( inputs );
		const flowData = this.flowStagesNode( callNode, layout.type );

		shaderNode.layout = layout;

		return flowData;

	}
```
</details>

##### `flowBuildStage(node: Node, buildStage: string, output: string | Node): string | Node`

<details><summary>Code</summary>

```ts
flowBuildStage( node, buildStage, output = null ) {

		const previousBuildStage = this.getBuildStage();

		this.setBuildStage( buildStage );

		const result = node.build( this, output );

		this.setBuildStage( previousBuildStage );

		return result;

	}
```
</details>

##### `flowStagesNode(node: Node, output: string): any`

<details><summary>Code</summary>

```ts
flowStagesNode( node, output = null ) {

		const previousFlow = this.flow;
		const previousVars = this.vars;
		const previousDeclarations = this.declarations;
		const previousCache = this.cache;
		const previousBuildStage = this.buildStage;
		const previousStack = this.stack;

		const flow = {
			code: ''
		};

		this.flow = flow;
		this.vars = {};
		this.declarations = {};
		this.cache = new NodeCache();
		this.stack = stack();

		for ( const buildStage of defaultBuildStages ) {

			this.setBuildStage( buildStage );

			flow.result = node.build( this, output );

		}

		flow.vars = this.getVars( this.shaderStage );

		this.flow = previousFlow;
		this.vars = previousVars;
		this.declarations = previousDeclarations;
		this.cache = previousCache;
		this.stack = previousStack;

		this.setBuildStage( previousBuildStage );

		return flow;

	}
```
</details>

##### `getFunctionOperator(): string`

<details><summary>Code</summary>

```ts
getFunctionOperator( /* op */ ) {

		return null;

	}
```
</details>

##### `buildFunctionCode(): string`

<details><summary>Code</summary>

```ts
buildFunctionCode( /* shaderNode */ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

##### `flowChildNode(node: Node, output: string): any`

<details><summary>Code</summary>

```ts
flowChildNode( node, output = null ) {

		const previousFlow = this.flow;

		const flow = {
			code: ''
		};

		this.flow = flow;

		flow.result = node.build( this, output );

		this.flow = previousFlow;

		return flow;

	}
```
</details>

##### `flowNodeFromShaderStage(shaderStage: "compute" | "vertex" | "fragment" | "any", node: Node, output: string, propertyName: string): any`

<details><summary>Code</summary>

```ts
flowNodeFromShaderStage( shaderStage, node, output = null, propertyName = null ) {

		const previousTab = this.tab;
		const previousCache = this.cache;
		const previousShaderStage = this.shaderStage;
		const previousContext = this.context;

		this.setShaderStage( shaderStage );

		const context = { ...this.context };
		delete context.nodeBlock;

		this.cache = this.globalCache;
		this.tab = '\t';
		this.context = context;

		let result = null;

		if ( this.buildStage === 'generate' ) {

			const flowData = this.flowChildNode( node, output );

			if ( propertyName !== null ) {

				flowData.code += `${ this.tab + propertyName } = ${ flowData.result };\n`;

			}

			this.flowCode[ shaderStage ] = this.flowCode[ shaderStage ] + flowData.code;

			result = flowData;

		} else {

			result = node.build( this );

		}

		this.setShaderStage( previousShaderStage );

		this.cache = previousCache;
		this.tab = previousTab;
		this.context = previousContext;

		return result;

	}
```
</details>

##### `getAttributesArray(): NodeAttribute[]`

<details><summary>Code</summary>

```ts
getAttributesArray() {

		return this.attributes.concat( this.bufferAttributes );

	}
```
</details>

##### `getAttributes(): string`

<details><summary>Code</summary>

```ts
getAttributes( /*shaderStage*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

##### `getVaryings(): string`

<details><summary>Code</summary>

```ts
getVaryings( /*shaderStage*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

##### `getVar(type: string, name: string, count: number): string`

<details><summary>Code</summary>

```ts
getVar( type, name, count = null ) {

		return `${ count !== null ? this.generateArrayDeclaration( type, count ) : this.getType( type ) } ${ name }`;

	}
```
</details>

##### `getVars(shaderStage: "compute" | "vertex" | "fragment" | "any"): string`

<details><summary>Code</summary>

```ts
getVars( shaderStage ) {

		let snippet = '';

		const vars = this.vars[ shaderStage ];

		if ( vars !== undefined ) {

			for ( const variable of vars ) {

				snippet += `${ this.getVar( variable.type, variable.name ) }; `;

			}

		}

		return snippet;

	}
```
</details>

##### `getUniforms(): string`

<details><summary>Code</summary>

```ts
getUniforms( /*shaderStage*/ ) {

		console.warn( 'Abstract function.' );

	}
```
</details>

##### `getCodes(shaderStage: "compute" | "vertex" | "fragment" | "any"): string`

<details><summary>Code</summary>

```ts
getCodes( shaderStage ) {

		const codes = this.codes[ shaderStage ];

		let code = '';

		if ( codes !== undefined ) {

			for ( const nodeCode of codes ) {

				code += nodeCode.code + '\n';

			}

		}

		return code;

	}
```
</details>

##### `getHash(): string`

<details><summary>Code</summary>

```ts
getHash() {

		return this.vertexShader + this.fragmentShader + this.computeShader;

	}
```
</details>

##### `setShaderStage(shaderStage: "compute" | "vertex" | "fragment" | "any"): void`

<details><summary>Code</summary>

```ts
setShaderStage( shaderStage ) {

		this.shaderStage = shaderStage;

	}
```
</details>

##### `getShaderStage(): "compute" | "vertex" | "fragment" | "any"`

<details><summary>Code</summary>

```ts
getShaderStage() {

		return this.shaderStage;

	}
```
</details>

##### `setBuildStage(buildStage: "setup" | "generate" | "analyze"): void`

<details><summary>Code</summary>

```ts
setBuildStage( buildStage ) {

		this.buildStage = buildStage;

	}
```
</details>

##### `getBuildStage(): "setup" | "generate" | "analyze"`

<details><summary>Code</summary>

```ts
getBuildStage() {

		return this.buildStage;

	}
```
</details>

##### `buildCode(): void`

<details><summary>Code</summary>

```ts
buildCode() {

		console.warn( 'Abstract function.' );

	}
```
</details>

##### `addSubBuild(subBuild: SubBuildNode): void`

<details><summary>Code</summary>

```ts
addSubBuild( subBuild ) {

		this.subBuildLayers.push( subBuild );

	}
```
</details>

##### `removeSubBuild(): SubBuildNode`

<details><summary>Code</summary>

```ts
removeSubBuild() {

		return this.subBuildLayers.pop();

	}
```
</details>

##### `getClosestSubBuild(data: any[] | Node | Set<any>): string`

<details><summary>Code</summary>

```ts
getClosestSubBuild( data ) {

		let subBuilds;

		if ( data && data.isNode ) {

			if ( data.isShaderCallNodeInternal ) {

				subBuilds = data.shaderNode.subBuilds;

			} else if ( data.isStackNode ) {

				subBuilds = [ data.subBuild ];

			} else {

				subBuilds = this.getDataFromNode( data, 'any' ).subBuilds;

			}

		} else if ( data instanceof Set ) {

			subBuilds = [ ...data ];

		} else {

			subBuilds = data;

		}

		if ( ! subBuilds ) return null;

		const subBuildLayers = this.subBuildLayers;

		for ( let i = subBuilds.length - 1; i >= 0; i -- ) {

			const subBuild = subBuilds[ i ];

			if ( subBuildLayers.includes( subBuild ) ) {

				return subBuild;

			}

		}

		return null;

	}
```
</details>

##### `getSubBuildOutput(node: Node): string`

<details><summary>Code</summary>

```ts
getSubBuildOutput( node ) {

		return this.getSubBuildProperty( 'outputNode', node );

	}
```
</details>

##### `getSubBuildProperty(property: string, node: Node): string`

<details><summary>Code</summary>

```ts
getSubBuildProperty( property = '', node = null ) {

		let subBuild;

		if ( node !== null ) {

			subBuild = this.getClosestSubBuild( node );

		} else {

			subBuild = this.subBuildFn;

		}

		let result;

		if ( subBuild ) {

			result = property ? ( subBuild + '_' + property ) : subBuild;

		} else {

			result = property;

		}

		return result;

	}
```
</details>

##### `build(): NodeBuilder`

<details><summary>Code</summary>

```ts
build() {

		const { object, material, renderer } = this;

		if ( material !== null ) {

			let nodeMaterial = renderer.library.fromMaterial( material );

			if ( nodeMaterial === null ) {

				console.error( `NodeMaterial: Material "${ material.type }" is not compatible.` );

				nodeMaterial = new NodeMaterial();

			}

			nodeMaterial.build( this );

		} else {

			this.addFlow( 'compute', object );

		}

		// setup() -> stage 1: create possible new nodes and/or return an output reference node
		// analyze()   -> stage 2: analyze nodes to possible optimization and validation
		// generate()  -> stage 3: generate shader

		for ( const buildStage of defaultBuildStages ) {

			this.setBuildStage( buildStage );

			if ( this.context.vertex && this.context.vertex.isNode ) {

				this.flowNodeFromShaderStage( 'vertex', this.context.vertex );

			}

			for ( const shaderStage of shaderStages ) {

				this.setShaderStage( shaderStage );

				const flowNodes = this.flowNodes[ shaderStage ];

				for ( const node of flowNodes ) {

					if ( buildStage === 'generate' ) {

						this.flowNode( node );

					} else {

						node.build( this );

					}

				}

			}

		}

		this.setBuildStage( null );
		this.setShaderStage( null );

		// stage 4: build code for a specific output

		this.buildCode();
		this.buildUpdateNodes();

		return this;

	}
```
</details>

##### `getNodeUniform(uniformNode: NodeUniform, type: string): Uniform`

<details><summary>Code</summary>

```ts
getNodeUniform( uniformNode, type ) {

		if ( type === 'float' || type === 'int' || type === 'uint' ) return new NumberNodeUniform( uniformNode );
		if ( type === 'vec2' || type === 'ivec2' || type === 'uvec2' ) return new Vector2NodeUniform( uniformNode );
		if ( type === 'vec3' || type === 'ivec3' || type === 'uvec3' ) return new Vector3NodeUniform( uniformNode );
		if ( type === 'vec4' || type === 'ivec4' || type === 'uvec4' ) return new Vector4NodeUniform( uniformNode );
		if ( type === 'color' ) return new ColorNodeUniform( uniformNode );
		if ( type === 'mat2' ) return new Matrix2NodeUniform( uniformNode );
		if ( type === 'mat3' ) return new Matrix3NodeUniform( uniformNode );
		if ( type === 'mat4' ) return new Matrix4NodeUniform( uniformNode );

		throw new Error( `Uniform "${type}" not declared.` );

	}
```
</details>

##### `format(snippet: string, fromType: string, toType: string): string`

<details><summary>Code</summary>

```ts
format( snippet, fromType, toType ) {

		fromType = this.getVectorType( fromType );
		toType = this.getVectorType( toType );

		if ( fromType === toType || toType === null || this.isReference( toType ) ) {

			return snippet;

		}

		const fromTypeLength = this.getTypeLength( fromType );
		const toTypeLength = this.getTypeLength( toType );

		if ( fromTypeLength === 16 && toTypeLength === 9 ) {

			return `${ this.getType( toType ) }( ${ snippet }[ 0 ].xyz, ${ snippet }[ 1 ].xyz, ${ snippet }[ 2 ].xyz )`;

		}

		if ( fromTypeLength === 9 && toTypeLength === 4 ) {

			return `${ this.getType( toType ) }( ${ snippet }[ 0 ].xy, ${ snippet }[ 1 ].xy )`;

		}


		if ( fromTypeLength > 4 ) { // fromType is matrix-like

			// @TODO: ignore for now

			return snippet;

		}

		if ( toTypeLength > 4 || toTypeLength === 0 ) { // toType is matrix-like or unknown

			// @TODO: ignore for now

			return snippet;

		}

		if ( fromTypeLength === toTypeLength ) {

			return `${ this.getType( toType ) }( ${ snippet } )`;

		}

		if ( fromTypeLength > toTypeLength ) {

			snippet = toType === 'bool' ? `all( ${ snippet } )` : `${ snippet }.${ 'xyz'.slice( 0, toTypeLength ) }`;

			return this.format( snippet, this.getTypeFromLength( toTypeLength, this.getComponentType( fromType ) ), toType );

		}

		if ( toTypeLength === 4 && fromTypeLength > 1 ) { // toType is vec4-like

			return `${ this.getType( toType ) }( ${ this.format( snippet, fromType, 'vec3' ) }, 1.0 )`;

		}

		if ( fromTypeLength === 2 ) { // fromType is vec2-like and toType is vec3-like

			return `${ this.getType( toType ) }( ${ this.format( snippet, fromType, 'vec2' ) }, 0.0 )`;

		}

		if ( fromTypeLength === 1 && toTypeLength > 1 && fromType !== this.getComponentType( toType ) ) { // fromType is float-like

			// convert a number value to vector type, e.g:
			// vec3( 1u ) -> vec3( float( 1u ) )

			snippet = `${ this.getType( this.getComponentType( toType ) ) }( ${ snippet } )`;

		}

		return `${ this.getType( toType ) }( ${ snippet } )`; // fromType is float-like

	}
```
</details>

##### `getSignature(): string`

<details><summary>Code</summary>

```ts
getSignature() {

		return `// Three.js r${ REVISION } - Node System\n`;

	}
```
</details>


---