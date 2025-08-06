[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `WebXRDepthSensing.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |
| 📊 Variables & Constants | 5 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/webxr/WebXRDepthSensing.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `PlaneGeometry` | `../../geometries/PlaneGeometry.js` |
| `ShaderMaterial` | `../../materials/ShaderMaterial.js` |
| `Mesh` | `../../objects/Mesh.js` |
| `ExternalTexture` | `../../textures/ExternalTexture.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_occlusion_vertex` | `"\nvoid main() {\n\n\tgl_Position = v...` | let/var | `` void main() { gl_Position = vec4( position, 1.0 ); }`` | ✗ |
| `_occlusion_fragment` | `"\nuniform sampler2DArray depthColor;...` | let/var | `` uniform sampler2DArray depthColor; uniform float depthWidth; uniform float ...` | ✗ |
| `texture` | `ExternalTexture` | let/var | `new ExternalTexture( depthData.texture )` | ✗ |
| `viewport` | `any` | let/var | `cameraXR.cameras[ 0 ].viewport` | ✗ |
| `material` | `ShaderMaterial` | let/var | `new ShaderMaterial( { vertexShader: _occlusion_vertex, fragmentShader: _occlu...` | ✗ |


---

## Functions

### `WebXRDepthSensing.init(depthData: XRWebGLDepthInformation, renderState: XRRenderState): void`

**JSDoc:**
```typescript
/**
	 * Inits the depth sensing module
	 *
	 * @param {XRWebGLDepthInformation} depthData - The XR depth data.
	 * @param {XRRenderState} renderState - The XR render state.
	 */
```

**Parameters:**

- **`depthData`** `XRWebGLDepthInformation`
- **`renderState`** `XRRenderState`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
init( depthData, renderState ) {

		if ( this.texture === null ) {

			const texture = new ExternalTexture( depthData.texture );

			if ( ( depthData.depthNear !== renderState.depthNear ) || ( depthData.depthFar !== renderState.depthFar ) ) {

				this.depthNear = depthData.depthNear;
				this.depthFar = depthData.depthFar;

			}

			this.texture = texture;

		}

	}
```
</details>

### `WebXRDepthSensing.getMesh(cameraXR: ArrayCamera): Mesh`

**JSDoc:**
```typescript
/**
	 * Returns a plane mesh that visualizes the depth texture.
	 *
	 * @param {ArrayCamera} cameraXR - The XR camera.
	 * @return {?Mesh} The plane mesh.
	 */
```

**Parameters:**

- **`cameraXR`** `ArrayCamera`

**Returns:** `Mesh`

<details><summary>Code</summary>

```typescript
getMesh( cameraXR ) {

		if ( this.texture !== null ) {

			if ( this.mesh === null ) {

				const viewport = cameraXR.cameras[ 0 ].viewport;
				const material = new ShaderMaterial( {
					vertexShader: _occlusion_vertex,
					fragmentShader: _occlusion_fragment,
					uniforms: {
						depthColor: { value: this.texture },
						depthWidth: { value: viewport.z },
						depthHeight: { value: viewport.w }
					}
				} );

				this.mesh = new Mesh( new PlaneGeometry( 20, 20 ), material );

			}

		}

		return this.mesh;

	}
```
</details>

### `WebXRDepthSensing.reset(): void`

**JSDoc:**
```typescript
/**
	 * Resets the module
	 */
```

**Returns:** `void`

<details><summary>Code</summary>

```typescript
reset() {

		this.texture = null;
		this.mesh = null;

	}
```
</details>

### `WebXRDepthSensing.getDepthTexture(): ExternalTexture`

**JSDoc:**
```typescript
/**
	 * Returns a texture representing the depth of the user's environment.
	 *
	 * @return {?ExternalTexture} The depth texture.
	 */
```

**Returns:** `ExternalTexture`

<details><summary>Code</summary>

```typescript
getDepthTexture() {

		return this.texture;

	}
```
</details>


---

## Classes

### `WebXRDepthSensing`

<details><summary>Class Code</summary>

```ts
class WebXRDepthSensing {

	/**
	 * Constructs a new depth sensing module.
	 */
	constructor() {

		/**
		 * An opaque texture representing the depth of the user's environment.
		 *
		 * @type {?ExternalTexture}
		 */
		this.texture = null;

		/**
		 * A plane mesh for visualizing the depth texture.
		 *
		 * @type {?Mesh}
		 */
		this.mesh = null;

		/**
		 * The depth near value.
		 *
		 * @type {number}
		 */
		this.depthNear = 0;

		/**
		 * The depth near far.
		 *
		 * @type {number}
		 */
		this.depthFar = 0;

	}

	/**
	 * Inits the depth sensing module
	 *
	 * @param {XRWebGLDepthInformation} depthData - The XR depth data.
	 * @param {XRRenderState} renderState - The XR render state.
	 */
	init( depthData, renderState ) {

		if ( this.texture === null ) {

			const texture = new ExternalTexture( depthData.texture );

			if ( ( depthData.depthNear !== renderState.depthNear ) || ( depthData.depthFar !== renderState.depthFar ) ) {

				this.depthNear = depthData.depthNear;
				this.depthFar = depthData.depthFar;

			}

			this.texture = texture;

		}

	}

	/**
	 * Returns a plane mesh that visualizes the depth texture.
	 *
	 * @param {ArrayCamera} cameraXR - The XR camera.
	 * @return {?Mesh} The plane mesh.
	 */
	getMesh( cameraXR ) {

		if ( this.texture !== null ) {

			if ( this.mesh === null ) {

				const viewport = cameraXR.cameras[ 0 ].viewport;
				const material = new ShaderMaterial( {
					vertexShader: _occlusion_vertex,
					fragmentShader: _occlusion_fragment,
					uniforms: {
						depthColor: { value: this.texture },
						depthWidth: { value: viewport.z },
						depthHeight: { value: viewport.w }
					}
				} );

				this.mesh = new Mesh( new PlaneGeometry( 20, 20 ), material );

			}

		}

		return this.mesh;

	}

	/**
	 * Resets the module
	 */
	reset() {

		this.texture = null;
		this.mesh = null;

	}

	/**
	 * Returns a texture representing the depth of the user's environment.
	 *
	 * @return {?ExternalTexture} The depth texture.
	 */
	getDepthTexture() {

		return this.texture;

	}

}
```
</details>

#### Methods

##### `init(depthData: XRWebGLDepthInformation, renderState: XRRenderState): void`

<details><summary>Code</summary>

```ts
init( depthData, renderState ) {

		if ( this.texture === null ) {

			const texture = new ExternalTexture( depthData.texture );

			if ( ( depthData.depthNear !== renderState.depthNear ) || ( depthData.depthFar !== renderState.depthFar ) ) {

				this.depthNear = depthData.depthNear;
				this.depthFar = depthData.depthFar;

			}

			this.texture = texture;

		}

	}
```
</details>

##### `getMesh(cameraXR: ArrayCamera): Mesh`

<details><summary>Code</summary>

```ts
getMesh( cameraXR ) {

		if ( this.texture !== null ) {

			if ( this.mesh === null ) {

				const viewport = cameraXR.cameras[ 0 ].viewport;
				const material = new ShaderMaterial( {
					vertexShader: _occlusion_vertex,
					fragmentShader: _occlusion_fragment,
					uniforms: {
						depthColor: { value: this.texture },
						depthWidth: { value: viewport.z },
						depthHeight: { value: viewport.w }
					}
				} );

				this.mesh = new Mesh( new PlaneGeometry( 20, 20 ), material );

			}

		}

		return this.mesh;

	}
```
</details>

##### `reset(): void`

<details><summary>Code</summary>

```ts
reset() {

		this.texture = null;
		this.mesh = null;

	}
```
</details>

##### `getDepthTexture(): ExternalTexture`

<details><summary>Code</summary>

```ts
getDepthTexture() {

		return this.texture;

	}
```
</details>


---