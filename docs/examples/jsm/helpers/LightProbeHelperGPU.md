[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `LightProbeHelperGPU.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 10 |
| 📊 Variables & Constants | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/helpers/LightProbeHelperGPU.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Mesh` | `three` |
| `NodeMaterial` | `three` |
| `SphereGeometry` | `three` |
| `float` | `three/tsl` |
| `Fn` | `three/tsl` |
| `getShIrradianceAt` | `three/tsl` |
| `normalWorld` | `three/tsl` |
| `uniformArray` | `three/tsl` |
| `uniform` | `three/tsl` |
| `vec4` | `three/tsl` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `material` | `any` | let/var | `new NodeMaterial()` | ✗ |
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

		this._intensity.value = this.lightProbe.intensity;
		this._sh.array = this.lightProbe.sh.coefficients;

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

		const sh = uniformArray( lightProbe.sh.coefficients );
		const intensity = uniform( lightProbe.intensity );

		const RECIPROCAL_PI = float( 1 / Math.PI );

		const fragmentNode = Fn( () => {

			const irradiance = getShIrradianceAt( normalWorld, sh );

			const outgoingLight = RECIPROCAL_PI.mul( irradiance ).mul( intensity );

			return vec4( outgoingLight, 1.0 );

		} )();

		const material = new NodeMaterial();
		material.fragmentNode = fragmentNode;

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

		this._intensity = intensity;
		this._sh = sh;

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

		this._intensity.value = this.lightProbe.intensity;
		this._sh.array = this.lightProbe.sh.coefficients;

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

		this._intensity.value = this.lightProbe.intensity;
		this._sh.array = this.lightProbe.sh.coefficients;

	}
```
</details>


---