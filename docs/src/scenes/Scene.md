[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Scene.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/scenes/Scene.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Object3D` | `../core/Object3D.js` |
| `Euler` | `../math/Euler.js` |


---

## Functions

### `Scene.copy(source: any, recursive: any): this`

**Parameters:**

- **`source`** `any`
- **`recursive`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `source.background.clone`
- `source.environment.clone`
- `source.fog.clone`
- `this.backgroundRotation.copy`
- `this.environmentRotation.copy`
- `source.overrideMaterial.clone`

<details><summary>Code</summary>

```typescript
copy( source, recursive ) {

		super.copy( source, recursive );

		if ( source.background !== null ) this.background = source.background.clone();
		if ( source.environment !== null ) this.environment = source.environment.clone();
		if ( source.fog !== null ) this.fog = source.fog.clone();

		this.backgroundBlurriness = source.backgroundBlurriness;
		this.backgroundIntensity = source.backgroundIntensity;
		this.backgroundRotation.copy( source.backgroundRotation );

		this.environmentIntensity = source.environmentIntensity;
		this.environmentRotation.copy( source.environmentRotation );

		if ( source.overrideMaterial !== null ) this.overrideMaterial = source.overrideMaterial.clone();

		this.matrixAutoUpdate = source.matrixAutoUpdate;

		return this;

	}
```
</details>

### `Scene.toJSON(meta: any): any`

**Parameters:**

- **`meta`** `any`

**Returns:** `any`

**Calls:**

- `super.toJSON`
- `this.fog.toJSON`
- `this.backgroundRotation.toArray`
- `this.environmentRotation.toArray`

<details><summary>Code</summary>

```typescript
toJSON( meta ) {

		const data = super.toJSON( meta );

		if ( this.fog !== null ) data.object.fog = this.fog.toJSON();

		if ( this.backgroundBlurriness > 0 ) data.object.backgroundBlurriness = this.backgroundBlurriness;
		if ( this.backgroundIntensity !== 1 ) data.object.backgroundIntensity = this.backgroundIntensity;
		data.object.backgroundRotation = this.backgroundRotation.toArray();

		if ( this.environmentIntensity !== 1 ) data.object.environmentIntensity = this.environmentIntensity;
		data.object.environmentRotation = this.environmentRotation.toArray();

		return data;

	}
```
</details>


---

## Classes

### `Scene`

<details><summary>Class Code</summary>

```ts
class Scene extends Object3D {

	/**
	 * Constructs a new scene.
	 */
	constructor() {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isScene = true;

		this.type = 'Scene';

		/**
		 * Defines the background of the scene. Valid inputs are:
		 *
		 * - A color for defining a uniform colored background.
		 * - A texture for defining a (flat) textured background.
		 * - Cube textures or equirectangular textures for defining a skybox.
		 *
		 * @type {?(Color|Texture)}
		 * @default null
		 */
		this.background = null;

		/**
		 * Sets the environment map for all physical materials in the scene. However,
		 * it's not possible to overwrite an existing texture assigned to the `envMap`
		 * material property.
		 *
		 * @type {?Texture}
		 * @default null
		 */
		this.environment = null;

		/**
		 * A fog instance defining the type of fog that affects everything
		 * rendered in the scene.
		 *
		 * @type {?(Fog|FogExp2)}
		 * @default null
		 */
		this.fog = null;

		/**
		 * Sets the blurriness of the background. Only influences environment maps
		 * assigned to {@link Scene#background}. Valid input is a float between `0`
		 * and `1`.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.backgroundBlurriness = 0;

		/**
		 * Attenuates the color of the background. Only applies to background textures.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.backgroundIntensity = 1;

		/**
		 * The rotation of the background in radians. Only influences environment maps
		 * assigned to {@link Scene#background}.
		 *
		 * @type {Euler}
		 * @default (0,0,0)
		 */
		this.backgroundRotation = new Euler();

		/**
		 * Attenuates the color of the environment. Only influences environment maps
		 * assigned to {@link Scene#environment}.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.environmentIntensity = 1;

		/**
		 * The rotation of the environment map in radians. Only influences physical materials
		 * in the scene when {@link Scene#environment} is used.
		 *
		 * @type {Euler}
		 * @default (0,0,0)
		 */
		this.environmentRotation = new Euler();

		/**
		 * Forces everything in the scene to be rendered with the defined material. It is possible
		 * to exclude materials from override by setting {@link Material#allowOverride} to `false`.
		 *
		 * @type {?Material}
		 * @default null
		 */
		this.overrideMaterial = null;

		if ( typeof __THREE_DEVTOOLS__ !== 'undefined' ) {

			__THREE_DEVTOOLS__.dispatchEvent( new CustomEvent( 'observe', { detail: this } ) );

		}

	}

	copy( source, recursive ) {

		super.copy( source, recursive );

		if ( source.background !== null ) this.background = source.background.clone();
		if ( source.environment !== null ) this.environment = source.environment.clone();
		if ( source.fog !== null ) this.fog = source.fog.clone();

		this.backgroundBlurriness = source.backgroundBlurriness;
		this.backgroundIntensity = source.backgroundIntensity;
		this.backgroundRotation.copy( source.backgroundRotation );

		this.environmentIntensity = source.environmentIntensity;
		this.environmentRotation.copy( source.environmentRotation );

		if ( source.overrideMaterial !== null ) this.overrideMaterial = source.overrideMaterial.clone();

		this.matrixAutoUpdate = source.matrixAutoUpdate;

		return this;

	}

	toJSON( meta ) {

		const data = super.toJSON( meta );

		if ( this.fog !== null ) data.object.fog = this.fog.toJSON();

		if ( this.backgroundBlurriness > 0 ) data.object.backgroundBlurriness = this.backgroundBlurriness;
		if ( this.backgroundIntensity !== 1 ) data.object.backgroundIntensity = this.backgroundIntensity;
		data.object.backgroundRotation = this.backgroundRotation.toArray();

		if ( this.environmentIntensity !== 1 ) data.object.environmentIntensity = this.environmentIntensity;
		data.object.environmentRotation = this.environmentRotation.toArray();

		return data;

	}

}
```
</details>

#### Methods

##### `copy(source: any, recursive: any): this`

<details><summary>Code</summary>

```ts
copy( source, recursive ) {

		super.copy( source, recursive );

		if ( source.background !== null ) this.background = source.background.clone();
		if ( source.environment !== null ) this.environment = source.environment.clone();
		if ( source.fog !== null ) this.fog = source.fog.clone();

		this.backgroundBlurriness = source.backgroundBlurriness;
		this.backgroundIntensity = source.backgroundIntensity;
		this.backgroundRotation.copy( source.backgroundRotation );

		this.environmentIntensity = source.environmentIntensity;
		this.environmentRotation.copy( source.environmentRotation );

		if ( source.overrideMaterial !== null ) this.overrideMaterial = source.overrideMaterial.clone();

		this.matrixAutoUpdate = source.matrixAutoUpdate;

		return this;

	}
```
</details>

##### `toJSON(meta: any): any`

<details><summary>Code</summary>

```ts
toJSON( meta ) {

		const data = super.toJSON( meta );

		if ( this.fog !== null ) data.object.fog = this.fog.toJSON();

		if ( this.backgroundBlurriness > 0 ) data.object.backgroundBlurriness = this.backgroundBlurriness;
		if ( this.backgroundIntensity !== 1 ) data.object.backgroundIntensity = this.backgroundIntensity;
		data.object.backgroundRotation = this.backgroundRotation.toArray();

		if ( this.environmentIntensity !== 1 ) data.object.environmentIntensity = this.environmentIntensity;
		data.object.environmentRotation = this.environmentRotation.toArray();

		return data;

	}
```
</details>


---