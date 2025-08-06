[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `CubeRenderTarget.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 13 |
| 📊 Variables & Constants | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/CubeRenderTarget.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `equirectUV` | `../../nodes/utils/EquirectUV.js` |
| `TSL_Texture` | `../../nodes/accessors/TextureNode.js` |
| `positionWorldDirection` | `../../nodes/accessors/Position.js` |
| `NodeMaterial` | `../../materials/nodes/NodeMaterial.js` |
| `WebGLCubeRenderTarget` | `../../renderers/WebGLCubeRenderTarget.js` |
| `Scene` | `../../scenes/Scene.js` |
| `CubeCamera` | `../../cameras/CubeCamera.js` |
| `BoxGeometry` | `../../geometries/BoxGeometry.js` |
| `Mesh` | `../../objects/Mesh.js` |
| `BackSide` | `../../constants.js` |
| `NoBlending` | `../../constants.js` |
| `LinearFilter` | `../../constants.js` |
| `LinearMipmapLinearFilter` | `../../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `currentMinFilter` | `any` | let/var | `texture.minFilter` | ✗ |
| `currentGenerateMipmaps` | `any` | let/var | `texture.generateMipmaps` | ✗ |
| `geometry` | `BoxGeometry` | let/var | `new BoxGeometry( 5, 5, 5 )` | ✗ |
| `material` | `NodeMaterial` | let/var | `new NodeMaterial()` | ✗ |
| `mesh` | `Mesh` | let/var | `new Mesh( geometry, material )` | ✗ |
| `scene` | `Scene` | let/var | `new Scene()` | ✗ |
| `camera` | `CubeCamera` | let/var | `new CubeCamera( 1, 10, this )` | ✗ |


---

## Functions

### `CubeRenderTarget.fromEquirectangularTexture(renderer: Renderer, texture: Texture): CubeRenderTarget`

**JSDoc:**
```typescript
/**
	 * Converts the given equirectangular texture to a cube map.
	 *
	 * @param {Renderer} renderer - The renderer.
	 * @param {Texture} texture - The equirectangular texture.
	 * @return {CubeRenderTarget} A reference to this cube render target.
	 */
```

**Parameters:**

- **`renderer`** `Renderer`
- **`texture`** `Texture`

**Returns:** `CubeRenderTarget`

**Calls:**

- `equirectUV (from ../../nodes/utils/EquirectUV.js)`
- `TSL_Texture (from ../../nodes/accessors/TextureNode.js)`
- `scene.add`
- `renderer.getMRT`
- `renderer.setMRT`
- `camera.update`
- `mesh.geometry.dispose`
- `mesh.material.dispose`

**Internal Comments:**
```
// Avoid blurred poles
```

<details><summary>Code</summary>

```typescript
fromEquirectangularTexture( renderer, texture ) {

		const currentMinFilter = texture.minFilter;
		const currentGenerateMipmaps = texture.generateMipmaps;

		texture.generateMipmaps = true;

		this.texture.type = texture.type;
		this.texture.colorSpace = texture.colorSpace;

		this.texture.generateMipmaps = texture.generateMipmaps;
		this.texture.minFilter = texture.minFilter;
		this.texture.magFilter = texture.magFilter;

		const geometry = new BoxGeometry( 5, 5, 5 );

		const uvNode = equirectUV( positionWorldDirection );

		const material = new NodeMaterial();
		material.colorNode = TSL_Texture( texture, uvNode, 0 );
		material.side = BackSide;
		material.blending = NoBlending;

		const mesh = new Mesh( geometry, material );

		const scene = new Scene();
		scene.add( mesh );

		// Avoid blurred poles
		if ( texture.minFilter === LinearMipmapLinearFilter ) texture.minFilter = LinearFilter;

		const camera = new CubeCamera( 1, 10, this );

		const currentMRT = renderer.getMRT();
		renderer.setMRT( null );

		camera.update( renderer, scene );

		renderer.setMRT( currentMRT );

		texture.minFilter = currentMinFilter;
		texture.currentGenerateMipmaps = currentGenerateMipmaps;

		mesh.geometry.dispose();
		mesh.material.dispose();

		return this;

	}
```
</details>


---

## Classes

### `CubeRenderTarget`

<details><summary>Class Code</summary>

```ts
class CubeRenderTarget extends WebGLCubeRenderTarget {

	/**
	 * Constructs a new cube render target.
	 *
	 * @param {number} [size=1] - The size of the render target.
	 * @param {RenderTarget~Options} [options] - The configuration object.
	 */
	constructor( size = 1, options = {} ) {

		super( size, options );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isCubeRenderTarget = true;

	}

	/**
	 * Converts the given equirectangular texture to a cube map.
	 *
	 * @param {Renderer} renderer - The renderer.
	 * @param {Texture} texture - The equirectangular texture.
	 * @return {CubeRenderTarget} A reference to this cube render target.
	 */
	fromEquirectangularTexture( renderer, texture ) {

		const currentMinFilter = texture.minFilter;
		const currentGenerateMipmaps = texture.generateMipmaps;

		texture.generateMipmaps = true;

		this.texture.type = texture.type;
		this.texture.colorSpace = texture.colorSpace;

		this.texture.generateMipmaps = texture.generateMipmaps;
		this.texture.minFilter = texture.minFilter;
		this.texture.magFilter = texture.magFilter;

		const geometry = new BoxGeometry( 5, 5, 5 );

		const uvNode = equirectUV( positionWorldDirection );

		const material = new NodeMaterial();
		material.colorNode = TSL_Texture( texture, uvNode, 0 );
		material.side = BackSide;
		material.blending = NoBlending;

		const mesh = new Mesh( geometry, material );

		const scene = new Scene();
		scene.add( mesh );

		// Avoid blurred poles
		if ( texture.minFilter === LinearMipmapLinearFilter ) texture.minFilter = LinearFilter;

		const camera = new CubeCamera( 1, 10, this );

		const currentMRT = renderer.getMRT();
		renderer.setMRT( null );

		camera.update( renderer, scene );

		renderer.setMRT( currentMRT );

		texture.minFilter = currentMinFilter;
		texture.currentGenerateMipmaps = currentGenerateMipmaps;

		mesh.geometry.dispose();
		mesh.material.dispose();

		return this;

	}

}
```
</details>

#### Methods

##### `fromEquirectangularTexture(renderer: Renderer, texture: Texture): CubeRenderTarget`

<details><summary>Code</summary>

```ts
fromEquirectangularTexture( renderer, texture ) {

		const currentMinFilter = texture.minFilter;
		const currentGenerateMipmaps = texture.generateMipmaps;

		texture.generateMipmaps = true;

		this.texture.type = texture.type;
		this.texture.colorSpace = texture.colorSpace;

		this.texture.generateMipmaps = texture.generateMipmaps;
		this.texture.minFilter = texture.minFilter;
		this.texture.magFilter = texture.magFilter;

		const geometry = new BoxGeometry( 5, 5, 5 );

		const uvNode = equirectUV( positionWorldDirection );

		const material = new NodeMaterial();
		material.colorNode = TSL_Texture( texture, uvNode, 0 );
		material.side = BackSide;
		material.blending = NoBlending;

		const mesh = new Mesh( geometry, material );

		const scene = new Scene();
		scene.add( mesh );

		// Avoid blurred poles
		if ( texture.minFilter === LinearMipmapLinearFilter ) texture.minFilter = LinearFilter;

		const camera = new CubeCamera( 1, 10, this );

		const currentMRT = renderer.getMRT();
		renderer.setMRT( null );

		camera.update( renderer, scene );

		renderer.setMRT( currentMRT );

		texture.minFilter = currentMinFilter;
		texture.currentGenerateMipmaps = currentGenerateMipmaps;

		mesh.geometry.dispose();
		mesh.material.dispose();

		return this;

	}
```
</details>


---