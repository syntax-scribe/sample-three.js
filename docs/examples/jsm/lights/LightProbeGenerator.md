[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LightProbeGenerator.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 11 |
| 📊 Variables & Constants | 38 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/lights/LightProbeGenerator.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `three` |
| `LightProbe` | `three` |
| `LinearSRGBColorSpace` | `three` |
| `SphericalHarmonics3` | `three` |
| `Vector3` | `three` |
| `SRGBColorSpace` | `three` |
| `NoColorSpace` | `three` |
| `HalfFloatType` | `three` |
| `DataUtils` | `three` |
| `WebGLCoordinateSystem` | `three` |
| `FloatType` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `totalWeight` | `number` | let/var | `0` | ✗ |
| `coord` | `any` | let/var | `new Vector3()` | ✗ |
| `dir` | `any` | let/var | `new Vector3()` | ✗ |
| `color` | `any` | let/var | `new Color()` | ✗ |
| `shBasis` | `number[]` | let/var | `[ 0, 0, 0, 0, 0, 0, 0, 0, 0 ]` | ✗ |
| `sh` | `any` | let/var | `new SphericalHarmonics3()` | ✗ |
| `shCoefficients` | `any` | let/var | `sh.coefficients` | ✗ |
| `image` | `any` | let/var | `cubeTexture.image[ faceIndex ]` | ✗ |
| `width` | `any` | let/var | `image.width` | ✗ |
| `height` | `any` | let/var | `image.height` | ✗ |
| `data` | `Uint8ClampedArray<ArrayBufferLike>` | let/var | `imageData.data` | ✗ |
| `imageWidth` | `number` | let/var | `imageData.width` | ✗ |
| `pixelSize` | `number` | let/var | `2 / imageWidth` | ✗ |
| `pixelIndex` | `number` | let/var | `i / 4` | ✗ |
| `col` | `number` | let/var | `- 1 + ( pixelIndex % imageWidth + 0.5 ) * pixelSize` | ✗ |
| `row` | `number` | let/var | `1 - ( Math.floor( pixelIndex / imageWidth ) + 0.5 ) * pixelSize` | ✗ |
| `weight` | `number` | let/var | `4 / ( Math.sqrt( lengthSq ) * lengthSq )` | ✗ |
| `norm` | `number` | let/var | `( 4 * Math.PI ) / totalWeight` | ✗ |
| `flip` | `1 \| -1` | let/var | `renderer.coordinateSystem === WebGLCoordinateSystem ? - 1 : 1` | ✗ |
| `totalWeight` | `number` | let/var | `0` | ✗ |
| `coord` | `any` | let/var | `new Vector3()` | ✗ |
| `dir` | `any` | let/var | `new Vector3()` | ✗ |
| `color` | `any` | let/var | `new Color()` | ✗ |
| `shBasis` | `number[]` | let/var | `[ 0, 0, 0, 0, 0, 0, 0, 0, 0 ]` | ✗ |
| `sh` | `any` | let/var | `new SphericalHarmonics3()` | ✗ |
| `shCoefficients` | `any` | let/var | `sh.coefficients` | ✗ |
| `dataType` | `any` | let/var | `cubeRenderTarget.texture.type` | ✗ |
| `imageWidth` | `any` | let/var | `cubeRenderTarget.width` | ✗ |
| `data` | `any` | let/var | `*not shown*` | ✗ |
| `pixelSize` | `number` | let/var | `2 / imageWidth` | ✗ |
| `r` | `any` | let/var | `*not shown*` | ✗ |
| `g` | `any` | let/var | `*not shown*` | ✗ |
| `b` | `any` | let/var | `*not shown*` | ✗ |
| `pixelIndex` | `number` | let/var | `i / 4` | ✗ |
| `col` | `number` | let/var | `( 1 - ( pixelIndex % imageWidth + 0.5 ) * pixelSize ) * flip` | ✗ |
| `row` | `number` | let/var | `1 - ( Math.floor( pixelIndex / imageWidth ) + 0.5 ) * pixelSize` | ✗ |
| `weight` | `number` | let/var | `4 / ( Math.sqrt( lengthSq ) * lengthSq )` | ✗ |
| `norm` | `number` | let/var | `( 4 * Math.PI ) / totalWeight` | ✗ |


---

## Functions

### `LightProbeGenerator.fromCubeTexture(cubeTexture: CubeTexture): LightProbe`

**JSDoc:**
```typescript
/**
	 * Creates a light probe from the given (radiance) environment map.
	 * The method expects that the environment map is represented as a cube texture.
	 *
	 * @param {CubeTexture} cubeTexture - The environment map.
	 * @return {LightProbe} The created light probe.
	 */
```

**Parameters:**

- **`cubeTexture`** `CubeTexture`

**Returns:** `LightProbe`

**Calls:**

- `document.createElement`
- `canvas.getContext`
- `context.drawImage`
- `context.getImageData`
- `color.setRGB`
- `convertColorToLinear`
- `Math.floor`
- `coord.set`
- `coord.lengthSq`
- `Math.sqrt`
- `dir.copy( coord ).normalize`
- `SphericalHarmonics3.getBasisAt`

**Internal Comments:**
```
// https://www.ppsloan.org/publications/StupidSH36.pdf (x2)
// pixel color (x4)
// convert to linear color space (x3)
// pixel coordinate on unit cube (x2)
// weight assigned to this pixel (x2)
// direction vector to this pixel (x6)
// evaluate SH basis functions in direction dir (x4)
// accumulate
// normalize (x2)
```

<details><summary>Code</summary>

```typescript
static fromCubeTexture( cubeTexture ) {

		// https://www.ppsloan.org/publications/StupidSH36.pdf

		let totalWeight = 0;

		const coord = new Vector3();

		const dir = new Vector3();

		const color = new Color();

		const shBasis = [ 0, 0, 0, 0, 0, 0, 0, 0, 0 ];

		const sh = new SphericalHarmonics3();
		const shCoefficients = sh.coefficients;

		for ( let faceIndex = 0; faceIndex < 6; faceIndex ++ ) {

			const image = cubeTexture.image[ faceIndex ];

			const width = image.width;
			const height = image.height;

			const canvas = document.createElement( 'canvas' );

			canvas.width = width;
			canvas.height = height;

			const context = canvas.getContext( '2d' );

			context.drawImage( image, 0, 0, width, height );

			const imageData = context.getImageData( 0, 0, width, height );

			const data = imageData.data;

			const imageWidth = imageData.width; // assumed to be square

			const pixelSize = 2 / imageWidth;

			for ( let i = 0, il = data.length; i < il; i += 4 ) { // RGBA assumed

				// pixel color
				color.setRGB( data[ i ] / 255, data[ i + 1 ] / 255, data[ i + 2 ] / 255 );

				// convert to linear color space
				convertColorToLinear( color, cubeTexture.colorSpace );

				// pixel coordinate on unit cube

				const pixelIndex = i / 4;

				const col = - 1 + ( pixelIndex % imageWidth + 0.5 ) * pixelSize;

				const row = 1 - ( Math.floor( pixelIndex / imageWidth ) + 0.5 ) * pixelSize;

				switch ( faceIndex ) {

					case 0: coord.set( - 1, row, - col ); break;

					case 1: coord.set( 1, row, col ); break;

					case 2: coord.set( - col, 1, - row ); break;

					case 3: coord.set( - col, - 1, row ); break;

					case 4: coord.set( - col, row, 1 ); break;

					case 5: coord.set( col, row, - 1 ); break;

				}

				// weight assigned to this pixel

				const lengthSq = coord.lengthSq();

				const weight = 4 / ( Math.sqrt( lengthSq ) * lengthSq );

				totalWeight += weight;

				// direction vector to this pixel
				dir.copy( coord ).normalize();

				// evaluate SH basis functions in direction dir
				SphericalHarmonics3.getBasisAt( dir, shBasis );

				// accumulate
				for ( let j = 0; j < 9; j ++ ) {

					shCoefficients[ j ].x += shBasis[ j ] * color.r * weight;
					shCoefficients[ j ].y += shBasis[ j ] * color.g * weight;
					shCoefficients[ j ].z += shBasis[ j ] * color.b * weight;

				}

			}

		}

		// normalize
		const norm = ( 4 * Math.PI ) / totalWeight;

		for ( let j = 0; j < 9; j ++ ) {

			shCoefficients[ j ].x *= norm;
			shCoefficients[ j ].y *= norm;
			shCoefficients[ j ].z *= norm;

		}

		return new LightProbe( sh );

	}
```
</details>

### `LightProbeGenerator.fromCubeRenderTarget(renderer: any, cubeRenderTarget: any): Promise<LightProbe>`

**JSDoc:**
```typescript
/**
	 * Creates a light probe from the given (radiance) environment map.
	 * The method expects that the environment map is represented as a cube render target.
	 *
	 * The cube render target must be in RGBA so `cubeRenderTarget.texture.format` must be
	 * set to {@link RGBAFormat}.
	 *
	 * @async
	 * @param {WebGPURenderer|WebGLRenderer} renderer - The renderer.
	 * @param {CubeRenderTarget|WebGLCubeRenderTarget} cubeRenderTarget - The environment map.
	 * @return {Promise<LightProbe>} A Promise that resolves with the created light probe.
	 */
```

**Parameters:**

- **`renderer`** `any`
- **`cubeRenderTarget`** `any`

**Returns:** `Promise<LightProbe>`

**Calls:**

- `renderer.readRenderTargetPixelsAsync`
- `DataUtils.fromHalfFloat`
- `color.setRGB`
- `convertColorToLinear`
- `Math.floor`
- `coord.set`
- `coord.lengthSq`
- `Math.sqrt`
- `dir.copy( coord ).normalize`
- `SphericalHarmonics3.getBasisAt`

**Internal Comments:**
```
// The renderTarget must be set to RGBA in order to make readRenderTargetPixels works (x2)
// assuming UnsignedByteType (x3)
// pixel color (x4)
// convert to linear color space (x3)
// pixel coordinate on unit cube (x2)
// weight assigned to this pixel (x2)
// direction vector to this pixel (x6)
// evaluate SH basis functions in direction dir (x4)
// accumulate
// normalize (x2)
```

<details><summary>Code</summary>

```typescript
static async fromCubeRenderTarget( renderer, cubeRenderTarget ) {

		const flip = renderer.coordinateSystem === WebGLCoordinateSystem ? - 1 : 1;

		// The renderTarget must be set to RGBA in order to make readRenderTargetPixels works
		let totalWeight = 0;

		const coord = new Vector3();

		const dir = new Vector3();

		const color = new Color();

		const shBasis = [ 0, 0, 0, 0, 0, 0, 0, 0, 0 ];

		const sh = new SphericalHarmonics3();
		const shCoefficients = sh.coefficients;

		const dataType = cubeRenderTarget.texture.type;
		const imageWidth = cubeRenderTarget.width; // assumed to be square

		let data;

		if ( renderer.isWebGLRenderer ) {

			if ( dataType === FloatType ) {

				data = new Float32Array( imageWidth * imageWidth * 4 );

			} else if ( dataType === HalfFloatType ) {

				data = new Uint16Array( imageWidth * imageWidth * 4 );

			} else {

				// assuming UnsignedByteType

				data = new Uint8Array( imageWidth * imageWidth * 4 );

			}

		}

		for ( let faceIndex = 0; faceIndex < 6; faceIndex ++ ) {

			if ( renderer.isWebGLRenderer ) {

				await renderer.readRenderTargetPixelsAsync( cubeRenderTarget, 0, 0, imageWidth, imageWidth, data, faceIndex );

			} else {

				data = await renderer.readRenderTargetPixelsAsync( cubeRenderTarget, 0, 0, imageWidth, imageWidth, 0, faceIndex );

			}

			const pixelSize = 2 / imageWidth;

			for ( let i = 0, il = data.length; i < il; i += 4 ) { // RGBA assumed

				let r, g, b;

				if ( dataType === FloatType ) {

					r = data[ i ];
					g = data[ i + 1 ];
					b = data[ i + 2 ];

				} else if ( dataType === HalfFloatType ) {

					r = DataUtils.fromHalfFloat( data[ i ] );
					g = DataUtils.fromHalfFloat( data[ i + 1 ] );
					b = DataUtils.fromHalfFloat( data[ i + 2 ] );

				} else {

					r = data[ i ] / 255;
					g = data[ i + 1 ] / 255;
					b = data[ i + 2 ] / 255;

				}

				// pixel color
				color.setRGB( r, g, b );

				// convert to linear color space
				convertColorToLinear( color, cubeRenderTarget.texture.colorSpace );

				// pixel coordinate on unit cube

				const pixelIndex = i / 4;

				const col = ( 1 - ( pixelIndex % imageWidth + 0.5 ) * pixelSize ) * flip;

				const row = 1 - ( Math.floor( pixelIndex / imageWidth ) + 0.5 ) * pixelSize;

				switch ( faceIndex ) {

					case 0: coord.set( - 1 * flip, row, col * flip ); break;

					case 1: coord.set( 1 * flip, row, - col * flip ); break;

					case 2: coord.set( col, 1, - row ); break;

					case 3: coord.set( col, - 1, row ); break;

					case 4: coord.set( col, row, 1 ); break;

					case 5: coord.set( - col, row, - 1 ); break;

				}

				// weight assigned to this pixel

				const lengthSq = coord.lengthSq();

				const weight = 4 / ( Math.sqrt( lengthSq ) * lengthSq );

				totalWeight += weight;

				// direction vector to this pixel
				dir.copy( coord ).normalize();

				// evaluate SH basis functions in direction dir
				SphericalHarmonics3.getBasisAt( dir, shBasis );

				// accumulate
				for ( let j = 0; j < 9; j ++ ) {

					shCoefficients[ j ].x += shBasis[ j ] * color.r * weight;
					shCoefficients[ j ].y += shBasis[ j ] * color.g * weight;
					shCoefficients[ j ].z += shBasis[ j ] * color.b * weight;

				}

			}

		}

		// normalize
		const norm = ( 4 * Math.PI ) / totalWeight;

		for ( let j = 0; j < 9; j ++ ) {

			shCoefficients[ j ].x *= norm;
			shCoefficients[ j ].y *= norm;
			shCoefficients[ j ].z *= norm;

		}

		return new LightProbe( sh );

	}
```
</details>

### `convertColorToLinear(color: any, colorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`colorSpace`** `any`

**Returns:** `any`

**Calls:**

- `color.convertSRGBToLinear`
- `console.warn`

<details><summary>Code</summary>

```typescript
function convertColorToLinear( color, colorSpace ) {

	switch ( colorSpace ) {

		case SRGBColorSpace:

			color.convertSRGBToLinear();
			break;

		case LinearSRGBColorSpace:
		case NoColorSpace:

			break;

		default:

			console.warn( 'WARNING: LightProbeGenerator convertColorToLinear() encountered an unsupported color space.' );
			break;

	}

	return color;

}
```
</details>


---

## Classes

### `LightProbeGenerator`

<details><summary>Class Code</summary>

```ts
class LightProbeGenerator {

	/**
	 * Creates a light probe from the given (radiance) environment map.
	 * The method expects that the environment map is represented as a cube texture.
	 *
	 * @param {CubeTexture} cubeTexture - The environment map.
	 * @return {LightProbe} The created light probe.
	 */
	static fromCubeTexture( cubeTexture ) {

		// https://www.ppsloan.org/publications/StupidSH36.pdf

		let totalWeight = 0;

		const coord = new Vector3();

		const dir = new Vector3();

		const color = new Color();

		const shBasis = [ 0, 0, 0, 0, 0, 0, 0, 0, 0 ];

		const sh = new SphericalHarmonics3();
		const shCoefficients = sh.coefficients;

		for ( let faceIndex = 0; faceIndex < 6; faceIndex ++ ) {

			const image = cubeTexture.image[ faceIndex ];

			const width = image.width;
			const height = image.height;

			const canvas = document.createElement( 'canvas' );

			canvas.width = width;
			canvas.height = height;

			const context = canvas.getContext( '2d' );

			context.drawImage( image, 0, 0, width, height );

			const imageData = context.getImageData( 0, 0, width, height );

			const data = imageData.data;

			const imageWidth = imageData.width; // assumed to be square

			const pixelSize = 2 / imageWidth;

			for ( let i = 0, il = data.length; i < il; i += 4 ) { // RGBA assumed

				// pixel color
				color.setRGB( data[ i ] / 255, data[ i + 1 ] / 255, data[ i + 2 ] / 255 );

				// convert to linear color space
				convertColorToLinear( color, cubeTexture.colorSpace );

				// pixel coordinate on unit cube

				const pixelIndex = i / 4;

				const col = - 1 + ( pixelIndex % imageWidth + 0.5 ) * pixelSize;

				const row = 1 - ( Math.floor( pixelIndex / imageWidth ) + 0.5 ) * pixelSize;

				switch ( faceIndex ) {

					case 0: coord.set( - 1, row, - col ); break;

					case 1: coord.set( 1, row, col ); break;

					case 2: coord.set( - col, 1, - row ); break;

					case 3: coord.set( - col, - 1, row ); break;

					case 4: coord.set( - col, row, 1 ); break;

					case 5: coord.set( col, row, - 1 ); break;

				}

				// weight assigned to this pixel

				const lengthSq = coord.lengthSq();

				const weight = 4 / ( Math.sqrt( lengthSq ) * lengthSq );

				totalWeight += weight;

				// direction vector to this pixel
				dir.copy( coord ).normalize();

				// evaluate SH basis functions in direction dir
				SphericalHarmonics3.getBasisAt( dir, shBasis );

				// accumulate
				for ( let j = 0; j < 9; j ++ ) {

					shCoefficients[ j ].x += shBasis[ j ] * color.r * weight;
					shCoefficients[ j ].y += shBasis[ j ] * color.g * weight;
					shCoefficients[ j ].z += shBasis[ j ] * color.b * weight;

				}

			}

		}

		// normalize
		const norm = ( 4 * Math.PI ) / totalWeight;

		for ( let j = 0; j < 9; j ++ ) {

			shCoefficients[ j ].x *= norm;
			shCoefficients[ j ].y *= norm;
			shCoefficients[ j ].z *= norm;

		}

		return new LightProbe( sh );

	}

	/**
	 * Creates a light probe from the given (radiance) environment map.
	 * The method expects that the environment map is represented as a cube render target.
	 *
	 * The cube render target must be in RGBA so `cubeRenderTarget.texture.format` must be
	 * set to {@link RGBAFormat}.
	 *
	 * @async
	 * @param {WebGPURenderer|WebGLRenderer} renderer - The renderer.
	 * @param {CubeRenderTarget|WebGLCubeRenderTarget} cubeRenderTarget - The environment map.
	 * @return {Promise<LightProbe>} A Promise that resolves with the created light probe.
	 */
	static async fromCubeRenderTarget( renderer, cubeRenderTarget ) {

		const flip = renderer.coordinateSystem === WebGLCoordinateSystem ? - 1 : 1;

		// The renderTarget must be set to RGBA in order to make readRenderTargetPixels works
		let totalWeight = 0;

		const coord = new Vector3();

		const dir = new Vector3();

		const color = new Color();

		const shBasis = [ 0, 0, 0, 0, 0, 0, 0, 0, 0 ];

		const sh = new SphericalHarmonics3();
		const shCoefficients = sh.coefficients;

		const dataType = cubeRenderTarget.texture.type;
		const imageWidth = cubeRenderTarget.width; // assumed to be square

		let data;

		if ( renderer.isWebGLRenderer ) {

			if ( dataType === FloatType ) {

				data = new Float32Array( imageWidth * imageWidth * 4 );

			} else if ( dataType === HalfFloatType ) {

				data = new Uint16Array( imageWidth * imageWidth * 4 );

			} else {

				// assuming UnsignedByteType

				data = new Uint8Array( imageWidth * imageWidth * 4 );

			}

		}

		for ( let faceIndex = 0; faceIndex < 6; faceIndex ++ ) {

			if ( renderer.isWebGLRenderer ) {

				await renderer.readRenderTargetPixelsAsync( cubeRenderTarget, 0, 0, imageWidth, imageWidth, data, faceIndex );

			} else {

				data = await renderer.readRenderTargetPixelsAsync( cubeRenderTarget, 0, 0, imageWidth, imageWidth, 0, faceIndex );

			}

			const pixelSize = 2 / imageWidth;

			for ( let i = 0, il = data.length; i < il; i += 4 ) { // RGBA assumed

				let r, g, b;

				if ( dataType === FloatType ) {

					r = data[ i ];
					g = data[ i + 1 ];
					b = data[ i + 2 ];

				} else if ( dataType === HalfFloatType ) {

					r = DataUtils.fromHalfFloat( data[ i ] );
					g = DataUtils.fromHalfFloat( data[ i + 1 ] );
					b = DataUtils.fromHalfFloat( data[ i + 2 ] );

				} else {

					r = data[ i ] / 255;
					g = data[ i + 1 ] / 255;
					b = data[ i + 2 ] / 255;

				}

				// pixel color
				color.setRGB( r, g, b );

				// convert to linear color space
				convertColorToLinear( color, cubeRenderTarget.texture.colorSpace );

				// pixel coordinate on unit cube

				const pixelIndex = i / 4;

				const col = ( 1 - ( pixelIndex % imageWidth + 0.5 ) * pixelSize ) * flip;

				const row = 1 - ( Math.floor( pixelIndex / imageWidth ) + 0.5 ) * pixelSize;

				switch ( faceIndex ) {

					case 0: coord.set( - 1 * flip, row, col * flip ); break;

					case 1: coord.set( 1 * flip, row, - col * flip ); break;

					case 2: coord.set( col, 1, - row ); break;

					case 3: coord.set( col, - 1, row ); break;

					case 4: coord.set( col, row, 1 ); break;

					case 5: coord.set( - col, row, - 1 ); break;

				}

				// weight assigned to this pixel

				const lengthSq = coord.lengthSq();

				const weight = 4 / ( Math.sqrt( lengthSq ) * lengthSq );

				totalWeight += weight;

				// direction vector to this pixel
				dir.copy( coord ).normalize();

				// evaluate SH basis functions in direction dir
				SphericalHarmonics3.getBasisAt( dir, shBasis );

				// accumulate
				for ( let j = 0; j < 9; j ++ ) {

					shCoefficients[ j ].x += shBasis[ j ] * color.r * weight;
					shCoefficients[ j ].y += shBasis[ j ] * color.g * weight;
					shCoefficients[ j ].z += shBasis[ j ] * color.b * weight;

				}

			}

		}

		// normalize
		const norm = ( 4 * Math.PI ) / totalWeight;

		for ( let j = 0; j < 9; j ++ ) {

			shCoefficients[ j ].x *= norm;
			shCoefficients[ j ].y *= norm;
			shCoefficients[ j ].z *= norm;

		}

		return new LightProbe( sh );

	}

}
```
</details>

#### Methods

##### `fromCubeTexture(cubeTexture: CubeTexture): LightProbe`

<details><summary>Code</summary>

```ts
static fromCubeTexture( cubeTexture ) {

		// https://www.ppsloan.org/publications/StupidSH36.pdf

		let totalWeight = 0;

		const coord = new Vector3();

		const dir = new Vector3();

		const color = new Color();

		const shBasis = [ 0, 0, 0, 0, 0, 0, 0, 0, 0 ];

		const sh = new SphericalHarmonics3();
		const shCoefficients = sh.coefficients;

		for ( let faceIndex = 0; faceIndex < 6; faceIndex ++ ) {

			const image = cubeTexture.image[ faceIndex ];

			const width = image.width;
			const height = image.height;

			const canvas = document.createElement( 'canvas' );

			canvas.width = width;
			canvas.height = height;

			const context = canvas.getContext( '2d' );

			context.drawImage( image, 0, 0, width, height );

			const imageData = context.getImageData( 0, 0, width, height );

			const data = imageData.data;

			const imageWidth = imageData.width; // assumed to be square

			const pixelSize = 2 / imageWidth;

			for ( let i = 0, il = data.length; i < il; i += 4 ) { // RGBA assumed

				// pixel color
				color.setRGB( data[ i ] / 255, data[ i + 1 ] / 255, data[ i + 2 ] / 255 );

				// convert to linear color space
				convertColorToLinear( color, cubeTexture.colorSpace );

				// pixel coordinate on unit cube

				const pixelIndex = i / 4;

				const col = - 1 + ( pixelIndex % imageWidth + 0.5 ) * pixelSize;

				const row = 1 - ( Math.floor( pixelIndex / imageWidth ) + 0.5 ) * pixelSize;

				switch ( faceIndex ) {

					case 0: coord.set( - 1, row, - col ); break;

					case 1: coord.set( 1, row, col ); break;

					case 2: coord.set( - col, 1, - row ); break;

					case 3: coord.set( - col, - 1, row ); break;

					case 4: coord.set( - col, row, 1 ); break;

					case 5: coord.set( col, row, - 1 ); break;

				}

				// weight assigned to this pixel

				const lengthSq = coord.lengthSq();

				const weight = 4 / ( Math.sqrt( lengthSq ) * lengthSq );

				totalWeight += weight;

				// direction vector to this pixel
				dir.copy( coord ).normalize();

				// evaluate SH basis functions in direction dir
				SphericalHarmonics3.getBasisAt( dir, shBasis );

				// accumulate
				for ( let j = 0; j < 9; j ++ ) {

					shCoefficients[ j ].x += shBasis[ j ] * color.r * weight;
					shCoefficients[ j ].y += shBasis[ j ] * color.g * weight;
					shCoefficients[ j ].z += shBasis[ j ] * color.b * weight;

				}

			}

		}

		// normalize
		const norm = ( 4 * Math.PI ) / totalWeight;

		for ( let j = 0; j < 9; j ++ ) {

			shCoefficients[ j ].x *= norm;
			shCoefficients[ j ].y *= norm;
			shCoefficients[ j ].z *= norm;

		}

		return new LightProbe( sh );

	}
```
</details>

##### `fromCubeRenderTarget(renderer: any, cubeRenderTarget: any): Promise<LightProbe>`

<details><summary>Code</summary>

```ts
static async fromCubeRenderTarget( renderer, cubeRenderTarget ) {

		const flip = renderer.coordinateSystem === WebGLCoordinateSystem ? - 1 : 1;

		// The renderTarget must be set to RGBA in order to make readRenderTargetPixels works
		let totalWeight = 0;

		const coord = new Vector3();

		const dir = new Vector3();

		const color = new Color();

		const shBasis = [ 0, 0, 0, 0, 0, 0, 0, 0, 0 ];

		const sh = new SphericalHarmonics3();
		const shCoefficients = sh.coefficients;

		const dataType = cubeRenderTarget.texture.type;
		const imageWidth = cubeRenderTarget.width; // assumed to be square

		let data;

		if ( renderer.isWebGLRenderer ) {

			if ( dataType === FloatType ) {

				data = new Float32Array( imageWidth * imageWidth * 4 );

			} else if ( dataType === HalfFloatType ) {

				data = new Uint16Array( imageWidth * imageWidth * 4 );

			} else {

				// assuming UnsignedByteType

				data = new Uint8Array( imageWidth * imageWidth * 4 );

			}

		}

		for ( let faceIndex = 0; faceIndex < 6; faceIndex ++ ) {

			if ( renderer.isWebGLRenderer ) {

				await renderer.readRenderTargetPixelsAsync( cubeRenderTarget, 0, 0, imageWidth, imageWidth, data, faceIndex );

			} else {

				data = await renderer.readRenderTargetPixelsAsync( cubeRenderTarget, 0, 0, imageWidth, imageWidth, 0, faceIndex );

			}

			const pixelSize = 2 / imageWidth;

			for ( let i = 0, il = data.length; i < il; i += 4 ) { // RGBA assumed

				let r, g, b;

				if ( dataType === FloatType ) {

					r = data[ i ];
					g = data[ i + 1 ];
					b = data[ i + 2 ];

				} else if ( dataType === HalfFloatType ) {

					r = DataUtils.fromHalfFloat( data[ i ] );
					g = DataUtils.fromHalfFloat( data[ i + 1 ] );
					b = DataUtils.fromHalfFloat( data[ i + 2 ] );

				} else {

					r = data[ i ] / 255;
					g = data[ i + 1 ] / 255;
					b = data[ i + 2 ] / 255;

				}

				// pixel color
				color.setRGB( r, g, b );

				// convert to linear color space
				convertColorToLinear( color, cubeRenderTarget.texture.colorSpace );

				// pixel coordinate on unit cube

				const pixelIndex = i / 4;

				const col = ( 1 - ( pixelIndex % imageWidth + 0.5 ) * pixelSize ) * flip;

				const row = 1 - ( Math.floor( pixelIndex / imageWidth ) + 0.5 ) * pixelSize;

				switch ( faceIndex ) {

					case 0: coord.set( - 1 * flip, row, col * flip ); break;

					case 1: coord.set( 1 * flip, row, - col * flip ); break;

					case 2: coord.set( col, 1, - row ); break;

					case 3: coord.set( col, - 1, row ); break;

					case 4: coord.set( col, row, 1 ); break;

					case 5: coord.set( - col, row, - 1 ); break;

				}

				// weight assigned to this pixel

				const lengthSq = coord.lengthSq();

				const weight = 4 / ( Math.sqrt( lengthSq ) * lengthSq );

				totalWeight += weight;

				// direction vector to this pixel
				dir.copy( coord ).normalize();

				// evaluate SH basis functions in direction dir
				SphericalHarmonics3.getBasisAt( dir, shBasis );

				// accumulate
				for ( let j = 0; j < 9; j ++ ) {

					shCoefficients[ j ].x += shBasis[ j ] * color.r * weight;
					shCoefficients[ j ].y += shBasis[ j ] * color.g * weight;
					shCoefficients[ j ].z += shBasis[ j ] * color.b * weight;

				}

			}

		}

		// normalize
		const norm = ( 4 * Math.PI ) / totalWeight;

		for ( let j = 0; j < 9; j ++ ) {

			shCoefficients[ j ].x *= norm;
			shCoefficients[ j ].y *= norm;
			shCoefficients[ j ].z *= norm;

		}

		return new LightProbe( sh );

	}
```
</details>


---