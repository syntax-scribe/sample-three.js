[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TextureHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 6 |
| 🧱 Classes | 1 |
| 📦 Imports | 8 |
| 📊 Variables & Constants | 16 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/helpers/TextureHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BoxGeometry` | `three` |
| `BufferAttribute` | `three` |
| `DoubleSide` | `three` |
| `Mesh` | `three` |
| `PlaneGeometry` | `three` |
| `ShaderMaterial` | `three` |
| `Vector3` | `three` |
| `mergeGeometries` | `../utils/BufferGeometryUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `material` | `any` | let/var | `new ShaderMaterial( { type: 'TextureHelperMaterial', side: DoubleSide, transp...` | ✗ |
| `geometry` | `any` | let/var | `texture.isCubeTexture ? createCubeGeometry( width, height, depth ) : createSl...` | ✗ |
| `geometry` | `any` | let/var | `new BoxGeometry( width, height, depth )` | ✗ |
| `position` | `any` | let/var | `geometry.attributes.position` | ✗ |
| `uv` | `any` | let/var | `geometry.attributes.uv` | ✗ |
| `uvw` | `any` | let/var | `new BufferAttribute( new Float32Array( uv.count * 3 ), 3 )` | ✗ |
| `_direction` | `any` | let/var | `new Vector3()` | ✗ |
| `u` | `any` | let/var | `_direction.x` | ✗ |
| `v` | `any` | let/var | `_direction.y` | ✗ |
| `w` | `any` | let/var | `_direction.z` | ✗ |
| `geometries` | `any[]` | let/var | `[]` | ✗ |
| `geometry` | `any` | let/var | `new PlaneGeometry( width, height )` | ✗ |
| `uv` | `any` | let/var | `geometry.attributes.uv` | ✗ |
| `uvw` | `any` | let/var | `new BufferAttribute( new Float32Array( uv.count * 3 ), 3 )` | ✗ |
| `v` | `any` | let/var | `texture.flipY ? uv.getY( j ) : 1 - uv.getY( j )` | ✗ |
| `w` | `number` | let/var | `sliceCount === 1 ? 1 : texture.isDataArrayTexture \|\| texture.isCompressedAr...` | ✗ |


---

## Functions

### `TextureHelper.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.geometry.dispose`
- `this.material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}
```
</details>

### `getSamplerType(texture: any): "samplerCube" | "sampler2DArray" | "sampler3D" | "sampler2D"`

**Parameters:**

- **`texture`** `any`

**Returns:** `"samplerCube" | "sampler2DArray" | "sampler3D" | "sampler2D"`

<details><summary>Code</summary>

```typescript
function getSamplerType( texture ) {

	if ( texture.isCubeTexture ) {

		return 'samplerCube';

	} else if ( texture.isDataArrayTexture || texture.isCompressedArrayTexture ) {

		return 'sampler2DArray';

	} else if ( texture.isData3DTexture || texture.isCompressed3DTexture ) {

		return 'sampler3D';

	} else {

		return 'sampler2D';

	}

}
```
</details>

### `getImageCount(texture: any): any`

**Parameters:**

- **`texture`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getImageCount( texture ) {

	if ( texture.isCubeTexture ) {

		return 6;

	} else if ( texture.isDataArrayTexture || texture.isCompressedArrayTexture ) {

		return texture.image.depth;

	} else if ( texture.isData3DTexture || texture.isCompressed3DTexture ) {

		return texture.image.depth;

	} else {

		return 1;

	}

}
```
</details>

### `getAlpha(texture: any): number`

**Parameters:**

- **`texture`** `any`

**Returns:** `number`

**Calls:**

- `Math.max`

<details><summary>Code</summary>

```typescript
function getAlpha( texture ) {

	if ( texture.isCubeTexture ) {

		return 1;

	} else if ( texture.isDataArrayTexture || texture.isCompressedArrayTexture ) {

		return Math.max( 1 / texture.image.depth, 0.25 );

	} else if ( texture.isData3DTexture || texture.isCompressed3DTexture ) {

		return Math.max( 1 / texture.image.depth, 0.25 );

	} else {

		return 1;

	}

}
```
</details>

### `createCubeGeometry(width: any, height: any, depth: any): any`

**Parameters:**

- **`width`** `any`
- **`height`** `any`
- **`depth`** `any`

**Returns:** `any`

**Calls:**

- `_direction.fromBufferAttribute( position, j ).normalize`
- `uvw.setXYZ`
- `geometry.deleteAttribute`
- `geometry.setAttribute`

<details><summary>Code</summary>

```typescript
function createCubeGeometry( width, height, depth ) {

	const geometry = new BoxGeometry( width, height, depth );

	const position = geometry.attributes.position;
	const uv = geometry.attributes.uv;
	const uvw = new BufferAttribute( new Float32Array( uv.count * 3 ), 3 );

	const _direction = new Vector3();

	for ( let j = 0, jl = uv.count; j < jl; ++ j ) {

		_direction.fromBufferAttribute( position, j ).normalize();

		const u = _direction.x;
		const v = _direction.y;
		const w = _direction.z;

		uvw.setXYZ( j, u, v, w );

	}

	geometry.deleteAttribute( 'uv' );
	geometry.setAttribute( 'uvw', uvw );

	return geometry;

}
```
</details>

### `createSliceGeometry(texture: any, width: any, height: any, depth: any): BufferGeometry`

**Parameters:**

- **`texture`** `any`
- **`width`** `any`
- **`height`** `any`
- **`depth`** `any`

**Returns:** `BufferGeometry`

**Calls:**

- `getImageCount`
- `geometry.translate`
- `uv.getX`
- `uv.getY`
- `uvw.setXYZ`
- `geometry.deleteAttribute`
- `geometry.setAttribute`
- `geometries.push`
- `mergeGeometries (from ../utils/BufferGeometryUtils.js)`

<details><summary>Code</summary>

```typescript
function createSliceGeometry( texture, width, height, depth ) {

	const sliceCount = getImageCount( texture );

	const geometries = [];

	for ( let i = 0; i < sliceCount; ++ i ) {

		const geometry = new PlaneGeometry( width, height );

		if ( sliceCount > 1 ) {

			geometry.translate( 0, 0, depth * ( i / ( sliceCount - 1 ) - 0.5 ) );

		}

		const uv = geometry.attributes.uv;
		const uvw = new BufferAttribute( new Float32Array( uv.count * 3 ), 3 );

		for ( let j = 0, jl = uv.count; j < jl; ++ j ) {

			const u = uv.getX( j );
			const v = texture.flipY ? uv.getY( j ) : 1 - uv.getY( j );
			const w = sliceCount === 1
				? 1
				: texture.isDataArrayTexture || texture.isCompressedArrayTexture
					? i
					: i / ( sliceCount - 1 );

			uvw.setXYZ( j, u, v, w );

		}

		geometry.deleteAttribute( 'uv' );
		geometry.setAttribute( 'uvw', uvw );

		geometries.push( geometry );

	}

	return mergeGeometries( geometries );

}
```
</details>


---

## Classes

### `TextureHelper`

<details><summary>Class Code</summary>

```ts
class TextureHelper extends Mesh {

	/**
	 * Constructs a new texture helper.
	 *
	 * @param {Texture} texture - The texture to visualize.
	 * @param {number} [width=1] - The helper's width.
	 * @param {number} [height=1] - The helper's height.
	 * @param {number} [depth=1] - The helper's depth.
	 */
	constructor( texture, width = 1, height = 1, depth = 1 ) {

		const material = new ShaderMaterial( {

			type: 'TextureHelperMaterial',

			side: DoubleSide,
			transparent: true,

			uniforms: {

				map: { value: texture },
				alpha: { value: getAlpha( texture ) },

			},

			vertexShader: [

				'attribute vec3 uvw;',

				'varying vec3 vUvw;',

				'void main() {',

				'	vUvw = uvw;',

				'	gl_Position = projectionMatrix * modelViewMatrix * vec4( position, 1.0 );',

				'}',

			].join( '\n' ),

			fragmentShader: [

				'precision highp float;',

				'precision highp sampler2DArray;',

				'precision highp sampler3D;',

				'uniform {samplerType} map;',

				'uniform float alpha;',

				'varying vec3 vUvw;',

				'vec4 textureHelper( in sampler2D map ) { return texture( map, vUvw.xy ); }',

				'vec4 textureHelper( in sampler2DArray map ) { return texture( map, vUvw ); }',

				'vec4 textureHelper( in sampler3D map ) { return texture( map, vUvw ); }',

				'vec4 textureHelper( in samplerCube map ) { return texture( map, vUvw ); }',

				'void main() {',

				'	gl_FragColor = linearToOutputTexel( vec4( textureHelper( map ).xyz, alpha ) );',

				'}'

			].join( '\n' ).replace( '{samplerType}', getSamplerType( texture ) )

		} );

		const geometry = texture.isCubeTexture
			? createCubeGeometry( width, height, depth )
			: createSliceGeometry( texture, width, height, depth );

		super( geometry, material );

		/**
		 * The texture to visualize.
		 *
		 * @type {Texture}
		 */
		this.texture = texture;
		this.type = 'TextureHelper';

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}

}
```
</details>

#### Methods

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}
```
</details>


---