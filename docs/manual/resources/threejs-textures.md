[⬅️ Back to Table of Contents](../../index.md)

# 📄 `threejs-textures.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 34 |
| ⚡ Async/Await Patterns | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Async/Await Patterns](#asyncawait-patterns)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/resources/threejs-textures.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `threejsLessonUtils` | `./threejs-lesson-utils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `loader` | `any` | let/var | `new THREE.TextureLoader()` | ✗ |
| `textureResolve` | `any` | let/var | `*not shown*` | ✗ |
| `promise` | `Promise<any>` | let/var | `new Promise( ( resolve ) => { textureResolve = resolve; } )` | ✗ |
| `filterTexture` | `any` | let/var | `filterTextureInfo.texture` | ✗ |
| `filterTexturePromise` | `Promise<any>` | let/var | `filterTextureInfo.promise` | ✗ |
| `size` | `8` | let/var | `8` | ✗ |
| `geometry` | `any` | let/var | `new THREE.BoxGeometry( size, size, size )` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshBasicMaterial( { map: texture \|\| filterTexture, } )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( geometry, material )` | ✗ |
| `renderTarget` | `any` | let/var | `new THREE.WebGLRenderTarget( 1, 1, { magFilter: THREE.NearestFilter, minFilte...` | ✗ |
| `planeScene` | `any` | let/var | `new THREE.Scene()` | ✗ |
| `plane` | `any` | let/var | `new THREE.PlaneGeometry( 1, 1 )` | ✗ |
| `planeMaterial` | `any` | let/var | `new THREE.MeshBasicMaterial( { map: renderTarget.texture, } )` | ✗ |
| `planeMesh` | `any` | let/var | `new THREE.Mesh( plane, planeMaterial )` | ✗ |
| `planeCamera` | `any` | let/var | `new THREE.OrthographicCamera( 0, 1, 0, 1, - 1, 1 )` | ✗ |
| `viewWidth` | `number` | let/var | `width / pixelRatio / pixelSize` | ✗ |
| `viewHeight` | `number` | let/var | `height / pixelRatio / pixelSize` | ✗ |
| `u` | `number` | let/var | `level / numLevels` | ✗ |
| `size` | `number` | let/var | `2 ** ( numLevels - level - 1 )` | ✗ |
| `texture` | `any` | let/var | `await filterTexturePromise` | ✗ |
| `texture` | `any` | let/var | `await filterTexturePromise` | ✗ |
| `texture` | `any` | let/var | `await filterTexturePromise` | ✗ |
| `root` | `any` | let/var | `new THREE.Object3D()` | ✗ |
| `depth` | `50` | let/var | `50` | ✗ |
| `plane` | `any` | let/var | `new THREE.PlaneGeometry( 1, depth )` | ✗ |
| `mipmap` | `any[]` | let/var | `[]` | ✗ |
| `numMips` | `7` | let/var | `7` | ✗ |
| `mipTexture` | `any` | let/var | `new THREE.CanvasTexture( mipmap[ 0 ] )` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshBasicMaterial( { map: copyTexture, } )` | ✗ |
| `mesh` | `any` | let/var | `new THREE.Mesh( plane, material )` | ✗ |
| `numMips` | `7` | let/var | `7` | ✗ |
| `textureDiagrams` | `{ differentColoredMips(parent: any): ...` | let/var | `{ differentColoredMips( parent ) { const numMips = 7; for ( let i = 0; i < nu...` | ✗ |
| `name` | `any` | let/var | `elem.dataset.textureDiagram` | ✗ |
| `info` | `any` | let/var | `textureDiagrams[ name ]` | ✗ |


---

## Async/Await Patterns

| Type | Function | Await Expressions | Promise Chains |
|------|----------|-------------------|----------------|
| promise-chain | `loadTextureAndPromise` | *none* | new Promise(...) |


---

## Functions

### `loadTextureAndPromise(url: any): { texture: any; promise: Promise<any>; }`

**Parameters:**

- **`url`** `any`

**Returns:** `{ texture: any; promise: Promise<any>; }`

**Calls:**

- `loader.load`
- `textureResolve`

<details><summary>Code</summary>

```typescript
function loadTextureAndPromise( url ) {

		let textureResolve;
		const promise = new Promise( ( resolve ) => {

			textureResolve = resolve;

		} );
		const texture = loader.load( url, ( texture ) => {

			textureResolve( texture );

		} );
		return {
			texture,
			promise,
		};

	}
```
</details>

### `filterCube(scale: any, texture: any): any`

**Parameters:**

- **`scale`** `any`
- **`texture`** `any`

**Returns:** `any`

**Calls:**

- `mesh.scale.set`

<details><summary>Code</summary>

```typescript
function filterCube( scale, texture ) {

		const size = 8;
		const geometry = new THREE.BoxGeometry( size, size, size );
		const material = new THREE.MeshBasicMaterial( {
			map: texture || filterTexture,
		} );
		const mesh = new THREE.Mesh( geometry, material );
		mesh.scale.set( scale, scale, scale );
		return mesh;

	}
```
</details>

### `lowResCube(scale: any, pixelSize: number): { obj3D: any; update(time: any, renderInfo: any): void; render(renderInfo: any): void; }`

**Parameters:**

- **`scale`** `any`
- **`pixelSize`** `number`

**Returns:** `{ obj3D: any; update(time: any, renderInfo: any): void; render(renderInfo: any): void; }`

**Calls:**

- `filterCube`
- `planeScene.add`
- `Math.ceil`
- `renderTarget.setSize`
- `camera.updateProjectionMatrix`
- `renderer.setRenderTarget`
- `renderer.render`
- `planeCamera.updateProjectionMatrix`
- `planeMesh.scale.set`

**Internal Comments:**
```
// compute the difference between our renderTarget size (x5)
// and the view size. The renderTarget is a multiple pixels magnified pixels (x5)
// so for example if the view is 15 pixels wide and the magnified pixel size is 10 (x5)
// the renderTarget will be 20 pixels wide. We only want to display 15 of those 20 (x5)
// pixels so (x5)
```

<details><summary>Code</summary>

```typescript
function lowResCube( scale, pixelSize = 16 ) {

		const mesh = filterCube( scale );
		const renderTarget = new THREE.WebGLRenderTarget( 1, 1, {
			magFilter: THREE.NearestFilter,
			minFilter: THREE.NearestFilter,
		} );

		const planeScene = new THREE.Scene();

		const plane = new THREE.PlaneGeometry( 1, 1 );
		const planeMaterial = new THREE.MeshBasicMaterial( {
			map: renderTarget.texture,
		} );
		const planeMesh = new THREE.Mesh( plane, planeMaterial );
		planeScene.add( planeMesh );

		const planeCamera = new THREE.OrthographicCamera( 0, 1, 0, 1, - 1, 1 );
		planeCamera.position.z = 1;

		return {
			obj3D: mesh,
			update( time, renderInfo ) {

				const { width, height, scene, camera, renderer, pixelRatio } = renderInfo;
				const rtWidth = Math.ceil( width / pixelRatio / pixelSize );
				const rtHeight = Math.ceil( height / pixelRatio / pixelSize );
				renderTarget.setSize( rtWidth, rtHeight );

				camera.aspect = rtWidth / rtHeight;
				camera.updateProjectionMatrix();

				renderer.setRenderTarget( renderTarget );

				renderer.render( scene, camera );
				renderer.setRenderTarget( null );

			},
			render( renderInfo ) {

				const { width, height, renderer, pixelRatio } = renderInfo;
				const viewWidth = width / pixelRatio / pixelSize;
				const viewHeight = height / pixelRatio / pixelSize;
				planeCamera.left = - viewWidth / 2;
				planeCamera.right = viewWidth / 2;
				planeCamera.top = viewHeight / 2;
				planeCamera.bottom = - viewHeight / 2;
				planeCamera.updateProjectionMatrix();

				// compute the difference between our renderTarget size
				// and the view size. The renderTarget is a multiple pixels magnified pixels
				// so for example if the view is 15 pixels wide and the magnified pixel size is 10
				// the renderTarget will be 20 pixels wide. We only want to display 15 of those 20
				// pixels so

				planeMesh.scale.set( renderTarget.width, renderTarget.height, 1 );

				renderer.render( planeScene, planeCamera );

			},
		};

	}
```
</details>

### `createMip(level: any, numLevels: any, scale: any): HTMLCanvasElement`

**Parameters:**

- **`level`** `any`
- **`numLevels`** `any`
- **`scale`** `any`

**Returns:** `HTMLCanvasElement`

**Calls:**

- `Math.ceil`
- `document.createElement( 'canvas' ).getContext`
- `ctx.scale`
- `ctx.fillRect`

<details><summary>Code</summary>

```typescript
function createMip( level, numLevels, scale ) {

		const u = level / numLevels;
		const size = 2 ** ( numLevels - level - 1 );
		const halfSize = Math.ceil( size / 2 );
		const ctx = document.createElement( 'canvas' ).getContext( '2d' );
		ctx.canvas.width = size * scale;
		ctx.canvas.height = size * scale;
		ctx.scale( scale, scale );
		ctx.fillStyle = `hsl(${180 + u * 360 | 0},100%,20%)`;
		ctx.fillRect( 0, 0, size, size );
		ctx.fillStyle = `hsl(${u * 360 | 0},100%,50%)`;
		ctx.fillRect( 0, 0, halfSize, halfSize );
		ctx.fillRect( halfSize, halfSize, halfSize, halfSize );
		return ctx.canvas;

	}
```
</details>

### `createTextureDiagram(elem: any): void`

**Parameters:**

- **`elem`** `any`

**Returns:** `void`

**Calls:**

- `info`

<details><summary>Code</summary>

```typescript
function createTextureDiagram( elem ) {

		const name = elem.dataset.textureDiagram;
		const info = textureDiagrams[ name ];
		info( elem );

	}
```
</details>


---