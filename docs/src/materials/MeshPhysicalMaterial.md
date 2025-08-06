[⬅️ Back to Table of Contents](../../index.md)

# 📄 `MeshPhysicalMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 5 |
| 🧱 Classes | 1 |
| 📦 Imports | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/MeshPhysicalMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Vector2` | `../math/Vector2.js` |
| `MeshStandardMaterial` | `./MeshStandardMaterial.js` |
| `Color` | `../math/Color.js` |
| `clamp` | `../math/MathUtils.js` |


---

## Functions

### `MeshPhysicalMaterial.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.clearcoatNormalScale.copy`
- `this.sheenColor.copy`
- `this.attenuationColor.copy`
- `this.specularColor.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.defines = {

			'STANDARD': '',
			'PHYSICAL': ''

		};

		this.anisotropy = source.anisotropy;
		this.anisotropyRotation = source.anisotropyRotation;
		this.anisotropyMap = source.anisotropyMap;

		this.clearcoat = source.clearcoat;
		this.clearcoatMap = source.clearcoatMap;
		this.clearcoatRoughness = source.clearcoatRoughness;
		this.clearcoatRoughnessMap = source.clearcoatRoughnessMap;
		this.clearcoatNormalMap = source.clearcoatNormalMap;
		this.clearcoatNormalScale.copy( source.clearcoatNormalScale );

		this.dispersion = source.dispersion;
		this.ior = source.ior;

		this.iridescence = source.iridescence;
		this.iridescenceMap = source.iridescenceMap;
		this.iridescenceIOR = source.iridescenceIOR;
		this.iridescenceThicknessRange = [ ...source.iridescenceThicknessRange ];
		this.iridescenceThicknessMap = source.iridescenceThicknessMap;

		this.sheen = source.sheen;
		this.sheenColor.copy( source.sheenColor );
		this.sheenColorMap = source.sheenColorMap;
		this.sheenRoughness = source.sheenRoughness;
		this.sheenRoughnessMap = source.sheenRoughnessMap;

		this.transmission = source.transmission;
		this.transmissionMap = source.transmissionMap;

		this.thickness = source.thickness;
		this.thicknessMap = source.thicknessMap;
		this.attenuationDistance = source.attenuationDistance;
		this.attenuationColor.copy( source.attenuationColor );

		this.specularIntensity = source.specularIntensity;
		this.specularIntensityMap = source.specularIntensityMap;
		this.specularColor.copy( source.specularColor );
		this.specularColorMap = source.specularColorMap;

		return this;

	}
```
</details>

### `get(): number`

**Returns:** `number`

**Calls:**

- `clamp (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
function () {

				return ( clamp( 2.5 * ( this.ior - 1 ) / ( this.ior + 1 ), 0, 1 ) );

			}
```
</details>

### `set(reflectivity: any): void`

**Parameters:**

- **`reflectivity`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( reflectivity ) {

				this.ior = ( 1 + 0.4 * reflectivity ) / ( 1 - 0.4 * reflectivity );

			}
```
</details>

### `get(): number`

**Returns:** `number`

**Calls:**

- `clamp (from ../math/MathUtils.js)`

<details><summary>Code</summary>

```typescript
function () {

				return ( clamp( 2.5 * ( this.ior - 1 ) / ( this.ior + 1 ), 0, 1 ) );

			}
```
</details>

### `set(reflectivity: any): void`

**Parameters:**

- **`reflectivity`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
function ( reflectivity ) {

				this.ior = ( 1 + 0.4 * reflectivity ) / ( 1 - 0.4 * reflectivity );

			}
```
</details>


---

## Classes

### `MeshPhysicalMaterial`

<details><summary>Class Code</summary>

```ts
class MeshPhysicalMaterial extends MeshStandardMaterial {

	/**
	 * Constructs a new mesh physical material.
	 *
	 * @param {Object} [parameters] - An object with one or more properties
	 * defining the material's appearance. Any property of the material
	 * (including any property from inherited materials) can be passed
	 * in here. Color values can be passed any type of value accepted
	 * by {@link Color#set}.
	 */
	constructor( parameters ) {

		super();

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isMeshPhysicalMaterial = true;

		this.defines = {

			'STANDARD': '',
			'PHYSICAL': ''

		};

		this.type = 'MeshPhysicalMaterial';

		/**
		 * The rotation of the anisotropy in tangent, bitangent space, measured in radians
		 * counter-clockwise from the tangent. When `anisotropyMap` is present, this
		 * property provides additional rotation to the vectors in the texture.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.anisotropyRotation = 0;

		/**
		 * Red and green channels represent the anisotropy direction in `[-1, 1]` tangent,
		 * bitangent space, to be rotated by `anisotropyRotation`. The blue channel
		 * contains strength as `[0, 1]` to be multiplied by `anisotropy`.
		 *
		 * @type {?Texture}
		 * @default null
		 */
		this.anisotropyMap = null;

		/**
		 * The red channel of this texture is multiplied against `clearcoat`,
		 * for per-pixel control over a coating's intensity.
		 *
		 * @type {?Texture}
		 * @default null
		 */
		this.clearcoatMap = null;

		/**
		 * Roughness of the clear coat layer, from `0.0` to `1.0`.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.clearcoatRoughness = 0.0;

		/**
		 * The green channel of this texture is multiplied against
		 * `clearcoatRoughness`, for per-pixel control over a coating's roughness.
		 *
		 * @type {?Texture}
		 * @default null
		 */
		this.clearcoatRoughnessMap = null;

		/**
		 * How much `clearcoatNormalMap` affects the clear coat layer, from
		 * `(0,0)` to `(1,1)`.
		 *
		 * @type {Vector2}
		 * @default (1,1)
		 */
		this.clearcoatNormalScale = new Vector2( 1, 1 );

		/**
		 * Can be used to enable independent normals for the clear coat layer.
		 *
		 * @type {?Texture}
		 * @default null
		 */
		this.clearcoatNormalMap = null;

		/**
		 * Index-of-refraction for non-metallic materials, from `1.0` to `2.333`.
		 *
		 * @type {number}
		 * @default 1.5
		 */
		this.ior = 1.5;

		/**
		 * Degree of reflectivity, from `0.0` to `1.0`. Default is `0.5`, which
		 * corresponds to an index-of-refraction of `1.5`.
		 *
		 * This models the reflectivity of non-metallic materials. It has no effect
		 * when `metalness` is `1.0`
		 *
		 * @name MeshPhysicalMaterial#reflectivity
		 * @type {number}
		 * @default 0.5
		 */
		Object.defineProperty( this, 'reflectivity', {
			get: function () {

				return ( clamp( 2.5 * ( this.ior - 1 ) / ( this.ior + 1 ), 0, 1 ) );

			},
			set: function ( reflectivity ) {

				this.ior = ( 1 + 0.4 * reflectivity ) / ( 1 - 0.4 * reflectivity );

			}
		} );

		/**
		 * The red channel of this texture is multiplied against `iridescence`, for per-pixel
		 * control over iridescence.
		 *
		 * @type {?Texture}
		 * @default null
		 */
		this.iridescenceMap = null;

		/**
		 * Strength of the iridescence RGB color shift effect, represented by an index-of-refraction.
		 * Between `1.0` to `2.333`.
		 *
		 * @type {number}
		 * @default 1.3
		 */
		this.iridescenceIOR = 1.3;

		/**
		 *Array of exactly 2 elements, specifying minimum and maximum thickness of the iridescence layer.
		 Thickness of iridescence layer has an equivalent effect of the one `thickness` has on `ior`.
		 *
		 * @type {Array<number,number>}
		 * @default [100,400]
		 */
		this.iridescenceThicknessRange = [ 100, 400 ];

		/**
		 * A texture that defines the thickness of the iridescence layer, stored in the green channel.
		 * Minimum and maximum values of thickness are defined by `iridescenceThicknessRange` array:
		 * - `0.0` in the green channel will result in thickness equal to first element of the array.
		 * - `1.0` in the green channel will result in thickness equal to second element of the array.
		 * - Values in-between will linearly interpolate between the elements of the array.
		 *
		 * @type {?Texture}
		 * @default null
		 */
		this.iridescenceThicknessMap = null;

		/**
		 * The sheen tint.
		 *
		 * @type {Color}
		 * @default (0,0,0)
		 */
		this.sheenColor = new Color( 0x000000 );

		/**
		 * The RGB channels of this texture are multiplied against  `sheenColor`, for per-pixel control
		 * over sheen tint.
		 *
		 * @type {?Texture}
		 * @default null
		 */
		this.sheenColorMap = null;

		/**
		 * Roughness of the sheen layer, from `0.0` to `1.0`.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.sheenRoughness = 1.0;

		/**
		 * The alpha channel of this texture is multiplied against `sheenRoughness`, for per-pixel control
		 * over sheen roughness.
		 *
		 * @type {?Texture}
		 * @default null
		 */
		this.sheenRoughnessMap = null;

		/**
		 * The red channel of this texture is multiplied against `transmission`, for per-pixel control over
		 * optical transparency.
		 *
		 * @type {?Texture}
		 * @default null
		 */
		this.transmissionMap = null;

		/**
		 * The thickness of the volume beneath the surface. The value is given in the
		 * coordinate space of the mesh. If the value is `0` the material is
		 * thin-walled. Otherwise the material is a volume boundary.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.thickness = 0;

		/**
		 * A texture that defines the thickness, stored in the green channel. This will
		 * be multiplied by `thickness`.
		 *
		 * @type {?Texture}
		 * @default null
		 */
		this.thicknessMap = null;

		/**
		 * Density of the medium given as the average distance that light travels in
		 * the medium before interacting with a particle. The value is given in world
		 * space units, and must be greater than zero.
		 *
		 * @type {number}
		 * @default Infinity
		 */
		this.attenuationDistance = Infinity;

		/**
		 * The color that white light turns into due to absorption when reaching the
		 * attenuation distance.
		 *
		 * @type {Color}
		 * @default (1,1,1)
		 */
		this.attenuationColor = new Color( 1, 1, 1 );

		/**
		 * A float that scales the amount of specular reflection for non-metals only.
		 * When set to zero, the model is effectively Lambertian. From `0.0` to `1.0`.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.specularIntensity = 1.0;

		/**
		 * The alpha channel of this texture is multiplied against `specularIntensity`,
		 * for per-pixel control over specular intensity.
		 *
		 * @type {?Texture}
		 * @default null
		 */
		this.specularIntensityMap = null;

		/**
		 * Tints the specular reflection at normal incidence for non-metals only.
		 *
		 * @type {Color}
		 * @default (1,1,1)
		 */
		this.specularColor = new Color( 1, 1, 1 );

		/**
		 * The RGB channels of this texture are multiplied against `specularColor`,
		 * for per-pixel control over specular color.
		 *
		 * @type {?Texture}
		 * @default null
		 */
		this.specularColorMap = null;

		this._anisotropy = 0;
		this._clearcoat = 0;
		this._dispersion = 0;
		this._iridescence = 0;
		this._sheen = 0.0;
		this._transmission = 0;

		this.setValues( parameters );

	}

	/**
	 * The anisotropy strength.
	 *
	 * @type {number}
	 * @default 0
	 */
	get anisotropy() {

		return this._anisotropy;

	}

	set anisotropy( value ) {

		if ( this._anisotropy > 0 !== value > 0 ) {

			this.version ++;

		}

		this._anisotropy = value;

	}

	/**
	 * Represents the intensity of the clear coat layer, from `0.0` to `1.0`. Use
	 * clear coat related properties to enable multilayer materials that have a
	 * thin translucent layer over the base layer.
	 *
	 * @type {number}
	 * @default 0
	 */
	get clearcoat() {

		return this._clearcoat;

	}

	set clearcoat( value ) {

		if ( this._clearcoat > 0 !== value > 0 ) {

			this.version ++;

		}

		this._clearcoat = value;

	}
	/**
	 * The intensity of the iridescence layer, simulating RGB color shift based on the angle between
	 * the surface and the viewer, from `0.0` to `1.0`.
	 *
	 * @type {number}
	 * @default 0
	 */
	get iridescence() {

		return this._iridescence;

	}

	set iridescence( value ) {

		if ( this._iridescence > 0 !== value > 0 ) {

			this.version ++;

		}

		this._iridescence = value;

	}

	/**
	 * Defines the strength of the angular separation of colors (chromatic aberration) transmitting
	 * through a relatively clear volume. Any value zero or larger is valid, the typical range of
	 * realistic values is `[0, 1]`. This property can be only be used with transmissive objects.
	 *
	 * @type {number}
	 * @default 0
	 */
	get dispersion() {

		return this._dispersion;

	}

	set dispersion( value ) {

		if ( this._dispersion > 0 !== value > 0 ) {

			this.version ++;

		}

		this._dispersion = value;

	}

	/**
	 * The intensity of the sheen layer, from `0.0` to `1.0`.
	 *
	 * @type {number}
	 * @default 0
	 */
	get sheen() {

		return this._sheen;

	}

	set sheen( value ) {

		if ( this._sheen > 0 !== value > 0 ) {

			this.version ++;

		}

		this._sheen = value;

	}

	/**
	 * Degree of transmission (or optical transparency), from `0.0` to `1.0`.
	 *
	 * Thin, transparent or semitransparent, plastic or glass materials remain
	 * largely reflective even if they are fully transmissive. The transmission
	 * property can be used to model these materials.
	 *
	 * When transmission is non-zero, `opacity` should be  set to `1`.
	 *
	 * @type {number}
	 * @default 0
	 */
	get transmission() {

		return this._transmission;

	}

	set transmission( value ) {

		if ( this._transmission > 0 !== value > 0 ) {

			this.version ++;

		}

		this._transmission = value;

	}

	copy( source ) {

		super.copy( source );

		this.defines = {

			'STANDARD': '',
			'PHYSICAL': ''

		};

		this.anisotropy = source.anisotropy;
		this.anisotropyRotation = source.anisotropyRotation;
		this.anisotropyMap = source.anisotropyMap;

		this.clearcoat = source.clearcoat;
		this.clearcoatMap = source.clearcoatMap;
		this.clearcoatRoughness = source.clearcoatRoughness;
		this.clearcoatRoughnessMap = source.clearcoatRoughnessMap;
		this.clearcoatNormalMap = source.clearcoatNormalMap;
		this.clearcoatNormalScale.copy( source.clearcoatNormalScale );

		this.dispersion = source.dispersion;
		this.ior = source.ior;

		this.iridescence = source.iridescence;
		this.iridescenceMap = source.iridescenceMap;
		this.iridescenceIOR = source.iridescenceIOR;
		this.iridescenceThicknessRange = [ ...source.iridescenceThicknessRange ];
		this.iridescenceThicknessMap = source.iridescenceThicknessMap;

		this.sheen = source.sheen;
		this.sheenColor.copy( source.sheenColor );
		this.sheenColorMap = source.sheenColorMap;
		this.sheenRoughness = source.sheenRoughness;
		this.sheenRoughnessMap = source.sheenRoughnessMap;

		this.transmission = source.transmission;
		this.transmissionMap = source.transmissionMap;

		this.thickness = source.thickness;
		this.thicknessMap = source.thicknessMap;
		this.attenuationDistance = source.attenuationDistance;
		this.attenuationColor.copy( source.attenuationColor );

		this.specularIntensity = source.specularIntensity;
		this.specularIntensityMap = source.specularIntensityMap;
		this.specularColor.copy( source.specularColor );
		this.specularColorMap = source.specularColorMap;

		return this;

	}

}
```
</details>

#### Methods

##### `copy(source: any): this`

<details><summary>Code</summary>

```ts
copy( source ) {

		super.copy( source );

		this.defines = {

			'STANDARD': '',
			'PHYSICAL': ''

		};

		this.anisotropy = source.anisotropy;
		this.anisotropyRotation = source.anisotropyRotation;
		this.anisotropyMap = source.anisotropyMap;

		this.clearcoat = source.clearcoat;
		this.clearcoatMap = source.clearcoatMap;
		this.clearcoatRoughness = source.clearcoatRoughness;
		this.clearcoatRoughnessMap = source.clearcoatRoughnessMap;
		this.clearcoatNormalMap = source.clearcoatNormalMap;
		this.clearcoatNormalScale.copy( source.clearcoatNormalScale );

		this.dispersion = source.dispersion;
		this.ior = source.ior;

		this.iridescence = source.iridescence;
		this.iridescenceMap = source.iridescenceMap;
		this.iridescenceIOR = source.iridescenceIOR;
		this.iridescenceThicknessRange = [ ...source.iridescenceThicknessRange ];
		this.iridescenceThicknessMap = source.iridescenceThicknessMap;

		this.sheen = source.sheen;
		this.sheenColor.copy( source.sheenColor );
		this.sheenColorMap = source.sheenColorMap;
		this.sheenRoughness = source.sheenRoughness;
		this.sheenRoughnessMap = source.sheenRoughnessMap;

		this.transmission = source.transmission;
		this.transmissionMap = source.transmissionMap;

		this.thickness = source.thickness;
		this.thicknessMap = source.thicknessMap;
		this.attenuationDistance = source.attenuationDistance;
		this.attenuationColor.copy( source.attenuationColor );

		this.specularIntensity = source.specularIntensity;
		this.specularIntensityMap = source.specularIntensityMap;
		this.specularColor.copy( source.specularColor );
		this.specularColorMap = source.specularColorMap;

		return this;

	}
```
</details>


---