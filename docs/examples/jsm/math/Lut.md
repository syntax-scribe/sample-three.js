[⬅️ Back to Table of Contents](../../../index.md)

# 📄 `Lut.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 9 |
| 🧱 Classes | 1 |
| 📦 Imports | 3 |
| 📊 Variables & Constants | 15 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)
- [Classes](#classes)

## 🛠️ File Location:
📂 **`examples/jsm/math/Lut.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `Color` | `three` |
| `LinearSRGBColorSpace` | `three` |
| `MathUtils` | `three` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `step` | `number` | let/var | `1.0 / this.n` | ✗ |
| `minColor` | `any` | let/var | `new Color()` | ✗ |
| `maxColor` | `any` | let/var | `new Color()` | ✗ |
| `alpha` | `number` | let/var | `i * step` | ✗ |
| `min` | `any` | let/var | `this.map[ j ][ 0 ]` | ✗ |
| `max` | `any` | let/var | `this.map[ j + 1 ][ 0 ]` | ✗ |
| `data` | `Uint8ClampedArray<ArrayBufferLike>` | let/var | `imageData.data` | ✗ |
| `k` | `number` | let/var | `0` | ✗ |
| `step` | `number` | let/var | `1.0 / this.n` | ✗ |
| `minColor` | `any` | let/var | `new Color()` | ✗ |
| `maxColor` | `any` | let/var | `new Color()` | ✗ |
| `finalColor` | `any` | let/var | `new Color()` | ✗ |
| `min` | `any` | let/var | `this.map[ j - 1 ][ 0 ]` | ✗ |
| `max` | `any` | let/var | `this.map[ j ][ 0 ]` | ✗ |
| `ColorMapKeywords` | `{ rainbow: number[][]; cooltowarm: nu...` | let/var | `{ 'rainbow': [[ 0.0, 0x0000FF ], [ 0.2, 0x00FFFF ], [ 0.5, 0x00FF00 ], [ 0.8,...` | ✗ |


---

## Functions

### `Lut.set(value: Lut): Lut`

**JSDoc:**
```typescript
/**
	 * Sets the given LUT.
	 *
	 * @param {Lut} value - The LUT to set.
	 * @return {Lut} A reference to this LUT.
	 */
```

**Parameters:**

- **`value`** `Lut`

**Returns:** `Lut`

**Calls:**

- `this.copy`

<details><summary>Code</summary>

```typescript
set( value ) {

		if ( value.isLut === true ) {

			this.copy( value );

		}

		return this;

	}
```
</details>

### `Lut.setMin(min: number): Lut`

**JSDoc:**
```typescript
/**
	 * Sets the minimum value to be represented with this LUT.
	 *
	 * @param {number} min - The minimum value to be represented with the lookup table.
	 * @return {Lut} A reference to this LUT.
	 */
```

**Parameters:**

- **`min`** `number`

**Returns:** `Lut`

<details><summary>Code</summary>

```typescript
setMin( min ) {

		this.minV = min;

		return this;

	}
```
</details>

### `Lut.setMax(max: number): Lut`

**JSDoc:**
```typescript
/**
	 * Sets the maximum value to be represented with this LUT.
	 *
	 * @param {number} max - The maximum value to be represented with the lookup table.
	 * @return {Lut} A reference to this LUT.
	 */
```

**Parameters:**

- **`max`** `number`

**Returns:** `Lut`

<details><summary>Code</summary>

```typescript
setMax( max ) {

		this.maxV = max;

		return this;

	}
```
</details>

### `Lut.setColorMap(colormap: string, count: number): Lut`

**JSDoc:**
```typescript
/**
	 * Configure the lookup table for the given color map and number of colors.
	 *
	 * @param {string} colormap - The name of the color map.
	 * @param {number} [count=32] - The number of colors.
	 * @return {Lut} A reference to this LUT.
	 */
```

**Parameters:**

- **`colormap`** `string`
- **`count`** `number`

**Returns:** `Lut`

**Calls:**

- `this.lut.push`
- `minColor.setHex`
- `maxColor.setHex`
- `new Color().lerpColors`

**Internal Comments:**
```
// sample at 0 (x5)
// sample at 1/n, ..., (n-1)/n
// sample at 1 (x5)
```

<details><summary>Code</summary>

```typescript
setColorMap( colormap, count = 32 ) {

		this.map = ColorMapKeywords[ colormap ] || ColorMapKeywords.rainbow;
		this.n = count;

		const step = 1.0 / this.n;
		const minColor = new Color();
		const maxColor = new Color();

		this.lut.length = 0;

		// sample at 0

		this.lut.push( new Color( this.map[ 0 ][ 1 ] ) );

		// sample at 1/n, ..., (n-1)/n

		for ( let i = 1; i < count; i ++ ) {

			const alpha = i * step;

			for ( let j = 0; j < this.map.length - 1; j ++ ) {

				if ( alpha > this.map[ j ][ 0 ] && alpha <= this.map[ j + 1 ][ 0 ] ) {

					const min = this.map[ j ][ 0 ];
					const max = this.map[ j + 1 ][ 0 ];

					minColor.setHex( this.map[ j ][ 1 ], LinearSRGBColorSpace );
					maxColor.setHex( this.map[ j + 1 ][ 1 ], LinearSRGBColorSpace );

					const color = new Color().lerpColors( minColor, maxColor, ( alpha - min ) / ( max - min ) );

					this.lut.push( color );

				}

			}

		}

		// sample at 1

		this.lut.push( new Color( this.map[ this.map.length - 1 ][ 1 ] ) );

		return this;

	}
```
</details>

### `Lut.copy(lut: Lut): Lut`

**JSDoc:**
```typescript
/**
	 * Copies the given lut.
	 *
	 * @param {Lut} lut - The LUT to copy.
	 * @return {Lut} A reference to this LUT.
	 */
```

**Parameters:**

- **`lut`** `Lut`

**Returns:** `Lut`

<details><summary>Code</summary>

```typescript
copy( lut ) {

		this.lut = lut.lut;
		this.map = lut.map;
		this.n = lut.n;
		this.minV = lut.minV;
		this.maxV = lut.maxV;

		return this;

	}
```
</details>

### `Lut.getColor(alpha: number): Color`

**JSDoc:**
```typescript
/**
	 * Returns an instance of Color for the given data value.
	 *
	 * @param {number} alpha - The value to lookup.
	 * @return {Color} The color from the LUT.
	 */
```

**Parameters:**

- **`alpha`** `number`

**Returns:** `Color`

**Calls:**

- `MathUtils.clamp`
- `Math.round`

<details><summary>Code</summary>

```typescript
getColor( alpha ) {

		alpha = MathUtils.clamp( alpha, this.minV, this.maxV );

		alpha = ( alpha - this.minV ) / ( this.maxV - this.minV );

		const colorPosition = Math.round( alpha * this.n );

		return this.lut[ colorPosition ];

	}
```
</details>

### `Lut.addColorMap(name: string, arrayOfColors: any[]): Lut`

**JSDoc:**
```typescript
/**
	 * Adds a color map to this Lut instance.
	 *
	 * @param {string} name - The name of the color map.
	 * @param {Array} arrayOfColors - An array of color values. Each value is an array
	 * holding a threshold and the actual color value as a hexadecimal number.
	 * @return {Lut} A reference to this LUT.
	 */
```

**Parameters:**

- **`name`** `string`
- **`arrayOfColors`** `any[]`

**Returns:** `Lut`

<details><summary>Code</summary>

```typescript
addColorMap( name, arrayOfColors ) {

		ColorMapKeywords[ name ] = arrayOfColors;

		return this;

	}
```
</details>

### `Lut.createCanvas(): HTMLCanvasElement`

**JSDoc:**
```typescript
/**
	 * Creates a canvas in order to visualize the lookup table as a texture.
	 *
	 * @return {HTMLCanvasElement} The created canvas.
	 */
```

**Returns:** `HTMLCanvasElement`

**Calls:**

- `document.createElement`
- `this.updateCanvas`

<details><summary>Code</summary>

```typescript
createCanvas() {

		const canvas = document.createElement( 'canvas' );
		canvas.width = 1;
		canvas.height = this.n;

		this.updateCanvas( canvas );

		return canvas;

	}
```
</details>

### `Lut.updateCanvas(canvas: HTMLCanvasElement): HTMLCanvasElement`

**JSDoc:**
```typescript
/**
	 * Updates the given canvas with the Lut's data.
	 *
	 * @param {HTMLCanvasElement} canvas - The canvas to update.
	 * @return {HTMLCanvasElement} The updated canvas.
	 */
```

**Parameters:**

- **`canvas`** `HTMLCanvasElement`

**Returns:** `HTMLCanvasElement`

**Calls:**

- `canvas.getContext`
- `ctx.getImageData`
- `minColor.setHex`
- `maxColor.setHex`
- `finalColor.lerpColors`
- `Math.round`
- `ctx.putImageData`

<details><summary>Code</summary>

```typescript
updateCanvas( canvas ) {

		const ctx = canvas.getContext( '2d', { alpha: false } );

		const imageData = ctx.getImageData( 0, 0, 1, this.n );

		const data = imageData.data;

		let k = 0;

		const step = 1.0 / this.n;

		const minColor = new Color();
		const maxColor = new Color();
		const finalColor = new Color();

		for ( let i = 1; i >= 0; i -= step ) {

			for ( let j = this.map.length - 1; j >= 0; j -- ) {

				if ( i < this.map[ j ][ 0 ] && i >= this.map[ j - 1 ][ 0 ] ) {

					const min = this.map[ j - 1 ][ 0 ];
					const max = this.map[ j ][ 0 ];

					minColor.setHex( this.map[ j - 1 ][ 1 ], LinearSRGBColorSpace );
					maxColor.setHex( this.map[ j ][ 1 ], LinearSRGBColorSpace );

					finalColor.lerpColors( minColor, maxColor, ( i - min ) / ( max - min ) );

					data[ k * 4 ] = Math.round( finalColor.r * 255 );
					data[ k * 4 + 1 ] = Math.round( finalColor.g * 255 );
					data[ k * 4 + 2 ] = Math.round( finalColor.b * 255 );
					data[ k * 4 + 3 ] = 255;

					k += 1;

				}

			}

		}

		ctx.putImageData( imageData, 0, 0 );

		return canvas;

	}
```
</details>


---

## Classes

### `Lut`

<details><summary>Class Code</summary>

```ts
class Lut {

	/**
	 * Constructs a new Lut.
	 *
	 * @param {('rainbow'|'cooltowarm'|'blackbody'|'grayscale')} [colormap='rainbow'] - Sets a colormap from predefined list of colormaps.
	 * @param {number} [count=32] - Sets the number of colors used to represent the data array.
	 */
 	constructor( colormap, count = 32 ) {

		/**
		 * This flag can be used for type testing.
		 *
		 * @type {boolean}
		 * @readonly
		 * @default true
		 */
		this.isLut = true;


		/**
		 * The lookup table for the selected color map
		 *
		 * @type {Array<Color>}
		 */
		this.lut = [];

		/**
		 * The currently selected color map.
		 *
		 * @type {Array}
		 */
		this.map = [];

		/**
		 * The number of colors of the current selected color map.
		 *
		 * @type {number}
		 * @default 32
		 */
		this.n = 0;

		/**
		 * The minimum value to be represented with the lookup table.
		 *
		 * @type {number}
		 * @default 0
		 */
		this.minV = 0;

		/**
		 * The maximum value to be represented with the lookup table.
		 *
		 * @type {number}
		 * @default 1
		 */
		this.maxV = 1;

		this.setColorMap( colormap, count );

	}

	/**
	 * Sets the given LUT.
	 *
	 * @param {Lut} value - The LUT to set.
	 * @return {Lut} A reference to this LUT.
	 */
	set( value ) {

		if ( value.isLut === true ) {

			this.copy( value );

		}

		return this;

	}

	/**
	 * Sets the minimum value to be represented with this LUT.
	 *
	 * @param {number} min - The minimum value to be represented with the lookup table.
	 * @return {Lut} A reference to this LUT.
	 */
	setMin( min ) {

		this.minV = min;

		return this;

	}

	/**
	 * Sets the maximum value to be represented with this LUT.
	 *
	 * @param {number} max - The maximum value to be represented with the lookup table.
	 * @return {Lut} A reference to this LUT.
	 */
	setMax( max ) {

		this.maxV = max;

		return this;

	}

	/**
	 * Configure the lookup table for the given color map and number of colors.
	 *
	 * @param {string} colormap - The name of the color map.
	 * @param {number} [count=32] - The number of colors.
	 * @return {Lut} A reference to this LUT.
	 */
	setColorMap( colormap, count = 32 ) {

		this.map = ColorMapKeywords[ colormap ] || ColorMapKeywords.rainbow;
		this.n = count;

		const step = 1.0 / this.n;
		const minColor = new Color();
		const maxColor = new Color();

		this.lut.length = 0;

		// sample at 0

		this.lut.push( new Color( this.map[ 0 ][ 1 ] ) );

		// sample at 1/n, ..., (n-1)/n

		for ( let i = 1; i < count; i ++ ) {

			const alpha = i * step;

			for ( let j = 0; j < this.map.length - 1; j ++ ) {

				if ( alpha > this.map[ j ][ 0 ] && alpha <= this.map[ j + 1 ][ 0 ] ) {

					const min = this.map[ j ][ 0 ];
					const max = this.map[ j + 1 ][ 0 ];

					minColor.setHex( this.map[ j ][ 1 ], LinearSRGBColorSpace );
					maxColor.setHex( this.map[ j + 1 ][ 1 ], LinearSRGBColorSpace );

					const color = new Color().lerpColors( minColor, maxColor, ( alpha - min ) / ( max - min ) );

					this.lut.push( color );

				}

			}

		}

		// sample at 1

		this.lut.push( new Color( this.map[ this.map.length - 1 ][ 1 ] ) );

		return this;

	}

	/**
	 * Copies the given lut.
	 *
	 * @param {Lut} lut - The LUT to copy.
	 * @return {Lut} A reference to this LUT.
	 */
	copy( lut ) {

		this.lut = lut.lut;
		this.map = lut.map;
		this.n = lut.n;
		this.minV = lut.minV;
		this.maxV = lut.maxV;

		return this;

	}

	/**
	 * Returns an instance of Color for the given data value.
	 *
	 * @param {number} alpha - The value to lookup.
	 * @return {Color} The color from the LUT.
	 */
	getColor( alpha ) {

		alpha = MathUtils.clamp( alpha, this.minV, this.maxV );

		alpha = ( alpha - this.minV ) / ( this.maxV - this.minV );

		const colorPosition = Math.round( alpha * this.n );

		return this.lut[ colorPosition ];

	}

	/**
	 * Adds a color map to this Lut instance.
	 *
	 * @param {string} name - The name of the color map.
	 * @param {Array} arrayOfColors - An array of color values. Each value is an array
	 * holding a threshold and the actual color value as a hexadecimal number.
	 * @return {Lut} A reference to this LUT.
	 */
	addColorMap( name, arrayOfColors ) {

		ColorMapKeywords[ name ] = arrayOfColors;

		return this;

	}

	/**
	 * Creates a canvas in order to visualize the lookup table as a texture.
	 *
	 * @return {HTMLCanvasElement} The created canvas.
	 */
	createCanvas() {

		const canvas = document.createElement( 'canvas' );
		canvas.width = 1;
		canvas.height = this.n;

		this.updateCanvas( canvas );

		return canvas;

	}

	/**
	 * Updates the given canvas with the Lut's data.
	 *
	 * @param {HTMLCanvasElement} canvas - The canvas to update.
	 * @return {HTMLCanvasElement} The updated canvas.
	 */
	updateCanvas( canvas ) {

		const ctx = canvas.getContext( '2d', { alpha: false } );

		const imageData = ctx.getImageData( 0, 0, 1, this.n );

		const data = imageData.data;

		let k = 0;

		const step = 1.0 / this.n;

		const minColor = new Color();
		const maxColor = new Color();
		const finalColor = new Color();

		for ( let i = 1; i >= 0; i -= step ) {

			for ( let j = this.map.length - 1; j >= 0; j -- ) {

				if ( i < this.map[ j ][ 0 ] && i >= this.map[ j - 1 ][ 0 ] ) {

					const min = this.map[ j - 1 ][ 0 ];
					const max = this.map[ j ][ 0 ];

					minColor.setHex( this.map[ j - 1 ][ 1 ], LinearSRGBColorSpace );
					maxColor.setHex( this.map[ j ][ 1 ], LinearSRGBColorSpace );

					finalColor.lerpColors( minColor, maxColor, ( i - min ) / ( max - min ) );

					data[ k * 4 ] = Math.round( finalColor.r * 255 );
					data[ k * 4 + 1 ] = Math.round( finalColor.g * 255 );
					data[ k * 4 + 2 ] = Math.round( finalColor.b * 255 );
					data[ k * 4 + 3 ] = 255;

					k += 1;

				}

			}

		}

		ctx.putImageData( imageData, 0, 0 );

		return canvas;

	}

}
```
</details>

#### Methods

##### `set(value: Lut): Lut`

<details><summary>Code</summary>

```ts
set( value ) {

		if ( value.isLut === true ) {

			this.copy( value );

		}

		return this;

	}
```
</details>

##### `setMin(min: number): Lut`

<details><summary>Code</summary>

```ts
setMin( min ) {

		this.minV = min;

		return this;

	}
```
</details>

##### `setMax(max: number): Lut`

<details><summary>Code</summary>

```ts
setMax( max ) {

		this.maxV = max;

		return this;

	}
```
</details>

##### `setColorMap(colormap: string, count: number): Lut`

<details><summary>Code</summary>

```ts
setColorMap( colormap, count = 32 ) {

		this.map = ColorMapKeywords[ colormap ] || ColorMapKeywords.rainbow;
		this.n = count;

		const step = 1.0 / this.n;
		const minColor = new Color();
		const maxColor = new Color();

		this.lut.length = 0;

		// sample at 0

		this.lut.push( new Color( this.map[ 0 ][ 1 ] ) );

		// sample at 1/n, ..., (n-1)/n

		for ( let i = 1; i < count; i ++ ) {

			const alpha = i * step;

			for ( let j = 0; j < this.map.length - 1; j ++ ) {

				if ( alpha > this.map[ j ][ 0 ] && alpha <= this.map[ j + 1 ][ 0 ] ) {

					const min = this.map[ j ][ 0 ];
					const max = this.map[ j + 1 ][ 0 ];

					minColor.setHex( this.map[ j ][ 1 ], LinearSRGBColorSpace );
					maxColor.setHex( this.map[ j + 1 ][ 1 ], LinearSRGBColorSpace );

					const color = new Color().lerpColors( minColor, maxColor, ( alpha - min ) / ( max - min ) );

					this.lut.push( color );

				}

			}

		}

		// sample at 1

		this.lut.push( new Color( this.map[ this.map.length - 1 ][ 1 ] ) );

		return this;

	}
```
</details>

##### `copy(lut: Lut): Lut`

<details><summary>Code</summary>

```ts
copy( lut ) {

		this.lut = lut.lut;
		this.map = lut.map;
		this.n = lut.n;
		this.minV = lut.minV;
		this.maxV = lut.maxV;

		return this;

	}
```
</details>

##### `getColor(alpha: number): Color`

<details><summary>Code</summary>

```ts
getColor( alpha ) {

		alpha = MathUtils.clamp( alpha, this.minV, this.maxV );

		alpha = ( alpha - this.minV ) / ( this.maxV - this.minV );

		const colorPosition = Math.round( alpha * this.n );

		return this.lut[ colorPosition ];

	}
```
</details>

##### `addColorMap(name: string, arrayOfColors: any[]): Lut`

<details><summary>Code</summary>

```ts
addColorMap( name, arrayOfColors ) {

		ColorMapKeywords[ name ] = arrayOfColors;

		return this;

	}
```
</details>

##### `createCanvas(): HTMLCanvasElement`

<details><summary>Code</summary>

```ts
createCanvas() {

		const canvas = document.createElement( 'canvas' );
		canvas.width = 1;
		canvas.height = this.n;

		this.updateCanvas( canvas );

		return canvas;

	}
```
</details>

##### `updateCanvas(canvas: HTMLCanvasElement): HTMLCanvasElement`

<details><summary>Code</summary>

```ts
updateCanvas( canvas ) {

		const ctx = canvas.getContext( '2d', { alpha: false } );

		const imageData = ctx.getImageData( 0, 0, 1, this.n );

		const data = imageData.data;

		let k = 0;

		const step = 1.0 / this.n;

		const minColor = new Color();
		const maxColor = new Color();
		const finalColor = new Color();

		for ( let i = 1; i >= 0; i -= step ) {

			for ( let j = this.map.length - 1; j >= 0; j -- ) {

				if ( i < this.map[ j ][ 0 ] && i >= this.map[ j - 1 ][ 0 ] ) {

					const min = this.map[ j - 1 ][ 0 ];
					const max = this.map[ j ][ 0 ];

					minColor.setHex( this.map[ j - 1 ][ 1 ], LinearSRGBColorSpace );
					maxColor.setHex( this.map[ j ][ 1 ], LinearSRGBColorSpace );

					finalColor.lerpColors( minColor, maxColor, ( i - min ) / ( max - min ) );

					data[ k * 4 ] = Math.round( finalColor.r * 255 );
					data[ k * 4 + 1 ] = Math.round( finalColor.g * 255 );
					data[ k * 4 + 2 ] = Math.round( finalColor.b * 255 );
					data[ k * 4 + 3 ] = 255;

					k += 1;

				}

			}

		}

		ctx.putImageData( imageData, 0, 0 );

		return canvas;

	}
```
</details>


---