[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGLMorphtargets.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 24 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/renderers/webgl/WebGLMorphtargets.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `FloatType` | `../../constants.js` |
| `DataArrayTexture` | `../../textures/DataArrayTexture.js` |
| `Vector4` | `../../math/Vector4.js` |
| `Vector2` | `../../math/Vector2.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `morphTextures` | `WeakMap<WeakKey, any>` | let/var | `new WeakMap()` | ✗ |
| `morph` | `Vector4` | let/var | `new Vector4()` | ✗ |
| `objectInfluences` | `any` | let/var | `object.morphTargetInfluences` | ✗ |
| `morphAttribute` | `any` | let/var | `geometry.morphAttributes.position \|\| geometry.morphAttributes.normal \|\| g...` | ✗ |
| `morphTargetsCount` | `any` | let/var | `( morphAttribute !== undefined ) ? morphAttribute.length : 0` | ✗ |
| `hasMorphPosition` | `boolean` | let/var | `geometry.morphAttributes.position !== undefined` | ✗ |
| `hasMorphNormals` | `boolean` | let/var | `geometry.morphAttributes.normal !== undefined` | ✗ |
| `hasMorphColors` | `boolean` | let/var | `geometry.morphAttributes.color !== undefined` | ✗ |
| `morphTargets` | `any` | let/var | `geometry.morphAttributes.position \|\| []` | ✗ |
| `morphNormals` | `any` | let/var | `geometry.morphAttributes.normal \|\| []` | ✗ |
| `morphColors` | `any` | let/var | `geometry.morphAttributes.color \|\| []` | ✗ |
| `vertexDataCount` | `number` | let/var | `0` | ✗ |
| `width` | `number` | let/var | `geometry.attributes.position.count * vertexDataCount` | ✗ |
| `height` | `number` | let/var | `1` | ✗ |
| `buffer` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( width * height * 4 * morphTargetsCount )` | ✗ |
| `texture` | `DataArrayTexture` | let/var | `new DataArrayTexture( buffer, width, height, morphTargetsCount )` | ✗ |
| `vertexDataStride` | `number` | let/var | `vertexDataCount * 4` | ✗ |
| `morphTarget` | `any` | let/var | `morphTargets[ i ]` | ✗ |
| `morphNormal` | `any` | let/var | `morphNormals[ i ]` | ✗ |
| `morphColor` | `any` | let/var | `morphColors[ i ]` | ✗ |
| `offset` | `number` | let/var | `width * height * 4 * i` | ✗ |
| `stride` | `number` | let/var | `j * vertexDataStride` | ✗ |
| `morphInfluencesSum` | `number` | let/var | `0` | ✗ |
| `morphBaseInfluence` | `number` | let/var | `geometry.morphTargetsRelative ? 1 : 1 - morphInfluencesSum` | ✗ |


---

## Functions

### `WebGLMorphtargets(gl: any, capabilities: any, textures: any): { update: (object: any, geometry: any, program: any) => void; }`

**Parameters:**

- **`gl`** `any`
- **`capabilities`** `any`
- **`textures`** `any`

**Returns:** `{ update: (object: any, geometry: any, program: any) => void; }`

**Calls:**

- `morphTextures.get`
- `entry.texture.dispose`
- `Math.ceil`
- `morph.fromBufferAttribute`
- `morphTextures.set`
- `texture.dispose`
- `morphTextures.delete`
- `geometry.removeEventListener`
- `geometry.addEventListener`
- `program.getUniforms().setValue`

**Internal Comments:**
```
// the following encodes morph targets into an array of data textures. Each layer represents a single morph target. (x2)
// fill buffer (x2)
//
```

<details><summary>Code</summary>

```typescript
function WebGLMorphtargets( gl, capabilities, textures ) {

	const morphTextures = new WeakMap();
	const morph = new Vector4();

	function update( object, geometry, program ) {

		const objectInfluences = object.morphTargetInfluences;

		// the following encodes morph targets into an array of data textures. Each layer represents a single morph target.

		const morphAttribute = geometry.morphAttributes.position || geometry.morphAttributes.normal || geometry.morphAttributes.color;
		const morphTargetsCount = ( morphAttribute !== undefined ) ? morphAttribute.length : 0;

		let entry = morphTextures.get( geometry );

		if ( entry === undefined || entry.count !== morphTargetsCount ) {

			if ( entry !== undefined ) entry.texture.dispose();

			const hasMorphPosition = geometry.morphAttributes.position !== undefined;
			const hasMorphNormals = geometry.morphAttributes.normal !== undefined;
			const hasMorphColors = geometry.morphAttributes.color !== undefined;

			const morphTargets = geometry.morphAttributes.position || [];
			const morphNormals = geometry.morphAttributes.normal || [];
			const morphColors = geometry.morphAttributes.color || [];

			let vertexDataCount = 0;

			if ( hasMorphPosition === true ) vertexDataCount = 1;
			if ( hasMorphNormals === true ) vertexDataCount = 2;
			if ( hasMorphColors === true ) vertexDataCount = 3;

			let width = geometry.attributes.position.count * vertexDataCount;
			let height = 1;

			if ( width > capabilities.maxTextureSize ) {

				height = Math.ceil( width / capabilities.maxTextureSize );
				width = capabilities.maxTextureSize;

			}

			const buffer = new Float32Array( width * height * 4 * morphTargetsCount );

			const texture = new DataArrayTexture( buffer, width, height, morphTargetsCount );
			texture.type = FloatType;
			texture.needsUpdate = true;

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

						morph.fromBufferAttribute( morphTarget, j );

						buffer[ offset + stride + 0 ] = morph.x;
						buffer[ offset + stride + 1 ] = morph.y;
						buffer[ offset + stride + 2 ] = morph.z;
						buffer[ offset + stride + 3 ] = 0;

					}

					if ( hasMorphNormals === true ) {

						morph.fromBufferAttribute( morphNormal, j );

						buffer[ offset + stride + 4 ] = morph.x;
						buffer[ offset + stride + 5 ] = morph.y;
						buffer[ offset + stride + 6 ] = morph.z;
						buffer[ offset + stride + 7 ] = 0;

					}

					if ( hasMorphColors === true ) {

						morph.fromBufferAttribute( morphColor, j );

						buffer[ offset + stride + 8 ] = morph.x;
						buffer[ offset + stride + 9 ] = morph.y;
						buffer[ offset + stride + 10 ] = morph.z;
						buffer[ offset + stride + 11 ] = ( morphColor.itemSize === 4 ) ? morph.w : 1;

					}

				}

			}

			entry = {
				count: morphTargetsCount,
				texture: texture,
				size: new Vector2( width, height )
			};

			morphTextures.set( geometry, entry );

			function disposeTexture() {

				texture.dispose();

				morphTextures.delete( geometry );

				geometry.removeEventListener( 'dispose', disposeTexture );

			}

			geometry.addEventListener( 'dispose', disposeTexture );

		}

		//
		if ( object.isInstancedMesh === true && object.morphTexture !== null ) {

			program.getUniforms().setValue( gl, 'morphTexture', object.morphTexture, textures );

		} else {

			let morphInfluencesSum = 0;

			for ( let i = 0; i < objectInfluences.length; i ++ ) {

				morphInfluencesSum += objectInfluences[ i ];

			}

			const morphBaseInfluence = geometry.morphTargetsRelative ? 1 : 1 - morphInfluencesSum;


			program.getUniforms().setValue( gl, 'morphTargetBaseInfluence', morphBaseInfluence );
			program.getUniforms().setValue( gl, 'morphTargetInfluences', objectInfluences );

		}

		program.getUniforms().setValue( gl, 'morphTargetsTexture', entry.texture, textures );
		program.getUniforms().setValue( gl, 'morphTargetsTextureSize', entry.size );

	}

	return {

		update: update

	};

}
```
</details>

### `update(object: any, geometry: any, program: any): void`

**Parameters:**

- **`object`** `any`
- **`geometry`** `any`
- **`program`** `any`

**Returns:** `void`

**Calls:**

- `morphTextures.get`
- `entry.texture.dispose`
- `Math.ceil`
- `morph.fromBufferAttribute`
- `morphTextures.set`
- `texture.dispose`
- `morphTextures.delete`
- `geometry.removeEventListener`
- `geometry.addEventListener`
- `program.getUniforms().setValue`

**Internal Comments:**
```
// the following encodes morph targets into an array of data textures. Each layer represents a single morph target. (x2)
// fill buffer (x2)
//
```

<details><summary>Code</summary>

```typescript
function update( object, geometry, program ) {

		const objectInfluences = object.morphTargetInfluences;

		// the following encodes morph targets into an array of data textures. Each layer represents a single morph target.

		const morphAttribute = geometry.morphAttributes.position || geometry.morphAttributes.normal || geometry.morphAttributes.color;
		const morphTargetsCount = ( morphAttribute !== undefined ) ? morphAttribute.length : 0;

		let entry = morphTextures.get( geometry );

		if ( entry === undefined || entry.count !== morphTargetsCount ) {

			if ( entry !== undefined ) entry.texture.dispose();

			const hasMorphPosition = geometry.morphAttributes.position !== undefined;
			const hasMorphNormals = geometry.morphAttributes.normal !== undefined;
			const hasMorphColors = geometry.morphAttributes.color !== undefined;

			const morphTargets = geometry.morphAttributes.position || [];
			const morphNormals = geometry.morphAttributes.normal || [];
			const morphColors = geometry.morphAttributes.color || [];

			let vertexDataCount = 0;

			if ( hasMorphPosition === true ) vertexDataCount = 1;
			if ( hasMorphNormals === true ) vertexDataCount = 2;
			if ( hasMorphColors === true ) vertexDataCount = 3;

			let width = geometry.attributes.position.count * vertexDataCount;
			let height = 1;

			if ( width > capabilities.maxTextureSize ) {

				height = Math.ceil( width / capabilities.maxTextureSize );
				width = capabilities.maxTextureSize;

			}

			const buffer = new Float32Array( width * height * 4 * morphTargetsCount );

			const texture = new DataArrayTexture( buffer, width, height, morphTargetsCount );
			texture.type = FloatType;
			texture.needsUpdate = true;

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

						morph.fromBufferAttribute( morphTarget, j );

						buffer[ offset + stride + 0 ] = morph.x;
						buffer[ offset + stride + 1 ] = morph.y;
						buffer[ offset + stride + 2 ] = morph.z;
						buffer[ offset + stride + 3 ] = 0;

					}

					if ( hasMorphNormals === true ) {

						morph.fromBufferAttribute( morphNormal, j );

						buffer[ offset + stride + 4 ] = morph.x;
						buffer[ offset + stride + 5 ] = morph.y;
						buffer[ offset + stride + 6 ] = morph.z;
						buffer[ offset + stride + 7 ] = 0;

					}

					if ( hasMorphColors === true ) {

						morph.fromBufferAttribute( morphColor, j );

						buffer[ offset + stride + 8 ] = morph.x;
						buffer[ offset + stride + 9 ] = morph.y;
						buffer[ offset + stride + 10 ] = morph.z;
						buffer[ offset + stride + 11 ] = ( morphColor.itemSize === 4 ) ? morph.w : 1;

					}

				}

			}

			entry = {
				count: morphTargetsCount,
				texture: texture,
				size: new Vector2( width, height )
			};

			morphTextures.set( geometry, entry );

			function disposeTexture() {

				texture.dispose();

				morphTextures.delete( geometry );

				geometry.removeEventListener( 'dispose', disposeTexture );

			}

			geometry.addEventListener( 'dispose', disposeTexture );

		}

		//
		if ( object.isInstancedMesh === true && object.morphTexture !== null ) {

			program.getUniforms().setValue( gl, 'morphTexture', object.morphTexture, textures );

		} else {

			let morphInfluencesSum = 0;

			for ( let i = 0; i < objectInfluences.length; i ++ ) {

				morphInfluencesSum += objectInfluences[ i ];

			}

			const morphBaseInfluence = geometry.morphTargetsRelative ? 1 : 1 - morphInfluencesSum;


			program.getUniforms().setValue( gl, 'morphTargetBaseInfluence', morphBaseInfluence );
			program.getUniforms().setValue( gl, 'morphTargetInfluences', objectInfluences );

		}

		program.getUniforms().setValue( gl, 'morphTargetsTexture', entry.texture, textures );
		program.getUniforms().setValue( gl, 'morphTargetsTextureSize', entry.size );

	}
```
</details>

### `disposeTexture(): void`

**Returns:** `void`

**Calls:**

- `texture.dispose`
- `morphTextures.delete`
- `geometry.removeEventListener`

<details><summary>Code</summary>

```typescript
function disposeTexture() {

				texture.dispose();

				morphTextures.delete( geometry );

				geometry.removeEventListener( 'dispose', disposeTexture );

			}
```
</details>


---