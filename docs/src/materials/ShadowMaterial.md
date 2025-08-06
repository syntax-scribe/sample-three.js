[⬅️ Back to Table of Contents](../../index.md)

# 📄 `ShadowMaterial.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 1 |
| 🧱 Classes | 1 |
| 📦 Imports | 2 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/materials/ShadowMaterial.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Material` | `./Material.js` |
| `Color` | `../math/Color.js` |


---

## Functions

### `ShadowMaterial.copy(source: any): this`

**Parameters:**

- **`source`** `any`

**Returns:** `this`

**Calls:**

- `super.copy`
- `this.color.copy`

<details><summary>Code</summary>

```typescript
copy( source ) {

		super.copy( source );

		this.color.copy( source.color );

		this.fog = source.fog;

		return this;

	}
```
</details>


---

## Classes

### `ShadowMaterial`

<details><summary>Class Code</summary>

```ts
class ShadowMaterial extends Material {

	/**
	 * Constructs a new shadow material.
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
		this.isShadowMaterial = true;

		this.type = 'ShadowMaterial';

		/**
		 * Color of the material.
		 *
		 * @type {Color}
		 * @default (0,0,0)
		 */
		this.color = new Color( 0x000000 );

		/**
		 * Overwritten since shadow materials are transparent
		 * by default.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.transparent = true;

		/**
		 * Whether the material is affected by fog or not.
		 *
		 * @type {boolean}
		 * @default true
		 */
		this.fog = true;

		this.setValues( parameters );

	}

	copy( source ) {

		super.copy( source );

		this.color.copy( source.color );

		this.fog = source.fog;

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

		this.color.copy( source.color );

		this.fog = source.fog;

		return this;

	}
```
</details>


---