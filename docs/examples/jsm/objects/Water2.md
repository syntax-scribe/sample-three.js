[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Water2.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 13 |
| 📊 Variables & Constants | 21 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/objects/Water2.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Clock` | `three` |
| `Color` | `three` |
| `Matrix4` | `three` |
| `Mesh` | `three` |
| `RepeatWrapping` | `three` |
| `ShaderMaterial` | `three` |
| `TextureLoader` | `three` |
| `UniformsLib` | `three` |
| `UniformsUtils` | `three` |
| `Vector2` | `three` |
| `Vector4` | `three` |
| `Reflector` | `../objects/Reflector.js` |
| `Refractor` | `../objects/Refractor.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `scope` | `this` | let/var | `this` | ✗ |
| `color` | `any` | let/var | `( options.color !== undefined ) ? new Color( options.color ) : new Color( 0xF...` | ✗ |
| `textureWidth` | `any` | let/var | `options.textureWidth !== undefined ? options.textureWidth : 512` | ✗ |
| `textureHeight` | `any` | let/var | `options.textureHeight !== undefined ? options.textureHeight : 512` | ✗ |
| `clipBias` | `any` | let/var | `options.clipBias !== undefined ? options.clipBias : 0` | ✗ |
| `flowDirection` | `any` | let/var | `options.flowDirection !== undefined ? options.flowDirection : new Vector2( 1,...` | ✗ |
| `flowSpeed` | `any` | let/var | `options.flowSpeed !== undefined ? options.flowSpeed : 0.03` | ✗ |
| `reflectivity` | `any` | let/var | `options.reflectivity !== undefined ? options.reflectivity : 0.02` | ✗ |
| `scale` | `any` | let/var | `options.scale !== undefined ? options.scale : 1` | ✗ |
| `shader` | `any` | let/var | `options.shader !== undefined ? options.shader : Water.WaterShader` | ✗ |
| `textureLoader` | `any` | let/var | `new TextureLoader()` | ✗ |
| `flowMap` | `any` | let/var | `options.flowMap \|\| undefined` | ✗ |
| `normalMap0` | `any` | let/var | `options.normalMap0 \|\| textureLoader.load( 'textures/water/Water_1_M_Normal....` | ✗ |
| `normalMap1` | `any` | let/var | `options.normalMap1 \|\| textureLoader.load( 'textures/water/Water_2_M_Normal....` | ✗ |
| `cycle` | `0.15` | let/var | `0.15` | ✗ |
| `halfCycle` | `number` | let/var | `cycle * 0.5` | ✗ |
| `textureMatrix` | `any` | let/var | `new Matrix4()` | ✗ |
| `clock` | `any` | let/var | `new Clock()` | ✗ |
| `reflector` | `Reflector` | let/var | `new Reflector( geometry, { textureWidth: textureWidth, textureHeight: texture...` | ✗ |
| `refractor` | `Refractor` | let/var | `new Refractor( geometry, { textureWidth: textureWidth, textureHeight: texture...` | ✗ |
| `config` | `any` | let/var | `scope.material.uniforms[ 'config' ]` | ✗ |


---

## Functions

### `updateTextureMatrix(camera: any): void`

**Parameters:**

- **`camera`** `any`

**Returns:** `void`

**Calls:**

- `textureMatrix.set`
- `textureMatrix.multiply`

<details><summary>Code</summary>

```typescript
function updateTextureMatrix( camera ) {

			textureMatrix.set(
				0.5, 0.0, 0.0, 0.5,
				0.0, 0.5, 0.0, 0.5,
				0.0, 0.0, 0.5, 0.5,
				0.0, 0.0, 0.0, 1.0
			);

			textureMatrix.multiply( camera.projectionMatrix );
			textureMatrix.multiply( camera.matrixWorldInverse );
			textureMatrix.multiply( scope.matrixWorld );

		}
```
</details>

### `updateFlow(): void`

**Returns:** `void`

**Calls:**

- `clock.getDelta`

**Internal Comments:**
```
// Important: The distance between offsets should be always the value of "halfCycle".
// Moreover, both offsets should be in the range of [ 0, cycle ].
// This approach ensures a smooth water flow and avoids "reset" effects.
```

<details><summary>Code</summary>

```typescript
function updateFlow() {

			const delta = clock.getDelta();
			const config = scope.material.uniforms[ 'config' ];

			config.value.x += flowSpeed * delta; // flowMapOffset0
			config.value.y = config.value.x + halfCycle; // flowMapOffset1

			// Important: The distance between offsets should be always the value of "halfCycle".
			// Moreover, both offsets should be in the range of [ 0, cycle ].
			// This approach ensures a smooth water flow and avoids "reset" effects.

			if ( config.value.x >= cycle ) {

				config.value.x = 0;
				config.value.y = halfCycle;

			} else if ( config.value.y >= cycle ) {

				config.value.y = config.value.y - cycle;

			}

		}
```
</details>


---

## Classes

### `Water`

<details><summary>Class Code</summary>

```ts
class Water extends Mesh {

	/**
	 * Constructs a new water instance.
	 *
	 * @param {BufferGeometry} geometry - The water's geometry.
	 * @param {module:Water2~Options} [options] - The configuration options.
	 */
	constructor( geometry, options = {} ) {

		super( geometry );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isWater = true;

		this.type = 'Water';

		const scope = this;

		const color = ( options.color !== undefined ) ? new Color( options.color ) : new Color( 0xFFFFFF );
		const textureWidth = options.textureWidth !== undefined ? options.textureWidth : 512;
		const textureHeight = options.textureHeight !== undefined ? options.textureHeight : 512;
		const clipBias = options.clipBias !== undefined ? options.clipBias : 0;
		const flowDirection = options.flowDirection !== undefined ? options.flowDirection : new Vector2( 1, 0 );
		const flowSpeed = options.flowSpeed !== undefined ? options.flowSpeed : 0.03;
		const reflectivity = options.reflectivity !== undefined ? options.reflectivity : 0.02;
		const scale = options.scale !== undefined ? options.scale : 1;
		const shader = options.shader !== undefined ? options.shader : Water.WaterShader;

		const textureLoader = new TextureLoader();

		const flowMap = options.flowMap || undefined;
		const normalMap0 = options.normalMap0 || textureLoader.load( 'textures/water/Water_1_M_Normal.jpg' );
		const normalMap1 = options.normalMap1 || textureLoader.load( 'textures/water/Water_2_M_Normal.jpg' );

		const cycle = 0.15; // a cycle of a flow map phase
		const halfCycle = cycle * 0.5;
		const textureMatrix = new Matrix4();
		const clock = new Clock();

		// internal components

		if ( Reflector === undefined ) {

			console.error( 'THREE.Water: Required component Reflector not found.' );
			return;

		}

		if ( Refractor === undefined ) {

			console.error( 'THREE.Water: Required component Refractor not found.' );
			return;

		}

		const reflector = new Reflector( geometry, {
			textureWidth: textureWidth,
			textureHeight: textureHeight,
			clipBias: clipBias
		} );

		const refractor = new Refractor( geometry, {
			textureWidth: textureWidth,
			textureHeight: textureHeight,
			clipBias: clipBias
		} );

		reflector.matrixAutoUpdate = false;
		refractor.matrixAutoUpdate = false;

		// material

		this.material = new ShaderMaterial( {
			name: shader.name,
			uniforms: UniformsUtils.merge( [
				UniformsLib[ 'fog' ],
				shader.uniforms
			] ),
			vertexShader: shader.vertexShader,
			fragmentShader: shader.fragmentShader,
			transparent: true,
			fog: true
		} );

		if ( flowMap !== undefined ) {

			this.material.defines.USE_FLOWMAP = '';
			this.material.uniforms[ 'tFlowMap' ] = {
				type: 't',
				value: flowMap
			};

		} else {

			this.material.uniforms[ 'flowDirection' ] = {
				type: 'v2',
				value: flowDirection
			};

		}

		// maps

		normalMap0.wrapS = normalMap0.wrapT = RepeatWrapping;
		normalMap1.wrapS = normalMap1.wrapT = RepeatWrapping;

		this.material.uniforms[ 'tReflectionMap' ].value = reflector.getRenderTarget().texture;
		this.material.uniforms[ 'tRefractionMap' ].value = refractor.getRenderTarget().texture;
		this.material.uniforms[ 'tNormalMap0' ].value = normalMap0;
		this.material.uniforms[ 'tNormalMap1' ].value = normalMap1;

		// water

		this.material.uniforms[ 'color' ].value = color;
		this.material.uniforms[ 'reflectivity' ].value = reflectivity;
		this.material.uniforms[ 'textureMatrix' ].value = textureMatrix;

		// initial values

		this.material.uniforms[ 'config' ].value.x = 0; // flowMapOffset0
		this.material.uniforms[ 'config' ].value.y = halfCycle; // flowMapOffset1
		this.material.uniforms[ 'config' ].value.z = halfCycle; // halfCycle
		this.material.uniforms[ 'config' ].value.w = scale; // scale

		// functions

		function updateTextureMatrix( camera ) {

			textureMatrix.set(
				0.5, 0.0, 0.0, 0.5,
				0.0, 0.5, 0.0, 0.5,
				0.0, 0.0, 0.5, 0.5,
				0.0, 0.0, 0.0, 1.0
			);

			textureMatrix.multiply( camera.projectionMatrix );
			textureMatrix.multiply( camera.matrixWorldInverse );
			textureMatrix.multiply( scope.matrixWorld );

		}

		function updateFlow() {

			const delta = clock.getDelta();
			const config = scope.material.uniforms[ 'config' ];

			config.value.x += flowSpeed * delta; // flowMapOffset0
			config.value.y = config.value.x + halfCycle; // flowMapOffset1

			// Important: The distance between offsets should be always the value of "halfCycle".
			// Moreover, both offsets should be in the range of [ 0, cycle ].
			// This approach ensures a smooth water flow and avoids "reset" effects.

			if ( config.value.x >= cycle ) {

				config.value.x = 0;
				config.value.y = halfCycle;

			} else if ( config.value.y >= cycle ) {

				config.value.y = config.value.y - cycle;

			}

		}

		//

		this.onBeforeRender = function ( renderer, scene, camera ) {

			updateTextureMatrix( camera );
			updateFlow();

			scope.visible = false;

			reflector.matrixWorld.copy( scope.matrixWorld );
			refractor.matrixWorld.copy( scope.matrixWorld );

			reflector.onBeforeRender( renderer, scene, camera );
			refractor.onBeforeRender( renderer, scene, camera );

			scope.visible = true;

		};

	}

}
```
</details>


---