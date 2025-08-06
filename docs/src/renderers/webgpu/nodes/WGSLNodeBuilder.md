[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `WGSLNodeBuilder.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 69 |
| 🧱 Classes | 1 |
| 📦 Imports | 19 |
| 📊 Variables & Constants | 105 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgpu/nodes/WGSLNodeBuilder.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeUniformsGroup` | `../../common/nodes/NodeUniformsGroup.js` |
| `NodeSampler` | `../../common/nodes/NodeSampler.js` |
| `NodeSampledTexture` | `../../common/nodes/NodeSampledTexture.js` |
| `NodeSampledCubeTexture` | `../../common/nodes/NodeSampledTexture.js` |
| `NodeSampledTexture3D` | `../../common/nodes/NodeSampledTexture.js` |
| `NodeUniformBuffer` | `../../common/nodes/NodeUniformBuffer.js` |
| `NodeStorageBuffer` | `../../common/nodes/NodeStorageBuffer.js` |
| `NodeBuilder` | `../../../nodes/Nodes.js` |
| `CodeNode` | `../../../nodes/Nodes.js` |
| `getFormat` | `../utils/WebGPUTextureUtils.js` |
| `WGSLNodeParser` | `./WGSLNodeParser.js` |
| `NodeAccess` | `../../../nodes/core/constants.js` |
| `VarNode` | `../../../nodes/core/VarNode.js` |
| `ExpressionNode` | `../../../nodes/code/ExpressionNode.js` |
| `FloatType` | `../../../constants.js` |
| `RepeatWrapping` | `../../../constants.js` |
| `ClampToEdgeWrapping` | `../../../constants.js` |
| `MirroredRepeatWrapping` | `../../../constants.js` |
| `NearestFilter` | `../../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `GPUShaderStage` | `any` | let/var | `( typeof self !== 'undefined' ) ? self.GPUShaderStage : { VERTEX: 1, FRAGMENT...` | ✗ |
| `accessNames` | `{ [x: string]: string; }` | let/var | `{ [ NodeAccess.READ_ONLY ]: 'read', [ NodeAccess.WRITE_ONLY ]: 'write', [ Nod...` | ✗ |
| `wrapNames` | `{ [x: number]: string; }` | let/var | `{ [ RepeatWrapping ]: 'repeat', [ ClampToEdgeWrapping ]: 'clamp', [ MirroredR...` | ✗ |
| `gpuShaderStageLib` | `{ vertex: any; fragment: any; compute...` | let/var | `{ 'vertex': GPUShaderStage ? GPUShaderStage.VERTEX : 1, 'fragment': GPUShader...` | ✗ |
| `supports` | `{ instance: boolean; swizzleAssign: b...` | let/var | `{ instance: true, swizzleAssign: false, storageBuffer: true }` | ✗ |
| `wgslFnOpLib` | `{ '^^': string; }` | let/var | `{ '^^': 'tsl_xor' }` | ✗ |
| `wgslTypeLib` | `{ float: string; int: string; uint: s...` | let/var | `{ float: 'f32', int: 'i32', uint: 'u32', bool: 'bool', color: 'vec3<f32>', ve...` | ✗ |
| `wgslCodeCache` | `{}` | let/var | `{}` | ✗ |
| `wgslPolyfill` | `{ tsl_xor: CodeNode; mod_float: CodeN...` | let/var | `{ tsl_xor: new CodeNode( 'fn tsl_xor( a : bool, b : bool ) -> bool { return (...` | ✗ |
| `wgslMethods` | `{ dFdx: string; dFdy: string; mod_flo...` | let/var | `{ dFdx: 'dpdx', dFdy: '- dpdy', mod_float: 'tsl_mod_float', mod_vec2: 'tsl_mo...` | ✗ |
| `diagnostics` | `string` | let/var | `''` | ✗ |
| `functionName` | `string` | let/var | ``tsl_coord_${ wrapNames[ texture.wrapS ] }S_${ wrapNames[ texture.wrapT ] }_$...` | ✗ |
| `nodeCode` | `any` | let/var | `wgslCodeCache[ functionName ]` | ✗ |
| `includes` | `any[]` | let/var | `[]` | ✗ |
| `coordType` | `"vec3f" \| "vec2f"` | let/var | `texture.isData3DTexture ? 'vec3f' : 'vec2f'` | ✗ |
| `code` | `string` | let/var | ``fn ${ functionName }( coord : ${ coordType } ) -> ${ coordType } {\n\n\tretu...` | ✗ |
| `textureDimensionNode` | `any` | let/var | `textureData.dimensionsSnippet[ levelSnippet ]` | ✗ |
| `textureDimensionsParams` | `any` | let/var | `*not shown*` | ✗ |
| `dimensionType` | `any` | let/var | `*not shown*` | ✗ |
| `isMultisampled` | `boolean` | let/var | `primarySamples > 1` | ✗ |
| `vecType` | `"vec2" \| "vec3"` | let/var | `texture.isData3DTexture ? 'vec3' : 'vec2'` | ✗ |
| `coordSnippet` | `string` | let/var | ``${ vecType }<u32>( ${ wrapFunction }( ${ uvSnippet } ) * ${ vecType }<f32>( ...` | ✗ |
| `snippet` | `any` | let/var | `*not shown*` | ✗ |
| `snippet` | `any` | let/var | `*not shown*` | ✗ |
| `snippet` | `any` | let/var | `null` | ✗ |
| `name` | `any` | let/var | `node.name` | ✗ |
| `type` | `any` | let/var | `node.type` | ✗ |
| `fnOp` | `any` | let/var | `wgslFnOpLib[ op ]` | ✗ |
| `uniformGPU` | `any` | let/var | `*not shown*` | ✗ |
| `group` | `any` | let/var | `node.groupNode` | ✗ |
| `groupName` | `any` | let/var | `group.name` | ✗ |
| `texture` | `any` | let/var | `null` | ✗ |
| `sampler` | `NodeSampler` | let/var | `new NodeSampler( `${ uniformNode.name }_sampler`, uniformNode.node, group )` | ✗ |
| `bufferClass` | `typeof NodeUniformBuffer \| typeof No...` | let/var | `type === 'buffer' ? NodeUniformBuffer : NodeStorageBuffer` | ✗ |
| `buffer` | `NodeUniformBuffer \| NodeStorageBuffer` | let/var | `new bufferClass( node, group )` | ✗ |
| `uniformsStage` | `{ [x: string]: NodeUniformsGroup; }` | let/var | `this.uniformGroups[ shaderStage ] \|\| ( this.uniformGroups[ shaderStage ] = ...` | ✗ |
| `uniformsGroup` | `NodeUniformsGroup` | let/var | `uniformsStage[ groupName ]` | ✗ |
| `map` | `Map<any, any>` | let/var | `this.builtins[ shaderStage ] \|\| ( this.builtins[ shaderStage ] = new Map() )` | ✗ |
| `layout` | `any` | let/var | `shaderNode.layout` | ✗ |
| `parameters` | `any[]` | let/var | `[]` | ✗ |
| `code` | `string` | let/var | ``fn ${ layout.name }( ${ parameters.join( ', ' ) } ) -> ${ this.getType( layo...` | ✗ |
| `stage` | `Set<string>` | let/var | `this.directives[ shaderStage ] \|\| ( this.directives[ shaderStage ] = new Se...` | ✗ |
| `snippets` | `any[]` | let/var | `[]` | ✗ |
| `directives` | `Set<string>` | let/var | `this.directives[ shaderStage ]` | ✗ |
| `snippets` | `any[]` | let/var | `[]` | ✗ |
| `builtins` | `Map<string, any>` | let/var | `this.builtins[ shaderStage ]` | ✗ |
| `snippets` | `any[]` | let/var | `[]` | ✗ |
| `snippets` | `any[]` | let/var | `[]` | ✗ |
| `attribute` | `NodeAttribute` | let/var | `attributes[ index ]` | ✗ |
| `name` | `string` | let/var | `attribute.name` | ✗ |
| `snippets` | `any[]` | let/var | `[]` | ✗ |
| `prefix` | `string` | let/var | `struct.output ? '@location( ' + member.index + ' ) ' : ''` | ✗ |
| `result` | `string` | let/var | `''` | ✗ |
| `structs` | `any` | let/var | `this.structs[ shaderStage ]` | ✗ |
| `snippets` | `any[]` | let/var | `[]` | ✗ |
| `snippet` | `string` | let/var | ``struct ${ struct.name } {\n`` | ✗ |
| `snippet` | `string` | let/var | ``var ${ name } : `` | ✗ |
| `snippets` | `any[]` | let/var | `[]` | ✗ |
| `vars` | `number \| NodeVar[]` | let/var | `this.vars[ shaderStage ]` | ✗ |
| `snippets` | `any[]` | let/var | `[]` | ✗ |
| `varyings` | `NodeVarying[]` | let/var | `this.varyings` | ✗ |
| `vars` | `number \| NodeVar[]` | let/var | `this.vars[ shaderStage ]` | ✗ |
| `varying` | `NodeVarying` | let/var | `varyings[ index ]` | ✗ |
| `attributesSnippet` | `string` | let/var | ``@location( ${index} )`` | ✗ |
| `samplingSnippet` | `string` | let/var | `varying.interpolationSampling !== null ? `, ${ varying.interpolationSampling ...` | ✗ |
| `attribute` | `any` | let/var | `nodeUniform.value` | ✗ |
| `bufferNode` | `any` | let/var | `nodeUniform.node` | ✗ |
| `isAttributeStructType` | `boolean` | let/var | `( attribute.isBufferAttribute \|\| attribute.isInstancedBufferAttribute ) && ...` | ✗ |
| `isStructArray` | `boolean` | let/var | `( bufferNode.value && bufferNode.value.array ) && ( typeof bufferNode.value.i...` | ✗ |
| `uniforms` | `any` | let/var | `this.uniforms[ shaderStage ]` | ✗ |
| `bindingSnippets` | `any[]` | let/var | `[]` | ✗ |
| `bufferSnippets` | `any[]` | let/var | `[]` | ✗ |
| `structSnippets` | `any[]` | let/var | `[]` | ✗ |
| `uniformGroups` | `{}` | let/var | `{}` | ✗ |
| `groupName` | `any` | let/var | `uniform.groupNode.name` | ✗ |
| `uniformIndexes` | `any` | let/var | `this.bindingsIndexes[ groupName ]` | ✗ |
| `texture` | `any` | let/var | `uniform.node.value` | ✗ |
| `textureType` | `any` | let/var | `*not shown*` | ✗ |
| `multisampled` | `string` | let/var | `''` | ✗ |
| `is3D` | `any` | let/var | `uniform.node.value.is3DTexture` | ✗ |
| `isArrayTexture` | `any` | let/var | `uniform.node.value.isArrayTexture` | ✗ |
| `dimension` | `string` | let/var | `is3D ? '3d' : `2d${ isArrayTexture ? '_array' : '' }`` | ✗ |
| `bufferNode` | `any` | let/var | `uniform.node` | ✗ |
| `bufferCount` | `any` | let/var | `bufferNode.bufferCount` | ✗ |
| `bufferCountSnippet` | `string` | let/var | `bufferCount > 0 && uniform.type === 'buffer' ? ', ' + bufferCount : ''` | ✗ |
| `bufferAccessMode` | `string` | let/var | `bufferNode.isStorageBufferNode ? `storage, ${ this.getStorageAccess( bufferNo...` | ✗ |
| `bufferTypeSnippet` | `string` | let/var | `bufferNode.isAtomic ? `atomic<${ bufferType }>` : `${ bufferType }`` | ✗ |
| `bufferSnippet` | `string` | let/var | ``\tvalue : array< ${ bufferTypeSnippet }${ bufferCountSnippet } >`` | ✗ |
| `groupName` | `any` | let/var | `uniform.groupNode.name` | ✗ |
| `group` | `any` | let/var | `uniformGroups[ groupName ] \|\| ( uniformGroups[ groupName ] = { index: unifo...` | ✗ |
| `group` | `any` | let/var | `uniformGroups[ name ]` | ✗ |
| `shadersData` | `{ fragment: {}; vertex: {}; compute?:...` | let/var | `this.material !== null ? { fragment: {}, vertex: {} } : { compute: {} }` | ✗ |
| `stageData` | `any` | let/var | `shadersData[ shaderStage ]` | ✗ |
| `flow` | `string` | let/var | `'// code\n\n'` | ✗ |
| `flowNodes` | `Node[]` | let/var | `this.flowNodes[ shaderStage ]` | ✗ |
| `mainNode` | `Node` | let/var | `flowNodes[ flowNodes.length - 1 ]` | ✗ |
| `outputNode` | `any` | let/var | `mainNode.outputNode` | ✗ |
| `isOutputStruct` | `boolean` | let/var | `( outputNode !== undefined && outputNode.isOutputStructNode === true )` | ✗ |
| `slotName` | `any` | let/var | `node.name` | ✗ |
| `structSnippet` | `string` | let/var | `'\t@location(0) color: vec4<f32>'` | ✗ |
| `workgroupSize` | `any` | let/var | `this.object.workgroupSize` | ✗ |
| `wgslMethod` | `any` | let/var | `*not shown*` | ✗ |
| `result` | `any` | let/var | `supports[ name ]` | ✗ |
| `codeNode` | `any` | let/var | `wgslPolyfill[ name ]` | ✗ |
| `structName` | `string` | let/var | `name + 'Struct'` | ✗ |


---

## Functions

### `WGSLNodeBuilder._generateTextureSample(texture: Texture, textureProperty: string, uvSnippet: string, depthSnippet: string, shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the WGSL snippet for sampled textures.
	 *
	 * @private
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The WGSL snippet.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`textureProperty`** `string`
- **`uvSnippet`** `string`
- **`depthSnippet`** `string`
- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `this.generateTextureSampleLevel`

<details><summary>Code</summary>

```typescript
_generateTextureSample( texture, textureProperty, uvSnippet, depthSnippet, shaderStage = this.shaderStage ) {

		if ( shaderStage === 'fragment' ) {

			if ( depthSnippet ) {

				return `textureSample( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ depthSnippet } )`;

			} else {

				return `textureSample( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet } )`;

			}

		} else {

			return this.generateTextureSampleLevel( texture, textureProperty, uvSnippet, '0', depthSnippet );

		}

	}
```
</details>

### `WGSLNodeBuilder.generateTextureSampleLevel(texture: Texture, textureProperty: string, uvSnippet: string, levelSnippet: string, depthSnippet: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the WGSL snippet when sampling textures with explicit mip level.
	 *
	 * @private
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {string} levelSnippet - A WGSL snippet that represents the mip level, with level 0 containing a full size version of the texture.
	 * @param {string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @return {string} The WGSL snippet.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`textureProperty`** `string`
- **`uvSnippet`** `string`
- **`levelSnippet`** `string`
- **`depthSnippet`** `string`

**Returns:** `string`

**Calls:**

- `this.isUnfilterable`
- `this.isFilteredTexture`
- `this.generateFilteredTexture`
- `this.generateTextureLod`

<details><summary>Code</summary>

```typescript
generateTextureSampleLevel( texture, textureProperty, uvSnippet, levelSnippet, depthSnippet ) {

		if ( this.isUnfilterable( texture ) === false ) {

			return `textureSampleLevel( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ levelSnippet } )`;

		} else if ( this.isFilteredTexture( texture ) ) {

			return this.generateFilteredTexture( texture, textureProperty, uvSnippet, levelSnippet );

		} else {

			return this.generateTextureLod( texture, textureProperty, uvSnippet, depthSnippet, levelSnippet );

		}

	}
```
</details>

### `WGSLNodeBuilder.generateWrapFunction(texture: Texture): string`

**JSDoc:**
```typescript
/**
	 * Generates a wrap function used in context of textures.
	 *
	 * @param {Texture} texture - The texture to generate the function for.
	 * @return {string} The name of the generated function.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `string`

**Calls:**

- `includes.push`
- `console.warn`
- `addWrapSnippet`
- `nodeCode.build`

**Internal Comments:**
```
// For 3D textures, use vec3f; for texture arrays, keep vec2f since array index is separate (x2)
```

<details><summary>Code</summary>

```typescript
generateWrapFunction( texture ) {

		const functionName = `tsl_coord_${ wrapNames[ texture.wrapS ] }S_${ wrapNames[ texture.wrapT ] }_${ texture.isData3DTexture ? '3d' : '2d' }T`;

		let nodeCode = wgslCodeCache[ functionName ];

		if ( nodeCode === undefined ) {

			const includes = [];

			// For 3D textures, use vec3f; for texture arrays, keep vec2f since array index is separate
			const coordType = texture.isData3DTexture ? 'vec3f' : 'vec2f';
			let code = `fn ${ functionName }( coord : ${ coordType } ) -> ${ coordType } {\n\n\treturn ${ coordType }(\n`;

			const addWrapSnippet = ( wrap, axis ) => {

				if ( wrap === RepeatWrapping ) {

					includes.push( wgslPolyfill.repeatWrapping_float );

					code += `\t\ttsl_repeatWrapping_float( coord.${ axis } )`;

				} else if ( wrap === ClampToEdgeWrapping ) {

					includes.push( wgslPolyfill.clampWrapping_float );

					code += `\t\ttsl_clampWrapping_float( coord.${ axis } )`;

				} else if ( wrap === MirroredRepeatWrapping ) {

					includes.push( wgslPolyfill.mirrorWrapping_float );

					code += `\t\ttsl_mirrorWrapping_float( coord.${ axis } )`;

				} else {

					code += `\t\tcoord.${ axis }`;

					console.warn( `WebGPURenderer: Unsupported texture wrap type "${ wrap }" for vertex shader.` );

				}

			};

			addWrapSnippet( texture.wrapS, 'x' );

			code += ',\n';

			addWrapSnippet( texture.wrapT, 'y' );

			if ( texture.isData3DTexture ) {

				code += ',\n';
				addWrapSnippet( texture.wrapR, 'z' );

			}

			code += '\n\t);\n\n}\n';

			wgslCodeCache[ functionName ] = nodeCode = new CodeNode( code, includes );

		}

		nodeCode.build( this );

		return functionName;

	}
```
</details>

### `WGSLNodeBuilder.generateArrayDeclaration(type: string, count: number): string`

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

		return `array< ${ this.getType( type ) }, ${ count } >`;

	}
```
</details>

### `WGSLNodeBuilder.generateTextureDimension(texture: Texture, textureProperty: string, levelSnippet: string): string`

**JSDoc:**
```typescript
/**
	 * Generates a WGSL variable that holds the texture dimension of the given texture.
	 * It also returns information about the number of layers (elements) of an arrayed
	 * texture as well as the cube face count of cube textures.
	 *
	 * @param {Texture} texture - The texture to generate the function for.
	 * @param {string} textureProperty - The name of the video texture uniform in the shader.
	 * @param {string} levelSnippet - A WGSL snippet that represents the mip level, with level 0 containing a full size version of the texture.
	 * @return {string} The name of the dimension variable.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`textureProperty`** `string`
- **`levelSnippet`** `string`

**Returns:** `string`

**Calls:**

- `this.getDataFromNode`
- `this.renderer.backend.utils.getTextureSampleData`
- `textureDimensionNode.build`

**Internal Comments:**
```
// Regular 2D textures, depth textures, etc. (x3)
// Build parameters string based on texture type and multisampling
// For cube textures, we know it's always 6 faces
```

<details><summary>Code</summary>

```typescript
generateTextureDimension( texture, textureProperty, levelSnippet ) {

		const textureData = this.getDataFromNode( texture, this.shaderStage, this.globalCache );

		if ( textureData.dimensionsSnippet === undefined ) textureData.dimensionsSnippet = {};

		let textureDimensionNode = textureData.dimensionsSnippet[ levelSnippet ];

		if ( textureData.dimensionsSnippet[ levelSnippet ] === undefined ) {

			let textureDimensionsParams;
			let dimensionType;

			const { primarySamples } = this.renderer.backend.utils.getTextureSampleData( texture );
			const isMultisampled = primarySamples > 1;

			if ( texture.isData3DTexture ) {

				dimensionType = 'vec3<u32>';

			} else {

				// Regular 2D textures, depth textures, etc.
				dimensionType = 'vec2<u32>';

			}

			// Build parameters string based on texture type and multisampling
			if ( isMultisampled || texture.isStorageTexture ) {

				textureDimensionsParams = textureProperty;

			} else {

				textureDimensionsParams = `${textureProperty}${levelSnippet ? `, u32( ${ levelSnippet } )` : ''}`;

			}

			textureDimensionNode = new VarNode( new ExpressionNode( `textureDimensions( ${ textureDimensionsParams } )`, dimensionType ) );

			textureData.dimensionsSnippet[ levelSnippet ] = textureDimensionNode;

			if ( texture.isArrayTexture || texture.isDataArrayTexture || texture.isData3DTexture ) {

				textureData.arrayLayerCount = new VarNode(
					new ExpressionNode(
						`textureNumLayers(${textureProperty})`,
						'u32'
					)
				);

			}

			// For cube textures, we know it's always 6 faces
			if ( texture.isTextureCube ) {

				textureData.cubeFaceCount = new VarNode(
					new ExpressionNode( '6u', 'u32' )
				);

			}

		}

		return textureDimensionNode.build( this );

	}
```
</details>

### `WGSLNodeBuilder.generateFilteredTexture(texture: Texture, textureProperty: string, uvSnippet: string, levelSnippet: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the WGSL snippet for a manual filtered texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {string} levelSnippet - A WGSL snippet that represents the mip level, with level 0 containing a full size version of the texture.
	 * @return {string} The WGSL snippet.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`textureProperty`** `string`
- **`uvSnippet`** `string`
- **`levelSnippet`** `string`

**Returns:** `string`

**Calls:**

- `this._include`
- `this.generateWrapFunction`
- `this.generateTextureDimension`

<details><summary>Code</summary>

```typescript
generateFilteredTexture( texture, textureProperty, uvSnippet, levelSnippet = '0u' ) {

		this._include( 'biquadraticTexture' );

		const wrapFunction = this.generateWrapFunction( texture );
		const textureDimension = this.generateTextureDimension( texture, textureProperty, levelSnippet );

		return `tsl_biquadraticTexture( ${ textureProperty }, ${ wrapFunction }( ${ uvSnippet } ), ${ textureDimension }, u32( ${ levelSnippet } ) )`;

	}
```
</details>

### `WGSLNodeBuilder.generateTextureLod(texture: Texture, textureProperty: string, uvSnippet: string, depthSnippet: string, levelSnippet: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the WGSL snippet for a texture lookup with explicit level-of-detail.
	 * Since it's a lookup, no sampling or filtering is applied.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [levelSnippet='0u'] - A WGSL snippet that represents the mip level, with level 0 containing a full size version of the texture.
	 * @return {string} The WGSL snippet.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`textureProperty`** `string`
- **`uvSnippet`** `string`
- **`depthSnippet`** `string`
- **`levelSnippet`** `string`

**Returns:** `string`

**Calls:**

- `this.generateWrapFunction`
- `this.generateTextureDimension`
- `this.generateTextureLoad`

<details><summary>Code</summary>

```typescript
generateTextureLod( texture, textureProperty, uvSnippet, depthSnippet, levelSnippet = '0u' ) {

		const wrapFunction = this.generateWrapFunction( texture );
		const textureDimension = this.generateTextureDimension( texture, textureProperty, levelSnippet );

		const vecType = texture.isData3DTexture ? 'vec3' : 'vec2';
		const coordSnippet = `${ vecType }<u32>( ${ wrapFunction }( ${ uvSnippet } ) * ${ vecType }<f32>( ${ textureDimension } ) )`;

		return this.generateTextureLoad( texture, textureProperty, coordSnippet, depthSnippet, levelSnippet );

	}
```
</details>

### `WGSLNodeBuilder.generateTextureLoad(texture: Texture, textureProperty: string, uvIndexSnippet: string, depthSnippet: string, levelSnippet: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the WGSL snippet that reads a single texel from a texture without sampling or filtering.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvIndexSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [levelSnippet='0u'] - A WGSL snippet that represents the mip level, with level 0 containing a full size version of the texture.
	 * @return {string} The WGSL snippet.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`textureProperty`** `string`
- **`uvIndexSnippet`** `string`
- **`depthSnippet`** `string`
- **`levelSnippet`** `string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
generateTextureLoad( texture, textureProperty, uvIndexSnippet, depthSnippet, levelSnippet = '0u' ) {

		let snippet;

		if ( depthSnippet ) {

			snippet = `textureLoad( ${ textureProperty }, ${ uvIndexSnippet }, ${ depthSnippet }, u32( ${ levelSnippet } ) )`;

		} else {

			snippet = `textureLoad( ${ textureProperty }, ${ uvIndexSnippet }, u32( ${ levelSnippet } ) )`;

			if ( this.renderer.backend.compatibilityMode && texture.isDepthTexture ) {

				snippet += '.x';

			}

		}

		return snippet;

	}
```
</details>

### `WGSLNodeBuilder.generateTextureStore(texture: Texture, textureProperty: string, uvIndexSnippet: string, depthSnippet: string, valueSnippet: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the WGSL snippet that writes a single texel to a texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvIndexSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} valueSnippet - A WGSL snippet that represent the new texel value.
	 * @return {string} The WGSL snippet.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`textureProperty`** `string`
- **`uvIndexSnippet`** `string`
- **`depthSnippet`** `string`
- **`valueSnippet`** `string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
generateTextureStore( texture, textureProperty, uvIndexSnippet, depthSnippet, valueSnippet ) {

		let snippet;

		if ( depthSnippet ) {

			snippet = `textureStore( ${ textureProperty }, ${ uvIndexSnippet }, ${ depthSnippet }, ${ valueSnippet } )`;

		} else {

			snippet = `textureStore( ${ textureProperty }, ${ uvIndexSnippet }, ${ valueSnippet } )`;

		}

		return snippet;

	}
```
</details>

### `WGSLNodeBuilder.isSampleCompare(texture: Texture): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the sampled values of the given texture should be compared against a reference value.
	 *
	 * @param {Texture} texture - The texture.
	 * @return {boolean} Whether the sampled values of the given texture should be compared against a reference value or not.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
isSampleCompare( texture ) {

		return texture.isDepthTexture === true && texture.compareFunction !== null;

	}
```
</details>

### `WGSLNodeBuilder.isUnfilterable(texture: Texture): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given texture is unfilterable.
	 *
	 * @param {Texture} texture - The texture.
	 * @return {boolean} Whether the given texture is unfilterable or not.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `boolean`

**Calls:**

- `this.getComponentTypeFromTexture`
- `this.isAvailable`
- `this.isSampleCompare`
- `this.renderer.backend.utils.getTextureSampleData`

<details><summary>Code</summary>

```typescript
isUnfilterable( texture ) {

		return this.getComponentTypeFromTexture( texture ) !== 'float' ||
			( ! this.isAvailable( 'float32Filterable' ) && texture.isDataTexture === true && texture.type === FloatType ) ||
			( this.isSampleCompare( texture ) === false && texture.minFilter === NearestFilter && texture.magFilter === NearestFilter ) ||
			this.renderer.backend.utils.getTextureSampleData( texture ).primarySamples > 1;

	}
```
</details>

### `WGSLNodeBuilder.generateTexture(texture: Texture, textureProperty: string, uvSnippet: string, depthSnippet: string, shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the WGSL snippet for sampling/loading the given texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The WGSL snippet.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`textureProperty`** `string`
- **`uvSnippet`** `string`
- **`depthSnippet`** `string`
- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `this.isUnfilterable`
- `this.generateTextureLod`
- `this._generateTextureSample`

<details><summary>Code</summary>

```typescript
generateTexture( texture, textureProperty, uvSnippet, depthSnippet, shaderStage = this.shaderStage ) {

		let snippet = null;

		if ( this.isUnfilterable( texture ) ) {

			snippet = this.generateTextureLod( texture, textureProperty, uvSnippet, depthSnippet, '0', shaderStage );

		} else {

			snippet = this._generateTextureSample( texture, textureProperty, uvSnippet, depthSnippet, shaderStage );

		}

		return snippet;

	}
```
</details>

### `WGSLNodeBuilder.generateTextureGrad(texture: Texture, textureProperty: string, uvSnippet: string, gradSnippet: string[], depthSnippet: string, shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the WGSL snippet for sampling/loading the given texture using explicit gradients.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {Array<string>} gradSnippet - An array holding both gradient WGSL snippets.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The WGSL snippet.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`textureProperty`** `string`
- **`uvSnippet`** `string`
- **`gradSnippet`** `string[]`
- **`depthSnippet`** `string`
- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `console.error`

**Internal Comments:**
```
// TODO handle i32 or u32 --> uvSnippet, array_index: A, ddx, ddy
```

<details><summary>Code</summary>

```typescript
generateTextureGrad( texture, textureProperty, uvSnippet, gradSnippet, depthSnippet, shaderStage = this.shaderStage ) {

		if ( shaderStage === 'fragment' ) {

			// TODO handle i32 or u32 --> uvSnippet, array_index: A, ddx, ddy
			return `textureSampleGrad( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet },  ${ gradSnippet[ 0 ] }, ${ gradSnippet[ 1 ] } )`;

		} else {

			console.error( `WebGPURenderer: THREE.TextureNode.gradient() does not support ${ shaderStage } shader.` );

		}

	}
```
</details>

### `WGSLNodeBuilder.generateTextureCompare(texture: Texture, textureProperty: string, uvSnippet: string, compareSnippet: string, depthSnippet: string, shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the WGSL snippet for sampling a depth texture and comparing the sampled depth values
	 * against a reference value.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {string} compareSnippet -  A WGSL snippet that represents the reference value.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The WGSL snippet.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`textureProperty`** `string`
- **`uvSnippet`** `string`
- **`compareSnippet`** `string`
- **`depthSnippet`** `string`
- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `console.error`

<details><summary>Code</summary>

```typescript
generateTextureCompare( texture, textureProperty, uvSnippet, compareSnippet, depthSnippet, shaderStage = this.shaderStage ) {

		if ( shaderStage === 'fragment' ) {

			if ( texture.isDepthTexture === true && texture.isArrayTexture === true ) {

				return `textureSampleCompare( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ depthSnippet }, ${ compareSnippet } )`;

			}

			return `textureSampleCompare( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ compareSnippet } )`;

		} else {

			console.error( `WebGPURenderer: THREE.DepthTexture.compareFunction() does not support ${ shaderStage } shader.` );

		}

	}
```
</details>

### `WGSLNodeBuilder.generateTextureLevel(texture: Texture, textureProperty: string, uvSnippet: string, levelSnippet: string, depthSnippet: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the WGSL snippet when sampling textures with explicit mip level.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {string} levelSnippet - A WGSL snippet that represents the mip level, with level 0 containing a full size version of the texture.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The WGSL snippet.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`textureProperty`** `string`
- **`uvSnippet`** `string`
- **`levelSnippet`** `string`
- **`depthSnippet`** `string`

**Returns:** `string`

**Calls:**

- `this.isUnfilterable`
- `this.isFilteredTexture`
- `this.generateFilteredTexture`
- `this.generateTextureLod`

<details><summary>Code</summary>

```typescript
generateTextureLevel( texture, textureProperty, uvSnippet, levelSnippet, depthSnippet ) {

		if ( this.isUnfilterable( texture ) === false ) {

			return `textureSampleLevel( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ levelSnippet } )`;

		} else if ( this.isFilteredTexture( texture ) ) {

			return this.generateFilteredTexture( texture, textureProperty, uvSnippet, levelSnippet );

		} else {

			return this.generateTextureLod( texture, textureProperty, uvSnippet, depthSnippet, levelSnippet );

		}

	}
```
</details>

### `WGSLNodeBuilder.generateTextureBias(texture: Texture, textureProperty: string, uvSnippet: string, biasSnippet: string, depthSnippet: string, shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the WGSL snippet when sampling textures with a bias to the mip level.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {string} biasSnippet - A WGSL snippet that represents the bias to apply to the mip level before sampling.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The WGSL snippet.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`textureProperty`** `string`
- **`uvSnippet`** `string`
- **`biasSnippet`** `string`
- **`depthSnippet`** `string`
- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `console.error`

<details><summary>Code</summary>

```typescript
generateTextureBias( texture, textureProperty, uvSnippet, biasSnippet, depthSnippet, shaderStage = this.shaderStage ) {

		if ( shaderStage === 'fragment' ) {

			return `textureSampleBias( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ biasSnippet } )`;

		} else {

			console.error( `WebGPURenderer: THREE.TextureNode.biasNode does not support ${ shaderStage } shader.` );

		}

	}
```
</details>

### `WGSLNodeBuilder.getPropertyName(node: Node, shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns a WGSL snippet that represents the property name of the given node.
	 *
	 * @param {Node} node - The node.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The property name.
	 */
```

**Parameters:**

- **`node`** `Node`
- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `this.isCustomStruct`
- `super.getPropertyName`

<details><summary>Code</summary>

```typescript
getPropertyName( node, shaderStage = this.shaderStage ) {

		if ( node.isNodeVarying === true && node.needsInterpolation === true ) {

			if ( shaderStage === 'vertex' ) {

				return `varyings.${ node.name }`;

			}

		} else if ( node.isNodeUniform === true ) {

			const name = node.name;
			const type = node.type;

			if ( type === 'texture' || type === 'cubeTexture' || type === 'storageTexture' || type === 'texture3D' ) {

				return name;

			} else if ( type === 'buffer' || type === 'storageBuffer' || type === 'indirectStorageBuffer' ) {

				if ( this.isCustomStruct( node ) ) {

					return name;

				}

				return name + '.value';

			} else {

				return node.groupNode.name + '.' + name;

			}

		}

		return super.getPropertyName( node );

	}
```
</details>

### `WGSLNodeBuilder.getOutputStructName(): string`

**JSDoc:**
```typescript
/**
	 * Returns the output struct name.
	 *
	 * @return {string} The name of the output struct.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getOutputStructName() {

		return 'output';

	}
```
</details>

### `WGSLNodeBuilder.getFunctionOperator(op: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the native shader operator name for a given generic name.
	 *
	 * @param {string} op - The operator name to resolve.
	 * @return {?string} The resolved operator name.
	 */
```

**Parameters:**

- **`op`** `string`

**Returns:** `string`

**Calls:**

- `this._include`

<details><summary>Code</summary>

```typescript
getFunctionOperator( op ) {

		const fnOp = wgslFnOpLib[ op ];

		if ( fnOp !== undefined ) {

			this._include( fnOp );

			return fnOp;

		}

		return null;

	}
```
</details>

### `WGSLNodeBuilder.getNodeAccess(node: any, shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the node access for the given node and shader stage.
	 *
	 * @param {StorageTextureNode|StorageBufferNode} node - The storage node.
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The node access.
	 */
```

**Parameters:**

- **`node`** `any`
- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
getNodeAccess( node, shaderStage ) {

		if ( shaderStage !== 'compute' ) {

			if ( node.isAtomic === true ) {

				console.warn( 'WebGPURenderer: Atomic operations are only supported in compute shaders.' );

				return NodeAccess.READ_WRITE;

			}

			return NodeAccess.READ_ONLY;

		}

		return node.access;

	}
```
</details>

### `WGSLNodeBuilder.getStorageAccess(node: any, shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns A WGSL snippet representing the storage access.
	 *
	 * @param {StorageTextureNode|StorageBufferNode} node - The storage node.
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The WGSL snippet representing the storage access.
	 */
```

**Parameters:**

- **`node`** `any`
- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `this.getNodeAccess`

<details><summary>Code</summary>

```typescript
getStorageAccess( node, shaderStage ) {

		return accessNames[ this.getNodeAccess( node, shaderStage ) ];

	}
```
</details>

### `WGSLNodeBuilder.getUniformFromNode(node: UniformNode, type: string, shaderStage: string, name: string): NodeUniform`

**JSDoc:**
```typescript
/**
	 * This method is one of the more important ones since it's responsible
	 * for generating a matching binding instance for the given uniform node.
	 *
	 * These bindings are later used in the renderer to create bind groups
	 * and layouts.
	 *
	 * @param {UniformNode} node - The uniform node.
	 * @param {string} type - The node data type.
	 * @param {string} shaderStage - The shader stage.
	 * @param {?string} [name=null] - An optional uniform name.
	 * @return {NodeUniform} The node uniform object.
	 */
```

**Parameters:**

- **`node`** `UniformNode`
- **`type`** `string`
- **`shaderStage`** `string`
- **`name`** `string`

**Returns:** `NodeUniform`

**Calls:**

- `super.getUniformFromNode`
- `this.getDataFromNode`
- `this.getBindGroupArray`
- `this.getNodeAccess`
- `texture.setVisibility`
- `this.isUnfilterable`
- `sampler.setVisibility`
- `bindings.push`
- `buffer.setVisibility`
- `uniformsGroup.setVisibility`
- `this.getNodeUniform`
- `uniformsGroup.addUniform`

<details><summary>Code</summary>

```typescript
getUniformFromNode( node, type, shaderStage, name = null ) {

		const uniformNode = super.getUniformFromNode( node, type, shaderStage, name );
		const nodeData = this.getDataFromNode( node, shaderStage, this.globalCache );

		if ( nodeData.uniformGPU === undefined ) {

			let uniformGPU;

			const group = node.groupNode;
			const groupName = group.name;

			const bindings = this.getBindGroupArray( groupName, shaderStage );

			if ( type === 'texture' || type === 'cubeTexture' || type === 'storageTexture' || type === 'texture3D' ) {

				let texture = null;

				const access = this.getNodeAccess( node, shaderStage );

				if ( type === 'texture' || type === 'storageTexture' ) {

					if ( node.value.is3DTexture === true ) {

						texture = new NodeSampledTexture3D( uniformNode.name, uniformNode.node, group, access );

					} else {

						texture = new NodeSampledTexture( uniformNode.name, uniformNode.node, group, access );

					}

				} else if ( type === 'cubeTexture' ) {

					texture = new NodeSampledCubeTexture( uniformNode.name, uniformNode.node, group, access );

				} else if ( type === 'texture3D' ) {

					texture = new NodeSampledTexture3D( uniformNode.name, uniformNode.node, group, access );

				}

				texture.store = node.isStorageTextureNode === true;
				texture.setVisibility( gpuShaderStageLib[ shaderStage ] );

				if ( this.isUnfilterable( node.value ) === false && texture.store === false ) {

					const sampler = new NodeSampler( `${ uniformNode.name }_sampler`, uniformNode.node, group );
					sampler.setVisibility( gpuShaderStageLib[ shaderStage ] );

					bindings.push( sampler, texture );

					uniformGPU = [ sampler, texture ];

				} else {

					bindings.push( texture );

					uniformGPU = [ texture ];

				}

			} else if ( type === 'buffer' || type === 'storageBuffer' || type === 'indirectStorageBuffer' ) {

				const bufferClass = type === 'buffer' ? NodeUniformBuffer : NodeStorageBuffer;

				const buffer = new bufferClass( node, group );
				buffer.setVisibility( gpuShaderStageLib[ shaderStage ] );

				bindings.push( buffer );

				uniformGPU = buffer;

				uniformNode.name = name ? name : 'NodeBuffer_' + uniformNode.id;

			} else {

				const uniformsStage = this.uniformGroups[ shaderStage ] || ( this.uniformGroups[ shaderStage ] = {} );

				let uniformsGroup = uniformsStage[ groupName ];

				if ( uniformsGroup === undefined ) {

					uniformsGroup = new NodeUniformsGroup( groupName, group );
					uniformsGroup.setVisibility( gpuShaderStageLib[ shaderStage ] );

					uniformsStage[ groupName ] = uniformsGroup;

					bindings.push( uniformsGroup );

				}

				uniformGPU = this.getNodeUniform( uniformNode, type );

				uniformsGroup.addUniform( uniformGPU );

			}

			nodeData.uniformGPU = uniformGPU;

		}

		return uniformNode;

	}
```
</details>

### `WGSLNodeBuilder.getBuiltin(name: string, property: string, type: string, shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * This method should be used whenever builtins are required in nodes.
	 * The internal builtins data structure will make sure builtins are
	 * defined in the WGSL source.
	 *
	 * @param {string} name - The builtin name.
	 * @param {string} property - The property name.
	 * @param {string} type - The node data type.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The property name.
	 */
```

**Parameters:**

- **`name`** `string`
- **`property`** `string`
- **`type`** `string`
- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `map.has`
- `map.set`

<details><summary>Code</summary>

```typescript
getBuiltin( name, property, type, shaderStage = this.shaderStage ) {

		const map = this.builtins[ shaderStage ] || ( this.builtins[ shaderStage ] = new Map() );

		if ( map.has( name ) === false ) {

			map.set( name, {
				name,
				property,
				type
			} );

		}

		return property;

	}
```
</details>

### `WGSLNodeBuilder.hasBuiltin(name: string, shaderStage: string): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if the given builtin is defined in the given shader stage.
	 *
	 * @param {string} name - The builtin name.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {boolean} Whether the given builtin is defined in the given shader stage or not.
	 */
```

**Parameters:**

- **`name`** `string`
- **`shaderStage`** `string`

**Returns:** `boolean`

**Calls:**

- `this.builtins[ shaderStage ].has`

<details><summary>Code</summary>

```typescript
hasBuiltin( name, shaderStage = this.shaderStage ) {

		return ( this.builtins[ shaderStage ] !== undefined && this.builtins[ shaderStage ].has( name ) );

	}
```
</details>

### `WGSLNodeBuilder.getVertexIndex(): string`

**JSDoc:**
```typescript
/**
	 * Returns the vertex index builtin.
	 *
	 * @return {string} The vertex index.
	 */
```

**Returns:** `string`

**Calls:**

- `this.getBuiltin`

<details><summary>Code</summary>

```typescript
getVertexIndex() {

		if ( this.shaderStage === 'vertex' ) {

			return this.getBuiltin( 'vertex_index', 'vertexIndex', 'u32', 'attribute' );

		}

		return 'vertexIndex';

	}
```
</details>

### `WGSLNodeBuilder.buildFunctionCode(shaderNode: ShaderNodeInternal): string`

**JSDoc:**
```typescript
/**
	 * Builds the given shader node.
	 *
	 * @param {ShaderNodeInternal} shaderNode - The shader node.
	 * @return {string} The WGSL function code.
	 */
```

**Parameters:**

- **`shaderNode`** `ShaderNodeInternal`

**Returns:** `string`

**Calls:**

- `this.flowShaderNode`
- `parameters.push`
- `this.getType`
- `parameters.join`

**Internal Comments:**
```
// (x3)
```

<details><summary>Code</summary>

```typescript
buildFunctionCode( shaderNode ) {

		const layout = shaderNode.layout;
		const flowData = this.flowShaderNode( shaderNode );

		const parameters = [];

		for ( const input of layout.inputs ) {

			parameters.push( input.name + ' : ' + this.getType( input.type ) );

		}

		//

		let code = `fn ${ layout.name }( ${ parameters.join( ', ' ) } ) -> ${ this.getType( layout.type ) } {
${ flowData.vars }
${ flowData.code }
`;

		if ( flowData.result ) {

			code += `\treturn ${ flowData.result };\n`;

		}

		code += '\n}\n';

		//

		return code;

	}
```
</details>

### `WGSLNodeBuilder.getInstanceIndex(): string`

**JSDoc:**
```typescript
/**
	 * Returns the instance index builtin.
	 *
	 * @return {string} The instance index.
	 */
```

**Returns:** `string`

**Calls:**

- `this.getBuiltin`

<details><summary>Code</summary>

```typescript
getInstanceIndex() {

		if ( this.shaderStage === 'vertex' ) {

			return this.getBuiltin( 'instance_index', 'instanceIndex', 'u32', 'attribute' );

		}

		return 'instanceIndex';

	}
```
</details>

### `WGSLNodeBuilder.getInvocationLocalIndex(): string`

**JSDoc:**
```typescript
/**
	 * Returns the invocation local index builtin.
	 *
	 * @return {string} The invocation local index.
	 */
```

**Returns:** `string`

**Calls:**

- `this.getBuiltin`

<details><summary>Code</summary>

```typescript
getInvocationLocalIndex() {

		return this.getBuiltin( 'local_invocation_index', 'invocationLocalIndex', 'u32', 'attribute' );

	}
```
</details>

### `WGSLNodeBuilder.getSubgroupSize(): string`

**JSDoc:**
```typescript
/**
	 * Returns the subgroup size builtin.
	 *
	 * @return {string} The subgroup size.
	 */
```

**Returns:** `string`

**Calls:**

- `this.enableSubGroups`
- `this.getBuiltin`

<details><summary>Code</summary>

```typescript
getSubgroupSize() {

		this.enableSubGroups();

		return this.getBuiltin( 'subgroup_size', 'subgroupSize', 'u32', 'attribute' );

	}
```
</details>

### `WGSLNodeBuilder.getInvocationSubgroupIndex(): string`

**JSDoc:**
```typescript
/**
	 * Returns the invocation subgroup index builtin.
	 *
	 * @return {string} The invocation subgroup index.
	 */
```

**Returns:** `string`

**Calls:**

- `this.enableSubGroups`
- `this.getBuiltin`

<details><summary>Code</summary>

```typescript
getInvocationSubgroupIndex() {

		this.enableSubGroups();

		return this.getBuiltin( 'subgroup_invocation_id', 'invocationSubgroupIndex', 'u32', 'attribute' );

	}
```
</details>

### `WGSLNodeBuilder.getSubgroupIndex(): string`

**JSDoc:**
```typescript
/**
	 * Returns the subgroup index builtin.
	 *
	 * @return {string} The subgroup index.
	 */
```

**Returns:** `string`

**Calls:**

- `this.enableSubGroups`
- `this.getBuiltin`

<details><summary>Code</summary>

```typescript
getSubgroupIndex() {

		this.enableSubGroups();

		return this.getBuiltin( 'subgroup_id', 'subgroupIndex', 'u32', 'attribute' );

	}
```
</details>

### `WGSLNodeBuilder.getDrawIndex(): null`

**JSDoc:**
```typescript
/**
	 * Overwritten as a NOP since this method is intended for the WebGL 2 backend.
	 *
	 * @return {null} Null.
	 */
```

**Returns:** `null`

<details><summary>Code</summary>

```typescript
getDrawIndex() {

		return null;

	}
```
</details>

### `WGSLNodeBuilder.getFrontFacing(): string`

**JSDoc:**
```typescript
/**
	 * Returns the front facing builtin.
	 *
	 * @return {string} The front facing builtin.
	 */
```

**Returns:** `string`

**Calls:**

- `this.getBuiltin`

<details><summary>Code</summary>

```typescript
getFrontFacing() {

		return this.getBuiltin( 'front_facing', 'isFront', 'bool' );

	}
```
</details>

### `WGSLNodeBuilder.getFragCoord(): string`

**JSDoc:**
```typescript
/**
	 * Returns the frag coord builtin.
	 *
	 * @return {string} The frag coord builtin.
	 */
```

**Returns:** `string`

**Calls:**

- `this.getBuiltin`

<details><summary>Code</summary>

```typescript
getFragCoord() {

		return this.getBuiltin( 'position', 'fragCoord', 'vec4<f32>' ) + '.xy';

	}
```
</details>

### `WGSLNodeBuilder.getFragDepth(): string`

**JSDoc:**
```typescript
/**
	 * Returns the frag depth builtin.
	 *
	 * @return {string} The frag depth builtin.
	 */
```

**Returns:** `string`

**Calls:**

- `this.getBuiltin`

<details><summary>Code</summary>

```typescript
getFragDepth() {

		return 'output.' + this.getBuiltin( 'frag_depth', 'depth', 'f32', 'output' );

	}
```
</details>

### `WGSLNodeBuilder.getClipDistance(): string`

**JSDoc:**
```typescript
/**
	 * Returns the clip distances builtin.
	 *
	 * @return {string} The clip distances builtin.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getClipDistance() {

		return 'varyings.hw_clip_distances';

	}
```
</details>

### `WGSLNodeBuilder.isFlipY(): boolean`

**JSDoc:**
```typescript
/**
	 * Whether to flip texture data along its vertical axis or not.
	 *
	 * @return {boolean} Returns always `false` in context of WGSL.
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

### `WGSLNodeBuilder.enableDirective(name: string, shaderStage: string): void`

**JSDoc:**
```typescript
/**
	 * Enables the given directive for the given shader stage.
	 *
	 * @param {string} name - The directive name.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage to enable the directive for.
	 */
```

**Parameters:**

- **`name`** `string`
- **`shaderStage`** `string`

**Returns:** `void`

**Calls:**

- `stage.add`

<details><summary>Code</summary>

```typescript
enableDirective( name, shaderStage = this.shaderStage ) {

		const stage = this.directives[ shaderStage ] || ( this.directives[ shaderStage ] = new Set() );
		stage.add( name );

	}
```
</details>

### `WGSLNodeBuilder.getDirectives(shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the directives of the given shader stage as a WGSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} A WGSL snippet that enables the directives of the given stage.
	 */
```

**Parameters:**

- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `snippets.push`
- `snippets.join`

<details><summary>Code</summary>

```typescript
getDirectives( shaderStage ) {

		const snippets = [];
		const directives = this.directives[ shaderStage ];

		if ( directives !== undefined ) {

			for ( const directive of directives ) {

				snippets.push( `enable ${directive};` );

			}

		}

		return snippets.join( '\n' );

	}
```
</details>

### `WGSLNodeBuilder.enableSubGroups(): void`

**JSDoc:**
```typescript
/**
	 * Enables the 'subgroups' directive.
	 */
```

**Returns:** `void`

**Calls:**

- `this.enableDirective`

<details><summary>Code</summary>

```typescript
enableSubGroups() {

		this.enableDirective( 'subgroups' );

	}
```
</details>

### `WGSLNodeBuilder.enableSubgroupsF16(): void`

**JSDoc:**
```typescript
/**
	 * Enables the 'subgroups-f16' directive.
	 */
```

**Returns:** `void`

**Calls:**

- `this.enableDirective`

<details><summary>Code</summary>

```typescript
enableSubgroupsF16() {

		this.enableDirective( 'subgroups-f16' );

	}
```
</details>

### `WGSLNodeBuilder.enableClipDistances(): void`

**JSDoc:**
```typescript
/**
	 * Enables the 'clip_distances' directive.
	 */
```

**Returns:** `void`

**Calls:**

- `this.enableDirective`

<details><summary>Code</summary>

```typescript
enableClipDistances() {

		this.enableDirective( 'clip_distances' );

	}
```
</details>

### `WGSLNodeBuilder.enableShaderF16(): void`

**JSDoc:**
```typescript
/**
	 * Enables the 'f16' directive.
	 */
```

**Returns:** `void`

**Calls:**

- `this.enableDirective`

<details><summary>Code</summary>

```typescript
enableShaderF16() {

		this.enableDirective( 'f16' );

	}
```
</details>

### `WGSLNodeBuilder.enableDualSourceBlending(): void`

**JSDoc:**
```typescript
/**
	 * Enables the 'dual_source_blending' directive.
	 */
```

**Returns:** `void`

**Calls:**

- `this.enableDirective`

<details><summary>Code</summary>

```typescript
enableDualSourceBlending() {

		this.enableDirective( 'dual_source_blending' );

	}
```
</details>

### `WGSLNodeBuilder.enableHardwareClipping(planeCount: string): void`

**JSDoc:**
```typescript
/**
	 * Enables hardware clipping.
	 *
	 * @param {string} planeCount - The clipping plane count.
	 */
```

**Parameters:**

- **`planeCount`** `string`

**Returns:** `void`

**Calls:**

- `this.enableClipDistances`
- `this.getBuiltin`

<details><summary>Code</summary>

```typescript
enableHardwareClipping( planeCount ) {

		this.enableClipDistances();
		this.getBuiltin( 'clip_distances', 'hw_clip_distances', `array<f32, ${ planeCount } >`, 'vertex' );

	}
```
</details>

### `WGSLNodeBuilder.getBuiltins(shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the builtins of the given shader stage as a WGSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} A WGSL snippet that represents the builtins of the given stage.
	 */
```

**Parameters:**

- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `builtins.values`
- `snippets.push`
- `snippets.join`

<details><summary>Code</summary>

```typescript
getBuiltins( shaderStage ) {

		const snippets = [];
		const builtins = this.builtins[ shaderStage ];

		if ( builtins !== undefined ) {

			for ( const { name, property, type } of builtins.values() ) {

				snippets.push( `@builtin( ${name} ) ${property} : ${type}` );

			}

		}

		return snippets.join( ',\n\t' );

	}
```
</details>

### `WGSLNodeBuilder.getScopedArray(name: string, scope: string, bufferType: string, bufferCount: string): string`

**JSDoc:**
```typescript
/**
	 * This method should be used when a new scoped buffer is used in context of
	 * compute shaders. It adds the array to the internal data structure which is
	 * later used to generate the respective WGSL.
	 *
	 * @param {string} name - The array name.
	 * @param {string} scope - The scope.
	 * @param {string} bufferType - The buffer type.
	 * @param {string} bufferCount - The buffer count.
	 * @return {string} The array name.
	 */
```

**Parameters:**

- **`name`** `string`
- **`scope`** `string`
- **`bufferType`** `string`
- **`bufferCount`** `string`

**Returns:** `string`

**Calls:**

- `this.scopedArrays.has`
- `this.scopedArrays.set`

<details><summary>Code</summary>

```typescript
getScopedArray( name, scope, bufferType, bufferCount ) {

		if ( this.scopedArrays.has( name ) === false ) {

			this.scopedArrays.set( name, {
				name,
				scope,
				bufferType,
				bufferCount
			} );

		}

		return name;

	}
```
</details>

### `WGSLNodeBuilder.getScopedArrays(shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the scoped arrays of the given shader stage as a WGSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string|undefined} The WGSL snippet that defines the scoped arrays.
	 * Returns `undefined` when used in the vertex or fragment stage.
	 */
```

**Parameters:**

- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `this.scopedArrays.values`
- `this.getType`
- `snippets.push`
- `snippets.join`

<details><summary>Code</summary>

```typescript
getScopedArrays( shaderStage ) {

		if ( shaderStage !== 'compute' ) {

			return;

		}

		const snippets = [];

		for ( const { name, scope, bufferType, bufferCount } of this.scopedArrays.values() ) {

			const type = this.getType( bufferType );

			snippets.push( `var<${scope}> ${name}: array< ${type}, ${bufferCount} >;` );

		}

		return snippets.join( '\n' );

	}
```
</details>

### `WGSLNodeBuilder.getAttributes(shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the shader attributes of the given shader stage as a WGSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The WGSL snippet that defines the shader attributes.
	 */
```

**Parameters:**

- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `this.getBuiltin`
- `this.renderer.hasFeature`
- `this.enableDirective`
- `this.getBuiltins`
- `snippets.push`
- `this.getAttributesArray`
- `this.getType`
- `snippets.join`

<details><summary>Code</summary>

```typescript
getAttributes( shaderStage ) {

		const snippets = [];

		if ( shaderStage === 'compute' ) {

			this.getBuiltin( 'global_invocation_id', 'globalId', 'vec3<u32>', 'attribute' );
			this.getBuiltin( 'workgroup_id', 'workgroupId', 'vec3<u32>', 'attribute' );
			this.getBuiltin( 'local_invocation_id', 'localId', 'vec3<u32>', 'attribute' );
			this.getBuiltin( 'num_workgroups', 'numWorkgroups', 'vec3<u32>', 'attribute' );

			if ( this.renderer.hasFeature( 'subgroups' ) ) {

				this.enableDirective( 'subgroups', shaderStage );
				this.getBuiltin( 'subgroup_size', 'subgroupSize', 'u32', 'attribute' );

			}

		}

		if ( shaderStage === 'vertex' || shaderStage === 'compute' ) {

			const builtins = this.getBuiltins( 'attribute' );

			if ( builtins ) snippets.push( builtins );

			const attributes = this.getAttributesArray();

			for ( let index = 0, length = attributes.length; index < length; index ++ ) {

				const attribute = attributes[ index ];
				const name = attribute.name;
				const type = this.getType( attribute.type );

				snippets.push( `@location( ${index} ) ${ name } : ${ type }` );

			}

		}

		return snippets.join( ',\n\t' );

	}
```
</details>

### `WGSLNodeBuilder.getStructMembers(struct: StructTypeNode): string`

**JSDoc:**
```typescript
/**
	 * Returns the members of the given struct type node as a WGSL string.
	 *
	 * @param {StructTypeNode} struct - The struct type node.
	 * @return {string} The WGSL snippet that defines the struct members.
	 */
```

**Parameters:**

- **`struct`** `StructTypeNode`

**Returns:** `string`

**Calls:**

- `this.getType`
- `snippets.push`
- `this.getBuiltins`
- `snippets.join`

<details><summary>Code</summary>

```typescript
getStructMembers( struct ) {

		const snippets = [];

		for ( const member of struct.members ) {

			const prefix = struct.output ? '@location( ' + member.index + ' ) ' : '';

			let type = this.getType( member.type );

			if ( member.atomic ) {

				type = 'atomic< ' + type + ' >';

			}

			snippets.push( `\t${ prefix + member.name } : ${ type }` );

		}

		if ( struct.output ) {

			snippets.push( `\t${ this.getBuiltins( 'output' ) }` );

		}

		return snippets.join( ',\n' );

	}
```
</details>

### `WGSLNodeBuilder.getStructs(shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the structs of the given shader stage as a WGSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The WGSL snippet that defines the structs.
	 */
```

**Parameters:**

- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `this.getStructMembers`
- `snippets.push`
- `snippets.join`

<details><summary>Code</summary>

```typescript
getStructs( shaderStage ) {

		let result = '';

		const structs = this.structs[ shaderStage ];

		if ( structs.length > 0 ) {

			const snippets = [];

			for ( const struct of structs ) {

				let snippet = `struct ${ struct.name } {\n`;
				snippet += this.getStructMembers( struct );
				snippet += '\n};';

				snippets.push( snippet );

			}

			result = '\n' + snippets.join( '\n\n' ) + '\n';

		}

		return result;

	}
```
</details>

### `WGSLNodeBuilder.getVar(type: string, name: string, count: number): string`

**JSDoc:**
```typescript
/**
	 * Returns a WGSL string representing a variable.
	 *
	 * @param {string} type - The variable's type.
	 * @param {string} name - The variable's name.
	 * @param {?number} [count=null] - The array length.
	 * @return {string} The WGSL snippet that defines a variable.
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

		let snippet = `var ${ name } : `;

		if ( count !== null ) {

			snippet += this.generateArrayDeclaration( type, count );

		} else {

			snippet += this.getType( type );

		}

		return snippet;

	}
```
</details>

### `WGSLNodeBuilder.getVars(shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the variables of the given shader stage as a WGSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The WGSL snippet that defines the variables.
	 */
```

**Parameters:**

- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `snippets.push`
- `this.getVar`
- `snippets.join`

<details><summary>Code</summary>

```typescript
getVars( shaderStage ) {

		const snippets = [];
		const vars = this.vars[ shaderStage ];

		if ( vars !== undefined ) {

			for ( const variable of vars ) {

				snippets.push( `\t${ this.getVar( variable.type, variable.name, variable.count ) };` );

			}

		}

		return `\n${ snippets.join( '\n' ) }\n`;

	}
```
</details>

### `WGSLNodeBuilder.getVaryings(shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the varyings of the given shader stage as a WGSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The WGSL snippet that defines the varyings.
	 */
```

**Parameters:**

- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `this.getBuiltin`
- `/^(int|uint|ivec|uvec)/.test`
- `snippets.push`
- `this.getType`
- `vars.includes`
- `vars.push`
- `this.getBuiltins`
- `snippets.join`
- `this._getWGSLStruct`

<details><summary>Code</summary>

```typescript
getVaryings( shaderStage ) {

		const snippets = [];

		if ( shaderStage === 'vertex' ) {

			this.getBuiltin( 'position', 'Vertex', 'vec4<f32>', 'vertex' );

		}

		if ( shaderStage === 'vertex' || shaderStage === 'fragment' ) {

			const varyings = this.varyings;
			const vars = this.vars[ shaderStage ];

			for ( let index = 0; index < varyings.length; index ++ ) {

				const varying = varyings[ index ];

				if ( varying.needsInterpolation ) {

					let attributesSnippet = `@location( ${index} )`;

					if ( varying.interpolationType ) {

						const samplingSnippet = varying.interpolationSampling !== null ? `, ${ varying.interpolationSampling } )` : ' )';

						attributesSnippet += ` @interpolate( ${ varying.interpolationType }${ samplingSnippet }`;

						// Otherwise, optimize interpolation when sensible

					} else if ( /^(int|uint|ivec|uvec)/.test( varying.type ) ) {

						attributesSnippet += ` @interpolate( ${ this.renderer.backend.compatibilityMode ? 'flat, either' : 'flat' } )`;

					}

					snippets.push( `${ attributesSnippet } ${ varying.name } : ${ this.getType( varying.type ) }` );

				} else if ( shaderStage === 'vertex' && vars.includes( varying ) === false ) {

					vars.push( varying );

				}

			}

		}

		const builtins = this.getBuiltins( shaderStage );

		if ( builtins ) snippets.push( builtins );

		const code = snippets.join( ',\n\t' );

		return shaderStage === 'vertex' ? this._getWGSLStruct( 'VaryingsStruct', '\t' + code ) : code;

	}
```
</details>

### `WGSLNodeBuilder.isCustomStruct(nodeUniform: any): boolean`

**Parameters:**

- **`nodeUniform`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
isCustomStruct( nodeUniform ) {

		const attribute = nodeUniform.value;
		const bufferNode = nodeUniform.node;

		const isAttributeStructType = ( attribute.isBufferAttribute || attribute.isInstancedBufferAttribute ) && bufferNode.structTypeNode !== null;

		const isStructArray =
			( bufferNode.value && bufferNode.value.array ) &&
			( typeof bufferNode.value.itemSize === 'number' && bufferNode.value.array.length > bufferNode.value.itemSize );

		return isAttributeStructType && ! isStructArray;

	}
```
</details>

### `WGSLNodeBuilder.getUniforms(shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the uniforms of the given shader stage as a WGSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The WGSL snippet that defines the uniforms.
	 */
```

**Parameters:**

- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `this.isUnfilterable`
- `this.isSampleCompare`
- `bindingSnippets.push`
- `this.renderer.backend.utils.getTextureSampleData`
- `getFormat (from ../utils/WebGPUTextureUtils.js)`
- `this.getStorageAccess`
- `this.getComponentTypeFromTexture( texture ).charAt`
- `this.getType`
- `bufferNode.getNodeType`
- `this.isCustomStruct`
- `bufferSnippets.push`
- `this._getWGSLStructBinding`
- `this.getVectorType`
- `group.snippets.push`
- `structSnippets.push`
- `group.snippets.join`
- `bindingSnippets.join`
- `bufferSnippets.join`
- `structSnippets.join`

<details><summary>Code</summary>

```typescript
getUniforms( shaderStage ) {

		const uniforms = this.uniforms[ shaderStage ];

		const bindingSnippets = [];
		const bufferSnippets = [];
		const structSnippets = [];
		const uniformGroups = {};

		for ( const uniform of uniforms ) {

			const groupName = uniform.groupNode.name;
			const uniformIndexes = this.bindingsIndexes[ groupName ];

			if ( uniform.type === 'texture' || uniform.type === 'cubeTexture' || uniform.type === 'storageTexture' || uniform.type === 'texture3D' ) {

				const texture = uniform.node.value;

				if ( this.isUnfilterable( texture ) === false && uniform.node.isStorageTextureNode !== true ) {

					if ( this.isSampleCompare( texture ) ) {

						bindingSnippets.push( `@binding( ${ uniformIndexes.binding ++ } ) @group( ${ uniformIndexes.group } ) var ${ uniform.name }_sampler : sampler_comparison;` );

					} else {

						bindingSnippets.push( `@binding( ${ uniformIndexes.binding ++ } ) @group( ${ uniformIndexes.group } ) var ${ uniform.name }_sampler : sampler;` );

					}

				}

				let textureType;

				let multisampled = '';

				const { primarySamples } = this.renderer.backend.utils.getTextureSampleData( texture );

				if ( primarySamples > 1 ) {

					multisampled = '_multisampled';

				}

				if ( texture.isCubeTexture === true ) {

					textureType = 'texture_cube<f32>';

				} else if ( texture.isDepthTexture === true ) {

					if ( this.renderer.backend.compatibilityMode && texture.compareFunction === null ) {

						textureType = `texture${ multisampled }_2d<f32>`;

					} else {

						textureType = `texture_depth${ multisampled }_2d${ texture.isArrayTexture === true ? '_array' : '' }`;

					}

				} else if ( uniform.node.isStorageTextureNode === true ) {

					const format = getFormat( texture );
					const access = this.getStorageAccess( uniform.node, shaderStage );

					const is3D = uniform.node.value.is3DTexture;
					const isArrayTexture = uniform.node.value.isArrayTexture;

					const dimension = is3D ? '3d' : `2d${ isArrayTexture ? '_array' : '' }`;

					textureType = `texture_storage_${ dimension }<${ format }, ${ access }>`;

				} else if ( texture.isArrayTexture === true || texture.isDataArrayTexture === true || texture.isCompressedArrayTexture === true ) {

					textureType = 'texture_2d_array<f32>';

				} else if ( texture.is3DTexture === true || texture.isData3DTexture === true ) {

					textureType = 'texture_3d<f32>';

				} else {

					const componentPrefix = this.getComponentTypeFromTexture( texture ).charAt( 0 );

					textureType = `texture${ multisampled }_2d<${ componentPrefix }32>`;

				}

				bindingSnippets.push( `@binding( ${ uniformIndexes.binding ++ } ) @group( ${ uniformIndexes.group } ) var ${ uniform.name } : ${ textureType };` );

			} else if ( uniform.type === 'buffer' || uniform.type === 'storageBuffer' || uniform.type === 'indirectStorageBuffer' ) {

				const bufferNode = uniform.node;
				const bufferType = this.getType( bufferNode.getNodeType( this ) );
				const bufferCount = bufferNode.bufferCount;
				const bufferCountSnippet = bufferCount > 0 && uniform.type === 'buffer' ? ', ' + bufferCount : '';
				const bufferAccessMode = bufferNode.isStorageBufferNode ? `storage, ${ this.getStorageAccess( bufferNode, shaderStage ) }` : 'uniform';

				if ( this.isCustomStruct( uniform ) ) {

					bufferSnippets.push( `@binding( ${ uniformIndexes.binding ++ } ) @group( ${ uniformIndexes.group } ) var<${ bufferAccessMode }> ${ uniform.name } : ${ bufferType };` );

				} else {

					const bufferTypeSnippet = bufferNode.isAtomic ? `atomic<${ bufferType }>` : `${ bufferType }`;
					const bufferSnippet = `\tvalue : array< ${ bufferTypeSnippet }${ bufferCountSnippet } >`;

					bufferSnippets.push( this._getWGSLStructBinding( uniform.name, bufferSnippet, bufferAccessMode, uniformIndexes.binding ++, uniformIndexes.group ) );

				}

			} else {

				const vectorType = this.getType( this.getVectorType( uniform.type ) );
				const groupName = uniform.groupNode.name;

				const group = uniformGroups[ groupName ] || ( uniformGroups[ groupName ] = {
					index: uniformIndexes.binding ++,
					id: uniformIndexes.group,
					snippets: []
				} );

				group.snippets.push( `\t${ uniform.name } : ${ vectorType }` );

			}

		}

		for ( const name in uniformGroups ) {

			const group = uniformGroups[ name ];

			structSnippets.push( this._getWGSLStructBinding( name, group.snippets.join( ',\n' ), 'uniform', group.index, group.id ) );

		}

		let code = bindingSnippets.join( '\n' );
		code += bufferSnippets.join( '\n' );
		code += structSnippets.join( '\n' );

		return code;

	}
```
</details>

### `WGSLNodeBuilder.buildCode(): void`

**JSDoc:**
```typescript
/**
	 * Controls the code build of the shader stages.
	 */
```

**Returns:** `void`

**Calls:**

- `this.sortBindingGroups`
- `this.getUniforms`
- `this.getAttributes`
- `this.getVaryings`
- `this.getStructs`
- `this.getVars`
- `this.getCodes`
- `this.getDirectives`
- `this.getScopedArrays`
- `this.getFlowData`
- `outputNode.getNodeType`
- `this.getBuiltins`
- `this._getWGSLStruct`
- `this._getWGSLVertexCode`
- `this._getWGSLFragmentCode`
- `this._getWGSLComputeCode`

**Internal Comments:**
```
// (x2)
// Early strictly validated in computeNode (x2)
```

<details><summary>Code</summary>

```typescript
buildCode() {

		const shadersData = this.material !== null ? { fragment: {}, vertex: {} } : { compute: {} };

		this.sortBindingGroups();

		for ( const shaderStage in shadersData ) {

			this.shaderStage = shaderStage;

			const stageData = shadersData[ shaderStage ];
			stageData.uniforms = this.getUniforms( shaderStage );
			stageData.attributes = this.getAttributes( shaderStage );
			stageData.varyings = this.getVaryings( shaderStage );
			stageData.structs = this.getStructs( shaderStage );
			stageData.vars = this.getVars( shaderStage );
			stageData.codes = this.getCodes( shaderStage );
			stageData.directives = this.getDirectives( shaderStage );
			stageData.scopedArrays = this.getScopedArrays( shaderStage );

			//

			let flow = '// code\n\n';
			flow += this.flowCode[ shaderStage ];

			const flowNodes = this.flowNodes[ shaderStage ];
			const mainNode = flowNodes[ flowNodes.length - 1 ];

			const outputNode = mainNode.outputNode;
			const isOutputStruct = ( outputNode !== undefined && outputNode.isOutputStructNode === true );

			for ( const node of flowNodes ) {

				const flowSlotData = this.getFlowData( node/*, shaderStage*/ );
				const slotName = node.name;

				if ( slotName ) {

					if ( flow.length > 0 ) flow += '\n';

					flow += `\t// flow -> ${ slotName }\n`;

				}

				flow += `${ flowSlotData.code }\n\t`;

				if ( node === mainNode && shaderStage !== 'compute' ) {

					flow += '// result\n\n\t';

					if ( shaderStage === 'vertex' ) {

						flow += `varyings.Vertex = ${ flowSlotData.result };`;

					} else if ( shaderStage === 'fragment' ) {

						if ( isOutputStruct ) {

							stageData.returnType = outputNode.getNodeType( this );
							stageData.structs += 'var<private> output : ' + stageData.returnType + ';';

							flow += `return ${ flowSlotData.result };`;

						} else {

							let structSnippet = '\t@location(0) color: vec4<f32>';

							const builtins = this.getBuiltins( 'output' );

							if ( builtins ) structSnippet += ',\n\t' + builtins;

							stageData.returnType = 'OutputStruct';
							stageData.structs += this._getWGSLStruct( 'OutputStruct', structSnippet );
							stageData.structs += '\nvar<private> output : OutputStruct;';

							flow += `output.color = ${ flowSlotData.result };\n\n\treturn output;`;

						}

					}

				}

			}

			stageData.flow = flow;

		}

		this.shaderStage = null;

		if ( this.material !== null ) {

			this.vertexShader = this._getWGSLVertexCode( shadersData.vertex );
			this.fragmentShader = this._getWGSLFragmentCode( shadersData.fragment );

		} else {

			// Early strictly validated in computeNode

			const workgroupSize = this.object.workgroupSize;

			this.computeShader = this._getWGSLComputeCode( shadersData.compute, workgroupSize );

		}

	}
```
</details>

### `WGSLNodeBuilder.getMethod(method: string, output: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the native shader method name for a given generic name.
	 *
	 * @param {string} method - The method name to resolve.
	 * @param {?string} [output=null] - An optional output.
	 * @return {string} The resolved WGSL method name.
	 */
```

**Parameters:**

- **`method`** `string`
- **`output`** `string`

**Returns:** `string`

**Calls:**

- `this._getWGSLMethod`

<details><summary>Code</summary>

```typescript
getMethod( method, output = null ) {

		let wgslMethod;

		if ( output !== null ) {

			wgslMethod = this._getWGSLMethod( method + '_' + output );

		}

		if ( wgslMethod === undefined ) {

			wgslMethod = this._getWGSLMethod( method );

		}

		return wgslMethod || method;

	}
```
</details>

### `WGSLNodeBuilder.getTernary(condSnippet: string, ifSnippet: string, elseSnippet: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the native snippet for a ternary operation.
	 *
	 * @param {string} condSnippet - The condition determining which expression gets resolved.
	 * @param {string} ifSnippet - The expression to resolve to if the condition is true.
	 * @param {string} elseSnippet - The expression to resolve to if the condition is false.
	 * @return {string} The resolved method name.
	 */
```

**Parameters:**

- **`condSnippet`** `string`
- **`ifSnippet`** `string`
- **`elseSnippet`** `string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getTernary( condSnippet, ifSnippet, elseSnippet ) {

		return `select( ${elseSnippet}, ${ifSnippet}, ${condSnippet} )`;

	}
```
</details>

### `WGSLNodeBuilder.getType(type: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the WGSL type of the given node data type.
	 *
	 * @param {string} type - The node data type.
	 * @return {string} The WGSL type.
	 */
```

**Parameters:**

- **`type`** `string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getType( type ) {

		return wgslTypeLib[ type ] || type;

	}
```
</details>

### `WGSLNodeBuilder.isAvailable(name: string): boolean`

**JSDoc:**
```typescript
/**
	 * Whether the requested feature is available or not.
	 *
	 * @param {string} name - The requested feature.
	 * @return {boolean} Whether the requested feature is supported or not.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `boolean`

**Calls:**

- `this.renderer.hasFeature`

<details><summary>Code</summary>

```typescript
isAvailable( name ) {

		let result = supports[ name ];

		if ( result === undefined ) {

			if ( name === 'float32Filterable' ) {

				result = this.renderer.hasFeature( 'float32-filterable' );

			} else if ( name === 'clipDistance' ) {

				result = this.renderer.hasFeature( 'clip-distances' );

			}

			supports[ name ] = result;

		}

		return result;

	}
```
</details>

### `WGSLNodeBuilder._getWGSLMethod(method: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the native shader method name for a given generic name.
	 *
	 * @private
	 * @param {string} method - The method name to resolve.
	 * @return {string} The resolved WGSL method name.
	 */
```

**Parameters:**

- **`method`** `string`

**Returns:** `string`

**Calls:**

- `this._include`

<details><summary>Code</summary>

```typescript
_getWGSLMethod( method ) {

		if ( wgslPolyfill[ method ] !== undefined ) {

			this._include( method );

		}

		return wgslMethods[ method ];

	}
```
</details>

### `WGSLNodeBuilder._include(name: string): CodeNode`

**JSDoc:**
```typescript
/**
	 * Includes the given method name into the current
	 * function node.
	 *
	 * @private
	 * @param {string} name - The method name to include.
	 * @return {CodeNode} The respective code node.
	 */
```

**Parameters:**

- **`name`** `string`

**Returns:** `CodeNode`

**Calls:**

- `codeNode.build`
- `this.currentFunctionNode.includes.push`

<details><summary>Code</summary>

```typescript
_include( name ) {

		const codeNode = wgslPolyfill[ name ];
		codeNode.build( this );

		if ( this.currentFunctionNode !== null ) {

			this.currentFunctionNode.includes.push( codeNode );

		}

		return codeNode;

	}
```
</details>

### `WGSLNodeBuilder._getWGSLVertexCode(shaderData: any): string`

**JSDoc:**
```typescript
/**
	 * Returns a WGSL vertex shader based on the given shader data.
	 *
	 * @private
	 * @param {Object} shaderData - The shader data.
	 * @return {string} The vertex shader.
	 */
```

**Parameters:**

- **`shaderData`** `any`

**Returns:** `string`

**Calls:**

- `this.getSignature`

<details><summary>Code</summary>

```typescript
_getWGSLVertexCode( shaderData ) {

		return `${ this.getSignature() }
// directives
${shaderData.directives}

// structs
${shaderData.structs}

// uniforms
${shaderData.uniforms}

// varyings
${shaderData.varyings}
var<private> varyings : VaryingsStruct;

// codes
${shaderData.codes}

@vertex
fn main( ${shaderData.attributes} ) -> VaryingsStruct {

	// vars
	${shaderData.vars}

	// flow
	${shaderData.flow}

	return varyings;

}
`;

	}
```
</details>

### `WGSLNodeBuilder._getWGSLFragmentCode(shaderData: any): string`

**JSDoc:**
```typescript
/**
	 * Returns a WGSL fragment shader based on the given shader data.
	 *
	 * @private
	 * @param {Object} shaderData - The shader data.
	 * @return {string} The vertex shader.
	 */
```

**Parameters:**

- **`shaderData`** `any`

**Returns:** `string`

**Calls:**

- `this.getSignature`

<details><summary>Code</summary>

```typescript
_getWGSLFragmentCode( shaderData ) {

		return `${ this.getSignature() }
// global
${ diagnostics }

// structs
${shaderData.structs}

// uniforms
${shaderData.uniforms}

// codes
${shaderData.codes}

@fragment
fn main( ${shaderData.varyings} ) -> ${shaderData.returnType} {

	// vars
	${shaderData.vars}

	// flow
	${shaderData.flow}

}
`;

	}
```
</details>

### `WGSLNodeBuilder._getWGSLComputeCode(shaderData: any, workgroupSize: string): string`

**JSDoc:**
```typescript
/**
	 * Returns a WGSL compute shader based on the given shader data.
	 *
	 * @private
	 * @param {Object} shaderData - The shader data.
	 * @param {string} workgroupSize - The workgroup size.
	 * @return {string} The vertex shader.
	 */
```

**Parameters:**

- **`shaderData`** `any`
- **`workgroupSize`** `string`

**Returns:** `string`

**Calls:**

- `this.getSignature`

<details><summary>Code</summary>

```typescript
_getWGSLComputeCode( shaderData, workgroupSize ) {

		const [ workgroupSizeX, workgroupSizeY, workgroupSizeZ ] = workgroupSize;

		return `${ this.getSignature() }
// directives
${ shaderData.directives }

// system
var<private> instanceIndex : u32;

// locals
${ shaderData.scopedArrays }

// structs
${ shaderData.structs }

// uniforms
${ shaderData.uniforms }

// codes
${ shaderData.codes }

@compute @workgroup_size( ${ workgroupSizeX }, ${ workgroupSizeY }, ${ workgroupSizeZ } )
fn main( ${ shaderData.attributes } ) {

	// system
	instanceIndex = globalId.x
		+ globalId.y * ( ${ workgroupSizeX } * numWorkgroups.x )
		+ globalId.z * ( ${ workgroupSizeX } * numWorkgroups.x ) * ( ${ workgroupSizeY } * numWorkgroups.y );

	// vars
	${ shaderData.vars }

	// flow
	${ shaderData.flow }

}
`;

	}
```
</details>

### `WGSLNodeBuilder._getWGSLStruct(name: string, vars: string): string`

**JSDoc:**
```typescript
/**
	 * Returns a WGSL struct based on the given name and variables.
	 *
	 * @private
	 * @param {string} name - The struct name.
	 * @param {string} vars - The struct variables.
	 * @return {string} The WGSL snippet representing a struct.
	 */
```

**Parameters:**

- **`name`** `string`
- **`vars`** `string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
_getWGSLStruct( name, vars ) {

		return `
struct ${name} {
${vars}
};`;

	}
```
</details>

### `WGSLNodeBuilder._getWGSLStructBinding(name: string, vars: string, access: string, binding: number, group: number): string`

**JSDoc:**
```typescript
/**
	 * Returns a WGSL struct binding.
	 *
	 * @private
	 * @param {string} name - The struct name.
	 * @param {string} vars - The struct variables.
	 * @param {string} access - The access.
	 * @param {number} [binding=0] - The binding index.
	 * @param {number} [group=0] - The group index.
	 * @return {string} The WGSL snippet representing a struct binding.
	 */
```

**Parameters:**

- **`name`** `string`
- **`vars`** `string`
- **`access`** `string`
- **`binding`** `number`
- **`group`** `number`

**Returns:** `string`

**Calls:**

- `this._getWGSLStruct`

<details><summary>Code</summary>

```typescript
_getWGSLStructBinding( name, vars, access, binding = 0, group = 0 ) {

		const structName = name + 'Struct';
		const structSnippet = this._getWGSLStruct( structName, vars );

		return `${structSnippet}
@binding( ${ binding } ) @group( ${ group } )
var<${access}> ${ name } : ${ structName };`;

	}
```
</details>

### `addWrapSnippet(wrap: any, axis: any): void`

**Parameters:**

- **`wrap`** `any`
- **`axis`** `any`

**Returns:** `void`

**Calls:**

- `includes.push`
- `console.warn`

<details><summary>Code</summary>

```typescript
( wrap, axis ) => {

				if ( wrap === RepeatWrapping ) {

					includes.push( wgslPolyfill.repeatWrapping_float );

					code += `\t\ttsl_repeatWrapping_float( coord.${ axis } )`;

				} else if ( wrap === ClampToEdgeWrapping ) {

					includes.push( wgslPolyfill.clampWrapping_float );

					code += `\t\ttsl_clampWrapping_float( coord.${ axis } )`;

				} else if ( wrap === MirroredRepeatWrapping ) {

					includes.push( wgslPolyfill.mirrorWrapping_float );

					code += `\t\ttsl_mirrorWrapping_float( coord.${ axis } )`;

				} else {

					code += `\t\tcoord.${ axis }`;

					console.warn( `WebGPURenderer: Unsupported texture wrap type "${ wrap }" for vertex shader.` );

				}

			}
```
</details>


---

## Classes

### `WGSLNodeBuilder`

<details><summary>Class Code</summary>

```ts
class WGSLNodeBuilder extends NodeBuilder {

	/**
	 * Constructs a new WGSL node builder renderer.
	 *
	 * @param {Object3D} object - The 3D object.
	 * @param {Renderer} renderer - The renderer.
	 */
	constructor( object, renderer ) {

		super( object, renderer, new WGSLNodeParser() );

		/**
		 * A dictionary that holds for each shader stage ('vertex', 'fragment', 'compute')
		 * another dictionary which manages UBOs per group ('render','frame','object').
		 *
		 * @type {Object<string,Object<string,NodeUniformsGroup>>}
		 */
		this.uniformGroups = {};

		/**
		 * A dictionary that holds for each shader stage a Map of builtins.
		 *
		 * @type {Object<string,Map<string,Object>>}
		 */
		this.builtins = {};

		/**
		 * A dictionary that holds for each shader stage a Set of directives.
		 *
		 * @type {Object<string,Set<string>>}
		 */
		this.directives = {};

		/**
		 * A map for managing scope arrays. Only relevant for when using
		 * {@link WorkgroupInfoNode} in context of compute shaders.
		 *
		 * @type {Map<string,Object>}
		 */
		this.scopedArrays = new Map();

	}

	/**
	 * Generates the WGSL snippet for sampled textures.
	 *
	 * @private
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The WGSL snippet.
	 */
	_generateTextureSample( texture, textureProperty, uvSnippet, depthSnippet, shaderStage = this.shaderStage ) {

		if ( shaderStage === 'fragment' ) {

			if ( depthSnippet ) {

				return `textureSample( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ depthSnippet } )`;

			} else {

				return `textureSample( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet } )`;

			}

		} else {

			return this.generateTextureSampleLevel( texture, textureProperty, uvSnippet, '0', depthSnippet );

		}

	}

	/**
	 * Generates the WGSL snippet when sampling textures with explicit mip level.
	 *
	 * @private
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {string} levelSnippet - A WGSL snippet that represents the mip level, with level 0 containing a full size version of the texture.
	 * @param {string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @return {string} The WGSL snippet.
	 */
	generateTextureSampleLevel( texture, textureProperty, uvSnippet, levelSnippet, depthSnippet ) {

		if ( this.isUnfilterable( texture ) === false ) {

			return `textureSampleLevel( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ levelSnippet } )`;

		} else if ( this.isFilteredTexture( texture ) ) {

			return this.generateFilteredTexture( texture, textureProperty, uvSnippet, levelSnippet );

		} else {

			return this.generateTextureLod( texture, textureProperty, uvSnippet, depthSnippet, levelSnippet );

		}

	}

	/**
	 * Generates a wrap function used in context of textures.
	 *
	 * @param {Texture} texture - The texture to generate the function for.
	 * @return {string} The name of the generated function.
	 */
	generateWrapFunction( texture ) {

		const functionName = `tsl_coord_${ wrapNames[ texture.wrapS ] }S_${ wrapNames[ texture.wrapT ] }_${ texture.isData3DTexture ? '3d' : '2d' }T`;

		let nodeCode = wgslCodeCache[ functionName ];

		if ( nodeCode === undefined ) {

			const includes = [];

			// For 3D textures, use vec3f; for texture arrays, keep vec2f since array index is separate
			const coordType = texture.isData3DTexture ? 'vec3f' : 'vec2f';
			let code = `fn ${ functionName }( coord : ${ coordType } ) -> ${ coordType } {\n\n\treturn ${ coordType }(\n`;

			const addWrapSnippet = ( wrap, axis ) => {

				if ( wrap === RepeatWrapping ) {

					includes.push( wgslPolyfill.repeatWrapping_float );

					code += `\t\ttsl_repeatWrapping_float( coord.${ axis } )`;

				} else if ( wrap === ClampToEdgeWrapping ) {

					includes.push( wgslPolyfill.clampWrapping_float );

					code += `\t\ttsl_clampWrapping_float( coord.${ axis } )`;

				} else if ( wrap === MirroredRepeatWrapping ) {

					includes.push( wgslPolyfill.mirrorWrapping_float );

					code += `\t\ttsl_mirrorWrapping_float( coord.${ axis } )`;

				} else {

					code += `\t\tcoord.${ axis }`;

					console.warn( `WebGPURenderer: Unsupported texture wrap type "${ wrap }" for vertex shader.` );

				}

			};

			addWrapSnippet( texture.wrapS, 'x' );

			code += ',\n';

			addWrapSnippet( texture.wrapT, 'y' );

			if ( texture.isData3DTexture ) {

				code += ',\n';
				addWrapSnippet( texture.wrapR, 'z' );

			}

			code += '\n\t);\n\n}\n';

			wgslCodeCache[ functionName ] = nodeCode = new CodeNode( code, includes );

		}

		nodeCode.build( this );

		return functionName;

	}

	/**
	 * Generates the array declaration string.
	 *
	 * @param {string} type - The type.
	 * @param {?number} [count] - The count.
	 * @return {string} The generated value as a shader string.
	 */
	generateArrayDeclaration( type, count ) {

		return `array< ${ this.getType( type ) }, ${ count } >`;

	}

	/**
	 * Generates a WGSL variable that holds the texture dimension of the given texture.
	 * It also returns information about the number of layers (elements) of an arrayed
	 * texture as well as the cube face count of cube textures.
	 *
	 * @param {Texture} texture - The texture to generate the function for.
	 * @param {string} textureProperty - The name of the video texture uniform in the shader.
	 * @param {string} levelSnippet - A WGSL snippet that represents the mip level, with level 0 containing a full size version of the texture.
	 * @return {string} The name of the dimension variable.
	 */
	generateTextureDimension( texture, textureProperty, levelSnippet ) {

		const textureData = this.getDataFromNode( texture, this.shaderStage, this.globalCache );

		if ( textureData.dimensionsSnippet === undefined ) textureData.dimensionsSnippet = {};

		let textureDimensionNode = textureData.dimensionsSnippet[ levelSnippet ];

		if ( textureData.dimensionsSnippet[ levelSnippet ] === undefined ) {

			let textureDimensionsParams;
			let dimensionType;

			const { primarySamples } = this.renderer.backend.utils.getTextureSampleData( texture );
			const isMultisampled = primarySamples > 1;

			if ( texture.isData3DTexture ) {

				dimensionType = 'vec3<u32>';

			} else {

				// Regular 2D textures, depth textures, etc.
				dimensionType = 'vec2<u32>';

			}

			// Build parameters string based on texture type and multisampling
			if ( isMultisampled || texture.isStorageTexture ) {

				textureDimensionsParams = textureProperty;

			} else {

				textureDimensionsParams = `${textureProperty}${levelSnippet ? `, u32( ${ levelSnippet } )` : ''}`;

			}

			textureDimensionNode = new VarNode( new ExpressionNode( `textureDimensions( ${ textureDimensionsParams } )`, dimensionType ) );

			textureData.dimensionsSnippet[ levelSnippet ] = textureDimensionNode;

			if ( texture.isArrayTexture || texture.isDataArrayTexture || texture.isData3DTexture ) {

				textureData.arrayLayerCount = new VarNode(
					new ExpressionNode(
						`textureNumLayers(${textureProperty})`,
						'u32'
					)
				);

			}

			// For cube textures, we know it's always 6 faces
			if ( texture.isTextureCube ) {

				textureData.cubeFaceCount = new VarNode(
					new ExpressionNode( '6u', 'u32' )
				);

			}

		}

		return textureDimensionNode.build( this );

	}

	/**
	 * Generates the WGSL snippet for a manual filtered texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {string} levelSnippet - A WGSL snippet that represents the mip level, with level 0 containing a full size version of the texture.
	 * @return {string} The WGSL snippet.
	 */
	generateFilteredTexture( texture, textureProperty, uvSnippet, levelSnippet = '0u' ) {

		this._include( 'biquadraticTexture' );

		const wrapFunction = this.generateWrapFunction( texture );
		const textureDimension = this.generateTextureDimension( texture, textureProperty, levelSnippet );

		return `tsl_biquadraticTexture( ${ textureProperty }, ${ wrapFunction }( ${ uvSnippet } ), ${ textureDimension }, u32( ${ levelSnippet } ) )`;

	}

	/**
	 * Generates the WGSL snippet for a texture lookup with explicit level-of-detail.
	 * Since it's a lookup, no sampling or filtering is applied.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [levelSnippet='0u'] - A WGSL snippet that represents the mip level, with level 0 containing a full size version of the texture.
	 * @return {string} The WGSL snippet.
	 */
	generateTextureLod( texture, textureProperty, uvSnippet, depthSnippet, levelSnippet = '0u' ) {

		const wrapFunction = this.generateWrapFunction( texture );
		const textureDimension = this.generateTextureDimension( texture, textureProperty, levelSnippet );

		const vecType = texture.isData3DTexture ? 'vec3' : 'vec2';
		const coordSnippet = `${ vecType }<u32>( ${ wrapFunction }( ${ uvSnippet } ) * ${ vecType }<f32>( ${ textureDimension } ) )`;

		return this.generateTextureLoad( texture, textureProperty, coordSnippet, depthSnippet, levelSnippet );

	}

	/**
	 * Generates the WGSL snippet that reads a single texel from a texture without sampling or filtering.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvIndexSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [levelSnippet='0u'] - A WGSL snippet that represents the mip level, with level 0 containing a full size version of the texture.
	 * @return {string} The WGSL snippet.
	 */
	generateTextureLoad( texture, textureProperty, uvIndexSnippet, depthSnippet, levelSnippet = '0u' ) {

		let snippet;

		if ( depthSnippet ) {

			snippet = `textureLoad( ${ textureProperty }, ${ uvIndexSnippet }, ${ depthSnippet }, u32( ${ levelSnippet } ) )`;

		} else {

			snippet = `textureLoad( ${ textureProperty }, ${ uvIndexSnippet }, u32( ${ levelSnippet } ) )`;

			if ( this.renderer.backend.compatibilityMode && texture.isDepthTexture ) {

				snippet += '.x';

			}

		}

		return snippet;

	}

	/**
	 * Generates the WGSL snippet that writes a single texel to a texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvIndexSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} valueSnippet - A WGSL snippet that represent the new texel value.
	 * @return {string} The WGSL snippet.
	 */
	generateTextureStore( texture, textureProperty, uvIndexSnippet, depthSnippet, valueSnippet ) {

		let snippet;

		if ( depthSnippet ) {

			snippet = `textureStore( ${ textureProperty }, ${ uvIndexSnippet }, ${ depthSnippet }, ${ valueSnippet } )`;

		} else {

			snippet = `textureStore( ${ textureProperty }, ${ uvIndexSnippet }, ${ valueSnippet } )`;

		}

		return snippet;

	}

	/**
	 * Returns `true` if the sampled values of the given texture should be compared against a reference value.
	 *
	 * @param {Texture} texture - The texture.
	 * @return {boolean} Whether the sampled values of the given texture should be compared against a reference value or not.
	 */
	isSampleCompare( texture ) {

		return texture.isDepthTexture === true && texture.compareFunction !== null;

	}

	/**
	 * Returns `true` if the given texture is unfilterable.
	 *
	 * @param {Texture} texture - The texture.
	 * @return {boolean} Whether the given texture is unfilterable or not.
	 */
	isUnfilterable( texture ) {

		return this.getComponentTypeFromTexture( texture ) !== 'float' ||
			( ! this.isAvailable( 'float32Filterable' ) && texture.isDataTexture === true && texture.type === FloatType ) ||
			( this.isSampleCompare( texture ) === false && texture.minFilter === NearestFilter && texture.magFilter === NearestFilter ) ||
			this.renderer.backend.utils.getTextureSampleData( texture ).primarySamples > 1;

	}

	/**
	 * Generates the WGSL snippet for sampling/loading the given texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The WGSL snippet.
	 */
	generateTexture( texture, textureProperty, uvSnippet, depthSnippet, shaderStage = this.shaderStage ) {

		let snippet = null;

		if ( this.isUnfilterable( texture ) ) {

			snippet = this.generateTextureLod( texture, textureProperty, uvSnippet, depthSnippet, '0', shaderStage );

		} else {

			snippet = this._generateTextureSample( texture, textureProperty, uvSnippet, depthSnippet, shaderStage );

		}

		return snippet;

	}

	/**
	 * Generates the WGSL snippet for sampling/loading the given texture using explicit gradients.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {Array<string>} gradSnippet - An array holding both gradient WGSL snippets.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The WGSL snippet.
	 */
	generateTextureGrad( texture, textureProperty, uvSnippet, gradSnippet, depthSnippet, shaderStage = this.shaderStage ) {

		if ( shaderStage === 'fragment' ) {

			// TODO handle i32 or u32 --> uvSnippet, array_index: A, ddx, ddy
			return `textureSampleGrad( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet },  ${ gradSnippet[ 0 ] }, ${ gradSnippet[ 1 ] } )`;

		} else {

			console.error( `WebGPURenderer: THREE.TextureNode.gradient() does not support ${ shaderStage } shader.` );

		}

	}

	/**
	 * Generates the WGSL snippet for sampling a depth texture and comparing the sampled depth values
	 * against a reference value.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {string} compareSnippet -  A WGSL snippet that represents the reference value.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The WGSL snippet.
	 */
	generateTextureCompare( texture, textureProperty, uvSnippet, compareSnippet, depthSnippet, shaderStage = this.shaderStage ) {

		if ( shaderStage === 'fragment' ) {

			if ( texture.isDepthTexture === true && texture.isArrayTexture === true ) {

				return `textureSampleCompare( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ depthSnippet }, ${ compareSnippet } )`;

			}

			return `textureSampleCompare( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ compareSnippet } )`;

		} else {

			console.error( `WebGPURenderer: THREE.DepthTexture.compareFunction() does not support ${ shaderStage } shader.` );

		}

	}

	/**
	 * Generates the WGSL snippet when sampling textures with explicit mip level.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {string} levelSnippet - A WGSL snippet that represents the mip level, with level 0 containing a full size version of the texture.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The WGSL snippet.
	 */
	generateTextureLevel( texture, textureProperty, uvSnippet, levelSnippet, depthSnippet ) {

		if ( this.isUnfilterable( texture ) === false ) {

			return `textureSampleLevel( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ levelSnippet } )`;

		} else if ( this.isFilteredTexture( texture ) ) {

			return this.generateFilteredTexture( texture, textureProperty, uvSnippet, levelSnippet );

		} else {

			return this.generateTextureLod( texture, textureProperty, uvSnippet, depthSnippet, levelSnippet );

		}

	}

	/**
	 * Generates the WGSL snippet when sampling textures with a bias to the mip level.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A WGSL snippet that represents texture coordinates used for sampling.
	 * @param {string} biasSnippet - A WGSL snippet that represents the bias to apply to the mip level before sampling.
	 * @param {?string} depthSnippet - A WGSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The WGSL snippet.
	 */
	generateTextureBias( texture, textureProperty, uvSnippet, biasSnippet, depthSnippet, shaderStage = this.shaderStage ) {

		if ( shaderStage === 'fragment' ) {

			return `textureSampleBias( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ biasSnippet } )`;

		} else {

			console.error( `WebGPURenderer: THREE.TextureNode.biasNode does not support ${ shaderStage } shader.` );

		}

	}

	/**
	 * Returns a WGSL snippet that represents the property name of the given node.
	 *
	 * @param {Node} node - The node.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The property name.
	 */
	getPropertyName( node, shaderStage = this.shaderStage ) {

		if ( node.isNodeVarying === true && node.needsInterpolation === true ) {

			if ( shaderStage === 'vertex' ) {

				return `varyings.${ node.name }`;

			}

		} else if ( node.isNodeUniform === true ) {

			const name = node.name;
			const type = node.type;

			if ( type === 'texture' || type === 'cubeTexture' || type === 'storageTexture' || type === 'texture3D' ) {

				return name;

			} else if ( type === 'buffer' || type === 'storageBuffer' || type === 'indirectStorageBuffer' ) {

				if ( this.isCustomStruct( node ) ) {

					return name;

				}

				return name + '.value';

			} else {

				return node.groupNode.name + '.' + name;

			}

		}

		return super.getPropertyName( node );

	}

	/**
	 * Returns the output struct name.
	 *
	 * @return {string} The name of the output struct.
	 */
	getOutputStructName() {

		return 'output';

	}

	/**
	 * Returns the native shader operator name for a given generic name.
	 *
	 * @param {string} op - The operator name to resolve.
	 * @return {?string} The resolved operator name.
	 */
	getFunctionOperator( op ) {

		const fnOp = wgslFnOpLib[ op ];

		if ( fnOp !== undefined ) {

			this._include( fnOp );

			return fnOp;

		}

		return null;

	}

	/**
	 * Returns the node access for the given node and shader stage.
	 *
	 * @param {StorageTextureNode|StorageBufferNode} node - The storage node.
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The node access.
	 */
	getNodeAccess( node, shaderStage ) {

		if ( shaderStage !== 'compute' ) {

			if ( node.isAtomic === true ) {

				console.warn( 'WebGPURenderer: Atomic operations are only supported in compute shaders.' );

				return NodeAccess.READ_WRITE;

			}

			return NodeAccess.READ_ONLY;

		}

		return node.access;

	}

	/**
	 * Returns A WGSL snippet representing the storage access.
	 *
	 * @param {StorageTextureNode|StorageBufferNode} node - The storage node.
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The WGSL snippet representing the storage access.
	 */
	getStorageAccess( node, shaderStage ) {

		return accessNames[ this.getNodeAccess( node, shaderStage ) ];

	}

	/**
	 * This method is one of the more important ones since it's responsible
	 * for generating a matching binding instance for the given uniform node.
	 *
	 * These bindings are later used in the renderer to create bind groups
	 * and layouts.
	 *
	 * @param {UniformNode} node - The uniform node.
	 * @param {string} type - The node data type.
	 * @param {string} shaderStage - The shader stage.
	 * @param {?string} [name=null] - An optional uniform name.
	 * @return {NodeUniform} The node uniform object.
	 */
	getUniformFromNode( node, type, shaderStage, name = null ) {

		const uniformNode = super.getUniformFromNode( node, type, shaderStage, name );
		const nodeData = this.getDataFromNode( node, shaderStage, this.globalCache );

		if ( nodeData.uniformGPU === undefined ) {

			let uniformGPU;

			const group = node.groupNode;
			const groupName = group.name;

			const bindings = this.getBindGroupArray( groupName, shaderStage );

			if ( type === 'texture' || type === 'cubeTexture' || type === 'storageTexture' || type === 'texture3D' ) {

				let texture = null;

				const access = this.getNodeAccess( node, shaderStage );

				if ( type === 'texture' || type === 'storageTexture' ) {

					if ( node.value.is3DTexture === true ) {

						texture = new NodeSampledTexture3D( uniformNode.name, uniformNode.node, group, access );

					} else {

						texture = new NodeSampledTexture( uniformNode.name, uniformNode.node, group, access );

					}

				} else if ( type === 'cubeTexture' ) {

					texture = new NodeSampledCubeTexture( uniformNode.name, uniformNode.node, group, access );

				} else if ( type === 'texture3D' ) {

					texture = new NodeSampledTexture3D( uniformNode.name, uniformNode.node, group, access );

				}

				texture.store = node.isStorageTextureNode === true;
				texture.setVisibility( gpuShaderStageLib[ shaderStage ] );

				if ( this.isUnfilterable( node.value ) === false && texture.store === false ) {

					const sampler = new NodeSampler( `${ uniformNode.name }_sampler`, uniformNode.node, group );
					sampler.setVisibility( gpuShaderStageLib[ shaderStage ] );

					bindings.push( sampler, texture );

					uniformGPU = [ sampler, texture ];

				} else {

					bindings.push( texture );

					uniformGPU = [ texture ];

				}

			} else if ( type === 'buffer' || type === 'storageBuffer' || type === 'indirectStorageBuffer' ) {

				const bufferClass = type === 'buffer' ? NodeUniformBuffer : NodeStorageBuffer;

				const buffer = new bufferClass( node, group );
				buffer.setVisibility( gpuShaderStageLib[ shaderStage ] );

				bindings.push( buffer );

				uniformGPU = buffer;

				uniformNode.name = name ? name : 'NodeBuffer_' + uniformNode.id;

			} else {

				const uniformsStage = this.uniformGroups[ shaderStage ] || ( this.uniformGroups[ shaderStage ] = {} );

				let uniformsGroup = uniformsStage[ groupName ];

				if ( uniformsGroup === undefined ) {

					uniformsGroup = new NodeUniformsGroup( groupName, group );
					uniformsGroup.setVisibility( gpuShaderStageLib[ shaderStage ] );

					uniformsStage[ groupName ] = uniformsGroup;

					bindings.push( uniformsGroup );

				}

				uniformGPU = this.getNodeUniform( uniformNode, type );

				uniformsGroup.addUniform( uniformGPU );

			}

			nodeData.uniformGPU = uniformGPU;

		}

		return uniformNode;

	}

	/**
	 * This method should be used whenever builtins are required in nodes.
	 * The internal builtins data structure will make sure builtins are
	 * defined in the WGSL source.
	 *
	 * @param {string} name - The builtin name.
	 * @param {string} property - The property name.
	 * @param {string} type - The node data type.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The property name.
	 */
	getBuiltin( name, property, type, shaderStage = this.shaderStage ) {

		const map = this.builtins[ shaderStage ] || ( this.builtins[ shaderStage ] = new Map() );

		if ( map.has( name ) === false ) {

			map.set( name, {
				name,
				property,
				type
			} );

		}

		return property;

	}

	/**
	 * Returns `true` if the given builtin is defined in the given shader stage.
	 *
	 * @param {string} name - The builtin name.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {boolean} Whether the given builtin is defined in the given shader stage or not.
	 */
	hasBuiltin( name, shaderStage = this.shaderStage ) {

		return ( this.builtins[ shaderStage ] !== undefined && this.builtins[ shaderStage ].has( name ) );

	}

	/**
	 * Returns the vertex index builtin.
	 *
	 * @return {string} The vertex index.
	 */
	getVertexIndex() {

		if ( this.shaderStage === 'vertex' ) {

			return this.getBuiltin( 'vertex_index', 'vertexIndex', 'u32', 'attribute' );

		}

		return 'vertexIndex';

	}

	/**
	 * Builds the given shader node.
	 *
	 * @param {ShaderNodeInternal} shaderNode - The shader node.
	 * @return {string} The WGSL function code.
	 */
	buildFunctionCode( shaderNode ) {

		const layout = shaderNode.layout;
		const flowData = this.flowShaderNode( shaderNode );

		const parameters = [];

		for ( const input of layout.inputs ) {

			parameters.push( input.name + ' : ' + this.getType( input.type ) );

		}

		//

		let code = `fn ${ layout.name }( ${ parameters.join( ', ' ) } ) -> ${ this.getType( layout.type ) } {
${ flowData.vars }
${ flowData.code }
`;

		if ( flowData.result ) {

			code += `\treturn ${ flowData.result };\n`;

		}

		code += '\n}\n';

		//

		return code;

	}

	/**
	 * Returns the instance index builtin.
	 *
	 * @return {string} The instance index.
	 */
	getInstanceIndex() {

		if ( this.shaderStage === 'vertex' ) {

			return this.getBuiltin( 'instance_index', 'instanceIndex', 'u32', 'attribute' );

		}

		return 'instanceIndex';

	}

	/**
	 * Returns the invocation local index builtin.
	 *
	 * @return {string} The invocation local index.
	 */
	getInvocationLocalIndex() {

		return this.getBuiltin( 'local_invocation_index', 'invocationLocalIndex', 'u32', 'attribute' );

	}

	/**
	 * Returns the subgroup size builtin.
	 *
	 * @return {string} The subgroup size.
	 */
	getSubgroupSize() {

		this.enableSubGroups();

		return this.getBuiltin( 'subgroup_size', 'subgroupSize', 'u32', 'attribute' );

	}

	/**
	 * Returns the invocation subgroup index builtin.
	 *
	 * @return {string} The invocation subgroup index.
	 */
	getInvocationSubgroupIndex() {

		this.enableSubGroups();

		return this.getBuiltin( 'subgroup_invocation_id', 'invocationSubgroupIndex', 'u32', 'attribute' );

	}

	/**
	 * Returns the subgroup index builtin.
	 *
	 * @return {string} The subgroup index.
	 */
	getSubgroupIndex() {

		this.enableSubGroups();

		return this.getBuiltin( 'subgroup_id', 'subgroupIndex', 'u32', 'attribute' );

	}

	/**
	 * Overwritten as a NOP since this method is intended for the WebGL 2 backend.
	 *
	 * @return {null} Null.
	 */
	getDrawIndex() {

		return null;

	}

	/**
	 * Returns the front facing builtin.
	 *
	 * @return {string} The front facing builtin.
	 */
	getFrontFacing() {

		return this.getBuiltin( 'front_facing', 'isFront', 'bool' );

	}

	/**
	 * Returns the frag coord builtin.
	 *
	 * @return {string} The frag coord builtin.
	 */
	getFragCoord() {

		return this.getBuiltin( 'position', 'fragCoord', 'vec4<f32>' ) + '.xy';

	}

	/**
	 * Returns the frag depth builtin.
	 *
	 * @return {string} The frag depth builtin.
	 */
	getFragDepth() {

		return 'output.' + this.getBuiltin( 'frag_depth', 'depth', 'f32', 'output' );

	}

	/**
	 * Returns the clip distances builtin.
	 *
	 * @return {string} The clip distances builtin.
	 */
	getClipDistance() {

		return 'varyings.hw_clip_distances';

	}

	/**
	 * Whether to flip texture data along its vertical axis or not.
	 *
	 * @return {boolean} Returns always `false` in context of WGSL.
	 */
	isFlipY() {

		return false;

	}

	/**
	 * Enables the given directive for the given shader stage.
	 *
	 * @param {string} name - The directive name.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage to enable the directive for.
	 */
	enableDirective( name, shaderStage = this.shaderStage ) {

		const stage = this.directives[ shaderStage ] || ( this.directives[ shaderStage ] = new Set() );
		stage.add( name );

	}

	/**
	 * Returns the directives of the given shader stage as a WGSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} A WGSL snippet that enables the directives of the given stage.
	 */
	getDirectives( shaderStage ) {

		const snippets = [];
		const directives = this.directives[ shaderStage ];

		if ( directives !== undefined ) {

			for ( const directive of directives ) {

				snippets.push( `enable ${directive};` );

			}

		}

		return snippets.join( '\n' );

	}

	/**
	 * Enables the 'subgroups' directive.
	 */
	enableSubGroups() {

		this.enableDirective( 'subgroups' );

	}

	/**
	 * Enables the 'subgroups-f16' directive.
	 */
	enableSubgroupsF16() {

		this.enableDirective( 'subgroups-f16' );

	}

	/**
	 * Enables the 'clip_distances' directive.
	 */
	enableClipDistances() {

		this.enableDirective( 'clip_distances' );

	}

	/**
	 * Enables the 'f16' directive.
	 */
	enableShaderF16() {

		this.enableDirective( 'f16' );

	}

	/**
	 * Enables the 'dual_source_blending' directive.
	 */
	enableDualSourceBlending() {

		this.enableDirective( 'dual_source_blending' );

	}

	/**
	 * Enables hardware clipping.
	 *
	 * @param {string} planeCount - The clipping plane count.
	 */
	enableHardwareClipping( planeCount ) {

		this.enableClipDistances();
		this.getBuiltin( 'clip_distances', 'hw_clip_distances', `array<f32, ${ planeCount } >`, 'vertex' );

	}

	/**
	 * Returns the builtins of the given shader stage as a WGSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} A WGSL snippet that represents the builtins of the given stage.
	 */
	getBuiltins( shaderStage ) {

		const snippets = [];
		const builtins = this.builtins[ shaderStage ];

		if ( builtins !== undefined ) {

			for ( const { name, property, type } of builtins.values() ) {

				snippets.push( `@builtin( ${name} ) ${property} : ${type}` );

			}

		}

		return snippets.join( ',\n\t' );

	}

	/**
	 * This method should be used when a new scoped buffer is used in context of
	 * compute shaders. It adds the array to the internal data structure which is
	 * later used to generate the respective WGSL.
	 *
	 * @param {string} name - The array name.
	 * @param {string} scope - The scope.
	 * @param {string} bufferType - The buffer type.
	 * @param {string} bufferCount - The buffer count.
	 * @return {string} The array name.
	 */
	getScopedArray( name, scope, bufferType, bufferCount ) {

		if ( this.scopedArrays.has( name ) === false ) {

			this.scopedArrays.set( name, {
				name,
				scope,
				bufferType,
				bufferCount
			} );

		}

		return name;

	}

	/**
	 * Returns the scoped arrays of the given shader stage as a WGSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string|undefined} The WGSL snippet that defines the scoped arrays.
	 * Returns `undefined` when used in the vertex or fragment stage.
	 */
	getScopedArrays( shaderStage ) {

		if ( shaderStage !== 'compute' ) {

			return;

		}

		const snippets = [];

		for ( const { name, scope, bufferType, bufferCount } of this.scopedArrays.values() ) {

			const type = this.getType( bufferType );

			snippets.push( `var<${scope}> ${name}: array< ${type}, ${bufferCount} >;` );

		}

		return snippets.join( '\n' );

	}

	/**
	 * Returns the shader attributes of the given shader stage as a WGSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The WGSL snippet that defines the shader attributes.
	 */
	getAttributes( shaderStage ) {

		const snippets = [];

		if ( shaderStage === 'compute' ) {

			this.getBuiltin( 'global_invocation_id', 'globalId', 'vec3<u32>', 'attribute' );
			this.getBuiltin( 'workgroup_id', 'workgroupId', 'vec3<u32>', 'attribute' );
			this.getBuiltin( 'local_invocation_id', 'localId', 'vec3<u32>', 'attribute' );
			this.getBuiltin( 'num_workgroups', 'numWorkgroups', 'vec3<u32>', 'attribute' );

			if ( this.renderer.hasFeature( 'subgroups' ) ) {

				this.enableDirective( 'subgroups', shaderStage );
				this.getBuiltin( 'subgroup_size', 'subgroupSize', 'u32', 'attribute' );

			}

		}

		if ( shaderStage === 'vertex' || shaderStage === 'compute' ) {

			const builtins = this.getBuiltins( 'attribute' );

			if ( builtins ) snippets.push( builtins );

			const attributes = this.getAttributesArray();

			for ( let index = 0, length = attributes.length; index < length; index ++ ) {

				const attribute = attributes[ index ];
				const name = attribute.name;
				const type = this.getType( attribute.type );

				snippets.push( `@location( ${index} ) ${ name } : ${ type }` );

			}

		}

		return snippets.join( ',\n\t' );

	}

	/**
	 * Returns the members of the given struct type node as a WGSL string.
	 *
	 * @param {StructTypeNode} struct - The struct type node.
	 * @return {string} The WGSL snippet that defines the struct members.
	 */
	getStructMembers( struct ) {

		const snippets = [];

		for ( const member of struct.members ) {

			const prefix = struct.output ? '@location( ' + member.index + ' ) ' : '';

			let type = this.getType( member.type );

			if ( member.atomic ) {

				type = 'atomic< ' + type + ' >';

			}

			snippets.push( `\t${ prefix + member.name } : ${ type }` );

		}

		if ( struct.output ) {

			snippets.push( `\t${ this.getBuiltins( 'output' ) }` );

		}

		return snippets.join( ',\n' );

	}

	/**
	 * Returns the structs of the given shader stage as a WGSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The WGSL snippet that defines the structs.
	 */
	getStructs( shaderStage ) {

		let result = '';

		const structs = this.structs[ shaderStage ];

		if ( structs.length > 0 ) {

			const snippets = [];

			for ( const struct of structs ) {

				let snippet = `struct ${ struct.name } {\n`;
				snippet += this.getStructMembers( struct );
				snippet += '\n};';

				snippets.push( snippet );

			}

			result = '\n' + snippets.join( '\n\n' ) + '\n';

		}

		return result;

	}

	/**
	 * Returns a WGSL string representing a variable.
	 *
	 * @param {string} type - The variable's type.
	 * @param {string} name - The variable's name.
	 * @param {?number} [count=null] - The array length.
	 * @return {string} The WGSL snippet that defines a variable.
	 */
	getVar( type, name, count = null ) {

		let snippet = `var ${ name } : `;

		if ( count !== null ) {

			snippet += this.generateArrayDeclaration( type, count );

		} else {

			snippet += this.getType( type );

		}

		return snippet;

	}

	/**
	 * Returns the variables of the given shader stage as a WGSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The WGSL snippet that defines the variables.
	 */
	getVars( shaderStage ) {

		const snippets = [];
		const vars = this.vars[ shaderStage ];

		if ( vars !== undefined ) {

			for ( const variable of vars ) {

				snippets.push( `\t${ this.getVar( variable.type, variable.name, variable.count ) };` );

			}

		}

		return `\n${ snippets.join( '\n' ) }\n`;

	}

	/**
	 * Returns the varyings of the given shader stage as a WGSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The WGSL snippet that defines the varyings.
	 */
	getVaryings( shaderStage ) {

		const snippets = [];

		if ( shaderStage === 'vertex' ) {

			this.getBuiltin( 'position', 'Vertex', 'vec4<f32>', 'vertex' );

		}

		if ( shaderStage === 'vertex' || shaderStage === 'fragment' ) {

			const varyings = this.varyings;
			const vars = this.vars[ shaderStage ];

			for ( let index = 0; index < varyings.length; index ++ ) {

				const varying = varyings[ index ];

				if ( varying.needsInterpolation ) {

					let attributesSnippet = `@location( ${index} )`;

					if ( varying.interpolationType ) {

						const samplingSnippet = varying.interpolationSampling !== null ? `, ${ varying.interpolationSampling } )` : ' )';

						attributesSnippet += ` @interpolate( ${ varying.interpolationType }${ samplingSnippet }`;

						// Otherwise, optimize interpolation when sensible

					} else if ( /^(int|uint|ivec|uvec)/.test( varying.type ) ) {

						attributesSnippet += ` @interpolate( ${ this.renderer.backend.compatibilityMode ? 'flat, either' : 'flat' } )`;

					}

					snippets.push( `${ attributesSnippet } ${ varying.name } : ${ this.getType( varying.type ) }` );

				} else if ( shaderStage === 'vertex' && vars.includes( varying ) === false ) {

					vars.push( varying );

				}

			}

		}

		const builtins = this.getBuiltins( shaderStage );

		if ( builtins ) snippets.push( builtins );

		const code = snippets.join( ',\n\t' );

		return shaderStage === 'vertex' ? this._getWGSLStruct( 'VaryingsStruct', '\t' + code ) : code;

	}

	isCustomStruct( nodeUniform ) {

		const attribute = nodeUniform.value;
		const bufferNode = nodeUniform.node;

		const isAttributeStructType = ( attribute.isBufferAttribute || attribute.isInstancedBufferAttribute ) && bufferNode.structTypeNode !== null;

		const isStructArray =
			( bufferNode.value && bufferNode.value.array ) &&
			( typeof bufferNode.value.itemSize === 'number' && bufferNode.value.array.length > bufferNode.value.itemSize );

		return isAttributeStructType && ! isStructArray;

	}

	/**
	 * Returns the uniforms of the given shader stage as a WGSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The WGSL snippet that defines the uniforms.
	 */
	getUniforms( shaderStage ) {

		const uniforms = this.uniforms[ shaderStage ];

		const bindingSnippets = [];
		const bufferSnippets = [];
		const structSnippets = [];
		const uniformGroups = {};

		for ( const uniform of uniforms ) {

			const groupName = uniform.groupNode.name;
			const uniformIndexes = this.bindingsIndexes[ groupName ];

			if ( uniform.type === 'texture' || uniform.type === 'cubeTexture' || uniform.type === 'storageTexture' || uniform.type === 'texture3D' ) {

				const texture = uniform.node.value;

				if ( this.isUnfilterable( texture ) === false && uniform.node.isStorageTextureNode !== true ) {

					if ( this.isSampleCompare( texture ) ) {

						bindingSnippets.push( `@binding( ${ uniformIndexes.binding ++ } ) @group( ${ uniformIndexes.group } ) var ${ uniform.name }_sampler : sampler_comparison;` );

					} else {

						bindingSnippets.push( `@binding( ${ uniformIndexes.binding ++ } ) @group( ${ uniformIndexes.group } ) var ${ uniform.name }_sampler : sampler;` );

					}

				}

				let textureType;

				let multisampled = '';

				const { primarySamples } = this.renderer.backend.utils.getTextureSampleData( texture );

				if ( primarySamples > 1 ) {

					multisampled = '_multisampled';

				}

				if ( texture.isCubeTexture === true ) {

					textureType = 'texture_cube<f32>';

				} else if ( texture.isDepthTexture === true ) {

					if ( this.renderer.backend.compatibilityMode && texture.compareFunction === null ) {

						textureType = `texture${ multisampled }_2d<f32>`;

					} else {

						textureType = `texture_depth${ multisampled }_2d${ texture.isArrayTexture === true ? '_array' : '' }`;

					}

				} else if ( uniform.node.isStorageTextureNode === true ) {

					const format = getFormat( texture );
					const access = this.getStorageAccess( uniform.node, shaderStage );

					const is3D = uniform.node.value.is3DTexture;
					const isArrayTexture = uniform.node.value.isArrayTexture;

					const dimension = is3D ? '3d' : `2d${ isArrayTexture ? '_array' : '' }`;

					textureType = `texture_storage_${ dimension }<${ format }, ${ access }>`;

				} else if ( texture.isArrayTexture === true || texture.isDataArrayTexture === true || texture.isCompressedArrayTexture === true ) {

					textureType = 'texture_2d_array<f32>';

				} else if ( texture.is3DTexture === true || texture.isData3DTexture === true ) {

					textureType = 'texture_3d<f32>';

				} else {

					const componentPrefix = this.getComponentTypeFromTexture( texture ).charAt( 0 );

					textureType = `texture${ multisampled }_2d<${ componentPrefix }32>`;

				}

				bindingSnippets.push( `@binding( ${ uniformIndexes.binding ++ } ) @group( ${ uniformIndexes.group } ) var ${ uniform.name } : ${ textureType };` );

			} else if ( uniform.type === 'buffer' || uniform.type === 'storageBuffer' || uniform.type === 'indirectStorageBuffer' ) {

				const bufferNode = uniform.node;
				const bufferType = this.getType( bufferNode.getNodeType( this ) );
				const bufferCount = bufferNode.bufferCount;
				const bufferCountSnippet = bufferCount > 0 && uniform.type === 'buffer' ? ', ' + bufferCount : '';
				const bufferAccessMode = bufferNode.isStorageBufferNode ? `storage, ${ this.getStorageAccess( bufferNode, shaderStage ) }` : 'uniform';

				if ( this.isCustomStruct( uniform ) ) {

					bufferSnippets.push( `@binding( ${ uniformIndexes.binding ++ } ) @group( ${ uniformIndexes.group } ) var<${ bufferAccessMode }> ${ uniform.name } : ${ bufferType };` );

				} else {

					const bufferTypeSnippet = bufferNode.isAtomic ? `atomic<${ bufferType }>` : `${ bufferType }`;
					const bufferSnippet = `\tvalue : array< ${ bufferTypeSnippet }${ bufferCountSnippet } >`;

					bufferSnippets.push( this._getWGSLStructBinding( uniform.name, bufferSnippet, bufferAccessMode, uniformIndexes.binding ++, uniformIndexes.group ) );

				}

			} else {

				const vectorType = this.getType( this.getVectorType( uniform.type ) );
				const groupName = uniform.groupNode.name;

				const group = uniformGroups[ groupName ] || ( uniformGroups[ groupName ] = {
					index: uniformIndexes.binding ++,
					id: uniformIndexes.group,
					snippets: []
				} );

				group.snippets.push( `\t${ uniform.name } : ${ vectorType }` );

			}

		}

		for ( const name in uniformGroups ) {

			const group = uniformGroups[ name ];

			structSnippets.push( this._getWGSLStructBinding( name, group.snippets.join( ',\n' ), 'uniform', group.index, group.id ) );

		}

		let code = bindingSnippets.join( '\n' );
		code += bufferSnippets.join( '\n' );
		code += structSnippets.join( '\n' );

		return code;

	}

	/**
	 * Controls the code build of the shader stages.
	 */
	buildCode() {

		const shadersData = this.material !== null ? { fragment: {}, vertex: {} } : { compute: {} };

		this.sortBindingGroups();

		for ( const shaderStage in shadersData ) {

			this.shaderStage = shaderStage;

			const stageData = shadersData[ shaderStage ];
			stageData.uniforms = this.getUniforms( shaderStage );
			stageData.attributes = this.getAttributes( shaderStage );
			stageData.varyings = this.getVaryings( shaderStage );
			stageData.structs = this.getStructs( shaderStage );
			stageData.vars = this.getVars( shaderStage );
			stageData.codes = this.getCodes( shaderStage );
			stageData.directives = this.getDirectives( shaderStage );
			stageData.scopedArrays = this.getScopedArrays( shaderStage );

			//

			let flow = '// code\n\n';
			flow += this.flowCode[ shaderStage ];

			const flowNodes = this.flowNodes[ shaderStage ];
			const mainNode = flowNodes[ flowNodes.length - 1 ];

			const outputNode = mainNode.outputNode;
			const isOutputStruct = ( outputNode !== undefined && outputNode.isOutputStructNode === true );

			for ( const node of flowNodes ) {

				const flowSlotData = this.getFlowData( node/*, shaderStage*/ );
				const slotName = node.name;

				if ( slotName ) {

					if ( flow.length > 0 ) flow += '\n';

					flow += `\t// flow -> ${ slotName }\n`;

				}

				flow += `${ flowSlotData.code }\n\t`;

				if ( node === mainNode && shaderStage !== 'compute' ) {

					flow += '// result\n\n\t';

					if ( shaderStage === 'vertex' ) {

						flow += `varyings.Vertex = ${ flowSlotData.result };`;

					} else if ( shaderStage === 'fragment' ) {

						if ( isOutputStruct ) {

							stageData.returnType = outputNode.getNodeType( this );
							stageData.structs += 'var<private> output : ' + stageData.returnType + ';';

							flow += `return ${ flowSlotData.result };`;

						} else {

							let structSnippet = '\t@location(0) color: vec4<f32>';

							const builtins = this.getBuiltins( 'output' );

							if ( builtins ) structSnippet += ',\n\t' + builtins;

							stageData.returnType = 'OutputStruct';
							stageData.structs += this._getWGSLStruct( 'OutputStruct', structSnippet );
							stageData.structs += '\nvar<private> output : OutputStruct;';

							flow += `output.color = ${ flowSlotData.result };\n\n\treturn output;`;

						}

					}

				}

			}

			stageData.flow = flow;

		}

		this.shaderStage = null;

		if ( this.material !== null ) {

			this.vertexShader = this._getWGSLVertexCode( shadersData.vertex );
			this.fragmentShader = this._getWGSLFragmentCode( shadersData.fragment );

		} else {

			// Early strictly validated in computeNode

			const workgroupSize = this.object.workgroupSize;

			this.computeShader = this._getWGSLComputeCode( shadersData.compute, workgroupSize );

		}

	}

	/**
	 * Returns the native shader method name for a given generic name.
	 *
	 * @param {string} method - The method name to resolve.
	 * @param {?string} [output=null] - An optional output.
	 * @return {string} The resolved WGSL method name.
	 */
	getMethod( method, output = null ) {

		let wgslMethod;

		if ( output !== null ) {

			wgslMethod = this._getWGSLMethod( method + '_' + output );

		}

		if ( wgslMethod === undefined ) {

			wgslMethod = this._getWGSLMethod( method );

		}

		return wgslMethod || method;

	}

	/**
	 * Returns the native snippet for a ternary operation.
	 *
	 * @param {string} condSnippet - The condition determining which expression gets resolved.
	 * @param {string} ifSnippet - The expression to resolve to if the condition is true.
	 * @param {string} elseSnippet - The expression to resolve to if the condition is false.
	 * @return {string} The resolved method name.
	 */
	getTernary( condSnippet, ifSnippet, elseSnippet ) {

		return `select( ${elseSnippet}, ${ifSnippet}, ${condSnippet} )`;

	}


	/**
	 * Returns the WGSL type of the given node data type.
	 *
	 * @param {string} type - The node data type.
	 * @return {string} The WGSL type.
	 */
	getType( type ) {

		return wgslTypeLib[ type ] || type;

	}

	/**
	 * Whether the requested feature is available or not.
	 *
	 * @param {string} name - The requested feature.
	 * @return {boolean} Whether the requested feature is supported or not.
	 */
	isAvailable( name ) {

		let result = supports[ name ];

		if ( result === undefined ) {

			if ( name === 'float32Filterable' ) {

				result = this.renderer.hasFeature( 'float32-filterable' );

			} else if ( name === 'clipDistance' ) {

				result = this.renderer.hasFeature( 'clip-distances' );

			}

			supports[ name ] = result;

		}

		return result;

	}

	/**
	 * Returns the native shader method name for a given generic name.
	 *
	 * @private
	 * @param {string} method - The method name to resolve.
	 * @return {string} The resolved WGSL method name.
	 */
	_getWGSLMethod( method ) {

		if ( wgslPolyfill[ method ] !== undefined ) {

			this._include( method );

		}

		return wgslMethods[ method ];

	}

	/**
	 * Includes the given method name into the current
	 * function node.
	 *
	 * @private
	 * @param {string} name - The method name to include.
	 * @return {CodeNode} The respective code node.
	 */
	_include( name ) {

		const codeNode = wgslPolyfill[ name ];
		codeNode.build( this );

		if ( this.currentFunctionNode !== null ) {

			this.currentFunctionNode.includes.push( codeNode );

		}

		return codeNode;

	}

	/**
	 * Returns a WGSL vertex shader based on the given shader data.
	 *
	 * @private
	 * @param {Object} shaderData - The shader data.
	 * @return {string} The vertex shader.
	 */
	_getWGSLVertexCode( shaderData ) {

		return `${ this.getSignature() }
// directives
${shaderData.directives}

// structs
${shaderData.structs}

// uniforms
${shaderData.uniforms}

// varyings
${shaderData.varyings}
var<private> varyings : VaryingsStruct;

// codes
${shaderData.codes}

@vertex
fn main( ${shaderData.attributes} ) -> VaryingsStruct {

	// vars
	${shaderData.vars}

	// flow
	${shaderData.flow}

	return varyings;

}
`;

	}

	/**
	 * Returns a WGSL fragment shader based on the given shader data.
	 *
	 * @private
	 * @param {Object} shaderData - The shader data.
	 * @return {string} The vertex shader.
	 */
	_getWGSLFragmentCode( shaderData ) {

		return `${ this.getSignature() }
// global
${ diagnostics }

// structs
${shaderData.structs}

// uniforms
${shaderData.uniforms}

// codes
${shaderData.codes}

@fragment
fn main( ${shaderData.varyings} ) -> ${shaderData.returnType} {

	// vars
	${shaderData.vars}

	// flow
	${shaderData.flow}

}
`;

	}

	/**
	 * Returns a WGSL compute shader based on the given shader data.
	 *
	 * @private
	 * @param {Object} shaderData - The shader data.
	 * @param {string} workgroupSize - The workgroup size.
	 * @return {string} The vertex shader.
	 */
	_getWGSLComputeCode( shaderData, workgroupSize ) {

		const [ workgroupSizeX, workgroupSizeY, workgroupSizeZ ] = workgroupSize;

		return `${ this.getSignature() }
// directives
${ shaderData.directives }

// system
var<private> instanceIndex : u32;

// locals
${ shaderData.scopedArrays }

// structs
${ shaderData.structs }

// uniforms
${ shaderData.uniforms }

// codes
${ shaderData.codes }

@compute @workgroup_size( ${ workgroupSizeX }, ${ workgroupSizeY }, ${ workgroupSizeZ } )
fn main( ${ shaderData.attributes } ) {

	// system
	instanceIndex = globalId.x
		+ globalId.y * ( ${ workgroupSizeX } * numWorkgroups.x )
		+ globalId.z * ( ${ workgroupSizeX } * numWorkgroups.x ) * ( ${ workgroupSizeY } * numWorkgroups.y );

	// vars
	${ shaderData.vars }

	// flow
	${ shaderData.flow }

}
`;

	}

	/**
	 * Returns a WGSL struct based on the given name and variables.
	 *
	 * @private
	 * @param {string} name - The struct name.
	 * @param {string} vars - The struct variables.
	 * @return {string} The WGSL snippet representing a struct.
	 */
	_getWGSLStruct( name, vars ) {

		return `
struct ${name} {
${vars}
};`;

	}

	/**
	 * Returns a WGSL struct binding.
	 *
	 * @private
	 * @param {string} name - The struct name.
	 * @param {string} vars - The struct variables.
	 * @param {string} access - The access.
	 * @param {number} [binding=0] - The binding index.
	 * @param {number} [group=0] - The group index.
	 * @return {string} The WGSL snippet representing a struct binding.
	 */
	_getWGSLStructBinding( name, vars, access, binding = 0, group = 0 ) {

		const structName = name + 'Struct';
		const structSnippet = this._getWGSLStruct( structName, vars );

		return `${structSnippet}
@binding( ${ binding } ) @group( ${ group } )
var<${access}> ${ name } : ${ structName };`;

	}

}
```
</details>

#### Methods

##### `_generateTextureSample(texture: Texture, textureProperty: string, uvSnippet: string, depthSnippet: string, shaderStage: string): string`

<details><summary>Code</summary>

```ts
_generateTextureSample( texture, textureProperty, uvSnippet, depthSnippet, shaderStage = this.shaderStage ) {

		if ( shaderStage === 'fragment' ) {

			if ( depthSnippet ) {

				return `textureSample( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ depthSnippet } )`;

			} else {

				return `textureSample( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet } )`;

			}

		} else {

			return this.generateTextureSampleLevel( texture, textureProperty, uvSnippet, '0', depthSnippet );

		}

	}
```
</details>

##### `generateTextureSampleLevel(texture: Texture, textureProperty: string, uvSnippet: string, levelSnippet: string, depthSnippet: string): string`

<details><summary>Code</summary>

```ts
generateTextureSampleLevel( texture, textureProperty, uvSnippet, levelSnippet, depthSnippet ) {

		if ( this.isUnfilterable( texture ) === false ) {

			return `textureSampleLevel( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ levelSnippet } )`;

		} else if ( this.isFilteredTexture( texture ) ) {

			return this.generateFilteredTexture( texture, textureProperty, uvSnippet, levelSnippet );

		} else {

			return this.generateTextureLod( texture, textureProperty, uvSnippet, depthSnippet, levelSnippet );

		}

	}
```
</details>

##### `generateWrapFunction(texture: Texture): string`

<details><summary>Code</summary>

```ts
generateWrapFunction( texture ) {

		const functionName = `tsl_coord_${ wrapNames[ texture.wrapS ] }S_${ wrapNames[ texture.wrapT ] }_${ texture.isData3DTexture ? '3d' : '2d' }T`;

		let nodeCode = wgslCodeCache[ functionName ];

		if ( nodeCode === undefined ) {

			const includes = [];

			// For 3D textures, use vec3f; for texture arrays, keep vec2f since array index is separate
			const coordType = texture.isData3DTexture ? 'vec3f' : 'vec2f';
			let code = `fn ${ functionName }( coord : ${ coordType } ) -> ${ coordType } {\n\n\treturn ${ coordType }(\n`;

			const addWrapSnippet = ( wrap, axis ) => {

				if ( wrap === RepeatWrapping ) {

					includes.push( wgslPolyfill.repeatWrapping_float );

					code += `\t\ttsl_repeatWrapping_float( coord.${ axis } )`;

				} else if ( wrap === ClampToEdgeWrapping ) {

					includes.push( wgslPolyfill.clampWrapping_float );

					code += `\t\ttsl_clampWrapping_float( coord.${ axis } )`;

				} else if ( wrap === MirroredRepeatWrapping ) {

					includes.push( wgslPolyfill.mirrorWrapping_float );

					code += `\t\ttsl_mirrorWrapping_float( coord.${ axis } )`;

				} else {

					code += `\t\tcoord.${ axis }`;

					console.warn( `WebGPURenderer: Unsupported texture wrap type "${ wrap }" for vertex shader.` );

				}

			};

			addWrapSnippet( texture.wrapS, 'x' );

			code += ',\n';

			addWrapSnippet( texture.wrapT, 'y' );

			if ( texture.isData3DTexture ) {

				code += ',\n';
				addWrapSnippet( texture.wrapR, 'z' );

			}

			code += '\n\t);\n\n}\n';

			wgslCodeCache[ functionName ] = nodeCode = new CodeNode( code, includes );

		}

		nodeCode.build( this );

		return functionName;

	}
```
</details>

##### `generateArrayDeclaration(type: string, count: number): string`

<details><summary>Code</summary>

```ts
generateArrayDeclaration( type, count ) {

		return `array< ${ this.getType( type ) }, ${ count } >`;

	}
```
</details>

##### `generateTextureDimension(texture: Texture, textureProperty: string, levelSnippet: string): string`

<details><summary>Code</summary>

```ts
generateTextureDimension( texture, textureProperty, levelSnippet ) {

		const textureData = this.getDataFromNode( texture, this.shaderStage, this.globalCache );

		if ( textureData.dimensionsSnippet === undefined ) textureData.dimensionsSnippet = {};

		let textureDimensionNode = textureData.dimensionsSnippet[ levelSnippet ];

		if ( textureData.dimensionsSnippet[ levelSnippet ] === undefined ) {

			let textureDimensionsParams;
			let dimensionType;

			const { primarySamples } = this.renderer.backend.utils.getTextureSampleData( texture );
			const isMultisampled = primarySamples > 1;

			if ( texture.isData3DTexture ) {

				dimensionType = 'vec3<u32>';

			} else {

				// Regular 2D textures, depth textures, etc.
				dimensionType = 'vec2<u32>';

			}

			// Build parameters string based on texture type and multisampling
			if ( isMultisampled || texture.isStorageTexture ) {

				textureDimensionsParams = textureProperty;

			} else {

				textureDimensionsParams = `${textureProperty}${levelSnippet ? `, u32( ${ levelSnippet } )` : ''}`;

			}

			textureDimensionNode = new VarNode( new ExpressionNode( `textureDimensions( ${ textureDimensionsParams } )`, dimensionType ) );

			textureData.dimensionsSnippet[ levelSnippet ] = textureDimensionNode;

			if ( texture.isArrayTexture || texture.isDataArrayTexture || texture.isData3DTexture ) {

				textureData.arrayLayerCount = new VarNode(
					new ExpressionNode(
						`textureNumLayers(${textureProperty})`,
						'u32'
					)
				);

			}

			// For cube textures, we know it's always 6 faces
			if ( texture.isTextureCube ) {

				textureData.cubeFaceCount = new VarNode(
					new ExpressionNode( '6u', 'u32' )
				);

			}

		}

		return textureDimensionNode.build( this );

	}
```
</details>

##### `generateFilteredTexture(texture: Texture, textureProperty: string, uvSnippet: string, levelSnippet: string): string`

<details><summary>Code</summary>

```ts
generateFilteredTexture( texture, textureProperty, uvSnippet, levelSnippet = '0u' ) {

		this._include( 'biquadraticTexture' );

		const wrapFunction = this.generateWrapFunction( texture );
		const textureDimension = this.generateTextureDimension( texture, textureProperty, levelSnippet );

		return `tsl_biquadraticTexture( ${ textureProperty }, ${ wrapFunction }( ${ uvSnippet } ), ${ textureDimension }, u32( ${ levelSnippet } ) )`;

	}
```
</details>

##### `generateTextureLod(texture: Texture, textureProperty: string, uvSnippet: string, depthSnippet: string, levelSnippet: string): string`

<details><summary>Code</summary>

```ts
generateTextureLod( texture, textureProperty, uvSnippet, depthSnippet, levelSnippet = '0u' ) {

		const wrapFunction = this.generateWrapFunction( texture );
		const textureDimension = this.generateTextureDimension( texture, textureProperty, levelSnippet );

		const vecType = texture.isData3DTexture ? 'vec3' : 'vec2';
		const coordSnippet = `${ vecType }<u32>( ${ wrapFunction }( ${ uvSnippet } ) * ${ vecType }<f32>( ${ textureDimension } ) )`;

		return this.generateTextureLoad( texture, textureProperty, coordSnippet, depthSnippet, levelSnippet );

	}
```
</details>

##### `generateTextureLoad(texture: Texture, textureProperty: string, uvIndexSnippet: string, depthSnippet: string, levelSnippet: string): string`

<details><summary>Code</summary>

```ts
generateTextureLoad( texture, textureProperty, uvIndexSnippet, depthSnippet, levelSnippet = '0u' ) {

		let snippet;

		if ( depthSnippet ) {

			snippet = `textureLoad( ${ textureProperty }, ${ uvIndexSnippet }, ${ depthSnippet }, u32( ${ levelSnippet } ) )`;

		} else {

			snippet = `textureLoad( ${ textureProperty }, ${ uvIndexSnippet }, u32( ${ levelSnippet } ) )`;

			if ( this.renderer.backend.compatibilityMode && texture.isDepthTexture ) {

				snippet += '.x';

			}

		}

		return snippet;

	}
```
</details>

##### `generateTextureStore(texture: Texture, textureProperty: string, uvIndexSnippet: string, depthSnippet: string, valueSnippet: string): string`

<details><summary>Code</summary>

```ts
generateTextureStore( texture, textureProperty, uvIndexSnippet, depthSnippet, valueSnippet ) {

		let snippet;

		if ( depthSnippet ) {

			snippet = `textureStore( ${ textureProperty }, ${ uvIndexSnippet }, ${ depthSnippet }, ${ valueSnippet } )`;

		} else {

			snippet = `textureStore( ${ textureProperty }, ${ uvIndexSnippet }, ${ valueSnippet } )`;

		}

		return snippet;

	}
```
</details>

##### `isSampleCompare(texture: Texture): boolean`

<details><summary>Code</summary>

```ts
isSampleCompare( texture ) {

		return texture.isDepthTexture === true && texture.compareFunction !== null;

	}
```
</details>

##### `isUnfilterable(texture: Texture): boolean`

<details><summary>Code</summary>

```ts
isUnfilterable( texture ) {

		return this.getComponentTypeFromTexture( texture ) !== 'float' ||
			( ! this.isAvailable( 'float32Filterable' ) && texture.isDataTexture === true && texture.type === FloatType ) ||
			( this.isSampleCompare( texture ) === false && texture.minFilter === NearestFilter && texture.magFilter === NearestFilter ) ||
			this.renderer.backend.utils.getTextureSampleData( texture ).primarySamples > 1;

	}
```
</details>

##### `generateTexture(texture: Texture, textureProperty: string, uvSnippet: string, depthSnippet: string, shaderStage: string): string`

<details><summary>Code</summary>

```ts
generateTexture( texture, textureProperty, uvSnippet, depthSnippet, shaderStage = this.shaderStage ) {

		let snippet = null;

		if ( this.isUnfilterable( texture ) ) {

			snippet = this.generateTextureLod( texture, textureProperty, uvSnippet, depthSnippet, '0', shaderStage );

		} else {

			snippet = this._generateTextureSample( texture, textureProperty, uvSnippet, depthSnippet, shaderStage );

		}

		return snippet;

	}
```
</details>

##### `generateTextureGrad(texture: Texture, textureProperty: string, uvSnippet: string, gradSnippet: string[], depthSnippet: string, shaderStage: string): string`

<details><summary>Code</summary>

```ts
generateTextureGrad( texture, textureProperty, uvSnippet, gradSnippet, depthSnippet, shaderStage = this.shaderStage ) {

		if ( shaderStage === 'fragment' ) {

			// TODO handle i32 or u32 --> uvSnippet, array_index: A, ddx, ddy
			return `textureSampleGrad( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet },  ${ gradSnippet[ 0 ] }, ${ gradSnippet[ 1 ] } )`;

		} else {

			console.error( `WebGPURenderer: THREE.TextureNode.gradient() does not support ${ shaderStage } shader.` );

		}

	}
```
</details>

##### `generateTextureCompare(texture: Texture, textureProperty: string, uvSnippet: string, compareSnippet: string, depthSnippet: string, shaderStage: string): string`

<details><summary>Code</summary>

```ts
generateTextureCompare( texture, textureProperty, uvSnippet, compareSnippet, depthSnippet, shaderStage = this.shaderStage ) {

		if ( shaderStage === 'fragment' ) {

			if ( texture.isDepthTexture === true && texture.isArrayTexture === true ) {

				return `textureSampleCompare( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ depthSnippet }, ${ compareSnippet } )`;

			}

			return `textureSampleCompare( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ compareSnippet } )`;

		} else {

			console.error( `WebGPURenderer: THREE.DepthTexture.compareFunction() does not support ${ shaderStage } shader.` );

		}

	}
```
</details>

##### `generateTextureLevel(texture: Texture, textureProperty: string, uvSnippet: string, levelSnippet: string, depthSnippet: string): string`

<details><summary>Code</summary>

```ts
generateTextureLevel( texture, textureProperty, uvSnippet, levelSnippet, depthSnippet ) {

		if ( this.isUnfilterable( texture ) === false ) {

			return `textureSampleLevel( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ levelSnippet } )`;

		} else if ( this.isFilteredTexture( texture ) ) {

			return this.generateFilteredTexture( texture, textureProperty, uvSnippet, levelSnippet );

		} else {

			return this.generateTextureLod( texture, textureProperty, uvSnippet, depthSnippet, levelSnippet );

		}

	}
```
</details>

##### `generateTextureBias(texture: Texture, textureProperty: string, uvSnippet: string, biasSnippet: string, depthSnippet: string, shaderStage: string): string`

<details><summary>Code</summary>

```ts
generateTextureBias( texture, textureProperty, uvSnippet, biasSnippet, depthSnippet, shaderStage = this.shaderStage ) {

		if ( shaderStage === 'fragment' ) {

			return `textureSampleBias( ${ textureProperty }, ${ textureProperty }_sampler, ${ uvSnippet }, ${ biasSnippet } )`;

		} else {

			console.error( `WebGPURenderer: THREE.TextureNode.biasNode does not support ${ shaderStage } shader.` );

		}

	}
```
</details>

##### `getPropertyName(node: Node, shaderStage: string): string`

<details><summary>Code</summary>

```ts
getPropertyName( node, shaderStage = this.shaderStage ) {

		if ( node.isNodeVarying === true && node.needsInterpolation === true ) {

			if ( shaderStage === 'vertex' ) {

				return `varyings.${ node.name }`;

			}

		} else if ( node.isNodeUniform === true ) {

			const name = node.name;
			const type = node.type;

			if ( type === 'texture' || type === 'cubeTexture' || type === 'storageTexture' || type === 'texture3D' ) {

				return name;

			} else if ( type === 'buffer' || type === 'storageBuffer' || type === 'indirectStorageBuffer' ) {

				if ( this.isCustomStruct( node ) ) {

					return name;

				}

				return name + '.value';

			} else {

				return node.groupNode.name + '.' + name;

			}

		}

		return super.getPropertyName( node );

	}
```
</details>

##### `getOutputStructName(): string`

<details><summary>Code</summary>

```ts
getOutputStructName() {

		return 'output';

	}
```
</details>

##### `getFunctionOperator(op: string): string`

<details><summary>Code</summary>

```ts
getFunctionOperator( op ) {

		const fnOp = wgslFnOpLib[ op ];

		if ( fnOp !== undefined ) {

			this._include( fnOp );

			return fnOp;

		}

		return null;

	}
```
</details>

##### `getNodeAccess(node: any, shaderStage: string): string`

<details><summary>Code</summary>

```ts
getNodeAccess( node, shaderStage ) {

		if ( shaderStage !== 'compute' ) {

			if ( node.isAtomic === true ) {

				console.warn( 'WebGPURenderer: Atomic operations are only supported in compute shaders.' );

				return NodeAccess.READ_WRITE;

			}

			return NodeAccess.READ_ONLY;

		}

		return node.access;

	}
```
</details>

##### `getStorageAccess(node: any, shaderStage: string): string`

<details><summary>Code</summary>

```ts
getStorageAccess( node, shaderStage ) {

		return accessNames[ this.getNodeAccess( node, shaderStage ) ];

	}
```
</details>

##### `getUniformFromNode(node: UniformNode, type: string, shaderStage: string, name: string): NodeUniform`

<details><summary>Code</summary>

```ts
getUniformFromNode( node, type, shaderStage, name = null ) {

		const uniformNode = super.getUniformFromNode( node, type, shaderStage, name );
		const nodeData = this.getDataFromNode( node, shaderStage, this.globalCache );

		if ( nodeData.uniformGPU === undefined ) {

			let uniformGPU;

			const group = node.groupNode;
			const groupName = group.name;

			const bindings = this.getBindGroupArray( groupName, shaderStage );

			if ( type === 'texture' || type === 'cubeTexture' || type === 'storageTexture' || type === 'texture3D' ) {

				let texture = null;

				const access = this.getNodeAccess( node, shaderStage );

				if ( type === 'texture' || type === 'storageTexture' ) {

					if ( node.value.is3DTexture === true ) {

						texture = new NodeSampledTexture3D( uniformNode.name, uniformNode.node, group, access );

					} else {

						texture = new NodeSampledTexture( uniformNode.name, uniformNode.node, group, access );

					}

				} else if ( type === 'cubeTexture' ) {

					texture = new NodeSampledCubeTexture( uniformNode.name, uniformNode.node, group, access );

				} else if ( type === 'texture3D' ) {

					texture = new NodeSampledTexture3D( uniformNode.name, uniformNode.node, group, access );

				}

				texture.store = node.isStorageTextureNode === true;
				texture.setVisibility( gpuShaderStageLib[ shaderStage ] );

				if ( this.isUnfilterable( node.value ) === false && texture.store === false ) {

					const sampler = new NodeSampler( `${ uniformNode.name }_sampler`, uniformNode.node, group );
					sampler.setVisibility( gpuShaderStageLib[ shaderStage ] );

					bindings.push( sampler, texture );

					uniformGPU = [ sampler, texture ];

				} else {

					bindings.push( texture );

					uniformGPU = [ texture ];

				}

			} else if ( type === 'buffer' || type === 'storageBuffer' || type === 'indirectStorageBuffer' ) {

				const bufferClass = type === 'buffer' ? NodeUniformBuffer : NodeStorageBuffer;

				const buffer = new bufferClass( node, group );
				buffer.setVisibility( gpuShaderStageLib[ shaderStage ] );

				bindings.push( buffer );

				uniformGPU = buffer;

				uniformNode.name = name ? name : 'NodeBuffer_' + uniformNode.id;

			} else {

				const uniformsStage = this.uniformGroups[ shaderStage ] || ( this.uniformGroups[ shaderStage ] = {} );

				let uniformsGroup = uniformsStage[ groupName ];

				if ( uniformsGroup === undefined ) {

					uniformsGroup = new NodeUniformsGroup( groupName, group );
					uniformsGroup.setVisibility( gpuShaderStageLib[ shaderStage ] );

					uniformsStage[ groupName ] = uniformsGroup;

					bindings.push( uniformsGroup );

				}

				uniformGPU = this.getNodeUniform( uniformNode, type );

				uniformsGroup.addUniform( uniformGPU );

			}

			nodeData.uniformGPU = uniformGPU;

		}

		return uniformNode;

	}
```
</details>

##### `getBuiltin(name: string, property: string, type: string, shaderStage: string): string`

<details><summary>Code</summary>

```ts
getBuiltin( name, property, type, shaderStage = this.shaderStage ) {

		const map = this.builtins[ shaderStage ] || ( this.builtins[ shaderStage ] = new Map() );

		if ( map.has( name ) === false ) {

			map.set( name, {
				name,
				property,
				type
			} );

		}

		return property;

	}
```
</details>

##### `hasBuiltin(name: string, shaderStage: string): boolean`

<details><summary>Code</summary>

```ts
hasBuiltin( name, shaderStage = this.shaderStage ) {

		return ( this.builtins[ shaderStage ] !== undefined && this.builtins[ shaderStage ].has( name ) );

	}
```
</details>

##### `getVertexIndex(): string`

<details><summary>Code</summary>

```ts
getVertexIndex() {

		if ( this.shaderStage === 'vertex' ) {

			return this.getBuiltin( 'vertex_index', 'vertexIndex', 'u32', 'attribute' );

		}

		return 'vertexIndex';

	}
```
</details>

##### `buildFunctionCode(shaderNode: ShaderNodeInternal): string`

<details><summary>Code</summary>

```ts
buildFunctionCode( shaderNode ) {

		const layout = shaderNode.layout;
		const flowData = this.flowShaderNode( shaderNode );

		const parameters = [];

		for ( const input of layout.inputs ) {

			parameters.push( input.name + ' : ' + this.getType( input.type ) );

		}

		//

		let code = `fn ${ layout.name }( ${ parameters.join( ', ' ) } ) -> ${ this.getType( layout.type ) } {
${ flowData.vars }
${ flowData.code }
`;

		if ( flowData.result ) {

			code += `\treturn ${ flowData.result };\n`;

		}

		code += '\n}\n';

		//

		return code;

	}
```
</details>

##### `getInstanceIndex(): string`

<details><summary>Code</summary>

```ts
getInstanceIndex() {

		if ( this.shaderStage === 'vertex' ) {

			return this.getBuiltin( 'instance_index', 'instanceIndex', 'u32', 'attribute' );

		}

		return 'instanceIndex';

	}
```
</details>

##### `getInvocationLocalIndex(): string`

<details><summary>Code</summary>

```ts
getInvocationLocalIndex() {

		return this.getBuiltin( 'local_invocation_index', 'invocationLocalIndex', 'u32', 'attribute' );

	}
```
</details>

##### `getSubgroupSize(): string`

<details><summary>Code</summary>

```ts
getSubgroupSize() {

		this.enableSubGroups();

		return this.getBuiltin( 'subgroup_size', 'subgroupSize', 'u32', 'attribute' );

	}
```
</details>

##### `getInvocationSubgroupIndex(): string`

<details><summary>Code</summary>

```ts
getInvocationSubgroupIndex() {

		this.enableSubGroups();

		return this.getBuiltin( 'subgroup_invocation_id', 'invocationSubgroupIndex', 'u32', 'attribute' );

	}
```
</details>

##### `getSubgroupIndex(): string`

<details><summary>Code</summary>

```ts
getSubgroupIndex() {

		this.enableSubGroups();

		return this.getBuiltin( 'subgroup_id', 'subgroupIndex', 'u32', 'attribute' );

	}
```
</details>

##### `getDrawIndex(): null`

<details><summary>Code</summary>

```ts
getDrawIndex() {

		return null;

	}
```
</details>

##### `getFrontFacing(): string`

<details><summary>Code</summary>

```ts
getFrontFacing() {

		return this.getBuiltin( 'front_facing', 'isFront', 'bool' );

	}
```
</details>

##### `getFragCoord(): string`

<details><summary>Code</summary>

```ts
getFragCoord() {

		return this.getBuiltin( 'position', 'fragCoord', 'vec4<f32>' ) + '.xy';

	}
```
</details>

##### `getFragDepth(): string`

<details><summary>Code</summary>

```ts
getFragDepth() {

		return 'output.' + this.getBuiltin( 'frag_depth', 'depth', 'f32', 'output' );

	}
```
</details>

##### `getClipDistance(): string`

<details><summary>Code</summary>

```ts
getClipDistance() {

		return 'varyings.hw_clip_distances';

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

##### `enableDirective(name: string, shaderStage: string): void`

<details><summary>Code</summary>

```ts
enableDirective( name, shaderStage = this.shaderStage ) {

		const stage = this.directives[ shaderStage ] || ( this.directives[ shaderStage ] = new Set() );
		stage.add( name );

	}
```
</details>

##### `getDirectives(shaderStage: string): string`

<details><summary>Code</summary>

```ts
getDirectives( shaderStage ) {

		const snippets = [];
		const directives = this.directives[ shaderStage ];

		if ( directives !== undefined ) {

			for ( const directive of directives ) {

				snippets.push( `enable ${directive};` );

			}

		}

		return snippets.join( '\n' );

	}
```
</details>

##### `enableSubGroups(): void`

<details><summary>Code</summary>

```ts
enableSubGroups() {

		this.enableDirective( 'subgroups' );

	}
```
</details>

##### `enableSubgroupsF16(): void`

<details><summary>Code</summary>

```ts
enableSubgroupsF16() {

		this.enableDirective( 'subgroups-f16' );

	}
```
</details>

##### `enableClipDistances(): void`

<details><summary>Code</summary>

```ts
enableClipDistances() {

		this.enableDirective( 'clip_distances' );

	}
```
</details>

##### `enableShaderF16(): void`

<details><summary>Code</summary>

```ts
enableShaderF16() {

		this.enableDirective( 'f16' );

	}
```
</details>

##### `enableDualSourceBlending(): void`

<details><summary>Code</summary>

```ts
enableDualSourceBlending() {

		this.enableDirective( 'dual_source_blending' );

	}
```
</details>

##### `enableHardwareClipping(planeCount: string): void`

<details><summary>Code</summary>

```ts
enableHardwareClipping( planeCount ) {

		this.enableClipDistances();
		this.getBuiltin( 'clip_distances', 'hw_clip_distances', `array<f32, ${ planeCount } >`, 'vertex' );

	}
```
</details>

##### `getBuiltins(shaderStage: string): string`

<details><summary>Code</summary>

```ts
getBuiltins( shaderStage ) {

		const snippets = [];
		const builtins = this.builtins[ shaderStage ];

		if ( builtins !== undefined ) {

			for ( const { name, property, type } of builtins.values() ) {

				snippets.push( `@builtin( ${name} ) ${property} : ${type}` );

			}

		}

		return snippets.join( ',\n\t' );

	}
```
</details>

##### `getScopedArray(name: string, scope: string, bufferType: string, bufferCount: string): string`

<details><summary>Code</summary>

```ts
getScopedArray( name, scope, bufferType, bufferCount ) {

		if ( this.scopedArrays.has( name ) === false ) {

			this.scopedArrays.set( name, {
				name,
				scope,
				bufferType,
				bufferCount
			} );

		}

		return name;

	}
```
</details>

##### `getScopedArrays(shaderStage: string): string`

<details><summary>Code</summary>

```ts
getScopedArrays( shaderStage ) {

		if ( shaderStage !== 'compute' ) {

			return;

		}

		const snippets = [];

		for ( const { name, scope, bufferType, bufferCount } of this.scopedArrays.values() ) {

			const type = this.getType( bufferType );

			snippets.push( `var<${scope}> ${name}: array< ${type}, ${bufferCount} >;` );

		}

		return snippets.join( '\n' );

	}
```
</details>

##### `getAttributes(shaderStage: string): string`

<details><summary>Code</summary>

```ts
getAttributes( shaderStage ) {

		const snippets = [];

		if ( shaderStage === 'compute' ) {

			this.getBuiltin( 'global_invocation_id', 'globalId', 'vec3<u32>', 'attribute' );
			this.getBuiltin( 'workgroup_id', 'workgroupId', 'vec3<u32>', 'attribute' );
			this.getBuiltin( 'local_invocation_id', 'localId', 'vec3<u32>', 'attribute' );
			this.getBuiltin( 'num_workgroups', 'numWorkgroups', 'vec3<u32>', 'attribute' );

			if ( this.renderer.hasFeature( 'subgroups' ) ) {

				this.enableDirective( 'subgroups', shaderStage );
				this.getBuiltin( 'subgroup_size', 'subgroupSize', 'u32', 'attribute' );

			}

		}

		if ( shaderStage === 'vertex' || shaderStage === 'compute' ) {

			const builtins = this.getBuiltins( 'attribute' );

			if ( builtins ) snippets.push( builtins );

			const attributes = this.getAttributesArray();

			for ( let index = 0, length = attributes.length; index < length; index ++ ) {

				const attribute = attributes[ index ];
				const name = attribute.name;
				const type = this.getType( attribute.type );

				snippets.push( `@location( ${index} ) ${ name } : ${ type }` );

			}

		}

		return snippets.join( ',\n\t' );

	}
```
</details>

##### `getStructMembers(struct: StructTypeNode): string`

<details><summary>Code</summary>

```ts
getStructMembers( struct ) {

		const snippets = [];

		for ( const member of struct.members ) {

			const prefix = struct.output ? '@location( ' + member.index + ' ) ' : '';

			let type = this.getType( member.type );

			if ( member.atomic ) {

				type = 'atomic< ' + type + ' >';

			}

			snippets.push( `\t${ prefix + member.name } : ${ type }` );

		}

		if ( struct.output ) {

			snippets.push( `\t${ this.getBuiltins( 'output' ) }` );

		}

		return snippets.join( ',\n' );

	}
```
</details>

##### `getStructs(shaderStage: string): string`

<details><summary>Code</summary>

```ts
getStructs( shaderStage ) {

		let result = '';

		const structs = this.structs[ shaderStage ];

		if ( structs.length > 0 ) {

			const snippets = [];

			for ( const struct of structs ) {

				let snippet = `struct ${ struct.name } {\n`;
				snippet += this.getStructMembers( struct );
				snippet += '\n};';

				snippets.push( snippet );

			}

			result = '\n' + snippets.join( '\n\n' ) + '\n';

		}

		return result;

	}
```
</details>

##### `getVar(type: string, name: string, count: number): string`

<details><summary>Code</summary>

```ts
getVar( type, name, count = null ) {

		let snippet = `var ${ name } : `;

		if ( count !== null ) {

			snippet += this.generateArrayDeclaration( type, count );

		} else {

			snippet += this.getType( type );

		}

		return snippet;

	}
```
</details>

##### `getVars(shaderStage: string): string`

<details><summary>Code</summary>

```ts
getVars( shaderStage ) {

		const snippets = [];
		const vars = this.vars[ shaderStage ];

		if ( vars !== undefined ) {

			for ( const variable of vars ) {

				snippets.push( `\t${ this.getVar( variable.type, variable.name, variable.count ) };` );

			}

		}

		return `\n${ snippets.join( '\n' ) }\n`;

	}
```
</details>

##### `getVaryings(shaderStage: string): string`

<details><summary>Code</summary>

```ts
getVaryings( shaderStage ) {

		const snippets = [];

		if ( shaderStage === 'vertex' ) {

			this.getBuiltin( 'position', 'Vertex', 'vec4<f32>', 'vertex' );

		}

		if ( shaderStage === 'vertex' || shaderStage === 'fragment' ) {

			const varyings = this.varyings;
			const vars = this.vars[ shaderStage ];

			for ( let index = 0; index < varyings.length; index ++ ) {

				const varying = varyings[ index ];

				if ( varying.needsInterpolation ) {

					let attributesSnippet = `@location( ${index} )`;

					if ( varying.interpolationType ) {

						const samplingSnippet = varying.interpolationSampling !== null ? `, ${ varying.interpolationSampling } )` : ' )';

						attributesSnippet += ` @interpolate( ${ varying.interpolationType }${ samplingSnippet }`;

						// Otherwise, optimize interpolation when sensible

					} else if ( /^(int|uint|ivec|uvec)/.test( varying.type ) ) {

						attributesSnippet += ` @interpolate( ${ this.renderer.backend.compatibilityMode ? 'flat, either' : 'flat' } )`;

					}

					snippets.push( `${ attributesSnippet } ${ varying.name } : ${ this.getType( varying.type ) }` );

				} else if ( shaderStage === 'vertex' && vars.includes( varying ) === false ) {

					vars.push( varying );

				}

			}

		}

		const builtins = this.getBuiltins( shaderStage );

		if ( builtins ) snippets.push( builtins );

		const code = snippets.join( ',\n\t' );

		return shaderStage === 'vertex' ? this._getWGSLStruct( 'VaryingsStruct', '\t' + code ) : code;

	}
```
</details>

##### `isCustomStruct(nodeUniform: any): boolean`

<details><summary>Code</summary>

```ts
isCustomStruct( nodeUniform ) {

		const attribute = nodeUniform.value;
		const bufferNode = nodeUniform.node;

		const isAttributeStructType = ( attribute.isBufferAttribute || attribute.isInstancedBufferAttribute ) && bufferNode.structTypeNode !== null;

		const isStructArray =
			( bufferNode.value && bufferNode.value.array ) &&
			( typeof bufferNode.value.itemSize === 'number' && bufferNode.value.array.length > bufferNode.value.itemSize );

		return isAttributeStructType && ! isStructArray;

	}
```
</details>

##### `getUniforms(shaderStage: string): string`

<details><summary>Code</summary>

```ts
getUniforms( shaderStage ) {

		const uniforms = this.uniforms[ shaderStage ];

		const bindingSnippets = [];
		const bufferSnippets = [];
		const structSnippets = [];
		const uniformGroups = {};

		for ( const uniform of uniforms ) {

			const groupName = uniform.groupNode.name;
			const uniformIndexes = this.bindingsIndexes[ groupName ];

			if ( uniform.type === 'texture' || uniform.type === 'cubeTexture' || uniform.type === 'storageTexture' || uniform.type === 'texture3D' ) {

				const texture = uniform.node.value;

				if ( this.isUnfilterable( texture ) === false && uniform.node.isStorageTextureNode !== true ) {

					if ( this.isSampleCompare( texture ) ) {

						bindingSnippets.push( `@binding( ${ uniformIndexes.binding ++ } ) @group( ${ uniformIndexes.group } ) var ${ uniform.name }_sampler : sampler_comparison;` );

					} else {

						bindingSnippets.push( `@binding( ${ uniformIndexes.binding ++ } ) @group( ${ uniformIndexes.group } ) var ${ uniform.name }_sampler : sampler;` );

					}

				}

				let textureType;

				let multisampled = '';

				const { primarySamples } = this.renderer.backend.utils.getTextureSampleData( texture );

				if ( primarySamples > 1 ) {

					multisampled = '_multisampled';

				}

				if ( texture.isCubeTexture === true ) {

					textureType = 'texture_cube<f32>';

				} else if ( texture.isDepthTexture === true ) {

					if ( this.renderer.backend.compatibilityMode && texture.compareFunction === null ) {

						textureType = `texture${ multisampled }_2d<f32>`;

					} else {

						textureType = `texture_depth${ multisampled }_2d${ texture.isArrayTexture === true ? '_array' : '' }`;

					}

				} else if ( uniform.node.isStorageTextureNode === true ) {

					const format = getFormat( texture );
					const access = this.getStorageAccess( uniform.node, shaderStage );

					const is3D = uniform.node.value.is3DTexture;
					const isArrayTexture = uniform.node.value.isArrayTexture;

					const dimension = is3D ? '3d' : `2d${ isArrayTexture ? '_array' : '' }`;

					textureType = `texture_storage_${ dimension }<${ format }, ${ access }>`;

				} else if ( texture.isArrayTexture === true || texture.isDataArrayTexture === true || texture.isCompressedArrayTexture === true ) {

					textureType = 'texture_2d_array<f32>';

				} else if ( texture.is3DTexture === true || texture.isData3DTexture === true ) {

					textureType = 'texture_3d<f32>';

				} else {

					const componentPrefix = this.getComponentTypeFromTexture( texture ).charAt( 0 );

					textureType = `texture${ multisampled }_2d<${ componentPrefix }32>`;

				}

				bindingSnippets.push( `@binding( ${ uniformIndexes.binding ++ } ) @group( ${ uniformIndexes.group } ) var ${ uniform.name } : ${ textureType };` );

			} else if ( uniform.type === 'buffer' || uniform.type === 'storageBuffer' || uniform.type === 'indirectStorageBuffer' ) {

				const bufferNode = uniform.node;
				const bufferType = this.getType( bufferNode.getNodeType( this ) );
				const bufferCount = bufferNode.bufferCount;
				const bufferCountSnippet = bufferCount > 0 && uniform.type === 'buffer' ? ', ' + bufferCount : '';
				const bufferAccessMode = bufferNode.isStorageBufferNode ? `storage, ${ this.getStorageAccess( bufferNode, shaderStage ) }` : 'uniform';

				if ( this.isCustomStruct( uniform ) ) {

					bufferSnippets.push( `@binding( ${ uniformIndexes.binding ++ } ) @group( ${ uniformIndexes.group } ) var<${ bufferAccessMode }> ${ uniform.name } : ${ bufferType };` );

				} else {

					const bufferTypeSnippet = bufferNode.isAtomic ? `atomic<${ bufferType }>` : `${ bufferType }`;
					const bufferSnippet = `\tvalue : array< ${ bufferTypeSnippet }${ bufferCountSnippet } >`;

					bufferSnippets.push( this._getWGSLStructBinding( uniform.name, bufferSnippet, bufferAccessMode, uniformIndexes.binding ++, uniformIndexes.group ) );

				}

			} else {

				const vectorType = this.getType( this.getVectorType( uniform.type ) );
				const groupName = uniform.groupNode.name;

				const group = uniformGroups[ groupName ] || ( uniformGroups[ groupName ] = {
					index: uniformIndexes.binding ++,
					id: uniformIndexes.group,
					snippets: []
				} );

				group.snippets.push( `\t${ uniform.name } : ${ vectorType }` );

			}

		}

		for ( const name in uniformGroups ) {

			const group = uniformGroups[ name ];

			structSnippets.push( this._getWGSLStructBinding( name, group.snippets.join( ',\n' ), 'uniform', group.index, group.id ) );

		}

		let code = bindingSnippets.join( '\n' );
		code += bufferSnippets.join( '\n' );
		code += structSnippets.join( '\n' );

		return code;

	}
```
</details>

##### `buildCode(): void`

<details><summary>Code</summary>

```ts
buildCode() {

		const shadersData = this.material !== null ? { fragment: {}, vertex: {} } : { compute: {} };

		this.sortBindingGroups();

		for ( const shaderStage in shadersData ) {

			this.shaderStage = shaderStage;

			const stageData = shadersData[ shaderStage ];
			stageData.uniforms = this.getUniforms( shaderStage );
			stageData.attributes = this.getAttributes( shaderStage );
			stageData.varyings = this.getVaryings( shaderStage );
			stageData.structs = this.getStructs( shaderStage );
			stageData.vars = this.getVars( shaderStage );
			stageData.codes = this.getCodes( shaderStage );
			stageData.directives = this.getDirectives( shaderStage );
			stageData.scopedArrays = this.getScopedArrays( shaderStage );

			//

			let flow = '// code\n\n';
			flow += this.flowCode[ shaderStage ];

			const flowNodes = this.flowNodes[ shaderStage ];
			const mainNode = flowNodes[ flowNodes.length - 1 ];

			const outputNode = mainNode.outputNode;
			const isOutputStruct = ( outputNode !== undefined && outputNode.isOutputStructNode === true );

			for ( const node of flowNodes ) {

				const flowSlotData = this.getFlowData( node/*, shaderStage*/ );
				const slotName = node.name;

				if ( slotName ) {

					if ( flow.length > 0 ) flow += '\n';

					flow += `\t// flow -> ${ slotName }\n`;

				}

				flow += `${ flowSlotData.code }\n\t`;

				if ( node === mainNode && shaderStage !== 'compute' ) {

					flow += '// result\n\n\t';

					if ( shaderStage === 'vertex' ) {

						flow += `varyings.Vertex = ${ flowSlotData.result };`;

					} else if ( shaderStage === 'fragment' ) {

						if ( isOutputStruct ) {

							stageData.returnType = outputNode.getNodeType( this );
							stageData.structs += 'var<private> output : ' + stageData.returnType + ';';

							flow += `return ${ flowSlotData.result };`;

						} else {

							let structSnippet = '\t@location(0) color: vec4<f32>';

							const builtins = this.getBuiltins( 'output' );

							if ( builtins ) structSnippet += ',\n\t' + builtins;

							stageData.returnType = 'OutputStruct';
							stageData.structs += this._getWGSLStruct( 'OutputStruct', structSnippet );
							stageData.structs += '\nvar<private> output : OutputStruct;';

							flow += `output.color = ${ flowSlotData.result };\n\n\treturn output;`;

						}

					}

				}

			}

			stageData.flow = flow;

		}

		this.shaderStage = null;

		if ( this.material !== null ) {

			this.vertexShader = this._getWGSLVertexCode( shadersData.vertex );
			this.fragmentShader = this._getWGSLFragmentCode( shadersData.fragment );

		} else {

			// Early strictly validated in computeNode

			const workgroupSize = this.object.workgroupSize;

			this.computeShader = this._getWGSLComputeCode( shadersData.compute, workgroupSize );

		}

	}
```
</details>

##### `getMethod(method: string, output: string): string`

<details><summary>Code</summary>

```ts
getMethod( method, output = null ) {

		let wgslMethod;

		if ( output !== null ) {

			wgslMethod = this._getWGSLMethod( method + '_' + output );

		}

		if ( wgslMethod === undefined ) {

			wgslMethod = this._getWGSLMethod( method );

		}

		return wgslMethod || method;

	}
```
</details>

##### `getTernary(condSnippet: string, ifSnippet: string, elseSnippet: string): string`

<details><summary>Code</summary>

```ts
getTernary( condSnippet, ifSnippet, elseSnippet ) {

		return `select( ${elseSnippet}, ${ifSnippet}, ${condSnippet} )`;

	}
```
</details>

##### `getType(type: string): string`

<details><summary>Code</summary>

```ts
getType( type ) {

		return wgslTypeLib[ type ] || type;

	}
```
</details>

##### `isAvailable(name: string): boolean`

<details><summary>Code</summary>

```ts
isAvailable( name ) {

		let result = supports[ name ];

		if ( result === undefined ) {

			if ( name === 'float32Filterable' ) {

				result = this.renderer.hasFeature( 'float32-filterable' );

			} else if ( name === 'clipDistance' ) {

				result = this.renderer.hasFeature( 'clip-distances' );

			}

			supports[ name ] = result;

		}

		return result;

	}
```
</details>

##### `_getWGSLMethod(method: string): string`

<details><summary>Code</summary>

```ts
_getWGSLMethod( method ) {

		if ( wgslPolyfill[ method ] !== undefined ) {

			this._include( method );

		}

		return wgslMethods[ method ];

	}
```
</details>

##### `_include(name: string): CodeNode`

<details><summary>Code</summary>

```ts
_include( name ) {

		const codeNode = wgslPolyfill[ name ];
		codeNode.build( this );

		if ( this.currentFunctionNode !== null ) {

			this.currentFunctionNode.includes.push( codeNode );

		}

		return codeNode;

	}
```
</details>

##### `_getWGSLVertexCode(shaderData: any): string`

<details><summary>Code</summary>

```ts
_getWGSLVertexCode( shaderData ) {

		return `${ this.getSignature() }
// directives
${shaderData.directives}

// structs
${shaderData.structs}

// uniforms
${shaderData.uniforms}

// varyings
${shaderData.varyings}
var<private> varyings : VaryingsStruct;

// codes
${shaderData.codes}

@vertex
fn main( ${shaderData.attributes} ) -> VaryingsStruct {

	// vars
	${shaderData.vars}

	// flow
	${shaderData.flow}

	return varyings;

}
`;

	}
```
</details>

##### `_getWGSLFragmentCode(shaderData: any): string`

<details><summary>Code</summary>

```ts
_getWGSLFragmentCode( shaderData ) {

		return `${ this.getSignature() }
// global
${ diagnostics }

// structs
${shaderData.structs}

// uniforms
${shaderData.uniforms}

// codes
${shaderData.codes}

@fragment
fn main( ${shaderData.varyings} ) -> ${shaderData.returnType} {

	// vars
	${shaderData.vars}

	// flow
	${shaderData.flow}

}
`;

	}
```
</details>

##### `_getWGSLComputeCode(shaderData: any, workgroupSize: string): string`

<details><summary>Code</summary>

```ts
_getWGSLComputeCode( shaderData, workgroupSize ) {

		const [ workgroupSizeX, workgroupSizeY, workgroupSizeZ ] = workgroupSize;

		return `${ this.getSignature() }
// directives
${ shaderData.directives }

// system
var<private> instanceIndex : u32;

// locals
${ shaderData.scopedArrays }

// structs
${ shaderData.structs }

// uniforms
${ shaderData.uniforms }

// codes
${ shaderData.codes }

@compute @workgroup_size( ${ workgroupSizeX }, ${ workgroupSizeY }, ${ workgroupSizeZ } )
fn main( ${ shaderData.attributes } ) {

	// system
	instanceIndex = globalId.x
		+ globalId.y * ( ${ workgroupSizeX } * numWorkgroups.x )
		+ globalId.z * ( ${ workgroupSizeX } * numWorkgroups.x ) * ( ${ workgroupSizeY } * numWorkgroups.y );

	// vars
	${ shaderData.vars }

	// flow
	${ shaderData.flow }

}
`;

	}
```
</details>

##### `_getWGSLStruct(name: string, vars: string): string`

<details><summary>Code</summary>

```ts
_getWGSLStruct( name, vars ) {

		return `
struct ${name} {
${vars}
};`;

	}
```
</details>

##### `_getWGSLStructBinding(name: string, vars: string, access: string, binding: number, group: number): string`

<details><summary>Code</summary>

```ts
_getWGSLStructBinding( name, vars, access, binding = 0, group = 0 ) {

		const structName = name + 'Struct';
		const structSnippet = this._getWGSLStruct( structName, vars );

		return `${structSnippet}
@binding( ${ binding } ) @group( ${ group } )
var<${access}> ${ name } : ${ structName };`;

	}
```
</details>


---