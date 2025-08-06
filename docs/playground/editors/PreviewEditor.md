[⬅️ Back to Table of Contents](../../index.md)

# 📄 `PreviewEditor.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 18 |
| 📊 Variables & Constants | 16 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`playground/editors/PreviewEditor.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `OrbitControls` | `three/addons/controls/OrbitControls.js` |
| `ViewHelper` | `three/addons/helpers/ViewHelper.js` |
| `Element` | `flow` |
| `LabelElement` | `flow` |
| `SelectInput` | `flow` |
| `BaseNodeEditor` | `../BaseNodeEditor.js` |
| `MeshBasicNodeMaterial` | `three/webgpu` |
| `vec4` | `three/tsl` |
| `PerspectiveCamera` | `three` |
| `Scene` | `three` |
| `Mesh` | `three` |
| `DoubleSide` | `three` |
| `SphereGeometry` | `three` |
| `BoxGeometry` | `three` |
| `PlaneGeometry` | `three` |
| `TorusKnotGeometry` | `three` |
| `WebGPURenderer` | `three` |
| `setInputAestheticsFromType` | `../DataTypeLib.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `sceneDict` | `{}` | let/var | `{}` | ✗ |
| `scene` | `any` | let/var | `sceneDict[ name ]` | ✗ |
| `box` | `any` | let/var | `new Mesh( new BoxGeometry( 1.3, 1.3, 1.3 ) )` | ✗ |
| `sphere` | `any` | let/var | `new Mesh( new SphereGeometry( 1, 32, 16 ) )` | ✗ |
| `plane` | `any` | let/var | `new Mesh( new PlaneGeometry( 2, 2 ) )` | ✗ |
| `torus` | `any` | let/var | `new Mesh( new TorusKnotGeometry( .7, .1, 100, 16 ) )` | ✗ |
| `width` | `300` | let/var | `300` | ✗ |
| `height` | `300` | let/var | `300` | ✗ |
| `material` | `any` | let/var | `new MeshBasicNodeMaterial()` | ✗ |
| `previewElement` | `any` | let/var | `new Element()` | ✗ |
| `sceneInput` | `any` | let/var | `new SelectInput( [ { name: 'Box', value: 'box' }, { name: 'Sphere', value: 's...` | ✗ |
| `renderer` | `any` | let/var | `new WebGPURenderer( { canvas, alpha: true, antialias: true } )` | ✗ |
| `camera` | `any` | let/var | `new PerspectiveCamera( 45, width / height, 0.1, 100 )` | ✗ |
| `controls` | `any` | let/var | `new OrbitControls( camera, previewElement.dom )` | ✗ |
| `viewHelper` | `any` | let/var | `new ViewHelper( camera, previewElement.dom )` | ✗ |
| `mesh` | `any` | let/var | `scene.children[ 0 ]` | ✗ |


---

## Functions

### `getScene(name: any): any`

**Parameters:**

- **`name`** `any`

**Returns:** `any`

**Calls:**

- `scene.add`

<details><summary>Code</summary>

```typescript
( name ) => {

	let scene = sceneDict[ name ];

	if ( scene === undefined ) {

		scene = new Scene();

		if ( name === 'box' ) {

			const box = new Mesh( new BoxGeometry( 1.3, 1.3, 1.3 ) );
			scene.add( box );

		} else if ( name === 'sphere' ) {

			const sphere = new Mesh( new SphereGeometry( 1, 32, 16 ) );
			scene.add( sphere );

		} else if ( name === 'plane' || name === 'sprite' ) {

			const plane = new Mesh( new PlaneGeometry( 2, 2 ) );
			scene.add( plane );


		} else if ( name === 'torus' ) {

			const torus = new Mesh( new TorusKnotGeometry( .7, .1, 100, 16 ) );
			scene.add( torus );

		}

		sceneDict[ name ] = scene;

	}

	return scene;

}
```
</details>

### `PreviewEditor.setEditor(editor: any): void`

**Parameters:**

- **`editor`** `any`

**Returns:** `void`

**Calls:**

- `super.setEditor`
- `this.updateAnimationRequest`

<details><summary>Code</summary>

```typescript
setEditor( editor ) {

		super.setEditor( editor );

		this.updateAnimationRequest();

	}
```
</details>

### `PreviewEditor.updateAnimationRequest(): void`

**Returns:** `void`

**Calls:**

- `requestAnimationFrame`
- `this.update`

<details><summary>Code</summary>

```typescript
updateAnimationRequest() {

		if ( this.editor !== null ) {

			requestAnimationFrame( () => this.update() );

		}

	}
```
</details>

### `PreviewEditor.update(): Promise<void>`

**Returns:** `Promise<void>`

**Calls:**

- `this.updateAnimationRequest`
- `sceneInput.getValue`
- `getScene`
- `mesh.lookAt`
- `renderer.clearAsync`
- `renderer.renderAsync`
- `viewHelper.render`

<details><summary>Code</summary>

```typescript
async update() {

		const { viewHelper, material, renderer, camera, sceneInput } = this;

		this.updateAnimationRequest();

		const sceneName = sceneInput.getValue();

		const scene = getScene( sceneName );
		const mesh = scene.children[ 0 ];

		mesh.material = material;

		if ( sceneName === 'sprite' ) {

			mesh.lookAt( camera.position );

		}

		await renderer.clearAsync();
		await renderer.renderAsync( scene, camera );

		viewHelper.render( renderer );

	}
```
</details>


---

## Classes

### `PreviewEditor`

<details><summary>Class Code</summary>

```ts
export class PreviewEditor extends BaseNodeEditor {

	constructor() {

		const width = 300;
		const height = 300;

		super( 'Preview', null, width );

		const material = new MeshBasicNodeMaterial();
		material.colorNode = vec4( 0, 0, 0, 1 );
		material.side = DoubleSide;
		material.transparent = true;

		const previewElement = new Element();
		previewElement.dom.style[ 'padding-top' ] = 0;
		previewElement.dom.style[ 'padding-bottom' ] = 0;
		previewElement.dom.style[ 'padding-left' ] = 0;
		previewElement.dom.style[ 'padding-right' ] = '14px';

		const sceneInput = new SelectInput( [
			{ name: 'Box', value: 'box' },
			{ name: 'Sphere', value: 'sphere' },
			{ name: 'Plane', value: 'plane' },
			{ name: 'Sprite', value: 'sprite' },
			{ name: 'Torus', value: 'torus' }
		], 'box' );

		const inputElement = setInputAestheticsFromType( new LabelElement( 'Input' ), 'Color' ).onConnect( () => {

			material.colorNode = inputElement.getLinkedObject() || vec4( 0, 0, 0, 1 );
			material.dispose();

		}, true );

		const canvas = document.createElement( 'canvas' );
		canvas.style.position = 'absolute';
		previewElement.dom.append( canvas );
		previewElement.setHeight( height );

		previewElement.dom.addEventListener( 'wheel', e => e.stopPropagation() );

		const renderer = new WebGPURenderer( {
			canvas,
			alpha: true,
			antialias: true
		} );

		renderer.autoClear = false;
		renderer.setSize( width, height, true );
		renderer.setPixelRatio( window.devicePixelRatio );

		const camera = new PerspectiveCamera( 45, width / height, 0.1, 100 );
		camera.aspect = width / height;
		camera.updateProjectionMatrix();
		camera.position.set( - 2, 2, 2 );
		camera.lookAt( 0, 0, 0 );

		const controls = new OrbitControls( camera, previewElement.dom );
		controls.enableKeys = false;
		controls.update();

		const viewHelper = new ViewHelper( camera, previewElement.dom );

		this.sceneInput = sceneInput;
		this.viewHelper = viewHelper;
		this.material = material;
		this.camera = camera;
		this.renderer = renderer;

		this.add( inputElement )
			.add( new LabelElement( 'Object' ).add( sceneInput ) )
			.add( previewElement );

	}

	setEditor( editor ) {

		super.setEditor( editor );

		this.updateAnimationRequest();

	}

	updateAnimationRequest() {

		if ( this.editor !== null ) {

			requestAnimationFrame( () => this.update() );

		}

	}

	async update() {

		const { viewHelper, material, renderer, camera, sceneInput } = this;

		this.updateAnimationRequest();

		const sceneName = sceneInput.getValue();

		const scene = getScene( sceneName );
		const mesh = scene.children[ 0 ];

		mesh.material = material;

		if ( sceneName === 'sprite' ) {

			mesh.lookAt( camera.position );

		}

		await renderer.clearAsync();
		await renderer.renderAsync( scene, camera );

		viewHelper.render( renderer );

	}

}
```
</details>

#### Methods

##### `setEditor(editor: any): void`

<details><summary>Code</summary>

```ts
setEditor( editor ) {

		super.setEditor( editor );

		this.updateAnimationRequest();

	}
```
</details>

##### `updateAnimationRequest(): void`

<details><summary>Code</summary>

```ts
updateAnimationRequest() {

		if ( this.editor !== null ) {

			requestAnimationFrame( () => this.update() );

		}

	}
```
</details>

##### `update(): Promise<void>`

<details><summary>Code</summary>

```ts
async update() {

		const { viewHelper, material, renderer, camera, sceneInput } = this;

		this.updateAnimationRequest();

		const sceneName = sceneInput.getValue();

		const scene = getScene( sceneName );
		const mesh = scene.children[ 0 ];

		mesh.material = material;

		if ( sceneName === 'sprite' ) {

			mesh.lookAt( camera.position );

		}

		await renderer.clearAsync();
		await renderer.renderAsync( scene, camera );

		viewHelper.render( renderer );

	}
```
</details>


---