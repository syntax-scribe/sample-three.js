[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLProgram.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 24 |
| 📦 Imports | 26 |
| 📊 Variables & Constants | 46 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLProgram.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `WebGLUniforms` | `./WebGLUniforms.js` |
| `WebGLShader` | `./WebGLShader.js` |
| `ShaderChunk` | `../shaders/ShaderChunk.js` |
| `NoToneMapping` | `../../constants.js` |
| `AddOperation` | `../../constants.js` |
| `MixOperation` | `../../constants.js` |
| `MultiplyOperation` | `../../constants.js` |
| `CubeRefractionMapping` | `../../constants.js` |
| `CubeUVReflectionMapping` | `../../constants.js` |
| `CubeReflectionMapping` | `../../constants.js` |
| `PCFSoftShadowMap` | `../../constants.js` |
| `PCFShadowMap` | `../../constants.js` |
| `VSMShadowMap` | `../../constants.js` |
| `AgXToneMapping` | `../../constants.js` |
| `ACESFilmicToneMapping` | `../../constants.js` |
| `NeutralToneMapping` | `../../constants.js` |
| `CineonToneMapping` | `../../constants.js` |
| `CustomToneMapping` | `../../constants.js` |
| `ReinhardToneMapping` | `../../constants.js` |
| `LinearToneMapping` | `../../constants.js` |
| `GLSL3` | `../../constants.js` |
| `LinearTransfer` | `../../constants.js` |
| `SRGBTransfer` | `../../constants.js` |
| `ColorManagement` | `../../math/ColorManagement.js` |
| `Vector3` | `../../math/Vector3.js` |
| `Matrix3` | `../../math/Matrix3.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `COMPLETION_STATUS_KHR` | `37297` | let/var | `0x91B1` | ✗ |
| `programIdCount` | `number` | let/var | `0` | ✗ |
| `lines2` | `any[]` | let/var | `[]` | ✗ |
| `line` | `number` | let/var | `i + 1` | ✗ |
| `_m0` | `Matrix3` | let/var | `new Matrix3()` | ✗ |
| `encodingMatrix` | `string` | let/var | ``mat3( ${ _m0.elements.map( ( v ) => v.toFixed( 4 ) ) } )`` | ✗ |
| `shaderInfoLog` | `any` | let/var | `gl.getShaderInfoLog( shader ) \|\| ''` | ✗ |
| `toneMappingName` | `any` | let/var | `*not shown*` | ✗ |
| `_v0` | `Vector3` | let/var | `new Vector3()` | ✗ |
| `chunks` | `string[]` | let/var | `[ parameters.extensionClipCullDistance ? '#extension GL_ANGLE_clip_cull_dista...` | ✗ |
| `chunks` | `any[]` | let/var | `[]` | ✗ |
| `value` | `any` | let/var | `defines[ name ]` | ✗ |
| `attributes` | `{}` | let/var | `{}` | ✗ |
| `name` | `any` | let/var | `info.name` | ✗ |
| `locationSize` | `number` | let/var | `1` | ✗ |
| `numSpotLightCoords` | `number` | let/var | `parameters.numSpotLightShadows + parameters.numSpotLightMaps - parameters.num...` | ✗ |
| `includePattern` | `RegExp` | let/var | `/^[ \t]*#include +<([\w\d./]+)>/gm` | ✗ |
| `shaderChunkMap` | `Map<any, any>` | let/var | `new Map()` | ✗ |
| `string` | `any` | let/var | `ShaderChunk[ include ]` | ✗ |
| `unrollLoopPattern` | `RegExp` | let/var | `/#pragma unroll_loop_start\s+for\s*\(\s*int\s+i\s*=\s*(\d+)\s*;\s*i\s*<\s*(\d...` | ✗ |
| `string` | `string` | let/var | `''` | ✗ |
| `precisionstring` | `string` | let/var | ``precision ${parameters.precision} float; precision ${parameters.precision} i...` | ✗ |
| `shadowMapTypeDefine` | `string` | let/var | `'SHADOWMAP_TYPE_BASIC'` | ✗ |
| `envMapTypeDefine` | `string` | let/var | `'ENVMAP_TYPE_CUBE'` | ✗ |
| `envMapModeDefine` | `string` | let/var | `'ENVMAP_MODE_REFLECTION'` | ✗ |
| `envMapBlendingDefine` | `string` | let/var | `'ENVMAP_BLENDING_NONE'` | ✗ |
| `imageHeight` | `any` | let/var | `parameters.envMapCubeUVHeight` | ✗ |
| `maxMip` | `number` | let/var | `Math.log2( imageHeight ) - 2` | ✗ |
| `texelHeight` | `number` | let/var | `1.0 / imageHeight` | ✗ |
| `texelWidth` | `number` | let/var | `1.0 / ( 3 * Math.max( Math.pow( 2, maxMip ), 7 * 16 ) )` | ✗ |
| `defines` | `any` | let/var | `parameters.defines` | ✗ |
| `vertexShader` | `any` | let/var | `parameters.vertexShader` | ✗ |
| `fragmentShader` | `any` | let/var | `parameters.fragmentShader` | ✗ |
| `prefixVertex` | `any` | let/var | `*not shown*` | ✗ |
| `prefixFragment` | `any` | let/var | `*not shown*` | ✗ |
| `versionString` | `string` | let/var | `parameters.glslVersion ? '#version ' + parameters.glslVersion + '\n' : ''` | ✗ |
| `vertexGlsl` | `string` | let/var | `versionString + prefixVertex + vertexShader` | ✗ |
| `fragmentGlsl` | `string` | let/var | `versionString + prefixFragment + fragmentShader` | ✗ |
| `programInfoLog` | `any` | let/var | `gl.getProgramInfoLog( program ) \|\| ''` | ✗ |
| `vertexShaderInfoLog` | `any` | let/var | `gl.getShaderInfoLog( glVertexShader ) \|\| ''` | ✗ |
| `fragmentShaderInfoLog` | `any` | let/var | `gl.getShaderInfoLog( glFragmentShader ) \|\| ''` | ✗ |
| `runnable` | `boolean` | let/var | `true` | ✗ |
| `haveDiagnostics` | `boolean` | let/var | `true` | ✗ |
| `cachedUniforms` | `any` | let/var | `*not shown*` | ✗ |
| `cachedAttributes` | `any` | let/var | `*not shown*` | ✗ |
| `programReady` | `boolean` | let/var | `( parameters.rendererExtensionParallelShaderCompile === false )` | ✗ |


---

## Functions

### `handleSource(string: any, errorLine: any): string`

**Parameters:**

- **`string`** `any`
- **`errorLine`** `any`

**Returns:** `string`

**Calls:**

- `string.split`
- `Math.max`
- `Math.min`
- `lines2.push`
- `lines2.join`

<details><summary>Code</summary>

```typescript
function handleSource( string, errorLine ) {

	const lines = string.split( '\n' );
	const lines2 = [];

	const from = Math.max( errorLine - 6, 0 );
	const to = Math.min( errorLine + 6, lines.length );

	for ( let i = from; i < to; i ++ ) {

		const line = i + 1;
		lines2.push( `${line === errorLine ? '>' : ' '} ${line}: ${lines[ i ]}` );

	}

	return lines2.join( '\n' );

}
```
</details>

### `getEncodingComponents(colorSpace: any): string[]`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `string[]`

**Calls:**

- `ColorManagement._getMatrix`
- `_m0.elements.map`
- `v.toFixed`
- `ColorManagement.getTransfer`
- `console.warn`

<details><summary>Code</summary>

```typescript
function getEncodingComponents( colorSpace ) {

	ColorManagement._getMatrix( _m0, ColorManagement.workingColorSpace, colorSpace );

	const encodingMatrix = `mat3( ${ _m0.elements.map( ( v ) => v.toFixed( 4 ) ) } )`;

	switch ( ColorManagement.getTransfer( colorSpace ) ) {

		case LinearTransfer:
			return [ encodingMatrix, 'LinearTransferOETF' ];

		case SRGBTransfer:
			return [ encodingMatrix, 'sRGBTransferOETF' ];

		default:
			console.warn( 'THREE.WebGLProgram: Unsupported color space: ', colorSpace );
			return [ encodingMatrix, 'LinearTransferOETF' ];

	}

}
```
</details>

### `getShaderErrors(gl: any, shader: any, type: any): any`

**Parameters:**

- **`gl`** `any`
- **`shader`** `any`
- **`type`** `any`

**Returns:** `any`

**Calls:**

- `gl.getShaderParameter`
- `gl.getShaderInfoLog`
- `shaderInfoLog.trim`
- `/ERROR: 0:(\d+)/.exec`
- `parseInt`
- `type.toUpperCase`
- `handleSource`
- `gl.getShaderSource`

**Internal Comments:**
```
// --enable-privileged-webgl-extension (x2)
// console.log( '**' + type + '**', gl.getExtension( 'WEBGL_debug_shaders' ).getTranslatedShaderSource( shader ) ); (x2)
```

<details><summary>Code</summary>

```typescript
function getShaderErrors( gl, shader, type ) {

	const status = gl.getShaderParameter( shader, gl.COMPILE_STATUS );

	const shaderInfoLog = gl.getShaderInfoLog( shader ) || '';
	const errors = shaderInfoLog.trim();

	if ( status && errors === '' ) return '';

	const errorMatches = /ERROR: 0:(\d+)/.exec( errors );
	if ( errorMatches ) {

		// --enable-privileged-webgl-extension
		// console.log( '**' + type + '**', gl.getExtension( 'WEBGL_debug_shaders' ).getTranslatedShaderSource( shader ) );

		const errorLine = parseInt( errorMatches[ 1 ] );
		return type.toUpperCase() + '\n\n' + errors + '\n\n' + handleSource( gl.getShaderSource( shader ), errorLine );

	} else {

		return errors;

	}

}
```
</details>

### `getTexelEncodingFunction(functionName: any, colorSpace: any): string`

**Parameters:**

- **`functionName`** `any`
- **`colorSpace`** `any`

**Returns:** `string`

**Calls:**

- `getEncodingComponents`
- `[

		`vec4 ${functionName}( vec4 value ) {`,

		`	return ${components[ 1 ]}( vec4( value.rgb * ${components[ 0 ]}, value.a ) );`,

		'}',

	].join`

<details><summary>Code</summary>

```typescript
function getTexelEncodingFunction( functionName, colorSpace ) {

	const components = getEncodingComponents( colorSpace );

	return [

		`vec4 ${functionName}( vec4 value ) {`,

		`	return ${components[ 1 ]}( vec4( value.rgb * ${components[ 0 ]}, value.a ) );`,

		'}',

	].join( '\n' );

}
```
</details>

### `getToneMappingFunction(functionName: any, toneMapping: any): string`

**Parameters:**

- **`functionName`** `any`
- **`toneMapping`** `any`

**Returns:** `string`

**Calls:**

- `console.warn`

<details><summary>Code</summary>

```typescript
function getToneMappingFunction( functionName, toneMapping ) {

	let toneMappingName;

	switch ( toneMapping ) {

		case LinearToneMapping:
			toneMappingName = 'Linear';
			break;

		case ReinhardToneMapping:
			toneMappingName = 'Reinhard';
			break;

		case CineonToneMapping:
			toneMappingName = 'Cineon';
			break;

		case ACESFilmicToneMapping:
			toneMappingName = 'ACESFilmic';
			break;

		case AgXToneMapping:
			toneMappingName = 'AgX';
			break;

		case NeutralToneMapping:
			toneMappingName = 'Neutral';
			break;

		case CustomToneMapping:
			toneMappingName = 'Custom';
			break;

		default:
			console.warn( 'THREE.WebGLProgram: Unsupported toneMapping:', toneMapping );
			toneMappingName = 'Linear';

	}

	return 'vec3 ' + functionName + '( vec3 color ) { return ' + toneMappingName + 'ToneMapping( color ); }';

}
```
</details>

### `getLuminanceFunction(): string`

**Returns:** `string`

**Calls:**

- `ColorManagement.getLuminanceCoefficients`
- `_v0.x.toFixed`
- `_v0.y.toFixed`
- `_v0.z.toFixed`
- `[

		'float luminance( const in vec3 rgb ) {',

		`	const vec3 weights = vec3( ${ r }, ${ g }, ${ b } );`,

		'	return dot( weights, rgb );',

		'}'

	].join`

<details><summary>Code</summary>

```typescript
function getLuminanceFunction() {

	ColorManagement.getLuminanceCoefficients( _v0 );

	const r = _v0.x.toFixed( 4 );
	const g = _v0.y.toFixed( 4 );
	const b = _v0.z.toFixed( 4 );

	return [

		'float luminance( const in vec3 rgb ) {',

		`	const vec3 weights = vec3( ${ r }, ${ g }, ${ b } );`,

		'	return dot( weights, rgb );',

		'}'

	].join( '\n' );

}
```
</details>

### `generateVertexExtensions(parameters: any): string`

**Parameters:**

- **`parameters`** `any`

**Returns:** `string`

**Calls:**

- `chunks.filter( filterEmptyLine ).join`

<details><summary>Code</summary>

```typescript
function generateVertexExtensions( parameters ) {

	const chunks = [
		parameters.extensionClipCullDistance ? '#extension GL_ANGLE_clip_cull_distance : require' : '',
		parameters.extensionMultiDraw ? '#extension GL_ANGLE_multi_draw : require' : '',
	];

	return chunks.filter( filterEmptyLine ).join( '\n' );

}
```
</details>

### `generateDefines(defines: any): string`

**Parameters:**

- **`defines`** `any`

**Returns:** `string`

**Calls:**

- `chunks.push`
- `chunks.join`

<details><summary>Code</summary>

```typescript
function generateDefines( defines ) {

	const chunks = [];

	for ( const name in defines ) {

		const value = defines[ name ];

		if ( value === false ) continue;

		chunks.push( '#define ' + name + ' ' + value );

	}

	return chunks.join( '\n' );

}
```
</details>

### `fetchAttributeLocations(gl: any, program: any): {}`

**Parameters:**

- **`gl`** `any`
- **`program`** `any`

**Returns:** `{}`

**Calls:**

- `gl.getProgramParameter`
- `gl.getActiveAttrib`
- `gl.getAttribLocation`

**Internal Comments:**
```
// console.log( 'THREE.WebGLProgram: ACTIVE VERTEX ATTRIBUTE:', name, i ); (x4)
```

<details><summary>Code</summary>

```typescript
function fetchAttributeLocations( gl, program ) {

	const attributes = {};

	const n = gl.getProgramParameter( program, gl.ACTIVE_ATTRIBUTES );

	for ( let i = 0; i < n; i ++ ) {

		const info = gl.getActiveAttrib( program, i );
		const name = info.name;

		let locationSize = 1;
		if ( info.type === gl.FLOAT_MAT2 ) locationSize = 2;
		if ( info.type === gl.FLOAT_MAT3 ) locationSize = 3;
		if ( info.type === gl.FLOAT_MAT4 ) locationSize = 4;

		// console.log( 'THREE.WebGLProgram: ACTIVE VERTEX ATTRIBUTE:', name, i );

		attributes[ name ] = {
			type: info.type,
			location: gl.getAttribLocation( program, name ),
			locationSize: locationSize
		};

	}

	return attributes;

}
```
</details>

### `filterEmptyLine(string: any): boolean`

**Parameters:**

- **`string`** `any`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
function filterEmptyLine( string ) {

	return string !== '';

}
```
</details>

### `replaceLightNums(string: any, parameters: any): any`

**Parameters:**

- **`string`** `any`
- **`parameters`** `any`

**Returns:** `any`

**Calls:**

- `string
		.replace( /NUM_DIR_LIGHTS/g, parameters.numDirLights )
		.replace( /NUM_SPOT_LIGHTS/g, parameters.numSpotLights )
		.replace( /NUM_SPOT_LIGHT_MAPS/g, parameters.numSpotLightMaps )
		.replace( /NUM_SPOT_LIGHT_COORDS/g, numSpotLightCoords )
		.replace( /NUM_RECT_AREA_LIGHTS/g, parameters.numRectAreaLights )
		.replace( /NUM_POINT_LIGHTS/g, parameters.numPointLights )
		.replace( /NUM_HEMI_LIGHTS/g, parameters.numHemiLights )
		.replace( /NUM_DIR_LIGHT_SHADOWS/g, parameters.numDirLightShadows )
		.replace( /NUM_SPOT_LIGHT_SHADOWS_WITH_MAPS/g, parameters.numSpotLightShadowsWithMaps )
		.replace( /NUM_SPOT_LIGHT_SHADOWS/g, parameters.numSpotLightShadows )
		.replace`

<details><summary>Code</summary>

```typescript
function replaceLightNums( string, parameters ) {

	const numSpotLightCoords = parameters.numSpotLightShadows + parameters.numSpotLightMaps - parameters.numSpotLightShadowsWithMaps;

	return string
		.replace( /NUM_DIR_LIGHTS/g, parameters.numDirLights )
		.replace( /NUM_SPOT_LIGHTS/g, parameters.numSpotLights )
		.replace( /NUM_SPOT_LIGHT_MAPS/g, parameters.numSpotLightMaps )
		.replace( /NUM_SPOT_LIGHT_COORDS/g, numSpotLightCoords )
		.replace( /NUM_RECT_AREA_LIGHTS/g, parameters.numRectAreaLights )
		.replace( /NUM_POINT_LIGHTS/g, parameters.numPointLights )
		.replace( /NUM_HEMI_LIGHTS/g, parameters.numHemiLights )
		.replace( /NUM_DIR_LIGHT_SHADOWS/g, parameters.numDirLightShadows )
		.replace( /NUM_SPOT_LIGHT_SHADOWS_WITH_MAPS/g, parameters.numSpotLightShadowsWithMaps )
		.replace( /NUM_SPOT_LIGHT_SHADOWS/g, parameters.numSpotLightShadows )
		.replace( /NUM_POINT_LIGHT_SHADOWS/g, parameters.numPointLightShadows );

}
```
</details>

### `replaceClippingPlaneNums(string: any, parameters: any): any`

**Parameters:**

- **`string`** `any`
- **`parameters`** `any`

**Returns:** `any`

**Calls:**

- `string
		.replace( /NUM_CLIPPING_PLANES/g, parameters.numClippingPlanes )
		.replace`

<details><summary>Code</summary>

```typescript
function replaceClippingPlaneNums( string, parameters ) {

	return string
		.replace( /NUM_CLIPPING_PLANES/g, parameters.numClippingPlanes )
		.replace( /UNION_CLIPPING_PLANES/g, ( parameters.numClippingPlanes - parameters.numClipIntersection ) );

}
```
</details>

### `resolveIncludes(string: any): any`

**Parameters:**

- **`string`** `any`

**Returns:** `any`

**Calls:**

- `string.replace`

<details><summary>Code</summary>

```typescript
function resolveIncludes( string ) {

	return string.replace( includePattern, includeReplacer );

}
```
</details>

### `includeReplacer(match: any, include: any): any`

**Parameters:**

- **`match`** `any`
- **`include`** `any`

**Returns:** `any`

**Calls:**

- `shaderChunkMap.get`
- `console.warn`
- `resolveIncludes`

<details><summary>Code</summary>

```typescript
function includeReplacer( match, include ) {

	let string = ShaderChunk[ include ];

	if ( string === undefined ) {

		const newInclude = shaderChunkMap.get( include );

		if ( newInclude !== undefined ) {

			string = ShaderChunk[ newInclude ];
			console.warn( 'THREE.WebGLRenderer: Shader chunk "%s" has been deprecated. Use "%s" instead.', include, newInclude );

		} else {

			throw new Error( 'Can not resolve #include <' + include + '>' );

		}

	}

	return resolveIncludes( string );

}
```
</details>

### `unrollLoops(string: any): any`

**Parameters:**

- **`string`** `any`

**Returns:** `any`

**Calls:**

- `string.replace`

<details><summary>Code</summary>

```typescript
function unrollLoops( string ) {

	return string.replace( unrollLoopPattern, loopReplacer );

}
```
</details>

### `loopReplacer(match: any, start: any, end: any, snippet: any): string`

**Parameters:**

- **`match`** `any`
- **`start`** `any`
- **`end`** `any`
- **`snippet`** `any`

**Returns:** `string`

**Calls:**

- `parseInt`
- `snippet
			.replace( /\[\s*i\s*\]/g, '[ ' + i + ' ]' )
			.replace`

<details><summary>Code</summary>

```typescript
function loopReplacer( match, start, end, snippet ) {

	let string = '';

	for ( let i = parseInt( start ); i < parseInt( end ); i ++ ) {

		string += snippet
			.replace( /\[\s*i\s*\]/g, '[ ' + i + ' ]' )
			.replace( /UNROLLED_LOOP_INDEX/g, i );

	}

	return string;

}
```
</details>

### `generatePrecision(parameters: any): string`

**Parameters:**

- **`parameters`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function generatePrecision( parameters ) {

	let precisionstring = `precision ${parameters.precision} float;
	precision ${parameters.precision} int;
	precision ${parameters.precision} sampler2D;
	precision ${parameters.precision} samplerCube;
	precision ${parameters.precision} sampler3D;
	precision ${parameters.precision} sampler2DArray;
	precision ${parameters.precision} sampler2DShadow;
	precision ${parameters.precision} samplerCubeShadow;
	precision ${parameters.precision} sampler2DArrayShadow;
	precision ${parameters.precision} isampler2D;
	precision ${parameters.precision} isampler3D;
	precision ${parameters.precision} isamplerCube;
	precision ${parameters.precision} isampler2DArray;
	precision ${parameters.precision} usampler2D;
	precision ${parameters.precision} usampler3D;
	precision ${parameters.precision} usamplerCube;
	precision ${parameters.precision} usampler2DArray;
	`;

	if ( parameters.precision === 'highp' ) {

		precisionstring += '\n#define HIGH_PRECISION';

	} else if ( parameters.precision === 'mediump' ) {

		precisionstring += '\n#define MEDIUM_PRECISION';

	} else if ( parameters.precision === 'lowp' ) {

		precisionstring += '\n#define LOW_PRECISION';

	}

	return precisionstring;

}
```
</details>

### `generateShadowMapTypeDefine(parameters: any): string`

**Parameters:**

- **`parameters`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function generateShadowMapTypeDefine( parameters ) {

	let shadowMapTypeDefine = 'SHADOWMAP_TYPE_BASIC';

	if ( parameters.shadowMapType === PCFShadowMap ) {

		shadowMapTypeDefine = 'SHADOWMAP_TYPE_PCF';

	} else if ( parameters.shadowMapType === PCFSoftShadowMap ) {

		shadowMapTypeDefine = 'SHADOWMAP_TYPE_PCF_SOFT';

	} else if ( parameters.shadowMapType === VSMShadowMap ) {

		shadowMapTypeDefine = 'SHADOWMAP_TYPE_VSM';

	}

	return shadowMapTypeDefine;

}
```
</details>

### `generateEnvMapTypeDefine(parameters: any): string`

**Parameters:**

- **`parameters`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function generateEnvMapTypeDefine( parameters ) {

	let envMapTypeDefine = 'ENVMAP_TYPE_CUBE';

	if ( parameters.envMap ) {

		switch ( parameters.envMapMode ) {

			case CubeReflectionMapping:
			case CubeRefractionMapping:
				envMapTypeDefine = 'ENVMAP_TYPE_CUBE';
				break;

			case CubeUVReflectionMapping:
				envMapTypeDefine = 'ENVMAP_TYPE_CUBE_UV';
				break;

		}

	}

	return envMapTypeDefine;

}
```
</details>

### `generateEnvMapModeDefine(parameters: any): string`

**Parameters:**

- **`parameters`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function generateEnvMapModeDefine( parameters ) {

	let envMapModeDefine = 'ENVMAP_MODE_REFLECTION';

	if ( parameters.envMap ) {

		switch ( parameters.envMapMode ) {

			case CubeRefractionMapping:

				envMapModeDefine = 'ENVMAP_MODE_REFRACTION';
				break;

		}

	}

	return envMapModeDefine;

}
```
</details>

### `generateEnvMapBlendingDefine(parameters: any): string`

**Parameters:**

- **`parameters`** `any`

**Returns:** `string`

<details><summary>Code</summary>

```typescript
function generateEnvMapBlendingDefine( parameters ) {

	let envMapBlendingDefine = 'ENVMAP_BLENDING_NONE';

	if ( parameters.envMap ) {

		switch ( parameters.combine ) {

			case MultiplyOperation:
				envMapBlendingDefine = 'ENVMAP_BLENDING_MULTIPLY';
				break;

			case MixOperation:
				envMapBlendingDefine = 'ENVMAP_BLENDING_MIX';
				break;

			case AddOperation:
				envMapBlendingDefine = 'ENVMAP_BLENDING_ADD';
				break;

		}

	}

	return envMapBlendingDefine;

}
```
</details>

### `generateCubeUVSize(parameters: any): { texelWidth: number; texelHeight: number; maxMip: number; }`

**Parameters:**

- **`parameters`** `any`

**Returns:** `{ texelWidth: number; texelHeight: number; maxMip: number; }`

**Calls:**

- `Math.log2`
- `Math.max`
- `Math.pow`

<details><summary>Code</summary>

```typescript
function generateCubeUVSize( parameters ) {

	const imageHeight = parameters.envMapCubeUVHeight;

	if ( imageHeight === null ) return null;

	const maxMip = Math.log2( imageHeight ) - 2;

	const texelHeight = 1.0 / imageHeight;

	const texelWidth = 1.0 / ( 3 * Math.max( Math.pow( 2, maxMip ), 7 * 16 ) );

	return { texelWidth, texelHeight, maxMip };

}
```
</details>

### `WebGLProgram(renderer: any, cacheKey: any, parameters: any, bindingStates: any): this`

**Parameters:**

- **`renderer`** `any`
- **`cacheKey`** `any`
- **`parameters`** `any`
- **`bindingStates`** `any`

**Returns:** `this`

**Calls:**

- `renderer.getContext`
- `generateShadowMapTypeDefine`
- `generateEnvMapTypeDefine`
- `generateEnvMapModeDefine`
- `generateEnvMapBlendingDefine`
- `generateCubeUVSize`
- `generateVertexExtensions`
- `generateDefines`
- `gl.createProgram`
- `[

			'#define SHADER_TYPE ' + parameters.shaderType,
			'#define SHADER_NAME ' + parameters.shaderName,

			customDefines

		].filter( filterEmptyLine ).join`
- `[

			generatePrecision( parameters ),

			'#define SHADER_TYPE ' + parameters.shaderType,
			'#define SHADER_NAME ' + parameters.shaderName,

			customDefines,

			parameters.extensionClipCullDistance ? '#define USE_CLIP_DISTANCE' : '',
			parameters.batching ? '#define USE_BATCHING' : '',
			parameters.batchingColor ? '#define USE_BATCHING_COLOR' : '',
			parameters.instancing ? '#define USE_INSTANCING' : '',
			parameters.instancingColor ? '#define USE_INSTANCING_COLOR' : '',
			parameters.instancingMorph ? '#define USE_INSTANCING_MORPH' : '',

			parameters.useFog && parameters.fog ? '#define USE_FOG' : '',
			parameters.useFog && parameters.fogExp2 ? '#define FOG_EXP2' : '',

			parameters.map ? '#define USE_MAP' : '',
			parameters.envMap ? '#define USE_ENVMAP' : '',
			parameters.envMap ? '#define ' + envMapModeDefine : '',
			parameters.lightMap ? '#define USE_LIGHTMAP' : '',
			parameters.aoMap ? '#define USE_AOMAP' : '',
			parameters.bumpMap ? '#define USE_BUMPMAP' : '',
			parameters.normalMap ? '#define USE_NORMALMAP' : '',
			parameters.normalMapObjectSpace ? '#define USE_NORMALMAP_OBJECTSPACE' : '',
			parameters.normalMapTangentSpace ? '#define USE_NORMALMAP_TANGENTSPACE' : '',
			parameters.displacementMap ? '#define USE_DISPLACEMENTMAP' : '',
			parameters.emissiveMap ? '#define USE_EMISSIVEMAP' : '',

			parameters.anisotropy ? '#define USE_ANISOTROPY' : '',
			parameters.anisotropyMap ? '#define USE_ANISOTROPYMAP' : '',

			parameters.clearcoatMap ? '#define USE_CLEARCOATMAP' : '',
			parameters.clearcoatRoughnessMap ? '#define USE_CLEARCOAT_ROUGHNESSMAP' : '',
			parameters.clearcoatNormalMap ? '#define USE_CLEARCOAT_NORMALMAP' : '',

			parameters.iridescenceMap ? '#define USE_IRIDESCENCEMAP' : '',
			parameters.iridescenceThicknessMap ? '#define USE_IRIDESCENCE_THICKNESSMAP' : '',

			parameters.specularMap ? '#define USE_SPECULARMAP' : '',
			parameters.specularColorMap ? '#define USE_SPECULAR_COLORMAP' : '',
			parameters.specularIntensityMap ? '#define USE_SPECULAR_INTENSITYMAP' : '',

			parameters.roughnessMap ? '#define USE_ROUGHNESSMAP' : '',
			parameters.metalnessMap ? '#define USE_METALNESSMAP' : '',
			parameters.alphaMap ? '#define USE_ALPHAMAP' : '',
			parameters.alphaHash ? '#define USE_ALPHAHASH' : '',

			parameters.transmission ? '#define USE_TRANSMISSION' : '',
			parameters.transmissionMap ? '#define USE_TRANSMISSIONMAP' : '',
			parameters.thicknessMap ? '#define USE_THICKNESSMAP' : '',

			parameters.sheenColorMap ? '#define USE_SHEEN_COLORMAP' : '',
			parameters.sheenRoughnessMap ? '#define USE_SHEEN_ROUGHNESSMAP' : '',

			//

			parameters.mapUv ? '#define MAP_UV ' + parameters.mapUv : '',
			parameters.alphaMapUv ? '#define ALPHAMAP_UV ' + parameters.alphaMapUv : '',
			parameters.lightMapUv ? '#define LIGHTMAP_UV ' + parameters.lightMapUv : '',
			parameters.aoMapUv ? '#define AOMAP_UV ' + parameters.aoMapUv : '',
			parameters.emissiveMapUv ? '#define EMISSIVEMAP_UV ' + parameters.emissiveMapUv : '',
			parameters.bumpMapUv ? '#define BUMPMAP_UV ' + parameters.bumpMapUv : '',
			parameters.normalMapUv ? '#define NORMALMAP_UV ' + parameters.normalMapUv : '',
			parameters.displacementMapUv ? '#define DISPLACEMENTMAP_UV ' + parameters.displacementMapUv : '',

			parameters.metalnessMapUv ? '#define METALNESSMAP_UV ' + parameters.metalnessMapUv : '',
			parameters.roughnessMapUv ? '#define ROUGHNESSMAP_UV ' + parameters.roughnessMapUv : '',

			parameters.anisotropyMapUv ? '#define ANISOTROPYMAP_UV ' + parameters.anisotropyMapUv : '',

			parameters.clearcoatMapUv ? '#define CLEARCOATMAP_UV ' + parameters.clearcoatMapUv : '',
			parameters.clearcoatNormalMapUv ? '#define CLEARCOAT_NORMALMAP_UV ' + parameters.clearcoatNormalMapUv : '',
			parameters.clearcoatRoughnessMapUv ? '#define CLEARCOAT_ROUGHNESSMAP_UV ' + parameters.clearcoatRoughnessMapUv : '',

			parameters.iridescenceMapUv ? '#define IRIDESCENCEMAP_UV ' + parameters.iridescenceMapUv : '',
			parameters.iridescenceThicknessMapUv ? '#define IRIDESCENCE_THICKNESSMAP_UV ' + parameters.iridescenceThicknessMapUv : '',

			parameters.sheenColorMapUv ? '#define SHEEN_COLORMAP_UV ' + parameters.sheenColorMapUv : '',
			parameters.sheenRoughnessMapUv ? '#define SHEEN_ROUGHNESSMAP_UV ' + parameters.sheenRoughnessMapUv : '',

			parameters.specularMapUv ? '#define SPECULARMAP_UV ' + parameters.specularMapUv : '',
			parameters.specularColorMapUv ? '#define SPECULAR_COLORMAP_UV ' + parameters.specularColorMapUv : '',
			parameters.specularIntensityMapUv ? '#define SPECULAR_INTENSITYMAP_UV ' + parameters.specularIntensityMapUv : '',

			parameters.transmissionMapUv ? '#define TRANSMISSIONMAP_UV ' + parameters.transmissionMapUv : '',
			parameters.thicknessMapUv ? '#define THICKNESSMAP_UV ' + parameters.thicknessMapUv : '',

			//

			parameters.vertexTangents && parameters.flatShading === false ? '#define USE_TANGENT' : '',
			parameters.vertexColors ? '#define USE_COLOR' : '',
			parameters.vertexAlphas ? '#define USE_COLOR_ALPHA' : '',
			parameters.vertexUv1s ? '#define USE_UV1' : '',
			parameters.vertexUv2s ? '#define USE_UV2' : '',
			parameters.vertexUv3s ? '#define USE_UV3' : '',

			parameters.pointsUvs ? '#define USE_POINTS_UV' : '',

			parameters.flatShading ? '#define FLAT_SHADED' : '',

			parameters.skinning ? '#define USE_SKINNING' : '',

			parameters.morphTargets ? '#define USE_MORPHTARGETS' : '',
			parameters.morphNormals && parameters.flatShading === false ? '#define USE_MORPHNORMALS' : '',
			( parameters.morphColors ) ? '#define USE_MORPHCOLORS' : '',
			( parameters.morphTargetsCount > 0 ) ? '#define MORPHTARGETS_TEXTURE_STRIDE ' + parameters.morphTextureStride : '',
			( parameters.morphTargetsCount > 0 ) ? '#define MORPHTARGETS_COUNT ' + parameters.morphTargetsCount : '',
			parameters.doubleSided ? '#define DOUBLE_SIDED' : '',
			parameters.flipSided ? '#define FLIP_SIDED' : '',

			parameters.shadowMapEnabled ? '#define USE_SHADOWMAP' : '',
			parameters.shadowMapEnabled ? '#define ' + shadowMapTypeDefine : '',

			parameters.sizeAttenuation ? '#define USE_SIZEATTENUATION' : '',

			parameters.numLightProbes > 0 ? '#define USE_LIGHT_PROBES' : '',

			parameters.logarithmicDepthBuffer ? '#define USE_LOGDEPTHBUF' : '',
			parameters.reversedDepthBuffer ? '#define USE_REVERSEDEPTHBUF' : '',

			'uniform mat4 modelMatrix;',
			'uniform mat4 modelViewMatrix;',
			'uniform mat4 projectionMatrix;',
			'uniform mat4 viewMatrix;',
			'uniform mat3 normalMatrix;',
			'uniform vec3 cameraPosition;',
			'uniform bool isOrthographic;',

			'#ifdef USE_INSTANCING',

			'	attribute mat4 instanceMatrix;',

			'#endif',

			'#ifdef USE_INSTANCING_COLOR',

			'	attribute vec3 instanceColor;',

			'#endif',

			'#ifdef USE_INSTANCING_MORPH',

			'	uniform sampler2D morphTexture;',

			'#endif',

			'attribute vec3 position;',
			'attribute vec3 normal;',
			'attribute vec2 uv;',

			'#ifdef USE_UV1',

			'	attribute vec2 uv1;',

			'#endif',

			'#ifdef USE_UV2',

			'	attribute vec2 uv2;',

			'#endif',

			'#ifdef USE_UV3',

			'	attribute vec2 uv3;',

			'#endif',

			'#ifdef USE_TANGENT',

			'	attribute vec4 tangent;',

			'#endif',

			'#if defined( USE_COLOR_ALPHA )',

			'	attribute vec4 color;',

			'#elif defined( USE_COLOR )',

			'	attribute vec3 color;',

			'#endif',

			'#ifdef USE_SKINNING',

			'	attribute vec4 skinIndex;',
			'	attribute vec4 skinWeight;',

			'#endif',

			'\n'

		].filter( filterEmptyLine ).join`
- `[

			generatePrecision( parameters ),

			'#define SHADER_TYPE ' + parameters.shaderType,
			'#define SHADER_NAME ' + parameters.shaderName,

			customDefines,

			parameters.useFog && parameters.fog ? '#define USE_FOG' : '',
			parameters.useFog && parameters.fogExp2 ? '#define FOG_EXP2' : '',

			parameters.alphaToCoverage ? '#define ALPHA_TO_COVERAGE' : '',
			parameters.map ? '#define USE_MAP' : '',
			parameters.matcap ? '#define USE_MATCAP' : '',
			parameters.envMap ? '#define USE_ENVMAP' : '',
			parameters.envMap ? '#define ' + envMapTypeDefine : '',
			parameters.envMap ? '#define ' + envMapModeDefine : '',
			parameters.envMap ? '#define ' + envMapBlendingDefine : '',
			envMapCubeUVSize ? '#define CUBEUV_TEXEL_WIDTH ' + envMapCubeUVSize.texelWidth : '',
			envMapCubeUVSize ? '#define CUBEUV_TEXEL_HEIGHT ' + envMapCubeUVSize.texelHeight : '',
			envMapCubeUVSize ? '#define CUBEUV_MAX_MIP ' + envMapCubeUVSize.maxMip + '.0' : '',
			parameters.lightMap ? '#define USE_LIGHTMAP' : '',
			parameters.aoMap ? '#define USE_AOMAP' : '',
			parameters.bumpMap ? '#define USE_BUMPMAP' : '',
			parameters.normalMap ? '#define USE_NORMALMAP' : '',
			parameters.normalMapObjectSpace ? '#define USE_NORMALMAP_OBJECTSPACE' : '',
			parameters.normalMapTangentSpace ? '#define USE_NORMALMAP_TANGENTSPACE' : '',
			parameters.emissiveMap ? '#define USE_EMISSIVEMAP' : '',

			parameters.anisotropy ? '#define USE_ANISOTROPY' : '',
			parameters.anisotropyMap ? '#define USE_ANISOTROPYMAP' : '',

			parameters.clearcoat ? '#define USE_CLEARCOAT' : '',
			parameters.clearcoatMap ? '#define USE_CLEARCOATMAP' : '',
			parameters.clearcoatRoughnessMap ? '#define USE_CLEARCOAT_ROUGHNESSMAP' : '',
			parameters.clearcoatNormalMap ? '#define USE_CLEARCOAT_NORMALMAP' : '',

			parameters.dispersion ? '#define USE_DISPERSION' : '',

			parameters.iridescence ? '#define USE_IRIDESCENCE' : '',
			parameters.iridescenceMap ? '#define USE_IRIDESCENCEMAP' : '',
			parameters.iridescenceThicknessMap ? '#define USE_IRIDESCENCE_THICKNESSMAP' : '',

			parameters.specularMap ? '#define USE_SPECULARMAP' : '',
			parameters.specularColorMap ? '#define USE_SPECULAR_COLORMAP' : '',
			parameters.specularIntensityMap ? '#define USE_SPECULAR_INTENSITYMAP' : '',

			parameters.roughnessMap ? '#define USE_ROUGHNESSMAP' : '',
			parameters.metalnessMap ? '#define USE_METALNESSMAP' : '',

			parameters.alphaMap ? '#define USE_ALPHAMAP' : '',
			parameters.alphaTest ? '#define USE_ALPHATEST' : '',
			parameters.alphaHash ? '#define USE_ALPHAHASH' : '',

			parameters.sheen ? '#define USE_SHEEN' : '',
			parameters.sheenColorMap ? '#define USE_SHEEN_COLORMAP' : '',
			parameters.sheenRoughnessMap ? '#define USE_SHEEN_ROUGHNESSMAP' : '',

			parameters.transmission ? '#define USE_TRANSMISSION' : '',
			parameters.transmissionMap ? '#define USE_TRANSMISSIONMAP' : '',
			parameters.thicknessMap ? '#define USE_THICKNESSMAP' : '',

			parameters.vertexTangents && parameters.flatShading === false ? '#define USE_TANGENT' : '',
			parameters.vertexColors || parameters.instancingColor || parameters.batchingColor ? '#define USE_COLOR' : '',
			parameters.vertexAlphas ? '#define USE_COLOR_ALPHA' : '',
			parameters.vertexUv1s ? '#define USE_UV1' : '',
			parameters.vertexUv2s ? '#define USE_UV2' : '',
			parameters.vertexUv3s ? '#define USE_UV3' : '',

			parameters.pointsUvs ? '#define USE_POINTS_UV' : '',

			parameters.gradientMap ? '#define USE_GRADIENTMAP' : '',

			parameters.flatShading ? '#define FLAT_SHADED' : '',

			parameters.doubleSided ? '#define DOUBLE_SIDED' : '',
			parameters.flipSided ? '#define FLIP_SIDED' : '',

			parameters.shadowMapEnabled ? '#define USE_SHADOWMAP' : '',
			parameters.shadowMapEnabled ? '#define ' + shadowMapTypeDefine : '',

			parameters.premultipliedAlpha ? '#define PREMULTIPLIED_ALPHA' : '',

			parameters.numLightProbes > 0 ? '#define USE_LIGHT_PROBES' : '',

			parameters.decodeVideoTexture ? '#define DECODE_VIDEO_TEXTURE' : '',
			parameters.decodeVideoTextureEmissive ? '#define DECODE_VIDEO_TEXTURE_EMISSIVE' : '',

			parameters.logarithmicDepthBuffer ? '#define USE_LOGDEPTHBUF' : '',
			parameters.reversedDepthBuffer ? '#define USE_REVERSEDEPTHBUF' : '',

			'uniform mat4 viewMatrix;',
			'uniform vec3 cameraPosition;',
			'uniform bool isOrthographic;',

			( parameters.toneMapping !== NoToneMapping ) ? '#define TONE_MAPPING' : '',
			( parameters.toneMapping !== NoToneMapping ) ? ShaderChunk[ 'tonemapping_pars_fragment' ] : '', // this code is required here because it is used by the toneMapping() function defined below
			( parameters.toneMapping !== NoToneMapping ) ? getToneMappingFunction( 'toneMapping', parameters.toneMapping ) : '',

			parameters.dithering ? '#define DITHERING' : '',
			parameters.opaque ? '#define OPAQUE' : '',

			ShaderChunk[ 'colorspace_pars_fragment' ], // this code is required here because it is used by the various encoding/decoding function defined below
			getTexelEncodingFunction( 'linearToOutputTexel', parameters.outputColorSpace ),
			getLuminanceFunction(),

			parameters.useDepthPacking ? '#define DEPTH_PACKING ' + parameters.depthPacking : '',

			'\n'

		].filter( filterEmptyLine ).join`
- `resolveIncludes`
- `replaceLightNums`
- `replaceClippingPlaneNums`
- `unrollLoops`
- `[
			customVertexExtensions,
			'#define attribute in',
			'#define varying out',
			'#define texture2D texture'
		].join`
- `[
			'#define varying in',
			( parameters.glslVersion === GLSL3 ) ? '' : 'layout(location = 0) out highp vec4 pc_fragColor;',
			( parameters.glslVersion === GLSL3 ) ? '' : '#define gl_FragColor pc_fragColor',
			'#define gl_FragDepthEXT gl_FragDepth',
			'#define texture2D texture',
			'#define textureCube texture',
			'#define texture2DProj textureProj',
			'#define texture2DLodEXT textureLod',
			'#define texture2DProjLodEXT textureProjLod',
			'#define textureCubeLodEXT textureLod',
			'#define texture2DGradEXT textureGrad',
			'#define texture2DProjGradEXT textureProjGrad',
			'#define textureCubeGradEXT textureGrad'
		].join`
- `WebGLShader (from ./WebGLShader.js)`
- `gl.attachShader`
- `gl.bindAttribLocation`
- `gl.linkProgram`
- `gl.getProgramInfoLog`
- `gl.getShaderInfoLog`
- `programInfoLog.trim`
- `vertexShaderInfoLog.trim`
- `fragmentShaderInfoLog.trim`
- `gl.getProgramParameter`
- `renderer.debug.onShaderError`
- `getShaderErrors`
- `console.error`
- `gl.getError`
- `console.warn`
- `gl.deleteShader`
- `fetchAttributeLocations`
- `onFirstUse`
- `bindingStates.releaseStatesOfProgram`
- `gl.deleteProgram`

**Internal Comments:**
```
// TODO Send this event to Three.js DevTools (x2)
// console.log( 'WebGLProgram', cacheKey ); (x2)
// (x11)
// GLSL 3.0 conversion for built-in materials and ShaderMaterial (x3)
// console.log( '*VERTEX*', vertexGlsl ); (x2)
// console.log( '*FRAGMENT*', fragmentGlsl ); (x2)
// Force a particular attribute to index 0.
// programs with morphTargets displace position out of attribute 0 (x4)
// check for link errors
// default error reporting (x2)
// Clean up (x4)
// Crashes in iOS9 and iOS10. #18402 (x4)
// gl.detachShader( program, glVertexShader ); (x4)
// gl.detachShader( program, glFragmentShader ); (x4)
// set up caching for uniform locations (x2)
// Populates cachedUniforms and cachedAttributes (x3)
// set up caching for attribute locations (x2)
// Populates cachedAttributes and cachedUniforms (x3)
// indicate when the program is ready to be used. if the KHR_parallel_shader_compile extension isn't supported, (x2)
// flag the program as ready immediately. It may cause a stall when it's first used. (x2)
// free resource (x4)
```

<details><summary>Code</summary>

```typescript
function WebGLProgram( renderer, cacheKey, parameters, bindingStates ) {

	// TODO Send this event to Three.js DevTools
	// console.log( 'WebGLProgram', cacheKey );

	const gl = renderer.getContext();

	const defines = parameters.defines;

	let vertexShader = parameters.vertexShader;
	let fragmentShader = parameters.fragmentShader;

	const shadowMapTypeDefine = generateShadowMapTypeDefine( parameters );
	const envMapTypeDefine = generateEnvMapTypeDefine( parameters );
	const envMapModeDefine = generateEnvMapModeDefine( parameters );
	const envMapBlendingDefine = generateEnvMapBlendingDefine( parameters );
	const envMapCubeUVSize = generateCubeUVSize( parameters );

	const customVertexExtensions = generateVertexExtensions( parameters );

	const customDefines = generateDefines( defines );

	const program = gl.createProgram();

	let prefixVertex, prefixFragment;
	let versionString = parameters.glslVersion ? '#version ' + parameters.glslVersion + '\n' : '';

	if ( parameters.isRawShaderMaterial ) {

		prefixVertex = [

			'#define SHADER_TYPE ' + parameters.shaderType,
			'#define SHADER_NAME ' + parameters.shaderName,

			customDefines

		].filter( filterEmptyLine ).join( '\n' );

		if ( prefixVertex.length > 0 ) {

			prefixVertex += '\n';

		}

		prefixFragment = [

			'#define SHADER_TYPE ' + parameters.shaderType,
			'#define SHADER_NAME ' + parameters.shaderName,

			customDefines

		].filter( filterEmptyLine ).join( '\n' );

		if ( prefixFragment.length > 0 ) {

			prefixFragment += '\n';

		}

	} else {

		prefixVertex = [

			generatePrecision( parameters ),

			'#define SHADER_TYPE ' + parameters.shaderType,
			'#define SHADER_NAME ' + parameters.shaderName,

			customDefines,

			parameters.extensionClipCullDistance ? '#define USE_CLIP_DISTANCE' : '',
			parameters.batching ? '#define USE_BATCHING' : '',
			parameters.batchingColor ? '#define USE_BATCHING_COLOR' : '',
			parameters.instancing ? '#define USE_INSTANCING' : '',
			parameters.instancingColor ? '#define USE_INSTANCING_COLOR' : '',
			parameters.instancingMorph ? '#define USE_INSTANCING_MORPH' : '',

			parameters.useFog && parameters.fog ? '#define USE_FOG' : '',
			parameters.useFog && parameters.fogExp2 ? '#define FOG_EXP2' : '',

			parameters.map ? '#define USE_MAP' : '',
			parameters.envMap ? '#define USE_ENVMAP' : '',
			parameters.envMap ? '#define ' + envMapModeDefine : '',
			parameters.lightMap ? '#define USE_LIGHTMAP' : '',
			parameters.aoMap ? '#define USE_AOMAP' : '',
			parameters.bumpMap ? '#define USE_BUMPMAP' : '',
			parameters.normalMap ? '#define USE_NORMALMAP' : '',
			parameters.normalMapObjectSpace ? '#define USE_NORMALMAP_OBJECTSPACE' : '',
			parameters.normalMapTangentSpace ? '#define USE_NORMALMAP_TANGENTSPACE' : '',
			parameters.displacementMap ? '#define USE_DISPLACEMENTMAP' : '',
			parameters.emissiveMap ? '#define USE_EMISSIVEMAP' : '',

			parameters.anisotropy ? '#define USE_ANISOTROPY' : '',
			parameters.anisotropyMap ? '#define USE_ANISOTROPYMAP' : '',

			parameters.clearcoatMap ? '#define USE_CLEARCOATMAP' : '',
			parameters.clearcoatRoughnessMap ? '#define USE_CLEARCOAT_ROUGHNESSMAP' : '',
			parameters.clearcoatNormalMap ? '#define USE_CLEARCOAT_NORMALMAP' : '',

			parameters.iridescenceMap ? '#define USE_IRIDESCENCEMAP' : '',
			parameters.iridescenceThicknessMap ? '#define USE_IRIDESCENCE_THICKNESSMAP' : '',

			parameters.specularMap ? '#define USE_SPECULARMAP' : '',
			parameters.specularColorMap ? '#define USE_SPECULAR_COLORMAP' : '',
			parameters.specularIntensityMap ? '#define USE_SPECULAR_INTENSITYMAP' : '',

			parameters.roughnessMap ? '#define USE_ROUGHNESSMAP' : '',
			parameters.metalnessMap ? '#define USE_METALNESSMAP' : '',
			parameters.alphaMap ? '#define USE_ALPHAMAP' : '',
			parameters.alphaHash ? '#define USE_ALPHAHASH' : '',

			parameters.transmission ? '#define USE_TRANSMISSION' : '',
			parameters.transmissionMap ? '#define USE_TRANSMISSIONMAP' : '',
			parameters.thicknessMap ? '#define USE_THICKNESSMAP' : '',

			parameters.sheenColorMap ? '#define USE_SHEEN_COLORMAP' : '',
			parameters.sheenRoughnessMap ? '#define USE_SHEEN_ROUGHNESSMAP' : '',

			//

			parameters.mapUv ? '#define MAP_UV ' + parameters.mapUv : '',
			parameters.alphaMapUv ? '#define ALPHAMAP_UV ' + parameters.alphaMapUv : '',
			parameters.lightMapUv ? '#define LIGHTMAP_UV ' + parameters.lightMapUv : '',
			parameters.aoMapUv ? '#define AOMAP_UV ' + parameters.aoMapUv : '',
			parameters.emissiveMapUv ? '#define EMISSIVEMAP_UV ' + parameters.emissiveMapUv : '',
			parameters.bumpMapUv ? '#define BUMPMAP_UV ' + parameters.bumpMapUv : '',
			parameters.normalMapUv ? '#define NORMALMAP_UV ' + parameters.normalMapUv : '',
			parameters.displacementMapUv ? '#define DISPLACEMENTMAP_UV ' + parameters.displacementMapUv : '',

			parameters.metalnessMapUv ? '#define METALNESSMAP_UV ' + parameters.metalnessMapUv : '',
			parameters.roughnessMapUv ? '#define ROUGHNESSMAP_UV ' + parameters.roughnessMapUv : '',

			parameters.anisotropyMapUv ? '#define ANISOTROPYMAP_UV ' + parameters.anisotropyMapUv : '',

			parameters.clearcoatMapUv ? '#define CLEARCOATMAP_UV ' + parameters.clearcoatMapUv : '',
			parameters.clearcoatNormalMapUv ? '#define CLEARCOAT_NORMALMAP_UV ' + parameters.clearcoatNormalMapUv : '',
			parameters.clearcoatRoughnessMapUv ? '#define CLEARCOAT_ROUGHNESSMAP_UV ' + parameters.clearcoatRoughnessMapUv : '',

			parameters.iridescenceMapUv ? '#define IRIDESCENCEMAP_UV ' + parameters.iridescenceMapUv : '',
			parameters.iridescenceThicknessMapUv ? '#define IRIDESCENCE_THICKNESSMAP_UV ' + parameters.iridescenceThicknessMapUv : '',

			parameters.sheenColorMapUv ? '#define SHEEN_COLORMAP_UV ' + parameters.sheenColorMapUv : '',
			parameters.sheenRoughnessMapUv ? '#define SHEEN_ROUGHNESSMAP_UV ' + parameters.sheenRoughnessMapUv : '',

			parameters.specularMapUv ? '#define SPECULARMAP_UV ' + parameters.specularMapUv : '',
			parameters.specularColorMapUv ? '#define SPECULAR_COLORMAP_UV ' + parameters.specularColorMapUv : '',
			parameters.specularIntensityMapUv ? '#define SPECULAR_INTENSITYMAP_UV ' + parameters.specularIntensityMapUv : '',

			parameters.transmissionMapUv ? '#define TRANSMISSIONMAP_UV ' + parameters.transmissionMapUv : '',
			parameters.thicknessMapUv ? '#define THICKNESSMAP_UV ' + parameters.thicknessMapUv : '',

			//

			parameters.vertexTangents && parameters.flatShading === false ? '#define USE_TANGENT' : '',
			parameters.vertexColors ? '#define USE_COLOR' : '',
			parameters.vertexAlphas ? '#define USE_COLOR_ALPHA' : '',
			parameters.vertexUv1s ? '#define USE_UV1' : '',
			parameters.vertexUv2s ? '#define USE_UV2' : '',
			parameters.vertexUv3s ? '#define USE_UV3' : '',

			parameters.pointsUvs ? '#define USE_POINTS_UV' : '',

			parameters.flatShading ? '#define FLAT_SHADED' : '',

			parameters.skinning ? '#define USE_SKINNING' : '',

			parameters.morphTargets ? '#define USE_MORPHTARGETS' : '',
			parameters.morphNormals && parameters.flatShading === false ? '#define USE_MORPHNORMALS' : '',
			( parameters.morphColors ) ? '#define USE_MORPHCOLORS' : '',
			( parameters.morphTargetsCount > 0 ) ? '#define MORPHTARGETS_TEXTURE_STRIDE ' + parameters.morphTextureStride : '',
			( parameters.morphTargetsCount > 0 ) ? '#define MORPHTARGETS_COUNT ' + parameters.morphTargetsCount : '',
			parameters.doubleSided ? '#define DOUBLE_SIDED' : '',
			parameters.flipSided ? '#define FLIP_SIDED' : '',

			parameters.shadowMapEnabled ? '#define USE_SHADOWMAP' : '',
			parameters.shadowMapEnabled ? '#define ' + shadowMapTypeDefine : '',

			parameters.sizeAttenuation ? '#define USE_SIZEATTENUATION' : '',

			parameters.numLightProbes > 0 ? '#define USE_LIGHT_PROBES' : '',

			parameters.logarithmicDepthBuffer ? '#define USE_LOGDEPTHBUF' : '',
			parameters.reversedDepthBuffer ? '#define USE_REVERSEDEPTHBUF' : '',

			'uniform mat4 modelMatrix;',
			'uniform mat4 modelViewMatrix;',
			'uniform mat4 projectionMatrix;',
			'uniform mat4 viewMatrix;',
			'uniform mat3 normalMatrix;',
			'uniform vec3 cameraPosition;',
			'uniform bool isOrthographic;',

			'#ifdef USE_INSTANCING',

			'	attribute mat4 instanceMatrix;',

			'#endif',

			'#ifdef USE_INSTANCING_COLOR',

			'	attribute vec3 instanceColor;',

			'#endif',

			'#ifdef USE_INSTANCING_MORPH',

			'	uniform sampler2D morphTexture;',

			'#endif',

			'attribute vec3 position;',
			'attribute vec3 normal;',
			'attribute vec2 uv;',

			'#ifdef USE_UV1',

			'	attribute vec2 uv1;',

			'#endif',

			'#ifdef USE_UV2',

			'	attribute vec2 uv2;',

			'#endif',

			'#ifdef USE_UV3',

			'	attribute vec2 uv3;',

			'#endif',

			'#ifdef USE_TANGENT',

			'	attribute vec4 tangent;',

			'#endif',

			'#if defined( USE_COLOR_ALPHA )',

			'	attribute vec4 color;',

			'#elif defined( USE_COLOR )',

			'	attribute vec3 color;',

			'#endif',

			'#ifdef USE_SKINNING',

			'	attribute vec4 skinIndex;',
			'	attribute vec4 skinWeight;',

			'#endif',

			'\n'

		].filter( filterEmptyLine ).join( '\n' );

		prefixFragment = [

			generatePrecision( parameters ),

			'#define SHADER_TYPE ' + parameters.shaderType,
			'#define SHADER_NAME ' + parameters.shaderName,

			customDefines,

			parameters.useFog && parameters.fog ? '#define USE_FOG' : '',
			parameters.useFog && parameters.fogExp2 ? '#define FOG_EXP2' : '',

			parameters.alphaToCoverage ? '#define ALPHA_TO_COVERAGE' : '',
			parameters.map ? '#define USE_MAP' : '',
			parameters.matcap ? '#define USE_MATCAP' : '',
			parameters.envMap ? '#define USE_ENVMAP' : '',
			parameters.envMap ? '#define ' + envMapTypeDefine : '',
			parameters.envMap ? '#define ' + envMapModeDefine : '',
			parameters.envMap ? '#define ' + envMapBlendingDefine : '',
			envMapCubeUVSize ? '#define CUBEUV_TEXEL_WIDTH ' + envMapCubeUVSize.texelWidth : '',
			envMapCubeUVSize ? '#define CUBEUV_TEXEL_HEIGHT ' + envMapCubeUVSize.texelHeight : '',
			envMapCubeUVSize ? '#define CUBEUV_MAX_MIP ' + envMapCubeUVSize.maxMip + '.0' : '',
			parameters.lightMap ? '#define USE_LIGHTMAP' : '',
			parameters.aoMap ? '#define USE_AOMAP' : '',
			parameters.bumpMap ? '#define USE_BUMPMAP' : '',
			parameters.normalMap ? '#define USE_NORMALMAP' : '',
			parameters.normalMapObjectSpace ? '#define USE_NORMALMAP_OBJECTSPACE' : '',
			parameters.normalMapTangentSpace ? '#define USE_NORMALMAP_TANGENTSPACE' : '',
			parameters.emissiveMap ? '#define USE_EMISSIVEMAP' : '',

			parameters.anisotropy ? '#define USE_ANISOTROPY' : '',
			parameters.anisotropyMap ? '#define USE_ANISOTROPYMAP' : '',

			parameters.clearcoat ? '#define USE_CLEARCOAT' : '',
			parameters.clearcoatMap ? '#define USE_CLEARCOATMAP' : '',
			parameters.clearcoatRoughnessMap ? '#define USE_CLEARCOAT_ROUGHNESSMAP' : '',
			parameters.clearcoatNormalMap ? '#define USE_CLEARCOAT_NORMALMAP' : '',

			parameters.dispersion ? '#define USE_DISPERSION' : '',

			parameters.iridescence ? '#define USE_IRIDESCENCE' : '',
			parameters.iridescenceMap ? '#define USE_IRIDESCENCEMAP' : '',
			parameters.iridescenceThicknessMap ? '#define USE_IRIDESCENCE_THICKNESSMAP' : '',

			parameters.specularMap ? '#define USE_SPECULARMAP' : '',
			parameters.specularColorMap ? '#define USE_SPECULAR_COLORMAP' : '',
			parameters.specularIntensityMap ? '#define USE_SPECULAR_INTENSITYMAP' : '',

			parameters.roughnessMap ? '#define USE_ROUGHNESSMAP' : '',
			parameters.metalnessMap ? '#define USE_METALNESSMAP' : '',

			parameters.alphaMap ? '#define USE_ALPHAMAP' : '',
			parameters.alphaTest ? '#define USE_ALPHATEST' : '',
			parameters.alphaHash ? '#define USE_ALPHAHASH' : '',

			parameters.sheen ? '#define USE_SHEEN' : '',
			parameters.sheenColorMap ? '#define USE_SHEEN_COLORMAP' : '',
			parameters.sheenRoughnessMap ? '#define USE_SHEEN_ROUGHNESSMAP' : '',

			parameters.transmission ? '#define USE_TRANSMISSION' : '',
			parameters.transmissionMap ? '#define USE_TRANSMISSIONMAP' : '',
			parameters.thicknessMap ? '#define USE_THICKNESSMAP' : '',

			parameters.vertexTangents && parameters.flatShading === false ? '#define USE_TANGENT' : '',
			parameters.vertexColors || parameters.instancingColor || parameters.batchingColor ? '#define USE_COLOR' : '',
			parameters.vertexAlphas ? '#define USE_COLOR_ALPHA' : '',
			parameters.vertexUv1s ? '#define USE_UV1' : '',
			parameters.vertexUv2s ? '#define USE_UV2' : '',
			parameters.vertexUv3s ? '#define USE_UV3' : '',

			parameters.pointsUvs ? '#define USE_POINTS_UV' : '',

			parameters.gradientMap ? '#define USE_GRADIENTMAP' : '',

			parameters.flatShading ? '#define FLAT_SHADED' : '',

			parameters.doubleSided ? '#define DOUBLE_SIDED' : '',
			parameters.flipSided ? '#define FLIP_SIDED' : '',

			parameters.shadowMapEnabled ? '#define USE_SHADOWMAP' : '',
			parameters.shadowMapEnabled ? '#define ' + shadowMapTypeDefine : '',

			parameters.premultipliedAlpha ? '#define PREMULTIPLIED_ALPHA' : '',

			parameters.numLightProbes > 0 ? '#define USE_LIGHT_PROBES' : '',

			parameters.decodeVideoTexture ? '#define DECODE_VIDEO_TEXTURE' : '',
			parameters.decodeVideoTextureEmissive ? '#define DECODE_VIDEO_TEXTURE_EMISSIVE' : '',

			parameters.logarithmicDepthBuffer ? '#define USE_LOGDEPTHBUF' : '',
			parameters.reversedDepthBuffer ? '#define USE_REVERSEDEPTHBUF' : '',

			'uniform mat4 viewMatrix;',
			'uniform vec3 cameraPosition;',
			'uniform bool isOrthographic;',

			( parameters.toneMapping !== NoToneMapping ) ? '#define TONE_MAPPING' : '',
			( parameters.toneMapping !== NoToneMapping ) ? ShaderChunk[ 'tonemapping_pars_fragment' ] : '', // this code is required here because it is used by the toneMapping() function defined below
			( parameters.toneMapping !== NoToneMapping ) ? getToneMappingFunction( 'toneMapping', parameters.toneMapping ) : '',

			parameters.dithering ? '#define DITHERING' : '',
			parameters.opaque ? '#define OPAQUE' : '',

			ShaderChunk[ 'colorspace_pars_fragment' ], // this code is required here because it is used by the various encoding/decoding function defined below
			getTexelEncodingFunction( 'linearToOutputTexel', parameters.outputColorSpace ),
			getLuminanceFunction(),

			parameters.useDepthPacking ? '#define DEPTH_PACKING ' + parameters.depthPacking : '',

			'\n'

		].filter( filterEmptyLine ).join( '\n' );

	}

	vertexShader = resolveIncludes( vertexShader );
	vertexShader = replaceLightNums( vertexShader, parameters );
	vertexShader = replaceClippingPlaneNums( vertexShader, parameters );

	fragmentShader = resolveIncludes( fragmentShader );
	fragmentShader = replaceLightNums( fragmentShader, parameters );
	fragmentShader = replaceClippingPlaneNums( fragmentShader, parameters );

	vertexShader = unrollLoops( vertexShader );
	fragmentShader = unrollLoops( fragmentShader );

	if ( parameters.isRawShaderMaterial !== true ) {

		// GLSL 3.0 conversion for built-in materials and ShaderMaterial

		versionString = '#version 300 es\n';

		prefixVertex = [
			customVertexExtensions,
			'#define attribute in',
			'#define varying out',
			'#define texture2D texture'
		].join( '\n' ) + '\n' + prefixVertex;

		prefixFragment = [
			'#define varying in',
			( parameters.glslVersion === GLSL3 ) ? '' : 'layout(location = 0) out highp vec4 pc_fragColor;',
			( parameters.glslVersion === GLSL3 ) ? '' : '#define gl_FragColor pc_fragColor',
			'#define gl_FragDepthEXT gl_FragDepth',
			'#define texture2D texture',
			'#define textureCube texture',
			'#define texture2DProj textureProj',
			'#define texture2DLodEXT textureLod',
			'#define texture2DProjLodEXT textureProjLod',
			'#define textureCubeLodEXT textureLod',
			'#define texture2DGradEXT textureGrad',
			'#define texture2DProjGradEXT textureProjGrad',
			'#define textureCubeGradEXT textureGrad'
		].join( '\n' ) + '\n' + prefixFragment;

	}

	const vertexGlsl = versionString + prefixVertex + vertexShader;
	const fragmentGlsl = versionString + prefixFragment + fragmentShader;

	// console.log( '*VERTEX*', vertexGlsl );
	// console.log( '*FRAGMENT*', fragmentGlsl );

	const glVertexShader = WebGLShader( gl, gl.VERTEX_SHADER, vertexGlsl );
	const glFragmentShader = WebGLShader( gl, gl.FRAGMENT_SHADER, fragmentGlsl );

	gl.attachShader( program, glVertexShader );
	gl.attachShader( program, glFragmentShader );

	// Force a particular attribute to index 0.

	if ( parameters.index0AttributeName !== undefined ) {

		gl.bindAttribLocation( program, 0, parameters.index0AttributeName );

	} else if ( parameters.morphTargets === true ) {

		// programs with morphTargets displace position out of attribute 0
		gl.bindAttribLocation( program, 0, 'position' );

	}

	gl.linkProgram( program );

	function onFirstUse( self ) {

		// check for link errors
		if ( renderer.debug.checkShaderErrors ) {

			const programInfoLog = gl.getProgramInfoLog( program ) || '';
			const vertexShaderInfoLog = gl.getShaderInfoLog( glVertexShader ) || '';
			const fragmentShaderInfoLog = gl.getShaderInfoLog( glFragmentShader ) || '';

			const programLog = programInfoLog.trim();
			const vertexLog = vertexShaderInfoLog.trim();
			const fragmentLog = fragmentShaderInfoLog.trim();

			let runnable = true;
			let haveDiagnostics = true;

			if ( gl.getProgramParameter( program, gl.LINK_STATUS ) === false ) {

				runnable = false;

				if ( typeof renderer.debug.onShaderError === 'function' ) {

					renderer.debug.onShaderError( gl, program, glVertexShader, glFragmentShader );

				} else {

					// default error reporting

					const vertexErrors = getShaderErrors( gl, glVertexShader, 'vertex' );
					const fragmentErrors = getShaderErrors( gl, glFragmentShader, 'fragment' );

					console.error(
						'THREE.WebGLProgram: Shader Error ' + gl.getError() + ' - ' +
						'VALIDATE_STATUS ' + gl.getProgramParameter( program, gl.VALIDATE_STATUS ) + '\n\n' +
						'Material Name: ' + self.name + '\n' +
						'Material Type: ' + self.type + '\n\n' +
						'Program Info Log: ' + programLog + '\n' +
						vertexErrors + '\n' +
						fragmentErrors
					);

				}

			} else if ( programLog !== '' ) {

				console.warn( 'THREE.WebGLProgram: Program Info Log:', programLog );

			} else if ( vertexLog === '' || fragmentLog === '' ) {

				haveDiagnostics = false;

			}

			if ( haveDiagnostics ) {

				self.diagnostics = {

					runnable: runnable,

					programLog: programLog,

					vertexShader: {

						log: vertexLog,
						prefix: prefixVertex

					},

					fragmentShader: {

						log: fragmentLog,
						prefix: prefixFragment

					}

				};

			}

		}

		// Clean up

		// Crashes in iOS9 and iOS10. #18402
		// gl.detachShader( program, glVertexShader );
		// gl.detachShader( program, glFragmentShader );

		gl.deleteShader( glVertexShader );
		gl.deleteShader( glFragmentShader );

		cachedUniforms = new WebGLUniforms( gl, program );
		cachedAttributes = fetchAttributeLocations( gl, program );

	}

	// set up caching for uniform locations

	let cachedUniforms;

	this.getUniforms = function () {

		if ( cachedUniforms === undefined ) {

			// Populates cachedUniforms and cachedAttributes
			onFirstUse( this );

		}

		return cachedUniforms;

	};

	// set up caching for attribute locations

	let cachedAttributes;

	this.getAttributes = function () {

		if ( cachedAttributes === undefined ) {

			// Populates cachedAttributes and cachedUniforms
			onFirstUse( this );

		}

		return cachedAttributes;

	};

	// indicate when the program is ready to be used. if the KHR_parallel_shader_compile extension isn't supported,
	// flag the program as ready immediately. It may cause a stall when it's first used.

	let programReady = ( parameters.rendererExtensionParallelShaderCompile === false );

	this.isReady = function () {

		if ( programReady === false ) {

			programReady = gl.getProgramParameter( program, COMPLETION_STATUS_KHR );

		}

		return programReady;

	};

	// free resource

	this.destroy = function () {

		bindingStates.releaseStatesOfProgram( this );

		gl.deleteProgram( program );
		this.program = undefined;

	};

	//

	this.type = parameters.shaderType;
	this.name = parameters.shaderName;
	this.id = programIdCount ++;
	this.cacheKey = cacheKey;
	this.usedTimes = 1;
	this.program = program;
	this.vertexShader = glVertexShader;
	this.fragmentShader = glFragmentShader;

	return this;

}
```
</details>

### `onFirstUse(self: any): void`

**Parameters:**

- **`self`** `any`

**Returns:** `void`

**Calls:**

- `gl.getProgramInfoLog`
- `gl.getShaderInfoLog`
- `programInfoLog.trim`
- `vertexShaderInfoLog.trim`
- `fragmentShaderInfoLog.trim`
- `gl.getProgramParameter`
- `renderer.debug.onShaderError`
- `getShaderErrors`
- `console.error`
- `gl.getError`
- `console.warn`
- `gl.deleteShader`
- `fetchAttributeLocations`

**Internal Comments:**
```
// check for link errors
// default error reporting (x2)
// Clean up (x4)
// Crashes in iOS9 and iOS10. #18402 (x4)
// gl.detachShader( program, glVertexShader ); (x4)
// gl.detachShader( program, glFragmentShader ); (x4)
```

<details><summary>Code</summary>

```typescript
function onFirstUse( self ) {

		// check for link errors
		if ( renderer.debug.checkShaderErrors ) {

			const programInfoLog = gl.getProgramInfoLog( program ) || '';
			const vertexShaderInfoLog = gl.getShaderInfoLog( glVertexShader ) || '';
			const fragmentShaderInfoLog = gl.getShaderInfoLog( glFragmentShader ) || '';

			const programLog = programInfoLog.trim();
			const vertexLog = vertexShaderInfoLog.trim();
			const fragmentLog = fragmentShaderInfoLog.trim();

			let runnable = true;
			let haveDiagnostics = true;

			if ( gl.getProgramParameter( program, gl.LINK_STATUS ) === false ) {

				runnable = false;

				if ( typeof renderer.debug.onShaderError === 'function' ) {

					renderer.debug.onShaderError( gl, program, glVertexShader, glFragmentShader );

				} else {

					// default error reporting

					const vertexErrors = getShaderErrors( gl, glVertexShader, 'vertex' );
					const fragmentErrors = getShaderErrors( gl, glFragmentShader, 'fragment' );

					console.error(
						'THREE.WebGLProgram: Shader Error ' + gl.getError() + ' - ' +
						'VALIDATE_STATUS ' + gl.getProgramParameter( program, gl.VALIDATE_STATUS ) + '\n\n' +
						'Material Name: ' + self.name + '\n' +
						'Material Type: ' + self.type + '\n\n' +
						'Program Info Log: ' + programLog + '\n' +
						vertexErrors + '\n' +
						fragmentErrors
					);

				}

			} else if ( programLog !== '' ) {

				console.warn( 'THREE.WebGLProgram: Program Info Log:', programLog );

			} else if ( vertexLog === '' || fragmentLog === '' ) {

				haveDiagnostics = false;

			}

			if ( haveDiagnostics ) {

				self.diagnostics = {

					runnable: runnable,

					programLog: programLog,

					vertexShader: {

						log: vertexLog,
						prefix: prefixVertex

					},

					fragmentShader: {

						log: fragmentLog,
						prefix: prefixFragment

					}

				};

			}

		}

		// Clean up

		// Crashes in iOS9 and iOS10. #18402
		// gl.detachShader( program, glVertexShader );
		// gl.detachShader( program, glFragmentShader );

		gl.deleteShader( glVertexShader );
		gl.deleteShader( glFragmentShader );

		cachedUniforms = new WebGLUniforms( gl, program );
		cachedAttributes = fetchAttributeLocations( gl, program );

	}
```
</details>


---