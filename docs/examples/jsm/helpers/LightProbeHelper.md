[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LightProbeHelper.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/helpers/LightProbeHelper.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Mesh` | `three` |
| `ShaderMaterial` | `three` |
| `SphereGeometry` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `material` | `any` | let/var | `new ShaderMaterial( { type: 'LightProbeHelperMaterial', uniforms: { sh: { val...` | ✗ |
| `geometry` | `any` | let/var | `new SphereGeometry( 1, 32, 16 )` | ✗ |


---

## Functions

### `LightProbeHelper.dispose(): void`

**JSDoc:**
```typescript
/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
```

**Returns:** `void`

**Calls:**

- `this.geometry.dispose`
- `this.material.dispose`

<details><summary>Code</summary>

```typescript
dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}
```
</details>

### `LightProbeHelper.onBeforeRender(): void`

**Returns:** `void`

**Calls:**

- `this.position.copy`
- `this.scale.set( 1, 1, 1 ).multiplyScalar`

<details><summary>Code</summary>

```typescript
onBeforeRender() {

		this.position.copy( this.lightProbe.position );

		this.scale.set( 1, 1, 1 ).multiplyScalar( this.size );

		this.material.uniforms.intensity.value = this.lightProbe.intensity;

	}
```
</details>


---

## Classes

### `LightProbeHelper`

<details><summary>Class Code</summary>

```ts
class LightProbeHelper extends Mesh {

	/**
	 * Constructs a new light probe helper.
	 *
	 * @param {LightProbe} lightProbe - The light probe to visualize.
	 * @param {number} [size=1] - The size of the helper.
	 */
	constructor( lightProbe, size = 1 ) {

		const material = new ShaderMaterial( {

			type: 'LightProbeHelperMaterial',

			uniforms: {

				sh: { value: lightProbe.sh.coefficients }, // by reference

				intensity: { value: lightProbe.intensity }

			},

			vertexShader: /* glsl */`

				varying vec3 vNormal;

				void main() {

					vNormal = normalize( normalMatrix * normal );

					gl_Position = projectionMatrix * modelViewMatrix * vec4( position, 1.0 );

				}

			`,

			fragmentShader: /* glsl */`

				#define RECIPROCAL_PI 0.318309886

				vec3 inverseTransformDirection( in vec3 normal, in mat4 matrix ) {

					// matrix is assumed to be orthogonal

					return normalize( ( vec4( normal, 0.0 ) * matrix ).xyz );

				}

				// source: https://graphics.stanford.edu/papers/envmap/envmap.pdf,
				vec3 shGetIrradianceAt( in vec3 normal, in vec3 shCoefficients[ 9 ] ) {

					// normal is assumed to have unit length,

					float x = normal.x, y = normal.y, z = normal.z;

					// band 0,
					vec3 result = shCoefficients[ 0 ] * 0.886227;

					// band 1,
					result += shCoefficients[ 1 ] * 2.0 * 0.511664 * y;
					result += shCoefficients[ 2 ] * 2.0 * 0.511664 * z;
					result += shCoefficients[ 3 ] * 2.0 * 0.511664 * x;

					// band 2,
					result += shCoefficients[ 4 ] * 2.0 * 0.429043 * x * y;
					result += shCoefficients[ 5 ] * 2.0 * 0.429043 * y * z;
					result += shCoefficients[ 6 ] * ( 0.743125 * z * z - 0.247708 );
					result += shCoefficients[ 7 ] * 2.0 * 0.429043 * x * z;
					result += shCoefficients[ 8 ] * 0.429043 * ( x * x - y * y );
					return result;

				}

				uniform vec3 sh[ 9 ]; // sh coefficients

				uniform float intensity; // light probe intensity

				varying vec3 vNormal;

				void main() {

					vec3 normal = normalize( vNormal );

					vec3 worldNormal = inverseTransformDirection( normal, viewMatrix );

					vec3 irradiance = shGetIrradianceAt( worldNormal, sh );

					vec3 outgoingLight = RECIPROCAL_PI * irradiance * intensity;

					gl_FragColor = linearToOutputTexel( vec4( outgoingLight, 1.0 ) );

				}

			`,

		} );

		const geometry = new SphereGeometry( 1, 32, 16 );

		super( geometry, material );

		/**
		 * The light probe to visualize.
		 *
		 * @type {LightProbe}
		 */
		this.lightProbe = lightProbe;

		/**
		 * The size of the helper.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.size = size;
		this.type = 'LightProbeHelper';

		this.onBeforeRender();

	}

	/**
	 * Frees the GPU-related resources allocated by this instance. Call this
	 * method whenever this instance is no longer used in your app.
	 */
	dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}

	onBeforeRender() {

		this.position.copy( this.lightProbe.position );

		this.scale.set( 1, 1, 1 ).multiplyScalar( this.size );

		this.material.uniforms.intensity.value = this.lightProbe.intensity;

	}

}
```
</details>

#### Methods

##### `dispose(): void`

<details><summary>Code</summary>

```ts
dispose() {

		this.geometry.dispose();
		this.material.dispose();

	}
```
</details>

##### `onBeforeRender(): void`

<details><summary>Code</summary>

```ts
onBeforeRender() {

		this.position.copy( this.lightProbe.position );

		this.scale.set( 1, 1, 1 ).multiplyScalar( this.size );

		this.material.uniforms.intensity.value = this.lightProbe.intensity;

	}
```
</details>


---