[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Color4.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 3 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/renderers/common/Color4.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `../../math/Color.js` |


---

## Functions

### `Color4.set(r: string | number | Color, g: number, b: number, a: number): Color4`

**JSDoc:**
```typescript
/**
	 * Overwrites the default to honor alpha.
	 * You can also pass a single THREE.Color, hex or
	 * string argument to this method.
	 *
	 * @param {number|string|Color} r - The red value.
	 * @param {number} [g] - The green value.
	 * @param {number} [b] - The blue value.
	 * @param {number} [a=1] - The alpha value.
	 * @return {Color4} A reference to this object.
	 */
```

**Parameters:**

- **`r`** `string | number | Color`
- **`g`** `number`
- **`b`** `number`
- **`a`** `number`

**Returns:** `Color4`

**Calls:**

- `super.set`

<details><summary>Code</summary>

```typescript
set( r, g, b, a = 1 ) {

		this.a = a;

		return super.set( r, g, b );

	}
```
</details>

### `Color4.copy(color: Color4): Color4`

**JSDoc:**
```typescript
/**
	 * Overwrites the default to honor alpha.
	 *
	 * @param {Color4} color - The color to copy.
	 * @return {Color4} A reference to this object.
	 */
```

**Parameters:**

- **`color`** `Color4`

**Returns:** `Color4`

**Calls:**

- `super.copy`

<details><summary>Code</summary>

```typescript
copy( color ) {

		if ( color.a !== undefined ) this.a = color.a;

		return super.copy( color );

	}
```
</details>

### `Color4.clone(): Color4`

**JSDoc:**
```typescript
/**
	 * Overwrites the default to honor alpha.
	 *
	 * @return {Color4} The cloned color.
	 */
```

**Returns:** `Color4`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor( this.r, this.g, this.b, this.a );

	}
```
</details>


---

## Classes

### `Color4`

<details><summary>Class Code</summary>

```ts
class Color4 extends Color {

	/**
	 * Constructs a new four-component color.
	 * You can also pass a single THREE.Color, hex or
	 * string argument to this constructor.
	 *
	 * @param {number|string} [r=1] - The red value.
	 * @param {number} [g=1] - The green value.
	 * @param {number} [b=1] - The blue value.
	 * @param {number} [a=1] - The alpha value.
	 */
	constructor( r, g, b, a = 1 ) {

		super( r, g, b );

		this.a = a;

	}

	/**
	 * Overwrites the default to honor alpha.
	 * You can also pass a single THREE.Color, hex or
	 * string argument to this method.
	 *
	 * @param {number|string|Color} r - The red value.
	 * @param {number} [g] - The green value.
	 * @param {number} [b] - The blue value.
	 * @param {number} [a=1] - The alpha value.
	 * @return {Color4} A reference to this object.
	 */
	set( r, g, b, a = 1 ) {

		this.a = a;

		return super.set( r, g, b );

	}

	/**
	 * Overwrites the default to honor alpha.
	 *
	 * @param {Color4} color - The color to copy.
	 * @return {Color4} A reference to this object.
	 */
	copy( color ) {

		if ( color.a !== undefined ) this.a = color.a;

		return super.copy( color );

	}

	/**
	 * Overwrites the default to honor alpha.
	 *
	 * @return {Color4} The cloned color.
	 */
	clone() {

		return new this.constructor( this.r, this.g, this.b, this.a );

	}

}
```
</details>

#### Methods

##### `set(r: string | number | Color, g: number, b: number, a: number): Color4`

<details><summary>Code</summary>

```ts
set( r, g, b, a = 1 ) {

		this.a = a;

		return super.set( r, g, b );

	}
```
</details>

##### `copy(color: Color4): Color4`

<details><summary>Code</summary>

```ts
copy( color ) {

		if ( color.a !== undefined ) this.a = color.a;

		return super.copy( color );

	}
```
</details>

##### `clone(): Color4`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor( this.r, this.g, this.b, this.a );

	}
```
</details>


---