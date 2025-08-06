[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Uniform.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 9 |
| 📦 Imports | 7 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/Uniform.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `../../math/Color.js` |
| `Matrix2` | `../../math/Matrix2.js` |
| `Matrix3` | `../../math/Matrix3.js` |
| `Matrix4` | `../../math/Matrix4.js` |
| `Vector2` | `../../math/Vector2.js` |
| `Vector3` | `../../math/Vector3.js` |
| `Vector4` | `../../math/Vector4.js` |


---

## Functions

### `Uniform.setValue(value: any): void`

**JSDoc:**
```typescript
/**
	 * Sets the uniform's value.
	 *
	 * @param {any} value - The value to set.
	 */
```

**Parameters:**

- **`value`** `any`

**Returns:** `void`

<details><summary>Code</summary>

```typescript
setValue( value ) {

		this.value = value;

	}
```
</details>

### `Uniform.getValue(): any`

**JSDoc:**
```typescript
/**
	 * Returns the uniform's value.
	 *
	 * @return {any} The value.
	 */
```

**Returns:** `any`

<details><summary>Code</summary>

```typescript
getValue() {

		return this.value;

	}
```
</details>


---

## Classes

### `Uniform`

<details><summary>Class Code</summary>

```ts
class Uniform {

	/**
	 * Constructs a new uniform.
	 *
	 * @param {string} name - The uniform's name.
	 * @param {any} value - The uniform's value.
	 */
	constructor( name, value ) {

		/**
		 * The uniform's name.
		 *
		 * @type {string}
		 */
		this.name = name;

		/**
		 * The uniform's value.
		 *
		 * @type {any}
		 */
		this.value = value;

		/**
		 * Used to build the uniform buffer according to the STD140 layout.
		 * Derived uniforms will set this property to a data type specific
		 * value.
		 *
		 * @type {number}
		 */
		this.boundary = 0;

		/**
		 * The item size. Derived uniforms will set this property to a data
		 * type specific value.
		 *
		 * @type {number}
		 */
		this.itemSize = 0;

		/**
		 * This property is set by {@link UniformsGroup} and marks
		 * the start position in the uniform buffer.
		 *
		 * @type {number}
		 */
		this.offset = 0;

	}

	/**
	 * Sets the uniform's value.
	 *
	 * @param {any} value - The value to set.
	 */
	setValue( value ) {

		this.value = value;

	}

	/**
	 * Returns the uniform's value.
	 *
	 * @return {any} The value.
	 */
	getValue() {

		return this.value;

	}

}
```
</details>

#### Methods

##### `setValue(value: any): void`

<details><summary>Code</summary>

```ts
setValue( value ) {

		this.value = value;

	}
```
</details>

##### `getValue(): any`

<details><summary>Code</summary>

```ts
getValue() {

		return this.value;

	}
```
</details>

### `NumberUniform`

<details><summary>Class Code</summary>

```ts
class NumberUniform extends Uniform {

	/**
	 * Constructs a new Number uniform.
	 *
	 * @param {string} name - The uniform's name.
	 * @param {number} value - The uniform's value.
	 */
	constructor( name, value = 0 ) {

		super( name, value );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isNumberUniform = true;

		this.boundary = 4;
		this.itemSize = 1;

	}

}
```
</details>

### `Vector2Uniform`

<details><summary>Class Code</summary>

```ts
class Vector2Uniform extends Uniform {

	/**
	 * Constructs a new Number uniform.
	 *
	 * @param {string} name - The uniform's name.
	 * @param {Vector2} value - The uniform's value.
	 */
	constructor( name, value = new Vector2() ) {

		super( name, value );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isVector2Uniform = true;

		this.boundary = 8;
		this.itemSize = 2;

	}

}
```
</details>

### `Vector3Uniform`

<details><summary>Class Code</summary>

```ts
class Vector3Uniform extends Uniform {

	/**
	 * Constructs a new Number uniform.
	 *
	 * @param {string} name - The uniform's name.
	 * @param {Vector3} value - The uniform's value.
	 */
	constructor( name, value = new Vector3() ) {

		super( name, value );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isVector3Uniform = true;

		this.boundary = 16;
		this.itemSize = 3;

	}

}
```
</details>

### `Vector4Uniform`

<details><summary>Class Code</summary>

```ts
class Vector4Uniform extends Uniform {

	/**
	 * Constructs a new Number uniform.
	 *
	 * @param {string} name - The uniform's name.
	 * @param {Vector4} value - The uniform's value.
	 */
	constructor( name, value = new Vector4() ) {

		super( name, value );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isVector4Uniform = true;

		this.boundary = 16;
		this.itemSize = 4;

	}

}
```
</details>

### `ColorUniform`

<details><summary>Class Code</summary>

```ts
class ColorUniform extends Uniform {

	/**
	 * Constructs a new Number uniform.
	 *
	 * @param {string} name - The uniform's name.
	 * @param {Color} value - The uniform's value.
	 */
	constructor( name, value = new Color() ) {

		super( name, value );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isColorUniform = true;

		this.boundary = 16;
		this.itemSize = 3;

	}

}
```
</details>

### `Matrix2Uniform`

<details><summary>Class Code</summary>

```ts
class Matrix2Uniform extends Uniform {

	/**
	 * Constructs a new Number uniform.
	 *
	 * @param {string} name - The uniform's name.
	 * @param {Matrix2} value - The uniform's value.
	 */
	constructor( name, value = new Matrix2() ) {

		super( name, value );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isMatrix2Uniform = true;

		this.boundary = 8;
		this.itemSize = 4;

	}

}
```
</details>

### `Matrix3Uniform`

<details><summary>Class Code</summary>

```ts
class Matrix3Uniform extends Uniform {

	/**
	 * Constructs a new Number uniform.
	 *
	 * @param {string} name - The uniform's name.
	 * @param {Matrix3} value - The uniform's value.
	 */
	constructor( name, value = new Matrix3() ) {

		super( name, value );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isMatrix3Uniform = true;

		this.boundary = 48;
		this.itemSize = 12;

	}

}
```
</details>

### `Matrix4Uniform`

<details><summary>Class Code</summary>

```ts
class Matrix4Uniform extends Uniform {

	/**
	 * Constructs a new Number uniform.
	 *
	 * @param {string} name - The uniform's name.
	 * @param {Matrix4} value - The uniform's value.
	 */
	constructor( name, value = new Matrix4() ) {

		super( name, value );

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isMatrix4Uniform = true;

		this.boundary = 64;
		this.itemSize = 16;

	}

}
```
</details>


---