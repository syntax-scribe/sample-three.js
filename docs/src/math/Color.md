[⬅️ Back to Table of Contents](../../index.md)

# 📄 `Color.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 38 |
| 🧱 Classes | 1 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 28 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`src/math/Color.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `clamp` | `./MathUtils.js` |
| `euclideanModulo` | `./MathUtils.js` |
| `lerp` | `./MathUtils.js` |
| `ColorManagement` | `./ColorManagement.js` |
| `SRGBToLinear` | `./ColorManagement.js` |
| `LinearToSRGB` | `./ColorManagement.js` |
| `SRGBColorSpace` | `../constants.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `_colorKeywords` | `{ aliceblue: number; antiquewhite: nu...` | let/var | `{ 'aliceblue': 0xF0F8FF, 'antiquewhite': 0xFAEBD7, 'aqua': 0x00FFFF, 'aquamar...` | ✗ |
| `_hslA` | `{ h: number; s: number; l: number; }` | let/var | `{ h: 0, s: 0, l: 0 }` | ✗ |
| `_hslB` | `{ h: number; s: number; l: number; }` | let/var | `{ h: 0, s: 0, l: 0 }` | ✗ |
| `value` | `string \| number \| Color` | let/var | `r` | ✗ |
| `p` | `number` | let/var | `l <= 0.5 ? l * ( 1 + s ) : l + s - ( l * s )` | ✗ |
| `q` | `number` | let/var | `( 2 * l ) - p` | ✗ |
| `m` | `any` | let/var | `*not shown*` | ✗ |
| `color` | `any` | let/var | `*not shown*` | ✗ |
| `name` | `string` | let/var | `m[ 1 ]` | ✗ |
| `components` | `string` | let/var | `m[ 2 ]` | ✗ |
| `hex` | `string` | let/var | `m[ 1 ]` | ✗ |
| `size` | `number` | let/var | `hex.length` | ✗ |
| `hex` | `any` | let/var | `_colorKeywords[ style.toLowerCase() ]` | ✗ |
| `r` | `number` | let/var | `_color.r` | ✗ |
| `g` | `number` | let/var | `_color.g` | ✗ |
| `b` | `number` | let/var | `_color.b` | ✗ |
| `hue` | `any` | let/var | `*not shown*` | ✗ |
| `saturation` | `any` | let/var | `*not shown*` | ✗ |
| `lightness` | `number` | let/var | `( min + max ) / 2.0` | ✗ |
| `delta` | `number` | let/var | `max - min` | ✗ |
| `r` | `number` | let/var | `_color.r` | ✗ |
| `g` | `number` | let/var | `_color.g` | ✗ |
| `b` | `number` | let/var | `_color.b` | ✗ |
| `r` | `number` | let/var | `this.r` | ✗ |
| `g` | `number` | let/var | `this.g` | ✗ |
| `b` | `number` | let/var | `this.b` | ✗ |
| `e` | `any` | let/var | `m.elements` | ✗ |
| `_color` | `Color` | let/var | `new Color()` | ✗ |


---

## Functions

### `hue2rgb(p: any, q: any, t: any): any`

**Parameters:**

- **`p`** `any`
- **`q`** `any`
- **`t`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function hue2rgb( p, q, t ) {

	if ( t < 0 ) t += 1;
	if ( t > 1 ) t -= 1;
	if ( t < 1 / 6 ) return p + ( q - p ) * 6 * t;
	if ( t < 1 / 2 ) return q;
	if ( t < 2 / 3 ) return p + ( q - p ) * 6 * ( 2 / 3 - t );
	return p;

}
```
</details>

### `Color.set(r: string | number | Color, g: number, b: number): Color`

**JSDoc:**
```typescript
/**
	 * Sets the colors's components from the given values.
	 *
	 * @param {(number|string|Color)} [r] - The red component of the color. If `g` and `b` are
	 * not provided, it can be hexadecimal triplet, a CSS-style string or another `Color` instance.
	 * @param {number} [g] - The green component.
	 * @param {number} [b] - The blue component.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`r`** `string | number | Color`
- **`g`** `number`
- **`b`** `number`

**Returns:** `Color`

**Calls:**

- `this.copy`
- `this.setHex`
- `this.setStyle`
- `this.setRGB`

**Internal Comments:**
```
// r is THREE.Color, hex or string (x2)
```

<details><summary>Code</summary>

```typescript
set( r, g, b ) {

		if ( g === undefined && b === undefined ) {

			// r is THREE.Color, hex or string

			const value = r;

			if ( value && value.isColor ) {

				this.copy( value );

			} else if ( typeof value === 'number' ) {

				this.setHex( value );

			} else if ( typeof value === 'string' ) {

				this.setStyle( value );

			}

		} else {

			this.setRGB( r, g, b );

		}

		return this;

	}
```
</details>

### `Color.setScalar(scalar: number): Color`

**JSDoc:**
```typescript
/**
	 * Sets the colors's components to the given scalar value.
	 *
	 * @param {number} scalar - The scalar value.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`scalar`** `number`

**Returns:** `Color`

<details><summary>Code</summary>

```typescript
setScalar( scalar ) {

		this.r = scalar;
		this.g = scalar;
		this.b = scalar;

		return this;

	}
```
</details>

### `Color.setHex(hex: number, colorSpace: string): Color`

**JSDoc:**
```typescript
/**
	 * Sets this color from a hexadecimal value.
	 *
	 * @param {number} hex - The hexadecimal value.
	 * @param {string} [colorSpace=SRGBColorSpace] - The color space.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`hex`** `number`
- **`colorSpace`** `string`

**Returns:** `Color`

**Calls:**

- `Math.floor`
- `ColorManagement.colorSpaceToWorking`

<details><summary>Code</summary>

```typescript
setHex( hex, colorSpace = SRGBColorSpace ) {

		hex = Math.floor( hex );

		this.r = ( hex >> 16 & 255 ) / 255;
		this.g = ( hex >> 8 & 255 ) / 255;
		this.b = ( hex & 255 ) / 255;

		ColorManagement.colorSpaceToWorking( this, colorSpace );

		return this;

	}
```
</details>

### `Color.setRGB(r: number, g: number, b: number, colorSpace: string): Color`

**JSDoc:**
```typescript
/**
	 * Sets this color from RGB values.
	 *
	 * @param {number} r - Red channel value between `0.0` and `1.0`.
	 * @param {number} g - Green channel value between `0.0` and `1.0`.
	 * @param {number} b - Blue channel value between `0.0` and `1.0`.
	 * @param {string} [colorSpace=ColorManagement.workingColorSpace] - The color space.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`r`** `number`
- **`g`** `number`
- **`b`** `number`
- **`colorSpace`** `string`

**Returns:** `Color`

**Calls:**

- `ColorManagement.colorSpaceToWorking`

<details><summary>Code</summary>

```typescript
setRGB( r, g, b, colorSpace = ColorManagement.workingColorSpace ) {

		this.r = r;
		this.g = g;
		this.b = b;

		ColorManagement.colorSpaceToWorking( this, colorSpace );

		return this;

	}
```
</details>

### `Color.setHSL(h: number, s: number, l: number, colorSpace: string): Color`

**JSDoc:**
```typescript
/**
	 * Sets this color from RGB values.
	 *
	 * @param {number} h - Hue value between `0.0` and `1.0`.
	 * @param {number} s - Saturation value between `0.0` and `1.0`.
	 * @param {number} l - Lightness value between `0.0` and `1.0`.
	 * @param {string} [colorSpace=ColorManagement.workingColorSpace] - The color space.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`h`** `number`
- **`s`** `number`
- **`l`** `number`
- **`colorSpace`** `string`

**Returns:** `Color`

**Calls:**

- `euclideanModulo (from ./MathUtils.js)`
- `clamp (from ./MathUtils.js)`
- `hue2rgb`
- `ColorManagement.colorSpaceToWorking`

**Internal Comments:**
```
// h,s,l ranges are in 0.0 - 1.0 (x3)
```

<details><summary>Code</summary>

```typescript
setHSL( h, s, l, colorSpace = ColorManagement.workingColorSpace ) {

		// h,s,l ranges are in 0.0 - 1.0
		h = euclideanModulo( h, 1 );
		s = clamp( s, 0, 1 );
		l = clamp( l, 0, 1 );

		if ( s === 0 ) {

			this.r = this.g = this.b = l;

		} else {

			const p = l <= 0.5 ? l * ( 1 + s ) : l + s - ( l * s );
			const q = ( 2 * l ) - p;

			this.r = hue2rgb( q, p, h + 1 / 3 );
			this.g = hue2rgb( q, p, h );
			this.b = hue2rgb( q, p, h - 1 / 3 );

		}

		ColorManagement.colorSpaceToWorking( this, colorSpace );

		return this;

	}
```
</details>

### `Color.setStyle(style: string, colorSpace: string): Color`

**JSDoc:**
```typescript
/**
	 * Sets this color from a CSS-style string. For example, `rgb(250, 0,0)`,
	 * `rgb(100%, 0%, 0%)`, `hsl(0, 100%, 50%)`, `#ff0000`, `#f00`, or `red` ( or
	 * any [X11 color name]{@link https://en.wikipedia.org/wiki/X11_color_names#Color_name_chart} -
	 * all 140 color names are supported).
	 *
	 * @param {string} style - Color as a CSS-style string.
	 * @param {string} [colorSpace=SRGBColorSpace] - The color space.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`style`** `string`
- **`colorSpace`** `string`

**Returns:** `Color`

**Calls:**

- `parseFloat`
- `console.warn`
- `/^(\w+)\(([^\)]*)\)/.exec`
- `/^\s*(\d+)\s*,\s*(\d+)\s*,\s*(\d+)\s*(?:,\s*(\d*\.?\d+)\s*)?$/.exec`
- `handleAlpha`
- `this.setRGB`
- `Math.min`
- `parseInt`
- `/^\s*(\d+)\%\s*,\s*(\d+)\%\s*,\s*(\d+)\%\s*(?:,\s*(\d*\.?\d+)\s*)?$/.exec`
- `/^\s*(\d*\.?\d+)\s*,\s*(\d*\.?\d+)\%\s*,\s*(\d*\.?\d+)\%\s*(?:,\s*(\d*\.?\d+)\s*)?$/.exec`
- `this.setHSL`
- `/^\#([A-Fa-f\d]+)$/.exec`
- `hex.charAt`
- `this.setHex`
- `this.setColorName`

**Internal Comments:**
```
// rgb / hsl (x2)
// rgb(255,0,0) rgba(255,0,0,0.5) (x3)
// rgb(100%,0%,0%) rgba(100%,0%,0%,0.5) (x3)
// hsl(120,50%,50%) hsla(120,50%,50%,0.5) (x3)
// hex color (x2)
// #ff0
// #ff0000
```

<details><summary>Code</summary>

```typescript
setStyle( style, colorSpace = SRGBColorSpace ) {

		function handleAlpha( string ) {

			if ( string === undefined ) return;

			if ( parseFloat( string ) < 1 ) {

				console.warn( 'THREE.Color: Alpha component of ' + style + ' will be ignored.' );

			}

		}


		let m;

		if ( m = /^(\w+)\(([^\)]*)\)/.exec( style ) ) {

			// rgb / hsl

			let color;
			const name = m[ 1 ];
			const components = m[ 2 ];

			switch ( name ) {

				case 'rgb':
				case 'rgba':

					if ( color = /^\s*(\d+)\s*,\s*(\d+)\s*,\s*(\d+)\s*(?:,\s*(\d*\.?\d+)\s*)?$/.exec( components ) ) {

						// rgb(255,0,0) rgba(255,0,0,0.5)

						handleAlpha( color[ 4 ] );

						return this.setRGB(
							Math.min( 255, parseInt( color[ 1 ], 10 ) ) / 255,
							Math.min( 255, parseInt( color[ 2 ], 10 ) ) / 255,
							Math.min( 255, parseInt( color[ 3 ], 10 ) ) / 255,
							colorSpace
						);

					}

					if ( color = /^\s*(\d+)\%\s*,\s*(\d+)\%\s*,\s*(\d+)\%\s*(?:,\s*(\d*\.?\d+)\s*)?$/.exec( components ) ) {

						// rgb(100%,0%,0%) rgba(100%,0%,0%,0.5)

						handleAlpha( color[ 4 ] );

						return this.setRGB(
							Math.min( 100, parseInt( color[ 1 ], 10 ) ) / 100,
							Math.min( 100, parseInt( color[ 2 ], 10 ) ) / 100,
							Math.min( 100, parseInt( color[ 3 ], 10 ) ) / 100,
							colorSpace
						);

					}

					break;

				case 'hsl':
				case 'hsla':

					if ( color = /^\s*(\d*\.?\d+)\s*,\s*(\d*\.?\d+)\%\s*,\s*(\d*\.?\d+)\%\s*(?:,\s*(\d*\.?\d+)\s*)?$/.exec( components ) ) {

						// hsl(120,50%,50%) hsla(120,50%,50%,0.5)

						handleAlpha( color[ 4 ] );

						return this.setHSL(
							parseFloat( color[ 1 ] ) / 360,
							parseFloat( color[ 2 ] ) / 100,
							parseFloat( color[ 3 ] ) / 100,
							colorSpace
						);

					}

					break;

				default:

					console.warn( 'THREE.Color: Unknown color model ' + style );

			}

		} else if ( m = /^\#([A-Fa-f\d]+)$/.exec( style ) ) {

			// hex color

			const hex = m[ 1 ];
			const size = hex.length;

			if ( size === 3 ) {

				// #ff0
				return this.setRGB(
					parseInt( hex.charAt( 0 ), 16 ) / 15,
					parseInt( hex.charAt( 1 ), 16 ) / 15,
					parseInt( hex.charAt( 2 ), 16 ) / 15,
					colorSpace
				);

			} else if ( size === 6 ) {

				// #ff0000
				return this.setHex( parseInt( hex, 16 ), colorSpace );

			} else {

				console.warn( 'THREE.Color: Invalid hex color ' + style );

			}

		} else if ( style && style.length > 0 ) {

			return this.setColorName( style, colorSpace );

		}

		return this;

	}
```
</details>

### `Color.setColorName(style: string, colorSpace: string): Color`

**JSDoc:**
```typescript
/**
	 * Sets this color from a color name. Faster than {@link Color#setStyle} if
	 * you don't need the other CSS-style formats.
	 *
	 * For convenience, the list of names is exposed in `Color.NAMES` as a hash.
	 * ```js
	 * Color.NAMES.aliceblue // returns 0xF0F8FF
	 * ```
	 *
	 * @param {string} style - The color name.
	 * @param {string} [colorSpace=SRGBColorSpace] - The color space.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`style`** `string`
- **`colorSpace`** `string`

**Returns:** `Color`

**Calls:**

- `style.toLowerCase`
- `this.setHex`
- `console.warn`

**Internal Comments:**
```
// color keywords (x2)
// red (x4)
// unknown color (x4)
```

<details><summary>Code</summary>

```typescript
setColorName( style, colorSpace = SRGBColorSpace ) {

		// color keywords
		const hex = _colorKeywords[ style.toLowerCase() ];

		if ( hex !== undefined ) {

			// red
			this.setHex( hex, colorSpace );

		} else {

			// unknown color
			console.warn( 'THREE.Color: Unknown color ' + style );

		}

		return this;

	}
```
</details>

### `Color.clone(): Color`

**JSDoc:**
```typescript
/**
	 * Returns a new color with copied values from this instance.
	 *
	 * @return {Color} A clone of this instance.
	 */
```

**Returns:** `Color`

<details><summary>Code</summary>

```typescript
clone() {

		return new this.constructor( this.r, this.g, this.b );

	}
```
</details>

### `Color.copy(color: Color): Color`

**JSDoc:**
```typescript
/**
	 * Copies the values of the given color to this instance.
	 *
	 * @param {Color} color - The color to copy.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`color`** `Color`

**Returns:** `Color`

<details><summary>Code</summary>

```typescript
copy( color ) {

		this.r = color.r;
		this.g = color.g;
		this.b = color.b;

		return this;

	}
```
</details>

### `Color.copySRGBToLinear(color: Color): Color`

**JSDoc:**
```typescript
/**
	 * Copies the given color into this color, and then converts this color from
	 * `SRGBColorSpace` to `LinearSRGBColorSpace`.
	 *
	 * @param {Color} color - The color to copy/convert.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`color`** `Color`

**Returns:** `Color`

**Calls:**

- `SRGBToLinear (from ./ColorManagement.js)`

<details><summary>Code</summary>

```typescript
copySRGBToLinear( color ) {

		this.r = SRGBToLinear( color.r );
		this.g = SRGBToLinear( color.g );
		this.b = SRGBToLinear( color.b );

		return this;

	}
```
</details>

### `Color.copyLinearToSRGB(color: Color): Color`

**JSDoc:**
```typescript
/**
	 * Copies the given color into this color, and then converts this color from
	 * `LinearSRGBColorSpace` to `SRGBColorSpace`.
	 *
	 * @param {Color} color - The color to copy/convert.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`color`** `Color`

**Returns:** `Color`

**Calls:**

- `LinearToSRGB (from ./ColorManagement.js)`

<details><summary>Code</summary>

```typescript
copyLinearToSRGB( color ) {

		this.r = LinearToSRGB( color.r );
		this.g = LinearToSRGB( color.g );
		this.b = LinearToSRGB( color.b );

		return this;

	}
```
</details>

### `Color.convertSRGBToLinear(): Color`

**JSDoc:**
```typescript
/**
	 * Converts this color from `SRGBColorSpace` to `LinearSRGBColorSpace`.
	 *
	 * @return {Color} A reference to this color.
	 */
```

**Returns:** `Color`

**Calls:**

- `this.copySRGBToLinear`

<details><summary>Code</summary>

```typescript
convertSRGBToLinear() {

		this.copySRGBToLinear( this );

		return this;

	}
```
</details>

### `Color.convertLinearToSRGB(): Color`

**JSDoc:**
```typescript
/**
	 * Converts this color from `LinearSRGBColorSpace` to `SRGBColorSpace`.
	 *
	 * @return {Color} A reference to this color.
	 */
```

**Returns:** `Color`

**Calls:**

- `this.copyLinearToSRGB`

<details><summary>Code</summary>

```typescript
convertLinearToSRGB() {

		this.copyLinearToSRGB( this );

		return this;

	}
```
</details>

### `Color.getHex(colorSpace: string): number`

**JSDoc:**
```typescript
/**
	 * Returns the hexadecimal value of this color.
	 *
	 * @param {string} [colorSpace=SRGBColorSpace] - The color space.
	 * @return {number} The hexadecimal value.
	 */
```

**Parameters:**

- **`colorSpace`** `string`

**Returns:** `number`

**Calls:**

- `ColorManagement.workingToColorSpace`
- `_color.copy`
- `Math.round`
- `clamp (from ./MathUtils.js)`

<details><summary>Code</summary>

```typescript
getHex( colorSpace = SRGBColorSpace ) {

		ColorManagement.workingToColorSpace( _color.copy( this ), colorSpace );

		return Math.round( clamp( _color.r * 255, 0, 255 ) ) * 65536 + Math.round( clamp( _color.g * 255, 0, 255 ) ) * 256 + Math.round( clamp( _color.b * 255, 0, 255 ) );

	}
```
</details>

### `Color.getHexString(colorSpace: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the hexadecimal value of this color as a string (for example, 'FFFFFF').
	 *
	 * @param {string} [colorSpace=SRGBColorSpace] - The color space.
	 * @return {string} The hexadecimal value as a string.
	 */
```

**Parameters:**

- **`colorSpace`** `string`

**Returns:** `string`

**Calls:**

- `( '000000' + this.getHex( colorSpace ).toString( 16 ) ).slice`
- `this.getHex( colorSpace ).toString`

<details><summary>Code</summary>

```typescript
getHexString( colorSpace = SRGBColorSpace ) {

		return ( '000000' + this.getHex( colorSpace ).toString( 16 ) ).slice( - 6 );

	}
```
</details>

### `Color.getHSL(target: { h: number; s: number; l: number; }, colorSpace: string): { h: number; s: number; l: number; }`

**JSDoc:**
```typescript
/**
	 * Converts the colors RGB values into the HSL format and stores them into the
	 * given target object.
	 *
	 * @param {{h:number,s:number,l:number}} target - The target object that is used to store the method's result.
	 * @param {string} [colorSpace=ColorManagement.workingColorSpace] - The color space.
	 * @return {{h:number,s:number,l:number}} The HSL representation of this color.
	 */
```

**Parameters:**

- **`target`** `{ h: number; s: number; l: number; }`
- **`colorSpace`** `string`

**Returns:** `{ h: number; s: number; l: number; }`

**Calls:**

- `ColorManagement.workingToColorSpace`
- `_color.copy`
- `Math.max`
- `Math.min`

**Internal Comments:**
```
// h,s,l ranges are in 0.0 - 1.0 (x4)
```

<details><summary>Code</summary>

```typescript
getHSL( target, colorSpace = ColorManagement.workingColorSpace ) {

		// h,s,l ranges are in 0.0 - 1.0

		ColorManagement.workingToColorSpace( _color.copy( this ), colorSpace );

		const r = _color.r, g = _color.g, b = _color.b;

		const max = Math.max( r, g, b );
		const min = Math.min( r, g, b );

		let hue, saturation;
		const lightness = ( min + max ) / 2.0;

		if ( min === max ) {

			hue = 0;
			saturation = 0;

		} else {

			const delta = max - min;

			saturation = lightness <= 0.5 ? delta / ( max + min ) : delta / ( 2 - max - min );

			switch ( max ) {

				case r: hue = ( g - b ) / delta + ( g < b ? 6 : 0 ); break;
				case g: hue = ( b - r ) / delta + 2; break;
				case b: hue = ( r - g ) / delta + 4; break;

			}

			hue /= 6;

		}

		target.h = hue;
		target.s = saturation;
		target.l = lightness;

		return target;

	}
```
</details>

### `Color.getRGB(target: Color, colorSpace: string): Color`

**JSDoc:**
```typescript
/**
	 * Returns the RGB values of this color and stores them into the given target object.
	 *
	 * @param {Color} target - The target color that is used to store the method's result.
	 * @param {string} [colorSpace=ColorManagement.workingColorSpace] - The color space.
	 * @return {Color} The RGB representation of this color.
	 */
```

**Parameters:**

- **`target`** `Color`
- **`colorSpace`** `string`

**Returns:** `Color`

**Calls:**

- `ColorManagement.workingToColorSpace`
- `_color.copy`

<details><summary>Code</summary>

```typescript
getRGB( target, colorSpace = ColorManagement.workingColorSpace ) {

		ColorManagement.workingToColorSpace( _color.copy( this ), colorSpace );

		target.r = _color.r;
		target.g = _color.g;
		target.b = _color.b;

		return target;

	}
```
</details>

### `Color.getStyle(colorSpace: string): string`

**JSDoc:**
```typescript
/**
	 * Returns the value of this color as a CSS style string. Example: `rgb(255,0,0)`.
	 *
	 * @param {string} [colorSpace=SRGBColorSpace] - The color space.
	 * @return {string} The CSS representation of this color.
	 */
```

**Parameters:**

- **`colorSpace`** `string`

**Returns:** `string`

**Calls:**

- `ColorManagement.workingToColorSpace`
- `_color.copy`
- `r.toFixed`
- `g.toFixed`
- `b.toFixed`
- `Math.round`

**Internal Comments:**
```
// Requires CSS Color Module Level 4 (https://www.w3.org/TR/css-color-4/).
```

<details><summary>Code</summary>

```typescript
getStyle( colorSpace = SRGBColorSpace ) {

		ColorManagement.workingToColorSpace( _color.copy( this ), colorSpace );

		const r = _color.r, g = _color.g, b = _color.b;

		if ( colorSpace !== SRGBColorSpace ) {

			// Requires CSS Color Module Level 4 (https://www.w3.org/TR/css-color-4/).
			return `color(${ colorSpace } ${ r.toFixed( 3 ) } ${ g.toFixed( 3 ) } ${ b.toFixed( 3 ) })`;

		}

		return `rgb(${ Math.round( r * 255 ) },${ Math.round( g * 255 ) },${ Math.round( b * 255 ) })`;

	}
```
</details>

### `Color.offsetHSL(h: number, s: number, l: number): Color`

**JSDoc:**
```typescript
/**
	 * Adds the given HSL values to this color's values.
	 * Internally, this converts the color's RGB values to HSL, adds HSL
	 * and then converts the color back to RGB.
	 *
	 * @param {number} h - Hue value between `0.0` and `1.0`.
	 * @param {number} s - Saturation value between `0.0` and `1.0`.
	 * @param {number} l - Lightness value between `0.0` and `1.0`.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`h`** `number`
- **`s`** `number`
- **`l`** `number`

**Returns:** `Color`

**Calls:**

- `this.getHSL`
- `this.setHSL`

<details><summary>Code</summary>

```typescript
offsetHSL( h, s, l ) {

		this.getHSL( _hslA );

		return this.setHSL( _hslA.h + h, _hslA.s + s, _hslA.l + l );

	}
```
</details>

### `Color.add(color: Color): Color`

**JSDoc:**
```typescript
/**
	 * Adds the RGB values of the given color to the RGB values of this color.
	 *
	 * @param {Color} color - The color to add.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`color`** `Color`

**Returns:** `Color`

<details><summary>Code</summary>

```typescript
add( color ) {

		this.r += color.r;
		this.g += color.g;
		this.b += color.b;

		return this;

	}
```
</details>

### `Color.addColors(color1: Color, color2: Color): Color`

**JSDoc:**
```typescript
/**
	 * Adds the RGB values of the given colors and stores the result in this instance.
	 *
	 * @param {Color} color1 - The first color.
	 * @param {Color} color2 - The second color.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`color1`** `Color`
- **`color2`** `Color`

**Returns:** `Color`

<details><summary>Code</summary>

```typescript
addColors( color1, color2 ) {

		this.r = color1.r + color2.r;
		this.g = color1.g + color2.g;
		this.b = color1.b + color2.b;

		return this;

	}
```
</details>

### `Color.addScalar(s: number): Color`

**JSDoc:**
```typescript
/**
	 * Adds the given scalar value to the RGB values of this color.
	 *
	 * @param {number} s - The scalar to add.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`s`** `number`

**Returns:** `Color`

<details><summary>Code</summary>

```typescript
addScalar( s ) {

		this.r += s;
		this.g += s;
		this.b += s;

		return this;

	}
```
</details>

### `Color.sub(color: Color): Color`

**JSDoc:**
```typescript
/**
	 * Subtracts the RGB values of the given color from the RGB values of this color.
	 *
	 * @param {Color} color - The color to subtract.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`color`** `Color`

**Returns:** `Color`

**Calls:**

- `Math.max`

<details><summary>Code</summary>

```typescript
sub( color ) {

		this.r = Math.max( 0, this.r - color.r );
		this.g = Math.max( 0, this.g - color.g );
		this.b = Math.max( 0, this.b - color.b );

		return this;

	}
```
</details>

### `Color.multiply(color: Color): Color`

**JSDoc:**
```typescript
/**
	 * Multiplies the RGB values of the given color with the RGB values of this color.
	 *
	 * @param {Color} color - The color to multiply.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`color`** `Color`

**Returns:** `Color`

<details><summary>Code</summary>

```typescript
multiply( color ) {

		this.r *= color.r;
		this.g *= color.g;
		this.b *= color.b;

		return this;

	}
```
</details>

### `Color.multiplyScalar(s: number): Color`

**JSDoc:**
```typescript
/**
	 * Multiplies the given scalar value with the RGB values of this color.
	 *
	 * @param {number} s - The scalar to multiply.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`s`** `number`

**Returns:** `Color`

<details><summary>Code</summary>

```typescript
multiplyScalar( s ) {

		this.r *= s;
		this.g *= s;
		this.b *= s;

		return this;

	}
```
</details>

### `Color.lerp(color: Color, alpha: number): Color`

**JSDoc:**
```typescript
/**
	 * Linearly interpolates this color's RGB values toward the RGB values of the
	 * given color. The alpha argument can be thought of as the ratio between
	 * the two colors, where `0.0` is this color and `1.0` is the first argument.
	 *
	 * @param {Color} color - The color to converge on.
	 * @param {number} alpha - The interpolation factor in the closed interval `[0,1]`.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`color`** `Color`
- **`alpha`** `number`

**Returns:** `Color`

<details><summary>Code</summary>

```typescript
lerp( color, alpha ) {

		this.r += ( color.r - this.r ) * alpha;
		this.g += ( color.g - this.g ) * alpha;
		this.b += ( color.b - this.b ) * alpha;

		return this;

	}
```
</details>

### `Color.lerpColors(color1: Color, color2: Color, alpha: number): Color`

**JSDoc:**
```typescript
/**
	 * Linearly interpolates between the given colors and stores the result in this instance.
	 * The alpha argument can be thought of as the ratio between the two colors, where `0.0`
	 * is the first and `1.0` is the second color.
	 *
	 * @param {Color} color1 - The first color.
	 * @param {Color} color2 - The second color.
	 * @param {number} alpha - The interpolation factor in the closed interval `[0,1]`.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`color1`** `Color`
- **`color2`** `Color`
- **`alpha`** `number`

**Returns:** `Color`

<details><summary>Code</summary>

```typescript
lerpColors( color1, color2, alpha ) {

		this.r = color1.r + ( color2.r - color1.r ) * alpha;
		this.g = color1.g + ( color2.g - color1.g ) * alpha;
		this.b = color1.b + ( color2.b - color1.b ) * alpha;

		return this;

	}
```
</details>

### `Color.lerpHSL(color: Color, alpha: number): Color`

**JSDoc:**
```typescript
/**
	 * Linearly interpolates this color's HSL values toward the HSL values of the
	 * given color. It differs from {@link Color#lerp} by not interpolating straight
	 * from one color to the other, but instead going through all the hues in between
	 * those two colors. The alpha argument can be thought of as the ratio between
	 * the two colors, where 0.0 is this color and 1.0 is the first argument.
	 *
	 * @param {Color} color - The color to converge on.
	 * @param {number} alpha - The interpolation factor in the closed interval `[0,1]`.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`color`** `Color`
- **`alpha`** `number`

**Returns:** `Color`

**Calls:**

- `this.getHSL`
- `color.getHSL`
- `lerp (from ./MathUtils.js)`
- `this.setHSL`

<details><summary>Code</summary>

```typescript
lerpHSL( color, alpha ) {

		this.getHSL( _hslA );
		color.getHSL( _hslB );

		const h = lerp( _hslA.h, _hslB.h, alpha );
		const s = lerp( _hslA.s, _hslB.s, alpha );
		const l = lerp( _hslA.l, _hslB.l, alpha );

		this.setHSL( h, s, l );

		return this;

	}
```
</details>

### `Color.setFromVector3(v: Vector3): Color`

**JSDoc:**
```typescript
/**
	 * Sets the color's RGB components from the given 3D vector.
	 *
	 * @param {Vector3} v - The vector to set.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`v`** `Vector3`

**Returns:** `Color`

<details><summary>Code</summary>

```typescript
setFromVector3( v ) {

		this.r = v.x;
		this.g = v.y;
		this.b = v.z;

		return this;

	}
```
</details>

### `Color.applyMatrix3(m: Matrix3): Color`

**JSDoc:**
```typescript
/**
	 * Transforms this color with the given 3x3 matrix.
	 *
	 * @param {Matrix3} m - The matrix.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`m`** `Matrix3`

**Returns:** `Color`

<details><summary>Code</summary>

```typescript
applyMatrix3( m ) {

		const r = this.r, g = this.g, b = this.b;
		const e = m.elements;

		this.r = e[ 0 ] * r + e[ 3 ] * g + e[ 6 ] * b;
		this.g = e[ 1 ] * r + e[ 4 ] * g + e[ 7 ] * b;
		this.b = e[ 2 ] * r + e[ 5 ] * g + e[ 8 ] * b;

		return this;

	}
```
</details>

### `Color.equals(c: Color): boolean`

**JSDoc:**
```typescript
/**
	 * Returns `true` if this color is equal with the given one.
	 *
	 * @param {Color} c - The color to test for equality.
	 * @return {boolean} Whether this bounding color is equal with the given one.
	 */
```

**Parameters:**

- **`c`** `Color`

**Returns:** `boolean`

<details><summary>Code</summary>

```typescript
equals( c ) {

		return ( c.r === this.r ) && ( c.g === this.g ) && ( c.b === this.b );

	}
```
</details>

### `Color.fromArray(array: number[], offset: number): Color`

**JSDoc:**
```typescript
/**
	 * Sets this color's RGB components from the given array.
	 *
	 * @param {Array<number>} array - An array holding the RGB values.
	 * @param {number} [offset=0] - The offset into the array.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`array`** `number[]`
- **`offset`** `number`

**Returns:** `Color`

<details><summary>Code</summary>

```typescript
fromArray( array, offset = 0 ) {

		this.r = array[ offset ];
		this.g = array[ offset + 1 ];
		this.b = array[ offset + 2 ];

		return this;

	}
```
</details>

### `Color.toArray(array: number[], offset: number): number[]`

**JSDoc:**
```typescript
/**
	 * Writes the RGB components of this color to the given array. If no array is provided,
	 * the method returns a new instance.
	 *
	 * @param {Array<number>} [array=[]] - The target array holding the color components.
	 * @param {number} [offset=0] - Index of the first element in the array.
	 * @return {Array<number>} The color components.
	 */
```

**Parameters:**

- **`array`** `number[]`
- **`offset`** `number`

**Returns:** `number[]`

<details><summary>Code</summary>

```typescript
toArray( array = [], offset = 0 ) {

		array[ offset ] = this.r;
		array[ offset + 1 ] = this.g;
		array[ offset + 2 ] = this.b;

		return array;

	}
```
</details>

### `Color.fromBufferAttribute(attribute: BufferAttribute, index: number): Color`

**JSDoc:**
```typescript
/**
	 * Sets the components of this color from the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute holding color data.
	 * @param {number} index - The index into the attribute.
	 * @return {Color} A reference to this color.
	 */
```

**Parameters:**

- **`attribute`** `BufferAttribute`
- **`index`** `number`

**Returns:** `Color`

**Calls:**

- `attribute.getX`
- `attribute.getY`
- `attribute.getZ`

<details><summary>Code</summary>

```typescript
fromBufferAttribute( attribute, index ) {

		this.r = attribute.getX( index );
		this.g = attribute.getY( index );
		this.b = attribute.getZ( index );

		return this;

	}
```
</details>

### `Color.toJSON(): number`

**JSDoc:**
```typescript
/**
	 * This methods defines the serialization result of this class. Returns the color
	 * as a hexadecimal value.
	 *
	 * @return {number} The hexadecimal value.
	 */
```

**Returns:** `number`

**Calls:**

- `this.getHex`

<details><summary>Code</summary>

```typescript
toJSON() {

		return this.getHex();

	}
```
</details>

### `Color.[ Symbol.iterator ](): Generator<number, void, unknown>`

**Returns:** `Generator<number, void, unknown>`

<details><summary>Code</summary>

```typescript
*[ Symbol.iterator ]() {

		yield this.r;
		yield this.g;
		yield this.b;

	}
```
</details>

### `handleAlpha(string: any): void`

**Parameters:**

- **`string`** `any`

**Returns:** `void`

**Calls:**

- `parseFloat`
- `console.warn`

<details><summary>Code</summary>

```typescript
function handleAlpha( string ) {

			if ( string === undefined ) return;

			if ( parseFloat( string ) < 1 ) {

				console.warn( 'THREE.Color: Alpha component of ' + style + ' will be ignored.' );

			}

		}
```
</details>


---

## Classes

### `Color`

<details><summary>Class Code</summary>

```ts
class Color {

	/**
	 * Constructs a new color.
	 *
	 * Note that standard method of specifying color in three.js is with a hexadecimal triplet,
	 * and that method is used throughout the rest of the documentation.
	 *
	 * @param {(number|string|Color)} [r] - The red component of the color. If `g` and `b` are
	 * not provided, it can be hexadecimal triplet, a CSS-style string or another `Color` instance.
	 * @param {number} [g] - The green component.
	 * @param {number} [b] - The blue component.
	 */
	constructor( r, g, b ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isColor = true;

		/**
		 * The red component.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.r = 1;

		/**
		 * The green component.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.g = 1;

		/**
		 * The blue component.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.b = 1;

		return this.set( r, g, b );

	}

	/**
	 * Sets the colors's components from the given values.
	 *
	 * @param {(number|string|Color)} [r] - The red component of the color. If `g` and `b` are
	 * not provided, it can be hexadecimal triplet, a CSS-style string or another `Color` instance.
	 * @param {number} [g] - The green component.
	 * @param {number} [b] - The blue component.
	 * @return {Color} A reference to this color.
	 */
	set( r, g, b ) {

		if ( g === undefined && b === undefined ) {

			// r is THREE.Color, hex or string

			const value = r;

			if ( value && value.isColor ) {

				this.copy( value );

			} else if ( typeof value === 'number' ) {

				this.setHex( value );

			} else if ( typeof value === 'string' ) {

				this.setStyle( value );

			}

		} else {

			this.setRGB( r, g, b );

		}

		return this;

	}

	/**
	 * Sets the colors's components to the given scalar value.
	 *
	 * @param {number} scalar - The scalar value.
	 * @return {Color} A reference to this color.
	 */
	setScalar( scalar ) {

		this.r = scalar;
		this.g = scalar;
		this.b = scalar;

		return this;

	}

	/**
	 * Sets this color from a hexadecimal value.
	 *
	 * @param {number} hex - The hexadecimal value.
	 * @param {string} [colorSpace=SRGBColorSpace] - The color space.
	 * @return {Color} A reference to this color.
	 */
	setHex( hex, colorSpace = SRGBColorSpace ) {

		hex = Math.floor( hex );

		this.r = ( hex >> 16 & 255 ) / 255;
		this.g = ( hex >> 8 & 255 ) / 255;
		this.b = ( hex & 255 ) / 255;

		ColorManagement.colorSpaceToWorking( this, colorSpace );

		return this;

	}

	/**
	 * Sets this color from RGB values.
	 *
	 * @param {number} r - Red channel value between `0.0` and `1.0`.
	 * @param {number} g - Green channel value between `0.0` and `1.0`.
	 * @param {number} b - Blue channel value between `0.0` and `1.0`.
	 * @param {string} [colorSpace=ColorManagement.workingColorSpace] - The color space.
	 * @return {Color} A reference to this color.
	 */
	setRGB( r, g, b, colorSpace = ColorManagement.workingColorSpace ) {

		this.r = r;
		this.g = g;
		this.b = b;

		ColorManagement.colorSpaceToWorking( this, colorSpace );

		return this;

	}

	/**
	 * Sets this color from RGB values.
	 *
	 * @param {number} h - Hue value between `0.0` and `1.0`.
	 * @param {number} s - Saturation value between `0.0` and `1.0`.
	 * @param {number} l - Lightness value between `0.0` and `1.0`.
	 * @param {string} [colorSpace=ColorManagement.workingColorSpace] - The color space.
	 * @return {Color} A reference to this color.
	 */
	setHSL( h, s, l, colorSpace = ColorManagement.workingColorSpace ) {

		// h,s,l ranges are in 0.0 - 1.0
		h = euclideanModulo( h, 1 );
		s = clamp( s, 0, 1 );
		l = clamp( l, 0, 1 );

		if ( s === 0 ) {

			this.r = this.g = this.b = l;

		} else {

			const p = l <= 0.5 ? l * ( 1 + s ) : l + s - ( l * s );
			const q = ( 2 * l ) - p;

			this.r = hue2rgb( q, p, h + 1 / 3 );
			this.g = hue2rgb( q, p, h );
			this.b = hue2rgb( q, p, h - 1 / 3 );

		}

		ColorManagement.colorSpaceToWorking( this, colorSpace );

		return this;

	}

	/**
	 * Sets this color from a CSS-style string. For example, `rgb(250, 0,0)`,
	 * `rgb(100%, 0%, 0%)`, `hsl(0, 100%, 50%)`, `#ff0000`, `#f00`, or `red` ( or
	 * any [X11 color name]{@link https://en.wikipedia.org/wiki/X11_color_names#Color_name_chart} -
	 * all 140 color names are supported).
	 *
	 * @param {string} style - Color as a CSS-style string.
	 * @param {string} [colorSpace=SRGBColorSpace] - The color space.
	 * @return {Color} A reference to this color.
	 */
	setStyle( style, colorSpace = SRGBColorSpace ) {

		function handleAlpha( string ) {

			if ( string === undefined ) return;

			if ( parseFloat( string ) < 1 ) {

				console.warn( 'THREE.Color: Alpha component of ' + style + ' will be ignored.' );

			}

		}


		let m;

		if ( m = /^(\w+)\(([^\)]*)\)/.exec( style ) ) {

			// rgb / hsl

			let color;
			const name = m[ 1 ];
			const components = m[ 2 ];

			switch ( name ) {

				case 'rgb':
				case 'rgba':

					if ( color = /^\s*(\d+)\s*,\s*(\d+)\s*,\s*(\d+)\s*(?:,\s*(\d*\.?\d+)\s*)?$/.exec( components ) ) {

						// rgb(255,0,0) rgba(255,0,0,0.5)

						handleAlpha( color[ 4 ] );

						return this.setRGB(
							Math.min( 255, parseInt( color[ 1 ], 10 ) ) / 255,
							Math.min( 255, parseInt( color[ 2 ], 10 ) ) / 255,
							Math.min( 255, parseInt( color[ 3 ], 10 ) ) / 255,
							colorSpace
						);

					}

					if ( color = /^\s*(\d+)\%\s*,\s*(\d+)\%\s*,\s*(\d+)\%\s*(?:,\s*(\d*\.?\d+)\s*)?$/.exec( components ) ) {

						// rgb(100%,0%,0%) rgba(100%,0%,0%,0.5)

						handleAlpha( color[ 4 ] );

						return this.setRGB(
							Math.min( 100, parseInt( color[ 1 ], 10 ) ) / 100,
							Math.min( 100, parseInt( color[ 2 ], 10 ) ) / 100,
							Math.min( 100, parseInt( color[ 3 ], 10 ) ) / 100,
							colorSpace
						);

					}

					break;

				case 'hsl':
				case 'hsla':

					if ( color = /^\s*(\d*\.?\d+)\s*,\s*(\d*\.?\d+)\%\s*,\s*(\d*\.?\d+)\%\s*(?:,\s*(\d*\.?\d+)\s*)?$/.exec( components ) ) {

						// hsl(120,50%,50%) hsla(120,50%,50%,0.5)

						handleAlpha( color[ 4 ] );

						return this.setHSL(
							parseFloat( color[ 1 ] ) / 360,
							parseFloat( color[ 2 ] ) / 100,
							parseFloat( color[ 3 ] ) / 100,
							colorSpace
						);

					}

					break;

				default:

					console.warn( 'THREE.Color: Unknown color model ' + style );

			}

		} else if ( m = /^\#([A-Fa-f\d]+)$/.exec( style ) ) {

			// hex color

			const hex = m[ 1 ];
			const size = hex.length;

			if ( size === 3 ) {

				// #ff0
				return this.setRGB(
					parseInt( hex.charAt( 0 ), 16 ) / 15,
					parseInt( hex.charAt( 1 ), 16 ) / 15,
					parseInt( hex.charAt( 2 ), 16 ) / 15,
					colorSpace
				);

			} else if ( size === 6 ) {

				// #ff0000
				return this.setHex( parseInt( hex, 16 ), colorSpace );

			} else {

				console.warn( 'THREE.Color: Invalid hex color ' + style );

			}

		} else if ( style && style.length > 0 ) {

			return this.setColorName( style, colorSpace );

		}

		return this;

	}

	/**
	 * Sets this color from a color name. Faster than {@link Color#setStyle} if
	 * you don't need the other CSS-style formats.
	 *
	 * For convenience, the list of names is exposed in `Color.NAMES` as a hash.
	 * ```js
	 * Color.NAMES.aliceblue // returns 0xF0F8FF
	 * ```
	 *
	 * @param {string} style - The color name.
	 * @param {string} [colorSpace=SRGBColorSpace] - The color space.
	 * @return {Color} A reference to this color.
	 */
	setColorName( style, colorSpace = SRGBColorSpace ) {

		// color keywords
		const hex = _colorKeywords[ style.toLowerCase() ];

		if ( hex !== undefined ) {

			// red
			this.setHex( hex, colorSpace );

		} else {

			// unknown color
			console.warn( 'THREE.Color: Unknown color ' + style );

		}

		return this;

	}

	/**
	 * Returns a new color with copied values from this instance.
	 *
	 * @return {Color} A clone of this instance.
	 */
	clone() {

		return new this.constructor( this.r, this.g, this.b );

	}

	/**
	 * Copies the values of the given color to this instance.
	 *
	 * @param {Color} color - The color to copy.
	 * @return {Color} A reference to this color.
	 */
	copy( color ) {

		this.r = color.r;
		this.g = color.g;
		this.b = color.b;

		return this;

	}

	/**
	 * Copies the given color into this color, and then converts this color from
	 * `SRGBColorSpace` to `LinearSRGBColorSpace`.
	 *
	 * @param {Color} color - The color to copy/convert.
	 * @return {Color} A reference to this color.
	 */
	copySRGBToLinear( color ) {

		this.r = SRGBToLinear( color.r );
		this.g = SRGBToLinear( color.g );
		this.b = SRGBToLinear( color.b );

		return this;

	}

	/**
	 * Copies the given color into this color, and then converts this color from
	 * `LinearSRGBColorSpace` to `SRGBColorSpace`.
	 *
	 * @param {Color} color - The color to copy/convert.
	 * @return {Color} A reference to this color.
	 */
	copyLinearToSRGB( color ) {

		this.r = LinearToSRGB( color.r );
		this.g = LinearToSRGB( color.g );
		this.b = LinearToSRGB( color.b );

		return this;

	}

	/**
	 * Converts this color from `SRGBColorSpace` to `LinearSRGBColorSpace`.
	 *
	 * @return {Color} A reference to this color.
	 */
	convertSRGBToLinear() {

		this.copySRGBToLinear( this );

		return this;

	}

	/**
	 * Converts this color from `LinearSRGBColorSpace` to `SRGBColorSpace`.
	 *
	 * @return {Color} A reference to this color.
	 */
	convertLinearToSRGB() {

		this.copyLinearToSRGB( this );

		return this;

	}

	/**
	 * Returns the hexadecimal value of this color.
	 *
	 * @param {string} [colorSpace=SRGBColorSpace] - The color space.
	 * @return {number} The hexadecimal value.
	 */
	getHex( colorSpace = SRGBColorSpace ) {

		ColorManagement.workingToColorSpace( _color.copy( this ), colorSpace );

		return Math.round( clamp( _color.r * 255, 0, 255 ) ) * 65536 + Math.round( clamp( _color.g * 255, 0, 255 ) ) * 256 + Math.round( clamp( _color.b * 255, 0, 255 ) );

	}

	/**
	 * Returns the hexadecimal value of this color as a string (for example, 'FFFFFF').
	 *
	 * @param {string} [colorSpace=SRGBColorSpace] - The color space.
	 * @return {string} The hexadecimal value as a string.
	 */
	getHexString( colorSpace = SRGBColorSpace ) {

		return ( '000000' + this.getHex( colorSpace ).toString( 16 ) ).slice( - 6 );

	}

	/**
	 * Converts the colors RGB values into the HSL format and stores them into the
	 * given target object.
	 *
	 * @param {{h:number,s:number,l:number}} target - The target object that is used to store the method's result.
	 * @param {string} [colorSpace=ColorManagement.workingColorSpace] - The color space.
	 * @return {{h:number,s:number,l:number}} The HSL representation of this color.
	 */
	getHSL( target, colorSpace = ColorManagement.workingColorSpace ) {

		// h,s,l ranges are in 0.0 - 1.0

		ColorManagement.workingToColorSpace( _color.copy( this ), colorSpace );

		const r = _color.r, g = _color.g, b = _color.b;

		const max = Math.max( r, g, b );
		const min = Math.min( r, g, b );

		let hue, saturation;
		const lightness = ( min + max ) / 2.0;

		if ( min === max ) {

			hue = 0;
			saturation = 0;

		} else {

			const delta = max - min;

			saturation = lightness <= 0.5 ? delta / ( max + min ) : delta / ( 2 - max - min );

			switch ( max ) {

				case r: hue = ( g - b ) / delta + ( g < b ? 6 : 0 ); break;
				case g: hue = ( b - r ) / delta + 2; break;
				case b: hue = ( r - g ) / delta + 4; break;

			}

			hue /= 6;

		}

		target.h = hue;
		target.s = saturation;
		target.l = lightness;

		return target;

	}

	/**
	 * Returns the RGB values of this color and stores them into the given target object.
	 *
	 * @param {Color} target - The target color that is used to store the method's result.
	 * @param {string} [colorSpace=ColorManagement.workingColorSpace] - The color space.
	 * @return {Color} The RGB representation of this color.
	 */
	getRGB( target, colorSpace = ColorManagement.workingColorSpace ) {

		ColorManagement.workingToColorSpace( _color.copy( this ), colorSpace );

		target.r = _color.r;
		target.g = _color.g;
		target.b = _color.b;

		return target;

	}

	/**
	 * Returns the value of this color as a CSS style string. Example: `rgb(255,0,0)`.
	 *
	 * @param {string} [colorSpace=SRGBColorSpace] - The color space.
	 * @return {string} The CSS representation of this color.
	 */
	getStyle( colorSpace = SRGBColorSpace ) {

		ColorManagement.workingToColorSpace( _color.copy( this ), colorSpace );

		const r = _color.r, g = _color.g, b = _color.b;

		if ( colorSpace !== SRGBColorSpace ) {

			// Requires CSS Color Module Level 4 (https://www.w3.org/TR/css-color-4/).
			return `color(${ colorSpace } ${ r.toFixed( 3 ) } ${ g.toFixed( 3 ) } ${ b.toFixed( 3 ) })`;

		}

		return `rgb(${ Math.round( r * 255 ) },${ Math.round( g * 255 ) },${ Math.round( b * 255 ) })`;

	}

	/**
	 * Adds the given HSL values to this color's values.
	 * Internally, this converts the color's RGB values to HSL, adds HSL
	 * and then converts the color back to RGB.
	 *
	 * @param {number} h - Hue value between `0.0` and `1.0`.
	 * @param {number} s - Saturation value between `0.0` and `1.0`.
	 * @param {number} l - Lightness value between `0.0` and `1.0`.
	 * @return {Color} A reference to this color.
	 */
	offsetHSL( h, s, l ) {

		this.getHSL( _hslA );

		return this.setHSL( _hslA.h + h, _hslA.s + s, _hslA.l + l );

	}

	/**
	 * Adds the RGB values of the given color to the RGB values of this color.
	 *
	 * @param {Color} color - The color to add.
	 * @return {Color} A reference to this color.
	 */
	add( color ) {

		this.r += color.r;
		this.g += color.g;
		this.b += color.b;

		return this;

	}

	/**
	 * Adds the RGB values of the given colors and stores the result in this instance.
	 *
	 * @param {Color} color1 - The first color.
	 * @param {Color} color2 - The second color.
	 * @return {Color} A reference to this color.
	 */
	addColors( color1, color2 ) {

		this.r = color1.r + color2.r;
		this.g = color1.g + color2.g;
		this.b = color1.b + color2.b;

		return this;

	}

	/**
	 * Adds the given scalar value to the RGB values of this color.
	 *
	 * @param {number} s - The scalar to add.
	 * @return {Color} A reference to this color.
	 */
	addScalar( s ) {

		this.r += s;
		this.g += s;
		this.b += s;

		return this;

	}

	/**
	 * Subtracts the RGB values of the given color from the RGB values of this color.
	 *
	 * @param {Color} color - The color to subtract.
	 * @return {Color} A reference to this color.
	 */
	sub( color ) {

		this.r = Math.max( 0, this.r - color.r );
		this.g = Math.max( 0, this.g - color.g );
		this.b = Math.max( 0, this.b - color.b );

		return this;

	}

	/**
	 * Multiplies the RGB values of the given color with the RGB values of this color.
	 *
	 * @param {Color} color - The color to multiply.
	 * @return {Color} A reference to this color.
	 */
	multiply( color ) {

		this.r *= color.r;
		this.g *= color.g;
		this.b *= color.b;

		return this;

	}

	/**
	 * Multiplies the given scalar value with the RGB values of this color.
	 *
	 * @param {number} s - The scalar to multiply.
	 * @return {Color} A reference to this color.
	 */
	multiplyScalar( s ) {

		this.r *= s;
		this.g *= s;
		this.b *= s;

		return this;

	}

	/**
	 * Linearly interpolates this color's RGB values toward the RGB values of the
	 * given color. The alpha argument can be thought of as the ratio between
	 * the two colors, where `0.0` is this color and `1.0` is the first argument.
	 *
	 * @param {Color} color - The color to converge on.
	 * @param {number} alpha - The interpolation factor in the closed interval `[0,1]`.
	 * @return {Color} A reference to this color.
	 */
	lerp( color, alpha ) {

		this.r += ( color.r - this.r ) * alpha;
		this.g += ( color.g - this.g ) * alpha;
		this.b += ( color.b - this.b ) * alpha;

		return this;

	}

	/**
	 * Linearly interpolates between the given colors and stores the result in this instance.
	 * The alpha argument can be thought of as the ratio between the two colors, where `0.0`
	 * is the first and `1.0` is the second color.
	 *
	 * @param {Color} color1 - The first color.
	 * @param {Color} color2 - The second color.
	 * @param {number} alpha - The interpolation factor in the closed interval `[0,1]`.
	 * @return {Color} A reference to this color.
	 */
	lerpColors( color1, color2, alpha ) {

		this.r = color1.r + ( color2.r - color1.r ) * alpha;
		this.g = color1.g + ( color2.g - color1.g ) * alpha;
		this.b = color1.b + ( color2.b - color1.b ) * alpha;

		return this;

	}

	/**
	 * Linearly interpolates this color's HSL values toward the HSL values of the
	 * given color. It differs from {@link Color#lerp} by not interpolating straight
	 * from one color to the other, but instead going through all the hues in between
	 * those two colors. The alpha argument can be thought of as the ratio between
	 * the two colors, where 0.0 is this color and 1.0 is the first argument.
	 *
	 * @param {Color} color - The color to converge on.
	 * @param {number} alpha - The interpolation factor in the closed interval `[0,1]`.
	 * @return {Color} A reference to this color.
	 */
	lerpHSL( color, alpha ) {

		this.getHSL( _hslA );
		color.getHSL( _hslB );

		const h = lerp( _hslA.h, _hslB.h, alpha );
		const s = lerp( _hslA.s, _hslB.s, alpha );
		const l = lerp( _hslA.l, _hslB.l, alpha );

		this.setHSL( h, s, l );

		return this;

	}

	/**
	 * Sets the color's RGB components from the given 3D vector.
	 *
	 * @param {Vector3} v - The vector to set.
	 * @return {Color} A reference to this color.
	 */
	setFromVector3( v ) {

		this.r = v.x;
		this.g = v.y;
		this.b = v.z;

		return this;

	}

	/**
	 * Transforms this color with the given 3x3 matrix.
	 *
	 * @param {Matrix3} m - The matrix.
	 * @return {Color} A reference to this color.
	 */
	applyMatrix3( m ) {

		const r = this.r, g = this.g, b = this.b;
		const e = m.elements;

		this.r = e[ 0 ] * r + e[ 3 ] * g + e[ 6 ] * b;
		this.g = e[ 1 ] * r + e[ 4 ] * g + e[ 7 ] * b;
		this.b = e[ 2 ] * r + e[ 5 ] * g + e[ 8 ] * b;

		return this;

	}

	/**
	 * Returns `true` if this color is equal with the given one.
	 *
	 * @param {Color} c - The color to test for equality.
	 * @return {boolean} Whether this bounding color is equal with the given one.
	 */
	equals( c ) {

		return ( c.r === this.r ) && ( c.g === this.g ) && ( c.b === this.b );

	}

	/**
	 * Sets this color's RGB components from the given array.
	 *
	 * @param {Array<number>} array - An array holding the RGB values.
	 * @param {number} [offset=0] - The offset into the array.
	 * @return {Color} A reference to this color.
	 */
	fromArray( array, offset = 0 ) {

		this.r = array[ offset ];
		this.g = array[ offset + 1 ];
		this.b = array[ offset + 2 ];

		return this;

	}

	/**
	 * Writes the RGB components of this color to the given array. If no array is provided,
	 * the method returns a new instance.
	 *
	 * @param {Array<number>} [array=[]] - The target array holding the color components.
	 * @param {number} [offset=0] - Index of the first element in the array.
	 * @return {Array<number>} The color components.
	 */
	toArray( array = [], offset = 0 ) {

		array[ offset ] = this.r;
		array[ offset + 1 ] = this.g;
		array[ offset + 2 ] = this.b;

		return array;

	}

	/**
	 * Sets the components of this color from the given buffer attribute.
	 *
	 * @param {BufferAttribute} attribute - The buffer attribute holding color data.
	 * @param {number} index - The index into the attribute.
	 * @return {Color} A reference to this color.
	 */
	fromBufferAttribute( attribute, index ) {

		this.r = attribute.getX( index );
		this.g = attribute.getY( index );
		this.b = attribute.getZ( index );

		return this;

	}

	/**
	 * This methods defines the serialization result of this class. Returns the color
	 * as a hexadecimal value.
	 *
	 * @return {number} The hexadecimal value.
	 */
	toJSON() {

		return this.getHex();

	}

	*[ Symbol.iterator ]() {

		yield this.r;
		yield this.g;
		yield this.b;

	}

}
```
</details>

#### Methods

##### `set(r: string | number | Color, g: number, b: number): Color`

<details><summary>Code</summary>

```ts
set( r, g, b ) {

		if ( g === undefined && b === undefined ) {

			// r is THREE.Color, hex or string

			const value = r;

			if ( value && value.isColor ) {

				this.copy( value );

			} else if ( typeof value === 'number' ) {

				this.setHex( value );

			} else if ( typeof value === 'string' ) {

				this.setStyle( value );

			}

		} else {

			this.setRGB( r, g, b );

		}

		return this;

	}
```
</details>

##### `setScalar(scalar: number): Color`

<details><summary>Code</summary>

```ts
setScalar( scalar ) {

		this.r = scalar;
		this.g = scalar;
		this.b = scalar;

		return this;

	}
```
</details>

##### `setHex(hex: number, colorSpace: string): Color`

<details><summary>Code</summary>

```ts
setHex( hex, colorSpace = SRGBColorSpace ) {

		hex = Math.floor( hex );

		this.r = ( hex >> 16 & 255 ) / 255;
		this.g = ( hex >> 8 & 255 ) / 255;
		this.b = ( hex & 255 ) / 255;

		ColorManagement.colorSpaceToWorking( this, colorSpace );

		return this;

	}
```
</details>

##### `setRGB(r: number, g: number, b: number, colorSpace: string): Color`

<details><summary>Code</summary>

```ts
setRGB( r, g, b, colorSpace = ColorManagement.workingColorSpace ) {

		this.r = r;
		this.g = g;
		this.b = b;

		ColorManagement.colorSpaceToWorking( this, colorSpace );

		return this;

	}
```
</details>

##### `setHSL(h: number, s: number, l: number, colorSpace: string): Color`

<details><summary>Code</summary>

```ts
setHSL( h, s, l, colorSpace = ColorManagement.workingColorSpace ) {

		// h,s,l ranges are in 0.0 - 1.0
		h = euclideanModulo( h, 1 );
		s = clamp( s, 0, 1 );
		l = clamp( l, 0, 1 );

		if ( s === 0 ) {

			this.r = this.g = this.b = l;

		} else {

			const p = l <= 0.5 ? l * ( 1 + s ) : l + s - ( l * s );
			const q = ( 2 * l ) - p;

			this.r = hue2rgb( q, p, h + 1 / 3 );
			this.g = hue2rgb( q, p, h );
			this.b = hue2rgb( q, p, h - 1 / 3 );

		}

		ColorManagement.colorSpaceToWorking( this, colorSpace );

		return this;

	}
```
</details>

##### `setStyle(style: string, colorSpace: string): Color`

<details><summary>Code</summary>

```ts
setStyle( style, colorSpace = SRGBColorSpace ) {

		function handleAlpha( string ) {

			if ( string === undefined ) return;

			if ( parseFloat( string ) < 1 ) {

				console.warn( 'THREE.Color: Alpha component of ' + style + ' will be ignored.' );

			}

		}


		let m;

		if ( m = /^(\w+)\(([^\)]*)\)/.exec( style ) ) {

			// rgb / hsl

			let color;
			const name = m[ 1 ];
			const components = m[ 2 ];

			switch ( name ) {

				case 'rgb':
				case 'rgba':

					if ( color = /^\s*(\d+)\s*,\s*(\d+)\s*,\s*(\d+)\s*(?:,\s*(\d*\.?\d+)\s*)?$/.exec( components ) ) {

						// rgb(255,0,0) rgba(255,0,0,0.5)

						handleAlpha( color[ 4 ] );

						return this.setRGB(
							Math.min( 255, parseInt( color[ 1 ], 10 ) ) / 255,
							Math.min( 255, parseInt( color[ 2 ], 10 ) ) / 255,
							Math.min( 255, parseInt( color[ 3 ], 10 ) ) / 255,
							colorSpace
						);

					}

					if ( color = /^\s*(\d+)\%\s*,\s*(\d+)\%\s*,\s*(\d+)\%\s*(?:,\s*(\d*\.?\d+)\s*)?$/.exec( components ) ) {

						// rgb(100%,0%,0%) rgba(100%,0%,0%,0.5)

						handleAlpha( color[ 4 ] );

						return this.setRGB(
							Math.min( 100, parseInt( color[ 1 ], 10 ) ) / 100,
							Math.min( 100, parseInt( color[ 2 ], 10 ) ) / 100,
							Math.min( 100, parseInt( color[ 3 ], 10 ) ) / 100,
							colorSpace
						);

					}

					break;

				case 'hsl':
				case 'hsla':

					if ( color = /^\s*(\d*\.?\d+)\s*,\s*(\d*\.?\d+)\%\s*,\s*(\d*\.?\d+)\%\s*(?:,\s*(\d*\.?\d+)\s*)?$/.exec( components ) ) {

						// hsl(120,50%,50%) hsla(120,50%,50%,0.5)

						handleAlpha( color[ 4 ] );

						return this.setHSL(
							parseFloat( color[ 1 ] ) / 360,
							parseFloat( color[ 2 ] ) / 100,
							parseFloat( color[ 3 ] ) / 100,
							colorSpace
						);

					}

					break;

				default:

					console.warn( 'THREE.Color: Unknown color model ' + style );

			}

		} else if ( m = /^\#([A-Fa-f\d]+)$/.exec( style ) ) {

			// hex color

			const hex = m[ 1 ];
			const size = hex.length;

			if ( size === 3 ) {

				// #ff0
				return this.setRGB(
					parseInt( hex.charAt( 0 ), 16 ) / 15,
					parseInt( hex.charAt( 1 ), 16 ) / 15,
					parseInt( hex.charAt( 2 ), 16 ) / 15,
					colorSpace
				);

			} else if ( size === 6 ) {

				// #ff0000
				return this.setHex( parseInt( hex, 16 ), colorSpace );

			} else {

				console.warn( 'THREE.Color: Invalid hex color ' + style );

			}

		} else if ( style && style.length > 0 ) {

			return this.setColorName( style, colorSpace );

		}

		return this;

	}
```
</details>

##### `setColorName(style: string, colorSpace: string): Color`

<details><summary>Code</summary>

```ts
setColorName( style, colorSpace = SRGBColorSpace ) {

		// color keywords
		const hex = _colorKeywords[ style.toLowerCase() ];

		if ( hex !== undefined ) {

			// red
			this.setHex( hex, colorSpace );

		} else {

			// unknown color
			console.warn( 'THREE.Color: Unknown color ' + style );

		}

		return this;

	}
```
</details>

##### `clone(): Color`

<details><summary>Code</summary>

```ts
clone() {

		return new this.constructor( this.r, this.g, this.b );

	}
```
</details>

##### `copy(color: Color): Color`

<details><summary>Code</summary>

```ts
copy( color ) {

		this.r = color.r;
		this.g = color.g;
		this.b = color.b;

		return this;

	}
```
</details>

##### `copySRGBToLinear(color: Color): Color`

<details><summary>Code</summary>

```ts
copySRGBToLinear( color ) {

		this.r = SRGBToLinear( color.r );
		this.g = SRGBToLinear( color.g );
		this.b = SRGBToLinear( color.b );

		return this;

	}
```
</details>

##### `copyLinearToSRGB(color: Color): Color`

<details><summary>Code</summary>

```ts
copyLinearToSRGB( color ) {

		this.r = LinearToSRGB( color.r );
		this.g = LinearToSRGB( color.g );
		this.b = LinearToSRGB( color.b );

		return this;

	}
```
</details>

##### `convertSRGBToLinear(): Color`

<details><summary>Code</summary>

```ts
convertSRGBToLinear() {

		this.copySRGBToLinear( this );

		return this;

	}
```
</details>

##### `convertLinearToSRGB(): Color`

<details><summary>Code</summary>

```ts
convertLinearToSRGB() {

		this.copyLinearToSRGB( this );

		return this;

	}
```
</details>

##### `getHex(colorSpace: string): number`

<details><summary>Code</summary>

```ts
getHex( colorSpace = SRGBColorSpace ) {

		ColorManagement.workingToColorSpace( _color.copy( this ), colorSpace );

		return Math.round( clamp( _color.r * 255, 0, 255 ) ) * 65536 + Math.round( clamp( _color.g * 255, 0, 255 ) ) * 256 + Math.round( clamp( _color.b * 255, 0, 255 ) );

	}
```
</details>

##### `getHexString(colorSpace: string): string`

<details><summary>Code</summary>

```ts
getHexString( colorSpace = SRGBColorSpace ) {

		return ( '000000' + this.getHex( colorSpace ).toString( 16 ) ).slice( - 6 );

	}
```
</details>

##### `getHSL(target: { h: number; s: number; l: number; }, colorSpace: string): { h: number; s: number; l: number; }`

<details><summary>Code</summary>

```ts
getHSL( target, colorSpace = ColorManagement.workingColorSpace ) {

		// h,s,l ranges are in 0.0 - 1.0

		ColorManagement.workingToColorSpace( _color.copy( this ), colorSpace );

		const r = _color.r, g = _color.g, b = _color.b;

		const max = Math.max( r, g, b );
		const min = Math.min( r, g, b );

		let hue, saturation;
		const lightness = ( min + max ) / 2.0;

		if ( min === max ) {

			hue = 0;
			saturation = 0;

		} else {

			const delta = max - min;

			saturation = lightness <= 0.5 ? delta / ( max + min ) : delta / ( 2 - max - min );

			switch ( max ) {

				case r: hue = ( g - b ) / delta + ( g < b ? 6 : 0 ); break;
				case g: hue = ( b - r ) / delta + 2; break;
				case b: hue = ( r - g ) / delta + 4; break;

			}

			hue /= 6;

		}

		target.h = hue;
		target.s = saturation;
		target.l = lightness;

		return target;

	}
```
</details>

##### `getRGB(target: Color, colorSpace: string): Color`

<details><summary>Code</summary>

```ts
getRGB( target, colorSpace = ColorManagement.workingColorSpace ) {

		ColorManagement.workingToColorSpace( _color.copy( this ), colorSpace );

		target.r = _color.r;
		target.g = _color.g;
		target.b = _color.b;

		return target;

	}
```
</details>

##### `getStyle(colorSpace: string): string`

<details><summary>Code</summary>

```ts
getStyle( colorSpace = SRGBColorSpace ) {

		ColorManagement.workingToColorSpace( _color.copy( this ), colorSpace );

		const r = _color.r, g = _color.g, b = _color.b;

		if ( colorSpace !== SRGBColorSpace ) {

			// Requires CSS Color Module Level 4 (https://www.w3.org/TR/css-color-4/).
			return `color(${ colorSpace } ${ r.toFixed( 3 ) } ${ g.toFixed( 3 ) } ${ b.toFixed( 3 ) })`;

		}

		return `rgb(${ Math.round( r * 255 ) },${ Math.round( g * 255 ) },${ Math.round( b * 255 ) })`;

	}
```
</details>

##### `offsetHSL(h: number, s: number, l: number): Color`

<details><summary>Code</summary>

```ts
offsetHSL( h, s, l ) {

		this.getHSL( _hslA );

		return this.setHSL( _hslA.h + h, _hslA.s + s, _hslA.l + l );

	}
```
</details>

##### `add(color: Color): Color`

<details><summary>Code</summary>

```ts
add( color ) {

		this.r += color.r;
		this.g += color.g;
		this.b += color.b;

		return this;

	}
```
</details>

##### `addColors(color1: Color, color2: Color): Color`

<details><summary>Code</summary>

```ts
addColors( color1, color2 ) {

		this.r = color1.r + color2.r;
		this.g = color1.g + color2.g;
		this.b = color1.b + color2.b;

		return this;

	}
```
</details>

##### `addScalar(s: number): Color`

<details><summary>Code</summary>

```ts
addScalar( s ) {

		this.r += s;
		this.g += s;
		this.b += s;

		return this;

	}
```
</details>

##### `sub(color: Color): Color`

<details><summary>Code</summary>

```ts
sub( color ) {

		this.r = Math.max( 0, this.r - color.r );
		this.g = Math.max( 0, this.g - color.g );
		this.b = Math.max( 0, this.b - color.b );

		return this;

	}
```
</details>

##### `multiply(color: Color): Color`

<details><summary>Code</summary>

```ts
multiply( color ) {

		this.r *= color.r;
		this.g *= color.g;
		this.b *= color.b;

		return this;

	}
```
</details>

##### `multiplyScalar(s: number): Color`

<details><summary>Code</summary>

```ts
multiplyScalar( s ) {

		this.r *= s;
		this.g *= s;
		this.b *= s;

		return this;

	}
```
</details>

##### `lerp(color: Color, alpha: number): Color`

<details><summary>Code</summary>

```ts
lerp( color, alpha ) {

		this.r += ( color.r - this.r ) * alpha;
		this.g += ( color.g - this.g ) * alpha;
		this.b += ( color.b - this.b ) * alpha;

		return this;

	}
```
</details>

##### `lerpColors(color1: Color, color2: Color, alpha: number): Color`

<details><summary>Code</summary>

```ts
lerpColors( color1, color2, alpha ) {

		this.r = color1.r + ( color2.r - color1.r ) * alpha;
		this.g = color1.g + ( color2.g - color1.g ) * alpha;
		this.b = color1.b + ( color2.b - color1.b ) * alpha;

		return this;

	}
```
</details>

##### `lerpHSL(color: Color, alpha: number): Color`

<details><summary>Code</summary>

```ts
lerpHSL( color, alpha ) {

		this.getHSL( _hslA );
		color.getHSL( _hslB );

		const h = lerp( _hslA.h, _hslB.h, alpha );
		const s = lerp( _hslA.s, _hslB.s, alpha );
		const l = lerp( _hslA.l, _hslB.l, alpha );

		this.setHSL( h, s, l );

		return this;

	}
```
</details>

##### `setFromVector3(v: Vector3): Color`

<details><summary>Code</summary>

```ts
setFromVector3( v ) {

		this.r = v.x;
		this.g = v.y;
		this.b = v.z;

		return this;

	}
```
</details>

##### `applyMatrix3(m: Matrix3): Color`

<details><summary>Code</summary>

```ts
applyMatrix3( m ) {

		const r = this.r, g = this.g, b = this.b;
		const e = m.elements;

		this.r = e[ 0 ] * r + e[ 3 ] * g + e[ 6 ] * b;
		this.g = e[ 1 ] * r + e[ 4 ] * g + e[ 7 ] * b;
		this.b = e[ 2 ] * r + e[ 5 ] * g + e[ 8 ] * b;

		return this;

	}
```
</details>

##### `equals(c: Color): boolean`

<details><summary>Code</summary>

```ts
equals( c ) {

		return ( c.r === this.r ) && ( c.g === this.g ) && ( c.b === this.b );

	}
```
</details>

##### `fromArray(array: number[], offset: number): Color`

<details><summary>Code</summary>

```ts
fromArray( array, offset = 0 ) {

		this.r = array[ offset ];
		this.g = array[ offset + 1 ];
		this.b = array[ offset + 2 ];

		return this;

	}
```
</details>

##### `toArray(array: number[], offset: number): number[]`

<details><summary>Code</summary>

```ts
toArray( array = [], offset = 0 ) {

		array[ offset ] = this.r;
		array[ offset + 1 ] = this.g;
		array[ offset + 2 ] = this.b;

		return array;

	}
```
</details>

##### `fromBufferAttribute(attribute: BufferAttribute, index: number): Color`

<details><summary>Code</summary>

```ts
fromBufferAttribute( attribute, index ) {

		this.r = attribute.getX( index );
		this.g = attribute.getY( index );
		this.b = attribute.getZ( index );

		return this;

	}
```
</details>

##### `toJSON(): number`

<details><summary>Code</summary>

```ts
toJSON() {

		return this.getHex();

	}
```
</details>

##### `[ Symbol.iterator ](): Generator<number, void, unknown>`

<details><summary>Code</summary>

```ts
*[ Symbol.iterator ]() {

		yield this.r;
		yield this.g;
		yield this.b;

	}
```
</details>


---