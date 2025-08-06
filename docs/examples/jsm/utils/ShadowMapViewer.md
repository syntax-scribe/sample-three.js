[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ShadowMapViewer.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 18 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/utils/ShadowMapViewer.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DoubleSide` | `three` |
| `CanvasTexture` | `three` |
| `Mesh` | `three` |
| `MeshBasicMaterial` | `three` |
| `OrthographicCamera` | `three` |
| `PlaneGeometry` | `three` |
| `Scene` | `three` |
| `ShaderMaterial` | `three` |
| `UniformsUtils` | `three` |
| `UnpackDepthRGBAShader` | `../shaders/UnpackDepthRGBAShader.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `doRenderLabel` | `boolean` | let/var | `( light.name !== undefined && light.name !== '' )` | ✗ |
| `userAutoClearSetting` | `any` | let/var | `*not shown*` | ✗ |
| `frame` | `{ x: number; y: number; width: number...` | let/var | `{ x: 10, y: 10, width: 256, height: 256 }` | ✗ |
| `camera` | `any` | let/var | `new OrthographicCamera( window.innerWidth / - 2, window.innerWidth / 2, windo...` | ✗ |
| `scene` | `any` | let/var | `new Scene()` | ✗ |
| `shader` | `ShaderMaterial` | let/var | `UnpackDepthRGBAShader` | ✗ |
| `material` | `any` | let/var | `new ShaderMaterial( { uniforms: uniforms, vertexShader: shader.vertexShader, ...` | ✗ |
| `plane` | `any` | let/var | `new PlaneGeometry( frame.width, frame.height )` | ✗ |
| `mesh` | `any` | let/var | `new Mesh( plane, material )` | ✗ |
| `labelCanvas` | `any` | let/var | `*not shown*` | ✗ |
| `labelMesh` | `any` | let/var | `*not shown*` | ✗ |
| `labelWidth` | `number` | let/var | `context.measureText( light.name ).width` | ✗ |
| `labelTexture` | `any` | let/var | `new CanvasTexture( labelCanvas )` | ✗ |
| `labelMaterial` | `any` | let/var | `new MeshBasicMaterial( { map: labelTexture, side: DoubleSide, transparent: tr...` | ✗ |
| `labelPlane` | `any` | let/var | `new PlaneGeometry( labelCanvas.width, labelCanvas.height )` | ✗ |
| `width` | `number` | let/var | `scope.size.width` | ✗ |
| `height` | `number` | let/var | `scope.size.height` | ✗ |


---

## Functions

### `resetPosition(): void`

**Returns:** `void`

**Calls:**

- `scope.position.set`

<details><summary>Code</summary>

```typescript
function resetPosition() {

			scope.position.set( scope.position.x, scope.position.y );

		}
```
</details>

### `set(width: any, height: any): void`

**Parameters:**

- **`width`** `any`
- **`height`** `any`

**Returns:** `void`

**Calls:**

- `mesh.scale.set`
- `resetPosition`

**Internal Comments:**
```
//Reset the position as it is off when we scale stuff (x3)
```

<details><summary>Code</summary>

```typescript
function ( width, height ) {

				this.width = width;
				this.height = height;

				mesh.scale.set( this.width / frame.width, this.height / frame.height, 1 );

				//Reset the position as it is off when we scale stuff
				resetPosition();

			}
```
</details>

### `set(width: any, height: any): void`

**Parameters:**

- **`width`** `any`
- **`height`** `any`

**Returns:** `void`

**Calls:**

- `mesh.scale.set`
- `resetPosition`

**Internal Comments:**
```
//Reset the position as it is off when we scale stuff (x3)
```

<details><summary>Code</summary>

```typescript
function ( width, height ) {

				this.width = width;
				this.height = height;

				mesh.scale.set( this.width / frame.width, this.height / frame.height, 1 );

				//Reset the position as it is off when we scale stuff
				resetPosition();

			}
```
</details>

### `set(x: number, y: number): void`

**Parameters:**

- **`x`** `number`
- **`y`** `number`

**Returns:** `void`

**Calls:**

- `mesh.position.set`
- `labelMesh.position.set`

<details><summary>Code</summary>

```typescript
function ( x, y ) {

				this.x = x;
				this.y = y;

				const width = scope.size.width;
				const height = scope.size.height;

				mesh.position.set( - window.innerWidth / 2 + width / 2 + this.x, window.innerHeight / 2 - height / 2 - this.y, 0 );

				if ( doRenderLabel ) labelMesh.position.set( mesh.position.x, mesh.position.y - scope.size.height / 2 + labelCanvas.height / 2, 0 );

			}
```
</details>

### `set(x: number, y: number): void`

**Parameters:**

- **`x`** `number`
- **`y`** `number`

**Returns:** `void`

**Calls:**

- `mesh.position.set`
- `labelMesh.position.set`

<details><summary>Code</summary>

```typescript
function ( x, y ) {

				this.x = x;
				this.y = y;

				const width = scope.size.width;
				const height = scope.size.height;

				mesh.position.set( - window.innerWidth / 2 + width / 2 + this.x, window.innerHeight / 2 - height / 2 - this.y, 0 );

				if ( doRenderLabel ) labelMesh.position.set( mesh.position.x, mesh.position.y - scope.size.height / 2 + labelCanvas.height / 2, 0 );

			}
```
</details>


---

## Classes

### `ShadowMapViewer`

<details><summary>Class Code</summary>

```ts
class ShadowMapViewer {

	/**
	 * Constructs a new shadow map viewer.
	 *
	 * @param {Light} light - The shadow casting light.
	 */
	constructor( light ) {

		//- Internals
		const scope = this;
		const doRenderLabel = ( light.name !== undefined && light.name !== '' );
		let userAutoClearSetting;

		//Holds the initial position and dimension of the HUD
		const frame = {
			x: 10,
			y: 10,
			width: 256,
			height: 256
		};

		const camera = new OrthographicCamera( window.innerWidth / - 2, window.innerWidth / 2, window.innerHeight / 2, window.innerHeight / - 2, 1, 10 );
		camera.position.set( 0, 0, 2 );
		const scene = new Scene();

		//HUD for shadow map
		const shader = UnpackDepthRGBAShader;

		const uniforms = UniformsUtils.clone( shader.uniforms );
		const material = new ShaderMaterial( {
			uniforms: uniforms,
			vertexShader: shader.vertexShader,
			fragmentShader: shader.fragmentShader
		} );
		const plane = new PlaneGeometry( frame.width, frame.height );
		const mesh = new Mesh( plane, material );

		scene.add( mesh );


		//Label for light's name
		let labelCanvas, labelMesh;

		if ( doRenderLabel ) {

			labelCanvas = document.createElement( 'canvas' );

			const context = labelCanvas.getContext( '2d' );
			context.font = 'Bold 20px Arial';

			const labelWidth = context.measureText( light.name ).width;
			labelCanvas.width = labelWidth;
			labelCanvas.height = 25;	//25 to account for g, p, etc.

			context.font = 'Bold 20px Arial';
			context.fillStyle = 'rgba( 255, 0, 0, 1 )';
			context.fillText( light.name, 0, 20 );

			const labelTexture = new CanvasTexture( labelCanvas );

			const labelMaterial = new MeshBasicMaterial( { map: labelTexture, side: DoubleSide, transparent: true } );

			const labelPlane = new PlaneGeometry( labelCanvas.width, labelCanvas.height );
			labelMesh = new Mesh( labelPlane, labelMaterial );

			scene.add( labelMesh );

		}


		function resetPosition() {

			scope.position.set( scope.position.x, scope.position.y );

		}

		/**
		 * Whether to display the shadow map viewer or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.enabled = true;

		/**
		 * The size of the viewer. When changing this property, make sure
		 * to call {@link ShadowMapViewer#update}.
		 *
		 * @type {{width:number,height:number}}
		 * @default true
		 */
		this.size = {
			width: frame.width,
			height: frame.height,
			set: function ( width, height ) {

				this.width = width;
				this.height = height;

				mesh.scale.set( this.width / frame.width, this.height / frame.height, 1 );

				//Reset the position as it is off when we scale stuff
				resetPosition();

			}
		};

		/**
		 * The position of the viewer. When changing this property, make sure
		 * to call {@link ShadowMapViewer#update}.
		 *
		 * @type {{x:number,y:number, set:function(number,number)}}
		 * @default true
		 */
		this.position = {
			x: frame.x,
			y: frame.y,
			set: function ( x, y ) {

				this.x = x;
				this.y = y;

				const width = scope.size.width;
				const height = scope.size.height;

				mesh.position.set( - window.innerWidth / 2 + width / 2 + this.x, window.innerHeight / 2 - height / 2 - this.y, 0 );

				if ( doRenderLabel ) labelMesh.position.set( mesh.position.x, mesh.position.y - scope.size.height / 2 + labelCanvas.height / 2, 0 );

			}
		};

		/**
		 * Renders the viewer. This method must be called in the app's animation loop.
		 *
		 * @param {WebGLRenderer} renderer - The renderer.
		 */
		this.render = function ( renderer ) {

			if ( this.enabled ) {

				//Because a light's .shadowMap is only initialised after the first render pass
				//we have to make sure the correct map is sent into the shader, otherwise we
				//always end up with the scene's first added shadow casting light's shadowMap
				//in the shader
				//See: https://github.com/mrdoob/three.js/issues/5932
				uniforms.tDiffuse.value = light.shadow.map.texture;

				userAutoClearSetting = renderer.autoClear;
				renderer.autoClear = false; // To allow render overlay
				renderer.clearDepth();
				renderer.render( scene, camera );
				renderer.autoClear = userAutoClearSetting;	//Restore user's setting

			}

		};

		/**
		 * Resizes the viewer. This method should be called whenever the app's
		 * window is resized.
		 */
		this.updateForWindowResize = function () {

			if ( this.enabled ) {

				 camera.left = window.innerWidth / - 2;
				 camera.right = window.innerWidth / 2;
				 camera.top = window.innerHeight / 2;
				 camera.bottom = window.innerHeight / - 2;
				 camera.updateProjectionMatrix();

				 this.update();

			}

		};

		/**
		 * Updates the viewer.
		 */
		this.update = function () {

			this.position.set( this.position.x, this.position.y );
			this.size.set( this.size.width, this.size.height );

		};

		//Force an update to set position/size
		this.update();

	}

}
```
</details>


---