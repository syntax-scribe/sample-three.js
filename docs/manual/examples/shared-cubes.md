[⬅️ Back to Table of Contents](../../index.md)

# 📄 `shared-cubes.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 📊 Variables & Constants | 24 |

## 📚 Table of Contents

- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`manual/examples/shared-cubes.js`**

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `state` | `{ width: number; height: number; }` | let/var | `{ width: 300, // canvas default height: 150, // canvas default }` | ✓ |
| `renderer` | `any` | let/var | `new THREE.WebGLRenderer( { antialias: true, canvas } )` | ✗ |
| `fov` | `75` | let/var | `75` | ✗ |
| `aspect` | `2` | let/var | `2` | ✗ |
| `near` | `0.1` | let/var | `0.1` | ✗ |
| `far` | `100` | let/var | `100` | ✗ |
| `camera` | `any` | let/var | `new THREE.PerspectiveCamera( fov, aspect, near, far )` | ✗ |
| `scene` | `any` | let/var | `new THREE.Scene()` | ✗ |
| `color` | `16777215` | let/var | `0xFFFFFF` | ✗ |
| `intensity` | `1` | let/var | `1` | ✗ |
| `light` | `any` | let/var | `new THREE.DirectionalLight( color, intensity )` | ✗ |
| `boxWidth` | `1` | let/var | `1` | ✗ |
| `boxHeight` | `1` | let/var | `1` | ✗ |
| `boxDepth` | `1` | let/var | `1` | ✗ |
| `geometry` | `any` | let/var | `new THREE.BoxGeometry( boxWidth, boxHeight, boxDepth )` | ✗ |
| `material` | `any` | let/var | `new THREE.MeshPhongMaterial( { color, } )` | ✗ |
| `cube` | `any` | let/var | `new THREE.Mesh( geometry, material )` | ✗ |
| `cubes` | `any[]` | let/var | `[ makeInstance( geometry, 0x44aa88, 0 ), makeInstance( geometry, 0x8844aa, - ...` | ✗ |
| `canvas` | `any` | let/var | `renderer.domElement` | ✗ |
| `width` | `number` | let/var | `state.width` | ✗ |
| `height` | `number` | let/var | `state.height` | ✗ |
| `needResize` | `boolean` | let/var | `canvas.width !== width \|\| canvas.height !== height` | ✗ |
| `speed` | `number` | let/var | `1 + ndx * .1` | ✗ |
| `rot` | `number` | let/var | `time * speed` | ✗ |


---

## Functions

### `init(data: any): void`

**Parameters:**

- **`data`** `any`

**Returns:** `void`

**Calls:**

- `light.position.set`
- `scene.add`
- `makeInstance`
- `renderer.setSize`
- `resizeRendererToDisplaySize`
- `camera.updateProjectionMatrix`
- `cubes.forEach`
- `renderer.render`
- `requestAnimationFrame`

<details><summary>Code</summary>

```typescript
export function init( data ) { /* eslint-disable-line no-unused-vars */

	const { canvas } = data;
	const renderer = new THREE.WebGLRenderer( { antialias: true, canvas } );

	state.width = canvas.width;
	state.height = canvas.height;

	const fov = 75;
	const aspect = 2; // the canvas default
	const near = 0.1;
	const far = 100;
	const camera = new THREE.PerspectiveCamera( fov, aspect, near, far );
	camera.position.z = 4;

	const scene = new THREE.Scene();

	{

		const color = 0xFFFFFF;
		const intensity = 1;
		const light = new THREE.DirectionalLight( color, intensity );
		light.position.set( - 1, 2, 4 );
		scene.add( light );

	}

	const boxWidth = 1;
	const boxHeight = 1;
	const boxDepth = 1;
	const geometry = new THREE.BoxGeometry( boxWidth, boxHeight, boxDepth );

	function makeInstance( geometry, color, x ) {

		const material = new THREE.MeshPhongMaterial( {
			color,
		} );

		const cube = new THREE.Mesh( geometry, material );
		scene.add( cube );

		cube.position.x = x;

		return cube;

	}

	const cubes = [
		makeInstance( geometry, 0x44aa88, 0 ),
		makeInstance( geometry, 0x8844aa, - 2 ),
		makeInstance( geometry, 0xaa8844, 2 ),
	];

	function resizeRendererToDisplaySize( renderer ) {

		const canvas = renderer.domElement;
		const width = state.width;
		const height = state.height;
		const needResize = canvas.width !== width || canvas.height !== height;
		if ( needResize ) {

			renderer.setSize( width, height, false );

		}

		return needResize;

	}

	function render( time ) {

		time *= 0.001;

		if ( resizeRendererToDisplaySize( renderer ) ) {

			camera.aspect = state.width / state.height;
			camera.updateProjectionMatrix();

		}

		cubes.forEach( ( cube, ndx ) => {

			const speed = 1 + ndx * .1;
			const rot = time * speed;
			cube.rotation.x = rot;
			cube.rotation.y = rot;

		} );

		renderer.render( scene, camera );

		requestAnimationFrame( render );

	}

	requestAnimationFrame( render );

}
```
</details>

### `makeInstance(geometry: any, color: any, x: any): any`

**Parameters:**

- **`geometry`** `any`
- **`color`** `any`
- **`x`** `any`

**Returns:** `any`

**Calls:**

- `scene.add`

<details><summary>Code</summary>

```typescript
function makeInstance( geometry, color, x ) {

		const material = new THREE.MeshPhongMaterial( {
			color,
		} );

		const cube = new THREE.Mesh( geometry, material );
		scene.add( cube );

		cube.position.x = x;

		return cube;

	}
```
</details>

### `resizeRendererToDisplaySize(renderer: any): boolean`

**Parameters:**

- **`renderer`** `any`

**Returns:** `boolean`

**Calls:**

- `renderer.setSize`

<details><summary>Code</summary>

```typescript
function resizeRendererToDisplaySize( renderer ) {

		const canvas = renderer.domElement;
		const width = state.width;
		const height = state.height;
		const needResize = canvas.width !== width || canvas.height !== height;
		if ( needResize ) {

			renderer.setSize( width, height, false );

		}

		return needResize;

	}
```
</details>

### `render(time: any): void`

**Parameters:**

- **`time`** `any`

**Returns:** `void`

**Calls:**

- `resizeRendererToDisplaySize`
- `camera.updateProjectionMatrix`
- `cubes.forEach`
- `renderer.render`
- `requestAnimationFrame`

<details><summary>Code</summary>

```typescript
function render( time ) {

		time *= 0.001;

		if ( resizeRendererToDisplaySize( renderer ) ) {

			camera.aspect = state.width / state.height;
			camera.updateProjectionMatrix();

		}

		cubes.forEach( ( cube, ndx ) => {

			const speed = 1 + ndx * .1;
			const rot = time * speed;
			cube.rotation.x = rot;
			cube.rotation.y = rot;

		} );

		renderer.render( scene, camera );

		requestAnimationFrame( render );

	}
```
</details>


---