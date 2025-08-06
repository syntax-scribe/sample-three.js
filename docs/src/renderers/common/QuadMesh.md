[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `QuadMesh.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 2 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/QuadMesh.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `BufferGeometry` | `../../core/BufferGeometry.js` |
| `Float32BufferAttribute` | `../../core/BufferAttribute.js` |
| `Mesh` | `../../objects/Mesh.js` |
| `OrthographicCamera` | `../../cameras/OrthographicCamera.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_camera` | `OrthographicCamera` | let/var | `new OrthographicCamera( - 1, 1, 1, - 1, 0, 1 )` | ✗ |
| `uv` | `number[]` | let/var | `flipY === false ? [ 0, - 1, 0, 1, 2, 1 ] : [ 0, 2, 0, 0, 2, 0 ]` | ✗ |
| `_geometry` | `QuadGeometry` | let/var | `new QuadGeometry()` | ✗ |


---

## Functions

### `QuadMesh.renderAsync(renderer: Renderer): Promise<any>`

**JSDoc:**
```typescript
/**
	 * Async version of `render()`.
	 *
	 * @async
	 * @param {Renderer} renderer - The renderer.
	 * @return {Promise} A Promise that resolves when the render has been finished.
	 */
```

**Parameters:**

- **`renderer`** `Renderer`

**Returns:** `Promise<any>`

**Calls:**

- `renderer.renderAsync`

<details><summary>Code</summary>

```typescript
async renderAsync( renderer ) {

		return renderer.renderAsync( this, _camera );

	}
```
</details>

### `QuadMesh.render(renderer: Renderer): void`

**JSDoc:**
```typescript
/**
	 * Renders the quad mesh
	 *
	 * @param {Renderer} renderer - The renderer.
	 */
```

**Parameters:**

- **`renderer`** `Renderer`

**Returns:** `void`

**Calls:**

- `renderer.render`

<details><summary>Code</summary>

```typescript
render( renderer ) {

		renderer.render( this, _camera );

	}
```
</details>


---

## Classes

### `QuadGeometry`

<details><summary>Class Code</summary>

```ts
class QuadGeometry extends BufferGeometry {

	/**
	 * Constructs a new quad geometry.
	 *
	 * @param {boolean} [flipY=false] - Whether the uv coordinates should be flipped along the vertical axis or not.
	 */
	constructor( flipY = false ) {

		super();

		const uv = flipY === false ? [ 0, - 1, 0, 1, 2, 1 ] : [ 0, 2, 0, 0, 2, 0 ];

		this.setAttribute( 'position', new Float32BufferAttribute( [ - 1, 3, 0, - 1, - 1, 0, 3, - 1, 0 ], 3 ) );
		this.setAttribute( 'uv', new Float32BufferAttribute( uv, 2 ) );

	}

}
```
</details>

### `QuadMesh`

<details><summary>Class Code</summary>

```ts
class QuadMesh extends Mesh {

	/**
	 * Constructs a new quad mesh.
	 *
	 * @param {?Material} [material=null] - The material to render the quad mesh with.
	 */
	constructor( material = null ) {

		super( _geometry, material );

		/**
		 * The camera to render the quad mesh with.
		 *
		 * @type {OrthographicCamera}
		 * @readonly
		 */
		this.camera = _camera;

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isQuadMesh = true;

	}

	/**
	 * Async version of `render()`.
	 *
	 * @async
	 * @param {Renderer} renderer - The renderer.
	 * @return {Promise} A Promise that resolves when the render has been finished.
	 */
	async renderAsync( renderer ) {

		return renderer.renderAsync( this, _camera );

	}

	/**
	 * Renders the quad mesh
	 *
	 * @param {Renderer} renderer - The renderer.
	 */
	render( renderer ) {

		renderer.render( this, _camera );

	}

}
```
</details>

#### Methods

##### `renderAsync(renderer: Renderer): Promise<any>`

<details><summary>Code</summary>

```ts
async renderAsync( renderer ) {

		return renderer.renderAsync( this, _camera );

	}
```
</details>

##### `render(renderer: Renderer): void`

<details><summary>Code</summary>

```ts
render( renderer ) {

		renderer.render( this, _camera );

	}
```
</details>


---