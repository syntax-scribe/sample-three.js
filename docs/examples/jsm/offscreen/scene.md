[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `scene.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 📊 Variables & Constants | 11 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`examples/jsm/offscreen/scene.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `camera` | `any` | let/var | `*not shown*` | ✗ |
| `scene` | `any` | let/var | `*not shown*` | ✗ |
| `renderer` | `any` | let/var | `*not shown*` | ✗ |
| `group` | `any` | let/var | `*not shown*` | ✗ |
| `texture` | `CanvasTexture` | let/var | `new THREE.CanvasTexture( imageBitmap )` | ✗ |
| `geometry` | `IcosahedronGeometry` | let/var | `new THREE.IcosahedronGeometry( 5, 8 )` | ✗ |
| `materials` | `MeshMatcapMaterial[]` | let/var | `[ new THREE.MeshMatcapMaterial( { color: 0xaa24df, matcap: texture } ), new T...` | ✗ |
| `material` | `MeshMatcapMaterial` | let/var | `materials[ i % materials.length ]` | ✗ |
| `mesh` | `Mesh` | let/var | `new THREE.Mesh( geometry, material )` | ✗ |
| `seed` | `number` | let/var | `1` | ✗ |
| `x` | `number` | let/var | `Math.sin( seed ++ ) * 10000` | ✗ |


---

## Functions

### `init(canvas: any, width: any, height: any, pixelRatio: any, path: any): void`

**Parameters:**

- **`canvas`** `any`
- **`width`** `any`
- **`height`** `any`
- **`pixelRatio`** `any`
- **`path`** `any`

**Returns:** `void`

**Calls:**

- `scene.add`
- `new THREE.ImageBitmapLoader().setPath`
- `loader.setOptions`
- `loader.load`
- `random`
- `mesh.scale.setScalar`
- `group.add`
- `renderer.setPixelRatio`
- `renderer.setSize`
- `animate`

**Internal Comments:**
```
// we don't use ImageLoader since it has a DOM dependency (HTML5 image element) (x2)
```

<details><summary>Code</summary>

```typescript
function init( canvas, width, height, pixelRatio, path ) {

	camera = new THREE.PerspectiveCamera( 40, width / height, 1, 1000 );
	camera.position.z = 200;

	scene = new THREE.Scene();
	scene.fog = new THREE.Fog( 0x444466, 100, 400 );
	scene.background = new THREE.Color( 0x444466 );

	group = new THREE.Group();
	scene.add( group );

	// we don't use ImageLoader since it has a DOM dependency (HTML5 image element)

	const loader = new THREE.ImageBitmapLoader().setPath( path );
	loader.setOptions( { imageOrientation: 'flipY' } );
	loader.load( 'textures/matcaps/matcap-porcelain-white.jpg', function ( imageBitmap ) {

		const texture = new THREE.CanvasTexture( imageBitmap );

		const geometry = new THREE.IcosahedronGeometry( 5, 8 );
		const materials = [
			new THREE.MeshMatcapMaterial( { color: 0xaa24df, matcap: texture } ),
			new THREE.MeshMatcapMaterial( { color: 0x605d90, matcap: texture } ),
			new THREE.MeshMatcapMaterial( { color: 0xe04a3f, matcap: texture } ),
			new THREE.MeshMatcapMaterial( { color: 0xe30456, matcap: texture } )
		];

		for ( let i = 0; i < 100; i ++ ) {

			const material = materials[ i % materials.length ];
			const mesh = new THREE.Mesh( geometry, material );
			mesh.position.x = random() * 200 - 100;
			mesh.position.y = random() * 200 - 100;
			mesh.position.z = random() * 200 - 100;
			mesh.scale.setScalar( random() + 1 );
			group.add( mesh );

		}

		renderer = new THREE.WebGLRenderer( { antialias: true, canvas: canvas } );
		renderer.setPixelRatio( pixelRatio );
		renderer.setSize( width, height, false );

		animate();

	} );

}
```
</details>

### `animate(): void`

**Returns:** `void`

**Calls:**

- `Date.now`
- `renderer.render`
- `self.requestAnimationFrame`

**Internal Comments:**
```
// group.rotation.x = Date.now() / 4000; (x5)
```

<details><summary>Code</summary>

```typescript
function animate() {

	// group.rotation.x = Date.now() / 4000;
	group.rotation.y = - Date.now() / 4000;

	renderer.render( scene, camera );

	if ( self.requestAnimationFrame ) {

		self.requestAnimationFrame( animate );

	} else {

		// Firefox

	}

}
```
</details>

### `random(): number`

**Returns:** `number`

**Calls:**

- `Math.sin`
- `Math.floor`

<details><summary>Code</summary>

```typescript
function random() {

	const x = Math.sin( seed ++ ) * 10000;

	return x - Math.floor( x );

}
```
</details>


---