[⬅️ Back to Table of Contents](../../index.md)

# 📄 `DepthTexture.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 6 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/textures/DepthTexture.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Source` | `./Source.js` |
| `Texture` | `./Texture.js` |
| `NearestFilter` | `../constants.js` |
| `UnsignedIntType` | `../constants.js` |
| `DepthFormat` | `../constants.js` |
| `DepthStencilFormat` | `../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `image` | `{ width: number; height: number; dept...` | let/var | `{ width: width, height: height, depth: depth }` | ✗ |


---

## Functions

### `DepthTexture.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `Object.assign`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.source = new Source( Object.assign( {}, source.image ) ); // see #30540
		this.compareFunction = source.compareFunction;

		return this;

	}
```
</details>

### `DepthTexture.toJSON(meta: any): any`

**Parameters:**

- **`meta`** `any`

**Returns:** `any`

**Calls:**

- `super.toJSON`

<details><summary>Code</summary>

```typescript
toJSON( meta ) {

		const data = super.toJSON( meta );

		if ( this.compareFunction !== null ) data.compareFunction = this.compareFunction;

		return data;

	}
```
</details>


---

## Classes

### `DepthTexture`

<details><summary>Class Code</summary>

```ts
class DepthTexture extends Texture {

	/**
	 * Constructs a new depth texture.
	 *
	 * @param {number} width - The width of the texture.
	 * @param {number} height - The height of the texture.
	 * @param {number} [type=UnsignedIntType] - The texture type.
	 * @param {number} [mapping=Texture.DEFAULT_MAPPING] - The texture mapping.
	 * @param {number} [wrapS=ClampToEdgeWrapping] - The wrapS value.
	 * @param {number} [wrapT=ClampToEdgeWrapping] - The wrapT value.
	 * @param {number} [magFilter=LinearFilter] - The mag filter value.
	 * @param {number} [minFilter=LinearFilter] - The min filter value.
	 * @param {number} [anisotropy=Texture.DEFAULT_ANISOTROPY] - The anisotropy value.
	 * @param {number} [format=DepthFormat] - The texture format.
	 * @param {number} [depth=1] - The depth of the texture.
	 */
	constructor( width, height, type = UnsignedIntType, mapping, wrapS, wrapT, magFilter = NearestFilter, minFilter = NearestFilter, anisotropy, format = DepthFormat, depth = 1 ) {

		if ( format !== DepthFormat && format !== DepthStencilFormat ) {

			throw new Error( 'DepthTexture format must be either THREE.DepthFormat or THREE.DepthStencilFormat' );

		}

		const image = { width: width, height: height, depth: depth };

		super( image, mapping, wrapS, wrapT, magFilter, minFilter, format, type, anisotropy );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isDepthTexture = true;

		/**
		 * If set to `true`, the texture is flipped along the vertical axis when
		 * uploaded to the GPU.
		 *
		 * Overwritten and set to `false` by default.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.flipY = false;

		/**
		 * Whether to generate mipmaps (if possible) for a texture.
		 *
		 * Overwritten and set to `false` by default.
		 *
		 * @type {boolean}
		 * @default false
		 */
		this.generateMipmaps = false;

		/**
		 * Code corresponding to the depth compare function.
		 *
		 * @type {?(NeverCompare|LessCompare|EqualCompare|LessEqualCompare|GreaterCompare|NotEqualCompare|GreaterEqualCompare|AlwaysCompare)}
		 * @default null
		 */
		this.compareFunction = null;

	}


	copy( source ) {

		super.copy( source );

		this.source = new Source( Object.assign( {}, source.image ) ); // see #30540
		this.compareFunction = source.compareFunction;

		return this;

	}

	toJSON( meta ) {

		const data = super.toJSON( meta );

		if ( this.compareFunction !== null ) data.compareFunction = this.compareFunction;

		return data;

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

		this.source = new Source( Object.assign( {}, source.image ) ); // see #30540
		this.compareFunction = source.compareFunction;

		return this;

	}
```
</details>

##### `toJSON(meta: any): any`

<details><summary>Code</summary>

```ts
toJSON( meta ) {

		const data = super.toJSON( meta );

		if ( this.compareFunction !== null ) data.compareFunction = this.compareFunction;

		return data;

	}
```
</details>


---