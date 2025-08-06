[⬅️ Back to Table of Contents](../../index.md)

# 📄 `ColorManagement.js`

## 📊 Analysis Summary

| Metric | Count |
|--------|-------|
| 🔧 Functions | 75 |
| 📦 Imports | 7 |
| 📊 Variables & Constants | 4 |

## 📚 Table of Contents

- [Imports](#imports)
- [Variables & Constants](#variables-constants)
- [Functions](#functions)

## 🛠️ File Location:
📂 **`src/math/ColorManagement.js`**

## 📦 Imports

| Name | Source |
|------|--------|
| `SRGBColorSpace` | `../constants.js` |
| `LinearSRGBColorSpace` | `../constants.js` |
| `SRGBTransfer` | `../constants.js` |
| `LinearTransfer` | `../constants.js` |
| `NoColorSpace` | `../constants.js` |
| `Matrix3` | `./Matrix3.js` |
| `warnOnce` | `../utils.js` |


---

## Variables & Constants

| Name | Type | Kind | Value | Exported |
|------|------|------|-------|----------|
| `ColorManagement` | `{ enabled: boolean; workingColorSpace...` | let/var | `{ enabled: true, workingColorSpace: LinearSRGBColorSpace, /** * Implementatio...` | ✗ |
| `REC709_PRIMARIES` | `number[]` | let/var | `[ 0.640, 0.330, 0.300, 0.600, 0.150, 0.060 ]` | ✗ |
| `REC709_LUMINANCE_COEFFICIENTS` | `number[]` | let/var | `[ 0.2126, 0.7152, 0.0722 ]` | ✗ |
| `D65` | `number[]` | let/var | `[ 0.3127, 0.3290 ]` | ✗ |


---

## Functions

### `createColorManagement(): { enabled: boolean; workingColorSpace: string; spaces: {}; convert: (color: any, sourceColorSpace: any, targetColorSpace: any) => any; workingToColorSpace: (color: any, targetColorSpace: any) => any; ... 9 more ...; toWorkingColorSpace: (color: any, sourceColorSpace: any) => any; }`

**Returns:** `{ enabled: boolean; workingColorSpace: string; spaces: {}; convert: (color: any, sourceColorSpace: any, targetColorSpace: any) => any; workingToColorSpace: (color: any, targetColorSpace: any) => any; ... 9 more ...; toWorkingColorSpace: (color: any, sourceColorSpace: any) => any; }`

**Calls:**

- `SRGBToLinear`
- `color.applyMatrix3`
- `LinearToSRGB`
- `this.convert`
- `target.fromArray`
- `Object.assign`
- `targetMatrix
				.copy( this.spaces[ sourceColorSpace ].toXYZ )
				.multiply`
- `warnOnce (from ../utils.js)`
- `ColorManagement.workingToColorSpace`
- `ColorManagement.colorSpaceToWorking`
- `ColorManagement.define`

**Internal Comments:**
```
/**
		 * Implementations of supported color spaces.
		 *
		 * Required:
		 *	- primaries: chromaticity coordinates [ rx ry gx gy bx by ]
		 *	- whitePoint: reference white [ x y ]
		 *	- transfer: transfer function (pre-defined)
		 *	- toXYZ: Matrix3 RGB to XYZ transform
		 *	- fromXYZ: Matrix3 XYZ to RGB transform
		 *	- luminanceCoefficients: RGB luminance coefficients
		 *
		 * Optional:
		 *  - outputColorSpaceConfig: { drawingBufferColorSpace: ColorSpace }
		 *  - workingColorSpaceConfig: { unpackColorSpace: ColorSpace }
		 *
		 * Reference:
		 * - https://www.russellcottrell.com/photo/matrixCalculator.htm
		 */ (x2)
// Internal APIs (x2)
// Deprecated (x2)
/******************************************************************************
	 * sRGB definitions
	 */ (x2)
```

<details><summary>Code</summary>

```typescript
function createColorManagement() {

	const ColorManagement = {

		enabled: true,

		workingColorSpace: LinearSRGBColorSpace,

		/**
		 * Implementations of supported color spaces.
		 *
		 * Required:
		 *	- primaries: chromaticity coordinates [ rx ry gx gy bx by ]
		 *	- whitePoint: reference white [ x y ]
		 *	- transfer: transfer function (pre-defined)
		 *	- toXYZ: Matrix3 RGB to XYZ transform
		 *	- fromXYZ: Matrix3 XYZ to RGB transform
		 *	- luminanceCoefficients: RGB luminance coefficients
		 *
		 * Optional:
		 *  - outputColorSpaceConfig: { drawingBufferColorSpace: ColorSpace }
		 *  - workingColorSpaceConfig: { unpackColorSpace: ColorSpace }
		 *
		 * Reference:
		 * - https://www.russellcottrell.com/photo/matrixCalculator.htm
		 */
		spaces: {},

		convert: function ( color, sourceColorSpace, targetColorSpace ) {

			if ( this.enabled === false || sourceColorSpace === targetColorSpace || ! sourceColorSpace || ! targetColorSpace ) {

				return color;

			}

			if ( this.spaces[ sourceColorSpace ].transfer === SRGBTransfer ) {

				color.r = SRGBToLinear( color.r );
				color.g = SRGBToLinear( color.g );
				color.b = SRGBToLinear( color.b );

			}

			if ( this.spaces[ sourceColorSpace ].primaries !== this.spaces[ targetColorSpace ].primaries ) {

				color.applyMatrix3( this.spaces[ sourceColorSpace ].toXYZ );
				color.applyMatrix3( this.spaces[ targetColorSpace ].fromXYZ );

			}

			if ( this.spaces[ targetColorSpace ].transfer === SRGBTransfer ) {

				color.r = LinearToSRGB( color.r );
				color.g = LinearToSRGB( color.g );
				color.b = LinearToSRGB( color.b );

			}

			return color;

		},

		workingToColorSpace: function ( color, targetColorSpace ) {

			return this.convert( color, this.workingColorSpace, targetColorSpace );

		},

		colorSpaceToWorking: function ( color, sourceColorSpace ) {

			return this.convert( color, sourceColorSpace, this.workingColorSpace );

		},

		getPrimaries: function ( colorSpace ) {

			return this.spaces[ colorSpace ].primaries;

		},

		getTransfer: function ( colorSpace ) {

			if ( colorSpace === NoColorSpace ) return LinearTransfer;

			return this.spaces[ colorSpace ].transfer;

		},

		getLuminanceCoefficients: function ( target, colorSpace = this.workingColorSpace ) {

			return target.fromArray( this.spaces[ colorSpace ].luminanceCoefficients );

		},

		define: function ( colorSpaces ) {

			Object.assign( this.spaces, colorSpaces );

		},

		// Internal APIs

		_getMatrix: function ( targetMatrix, sourceColorSpace, targetColorSpace ) {

			return targetMatrix
				.copy( this.spaces[ sourceColorSpace ].toXYZ )
				.multiply( this.spaces[ targetColorSpace ].fromXYZ );

		},

		_getDrawingBufferColorSpace: function ( colorSpace ) {

			return this.spaces[ colorSpace ].outputColorSpaceConfig.drawingBufferColorSpace;

		},

		_getUnpackColorSpace: function ( colorSpace = this.workingColorSpace ) {

			return this.spaces[ colorSpace ].workingColorSpaceConfig.unpackColorSpace;

		},

		// Deprecated

		fromWorkingColorSpace: function ( color, targetColorSpace ) {

			warnOnce( 'THREE.ColorManagement: .fromWorkingColorSpace() has been renamed to .workingToColorSpace().' ); // @deprecated, r177

			return ColorManagement.workingToColorSpace( color, targetColorSpace );

		},

		toWorkingColorSpace: function ( color, sourceColorSpace ) {

			warnOnce( 'THREE.ColorManagement: .toWorkingColorSpace() has been renamed to .colorSpaceToWorking().' ); // @deprecated, r177

			return ColorManagement.colorSpaceToWorking( color, sourceColorSpace );

		},

	};

	/******************************************************************************
	 * sRGB definitions
	 */

	const REC709_PRIMARIES = [ 0.640, 0.330, 0.300, 0.600, 0.150, 0.060 ];
	const REC709_LUMINANCE_COEFFICIENTS = [ 0.2126, 0.7152, 0.0722 ];
	const D65 = [ 0.3127, 0.3290 ];

	ColorManagement.define( {

		[ LinearSRGBColorSpace ]: {
			primaries: REC709_PRIMARIES,
			whitePoint: D65,
			transfer: LinearTransfer,
			toXYZ: LINEAR_REC709_TO_XYZ,
			fromXYZ: XYZ_TO_LINEAR_REC709,
			luminanceCoefficients: REC709_LUMINANCE_COEFFICIENTS,
			workingColorSpaceConfig: { unpackColorSpace: SRGBColorSpace },
			outputColorSpaceConfig: { drawingBufferColorSpace: SRGBColorSpace }
		},

		[ SRGBColorSpace ]: {
			primaries: REC709_PRIMARIES,
			whitePoint: D65,
			transfer: SRGBTransfer,
			toXYZ: LINEAR_REC709_TO_XYZ,
			fromXYZ: XYZ_TO_LINEAR_REC709,
			luminanceCoefficients: REC709_LUMINANCE_COEFFICIENTS,
			outputColorSpaceConfig: { drawingBufferColorSpace: SRGBColorSpace }
		},

	} );

	return ColorManagement;

}
```
</details>

### `convert(color: any, sourceColorSpace: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `SRGBToLinear`
- `color.applyMatrix3`
- `LinearToSRGB`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace, targetColorSpace ) {

			if ( this.enabled === false || sourceColorSpace === targetColorSpace || ! sourceColorSpace || ! targetColorSpace ) {

				return color;

			}

			if ( this.spaces[ sourceColorSpace ].transfer === SRGBTransfer ) {

				color.r = SRGBToLinear( color.r );
				color.g = SRGBToLinear( color.g );
				color.b = SRGBToLinear( color.b );

			}

			if ( this.spaces[ sourceColorSpace ].primaries !== this.spaces[ targetColorSpace ].primaries ) {

				color.applyMatrix3( this.spaces[ sourceColorSpace ].toXYZ );
				color.applyMatrix3( this.spaces[ targetColorSpace ].fromXYZ );

			}

			if ( this.spaces[ targetColorSpace ].transfer === SRGBTransfer ) {

				color.r = LinearToSRGB( color.r );
				color.g = LinearToSRGB( color.g );
				color.b = LinearToSRGB( color.b );

			}

			return color;

		}
```
</details>

### `workingToColorSpace(color: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `this.convert`

<details><summary>Code</summary>

```typescript
function ( color, targetColorSpace ) {

			return this.convert( color, this.workingColorSpace, targetColorSpace );

		}
```
</details>

### `colorSpaceToWorking(color: any, sourceColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `this.convert`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace ) {

			return this.convert( color, sourceColorSpace, this.workingColorSpace );

		}
```
</details>

### `getPrimaries(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			return this.spaces[ colorSpace ].primaries;

		}
```
</details>

### `getTransfer(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			if ( colorSpace === NoColorSpace ) return LinearTransfer;

			return this.spaces[ colorSpace ].transfer;

		}
```
</details>

### `getLuminanceCoefficients(target: any, colorSpace: any): any`

**Parameters:**

- **`target`** `any`
- **`colorSpace`** `any`

**Returns:** `any`

**Calls:**

- `target.fromArray`

<details><summary>Code</summary>

```typescript
function ( target, colorSpace = this.workingColorSpace ) {

			return target.fromArray( this.spaces[ colorSpace ].luminanceCoefficients );

		}
```
</details>

### `define(colorSpaces: any): void`

**Parameters:**

- **`colorSpaces`** `any`

**Returns:** `void`

**Calls:**

- `Object.assign`

<details><summary>Code</summary>

```typescript
function ( colorSpaces ) {

			Object.assign( this.spaces, colorSpaces );

		}
```
</details>

### `_getMatrix(targetMatrix: any, sourceColorSpace: any, targetColorSpace: any): any`

**Parameters:**

- **`targetMatrix`** `any`
- **`sourceColorSpace`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `targetMatrix
				.copy( this.spaces[ sourceColorSpace ].toXYZ )
				.multiply`

<details><summary>Code</summary>

```typescript
function ( targetMatrix, sourceColorSpace, targetColorSpace ) {

			return targetMatrix
				.copy( this.spaces[ sourceColorSpace ].toXYZ )
				.multiply( this.spaces[ targetColorSpace ].fromXYZ );

		}
```
</details>

### `_getDrawingBufferColorSpace(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			return this.spaces[ colorSpace ].outputColorSpaceConfig.drawingBufferColorSpace;

		}
```
</details>

### `_getUnpackColorSpace(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace = this.workingColorSpace ) {

			return this.spaces[ colorSpace ].workingColorSpaceConfig.unpackColorSpace;

		}
```
</details>

### `fromWorkingColorSpace(color: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `warnOnce (from ../utils.js)`
- `ColorManagement.workingToColorSpace`

<details><summary>Code</summary>

```typescript
function ( color, targetColorSpace ) {

			warnOnce( 'THREE.ColorManagement: .fromWorkingColorSpace() has been renamed to .workingToColorSpace().' ); // @deprecated, r177

			return ColorManagement.workingToColorSpace( color, targetColorSpace );

		}
```
</details>

### `toWorkingColorSpace(color: any, sourceColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `warnOnce (from ../utils.js)`
- `ColorManagement.colorSpaceToWorking`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace ) {

			warnOnce( 'THREE.ColorManagement: .toWorkingColorSpace() has been renamed to .colorSpaceToWorking().' ); // @deprecated, r177

			return ColorManagement.colorSpaceToWorking( color, sourceColorSpace );

		}
```
</details>

### `convert(color: any, sourceColorSpace: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `SRGBToLinear`
- `color.applyMatrix3`
- `LinearToSRGB`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace, targetColorSpace ) {

			if ( this.enabled === false || sourceColorSpace === targetColorSpace || ! sourceColorSpace || ! targetColorSpace ) {

				return color;

			}

			if ( this.spaces[ sourceColorSpace ].transfer === SRGBTransfer ) {

				color.r = SRGBToLinear( color.r );
				color.g = SRGBToLinear( color.g );
				color.b = SRGBToLinear( color.b );

			}

			if ( this.spaces[ sourceColorSpace ].primaries !== this.spaces[ targetColorSpace ].primaries ) {

				color.applyMatrix3( this.spaces[ sourceColorSpace ].toXYZ );
				color.applyMatrix3( this.spaces[ targetColorSpace ].fromXYZ );

			}

			if ( this.spaces[ targetColorSpace ].transfer === SRGBTransfer ) {

				color.r = LinearToSRGB( color.r );
				color.g = LinearToSRGB( color.g );
				color.b = LinearToSRGB( color.b );

			}

			return color;

		}
```
</details>

### `workingToColorSpace(color: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `this.convert`

<details><summary>Code</summary>

```typescript
function ( color, targetColorSpace ) {

			return this.convert( color, this.workingColorSpace, targetColorSpace );

		}
```
</details>

### `colorSpaceToWorking(color: any, sourceColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `this.convert`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace ) {

			return this.convert( color, sourceColorSpace, this.workingColorSpace );

		}
```
</details>

### `getPrimaries(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			return this.spaces[ colorSpace ].primaries;

		}
```
</details>

### `getTransfer(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			if ( colorSpace === NoColorSpace ) return LinearTransfer;

			return this.spaces[ colorSpace ].transfer;

		}
```
</details>

### `getLuminanceCoefficients(target: any, colorSpace: any): any`

**Parameters:**

- **`target`** `any`
- **`colorSpace`** `any`

**Returns:** `any`

**Calls:**

- `target.fromArray`

<details><summary>Code</summary>

```typescript
function ( target, colorSpace = this.workingColorSpace ) {

			return target.fromArray( this.spaces[ colorSpace ].luminanceCoefficients );

		}
```
</details>

### `define(colorSpaces: any): void`

**Parameters:**

- **`colorSpaces`** `any`

**Returns:** `void`

**Calls:**

- `Object.assign`

<details><summary>Code</summary>

```typescript
function ( colorSpaces ) {

			Object.assign( this.spaces, colorSpaces );

		}
```
</details>

### `_getMatrix(targetMatrix: any, sourceColorSpace: any, targetColorSpace: any): any`

**Parameters:**

- **`targetMatrix`** `any`
- **`sourceColorSpace`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `targetMatrix
				.copy( this.spaces[ sourceColorSpace ].toXYZ )
				.multiply`

<details><summary>Code</summary>

```typescript
function ( targetMatrix, sourceColorSpace, targetColorSpace ) {

			return targetMatrix
				.copy( this.spaces[ sourceColorSpace ].toXYZ )
				.multiply( this.spaces[ targetColorSpace ].fromXYZ );

		}
```
</details>

### `_getDrawingBufferColorSpace(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			return this.spaces[ colorSpace ].outputColorSpaceConfig.drawingBufferColorSpace;

		}
```
</details>

### `_getUnpackColorSpace(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace = this.workingColorSpace ) {

			return this.spaces[ colorSpace ].workingColorSpaceConfig.unpackColorSpace;

		}
```
</details>

### `fromWorkingColorSpace(color: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `warnOnce (from ../utils.js)`
- `ColorManagement.workingToColorSpace`

<details><summary>Code</summary>

```typescript
function ( color, targetColorSpace ) {

			warnOnce( 'THREE.ColorManagement: .fromWorkingColorSpace() has been renamed to .workingToColorSpace().' ); // @deprecated, r177

			return ColorManagement.workingToColorSpace( color, targetColorSpace );

		}
```
</details>

### `toWorkingColorSpace(color: any, sourceColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `warnOnce (from ../utils.js)`
- `ColorManagement.colorSpaceToWorking`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace ) {

			warnOnce( 'THREE.ColorManagement: .toWorkingColorSpace() has been renamed to .colorSpaceToWorking().' ); // @deprecated, r177

			return ColorManagement.colorSpaceToWorking( color, sourceColorSpace );

		}
```
</details>

### `convert(color: any, sourceColorSpace: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `SRGBToLinear`
- `color.applyMatrix3`
- `LinearToSRGB`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace, targetColorSpace ) {

			if ( this.enabled === false || sourceColorSpace === targetColorSpace || ! sourceColorSpace || ! targetColorSpace ) {

				return color;

			}

			if ( this.spaces[ sourceColorSpace ].transfer === SRGBTransfer ) {

				color.r = SRGBToLinear( color.r );
				color.g = SRGBToLinear( color.g );
				color.b = SRGBToLinear( color.b );

			}

			if ( this.spaces[ sourceColorSpace ].primaries !== this.spaces[ targetColorSpace ].primaries ) {

				color.applyMatrix3( this.spaces[ sourceColorSpace ].toXYZ );
				color.applyMatrix3( this.spaces[ targetColorSpace ].fromXYZ );

			}

			if ( this.spaces[ targetColorSpace ].transfer === SRGBTransfer ) {

				color.r = LinearToSRGB( color.r );
				color.g = LinearToSRGB( color.g );
				color.b = LinearToSRGB( color.b );

			}

			return color;

		}
```
</details>

### `workingToColorSpace(color: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `this.convert`

<details><summary>Code</summary>

```typescript
function ( color, targetColorSpace ) {

			return this.convert( color, this.workingColorSpace, targetColorSpace );

		}
```
</details>

### `colorSpaceToWorking(color: any, sourceColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `this.convert`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace ) {

			return this.convert( color, sourceColorSpace, this.workingColorSpace );

		}
```
</details>

### `getPrimaries(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			return this.spaces[ colorSpace ].primaries;

		}
```
</details>

### `getTransfer(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			if ( colorSpace === NoColorSpace ) return LinearTransfer;

			return this.spaces[ colorSpace ].transfer;

		}
```
</details>

### `getLuminanceCoefficients(target: any, colorSpace: any): any`

**Parameters:**

- **`target`** `any`
- **`colorSpace`** `any`

**Returns:** `any`

**Calls:**

- `target.fromArray`

<details><summary>Code</summary>

```typescript
function ( target, colorSpace = this.workingColorSpace ) {

			return target.fromArray( this.spaces[ colorSpace ].luminanceCoefficients );

		}
```
</details>

### `define(colorSpaces: any): void`

**Parameters:**

- **`colorSpaces`** `any`

**Returns:** `void`

**Calls:**

- `Object.assign`

<details><summary>Code</summary>

```typescript
function ( colorSpaces ) {

			Object.assign( this.spaces, colorSpaces );

		}
```
</details>

### `_getMatrix(targetMatrix: any, sourceColorSpace: any, targetColorSpace: any): any`

**Parameters:**

- **`targetMatrix`** `any`
- **`sourceColorSpace`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `targetMatrix
				.copy( this.spaces[ sourceColorSpace ].toXYZ )
				.multiply`

<details><summary>Code</summary>

```typescript
function ( targetMatrix, sourceColorSpace, targetColorSpace ) {

			return targetMatrix
				.copy( this.spaces[ sourceColorSpace ].toXYZ )
				.multiply( this.spaces[ targetColorSpace ].fromXYZ );

		}
```
</details>

### `_getDrawingBufferColorSpace(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			return this.spaces[ colorSpace ].outputColorSpaceConfig.drawingBufferColorSpace;

		}
```
</details>

### `_getUnpackColorSpace(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace = this.workingColorSpace ) {

			return this.spaces[ colorSpace ].workingColorSpaceConfig.unpackColorSpace;

		}
```
</details>

### `fromWorkingColorSpace(color: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `warnOnce (from ../utils.js)`
- `ColorManagement.workingToColorSpace`

<details><summary>Code</summary>

```typescript
function ( color, targetColorSpace ) {

			warnOnce( 'THREE.ColorManagement: .fromWorkingColorSpace() has been renamed to .workingToColorSpace().' ); // @deprecated, r177

			return ColorManagement.workingToColorSpace( color, targetColorSpace );

		}
```
</details>

### `toWorkingColorSpace(color: any, sourceColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `warnOnce (from ../utils.js)`
- `ColorManagement.colorSpaceToWorking`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace ) {

			warnOnce( 'THREE.ColorManagement: .toWorkingColorSpace() has been renamed to .colorSpaceToWorking().' ); // @deprecated, r177

			return ColorManagement.colorSpaceToWorking( color, sourceColorSpace );

		}
```
</details>

### `convert(color: any, sourceColorSpace: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `SRGBToLinear`
- `color.applyMatrix3`
- `LinearToSRGB`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace, targetColorSpace ) {

			if ( this.enabled === false || sourceColorSpace === targetColorSpace || ! sourceColorSpace || ! targetColorSpace ) {

				return color;

			}

			if ( this.spaces[ sourceColorSpace ].transfer === SRGBTransfer ) {

				color.r = SRGBToLinear( color.r );
				color.g = SRGBToLinear( color.g );
				color.b = SRGBToLinear( color.b );

			}

			if ( this.spaces[ sourceColorSpace ].primaries !== this.spaces[ targetColorSpace ].primaries ) {

				color.applyMatrix3( this.spaces[ sourceColorSpace ].toXYZ );
				color.applyMatrix3( this.spaces[ targetColorSpace ].fromXYZ );

			}

			if ( this.spaces[ targetColorSpace ].transfer === SRGBTransfer ) {

				color.r = LinearToSRGB( color.r );
				color.g = LinearToSRGB( color.g );
				color.b = LinearToSRGB( color.b );

			}

			return color;

		}
```
</details>

### `workingToColorSpace(color: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `this.convert`

<details><summary>Code</summary>

```typescript
function ( color, targetColorSpace ) {

			return this.convert( color, this.workingColorSpace, targetColorSpace );

		}
```
</details>

### `colorSpaceToWorking(color: any, sourceColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `this.convert`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace ) {

			return this.convert( color, sourceColorSpace, this.workingColorSpace );

		}
```
</details>

### `getPrimaries(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			return this.spaces[ colorSpace ].primaries;

		}
```
</details>

### `getTransfer(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			if ( colorSpace === NoColorSpace ) return LinearTransfer;

			return this.spaces[ colorSpace ].transfer;

		}
```
</details>

### `getLuminanceCoefficients(target: any, colorSpace: any): any`

**Parameters:**

- **`target`** `any`
- **`colorSpace`** `any`

**Returns:** `any`

**Calls:**

- `target.fromArray`

<details><summary>Code</summary>

```typescript
function ( target, colorSpace = this.workingColorSpace ) {

			return target.fromArray( this.spaces[ colorSpace ].luminanceCoefficients );

		}
```
</details>

### `define(colorSpaces: any): void`

**Parameters:**

- **`colorSpaces`** `any`

**Returns:** `void`

**Calls:**

- `Object.assign`

<details><summary>Code</summary>

```typescript
function ( colorSpaces ) {

			Object.assign( this.spaces, colorSpaces );

		}
```
</details>

### `_getMatrix(targetMatrix: any, sourceColorSpace: any, targetColorSpace: any): any`

**Parameters:**

- **`targetMatrix`** `any`
- **`sourceColorSpace`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `targetMatrix
				.copy( this.spaces[ sourceColorSpace ].toXYZ )
				.multiply`

<details><summary>Code</summary>

```typescript
function ( targetMatrix, sourceColorSpace, targetColorSpace ) {

			return targetMatrix
				.copy( this.spaces[ sourceColorSpace ].toXYZ )
				.multiply( this.spaces[ targetColorSpace ].fromXYZ );

		}
```
</details>

### `_getDrawingBufferColorSpace(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			return this.spaces[ colorSpace ].outputColorSpaceConfig.drawingBufferColorSpace;

		}
```
</details>

### `_getUnpackColorSpace(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace = this.workingColorSpace ) {

			return this.spaces[ colorSpace ].workingColorSpaceConfig.unpackColorSpace;

		}
```
</details>

### `fromWorkingColorSpace(color: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `warnOnce (from ../utils.js)`
- `ColorManagement.workingToColorSpace`

<details><summary>Code</summary>

```typescript
function ( color, targetColorSpace ) {

			warnOnce( 'THREE.ColorManagement: .fromWorkingColorSpace() has been renamed to .workingToColorSpace().' ); // @deprecated, r177

			return ColorManagement.workingToColorSpace( color, targetColorSpace );

		}
```
</details>

### `toWorkingColorSpace(color: any, sourceColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `warnOnce (from ../utils.js)`
- `ColorManagement.colorSpaceToWorking`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace ) {

			warnOnce( 'THREE.ColorManagement: .toWorkingColorSpace() has been renamed to .colorSpaceToWorking().' ); // @deprecated, r177

			return ColorManagement.colorSpaceToWorking( color, sourceColorSpace );

		}
```
</details>

### `convert(color: any, sourceColorSpace: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `SRGBToLinear`
- `color.applyMatrix3`
- `LinearToSRGB`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace, targetColorSpace ) {

			if ( this.enabled === false || sourceColorSpace === targetColorSpace || ! sourceColorSpace || ! targetColorSpace ) {

				return color;

			}

			if ( this.spaces[ sourceColorSpace ].transfer === SRGBTransfer ) {

				color.r = SRGBToLinear( color.r );
				color.g = SRGBToLinear( color.g );
				color.b = SRGBToLinear( color.b );

			}

			if ( this.spaces[ sourceColorSpace ].primaries !== this.spaces[ targetColorSpace ].primaries ) {

				color.applyMatrix3( this.spaces[ sourceColorSpace ].toXYZ );
				color.applyMatrix3( this.spaces[ targetColorSpace ].fromXYZ );

			}

			if ( this.spaces[ targetColorSpace ].transfer === SRGBTransfer ) {

				color.r = LinearToSRGB( color.r );
				color.g = LinearToSRGB( color.g );
				color.b = LinearToSRGB( color.b );

			}

			return color;

		}
```
</details>

### `workingToColorSpace(color: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `this.convert`

<details><summary>Code</summary>

```typescript
function ( color, targetColorSpace ) {

			return this.convert( color, this.workingColorSpace, targetColorSpace );

		}
```
</details>

### `colorSpaceToWorking(color: any, sourceColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `this.convert`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace ) {

			return this.convert( color, sourceColorSpace, this.workingColorSpace );

		}
```
</details>

### `getPrimaries(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			return this.spaces[ colorSpace ].primaries;

		}
```
</details>

### `getTransfer(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			if ( colorSpace === NoColorSpace ) return LinearTransfer;

			return this.spaces[ colorSpace ].transfer;

		}
```
</details>

### `getLuminanceCoefficients(target: any, colorSpace: any): any`

**Parameters:**

- **`target`** `any`
- **`colorSpace`** `any`

**Returns:** `any`

**Calls:**

- `target.fromArray`

<details><summary>Code</summary>

```typescript
function ( target, colorSpace = this.workingColorSpace ) {

			return target.fromArray( this.spaces[ colorSpace ].luminanceCoefficients );

		}
```
</details>

### `define(colorSpaces: any): void`

**Parameters:**

- **`colorSpaces`** `any`

**Returns:** `void`

**Calls:**

- `Object.assign`

<details><summary>Code</summary>

```typescript
function ( colorSpaces ) {

			Object.assign( this.spaces, colorSpaces );

		}
```
</details>

### `_getMatrix(targetMatrix: any, sourceColorSpace: any, targetColorSpace: any): any`

**Parameters:**

- **`targetMatrix`** `any`
- **`sourceColorSpace`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `targetMatrix
				.copy( this.spaces[ sourceColorSpace ].toXYZ )
				.multiply`

<details><summary>Code</summary>

```typescript
function ( targetMatrix, sourceColorSpace, targetColorSpace ) {

			return targetMatrix
				.copy( this.spaces[ sourceColorSpace ].toXYZ )
				.multiply( this.spaces[ targetColorSpace ].fromXYZ );

		}
```
</details>

### `_getDrawingBufferColorSpace(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			return this.spaces[ colorSpace ].outputColorSpaceConfig.drawingBufferColorSpace;

		}
```
</details>

### `_getUnpackColorSpace(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace = this.workingColorSpace ) {

			return this.spaces[ colorSpace ].workingColorSpaceConfig.unpackColorSpace;

		}
```
</details>

### `fromWorkingColorSpace(color: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `warnOnce (from ../utils.js)`
- `ColorManagement.workingToColorSpace`

<details><summary>Code</summary>

```typescript
function ( color, targetColorSpace ) {

			warnOnce( 'THREE.ColorManagement: .fromWorkingColorSpace() has been renamed to .workingToColorSpace().' ); // @deprecated, r177

			return ColorManagement.workingToColorSpace( color, targetColorSpace );

		}
```
</details>

### `toWorkingColorSpace(color: any, sourceColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `warnOnce (from ../utils.js)`
- `ColorManagement.colorSpaceToWorking`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace ) {

			warnOnce( 'THREE.ColorManagement: .toWorkingColorSpace() has been renamed to .colorSpaceToWorking().' ); // @deprecated, r177

			return ColorManagement.colorSpaceToWorking( color, sourceColorSpace );

		}
```
</details>

### `convert(color: any, sourceColorSpace: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `SRGBToLinear`
- `color.applyMatrix3`
- `LinearToSRGB`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace, targetColorSpace ) {

			if ( this.enabled === false || sourceColorSpace === targetColorSpace || ! sourceColorSpace || ! targetColorSpace ) {

				return color;

			}

			if ( this.spaces[ sourceColorSpace ].transfer === SRGBTransfer ) {

				color.r = SRGBToLinear( color.r );
				color.g = SRGBToLinear( color.g );
				color.b = SRGBToLinear( color.b );

			}

			if ( this.spaces[ sourceColorSpace ].primaries !== this.spaces[ targetColorSpace ].primaries ) {

				color.applyMatrix3( this.spaces[ sourceColorSpace ].toXYZ );
				color.applyMatrix3( this.spaces[ targetColorSpace ].fromXYZ );

			}

			if ( this.spaces[ targetColorSpace ].transfer === SRGBTransfer ) {

				color.r = LinearToSRGB( color.r );
				color.g = LinearToSRGB( color.g );
				color.b = LinearToSRGB( color.b );

			}

			return color;

		}
```
</details>

### `workingToColorSpace(color: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `this.convert`

<details><summary>Code</summary>

```typescript
function ( color, targetColorSpace ) {

			return this.convert( color, this.workingColorSpace, targetColorSpace );

		}
```
</details>

### `colorSpaceToWorking(color: any, sourceColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `this.convert`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace ) {

			return this.convert( color, sourceColorSpace, this.workingColorSpace );

		}
```
</details>

### `getPrimaries(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			return this.spaces[ colorSpace ].primaries;

		}
```
</details>

### `getTransfer(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			if ( colorSpace === NoColorSpace ) return LinearTransfer;

			return this.spaces[ colorSpace ].transfer;

		}
```
</details>

### `getLuminanceCoefficients(target: any, colorSpace: any): any`

**Parameters:**

- **`target`** `any`
- **`colorSpace`** `any`

**Returns:** `any`

**Calls:**

- `target.fromArray`

<details><summary>Code</summary>

```typescript
function ( target, colorSpace = this.workingColorSpace ) {

			return target.fromArray( this.spaces[ colorSpace ].luminanceCoefficients );

		}
```
</details>

### `define(colorSpaces: any): void`

**Parameters:**

- **`colorSpaces`** `any`

**Returns:** `void`

**Calls:**

- `Object.assign`

<details><summary>Code</summary>

```typescript
function ( colorSpaces ) {

			Object.assign( this.spaces, colorSpaces );

		}
```
</details>

### `_getMatrix(targetMatrix: any, sourceColorSpace: any, targetColorSpace: any): any`

**Parameters:**

- **`targetMatrix`** `any`
- **`sourceColorSpace`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `targetMatrix
				.copy( this.spaces[ sourceColorSpace ].toXYZ )
				.multiply`

<details><summary>Code</summary>

```typescript
function ( targetMatrix, sourceColorSpace, targetColorSpace ) {

			return targetMatrix
				.copy( this.spaces[ sourceColorSpace ].toXYZ )
				.multiply( this.spaces[ targetColorSpace ].fromXYZ );

		}
```
</details>

### `_getDrawingBufferColorSpace(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace ) {

			return this.spaces[ colorSpace ].outputColorSpaceConfig.drawingBufferColorSpace;

		}
```
</details>

### `_getUnpackColorSpace(colorSpace: any): any`

**Parameters:**

- **`colorSpace`** `any`

**Returns:** `any`

<details><summary>Code</summary>

```typescript
function ( colorSpace = this.workingColorSpace ) {

			return this.spaces[ colorSpace ].workingColorSpaceConfig.unpackColorSpace;

		}
```
</details>

### `fromWorkingColorSpace(color: any, targetColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`targetColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `warnOnce (from ../utils.js)`
- `ColorManagement.workingToColorSpace`

<details><summary>Code</summary>

```typescript
function ( color, targetColorSpace ) {

			warnOnce( 'THREE.ColorManagement: .fromWorkingColorSpace() has been renamed to .workingToColorSpace().' ); // @deprecated, r177

			return ColorManagement.workingToColorSpace( color, targetColorSpace );

		}
```
</details>

### `toWorkingColorSpace(color: any, sourceColorSpace: any): any`

**Parameters:**

- **`color`** `any`
- **`sourceColorSpace`** `any`

**Returns:** `any`

**Calls:**

- `warnOnce (from ../utils.js)`
- `ColorManagement.colorSpaceToWorking`

<details><summary>Code</summary>

```typescript
function ( color, sourceColorSpace ) {

			warnOnce( 'THREE.ColorManagement: .toWorkingColorSpace() has been renamed to .colorSpaceToWorking().' ); // @deprecated, r177

			return ColorManagement.colorSpaceToWorking( color, sourceColorSpace );

		}
```
</details>

### `SRGBToLinear(c: any): number`

**Parameters:**

- **`c`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
export function SRGBToLinear( c ) {

	return ( c < 0.04045 ) ? c * 0.0773993808 : Math.pow( c * 0.9478672986 + 0.0521327014, 2.4 );

}
```
</details>

### `LinearToSRGB(c: any): number`

**Parameters:**

- **`c`** `any`

**Returns:** `number`

**Calls:**

- `Math.pow`

<details><summary>Code</summary>

```typescript
export function LinearToSRGB( c ) {

	return ( c < 0.0031308 ) ? c * 12.92 : 1.055 * ( Math.pow( c, 0.41666 ) ) - 0.055;

}
```
</details>


---