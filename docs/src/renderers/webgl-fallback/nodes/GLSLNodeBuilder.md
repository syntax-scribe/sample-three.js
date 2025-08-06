[⬅️ Back to Table of Contents](../../../../index.md)

# 📄 `GLSLNodeBuilder.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 42 |
| 🧱 Classes | 1 |
| 📦 Imports | 26 |
| 📊 Variables & Constants | 83 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webgl-fallback/nodes/GLSLNodeBuilder.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `GLSLNodeParser` | `../../../nodes/Nodes.js` |
| `NodeBuilder` | `../../../nodes/Nodes.js` |
| `TextureNode` | `../../../nodes/Nodes.js` |
| `vectorComponents` | `../../../nodes/Nodes.js` |
| `NodeUniformBuffer` | `../../common/nodes/NodeUniformBuffer.js` |
| `NodeUniformsGroup` | `../../common/nodes/NodeUniformsGroup.js` |
| `NodeSampledTexture` | `../../common/nodes/NodeSampledTexture.js` |
| `NodeSampledCubeTexture` | `../../common/nodes/NodeSampledTexture.js` |
| `NodeSampledTexture3D` | `../../common/nodes/NodeSampledTexture.js` |
| `NoColorSpace` | `../../../constants.js` |
| `ByteType` | `../../../constants.js` |
| `ShortType` | `../../../constants.js` |
| `RGBAIntegerFormat` | `../../../constants.js` |
| `RGBIntegerFormat` | `../../../constants.js` |
| `RedIntegerFormat` | `../../../constants.js` |
| `RGIntegerFormat` | `../../../constants.js` |
| `UnsignedByteType` | `../../../constants.js` |
| `UnsignedIntType` | `../../../constants.js` |
| `UnsignedShortType` | `../../../constants.js` |
| `RedFormat` | `../../../constants.js` |
| `RGFormat` | `../../../constants.js` |
| `IntType` | `../../../constants.js` |
| `RGBFormat` | `../../../constants.js` |
| `RGBAFormat` | `../../../constants.js` |
| `FloatType` | `../../../constants.js` |
| `DataTexture` | `../../../textures/DataTexture.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `glslMethods` | `{ textureDimensions: string; equals: ...` | let/var | `{ textureDimensions: 'textureSize', equals: 'equal' }` | ✗ |
| `precisionLib` | `{ low: string; medium: string; high: ...` | let/var | `{ low: 'lowp', medium: 'mediump', high: 'highp' }` | ✗ |
| `supports` | `{ swizzleAssign: boolean; storageBuff...` | let/var | `{ swizzleAssign: true, storageBuffer: false }` | ✗ |
| `interpolationTypeMap` | `{ perspective: string; linear: string; }` | let/var | `{ perspective: 'smooth', linear: 'noperspective' }` | ✗ |
| `interpolationModeMap` | `{ centroid: string; }` | let/var | `{ 'centroid': 'centroid' }` | ✗ |
| `defaultPrecisions` | `"\nprecision highp float;\nprecision ...` | let/var | `` precision highp float; precision highp int; precision highp sampler2D; prec...` | ✗ |
| `layout` | `any` | let/var | `shaderNode.layout` | ✗ |
| `parameters` | `any[]` | let/var | `[]` | ✗ |
| `code` | `string` | let/var | ``${ this.getType( layout.type ) } ${ layout.name }( ${ parameters.join( ', ' ...` | ✗ |
| `attribute` | `any` | let/var | `storageBufferNode.value` | ✗ |
| `originalArray` | `any` | let/var | `attribute.array` | ✗ |
| `numElements` | `number` | let/var | `attribute.count * attribute.itemSize` | ✗ |
| `format` | `number` | let/var | `isInteger ? RedIntegerFormat : RedFormat` | ✗ |
| `typeMap` | `{ Float32Array: number; Uint8Array: n...` | let/var | `{ Float32Array: FloatType, Uint8Array: UnsignedByteType, Uint16Array: Unsigne...` | ✗ |
| `newSize` | `number` | let/var | `width * height * itemSize` | ✗ |
| `newArray` | `any` | let/var | `new originalArray.constructor( newSize )` | ✗ |
| `pboTexture` | `DataTexture` | let/var | `new DataTexture( attribute.array, width, height, format, typeMap[ attribute.a...` | ✗ |
| `pbo` | `TextureNode` | let/var | `new TextureNode( pboTexture, null, null )` | ✗ |
| `attribute` | `any` | let/var | `node.value` | ✗ |
| `propertyName` | `any` | let/var | `elementNodeData.propertyName` | ✗ |
| `propertySizeName` | `any` | let/var | `bufferNodeData.propertySizeName` | ✗ |
| `channel` | `string` | let/var | `'.' + vectorComponents.join( '' ).slice( 0, itemSize )` | ✗ |
| `uvSnippet` | `string` | let/var | ``ivec2(${indexSnippet} % ${ propertySizeName }, ${indexSnippet} / ${ property...` | ✗ |
| `prefix` | `string` | let/var | `'vec4'` | ✗ |
| `snippets` | `any[]` | let/var | `[]` | ✗ |
| `vars` | `number \| NodeVar[]` | let/var | `this.vars[ shaderStage ]` | ✗ |
| `uniforms` | `any` | let/var | `this.uniforms[ shaderStage ]` | ✗ |
| `bindingSnippets` | `any[]` | let/var | `[]` | ✗ |
| `uniformGroups` | `{}` | let/var | `{}` | ✗ |
| `snippet` | `any` | let/var | `null` | ✗ |
| `group` | `boolean` | let/var | `false` | ✗ |
| `texture` | `any` | let/var | `uniform.node.value` | ✗ |
| `typePrefix` | `string` | let/var | `''` | ✗ |
| `bufferNode` | `any` | let/var | `uniform.node` | ✗ |
| `bufferCount` | `any` | let/var | `bufferNode.bufferCount` | ✗ |
| `bufferCountSnippet` | `any` | let/var | `bufferCount > 0 ? bufferCount : ''` | ✗ |
| `precision` | `any` | let/var | `uniform.node.precision` | ✗ |
| `groupName` | `any` | let/var | `uniform.groupNode.name` | ✗ |
| `groupSnippets` | `any` | let/var | `uniformGroups[ groupName ] \|\| ( uniformGroups[ groupName ] = [] )` | ✗ |
| `output` | `string` | let/var | `''` | ✗ |
| `groupSnippets` | `any` | let/var | `uniformGroups[ name ]` | ✗ |
| `dataAttribute` | `BufferAttribute` | let/var | `attribute` | ✗ |
| `array` | `any` | let/var | `dataAttribute.array` | ✗ |
| `snippet` | `string` | let/var | `''` | ✗ |
| `location` | `number` | let/var | `0` | ✗ |
| `snippets` | `any[]` | let/var | `[]` | ✗ |
| `snippets` | `any[]` | let/var | `[]` | ✗ |
| `structs` | `any` | let/var | `this.structs[ shaderStage ]` | ✗ |
| `outputSnippet` | `any[]` | let/var | `[]` | ✗ |
| `snippet` | `string` | let/var | `'struct ' + struct.name + ' {\n'` | ✗ |
| `snippet` | `string` | let/var | `''` | ✗ |
| `varyings` | `NodeVarying[]` | let/var | `this.varyings` | ✗ |
| `interpolationType` | `any` | let/var | `interpolationTypeMap[ varying.interpolationType ] \|\| varying.interpolationType` | ✗ |
| `sampling` | `any` | let/var | `interpolationModeMap[ varying.interpolationSampling ] \|\| ''` | ✗ |
| `flat` | `"" \| "flat "` | let/var | `type.includes( 'int' ) \|\| type.includes( 'uv' ) \|\| type.includes( 'iv' ) ...` | ✗ |
| `interpolationType` | `any` | let/var | `interpolationTypeMap[ varying.interpolationType ] \|\| varying.interpolationType` | ✗ |
| `sampling` | `any` | let/var | `interpolationModeMap[ varying.interpolationSampling ] \|\| ''` | ✗ |
| `flat` | `"" \| "flat "` | let/var | `type.includes( 'int' ) \|\| type.includes( 'uv' ) \|\| type.includes( 'iv' ) ...` | ✗ |
| `workgroupSize` | `any` | let/var | `this.object.workgroupSize` | ✗ |
| `extensions` | `any` | let/var | `this.renderer.backend.extensions` | ✗ |
| `map` | `Map<any, any>` | let/var | `this.extensions[ shaderStage ] \|\| ( this.extensions[ shaderStage ] = new Ma...` | ✗ |
| `snippets` | `any[]` | let/var | `[]` | ✗ |
| `ext` | `any` | let/var | `this.renderer.backend.extensions` | ✗ |
| `isBatchedMesh` | `any` | let/var | `this.object.isBatchedMesh` | ✗ |
| `extensions` | `Map<string, any>` | let/var | `this.extensions[ shaderStage ]` | ✗ |
| `result` | `any` | let/var | `supports[ name ]` | ✗ |
| `extensionName` | `any` | let/var | `*not shown*` | ✗ |
| `extensions` | `any` | let/var | `this.renderer.backend.extensions` | ✗ |
| `transforms` | `{ [x: string]: any; }[]` | let/var | `this.transforms` | ✗ |
| `snippet` | `string` | let/var | `''` | ✗ |
| `transform` | `{ [x: string]: any; }` | let/var | `transforms[ i ]` | ✗ |
| `shadersData` | `{ fragment: {}; vertex: {}; compute?:...` | let/var | `this.material !== null ? { fragment: {}, vertex: {} } : { compute: {} }` | ✗ |
| `flow` | `string` | let/var | `'// code\n\n'` | ✗ |
| `flowNodes` | `Node[]` | let/var | `this.flowNodes[ shaderStage ]` | ✗ |
| `mainNode` | `Node` | let/var | `flowNodes[ flowNodes.length - 1 ]` | ✗ |
| `slotName` | `any` | let/var | `node.name` | ✗ |
| `stageData` | `any` | let/var | `shadersData[ shaderStage ]` | ✗ |
| `uniformGPU` | `any` | let/var | `nodeData.uniformGPU` | ✗ |
| `group` | `any` | let/var | `node.groupNode` | ✗ |
| `groupName` | `any` | let/var | `group.name` | ✗ |
| `buffer` | `NodeUniformBuffer` | let/var | `new NodeUniformBuffer( node, group )` | ✗ |
| `uniformsStage` | `{ [x: string]: NodeUniformsGroup; }` | let/var | `this.uniformGroups[ shaderStage ] \|\| ( this.uniformGroups[ shaderStage ] = ...` | ✗ |
| `uniformsGroup` | `NodeUniformsGroup` | let/var | `uniformsStage[ groupName ]` | ✗ |


---

## Functions

### `GLSLNodeBuilder.needsToWorkingColorSpace(texture: Texture): boolean`

**JSDoc:**
```typescript
/**
	 * Checks if the given texture requires a manual conversion to the working color space.
	 *
	 * @param {Texture} texture - The texture to check.
	 * @return {boolean} Whether the given texture requires a conversion to working color space or not.
	 */
```

**Parameters:**

- **`texture`** `Texture`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
needsToWorkingColorSpace( texture ) {

		return texture.isVideoTexture === true && texture.colorSpace !== NoColorSpace;

	}
```
</details>

### `GLSLNodeBuilder.getMethod(method: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the native shader method name for a given generic name.
	 *
	 * @param {string} method - The method name to resolve.
	 * @return {string} The resolved GLSL method name.
	 */
```

**Parameters:**

- **`method`** `string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getMethod( method ) {

		return glslMethods[ method ] || method;

	}
```
</details>

### `GLSLNodeBuilder.getTernary(condSnippet: string, ifSnippet: string, elseSnippet: string): string`

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

		return `${condSnippet} ? ${ifSnippet} : ${elseSnippet}`;

	}
```
</details>

### `GLSLNodeBuilder.getOutputStructName(): string`

**JSDoc:**
```typescript
/**
	 * Returns the output struct name. Not relevant for GLSL.
	 *
	 * @return {string}
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getOutputStructName() {

		return '';

	}
```
</details>

### `GLSLNodeBuilder.buildFunctionCode(shaderNode: ShaderNodeInternal): string`

**JSDoc:**
```typescript
/**
	 * Builds the given shader node.
	 *
	 * @param {ShaderNodeInternal} shaderNode - The shader node.
	 * @return {string} The GLSL function code.
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

			parameters.push( this.getType( input.type ) + ' ' + input.name );

		}

		//

		const code = `${ this.getType( layout.type ) } ${ layout.name }( ${ parameters.join( ', ' ) } ) {

	${ flowData.vars }

${ flowData.code }
	return ${ flowData.result };

}`;

		//

		return code;

	}
```
</details>

### `GLSLNodeBuilder.setupPBO(storageBufferNode: StorageBufferNode): void`

**JSDoc:**
```typescript
/**
	 * Setups the Pixel Buffer Object (PBO) for the given storage
	 * buffer node.
	 *
	 * @param {StorageBufferNode} storageBufferNode - The storage buffer node.
	 */
```

**Parameters:**

- **`storageBufferNode`** `StorageBufferNode`

**Returns:** `void`

**Calls:**

- `attribute.array.constructor.name.toLowerCase().includes`
- `Math.pow`
- `Math.ceil`
- `Math.log2`
- `Math.sqrt`
- `newArray.set`
- `pbo.setPrecision`
- `this.getUniformFromNode`

<details><summary>Code</summary>

```typescript
setupPBO( storageBufferNode ) {

		const attribute = storageBufferNode.value;

		if ( attribute.pbo === undefined ) {

			const originalArray = attribute.array;
			const numElements = attribute.count * attribute.itemSize;

			const { itemSize } = attribute;

			const isInteger = attribute.array.constructor.name.toLowerCase().includes( 'int' );

			let format = isInteger ? RedIntegerFormat : RedFormat;

			if ( itemSize === 2 ) {

				format = isInteger ? RGIntegerFormat : RGFormat;

			} else if ( itemSize === 3 ) {

				format = isInteger ? RGBIntegerFormat : RGBFormat;

			} else if ( itemSize === 4 ) {

				format = isInteger ? RGBAIntegerFormat : RGBAFormat;

			}

			const typeMap = {
				Float32Array: FloatType,
				Uint8Array: UnsignedByteType,
				Uint16Array: UnsignedShortType,
				Uint32Array: UnsignedIntType,
				Int8Array: ByteType,
				Int16Array: ShortType,
				Int32Array: IntType,
				Uint8ClampedArray: UnsignedByteType,
			};

			const width = Math.pow( 2, Math.ceil( Math.log2( Math.sqrt( numElements / itemSize ) ) ) );
			let height = Math.ceil( ( numElements / itemSize ) / width );
			if ( width * height * itemSize < numElements ) height ++; // Ensure enough space

			const newSize = width * height * itemSize;

			const newArray = new originalArray.constructor( newSize );

			newArray.set( originalArray, 0 );

			attribute.array = newArray;

			const pboTexture = new DataTexture( attribute.array, width, height, format, typeMap[ attribute.array.constructor.name ] || FloatType );
			pboTexture.needsUpdate = true;
			pboTexture.isPBOTexture = true;

			const pbo = new TextureNode( pboTexture, null, null );
			pbo.setPrecision( 'high' );

			attribute.pboNode = pbo;
			attribute.pbo = pbo.value;

			this.getUniformFromNode( attribute.pboNode, 'texture', this.shaderStage, this.context.nodeName );

		}

	}
```
</details>

### `GLSLNodeBuilder.getPropertyName(node: Node, shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns a GLSL snippet that represents the property name of the given node.
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

- `shaderStage.charAt`
- `super.getPropertyName`

<details><summary>Code</summary>

```typescript
getPropertyName( node, shaderStage = this.shaderStage ) {

		if ( node.isNodeUniform && node.node.isTextureNode !== true && node.node.isBufferNode !== true ) {

			return shaderStage.charAt( 0 ) + '_' + node.name;

		}

		return super.getPropertyName( node, shaderStage );

	}
```
</details>

### `GLSLNodeBuilder.generatePBO(storageArrayElementNode: StorageArrayElementNode): string`

**JSDoc:**
```typescript
/**
	 * Setups the Pixel Buffer Object (PBO) for the given storage
	 * buffer node.
	 *
	 * @param {StorageArrayElementNode} storageArrayElementNode - The storage array element node.
	 * @return {string} The property name.
	 */
```

**Parameters:**

- **`storageArrayElementNode`** `StorageArrayElementNode`

**Returns:** `string`

**Calls:**

- `this.renderer.backend.has`
- `this.renderer.backend.get`
- `this.getUniformFromNode`
- `this.getPropertyName`
- `this.increaseUsage`
- `indexNode.build`
- `this.getDataFromNode`
- `this.getVarFromNode`
- `this.addLineFlowCode`
- `vectorComponents.join( '' ).slice`
- `this.generateTextureLoad`

**Internal Comments:**
```
// property element (x2)
// property size (x2)
// (x4)
```

<details><summary>Code</summary>

```typescript
generatePBO( storageArrayElementNode ) {

		const { node, indexNode } = storageArrayElementNode;
		const attribute = node.value;

		if ( this.renderer.backend.has( attribute ) ) {

			const attributeData = this.renderer.backend.get( attribute );
			attributeData.pbo = attribute.pbo;

		}

		const nodeUniform = this.getUniformFromNode( attribute.pboNode, 'texture', this.shaderStage, this.context.nodeName );
		const textureName = this.getPropertyName( nodeUniform );

		this.increaseUsage( indexNode ); // force cache generate to be used as index in x,y
		const indexSnippet = indexNode.build( this, 'uint' );

		const elementNodeData = this.getDataFromNode( storageArrayElementNode );

		let propertyName = elementNodeData.propertyName;

		if ( propertyName === undefined ) {

			// property element

			const nodeVar = this.getVarFromNode( storageArrayElementNode );

			propertyName = this.getPropertyName( nodeVar );

			// property size

			const bufferNodeData = this.getDataFromNode( node );

			let propertySizeName = bufferNodeData.propertySizeName;

			if ( propertySizeName === undefined ) {

				propertySizeName = propertyName + 'Size';

				this.getVarFromNode( node, propertySizeName, 'uint' );

				this.addLineFlowCode( `${ propertySizeName } = uint( textureSize( ${ textureName }, 0 ).x )`, storageArrayElementNode );

				bufferNodeData.propertySizeName = propertySizeName;

			}

			//

			const { itemSize } = attribute;

			const channel = '.' + vectorComponents.join( '' ).slice( 0, itemSize );
			const uvSnippet = `ivec2(${indexSnippet} % ${ propertySizeName }, ${indexSnippet} / ${ propertySizeName })`;

			const snippet = this.generateTextureLoad( null, textureName, uvSnippet, null, '0' );

			//


			let prefix = 'vec4';

			if ( attribute.pbo.type === UnsignedIntType ) {

				prefix = 'uvec4';

			} else if ( attribute.pbo.type === IntType ) {

				prefix = 'ivec4';

			}

			this.addLineFlowCode( `${ propertyName } = ${prefix}(${ snippet })${channel}`, storageArrayElementNode );

			elementNodeData.propertyName = propertyName;

		}

		return propertyName;

	}
```
</details>

### `GLSLNodeBuilder.generateTextureLoad(texture: Texture, textureProperty: string, uvIndexSnippet: string, depthSnippet: string, levelSnippet: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the GLSL snippet that reads a single texel from a texture without sampling or filtering.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvIndexSnippet - A GLSL snippet that represents texture coordinates used for sampling.
	 * @param {?string} depthSnippet - A GLSL snippet that represents the 0-based texture array index to sample.
	 * @param {string} [levelSnippet='0u'] - A GLSL snippet that represents the mip level, with level 0 containing a full size version of the texture.
	 * @return {string} The GLSL snippet.
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
generateTextureLoad( texture, textureProperty, uvIndexSnippet, depthSnippet, levelSnippet = '0' ) {

		if ( depthSnippet ) {

			return `texelFetch( ${ textureProperty }, ivec3( ${ uvIndexSnippet }, ${ depthSnippet } ), ${ levelSnippet } )`;

		} else {

			return `texelFetch( ${ textureProperty }, ${ uvIndexSnippet }, ${ levelSnippet } )`;

		}

	}
```
</details>

### `GLSLNodeBuilder.generateTexture(texture: Texture, textureProperty: string, uvSnippet: string, depthSnippet: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the GLSL snippet for sampling/loading the given texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A GLSL snippet that represents texture coordinates used for sampling.
	 * @param {?string} depthSnippet -  A GLSL snippet that represents the 0-based texture array index to sample.
	 * @return {string} The GLSL snippet.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`textureProperty`** `string`
- **`uvSnippet`** `string`
- **`depthSnippet`** `string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
generateTexture( texture, textureProperty, uvSnippet, depthSnippet ) {

		if ( texture.isDepthTexture ) {

			if ( depthSnippet ) uvSnippet = `vec4( ${ uvSnippet }, ${ depthSnippet } )`;

			return `texture( ${ textureProperty }, ${ uvSnippet } ).x`;

		} else {

			if ( depthSnippet ) uvSnippet = `vec3( ${ uvSnippet }, ${ depthSnippet } )`;

			return `texture( ${ textureProperty }, ${ uvSnippet } )`;

		}

	}
```
</details>

### `GLSLNodeBuilder.generateTextureLevel(texture: Texture, textureProperty: string, uvSnippet: string, levelSnippet: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the GLSL snippet when sampling textures with explicit mip level.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A GLSL snippet that represents texture coordinates used for sampling.
	 * @param {string} levelSnippet - A GLSL snippet that represents the mip level, with level 0 containing a full size version of the texture.
	 * @return {string} The GLSL snippet.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`textureProperty`** `string`
- **`uvSnippet`** `string`
- **`levelSnippet`** `string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
generateTextureLevel( texture, textureProperty, uvSnippet, levelSnippet ) {

		return `textureLod( ${ textureProperty }, ${ uvSnippet }, ${ levelSnippet } )`;

	}
```
</details>

### `GLSLNodeBuilder.generateTextureBias(texture: Texture, textureProperty: string, uvSnippet: string, biasSnippet: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the GLSL snippet when sampling textures with a bias to the mip level.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A GLSL snippet that represents texture coordinates used for sampling.
	 * @param {string} biasSnippet - A GLSL snippet that represents the bias to apply to the mip level before sampling.
	 * @return {string} The GLSL snippet.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`textureProperty`** `string`
- **`uvSnippet`** `string`
- **`biasSnippet`** `string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
generateTextureBias( texture, textureProperty, uvSnippet, biasSnippet ) {

		return `texture( ${ textureProperty }, ${ uvSnippet }, ${ biasSnippet } )`;

	}
```
</details>

### `GLSLNodeBuilder.generateTextureGrad(texture: Texture, textureProperty: string, uvSnippet: string, gradSnippet: string[]): string`

**JSDoc:**
```typescript
/**
	 * Generates the GLSL snippet for sampling/loading the given texture using explicit gradients.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A GLSL snippet that represents texture coordinates used for sampling.
	 * @param {Array<string>} gradSnippet - An array holding both gradient GLSL snippets.
	 * @return {string} The GLSL snippet.
	 */
```

**Parameters:**

- **`texture`** `Texture`
- **`textureProperty`** `string`
- **`uvSnippet`** `string`
- **`gradSnippet`** `string[]`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
generateTextureGrad( texture, textureProperty, uvSnippet, gradSnippet ) {

		return `textureGrad( ${ textureProperty }, ${ uvSnippet }, ${ gradSnippet[ 0 ] }, ${ gradSnippet[ 1 ] } )`;

	}
```
</details>

### `GLSLNodeBuilder.generateTextureCompare(texture: Texture, textureProperty: string, uvSnippet: string, compareSnippet: string, depthSnippet: string, shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Generates the GLSL snippet for sampling a depth texture and comparing the sampled depth values
	 * against a reference value.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A GLSL snippet that represents texture coordinates used for sampling.
	 * @param {string} compareSnippet -  A GLSL snippet that represents the reference value.
	 * @param {?string} depthSnippet - A GLSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The GLSL snippet.
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

			if ( depthSnippet ) {

				return `texture( ${ textureProperty }, vec4( ${ uvSnippet }, ${ depthSnippet }, ${ compareSnippet } ) )`;

			}

			return `texture( ${ textureProperty }, vec3( ${ uvSnippet }, ${ compareSnippet } ) )`;

		} else {

			console.error( `WebGPURenderer: THREE.DepthTexture.compareFunction() does not support ${ shaderStage } shader.` );

		}

	}
```
</details>

### `GLSLNodeBuilder.getVars(shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the variables of the given shader stage as a GLSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The GLSL snippet that defines the variables.
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

				snippets.push( `${ this.getVar( variable.type, variable.name, variable.count ) };` );

			}

		}

		return snippets.join( '\n\t' );

	}
```
</details>

### `GLSLNodeBuilder.getUniforms(shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the uniforms of the given shader stage as a GLSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The GLSL snippet that defines the uniforms.
	 */
```

**Parameters:**

- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `this.getType`
- `this.getVectorType`
- `this.getPropertyName`
- `groupSnippets.push`
- `bindingSnippets.push`
- `this._getGLSLUniformStruct`
- `groupSnippets.join`
- `bindingSnippets.join`

<details><summary>Code</summary>

```typescript
getUniforms( shaderStage ) {

		const uniforms = this.uniforms[ shaderStage ];

		const bindingSnippets = [];
		const uniformGroups = {};

		for ( const uniform of uniforms ) {

			let snippet = null;
			let group = false;

			if ( uniform.type === 'texture' || uniform.type === 'texture3D' ) {

				const texture = uniform.node.value;

				let typePrefix = '';

				if ( texture.isDataTexture === true || texture.isData3DTexture === true ) {

					if ( texture.type === UnsignedIntType ) {

						typePrefix = 'u';

					} else if ( texture.type === IntType ) {

						typePrefix = 'i';

					}

				}

				if ( uniform.type === 'texture3D' && texture.isArrayTexture === false ) {

					snippet = `${typePrefix}sampler3D ${ uniform.name };`;

				} else if ( texture.compareFunction ) {

					if ( texture.isArrayTexture === true ) {

						snippet = `sampler2DArrayShadow ${ uniform.name };`;

					} else {

						snippet = `sampler2DShadow ${ uniform.name };`;

					}

				} else if ( texture.isArrayTexture === true || texture.isDataArrayTexture === true || texture.isCompressedArrayTexture === true ) {

					snippet = `${typePrefix}sampler2DArray ${ uniform.name };`;

				} else {

					snippet = `${typePrefix}sampler2D ${ uniform.name };`;

				}

			} else if ( uniform.type === 'cubeTexture' ) {

				snippet = `samplerCube ${ uniform.name };`;

			} else if ( uniform.type === 'buffer' ) {

				const bufferNode = uniform.node;
				const bufferType = this.getType( bufferNode.bufferType );
				const bufferCount = bufferNode.bufferCount;

				const bufferCountSnippet = bufferCount > 0 ? bufferCount : '';
				snippet = `${bufferNode.name} {\n\t${ bufferType } ${ uniform.name }[${ bufferCountSnippet }];\n};\n`;

			} else {

				const vectorType = this.getVectorType( uniform.type );

				snippet = `${ vectorType } ${ this.getPropertyName( uniform, shaderStage ) };`;

				group = true;

			}

			const precision = uniform.node.precision;

			if ( precision !== null ) {

				snippet = precisionLib[ precision ] + ' ' + snippet;

			}

			if ( group ) {

				snippet = '\t' + snippet;

				const groupName = uniform.groupNode.name;
				const groupSnippets = uniformGroups[ groupName ] || ( uniformGroups[ groupName ] = [] );

				groupSnippets.push( snippet );

			} else {

				snippet = 'uniform ' + snippet;

				bindingSnippets.push( snippet );

			}

		}

		let output = '';

		for ( const name in uniformGroups ) {

			const groupSnippets = uniformGroups[ name ];

			output += this._getGLSLUniformStruct( shaderStage + '_' + name, groupSnippets.join( '\n' ) ) + '\n';

		}

		output += bindingSnippets.join( '\n' );

		return output;

	}
```
</details>

### `GLSLNodeBuilder.getTypeFromAttribute(attribute: BufferAttribute): string`

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

- `super.getTypeFromAttribute`
- `/^[iu]/.test`
- `nodeType.slice`

<details><summary>Code</summary>

```typescript
getTypeFromAttribute( attribute ) {

		let nodeType = super.getTypeFromAttribute( attribute );

		if ( /^[iu]/.test( nodeType ) && attribute.gpuType !== IntType ) {

			let dataAttribute = attribute;

			if ( attribute.isInterleavedBufferAttribute ) dataAttribute = attribute.data;

			const array = dataAttribute.array;

			if ( ( array instanceof Uint32Array || array instanceof Int32Array ) === false ) {

				nodeType = nodeType.slice( 1 );

			}

		}

		return nodeType;

	}
```
</details>

### `GLSLNodeBuilder.getAttributes(shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the shader attributes of the given shader stage as a GLSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The GLSL snippet that defines the shader attributes.
	 */
```

**Parameters:**

- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `this.getAttributesArray`

<details><summary>Code</summary>

```typescript
getAttributes( shaderStage ) {

		let snippet = '';

		if ( shaderStage === 'vertex' || shaderStage === 'compute' ) {

			const attributes = this.getAttributesArray();

			let location = 0;

			for ( const attribute of attributes ) {

				snippet += `layout( location = ${ location ++ } ) in ${ attribute.type } ${ attribute.name };\n`;

			}

		}

		return snippet;

	}
```
</details>

### `GLSLNodeBuilder.getStructMembers(struct: StructTypeNode): string`

**JSDoc:**
```typescript
/**
	 * Returns the members of the given struct type node as a GLSL string.
	 *
	 * @param {StructTypeNode} struct - The struct type node.
	 * @return {string} The GLSL snippet that defines the struct members.
	 */
```

**Parameters:**

- **`struct`** `StructTypeNode`

**Returns:** `string`

**Calls:**

- `snippets.push`
- `snippets.join`

<details><summary>Code</summary>

```typescript
getStructMembers( struct ) {

		const snippets = [];

		for ( const member of struct.members ) {

			snippets.push( `\t${ member.type } ${ member.name };` );

		}

		return snippets.join( '\n' );

	}
```
</details>

### `GLSLNodeBuilder.getStructs(shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the structs of the given shader stage as a GLSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The GLSL snippet that defines the structs.
	 */
```

**Parameters:**

- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `outputSnippet.push`
- `this.getStructMembers`
- `snippets.push`
- `outputSnippet.join`
- `snippets.join`

<details><summary>Code</summary>

```typescript
getStructs( shaderStage ) {

		const snippets = [];
		const structs = this.structs[ shaderStage ];

		const outputSnippet = [];

		for ( const struct of structs ) {

			if ( struct.output ) {

				for ( const member of struct.members ) {

					outputSnippet.push( `layout( location = ${ member.index } ) out ${ member.type } ${ member.name };` );

				}

			} else {

				let snippet = 'struct ' + struct.name + ' {\n';
				snippet += this.getStructMembers( struct );
				snippet += '\n};\n';

				snippets.push( snippet );

			}

		}

		if ( outputSnippet.length === 0 ) {

			outputSnippet.push( 'layout( location = 0 ) out vec4 fragColor;' );

		}

		return '\n' + outputSnippet.join( '\n' ) + '\n\n' + snippets.join( '\n' );

	}
```
</details>

### `GLSLNodeBuilder.getVaryings(shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the varyings of the given shader stage as a GLSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The GLSL snippet that defines the varyings.
	 */
```

**Parameters:**

- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `this.getType`
- `type.includes`

<details><summary>Code</summary>

```typescript
getVaryings( shaderStage ) {

		let snippet = '';

		const varyings = this.varyings;

		if ( shaderStage === 'vertex' || shaderStage === 'compute' ) {

			for ( const varying of varyings ) {

				if ( shaderStage === 'compute' ) varying.needsInterpolation = true;

				const type = this.getType( varying.type );

				if ( varying.needsInterpolation ) {

					if ( varying.interpolationType ) {

						const interpolationType = interpolationTypeMap[ varying.interpolationType ] || varying.interpolationType;
						const sampling = interpolationModeMap[ varying.interpolationSampling ] || '';

						snippet += `${ interpolationType } ${ sampling } out ${ type } ${ varying.name };\n`;

					} else {

						const flat = type.includes( 'int' ) || type.includes( 'uv' ) || type.includes( 'iv' ) ? 'flat ' : '';

						snippet += `${ flat }out ${ type } ${ varying.name };\n`;

					}

				} else {

					snippet += `${type} ${varying.name};\n`; // generate variable (no varying required)

				}

			}

		} else if ( shaderStage === 'fragment' ) {

			for ( const varying of varyings ) {

				if ( varying.needsInterpolation ) {

					const type = this.getType( varying.type );

					if ( varying.interpolationType ) {

						const interpolationType = interpolationTypeMap[ varying.interpolationType ] || varying.interpolationType;
						const sampling = interpolationModeMap[ varying.interpolationSampling ] || '';

						snippet += `${ interpolationType } ${ sampling } in ${ type } ${ varying.name };\n`;


					} else {

						const flat = type.includes( 'int' ) || type.includes( 'uv' ) || type.includes( 'iv' ) ? 'flat ' : '';

						snippet += `${ flat }in ${ type } ${ varying.name };\n`;

					}

				}

			}

		}

		for ( const builtin of this.builtins[ shaderStage ] ) {

			snippet += `${builtin};\n`;

		}

		return snippet;

	}
```
</details>

### `GLSLNodeBuilder.getVertexIndex(): string`

**JSDoc:**
```typescript
/**
	 * Returns the vertex index builtin.
	 *
	 * @return {string} The vertex index.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getVertexIndex() {

		return 'uint( gl_VertexID )';

	}
```
</details>

### `GLSLNodeBuilder.getInstanceIndex(): string`

**JSDoc:**
```typescript
/**
	 * Returns the instance index builtin.
	 *
	 * @return {string} The instance index.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getInstanceIndex() {

		return 'uint( gl_InstanceID )';

	}
```
</details>

### `GLSLNodeBuilder.getInvocationLocalIndex(): string`

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

- `workgroupSize.reduce`

<details><summary>Code</summary>

```typescript
getInvocationLocalIndex() {

		const workgroupSize = this.object.workgroupSize;

		const size = workgroupSize.reduce( ( acc, curr ) => acc * curr, 1 );

		return `uint( gl_InstanceID ) % ${size}u`;

	}
```
</details>

### `GLSLNodeBuilder.getDrawIndex(): string`

**JSDoc:**
```typescript
/**
	 * Returns the draw index builtin.
	 *
	 * @return {?string} The drawIndex shader string. Returns `null` if `WEBGL_multi_draw` isn't supported by the device.
	 */
```

**Returns:** `string`

**Calls:**

- `extensions.has`

<details><summary>Code</summary>

```typescript
getDrawIndex() {

		const extensions = this.renderer.backend.extensions;

		if ( extensions.has( 'WEBGL_multi_draw' ) ) {

			return 'uint( gl_DrawID )';

		}

		return null;

	}
```
</details>

### `GLSLNodeBuilder.getFrontFacing(): string`

**JSDoc:**
```typescript
/**
	 * Returns the front facing builtin.
	 *
	 * @return {string} The front facing builtin.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getFrontFacing() {

		return 'gl_FrontFacing';

	}
```
</details>

### `GLSLNodeBuilder.getFragCoord(): string`

**JSDoc:**
```typescript
/**
	 * Returns the frag coord builtin.
	 *
	 * @return {string} The frag coord builtin.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getFragCoord() {

		return 'gl_FragCoord.xy';

	}
```
</details>

### `GLSLNodeBuilder.getFragDepth(): string`

**JSDoc:**
```typescript
/**
	 * Returns the frag depth builtin.
	 *
	 * @return {string} The frag depth builtin.
	 */
```

**Returns:** `string`

<details><summary>Code</summary>

```typescript
getFragDepth() {

		return 'gl_FragDepth';

	}
```
</details>

### `GLSLNodeBuilder.enableExtension(name: string, behavior: string, shaderStage: string): void`

**JSDoc:**
```typescript
/**
	 * Enables the given extension.
	 *
	 * @param {string} name - The extension name.
	 * @param {string} behavior - The extension behavior.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage.
	 */
```

**Parameters:**

- **`name`** `string`
- **`behavior`** `string`
- **`shaderStage`** `string`

**Returns:** `void`

**Calls:**

- `map.has`
- `map.set`

<details><summary>Code</summary>

```typescript
enableExtension( name, behavior, shaderStage = this.shaderStage ) {

		const map = this.extensions[ shaderStage ] || ( this.extensions[ shaderStage ] = new Map() );

		if ( map.has( name ) === false ) {

			map.set( name, {
				name,
				behavior
			} );

		}

	}
```
</details>

### `GLSLNodeBuilder.getExtensions(shaderStage: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the enabled extensions of the given shader stage as a GLSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The GLSL snippet that defines the enabled extensions.
	 */
```

**Parameters:**

- **`shaderStage`** `string`

**Returns:** `string`

**Calls:**

- `ext.has`
- `this.enableExtension`
- `extensions.values`
- `snippets.push`
- `snippets.join`

<details><summary>Code</summary>

```typescript
getExtensions( shaderStage ) {

		const snippets = [];

		if ( shaderStage === 'vertex' ) {

			const ext = this.renderer.backend.extensions;
			const isBatchedMesh = this.object.isBatchedMesh;

			if ( isBatchedMesh && ext.has( 'WEBGL_multi_draw' ) ) {

				this.enableExtension( 'GL_ANGLE_multi_draw', 'require', shaderStage );

			}

		}

		const extensions = this.extensions[ shaderStage ];

		if ( extensions !== undefined ) {

			for ( const { name, behavior } of extensions.values() ) {

				snippets.push( `#extension ${name} : ${behavior}` );

			}

		}

		return snippets.join( '\n' );

	}
```
</details>

### `GLSLNodeBuilder.getClipDistance(): string`

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

		return 'gl_ClipDistance';

	}
```
</details>

### `GLSLNodeBuilder.isAvailable(name: string): boolean`

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

- `extensions.has`
- `extensions.get`

<details><summary>Code</summary>

```typescript
isAvailable( name ) {

		let result = supports[ name ];

		if ( result === undefined ) {

			let extensionName;

			result = false;

			switch ( name ) {

				case 'float32Filterable':
					extensionName = 'OES_texture_float_linear';
					break;

				case 'clipDistance':
					extensionName = 'WEBGL_clip_cull_distance';
					break;

			}

			if ( extensionName !== undefined ) {

				const extensions = this.renderer.backend.extensions;

				if ( extensions.has( extensionName ) ) {

					extensions.get( extensionName );
					result = true;

				}

			}

			supports[ name ] = result;

		}

		return result;

	}
```
</details>

### `GLSLNodeBuilder.isFlipY(): boolean`

**JSDoc:**
```typescript
/**
	 * Whether to flip texture data along its vertical axis or not.
	 *
	 * @return {boolean} Returns always `true` in context of GLSL.
	 */
```

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
isFlipY() {

		return true;

	}
```
</details>

### `GLSLNodeBuilder.enableHardwareClipping(planeCount: string): void`

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

- `this.enableExtension`
- `this.builtins[ 'vertex' ].push`

<details><summary>Code</summary>

```typescript
enableHardwareClipping( planeCount ) {

		this.enableExtension( 'GL_ANGLE_clip_cull_distance', 'require' );

		this.builtins[ 'vertex' ].push( `out float gl_ClipDistance[ ${ planeCount } ]` );

	}
```
</details>

### `GLSLNodeBuilder.enableMultiview(): void`

**JSDoc:**
```typescript
/**
	 * Enables multiview.
	 */
```

**Returns:** `void`

**Calls:**

- `this.enableExtension`
- `this.builtins[ 'vertex' ].push`

<details><summary>Code</summary>

```typescript
enableMultiview() {

		this.enableExtension( 'GL_OVR_multiview2', 'require', 'fragment' );
		this.enableExtension( 'GL_OVR_multiview2', 'require', 'vertex' );

		this.builtins[ 'vertex' ].push( 'layout(num_views = 2) in' );

	}
```
</details>

### `GLSLNodeBuilder.registerTransform(varyingName: string, attributeNode: AttributeNode): void`

**JSDoc:**
```typescript
/**
	 * Registers a transform in context of Transform Feedback.
	 *
	 * @param {string} varyingName - The varying name.
	 * @param {AttributeNode} attributeNode - The attribute node.
	 */
```

**Parameters:**

- **`varyingName`** `string`
- **`attributeNode`** `AttributeNode`

**Returns:** `void`

**Calls:**

- `this.transforms.push`

<details><summary>Code</summary>

```typescript
registerTransform( varyingName, attributeNode ) {

		this.transforms.push( { varyingName, attributeNode } );

	}
```
</details>

### `GLSLNodeBuilder.getTransforms(): string`

**JSDoc:**
```typescript
/**
	 * Returns the transforms of the given shader stage as a GLSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The GLSL snippet that defines the transforms.
	 */
```

**Returns:** `string`

**Calls:**

- `this.getPropertyName`

<details><summary>Code</summary>

```typescript
getTransforms( /* shaderStage  */ ) {

		const transforms = this.transforms;

		let snippet = '';

		for ( let i = 0; i < transforms.length; i ++ ) {

			const transform = transforms[ i ];
			const attributeName = this.getPropertyName( transform.attributeNode );

			if ( attributeName ) snippet += `${ transform.varyingName } = ${ attributeName };\n\t`;

		}

		return snippet;

	}
```
</details>

### `GLSLNodeBuilder._getGLSLUniformStruct(name: string, vars: string): string`

**JSDoc:**
```typescript
/**
	 * Returns a GLSL struct based on the given name and variables.
	 *
	 * @private
	 * @param {string} name - The struct name.
	 * @param {string} vars - The struct variables.
	 * @return {string} The GLSL snippet representing a struct.
	 */
```

**Parameters:**

- **`name`** `string`
- **`vars`** `string`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
_getGLSLUniformStruct( name, vars ) {

		return `
layout( std140 ) uniform ${name} {
${vars}
};`;

	}
```
</details>

### `GLSLNodeBuilder._getGLSLVertexCode(shaderData: any): string`

**JSDoc:**
```typescript
/**
	 * Returns a GLSL vertex shader based on the given shader data.
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
_getGLSLVertexCode( shaderData ) {

		return `#version 300 es

${ this.getSignature() }

// extensions
${shaderData.extensions}

// precision
${ defaultPrecisions }

// uniforms
${shaderData.uniforms}

// varyings
${shaderData.varyings}

// attributes
${shaderData.attributes}

// codes
${shaderData.codes}

void main() {

	// vars
	${shaderData.vars}

	// transforms
	${shaderData.transforms}

	// flow
	${shaderData.flow}

	gl_PointSize = 1.0;

}
`;

	}
```
</details>

### `GLSLNodeBuilder._getGLSLFragmentCode(shaderData: any): string`

**JSDoc:**
```typescript
/**
	 * Returns a GLSL fragment shader based on the given shader data.
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
_getGLSLFragmentCode( shaderData ) {

		return `#version 300 es

${ this.getSignature() }

// extensions
${shaderData.extensions}

// precision
${ defaultPrecisions }

// uniforms
${shaderData.uniforms}

// varyings
${shaderData.varyings}

// codes
${shaderData.codes}

// structs
${shaderData.structs}

void main() {

	// vars
	${shaderData.vars}

	// flow
	${shaderData.flow}

}
`;

	}
```
</details>

### `GLSLNodeBuilder.buildCode(): void`

**JSDoc:**
```typescript
/**
	 * Controls the code build of the shader stages.
	 */
```

**Returns:** `void`

**Calls:**

- `this.sortBindingGroups`
- `this.getFlowData`
- `this.getExtensions`
- `this.getUniforms`
- `this.getAttributes`
- `this.getVaryings`
- `this.getVars`
- `this.getStructs`
- `this.getCodes`
- `this.getTransforms`
- `this._getGLSLVertexCode`
- `this._getGLSLFragmentCode`

<details><summary>Code</summary>

```typescript
buildCode() {

		const shadersData = this.material !== null ? { fragment: {}, vertex: {} } : { compute: {} };

		this.sortBindingGroups();

		for ( const shaderStage in shadersData ) {

			let flow = '// code\n\n';
			flow += this.flowCode[ shaderStage ];

			const flowNodes = this.flowNodes[ shaderStage ];
			const mainNode = flowNodes[ flowNodes.length - 1 ];

			for ( const node of flowNodes ) {

				const flowSlotData = this.getFlowData( node/*, shaderStage*/ );
				const slotName = node.name;

				if ( slotName ) {

					if ( flow.length > 0 ) flow += '\n';

					flow += `\t// flow -> ${ slotName }\n\t`;

				}

				flow += `${ flowSlotData.code }\n\t`;

				if ( node === mainNode && shaderStage !== 'compute' ) {

					flow += '// result\n\t';

					if ( shaderStage === 'vertex' ) {

						flow += 'gl_Position = ';
						flow += `${ flowSlotData.result };`;

					} else if ( shaderStage === 'fragment' ) {

						if ( ! node.outputNode.isOutputStructNode ) {

							flow += 'fragColor = ';
							flow += `${ flowSlotData.result };`;

						}

					}

				}

			}

			const stageData = shadersData[ shaderStage ];

			stageData.extensions = this.getExtensions( shaderStage );
			stageData.uniforms = this.getUniforms( shaderStage );
			stageData.attributes = this.getAttributes( shaderStage );
			stageData.varyings = this.getVaryings( shaderStage );
			stageData.vars = this.getVars( shaderStage );
			stageData.structs = this.getStructs( shaderStage );
			stageData.codes = this.getCodes( shaderStage );
			stageData.transforms = this.getTransforms( shaderStage );
			stageData.flow = flow;

		}

		if ( this.material !== null ) {

			this.vertexShader = this._getGLSLVertexCode( shadersData.vertex );
			this.fragmentShader = this._getGLSLFragmentCode( shadersData.fragment );

		} else {

			this.computeShader = this._getGLSLVertexCode( shadersData.compute );

		}

	}
```
</details>

### `GLSLNodeBuilder.getUniformFromNode(node: UniformNode, type: string, shaderStage: string, name: string): NodeUniform`

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
- `bindings.push`
- `this.getNodeUniform`
- `uniformsGroup.addUniform`

**Internal Comments:**
```
//uniformsGroup.setVisibility( gpuShaderStageLib[ shaderStage ] ); (x4)
```

<details><summary>Code</summary>

```typescript
getUniformFromNode( node, type, shaderStage, name = null ) {

		const uniformNode = super.getUniformFromNode( node, type, shaderStage, name );
		const nodeData = this.getDataFromNode( node, shaderStage, this.globalCache );

		let uniformGPU = nodeData.uniformGPU;

		if ( uniformGPU === undefined ) {

			const group = node.groupNode;
			const groupName = group.name;

			const bindings = this.getBindGroupArray( groupName, shaderStage );

			if ( type === 'texture' ) {

				uniformGPU = new NodeSampledTexture( uniformNode.name, uniformNode.node, group );
				bindings.push( uniformGPU );

			} else if ( type === 'cubeTexture' ) {

				uniformGPU = new NodeSampledCubeTexture( uniformNode.name, uniformNode.node, group );
				bindings.push( uniformGPU );

			} else if ( type === 'texture3D' ) {

				uniformGPU = new NodeSampledTexture3D( uniformNode.name, uniformNode.node, group );
				bindings.push( uniformGPU );

			} else if ( type === 'buffer' ) {

				node.name = `NodeBuffer_${ node.id }`;
				uniformNode.name = `buffer${ node.id }`;

				const buffer = new NodeUniformBuffer( node, group );
				buffer.name = node.name;

				bindings.push( buffer );

				uniformGPU = buffer;

			} else {

				const uniformsStage = this.uniformGroups[ shaderStage ] || ( this.uniformGroups[ shaderStage ] = {} );

				let uniformsGroup = uniformsStage[ groupName ];

				if ( uniformsGroup === undefined ) {

					uniformsGroup = new NodeUniformsGroup( shaderStage + '_' + groupName, group );
					//uniformsGroup.setVisibility( gpuShaderStageLib[ shaderStage ] );

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


---

## Classes

### `GLSLNodeBuilder`

<details><summary>Class Code</summary>

```ts
class GLSLNodeBuilder extends NodeBuilder {

	/**
	 * Constructs a new GLSL node builder renderer.
	 *
	 * @param {Object3D} object - The 3D object.
	 * @param {Renderer} renderer - The renderer.
	 */
	constructor( object, renderer ) {

		super( object, renderer, new GLSLNodeParser() );

		/**
		 * A dictionary holds for each shader stage ('vertex', 'fragment', 'compute')
		 * another dictionary which manages UBOs per group ('render','frame','object').
		 *
		 * @type {Object<string,Object<string,NodeUniformsGroup>>}
		 */
		this.uniformGroups = {};

		/**
		 * An array that holds objects defining the varying and attribute data in
		 * context of Transform Feedback.
		 *
		 * @type {Array<Object<string,AttributeNode|string>>}
		 */
		this.transforms = [];

		/**
		 * A dictionary that holds for each shader stage a Map of used extensions.
		 *
		 * @type {Object<string,Map<string,Object>>}
		 */
		this.extensions = {};

		/**
		 * A dictionary that holds for each shader stage an Array of used builtins.
		 *
		 * @type {Object<string,Array<string>>}
		 */
		this.builtins = { vertex: [], fragment: [], compute: [] };

	}

	/**
	 * Checks if the given texture requires a manual conversion to the working color space.
	 *
	 * @param {Texture} texture - The texture to check.
	 * @return {boolean} Whether the given texture requires a conversion to working color space or not.
	 */
	needsToWorkingColorSpace( texture ) {

		return texture.isVideoTexture === true && texture.colorSpace !== NoColorSpace;

	}

	/**
	 * Returns the native shader method name for a given generic name.
	 *
	 * @param {string} method - The method name to resolve.
	 * @return {string} The resolved GLSL method name.
	 */
	getMethod( method ) {

		return glslMethods[ method ] || method;

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

		return `${condSnippet} ? ${ifSnippet} : ${elseSnippet}`;

	}

	/**
	 * Returns the output struct name. Not relevant for GLSL.
	 *
	 * @return {string}
	 */
	getOutputStructName() {

		return '';

	}

	/**
	 * Builds the given shader node.
	 *
	 * @param {ShaderNodeInternal} shaderNode - The shader node.
	 * @return {string} The GLSL function code.
	 */
	buildFunctionCode( shaderNode ) {

		const layout = shaderNode.layout;
		const flowData = this.flowShaderNode( shaderNode );

		const parameters = [];

		for ( const input of layout.inputs ) {

			parameters.push( this.getType( input.type ) + ' ' + input.name );

		}

		//

		const code = `${ this.getType( layout.type ) } ${ layout.name }( ${ parameters.join( ', ' ) } ) {

	${ flowData.vars }

${ flowData.code }
	return ${ flowData.result };

}`;

		//

		return code;

	}

	/**
	 * Setups the Pixel Buffer Object (PBO) for the given storage
	 * buffer node.
	 *
	 * @param {StorageBufferNode} storageBufferNode - The storage buffer node.
	 */
	setupPBO( storageBufferNode ) {

		const attribute = storageBufferNode.value;

		if ( attribute.pbo === undefined ) {

			const originalArray = attribute.array;
			const numElements = attribute.count * attribute.itemSize;

			const { itemSize } = attribute;

			const isInteger = attribute.array.constructor.name.toLowerCase().includes( 'int' );

			let format = isInteger ? RedIntegerFormat : RedFormat;

			if ( itemSize === 2 ) {

				format = isInteger ? RGIntegerFormat : RGFormat;

			} else if ( itemSize === 3 ) {

				format = isInteger ? RGBIntegerFormat : RGBFormat;

			} else if ( itemSize === 4 ) {

				format = isInteger ? RGBAIntegerFormat : RGBAFormat;

			}

			const typeMap = {
				Float32Array: FloatType,
				Uint8Array: UnsignedByteType,
				Uint16Array: UnsignedShortType,
				Uint32Array: UnsignedIntType,
				Int8Array: ByteType,
				Int16Array: ShortType,
				Int32Array: IntType,
				Uint8ClampedArray: UnsignedByteType,
			};

			const width = Math.pow( 2, Math.ceil( Math.log2( Math.sqrt( numElements / itemSize ) ) ) );
			let height = Math.ceil( ( numElements / itemSize ) / width );
			if ( width * height * itemSize < numElements ) height ++; // Ensure enough space

			const newSize = width * height * itemSize;

			const newArray = new originalArray.constructor( newSize );

			newArray.set( originalArray, 0 );

			attribute.array = newArray;

			const pboTexture = new DataTexture( attribute.array, width, height, format, typeMap[ attribute.array.constructor.name ] || FloatType );
			pboTexture.needsUpdate = true;
			pboTexture.isPBOTexture = true;

			const pbo = new TextureNode( pboTexture, null, null );
			pbo.setPrecision( 'high' );

			attribute.pboNode = pbo;
			attribute.pbo = pbo.value;

			this.getUniformFromNode( attribute.pboNode, 'texture', this.shaderStage, this.context.nodeName );

		}

	}

	/**
	 * Returns a GLSL snippet that represents the property name of the given node.
	 *
	 * @param {Node} node - The node.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The property name.
	 */
	getPropertyName( node, shaderStage = this.shaderStage ) {

		if ( node.isNodeUniform && node.node.isTextureNode !== true && node.node.isBufferNode !== true ) {

			return shaderStage.charAt( 0 ) + '_' + node.name;

		}

		return super.getPropertyName( node, shaderStage );

	}

	/**
	 * Setups the Pixel Buffer Object (PBO) for the given storage
	 * buffer node.
	 *
	 * @param {StorageArrayElementNode} storageArrayElementNode - The storage array element node.
	 * @return {string} The property name.
	 */
	generatePBO( storageArrayElementNode ) {

		const { node, indexNode } = storageArrayElementNode;
		const attribute = node.value;

		if ( this.renderer.backend.has( attribute ) ) {

			const attributeData = this.renderer.backend.get( attribute );
			attributeData.pbo = attribute.pbo;

		}

		const nodeUniform = this.getUniformFromNode( attribute.pboNode, 'texture', this.shaderStage, this.context.nodeName );
		const textureName = this.getPropertyName( nodeUniform );

		this.increaseUsage( indexNode ); // force cache generate to be used as index in x,y
		const indexSnippet = indexNode.build( this, 'uint' );

		const elementNodeData = this.getDataFromNode( storageArrayElementNode );

		let propertyName = elementNodeData.propertyName;

		if ( propertyName === undefined ) {

			// property element

			const nodeVar = this.getVarFromNode( storageArrayElementNode );

			propertyName = this.getPropertyName( nodeVar );

			// property size

			const bufferNodeData = this.getDataFromNode( node );

			let propertySizeName = bufferNodeData.propertySizeName;

			if ( propertySizeName === undefined ) {

				propertySizeName = propertyName + 'Size';

				this.getVarFromNode( node, propertySizeName, 'uint' );

				this.addLineFlowCode( `${ propertySizeName } = uint( textureSize( ${ textureName }, 0 ).x )`, storageArrayElementNode );

				bufferNodeData.propertySizeName = propertySizeName;

			}

			//

			const { itemSize } = attribute;

			const channel = '.' + vectorComponents.join( '' ).slice( 0, itemSize );
			const uvSnippet = `ivec2(${indexSnippet} % ${ propertySizeName }, ${indexSnippet} / ${ propertySizeName })`;

			const snippet = this.generateTextureLoad( null, textureName, uvSnippet, null, '0' );

			//


			let prefix = 'vec4';

			if ( attribute.pbo.type === UnsignedIntType ) {

				prefix = 'uvec4';

			} else if ( attribute.pbo.type === IntType ) {

				prefix = 'ivec4';

			}

			this.addLineFlowCode( `${ propertyName } = ${prefix}(${ snippet })${channel}`, storageArrayElementNode );

			elementNodeData.propertyName = propertyName;

		}

		return propertyName;

	}

	/**
	 * Generates the GLSL snippet that reads a single texel from a texture without sampling or filtering.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvIndexSnippet - A GLSL snippet that represents texture coordinates used for sampling.
	 * @param {?string} depthSnippet - A GLSL snippet that represents the 0-based texture array index to sample.
	 * @param {string} [levelSnippet='0u'] - A GLSL snippet that represents the mip level, with level 0 containing a full size version of the texture.
	 * @return {string} The GLSL snippet.
	 */
	generateTextureLoad( texture, textureProperty, uvIndexSnippet, depthSnippet, levelSnippet = '0' ) {

		if ( depthSnippet ) {

			return `texelFetch( ${ textureProperty }, ivec3( ${ uvIndexSnippet }, ${ depthSnippet } ), ${ levelSnippet } )`;

		} else {

			return `texelFetch( ${ textureProperty }, ${ uvIndexSnippet }, ${ levelSnippet } )`;

		}

	}

	/**
	 * Generates the GLSL snippet for sampling/loading the given texture.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A GLSL snippet that represents texture coordinates used for sampling.
	 * @param {?string} depthSnippet -  A GLSL snippet that represents the 0-based texture array index to sample.
	 * @return {string} The GLSL snippet.
	 */
	generateTexture( texture, textureProperty, uvSnippet, depthSnippet ) {

		if ( texture.isDepthTexture ) {

			if ( depthSnippet ) uvSnippet = `vec4( ${ uvSnippet }, ${ depthSnippet } )`;

			return `texture( ${ textureProperty }, ${ uvSnippet } ).x`;

		} else {

			if ( depthSnippet ) uvSnippet = `vec3( ${ uvSnippet }, ${ depthSnippet } )`;

			return `texture( ${ textureProperty }, ${ uvSnippet } )`;

		}

	}

	/**
	 * Generates the GLSL snippet when sampling textures with explicit mip level.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A GLSL snippet that represents texture coordinates used for sampling.
	 * @param {string} levelSnippet - A GLSL snippet that represents the mip level, with level 0 containing a full size version of the texture.
	 * @return {string} The GLSL snippet.
	 */
	generateTextureLevel( texture, textureProperty, uvSnippet, levelSnippet ) {

		return `textureLod( ${ textureProperty }, ${ uvSnippet }, ${ levelSnippet } )`;

	}

	/**
	 * Generates the GLSL snippet when sampling textures with a bias to the mip level.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A GLSL snippet that represents texture coordinates used for sampling.
	 * @param {string} biasSnippet - A GLSL snippet that represents the bias to apply to the mip level before sampling.
	 * @return {string} The GLSL snippet.
	 */
	generateTextureBias( texture, textureProperty, uvSnippet, biasSnippet ) {

		return `texture( ${ textureProperty }, ${ uvSnippet }, ${ biasSnippet } )`;

	}

	/**
	 * Generates the GLSL snippet for sampling/loading the given texture using explicit gradients.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A GLSL snippet that represents texture coordinates used for sampling.
	 * @param {Array<string>} gradSnippet - An array holding both gradient GLSL snippets.
	 * @return {string} The GLSL snippet.
	 */
	generateTextureGrad( texture, textureProperty, uvSnippet, gradSnippet ) {

		return `textureGrad( ${ textureProperty }, ${ uvSnippet }, ${ gradSnippet[ 0 ] }, ${ gradSnippet[ 1 ] } )`;

	}

	/**
	 * Generates the GLSL snippet for sampling a depth texture and comparing the sampled depth values
	 * against a reference value.
	 *
	 * @param {Texture} texture - The texture.
	 * @param {string} textureProperty - The name of the texture uniform in the shader.
	 * @param {string} uvSnippet - A GLSL snippet that represents texture coordinates used for sampling.
	 * @param {string} compareSnippet -  A GLSL snippet that represents the reference value.
	 * @param {?string} depthSnippet - A GLSL snippet that represents 0-based texture array index to sample.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage this code snippet is generated for.
	 * @return {string} The GLSL snippet.
	 */
	generateTextureCompare( texture, textureProperty, uvSnippet, compareSnippet, depthSnippet, shaderStage = this.shaderStage ) {

		if ( shaderStage === 'fragment' ) {

			if ( depthSnippet ) {

				return `texture( ${ textureProperty }, vec4( ${ uvSnippet }, ${ depthSnippet }, ${ compareSnippet } ) )`;

			}

			return `texture( ${ textureProperty }, vec3( ${ uvSnippet }, ${ compareSnippet } ) )`;

		} else {

			console.error( `WebGPURenderer: THREE.DepthTexture.compareFunction() does not support ${ shaderStage } shader.` );

		}

	}

	/**
	 * Returns the variables of the given shader stage as a GLSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The GLSL snippet that defines the variables.
	 */
	getVars( shaderStage ) {

		const snippets = [];

		const vars = this.vars[ shaderStage ];

		if ( vars !== undefined ) {

			for ( const variable of vars ) {

				snippets.push( `${ this.getVar( variable.type, variable.name, variable.count ) };` );

			}

		}

		return snippets.join( '\n\t' );

	}

	/**
	 * Returns the uniforms of the given shader stage as a GLSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The GLSL snippet that defines the uniforms.
	 */
	getUniforms( shaderStage ) {

		const uniforms = this.uniforms[ shaderStage ];

		const bindingSnippets = [];
		const uniformGroups = {};

		for ( const uniform of uniforms ) {

			let snippet = null;
			let group = false;

			if ( uniform.type === 'texture' || uniform.type === 'texture3D' ) {

				const texture = uniform.node.value;

				let typePrefix = '';

				if ( texture.isDataTexture === true || texture.isData3DTexture === true ) {

					if ( texture.type === UnsignedIntType ) {

						typePrefix = 'u';

					} else if ( texture.type === IntType ) {

						typePrefix = 'i';

					}

				}

				if ( uniform.type === 'texture3D' && texture.isArrayTexture === false ) {

					snippet = `${typePrefix}sampler3D ${ uniform.name };`;

				} else if ( texture.compareFunction ) {

					if ( texture.isArrayTexture === true ) {

						snippet = `sampler2DArrayShadow ${ uniform.name };`;

					} else {

						snippet = `sampler2DShadow ${ uniform.name };`;

					}

				} else if ( texture.isArrayTexture === true || texture.isDataArrayTexture === true || texture.isCompressedArrayTexture === true ) {

					snippet = `${typePrefix}sampler2DArray ${ uniform.name };`;

				} else {

					snippet = `${typePrefix}sampler2D ${ uniform.name };`;

				}

			} else if ( uniform.type === 'cubeTexture' ) {

				snippet = `samplerCube ${ uniform.name };`;

			} else if ( uniform.type === 'buffer' ) {

				const bufferNode = uniform.node;
				const bufferType = this.getType( bufferNode.bufferType );
				const bufferCount = bufferNode.bufferCount;

				const bufferCountSnippet = bufferCount > 0 ? bufferCount : '';
				snippet = `${bufferNode.name} {\n\t${ bufferType } ${ uniform.name }[${ bufferCountSnippet }];\n};\n`;

			} else {

				const vectorType = this.getVectorType( uniform.type );

				snippet = `${ vectorType } ${ this.getPropertyName( uniform, shaderStage ) };`;

				group = true;

			}

			const precision = uniform.node.precision;

			if ( precision !== null ) {

				snippet = precisionLib[ precision ] + ' ' + snippet;

			}

			if ( group ) {

				snippet = '\t' + snippet;

				const groupName = uniform.groupNode.name;
				const groupSnippets = uniformGroups[ groupName ] || ( uniformGroups[ groupName ] = [] );

				groupSnippets.push( snippet );

			} else {

				snippet = 'uniform ' + snippet;

				bindingSnippets.push( snippet );

			}

		}

		let output = '';

		for ( const name in uniformGroups ) {

			const groupSnippets = uniformGroups[ name ];

			output += this._getGLSLUniformStruct( shaderStage + '_' + name, groupSnippets.join( '\n' ) ) + '\n';

		}

		output += bindingSnippets.join( '\n' );

		return output;

	}

	/**
	 * Returns the type for a given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute.
	 * @return {string} The type.
	 */
	getTypeFromAttribute( attribute ) {

		let nodeType = super.getTypeFromAttribute( attribute );

		if ( /^[iu]/.test( nodeType ) && attribute.gpuType !== IntType ) {

			let dataAttribute = attribute;

			if ( attribute.isInterleavedBufferAttribute ) dataAttribute = attribute.data;

			const array = dataAttribute.array;

			if ( ( array instanceof Uint32Array || array instanceof Int32Array ) === false ) {

				nodeType = nodeType.slice( 1 );

			}

		}

		return nodeType;

	}

	/**
	 * Returns the shader attributes of the given shader stage as a GLSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The GLSL snippet that defines the shader attributes.
	 */
	getAttributes( shaderStage ) {

		let snippet = '';

		if ( shaderStage === 'vertex' || shaderStage === 'compute' ) {

			const attributes = this.getAttributesArray();

			let location = 0;

			for ( const attribute of attributes ) {

				snippet += `layout( location = ${ location ++ } ) in ${ attribute.type } ${ attribute.name };\n`;

			}

		}

		return snippet;

	}

	/**
	 * Returns the members of the given struct type node as a GLSL string.
	 *
	 * @param {StructTypeNode} struct - The struct type node.
	 * @return {string} The GLSL snippet that defines the struct members.
	 */
	getStructMembers( struct ) {

		const snippets = [];

		for ( const member of struct.members ) {

			snippets.push( `\t${ member.type } ${ member.name };` );

		}

		return snippets.join( '\n' );

	}

	/**
	 * Returns the structs of the given shader stage as a GLSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The GLSL snippet that defines the structs.
	 */
	getStructs( shaderStage ) {

		const snippets = [];
		const structs = this.structs[ shaderStage ];

		const outputSnippet = [];

		for ( const struct of structs ) {

			if ( struct.output ) {

				for ( const member of struct.members ) {

					outputSnippet.push( `layout( location = ${ member.index } ) out ${ member.type } ${ member.name };` );

				}

			} else {

				let snippet = 'struct ' + struct.name + ' {\n';
				snippet += this.getStructMembers( struct );
				snippet += '\n};\n';

				snippets.push( snippet );

			}

		}

		if ( outputSnippet.length === 0 ) {

			outputSnippet.push( 'layout( location = 0 ) out vec4 fragColor;' );

		}

		return '\n' + outputSnippet.join( '\n' ) + '\n\n' + snippets.join( '\n' );

	}

	/**
	 * Returns the varyings of the given shader stage as a GLSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The GLSL snippet that defines the varyings.
	 */
	getVaryings( shaderStage ) {

		let snippet = '';

		const varyings = this.varyings;

		if ( shaderStage === 'vertex' || shaderStage === 'compute' ) {

			for ( const varying of varyings ) {

				if ( shaderStage === 'compute' ) varying.needsInterpolation = true;

				const type = this.getType( varying.type );

				if ( varying.needsInterpolation ) {

					if ( varying.interpolationType ) {

						const interpolationType = interpolationTypeMap[ varying.interpolationType ] || varying.interpolationType;
						const sampling = interpolationModeMap[ varying.interpolationSampling ] || '';

						snippet += `${ interpolationType } ${ sampling } out ${ type } ${ varying.name };\n`;

					} else {

						const flat = type.includes( 'int' ) || type.includes( 'uv' ) || type.includes( 'iv' ) ? 'flat ' : '';

						snippet += `${ flat }out ${ type } ${ varying.name };\n`;

					}

				} else {

					snippet += `${type} ${varying.name};\n`; // generate variable (no varying required)

				}

			}

		} else if ( shaderStage === 'fragment' ) {

			for ( const varying of varyings ) {

				if ( varying.needsInterpolation ) {

					const type = this.getType( varying.type );

					if ( varying.interpolationType ) {

						const interpolationType = interpolationTypeMap[ varying.interpolationType ] || varying.interpolationType;
						const sampling = interpolationModeMap[ varying.interpolationSampling ] || '';

						snippet += `${ interpolationType } ${ sampling } in ${ type } ${ varying.name };\n`;


					} else {

						const flat = type.includes( 'int' ) || type.includes( 'uv' ) || type.includes( 'iv' ) ? 'flat ' : '';

						snippet += `${ flat }in ${ type } ${ varying.name };\n`;

					}

				}

			}

		}

		for ( const builtin of this.builtins[ shaderStage ] ) {

			snippet += `${builtin};\n`;

		}

		return snippet;

	}

	/**
	 * Returns the vertex index builtin.
	 *
	 * @return {string} The vertex index.
	 */
	getVertexIndex() {

		return 'uint( gl_VertexID )';

	}

	/**
	 * Returns the instance index builtin.
	 *
	 * @return {string} The instance index.
	 */
	getInstanceIndex() {

		return 'uint( gl_InstanceID )';

	}

	/**
	 * Returns the invocation local index builtin.
	 *
	 * @return {string} The invocation local index.
	 */
	getInvocationLocalIndex() {

		const workgroupSize = this.object.workgroupSize;

		const size = workgroupSize.reduce( ( acc, curr ) => acc * curr, 1 );

		return `uint( gl_InstanceID ) % ${size}u`;

	}

	/**
	 * Returns the draw index builtin.
	 *
	 * @return {?string} The drawIndex shader string. Returns `null` if `WEBGL_multi_draw` isn't supported by the device.
	 */
	getDrawIndex() {

		const extensions = this.renderer.backend.extensions;

		if ( extensions.has( 'WEBGL_multi_draw' ) ) {

			return 'uint( gl_DrawID )';

		}

		return null;

	}

	/**
	 * Returns the front facing builtin.
	 *
	 * @return {string} The front facing builtin.
	 */
	getFrontFacing() {

		return 'gl_FrontFacing';

	}

	/**
	 * Returns the frag coord builtin.
	 *
	 * @return {string} The frag coord builtin.
	 */
	getFragCoord() {

		return 'gl_FragCoord.xy';

	}

	/**
	 * Returns the frag depth builtin.
	 *
	 * @return {string} The frag depth builtin.
	 */
	getFragDepth() {

		return 'gl_FragDepth';

	}

	/**
	 * Enables the given extension.
	 *
	 * @param {string} name - The extension name.
	 * @param {string} behavior - The extension behavior.
	 * @param {string} [shaderStage=this.shaderStage] - The shader stage.
	 */
	enableExtension( name, behavior, shaderStage = this.shaderStage ) {

		const map = this.extensions[ shaderStage ] || ( this.extensions[ shaderStage ] = new Map() );

		if ( map.has( name ) === false ) {

			map.set( name, {
				name,
				behavior
			} );

		}

	}

	/**
	 * Returns the enabled extensions of the given shader stage as a GLSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The GLSL snippet that defines the enabled extensions.
	 */
	getExtensions( shaderStage ) {

		const snippets = [];

		if ( shaderStage === 'vertex' ) {

			const ext = this.renderer.backend.extensions;
			const isBatchedMesh = this.object.isBatchedMesh;

			if ( isBatchedMesh && ext.has( 'WEBGL_multi_draw' ) ) {

				this.enableExtension( 'GL_ANGLE_multi_draw', 'require', shaderStage );

			}

		}

		const extensions = this.extensions[ shaderStage ];

		if ( extensions !== undefined ) {

			for ( const { name, behavior } of extensions.values() ) {

				snippets.push( `#extension ${name} : ${behavior}` );

			}

		}

		return snippets.join( '\n' );

	}

	/**
	 * Returns the clip distances builtin.
	 *
	 * @return {string} The clip distances builtin.
	 */
	getClipDistance() {

		return 'gl_ClipDistance';

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

			let extensionName;

			result = false;

			switch ( name ) {

				case 'float32Filterable':
					extensionName = 'OES_texture_float_linear';
					break;

				case 'clipDistance':
					extensionName = 'WEBGL_clip_cull_distance';
					break;

			}

			if ( extensionName !== undefined ) {

				const extensions = this.renderer.backend.extensions;

				if ( extensions.has( extensionName ) ) {

					extensions.get( extensionName );
					result = true;

				}

			}

			supports[ name ] = result;

		}

		return result;

	}

	/**
	 * Whether to flip texture data along its vertical axis or not.
	 *
	 * @return {boolean} Returns always `true` in context of GLSL.
	 */
	isFlipY() {

		return true;

	}

	/**
	 * Enables hardware clipping.
	 *
	 * @param {string} planeCount - The clipping plane count.
	 */
	enableHardwareClipping( planeCount ) {

		this.enableExtension( 'GL_ANGLE_clip_cull_distance', 'require' );

		this.builtins[ 'vertex' ].push( `out float gl_ClipDistance[ ${ planeCount } ]` );

	}

	/**
	 * Enables multiview.
	 */
	enableMultiview() {

		this.enableExtension( 'GL_OVR_multiview2', 'require', 'fragment' );
		this.enableExtension( 'GL_OVR_multiview2', 'require', 'vertex' );

		this.builtins[ 'vertex' ].push( 'layout(num_views = 2) in' );

	}

	/**
	 * Registers a transform in context of Transform Feedback.
	 *
	 * @param {string} varyingName - The varying name.
	 * @param {AttributeNode} attributeNode - The attribute node.
	 */
	registerTransform( varyingName, attributeNode ) {

		this.transforms.push( { varyingName, attributeNode } );

	}

	/**
	 * Returns the transforms of the given shader stage as a GLSL string.
	 *
	 * @param {string} shaderStage - The shader stage.
	 * @return {string} The GLSL snippet that defines the transforms.
	 */
	getTransforms( /* shaderStage  */ ) {

		const transforms = this.transforms;

		let snippet = '';

		for ( let i = 0; i < transforms.length; i ++ ) {

			const transform = transforms[ i ];
			const attributeName = this.getPropertyName( transform.attributeNode );

			if ( attributeName ) snippet += `${ transform.varyingName } = ${ attributeName };\n\t`;

		}

		return snippet;

	}

	/**
	 * Returns a GLSL struct based on the given name and variables.
	 *
	 * @private
	 * @param {string} name - The struct name.
	 * @param {string} vars - The struct variables.
	 * @return {string} The GLSL snippet representing a struct.
	 */
	_getGLSLUniformStruct( name, vars ) {

		return `
layout( std140 ) uniform ${name} {
${vars}
};`;

	}

	/**
	 * Returns a GLSL vertex shader based on the given shader data.
	 *
	 * @private
	 * @param {Object} shaderData - The shader data.
	 * @return {string} The vertex shader.
	 */
	_getGLSLVertexCode( shaderData ) {

		return `#version 300 es

${ this.getSignature() }

// extensions
${shaderData.extensions}

// precision
${ defaultPrecisions }

// uniforms
${shaderData.uniforms}

// varyings
${shaderData.varyings}

// attributes
${shaderData.attributes}

// codes
${shaderData.codes}

void main() {

	// vars
	${shaderData.vars}

	// transforms
	${shaderData.transforms}

	// flow
	${shaderData.flow}

	gl_PointSize = 1.0;

}
`;

	}

	/**
	 * Returns a GLSL fragment shader based on the given shader data.
	 *
	 * @private
	 * @param {Object} shaderData - The shader data.
	 * @return {string} The vertex shader.
	 */
	_getGLSLFragmentCode( shaderData ) {

		return `#version 300 es

${ this.getSignature() }

// extensions
${shaderData.extensions}

// precision
${ defaultPrecisions }

// uniforms
${shaderData.uniforms}

// varyings
${shaderData.varyings}

// codes
${shaderData.codes}

// structs
${shaderData.structs}

void main() {

	// vars
	${shaderData.vars}

	// flow
	${shaderData.flow}

}
`;

	}

	/**
	 * Controls the code build of the shader stages.
	 */
	buildCode() {

		const shadersData = this.material !== null ? { fragment: {}, vertex: {} } : { compute: {} };

		this.sortBindingGroups();

		for ( const shaderStage in shadersData ) {

			let flow = '// code\n\n';
			flow += this.flowCode[ shaderStage ];

			const flowNodes = this.flowNodes[ shaderStage ];
			const mainNode = flowNodes[ flowNodes.length - 1 ];

			for ( const node of flowNodes ) {

				const flowSlotData = this.getFlowData( node/*, shaderStage*/ );
				const slotName = node.name;

				if ( slotName ) {

					if ( flow.length > 0 ) flow += '\n';

					flow += `\t// flow -> ${ slotName }\n\t`;

				}

				flow += `${ flowSlotData.code }\n\t`;

				if ( node === mainNode && shaderStage !== 'compute' ) {

					flow += '// result\n\t';

					if ( shaderStage === 'vertex' ) {

						flow += 'gl_Position = ';
						flow += `${ flowSlotData.result };`;

					} else if ( shaderStage === 'fragment' ) {

						if ( ! node.outputNode.isOutputStructNode ) {

							flow += 'fragColor = ';
							flow += `${ flowSlotData.result };`;

						}

					}

				}

			}

			const stageData = shadersData[ shaderStage ];

			stageData.extensions = this.getExtensions( shaderStage );
			stageData.uniforms = this.getUniforms( shaderStage );
			stageData.attributes = this.getAttributes( shaderStage );
			stageData.varyings = this.getVaryings( shaderStage );
			stageData.vars = this.getVars( shaderStage );
			stageData.structs = this.getStructs( shaderStage );
			stageData.codes = this.getCodes( shaderStage );
			stageData.transforms = this.getTransforms( shaderStage );
			stageData.flow = flow;

		}

		if ( this.material !== null ) {

			this.vertexShader = this._getGLSLVertexCode( shadersData.vertex );
			this.fragmentShader = this._getGLSLFragmentCode( shadersData.fragment );

		} else {

			this.computeShader = this._getGLSLVertexCode( shadersData.compute );

		}

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

		let uniformGPU = nodeData.uniformGPU;

		if ( uniformGPU === undefined ) {

			const group = node.groupNode;
			const groupName = group.name;

			const bindings = this.getBindGroupArray( groupName, shaderStage );

			if ( type === 'texture' ) {

				uniformGPU = new NodeSampledTexture( uniformNode.name, uniformNode.node, group );
				bindings.push( uniformGPU );

			} else if ( type === 'cubeTexture' ) {

				uniformGPU = new NodeSampledCubeTexture( uniformNode.name, uniformNode.node, group );
				bindings.push( uniformGPU );

			} else if ( type === 'texture3D' ) {

				uniformGPU = new NodeSampledTexture3D( uniformNode.name, uniformNode.node, group );
				bindings.push( uniformGPU );

			} else if ( type === 'buffer' ) {

				node.name = `NodeBuffer_${ node.id }`;
				uniformNode.name = `buffer${ node.id }`;

				const buffer = new NodeUniformBuffer( node, group );
				buffer.name = node.name;

				bindings.push( buffer );

				uniformGPU = buffer;

			} else {

				const uniformsStage = this.uniformGroups[ shaderStage ] || ( this.uniformGroups[ shaderStage ] = {} );

				let uniformsGroup = uniformsStage[ groupName ];

				if ( uniformsGroup === undefined ) {

					uniformsGroup = new NodeUniformsGroup( shaderStage + '_' + groupName, group );
					//uniformsGroup.setVisibility( gpuShaderStageLib[ shaderStage ] );

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

}
```
</details>

#### Methods

##### `needsToWorkingColorSpace(texture: Texture): boolean`

<details><summary>Code</summary>

```ts
needsToWorkingColorSpace( texture ) {

		return texture.isVideoTexture === true && texture.colorSpace !== NoColorSpace;

	}
```
</details>

##### `getMethod(method: string): string`

<details><summary>Code</summary>

```ts
getMethod( method ) {

		return glslMethods[ method ] || method;

	}
```
</details>

##### `getTernary(condSnippet: string, ifSnippet: string, elseSnippet: string): string`

<details><summary>Code</summary>

```ts
getTernary( condSnippet, ifSnippet, elseSnippet ) {

		return `${condSnippet} ? ${ifSnippet} : ${elseSnippet}`;

	}
```
</details>

##### `getOutputStructName(): string`

<details><summary>Code</summary>

```ts
getOutputStructName() {

		return '';

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

			parameters.push( this.getType( input.type ) + ' ' + input.name );

		}

		//

		const code = `${ this.getType( layout.type ) } ${ layout.name }( ${ parameters.join( ', ' ) } ) {

	${ flowData.vars }

${ flowData.code }
	return ${ flowData.result };

}`;

		//

		return code;

	}
```
</details>

##### `setupPBO(storageBufferNode: StorageBufferNode): void`

<details><summary>Code</summary>

```ts
setupPBO( storageBufferNode ) {

		const attribute = storageBufferNode.value;

		if ( attribute.pbo === undefined ) {

			const originalArray = attribute.array;
			const numElements = attribute.count * attribute.itemSize;

			const { itemSize } = attribute;

			const isInteger = attribute.array.constructor.name.toLowerCase().includes( 'int' );

			let format = isInteger ? RedIntegerFormat : RedFormat;

			if ( itemSize === 2 ) {

				format = isInteger ? RGIntegerFormat : RGFormat;

			} else if ( itemSize === 3 ) {

				format = isInteger ? RGBIntegerFormat : RGBFormat;

			} else if ( itemSize === 4 ) {

				format = isInteger ? RGBAIntegerFormat : RGBAFormat;

			}

			const typeMap = {
				Float32Array: FloatType,
				Uint8Array: UnsignedByteType,
				Uint16Array: UnsignedShortType,
				Uint32Array: UnsignedIntType,
				Int8Array: ByteType,
				Int16Array: ShortType,
				Int32Array: IntType,
				Uint8ClampedArray: UnsignedByteType,
			};

			const width = Math.pow( 2, Math.ceil( Math.log2( Math.sqrt( numElements / itemSize ) ) ) );
			let height = Math.ceil( ( numElements / itemSize ) / width );
			if ( width * height * itemSize < numElements ) height ++; // Ensure enough space

			const newSize = width * height * itemSize;

			const newArray = new originalArray.constructor( newSize );

			newArray.set( originalArray, 0 );

			attribute.array = newArray;

			const pboTexture = new DataTexture( attribute.array, width, height, format, typeMap[ attribute.array.constructor.name ] || FloatType );
			pboTexture.needsUpdate = true;
			pboTexture.isPBOTexture = true;

			const pbo = new TextureNode( pboTexture, null, null );
			pbo.setPrecision( 'high' );

			attribute.pboNode = pbo;
			attribute.pbo = pbo.value;

			this.getUniformFromNode( attribute.pboNode, 'texture', this.shaderStage, this.context.nodeName );

		}

	}
```
</details>

##### `getPropertyName(node: Node, shaderStage: string): string`

<details><summary>Code</summary>

```ts
getPropertyName( node, shaderStage = this.shaderStage ) {

		if ( node.isNodeUniform && node.node.isTextureNode !== true && node.node.isBufferNode !== true ) {

			return shaderStage.charAt( 0 ) + '_' + node.name;

		}

		return super.getPropertyName( node, shaderStage );

	}
```
</details>

##### `generatePBO(storageArrayElementNode: StorageArrayElementNode): string`

<details><summary>Code</summary>

```ts
generatePBO( storageArrayElementNode ) {

		const { node, indexNode } = storageArrayElementNode;
		const attribute = node.value;

		if ( this.renderer.backend.has( attribute ) ) {

			const attributeData = this.renderer.backend.get( attribute );
			attributeData.pbo = attribute.pbo;

		}

		const nodeUniform = this.getUniformFromNode( attribute.pboNode, 'texture', this.shaderStage, this.context.nodeName );
		const textureName = this.getPropertyName( nodeUniform );

		this.increaseUsage( indexNode ); // force cache generate to be used as index in x,y
		const indexSnippet = indexNode.build( this, 'uint' );

		const elementNodeData = this.getDataFromNode( storageArrayElementNode );

		let propertyName = elementNodeData.propertyName;

		if ( propertyName === undefined ) {

			// property element

			const nodeVar = this.getVarFromNode( storageArrayElementNode );

			propertyName = this.getPropertyName( nodeVar );

			// property size

			const bufferNodeData = this.getDataFromNode( node );

			let propertySizeName = bufferNodeData.propertySizeName;

			if ( propertySizeName === undefined ) {

				propertySizeName = propertyName + 'Size';

				this.getVarFromNode( node, propertySizeName, 'uint' );

				this.addLineFlowCode( `${ propertySizeName } = uint( textureSize( ${ textureName }, 0 ).x )`, storageArrayElementNode );

				bufferNodeData.propertySizeName = propertySizeName;

			}

			//

			const { itemSize } = attribute;

			const channel = '.' + vectorComponents.join( '' ).slice( 0, itemSize );
			const uvSnippet = `ivec2(${indexSnippet} % ${ propertySizeName }, ${indexSnippet} / ${ propertySizeName })`;

			const snippet = this.generateTextureLoad( null, textureName, uvSnippet, null, '0' );

			//


			let prefix = 'vec4';

			if ( attribute.pbo.type === UnsignedIntType ) {

				prefix = 'uvec4';

			} else if ( attribute.pbo.type === IntType ) {

				prefix = 'ivec4';

			}

			this.addLineFlowCode( `${ propertyName } = ${prefix}(${ snippet })${channel}`, storageArrayElementNode );

			elementNodeData.propertyName = propertyName;

		}

		return propertyName;

	}
```
</details>

##### `generateTextureLoad(texture: Texture, textureProperty: string, uvIndexSnippet: string, depthSnippet: string, levelSnippet: string): string`

<details><summary>Code</summary>

```ts
generateTextureLoad( texture, textureProperty, uvIndexSnippet, depthSnippet, levelSnippet = '0' ) {

		if ( depthSnippet ) {

			return `texelFetch( ${ textureProperty }, ivec3( ${ uvIndexSnippet }, ${ depthSnippet } ), ${ levelSnippet } )`;

		} else {

			return `texelFetch( ${ textureProperty }, ${ uvIndexSnippet }, ${ levelSnippet } )`;

		}

	}
```
</details>

##### `generateTexture(texture: Texture, textureProperty: string, uvSnippet: string, depthSnippet: string): string`

<details><summary>Code</summary>

```ts
generateTexture( texture, textureProperty, uvSnippet, depthSnippet ) {

		if ( texture.isDepthTexture ) {

			if ( depthSnippet ) uvSnippet = `vec4( ${ uvSnippet }, ${ depthSnippet } )`;

			return `texture( ${ textureProperty }, ${ uvSnippet } ).x`;

		} else {

			if ( depthSnippet ) uvSnippet = `vec3( ${ uvSnippet }, ${ depthSnippet } )`;

			return `texture( ${ textureProperty }, ${ uvSnippet } )`;

		}

	}
```
</details>

##### `generateTextureLevel(texture: Texture, textureProperty: string, uvSnippet: string, levelSnippet: string): string`

<details><summary>Code</summary>

```ts
generateTextureLevel( texture, textureProperty, uvSnippet, levelSnippet ) {

		return `textureLod( ${ textureProperty }, ${ uvSnippet }, ${ levelSnippet } )`;

	}
```
</details>

##### `generateTextureBias(texture: Texture, textureProperty: string, uvSnippet: string, biasSnippet: string): string`

<details><summary>Code</summary>

```ts
generateTextureBias( texture, textureProperty, uvSnippet, biasSnippet ) {

		return `texture( ${ textureProperty }, ${ uvSnippet }, ${ biasSnippet } )`;

	}
```
</details>

##### `generateTextureGrad(texture: Texture, textureProperty: string, uvSnippet: string, gradSnippet: string[]): string`

<details><summary>Code</summary>

```ts
generateTextureGrad( texture, textureProperty, uvSnippet, gradSnippet ) {

		return `textureGrad( ${ textureProperty }, ${ uvSnippet }, ${ gradSnippet[ 0 ] }, ${ gradSnippet[ 1 ] } )`;

	}
```
</details>

##### `generateTextureCompare(texture: Texture, textureProperty: string, uvSnippet: string, compareSnippet: string, depthSnippet: string, shaderStage: string): string`

<details><summary>Code</summary>

```ts
generateTextureCompare( texture, textureProperty, uvSnippet, compareSnippet, depthSnippet, shaderStage = this.shaderStage ) {

		if ( shaderStage === 'fragment' ) {

			if ( depthSnippet ) {

				return `texture( ${ textureProperty }, vec4( ${ uvSnippet }, ${ depthSnippet }, ${ compareSnippet } ) )`;

			}

			return `texture( ${ textureProperty }, vec3( ${ uvSnippet }, ${ compareSnippet } ) )`;

		} else {

			console.error( `WebGPURenderer: THREE.DepthTexture.compareFunction() does not support ${ shaderStage } shader.` );

		}

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

				snippets.push( `${ this.getVar( variable.type, variable.name, variable.count ) };` );

			}

		}

		return snippets.join( '\n\t' );

	}
```
</details>

##### `getUniforms(shaderStage: string): string`

<details><summary>Code</summary>

```ts
getUniforms( shaderStage ) {

		const uniforms = this.uniforms[ shaderStage ];

		const bindingSnippets = [];
		const uniformGroups = {};

		for ( const uniform of uniforms ) {

			let snippet = null;
			let group = false;

			if ( uniform.type === 'texture' || uniform.type === 'texture3D' ) {

				const texture = uniform.node.value;

				let typePrefix = '';

				if ( texture.isDataTexture === true || texture.isData3DTexture === true ) {

					if ( texture.type === UnsignedIntType ) {

						typePrefix = 'u';

					} else if ( texture.type === IntType ) {

						typePrefix = 'i';

					}

				}

				if ( uniform.type === 'texture3D' && texture.isArrayTexture === false ) {

					snippet = `${typePrefix}sampler3D ${ uniform.name };`;

				} else if ( texture.compareFunction ) {

					if ( texture.isArrayTexture === true ) {

						snippet = `sampler2DArrayShadow ${ uniform.name };`;

					} else {

						snippet = `sampler2DShadow ${ uniform.name };`;

					}

				} else if ( texture.isArrayTexture === true || texture.isDataArrayTexture === true || texture.isCompressedArrayTexture === true ) {

					snippet = `${typePrefix}sampler2DArray ${ uniform.name };`;

				} else {

					snippet = `${typePrefix}sampler2D ${ uniform.name };`;

				}

			} else if ( uniform.type === 'cubeTexture' ) {

				snippet = `samplerCube ${ uniform.name };`;

			} else if ( uniform.type === 'buffer' ) {

				const bufferNode = uniform.node;
				const bufferType = this.getType( bufferNode.bufferType );
				const bufferCount = bufferNode.bufferCount;

				const bufferCountSnippet = bufferCount > 0 ? bufferCount : '';
				snippet = `${bufferNode.name} {\n\t${ bufferType } ${ uniform.name }[${ bufferCountSnippet }];\n};\n`;

			} else {

				const vectorType = this.getVectorType( uniform.type );

				snippet = `${ vectorType } ${ this.getPropertyName( uniform, shaderStage ) };`;

				group = true;

			}

			const precision = uniform.node.precision;

			if ( precision !== null ) {

				snippet = precisionLib[ precision ] + ' ' + snippet;

			}

			if ( group ) {

				snippet = '\t' + snippet;

				const groupName = uniform.groupNode.name;
				const groupSnippets = uniformGroups[ groupName ] || ( uniformGroups[ groupName ] = [] );

				groupSnippets.push( snippet );

			} else {

				snippet = 'uniform ' + snippet;

				bindingSnippets.push( snippet );

			}

		}

		let output = '';

		for ( const name in uniformGroups ) {

			const groupSnippets = uniformGroups[ name ];

			output += this._getGLSLUniformStruct( shaderStage + '_' + name, groupSnippets.join( '\n' ) ) + '\n';

		}

		output += bindingSnippets.join( '\n' );

		return output;

	}
```
</details>

##### `getTypeFromAttribute(attribute: BufferAttribute): string`

<details><summary>Code</summary>

```ts
getTypeFromAttribute( attribute ) {

		let nodeType = super.getTypeFromAttribute( attribute );

		if ( /^[iu]/.test( nodeType ) && attribute.gpuType !== IntType ) {

			let dataAttribute = attribute;

			if ( attribute.isInterleavedBufferAttribute ) dataAttribute = attribute.data;

			const array = dataAttribute.array;

			if ( ( array instanceof Uint32Array || array instanceof Int32Array ) === false ) {

				nodeType = nodeType.slice( 1 );

			}

		}

		return nodeType;

	}
```
</details>

##### `getAttributes(shaderStage: string): string`

<details><summary>Code</summary>

```ts
getAttributes( shaderStage ) {

		let snippet = '';

		if ( shaderStage === 'vertex' || shaderStage === 'compute' ) {

			const attributes = this.getAttributesArray();

			let location = 0;

			for ( const attribute of attributes ) {

				snippet += `layout( location = ${ location ++ } ) in ${ attribute.type } ${ attribute.name };\n`;

			}

		}

		return snippet;

	}
```
</details>

##### `getStructMembers(struct: StructTypeNode): string`

<details><summary>Code</summary>

```ts
getStructMembers( struct ) {

		const snippets = [];

		for ( const member of struct.members ) {

			snippets.push( `\t${ member.type } ${ member.name };` );

		}

		return snippets.join( '\n' );

	}
```
</details>

##### `getStructs(shaderStage: string): string`

<details><summary>Code</summary>

```ts
getStructs( shaderStage ) {

		const snippets = [];
		const structs = this.structs[ shaderStage ];

		const outputSnippet = [];

		for ( const struct of structs ) {

			if ( struct.output ) {

				for ( const member of struct.members ) {

					outputSnippet.push( `layout( location = ${ member.index } ) out ${ member.type } ${ member.name };` );

				}

			} else {

				let snippet = 'struct ' + struct.name + ' {\n';
				snippet += this.getStructMembers( struct );
				snippet += '\n};\n';

				snippets.push( snippet );

			}

		}

		if ( outputSnippet.length === 0 ) {

			outputSnippet.push( 'layout( location = 0 ) out vec4 fragColor;' );

		}

		return '\n' + outputSnippet.join( '\n' ) + '\n\n' + snippets.join( '\n' );

	}
```
</details>

##### `getVaryings(shaderStage: string): string`

<details><summary>Code</summary>

```ts
getVaryings( shaderStage ) {

		let snippet = '';

		const varyings = this.varyings;

		if ( shaderStage === 'vertex' || shaderStage === 'compute' ) {

			for ( const varying of varyings ) {

				if ( shaderStage === 'compute' ) varying.needsInterpolation = true;

				const type = this.getType( varying.type );

				if ( varying.needsInterpolation ) {

					if ( varying.interpolationType ) {

						const interpolationType = interpolationTypeMap[ varying.interpolationType ] || varying.interpolationType;
						const sampling = interpolationModeMap[ varying.interpolationSampling ] || '';

						snippet += `${ interpolationType } ${ sampling } out ${ type } ${ varying.name };\n`;

					} else {

						const flat = type.includes( 'int' ) || type.includes( 'uv' ) || type.includes( 'iv' ) ? 'flat ' : '';

						snippet += `${ flat }out ${ type } ${ varying.name };\n`;

					}

				} else {

					snippet += `${type} ${varying.name};\n`; // generate variable (no varying required)

				}

			}

		} else if ( shaderStage === 'fragment' ) {

			for ( const varying of varyings ) {

				if ( varying.needsInterpolation ) {

					const type = this.getType( varying.type );

					if ( varying.interpolationType ) {

						const interpolationType = interpolationTypeMap[ varying.interpolationType ] || varying.interpolationType;
						const sampling = interpolationModeMap[ varying.interpolationSampling ] || '';

						snippet += `${ interpolationType } ${ sampling } in ${ type } ${ varying.name };\n`;


					} else {

						const flat = type.includes( 'int' ) || type.includes( 'uv' ) || type.includes( 'iv' ) ? 'flat ' : '';

						snippet += `${ flat }in ${ type } ${ varying.name };\n`;

					}

				}

			}

		}

		for ( const builtin of this.builtins[ shaderStage ] ) {

			snippet += `${builtin};\n`;

		}

		return snippet;

	}
```
</details>

##### `getVertexIndex(): string`

<details><summary>Code</summary>

```ts
getVertexIndex() {

		return 'uint( gl_VertexID )';

	}
```
</details>

##### `getInstanceIndex(): string`

<details><summary>Code</summary>

```ts
getInstanceIndex() {

		return 'uint( gl_InstanceID )';

	}
```
</details>

##### `getInvocationLocalIndex(): string`

<details><summary>Code</summary>

```ts
getInvocationLocalIndex() {

		const workgroupSize = this.object.workgroupSize;

		const size = workgroupSize.reduce( ( acc, curr ) => acc * curr, 1 );

		return `uint( gl_InstanceID ) % ${size}u`;

	}
```
</details>

##### `getDrawIndex(): string`

<details><summary>Code</summary>

```ts
getDrawIndex() {

		const extensions = this.renderer.backend.extensions;

		if ( extensions.has( 'WEBGL_multi_draw' ) ) {

			return 'uint( gl_DrawID )';

		}

		return null;

	}
```
</details>

##### `getFrontFacing(): string`

<details><summary>Code</summary>

```ts
getFrontFacing() {

		return 'gl_FrontFacing';

	}
```
</details>

##### `getFragCoord(): string`

<details><summary>Code</summary>

```ts
getFragCoord() {

		return 'gl_FragCoord.xy';

	}
```
</details>

##### `getFragDepth(): string`

<details><summary>Code</summary>

```ts
getFragDepth() {

		return 'gl_FragDepth';

	}
```
</details>

##### `enableExtension(name: string, behavior: string, shaderStage: string): void`

<details><summary>Code</summary>

```ts
enableExtension( name, behavior, shaderStage = this.shaderStage ) {

		const map = this.extensions[ shaderStage ] || ( this.extensions[ shaderStage ] = new Map() );

		if ( map.has( name ) === false ) {

			map.set( name, {
				name,
				behavior
			} );

		}

	}
```
</details>

##### `getExtensions(shaderStage: string): string`

<details><summary>Code</summary>

```ts
getExtensions( shaderStage ) {

		const snippets = [];

		if ( shaderStage === 'vertex' ) {

			const ext = this.renderer.backend.extensions;
			const isBatchedMesh = this.object.isBatchedMesh;

			if ( isBatchedMesh && ext.has( 'WEBGL_multi_draw' ) ) {

				this.enableExtension( 'GL_ANGLE_multi_draw', 'require', shaderStage );

			}

		}

		const extensions = this.extensions[ shaderStage ];

		if ( extensions !== undefined ) {

			for ( const { name, behavior } of extensions.values() ) {

				snippets.push( `#extension ${name} : ${behavior}` );

			}

		}

		return snippets.join( '\n' );

	}
```
</details>

##### `getClipDistance(): string`

<details><summary>Code</summary>

```ts
getClipDistance() {

		return 'gl_ClipDistance';

	}
```
</details>

##### `isAvailable(name: string): boolean`

<details><summary>Code</summary>

```ts
isAvailable( name ) {

		let result = supports[ name ];

		if ( result === undefined ) {

			let extensionName;

			result = false;

			switch ( name ) {

				case 'float32Filterable':
					extensionName = 'OES_texture_float_linear';
					break;

				case 'clipDistance':
					extensionName = 'WEBGL_clip_cull_distance';
					break;

			}

			if ( extensionName !== undefined ) {

				const extensions = this.renderer.backend.extensions;

				if ( extensions.has( extensionName ) ) {

					extensions.get( extensionName );
					result = true;

				}

			}

			supports[ name ] = result;

		}

		return result;

	}
```
</details>

##### `isFlipY(): boolean`

<details><summary>Code</summary>

```ts
isFlipY() {

		return true;

	}
```
</details>

##### `enableHardwareClipping(planeCount: string): void`

<details><summary>Code</summary>

```ts
enableHardwareClipping( planeCount ) {

		this.enableExtension( 'GL_ANGLE_clip_cull_distance', 'require' );

		this.builtins[ 'vertex' ].push( `out float gl_ClipDistance[ ${ planeCount } ]` );

	}
```
</details>

##### `enableMultiview(): void`

<details><summary>Code</summary>

```ts
enableMultiview() {

		this.enableExtension( 'GL_OVR_multiview2', 'require', 'fragment' );
		this.enableExtension( 'GL_OVR_multiview2', 'require', 'vertex' );

		this.builtins[ 'vertex' ].push( 'layout(num_views = 2) in' );

	}
```
</details>

##### `registerTransform(varyingName: string, attributeNode: AttributeNode): void`

<details><summary>Code</summary>

```ts
registerTransform( varyingName, attributeNode ) {

		this.transforms.push( { varyingName, attributeNode } );

	}
```
</details>

##### `getTransforms(): string`

<details><summary>Code</summary>

```ts
getTransforms( /* shaderStage  */ ) {

		const transforms = this.transforms;

		let snippet = '';

		for ( let i = 0; i < transforms.length; i ++ ) {

			const transform = transforms[ i ];
			const attributeName = this.getPropertyName( transform.attributeNode );

			if ( attributeName ) snippet += `${ transform.varyingName } = ${ attributeName };\n\t`;

		}

		return snippet;

	}
```
</details>

##### `_getGLSLUniformStruct(name: string, vars: string): string`

<details><summary>Code</summary>

```ts
_getGLSLUniformStruct( name, vars ) {

		return `
layout( std140 ) uniform ${name} {
${vars}
};`;

	}
```
</details>

##### `_getGLSLVertexCode(shaderData: any): string`

<details><summary>Code</summary>

```ts
_getGLSLVertexCode( shaderData ) {

		return `#version 300 es

${ this.getSignature() }

// extensions
${shaderData.extensions}

// precision
${ defaultPrecisions }

// uniforms
${shaderData.uniforms}

// varyings
${shaderData.varyings}

// attributes
${shaderData.attributes}

// codes
${shaderData.codes}

void main() {

	// vars
	${shaderData.vars}

	// transforms
	${shaderData.transforms}

	// flow
	${shaderData.flow}

	gl_PointSize = 1.0;

}
`;

	}
```
</details>

##### `_getGLSLFragmentCode(shaderData: any): string`

<details><summary>Code</summary>

```ts
_getGLSLFragmentCode( shaderData ) {

		return `#version 300 es

${ this.getSignature() }

// extensions
${shaderData.extensions}

// precision
${ defaultPrecisions }

// uniforms
${shaderData.uniforms}

// varyings
${shaderData.varyings}

// codes
${shaderData.codes}

// structs
${shaderData.structs}

void main() {

	// vars
	${shaderData.vars}

	// flow
	${shaderData.flow}

}
`;

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

			let flow = '// code\n\n';
			flow += this.flowCode[ shaderStage ];

			const flowNodes = this.flowNodes[ shaderStage ];
			const mainNode = flowNodes[ flowNodes.length - 1 ];

			for ( const node of flowNodes ) {

				const flowSlotData = this.getFlowData( node/*, shaderStage*/ );
				const slotName = node.name;

				if ( slotName ) {

					if ( flow.length > 0 ) flow += '\n';

					flow += `\t// flow -> ${ slotName }\n\t`;

				}

				flow += `${ flowSlotData.code }\n\t`;

				if ( node === mainNode && shaderStage !== 'compute' ) {

					flow += '// result\n\t';

					if ( shaderStage === 'vertex' ) {

						flow += 'gl_Position = ';
						flow += `${ flowSlotData.result };`;

					} else if ( shaderStage === 'fragment' ) {

						if ( ! node.outputNode.isOutputStructNode ) {

							flow += 'fragColor = ';
							flow += `${ flowSlotData.result };`;

						}

					}

				}

			}

			const stageData = shadersData[ shaderStage ];

			stageData.extensions = this.getExtensions( shaderStage );
			stageData.uniforms = this.getUniforms( shaderStage );
			stageData.attributes = this.getAttributes( shaderStage );
			stageData.varyings = this.getVaryings( shaderStage );
			stageData.vars = this.getVars( shaderStage );
			stageData.structs = this.getStructs( shaderStage );
			stageData.codes = this.getCodes( shaderStage );
			stageData.transforms = this.getTransforms( shaderStage );
			stageData.flow = flow;

		}

		if ( this.material !== null ) {

			this.vertexShader = this._getGLSLVertexCode( shadersData.vertex );
			this.fragmentShader = this._getGLSLFragmentCode( shadersData.fragment );

		} else {

			this.computeShader = this._getGLSLVertexCode( shadersData.compute );

		}

	}
```
</details>

##### `getUniformFromNode(node: UniformNode, type: string, shaderStage: string, name: string): NodeUniform`

<details><summary>Code</summary>

```ts
getUniformFromNode( node, type, shaderStage, name = null ) {

		const uniformNode = super.getUniformFromNode( node, type, shaderStage, name );
		const nodeData = this.getDataFromNode( node, shaderStage, this.globalCache );

		let uniformGPU = nodeData.uniformGPU;

		if ( uniformGPU === undefined ) {

			const group = node.groupNode;
			const groupName = group.name;

			const bindings = this.getBindGroupArray( groupName, shaderStage );

			if ( type === 'texture' ) {

				uniformGPU = new NodeSampledTexture( uniformNode.name, uniformNode.node, group );
				bindings.push( uniformGPU );

			} else if ( type === 'cubeTexture' ) {

				uniformGPU = new NodeSampledCubeTexture( uniformNode.name, uniformNode.node, group );
				bindings.push( uniformGPU );

			} else if ( type === 'texture3D' ) {

				uniformGPU = new NodeSampledTexture3D( uniformNode.name, uniformNode.node, group );
				bindings.push( uniformGPU );

			} else if ( type === 'buffer' ) {

				node.name = `NodeBuffer_${ node.id }`;
				uniformNode.name = `buffer${ node.id }`;

				const buffer = new NodeUniformBuffer( node, group );
				buffer.name = node.name;

				bindings.push( buffer );

				uniformGPU = buffer;

			} else {

				const uniformsStage = this.uniformGroups[ shaderStage ] || ( this.uniformGroups[ shaderStage ] = {} );

				let uniformsGroup = uniformsStage[ groupName ];

				if ( uniformsGroup === undefined ) {

					uniformsGroup = new NodeUniformsGroup( shaderStage + '_' + groupName, group );
					//uniformsGroup.setVisibility( gpuShaderStageLib[ shaderStage ] );

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


---