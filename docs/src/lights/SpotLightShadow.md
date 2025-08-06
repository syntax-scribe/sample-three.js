[⬅️ Back to Table of Contents](../../index.md)

# 📄 `SpotLightShadow.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/lights/SpotLightShadow.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `LightShadow` | `./LightShadow.js` |
| `RAD2DEG` | `../math/MathUtils.js` |
| `PerspectiveCamera` | `../cameras/PerspectiveCamera.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `camera` | `Camera` | let/var | `this.camera` | ✗ |
| `fov` | `number` | let/var | `RAD2DEG * 2 * light.angle * this.focus` | ✗ |
| `aspect` | `number` | let/var | `( this.mapSize.width / this.mapSize.height ) * this.aspect` | ✗ |
| `far` | `any` | let/var | `light.distance \|\| camera.far` | ✗ |


---

## Functions

### `SpotLightShadow.updateMatrices(light: any): void`

**Parameters:**

- **`light`** `any`

**Returns:** `void`

**Calls:**

- `camera.updateProjectionMatrix`
- `super.updateMatrices`

<details><summary>Code</summary>

```typescript
updateMatrices( light ) {

		const camera = this.camera;

		const fov = RAD2DEG * 2 * light.angle * this.focus;
		const aspect = ( this.mapSize.width / this.mapSize.height ) * this.aspect;
		const far = light.distance || camera.far;

		if ( fov !== camera.fov || aspect !== camera.aspect || far !== camera.far ) {

			camera.fov = fov;
			camera.aspect = aspect;
			camera.far = far;
			camera.updateProjectionMatrix();

		}

		super.updateMatrices( light );

	}
```
</details>

### `SpotLightShadow.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.focus = source.focus;

		return this;

	}
```
</details>


---

## Classes

### `SpotLightShadow`

<details><summary>Class Code</summary>

```ts
class SpotLightShadow extends LightShadow {

	/**
	 * Constructs a new spot light shadow.
	 */
	constructor() {

		super( new PerspectiveCamera( 50, 1, 0.5, 500 ) );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isSpotLightShadow = true;

		/**
		 * Used to focus the shadow camera. The camera's field of view is set as a
		 * percentage of the spotlight's field-of-view. Range is `[0, 1]`.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.focus = 1;

		/**
		 * Texture aspect ratio.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.aspect = 1;

	}

	updateMatrices( light ) {

		const camera = this.camera;

		const fov = RAD2DEG * 2 * light.angle * this.focus;
		const aspect = ( this.mapSize.width / this.mapSize.height ) * this.aspect;
		const far = light.distance || camera.far;

		if ( fov !== camera.fov || aspect !== camera.aspect || far !== camera.far ) {

			camera.fov = fov;
			camera.aspect = aspect;
			camera.far = far;
			camera.updateProjectionMatrix();

		}

		super.updateMatrices( light );

	}

	copy( source ) {

		super.copy( source );

		this.focus = source.focus;

		return this;

	}

}
```
</details>

#### Methods

##### `updateMatrices(light: any): void`

<details><summary>Code</summary>

```ts
updateMatrices( light ) {

		const camera = this.camera;

		const fov = RAD2DEG * 2 * light.angle * this.focus;
		const aspect = ( this.mapSize.width / this.mapSize.height ) * this.aspect;
		const far = light.distance || camera.far;

		if ( fov !== camera.fov || aspect !== camera.aspect || far !== camera.far ) {

			camera.fov = fov;
			camera.aspect = aspect;
			camera.far = far;
			camera.updateProjectionMatrix();

		}

		super.updateMatrices( light );

	}
```
</details>

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source );

		this.focus = source.focus;

		return this;

	}
```
</details>


---