[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `TextureHelperGPU.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 14 |
| 📊 Variables & Constants | 17 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/helpers/TextureHelperGPU.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `NodeMaterial` | `three` |
| `BoxGeometry` | `three` |
| `BufferAttribute` | `three` |
| `Mesh` | `three` |
| `PlaneGeometry` | `three` |
| `DoubleSide` | `three` |
| `Vector3` | `three` |
| `textureNode` | `three/tsl` |
| `cubeTexture` | `three/tsl` |
| `texture3D` | `three/tsl` |
| `float` | `three/tsl` |
| `vec4` | `three/tsl` |
| `attribute` | `three/tsl` |
| `mergeGeometries` | `../utils/BufferGeometryUtils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `material` | `any` | let/var | `new NodeMaterial()` | ✗ |
| `colorNode` | `any` | let/var | `*not shown*` | ✗ |
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
| `w` | `number` | let/var | `sliceCount === 1 ? 1 : texture.isArrayTexture \|\| texture.isDataArrayTexture...` | ✗ |


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

### `getImageCount(texture: any): any`

**Parameters:**

- **`texture`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function getImageCount( texture ) {

	if ( texture.isCubeTexture ) {

		return 6;

	} else if ( texture.isArrayTexture || texture.isDataArrayTexture || texture.isCompressedArrayTexture ) {

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

	} else if ( texture.isArrayTexture || texture.isDataArrayTexture || texture.isCompressedArrayTexture ) {

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
				: texture.isArrayTexture || texture.isDataArrayTexture || texture.isCompressedArrayTexture
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

		const material = new NodeMaterial();
		material.side = DoubleSide;
		material.transparent = true;
		material.name = 'TextureHelper';

		let colorNode;

		const uvw = attribute( 'uvw' );

		if ( texture.isCubeTexture ) {

			colorNode = cubeTexture( texture ).sample( uvw );

		} else if ( texture.isData3DTexture || texture.isCompressed3DTexture ) {

			colorNode = texture3D( texture ).sample( uvw );

		} else if ( texture.isArrayTexture || texture.isDataArrayTexture || texture.isCompressedArrayTexture ) {

			colorNode = textureNode( texture ).sample( uvw.xy ).depth( uvw.z );

		} else {

			colorNode = textureNode( texture );

		}

		const alphaNode = float( getAlpha( texture ) );

		material.colorNode = vec4( colorNode.rgb, alphaNode );

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