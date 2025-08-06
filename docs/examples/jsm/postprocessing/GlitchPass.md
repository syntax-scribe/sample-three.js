[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `GlitchPass.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 4 |
| 🧱 Classes | 1 |
| 📦 Imports | 9 |
| 📊 Variables & Constants | 3 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/postprocessing/GlitchPass.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `DataTexture` | `three` |
| `FloatType` | `three` |
| `MathUtils` | `three` |
| `RedFormat` | `three` |
| `ShaderMaterial` | `three` |
| `UniformsUtils` | `three` |
| `Pass` | `./Pass.js` |
| `FullScreenQuad` | `./Pass.js` |
| `DigitalGlitch` | `../shaders/DigitalGlitch.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `data_arr` | `Float32Array<ArrayBuffer>` | let/var | `new Float32Array( dt_size * dt_size )` | ✗ |
| `length` | `number` | let/var | `dt_size * dt_size` | ✗ |
| `texture` | `any` | let/var | `new DataTexture( data_arr, dt_size, dt_size, RedFormat, FloatType )` | ✗ |


---

## Functions

### `GlitchPass.render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget): void`

**JSDoc:**
```typescript
/**
	 * Performs the glitch pass.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {WebGLRenderTarget} writeBuffer - The write buffer. This buffer is intended as the rendering
	 * destination for the pass.
	 * @param {WebGLRenderTarget} readBuffer - The read buffer. The pass can access the result from the
	 * previous pass from this buffer.
	 * @param {number} deltaTime - The delta time in seconds.
	 * @param {boolean} maskActive - Whether masking is active or not.
	 */
```

**Parameters:**

- **`renderer`** `WebGLRenderer`
- **`writeBuffer`** `WebGLRenderTarget`
- **`readBuffer`** `WebGLRenderTarget`

**Returns:** `void`

**Calls:**

- `Math.random`
- `MathUtils.randFloat`
- `this._generateTrigger`
- `renderer.setRenderTarget`
- `this._fsQuad.render`
- `renderer.clear`

<details><summary>Code</summary>

```typescript
render( renderer, writeBuffer, readBuffer /*, deltaTime, maskActive */ ) {

		this.uniforms[ 'tDiffuse' ].value = readBuffer.texture;
		this.uniforms[ 'seed' ].value = Math.random(); // default seeding
		this.uniforms[ 'byp' ].value = 0;

		if ( this._curF % this._randX == 0 || this.goWild == true ) {

			this.uniforms[ 'amount' ].value = Math.random() / 30;
			this.uniforms[ 'angle' ].value = MathUtils.randFloat( - Math.PI, Math.PI );
			this.uniforms[ 'seed_x' ].value = MathUtils.randFloat( - 1, 1 );
			this.uniforms[ 'seed_y' ].value = MathUtils.randFloat( - 1, 1 );
			this.uniforms[ 'distortion_x' ].value = MathUtils.randFloat( 0, 1 );
			this.uniforms[ 'distortion_y' ].value = MathUtils.randFloat( 0, 1 );
			this._curF = 0;
			this._generateTrigger();

		} else if ( this._curF % this._randX < this._randX / 5 ) {

			this.uniforms[ 'amount' ].value = Math.random() / 90;
			this.uniforms[ 'angle' ].value = MathUtils.randFloat( - Math.PI, Math.PI );
			this.uniforms[ 'distortion_x' ].value = MathUtils.randFloat( 0, 1 );
			this.uniforms[ 'distortion_y' ].value = MathUtils.randFloat( 0, 1 );
			this.uniforms[ 'seed_x' ].value = MathUtils.randFloat( - 0.3, 0.3 );
			this.uniforms[ 'seed_y' ].value = MathUtils.randFloat( - 0.3, 0.3 );

		} else if ( this.goWild == false ) {

			this.uniforms[ 'byp' ].value = 1;

		}

		this._curF ++;

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );
			this._fsQuad.render( renderer );

		} else {

			renderer.setRenderTarget( writeBuffer );
			if ( this.clear ) renderer.clear();
			this._fsQuad.render( renderer );

		}

	}
```
</details>

### `GlitchPass.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.material.dispose`
- `this.heightMap.dispose`
- `this._fsQuad.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.material.dispose();

		this.heightMap.dispose();

		this._fsQuad.dispose();

	}
```
</details>

### `GlitchPass._generateTrigger(): void`

**Returns:** `void`

**Calls:**

- `MathUtils.randInt`

<details><summary>Code</summary>

```typescript
_generateTrigger() {

		this._randX = MathUtils.randInt( 120, 240 );

	}
```
</details>

### `GlitchPass._generateHeightmap(dt_size: any): any`

**Parameters:**

- **`dt_size`** `any`

**Returns:** `any`

**Calls:**

- `MathUtils.randFloat`

<details><summary>Code</summary>

```typescript
_generateHeightmap( dt_size ) {

		const data_arr = new Float32Array( dt_size * dt_size );
		const length = dt_size * dt_size;

		for ( let i = 0; i < length; i ++ ) {

			const val = MathUtils.randFloat( 0, 1 );
			data_arr[ i ] = val;

		}

		const texture = new DataTexture( data_arr, dt_size, dt_size, RedFormat, FloatType );
		texture.needsUpdate = true;
		return texture;

	}
```
</details>


---

## Classes

### `GlitchPass`

<details><summary>Class Code</summary>

```ts
class GlitchPass extends Pass {

	/**
	 * Constructs a new glitch pass.
	 *
	 * @param {number} [dt_size=64] - The size of the displacement texture
	 * for digital glitch squares.
	 */
	constructor( dt_size = 64 ) {

		super();

		/**
		 * The pass uniforms.
		 *
		 * @type {Object}
		 */
		this.uniforms = UniformsUtils.clone( DigitalGlitch.uniforms );

		/**
		 * The pass material.
		 *
		 * @type {ShaderMaterial}
		 */
		this.material = new ShaderMaterial( {
			uniforms: this.uniforms,
			vertexShader: DigitalGlitch.vertexShader,
			fragmentShader: DigitalGlitch.fragmentShader
		} );

		/**
		 * Whether to noticeably increase the effect intensity or not.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.goWild = false;

		// internals

		this._heightMap = this._generateHeightmap( dt_size );
		this.uniforms[ 'tDisp' ].value = this.heightMap;

		this._fsQuad = new FullScreenQuad( this.material );

		this._curF = 0;
		this._randX = 0;

		this._generateTrigger();

	}

	/**
	 * Performs the glitch pass.
	 *
	 * @param {WebGLRenderer} renderer - The renderer.
	 * @param {WebGLRenderTarget} writeBuffer - The write buffer. This buffer is intended as the rendering
	 * destination for the pass.
	 * @param {WebGLRenderTarget} readBuffer - The read buffer. The pass can access the result from the
	 * previous pass from this buffer.
	 * @param {number} deltaTime - The delta time in seconds.
	 * @param {boolean} maskActive - Whether masking is active or not.
	 */
	render( renderer, writeBuffer, readBuffer /*, deltaTime, maskActive */ ) {

		this.uniforms[ 'tDiffuse' ].value = readBuffer.texture;
		this.uniforms[ 'seed' ].value = Math.random(); // default seeding
		this.uniforms[ 'byp' ].value = 0;

		if ( this._curF % this._randX == 0 || this.goWild == true ) {

			this.uniforms[ 'amount' ].value = Math.random() / 30;
			this.uniforms[ 'angle' ].value = MathUtils.randFloat( - Math.PI, Math.PI );
			this.uniforms[ 'seed_x' ].value = MathUtils.randFloat( - 1, 1 );
			this.uniforms[ 'seed_y' ].value = MathUtils.randFloat( - 1, 1 );
			this.uniforms[ 'distortion_x' ].value = MathUtils.randFloat( 0, 1 );
			this.uniforms[ 'distortion_y' ].value = MathUtils.randFloat( 0, 1 );
			this._curF = 0;
			this._generateTrigger();

		} else if ( this._curF % this._randX < this._randX / 5 ) {

			this.uniforms[ 'amount' ].value = Math.random() / 90;
			this.uniforms[ 'angle' ].value = MathUtils.randFloat( - Math.PI, Math.PI );
			this.uniforms[ 'distortion_x' ].value = MathUtils.randFloat( 0, 1 );
			this.uniforms[ 'distortion_y' ].value = MathUtils.randFloat( 0, 1 );
			this.uniforms[ 'seed_x' ].value = MathUtils.randFloat( - 0.3, 0.3 );
			this.uniforms[ 'seed_y' ].value = MathUtils.randFloat( - 0.3, 0.3 );

		} else if ( this.goWild == false ) {

			this.uniforms[ 'byp' ].value = 1;

		}

		this._curF ++;

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );
			this._fsQuad.render( renderer );

		} else {

			renderer.setRenderTarget( writeBuffer );
			if ( this.clear ) renderer.clear();
			this._fsQuad.render( renderer );

		}

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever the pass is no longer used in your app.
	 */
	dispose() {

		this.material.dispose();

		this.heightMap.dispose();

		this._fsQuad.dispose();

	}

	// internals

	_generateTrigger() {

		this._randX = MathUtils.randInt( 120, 240 );

	}

	_generateHeightmap( dt_size ) {

		const data_arr = new Float32Array( dt_size * dt_size );
		const length = dt_size * dt_size;

		for ( let i = 0; i < length; i ++ ) {

			const val = MathUtils.randFloat( 0, 1 );
			data_arr[ i ] = val;

		}

		const texture = new DataTexture( data_arr, dt_size, dt_size, RedFormat, FloatType );
		texture.needsUpdate = true;
		return texture;

	}

}
```
</details>

#### Methods

##### `render(renderer: WebGLRenderer, writeBuffer: WebGLRenderTarget, readBuffer: WebGLRenderTarget): void`

<details><summary>Code</summary>

```ts
render( renderer, writeBuffer, readBuffer /*, deltaTime, maskActive */ ) {

		this.uniforms[ 'tDiffuse' ].value = readBuffer.texture;
		this.uniforms[ 'seed' ].value = Math.random(); // default seeding
		this.uniforms[ 'byp' ].value = 0;

		if ( this._curF % this._randX == 0 || this.goWild == true ) {

			this.uniforms[ 'amount' ].value = Math.random() / 30;
			this.uniforms[ 'angle' ].value = MathUtils.randFloat( - Math.PI, Math.PI );
			this.uniforms[ 'seed_x' ].value = MathUtils.randFloat( - 1, 1 );
			this.uniforms[ 'seed_y' ].value = MathUtils.randFloat( - 1, 1 );
			this.uniforms[ 'distortion_x' ].value = MathUtils.randFloat( 0, 1 );
			this.uniforms[ 'distortion_y' ].value = MathUtils.randFloat( 0, 1 );
			this._curF = 0;
			this._generateTrigger();

		} else if ( this._curF % this._randX < this._randX / 5 ) {

			this.uniforms[ 'amount' ].value = Math.random() / 90;
			this.uniforms[ 'angle' ].value = MathUtils.randFloat( - Math.PI, Math.PI );
			this.uniforms[ 'distortion_x' ].value = MathUtils.randFloat( 0, 1 );
			this.uniforms[ 'distortion_y' ].value = MathUtils.randFloat( 0, 1 );
			this.uniforms[ 'seed_x' ].value = MathUtils.randFloat( - 0.3, 0.3 );
			this.uniforms[ 'seed_y' ].value = MathUtils.randFloat( - 0.3, 0.3 );

		} else if ( this.goWild == false ) {

			this.uniforms[ 'byp' ].value = 1;

		}

		this._curF ++;

		if ( this.renderToScreen ) {

			renderer.setRenderTarget( null );
			this._fsQuad.render( renderer );

		} else {

			renderer.setRenderTarget( writeBuffer );
			if ( this.clear ) renderer.clear();
			this._fsQuad.render( renderer );

		}

	}
```
</details>

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.material.dispose();

		this.heightMap.dispose();

		this._fsQuad.dispose();

	}
```
</details>

##### `_generateTrigger(): void`

<details><summary>Code</summary>

```ts
_generateTrigger() {

		this._randX = MathUtils.randInt( 120, 240 );

	}
```
</details>

##### `_generateHeightmap(dt_size: any): any`

<details><summary>Code</summary>

```ts
_generateHeightmap( dt_size ) {

		const data_arr = new Float32Array( dt_size * dt_size );
		const length = dt_size * dt_size;

		for ( let i = 0; i < length; i ++ ) {

			const val = MathUtils.randFloat( 0, 1 );
			data_arr[ i ] = val;

		}

		const texture = new DataTexture( data_arr, dt_size, dt_size, RedFormat, FloatType );
		texture.needsUpdate = true;
		return texture;

	}
```
</details>


---