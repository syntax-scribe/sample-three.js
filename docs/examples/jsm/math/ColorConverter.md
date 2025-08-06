[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `ColorConverter.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 2 |
| 🧱 Classes | 1 |
| 📦 Imports | 1 |
| 📊 Variables & Constants | 1 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/math/ColorConverter.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `MathUtils` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_hsl` | `{}` | let/var | `{}` | ✗ |


---

## Functions

### `ColorConverter.setHSV(color: Color, h: number, s: number, v: number): Color`

**JSDoc:**
```typescript
/**
	 * Sets the given HSV color definition to the given color object.
	 *
	 * @param {Color} color - The color to set.
	 * @param {number} h - The hue.
	 * @param {number} s - The saturation.
	 * @param {number} v - The value.
	 * @return {Color} The update color.
	 */
```

**Parameters:**

- **`color`** `Color`
- **`h`** `number`
- **`s`** `number`
- **`v`** `number`

**Returns:** `Color`

**Calls:**

- `MathUtils.euclideanModulo`
- `MathUtils.clamp`
- `color.setHSL`

**Internal Comments:**
```
// https://gist.github.com/xpansive/1337890#file-index-js (x3)
```

<details><summary>Code</summary>

```typescript
static setHSV( color, h, s, v ) {

		// https://gist.github.com/xpansive/1337890#file-index-js

		h = MathUtils.euclideanModulo( h, 1 );
		s = MathUtils.clamp( s, 0, 1 );
		v = MathUtils.clamp( v, 0, 1 );

		return color.setHSL( h, ( s * v ) / ( ( h = ( 2 - s ) * v ) < 1 ? h : ( 2 - h ) ), h * 0.5 );

	}
```
</details>

### `ColorConverter.getHSV(color: Color, target: { h: number; s: number; v: number; }): { h: number; s: number; v: number; }`

**JSDoc:**
```typescript
/**
	 * Returns a HSV color representation of the given color object.
	 *
	 * @param {Color} color - The color to get HSV values from.
	 * @param {{h:number,s:number,v:number}} target - The target object that is used to store the method's result.
	 * @return {{h:number,s:number,v:number}} The HSV color.
	 */
```

**Parameters:**

- **`color`** `Color`
- **`target`** `{ h: number; s: number; v: number; }`

**Returns:** `{ h: number; s: number; v: number; }`

**Calls:**

- `color.getHSL`

**Internal Comments:**
```
// based on https://gist.github.com/xpansive/1337890#file-index-js (x4)
```

<details><summary>Code</summary>

```typescript
static getHSV( color, target ) {

		color.getHSL( _hsl );

		// based on https://gist.github.com/xpansive/1337890#file-index-js
		_hsl.s *= ( _hsl.l < 0.5 ) ? _hsl.l : ( 1 - _hsl.l );

		target.h = _hsl.h;
		target.s = 2 * _hsl.s / ( _hsl.l + _hsl.s );
		target.v = _hsl.l + _hsl.s;

		return target;

	}
```
</details>


---

## Classes

### `ColorConverter`

<details><summary>Class Code</summary>

```ts
class ColorConverter {

	/**
	 * Sets the given HSV color definition to the given color object.
	 *
	 * @param {Color} color - The color to set.
	 * @param {number} h - The hue.
	 * @param {number} s - The saturation.
	 * @param {number} v - The value.
	 * @return {Color} The update color.
	 */
	static setHSV( color, h, s, v ) {

		// https://gist.github.com/xpansive/1337890#file-index-js

		h = MathUtils.euclideanModulo( h, 1 );
		s = MathUtils.clamp( s, 0, 1 );
		v = MathUtils.clamp( v, 0, 1 );

		return color.setHSL( h, ( s * v ) / ( ( h = ( 2 - s ) * v ) < 1 ? h : ( 2 - h ) ), h * 0.5 );

	}

	/**
	 * Returns a HSV color representation of the given color object.
	 *
	 * @param {Color} color - The color to get HSV values from.
	 * @param {{h:number,s:number,v:number}} target - The target object that is used to store the method's result.
	 * @return {{h:number,s:number,v:number}} The HSV color.
	 */
	static getHSV( color, target ) {

		color.getHSL( _hsl );

		// based on https://gist.github.com/xpansive/1337890#file-index-js
		_hsl.s *= ( _hsl.l < 0.5 ) ? _hsl.l : ( 1 - _hsl.l );

		target.h = _hsl.h;
		target.s = 2 * _hsl.s / ( _hsl.l + _hsl.s );
		target.v = _hsl.l + _hsl.s;

		return target;

	}

}
```
</details>

#### Methods

##### `setHSV(color: Color, h: number, s: number, v: number): Color`

<details><summary>Code</summary>

```ts
static setHSV( color, h, s, v ) {

		// https://gist.github.com/xpansive/1337890#file-index-js

		h = MathUtils.euclideanModulo( h, 1 );
		s = MathUtils.clamp( s, 0, 1 );
		v = MathUtils.clamp( v, 0, 1 );

		return color.setHSL( h, ( s * v ) / ( ( h = ( 2 - s ) * v ) < 1 ? h : ( 2 - h ) ), h * 0.5 );

	}
```
</details>

##### `getHSV(color: Color, target: { h: number; s: number; v: number; }): { h: number; s: number; v: number; }`

<details><summary>Code</summary>

```ts
static getHSV( color, target ) {

		color.getHSL( _hsl );

		// based on https://gist.github.com/xpansive/1337890#file-index-js
		_hsl.s *= ( _hsl.l < 0.5 ) ? _hsl.l : ( 1 - _hsl.l );

		target.h = _hsl.h;
		target.s = 2 * _hsl.s / ( _hsl.l + _hsl.s );
		target.v = _hsl.l + _hsl.s;

		return target;

	}
```
</details>


---