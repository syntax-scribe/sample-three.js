[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebGPUTextureUtils.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 5 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/utils/WebGPUTextureUtils.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `QuadMesh` | `three` |
| `NodeMaterial` | `three` |
| `WebGPURenderer` | `three` |
| `CanvasTexture` | `three` |
| `texture` | `three/tsl` |
| `uv` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_renderer` | `any` | let/var | `*not shown*` | ✗ |
| `_quadMesh` | `any` | let/var | `new QuadMesh()` | ✗ |
| `material` | `any` | let/var | `new NodeMaterial()` | ✗ |
| `currentOutputColorSpace` | `any` | let/var | `renderer.outputColorSpace` | ✗ |
| `readableTexture` | `any` | let/var | `new CanvasTexture( canvas )` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| async-function | `decompress` | renderer.init() | *none* |


---

## Functions

### `decompress(blitTexture: CompressedTexture, maxTextureSize: number, renderer: WebGPURenderer): Promise<CanvasTexture>`

**JSDoc:**
```typescript
/**
 * Returns an uncompressed version of the given compressed texture.
 *
 * This module can only be used with {@link WebGPURenderer}. When using {@link WebGLRenderer},
 * import the function from {@link WebGLTextureUtils}.
 *
 * @async
 * @param {CompressedTexture} blitTexture - The compressed texture.
 * @param {number} [maxTextureSize=Infinity] - The maximum size of the uncompressed texture.
 * @param {?WebGPURenderer} [renderer=null] - A reference to a renderer.
 * @return {Promise<CanvasTexture>} A Promise that resolved with the uncompressed texture.
 */
```

**Parameters:**

- **`blitTexture`** `CompressedTexture`
- **`maxTextureSize`** `number`
- **`renderer`** `WebGPURenderer`

**Returns:** `Promise<CanvasTexture>`

**Calls:**

- `renderer.init`
- `texture (from three/tsl)`
- `uv().flipY`
- `Math.min`
- `renderer.setSize`
- `_quadMesh.render`
- `document.createElement`
- `canvas.getContext`
- `context.drawImage`
- `_renderer.dispose`

<details><summary>Code</summary>

```typescript
export async function decompress( blitTexture, maxTextureSize = Infinity, renderer = null ) {

	if ( renderer === null ) {

		renderer = _renderer = new WebGPURenderer();
		await renderer.init();

	}

	const material = new NodeMaterial();

	material.fragmentNode = texture( blitTexture, uv().flipY() );

	const width = Math.min( blitTexture.image.width, maxTextureSize );
	const height = Math.min( blitTexture.image.height, maxTextureSize );

	const currentOutputColorSpace = renderer.outputColorSpace;

	renderer.setSize( width, height );
	renderer.outputColorSpace = blitTexture.colorSpace;

	_quadMesh.material = material;
	_quadMesh.render( renderer );

	renderer.outputColorSpace = currentOutputColorSpace;

	const canvas = document.createElement( 'canvas' );
	const context = canvas.getContext( '2d' );

	canvas.width = width;
	canvas.height = height;

	context.drawImage( renderer.domElement, 0, 0, width, height );

	const readableTexture = new CanvasTexture( canvas );

	readableTexture.minFilter = blitTexture.minFilter;
	readableTexture.magFilter = blitTexture.magFilter;
	readableTexture.wrapS = blitTexture.wrapS;
	readableTexture.wrapT = blitTexture.wrapT;
	readableTexture.colorSpace = blitTexture.colorSpace;
	readableTexture.name = blitTexture.name;

	if ( _renderer !== null ) {

		_renderer.dispose();
		_renderer = null;

	}

	return readableTexture;

}
```
</details>


---